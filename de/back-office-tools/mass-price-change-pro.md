---
title: "Mass price change pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mass price change pro“ von MyPresta.eu."
sidebar:
  label: "Mass price change pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Mass price change pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/mass-price-change-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/mass-price-change-pro/)
>
> ---


# Mass price change pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.0.0 - 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den allgemeinen PrestaShop-Betrieb erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Mass price change pro“ bietet eine umfassende Oberfläche innerhalb des PrestaShop Back Office, um Ihre Preisänderungen zu definieren und auszuführen. Alle Einstellungen werden über die Hauptkonfigurationsseite des Moduls aufgerufen.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Modul-Manager > Mass price change pro > Konfigurieren)

Beim Aufrufen der Konfigurationsseite des Moduls finden Sie eine Reihe von Registerkarten oder Abschnitten, die Sie durch den Prozess der Definition Ihrer Preisänderungsoperation führen sollen.

#### **Hauptregisterkarten / Abschnitte:**

Die Konfiguration des Moduls ist typischerweise in mehrere Schlüsselabschnitte unterteilt, die oft als Registerkarten oder separate Blöcke auf der Hauptseite präsentiert werden. Obwohl die genauen Bezeichnungen zwischen den Versionen leicht variieren können, bleibt die Kernfunktionalität konsistent:

1.  **Was zu tun ist (WTD):** Definieren Sie die Art der Preisänderung.
2.  **Zielprodukte:** Wählen Sie aus, welche Produkte betroffen sein sollen.
3.  **Einschränkungen:** Fügen Sie zusätzliche Bedingungen für die Zielauswahl hinzu.
4.  **Regeln:** Definieren Sie spezifische Preisregeln.
5.  **Vorschau:** Sehen Sie die Auswirkungen, bevor Sie sie anwenden.
6.  **Historie:** Überprüfen Sie vergangene Operationen.
7.  **Planer:** Planen Sie zukünftige Preisänderungen.
8.  **CSV Import/Export:** Verwalten Sie Preise über CSV.
9.  **Cron-Einrichtung:** Konfigurieren Sie automatisierte Aufgaben.

Gehen wir jeden Abschnitt im Detail durch:

#### **4.1.1 Was zu tun ist (WTD)**

In diesem Abschnitt definieren Sie die Kernaktion Ihrer Preisänderung.

-   **Was diese Einstellung bewirkt:** Bestimmt, wie Produktpreise geändert werden. Sie wählen zwischen Erhöhen, Verringern oder Festlegen eines neuen Preises und ob dies für den Grundpreis, den spezifischen Preis oder die Auswirkung auf Kombinationen gilt.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Um Prozentsatz erhöhen:* Fügt einen Prozentsatz des aktuellen Preises zum Produkt hinzu.
    *   *Um Prozentsatz verringern:* Zieht einen Prozentsatz des aktuellen Preises vom Produkt ab.
    *   *Um festen Betrag erhöhen:* Fügt einen bestimmten monetären Wert zum Produktpreis hinzu.
    *   *Um festen Betrag verringern:* Zieht einen bestimmten monetären Wert vom Produktpreis ab.
    *   *Neuen Preis festlegen auf:* Überschreibt den aktuellen Preis mit einem neuen, angegebenen Wert.
    *   *Auf Grundpreis anwenden:* Ändert den Hauptproduktpreis.
    *   *Auf spezifischen Preis anwenden:* Ändert Preise, die über „Spezifische Preise“-Regeln festgelegt wurden (z. B. für Gruppen, Länder oder Mengen).
    *   *Auf Auswirkung auf Kombinationen anwenden:* Ändert die Preisanpassung für Produktkombinationen (Attribute).
-   **Empfohlener Wert:** Hängt vollständig von Ihrem Geschäftsziel ab. Beginnen Sie mit einem klaren Ziel (z. B. „alle Preise um 5 % erhöhen“), bevor Sie auswählen.
-   **Händlerszenario / Beispiel:**
    *   *Szenario 1 (Inflation):* „Ich muss alle meine Produktpreise aufgrund steigender Lieferantenkosten um 3 % erhöhen.“ -> Wählen Sie „Um Prozentsatz erhöhen“, geben Sie „3“ ein und wählen Sie „Auf Grundpreis anwenden“.
    *   *Szenario 2 (Ausverkauf):* „Ich möchte den Preis aller Produkte in der Kategorie ‚Sommerkollektion‘ um 5 $ reduzieren.“ -> Wählen Sie „Um festen Betrag verringern“, geben Sie „5“ ein und wählen Sie „Auf Grundpreis anwenden“.

#### **4.1.2 Zielprodukte**

Hier wählen Sie präzise aus, *welche* Produkte von der Preisänderung betroffen sein sollen.

-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf verschiedenen Kriterien wie Kategorien, Herstellern, Lieferanten, spezifischen Produkt-IDs oder sogar Produkten ohne spezifischen Preis zu filtern.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Kategorien auswählen:* Nur Produkte innerhalb der ausgewählten Kategorien werden berücksichtigt.
    *   *Hersteller/Lieferanten auswählen:* Nur Produkte dieser Marken/Quellen sind betroffen.
    *   *Produkt-IDs eingeben:* Nur die exakten Produkte, die Sie auflisten, werden gezielt angesprochen.
    *   *Filtern nach „Produkte ohne spezifischen Preis“:* Nützlich, um sicherzustellen, dass Sie nicht versehentlich bestehende spezifische Preisregeln überschreiben.
-   **Empfohlener Wert:** Seien Sie so spezifisch wie möglich, um unbeabsichtigte Änderungen zu vermeiden. Verwenden Sie bei Bedarf mehrere Filter.
-   **Händlerszenario / Beispiel:**
    *   *Szenario 1 (Marken-Update):* „Mein Hauptlieferant, ‚Fashionista Co.‘, hat seine Preise erhöht. Ich muss alle Produkte dieses Herstellers aktualisieren.“ -> Wählen Sie „Hersteller“ und dann „Fashionista Co.“ aus.
    *   *Szenario 2 (Saisonware):* „Ich möchte alle Produkte in der Kategorie ‚Winterbekleidung‘ in den Verkauf geben.“ -> Wählen Sie „Kategorie“ und dann „Winterbekleidung“ aus.

#### **4.1.3 Einschränkungen**

Dieser Abschnitt ermöglicht es Ihnen, noch spezifischere Bedingungen für Ihre Produktauswahl hinzuzufügen.

-   **Was diese Einstellung bewirkt:** Bietet erweiterte Filteroptionen, wie z. B. das Anzielen von Produkten innerhalb eines bestimmten Preisbereichs, Produkten mit bestimmten Merkmalen oder Attributen oder Produkten, die derzeit auf Lager sind.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Preisbereich:* Nur Produkte, deren aktueller Preis innerhalb des angegebenen Minimums und Maximums liegt, werden berücksichtigt.
    *   *Merkmale/Attribute:* Zielen Sie auf Produkte ab, die ein bestimmtes Merkmal (z. B. „Farbe: Rot“) oder Attribut (z. B. „Größe: XL“) haben.
    *   *Nur auf Lager:* Stellt sicher, dass nur Produkte betroffen sind, die derzeit zum Kauf verfügbar sind.
-   **Empfohlener Wert:** Verwenden Sie diese, um Ihre Zielliste weiter zu verfeinern, insbesondere für komplexe Aktionen oder bestandsbasierte Anpassungen.
-   **Händlerszenario / Beispiel:**
    *   *Szenario 1 (Premium-Produktverkauf):* „Ich möchte einen Rabatt auf hochwertige Artikel anbieten. Reduzieren Sie die Preise um 10 % für alle Produkte über 100 $ in der Kategorie ‚Elektronik‘.“ -> Wählen Sie unter „Zielprodukte“ „Elektronik“ aus. Unter „Einschränkungen“ stellen Sie den „Preisbereich“ von „100 $“ auf „Max.“ ein.
    *   *Szenario 2 (Räumung spezifischer Bestände):* „Ich muss alle ‚blauen‘ Hemden, die derzeit auf Lager sind, abverkaufen.“ -> Wählen Sie unter „Zielprodukte“ „Hemden“ aus. Unter „Einschränkungen“ wählen Sie „Attribut: Farbe > Blau“ und „Nur auf Lager“.

#### **4.1.4 Regeln**

Dieser Abschnitt ermöglicht es Ihnen, komplexere Preislogiken zu definieren, die die allgemeine Aktion „Was zu tun ist“ möglicherweise überschreiben oder ergänzen.

-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bedingte Preisanpassungen zu erstellen. Zum Beispiel: „Wenn ein Produkt in Kategorie A ist, erhöhen Sie seinen Preis um 5 %, aber wenn es in Kategorie B ist, verringern Sie ihn um 10 %.“
-   **Auswirkung der Änderung dieser Einstellung:** Ermöglicht hochgradig nuancierte Preisstrategien, bei denen verschiedene Produktgruppen innerhalb einer einzigen Operation unterschiedliche Anpassungen erhalten.
-   **Empfohlener Wert:** Verwenden Sie dies, wenn eine einzelne, einheitliche Preisänderung für alle Zielprodukte nicht ausreicht.
-   **Händlerszenario / Beispiel:**
    *   *Szenario (Gestaffelter Rabatt):* „Für Produkte in der Kategorie ‚Accessoires‘, wenn ihr Preis zwischen 10 $ und 50 $ liegt, um 5 % reduzieren. Wenn ihr Preis über 50 $ liegt, um 10 % reduzieren.“ -> Sie würden hier mehrere Regeln einrichten, jede mit ihrem eigenen Preisbereich und ihrer eigenen Anpassung.

#### **4.1.5 Vorschau**

Bevor Sie Änderungen vornehmen, können Sie in diesem entscheidenden Abschnitt die vorgeschlagenen Änderungen überprüfen.

-   **Was diese Einstellung bewirkt:** Zeigt eine Liste der Produkte an, die betroffen sein werden, mit ihrem aktuellen Preis und ihrem neuen Preis nach der Operation.
-   **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschützter Abschnitt. Er bietet ein Sicherheitsnetz, mit dem Sie Fehler in Ihrer Zielauswahl oder Ihren Regeln erkennen können, bevor sie auf Ihren Live-Shop angewendet werden.
-   **Empfohlener Wert:** Überprüfen Sie die Vorschau **IMMER** sorgfältig, bevor Sie mit der eigentlichen Preisänderung fortfahren.
-   **Händlerszenario / Beispiel:**
    *   *Szenario (Doppelprüfung):* „Ich habe einen Rabatt von 10 % für alle ‚Sommerkleider‘ eingerichtet. Die Vorschau zeigt ein Kleid, von dem ich weiß, dass es nicht rabattiert werden sollte. Ich kann zu ‚Zielprodukte‘ oder ‚Einschränkungen‘ zurückkehren, um meine Auswahl zu verfeinern.“

#### **4.1.6 Historie**

Dieser Abschnitt führt ein Protokoll aller vergangenen Preisänderungsoperationen.

-   **Was diese Einstellung bewirkt:** Zeigt ein Protokoll an, wer welche Preisänderung wann und welche Art von Operation es war, durchgeführt hat.
-   **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Protokoll. Es ist von unschätzbarem Wert für Audits, Fehlerbehebung und das Verständnis vergangener Preisentscheidungen.
-   **Empfohlener Wert:** Überprüfen Sie regelmäßig die Historie, insbesondere wenn mehrere Personen den Shop verwalten, um sicherzustellen, dass alle Änderungen beabsichtigt und nachverfolgt werden.
-   **Händlerszenario / Beispiel:**
    *   *Szenario (Audit):* „Ein Kunde hat einen falschen Preis gemeldet. Ich kann die Historie überprüfen, um zu sehen, ob eine kürzliche Massenpreisänderung dies verursacht haben könnte und wer die Änderung initiiert hat.“

#### **4.1.7 Planer**

Planen Sie Ihre Preisänderungen so, dass sie automatisch zu einem zukünftigen Datum und einer zukünftigen Uhrzeit ausgeführt werden.

-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine Preisänderungsoperation zu definieren und sie so einzustellen, dass sie automatisch zu einem bestimmten Datum und einer bestimmten Uhrzeit ausgeführt wird. Sie können auch festlegen, dass die Preise nach einem bestimmten Zeitraum zurückgesetzt werden, perfekt für temporäre Verkäufe.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Geplante Ausführung:* Die Preisänderung wird zum gewählten Zeitpunkt ohne manuelles Eingreifen angewendet.
    *   *Preise zurücksetzen:* Produkte kehren nach Ablauf des Verkaufszeitraums zu ihren ursprünglichen Preisen (oder einem anderen angegebenen Preis) zurück.
-   **Empfohlener Wert:** Unerlässlich für die Verwaltung von Aktionen, saisonalen Verkäufen oder Preisänderungen, die außerhalb der Geschäftszeiten live gehen müssen.
-   **Händlerszenario / Beispiel:**
    *   *Szenario (Black Friday Sale):* „Ich möchte am Black Friday um 00:00 Uhr einen Rabatt von 20 % auf alle Produkte anwenden und am Cyber Monday um 23:59 Uhr zu den ursprünglichen Preisen zurückkehren.“ -> Richten Sie die Rabattaktion ein, planen Sie sie für den Black Friday und fügen Sie einen Rücksetzplan für den Cyber Monday hinzu.

#### **4.1.8 CSV Import/Export**

Verwalten Sie Ihre Produktpreise mithilfe von CSV-Dateien für erweiterte Kontrolle oder externe Datenmanipulation.

-   **Was diese Einstellung bewirkt:**
    *   *Exportieren:* Ermöglicht Ihnen, eine Liste von Produkten (basierend auf Ihren Zielkriterien) mit ihren aktuellen Preisen in eine CSV-Datei zu exportieren.
    *   *Importieren:* Ermöglicht Ihnen, eine CSV-Datei mit Produkt-IDs und neuen Preisen hochzuladen und diese Änderungen auf Ihren Shop anzuwenden.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Exportieren:* Bietet eine Tabelle Ihrer Zielprodukte und deren Preise, die extern bearbeitet werden kann.
    *   *Importieren:* Überschreibt oder aktualisiert Preise für Produkte, die in der CSV-Datei aufgeführt sind, und bietet eine leistungsstarke Möglichkeit, große, komplexe Preislisten zu verwalten.
-   **Empfohlener Wert:** Verwenden Sie den Export für detaillierte Analysen oder wenn Sie sehr spezifische, nicht-formelhafte Preisanpassungen vornehmen müssen, die in einer Tabelle einfacher zu verwalten sind. Verwenden Sie den Import, wenn Sie eine vordefinierte Liste neuer Preise von einem Lieferanten oder einem externen System haben.
-   **Händlerszenario / Beispiel:**
    *   *Szenario (Lieferantenpreisliste):* „Mein Lieferant hat mir eine neue Preisliste für 500 Produkte geschickt. Anstatt jedes manuell zu aktualisieren, kann ich meine aktuelle Produktliste exportieren, sie mit der des Lieferanten abgleichen, die Preise in der CSV-Datei anpassen und sie dann wieder importieren.“

#### **4.1.9 Cron-Einrichtung**

Konfigurieren Sie den Cron-Job des Moduls für automatisierte Aufgaben, insbesondere für geplante Preisänderungen.

-   **Was diese Einstellung bewirkt:** Stellt den notwendigen Befehl oder die URL bereit, um einen Cron-Job auf Ihrem Server einzurichten. Dieser Cron-Job ist unerlässlich, damit die Funktion „Planer“ funktioniert, da er regelmäßig nach geplanten Preisänderungen sucht und diese ausführt.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Korrekte Cron-Einrichtung:* Stellt sicher, dass Ihre geplanten Preisänderungen automatisch zu den angegebenen Zeiten ausgeführt werden. Ohne einen ordnungsgemäß konfigurierten Cron-Job werden geplante Aufgaben nicht ausgeführt.
-   **Empfohlener Wert:** Befolgen Sie die Anweisungen des Moduls, um den Cron-Job auf Ihrem Hosting-Server einzurichten. Dies beinhaltet typischerweise das Hinzufügen einer Zeile zu Ihrer Server-Crontab. Das Modul stellt normalerweise den genauen Befehl bereit.
-   **Händlerszenario / Beispiel:**
    *   *Szenario (Automatisierte Verkäufe):* „Ich habe einen Flash-Sale für nächste Woche geplant. Um sicherzustellen, dass er pünktlich beginnt, muss ich sicherstellen, dass der Cron-Job korrekt eingerichtet ist und alle 5-15 Minuten ausgeführt wird.“ -> Kopieren Sie den bereitgestellten Cron-Befehl und fügen Sie ihn in den Cron-Manager Ihres Servers ein.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Was zu tun ist** | Operationstyp (Erhöhen/Verringern/Festlegen) | N/A (abhängig vom Ziel) | Definiert, wie Preise geändert werden (z. B. +5 %, -10 $, auf 25 $ festlegen). |
| | Wert (Prozentsatz/Fest) | N/A (abhängig vom Ziel) | Der Betrag oder Prozentsatz der Preisanpassung. |
| | Anwenden auf (Basis/Spezifisch/Kombinationen) | Grundpreis | Bestimmt, welcher Preistyp betroffen ist. |
| **Zielprodukte** | Kategorien | Spezifische auswählen | Filtert Produkte nach Kategorie. |
| | Hersteller | Spezifische auswählen | Filtert Produkte nach Marke. |
| | Lieferanten | Spezifische auswählen | Filtert Produkte nach Lieferant. |
| | Produkt-IDs | Liste eingeben | Zielt auf bestimmte Produkte nach ID ab. |
| | Produkte ohne spezifischen Preis | Ja/Nein | Schließt Produkte mit bestehenden spezifischen Preisen aus. |
| **Einschränkungen** | Preisbereich (Min/Max) | N/A (optional) | Filtert Produkte innerhalb einer Preisspanne. |
| | Merkmale / Attribute | Spezifische auswählen | Filtert Produkte nach ihren Merkmalen oder Attributen. |
| | Nur auf Lager | Ja/Nein | Betrifft nur Produkte, die derzeit auf Lager sind. |
| **Regeln** | Regel hinzufügen | N/A (optional) | Definiert bedingte Preisanpassungen basierend auf Kriterien. |
| **Vorschau** | (Schreibgeschützte Tabelle) | N/A | Zeigt aktuelle vs. neue Preise für betroffene Produkte. **Immer überprüfen!** |
| **Historie** | (Schreibgeschütztes Protokoll) | N/A | Zeichnet alle vergangenen Preisänderungsoperationen auf. |
| **Planer** | Operation planen | N/A (optional) | Legt ein zukünftiges Datum/eine zukünftige Uhrzeit fest, zu der Preisänderungen automatisch ausgeführt werden sollen. |
| | Preise zurücksetzen | N/A (optional) | Plant eine Preisrücksetzung nach einem festgelegten Zeitraum. |
| **CSV Import/Export** | Produkte exportieren | N/A (optional) | Lädt gezielte Produktdaten zur externen Bearbeitung herunter. |
| | Preise importieren | N/A (optional) | Lädt eine CSV-Datei hoch, um neue Preise auf Produkte anzuwenden. |
| **Cron-Einrichtung** | Cron-Befehl | Aus Modul kopieren | Unerlässlich für automatisierte geplante Aufgaben. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Preise haben sich nach dem Anwenden der Operation nicht geändert. Was ist schiefgelaufen?**
A1:

-   **Registerkarte „Historie“ prüfen:** Überprüfen Sie, ob die Operation erfolgreich aufgezeichnet und abgeschlossen wurde.
-   **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“. Ihr Browser könnte auch alte Daten zwischenspeichern, versuchen Sie daher, Ihren Browser-Cache zu leeren oder den Shop im Inkognito-Modus anzuzeigen.
-   **Zielauswahl prüfen:** Überprüfen Sie Ihre Einstellungen unter „Zielprodukte“ und „Einschränkungen“. Haben Sie versehentlich die Produkte ausgeschlossen, die Sie ändern wollten?
-   **Spezifische Preise:** Wenn Sie versucht haben, Grundpreise zu ändern, aber Produkte spezifische Preise haben, könnten die spezifischen Preise diese überschreiben. Überprüfen Sie, ob Ihre Operation so eingestellt war, dass sie „Spezifische Preise“ oder „Grundpreis“ betrifft.

**F2: Meine geplante Preisänderung wurde nicht zur angegebenen Zeit ausgeführt.**
A2:

-   **Cron-Job:** Der häufigste Grund dafür ist ein falsch eingerichteter oder nicht laufender Cron-Job. Gehen Sie zur Registerkarte **Cron-Einrichtung** in der Modulkonfiguration. Stellen Sie sicher, dass der bereitgestellte Cron-Befehl korrekt zu Ihrer Server-Crontab hinzugefügt wurde und mit der empfohlenen Häufigkeit (z. B. alle 5-15 Minuten) ausgeführt wird. Wenn Sie sich unsicher sind, wie das geht, wenden Sie sich an Ihren Hosting-Anbieter oder einen Webmaster.
-   **Modul aktiviert:** Stellen Sie sicher, dass das Modul „Mass price change pro“ in Ihrem Modul-Manager noch aktiviert ist.

**F3: Ich habe versehentlich die falschen Preise geändert. Kann ich die Änderungen rückgängig machen?**
A3:

-   **Registerkarte „Historie“:** Die Registerkarte „Historie“ des Moduls bietet oft eine Option, eine vorherige Operation rückgängig zu machen. Suchen Sie nach einer Schaltfläche „Rückgängig machen“ oder „Widerrufen“ neben der spezifischen Operation, die Sie rückgängig machen möchten.
-   **Datenbank-Backup:** Wenn eine Rückgängig-Option nicht verfügbar ist oder nicht wie erwartet funktioniert, unterstreicht dies die Bedeutung eines aktuellen Datenbank-Backups. Sie müssten Ihre Datenbank auf einen Zeitpunkt vor der fehlerhaften Preisänderung wiederherstellen. **Sichern Sie immer, bevor Sie größere Operationen durchführen!**

**F4: Das Modul wird nach der Installation nicht korrekt angezeigt oder verursacht Fehler.**
A4:

-   **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre spezifische PrestaShop-Installation (z. B. PrestaShop 8.x, 1.7.x) heruntergeladen und installiert haben.
-   **PHP-Kompatibilität:** Überprüfen Sie, ob die PHP-Version Ihres Servers innerhalb des unterstützten Bereichs des Moduls liegt (PHP 5.6 - 8.5).
-   **Theme-Konflikte:** Manchmal können benutzerdefinierte Themes stören. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob das Problem behoben wird. Wenn ja, benötigt Ihr Theme möglicherweise Anpassungen.
-   **Fehlerprotokolle:** Überprüfen Sie Ihren PrestaShop-Debug-Modus (falls aktiviert) oder die PHP-Fehlerprotokolle Ihres Servers auf spezifische Fehlermeldungen. Diese können Entwicklern Hinweise geben.

**F5: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A5:

-   Navigieren Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
-   Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Mass price change pro“ aus der Modul-Dropdown-Liste.
-   Sie können dann alle Zeichenketten des Moduls in Ihre gewünschten Sprachen übersetzen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Mass price change pro“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Mass price change pro“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und `ModuleFrontController` für spezifische Front-Office-Aufgaben wie die Cron-Ausführung nutzt. Das Modul stützt sich stark auf seine `index.php` (Hauptmoduldatei) für die Back-Office-Konfiguration und -Verarbeitung, wobei Smarty-Templates für die Darstellung verschiedener Konfigurationsabschnitte verwendet werden. Es integriert benutzerdefiniertes JavaScript für verbesserte UI-Elemente wie Produkt-Targeting und Autovervollständigung sowie CSS für das Styling. Obwohl es in der bereitgestellten Inventur keine expliziten `ObjectModel`-Klassen definiert, interagiert es wahrscheinlich direkt mit den Kern-PrestaShop-Tabellen `Product`, `SpecificPrice` und `Configuration`.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `controllers/front/cron.php`
    *   **Klassenname:** `MassPriceProCronModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem serverseitigen Cron-Job aufgerufen zu werden. Seine Hauptaufgabe ist die Ausführung geplanter Preisänderungsoperationen, die in der Back-Office-Konfiguration des Moduls definiert sind. Er verarbeitet Aufgaben wie das Anwenden geplanter Rabatte, das Zurücksetzen von Preisen oder das Ausführen anderer automatisierter Preisanpassungen. Er gibt typischerweise eine einfache Erfolgs-/Fehlermeldung zurück oder protokolliert seine Aktivität.
-   `controllers/front/index.php`
    *   **Klassenname:** `MassPriceProIndexModuleFrontController` (wahrscheinlich)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dieser Controller könnte als allgemeiner Einstiegspunkt für Front-Office-Modulaktionen dienen, die nicht in eine bestimmte Kategorie passen, oder er könnte ein Platzhalter sein. Angesichts der Natur des Moduls ist es weniger wahrscheinlich, dass es direkte kundenorientierte Funktionalität hat, und wahrscheinlicher, dass es Hintergrund-AJAX-Anfragen oder spezifische Datenabrufe verarbeitet, falls dies von Front-End-Skripten benötigt wird.

#### Back-Office-Admin-Controller

Das Modul scheint basierend auf der bereitgestellten Inventur keine dedizierten `AdminController`-Dateien zu verwenden. Alle Back-Office-Konfigurationen und -Verarbeitungen werden wahrscheinlich direkt in der Methode `getContent()` der Hauptdatei `masspricepro/index.php` behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Basierend auf der bereitgestellten Inventur gibt es keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen innerhalb eines `classes/`-Verzeichnisses. Dies deutet darauf hin, dass das Modul direkt mit den Kern-PrestaShop-Klassen `Product`, `SpecificPrice`, `Category`, `Manufacturer`, `Supplier`, `Configuration` und möglicherweise anderen verwandten `ObjectModel`-Klassen und deren zugehörigen Datenbanktabellen interagiert. Die Preisänderungslogik ist wahrscheinlich in Methoden der Hauptklasse `MassPricePro` (in `index.php`) gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

-   `masspricepro/lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Wahrscheinlich sowohl Front-Office (falls für Produktsuche verwendet) als auch Back-Office (für Produkt-Targeting).
    *   **Details:** Bietet generische Autovervollständigungsfunktionalität. Es lauscht auf Benutzereingaben in Textfeldern, sendet AJAX-Anfragen an einen Backend-Endpunkt (möglicherweise `controllers/front/index.php` oder einen dedizierten AJAX-Handler in der Hauptmoduldatei) und zeigt Vorschläge in einer Dropdown-Liste an.
-   `masspricepro/views/js/jquery.autocomplete.js`
    *   **Geltungsbereich:** Wahrscheinlich Back-Office.
    *   **Details:** Ein jQuery-basiertes Autovervollständigungs-Plugin. Dies könnte eine spezifische Implementierung oder eine Abhängigkeit für die Produktauswahloberflächen des Moduls im Back Office sein, z. B. beim Anzielen von Produkten nach Name oder ID. Es verarbeitet die UI-Darstellung von Vorschlägen und Auswahlereignissen.
-   `masspricepro/views/js/mpp_pro.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Dies ist wahrscheinlich die Haupt-JavaScript-Datei für die Back-Office-Konfiguration des Moduls. Sie würde Folgendes enthalten:
        *   Ereignis-Listener für Formularübermittlungen, Tab-Änderungen, Schaltflächenklicks (z. B. „Änderungen anwenden“, „Vorschau“, „Regel hinzufügen“).
        *   AJAX-Aufrufe an die Methode `getContent()` oder einen Front-Controller zur Datenverarbeitung (z. B. Generieren von Vorschauen, Speichern von Einstellungen, Ausführen von Preisänderungen).
        *   DOM-Manipulation zum dynamischen Anzeigen/Ausblenden von Abschnitten, Aktualisieren von Vorschautabellen oder Verwalten von Regeleingaben.
        *   Validierungslogik für Formularfelder.
-   `masspricepro/views/js/mpp_target_products.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Behandelt speziell die Logik für den Abschnitt „Zielprodukte“ des Moduls. Dies würde Folgendes umfassen:
        *   Verwaltung der Auswahl von Kategorien, Herstellern, Lieferanten (z. B. mithilfe von Mehrfachauswahl-Dropdowns oder Baumansichten).
        *   Verarbeitung der Eingabe von Produkt-IDs, möglicherweise mit Validierung.
        *   Interaktion mit den Autovervollständigungsskripten, um Administratoren die Suche und Auswahl von Produkten zu ermöglichen.
        *   Dynamische Aktualisierung der Liste der ausgewählten Zielprodukte.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `masspricepro/lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Sowohl Front-Office als auch Back-Office.
    *   **Details:** Bietet Styling für die Autovervollständigungs-Vorschlags-Dropdowns und Eingabefelder, um sicherzustellen, dass sie visuell konsistent und benutzerfreundlich sind.
-   `masspricepro/views/css/mpp_admin.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Details:** Dies ist das primäre Stylesheet für die Konfigurationsoberfläche des Moduls im PrestaShop Back Office. Es stylt:
        *   Das Layout der Konfigurationsregisterkarten/-abschnitte.
        *   Formularelemente (Eingaben, Schaltflächen, Auswahlen, Kontrollkästchen).
        *   Tabellen (z. B. für Historie, Vorschau).
        *   Alle benutzerdefinierten UI-Komponenten, die spezifisch für das Modul sind.
        *   Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können: `.mpp-container`, `.mpp-tab-content`, `.mpp-form-group`, `.mpp-table`, etc.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden innerhalb der Methode `getContent()` der Hauptmoduldatei gerendert, um die Back-Office-Konfigurationsoberfläche zu erstellen.

-   `constraints.tpl`: Rendert den Abschnitt zum Definieren zusätzlicher Einschränkungen (z. B. Preisbereich, Merkmale, Attribute).
-   `cron_setup.tpl`: Zeigt Anweisungen und den Befehl zum Einrichten des Server-Cron-Jobs an.
-   `csv.tpl`: Rendert die Oberfläche für die CSV-Importfunktionalität.
-   `csv_export_target.tpl`: Rendert die Oberfläche für die CSV-Exportfunktionalität, speziell für Zielprodukte.
-   `history.tpl`: Zeigt die Tabelle und Details vergangener Preisänderungsoperationen an.
-   `mpp_operation_block.tpl`: Wahrscheinlich ein wiederverwendbarer Block zum Definieren einer einzelnen Preisänderungsoperation (erhöhen/verringern/festlegen).
-   `mpp_target_block.tpl`: Wahrscheinlich ein wiederverwendbarer Block zum Definieren von Produkt-Targeting-Kriterien.
-   `mpp_target_products_full.tpl`: Rendert die vollständige Oberfläche zur Auswahl von Zielprodukten, möglicherweise einschließlich Autovervollständigungsfeldern und ausgewählten Produktlisten.
-   `preview.tpl`: Zeigt die Tabelle mit den aktuellen und vorgeschlagenen neuen Preisen vor der Ausführung an.
-   `rules.tpl`: Rendert die Oberfläche zum Definieren bedingter Preisregeln.
-   `scheduler.tpl`: Zeigt das Formular zum Planen zukünftiger Preisänderungen und Rücksetzungen an.
-   `target_products.tpl`: Eine prägnantere oder alternative Vorlage für die Produkt-Targeting, möglicherweise in anderen Abschnitten verwendet.
-   `wtd.tpl`: Rendert den Abschnitt „Was zu tun ist“, in dem die Hauptart der Preisanpassung ausgewählt wird.

#### Hook-Templates (`views/templates/hook/`)

-   `form.tpl`: Dieses Template wird wahrscheinlich verwendet, um das Hauptkonfigurationsformular oder einen bestimmten Teil davon zu rendern, wenn das Modul in einen generischen Anzeige-Hook eingehängt wird (obwohl das Modul hauptsächlich `getContent()` für seine Hauptkonfiguration verwendet). Angesichts des Zwecks des Moduls ist es unwahrscheinlich, dass es etwas direkt im Front Office über Hooks wie `displayHeader` oder `displayFooter` anzeigt, sondern diese Hooks zum Laden von Assets oder zur internen Verarbeitung verwendet.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt basierend auf der bereitgestellten Inventur keine benutzerdefinierten SQL-Tabellen. Es stützt sich hauptsächlich auf die Kern-PrestaShop-Tabellen:

-   `ps_product`: Für Basisproduktpreise.
-   `ps_product_shop`: Für shop-spezifische Produktpreise.
-   `ps_specific_price`: Für spezifische Preisregeln.
-   `ps_product_attribute`, `ps_product_attribute_shop`: Für Kombinationspreise und Auswirkungen.
-   `ps_category_product`, `ps_manufacturer`, `ps_supplier`: Für Produkt-Targeting.
-   `ps_configuration`: Zum Speichern von Moduleinstellungen und Konfigurationswerten (z. B. `MPP_LAST_OPERATION_DATE`, `MPP_CRON_TOKEN`, `MPP_SCHEDULED_TASKS`).

#### Registrierte Hooks-Tabelle

Das Modul registriert wahrscheinlich Hooks, um sich in den PrestaShop-Lebenszyklus zu integrieren und Assets anzuzeigen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Zum Laden modulspezifischer CSS (`mpp_admin.css`, falls aus irgendeinem Grund benötigt, obwohl unwahrscheinlich für das Front-Office) und JavaScript (`autocomplete.js`, `jquery.autocomplete.js`, falls für die Front-End-Suche verwendet). |
| `actionModuleInstall` | Während der Modulinstallation. | Zur Durchführung der Erstkonfiguration, zum Erstellen von Konfigurationseinträgen und zum Registrieren weiterer Hooks. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Bereinigen von Konfigurationseinträgen und zum Deregistrieren von Hooks. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird. | Zum Laden von Back-Office-spezifischem CSS (`mpp_admin.css`) und JavaScript (`mpp_pro.js`, `mpp_target_products.js`, `autocomplete.js`) für die Konfigurationsseite des Moduls. |
| `actionScheduler` (oder ähnlicher benutzerdefinierter Hook) | Wird durch den Cron-Job des Moduls ausgelöst. | Zum Ausführen geplanter Preisänderungen und Rücksetzoperationen. Dies ist ein benutzerdefinierter interner Hook oder eine Methode, die vom `cron.php`-Controller aufgerufen wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Mass price change pro“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Sie können die neuesten Versionen aus Ihrer Bestellhistorie herunterladen und direkt über die Plattform auf Support-Ressourcen zugreifen.
