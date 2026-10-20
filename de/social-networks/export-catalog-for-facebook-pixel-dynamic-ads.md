---
title: "Katalog für Facebook Pixel Dynamic Ads exportieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Katalog für Facebook Pixel Dynamic Ads exportieren“ von MyPresta.eu."
sidebar:
  label: "Katalog für Facebook Pixel Dynamic Ads exportieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Export catalog for facebook pixel dynamic ads auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/export-catalog-for-facebook-pixel-dynamic-ads.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/export-catalog-for-facebook-pixel-dynamic-ads/)
>
> ---


# Katalog für Facebook Pixel Dynamic Ads exportieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Stellen Sie sicher, dass Ihr Server über genügend Speicher und Ausführungszeit verfügt, um große Produkt-Feeds zu generieren, wenn Sie viele Produkte haben.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Die Konfiguration des Moduls erfolgt hauptsächlich über einen dedizierten Administrationsbildschirm, der es Ihnen ermöglicht, zu definieren, wie Ihr Produktkatalog exportiert wird.

### 2.1 Hauptkonfigurationsbildschirm des Moduls (Back Office > Module > Modul-Manager > Konfigurieren)

Dieser Bildschirm bietet die Haupteinstellungen für das Modul, mit denen Sie Ihre Produkt-Feeds generieren und verwalten können.

**Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach „Katalog für Facebook Pixel Dynamic Ads exportieren“ > Klicken Sie auf „Konfigurieren“.

#### Allgemeine Einstellungen & Feed-Generierung

In diesem Abschnitt definieren Sie die Kernparameter für Ihren Produkt-Feed.

- **Sprache für den Export auswählen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, welche Sprache für Produktnamen, Beschreibungen und andere Textfelder im exportierten Feed enthalten sein wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf Englisch eingestellt:* Ihr Feed enthält Produktdetails auf Englisch.
    - *Wenn auf Französisch eingestellt:* Ihr Feed enthält Produktdetails auf Französisch.
  - **Empfohlener Wert:** Die primäre Sprache Ihrer Zielgruppe für Facebook Ads. Wenn Sie Anzeigen in mehreren Sprachen schalten, müssen Sie für jede Sprache separate Feeds generieren.
  - **Händlerszenario / Beispiel:** Wenn Sie hauptsächlich Kunden in den USA ansprechen, würden Sie „Englisch“ auswählen. Wenn Sie auch Kunden in Frankreich ansprechen, würden Sie einen separaten Feed mit der Auswahl „Französisch“ generieren.
- **Währung für den Export auswählen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, welche Währungspreise im exportierten Feed enthalten sein werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf USD eingestellt:* Alle Produktpreise im Feed werden in US-Dollar angegeben.
    - *Wenn auf EUR eingestellt:* Alle Produktpreise im Feed werden in Euro angegeben.
  - **Empfohlener Wert:** Die primäre Währung Ihrer Zielgruppe für Facebook Ads. Wie bei der Sprache benötigen Sie bei der Ausrichtung auf mehrere Währungen separate Feeds.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop sowohl in USD als auch in CAD verkauft und Sie Facebook Ads für Ihre kanadischen Kunden schalten möchten, würden Sie für diesen spezifischen Feed „Kanadischer Dollar“ auswählen.
- **Nur aktive Produkte exportieren:**

  - **Was diese Einstellung bewirkt:** Steuert, ob nur Produkte, die derzeit in Ihrem Shop aktiviert und sichtbar sind, im Feed enthalten sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nur Produkte, die in Ihrem PrestaShop-Shop aktiv sind, werden exportiert. Dies verhindert, dass Anzeigen für nicht vorrätige oder eingestellte Artikel angezeigt werden.
    - *Wenn deaktiviert (NEIN):* Alle Produkte, einschließlich inaktiver, könnten exportiert werden. Dies wird im Allgemeinen für Live-Werbekampagnen nicht empfohlen.
  - **Empfohlener Wert:** **JA**. Dies stellt sicher, dass Ihre Anzeigen immer relevant sind und auf verfügbare Produkte verlinken.
  - **Händlerszenario / Beispiel:** Sie haben saisonale Produkte, die derzeit inaktiv sind. Wenn diese Einstellung aktiviert ist, erscheinen sie erst in Ihren Facebook Ads, wenn Sie sie reaktivieren.
- **Nur vorrätige Produkte exportieren:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob nur Produkte mit verfügbarem Lagerbestand im Feed enthalten sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nur Produkte, die derzeit auf Lager sind, werden exportiert.
    - *Wenn deaktiviert (NEIN):* Produkte, die nicht auf Lager sind, könnten exportiert werden, was möglicherweise zu einer schlechten Kundenerfahrung führt, wenn sie auf eine Anzeige für einen nicht verfügbaren Artikel klicken.
  - **Empfohlener Wert:** **JA**. Dies verhindert, dass Kunden auf Anzeigen für Produkte klicken, die sie nicht kaufen können, und reduziert Frustration und verschwendete Werbeausgaben.
  - **Händlerszenario / Beispiel:** Ein beliebter Artikel ist gerade ausverkauft. Wenn diese Einstellung aktiviert ist, wird er automatisch aus Ihrem Facebook-Feed entfernt, bis er wieder auf Lager ist.
- **Produktkombinationen (Variationen) exportieren:**

  - **Was diese Einstellung bewirkt:** Steuert, ob einzelne Produktkombinationen (z. B. ein T-Shirt in verschiedenen Größen und Farben) als separate Artikel im Feed exportiert werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Jede Kombination (z. B. „Rotes T-Shirt – Klein“, „Rotes T-Shirt – Mittel“) erscheint als einzigartiger Artikel im Feed, mit eigenem Bild, Preis und Link. Dies ist entscheidend, damit dynamische Anzeigen genau die Variante anzeigen, die ein Kunde angesehen hat.
    - *Wenn deaktiviert (NEIN):* Nur das Hauptprodukt wird ohne individuelle Kombinationen exportiert. Dies begrenzt die Granularität Ihrer dynamischen Anzeigen.
  - **Empfohlener Wert:** **JA**. Dies wird für die meisten Shops dringend empfohlen, insbesondere für solche, die Bekleidung, Elektronik oder Produkte mit Variationen verkaufen, um die genaueste und personalisierteste Werbeerfahrung zu gewährleisten.
  - **Händlerszenario / Beispiel:** Ein Kunde sieht ein „Blaues Kleid – Groß“ auf Ihrer Website. Wenn Kombinationen exportiert werden, kann Facebook ihm eine Anzeige speziell für dieses „Blaue Kleid – Groß“ zeigen.
- **Produktidentifikation (ID-Feld):**

  - **Was diese Einstellung bewirkt:** Legt fest, welches PrestaShop-ID-Feld als eindeutiger Bezeichner für Produkte im Facebook-Feed (`id`-Feld) verwendet werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Produkt-ID:* Verwendet die Standard `id_product` von PrestaShop.
    - *EAN13:* Verwendet den EAN13-Barcode.
    - *UPC:* Verwendet den UPC-Barcode.
    - *Referenz:* Verwendet den internen Referenzcode des Produkts.
  - **Empfohlener Wert:** **Produkt-ID** ist im Allgemeinen die sicherste und zuverlässigste Option, da sie immer eindeutig und intern für PrestaShop ist. Wenn Sie EAN13/UPC konsistent für alle Produkte und Kombinationen verwenden, können diese ebenfalls funktionieren.
  - **Händlerszenario / Beispiel:** Sie haben eine benutzerdefinierte Integration, die für die Nachverfolgung auf `id_product` basiert. Die Verwendung von „Produkt-ID“ hier gewährleistet Konsistenz.
- **Produktkategorie-Feld:**

  - **Was diese Einstellung bewirkt:** Bestimmt, welche Kategorieinformationen an Facebook gesendet werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Standard PrestaShop Kategorie:* Verwendet den primären Kategorienamen des Produkts.
    - *Google Produktkategorie:* Verwendet die Google Produktkategorie (falls zugewiesen). Dies wird von Facebook oft für eine bessere Übereinstimmung bevorzugt.
  - **Empfohlener Wert:** **Google Produktkategorie**, falls vorhanden. Andernfalls „Standard PrestaShop Kategorie“.
  - **Händlerszenario / Beispiel:** Sie verkaufen „T-Shirts“ in PrestaShop, aber die Google Produktkategorie ist „Bekleidung & Accessoires > Kleidung > Hemden & Oberteile > T-Shirts“. Die Verwendung der Google-Kategorie liefert Facebook spezifischere Daten.
- **Produktmarkenfeld:**

  - **Was diese Einstellung bewirkt:** Wählt aus, welches Feld aus Ihren Produktdaten für das `brand`-Attribut im Facebook-Feed verwendet werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Herstellername:* Verwendet den dem Produkt in PrestaShop zugewiesenen Hersteller.
    - *Lieferantenname:* Verwendet den dem Produkt zugewiesenen Lieferanten.
  - **Empfohlener Wert:** **Herstellername**. Dies ist das gebräuchlichste und logischste Feld für „Marke“.
  - **Händlerszenario / Beispiel:** Sie verkaufen Nike-Schuhe. Die Auswahl von „Herstellername“ füllt „Nike“ korrekt als Marke in Ihrem Feed aus.
- **Produkttyp-Feld:**

  - **Was diese Einstellung bewirkt:** Legt fest, welche Informationen für das Feld `product_type` im Facebook-Feed verwendet werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Standard PrestaShop Kategorie:* Verwendet den primären Kategorienamen des Produkts.
    - *Google Produktkategorie:* Verwendet die Google Produktkategorie (falls zugewiesen).
  - **Empfohlener Wert:** **Google Produktkategorie**, falls verfügbar, andernfalls „Standard PrestaShop Kategorie“. Dies hilft Facebook, den Produkttyp zu verstehen.
  - **Händlerszenario / Beispiel:** Für ein Produkt in „Elektronik > Smartphones“ könnte die Google Produktkategorie „Elektronik > Kommunikation > Telefonie > Mobiltelefone“ sein.
- **Produktbild-Feld:**

  - **Was diese Einstellung bewirkt:** Bestimmt, welche Bild-URL für den `image_link` im Feed verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Standard-Produktbild:* Verwendet das Hauptbild, das dem Produkt zugeordnet ist.
    - *Kombinationsbild (falls verfügbar):* Wenn Kombinationen exportiert werden, wird das spezifische Bild verwendet, das dieser Kombination zugewiesen ist, andernfalls das Standard-Produktbild.
  - **Empfohlener Wert:** **Kombinationsbild (falls verfügbar)**. Dies stellt sicher, dass, wenn ein Kunde ein rotes Hemd ansieht, die Anzeige ein rotes Hemd zeigt und nicht nur das generische Produktbild.
  - **Händlerszenario / Beispiel:** Sie haben ein Produkt mit mehreren Farbkombinationen, jede mit einem eigenen Bild. Diese Einstellung stellt sicher, dass das richtige Farbbild in der Anzeige angezeigt wird.
- **Produktbeschreibungsfeld:**

  - **Was diese Einstellung bewirkt:** Wählt aus, welches Beschreibungsfeld von PrestaShop (`description` oder `short_description`) für das `description`-Attribut im Facebook-Feed verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Beschreibung:* Exportiert die vollständige, detaillierte Produktbeschreibung.
    - *Kurzbeschreibung:* Exportiert die kurze Produktzusammenfassung.
  - **Empfohlener Wert:** **Beschreibung**. Facebook bevorzugt in der Regel eine detailliertere Beschreibung für einen besseren Anzeigenkontext.
  - **Händlerszenario / Beispiel:** Sie möchten so viele Informationen wie möglich in Ihren Anzeigen bereitstellen. Die Verwendung der vollständigen Beschreibung stellt dies sicher.
- **Produktkurzbeschreibungsfeld:**

  - **Was diese Einstellung bewirkt:** Wählt aus, welches Beschreibungsfeld von PrestaShop (`description` oder `short_description`) für das `short_description`-Attribut im Facebook-Feed verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Beschreibung:* Exportiert die vollständige, detaillierte Produktbeschreibung.
    - *Kurzbeschreibung:* Exportiert die kurze Produktzusammenfassung.
  - **Empfohlener Wert:** **Kurzbeschreibung**. Dies ist nützlich, wenn der Facebook-Feed sowohl eine lange als auch eine kurze Beschreibung erfordert oder wenn Sie eine prägnante Zusammenfassung für bestimmte Anzeigenformate bevorzugen.
  - **Händlerszenario / Beispiel:** Sie möchten eine prägnante Zusammenfassung für das Feld `short_description` in Ihrem Feed.
- **CSV-Trennzeichen:**

  - **Was diese Einstellung bewirkt:** Legt das Zeichen fest, das zum Trennen von Werten in der generierten CSV-Datei verwendet wird (z. B. Komma, Semikolon).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Komma (,):* Standard-CSV-Format.
    - *Semikolon (;):* In einigen europäischen Regionen üblich.
  - **Empfohlener Wert:** **Komma (,)**. Dies ist das am weitesten verbreitete Trennzeichen für CSV-Dateien, auch von Facebook.
  - **Händlerszenario / Beispiel:** Wenn das Facebook-Importtool ein Semikolon als Trennzeichen angibt, würden Sie es hier ändern. Andernfalls bleiben Sie beim Komma.
- **Bilder aus Feed löschen:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, entfernt das Modul Bildlinks aus dem generierten Feed.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Die Spalten `image_link` und `additional_image_link` im Feed sind leer. Dies wird im Allgemeinen NICHT empfohlen, da Bilder für dynamische Anzeigen entscheidend sind.
    - *Wenn deaktiviert (NEIN):* Bildlinks werden im Feed enthalten sein.
  - **Empfohlener Wert:** **NEIN**. Bilder sind grundlegend für visuelle Anzeigen.
  - **Händlerszenario / Beispiel:** Diese Einstellung ist selten nützlich, es sei denn, Sie haben eine sehr spezifische, erweiterte Einrichtung, bei der Bilder vollständig separat behandelt werden.

#### Produkte ausschließen

Dieser Abschnitt ermöglicht es Ihnen, bestimmte Produkte vom Einschuss in Ihren Facebook-Feed auszuschließen.

- **Produkte nach ID ausschließen:**
  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine durch Kommas getrennte Liste von Produkt-IDs einzugeben, die Sie nicht in Ihrem Facebook-Produktkatalog erscheinen lassen möchten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Hier gelistete Produkte:* Werden vollständig aus dem generierten Feed weggelassen.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben bestimmte Produkte, die Sie niemals bewerben möchten (z. B. interne Testprodukte, Dienstleistungen, die nicht für dynamische Anzeigen geeignet sind).
  - **Händlerszenario / Beispiel:** Sie verkaufen sowohl physische Produkte als auch digitale Dienstleistungen. Sie könnten die digitalen Dienstleistungsprodukte aus dem Feed ausschließen, da sie nicht zum Format dynamischer Anzeigen passen.

#### Feed generieren Schaltfläche

- **Was diese Schaltfläche bewirkt:** Startet den Prozess der Generierung der CSV-Datei des Produktkatalogs basierend auf allen oben konfigurierten Einstellungen.
- **Auswirkung des Klickens auf diese Schaltfläche:** Das Modul verarbeitet Ihre Produkte und erstellt eine herunterladbare CSV-Datei. Je nach Anzahl der Produkte kann dies einige Zeit dauern.
- **Empfohlene Aktion:** Klicken Sie auf diese Schaltfläche, nachdem Sie alle gewünschten Einstellungen überprüft und gespeichert haben.
- **Händlerszenario / Beispiel:** Nachdem Sie Änderungen an Ihren Produktbeschreibungen vorgenommen oder neue Produkte hinzugefügt haben, würden Sie hier klicken, um einen aktualisierten Feed für Facebook zu generieren.

#### Feed herunterladen Schaltfläche

- **Was diese Schaltfläche bewirkt:** Ermöglicht Ihnen, die zuletzt generierte CSV-Datei des Produktkatalogs auf Ihren Computer herunterzuladen.
- **Auswirkung des Klickens auf diese Schaltfläche:** Ihr Browser lädt die Datei `facebook_products.csv` herunter.
- **Empfohlene Aktion:** Laden Sie die Datei nach der Generierung herunter und laden Sie sie dann in Ihren Facebook Business Manager hoch.
- **Händlerszenario / Beispiel:** Sobald der Feed generiert ist, laden Sie ihn herunter und navigieren dann zu Ihrem Facebook Business Manager > Kataloge > Datenquellen, um die CSV-Datei hochzuladen.

### 2.2 Dedizierter Admin-Bildschirm: AdminExportProductsFeedController

Dies ist der zentrale Administrationsbildschirm, auf dem Sie die eigentliche Produkt-Feed-Generierung verwalten und die zu exportierenden Daten überprüfen.

**Menüpfad:** Back Office > Module > Modul-Manager > Konfigurieren „Katalog für Facebook Pixel Dynamic Ads exportieren“ > (Dieser Bildschirm ist die Hauptkonfigurationsschnittstelle selbst, oft direkt nach dem Klicken auf „Konfigurieren“ zugänglich).

Dieser Bildschirm präsentiert eine gitterartige Oberfläche oder ein Formular mit verschiedenen Optionen zur Steuerung der Ausgabe Ihres Produkt-Feeds. Die unten aufgeführten Felder stellen die Datenpunkte dar, die in Ihrem Facebook-Produktkatalog enthalten sein können.

- **ID:** Der eindeutige Bezeichner für das Produkt (basierend auf Ihrer Einstellung „Produktidentifikation“).
- **item\_group\_id:** Wird für Produktkombinationen verwendet, um sie unter einem einzigen übergeordneten Produkt zu gruppieren.
- **Titel:** Der Name des Produkts.
- **Kurzbeschreibung:** Die kurze Zusammenfassung des Produkts.
- **Beschreibung:** Die vollständige Beschreibung des Produkts.
- **Override:** (Wahrscheinlich eine interne Moduleinstellung, nicht direkt nach Facebook exportiert).
- **Verfügbarkeit:** Zeigt an, ob das Produkt auf Lager ist (`in stock`, `out of stock`).
- **Bestand:** Die aktuelle Lagerbestandsmenge.
- **Zustand:** Der Zustand des Produkts (z. B. `new`, `used`, `refurbished`).
- **Bildlink:** Die URL des Hauptproduktbildes.
- **Additional\_image\_link:** URLs zusätzlicher Produktbilder.
- **Preis:** Der aktuelle Preis des Produkts.
- **sale\_price:** Der Verkaufspreis des Produkts (falls zutreffend).
- **Marke:** Die Marke des Produkts (Hersteller).
- **Link:** Die direkte URL zur Produktseite in Ihrem Shop.
- **Google Produktkategorie:** Die dem Produkt zugewiesene Google Produktkategorie.
- **product\_type:** Der Produkttyp (z. B. Kategoriename).
- **gender:** Für Bekleidung, das Zielgeschlecht (z. B. `male`, `female`, `unisex`).
- **size:** Für Bekleidung, die Produktgröße.
- **age\_group:** Für Bekleidung, die Zielaltersgruppe (z. B. `newborn`, `infant`, `toddler`, `kids`, `adult`).

**Verfügbare Aktionen & Einstellungen:**
Auf diesem Bildschirm finden Sie die verschiedenen Konfigurationsoptionen, die in Abschnitt 4.1 detailliert beschrieben sind. Die „Verwaltete Tabelle / Entität“ bezieht sich hier auf die virtuelle Tabelle der Produktdaten, die das Modul vor dem Export erstellt. Es gibt keine direkte Datenbanktabelle, die von diesem spezifischen Controller verwaltet wird, sondern er verarbeitet und bereitet Daten aus Ihren vorhandenen PrestaShop-Produkttabellen vor.

**Auswirkung von Änderungen:**
Alle Änderungen an den Einstellungen auf diesem Bildschirm (z. B. Auswahl einer anderen Sprache, Aktivieren/Deaktivieren des Kombinationsexports) ändern direkt den Inhalt und das Format der CSV-Datei, die generiert wird, wenn Sie auf die Schaltfläche „Feed generieren“ klicken.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. Besuchen Sie diese Konfigurationsseite regelmäßig (z. B. täglich oder wöchentlich, je nachdem, wie oft sich Ihr Produktkatalog ändert).
2. Stellen Sie sicher, dass Ihre Sprach-, Währungs- und Lager-/aktiven Produkteinstellungen korrekt sind.
3. Klicken Sie auf „Feed generieren“, um eine aktualisierte CSV-Datei zu erstellen.
4. Laden Sie die generierte CSV-Datei herunter.
5. Laden Sie diese neue CSV-Datei in Ihren Facebook Business Manager hoch, um Ihren Produktkatalog zu aktualisieren. Facebook bietet auch Optionen zum Planen automatischer Abrufe von einer URL an, die konfiguriert werden können, sobald Sie eine stabile Feed-URL haben (oft vom Modul oder Ihrer Serverkonfiguration bereitgestellt).

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Sprache für den Export auswählen | Ihre Primärsprache | Bestimmt die Sprache der Produktnamen/Beschreibungen im Feed. |
|  | Währung für den Export auswählen | Ihre Primärwährung | Bestimmt die Währung der Preise im Feed. |
|  | Nur aktive Produkte exportieren | JA | Schließt nur aktive Produkte ein, verhindert Anzeigen für nicht verfügbare Artikel. |
|  | Nur vorrätige Produkte exportieren | JA | Schließt nur vorrätige Produkte ein, verhindert Anzeigen für nicht vorrätige Artikel. |
|  | Produktkombinationen exportieren | JA | Exportiert jede Produktvariation (Größe, Farbe) als einzigartigen Artikel für detaillierte Anzeigen. |
|  | Produktidentifikation (ID-Feld) | Produkt-ID | Definiert den eindeutigen Bezeichner für Produkte im Feed. |
|  | Produktkategorie-Feld | Google Produktkategorie (falls verfügbar) | Spezifiziert Kategoriedaten für Facebook. |
|  | Produktmarkenfeld | Herstellername | Spezifiziert Markendaten für Facebook. |
|  | Produkttyp-Feld | Google Produktkategorie (falls verfügbar) | Spezifiziert Produkttypdaten für Facebook. |
|  | Produktbild-Feld | Kombinationsbild (falls verfügbar) | Stellt das richtige Bild für Produktvariationen sicher. |
|  | Produktbeschreibungsfeld | Beschreibung | Verwendet die vollständige Produktbeschreibung für den Feed. |
|  | Produktkurzbeschreibungsfeld | Kurzbeschreibung | Verwendet die kurze Produktbeschreibung für den Feed. |
|  | CSV-Trennzeichen | Komma (,) | Zeichen, das Werte in der CSV-Datei trennt. |
|  | Bilder aus Feed löschen | NEIN | Enthält Bildlinks im Feed (essenziell für Anzeigen). |
|  | Produkte nach ID ausschließen | Leer | Durch Kommas getrennte Liste von Produkt-IDs, die aus dem Feed ausgeschlossen werden sollen. |
|  | Feed generieren Schaltfläche | Nach Abschluss der Einstellungen klicken | Erstellt die CSV-Produktkatalogdatei. |
|  | Feed herunterladen Schaltfläche | Nach der Generierung klicken | Lädt die CSV-Datei auf Ihren Computer herunter. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine generierte Feed-Datei ist leer oder enthält nur sehr wenige Produkte.**
A:

- **Überprüfen Sie „Nur aktive Produkte exportieren“ und „Nur vorrätige Produkte exportieren“:** Stellen Sie sicher, dass diese nicht zu restriktiv sind, wenn Sie viele Produkte erwarten.
- **Überprüfen Sie die ausgewählte Sprache und Währung:** Stellen Sie sicher, dass Produkte für die ausgewählte Sprache existieren und Preise in der ausgewählten Währung haben.
- **Überprüfen Sie die Produktsichtbarkeit:** Sind Ihre Produkte im ausgewählten Shop-Kontext (wenn Sie Multi-Store aktiviert haben) tatsächlich sichtbar?
- **Smarty-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal können alte Daten stören.

**F: Facebook lehnt meinen Feed ab oder zeigt Fehler an.**
A:

- **Überprüfen Sie das CSV-Trennzeichen:** Stellen Sie sicher, dass es den Erwartungen von Facebook entspricht (normalerweise ein Komma).
- **Überprüfen Sie die Fehlermeldungen von Facebook:** Der Facebook Business Manager bietet detaillierte Fehlerberichte. Achten Sie genau darauf, welche Felder Probleme verursachen (z. B. fehlende Bildlinks, ungültige Preise).
- **Überprüfen Sie die Bildlinks:** Stellen Sie sicher, dass Ihre Produktbilder öffentlich zugänglich sind und die URLs korrekt sind. Wenn Sie SSL (HTTPS) verwenden, stellen Sie sicher, dass die Bildlinks ebenfalls HTTPS sind.
- **Auf Sonderzeichen prüfen:** Manchmal können ungewöhnliche Zeichen in Produktnamen oder -beschreibungen zu Parsing-Problemen führen.
- **Eindeutige IDs sicherstellen:** Die Einstellung „Produktidentifikation“ ist entscheidend. Jeder Artikel im Feed (insbesondere Kombinationen) benötigt eine eindeutige `id`.

**F: Meine Produktbilder werden im Facebook-Feed nicht angezeigt.**
A:

- **Überprüfen Sie die Einstellung „Bilder aus Feed löschen“:** Stellen Sie sicher, dass diese auf **NEIN** gesetzt ist.
- **Überprüfen Sie die Bild-URLs:** Öffnen Sie einige Bildlinks aus der generierten CSV-Datei in Ihrem Browser. Werden sie korrekt geladen? Sind sie von außerhalb Ihres Netzwerks zugänglich?
- **Kombinationsbilder:** Wenn Sie Kombinationsbilder verwenden, stellen Sie sicher, dass diese Ihren Produktkombinationen in PrestaShop korrekt zugewiesen sind.

**F: Wie oft sollte ich einen neuen Feed generieren und hochladen?**
A:

- Es hängt davon ab, wie häufig sich Ihr Produktkatalog ändert.
- **Täglich:** Für die meisten Shops empfohlen, insbesondere wenn Sie häufige Lagerbestandsänderungen, Preisaktualisierungen oder neue Produktzugänge haben.
- **Wöchentlich:** Akzeptabel für Shops mit einem sehr stabilen Katalog.
- **Automatischer Abruf:** Die beste Praxis ist es, Facebook so einzurichten, dass der Feed automatisch von einer URL abgerufen wird. Dieses Modul generiert den Feed bei Bedarf, daher benötigen Sie möglicherweise einen Cron-Job, um die Generierung auszulösen und die Datei unter einer konsistenten URL für Facebook zum Abrufen verfügbar zu machen.

**F: Das Modul wird nicht in meiner Modulliste angezeigt oder ich kann es nicht konfigurieren.**
A:

- **Erneut hochladen:** Versuchen Sie, die Modul-ZIP-Datei über den Modul-Manager erneut hochzuladen.
- **Berechtigungen überprüfen:** Stellen Sie sicher, dass der Modulordner (`/modules/pixelfeed/`) und seine Inhalte die richtigen Dateiberechtigungen haben (normalerweise 755 für Ordner, 644 für Dateien).
- **Fehlerprotokolle:** Überprüfen Sie Ihren PrestaShop-Debug-Modus und die Server-Fehlerprotokolle auf PHP-Fehler während der Installation oder Konfiguration.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Katalog für Facebook Pixel Dynamic Ads exportieren“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) und konzentriert sich hauptsächlich auf administrative Funktionen zur Generierung eines Produkt-Feeds. Es nutzt die Kernklassen `Product` und `Combination` von PrestaShop, um Daten zu extrahieren, und formatiert diese Daten dann in eine CSV-Datei, die mit der Katalogspezifikation für Facebook Dynamic Ads kompatibel ist. Die Hauptmoduldatei (`index.php`) dient als Einstiegspunkt für die Konfiguration, während dedizierte Admin-Controller die komplexe Logik der Datenextraktion und Feed-Generierung handhaben. Front-Controller sind vorhanden, wahrscheinlich für die Bereitstellung des generierten Feeds oder für spezifische AJAX-Anfragen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/feed.php`
  - **Klassenname:** `PixelfeedFeedModuleFrontController` (oder ähnlich, erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die Bereitstellung der generierten CSV-Feed-Datei über eine öffentliche URL verantwortlich. Er würde Anfragen an eine bestimmte Route (z. B. `ihrshop.com/module/pixelfeed/feed`) bearbeiten und den CSV-Inhalt direkt ausgeben. Dies ist entscheidend für die geplanten Abrufe von Facebook.
- `controllers/front/index.php`
  - **Klassenname:** `PixelfeedIndexModuleFrontController` (oder ähnlich, erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dies könnte ein Platzhalter oder ein Controller für eine sehr spezifische, nicht-feed-bezogene Front-Office-Aktion sein, obwohl die Hauptfunktion des Moduls die Back-Office-Feed-Generierung ist. Es könnte potenziell AJAX-Anfragen im Zusammenhang mit dem Feed-Status oder anderen kleineren Interaktionen bearbeiten.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminExportProductsFeed.php`
  - **Klassenname:** `AdminExportProductsFeedController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Dieser Controller ist das Herzstück der administrativen Schnittstelle des Moduls. Es ist der Hauptkonfigurationsbildschirm, auf dem Händler mit Einstellungen interagieren und die Feed-Generierung auslösen.
  - **Verwaltete Entität:** Es verwaltet nicht direkt eine einzelne `ObjectModel`-Entität, sondern orchestriert den Abruf und die Verarbeitung von `Product`- und `Combination`-Daten aus dem PrestaShop-Kern.
  - **Schlüsselfunktionalität:**
    - Handhabt die Anzeige des Konfigurationsformulars (`renderForm`).
    - Verarbeitet Formularübermittlungen (`postProcess`), um Moduleinstellungen (z. B. Sprache, Währung, Exportoptionen) zu speichern.
    - Löst die Datenextraktions- und CSV-Generierungslogik aus.
    - Verwaltet den Ausschluss von Produkten.
    - Die im Moduldossier aufgeführten Formularfelder und Spalten (`ID`, `item_group_id`, `Title` usw.) stellen die *Ausgabestruktur* des Feeds dar, nicht unbedingt direkte Eingabefelder im Admin-Formular, obwohl viele Einstellungen diese Ausgabespalten beeinflussen.
    - Zugehörige Konfigurationsschlüssel: `pf_tree`, `PS_LANG_DEFAULT`, `PS_CURRENCY_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `pf_pixelfeed_products`, `pf_remember_settings`, `pf_export_not_group_combinations`, `pf_export_active`, `pf_export_instock`, `pf_export_identification`, `pf_export_category`, `pf_export_manufacturers_default`, `pf_export_type`, `pf_export_img`, `pf_export_manufacturers`, `pf_export_description_what`, `pf_export_short_description_what`, `pf_export_suppliers`, `pf_export_delimiter`, `pf_delete_images`. Dies sind die `Configuration`-Schlüssel, die zum Speichern der Moduleinstellungen verwendet werden.
- `controllers/admin/index.php`
  - **Klassenname:** `PixelfeedAdminIndexController` (oder ähnlich, erweitert `ModuleAdminController`)
  - **Tab-Name:** Dies könnte ein sekundärer Admin-Controller sein, möglicherweise für ein Dashboard oder eine einfachere Verwaltungsansicht, oder es könnte eine veraltete Datei sein. Da der `AdminExportProductsFeedController` die Hauptlogik handhabt, könnte diese `index.php` eine Weiterleitung oder eine sehr einfache Landingpage innerhalb des Admin-Bereichs sein.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies impliziert, dass die Kernlogik für die Datenextraktion und Feed-Generierung wahrscheinlich in der Hauptmoduldatei (`pixelfeed/index.php`) und dem `AdminExportProductsFeedController` enthalten ist. Es verwendet direkt die PrestaShop-Kernklassen `Product`, `Combination`, `Category`, `Manufacturer`, `Image` und `Tools`.

### 4.4 JavaScript-Assets (`views/js/`)

- `pixelfeed/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Bietet wahrscheinlich eine Autocomplete-Funktion für Eingabefelder innerhalb der Admin-Konfiguration, wie z. B. das Feld „Produkte nach ID ausschließen“. Es würde an Eingabeelemente gebunden, AJAX-Aufrufe zur Produktsuche tätigen und Vorschläge anzeigen.
- `pixelfeed/views/js/admin-app.js`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Dies ist die Haupt-JavaScript-Datei für die Admin-Oberfläche des Moduls. Sie würde Folgendes behandeln:
    - Formularvalidierung und -übermittlung.
    - AJAX-Anfragen zur Generierung des Feeds (an `AdminExportProductsFeedController`).
    - Anzeige von Ladeindikatoren oder Erfolgs-/Fehlermeldungen.
    - Potenziell dynamische Aktualisierungen der Benutzeroberfläche basierend auf ausgewählten Optionen.
    - Interaktionen mit Fancybox (falls für die Kategorieauswahl oder Ähnliches verwendet).

### 4.5 CSS-Stylesheets (`views/css/`)

- `pixelfeed/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Funktionalität:** Gestaltet das Autocomplete-Dropdown und die Eingabefelder und sorgt für ein konsistentes Erscheinungsbild im PrestaShop-Back-Office.
- `pixelfeed/views/admin-theme.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Funktionalität:** Bietet allgemeines Styling für die Konfigurationsseite des Moduls und stellt sicher, dass es gut in das PrestaShop-Back-Office-Theme integriert ist. Dies kann Layout, Schaltflächenstile und Formularelement-Styling umfassen.
- `pixelfeed/views/css/admin-app.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Funktionalität:** Spezifisches Styling für die benutzerdefinierten UI-Elemente des Moduls, wie z. B. den Feed-Generierungsfortschritt, Warnungen oder benutzerdefinierte Widgets auf der Konfigurationsseite.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet hauptsächlich Smarty-Templates für seine Back-Office-Oberfläche.

#### Admin-Templates (`views/templates/admin/`)

- `pixelfeed/views/templates/admin/dashboard.tpl`
  - **Zweck:** Könnte eine Dashboard-ähnliche Übersicht für das Modul sein, die möglicherweise den Feed-Status, das letzte Generierungsdatum oder Schnelllinks anzeigt.
- `pixelfeed/views/templates/admin/feeds.tpl`
  - **Zweck:** Wahrscheinlich das Haupttemplate zur Anzeige der Feed-Generierungsoptionen und -ergebnisse, möglicherweise einschließlich einer Liste generierter Feeds oder eines Protokolls.
- `pixelfeed/views/templates/admin/form-chrome.tpl`
  - **Zweck:** Ein generischer Wrapper oder ein strukturelles Template für Formulare innerhalb der Admin-Oberfläche, das ein konsistentes Layout und Styling gewährleistet.
- `pixelfeed/views/templates/admin/layout.tpl`
  - **Zweck:** Das übergeordnete Layout-Template für die Admin-Seiten des Moduls, das die Gesamtstruktur, den Header und den Footer definiert.

#### Andere Templates (`views/`)

- `pixelfeed/lib/searchTool/views/scripts.tpl`
  - **Zweck:** Enthält JavaScript für das Suchwerkzeug, wahrscheinlich am Ende des HTML-Bodys oder innerhalb eines bestimmten Abschnitts gerendert.
- `pixelfeed/views/categories-fancybox.tpl`
  - **Zweck:** Template für ein Fancybox-Modal, möglicherweise zur Auswahl von Kategorien, die in den Feed aufgenommen/ausgeschlossen werden sollen, oder zur Anzeige von Kategoriebäumen.
- `pixelfeed/views/exclude-products.tpl`
  - **Zweck:** Template für den Abschnitt, in dem Produkte nach ID ausgeschlossen werden können, möglicherweise einschließlich des Autocomplete-Eingabefeldes.
- `pixelfeed/views/google_lang_links.tpl`
  - **Zweck:** Könnte sich auf die Anzeige sprachspezifischer Links oder Informationen beziehen, möglicherweise für Google-Produktkategorien.
- `pixelfeed/views/returnAlert.tpl`
  - **Zweck:** Ein Template zur Anzeige von Erfolgs-, Fehler- oder Warnmeldungen an den Benutzer in der Admin-Oberfläche.
- `pixelfeed/views/script-fancybox.tpl`
  - **Zweck:** Enthält JavaScript für die Fancybox-Integration, oft für modale Popups.
- `pixelfeed/views/script.tpl`
  - **Zweck:** Allgemeine JavaScript-Einbindungen für die Admin-Seiten des Moduls, möglicherweise für globale Variablen oder Initialisierungen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Moduldossier weist keine benutzerdefinierten SQL-Dateien aus, was darauf hindeutet, dass es keine eigenen dedizierten Datenbanktabellen erstellt. Alle Konfigurationseinstellungen werden in der PrestaShop-Tabelle `ps_configuration` unter Schlüsseln mit dem Präfix `pf_` gespeichert (z. B. `pf_export_active`, `pf_export_delimiter`).

#### Registrierte Hooks-Tabelle

Die Hauptfunktion des Moduls ist der Datenexport, nicht die Front-Office-Anzeige. Die aufgeführten Front-Office-Hooks (Header, Spalten, Produkt, Footer) werden von diesem Modul wahrscheinlich *nicht* für die direkte visuelle Ausgabe verwendet. Stattdessen könnten sie registriert sein für:

- **`displayHeader`**: Zum Einbinden notwendiger JavaScript- oder CSS-Assets für den Front-Office-Feed-Controller des Moduls (falls dieser den Feed direkt bereitstellt).
- **`action*`-Hooks**: Das Modul verwendet wahrscheinlich `action`-Hooks (z. B. `actionProductUpdate`, `actionProductAdd`) intern, um Caches zu leeren oder Aufforderungen zur erneuten Generierung im Back Office auszulösen, wenn sich Produktdaten ändern, obwohl diese im Dossier nicht explizit aufgeführt sind. Die Kernlogik des Moduls zur Generierung des Feeds wird typischerweise manuell oder über einen Cron-Job ausgelöst, nicht direkt durch einen Front-Office-Hook.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich der Front-Office-Seiten. | Potenziell zum Laden von JS/CSS für die Front-Office-Feed-Bereitstellung oder für sehr spezifische, nicht-visuelle Integrationen. |
| `displayRightColumn` / `displayLeftColumn` | In den Seitenleisten der Front-Office-Seiten. | Unwahrscheinlich für die Kernfunktion dieses Moduls verwendet; möglicherweise für einen Debug-Block oder eine sehr spezielle Funktion, die nicht zentral für die Feed-Generierung ist. |
| `displayProductAdditionalInfo` / `displayProductButtons` (Produktseite) | Auf Produktseiten. | Unwahrscheinlich für die Kernfunktion dieses Moduls verwendet. |
| `displayFooter` | Im Footer der Front-Office-Seiten. | Unwahrscheinlich für die Kernfunktion dieses Moduls verwendet. |
| (Implizit) `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Nach Produktänderungen im BO. | Zum Invalidieren von zwischengespeicherten Feed-Daten oder zur Aufforderung an den Administrator zur erneuten Feed-Generierung. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Katalog für Facebook Pixel Dynamic Ads exportieren“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
