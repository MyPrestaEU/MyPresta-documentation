---
title: "My ChatGPT - KI-Inhaltsgenerierung - Dokumentation und Benutzerhandbuch"
description: "Mit diesem Handbuch richten Sie OpenAI ein, erzeugen Katalogtexte mit dem bereits vorhandenen Modul und beheben Probleme, wenn eine Generierung fehlschlägt."
sidebar:
  label: "My ChatGPT - KI-Inhaltsgenerierung - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product and Category Descriptions with ChatGPT auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt/)
>
> ---


## 1. Voraussetzungen

Prüfen Sie diese Punkte, bevor Sie das Modul mit OpenAI verbinden.

- Verwenden Sie PrestaShop 1.6, 1.7, 8 oder 9 (bis 9.99.99).
- Verwenden Sie PHP 7.0 oder neuer. Das Installationsprogramm bricht bei einer älteren PHP-Version ab.
- Aktivieren Sie die PHP-Erweiterungen cURL und JSON. Jeder Aufruf an OpenAI und die Update-Prüfung nutzen cURL. Aktivieren Sie außerdem mbstring, denn die Textbereinigung in der Bildsuche und im Bildschirm für neue Produkte verwendet es.
- Nutzen Sie das optionale Feld **Optionale Quell-URL** unter **Neues Produkt** nur, wenn PHP Webseiten lesen kann (Einstellung `allow_url_fopen`) und die DOM-Erweiterung verfügbar ist. Ohne beides wird das Feld ignoriert und nur Ihr Briefing verwendet.
- Haben Sie ein eigenes OpenAI-Konto und einen API-Schlüssel von platform.openai.com. Der Schlüssel muss das gewählte Modell aufrufen dürfen. Jede Anfrage bezahlen Sie bei OpenAI. Das Modul enthält kein Guthaben.
- Erlauben Sie dem Server den Internetzugang über Port 443. Der Shop kontaktiert OpenAI bei jeder Generierung und den MyPresta.eu-Update-Server für Update-Prüfungen.
- Richten Sie auf dem Server nur dann eine geplante Aufgabe (CRON) ein, wenn die Generierung ohne Klicks laufen soll. Die Cron-Adressen tun nichts, solange der Server sie nicht aufruft.
- Es ist kein weiteres PrestaShop-Modul erforderlich.
- Planen Sie bei großen Katalogen Zeit ein. Jedes Feld in jeder Sprache ist eine eigene Anfrage an OpenAI. Ein Massenlauf über 500 Produkte mit vier Feldern und zwei Sprachen sendet 4000 Anfragen nacheinander und hält Ihren Browser-Tab beschäftigt. Beginnen Sie mit kleinen Testläufen oder nutzen Sie bei großen Katalogen Cron-Stapel.

## 2. Installation

1. Öffnen Sie **Module**, dann **Modul-Manager**.
2. Klicken Sie auf **Modul hochladen** und laden Sie die ZIP-Datei hoch.
3. Klicken Sie bei **My ChatGPT - KI-Inhaltsgenerierung** auf **Installieren**.
4. Öffnen Sie im linken Menü **Module**. Dort erscheint ein neuer Eintrag **KI-Inhaltsgenerator**. Klicken Sie darauf, um das **Dashboard** des Moduls zu öffnen. **Konfigurieren** im **Modul-Manager** führt an dieselbe Stelle.

Die Installation macht Folgendes:

- Sie fügt den Menüeintrag **KI-Inhaltsgenerator** unter **Module** hinzu. Alle anderen Bildschirme des Moduls erreichen Sie über das eigene obere Menü des Moduls; sie haben keine eigenen Menüeinträge.
- Sie legt zwei Tabellen an: eine für Prompt-Vorlagen und eine für den Verlauf jeder Generierung.
- Sie fügt 16 vorgefertigte Prompt-Vorlagen hinzu (Produktnamen, Beschreibungen, Meta-Titel, Meta-Beschreibungen und Tags). Alle sind aktiviert.
- Sie erzeugt lange geheime Werte für die internen Aufrufe des Moduls und für die beiden Cron-Adressen.
- Sie schaltet den shopweiten HTML-Filter (HTMLPurifier) aus. Beschreibungen und Kategorietexte behalten dann ihre HTML-Tags, aber derselbe Schalter ist für jeden anderen Text im Shop ausgeschaltet. Schalten Sie ihn in den Shop-Einstellungen wieder ein, wenn Sie das nicht möchten.
- Sie leert den PrestaShop-Cache nicht. Leeren Sie ihn unter **Erweiterte Parameter**, dann **Leistung**, nur wenn alte Stile oder ein alter Bildschirm sichtbar bleiben.

Wenn das Installationsprogramm „Dieses Modul erfordert PHP 7.0.0 oder neuer“ anzeigt, aktualisieren Sie zuerst PHP. Wenn es „Die Datenbanktabellen des Moduls konnten nicht erstellt werden.“ anzeigt, prüfen Sie, ob der Datenbankbenutzer Tabellen anlegen darf, und installieren Sie erneut.

Deinstallation:

- Sie entfernt die Menüeinträge, beide Tabellen (alle Prompt-Vorlagen und der gesamte **Verlauf** gehen verloren) und fast alle Moduleinstellungen, einschließlich des API-Schlüssels und der Cron-Geheimnisse.
- Sie schaltet den HTML-Filter nicht wieder ein. Schalten Sie ihn selbst ein, wenn Sie das möchten.
- Sie löscht keine Produkttexte, Kategorietexte oder Produktfotos, die das Modul erzeugt hat. Diese bleiben im Katalog.
- Sie hinterlässt einige harmlose Reste in der Shop-Konfiguration (die gespeicherte Cron-Kategorieauswahl, die letzten Filterwerte aus **Generieren** und die Werte der Update-Prüfung).
- Eine Neuinstallation erzeugt neue Geheimnisse, einen leeren Verlauf und wieder die 16 Standardvorlagen. Alte Cron-Adressen funktionieren nicht mehr, kopieren Sie sie daher erneut.

## 3. Konfiguration und Arbeit im Back Office

Öffnen Sie **Module**, dann **KI-Inhaltsgenerator**. Das obere Menü des Moduls enthält diese Einträge: **Dashboard**, **Einstellungen**, **Generieren**, **Neues Produkt**, **Cron**, **Verlauf**, **Bilder** und, rechts, **Updates**. Eine runde Schaltfläche **Hilfe** am unteren Rand jedes Modulbildschirms öffnet eine kurze Erklärung des Bildschirms, auf dem Sie sich befinden.

Die Screenshots in diesem Handbuch stammen aus dem englischen Back Office. Die Namen von Schaltflächen, Feldern und Reitern sind in diesem Handbuch auf Deutsch angegeben. In der Beschreibung jedes Screenshots steht in Klammern die englische Beschriftung vom Bildschirm.

Gehen Sie so vor:

1. Öffnen Sie **Einstellungen**, dann **ChatGPT**. Fügen Sie den OpenAI-API-Schlüssel ein und wählen Sie ein Modell. Klicken Sie auf **Speichern**.
2. Öffnen Sie optional **Studio** und legen Sie Markenstimme, Zielgruppe, Ton, Glossar, verbotene Wörter, Monatsbudget und das Qualitäts-Gate fest.
3. Öffnen Sie **Prompt-Vorlagen**. Prüfen Sie die 16 Vorlagen, bearbeiten Sie sie oder fügen Sie eigene hinzu und lassen Sie nur die aktiviert, die Ihr Team verwenden soll.
4. Erzeugen Sie Text so, wie es zur Aufgabe passt:
   - Ein Produkt: Öffnen Sie das Produkt, den Reiter **Module**, und nutzen Sie **Generieren**, **Simulieren** oder **Fotos**. Auch die kleinen Schaltflächen **Mit KI generieren** neben den Beschreibungs- und Meta-Feldern funktionieren.
   - Viele Produkte oder Kategorien auf einmal: Öffnen Sie **Generieren**, erstellen Sie mit Filtern eine Liste und drücken Sie **Ausführen**.
   - Ein neues Produkt aus einem kurzen Briefing: Öffnen Sie **Neues Produkt**.
   - Geplante Stapel ohne Klicks: Öffnen Sie **Cron** und tragen Sie die Adresse im Scheduler des Servers ein.
5. Prüfen Sie im **Verlauf** jeden Prompt, jede Antwort, jeden Fehler und die Token-Anzahl. Prüfen Sie im **Dashboard** Summen und Diagramme.

Das Modul kennt keine Bestellstatus. Eine Prompt-Vorlage ist **Aktiviert** oder **Deaktiviert**. Jeder Aufruf im **Verlauf** ist **Erfolg** oder **Fehler**. Ein Massen- oder Cron-Lauf endet, wenn das letzte Element geschrieben wurde, und der Text wird am Produkt oder an der Kategorie gespeichert, sobald jede Antwort eintrifft.

Wenn **Admin-Top-Bar-CTA** aktiviert ist, befindet sich in der oberen Leiste jeder Back-Office-Seite eine kleine Zauberstab-Schaltfläche **Mein ChatGPT**. Sie öffnet ein kleines Feld mit einer Vorlagenliste, einem Textfeld und **Generieren**. Sie funktioniert wie die **Spielwiese** (Abschnitt 3.6): Die Antwort wird im Feld angezeigt und nichts wird im Katalog gespeichert.

In der Produktliste unter **Katalog**, **Produkte**, fügt das Modul außerdem eine Schaltfläche **Mein ChatGPT** hinzu, die **Generieren** öffnet.

### 3.1 Dashboard

Öffnen Sie **KI-Inhaltsgenerator**, **Dashboard**. Diese Seite ist ein Bericht. Sie schreibt niemals Produkt- oder Kategorietexte.

![Dashboard (Dashboard)](https://mypresta.eu/docs/images/docs/mychatgpt-dashboard.webp)

- Klicken Sie auf eine Zeitraum-Schaltfläche: **Heute**, **7 Tage**, **30 Tage** (standardmäßig geöffnet), **90 Tage**, **Diesen Monat** oder **Gesamtzeit**. Oder geben Sie **Von** und **Bis** ein und klicken Sie auf **Anwenden**.
- Die Zeile **Aktiver Dienst** zeigt ChatGPT und das in **Einstellungen**, **ChatGPT** gespeicherte Modell.
- Lesen Sie die Karten **Anfragen**, **Erfolg**, **Fehler**, **Gesendete Tokens** und **Empfangene Tokens** für den gewählten Zeitraum. **Anfragen** zählt jeden im **Verlauf** gespeicherten Aufruf. **Fehler** zählt die fehlgeschlagenen. Gesendete Tokens sind die Größe Ihrer Anweisung, empfangene Tokens die Größe der Antwort.
- Lesen Sie die Diagramme **Anfragen und Fehler**, **Gesendete und empfangene Tokens** und **Anfragen nach Modell**.
- Leere Diagramme bedeuten, dass in diesem Zeitraum nichts generiert wurde. Das Ändern der Daten zeichnet nur die Seite neu. Es wird nichts gelöscht.

### 3.2 Einstellungen – Allgemein

Öffnen Sie **Einstellungen**, dann **Allgemein**. Klicken Sie nach jeder Änderung auf **Speichern**. Sie sehen „Einstellungen aktualisiert“.

![Allgemeine Einstellungen (General settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-general.webp)

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Live-Modus** | Nein | Kennzeichnet das Modul als im echten Shop laufend und nicht als Testumgebung. Schalten Sie ihn im Produktivbetrieb ein. Ausgeschaltet bleiben dieselben Werkzeuge erhalten, aber es wird signalisiert, dass dies nicht die Produktivumgebung ist. |
| **Debug-Modus** | Nein | Schreibt zusätzliche technische Details, wenn ein Aufruf an OpenAI fehlschlägt. Schalten Sie ihn nur ein, solange Sie ein Problem untersuchen. Die Details erscheinen unter **Erweiterte Parameter**, **Logs**. Kunden sehen sie nie. |
| **API-Timeout (Sekunden)** | 120 | Wie lange ein Aufruf an OpenAI dauern darf, bevor das Modul aufgibt. 120 genügt für normale Beschreibungen. Erhöhen Sie bis auf 600 bei langen Texten oder langsamen Modellen. Werte unter 10 werden auf 10 angehoben, Werte über 600 auf 600 gesenkt, und ein leerer oder nicht numerischer Wert wird zu 120. Ein kurzer Timeout schlägt schnell fehl und schreibt einen Fehler in den Verlauf. |
| **Produktbearbeitungsverlauf** | Ja | Fügt auf der Produktseite eine Liste **Verlauf** mit der Schaltfläche **Wiederherstellen** hinzu, damit Redakteure einen älteren Text zurückholen können. Ausgeschaltet blendet die Liste aus. Die Zeilen bleiben in jedem Fall im **Verlauf**. |
| **Admin-Top-Bar-CTA** | Ja | Fügt die Verknüpfung **Mein ChatGPT** zur oberen Leiste des Back Office auf jeder Seite hinzu. Ausgeschaltet entfernt nur diese Schaltfläche. Der Menüeintrag **KI-Inhaltsgenerator** bleibt. |
| **Formular der Produktbearbeitungsseite** | Ja | Zeigt das Generator-Panel (**Generieren**, **Simulieren**, **Fotos**) im Reiter **Module** des Produkts und die Schaltflächen **Mit KI generieren** neben den Beschreibungs- und Meta-Feldern. Ausgeschaltet blendet sie aus. Schalten Sie aus, wenn nur Massengenerierung und Cron genutzt werden sollen. |
| **KI-Bildfinder** | Ja | Lässt einen Redakteur das Modell nach Webseiten fragen, die wahrscheinlich Fotos des aktuellen Produkts zeigen. Eingeschaltet zeigt den Reiter **Fotos** am Produkt. Ausgeschaltet blendet ihn aus. Es wird nichts heruntergeladen, bevor jemand Fotos bestätigt. Derselbe Schalter befindet sich unter **Bilder** (Abschnitt 3.12). |
| **KI-Bildsuch-Prompt** | Langer Standardtext | Die Anweisung, die bei der Fotosuche gesendet wird. Standardmäßig verlangt sie genau fünf Seitenadressen als einfache Liste, bevorzugt Herstellerseiten, große Händler und Kataloge. Die Platzhalter `{product_name}` und `{product_description}` werden durch das aktuelle Produkt ersetzt. Behalten Sie die Aufforderung zu einer einfachen Adressliste bei. Ein präziser Prompt liefert passende Seiten, ein vager Prompt unpassende Links. Derselbe Text steht unter **Bilder**. |

### 3.3 Einstellungen – ChatGPT

Öffnen Sie **Einstellungen**, dann **ChatGPT**. Das Formular heißt **OpenAI-Einstellungen**. Jede Generierung, auch die Produkt-Schaltflächen, Massenläufe und Cron, verwendet diese Werte. Klicken Sie auf **Speichern**. Sie sehen „OpenAI-Einstellungen aktualisiert“.

![ChatGPT-Einstellungen (ChatGPT settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-chatgpt.webp)

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **OpenAI API-SCHLÜSSEL** | Leer | Das Geheimnis, mit dem dieser Shop Ihr OpenAI-Konto aufrufen darf. Fügen Sie den auf platform.openai.com in Ihrem OpenAI-Konto erstellten Schlüssel ein. Leerzeichen drumherum werden beim Speichern entfernt. Lassen Sie das Feld unberührt, um den bereits gespeicherten Schlüssel zu behalten. Ein leerer oder falscher Schlüssel lässt jede Generierung fehlschlagen, und der Fehler wird in den Verlauf geschrieben. Wenn Sie einen neuen Schlüssel mit weniger als 10 Zeichen speichern, während kein Schlüssel gespeichert ist, sehen Sie „Das Feld 'OpenAI API-SCHLÜSSEL' ist ungültig!“. |
| **Modell** | gpt-3.5-turbo | Das ChatGPT-Modell, das den Text schreibt. Die Liste enthält die eingebauten Modelle (gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4, gpt-3.5-turbo, o4-mini, o3-mini, o1-mini und weitere) und die von Ihnen hinzugefügten Modelle. Wählen Sie eines und klicken Sie auf **Speichern**. Ein Modell, das Ihr Schlüssel nicht nutzen kann, liefert statt Text einen OpenAI-Fehler. Ein leeres Modell ergibt „Das Feld 'OpenAI Modell' ist ungültig!“. |
| **ChatGPT-Modell hinzufügen** | Leer | Fügt einen Modellnamen hinzu, der nicht in der eingebauten Liste steht. Geben Sie den genauen Namen aus Ihrem OpenAI-Konto ein (zum Beispiel `gpt-4.1`) und klicken Sie auf **Modell hinzufügen**. Der Name erscheint unter **Modell** und wird zum aktiven Modell. **Entfernen** neben einem hinzugefügten Namen löscht ihn. Eingebaute Namen lassen sich nicht entfernen. Wenn Sie das aktive hinzugefügte Modell entfernen, wechselt das Modul zu gpt-4o. Meldungen: „Modell hinzugefügt.“, „Dieses Modell ist bereits integriert.“, „Modell entfernt.“, „Integrierte Modelle können nicht entfernt werden.“, „Geben Sie eine Modell-ID wie gpt-4.1 ein.“. |
| **Max. Tokens** | 3200 | Die Obergrenze für die Länge einer Antwort, gezählt in Tokens, nicht in Wörtern. Verwenden Sie etwa 256 für eine Meta-Beschreibung und 1000 oder mehr für eine vollständige HTML-Beschreibung. Zu niedrig schneidet die Antwort ab. Zu hoch erlaubt langen Text und erhöht die Kosten bei OpenAI. Ein Wert von 0 gilt als leer und wird durch 256 ersetzt. |
| **Temperatur** | 0.7 | Wie frei das Modell Wörter wählt. Bleiben Sie zwischen 0 und 1. Verwenden Sie etwa 0.2 für Spezifikationen und Meta-Texte und etwa 0.7 für Beschreibungen. Ändern Sie entweder diesen Wert oder **Top P**, nicht beide. Niedrige Werte wiederholen eine ähnliche Struktur. Hohe Werte variieren stärker und können vom Briefing abweichen. Ein Wert von 0 gilt als leer und wird durch 0.7 ersetzt. |
| **Top P** | 1 | Eine weitere Möglichkeit, zu begrenzen, wie überraschend das nächste Wort sein darf. 1 berücksichtigt den gesamten Bereich. Lassen Sie 1 stehen, wenn Sie bereits die **Temperatur** gesetzt haben. Ein niedrigerer Wert wie 0.9 ergibt einen engeren Wortschatz. Ein Wert von 0 wird durch 1 ersetzt. |
| **Frequenz-Penalty-Wert** | 0 | Verringert Formulierungen, die sich innerhalb einer Antwort wiederholen. Verwenden Sie 0, es sei denn, Beschreibungen kopieren immer wieder denselben Satz, dann probieren Sie 0.3–0.6. Zulässiger Bereich -2 bis 2. Produkte werden nicht untereinander verglichen. |
| **Präsenz-Penalty-Wert** | 0 | Lenkt die Antwort auf neue Themen. Verwenden Sie standardmäßig 0. Probieren Sie eine kleine positive Zahl, wenn jeder Absatz dasselbe sagt. Zulässiger Bereich -2 bis 2. Einige neuere Modelle ignorieren dieses Feld. |

Das Modul lernt selbstständig, welche Einstellungen ein Modell ablehnt (einige Reasoning-Modelle weisen Temperatur oder Penalties zurück), und sendet sie diesem Modell dann nicht mehr.

### 3.4 Einstellungen – Studio

Öffnen Sie **Einstellungen**, dann **Studio**. Das Studio legt Hausregeln über jeden Prompt: Produkt-Schaltflächen, Massenläufe, Cron und die Spielwiese. Leere Felder werden übersprungen. Klicken Sie auf **Studio speichern**. Sie sehen „Studio-Einstellungen gespeichert.“. Bereits im Katalog vorhandener Text wird nicht neu geschrieben.

![Studio-Einstellungen (Studio settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-studio.webp)

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Markenstimme** | Leer | Sagt dem Modell, wer spricht, damit der Text zu Ihrem Shop passt und nicht zu einem allgemeinen Assistenten. Schreiben Sie ein kurzes Briefing, zum Beispiel „Fachwerkstatt, kurze Sätze, keine Übertreibung“. Jede spätere Generierung beginnt mit dieser Stimme. |
| **Zielgruppe** | Leer | Nennt den Leser, für den geschrieben wird, zum Beispiel „professionelle Installateure“ oder „Erstkäufer“. Die Antworten verwenden Wortschatz und Beispiele, die auf diesen Leser zugeschnitten sind. |
| **Ton** | Leer | Die Stimmung der Formulierung: formell, warm, technisch. Ein oder zwei Wörter genügen. Das ändert weder das Modell noch die Temperatur. |
| **Glossar** | Leer | Markennamen, Materialien und Schreibweisen, die das Modell genau übernehmen muss. Tragen Sie einen Begriff pro Zeile ein. Neuer Text bevorzugt diese Schreibweisen. Nicht aufgeführte Begriffe können weiterhin umformuliert werden. |
| **Verbotene Wörter** | Leer | Wörter und Wendungen, die in einer gespeicherten Antwort nicht vorkommen dürfen. Eine pro Zeile. Die Liste wirkt nur, wenn das **Qualitäts-Gate** eingeschaltet ist. Eine Antwort, die eine der Zeilen enthält (auch innerhalb eines längeren Wortes), wird abgelehnt, nicht ins Produkt geschrieben und im Verlauf als Fehler gespeichert. |
| **Monatliches Generierungsbudget** | 0 | Die höchste Zahl erfolgreicher Generierungen, die der Shop im laufenden Kalendermonat ausführen darf. Geben Sie eine ganze Zahl ein. 0 bedeutet keine Begrenzung. Der Zähler beginnt am ersten Tag des Monats von vorn. Ist die Obergrenze erreicht, stoppen neue Generierungen mit einer Budget-Meldung. Fehlgeschlagene Aufrufe werden nicht gezählt. Spielwiese, Produkt-Schaltflächen, Massenläufe und Cron zählen alle. |
| **Qualitäts-Gate** | Ja | Prüft jede Antwort gegen die **Verbotenen Wörter**, bevor etwas gespeichert wird. Eingeschaltet blockiert eine passende Antwort. Ausgeschaltet speichert die Antwort auch dann, wenn sie ein aufgeführtes Wort enthält. |

### 3.5 Einstellungen – Prompt-Vorlagen

Öffnen Sie **Einstellungen**, dann **Prompt-Vorlagen**. Eine Vorlage ist eine gespeicherte Anweisung, die Redakteure per Titel auswählen, statt jedes Mal dasselbe Briefing zu tippen. Der Titel ist nur eine Beschriftung für das Dropdown. Das Modell erhält den Prompt-Text. Aktivierte Vorlagen erscheinen im Produkt-Panel, im Massengenerator und im Cron-Formular. Deaktivierte bleiben in der Liste, werden aber nicht angeboten (das Cron-Formular listet sie weiterhin auf, wählen Sie daher eine aktivierte).

![Prompt-Vorlagen (Prompt templates)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-templates.webp)

Die Liste **Prompt-Vorlagen** zeigt **ID**, **Titel**, **Prompt**, **Status** und **Zeitstempel**, neueste zuerst, 50 pro Seite.

- Klicken Sie auf die grüne Schaltfläche **+**, um eine Vorlage zu erstellen.
- Klicken Sie in einer Zeile auf das Statuszeichen, um eine Vorlage zwischen aktiviert und deaktiviert umzuschalten.
- Nutzen Sie **Bearbeiten** oder **Löschen** in einer Zeile. Markieren Sie mehrere Zeilen und nutzen Sie die Sammelaktion **Löschen** (Sie müssen „Sind Sie sicher, dass Sie die ausgewählten Prompts löschen möchten?“ bestätigen).

Das Formular **Prompt-Vorlage generieren**:

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Status** | Deaktiviert bei einer neuen Vorlage | Zeigt oder verbirgt diese Vorlage in den Dropdowns auf der Produktseite, in der Massengenerierung und im Cron. Aktivieren Sie Vorlagen, die Ihre Mitarbeiter nutzen sollen. Deaktivieren Sie einen Entwurf, statt ihn zu löschen. |
| **Prompt-Titel** | Leer (erforderlich) | Der Name, den Redakteure im Dropdown sehen, zum Beispiel „HTML-Beschreibung mit Merkmalen“. Er wird nicht an das Modell gesendet. |
| **Prompt-Inhalt** | Leer (erforderlich) | Die an das Modell gesendete Anweisung. Schreiben Sie sie so, wie Sie einen Texter briefen würden: Länge, HTML, Sprache. Platzhalter werden aus dem Element gefüllt, das geschrieben wird. Doppelte Anführungszeichen werden beim Speichern in einfache umgewandelt. |

Klicken Sie auf **Prompt speichern**. Sie sehen „Prompt-Vorlage erfolgreich hinzugefügt!“ oder „Prompt-Vorlage erfolgreich aktualisiert!“. **Zurück zu den Moduleinstellungen** führt zur Liste zurück. Beim Löschen sehen Sie „Prompt-Vorlage entfernt.“.

Platzhalter, die Sie in einer Vorlage verwenden können:

| Für | Platzhalter | Ersetzt durch |
|---|---|---|
| Produkte | `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}`, `{product_reference}`, `{product_ean13}`, `{product_weight}` | Der Wert dieses Produkts in der Sprache, in der geschrieben wird. |
| Produkte | `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Die Marken- und Kategoriedaten des Produkts. |
| Produkte | `{product_attributes}`, `{product_features}`, `{product_feature_values}`, `{product_images}` | Kommagetrennte Attribute, Merkmalsnamen, Paare aus Merkmalsname:Wert und Fotoadressen des Produkts. |
| Kategorien | `{category_name}`, `{category_description}`, `{category_parent_name}` | Die Kategorie und ihre übergeordnete Kategorie. |
| Produkte und Kategorien | `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Ihre Shop-Daten. |

Die 16 Standardvorlagen sind **Produktname 1–2**, **Produktbeschreibung 1–7**, **Produkt-Meta-Titel 1–3**, **Produkt-Meta-Beschreibung 1–3** und **Produkt-Tags**. Einige enthalten Beispielformulierungen (zum Beispiel eine Smartwatch). Prüfen Sie sie vor dem ersten Massenlauf.

### 3.6 Einstellungen – Spielwiese

Öffnen Sie **Einstellungen**, dann **Spielwiese**. Die Spielwiese ist ein Notizblock, der das aktive Modell aufruft und die Antwort auf der Seite anzeigt. Nutzen Sie sie, um einen Prompt auszuprobieren, bevor Sie ihn als Vorlage speichern, oder um zu prüfen, ob Ihr API-Schlüssel funktioniert.

![Spielwiese (Playground)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-playground.webp)

1. Geben Sie eine Anweisung in das Feld ein. Der graue Hinweis lautet „Fragen Sie das Modell alles über Ihren Katalog“.
2. Klicken Sie auf **Generieren**.
3. Lesen Sie die Antwort und die Token-Anzahl unter der Schaltfläche.

Der Aufruf verwendet das Modell, die Sampling-Werte und die Studio-Regeln, die Sie gespeichert haben. Die Antwort wird im Verlauf gespeichert. Kein Produkt, keine Kategorie und kein Meta-Feld wird geändert. Schreiben Sie echte Namen und Details: Platzhalter in geschweiften Klammern werden auf der Spielwiese nicht gefüllt.

### 3.7 Generieren – Produkte

Öffnen Sie **Generieren**, dann den Unterreiter **Produkte**. Arbeiten Sie in zwei Schritten. Schritt 1 erstellt nur eine Liste. Es wird nichts an OpenAI gesendet und nichts als Shop-Einstellung gespeichert.

![Produkte generieren (Generate products)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-products.webp)

Schritt 1 – das Formular **Zu aktualisierende Produkte filtern**. Alle Filter werden kombiniert. Ein leer gelassener Filter wird ignoriert.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Produktkategorien** | Nichts markiert | Behält Produkte aus den markierten Kategorien (auch Produkte, deren Standardkategorie eine davon ist). Ein leerer Baum schaltet diesen Filter aus. |
| **Marke** | Marke auswählen | Behält Produkte eines Herstellers. Die leere Option umfasst jede Marke. |
| **Produktstatus** | Aktiv | **Aktiv** behält Produkte im Verkauf, **Deaktiviert** behält Entwürfe, **Beide** behält alle. |
| **Produktbestand** | Alle Produkte | **Nur Produkte auf Lager** entfernt Produkte ohne verfügbare Menge. **Alle Produkte** ignoriert den Bestand. |
| **Nur aktualisieren** | Alles aktualisieren | **Produkte, die noch nicht mit OpenAI-Inhalten aktualisiert wurden** dient dem ersten Durchgang (Produkte ohne Zeile im Verlauf). **Produkte, die bereits mit OpenAI-Inhalten aktualisiert wurden** dient dem Überschreiben. **Alles aktualisieren** ignoriert den Verlauf. |
| **Produkt-IDs** | Leer | Nur diese Produktnummern, durch Kommas getrennt, zum Beispiel 12,45,103. |
| **Produktreferenz** | Leer | Nur Produkte mit diesen Referenzcodes, durch Kommas getrennt. |
| **Produkt hinzugefügt ab** | Leer | Lässt Produkte aus, die vor diesem Datum und dieser Uhrzeit erstellt wurden. |
| **Produkt hinzugefügt bis** | Leer | Lässt Produkte aus, die nach diesem Datum und dieser Uhrzeit erstellt wurden. |
| **Minimale Produkt-ID** | Leer | Überspringt Produkte mit kleinerer Nummer. |
| **Maximale Produkt-ID** | Leer | Überspringt Produkte mit größerer Nummer. |
| **Produktlimit** | Leer | Die höchste Zahl an Produkten, die in die Liste geladen werden, zum Beispiel 20. Die Liste zeigt nie mehr, sodass ein Lauf nicht versehentlich den ganzen Katalog durchläuft. |

Klicken Sie auf **Weiter zum nächsten Schritt**. **Moduleinstellungen** öffnet die Modulkonfiguration.

Schritt 2 – das Panel **Massenproduktgenerierung** und die Produkttabelle (**ID**, **Referenz**, **Ergebnis**):

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Vorlage** | Vorlage auswählen | Füllt das Prompt-Feld aus einer aktivierten Vorlage. Sie können auch einen eigenen Prompt eintippen. Der Titel wird nicht gesendet. Bleibt das Feld leer, verwendet das Modul für jedes Feld ein Standard-Briefing. |
| Prompt-Feld | Leer | Die Anweisung für jedes Produkt in der Tabelle. Wenn Sie einen Text eingeben, wird derselbe Text für jedes gewählte Feld verwendet. Führen Sie daher ein Feld nach dem anderen aus, wenn die Felder unterschiedliche Formulierungen brauchen. |
| **Was generiert werden soll** | Beschreibungen | **Beschreibungen** schreibt die lange und die kurze Beschreibung. **Meta-Titel und Meta-Beschreibung** schreibt beide Meta-Felder. **Beschreibungen und Meta zusammen** schreibt alle vier. Jedes Feld ist eine eigene Anfrage. Namen und Tags werden von der Produktseite aus geschrieben, nicht von hier. |
| **Bestehender Text** | Ersetzen | **Ersetzen** überschreibt. **Überspringen, wenn gefüllt** lässt ein gefülltes Feld unangetastet und ruft das Modell dafür nicht auf. **Darüber hinzufügen** und **Darunter hinzufügen** behalten den alten Text und hängen den neuen an. |
| **Sprachen** | Ihre aktuelle Sprache markiert | Markieren Sie jede Sprache, die geschrieben werden soll. Jede markierte Sprache wird einzeln generiert. Nicht markierte Sprachen behalten ihren Text. |

Klicken Sie auf **Auf der Liste unten ausführen**. Die Statuszeile zeigt den Fortschritt, zum Beispiel „3 / 40 – description“. Jede Zeile zeigt ihre eigenen Ergebnisse, sobald das Produkt fertig ist, zum Beispiel „description: success Content successfully generated and updated to product.“, „description_short: skipped Product skipped.“ oder „meta_title: error …“ mit der Ursache. Am Ende sehen Sie „Finished N products.“. Ohne markierte Sprache sehen Sie „Select at least one language.“.

Lassen Sie den Browser-Tab bis zum Ende des Laufs geöffnet. Schließen stoppt den Lauf, und bereits geschriebene Produkte bleiben gespeichert. Um fortzufahren, erstellen Sie die Liste erneut, wobei **Nur aktualisieren** auf noch nicht aktualisierte Produkte steht. Ein Fehler bei einem Feld macht bereits gespeicherte Felder nicht rückgängig. Beginnen Sie mit einem kleinen **Produktlimit**, etwa 20, und prüfen Sie zuerst die Formulierungen.

### 3.8 Generieren – Kategorien

Öffnen Sie **Generieren**, dann den Unterreiter **Kategorien**. Die beiden Schritte funktionieren wie im Produktbildschirm.

![Kategorien generieren (Generate categories)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-categories.webp)

Schritt 1 – das Formular **Zu aktualisierende Kategorien filtern**:

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Kategorien** | Nichts markiert | Wählt die Kategorien für den nächsten Schritt. Ein leerer Baum schränkt die Liste nicht nach Kategorie ein, die Liste enthält dann jede Kategorie mit dem gewählten Status, auch **Startseite** und die Stammkategorie. Markieren Sie die gewünschten Kategorien. |
| **Kategoriestatus** | Aktiv | **Aktiv**, **Deaktiviert** oder **Beide**. |

Klicken Sie auf **Weiter zum nächsten Schritt**.

Schritt 2 – das Panel **Massen-Kategoriegenerierung** und die Kategorietabelle (**ID**, **Ergebnis**):

| Feld | Standard | Was es bewirkt |
|---|---|---|
| Prompt-Feld (erstes Feld) | Leer | Die Anweisung, die für jede Kategorie gesendet wird. Beschreiben Sie Ton, Länge und HTML. Nennen Sie das Thema im Text. Dieses Feld fügt keine Produkt-Platzhalter ein. Dieses Panel hat keine Vorlagenauswahl. |
| Feldliste | Beschreibung | Das zu schreibende Feld: **Beschreibung**, **Name**, **Meta-Titel**, **Meta-Beschreibung** oder **Zusätzliche Beschreibung**. Nur dieses Feld wird gespeichert. |
| Liste für bestehenden Text | Ersetzen | **Ersetzen** überschreibt. **Überspringen, wenn gefüllt** lässt ein gefülltes Feld unangetastet und ruft das Modell für diese Kategorie nicht auf. |
| Sprachliste | Ihre aktuelle Sprache | Eine Sprache. Führen Sie den Lauf für eine weitere Sprache erneut aus. |

Klicken Sie auf **Auf den Kategorien unten ausführen**. Die Ergebnisse erscheinen pro Zeile wie im Produktbildschirm. Eine Kategorie ohne das Feld **Zusätzliche Beschreibung** in Ihrer PrestaShop-Version zeigt „Error! This PrestaShop version does not support the category Additional Description field.“.

Unter der Tabelle zeigt der Bildschirm außerdem das Formular **Kategorieinhalt generieren**. Seine Einleitung lautet „This form writes the filtered categories. Press Generate content to start. Each category is saved as soon as its reply arrives.“ In dieser Version startet dieses Formular keinen Lauf. Nutzen Sie **Auf den Kategorien unten ausführen** darüber. Das Formular hat diese Felder:

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Zu aktualisierendes Feld** | Beschreibung | Das Kategoriefeld, das dieses Formular neu schreiben würde: **Kategoriename**, **Beschreibung**, **Meta-Titel**, **Meta-Beschreibung** oder **Zusätzliche Beschreibung**. Nur dieses Feld wird an das Modell gesendet und gespeichert. Die anderen Felder bleiben unverändert. Beschreibung und Meta sind getrennte Läufe. |
| **Bestehende Daten** | Bestehende Daten behalten und neuen generierten Inhalt oben hinzufügen | Was passiert, wenn das gewählte Feld bereits Text hat: **Bestehende Daten behalten und neuen generierten Inhalt oben hinzufügen**, **Bestehende Daten behalten und neuen generierten Inhalt am Ende hinzufügen**, **Bestehende Daten behalten und Kategorie überspringen** oder **Daten entfernen und neuen generierten Inhalt hinzufügen**. Ersetzen ändert den gespeicherten Text. Überspringen ruft das Modell für eine Kategorie, die dieses Feld schon hat, nicht auf. Hinzufügen behält beide Versionen in einem Feld. |
| **Sprache** | Erste Sprache in der Liste | Die Sprachversion, die geschrieben wird. Nur diese Sprache ändert sich. |
| **Inhalts-Prompt** | Leer (erforderlich) | Die Anweisung für jede Kategorie in der Liste. Beschreiben Sie Ton, Länge und HTML. Nennen Sie das Kategoriethema im Text, da Produkt-Platzhalter nicht eingefügt werden. |
| **API-Aufrufverzögerung** | Leer | Eine Pause in Sekunden zwischen einer Kategorie und der nächsten, damit das Ratenlimit von OpenAI nicht erreicht wird. Verwenden Sie 1 oder 2 bei einem Schlüssel der unteren Stufe. Setzen Sie 0, um die nächste Anfrage sofort zu senden. Das Panel **Ausführen** darüber nutzt diese Pause nicht. |

Die Schaltflächen **Inhalt generieren** und **Zurück zum Kategoriefilter** erzeugen keinen Text. **Inhalt generieren** speichert nur die eingegebenen Werte und zeigt den Filter erneut an. **Moduleinstellungen** öffnet die Modulkonfiguration.

### 3.9 Neues Produkt

Öffnen Sie **Neues Produkt**. Das Panel **Produkt aus einem Briefing erstellen** bittet das Modell um einen Produktentwurf und kann diesen Entwurf als neues Produkt einfügen. Es ist für Produkte gedacht, die noch nicht im Katalog sind. Um ein bestehendes Produkt zu füllen, nutzen Sie **Generieren** oder die Produktseite.

![Neues Produkt (New product)](https://mypresta.eu/docs/images/docs/mychatgpt-new-product.webp)

Ist kein Schlüssel gespeichert, sehen Sie „Fügen Sie zuerst einen API-Schlüssel in den Moduleinstellungen hinzu.“.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Was ist das Produkt?** | Leer (erforderlich) | Das Briefing, das das Modell zu Name, Beschreibungen, Meta, Tags, Merkmalen, Referenz und Preis ausbaut. Schreiben Sie einige Sätze mit Material, Zielgruppe und Namen, die erhalten bleiben müssen. Ein leeres Feld wird mit „Prompt is required“ abgelehnt. |
| **Optionale Quell-URL** | Leer | Eine vollständige Webadresse einer öffentlichen Seite über das Produkt. Eine lesbare Seite fügt ihren Titel, ihre Beschreibung und ihren Preistext zum Briefing hinzu. Eine nicht lesbare Seite wird ignoriert. |
| **Sprache** | Standardsprache des Shops | Die Sprache, in der der Text gespeichert wird. Andere Sprachen werden nicht gefüllt. Wählen Sie die Standardsprache Ihres Shops, denn PrestaShop braucht einen Namen in der Standardsprache, um ein Produkt anzulegen. |
| **Standard-Kategorie-ID** | 2 | Die Kategorienummer aus **Katalog**, **Kategorien**. 2 ist meist **Startseite**. Das Produkt wird in diese Kategorie gelegt und sie wird zur Standardkategorie. |

1. Klicken Sie auf **Daten generieren**. Der Entwurf erscheint als Text im Feld darunter (Name, Beschreibung, Kurzbeschreibung, Meta-Titel, Meta-Beschreibung, Schlüsselwörter, Tags, Referenz, Preis, Merkmale). Noch wird nichts gespeichert. Klicken Sie erneut für einen neuen Entwurf. Den Entwurf können Sie in diesem Bildschirm nicht bearbeiten.
2. Prüfen Sie den Entwurf, besonders den vorgeschlagenen Preis und die Referenz.
3. Klicken Sie auf **Produkt erstellen**. Die Ergebniszeile zeigt „Product #“ und die neue Produktnummer.

Das neue Produkt ist aktiv, bestellbar, im Katalog und in der Suche sichtbar, im Zustand neu, mit der Steuerregelgruppe Nummer 1, einem Bestand von 100 Stück und dem vorgeschlagenen Preis. Name, Beschreibungen, Meta, Tags und Merkmale werden nur in der gewählten Sprache gespeichert. Dieser Bildschirm fügt keine Fotos hinzu. Öffnen Sie das neue Produkt, Reiter **Module**, **Fotos**, um sie hinzuzufügen. Prüfen Sie Preis, Steuer, Menge und Kategorie, bevor Sie veröffentlichen. Die Generierung hier wird nicht im Verlauf protokolliert und zählt nicht zum Monatsbudget.

### 3.10 Cron

Öffnen Sie **Cron**. Cron ist für den Server gedacht, nicht für eine Person, die auf **Ausführen** klickt. Dieser Bildschirm speichert Ihre Auswahl und zeigt die geheimen Adressen, die Ihr Server nach Zeitplan aufruft. Jeder echte Aufruf schreibt einen kleinen Stapel und hört auf. Der Shop tut nichts, bis der Server die Adresse anfordert.

![Cron (Cron)](https://mypresta.eu/docs/images/docs/mychatgpt-cron.webp)

Das obere Panel **Kategorie-Cron** und das Panel **Cron-Parameter** zeigen die Adressen Ihres Shops mit den Geheimnissen. Behandeln Sie die Geheimnisse wie Passwörter: Veröffentlichen Sie nie eine vollständige Adresse. Dieses Handbuch zeigt sie als `YOUR_SECURE_KEY`, zum Beispiel `https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY`. An jede Adresse müssen die Einstellungen aus dem Formular angehängt werden (Feld, Sprache, Vorlage, Stapelgröße und so weiter). Abschnitt 6.3 listet sie auf. Bitten Sie Ihren Entwickler oder Hoster, sie bei der Einrichtung des Schedulers hinzuzufügen.

Produktformular **CRON JOB Settings – Generate product content using OpenAI**. Klicken Sie nach einer Änderung auf **Speichern**.

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Cron-Funktion aktivieren** | Nein | Erlaubt dem Server, Produkt- und Kategorietexte nach Zeitplan zu erzeugen. Schalten Sie sie erst ein, wenn Geheimnis, Feld, Sprache und Vorlage gespeichert sind. Solange sie aus ist, antwortet jede Cron-Adresse, dass die Funktion deaktiviert ist. Dieser eine Schalter ist auch für den Kategorie-Cron erforderlich. |
| **Geheimer Cron-Job-Token** | Langer Zufallswert | Ein langes Passwort, das Teil der Produkt-Cron-Adresse sein muss. Ohne es lehnt der Shop den Aufruf ab. Behalten Sie den erzeugten Wert. Eine Änderung macht die alte Adresse sofort ungültig. Die Schaltfläche **Token generieren** erzeugt in dieser Version keinen neuen Wert, behalten Sie also den bei der Installation erzeugten Wert. |
| **Zu aktualisierendes Feld** | description | Das einzelne Produktfeld, das dieser Cron schreibt: name, description, description_short, meta_title, meta_description oder tags. Um mehrere Felder zu füllen, legen Sie mehrere Cron-Befehle an. |
| **Ausgewählte Produkte** | pendingOpenAI | Bestimmt, welche Produkte noch warten. **pendingOpenAI**: Produkte, die das Modul noch nicht geschrieben hat (irgendein Feld). **pendingField**: Produkte, die für dieses bestimmte Feld noch nicht geschrieben wurden, sodass mehrere Befehle (zum Beispiel description und name) an denselben Produkten arbeiten können. **emptyField**: nur Produkte, bei denen das gewählte Feld leer ist. Jeder Lauf überspringt Produkte, die nicht mehr passen, sodass ein fertiger Katalog sich nicht mehr ändert. |
| **Produktkategorien** | Nichts markiert | Beschränkt den Lauf auf die markierten Kategorien. Ein leerer Baum bedeutet, dass die Kategorie kein Filter ist. |
| **Liste der Produkt-IDs** | Leer | Beschränkt den Lauf auf diese Produktnummern, durch Kommas getrennt. Buchstaben und andere Zeichen werden beim Speichern entfernt. |
| **Sprache** | Standardsprache des Shops | Die Sprachversion, die geschrieben wird. Andere Sprachen brauchen einen eigenen Befehl. |
| **Zu aktualisierende Produkte** | 5 Produkte | Wie viele passende Produkte ein Aufruf verarbeitet (2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 oder 1000). Beginnen Sie mit 5 oder 10, damit ein langsames Modell das Zeitlimit des Servers nicht überschreitet. |
| **Prompt-Vorlage** | Erste Vorlage in der Liste | Die gespeicherte Anweisung, die für jedes Produkt im Lauf verwendet wird. Platzhalter werden pro Produkt gefüllt. Wählen Sie eine aktivierte Vorlage. |
| **Debug aktivieren** | Nein | Wenn die Adresse mit eingeschaltetem Debug geöffnet wird, gibt sie den Plan aus (Einstellungen, ausgewählte Produkte, endgültige Prompts) und schreibt nichts. Prüfen Sie einen Befehl damit einmal. Schalten Sie es aus, bevor der Scheduler die Adresse nutzt. |
| **Cron-Job-Intervall** | Jede Stunde | Der geplante Rhythmus (alle 1, 2, 5, 10 oder 30 Minuten, jede Stunde, alle 2 oder alle 6 Stunden). Er dokumentiert Ihren Plan. Das Modul startet den Scheduler nicht. |
| **Cron-Job-Befehl für Produkte** | – | Zeigt die Befehlszeile, die in den Scheduler kopiert wird. Speichern Sie zuerst das Formular. |

Kategorieformular **CRON JOB Settings – Generate category content using OpenAI**. Es hat ein eigenes Geheimnis und eine eigene Schaltfläche **Speichern** und braucht keinen eigenen Aktivierungsschalter:

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Geheimer Cron-Job-Token** | Langer Zufallswert | Das Passwort der Kategorie-Adresse. Es ist vom Produkt-Geheimnis getrennt. Eine Änderung macht die alte Kategorie-Adresse ungültig. |
| **Zu aktualisierendes Feld** | description | Das einzelne geschriebene Kategoriefeld: name, description, meta_title oder meta_description. |
| **Ausgewählte Kategorien** | pendingOpenAI | Dieselben drei Regeln wie bei Produkten, auf Kategorien angewendet. **pendingField** lässt mehrere Befehle dieselben Kategorien teilen. |
| **Sprache** | Standardsprache des Shops | Die Sprachversion, die geschrieben wird. |
| **Zu aktualisierende Kategorien** | 5 Kategorien | Wie viele Kategorien ein Aufruf verarbeitet (2 bis 1000). |
| **Prompt-Vorlage** | Erste Vorlage in der Liste | Schreiben Sie die Vorlage für eine Kategorie, nicht für ein Produkt, zum Beispiel mit `{category_name}`. |
| **Debug aktivieren** | Nein | Gibt den Plan aus und speichert keine Kategorien. |
| **Cron-Job-Intervall** | Jede Stunde | Der geplante Rhythmus. |
| **Cron-Job-Befehl für Kategorien** | – | Die Befehlszeile, die nach dem Speichern kopiert wird. |

Der Kategorie-Cron fasst **Startseite** und die Stammkategorie nie an.

### 3.11 Verlauf

Öffnen Sie **Verlauf**. Der Verlauf ist das Protokoll dessen, was angefragt wurde und was zurückkam. Das Öffnen oder Filtern der Seite löscht nichts und ändert kein Produkt.

![Verlauf (History)](https://mypresta.eu/docs/images/docs/mychatgpt-history.webp)

Die Filterleiste öffnet sich auf **Diesen Monat**. Nutzen Sie die Zeitraum-Schaltflächen **Heute**, **7 Tage**, **30 Tage**, **Diesen Monat** und **Gesamtzeit** oder **Von** und **Bis**. Sie können auch nach **Modell**, **Typ**, **Status** (**Beliebig**, **Erfolg**, **Fehler**), **Sprache**, **Mitarbeiter**, **Produkt-/Kategorie-ID** und **Prompt oder Antwort enthält** eingrenzen. Klicken Sie auf **Filtern**.

- Die Karten zeigen **Anfragen**, **Erfolg**, **Fehler**, **Gesendete Tokens**, **Empfangene Tokens**, **Tokens gesamt** und **Durchschnittliche Zeit** für den Filter. Ein Strich bedeutet, dass OpenAI für diesen Aufruf keine Token-Anzahl geliefert hat.
- Die Panels **Nach Tag**, **Nach Modell**, **Nach Typ**, **Nach Sprache** und **Nach Mitarbeiter** gruppieren dieselben Zeilen nach **Gruppe**, **Aufrufe**, **Gesendet**, **Empfangen** und **Gesamt**. Eine kleine kursive Zahl neben den Aufrufen ist die Anzahl der Fehler.
- Die Liste **Prompt-Verlauf** hat die Spalten **ID**, **Status**, **Prompt**, **Antwort / Fehler**, **Anbieter** (Modell, Fehlercode, Sekunden), **Gesendet**, **Empfangen**, **Gesamt**, **Objekt-ID**, **Typ** und **Zeitstempel**. Prompt und Antwort sind gekürzt. Klicken Sie in einer Zeile auf **Ansehen**, um den vollständigen Prompt und die vollständige Antwort mit den Tokens zu lesen, dann auf **Zurück zur Liste**. Eine Fehlerzeile zeigt den Fehlertext statt einer Antwort. **Typ** zeigt, was geschrieben wurde, zum Beispiel product_description oder category_meta_title. Auch Simulationen und die Spielwiese erzeugen Zeilen.
- Die Schaltfläche **Liste leeren** löscht alle Zeilen auf einmal, ohne Rückfrage, auch Zeilen außerhalb Ihres Filters. Danach beginnen die Zähler im **Dashboard**, der Filter **Nur aktualisieren**, die Regel **pendingOpenAI** und der Zähler des Monatsbudgets bei null, und **Wiederherstellen** ist für alte Texte nicht mehr möglich.

### 3.12 Bilder

Öffnen Sie **Bilder**. Diese Seite lädt keine Bilder herunter. Sie schaltet die Bildsuche auf der Produktseite ein oder aus und speichert die dafür verwendete Anweisung.

![Bilder (Images)](https://mypresta.eu/docs/images/docs/mychatgpt-images.webp)

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **KI-Bildfinder** | Aktiviert | **Aktiviert** zeigt den Reiter **Fotos** auf der Produktbearbeitungsseite. **Deaktiviert** entfernt ihn. Ein Bild wird erst importiert, nachdem jemand es bestätigt hat. |
| **KI-Bildsuch-Prompt** | Derselbe lange Standardtext wie unter **Allgemein** | Die Anweisung, die bei der Suche gesendet wird. `{product_name}` und `{product_description}` werden durch das aktuelle Produkt ersetzt. Behalten Sie die Aufforderung zu einer einfachen Liste von Seitenadressen bei. |

Klicken Sie auf **Speichern**. Sie sehen „Einstellungen gespeichert.“. Die Suche nach Seiten und der Import von Fotos sind in Abschnitt 3.13 beschrieben.

### 3.13 Produktbearbeitung (Reiter Module)

Öffnen Sie **Katalog**, **Produkte**, bearbeiten Sie ein Produkt und öffnen Sie den Reiter **Module**. Das Panel **Mein ChatGPT** hat die Reiter **Generieren**, **Simulieren**, **Fotos** und **Verlauf**. Ist **Formular der Produktbearbeitungsseite** ausgeschaltet, bleibt nur **Verlauf**. Ist auch **Produktbearbeitungsverlauf** ausgeschaltet, erscheint nichts. Speichern Sie ein neues Produkt einmal, bevor Sie generieren, damit es eine Nummer hat.

![Produktbearbeitung (Product edit)](https://mypresta.eu/docs/images/docs/mychatgpt-product-edit.webp)

**Generieren** schreibt ein Feld und speichert es sofort am Produkt.

1. Wählen Sie einen Chip **Sprache** oder **Jede Sprache**.
2. Wählen Sie unter **Wenn das Feld bereits Text enthält** **Ersetzen**, **Darüber hinzufügen**, **Darunter hinzufügen** oder **Überspringen, wenn gefüllt**.
3. Klicken Sie auf einer Feldkarte auf **Füllen**: **Beschreibung** (langer Text mit kurzer Einleitung und Merkmalsliste), **Kurzbeschreibung** (einfache Zusammenfassung unter etwa 400 Zeichen), **Name**, **Meta-Titel** (etwa 70 Zeichen), **Meta-Beschreibung** (etwa 160 Zeichen) oder **Tags** (durch Kommas getrennte Wörter).
4. **SEO-Paket** mit **Alle füllen** schreibt Name, beide Beschreibungen und beide Meta-Felder in einem Zug. Es ersetzt diese Felder unabhängig davon, was Sie unter **Wenn das Feld bereits Text enthält** gewählt haben.
5. Optional: Öffnen Sie **Verwenden Sie Ihre eigene Anweisung oder einen gespeicherten Prompt**. Tippen Sie in **Nach Titel oder Text filtern**, wählen Sie **Standard-Briefing** (ein fertiges Briefing für das Feld, das Sie drücken) oder eine aktivierte Vorlage, oder schreiben Sie Ihre eigene **Anweisung**.

Unter den Schaltflächen sehen Sie die gesendete Anweisung und die Antwort sowie „Content successfully generated and updated to product.“. Das Produktformular auf dem Bildschirm wird nicht aktualisiert. Laden Sie die Produktseite neu, bevor Sie weiter bearbeiten. Wenn Sie im alten Formular auf **Speichern** drücken, schreibt PrestaShop den alten Text zurück. Das Modul kürzt lange Antworten auf die Feldgröße: Name 128 Zeichen, Kurzbeschreibung 800, Meta-Titel 69, Meta-Beschreibung 159.

**Simulieren** hat dieselben Auswahlmöglichkeiten und die Schaltflächen **Testen**. Es zeigt die Antwort auf der Seite und ändert das Produkt nicht. Der Versuch wird in den Verlauf geschrieben.

**Fotos** (erfordert eingeschalteten **KI-Bildfinder**):

1. Klicken Sie auf **Seiten finden**. Das Modell schlägt Seiten vor, die dieses Produkt wahrscheinlich zeigen.
2. Klicken Sie auf eine Seitenadresse. Der Shop liest die Seite (Adressen privater oder lokaler Netzwerke werden abgelehnt) und listet bis zu 24 Bilder auf. Kleine Symbole und Tracking-Pixel werden übersprungen.
3. Markieren Sie die gewünschten Fotos. Das erste markierte Foto wird zum Titelbild des Produkts und ersetzt das aktuelle Titelbild. Die anderen werden hinter den vorhandenen Fotos eingefügt.
4. Klicken Sie auf **Ausgewählte zu diesem Produkt hinzufügen**. Vor diesem Klick wird nichts gespeichert. Laden Sie das Produkt neu, um die Fotos zu sehen.

Fotosuchen werden nicht in den Verlauf geschrieben und zählen nicht zum Budget. Beachten Sie das Urheberrecht der Fotos, die Sie importieren.

**Verlauf** listet frühere Schreibvorgänge für dieses Produkt mit **Wann**, **Typ** und **Status** auf. **Wiederherstellen** bringt nach Bestätigung von „Restore the previous value?“ den vorherigen Text zurück. Sie sehen „Content successfully restored. Refresh this page to see changes.“. Der shopweite Verlauf wird nicht gelöscht.

Neben den Feldern Beschreibung, Kurzbeschreibung, Meta-Titel und Meta-Beschreibung (in jedem Produktformular) sehen Sie außerdem eine kleine runde Schaltfläche mit dem OpenAI-Logo **Mit KI generieren**. Klicken Sie darauf. Hat der Shop mehr als eine Sprache, wählen Sie **Aktuelle Sprache**, **Alle Sprachen** oder **Abbrechen**. Das Feld erhält ein fertiges Briefing für dieses Feld, und der Text landet nur im Formularfeld, mit „Text ist im Feld. Speichern Sie das Produkt, um ihn zu behalten.“. Klicken Sie am Produkt auf **Speichern**, um ihn zu behalten. Diese Schaltfläche nutzt weder Vorlagen noch das Feld **Anweisung**.

### 3.14 Updates

Öffnen Sie **Updates** (rechte Seite des oberen Menüs). Das Formular **MyPresta Updates** prüft bei MyPresta.eu, ob es eine neuere Moduldatei gibt. Es ändert Ihren Katalog nicht und installiert nichts.

![Updates (Updates)](https://mypresta.eu/docs/images/docs/mychatgpt-updates.webp)

| Feld | Standard | Was es bewirkt |
|---|---|---|
| **Manuelle Prüfung** | – | Klicken Sie auf **Jetzt prüfen**. Der Shop fragt den MyPresta.eu-Update-Server einmal ab und zeigt neben der Schaltfläche „Modul ist auf dem neuesten Stand!“ oder „Neue Version verfügbar!“. |
| **Automatische Benachrichtigungen** | Aktiviert | **Aktiviert** lässt das Back Office etwa alle drei Tage prüfen und eine Warnung mit Link anzeigen, wenn eine neuere Version existiert. **Deaktiviert** stoppt das. |
| **Produktseite** | – | Ein Link zur Modulseite bei MyPresta.eu. |

Klicken Sie auf **Speichern**, um die Auswahl der Benachrichtigungen zu speichern. Sie sehen „Update-Einstellungen gespeichert.“. Die Versionsnummer neben dem Modulnamen im Menü ist die in Ihrem Shop installierte Version, nicht die neueste.

## 4. Shop-Frontend

Das Modul zeigt Ihren Kunden nichts an. Es fügt dem Shop-Frontend weder einen Block noch eine Seite, ein Skript oder einen Stil hinzu. Das Theme hat nichts zu überschreiben. Alles, was Sie sehen, befindet sich im Back Office: die Schaltfläche **Mein ChatGPT** in der oberen Leiste, die Modulbildschirme und das Panel auf der Produktseite.

Das Modul hat zwei Webadressen, die nur für Server und für das Back Office existieren:

- Die **Cron-Adresse**. Kopieren Sie sie aus **Cron** (Abschnitt 3.10) und tragen Sie sie nur im Scheduler Ihres Servers ein. Jeder, der die vollständige Adresse mit dem Geheimnis kennt, kann einen Stapel starten. Veröffentlichen Sie sie daher nie und fügen Sie sie nicht in Chats oder Tickets ein.
- Eine technische Adresse, die die Schaltflächen im Back Office bei jeder Generierung verwenden. Öffnen oder teilen Sie sie nicht.

Das Öffnen der Cron-Adresse im Browser zeigt reinen Text. Diese Meldungen können Sie lesen:

| Was Sie sehen | Was zu tun ist |
|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | Öffnen Sie **Cron**, setzen Sie **Cron-Funktion aktivieren** auf **Ja** und klicken Sie auf **Speichern**. |
| The token does not exist or it’s wrong! | Das Geheimnis fehlt oder stimmt nicht überein. Kopieren Sie die Adresse nach dem Speichern erneut aus **Cron**. |
| Invalid action! | Die Adresse hat keinen Aufgabenteil. Fügen Sie die in Abschnitt 6.3 aufgeführten Einstellungen hinzu. |
| updatedField parameter is wrong! | Der Feldname in der Adresse gehört nicht zu den erlaubten Feldern. Verwenden Sie ein in **Zu aktualisierendes Feld** aufgeführtes Feld. |
| All must include all mandatory parameters! | Der Adresse fehlen Feld, Auswahlregel, Stapelgröße, Sprache oder Vorlage. Fügen Sie sie hinzu (Abschnitt 6.3). |
| productTarget parameter is wrong! Allowed values: … (oder categoryTarget) | Verwenden Sie pendingOpenAI, pendingField oder emptyField. |
| No valid product IDs provided. | Die **Liste der Produkt-IDs** enthält keine brauchbaren Nummern. Korrigieren oder leeren Sie die Liste. |
| No products to update. / No categories to update. | Nichts entspricht der Regel mehr. Der Auftrag ist abgeschlossen, oder ändern Sie **Ausgewählte Produkte** oder die Filter. |
| N products have been updated. / N categories have been updated. | Ein Stapel wurde geschrieben. Der nächste Aufruf setzt mit den nächsten Elementen fort. |
| N pending products. | Debug ist eingeschaltet. Es wurde nichts geschrieben. Schalten Sie Debug für echte Läufe aus. |
| Error!Monthly generation budget reached. | Erhöhen Sie das **Monatliche Generierungsbudget** oder warten Sie bis zum nächsten Monat. |
| Error!Reply rejected by the studio quality gate. | Die Antwort enthielt ein verbotenes Wort. Bearbeiten Sie **Verbotene Wörter** oder schalten Sie das **Qualitäts-Gate** aus. |
| Error! The model returned an empty response. | Erhöhen Sie **Max. Tokens**, probieren Sie ein anderes Modell oder eine andere Vorlage. |
| Error! gefolgt von einer OpenAI-Meldung | Lesen Sie die Meldung. Typische Ursachen sind ein falscher Schlüssel, fehlendes Guthaben oder ein unbekanntes Modell. |
| Error! Could not save product … (N product(s) updated before this one.) | PrestaShop hat den Text für dieses Element abgelehnt. Prüfen Sie das Produkt und führen Sie den Lauf erneut aus. |

## 5. Fehlerbehebung

### 5.1 Verbindung und Einstellungen

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| „The OpenAI API key is not set. Add it in the module settings.“ oder „The ChatGPT API key is not set. Add it in the module settings.“ | Es ist kein Schlüssel gespeichert. | Öffnen Sie **Einstellungen**, **ChatGPT**, fügen Sie den Schlüssel in **OpenAI API-SCHLÜSSEL** ein und klicken Sie auf **Speichern**. |
| „Das Feld 'OpenAI API-SCHLÜSSEL' ist ungültig!“ | Sie haben einen neuen Schlüssel mit weniger als 10 Zeichen gespeichert, obwohl kein Schlüssel gespeichert war. | Fügen Sie den vollständigen Schlüssel ein. |
| „Das Feld 'OpenAI Modell' ist ungültig!“ | **Modell** hat weniger als 3 Zeichen. | Wählen Sie ein Modell aus der Liste und speichern Sie erneut. |
| Meldung von OpenAI über einen falschen Schlüssel, ein Kontingent oder ein nicht existierendes Modell | OpenAI hat den Aufruf abgelehnt. Das Modul zeigt den Originaltext von OpenAI. | Prüfen Sie Schlüssel, OpenAI-Abrechnung und Modellnamen unter **Einstellungen**, **ChatGPT**. Ein von Ihnen hinzugefügtes Modell muss für Ihr Konto verfügbar sein. |
| „Error! Invalid token!“ | Die Seite wurde geöffnet, bevor das Modul sein internes Geheimnis erneuert hat, oder sie war sehr lange geöffnet. | Laden Sie die Seite neu und versuchen Sie es erneut. |
| „OpenAI request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.“ | OpenAI hat zu langsam geantwortet. | Erhöhen Sie **API-Timeout (Sekunden)** unter **Einstellungen**, **Allgemein** (bis 600), nutzen Sie ein schnelleres Modell oder verlangen Sie kürzeren Text. |
| „The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings – reasoning models spend part of that budget on thinking.“ | **Max. Tokens** ist für dieses Modell zu niedrig. | Erhöhen Sie **Max. Tokens** unter **Einstellungen**, **ChatGPT**. |
| „The response was blocked by the provider content filter. Try rewording the prompt.“ | Der Filter von OpenAI hat die Antwort gestoppt. | Formulieren Sie den Prompt oder die verwendeten Produktdaten um. |
| „The model returned an empty response.“ | Das Modell hat keinen Text geliefert. | Versuchen Sie es erneut, mit einem anderen Modell oder einem weniger strengen Prompt. |
| „Monthly generation budget reached. Raise it in the studio settings or wait until next month.“ | Die Zahl der erfolgreichen Generierungen hat das **Monatliche Generierungsbudget** erreicht. | Erhöhen Sie die Zahl unter **Einstellungen**, **Studio**, setzen Sie sie auf 0 oder warten Sie auf den nächsten Monat. Auch das Leeren des **Verlaufs** setzt den Zähler zurück. |
| „The reply was rejected because it contains a forbidden word from the studio settings.“ | Eine Zeile aus **Verbotene Wörter** kommt in der Antwort vor, auch innerhalb eines längeren Wortes. | Kürzen oder bearbeiten Sie die Liste oder setzen Sie das **Qualitäts-Gate** auf **Nein**. Es wurde nichts ins Produkt geschrieben. |

### 5.2 Produktseite und Generierungsergebnisse

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Das Panel **Mein ChatGPT** fehlt auf der Produktseite. | **Formular der Produktbearbeitungsseite** und **Produktbearbeitungsverlauf** sind beide ausgeschaltet, oder Sie befinden sich nicht im Reiter **Module**. | Schalten Sie die Schalter unter **Einstellungen**, **Allgemein** ein und öffnen Sie dann den Reiter **Module**. |
| „Speichern Sie das Produkt einmal, bevor Sie generieren.“ | Das Produkt hat noch keine Nummer. | Speichern Sie das Produkt und generieren Sie dann. |
| Der neue Text ist nach dem Speichern des Produkts verschwunden. | Das Produktformular auf dem Bildschirm enthielt noch den alten Text. | Laden Sie die Produktseite nach **Füllen** neu, bevor Sie bearbeiten und speichern. |
| „Product skipped.“ oder „Category skipped.“ | **Überspringen, wenn gefüllt** hat Text im Feld gefunden. Das ist kein Fehler. | Wählen Sie **Ersetzen**, **Darüber hinzufügen** oder **Darunter hinzufügen**, wenn Sie trotzdem schreiben möchten. |
| „Error! Content retrieve has failed! Details: …“ | OpenAI oder der Server hat einen Fehler zurückgegeben. | Lesen Sie die Details nach „Details:“. Öffnen Sie den **Verlauf**, filtern Sie **Status** nach **Fehler** und öffnen Sie die Zeile. |
| „Error! The generated content could not be saved to the product.“ oder „… to the category.“ | PrestaShop hat den Text abgelehnt, zum Beispiel wegen eines unzulässigen Zeichens. | Lesen Sie die Begründung nach dem Satz. Probieren Sie einen anderen Prompt oder ein kürzeres Feld. |
| „Error! Prompt is missing or too short!“ | Die Anweisung hat weniger als 4 Zeichen. | Schreiben Sie eine längere Anweisung oder lassen Sie das Feld leer, um das Standard-Briefing zu nutzen. |
| „Error! Product not found!“ / „Error! Category not found!“ | Das Element wurde gelöscht oder die Nummer ist falsch. | Erstellen Sie die Liste neu und führen Sie den Lauf erneut aus. |
| „Error! This log entry has no previous value to restore.“ oder „Error! Nothing to restore for this entry.“ | Diese Verlaufszeile hat keinen alten Text. | Nutzen Sie eine andere Zeile. Von **Simulieren** geschriebene Zeilen oder Fehler können nichts Brauchbares wiederherstellen. |
| „The model did not return a usable SEO pack.“ | Die Antwort hatte nicht das erwartete Format. | Klicken Sie erneut auf **Alle füllen** oder füllen Sie die Felder einzeln. |
| „Generierung fehlgeschlagen.“ bei einer Schaltfläche **Mit KI generieren** | Der Aufruf ist fehlgeschlagen. | Versuchen Sie es erneut. Den Grund finden Sie im **Verlauf**. |
| „Error! This PrestaShop version does not support the category Additional Description field.“ | Ihr Shop hat dieses Kategoriefeld nicht. | Wählen Sie ein anderes Kategoriefeld. |

### 5.3 Massengenerierung

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Die Tabelle nach **Weiter zum nächsten Schritt** ist leer. | Die Filter passen auf nichts. | Lockern Sie die Filter. Prüfen Sie **Produktstatus**, **Produktbestand** und **Nur aktualisieren**. |
| „Select at least one language.“ | Es ist keine Sprache markiert. | Markieren Sie mindestens eine Sprache. |
| Der Lauf ist mittendrin stehen geblieben. | Der Tab wurde geschlossen, die Verbindung brach ab oder der Server stoppte. | Erstellen Sie die Liste neu, wobei **Nur aktualisieren** auf noch nicht aktualisierte Produkte steht, und führen Sie den Lauf erneut aus. |
| Viele Zeilen zeigen Fehler. | Ein Problem mit Budget, Schlüssel oder Timeout. | Öffnen Sie den **Verlauf**, lesen Sie den ersten Fehler, beheben Sie ihn und führen Sie den Lauf erneut aus. |
| Startseite und Stammkategorie stehen in der Kategorieliste. | **Kategorien** wurde leer gelassen. | Markieren Sie die gewünschten Kategorien vor **Weiter zum nächsten Schritt**. |

### 5.4 Cron

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Im Katalog ändert sich nichts. | **Cron-Funktion aktivieren** ist aus, der Scheduler ruft die Adresse nicht auf, oder kein Element entspricht der Regel. | Prüfen Sie den Schalter, das Scheduler-Protokoll und **Ausgewählte Produkte**. Öffnen Sie die Adresse einmal mit eingeschaltetem Debug, um den Plan zu sehen. |
| Die Adresse antwortet mit einer Meldung aus der Tabelle in Abschnitt 4. | Siehe diese Tabelle. | Tun Sie, was die Tabelle sagt. |
| Dieselben Produkte werden immer wieder geschrieben. | **Ausgewählte Produkte** steht auf **emptyField** und das Feld bleibt leer, oder **pendingOpenAI** wird verwendet und der Verlauf wurde geleert. | Nutzen Sie **pendingField** oder korrigieren Sie den Prompt, damit Text geschrieben wird. |
| Eine alte Adresse funktioniert nicht mehr. | Das Modul ersetzt Geheimnisse mit weniger als 24 Zeichen, oder das Geheimnis wurde geändert, oder das Modul wurde neu installiert. | Kopieren Sie die Adresse erneut aus **Cron** und aktualisieren Sie den Scheduler. |
| **Token generieren** tut nichts. | Die Schaltfläche hat in dieser Version keine Funktion. | Behalten Sie das bei der Installation erzeugte Geheimnis. |

### 5.5 Bilder, neues Produkt und Menü

| Symptom | Ursache | Was zu tun ist |
|---|---|---|
| Der Reiter **Fotos** fehlt. | **KI-Bildfinder** ist aus. | Schalten Sie ihn unter **Einstellungen**, **Allgemein** oder **Bilder** ein und laden Sie das Produkt neu. |
| „No pages were suggested.“ oder „The search failed.“ | Das Modell hat keine brauchbaren Adressen geliefert, oder der Schlüssel hat ein Problem. | Klicken Sie erneut auf **Seiten finden** oder prüfen Sie den **KI-Bildsuch-Prompt**. |
| „That page could not be read.“, „URL not allowed (private network)“ oder ein Fehler, der mit HTTP beginnt | Die Seite sperrt den Shop, verlangt eine Anmeldung oder liegt in einem privaten Netzwerk. | Wählen Sie eine andere Seite. |
| „No photos were found on that page.“ | Die Seite hat keine brauchbaren Bilder. | Wählen Sie eine andere Seite. |
| „No images could be imported. Details: …“ | Die Bilder ließen sich nicht herunterladen oder sind keine echten Bilder. | Lesen Sie die Details. Wählen Sie andere Fotos. |
| „Failed to parse AI response. Please try again.“ bei **Neues Produkt** | Die Antwort hatte nicht das erwartete Format. | Klicken Sie erneut auf **Daten generieren**. |
| „Error creating product: …“ oder „Failed to create product“ | PrestaShop hat das Produkt abgelehnt, oft weil die gewählte **Sprache** nicht die Standardsprache des Shops ist. | Wählen Sie die Standardsprache und prüfen Sie die Kategorienummer. |
| „Generate the product first.“ | Sie haben auf **Produkt erstellen** geklickt, bevor Sie **Daten generieren** gedrückt haben. | Klicken Sie zuerst auf **Daten generieren**. |
| Der Menüeintrag **KI-Inhaltsgenerator** fehlt. | Das Modul ist deaktiviert, oder der Eintrag wurde verschoben. | Aktivieren Sie das Modul im **Modul-Manager** und öffnen Sie einmal eine beliebige Back-Office-Seite. Das Modul legt den Eintrag wieder unter **Module** ab. Fehlt er weiterhin, prüfen Sie, ob Ihr Mitarbeiterprofil **Module** öffnen darf. |
| Dashboard und Verlauf sind leer. | Im gewählten Zeitraum wurde nichts generiert, oder **Liste leeren** wurde verwendet. | Wählen Sie **Gesamtzeit**. |

## 6. Für Entwickler

### 6.1 Überblick

| Punkt | Wert |
|---|---|
| Technischer Name | mychatgpt |
| Version | 1.1.0 |
| Name in der Modulliste | My ChatGPT - AI content generation |
| Autor | MyPresta.eu |
| Modul-Tab | front_office_features |
| PrestaShop | 1.6 – 9.99.99 |
| Minimale PHP-Version | 7.0.0 (geprüft in `install()`) |
| Hauptklasse | `mychatgpt extends Module`, mit den Hilfsklassen `mychatgptUpdate` und `searchToolmychatgpt`, die sie erweitern |

Datenfluss: JavaScript im Back Office ruft den Front-Controller `ajax` mit `secret_token` (gelesen aus `MYPRESTA_MYCHATGPT_TOKEN`) oder einen Admin-Controller auf. Der Controller liest die Modell- und Sampling-Schlüssel, wendet das Studio an (`MyChatGPT\Studio`), ruft OpenAI über `MyChatGPT\OpenAIService` auf (cURL zum Chat-Completions-Endpunkt der OpenAI-API), schreibt den Text mit dem PrestaShop-Objektmodell und fügt eine Zeile in `mychatgpt_log` ein. `cron` tut dasselbe ohne Browser. `getServiceName()` gibt immer `openai` zurück. Übrig gebliebener Code für andere Anbieter wurde entfernt. Die Einstellungsschlüssel eines früheren zweiten Anbieters (`_GEMINI_API_KEY`, `_GEMINI_MODEL`, `_ACTIVE_SERVICE`) werden bei jedem Öffnen des Einstellungsbildschirms gelöscht.

### 6.2 Dateien

| Pfad | Zweck |
|---|---|
| `mychatgpt.php` | Hauptklasse: Installation und Deinstallation, Tabs, Einstellungsformulare, Prompt-Vorlagen, Dashboard, Hooks, Produkt-Tab, Modellkatalog. |
| `autoload.php` | Kleiner Klassenlader für den Namensraum `MyChatGPT\` (ohne Composer). |
| `src/OpenAIService.php` | cURL-Client für Chat Completions und die Modellliste. Timeout 10–600 s, verwirft Parameter, die ein Modell ablehnt (bis zu 6 Wiederholungen), deaktiviert Zertifikatsprüfungen nur auf localhost. |
| `src/Studio.php` | Budgetprüfung, Prompt-Anreicherung (Sprache, Stimme, Zielgruppe, Ton, Glossar, Verbotenes), Antwortprüfung, SEO-Paket und Alt-Text-Prompts. |
| `controllers/admin/*.php` | Sieben Admin-Controller (Abschnitt 6.3). |
| `controllers/front/ajax.php` | JSON-Endpunkt für alle im Browser ausgelösten Generierungen. |
| `controllers/front/cron.php` | Cron-Endpunkt mit reinem Text. |
| `lib/updateChecker.php` | Update-Prüfung gegen dev.mypresta.eu alle 3 Tage und das Formular Updates. |
| `lib/sectionHelp.php` | Texte der Hilfe-Schublade. |
| `lib/searchTool/` | Hilfsklasse `searchToolmychatgpt` (Autocomplete-Werkzeug in den Modulbildschirmen). |
| `lib/prestashop9compatibility.php` | Wrapper für Preisanzeige, Hashing und Weiterleitungen in PrestaShop 9. |
| `views/templates/hook/*.tpl` | Modulbildschirme und -panels (Dashboard, Navigation, Unternavigation, Massengeneratoren, Produkt-Tab, Verlauf, Cron-Info, Feld der oberen Leiste). |
| `views/templates/admin/product_creator.tpl` | Bildschirm für neue Produkte. |
| `views/js/back.js` | Massenläufe, Produkt-Panel, Spielwiese, Feld der oberen Leiste, neues Produkt, Wiederherstellung. |
| `views/js/product-fields.js` | Schaltflächen **Mit KI generieren** neben den Produktfeldern. |
| `views/js/image-finder.js` | Reiter **Fotos**. |
| `views/js/admin-products-bulk.js` | Fügt der Produktliste die Schaltfläche **Mein ChatGPT** hinzu. |
| `views/js/dashboard.js`, `chart.min.js`, `admin-help.js` | Diagramme und Hilfe-Schublade. |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Stile. |
| `translations/*.php` | 34 Sprachdateien. |
| `upgrade/index.php` | Nur eine Weiterleitungsdatei. Es gibt keine Upgrade-Skripte. |

Die Klassen `AdminMyChatGPTMain` und `AdminMyChatGPTSettings` rufen `addJS`/`addCSS` für `views/js/admin.js` und `views/css/admin.css` auf, und der Controller für neue Produkte für `product_creator.js` und `product_creator.css`. Keine dieser Dateien wird mitgeliefert. Das Cron-Formular erwartet die JavaScript-Funktionen `generateTokenAndFill()` und `generateCategoryTokenAndFill()` und füllt die `.cron-parameters`-Spans. Auch dieses Skript wird nicht mitgeliefert.

### 6.3 Controller

| Controller | Eltern und Route | Zweck |
|---|---|---|
| `AdminMyChatGPTMain` | Unter **Module**, sichtbar. Leitet zur Modulkonfiguration, Dashboard, weiter. | Der Menüeintrag **KI-Inhaltsgenerator**. |
| `AdminMyChatGPTSettings` | Versteckter Tab (`active = 0`). Leitet zur Konfiguration, Einstellungen, weiter. | Kompatibilitätseintrag. |
| `AdminMyChatGPT` (Datei `AdminMyChatGPT.php`, Klasse `AdminMyChatGPTController`) | Versteckter Tab. `mcg_sub=products` oder `categories`. | Filter und Massengeneratoren. `renderProductUpdateForm()` und das Kategorie-Aktualisierungsformular haben keinen Handler. Die Submits `generateProductContent` und `generateCategoryContent` speichern nur die Formularwerte. Die Generierung läuft aus `back.js`. |
| `AdminMyChatGPTProductCreator` | Versteckter Tab. Ajax-Aktionen `generateProductData`, `createProduct`, `extractImages`, `generateImages` (Stub). | Neues Produkt. |
| `AdminMyChatGPTCron` | Versteckter Tab. Formulare `submitCronUpdate`, `submitCatCronUpdate`. | Cron-Einstellungen. |
| `AdminMyChatGPTUsage` | Versteckter Tab. Parameter `stats_*`, `view` und `clear_log`. | Verlauf. `clear_log` führt `DELETE` auf der gesamten Log-Tabelle aus. |
| `AdminMyChatGPTImageFinder` | Versteckter Tab. Ajax-Aktionen `searchImages`, `extractImages`, `saveImages`. | Formular **Bilder** und Fotosuche. |

Alle Admin-Controller leiten auf die Startseite um, wenn das Modul inaktiv ist. Die Konfigurationsseite des Moduls (`getContent`) rendert Dashboard, Einstellungen (`mcg_tab=settings`, `mcg_sub` general, openai, studio, templates, playground) und Updates (`mcg_tab=updates`).

Front-Controller `ajax` (`secret_token` muss `_TOKEN` entsprechen; es gibt keine Mitarbeiterprüfung). Aktionen: `initiatePrompt`, `updateSettings` (schreibt Max Tokens, Temperature, Top P und beide Penalties), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateAltTexts` (keine Schaltfläche nutzt sie; höchstens 8 Bilder), `generateSeoPack`. `updateProduct` und `updateCategory` nehmen `target` (Feld), `behavior` (`replace`, `keep`, `keep_top`, `keep_end` oder `single_product` für eine Vorschau, die nicht gespeichert wird), `prompt`, Sprache und die Elementnummer entgegen. Antworten sind JSON mit `status` (`success`, `error`, `skipped`), `msg` und `date`.

Front-Controller `cron`: lehnt mit der Meldung „disabled“ ab, wenn `_ENABLE_CRON` 0 ist. Der Parameter `secret` muss `_SECRET` oder `_CAT_SECRET` entsprechen (jedes der beiden Geheimnisse öffnet beide Aufgaben). Parameter:

| Parameter | Verwendet von | Bedeutung |
|---|---|---|
| `secret` | beide | Produkt- oder Kategorie-Geheimnis. |
| `action` | beide | `generateProductContent` oder `generateCategoryContent`. |
| `updatedField` | beide | Produkte: name, description, description_short, meta_title, meta_description, tags. Kategorien: name, description, meta_title, meta_description, additional_description. |
| `productTarget` / `categoryTarget` | jeweils | `pendingOpenAI`, `pendingField`, `emptyField`. |
| `productsToUpdate` / `categoriesToUpdate` | jeweils | Stapelgröße (`LIMIT`). |
| `languageId` | beide | Sprachnummer. |
| `promptTemplateId` | beide | Vorlagennummer aus `mychatgpt_prompt`. |
| `debug` | beide | Jeder Wert außer 0 gibt den Plan aus und schreibt nichts. |
| `categories` | Produkte | Kommagetrennte Kategorienummern. |
| `productIds` | Produkte | Kommagetrennte Produktnummern. |

Beispiel (verwenden Sie `YOUR_SECURE_KEY` nur als Platzhalter):

```text
https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY&action=generateProductContent&updatedField=description&productTarget=pendingField&productsToUpdate=5&languageId=1&promptTemplateId=3&debug=1
```

`pendingOpenAI` und `pendingField` betrachten erfolgreiche Zeilen von `mychatgpt_log` (Zeilen mit Status error werden ignoriert, sodass fehlgeschlagene Elemente erneut versucht werden). Der Kategorie-Auftrag schließt Kategorien mit einer Nummer bis einschließlich der Startkategorie aus.

### 6.4 Hooks

Registriert in `install()`:

| Hook | Verhalten |
|---|---|
| `displayAdminProductsExtra` | Rendert das Panel des Reiters **Module** (`product-tab-wrapper.tpl`), wenn `_PRODUCT` oder `_PRODUCT_LOG` 1 ist. |
| `displayBackOfficeHeader` | Lädt Assets; führt `ensureLongSecrets()` aus (ersetzt `_TOKEN`, `_SECRET`, `_CAT_SECRET` mit weniger als 24 Zeichen) und `placeModuleMenu()`; registriert den Reiter **KI-Bildfinder** einmalig (`_IMAGEFINDER_TAB_OK`); reiht `product-fields.js`, `admin-products-bulk.js` und `image-finder.js` auf `AdminProducts` ein; registriert `dashboardZoneTwo` neu, falls es fehlt. `product-fields.js` wird auf jeder Produktseite eingereiht, unabhängig von `_PRODUCT`. |
| `displayBackOfficeTop` | Definiert JavaScript-Werte (`admin_controller_url`, `idcms`, `idcategory`, `idmanufacturer`) und rendert das Feld der oberen Leiste, wenn `_TOPCTA` 1 ist. |
| `dashboardZoneTwo` | Rendert `dashboard.tpl`, das `mcg_*`-Variablen liest, die dieser Hook nicht zuweist. |
| `displayAdminProductsMainStepLeftColumnMiddle` | Leerer Stub, gibt einen leeren String zurück. |
| `displayAdminProductsMainStepLeftColumnBottom` | Leerer Stub, gibt einen leeren String zurück. |
| `actionProductFormBuilderModifier` | Keine Wirkung, gibt nichts zurück. |
| `displayHeader` | Leerer Stub. |
| `displayFooter` | Leerer Stub. |

Die Methode `hookActionProductGridDataModifier` existiert, ist aber nicht registriert. Das Modul hat keine Überschreibung von `enable()` oder `disable()` und stellt keine eigenen Hooks bereit.

### 6.5 Überschreibungen

Das Modul hat keine Überschreibungen.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `mychatgpt_prompt` | `id_prompt`, `status` (0/1), `title` (128), `prompt` (text), `date_generated`. Mit 16 Zeilen vorbefüllt. |
| `mychatgpt_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, Paare `old_*` und `new_*` für name, description, description_short, meta_title, meta_description und tags, `date_updated`. Schlüssel auf `id_product` und `status`. |

Die Deinstallation löscht beide Tabellen. `ensureUsageColumns()` fügt die drei Token-Spalten beim Öffnen eines Bildschirms hinzu, falls einer älteren Tabelle diese fehlen. Vom Modul geschriebene Produkt-, Kategorie- und Bildzeilen sind Standarddaten von PrestaShop und werden bei der Deinstallation nicht angetastet.

### 6.7 Schlüssel und Übersetzungen

Die Schlüssel haben das Präfix `MYPRESTA_MYCHATGPT_`. Bei der Installation gesetzte Werte:

| Schlüssel | Standard |
|---|---|
| `_LIVE_MODE`, `_DEBUG_MODE` | 0 |
| `_TOPCTA`, `_PRODUCT`, `_PRODUCT_LOG` | 1 |
| `_TOKEN`, `_SECRET`, `_CAT_SECRET` | Zufällige 32 Zeichen |
| `_API_KEY` | Ein Leerzeichen |
| `_MODEL` | gpt-3.5-turbo |
| `_EXTRA_MODELS`, `_MODEL_CAPS` | Leer (der zweite wird zur Laufzeit mit abgelehnten Parametern je Modell gefüllt) |
| `_TEMPERATURE`, `_TOP_P` | 0.7, 1 |
| `_MAX_TOKENS`, `_TIMEOUT` | 3200, 120 |
| `_FREQ_PEN`, `_PRES_PEN` | 0 |
| `_VOICE`, `_AUDIENCE`, `_TONE`, `_GLOSSARY`, `_FORBIDDEN` | Leer |
| `_BUDGET`, `_QUALITY` | 0, 1 |
| `_IMAGEFINDER_ENABLE`, `_IMAGEFINDER_PROMPT` | 1, langer Standard-Prompt |
| `_ENABLE_CRON`, `_CRON_INTERVAL`, `_CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingOpenAI, 5, leer, Standardsprache, leer, 0, leer |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | description, pendingOpenAI, 5, leer, Standardsprache, 0 |
| `PS_USE_HTMLPURIFIER` | Auf 0 gesetzt (shopweit) |

Die Cron-Schlüssel ohne Präfix (`updatedField`, `debug` und die anderen oben) sind globale Namen und können mit anderen Modulen kollidieren.

Später angelegt: `_IMAGEFINDER_TAB_OK`, `categories` (Cron-Kategorieauswahl), `mypresta_updates`, `update_mychatgpt`, `updatev_mychatgpt`. `AdminMyChatGPT::postProcess()` schreibt außerdem bei jeder Anfrage dieses Controllers jedes Filterfeld (`_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`) in die Konfiguration, aber nichts liest sie zurück.

Die Deinstallation löscht die in `uninstall()` aufgeführten Schlüssel. Sie stellt `PS_USE_HTMLPURIFIER` nicht wieder her. Sie lässt `categories`, die oben genannten Filterschlüssel und die Update-Schlüssel zurück.

Die Generatoren, der Cron und die übliche Validierung verwenden `Tools::getValue` mit Whitelists. Der API-Schlüssel wird als Klartext in der Konfigurationstabelle gespeichert. `randomString()` verwendet `rand()`.

Übersetzungen: Fügen Sie `translations/{iso}.php` im Standardformat für PrestaShop-Module hinzu (34 Sprachen werden mitgeliefert). Texte laufen in der Hauptklasse, im Update-Prüfer und in der Hilfe-Schublade durch `$this->l()`. In PrestaShop 8 und 9 verwenden die Admin-Controller `trans()` mit den Domänen `Admin.MyChatGPT`, `Admin.MyChatGPTCron` und `Admin.MyChatGPTUsage`. Nicht übersetzt: die Meldungen in `back.js` und `image-finder.js`, die Standardanweisungen von **Füllen** und **Mit KI generieren**, die Ausgabe von `cron` und die Fehlertexte von `AdminMyChatGPTProductCreator` und `AdminMyChatGPTImageFinder`. Die langen Hilfetexte („What it does / How to configure / Effect“) werden von `fieldHelp()` erzeugt und stehen in den Formulardefinitionen von `mychatgpt.php` und der Admin-Controller (Methode `help()`), in den Templates und in `lib/sectionHelp.php`. Die Namen der Standardvorlagen und die Menünamen werden bei der Installation in den Shop-Sprachen in die Datenbank geschrieben.

### 6.8 Erweiterung

- Fügen Sie Prompt-Vorlagen im Modulbildschirm oder in `mychatgpt_prompt` hinzu oder bearbeiten Sie sie.
- Fügen Sie Platzhalter in den Prompt-Buildern von `ajax.php` (`updateProduct`, `updateCategory`) und von `cron.php` hinzu.
- Fügen Sie Modelle unter **Einstellungen**, **ChatGPT** ohne Codeänderung hinzu. Das Modul lernt nicht unterstützte Parameter selbstständig.
- Ändern Sie die Standardanweisungen für **Füllen**, **Mit KI generieren** und Massenläufe in `back.js` und `product-fields.js`.
- Das Frontend hat kein Template, das Theme hat also nichts zu überschreiben. Die Back-Office-Templates in `views/templates` ändern Sie im Modulordner.

## 7. Hilfe

Produktseite: https://mypresta.eu/modules/administration-tools/my-chatgpt.html

So schreiben Sie uns zum Modul:

1. Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an.
2. Öffnen Sie die Kontaktseite.
3. Wählen Sie **Support for paid modules**.
4. Beschreiben Sie das Problem. Geben Sie die genaue Meldung vom Bildschirm und die Schritte an, die dorthin führen. Fügen Sie niemals Ihren OpenAI-API-Schlüssel oder eine vollständige Cron-Adresse mit dem Geheimnis ein.
