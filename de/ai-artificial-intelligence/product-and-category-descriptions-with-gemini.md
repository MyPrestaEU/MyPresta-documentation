---
title: My AI Gemini - AI content generation - Dokumentation und Benutzerhandbuch
description: Leitfaden zu Einrichtung, täglicher Arbeit und Fehlerbehebung für Shopbetreiber, die das Modul My AI Gemini bereits in ihrem PrestaShop-Back-Office installiert haben.
sidebar:
  label: My AI Gemini - AI content generation - Dokumentation und Benutzerhandbuch
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product and Category Descriptions with Gemini auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/product-and-category-descriptions-with-gemini/)
>
> ---


Die Screenshots in diesem Handbuch stammen aus einem englischen Back Office. Jeder Button und jeder Feldname ist genau so geschrieben, wie er auf dem Bildschirm erscheint.

## 1. Voraussetzungen

Prüfen Sie vor dem Start, ob Ihr Shop und Ihr Server die folgenden Punkte erfüllen.

- **PrestaShop:** 1.6, 1.7, 8 und 9 (alle Versionen von 1.6 bis 9.99.99).
- **PHP:** 7.0 oder neuer. Der Installer bricht bei älterem PHP ab und zeigt die Meldung "This module requires PHP 7.0.0 or newer. This server is running PHP …".
- **PHP-Erweiterungen:** cURL (jeder Aufruf von Gemini und jeder Seitenabruf), JSON, DOM (Lesen von Webseiten für New product und die Fotosuche), mbstring und fileinfo (Prüfen heruntergeladener Bilder).
- **Ausgehende Verbindung:** Ihr Server muss sichere (HTTPS-)Verbindungen zum Google-Gemini-Dienst aufbauen dürfen. Blockiert der Server ausgehende Verbindungen, kann nichts generiert werden.
- **Andere Module:** Das Modul benötigt kein weiteres Modul.
- **Google-Konto:** Sie benötigen Ihren eigenen Google-Gemini-API-Schlüssel. Erstellen Sie ihn unter https://aistudio.google.com/apikey und halten Sie ihn geheim. Google rechnet ab bzw. begrenzt die Nutzung nach Ihrem eigenen Google-Konto, nicht über dieses Modul.
- **Zeit und Umfang:** Jedes Feld ist eine Anfrage an Gemini. Lange Texte und langsame Modelle können pro Anfrage mehr als eine Minute dauern. Ein großer Massenlauf oder ein großer Cron-Stapel dauert so lange wie alle seine Anfragen zusammen. Beginnen Sie deshalb mit kleinen Listen.

## 2. Installation

1. Öffnen Sie **Modules**, dann **Module Manager**.
2. Klicken Sie auf **Upload a module** und ziehen Sie die ZIP-Datei hinein oder laden Sie sie auf Ihrem gewohnten Weg hoch.
3. Klicken Sie neben dem Modul, sobald es in der Liste erscheint, auf **Install** und bestätigen Sie.
4. Nach der Installation erscheint im linken Menü im Bereich **Modules** ein neuer Eintrag **AI Content Generator**. Klicken Sie darauf: Es öffnet sich das **Dashboard** des Moduls. Dieselben Bildschirme erreichen Sie auch über **Module Manager**, **Configure**.
5. Bevor etwas generiert werden kann, öffnen Sie **Settings**, dann **Gemini**, fügen den Schlüssel in **Google Gemini API KEY** ein und speichern (Details in Kapitel 3).

Die Installation legt 16 fertige Prompt-Vorlagen an (Produktnamen, Beschreibungen, Meta-Titel, Meta-Beschreibungen und Tags), damit Sie das Modul sofort ausprobieren können. Der Shop-Cache wird nicht geleert. Erscheint der Menüeintrag nicht, öffnen Sie eine beliebige Back-Office-Seite noch einmal: Das Modul setzt den Menüeintrag bei jedem Laden einer Back-Office-Seite wieder an seinen Platz.

**Deinstallation.** Die Deinstallation entfernt den Menüeintrag **AI Content Generator**, löscht die Prompt-Vorlagen und die gesamte History (damit verschwinden auch die Wiederherstellungslisten bei den Produkten) und löscht die Moduleinstellungen, einschließlich API-Schlüssel und Cron-Geheimnisse. Texte, Bilder und Produkte, die bereits mit dem Modul geschrieben oder angelegt wurden, bleiben unberührt. Einige Bildschirmfilter, die Sie auf den **Generate**-Seiten benutzt haben, können in den Shop-Einstellungen gespeichert bleiben; sie sind harmlos. Eine erneute Installation beginnt mit einem sauberen Zustand: Die 16 Standardvorlagen kehren zurück, alte Einstellungen, Vorlagen und die History werden nicht wiederhergestellt.

## 3. Konfiguration und tägliche Arbeit im Back Office

### 3.1 Der gesamte Ablauf, Schritt für Schritt

1. **Gemini verbinden.** **Settings**, **Gemini**: API-Schlüssel einfügen, Modell beibehalten oder ändern, speichern.
2. **Testen.** **Settings**, **Playground**: Geben Sie eine kurze Anweisung ein und drücken Sie **Generate**. Sehen Sie eine Antwort, funktioniert die Verbindung. Im Katalog wird nichts gespeichert.
3. **Shop-Stil festlegen (optional).** **Settings**, **Studio**: Markenstimme, Zielgruppe, Tonalität, beizubehaltende und verbotene Wörter eintragen.
4. **Anweisungen vorbereiten.** **Settings**, **Prompt templates**: Standardvorlagen behalten oder eigene hinzufügen. Aktivierte Vorlagen werden überall sonst angeboten.
5. **Arbeitsweise wählen:**
   - Ein Produkt nach dem anderen: Produkt öffnen, dann **Modules**, **My AI Gemini**, und neben einem Feld **Fill** drücken (3.16).
   - Viele Produkte oder Kategorien: **Generate**, **Products** oder **Categories** (3.9 und 3.10).
   - Ein Produkt, das noch nicht existiert: **New product** (3.11).
   - Automatisch, in kleinen Stapeln, ohne dass jemand klickt: **Cron** (3.12).
6. **Ergebnis prüfen.** **History** listet jede Anfrage mit Prompt, Antwort, Status und Token-Verbrauch auf. Das **Dashboard** zeigt dieselben Zahlen als Diagramme.
7. **Rückgängig machen.** Am Produkt: **Modules**, **My AI Gemini**, **History**: **Restore** setzt den vorherigen Text wieder ein.

Texte werden direkt im Produkt oder in der Kategorie gespeichert, sobald Gemini antwortet, außer wo dieses Handbuch etwas anderes sagt (die **Try**-Buttons, der **Playground**, **Generate data** und die **Generate with AI**-Buttons neben Feldern, die den Text nur in das geöffnete Formular einfügen, bis Sie speichern).

### 3.2 Das Modul öffnen und sich darin bewegen

Öffnen Sie **AI Content Generator** im linken Menü. Die Leiste oben auf jedem Bildschirm enthält diese Punkte: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** und ganz rechts **Updates**. Halten Sie die Maus über einen Punkt, um eine kurze Erklärung zu sehen. Unter **Settings** erscheint eine zweite Zeile mit **General**, **Gemini**, **Studio**, **Prompt templates** und **Playground**. Unter **Generate** zeigt die zweite Zeile **Products** und **Categories**.

Der runde **Help**-Button am Rand jeder Modulseite öffnet ein Seitenpanel mit einer kurzen Erklärung der aktuellen Seite. Eine Zeile in diesem Panel verweist noch auf ein OpenAI-Konto (siehe Kapitel 5); verwenden Sie Ihren Google-Gemini-Schlüssel.

Das Modul erreichen Sie außerdem aus **Module Manager** mit dem Button **Configure**, über den Shortcut-Button in der oberen Leiste (3.18) und über einen Link in der Produktliste (3.18).

### 3.3 Dashboard

Das **Dashboard** ist ein Bericht. Es schreibt niemals Produkt- oder Kategorietexte.

![My AI Gemini – Dashboard mit Datumsbereich, Karten und Diagrammen](https://mypresta.eu/docs/images/docs/myaigemini-dashboard.webp)

Oben wählen Sie den Zeitraum. Die Zeile **Active service** zeigt immer Gemini und das auf dem Bildschirm **Gemini** gespeicherte Modell.

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | **30 days** | Schnellbuttons für den Zeitraum. Der gewählte ist hervorgehoben. Nur die Zahlen und Diagramme auf dieser Seite ändern sich. |
| **From** und **To** | Daten der letzten 30 Tage | Ihr eigener Zeitraum. Drücken Sie **Apply**, um neu zu zeichnen. Liegt From nach To, vertauscht das Modul beide. |
| **Apply** | – | Zeichnet die Karten und Diagramme für die eingegebenen Daten neu. |
| **Requests** | Aus History berechnet | Jeder gespeicherte Aufruf im Zeitraum, erfolgreich oder fehlgeschlagen. |
| **Success** | Aus History berechnet | Aufrufe, die nicht mit einem Fehler endeten. |
| **Errors** | Aus History berechnet | Aufrufe, die mit einem Fehler endeten. |
| **Tokens sent** | Aus History berechnet | Gesamtumfang Ihrer an Gemini gesendeten Anweisungen. |
| **Tokens received** | Aus History berechnet | Gesamtumfang der Antworten. |
| Diagramm **Requests and errors** | – | Liniendiagramm, ein Punkt pro Tag. Bei Zeiträumen über 120 Tagen deckt ein Punkt eine Woche ab. |
| Diagramm **Tokens sent and received** | – | Gleicher Zeitraum, zwei Linien. |
| Diagramm **Requests by model** | – | Balkendiagramm: wie viele Anfragen jedes Modell bearbeitet hat. |

Sind die Diagramme leer, wurde in diesem Zeitraum nichts generiert. Das Dashboard gibt es auch als kleinen Block im Haupt-Dashboard von PrestaShop, doch dieser Block erhält die History-Zahlen nicht, sodass seine Karten und Diagramme leer bleiben. Verwenden Sie das **Dashboard** des Moduls.

### 3.4 Settings – General

Öffnen Sie **Settings**, dann **General**. Diese Schalter bestimmen, was Mitarbeiter im Back Office sehen. Das Speichern schreibt keinen Produkttext um.

![Settings – General](https://mypresta.eu/docs/images/docs/myaigemini-settings-general.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Live mode** | Disabled | Kennzeichnet das Modul als im echten Shop laufend. Aktivieren Sie es im Produktivshop. Lassen Sie es auf einer Testkopie deaktiviert, um zu zeigen, dass dies nicht die Produktivumgebung ist. Die gleichen Werkzeuge funktionieren in beiden Zuständen. |
| **Debug mode** | Disabled | Schreibt zusätzliche technische Meldungen in das PrestaShop-Log (**Advanced Parameters**, **Logs**), wenn ein Gemini-Aufruf fehlschlägt. Schalten Sie ihn nur ein, solange Sie einen Fehler untersuchen, und danach wieder aus. Kunden sehen ihn nie. |
| **API timeout (seconds)** | 120 | Wie viele Sekunden ein Aufruf an Gemini laufen darf, bevor das Modul aufgibt. 120 genügt für normale Beschreibungen. Erhöhen Sie bis auf 600 für lange SEO-Texte oder langsame Modelle. Werte unter 10 werden zu 10, Werte über 600 zu 600, ein leerer oder nicht numerischer Wert wird zu 120. Ein kurzes Timeout scheitert schnell und protokolliert einen Fehler. |
| **Product Edit History** | Enabled | Zeigt den Tab **History** mit **Restore**-Buttons auf der Produktseite (**Modules**, **My AI Gemini**). Deaktiviert blendet die Liste aus. Frühere Zeilen bleiben in jedem Fall in der shopweiten **History**. |
| **Admin Top Bar CTA** | Enabled | Setzt einen kleinen Zauberstab-Button in die obere Leiste jeder Back-Office-Seite, der ein Prompt-Fenster öffnet. Deaktiviert entfernt nur diesen Button. Das Modulmenü bleibt. |
| **Product edit page Form** | Enabled | Zeigt das Generator-Panel unter **Modules**, **My AI Gemini** auf der Produktseite. Aktivieren Sie es für Katalogredakteure. Deaktivieren Sie es, wenn nur Massengenerierung und Cron genutzt werden sollen. |
| **AI Image Finder** | Enabled | Zeigt den Tab **Photos** auf der Produktseite. Deaktiviert blendet ihn aus. Ein Bild wird erst importiert, nachdem es angehakt und bestätigt wurde. |
| **AI Image Search Prompt** | Eine eingebaute englische Anweisung, die nach 5 Seitenadressen fragt | Die Anweisung, die bei der Suche nach Produktbildern gesendet wird. Die Wörter {product_name} und {product_description} werden durch das aktuelle Produkt ersetzt. Behalten Sie die Bitte um eine Liste von Seitenadressen bei. Ein präziserer Prompt liefert passendere Seiten. |
| **Save** | – | Speichert alle obigen Felder. Meldung: **Settings Updated**. |

Die beiden Bildfelder erscheinen sowohl hier als auch auf dem Bildschirm **Images** (3.14). Es sind dieselben zwei Einstellungen.

### 3.5 Settings – Gemini

Öffnen Sie **Settings**, dann **Gemini**. Hier verbinden Sie das Google-Konto und legen fest, wie abwechslungsreich die Wortwahl ist. Jede Generierung (Produkt-Buttons, Massenläufe, Cron, New product, Fotosuche, Playground) verwendet diese Werte.

![Settings – Gemini](https://mypresta.eu/docs/images/docs/myaigemini-settings-gemini.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Google Gemini API KEY** | Leer | Das Geheimnis, mit dem Ihr Shop Ihr Gemini-Konto aufrufen darf. Fügen Sie den Schlüssel von https://aistudio.google.com/apikey ein. Leerzeichen am Anfang und Ende werden entfernt. Lassen Sie das Feld unberührt, bleibt der gespeicherte Schlüssel erhalten. Ein leerer oder falscher Schlüssel lässt Aufrufe scheitern, und der Fehler wird in die History geschrieben. |
| **Model** | gemini-2.0-flash | Das Gemini-Modell, das den Text schreibt. Eingebaute Auswahl: gemini-2.0-flash, gemini-2.0-flash-lite, gemini-1.5-flash, gemini-1.5-flash-8b, gemini-1.5-pro, gemini-2.5-flash, gemini-2.5-pro. Die nächste Generierung verwendet das gespeicherte Modell. Ein Modell, das Ihr Schlüssel nicht nutzen kann, liefert einen Fehler statt Text. |
| **Add a Gemini model** (Feld mit **Add model**) | – | Fügt einen Modellnamen hinzu, der nicht in der eingebauten Liste steht. Geben Sie den exakten Namen aus Ihrem Gemini-Konto ein und drücken Sie **Add model**. Der Name erscheint in **Model** und wird sofort ausgewählt. Hinzugefügte Namen haben daneben einen Link **Remove**. Eingebaute Namen lassen sich nicht entfernen. |
| **Max Tokens** | 3200 | Obergrenze für die Länge einer Antwort, in Tokens gezählt, nicht in Wörtern. Etwa 256 genügen für eine Meta-Beschreibung, 1000 oder mehr für eine vollständige HTML-Beschreibung. Ein niedriges Limit schneidet die Antwort ab. Ein hohes Limit erlaubt längeren Text. Einige Gemini-2.5-Modelle verbrauchen einen Teil dieses Limits zum „Nachdenken“, lassen Sie es für sie daher großzügig. |
| **Temperature** | 0.7 | Wie frei das Modell Wörter wählt. Bleiben Sie zwischen 0 und 1. Etwa 0.2 passt zu Spezifikationen und Meta-Text, etwa 0.7 zu Beschreibungen. Ein niedriger Wert wiederholt eine ähnliche Struktur. Ein hoher Wert liefert abwechslungsreichere Formulierungen und mehr Risiko, vom Briefing abzuweichen. |
| **Top P** | 1 | Eine zweite Möglichkeit, die Auswahl des nächsten Wortes einzugrenzen. In dieser Version wird der Wert gespeichert, aber nicht an Gemini gesendet; eine Änderung verändert die Antworten also nicht. |
| **Frequency Penalty Value** | 0 | Soll wiederholte Wendungen vermeiden. Gespeichert, aber in dieser Version nicht an Gemini gesendet, daher ohne Wirkung auf die Antworten. |
| **Presence Penalty Value** | 0 | Soll den Text zu neuen Punkten lenken. Gespeichert, aber in dieser Version nicht an Gemini gesendet, daher ohne Wirkung auf die Antworten. |
| **Save** | – | Speichert das Formular. Meldung: **OpenAi Settings Updated** (das Modul verwendet hier noch die ältere Formulierung). |

Meldungen, die Sie auf diesem Bildschirm sehen können:

| Meldung | Ursache | Was zu tun ist |
|---|---|---|
| **Google Gemini API KEY field is invalid!** | Das Schlüsselfeld hat weniger als 10 Zeichen und es ist noch kein Schlüssel gespeichert. | Fügen Sie den vollständigen Schlüssel ein und drücken Sie erneut **Save**. |
| **OpenAi Model field is invalid!** | Der Modellname hat weniger als 3 Zeichen. | Wählen Sie einen Namen aus der Liste **Model**. |
| **Google Gemini API Key has been automatically cleaned (whitespace removed).** | Der gespeicherte Schlüssel hatte Leerzeichen drumherum. | Nichts: Das Modul hat es korrigiert. |
| **Model added.** | Der neue Name wurde gespeichert und ausgewählt. | Drücken Sie **Save**, wenn Sie auch andere Felder geändert haben. |
| **That model is already built in.** | Der eingegebene Name steht bereits in der Liste. | Das Modul wählt ihn für Sie aus. |
| **Model removed.** | Ein hinzugefügter Name wurde gelöscht. | War es das aktive Modell, wählen Sie erneut ein Gemini-Modell (siehe Kapitel 5). |
| **Built-in models cannot be removed.** | Sie wollten einen eingebauten Namen entfernen. | Nichts zu tun. |
| **Enter a model id such as gpt-4.1.** | Das Feld für den Modellnamen war leer oder enthielt unzulässige Zeichen. | Geben Sie einen Gemini-Namen ein, zum Beispiel gemini-2.5-flash. Das Beispiel in dieser Meldung ist ein Überbleibsel. |

### 3.6 Settings – Studio

Öffnen Sie **Settings**, dann **Studio**. Studio legt Hausregeln über jeden Prompt: Produkt-Buttons, Massenläufe, Cron und den Playground. Leere Felder werden übersprungen. Das Modul weist Gemini außerdem immer an, in der Sprache des gerade generierten Elements zu schreiben.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaigemini-settings-studio.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Brand voice** | Leer | Sagt dem Modell, wer spricht, damit der Text wie Ihr Shop klingt. Schreiben Sie ein kurzes Briefing, zum Beispiel: Fachwerkstatt, kurze Sätze, kein Marktgeschrei. Eine Änderung schreibt bereits gespeicherte Texte nicht um. |
| **Audience** | Leer | Nennt den Leser, zum Beispiel professionelle Installateure oder Erstkäufer. Neue Antworten verwenden einen auf diesen Leser zugeschnittenen Wortschatz. |
| **Tone** | Leer | Ein oder zwei Wörter für die Stimmung: formell, herzlich, technisch. Es ändert weder Modell noch Temperatur. |
| **Glossary** | Leer | Markennamen, Materialien und Schreibweisen, die das Modell exakt übernehmen muss. Ein Begriff pro Zeile. Nicht aufgeführte Begriffe können weiterhin umformuliert werden. |
| **Forbidden words** | Leer | Wörter und Wendungen, die in einer gespeicherten Antwort nicht vorkommen dürfen. Eines pro Zeile. Die Liste wird dem Modell außerdem als zu vermeidende Wörter gesendet. Eine passende Antwort wird nur dann abgelehnt, wenn **Quality gate** aktiviert ist. |
| **Monthly generation budget** | 0 | Maximale Anzahl erfolgreicher Generierungen im laufenden Kalendermonat, aus der History gezählt. 0 bedeutet kein Limit. Ist die Grenze erreicht, werden neue Anfragen mit einer Budgetmeldung bis zum nächsten Monat gestoppt. Fehlgeschlagene Aufrufe zählen nicht. |
| **Quality gate** | Enabled | Prüft jede Antwort gegen **Forbidden words**, bevor etwas gespeichert wird. Aktiviert lehnt es eine passende Antwort ab: Das Produkt bleibt unverändert, und die History protokolliert einen Fehler. Deaktiviert speichert es die Antwort, auch wenn sie ein gelistetes Wort enthält. Bei leerer Liste Forbidden words hat das Gate nichts zu prüfen. |
| **Save studio** | – | Speichert das Formular. Meldung: **Studio settings saved.** |

### 3.7 Settings – Prompt templates

Öffnen Sie **Settings**, dann **Prompt templates**. Eine Vorlage ist eine gespeicherte Anweisung. Redakteure wählen sie nach Titel aus, statt dasselbe Briefing jedes Mal neu zu tippen.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaigemini-settings-templates.webp)

Die Liste zeigt diese Spalten: **ID**, **Title**, **Prompt**, **Status** (Häkchen oder Kreuz anklicken, um die Vorlage zu aktivieren oder zu deaktivieren), **Timestamp**. Jede Zeile hat **Edit** und **Delete**. Haken Sie mehrere Zeilen an und nutzen Sie die Sammelaktion **Delete** (es erscheint die Frage "Are you sure you want to delete the selected prompts?"). Der grüne Plus-Button über der Liste legt eine neue Vorlage an.

Das Vorlagenformular:

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Status** | Schalter Enabled / Disabled | Zeigt oder verbirgt die Vorlage in den Listen auf der Produktseite, im Prompt-Fenster der oberen Leiste, in der Massengenerierung und im Cron. Aktivieren Sie die Vorlagen, die Ihr Team nutzen soll. Deaktivieren Sie einen Entwurf, statt ihn zu löschen. |
| **Prompt title** | Leer (Pflichtfeld) | Der Name, den Redakteure in der Liste sehen. Er wird nicht an Gemini gesendet. Verwenden Sie eine kurze Bezeichnung, zum Beispiel HTML description with features. |
| **Prompt content** | Leer (Pflichtfeld) | Die an Gemini gesendete Anweisung. Schreiben Sie sie so, wie Sie einen Texter briefen würden: Länge, HTML, Sprache. Sie können Platzhalter verwenden (3.19). Doppelte Anführungszeichen werden beim Speichern in einfache umgewandelt. |
| **Save Prompt** | – | Speichert die Vorlage. |
| **Go Back to Module Settings** | – | Kehrt ohne Speichern zur Liste zurück. |

Meldungen: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.**, **Unable to delete prompt template with id:** gefolgt von einer Nummer, **Failed to edit prompt template! Please fill the form with the right informations!**.

Die 16 Standardvorlagen sind: Product name 1–2, Product description 1–7 (die siebte bettet die Links zu den Produktbildern ein), Product meta title 1–3, Product meta description 1–3 und Product tags. Zwei der Vorlagen für Meta-Beschreibungen erwähnen eine Smartwatch; passen Sie sie vor der Nutzung an, wenn Sie etwas anderes verkaufen. Die Vorlagentexte sind in der Sprache gespeichert, die der Shop bei der Installation verwendete.

### 3.8 Settings – Playground

Öffnen Sie **Settings**, dann **Playground**. Er ist ein Schmierzettel: Er sendet eine freie Anweisung an das aktive Modell und zeigt die Antwort auf der Seite.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaigemini-settings-playground.webp)

1. Geben Sie die Anweisung in das große Feld ein ("Ask the model anything about your catalog").
2. Drücken Sie **Generate**.
3. Lesen Sie die Antwort unter dem Button, zusammen mit der Zahl der verbrauchten Tokens.

Sie können Shopname, Shopadresse, einen Produktnamen, eine Referenz oder Merkmale erwähnen, wenn die Antwort auf Katalogdaten beruhen soll. Studio-Regeln werden angewendet. Es wird kein Produkt-, Kategorie- oder Meta-Feld geändert, und der Aufruf wird in der History protokolliert. Ist das Feld leer, sehen Sie "Write a prompt first." Nutzen Sie den Playground, um den Schlüssel zu testen und einen Prompt zu verfeinern, bevor Sie ihn in eine Vorlage verwandeln.

### 3.9 Generate – Products

Öffnen Sie **Generate**, dann **Products**. Die Massengenerierung hat zwei Schritte. In Schritt 1 wird nichts an Gemini gesendet.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaigemini-generate-products.webp)

**Schritt 1 – Produkte filtern.** Alle Filter sind optional und werden nicht als Shop-Einstellungen gespeichert.

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Product Categories** | Nichts angehakt | Behält Produkte, die in einer der angehakten Kategorien liegen oder sie als Hauptkategorie haben. Ein leerer Baum filtert nicht nach Kategorie. |
| **Brand** | **Select brand** | Behält Produkte eines Herstellers. Die erste Option bedeutet jede Marke. |
| **Product status** | **Active** | **Active** behält Produkte im Verkauf, **Disabled** deaktivierte Produkte, **Both** alle. |
| **Product stock** | **All products** | **Only in stock products** schließt Produkte ohne verfügbare Menge aus. |
| **Update only** | **Update all** | Nutzt die History. Die erste Option behält Produkte, die dieses Modul nie beschrieben hat. Die zweite behält Produkte, die es bereits beschrieben hat. Die Beschriftungen sagen weiterhin "OpenAi content" (siehe Kapitel 5). |
| **Product IDs** | Leer | Geben Sie IDs durch Kommas getrennt ein, zum Beispiel 12,45,103. Nur diese Produkte können erscheinen. |
| **Product Reference** | Leer | Geben Sie eine oder mehrere Referenzen durch Kommas getrennt ein. |
| **Product Add Date From** / **Product Add Date To** | Leer | Behalten Produkte, die nach dem ersten und vor dem zweiten Datum angelegt wurden. |
| **Minimum product ID** / **Maximum product ID** | Leer | Behalten Produkte innerhalb dieses ID-Bereichs. |
| **Product Limit** | Leer | Maximale Zahl der in die Liste geladenen Produkte. Verwenden Sie beim ersten Mal eine kleine Zahl wie 20. |
| **Go to next step** | – | Erstellt die Liste. |
| **Module settings** | – | Button neben **Go to next step**. Er öffnet die Einstellungsseite eines anderen Moduls (siehe Kapitel 5); verwenden Sie stattdessen **Settings** in der Modulleiste. |

**Schritt 2 – schreiben.** Die Seite zeigt nun das Panel **Mass product generation** mit einer Tabelle der gefundenen Produkte (Spalten **ID**, **Reference**, **Result**).

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Template** | **Choose a template** | Kopiert den Text einer aktivierten Vorlage in das Feld darunter. Der Titel selbst wird nicht gesendet. |
| Großes Prompt-Feld | Leer | Die Anweisung, die für jedes Produkt gesendet wird. Platzhalter werden für jedes Produkt ausgefüllt (3.19). Lassen Sie das Feld leer, wird für jedes Feld eine Standardanweisung verwendet. |
| **What to generate** | **Descriptions** | **Descriptions** schreibt die lange und die kurze Beschreibung. **Meta title and meta description** schreibt beide Meta-Felder. **Descriptions and meta together** schreibt alle vier. Jedes Feld ist eine eigene Anfrage. Andere Felder (einschließlich Produktname und Tags) werden hier nie geändert. |
| **Existing text** | **Replace** | **Replace** überschreibt das Feld. **Skip if filled** lässt ein gefülltes Feld unberührt und sendet dafür nichts an Gemini. **Add above** und **Add below** behalten den alten Text und fügen den neuen davor oder danach an. |
| **Languages** | Die im Back Office verwendete Sprache ist angehakt | Haken Sie jede gewünschte Sprache an. Jede angehakte Sprache wird separat generiert. Mindestens eine muss angehakt sein ("Select at least one language."). |
| **Run on the list below** | – | Startet den Lauf. |

Während des Laufs zeigt die Zeile über dem Button den Fortschritt, zum Beispiel "3 / 40 – description". Jede Tabellenzeile zeigt ein Ergebnis wie "description: success Content successfully generated and updated to product." oder "description: skipped Product skipped." oder einen Fehlertext. Der Lauf nimmt die Produkte nacheinander und speichert jede Antwort sofort, sodass ein Fehler bei einem Produkt bereits gespeicherte nicht rückgängig macht. Schließen Sie die Seite nicht, bevor Sie "Finished … products." sehen.

### 3.10 Generate – Categories

Öffnen Sie **Generate**, dann **Categories**.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaigemini-generate-categories.webp)

**Schritt 1 – Kategorien filtern.**

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Categories** | Nichts angehakt | Haken Sie die einzubeziehenden Kategorien an. Ein leerer Baum schließt jede Kategorie ein, die zum Status passt. |
| **Category status** | **Active** | **Active**, **Disabled** oder **Both**. |
| **Go to next step** | – | Erstellt die Liste. Noch wird nichts generiert. |
| **Module settings** | – | Öffnet die Einstellungsseite eines anderen Moduls (siehe Kapitel 5). |

**Schritt 2 – schreiben.** Das Panel **Mass category generation** listet die Kategorien auf (Spalten **ID**, **Result**).

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| Großes Prompt-Feld | Leer | Die Anweisung, die für jede Kategorie gesendet wird. Sie können {category_name}, {category_description}, {category_parent_name} und die Shop-Platzhalter (3.19) verwenden. Tragen Sie hier immer einen Prompt ein: Für Kategorien gibt es keine Standardanweisung. |
| Feldliste | **Description** | **Description**, **Name**, **Meta title**, **Meta description** oder **Additional description**. Nur dieses Feld wird gespeichert. |
| Liste für vorhandenen Text | **Replace** | **Replace** überschreibt. **Skip if filled** lässt ein gefülltes Feld unberührt. |
| Sprachliste | Ihre Back-Office-Sprache | Eine Sprache pro Lauf. Starten Sie für eine weitere Sprache erneut. |
| **Run on the categories below** | – | Startet den Lauf. Jede Kategorie wird gespeichert, sobald ihre Antwort eintrifft. |

Unter der Tabelle befindet sich ein zweites Formular mit dem Titel **Generate category content** und einem Button **Generate content**. Er generiert nichts: Er bringt Sie nur zum Kategoriefilter zurück. Verwenden Sie immer **Run on the categories below**.

### 3.11 New product

Öffnen Sie **New product**. Dieser Bildschirm macht aus einem kurzen Briefing den Entwurf eines Produkts, das noch nicht existiert.

![New product](https://mypresta.eu/docs/images/docs/myaigemini-new-product.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **What is the product?** | Leer | Das Briefing. Schreiben Sie ein paar Sätze mit Materialien, Zielgruppe und Namen, die bleiben müssen. Ein reichhaltigeres Briefing liefert einen passenderen Entwurf. Ein leeres Briefing wird abgelehnt. |
| **Optional source URL** | Leer | Eine vollständige Adresse einer öffentlichen Seite über das Produkt. Text von der Seite (Titel, Beschreibung, Preis) wird Ihrem Briefing hinzugefügt. Ein leeres Feld oder eine Seite, die der Shop nicht lesen kann, wird ignoriert. |
| **Language** | Standardsprache des Shops | Die Sprache, in der Name, Beschreibungen, Meta und Tags gespeichert werden. Andere Sprachen werden nicht befüllt. Wählen Sie die Standardsprache des Shops, da PrestaShop darin einen Namen erwartet. |
| **Default category ID** | 2 | Die Nummer der Kategorie unter Catalog, Categories. 2 ist meist Home. Das neue Produkt wird in diese Kategorie gelegt und sie wird zur Standardkategorie. |
| **Generate data** | – | Bittet Gemini um einen Entwurf und gibt ihn darunter als strukturierten Text aus (Name, Beschreibungen, Meta, Tags, Referenz, Preis, Merkmale). Es wird kein Produkt gespeichert. |
| **Create product** | – | Speichert den Entwurf als neues aktives Produkt. Es setzt Name, Beschreibungen, Meta, Tags, Merkmale, Referenz und Preis aus dem Entwurf, Sichtbarkeit überall und einen Lagerbestand von 100. Es werden keine Bilder angehängt; fügen Sie diese danach hinzu (3.16). Ergebniszeile: "Product #" gefolgt von der neuen Produktnummer. |

Ist kein API-Schlüssel gespeichert, sehen Sie "Add an API key in the module settings first." Drücken Sie **Create product** vor **Generate data**, erscheint "Generate the product first." Prüfen Sie nach dem Anlegen Preis, Steuer und Bilder: Das Modul setzt die erste Steuerregelgruppe und den von Gemini vorgeschlagenen Preis.

### 3.12 Cron

Öffnen Sie **Cron**. Cron ist für den Server gedacht, nicht für eine Person: Ihr Server ruft nach einem Zeitplan eine geheime Webadresse auf, und der Shop füllt jedes Mal einen kleinen Stapel Produkte oder Kategorien. Es passiert nichts, bis der Server die Adresse anfordert.

![Cron](https://mypresta.eu/docs/images/docs/myaigemini-cron.webp)

Der Bildschirm hat zwei Formulare: eines für Produkte und eines für Kategorien. Jedes hat einen eigenen Button **Save**, und nach dem Speichern wird keine Bestätigungsmeldung angezeigt.

**Cron-Formular für Produkte**

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Enable Cron Feature** | **No** | Schalter für den gesamten Cron (Produkte und Kategorien). Solange er auf **No** steht, wird jeder Aufruf mit "Cron Job feature is disabled. You can enable it from the module settings." abgewiesen. Schalten Sie ihn erst ein, nachdem die übrigen Felder gespeichert sind. |
| **Cron Job Secret Token** | Ein langer Zufallswert | Das Passwort, das in der Adresse stehen muss. Ohne es weist der Shop den Aufruf ab. Wird es ersetzt, ist die alte Adresse ungültig. Der Button **Generate Token** neben dem Feld tut in dieser Version möglicherweise nichts; wenn nicht, tippen Sie selbst einen langen Wert ein. |
| **Update Field** | **description** | Welches einzelne Produktfeld der Cron umschreibt: **name**, **description**, **description_short**, **meta_title**, **meta_description** oder **tags**. Um mehrere Felder zu füllen, legen Sie mehrere Cron-Befehle an. |
| **Selected Products** | **pendingGemini** | Welche Produkte noch warten. **pendingGemini**: Produkte, die dieses Modul nie erfolgreich beschrieben hat (egal welches Feld). **pendingField**: Produkte, für die das gewählte Feld noch nicht generiert wurde, sodass ein Katalog von mehreren Cron-Jobs bearbeitet werden kann. **emptyField**: nur Produkte, deren gewähltes Feld in der gewählten Sprache leer ist. |
| **Product Categories** | Nichts angehakt | Begrenzt den Lauf auf angehakte Kategorien (Warnhinweis in Kapitel 5). |
| **Product ID list** | Leer | Ausdrückliche Produkt-IDs durch Kommas getrennt. Andere Zeichen als Ziffern werden beim Speichern entfernt. |
| **Language** | Standardsprache des Shops | Die Sprachversion, die geschrieben wird. |
| **Product to update** | 5 products | Stapelgröße pro Aufruf: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 oder 1000. Beginnen Sie mit 5 oder 10, damit ein langsames Modell das Zeitlimit des Servers nicht erreicht. Produkte werden in der Reihenfolge der ID genommen. |
| **Prompt Template** | Erste Vorlage der Liste | Die gespeicherte Anweisung, die für jedes Produkt verwendet wird. Platzhalter werden pro Produkt ausgefüllt (3.19). |
| **Enable Debug** | **No** | **Yes** lässt die Adresse den Plan ausgeben (Abfrage, gewählte Produkte, endgültige Prompts) und nichts speichern. Schalten Sie es aus, bevor der Server-Scheduler die Adresse verwendet. |
| **CRON JOB interval** | **Every Hour** | Ein Vorschlag für Ihre eigene Planung. Das Modul führt keinen Scheduler aus. Stellen Sie den tatsächlichen Takt auf Ihrem Server ein. |
| **Product Cron Job command** | – | Zeigt das Adresspräfix. In dieser Version ist die Befehlszeile auf dem Bildschirm unvollständig (siehe unten). |
| **Save** | – | Speichert die Cron-Einstellungen für Produkte. |

Das **Cron-Formular für Kategorien** hat ein eigenes **Cron Job Secret Token**, **Update Field** (**name**, **description**, **meta_title**, **meta_description**), **Selected categories** (dieselben drei Modi), **Language**, **Categories to update** (2–1000), **Prompt Template**, **Enable Debug**, **CRON JOB interval** und **Save**. Es überspringt immer die Stammkategorie (Root) des Shops.

**Die Adresse, die Sie dem Server geben.** Über den Formularen gibt der Bildschirm eine Produktadresse und eine Kategorieadresse aus, die jeweils nach dem Geheimnis enden. Dem Server muss außerdem gesagt werden, welcher Job laufen soll. Ergänzen Sie am Ende der Adresse vom Bildschirm Folgendes:

| Job | Vollständige Adresse | Hinweise |
|---|---|---|
| Produkte | `https://your-shop.example/module/myaigemini/cron?secret=PRODUCT_SECRET&action=generateProductContent` | Verwenden Sie das Geheimnis aus dem Produktformular. |
| Kategorien | `https://your-shop.example/module/myaigemini/cron?secret=CATEGORY_SECRET&action=generateCategoryContent` | Die Kategoriezeile auf dem Bildschirm endet mit `&entity=category`; ersetzen Sie dieses Ende durch `&action=generateCategoryContent`. |

Optionale Zusätze, die Sie anhängen können, um das gespeicherte Formular für einen Befehl zu überschreiben: für Produkte `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug=1`, `categories` (IDs durch Kommas getrennt), `productIds`; für Kategorien `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug=1`. Nicht angehängte Werte stammen aus dem gespeicherten Formular.

**Scheduler.** Legen Sie in Ihrem Hosting-Panel eine geplante Aufgabe an, die die vollständige Adresse öffnet, zum Beispiel mit `curl -s "ADDRESS"` jede Stunde. Testen Sie zuerst im Browser mit **Enable Debug** auf **Yes**: Sie sehen, welche Produkte verarbeitet würden, und die endgültigen Prompts. Stellen Sie es dann auf **No** und öffnen Sie die Adresse noch einmal. Jeder echte Aufruf aktualisiert einen Stapel und endet.

Antworten, die Sie beim Öffnen der Adresse sehen können:

| Antwort | Ursache | Was zu tun ist |
|---|---|---|
| **N products have been updated.** / **N categories have been updated.** | Der Stapel hat funktioniert. | Nichts. |
| **N pending products.** | Debug ist an, nichts wurde gespeichert. | Schalten Sie Debug aus, wenn Sie zufrieden sind. |
| **No products to update.** / **No categories to update.** | Nichts passt mehr zu **Selected Products** und den übrigen Filtern. | Der Job ist abgeschlossen, oder ändern Sie die Regel. |
| **Cron Job feature is disabled. You can enable it from the module settings.** | **Enable Cron Feature** steht auf **No**. | Stellen Sie es auf **Yes** und drücken Sie **Save**. |
| **The token does not exist or it's wrong!** | Das Geheimnis fehlt oder stimmt nicht überein. | Kopieren Sie die Adresse erneut vom Bildschirm. |
| **Invalid action!** | Die Adresse hat keinen Teil `action` oder einen falschen. | Ergänzen Sie den Teil `action` aus der obigen Tabelle. |
| **updatedField parameter is wrong!** | Das Feld ist für diesen Job nicht erlaubt. | Wählen Sie ein Feld aus dem Formular. |
| **All must include all mandatory parameters!** | Ein gespeicherter Wert (zum Beispiel die Vorlage) ist leer. | Wählen Sie ein **Prompt Template** und speichern Sie. |
| **productTarget parameter is wrong! Allowed values: …** | Der Modusname in der Adresse ist falsch. | Verwenden Sie einen der drei Modi. |
| **Error!** gefolgt von einer Meldung | Gemini hat abgelehnt oder ist gescheitert. | Lesen Sie die Meldung und prüfen Sie dann die History. |
| **Error! The model returned an empty response.** | Gemini hat nichts zurückgegeben, zum Beispiel weil das Limit Max Tokens zu niedrig war. | Erhöhen Sie **Max Tokens** auf dem Bildschirm **Gemini**. |
| **Monthly generation budget reached.** | Das Studio-Budget ist aufgebraucht. | Erhöhen Sie das Budget oder warten Sie bis zum nächsten Monat. |
| **Reply rejected by the studio quality gate.** | Die Antwort enthielt ein verbotenes Wort. | Passen Sie die Liste oder die Vorlage an. |
| **Error! Could not save product …** | PrestaShop hat den neuen Text abgelehnt (zum Beispiel zu lang). | Prüfen Sie das Feld und den Prompt. |

Ein Cron-Aufruf stoppt beim ersten Fehler und meldet, wie viele Elemente davor bereits aktualisiert wurden.

### 3.13 History

Öffnen Sie **History**. Sie ist das Protokoll dessen, was angefragt wurde und was zurückkam. Das Öffnen oder Filtern der Seite löscht nichts und ändert keine Produkte.

![History](https://mypresta.eu/docs/images/docs/myaigemini-history.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Today**, **7 days**, **30 days**, **This month**, **All time** | **This month** | Datumsvoreinstellungen. |
| **From** / **To** | Der aktuelle Monat | Ihr eigener Zeitraum. |
| **Model** | **Any** | Nur Anfragen mit diesem Modell. |
| **Type** | **Any** | Nur eine Art von Job, zum Beispiel eine Produktbeschreibung oder ein Kategorie-Meta-Titel. |
| **Status** | **Any** | **Success** oder **Error**. |
| **Language** | **Any** | Nur Anfragen für diese Sprache. |
| **Employee** | **Any** | Nur Anfragen, die dieser Back-Office-Benutzer gestartet hat. |
| **Product / category ID** | Leer | Eine Produkt- oder Kategorienummer. |
| **Prompt or reply contains** | Leer | Ein Wort, das im Prompt, in der Antwort oder im Fehlertext vorkommen muss. |
| **Filter** | – | Wendet die Filter an. |

Karten: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**. Ein Strich in einer Token-Spalte bedeutet, dass Gemini für diesen Aufruf keine Zahl zurückgegeben hat. Darunter gruppieren fünf Tabellen die gefilterten Anfragen: **By day**, **By model**, **By type**, **By language**, **By employee**, mit einem kleinen Balken für den Anteil der Tokens. Eine kleine kursive Zahl neben einer Aufrufzahl ist die Zahl der Fehler.

Die Liste unten hat die Spalten **ID**, **Status** (grünes **Success** oder rotes **Error**), **Prompt** (erste 180 Zeichen), **Reply / Error**, **Provider** (Dienst, Modell und Dauer), **Sent**, **Received**, **Total**, **Entity ID**, **Type**, **Timestamp** und einen Button **View**, der den vollständigen Prompt und die Antwort mit **Back to the list** öffnet. Die Liste zeigt 50 Zeilen pro Seite.

Der Symbolleisten-Button **Clear list** löscht alle History-Zeilen auf einmal, ohne nachzufragen. Tun Sie das nur mit Absicht: Die Restore-Buttons an Produkten, der monatliche Budgetzähler und die Cron-Modi **pendingGemini** und **pendingField** stützen sich alle auf die History, daher behandelt der Cron nach dem Leeren jedes Produkt als noch nicht beschrieben.

### 3.14 Images

Öffnen Sie **Images**. Dieser Bildschirm schaltet nur die Produktfotosuche ein oder aus und speichert deren Anweisung. Er lädt keine Bilder herunter.

![Images](https://mypresta.eu/docs/images/docs/myaigemini-images.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **AI Image Finder** | Enabled | Zeigt den Tab **Photos** auf der Produktseite. Deaktiviert blendet ihn aus. |
| **AI Image Search Prompt** | Eingebaute englische Anweisung | Die Anweisung, die Gemini nach Seitenadressen fragt, auf denen Fotos dieses Produkts wahrscheinlich zu finden sind. {product_name} und {product_description} werden für das aktuelle Produkt ersetzt. Behalten Sie die Bitte um eine einfache Liste von Adressen bei. |
| **Save** | – | Speichert beide Felder. Meldung: **Settings saved.** |

Die Suche findet Webseiten, die Ihr Produkt bereits zeigen; sie erzeugt keine Bilder. Prüfen Sie, dass Sie das Recht haben, jedes importierte Bild zu verwenden.

### 3.15 Updates

Öffnen Sie **Updates** (ganz rechts in der Modulleiste). Die Seite prüft bei MyPresta.eu, ob es eine neuere Moduldatei gibt. Sie ändert Ihren Katalog nicht und installiert nichts.

![Updates](https://mypresta.eu/docs/images/docs/myaigemini-updates.webp)

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| **Manual Check** (**Check Now**) | – | Fragt einmalig sofort an. Sie sehen **Module is up to date!** oder **New version available!**. |
| **Automatic Notifications** | Schalter Enabled oder Disabled | Enabled: Etwa alle drei Tage prüft das Back Office und zeigt ein Warnbanner mit Link, wenn eine neuere Version existiert. Diese Einstellung wird mit anderen MyPresta-Modulen im selben Shop geteilt. |
| **Product Page** | – | Ein Link zur Modulseite auf MyPresta.eu, wo Sie lesen können, was sich geändert hat, und die Datei herunterladen. |
| **Save** | – | Speichert die Benachrichtigungseinstellung. Meldung: **Update settings saved.** |

### 3.16 Arbeiten auf der Produktbearbeitungsseite

Öffnen Sie **Catalog**, **Products**, bearbeiten Sie ein Produkt und öffnen Sie **Modules**, dann **My AI Gemini**. Das Produkt muss bereits einmal gespeichert sein. Das Panel erscheint, wenn **Product edit page Form** oder **Product Edit History** (3.4) aktiviert ist.

![Produktbearbeitungsseite – Panel My AI Gemini](https://mypresta.eu/docs/images/docs/myaigemini-product-edit.webp)

Das Panel hat bis zu vier Tabs: **Generate**, **Simulate**, **Photos** und **History**.

**Tab Generate**

| Feld | Beim Start | Was es bewirkt |
|---|---|---|
| Buttons **Language** | Die erste Sprache | Wählen Sie, welche Sprachversion geschrieben wird. **Every language** schreibt alle aktiven Sprachen nacheinander. |
| **If the field already has text** | **Replace** | **Replace**, **Add above**, **Add below** oder **Skip if filled**. Skip sendet für ein gefülltes Feld nichts an Gemini. |
| Feldkarten | – | **Description**, **Short description**, **Name**, **Meta title**, **Meta description**, **Tags**. Drücken Sie auf der Karte **Fill**, um genau dieses Feld zu schreiben und sofort im Produkt zu speichern. |
| **SEO pack** – **Fill all** | – | Schreibt Name, beide Beschreibungen und beide Meta-Felder in einer Anfrage und speichert sie. |
| **Use your own instruction or a saved prompt** | Eingeklappt | Klappen Sie es auf, um gespeicherte Vorlagen nach Titel oder Text zu filtern, eine Kachel (**Standard brief** oder eine aktivierte Vorlage) zu wählen und das Feld **Instruction** zu bearbeiten. Ist das Feld leer, verwendet **Fill** eine Standardanweisung für das Feld. |

Die Antwort wird unter dem Panel ausgegeben. Der Text wird sofort im Produkt gespeichert, doch die Felder des geöffneten Produktformulars aktualisieren sich nicht von selbst: Laden Sie die Produktseite neu, bevor Sie bearbeiten und im Formular speichern, sonst können die alten Werte im Formular den neuen Text überschreiben.

**Tab Simulate.** Gleiche Sprachauswahl und gleiche Feldkarten, aber die Buttons heißen **Try**. Die Antwort bleibt auf dieser Seite, und das Produkt wird nicht verändert. Nutzen Sie ihn, um die Formulierung zuerst zu prüfen.

![Produktbearbeitungsseite – Tab Photos](https://mypresta.eu/docs/images/docs/myaigemini-product-photos.webp)

**Tab Photos.** Drücken Sie **Find pages**. Das Modul fragt Gemini nach bis zu 5 Seiten, die dieses Produkt wahrscheinlich zeigen, liest daraus bis zu 24 Bilder und zeigt sie als kleine Vorschaubilder. Haken Sie die gewünschten an und drücken Sie **Add selected to this product**. Das erste angehakte Bild wird zum Titelbild, wenn Sie mehrere hinzufügen. Vor dem Drücken des Buttons wird nichts gespeichert. Die Zeile unter den Buttons zeigt den Fortschritt: "Looking for photos…", "Reading photos…", "Tick the photos you want, then add them to this product." Laden Sie nach dem Hinzufügen die Produktseite neu, um sie zu sehen. Ist der Schalter aus, sehen Sie einen Hinweis, **AI Image Finder** unter **Settings**, **General** zu aktivieren.

**Tab History.** Eine Tabelle mit **When**, **Type**, **Status** und einem Button **Restore** für jeden erfolgreichen Schreibvorgang, der einen vorherigen Wert gesichert hat. Drücken Sie **Restore**, bestätigen Sie "Restore the previous value?", und der vorherige Text kehrt zurück. Fehlgeschlagene Zeilen haben keinen Button. Ein wiederhergestelltes SEO pack bringt Name, beide Beschreibungen und beide Meta-Felder zurück. Ohne Zeilen sehen Sie "No generations for this product yet."

**Generate with AI-Buttons neben Feldern.** Auf der Produktseite fügt das Modul außerdem einen Button **Generate with AI** neben den Feldern Beschreibung, Kurzbeschreibung, Meta-Titel und Meta-Beschreibung hinzu. Hat der Shop mehr als eine Sprache, fragt er "Generate this field for the current language, or for every active language?" mit **Current language**, **All languages** und **Cancel**. Der Text geht nur in das geöffnete Formular: "Text is in the field. Save the product to keep it." Andere Felder werden nicht geändert. Bei einem Produkt, das noch nie gespeichert wurde, sehen Sie "Save the product once before generating."

### 3.17 Arbeiten auf der Kategoriebearbeitungsseite

Bearbeiten Sie eine Kategorie unter **Catalog**, **Categories**. Neben den Feldern Beschreibung, zusätzliche Beschreibung, Meta-Titel und Meta-Beschreibung fügt das Modul den Button **Generate with AI** hinzu. Er funktioniert genau wie bei Produkten: Wählen Sie die aktuelle Sprache oder alle Sprachen, der Text wird in das Formular eingefügt, und Sie speichern die Kategorie, um ihn zu behalten ("Text is in the field. Save the category to keep it."). Eine Kategorie, die noch nie gespeichert wurde, zeigt "Save the category once before generating." Das gleiche Prompt-Fenster der oberen Leiste (3.18) funktioniert auch auf Kategorie-, CMS-Seiten- und Markenseiten und protokolliert sie in der History.

### 3.18 Shortcuts: obere Leiste, Produktliste und Help

- **Button in der oberen Leiste.** Bei aktiviertem **Admin Top Bar CTA** sitzt ein Zauberstab-Symbol in der oberen Leiste. Es öffnet das Fenster **My AI Gemini** mit einer Liste **Template**, einem Textfeld und **Generate**. Die Antwort wird unter dem Button angezeigt, mit der Zahl der Tokens. Es ändert kein Feld. Schließen Sie mit **×**.
- **Produktliste.** In der Produktliste unter **Catalog**, **Products** fügt das Modul einen Link **My AI Gemini** neben den Sammelaktionen oder in der Symbolleiste hinzu. Er öffnet **Generate**, **Products**.
- **Help.** Der Button **Help** auf jeder Modulseite öffnet die Erklärung der Seite.

### 3.19 Platzhalter, die Sie in Prompts verwenden können

In Vorlagen, im Feld **Instruction**, in den Massen-Prompt-Feldern und im Playground können Sie Platzhalter in geschweiften Klammern schreiben. Das Modul ersetzt sie vor dem Senden der Anweisung für jedes Element durch echte Daten.

| Platzhalter | Funktioniert für | Wozu er wird |
|---|---|---|
| {product_name}, {product_description}, {product_description_short}, {product_tags}, {product_reference}, {product_ean13}, {product_weight} | Produkte | Die eigenen Daten des Produkts in der gewählten Sprache. |
| {product_default_category}, {product_category_description}, {product_categories}, {product_brand} | Produkte | Name und Beschreibung der Hauptkategorie, alle Kategorienamen (durch Kommas getrennt), Markenname. |
| {product_attributes}, {product_features}, {product_feature_values} | Produkte | Kombinationsattribute, Merkmalsnamen und Paare aus Merkmalsname:Wert. |
| {product_images} | Produkte | Die Links zu den Produktbildern, durch Kommas getrennt. |
| {category_name}, {category_description}, {category_parent_name} | Kategorien | Die eigenen Daten der Kategorie und der Name der übergeordneten Kategorie. |
| {cms_title}, {brand_name}, {brand_description}, {brand_short_description} | CMS-Seiten, Marken (Fenster der oberen Leiste) | Der Seitentitel oder die Markendaten. |
| {shop_name}, {shop_url}, {shop_language}, {shop_country}, {shop_currency} | Alles | Shopname, Domain, Sprachname, Standardland und Code der Standardwährung. |

Ein Platzhalter ohne Daten wird zu leerem Text. Platzhalter für Kategorien werden in Produkt-Prompts nicht ersetzt und umgekehrt.

## 4. Shop-Frontend

My AI Gemini hat keine Kundenoberfläche. Es fügt nichts zu Produktseiten, Kategorieseiten, Warenkorb, Footer oder Kundenkonto hinzu, und im Theme gibt es nichts ein- oder auszuschalten. Das Shop-Frontend erhält kein Modul-Template, daher wird kein Screenshot gezeigt.

Das Modul besitzt zwei Webadressen, die keine Seiten für Kunden sind:

| Adresse | Wer sie nutzt | Was zu beachten ist |
|---|---|---|
| Cron-Adresse (`…/module/myaigemini/cron?secret=…&action=…`) | Der Scheduler Ihres Servers | Beschrieben in 3.12. Ohne das richtige Geheimnis geöffnet antwortet sie nur "The token does not exist or it's wrong!". Halten Sie sie geheim: Wer sie kennt, kann einen Stapel starten. |
| Interne Adresse der Modulbildschirme | Die eigenen Buttons des Moduls im Back Office | Nicht öffnen oder weitergeben. Sie weist Anfragen ohne das eigene Geheimnis des Moduls ab ("Error! Invalid token!"). |

## 5. Probleme

**Es wird nichts generiert, und ich sehe die Meldung "The Gemini API key is not set. Add it in the module settings."**
Das Schlüsselfeld unter **Settings**, **Gemini** ist leer. Fügen Sie den Schlüssel von https://aistudio.google.com/apikey ein und drücken Sie **Save**.

**Ein Fehler von Google erscheint in einem Ergebnis, in der History oder in einer Cron-Antwort (zum Beispiel eine Meldung, die mit "Google Gemini API Error" beginnt).**
Google hat den Aufruf abgelehnt: falscher oder deaktivierter Schlüssel, ein Modell, das Ihr Schlüssel nicht nutzen darf, ausgeschöpfte kostenlose Limits oder eine gesperrte Region. Öffnen Sie die **History**, drücken Sie in der roten Zeile **View**, um den vollständigen Text zu lesen. Korrigieren Sie den Schlüssel oder wählen Sie unter **Settings**, **Gemini** ein anderes Modell und versuchen Sie es erneut.

**"Gemini request timed out after … seconds. The model may be overloaded, or the timeout is too low for this prompt."**
Das Modell brauchte länger als **API timeout (seconds)**. Erhöhen Sie das Timeout unter **Settings**, **General** (bis 600), kürzen Sie den Text oder wählen Sie ein schnelleres Modell wie gemini-2.0-flash.

**"The model hit the token limit before returning any text. Increase "Max Tokens" …" oder "The model returned an empty response."**
Die Antwort wurde abgeschnitten oder ist leer. Erhöhen Sie **Max Tokens** unter **Settings**, **Gemini**. Einige Gemini-2.5-Modelle verbrauchen einen Teil des Limits zum „Nachdenken“.

**"The response was blocked by the provider content filter. Try rewording the prompt."**
Google hat die Antwort auf die Anweisung verweigert. Formulieren Sie die Vorlage oder den verwendeten Produkttext um.

**"Monthly generation budget reached. Raise it in the studio settings or wait until next month."**
Die Grenze unter **Settings**, **Studio**, **Monthly generation budget** ist aufgebraucht. Erhöhen Sie sie oder setzen Sie 0 für kein Limit.

**"The reply was rejected because it contains a forbidden word from the studio settings."**
**Quality gate** ist aktiviert, und die Antwort enthielt eine Zeile aus **Forbidden words**. Das Produkt blieb unverändert. Passen Sie die Liste an, ändern Sie den Prompt oder deaktivieren Sie das Gate.

**"Error! Prompt is missing or too short!"**
Die Anweisung hat weniger als 4 Zeichen. Geben Sie eine vollständige Anweisung ein oder wählen Sie eine Vorlage.

**Eine Zeile eines Massenlaufs zeigt "skipped Product skipped."**
**Existing text** steht auf **Skip if filled**, und das Feld hatte bereits Text. Wählen Sie **Replace**, **Add above** oder **Add below**, um trotzdem zu schreiben.

**Nachdem ich ein hinzugefügtes Modell entfernt habe, scheitert jede Anfrage.**
Das Entfernen des aktiven Modells setzt den Modellnamen auf gpt-4o zurück, den Gemini nicht kennt. Öffnen Sie **Settings**, **Gemini**, wählen Sie in **Model** einen Gemini-Namen (zum Beispiel gemini-2.0-flash) und drücken Sie **Save**.

**Bildschirme sagen weiterhin "OpenAi" oder "gpt".**
Diese Version enthält noch einige Formulierungen aus einer älteren Ausgabe: die Bestätigung **OpenAi Settings Updated**, den Fehler **OpenAi Model field is invalid!**, die Filterbeschriftungen "Products that have not been updated with OpenAi content" und "Products that already have been updated with OpenAi content" unter **Generate**, **Products**, das Beispiel "gpt-4.1" im Modellfeld und in der Meldung "Enter a model id such as gpt-4.1.", den Dienstnamen "openai" in der Spalte **Provider** der History und die Zeile "Paste the secret key from your OpenAI account" im **Help**-Panel. All das sind nur Formulierungen. Das Modul ruft Google Gemini auf. Verwenden Sie einen Schlüssel von https://aistudio.google.com/apikey und Gemini-Modellnamen.

**Der Button "Module settings" unter Generate öffnet die Seite eines anderen Moduls oder einen Fehler.**
Dieser Button verweist auf die Einstellungen eines älteren Schwestermoduls und nicht auf dieses. Verwenden Sie **Settings** in der Modulleiste.

**Das untere Formular "Generate category content" tut nichts.**
Es lädt nur den Kategoriefilter neu. Drücken Sie **Run on the categories below** im Panel darüber.

**Der Produkt-Cron tut nichts.**
Prüfen Sie in dieser Reihenfolge: **Enable Cron Feature** steht auf **Yes** und ist gespeichert; die Adresse enthält `&action=generateProductContent`; das Geheimnis in der Adresse stimmt mit dem Bildschirm überein; ein **Prompt Template** ist gewählt; **Enable Debug** steht auf **No**; Ihr Server ruft die Adresse tatsächlich auf (Scheduler-Log ansehen). Ein Browsertest mit **Enable Debug** auf **Yes** gibt aus, was laufen würde.

**Der Cron-Befehl auf dem Bildschirm endet direkt nach dem Geheimnis, und der Button "Generate Token" tut nichts.**
Bekannte Einschränkung dieser Version. Die Befehlszeile wird von der Seite nicht vervollständigt, und der Token-Button füllt das Feld nicht. Bauen Sie die Adresse selbst wie in 3.12 gezeigt und tippen Sie ein langes Geheimnis ein, wenn Sie es ändern möchten.

**Der Cron schreibt Produkte in einer angehakten Kategorie immer wieder um.**
Ist **Product Categories** angehakt, werden bei jedem Aufruf Produkte ausgewählt, deren Hauptkategorie angehakt ist, auch wenn sie bereits beschrieben wurden. Lassen Sie für geplante Läufe den Kategoriebaum leer und begrenzen Sie den Lauf mit **Product ID list**, oder nutzen Sie **Enable Debug**, um vor der Planung zu prüfen, welche Produkte gewählt werden.

**Der Cron verarbeitet dieselben Produkte erneut, nachdem ich die History geleert habe.**
Die Cron-Modi **pendingGemini** und **pendingField** nutzen die History, um zu wissen, was bereits geschrieben ist. Nach **Clear list** gilt alles als nicht geschrieben. Verwenden Sie **emptyField**, wenn gefüllte Felder unberührt bleiben sollen.

**Top P, Frequency Penalty und Presence Penalty ändern nichts.**
In dieser Version werden nur **Temperature** und **Max Tokens** an Gemini gesendet. Die anderen drei werden gespeichert, aber nicht verwendet.

**Der Menüeintrag "AI Content Generator" fehlt.**
Öffnen Sie noch einmal eine beliebige Back-Office-Seite; das Modul setzt den Eintrag zurück. Fehlt er weiterhin, deinstallieren und installieren Sie das Modul erneut (das löscht History und Einstellungen).

**Kein Panel "Modules → My AI Gemini" auf der Produktseite.**
Prüfen Sie, ob **Product edit page Form** (oder **Product Edit History**) unter **Settings**, **General** aktiviert ist, ob das Produkt einmal gespeichert wurde und ob Sie den Tab **Modules** des Produkts öffnen. Die Buttons **Generate with AI** neben den Feldern werden vom Modul separat hinzugefügt und können sichtbar bleiben, auch wenn das Panel abgeschaltet ist.

**Der generierte Text ist verschwunden, nachdem ich das Produkt gespeichert habe.**
Das Produktformular war mit den alten Werten geöffnet. Laden Sie die Produktseite nach der Verwendung von **Fill** neu und bearbeiten Sie erst danach. Nutzen Sie **Restore** im Tab **History**, um einen früheren Text zurückzuholen.

**Der Dashboard-Block im Haupt-Dashboard von PrestaShop ist leer.**
Dieser Block erhält keine History-Zahlen. Öffnen Sie **AI Content Generator**, **Dashboard**.

**Fotosuche: "The search did not return photos. Reload the product page and try again." oder "No photos were found on the suggested pages."**
Gemini hat Seiten vorgeschlagen, die nicht gelesen werden konnten oder keine geeigneten Bilder enthielten. Drücken Sie erneut **Find pages** oder verbessern Sie **AI Image Search Prompt** unter **Images**. Seiten mit privaten oder lokalen Adressen werden abgelehnt.

**New product zeigt "Failed to parse AI response. Please try again." oder "Failed to create product".**
Gemini hat keinen brauchbaren Entwurf geliefert, oder der Shop hat die Daten abgelehnt (zum Beispiel eine Sprache ohne Namen in der Standardsprache). Drücken Sie erneut **Generate data**, wählen Sie die Standardsprache des Shops und prüfen Sie die Kategorienummer.

## 6. Für Entwickler

### 6.1 Überblick

| Element | Wert | Wo definiert |
|---|---|---|
| Technischer Name | `myaigemini` | Hauptdatei des Moduls |
| Hauptklasse | `myaigemini` (extends `Module`) | Hauptdatei des Moduls |
| Version | **1.1.0** | Hauptdatei des Moduls |
| Anzeigename | My AI Gemini - AI content generation | Hauptdatei des Moduls |
| Autor | MyPresta.eu | Hauptdatei des Moduls |
| Tab | `front_office_features` | Hauptdatei des Moduls |
| PrestaShop | 1.6 – 9.99.99 (`ps_versions_compliancy`) | Hauptdatei des Moduls |
| PHP | 7.0 oder neuer (`MIN_PHP_VERSION`, geprüft in `install()`) | Hauptdatei des Moduls |
| API | Google Gemini unter `https://generativelanguage.googleapis.com/v1beta`, Schlüssel als Query-Parameter `key` | Hauptdatei des Moduls |
| Schlüsselquelle | https://aistudio.google.com/apikey | Hauptdatei des Moduls |
| Konfigurationspräfix | `MYPRESTA_MYAIGEMINI_` | Hauptdatei des Moduls |
| CSS-Präfix | `.mag-` (sowie `.myaigemini-ui`, `.myaigemini-stats`) | Hauptdatei des Moduls |

Datenfluss: Ein Bildschirm (Produktpanel, Massenlauf, Fenster der oberen Leiste, Playground) sendet per POST an den Front-Controller `ajax` des Moduls mit dem geheimen Token; der Controller baut den Prompt (Vorlage, Platzhalter, `Studio::decorate`), ruft `OpenAIService` auf (ein Gemini-Client unter seinem alten Klassennamen), schreibt das Ergebnis in das Produkt oder die Kategorie und fügt eine Zeile in `myaigemini_log` ein. Der Cron arbeitet genauso über den Front-Controller `cron`. Generierter Text wird mit `Product::save()` oder `Category::save()` gespeichert.

URL-Parameter auf der Konfigurationsseite: `mag_tab` (`dashboard`, `settings`, `updates`), `mag_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` ist der Tab **Gemini**; unter **Generate** `products` und `categories`), Dashboard-Zeitraum `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`), `mag_from`, `mag_to`. In der History: `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`.

### 6.2 Dateien

| Datei | Zweck | Bereich |
|---|---|---|
| `myaigemini.php` | Hauptklasse: Installation und Deinstallation, Konfigurationsformulare (General, Gemini, Studio, Vorlagen), Dashboard, Hooks, Menüplatzierung, Modellkatalog. | Modulcode |
| `autoload.php` | Lädt die Modulklassen ohne Composer. | Modulcode |
| `src/OpenAIService.php` | Gemini-Client (`generateContent`, `models`); Timeouts; merkt sich Parameter, die ein Modell ablehnt. | Modulcode |
| `src/Studio.php` | Prompt-Dekoration, Monatsbudget, Prüfung verbotener Wörter, SEO pack und Prompts für Alt-Texte. | Modulcode |
| `controllers/admin/AdminMyAIGeminiMain.php` | Menüeintrag; leitet zum Dashboard weiter. | Modulcode |
| `controllers/admin/AdminMyAIGeminiSettings.php` | Versteckt; leitet zu Settings weiter. | Modulcode |
| `controllers/admin/AdminMyAIGemini.php` | **Generate** (Filter und Massenpanels). | Modulcode |
| `controllers/admin/AdminMyAIGeminiProductCreator.php` | **New product**. | Modulcode |
| `controllers/admin/AdminMyAIGeminiCron.php` | **Cron**-Formulare. | Modulcode |
| `controllers/admin/AdminMyAIGeminiUsage.php` | **History**. | Modulcode |
| `controllers/admin/AdminMyAIGeminiImageFinder.php` | Formular **Images** und Aktionen der Fotosuche. | Modulcode |
| `controllers/front/ajax.php` | JSON-Aktionen, die von den Bildschirmen genutzt werden. | Modulcode |
| `controllers/front/cron.php` | Cron-Endpunkt. | Modulcode |
| `lib/sectionHelp.php` | Text des Help-Panels. | Modulcode |
| `lib/updateChecker.php` | Update-Prüfung (`myaigeminiUpdate`). | Modulcode |
| `lib/prestashop9compatibility.php`, `lib/searchTool/` | Kompatibilitätshelfer und das Suchwerkzeug des Moduls. | Modulcode |
| `views/templates/hook/*.tpl`, `views/templates/admin/product_creator.tpl` | Bildschirme. | Modulcode |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | Verhalten der Bildschirme. | Modulcode |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Stile. | Modulcode |
| `translations/*.php` | Sprachdateien (viele Sprachen). | Modulcode |

Referenzierte, aber nicht mitgelieferte Assets: `views/js/admin.js`, `views/css/admin.css` (Controller Main und Settings), `views/js/product_creator.js` und `views/css/product_creator.css` (Controller New product). Sie werden stillschweigend übersprungen; die Buttons von New product werden von `back.js` verarbeitet.

### 6.3 Controller

| Controller | Klasse und Menü-Elternteil | Hinweise |
|---|---|---|
| `AdminMyAIGeminiMain` | `AdminMyAIGeminiMainController` (Elternteil: Bereich Modules) | Sichtbarer Eintrag **AI Content Generator**. `initContent()` leitet auf die Konfigurationsseite mit `mag_tab=dashboard` um. |
| `AdminMyAIGemini` | `AdminMyAIGeminiController` (Elternteil: AdminMyAIGeminiMain) | Versteckter Tab (`active = 0`). **Generate**. `mag_sub` `products` / `categories`; Submit-Namen `filterProducts`, `filterCategories`. |
| `AdminMyAIGeminiProductCreator` | `AdminMyAIGeminiProductCreatorController` (Elternteil: AdminMyAIGeminiMain) | Versteckt. AJAX `generateProductData`, `extractImages`, `createProduct`, `generateImages` (Platzhalterantwort "coming soon"). |
| `AdminMyAIGeminiSettings` | `AdminMyAIGeminiSettingsController` (Elternteil: AdminMyAIGeminiMain) | Versteckt. Nur Weiterleitung. |
| `AdminMyAIGeminiCron` | `AdminMyAIGeminiCronController` (Elternteil: AdminMyAIGeminiMain) | Versteckt. Submit `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGeminiUsage` | `AdminMyAIGeminiUsageController` (Elternteil: AdminMyAIGeminiMain) | Versteckt. `clear_log` leert die Log-Tabelle. |
| `AdminMyAIGeminiImageFinder` | `AdminMyAIGeminiImageFinderController` (Elternteil: AdminMyAIGeminiMain) | Versteckt. Aktionen `searchImages`, `extractImages` (private Hosts abgelehnt), `saveImages`. Formular-Submit `submitImageFinder`. |
| `ajax` (front) | `myaigeminiajaxModuleFrontController` (Elternteil: –) | Erfordert `secret_token` gleich `MYPRESTA_MYAIGEMINI_TOKEN`, sonst "Error! Invalid token!". Aktionen: `initiatePrompt`, `updateSettings`, `updateProduct`, `initiateProductRestore`, `updateCategory`, `generateSeoPack`, `generateAltTexts` (kein Button ruft diese auf). |
| `cron` (front) | `MyAIGeminiCronModuleFrontController` (Elternteil: –) | Erfordert `MYPRESTA_MYAIGEMINI_ENABLE_CRON` und ein `secret` gleich `_SECRET` oder `_CAT_SECRET` (jedes Geheimnis öffnet beide Aktionen). `action` = `generateProductContent` oder `generateCategoryContent`. |

Die Filterformulare von Generate verlinken "Module settings" auf `configure=mychatgpt`. Die Hook-Ausgabe des Produktbearbeitungspanels wird in `renderProductModulesContent()` erzeugt.

Cron-Auswahl-SQL: Der Kategoriefilter und die Produkt-ID-Liste werden an die WHERE-Klausel angehängt; die Kategoriebedingung (`id_product IN (…) OR id_category_default IN (…)`) ist nicht in Klammern gesetzt, sodass das OR die gesamte Bedingung erweitert. `pendingGemini` und `pendingField` verwenden `NOT EXISTS` auf `myaigemini_log`-Zeilen, deren Status leer oder nicht `error` ist; `pendingField` stimmt außerdem mit `type = product_<field>` / `category_<field>` ab. `emptyField` verbindet `product_lang` / `category_lang` für die gewählte Sprache. Textlängen beim Speichern von Produkten: Name 128, Kurzbeschreibung 799 (Cron) oder 800 (ajax), Meta-Titel 69, Meta-Beschreibung 159.

### 6.4 Hooks

In `install()` registriert: `displayAdminProductsMainStepLeftColumnMiddle` (gibt einen leeren String zurück), `displayAdminProductsMainStepLeftColumnBottom` (leer), `actionProductFormBuilderModifier` (keine Aktion), `displayAdminProductsExtra` (rendert das Panel im Tab **Modules** des Produkts), `displayBackOfficeHeader` (lädt Assets, führt `ensureLongSecrets()` und `placeModuleMenu()` aus, registriert den Tab der Bildersuche einmalig, fügt JS-Variablen hinzu), `displayBackOfficeTop` (das Fenster der oberen Leiste, wenn `TOPCTA` an ist, und JS-Variablen für Kategorie-, CMS- und Marken-IDs), `displayFooter` (leer), `displayHeader` (leer), `dashboardZoneTwo` (rendert `dashboard.tpl` ohne seine Daten). `actionProductGridDataModifier` existiert als Methode, ist aber nicht registriert. Das Modul hat keine Methoden `enable()` und `disable()`. Das Modul stellt keine eigenen Hooks bereit.

`hookDisplayBackOfficeHeader` lädt `product-fields.js` auf den Bearbeitungsseiten für Produkte und Kategorien unabhängig vom Schalter `MYPRESTA_MYAIGEMINI_PRODUCT` (der Schalter steuert nur das Panel im Tab Modules).

### 6.5 Overrides

Das Modul hat keine Overrides. Es ersetzt keine Core-Datei.

### 6.6 Datenbank

| Tabelle | Inhalt | Hinweise |
|---|---|---|
| `myaigemini_prompt` | `id_prompt` (PK), `status`, `title` (128), `prompt` (text), `date_generated`. 16 Zeilen werden bei der Installation eingefügt. | Bei der Installation angelegt, bei der Deinstallation gelöscht |
| `myaigemini_log` | `id_log` (PK), `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, `old_` / `new_`-Paare für `name`, `description`, `description_short`, `meta_title`, `meta_description`, `tags`, `date_updated`. Indizes auf `id_product` und `status`. | Bei der Installation angelegt, bei der Deinstallation gelöscht |

Beide Tabellen nutzen die Datenbank-Engine des Shops und werden bei der Deinstallation gelöscht. Die drei Token-Spalten werden außerdem zur Laufzeit von `ensureUsageColumns()` hinzugefügt, wenn Dashboard, History oder ein Cron-/Ajax-Log-Eintrag sie benötigt und sie fehlen. `ai_service` speichert immer den Wert `openai` (Überbleibsel). `postProcess()` des Massengenerators schreibt die übermittelten Filterwerte in Konfigurationsschlüssel wie `MYPRESTA_MYAIGEMINI_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_*`, `_CATEGORIES`, `_BRANDS`, jedes Mal wenn **Generate** geladen wird. Die Deinstallation löscht diese Schlüssel nicht.

### 6.7 Konfigurationsschlüssel und Übersetzungen

Präfix `MYPRESTA_MYAIGEMINI_`. Von `install()` geschriebene Werte:

| Schlüssel | Standard | Bedeutung |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | `0`, `0` | Schalter für Live und Debug (`PrestaShopLogger` mit Objekttyp `MyAIGemini`). |
| `TIMEOUT` | `120` | Sekunden; auf 10–600 begrenzt; das Browser-Timeout ist dieser Wert plus 15. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT` | `1`, `1`, `1` | Wiederherstellungsliste, Fenster der oberen Leiste, Produktpanel. |
| `IMAGEFINDER_ENABLE`, `IMAGEFINDER_PROMPT` | `1`, eingebauter Text | Schalter und Anweisung der Fotosuche. `IMAGEFINDER_TAB_OK` markiert die einmalige Tab-Reparatur. |
| `TOKEN`, `SECRET`, `CAT_SECRET` | zufällige 32 Zeichen | Ajax-Token, Geheimnis des Produkt-Crons, Geheimnis des Kategorie-Crons. Werte unter 24 Zeichen werden auf der nächsten Back-Office-Seite neu erzeugt. |
| `API_KEY` | ein einzelnes Leerzeichen | Getrimmt gespeichert; das Formular behält den gespeicherten Schlüssel, wenn das Feld leer ist. |
| `MODEL`, `EXTRA_MODELS` | `gemini-2.0-flash`, leer | Aktives Modell und hinzugefügte Namen (einer pro Zeile). Das Entfernen des aktiven hinzugefügten Modells setzt `gpt-4o`. |
| `TEMPERATURE`, `MAX_TOKENS` | `0.7`, `3200` | Werden als `temperature` und `maxOutputTokens` an Gemini gesendet. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | `1`, `0`, `0` | Gespeichert; nicht in der Gemini-Anfrage enthalten. |
| `MODEL_CAPS` | leer | Gelernte Parameter pro Modell. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | leer | Studio-Texte. |
| `BUDGET`, `QUALITY` | `0`, `1` | Monatsgrenze; Quality gate. |
| `ENABLE_CRON` | `0` | Globaler Cron-Schalter. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | `6`, `6` | Intervallauswahl (6 = Every Hour). Nur gespeichert; für die Anzeige verwendet. |
| `updatedField`, `catupdatedField` | `description`, `description` | Cron-Feld (die Schlüsselnamen werden als `MYPRESTA_MYAIGEMINI_updatedField` usw. geschrieben). |
| `productTarget`, `categoryTarget` | `pendingGemini` | Cron-Auswahlmodus. |
| `productsToUpdate`, `categoriesToUpdate` | `5`, `5` | Stapelgröße. |
| `promptTemplateId`, `catpromptTemplateId` | leer | Cron-Vorlage. |
| `languageId`, `catlanguageId` | `PS_LANG_DEFAULT` | Cron-Sprache. |
| `debug`, `catdebug`, `interval_select` | `0`, `0`, leer | Cron-Debug und alte Auswahl. |
| `productIdsList`, `categories` | leer | Cron-Filter. |

Die Deinstallation löscht die obigen Schlüssel sowie `ACTIVE_SERVICE`, `GEMINI_API_KEY` und `GEMINI_MODEL` (alte Namen), die Tabs und beide Tabellen. Das Back Office entfernt außerdem bei jedem Laden der Konfigurationsseite `GEMINI_API_KEY`, `GEMINI_MODEL` und `ACTIVE_SERVICE`. Die gemeinsamen Schlüssel `mypresta_updates`, `update_myaigemini` und `updatev_myaigemini` gehören zur Update-Prüfung und werden nicht entfernt.

Übersetzungen: Eine Sprache fügen Sie hinzu, indem Sie `translations/{iso}.php` anlegen (das Modul liefert viele mit). Texte laufen in der Hauptklasse über `$this->l()` und in Templates über `l s='…' mod='myaigemini'`. Admin-Controller übersetzen in PrestaShop 8 und 9 über `trans()` und in 1.6 und 1.7 über das `l()` des Moduls. Nicht übersetzte Texte: der Spaltentitel **ID**, die Beschriftung **Cron Job Secret Token** und **Generate Token**, JavaScript-Meldungen in `back.js`, `image-finder.js` und auf der Seite der Fotoauswahl ("Write a prompt first.", "Looking for photos…" und ähnliche) sowie der von New product zurückgegebene Entwurf. Feldbeschreibungen sind `desc`-Einträge, die mit `fieldHelp()` in den Formulardefinitionen erzeugt werden, in der Form "What it does / How to configure / Effect"; der Text des Help-Panels steht in `lib/sectionHelp.php`.

Platzhalter werden in `controllers/front/ajax.php` (interaktive Läufe) und `controllers/front/cron.php` (Cron) ersetzt; die Listen sind gleich, außer dass der Cron keine CMS- oder Marken-Platzhalter hat.

### 6.8 Erweitern

Es gibt kein Front-Template, das in einem Theme überschrieben werden könnte. Um Prompt-Platzhalter hinzuzufügen, erweitern Sie die Ersetzungsblöcke in `ajax.php` und `cron.php`. Um das Verhalten des KI-Dienstes zu ändern, bearbeiten Sie `src/OpenAIService.php` (`createChatCompletion()` baut die Gemini-Nutzlast). Um ein Modell hinzuzufügen, nutzen Sie **Add a Gemini model** oder erweitern Sie `getPopularGeminiModels()`. Eigenes CSS kann die Klassen `.mag-` auf Modulbildschirmen ansprechen. Eine Änderung des Cron-Adressformats erfordert die Bearbeitung von `AdminMyAIGeminiCron.php` und der Templates `cron.tpl` und `cron-info.tpl`.

## 7. Hilfe

Modulseite: https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html

So bitten Sie um Hilfe:

1. Melden Sie sich auf mypresta.eu in Ihrem Kundenkonto an.
2. Gehen Sie zur Kontaktseite.
3. Wählen Sie das Thema **Support for paid modules**. Bei kostenpflichtigen Modulen weist das Formular darauf hin, dass Sie angemeldet sein müssen; wählen Sie nach der Anmeldung dieses Modul aus Ihrem Kaufverlauf.
4. Beschreiben Sie, was Sie getan haben, was Sie erwartet haben und was Sie gesehen haben. Fügen Sie die rote **History**-Zeile (mit **View** öffnen) oder den Text der Meldung vom Bildschirm sowie den Namen des verwendeten Modells hinzu.
