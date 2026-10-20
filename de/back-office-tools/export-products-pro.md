---
title: "Export Products Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Export Products Pro von MyPresta.eu."
sidebar:
  label: "Export Products Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Export Products Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/export-products-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/export-products-pro/)
>
> ---


# Export Products Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den allgemeinen PrestaShop-Betrieb erforderlich, aber dieses Modul hat keine spezifischen exotischen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Export Products Pro)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das allgemeine Verhalten und die Einstellungen für Ihre Produktexporte definieren.

#### Allgemeine Einstellungen

- **Exportformat**:

  - **Was diese Einstellung bewirkt:** Bestimmt das Dateiformat für Ihre exportierten Daten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf CSV eingestellt:* Das Modul generiert eine durch Kommas getrennte Werte-Datei (Comma Separated Values), die weitgehend mit Tabellenkalkulationssoftware wie Excel, Google Sheets oder LibreOffice Calc kompatibel ist. Dies ist das gebräuchlichste und vielseitigste Format.
    - *Wenn auf XML eingestellt:* Das Modul generiert eine Extensible Markup Language-Datei, die oft für einen strukturierteren Datenaustausch zwischen Systemen oder für spezifische Produktfeeds (z.B. Google Shopping) verwendet wird.
  - **Empfohlener Wert:** CSV für den allgemeinen Gebrauch und die Tabellenkalkulationsanalyse. XML, wenn Sie ein spezifisches System haben, das dies erfordert.
  - **Händlerszenario / Beispiel:** Wenn Sie die Daten in Excel öffnen möchten, um Preise zu analysieren, wählen Sie CSV. Wenn Sie einen Feed für eine Drittanbieteranwendung erstellen, die XML vorschreibt, wählen Sie XML.
- **Trennzeichen**:

  - **Was diese Einstellung bewirkt:** Dieses Zeichen trennt die verschiedenen Spalten (Felder) in Ihrer CSV-Datei.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf Komma (,) eingestellt:* Jedes Datenelement in einer Zeile wird durch ein Komma getrennt. Dies ist Standard für viele Systeme.
    - *Wenn auf Semikolon (;) eingestellt:* Jedes Datenelement wird durch ein Semikolon getrennt. Dies ist in einigen europäischen Regionen üblich oder wenn Kommas in Ihren Produktdaten (z.B. in Beschreibungen) vorkommen könnten, was zu Parsing-Problemen führen würde.
  - **Empfohlener Wert:** Komma (`,`) für die meisten Fälle. Wenn Ihre Tabellenkalkulationssoftware Schwierigkeiten hat, die CSV-Datei korrekt zu öffnen, versuchen Sie Semikolon (`;`).
  - **Händlerszenario / Beispiel:** Wenn Sie Ihre CSV-Datei in Excel öffnen und alle Daten in einer Spalte erscheinen, versuchen Sie, das Trennzeichen auf Semikolon zu ändern und erneut zu exportieren.
- **Nur aktive Produkte exportieren**:

  - **Was diese Einstellung bewirkt:** Steuert, ob nur Produkte, die derzeit in Ihrem Shop sichtbar und kaufbar sind, in den Export aufgenommen werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Nur Produkte, deren „Status“ im PrestaShop Back Office auf „Online“ oder „Aktiv“ gesetzt ist, werden exportiert. Dies ist nützlich für den aktuellen Bestand.
    - *Wenn deaktiviert (Nein):* Alle Produkte, einschließlich der als inaktiv oder deaktiviert markierten, werden exportiert. Dies ist nützlich für ein vollständiges Katalog-Backup oder eine Prüfung.
  - **Empfohlener Wert:** Ja, für die meisten operativen Exporte.
  - **Händlerszenario / Beispiel:** Wenn Sie einen Produktfeed für Google Shopping generieren, möchten Sie nur aktive Produkte, also aktivieren Sie dies. Wenn Sie ein vollständiges Daten-Backup erstellen, deaktivieren Sie es.
- **Nur vorrätige Produkte exportieren**:

  - **Was diese Einstellung bewirkt:** Filtert den Export, um nur Produkte einzuschließen, die derzeit eine Menge größer als Null haben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Nur Produkte, die derzeit auf Lager sind, werden exportiert.
    - *Wenn deaktiviert (Nein):* Produkte werden unabhängig von ihrem Lagerbestand (auf Lager oder nicht auf Lager) exportiert.
  - **Empfohlener Wert:** Ja, wenn Sie einen Feed für Verkäufe oder aktuelle Verfügbarkeit erstellen.
  - **Händlerszenario / Beispiel:** Wenn Sie eine Liste verfügbarer Produkte an einen Dropshipper senden, aktivieren Sie dies. Wenn Sie alle Produkte sehen müssen, einschließlich derer, die Sie nachbestellen müssen, deaktivieren Sie es.
- **Produktbilder exportieren**:

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die URLs Ihrer Produktbilder in den Export aufgenommen werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Die CSV-/XML-Datei enthält Spalten mit den URLs zu Ihren Produktbildern.
    - *Wenn deaktiviert (Nein):* Bild-URLs werden weggelassen, was zu einer kleineren Dateigröße führt, wenn Bilder nicht benötigt werden.
  - **Empfohlener Wert:** Ja, wenn Sie Bilder für Marktplätze oder externe Kataloge benötigen.
  - **Händlerszenario / Beispiel:** Wenn Sie einen Produktkatalog auf einer anderen Plattform aktualisieren, die Bild-URLs erfordert, aktivieren Sie dies.
- **Kurzbeschreibung des Produkts exportieren**:

  - **Was diese Einstellung bewirkt:** Schließt die Kurzbeschreibung (Zusammenfassung) Ihrer Produkte in den Export ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Die Kurzbeschreibung für jedes Produkt wird als Spalte aufgenommen.
    - *Wenn deaktiviert (Nein):* Die Kurzbeschreibung wird weggelassen.
  - **Empfohlener Wert:** Ja, da Kurzbeschreibungen oft für Produktlisten und Suchergebnisse verwendet werden.
  - **Händlerszenario / Beispiel:** Wenn Sie einen Produktfeed für eine Vergleichsseite erstellen, die Kurzbeschreibungen anzeigt, aktivieren Sie dies.
- **Produktbeschreibung exportieren**:

  - **Was diese Einstellung bewirkt:** Schließt die vollständige, detaillierte Beschreibung Ihrer Produkte in den Export ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Die vollständige Produktbeschreibung wird als Spalte aufgenommen.
    - *Wenn deaktiviert (Nein):* Die vollständige Beschreibung wird weggelassen.
  - **Empfohlener Wert:** Ja, für einen vollständigen Datenexport.
  - **Händlerszenario / Beispiel:** Wenn Sie Ihren Shop auf eine neue Plattform migrieren und alle Produktinhalte benötigen, aktivieren Sie dies.
- **Einstellungen speichern**:

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, speichert das Modul Ihre zuletzt verwendeten Exporteinstellungen (Filter, ausgewählte Felder) für Ihren nächsten Export.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Das Modul füllt das Exportformular mit Ihren vorherigen Auswahlmöglichkeiten vorab aus, was Zeit bei wiederholten Exporten spart.
    - *Wenn deaktiviert (Nein):* Das Exportformular wird jedes Mal, wenn Sie es besuchen, auf die Standardeinstellungen zurückgesetzt.
  - **Empfohlener Wert:** Ja, wenn Sie häufig ähnliche Exporte durchführen.
  - **Händlerszenario / Beispiel:** Wenn Sie regelmäßig eine Liste aktiver, vorrätiger Produkte mit bestimmten Feldern exportieren, beschleunigt die Aktivierung dieses Vorgangs Ihren Arbeitsablauf.

#### Filteroptionen

- **Produkte aus Kategorie exportieren**:

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl spezifischer Produktkategorien, die in Ihren Export aufgenommen werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn spezifische Kategorien ausgewählt sind:* Nur Produkte, die zu diesen Kategorien gehören, werden exportiert.
    - *Wenn keine Kategorien ausgewählt sind (oder alle ausgewählt sind):* Alle Produkte, unabhängig von der Kategorie, werden für den Export berücksichtigt (vorbehaltlich anderer Filter).
  - **Empfohlener Wert:** Wählen Sie spezifische Kategorien, wenn Sie einen gezielten Export benötigen; andernfalls lassen Sie die Auswahl für einen vollständigen Katalog unberührt.
  - **Händlerszenario / Beispiel:** Wenn Sie nur Produkte aus Ihrer Kategorie „Elektronik“ exportieren möchten, wählen Sie diese hier aus.
- **Nur übergeordnete Kategorien exportieren**:

  - **Was diese Einstellung bewirkt:** Wenn Sie Kategorien ausgewählt haben, verfeinert diese Option weiter, ob Produkte aus Unterkategorien ebenfalls eingeschlossen werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Nur Produkte, die direkt den ausgewählten übergeordneten Kategorien zugeordnet sind, werden exportiert. Produkte in deren Unterkategorien werden ausgeschlossen.
    - *Wenn deaktiviert (Nein):* Produkte aus den ausgewählten übergeordneten Kategorien UND all ihren Unterkategorien werden exportiert.
  - **Empfohlener Wert:** Nein, in den meisten Fällen, da Sie normalerweise auch Produkte aus Unterkategorien wünschen. Aktivieren Sie nur, wenn Sie einen spezifischen Grund haben, Produkte aus Unterkategorien auszuschließen.
  - **Händlerszenario / Beispiel:** Wenn Sie „Kleidung“ als übergeordnete Kategorie und „T-Shirts“ als Unterkategorie haben, würde die Aktivierung dieses Exports Produkte direkt in „Kleidung“ exportieren, aber nicht die in „T-Shirts“.
- **Produkte vom Hersteller exportieren**:

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte nach ihrem zugewiesenen Hersteller zu filtern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn spezifische Hersteller ausgewählt sind:* Nur Produkte dieser Hersteller werden exportiert.
    - *Wenn keine Hersteller ausgewählt sind (oder alle ausgewählt sind):* Produkte aller Hersteller werden berücksichtigt.
  - **Empfohlener Wert:** Wählen Sie spezifische Hersteller für gezielte Exporte.
  - **Händlerszenario / Beispiel:** Wenn Sie eine Produktliste zur Überprüfung an eine bestimmte Marke senden müssen, wählen Sie deren Hersteller hier aus.
- **Produkte vom Lieferanten exportieren**:

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte nach ihrem zugewiesenen Lieferanten zu filtern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn spezifische Lieferanten ausgewählt sind:* Nur Produkte dieser Lieferanten werden exportiert.
    - *Wenn keine Lieferanten ausgewählt sind (oder alle ausgewählt sind):* Produkte aller Lieferanten werden berücksichtigt.
  - **Empfohlener Wert:** Wählen Sie spezifische Lieferanten für gezielte Exporte.
  - **Händlerszenario / Beispiel:** Wenn Sie eine Liste der Produkte, die Sie von einem bestimmten Lieferanten führen, bereitstellen müssen, wählen Sie diese hier aus.

### 2.2 Dedizierter Admin-Bildschirm: Export Products Pro Dashboard (Back Office > Katalog > Export Products Pro)

Dies ist die primäre Schnittstelle zum Initiieren und Verwalten Ihrer Produktexporte.

- **Bildschirmname & Menüpfad:** **Katalog > Export Products Pro**
- **Verfügbare Aktionen & Einstellungen:**
  - **Export-Schaltfläche:** Dies ist die Hauptaktionsschaltfläche. Ein Klick darauf startet den Exportvorgang basierend auf den Einstellungen, die Sie auf dieser Seite konfiguriert haben.
  - **Feldauswahl:** Unter den allgemeinen Einstellungen finden Sie eine umfassende Liste aller verfügbaren Produkt- und Kombinationsfelder. Sie können individuell ankreuzen oder abwählen, welche Felder Sie in Ihren Export aufnehmen möchten.
    - **Produktfelder:** Enthält Standard-Produktdetails wie ID, Name, Referenz, EAN13, UPC, Preis, Menge, Gewicht, Beschreibungen usw.
    - **Kombinationsfelder:** Wenn Ihre Produkte Kombinationen haben (z.B. Größe, Farbe), sehen Sie Felder, die spezifisch für Kombinationen sind, wie „Kombinations-ID“, „Attribut (Name:Typ:Position)“, „Wert (Wert:Position)“, „Auswirkung auf den Preis“, „Auswirkung auf das Gewicht“, „Standard (0 = Nein, 1 = Ja)“, „Verfügbarkeitsdatum der Kombination“.
  - **Auswirkung von Änderungen:**
    - **Auswählen/Abwählen von Feldern:** Nur die angekreuzten Felder erscheinen als Spalten in Ihrer exportierten CSV-/XML-Datei. Dies ermöglicht Ihnen, hochgradig angepasste Exporte zu erstellen, die nur die benötigten Daten enthalten und unnötige Informationen weglassen.
  - **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
    1. Navigieren Sie zu **Katalog > Export Products Pro**.
    2. Überprüfen Sie die „Allgemeinen Einstellungen“ und „Filteroptionen“ oben auf der Seite. Passen Sie diese an, je nachdem, ob Sie aktive Produkte, vorrätige Produkte, spezifische Kategorien, Hersteller oder Lieferanten benötigen.
    3. Wählen Sie sorgfältig die „Produktfelder“ und „Kombinationsfelder“ aus, die Sie in Ihren Export aufnehmen möchten. Wenn Sie unsicher sind, ist es oft sicherer, zunächst mehr Felder auszuwählen und dann unerwünschte Spalten in Ihrer Tabellenkalkulationssoftware zu entfernen.
    4. Klicken Sie auf die Schaltfläche „Exportieren“. Das Modul generiert die CSV- oder XML-Datei und fordert Sie zum Herunterladen auf.
    5. Öffnen Sie die heruntergeladene Datei in Ihrer bevorzugten Tabellenkalkulationssoftware (z.B. Excel, Google Sheets), um die Daten und das Format zu überprüfen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Exportformat | CSV | Bestimmt den Ausgabedateityp (CSV oder XML). |
|  | Trennzeichen | Komma (`,`) | Zeichen, das Felder in CSV trennt. Ändern, wenn Parsing-Probleme auftreten. |
|  | Nur aktive Produkte exportieren | Ja | Schließt nur aktive Produkte ein. |
|  | Nur vorrätige Produkte exportieren | Ja | Schließt nur Produkte mit Menge > 0 ein. |
|  | Produktbilder exportieren | Ja | Schließt Bild-URLs in den Export ein. |
|  | Kurzbeschreibung des Produkts exportieren | Ja | Schließt die Kurzbeschreibung des Produkts ein. |
|  | Produktbeschreibung exportieren | Ja | Schließt die vollständige Produktbeschreibung ein. |
|  | Einstellungen speichern | Ja | Speichert Ihre letzten Exportauswahlen zur Bequemlichkeit. |
|  | Produkte aus Kategorie exportieren | (Nichts ausgewählt) | Filtert den Export nach ausgewählten Kategorien. |
|  | Nur übergeordnete Kategorien exportieren | Nein | Wenn Kategorien ausgewählt sind, schließt/schließt Produkte aus Unterkategorien ein/aus. |
|  | Produkte vom Hersteller exportieren | (Nichts ausgewählt) | Filtert den Export nach ausgewählten Herstellern. |
|  | Produkte vom Lieferanten exportieren | (Nichts ausgewählt) | Filtert den Export nach ausgewählten Lieferanten. |
| **Export Products Pro Dashboard** | **Feldauswahl** | Variiert je nach Bedarf | Wählen Sie spezifische Produkt-/Kombinationsattribute aus, die als Spalten in der Exportdatei enthalten sein sollen. |
|  | Export-Schaltfläche | N/A | Startet den Produktexport basierend auf allen konfigurierten Einstellungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine exportierte CSV-Datei sieht beim Öffnen in Excel verstümmelt aus oder alle Daten befinden sich in einer Spalte.**
**A1:** Dies ist normalerweise ein Problem mit dem Trennzeichen oder der Zeichenkodierung.

- **Lösung 1 (Trennzeichen):** Gehen Sie zurück zur Modulkonfiguration, ändern Sie die Einstellung „Trennzeichen“ von Komma (`,`) auf Semikolon (`;`) und exportieren Sie erneut. Versuchen Sie, die neue Datei zu öffnen.
- **Lösung 2 (Kodierung):** Verwenden Sie beim Öffnen der CSV-Datei in Excel die Option „Daten > Aus Text/CSV“. Stellen Sie im Importassistenten sicher, dass Sie den richtigen „Dateieursprung“ oder die „Kodierung“ (normalerweise `UTF-8`) auswählen und das richtige Trennzeichen angeben.

**F2: Einige Produkte fehlen in meinem Export, obwohl ich weiß, dass sie in meinem Shop existieren.**
**A2:** Überprüfen Sie Ihre Filtereinstellungen in der Modulkonfiguration:

- **Lösung:** Stellen Sie sicher, dass „Nur aktive Produkte exportieren“ und „Nur vorrätige Produkte exportieren“ Ihren Anforderungen entsprechend eingestellt sind. Wenn Sie spezifische Kategorien, Hersteller oder Lieferanten ausgewählt haben, überprüfen Sie, ob die fehlenden Produkte in diese Filter fallen. Wenn Sie alles exportieren möchten, stellen Sie sicher, dass keine Filter ausgewählt sind.

**F3: Der Exportvorgang dauert sehr lange oder bricht bei großen Katalogen mit einem Timeout ab.**
**A3:** Das Exportieren von Tausenden von Produkten kann ressourcenintensiv sein.

- **Lösung 1:** Versuchen Sie, kleinere Chargen zu exportieren, indem Sie die Filter „Produkte aus Kategorie“, „Hersteller“ oder „Lieferant“ verwenden.
- **Lösung 2:** Wenn Sie Zugriff auf Ihre Servereinstellungen haben, müssen Sie möglicherweise das `memory_limit` und die `max_execution_time` von PHP in Ihrer `php.ini`-Datei vorübergehend erhöhen. Wenden Sie sich hierfür an Ihren Hosting-Anbieter.
- **Lösung 3:** Deaktivieren Sie unnötige Felder, um die Menge der zu verarbeitenden Daten zu reduzieren.

**F4: Wie übersetze ich die Spaltenüberschriften in der exportierten Datei?**
**A4:** Die Spaltenüberschriften in der exportierten Datei basieren im Allgemeinen auf den internen Feldnamen oder den Standard-PrestaShop-Bezeichnungen und sind nicht direkt über die Moduloberfläche übersetzbar.

- **Lösung:** Der einfachste Weg ist, die exportierte CSV-Datei in einem Tabellenkalkulationsprogramm (wie Excel oder Google Sheets) zu öffnen und die Spaltenüberschriften manuell in Ihre gewünschte Sprache oder Terminologie umzubenennen. Speichern Sie die Datei mit den neuen Überschriften.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls Export Products Pro, der für Entwickler, Webmaster und technische Agenturen gedacht ist.

### 4.1 Architekturübersicht

Das Modul `Export Products Pro` folgt dem Standard-PrestaShop-MVC-Muster und konzentriert sich hauptsächlich auf die Back-Office-Funktionalität. Es nutzt Admin-Controller für seine Benutzeroberfläche und benutzerdefinierte Klassen für die Datenverarbeitung und Feed-Generierung. Die Kernlogik des Moduls befindet sich in seiner Hauptdatei `exportproducts.php` und dem `AdminExportProductsController`, der den Exportprozess und die Konfiguration verwaltet. Es verwendet `ObjectModel` für seine benutzerdefinierten Daten, falls vorhanden, obwohl es in diesem Fall hauptsächlich mit den Kern-PrestaShop-Produktdaten interagiert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/feed.php`
  - **Klassenname & übergeordnete Klasse:** `ExportProductsFeedModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die Generierung eines Produktfeeds (z.B. XML oder CSV) verantwortlich, der direkt über eine URL zugänglich ist. Er würde die Logik für die Abfrage von Produkten basierend auf spezifischen Parametern und deren Ausgabe im gewählten Format handhaben. Dies könnte für die automatisierte Feed-Generierung für externe Dienste verwendet werden.
- `controllers/front/index.php`
  - **Klassenname & übergeordnete Klasse:** `ExportProductsIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller könnte als Standard-Einstiegspunkt oder Fallback für Front-Office-Anfragen im Zusammenhang mit dem Modul dienen. Angesichts der primären Funktion des Moduls könnte er umleiten oder eine einfache Nachricht anzeigen, oder er könnte ein Platzhalter für zukünftige Front-Office-Funktionen sein.

#### Back-Office Admin-Controller

- `controllers/admin/AdminExportProducts.php`
  - **Tab-Name und verwaltete Entität:** Dieser Controller verwaltet das Haupt-Dashboard „Export Products Pro“ im PrestaShop Back Office, zugänglich über **Katalog > Export Products Pro**. Er verwaltet keine einzelne `ObjectModel`-Entität im traditionellen Sinne, sondern orchestriert den Produktexportprozess.
  - **Verantwortlichkeit:**
    - Zeigt das Konfigurationsformular für Exporteinstellungen an (Filter, Format, Trennzeichen usw.).
    - Behandelt die POST-Anfrage, wenn die Schaltfläche „Exportieren“ geklickt wird.
    - Verarbeitet die ausgewählten Produkt- und Kombinationsfelder.
    - Fragt die PrestaShop-Datenbank nach Produkt- und Kombinationsdaten basierend auf den angewendeten Filtern ab.
    - Generiert den Inhalt der CSV- oder XML-Datei.
    - Initiiert den Dateidownload an den Browser des Benutzers.
    - Verwaltet die `ep_remember_settings`-Funktionalität, um Benutzerauswahlen beizubehalten.
- `controllers/admin/index.php`
  - **Verantwortlichkeit:** Dies ist typischerweise eine leere Datei oder eine Datei, die eine einfache `die('No direct script access');`-Anweisung enthält, die als Sicherheitsmaßnahme dient, um den direkten Zugriff auf das Verzeichnis `controllers/admin` zu verhindern. Sie enthält keine aktive Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/ExportProductsFeed.php`
  - **Mit welcher Datenbanktabelle es interagiert:** Diese Klasse interagiert wahrscheinlich mit verschiedenen Kern-PrestaShop-Tabellen wie `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
  - **Ob es `ObjectModel` erweitert und Definition der `$definition`-Felder:** Es ist unwahrscheinlich, dass es `ObjectModel` direkt erweitert, da seine primäre Rolle darin besteht, vorhandene Produktdaten abzufragen und zu verarbeiten, anstatt eine neue Datenbankentität zu verwalten. Es würde Methoden zum Abrufen von Produktdaten mit verschiedenen Joins (Kategorien, Hersteller, Lieferanten, Bilder, Beschreibungen) enthalten.
  - **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:**
    - Methoden zum Abrufen von Produktdaten mit verschiedenen Joins (Kategorien, Hersteller, Lieferanten, Bilder, Beschreibungen).
    - Methoden zur Handhabung von Produktkombinationen und deren spezifischen Attributen.
    - Logik zum Anwenden von Filtern (aktiv, auf Lager, Kategorie, Hersteller, Lieferant).
    - Methoden zum Formatieren von Daten in CSV- oder XML-Strukturen.
    - Potenziell Methoden zur Handhabung großer Datensätze, um Speichererschöpfung zu verhindern.
- `classes/index.php`
  - **Verantwortlichkeit:** Ähnlich wie `controllers/admin/index.php` ist dies eine Sicherheitsdatei, um die direkte Verzeichnisauflistung oder Ausführung von Dateien innerhalb des Verzeichnisses `classes/` zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

Das bereitgestellte Modulinventar zeigt keine benutzerdefinierten JavaScript-Dateien (`[]`). Dies deutet darauf hin, dass das Front-End des Moduls (Back-Office-Konfiguration) vollständig auf PrestaShops nativen JavaScript-Bibliotheken (z.B. jQuery, PrestaShops Kern-JS) für die Formularbehandlung basiert oder seine Oberfläche einfach genug ist, um keine komplexen clientseitigen Interaktionen über Standard-Formularübermittlungen hinaus zu erfordern.

### 4.5 CSS-Stylesheets (`views/css/`)

Das bereitgestellte Modulinventar zeigt keine benutzerdefinierten CSS-Dateien (`[]`). Dies impliziert, dass die Back-Office-Oberfläche des Moduls das Standard-Back-Office-Styling von PrestaShop verwendet, um ein konsistentes Erscheinungsbild zu gewährleisten, ohne benutzerdefinierte Stile einzuführen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`exportproducts/script.tpl`**
  - **Geltungsbereich:** Wahrscheinlich ein generisches Template, das zum Einbetten kleiner JavaScript-Snippets oder Konfigurationsvariablen direkt in den HTML-Code verwendet wird, möglicherweise über `displayHeader` oder `displayBackOfficeHeader` eingebunden, wenn es auf bestimmten Seiten ausgeführt werden muss. Da keine JS-Dateien vorhanden sind, könnte dies Inline-JS für Formularvalidierung oder dynamisches Verhalten enthalten.
- **`exportproducts/views/templates/admin/dashboard.tpl`**
  - **Geltungsbereich:** Admin-Template.
  - **Zweck:** Dies ist das Haupt-Template für den `AdminExportProductsController`. Es rendert das gesamte Exportkonfigurationsformular, einschließlich allgemeiner Einstellungen, Filteroptionen und der umfangreichen Liste von Produkt- und Kombinationsfeldern, die der Händler für den Export auswählen kann. Es enthält auch die Schaltfläche „Exportieren“.
- **`exportproducts/views/templates/admin/form_header.tpl`**
  - **Geltungsbereich:** Admin-Template.
  - **Zweck:** Dieses Template rendert wahrscheinlich einen gemeinsamen Header-Bereich für die Admin-Konfigurationsformulare, möglicherweise einschließlich des Modultitels, der Beschreibung und vielleicht einiger Einführungstexte oder Links. Es ist so konzipiert, dass es zur Konsistenz am Anfang anderer Admin-Templates (wie `dashboard.tpl`) eingefügt wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul scheint keine eigenen benutzerdefinierten Datenbanktabellen zu erstellen.
  - Es speichert seine Konfigurationseinstellungen (z.B. `ep_export_format`, `ep_export_active`, `ep_remember_settings`, `ep_export_categories_onlycats`, etc.) in der Standard-PrestaShop-Tabelle `ps_configuration`. Diese Schlüssel sind mit `ep_` für „Export Products“ präfixiert.
  - Es liest primär Daten aus den Kern-PrestaShop-Tabellen: `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayModuleRoutes` | Während der Routengenerierung für Module. | Ermöglicht dem Modul, benutzerdefinierte freundliche URLs für seine Front-Office-Controller (z.B. `/feed` für `feed.php`) zu registrieren. |
| `moduleRoutes` | Während der Routengenerierung für Module. | Ähnlich wie `displayModuleRoutes`, wird zur Definition benutzerdefinierter URL-Muster und deren Zuordnung zu Modul-Controllern verwendet. |
| `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Bereich des Back Office. | Potenziell verwendet, um `script.tpl` für Inline-JS oder CSS einzubinden oder spezifische Meta-Tags oder JS-Variablen hinzuzufügen, die von der Admin-Oberfläche benötigt werden. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Seite rendert. | Wird verwendet, um CSS- und JavaScript-Dateien für das Back Office zu registrieren, um sicherzustellen, dass sie nur bei Bedarf geladen werden. (Obwohl keine JS/CSS-Dateien aufgeführt sind, wäre dieser Hook der Standardplatz, wenn sie vorhanden wären). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul **Export Products Pro** besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung unserer Module zu gewährleisten.
