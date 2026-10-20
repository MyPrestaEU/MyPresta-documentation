---
title: "Massen-Produktkombinationen-Editor – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Massen-Produktkombinationen-Editor“ von MyPresta.eu."
sidebar:
  label: "Massen-Produktkombinationen-Editor – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Mass product combinations editor auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/mass-product-combinations-editor.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/mass-product-combinations-editor/)
>
> ---


# Massen-Produktkombinationen-Editor

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine speziellen Serveranforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Massen-Produktkombinationen-Editor)

Nachdem Sie auf „Konfigurieren“ für das Modul „Massen-Produktkombinationen-Editor“ geklickt haben, gelangen Sie zu einer speziellen Verwaltungsoberfläche. Hier werden Sie alle Ihre Massen-Kombinationsbearbeitungen durchführen.

Die Hauptkonfigurationsseite für dieses Modul dient als primäre Schnittstelle. Sie hat kein traditionelles „Einstellungsformular“ mit Schaltern und Eingabefeldern für das Modul selbst, sondern ist das Werkzeug zum Bearbeiten von Kombinationen.

Hier ist eine Aufschlüsselung dessen, was Sie sehen und wie Sie es verwenden:

**Bildschirmname & Menüpfad:**

- **Menüpfad:** Nach der Installation finden Sie in der Regel einen neuen Menüpunkt unter **Katalog** oder **Module** (abhängig von Ihrer PrestaShop-Version und Ihrem Theme) oder Sie können ihn jederzeit über **Module > Modul-Manager** aufrufen und neben „Massen-Produktkombinationen-Editor“ auf „Konfigurieren“ klicken.
- **Bildschirmtitel:** „Massen-Produktkombinationen-Editor“ oder ähnlich.

**Verfügbare Aktionen & Einstellungen:**

Die Hauptschnittstelle präsentiert Ihnen ein leistungsstarkes Raster oder eine Tabelle, die Produktkombinationen auflistet. Das genaue Aussehen kann zwischen PrestaShop-Versionen leicht variieren, aber die Kernfunktionalität bleibt konsistent.

1. **Produktauswahl / Filterung:**

   - **Was dies bewirkt:** Dieser Bereich ermöglicht es Ihnen, auszuwählen, welche Produktkombinationen Sie bearbeiten möchten. Möglicherweise sehen Sie eine Suchleiste, ein Produktauswahlfeld oder Filter nach Kategorie, Hersteller usw.
   - **Auswirkung der Änderung dieser Einstellung:** Durch die Auswahl eines Produkts oder das Anwenden von Filtern wird die Tabelle unten nur mit den Kombinationen der ausgewählten Produkte gefüllt. Dies ist entscheidend, um Ihren Fokus einzugrenzen.
   - **Empfohlener Wert:** Beginnen Sie mit der Suche nach einem bestimmten Produkt oder filtern Sie nach einer Kategorie, um sich mit der Oberfläche vertraut zu machen.
   - **Händlerszenario / Beispiel:** Sie möchten den Lagerbestand für alle Kombinationen Ihres Produkts „Sommer-T-Shirt“ aktualisieren. Sie würden nach „Sommer-T-Shirt“ suchen und es auswählen.
2. **Kombinationslistentabelle:**

   - **Was dies bewirkt:** Dies ist das Herzstück des Moduls. Es zeigt eine Tabelle an, in der jede Zeile eine eindeutige Produktkombination darstellt (z. B. „T-Shirt – Rot – Klein“). Die Spalten stellen bearbeitbare Felder dar, wie z. B.:
     - **Referenz:** Interne Produktnummer für diese spezifische Kombination.
     - **EAN13 / UPC:** Barcode-Nummern.
     - **Menge:** Lagerbestand für diese Kombination.
     - **Auswirkung auf den Preis:** Wie diese Kombination den Grundproduktpreis beeinflusst (z. B. +5 $ für Größe XL).
     - **Großhandelspreis:** Der Einkaufspreis dieser Kombination.
     - **Gewicht:** Wie diese Kombination das Grundproduktgewicht beeinflusst.
     - **Mindestmenge:** Die Mindestanzahl dieser Kombination, die ein Kunde kaufen muss.
     - **Standardkombination:** Ein Kontrollkästchen, um eine Kombination als Standard für das Produkt zu markieren.
     - **Bild:** Das dieser Kombination zugeordnete Bild.
   - **Auswirkung der Änderung dieser Einstellung:** Sie können direkt in Zellen dieser Tabelle klicken und neue Werte eingeben. Wenn Sie beispielsweise die „Menge“ von 5 auf 10 ändern, wird der Lagerbestand für diese spezifische Kombination aktualisiert.
   - **Empfohlener Wert:** Überprüfen Sie jede Kombination und ihre aktuellen Werte sorgfältig, bevor Sie Änderungen vornehmen.
   - **Händlerszenario / Beispiel:** Sie haben gerade eine neue Lieferung erhalten. Sie können die Spalte „Menge“ durchgehen und die Lagerbestände für alle relevanten Kombinationen in Sekundenschnelle aktualisieren.
3. **Speichern-Schaltfläche:**

   - **Was dies bewirkt:** Nachdem Sie alle gewünschten Änderungen in der Tabelle vorgenommen haben, **müssen** Sie eine Schaltfläche „Speichern“ oder „Änderungen übernehmen“ (normalerweise oben oder unten in der Tabelle zu finden) klicken, um Ihre Änderungen in der Datenbank zu speichern.
   - **Auswirkung der Änderung dieser Einstellung:** Bis Sie auf Speichern klicken, sind Ihre Änderungen nur auf dem Bildschirm sichtbar und nicht live in Ihrem Shop. Durch Klicken auf Speichern werden alle ausstehenden Änderungen angewendet.
   - **Empfohlener Wert:** Speichern Sie Ihre Arbeit immer häufig, insbesondere nach einer Reihe von Änderungen.
   - **Händlerszenario / Beispiel:** Sie haben Preise für 20 Kombinationen aktualisiert. Klicken Sie auf „Speichern“, um diese neuen Preise auf Ihren Produktseiten live zu schalten.

**Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**

1. **Identifizieren Sie Ihre Aufgabe:** Müssen Sie den Lagerbestand aktualisieren, Preise ändern oder Referenzen modifizieren?
2. **Navigieren Sie zum Modul:** Gehen Sie zu **Module > Modul-Manager** und klicken Sie auf „Konfigurieren“ für „Massen-Produktkombinationen-Editor“.
3. **Produkte auswählen:** Verwenden Sie die Such- oder Filteroptionen, um die Kombinationen zu laden, mit denen Sie arbeiten müssen.
4. **Änderungen vornehmen:** Bearbeiten Sie die Werte direkt in den Tabellenzellen. Sie können oft Tastenkombinationen (wie Tab) verwenden, um schnell zwischen den Feldern zu wechseln.
5. **Überprüfen:** Überprüfen Sie Ihre Änderungen noch einmal, bevor Sie speichern.
6. **Speichern:** Klicken Sie auf die Schaltfläche „Speichern“, um alle Änderungen anzuwenden.
7. **Cache leeren (falls erforderlich):** In einigen Fällen, insbesondere nach größeren Preis- oder Lagerbestandsänderungen, ist es eine gute Praxis, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung**), um sicherzustellen, dass die Änderungen sofort im Front Office sichtbar sind.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Produktauswahl/Filter | (Variiert je nach Produkt) | Engt die angezeigten Kombinationen zur Bearbeitung ein. |
| Modul-Konfigurationsseite | Kombinationslistentabelle (z. B. Menge, Preisauswirkung, Referenz, EAN13) | (Variiert je nach Produkt) | Direkte Bearbeitung von Kombinationsattributen. Änderungen werden auf die ausgewählte Kombination angewendet. |
| Modul-Konfigurationsseite | Speichern-Schaltfläche | Nach Änderungen klicken | Überträgt alle auf dem Bildschirm vorgenommenen Änderungen in die Datenbank und macht sie in Ihrem Shop live. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Änderungen werden nach dem Speichern nicht im Front Office angezeigt!**
A: Dies ist normalerweise ein Caching-Problem. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ / „Cache leeren“, je nach Ihrer Version). Ihre Änderungen sollten dann erscheinen.

**F: Das Modul lädt Kombinationen für Produkte mit vielen Variationen langsam.**
A: Bei Produkten mit Hunderten oder Tausenden von Kombinationen kann das Laden aller Daten einige Zeit in Anspruch nehmen. Dies ist aufgrund der Menge der verarbeiteten Daten normal. Stellen Sie sicher, dass Ihr Server die empfohlenen PrestaShop-Spezifikationen erfüllt. Wenn es durchweg sehr langsam ist, überprüfen Sie die PHP-Speicherbegrenzung und die Ausführungszeiteinstellungen Ihres Servers (Ihr Hosting-Anbieter kann Ihnen dabei helfen).

**F: Kann ich mit diesem Modul vorgenommene Änderungen rückgängig machen?**
A: Das Modul aktualisiert Ihre Datenbank direkt. Es gibt keine integrierte „Rückgängig“-Schaltfläche. Deshalb ist es entscheidend, **immer ein aktuelles Backup Ihres Shops zu haben**, bevor Sie Massenänderungen vornehmen. Wenn Sie einen Fehler machen, müssten Sie die Werte manuell korrigieren oder aus einem Backup wiederherstellen.

**F: Ich kann das Modul nach der Installation nicht im Menü finden.**
A: Navigieren Sie nach der Installation zu **Module > Modul-Manager**. Suchen Sie nach „Massen-Produktkombinationen-Editor“ und klicken Sie auf die Schaltfläche „Konfigurieren“ daneben. Dies führt Sie immer zur Moduloberfläche. Je nach Ihrer PrestaShop-Version und Ihrem Theme kann ein direkter Menülink unter „Katalog“ oder „Module“ für einen schnelleren Zugriff erscheinen.

**F: Funktioniert dieses Modul mit benutzerdefinierten Themes?**
A: Ja, dieses Modul arbeitet vollständig innerhalb des PrestaShop Back Office. Es gibt keine Front-Office-Elemente aus, daher sollte es vollständig mit jedem benutzerdefinierten Theme ohne Konflikte kompatibel sein.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Massen-Produktkombinationen-Editor“ (`qce`) ist primär ein Back-Office-Verwaltungstool. Es nutzt PrestaShops `Module`-Klasse für seine Kernfunktionalität und verwendet einen benutzerdefinierten AJAX-Endpunkt, um das dynamische Laden und Speichern von Produktkombinationsdaten zu handhaben. Die Moduloberfläche wird über eine Smarty-Vorlage gerendert, wobei JavaScript Benutzerinteraktionen und Datenübermittlung übernimmt. Es interagiert direkt mit PrestaShops Kernprodukt- und Kombinationsdatenstrukturen, ohne neue `ObjectModel`-Klassen oder Datenbanktabellen einzuführen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten `ModuleFrontController`- oder `AdminController`-Klassen im Verzeichnis `controllers/`. Die gesamte Back-Office-Logik, einschließlich des AJAX-Endpunkts, wird direkt in der Hauptmoduldatei `qce/ajax_qce.php` über die Methode `getContent()` behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul führt keine benutzerdefinierten Klassen in einem `classes/`-Verzeichnis ein. Es verwendet direkt PrestaShops Kernklassen wie `Product`, `Combination`, `Tools`, `Configuration` usw., um Daten abzurufen und zu aktualisieren.

### 4.4 JavaScript-Assets (`views/js/`)

- **`qce/views/admin/js/qce.js`**
  - **Geltungsbereich:** Back-Office (Admin-Panel).
  - **Zweck:** Dies ist die primäre JavaScript-Datei für die Moduloberfläche. Sie handhabt:
    - **Produktauswahl:** Verwaltet wahrscheinlich das Dropdown-Menü oder das Suchfeld zur Auswahl eines Produkts.
    - **AJAX-Datenladen:** Sendet AJAX-Anfragen an die `getContent()`-Methode des Moduls (oder einen spezifischen AJAX-Handler darin), um Kombinationsdaten für das ausgewählte Produkt abzurufen.
    - **Tabellen-Rendering:** Füllt die HTML-Tabelle dynamisch mit den vom Server empfangenen Kombinationsdaten.
    - **Direktbearbeitung:** Implementiert die Funktionalität, mit der Benutzer auf Tabellenzellen klicken und Werte direkt bearbeiten können (z. B. Eingabefelder, die beim Klicken erscheinen).
    - **Datenvalidierung:** Kann clientseitige Validierung für Eingabefelder enthalten (z. B. Sicherstellen, dass die Menge eine Zahl ist).
    - **AJAX-Datenspeicherung:** Sammelt alle geänderten Kombinationsdaten aus der Tabelle und sendet sie per AJAX an die `getContent()`-Methode des Moduls zur Verarbeitung und Speicherung in der Datenbank.
    - **Benutzer-Feedback:** Zeigt Lade-Spinner, Erfolgsmeldungen oder Fehlerwarnungen an.
    - **Event-Listener:** Bindet Listener an Elemente wie Produktauswahl-Dropdowns, Eingabefelder innerhalb der Tabelle und die Schaltfläche „Speichern“.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`qce/lib/blue/style.css`**

  - **Geltungsbereich:** Back-Office (Admin-Panel).
  - **Zweck:** Dies scheint ein Drittanbieter- oder generisches Stylesheet zu sein, möglicherweise für eine UI-Komponente oder ein spezifisches Styling-Theme, das innerhalb der Moduloberfläche verwendet wird. Es definiert wahrscheinlich allgemeine Tabellenstile, Eingabefeldstile oder Schaltflächenästhetik. Entwickler sollten diese Datei überprüfen, um ihre Auswirkungen auf die visuelle Darstellung des Moduls zu verstehen.
- **`qce/views/admin/css/qce.css`**

  - **Geltungsbereich:** Back-Office (Admin-Panel).
  - **Zweck:** Dies ist das spezifische Stylesheet des Moduls. Es enthält benutzerdefinierte CSS-Regeln, um die Kombinationsbearbeitungstabelle, Produktauswahlelemente und andere einzigartige UI-Komponenten auf der Konfigurationsseite des Moduls zu gestalten.
  - **Wichtige CSS-Klassenselektoren:** Entwickler, die das Erscheinungsbild des Moduls überschreiben oder anpassen möchten, sollten diese Datei nach Klassennamen wie `.qce-table`, `.qce-product-selector`, `.qce-input-field` usw. durchsuchen und diese in ihrem benutzerdefinierten Admin-Theme oder durch Überschreiben des Modul-CSS ansprechen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **`qce/views/admin/qce.tpl`**
  - **Geltungsbereich:** Admin-Vorlage.
  - **Zweck:** Dies ist die Haupt-Smarty-Vorlagendatei, die für das Rendern der gesamten Oberfläche des „Massen-Produktkombinationen-Editors“ im PrestaShop Back Office verantwortlich ist.
  - **Inhalt:** Sie enthält typischerweise:
    - Die HTML-Struktur für den Bereich zur Produktauswahl/Filterung.
    - Den Platzhalter (z. B. eine leere `<table>` oder `<div>`), wo die Kombinationsdaten dynamisch von `qce.js` geladen und gerendert werden.
    - Die Schaltfläche „Speichern“ und alle anderen Aktionsschaltflächen.
    - Includes für die notwendigen JavaScript- (`qce.js`) und CSS-Dateien (`qce.css`, `style.css`).
    - Alle anfänglichen Nachrichten oder Anweisungen für den Händler.
  - **Rendering:** Diese Vorlage wird von der `getContent()`-Methode der Moduldatei `ajax_qce.php` gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt **keine** benutzerdefinierten Datenbanktabellen.
  - Es liest und schreibt direkt in PrestaShops Kerntabellen, die sich auf Produkte und Kombinationen beziehen, hauptsächlich:
    - `ps_product_attribute` (Hauptkombinationsdaten)
    - `ps_product_attribute_shop` (Shop-spezifische Kombinationsdaten)
    - `ps_product_attribute_combination` (verknüpft Attribute mit Kombinationen)
    - `ps_product` (für Produktinformationen)
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` (für Attributdefinitionen)
    - `ps_image`, `ps_image_shop`, `ps_image_lang` (für Kombinationsbilder)
  - Konfigurationseinstellungen (falls vorhanden, über die Hauptschnittstelle hinaus) würden in `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine expliziten Front-Office- oder Back-Office-Anzeige-Hooks (`displayHeader`, `actionValidateOrder` usw.) im traditionellen Sinne. Seine Funktionalität wird direkt über seine Konfigurationsseite im Back Office aufgerufen. Die `install()`-Methode des Moduls würde sich als Admin-Modul registrieren und es über den Modul-Manager zugänglich machen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Massen-Produktkombinationen-Editor“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
