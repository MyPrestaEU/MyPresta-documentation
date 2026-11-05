---
title: "My AI DeepSeek - AI content generation - Dokumentation und Benutzerhandbuch"
description: "Handbuch für Einrichtung, tägliche Nutzung und Fehlerbehebung für Shopbetreiber, die das Modul My AI DeepSeek bereits in PrestaShop installiert haben."
sidebar:
  label: "My AI DeepSeek - AI content generation - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul SEO meta and catalog descriptions with DeepSeek AI auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai/)
>
> ---


## 1. Voraussetzungen

Das Modul schreibt Katalogtexte über den Dienst DeepSeek. Ihr Shop benötigt daher eine funktionierende Verbindung zu DeepSeek und ein eigenes DeepSeek-Konto.

- **PrestaShop:** Versionen 1.6 bis 9.99.99.
- **PHP:** 7.0 oder neuer. Bei einer älteren PHP-Version wird die Installation mit einer Meldung abgelehnt, die die erforderliche und die erkannte Version nennt.
- **PHP-Erweiterung:** cURL. Der Shop-Server muss ausgehende HTTPS-Verbindungen zu `https://api.deepseek.com/v1` öffnen können. Wenn Ihr Hoster ausgehende Verbindungen blockiert, bitten Sie den Hoster, sie zu erlauben.
- **Andere Module:** keine. Das Modul hängt von keinem anderen Modul ab.
- **DeepSeek-Konto:** Sie benötigen einen API-Schlüssel. Erstellen Sie ihn unter https://platform.deepseek.com/api_keys. Die Nutzung wird von DeepSeek Ihrem Konto in Rechnung gestellt, nicht von MyPresta.eu.
- **Sprache des Back Office:** In diesem Handbuch werden die Bildschirme auf Englisch gezeigt, und die Screenshots stammen aus dem englischen Back Office. Die fett gedruckten Namen sind die Namen, die Sie auf dem Bildschirm sehen.
- **Große Kataloge:** Jedes generierte Feld ist eine Anfrage an DeepSeek und dauert einige Sekunden. Ein Durchlauf über Hunderte Produkte dauert lange, und der Browser-Tab muss auf den Generate-Bildschirmen während des gesamten Durchlaufs geöffnet bleiben. Bei großen Katalogen bevorzugen Sie den Cron-Bildschirm, der im Hintergrund in kleinen Stapeln arbeitet.

## 2. Installation

### 2.1 Hochladen und installieren

1. Öffnen Sie **Modules**, dann **Module Manager**.
2. Klicken Sie auf **Upload a module** und wählen Sie die ZIP-Datei aus. Entpacken Sie sie vorher nicht.
3. Wenn der Upload beendet ist, klicken Sie auf **Install** (falls die Schaltfläche angezeigt wird) und dann auf **Configure**.

Die Installation speichert Standardeinstellungen, legt die Modultabellen an, fügt 16 vorgefertigte Prompt-Vorlagen hinzu und trägt das Modul in das Menü des Back Office ein.

### 2.2 Was im Menü erscheint

Ein neuer Menüeintrag **AI Content Generator** wird hinzugefügt. Seine erste Seite ist **Dashboard**. Innerhalb des Moduls wechseln Sie mit der Navigationsleiste am oberen Rand jeder Seite zwischen den Bildschirmen:

| Navigationspunkt | Was er öffnet |
|---|---|
| **Dashboard** | Diagramme zu Anfragen, Fehlern und Tokens. |
| **Settings** | Fünf Bereiche: **General**, **DeepSeek**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Zwei Listen: **Products** und **Categories**. |
| **New product** | Erstellt aus einer kurzen Beschreibung einen Produktentwurf. |
| **Cron** | Erstellt Adressen für geplante Aufgaben für Produkte und Kategorien. |
| **History** | Jede Anfrage mit Prompt, Antwort, Status und Tokens. |
| **Images** | Schalter und Prompt der Produktfoto-Suche. |
| **Updates** | Prüft, ob eine neuere Version veröffentlicht ist. |

Wenn Sie mit der Maus über einen Navigationspunkt fahren, erscheint ein kurzer Hinweis in der Form What it does / How to configure / Effect.

### 2.3 Cache

Die Installation leert den PrestaShop-Cache nicht. Wenn der Eintrag **AI Content Generator** nach der ersten Installation im Menü fehlt, leeren Sie den Cache unter **Advanced Parameters**, **Performance** und laden Sie das Back Office neu.

### 2.4 Deinstallation und Neuinstallation

- **Entfernt:** der Menüeintrag, die Liste der Prompt-Vorlagen, die Tabelle History mit allen Zeilen und die Haupteinstellungen des Moduls, einschließlich des API-Schlüssels.
- **Beibehalten:** jeder bereits in Produkte und Kategorien geschriebene Text. Das Modul entfernt niemals Katalogtexte.
- **Mögliche Reste:** Einige gespeicherte Filterwerte der Generate-Bildschirme können in der Shop-Konfiguration verbleiben. Sie schaden nicht.
- **Neuinstallation:** Eine Neuinstallation beginnt mit den Standardwerten. Prompt-Vorlagen, History und der API-Schlüssel sind dann weg. Notieren Sie sich daher Ihre eigenen Vorlagen und Ihre Studio-Regeln, bevor Sie deinstallieren.

## 3. Konfiguration und tägliche Arbeit im Back Office

### 3.1 Der gesamte Ablauf im Überblick

Das Modul hat keine Schritte auf der Kundenseite. Ihre Mitarbeiter starten jede Aktion im Back Office.

1. **Einmalig:** Fügen Sie den DeepSeek-API-Schlüssel ein und wählen Sie unter **Settings**, **DeepSeek** ein Modell. Optional füllen Sie **Studio** aus (Markenstimme, verbotene Wörter, Monatslimit).
2. **Einzelnes Produkt:** Öffnen Sie ein Produkt und gehen Sie zum Tab **Modules**, **My AI DeepSeek**. Mit **Generate** schreiben Sie Felder, mit **Simulate** probieren Sie zuerst aus, mit **Photos** finden Sie Bilder und mit **History** stellen Sie älteren Text wieder her.
3. **Viele Produkte oder Kategorien:** Öffnen Sie **Generate**, filtern Sie die Liste, wählen Sie einen Prompt und einen Umfang und drücken Sie **Run**. Jede Zeile zeigt ihr eigenes Ergebnis, sobald sie fertig ist.
4. **Unbeaufsichtigt:** Öffnen Sie **Cron**, speichern Sie eine Stapeldefinition, kopieren Sie die Adresse und geben Sie sie an den Scheduler des Servers weiter.
5. **Kontrolle:** **History** zeigt jede Anfrage. **Dashboard** zeigt Summen. Nichts geht verloren: Der vorherige Text jedes geschriebenen Feldes bleibt erhalten und kann am Produkt mit **Restore** wiederhergestellt werden.
6. **Neues Produkt aus einer Idee:** **New product** erstellt einen Entwurf und, nachdem Sie ihn akzeptiert haben, ein echtes Produkt.

Jede Anfrage wird in **History** mit dem Status **Success** oder **Error** gespeichert. Eine Antwort, die gegen die Liste **Forbidden words** verstößt oder eintrifft, nachdem das **Monthly generation budget** aufgebraucht ist, wird nicht in das Produkt geschrieben.

![Dashboard](https://mypresta.eu/docs/images/docs/myaideepseek-dashboard.webp)

### 3.2 Dashboard

Öffnen Sie **AI Content Generator**, dann **Dashboard**. Die Seite stellt die in **History** gespeicherten DeepSeek-Anfragen, Tokens und Fehler für den gewählten Zeitraum in Diagrammen dar. Von dieser Seite aus wird im Katalog nichts generiert oder geändert.

| Element | Startwert | Was es tut |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | das Modul öffnet sich mit einem Standardzeitraum | Schnelle Datumsbereiche. Klicken Sie auf einen, um die Seite neu zu zeichnen. |
| **From** / **To** und **Apply** | leer | Ihr eigener Zeitraum. Die Karten und Diagramme folgen ihm. |
| Zeile **Active service** | – | Zeigt, welchen Dienst das Modul verwendet. |
| Karten **Requests**, **Errors**, **Tokens sent**, **Tokens received** | – | Anzahl der gespeicherten Aufrufe, der fehlgeschlagenen Aufrufe, Größe der Prompts und Größe der Antworten innerhalb des Zeitraums. |
| Diagramme **Requests and errors**, **Tokens sent and received**, **Requests by model** | – | Tageskurven und eine Aufteilung nach Modell. |

Die Seite erscheint außerdem als kleiner Block auf dem Standard-**Dashboard** von PrestaShop mit Schnellzugriffen auf **Generate**, **History** und **Cron**.

### 3.3 Settings – General

Öffnen Sie **Settings**, dann **General**. Diese Schalter bestimmen, wie lange ein Aufruf laufen darf und welche Werkzeuge die Mitarbeiter sehen. Das Speichern an dieser Stelle ändert keinen Produkttext.

![Settings – General](https://mypresta.eu/docs/images/docs/myaideepseek-settings-general.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Live mode** | Disabled | Kennzeichnet das Modul als im echten Shop laufend und nicht in einer Testumgebung. Aktivieren Sie ihn im Produktivshop. Auf einer Staging-Kopie lassen Sie ihn deaktiviert, wenn Mitarbeiter die Werkzeuge nicht als einsatzbereit ansehen sollen. Die Werkzeuge arbeiten in beiden Zuständen gleich. |
| **Debug mode** | Disabled | Schreibt zusätzliche Diagnosedetails, wenn ein DeepSeek-Aufruf fehlschlägt. Schalten Sie ihn nur ein, solange Sie einen Fehler untersuchen, und danach wieder aus. Technische Meldungen gehen in das PrestaShop-Log. Kunden sehen sie nie. |
| **API timeout (seconds)** | 120 | Wie viele Sekunden ein Aufruf an DeepSeek laufen darf, bevor das Modul aufgibt. Verwenden Sie 120 für normale Beschreibungen. Erhöhen Sie den Wert in Richtung 600 für lange SEO-Pakete oder das Reasoning-Modell. Gehen Sie nicht unter 10. Ein kurzes Timeout schlägt schnell fehl und schreibt einen Fehler in History. Ein langes Timeout wartet auf eine langsame Antwort. |
| **Product Edit History** | Enabled | Zeigt frühere KI-Schreibvorgänge auf der Produktseite, damit ein Redakteur einen alten Wert zurücksetzen kann. Deaktiviert blendet diese Liste aus. Frühere Zeilen bleiben in beiden Fällen in **History**. |
| **Admin Top Bar CTA** | Enabled | Fügt in der oberen Leiste des Back Office eine Verknüpfung hinzu, die den Generator auf jeder Seite öffnet. Deaktiviert entfernt nur diese Schaltfläche. Das Modulmenü bleibt. |
| **Product edit page Form** | Enabled | Zeigt das Generator-Panel und die Schaltflächen Generate with AI auf der Produktbearbeitungsseite (PrestaShop 1.7, 8 und 9). Deaktivieren Sie es, wenn nur die Massengenerierung und Cron genutzt werden sollen. |
| **AI Image Finder** | Enabled | Lässt einen Redakteur das Modell nach Seiten fragen, die wahrscheinlich Fotos des aktuellen Produkts enthalten. Es wird nichts heruntergeladen, bevor jemand ein Bild bestätigt. Deaktiviert blendet die Suche aus, und der Tab **Photos** erklärt dann, wie Sie sie einschalten. |
| **AI Image Search Prompt** | vorgefertigte englische Anweisung | Die Anweisung, die gesendet wird, wenn jemand nach Produktbildern sucht. Produktname und Produktbeschreibung werden für das aktuelle Produkt eingesetzt. Behalten Sie die Bitte um eine Liste von Seitenadressen bei. Ein genauerer Prompt liefert relevantere Seiten. |

Drücken Sie **Save**. Es erscheint eine grüne Bestätigung. Dieselben beiden Bildfelder gibt es unter **Images**.

### 3.4 Settings – DeepSeek

Öffnen Sie **Settings**, dann **DeepSeek**. Dies sind das Konto und die Sampling-Parameter, die jede Generierung verwendet: die Produktschaltflächen, Massenläufe, Cron und der Playground.

![Settings – DeepSeek](https://mypresta.eu/docs/images/docs/myaideepseek-settings-deepseek.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **DeepSeek API KEY** | leer | Das Geheimnis, mit dem dieser Shop Ihr DeepSeek-Konto aufrufen darf. Fügen Sie den Schlüssel von https://platform.deepseek.com/api_keys ein. Leerzeichen werden beim Speichern entfernt (Sie sehen einen Hinweis, dass der Schlüssel bereinigt wurde). Lassen Sie das Feld unberührt, um den gespeicherten Schlüssel zu behalten. Ein leerer oder falscher Schlüssel lässt Aufrufe fehlschlagen, und der Fehler wird in History geschrieben. |
| **Model** | `deepseek-chat` | Das Modell, das den Text schreibt. Eingebaute Modelle: `deepseek-chat` (schnell, die normale Wahl) und `deepseek-reasoner` (Reasoning-Modell, langsamer). Von Ihnen hinzugefügte Modelle werden ebenfalls angezeigt. Die nächste Generierung verwendet das ausgewählte Modell. Ein Modell, das Ihr Schlüssel nicht nutzen kann, liefert statt Text einen API-Fehler. |
| **Add a DeepSeek model** | leere Zeile | Geben Sie eine Modell-ID ein und drücken Sie die Schaltfläche zum Hinzufügen in dieser Zeile. Sie sehen **Model added.** Eingebaute Modelle lassen sich nicht entfernen (**Built-in models cannot be removed.**). Ein Modell, das bereits eingebaut ist, antwortet mit **That model is already built in.** Von Ihnen hinzugefügte Modelle können in derselben Zeile entfernt werden (**Model removed.**). |
| **Max Tokens** | 3200 | Obergrenze der Antwortlänge, gezählt in Tokens statt in Wörtern. Verwenden Sie etwa 256 für eine Meta-Beschreibung und 1000 oder mehr für eine vollständige HTML-Beschreibung. Ein niedriges Limit schneidet die Antwort ab. Ein hohes Limit erlaubt längeren Text und kostet mehr. Bei `deepseek-reasoner` wird ein Teil des Limits für das Reasoning verbraucht, geben Sie daher einen größeren Wert an. |
| **Temperature** | 0.7 | Wie frei das Modell Wörter wählt. Bleiben Sie zwischen 0 und 1. Verwenden Sie etwa 0.2 für Spezifikationen und Meta-Texte und etwa 0.7 für Beschreibungen. Ändern Sie Temperature oder Top P, nicht beide. |
| **Top P** | 1 | Eine andere Möglichkeit, zu begrenzen, wie überraschend das nächste Wort sein kann. Lassen Sie 1, wenn Sie bereits Temperature gesetzt haben. Ein niedrigerer Wert wie 0.9 ergibt einen engeren Wortschatz. |
| **Frequency Penalty Value** | 0 | Verringert Zeilen, die dieselbe Formulierung innerhalb einer Antwort wiederholen. Probieren Sie 0.3 bis 0.6 nur, wenn Beschreibungen immer wieder einen Satz kopieren. Bereich –2 bis 2. |
| **Presence Penalty Value** | 0 | Drängt die Antwort zu neuen Themen. Verwenden Sie standardmäßig 0. Eine kleine positive Zahl hilft, wenn jeder Absatz denselben Punkt wiederholt. Bereich –2 bis 2. |

Drücken Sie **Save**. Die Sampling-Felder ändern nicht, welche Produkte aktualisiert werden.

> Das Reasoning-Modell kann Temperature, Top P und die beiden Penalties ignorieren. Wenn eine Änderung dieser Felder mit `deepseek-reasoner` keine sichtbare Wirkung hat, wechseln Sie zu `deepseek-chat`.

### 3.5 Settings – Studio

Öffnen Sie **Settings**, dann **Studio**. Studio legt Ihre Hausregeln über jeden Prompt: die Produktschaltflächen, Massenläufe und Cron. Leere Felder werden übersprungen. Bereits im Katalog gespeicherter Text wird nicht neu geschrieben, wenn Sie eine Regel ändern.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaideepseek-settings-studio.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **Brand voice** | leer | Sagt dem Modell, wer spricht, damit der Produkttext zu Ihrem Shop passt und nicht zu einem allgemeinen Assistenten. Schreiben Sie eine kurze Vorgabe, zum Beispiel: Fachwerkstatt, kurze Sätze, keine Übertreibung. |
| **Audience** | leer | Benennt den Leser, für den der Text geschrieben wird, zum Beispiel professionelle Installateure oder Erstkäufer. |
| **Tone** | leer | Legt die Stimmung fest: formell, warm, technisch und so weiter. Ein oder zwei Wörter genügen. Es ändert weder das Modell noch die Temperatur. |
| **Glossary** | leer | Markennamen, Materialien und Schreibweisen, die das Modell genau übernehmen muss. Ein Begriff pro Zeile. Nicht aufgeführte Begriffe können weiterhin umformuliert werden. |
| **Forbidden words** | leer | Wörter und Wendungen, die in einer gespeicherten Antwort nicht vorkommen dürfen. Eines pro Zeile. Wird nur verwendet, wenn **Quality gate** aktiviert ist. Eine Antwort, die eine aufgeführte Zeile enthält, wird abgelehnt und nicht in das Produkt geschrieben. Der Versuch bleibt in History als Fehler. |
| **Monthly generation budget** | 0 | Begrenzt, wie viele erfolgreiche Generierungen der Shop im laufenden Kalendermonat ausführen darf. Geben Sie eine ganze Zahl ein. 0 bedeutet kein Limit. Der Zähler beginnt am ersten Tag des Monats von vorn. Nach Erreichen der Grenze sehen Sie **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Fehlgeschlagene Aufrufe werden nicht gezählt. |
| **Quality gate** | Enabled | Prüft die Antwort des Modells gegen **Forbidden words**, bevor etwas gespeichert wird. Aktiviert blockiert eine passende Antwort. Deaktiviert speichert sie, auch wenn sie ein aufgeführtes Wort enthält. |

Drücken Sie **Save studio**. Sie sehen **Studio settings saved.**

### 3.6 Settings – Prompt templates

Öffnen Sie **Settings**, dann **Prompt templates**. Eine Vorlage ist eine gespeicherte Anweisung. Redakteure wählen sie aus, statt jedes Mal dieselbe Vorgabe neu zu tippen. Nur aktivierte Vorlagen werden auf der Produktseite, in der Massengenerierung und in Cron angeboten.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaideepseek-settings-templates.webp)

Die Installation fügt **16 Vorlagen** hinzu: Product name 1 und 2; Product description 1 bis 7 (Nummer 7 verwendet die Produktbilder); Product meta title 1 bis 3; Product meta description 1 bis 3; Product tags.

**Listenspalten:** ID, **Title**, **Prompt**, **Status** (klicken Sie auf das Häkchen, um zwischen Enabled/Disabled umzuschalten), **Timestamp**. Zeilenaktionen: **Edit** und **Delete**. Sammelaktion: **Delete** für die markierten Zeilen (Bestätigung: *Are you sure you want to delete the selected prompts?*).

Verwenden Sie die Schaltfläche **+** in der Listenkopfzeile, um eine Vorlage zu erstellen. Das Formular **Generate Prompt Template** hat diese Felder:

| Feld | Startwert | Was es tut |
|---|---|---|
| **Status** | Schalter Enabled / Disabled | Zeigt oder verbirgt die Vorlage in den Listen, die auf der Produktseite, in der Massengenerierung und in Cron verwendet werden. Deaktivieren Sie einen Entwurf, statt ihn zu löschen. |
| **Prompt title** | leer (erforderlich) | Der Name, den Redakteure in der Vorlagenliste sehen, zum Beispiel HTML description with features. Er wird nicht an das Modell gesendet. |
| **Prompt content** | leer (erforderlich) | Die Anweisung, die an das Modell gesendet wird. Schreiben Sie sie so, wie Sie einen Texter briefen würden, und nennen Sie Länge, HTML und Sprache, wenn sie wichtig sind. Sie können die Platzhalter `{product_name}`, `{product_brand}`, `{product_features}` und `{product_tags}` verwenden. Sie werden durch das Produkt ersetzt, für das Sie generieren. |

Drücken Sie **Save Prompt**. Meldungen: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Ist das Formular unvollständig, sehen Sie **Failed to edit prompt template! Please fill the form with the right informations!** Die Schaltfläche **Go Back to Module Settings** führt zur Liste zurück.

Schreiben Sie Kategorievorlagen ohne Produktplatzhalter. Die Kategorie-Bildschirme setzen sie nicht ein.

### 3.7 Settings – Playground

Öffnen Sie **Settings**, dann **Playground**. Es ist ein Notizblock, der das aktive Modell aufruft und die Antwort unter der Schaltfläche ausgibt. Kein Produkt, keine Kategorie und kein Meta-Feld wird geändert.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaideepseek-settings-playground.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| Großes Textfeld (**Ask the model anything about your catalog**) | leer | Die Anweisung für diesen einen Aufruf. Schreiben Sie sie in einfacher Sprache. Sie können den Shopnamen, die Shopadresse, einen Produktnamen, eine Referenz oder Produktmerkmale nennen, wenn die Antwort auf Katalogdaten beruhen soll. Ihre Studio-Regeln werden ebenfalls hinzugefügt. |
| **Generate** | – | Sendet die Anweisung. Die Antwort erscheint unter der Schaltfläche. |

### 3.8 Generate – Products

Öffnen Sie **Generate**, dann **Products**. Dies ist ein zweistufiger Bildschirm. Der erste Schritt erstellt nur eine Liste. Es wird nichts an DeepSeek gesendet, bis Sie im zweiten Schritt **Run** drücken.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaideepseek-generate-products.webp)

**Schritt 1 – Filter products to update.** Die Filter werden nicht als Shop-Einstellungen gespeichert. Leere Filter schränken die Liste nicht ein.

| Feld | Startwert | Was es tut |
|---|---|---|
| **Product Categories** | keine markiert | Behält Produkte aus den markierten Kategorien. Ein leerer Baum lässt diesen Filter aus. |
| **Brand** | erste (leere) Option | Behält Produkte eines Herstellers. |
| **Product status** | – | **Active** (im Verkauf), **Disabled** (Entwürfe) oder **Both**. |
| **Product stock** | – | **Only in stock products** entfernt Produkte ohne Menge. **All products** ignoriert den Lagerbestand. |
| **Update only** | – | Nutzt den Generierungsverlauf: Produkte, die dieses Modul nie geschrieben hat, bereits geschriebene Produkte oder **Update all**. Verwenden Sie "not yet updated" für einen ersten Durchgang und "already updated" zum Neuschreiben. |
| **Product IDs** | leer | Produktnummern, durch Kommas getrennt, zum Beispiel 12,45,103. |
| **Product Reference** | leer | Ein oder mehrere Referenzcodes, durch Kommas getrennt. |
| **Product Add Date From** / **Product Add Date To** | leer | Zeitraum des Erstellungsdatums. Leer bedeutet auf dieser Seite keine Begrenzung. |
| **Minimum product ID** / **Maximum product ID** | leer | Niedrigste und höchste einzubeziehende Produktnummer. |
| **Product Limit** | leer | Begrenzt, wie viele Produkte in die Liste geladen werden. Verwenden Sie bei einem großen Katalog eine kleine Zahl wie 20, damit ein Durchlauf nicht versehentlich den ganzen Katalog durchläuft. |

Drücken Sie **Go to next step**. Die Schaltfläche **Module settings** führt zu den Moduleinstellungen zurück.

**Schritt 2 – Run.** Sie sehen **Mass product generation** mit der Tabelle der gefilterten Produkte (Spalten **ID**, **Reference**, **Result**).

| Feld | Startwert | Was es tut |
|---|---|---|
| **Template** | **Choose a template** | Füllt das Prompt-Feld aus einer aktivierten Vorlage. Lassen Sie die erste Option stehen und tippen Sie Ihren eigenen Prompt, wenn Sie das bevorzugen. Der Titel selbst wird nicht gesendet. |
| Prompt-Feld | leer | Der Text, der für jede Zeile gesendet wird. Produktplatzhalter werden pro Zeile ersetzt. |
| **What to generate** | **Descriptions** | **Descriptions** schreibt die lange und die kurze Beschreibung. **Meta title and meta description** schreibt beide Meta-Felder. **Descriptions and meta together** schreibt alle vier. Jedes Feld ist eine eigene Anfrage. Andere Felder bleiben unverändert. |
| **Existing text** | **Replace** | **Replace** überschreibt. **Skip if filled** behält gefüllte Felder und ruft DeepSeek für sie nicht auf. **Add above** und **Add below** behalten den alten Text und hängen den neuen an. |
| **Languages** | die Sprache Ihres Back Office, markiert | Markieren Sie jede gewünschte Sprache. Nicht markierte Sprachen behalten ihren Text. Jede markierte Sprache wird gesondert generiert. |
| **Run on the list below** | – | Startet den Durchlauf. Jede Zeile zeigt ihr Ergebnis, sobald das jeweilige Produkt fertig ist. Produkte außerhalb des Filters bleiben unberührt. |

Lassen Sie den Browser-Tab geöffnet, bis jede Zeile ein Ergebnis zeigt. Eine fehlgeschlagene Zeile zeigt den Grund; die anderen Zeilen laufen weiter.

### 3.9 Generate – Categories

Öffnen Sie **Generate**, dann **Categories**. Der Bildschirm funktioniert wie der Produktbildschirm, mit weniger Filtern.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaideepseek-generate-categories.webp)

**Schritt 1 – Filter categories to update.**

| Feld | Startwert | Was es tut |
|---|---|---|
| **Categories** | keine markiert | Die in der Liste angebotenen Kategorien. Lassen Sie den Baum leer, um jede Kategorie einzubeziehen, die zum Status passt. |
| **Category status** | – | **Active**, **Disabled** oder **Both**. |

Drücken Sie **Go to next step**.

**Schritt 2 – Mass category generation.**

| Feld | Startwert | Was es tut |
|---|---|---|
| Prompt-Feld | leer | Die Anweisung, die für jede Kategorie gesendet wird. Beschreiben Sie Ton, Länge und HTML. Produktplatzhalter sind hier nicht verfügbar. |
| Feldauswahl | **Description** | Das eine Feld, das dieser Durchlauf schreibt: **Description**, **Name**, **Meta title**, **Meta description** oder **Additional description**. |
| Existing data | **Replace** | **Replace** überschreibt. **Skip if filled** schützt gefüllte Felder und ruft DeepSeek für diese Kategorie nicht auf. |
| **Language** | Ihre Back-Office-Sprache | Eine Sprache pro Durchlauf. Führen Sie ihn für eine andere Sprache erneut aus. |
| **Run on the categories below** | – | Startet den Durchlauf. Die Tabelle zeigt **ID** und **Result** pro Kategorie. |

### 3.10 New product

Öffnen Sie **New product**. Der Bildschirm macht aus einer kurzen Beschreibung einen Produktentwurf und kann dieses Produkt in den Katalog einfügen.

![New product](https://mypresta.eu/docs/images/docs/myaideepseek-new-product.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **What is the product?** | leer | Die Beschreibung, die das Modell zu Name, Beschreibungen, Meta-Feldern, Tags, Merkmalen, Referenz und Preis ausbaut. Einige Sätze mit Materialien, Zielgruppe und beizubehaltenden Namen ergeben einen genaueren Entwurf. Ein leeres Feld wird abgelehnt. |
| **Optional source URL** | leer | Eine öffentliche Seite (http oder https), die das Produkt beschreibt. Ihr Text wird als Kontext hinzugefügt. Ein leeres Feld oder eine Seite, die der Shop nicht lesen kann, wird ignoriert. |
| **Language** | Ihre Back-Office-Sprache | Die Sprache, in der Name, Beschreibungen, Meta und Tags gespeichert werden. Andere Sprachen werden hier nicht gefüllt. |
| **Default category ID** | 2 | Die Nummer der Kategorie aus **Catalog**, **Categories**. 2 ist normalerweise Home. Das neue Produkt wird dort platziert. |
| **Generate data** | – | Zeigt den Entwurf als Text. Es wird kein Produkt gespeichert. |
| **Create product** | – | Fügt ein **aktives** Produkt in dieser Sprache und Kategorie hinzu, mit Name, Beschreibungen, Meta, Tags, Merkmalen, Preis und einer Lagermenge aus dem Entwurf. |

Wenn kein Schlüssel gespeichert ist, sehen Sie **Add an API key in the module settings first.** Prüfen Sie Entwurf, Preis und Lagerbestand, bevor Sie verkaufen: Der Entwurf wird von einem Modell geschrieben.

### 3.11 Cron

Öffnen Sie **Cron**. Die Seite erstellt Adressen, die der Scheduler des Servers aufruft. Jeder Aufruf füllt **einen Stapel** und endet. Der Shop tut nichts, bis Ihr Server die Adresse anfordert.

![Cron](https://mypresta.eu/docs/images/docs/myaideepseek-cron.webp)

Die Seite hat zwei Formulare: **CRON JOB Settings – Generate product content using DeepSeek** und das entsprechende Formular für Kategorien. Sie können beliebig viele Befehlsvarianten anlegen, eine pro Feld.

**Cron-Formular für Produkte**

| Feld | Startwert | Was es tut |
|---|---|---|
| **Enable Cron Feature** | No | Ein Schalter für den ganzen Shop (Produkte und Kategorien). Schalten Sie ihn erst ein, nachdem das Geheimnis, das Feld, die Sprache und der Prompt unten gespeichert sind. Der Server muss die Adresse trotzdem aufrufen. |
| **Cron Job Secret Token** | generiert | Ein langes Passwort, das Teil der Produktadresse sein muss. Ohne es lehnt der Shop den Aufruf ab. Behalten Sie den nach der Installation angezeigten Wert. Wenn Sie ihn ersetzen, kopieren Sie sofort die neue Adresse in den Scheduler des Servers. Die Schaltfläche **Generate Token** im Formular füllt unter Umständen keinen neuen Wert ein; tippen Sie selbst eine lange Zufallszeichenfolge, wenn Sie den Wert erneuern müssen. |
| **Update Field** | description | Das einzelne Produktfeld, das dieser Befehl neu schreibt: name, description, short description, meta title, meta description oder tags. Um mehrere Felder zu füllen, legen Sie mehrere Befehle an. |
| **Selected Products** | pendingDeepSeek | Welche Produkte noch warten. **pendingDeepSeek**: Produkte, die dieses Modul nie bearbeitet hat (beliebiges Feld). **pendingField**: Produkte, für die dieses Feld noch nicht generiert wurde, für mehrere Befehle über dieselben Produkte. **emptyField**: nur Produkte, deren Feld leer ist. |
| **Product Categories** | keine markiert | Beschränkt den Durchlauf auf die markierten Kategorien. Leer bedeutet, dass die Kategorie kein Filter ist. |
| **Product ID list** | leer | Nur diese Produktnummern, durch Kommas getrennt. Buchstaben werden beim Speichern entfernt. |
| **Language** | Standardsprache des Shops | Eine Sprache pro Befehl. Andere Sprachen brauchen einen eigenen Befehl. |
| **Product to update** | 5 products | Stapelgröße pro Aufruf, von 2 bis 1000. Beginnen Sie mit 5 oder 10, damit ein langsames Modell das Zeitlimit des Servers nicht erreicht. |
| **Prompt Template** | none | Eine aktivierte Vorlage. Jedes Produkt im Durchlauf wird nach dieser Vorgabe geschrieben. |
| **Enable Debug** | No | **Yes** gibt den Plan aus, wenn Sie die Adresse im Browser öffnen, und speichert nichts. Setzen Sie **No**, bevor der Scheduler sie verwendet. |
| **CRON JOB interval** | Every Hour | Nur ein Vorschlag, der zum Erstellen des Befehlstexts dient (von **Every 1 Minute** bis **Every 6 Hours**). Das Modul startet keinen Scheduler. |
| **Product Cron Job command** | – | Der fertige Befehl zum Kopieren. Speichern Sie zuerst das Formular. |

Das **Cron-Formular für Kategorien** hat eigene Felder **Cron Job Secret Token**, **Update Field** (name, description, meta title, meta description), **Selected categories** (dieselben drei Regeln), **Language**, **Categories to update** (Stapelgröße), **Prompt Template** (schreiben Sie die Vorgabe für eine Kategorie), **Enable Debug**, **CRON JOB interval** und **Category Cron Job command**. Standardwerte: description, pendingDeepSeek, 5 categories, Every Hour.

**Vervollständigen Sie die Adresse.** Die auf der Seite angezeigte Adresse kann unvollständig sein. Prüfen Sie immer, dass die endgültige Adresse die Aktion enthält. Verwenden Sie diese Form und ersetzen Sie die Platzhalter:

```text
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent&updatedField=description&productTarget=pendingDeepSeek&productsToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent&updatedField=description&categoryTarget=pendingDeepSeek&categoriesToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
```

Verwenden Sie `&action=generateProductContent` für Produkte und `&action=generateCategoryContent` für Kategorien. Ohne sie geschieht beim Aufruf nichts. Wenn Ihr Shop keine sprechenden URLs verwendet, kopieren Sie die Basisadresse von der Seite und hängen Sie die Teile mit `&` an. Veröffentlichen Sie diese Adressen nicht: Das darin enthaltene Geheimnis ist der einzige Schutz.

Empfohlener erster Test: Setzen Sie **Enable Debug** auf **Yes**, öffnen Sie die Adresse in Ihrem Browser und lesen Sie den Plan. Setzen Sie es dann auf **No**, planen Sie die Adresse ein und prüfen Sie nach dem ersten Aufruf **History**.

### 3.12 History

Öffnen Sie **History**. Die Seite listet jeden Prompt, jede Antwort, jeden Status und jede Token-Anzahl auf. Die Seite ist ein Bericht: Das Filtern löscht keine Zeilen und ändert keine Produkte.

![History](https://mypresta.eu/docs/images/docs/myaideepseek-history.webp)

| Element | Was es tut |
|---|---|
| **7 days**, **30 days**, **This month**, **All time** | Datumsvorgaben. |
| **From** / **To** | Eigener Zeitraum. |
| **Model**, **Type**, **Status** (**Success** oder **Error**), **Language**, **Employee** | Schränken die Seite auf einen Ausschnitt ein. |
| **Product / category ID** | Nur Anfragen für dieses Element. |
| **Prompt or reply contains** | Ein Wort, das im Prompt oder in der Antwort vorkommen muss. |
| **Filter** | Wendet die Filter an. |
| Karten **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** | Summen für die gefilterten Zeilen. Ein Strich bedeutet, dass DeepSeek für diesen Aufruf keine Token-Anzahl zurückgegeben hat. |
| Gruppen **By day**, **By model**, **By type**, **By language**, **By employee** | Aufschlüsselungstabellen. |
| Listenspalten **Status**, **Prompt**, **Reply / Error**, **Provider**, **Received**, **Entity ID**, **Timestamp** | Eine Zeile pro Anfrage. Öffnen Sie eine Zeile, um den vollständigen Prompt, die Antwort und die Tokens zu lesen. **Back to the list** führt zurück. |
| **Clear list** | Löscht die History-Zeilen. Sie sehen **Log list successfully deleted.** Die **Restore**-Punkte auf der Produktseite verschwinden damit. Der Katalogtext wird nicht geändert. |

### 3.13 Images

Öffnen Sie **Images**. Hier werden der Schalter und die Anweisung der Produktfoto-Suche gespeichert. Das Öffnen dieser Seite lädt nichts herunter.

![Images](https://mypresta.eu/docs/images/docs/myaideepseek-images.webp)

| Feld | Startwert | Was es tut |
|---|---|---|
| **AI Image Finder** | Enabled | Zeigt oder verbirgt die Fotosuche auf der Produktbearbeitungsseite. Ein Bild wird erst importiert, nachdem jemand es bestätigt hat. |
| **AI Image Search Prompt** | vorgefertigte englische Anweisung | Die Anweisung, die bei einer Suche gesendet wird. Produktname und Kurzbeschreibung werden eingesetzt. Behalten Sie die Bitte um eine einfache Liste von Seitenadressen bei. |

Drücken Sie **Save**. Dies sind dieselben beiden Einstellungen wie unter **Settings**, **General**.

### 3.14 Updates

Öffnen Sie **Updates**. Die Seite fragt MyPresta.eu, ob eine neuere Version dieses Moduls veröffentlicht ist.

![Updates](https://mypresta.eu/docs/images/docs/myaideepseek-updates.webp)

| Element | Startwert | Was es tut |
|---|---|---|
| **Automatic Notifications** | folgt der gespeicherten Einstellung | Lässt das Back Office Sie warnen, wenn eine neuere Version existiert. |
| **Check Now** | – | Fragt einmal, sofort. Die Seite meldet dann, dass diese Kopie aktuell ist oder dass eine neuere Version existiert. |
| Link zur Modulseite | – | Öffnet die Modulseite auf MyPresta.eu. |

Ihr Katalog und die generierten Texte werden von dieser Seite nicht berührt.

### 3.15 Die Produktbearbeitungsseite

Öffnen Sie **Catalog**, dann **Products**, bearbeiten Sie ein Produkt und öffnen Sie den Tab **Modules**, dann **My AI DeepSeek**. Je nach PrestaShop-Version und den Einstellungen unter **General** sehen Sie möglicherweise auch kleine Schaltflächen **Generate with AI** neben der Beschreibung, der Kurzbeschreibung und den Meta-Feldern.

![Product edit](https://mypresta.eu/docs/images/docs/myaideepseek-product-edit.webp)

Der Tab hat vier Teile: **Generate**, **Simulate**, **Photos** und **History**. Wenn **Product edit page Form** deaktiviert ist, bleibt nur **History** übrig (wenn **Product Edit History** aktiviert ist).

**Generate** – jede Schaltfläche schreibt ein Feld und speichert den Text am Produkt.

| Bedienelement | Was es tut |
|---|---|
| **Language**-Schaltflächen | Wählen eine Shop-Sprache. **Every language** schreibt alle. |
| **If the field already has text** | **Replace** (Standard), **Add above**, **Add below** oder **Skip if filled**. |
| **Description** | Der lange Text, mit kurzer Einleitung und einer Merkmalsliste. |
| **Short description** | Eine kurze, einfache Zusammenfassung, unter etwa 400 Zeichen. |
| **Name** | Der Produkttitel, den Kunden sehen. |
| **Meta title** | Der Titel im Suchergebnis, etwa 70 Zeichen. |
| **Meta description** | Der Text im Suchergebnis, etwa 160 Zeichen. |
| **Tags** | Eine durch Kommas getrennte Wortliste. |
| **SEO pack** – **Fill all** | Schreibt Name, beide Beschreibungen und beide Meta-Felder in einem Zug. Wenn die Antwort nicht verwendbar ist, sehen Sie **The model did not return a usable SEO pack.** |
| **Fill** | Erscheint auf jeder Feldkarte: generiert und speichert dieses Feld. |
| **Use your own instruction or a saved prompt** | Öffnet ein Filterfeld, Kacheln mit den aktivierten Vorlagen (**Standard brief** ist die Vorgabe) und ein Feld **Instruction**. Lassen Sie das Feld leer, um die Standardvorgabe des Feldes zu verwenden, das Sie drücken. |

**Simulate** – dieselben Feldkarten mit einer Schaltfläche **Try**. Die Antwort wird auf dieser Seite angezeigt, und das Produkt wird **nicht** geändert. Nutzen Sie es, um einen Prompt zu testen, und wechseln Sie dann zurück zu **Generate**.

**Photos** – siehe Abschnitt 3.16.

**History** – die Tabelle **When**, **Type**, **Status** und eine Schaltfläche **Restore**. **Restore** setzt den vorherigen Text dieses Schreibvorgangs am Produkt zurück. Zeilen ohne vorherigen Wert oder mit Fehler haben keine Schaltfläche. Der shopweite Bericht **History** wird nicht gelöscht. Eine leere Liste zeigt **No generations for this product yet.**

![Product photos](https://mypresta.eu/docs/images/docs/myaideepseek-product-photos.webp)

### 3.16 Produktfotos

Öffnen Sie den Tab **Photos** an einem Produkt. Wenn **AI Image Finder** deaktiviert ist, erklärt der Tab, wie Sie ihn unter **Settings**, **General** einschalten.

1. Klicken Sie auf **Find pages**. DeepSeek schlägt Webseiten vor, die wahrscheinlich Fotos des Produkts enthalten.
2. Seiten und Bilder erscheinen. Markieren Sie die gewünschten Bilder.
3. Klicken Sie auf **Add selected to this product**. Vor diesem Klick wird nichts gespeichert.

Das Modell schlägt Seiten aus seinem eigenen Wissen vor, nicht aus einer Live-Websuche. Prüfen Sie die Bilder auf Urheberrecht und Qualität, bevor Sie sie veröffentlichen.

## 4. Shop-Frontend

Das Modul zeigt Kunden nichts an. Die beiden Front-Hooks, die es registriert, sind leer, und es wird kein Template, keine Schaltfläche und kein Block zu Ihrem Theme hinzugefügt. Vom Modul geschriebener Text erscheint in Ihrem Shop nur als gewöhnliche Produkt- und Kategoriefelder (Name, Beschreibungen, Meta-Tags, Tags). Sie müssen das Theme nicht ändern.

Das Modul hat außerdem zwei Adressen, die ein Browser oder ein Server öffnen kann:

| Adresse | Wer sie nutzt | Was passiert |
|---|---|---|
| Die **Cron**-Adresse mit `&action=generateProductContent` oder `&action=generateCategoryContent` | Der Scheduler Ihres Servers oder Sie beim Testen | Ein Stapel wird geschrieben. Bei **Enable Debug** auf **Yes** wird der Plan ausgegeben und nichts gespeichert. Ein falsches oder fehlendes Geheimnis wird abgelehnt. |
| Die interne Anfrageadresse, die von den Schaltflächen des Back Office verwendet wird | Ihr Browser, während Sie im Back Office arbeiten | Sie benötigt ein Token, das das Back Office automatisch hinzufügt. Sie tippen es nie ein. Wird sie abgelehnt, laden Sie die Back-Office-Seite neu. |

## 5. Probleme

**Eine Generierung schlägt fehl und History zeigt einen Error.**
Öffnen Sie **History**, öffnen Sie die Zeile und lesen Sie die Meldung. Die häufigen Ursachen stehen unten.

**Der API-Schlüssel wird abgelehnt oder fehlt.**
Öffnen Sie **Settings**, **DeepSeek**, fügen Sie den Schlüssel erneut von https://platform.deepseek.com/api_keys ein und drücken Sie **Save**. Auf der Seite für neue Produkte verschwindet danach die Warnung **Add an API key in the module settings first.** Meldet DeepSeek kein Guthaben, laden Sie das Konto bei DeepSeek auf.

**Der Aufruf endet mit einem Timeout.**
Erhöhen Sie **API timeout (seconds)** unter **Settings**, **General** (für `deepseek-reasoner` verwenden Sie mehrere hundert Sekunden). Bei Cron verringern Sie **Product to update**.

**Der Text wird mitten im Satz abgeschnitten.**
Erhöhen Sie **Max Tokens** unter **Settings**, **DeepSeek**. Bei `deepseek-reasoner` umfasst das Limit auch das Reasoning.

**Einstellungen scheinen den Stil nicht zu ändern.**
Bei `deepseek-reasoner` können **Temperature**, **Top P** und die beiden Penalty-Felder ignoriert werden. Verwenden Sie `deepseek-chat`. Prüfen Sie außerdem, ob **Studio** gespeichert ist und ob Sie die richtige Sprache verwendet haben.

**Eine Antwort wird nicht gespeichert und am Produkt ändert sich nichts.**
Mögliche Ursachen: Die Antwort enthält eine Zeile aus **Forbidden words** und **Quality gate** ist aktiviert (bearbeiten Sie die Liste oder deaktivieren Sie die Schranke); **Existing text** steht auf **Skip if filled** und das Feld enthält Text; das Monatslimit ist erreicht (**Monthly generation budget reached. Raise it in the studio settings or wait until next month.**).

**Der von mir eingegebene Modellname funktioniert nicht.**
Sie haben eine ID hinzugefügt, die Ihr Konto nicht aufrufen kann. Wählen Sie wieder das eingebaute `deepseek-chat` und entfernen Sie Ihren eigenen Eintrag.

**Die Generate-Liste ist leer oder zu kurz.**
Prüfen Sie **Product status**, **Product stock**, **Update only** und **Product Limit**. Ein häufiger Fehler ist, **Update only** bei einem ersten Durchlauf auf "already updated" stehen zu lassen.

**Cron tut nichts.**
Prüfen Sie in dieser Reihenfolge: **Enable Cron Feature** steht auf **Yes**; die Adresse endet mit der richtigen `&action=…`; das Geheimnis ist das aktuell angezeigte; **Enable Debug** steht auf **No**; **Selected Products** hat noch wartende Einträge; der Server ruft die Adresse tatsächlich auf. Ein abgeschlossener Satz ändert sich absichtlich nicht mehr. Für mehrere Felder verwenden Sie **pendingField** statt **pendingDeepSeek**, weil Letzteres ein Produkt überspringt, sobald irgendein Feld generiert wurde.

**Cron ist nach dem Ändern des Geheimnisses stehen geblieben.**
Die alte Adresse ist nicht mehr gültig. Kopieren Sie die neue Adresse (mit `&action=…`) in den Scheduler.

**Die Seite meldet "Error! Invalid token!" oder Schaltflächen reagieren nicht.**
Die Seite war zu lange geöffnet. Laden Sie die Back-Office-Seite neu und versuchen Sie es erneut.

**Der Tab Modules des Produkts enthält keinen Inhalt von My AI DeepSeek.**
Prüfen Sie, ob **Product edit page Form** oder **Product Edit History** aktiviert ist, ob das Modul aktiv ist und ob der Cache geleert wurde.

**Es gibt keine Schaltfläche "Restore".**
Die Zeile war ein Fehler, der Schreibvorgang hatte keinen vorherigen Wert, oder **Clear list** hat die History-Zeilen entfernt.

**Einige Beschriftungen sagen noch "OpenAi".**
Einige Meldungen und Filterbeschriftungen behalten einen älteren Namen, zum Beispiel **OpenAi Settings Updated** nach dem Speichern des Formulars **DeepSeek**, die Optionen "updated with OpenAi content" des Filters **Update only** oder einen älteren Beispiel-Modellnamen in einem Hinweis. Der verwendete Dienst ist DeepSeek. In History kann die Spalte **Provider** den älteren internen Namen zeigen. Das hat keinen Einfluss auf die Ergebnisse.

**Im Shop-Frontend ändert sich nichts.**
Das Modul schreibt gewöhnliche Produktfelder. Prüfen Sie das Produkt unter **Catalog** und den Cache Ihres Themes.

## 6. Für Entwickler

### 6.1 Überblick

- **Technischer Name:** `myaideepseek`
- **Modulname in der Liste:** My AI DeepSeek - AI content generation
- **Version:** 1.0.0
- **Autor:** MyPresta.eu
- **PrestaShop-Kompatibilität:** 1.6 – 9.99.99
- **PHP:** 7.0 oder neuer (die Installation lehnt ältere Versionen ab)
- **Netzwerk:** cURL und HTTPS zu `https://api.deepseek.com/v1`
- **Konfigurationspräfix:** `MYPRESTA_MYAIDEEPSEEK_`
- **Ablauf:** Einstellungen werden aus der Konfigurationstabelle gelesen; Prompts werden aus der Vorlage oder Anweisung plus Studio-Regeln aufgebaut; pro Feld wird eine Chat-Anfrage gesendet; die Antwort wird geprüft (Quality gate, Budget), am Produkt oder an der Kategorie gespeichert und mit dem vorherigen Wert in `myaideepseek_log` protokolliert.

### 6.2 Dateien

| Datei | Zweck |
|---|---|
| `myaideepseek.php` | Hauptklasse: Installation, Deinstallation, Einstellungsformulare, Navigation, Hooks, Produkt-Tab. |
| `autoload.php` | Klassenladen für `src/` und `lib/`. |
| `src/OpenAIService.php` | HTTP-Client für den Chat-Completion-Aufruf (unter dem älteren Dateinamen beibehalten). |
| `src/Studio.php` | Fügt Studio-Regeln und die Qualitätsprüfung hinzu. |
| `lib/updateChecker.php` | Update-Prüfung bei MyPresta.eu. |
| `lib/sectionHelp.php` | Texte der Hilfehinweise. |
| `lib/searchTool/` | Autocomplete-Helfer. |
| `lib/prestashop9compatibility.php` | Kompatibilitätshelfer für PrestaShop 9. |
| `controllers/admin/` | Sieben Admin-Controller (siehe 6.3). |
| `controllers/front/ajax.php` | AJAX-Aktionen des Back Office (Generieren, Wiederherstellen, Bildsuche). |
| `controllers/front/cron.php` | Geplante Generierung. |
| `views/templates/hook/*.tpl` | Produkt-Tab, Massengeneratoren, Dashboard, Cron, History, Playground, Navigation. |
| `views/templates/admin/product_creator.tpl` | Bildschirm für neue Produkte. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `dashboard.js`, `admin-help.js`, `admin-products-bulk.js`, `chart.min.js`. |
| `views/css/` | `back.css`, `admin-nav.css`, `stats.css`. |
| `translations/{iso}.php` | Modulübersetzungen. |

### 6.3 Controller

| Klasse | Rolle |
|---|---|
| `AdminMyAIDeepSeekMain` | Menü-Elternpunkt **AI Content Generator**. |
| `AdminMyAIDeepSeek` | **Generate** (`mds_sub=products` oder `categories`). |
| `AdminMyAIDeepSeekProductCreator` | **New product**. |
| `AdminMyAIDeepSeekSettings` | Einstieg in die Einstellungen (die Formulare liegen auf der Modul-Konfigurationsseite). |
| `AdminMyAIDeepSeekCron` | **Cron**-Formulare. |
| `AdminMyAIDeepSeekUsage` | **History**. |
| `AdminMyAIDeepSeekImageFinder` | **Images**. |
| `ModuleFrontController` ajax | Benötigt den Parameter `secret_token` gleich `MYPRESTA_MYAIDEEPSEEK_TOKEN`; andernfalls antwortet er mit *Error! Invalid token!* |
| `ModuleFrontController` cron | Benötigt `secret` gleich dem Produkt- oder Kategoriegeheimnis. |

Die Modul-Konfigurationsseite verwendet `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai` = der Bereich **DeepSeek**, `studio`, `templates`, `playground`) und `mcg_preset` für die Datumsvorgaben.

Cron-Abfrageparameter, die `controllers/front/cron.php` liest:

| Parameter | Verwendet für | Standard, wenn nicht angegeben |
|---|---|---|
| `secret` | Produkt- oder Kategoriegeheimnis (erforderlich) | – |
| `action` | `generateProductContent` oder `generateCategoryContent` (erforderlich) | – |
| `updatedField` | Zu schreibendes Feld | gespeicherter Wert |
| `productTarget` / `categoryTarget` | `pendingDeepSeek`, `pendingField`, `emptyField` | gespeicherter Wert |
| `productsToUpdate` / `categoriesToUpdate` | Stapelgröße | gespeicherter Wert |
| `languageId` | Sprache | gespeicherter Wert |
| `promptTemplateId` | Vorlage | gespeicherter Wert |
| `debug` | Nur den Plan ausgeben | gespeicherter Wert |
| `categories` | Kategoriefilter (Produkte) | gespeicherter Wert |
| `productIds` | Produkt-ID-Filter | gespeicherter Wert |

### 6.4 Hooks

Registriert: `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` (beide geben eine leere Zeichenkette zurück), `actionProductFormBuilderModifier` (kehrt ohne Ausgabe zurück), `displayAdminProductsExtra` (der Inhalt des Tabs **Modules**), `displayBackOfficeHeader` (Assets, Loader der Produktseite), `displayBackOfficeTop` (Verknüpfung in der oberen Leiste), `dashboardZoneTwo` (Block auf dem PrestaShop-Dashboard), `displayHeader` und `displayFooter` (beide leer). Das Modul stellt keine eigenen Hooks bereit. Es hat keine Überschreibung von `enable()` oder `disable()`.

### 6.5 Overrides

Keine.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `myaideepseek_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated`. 16 Zeilen nach der Installation. |
| `myaideepseek_log` | Eine Zeile pro Anfrage: IDs von Produkt, Kategorie, CMS, Hersteller, Sprache und Mitarbeiter; `type`, `method`, `status`, Dienst, `model`, HTTP-Code, Dauer, Token-Anzahlen, Fehlermeldung, `prompt`, `reply` sowie alte und neue Werte von Name, Beschreibungen, Meta-Feldern und Tags. |

Die Deinstallation löscht beide Tabellen. Tabs werden entfernt. Produkt- und Kategorietexte werden nicht berührt.

### 6.7 Schlüssel und Übersetzungen

Alle Schlüssel tragen das Präfix `MYPRESTA_MYAIDEEPSEEK_`.

| Schlüssel-Suffix | Standard | Bedeutung |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TIMEOUT` | 120 | Aufruf-Timeout in Sekunden. |
| `PRODUCT_LOG` | 1 | Produkt-Bearbeitungsverlauf. |
| `TOPCTA` | 1 | Verknüpfung in der oberen Leiste. |
| `PRODUCT` | 1 | Generator auf der Produktseite. |
| `IMAGEFINDER_ENABLE` | 1 | Schalter der Fotosuche. |
| `IMAGEFINDER_PROMPT` | eingebauter englischer Text | Anweisung der Fotosuche. |
| `API_KEY` | leer | DeepSeek-Schlüssel. |
| `MODEL` | `deepseek-chat` | Aktives Modell. |
| `EXTRA_MODELS` | leer | Vom Händler hinzugefügte Modelle, eines pro Zeile. |
| `MODEL_CAPS` | leer | Zur Laufzeit je Modell gelernte Parameter. |
| `TEMPERATURE` | 0.7 | Sampling. |
| `MAX_TOKENS` | 3200 | Antwortlimit. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 1, 0, 0 | Sampling und Penalties. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | leer | Studio-Regeln. |
| `BUDGET` | 0 | Monatslimit, 0 = keines. |
| `QUALITY` | 1 | Quality gate. |
| `TOKEN` | zufällig | Token der AJAX-Adresse. |
| `SECRET`, `CAT_SECRET` | zufällig | Cron-Geheimnisse für Produkte und Kategorien. |
| `ENABLE_CRON` | 0 | Globaler Cron-Schalter. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Vorgeschlagenes Intervall (Every Hour). |
| `updatedField`, `catupdatedField` | `description` | Cron-Feld. |
| `productTarget`, `categoryTarget` | `pendingDeepSeek` | Cron-Regel. |
| `productsToUpdate`, `categoriesToUpdate` | 5 | Cron-Stapel. |
| `promptTemplateId`, `catpromptTemplateId` | leer | Cron-Vorlage. |
| `languageId`, `catlanguageId` | Standardsprache | Cron-Sprache. |
| `debug`, `catdebug` | 0 | Cron-Debug. |
| `productIdsList`, `categories` | leer | Cron-Filter. |
| `interval_select`, `IMAGEFINDER_TAB_OK` | leer / zur Laufzeit gesetzt | UI-Zustand. |

Das Standardmodell ist `deepseek-chat`. Eingebaute Modelle sind `deepseek-chat` und `deepseek-reasoner`. Die Deinstallation löscht die oben genannten Schlüssel. Filterschlüssel von Generate (zum Beispiel die Kategorie-, Marken- und Statusfilter der **Generate**-Formulare) stehen nicht in der Deinstallationsliste und können verbleiben.

Übersetzungen: Fügen Sie `translations/{iso}.php` im Standardformat von PrestaShop hinzu. Feldhilfetexte werden von `fieldHelp()` in der Form What it does / How to configure / Effect erstellt und laufen durch `$this->l()`. Einige Zeichenfolgen im Produkt-Tab und in den Generate-Templates sind in den `.tpl`-Dateien mit `{l s=…}` definiert. Einige übrig gebliebene Zeichenfolgen enthalten noch den älteren Anbieternamen (siehe Probleme).

### 6.8 Erweitern

Der Produkt-Tab, die Massenbildschirme und Cron verwenden dieselben Prompt-Platzhalter und dieselben AJAX-Aktionen. Eine eigene Vorlage, die `{product_name}`, `{product_brand}`, `{product_features}` und `{product_tags}` verwendet, funktioniert daher überall. Die Front-Controller rendern kein Template, sodass ein Theme nichts zu überschreiben hat. Admin-Templates in `views/templates/hook/` können über das Standard-Template-Override für Module in Ihrem Back-Office-Theme überschrieben werden.

## 7. Hilfe

Modulseite: https://mypresta.eu/modules/administration-tools/my-ai-deepseek.html

So schreiben Sie uns zum Modul:

1. Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an.
2. Öffnen Sie die Kontaktseite.
3. Wählen Sie das Thema **Support for paid modules**. Das Formular weist darauf hin, dass Sie angemeldet sein müssen. Wählen Sie nach der Anmeldung dieses Modul aus Ihrem Kaufverlauf.
4. Beschreiben Sie das Problem. Fügen Sie die Zeile aus **History** (Status und Meldung) sowie die PrestaShop- und PHP-Versionen bei. Senden Sie niemals den API-Schlüssel oder das Cron-Geheimnis.
