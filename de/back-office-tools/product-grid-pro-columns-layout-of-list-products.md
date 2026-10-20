---
title: "Product Grid Pro - Spalten & Layout von Listenprodukten - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Product Grid Pro - Spalten & Layout von Listenprodukten“ von MyPresta.eu."
sidebar:
  label: "Product Grid Pro - Spalten & Layout von Listenprodukten"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product Grid Pro - columns & layout of list products auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/product-grid-pro-columns-layout-of-list-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/product-grid-pro-columns-layout-of-list-products/)
>
> ---


# Product Grid Pro - Spalten & Layout von Listenprodukten

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Installation hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul funktioniert hauptsächlich, indem es den Standard-PrestaShop-Produktlisten-Controller überschreibt. Seine Konfiguration wird hauptsächlich direkt im Bereich „Katalog > Produkte“ selbst verwaltet, mit einer einfachen „Zurücksetzen“-Option, die in der Hauptkonfiguration des Moduls verfügbar ist.

### 2.1 Modulkonfigurationsseite (Back-Office > Module > Konfigurieren)

Um darauf zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Product Grid Pro“ und klicken Sie auf „Konfigurieren“.

Dieser Bildschirm bietet eine einzige, entscheidende Option:

-   **Modulkonfiguration zurücksetzen**
    -   **Was diese Einstellung bewirkt:** Diese Schaltfläche ermöglicht es Ihnen, alle vom Modul vorgenommenen Änderungen auf die Standardeinstellungen zurückzusetzen. Das bedeutet, dass jede benutzerdefinierte Spaltenreihenfolge, Sichtbarkeit oder hinzugefügte Spalten, die Sie in der Liste „Katalog > Produkte“ konfiguriert haben, auf den ursprünglichen Zustand des Moduls zurückgesetzt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Beim Klicken:* Das Modul löscht seine gespeicherten Präferenzen für Ihr Produktgitter-Layout. Dies ist nützlich, wenn Sie viele Änderungen vorgenommen haben und neu beginnen möchten, oder wenn Sie auf ein unerwartetes Anzeigeproblem stoßen und Konfigurationsprobleme ausschließen möchten.
    -   **Empfohlener Wert:** Klicken Sie dies nur, wenn Sie Ihre Produktgitter-Anpassung explizit zurücksetzen möchten.
    -   **Händlerszenario / Beispiel:** Sie haben monatelang mit verschiedenen Spaltenlayouts experimentiert, und jetzt fühlt sich Ihre Produktliste überladen oder unorganisiert an. Das Klicken auf „Modulkonfiguration zurücksetzen“ bringt sie in einen sauberen, standardmäßigen Zustand zurück, sodass Sie sie von Grund auf neu konfigurieren können.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Die Kernfunktionalität von „Product Grid Pro“ wird direkt im Bereich **Katalog > Produkte** Ihres PrestaShop-Back-Office erlebt. Dieses Modul erweitert die Standardproduktliste, fügt neue Spalten hinzu und ermöglicht Ihnen die Anpassung ihres Layouts.

-   **Bildschirmname & Menüpfad:** **Katalog > Produkte**
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Neue Spalten:** Das Modul führt mehrere neue, sehr nützliche Spalten in Ihre Produktliste ein. Dazu gehören:
        -   **EAN13:** European Article Number (Barcode).
        -   **Lieferantenreferenz:** Ihre interne Referenz für das Produkt von Ihrem Lieferanten.
        -   **Hersteller:** Die Marke oder der Hersteller des Produkts.
        -   **Kombinationen:** Zeigt an, ob das Produkt Variationen (Größen, Farben usw.) hat.
        -   **Verkaufte Einheiten:** Die Gesamtzahl der verkauften Einheiten dieses Produkts.
        -   **Zuletzt verkauft:** Das Datum, an dem die letzte Einheit dieses Produkts verkauft wurde.
        -   **Gewicht:** Das Gewicht des Produkts.
        -   **Großhandel:** Der Großhandelspreis des Produkts.
        -   **Erstellt:** Das Datum, an dem das Produkt Ihrem Katalog hinzugefügt wurde.
        -   **Zustand:** Der Zustand des Produkts (Neu, Gebraucht, Generalüberholt).
        -   **Im Angebot:** Zeigt an, ob das Produkt derzeit im Angebot ist.
        -   **Zur Bestellung verfügbar:** Ob Kunden das Produkt derzeit kaufen können.
        -   **Preis anzeigen:** Ob der Preis des Produkts im Front-Office angezeigt wird.
        -   **Nur online:** Zeigt an, ob das Produkt nur online verfügbar ist (nicht in physischen Geschäften).
        -   **Sichtbarkeit:** Wo das Produkt sichtbar ist (Katalog, Suche, Beides, Keine).
        -   **Virtuell:** Zeigt an, ob das Produkt ein virtuelles Produkt ist (z. B. Download, Dienstleistung).
        -   **Paket:** Zeigt an, ob das Produkt ein Produktpaket ist.
        -   **Indiziert:** Ob das Produkt für die Suche indiziert ist.
        -   **Anpassbar:** Ob das Produkt Anpassungsfelder hat.
        -   **Lieferant:** Der spezifische Lieferant, der mit dem Produkt verbunden ist.
    -   **Spaltensichtbarkeit:** Sie können wählen, welche dieser neuen und bestehenden Spalten in Ihrer Produktliste sichtbar sind. Dies hilft, die Ansicht zu entrümpeln und sich auf das Wesentliche zu konzentrieren.
    -   **Spaltenreihenfolge (Drag & Drop):** Sie können die Spalten einfach per Drag & Drop in Ihre bevorzugte Reihenfolge bringen. So können Sie die wichtigsten Informationen für einen schnellen Zugriff nach links verschieben.
    -   **Filtern & Sortieren:** Jede der neuen Spalten unterstützt das Filtern und Sortieren, genau wie die Standard-PrestaShop-Spalten. Das bedeutet, Sie können beispielsweise Produkte nach „Verkaufte Einheiten“ sortieren, um Ihre Bestseller zu sehen, oder nach „Hersteller“ filtern, um Produkte einer bestimmten Marke zu verwalten.
-   **Auswirkung der Änderungen:**
    -   **Spalten hinzufügen/entfernen:** Ändert direkt die in Ihrer Liste „Katalog > Produkte“ angezeigten Informationen. Das Entfernen einer Spalte blendet diese Daten aus; das Hinzufügen einer Spalte macht sie sichtbar.
    -   **Spalten neu anordnen:** Ändert das visuelle Layout der Produktliste, sodass Sie Informationen priorisieren können.
    -   **Filtern/Sortieren:** Hilft Ihnen, bestimmte Produktgruppen basierend auf den von Ihnen festgelegten Kriterien schnell zu finden und zu analysieren.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
    1.  **Identifizieren Sie Ihre Schlüsselkennzahlen:** Welche Produktinformationen überprüfen Sie am häufigsten? (z. B. Lagerbestand, Preis, verkaufte Einheiten, Lieferantenreferenz).
    2.  **Aktivieren Sie wesentliche Spalten:** Gehen Sie zu **Katalog > Produkte**, suchen Sie die Spaltenanpassungsoptionen (oft ein Zahnradsymbol oder eine Schaltfläche „Spalten“) und aktivieren Sie nur die Spalten, die Sie wirklich benötigen.
    3.  **Für Effizienz anordnen:** Ziehen Sie Ihre wichtigsten Spalten auf die linke Seite des Rasters, damit sie ohne horizontales Scrollen sofort sichtbar sind.
    4.  **Filter verwenden:** Verwenden Sie beim Bestandsmanagement den Filter „Verkaufte Einheiten“, um sich langsam verkaufende Artikel zu identifizieren, oder filtern Sie nach „Zuletzt verkauft“, um Produkte zu finden, die sich seit langem nicht mehr verkauft haben.
    5.  **Regelmäßige Überprüfung:** Überprüfen Sie regelmäßig Ihre Spaltenkonfiguration, um sicherzustellen, dass sie weiterhin Ihren betrieblichen Anforderungen entspricht.

### 2.3 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | Modulkonfiguration zurücksetzen | N/A (Schaltfläche) | Setzt alle benutzerdefinierten Produktgittereinstellungen (Spaltensichtbarkeit, Reihenfolge) auf die Modulstandards zurück. Zum Neuanfang oder zur Fehlerbehebung verwenden. |
| Katalog > Produkte Raster | EAN13-Spalte | Deaktiviert | Zeigt den EAN13-Barcode für jedes Produkt an. Nützlich für Inventur und Scannen. |
| Katalog > Produkte Raster | Lieferantenreferenz-Spalte | Deaktiviert | Zeigt die interne Referenz des Lieferanten für das Produkt an. Wesentlich für die Lieferantenverwaltung. |
| Katalog > Produkte Raster | Hersteller-Spalte | Deaktiviert | Zeigt den Hersteller/die Marke des Produkts an. Nützlich für markenspezifische Verwaltung. |
| Katalog > Produkte Raster | Kombinationen-Spalte | Deaktiviert | Zeigt an, ob ein Produkt Kombinationen hat. Schnelle Überprüfung für komplexe Produkte. |
| Katalog > Produkte Raster | Verkaufte Einheiten-Spalte | Deaktiviert | Zeigt die insgesamt verkauften Einheiten für jedes Produkt an. Ideal zur Identifizierung von Bestsellern. |
| Katalog > Produkte Raster | Zuletzt verkauft-Spalte | Deaktiviert | Zeigt das Datum des letzten Verkaufs für ein Produkt an. Hilft, sich langsam verkaufende Bestände zu identifizieren. |
| Katalog > Produkte Raster | Gewicht-Spalte | Deaktiviert | Zeigt das Gewicht des Produkts an. Wichtig für Versandberechnungen. |
| Katalog > Produkte Raster | Großhandel-Spalte | Deaktiviert | Zeigt den Großhandelspreis an. Nützlich für Margenberechnungen und B2B-Shops. |
| Katalog > Produkte Raster | Erstellt-Spalte | Deaktiviert | Zeigt das Datum an, an dem das Produkt hinzugefügt wurde. Hilft, das Katalogwachstum zu verfolgen. |
| Katalog > Produkte Raster | Zustand-Spalte | Deaktiviert | Zeigt den Zustand des Produkts an (Neu, Gebraucht, Generalüberholt). Relevant für bestimmte Produkttypen. |
| Katalog > Produkte Raster | Im Angebot-Spalte | Deaktiviert | Zeigt an, ob das Produkt derzeit im Angebot ist. Schneller Überblick über Aktionen. |
| Katalog > Produkte Raster | Zur Bestellung verfügbar-Spalte | Deaktiviert | Zeigt an, ob das Produkt bestellt werden kann. Wesentlich für die Bestandsverwaltung. |
| Katalog > Produkte Raster | Preis anzeigen-Spalte | Deaktiviert | Zeigt an, ob der Preis im Front-Office sichtbar ist. |
| Katalog > Produkte Raster | Nur online-Spalte | Deaktiviert | Zeigt an, ob das Produkt ausschließlich online erhältlich ist. |
| Katalog > Produkte Raster | Sichtbarkeit-Spalte | Deaktiviert | Zeigt an, wo das Produkt sichtbar ist (Katalog, Suche, beides, keine). |
| Katalog > Produkte Raster | Virtuell-Spalte | Deaktiviert | Zeigt an, ob das Produkt virtuell ist (herunterladbar, Dienstleistung). |
| Katalog > Produkte Raster | Paket-Spalte | Deaktiviert | Zeigt an, ob das Produkt ein Paket anderer Produkte ist. |
| Katalog > Produkte Raster | Indiziert-Spalte | Deaktiviert | Zeigt an, ob das Produkt für die Suche indiziert ist. |
| Katalog > Produkte Raster | Anpassbar-Spalte | Deaktiviert | Zeigt an, ob das Produkt Anpassungsoptionen hat. |
| Katalog > Produkte Raster | Lieferant-Spalte | Deaktiviert | Zeigt den Hauptlieferanten des Produkts an. |
| Katalog > Produkte Raster | Spaltenreihenfolge (Drag & Drop) | N/A (benutzerdefiniert) | Passen Sie die visuelle Reihenfolge der Spalten für einen optimalen Arbeitsablauf an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe neue Spalten aktiviert, aber sie erscheinen nicht in der Produktliste.**
A1: Stellen Sie nach dem Aktivieren der Spalten sicher, dass Sie Ihre Änderungen speichern (falls es eine Speichern-Schaltfläche in der Spaltenanpassungsoberfläche gibt). Manchmal kann das Leeren Ihres Browser-Caches oder des Smarty-Caches von PrestaShop helfen. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.

**F2: Das Drag-and-Drop-Neuordnen funktioniert nicht, oder das Layout sieht seltsam aus.**
A2: Dies könnte ein JavaScript-Konflikt mit einem anderen Modul oder Ihrem Theme sein.
    1.  Versuchen Sie, Ihren Browser-Cache und den Smarty-Cache von PrestaShop zu leeren (**Erweiterte Einstellungen > Leistung > Cache leeren**).
    2.  Wenn das Problem weiterhin besteht, versuchen Sie, auf die Schaltfläche „Modulkonfiguration zurücksetzen“ auf der Konfigurationsseite des Moduls zu klicken (**Module > Modul-Manager > Product Grid Pro > Konfigurieren**). Dies setzt das Layout auf die Standardeinstellungen zurück und könnte den Konflikt beheben.
    3.  Wenn es immer noch problematisch ist, deaktivieren Sie vorübergehend andere Module, die ebenfalls die Produktliste oder die Admin-Oberfläche ändern, um einen Konflikt zu identifizieren.

**F3: Kann ich noch mehr benutzerdefinierte Felder zum Produktgitter hinzufügen?**
A3: Dieses Modul bietet einen vordefinierten Satz häufig angefragter Felder. Es bietet keine generische Möglichkeit, *beliebige* benutzerdefinierte Felder hinzuzufügen, die Sie möglicherweise erstellt haben (z. B. mit einem anderen Modul für benutzerdefinierte Felder). Wenn Sie ein sehr spezifisches benutzerdefiniertes Feld benötigen, wäre eine weitere kundenspezifische Entwicklung erforderlich.

**F4: Wird dieses Modul mein Back-Office verlangsamen?**
A4: Das Modul ist auf Effizienz ausgelegt. Obwohl das Hinzufügen vieler Spalten bedeutet, dass mehr Daten geladen werden, ist die Auswirkung auf die Leistung im Allgemeinen minimal und wird durch die Effizienzgewinne aufgewogen. Wenn Sie erhebliche Verlangsamungen bemerken, sollten Sie weniger kritische Spalten deaktivieren, um die geladenen Daten zu reduzieren.

**F5: Das Modul ist installiert, aber ich sehe keine neuen Optionen unter Katalog > Produkte.**
A5: Stellen Sie sicher, dass das Modul korrekt installiert und aktiviert ist. Manchmal müssen Sie nach der Installation Ihren Browser aktualisieren oder sich sogar aus- und wieder im Back-Office anmelden, damit die Änderungen wirksam werden. Überprüfen Sie auch auf Fehlermeldungen während der Installation. Wenn Sie PrestaShop 1.6 verwenden, kann die Oberfläche zur Spaltenanpassung geringfügig von 1.7/8/9 abweichen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Product Grid Pro“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Product Grid Pro“ funktioniert hauptsächlich durch das Überschreiben des Kern-`AdminProductsController` in PrestaShop. Dies ist eine gängige und leistungsstarke Technik in der PrestaShop-Modulentwicklung, die es Modulen ermöglicht, das Verhalten von Kernfunktionen zu erweitern oder zu ändern, ohne Kerndateien direkt zu modifizieren. Das Modul fügt zusätzliche Spalten, Filter und Sortierfunktionen in die Produktlistentabelle ein, indem es das `$this->fields_list`-Array innerhalb des überschriebenen Controllers manipuliert. Es verwendet auch eine dedizierte JavaScript-Datei, um das Drag-and-Drop-Neuordnen von Spalten und potenziell andere dynamische UI-Verbesserungen zu handhaben. Die Konfiguration wird in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine neuen Front-Office-Controller ein. Seine primäre Interaktion erfolgt mit dem Back-Office `AdminProductsController`.

-   **Front-Office-Controller**: Keine.
-   **Back-Office-Admin-Controller**:
    *   `myproductgridpro/override/controllers/admin/AdminProductsController.php`
        *   **Klassenname & Elternklasse**: `AdminProductsController` (überschreibt den Kern-`AdminProductsController`).
        *   **Verantwortlichkeit**: Dies ist der Kern der Modulfunktionalität. Es erweitert die Standardproduktlistenfunktionalität.
            *   Es modifiziert das `$this->fields_list`-Array, um neue Spaltendefinitionen hinzuzufügen (EAN13, Lieferantenreferenz, Hersteller, Verkaufte Einheiten, Zuletzt verkauft, Gewicht, Großhandel, Erstellt, Zustand, Im Angebot, Zur Bestellung verfügbar, Preis anzeigen, Nur online, Sichtbarkeit, Virtuell, Paket, Indiziert, Anpassbar, Lieferant).
            *   Es stellt sicher, dass diese neuen Felder sortierbar und filterbar sind.
            *   Es handhabt die Logik zum Abrufen der Daten für diese neuen Spalten aus der Datenbank.
            *   Es integriert das JavaScript für die Spaltenneuordnung und Sichtbarkeitsverwaltung.
    *   `myproductgridpro/override/controllers/admin/index.php`
        *   **Klassenname & Elternklasse**: Diese Datei ist wahrscheinlich ein Platzhalter oder ein einfacher Redirector innerhalb der Override-Struktur und enthält keine vollständige Controller-Klassendefinition für eine bestimmte Entität. Ihre Präsenz im Verzeichnis `override/controllers/admin/` deutet darauf hin, dass sie Teil des Override-Mechanismus selbst sein könnte, möglicherweise um sicherzustellen, dass der `AdminProductsController.php`-Override korrekt geladen wird oder um den allgemeinen Admin-Kontext zu handhaben. In den meisten Fällen liegt die eigentliche Logik in `AdminProductsController.php`.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen. Es interagiert direkt mit bestehenden PrestaShop `Product`- und `Configuration`-Objekten.

### 4.4 JavaScript-Assets (`views/js/`)

-   `myproductgridpro/views/js/product_grid_admin.js`
    *   **Geltungsbereich**: Back-Office (speziell die Seite `Katalog > Produkte`).
    *   **Verantwortlichkeit**:
        *   Handhabt die dynamische Manipulation der Produktlistentabelle im PrestaShop-Back-Office.
        *   Implementiert Drag-and-Drop-Funktionalität zum Neuordnen von Spalten, sodass Administratoren das Layout anpassen können.
        *   Verwaltet die Sichtbarkeit von Spalten (Anzeigen/Ausblenden basierend auf Benutzerpräferenzen).
        *   Speichert und ruft wahrscheinlich Benutzerpräferenzen für Spaltenreihenfolge und Sichtbarkeit mithilfe von AJAX-Aufrufen oder lokalem Speicher/Cookies ab, die dann vom überschriebenen `AdminProductsController` zum Rendern des Rasters verwendet werden.
        *   Kann Event-Listener für UI-Elemente enthalten, die die Spaltenauswahl steuern (z. B. ein Zahnradsymbol oder ein Dropdown-Menü zum Umschalten von Spalten).

### 4.5 CSS-Stylesheets (`views/css/`)

-   `myproductgridpro/views/css/product_grid_admin.css`
    *   **Geltungsbereich**: Back-Office (speziell die Seite `Katalog > Produkte`).
    *   **Verantwortlichkeit**:
        *   Bietet Styling für das erweiterte Produktgitter und stellt sicher, dass neue Spalten und UI-Elemente (wie Ziehgriffe oder Spaltenumschalter) korrekt angezeigt werden und sich nahtlos in das PrestaShop-Back-Office-Theme integrieren.
        *   Kann Stile für Drag-and-Drop-Indikatoren, ausgeblendete Spaltenzustände oder spezifische Breiten für neue Spalten enthalten.
        *   Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können: Suchen Sie nach Klassen, die mit `product-grid-pro` oder ähnlichem beginnen, oder nach spezifischen Tabellenkopf-/Zellenklassen, die für benutzerdefiniertes Styling angesprochen werden könnten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul scheint basierend auf dem bereitgestellten Inventar keine benutzerdefinierten `.tpl`-Dateien zu verwenden. Dies deutet darauf hin, dass die Änderungen am Produktgitter hauptsächlich durch PHP (im überschriebenen Controller) und JavaScript erreicht werden, das die vorhandene HTML-Struktur, die von PrestaShops Kern-Templates für den `AdminProductsController` generiert wird, dynamisch manipuliert. Das Modul injiziert wahrscheinlich seine JS und CSS über Hooks wie `displayBackOfficeHeader`.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul speichert seine Konfigurationseinstellungen (z. B. bevorzugte Spaltenreihenfolge, Sichtbarkeit) hauptsächlich in der Tabelle `ps_configuration`. Konfigurationsschlüssel würden typischerweise mit `MYPRODUCTGRIDPRO_` oder ähnlichem präfixiert.
    *   Es erstellt keine neuen benutzerdefinierten Datenbanktabellen.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich des Back-Office ausgeführt. | Wird verwendet, um die `product_grid_admin.js`- und `product_grid_admin.css`-Assets des Moduls einzubinden und sicherzustellen, dass sie auf der `AdminProductsController`-Seite geladen werden. |
| `actionAdminProductsControllerSave` (oder ähnliche `actionAdminController`-Hooks) | Wird ausgeführt, wenn ein Admin-Controller Daten speichert. | Obwohl nicht explizit aufgeführt, könnte das Modul solche Hooks verwenden, um die benutzerdefinierten Spaltenpräferenzen (Reihenfolge, Sichtbarkeit) in `ps_configuration` zu speichern, wenn ein Admin-Benutzer sie ändert. |
| `actionAdminProductsListingFieldsModifier` (PrestaShop 1.7+) | Wird ausgeführt, bevor die Produktlistenfelder gerendert werden. | Dieser Hook ist entscheidend für Module, die das `$this->fields_list` des `AdminProductsController` modifizieren. Er ermöglicht es dem Modul, Spaltendefinitionen dynamisch hinzuzufügen, zu entfernen oder zu ändern. |
| `actionAdminProductsListingResultsModifier` (PrestaShop 1.7+) | Wird ausgeführt, nachdem die Produktdaten abgerufen wurden, aber vor dem Rendern. | Ermöglicht es dem Modul, die tatsächlichen Datenzeilen für die neuen Spalten zu ändern (z. B. das Berechnen von „Verkaufte Einheiten“ oder „Zuletzt verkauft“, wenn nicht direkt aus der Hauptproduktabfrage verfügbar). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Product Grid Pro - Spalten & Layout von Listenprodukten“ besuchen Sie bitte Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
