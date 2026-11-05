---
title: "PrestaMind AI - Dokumentation und Benutzerhandbuch"
sidebar:
  label: "PrestaMind AI - Dokumentation und Benutzerhandbuch"
description: "Konfiguration und Fehlerbehebung für einen Shop, der PrestaMind AI bereits installiert hat."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul PrestaMind AI - AI assistant, live chat and chatbot auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot/)
>
> ---


Die Schaltflächen- und Reiternamen unten sind die englischen Beschriftungen auf dem Bildschirm des Moduls. Ist die Sprache des Mitarbeiters Deutsch, zeigt PrestaShop die deutsche Entsprechung derselben Beschriftung, sofern die Modulübersetzung sie enthält.

## 1. Anforderungen

PrestaShop 1.7.6, 8 und 9. PHP in der Version, die diese PrestaShop-Installation verlangt. Das Modul ruft die Erweiterung cURL sowie OpenSSL oder libsodium auf, um Anbieter-Schlüssel zu speichern. Es verlangt kein weiteres Modul.

Sie brauchen ein Konto und einen API-Schlüssel beim gewählten Anbieter, außer Sie bleiben bei der Offline-Demo. Ein lokaler OpenAI-kompatibler Server (Ollama, vLLM, LM Studio) braucht eine Adresse, die der Shop-Server erreicht. DHL-Live-Status braucht einen kostenlosen Schlüssel von der DHL-Entwicklerseite. InPost-Live-Status braucht keinen Schlüssel.

Ein großer Katalog verlängert die erste Indexierung. Embeddings senden jeden Produkttext einmal an den Embedding-Anbieter, der erste Lauf verbraucht also Token und Zeit. Die Stichwortsuche tut das nicht.

## 2. Installation

1. Laden Sie das Modul im **Module Manager** hoch und drücken Sie **Install**.
2. Die Frage **Delete this module and all its data (conversations, knowledge index, settings)?** erscheint beim Deinstallieren, nicht beim Installieren.
3. Nach der Installation steht der Menüpunkt **PrestaMind AI** unter **Customer service**. Fehlt dieses Menü, liegt der Punkt unter **Improve**. **Configure** in der Modulzeile öffnet dieselbe Seite.
4. Die Installation leert den Shop-Cache nicht. Die Sprechblase bleibt verborgen, bis Sie sie einschalten.

Die Deinstallation entfernt den Menüpunkt, die Modultabellen und die gespeicherten Einstellungen, einschließlich der Anbieter-Schlüssel. Bereits in PrestaShop gespeicherte Bestellungen, Produkte, CMS-Seiten und Warenkorbregeln bleiben. Der Modulordner bleibt auf der Festplatte, bis Sie ihn löschen. Eine neue Installation beginnt mit leeren Gesprächen und einem leeren Index. Die vorherigen stellt sie nicht wieder her.

## 3. Konfiguration und tägliche Arbeit

### 3.1 Der gesamte Ablauf

Sie beginnen im Backoffice. Der Besucher beginnt im Shop.

1. Öffnen Sie **PrestaMind AI**. Unter **Settings**, dann **Health**, beheben Sie jede Zeile, die nicht OK ist.
2. Unter **Model provider** klicken Sie auf eine Anbieter-Kachel, fügen den API-Schlüssel ein, wählen das Hauptmodell und das schnelle Modell, tragen die Preise ein und drücken **Save and test the connection**.
3. Unter **Knowledge** auf der Einstellungsseite legen Sie fest, was indexiert wird. Danach öffnen Sie den Reiter **Knowledge** und drücken **Reindex now**.
4. Unter **Playground** senden Sie eine Produktfrage, eine Lieferfrage und eine Bestellfrage. Jedes Senden verbraucht Token beim echten Anbieter.
5. Unter **Settings**, dann **Widget**, lassen Sie **Show the assistant to all visitors** aus. Tragen Sie Ihre öffentliche IP in **Preview only for these IP addresses** ein, speichern Sie und öffnen Sie den Shop. Wenn die Antworten stimmen, schalten Sie das Widget für alle ein und leeren Sie einen Full-Page-Cache, falls die Blase fehlt.
6. Der Besucher öffnet die Blase, schreibt eine Frage und drückt den Pfeil. Das Modul liest Preis, Bestand, Versand oder die Bestellung aus dem Shop, wenn die Frage das braucht, und zeigt die Antwort im selben Fenster.
7. Ein Rabatt existiert nur, wenn eine von Ihnen gespeicherte Angebotsregel zum Warenkorb passt. **Add to cart**, **Send the return request** und **Send the quote request** warten auf den Klick des Besuchers.
8. Drückt der Besucher **Talk to a person**, steht die Zeile unter **Escalations** und, wenn die Konsole an ist, auch an der Schaltfläche **Live chats**. Sie drücken **Take over this conversation**, schreiben die Antwort, drücken **Send**, dann **Give back to the assistant**. Der Status **new**, **open** oder **done** schickt keine E-Mail an den Besucher.

### 3.2 Wo die Bildschirme liegen

Die Reiter in dieser Reihenfolge: **Dashboard**, **Live stats**, **History**, **Conversations**, **Knowledge**, **Triggers & offers**, **Playground**, **Quality tests**, **Escalations**, **Settings**, **Updates**.

**Settings** hat eine eigene Zeile: **Health**, **Widget**, **Model provider**, **Knowledge**, **Limits & cost**, **Privacy**, **Escalation**, **Cart reminders**, **Couriers**, **Tools**. Jede Unterseite speichert nur ihre eigenen Felder. **Save** zeigt **Settings saved.** Speichern löscht weder Gespräche noch den Index.

Das Shop-Dashboard nach der Anmeldung zeigt einen Block mit den Zahlen des Assistenten, Kunden, die auf eine Person warten, und den letzten Gesprächen.

### 3.3 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/prestamindai-dashboard.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Dashboard.

Nur Lesen. Wählen Sie **today**, **7**, **30** oder **90** Tage, oder setzen Sie **From** und **To**. Sie können die KI-Aufrufe nach Modell, Anbieter, Typ (Antworten oder Embeddings) oder Status eingrenzen und dann **Filter** drücken. **See full history** öffnet **History**.

Der Bildschirm zeigt Umsatz aus Bestellungen in den 7 Tagen nach einem Chat, Gespräche, wie viele ohne Person gelöst wurden, Bewertungen, gesendete und empfangene Token und die geschätzten Kosten. Die Kosten nehmen den Preis, der beim Aufruf gespeichert wurde. Das ist keine Rechnung des Anbieters. Eine Kontrollgruppe setzen Sie unter **Settings**, dann **Privacy**, wenn Sie den Bestellwert vergleichen wollen.

### 3.4 Live stats

![Live stats](https://mypresta.eu/docs/images/docs/prestamindai-live.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Live stats.

Lassen Sie die Seite offen. Neue Zeilen erscheinen alle paar Sekunden oben. Chips blenden Kunden, den Assistenten, das Team, Werkzeuge oder Eskalationen aus. Suchen Sie im Text oder geben Sie eine Chat-Nummer ein. **thumbs down only** behält Antworten, die Besucher abgelehnt haben. **Pause** friert die Ansicht ein. **Compact** macht die Zeilen dichter. **Reset filters** zeigt alles. **Clear** leert die Ansicht auf dieser Seite. **Open chat** öffnet das Gespräch. **Take over** lässt Sie antworten.

Die Seite liest nur gespeicherte Gespräche. Filter bleiben in diesem Browser. Maskierte Karten-, IBAN- und PESEL-Nummern bleiben maskiert.

### 3.5 History

![History](https://mypresta.eu/docs/images/docs/prestamindai-history.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite History.

Die vollständige Liste der Modellaufrufe, neueste zuerst: Datum, Typ, Anbieter, Modell, gesendete Token, empfangene Token, der damals gültige Preis je 1M Token, die geschätzten Kosten, die Zeit und der Status, mit Link zum Gespräch. Dieselben Filter wie auf dem **Dashboard**. Die Karten über der Liste rechnen denselben Filter.

Die Liste speichert keinen Nachrichtentext. Ein später geänderter Preis ändert alte Zeilen nicht. Das Protokoll bleibt, nachdem die Aufbewahrung Gespräche gelöscht hat.

### 3.6 Conversations

![Conversations](https://mypresta.eu/docs/images/docs/prestamindai-conversations.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Conversations.

Filtern Sie nach **Waiting for a reply**, **Handled by a person**, Eskalation oder negativer Stimmung. Das Augensymbol öffnet den Thread: Nachrichten, Modell, Antwortzeit, Daumen hoch und runter und jeden Werkzeugaufruf. Der Papierkorb löscht dieses Gespräch, seine Nachrichten und seine Werkzeugaufrufe. Das Löschen ist endgültig.

Drücken Sie **Take over this conversation**. Der Assistent schweigt für diesen Besucher. Ihre Antworten erscheinen als **Shop team**. **Send** stellt die Antwort ein. **Give back to the assistant** gibt den Chat zurück.

**Live chats** ist eine schwebende Schaltfläche unten rechts auf jeder Backoffice-Seite, wenn **Live chat console in the back office** an ist und Sie **PrestaMind AI** öffnen dürfen. Der Zähler zeigt wartende Kunden. Sie können mehrere Fenster offen halten. Aus schaltet die Schaltfläche aus. Diese Seite funktioniert weiter.

### 3.7 Knowledge

![Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Knowledge.

Drücken Sie **Reindex now** nach der Installation, nach einer Änderung der Ausschlüsse und nach einem Wechsel des Embedding-Anbieters oder -Modells. **Clear answer cache** löscht gespeicherte Antworten auf wiederholte Regelfragen. Der Cache wird auch geleert, wenn Sie einen FAQ-Eintrag oder ein Produkt bearbeiten. Ein Dokument, das noch wartet, wird nicht benutzt. Ein neuer FAQ-Eintrag gilt ab der nächsten Frage.

Preis und Bestand stehen nicht im Index. Sie werden im Moment der Frage vom Produkt gelesen.

**Add FAQ entry** / **Edit FAQ entry**: Schreiben Sie Frage und Antwort so, wie der Assistent sie sagen soll, und speichern Sie.

### 3.8 Triggers

![Triggers](https://mypresta.eu/docs/images/docs/prestamindai-triggers.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Triggers.

**Triggers & offers** hat zwei Unterseiten. Legen Sie zuerst das Angebot an, dann hängen Sie es an einen Auslöser. Ein Besucher sieht höchstens eine vorausschauende Nachricht je Besuch. Derselbe Auslöser bleibt danach für die Cool-down-Zeit still.

Spalten: **Name**, **When**, **Threshold**, **Page**, **Message**, **Discount**, **Active**. In der Zeile: Bearbeiten und Löschen. Der Statuskasten erklärt, warum eine Blase ausbleiben kann. **Open the shop in test mode** ignoriert Einwilligung, Cool-down und das Limit von einer Nachricht je Besuch.

| Feld | Bei einem neuen Auslöser | Was es tut |
|---|---|---|
| **Name** | leer | Eine Bezeichnung für Sie. Leer nimmt den Nachrichtentext. Besucher sehen sie nicht. |
| **Type** | **Seconds on the page** | **Seconds on the page**, **Scrolled percent of the page**, **Exit intent (desktop)**, **Seconds idle on the cart page** oder **Product viewed N times in a visit**. Die Nachricht steht neben der Chat-Schaltfläche. Ein Klick öffnet den Chat. |
| **Threshold** | 30 | Sekunden, Scroll-Prozent oder Anzahl der Aufrufe. Exit intent ignoriert den Wert. Zeit und ruhender Warenkorb nutzen mindestens 5 Sekunden. |
| **Page type** | **Any page** | **Any page**, **Product page**, **Category page**, **Cart / checkout** oder **Home page**. Auf anderen Seiten schweigt dieser Auslöser. |
| **Message shown to the visitor** | leer, Pflicht | Ein oder zwei Sätze je Shopsprache, bis 300 Zeichen. Eine leere Sprache nimmt die Standardsprache. Dieser Text ist auch die erste Zeile, wenn der Besucher den Chat aus der Blase öffnet. |
| **Only for these categories** | keine | Auf einer Produktseite muss das Produkt in einer davon liegen. Auf einer Kategorieseite muss die Kategorie passen. Leer bedeutet alle Kategorien. |
| **Only for these products** | keine | Begrenzt den Auslöser auf diese Produkte. Leer bedeutet alle Produkte. |
| **Offer the assistant may grant after this trigger** | **None** | Wählen Sie ein gespeichertes Angebot oder **None**. Die Regeln entscheiden. Das Modell erfindet keinen Prozentsatz. |
| **How the discount is handed out** | **Give the code at once when the visitor clicks the message** | **Only if the visitor asks or hesitates over the price**, oder sofort, wenn der Chat aus der Nachricht geöffnet wird. In beiden Fällen muss der Warenkorb zur Regel passen. Ist **apply_offer** unter **Tools** abgewählt, wird der Code sofort ausgegeben. |
| **Cool-down (days)** | 7 | 0 bis 365. Nach der Blase sieht dieser Besucher diesen Auslöser nicht wieder, bis die Frist abläuft. |

**Add trigger** oder **Save trigger** speichert die Zeile. **Allow proactive messages** muss unter **Privacy** an sein, sonst feuert kein Auslöser.

### 3.9 Offers

![Offers](https://mypresta.eu/docs/images/docs/prestamindai-offers.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Offers.

Spalten: **Name**, **%**, **Min. cart**, **Valid (h)**, **Max / day**. In der Zeile Bearbeiten und Löschen. Ohne Angebote gibt der Assistent nie einen Rabatt. Ein Gespräch erhält höchstens ein Angebot. Der Code ist einmalig, liegt im Warenkorb und stapelt sich nicht auf bereits reduzierte Produkte. Der Besucher sieht den Regelnamen **PrestaMind offer**.

| Feld | Bei einem neuen Angebot | Was es tut |
|---|---|---|
| **Name** | leer | Ihre Bezeichnung im Auslöserformular. |
| **Discount percent (1-50)** | 5 | Prozent auf Produkte, die nicht schon reduziert sind. |
| **Minimum cart value (tax incl.)** | 0 | 0 bedeutet jeder Warenkorb. Darunter wird das Angebot abgelehnt. Der Betrag ist in der Standardwährung des Shops. |
| **Valid for (hours)** | 24 | 1 bis 720. Danach läuft der Code ab. |
| **Maximum codes per day** | 20 | 0 bedeutet keine Obergrenze. Ist sie erreicht, pausiert dieses Angebot bis zum nächsten Tag. |
| **No offer when the cart contains products from** | keine | Liegt irgendeine Position in diesen Kategorien, wird der ganze Warenkorb abgelehnt. |

**Add offer** oder **Save offer** speichert die Regel. Hängen Sie sie an einen Auslöser, bevor der Assistent sie nutzen kann. Warenkorb-Erinnerungen können ebenfalls ein Angebot anhängen.

### 3.10 Playground

![Playground](https://mypresta.eu/docs/images/docs/prestamindai-playground.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Playground.

Nutzt den echten Anbieter. Verbraucht Token und zählt zum Tagesbudget. Der Thread hat den Kanal playground. An Besucher geht nichts.

| Feld | Am Start | Was es tut |
|---|---|---|
| **Page the customer is on** | **Other** | **Other**, **Home**, **Product page**, **Category** oder **Cart**. Der Assistent erhält diese Seite als Kontext. |
| **Product id (optional)** | leer | Nur bei **Product page**. Die Id aus **Catalog**, dann **Products**. Der Assistent sieht den aktuellen Preis und Bestand. |
| **Customer message** | leer | Die Frage. **Send** zeigt die Antwort und die Spur. **New conversation** beginnt neu. |

### 3.11 Quality tests

![Quality tests](https://mypresta.eu/docs/images/docs/prestamindai-quality-tests.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Quality tests.

Legen Sie eine Frage an, Wörter, die die Antwort enthalten muss, und Wörter, die sie nicht enthalten darf. Drücken Sie **Run all tests**. Jeder Lauf fragt das echte Modell und verbraucht Token. Die Liste zeigt bestanden oder nicht, den Grund und die Antwort. Testgespräche werden nach dem Lauf gelöscht.

### 3.12 Escalations

![Escalations](https://mypresta.eu/docs/images/docs/prestamindai-escalations.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Escalations.

Zeilen sind Kunden, die eine Person wollten, Rückgabeanfragen und Angebotsanfragen, mit Zusammenfassung und hinterlassenem Kontakt. Das Ziel stellen Sie unter **Settings**, dann **Escalation**, ein. Setzen Sie den Status auf **new**, **open** oder **done**. Der Status schickt keine E-Mail an den Besucher. Antworten Sie über den Kontakt in der Zeile oder öffnen Sie den Chat-Link.

### 3.13 Health

![Health](https://mypresta.eu/docs/images/docs/prestamindai-health.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Health.

Eine Prüfliste. **OK** bedeutet bereit. **!** bedeutet nicht bereit. **Repair hooks** registriert fehlende Hooks und zeigt **All hooks are registered.** oder **Could not register:** mit den Hook-Namen. **Test streaming** prüft, ob der Server die Live-Antwort puffert. Das Ansehen der Seite ändert sonst nichts. Die Widget-Zeile ist nur OK, wenn die Blase für Sie sichtbar ist.

### 3.14 Widget

![Widget](https://mypresta.eu/docs/images/docs/prestamindai-widget.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Widget.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Show the assistant to all visitors** | Nein | An: jeder Besucher sieht die Blase, außer der Kontrollgruppe. Aus: niemand, außer den Vorschau-IPs. Leeren Sie danach einen Full-Page-Cache. |
| **Preview only for these IP addresses** | leer | Öffentliche IPs, durch Kommas getrennt. Die Seite zeigt die IP, die der Shop jetzt sieht. Hinter einem Proxy kann sie von der bekannten abweichen. |
| **Assistant name** | PrestaMind | Name in der Chat-Kopfzeile, je Sprache, bis 60 Zeichen. Eine leere Sprache nimmt die Standardsprache. |
| **Greeting** | leer | Erste Nachricht eines leeren Chats, bis 300 Zeichen je Sprache. Leer nimmt einen eingebauten Satz. |
| **AI disclosure line** | leer | Zeile unter der Kopfzeile, bis 300 Zeichen je Sprache. Leer nimmt einen eingebauten Satz, der auch sagt, dass Antworten Fehler enthalten können. |
| **Color** | #2563eb | Hauptfarbe von Schaltfläche, Kopfzeile, Schaltflächen und Besucherblasen. |
| **Position** | **Bottom right** | **Bottom right** oder **Bottom left**. |
| **Button shape** | **Circle** | **Circle**, **Rounded square** oder **Square with sharp corners**. Das Fenster bleibt. |
| **Button size** | **Medium (56 px)** | **Small (48 px)**, **Medium (56 px)** oder **Large (68 px)**. |
| **Window corners** | **Soft (default)** | **Sharp**, **Soft (default)** oder **Very round**. |
| **Button icon** | eingebaute Sprechblase | **Choose icon** öffnet Font Awesome und Material Icons. **Use the built-in bubble** stellt die Vorgabe wieder her. Das Symbol wird im Shop gespeichert. Speichern Sie das Formular. |
| **Button color** | leer (nimmt **Color**) | Hintergrund der Chat-Schaltfläche. |
| **Icon color** | #ffffff | Farbe des Symbols auf der Schaltfläche. |
| **Header color** | leer (nimmt **Color**) | Hintergrund der oberen Leiste. |
| **Header text color** | #ffffff | Name und Schaltflächen in der oberen Leiste. |
| **Customer bubble color** | leer (nimmt **Color**) | Besuchernachrichten sowie Schaltflächen und Sende-Pfeil. |
| **Customer bubble text color** | #ffffff | Text in Besuchernachrichten und auf den primären Schaltflächen. |
| **Preview** | Muster | Ändert sich mit den Feldern. Nichts ist gespeichert vor **Save**. |
| **Tone** | **Friendly** | **Friendly**, **Formal**, **Casual** oder **Expert**. Gilt für neue Nachrichten. |
| **Your instructions to the assistant** | leer | Bis 1500 Zeichen, an jedes Gespräch angehängt. Sie heben aktuelle Preise, das Verbot erfundener Rabatte und das Verbot fremder Kundendaten nicht auf. Langer Text kostet bei jeder Nachricht Token. |

### 3.15 Modellanbieter und jedes eingebaute Modell

![Modellanbieter und jedes eingebaute Modell](https://mypresta.eu/docs/images/docs/prestamindai-provider.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Modellanbieter und jedes eingebaute Modell.

Klicken Sie auf eine Kachel. Aufgerufen wird nur der aktive Anbieter, plus der Ausweichanbieter, wenn Sie einen gesetzt haben und der aktive scheitert, bevor das erste Wort gesendet wurde. Modelle und Preise bleiben bei jedem Anbieter.

Nach der Installation ist **Demo (offline)** aktiv. Kein Schlüssel, keine Kosten. Feste Antworten, nur zum Prüfen der Installation. Das ist kein Shop-Assistent.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Fallback provider** | **None** | Zweiter Anbieter bei Zeitüberschreitung, Rate-Limit oder Serverfehler. Wählen Sie einen mit gespeichertem Schlüssel. Dessen Verbrauch rechnet dieser zweite Anbieter ab. Die Demo kann nicht Ausweichanbieter sein. |
| **API key** | leer | Schlüssel einfügen und speichern. Ein leeres Feld behält den gespeicherten Schlüssel. Der Schlüssel ist verschlüsselt und wird nicht wieder gezeigt, nur die ersten und letzten Zeichen. **Remove the stored key** auf Yes, dann speichern, löscht ihn. Der kompatible Server kann ohne Schlüssel bleiben. |
| **Base URL** | http://localhost:11434/v1 | Nur für **OpenAI-compatible / Ollama**. Die URL muss auf /v1 enden. Anfragen gehen dorthin statt in die Cloud. |
| **Main model** | Tabelle dieses Anbieters | Produktberatung, Bestellfragen und jede Antwort, die Werkzeuge braucht. |
| **Fast model** | Tabelle dieses Anbieters | Regelfragen und Smalltalk. Setzen Sie dasselbe Modell wie das Hauptmodell, wenn Sie überall eines wollen. |
| **Your own model id** | leer | Buchstaben, Ziffern und . _ - : / @, bis 100 Zeichen. **Add model** speichert sofort mit der restlichen Seite. **Model added. Choose it as the main or fast model and enter its price.** Schon vorhanden: **That model is already on the list.** Ungültige Id: **Enter a model id: letters, digits and . _ - : / @ only.** |
| Preisspalten | Listenpreis | **USD / 1M input tokens** und **USD / 1M output tokens**. Punkt als Dezimaltrennzeichen. **set price** bedeutet, es gibt keinen bekannten Vorgabepreis. Ein Modell ohne Preis zählt als kostenlos, das Tagesbudget in Dollar schützt Sie dann nicht. |
| **Reset prices to defaults** | - | Setzt die eingebauten Preise zurück. **Prices set back to the built-in defaults.** Getippte Preise gehen verloren. |
| **Remove** | - | Nur bei einem eigenen Chat-Modell. **Model removed.** Ein eingebautes Modell zeigt ein Schloss und **Built-in models cannot be removed.** |

**Save and test the connection** speichert und ruft den aktiven Anbieter mit dem Hauptmodell auf. **No API key stored for the selected provider.** bedeutet, der Schlüssel fehlt noch.

Preise unten sind USD je 1 Million Token, zuerst Eingabe, dann Ausgabe. Das sind die Listenpreise, die das Modul am 2026-10-31 gespeichert hat. Der Anbieter kann sie ändern. Korrigieren Sie die beiden Spalten, wenn Ihre Rechnung abweicht. DeepSeek hat Haupt- und Nebenzeiten. Das Modul speichert den Hauptzeitpreis, damit die Schätzung nicht zu niedrig ist.

**OpenAI.** Streaming, Werkzeuge und Embeddings. Standard-Hauptmodell **gpt-6.1-sol**. Standard-Schnellmodell **gpt-6-luna**.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| gpt-6.1-sol | Chat | 2 / 10 | Hauptmodell |
| gpt-6.1-terra | Chat | 1 / 5 | nein |
| gpt-6-luna | Chat | 0.10 / 0.50 | schnelles Modell |
| gpt-5.5 | Chat | 5 / 30 | nein |
| gpt-5-mini | Chat | 0.25 / 2 | nein |
| gpt-4.1 | Chat | 2 / 8 | nein |
| gpt-4.1-mini | Chat | 0.40 / 1.60 | nein |
| gpt-4o-mini | Chat | 0.15 / 0.60 | nein |
| text-embedding-3-small | Embeddings | 0.02 / 0 | Standard-Embedding-Modell |
| text-embedding-3-large | Embeddings | 0.13 / 0 | nein |

**Anthropic Claude.** Streaming und Werkzeuge. Keine Embeddings. Standard-Hauptmodell **claude-sonnet-5-5**. Standard-Schnellmodell **claude-haiku-5-5**.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| claude-fable-5-1 | Chat | 10 / 50 | nein |
| claude-opus-5-5 | Chat | 4 / 20 | nein |
| claude-opus-5 | Chat | 5 / 25 | nein |
| claude-sonnet-5-5 | Chat | 2 / 10 | Hauptmodell |
| claude-sonnet-4-6 | Chat | 3 / 15 | nein |
| claude-haiku-5-5 | Chat | 0.10 / 0.50 | schnelles Modell |
| claude-haiku-4-5 | Chat | 1 / 5 | nein |

**Google Gemini.** Streaming, Werkzeuge und Embeddings. Standard-Hauptmodell **gemini-2.5-flash**. Standard-Schnellmodell **gemini-2.5-flash-lite**.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| gemini-2.5-pro | Chat | 1.25 / 10 | nein |
| gemini-2.5-flash | Chat | 0.30 / 2.50 | Hauptmodell |
| gemini-2.5-flash-lite | Chat | 0.10 / 0.40 | schnelles Modell |
| gemini-embedding-001 | Embeddings | 0.15 / 0 | Standard-Embedding-Modell |

**DeepSeek.** OpenAI-kompatible API. Keine Embeddings. Standard-Hauptmodell und Standard-Schnellmodell sind beide **deepseek-flash**.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| deepseek-flash | Chat | 0.30 / 1.20 | Hauptmodell und schnelles Modell |
| deepseek-v4-pro | Chat | 1.32 / 3.96 | nein |

**Mistral AI.** Streaming, Werkzeuge und Embeddings. Standard-Hauptmodell **mistral-large-latest**. Standard-Schnellmodell **mistral-small-latest**. Ein leerer Preis bedeutet, das Modul hat keinen Listenpreis: die Zeile trägt **set price**, bis Sie einen eintragen.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| mistral-large-latest | Chat | 0.50 / 1.50 | Hauptmodell |
| mistral-medium-latest | Chat | kein eingebauter Preis | nein |
| mistral-small-latest | Chat | kein eingebauter Preis | schnelles Modell |
| open-mistral-nemo | Chat | kein eingebauter Preis | nein |
| mistral-embed | Embeddings | kein eingebauter Preis | Standard-Embedding-Modell |

**OpenAI-compatible / Ollama.** Ihr Server. Eingebaute Preise sind 0 / 0, auch für lokale Modelle. Standard-Hauptmodell und Standard-Schnellmodell sind **llama3.1**. Standard-Embedding-Modell ist **nomic-embed-text**.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| llama3.1 | Chat | 0 / 0 | Hauptmodell und schnelles Modell |
| llama3.2 | Chat | 0 / 0 | nein |
| mistral | Chat | 0 / 0 | nein |
| qwen2.5 | Chat | 0 / 0 | nein |
| nomic-embed-text | Embeddings | 0 / 0 | Standard-Embedding-Modell |
| mxbai-embed-large | Embeddings | 0 / 0 | nein |
| bge-m3 | Embeddings | 0 / 0 | nein |
| snowflake-arctic-embed | Embeddings | 0 / 0 | nein |

**Demo (offline).** Kein Schlüssel. Preise 0 / 0.

| Modell | Art | Eingabe / Ausgabe USD je 1M | Nach der Installation |
|---|---|---|---|
| mock | Chat | 0 / 0 | Hauptmodell und schnelles Modell, und dieser Anbieter ist aktiv |
| mock-64 | Embeddings | 0 / 0 | wenn der Embedding-Anbieter die Demo ist |

Einige neuere OpenAI-Modelle ignorieren **Temperature**. Eine Id, die der Anbieter nicht kennt, erscheint als Anbieterfehler auf dem **Dashboard**.

### 3.16 Knowledge-Einstellungen

![Knowledge-Einstellungen](https://mypresta.eu/docs/images/docs/prestamindai-knowledge-settings.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Knowledge-Einstellungen.

Die Cron-Adresse steht auf dieser Seite. Rufen Sie sie alle 10 bis 15 Minuten auf. Jeder Aufruf indexiert neue und geänderte Seiten, baut Embeddings, sendet Warenkorb-Erinnerungen, wenn Sie sie eingeschaltet haben, löscht Gespräche, die älter als die Aufbewahrung sind, und leert den Antwort-Cache sowie Rate-Limit-Zeilen, die älter als zwei Tage sind. Ohne Cron aktualisiert sich der Index trotzdem, wenn Besucher schreiben oder Produkt- und CMS-Hooks laufen. Aufbewahrung und Embeddings laufen dann nur über die Schaltflächen.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Embeddings provider** | **None (keyword search)** | **None (keyword search)**, **openai**, **gemini**, **mistral**, **compatible** oder **demo**. Anthropic und DeepSeek stehen nicht in dieser Liste. Eine Änderung verlangt **Reindex now**. |
| **Embeddings model** | **Default for the chosen provider** | Ein Modell des Anbieters oben. Vektoren zweier Modelle lassen sich nicht vergleichen. Ein Modell eines anderen Anbieters wird ignoriert, es gilt der Standard. Danach neu indexieren. |
| **Other embeddings model** | leer | Genaue Id eines Modells, das nicht in der Liste steht, zum Beispiel aus Ollama. Ist das Feld gefüllt, ersetzt es die Wahl oben. |
| **Index products** | Ja | Indexiert Name, Marke, Kategorien, Merkmale und Beschreibungen aktiver sichtbarer Produkte. Nein: Produktfragen haben keinen Katalogtext. |
| **Index CMS pages** | Ja | Indexiert aktive CMS-Seiten. Indexieren Sie keine Seiten mit internen Notizen. |
| **Never use these categories** | keine | Produkte dieser Kategorien werden nicht indexiert und können nicht gezeigt, verglichen oder in den Warenkorb gelegt werden. Danach neu indexieren. |
| **Never use these products** | keine | Dasselbe für einzelne Produkte. |
| **Cache answers to repeated policy questions** | Ja | Gäste, nur die erste Frage, und nie eine Antwort mit Preis oder Bestellung. **Clear answer cache** auf dem Knowledge-Reiter nach einer Änderung einer Regelseite. |
| **Cache lifetime (hours)** | 24 | 1 bis 720. Danach antwortet das Modell wieder neu. |

### 3.17 Grenzen und Kosten

![Grenzen und Kosten](https://mypresta.eu/docs/images/docs/prestamindai-limits.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Grenzen und Kosten.

Die obere Zeile zeigt die heutigen Anfragen, Token und geschätzten Kosten. Ist ein Tagesbudget erreicht, sendet der Assistent einen kurzen Hinweis und bietet an, die Frage an Ihr Team zu geben, bis zum nächsten Tag.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Daily budget (USD)** | 0 | 0 bedeutet keine Grenze. Wirkt nur, wenn die genutzten Modelle Preise haben. Erreichen die heutigen Kosten den Wert, stoppen Modellaufrufe bis Mitternacht. |
| **Daily token budget** | 0 | 0 bedeutet keine Grenze. Zählt Token auch bei Preis 0. 1000000 Token sind ungefähr einige hundert Gespräche. |
| **Messages per minute per visitor IP** | 8 | 1 bis 60. Schnellere Absender erhalten eine Warte-Antwort und keinen Modellaufruf. |
| **Messages per conversation per day** | 60 | 1 bis 500. Danach ist das Gespräch für den Tag gesperrt. |
| **Max reply tokens** | 700 | 150 bis 3000. Bei 700 ungefähr 450 Wörter. Ein kurzes Limit schneidet die Antwort ab. |
| **Max tool steps per message** | 5 | 1 bis 8. Wie viele Live-Abfragen (Suche, Produkt, Versand) eine Nachricht ausführen darf. 1 beendet die mehrstufige Suche. |
| **Max characters per customer message** | 800 | 100 bis 2000. Längerer Text wird abgeschnitten. |
| **Messages of history sent to the model** | 12 | 2 bis 30. 12 sind die letzten sechs Wechsel. Mehr Verlauf sendet mehr Token. |
| **Temperature (0-1)** | 0.3 | 0.2 bis 0.4 bleibt näher an den Shop-Daten. Höher variiert die Formulierung. Einige neuere OpenAI-Modelle ignorieren den Wert. |

### 3.18 Privacy

![Privacy](https://mypresta.eu/docs/images/docs/prestamindai-privacy.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Privacy.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Mask card numbers, IBAN and PESEL** | Ja | Ersetzt sie durch [card], [iban] und [id], bevor der Text gespeichert wird und bevor er an den Anbieter geht. |
| **Delete conversations after (days)** | 90 | 0 behält sie. Die Cron-URL löscht ältere Gespräche. Bestellstatistiken bleiben. |
| **Order status without signing in, for registered customers** | Ja | Ein Besucher darf mit Bestellreferenz und Checkout-E-Mail fragen. Nein: dieses Paar gilt nur für Gastbestellungen, ein Kunde mit Konto muss sich anmelden. Höchstens 10 Versuche in 10 Minuten. |
| **Allow proactive messages** | Ja | Nein schaltet jeden Auslöser aus. |
| **Proactive triggers wait for consent** | Ja | Keine Blase, bis das Cookie-Banner die Einwilligungsfunktion aufruft. Der Chat selbst funktioniert. Nein: Auslöser feuern für alle. |
| **Control group (% of visitors)** | 0 | 0 bis 50. Diese Besucher sehen den Assistenten nie. Das **Dashboard** kann den Bestellwert vergleichen. |

**Delete old conversations** ist ein eigenes Formular. **Older than (days)** startet dort bei 30. **Delete** entfernt diese Gespräche sofort. Die Meldung ist **Deleted N conversations.** Das lässt sich nicht rückgängig machen.

### 3.19 Escalation-Einstellungen

![Escalation-Einstellungen](https://mypresta.eu/docs/images/docs/prestamindai-escalation.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Escalation-Einstellungen.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Live chat console in the back office** | Ja | Zeigt die Schaltfläche **Live chats**. Nur Mitarbeiter, die **PrestaMind AI** öffnen dürfen, sehen sie. Aus blendet die Schaltfläche aus. **Conversations** funktioniert weiter. |
| **E-mail for hand-offs** | leer | Jede Eskalation sendet eine Zusammenfassung und den hinterlassenen Kontakt. Leer bedeutet keine E-Mail. Die Shop-Mail muss funktionieren. |
| **Webhook type** | **Slack** | **Slack**, **Telegram** oder **Generic JSON**. |
| **Webhook URL** | leer | Slack-Incoming-Webhook, Telegram `https://api.telegram.org/bot<TOKEN>/sendMessage` oder eine beliebige https-URL. Leer bedeutet kein Webhook. Das Ergebnis steht in der Liste **Escalations**. |
| **Telegram chat id** | leer | Numerische Id des Chats oder der Gruppe. Für Slack und Generic JSON wird sie ignoriert. |
| **Offer a person when sentiment falls below** | -0.5 | Von -1 bis 0. Näher an 0 reagiert früher. Der Assistent entschuldigt sich und bietet an, den Fall an das Team zu geben. |

### 3.20 Warenkorb-Erinnerungen

![Warenkorb-Erinnerungen](https://mypresta.eu/docs/images/docs/prestamindai-reminders.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Warenkorb-Erinnerungen.

Nichts geht hinaus, bis **Send cart reminders** auf Yes steht und die Cron-URL läuft. Eine E-Mail je verlassenem Warenkorb, nur an einen Kunden mit Konto. Gäste erhalten keine E-Mail.

| Feld | Nach der Installation | Was es tut |
|---|---|---|
| **Send cart reminders** | Nein | An: der nächste Cron-Lauf sendet passende Erinnerungen. Aus: nichts Neues wird gesendet. Bereits gesendete Zeilen bleiben in der Liste. |
| **Only customers who subscribed to the newsletter** | Ja | Ja: Kunden ohne Newsletter-Haken erhalten nichts. |
| **Send after (hours of inactivity)** | 3 | Mindestens 1. So lange muss der Warenkorb unberührt bleiben. |
| **Stop after (hours since the last change)** | 72 | Muss größer sein als der Wert darüber. Ältere Warenkörbe werden übersprungen. |
| **Minimum cart value (tax incl.)** | 0 | 0 bedeutet jeder Warenkorb. Der Betrag ist in der Shop-Währung. |
| **Discount code in the e-mail** | **No discount code** | Eines Ihrer Angebote oder keines. Die Angebotsregeln gelten weiter. Ist die Tagesgrenze erreicht, geht die E-Mail ohne Code hinaus. |
| **E-mail subject** | leer | Je Sprache. Leer nimmt einen eingebauten Betreff. Der Kunde erhält den Betreff der Kontosprache. |

**Send a test e-mail** nutzt **Send the test to** (zuerst Ihre Backoffice-E-Mail) und **Send test**. Eine Probe geht sofort hinaus. Sie wird nicht protokolliert und erzeugt keinen Code. **Test e-mail sent.** oder **The e-mail could not be sent. Check the e-mail settings of the shop.** Eine ungültige Adresse zeigt **Enter a valid e-mail address.**

**Latest reminders** listet Datum, Warenkorb, Kunde, Code und Status.

### 3.21 Couriers

![Couriers](https://mypresta.eu/docs/images/docs/prestamindai-couriers.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Couriers.

Die Seite listet die Versandarten dieses Shops. Hat der Shop keine, sehen Sie **Your shop has no shipping methods yet. Add them in Shipping > Carriers; they appear here automatically.**

Je Methode ist **tracking link** eine Adresse je Sprache. Setzen Sie `{n}` dorthin, wo die Sendungsnummer steht. Eine Adresse ohne `{n}` oder eine, die nicht mit http oder https beginnt, wird ignoriert. Eine leere Sprache nimmt die Standardsprache. Hat der Carrier schon eine Tracking-URL unter **Shipping**, dann **Carriers**, wird diese URL zuerst benutzt. Ohne Link nennt der Assistent nur die Nummer.

**live status** erscheint nur, wenn der Name InPost oder DHL enthält oder Sie es früher gewählt haben. **No live status (tracking link only)** behält den Link. InPost braucht keinen Schlüssel. DHL zeigt **DHL API key**: registrieren Sie sich auf der DHL-Entwicklerseite, legen Sie eine App Shipment Tracking - Unified an und fügen Sie den Schlüssel ein. Der kostenlose Schlüssel erlaubt ungefähr 250 Aufrufe am Tag. Der Schlüssel wird verschlüsselt gespeichert. Ohne ihn entfällt der DHL-Live-Status und der Link wird benutzt. Live-Antworten liegen 10 Minuten im Cache.

### 3.22 Tools

![Tools](https://mypresta.eu/docs/images/docs/prestamindai-tools.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Tools.

Haken Sie ein Werkzeug ab, damit das Modell es nicht angeboten bekommt. Ein abgeschaltetes Werkzeug kann nicht laufen. Im Katalogmodus bleiben Warenkorb-, Angebots- und Warenkorb-Inhalt-Werkzeuge aus. Eine Regelfrage oder Smalltalk darf nur **create_ticket** aufrufen.

| Werkzeug | Risiko auf dem Bildschirm | Braucht | Was der Besucher erhält |
|---|---|---|---|
| search_products | Lesen | - | Bis zu sechs Produktkarten. Optional Höchstpreis und nur auf Lager. Der Besucher drückt **Add to cart**. |
| popular_products | Lesen | - | Bestseller aus echten Bestellungen, Standard 90 Tage, von 7 bis 365, bis zu sechs Karten. Keine genauen Verkaufszahlen. |
| get_product_live | Lesen | - | Aktueller Preis, Bestand, Merkmale und Varianten eines Produkts. |
| compare_products | Lesen | - | Zwei oder drei Produkte nebeneinander. |
| suggest_substitute | Lesen | - | Alternativen, die auf Lager sind. |
| get_cart | Lesen | ein Warenkorb | Inhalt und Summe. |
| add_to_cart | der Bildschirm markiert die Bestätigung | Bestätigung des Kunden | Eine Produktkarte. Menge 1 bis 20. Das Modul legt die Zeile nicht an. Der Besucher drückt **Add to cart**. |
| check_shipping | Lesen | - | Methoden, Zeiten und die Grenze für kostenlosen Versand. Optionaler ISO-Ländercode. |
| get_order_status | Lesen | Sitzung oder Referenz plus Checkout-E-Mail | Status dieser Bestellung. |
| track_parcel | Lesen | dieselbe Identität wie der Bestellstatus | Carrier, Nummer und Link. InPost live ohne Schlüssel. DHL live mit dem DHL-Schlüssel. |
| start_return | Bestätigung | angemeldeter Kunde | Nichts geht hinaus vor **Send the return request**. |
| request_quote | Bestätigung | das Formular | Positionen, Firma und Kontakt. Nichts geht hinaus vor **Send the quote request**. |
| create_ticket | Übergabe | ein Gast wird nach E-Mail oder Telefon gefragt | **Talk to a person** öffnet eine Eskalation. |
| apply_offer | die Regeln entscheiden | ein Warenkorb | Ein Code nur, wenn ein gespeichertes Angebot passt. Keine passende Regel bedeutet kein Code. |

**Save** speichert die Haken.

### 3.23 Updates

![Updates](https://mypresta.eu/docs/images/docs/prestamindai-updates.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt diese Seite Updates.

**Check now** vergleicht die installierte Version mit der Version auf den Servern von MyPresta.eu. Lassen Sie automatische Hinweise an, um eine Meldung im Backoffice zu sehen. Das Modul aktualisiert sich nie von selbst. Das neue Paket installieren Sie selbst.

## 4. Shop-Frontend

Die Blase ist verborgen, bis **Show the assistant to all visitors** an ist, außer für IPs auf der Vorschau-Liste. Besucher der Kontrollgruppe sehen sie nicht.

Der Besucher drückt die Schaltfläche in der von Ihnen gewählten Ecke. Das Fenster zeigt den Namen des Assistenten, die Hinweiszeile und die Begrüßung. Der Besucher schreibt und drückt den Pfeil. Im Shop gibt es keine Schaltfläche mit der Aufschrift Send. Die Antwort läuft ins Fenster, wenn der Server sie nicht puffert.

Produktkarten zeigen **Add to cart**. Eine Rückgabe wartet auf **Send the return request**. Ein Angebot wartet auf **Send the quote request**. **Talk to a person** gibt den Chat an das Team. Solange Sie übernommen haben, werden neue Besuchernachrichten gespeichert und Ihre Antworten erscheinen als **Shop team**.

Eine vorausschauende Blase erscheint nur, wenn Auslöser erlaubt sind, der Besucher zur Regel passt und die Einwilligung vorliegt, falls Sie sie verlangen. Eine Blase je Besuch. Der Testlink unter **Triggers** ist für Sie, nicht für Kunden.

Die Cron-Adresse ist keine Seite für Besucher. Öffnen Sie sie nur aus dem Server-Zeitplan. Ein falsches Token erhält eine Ablehnung und tut nichts.

## 5. Probleme

**Die Blase fehlt.** **Show the assistant to all visitors** ist aus, dieser Besucher ist in der Kontrollgruppe, oder ein Full-Page-Cache hält die alte Seite. Schalten Sie den Schalter ein oder tragen Sie Ihre IP in die Vorschau-Liste ein, speichern Sie und leeren Sie den Full-Page-Cache.

**Could not create the module tables.** Die Installation stoppte, bevor der Menüpunkt da war. Lesen Sie die Datenbankmeldung, korrigieren Sie die Rechte des Datenbankbenutzers und installieren Sie erneut.

**Could not register hook** mit einem Hook-Namen, oder **Could not register:** unter **Health**. Drücken Sie **Repair hooks**. Bleibt die Zeile, darf der Shop-Benutzer keine Hooks schreiben. Korrigieren Sie die Datenbankrechte und drücken Sie die Schaltfläche erneut.

**Could not add the menu tab.** Die Installation hat das Menü nicht beendet. Öffnen Sie den **Module Manager**, deinstallieren Sie, wenn das Modul halb installiert ist, und installieren Sie erneut. **Configure** versucht den Menüpunkt ebenfalls neu anzulegen.

**No API key stored for the selected provider.** Fügen Sie den Schlüssel unter **Model provider** ein und drücken Sie **Save and test the connection**. Ein leeres Passwortfeld löscht keinen Schlüssel. **Remove the stored key** löscht ihn.

**That model is already on the list.** Wählen Sie es als **Main model** oder **Fast model**, statt es noch einmal hinzuzufügen.

**Enter a model id: letters, digits and . _ - : / @ only.** Tippen Sie die Id aus der Modellliste des Anbieters. Leerzeichen sind nicht erlaubt.

**Built-in models cannot be removed.** Lassen Sie die Zeile. Fügen Sie eine eigene Id hinzu, wenn Sie ein anderes Modell brauchen.

**Anbieterfehler auf dem Dashboard.** Der Schlüssel ist falsch, der Anbieter kennt die Modell-Id nicht, oder der Anbieter ist nicht erreichbar. Ist ein Ausweichanbieter gesetzt und der Fehler liegt vor dem ersten Wort, antwortet der Ausweichanbieter. Korrigieren Sie Schlüssel oder Modell und nutzen Sie **Playground**.

**Die Antwort kommt in einem Block, nicht Wort für Wort.** Drücken Sie **Test streaming** unter **Health**. Schlägt der Test fehl, puffert Proxy oder Host die Antwort. Bitten Sie den Host, das Puffern auf der Chat-Adresse des Shops abzuschalten.

**I cannot answer right now.** Das Tagesbudget oder das Token-Budget ist erreicht, oder der Anbieter ist ausgefallen und es gibt keinen Ausweichanbieter. Heben Sie das Budget an, warten Sie bis zum nächsten Tag oder reparieren Sie den Anbieter. Der Assistent bietet an, die Frage an das Team zu geben.

**Bitte warten, oder das Gespräch ist gesperrt.** Der Besucher hat mehr gesendet als **Messages per minute per visitor IP** oder mehr als **Messages per conversation per day**. Warten Sie oder heben Sie das Limit an.

**Ein Auslöser erscheint nie.** Lesen Sie den Kasten unter **Triggers**. **Allow proactive messages** ist aus, der Auslöser ist inaktiv, **apply_offer** ist aus, während der Auslöser wartet, bis der Besucher fragt, oder die Auslöser warten auf Einwilligung und das Banner ruft die Funktion nie auf. Nutzen Sie **Open the shop in test mode**. Nach einem echten Test verbirgt der Cool-down diesen Auslöser in diesem Browser.

**Der Rabatt erscheint nie.** Es gibt kein Angebot, das Angebot hängt nicht am Auslöser, der Warenkorb liegt unter dem Minimum, die Tagesgrenze ist erreicht, ein Produkt liegt in einer ausgeschlossenen Kategorie, oder das Produkt ist schon reduziert. Der Assistent erfindet keinen Prozentsatz.

**Add to cart legt von selbst nichts an.** Die Karte ist nur eine Karte. Der Besucher drückt **Add to cart**. Im Katalogmodus bleiben die Warenkorb-Werkzeuge aus.

**Test e-mail sent.** ist Erfolg. **The e-mail could not be sent. Check the e-mail settings of the shop.** bedeutet, die Shop-Mail ist fehlgeschlagen. **Enter a valid e-mail address.** bedeutet, die Testadresse ist leer oder ungültig. Kunden-E-Mails brauchen außerdem **Send cart reminders** auf Yes und eine laufende Cron-URL.

**Deleted N conversations.** Sie haben **Delete** unter **Privacy** gedrückt. Diese Threads sind weg.

## 6. Für Entwickler

### 6.1 Überblick

Technischer Name `prestamindai`, Klasse `prestamindai`, Version in der Datei `1.8.9`, Anzeigename **PrestaMind AI**, Autor MyPresta.eu, Tab `front_office_features`. Kompatibilität ab 1.7.6.0, Maximum `99.99.99`. Es gibt kein eigenes `enable()` und kein `disable()`. Das Deaktivieren in PrestaShop stoppt die registrierten Hooks. Aktivieren registriert sie über den Kern erneut.

`PmaiConfig` liest und schreibt `Configuration`-Schlüssel mit dem Präfix `PMAI_`. `PmaiProviderRouter` wählt `PmaiOpenAiProvider`, `PmaiAnthropicProvider`, `PmaiGeminiProvider` oder `PmaiMockProvider`. DeepSeek und die kompatible URL nutzen den OpenAI-kompatiblen Client. `PmaiOrchestrator` baut den Prompt, ruft das Modell und führt Werkzeuge aus `PmaiToolRegistry` aus. Die beim Aufruf genutzten Preise werden in die Usage-Zeile kopiert.

### 6.2 Dateien

| Datei | Rolle |
|---|---|
| `prestamindai.php` | Installation, Deinstallation, Hooks, Menü-Tab, Weiterleitung von **Configure**. |
| `sql/install.php` | Legt die 16 Tabellen an. |
| `sql/uninstall.php` | Löscht diese Tabellen. |
| `controllers/admin/AdminPrestamindaiController.php` | Backoffice-Reiter und POST-Aktionen. |
| `controllers/front/chat.php` | Chat-Adresse im Shop. |
| `controllers/front/cron.php` | Eine Cron-URL. |
| `src/Service/PmaiConfig.php` | Vorgaben, Modelllisten, eingebaute Preise, eigene Modelle. |
| `src/Admin/PmaiForms.php` | Jedes Backoffice-Formular und die Feldbeschreibungen. |
| `src/Admin/PmaiSectionHelp.php` | Hilfetext jedes Reiters. |
| `src/Agent/PmaiToolRegistry.php` | Die 14 Werkzeuge und der Katalogmodus-Filter. |
| `src/Llm/PmaiOpenAiProvider.php` | OpenAI, DeepSeek und die kompatible URL. |
| `src/Llm/PmaiAnthropicProvider.php` | Anthropic. |
| `src/Llm/PmaiGeminiProvider.php` | Gemini. |
| `src/Llm/PmaiMockProvider.php` | Offline-Demo. |
| `src/Knowledge/PmaiIndexer.php` | Entdecken und neu indexieren. |
| `src/Safety/PmaiGuardrails.php` | Ersetzt Karte, IBAN und PESEL. |
| `upgrade/` | Versions-Upgrades rufen `upgradeDb()` auf. |
| `translations/{iso}.php` | Backoffice-Texte. |
| `views/` | Templates, CSS und JS für Backoffice und Shop. |

### 6.3 Controller

`AdminPrestamindai` ist die Menüklasse. Elternklasse ist die erste vorhandene unter `AdminParentCustomerThreads`, `AdminCustomerThreads` und `IMPROVE`. Die Tab-Beschriftung ist **PrestaMind AI**. `getContent()` leitet auf diesen Controller um.

`pmai_tab` ist eines von `dashboard`, `live`, `history`, `conversations`, `knowledge`, `triggers`, `playground`, `evals`, `escalations`, `settings`, `updates`. Einstellungen lesen außerdem `pmai_sub`: `health`, `widget`, `provider`, `knowledge`, `limits`, `privacy`, `escalation`, `reminders`, `couriers`, `tools`.

`controllers/front/chat.php` nimmt die Shop-Operationen init, message, feedback, confirm, add_to_cart, escalate, poll, event und open_trigger entgegen. `controllers/front/cron.php` verlangt das Cron-Token. Ein falsches Token liefert JSON `ok: false` und `error: token`.

### 6.4 Hooks

Bei der Installation registriert: `displayBackOfficeHeader`, `dashboardZoneTwo`, `actionAdminControllerSetMedia`, `displayHeader`, `displayBeforeBodyClosingTag`, `displayFooter`, `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`, `actionObjectCmsAddAfter`, `actionObjectCmsUpdateAfter`, `actionObjectCmsDeleteAfter`, `actionValidateOrder`, `registerGDPRConsent`, `actionDeleteGDPRCustomer`, `actionExportGDPRData`.

`displayBeforeBodyClosingTag` gibt das Widget aus, `displayFooter` ist der Ersatz. Produkt- und CMS-Hooks markieren Dokumente zur Neuindexierung. `actionValidateOrder` verknüpft die Bestellung mit der Umsatzzahl. GDPR-Hooks exportieren oder löschen die Modulzeilen dieses Kunden. **Repair hooks** ruft `ensureHooks()` für jeden fehlenden Namen auf. Das Modul stellt keine eigenen Hooks für andere Module bereit.

### 6.5 Überschreibungen

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6 Datenbank

Die Deinstallation führt `DROP TABLE` auf jeder Tabelle unten aus. Die Installation nutzt `CREATE TABLE IF NOT EXISTS`. Eine fehlgeschlagene Deinstallation, die Tabellen liegen ließ, würde alte Zeilen behalten. Eine normale Deinstallation löscht sie, die nächste Installation ist leer.

| Tabelle | Inhalt |
|---|---|
| `PREFIX_pmai_thread` | Ein Gespräch: Shop, Kunde, Gast, Kanal, Status, Seite. |
| `PREFIX_pmai_message` | Nachrichten des Threads, einschließlich Karten-Payload. |
| `PREFIX_pmai_tool_call` | Werkzeugname, Argumente und Ergebnis einer Nachricht. |
| `PREFIX_pmai_doc` | Indexiertes Produkt-, CMS- oder FAQ-Dokument. |
| `PREFIX_pmai_chunk` | Stücke eines Dokuments, einschließlich Embedding, wenn vorhanden. |
| `PREFIX_pmai_cache` | Zwischengespeicherte Regelantworten. |
| `PREFIX_pmai_trigger` | Auslöserregeln. |
| `PREFIX_pmai_offer` | Rabattregeln. |
| `PREFIX_pmai_event` | Shop-Ereignisse für Auslöser und Statistik. |
| `PREFIX_pmai_usage` | Ein Modellaufruf: Anbieter, Modell, Token, Preisschnappschuss, Kosten, Status. Kein Nachrichtentext. |
| `PREFIX_pmai_request` | Zeilen der Anfragebegrenzung. |
| `PREFIX_pmai_cart_reminder` | Eine gesendete Warenkorb-Erinnerung. |
| `PREFIX_pmai_escalation` | Übergabe, Rückgabe oder Angebot sowie das Ergebnis der Benachrichtigung. |
| `PREFIX_pmai_ratelimit` | Zähler des kurzen Fensters. |
| `PREFIX_pmai_eval_case` | Eine Qualitätsfrage und die verlangten Wörter. |
| `PREFIX_pmai_eval_run` | Ein Lauf dieser Tests. |

`PmaiConfig::PRICES_CHECKED` ist `2026-10-31`. Eingebaute Chat- und Embedding-Ids und Preise stehen in `PmaiConfig::builtinModels()`, `builtinEmbeddingModels()` und `builtinPrices()`. Eigene Ids sind JSON in `PMAI_CUSTOM_MODELS`. Bearbeitete Preise sind JSON in `PMAI_MODEL_PRICES` und gewinnen gegen den eingebauten Preis.

### 6.7 Schlüssel und Übersetzungen

Jeder Schlüssel ist `PMAI_` plus der Name aus `PmaiConfig::defaults()`. Anbieter-Geheimnisse sind `PMAI_KEY_OPENAI`, `PMAI_KEY_ANTHROPIC`, `PMAI_KEY_GEMINI`, `PMAI_KEY_DEEPSEEK`, `PMAI_KEY_MISTRAL`, `PMAI_KEY_COMPATIBLE`, `PMAI_KEY_MOCK` und `PMAI_KEY_DHLTRACK`. Sie werden mit libsodium verschlüsselt, wenn `sodium_crypto_secretbox` existiert, sonst mit OpenSSL. `PMAI_CRON_TOKEN` ist ein zufälliger Hex-String, der bei der Installation entsteht, wenn er leer ist.

Modellwahl-Schlüssel sind `PMAI_MODEL_MAIN_{PROVIDER}` und `PMAI_MODEL_FAST_{PROVIDER}`. Nach der Installation: OpenAI `gpt-6.1-sol` / `gpt-6-luna`, Anthropic `claude-sonnet-5-5` / `claude-haiku-5-5`, Gemini `gemini-2.5-flash` / `gemini-2.5-flash-lite`, DeepSeek `deepseek-flash` / `deepseek-flash`, Mistral `mistral-large-latest` / `mistral-small-latest`, compatible `llama3.1` / `llama3.1`, mock `mock` / `mock`. `PMAI_PROVIDER` ist `mock`. `PMAI_EMBED_PROVIDER` ist `none`. `PMAI_EMBED_MODEL` ist leer, also wird das erste eingebaute Embedding-Modell des gewählten Anbieters benutzt.

`PMAI_BOT_NAME`, `PMAI_GREETING`, `PMAI_DISCLOSURE` und `PMAI_REMINDER_SUBJECT` sind mehrsprachig. Die Feldhilfe ist das `desc`-HTML aus `PmaiForms`. Eine Sprache fügen Sie über `translations/{iso}.php` hinzu. Zeichenketten, die nicht durch `$this->l()` gehen, bleiben wie in den PHP-Arrays geschrieben (Kachelnamen, Modell-Ids, Werkzeug-Ids).

### 6.8 Erweitern

Template und CSS des Shop-Widgets lassen sich im Theme auf die übliche PrestaShop-Art unter `modules/prestamindai/views/` überschreiben. Das Backoffice ist keine Theme-Überschreibung. Ändern Sie Modell-Ids nicht im Theme. Ein Modell fügen Sie unter **Model provider** hinzu. Ein Cookie-Banner kann nach der Zustimmung `window.PrestaMindAI.setConsent(true)` aufrufen. Das Modul liefert kein Banner mit.

## 7. Hilfe

Modulseite: [https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)

Um zu diesem Modul zu schreiben, melden Sie sich mit Ihrem Kundenkonto auf mypresta.eu an, öffnen Sie das Kontaktformular und wählen Sie das Thema **Support for paid modules**. Das Formular sagt, dass die Anmeldung für kostenpflichtige Module erforderlich ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.
