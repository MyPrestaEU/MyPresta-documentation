---
title: "Sliding Sidebar Cart – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Sliding sidebar cart“ von MyPresta.eu."
sidebar:
  label: "Sliding sidebar cart – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Sliding sidebar cart auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/sliding-sidebar-cart.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/sliding-sidebar-cart/)
>
> ---


# Sliding sidebar cart

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls klicken Sie auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen. Auf dieser Seite können Sie genau steuern, welche Informationen in der gleitenden Seitenleiste des Warenkorbs angezeigt werden.

- **Produktbild anzeigen**

  - **Was diese Einstellung bewirkt:** Steuert, ob das Miniaturbild jedes Produkts im Warenkorb in der Seitenleiste angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Ein kleines Bild jedes Produkts wird neben seinem Namen in der Seitenleiste angezeigt, was es Kunden erleichtert, Artikel visuell zu identifizieren.
    - *Wenn deaktiviert („Aus“):* Nur der Produktname und andere Textdetails werden angezeigt, was Platz spart, den Warenkorb aber möglicherweise weniger visuell ansprechend macht.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Dies hilft Kunden, schnell zu bestätigen, dass sie den richtigen Artikel hinzugefügt haben, besonders nützlich für Geschäfte mit vielen ähnlich klingenden Produkten oder Variationen.
- **Produktname anzeigen**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der Name jedes Produkts im gleitenden Warenkorb sichtbar ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Der vollständige Name jedes Produkts wird angezeigt.
    - *Wenn deaktiviert („Aus“):* Produktnamen werden ausgeblendet. Dies wird im Allgemeinen nicht empfohlen, da es den Warenkorb schwer verständlich macht.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Dies ist eine grundlegende Information. Halten Sie sie immer „An“, damit Kunden genau wissen, was sich in ihrem Warenkorb befindet.
- **Produktattributwerte anzeigen**

  - **Was diese Einstellung bewirkt:** Wenn Ihre Produkte Attribute (wie Größe, Farbe, Material) haben, steuert diese Einstellung, ob die ausgewählten Attribute für jedes Produkt im Warenkorb angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Für ein Produkt wie „T-Shirt (Größe: M, Farbe: Blau)“ wird „Größe: M, Farbe: Blau“ angezeigt.
    - *Wenn deaktiviert („Aus“):* Nur „T-Shirt“ wird angezeigt, was Kunden möglicherweise über die genaue Variante, die sie hinzugefügt haben, verwirrt.
  - **Empfohlener Wert:** „An“ (insbesondere für Geschäfte, die konfigurierbare Produkte verkaufen)
  - **Händlerszenario / Beispiel:** Entscheidend für Geschäfte, die Kleidung, Elektronik mit unterschiedlichen Spezifikationen oder Produkte mit mehreren Optionen verkaufen. Es hilft Kunden zu überprüfen, ob sie die richtige Variante ausgewählt haben.
- **Produktpreis anzeigen**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Einzelpreis jedes Produkts im Warenkorb angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Der Stückpreis für jeden Artikel wird sichtbar sein.
    - *Wenn deaktiviert („Aus“):* Einzelne Produktpreise werden ausgeblendet, obwohl der Gesamtwert des Warenkorbs weiterhin angezeigt wird.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Transparenz ist der Schlüssel. Das Anzeigen von Einzelpreisen hilft Kunden, die Kostenaufschlüsselung zu verstehen und ihre Auswahl zu bestätigen.
- **Mengen-Eingabefeld anzeigen**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, die Menge eines Artikels direkt im Seitenleisten-Warenkorb über ein Eingabefeld zu ändern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Ein numerisches Eingabefeld (z. B. „1“, „2“, „3“) erscheint neben jedem Produkt, sodass Kunden eine neue Menge eingeben oder Inkrement-/Dekrement-Buttons verwenden können.
    - *Wenn deaktiviert („Aus“):* Kunden können die Mengen in der Seitenleiste nicht ändern; sie müssten dazu auf die vollständige Warenkorbseite gehen.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Dies verbessert die Benutzerfreundlichkeit erheblich. Ein Kunde, der versehentlich 2 statt 1 Artikel hinzugefügt hat, kann dies sofort korrigieren, ohne die aktuelle Seite zu verlassen, was Frustration und potenzielle Warenkorbabbrüche reduziert.
- **Entfernen-Button anzeigen**

  - **Was diese Einstellung bewirkt:** Fügt neben jedem Produkt einen Button (normalerweise ein „X“ oder ein Papierkorbsymbol) hinzu, mit dem Kunden es aus dem Warenkorb entfernen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Kunden können unerwünschte Artikel direkt aus der Seitenleiste aus ihrem Warenkorb löschen.
    - *Wenn deaktiviert („Aus“):* Kunden können Artikel nicht aus der Seitenleiste entfernen; sie müssten dazu auf die vollständige Warenkorbseite gehen.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Wesentlich für ein flexibles Einkaufserlebnis. Wenn ein Kunde seine Meinung zu einem Artikel ändert, kann er ihn sofort entfernen, wodurch verhindert wird, dass er den gesamten Warenkorb aufgrund eines unerwünschten Produkts abbricht.
- **Versandkosten anzeigen**

  - **Was diese Einstellung bewirkt:** Zeigt eine Schätzung oder die tatsächlichen Versandkosten in der Zusammenfassung des Seitenleisten-Warenkorbs an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Die geschätzten oder berechneten Versandkosten werden in der Warenkorbzusammenfassung angezeigt.
    - *Wenn deaktiviert („Aus“):* Versandkosten werden in der Seitenleiste nicht angezeigt, nur auf der vollständigen Warenkorb- oder Checkout-Seite.
  - **Empfohlener Wert:** „An“ (wenn Ihre Versandkostenberechnung frühzeitig genau ist)
  - **Händlerszenario / Beispiel:** Transparenz über die Versandkosten im Voraus kann einen „Preisschock“ an der Kasse verhindern, der eine Hauptursache für Warenkorbabbrüche ist. Wenn Ihr Versand komplex ist oder stark von der Adresse des Kunden abhängt, sollten Sie ihn möglicherweise „Aus“ lassen, um irreführende Schätzungen zu vermeiden.
- **Zwischensumme anzeigen (Gesamtwert der Produkte)**

  - **Was diese Einstellung bewirkt:** Zeigt den Gesamtwert aller Produkte im Warenkorb an, *bevor* Versandkosten, Steuern oder Rabatte angewendet werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Die Summe aller Produktpreise wird angezeigt.
    - *Wenn deaktiviert („Aus“):* Diese spezifische Zwischensummenzeile wird ausgeblendet.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Bietet dem Kunden eine klare Aufschlüsselung und hilft ihm, die Kosten der Artikel selbst getrennt von anderen Gebühren zu verstehen.
- **Zwischensumme Steuern anzeigen**

  - **Was diese Einstellung bewirkt:** Zeigt den Gesamtbetrag der auf die Produkte im Warenkorb angewendeten Steuern an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Der Gesamtsteuerbetrag wird in der Warenkorbzusammenfassung angezeigt.
    - *Wenn deaktiviert („Aus“):* Steuerdetails werden in der Seitenleiste nicht angezeigt.
  - **Empfohlener Wert:** „An“ (insbesondere in Regionen, in denen Steuertransparenz gesetzlich vorgeschrieben oder von Kunden erwartet wird)
  - **Händlerszenario / Beispiel:** Wichtig für die Transparenz, insbesondere in Ländern, in denen die Mehrwertsteuer oder Umsatzsteuer einen erheblichen Bestandteil des Endpreises ausmacht. Es hilft Kunden, die vollständige Kostenaufschlüsselung zu verstehen, bevor sie zur Kasse gehen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Produktbild anzeigen | An | Zeigt Produktminiaturen zur visuellen Identifikation. |
| Modulkonfiguration | Produktname anzeigen | An | Zeigt den Namen jedes Produkts im Warenkorb. |
| Modulkonfiguration | Produktattributwerte anzeigen | An | Zeigt ausgewählte Attribute (Größe, Farbe) für konfigurierbare Produkte. |
| Modulkonfiguration | Produktpreis anzeigen | An | Zeigt den Einzelpreis jedes Produkts. |
| Modulkonfiguration | Mengen-Eingabefeld anzeigen | An | Ermöglicht Kunden, Produktmengen direkt in der Seitenleiste zu ändern. |
| Modulkonfiguration | Entfernen-Button anzeigen | An | Ermöglicht Kunden, Produkte direkt in der Seitenleiste aus dem Warenkorb zu entfernen. |
| Modulkonfiguration | Versandkosten anzeigen | An | Zeigt geschätzte/tatsächliche Versandkosten in der Zusammenfassung. |
| Modulkonfiguration | Zwischensumme anzeigen (Gesamtwert der Produkte) | An | Zeigt den Gesamtwert der Produkte vor Versand/Steuern. |
| Modulkonfiguration | Zwischensumme Steuern anzeigen | An | Zeigt den Gesamtsteuerbetrag, der auf Produkte angewendet wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Seitenleiste fährt nicht aus, wenn ich ein Produkt in den Warenkorb lege.**
A1:

- **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul „Sliding sidebar cart“ unter **Module > Modul-Manager** installiert und aktiviert ist.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Modulfunktionen geladen werden.
- **Theme-Konflikte:** Ihr Theme hat möglicherweise eine eigene „In den Warenkorb legen“-Bestätigung oder JavaScript, die mit diesem Modul in Konflikt steht. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic), um zu sehen, ob die Seitenleiste funktioniert. Wenn ja, liegt das Problem am JavaScript oder CSS Ihres benutzerdefinierten Themes. Möglicherweise müssen Sie einen Entwickler hinzuziehen.
- **JavaScript-Fehler:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (normalerweise F12) und suchen Sie nach JavaScript-Fehlern, wenn Sie ein Produkt hinzufügen. Diese Fehler können verhindern, dass die Seitenleiste angezeigt wird.

**F2: Die Seitenleiste wird angezeigt, aber das Styling sieht falsch aus (falsche Farben, Schriftarten oder Layout).**
A2:

- **Theme-CSS-Konflikte:** Dies ist fast immer ein CSS-Konflikt mit Ihrem aktiven PrestaShop-Theme. Die Stylesheets Ihres Themes könnten die Stile des Moduls überschreiben.
- **Lösung:** Sie benötigen wahrscheinlich einen Webmaster oder Entwickler, um das CSS mit den Browser-Entwicklertools zu überprüfen. Sie können die widersprüchlichen Stile identifizieren und benutzerdefiniertes CSS zu Ihrem Theme (oder der benutzerdefinierten CSS-Datei des Moduls, falls verfügbar) hinzufügen, um sicherzustellen, dass die Seitenleiste korrekt angezeigt wird.

**F3: Die Mengen oder Preise werden nicht korrekt aktualisiert, wenn ich sie in der Seitenleiste ändere.**
A3:

- **Cache leeren:** Versuchen Sie erneut, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung**).
- **AJAX-Probleme:** Das Modul verwendet AJAX, um den Warenkorb zu aktualisieren. Wenn serverseitige Fehler oder JavaScript-Konflikte die AJAX-Aufrufe daran hindern, abgeschlossen zu werden, werden Updates nicht registriert. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf Netzwerkfehler oder JavaScript-Fehler, wenn Sie versuchen, Mengen zu ändern.
- **Modulkonfiguration:** Überprüfen Sie nochmals, ob „Mengen-Eingabefeld anzeigen“ in der Modulkonfiguration aktiviert ist.

**F4: Wie übersetze ich den Text in der Seitenleiste in andere Sprachen?**
A4:

- **PrestaShop-Übersetzungssystem:** Gehen Sie in Ihrem Back Office zu **International > Übersetzungen**.
- **Übersetzungstyp:** Wählen Sie „Übersetzungen installierter Module“.
- **Modul auswählen:** Wählen Sie „Sliding sidebar cart“ aus dem Modul-Dropdown.
- **Sprache auswählen:** Wählen Sie die Sprache aus, in die Sie übersetzen möchten.
- **Übersetzen:** Sie sehen eine Liste der übersetzbaren Zeichenfolgen aus dem Modul. Geben Sie Ihre Übersetzungen ein und speichern Sie.

**F5: Kann ich ändern, von welcher Seite die Seitenleiste ausfährt (links vs. rechts)?**
A5:

- Das Standardverhalten des Moduls ist typischerweise, von rechts auszufahren. Eine Änderung würde benutzerdefinierte CSS-Modifikationen erfordern, da dies durch die Dateien `sidcart.css` und `sidcart-right.css` gesteuert wird. Ein Entwickler könnte die CSS-Eigenschaften (z. B. `right: 0` zu `left: 0`) und möglicherweise die Animationslogik anpassen, um dies zu erreichen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Sliding sidebar cart“ (`sidcart`) folgt einer Standard-PrestaShop-Modularchitektur, die sich hauptsächlich auf Front-Office-Verbesserungen konzentriert. Es nutzt das PrestaShop-Hook-System, um seine Funktionalität und Templates in den Shop einzubinden. Die Kernlogik für die Warenkorbinteraktion (Hinzufügen, Aktualisieren, Entfernen von Produkten) wird über einen AJAX-Front-Controller abgewickelt, um ein dynamisches und störungsfreies Benutzererlebnis zu gewährleisten. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajax.php`
    - **Klassenname & Elternklasse**: `SidcartAjaxModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist für die Bearbeitung aller AJAX-Anfragen im Zusammenhang mit dem gleitenden Warenkorb zuständig. Wenn ein Benutzer ein Produkt hinzufügt, eine Menge aktualisiert oder einen Artikel aus der Seitenleiste entfernt, sendet das JavaScript eine Anfrage an diesen Controller. Er verarbeitet die Warenkorbänderung mithilfe der PrestaShop-Kernklasse `Cart` und gibt dann eine aktualisierte Warenkorbzusammenfassung (normalerweise HTML-Fragmente oder JSON-Daten) an das Front-End-JavaScript zurück, das dann den Inhalt der Seitenleiste aktualisiert. Dies gewährleistet Echtzeit-Updates ohne vollständige Seitenneuladungen.
- **Back-Office-Admin-Controller**: Keine. Alle Konfigurationen werden innerhalb der `getContent()`-Methode des Hauptmoduls behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Klassen im Verzeichnis `classes/`. Seine Kernlogik befindet sich in der Datei `sidcart.php` und dem `ajax.php`-Front-Controller, die direkt mit den nativen PrestaShop-Klassen `Cart` und `Product` interagieren.

### 4.4 JavaScript-Assets (`views/js/`)

- `sidcart/views/js/sidcart.js`
  - **Umfang**: Front-Office.
  - **Details**: Dies ist die primäre JavaScript-Datei für das Modul.
    - Sie lauscht auf „In den Warenkorb legen“-Ereignisse (z. B. Klicks auf Schaltflächen mit spezifischen Klassen wie `.add-to-cart`).
    - Sie fängt das Standardverhalten „In den Warenkorb legen“ ab und löst stattdessen die gleitende Seitenleiste aus.
    - Sie verwaltet die AJAX-Kommunikation mit `controllers/front/ajax.php`, um den Warenkorbinhalt zu aktualisieren.
    - Sie verwaltet die Anzeige und Animation der Seitenleiste (Ein-/Ausblenden).
    - Sie bindet Event-Listener für Mengenänderungen und Entfernen-Buttons innerhalb der Seitenleiste selbst, sendet weitere AJAX-Anfragen zur Aktualisierung des Warenkorbs.
    - Sie verwendet wahrscheinlich `jQuery` für DOM-Manipulation und AJAX-Aufrufe, was in PrestaShop 1.7.x und 8.x üblich ist.
    - Sie kann auch auf `prestashop.on('updateCart', ...)` oder ähnliche Ereignisse lauschen, um sicherzustellen, dass die Seitenleiste Änderungen widerspiegelt, die von anderen Modulen oder der PrestaShop-Kernfunktionalität vorgenommen wurden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `sidcart/views/css/sidcart-right.css`

  - **Umfang**: Front-Office-Kundenstyling.
  - **Details**: Dieses Stylesheet definiert das visuelle Erscheinungsbild und die Positionierung der gleitenden Seitenleiste, wenn sie von der rechten Seite des Bildschirms erscheint.
    - Es enthält Regeln für die Breite, den Hintergrund, den Z-Index und die anfängliche `right`-Position der Seitenleiste (z. B. `right: -300px;` zum Ausblenden).
    - Es definiert die Übergangseigenschaften für sanfte Gleitanimationen (z. B. `transition: right 0.3s ease-in-out;`).
    - Es gestaltet das Overlay, das hinter der Seitenleiste erscheint, wenn diese geöffnet ist.
    - Es enthält spezifische Regeln für die mobile Responsivität, die die Breite oder Position der Seitenleiste auf kleineren Bildschirmen anpassen.
    - **Wichtige CSS-Klassenselektoren**: `.sidcart-wrapper`, `.sidcart-content`, `.sidcart-overlay`, `.sidcart-open`.
- `sidcart/views/css/sidcart.css`

  - **Umfang**: Front-Office-Kundenstyling.
  - **Details**: Dieses Stylesheet enthält allgemeine Styling-Regeln für die Elemente *innerhalb* des gleitenden Warenkorbs, unabhängig davon, ob er von links oder rechts gleitet.
    - Es gestaltet die Produktlistenelemente (`.sidcart-product-line`).
    - Es gestaltet Produktbilder, Namen, Preise, Attribute, Mengen-Eingabefelder und Entfernen-Buttons.
    - Es gestaltet die Warenkorbzusammenfassungsbereiche (Zwischensumme, Versand, Gesamt).
    - Es gestaltet die Schaltflächen „Weiter einkaufen“ und „Zur Kasse gehen“.
    - **Wichtige CSS-Klassenselektoren**: `.sidcart-product-image`, `.sidcart-product-name`, `.sidcart-product-price`, `.sidcart-qty-input`, `.sidcart-remove-button`, `.sidcart-summary`, `.sidcart-buttons`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `sidcart/views/templates/hook/product-line.tpl`
    - **Hook**: Dieses Template ist nicht direkt gehookt, sondern wird dynamisch vom AJAX-Controller (`ajax.php`) gerendert, um einen einzelnen Produkteintrag innerhalb des gleitenden Warenkorbs darzustellen.
    - **Ausgabe**: Rendert den HTML-Code für ein Produkt, einschließlich Bild, Name, Attribute, Preis, Mengen-Eingabefeld und Entfernen-Button, basierend auf den Konfigurationseinstellungen des Moduls.
  - `sidcart/views/templates/hook/sidcart.tpl`
    - **Hook**: Dieses Template wird wahrscheinlich vom `displayHeader`- oder `displayNav2`-Hook (oder ähnlichem) gerendert, um die Hauptstruktur der gleitenden Seitenleiste in die Seite einzufügen. Es könnte anfänglich ausgeblendet und dann durch JavaScript sichtbar gemacht werden.
    - **Ausgabe**: Enthält die Haupt-HTML-Struktur für die gesamte gleitende Seitenleiste, einschließlich des Containers, des Produktlistenbereichs, der Warenkorbzusammenfassung und der Aktionsschaltflächen. Es dient als Wrapper für den dynamisch geladenen `product-line.tpl`-Inhalt.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `sidcart/views/templates/modal.tpl`
    - **Hook**: Dieses Template ist wahrscheinlich ein Fallback oder eine alternative Struktur für eine modale Anzeige, oder es könnte für einen bestimmten Teil der Seitenleiste verwendet werden (z. B. eine Bestätigungsnachricht). Angesichts der Modulbeschreibung ist es weniger wahrscheinlich, dass es sich um das primäre gleitende Panel selbst handelt, könnte aber eine Komponente darin oder ein Legacy-Template sein.
    - **Ausgabe**: Rendert eine generische modale oder Popup-Struktur. Entwickler sollten die tatsächliche Verwendung innerhalb der `sidcart.js`- oder `ajax.php`-Logik überprüfen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der PrestaShop-Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `sc_ajaxInfo`, `sc_continueshopping`, `sc_pimage`, `sc_total`, `sc_subtotals_tax`, `sc_subtotals`, `sc_shipping`, `sc_remove`, `sc_qty_change`, `sc_price`, `sc_pname`, `sc_attributes` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um die CSS- und JavaScript-Dateien des Moduls (`sidcart.css`, `sidcart-right.css`, `sidcart.js`) einzubinden und möglicherweise die anfängliche, ausgeblendete HTML-Struktur der Seitenleiste zu injizieren. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller initialisiert wird und seine Medien-Assets gesetzt werden. | Wird verwendet, um alle notwendigen CSS/JS für die Konfigurationsseite des Moduls im Back Office einzubinden. |
| `displayNav2` | In der Navigationsleiste, typischerweise in der Nähe des Warenkorbsymbols. | Wird verwendet, um eine kleine Warenkorbzusammenfassung (z. B. Anzahl der Artikel, Gesamtpreis) einzufügen oder den Event-Listener an das vorhandene Warenkorbsymbol anzuhängen, das die Seitenleiste auslöst. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Sliding sidebar cart“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
