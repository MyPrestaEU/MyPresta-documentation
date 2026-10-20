---
title: "Stylight - Sales-Tracking-Pixel - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Stylight - Sales-Tracking-Pixel“ von MyPresta.eu."
sidebar:
  label: "Stylight - Sales-Tracking-Pixel"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Stylight - sales tracking pixel auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/stylight-sales-tracking-pixel.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/stylight-sales-tracking-pixel/)
>
> ---


# Stylight - Sales-Tracking-Pixel

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Das Modul „Stylight - Sales-Tracking-Pixel“ ist extrem einfach zu konfigurieren und erfordert keine spezifischen Einstellungen vom Händler. Seine Funktionalität ist primär eigenständig und erkennt und übermittelt die notwendigen Bestelldaten automatisch.

Wenn Sie zur Konfigurationsseite des Moduls navigieren (Back Office > Module > Modul-Manager > Stylight - Sales-Tracking-Pixel > Konfigurieren), finden Sie normalerweise eine Bestätigungsmeldung, die anzeigt, dass das Modul installiert und aktiv ist.

-   **Was dieser Bildschirm tut:** Diese Seite dient als Bestätigung, dass das Modul korrekt installiert und bereit ist, Verkäufe zu verfolgen. Es gibt keine Eingabefelder oder Schalter, die Sie anpassen müssen. Das Modul klinkt sich automatisch in den Bestellbestätigungsprozess ein und sammelt alle erforderlichen Daten (Gesamtbetrag, Währung, Artikelanzahl, SKU-Nummern, Bestell-ID) direkt aus den Bestelldetails von PrestaShop.
-   **Auswirkung der Änderung dieser Einstellung:** Da es keine konfigurierbaren Einstellungen gibt, gibt es nichts zu ändern. Das Modul funktioniert nach der Installation sofort.
-   **Empfohlener Wert:** Keine Aktion erforderlich.
-   **Händlerszenario / Beispiel:** Nach der Installation des Moduls besuchen Sie diese Seite einfach, um dessen Vorhandensein zu bestätigen. Sie müssen keine Stylight-spezifischen IDs oder Schlüssel eingeben, da das Pixel selbst generisch ist und so konzipiert wurde, dass es mit dem Stylight-System funktioniert, indem es Standard-E-Commerce-Daten sendet.

### 2.2 Konfigurations-Kurzübersichtstabelle
| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | *(Keine benutzerkonfigurierbaren Einstellungen)* | N/A | Das Modul verfolgt automatisch Verkaufsdaten (Gesamtbetrag, Währung, Artikelanzahl, SKUs, Bestell-ID) auf der Bestellbestätigungsseite für Stylight.com. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber keine Verkäufe in meinem Stylight-Konto. Was soll ich tun?**
A: Stellen Sie zunächst sicher, dass das Modul in Ihrem PrestaShop Back Office aktiviert ist. Versuchen Sie dann, Ihren PrestaShop-Cache zu leeren (Erweiterte Einstellungen > Leistung > Cache leeren). Wenn das Problem weiterhin besteht, führen Sie selbst eine Testbestellung durch. Wenn immer noch keine Daten vorhanden sind, wenden Sie sich an den MyPresta.eu-Support mit Details zu Ihrer PrestaShop-Version und allen anderen kürzlich installierten Modulen.

**F: Verlangsamt dieses Modul meine Bestellbestätigungsseite?**
A: Das Tracking-Pixel ist sehr leichtgewichtig und lädt asynchron, was bedeutet, dass es die Ladezeiten der Seite oder das Kundenerlebnis im Allgemeinen nicht wesentlich beeinträchtigt. Seine Auswirkungen auf die Leistung sind minimal.

**F: Muss ich eine Stylight-ID oder einen API-Schlüssel in das Modul eingeben?**
A: Nein, dieses Modul ist so konzipiert, dass es sofort funktioniert. Es implementiert ein Standard-Stylight-Tracking-Pixel, das die notwendigen Bestelldaten automatisch sendet, ohne dass spezifische, vom Händler eingegebene IDs in der Modulkonfiguration selbst erforderlich sind. Ihr Stylight-Konto ist mit Ihrer Domain verknüpft, und deren System identifiziert Ihren Shop anhand des Ursprungs des Pixels.

**F: Ist dieses Modul mit benutzerdefinierten Themes kompatibel?**
A: Ja, das Modul klinkt sich in einen Standard-PrestaShop-Hook (`displayOrderConfirmation`) ein, der typischerweise in allen gut codierten Themes vorhanden ist. Es ist nicht auf spezifische Theme-Elemente angewiesen, daher sollte es nahtlos mit den meisten benutzerdefinierten Themes funktionieren.

**F: Ich habe mehrere Sprachen/Währungen. Verfolgt das Modul diese korrekt?**
A: Ja, das Modul ist so konzipiert, dass es den Gesamtbetrag und die Währung der Bestellung, wie sie von PrestaShop verarbeitet werden, automatisch erfasst, um eine genaue Verfolgung für Shops mit mehreren Währungen und Sprachen zu gewährleisten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul „Stylight - Sales-Tracking-Pixel“ ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf das Hooking von Front-Office-Ereignissen konzentriert. Es nutzt den `displayOrderConfirmation`-Hook, um ein JavaScript-basiertes Tracking-Pixel auf der finalen Bestellbestätigungsseite einzufügen. Die Logik des Moduls ist in seiner Haupt-PHP-Datei, `index.php`, enthalten, die die Installation, Deinstallation und die Hook-Registrierung handhabt. Die Datenerfassung ist dynamisch und ruft Bestelldetails direkt aus den `Order`- und `Product`-Objekten ab, die im Kontext der Bestellbestätigungsseite verfügbar sind.

### 4.2 Controller (`controllers/`)
-   **Front-Office-Controller**: Keine. Die Front-Office-Funktionalität des Moduls wird vollständig durch das Hooking in `displayOrderConfirmation` und das Rendern einer Smarty-Vorlage abgewickelt.
-   **Back-Office-Admin-Controller**: Keine. Das Modul hat keine dedizierte Admin-Oberfläche über die Standard-Modulkonfigurationsseite (`getContent()`) hinaus.

### 4.3 Kernklassen & Modelle (`classes/`)
-   Keine. Das Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Logik befindet sich in der Hauptdatei `stylightpixel/index.php`.

### 4.4 JavaScript-Assets (`views/js/`)
-   Keine. Der Tracking-Pixel-Code ist direkt in die Smarty-Vorlage (`displayOrderConfirmation.tpl`) eingebettet, um sicherzustellen, dass er sofort beim Laden der Seite ausgelöst wird.

### 4.5 CSS-Stylesheets (`views/css/`)
-   Keine. Das Modul ist rein funktional und hat keine visuellen Komponenten oder Styling-Anforderungen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)
-   **Hook-Vorlagen (`views/templates/hook/`)**:
    *   `stylightpixel/views/templates/hook/displayOrderConfirmation.tpl`
        *   **Hook**: `displayOrderConfirmation`
        *   **Zweck**: Diese Vorlage wird auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf gerendert. Sie enthält den JavaScript-Code für das Stylight-Tracking-Pixel.
        *   **Verfügbare Daten**: Die Vorlage empfängt `$order` (ein `Order`-Objekt) und `$products` (ein Array von `Product`-Objekten, die mit der Bestellung verknüpft sind) von der Methode `hookDisplayOrderConfirmation`.
        *   **Ausgabe**: Es gibt einen `<script>`-Block aus, der die Stylight-Tracking-Pixel-URL mit dynamischen Parametern wie `order_id`, `total_amount`, `currency`, `item_count` und `sku` für jedes Produkt konstruiert.

### 4.7 Datenbankschema & Hooks-Map
-   **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es greift auf Standard-PrestaShop-Tabellen (`ps_orders`, `ps_order_detail`, `ps_product` usw.) zurück, um Bestellinformationen abzurufen.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayOrderConfirmation` | Wird auf der finalen Bestellbestätigungsseite nach einem erfolgreichen Kauf ausgeführt. | Fügt das Stylight-Tracking-Pixel-JavaScript in die Seite ein, um Konversionsdaten (Bestell-ID, Gesamtbetrag, Währung, Produkt-SKUs, Artikelanzahl) an Stylight zu senden. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Stylight - Sales-Tracking-Pixel“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei Modul-bezogenen Anfragen zur Verfügung und stellt sicher, dass Ihr Tracking-Pixel korrekt funktioniert.
