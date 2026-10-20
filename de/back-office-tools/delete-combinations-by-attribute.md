---
title: "Kombinationen nach Attribut löschen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kombinationen nach Attribut löschen“ von MyPresta.eu."
sidebar:
  label: "Kombinationen nach Attribut löschen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Delete combinations by attribute auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/delete-combinations-by-attribute.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/delete-combinations-by-attribute/)
>
> ---


# Kombinationen nach Attribut löschen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Kombinationen nach Attribut löschen“. Hier finden Sie alle Tools zum Auswählen und Löschen von Kombinationen.

#### **Oberer Bereich: Modul-Updates & Informationen**

Dieser Bereich zeigt in der Regel Informationen zu Modul-Updates und -Versionen von MyPresta.eu an.

- **Was diese Einstellung bewirkt:** Bietet Informationen zu verfügbaren Updates für das Modul, um sicherzustellen, dass Sie die neueste Version für Fehlerbehebungen und neue Funktionen verwenden.
- **Auswirkung der Änderung dieser Einstellung:** Dies sind Informationsfelder und haben keine direkten Einstellungen, die Sie ändern können. Sie zeigen lediglich Daten an.
- **Empfohlener Wert:** Halten Sie Ihr Modul auf dem neuesten Stand.
- **Händlerszenario / Beispiel:** Sie sehen eine Benachrichtigung, dass eine neue Version `1.3.1` verfügbar ist. Sie würden diese dann von MyPresta.eu herunterladen und das Modul aktualisieren.

#### **Hauptkonfigurationsoptionen**

1. **Attributwert**

   - **Was diese Einstellung bewirkt:** Dies ist der primäre Filter. Er ermöglicht Ihnen die Auswahl eines spezifischen Attributwerts (z. B. „Rot“, „Klein“, „Baumwolle“), den Sie für die Löschung anvisieren möchten. Das Modul sucht nach allen Produktkombinationen, die diesen ausgewählten Attributwert enthalten.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ein Wert ausgewählt ist:* Das Modul identifiziert alle Kombinationen in Ihrem Shop, die diesen spezifischen Attributwert verwenden.
     - *Wenn kein Wert ausgewählt ist:* Sie können den Löschvorgang nicht fortsetzen, da das Modul nicht weiß, welche Kombinationen angesprochen werden sollen.
   - **Empfohlener Wert:** Wählen Sie den genauen Attributwert aus, für den Sie Kombinationen entfernen möchten.
   - **Händlerszenario / Beispiel:** Sie haben alle „Orange“ farbigen Produkte eingestellt. Sie würden „Orange“ aus diesem Dropdown auswählen, um alle Kombinationen mit „Orange“ als eines ihrer Attribute anzusprechen.
2. **Menge**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, Kombinationen basierend auf ihrer aktuellen Lagerbestandsmenge zu filtern. Sie können wählen, Kombinationen nur dann zu löschen, wenn ihre Menge unter, gleich oder über einer bestimmten Zahl liegt.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn „Was zu tun ist“ auf „weniger als“ und „Menge“ auf 5 eingestellt ist:* Nur Kombinationen mit einer Lagerbestandsmenge von 4 oder weniger werden für die Löschung berücksichtigt.
     - *Wenn „Was zu tun ist“ auf „gleich“ und „Menge“ auf 0 eingestellt ist:* Nur Kombinationen mit genau 0 Lagerbestand werden berücksichtigt.
   - **Empfohlener Wert:** Oft verwendet mit „gleich“ und „0“, um nicht vorrätige Kombinationen zu bereinigen.
   - **Händlerszenario / Beispiel:** Sie möchten alle Kombinationen von „Orange“-Produkten entfernen, die derzeit nicht vorrätig sind. Sie würden „Orange“ unter „Attributwert“ auswählen und dann „Was zu tun ist“ auf „gleich“ und „Menge“ auf „0“ setzen.
3. **Was zu tun ist (mit Menge)**

   - **Was diese Einstellung bewirkt:** Dieses Dropdown arbeitet in Verbindung mit dem Feld „Menge“, um die Bedingung für die Bestandsfilterung zu definieren. Optionen umfassen typischerweise „weniger als“, „gleich“, „größer als“.
   - **Auswirkung der Änderung dieser Einstellung:** Es ändert die Vergleichslogik für den „Menge“-Filter.
   - **Empfohlener Wert:** „gleich“ ist üblich, um nicht vorrätige Artikel anzusprechen.
   - **Händlerszenario / Beispiel:** Um Kombinationen mit sehr geringem Lagerbestand zu entfernen, könnten Sie „weniger als“ wählen und „Menge“ auf „3“ setzen.
4. **Liste der Referenzcodes**

   - **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, eine Liste von Produktreferenzcodes (SKUs) anzugeben, die in den Löschvorgang einbezogen oder davon ausgeschlossen werden sollen. Dies ist nützlich, wenn Sie nur eine Untermenge von Produkten beeinflussen möchten.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn „Codefeld“ „Referenz“ ist und „Was zu tun ist“ „einschließen“ ist:* Nur Kombinationen, die zu Produkten mit diesen spezifischen Referenzcodes gehören, werden betroffen sein.
     - *Wenn „Codefeld“ „Referenz“ ist und „Was zu tun ist“ „ausschließen“ ist:* Kombinationen, die zu Produkten mit diesen spezifischen Referenzcodes gehören, werden übersprungen.
   - **Empfohlener Wert:** Verwenden Sie dies, um den Umfang der Löschung auf bestimmte Produkte einzugrenzen. Geben Sie einen Code pro Zeile ein.
   - **Händlerszenario / Beispiel:** Sie möchten „Orange“-Kombinationen nur von Produkten mit den Referenzcodes `PROD-A`, `PROD-B` und `PROD-C` entfernen. Sie würden diese Codes eingeben, „Referenz“ für „Codefeld“ und „einschließen“ für „Was zu tun ist“ auswählen.
5. **Codefeld**

   - **Was diese Einstellung bewirkt:** Definiert, auf welches Produktidentifikationsfeld sich die „Liste der Codes“ bezieht. Optionen sind typischerweise „Referenz“ (SKU) oder „EAN13“ (Barcode).
   - **Auswirkung der Änderung dieser Einstellung:** Ändert, wie das Modul die in „Liste der Codes“ eingegebenen Codes interpretiert.
   - **Empfohlener Wert:** „Referenz“ für interne SKUs, „EAN13“ für Barcodes.
   - **Händlerszenario / Beispiel:** Wenn Ihre Liste EAN13-Barcodes enthält, wählen Sie hier „EAN13“.
6. **Liste der Codes (Was zu tun ist)**

   - **Was diese Einstellung bewirkt:** Bestimmt, ob die „Liste der Referenzcodes“ (oder EAN-Codes) in den Löschvorgang *einbezogen* (nur von diesen Produkten löschen) oder *ausgeschlossen* (von allen Produkten löschen, AUSSER diesen) werden sollen.
   - **Auswirkung der Änderung dieser Einstellung:** Steuert den Umfang der von der Löschung betroffenen Produkte.
   - **Empfohlener Wert:** „einschließen“ für gezielte Löschungen, „ausschließen“ für breite Löschungen mit Ausnahmen.
   - **Händlerszenario / Beispiel:** Sie möchten „Orange“-Kombinationen von allen Produkten löschen, *außer* Ihrem Bestseller `BESTSELLER-01`. Sie würden `BESTSELLER-01` in die „Liste der Codes“ eingeben und hier „ausschließen“ auswählen.
7. **Produkt**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, ein bestimmtes Produkt anhand seines Namens auszuwählen. Wenn ausgewählt, gilt die Löschung *nur* für Kombinationen dieses einzelnen Produkts, wodurch alle anderen produktbezogenen Filter überschrieben werden.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ein Produkt ausgewählt ist:* Das Modul verarbeitet nur Kombinationen, die zu diesem spezifischen Produkt gehören.
     - *Wenn leer gelassen:* Das Modul wendet die Löschkriterien auf alle Produkte in Ihrem Shop an (vorbehaltlich anderer Filter wie „Liste der Referenzcodes“).
   - **Empfohlener Wert:** Verwenden Sie dies für hochgradig gezielte Löschungen an einem einzelnen Produkt.
   - **Händlerszenario / Beispiel:** Sie möchten „Orange“-Kombinationen nur von Ihrem Produkt „Sommerkleid“ entfernen. Sie würden hier „Sommerkleid“ auswählen.

#### **Aktionsschaltfläche**

- **Schaltfläche „Ausgewählte Kombinationen löschen“**
  - **Was diese Schaltfläche bewirkt:** Dies ist die Aktionsschaltfläche, die beim Klicken den Löschvorgang basierend auf allen oben festgelegten Kriterien ausführt.
  - **Auswirkung des Klickens auf diese Schaltfläche:** **Diese Aktion ist irreversibel!** Alle Produktkombinationen, die Ihrem ausgewählten „Attributwert“, den „Menge“-Filtern und den „Produkt“- oder „Referenz-/EAN“-Filtern entsprechen, werden dauerhaft aus Ihrer Datenbank gelöscht. Dies umfasst deren zugehörigen Lagerbestand, Bilder und spezifische Preise.
  - **Empfohlener Wert:** **Führen Sie IMMER ein vollständiges Datenbank-Backup durch, bevor Sie auf diese Schaltfläche klicken.** Überprüfen Sie alle Ihre Einstellungen sorgfältig.
  - **Händlerszenario / Beispiel:** Nachdem Sie sorgfältig „Farbe: Orange“ ausgewählt, „Menge: gleich 0“ eingestellt und Ihr Backup bestätigt haben, klicken Sie auf diese Schaltfläche, um alle nicht vorrätigen orangefarbenen Kombinationen zu entfernen.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Attributwert** | *Spezifischen Wert auswählen* | Primärer Filter: Löscht Kombinationen, die diesen Attributwert enthalten. |
| Modulkonfiguration | **Menge** | *0 oder gewünschte Zahl* | Filtert Kombinationen basierend auf ihrer Lagerbestandsmenge. |
| Modulkonfiguration | **Was zu tun ist (mit Menge)** | *gleich* | Definiert die Vergleichslogik für den „Menge“-Filter (weniger als, gleich, größer als). |
| Modulkonfiguration | **Liste der Referenzcodes** | *Leer oder spezifische Codes* | Liste der Produktreferenz- (SKU) oder EAN-Codes zum Einschließen/Ausschließen. Einer pro Zeile. |
| Modulkonfiguration | **Codefeld** | *Referenz* | Gibt an, ob sich die „Liste der Codes“ auf „Referenz“ oder „EAN13“ bezieht. |
| Modulkonfiguration | **Liste der Codes (Was zu tun ist)** | *einschließen* | Bestimmt, ob die gelisteten Codes in die Löschung einbezogen oder davon ausgeschlossen werden. |
| Modulkonfiguration | **Produkt** | *Leer oder spezifischer Produktname* | Zielt die Löschung auf ein einzelnes Produkt ab und überschreibt andere Produktfilter. |
| Modulkonfiguration | **Ausgewählte Kombinationen löschen** | **Vorsichtig klicken!** | Führt die irreversible Löschung von Kombinationen basierend auf allen Kriterien aus. **Zuerst Backup erstellen!** |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe auf „Löschen“ geklickt, aber es ist nichts passiert, oder nicht alle Kombinationen wurden gelöscht.**
A:

- **Überprüfen Sie Ihre Filter:** Überprüfen Sie alle Ihre Einstellungen erneut: „Attributwert“, „Menge“-Bedingungen, „Liste der Codes“ (einschließen/ausschließen) und „Produkt“-Auswahl. Selbst eine kleine Diskrepanz kann verhindern, dass Kombinationen angesprochen werden.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache Anzeigeprobleme verursachen. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
- **Modulkonflikte:** Ein anderes Modul könnte stören. Versuchen Sie, andere Module nacheinander zu deaktivieren (insbesondere solche, die mit der Produktverwaltung oder Kombinationen zusammenhängen), um zu sehen, ob sich das Problem löst.

**F: Ich habe versehentlich Kombinationen gelöscht, die ich nicht löschen wollte. Kann ich sie wiederherstellen?**
A: **Nein, nicht direkt über das Modul.** Deshalb ist ein Backup so wichtig. Wenn Sie ein aktuelles Datenbank-Backup haben, können Sie Ihren Shop auf den Zustand vor der Löschung zurücksetzen. Wenn Sie kein Backup haben, müssen Sie die Kombinationen manuell neu erstellen.

**F: Der Attributwert, den ich löschen möchte, wird im Dropdown nicht angezeigt.**
A:

- **Überprüfen Sie, ob er existiert:** Stellen Sie sicher, dass der Attributwert tatsächlich in Ihrem PrestaShop-Katalog existiert und mindestens einem Produkt zugewiesen ist. Gehen Sie zu **Katalog > Attribute & Merkmale**, um dies zu überprüfen.
- **Sprache:** Stellen Sie sicher, dass Sie das Back Office in der richtigen Sprache anzeigen, wenn der Attributwertname sprachabhängig ist.

**F: Kann ich Kombinationen basierend auf Merkmalen anstelle von Attributen löschen?**
A: Nein, dieses Modul ist speziell für die Arbeit mit **Attributen und Attributwerten** konzipiert. Merkmale sind ein anderes Konzept in PrestaShop und werden von diesem Modul nicht zum Löschen unterstützt.

**F: Werden beim Löschen von Kombinationen auch die zugehörigen Bilder oder spezifischen Preise gelöscht?**
A: Ja, wenn eine Kombination gelöscht wird, werden alle direkt mit dieser spezifischen Kombination verknüpften Daten (wie ihr einzigartiges Bild, spezifische Preisregeln für diese Kombination und ihre Lagerbestandsmenge) ebenfalls entfernt. Das Hauptproduktbild und die allgemeinen produktspezifischen Preise bleiben erhalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `delcombs` ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Back-Office-Funktionalität konzentriert. Es hält sich an die PrestaShop-Modulstruktur und verwendet die `Module`-Klasse für Installation, Deinstallation und Konfiguration. Seine Kernlogik befindet sich in der `getContent()`-Methode der Hauptmoduldatei, wo es die Formularübermittlung, Datenvalidierung und die Ausführung von Datenbankoperationen zum Löschen von Produktkombinationen handhabt. Es führt keine benutzerdefinierten Front-Office-Controller oder komplexen ObjectModels ein, sondern verlässt sich stattdessen auf direkte Datenbankabfragen und PrestaShops Kernklassen `Product` und `Combination` für die Datenmanipulation.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Alle Funktionen sind auf das Back Office beschränkt.
- **Back-Office-Admin-Controller**: Keine. Die Konfigurations- und Verarbeitungslogik des Moduls wird innerhalb der `getContent()`-Methode der Hauptmodulklasse behandelt, die als Teil der Standard-Modulkonfigurationsseite gerendert wird.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Es interagiert direkt mit PrestaShops Kernklassen `Product` und `Combination` und führt direkte Datenbankabfragen für Effizienz bei Massenlöschvorgängen durch.

### 4.4 JavaScript-Assets (`views/js/`)

- `delcombs/views/js/delcombs-admin.js`
  - **Umfang:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Dieses Skript verarbeitet wahrscheinlich dynamisches Verhalten auf dem Konfigurationsformular des Moduls. Dies könnte umfassen:
    - AJAX-Aufrufe zum Suchen von Produkten oder Attributen (z. B. für das Feld „Produkt“-Auswahl).
    - Bedingte Anzeige von Formularfeldern basierend auf Benutzerauswahlen (z. B. Anzeigen/Ausblenden von Mengenfiltern).
    - Eingabevalidierung vor dem Absenden des Formulars.
    - Bestätigungsdialoge vor der Ausführung der Löschaktion.
    - Interaktionen mit dem `searchTool` (wahrscheinlich eine benutzerdefinierte Suchkomponente für Produkte/Attribute).

### 4.5 CSS-Stylesheets (`views/css/`)

- `delcombs/views/css/delcombs-admin.css`
  - **Umfang:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Bietet Styling für die Konfigurationsformular-Elemente des Moduls, um eine konsistente und benutzerfreundliche Oberfläche innerhalb des PrestaShop Back Office zu gewährleisten.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf spezifische IDs oder Klassen innerhalb der `getContent()`-Ausgabe des Moduls ab, wie Formulargruppen, Eingabefelder und möglicherweise die `searchTool`-Komponente. Entwickler können diese Stile in ihren benutzerdefinierten Admin-Themes oder durch Hinzufügen von CSS mit höherer Spezifität überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `delcombs/lib/searchTool/views/scripts.tpl`
  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Template enthält wahrscheinlich JavaScript-Code oder Smarty-Variablen, die von einer generischen Suchwerkzeugkomponente benötigt werden, die innerhalb des Moduls verwendet wird. Es könnte Suchfelder initialisieren, AJAX-Endpunkte für Suchanfragen definieren oder clientseitige Datenverarbeitung für Suchergebnisse einrichten. Es wird wahrscheinlich vom Hauptkonfigurationstemplate eingebunden.
- `delcombs/views/templates/admin/tabs.tpl`
  - **Umfang:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Dies ist das Haupt-Smarty-Template, das von der `getContent()`-Methode des `delcombs`-Moduls gerendert wird. Es strukturiert das gesamte Konfigurationsformular, einschließlich:
    - Der verschiedenen Eingabefelder (Dropdowns für Attribute, Textbereiche für Codes, Mengeneingaben).
    - Der Schaltfläche „Ausgewählte Kombinationen löschen“.
    - Aller Informationsmeldungen oder Warnungen.
    - Es enthält wahrscheinlich `scripts.tpl` für die Suchfunktionalität.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es arbeitet direkt mit den Kern-PrestaShop-Tabellen, hauptsächlich:
    - `ps_product_attribute` (Haupttabelle für Kombinationen)
    - `ps_product_attribute_combination` (verknüpft Kombinationen mit Attributwerten)
    - `ps_product_attribute_shop` (shop-spezifische Kombinationsdaten)
    - `ps_stock_available` (Lagerbestand für Kombinationen)
    - `ps_specific_price` (spezifische Preise für Kombinationen)
    - `ps_image` (Bilder, die mit Kombinationen verknüpft sind)
    - `ps_product` (zum Filtern nach Produkt-ID, Referenz, EAN)
    - `ps_attribute_lang`, `ps_attribute_group_lang` (zum Anzeigen von Attributnamen in den Dropdowns)
  - Konfigurationseinstellungen werden in `ps_configuration` mit Schlüsseln wie `delcombs_attribute`, `delcombs_product`, `delcombs_qty_wtd`, `delcombs_qty`, `delcombs_ref_codes`, `delcombs_ref_type`, `delcombs_ean_codes`, `delcombs_ean_type`, `delcombs_ean_field`, `delcombs_product_mode` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine Front-Office- oder Back-Office-Anzeige-Hooks. Seine Funktionalität ist vollständig in seiner Konfigurationsseite enthalten.
  Es könnte intern Aktions-Hooks verwenden (z. B. `actionProductUpdate` oder `actionAttributeCombinationSave`), um den Cache zu leeren oder auf Änderungen zu reagieren, diese sind jedoch nicht explizit als registrierte Hooks für die externe Modulinteraktion aufgeführt.
  Die Kernlogik des Moduls wird durch die Formularübermittlung innerhalb seiner `getContent()`-Methode ausgelöst, nicht durch einen Standard-PrestaShop-Hook.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Kombinationen nach Attribut löschen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
