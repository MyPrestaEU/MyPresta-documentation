---
title: "My AI Grok - AI content generation - Dokumentation und Benutzerhandbuch"
description: "Ein Leitfaden für Händler, die das Modul bereits besitzen: Grok-Konto (xAI) verbinden, Katalogtexte im Backoffice erzeugen und Probleme beheben, wenn etwas nicht funktioniert."
sidebar:
  label: "My AI Grok - AI content generation - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul SEO meta and catalog descriptions with Grok AI auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai/)
>
> ---


## 1. Voraussetzungen

Dieses Kapitel listet auf, was Ihr Shop und Ihr Server benötigen, bevor das Modul Texte für Sie schreiben kann.

- **PrestaShop:** Versionen 1.6 bis 9.x.
- **PHP:** Version 7.0 oder neuer. Bei einem älteren PHP wird die Installation mit einer Meldung abgelehnt.
- **PHP-Erweiterungen:** cURL. Das Modul kommuniziert über cURL mit Grok.
- **Ausgehende Verbindung:** Der Server muss sichere (HTTPS) Verbindungen zu `https://api.x.ai/v1` öffnen dürfen. Blockiert eine Firewall diese, schlägt jede Generierung fehl.
- **Andere Module:** keine. Das Modul arbeitet eigenständig.
- **Ein xAI-Konto:** Sie benötigen ein eigenes Konto auf https://console.x.ai, um einen Grok-API-Schlüssel zu erhalten. Anfragen an Grok werden von xAI Ihrem Konto in Rechnung gestellt, nicht vom Modul.
- **Große Kataloge:** Das Modul schreibt pro Anfrage ein Feld eines Produkts. Ein langer Massenlauf dauert daher so lange wie alle Anfragen zusammen. Nutzen Sie die Stapelgrenzen auf den Bildschirmen Generate und Cron und halten Sie das API-Timeout für langsame Modelle hoch genug (siehe Abschnitt 3.4).

## 2. Installation

### 2.1 Hochladen, installieren und aktivieren

1. Öffnen Sie im Backoffice **Modules**, dann **Module Manager**.
2. Laden Sie die ZIP-Datei des Moduls hoch oder suchen Sie es in der Liste, falls es bereits auf dem Server liegt.
3. Klicken Sie auf **Install**. Die Installation prüft die PHP-Version, legt die Daten des Moduls an und aktiviert das Modul anschließend.
4. Bricht die Installation mit einer Meldung ab, lesen Sie Abschnitt 5.1.

### 2.2 Was im Menü erscheint

- Unter **Modules** erscheint ein neuer Eintrag **AI Content Generator**. Ein Klick darauf öffnet den Bildschirm **Dashboard** des Moduls.
- Alle weiteren Bildschirme des Moduls (Settings, Generate, New product, Cron, History, Images, Updates) erreichen Sie über die Navigationsleiste oben im Modul, nicht über das linke Menü.
- Auf der Produktbearbeitungsseite erscheint im Reiter **Modules** ein Block **My AI Grok**, und neben den Textfeldern erscheinen kleine Schaltflächen **Generate with AI** (siehe Abschnitt 3.16).
- In der oberen Leiste jeder Backoffice-Seite kann eine Zauberstab-Verknüpfung erscheinen (siehe **Admin Top Bar CTA** in Abschnitt 3.4).

Die Einstellungen erreichen Sie auch über **Modules**, **Module Manager**, Modulname, **Configure**.

### 2.3 Cache

Die Installation leert den PrestaShop-Cache nicht. Erscheint der Menüeintrag oder der Produktblock nicht sofort nach der Installation, leeren Sie den Cache selbst unter **Advanced Parameters**, **Performance** und laden Sie die Seite neu.

### 2.4 Deinstallation und Neuinstallation

- **Was verschwindet:** der Menüeintrag **AI Content Generator** samt seinen versteckten Bildschirmen, die 16 vorgefertigten Prompt-Vorlagen zusammen mit allen von Ihnen hinzugefügten Vorlagen, die gesamte History (jeder gespeicherte Prompt, jede Antwort und jede Token-Zahl) sowie die gespeicherten Einstellungen des Moduls (API-Schlüssel, Modell, Studio-Regeln, Cron-Auswahl, Secrets).
- **Was bleibt:** alle bereits in Produkte und Kategorien geschriebenen Texte. Das Modul entfernt erzeugte Texte nie.
- **Reste:** einige gemerkte Auswahlen der Generate-Bildschirme (Filter wie die zuletzt gewählte Sprache oder der Status) können im Shop gespeichert bleiben. Sie haben keine Wirkung.
- **Neuinstallation:** Eine neue Installation beginnt mit den in Kapitel 3 genannten Standardwerten. Ihr API-Schlüssel, die Studio-Regeln, eigene Vorlagen und die History werden nicht wiederhergestellt – notieren oder exportieren Sie vorher, was Sie brauchen.

## 3. Konfiguration und Arbeit im Backoffice

Dies ist das Hauptkapitel. Es beginnt mit dem gesamten Arbeitsablauf und beschreibt dann jeden Bildschirm in der Reihenfolge der Navigationsleiste.

Die Screenshots stammen aus einem englischen Backoffice. Namen von Schaltflächen, Feldern und Meldungen stehen in diesem Kapitel fett, so wie sie in der englischen Oberfläche erscheinen; die Erklärungen sind auf Deutsch.

### 3.1 Der gesamte Ablauf, Schritt für Schritt

1. **Grok verbinden.** Öffnen Sie **Settings**, dann **Grok**. Fügen Sie Ihren API-Schlüssel von https://console.x.ai ein und wählen Sie ein Modell. Speichern.
2. **Hausstil festlegen (optional).** Öffnen Sie **Settings**, dann **Studio**. Füllen Sie Stimme, Zielgruppe, Tonalität, ein Glossar zu erhaltender Namen, verbotene Wörter, ein Monatsbudget und das Quality gate aus. Lassen Sie leer, was Sie nicht brauchen.
3. **Sicher testen.** Nutzen Sie **Settings**, dann **Playground**, um eine freie Anweisung zu senden und die Antwort zu lesen. Auf einer Produktseite verwenden Sie den Reiter **Simulate** und **Try**. An diesen beiden Stellen wird nichts im Katalog gespeichert.
4. **Ein Produkt füllen.** Öffnen Sie das Produkt, gehen Sie zum Reiter **Modules**, **My AI Grok**, **Generate**, wählen Sie die Sprache und drücken Sie neben dem Feld auf **Fill**. Oder nutzen Sie die Schaltflächen **Generate with AI** neben den eigenen Feldern des Produkts und speichern Sie das Produkt anschließend.
5. **Viele Produkte füllen.** Öffnen Sie **Generate**, **Products**. Filtern Sie die Liste, drücken Sie **Go to next step**, wählen Sie eine Vorlage oder schreiben Sie eine Anweisung, legen Sie fest, was erzeugt wird, wie vorhandener Text behandelt wird und für welche Sprachen, und drücken Sie dann **Run on the list below**. Dasselbe tun Sie für Kategorien unter **Generate**, **Categories**.
6. **Unbeaufsichtigte Stapel.** Öffnen Sie **Cron**, speichern Sie Ihre Auswahl und kopieren Sie die Adresse in den Scheduler Ihres Servers (siehe Abschnitte 3.12 und 4.2).
7. **Prüfen und rückgängig machen.** **History** zeigt jeden Aufruf mit Prompt, Antwort, Status und Tokens. Im Produkt können Sie im Reiter **History** mit **Restore** einen früheren Text zurückholen.

Erzeugter Text wird direkt in den Katalog geschrieben, sobald jeweils die Antwort eintrifft. Testen Sie vor einem ersten großen Lauf an einigen Produkten mit **Simulate** oder den Filtern **Product IDs** und **Product Limit**.

### 3.2 Navigation und das Help-Panel

![Dashboard with the navigation bar and date presets](https://mypresta.eu/docs/images/docs/myaigrok-dashboard.webp)

*Dashboard: Die Navigationsleiste befindet sich oben auf jedem Bildschirm des Moduls.*

Die Leiste zeigt den Modulnamen mit der Version und diese Einträge in dieser Reihenfolge:

| Eintrag | Was Sie dort finden |
|---|---|
| **Dashboard** | Diagramme zu Anfragen, Tokens und Fehlern. |
| **Settings** | Fünf Unterreiter: **General**, **Grok**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Zwei Unterreiter: **Products** und **Categories** für Massenläufe. |
| **New product** | Legt aus einem kurzen Briefing ein neues Produkt an. |
| **Cron** | Erstellt Adressen, die der Server nach Zeitplan aufrufen kann. |
| **History** | Die vollständige Liste der Aufrufe mit Filtern. |
| **Images** | Schalter und Anweisung für die Produktbildsuche. |
| **Updates** | Prüft, ob eine neuere Version des Moduls veröffentlicht ist. |

Fahren Sie mit der Maus über einen Eintrag, um eine kurze Erklärung zu lesen. Eine runde Schaltfläche **Help** am Bildschirmrand öffnet ein Seitenpanel mit Hilfe zur aktuellen Seite. Schließen Sie es mit dem Kreuz.

Jedes Feld im Modul wird auf dem Bildschirm in drei Teilen erklärt: **What it does**, **How to configure** und **Effect**. Die Tabellen unten geben diese Texte in einfachen Worten wieder und ergänzen den Wert, den das Feld direkt nach der Installation hat.

### 3.3 Dashboard

Öffnen Sie **AI Content Generator** unter **Modules** oder den Eintrag **Dashboard** der Leiste.

- **Datumsvorgaben:** **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**. Die Seite öffnet mit **30 days**.
- **From** und **To:** Wählen Sie eigene Daten und drücken Sie **Apply**. Liegt From nach To, werden die Daten vertauscht.
- **Active service:** zeigt Grok und das in Settings gewählte Modell.
- **Karten:** **Requests** (jeder gespeicherte Aufruf), **Success**, **Errors**, **Tokens sent** (Größe der Prompts) und **Tokens received** (Größe der Antworten).
- **Diagramme:** **Requests and errors**, **Tokens sent and received** und **Requests by model**. Bei Zeiträumen von mehr als etwa vier Monaten werden die Tage wochenweise zusammengefasst.

| Bedienelement | Bei Installation | Was es bewirkt |
|---|---|---|
| **Presets** | 30 days | Zählt die in der History gespeicherten Grok-Generierungen innerhalb der gewählten Daten. API-Schlüssel und Modell werden nicht hier, sondern in Settings gewählt. |
| **From / To / Apply** | letzte 30 Tage | Zeichnet nur diesen Ausschnitt. Von dieser Seite aus wird im Katalog nichts erzeugt oder geändert, und die History wird nicht gelöscht. |

### 3.4 Settings – General

Öffnen Sie **Settings**, dann **General**.

![Settings, General tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-general.webp)

*Settings – General: shopweite Schalter und das API-Timeout.*

Diese Schalter bestimmen, was Mitarbeiter im Backoffice sehen. Das Speichern ändert für sich genommen keine Produkttexte. Drücken Sie **Save**; die Bestätigung lautet **Settings Updated**.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Live mode** | Deaktiviert | Kennzeichnet das Modul als im echten Shop laufend statt in einer Testumgebung. Aktivieren Sie es im Produktivshop. Lassen Sie es auf einer Staging-Kopie deaktiviert, wenn Mitarbeiter die Werkzeuge nicht als einsatzbereit ansehen sollen. Deaktiviert behält dieselben Werkzeuge, signalisiert aber, dass es nicht die Produktivumgebung ist. |
| **Debug mode** | Deaktiviert | Schreibt zusätzliche Diagnosedetails, wenn ein Aufruf an Grok fehlschlägt. Schalten Sie es nur ein, während Sie einen Fehler untersuchen, und danach wieder aus. Aktiviert fügt dem PrestaShop-Log technische Meldungen hinzu (**Advanced Parameters**, **Logs**). Deaktiviert beschränkt das Log auf die normale Generierungs-History. Kunden sehen dies nie. |
| **API timeout (seconds)** | 120 | Wie viele Sekunden ein Aufruf an Grok laufen darf, bevor das Modul aufgibt. Verwenden Sie 120 für normale Beschreibungen. Erhöhen Sie in Richtung 600 für lange SEO-Pakete oder langsame Modelle. Gehen Sie nicht unter 10. Werte unter 10 werden als 10 gespeichert, Werte über 600 als 600; ein leerer oder nicht numerischer Wert wird als 120 gespeichert. Ein kurzes Timeout schlägt schnell fehl und protokolliert einen Fehler. Ein langes Timeout wartet auf ein langsames Modell, statt eine gute Antwort abzubrechen. |
| **Product Edit History** | Aktiviert | Zeigt auf der Produktseite frühere KI-Schreibvorgänge an, damit ein alter Wert zurückgesetzt werden kann. Aktivieren Sie es, wenn Redakteure eine Generierung rückgängig machen können sollen. Aktiviert fügt dem Modulblock des Produkts einen Reiter **History** mit **Restore** hinzu. Deaktiviert blendet ihn aus. Frühere Zeilen bleiben in beiden Fällen in der History. |
| **Admin Top Bar CTA** | Aktiviert | Legt in die obere Leiste des Backoffice eine Verknüpfung, die den Generator öffnet. Aktivieren Sie sie in Shops, in denen das Team oft Texte erzeugt. Deaktivieren Sie sie, wenn die Leiste bereits überfüllt ist. Aktiviert zeigt die Schaltfläche auf jeder Backoffice-Seite. Deaktiviert entfernt nur diese Schaltfläche. Das Modulmenü bleibt. |
| **Product edit page Form** | Aktiviert | Zeigt das Generator-Panel auf der Produktbearbeitungsseite: die Reiter **Generate**, **Simulate** und **Photos** des Blocks **My AI Grok**. Aktivieren Sie es für Katalogredakteure. Deaktivieren Sie es, wenn nur Massengenerierung und Cron genutzt werden sollen. |
| **AI Image Finder** | Aktiviert | Lässt einen Redakteur das Modell nach Seiten fragen, die wahrscheinlich Fotos des aktuellen Produkts enthalten. Aktivieren Sie es, wenn Sie diese Schaltfläche auf der Produktseite wünschen. Sie wählen weiterhin selbst, welche Bilder importiert werden. Deaktiviert blendet den Inhalt des Reiters **Photos** aus. Es wird nichts heruntergeladen, bis jemand ein Bild bestätigt. |
| **AI Image Search Prompt** | Verlangt genau 5 Seitenadressen | Die Anweisung, die bei der Suche nach Produktbildern gesendet wird. `{product_name}` und `{product_description}` werden durch das aktuelle Produkt ersetzt. Behalten Sie die Aufforderung nach einer Liste von Seitenadressen bei. Ändern Sie den Wortlaut, wenn Sie Herstellerseiten oder eine andere Anzahl wünschen. Ein präziserer Prompt liefert relevantere Seiten. Ein vager Prompt liefert unpassende Links. Es wird nichts gespeichert, bis Sie Bilder auswählen. |

Derselbe Schalter **AI Image Finder** und derselbe Prompt existieren auch auf dem Bildschirm **Images** (Abschnitt 3.14); beide Stellen ändern dieselbe Einstellung.

### 3.5 Settings – Grok

Öffnen Sie **Settings**, dann **Grok**.

![Settings, Grok tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-grok.webp)

*Settings – Grok: API-Schlüssel, Modell und die Sampling-Werte.*

Dieses Formular enthält das Grok-Konto, das für jede Generierung genutzt wird, auch für Cron und die Produktschaltflächen. Sampling-Felder verändern, wie abwechslungsreich der Wortlaut ist. Sie ändern nicht, welche Produkte aktualisiert werden.

Meldungen, die Sie nach **Save** sehen können: **OpenAi Settings Updated** (Erfolg; die Bezeichnung ist ein Überbleibsel, der Bildschirm gehört aber zu Grok), **Grok API KEY field is invalid!** (kein Schlüssel gespeichert und der eingefügte ist kürzer als 10 Zeichen) und **OpenAi Model field is invalid!** (der Modellname ist zu kurz). Ein Schlüssel mit Leerzeichen am Rand wird automatisch bereinigt, und Sie sehen möglicherweise **Grok API Key has been automatically cleaned (whitespace removed).**

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Grok API KEY** | leer | Das Geheimnis, mit dem dieser Shop Ihr Grok-Konto aufrufen darf. Fügen Sie den Schlüssel von https://console.x.ai ein. Leerzeichen werden beim Speichern entfernt. Lassen Sie das Feld unverändert, um den bereits gespeicherten Schlüssel zu behalten. Ein gültiger Schlüssel erlaubt Grok-Generierungen. Ein leerer oder falscher Schlüssel lässt diese Aufrufe fehlschlagen, und der Fehler wird in der History protokolliert. |
| **Model** | grok-4.7 | Das Grok-Modell, das den Text schreibt. Die eingebauten Namen sind grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning und grok-4.20-0309-reasoning. Sie bleiben in der Liste. Namen, die Sie in der nächsten Zeile hinzufügen, können entfernt werden. Die nächste Generierung verwendet dieses Modell. Ein Modell, auf das Ihr Schlüssel keinen Zugriff hat, liefert einen Fehler statt Text. |
| **Add a Grok model** | keine zusätzlichen Modelle | Fügt eine Grok-Modell-ID hinzu, die nicht in der eingebauten Liste steht, damit Sie sie oben auswählen können. Geben Sie die exakte ID aus Ihrem Grok-Konto ein (zum Beispiel grok-4.6) und klicken Sie auf **Add model**. Die neue ID erscheint in der Liste **Model** und wird zum aktiven Modell. **Remove** neben einer hinzugefügten ID löscht nur hier hinzugefügte IDs. Eingebaute IDs können nicht gelöscht werden. Entfernen Sie das aktive Modell, wird grok-4.7 aktiv. Meldungen: **Model added.**, **Model removed.**, **That model is already built in.**, **Built-in models cannot be removed.**, **Enter a model id such as grok-4.6.** |
| **Max Tokens** | 3200 | Obergrenze für die Länge der Antwort, gezählt in Tokens statt in Wörtern. Verwenden Sie etwa 256 für eine Meta-Beschreibung und 1000 oder mehr für eine vollständige HTML-Beschreibung. Ein niedriges Limit schneidet die Antwort ab. Ein hohes Limit erlaubt längeren Text und verursacht höhere Kosten auf der Rechnung des Anbieters. Es ändert den Prompt nicht. |
| **Temperature** | 0.7 | Wie frei das Modell Wörter wählt. Niedriger ist gleichmäßiger, höher ist abwechslungsreicher. Bleiben Sie zwischen 0 und 1. Verwenden Sie etwa 0,2 für technische Daten und Meta-Texte, etwa 0,7 für Beschreibungen. Ändern Sie entweder diesen Wert oder **Top P**, nicht beide. Ein niedriger Wert wiederholt eine ähnliche Struktur. Ein hoher Wert erzeugt mehr unterschiedliche Formulierungen und ein höheres Risiko, vom Briefing abzuweichen. |
| **Top P** | 1 | Eine andere Möglichkeit, zu begrenzen, wie überraschend das nächste Wort sein darf. 1 berücksichtigt den vollen Bereich. Lassen Sie 1, wenn Sie bereits **Temperature** gesetzt haben. Verwenden Sie einen niedrigeren Wert, etwa 0,9, nur, wenn Sie ein engeres Vokabular wünschen. Niedrigere Werte machen Antworten sicherer und repetitiver. |
| **Frequency Penalty Value** | 0 | Verringert Zeilen, die dieselbe Phrase innerhalb einer Antwort wiederholen. Verwenden Sie 0, außer Beschreibungen kopieren ständig denselben Satz. Probieren Sie 0,3 bis 0,6. Bleiben Sie zwischen -2 und 2. Ein positiver Wert macht wiederholten Wortlaut unwahrscheinlicher. Andere Produkte werden dabei nicht berücksichtigt. |
| **Presence Penalty Value** | 0 | Drängt die Antwort zu neuen Themen, statt bei bereits verwendeten Wörtern zu bleiben. Standardmäßig 0. Probieren Sie eine kleine positive Zahl, wenn jeder Absatz denselben Punkt behandelt. Bleiben Sie zwischen -2 und 2. Einige neuere Modelle ignorieren dieses Feld. |

Das Modul merkt sich selbstständig, welche dieser Werte ein Modell ablehnt, und sendet sie nicht mehr an dieses Modell, sodass Sie deswegen keinen Fehler sehen.

### 3.6 Settings – Studio

Öffnen Sie **Settings**, dann **Studio**.

![Settings, Studio tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-studio.webp)

*Settings – Studio: Hausregeln, die jedem Prompt hinzugefügt werden.*

Studio wird auf jeden Prompt angewendet, auch auf die Produktschaltflächen, die Massengenerierung und Cron. Leere Felder werden übersprungen. Ein Budget von 0 bedeutet kein Monatslimit. Das Modul teilt dem Modell außerdem mit, in welcher Sprache es schreiben soll, anhand der Sprache des Produkts, der Kategorie oder des verwendeten Bildschirms. Drücken Sie **Save studio**; die Bestätigung lautet **Studio settings saved.** Bereits im Katalog gespeicherter Text wird nicht neu geschrieben.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Brand voice** | leer | Sagt dem Modell, wer spricht, damit Produkttexte zum Shop passen statt zu einem allgemeinen Assistenten. Schreiben Sie ein kurzes Briefing, zum Beispiel: Fachwerkstatt, kurze Sätze, keine Übertreibung. Jede spätere Generierung beginnt mit dieser Stimme. Eine Änderung schreibt bereits gespeicherten Text nicht um. |
| **Audience** | leer | Benennt den Leser, für den das Modell schreiben soll. Verwenden Sie eine einfache Formulierung wie professionelle Installateure oder Erstkäufer. Die Antworten nutzen Vokabular und Beispiele, die auf diesen Leser zugeschnitten sind. |
| **Tone** | leer | Legt die Stimmung des Wortlauts fest: formell, warm, technisch und so weiter. Ein oder zwei Wörter genügen. Lassen Sie das Feld leer, damit der Prompt entscheidet. Es ändert weder das Modell noch die Temperature. |
| **Glossary** | leer | Eine Liste von Markennamen, Materialien und Schreibweisen, die das Modell genau übernehmen muss. Tragen Sie einen Begriff pro Zeile ein, in der Form, die erhalten bleiben soll. Neuer Text bevorzugt diese Schreibweisen. Nicht aufgeführte Begriffe können weiterhin umformuliert werden. |
| **Forbidden words** | leer | Wörter und Phrasen, die in einer gespeicherten Antwort nicht vorkommen dürfen. Ein Wort oder eine Phrase pro Zeile. Die Liste wird nur geprüft, wenn das **Quality gate** aktiviert ist. Eine Antwort, die eine dieser Zeilen enthält, wird abgelehnt und nicht ins Produkt geschrieben. Der Versuch wird trotzdem als Fehler in der History gespeichert. |
| **Monthly generation budget** | 0 | Begrenzt, wie viele erfolgreiche Generierungen der Shop im laufenden Kalendermonat ausführen kann. Geben Sie eine ganze Zahl ein. Verwenden Sie 0 für kein Limit. Der Zähler beginnt am ersten Tag des Monats von vorn. Ist das Limit erreicht, stoppen neue Generierungen mit einer Budgetmeldung bis zum nächsten Monat. Fehlgeschlagene Aufrufe werden nicht gezählt. Negative Zahlen werden als 0 gespeichert. |
| **Quality gate** | Aktiviert | Prüft die Antwort des Modells gegen die Verbotsliste, bevor etwas gespeichert wird. Aktivieren Sie es, nachdem Sie **Forbidden words** gefüllt haben. Deaktivieren Sie es, wenn die Liste nur für später hinterlegt werden soll. Aktiviert blockiert eine Antwort mit Treffer. Deaktiviert speichert die Antwort auch dann, wenn sie ein aufgeführtes Wort enthält. |

Das Budget zählt die Zeilen in der History; wenn Sie also auf dem Bildschirm History **Clear list** verwenden, beginnt die Zählung des Monats wieder bei null.

### 3.7 Settings – Prompt templates

Öffnen Sie **Settings**, dann **Prompt templates**.

![Settings, Prompt templates tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-templates.webp)

*Settings – Prompt templates: die Liste der gespeicherten Anweisungen.*

Eine Vorlage ist eine gespeicherte Anweisung. Redakteure wählen sie aus, statt dasselbe Briefing erneut zu tippen. Platzhalter werden durch das Produkt oder die Kategorie ersetzt, für die Sie erzeugen. Der Shop startet mit 16 vorgefertigten Vorlagen für Produktnamen, Beschreibungen, Meta-Titel, Meta-Beschreibungen und Tags, alle aktiviert.

**Die Liste** zeigt **ID**, **Title**, **Prompt**, **Status** (klicken Sie auf Häkchen oder Kreuz, um eine Vorlage ein- oder auszuschalten) und **Timestamp**. Jede Zeile hat **Edit** und **Delete**. Markieren Sie mehrere Zeilen und nutzen Sie die Sammelaktion **Delete** (Sie werden gefragt: **Are you sure you want to delete the selected prompts?**). Die Schaltfläche **Add new** über der Liste legt eine Vorlage an.

**Das Formular** (**Generate Prompt Template**) hat drei Felder. Drücken Sie **Save Prompt** oder **Go Back to Module Settings**, um es ohne Speichern zu verlassen. Meldungen: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Im Prompt eingegebene doppelte Anführungszeichen werden als einfache gespeichert.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Status** | Deaktiviert bei einer neuen Vorlage | Zeigt oder verbirgt diese Vorlage in den Auswahllisten auf der Produktseite, in der Massengenerierung und in Cron. Aktivieren Sie die Vorlagen, die das Team nutzen soll. Deaktivieren Sie einen Entwurf, statt ihn zu löschen. Aktivierte Vorlagen erscheinen in den Listen. Deaktivierte bleiben in dieser Tabelle, werden aber nicht angeboten. |
| **Prompt title** | leer (Pflicht) | Der Name, den Redakteure in der Vorlagenauswahl sehen. Er wird nicht an das Modell gesendet. Verwenden Sie eine kurze Bezeichnung wie HTML description with features. |
| **Prompt content** | leer (Pflicht) | Die Anweisung, die an das Modell gesendet wird. Schreiben Sie das Briefing so, wie Sie es einem Texter sagen würden, und nennen Sie Länge, HTML und Sprache, wenn sie wichtig sind. Wenn jemand die Vorlage ausführt, werden die Platzhalter aus dem aktuellen Element gefüllt, und die Antwort wird in das gewählte Feld geschrieben. |

**Platzhalter**, die Sie in einen Prompt schreiben können (sie werden für jedes Produkt, jede Kategorie oder Seite gefüllt, wenn die Vorlage läuft):

| Platzhalter | Wird ersetzt durch |
|---|---|
| `{product_name}` `{product_description}` `{product_description_short}` `{product_tags}` `{product_reference}` `{product_ean13}` `{product_weight}` | Die eigenen Daten des Produkts in der Sprache, in der geschrieben wird. |
| `{product_brand}` `{product_default_category}` `{product_category_description}` `{product_categories}` | Die Marke des Produkts, Name und Beschreibung seiner Standardkategorie und die Namen aller seiner Kategorien. |
| `{product_attributes}` `{product_features}` `{product_feature_values}` `{product_images}` | Die Kombinationsattribute des Produkts, Merkmalsnamen, Paare aus Merkmalsname und -wert sowie Links zu seinen Bildern. |
| `{category_name}` `{category_description}` `{category_parent_name}` | Die Kategorie, für die geschrieben wird, und der Name ihrer übergeordneten Kategorie. |
| `{cms_title}` `{brand_name}` `{brand_description}` `{brand_short_description}` | Daten der Inhaltsseite oder Marke, die geöffnet ist, wenn Sie die Verknüpfung der oberen Leiste verwenden. |
| `{shop_name}` `{shop_url}` `{shop_language}` `{shop_country}` `{shop_currency}` | Shopweite Daten: Name, Domain, Sprache, Standardland und Code der Standardwährung. |

Verwenden Sie nur Platzhalter, die dort sinnvoll sind, wo die Vorlage laufen wird. Ein Produkt-Platzhalter in einem Kategorie-Briefing bleibt als eingetippter Text stehen.

### 3.8 Settings – Playground

Öffnen Sie **Settings**, dann **Playground**.

![Settings, Playground tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-playground.webp)

*Settings – Playground: ein Notizblock für eine freie Anweisung.*

Der Playground sendet eine freie Anweisung an das aktive Modell und gibt die Antwort unter der Schaltfläche aus. Sie können Shopnamen, Shop-URL, einen Produktnamen, eine Referenz oder Produktmerkmale erwähnen, damit das Modul Katalogdaten einsetzt. Die Antwort bleibt auf dieser Seite. Es wird kein Produkt- oder Kategoriefeld gespeichert.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Instruction box** | leer | Geben Sie die Anweisung in einfacher Sprache ein und drücken Sie **Generate**. Der aktive Anbieter erhält diesen Text zusammen mit den Studio-Regeln. Die Antwort erscheint unter der Schaltfläche mit der Anzahl der verbrauchten Tokens. Der Katalog wird nicht aktualisiert. |

Drücken Sie **Generate** bei leerem Feld, sehen Sie **Write a prompt first.** Jeder Aufruf wird in der History mit dem Typ **general** gespeichert.

### 3.9 Generate – Products

Öffnen Sie **Generate**, dann **Products**. Sie können auch auf die Schaltfläche **My AI Grok** neben den Sammelaktionen der Produktliste klicken.

Die Massengenerierung hat zwei Schritte: einen Filter, der eine Liste aufbaut, und einen Lauf über diese Liste.

**Schritt 1: Filter products to update.** Dieser Schritt baut nur die Produktliste auf. Es wird nichts in Produkte geschrieben, bis Sie auf dem nächsten Bildschirm einen Umfang und Sprachen wählen und **Run** drücken. Diese Filter werden nicht als Shop-Einstellungen gespeichert. Drücken Sie **Go to next step**, wenn Sie bereit sind. Ein leerer Filter wird ignoriert.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Product Categories** | nichts markiert | Beschränkt die Produktliste auf Artikel, die in den markierten Kategorien liegen (oder eine davon als Standardkategorie haben). Markieren Sie die gewünschten Kategorien. Lassen Sie den Baum leer, wenn die Kategorie keine Rolle spielen soll. |
| **Brand** | Select brand (no filter) | Behält Produkte eines Herstellers. Wählen Sie eine Marke oder lassen Sie die erste leere Option, wenn alle Marken enthalten sein sollen. |
| **Product status** | Active | Behält Produkte, die im Verkauf sind, deaktiviert sind oder beides. Wählen Sie **Active** für den Live-Katalog, **Disabled** für Entwürfe oder **Both**. |
| **Product stock** | All products | Überspringt optional Produkte, die nicht auf Lager sind. **Only in stock products** entfernt Produkte ohne verfügbare Menge aus der Liste. **All products** lässt den Lagerbestand aus dem Filter heraus. |
| **Update only** | Update all | Nutzt die Generierungs-History, um Produkte einzubeziehen, die dieses Modul noch nie beschrieben hat (**Products that have not been updated with OpenAi content**), nur solche, bei denen das schon geschah (**Products that already have been updated with OpenAi content**), oder jedes Produkt (**Update all**). Wählen Sie „noch nicht aktualisiert“ für einen ersten Durchgang und „bereits aktualisiert“, wenn Sie neu schreiben wollen. Ein Produkt gilt als bereits aktualisiert, wenn die History irgendeinen Eintrag dafür enthält, auch einen fehlgeschlagenen Versuch. |
| **Product IDs** | leer | Beschränkt die Liste auf bestimmte Produkt-IDs. Geben Sie IDs durch Kommas getrennt ein, zum Beispiel 12,45,103. |
| **Product Reference** | leer | Beschränkt die Liste auf bestimmte Referenzcodes. Geben Sie eine oder mehrere Referenzen durch Kommas getrennt ein. |
| **Product Add Date From** | leer | Das früheste Erstellungsdatum, das ein Produkt haben darf, um einbezogen zu werden. Davor erstellte Produkte werden ausgelassen. |
| **Product Add Date To** | leer | Das späteste Erstellungsdatum, das ein Produkt haben darf, um einbezogen zu werden. Danach erstellte Produkte werden ausgelassen. |
| **Minimum product ID** | leer | Die kleinste Produkt-ID, die in der Liste erscheinen darf. Geben Sie eine ganze Zahl ein. |
| **Maximum product ID** | leer | Die größte Produkt-ID, die in der Liste erscheinen darf. Geben Sie eine ganze Zahl ein. |
| **Product Limit** | leer (kein Limit) | Begrenzt, wie viele Produkte in die Generierungsliste geladen werden. Verwenden Sie bei einem großen Katalog eine kleine Zahl, etwa 20. Der nächste Bildschirm zeigt nie mehr als diese Anzahl, sodass ein Lauf nicht versehentlich den ganzen Katalog durchläuft. |

**Schritt 2: Mass product generation.** Der nächste Bildschirm zeigt eine Tabelle der passenden Produkte (**ID**, **Reference**, **Result**) mit den Bedienelementen des Laufs darüber.

![Mass product generation with the filtered list](https://mypresta.eu/docs/images/docs/myaigrok-generate-products.webp)

*Generate – Products: Vorlage, Umfang, vorhandener Text, Sprachen und die Liste, auf der der Lauf stattfindet.*

Schreibt die gefilterten Produkte nacheinander mit dem aktiven Modell. Jedes Produkt in der Tabelle wird in den markierten Sprachen aktualisiert. Produkte, die nicht im Filter waren, bleiben unberührt. Eine Zeile zeigt ihr Ergebnis, sobald das jeweilige Produkt fertig ist.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Template** | **Choose a template** (keine) | Füllt das Prompt-Feld aus einer in Settings gespeicherten Vorlage. Wählen Sie einen Titel oder lassen Sie die erste Option und tippen Sie im Feld darunter Ihren eigenen Prompt. Das Modell erhält den Text aus dem Feld, wobei Produkt-Platzhalter für jede Zeile ersetzt werden. Der Titel selbst wird nicht gesendet. Bleibt das Feld leer, wird für jedes Feld ein vorgefertigtes kurzes Briefing verwendet. |
| **What to generate** | Descriptions | **Descriptions** schreibt die lange und die kurze Beschreibung. **Meta title and meta description** schreibt beide Meta-Felder. **Descriptions and meta together** schreibt alle vier. Felder außerhalb dieser Auswahl bleiben unverändert. Jedes Feld erhält eine eigene Anfrage. |
| **Existing text** | Replace | **Replace** überschreibt das Feld. **Skip if filled** lässt ein gefülltes Feld unberührt und ruft das Modell dafür nicht auf. **Add above** und **Add below** behalten den alten Text und hängen den neuen davor oder danach an. Replace ändert den gespeicherten Wert. Skip schützt gefüllte Felder. Add behält beide Versionen im selben Feld. |
| **Languages** | die Sprache Ihrer eigenen Backoffice-Sitzung ist markiert | Markieren Sie jede Sprache, die geschrieben werden soll. Entfernen Sie die Markierung, um eine Sprache unberührt zu lassen. Jede markierte Sprache wird separat erzeugt. Nicht markierte Sprachen behalten ihren aktuellen Text. |
| **Run on the list below** | – | Startet den Lauf. Eine Statuszeile zeigt den Fortschritt (zum Beispiel 3 / 24 gefolgt vom Feldnamen) und endet mit **Finished N products.** Ist keine Sprache markiert, sehen Sie **Select at least one language.** |

Jede Zeile in der Spalte **Result** meldet eine Zeile pro Feld und Sprache, zum Beispiel den Feldnamen gefolgt von **success**, **skipped** oder **error** und einer kurzen Meldung. **skipped** mit **Product skipped.** bedeutet, dass das Feld bereits Text hatte und **Skip if filled** gewählt war. **error**-Zeilen enthalten den Grund; derselbe Fehler wird in der History gespeichert.

Lassen Sie diesen Browser-Tab geöffnet, bis der Lauf **Finished** meldet. Der Lauf wird von der Seite gesteuert: Sie sendet jeweils eine Anfrage, und Schließen oder Neuladen des Tabs stoppt ihn. Bereits fertige Produkte bleiben geschrieben. Ein sehr langer Text wird auf die Grenzen von PrestaShop gekürzt: Namen auf 128 Zeichen, Kurzbeschreibungen auf 800, Meta-Titel auf 69 und Meta-Beschreibungen auf 159.

### 3.10 Generate – Categories

Öffnen Sie **Generate**, dann **Categories**. Es funktioniert wie der Produktbildschirm mit weniger Filtern.

**Schritt 1: Filter categories to update.** Dieser Schritt baut nur die Kategorieliste auf. Es wird nichts an das Modell gesendet, bis Sie auf dem nächsten Bildschirm einen Prompt schreiben und den Lauf starten. Die Filter hier werden nicht als Shop-Einstellungen gespeichert. Drücken Sie **Go to next step**.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Categories** | nichts markiert | Wählt die Kategorien aus, die im nächsten Schritt in der Liste erscheinen. Markieren Sie eine oder mehrere Kategorien. Lassen Sie den Baum leer, um jede Kategorie einzubeziehen, die zum Status unten passt. |
| **Category status** | Active | Behält aktive Kategorien, deaktivierte oder beides (**Active**, **Disabled**, **Both**). Der nächste Schritt listet nur Kategorien mit diesem Status. |

**Schritt 2: Mass category generation.**

![Mass category generation](https://mypresta.eu/docs/images/docs/myaigrok-generate-categories.webp)

*Generate – Categories: die Anweisung, das Feld, vorhandener Text, Sprache und die Kategorieliste.*

Schreibt ein Feld für jede Kategorie der gefilterten Liste. Jede aufgeführte Kategorie wird in dieser Sprache aktualisiert. Andere Felder und andere Sprachen bleiben unverändert.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Instruction box** (über der Feldliste) | leer | Die Anweisung, die für jede Kategorie gesendet wird. Beschreiben Sie Tonalität, Länge und HTML. Verwenden Sie `{category_name}`, wenn der Kategoriename im Briefing erscheinen soll. Jede Kategorie wird aus diesem gleichen Text erzeugt. Bleibt das Feld leer, wird ein vorgefertigtes kurzes Briefing verwendet. |
| **Field selector** | Description | Das Kategoriefeld, das dieser Lauf schreibt: **Description**, **Name**, **Meta title**, **Meta description** oder **Additional description**. Nur dieses Feld wird gespeichert. Die anderen Kategoriefelder bleiben unverändert. Hat Ihr PrestaShop kein Feld Additional description für Kategorien, sehen Sie **Error! This PrestaShop version does not support the category Additional Description field.** |
| **Existing text selector** | Replace | **Replace** überschreibt das Feld. **Skip if filled** lässt es unberührt und ruft das Modell für diese Kategorie nicht auf. |
| **Language selector** | Ihre Backoffice-Sprache | Die Sprachversion, die geschrieben wird. Wählen Sie eine Sprache. Führen Sie den Lauf für eine weitere Sprache erneut aus. Nur diese Sprache ändert sich. |
| **Run on the categories below** | – | Startet den Lauf. Die Ergebnisse erscheinen pro Zeile, wie auf dem Produktbildschirm. |

Unter der Liste zeigt der Bildschirm außerdem ein zweites Formular namens **Generate category content**. Nutzen Sie zum Erzeugen die Schaltfläche **Run on the categories below** darüber. Dieses zweite Formular merkt sich nur seine Auswahl und bringt Sie zum Kategoriefilter zurück (siehe Abschnitt 5.12).

### 3.11 New product

Öffnen Sie **New product**. Dieser Bildschirm macht aus einem kurzen Briefing einen Produktentwurf und kann diesen Entwurf in den Katalog einfügen.

![New product screen](https://mypresta.eu/docs/images/docs/myaigrok-new-product.webp)

*New product: Briefing, optionale Quellseite, Sprache und Standardkategorie.*

**Generate data** zeigt den Entwurf und speichert kein Produkt. **Create product** legt ein aktives Produkt in dieser Sprache und Kategorie an, übernimmt Name, Beschreibungen, Meta-Daten, Tags, Merkmale, Preis und Referenz aus dem Entwurf, gibt ihm einen Anfangsbestand von 100 Stück und ordnet es der gewählten Kategorie zu.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **What is the product?** | leer | Das Briefing, das das Modell zu Name, Beschreibungen, Meta-Daten, Tags, Merkmalen, Referenz und Preis ausbaut. Beschreiben Sie das Produkt in wenigen Sätzen. Nennen Sie Materialien, Zielgruppe und unbedingt zu erhaltende Namen. Ein reichhaltigeres Briefing ergibt einen passenderen Entwurf. Ein leeres Feld wird mit **Prompt is required** abgelehnt. |
| **Optional source URL** | leer | Fügt dem Briefing Text hinzu, der von einer öffentlichen Seite gelesen wird, damit der Entwurf einer vorhandenen Produktseite folgen kann. Fügen Sie eine vollständige Webadresse ein oder lassen Sie das Feld leer. Eine lesbare Seite wird als zusätzlicher Kontext angehängt. Eine Seite, die der Shop nicht lesen kann, wird ignoriert, und es wird nur das Briefing verwendet. |
| **Language** | die Standardsprache des Shops | Die Shopsprache, in der der Text des neuen Produkts gespeichert wird. Andere Sprachen werden von diesem Bildschirm nicht gefüllt. Name, Beschreibungen, Meta-Daten und Tags werden nur in dieser Sprache gespeichert. |
| **Default category ID** | 2 | Die Kategorie-ID, die als Standardkategorie des Produkts zugewiesen wird. Geben Sie die numerische ID aus **Catalog**, **Categories** ein. 2 ist meist Home. Das neue Produkt wird dieser Kategorie zugeordnet. |
| **Generate data** | – | Fragt das Modell nach dem Entwurf und gibt ihn als strukturierten Text unter den Schaltflächen aus. Kann die Antwort nicht gelesen werden, sehen Sie **Failed to parse AI response. Please try again.** |
| **Create product** | – | Fügt den Entwurf ein. Bei Erfolg zeigt das Feld **Product #** gefolgt von der ID des neuen Produkts. Drücken Sie es vor dem Erzeugen, erscheint **Generate the product first.** |

Das Produkt wird ohne Bilder, mit der ersten Steuerregel des Shops und einem Preis aus dem Entwurf angelegt; öffnen Sie es anschließend, um Preis, Steuer, Bilder und Lagerbestand zu prüfen. Ist kein API-Schlüssel gespeichert, zeigt der Bildschirm **Add an API key in the module settings first.**

### 3.12 Cron

Öffnen Sie **Cron**. Dieser Bildschirm erstellt Adressen, die Ihr Server nach Zeitplan aufruft, um Produkt- oder Kategoriefelder in kleinen Stapeln zu füllen. Nichts läuft von selbst. Der Shop tut nichts, bis der Server die Adresse aufruft.

![Cron screen](https://mypresta.eu/docs/images/docs/myaigrok-cron.webp)

*Cron: das Panel mit der Kategorieadresse, dann das Produktformular mit seiner Adresse und seinen Schaltern.*

**Was der Bildschirm von oben nach unten enthält:** ein Panel **Category cron** mit der Kategorieadresse; das Formular **CRON JOB Settings – Generate product content using Grok**; das Formular **CRON JOB Settings - Generate category content using Grok**; und ein Panel **Cron parameters** mit der Produktadresse, dem gewählten Feld, dem Ziel und der Stapelgröße.

**Wichtig:** Die auf diesem Bildschirm angezeigten Adressen enden beim Secret. Damit der Aufruf etwas bewirkt, müssen Sie der Adresse die Aktion hinzufügen. Die vollständigen Adressformen stehen in Abschnitt 4.2. Außerdem muss **Enable Cron Feature** auf **Yes** stehen, sonst antwortet jeder Cron-Aufruf, für Produkte wie für Kategorien, dass die Funktion deaktiviert ist.

**Produktformular** (drücken Sie unten im Formular auf **Save**):

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Enable Cron Feature** | No | Erlaubt dem Server, Text nach Zeitplan zu erzeugen, ohne dass ein Mitarbeiter durch den Katalog klickt. Schalten Sie dies erst ein, nachdem Secret, Feld, Sprache und Prompt unten gespeichert sind. Der Server muss die Adresse weiterhin aufrufen. Aktiviert lässt die gespeicherte Adresse die Arbeit erledigen. Dieser Schalter steuert auch die Kategorieadresse. |
| **Cron Job Secret Token** | ein langer Zufallswert, bei der Installation erzeugt | Ein langes Passwort, das in der Produktadresse enthalten sein muss. Ohne es lehnt der Shop den Aufruf ab. Behalten Sie den erzeugten Wert. Wenn Sie ihn ersetzen, kopieren Sie die neue Adresse in den Scheduler des Servers. Wer dieses Secret nicht kennt, kann den Produkt-Cron nicht ausführen. Eine Änderung macht die alte Adresse sofort ungültig. Verwenden Sie mindestens 24 Zeichen (siehe Abschnitt 5.10). |
| **Update Field** | description | Das einzelne Produktfeld, das dieser Cron-Befehl neu schreibt: **name**, **description**, **description_short**, **meta_title**, **meta_description** oder **tags**. Um Beschreibung und Meta-Daten zu füllen, legen Sie zwei Cron-Befehle mit zwei verschiedenen Feldern an. Jeder Lauf schreibt nur dieses Feld in der unten gewählten Sprache. |
| **Selected Products** | pendingGrok | Bestimmt, welche Produkte noch warten. **pendingGrok** nimmt Produkte, die dieses Modul in keinem Feld je erfolgreich geschrieben hat. **pendingField** nimmt Produkte, die für genau dieses Feld noch nicht geschrieben wurden, sodass Sie mehrere Cron-Jobs (zum Beispiel Beschreibung und Name) über dieselben Produkte laufen lassen können. **emptyField** nimmt nur Produkte, bei denen das gewählte Feld in der gewählten Sprache leer ist. Jeder Lauf überspringt Produkte, die nicht mehr passen, sodass sich ein fertiger Katalog nicht mehr ändert. Fehlgeschlagene frühere Versuche zählen nicht als geschrieben und werden erneut versucht. |
| **Product Categories** | nichts markiert | Beschränkt den Cron auf Produkte, die in den markierten Kategorien liegen. Markieren Sie eine oder mehrere Kategorien. Lassen Sie den Baum leer, um die Kategorie zu ignorieren und nur die übrigen Filter zu nutzen. Lesen Sie Abschnitt 5.10, bevor Sie Kategorien markieren. |
| **Product ID list** | leer | Beschränkt den Lauf auf eine ausdrückliche Liste von Produkt-IDs. Geben Sie IDs durch Kommas getrennt ein, zum Beispiel 12,45,103. Buchstaben und andere Zeichen werden beim Speichern entfernt. Nur diese Produkte können durch diesen Befehl aktualisiert werden. |
| **Language** | die Standardsprache des Shops zum Zeitpunkt der Installation | Die Sprachversion des Produktfelds, die dieser Cron schreibt. Wählen Sie eine Shopsprache. Andere Sprachen benötigen einen eigenen Cron-Befehl. |
| **Product to update** | 5 products | Wie viele passende Produkte bei jedem Aufruf der Adresse verarbeitet werden (2 bis 1000). Beginnen Sie mit 5 oder 10, damit ein langsames Modell das Zeitlimit des Servers nicht erreicht. Erhöhen Sie den Wert, sobald ein Lauf sauber durchläuft. |
| **Prompt Template** | keine gewählt | Die gespeicherte Anweisung, die für jedes Produkt dieses Laufs an das Modell gesendet wird. Wählen Sie eine aktivierte Vorlage aus Settings. Platzhalter in dieser Vorlage werden pro Produkt gefüllt. Wählen Sie vor dem ersten Aufruf eine Vorlage. Eine spätere Änderung der Vorlage betrifft nur den nächsten Lauf. |
| **Enable Debug** | No | Zeigt, was der Cron tun würde, wenn Sie die Adresse im Browser öffnen, ohne Produkte zu speichern. Aktivieren Sie es, während Sie den Befehl prüfen. Deaktivieren Sie es, bevor der Server-Scheduler dieselbe Adresse nutzt. Aktiviert gibt den Plan aus und schreibt keinen Katalogtext. |
| **CRON JOB interval** | Every Hour | Der Rhythmus, den Sie auf dem Server einsetzen wollen (**Every 1 Minute** bis **Every 6 Hours**). Passen Sie ihn an den Scheduler an, den Sie anlegen. Das Modul startet den Scheduler nicht selbst und erzwingt diesen Wert nicht. |
| **Product Cron Job command** | – | Zeigt die Basisadresse. Kopieren Sie sie, fügen Sie die Aktion gemäß Abschnitt 4.2 hinzu und fügen Sie das Ergebnis in Ihren Server-Scheduler ein. Sie können beliebig viele Cron-Befehle anlegen. |

**Das Kategorieformular** folgt derselben Logik mit eigenem Secret und eigenem Stapel:

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Cron Job Secret Token** | ein langer Zufallswert, bei der Installation erzeugt | Ein langes Passwort, das in der Kategorieadresse enthalten sein muss. Es ist vom Produkt-Secret getrennt. Behalten Sie den erzeugten Wert. Aufrufe ohne dieses Secret werden abgelehnt. Eine Änderung macht die alte Kategorieadresse sofort ungültig. |
| **Update Field** | description | Das einzelne Kategoriefeld, das dieser Befehl neu schreibt: **name**, **description**, **meta_title** oder **meta_description**. Name, Beschreibung und Meta-Daten benötigen jeweils einen eigenen Befehl, wenn Sie alle füllen wollen. |
| **Selected categories** | pendingGrok | Dieselben drei Auswahlmöglichkeiten wie bei Produkten (**pendingGrok**, **pendingField**, **emptyField**), angewendet auf Kategorien. Jeder Lauf überspringt Kategorien, die nicht mehr passen. |
| **Language** | die Standardsprache des Shops zum Zeitpunkt der Installation | Die Sprachversion des Kategoriefelds, die dieser Cron schreibt. Andere Sprachen benötigen einen eigenen Befehl. |
| **Categories to update** | 5 categories | Wie viele passende Kategorien bei jedem Aufruf der Adresse verarbeitet werden. Beginnen Sie mit 5 oder 10. |
| **Prompt Template** | keine gewählt | Die gespeicherte Anweisung, die für jede Kategorie dieses Laufs an das Modell gesendet wird. Schreiben Sie das Briefing für eine Kategorie, nicht für ein Produkt (zum Beispiel mit `{category_name}`). |
| **Enable Debug** | No | Zeigt, was der Kategorie-Cron tun würde, wenn Sie die Adresse im Browser öffnen, ohne Kategorien zu speichern. Deaktivieren Sie es, bevor der Scheduler die Adresse nutzt. |
| **CRON JOB interval** | Every Hour | Der Rhythmus, den Sie auf dem Server einsetzen wollen. Er ist nur eine Erinnerung. |
| **Category Cron Job command** | – | Zeigt die zu kopierende Basisadresse. Fügen Sie die Aktion gemäß Abschnitt 4.2 hinzu. |

Der Kategorie-Cron berührt die Startkategorie (Home) selbst nie.

### 3.13 History

Öffnen Sie **History**. Dieser Bildschirm ist ein Bericht über jeden Aufruf an Grok und dient als Ihr Prüfpfad.

![History screen](https://mypresta.eu/docs/images/docs/myaigrok-history.webp)

*History: Filter, Summen, Aufschlüsselungstabellen und die Liste der Aufrufe.*

Grenzen Sie die Karten, die Aufschlüsselungstabellen und die History-Liste auf einen Ausschnitt der Generierungen ein. Klicken Sie auf eine Datumsvorgabe oder setzen Sie **From** und **To**. Anschließend können Sie optional nach Modell, Typ, Status, Sprache, Mitarbeiter, einer Produkt- oder Kategorie-ID oder einem Wort einschränken, das im Prompt oder in der Antwort vorkommen muss. Drücken Sie **Filter**. Nur passende Zeilen bleiben sichtbar. Die gespeicherte History wird nicht gelöscht, und kein Produkt wird geändert.

| Bedienelement | Bei Installation | Was es bewirkt |
|---|---|---|
| **Date presets** | This month | **Today**, **7 days**, **30 days**, **This month**, **All time**. |
| **From / To** | erster Tag des Monats bis heute | Ein benutzerdefinierter Datumsbereich. |
| **Model** | Any | Nur Aufrufe mit diesem Modell. |
| **Type** | Any | Nur diese Art von Aufruf (siehe Tabelle unten). |
| **Status** | Any | **Success** oder **Error**. |
| **Language** | Any | Nur Aufrufe für diese Sprache. |
| **Employee** | Any | Nur Aufrufe, die dieser Mitarbeiter gestartet hat. Von Cron gestartete Aufrufe haben keinen Mitarbeiter. |
| **Product / category ID** | leer | Nur Zeilen für diese ID (ein Produkt, eine Kategorie, eine Inhaltsseite oder eine Marke mit dieser Nummer). |
| **Prompt or reply contains** | leer | Nur Zeilen, in denen Prompt, Antwort oder Fehlertext das Wort enthält. |
| **Filter** | – | Wendet die Filter an. |

**Karten:** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** und **Average time**. Ein Strich bedeutet, dass Grok für diesen Aufruf keine Token-Zahl geliefert hat.

**Aufschlüsselungstabellen:** **By day**, **By model**, **By type**, **By language**, **By employee**, jeweils mit **Group**, **Calls**, **Sent**, **Received** und **Total**. Eine kleine Zahl neben Calls ist die Anzahl der Fehler in dieser Gruppe.

**Die Liste** trägt den Titel **Prompt history** und zeigt 50 Zeilen pro Seite mit den Spalten **ID**, **Status** (ein grünes Abzeichen **Success** oder ein rotes **Error**), **Prompt**, **Reply / Error**, **Provider** (Dienst, Modell und benötigte Zeit, plus gegebenenfalls ein Statuscode von Grok), **Sent**, **Received**, **Total**, **Entity ID**, **Type** und **Timestamp**. Die Zeilenaktion **View** öffnet den vollständigen Prompt und die Antwort mit den Tokens, und **Back to the list** führt zurück. Wurde die Zeile inzwischen gelöscht, sehen Sie **This log entry no longer exists.**

| Typwert | Bedeutung |
|---|---|
| **general** | Eine freie Anweisung aus dem Playground oder der Verknüpfung der oberen Leiste. |
| **singleCategory**, **singleCMS**, **singleBrand** | Die Verknüpfung der oberen Leiste wurde verwendet, während eine Kategorie, Inhaltsseite oder Marke geöffnet war. |
| **product_name**, **product_description**, **product_description_short**, **product_meta_title**, **product_meta_description**, **product_tags** | Ein Produktfeld wurde per Schaltfläche, Massenlauf oder Cron geschrieben (oder versucht). |
| **product_seo_pack** | Das SEO-Paket hat Name, Beschreibungen und Meta-Daten in einem Zug geschrieben. |
| **category_name**, **category_description**, **category_meta_title**, **category_meta_description**, **category_additional_description** | Ein Kategoriefeld wurde geschrieben. |
| **error** | Ein fehlgeschlagener Produktaufruf. |

Die Symbolleisten-Schaltfläche **Clear list** löscht jede Zeile der History endgültig und bestätigt mit **Log list successfully deleted.** Das entfernt auch die Wiederherstellungspunkte auf Produktseiten und setzt die Zählung des Monatsbudgets zurück, verwenden Sie sie daher mit Bedacht.

### 3.14 Images

Öffnen Sie **Images**. Dieser Bildschirm schaltet die Bildsuche auf der Produktseite ein oder aus und speichert die Anweisung, die an das Modell gesendet wird.

![Images screen](https://mypresta.eu/docs/images/docs/myaigrok-images.webp)

*Images: der Schalter AI Image Finder und sein Prompt.*

Diese beiden Felder steuern die Bildsuche auf der Produktseite. Das Speichern lädt keine Bilder herunter und ändert keine Produkttexte. Drücken Sie **Save**; die Bestätigung lautet **Settings saved.**

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **AI Image Finder** | Aktiviert | Zeigt oder verbirgt die Bildsuche auf der Produktbearbeitungsseite. Aktivieren Sie es, wenn Redakteure nach Fotos des aktuellen Produkts suchen sollen. Deaktivieren Sie es, um diese Schaltfläche zu entfernen. Aktiviert zeigt die Suche. Deaktiviert blendet sie aus. Ein Bild wird erst importiert, nachdem jemand es bestätigt hat. |
| **AI Image Search Prompt** | Verlangt genau 5 Seitenadressen | Die Anweisung, die bei der Suche nach Produktbildern gesendet wird. Die Platzhalter für Produktname und Produktbeschreibung werden durch das aktuelle Produkt ersetzt. Behalten Sie die Aufforderung nach einer Liste von Seitenadressen bei (der Bildschirm nennt sie ein JSON-Array von Seiten-URLs). Ändern Sie den Wortlaut, wenn Sie Herstellerseiten oder eine andere Anzahl von Links wünschen. Ein präziserer Prompt liefert relevantere Seiten. Ein vager Prompt liefert unpassende Links. Es wird nichts gespeichert, bis ein Redakteur ein Bild auswählt. |

### 3.15 Updates

Öffnen Sie **Updates** (ganz rechts in der Leiste).

![Updates screen](https://mypresta.eu/docs/images/docs/myaigrok-updates.webp)

*Updates: manuelle Prüfung, automatische Benachrichtigungen und der Link zur Produktseite.*

Der Bildschirm trägt den Titel **MyPresta Updates**. Er prüft bei MyPresta.eu, ob es eine neuere Modulversion gibt, und kann Sie im Backoffice warnen. Der Katalog und die erzeugten Texte bleiben unverändert.

| Feld | Bei Installation | Was es bewirkt |
|---|---|---|
| **Manual Check** | – | Kontaktiert einmal die Update-Server von MyPresta.eu und vergleicht die entfernte Version mit der in diesem Shop. Klicken Sie nach der Installation oder bei Verdacht auf ein neues Release auf **Check Now**. Neben der Schaltfläche erscheint **Module is up to date!** oder **New version available!**. |
| **Automatic Notifications** | Aktiviert | Prüft im Backoffice regelmäßig (etwa alle 3 Tage) auf Updates. Stellen Sie **Enabled** ein, um ein Warnbanner zu erhalten, wenn eine neuere Version existiert. Mitarbeiter sehen dann eine Benachrichtigung mit einem Link zu weiteren Details. Stellen Sie **Disabled** ein, wenn Sie Updates nur manuell verwalten. Speichern Sie mit **Save**; die Bestätigung lautet **Update settings saved.** |
| **Product Page** | Link | Öffnet die offizielle MyPresta-Produktseite dieses Moduls in einem neuen Tab. |

### 3.16 Arbeiten auf der Produktbearbeitungsseite

Öffnen Sie ein Produkt (**Catalog**, **Products**, das Produkt), dann den Reiter **Modules**, dann **My AI Grok**. Der Block hat bis zu vier Reiter: **Generate**, **Simulate**, **Photos** und **History**. Welche Reiter Sie sehen, hängt von **Product edit page Form** und **Product Edit History** in Abschnitt 3.4 ab. Das Produkt muss mindestens einmal gespeichert worden sein.

![My AI Grok block on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-edit.webp)

*Produktbearbeitungsseite, Reiter Generate: Sprach-Chips, Verhalten bei vorhandenem Text und eine Karte pro Feld.*

**Reiter Generate.** Jede Schaltfläche schreibt ein Produktfeld, und der Text wird sofort im Produkt gespeichert.

- **Language:** ein Chip pro aktiver Sprache sowie **Every language**, das jede Sprache nacheinander ausführt.
- **If the field already has text:** **Replace**, **Add above**, **Add below** oder **Skip if filled**. Sie verhalten sich wie in Abschnitt 3.9 beschrieben.
- **Feldkarten:** **Description** (langer Text mit kurzer Einleitung und Merkmalsliste), **Short description** (eine kurze, schlichte Zusammenfassung, unter etwa 400 Zeichen), **Name**, **Meta title** (etwa 70 Zeichen), **Meta description** (etwa 160 Zeichen) und **Tags** (eine durch Kommas getrennte Liste). Drücken Sie auf der Karte **Fill**.
- **SEO pack:** **Fill all** füllt Name, beide Beschreibungen und beide Meta-Felder in einer Anfrage. Es ist nur im Reiter Generate verfügbar. Aktualisieren Sie danach die Produktseite, um die neuen Werte zu sehen.
- **Use your own instruction or a saved prompt:** Öffnen Sie diesen Bereich, um Ihre gespeicherten Vorlagen nach Titel oder Text zu filtern, eine auszuwählen (die erste Kachel **Standard brief** nutzt ein vorgefertigtes Briefing für das Feld, das Sie drücken) oder unter **Instruction** einen eigenen Text einzutippen. Lassen Sie das Feld leer, um das Standard-Briefing zu verwenden. Passt keine Vorlage zum Filter, sehen Sie **No prompt matches that filter.**
- Das Ergebnis wird außerdem in einem Panel unter den Karten ausgegeben, mit der Anzahl der Tokens.

Laden Sie nach einem **Fill** die Produktseite neu, um den neuen Text im Formular zu sehen.

**Reiter Simulate.** Probieren Sie ein Feld zuerst aus. Die Antwort bleibt auf dieser Seite, und das Produkt wird nicht geändert. Er hat dieselben Sprach-Chips und Feldkarten, aber jede Karte hat **Try** statt **Fill**. Jedes Try erzeugt dennoch eine Zeile in der History.

![Simulate tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-simulate.webp)

*Reiter Simulate: **Try** zeigt die Antwort, ohne zu speichern.*

**Reiter Photos.** Ist **AI Image Finder** aktiviert, sucht Grok nach Fotos dieses Produkts.

![Photos tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-photos.webp)

*Reiter Photos: Seiten finden, Fotos markieren, dem Produkt hinzufügen.*

1. Drücken Sie **Find pages**. Grok schlägt Webseiten vor, und das Modul liest Fotos von bis zu fünf davon (bis zu 24 Fotos).
2. Markieren Sie die gewünschten Fotos.
3. Drücken Sie **Add selected to this product**. Die Fotos werden heruntergeladen und angehängt; das zuerst markierte Foto wird zum Titelbild. Vor diesem Schritt wird nichts gespeichert.

Adressen in privaten Netzwerken werden nie geöffnet. Ist der Finder abgeschaltet, weist der Reiter darauf hin, dass Sie **AI Image Finder** unter Settings, General aktivieren und das Produkt erneut öffnen müssen.

**Reiter History.** Listet frühere Schreibvorgänge für dieses Produkt mit **When**, **Type**, **Status** und einer Schaltfläche **Restore**. **Restore** fragt **Restore the previous value?** und holt nach Bestätigung den früheren Text zurück und weist Sie an, die Seite zu aktualisieren. Die shopweite History wird nicht gelöscht. **Restore** wird nur für erfolgreiche Zeilen angeboten, die einen vorherigen Wert gespeichert haben. Ist die Liste leer, zeigt der Reiter **No generations for this product yet.**

![History tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-history.webp)

*Reiter History: frühere Schreibvorgänge mit einer Schaltfläche Restore.*

### 3.17 Weitere Stellen, an denen das Modul erscheint

- **Schaltflächen Generate with AI neben Feldern.** Im Produktbearbeitungsformular erscheint neben Beschreibung, Kurzbeschreibung, Meta-Titel und Meta-Beschreibung jeder Sprache eine kleine Schaltfläche. Im Kategoriebearbeitungsformular erscheint sie neben Beschreibung, zusätzlicher Beschreibung, Meta-Titel und Meta-Beschreibung. Klicken Sie darauf. Hat der Shop mehr als eine Sprache, werden Sie gebeten, **Current language**, **All languages** oder **Cancel** zu wählen. Der Text wird in das Formularfeld eingefügt. Speichern Sie das Produkt oder die Kategorie, um ihn zu behalten. Es wird ein vorgefertigtes Briefing für dieses Feld verwendet, und Ihre Studio-Regeln gelten weiterhin. Wurde das Element noch nie gespeichert, sehen Sie **Save the product once before generating.** (oder **Save the category once before generating.**). Der Schalter **Product edit page Form** blendet nur den Modulblock im Reiter **Modules** aus; diese kleinen Schaltflächen entfernt er nicht.
- **Verknüpfung in der oberen Leiste.** Bei aktiviertem **Admin Top Bar CTA** öffnet ein Zauberstab-Symbol in der oberen Leiste ein kleines Fenster: Wählen Sie ein **Template** (optional), geben Sie die Anweisung ein und drücken Sie **Generate**. Befinden Sie sich auf einem Bearbeitungsbildschirm einer Kategorie, Inhaltsseite oder Marke, werden die passenden Platzhalter gefüllt. Die Antwort erscheint im Fenster, und es wird nichts gespeichert.
- **Produktliste.** Eine Schaltfläche **My AI Grok** neben den Sammelaktionen öffnet **Generate**, **Products**.

## 4. Frontoffice des Shops

Das Modul hat keinen kundenseitigen Bildschirm. Es zeigt nichts in Kopfzeile, Fußzeile oder auf einer Produkt-, Kategorie- oder Kassenseite, und das Theme hat nichts anzuzeigen oder zu überschreiben. Kunden sehen nie ein Werkzeug zur Textgenerierung; sie sehen nur den Text, den Sie bereits im Katalog gespeichert haben.

### 4.1 Vom Modul selbst genutzte Adressen

Zwei Webadressen Ihres Shops gehören zum Modul. Die erste öffnen Sie nie selbst.

- Die **Generator-Adresse** wird von den Schaltflächen im Backoffice aufgerufen (Fill, Try, Run, Playground und so weiter). Sie ist durch ein Secret geschützt, das in die Backoffice-Seiten eingebaut ist.
- Die **Cron-Adresse** wird vom Scheduler Ihres Servers aufgerufen oder von Ihnen im Browser beim Testen. Sie wird unten beschrieben.

### 4.2 Cron-Adresse

Die Adresse hat die Form Ihrer Shopadresse, gefolgt vom Modulpfad, dem Secret und der Aktion. Ersetzen Sie die Platzhalter durch Ihre eigenen Werte. Verwenden Sie das Secret, das Sie auf dem Bildschirm **Cron** sehen, und veröffentlichen Sie es nie.

Für Produkte:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent`

Für Kategorien:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent`

Die auf dem Bildschirm Cron gezeigte Adresse endet nach dem Secret (das Kategorie-Panel fügt ein anderes Ende hinzu, das der Shop nicht verwendet). Fügen Sie den Teil `action` selbst hinzu. Ohne Aktion antwortet der Shop **Invalid action!**

Der Stapel nutzt die auf dem Bildschirm Cron gespeicherten Auswahlen: Feld, Auswahlregel, Sprache, Vorlage, Stapelgröße und Debug. Jeder Aufruf aktualisiert einen Stapel und endet dann. Jeder erfolgreiche Schreibvorgang erscheint außerdem in der History mit der Methode **cron**.

Um dies auf einem Linux-Server zu planen, legen Sie einen Cron-Job an, der die Adresse abruft, zum Beispiel alle zehn Minuten:

```
*/10 * * * * curl -s "https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent" > /dev/null
```

Setzen Sie die Adresse in Anführungszeichen, weil sie ein Kaufmanns-Und enthält. Unter Windows verwenden Sie die Aufgabenplanung mit einer Aufgabe, die die Adresse öffnet. Zum Testen stellen Sie **Enable Debug** auf **Yes**, speichern und öffnen die Adresse im Browser: Die Seite gibt den Plan aus (die Parameter, die ausgewählten Produkte oder Kategorien und die endgültige Anweisung) und speichert nichts. Geben Sie diese Ausgabe nicht weiter, da sie Ihre Adressparameter enthält. Stellen Sie Debug wieder auf **No**, bevor der Scheduler die Adresse nutzt.

### 4.3 Was die Cron-Adresse antwortet

| Was Sie sehen | Was zu tun ist |
|---|---|
| **Cron Job feature is disabled. You can enable it from the module settings.** | Stellen Sie auf dem Bildschirm Cron **Enable Cron Feature** auf **Yes** und speichern Sie. |
| **The token does not exist or it's wrong!** | Das Secret fehlt oder stimmt nicht überein. Kopieren Sie das Secret erneut vom Bildschirm Cron. |
| **Invalid action!** | Der Teil `action` fehlt oder ist falsch geschrieben. Verwenden Sie eine der beiden Formen aus Abschnitt 4.2. |
| **All must include all mandatory parameters!** | Ein Wert wie Feld, Ziel, Stapelgröße, Sprache oder Vorlage ist leer. Öffnen Sie den Bildschirm Cron, füllen Sie ihn aus und speichern Sie. |
| **No valid product IDs provided.** | Die Product ID list enthält keine verwendbare Zahl. Korrigieren Sie die Liste oder leeren Sie sie und speichern Sie. |
| **No products to update.** oder **No categories to update.** | Nichts entspricht der Regel mehr. Das ist das normale Ende eines abgeschlossenen Jobs. Ändern Sie die Auswahlregel oder die Filter, um mehr zu verarbeiten. |
| **N products have been updated.** oder **N categories have been updated.** | Der Stapel ist fertig. Der Scheduler nimmt beim nächsten Aufruf den nächsten Stapel. |
| **Error!** gefolgt von einer Meldung (zum Beispiel **Monthly generation budget reached.** oder **Reply rejected by the studio quality gate.**) | Lesen Sie die Meldung und folgen Sie Kapitel 5. Der Lauf stoppt beim ersten Fehler. |
| **Error! The model returned an empty response.** | Erhöhen Sie **Max Tokens** unter Settings, Grok, oder probieren Sie ein anderes Modell. |
| **Error! Could not save product** gefolgt von einer ID | Das Produkt konnte nicht mit dem neuen Text gespeichert werden, zum Beispiel weil PrestaShop den Text abgelehnt hat. Prüfen Sie dieses Produkt und starten Sie erneut. |

## 5. Probleme

### 5.1 Die Installation wird abgelehnt

- **Symptom:** **This module requires PHP 7.0.0 or newer. This server is running PHP** gefolgt von Ihrer Version, oder **Could not create the module database tables.**
- **Ursache:** Das PHP des Servers ist zu alt, oder der Datenbankbenutzer darf keine Tabellen anlegen.
- **Was zu tun ist:** Bitten Sie Ihren Hosting-Anbieter, auf PHP 7.0 oder neuer umzustellen oder dem Datenbankbenutzer das Recht zum Anlegen von Tabellen zu geben, und installieren Sie erneut.

### 5.2 Der Menüeintrag oder der Produktblock fehlt

- **Symptom:** kein **AI Content Generator** unter **Modules** oder kein Block **My AI Grok** im Reiter **Modules** des Produkts.
- **Ursache:** ein veralteter Cache, fehlende Berechtigungen Ihres Mitarbeiterprofils oder ein deaktivierter Schalter.
- **Was zu tun ist:** Leeren Sie den Cache unter **Advanced Parameters**, **Performance**. Prüfen Sie unter **Advanced Parameters**, **Team**, **Permissions**, ob Ihr Profil die Bildschirme des Moduls öffnen darf. Fehlt das Menü weiterhin, deinstallieren Sie das Modul und installieren Sie es erneut. Für den Produktblock prüfen Sie **Product edit page Form** und **Product Edit History** unter Settings, General, und speichern Sie das Produkt einmal, damit es eine ID hat.

### 5.3 Der Schlüssel wird abgelehnt oder fehlt

- **Symptom:** **Grok API KEY field is invalid!** beim Speichern, oder **The Grok API key is not set. Add it in the module settings.** beim Erzeugen, oder nach jedem Versuch eine Fehlerzeile in der History.
- **Ursache:** Das Schlüsselfeld ist leer oder zu kurz, oder der Schlüssel wurde mit einem Tippfehler kopiert oder bei xAI widerrufen.
- **Was zu tun ist:** Öffnen Sie **Settings**, **Grok**, fügen Sie einen frischen Schlüssel von https://console.x.ai ein und drücken Sie **Save**. Öffnen Sie dann **History**, filtern Sie **Status** nach **Error** und öffnen Sie die neueste Zeile, um die genaue Antwort von Grok zu lesen.

### 5.4 Das Modell wird abgelehnt

- **Symptom:** **OpenAi Model field is invalid!**, oder Fehler in der History, die besagen, dass das Modell nicht existiert oder Sie keinen Zugriff haben.
- **Ursache:** Der Modellname ist zu kurz oder falsch geschrieben, oder Ihr xAI-Konto kann dieses Modell nicht aufrufen.
- **Was zu tun ist:** Wählen Sie unter **Settings**, **Grok** eines der eingebauten Modelle oder fügen Sie mit **Add model** die exakte ID aus Ihrem xAI-Konto hinzu und speichern Sie.

### 5.5 Der Aufruf läuft in ein Timeout

- **Symptom:** **Grok request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** oder, auf einem Bildschirm, **The request timed out or the shop blocked it.**
- **Ursache:** ein langsames Modell, eine sehr lange Antwort, ein ausgelasteter xAI-Dienst oder ein Server, der lange Anfragen blockiert.
- **Was zu tun ist:** Erhöhen Sie **API timeout (seconds)** unter **Settings**, **General** (bis 600), senken Sie **Max Tokens** für kurze Felder oder probieren Sie ein schnelleres Modell. Senken Sie bei Cron **Product to update**, damit ein Stapel in das Zeitlimit des Servers passt.

### 5.6 Die Antwort ist leer oder abgeschnitten

- **Symptom:** **The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings — reasoning models spend part of that budget on thinking.** oder **The response was blocked by the provider content filter. Try rewording the prompt.** oder **The model returned an empty response.**
- **Was zu tun ist:** Erhöhen Sie **Max Tokens** unter **Settings**, **Grok**. Formulieren Sie bei einer blockierten Antwort die Anweisung um. Versuchen Sie es dann erneut.

### 5.7 Das Monatsbudget ist erreicht

- **Symptom:** **Monthly generation budget reached. Raise it in the studio settings or wait until next month.**
- **Was zu tun ist:** Öffnen Sie **Settings**, **Studio**, erhöhen Sie **Monthly generation budget** oder setzen Sie es auf 0 und speichern Sie. Fehlgeschlagene Aufrufe werden nicht gezählt.

### 5.8 Eine Antwort wird wegen eines verbotenen Worts abgelehnt

- **Symptom:** **The reply was rejected because it contains a forbidden word from the studio settings.** (Cron zeigt **Reply rejected by the studio quality gate.**). Das Produkt bleibt unverändert, und die History zeigt eine Fehlerzeile.
- **Was zu tun ist:** Führen Sie die Generierung erneut aus (der Wortlaut unterscheidet sich jedes Mal), kürzen Sie **Forbidden words** unter **Settings**, **Studio** oder stellen Sie **Quality gate** auf **Disabled**.

### 5.9 Ein Feld wird übersprungen oder der Text ist falsch

- **Symptom:** Eine Zeile zeigt **skipped** mit **Product skipped.** (oder **Category skipped.**), oder der Text wurde an den alten Text angehängt, statt ihn zu ersetzen.
- **Ursache:** **Existing text** war auf **Skip if filled**, **Add above** oder **Add below** gestellt.
- **Was zu tun ist:** Wählen Sie **Replace** und starten Sie erneut. Um einen unerwünschten Schreibvorgang bei einem Produkt rückgängig zu machen, nutzen Sie den Reiter **History** des Produkts und drücken Sie **Restore**.

### 5.10 Cron tut nichts, wiederholt sich oder die Adresse funktioniert nicht mehr

- **Symptom:** Der Scheduler läuft, aber nichts wird geschrieben, oder dieselben Produkte werden neu geschrieben, oder eine Adresse, die gestern funktionierte, antwortet jetzt **The token does not exist or it's wrong!**
- **Cron deaktiviert:** **Cron Job feature is disabled.** Stellen Sie auf dem Bildschirm Cron **Enable Cron Feature** auf **Yes** und speichern Sie.
- **Keine Aktion in der Adresse:** Sie erhalten **Invalid action!** Fügen Sie die Aktion hinzu, wie in Abschnitt 4.2 gezeigt.
- **Debug eingeschaltet gelassen:** Debug gibt den Plan aus und speichert nie. Stellen Sie **Enable Debug** auf **No** und speichern Sie.
- **Keine Vorlage:** Ist **Prompt Template** leer, ist die gesendete Anweisung leer. Wählen Sie eine aktivierte Vorlage und speichern Sie.
- **Secret ersetzt:** Die Schaltfläche **Generate Token** neben dem Secret hat in dieser Version keine Funktion, tippen oder fügen Sie daher selbst ein langes Zufalls-Secret ein. Ein Secret, das kürzer als 24 Zeichen ist, wird beim nächsten Öffnen einer beliebigen Backoffice-Seite durch ein neues zufälliges ersetzt, und die alte Adresse funktioniert dann nicht mehr. Kopieren Sie das Secret erneut vom Bildschirm Cron.
- **Immer dieselben Produkte:** Wenn Sie **Product Categories** markieren, werden Produkte, deren Standardkategorie markiert ist, bei jedem Aufruf ausgewählt, selbst wenn die Auswahlregel sagt, dass sie nicht mehr ausstehen. Lassen Sie den Kategoriebaum leer und begrenzen Sie den Cron stattdessen mit **Product ID list**, oder nutzen Sie den Bildschirm **Generate** für kategoriebezogene Arbeit.
- **Serverfehler:** Cron-Fehler werden nur in der Antwort der Adresse ausgegeben; sie werden nicht in der History gespeichert. Rufen Sie die Adresse mit eingeschaltetem Debug im Browser auf, um sie zu lesen.

### 5.11 Ein Massenlauf bleibt auf halbem Weg stehen

- **Symptom:** Die Statuszeile bewegt sich nicht mehr, oder einige Zeilen haben kein Ergebnis.
- **Ursache:** Der Browser-Tab wurde geschlossen oder neu geladen, der Computer ging in den Ruhezustand, oder ein Aufruf lief in ein Timeout.
- **Was zu tun ist:** Drücken Sie erneut **Run**. Wählen Sie unter **Existing text** **Skip if filled**, damit fertige Felder nicht zweimal bezahlt werden. Zeilen mit einem Fehler nennen den Grund; derselbe Grund steht in der History.

### 5.12 Das Formular Generate category content tut nichts

- **Symptom:** Nach dem Drücken von **Generate content** im Formular unter der Kategorieliste landen Sie im Kategoriefilter, und nichts wird geschrieben.
- **Was zu tun ist:** Nutzen Sie die Schaltfläche **Run on the categories below** über diesem Formular. Die Schaltfläche **Module settings** auf den Filterbildschirmen für Produkte und Kategorien öffnet nicht die Einstellungen dieses Moduls; verwenden Sie den Eintrag **Settings** der Navigationsleiste.

### 5.13 Probleme mit Produktfotos (Photos)

- **Symptom:** **Find pages** zeigt keine Fotos, oder Sie sehen **No images could be imported.** mit Details.
- **Ursache:** Grok hat Seiten ohne brauchbare Fotos vorgeschlagen, die Seite hat den Download des Shops blockiert, die Adresse zeigte auf ein privates Netzwerk, oder die Datei war kein gültiges Bild.
- **Was zu tun ist:** Drücken Sie erneut **Find pages**, formulieren Sie **AI Image Search Prompt** auf dem Bildschirm **Images** um (zum Beispiel Herstellerseiten anfordern) oder laden Sie die Fotos von Hand hoch.

### 5.14 Der Bildschirm New product schlägt fehl

- **Symptom:** **Add an API key in the module settings first.**, **Prompt is required**, **Failed to parse AI response. Please try again.** oder **Failed to create product**.
- **Was zu tun ist:** Hinterlegen Sie den API-Schlüssel unter **Settings**, **Grok**, schreiben Sie ein Briefing und drücken Sie erneut **Generate data**. Erhöhen Sie **Max Tokens**, wenn die Antwort abgeschnitten wirkt. Schlägt **Create product** fehl, prüfen Sie den Entwurf auf einen leeren Namen.

### 5.15 Restore ist nicht möglich

- **Symptom:** **Error! This log entry has no previous value to restore.** oder **Error! Nothing to restore for this entry.**
- **Ursache:** Diese Zeile hat keinen früheren Wert gespeichert (zum Beispiel ein freier Prompt oder ein Feld, das leer war).
- **Was zu tun ist:** Verwenden Sie eine andere Zeile desselben Produkts oder korrigieren Sie den Text von Hand.

### 5.16 Der Bildschirm meldet, das Token sei ungültig

- **Symptom:** **Error! Invalid token!** beim Drücken einer Schaltfläche nach längerer Pause.
- **Ursache:** Die Backoffice-Seite wurde geöffnet, bevor das interne Secret des Moduls erneuert wurde.
- **Was zu tun ist:** Laden Sie die Seite neu und versuchen Sie es erneut.

### 5.17 Der Text ist kürzer als erwartet

- **Ursache:** PrestaShop begrenzt einige Felder. Das Modul kürzt einen Namen auf 128 Zeichen, eine Kurzbeschreibung auf 800, einen Meta-Titel auf 69 und eine Meta-Beschreibung auf 159.
- **Was zu tun ist:** Verwenden Sie eine knappere Anweisung, zum Beispiel indem Sie einen Titel unter 60 Zeichen verlangen.

### 5.18 Technisches Log und Debug

- **Symptom:** Sie benötigen mehr Details zu einem fehlgeschlagenen Aufruf, oder das PrestaShop-Log wächst.
- **Was zu tun ist:** Schalten Sie unter **Settings**, **General** **Debug mode** ein, wiederholen Sie die Aktion, lesen Sie die neuen Einträge unter **Advanced Parameters**, **Logs** und schalten Sie Debug wieder aus. Stellen Sie nach dem Testen auch **Enable Debug** auf dem Bildschirm Cron wieder auf **No**.

### 5.19 Update-Benachrichtigungen

- **Symptom:** **Check Now** zeigt weder **Module is up to date!** noch **New version available!**
- **Ursache:** Ihr Server kann den Update-Server von MyPresta.eu nicht erreichen, der mit einem kurzen Zeitlimit geprüft wird.
- **Was zu tun ist:** Erlauben Sie ausgehende Verbindungen oder versuchen Sie es später erneut. Das Modul funktioniert auch ohne diese Prüfung.

## 6. Für Entwickler

### 6.1 Überblick

- **Hauptklasse:** `myaigrok` (Datei `myaigrok.php`), erweitert `Module`, Version `1.1.0`, `bootstrap = true`, `need_instance = 0`.
- **Name in der Modulliste:** `My AI Grok - AI content generation`. **Autor:** `MyPresta.eu`. **Tab:** `front_office_features`.
- **Kompatibilität:** PrestaShop 1.6 bis 9.99.99 (`ps_versions_compliancy`). Mindestens PHP 7.0.0 (`MIN_PHP_VERSION`); `install()` lehnt ein älteres PHP mit einer übersetzten Meldung ab.
- **Klassen:** Der Namespace `MyAIGrok\` wird von `autoload.php` geladen (kein Composer). `MyAIGrok\OpenAIService` ist ein cURL-Client für `https://api.x.ai/v1` (`/chat/completions`, `/models`); `MyAIGrok\Studio` wendet den Hausstil, das Monatsbudget und das Quality gate an. Der Update-Prüfer `myaigrokUpdate` (in `lib/updateChecker.php`) erweitert `myaigrok`.
- **Datenfluss:** Die Einstellungen liegen in `ps_configuration` (Präfix `MYPRESTA_MYAIGROK_`). Backoffice-Schaltflächen und Massenläufe rufen den Front-Controller `ajax` auf; Scheduler rufen den Front-Controller `cron` auf. Beide lesen die Einstellungen, leiten den Prompt durch `Studio::gate()` (Budgetprüfung und `Studio::decorate()`), senden ihn mit `OpenAIService::createChatCompletion()`, prüfen die Antwort mit `Studio::inspect()`, schreiben den Text in das Produkt- oder Kategorieobjekt und fügen eine Zeile in `myaigrok_log` ein.
- **Aufrufe beim Anbieter:** Die Modellparameter `temperature`, `max_tokens`, `top_p`, `frequency_penalty`, `presence_penalty` werden gesendet; Parameter, die ein Modell ablehnt, werden gelernt und in `MYPRESTA_MYAIGROK_MODEL_CAPS` gespeichert. Die Zertifikatsprüfung wird nur abgeschaltet, wenn der Shop selbst auf localhost läuft.

### 6.2 Dateien

| Pfad | Zweck |
|---|---|
| `myaigrok.php` | Modulklasse: Installation, Deinstallation, Hooks, Settings-Bildschirme (HelperForm), Dashboard, Menüplatzierung, Reiter Modules am Produkt. |
| `autoload.php` | Klassenlader für den Namespace `MyAIGrok\`. |
| `src/OpenAIService.php` | cURL-Client für Grok: Chat Completions, Modellliste, Timeouts, Parameteranpassung. |
| `src/Studio.php` | `gate()`, `decorate()`, `inspect()`, `overBudget()`, Prompts für SEO-Paket und Alt-Texte. |
| `controllers/admin/AdminMyAIGrok.php` | Generate-Bildschirme (Produkt- und Kategoriefilter, Massenpanels). |
| `controllers/admin/AdminMyAIGrokProductCreator.php` | Bildschirm New product und seine Ajax-Aktionen. |
| `controllers/admin/AdminMyAIGrokCron.php` | Cron-Formulare. |
| `controllers/admin/AdminMyAIGrokUsage.php` | History-Bericht und -Liste. |
| `controllers/admin/AdminMyAIGrokImageFinder.php` | Bildschirm Images und Aktionen für Bildsuche und -import. |
| `controllers/admin/AdminMyAIGrokMain.php`, `AdminMyAIGrokSettings.php` | Weiterleitung auf die Konfigurationsseite des Moduls. |
| `controllers/front/ajax.php` | Generierungs-Endpunkt, der vom Backoffice genutzt wird. |
| `controllers/front/cron.php` | Cron-Endpunkt. |
| `lib/sectionHelp.php` | Inhalt des Seitenpanels Help. |
| `lib/updateChecker.php` | Update-Prüfung bei MyPresta.eu (`dev.mypresta.eu/update/get.php`; sendet Modulname, Version, Platzhalter für den Lizenzschlüssel und Shopadresse). |
| `lib/prestashop9compatibility.php` | Kompatibilitätshilfen (Token-Verschlüsselung für PS 9). |
| `lib/searchTool/` | Kleiner Autocomplete-Helfer, der auf der Konfigurationsseite geladen wird. |
| `views/templates/hook/*.tpl` | Templates für Hooks und Bildschirme (Nav, Subnav, Dashboard, Usage, Massengeneratoren, Playground, Produktreiter, Cron-Panels). |
| `views/templates/admin/product_creator.tpl` | Bildschirm New product. |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `admin-help.js`, `dashboard.js`, `chart.min.js` | Backoffice-Skripte. |
| `views/css/back.css`, `admin-nav.css`, `stats.css` | Backoffice-Stile. |
| `translations/{iso}.php` | Übersetzungsdateien (viele Sprachen). |

### 6.3 Controller

| Controller | Eltern und Route | Hinweise |
|---|---|---|
| `AdminMyAIGrokMain` | Kind des übergeordneten Reiters Modules (`AdminParentModulesSf`, sonst `AdminParentModules`, sonst `AdminModules`), Menüname **AI Content Generator** | Leitet weiter auf `AdminModules&configure=myaigrok&mds_tab=dashboard`. |
| `AdminMyAIGrokSettings` | Verstecktes Kind (`active = 0`) von Main | Leitet weiter auf `mds_tab=settings`. |
| `AdminMyAIGrok` | Verstecktes Kind von Main | `mds_sub=products` oder `categories`; Submit-Aktionen `filterProducts`, `filterCategories`. |
| `AdminMyAIGrokProductCreator` | Verstecktes Kind von Main | Ajax-Aktionen `generateProductData`, `extractImages`, `createProduct`, `generateImages` (Platzhalter). |
| `AdminMyAIGrokCron` | Verstecktes Kind von Main | Submit `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGrokUsage` | Verstecktes Kind von Main | Filter `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`; `clear_log` löscht alle Zeilen; Zeilenaktion `view`. |
| `AdminMyAIGrokImageFinder` | Verstecktes Kind von Main | Aktionen `searchImages`, `extractImages`, `saveImages`; Hosts in privaten Netzwerken abgelehnt; bis zu 5 Seiten und 24 Fotos. |

Berechtigungen sind die üblichen Reiterrechte des Backoffice für diese Controller. Jeder Admin-Controller leitet auf `AdminHome` weiter, wenn das Modul deaktiviert ist. `AdminModules` mit `configure=myaigrok` akzeptiert `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` ist der Reiter Grok) und `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`) sowie `mds_from`, `mds_to`.

**Front `ajax`** (`module/myaigrok/ajax`): verlangt `secret_token` gleich `MYPRESTA_MYAIGROK_TOKEN`, sonst `Error! Invalid token!`. Es gibt keine Mitarbeiterprüfung; das Token auf der Seite ist der einzige Schutz. Aktionen: `initiatePrompt`, `updateSettings` (schreibt die Sampling-Schlüssel), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateSeoPack`, `generateAltTexts` (keine Schaltfläche in der Oberfläche). `updateProduct` und `updateCategory` akzeptieren die `behavior`-Werte `replace`, `keep`, `keep_top`, `keep_end` und `single_product` / `single_category` (Probelauf, nichts wird gespeichert).

**Front `cron`** (`module/myaigrok/cron`): Der Konstruktor erledigt die gesamte Arbeit. Er beendet sich mit einer Meldung, wenn `ENABLE_CRON` 0 ist, und verlangt dann `secret` gleich `MYPRESTA_MYAIGROK_SECRET` oder `MYPRESTA_MYAIGROK_CAT_SECRET` (für jede Aktion wird jedes der beiden Secrets akzeptiert). `action` muss `generateProductContent` oder `generateCategoryContent` sein, sonst `Invalid action!`. Der Parameter `entity`, der in der Kategorieadresse auf dem Bildschirm Cron gezeigt wird, wird nicht gelesen. Optionale Parameter überschreiben die gespeicherten Auswahlen: für Produkte `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`; für Kategorien `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. Erlaubte Ziele: `pendingGrok`, `pendingField`, `emptyField`; ein falscher Wert antwortet `productTarget parameter is wrong! Allowed values: ...`, ein falsches Feld `updatedField parameter is wrong!`. Die Bedingung der Kategorieliste für Produkte wird als `p.id_product IN (...) OR p.id_category_default IN (...)` ohne Klammern hinzugefügt und wird daher nach SQL-Rangfolge mit den übrigen Bedingungen verknüpft (siehe Abschnitt 5.10). Cron-Fehler werden ausgegeben (echo) und die Anfrage endet; sie werden nicht in `myaigrok_log` geschrieben.

Referenzierte, aber nicht im Paket ausgelieferte Assets: `views/js/admin.js` und `views/css/admin.css` (Main- und Settings-Controller, nicht erreichbar, weil zuvor weitergeleitet wird) sowie `views/js/product_creator.js` und `views/css/product_creator.css` (Bildschirm New product; der Bildschirm nutzt `back.js`). Die Funktionen `generateTokenAndFill()` und `generateCategoryTokenAndFill()`, die von den Schaltflächen **Generate Token** aufgerufen werden, sind in keinem ausgelieferten Skript definiert. Die Schaltflächen **Module settings** auf den Filterformularen von Generate verlinken auf `configure=mychatgpt`.

### 6.4 Hooks

In `install()` registriert:

| Hook | Verhalten |
|---|---|
| `displayAdminProductsExtra` | Rendert den Block My AI Grok (`product-tab-wrapper.tpl`) im Reiter Modules des Produkts. Gibt nichts zurück, wenn sowohl `PRODUCT` als auch `PRODUCT_LOG` 0 sind. |
| `displayBackOfficeHeader` | Ruft `ensureLongSecrets()` und `placeModuleMenu()` auf, fügt CSS und JS hinzu, veröffentlicht JS-Variablen, registriert den Reiter Image Finder einmalig (`IMAGEFINDER_TAB_OK`), lädt `product-fields.js` auf Produkt- und Kategorieseiten sowie das Skript der Schaltfläche in der Produktliste. |
| `displayBackOfficeTop` | Veröffentlicht `admin_controller_url` und die IDs der gerade bearbeiteten Kategorie, CMS-Seite oder Marke und gibt den Generator der oberen Leiste zurück, wenn `TOPCTA` 1 ist. |
| `dashboardZoneTwo` | Rendert `dashboard.tpl`. Wird in `displayBackOfficeHeader` erneut registriert, falls es fehlt. |
| `displayHeader`, `displayFooter` | Registriert; die Methoden sind leer. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom`, `actionProductFormBuilderModifier` | Registriert; die Methoden geben einen leeren String oder nichts zurück. |

Das Modul überschreibt weder `enable()` noch `disable()`. Das Deaktivieren des Moduls bewirkt nur, dass seine Admin-Controller auf das Dashboard von PrestaShop weiterleiten. Die Methode `hookActionProductGridDataModifier` existiert, ist aber nicht registriert. Das Modul stellt keine eigenen Hooks bereit.

### 6.5 Overrides

Das Modul hat keine Overrides.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `{prefix}myaigrok_prompt` | `id_prompt`, `status`, `title` (128), `prompt` (text), `date_generated`. Bei der Installation mit 16 Vorlagen befüllt. |
| `{prefix}myaigrok_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, `old_`- und `new_`-Paare für name, description, description_short, meta_title, meta_description und tags, `date_updated`. Schlüssel auf `id_product` und `status`. |

Die drei Token-Spalten werden von `ensureUsageColumns()` bei der ersten Nutzung hinzugefügt, wenn einer älteren Tabelle sie fehlen. Die Deinstallation löscht beide Tabellen, alle Admin-Tabs (einschließlich des alten `AdminMyAIGrokChangelog`) und die Haupt-Konfigurationsschlüssel. Erzeugte Produkt- und Kategorietexte werden nicht angetastet.

### 6.7 Schlüssel und Übersetzungen

Alle Schlüssel beginnen mit `MYPRESTA_MYAIGROK_`. Werte nach der Installation:

| Schlüssel | Wert |
|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0, 0 |
| `TIMEOUT` | 120 (beim Speichern auf 10–600 begrenzt) |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | jeweils 1 |
| `IMAGEFINDER_PROMPT` | Standard-Prompt, der 5 Seiten-URLs als JSON-Array verlangt |
| `TOKEN`, `SECRET`, `CAT_SECRET` | Zufällige 32 Zeichen; `ensureLongSecrets()` erzeugt jedes, das kürzer als 24 Zeichen ist, neu |
| `API_KEY`, `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | einzelnes Leerzeichen, `grok-4.7`, leer, leer |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | leer |
| `BUDGET`, `QUALITY` | 0, 1 |
| `ENABLE_CRON`, `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList`, `categories` | `description`, `pendingGrok`, 5, leer, Standardsprache des Shops, leer, 0, leer, leer |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | `description`, `pendingGrok`, 5, leer, Standardsprache des Shops, 0 |
| `IMAGEFINDER_TAB_OK` | Wird nach dem ersten Laden des Backoffice gesetzt |

Die Generate-Bildschirme speichern außerdem ihre zuletzt verwendeten Filterwerte unter `MYPRESTA_MYAIGROK_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`. Die Deinstallation löscht diese nicht. Der Update-Prüfer verwendet `mypresta_updates`, `update_myaigrok` und `updatev_myaigrok`. Jedes Laden der Konfigurationsseite im Backoffice löscht die veralteten Schlüssel `GEMINI_API_KEY`, `GEMINI_MODEL` und `ACTIVE_SERVICE`.

**Übersetzungen:** Eine Sprache fügen Sie hinzu, indem Sie `translations/{iso}.php` anlegen. Modulstrings verwenden `$this->l()` und `{l s='...' mod='myaigrok'}`. Die Admin-Controller verwenden `trans()` mit Domains wie `Admin.MyAIGrok` und `Admin.MyAIGrokCron` bei PrestaShop 8 und 9 sowie das `l()` des Moduls bei 1.6 und 1.7. Diese Strings sind nicht übersetzt: in `back.js` aufgebaute Meldungen und die Fallbacks in `product-fields.js`, einfache Textantworten von Cron, Fehlertexte von Image Finder und New product sowie die von `Studio` aufgebauten englischen Prompts. Die Feldbeschreibungen (What it does / How to configure / Effect) werden von `fieldHelp()` in `myaigrok.php` und vom Wrapper `help()` in jedem Admin-Controller aufgebaut; die Texte der Massengeneratoren und des Playground liegen in den Templates; die Texte des Help-Panels stehen in `lib/sectionHelp.php`.

### 6.8 Erweitern

- Fügen Sie Prompt-Vorlagen in `myaigrok_prompt` hinzu oder bearbeiten Sie sie dort (oder auf dem Bildschirm Prompt templates); Platzhalter werden in `ajax.php` und `cron.php` ersetzt.
- Fügen Sie Modell-IDs über **Add a Grok model** hinzu; sie werden in `EXTRA_MODELS` gespeichert.
- Formen Sie die Ausgabe mit den Studio-Regeln; sie werden in `Studio::decorate()` angewendet.
- Rufen Sie den Cron-Endpunkt mit Parameter-Überschreibungen auf, um verschiedene Jobs auszuführen, ohne das gespeicherte Formular anzutasten.
- Das Frontoffice rendert kein Modul-Template, sodass das Theme nichts zu überschreiben hat.

## 7. Hilfe

Produktseite des Moduls: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html

So kontaktieren Sie den Support zum Modul:

1. Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an.
2. Gehen Sie zum Kontaktformular.
3. Wählen Sie das Thema **Support for paid modules**.
4. Beschreiben Sie, was Sie getan und was Sie gesehen haben. Fügen Sie die Versionsnummer hinzu, die neben dem Modulnamen oben auf seinen Bildschirmen steht, und, falls eine Generierung fehlgeschlagen ist, den Text des Fehlers aus der Spalte **Reply / Error** der **History**.
