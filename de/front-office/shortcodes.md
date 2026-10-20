---
title: "Shortcodes – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Shortcodes von MyPresta.eu."
sidebar:
  label: "Shortcodes"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Shortcodes auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/shortcodes.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/shortcodes/)
>
> ---


# Shortcodes

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation des Moduls navigieren Sie zu **Module > Modul-Manager** und suchen Sie nach „Shortcodes“. Klicken Sie auf die Schaltfläche „Konfigurieren“, um auf die Einstellungen zuzugreifen.

Die Konfigurationsseite für das Shortcodes-Modul ist unkompliziert und konzentriert sich auf eine einzige, entscheidende Einstellung:

#### Alle Shortcodes deaktivieren
-   **Was diese Einstellung bewirkt:** Dies ist ein Hauptschalter, der steuert, ob das Modul Shortcodes auf Ihrer gesamten Website verarbeitet und ersetzt.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (auf „Ein“ gesetzt):* Das Modul scannt aktiv Ihre Inhalte und Theme-Dateien nach erkannten Shortcodes (z. B. `[products]`, `[categories]`, `[html]`) und ersetzt sie durch den entsprechenden dynamischen Inhalt. Dies ist der beabsichtigte Betriebsmodus für das Modul.
    -   *Wenn deaktiviert (auf „Aus“ gesetzt):* Das Modul stoppt die Verarbeitung aller Shortcodes. Alle Shortcodes, die Sie in Ihren Inhalten oder Theme-Dateien platziert haben, werden einfach als Klartext angezeigt (z. B. `[products]` wird für Ihre Kunden als `[products]` sichtbar sein) und nicht durch dynamische Inhalte ersetzt.
-   **Empfohlener Wert:** **Ein**
-   **Händlerszenario / Beispiel:**
    -   Sie würden dies auf „Ein“ setzen, um die Shortcode-Funktionalität zu aktivieren und Ihre dynamischen Inhalte anzuzeigen.
    -   Sie könnten dies vorübergehend auf „Aus“ setzen, wenn Sie ein Problem debuggen, Wartungsarbeiten durchführen oder wenn Sie alle durch Shortcodes generierten dynamischen Inhalte in Ihrem Shop deaktivieren möchten, ohne das Modul zu deinstallieren. Denken Sie daran, Ihre Änderungen nach dem Umschalten dieser Einstellung zu speichern.

:::tip
Nachdem Sie Einstellungen geändert haben, klicken Sie immer auf die Schaltfläche „Speichern“, um Ihre Änderungen zu übernehmen.
:::

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | Alle Shortcodes deaktivieren | Ein | Steuert, ob das Modul Shortcodes verarbeitet und durch dynamische Inhalte ersetzt. Auf „Ein“ setzen, um zu aktivieren, auf „Aus“, um zu deaktivieren. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Shortcodes werden als Klartext (z. B. `[products]`) anstatt als dynamischer Inhalt angezeigt. Was ist falsch?**
**A1:**
1.  **Modulstatus prüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Shortcodes“ installiert und aktiviert ist.
2.  **Modulkonfiguration prüfen:** Gehen Sie zur Konfigurationsseite des Moduls und stellen Sie sicher, dass „Alle Shortcodes deaktivieren“ auf **„Ein“** gesetzt ist.
3.  **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
4.  **Korrekte Shortcode-Syntax:** Überprüfen Sie sorgfältig, ob Sie den Shortcode genau wie erforderlich eingegeben haben, einschließlich Klammern `[]` und aller Parameter (z. B. `[products type="new"]`). Jeder Tippfehler verhindert die Verarbeitung.

**F2: Der dynamische Inhalt (z. B. Produktkarussell) ist nicht korrekt gestylt oder sieht in meinem Theme fehlerhaft aus.**
**A2:**
Dies deutet normalerweise auf einen CSS-Konflikt oder fehlende, themenspezifische Stile hin.
1.  **Theme-Kompatibilität:** Obwohl das Modul grundlegendes Styling bietet, können benutzerdefinierte Themes Stile für bestimmte Elemente überschreiben oder ihnen fehlen.
2.  **Entwicklerunterstützung:** Möglicherweise benötigen Sie einen Webentwickler, um die Seite mit den Browser-Entwicklertools (F12) zu überprüfen, um CSS-Konflikte zu identifizieren und benutzerdefinierte CSS-Regeln zu Ihrem Theme hinzuzufügen, um sicherzustellen, dass die Shortcode-Ausgabe visuell integriert wird. Die CSS-Datei des Moduls (`cmsproductspro.css`) kann als Ausgangspunkt dienen.

**F3: Kann ich Shortcodes in mehrsprachigen Shops verwenden?**
**A3:** Ja, Shortcodes selbst sind sprachunabhängig. Die Inhalte, die sie generieren (z. B. Produktnamen, Beschreibungen), werden automatisch in der vom Kunden ausgewählten Sprache angezeigt, vorausgesetzt, Ihre Produkte und Kategorien verfügen über Übersetzungen für diese Sprache. Achten Sie beim Platzieren von Shortcodes auf CMS-Seiten oder in Produktbeschreibungen darauf, dass Sie den Inhalt für die richtige Sprache im Back Office bearbeiten.

**F4: Ich habe einen Shortcode zu einer neuen CMS-Seite hinzugefügt, aber er wird im Front Office nicht angezeigt.**
**A4:**
1.  **Seitenstatus:** Stellen Sie sicher, dass Ihre CMS-Seite aktiviert und in Ihrem Navigationsmenü sichtbar ist oder von einer anderen Seite verlinkt wird.
2.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung**).
3.  **Shortcode-Platzierung:** Überprüfen Sie, ob der Shortcode in einem Inhaltsbereich platziert ist, der von Ihrem Theme für diese CMS-Seite tatsächlich gerendert wird. Einige Themes haben möglicherweise spezifische Inhaltsblöcke.

**F5: Welche Shortcodes sind verfügbar und welche Parameter kann ich verwenden?**
**A5:** Die Dokumentation des Moduls (dieses Handbuch) oder die Konfigurationsseite des Moduls (falls dort aufgeführt) sollten die verfügbaren Shortcodes detailliert beschreiben. Gängige Shortcodes sind:
-   `[products]` (für verschiedene Produktlisten wie neu, Bestseller, spezifische IDs)
-   `[categories]` (zum Anzeigen von Kategorielisten)
-   `[html]` (zum Einbetten von benutzerdefiniertem HTML)
-   `[imageManufacturer]` (zum Anzeigen von Herstellerbildern)
Sie müssen sich auf die spezifische Implementierung des Moduls für genaue Parameter (z. B. `limit`, `carousel`, `id`, `type`) beziehen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Shortcodes-Modul verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht
Das Shortcodes-Modul (`cmsproductspro`) fungiert hauptsächlich als Inhaltsfilter. Es greift in den PrestaShop-Ausgabe-Rendering-Prozess ein, um HTML-Inhalte abzufangen, bevor sie an den Browser gesendet werden. Anschließend werden reguläre Ausdrücke verwendet, um vordefinierte Shortcode-Muster zu finden und durch dynamisch generierte HTML-Inhalte zu ersetzen. Die Modulkonfiguration ist minimal und konzentriert sich auf einen globalen Aktivierungs-/Deaktivierungsschalter. Die Logik zur Inhaltserzeugung ist in der Hauptmodulklasse gekapselt und nutzt die Kernfunktionen von PrestaShop zur Datenabfrage (Produkte, Kategorien, Hersteller).

### 4.2 Controller (`controllers/`)
Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfigurations- und Inhaltsverarbeitungslogik wird innerhalb der Hauptmoduldatei (`cmsproductspro.php`) behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert **keine** benutzerdefinierten Klassen oder `ObjectModel`s in einem `classes/`-Verzeichnis. Die gesamte Kernlogik befindet sich in der Datei `cmsproductspro.php`.

### 4.4 JavaScript-Assets (`views/js/`)
Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Jedes dynamische Verhalten (wie Karussells) würde typischerweise auf vorhandene PrestaShop- oder vom Theme bereitgestellte JavaScript-Bibliotheken (z. B. Owl Carousel, Slick Carousel) zurückgreifen, wenn die Shortcode-Ausgabe solche Komponenten enthält.

### 4.5 CSS-Stylesheets (`views/css/`)
-   **`cmsproductspro/cmsproductspro.css`**
    *   **Geltungsbereich:** Front-Office-Kunden-Styling.
    *   **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet bietet grundlegendes Styling für die durch die Shortcodes generierte HTML-Ausgabe. Dazu gehören:
        *   Produktraster und Karussells (z. B. `.cmsproductspro-products-grid`, `.cmsproductspro-carousel`).
        *   Einzelne Produktelemente (z. B. `.cmsproductspro-product-item`, `.cmsproductspro-product-image`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`).
        *   Kategorielisten (z. B. `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`).
        *   Herstellerbilder (z. B. `.cmsproductspro-manufacturer-image`).
        *   Allgemeines Layout und Responsivität für diese Elemente.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler können Klassen wie `.cmsproductspro-products-grid`, `.cmsproductspro-product-item`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`, `.cmsproductspro-manufacturer-image` ansprechen, um das Erscheinungsbild der durch Shortcodes generierten Inhalte in ihrem Theme anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Das Modul verwendet mehrere Smarty-Templates, um die dynamischen Inhalte für verschiedene Shortcodes zu rendern. Diese Templates befinden sich in `views/templates/`.

-   **Hook-Templates (`views/templates/hook/`)**: Dieses Modul verwendet keinen expliziten `hook/`-Unterordner für seine Templates. Die Templates befinden sich direkt in `views/templates/` und werden basierend auf dem erkannten Shortcode gerendert.

-   **Admin-Templates (`views/templates/admin/`)**: Dieses Modul enthält keine spezifischen Admin-Templates über das Standardkonfigurationsformular hinaus, das von `getContent()` behandelt wird.

-   **Front-Office-Templates (`views/templates/front/`)**:
    *   **`cmsproductspro/categories.tpl`**:
        *   **Zweck:** Rendert eine Liste von Kategorien, typischerweise verwendet von einem `[categories]`-Shortcode.
        *   **Variablen:** Erwartet Variablen wie `$categories` (ein Array von Kategorieobjekten), `$display_subcategories`, `$image` usw.
        *   **Ausgabe:** Generiert HTML für ein Raster oder eine Liste von Kategorien, potenziell mit Bildern und Links.
    *   **`cmsproductspro/html.tpl`**:
        *   **Zweck:** Rendert rohen HTML-Inhalt, verwendet von einem `[html]`-Shortcode.
        *   **Variablen:** Erwartet eine `$content`-Variable, die den auszugebenden HTML-String enthält.
        *   **Ausgabe:** Gibt den bereitgestellten HTML-Inhalt direkt aus.
    *   **`cmsproductspro/imageManufacturer.tpl`**:
        *   **Zweck:** Zeigt das Bild eines Herstellers an, verwendet von einem `[imageManufacturer]`-Shortcode.
        *   **Variablen:** Erwartet `$manufacturer` (ein Objekt mit Herstellerdetails, einschließlich Bildpfad) und potenziell `$link` für die Herstellerseite.
        *   **Ausgabe:** Generiert ein `<img>`-Tag für das Herstellerlogo, oft in einem Link verpackt.
    *   **`cmsproductspro/productGallery.tpl`**:
        *   **Zweck:** Rendert eine Produktgalerie, potenziell mit spezifischem Layout oder Funktionen. Dies könnte ein generischeres Produktanzeige-Template sein.
        *   **Variablen:** Erwartet `$products` (ein Array von Produktobjekten) und andere Anzeigeoptionen.
        *   **Ausgabe:** HTML-Struktur für eine Produktgalerie.
    *   **`cmsproductspro/products-carousel.tpl`**:
        *   **Zweck:** Rendert eine Produktliste, die speziell für die Verwendung in einer Karussellkomponente entwickelt wurde.
        *   **Variablen:** Erwartet `$products` (Array von Produktobjekten) und potenziell karussellspezifische Optionen.
        *   **Ausgabe:** HTML-Struktur für eine Produktliste, oft mit Klassen, die für eine JavaScript-Karussellbibliothek geeignet sind.
    *   **`cmsproductspro/products.tpl`**:
        *   **Zweck:** Rendert eine allgemeine Liste oder ein Raster von Produkten, verwendet von einem `[products]`-Shortcode.
        *   **Variablen:** Erwartet `$products` (Array von Produktobjekten) und andere Anzeigeoptionen wie `$grid_class`, `$item_class`.
        *   **Ausgabe:** HTML-Struktur für ein Produktraster oder eine Liste.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**: Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen. Seine Konfiguration wird in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `CMSPRODUCTSPRO_HIDE` (für die Einstellung „Alle Shortcodes deaktivieren“) gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionOutputHTMLBefore` | Wird ausgeführt, kurz bevor die endgültige HTML-Ausgabe an den Browser gesendet wird. | Dies ist der primäre Hook, an dem das Modul den gesamten Seiteninhalt abfängt, nach Shortcodes scannt und Ersetzungen vornimmt. |
| `displayHeader` | Wird im `<head>`-Bereich des HTML ausgeführt. | Wird verwendet, um notwendige CSS-Dateien (`cmsproductspro.css`) für die durch Shortcodes generierten Inhalte einzubinden. |
| `actionAjaxDieProductControllerdisplayAjaxQuickviewBefore` | Wird vor der Methode `displayAjaxQuickview` in `ProductController` (für Quick-View-Modals) ausgeführt. | Dieser Hook stellt sicher, dass Shortcodes auch in den über AJAX für Produkt-Quick-Views geladenen Inhalten verarbeitet und ersetzt werden, um Konsistenz zu gewährleisten. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Shortcodes“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
