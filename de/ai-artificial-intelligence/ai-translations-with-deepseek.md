---
title: "AI Translations with DeepSeek – Dokumentation und Benutzerhandbuch (user manual)"
sidebar:
  label: "AI Translations with DeepSeek – Dokumentation und Benutzerhandbuch (user manual)"
description: "Anleitung zur Konfiguration und Fehlerbehebung des Moduls AI Translations with DeepSeek für Shopbetreiber, die das Modul bereits besitzen."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul AI Translations with DeepSeek auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/ai-translations-with-deepseek/)
>
> ---


## 1. Anforderungen

Das Modul läuft in PrestaShop 1.7.0.0 oder neuer und benötigt einen API-Schlüssel aus Ihrem eigenen DeepSeek-Konto.

- **PrestaShop:** Version 1.7.0.0 oder neuer.
- **PHP:** Das Modul legt keine eigene minimale PHP-Version fest. Der Server muss die PHP-Version unterstützen, die Ihre PrestaShop-Version verlangt.
- **PHP-Erweiterungen:** cURL (Verbindung zu DeepSeek), mbstring (Zählen der Zeichen in Texten), OpenSSL (Verschlüsselung des API-Schlüssels) und JSON (Speichern der gesendeten und empfangenen Daten).
- **Andere Module:** Das Modul benötigt kein anderes Modul.
- **Außerhalb des Shops:** Ein eigenes DeepSeek-Konto mit API-Schlüssel. Ohne Schlüssel kann das Modul nichts übersetzen.
- **Cron auf dem Server:** Nur nötig, wenn Massenaufträge ohne Klicks laufen sollen. Siehe Abschnitt 3.1.
- **Großer Katalog:** Ein Massenauftrag wird in Teile (Slices) aufgeteilt, und jeder Teil ist ein Aufruf an DeepSeek. Große Bereiche dauern lange, prüfen Sie sie deshalb vor dem Start mit **Estimate**.

## 2. Installation

1. Laden Sie die ZIP-Datei des Moduls im **Module Manager** mit der Schaltfläche **Upload a module** hoch und klicken Sie auf **Install**.
2. Nach der Installation erscheint im Menü der Eintrag **International → AI Translations with DeepSeek**. Dieser Eintrag öffnet das Modulpanel.
3. Die Installation leert den Shop-Cache nicht. Wenn der neue Menüeintrag nicht erscheint, gehen Sie zu **Erweiterte Parameter → Leistung** (**Advanced Parameters → Performance**) und klicken Sie auf **Clear cache**.

Nach der Installation ist das Panel leer: Es gibt keinen API-Schlüssel, und die Einstellungen haben die Startwerte aus Abschnitt 3.1.

**Die Deinstallation** entfernt den Menüeintrag, die Massenaufträge mit ihrem Verlauf, das Glossar, die Ausschlussliste, das Übersetzungsgedächtnis, die Sicherungskopien für **Rollback**, den Aufruf- und Fehlerverlauf, die Prüfwarteschlange, die Liste auf dem Tab **Catalog** und alle Einstellungen einschließlich des API-Schlüssels und der Cron-Adresse.

Die Deinstallation **entfernt nicht** die bereits im Shop gespeicherten Übersetzungen: Texte von Produkten, Kategorien, CMS-Seiten und International → Translations bleiben, wie sie sind. Nach der Deinstallation können Sie diese Übersetzungen nicht mehr mit **Rollback** rückgängig machen, weil die Sicherungskopien zusammen mit dem Modul entfernt werden.

Eine erneute Installation **stellt entfernte Daten nicht wieder her**. Die Tabellen werden leer angelegt, und die Einstellungen kehren zu den Startwerten zurück. Auch die Cron-Adresse ändert sich. Kopieren Sie deshalb die neue Adresse erneut aus **Settings** und aktualisieren Sie den Zeitplan auf dem Server.

## 3. Konfiguration und Arbeit im Backoffice

Die Bildschirme des Panels sind auf Englisch. In dieser Anleitung werden Feld-, Tab- und Schaltflächennamen genau so angegeben, wie Sie sie auf dem Bildschirm sehen.

**Wer beginnt:** immer ein Mitarbeiter im Backoffice. Kunden starten keine Übersetzungen.

**Der Ablauf von Anfang bis Ende:**

1. Fügen Sie in **Settings** Ihren DeepSeek-Schlüssel ein, wählen Sie ein Modell und klicken Sie auf **Save**. Klicken Sie danach auf **Test connection**, um den Schlüssel zu prüfen.
2. Legen Sie **Source locale** (die Sprache des Originals) fest und prüfen Sie, ob **Allow publish / save** aktiviert ist.
3. Wählen Sie, was übersetzt werden soll. Einzelne Domänen und Zeichenketten übersetzen Sie auf **Manual**. Große Bereiche geben Sie über **Bulk** in Auftrag. Felder von Produkten, Kategorien und CMS-Seiten übersetzen Sie auf **Catalog**. Die Schaltflächen bei Feldern in Shop-Formularen und auf der Seite International → Translations funktionieren direkt dort, wo Sie arbeiten.
4. Auf **Manual** und neben Feldern erhalten Sie zuerst einen Übersetzungsvorschlag. Sie speichern ihn in einem separaten Schritt: mit der Schaltfläche **Save approved** auf **Manual**, durch Ankreuzen von **Save now (skip review)** oder mit der Schaltfläche **Save** von PrestaShop im Formular.
5. Auf **Bulk** klicken Sie auf **Estimate**. Es wird nichts gesendet oder gespeichert. Wenn die Schätzung passt, klicken Sie auf **Start job**. Der Auftrag landet auf **Jobs** und wartet. Er läuft nicht von selbst: Klicken Sie auf **Process slice** oder **Auto-process**, oder lassen Sie einen Cron-Aufruf auf dem Server die Teile abarbeiten.
6. Übersetzungen, die die Qualitätsprüfung nicht bestanden haben, landen in **Review**. Die Schaltfläche **Approve** ändert nur den Status der Zeile. Sie schreibt den Text nicht in den Shop.
7. **Glossary** und **Excludes** wirken sich auf die nächsten Übersetzungen aus. Bereits gespeicherte Übersetzungen ändern sich nicht.
8. **Dashboard** zeigt Lücken und Kosten, **History** zeigt jeden Aufruf an DeepSeek.

**So endet die Arbeit:** Ein Massenauftrag endet mit dem Status **completed** (alles übersetzt) oder **completed_with_errors** (es gab Fehler). Wenn die Benachrichtigung aktiviert ist, wird danach eine E-Mail gesendet. Eine manuelle Übersetzung endet, wenn die ausgewählten Zeilen im Shop gespeichert sind.

### 3.1 Settings (Moduleinstellungen)

Weg: **Module** → **Module Manager** → Name des Moduls → **Configure**. Die Schaltfläche **Configure** öffnet das Modulpanel, und der Tab **Settings** befindet sich in der Leiste oben.

![Tab Settings](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings.webp)

Weitere Teile desselben Formulars:

![Settings – Schalter für Übersetzungsschaltflächen und Quellsprache](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-buttons.webp)

![Settings – Limits, Budget und Temperatur](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-limits.webp)

![Settings – E-Mail, Speichern und Cron-Adresse mit den Schaltflächen Test connection und Save](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-publish.webp)

Das Speichern des Formulars mit **Save** ändert keine fertigen Übersetzungen. Wenn das Feld **DeepSeek API key** leer ist und vorher kein Schlüssel gespeichert wurde, erscheint die Meldung: „Settings saved. No API key is stored, so nothing can be translated until you paste one.“

| Feld | Startwert | Was es tut |
|---|---|---|
| **DeepSeek API key** | leer | Der Schlüssel aus Ihrem DeepSeek-Konto. Ein leeres Feld behält den bereits gespeicherten Schlüssel, ein neuer Wert ersetzt ihn. Ein leeres Feld löscht den Schlüssel nicht. Unter dem Feld wird der gespeicherte Schlüssel maskiert angezeigt. Anfragen gehen an api.deepseek.com. |
| **Model** | deepseek-flash | Das DeepSeek-Modell, das die Übersetzung schreibt. Die eingebauten Modelle sind: deepseek-flash, deepseek-v4-pro, deepseek-v4-flash, deepseek-chat und deepseek-reasoner. Ein Modell, auf das das Konto keinen Zugriff hat, schlägt mit einem Fehler fehl, der in **History** gespeichert wird. |
| **Add a DeepSeek model** | leer | Fügt eine Modellkennung hinzu, die nicht in der Liste steht. Geben Sie sie genau so ein, wie im DeepSeek-Konto, und klicken Sie auf **Add model**. Das hinzugefügte Modell wird sofort das aktive Modell. **Remove** löscht nur hier hinzugefügte Modelle. Eingebaute Modelle lassen sich nicht entfernen. |
| **Tone** | Formal | Ein Stil, der jeder Anweisung an das Modell hinzugefügt wird. **Formal** ist für Shop- und Backoffice-Texte, **Casual** ist lockerer, und **Brand** arbeitet zusammen mit dem Feld **Brand voice**. Neue Übersetzungen folgen dem Stil. Gespeicherte Übersetzungen ändern sich erst, wenn Sie sie erneut übersetzen. |
| **Brand voice** | leer | Einige Sätze, die beschreiben, wie der Shop klingen soll. Das Feld erscheint, wenn **Tone** auf **Brand** steht. Der Text wird der nächsten Anweisung hinzugefügt und überschreibt keine gespeicherten Übersetzungen. |
| **Source locale** | leer (—) | Die als Original behandelte Sprache, zum Beispiel English (en-US). Der Strich „—“ bedeutet, dass der Bildschirm, auf dem Sie übersetzen, die Quellsprache selbst liefert. Manuelle und Massenübersetzungen sowie die Schaltflächen auf International → Translations senden diese Sprache als Quelle. Die Standardsprache des Shops ändert sich nicht. |
| **Individual field buttons — shop forms** | Ja | Eine Schaltfläche neben jedem mehrsprachigen Feld in Shop-Formularen: Produkt, Kategorie, CMS und andere Formulare. Die Schaltfläche übersetzt nur dieses eine Feld. **Nein** blendet diese Schaltflächen im gesamten Shop aus. Auf International → Translations hat dies keine Wirkung. |
| **Individual field checkboxes — shop forms** | Ja | Ein Kontrollkästchen neben den Feldern in Shop-Formularen und eine Leiste unten, die die angekreuzten Felder übersetzt. **Nein** blendet Kontrollkästchen und Leiste aus. Die Schaltflächen aus der Zeile darüber haben einen eigenen Schalter. |
| **Individual field buttons — International → Translations** | Ja | Eine Schaltfläche neben jedem Feld auf International → Translations. **Nein** blendet diese Schaltflächen nur auf dieser Seite aus. Shop-Formulare bleiben unverändert. |
| **Individual field checkboxes — International → Translations** | Ja | Kontrollkästchen und Leiste auf International → Translations. Die Leiste übersetzt die angekreuzten Felder nacheinander. **Nein** blendet Kontrollkästchen und Leiste auf dieser Seite aus. |
| **Batch size** | 25 | Wie viele Zeichenketten in einem Aufruf an DeepSeek gesendet werden. Erlaubt sind Werte von 1 bis 100. Für den ersten Lauf wählen Sie 10 bis 25. Ein größerer Block beendet einen Auftrag mit weniger Aufrufen, aber nach einem Fehler wird ein größerer Teil wiederholt. |
| **Dry-run sample** | 10 | Wie viele Beispielzeichenketten **Estimate** vor einem Massenauftrag zeigt. Erlaubt sind Werte von 1 bis 50. **Estimate** speichert keine Übersetzungen. |
| **Max tokens (0 = default)** | 0 | Eine Grenze für die Länge einer Antwort. 0 bedeutet das Standardlimit von DeepSeek. Setzen Sie eine Zahl, wenn Antworten abgeschnitten oder zu lang sind. Die Grenze gilt nur für die folgenden Aufrufe. |
| **Budget USD / month** | 0 | Ein monatliches Limit in US-Dollar, berechnet aus dem gespeicherten Verbrauch. 0 bedeutet kein Limit. Wenn das Limit erreicht ist, stoppen neue Übersetzungen, bereits gespeicherte bleiben erhalten. |
| **Rate limit / min** | 60 | Wie viele Aufrufe der Shop pro Minute ausführen darf. 0 schaltet dieses lokale Limit aus. Aufrufe über dem Limit werden übersprungen und in **History** vermerkt. DeepSeek kann zusätzlich eigene Limits anwenden. |
| **Log retention days** | 30 | Wie viele Tage Einträge in **History** aufbewahrt werden. Das Minimum ist 1 Tag. Ältere Einträge werden gelöscht. Aufträge, Glossar und gespeicherte Übersetzungen werden nicht gelöscht. |
| **Temperature** | 0.2 | Wie frei das Modell den Text umformuliert. Ein Wert um 0,2 bleibt nah am Original, Werte näher bei 1 verändern die Sätze stärker. Erlaubter Bereich: 0 bis 1. Platzhalter und HTML werden nach jeder Übersetzung weiterhin geprüft. |
| **Email notify on complete** | Nein | Sendet eine E-Mail, wenn ein Massenauftrag abgeschlossen ist. Der Auftrag selbst läuft gleich, nur der Versand ändert sich. |
| **Notify email** | leer | Die Adresse, die die E-Mail über einen abgeschlossenen Auftrag erhält. Das Feld wirkt nur, wenn **Email notify on complete** aktiviert ist. Ein leeres Feld sendet an die Shop-Adresse aus den Firmendaten. Das Speichern der Adresse sendet keine Nachricht. Betreff und Text sind auf Englisch, zum Beispiel „myaitranslationsdeepseek job #41 completed“, im Text stehen die Anzahlen der erledigten, fehlgeschlagenen und übersprungenen Zeichenketten. |
| **Allow publish / save** | Ja | Ob das Modul Übersetzungen im Shop speichern darf. Bei **Nein** ist das Speichern auf **Manual**, in Massenaufträgen und auf **Catalog** gesperrt. Die Schaltflächen auf International → Translations füllen nur das Formular, und die Schaltfläche **Save** von PrestaShop speichert es. |
| **CRON URL** | erzeugte Adresse | Eine Adresse für den Zeitplan des Servers. Jeder Aufruf verarbeitet einen Teil eines wartenden Auftrags und endet dann. Veröffentlichen Sie diese Adresse nicht, denn wer sie kennt, kann einen Teil starten. Das Öffnen von **Settings** startet keinen Auftrag. |

Schaltflächen unten im Formular: **Save** speichert die Einstellungen. **Test connection** prüft den Schlüssel und speichert keine Übersetzung.

Empfohlener Start: Schlüssel einfügen, Modell wählen, **Source locale** setzen, auf **Save** klicken und danach **Test connection** ausführen. Lassen Sie die übrigen Werte auf den Startwerten, bis ein Auftrag nicht wie erwartet läuft.

### 3.2 Dashboard

Das Dashboard zeigt, wie viele Texte für die gewählte Sprache in jedem Teil des Katalogs fehlen, sowie die Nutzung von DeepSeek. Das Öffnen von **Dashboard** sendet keine Anfrage und ändert keine Übersetzungen.

![Dashboard](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard.webp)

- **Locale** ist die Sprache, deren Lücken gezählt werden. Beim ersten Öffnen wird die erste Sprache der Shopliste gewählt. Ändern Sie die Sprache und klicken Sie auf **Show**, um die Tabelle neu zu berechnen.
- **Abdeckungstabelle** mit den Spalten **Section**, **Done**, **Missing** und **Total**. Jede Zeile ist ein Teil des Katalogs: Backoffice, Themes, Module, E-Mails oder Sonstiges. Der Balken zeigt, wie viel bereits übersetzt ist.
- **Karten und Diagramme** zählen die Aufrufe aus dem gewählten Zeitraum. Die Filterfelder sind Datumsangaben (Vorgaben sowie **From** und **To**), dann **Model**, Typ, Status, Sprache, Mitarbeiter und ein Wort im Prompt oder in der Antwort. Die Schaltfläche **Filter** wendet den Filter an. Die Karten zeigen die Anzahl der Aufrufe, gesendete und empfangene Tokens, die durchschnittliche Dauer und die geschätzten Kosten. Die Kosten sind eine lokale Schätzung, keine Rechnung.
- **Latest prompts** listet die zehn neuesten Aufrufe. **View** öffnet Prompt und Antwort in einem Fenster. **See all** führt zu **History**.
- Unter der Tabelle steht die Cron-Adresse. Es ist dasselbe Geheimnis wie in **Settings**.

![Dashboard – Diagramme und Übersichten](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard-charts.webp)

Eine leere Abdeckungstabelle bedeutet, dass der Shop für diese Sprache noch keinen Katalog hat. Den Katalog legt International → Translations an.

### 3.3 Manual

**Manual** übersetzt eine gewählte Domäne, einige Zeichenketten auf einmal. **Filter** lädt nur die Liste und speichert nichts.

![Manual](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-manual.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Section** | Back office | Wählt den PrestaShop-Katalog zum Lesen: **Back office**, **Themes**, **Installed modules**, **Emails** oder **Others**. Ein Wechsel lädt das Formular neu und ruft DeepSeek nicht auf. |
| **Theme** | — | Erscheint nur bei **Themes**. Begrenzt die Liste auf ein Theme. |
| **Module** | — | Erscheint nur bei **Installed modules**. Begrenzt die Liste auf ein Modul. Ein Modul ohne Domänen lädt sofort alle seine Zeichenketten. |
| **Source** | Source locale aus **Settings** (en-US) | Die Sprache, aus der die Texte stammen. Wählen Sie die, die bereits eine verlässliche Übersetzung hat. Die Zielsprache ändert sich nicht. |
| **Target** | erste Sprache der Shopliste | Die Sprache, die Sie ergänzen möchten. Sie muss unter International → Localization → Languages existieren. Liste und späteres Speichern betreffen nur diese Sprache. |
| **Domain** | — | Die Übersetzungsdomäne, dieselben Gruppen wie auf International → Translations. Drücken Sie **Filter**, damit sich die Liste füllt, wählen Sie eine Domäne und drücken Sie erneut **Filter**. Bei einem Modul ohne Domänen erscheint das Feld nicht. |
| **Only empty** | Ja | Blendet Zeichenketten aus, die bereits eine Übersetzung haben. **Nein** zeigt alle Zeichenketten. Die Tabelle ändert sich, gespeicherte Übersetzungen werden nicht gelöscht. |
| **Search** | leer | Behält nur Zeichenketten, deren Quelle das eingegebene Wort enthält. Der Katalog ändert sich nicht. |

**So übersetzen Sie:**

1. Kreuzen Sie die Zeilen an oder klicken Sie auf **Check all** (markiert die sichtbaren Zeilen). **Uncheck all** hebt die Markierungen auf.
2. Klicken Sie auf **Translate selected (review)**. Das Modul sendet die markierten Zeichenketten und zeigt eine Prüftabelle. Noch wird nichts gespeichert.
3. Entfernen Sie in der Prüftabelle die Markierung bei einer Zeile, die Sie nicht speichern möchten, und korrigieren Sie den Vorschlag im Feld **AI proposal**.
4. Klicken Sie auf **Save approved**. Die markierten Zeilen werden gespeichert.

Wenn Sie vor dem Übersetzen **Save now (skip review)** ankreuzen, werden akzeptierte Zeilen sofort gespeichert, ohne die Prüftabelle.

Die Ergebnistabelle hat die Spalten **Source**, **Current** (die aktuelle Übersetzung), **AI proposal**, **Status** (**empty** oder **filled**), **Tokens** und **Warnings**. Eine Zeile mit defektem Platzhalter oder defektem HTML wird nicht gespeichert.

Meldungen, die Sie sehen können:

- „No strings match this filter. Nothing was sent to DeepSeek.“ — der Filter hat keine Zeichenketten gefunden. Es wurde nichts gesendet.
- „Review is ready. Nothing is saved until you press Save approved.“ — die Vorschläge warten in der Tabelle. Erst **Save approved** speichert sie.
- „Saved. The approved strings were written for the target language.“ — die markierten Zeilen wurden gespeichert.
- „Not saved because of broken placeholders or HTML: N.“ — N Zeilen wurden nicht gespeichert, weil das Modell einen Platzhalter oder ein HTML-Tag verändert hat. Korrigieren Sie sie in der Tabelle oder entfernen Sie die Markierung.

### 3.4 Bulk

**Bulk** legt einen Auftrag für viele Domänen und Sprachen an. Der Auftrag läuft auf dieser Seite nicht. Er wartet auf **Jobs**.

![Bulk](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-bulk.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Section** | Back office | Der Katalog, den der Auftrag liest. Das Feld **Theme** erscheint nur bei **Themes**, das Feld **Module** nur bei **Installed modules**. Zeichenketten außerhalb des gewählten Bereichs gehören nicht zum Auftrag. |
| **Source** | Source locale aus **Settings** (en-US) | Die Sprache, die der Auftrag als Original behandelt. Jedes Ziel wird aus ihr übersetzt. |
| **Targets** | leer | Die Sprachen, die der Auftrag ergänzt. Sie können mehrere wählen: Halten Sie Strg oder Cmd gedrückt und klicken Sie. Der Auftrag legt für jede gewählte Sprache eigene Zeichenketten an. |
| **Domains** | leer | Die Domänen, die in den Auftrag aufgenommen werden. Nicht gewählte Domänen werden nicht übersetzt. |
| **Policy** | Fill empty | **Fill empty** überspringt Zeichenketten, die bereits eine Übersetzung haben. **Overwrite all** sendet alle Zeichenketten, auch übersetzte, und kann sie ersetzen. **Outdated if equals source** sendet Zeichenketten, deren Übersetzung mit dem Original identisch ist. |
| **Dry-run job** | Nein | Der Auftrag ruft das Modell auf und speichert das Ergebnis im Auftragsverlauf, schreibt aber keine Übersetzungen in den Shop. Bei **Nein** speichert der Auftrag die Ergebnisse, sofern **Allow publish / save** aktiviert ist. |

**Estimate** zeigt die Anzahl der Zeichenketten, die geschätzten Tokens und Kosten sowie Beispielzeichenketten. Es wird nichts gesendet oder gespeichert. Meldung: „Estimate only: N strings, ~N tokens, ~$… Nothing was sent to DeepSeek and nothing was saved.“

**Start job** legt den Auftrag an und führt Sie zu **Jobs**, wo der neue Auftrag geöffnet ist. Meldung: „Job #N is waiting (N strings, est. $…). It has not run yet.“

Meldungen bei Fehlern, die den Start verhindern:

- „Nothing was started. Select at least one target language.“ — keine Zielsprache gewählt.
- „Nothing was started. Pick a theme.“ oder „Nothing was started. Pick a module.“ — im Bereich **Themes** oder **Installed modules** wurde kein Theme oder Modul gewählt.
- „Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.“ — kein Schlüssel. Es wurde kein Auftrag angelegt.

### 3.5 Jobs

**Jobs** ist die Warteschlange der Massenaufträge. Das Öffnen der Liste ruft DeepSeek nicht auf. Der Katalog ändert sich nur, während ein Auftrag verarbeitet wird und kein Probelauf (Dry-run) ist.

![Jobs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-jobs.webp)

**Die Auftragsliste** hat die Spalten **ID**, **Status**, **Locales**, **Progress**, **Cost**, **Employee** und **Date**. Klicken Sie auf einen Auftrag, um seine Zeichenketten zu sehen. Der Filter **Failed only** zeigt nur Fehler, und **Error CSV** lädt die Fehlerliste als Datei herunter.

Auftragsstatus, genau so wie in der Spalte **Status**: **pending** (wartet), **running** (läuft), **paused** (pausiert), **completed** (fertig), **completed_with_errors** (fertig mit Fehlern), **cancelled** (abgebrochen) und **failed** (mit Fehler beendet). Status der Zeichenketten in den Details: **pending**, **processing**, **done**, **failed**, **skipped** und **rolled_back**. Die Kennzeichnung **dry-run** markiert einen Probelauf.

**Schaltflächen im Auftrag:**

- **Process slice** sendet den nächsten Block (so viele Zeichenketten, wie **Batch size** angibt) und hält an. Nach dem Klick sehen Sie, welche Zeilen gespeichert, übersprungen oder fehlgeschlagen sind.
- **Auto-process** sendet Blöcke nacheinander, bis der Auftrag fertig ist oder fehlschlägt. Lassen Sie die Seite offen, denn der Fortschrittsbalken aktualisiert sich selbst.
- **Pause** hält den Auftrag an. Er übersetzt keine weiteren Zeichenketten, bis Sie ihn fortsetzen.
- **Resume** setzt den Auftrag zurück in die Warteschlange. Der Auftrag startet nicht von selbst: Klicken Sie auf **Process slice** oder **Auto-process**, oder warten Sie auf den Cron-Aufruf.
- **Retry failed** setzt die fehlgeschlagenen Zeichenketten zurück auf wartend.
- **Rollback** stellt die vorherigen Übersetzungen wieder her, wo das Modul vor der Änderung eine Sicherungskopie gespeichert hat. Vorher erscheint die Frage „Roll back this job?“. Meldung nach der Ausführung: „Rollback: restored N translations.“
- **Error CSV** lädt die Liste der fehlgeschlagenen Zeilen herunter.

**In dieser Version des Moduls gibt es auf dem Auftragsbildschirm keine Abbrechen-Schaltfläche.** Versuchen Sie nicht, einen Auftrag hier abzubrechen. Halten Sie ihn mit **Pause** an und setzen Sie ihn nicht fort.

Wenn DeepSeek zu viele Aufrufe ablehnt, stoppt der Auftrag von selbst. Sein Fehler lautet: „Rate limit — job auto-paused. Resume later.“

### 3.6 Review

**Review** ist die Warteschlange der Übersetzungen, die die Qualitätsprüfung angehalten hat. Hier landen Zeilen mit defektem Platzhalter oder HTML, mit sehr langer oder sehr kurzer Übersetzung oder mit einer Bewertung unter 70.

![Review](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-review.webp)

| Spalte | Was sie zeigt |
|---|---|
| **ID** | Die Nummer der Zeile in der Warteschlange. |
| **Domain** | Die Domäne, aus der der Text stammt. |
| **Source** | Der Originaltext. |
| **AI** | Der Vorschlag des Modells. |
| **Score** | Die automatische Qualitätsbewertung von 0 bis 100. |
| **Flags** | Die Gründe für das Anhalten, unten beschrieben. |

**Flags:**

- **validation_failed** — ein Platzhalter oder HTML-Tag fehlt oder wurde verändert.
- **length_explosion** — die Übersetzung hat mehr als das 2,5-Fache der Zeichen des Originals.
- **too_short** — die Übersetzung hat weniger als 30 % der Länge des Originals, und das Original hat mehr als 20 Zeichen.
- **possible_untranslated** — englische Wörter wie „the“, „and“, „with“ sind in der Übersetzung geblieben.
- **warning** — eine Prüfwarnung, die die Bewertung senkt.

**Approve** markiert die Zeile als akzeptiert, **Reject** als abgelehnt. Keine der beiden Schaltflächen speichert Text im Shop. Eine leere Warteschlange zeigt: „The queue is empty.“ Eine leere Warteschlange bedeutet nicht, dass alle Sprachen übersetzt sind. Prüfen Sie das im **Dashboard**.

Wenn der Auftrag speichern durfte und die Zeichenkette die Prüfung bestanden hat, kann die Übersetzung bereits im Shop stehen. Die Warteschlange **Review** ist eine Liste für die manuelle Kontrolle, keine Speichersperre. Das separate Speichern ausgewählter Zeilen erfolgt auf **Manual**.

### 3.7 Catalog

**Catalog** übersetzt Felder von Produkten, Kategorien und CMS-Seiten. Es betrifft nicht die Texte auf International → Translations. Ein Block umfasst höchstens 100 Datensätze.

![Catalog](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-catalog.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Entity** | product | Wählt die Art der Datensätze: **product**, **category** oder **cms**. Die Feldliste ändert sich mit der Wahl. Die Wahl allein übersetzt nichts. |
| **Fields** | für die Art standardmäßig gewählte Felder | Die Texte, die der Block sendet. Bei Produkten: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** und **Friendly URL**. Bei Kategorien: **Title**, **Description**, **Meta title**, **Meta description** und **Friendly URL**. Bei CMS: **Title**, **Meta description**, **Meta keywords**, **Content** und **Friendly URL**. Auswahl mit gedrückter Strg- oder Cmd-Taste. Nicht gewählte Felder werden nicht gesendet und bleiben unverändert. |
| **Source language** | erste Sprache der Liste | Die Sprache, aus der der Text kopiert wird. Sie ändert sich nicht. |
| **Target language** | erste Sprache der Liste | Die Sprache, die die Übersetzung erhält. Wählen Sie eine andere als die Quelle. |
| **Only empty** | Ja | Überspringt Felder, die in der Zielsprache bereits Text haben. **Nein** sendet auch gefüllte Felder, dann kann der Block diesen Text ersetzen. |
| **Start after ID** | 0 | Überspringt Datensätze bis zu dieser ID. 0 beginnt beim ersten Datensatz. Nach jedem Block füllt sich das Feld selbst, und der nächste Block beginnt nach dieser ID. |

Die Schaltfläche **Translate batch (max 100)** startet einen Block. Das Ergebnis zeigt, wie viele Zeilen gespeichert wurden und wie viele fehlgeschlagen sind.

Bevor Sie **Only empty** auf **Nein** setzen, führen Sie einen kleinen Block aus und öffnen Sie ein Produkt in der Zielsprache.

### 3.8 Glossary

**Glossary** ist eine Liste von Begriffen, die das Modell beibehalten oder auf feste Weise übersetzen soll. Das Hinzufügen eines Begriffs ändert keine gespeicherten Übersetzungen. Die nächsten Übersetzungen lesen die Liste.

![Glossary](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-glossary.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Source term** | leer (Pflichtfeld) | Das Wort oder die Wendung in der Originalsprache, einschließlich Groß- und Kleinschreibung, wenn sie wichtig ist. Das Modell behandelt diesen Begriff als fest, wenn er im Quelltext vorkommt. |
| **Target locale** | leer | Begrenzt die Zeile auf eine Sprache, z. B. pl-PL. Ein leeres Feld gilt für alle Zielsprachen. |
| **Target term** | leer | Die freigegebene Übersetzung des Begriffs. Lassen Sie das Feld nur leer, wenn **Do not translate** aktiviert ist. |
| **Do not translate** | Nein | Das Modell kopiert den Begriff unverändert. Aktivieren Sie es für Markennamen, SKUs und Platzhalter. Deaktivieren Sie es, wenn **Target term** die Übersetzung sein soll. |

Die Schaltfläche **Add** fügt den Begriff hinzu. Die Tabelle unter dem Formular hat die Spalten **Source**, **Locale**, **Target** und **Do not translate**, und jede Zeile hat eine Schaltfläche **Delete**, die nur diese Zeile entfernt. Eine leere Liste zeigt: „No glossary terms yet.“

**Import CSV** fügt Zeilen aus einer Datei hinzu. Die Datei braucht die Spalten: source_term, target_locale, target_term, do_not_translate. Der Import fügt nur Zeilen hinzu, die er lesen kann. **Export CSV** lädt die aktuelle Liste herunter und ändert nichts.

Kurze, genaue Begriffe funktionieren am besten. Ein sehr allgemeiner Begriff wird jedes Mal erzwungen, wenn er vorkommt.

### 3.9 Excludes

**Excludes** sind Textmuster, die nicht an DeepSeek gesendet werden dürfen. Der Text bleibt unverändert in PrestaShop. Das Modul überspringt ihn bei der nächsten manuellen Übersetzung, im Massenauftrag und bei Aktionen auf International → Translations.

![Excludes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-excludes.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Pattern** | leer (Pflichtfeld) | Der Text oder Ausdruck, der mit jedem Quelltext verglichen wird. Je nach **Type** ist es der ganze Text, der Anfang, ein Teil oder ein regulärer Ausdruck. |
| **Type** | exact | **exact** ist der ganze Text, **prefix** der Anfang, **contains** ein Teil an beliebiger Stelle und **regex** ein regulärer PHP-Ausdruck. Ein zu weites Muster überspringt mehr, als Sie erwarten. Beginnen Sie mit einem kurzen. |

Die Schaltfläche **Add** fügt das Muster hinzu. Die Tabelle hat die Spalten **Pattern**, **Type** und **On** (ob das Muster aktiv ist). Jede Zeile hat eine Schaltfläche **Delete**, die nur dieses Muster entfernt. Gespeicherte Übersetzungen werden nicht gelöscht. Eine leere Liste zeigt: „No patterns yet.“

Verwenden Sie Muster für Texte, die in der Originalsprache bleiben müssen, etwa rechtliche Namen oder technische Token. Soll ein Text auf feste Weise übersetzt werden, nutzen Sie **Glossary**.

### 3.10 History

**History** ist die vollständige Liste der gespeicherten Aufrufe an DeepSeek: manuelle Übersetzung, die Seite International → Translations, Massenaufträge, Catalog und der Verbindungstest. Jede Zeile enthält Prompt, Antwort, Modell, Sprachen, Tokenanzahl und Antwortzeit.

![History](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-history.webp)

- **When** ist das Datum des Aufrufs. **Type** ist der Ort, an dem er gestartet wurde. Bei einem Massenauftrag ist die Zahl nach dem Typ die Auftragsnummer.
- **View** öffnet den gesendeten Prompt und die zurückgekommene Antwort in einem Fenster auf dieser Seite. Eine Zeile mit Fehler zeigt den Fehler an Stelle der Antwort.
- Filter: Datum, **Model**, Typ, Status, Sprache, Mitarbeiter und ein Wort im Prompt oder in der Antwort. Die Schaltflächen **Previous** und **Next** blättern durch die Seiten.
- **HTTP 401** oder **HTTP 403** bedeutet, dass der Schlüssel in **Settings** falsch ist oder das Konto keinen Zugriff auf das gewählte Modell hat.
- **Clear history** löscht diese Einträge, gespeicherte Übersetzungen bleiben. Die Frage vor dem Löschen lautet: „Clear the stored history? Saved translations stay.“

Diese Seite sendet keine neue Anfrage und ändert keine Übersetzung. Wenn Übersetzungen plötzlich aufhören, sehen Sie sich die neueste Zeile mit Fehler an, bevor Sie das Glossar ändern.

### 3.11 Updates

Der Tab **Updates** zeigt den Bereich **MyPresta Updates**. Die Schaltfläche **Check Now** neben **Manual Check** prüft sofort, ob eine neuere Modulversion existiert. Das Feld **Automatic Notifications** (**Enabled** oder **Disabled**) legt fest, ob das Modul selbst prüft. Speichern Sie Ihre Wahl mit **Save**.

Wenn die automatischen Benachrichtigungen aktiviert sind, prüft das Modul alle 3 Tage die Version, sobald das Backoffice geöffnet wird. Es sendet den Modulnamen, die Modulversion, die Shop-Adresse und die Lizenzkennung, falls gespeichert, an den Server von MyPresta. Wenn Sie die Option ausschalten, enden diese automatischen Prüfungen.

![Updates](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-updates.webp)

### 3.12 Schaltflächen neben Feldern in Shop-Formularen

Neben mehrsprachigen Feldern in den Formularen für Produkte, Kategorien, CMS und andere Backoffice-Formulare erscheint eine Übersetzungsschaltfläche. Sind Felder angekreuzt, erscheint außerdem eine Leiste am unteren Rand des Formulars.

![Produkt – Übersetzung eines Feldes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-translate.webp)

![Produkt – Meta-Felder](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-meta.webp)

![Produkt – Übersetzungsleiste](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-bulk-bar.webp)

![Kategorieformular mit Übersetzungsleiste](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-category-translate.webp)

**Die Leiste** unten hat die Felder **Source** und **Target** sowie die Schaltflächen **Check all**, **Uncheck all**, **Check empty**, **Translate empty** und **Translate selected**. Der Zähler **Selected** zeigt, wie viele Felder angekreuzt sind.

Die Schaltfläche neben einem Feld füllt nur dieses Feld. Damit die Änderung im Shop bleibt, klicken Sie auf die Schaltfläche **Save** von PrestaShop unten im Formular. Die Leiste funktioniert genauso: Sie füllt die angekreuzten Felder und verlangt das Speichern des Formulars.

Meldungen auf der Leiste:

- „Fill the source language field first.“ — das Quellfeld ist leer. Geben Sie Text in der Quellsprache ein und versuchen Sie es erneut.
- „Tick at least one field.“ — nichts ist angekreuzt.
- „Target is not a language from this shop.“ — die gewählte Zielsprache gehört nicht zum Shop.
- „Translating…“ und „Done“ — Übersetzung läuft bzw. ist abgeschlossen.

Die Schaltflächen und die Leiste verschwinden, wenn die Schalter in **Settings** ausgeschaltet sind. Für Shop-Formulare steuern die Schalter **shop forms** diese Elemente.

### 3.13 Seite International → Translations

Auf der Seite International → Translations erscheint neben jedem Feld eine Übersetzungsschaltfläche, und unten erscheint dieselbe Leiste. Die Leiste hat das Feld **Source** (standardmäßig en-US) und das Feld **Target**. Wählen Sie die Sprache, die Sie ergänzen möchten.

![Seite International → Translations](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-translations-page.webp)

- Die Schaltfläche neben einem Feld füllt es mit der Übersetzung. Nur die Schaltfläche **Save** von PrestaShop auf dieser Seite speichert sie.
- Die Leiste übersetzt die angekreuzten Felder nacheinander.
- **Translate empty in this section** übersetzt die leeren Felder im geöffneten Bereich.
- Im Bereich **Emails** liest das Modul die Quelldatei der Vorlage. Findet es sie nicht, erscheint die Meldung: „The source language mail file was not found.“ Wählen Sie dann in **Settings** eine andere Quellsprache.
- Die Meldung „The source language field is not on this page.“ bedeutet, dass auf dieser Seite kein Feld für die Quellsprache vorhanden ist. Öffnen Sie einen anderen Tab oder Bereich, der diese Sprache hat.

Die Schalter **Individual field buttons** und **Individual field checkboxes — International → Translations** in **Settings** blenden die Schaltflächen und die Leiste nur auf dieser Seite aus.

## 4. Storefront

Das Modul zeigt Kunden nichts. Es fügt im Shop-Frontend keine Seite, keinen Block, keine Schaltfläche und keine Meldung hinzu. Daher zeigt das Theme keine Wirkung des Moduls, und es wird kein Screenshot der Storefront gemacht. Kunden haben im Modul keinen Schritt.

Die einzige Adresse, unter der ein externer Server das Modul aufrufen kann, ist die Cron-Adresse in **Settings**. Sie ist nicht für Kunden gedacht. Der Server nutzt sie, um Aufträge abzuarbeiten.

Was Sie sehen, wenn Sie diese Adresse im Browser öffnen:

| Was Sie sehen | Was zu tun ist |
|---|---|
| Der Text `{"ok":false,"error":"Forbidden"}` | Die Adresse ist falsch oder ihr Token ist veraltet. Kopieren Sie die CRON URL neu aus **Settings** und fügen Sie sie im Zeitplan ein. |
| Der Text `{"ok":true,"message":"No pending jobs"}` | Kein Auftrag wartet. Das ist normal, Sie müssen nichts tun. |
| Der Text `{"ok":true,...}` mit Daten eines Teils | Ein Teil wurde verarbeitet. Die Details sehen Sie auf **Jobs**. |
| Der Text `{"ok":false,"error":"..."}` mit einer Meldung | Lesen Sie die Meldung und gehen Sie zu Abschnitt 5 dieser Anleitung. |

## 5. Probleme

**Kein Eintrag im Menü International.** Die übliche Ursache ist der Shop-Cache. Gehen Sie zu **Erweiterte Parameter → Leistung** und klicken Sie auf **Clear cache**. Erscheint der Eintrag dann immer noch nicht, deinstallieren Sie das Modul und installieren Sie es erneut. Die Deinstallation entfernt die Einstellungen und den Auftragsverlauf, sichern Sie deshalb vorher Ihren API-Schlüssel und Ihre Einstellungen.

**„Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.“** Es wurde kein Schlüssel eingegeben oder er wurde entfernt. Öffnen Sie **Settings**, fügen Sie den Schlüssel aus Ihrem DeepSeek-Konto ein, klicken Sie auf **Save** und danach auf **Test connection**.

**„No DeepSeek API key. Nothing was translated.“** Derselbe Fall: Fügen Sie den Schlüssel in **Settings** ein und speichern Sie.

**„Settings saved. No API key is stored, so nothing can be translated until you paste one.“** Die Einstellungen wurden ohne Schlüssel gespeichert. Fügen Sie den Schlüssel ein und speichern Sie erneut.

**Test connection schlägt fehl, oder History zeigt HTTP 401 oder 403.** Der Schlüssel ist falsch, veraltet, oder das Konto hat keinen Zugriff auf das gewählte Modell. Fügen Sie den Schlüssel erneut ein. Betrifft der Fehler das Modell, wählen Sie ein anderes aus der Liste oder fügen Sie unter **Add a DeepSeek model** eine gültige Kennung hinzu.

**„DeepSeek rate limit (429). Try again later.“** DeepSeek hat die Anzahl der Aufrufe begrenzt. Warten Sie einige Minuten und setzen Sie den Auftrag auf **Jobs** mit **Resume** und **Process slice** fort. Kehrt der Fehler zurück, senken Sie **Batch size** in **Settings**.

**„Rate limit — job auto-paused. Resume later.“** Der Auftrag hat sich nach zu vielen abgelehnten Aufrufen selbst pausiert. Klicken Sie nach einiger Zeit im Auftrag auf **Resume** und danach auf **Process slice** oder **Auto-process**.

**„Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.“** Der Auftrag wartet auf einen manuellen Start oder auf den Cron-Aufruf. Klicken Sie auf **Process slice** oder **Auto-process**. Damit Aufträge ohne Klicks laufen, fügen Sie die CRON URL in den Zeitplan auf dem Server ein und rufen Sie sie regelmäßig auf.

**„Monthly API budget has been exhausted.“** Das monatliche Limit **Budget USD / month** ist erreicht. Öffnen Sie **Settings**, erhöhen Sie den Betrag oder setzen Sie 0, um das Limit aufzuheben. Neue Übersetzungen laufen weiter, sobald der Auftrag fortgesetzt wird.

**„Allow publish is off in Settings.“** Das Speichern von Übersetzungen ist gesperrt. Öffnen Sie **Settings** und aktivieren Sie **Allow publish / save**. Ohne diese Option speichert **Process slice** keinen Text im Shop.

**„Not saved because of broken placeholders or HTML: N.“** N Zeilen wurden nicht gespeichert, weil das Modell einen Platzhalter oder ein HTML-Tag verändert hat. Öffnen Sie **Review** oder die Tabelle auf **Manual**, korrigieren Sie den Vorschlag und speichern Sie erneut, oder lehnen Sie die Zeile ab.

**Der Auftrag ist mit dem Status completed_with_errors beendet.** Einige Zeichenketten sind fehlgeschlagen. Aktivieren Sie auf **Jobs** den Filter **Failed only**, laden Sie die **Error CSV** herunter und klicken Sie auf **Retry failed**, um die fehlgeschlagenen Zeichenketten erneut zu versuchen.

**Eine Übersetzung lässt sich nicht rückgängig machen.** **Rollback** stellt nur Übersetzungen wieder her, für die das Modul vor der Änderung eine Sicherungskopie gespeichert hat. Die Kopien gehören zum Auftrag. Sie verschwinden, wenn das Modul deinstalliert wird.

**Die Übersetzung ist gespeichert, aber die Seite zeigt den alten Text.** Leeren Sie den Cache: **Erweiterte Parameter → Leistung → Clear cache**. Denken Sie bei Shop-Formularen und auf International → Translations daran, dass die Schaltflächen und die Leiste die Felder nur füllen. Gespeichert werden sie durch die Schaltfläche **Save** von PrestaShop.

**Die Übersetzungsschaltflächen erscheinen nicht neben den Feldern.** Die Schalter sind ausgeschaltet. Öffnen Sie **Settings** und aktivieren Sie den passenden Schalter: **Individual field buttons** oder **Individual field checkboxes** für Shop-Formulare bzw. für International → Translations.

**„Fill the source language field first.“** Das Feld der Quellsprache ist leer. Geben Sie Text in dieser Sprache ein und versuchen Sie es erneut.

**„The source language mail file was not found.“** Für diese E-Mail-Vorlage gibt es keine Datei in der Quellsprache. Wählen Sie in **Settings** eine andere **Source locale** oder übersetzen Sie die Vorlage von Hand.

**Nach Start job passiert nichts.** Start job erstellt nur den Auftrag und startet ihn nicht. Öffnen Sie **Jobs** und klicken Sie auf **Process slice** oder **Auto-process**.

**Die E-Mail über einen abgeschlossenen Auftrag kommt nicht an.** Prüfen Sie, ob **Email notify on complete** aktiviert ist und die Adresse in **Notify email** stimmt. Ein leeres Feld sendet an die Shop-Adresse. Die E-Mail wird nur nach Abschluss des Auftrags gesendet. Prüfen Sie außerdem, ob der Shop überhaupt E-Mails versendet, unter **Erweiterte Parameter → E-Mail**.

**Ein Auftrag lässt sich nicht abbrechen.** Diese Version des Moduls hat auf dem Auftragsbildschirm keine Abbrechen-Schaltfläche. Halten Sie den Auftrag mit **Pause** an und setzen Sie ihn nicht fort.

**History ist leer oder zeigt „No requests yet.“** Es gab noch keinen Aufruf an DeepSeek. Auch das Dashboard zeigt Nullen, bis Sie eine Übersetzung ausführen.

## 6. Für Entwickler

Dieser Abschnitt beschreibt den Code des Moduls. Konfigurationsschlüssel und Klassennamen stehen nur hier.

### 6.1 Überblick

- **Hauptklasse:** `myaitranslationsdeepseek` (erweitert `Module`), Datei `myaitranslationsdeepseek.php`.
- **Technischer Name:** `myaitranslationsdeepseek`. Das Präfix der Konfigurationsschlüssel und Tabellen ist `MYAITDS_` bzw. `myaitds_`.
- **Version:** 1.2.0.
- **Name in der Modulliste:** AI Translations with DeepSeek.
- **Autor im Code:** MyPresta.eu. Tab: `administration`.
- **Kompatibilität:** PrestaShop 1.7.0.0 bis 99.99.99, `bootstrap = true`, `need_instance = 0`.
- **Menü-Tab:** Klasse `AdminMyaitranslationsdeepseek`, Elternteil `AdminInternational` (Ausweichlösung: `IMPROVE`).

Datenfluss: Die Einstellungen liest `MyaitdsConfigService` aus `Configuration` (Schlüssel `MYAITDS_*`). Die Dienste `MyaitdsTranslateService`, `MyaitdsJobWorker` und `MyaitdsCatalogTranslateService` sowie der Backoffice-Controller rufen `MyaitdsDeepSeekTranslationProvider` auf, der eine cURL-Anfrage an `https://api.deepseek.com/chat/completions` sendet (120 s Timeout, 15 s Verbindungs-Timeout). Die Antwort durchläuft die Validatoren (`MyaitdsPlaceholderValidator`, `MyaitdsHtmlValidator`, `MyaitdsPsNativeValidator`) und `MyaitdsQualityScorer`. Gespeichert wird über `MyaitdsTranslationAdapterFactory` in den Übersetzungsdienst von PrestaShop, und in die Tabelle `translation`, wenn der Dienst fehlt. Bei klassischen Modulen geht das Speichern in die `translations/{iso}.php` des jeweiligen Moduls. Aufrufe werden in `myaitds_request` und `myaitds_api_log` protokolliert, Kosten in `myaitds_usage_ledger`. Das Übersetzungsgedächtnis (`myaitds_memory`) erlaubt, einen API-Aufruf für dieselbe Quelle, Sprache, dasselbe Modell und dieselbe Glossarversion zu überspringen.

### 6.2 Dateien

| Datei | Zweck |
|---|---|
| `myaitranslationsdeepseek.php` | Hauptklasse: Installation, Deinstallation, Menü-Tab, Backoffice-Hooks, `getContent()` leitet zum Controller weiter. |
| `sql/install.php` | Legt die 11 Tabellen an (`CREATE TABLE IF NOT EXISTS`). |
| `sql/uninstall.php` | Löscht die 11 Tabellen (`DROP TABLE IF EXISTS`). |
| `controllers/admin/AdminMyaitranslationsdeepseekController.php` | Backoffice-Controller: alle Tabs, Formularaktionen, Auftragsaktionen und AJAX-Anfragen. |
| `controllers/front/cron.php` | Front-Controller `cron`: verarbeitet einen Teil eines Auftrags. |
| `src/Admin/MyaitdsForms.php` | HelperForm-Formulare und ihre `desc`-Texte. |
| `src/Admin/MyaitdsSectionHelp.php` | Hilfetext jedes Tabs. |
| `src/Service/MyaitdsConfigService.php` | Liest und schreibt `MYAITDS_*`, Modellliste, Wertebereiche, API-Schlüssel. |
| `src/Service/MyaitdsTranslateService.php` | Manuelle und schaltflächengestützte Übersetzung: Gedächtnis, Budget, Validierung, Speichern. |
| `src/Service/MyaitdsBulkJobFactory.php` | Schätzung und Anlage von Massenaufträgen. |
| `src/Service/MyaitdsCatalogTranslateService.php` | Felder von Produkten, Kategorien und CMS, Blöcke mit höchstens 100 Datensätzen. |
| `src/Service/MyaitdsDashboardService.php` | Berechnung der Abdeckung (fehlende und übersetzte Texte). |
| `src/Service/MyaitdsRateLimiter.php` | Limit der Aufrufe pro Minute, gespeichert in `var/rate_limit.json`. |
| `src/Job/MyaitdsJobWorker.php` | Verarbeitet Teile, speichert, Snapshots, Prüfwarteschlange, Abschluss-E-Mail. |
| `src/Job/MyaitdsJobRepository.php` | Liest und schreibt Aufträge und ihre Zeichenketten. |
| `src/Job/MyaitdsJobStatuses.php` | Konstanten für Auftrags- und Zeichenkettenstatus. |
| `src/Provider/MyaitdsDeepSeekTranslationProvider.php` | DeepSeek-API-Aufruf (cURL), Behandlung von Fehlern und HTTP-Codes. |
| `src/Provider/MyaitdsPromptBuilder.php` | Erstellt den Prompt mit Ton, Markenstimme und Glossar. |
| `src/Provider/MyaitdsProviderFactory.php` | Erstellt den Anbieter (derzeit nur DeepSeek). |
| `src/Provider/MyaitdsTranslationProviderInterface.php` | Schnittstelle des Übersetzungsanbieters. |
| `src/Adapter/MyaitdsTranslationAdapterInterface.php` | Schnittstelle zum Zugriff auf den PrestaShop-Katalog. |
| `src/Adapter/MyaitdsAbstractTranslationAdapter.php` | Gemeinsame Logik: Bereiche, Domänen, Speichern, Cache-Leerung. |
| `src/Adapter/MyaitdsFilesystemCatalogueTrait.php` | Durchsuchen von XLF-Dateien und Übersetzungsverzeichnissen. |
| `src/Adapter/MyaitdsLegacyModuleCatalogue.php` | Liest und schreibt `translations/{iso}.php` klassischer Module. |
| `src/Adapter/MyaitdsTranslationAdapter.php` | Konkrete Adapter-Implementierung (erweitert den abstrakten Adapter). |
| `src/Adapter/MyaitdsTranslationAdapterFactory.php` | Erstellt den Adapter. |
| `src/Quality/MyaitdsPlaceholderValidator.php` | Prüft Platzhalter in der Übersetzung. |
| `src/Quality/MyaitdsHtmlValidator.php` | Prüft HTML-Tags. |
| `src/Quality/MyaitdsPsNativeValidator.php` | Kombiniert Platzhalter- und HTML-Prüfung. Nutzt PrestaShop-Klassen (`Validate::isCleanHtml`), wenn verfügbar. |
| `src/Quality/MyaitdsEmailHtmlPipeline.php` | Schützt Tags und Variablen in E-Mail-Vorlagen vor der Übersetzung. |
| `src/Quality/MyaitdsQualityScorer.php` | Bewertung 0–100, Flags und die Entscheidung für die Prüfwarteschlange (Schwelle 70). |
| `src/Glossary/MyaitdsGlossaryRepository.php` | Liest und schreibt das Glossar. CSV-Import und -Export liegen im Controller. |
| `src/Glossary/MyaitdsExcludePatternRepository.php` | Ausschlussmuster. |
| `src/Audit/MyaitdsRequestLogRepository.php` | Aufrufverlauf (**History**): Speichern, Filter, Anzeige und Bereinigung nach Aufbewahrung. |
| `src/Audit/MyaitdsApiLogRepository.php` | API-Protokoll und dessen Aufbewahrung. |
| `src/Audit/MyaitdsTranslationMemory.php` | Übersetzungsgedächtnis (Hash aus Quelle, Sprache, Modell und Glossar). |
| `src/Audit/MyaitdsUsageLedger.php` | Monatlicher Verbrauch und Kosten, Quelle für das Budget. |
| `src/Audit/MyaitdsSnapshotService.php` | Werte vor einer Änderung und deren Wiederherstellung (**Rollback**). |
| `src/Security/MyaitdsApiKeyEncryptor.php` | Verschlüsselung des API-Schlüssels (AES-256-CBC). |
| `views/templates/admin/configure.tpl` | Gerüst des Panels mit Tabs. |
| `views/templates/admin/_partials/*.tpl` | Inhalt der Tabs: dashboard, manual, bulk, jobs, review, catalog, glossary, excludes, logs, settings, history-stats. |
| `views/js/admin.js` | Backoffice-Logik: Aufträge, automatische Verarbeitung, Formulare. |
| `views/js/admin-help.js` | Hilfefenster auf den Tabs. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Diagramme auf **Dashboard**. |
| `views/js/entity-fields.js` | Schaltflächen und Leiste neben Feldern in Shop-Formularen. |
| `views/js/translations-tool.js` | Schaltflächen und Leiste auf International → Translations. |
| `views/css/admin.css` | Stile des Panels und der Schaltflächen. |
| `lib/updateChecker.php` | Versionsprüfung bei MyPresta und Tab **Updates**. |
| `translations/*.php` | Übersetzungen des Moduls (27 Sprachen, darunter `pl.php`). |
| `var/rate_limit.json` | Stand des Limits der Aufrufe pro Minute. |
| `logo.png`, `logo.gif` | Logo in der Modulliste und im Panel. |

### 6.3 Controller

**Backoffice:** `AdminMyaitranslationsdeepseekController`, Tab `AdminMyaitranslationsdeepseek`, Elternteil `AdminInternational`. Der Tab wird über den Parameter `myaitds_tab` gewählt. Erlaubte Werte: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (der Tab **History**), `review`, `catalog` und `updates`. Jeder andere Wert öffnet `dashboard`. Der Controller definiert keine eigenen Berechtigungen; es gelten die in PrestaShop gesetzten Tab-Berechtigungen.

Formularaktionen (`Tools::isSubmit`): `submitMyaitranslationsdeepseekSettings`, `…Ping` (Test connection), `…AddModel`, `…GlossaryAdd`, `…GlossaryImport`, `…GlossaryExport`, `…ExcludeAdd`, `…BulkPreview`, `…Bulk`, `…ManualFilter`, `…ManualTranslate`, `…SaveReview`, `…Catalog`, `…Dashboard`, `…ClearHistory`.

GET-Aktionen: `job_action` (`process`, `pause`, `resume`, `retry_failed`, `rollback`, `export_errors`; `cancel` ist implementiert, aber kein Template erzeugt einen Link dazu), `review_action` (`approve`, `reject`) mit `id_review`, `delete_deepseek_model`, `delete_glossary`, `delete_exclude`.

AJAX-Aktionen (`?controller=AdminMyaitranslationsdeepseek&ajax=1&action=…`), verarbeitet von den Methoden `displayAjax*`: `HistoryDetail` (Details eines Verlaufseintrags, Parameter `hist_id`), `ProcessJob` (ein Teil, `id_job`), `JobStatus` (Auftragsstatus), `TranslatePageLines` (Zeilen der Übersetzungsseite), `MailSource` (Quelldatei einer Mailvorlage), `ListDomains` (Domänen eines Bereichs).

**Front:** `MyaitranslationsdeepseekCronModuleFrontController` in `controllers/front/cron.php`. Die Adresse hat die Form `index.php?fc=module&module=myaitranslationsdeepseek&controller=cron&token=…`. Controller-Einstellungen: `$ssl = true`, `$ajax = true`. Parameter: `token` (Pflicht, Vergleich mit `MYAITDS_CRON_TOKEN` über `hash_equals`) und optional `id_job`. Ohne `id_job` nimmt das Modul den ersten Auftrag mit Status `pending` oder `running` unter den 20 neuesten. Ein falsches Token liefert HTTP 403 mit `{"ok":false,"error":"Forbidden"}`. Ohne Aufträge kommt `{"ok":true,"message":"No pending jobs"}`. Ein verarbeiteter Teil liefert das Ergebnis von `processSlice`.

### 6.4 Hooks

Bei der Installation registriert:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: benennt den Tab um, falls der Name noch technisch ist, und lädt die Backoffice-Assets.
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: lädt dieselben Assets.

`loadBoAssets()` arbeitet so: Auf dem Tab `AdminMyaitranslationsdeepseek` werden `admin.css`, `admin.js`, `admin-help.js` eingebunden, auf **Dashboard** zusätzlich `chart.min.js` und `history-charts.js`. Auf der Seite `AdminTranslations` wird `translations-tool.js` eingebunden, wenn Schaltflächen oder Leiste für International → Translations aktiv sind (`MYAITDS_TR_BUTTONS` oder `MYAITDS_TR_BULK`). Auf den übrigen Backoffice-Seiten wird `entity-fields.js` eingebunden, wenn Schaltflächen oder Leiste für Shop-Formulare aktiv sind (`MYAITDS_ENTITY_BUTTONS` oder `MYAITDS_ENTITY_BULK`). Über `Media::addJsDef` werden `myaitdsTr` und `aitHelpLabels` übergeben.

Das Modul stellt **keine eigenen Hooks** bereit: Es ruft `Hook::exec` nicht auf und registriert keine Hooks für das Frontend.

Das Modul hat **keine** Methoden `enable()` und `disable()`. Aktivieren und Deaktivieren führen keine Modulaktion aus. Die Hooks entfernt PrestaShop bei der Deinstallation.

### 6.5 Überschreibungen

Das Modul hat kein Verzeichnis `override/` und überschreibt keine Klasse oder Controller von PrestaShop.

Vom Modul geschriebene Dateien: Übersetzungen gehen über den Übersetzungsdienst von PrestaShop (`prestashop.service.translation`) und in die Tabelle `translation`, wenn der Dienst fehlt. Bei klassischen Modulen (Schlüssel im Format `<{name}>prestashop`) schreibt das Modul die `translations/{iso}.php` dieses Moduls neu, zuerst in eine temporäre Datei, dann durch Umbenennen. Den Cache leert es mit `Tools::clearCache()`. Außerdem schreibt es `var/rate_limit.json` sowie die Werte `update_<Modul>`, `updatev_<Modul>` und `mypresta_updates` in `Configuration`.

### 6.6 Datenbank

Die Tabellen verwenden das Shop-Präfix (`_DB_PREFIX_`). Alle werden mit der Engine `_MYSQL_ENGINE_` und der Kollation `utf8mb4_unicode_ci` angelegt.

| Tabelle | Inhalt |
|---|---|
| `myaitds_glossary` | Glossarbegriffe: `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, Daten. Index `idx_shop_locale`. |
| `myaitds_exclude_pattern` | Ausschlussmuster: `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`, `date_add`. |
| `myaitds_job` | Aufträge: `uuid` (eindeutig), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, Zähler `items_*`, Tokens, `cost_usd_estimate` und `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`. |
| `myaitds_job_item` | Zeichenketten eines Auftrags: `id_myaitds_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`. |
| `myaitds_memory` | Übersetzungsgedächtnis: `memory_hash` (eindeutig), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitds_usage_ledger` | Tagesverbrauch: `usage_date`, `id_myaitds_job`, `model`, Tokens, `cost_usd`. Quelle für das monatliche Budget. |
| `myaitds_snapshot` | Werte vor einer Änderung: `id_myaitds_job`, `id_myaitds_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. Quelle für **Rollback**. |
| `myaitds_api_log` | API-Protokoll: `id_myaitds_job`, `level`, `provider`, `http_code`, `message`, `context_json`. Bereinigt durch `MYAITDS_LOG_RETENTION_DAYS`. |
| `myaitds_request` | Aufrufverlauf (**History**): Typ, Status, Modell, Sprachen, HTTP-Code, Dauer, Tokens, Kosten, `prompt`, `reply`, `error_message`. Bereinigt nach Aufbewahrung. |
| `myaitds_review` | Prüfwarteschlange: `id_myaitds_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`. |
| `myaitds_catalog_item` | Wird bei der Installation angelegt, aber kein Code schreibt in sie oder liest aus ihr. |

Die Installation legt Tabellen nur mit `CREATE TABLE IF NOT EXISTS` an. Beim Öffnen einer Seite ergänzt das Modul keine Spalten (im Code gibt es kein `ALTER TABLE`).

Die Deinstallation löscht alle 11 Tabellen. Eine erneute Installation legt sie leer an.

### 6.7 Schlüssel und Übersetzungen

**Konfigurationsschlüssel** (Präfix `MYAITDS_`) und Startwerte aus `installDefaults()`:

| Schlüssel | Startwert | Hinweise |
|---|---|---|
| `API_KEY_ENC` | `''` | Mit AES-256-CBC verschlüsselter Schlüssel; der Verschlüsselungsschlüssel wird aus `_COOKIE_KEY_` abgeleitet. |
| `MODEL` | `deepseek-flash` | Das Aufrufmodell. |
| `EXTRA_MODELS` | `''` | Hinzugefügte Modellkennungen (**Add a DeepSeek model**). |
| `PROVIDER` | `deepseek` | Der einzige Anbieter. Im Panel gibt es dafür kein Feld. |
| `TONE` | `formal` | `formal`, `casual`, `brand`. |
| `CUSTOM_VOICE` | `''` | Text der Markenstimme. |
| `BATCH_SIZE` | `25` | Bereich 1–100. |
| `MONTHLY_BUDGET` | `0` | 0 = kein Limit. |
| `SOURCE_LOCALE` | `''` | Leer heißt: Der Bildschirm liefert die Quelle. Fallback im Code: `en-US`. |
| `TEMPERATURE` | `0.2` | Bereich 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Bereich 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | Das Formularfeld heißt `MYAITDS_RATE_LIMIT`. 0 schaltet das Limit aus. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | E-Mail-Schalter. |
| `NOTIFY_EMAIL` | `''` | Leer = `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Sperrt das Speichern aus **Manual**, Aufträgen und **Catalog**. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Schaltflächen und Leiste neben Feldern in Shop-Formularen. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Schaltflächen und Leiste auf International → Translations. |
| `MAX_TOKENS` | `0` | 0 = Standardlimit von DeepSeek. |
| `CRON_TOKEN` | zufällige 16 Byte (hex) | Token der Cron-Adresse. |

Bei der Deinstallation werden die oben genannten Schlüssel entfernt sowie `DEEPL_API_KEY` und `CLAUDE_API_KEY`, die das Modul nicht mehr verwendet.

**Texte ohne `$this->l()`.** Feld- und Hilfetexte laufen über `l()` in den Domänen `myaitdsforms` (`MyaitdsForms`) und `sectionhelp` (`MyaitdsSectionHelp`). JavaScript-Bezeichnungen gehen über `translationClientConfig()` an `Media::addJsDef`. Betreff und Text der Abschluss-E-Mail stehen in `MyaitdsJobWorker::notifyComplete()` auf Englisch und laufen nicht über `l()`. Meldungen, die über `$this->module->l()` im Controller ausgegeben werden, verwenden die Domäne `adminmyaitranslationsdeepseekcontroller`.

**Sprache hinzufügen:** Legen Sie eine Datei `translations/{iso}.php` nach dem Vorbild der vorhandenen an (z. B. `translations/pl.php`). PrestaShop lädt die Datei, die zum ISO-Code des Shops passt.

**Quelle der Feldtexte:** `MyaitdsForms::help()` (das `desc` jedes Feldes) sowie `MyaitdsSectionHelp::pages()` und `brief()` (Hilfetext der Tabs).

### 6.8 Erweiterungen

- **Theme:** Es gibt nichts zu überschreiben. Das Modul rendert keine Frontend-Templates.
- **Backoffice-Templates:** `views/templates/admin/`. Änderungen an den Moduldateien gehen bei einem Update verloren.
- **Neue DeepSeek-Modelle:** keine Codeänderung nötig; nutzen Sie **Add a DeepSeek model** (`EXTRA_MODELS`).
- **Neuer Anbieter:** Implementieren Sie `MyaitdsTranslationProviderInterface` und fügen Sie einen Eintrag in `MyaitdsProviderFactory` hinzu.
- **Schwelle der Prüfwarteschlange:** 70 Punkte, gesetzt in `MyaitdsQualityScorer::score()`.
- **Glossar und Ausschlüsse:** werden im Panel gepflegt, keine Codeänderung nötig.

## 7. Hilfe

Modulseite: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html

Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an, gehen Sie zum Kontakt und wählen Sie das Thema **Support for paid modules**. Das Formular gibt an, dass für kostenpflichtige Module eine Anmeldung erforderlich ist. Wählen Sie nach der Anmeldung dieses Modul aus Ihrem Kaufverlauf aus.
