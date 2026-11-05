---
title: "My AI Mistral - AI content generation - Dokumentation und Benutzerhandbuch"
description: "Anleitung zu Konfiguration, täglicher Nutzung und Fehlerbehebung für Händler, die My AI Mistral bereits in ihrem PrestaShop-Shop installiert haben."
sidebar:
  label: "My AI Mistral - AI content generation - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Meta and catalog descriptions with Mistral AI auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai/)
>
> ---


## 1. Voraussetzungen

### 1.1 Shop und Server

| Punkt | Erforderlich | Hinweise |
|---|---|---|
| PrestaShop | 1.6 bis 9.x | Das Modul gibt Unterstützung für die Versionen 1.6 bis 9.99.99 an. Der Reiter **My AI Mistral** auf der Produktbearbeitungsseite und die kleinen Schaltflächen "Generate with AI" sind für PrestaShop 1.7, 8 und 9 ausgelegt. |
| PHP | 7.0 oder neuer | Die Installation bricht mit einer Meldung ab, wenn der Server eine ältere PHP-Version verwendet. |
| PHP-Erweiterungen | cURL, JSON, mbstring, DOM | cURL wird für jeden Aufruf von Mistral AI verwendet. DOM und mbstring dienen dazu, die Webseiten der Fotosuche auszulesen sowie den generierten Text zu messen und zu kürzen. |
| Ausgehende Verbindung | HTTPS (Port 443) zu `api.mistral.ai` | Der Server muss die Mistral-AI-API aufrufen dürfen. Hosting-Tarife, die ausgehende Verbindungen sperren, funktionieren nicht. |
| Shop-Frontadresse | Vom Browser aus erreichbar | Die Schaltflächen im Back Office senden ihre Anfragen an eine Adresse im Frontend Ihres Shops. Ein Passwortschutz, eine Firewall-Regel oder eine Wartungsseite, die diese Adresse blockiert, lässt die Schaltflächen fehlschlagen. |

### 1.2 Mistral-AI-Konto

1. Erstellen Sie ein Konto in der Mistral-AI-Konsole und öffnen Sie die Seite für API-Schlüssel: https://console.mistral.ai/api-keys/
2. Erstellen Sie einen Schlüssel und kopieren Sie ihn. Die Konsole zeigt ihn nur einmal an.
3. Stellen Sie sicher, dass das Konto die API nutzen darf (ein Tarif oder eine Abrechnung mit API-Zugang). Jeder generierte Text ist eine API-Anfrage, die bezahlt oder auf Ihr Kontingent angerechnet wird.

Das Modul benötigt kein anderes Modul und fügt keinen Override hinzu. Es zeigt Ihren Kunden nichts an.

### 1.3 Kosten und Last

- Ein generiertes Feld in einer Sprache entspricht einer Anfrage. Ein Stapel von 40 Produkten mit Beschreibungen und Meta-Tags in zwei Sprachen sind 40 × 4 × 2 = 320 Anfragen, weil die Option für Beschreibungen zwei Felder schreibt und die Meta-Option ebenfalls zwei Felder.
- Jede Anfrage wartet höchstens so lange auf die Antwort, wie unter **API timeout (seconds)** eingestellt ist (standardmäßig 120 Sekunden). Ein großer, im Browser gestarteter Stapel ist von Natur aus langsam; nutzen Sie bei großen Katalogen Cron.
- Das Modul kann die Generierung nach einer monatlichen Anzahl erfolgreicher Anfragen stoppen (**Monthly generation budget** im Studio).

## 2. Installation

### 2.1 Modul installieren

1. Öffnen Sie **Modules > Module Manager** (**Modules and Services** in PrestaShop 1.6).
2. Klicken Sie auf **Upload a module** (**Add a new module** in 1.6) und wählen Sie die ZIP-Datei des Moduls.
3. Klicken Sie auf **Install** und dann auf **Configure**.

Was die Installation für Sie erledigt:

- Sie fügt den Back-Office-Menüeintrag **AI Content Generator** unter **Modules** hinzu. Er öffnet die Einstellungsseite des Moduls; alle weiteren Bildschirme erreichen Sie über die Menüleiste am oberen Rand dieser Seite.
- Sie legt zwei Datenbanktabellen an: eine für die Prompt-Vorlagen und eine für den Verlauf der Anfragen.
- Sie speichert 16 vorgefertigte Prompt-Vorlagen (Produktnamen, Beschreibungen, Meta-Titel, Meta-Beschreibungen und Tags). Alle sind zu Beginn aktiviert.
- Sie erzeugt die Geheimcodes für die Back-Office-Schaltflächen und für Cron und wählt das Modell **mistral-small-latest**.
- Sie leert den PrestaShop-Cache nicht. Erscheint der Menüeintrag nicht, leeren Sie den Cache unter **Advanced Parameters > Performance**.

Beim ersten Aufruf sehen Sie möglicherweise die grüne Meldung "Mistral AI API Key has been automatically cleaned (whitespace removed)". Sie bedeutet lediglich, dass der leere Platzhalter-Schlüssel bereinigt wurde. Es ist nichts falsch.

### 2.2 Erste Schritte nach der Installation

1. Öffnen Sie **AI Content Generator > Settings > Mistral** und fügen Sie Ihren API-Schlüssel ein.
2. Behalten Sie für einen ersten Test das Standardmodell bei und klicken Sie auf **Save**.
3. Öffnen Sie **Settings > Playground**, schreiben Sie eine kurze Anweisung und klicken Sie auf **Generate**. Eine Antwort zeigt, dass die Verbindung funktioniert.
4. Öffnen Sie ein vorhandenes Produkt, gehen Sie zum Reiter **Modules**, wählen Sie **My AI Mistral**, öffnen Sie **Simulate** und klicken Sie neben **Meta title** auf **Try**. Der Text wird angezeigt, gespeichert wird nichts.

### 2.3 Aktualisierung

Laden Sie die neue ZIP-Datei im Module Manager genauso hoch wie bei der Erstinstallation. Einstellungen, Vorlagen und Verlauf bleiben erhalten. Die Seite **Updates** des Moduls zeigt an, ob eine neuere Version existiert (Abschnitt 3.15).

### 2.4 Deinstallation

Die Deinstallation entfernt die Menüeinträge, die Prompt-Vorlagen, den gesamten Anfrageverlauf und die Moduleinstellungen, einschließlich API-Schlüssel und Cron-Geheimnisse. Eine Neuinstallation beginnt von vorn und erzeugt neue Geheimnisse, daher muss jede Adresse, die Sie einem Zeitplaner übergeben haben, ersetzt werden.

Bereits in Produkte und Kategorien geschriebene Texte, importierte Fotos, mit **New product** angelegte Produkte und Tags bleiben in Ihrem Shop erhalten. Die Einstellungen der Update-Prüfung und einige übrig gebliebene Filterwerte werden nicht entfernt.

## 3. Konfiguration und Arbeit im Back Office

Die Screenshots in diesem Handbuch zeigen das englische Back Office. Menü-, Feld- und Schaltflächennamen werden daher auf Englisch und in Fettschrift angegeben, so wie Sie sie auf dem Bildschirm sehen.

### 3.1 Wie die Arbeit abläuft

1. **Connect** – API-Schlüssel einfügen und Modell wählen (Settings – Mistral).
2. **Set the rules** – Hausregeln, Budget und Qualitätsprüfung (Settings – Studio).
3. **Prepare prompts** – Prompt-Vorlagen bearbeiten oder hinzufügen (Settings – Prompt templates) und im Playground ausprobieren.
4. **Generate** – wählen Sie einen von drei Wegen:
   - ein Produkt nach dem anderen, von der Produktbearbeitungsseite (Abschnitt 3.16) oder mit den kleinen Schaltflächen "Generate with AI" neben den Feldern (Abschnitt 3.17);
   - viele Produkte oder Kategorien auf einmal, über die Generate-Seiten (Abschnitte 3.9 und 3.10);
   - automatisch in kleinen Stapeln mit Cron (Abschnitt 3.12).
5. **Check** – jede Anfrage wird im History protokolliert (Abschnitt 3.13). Ein falscher Text lässt sich über den Reiter History des Produkts selbst wiederherstellen.

Jede Einstellungsseite hat ihre eigene Schaltfläche **Save**. Speichern Sie eine Seite, bevor Sie sie verlassen, denn die Seiten teilen sich kein gemeinsames Formular.

### 3.2 Modul öffnen und Menüleiste

Öffnen Sie **Modules > AI Content Generator** oder klicken Sie im Module Manager auf **Configure**. Jeder Bildschirm zeigt oben dieselbe Menüleiste:

| Menüpunkt | Was er öffnet |
|---|---|
| Dashboard | Nutzungskarten und Diagramme (Abschnitt 3.3). |
| Settings | Eine Gruppe mit fünf Unterseiten: General, Mistral, Studio, Prompt templates, Playground (Abschnitte 3.4 bis 3.8). |
| Generate | Massengenerierung für Produkte und Kategorien (Abschnitte 3.9 und 3.10). |
| New product | Ein Produkt aus einem kurzen Briefing anlegen (Abschnitt 3.11). |
| Cron | Adressen für zeitgesteuerte Generierung (Abschnitt 3.12). |
| History | Liste aller Anfragen mit Filtern und Token-Summen (Abschnitt 3.13). |
| Images | Einstellungen der Fotosuche (Abschnitt 3.14). |
| Updates | Update-Prüfung (Abschnitt 3.15). |

Jeder Bildschirm hat eine Schaltfläche **Help**. Sie öffnet ein Seitenpanel mit einer kurzen Erklärung zu diesem Bildschirm. Wenn Sie mit der Maus über einen Menüpunkt fahren, erscheint ein einzeiliger Hinweis. Unter jedem Feld finden Sie eine Beschreibung in drei Teilen: was das Feld bewirkt, wie Sie es einstellen und welche Wirkung es hat.

### 3.3 Dashboard

![Dashboard with usage cards and charts](https://mypresta.eu/docs/images/docs/myaimistral-dashboard.webp)

Das Dashboard zählt, was das Modul im gewählten Zeitraum getan hat. Die Zeile oben nennt den aktiven Dienst und das Modell.

| Element | Standard | Was es zeigt |
|---|---|---|
| Period buttons | 30 days | Today, 7 days, 30 days, 90 days, This month, All time. |
| From / To and Apply | vom Zeitraum befüllt | Ein eigener Zeitraum. Liegt From nach To, werden beide Daten vertauscht. |
| Requests | – | Jeder gespeicherte Aufruf von Mistral AI im Zeitraum. |
| Success | – | Aufrufe, die einen Text geliefert haben. |
| Errors | – | Fehlgeschlagene Aufrufe. Öffnen Sie History, um die Ursache zu sehen. |
| Tokens sent | – | Umfang der von Ihnen gesendeten Anweisungen. |
| Tokens received | – | Umfang der Antworten. |
| Requests and errors | – | Liniendiagramm pro Tag. |
| Tokens sent and received | – | Liniendiagramm pro Tag. |
| Requests by model | – | Balkendiagramm. |

Die Seite berichtet nur. Von hier aus wird im Katalog nichts generiert oder geändert, und History wird nicht gelöscht.

### 3.4 Settings – General

![Settings – General](https://mypresta.eu/docs/images/docs/myaimistral-settings-general.webp)

Öffnen Sie **Settings > General**. Diese Seite bestimmt, was Mitarbeiter im Back Office sehen. Das Speichern ändert keinen Produkttext.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Live mode | Disabled | Kennzeichnet das Modul als im echten Shop laufend statt in einem Testaufbau. Aktivieren Sie es im Produktivshop. |
| Debug mode | Disabled | Schreibt zusätzliche Diagnosedetails in das PrestaShop-Log, wenn ein Aufruf beim Anbieter fehlschlägt. Schalten Sie ihn nur ein, solange Sie einen Fehler untersuchen. Kunden sehen ihn nie. Er ist nicht dasselbe wie **Enable Debug** auf der Cron-Seite. |
| API timeout (seconds) | 120 | Wie viele Sekunden ein Aufruf an Mistral dauern darf, bevor das Modul aufgibt. Der Wert wird zwischen 10 und 600 gehalten. Ein leerer oder nicht numerischer Wert wird als 120 gespeichert. Erhöhen Sie ihn für lange Texte und langsame Modelle in Richtung 600. |
| Product Edit History | Enabled | Zeigt den Unterreiter **History** auf der Produktbearbeitungsseite, damit Sie einen alten Wert zurückspielen können. Vergangene Zeilen bleiben in jedem Fall in History. |
| Admin Top Bar CTA | Enabled | Zeigt das kleine Zauberstab-Symbol in der oberen Leiste des Back Office. Das Deaktivieren entfernt nur diese Schaltfläche, nicht das Modulmenü. |
| Product edit page Form | Enabled | Zeigt das Panel **My AI Mistral** (Generate, Simulate, Photos) im Reiter **Modules** der Produktbearbeitungsseite. Deaktivieren Sie es, wenn nur Massengenerierung und Cron genutzt werden sollen. Die kleinen Schaltflächen "Generate with AI" neben den Feldern (Abschnitt 3.17) werden in dieser Version durch diese Einstellung nicht abgeschaltet. |
| AI Image Finder | Enabled | Zeigt oder verbirgt die Fotosuche auf der Produktbearbeitungsseite. Ein Bild wird erst importiert, nachdem Sie es bestätigt haben. |
| AI Image Search Prompt | Eingebaute Anweisung | Die Anweisung, die gesendet wird, wenn jemand nach Fotos sucht. `{product_name}` und `{product_description}` werden durch das aktuelle Produkt ersetzt. Behalten Sie die Aufforderung bei, eine Liste von Seitenadressen im JSON-Format zu liefern. Dieselben beiden Felder wiederholen sich auf der Seite **Images**. |

Klicken Sie auf **Save**. Die Bestätigung lautet "Settings Updated".

### 3.5 Settings – Mistral

![Settings – Mistral](https://mypresta.eu/docs/images/docs/myaimistral-settings-mistral.webp)

Öffnen Sie **Settings > Mistral**. Die Seite verbindet den Shop mit Ihrem Mistral-AI-Konto und legt fest, wie abwechslungsreich die Wortwahl ist. Die Sampling-Felder ändern nichts daran, welche Produkte aktualisiert werden.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Mistral AI API KEY | leer | Der Schlüssel von https://console.mistral.ai/api-keys/. Leerzeichen werden beim Speichern entfernt. Lassen Sie das Feld unberührt, um den gespeicherten Schlüssel zu behalten. Ein Wert mit weniger als 10 Zeichen wird abgelehnt, solange kein Schlüssel gespeichert ist. |
| Model | mistral-small-latest | Das Modell, das den Text schreibt. Die Liste enthält die eingebauten und die von Ihnen hinzugefügten Modelle. Ein Modell, das Ihr Schlüssel nicht nutzen kann, liefert einen API-Fehler statt eines Textes. |
| Add a Mistral model | leer | Geben Sie den exakten Modellnamen aus Ihrem Mistral-Konto ein und drücken Sie **Add model**. Der neue Name erscheint in der Liste **Model** und wird sofort zum aktiven Modell. Namen dürfen Buchstaben, Ziffern und die Zeichen `.`, `_`, `:` und `-` enthalten. Neben jedem hinzugefügten Namen steht ein Link **Remove**. Eingebaute Modelle lassen sich nicht entfernen. |
| Max Tokens | 3200 | Die längste Antwort in Tokens. Verwenden Sie etwa 256 für eine Meta-Beschreibung und 1000 oder mehr für eine vollständige HTML-Beschreibung. Ein zu niedriger Wert schneidet den Text ab. Ein hoher Wert kostet mehr. |
| Temperature | 0.7 | Wie frei das Modell Wörter wählt, von 0 bis 1. Etwa 0.2 eignet sich für Meta-Texte, etwa 0.7 für Beschreibungen. Ändern Sie entweder Temperature oder Top P, nicht beides. |
| Top P | 1 | Eine weitere Möglichkeit, zu begrenzen, wie überraschend das nächste Wort sein darf, von 0 bis 1. Lassen Sie 1 stehen, wenn Sie Temperature einstellen. |
| Frequency Penalty Value | 0 | Von -2 bis 2. Ein positiver Wert wie 0.3 bis 0.6 verringert wiederholte Formulierungen innerhalb einer Antwort. |
| Presence Penalty Value | 0 | Von -2 bis 2. Ein positiver Wert verteilt den Text auf mehr Punkte. Manche Modelle ignorieren ihn. |

Die eingebauten Modelle sind: mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest, codestral-latest und open-mistral-nemo.

Lehnt Mistral eine der numerischen Einstellungen für ein bestimmtes Modell ab, merkt sich das Modul das, lässt diese Einstellung für dieses Modell weg und versucht es erneut. Sie müssen nichts tun.

Das Feld für den Modellnamen muss beim Speichern mindestens 3 Zeichen enthalten, sonst zeigt die Seite "OpenAi Model field is invalid!". Die Bestätigung nach dem Speichern lautet "OpenAi Settings Updated". Die Meldungen "Model added.", "Model removed." und "That model is already built in." gehören zu den Schaltflächen zum Hinzufügen und Entfernen.

### 3.6 Settings – Studio

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaimistral-settings-studio.webp)

Studio wird auf jeden Prompt angewendet, egal wo die Anfrage beginnt: Produktseite, Generate-Seiten, Cron, Playground oder obere Leiste. Leere Felder werden übersprungen.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Brand voice | leer | Ein kurzes Briefing, das dem Modell sagt, wer spricht, zum Beispiel "specialist workshop, short sentences, no hype". |
| Audience | leer | Die Leserschaft, für die geschrieben werden soll, zum Beispiel "professional installers". |
| Tone | leer | Die Stimmung der Formulierung. Ein oder zwei Wörter genügen. |
| Glossary | leer | Markennamen, Materialien und Schreibweisen, die das Modell exakt übernehmen muss. Ein Begriff pro Zeile. |
| Forbidden words | leer | Wörter und Wendungen, die in einer gespeicherten Antwort nicht vorkommen dürfen. Eines pro Zeile. Wird nur verwendet, wenn Quality gate auf Enabled steht. |
| Monthly generation budget | 0 | Die höchste Zahl erfolgreicher Generierungen im laufenden Kalendermonat. 0 bedeutet kein Limit. Der Zähler beginnt am ersten Tag des Monats neu. Ist die Zahl erreicht, stoppt die Generierung mit einer Budget-Meldung. Fehlgeschlagene Aufrufe werden nicht gezählt. |
| Quality gate | Enabled | Prüft jede Antwort gegen Forbidden words, bevor etwas gespeichert wird. Eine Antwort mit einem aufgelisteten Wort wird abgelehnt, nicht ins Produkt geschrieben und in History als Fehler gespeichert. Bei Disabled wird die Antwort trotzdem gespeichert. |

Klicken Sie auf **Save studio**. Die Bestätigung lautet "Studio settings saved.".

### 3.7 Settings – Prompt templates

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaimistral-settings-templates.webp)

Eine Prompt-Vorlage ist eine gespeicherte Anweisung. Die Seite zeigt die Liste **Prompt Templates** mit einer Schaltfläche zum Anlegen einer neuen Vorlage.

#### Die Liste

| Spalte | Was sie zeigt |
|---|---|
| ID | Nummer der Vorlage. |
| Title | Der Name, den Sie in den Vorlagenlisten sehen. |
| Prompt | Der Text der Anweisung. |
| Status | Klicken Sie auf das Symbol, um eine Vorlage ein- oder auszuschalten. |
| Timestamp | Erstellungszeitpunkt. |

Jede Zeile hat **Edit** und **Delete**. Markieren Sie mehrere Zeilen und nutzen Sie das Sammel-**Delete**, um sie zu entfernen. Die neuesten Vorlagen stehen oben.

#### Das Formular "Generate Prompt Template"

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Status | nicht gesetzt | Aktivierte Vorlagen werden im Produktpanel, auf der Seite Generate – Products und in der oberen Leiste angeboten. Deaktivierte bleiben in der Tabelle, werden dort aber nicht angeboten. Wählen Sie vor dem Speichern **Enabled**, denn eine neue Vorlage startet ohne Auswahl. |
| Prompt title | leer | Der in den Auswahllisten angezeigte Name. Er wird nicht an das Modell gesendet. Pflichtfeld. |
| Prompt content | leer | Die Anweisung, die an das Modell gesendet wird. Platzhalter in geschweiften Klammern werden vor dem Senden für jede Position ersetzt. Doppelte Anführungszeichen werden beim Speichern durch einfache ersetzt. Pflichtfeld. |

Klicken Sie auf **Save Prompt**. Die Bestätigungen lauten "Prompt template successfully added!", "Prompt template successfully updated!" und "Prompt template removed.". **Go Back to Module Settings** führt zur Liste zurück.

#### Platzhalter

| Platzhalter | Wird ersetzt durch | Funktioniert in |
|---|---|---|
| {product_name} | Produktname | Produktgenerierung |
| {product_description} | Langbeschreibung | Produktgenerierung |
| {product_description_short} | Kurzbeschreibung | Produktgenerierung |
| {product_tags} | Aktuelle Tags | Produktgenerierung |
| {product_reference} | Referenz | Produktgenerierung |
| {product_ean13} | EAN-13-Code | Produktgenerierung |
| {product_weight} | Gewicht | Produktgenerierung |
| {product_brand} | Markenname | Produktgenerierung |
| {product_default_category} | Name der Standardkategorie | Produktgenerierung |
| {product_category_description} | Beschreibung der Standardkategorie | Produktgenerierung |
| {product_categories} | Namen aller Kategorien des Produkts | Produktgenerierung |
| {product_attributes} | Kombinationsattribute (Gruppe und Wert) | Produktgenerierung |
| {product_features} | Namen der Merkmale | Produktgenerierung |
| {product_feature_values} | Merkmale mit ihren Werten | Produktgenerierung |
| {product_images} | Adressen der Produktfotos | Produktgenerierung |
| {category_name} | Kategoriename | Kategoriegenerierung |
| {category_description} | Kategoriebeschreibung | Kategoriegenerierung |
| {category_parent_name} | Name der übergeordneten Kategorie | Kategoriegenerierung |
| {shop_name} | Shop-Name | Produkt- und Kategoriegenerierung |
| {shop_url} | Shop-Domain | Produkt- und Kategoriegenerierung |
| {shop_language} | Name der Sprache | Produkt- und Kategoriegenerierung |
| {shop_country} | Standardland | Produkt- und Kategoriegenerierung |
| {shop_currency} | Code der Standardwährung | Produkt- und Kategoriegenerierung |

"Produktgenerierung" bedeutet das Produktpanel, Generate – Products und den Produkt-Cron. "Kategoriegenerierung" bedeutet Generate – Categories und den Kategorie-Cron. Platzhalter werden im Playground und im Feld der oberen Leiste nicht ersetzt, weil dort kein Produkt und keine Kategorie ausgewählt ist. Ein Platzhalter ohne Daten wird durch einen leeren Text ersetzt.

#### Die 16 Vorlagen, die mit dem Modul geliefert werden

| Nr. | Titel | Zweck |
|---|---|---|
| 1 | Product name 1 | Ein kürzerer, besserer Name auf Basis des aktuellen Namens. |
| 2 | Product name 2 | Ein verkaufsstarker Titel, der Marke und Standardkategorie nutzt. |
| 3 | Product description 1 | HTML-Beschreibung mit drei Überschriften und den Tags in Fettschrift. |
| 4 | Product description 2 | Beschreibung in drei schlichten Abschnitten. |
| 5 | Product description 3 | Ein langes SEO-Briefing, das zusätzlich Überschriftenideen, Keywords und Meta-Texte anfordert. |
| 6 | Product description 4 | Eine kurze Aufforderung für eine "fesselnde Beschreibung". |
| 7 | Product description 5 | Beschreibung, die die Produkt-Tags als Keywords verwendet. |
| 8 | Product description 6 | Beschreibung, die Marke und Standardkategorie verwendet. |
| 9 | Product description 7 - using product images | Beschreibung, die die Produktfotos über {product_images} einbettet. |
| 10 | Product meta title 1 | SEO-Meta-Titel, bis zu 60 Zeichen. |
| 11 | Product meta title 2 | Eine zweite Variante des Meta-Titels. |
| 12 | Product meta title 3 | Meta-Titel mit der Marke. |
| 13 | Product meta description 1 | SEO-Meta-Beschreibung, bis zu 160 Zeichen. |
| 14 | Product meta description 2 | Eine zweite Variante; der Beispieltext erwähnt eine Smartwatch. |
| 15 | Product meta description 3 | Derselbe Text wie Nummer 14. |
| 16 | Product tags | Fünf Tags in einer Zeile, durch Kommas getrennt. |

Lesen und passen Sie die Vorlagen an, bevor Sie sie bei echten Produkten einsetzen:

- Vorlage 3 weist das Modell an, einige Rechtschreibfehler in den Text einzubauen. Löschen Sie diesen Satz.
- Vorlage 5 liefert mehr als eine Beschreibung (Überschriftenideen, eine Keyword-Liste und Meta-Texte). Nutzen Sie sie als Inspiration, nicht zum direkten Speichern in das Beschreibungsfeld.
- Die Vorlagen 5, 10, 13 und 16 verlangen eine Antwort auf Englisch. Ändern Sie diese Zeile, wenn Ihr Shop eine andere Sprache nutzt.
- Die Vorlagen 14 und 15 sind für eine Smartwatch geschrieben. Ersetzen Sie das Beispiel, bevor Sie sie verwenden.

### 3.8 Settings – Playground

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaimistral-settings-playground.webp)

Der Playground sendet einen freien Prompt an das aktive Modell und gibt die Antwort unter der Schaltfläche aus. Die Antwort bleibt auf dieser Seite. Es wird kein Produkt und keine Kategorie gespeichert.

| Element | Standard | Was es bewirkt |
|---|---|---|
| Prompt box | leer | Die Anweisung für diesen einen Aufruf. Die Studio-Regeln werden hinzugefügt. |
| Generate | – | Sendet den Prompt. Während des Wartens zeigt der Antwortbereich "Working…". |
| Answer area | – | Die Antwort des Modells mit der Zahl der verbrauchten Tokens. |

Meldungen: "Write a prompt first." (das Feld ist leer) und "The request timed out or the shop blocked it." (siehe Abschnitt 5.2).

Die Anfrage wird wie jede andere in History protokolliert.

### 3.9 Generate – Products

![Generate – Products](https://mypresta.eu/docs/images/docs/myaimistral-generate-products.webp)

Öffnen Sie **Generate** und bleiben Sie bei **Products**. Die Arbeit hat zwei Schritte: eine Liste erstellen, dann die Generierung darauf ausführen.

#### Schritt 1 – Liste erstellen ("Filter products to update")

In diesem Schritt wird nichts an das Modell gesendet. Die Filter starten bei jedem Öffnen der Seite mit den unten genannten Werten.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Product Categories | keine markiert | Kategoriebaum. Es werden nur Produkte gelistet, die in einer markierten Kategorie liegen oder sie als Standardkategorie haben. Lassen Sie den Baum leer, um die Kategorie zu ignorieren. |
| Brand | Select brand (all) | Nur Produkte einer Marke. |
| Product status | Active | **Active**, **Disabled** oder **Both**. |
| Product stock | All products | **All products** oder **Only in stock products**. |
| Update only | Update all | Nutzt History: **Products that have not been updated with OpenAi content** listet Produkte ohne Zeile in History, **Products that already have been updated with OpenAi content** listet Produkte mit einer Zeile, **Update all** ignoriert History. Das Wort "OpenAi" in den ersten beiden Auswahlmöglichkeiten ist eine alte Bezeichnung; gemeint ist dieses Modul. Eine Zeile mit beliebigem Status zählt, auch eine fehlgeschlagene. |
| Product IDs | leer | Produkt-IDs, durch Kommas getrennt, zum Beispiel 12,45,103. Geben Sie nur Ziffern und Kommas ein. |
| Product Reference | leer | Eine oder mehrere Referenzen, durch Kommas getrennt. Die Referenz muss exakt übereinstimmen. |
| Product Add Date From | leer | Nur Produkte, die nach diesem Datum und dieser Uhrzeit angelegt wurden. |
| Product Add Date To | leer | Nur Produkte, die vor diesem Datum und dieser Uhrzeit angelegt wurden. |
| Minimum product ID | leer | Die kleinste Produkt-ID in der Liste. |
| Maximum product ID | leer | Die größte Produkt-ID in der Liste. |
| Product Limit | leer | Die höchste Zahl zu ladender Produkte. Nutzen Sie bei einem großen Katalog eine kleine Zahl wie 20. |

Klicken Sie auf **Go to next step**. Die Schaltfläche **Module settings** daneben ist eine alte Verknüpfung und öffnet nicht die Einstellungen dieses Moduls.

#### Schritt 2 – Generierung ausführen ("Mass product generation")

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Template | Choose a template | Kopiert eine aktivierte Vorlage in das Prompt-Feld. Der Titel selbst wird nicht gesendet. |
| Prompt box | leer | Die Anweisung, die für jedes Produkt gesendet wird, wobei die Platzhalter je Produkt ersetzt werden. Ist das Feld leer, wird für jedes Feld ein Standard-Briefing verwendet. |
| What to generate | Descriptions | **Descriptions** (lange und kurze Beschreibung), **Meta title and meta description** oder **Descriptions and meta together** (alle vier). Jedes Feld ist eine eigene Anfrage. |
| Existing text | Replace | **Replace** überschreibt den Text. **Skip if filled** lässt ein befülltes Feld unberührt und ruft das Modell dafür nicht auf. **Add above** und **Add below** behalten den alten Text und hängen den neuen an. |
| Languages | Ihre Back-Office-Sprache markiert | Markieren Sie jede Sprache, die geschrieben werden soll. Jede markierte Sprache bedeutet eine weitere Anfrage pro Feld. |

Klicken Sie auf **Run on the list below**. Die Tabelle listet die Produkte nach ID und Referenz auf. Der Lauf geht nacheinander durch jedes Produkt, jedes Feld und jede Sprache. Die Zeile über der Schaltfläche zeigt den Fortschritt, zum Beispiel "3 / 120 – description", und die Spalte **Result** zeigt die Antwort für jeden Schritt. "skipped" bedeutet, dass das Feld bereits Text hatte und Sie **Skip if filled** gewählt haben. Am Ende lautet die Zeile "Finished N products.".

Sie können einzelne Produkte in der Tabelle nicht abwählen. Ändern Sie den Filter in Schritt 1, um die Liste zu ändern. Namen und Tags sind nicht Teil dieses Laufs; nutzen Sie dafür die Produktbearbeitungsseite oder Cron. Der Text wird gespeichert, sobald jeweils eine Antwort eintrifft. Das Schließen der Seite stoppt den Lauf, und die bereits bearbeiteten Produkte behalten ihren neuen Text.

### 3.10 Generate – Categories

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaimistral-generate-categories.webp)

Öffnen Sie **Generate** und wechseln Sie zu **Categories**.

#### Schritt 1 – Liste erstellen ("Filter categories to update")

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Categories | keine markiert | Markieren Sie die Kategorien, die gelistet werden sollen. Ist nichts markiert, enthält die Liste jede Kategorie, die zum Status passt, einschließlich Root und Home. Markieren Sie bestimmte Kategorien, um das zu vermeiden. |
| Category status | Active | **Active**, **Disabled** oder **Both**. |

Klicken Sie auf **Go to next step**.

#### Schritt 2 – Generierung ausführen ("Mass category generation")

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Prompt box | leer | Die Anweisung, die für jede Kategorie gesendet wird. Verwenden Sie {category_name}, {category_description}, {category_parent_name} und die Shop-Platzhalter. Auf dieser Seite gibt es keine Vorlagenliste. |
| Field | Description | Das zu schreibende Feld: **Description**, **Name**, **Meta title**, **Meta description** oder **Additional description**. Nur dieses Feld wird gespeichert. |
| Existing text | Replace | **Replace** oder **Skip if filled**. |
| Language | Ihre Back-Office-Sprache | Eine Sprache. Führen Sie den Lauf für eine weitere Sprache erneut aus. |

Klicken Sie auf **Run on the categories below**. Die Tabelle listet die Kategorie-IDs auf und zeigt für jede ein Ergebnis.

Ist das Prompt-Feld leer, wird für Beschreibung, Meta-Titel und Meta-Beschreibung ein Standard-Briefing verwendet. Für **Name** und **Additional description** würde das Beschreibungs-Briefing verwendet, geben Sie daher für diese beiden Felder immer einen eigenen Prompt ein.

Unter der Liste zeigt die Seite außerdem das ältere Formular **Generate category content** mit der Schaltfläche **Generate content**. Es generiert nichts. Nutzen Sie die Ausführen-Schaltfläche darüber.

### 3.11 New product

![New product](https://mypresta.eu/docs/images/docs/myaimistral-new-product.webp)

**New product** bittet das Modell um einen vollständigen Produktentwurf und kann ihn in den Katalog einfügen.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| What is the product? | leer | Ein paar Sätze: was das Produkt ist, Materialien, Zielgruppe, beizubehaltende Namen. Ein ausführlicheres Briefing ergibt einen passenderen Entwurf. Ein leeres Feld wird abgelehnt. |
| Optional source URL | leer | Eine vollständige http- oder https-Adresse einer öffentlichen Seite. Ihr lesbarer Text wird dem Briefing hinzugefügt. Eine Seite, die der Shop nicht lesen kann, wird ignoriert. |
| Language | Standardsprache des Shops | Die Sprache, in der Name, Beschreibungen, Meta-Texte und Tags gespeichert werden. Andere Sprachen werden nicht befüllt. |
| Default category ID | 2 | Die Nummer der Kategorie aus **Catalog > Categories**. 2 ist meist Home. Das Produkt wird dort eingeordnet. |

Schaltflächen:

- **Generate data** zeigt den Entwurf als reinen Text im Feld unter den Schaltflächen. Es wird nichts gespeichert. Der Entwurf enthält Name, Beschreibungen, Meta-Texte, Tags, Referenz, einen Preisvorschlag und Merkmale.
- **Create product** fügt den zuletzt generierten Entwurf ein. Das neue Produkt ist **aktiv**, hat den Bestand **100**, verwendet die erste Steuerregelgruppe des Shops und wird in die von Ihnen eingegebene Kategorie eingeordnet. Nach dem Erfolg zeigt das Feld "Product #" und die neue Produktnummer.

Der Entwurf lässt sich auf dieser Seite nicht bearbeiten. Prüfen Sie Preis, Steuer, Fotos und Kategorie anschließend im Produkt; der Preis ist der vom Modell vorgeschlagene und kann 0 sein. Die Seite zeigt "Add an API key in the module settings first.", wenn kein Schlüssel gespeichert ist.

### 3.12 Cron

![Cron](https://mypresta.eu/docs/images/docs/myaimistral-cron.webp)

Mit Cron kann Ihr Server jedes Mal einige Produkte oder Kategorien aktualisieren, wenn ein Zeitplaner eine Adresse aufruft. Die Seite zeigt: das Panel **Category cron**, das Formular **CRON JOB Settings - Generate product content using Mistral AI**, das Formular **CRON JOB Settings - Generate category content using Mistral AI** und das Panel **Cron parameters**. Die Formulare erstellen und speichern nur Einstellungen; nichts läuft, bis Ihr Server die Adresse aufruft.

#### Die Cron-Adresse

Die Produktadresse sieht so aus:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent
```

Die Kategorieadresse sieht so aus:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent
```

- Ersetzen Sie `YOUR-SHOP.EXAMPLE` durch Ihre Shop-Adresse.
- Ersetzen Sie das Geheimnis durch das **Cron Job Secret Token** des passenden Formulars. Veröffentlichen Sie es niemals.
- Der Teil `&action=generateProductContent` bzw. `&action=generateCategoryContent` ist erforderlich. Ohne ihn antwortet die Adresse "Invalid action!".
- Die Panels auf der Seite zeigen die Adresse nur bis zum Geheimnis. Das Kategorie-Panel fügt `&entity=category` hinzu, das der Shop nicht verwendet. Ergänzen Sie den Teil `action` selbst, wie oben gezeigt.
- Die Zeile "Command:" in jedem Formular zeigt nur die schlichte Adresse ohne Geheimnis und ohne Aktion. Bauen Sie die vollständige Adresse selbst zusammen.

#### Produktformular

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Enable Cron Feature | No | Der Hauptschalter für Produkt- und Kategorie-Cron. Bei No antwortet jede Cron-Adresse, dass die Funktion deaktiviert ist. |
| Cron Job Secret Token | zufällig, 32 Zeichen | Das Passwort in der Produktadresse. Es muss mindestens 24 Zeichen haben. Ein kürzeres Geheimnis wird beim Laden der Modulseite durch ein zufälliges ersetzt. |
| Update Field | description | Ein Feld pro Eintrag im Zeitplaner: name, description, description_short, meta_title, meta_description oder tags. Um mehrere Felder zu befüllen, legen Sie mehrere Einträge an. |
| Selected Products | pendingMistral | Welche Produkte noch warten. **pendingMistral** nimmt Produkte, die für kein Feld eine erfolgreiche Zeile in History haben. **pendingField** nimmt Produkte ohne erfolgreiche Zeile für das gewählte Feld, sodass mehrere Einträge verschiedene Felder derselben Produkte befüllen können. **emptyField** nimmt Produkte, bei denen das gewählte Feld in der gewählten Sprache leer ist. |
| Product Categories | keine markiert | Beschränkt den Lauf auf Produkte in den markierten Kategorien. Siehe die Warnung unten. |
| Product ID list | leer | Eine feste Liste von Produkt-IDs, durch Kommas getrennt. Buchstaben werden beim Speichern verworfen. |
| Language | Standardsprache des Shops | Die zu schreibende Sprache. Weitere Sprachen brauchen einen eigenen Eintrag. |
| Product to update | 5 products | Wie viele Produkte pro Aufruf verarbeitet werden: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 oder 1000. Beginnen Sie mit 5 oder 10, damit ein langsames Modell nicht das Zeitlimit des Servers erreicht. |
| Prompt Template | erste Vorlage in der Liste | Die gespeicherte Anweisung, die für jedes Produkt verwendet wird. Siehe den Hinweis unten. |
| Enable Debug | No | Bei Yes gibt die Adresse aus, was sie tun würde, und speichert nichts. |
| CRON JOB interval | Every Hour | Eine Erinnerung daran, wie oft Sie die Adresse aufrufen wollen (von jeder Minute bis alle 6 Stunden). Das Modul startet von sich aus nichts. |

Klicken Sie auf **Save**. Die Liste für **Prompt Template** hat keine leere Auswahl und zeigt jede gespeicherte Vorlage, auch deaktivierte, die neueste zuerst. Solange Sie keine gespeichert haben, zeigt das Formular die neueste Vorlage (Product tags). Wählen Sie immer die gewünschte Vorlage und speichern Sie, sonst wird die angezeigte gespeichert.

Warnung: Sind unter **Product Categories** Kategorien markiert, wählt der Shop auch Produkte aus, deren Standardkategorie markiert ist, selbst wenn sie bereits verarbeitet wurden. Der Cron schreibt dann bei jedem Aufruf womöglich dieselben ersten Produkte neu. Lassen Sie den Kategoriebaum leer und verwenden Sie stattdessen **Product ID list**.

#### Kategorieformular

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Cron Job Secret Token | zufällig, 32 Zeichen | Das Passwort in der Kategorieadresse. Mindestens 24 Zeichen. |
| Update Field | description | name, description, meta_title oder meta_description. |
| Selected categories | pendingMistral | **pendingMistral**, **pendingField** oder **emptyField**, mit derselben Bedeutung wie bei Produkten. |
| Language | Standardsprache des Shops | Die zu schreibende Sprache. |
| Categories to update | 5 categories | Wie viele Kategorien pro Aufruf (dieselben Auswahlmöglichkeiten wie bei Produkten). |
| Prompt Template | erste Vorlage in der Liste | Die gespeicherte Anweisung. Schreiben Sie sie für eine Kategorie, nicht für ein Produkt. |
| Enable Debug | No | Bei Yes gibt die Adresse den Plan aus und speichert nichts. |
| CRON JOB interval | Every Hour | Nur eine Erinnerung. |

Klicken Sie unter dem Formular auf **Save**. Root und Home werden vom Kategorie-Cron nie verarbeitet. Der Schalter **Enable Cron Feature** befindet sich im Produktformular und steuert auch den Kategorie-Cron.

#### Geheimnisse und "Generate Token"

Wenn Sie ein neues Geheimnis möchten, tippen Sie es von Hand in das Feld ein, mindestens 24 Zeichen, Buchstaben und Ziffern. Die Schaltfläche **Generate Token** füllt das Feld in dieser Version möglicherweise nicht aus, verlassen Sie sich also nicht darauf. Ändern Sie ein neu gespeichertes Geheimnis auch in Ihrem Zeitplaner, denn die alte Adresse funktioniert dann nicht mehr. Jedes der beiden Geheimnisse öffnet jede der beiden Aktionen, halten Sie daher beide privat.

#### Zeitplaner einrichten

Fügen Sie auf einem Linux-Server eine Zeile wie diese in die Crontab ein (stündlich):

```text
0 * * * * curl -s -o /dev/null "https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent"
```

Setzen Sie die Adresse in Anführungszeichen, da sie das Zeichen `&` enthält. Unter Windows nutzen Sie die Aufgabenplanung mit `curl.exe` und derselben Adresse. Hosting-Panels mit einem "cron job"-Bildschirm übernehmen denselben Befehl.

#### Sicher testen

1. Speichern Sie das Formular mit **Enable Cron Feature** auf Yes und **Enable Debug** auf Yes.
2. Öffnen Sie die vollständige Adresse in einem Browser. Sie sehen die gelesenen Einstellungen, die Abfrage und den finalen Prompt, und es wird nichts gespeichert.
3. Stellen Sie **Enable Debug** auf No, speichern Sie und öffnen Sie die Adresse erneut. Die Seite antwortet nun mit einem kurzen Text wie "5 products have been updated.".

Bleibt **Enable Debug** eingeschaltet, speichern zeitgesteuerte Aufrufe nichts. Das ist der häufigste Grund dafür, dass ein Cron "nichts tut".

Der gespeicherte Text wird auf die von PrestaShop erlaubte Länge gekürzt: Name 128, Kurzbeschreibung 799, Meta-Titel 69 und Meta-Beschreibung 159 Zeichen. Der alte Text bleibt in History erhalten, sodass Sie ihn von der Produktseite wiederherstellen können.

### 3.13 History

![History](https://mypresta.eu/docs/images/docs/myaimistral-history.webp)

Jede Anfrage an Mistral AI wird in History mit ihrer Anweisung, ihrer Antwort oder ihrem Fehler, dem Modell, den Token-Zahlen und der benötigten Zeit protokolliert.

#### Filter und Summen

| Element | Standard | Was es bewirkt |
|---|---|---|
| Period buttons | This month | Today, 7 days, 30 days, This month, All time. |
| From / To | vom Zeitraum befüllt | Ein eigener Zeitraum. |
| Model | Any | Nur ein Modell. |
| Type | Any | Nur eine Art von Anfrage, zum Beispiel product_description oder category_meta_title. |
| Status | Any | Success oder Error. |
| Language | Any | Nur eine Sprache. |
| Employee | Any | Nur Anfragen eines Mitarbeiters. |
| Product / category ID | leer | Nur Anfragen zu diesem Datensatz. |
| Prompt or reply contains | leer | Ein Wort, das in der Anweisung und in der Antwort gesucht wird. |
| Filter | – | Wendet die Filter an. |

Die Karten zeigen Requests, Success, Errors, Tokens sent, Tokens received, Tokens total und Average time. Ein Strich bedeutet, dass Mistral für diesen Aufruf keine Token-Zahl geliefert hat. Unter den Karten stehen die Tabellen **By day**, **By model**, **By type**, **By language** und **By employee** mit den Spalten Group, Calls, Sent, Received und Total. Eine kleine Zahl neben Calls ist die Anzahl der Fehler in dieser Gruppe.

#### Die Liste "Prompt history"

Die Liste folgt den Filtern und zeigt 50 Zeilen pro Seite.

| Spalte | Was sie zeigt |
|---|---|
| ID | Nummer der Log-Zeile. |
| Status | Success oder Error. |
| Prompt | Der erste Teil der Anweisung. |
| Reply / Error | Der erste Teil der Antwort oder der Fehlertext. |
| Provider | Der Name des Anbieters, das Modell, der HTTP-Code und die Zeit in Sekunden, durch Punkte getrennt. Der Anbietername lautet weiterhin "openai". |
| Sent / Received / Total | Tokens. |
| Entity ID | Das Produkt oder die Kategorie, für die die Anfrage galt. |
| Type | Die Art der Anfrage. |
| Timestamp | Wann die Anfrage gestellt wurde. |

Klicken Sie in einer Zeile auf **View**, um den vollständigen Prompt und die Antwort zu lesen. **Back to the list** führt zur Liste zurück.

**Clear list** (Symbolleiste) löscht alle Zeilen, nicht nur die gefilterten, und zeigt "Log list successfully deleted.". Außerdem setzt es die Informationen zurück, mit denen Cron erkennt, welche Elemente bereits aktualisiert wurden (die "pending"-Ziele beginnen von vorn), setzt den monatlichen Budgetzähler zurück und entfernt die vorherigen Texte, die für **Restore** benötigt werden. Es gibt kein Rückgängigmachen.

### 3.14 Images

![Images](https://mypresta.eu/docs/images/docs/myaimistral-images.webp)

Die Seite **AI Image Finder** enthält dieselben zwei Einstellungen wie das Ende von Settings – General. Das Speichern lädt kein Bild herunter und ändert keinen Text.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| AI Image Finder | Enabled | Zeigt oder verbirgt die Fotosuche auf der Produktbearbeitungsseite. |
| AI Image Search Prompt | Eingebaute Anweisung | Die Anweisung, die gesendet wird, wenn jemand nach Fotos sucht. `{product_name}` und `{product_description}` werden durch das aktuelle Produkt ersetzt. Der eingebaute Text verlangt genau 5 Seitenadressen als JSON-Liste. Ändern Sie die Formulierung, wenn Sie Hersteller-Websites bevorzugen. Ein vager Prompt liefert unpassende Links. |

Klicken Sie auf **Save**. Die Bestätigung lautet "Settings saved.".

So funktioniert es: Das Modell schlägt Webseiten vor, die das Produkt wahrscheinlich zeigen, das Modul öffnet diese Seiten und listet die gefundenen Fotos auf, und Sie markieren die Fotos, die importiert werden sollen. Das Modul prüft nicht, wem die Fotos gehören. Verwenden Sie nur Fotos, zu deren Nutzung Sie berechtigt sind.

### 3.15 Updates

![Updates](https://mypresta.eu/docs/images/docs/myaimistral-updates.webp)

| Element | Standard | Was es bewirkt |
|---|---|---|
| Manual Check – Check Now | – | Fragt den Update-Server einmal nach der neuesten Version. Die Antwort lautet "Module is up to date!" oder "New version available!". |
| Automatic Notifications | Enabled | Etwa alle drei Tage prüft das Modul im Hintergrund. Gibt es eine neuere Version, sehen Mitarbeiter im Back Office ein Warnbanner. Wählen Sie Disabled, um Updates von Hand zu verwalten. |
| Product Page | – | Ein Link zur Modulseite. |

Klicken Sie auf **Save**. Die Bestätigung lautet "Update settings saved.". Die Prüfung sendet den Modulnamen, seine Version und Ihre Shop-Adresse an MyPresta.eu.

### 3.16 Produktbearbeitungsseite

![Product edit page – My AI Mistral tab](https://mypresta.eu/docs/images/docs/myaimistral-product-edit.webp)

Öffnen Sie **Catalog > Products**, bearbeiten Sie ein vorhandenes Produkt und öffnen Sie den Reiter **Modules**. Wählen Sie **My AI Mistral**. Der Reiter hat die Unterreiter **Generate**, **Simulate**, **Photos** und **History**. Die ersten drei erscheinen, wenn **Product edit page Form** auf Enabled steht; **History** erscheint, wenn **Product Edit History** auf Enabled steht.

#### Gemeinsame Bedienelemente von Generate und Simulate

| Element | Standard | Was es bewirkt |
|---|---|---|
| Language | erste Sprache | Klicken Sie auf eine Sprache oder auf **Every language**, um alle nacheinander zu schreiben. |
| If the field already has text | Replace | **Replace**, **Add above**, **Add below** oder **Skip if filled**. Nur im Unterreiter Generate sichtbar. |
| Use your own instruction or a saved prompt | geschlossen | Öffnet ein Filterfeld und Kacheln: **Standard brief** und jede aktivierte Vorlage. Klicken Sie auf eine Kachel, um sie zu verwenden. |
| Instruction | leer | Ihr eigener Text. Ist es leer, wird das Standard-Briefing des Feldes verwendet, dessen Schaltfläche Sie drücken. Platzhalter werden für dieses Produkt ersetzt. |

Das Feld Instruction behält den Text des letzten Laufs. Nachdem Sie eine Schaltfläche gedrückt haben, zeigt das Feld das verwendete Briefing, und die nächste Schaltfläche verwendet es erneut. Leeren Sie das Feld, bevor Sie die Schaltfläche eines anderen Feldes drücken.

#### Generate

Jede Karte hat eine Schaltfläche **Fill**: **Description** ("The long text on the product page, with a short intro and a feature list."), **Short description**, **Name**, **Meta title**, **Meta description** und **Tags**. Der Text wird **sofort im Produkt gespeichert** und unter den Karten mit der Zahl der Tokens angezeigt. Die Karte **SEO pack** hat die Schaltfläche **Fill all**; sie befüllt Name, beide Beschreibungen und beide Meta-Felder in einer Anfrage und antwortet "SEO pack saved. Refresh the product to see it.".

Wichtig: Das in Ihrem Browser geöffnete Produktformular enthält weiterhin die alten Texte. Laden Sie die Produktseite neu, bevor Sie in PrestaShop auf **Save** klicken, sonst überschreiben die alten Texte die neuen.

#### Simulate

Dieselben Karten mit der Schaltfläche **Try**. Der Text wird auf der Seite angezeigt, das Produkt wird nicht verändert. Nutzen Sie das, um Prompts und Modelle zu vergleichen, bevor das Modul schreibt.

#### Photos

![Photos sub-tab](https://mypresta.eu/docs/images/docs/myaimistral-product-photos.webp)

1. Klicken Sie auf **Find pages**. Das Modell schlägt Seiten vor, die das Produkt wahrscheinlich zeigen, und das Modul listet die dort gefundenen Fotos auf.
2. Markieren Sie die gewünschten Fotos. Die Meldung lautet "Tick the photos you want, then add them to this product.".
3. Klicken Sie auf **Add selected to this product**. Die Fotos werden heruntergeladen und dem Produkt zugeordnet. Die Meldung lautet "Done. Reload the product to see the new photos." oder nennt die Anzahl der hinzugefügten.

Ist die Suche ausgeschaltet, sagt der Reiter das und verweist auf Settings – General. Weitere Meldungen: "No photos were found on the suggested pages.", "The search failed." und "The photos could not be added.".

#### History

Eine Tabelle mit **When**, **Type**, **Status** und einer Schaltfläche **Restore** für die letzten 50 Anfragen des Produkts. **Restore** fragt "Restore the previous value?", spielt den vorherigen Text zurück und antwortet "Content successfully restored. Refresh this page to see changes.". Die Schaltfläche erscheint nur bei erfolgreichen Änderungen, die einen vorherigen Text aufbewahrt haben. Gibt es keine, zeigt die Seite "No generations for this product yet.".

### 3.17 Schaltflächen "Generate with AI" neben Feldern

Auf der Produktbearbeitungsseite steht eine kleine Schaltfläche mit dem Mistral-Logo neben den Editoren für **Description**, **Short description**, **Meta title** und **Meta description**. Auf der Kategoriebearbeitungsseite steht sie neben **Description**, **Additional description**, **Meta title** und **Meta description**.

1. Klicken Sie auf die Schaltfläche. Hat der Shop mehr als eine Sprache, wählen Sie **Current language**, **All languages** oder **Cancel**.
2. Warten Sie. Die Schaltfläche zeigt einen Beschäftigt-Zustand, solange die Anfrage läuft.
3. Der Text erscheint im Feld. Klicken Sie im Produkt oder in der Kategorie auf **Save**, um ihn zu behalten. Vorher wird nichts gespeichert.

Der Datensatz muss bereits existieren. Bei einem neuen Produkt antwortet die Schaltfläche "Save the product once before generating." und bei einer neuen Kategorie "Save the category once before generating.". Fehler erscheinen in einem Meldungsfeld, zum Beispiel "Generation failed.".

Diese Schaltflächen verwenden immer das Standard-Briefing des Feldes, nicht Ihre Vorlagen. Hausregeln, Budget und Qualitätsprüfung aus Studio sowie das Modell aus Settings gelten weiterhin.

### 3.18 Weitere Verknüpfungen

| Ort | Was es bewirkt |
|---|---|
| Zauberstab-Symbol in der oberen Leiste | Öffnet ein kleines Feld: optional **Template**, ein Textfeld und **Generate**. Die Antwort wird im Feld angezeigt; kopieren Sie sie dorthin, wo Sie sie brauchen. Es wird nichts gespeichert, und Platzhalter werden nicht ersetzt. Blenden Sie das Symbol über **Admin Top Bar CTA** in Settings – General aus. |
| Produktliste | Eine Schaltfläche **My AI Mistral** neben den Sammelaktionen oder der Symbolleiste von **Catalog > Products** öffnet die Seite Generate. |
| PrestaShop Dashboard | Ein kleines Panel mit den Verknüpfungen **Mass content**, **Log** und **Cron** und dem Link zum Support von MyPresta.eu. |

## 4. Shop-Frontend

My AI Mistral hat keinen für Kunden sichtbaren Teil. Es fügt Ihren Shopseiten keine Blöcke, Seiten, Skripte oder Stile hinzu, und Kunden sehen nicht, dass das Modul existiert. Seine zwei Front-Adressen werden nur vom Back Office und von Ihrem Zeitplaner genutzt.

### 4.1 Adressen

| Adresse | Verwendet von | Was zu tun ist |
|---|---|---|
| /module/myaimistral/cron | Ihr Zeitplaner (Abschnitt 3.12) | Rufen Sie sie mit Geheimnis und Aktion auf, wie in Abschnitt 3.12 gezeigt. |
| /module/myaimistral/ajax | Die Schaltflächen im Back Office | Rufen Sie sie nicht von Hand auf und tragen Sie sie nicht in einen Zeitplaner ein. |

### 4.2 Was die Cron-Adresse antwortet

Die Adresse antwortet mit reinem Text. Ein Lauf stoppt beim ersten Fehler; bereits abgeschlossene Elemente bleiben gespeichert.

| Antwort | Bedeutung | Was zu tun ist |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** steht auf No. | Auf Yes stellen und speichern. |
| The token does not exist or it's wrong! | Das Geheimnis fehlt, ist falsch oder veraltet. | Kopieren Sie das aktuelle Geheimnis des Formulars. |
| Invalid action! | Der Teil `action` fehlt oder ist falsch geschrieben. | Fügen Sie `&action=generateProductContent` oder `&action=generateCategoryContent` hinzu. |
| updatedField parameter is wrong! | Das Feld gehört nicht zu den erlaubten. | Wählen Sie das Feld erneut und speichern Sie das Formular. |
| All must include all mandatory parameters! | Eine gespeicherte Einstellung ist leer. | Speichern Sie das Formular erneut, mit gewählter Sprache und Vorlage. |
| productTarget parameter is wrong! Allowed values: … | Der Zielwert ist unbekannt. | Wählen Sie **Selected Products** erneut. Dasselbe gilt für das Kategorieformular. |
| No valid product IDs provided. | **Product ID list** enthält Text, aber keine gültige Zahl. | Korrigieren oder leeren Sie die Liste. |
| No products to update. / No categories to update. | Nichts entspricht den Einstellungen. | Ändern Sie die Filter oder das Ziel, oder akzeptieren Sie, dass die Arbeit erledigt ist. |
| 5 products have been updated. / 5 categories have been updated. | Der Lauf ist beendet. Die Zahl ist die Anzahl. | Details finden Sie in History. |
| 5 pending products. | Debug ist an; nichts wurde gespeichert. | Stellen Sie **Enable Debug** auf No. |
| Error! followed by a text | Der Anbieter hat einen Fehler zurückgegeben. | Lesen Sie den Text, siehe Abschnitt 5.2. |
| Error! The model returned an empty response. | Mistral hat keinen Text gesendet. | Erhöhen Sie **Max Tokens** oder ändern Sie die Vorlage. |
| Error! Could not save product 12: … | PrestaShop hat den Text für dieses Produkt abgelehnt. | Lesen Sie den folgenden Grund; der Lauf wurde dort gestoppt. |

## 5. Probleme

### 5.1 Installation und Menü

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Das Installationsprogramm meldet, das Modul benötige PHP 7.0 oder neuer | Der Server verwendet ein älteres PHP. | Wechseln Sie die PHP-Version im Hosting-Panel und installieren Sie erneut. |
| "Could not create the module database tables." | Der Datenbankbenutzer darf keine Tabellen anlegen. | Geben Sie dem Benutzer dieses Recht oder fragen Sie Ihren Hoster. |
| Der Menüeintrag AI Content Generator fehlt | Alter Cache, das Modul ist deaktiviert oder das Profil des Mitarbeiters hat keine Berechtigung. | Leeren Sie den Cache, aktivieren Sie das Modul und prüfen Sie **Administration > Permissions** für das Profil. |
| Die Produktseite hat im Reiter Modules kein Panel My AI Mistral | **Product edit page Form** und **Product Edit History** stehen beide auf Disabled, oder die Seite ist im Cache. | Aktivieren Sie die Einstellung in Settings – General und laden Sie die Produktseite neu. |

### 5.2 Verbindung zu Mistral AI

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| "The Mistral API key is not set. Add it in the module settings." | Es ist kein Schlüssel gespeichert. | Fügen Sie den Schlüssel in Settings – Mistral ein. |
| "Mistral AI API KEY field is invalid!" | Weniger als 10 Zeichen und kein gespeicherter Schlüssel. | Kopieren Sie den vollständigen Schlüssel aus der Konsole. |
| "Mistral AI API Error (401): …" | Der Schlüssel ist falsch, widerrufen oder stammt von einem anderen Konto. | Erstellen Sie einen neuen Schlüssel und fügen Sie ihn erneut ein. |
| "Mistral AI API Error (429): …" | Ein Mistral-Limit wurde erreicht. | Warten Sie eine Minute und versuchen Sie es erneut, nutzen Sie kleinere Stapel oder erhöhen Sie Ihren Tarif. |
| "Mistral request timed out after N seconds…" | Das Modell ist langsam oder der Text ist lang. | Erhöhen Sie **API timeout (seconds)** in Settings – General oder nutzen Sie ein schnelleres Modell. |
| "The request timed out or the shop blocked it." | Der Server, eine Firewall oder das Shop-Frontend hat die Anfrage blockiert. | Erlauben Sie ausgehendes HTTPS zur Mistral-API und machen Sie die Frontadresse des Shops erreichbar. |
| Das Modell wird nicht gefunden | Ein Modellname, den Ihr Mistral-Konto nicht nutzen kann. | Wählen Sie ein anderes Modell aus der Liste. |
| Die Liste Model ist nach dem Entfernen eines Modells auf gpt-4o gesprungen | Das Modul fällt auf einen alten Standardnamen zurück. | Wählen Sie erneut ein Mistral-Modell und speichern Sie. |
| "Error! Invalid token!" | Das Geheimnis der geöffneten Back-Office-Seite stimmt nicht mehr mit dem im Shop überein, zum Beispiel nach einer Neuinstallation. | Laden Sie die Seite neu. |

### 5.3 Generierung

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| "Error! Content retrieve has failed! Details: …" | Die API hat einen Fehler zurückgegeben. Die Details nennen ihn. | Lesen Sie die Details und die Zeile in History. |
| "Monthly generation budget reached. Raise it in the studio settings or wait until next month." | Das Studio-Limit ist aufgebraucht. | Erhöhen Sie das Budget oder warten Sie auf den nächsten Monat. |
| "The reply was rejected because it contains a forbidden word from the studio settings." | Quality gate hat ein Wort aus Ihrer Liste gefunden. | Bearbeiten Sie die Liste oder den Prompt und führen Sie erneut aus. |
| "The model returned an empty response." oder "The model hit the token limit before returning any text…" | **Max Tokens** ist zu niedrig oder das Modell hat sie zum Nachdenken verbraucht. | Erhöhen Sie **Max Tokens**. |
| "The response was blocked by the provider content filter. Try rewording the prompt." | Mistral hat den Inhalt abgelehnt. | Formulieren Sie den Prompt um. |
| "Error! Prompt is missing or too short!" | Der Prompt hat weniger als 4 Zeichen. | Schreiben Sie eine längere Anweisung oder lassen Sie das Feld leer. |
| Ein Meta-Titel oder eine Meta-Beschreibung endet in einem Cron-Lauf abrupt | Der Cron kürzt Meta-Titel bei 69 und Meta-Beschreibungen bei 159 Zeichen. | Bitten Sie im Prompt um einen kürzeren Text. |
| Das Produkt zeigt nach der Generierung den alten Text | Das im Browser geöffnete Produktformular wurde darüber gespeichert. | Laden Sie die Produktseite neu, bevor Sie auf Save klicken. |
| Eine Zeile sagt "skipped" | Das Feld hatte Text und Sie haben Skip if filled gewählt. | Wählen Sie Replace, um zu überschreiben. |
| Für zwei Felder wird dasselbe Briefing verwendet | Das Feld Instruction enthält noch das vorherige Briefing. | Leeren Sie das Feld, bevor Sie ein anderes Feld drücken. |
| Name oder Additional description erhält in Generate – Categories einen beschreibungsähnlichen Text | Der leere Prompt verwendet für diese beiden Felder das Beschreibungs-Briefing. | Geben Sie einen eigenen Prompt ein. |
| "Error! This log entry has no previous value to restore." | Die Zeile hat keinen alten Text aufbewahrt, oder die Liste wurde geleert. | Der alte Text lässt sich vom Modul nicht wiederherstellen. |
| "Error! This PrestaShop version does not support the category Additional Description field." | Ältere PrestaShop-Version. | Überspringen Sie dieses Feld. |

### 5.4 Fotos und New product

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Der Reiter Photos sagt, die Suche sei aus | **AI Image Finder** steht auf Disabled. | Aktivieren Sie ihn in Settings – General oder Images und laden Sie die Produktseite neu. |
| "No photos were found on the suggested pages." | Die vorgeschlagenen Seiten haben keine brauchbaren Fotos. | Klicken Sie erneut auf **Find pages** oder fügen Sie die Fotos von Hand hinzu. |
| "The photos could not be added." | Der Server konnte sie nicht herunterladen. | Wählen Sie andere Fotos. |
| "Failed to parse AI response. Please try again." | Das Modell hat Daten zurückgegeben, die das Modul nicht lesen kann. | Klicken Sie erneut auf **Generate data** oder erhöhen Sie **Max Tokens**. |
| "Generate the product first." | **Create product** wurde vor **Generate data** angeklickt. | Generieren Sie zuerst. |
| "Prompt is required" | **What is the product?** ist leer. | Beschreiben Sie das Produkt. |

### 5.5 Cron

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Die Adresse antwortet, aber nichts ändert sich | **Enable Debug** steht auf Yes. | Stellen Sie es auf No und speichern Sie. |
| Die Adresse meldet, die Funktion sei deaktiviert | **Enable Cron Feature** steht auf No. | Stellen Sie es auf Yes. |
| Das Geheimnis hat sich von selbst geändert | Ein Geheimnis mit weniger als 24 Zeichen wurde ersetzt. | Kopieren Sie das neue Geheimnis aus dem Formular und aktualisieren Sie den Zeitplaner. |
| Dieselben Produkte werden jedes Mal neu geschrieben | **Product Categories** ist markiert (siehe Abschnitt 3.12). | Lassen Sie den Kategoriebaum leer und verwenden Sie **Product ID list**. |
| Der Cron verwendet die falsche Vorlage | Das Formular zeigte die neueste Vorlage an, und diese Auswahl wurde gespeichert. | Wählen Sie die richtige **Prompt Template** und speichern Sie. |
| "Generate Token" tut nichts | Das Skript der Schaltfläche wird in dieser Version nicht mitgeliefert. | Tippen Sie das neue Geheimnis selbst ein. |
| "Command:" im Formular zeigt kein Geheimnis | Es zeigt nur die schlichte Adresse. | Bauen Sie die Adresse wie in Abschnitt 3.12 zusammen. |
| Die Adresse endet in einem Timeout | Zu viele Elemente pro Aufruf. | Verringern Sie **Product to update**. |
| Nach einer Weile wird alles erneut verarbeitet | **Clear list** in History hat das Log entfernt, das abgeschlossene Elemente markiert. | Leeren Sie History nicht, während ein Cron läuft, oder verwenden Sie **Product ID list**. |

### 5.6 Texte, die OpenAI oder ChatGPT erwähnen

Das Modul wurde aus einem früheren Modul für einen anderen KI-Anbieter entwickelt. Einige Texte zeigen noch den alten Namen. Sie ändern nichts an der Funktionsweise des Moduls.

| Wo | Was Sie sehen | Bedeutung |
|---|---|---|
| Settings – Mistral | Das Modellnamen-Beispiel im Hinzufügen-Feld ist ein GPT-Name; die Meldungen "OpenAi Settings Updated" und "OpenAi Model field is invalid!". | Nur Beispiele und Formulierungen. Geben Sie einen Mistral-Modellnamen ein. |
| Generate – Products | "OpenAi content" in **Update only**. | Gemeint sind Inhalte dieses Moduls. |
| Generate pages | Schaltfläche **Module settings**. | Eine alte Verknüpfung, die dieses Modul nicht öffnet. Nutzen Sie die Menüleiste. |
| History | Der Anbieter zeigt "openai". | Nur eine Bezeichnung. |

## 6. Für Entwickler

### 6.1 Überblick

| Punkt | Wert |
|---|---|
| Modulname | `myaimistral` |
| Anzeigename | My AI Mistral - AI content generation |
| Version | 1.0.0 |
| Hauptklasse | `myaimistral` (`myaimistral.php`) |
| PrestaShop | 1.6 bis 9.99.99 |
| PHP | 7.0.0 oder neuer (bei der Installation geprüft, Konstante `MIN_PHP_VERSION`) |
| API-Basis | `https://api.mistral.ai/v1` (`/chat/completions`, `/models`) |
| Konfigurationspräfix | `MYPRESTA_MYAIMISTRAL_` |
| Tabellen | `PREFIX_myaimistral_prompt`, `PREFIX_myaimistral_log` |
| CSS-Präfix | `.mam-` |
| URL-Parameter | `mam_tab`, `mam_sub`, `mcg_preset`, `mam_from`, `mam_to` und `stats_*` bei History |

Ordner: `controllers/admin`, `controllers/front`, `src` (automatisch geladene Klassen `OpenAIService` und `Studio` im Namespace `MyAIMistral`), `lib` (Update-Prüfung, Abschnittshilfe, PrestaShop-9-Kompatibilität), `views/templates`, `views/js`, `views/css`, `translations`.

Das Modul hat keine Overrides und keine Front-Templates. Die Feldhilfe wird mit dem Helper `fieldHelp($does,$how,$effect)` geschrieben, der den Text "What it does / How to configure / Effect" jedes HelperForm-`desc` aufbaut.

### 6.2 Admin-Controller, Hooks und Routing

| Controller-Klasse | Tab-Name | Zweck |
|---|---|---|
| `AdminMyAIMistralMain` | AI Content Generator (menu entry) | Leitet auf `AdminModules&configure=myaimistral` um. |
| `AdminMyAIMistral` | Mass Content Creator | Generate-Seiten (Produkte und Kategorien). |
| `AdminMyAIMistralProductCreator` | AI Product Creator | New product. |
| `AdminMyAIMistralSettings` | Module Settings | Einstieg in die Einstellungen. |
| `AdminMyAIMistralCron` | Cron Job Settings | Cron-Formulare. |
| `AdminMyAIMistralUsage` | Module Log and Usage | History. |
| `AdminMyAIMistralImageFinder` | AI Image Finder | Seite Images und die Foto-Aktionen `searchImages`, `extractImages`, `saveImages`. |

Admin-Controller leiten auf `AdminHome` um, wenn das Modul inaktiv ist.

Bei der Installation registrierte Hooks: `displayBackOfficeHeader` (Assets und `Media::addJsDef`-Werte wie `myaimistralField`, `myaimistralAdminLink`, `mamHelpLabels`), `displayBackOfficeTop` (Symbol der oberen Leiste und Dropdown), `displayAdminProductsExtra` und `actionProductFormBuilderModifier` (Produktreiter), `actionProductGridDataModifier` (Produktliste), `dashboardZoneTwo` (PrestaShop-Dashboard-Panel), `displayAdminProductsMainStepLeftColumnMiddle` und `displayAdminProductsMainStepLeftColumnBottom` (leer), `displayHeader` und `displayFooter` (leer).

Die Navigation innerhalb der Modulseite verwendet URL-Parameter:

| Parameter | Werte | Bedeutung |
|---|---|---|
| `mam_tab` | dashboard, settings, updates (Modulseite); die anderen Reiter sind Controller | Der Hauptreiter auf der Konfigurationsseite des Moduls. |
| `mam_sub` | general, openai, studio, templates, playground (settings); products, categories (Generate) | Der Unterreiter. `openai` ist der Mistral-Reiter. |
| `mcg_preset` | today, 7, 30, 90, month, all | Zeitraum-Voreinstellung des Dashboards. |
| `mam_from`, `mam_to` | `YYYY-MM-DD` | Eigener Zeitraum des Dashboards. |
| `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` | siehe History | History-Filter. `clear_log` löscht das Log. |

### 6.3 Cron-Vertrag

```text
GET /module/myaimistral/cron?secret=SECRET&action=generateProductContent
GET /module/myaimistral/cron?secret=SECRET&action=generateCategoryContent
```

| Regel | Verhalten |
|---|---|
| Schalter | `MYPRESTA_MYAIMISTRAL_ENABLE_CRON` darf nicht 0 sein. |
| Authentifizierung | `secret` muss `SECRET` oder `CAT_SECRET` entsprechen. Beide funktionieren für beide Aktionen. |
| Optionale Überschreibungen (Produkte) | `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`. Sie ersetzen die gespeicherten Werte nur für diesen einen Aufruf. |
| Optionale Überschreibungen (Kategorien) | `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. |
| Erlaubte Felder | Produkte: name, description, description_short, meta_title, meta_description, tags. Kategorien: name, description, meta_title, meta_description, additional_description. |
| Ziele | `pendingMistral`: keine erfolgreiche Log-Zeile für das Element. `pendingField`: keine erfolgreiche Log-Zeile vom Typ `product_FIELD` bzw. `category_FIELD`. `emptyField`: das Feld ist in der Sprache leer. Zeilen mit dem Status `error` zählen nicht. |
| Reihenfolge und Limit | `ORDER BY id ASC LIMIT n`. Kategorieabfragen beginnen nach `PS_HOME_CATEGORY`. |
| Debug | Bei `debug` gleich 1 werden das SQL, die ausgewählten Elemente und die finalen Prompts ausgegeben, und es wird nichts gespeichert. Ein gespeicherter Debug-Wert 1 stoppt auch das zeitgesteuerte Speichern. |
| Kürzung | name 128, Kurzbeschreibung 799, Meta-Titel 69, Meta-Beschreibung 159. Tags laufen über `Tag::addTags`. |
| Geheimnisse | `ensureLongSecrets()` ersetzt Geheimnisse mit weniger als 24 Zeichen. |
| Log | Jedes gespeicherte Element schreibt eine Zeile mit `method` `cron` sowie dem alten und neuen Wert. |

Der Kategoriefilter des Produkt-Crons wird als `... AND p.id_product IN (...) OR p.id_category_default IN (...)` ohne Klammern aufgebaut, sodass Produkte mit einer markierten Standardkategorie die übrigen Bedingungen umgehen. Der Filter in Generate – Products verwendet Klammern und ist nicht betroffen.

### 6.4 AJAX-Controller

`/module/myaimistral/ajax` ist ein Front-Modul-Controller. Jeder Aufruf trägt `secret_token` (den Wert `TOKEN`) und antwortet mit JSON `{status, msg, date}`.

| Aktion | Zweck |
|---|---|
| `initiatePrompt` | Playground und obere Leiste. Kann `id_category`, `id_cms` oder `id_manufacturer` mitführen, um `{category_*}`, `{cms_title}`, `{brand_name}`, `{brand_description}`, `{brand_short_description}` zu ersetzen. |
| `updateProduct` | Ein Produktfeld generieren. Verhalten: `replace`, `keep`, `keep_top`, `keep_end`, `single_product` (kein Speichern). `keep` antwortet mit dem Status `skipped`. |
| `updateCategory` | Dasselbe für Kategorien (`single_category` speichert nichts). |
| `generateSeoPack` | Schreibt Name, Beschreibungen und Meta-Felder in einer Anfrage. |
| `generateAltTexts` | Schreibt Alt-Texte für Bilder. Keine Schaltfläche in der Oberfläche. |
| `initiateProductRestore` | Stellt einen vorherigen Wert aus einer Log-Zeile wieder her. |
| `updateSettings` | Speichert Max Tokens, Temperature, Top P und die Penalties. |

Das Token wird in Back-Office-Seiten ausgegeben, und der Controller prüft keine Mitarbeitersitzung. Behandeln Sie das Token als Geheimnis.

`Studio::gate()` wendet Hausregeln, das monatliche Budget (zählt Zeilen, die keine Fehler sind) und die Prüfung auf verbotene Wörter an. `OpenAIService` ruft Mistral per cURL auf, hält das Timeout zwischen 10 und 600 Sekunden, wiederholt bis zu sechsmal ohne die von der API abgelehnten Parameter (gemerkt in `MODEL_CAPS`) und lockert die SSL-Prüfung nur auf localhost. Der Ajax-Controller verlängert das PHP-`max_execution_time` passend zum Timeout.

### 6.5 Konfigurationsschlüssel

Alle Schlüssel beginnen mit `MYPRESTA_MYAIMISTRAL_`.

| Schlüssel-Suffix | Standard | Zweck |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TOPCTA` | 1 | Admin Top Bar CTA. |
| `PRODUCT` | 1 | Product edit page Form. |
| `PRODUCT_LOG` | 1 | Product Edit History. |
| `TOKEN` | zufällig | AJAX-Geheimnis. |
| `SECRET` | zufällig | Geheimnis des Produkt-Crons. |
| `CAT_SECRET` | zufällig | Geheimnis des Kategorie-Crons. |
| `API_KEY` | einzelnes Leerzeichen | Mistral-Schlüssel. |
| `MODEL` | mistral-small-latest | Aktives Modell. |
| `EXTRA_MODELS` | leer | Vom Händler hinzugefügte Modelle, eines pro Zeile. |
| `MODEL_CAPS` | leer | Pro Modell abgelehnte Parameter. |
| `TEMPERATURE` | 0.7 | Sampling-Temperatur. |
| `MAX_TOKENS` | 3200 | Antwortlimit. |
| `TOP_P` | 1 | Top P. |
| `FREQ_PEN`, `PRES_PEN` | 0 | Penalties. |
| `TIMEOUT` | 120 | Sekunden, 10 bis 600. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | leer | Studio-Texte. |
| `BUDGET` | 0 | Monatliches Anfragelimit. |
| `QUALITY` | 1 | Prüfung auf verbotene Wörter. |
| `IMAGEFINDER_ENABLE` | 1 | Schalter der Fotosuche. |
| `IMAGEFINDER_PROMPT` | eingebauter Text | Anweisung der Fotosuche. |
| `ENABLE_CRON` | 0 | Cron-Schalter. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Erinnerung an das Intervall (6 ist Every Hour). |
| `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `productIdsList`, `categories` | description, pendingMistral, 5, Standardsprache des Shops, leer, 0, leer, leer | Produkt-Cron-Formular. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catlanguageId`, `catpromptTemplateId`, `catdebug` | description, pendingMistral, 5, Standardsprache des Shops, leer, 0 | Kategorie-Cron-Formular. |

Die Filter der Seite Generate verwenden dasselbe Präfix: `CATEGORIES`, `BRANDS`, `STATUS`, `STOCK`, `HISTORY`, `PROD_IDS`, `PROD_REF`, `PROD_DATE_FROM`, `PROD_DATE_TO`, `PROD_MIN_ID`, `PROD_MAX_ID`, `PROD_LIMIT`, `CATEGORIESC`, dazu `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY` und `EXISTING` des alten Kategorieformulars. Sie werden bei jeder Anfrage des Generate-Controllers geschrieben und bei der Deinstallation nicht entfernt. Der Wert von Product IDs wird mit entfernten Leerzeichen so in die Abfrage eingefügt, wie er eingegeben wurde. Lassen Sie diese Seite daher nur vertrauenswürdigen Mitarbeitern zugänglich.

### 6.6 Datenbank

| Tabelle | Spalten | Hinweise |
|---|---|---|
| `myaimistral_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated` | 16 Zeilen bei der Installation. |
| `myaimistral_log` | `id_log`, `type`, `method`, `status`, `ai_service`, `model`, `prompt`, `reply`, `error_message`, `http_code`, `duration_ms`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `old_*`- und `new_*`-Feldwerte, `prompt_tokens`, `completion_tokens`, `total_tokens`, `date_updated` | Token-Spalten werden bei Bedarf von `ensureUsageColumns()` hinzugefügt. Beide Tabellen werden bei der Deinstallation gelöscht. |

Werte von `type` sind zum Beispiel `general`, `singleCategory`, `singleCMS`, `singleBrand`, `product_name`, `product_description`, `product_description_short`, `product_meta_title`, `product_meta_description`, `product_tags`, `category_description` und `error`. Werte von `method` sind `initiatePrompt`, `updateProduct`, `updateCategory` und `cron`.

### 6.7 Frontend-Bausteine

| Punkt | Hinweise |
|---|---|
| Klassen | Admin-Stile beginnen mit `.mam-` (Navigation, Dashboard, Karten, Chips, Kacheln, Hilfe-Schublade). Das Produktpanel verwendet `.myaimistral-ui`, und die Feldschaltflächen verwenden `.myaimistral-field-btn`. |
| `views/js/back.js` | Playground, Schaltflächen des Produktpanels, Massen-Runner, New product, Restore, Reiter, Dropdown der oberen Leiste. Data-Attribute des Produktpanels: `data-myaimistral`, `data-myaimistral-product`, `data-mam-fill`, `data-mam-for`. |
| `views/js/product-fields.js` | Die Feldschaltflächen auf Produkt- und Kategorieseiten. Liest `window.myaimistralField`. |
| `views/js/image-finder.js` | Fotosuche und Import. |
| `views/js/admin-products-bulk.js` | Die Schaltfläche in der Produktliste. Liest `myaimistralAdminLink`. |
| Stile | `back.css`, `admin-nav.css`, `stats.css`. |

### 6.8 Erweitern

- Neue Prompt-Vorlagen: Fügen Sie eine Zeile mit `status` 1 in `myaimistral_prompt` ein.
- Neue Platzhalter: Erweitern Sie die Prompt-Builder für Produkte und Kategorien in `controllers/front/ajax.php` und in `controllers/front/cron.php`. Shop-Platzhalter werden in `applyShopShortcodes()` behandelt.
- Neue Modelle: Fügen Sie sie in Settings – Mistral hinzu oder hängen Sie den Namen an die eingebaute Liste in `myaimistral.php` an.
- Anderer Anbieter: Ändern Sie die Basis-URL und den Anfragetext in `src/OpenAIService.php`. Alles andere spricht nur mit dieser Klasse.
- Übersetzungen: Verwenden Sie `$this->l()` im Modul und `trans()` in Controllern unter PrestaShop 8 und 9. Die Texte liegen in `translations/`.

## 7. Hilfe

Produktseite: https://mypresta.eu/modules/administration-tools/my-ai-mistral.html

Für Hilfe zum Modul melden Sie sich bei mypresta.eu an, öffnen Sie **contact** und wählen Sie **Support for paid modules**. Beschreiben Sie das Problem, Ihre PrestaShop- und PHP-Versionen und den Text der Meldung, die Sie sehen. Senden Sie niemals den API-Schlüssel oder ein Cron-Geheimnis.
