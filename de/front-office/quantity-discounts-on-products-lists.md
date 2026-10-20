---
title: "Mengenrabatte auf Produktlisten – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mengenrabatte auf Produktlisten“ von MyPresta.eu."
sidebar:
  label: "Mengenrabatte auf Produktlisten – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Quantity discounts on products lists auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/quantity-discounts-on-products-lists.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/quantity-discounts-on-products-lists/)
>
> ---


# Mengenrabatte auf Produktlisten

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der nach der Installation durch Klicken auf die Schaltfläche „Konfigurieren“ zugänglich ist.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält die Kerneinstellungen zum Aktivieren oder Deaktivieren der Modulfunktionalität und zur Steuerung des grundlegenden Verhaltens.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul beginnt, Mengenrabatte auf Produktlistenseiten gemäß Ihren anderen Einstellungen anzuzeigen.
  - *Wenn deaktiviert:* Das Modul stoppt die Anzeige von Mengenrabatten auf Produktlistenseiten.
- **Empfohlener Wert:** JA (es sei denn, Sie müssen es vorübergehend für Wartungsarbeiten deaktivieren).
- **Händlerszenario / Beispiel:** Wenn Sie eine Sonderaktion durchführen, die Mengenrabatte außer Kraft setzt, könnten Sie das Modul vorübergehend deaktivieren. Andernfalls lassen Sie es aktiviert, um seine Vorteile zu nutzen.

#### Anzeigeoptionen

- **Was diese Einstellung bewirkt:** Diese Optionen steuern das visuelle Erscheinungsbild und die Platzierung der Mengenrabattinformationen in Ihren Produktlisten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beispiel: „Auf Produktseite anzeigen“:*
    - *Wenn aktiviert:* Die Mengenrabatte werden auch auf der einzelnen Produktdetailseite angezeigt.
    - *Wenn deaktiviert:* Die Mengenrabatte erscheinen nur auf Produktlistenseiten (Kategorien, Suchergebnisse usw.), vorausgesetzt, sie sind dort standardmäßig durch die PrestaShop-Funktionalität bereits vorhanden.
  - *Beispiel: „Position der Rabattinformationen“:*
    - *Option A (z.B. „Unter dem Produktpreis“):* Die Rabattdetails erscheinen direkt unter dem Hauptpreis des Produkts.
    - *Option B (z.B. „Über dem Produktnamen“):* Die Rabattdetails erscheinen über dem Produktnamen.
- **Empfohlener Wert:** Experimentieren Sie mit den Positionen, um herauszufinden, was am besten zu Ihrem Theme passt. Oft ist „Unter dem Produktpreis“ ein guter Ausgangspunkt. „Auf Produktseite anzeigen“ kann aktiviert werden, wenn Ihr Theme Mengenrabatte dort nicht bereits prominent anzeigt.
- **Händlerszenario / Beispiel:** Wenn Ihre Produktkarten sehr kompakt sind, könnten Sie eine subtile Position wählen. Wenn Sie die Rabatte hervorheben möchten, könnte eine prominentere Position besser sein.

#### Styling & Anpassung

- **Was diese Einstellung bewirkt:** Diese Einstellungen ermöglichen es Ihnen, das Aussehen und Gefühl der Rabattanzeige an das Theme Ihres Shops anzupassen. Dies kann Optionen für Textfarbe, Hintergrundfarbe, Schriftgröße oder sogar benutzerdefiniertes CSS umfassen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beispiel: „Textfarbe“:*
    - *Wenn auf Rot gesetzt:* Der Rabatttext erscheint in Rot.
    - *Wenn auf Grün gesetzt:* Der Rabatttext erscheint in Grün.
- **Empfohlener Wert:** Wählen Sie Farben und Stile, die Ihr bestehendes Theme ergänzen.
- **Händlerszenario / Beispiel:** Wenn Ihre Marke eine bestimmte Farbpalette verwendet, möchten Sie, dass die Rabattinformationen nahtlos integriert werden, anstatt zu kollidieren.

#### Erweiterte Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt könnte Einstellungen für Caching, Leistungsoptimierung oder spezifische Integrationsoptionen enthalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beispiel: „Caching aktivieren“:*
    - *Wenn aktiviert:* Das Modul speichert generiertes Rabatt-HTML, um schneller zu laden und die Seitengeschwindigkeit zu verbessern.
    - *Wenn deaktiviert:* Das Modul generiert das Rabatt-HTML bei jedem Seitenaufruf, was die Seiten möglicherweise verlangsamt, aber sicherstellt, dass immer die absolut neuesten Daten angezeigt werden (nützlich während der Entwicklung).
- **Empfohlener Wert:** JA für Caching in Live-Shops.
- **Händlerszenario / Beispiel:** Wenn Sie Leistungsprobleme auf Seiten mit vielen Produktlisten bemerken, kann das Aktivieren des Caching helfen. Während der Theme-Entwicklung könnten Sie das Caching deaktivieren, um Änderungen sofort zu sehen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminPlqdSearchController (Back Office > Module > Mengenrabatte auf Produktlisten > Sucheinstellungen)

Dieser Controller verwaltet wahrscheinlich Einstellungen dazu, wie das Modul Produkte zur Anzeige von Rabatten identifiziert und verarbeitet, möglicherweise einschließlich eines Suchwerkzeugs für bestimmte Produkte oder Kategorien.

- **Bildschirmname & Menüposition:** Dieser Bildschirm ist möglicherweise über einen Unterreiter oder einen dedizierten Link innerhalb der Hauptmodulkonfigurationsseite zugänglich, möglicherweise mit der Bezeichnung „Sucheinstellungen“ oder „Produktauswahl“.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm würde typischerweise ein Raster oder ein Formular enthalten, um:
  - **Produkte suchen:** Ermöglicht Ihnen, bestimmte Produkte nach Name, ID oder Referenz zu finden.
  - **Produkte/Kategorien ausschließen:** Definieren Sie bestimmte Produkte oder ganze Kategorien, in denen Mengenrabatte NICHT angezeigt werden sollen, auch wenn sie konfiguriert sind.
  - **Anzeigeregeln verwalten:** Möglicherweise granularere Regeln festlegen, wann und wo Rabatte basierend auf Produktattributen oder anderen Kriterien erscheinen.
- **Auswirkung von Änderungen:**
  - *Ausschluss eines Produkts:* Die Mengenrabattinformationen für dieses spezifische Produkt werden nicht mehr auf Produktlistenseiten angezeigt.
  - *Ausschluss einer Kategorie:* Alle Produkte innerhalb der ausgewählten Kategorie erhalten ihre Mengenrabattinformationen auf Listenseiten ausgeblendet.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, wenn Sie bestimmte Produkte oder Kategorien haben, bei denen die Anzeige von Mengenrabatten auf Listen nicht erwünscht ist (z.B. sehr hochwertige Artikel, kundenspezifische Produkte oder Produkte mit komplexen Preisen, die Kunden verwirren könnten, wenn sie vereinfacht werden).

#### index.php (plqd/controllers/admin/index.php)

Diese Datei, obwohl als Admin-Controller aufgeführt, ist in PrestaShop-Modulen oft ein Platzhalter oder eine Weiterleitung. Im Kontext dieses Moduls ist es sehr wahrscheinlich, dass `plqd/index.php` (die Hauptmoduldatei) das primäre Konfigurationsformular über `getContent()` handhabt und `AdminPlqdSearchController.php` alle sekundären, komplexeren Admin-Oberflächen. Die `index.php` im Verzeichnis `controllers/admin` könnte einfach sicherstellen, dass der direkte Zugriff auf das Verzeichnis ordnungsgemäß behandelt wird, oder es könnte eine Legacy-Datei sein. Für Händler finden sich alle relevanten Einstellungen in der Hauptmodulkonfiguration oder im `AdminPlqdSearchController`.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität des Moduls. |
|  | Auf Produktseite anzeigen | JA/NEIN (Theme-abhängig) | Zeigt Rabatte auf einzelnen Produktseiten an. |
|  | Position der Rabattinfo | Unter dem Produktpreis | Steuert, wo der Rabatttext auf Produktkarten erscheint. |
|  | Textfarbe | (Theme-Standard) | Legt die Farbe des Rabatttextes fest. |
|  | Hintergrundfarbe | (Theme-Standard) | Legt die Hintergrundfarbe des Rabattblocks fest. |
|  | Caching aktivieren | JA | Verbessert die Leistung durch Speichern von generiertem HTML. |
| **AdminPlqdSearchController** | Produkt ausschließen (nach ID/Name) | N/A | Verhindert die Rabattanzeige für bestimmte Produkte. |
|  | Kategorie ausschließen | N/A | Verhindert die Rabattanzeige für alle Produkte in einer Kategorie. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Mengenrabatte werden nach der Installation nicht in meinen Produktlisten angezeigt.**
A:

1. **Modulstatus prüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Mengenrabatte auf Produktlisten“ installiert und aktiviert ist.
2. **Modul konfigurieren:** Klicken Sie für das Modul auf „Konfigurieren“ und stellen Sie sicher, dass die Haupteinstellung „Modul aktivieren“ auf JA gesetzt ist.
3. **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
4. **Produktrabatte prüfen:** Stellen Sie sicher, dass die Produkte, für die Sie Rabatte erwarten, tatsächlich Mengenrabatte in ihren Produkteinstellungen konfiguriert haben (Back Office > Katalog > Produkte > Produkt bearbeiten > Registerkarte Preise > Spezifische Preise).
5. **Theme-Kompatibilität:** Einige stark angepasste Themes erfordern möglicherweise geringfügige Anpassungen. Wenn es nach dem Leeren des Caches und der Überprüfung der Einstellungen immer noch nicht angezeigt wird, wenden Sie sich mit Details zu Ihrem Theme an den MyPresta.eu-Support.

**F2: Der Rabatttext wird angezeigt, sieht aber mit meinem Theme nicht gut aus (falsche Farben, Schriftart oder Ausrichtung).**
A:

1. **Modulkonfiguration:** Gehen Sie zur Konfigurationsseite des Moduls (**Module > Modul-Manager > Konfigurieren** für „Mengenrabatte auf Produktlisten“). Suchen Sie nach den Optionen „Styling & Anpassung“. Möglicherweise können Sie Farben, Schriftgrößen oder Abstände direkt hier anpassen.
2. **Benutzerdefiniertes CSS:** Wenn die Moduleinstellungen nicht genügend Kontrolle bieten, kann Ihr Webmaster oder Entwickler benutzerdefiniertes CSS zu Ihrem Theme hinzufügen, um die Standardstile des Moduls zu überschreiben. Die CSS-Dateien des Moduls (siehe Abschnitt 7.5) geben ihnen die notwendigen Klassenselektoren.

**F3: Ich möchte Mengenrabatte für bestimmte Produkte oder Kategorien ausblenden, aber nicht für alle.**
A:

1. **AdminPlqdSearchController:** Navigieren Sie zum dedizierten Admin-Bildschirm des Moduls (wahrscheinlich ein Unterreiter oder Link von der Hauptkonfiguration, möglicherweise benannt „Sucheinstellungen“ oder „Ausschlüsse“).
2. **Ausschlüsse hinzufügen:** Verwenden Sie die Tools auf diesem Bildschirm, um bestimmte Produkte oder ganze Kategorien zu suchen und einer Ausschlussliste hinzuzufügen. Sobald hinzugefügt, ignoriert das Modul diese Artikel bei der Anzeige von Rabatten auf Produktlisten.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
A: Das Modul ist auf Effizienz ausgelegt. Es nutzt die vorhandenen Mengenrabattdaten von PrestaShop.

1. **Caching aktivieren:** Stellen Sie sicher, dass die Option „Caching aktivieren“ in den erweiterten Einstellungen des Moduls auf JA gesetzt ist. Dies reduziert die Verarbeitungslast bei nachfolgenden Seitenaufrufen erheblich.
2. **Serverleistung:** Wenn Ihr Server bereits unterdimensioniert oder stark ausgelastet ist, kann jedes zusätzliche Modul einen geringfügigen Einfluss haben. Stellen Sie sicher, dass Ihr Hosting die empfohlenen Spezifikationen von PrestaShop erfüllt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Mengenrabatte auf Produktlisten“ (`plqd`) ist ein Standard-PrestaShop-Modul, das dem MVC-Muster folgt. Es erweitert hauptsächlich die Klasse `Module` und nutzt das PrestaShop-Hook-System, um Inhalte in Produktlistenvorlagen einzufügen. Es führt keine benutzerdefinierten `ObjectModel`-Entitäten ein, sondern liest vorhandene `SpecificPrice`-Daten. Das Modul verwendet einen dedizierten Admin-Controller (`AdminPlqdSearchController`) zur Verwaltung von Produkt-/Kategorieausschlüssen und integriert JavaScript und CSS für die Front-Office-Anzeige.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine explizit als eigenständige Front-Controller definiert. Das Modul fügt seine Inhalte wahrscheinlich direkt über Hooks in Templates ein und verarbeitet dynamische Inhalte oder AJAX über `displayAjax`-Methoden innerhalb der Hauptmodulklasse oder über enthaltenes JS.
- **Back-Office-Admin-Controller**:
  - `plqd/controllers/admin/AdminPlqdSearchController.php`
    - **Klassenname & Elternklasse**: `AdminPlqdSearchController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität**: Dieser Controller ist für die Verwaltung der Such- und Ausschluss-Einstellungen für Produkte und Kategorien zuständig. Er bietet wahrscheinlich eine Raster- oder Formularoberfläche zur Auswahl von Produkten/Kategorien, die keine Mengenrabatte auf Produktlisten anzeigen sollen. Er verwaltet keine spezifische `ObjectModel`, sondern Konfigurationsdaten (z.B. `Configuration::updateValue` für kommagetrennte IDs).
  - `plqd/controllers/admin/index.php`
    - Diese Datei ist in PrestaShop typischerweise eine Sicherheitsmaßnahme, die das direkte Auflisten von Verzeichnissen verhindert. Sie enthält normalerweise ein einfaches `header('Location: ../../index.php?controller=AdminHome');` oder `die('No direct script access');`. Sie dient nicht als funktionaler Controller für die Modullogik oder Benutzeroberfläche.

### 4.3 Kernklassen & Modelle (`classes/`)

In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` zu finden. Das Modul interagiert direkt mit den PrestaShop-Kernklassen `Product` und `SpecificPrice` sowie der Klasse `Configuration` für seine Einstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

- `plqd/lib/searchTool/views/js/autocomplete.js`
  - **Umfang**: Back-Office (wahrscheinlich innerhalb von `AdminPlqdSearchController` verwendet).
  - **Zweck**: Bietet Autocomplete-Funktionalität für die Suche nach Produkten oder Kategorien innerhalb der Admin-Ausschluss-Oberfläche. Es bindet sich an Eingabefelder, sendet AJAX-Anfragen an einen Backend-Endpunkt (möglicherweise `AdminPlqdSearchController` selbst oder einen dedizierten AJAX-Handler) und zeigt dem Benutzer Vorschläge an.
- `plqd/views/js/plqd.js`
  - **Umfang**: Front-Office.
  - **Zweck**: Dies ist das Haupt-Front-Office-JavaScript für das Modul. Es wird wahrscheinlich:
    - Produktlistenelemente beim Laden der Seite oder nach AJAX-Updates (z.B. Infinite Scroll, Kategoriefilter) scannen.
    - Die Mengenrabattinformationen dynamisch in die Produktkarten einfügen oder formatieren.
    - Responsive Anpassungen oder kleinere UI-Interaktionen im Zusammenhang mit der Rabattanzeige handhaben.
    - Potenziell AJAX-Aufrufe tätigen, um Rabattdaten abzurufen, wenn diese nicht von Smarty vorgerendert wurden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `plqd/lib/searchTool/views/css/autocomplete.css`
  - **Umfang**: Back-Office.
  - **Zweck**: Stile das Autocomplete-Dropdown und die Eingabefelder, die im `AdminPlqdSearchController` für die Produkt-/Kategoriesuche verwendet werden.
  - **Schlüsselselektoren**: Zielt wahrscheinlich auf Klassen wie `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` usw. ab.
- `plqd/views/css/plqd-classic.css`
  - **Umfang**: Front-Office.
  - **Zweck**: Bietet Standard-Styling für die Mengenrabattanzeige, möglicherweise zugeschnitten auf ältere PrestaShop-Themes oder einen „klassischen“ Look.
  - **Schlüsselselektoren**: Zielt auf den Hauptcontainer für Rabattinformationen (z.B. `.plqd-discounts-wrapper`), einzelne Rabattzeilen (`.plqd-discount-item`), Mengen (`.plqd-quantity`) und Preise (`.plqd-price`).
- `plqd/views/css/plqd-hide-default.css`
  - **Umfang**: Front-Office.
  - **Zweck**: Dieses Stylesheet enthält wahrscheinlich Regeln zum Ausblenden von Standard-Mengenrabattanzeigen, die in einigen Themes vorhanden sein könnten, um Duplikate zu vermeiden, wenn das Modul seine eigene gestylte Version einfügt.
  - **Schlüsselselektoren**: Könnte auf gängige Theme-Elemente wie `.product-price-and-shipping .discount-quantity` oder ähnliches abzielen.
- `plqd/views/css/plqd.css`
  - **Umfang**: Front-Office.
  - **Zweck**: Das primäre Front-Office-Stylesheet für das Modul, das das Kern-Styling für die Mengenrabattanzeige bereitstellt. Dies könnte ein moderneres oder allgemeineres Stylesheet sein als `plqd-classic.css`.
  - **Schlüsselselektoren**: Ähnlich wie `plqd-classic.css`, zielt auf `.plqd-discounts-wrapper`, `.plqd-discount-item` usw. ab. Entwickler können diese Klassen in der `custom.css` oder `theme.css` ihres Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `plqd/views/tpl/html.tpl`
    - **Hook**: Dies ist wahrscheinlich das Haupttemplate, das vom `hookDisplayProductListFunctionalButtons` (oder einem ähnlichen Produktlisten-Hook) des Moduls gerendert wird, um das Mengenrabatt-HTML für ein einzelnes Produkt auszugeben. Es empfängt Produkt- und spezifische Preisdaten vom Modul.
    - **Ausgabe**: Rendert das strukturierte HTML für die Mengenrabattzeilen (z.B. „Ab X Einheiten: Y €“).
- **Admin-Templates (`views/templates/admin/`)**:
  - `plqd/lib/searchTool/views/scripts.tpl`
    - **Zweck**: Dieses Template ist wahrscheinlich in der `AdminPlqdSearchController`-Ansicht enthalten. Es enthält JavaScript-Initialisierungen für die Autocomplete-Funktionalität (z.B. `$(document).ready()`-Blöcke, Variablendefinitionen für AJAX-URLs usw.) und möglicherweise CSS-Einbindungen.
  - `plqd/views/tpl/selectedProducts.tpl`
    - **Zweck**: Wird innerhalb von `AdminPlqdSearchController` verwendet, um die Liste der Produkte oder Kategorien anzuzeigen, die zum Ausschluss ausgewählt wurden. Es würde typischerweise eine Tabelle oder Liste dieser Elemente rendern, möglicherweise mit Optionen zum Entfernen.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `plqd/views/tpl/html-product-page.tpl`
    - **Zweck**: Dieses Template ist speziell für die Anzeige von Mengenrabatten auf der einzelnen Produktseite konzipiert, wenn das Modul entsprechend konfiguriert ist. Es könnte ein leicht anderes Styling oder eine andere Struktur als das Listenseiten-Template (`html.tpl`) haben, um besser zum Layout der Produktseite zu passen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es stützt sich auf die PrestaShop-Kerntabelle `ps_specific_price` für Mengenrabattdaten.
  - Konfigurationseinstellungen (z.B. aktivierter Status, Styling-Optionen, ausgeschlossene Produkt-/Kategorie-IDs) werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die typischerweise mit `PLQD_` präfixiert sind.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um die CSS-Dateien des Moduls (`plqd.css`, `plqd-classic.css`, `plqd-hide-default.css`) und JavaScript (`plqd.js`) einzubinden. |
| `displayProductListFunctionalButtons` | Innerhalb von Produktlistenelementen (z.B. Kategorie, Suchergebnisse). | Primärer Hook zum Einfügen des Mengenrabatt-HTML (`html.tpl`) in Produktkarten. |
| `displayProductPriceBlock` (Typ `after_price`) | Nach dem Hauptpreisblock auf Produktseiten. | Wird verwendet, um `html-product-page.tpl` einzufügen, wenn konfiguriert, um Rabatte auf Produktseiten anzuzeigen. |
| `displayRightColumn` / `displayLeftColumn` | In den rechten/linken Seitenleistenspalten. | Weniger wahrscheinlich für dieses Modul, könnte aber für einen Werbeblock im Zusammenhang mit Mengenrabatten verwendet werden, falls implementiert. |
| `displayFooter` | Am unteren Rand jeder Front-Office-Seite. | Könnte für spät ladendes JS oder zusätzliche Skripte verwendet werden, falls erforderlich. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Könnte verwendet werden, um den Modul-Cache für dieses Produkt zu leeren, um sicherzustellen, dass aktualisierte spezifische Preise widergespiegelt werden. |
| `actionModuleInstall` | Während der Modulinstallation. | Erstellt Konfigurationseinträge in `ps_configuration`. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Bereinigt Konfigurationseinträge und potenziell benutzerdefinierte Daten. |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwicklersupport für das Modul „Mengenrabatte auf Produktlisten“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität und Integration des Moduls gerne zur Verfügung.
