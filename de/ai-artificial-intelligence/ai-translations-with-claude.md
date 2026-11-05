---
title: "AI Translations with Claude - Dokumentation und Benutzerhandbuch"
description: "Konfiguration und Fehlersuche für Shops, die das Modul AI Translations with Claude bereits einsetzen."
sidebar:
  label: "AI Translations with Claude - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul AI Translations with Claude auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/ai-translations-with-claude/)
>
> ---


## 1. Voraussetzungen

Das Modul läuft mit PrestaShop 1.7.0.0 und neuer, einschließlich PrestaShop 8 und 9.

- **PrestaShop:** 1.7.0.0 oder neuer.
- **PHP:** 5.6 oder neuer.
- **PHP-Erweiterungen:** cURL, OpenSSL, SimpleXML und mbstring.
- **Weitere Module:** Das Modul braucht kein anderes Modul.
- **Außerhalb des Shops:** ein Anthropic-Konto und ein API-Schlüssel, den Sie unter https://console.anthropic.com/settings/keys erstellen. Der Server des Shops muss `https://api.anthropic.com/v1/messages` erreichen können.
- **Optional:** eine geplante Aufgabe auf dem Server, die die Cron-Adresse aus **Settings** aufruft. Ohne sie arbeiten Sie die Aufträge selbst auf **Jobs** ab.
- **Große Kataloge:** Eine Domain mit Tausenden Zeichenketten bedeutet viele API-Aufrufe. Der Auftrag wird in Abschnitte der Größe **Batch size** aufgeteilt. Starten Sie vorher auf **Bulk** die Schätzung mit **Estimate**.
- Der Shop braucht mindestens zwei Sprachen. Bei nur einer Sprache zeigt das Backoffice den Hinweis **The shop needs at least two languages.** An dieser Stelle gibt es nichts zu übersetzen.

## 2. Installation

1. Öffnen Sie **Modules** und danach **Module Manager**. Wählen Sie **Upload a module**, laden Sie die ZIP-Datei hoch und klicken Sie bei **AI Translations with Claude** auf **Install**.
2. Nach der Installation finden Sie **AI Translations with Claude** im Menü **International**.
3. Die Installation leert den Shop-Cache nicht. Das Modul leert ihn, sobald es eine Übersetzung speichert.

Öffnen Sie danach **AI Translations with Claude**, wechseln Sie zu **Settings** und fügen Sie Ihren Claude-Schlüssel ein. Solange kein Schlüssel gespeichert ist, zeigt jede Seite des Moduls **No Claude API key.** und den Link **Open Settings**.

**Deinstallation.** Klicken Sie im **Module Manager** auf **Uninstall** und bestätigen Sie **Delete this module and its data (jobs, glossary, cache)?**

- Der Menüeintrag verschwindet. Gelöscht werden die Aufträge, das Glossar, die Ausschlussmuster, der Aufrufverlauf, die Warteschlange **Review**, die Rollback-Kopien, das Kostenprotokoll und die Moduleinstellungen, einschließlich des API-Schlüssels.
- Texte, die das Modul bereits in den Shop geschrieben hat, bleiben erhalten: Katalogübersetzungen und die Übersetzungsdateien klassischer Module, die dieses Modul geschrieben hat. Die Auswahl zur Update-Prüfung bleibt ebenfalls.
- Eine Neuinstallation stellt gelöschte Aufträge, das Glossar und den Verlauf nicht wieder her. Sie setzt die Standardwerte und erzeugt eine neue Cron-Adresse.

## 3. Konfiguration und tägliche Arbeit

Das gesamte Modul liegt auf einer Seite: **International**, danach **AI Translations with Claude**. Die Registerkarten heißen **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** und **Settings**. **Updates** steht am Ende der Leiste. **Help** öffnet ein Fenster für die Registerkarte, auf der Sie gerade sind.

Die Namen der Schaltflächen und Felder in dieser Anleitung stammen aus dem englischen Backoffice. In einer anderen Backoffice-Sprache sehen Sie die Übersetzung desselben Elements.

**Vom ersten Klick bis zur gespeicherten Übersetzung**

Ein Mitarbeiter des Shops startet die Arbeit im Backoffice. Kunden lösen keine Übersetzung aus.

1. **Settings.** Fügen Sie den Claude-Schlüssel ein, wählen Sie Modell und Ausgangssprache, klicken Sie auf **Test connection** und danach auf **Save**. Ohne Schlüssel sendet kein Werkzeug Text an Claude.
2. **Wählen Sie die Arbeitsweise.**
   - Wenige Zeichenketten oder eine Domain, mit Prüfung vor dem Speichern: **Manual** (3.3).
   - Eine große Domain, ein Theme oder ein Modul: **Bulk**, danach der Auftrag auf **Jobs** (3.4 und 3.5).
   - Felder von Produkt, Kategorie und CMS: **Catalog**, höchstens 100 Datensätze auf einmal (3.7).
   - Einzelne Felder auf **International → Translations** (3.12) und in den Formularen von Produkt, Kategorie und CMS (3.13).
3. **Qualitätsprüfung.** Jede übersetzte Zeichenkette wird auf Platzhalter und HTML geprüft. Besteht sie die Prüfung nicht, wird sie nicht gespeichert. Zeichenketten mit einem Wert unter 70, Zeichenketten, die mehr als zweieinhalbmal so lang sind wie die Quelle, sowie Zeichenketten mit noch enthaltenen englischen Wörtern wie *the*, *and*, *with*, *your* oder *please* landen in **Review**.
4. **Speichern.**
   - **Manual:** **Translate selected (review)** speichert nichts, bis Sie auf **Save approved** klicken. **Save now (skip review)** schreibt die gültigen Zeilen sofort.
   - **Bulk:** Der Auftrag wartet auf **Jobs**. Er schreibt erst nach **Process slice**, nach **Auto-process** oder nach dem Aufruf der Cron-Adresse. Ein Auftrag mit eingeschaltetem **Dry-run job** schreibt nichts.
   - **Catalog:** Gültige Zeilen werden sofort in der Zielsprache gespeichert.
   - **International → Translations** und die Shop-Formulare: Die Schaltflächen füllen nur die Felder. Gespeichert werden sie mit der Schaltfläche **Save** von PrestaShop.
   - Ist **Allow publish / save** ausgeschaltet, schreiben **Manual**, **Bulk** und **Catalog** nichts in den Shop.
5. **Ende des Auftrags.** Auf **Jobs** wechselt der Status zu **completed** oder **completed_with_errors**. Zeilen auf **Review** verschwinden nach **Approve** oder **Reject** aus der Liste. **Catalog** meldet, wie viele Zeilen gespeichert wurden und wie viele fehlgeschlagen sind.

### 3.1. Modulkonfiguration

Öffnen Sie **Modules**, dann **Module Manager**, suchen Sie **AI Translations with Claude** und klicken Sie auf **Configure**. Es öffnet sich das **Dashboard**. Wechseln Sie zu **Settings**.

**Save** und **Test connection** stehen unten im Formular. Das Speichern dieses Formulars startet keine Übersetzung und ändert keine Übersetzungen, die bereits im Shop gespeichert sind.

![Einstellungen, englisches Backoffice. Oberer Teil des Formulars: Claude API key, Model, Add a Claude model, Tone und Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings.webp)

**Verbindung**

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Claude API key** | leer | Der geheime Schlüssel, den dieser Shop an Claude sendet. Fügen Sie den Schlüssel von https://console.anthropic.com/settings/keys ein. Lassen Sie das Feld leer, um den bereits gespeicherten Schlüssel zu behalten. Ein neuer Wert ersetzt den gespeicherten Schlüssel. Ein leeres Feld löscht ihn nicht. Ist ein Schlüssel gespeichert, zeigt der Hilfetext **Key saved:** und den maskierten Schlüssel. |
| **Model** | claude-haiku-4-5 | Das Claude-Modell, das die Übersetzungen schreibt. Die eingebauten Namen bleiben in der Liste: claude-haiku-4-5, claude-sonnet-4-5 und claude-opus-4-5. Die nächste Übersetzung verwendet das gewählte Modell. Kann das Konto ein Modell nicht nutzen, schlägt der Aufruf fehl, und der Fehler steht auf **History**. |
| **Add a Claude model** | leer | Geben Sie die genaue ID aus Ihrem Anthropic-Konto ein und klicken Sie auf **Add model**. Die neue ID erscheint in **Model** und wird zum aktiven Modell. **Remove** löscht nur die hier hinzugefügten IDs. Eingebaute IDs lassen sich nicht löschen. |

Meldungen: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example claude-haiku-4-5.**, **Built-in models cannot be removed.**

**Stimme und Quelle**

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Tone** | Formal | Hängt jedem Prompt eine Stilvorgabe an. **Formal** eignet sich für Shop- und Backoffice-Texte, **Casual** klingt lockerer, und **Brand** wird zusammen mit **Brand voice** verwendet. Neue Übersetzungen folgen diesem Stil. Bereits vorhandene Übersetzungen bleiben, bis Sie sie erneut übersetzen lassen. |
| **Brand voice** | leer | Erscheint, wenn **Tone** auf **Brand** steht. Ein paar schlichte Sätze darüber, wie der Shop klingen soll. Der Text wird dem nächsten Prompt hinzugefügt. Ist das Feld leer, gibt es keine zusätzliche Stimme. Bereits gespeicherte Übersetzungen werden nicht umgeschrieben. |
| **Source locale** | leer | Die Sprache, die das Modell als Original behandelt. Die leere Auswahl ist ein Strich in der Liste: Dann liefert der Bildschirm, den Sie übersetzen, die Quelle. Wählen Sie die Locale, in der Ihre Kataloge geschrieben sind, meist en-US. **Manual**, **Bulk** und die Symbole auf **International → Translations** verwenden diese Locale als Quelle. Die Standardsprache des Shops ändert sich nicht. |
| **Individual field buttons — shop forms** | Yes | Eine Schaltfläche an jedem mehrsprachigen Feld der Shop-Formulare: Produkt, Kategorie, CMS und die übrigen Backoffice-Formulare. Die Schaltfläche übersetzt nur dieses eine Feld. **No** blendet diese Schaltflächen im ganzen Shop aus. Gespeicherte Übersetzungen bleiben unverändert. |
| **Individual field checkboxes — shop forms** | Yes | An jedem dieser Felder gibt es ein Kontrollkästchen, und die Leiste übersetzt nur die Felder, die Sie ankreuzen. **No** blendet Kontrollkästchen und Leiste aus. Die Schaltflächen darüber haben einen eigenen Schalter. |
| **Individual field buttons — International → Translations** | Yes | Eine Schaltfläche an jedem Feld auf **International → Translations**. **No** blendet diese Schaltflächen aus. Die Shop-Formulare sind nicht betroffen. Ein Klick füllt das Feld aus. Die Seite speichert weiterhin die Schaltfläche **Save** von PrestaShop. |
| **Individual field checkboxes — International → Translations** | Yes | Kontrollkästchen und Leiste auf **International → Translations**. **No** blendet sie aus. Die Shop-Formulare sind nicht betroffen. |

![Einstellungen, englisches Backoffice. Unterer Teil des Formulars: Grenzwerte, E-Mail, die Cron-Adresse, Test connection und Save.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings-limits.webp)

**Grenzwerte**

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Batch size** | 25 | Wie viele Zeichenketten in einen API-Aufruf gehen. Für den ersten Lauf nehmen Sie einen Wert zwischen 10 und 25. Der Wert bleibt zwischen 1 und 100. Eine größere Charge schließt einen Auftrag mit weniger Aufrufen ab. Schlägt ein Aufruf fehl, wird beim Wiederholen ein größeres Stück verarbeitet. |
| **Dry-run sample** | 10 | Wie viele Beispielzeichenketten **Estimate** vor einem Massenauftrag zeigt. Der Wert bleibt zwischen 1 und 50. **Estimate** schreibt keine Übersetzungen. |
| **Max tokens (0 = default)** | 0 | Eine Obergrenze für die Länge einer Antwort. Bei 0 werden 4096 Tokens als Grenze gesendet. Setzen Sie eine Zahl, wenn Antworten abgeschnitten werden oder kürzer sein sollen. Nur der nächste Aufruf nutzt die Grenze. Bereits gespeicherte Übersetzungen werden nicht gekürzt. |
| **Budget USD / month** | 0 | Eine monatliche Obergrenze in US-Dollar, berechnet aus dem Nutzungsprotokoll. 0 bedeutet keine Obergrenze. Erreicht das Protokoll den Betrag, werden neue Übersetzungen angehalten. Bereits gespeicherte Arbeit bleibt erhalten. |
| **Rate limit / min** | 60 | Wie viele API-Aufrufe dieser Shop in einer Minute starten darf. 0 schaltet diese lokale Grenze ab. Aufrufe über dem Limit werden übersprungen und auf **History** aufgeführt. Claude kann zusätzlich eine eigene Grenze anwenden. |
| **Log retention days** | 30 | Wie viele Tage an Zeilen auf **History** bleiben. Mindestens 1. Ältere Zeilen werden entfernt. Aufträge, das Glossar und gespeicherte Übersetzungen löscht diese Zahl nicht. |
| **Temperature** | 0.2 | Wie frei das Modell umformulieren darf. Bei etwa 0.2 bleibt es nah an der Quelle. Werte nahe 1 verändern die Sätze stärker. Der gespeicherte Wert bleibt zwischen 0 und 1. Platzhalter und HTML werden danach trotzdem geprüft. Die eingebauten Modelle erhalten diesen Wert. Eine von Ihnen hinzugefügte Modell-ID, die kein Claude Haiku, Sonnet oder Opus 4.0, 4.1, 4.5 oder 4.6 ist, erhält ihn nicht. Bei diesem Modell hat das Feld also keine Wirkung. |
| **Allow publish / save** | Yes | Ob dieses Modul Übersetzungen in PrestaShop schreiben darf. **No** blockiert das Speichern auf **Manual**, bei Massenaufträgen und auf **Catalog**. Die Symbole auf der Übersetzungsseite und in den Shop-Formularen füllen weiterhin nur das Formular. Die Schaltfläche **Save** von PrestaShop ist davon unabhängig. |

Nach **Save** erscheint eine der folgenden Meldungen:

- **Settings saved. No translation was started.** Die Einstellungen sind gespeichert. Es wurde nichts übersetzt.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Fügen Sie einen Schlüssel in **Claude API key** ein und klicken Sie erneut auf **Save**.

**E-Mail und Cron**

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Email notify on complete** | No | Sendet eine E-Mail, wenn ein Massenauftrag endet. Der Auftrag läuft in jedem Fall. Nur die E-Mail wird hinzugefügt oder entfällt. |
| **Notify email** | leer | Die Adresse, die diese E-Mail erhält. Das Feld wird nur genutzt, wenn der Schalter darüber eingeschaltet ist. Allein das Speichern der Adresse verschickt keine Nachricht. |
| **CRON URL** | eine Adresse mit Token | Eine geheime Adresse, die der Server aufrufen kann, um einen Abschnitt eines wartenden Auftrags zu verarbeiten. Kopieren Sie sie in den Aufgabenplaner des Servers. Veröffentlichen Sie sie nicht. Wer die Adresse kennt, kann einen Abschnitt starten. Das Öffnen von **Settings** startet keinen Auftrag. |

**Test connection** prüft Schlüssel und Modell mit einer kurzen Anfrage. Es wird nichts übersetzt und nichts gespeichert.

- **Connection OK (N ms). No translation was started.** Die Verbindung funktioniert.
- **Connection was not made. Nothing was translated.** gefolgt vom Grund. Prüfen Sie Schlüssel und Modell. Die Details stehen auf **History**.

Zum Einstieg: Fügen Sie den Schlüssel ein, wählen Sie Modell und Quell-Locale, klicken Sie auf **Test connection** und danach auf **Save**. Lassen Sie die Zahlen auf ihren Installationswerten, bis ein Auftrag Probleme macht.

### 3.2. Dashboard

Öffnen Sie die Registerkarte **Dashboard**. Sie zählt die fehlenden Zeichenketten im Katalog und zeigt danach die Claude-Nutzung als Karten, Diagramme und die zehn neuesten Prompts. Die Seite übersetzt nichts und ändert keine Zeichenketten.

![Dashboard, englisches Backoffice. Abdeckung für eine Locale, die Cron-Zeile und die Verlaufsfilter.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-dashboard.webp)

**Abdeckung**

- **Locale:** die Shop-Locale, für die die fehlenden Zeichenketten gezählt werden.
- **Show:** zeichnet die Tabelle für diese Locale neu.
- Spalten: **Section**, **Total**, **Missing**, **Done** und ein Fortschrittsbalken. Die Bereiche sind **Back office**, **Themes**, **Installed modules**, **Emails** und **Others**. **Missing** ist die Anzahl der Zeichenketten ohne Übersetzung in dieser Locale.
- Unter der Tabelle zeigt **CRON** dieselbe Adresse wie **CRON URL** in **Settings**.
- Eine leere Tabelle heißt, dass der Shop für diese Locale noch keinen Katalog hat. Legen Sie ihn unter **International → Translations** an.

Nach **Show** lautet die Meldung **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Nutzung**

- Zeiträume: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filter: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** und **Prompt or reply contains**. Klicken Sie auf **Filter**.
- Karten: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** und **Estimated cost**. Die geschätzten Kosten sind eine lokale Berechnung, keine Rechnung von Anthropic.
- Diagramme: **Requests and errors**, **Tokens sent and received**, **Requests by model**. Darunter stehen die Gruppen **By day**, **By model**, **By type**, **By language** und **By employee** mit den Spalten **Group**, **Calls**, **Sent**, **Received** und **Total**. Eine leere Gruppe zeigt **No requests in this range.**
- **Latest prompts** listet zehn Aufrufe. **View** öffnet den Prompt und die Antwort. **See all** öffnet **History** (3.10). Eine leere Liste zeigt **No requests yet.**

Filtern löscht den Verlauf nicht und ändert keine Übersetzungen.

Fehlt in einem Bereich der größte Teil, öffnen Sie **Manual** für einige Zeichenketten oder **Bulk** für eine ganze Domain.

### 3.3. Manual

Öffnen Sie **Manual**. Die Seite übersetzt eine Domain oder ein klassisches Modul, einige Dutzend Zeichenketten auf einmal. Das reine Filtern speichert nichts.

![Manual, englisches Backoffice. Section, Source, Target, Domain, Only empty und Search.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-manual.webp)

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Section** | Back office | Welcher Katalog gelesen wird: **Back office**, **Themes**, **Installed modules**, **Emails** oder **Others**. Ein Wechsel des Bereichs lädt die Seite neu und zeigt nur die Felder dieses Bereichs. Claude wird dabei nicht aufgerufen. |
| **Theme** | leer | Nur bei **Themes** sichtbar. Beschränkt die Liste auf ein Theme. |
| **Module** | leer | Nur bei **Installed modules** sichtbar. Beschränkt die Liste auf ein Modul. Ein klassisches Modul ohne Domain lädt jede Zeichenkette dieses Moduls. |
| **Domain** | leer | Dieselbe Gruppierung wie auf **International → Translations**. Wählen Sie sie und klicken Sie auf **Filter**. Ausgeblendet bei einem klassischen Modul und bei einem Bereich ohne Domains. |
| **Source** | die **Source locale** aus **Settings** oder en-US | Die Sprache, aus der die Zeichenketten gelesen werden. Wählen Sie eine Sprache, die bereits einen guten Text hat. |
| **Target** | die erste Sprache der Liste | Die Sprache, die Sie füllen möchten. Sie muss unter **International → Localization → Languages** existieren. |
| **Only empty** | Yes | Zeigt nur Zeichenketten ohne Übersetzung. Ausgeschaltet zeigt es jede Zeichenkette. Gespeicherte Übersetzungen werden nicht gelöscht. |
| **Search** | leer | Behält nur Quellzeichenketten, die das eingegebene Wort enthalten. |

Schritte:

1. Setzen Sie **Section**, **Source** und **Target**.
2. Bei **Themes** wählen Sie ein **Theme**. Bei **Installed modules** wählen Sie ein **Module**.
3. Klicken Sie auf **Filter**. Die Liste **Domain** wird aktualisiert. Wählen Sie eine Domain und klicken Sie noch einmal auf **Filter**. Bei einem klassischen Modul lassen Sie die Domain weg: **Filter** lädt jede Zeichenkette des Moduls.
4. Kreuzen Sie die gewünschten Zeilen an. **Check all** und **Uncheck all** wählen die Liste aus oder heben die Auswahl auf.
5. Klicken Sie auf **Translate selected (review)**. Es öffnet sich die Tabelle **Review before save** mit **Source**, **AI proposal** und **Warnings**. Entfernen Sie das Häkchen bei Zeilen, die Sie nicht übernehmen wollen. Bearbeiten Sie einen Vorschlag direkt im Feld. Klicken Sie auf **Save approved**.
6. Oder setzen Sie vor dem Übersetzen das Häkchen bei **Save now (skip review)**. Gültige Zeilen werden dann sofort geschrieben, ohne die Prüftabelle.

Die Spalten der Zeichenkettenliste sind **Source**, **Current** und **Status** (**empty** oder **filled**).

Meldungen:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Das ist die Liste eines klassischen Moduls.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Claude.**
- **No strings match this filter. Nothing was sent to Claude.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Claude.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Diese Zeilen wurden übersprungen. Korrigieren Sie Platzhalter und Tags, bis sie zur Quelle passen, und speichern Sie erneut.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Beim Wechsel des Bereichs erscheint außerdem eine kurze Zeile wie **Section is Back office. Theme and module are not used.**, zusammen mit **Nothing was sent to Claude.** Dasselbe Muster gilt für **Themes**, **Installed modules**, **Emails** und **Others**.

### 3.4. Bulk

Öffnen Sie **Bulk**. Die Seite legt einen Auftrag für viele Domains und Sprachen an. **Estimate** speichert nichts. **Start job** erzeugt eine Zeile auf **Jobs**. Im Shop wird erst geschrieben, wenn der Auftrag verarbeitet wird und **Allow publish / save** auf **Yes** steht.

![Bulk, englisches Backoffice. Section, Source, Targets, Domains, Policy und Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-bulk.webp)

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Section** | Back office | Welchen Katalog der Auftrag liest. Dieselben Auswahlmöglichkeiten wie auf **Manual**. |
| **Theme** / **Module** | leer | Nur beim passenden Bereich sichtbar, wie auf **Manual**. |
| **Source** | die **Source locale** aus **Settings** oder en-US | Die Sprache, die als Original gilt. Jede Zielsprache wird aus dieser Sprache übersetzt. |
| **Targets** | keine | Eine oder mehrere Sprachen, die gefüllt werden sollen. Halten Sie Strg gedrückt (auf dem Mac Cmd), um mehrere auszuwählen. Ein einfacher Klick ersetzt die Auswahl. |
| **Domains** | keine | Die Domains, die im Auftrag enthalten sind. Halten Sie Strg oder Cmd gedrückt. Wählen Sie keine aus, umfasst der Auftrag alle Domains des gewählten Bereichs. |
| **Policy** | Fill empty | **Fill empty** sendet nur Zeichenketten ohne Übersetzung. **Overwrite all** sendet jede Zeichenkette, auch solche mit vorhandener Übersetzung, und kann sie ersetzen. **Outdated if equals source** sendet nur Zeichenketten, deren Übersetzung identisch mit der Quelle ist. |
| **Dry-run job** | No | Claude arbeitet trotzdem, und der Auftrag erscheint auf **Jobs**. Die Antworten werden aber nicht in den Shop geschrieben. |

Schritte:

1. Wählen Sie Bereich, Quelle, Zielsprachen, Domains und Richtlinie.
2. Klicken Sie auf **Estimate**. Die Seite zeigt **Estimate**, die Anzahl der Zeichenketten, eine Schätzung der Tokens, eine Kostenschätzung und ein **Sample**.
3. Wenn die Schätzung passt, klicken Sie auf **Start job**. **Jobs** öffnet sich mit dem neuen Auftrag.
4. Arbeiten Sie ihn auf **Jobs** ab (3.5) oder überlassen Sie ihn der Cron-Adresse.

Meldungen:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Claude and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Claude API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Öffnen Sie **Jobs**. Jede Zeile ist ein Lauf aus **Bulk**.

![Jobs, englisches Backoffice. Die Auftragsliste. In diesem Shop gibt es noch keine Aufträge.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-jobs.webp)

Spalten: **#**, **Status**, **Locales** (Quelle, danach die Zielsprachen), **Progress** (erledigt/gesamt), **Cost**, **Employee**, **Date** und **Open**. Eine leere Liste zeigt **No jobs yet.**

Status der Aufträge, wie sie auf dem Bildschirm erscheinen:

- `pending` - wartet. Er startet nicht von selbst.
- `running` - läuft gerade.
- `paused` - angehalten, bis Sie ihn fortsetzen.
- `cancelled` - beendet. Zeichenketten, die noch warteten, wurden nicht übersetzt.
- `completed` - jede Zeichenkette verarbeitet, ohne Fehler.
- `completed_with_errors` - abgeschlossen, aber einige Zeichenketten sind fehlgeschlagen.
- `failed` - der Auftrag wurde mit einem Fehler beendet.

**Die Auftragsseite**

**Open** zeigt **Job #N**, den Status, den Fortschritt (erledigt/gesamt), **failed**, **skipped**, die Kosten, die Mitarbeiternummer und die Markierung **dry-run**, wenn der Auftrag ein Testlauf ist. Solange der Auftrag geöffnet ist, aktualisiert sich der Fortschrittsbalken selbst. Die Tabelle darunter hat die Spalten **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** und **Error**.

Zeilenstatus: `pending`, `processing`, `done`, `failed`, `skipped` (ein Ausschluss hat gegriffen oder die Zeichenkette war schon übersetzt) und `rolled_back`.

Schaltflächen:

- **Process slice** - verarbeitet einen Abschnitt in der Größe von **Batch size** und hält dann an. Meldung: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Ist nichts mehr übrig: **The job has no more strings waiting.**
- **Auto-process** - wiederholt Abschnitte, bis der Auftrag endet oder ein Fehler ihn stoppt. Das läuft im Browser, daher muss der Tab geöffnet bleiben. Wird der Tab geschlossen, stoppt die Schleife. Der Auftrag bleibt bestehen und lässt sich mit **Process slice** oder über die Cron-Adresse abschließen.
- **Pause** - Meldung: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - Meldung: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - fehlgeschlagene Zeichenketten gehen zurück ins Warten, und der Auftrag wartet erneut. Meldung: **Retried N failed items.**
- **Rollback** - fragt **Roll back this job?** und stellt die vorherige Übersetzung wieder her, wo das Modul vor der Änderung eine Kopie gespeichert hat. Meldung: **Rollback: restored N translations.**
- **Error CSV** - lädt die fehlerhaften Zeilen herunter. Spalten: id, domain, locale, source, error.
- **Failed only** - zeigt nur die fehlerhaften Zeilen.
- **Review queue** - öffnet **Review** (3.6).

Auf der Auftragsseite gibt es keine Schaltfläche Cancel. Um die weitere Arbeit anzuhalten, verwenden Sie **Pause**.

**Automatische Pause**

Lehnt Claude Aufrufe wegen eines Ratenlimits ab, pausiert der Auftrag von selbst. Die Fehlerzeile lautet **Rate limit — job auto-paused. Resume later.** Warten Sie und klicken Sie danach auf **Resume**. Über **Rate limit / min** in **Settings** verringern Sie, wie viele Aufrufe der Shop pro Minute startet.

Weitere Meldungen auf dieser Seite:

- **Nothing was translated.**, gefolgt von **No Claude API key. Nothing was translated.** Fügen Sie den Schlüssel in **Settings** ein.
- **Allow publish is off in Settings.** Ein Auftrag, der kein Testlauf ist, läuft erst, wenn Sie **Allow publish / save** einschalten.
- **Monthly API budget has been exhausted.** Erhöhen Sie **Budget USD / month** oder setzen Sie den Wert auf 0.

### 3.6. Review

Öffnen Sie **Review** oder klicken Sie bei einem Auftrag auf **Review queue**. Die Überschrift der Seite lautet **Needs-review queue (quality score / flags).** Sie listet die neuesten Zeilen auf, die die Qualitätsprüfung nicht automatisch bestanden haben, bis zu 100.

![Review, englisches Backoffice. Die Prüfliste ist leer.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-review.webp)

Spalten: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, danach **Approve** und **Reject**. Eine leere Liste zeigt **The queue is empty.**

So lesen Sie eine Zeile:

- **Score** liegt zwischen 0 und 100. Unter 70 landet die Zeile in der Liste.
- **Flags:**
  - `validation_failed` - Platzhalter oder HTML haben die Prüfung nicht bestanden.
  - `warning` - ein kleinerer Hinweis aus der Prüfung.
  - `length_explosion` - die Übersetzung ist mehr als zweieinhalbmal so lang wie die Quelle.
  - `too_short` - die Übersetzung ist deutlich kürzer als eine lange Quelle.
  - `possible_untranslated` - englische Wörter wie *the*, *and*, *with*, *your* oder *please* stehen noch in der Übersetzung.
- **Source** ist das Original. **AI** ist der Vorschlag des Modells.

**Approve** und **Reject** ändern nur den Status der Zeile. Die Meldung lautet **Review updated.** Die Zeile verschwindet aus der Liste. Diese Aktion schreibt den Text nicht in den Shop und ändert den Rest der Domain nicht.

Durfte der Auftrag speichern, steht der Vorschlag möglicherweise schon im Shop. Um Änderungen dieses Auftrags rückgängig zu machen, nutzen Sie **Rollback** beim Auftrag auf **Jobs**.

### 3.7. Catalog

Öffnen Sie **Catalog**. Die Seite übersetzt Produkt-, Kategorie- oder CMS-Felder, die in den Sprachen des Shops gespeichert sind. **International → Translations** wird dabei nicht bearbeitet. Ein Klick verarbeitet höchstens 100 Datensätze. Gespeicherte Zeilen werden in der Zielsprache geschrieben.

![Catalog, englisches Backoffice. Entity, Fields, Sprachen, Only empty und Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-catalog.webp)

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Entity** | product | Was gelesen wird: **product**, **category** oder **cms**. Ein Wechsel lädt die Seite neu und zeigt nur die Feldliste dieser Entität. Der Wechsel selbst übersetzt nichts. |
| **Fields** | alle Felder dieser Entität | Welche Texte die Charge sendet. Halten Sie Strg oder Cmd gedrückt. Nicht gewählte Felder werden nicht gesendet und bleiben, wie sie sind. Produkt: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Kategorie: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. Bei einem Produkt oder einer Kategorie ist **Title** der Name. Bei CMS ist **Title** der Seitentitel und **Content** der Seiteninhalt. Lassen Sie **Friendly URL** ungewählt, wenn die Links unverändert bleiben sollen. |
| **Source language** | die erste Shop-Sprache | Die Sprache, aus der die Felder kopiert werden. Diese Sprache wird nicht verändert. |
| **Target language** | die erste Shop-Sprache | Die Sprache, die die Übersetzung erhält. Sie muss sich von der Quelle unterscheiden. |
| **Only empty** | Yes | Überspringt Felder, die in der Zielsprache schon Text haben. Schalten Sie es nur aus, wenn Sie vorhandenen Text ersetzen wollen. Eingeschaltet bleibt vorhandener Zieltext erhalten. Ausgeschaltet darf die Charge ihn überschreiben, sofern das Speichern erlaubt ist. |
| **Start after ID** | 0 | Überspringt Datensätze bis zu dieser ID. 0 beginnt beim ersten Datensatz. Nach einer Charge wird das Feld auf die höchste ID dieser Charge gesetzt, fehlgeschlagene Zeilen eingeschlossen. Klicken Sie erneut auf die Schaltfläche, um weiterzumachen. Um eine fehlgeschlagene Zeile zu wiederholen, setzen Sie die ID vor dem nächsten Klick wieder unter diesen Datensatz. |

Schaltfläche: **Translate batch (max 100)**.

Schritte:

1. Wählen Sie **Entity** und kreuzen Sie die Felder an.
2. Wählen Sie **Source language** und **Target language**.
3. Lassen Sie **Only empty** eingeschaltet.
4. Klicken Sie auf **Translate batch (max 100)**. Die Meldung lautet **Catalog finished: saved N, failed M.** Die Seite zeigt außerdem die Zähler **Saved** und **failed**.
5. Öffnen Sie einen Datensatz in der Zielsprache und prüfen Sie das Ergebnis, bevor Sie **Only empty** ausschalten oder die nächste Charge starten.

Meldungen:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- Ein Wechsel von **Entity** zeigt **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Öffnen Sie **Glossary**. Das Glossar ist eine Liste von Wörtern und Wendungen, die das Modell unverändert lassen oder immer gleich übersetzen soll. Eine neue Zeile ändert bereits gespeicherte Übersetzungen nicht. Die nächste Übersetzung liest diese Liste.

![Glossary, englisches Backoffice. Begriff hinzufügen und CSV-Import.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-glossary.webp)

**Ein Begriff**

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Source term** | leer, Pflicht | Das Wort oder die Wendung in der Ausgangssprache. Schreiben Sie es genau so, wie es im Text vorkommt, mit Großbuchstaben, wo sie eine Rolle spielen. |
| **Target locale** | leer | Begrenzt die Zeile auf eine Locale, zum Beispiel pl-PL. Leer heißt: Die Zeile gilt für jede Zielsprache. Eine ausgefüllte Locale wird bei anderen Sprachen ignoriert. |
| **Target term** | leer | Die freigegebene Übersetzung. Das Feld darf nur leer sein, wenn **Do not translate** eingeschaltet ist. |
| **Do not translate** | No | Eingeschaltet: Das Modell übernimmt den Begriff unverändert, etwa einen Markennamen, eine SKU oder ein Tag. Ausgeschaltet: Es verwendet **Target term**. |

Klicken Sie auf **Add**. Meldungen: **Glossary term added. Translations already stored were not changed.** oder **Nothing was added. Type a source term.**

**Die Tabelle**

Spalten: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** oder **No**) und **Delete**. **Delete** entfernt nur diese Zeile. Meldung: **Glossary term deleted.** Eine leere Liste zeigt **No glossary terms yet.**

**CSV**

- Wählen Sie **CSV file** und klicken Sie auf **Import CSV**. Meldung: **Imported N rows.** Fehlt die Datei: **CSV file is missing.** Lässt sie sich nicht lesen: **Cannot open the CSV file.**
- Die erste Zeile ist eine Kopfzeile: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Diese Zeile wird immer übersprungen. Zeilen mit weniger als drei Spalten werden ebenfalls übersprungen. In der vierten Spalte bedeutet ein leerer Wert oder 0 **No**. Jeder andere Wert bedeutet **Yes**.
- Der Import übernimmt die Zeilen aus der Datei. Er prüft nicht, ob ein Begriff schon vorhanden ist. Wird dieselbe Datei zweimal importiert, entstehen Duplikate.
- **Export CSV** lädt die aktuelle Liste als `glossary.csv` herunter. Es wird keine Eingabedatei gebraucht, und die Liste bleibt unverändert.

Verwenden Sie kurze, genaue Begriffe. Ein sehr allgemeiner Begriff wird bei jedem Vorkommen erzwungen.

### 3.9. Excludes

Öffnen Sie **Excludes**. Ein Ausschluss ist ein Muster für Quelltext, den das Modul nicht an Claude sendet. Der Text bleibt im Shop unverändert. Das Muster gilt auf **Manual**, **Bulk**, **Catalog** und den Übersetzungsseiten.

![Excludes, englisches Backoffice. Pattern, Type und die leere Liste.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-excludes.webp)

| Feld | Bei der Installation | Was es bewirkt |
|---|---|---|
| **Pattern** | leer, Pflicht | Der Text, der mit jeder Quellzeichenkette verglichen wird. Die Art des Vergleichs hängt von **Type** ab. |
| **Type** | exact | **exact** trifft die ganze Zeichenkette. **prefix** trifft den Anfang. **contains** trifft einen Ausschnitt an beliebiger Stelle. **regex** ist ein PHP-Regulärausdruck und wird genau so angewendet, wie Sie ihn eingeben. Ein fehlerhafter Ausdruck trifft nichts. Beginnen Sie mit einem kurzen Muster und prüfen Sie, was übersprungen wird. Ein falscher Typ kann zu viel oder gar nichts überspringen. |

Klicken Sie auf **Add**. Meldung: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Ein leeres Muster ergibt **Nothing was added. Type a pattern.**

Spalten: **Pattern**, **Type**, **On** und **Delete**. **On** zeigt 1, wenn das Muster aktiv ist. Auf dieser Seite gibt es keinen Schalter, um ein Muster abzuschalten. Wollen Sie es nicht mehr nutzen, klicken Sie auf **Delete** und legen Sie es bei Bedarf neu an. **Delete** entfernt nur dieses Muster und löscht keine bestehenden Übersetzungen. Meldung: **Pattern deleted.** Eine leere Liste zeigt **No patterns yet.**

Nutzen Sie Ausschlüsse für Text, der in der Ausgangssprache bleiben muss, etwa einen Firmennamen oder ein technisches Token. Für einen Begriff, der immer gleich übersetzt werden soll, verwenden Sie das **Glossary**.

### 3.10. History

Öffnen Sie **History** oder klicken Sie auf **See all** im **Dashboard**.

![History, englisches Backoffice. Die Aufrufliste und Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-history.webp)

**History** ist die vollständige Liste der gespeicherten Claude-Aufrufe: manuelle Läufe, die Übersetzungsseite, Massenaufträge, Katalogchargen und der Verbindungstest. Jede Zeile enthält Prompt, Antwort, Modell, Sprachen, Tokenzahlen und die Dauer des Aufrufs. Karten und Diagramme finden Sie auf **Dashboard**. Das Öffnen dieser Seite sendet keine neue Anfrage und ändert keine Übersetzungen.

Filter und Diagramme bleiben auf **Dashboard**. Diese Seite ist nur die Liste.

Spalten: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** und **Prompt**. Typen: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** und **Not sent** (der Aufruf wurde nicht gesendet, etwa wegen des lokalen Limits oder des Budgets). Eine Zeile **Bulk job** zeigt die Auftragsnummer.

- **View** öffnet Prompt und Antwort mit **HTTP**, **Sent**, **Received** und **Total**. Bei einem Fehler ist die Antwort der Fehlertext. **Back to the list** führt zurück zur Tabelle. Existiert die Zeile nicht mehr: **This history row no longer exists.**
- Ein Zugriffsfehler bedeutet, dass der Schlüssel auf **Settings** falsch ist oder das Konto das gewählte Modell nicht nutzen darf.
- **Previous**, **Next** und **Page** blättern durch die Liste.
- **Clear history** fragt **Clear the stored history? Saved translations stay.** Danach erscheint **History cleared. Saved translations were not changed.** Die Hilfe der Schaltfläche sagt **Clear history deletes these rows only. Saved translations stay.**

Eine leere Liste zeigt **No requests yet.**

Brechen die Übersetzungen plötzlich ab, öffnen Sie hier zuerst die neueste Fehlerzeile, bevor Sie das Glossar ändern.

### 3.11. Updates

Öffnen Sie **Updates** am rechten Ende der Modulleiste. Der Formulartitel lautet **MyPresta Updates**.

![Updates, englisches Backoffice. Manual Check, Automatic Notifications und Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-updates.webp)

- **Manual Check** enthält **Check Now**. Damit prüfen Sie die Version sofort.
- **Automatic Notifications** steht auf **Enabled** oder **Disabled**. **Enabled** gilt, solange Sie nie eine Auswahl gespeichert haben. Ist die Prüfung eingeschaltet, sieht das Modul nach, ob MyPresta eine neuere Version hat, und kann im Backoffice einen Hinweis anzeigen.
- **Product Page** ist ein Link zur Kontaktseite, die dieses Modul verwendet.
- **Save** speichert die Auswahl. Meldung: **Update settings saved.**

Nach **Check Now**: **New version available!** oder **Module is up to date!**

### 3.12. Schaltflächen auf International → Translations

Öffnen Sie **International → Translations**. Die Feldschaltflächen erscheinen, wenn **Individual field buttons — International → Translations** eingeschaltet ist. Kontrollkästchen und Leiste erscheinen, wenn **Individual field checkboxes — International → Translations** eingeschaltet ist.

Das sehen Sie:

- Eine Schaltfläche **Translate** an jedem Textfeld.
- Ein Kontrollkästchen an jedem Feld, wenn die Kontrollkästchen eingeschaltet sind.
- Eine Leiste mit der Beschriftung **Claude translations** und den Elementen **Source** (en-US oder die **Source locale** aus **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** sowie dem Hinweis **Fills the fields. Save with the PrestaShop button.** Mit **Translate empty in this section** werden die leeren Felder des aktuellen Bereichs gefüllt.

Schritte:

1. Wählen Sie **Target**.
2. Kreuzen Sie Felder an oder klicken Sie auf **Check empty**.
3. Klicken Sie auf **Translate selected** oder **Translate empty**.
4. Warten Sie, bis die Leiste **Done** anzeigt. Während der Arbeit steht dort **Translating…** mit einem Zähler. Haben Sie nichts angekreuzt, meldet die Leiste **Tick at least one field.**
5. Prüfen Sie die gefüllten Felder und speichern Sie die Seite mit der Schaltfläche **Save** von PrestaShop.

Die Schaltflächen füllen nur die Felder. Ohne die Schaltfläche **Save** von PrestaShop gelangt der Text nicht in den Shop. Ist **Allow publish / save** ausgeschaltet, werden die Felder trotzdem gefüllt, und die Schaltfläche **Save** von PrestaShop speichert die Seite.

Meldungen:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Bei **Emails** stammt der Quelltext aus der Mailvorlage und nicht aus einem Feld der Seite. Wählen Sie eine andere **Source locale**, für die diese Mail-Dateien vorliegen.

### 3.13. Schaltflächen auf Formularen von Produkt, Kategorie und CMS

Öffnen Sie ein Produkt, eine Kategorie, eine CMS-Seite oder ein anderes Shop-Formular mit mehrsprachigen Feldern. Die Schaltflächen erscheinen, wenn **Individual field buttons — shop forms** eingeschaltet ist. Kontrollkästchen und Leiste erscheinen, wenn **Individual field checkboxes — shop forms** eingeschaltet ist.

Das sehen Sie:

- Eine Schaltfläche **Translate** an jedem mehrsprachigen Feld.
- Ein Kontrollkästchen für die Leiste.
- Eine Leiste mit der Beschriftung **Claude translations** und den Elementen **Translate from** und **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** sowie dem Hinweis **Fills the fields. Save with the PrestaShop button.**

Schritte:

1. Füllen Sie das Feld in der Ausgangssprache aus. Ist es leer, zeigt die Leiste **Fill the source language field first.**
2. Wählen Sie auf der Leiste die Zielsprache.
3. Klicken Sie auf die Schaltfläche eines Feldes oder kreuzen Sie mehrere Felder an und klicken Sie auf **Translate selected**. **Translate empty** füllt die leeren Felder.
4. Klicken Sie im PrestaShop-Formular auf **Save**. Ohne diesen Schritt wird der Text nicht gespeichert.

Die Schaltfläche füllt nur das Feld im Formular. Nicht angekreuzte Felder bleiben unverändert.

## 4. Shopansicht

Das Modul ergänzt nichts auf der Seite, die Kunden sehen. Es gibt keinen Block, keine Schaltfläche und keine Meldung im Shop, daher hat das Theme für dieses Modul nichts anzuzeigen.

Die einzige Adresse außerhalb des Backoffice ist die Cron-Adresse. Sie ist für eine geplante Aufgabe auf dem Server gedacht und nicht für Kunden.

- Kopieren Sie sie aus **Settings**, Feld **CRON URL**, oder aus der Zeile **CRON** auf **Dashboard**.
- Tragen Sie sie im Aufgabenplaner des Servers ein, zum Beispiel alle paar Minuten. Jeder Aufruf verarbeitet einen Abschnitt eines wartenden Auftrags.
- Ist SSL im Shop aktiv, verwenden Sie die Adresse mit `https://`.

| Was Sie sehen, wenn Sie die Adresse öffnen | Was Sie tun sollten |
|---|---|
| **Forbidden** | Die Adresse ist unvollständig oder wurde geändert. Kopieren Sie sie erneut aus **Settings**. |
| **No pending jobs** | Es gibt keinen Auftrag in `pending` oder `running`. Legen Sie auf **Bulk** einen an oder setzen Sie einen pausierten Auftrag auf **Jobs** fort. |
| Ein JSON-Ergebnis mit `ok`, `finished` und `counts` | Ein Abschnitt wurde verarbeitet. Prüfen Sie den Fortschritt auf **Jobs**. |

Die Cron-Adresse verarbeitet nur Aufträge in `pending` und `running`. Ein Auftrag in `paused` muss auf **Jobs** fortgesetzt werden.

## 5. Probleme

| Was Sie sehen | Ursache | Was Sie tun sollten |
|---|---|---|
| **No Claude API key.** auf jeder Modulseite | Es ist kein Schlüssel gespeichert. | Öffnen Sie **Settings**, fügen Sie den Schlüssel in **Claude API key** ein und klicken Sie auf **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Die Einstellungen wurden ohne Schlüssel gespeichert. | Fügen Sie den Schlüssel ein und klicken Sie auf **Save**. |
| **Connection was not made. Nothing was translated.** nach **Test connection** | Falscher Schlüssel, keine Verbindung zu Anthropic oder ein Modell, das das Konto nicht nutzen darf. | Prüfen Sie den Schlüssel, wählen Sie ein anderes **Model** oder fügen Sie die richtige ID unter **Add a Claude model** hinzu. Lesen Sie die Zeile auf **History**. |
| Zugriffsfehler auf **History** | Der Schlüssel ist falsch, oder das Konto darf das gewählte Modell nicht nutzen. | Korrigieren Sie den Schlüssel oder wählen Sie ein Modell, das das Konto aufrufen darf. |
| **Nothing was started. There is no Claude API key.** auf **Bulk** | Kein Schlüssel. | Fügen Sie den Schlüssel auf **Settings** ein und führen Sie danach **Estimate** und **Start job** erneut aus. |
| Ein Auftrag bleibt auf `pending` | Ein Auftrag startet nicht von selbst. | Klicken Sie auf **Jobs** auf **Process slice** oder **Auto-process**, oder richten Sie die Cron-Adresse ein (Abschnitt 4). |
| Ein Auftrag ist `paused` mit **Rate limit — job auto-paused. Resume later.** | Claude hat Aufrufe wegen eines Ratenlimits abgelehnt. | Warten Sie einige Minuten und klicken Sie auf **Resume**. Senken Sie **Batch size** oder **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Der Betrag aus **Budget USD / month** ist erreicht. | Erhöhen Sie den Betrag oder setzen Sie 0. Ein neuer Monat beginnt bei null. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** ist ausgeschaltet. | Schalten Sie **Allow publish / save** ein. |
| **Not saved because of broken placeholders or HTML: N.** auf **Manual** | Die Übersetzung hat Platzhalter oder HTML-Tags verändert. | Bearbeiten Sie die Zeile in **Review before save**, bis Platzhalter und Tags zur Quelle passen, und klicken Sie auf **Save approved**. |
| Ein Auftrag endet als `completed_with_errors` | Einige Zeichenketten sind fehlgeschlagen. | Öffnen Sie den Auftrag, klicken Sie auf **Failed only**, laden Sie **Error CSV** herunter und klicken Sie danach auf **Retry failed**. |
| Zeilen auf **Review** haben einen niedrigen **Score** | Die Qualitätsprüfung hat sie in die Warteschlange gestellt. | Lesen Sie **Source** und **AI**. Klicken Sie auf **Approve** oder **Reject**. Wurde ein schlechter Text bereits gespeichert, nutzen Sie **Rollback** am Auftrag. |
| Die Übersetzung wurde gespeichert, die Shopansicht zeigt aber noch den alten Text | Der Cache dieser Seite wurde nicht erneuert. Das Modul leert den Cache beim Speichern einer Katalogübersetzung, eines Abschnitts eines Massenauftrags und bei einem Rollback. | Leeren Sie den Cache im PrestaShop-Backoffice. |
| Ein Ausschluss überspringt die Zeichenkette nicht | Falscher **Type** oder ein **regex**, der nichts trifft. | Löschen Sie das Muster auf **Excludes** und fügen Sie ein kürzeres mit dem richtigen **Type** hinzu. |
| Ein neuer Glossarbegriff ändert gespeicherte Übersetzungen nicht | Das Glossar wird beim nächsten Übersetzen gelesen. Gespeicherte Texte bleiben unverändert. | Übersetzen Sie diese Zeichenketten auf **Bulk** mit **Overwrite all** neu, nachdem Sie **Estimate** geprüft haben. |
| **The source language mail file was not found.** | Die gewählte Quelle hat keine Mail-Datei. | Wählen Sie auf **Settings** eine andere **Source locale** oder auf der Übersetzungsseite eine andere **Source**, zu der die Mail-Dateien vorliegen. |
| **No strings match this filter. Nothing was sent to Claude.** | Der Filter trifft nichts. | Schalten Sie **Only empty** aus, leeren Sie **Search** oder wählen Sie eine andere Domain. |
| **Nothing was translated. Tick at least one row.** | Keine Zeile war angekreuzt. | Kreuzen Sie Zeilen an und klicken Sie auf **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** auf **Catalog** | Quelle und Ziel sind dieselbe Sprache. | Wählen Sie eine andere **Target language**. |
| **Catalog finished** hat **Start after ID** hinter fehlgeschlagene Zeilen gesetzt | Das Feld erhält die höchste ID der Charge, fehlgeschlagene Zeilen eingeschlossen. | Setzen Sie **Start after ID** unter den fehlgeschlagenen Datensatz und starten Sie die Charge erneut. |
| Die Abdeckung auf **Dashboard** ist leer | Der Shop hat für diese Locale noch keinen Katalog. | Legen Sie ihn unter **International → Translations** an und kehren Sie dann zu **Dashboard** zurück. |
| **History** zeigt **Not sent** | Das lokale Limit oder das Budget hat den Aufruf gestoppt, bevor er gesendet wurde. | Prüfen Sie **Rate limit / min** und **Budget USD / month** auf **Settings**. |
| **The shop needs at least two languages.** | Der Shop hat nur eine Sprache. | Fügen Sie eine Sprache unter **International → Localization → Languages** hinzu. |

## 6. Für Entwickler

### 6.1. Überblick

- Hauptklasse: `myaitranslationsclaude`, Datei `myaitranslationsclaude.php`.
- Version: 1.2.0.
- Technischer Name: `myaitranslationsclaude`. Name in der Modulliste: **AI Translations with Claude**.
- Autor: MyPresta.eu. Registerkarte im Module Manager: `administration`.
- Backoffice-Registerkarte: `AdminMyaitranslationsclaude`, übergeordnet `AdminInternational`, ersatzweise `IMPROVE`. Die sichtbare Beschriftung lautet `AI Translations with Claude`. `ensureTab()` stellt eine fehlende Registerkarte wieder her. `renameTabIfTechnical()` ersetzt einen Namen, der noch der technische Name ist.
- Installation: `parent::install()`, Tabellen aus `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (schreibt einen Schlüssel nur, wenn er fehlt), die Hooks `displayBackOfficeHeader` und `actionAdminControllerSetMedia`, danach die Registerkarte.
- Deinstallation: löscht die Registerkarte, führt `sql/uninstall.php` aus (entfernt 11 Tabellen), `removeConfiguration()` löscht die dort aufgeführten Schlüssel `MYAITCL_*`, danach `parent::uninstall()`. Nicht gelöscht werden `mypresta_updates`, `update_myaitranslationsclaude` und `updatev_myaitranslationsclaude`.
- Eine Methode `enable()` gibt es nicht, ebenso wenig `disable()`.
- `getContent()` ruft `ensureTab()` auf und leitet auf `AdminMyaitranslationsclaude` weiter (Standardregisterkarte `dashboard`).

Datenfluss:

1. Das Einstellungsformular sendet per POST an `AdminMyaitranslationsclaudeController::initContent()`.
2. `MyaitclConfigService::saveFromForm()` speichert `MYAITCL_*` in `Configuration`. `MyaitclApiKeyEncryptor` verschlüsselt den API-Schlüssel mit AES-256-CBC. Dafür wird ein Schlüssel aus `_COOKIE_KEY_` abgeleitet, und der Schlüssel wird als `MYAITCL_API_KEY_ENC` gespeichert. Ein leer abgesendeter Schlüssel oder ein maskierter Wert ersetzt den gespeicherten Schlüssel nicht.
3. Übersetzung: `MyaitclTranslateService::translateMessages()` erstellt die Prompts (`MyaitclPromptBuilder`), sendet sie über `MyaitclClaudeTranslationProvider` (cURL-POST an `https://api.anthropic.com/v1/messages` mit dem Header `anthropic-version: 2023-06-01`), prüft die Antwort (`MyaitclPlaceholderValidator`, `MyaitclHtmlValidator`, `MyaitclPsNativeValidator`), bewertet sie (`MyaitclQualityScorer`) und speichert sie über `MyaitclTranslationAdapter`.
4. Steht **Max tokens** auf 0, sendet der Provider `max_tokens` mit 4096. `acceptsTemperature()` sendet **Temperature** nur, wenn die Modell-ID dem Muster `claude-(opus|sonnet|haiku)-4-(0|1|5|6)` entspricht.
5. Beim Speichern des Katalogs wird der Übersetzungsdienst von PrestaShop verwendet, sofern er existiert. Andernfalls wird die Tabelle `_DB_PREFIX_translation` genutzt. Schlüssel klassischer Module schreibt `MyaitclLegacyModuleCatalogue` in die Datei `translations/{iso}.php` des Moduls.
6. Massenauftrag: `MyaitclBulkJobFactory` fügt Zeilen in `myaitcl_job` und `myaitcl_job_item` ein. `MyaitclJobWorker::processSlice()` verarbeitet einen Abschnitt der Größe `BATCH_SIZE`. Aufgerufen wird die Methode von **Process slice**, von der Schleife **Auto-process** (AJAX `ProcessJob`) und von `controllers/front/cron.php`.
7. Katalog: `MyaitclCatalogTranslateService::collect()` liest höchstens 100 Zeilen. `translateAndSave()` schreibt in `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` oder `_DB_PREFIX_cms_lang`. Die Ergebnisse werden über die ID zugeordnet. Nach dem Stapel wird **Start after ID** auf die höchste `id_entity` der gesammelten Menge gesetzt, fehlgeschlagene Zeilen eingeschlossen.
8. Jeder Aufruf wird in `myaitcl_request` gespeichert (**History**). Fehler gehen zusätzlich nach `myaitcl_api_log`, die Kosten nach `myaitcl_usage_ledger`. `MyaitclSnapshotService` kopiert den vorherigen Wert für **Rollback** nach `myaitcl_snapshot`. `clearTranslationCache()` ruft `Tools::clearCache()` nach dem Speichern eines Katalogs, nach einem Abschnitt, der kein Testlauf ist, und nach einem Rollback auf.

### 6.2. Dateien

| Datei | Aufgabe |
|---|---|
| `myaitranslationsclaude.php` | Installation, Deinstallation, Registerkarte, Hooks, Assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Update-Prüfung für die Registerkarte **Updates** und die Warnung im Backoffice. Klasse `myaitranslationsclaudeUpdate`. |
| `logo.png`, `logo.gif` | Logo im Modulkopf. |
| `controllers/admin/AdminMyaitranslationsclaudeController.php` | Jede Backoffice-Registerkarte, Speichervorgänge, Auftragsaktionen, Glossar, Ausschlüsse, Katalog, CSV, AJAX. |
| `controllers/front/cron.php` | Cron-Adresse. Verarbeitet einen Abschnitt und gibt JSON zurück. |
| `sql/install.php`, `sql/uninstall.php` | Erstellen und Löschen der Tabellen. |
| `src/Adapter/MyaitclTranslationAdapterInterface.php` | Schnittstelle zum Lesen und Schreiben von PrestaShop-Übersetzungen. |
| `src/Adapter/MyaitclAbstractTranslationAdapter.php` | Bereiche, Domains, Locales, Speichern über den Dienst oder die Tabelle `translation`, Leeren des Caches. |
| `src/Adapter/MyaitclTranslationAdapter.php` | Konkreter Adapter. |
| `src/Adapter/MyaitclTranslationAdapterFactory.php` | Erstellt den Adapter. |
| `src/Adapter/MyaitclFilesystemCatalogueTrait.php` | Liest XLF-Kataloge aus Themes und Modulen. |
| `src/Adapter/MyaitclLegacyModuleCatalogue.php` | Klassische Module: liest und schreibt `translations/{iso}.php`. |
| `src/Admin/MyaitclForms.php` | Formulare des Backoffice und der Feldtext `desc`. |
| `src/Admin/MyaitclSectionHelp.php` | Text des Panels **Help** für jede Registerkarte. |
| `src/Audit/MyaitclRequestLogRepository.php` | **History**: Zeilen, Karten, Diagramme, Filter, Leeren, Aufbewahrung. |
| `src/Audit/MyaitclApiLogRepository.php` | Protokoll der API-Fehler und -Warnungen, Aufbewahrung. |
| `src/Audit/MyaitclTranslationMemory.php` | Verwendet ein Ergebnis für denselben Text, dieselbe Locale, dasselbe Modell und dasselbe Glossar erneut. |
| `src/Audit/MyaitclUsageLedger.php` | Kostenschätzung aus der Preistabelle in dieser Datei und das monatliche Budget. |
| `src/Audit/MyaitclSnapshotService.php` | Kopien vor einem Schreibvorgang und deren Wiederherstellung bei **Rollback**. |
| `src/Glossary/MyaitclGlossaryRepository.php` | Glossarliste, Einfügen, Löschen. |
| `src/Glossary/MyaitclExcludePatternRepository.php` | Ausschlüsse einfügen, löschen und abgleichen. |
| `src/Job/MyaitclJobStatuses.php` | Statuskonstanten für Aufträge und Zeilen. |
| `src/Job/MyaitclJobRepository.php` | Aufträge und Zeilen: Lesen, Status, nächster Abschnitt, Zähler. |
| `src/Job/MyaitclJobWorker.php` | Verarbeitung von Abschnitten, Wiederholung, Abschluss, Prüfliste, Abschluss-E-Mail. |
| `src/Provider/MyaitclTranslationProviderInterface.php` | Schnittstelle des Providers. |
| `src/Provider/MyaitclClaudeTranslationProvider.php` | Claude-Aufrufe, Verbindungstest, Anfrageprotokoll. |
| `src/Provider/MyaitclPromptBuilder.php` | System- und Benutzer-Prompts: Ton, Markenstimme, Glossar. |
| `src/Provider/MyaitclProviderFactory.php` | Erstellt den Provider. |
| `src/Quality/MyaitclPlaceholderValidator.php` | Prüfung von Platzhaltern und Tags. |
| `src/Quality/MyaitclHtmlValidator.php` | HTML-Prüfung. |
| `src/Quality/MyaitclPsNativeValidator.php` | Prüfung vor dem Speichern bei **Manual**. |
| `src/Quality/MyaitclEmailHtmlPipeline.php` | Schützt das HTML von E-Mails vor dem Aufruf und stellt es nach der Antwort wieder her. |
| `src/Quality/MyaitclQualityScorer.php` | Wert 0-100, Flags, Entscheidung über die Prüfliste. |
| `src/Security/MyaitclApiKeyEncryptor.php` | Verschlüsseln und Entschlüsseln des API-Schlüssels. |
| `src/Service/MyaitclConfigService.php` | Lesen und Speichern von Einstellungen, Modellen, Cron-Token und Wertebereichen. |
| `src/Service/MyaitclRateLimiter.php` | Lokales Limit pro Minute, Datei `var/rate_limit.json`. |
| `src/Service/MyaitclTranslateService.php` | Ausschlüsse, Übersetzungsspeicher, Aufrufe, Prüfung, Bewertung, Speichern, Schätzung. |
| `src/Service/MyaitclBulkJobFactory.php` | Erstellt einen Auftrag auf **Bulk** und die Schätzung. |
| `src/Service/MyaitclCatalogTranslateService.php` | Sammelt und speichert Zeilen von **Catalog**. |
| `src/Service/MyaitclDashboardService.php` | Abdeckungszahlen auf **Dashboard**. |
| `translations/*.php` | Übersetzungen der Oberfläche, eine Datei pro Sprache. |
| `views/templates/admin/configure.tpl` | Die Modulseite und das Panel **Help**. |
| `views/templates/admin/_partials/*.tpl` | Registerkarten: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Stile des Backoffice. |
| `views/js/admin.js` | Fortschritt auf **Jobs** und **Auto-process**, Zeilenauswahl, AJAX. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Schaltflächen und Leiste auf **International → Translations**. |
| `views/js/entity-fields.js` | Schaltflächen und Leiste auf den Formularen von Produkt, Kategorie und CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Diagramme auf **Dashboard**. |
| `var/rate_limit.json` | Zähler für das lokale Limit pro Minute. |
| `index.php` in jedem Verzeichnis | Verhindert die Verzeichnisauflistung. |

### 6.3. Controller

**Backoffice: `AdminMyaitranslationsclaudeController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsclaude&token=…`, optional `&myaitcl_tab=` mit `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (die Beschriftung der Registerkarte ist **History**), `settings` oder `updates`.
- Auftragsaktionen über den Parameter `job_action` zusammen mit `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. Das Template zeigt keine Schaltfläche Cancel. `filter_failed=1` beschränkt die Zeilentabelle auf Fehler.
- Aktionen auf **Review**: `review_action=approve|reject` und `id_review`.
- Glossar: `delete_glossary`. Ausschlüsse: `delete_exclude`. Modelle: `delete_claude_model` sowie ein POST mit `new_claude_model` und `submitMyaitranslationsclaudeAddModel`.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail` sowie die Endpunkte für die Feldübersetzung, die `translations-tool.js` und `entity-fields.js` aufrufen.

**Front: `MyaitranslationsclaudeCronModuleFrontController`** (`controllers/front/cron.php`).

- Shop-URL: `module/myaitranslationsclaude/cron`.
- Der Parameter `token` muss mit `MYAITCL_CRON_TOKEN` übereinstimmen (`hash_equals`). Fehlt er oder ist er falsch, antwortet der Controller mit HTTP 403 und dem JSON `{"ok":false,"error":"Forbidden"}`.
- Ein optionales `id_job` verarbeitet genau diesen Auftrag. Ohne diesen Parameter wird der erste Auftrag in `pending` oder `running` verarbeitet.
- Ein erfolgreicher Abschnitt liefert JSON mit `ok`, `finished` und `counts`. Wartet kein Auftrag, lautet die Antwort `{"ok":true,"message":"No pending jobs"}`.
- Am Controller ist `ssl` auf true gesetzt.

### 6.4. Hooks

Registrierte Hooks:

- `displayBackOfficeHeader` - benennt eine technische Beschriftung der Registerkarte um und lädt danach CSS und JS.
- `actionAdminControllerSetMedia` - lädt dieselben Assets.

`translations-tool.js` wird im Controller für Übersetzungen eingebunden. `entity-fields.js` wird auf Shop-Formularen eingebunden, wenn die Feldschalter eingeschaltet sind. `Media::addJsDef` stellt `myaitclTr` bereit (AJAX-URL, Quell-Locale, Sprachen und die Beschriftungen der Leiste).

Das Modul registriert keinen eigenen Hook, den andere Module umsetzen könnten. Eine Methode `enable()` gibt es nicht, ebenso wenig `disable()`.

### 6.5. Overrides

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6. Datenbank

| Tabelle | Inhalt |
|---|---|
| `myaitcl_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, Shop-ID, Datumsfelder. |
| `myaitcl_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitcl_job` | Ein Massenlauf: Locales, `scope_json`, `policy_json`, `dry_run`, Zähler, Token-Summen, Kosten, Mitarbeiter, Fehler, Zeitstempel. |
| `myaitcl_job_item` | Eine Zeichenkette eines Auftrags: Domain, Schlüssel, Theme, Locale, Quelle, vorheriger Wert, neuer Wert, Status, Grund für das Überspringen, Fehler, Tokens, Prüfung. |
| `myaitcl_memory` | Übersetzungsspeicher: Hash, Quelle, Locale, Übersetzung, Modell, Trefferzahl. |
| `myaitcl_usage_ledger` | Tägliche Zeilen für Tokens und Kosten, optionale Auftrags-ID, Modell. |
| `myaitcl_snapshot` | Wert vor einem Schreibvorgang des Auftrags, verwendet von **Rollback**. |
| `myaitcl_api_log` | Fehler- und Warnzeilen: Stufe, Provider `claude`, HTTP-Code, Meldung, Kontext. |
| `myaitcl_request` | Zeilen von **History**: Typ, Status, Modell, Locales, HTTP-Code, Dauer, Tokens, Kosten, Mitarbeiter, Auftrag, Prompt, Antwort, Fehler. |
| `myaitcl_review` | Prüfliste: Auftragszeile, Status, Wert, Flags, Mitarbeiter. |
| `myaitcl_catalog_item` | Zeilen einer Katalogcharge: Entität, Feld, Sprachen, Quelle, vorheriger Wert, neuer Wert, Status, Fehler. |

Die Deinstallation löscht alle elf Tabellen. Die Installation verwendet `CREATE TABLE IF NOT EXISTS`. Eine Neuinstallation auf einer Datenbank, in der die Tabellen noch existieren, behält diese Zeilen. Eine normale Deinstallation entfernt sie vorher. Beim ersten Aufruf einer Seite wird keine Spalte ergänzt.

### 6.7. Schlüssel und Übersetzungen

Präfix `MYAITCL_`. Die Werte, die gelten, wenn ein Schlüssel fehlt. Sie entsprechen auch den Werten, die bei der Installation geschrieben werden:

| Schlüssel | Wert, wenn er fehlt |
|---|---|
| `API_KEY_ENC` | leer |
| `MODEL` | `claude-haiku-4-5` |
| `EXTRA_MODELS` | leer |
| `PROVIDER` | `claude` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | leer |
| `BATCH_SIZE` | `25` (beim Speichern erneut auf 1-100 begrenzt) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | leer |
| `TEMPERATURE` | `0.2` (beim Speichern erneut auf 0-1 begrenzt) |
| `DRY_RUN_SAMPLE` | `10` (beim Speichern erneut auf 1-50 begrenzt) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (mindestens 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | leer |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (der Provider sendet dann 4096) |
| `CRON_TOKEN` | 16 Zufallsbytes als Hex, bei der Installation erzeugt |

`removeConfiguration()` löscht unter demselben Präfix außerdem die alten Namen `DEEPL_API_KEY` und `CLAUDE_API_KEY`. Die Schlüssel der Update-Prüfung bleiben erhalten.

Die Feldbeschreibungen sind die Zeichenketten `desc` in `src/Admin/MyaitclForms.php`. `help()` setzt sie aus Zweck, Einstellung und Wirkung zusammen. Die Hilfe der Registerkarten steht in `src/Admin/MyaitclSectionHelp.php`.

Texte der Oberfläche laufen über `$this->l()` bzw. `{l s=... mod='myaitranslationsclaude'}`. Eine weitere Sprache fügen Sie mit `translations/{iso}.php` hinzu. Die Auftragsfehler **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No Claude API key. Nothing was translated.** und **Monthly API budget has been exhausted.** sind englische Zeichenketten, die `MyaitclJobWorker` und `MyaitclTranslateService` zurückgeben. Sie sind keine Aufrufe von `$this->l()`. Die Texte von **Updates** nutzen die Übersetzungsdomain `updatechecker`.

### 6.8. Erweitern

Die Shopansicht gibt kein Template dieses Moduls aus, daher gibt es für das Theme nichts zu überschreiben.

Die Backoffice-Templates liegen in `views/templates/admin/`. PrestaShop bietet für diese Admin-Templates kein Überschreiben über das Theme. Ändern Sie Beschriftungen über `translations/{iso}.php`. Die Schaltflächen auf **International → Translations** und auf den Shop-Formularen fügen `views/js/translations-tool.js` und `views/js/entity-fields.js` mit `myaitclTr` ein. Es gibt keinen Hook, mit dem ein Theme diese Leiste ersetzen könnte.

## 7. Hilfe

Modulseite: https://mypresta.eu/de/ki-kunstliche-intelligenz/ki-ubersetzungen-mit-claude.html

Um zu diesem Modul Kontakt aufzunehmen, melden Sie sich auf mypresta.eu in Ihrem Kundenkonto an, öffnen Sie das Kontaktformular und wählen Sie das Thema **Support for paid modules**. Das Formular weist darauf hin, dass für kostenpflichtige Module eine Anmeldung erforderlich ist. Nach der Anmeldung wählen Sie dieses Modul in Ihrer Kaufhistorie aus.
