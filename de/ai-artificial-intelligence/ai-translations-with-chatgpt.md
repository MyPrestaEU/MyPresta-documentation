---
title: "AI Translations with ChatGPT - Dokumentation und Benutzerhandbuch"
description: "Konfiguration und Fehlersuche für Shops, die AI Translations with ChatGPT bereits haben."
sidebar:
  label: "AI Translations with ChatGPT - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul AI Translations with ChatGPT auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/ai-translations-with-chatgpt/)
>
> ---


## 1. Voraussetzungen

Das Modul läuft auf PrestaShop 1.7.0.0 und neuer, einschließlich PrestaShop 8 und 9.

- **PrestaShop:** 1.7.0.0 oder neuer.
- **PHP:** 5.6 oder neuer.
- **PHP-Erweiterungen:** cURL, OpenSSL, SimpleXML und mbstring.
- **Andere Module:** dieses Modul braucht kein weiteres Modul.
- **Außerhalb des Shops:** ein OpenAI-Konto und ein API-Schlüssel. Der Shop-Server muss `https://api.openai.com/v1/chat/completions` öffnen können.
- **Optional:** ein geplanter Aufruf auf dem Server, der die Cron-Adresse aus **Settings** öffnet. Ohne ihn bearbeiten Sie Aufträge selbst unter **Jobs**.
- **Große Kataloge:** eine Domain mit Tausenden von Zeichenketten sind viele API-Aufrufe. Der Auftrag wird in Scheiben der Größe **Batch size** geteilt. Starten Sie **Estimate** unter **Bulk**, bevor Sie beginnen.
- Der Shop braucht mindestens zwei Sprachen. Bei einer Sprache zeigt das Backoffice **The shop needs at least two languages.** und es gibt nichts zu übersetzen.

## 2. Installation

1. Öffnen Sie **Modules**, dann **Module Manager**. Wählen Sie **Upload a module**, laden Sie die ZIP-Datei hoch und drücken Sie **Install** bei **AI Translations with ChatGPT**.
2. Nach der Installation steht **AI Translations with ChatGPT** im Menü **International**.
3. Die Installation leert den Shop-Cache nicht. Das Modul leert den Cache, wenn es eine Übersetzung speichert.

Öffnen Sie **AI Translations with ChatGPT**, dann **Settings**, und fügen Sie den ChatGPT-Schlüssel ein. Solange kein Schlüssel gespeichert ist, zeigt jede Seite des Moduls **No ChatGPT API key.** und den Link **Open Settings**.

**Deinstallation.** Drücken Sie im **Module Manager** **Uninstall** und bestätigen Sie **Delete this module and its data (jobs, glossary, cache)?**

- Der Menüeintrag verschwindet. Aufträge, das Glossar, Ausschlussmuster, der Aufrufverlauf, die Warteschlange **Review**, Rollback-Kopien, das Kostenbuch und die Moduleinstellungen (einschließlich des API-Schlüssels) werden gelöscht.
- Text, den das Modul bereits in den Shop geschrieben hat, bleibt: Katalogübersetzungen und die Übersetzungsdateien klassischer Module, die dieses Modul geschrieben hat. Die Wahl der Update-Prüfung bleibt ebenfalls.
- Eine neue Installation stellt gelöschte Aufträge, das Glossar oder den Verlauf nicht wieder her. Sie setzt die Standardwerte und erzeugt eine neue Cron-Adresse.

## 3. Konfiguration und tägliche Arbeit

Das ganze Modul ist eine Seite: **International**, dann **AI Translations with ChatGPT**. Die Register sind **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** und **Settings**. **Updates** steht am Ende der Leiste. **Help** öffnet ein Feld für das aktuelle Register.

Schaltflächen- und Feldnamen in diesem Handbuch sind die des englischen Backoffice. In einer anderen Backoffice-Sprache sehen Sie die Übersetzung derselben Steuerung. Die Bildschirmfotos sind auf Englisch.

Ein normaler Lauf hat vier Teile.

1. **Verbindung.** Fügen Sie unter **Settings** den Schlüssel ein, wählen Sie das Modell und drücken Sie **Test connection**, dann **Save**.
2. **Ein kleiner Test.** Filtern Sie unter **Manual** eine Domain, markieren Sie ein paar leere Zeichenketten und übersetzen Sie sie. Prüfen Sie das Ergebnis, bevor Sie einen ganzen Katalog starten.
3. **Ein Auftrag.** Wählen Sie unter **Bulk** den Bereich, die Sprachen und die Domains, drücken Sie **Estimate**, dann **Start job**. Öffnen Sie den Auftrag und drücken Sie **Process slice** oder **Auto-process**, oder lassen Sie die Cron-Adresse ihn aufrufen.
4. **Eine Kontrolle.** Öffnen Sie **Review** für Zeilen, die die Qualitätsprüfung zurückgehalten hat, und **History**, wenn ein Aufruf scheitert. **Rollback** am Auftrag stellt den vorherigen Text wieder her, wo das Modul eine Kopie behalten hat.

Das Modul startet eine Übersetzung nicht von selbst. **Estimate**, **Filter** und **Save** unter **Settings** schreiben keinen Katalogtext. Ein Auftrag bleibt unter **Jobs**, bis Sie ihn verarbeiten oder die Cron-Adresse aufgerufen wird.

### 3.1. Modulkonfiguration

Öffnen Sie **Modules**, **Module Manager**, suchen Sie **AI Translations with ChatGPT** und drücken Sie **Configure**. Das öffnet **Dashboard**. Gehen Sie zu **Settings**.

**Save** und **Test connection** stehen unten im Formular. Das Speichern dieses Formulars startet keine Übersetzung und schreibt bereits gespeicherte Übersetzungen nicht um.

![Einstellungen, englisches Backoffice. Oben im Formular: ChatGPT API key, Model, Add a ChatGPT model, Tone und Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings.webp)

**Verbindung**

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **ChatGPT API key** | leer | Das Geheimnis, das dieser Shop an ChatGPT sendet. Fügen Sie den Schlüssel aus Ihrem OpenAI-Konto ein. Lassen Sie das Feld leer, um den bereits gespeicherten Schlüssel zu behalten. Ein neuer Wert ersetzt den gespeicherten Schlüssel. Ein leeres Feld löscht ihn nicht. Wenn ein Schlüssel gespeichert ist, zeigt der Hilfetext **Key saved:** und einen maskierten Schlüssel. |
| **Model** | gpt-4.1-mini | Das ChatGPT-Modell, das die Übersetzung schreibt. Eingebaute Namen bleiben in der Liste: gpt-4.1, gpt-4.1-mini, gpt-4.1-nano, gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4-turbo-preview, gpt-4, gpt-4-0613, gpt-3.5-turbo, gpt-3.5-turbo-0125, o4-mini, o3-mini und o1-mini. Die nächste Übersetzung verwendet das gewählte Modell. Ein Modell, das das Konto nicht nutzen kann, lässt den Aufruf fehlschlagen, und der Fehler steht unter **History**. |
| **Add a ChatGPT model** | leer | Geben Sie die genaue Kennung aus dem OpenAI-Konto ein und drücken Sie **Add model**. Der Platzhalter im Feld ist gpt-4.1. Die neue Kennung erscheint unter **Model** und wird das aktive Modell. **Remove** löscht nur hier hinzugefügte Kennungen. Eingebaute Kennungen lassen sich nicht löschen. |

Meldungen: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example gpt-4.1.**, **Built-in models cannot be removed.**

**Stimme und Quelle**

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Tone** | Formal | Fügt jedem Prompt eine Stilanweisung hinzu. **Formal** gilt für Shop- und Backoffice-Texte, **Casual** ist leichter, **Brand** wird zusammen mit **Brand voice** verwendet. Neue Übersetzungen folgen diesem Stil. Vorhandene Übersetzungen bleiben, bis Sie sie erneut ausführen. |
| **Brand voice** | leer | Sichtbar, wenn **Tone** auf **Brand** steht. Ein paar schlichte Sätze, wie der Shop klingen soll, oder ein leeres Feld. Der Text kommt in den nächsten Prompt. Leer bedeutet keine zusätzliche Stimme. Gespeicherte Übersetzungen werden nicht umgeschrieben. |
| **Source locale** | leer | Die Sprache, die das Modell als Original behandelt. Die leere Wahl ist ein Strich in der Liste: der Bildschirm, den Sie übersetzen, liefert die Quelle. Wählen Sie das Locale, in dem Ihre Kataloge geschrieben sind, meist en-US. **Manual**, **Bulk** und die Symbole unter **International → Translations** senden dieses Locale als Quelle. Die Standard-Shopsprache ändert sich nicht. |
| **Individual field buttons — shop forms** | Yes | Eine Schaltfläche an jedem mehrsprachigen Feld der Shop-Formulare: Produkt, Kategorie, CMS und die übrigen Backoffice-Formulare. Die Schaltfläche übersetzt nur dieses Feld. **No** blendet diese Schaltflächen im ganzen Shop aus. Gespeicherte Übersetzungen ändern sich nicht. |
| **Individual field checkboxes — shop forms** | Yes | Jedes dieser Felder bekommt ein Kontrollkästchen, und die Leiste übersetzt nur die Felder, die Sie ankreuzen. **No** blendet die Kästen und die Leiste aus. Die Schaltflächen darüber folgen ihrem eigenen Schalter. |
| **Individual field buttons — International → Translations** | Yes | Eine Schaltfläche an jedem Feld von **International → Translations**. **No** blendet diese Schaltflächen aus. Shop-Formulare sind nicht betroffen. Ein Klick füllt dieses Feld. **Save** von PrestaShop schreibt die Seite weiterhin. |
| **Individual field checkboxes — International → Translations** | Yes | Kontrollkästchen und die Leiste unter **International → Translations**. **No** blendet sie aus. Shop-Formulare sind nicht betroffen. |

**Grenzen**

![Einstellungen, englisches Backoffice. Batch size und die Grenzwertfelder darunter.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings-limits.webp)

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Batch size** | 25 | Wie viele Zeichenketten in einem API-Aufruf gesendet werden. Nehmen Sie für den ersten Lauf 10 bis 25. Der Wert bleibt zwischen 1 und 100. Eine größere Scheibe beendet einen Auftrag mit weniger Aufrufen. Ein Fehler wiederholt dann ein größeres Stück. |
| **Dry-run sample** | 10 | Wie viele Beispielzeichenketten **Estimate** vor einem Sammelauftrag zeigt. Der Wert bleibt zwischen 1 und 50. **Estimate** schreibt keine Übersetzungen. |
| **Max tokens (0 = default)** | 0 | Das Formular speichert diese Zahl. Die Übersetzungsanfrage sendet sie nicht, daher kürzt sie die Antwort nicht und stoppt auch keine abgeschnittene Antwort. Der Verbindungstest verwendet eine eigene kurze Anfrage. Bereits gespeicherte Übersetzungen werden nicht beschnitten. |
| **Budget USD / month** | 0 | Eine monatliche Obergrenze in US-Dollar, gezählt aus dem Nutzungsbuch. 0 bedeutet keine Obergrenze. Wenn das Buch den Betrag erreicht, stoppen neue Übersetzungen. Bereits Gespeichertes bleibt. |
| **Rate limit / min** | 60 | Wie viele API-Aufrufe dieser Shop in einer Minute starten darf. 0 schaltet diese lokale Grenze aus. Aufrufe über der Grenze werden übersprungen und unter **History** aufgeführt. ChatGPT kann weiterhin seine eigene Grenze anwenden. |
| **Log retention days** | 30 | Wie viele Tage an Zeilen unter **History** bleiben. Mindestens 1. Ältere Zeilen werden entfernt. Diese Zahl löscht keine Aufträge, kein Glossar und keine gespeicherten Übersetzungen. |
| **Temperature** | 0.2 | Wie frei das Modell umformulieren darf. Etwa 0,2 bleibt nah an der Quelle. Werte nahe 1 verändern die Sätze stärker. Der gespeicherte Wert bleibt zwischen 0 und 1. Platzhalter und HTML werden danach weiter geprüft. Die Übersetzungsanfrage sendet diesen Wert für jedes Modell in der Liste, auch für eine Kennung, die Sie hinzufügen. |
| **Allow publish / save** | Yes | Ob dieses Modul eine Übersetzung in PrestaShop schreiben darf. **No** blockiert das Speichern unter **Manual**, bei Sammelaufträgen und unter **Catalog**. Die Symbole auf der Übersetzungsseite und auf Shop-Formularen füllen weiterhin nur das Formular. **Save** von PrestaShop ist getrennt. |

Nach **Save**:

- **Settings saved. No translation was started.** Die Einstellungen sind gespeichert und nichts wurde übersetzt.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Fügen Sie einen Schlüssel unter **ChatGPT API key** ein und drücken Sie **Save** erneut.

**E-Mail und Cron**

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Email notify on complete** | No | Sendet eine E-Mail, wenn ein Sammelauftrag endet. Der Auftrag läuft in jedem Fall. Nur die E-Mail wird hinzugefügt oder ausgelassen. |
| **Notify email** | leer | Die Adresse, die diese E-Mail erhält. Das Feld ist nur sichtbar, wenn der Schalter darüber an ist. Das Speichern der Adresse sendet von selbst keine Nachricht. |
| **CRON URL** | eine Adresse mit Token | Eine geheime Adresse, mit der der Server eine Scheibe eines wartenden Auftrags verarbeiten kann. Kopieren Sie sie in den Server-Zeitplan. Veröffentlichen Sie sie nicht. Wer die Adresse hat, kann eine Scheibe starten. Das Öffnen von **Settings** startet keinen Auftrag. |

**Test connection** prüft Schlüssel und Modell mit einer kurzen Anfrage. Es übersetzt nicht und speichert nicht.

- **Connection OK (N ms). No translation was started.** Die Verbindung funktioniert.
- **Connection was not made. Nothing was translated.** und danach der Grund. Prüfen Sie Schlüssel und Modell. Das Detail steht unter **History**.

Ein praktischer Start: Schlüssel einfügen, Modell und Quell-Locale wählen, **Test connection** drücken, dann **Save**. Lassen Sie die Zahlen auf den Installationswerten, bis sich ein Auftrag schlecht verhält.

### 3.2. Dashboard

Öffnen Sie das Register **Dashboard**. Es zählt fehlende Katalogzeichenketten und zeigt danach die ChatGPT-Nutzung als Karten, Diagramme und die zehn neuesten Prompts. Die Seite übersetzt nicht und ändert keine Zeichenketten.

![Dashboard, englisches Backoffice. Abdeckung für ein Locale, die Cron-Zeile und die Verlaufsfilter.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-dashboard.webp)

**Abdeckung**

- **Locale:** das Shop-Locale, dessen fehlende Zeichenketten gezählt werden.
- **Show:** zeichnet die Tabelle für dieses Locale neu.
- Spalten: **Section**, **Total**, **Missing**, **Done** und ein Fortschrittsbalken. Bereiche sind **Back office**, **Themes**, **Installed modules**, **Emails** und **Others**. **Missing** ist die Zahl der Zeichenketten ohne Übersetzung in diesem Locale.
- Unter der Tabelle zeigt **CRON** dieselbe Adresse wie **CRON URL** unter **Settings**.
- Eine leere Tabelle bedeutet, dass der Shop für dieses Locale noch keinen Katalog hat. Legen Sie ihn unter **International → Translations** an.

Nach **Show** lautet die Meldung **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Nutzung**

- Vorgaben: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filter: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** und **Prompt or reply contains**. Drücken Sie **Filter**.
- Karten: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** und **Estimated cost**. Die geschätzten Kosten sind eine lokale Schätzung, keine Rechnung von OpenAI.
- Diagramme: **Requests and errors**, **Tokens sent and received**, **Requests by model**. Darunter die Gruppen **By day**, **By model**, **By type**, **By language** und **By employee**, mit den Spalten **Group**, **Calls**, **Sent**, **Received** und **Total**. Eine leere Gruppe sagt **No requests in this range.**
- **Latest prompts** listet zehn Aufrufe. **View** öffnet Prompt und Antwort. **See all** öffnet **History** (3.10). Eine leere Liste sagt **No requests yet.**

Filtern löscht den Verlauf nicht und ändert keine Übersetzungen.

Wenn ein Bereich größtenteils fehlt, öffnen Sie **Manual** für ein paar Zeichenketten oder **Bulk** für eine ganze Domain.

### 3.3. Manual

Öffnen Sie **Manual**. Es übersetzt eine Domain oder ein klassisches Modul, ein paar Dutzend Zeichenketten auf einmal. Filtern speichert nichts.

![Manual, englisches Backoffice. Section, Source, Target, Domain, Only empty und Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-manual.webp)

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Section** | Back office | Welcher Katalog gelesen wird: **Back office**, **Themes**, **Installed modules**, **Emails** oder **Others**. Ein Wechsel lädt die Seite neu und zeigt nur die Felder dieses Bereichs. Er ruft ChatGPT nicht auf. |
| **Theme** | leer | Nur bei **Themes** sichtbar. Begrenzt die Liste auf ein Theme. |
| **Module** | leer | Nur bei **Installed modules** sichtbar. Begrenzt die Liste auf ein Modul. Ein klassisches Modul ohne Domain lädt jede Zeichenkette dieses Moduls. |
| **Domain** | leer | Dieselbe Gruppierung wie unter **International → Translations**. Wählen Sie sie und drücken Sie **Filter**. Verborgen bei einem klassischen Modul und bei einem Bereich ohne Domains. |
| **Source** | das **Source locale** aus **Settings**, oder en-US | Die Sprache, aus der die Zeichenketten genommen werden. Wählen Sie eine Sprache, die schon einen guten Text hat. |
| **Target** | die erste Sprache der Liste | Die Sprache, die Sie füllen wollen. Sie muss unter **International → Localization → Languages** existieren. |
| **Only empty** | Yes | Zeigt nur Zeichenketten ohne Übersetzung. Ausgeschaltet zeigt es jede Zeichenkette. Gespeicherte Übersetzungen werden nicht gelöscht. |
| **Search** | leer | Behält nur Quellzeichenketten, die das eingegebene Wort enthalten. |

Schritte:

1. Setzen Sie **Section**, **Source** und **Target**.
2. Wählen Sie bei **Themes** **Theme**. Wählen Sie bei **Installed modules** **Module**.
3. Drücken Sie **Filter**. Die Liste **Domain** wird neu gefüllt. Wählen Sie eine Domain und drücken Sie **Filter** erneut. Bei einem klassischen Modul lassen Sie die Domain aus: **Filter** lädt jede Zeichenkette des Moduls.
4. Kreuzen Sie die Zeilen an. **Check all** und **Uncheck all** wählen die Liste oder leeren sie.
5. Drücken Sie **Translate selected (review)**. Eine Tabelle **Review before save** öffnet sich mit **Source**, **AI proposal** und **Warnings**. Nehmen Sie Zeilen heraus, die Sie nicht wollen. Bearbeiten Sie den Vorschlag im Feld. Drücken Sie **Save approved**.
6. Oder kreuzen Sie vor dem Übersetzen **Save now (skip review)** an. Gültige Zeilen werden sofort geschrieben, ohne die Prüftabelle.

Die Spalten der Zeichenkettenliste sind **Source**, **Current** und **Status** (**empty** oder **filled**).

Meldungen:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Das ist die Liste eines klassischen Moduls.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to ChatGPT.**
- **No strings match this filter. Nothing was sent to ChatGPT.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to ChatGPT.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Diese Zeilen wurden übersprungen. Korrigieren Sie Platzhalter und Tags, damit sie zur Quelle passen, und speichern Sie erneut.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Ein Wechsel des Bereichs zeigt außerdem eine kurze Zeile wie **Section is Back office. Theme and module are not used.** zusammen mit **Nothing was sent to ChatGPT.** Dasselbe Muster gilt für **Themes**, **Installed modules**, **Emails** und **Others**.

### 3.4. Bulk

Öffnen Sie **Bulk**. Es legt einen Auftrag für viele Domains und Sprachen an. **Estimate** speichert nicht. **Start job** legt eine Zeile unter **Jobs** an. Nichts wird geschrieben, bis der Auftrag verarbeitet wird und **Allow publish / save** an ist.

![Bulk, englisches Backoffice. Section, Source, Targets, Domains, Policy und Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-bulk.webp)

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Section** | Back office | Welchen Katalog der Auftrag liest. Dieselben Wahlmöglichkeiten wie unter **Manual**. |
| **Theme** / **Module** | leer | Nur für den passenden Bereich sichtbar, wie unter **Manual**. |
| **Source** | das **Source locale** aus **Settings**, oder en-US | Die Sprache, die als Original gilt. Jedes Ziel wird aus dieser Sprache übersetzt. |
| **Targets** | keine | Eine oder mehrere Sprachen zum Füllen. Halten Sie Strg, oder Cmd auf dem Mac, um mehrere zu wählen. Ein einfacher Klick ersetzt die Auswahl. |
| **Domains** | keine | Domains im Auftrag. Halten Sie Strg oder Cmd. Domains, die Sie nicht wählen, werden nicht übersetzt. Lassen Sie alle ungewählt nur, wenn Sie einen leeren Auftrag wollen. Ausnahme ist ein klassisches Modul ohne Domain: der Auftrag umfasst dann dieses Modul. |
| **Policy** | Fill empty | **Fill empty** sendet nur Zeichenketten ohne Übersetzung. **Overwrite all** sendet jede Zeichenkette, auch solche mit Übersetzung, und kann sie ersetzen. **Outdated if equals source** sendet nur Zeichenketten, deren Übersetzung mit der Quelle identisch ist. |
| **Dry-run job** | No | ChatGPT läuft trotzdem und der Auftrag erscheint unter **Jobs**, aber die Antworten werden nicht in den Shop geschrieben. |

Schritte:

1. Wählen Sie Bereich, Quelle, Ziele, Domains und Richtlinie.
2. Drücken Sie **Estimate**. Die Seite zeigt **Estimate**, die Zahl der Zeichenketten, eine Token-Schätzung, eine Kostenschätzung und ein **Sample**.
3. Wenn die Schätzung passt, drücken Sie **Start job**. **Jobs** öffnet sich mit dem neuen Auftrag.
4. Verarbeiten Sie ihn unter **Jobs** (3.5), oder lassen Sie ihn für die Cron-Adresse.

Meldungen:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to ChatGPT and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no ChatGPT API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Öffnen Sie **Jobs**. Jede Zeile ist ein Lauf aus **Bulk**.

![Jobs, englisches Backoffice. Die leere Auftragsliste.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-jobs.webp)

Spalten: **#**, **Status**, **Locales** (Quelle, dann Ziele), **Progress** (erledigt/gesamt), **Cost**, **Employee**, **Date** und **Open**. Eine leere Liste sagt **No jobs yet.**

Auftragsstatus, wie auf dem Bildschirm:

- `pending` - wartet. Er startet nicht von selbst.
- `running` - in Arbeit.
- `paused` - angehalten, bis Sie ihn fortsetzen.
- `cancelled` - gestoppt. Zeichenketten, die noch warteten, wurden nicht übersetzt.
- `completed` - jede Zeichenkette verarbeitet, ohne Fehler.
- `completed_with_errors` - beendet, und einige Zeichenketten sind fehlgeschlagen.
- `failed` - der Auftrag endete mit einem Fehler.

**Der Auftragsbildschirm**

**Open** zeigt **Job #N**, den Status, den Fortschritt (erledigt/gesamt), **failed**, **skipped**, die Kosten, die Mitarbeiternummer und die Beschriftung **dry-run**, wenn der Auftrag ein Probelauf ist. Der Fortschrittsbalken aktualisiert sich von selbst, solange der Auftrag offen ist. Die Tabelle darunter hat **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** und **Error**.

Zeilenstatus: `pending`, `processing`, `done`, `failed`, `skipped` (ein Ausschluss passte, oder die Zeichenkette war schon übersetzt) und `rolled_back`.

Schaltflächen:

- **Process slice** - eine Scheibe in der Größe von **Batch size**, dann Stopp. Meldung: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Wenn nichts mehr da ist: **The job has no more strings waiting.**
- **Auto-process** - wiederholt Scheiben, bis der Auftrag endet oder ein Fehler ihn stoppt. Es läuft im Browser, die Registerkarte muss offen bleiben. Schließen der Registerkarte stoppt die Schleife. Der Auftrag bleibt und lässt sich mit **Process slice** oder der Cron-Adresse beenden.
- **Pause** - Meldung: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - Meldung: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - fehlgeschlagene Zeichenketten warten wieder, und der Auftrag wartet erneut. Meldung: **Retried N failed items.**
- **Rollback** - fragt **Roll back this job?** und stellt die vorherige Übersetzung wieder her, wo das Modul vor der Änderung eine Kopie gespeichert hat. Meldung: **Rollback: restored N translations.**
- **Error CSV** - lädt die fehlgeschlagenen Zeilen herunter. Spalten: id, domain, locale, source, error.
- **Failed only** - zeigt nur die fehlgeschlagenen Zeilen.
- **Review queue** - öffnet **Review** (3.6).

Der Auftragsbildschirm hat keine Schaltfläche Cancel. Stoppen Sie weitere Arbeit mit **Pause**.

**Automatische Pause**

Wenn ChatGPT Aufrufe wegen eines Ratenlimits ablehnt, pausiert der Auftrag selbst. Die Fehlerzeile ist **Rate limit — job auto-paused. Resume later.** Warten Sie, dann drücken Sie **Resume**. **Rate limit / min** unter **Settings** senkt, wie viele Aufrufe der Shop in einer Minute startet.

Weitere Meldungen auf diesem Bildschirm:

- **Nothing was translated.** gefolgt von **No ChatGPT API key. Nothing was translated.** Fügen Sie den Schlüssel unter **Settings** ein.
- **Allow publish is off in Settings.** Ein Auftrag, der kein Probelauf ist, läuft erst, wenn Sie **Allow publish / save** einschalten.
- **Monthly API budget has been exhausted.** Erhöhen Sie **Budget USD / month**, oder setzen Sie es auf 0.

### 3.6. Review

Öffnen Sie **Review**, oder drücken Sie **Review queue** an einem Auftrag. Die Titelzeile ist **Needs-review queue (quality score / flags).** Sie listet die neuesten Zeilen, die die Qualitätsprüfung nicht automatisch bestanden hat, bis zu 100.

![Review, englisches Backoffice. Die leere Prüfliste.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-review.webp)

Spalten: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, dann **Approve** und **Reject**. Eine leere Liste sagt **The queue is empty.**

So lesen Sie eine Zeile:

- **Score** geht von 0 bis 100. Unter 70 kommt die Zeile in die Warteschlange.
- **Flags:**
  - `validation_failed` - Platzhalter oder HTML haben die Prüfung nicht bestanden.
  - `warning` - ein kleinerer Prüfhinweis.
  - `length_explosion` - die Übersetzung ist mehr als zweieinhalbmal so lang wie die Quelle.
  - `too_short` - die Übersetzung ist viel kürzer als eine längere Quelle.
  - `possible_untranslated` - englische Wörter wie the, and, with, your oder please stehen noch in der Übersetzung.
- **Source** ist das Original. **AI** ist der Vorschlag des Modells.

**Approve** und **Reject** ändern nur den Zeilenstatus. Die Meldung ist **Review updated.** Die Zeile verlässt die Liste. Diese Seite fügt den Text nicht von selbst in den Katalog ein.

Wenn der Auftrag speichern durfte, kann der Vorschlag schon im Shop stehen. Um eine Änderung aus diesem Auftrag rückgängig zu machen, verwenden Sie **Rollback** am Auftrag unter **Jobs**.

### 3.7. Catalog

Öffnen Sie **Catalog**. Es übersetzt Produkt-, Kategorie- oder CMS-Felder, die in den Shop-Sprachen gespeichert sind. Es bearbeitet nicht **International → Translations**. Ein Druck verarbeitet höchstens 100 Datensätze. Gespeicherte Zeilen werden in der Zielsprache geschrieben.

![Catalog, englisches Backoffice. Entität, Felder, Sprachen und Translate batch.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-catalog.webp)

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Entity** | product | Was gelesen wird: **product**, **category** oder **cms**. Ein Wechsel lädt die Seite neu und zeigt nur diese Feldliste. Der Wechsel selbst übersetzt nicht. |
| **Fields** | jedes Feld dieser Entität | Welche Texte der Stapel sendet. Halten Sie Strg oder Cmd. Nicht gewählte Felder werden nicht gesendet und bleiben, wie sie sind. Produkt: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Kategorie: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. **Title** bei Produkt oder Kategorie ist der Name. Bei CMS ist **Title** der Seitentitel und **Content** der Seitentext. Lassen Sie **Friendly URL** ungewählt, wenn die Links bleiben sollen. |
| **Source language** | die erste Shop-Sprache | Die Sprache, aus der die Felder kopiert werden. Diese Sprache wird nicht geändert. |
| **Target language** | die erste Shop-Sprache | Die Sprache, die die Übersetzung erhält. Sie muss sich von der Quelle unterscheiden. |
| **Only empty** | Yes | Überspringt Felder, die in der Zielsprache schon Text haben. Schalten Sie es nur aus, wenn Sie vorhandenen Text ersetzen wollen. An: vorhandener Zieltext bleibt. Aus: der Stapel kann ihn ersetzen, wenn das Veröffentlichen erlaubt ist. |
| **Start after ID** | 0 | Überspringt Datensätze bis zu dieser ID. 0 beginnt beim ersten Datensatz. Nach einem Stapel wird das Feld auf die höchste ID in diesem Stapel gesetzt, einschließlich fehlgeschlagener Zeilen. Drücken Sie die Schaltfläche erneut, um fortzufahren. Um eine fehlgeschlagene Zeile zu wiederholen, setzen Sie die ID vor dem nächsten Druck wieder unter diesen Datensatz. |

Schaltfläche: **Translate batch (max 100)**.

Schritte:

1. Wählen Sie **Entity** und kreuzen Sie die Felder an.
2. Wählen Sie **Source language** und **Target language**.
3. Lassen Sie **Only empty** an.
4. Drücken Sie **Translate batch (max 100)**. Die Meldung ist **Catalog finished: saved N, failed M.** Die Seite zeigt außerdem die Zahlen **Saved** und **failed**.
5. Öffnen Sie einen Datensatz in der Zielsprache und prüfen Sie das Ergebnis, bevor Sie **Only empty** ausschalten oder den nächsten Stapel starten.

Meldungen:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- Ein Wechsel von **Entity** zeigt **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Öffnen Sie **Glossary**. Das Glossar ist eine Liste von Wörtern und Wendungen, die das Modell behalten oder immer gleich übersetzen muss. Eine neue Zeile ändert bereits gespeicherte Übersetzungen nicht. Die nächste Übersetzung liest die Liste.

![Glossary, englisches Backoffice. Begriff hinzufügen und die Begriffsliste.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-glossary.webp)

**Ein Begriff**

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Source term** | leer, erforderlich | Das Wort oder die Wendung in der Quellsprache. Geben Sie es genau so ein, wie es vorkommt, einschließlich Großbuchstaben, wenn sie zählen. |
| **Target locale** | leer | Begrenzt die Zeile auf ein Locale, zum Beispiel pl-PL. Leer bedeutet, dass die Zeile für jede Zielsprache gilt. Ein gefülltes Locale wird für andere Sprachen ignoriert. |
| **Target term** | leer | Die freigegebene Übersetzung. Sie darf nur leer sein, wenn **Do not translate** an ist. |
| **Do not translate** | No | An: das Modell kopiert den Begriff unverändert, zum Beispiel eine Marke, eine SKU oder ein Tag. Aus: es verwendet **Target term**. |

Drücken Sie **Add**. Meldungen: **Glossary term added. Translations already stored were not changed.** oder **Nothing was added. Type a source term.**

**Die Tabelle**

Spalten: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** oder **No**) und **Delete**. **Delete** entfernt nur diese Zeile. Meldung: **Glossary term deleted.** Eine leere Liste sagt **No glossary terms yet.**

**CSV**

- Wählen Sie **CSV file** und drücken Sie **Import CSV**. Meldung: **Imported N rows.** Fehlt die Datei: **CSV file is missing.** Lässt sie sich nicht lesen: **Cannot open the CSV file.**
- Die erste Zeile ist eine Kopfzeile: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Diese erste Zeile wird immer übersprungen. Zeilen mit weniger als drei Spalten werden übersprungen. In der vierten Spalte bedeuten ein leerer Wert oder 0 **No**. Jeder andere Wert bedeutet **Yes**.
- Der Import fügt die Zeilen hinzu, die er lesen kann. Er sucht keinen vorhandenen Begriff und ersetzt ihn nicht, daher legt derselbe Import noch einmal Duplikate an.
- **Export CSV** lädt die aktuelle Liste als `glossary.csv` herunter. Er braucht keine Eingabedatei und ändert die Liste nicht.

Verwenden Sie kurze, genaue Begriffe. Ein sehr breiter Begriff wird jedes Mal erzwungen, wenn er vorkommt.

### 3.9. Excludes

Öffnen Sie **Excludes**. Ein Ausschluss ist ein Muster von Quelltext, den das Modul nicht an ChatGPT sendet. Der Text bleibt im Shop unverändert. Das Muster gilt unter **Manual**, **Bulk**, **Catalog** und auf den Übersetzungsseiten.

![Excludes, englisches Backoffice. Pattern, Type und die Musterliste.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-excludes.webp)

| Feld | Bei der Installation | Wirkung |
|---|---|---|
| **Pattern** | leer, erforderlich | Der Text, der mit jeder Quellzeichenkette verglichen wird. Der Vergleich hängt von **Type** ab. |
| **Type** | exact | **exact** ist die ganze Zeichenkette. **prefix** ist der Anfang. **contains** ist ein Stück irgendwo in der Zeichenkette. **regex** ist ein PHP-regulärer Ausdruck, so angewendet, wie er geschrieben ist. Ein falscher Ausdruck passt auf nichts. Beginnen Sie mit einem kurzen Muster und prüfen Sie, was übersprungen wurde. Ein falscher Typ kann zu viel oder nichts überspringen. |

Drücken Sie **Add**. Meldung: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Ein leeres Muster: **Nothing was added. Type a pattern.**

Spalten: **Pattern**, **Type**, **On** und **Delete**. **On** zeigt 1, wenn das Muster aktiv ist. Dieser Bildschirm hat keinen Schalter, um ein Muster auszuschalten. Um es nicht mehr zu verwenden, **Delete** und fügen Sie es erneut hinzu, wenn Sie es noch brauchen. **Delete** entfernt nur dieses Muster. Vorhandene Übersetzungen werden nicht gelöscht. Meldung: **Pattern deleted.** Eine leere Liste sagt **No patterns yet.**

Verwenden Sie Ausschlüsse für Text, der in der Quellsprache bleiben muss, etwa einen rechtlichen Namen oder ein technisches Token. Für einen Begriff, der immer auf eine Weise übersetzt werden muss, verwenden Sie **Glossary**.

### 3.10. History

Öffnen Sie **History**, oder drücken Sie **See all** auf dem **Dashboard**.

![History, englisches Backoffice. Die Anforderungsliste.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-history.webp)

**History** ist die volle Liste gespeicherter ChatGPT-Aufrufe: manuelle Läufe, die Übersetzungsseite, Sammelaufträge, Katalogstapel und der Verbindungstest. Jede Zeile behält Prompt, Antwort, Modell, Sprachen, Tokenzahlen und die Dauer. Karten und Diagramme stehen auf dem **Dashboard**. Das Öffnen dieser Seite sendet keine neue Anfrage und ändert keine Übersetzungen.

Die Filter sind dieselben wie auf dem **Dashboard** (3.2).

Spalten: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** und **Prompt**. Typen: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** und **Not sent** (der Aufruf wurde nicht gesendet, zum Beispiel wegen der lokalen Grenze oder des Budgets). Eine Zeile **Bulk job** zeigt die Auftragsnummer.

- **View** öffnet Prompt und Antwort, mit **HTTP**, **Sent**, **Received** und **Total**. Bei einem Fehler ist die Antwort der Fehlertext. **Back to the list** kehrt zur Tabelle zurück. Fehlt die Zeile: **This history row no longer exists.**
- Ein Zugriffsfehler bedeutet, dass der Schlüssel unter **Settings** falsch ist oder das Konto das gewählte Modell nicht nutzen kann.
- **Previous**, **Next** und **Page** blättern durch die Liste.
- **Clear history** fragt **Clear the stored history? Saved translations stay.** Danach: **History cleared. Saved translations were not changed.** Die Schaltflächenhilfe sagt **Clear history deletes these rows only. Saved translations stay.**

Eine leere Liste sagt **No requests yet.**

Wenn Übersetzungen plötzlich stoppen, öffnen Sie hier die neueste Fehlerzeile, bevor Sie das Glossar ändern.

### 3.11. Updates

Öffnen Sie **Updates** am rechten Ende der Modulleiste. Der Formulartitel ist **MyPresta Updates**.

![Updates, englisches Backoffice. Manual Check, Automatic Notifications und Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-updates.webp)

- **Manual Check** enthält **Check Now**. Es prüft die Version sofort.
- **Automatic Notifications** ist **Enabled** oder **Disabled**. **Enabled** ist der Wert, wenn die Wahl noch nie gespeichert wurde. Wenn es eingeschaltet ist, prüft das Modul, ob MyPresta eine neuere Version hat, und kann eine Warnung im Backoffice zeigen.
- **Product Page** ist ein Link, der die Kontaktseite dieses Moduls öffnet.
- **Save** speichert die Wahl. Meldung: **Update settings saved.**

Nach **Check Now**: **New version available!** oder **Module is up to date!**

### 3.12. Schaltflächen unter International → Translations

Öffnen Sie **International → Translations**. Feldschaltflächen erscheinen, wenn **Individual field buttons — International → Translations** an ist. Kontrollkästchen und die Leiste erscheinen, wenn **Individual field checkboxes — International → Translations** an ist.

Was Sie sehen:

- Eine Schaltfläche **Translate** an jedem Textfeld.
- Ein Kontrollkästchen an jedem Feld, wenn die Kästen an sind.
- Eine Leiste **ChatGPT translations**, mit **Source** (en-US oder das **Source locale** aus **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** und dem Hinweis **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** füllt die leeren Felder des aktuellen Bereichs.

Schritte:

1. Wählen Sie **Target**.
2. Kreuzen Sie die Felder an, oder drücken Sie **Check empty**.
3. Drücken Sie **Translate selected** oder **Translate empty**.
4. Warten Sie, bis die Leiste **Done** zeigt. Während der Arbeit ist der Status **Translating…** mit der Zahl. Wenn Sie nichts ankreuzen, sagt die Leiste **Tick at least one field.**
5. Prüfen Sie die gefüllten Felder. Speichern Sie die Seite mit der Schaltfläche **Save** von PrestaShop.

Die Schaltflächen füllen nur die Felder. Ohne **Save** von PrestaShop kommt der Text nicht in den Shop. Bei ausgeschaltetem **Allow publish / save** werden die Felder trotzdem gefüllt, und **Save** von PrestaShop schreibt die Seite.

Meldungen:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Bei **Emails** kommt der Quelltext aus der Mailvorlage, nicht aus dem Feld auf der Seite. Wählen Sie ein anderes **Source locale**, das diese Maildateien hat.

### 3.13. Schaltflächen an Produkt-, Kategorie- und CMS-Formularen

Öffnen Sie ein Produkt, eine Kategorie, eine CMS-Seite oder ein anderes Shop-Formular mit mehrsprachigen Feldern. Die Schaltflächen sind sichtbar, wenn **Individual field buttons — shop forms** an ist. Die Kontrollkästchen und die Leiste sind sichtbar, wenn **Individual field checkboxes — shop forms** an ist.

Was Sie sehen:

- Eine Schaltfläche **Translate** an jedem mehrsprachigen Feld.
- Ein Kontrollkästchen für die Leiste.
- Eine Leiste **ChatGPT translations**, mit **Translate from** und **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** und dem Hinweis **Fills the fields. Save with the PrestaShop button.**

Schritte:

1. Füllen Sie das Feld in der Quellsprache. Ist es leer, sagt die Leiste **Fill the source language field first.**
2. Wählen Sie die Zielsprache auf der Leiste.
3. Drücken Sie die Schaltfläche an einem Feld, oder kreuzen Sie Felder an und drücken Sie **Translate selected**. **Translate empty** füllt leere Felder.
4. Drücken Sie **Save** am PrestaShop-Formular. Ohne das wird der Text nicht gespeichert.

Die Schaltfläche füllt nur das Feld im Formular. Felder, die Sie nicht ankreuzen, bleiben unverändert.

## 4. Shop-Frontend

Das Modul fügt der Seite, die der Kunde sieht, nichts hinzu. Es gibt keinen Storefront-Block, keine Schaltfläche und keine Meldung, daher hat das Theme für dieses Modul nichts anzuzeigen.

Die einzige Adresse außerhalb des Backoffice ist die Cron-Adresse. Sie ist für einen geplanten Aufruf auf dem Server. Sie ist nicht für Kunden.

- Kopieren Sie sie aus **Settings**, **CRON URL**, oder aus der Zeile **CRON** auf dem **Dashboard**.
- Fügen Sie sie in den Server-Zeitplan ein, zum Beispiel alle paar Minuten. Jeder Aufruf verarbeitet eine Scheibe eines wartenden Auftrags.
- Verwenden Sie die Adresse `https://`, wenn der Shop SSL eingeschaltet hat.

| Was Sie beim Öffnen der Adresse sehen | Was Sie tun |
|---|---|
| **Forbidden** | Die Adresse ist unvollständig oder wurde geändert. Kopieren Sie sie erneut aus **Settings**. |
| **No pending jobs** | Es gibt keinen Auftrag in `pending` oder `running`. Legen Sie einen unter **Bulk** an, oder setzen Sie einen pausierten Auftrag unter **Jobs** fort. |
| Ein JSON-Ergebnis mit `ok`, `finished` und `counts` | Eine Scheibe wurde verarbeitet. Prüfen Sie den Fortschritt unter **Jobs**. |

Die Cron-Adresse verarbeitet nur Aufträge in `pending` und `running`. Ein Auftrag `paused` muss unter **Jobs** fortgesetzt werden.

## 5. Probleme

| Was Sie sehen | Ursache | Was Sie tun |
|---|---|---|
| **No ChatGPT API key.** auf jeder Modulseite | Kein Schlüssel ist gespeichert. | Öffnen Sie **Settings**, fügen Sie den Schlüssel unter **ChatGPT API key** ein und drücken Sie **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Die Einstellungen wurden ohne Schlüssel gespeichert. | Fügen Sie den Schlüssel ein und drücken Sie **Save**. |
| **Connection was not made. Nothing was translated.** nach **Test connection** | Falscher Schlüssel, kein Weg zu OpenAI, oder ein Modell, das das Konto nicht nutzen kann. | Prüfen Sie den Schlüssel, wählen Sie ein anderes **Model**, oder fügen Sie die richtige Kennung unter **Add a ChatGPT model** hinzu. Lesen Sie die Zeile unter **History**. |
| Zugriffsfehler unter **History** | Der Schlüssel ist falsch, oder das Konto kann das gewählte Modell nicht nutzen. | Korrigieren Sie den Schlüssel, oder wählen Sie ein Modell, das das Konto aufrufen kann. |
| **Nothing was started. There is no ChatGPT API key.** unter **Bulk** | Kein Schlüssel. | Fügen Sie den Schlüssel unter **Settings** ein, dann führen Sie **Estimate** und **Start job** erneut aus. |
| Ein Auftrag bleibt auf `pending` | Ein Auftrag startet nicht von selbst. | Drücken Sie **Process slice** oder **Auto-process** unter **Jobs**, oder richten Sie die Cron-Adresse ein (Abschnitt 4). |
| Ein Auftrag ist `paused` mit **Rate limit — job auto-paused. Resume later.** | ChatGPT hat Aufrufe wegen eines Ratenlimits abgelehnt. Die Antwort unter **History** kann auch **ChatGPT rate limit (429). Try again later.** lauten. | Warten Sie ein paar Minuten und drücken Sie **Resume**. Senken Sie **Batch size** oder **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | **Budget USD / month** wurde erreicht. | Erhöhen Sie den Betrag, oder setzen Sie 0. Ein neuer Monat beginnt bei null. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** ist aus. | Schalten Sie **Allow publish / save** ein. |
| **Not saved because of broken placeholders or HTML: N.** unter **Manual** | Die Übersetzung hat Platzhalter oder HTML-Tags verändert. | Bearbeiten Sie die Zeile in **Review before save**, damit Platzhalter und Tags zur Quelle passen, und drücken Sie **Save approved**. |
| Ein Auftrag endet als `completed_with_errors` | Einige Zeichenketten sind fehlgeschlagen. | Öffnen Sie den Auftrag, drücken Sie **Failed only**, laden Sie **Error CSV** herunter und drücken Sie **Retry failed**. |
| Eine Zeile steht unter **Review** | Der Wert liegt unter 70, die Längenprüfung ist fehlgeschlagen, oder die Platzhalter sind fehlgeschlagen. | Lesen Sie **Flags**. **Approve** oder **Reject** ändert nur die Warteschlange. Verwenden Sie **Rollback** am Auftrag, wenn der Text schon geschrieben wurde. |
| **The shop needs at least two languages.** | Der Shop hat eine Sprache. | Fügen Sie eine Sprache unter **International → Localization → Languages** hinzu und öffnen Sie das Modul erneut. |
| Schaltflächen fehlen an einem Produktformular | Die Schalter der Shop-Formulare sind aus. | Schalten Sie unter **Settings** **Individual field buttons — shop forms** ein und, wenn Sie die Leiste wollen, **Individual field checkboxes — shop forms**. |
| Die Übersetzungsseite hat keine Leiste | Die Schalter der Übersetzungsseite sind aus. | Schalten Sie die beiden Schalter **International → Translations** unter **Settings** ein. |
| **Max tokens** ändert die Länge der Antworten nicht | Die Übersetzungsanfrage sendet diese Zahl nicht. | Lassen Sie sie auf 0. Kürzen Sie ein einzelnes Ergebnis, indem Sie es vor **Save approved** bearbeiten. |
| Ein Glossar-CSV-Import hat Duplikate erzeugt | Der Import fügt Zeilen hinzu. Er ersetzt einen bereits gespeicherten Begriff nicht. | Löschen Sie die zusätzlichen Zeilen, oder exportieren Sie, bereinigen Sie die Datei, löschen Sie die alten Zeilen und importieren Sie einmal. |

## 6. Für Entwickler

### 6.1. Überblick

- Hauptklasse: `myaitranslationsgpt`, Datei `myaitranslationsgpt.php`.
- Version: 1.2.0.
- Technischer Name: `myaitranslationsgpt`. Name in der Modulliste: **AI Translations with ChatGPT**.
- Autor: MyPresta.eu. Register im Module Manager: `administration`.
- Backoffice-Register: `AdminMyaitranslationsgpt`, Elternteil `AdminInternational`, Ersatz-Elternteil `IMPROVE`. Die sichtbare Beschriftung ist `AI Translations with ChatGPT`. `ensureTab()` repariert ein fehlendes Register. `renameTabIfTechnical()` ersetzt einen Registernamen, der noch der technische Name ist.
- Installation: `parent::install()`, Tabellen aus `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (schreibt einen Schlüssel nur, wenn er fehlt), Hooks `displayBackOfficeHeader` und `actionAdminControllerSetMedia`, dann das Register.
- Deinstallation: löscht das Register, `sql/uninstall.php` (löscht 11 Tabellen), `removeConfiguration()` löscht die dort genannten Schlüssel `MYAITGPT_*`, dann `parent::uninstall()`. Es löscht nicht `mypresta_updates`, `update_myaitranslationsgpt` oder `updatev_myaitranslationsgpt`.
- Es gibt kein `enable()` und kein `disable()`.
- `getContent()` ruft `ensureTab()` auf und leitet zu `AdminMyaitranslationsgpt` um (Standardregister `dashboard`).

Datenfluss:

1. Das Einstellungsformular sendet an `AdminMyaitranslationsgptController::initContent()`.
2. `ConfigService::saveFromForm()` speichert `MYAITGPT_*` in `Configuration`. `ApiKeyEncryptor` verschlüsselt den API-Schlüssel mit AES-256-CBC. Der Schlüssel ist `hash('sha256', _COOKIE_KEY_ . '|myaitranslationsgpt|v1', true)`. Der gespeicherte Wert hat das Präfix `MYAITGPT1:`. Ein leerer gesendeter Schlüssel oder ein maskierter Wert ersetzt den gespeicherten Schlüssel nicht.
3. Übersetzung: `TranslateService::translateMessages()` baut Prompts (`PromptBuilder`), sendet sie über `OpenAiTranslationProvider` (cURL POST an `https://api.openai.com/v1/chat/completions`, Kopf `Authorization: Bearer`), prüft die Antwort (`PlaceholderValidator`, `HtmlValidator`, `PsNativeValidator`), bewertet sie (`QualityScorer`) und speichert über `TranslationAdapter`.
4. `translateBatch()` sendet `temperature` aus den Einstellungen und sendet kein `max_tokens`. Der Verbindungstest (`ping`) sendet `max_tokens` 5 und `temperature` 0. `MYAITGPT_MAX_TOKENS` wird gespeichert und von `translateBatch()` nicht gelesen.
5. Der Katalogspeicher verwendet den PrestaShop-Übersetzungsdienst, wenn er existiert, sonst die Tabelle `_DB_PREFIX_translation`. Schlüssel klassischer Module schreibt `LegacyModuleCatalogue` in `translations/{iso}.php` dieses Moduls.
6. Bulk: `BulkJobFactory` fügt `myaitgpt_job` und `myaitgpt_job_item` ein. Eine leere Domainliste erzeugt keine Positionen, außer bei einem klassischen Modul, das `LegacyModuleCatalogue::DOMAIN` verwendet. `JobWorker::processSlice()` führt eine Scheibe der Größe `BATCH_SIZE` aus. Aufgerufen von **Process slice**, von der Schleife **Auto-process** (AJAX `ProcessJob`) und von `controllers/front/cron.php`.
7. Catalog: `CatalogTranslateService::collect()` wird mit einem Limit von 100 aufgerufen. `translateAndSave()` schreibt `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` oder `_DB_PREFIX_cms_lang`. Ergebnisse werden über die ID zugeordnet. Nach dem Stapel wird **Start after ID** zur höchsten `id_entity` in der gesammelten Menge, einschließlich fehlgeschlagener Zeilen.
8. Jeder Aufruf wird in `myaitgpt_request` gespeichert (**History**). Fehler gehen auch nach `myaitgpt_api_log` (Spalte `provider` standardmäßig `openai`). Kosten gehen nach `myaitgpt_usage_ledger`. `SnapshotService` kopiert den vorherigen Wert nach `myaitgpt_snapshot` für **Rollback**. `clearTranslationCache()` ruft `Tools::clearCache()` nach einem Katalogspeicher, nach einer Scheibe, die kein Probelauf ist, und nach einem Rollback auf.

`QualityScorer` beginnt bei 100. `validation_failed` zieht 40 ab. Jede Warnung zieht 5 ab. Ein Längenverhältnis über 2,5 setzt `length_explosion` und zieht 20 ab. Ein Verhältnis unter 0,3 bei einer Quelle länger als 20 Zeichen setzt `too_short` und zieht 15 ab. Verbliebene englische Wörter the, and, with, your oder please setzen `possible_untranslated` und ziehen 10 ab. Die Zeile braucht eine Prüfung, wenn der Wert unter 70 liegt oder `validation_failed` oder `length_explosion` gesetzt ist.

### 6.2. Dateien

| Datei | Rolle |
|---|---|
| `myaitranslationsgpt.php` | Installation, Deinstallation, Register, Hooks, Assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Update-Prüfung für das Register **Updates** und die Backoffice-Warnung. Klasse `myaitranslationsgptUpdate`. |
| `logo.png`, `logo.gif` | Logo in der Modulköpfe. |
| `controllers/admin/AdminMyaitranslationsgptController.php` | Jedes Backoffice-Register, Speicherungen, Auftragsaktionen, Glossar, Ausschlüsse, Katalog, CSV, AJAX. |
| `controllers/front/cron.php` | Cron-Adresse. Verarbeitet eine Scheibe und gibt JSON zurück. |
| `sql/install.php`, `sql/uninstall.php` | Tabellen anlegen und löschen. |
| `src/Adapter/TranslationAdapterInterface.php` | Lese- und Schreibschnittstelle für PrestaShop-Übersetzungen. |
| `src/Adapter/AbstractTranslationAdapter.php` | Bereiche, Domains, Locales, Speichern über den Dienst oder die Tabelle `translation`, Cache leeren. |
| `src/Adapter/TranslationAdapter.php` | Konkreter Adapter. |
| `src/Adapter/TranslationAdapterFactory.php` | Baut den Adapter. |
| `src/Adapter/FilesystemCatalogueTrait.php` | Liest XLF-Kataloge aus Themes und Modulen. |
| `src/Adapter/LegacyModuleCatalogue.php` | Klassische Module: lesen und schreiben von `translations/{iso}.php`. |
| `src/Admin/MyaitgptForms.php` | Backoffice-Formulare und Feldtext `desc`. |
| `src/Admin/MyaitgptSectionHelp.php` | Text des Feldes **Help** für jedes Register. |
| `src/Audit/RequestLogRepository.php` | **History**: Zeilen, Karten, Diagramme, Filter, Leeren, Aufbewahrung. |
| `src/Audit/ApiLogRepository.php` | API-Fehler- und Warnprotokoll, Aufbewahrung. |
| `src/Audit/TranslationMemory.php` | Verwendet ein Ergebnis für denselben Text, dasselbe Locale, Modell und Glossar erneut. |
| `src/Audit/UsageLedger.php` | Kostenschätzung und Monatsbudget. |
| `src/Audit/SnapshotService.php` | Kopien vor einem Schreiben und Wiederherstellen bei **Rollback**. |
| `src/Glossary/GlossaryRepository.php` | Glossarliste, Einfügen, Löschen. |
| `src/Glossary/ExcludePatternRepository.php` | Ausschluss einfügen, löschen und vergleichen. |
| `src/Job/JobStatuses.php` | Statuskonstanten für Aufträge und Zeilen. |
| `src/Job/JobRepository.php` | Aufträge und Zeilen: lesen, Status, nächste Scheibe, Zähler. |
| `src/Job/JobWorker.php` | Scheibenverarbeitung, Wiederholen, Beenden, Prüfliste, Abschluss-E-Mail. |
| `src/Provider/TranslationProviderInterface.php` | Anbieterschnittstelle. |
| `src/Provider/OpenAiTranslationProvider.php` | ChatGPT-Aufrufe, Verbindungstest, Anforderungsprotokoll. |
| `src/Provider/PromptBuilder.php` | System- und Benutzerprompts: Ton, Markenstimme, Glossar. |
| `src/Provider/ProviderFactory.php` | Baut den Anbieter. |
| `src/Quality/PlaceholderValidator.php` | Prüfung von Platzhaltern und Tags. |
| `src/Quality/HtmlValidator.php` | HTML-Prüfung. |
| `src/Quality/PsNativeValidator.php` | Prüfung vor einem Speichern unter **Manual**. |
| `src/Quality/EmailHtmlPipeline.php` | Schützt Mail-HTML vor dem Aufruf und stellt es nach der Antwort wieder her. |
| `src/Quality/QualityScorer.php` | Wert 0-100, Flags, Prüfentscheidung. |
| `src/Security/ApiKeyEncryptor.php` | API-Schlüssel ver- und entschlüsseln. |
| `src/Service/ConfigService.php` | Einstellungen lesen und speichern, Modelle, Cron-Token, Bereiche. |
| `src/Service/RateLimiter.php` | Lokale Grenze pro Minute, Datei `var/rate_limit.json`. |
| `src/Service/TranslateService.php` | Ausschlüsse, Speicher, Aufrufe, Prüfung, Bewertung, Speichern, Schätzung. |
| `src/Service/BulkJobFactory.php` | Baut einen Auftrag **Bulk** und die Schätzung. |
| `src/Service/CatalogTranslateService.php` | Sammelt und speichert Zeilen von **Catalog**. |
| `src/Service/DashboardService.php` | Abdeckungszahlen auf dem **Dashboard**. |
| `translations/*.php` | Oberflächentexte, eine Datei je Sprache. |
| `views/templates/admin/configure.tpl` | Die Modulseite und die Schublade **Help**. |
| `views/templates/admin/_partials/*.tpl` | Register: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Backoffice-Stile. |
| `views/js/admin.js` | Fortschritt von **Jobs** und **Auto-process**, Zeilenauswahl, AJAX. Zeigt **Brand voice** nur, wenn **Tone** **Brand** ist, und **Notify email** nur, wenn die E-Mail-Benachrichtigung an ist. |
| `views/js/admin-help.js` | Feld **Help**. |
| `views/js/translations-tool.js` | Schaltflächen und Leiste unter **International → Translations**. |
| `views/js/entity-fields.js` | Schaltflächen und Leiste an Produkt-, Kategorie- und CMS-Formularen. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Diagramme auf dem **Dashboard**. |
| `var/rate_limit.json` | Zähler für die lokale Grenze pro Minute. |
| `index.php` in jedem Verzeichnis | Blockiert die Verzeichnisauflistung. |

### 6.3. Controller

**Backoffice: `AdminMyaitranslationsgptController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsgpt&token=…`, optional `&myaitgpt_tab=` mit `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (die Registerbeschriftung ist **History**), `settings`, `updates`.
- Auftragsaktionen, Abfrage `job_action` plus `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. Die Vorlage zeichnet keine Schaltfläche Cancel. `filter_failed=1` begrenzt die Zeilentabelle. `cancel` setzt den Auftrag auf `cancelled` und lässt wartende Zeichenketten unübersetzt. Meldung: **Job cancelled. Strings still waiting were not translated.**
- Prüfaktionen: `review_action=approve|reject` und `id_review`.
- Glossar: `delete_glossary`. Ausschlüsse: `delete_exclude`. Modelle: `delete_openai_model`, und POST `new_openai_model` mit `submitMyaitranslationsgptAddModel`.
- Glossar-CSV: `importGlossaryCsv()` überspringt die Kopfzeile und jede Zeile mit weniger als drei Spalten und fügt dann jede übrige Zeile ein. Es aktualisiert keinen vorhandenen Begriff.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, `displayAjaxTranslatePageLines`, `displayAjaxMailSource`, `displayAjaxListDomains`.

**Frontend: `MyaitranslationsgptCronModuleFrontController`** (`controllers/front/cron.php`).

- Shop-URL: `module/myaitranslationsgpt/cron`.
- Die Abfrage `token` muss `MYAITGPT_CRON_TOKEN` entsprechen (`hash_equals`). Ein fehlender oder falscher Token gibt HTTP 403 und JSON `{"ok":false,"error":"Forbidden"}` zurück.
- Optionales `id_job` verarbeitet diesen Auftrag. Ohne es wird der erste Auftrag `pending` oder `running` verarbeitet.
- Eine erfolgreiche Scheibe gibt JSON mit `ok`, `finished` und `counts` zurück. Wenn kein Auftrag wartet, ist der Körper `{"ok":true,"message":"No pending jobs"}`.
- `ssl` am Controller ist true.

### 6.4. Hooks

Registrierte Hooks:

- `displayBackOfficeHeader` - benennt eine technische Registerbeschriftung um und lädt dann CSS und JS.
- `actionAdminControllerSetMedia` - lädt dieselben Assets.

`translations-tool.js` wird am Übersetzungscontroller hinzugefügt. `entity-fields.js` wird an Shop-Formularen hinzugefügt, wenn die Feldschalter an sind. `Media::addJsDef` veröffentlicht `myaitgptTr` (Ajax-URL, Quell-Locale, Sprachen und die Leistenbeschriftungen). Die Leistenbeschriftung ist **ChatGPT translations**.

Das Modul registriert keinen eigenen Hook, den andere Module implementieren sollen. Es gibt kein `enable()` und kein `disable()`.

### 6.5. Overrides

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6. Datenbank

| Tabelle | Inhalt |
|---|---|
| `myaitgpt_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, Shop-ID, Daten. |
| `myaitgpt_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgpt_job` | Ein Sammellauf: Locales, `scope_json`, `policy_json`, `dry_run`, Zähler, Token-Summen, Kosten, Mitarbeiter, Fehler, Zeitstempel. |
| `myaitgpt_job_item` | Eine Zeichenkette eines Auftrags: Domain, Schlüssel, Theme, Locale, Quelle, vorheriger Wert, neuer Wert, Status, Überspringgrund, Fehler, Tokens, Prüfung. |
| `myaitgpt_memory` | Übersetzungsspeicher: Hash, Quelle, Locale, Übersetzung, Modell, Trefferzahl. |
| `myaitgpt_usage_ledger` | Tägliche Token- und Kostenzeilen, optionale Auftrags-ID, Modell. |
| `myaitgpt_snapshot` | Wert vor einem Auftragsschreiben, verwendet von **Rollback**. |
| `myaitgpt_api_log` | Fehler- und Warnzeilen: Stufe, Anbieter (Standard `openai`), HTTP-Code, Meldung, Kontext. |
| `myaitgpt_request` | Zeilen von **History**: Typ, Status, Modell, Locales, HTTP-Code, Dauer, Tokens, Kosten, Mitarbeiter, Auftrag, Prompt, Antwort, Fehler. |
| `myaitgpt_review` | Prüfliste: Auftragsposition, Status, Wert, Flags, Mitarbeiter. |
| `myaitgpt_catalog_item` | Katalogstapelzeilen: Entität, Feld, Sprachen, Quelle, vorher, neu, Status, Fehler. |

Die Deinstallation löscht alle elf Tabellen. Die Installation verwendet `CREATE TABLE IF NOT EXISTS`, daher behält eine Neuinstallation auf einer Datenbank, die die Tabellen noch hat, diese Zeilen. Eine normale Deinstallation entfernt sie zuerst. Beim ersten Besuch einer Seite wird keine Spalte hinzugefügt.

### 6.7. Schlüssel und Übersetzungen

Präfix `MYAITGPT_`. Werte, wenn der Schlüssel fehlt, das ist auch der bei der Installation geschriebene Wert:

| Schlüssel | Wenn er fehlt |
|---|---|
| `API_KEY_ENC` | leer |
| `MODEL` | `gpt-4.1-mini` |
| `EXTRA_MODELS` | leer |
| `PROVIDER` | `openai` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | leer |
| `BATCH_SIZE` | `25` (beim Speichern erneut auf 1-100 begrenzt) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | leer |
| `TEMPERATURE` | `0.2` (beim Speichern erneut auf 0-1 begrenzt) |
| `DRY_RUN_SAMPLE` | `10` (beim Speichern erneut auf 1-50 begrenzt) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (Minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | leer |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (nur gespeichert; `translateBatch()` sendet ihn nicht) |
| `CRON_TOKEN` | 16 zufällige Bytes als Hex, bei der Installation erzeugt |

`removeConfiguration()` löscht auch die Restnamen `DEEPL_API_KEY` und `CLAUDE_API_KEY` unter demselben Präfix. Es löscht die Schlüssel der Update-Prüfung nicht.

Feldbeschreibungen sind die Zeichenketten `desc` in `src/Admin/MyaitgptForms.php`, gebaut von `help()` als Zweck, Einstellung und Wirkung. Die Hilfe zu **Max tokens** sagt, 0 für den ChatGPT-Standard zu lassen. Die Anfrage ignoriert den gespeicherten Wert. Die Registerhilfe ist `src/Admin/MyaitgptSectionHelp.php`.

Oberflächentexte gehen über `$this->l()` / `{l s=... mod='myaitranslationsgpt'}`. Eine Sprache fügen Sie mit `translations/{iso}.php` hinzu. Der Auftragsfehler **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No ChatGPT API key. Nothing was translated.** und **Monthly API budget has been exhausted.** sind englische Zeichenketten aus `JobWorker` und `TranslateService`, keine Aufrufe von `$this->l()`. Die Texte von **Updates** verwenden die Übersetzungsdomain `updatechecker`. `OpenAiTranslationProvider` gibt bei HTTP 429 **ChatGPT rate limit (429). Try again later.** zurück.

### 6.8. Erweitern

Das Frontend rendert keine Modulvorlage, daher hat das Theme nichts zu überschreiben.

Backoffice-Vorlagen liegen in `views/templates/admin/`. PrestaShop bietet keine Theme-Überschreibung für diese Admin-Vorlagen. Beschriftungen ändern Sie über `translations/{iso}.php`. Die Schaltflächen unter **International → Translations** und an Shop-Formularen werden von `views/js/translations-tool.js` und `views/js/entity-fields.js` aus `myaitgptTr` eingefügt. Es gibt keinen Hook, mit dem ein Theme diese Leiste ersetzen kann.

## 7. Hilfe

Modulseite: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html

Um zu diesem Modul zu schreiben, melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an, öffnen Sie das Kontaktformular und wählen Sie **Support for paid modules**. Das Formular sagt, dass für kostenpflichtige Module eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.
