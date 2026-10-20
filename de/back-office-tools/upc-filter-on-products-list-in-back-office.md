---
title: "UPC-Filter in der Produktliste im Back Office – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'UPC-Filter in der Produktliste im Back Office' von MyPresta.eu."
sidebar:
  label: "UPC-Filter in der Produktliste im Back Office – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul UPC filter on products list in back office auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/upc-filter-on-products-list-in-back-office.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/upc-filter-on-products-list-in-back-office/)
>
> ---


# UPC-Filter in der Produktliste im Back Office

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul ist als Plug-and-Play konzipiert. Es verfügt über keinen dedizierten Konfigurationsbildschirm mit einzustellenden Optionen. Nach der Installation integriert das Modul die UPC-Spalte und den Filter automatisch in Ihre Produktliste im Back Office.

Die neue Funktionalität finden Sie unter:
**Back Office > Katalog > Produkte**

Auf dieser Seite sehen Sie nun:

- Eine neue Spalte mit der Bezeichnung „UPC“, die den UPC-Code für jedes Produkt anzeigt.
- Ein neues Filterfeld oben in der Spalte „UPC“, in das Sie einen UPC-Code (oder einen Teil davon) eingeben können, um die Produktliste zu filtern.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber die UPC-Spalte oder den Filter nicht in meiner Produktliste.**
A:
\* **Cache leeren:** Die häufigste Lösung ist das Leeren Ihres PrestaShop-Caches. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
\* **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul aktiviert ist. Gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „UPC-Filter in der Produktliste im Back Office“ und überprüfen Sie, ob es aktiv ist.
\* **Theme-Kompatibilität:** Obwohl selten bei Back-Office-Modulen, könnte ein stark angepasstes Admin-Theme potenziell stören. Wenn das Leeren des Caches nicht funktioniert, wechseln Sie vorübergehend zum Standard-PrestaShop-Admin-Theme, um zu sehen, ob die Spalte erscheint.
\* **Modulposition:** Dieses Modul modifiziert bestehende Templates. Stellen Sie sicher, dass das Modul korrekt installiert ist und während der Installation keine Fehler angezeigt werden.

**F: Die UPC-Spalte ist vorhanden, aber einige Produkte zeigen keinen UPC an.**
A: Dieses Modul zeigt lediglich den UPC-Code an, der bereits in den Produktinformationen gespeichert ist. Wenn ein Produkt keinen UPC anzeigt, bedeutet dies, dass das UPC-Feld für dieses spezifische Produkt in Ihrem PrestaShop-Katalog leer ist. Sie müssen das Produkt bearbeiten (Katalog > Produkte > Produkt bearbeiten > Reiter Mengen) und den UPC-Code dort eingeben.

**F: Kann ich die Position der UPC-Spalte ändern?**
A: Das Modul integriert die UPC-Spalte an einer bestimmten Position in der Produkttabellenliste. Es gibt keine Konfigurationsoption innerhalb des Moduls, um seine Position zu ändern. Dies würde benutzerdefinierte Template-Modifikationen erfordern (siehe Entwicklerhandbuch).

**F: Fügt dieses Modul UPC-Felder zu Produkten hinzu, wenn sie nicht existieren?**
A: Nein, dieses Modul geht davon aus, dass Ihre PrestaShop-Installation bereits das Standard-UPC-Feld für Produkte zur Verfügung hat (was standardmäßig der Fall ist). Es zeigt und filtert nur basierend auf den Daten, die Sie bereits in dieses Feld eingegeben haben.

**F: Wird dieses Modul mein Back Office verlangsamen?**
A: Das Modul ist hochoptimiert. Es nutzt die bestehenden Filtermechanismen von PrestaShop und fügt lediglich eine einfache Spaltenanzeige hinzu. Es sollte die Leistung Ihrer Back-Office-Produktliste nicht merklich beeinträchtigen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die das Modul „UPC-Filter in der Produktliste im Back Office“ verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht

Das Modul funktioniert hauptsächlich durch das Überschreiben spezifischer Twig-Templates, die für die Produktkatalogliste im PrestaShop-Back Office verwendet werden. Es injiziert den notwendigen HTML-Code für den UPC-Spaltenkopf und die Filter-Eingabe und modifiziert dann das Produktzeilen-Template, um den UPC-Wert anzuzeigen. Die Filterlogik wird vom nativen `AdminProducts`-Controller von PrestaShop gehandhabt, der das `upc`-Feld automatisch zum Filtern erkennt, sobald es im Template vorhanden ist.

### 4.2 Controller (`controllers/`)

Dieses Modul führt **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität wird durch Template-Overrides und die Nutzung bestehender PrestaShop-Controller-Logik erreicht.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt **keine** benutzerdefinierten PHP-Klassen oder `ObjectModel`-Definitionen ein. Es interagiert direkt mit vorhandenen PrestaShop-Produktdaten.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Die Filterfunktionalität wird serverseitig vom `AdminProducts`-Controller von PrestaShop gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Es basiert auf dem Standard-Back-Office-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul verwendet die neue Twig-Templating-Engine, die in PrestaShop 1.7+ für Back-Office-Seiten eingeführt wurde. Es überschreibt zwei Kern-Produktlisten-Templates:

- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**

  - **Zweck:** Dieses Template ist für das Rendern der Hauptproduktkatalogseite verantwortlich, einschließlich des Tabellenkopfes und des Such-/Filterformulars.
  - **Modifikation:** Das Modul injiziert ein neues `<th>`-Element für die „UPC“-Spalte in den Tabellenkopf und ein entsprechendes Eingabefeld zum Filtern in das Suchformular. Dies ermöglicht es dem `AdminProducts`-Controller, das `upc`-Feld zum Filtern zu erkennen.
- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**

  - **Zweck:** Dieses Template ist für das Rendern der einzelnen Zeilen der Produktlistentabelle verantwortlich.
  - **Modifikation:** Das Modul fügt ein neues `<td>`-Element innerhalb der Produktschleife hinzu, um den `product.upc`-Wert für jedes Produkt anzuzeigen.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**: Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen. Es liest das `upc`-Feld aus der Standardtabelle `ps_product`.
- **Registrierte Hooks-Tabelle**: Dieses Modul registriert **keine** spezifischen Hooks im traditionellen PrestaShop-Sinne (z.B. `displayHeader`, `actionValidateOrder`). Seine Integration wird ausschließlich durch Twig-Template-Overrides erreicht, die eine Form des impliziten „Hookings“ in den Rendering-Prozess darstellen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „UPC-Filter in der Produktliste im Back Office“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls zur Verfügung.
