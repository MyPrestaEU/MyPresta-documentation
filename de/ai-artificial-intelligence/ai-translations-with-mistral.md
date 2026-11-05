---
title: "AI Translations with Mistral – Dokumentation und Benutzerhandbuch"
description: "Anleitung zur Konfiguration und Fehlersuche für alle, die das Modul AI Translations with Mistral nutzen."
sidebar:
  label: "AI Translations with Mistral – Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul AI Translations with Mistral auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/ai-translations-with-mistral/)
>
> ---


## 1. Anforderungen

Das Modul funktioniert mit PrestaShop ab Version 1.7.0.0.

- **PrestaShop:** 1.7.0.0 oder neuer.
- **PHP:** die Version, die Ihre PrestaShop-Version voraussetzt. Das Modul legt keine eigene Mindestversion fest.
- **PHP-Erweiterungen:** cURL (Verbindung zu Mistral), OpenSSL (Verschlüsselung des API-Schlüssels), SimpleXML (Lesen der XLF-Übersetzungsdateien), mbstring.
- **Andere Module:** Das Modul ist von keinem anderen Modul abhängig.
- **Außerhalb des Shops:** ein Konto bei Mistral AI und ein API-Schlüssel, den Sie unter https://console.mistral.ai/api-keys erstellen. Der Server Ihres Shops muss ausgehende HTTPS-Verbindungen zu `api.mistral.ai` aufbauen dürfen.
- **Optional:** eine geplante Aufgabe auf dem Server, die die Cron-Adresse aufruft (siehe 3.1). Ohne sie bearbeiten Sie Aufträge manuell im Tab **Jobs**.
- **Große Kataloge:** Wenn Sie eine ganze Domain mit Tausenden Texten übersetzen, sind das viele API-Aufrufe und eine lange Laufzeit. Der Auftrag wird in Portionen aufgeteilt, deren Größe unter **Batch size** festgelegt ist. Führen Sie vor dem Start in **Bulk** immer **Estimate** aus.
- Der Shop braucht mindestens zwei Sprachen. Bei nur einer Sprache zeigt das Back Office eine Warnung, denn dann gibt es nichts zu übersetzen.

## 2. Installation

1. Öffnen Sie **Modules** → **Module Manager**, klicken Sie auf **Upload a module**, laden Sie die ZIP-Datei des Moduls hoch und klicken Sie bei **AI Translations with Mistral** auf **Install**.
2. Nach der Installation erscheint **AI Translations with Mistral** im Menü **International**.
3. Die Installation leert den Shop-Cache nicht. Beim Speichern einer Übersetzung leert das Modul den PrestaShop-Cache selbst.
4. Öffnen Sie **AI Translations with Mistral** → **Settings** und fügen Sie Ihren Mistral-Schlüssel ein. Solange kein Schlüssel gespeichert ist, zeigt das Back Office die Meldung **No Mistral API key.**

**Deinstallation.** Klicken Sie im **Module Manager** auf **Uninstall** und bestätigen Sie die Abfrage **Delete this module and its data (jobs, glossary, cache)?**

- Entfernt werden: der Menüeintrag, alle Aufträge, das Glossar, die Ausschlüsse, der Verlauf der Aufrufe, die Warteschlange **Review**, die Sicherungskopien für das Zurücksetzen, die Kostenübersicht und die Einstellungen des Moduls (einschließlich des API-Schlüssels).
- Erhalten bleiben die Texte, die das Modul im Shop gespeichert hat, also die Übersetzungen im PrestaShop-Katalog und die Übersetzungsdateien klassischer Module, in die das Modul geschrieben hat. Auch die Einstellungen für die Update-Prüfung bleiben bestehen.
- Eine erneute Installation stellt gelöschte Aufträge, das Glossar und den Verlauf nicht wieder her. Sie setzt die Standardwerte und legt eine neue Cron-Adresse an.

## 3. Konfiguration und Arbeit im Back Office

Das gesamte Modul befindet sich auf einer Seite: **International** → **AI Translations with Mistral**. Oben stehen die Tabs **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** und **Settings**. Der Tab **Updates** steht ganz rechts in der Leiste. Die Schaltfläche **Help** öffnet ein Panel, das den aktuellen Tab erklärt.

Die Namen der Felder und Schaltflächen in dieser Anleitung entsprechen dem englischen Back Office. Ist Ihr Back Office auf eine andere Sprache eingestellt, sehen Sie die übersetzten Bezeichnungen. Auch die Screenshots stammen aus dem englischen Back Office.

Jeder Tab beginnt mit einem Satz, der erklärt, was der Tab tut, wie man ihn benutzt und was dabei passiert. Dieselbe Erklärung steht, in drei Teilen gegliedert, auch unter den Formularfeldern. Die Schaltfläche **Help** unten rechts zeigt sie für den aktuellen Tab an. Das bloße Öffnen von **Help** übersetzt nichts.

**Der Ablauf von Anfang bis Ende**

Eine Übersetzung startet immer ein Mitarbeiter im Back Office. Kunden im Shop lösen nichts aus.

1. **Einstellungen.** Fügen Sie in **Settings** Ihren Mistral-Schlüssel ein und wählen Sie Modell und Quellsprache. Klicken Sie auf **Test connection** und danach auf **Save**. Ohne Schlüssel kann keine der Methoden Text an Mistral senden.
2. **Wählen Sie Ihren Arbeitsweg.**
   - Ein paar Sätze oder eine Domain, mit Prüfung vor dem Speichern: **Manual** (3.3).
   - Eine große Domain, ein Theme oder ein Modul: **Bulk**, danach bearbeiten Sie den Auftrag in **Jobs** (3.4, 3.5).
   - Felder von Produkten, Kategorien und CMS-Seiten: **Catalog** (Stapel mit bis zu 100 Datensätzen, 3.7).
   - Einzelne Felder auf der Seite **International → Translations** (3.12) sowie in den Formularen für Produkte, Kategorien und CMS (3.13).
3. **Qualitätsprüfung.** Jeder übersetzte Text wird kontrolliert: Variablen, Markierungen und HTML. Ein Text, der die Prüfung nicht besteht, wird nicht gespeichert. Ein Text mit einer Bewertung unter 70, der mehr als zweieinhalbmal so lang ist wie das Original oder noch englische Wörter enthält, landet in **Review**.
4. **Speichern.** Das hängt vom gewählten Arbeitsweg ab:
   - **Manual:** Nach **Translate selected (review)** wird nichts gespeichert, bis Sie **Save approved** klicken. Mit dem Häkchen bei **Save now (skip review)** speichern Sie die korrekten Zeilen sofort.
   - **Bulk:** Der Auftrag wartet in **Jobs** und wird erst gespeichert, wenn Sie ihn verarbeiten (**Process slice**, **Auto-process**) oder der Cron es übernimmt. Ein Probelauf (Dry-run) speichert nie etwas.
   - **Catalog:** Speichert Zeilen sofort in der gewählten Zielsprache.
   - **Die Seite International → Translations und die Shop-Formulare:** Die Schaltflächen füllen nur die Felder. Der Text erreicht den Shop erst, wenn Sie in PrestaShop auf **Save** klicken.
   - Bei ausgeschaltetem **Allow publish / save** speichert keiner dieser Wege Text im Shop.
5. **Abschluss.** Ein Auftrag in **Jobs** endet mit dem Status **completed** (alles gespeichert) oder **completed_with_errors** (es gab Fehler, siehe 3.5). Zeilen in **Review** verschwinden nach **Approve** oder **Reject**. Das Ergebnis von **Catalog** zeigt, wie viele Zeilen gespeichert wurden und wie viele fehlgeschlagen sind.

### 3.1. Konfigurationsseite des Moduls

Öffnen Sie **Modules** → **Module Manager**, suchen Sie **AI Translations with Mistral** und klicken Sie auf **Configure**. Das **Dashboard** öffnet sich. Wechseln Sie zum Tab **Settings**.

**Settings** ist ein einziges Formular. Die Felder erscheinen in der unten beschriebenen Reihenfolge. Die Schaltflächen **Save** und **Test connection** finden Sie unten im Formular, nicht oben.

![Einstellungen: Schlüssel, Modell, Ton und Quellsprache. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings.webp)

![Schalter für die Schaltflächen an den Feldern sowie Limits. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-fields.webp)

![Kosten, E-Mail, Cron-Adresse sowie die Schaltflächen Test connection und Save. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-cron.webp)

**Verbindung**

| Feld | Standard | Funktion |
|---|---|---|
| **Mistral API key** | leer | Der Schlüssel aus Ihrem Mistral-Konto. Kopieren Sie ihn von https://console.mistral.ai/api-keys. Lassen Sie das Feld leer, um einen bereits gespeicherten Schlüssel zu behalten. Ein neuer Wert ersetzt den gespeicherten Schlüssel, ein leeres Feld löscht ihn nicht. Der gespeicherte Schlüssel wird maskiert angezeigt. |
| **Model** | mistral-small-latest | Das Mistral-Modell, das übersetzt. Zur Auswahl stehen mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest und codestral-latest. Die Auswahl gilt ab der nächsten Übersetzung. Kann Ihr Konto ein Modell nicht nutzen, bricht der Aufruf ab und der Fehler wird in **History** vermerkt. |
| **Add a Mistral model** | leer | Ein Feld unter der Modellliste. Geben Sie die genaue Modellkennung aus Ihrem Konto ein und klicken Sie auf **Add model**. Das neue Modell erscheint in der Liste und wird aktiv. Darunter sehen Sie die von Hand ergänzten Modelle, jeweils mit einer Schaltfläche **Remove**. Eingebaute Modelle lassen sich nicht entfernen. |

Meldungen nach diesen Aktionen: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example mistral-small-latest.**, **Built-in models cannot be removed.**

**Stil und Sprache**

| Feld | Standard | Funktion |
|---|---|---|
| **Tone** | Formal | Fügt jeder Anfrage einen Stil hinzu: **Formal** für einen offiziellen Ton im Shop und im Back Office, **Casual** für einen lockereren Ton und **Brand** zusammen mit dem Feld **Brand voice**. Neue Übersetzungen übernehmen den gewählten Stil. Bestehende bleiben unverändert, bis Sie sie erneut übersetzen lassen. |
| **Brand voice** | leer | Erscheint, sobald Sie **Tone: Brand** wählen. Einige Sätze, die beschreiben, wie der Shop klingen soll. Ein leeres Feld bedeutet, dass keine zusätzliche Beschreibung mitgeschickt wird. Der Text fließt in künftige Anfragen ein, ändert aber keine bereits gespeicherten Übersetzungen. |
| **Source locale** | — | Die Sprache, die das Modell als Original behandelt. In der Regel wählen Sie en-US, also die Sprache, in der Sie Ihre Kataloge verfassen. Das Zeichen **—** bedeutet, dass die Quellsprache vom Bildschirm kommt, auf dem Sie gerade übersetzen. Diese Einstellung ändert nicht die Standardsprache des Shops. |
| **Individual field buttons — shop forms** | Yes | Eine Übersetzungsschaltfläche neben jedem mehrsprachigen Feld in den Shop-Formularen, also bei Produkten, Kategorien, CMS-Seiten und weiteren. Jede Schaltfläche übersetzt nur ihr eigenes Feld. Mit **No** blenden Sie diese Schaltflächen im gesamten Shop aus. Gespeicherte Übersetzungen bleiben unverändert. |
| **Individual field checkboxes — shop forms** | Yes | Mehrsprachige Felder in den Shop-Formularen bekommen Kontrollkästchen. Die Leiste am Ende des Formulars übersetzt die markierten Felder nacheinander. Bei **No** verschwinden Kontrollkästchen und Leiste. |
| **Individual field buttons — International → Translations** | Yes | Eine Schaltfläche neben jedem Feld auf der Seite **International → Translations**. Die Shop-Formulare bleiben davon unberührt. |
| **Individual field checkboxes — International → Translations** | Yes | Kontrollkästchen und Leiste auf der Seite **International → Translations**. Bei **No** verschwinden sie nur auf dieser Seite. |

**Limits und Kosten**

| Feld | Standard | Funktion |
|---|---|---|
| **Batch size** | 25 | Wie viele Texte in einen Aufruf gehen. Für den ersten Lauf empfehlen sich 10 bis 25. Der Wert bleibt im Bereich 1–100. Größere Portionen beenden einen Auftrag mit weniger Aufrufen; schlägt ein Aufruf fehl, wird eine größere Portion wiederholt. |
| **Dry-run sample** | 10 | Wie viele Beispieltexte **Estimate** in **Bulk** anzeigt. Der Wert bleibt im Bereich 1–50. Die Schätzung speichert nichts. |
| **Max tokens (0 = default)** | 0 | Die Längenbegrenzung für eine einzelne Antwort. Geben Sie 0 ein, um das Standardlimit von Mistral zu nutzen. Setzen Sie einen eigenen Wert, wenn Antworten abgeschnitten oder zu lang werden. Die Änderung gilt ab dem nächsten Aufruf. |
| **Budget USD / month** | 0 | Eine monatliche Obergrenze in US-Dollar, berechnet aus der Kostenübersicht. Geben Sie 0 ein, wenn es keine Grenze geben soll. Ist der Betrag erreicht, werden neue Übersetzungen angehalten. Bereits Erledigtes bleibt erhalten. |
| **Rate limit / min** | 60 | Wie viele API-Aufrufe der Shop pro Minute ausführen darf. Geben Sie 0 ein, um diese lokale Begrenzung auszuschalten. Aufrufe über dem Limit werden übersprungen und in **History** vermerkt. Mistral kann zusätzlich eine eigene Begrenzung anwenden. |
| **Temperature** | 0.2 | Wie frei das Modell den Text umformuliert. Bei etwa 0.2 bleibt es nah am Original, höhere Werte bis 1 verändern die Sätze stärker. Der Bereich ist 0–1. Die Prüfung von Variablen und HTML bleibt in jedem Fall aktiv. |
| **Log retention days** | 30 | Wie viele Tage Einträge in **History** bleiben. Das Minimum ist 1. Ältere Einträge werden gelöscht. Aufträge, Glossar und gespeicherte Übersetzungen bleiben unberührt. |
| **Allow publish / save** | Yes | Ob das Modul Übersetzungen im Shop speichern darf. Bei **No** ist das Speichern in **Manual** (Schaltflächen **Save approved** und **Save now**), in **Bulk** (Aufträge ohne Probelauf) und in **Catalog** gesperrt. Die Schaltflächen auf den Seiten füllen nur die Felder; gespeichert wird von PrestaShop. |

Meldungen nach **Save**:

- **Settings saved. No translation was started.** (grün) – die Einstellungen sind gespeichert, es wurde nichts übersetzt.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** (gelb) – es ist noch kein Schlüssel hinterlegt; fügen Sie einen ein.

**E-Mail und Cron**

| Feld | Standard | Funktion |
|---|---|---|
| **Email notify on complete** | No | Verschickt eine E-Mail, sobald ein Auftrag aus **Bulk** abgeschlossen ist. Der Auftrag selbst läuft genauso; nur der Versand kommt dazu. |
| **Notify email** | leer | Die Empfängeradresse für die E-Mail über den Abschluss des Auftrags. Das Feld erscheint, sobald **Email notify on complete** eingeschaltet ist. Das bloße Speichern der Adresse verschickt noch keine Nachricht. |
| **CRON URL** | Adresse mit Token | Eine Adresse, die Ihr Server aufrufen kann, um eine Portion eines wartenden Auftrags zu verarbeiten. Jeder Aufruf bearbeitet eine Portion und endet dann. Veröffentlichen Sie diese Adresse nicht, denn wer sie kennt, kann eine Portion starten. Das Öffnen von **Settings** startet keinen Auftrag. |

**Test connection** prüft Schlüssel und Modell mit einer kurzen Anfrage. Dabei wird nichts übersetzt und nichts gespeichert. Mögliche Ergebnisse:

- **Connection OK (N ms). No translation was started.** – die Verbindung funktioniert.
- **Connection was not made. Nothing was translated.** mit einem Grund – prüfen Sie Schlüssel und Modell.

So starten Sie am besten: Fügen Sie den Schlüssel ein, wählen Sie Modell und Quellsprache und klicken Sie auf **Test connection**. Lassen Sie die übrigen Werte auf den Standardeinstellungen, bis sich ein Auftrag auffällig verhält.

### 3.2. Dashboard

Zu finden unter: der erste Tab **Dashboard**.

![Übersicht der fehlenden Texte, Verlaufsfilter und Karten der Aufrufe. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard.webp)

![Diagramme der Aufrufe und Tokens. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-charts.webp)

![Auswertungen sowie die zehn letzten Aufrufe. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-latest.webp)

Das Dashboard besteht aus zwei Teilen. Der erste zeigt, welche Texte noch keine Übersetzung haben. Der zweite zeigt den Verlauf der Mistral-Aufrufe als Karten und Diagramme. Die Seite übersetzt nichts und ändert keine Texte.

**Übersicht der fehlenden Texte**

- **Locale:** Wählen Sie die Sprache, für die Sie die fehlenden Texte zählen möchten.
- **Show:** aktualisiert die Tabelle für die gewählte Sprache.
- Die Tabelle hat die Spalten **Section**, **Total**, **Missing** und **Done**. In der Spalte **Done** steht ein Fortschrittsbalken. Die Bereiche heißen **Back office**, **Themes**, **Installed modules**, **Emails** und **Others**. **Missing** ist die Zahl der Texte ohne Übersetzung in dieser Sprache.
- Nach **Show** erscheint die Meldung **Coverage for [Sprache]. This page only counts strings. Nothing was translated.**
- Unter der Tabelle steht eine Zeile **CRON** mit der Cron-Adresse, dieselbe wie in **Settings**.
- Eine leere Tabelle heißt, dass der Shop für diese Sprache noch keinen Katalog hat. Den legen Sie unter **International → Translations** an.

**Verlauf der Aufrufe**

- **Filter** arbeitet mit den Vorlagen **Today**, **7 days**, **30 days**, **This month** und **All time** sowie mit den Feldern **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** und **Prompt or reply contains**.
- Die Karten zeigen **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** und **Estimated cost**. Die Kosten sind eine Schätzung, keine Rechnung.
- Diagramme: **Requests and errors**, **Tokens sent and received**, **Requests by model**.
- Unter den Diagrammen stehen fünf Auswertungen: **By day**, **By model**, **By type**, **By language** und **By employee**. Gibt es im gewählten Zeitraum Aufrufe, ist jede Auswertung eine Tabelle mit den Spalten **Group**, **Calls**, **Sent**, **Received** und **Total**. Gibt es keine, sehen Sie **No requests in this range.**
- **Latest prompts** zeigt die zehn letzten Aufrufe mit den Spalten **When**, **Status**, **Type**, **Languages** und **Preview**. Ist die Liste leer, steht dort **No requests yet.** Mit **View** öffnen Sie ein Fenster mit der gesendeten Anweisung und der Antwort. **See all** führt zu **History** (3.10).

Was als Nächstes zu tun ist: Fehlen in einem Bereich die meisten Texte, öffnen Sie **Manual** für einige Texte oder **Bulk** für die ganze Domain.

### 3.3. Manual

Zu finden unter: Tab **Manual**.

![Filter von Manual. Die Schaltfläche Filter befindet sich unter dem Feld Search. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-manual.webp)

**Manual** übersetzt eine Domain oder ein Modul, jeweils einige Dutzend Texte auf einmal. Das Filtern selbst speichert nichts.

**Filterfelder**

| Feld | Standard | Funktion |
|---|---|---|
| **Section** | Back office | Wählt den PrestaShop-Katalog, der gelesen wird: **Back office**, **Themes**, **Installed modules**, **Emails** oder **Others**. Ein Wechsel lädt die Seite neu, zeigt nur die Felder dieses Bereichs und ruft Mistral nicht auf. |
| **Theme** | — | Nur sichtbar bei **Themes**. Beschränkt die Liste auf ein Theme. Andere Themes werden übersprungen. |
| **Module** | — | Nur sichtbar bei **Installed modules**. Beschränkt die Liste auf ein Modul. Ein Modul ohne Domains (klassisch) zeigt alle seine Texte auf einmal. |
| **Domain** | — | Eine Textgruppe, dieselbe wie unter **International → Translations**. Wählen Sie sie und klicken Sie auf **Filter**. Bei klassischen Modulen und bei Bereichen ohne Domains ist das Feld ausgeblendet. |
| **Source** | en-US oder der Wert aus **Settings** | Die Sprache, aus der Sie die Texte übernehmen. Wählen Sie eine Sprache, die bereits gute Übersetzungen hat. |
| **Target** | erste Sprache der Liste | Die Sprache, die Sie ergänzen möchten. Sie muss unter **International → Localization → Languages** existieren. |
| **Only empty** | Yes | Zeigt nur Texte ohne Übersetzung. Schalten Sie es aus, um alle Texte zu sehen. Gespeicherte Übersetzungen werden nicht gelöscht. |
| **Search** | leer | Zeigt nur Quelltexte, die das eingegebene Wort enthalten. |

Schritte:

1. Stellen Sie **Section**, **Source** und **Target** ein.
2. Bei **Themes** wählen Sie ein **Theme**. Bei **Installed modules** wählen Sie ein **Module**.
3. Klicken Sie auf **Filter**. Die Liste **Domain** wird aktualisiert. Wählen Sie eine Domain und klicken Sie erneut auf **Filter**. Bei einem klassischen Modul lassen Sie die Domain weg: **Filter** lädt dann alle Texte des Moduls.
4. Markieren Sie die gewünschten Zeilen. Dafür gibt es **Check all**, **Uncheck all** und die Kontrollkästchen neben den Zeilen.
5. Nach **Filter** zeigt die Liste die Spalten **Source**, **Current** und **Status** (**empty** oder **filled**). Oberhalb der Liste finden Sie **Translate selected (review)** und das Kontrollkästchen **Save now (skip review)**.
6. Klicken Sie auf **Translate selected (review)**. Es erscheint die Tabelle **Review before save** mit den Spalten Kontrollkästchen, **Source**, **AI proposal** und **Warnings**. Zeilen, die die Prüfung bestanden haben, sind bereits markiert. Entfernen Sie die Markierung bei Zeilen, die Sie nicht übernehmen möchten, und korrigieren Sie bei Bedarf den Vorschlag direkt im Feld. Mit **Save approved** speichern Sie die markierten Zeilen.
7. Statt Schritt 6 können Sie vor dem Übersetzen **Save now (skip review)** aktivieren. Dann werden die Zeilen, die die Prüfung bestehen, sofort gespeichert, ohne die Prüftabelle.

**Meldungen**

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – die Liste ist bereit.
- **No strings match this filter. Nothing was sent to Mistral.** – ändern Sie den Filter oder deaktivieren Sie **Only empty**.
- **Nothing was translated. Choose a domain, then press Filter to load the strings.** – wählen Sie zuerst eine Domain.
- **Nothing was translated. Tick at least one row.** – markieren Sie mindestens eine Zeile.
- **Review is ready. Nothing is saved until you press Save approved.** – die Übersetzungen sind fertig; gespeichert wird erst nach **Save approved**.
- **Saved. The approved strings were written for the target language.** – nach **Save now (skip review)** wurden die korrekten Zeilen gespeichert.
- **Saved N. Only the ticked rows were written.** – nach **Save approved** wurden die markierten Zeilen gespeichert.
- **Nothing was saved. Tick OK on the rows you want to keep.** – in der Prüftabelle war keine Zeile markiert. Markieren Sie die gewünschten Zeilen und klicken Sie erneut auf **Save approved**.
- **Not saved because of broken placeholders or HTML: N.** – N Zeilen haben die Prüfung nicht bestanden und wurden übersprungen. Korrigieren Sie sie von Hand in der Tabelle, sodass Variablen und HTML-Markierungen dem Original entsprechen.
- **Nothing was saved. Turn on Allow publish in Settings.** – schalten Sie **Allow publish / save** ein.
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.** – die Liste hat sich geändert. Klicken Sie auf **Filter** und markieren Sie die Zeilen erneut.
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – klassisches Modul ohne Domains. Die vollständige Liste ist geladen.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Mistral.** – derselbe Fall, bevor Sie auf **Filter** klicken.
- **Nothing was translated. Pick a theme, then press Filter.** / **Nothing was translated. Pick a module, then press Filter.** – wählen Sie ein Theme oder ein Modul.

### 3.4. Bulk

Zu finden unter: Tab **Bulk**.

![Umfang eines Bulk-Auftrags. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk.webp)

![Richtlinie, Probelauf ohne Speichern sowie die Schaltflächen Start job und Estimate. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk-actions.webp)

**Bulk** legt einen Auftrag an, der mehrere Domains und Sprachen umfasst. Die Schätzung speichert nichts. **Start job** fügt den Auftrag der Liste **Jobs** hinzu. Gespeichert wird erst, wenn der Auftrag verarbeitet wird und **Allow publish / save** eingeschaltet ist.

**Felder**

| Feld | Standard | Funktion |
|---|---|---|
| **Section** | Back office | Welchen Katalog der Auftrag liest. Dieselbe Auswahl wie bei **Manual**. |
| **Theme** / **Module** | — | Erscheinen nur beim passenden Bereich, wie bei **Manual**. |
| **Source** | en-US oder der Wert aus **Settings** | Die Sprache, die als Original gilt. Jede Zielsprache wird aus dieser Sprache übersetzt. |
| **Targets** | keine | Eine oder mehrere Sprachen, die ergänzt werden sollen. Zum Mehrfachauswählen halten Sie Strg (bzw. Cmd am Mac) gedrückt. Ein einfacher Klick ersetzt die bisherige Auswahl. |
| **Domains** | keine | Die Domains, die der Auftrag umfasst. Mehrfachauswahl mit Strg oder Cmd. Wählen Sie keine Domain aus, umfasst der Auftrag alle Domains des gewählten Bereichs. |
| **Policy** | Fill empty | **Fill empty** sendet nur Texte ohne Übersetzung. **Overwrite all** sendet alle Texte, auch bereits übersetzte, und kann sie überschreiben. **Outdated if equals source** sendet nur Texte, deren Übersetzung mit dem Original identisch ist. |
| **Dry-run job** | No | Das Modell erledigt die Arbeit, und der Auftrag erscheint in **Jobs**, aber die Antworten gelangen nicht in den Shop. Gut geeignet, um Kosten und Qualität zu prüfen. |

**Schritte**

1. Wählen Sie Bereich, Quellsprache, Zielsprachen, Domains und Richtlinie.
2. Klicken Sie auf **Estimate**. Über dem Formular erscheint die Schätzung: Anzahl der Texte, geschätzte Tokens, Kosten und eine Stichprobe der Texte.
3. Wenn die Schätzung passt, klicken Sie auf **Start job**. **Jobs** öffnet sich mit dem neuen Auftrag.
4. Verarbeiten Sie den Auftrag in **Jobs** (3.5) oder überlassen Sie ihn dem Cron.

**Meldungen**

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Mistral and nothing was saved.** – Ergebnis der Schätzung.
- **Job #N is waiting (N strings, est. $X). It has not run yet.** – der Auftrag wurde angelegt und wartet.
- **Nothing was started. Select at least one target language.** – keine Zielsprache gewählt.
- **Nothing was started. Pick a theme.** / **Nothing was started. Pick a module.** – wählen Sie ein Theme oder ein Modul.
- **Nothing was started. There is no Mistral API key. Open Settings and paste the key. No job was created.** – noch kein Schlüssel vorhanden.

### 3.5. Jobs

Zu finden unter: Tab **Jobs**.

![Liste der Aufträge. Eine leere Liste zeigt No jobs yet. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-jobs.webp)

**Liste der Aufträge**

Gibt es keinen Auftrag, zeigt die Tabelle **No jobs yet.**

Jede Zeile ist ein Lauf aus **Bulk**. Die Spalten: **#**, **Status**, **Locales** (Quellsprache → Zielsprachen), **Progress** (erledigt/gesamt), **Cost**, **Employee** und **Date**. Mit **Open** öffnen Sie den Auftrag.

Status eines Auftrags, genau so wie auf dem Bildschirm:

- `pending` – wartet, noch nichts verarbeitet. Startet nicht von selbst.
- `running` – läuft gerade.
- `paused` – angehalten. Es wird nichts weiter verarbeitet, bis Sie den Auftrag fortsetzen.
- `cancelled` – abgebrochen. Texte, die noch warteten, wurden nicht übersetzt.
- `completed` – alle Texte ohne Fehler verarbeitet.
- `completed_with_errors` – beendet, aber ein Teil der Texte ist fehlgeschlagen.
- `failed` – der Auftrag wurde wegen eines Fehlers beendet.

**Bildschirm des Auftrags**

Nach dem Öffnen sehen Sie die Überschrift **Job #N**, den Status, den Fortschritt (**done/total**), die Zähler **failed** und **skipped**, die Kosten, den Mitarbeiter und die Kennzeichnung **dry-run**, falls es sich um einen Probelauf handelt. Der Fortschrittsbalken aktualisiert sich alle 2–3 Sekunden von selbst, solange der Auftrag geöffnet ist. Die Tabelle darunter zeigt die Zeilen des Auftrags: **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** und **Error**.

Status der Zeilen: `pending`, `processing`, `done`, `failed`, `skipped` (übersprungen, weil der Text zu einem Ausschluss passt oder schon übersetzt war) und `rolled_back` (zurückgesetzt).

**Schaltflächen**

- **Process slice** – verarbeitet eine Portion (**Batch size** Texte) und hält dann an. Meldung: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Ist nichts mehr zu tun: **The job has no more strings waiting.**
- **Auto-process** – arbeitet Portionen ab, bis der Auftrag endet oder ein Fehler auftritt. Das läuft im Browser und damit nur, solange der Tab offen ist. Schließen Sie den Tab, stoppt es. Der Auftrag bleibt dabei erhalten und lässt sich mit einem weiteren **Process slice** oder per Cron zu Ende führen.
- **Pause** – hält den Auftrag an. Meldung: **Job paused. It will not translate more strings until you resume it.**
- **Resume** – setzt den Auftrag zurück in die Warteschlange. Meldung: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.** Der Auftrag startet nicht von selbst.
- **Retry failed** – fehlerhafte Texte gehen zurück in die Wartenden, und der Auftrag wartet wieder. Meldung: **Retried N failed items.**
- **Rollback** – stellt die vorherige Übersetzung wieder her, sofern das Modul vor der Änderung eine Kopie gespeichert hat. Zuerst bestätigen Sie **Roll back this job?** Danach erscheint **Rollback: restored N translations.**
- **Error CSV** – lädt eine CSV-Datei mit den fehlerhaften Zeilen herunter. Spalten: **id**, **domain**, **locale**, **source**, **error**.
- **Failed only** – zeigt in der Tabelle nur die fehlerhaften Zeilen.
- **Review queue** – führt zu **Review** (3.6).

Auf dem Bildschirm des Auftrags gibt es keine Abbrechen-Schaltfläche. Zum Anhalten verwenden Sie **Pause**.

**Automatisches Anhalten**

Lehnt Mistral Aufrufe wegen eines Limits ab, hält der Auftrag selbst an, mit dem Status `paused` und dieser Meldung im Fehlerfeld: **Rate limit — job auto-paused. Resume later.** Warten Sie kurz und klicken Sie dann auf **Resume**. Die Einstellung **Rate limit / min** in **Settings** verringert die Zahl der Aufrufe pro Minute.

**Fehlermeldungen**

- **Nothing was translated.** mit dem Zusatz **No Mistral API key. Nothing was translated.** – kein Schlüssel, der Auftrag startet nicht. Fügen Sie den Schlüssel unter **Settings** ein.
- **Allow publish is off in Settings.** – ein Auftrag ohne Probelauf startet erst, wenn Sie **Allow publish / save** einschalten.
- **Monthly API budget has been exhausted.** – das Monatsbudget ist aufgebraucht. Erhöhen Sie **Budget USD / month** oder setzen Sie den Wert auf 0.

### 3.6. Review

Zu finden unter: Tab **Review** oder die Schaltfläche **Review queue** auf dem Bildschirm eines Auftrags.

![Warteschlange Review. Eine leere Liste zeigt The queue is empty. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-review.webp)

Über der Tabelle steht die Überschrift **Needs-review queue (quality score / flags).** **Review** listet die Texte, die die Qualitätsprüfung nicht automatisch bestanden haben. Es werden bis zu 100 der neuesten Zeilen angezeigt.

Spalten: **ID**, **Score**, **Domain**, **Source**, **AI** (der Vorschlag), **Flags** sowie die Schaltflächen **Approve** und **Reject**. Ist die Liste leer, steht dort **The queue is empty.**

**So lesen Sie eine Zeile**

- **Score** – Bewertung von 0 bis 100. Liegt sie unter 70, landet die Zeile in der Prüfung.
- **Flags** – die Gründe, warum die Zeile angehalten wurde:
  - `validation_failed` – der Text hat die Prüfung der Variablen oder des HTML nicht bestanden.
  - `warning` – ein kleiner Hinweis aus der Prüfung.
  - `length_explosion` – die Übersetzung ist mehr als zweieinhalbmal so lang wie das Original.
  - `too_short` – die Übersetzung ist deutlich kürzer als das längere Original.
  - `possible_untranslated` – in der Übersetzung sind englische Wörter stehen geblieben, z. B. the, and, with, your, please.
- **Source** – der Originaltext. **AI** – der Vorschlag des Modells.

**Approve** und **Reject** ändern nur den Status der Zeile. Meldung: **Review updated.** Die Zeile verschwindet aus der Liste. Diese Aktionen schreiben keinen Text in den Shop und ändern auch nicht den Rest der Domain.

Hat der Auftrag bereits Ergebnisse gespeichert, kann der Vorschlag schon im Shop stehen. Um eine Änderung aus dem Auftrag rückgängig zu machen, nutzen Sie **Rollback** auf dem Bildschirm dieses Auftrags unter **Jobs**.

### 3.7. Catalog

Zu finden unter: Tab **Catalog**.

![Portion des Katalogs. Die Schaltfläche Translate batch (max 100) befindet sich unter dem Feld Start after ID. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-catalog.webp)

**Catalog** übersetzt die Felder von Produkten, Kategorien und CMS-Seiten in den Sprachen des Shops. Nicht betroffen sind die Seiten unter **International → Translations**. Ein Klick verarbeitet höchstens 100 Datensätze. Das Ergebnis wird direkt in der gewählten Zielsprache gespeichert.

**Felder**

| Feld | Standard | Funktion |
|---|---|---|
| **Entity** | product | Was übersetzt wird: **product**, **category** oder **cms**. Ein Wechsel lädt die Seite neu und zeigt nur die Felder dieser Art. Der Wechsel allein übersetzt nichts. |
| **Fields** | alle Felder der Liste | Welche Texte die Portion sendet. Markieren Sie nur die Felder, die sich ändern sollen. Nicht markierte Felder werden nicht gesendet und bleiben unverändert. Für Produkte: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Für Kategorien: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Für CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. |
| **Source language** | erste Sprache der Liste | Die Sprache, aus der die Texte stammen. |
| **Target language** | erste Sprache der Liste | Die Sprache, in die die Übersetzung geht. Sie muss sich von der Quellsprache unterscheiden. |
| **Only empty** | Yes | Überspringt Felder, die in der Zielsprache bereits Text enthalten. Schalten Sie es nur aus, wenn vorhandener Text ersetzt werden soll. |
| **Start after ID** | 0 | Überspringt Datensätze mit einer ID, die kleiner oder gleich dem eingegebenen Wert ist. Nach einem Stapel springt das Feld auf die zuletzt bearbeitete ID. Klicken Sie erneut auf die Schaltfläche, um weiterzumachen. |

Schaltfläche: **Translate batch (max 100)**.

**Schritte**

1. Wählen Sie **Entity** und markieren Sie die Felder.
2. Wählen Sie **Source language** und **Target language**.
3. Lassen Sie **Only empty** eingeschaltet.
4. Klicken Sie auf **Translate batch (max 100)**. Das Ergebnis sieht so aus: **Catalog finished: saved N, failed M.**
5. Öffnen Sie ein Produkt in der Zielsprache und prüfen Sie das Ergebnis. Erst danach schalten Sie **Only empty** aus oder gehen zum nächsten Stapel über.

**Meldungen**

- **Nothing was translated. Select at least one field.** – markieren Sie Felder.
- **Nothing was translated. Source and target language must be different.** – wählen Sie zwei verschiedene Sprachen.
- **Nothing was saved. Turn on Allow publish in Settings.** – schalten Sie **Allow publish / save** ein.
- **Nothing was translated. There is no Mistral API key. Open Settings and paste the key.** – noch kein Schlüssel vorhanden.

### 3.8. Glossary

Zu finden unter: Tab **Glossary**.

![Hinzufügen eines Begriffs. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary.webp)

![CSV-Import und -Export sowie leere Liste der Begriffe. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary-csv.webp)

Das Glossar ist eine Liste von Wörtern und Wendungen, die das Modell entweder unverändert lassen oder immer gleich übersetzen soll. Eine neue Zeile ändert bereits gespeicherte Übersetzungen nicht. Die nächste Übersetzung berücksichtigt aber die Liste.

**Einen Begriff hinzufügen**

| Feld | Standard | Funktion |
|---|---|---|
| **Source term** | leer, Pflichtfeld | Ein Wort oder eine Wendung in der Quellsprache. Schreiben Sie sie genau so, wie sie vorkommt, mit Großbuchstaben, wenn es darauf ankommt. |
| **Target locale** | leer | Beschränkt die Zeile auf eine Sprache, z. B. pl-PL. Leer heißt: Die Zeile gilt für jede Zielsprache. |
| **Target term** | leer | Die freigegebene Übersetzung des Begriffs. Dieses Feld darf nur leer sein, wenn **Do not translate** eingeschaltet ist. |
| **Do not translate** | No | Eingeschaltet: Das Modell übernimmt den Begriff unverändert, etwa einen Markennamen, eine SKU oder ein Kennzeichen. Ausgeschaltet: Das Modell verwendet **Target term**. |

Schaltfläche: **Add**. Meldungen: **Glossary term added. Translations already stored were not changed.** oder **Nothing was added. Type a source term.**

**Tabelle**

Spalten: **Source**, **Locale**, **Target**, **Do not translate** (Yes oder No) sowie eine Schaltfläche **Delete** in jeder Zeile. Sie löscht nur diese Zeile. Meldung: **Glossary term deleted.** Leere Liste: **No glossary terms yet.**

**CSV-Import und -Export**

- **CSV file** – wählen Sie eine Datei und klicken Sie auf **Import CSV**. Meldung: **Imported N rows.**
- Aufbau der Datei: Die erste Zeile ist die Kopfzeile `source_term`, `target_locale`, `target_term`, `do_not_translate`. Die Kopfzeile wird immer übersprungen. Zeilen mit weniger als drei Spalten werden ebenfalls übersprungen. In der vierten Spalte bedeutet ein leerer Wert oder 0 **No**, jeder andere Wert bedeutet **Yes**.
- Der Import fügt die Zeilen aus der Datei hinzu. Er prüft nicht, ob ein Begriff schon existiert. Dieselbe Datei zweimal zu importieren, erzeugt also Duplikate.
- **Export CSV** lädt die aktuelle Liste als Datei `glossary.csv` herunter. Es ist keine Eingabedatei nötig, und es wird nichts verändert.

Tipp: Verwenden Sie kurze, genaue Begriffe. Ein sehr allgemeiner Begriff wird bei jedem Auftreten erzwungen.

### 3.9. Excludes

Zu finden unter: Tab **Excludes**.

![Ausschlussmuster. Eine leere Liste zeigt No patterns yet. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-excludes.webp)

Ein Ausschluss ist ein Muster für Quelltext, den das Modul nie an Mistral schickt. Der Text bleibt im Shop unverändert. Ausschlüsse gelten auf allen Arbeitswegen: **Manual**, **Bulk**, **Catalog** und den Übersetzungsseiten.

**Muster hinzufügen**

| Feld | Standard | Funktion |
|---|---|---|
| **Pattern** | leer, Pflichtfeld | Ein Text oder Ausdruck, der mit jedem Quelltext verglichen wird. Wie der Vergleich erfolgt, hängt von **Type** ab. |
| **Type** | exact | **exact** – der gesamte Text muss übereinstimmen. **prefix** – der Text beginnt mit dem Muster. **contains** – das Muster kommt irgendwo vor. **regex** – ein regulärer PHP-Ausdruck. |

Schaltfläche: **Add**. Meldung: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Bei leerem Feld: **Nothing was added. Type a pattern.**

Ein Muster vom Typ **regex** wird genau so angewendet, wie Sie es eingegeben haben. Ein fehlerhafter Ausdruck trifft auf nichts. Beginnen Sie mit einem kurzen Muster und prüfen Sie, was es übersprungen hat.

**Tabelle**

Spalten: **Pattern**, **Type**, **On** und **Delete**. Die Spalte **On** zeigt bei einem aktiven Muster eine 1. Auf dieser Seite gibt es keinen Schalter. Um ein Muster zu deaktivieren, löschen Sie es und legen es neu an. **Delete** entfernt nur dieses Muster; vorhandene Übersetzungen bleiben erhalten. Meldung: **Pattern deleted.** Leere Liste: **No patterns yet.**

Nutzen Sie Ausschlüsse für Texte, die in der Quellsprache bleiben sollen, etwa einen Firmennamen oder eine technische Kennung. Für Texte, die immer auf dieselbe Weise übersetzt werden sollen, ist **Glossary** da.

### 3.10. History

Zu finden unter: Tab **History** oder die Schaltfläche **See all** im **Dashboard**.

![Liste des Verlaufs. Eine leere Liste zeigt No requests yet. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-history.webp)

**History** ist die vollständige Liste aller protokollierten Mistral-Aufrufe: manuelle Übersetzungen, Übersetzungsseiten, **Bulk**-Aufträge, **Catalog** und Verbindungstests. Jeder Eintrag enthält den gesendeten Text, die Antwort, das Modell, die Sprachen, die Anzahl der Tokens und die Dauer des Aufrufs. Karten, Diagramme und Filter finden Sie im **Dashboard**, nicht auf dieser Seite. Das Öffnen dieser Seite sendet keine Anfrage und verändert keine Übersetzungen. Der Hinweis unter dem Feld **Model** in **Settings** spricht von **Logs**. Gemeint sind die Einträge, die Sie hier sehen. Einen eigenen Tab Logs gibt es nicht.

**Spalten der Liste:** **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** und **Prompt**. Typen: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** und **Not sent** (der Aufruf ging nicht hinaus, etwa wegen des lokalen Limits oder des Budgets). Bei einem Eintrag von **Bulk job** sehen Sie die Nummer des Auftrags.

- **View** öffnet ein Fenster mit der gesendeten Anweisung und der Antwort. Bei einem Fehler steht dort stattdessen die Fehlermeldung.
- Ein Eintrag mit einem Zugriffsfehler bedeutet, dass der Schlüssel unter **Settings** falsch ist oder das Konto das gewählte Modell nicht nutzen darf.
- **Previous**, **Next** und das Feld **Page** blättern durch die Liste.
- **Clear history** löscht diese Einträge. Bestätigen Sie mit **Clear the stored history? Saved translations stay.** Danach erscheint **History cleared. Saved translations were not changed.**

Bleiben Übersetzungen plötzlich stehen, öffnen Sie auf dieser Seite den neuesten Eintrag mit einem Fehler, bevor Sie das Glossar ändern.

### 3.11. Updates

Zu finden unter: Tab **Updates** ganz rechts im Menü.

![Prüfung auf Aktualisierungen. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-updates.webp)

Das Panel heißt **MyPresta Updates**.

- **Manual Check** – mit **Check Now** prüfen Sie die Version sofort.
- **Automatic Notifications** – **Enabled** oder **Disabled**. Ist es eingeschaltet, prüft das Modul, ob auf dem MyPresta-Server eine neuere Version liegt, und zeigt im Back Office eine Warnung an.
- **Product Page** – Link zur Seite des Moduls.
- **Save** – speichert Ihre Auswahl bei **Automatic Notifications**.

Meldungen: **Update settings saved.**, **New version available!**, **Module is up to date!**

### 3.12. Schaltflächen auf der Seite International → Translations

Zu finden unter: **International** → **Translations**. Wählen Sie den Übersetzungstyp und die Sprache und klicken Sie dann auf **Modify**. Die Schaltflächen neben den Feldern erscheinen, wenn unter **Settings** **Individual field buttons — International → Translations** eingeschaltet ist. Die Kontrollkästchen und die Leiste erscheinen, wenn **Individual field checkboxes — International → Translations** eingeschaltet ist.

![Leiste Mistral translations unten auf der Seite International → Translations. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-translations-page.webp)

**Was Sie sehen**

- Neben jedem Textfeld eine Schaltfläche, die genau dieses Feld übersetzt.
- Neben jedem Feld ein Kontrollkästchen (sofern die Kontrollkästchen aktiviert sind).
- Eine Leiste mit **Mistral translations**: das Feld **Source** (standardmäßig en-US oder der Wert aus **Settings**), die Liste **Target**, die Schaltflächen **Check all**, **Uncheck all**, **Check empty**, **Translate empty** und **Translate selected** sowie den Hinweis **Fills the fields. Save with the PrestaShop button.**

**Schritte**

1. Wählen Sie **Target**.
2. Markieren Sie die Felder, die Sie füllen möchten, oder klicken Sie auf **Check empty**.
3. Klicken Sie auf **Translate selected** oder auf **Translate empty**, das alle leeren Felder des Bereichs füllt.
4. Warten Sie, bis die Leiste **Done (N)** anzeigt. Während der Arbeit sehen Sie **Translating… N/M**.
5. Prüfen Sie die gefüllten Felder und speichern Sie die Seite mit der Schaltfläche **Save** von PrestaShop.

Die Schaltflächen füllen nur die Felder. Ohne **Save** in PrestaShop gelangt der Text nicht in den Shop. Ist **Allow publish / save** ausgeschaltet, werden die Felder trotzdem gefüllt; gespeichert wird dann durch PrestaShop.

**Meldungen**

- **Target is not a language from this shop.** – die gewählte Sprache existiert in diesem Shop nicht.
- **Fill the source language field first.** – füllen Sie zuerst das Feld der Quellsprache aus.
- **The source language field is not on this page.** – auf dieser Seite gibt es kein Feld für die Quellsprache.
- **The source language mail file was not found.** – die Quelldatei der E-Mail wurde nicht gefunden. Wählen Sie unter **Settings** eine andere **Source locale**, für die E-Mail-Dateien vorhanden sind.

Im Bereich **Emails** stammt der Quelltext aus der Quelldatei der E-Mail-Vorlage und nicht aus einem Feld auf der Seite.

### 3.13. Schaltflächen in den Formularen für Produkte, Kategorien und CMS

Zu finden unter: das Formular eines Produkts, einer Kategorie, einer CMS-Seite oder eines anderen Shop-Formulars mit mehrsprachigen Feldern. Die Schaltflächen sind sichtbar, wenn unter **Settings** **Individual field buttons — shop forms** und **Individual field checkboxes — shop forms** eingeschaltet sind.

![Leiste unten im Produktformular sowie ein Kontrollkästchen an einem mehrsprachigen Feld. Bildschirm auf Englisch.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-product-form.webp)

**Was Sie sehen**

- Neben jedem mehrsprachigen Feld eine Schaltfläche, die dieses Feld übersetzt.
- Neben den Feldern ein Kontrollkästchen, mit dem Sie das Feld für die Leiste auswählen.
- Eine Leiste unten auf der Produktseite mit der Bezeichnung **Mistral translations**, der Sprachauswahl **Translate from … to …**, den Schaltflächen **Check all**, **Uncheck all**, **Check empty**, **Translate empty** und **Translate selected** sowie dem Hinweis **Fills the fields. Save with the PrestaShop button.**

**Schritte**

1. Füllen Sie das Feld in der Quellsprache aus. Ohne das zeigt die Leiste **Fill the source language field first.**
2. Wählen Sie auf der Leiste die Zielsprache.
3. Klicken Sie auf die Schaltfläche neben einem Feld oder markieren Sie mehrere Felder und klicken Sie auf **Translate selected**. **Translate empty** füllt die leeren Felder.
4. Klicken Sie danach im PrestaShop-Formular auf **Save**. Ohne diesen Schritt ist der Text nicht gespeichert.

Die Schaltfläche füllt nur das Feld im Formular. Gespeichert wird erst mit **Save** des Produkt-, Kategorie- oder CMS-Formulars. Nicht markierte Felder bleiben unverändert.

## 4. Storefront

Das Modul fügt den Shopseiten, die Kunden sehen, nichts hinzu. Kunden haben keinen Bildschirm und keine Schaltfläche, die mit dem Modul zu tun hat. Im Theme gibt es also nichts zu prüfen.

Die einzige Adresse außerhalb des Back Office ist die Cron-Adresse. Sie ist für eine geplante Aufgabe auf dem Server gedacht und nicht für Kunden.

- **Woher Sie die Adresse kopieren:** **Settings** → **CRON URL** oder **Dashboard** → Zeile **CRON**.
- **Was zu tun ist:** Tragen Sie die Adresse im Aufgabenplaner Ihres Servers ein, z. B. alle paar Minuten. Jeder Aufruf verarbeitet eine Portion eines wartenden Auftrags.
- **Die Adresse läuft über HTTPS.** Ist SSL im Shop aktiv, verwenden Sie die Adresse, die mit `https://` beginnt.

| Was beim Öffnen der Adresse erscheint | Was zu tun ist |
|---|---|
| Die Meldung **Forbidden** | Die Adresse ist unvollständig oder hat sich geändert. Kopieren Sie sie erneut aus **Settings**. |
| Die Meldung **No pending jobs** | Es gibt keine wartenden oder laufenden Aufträge. Legen Sie unter **Bulk** einen Auftrag an oder setzen Sie einen angehaltenen unter **Jobs** fort. |
| Daten im JSON-Format mit dem Ergebnis der Portion (Felder `ok`, `finished`, `counts`) | Eine Portion des Auftrags wurde verarbeitet. Den Fortschritt sehen Sie unter **Jobs**. |

Der Cron bearbeitet nur Aufträge mit dem Status `pending` oder `running`. Einen Auftrag mit dem Status `paused` müssen Sie von Hand fortsetzen.

## 5. Fehlerbehebung

| Symptom (was Sie sehen) | Ursache | Was zu tun ist |
|---|---|---|
| **No Mistral API key.** auf jeder Seite des Moduls | Der Schlüssel wurde nicht gespeichert. | Öffnen Sie **Settings**, fügen Sie den Schlüssel in das Feld **Mistral API key** ein und klicken Sie auf **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Die Einstellungen wurden ohne Schlüssel gespeichert. | Fügen Sie den Schlüssel in **Mistral API key** ein und klicken Sie auf **Save**. |
| **Connection was not made. Nothing was translated.** nach **Test connection** | Falscher Schlüssel, keine Verbindung zum Server oder das Modell ist für das Konto nicht verfügbar. | Prüfen Sie den Schlüssel, wählen Sie ein anderes **Model** oder fügen Sie unter **Add a Mistral model** eine korrekte Kennung hinzu. Details finden Sie in **History**. |
| Aufrufe enden in **History** mit einem Zugriffsfehler | Der Schlüssel ist falsch oder das Konto darf das gewählte Modell nicht nutzen. | Korrigieren Sie den Schlüssel oder wählen Sie ein Modell, das Ihr Konto verwenden darf. |
| **Nothing was started. There is no Mistral API key.** bei **Bulk** | Es ist kein Schlüssel vorhanden. | Fügen Sie den Schlüssel unter **Settings** ein und führen Sie danach **Estimate** und **Start job** erneut aus. |
| Ein Auftrag bleibt auf `pending` und nichts passiert | Aufträge starten nicht von selbst. | Klicken Sie unter **Jobs** auf **Process slice** oder **Auto-process**. Oder richten Sie den Cron ein (Abschnitt 4). |
| Ein Auftrag steht auf `paused` mit der Meldung **Rate limit — job auto-paused. Resume later.** | Mistral hat Aufrufe wegen eines Limits abgelehnt. | Warten Sie einige Minuten und klicken Sie auf **Resume**. Senken Sie **Batch size** oder **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Das **Budget USD / month** wurde überschritten. | Erhöhen Sie den Betrag oder setzen Sie ihn auf 0. Ein neuer Monat beginnt wieder bei null. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** ist ausgeschaltet. | Schalten Sie **Allow publish / save** unter **Settings** ein. |
| **Not saved because of broken placeholders or HTML: N.** bei **Manual** | Die Übersetzung hat Variablen oder HTML-Markierungen verändert. | Korrigieren Sie die Zeile von Hand in der Prüftabelle, sodass Variablen und Markierungen dem Original entsprechen, und speichern Sie. |
| Ein Auftrag endet mit `completed_with_errors` | Ein Teil der Texte ist fehlgeschlagen. | Öffnen Sie den Auftrag, markieren Sie **Failed only**, laden Sie die **Error CSV** herunter und klicken Sie dann auf **Retry failed**. |
| Zeilen in **Review** haben eine niedrige **Score** | Die Qualitätsprüfung hat sie nicht durchgelassen. | Vergleichen Sie **Source** und **AI**. Bestätigen Sie mit **Approve** oder lehnen Sie mit **Reject** ab. Wurde eine fehlerhafte Übersetzung bereits gespeichert, nutzen Sie **Rollback** im Auftrag. |
| Die Übersetzung ist gespeichert, im Shop steht aber noch der alte Text | Beim Speichern wird der PrestaShop-Cache geleert. Das Theme oder der Browser kann die alte Seite aber noch anzeigen. | Öffnen Sie **Advanced Parameters** → **Performance**, leeren Sie den Cache und laden Sie die Shop-Seite neu. |
| Ein **Exclude pattern** überspringt den Text nicht | Der **Type** ist falsch oder der **regex**-Ausdruck fehlerhaft. | Ändern Sie unter **Excludes** den Typ oder löschen Sie das Muster und legen Sie es mit einem kürzeren Text neu an. |
| Ein neuer Glossarbegriff wirkt sich auf gespeicherte Übersetzungen nicht aus | Das Glossar gilt für neue Übersetzungen. Gespeicherte Texte werden nicht geändert. | Lassen Sie die Übersetzung dieser Texte in **Bulk** mit der Richtlinie **Overwrite all** neu laufen. Prüfen Sie vorher die Schätzung unter **Estimate**. |
| **The source language mail file was not found.** | Für die gewählte Quellsprache gibt es keine E-Mail-Datei. | Wählen Sie unter **Settings** oder auf der Übersetzungsseite eine andere **Source locale**, für die E-Mail-Dateien vorhanden sind. |
| **No strings match this filter. Nothing was sent to Mistral.** | Der Filter trifft auf keine Texte zu. | Deaktivieren Sie **Only empty**, leeren Sie **Search** oder wählen Sie eine andere Domain. |
| **Nothing was translated. Tick at least one row.** | Keine Zeile ist markiert. | Markieren Sie Zeilen und klicken Sie auf **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** bei **Catalog** | Quell- und Zielsprache sind gleich. | Wählen Sie eine andere **Target language**. |
| Das Dashboard zeigt eine leere Übersicht | Der Shop hat für die gewählte Sprache noch keinen Katalog. | Legen Sie den Katalog unter **International → Translations** an und kehren Sie dann zum **Dashboard** zurück. |
| Der Verlauf enthält Einträge **Not sent** | Das lokale Limit oder das Budget hat den Aufruf gestoppt. | Prüfen Sie **Rate limit / min** und **Budget USD / month** unter **Settings**. |

## 6. Für Entwickler

### 6.1. Überblick

- **Hauptklasse:** `myaitranslationsmistral`, Datei `myaitranslationsmistral.php`.
- **Version:** 1.2.0.
- **Technischer Name:** `myaitranslationsmistral`. In der Modulliste erscheint er als **AI Translations with Mistral**.
- **Autor:** MyPresta.eu. Tab des Moduls im Module Manager: `administration`.
- **Back-Office-Tab:** `AdminMyaitranslationsmistral`, übergeordnet `AdminInternational` (ersatzweise `IMPROVE`).
- **Installation:** `parent::install()`, Tabellen aus `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), Standardwerte über `installDefaults()` (es werden nur fehlende Schlüssel gesetzt), Registrierung der Hooks `displayBackOfficeHeader` und `actionAdminControllerSetMedia`, Anlegen des Tabs.
- **Deinstallation:** Entfernen des Tabs, `sql/uninstall.php` (löscht 11 Tabellen), Entfernen der `MYAITMI_*`-Schlüssel über `removeConfiguration()`, danach `parent::uninstall()`.
- Das Modul hat **keine** Methoden `enable()` und `disable()`.
- **Konfiguration:** `getContent()` leitet zu `AdminMyaitranslationsmistral` weiter (standardmäßig der Tab `dashboard`).

**Datenfluss**

1. Die Formulare aus `MyaitmiForms` (Tab `settings`) senden ihre Werte an `AdminMyaitranslationsmistralController::initContent()`.
2. `MyaitmiConfigService::saveFromForm()` speichert die Schlüssel `MYAITMI_*` in `Configuration`. Den API-Schlüssel verschlüsselt `MyaitmiApiKeyEncryptor` (AES-256-CBC, Schlüssel abgeleitet aus `_COOKIE_KEY_`) und legt ihn unter `MYAITMI_API_KEY_ENC` ab.
3. Übersetzung: `MyaitmiTranslateService::translateMessages()` erstellt die Anweisungen (`MyaitmiPromptBuilder`), sendet sie über `MyaitmiMistralTranslationProvider` (cURL, POST an `https://api.mistral.ai/v1/chat/completions`), prüft die Antwort (`MyaitmiPlaceholderValidator`, `MyaitmiHtmlValidator`, `MyaitmiPsNativeValidator`), bewertet sie (`MyaitmiQualityScorer`) und speichert sie über `MyaitmiTranslationAdapter`.
4. Speichern der Übersetzung: über den Dienst `prestashop.service.translation`. Fehlt dieser, wird direkt in die Tabelle `_DB_PREFIX_translation` geschrieben. Schlüssel klassischer Module (Form `<{name}prestashop>…`) landen in der Datei `translations/{iso}.php` des jeweiligen Moduls (`MyaitmiLegacyModuleCatalogue`).
5. Bulk: `MyaitmiBulkJobFactory` legt Auftrag und Zeilen in `myaitmi_job` und `myaitmi_job_item` an. `MyaitmiJobWorker::processSlice()` verarbeitet eine Portion (Größe aus `BATCH_SIZE`). Aufgerufen wird sie durch die Schaltfläche **Process slice** (Anfrage des Tabs **Jobs**), durch die Schleife **Auto-process** im Browser (AJAX `ProcessJob`) oder durch den Cron (`controllers/front/cron.php`).
6. Catalog: `MyaitmiCatalogTranslateService` wählt die Datensätze aus (`collect()`, max. 100) und speichert sie direkt in `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` oder `_DB_PREFIX_cms_lang`.
7. Jeder Aufruf wird in `myaitmi_request` protokolliert (Tab **History**), Fehler landen in `myaitmi_api_log`. Die Kosten gehen in `myaitmi_usage_ledger`. Den Text vor einer Änderung durch einen Auftrag kopiert `MyaitmiSnapshotService` nach `myaitmi_snapshot`; so ist das Zurücksetzen über **Rollback** möglich.

### 6.2. Dateien

| Datei | Wofür sie da ist |
|---|---|
| `myaitranslationsmistral.php` | Hauptklasse: Installation, Deinstallation, Menü-Tab, Hooks, Laden der Assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Prüfung auf Aktualisierungen (Tab **Updates**, Warnung im Back Office). |
| `logo.png`, `logo.gif` | Logo in der Kopfzeile der Tabs und im Menü des Moduls. |
| `controllers/admin/AdminMyaitranslationsmistralController.php` | Das gesamte Back Office: Tabs, Speichern, Auftragsaktionen, Glossar, Ausschlüsse, Katalog, CSV, AJAX-Antworten. |
| `controllers/front/cron.php` | Cron-Adresse: verarbeitet eine Portion eines Auftrags und liefert JSON zurück. |
| `sql/install.php`, `sql/uninstall.php` | Anlegen und Löschen der Tabellen. |
| `src/Adapter/MyaitmiTranslationAdapterInterface.php` | Schnittstelle zum Lesen und Schreiben von PrestaShop-Übersetzungen. |
| `src/Adapter/MyaitmiAbstractTranslationAdapter.php` | Gemeinsame Logik des Adapters: Listen der Bereiche, Domains und Sprachen, Speichern über den Dienst oder die Tabelle `translation`, Leeren des Caches. |
| `src/Adapter/MyaitmiTranslationAdapter.php` | Der konkrete Adapter (wird von der Factory verwendet). |
| `src/Adapter/MyaitmiTranslationAdapterFactory.php` | Erzeugt den Adapter. |
| `src/Adapter/MyaitmiFilesystemCatalogueTrait.php` | Liest XLF-Kataloge aus Themes und Modulen (Domains). |
| `src/Adapter/MyaitmiLegacyModuleCatalogue.php` | Klassische Module: liest und schreibt `translations/{iso}.php`, leert nach dem Schreiben den OPcache. |
| `src/Admin/MyaitmiForms.php` | Baut alle Formulare des Back Office und die Feldbeschreibungen (`desc`). |
| `src/Admin/MyaitmiSectionHelp.php` | Texte des Panels **Help** für jeden Tab. |
| `src/Audit/MyaitmiRequestLogRepository.php` | Verlauf der Aufrufe, Karten, Diagramme, Filter, Löschen, Aufbewahrung. |
| `src/Audit/MyaitmiApiLogRepository.php` | Protokoll der API-Fehler und -Warnungen, Aufbewahrung. |
| `src/Audit/MyaitmiTranslationMemory.php` | Übersetzungsspeicher (Cache): Wiederverwendung eines Ergebnisses für denselben Text, dieselbe Sprache, dasselbe Modell und dasselbe Glossar. |
| `src/Audit/MyaitmiUsageLedger.php` | Kosten laut Preistabelle im Code, Monatsbudget. |
| `src/Audit/MyaitmiSnapshotService.php` | Kopien vor dem Speichern und Zurücksetzen von Aufträgen. |
| `src/Glossary/MyaitmiGlossaryRepository.php` | Glossar: Auflisten, Speichern, Löschen. |
| `src/Glossary/MyaitmiExcludePatternRepository.php` | Ausschlüsse: Hinzufügen, Löschen, Abgleich. |
| `src/Job/MyaitmiJobStatuses.php` | Konstanten für die Status von Aufträgen und Zeilen. |
| `src/Job/MyaitmiJobRepository.php` | Aufträge und Zeilen: Lesen, Statuswechsel, Abrufen der Portionen, Neuberechnung der Zähler. |
| `src/Job/MyaitmiJobWorker.php` | Verarbeitung der Portionen, Wiederholung von Fehlern, Abschluss des Auftrags, Prüfwarteschlange, E-Mail nach Abschluss. |
| `src/Provider/MyaitmiTranslationProviderInterface.php` | Schnittstelle des Übersetzungsanbieters. |
| `src/Provider/MyaitmiMistralTranslationProvider.php` | Mistral-Aufrufe (cURL), Verbindungstest, Speichern des Aufrufverlaufs. |
| `src/Provider/MyaitmiPromptBuilder.php` | Erstellt die System- und Benutzeranweisungen (Ton, Markenstimme, Glossar). |
| `src/Provider/MyaitmiProviderFactory.php` | Erzeugt den Anbieter. |
| `src/Quality/MyaitmiPlaceholderValidator.php` | Prüfung der Variablen und Markierungen im Text. |
| `src/Quality/MyaitmiHtmlValidator.php` | Prüfung der Gültigkeit des HTML. |
| `src/Quality/MyaitmiPsNativeValidator.php` | Prüfung vor dem Speichern im Bereich **Manual**. |
| `src/Quality/MyaitmiEmailHtmlPipeline.php` | Schützt das HTML von E-Mail-Vorlagen vor dem Versand und stellt es nach der Antwort wieder her. |
| `src/Quality/MyaitmiQualityScorer.php` | Bewertung 0–100, Flags, Entscheidung über die Prüfung. |
| `src/Security/MyaitmiApiKeyEncryptor.php` | Verschlüsselt und entschlüsselt den API-Schlüssel. |
| `src/Service/MyaitmiConfigService.php` | Liest und speichert Einstellungen, Modelle und Cron-Token, prüft Wertebereiche. |
| `src/Service/MyaitmiRateLimiter.php` | Lokales Limit der Aufrufe pro Minute (Datei `var/rate_limit.json`). |
| `src/Service/MyaitmiTranslateService.php` | Hauptablauf der Übersetzung: Ausschlüsse, Speicher, Aufrufe, Prüfung, Bewertung, Speichern, Schätzung. |
| `src/Service/MyaitmiBulkJobFactory.php` | Erstellt den Auftrag **Bulk** und die Schätzung. |
| `src/Service/MyaitmiCatalogTranslateService.php` | Sammelt und speichert die Datensätze von **Catalog**. |
| `src/Service/MyaitmiDashboardService.php` | Übersicht der fehlenden Texte im **Dashboard**. |
| `translations/*.php` | Übersetzungen der Oberfläche (eine Datei pro Sprache). |
| `views/templates/admin/configure.tpl` | Vorlage der gesamten Back-Office-Seite und des Panels **Help**. |
| `views/templates/admin/_partials/*.tpl` | Tabs: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Stile des Back Office. |
| `views/js/admin.js` | Tab **Jobs** (Fortschritt, **Auto-process**), Markieren von Zeilen, AJAX-Antworten. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Schaltflächen und Leiste auf **International → Translations**. |
| `views/js/entity-fields.js` | Schaltflächen und Leiste in den Formularen für Produkte, Kategorien und CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Diagramme im **Dashboard**. |
| `var/rate_limit.json` | Zähler für das lokale Limit der Aufrufe in der aktuellen Minute. |
| `index.php` (in jedem Verzeichnis) | Schutz vor dem Durchsuchen von Verzeichnissen. |

### 6.3. Controller

**Back Office: `AdminMyaitranslationsmistralController`** (Klasse `ModuleAdminController`, Tab unter `AdminInternational`).

- Adresse: `index.php?controller=AdminMyaitranslationsmistral&token=…`, optional mit `&myaitmi_tab=…`.
- Zulässige Werte für `myaitmi_tab`: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (**History**), `review`, `catalog`, `updates`. Jeder andere Wert führt zu `dashboard`.
- Eingabeparameter (GET/POST):
  - Einstellungen: die Felder `MYAITMI_*` aus dem Formular, `new_mistral_model`, `delete_mistral_model` sowie die Schaltflächen `submitMyaitranslationsmistralSettings`, `…Ping`, `…AddModel`.
  - Filter und Übersetzung: `section`, `theme`, `module`, `domain`, `source_locale`, `target_locale`, `only_empty`, `search`, `selected_keys[]`, `save_now`, `review_key[]`, `review_value[]`, `review_approve[]`, `review_source[]`.
  - Bulk: `target_locales[]`, `domains[]`, `policy_mode` (`fill_empty`, `overwrite`, `outdated_if_changed`), `dry_run`, `bulk_step` (`estimate`).
  - Aufträge: `id_job`, `job_action` (`pause`, `resume`, `cancel`, `process`, `retry_failed`, `rollback`, `export_errors`), `filter_failed`.
  - Prüfung: `review_action` (`approve`, `reject`) und `id_review`.
  - Catalog: `entity_type` (`product`, `category`, `cms`), `id_lang_source`, `id_lang_target`, `catalog_fields_{entity}[]`, `catalog_start_id`, `only_empty`.
  - Glossar und Ausschlüsse: `source_term`, `target_locale`, `target_term`, `do_not_translate`, `glossary_csv` (Datei), `pattern`, `pattern_type`, `delete_glossary`, `delete_exclude`.
  - Verlauf und Karten: `dash_locale`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_q`, `stats_preset`, `hist_id`.
- Liefert entweder eine HTML-Seite (`configure.tpl`) oder eine Datei: `glossary.csv` (Export des Glossars) oder `job-{id}-errors.csv` (Fehler eines Auftrags).
- Erfolgs- und Fehlermeldungen werden über die Parameter `flash` und `flash_kind` (`info`, `success`, `warning`, `danger`) übergeben.

**AJAX-Aktionen des Back Office** (`index.php?controller=AdminMyaitranslationsmistral&ajax=1&action=…`):

| `action` | Parameter | Rückgabe |
|---|---|---|
| `ProcessJob` | `id_job` | Ergebnis der Portion: `ok`, `finished`, `paused`, `rate_limited`, `counts`, `job`. |
| `JobStatus` | `id_job` | `ok` und das Objekt `job`. |
| `TranslatePageLines` | `items` (JSON), `source_locale`, `target_locale` | `translations` (id → Text), `error`. Speichert nicht. |
| `MailSource` | `template`, `kind` (`html`/`txt`), `module`, `theme` | Quelldatei der E-Mail. |
| `ListDomains` | `section`, `locale`, `theme`, `module` | Liste `domains`. |
| `HistoryDetail` | `hist_id` | Details des Aufrufs. |

**Front: `MyaitranslationsmistralCronModuleFrontController`** (`ajax = true`, `ssl = true`).

- Adresse: `index.php?fc=module&module=myaitranslationsmistral&controller=cron&token=…`, optional mit `&id_job=N`.
- `token` ist erforderlich und wird per `hash_equals()` mit `MYAITMI_CRON_TOKEN` verglichen. Ein falsches Token ergibt Code 403 und das JSON `{"ok":false,"error":"Forbidden"}`.
- Mit `id_job`: verarbeitet eine Portion dieses Auftrags.
- Ohne `id_job`: nimmt den ersten Auftrag mit dem Status `pending` oder `running` aus den 20 letzten. Gibt es keinen, lautet die Antwort `{"ok":true,"message":"No pending jobs"}`.

### 6.4. Hooks

Bei der Installation registriert:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: ersetzt den technischen Tab-Namen durch die Bezeichnung (`renameTabIfTechnical()`) und lädt die Assets des Back Office (`loadBoAssets()`).
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: lädt die Assets (`loadBoAssets()`).

Assets aus `loadBoAssets()`:

- Im Tab des Moduls: `admin.css`, `admin.js`, `admin-help.js`; im Tab **Dashboard** zusätzlich `chart.min.js` und `history-charts.js`. `Media::addJsDef` mit `aitHelpLabels`.
- Auf **International → Translations** (`AdminTranslations` bzw. `/international/translations`), wenn die Schaltflächen dieser Seite aktiv sind: `admin.css` und `translations-tool.js`.
- Auf den übrigen Seiten des Back Office (Formulare für Produkte, Kategorien, CMS), wenn die Formular-Schaltflächen aktiv sind: `admin.css` und `entity-fields.js`.
- Daten für JS: `Media::addJsDef(['myaitmiTr' => …])` mit der Sprachliste, den Locales, den Flags der Schaltflächen und den Bezeichnungen (`translationClientConfig()`).

Das Modul stellt keine eigenen Hooks bereit (kein `Hook::exec`).

### 6.5. Überschreibungen

Das Modul überschreibt keine Klasse und keinen Controller von PrestaShop. Ein Verzeichnis `override` gibt es nicht.

### 6.6. Datenbank

Die Tabellen werden in `sql/install.php` angelegt (`_DB_PREFIX_` ist das Tabellenpräfix des Shops, standardmäßig `ps_`). Alle verwenden die Engine `_MYSQL_ENGINE_` und `utf8mb4_unicode_ci`.

| Tabelle | Inhalt |
|---|---|
| `myaitmi_glossary` | `id_myaitmi_glossary`, `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, `date_add`, `date_upd`. Schlüssel `idx_shop_locale` (`id_shop`, `target_locale`). Lesen: `id_shop` IN (0, Shop). |
| `myaitmi_exclude_pattern` | `id_myaitmi_exclude_pattern`, `pattern` (VARCHAR 512), `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled` (beim Anlegen immer 1), `date_add`. |
| `myaitmi_job` | `id_myaitmi_job`, `uuid` (eindeutig), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_total`, `items_done`, `items_failed`, `items_skipped`, `tokens_prompt`, `tokens_completion`, `cost_usd_estimate`, `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`, `date_add`, `date_upd`. Schlüssel `idx_status`. |
| `myaitmi_job_item` | `id_myaitmi_job_item`, `id_myaitmi_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`, `date_add`, `date_upd`. Schlüssel `idx_job_status`. Eine Portion umfasst eine Zielsprache. |
| `myaitmi_memory` | Übersetzungsspeicher: `memory_hash` (eindeutig), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitmi_usage_ledger` | `usage_date`, `id_myaitmi_job`, `model`, `tokens_prompt`, `tokens_completion`, `cost_usd`, `date_add`. Die Monatssumme wird gegen das Budget gerechnet. |
| `myaitmi_snapshot` | Kopie vor dem Speichern: `id_myaitmi_job`, `id_myaitmi_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. |
| `myaitmi_api_log` | Protokoll der Fehler und Warnungen: `id_myaitmi_job`, `level`, `provider`, `http_code`, `message`, `context_json`, `date_add`. Aufbewahrung gemäß `MYAITMI_LOG_RETENTION_DAYS`. |
| `myaitmi_review` | Prüfwarteschlange: `id_myaitmi_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`, `date_add`, `date_upd`. |
| `myaitmi_catalog_item` | Wird bei der Installation angelegt und bei der Deinstallation entfernt. Der Modul-Code schreibt nicht hinein; **Catalog** speichert direkt in den Sprachtabellen des Shops. |
| `myaitmi_request` | Verlauf der Aufrufe: `request_type` (`translate`, `manual`, `page`, `job`, `catalog`, `ping`, `blocked`), `status`, `model`, `source_locale`, `target_locale`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `cost_usd`, `id_employee`, `id_myaitmi_job`, `item_count`, `prompt`, `reply`, `error_message`, `date_add`. Fehlt die Tabelle, legt `ensure()` sie beim ersten Speichern oder beim Öffnen von **History** an. |

Die Deinstallation löscht alle 11 Tabellen aus der obigen Liste. Die Übersetzungstabelle von PrestaShop (`_DB_PREFIX_translation`) sowie die Sprachtabellen von Produkten, Kategorien und CMS bleiben unangetastet.

### 6.7. Schlüssel und Übersetzungen

**Schlüssel in `Configuration`** (Präfix `MYAITMI_`), Standardwerte aus `installDefaults()`:

| Schlüssel | Standard | Hinweise |
|---|---|---|
| `API_KEY_ENC` | `''` | Verschlüsselter API-Schlüssel. Lesen über `MyaitmiConfigService::getApiKey()`. |
| `MODEL` | `mistral-small-latest` | Aktives Modell. |
| `EXTRA_MODELS` | `''` | Von Hand ergänzte Modellkennungen, eine pro Zeile. |
| `PROVIDER` | `mistral` | Nach dem Speichern des Formulars immer `mistral`. |
| `TONE` | `formal` | `formal`, `casual` oder `brand`. |
| `CUSTOM_VOICE` | `''` | Der Text für **Brand voice**. |
| `BATCH_SIZE` | `25` | Bereich 1–100. |
| `MONTHLY_BUDGET` | `0` | USD, 0 = kein Limit. |
| `SOURCE_LOCALE` | `''` | Leer = die Sprache gibt der Bildschirm vor. |
| `TEMPERATURE` | `0.2` | Bereich 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Bereich 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | 0 schaltet das lokale Limit aus. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Versendet beim Abschluss eines Auftrags eine E-Mail (Vorlage `contact`). |
| `NOTIFY_EMAIL` | `''` | Empfängeradresse. Ist sie leer, wird `PS_SHOP_EMAIL` verwendet. |
| `PERM_ALLOW_PUBLISH` | `1` | Speichern im Shop. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Schaltflächen und Leiste in den Shop-Formularen. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Schaltflächen und Leiste auf der Übersetzungsseite. |
| `MAX_TOKENS` | `0` | 0 = Standardlimit des Anbieters. |
| `CRON_TOKEN` | zufällige 32-stellige Hex-Zeichenfolge | Token der Cron-Adresse. Wird beim ersten Lesen erzeugt, falls er fehlt. |

Schlüssel, die beim Speichern des Formulars oder bei der Deinstallation entfernt werden: `DEEPL_API_KEY` und `CLAUDE_API_KEY` (Überbleibsel früherer Versionen). Die Schlüssel der Update-Prüfung (`mypresta_updates`, `update_{name}`, `updatev_{name}`) bleiben erhalten.

**Übersetzungen der Oberfläche.** Jede Sprache liegt in `translations/{iso}.php` (z. B. `pl.php`, `de.php`, `fr.php`). Die Datei `en.php` ist die Quelle aller Texte. Die Texte laufen über `$this->l()` oder über die Domains `myaitmiforms` und `sectionhelp` (Feldbeschreibungen und Panel **Help**). Texte in Vorlagen werden als `{l s='…' mod='myaitranslationsmistral'}` geschrieben. Texte, die an JS übergeben werden (`labels` in `translationClientConfig()` und `aitHelpLabels`), laufen ebenfalls über `$this->l()`.

So fügen Sie eine Sprache hinzu: Kopieren Sie `translations/en.php` nach `translations/{iso}.php`, übersetzen Sie die Werte und lassen Sie die Schlüsselbezeichner unverändert.

### 6.8. Erweiterung

- **Theme des Shops:** Das Modul rendert nichts im Theme, daher gibt es keine Vorlage zum Überschreiben.
- **Übersetzungsanbieter:** Ein neuer Anbieter braucht eine Klasse, die `MyaitmiTranslationProviderInterface` implementiert, sowie eine Änderung in `MyaitmiProviderFactory`. Derzeit liefert die Factory nur Mistral.
- **Katalog-Adapter:** die Schnittstelle `MyaitmiTranslationAdapterInterface` und die Factory `MyaitmiTranslationAdapterFactory`.
- **Preisliste:** Die Preise pro Million Tokens stehen in `MyaitmiUsageLedger::estimateCost()`. Ändert Mistral die Preise, müssen Sie sie im Code aktualisieren.
- **Lokales Limit:** Die Datei `var/rate_limit.json` wird im Verzeichnis des Moduls angelegt.

## 7. Hilfe

Seite des Moduls: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html

Wenn Sie Hilfe zum Modul brauchen:

1. Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an.
2. Wechseln Sie zum Kontaktformular und wählen Sie das Thema **Support for paid modules**. Das Formular weist darauf hin, dass für kostenpflichtige Module eine Anmeldung nötig ist.
3. Wählen Sie nach dem Login dieses Modul aus Ihrem Kaufverlauf aus.
