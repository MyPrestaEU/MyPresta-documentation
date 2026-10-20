---
title: "Back office Ajax-Produktsuche – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Back office Ajax-Produktsuche' von MyPresta.eu."
sidebar:
  label: "Back office Ajax-Produktsuche – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Back office ajax product search auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/back-office-ajax-product-search.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/back-office-ajax-product-search/)
>
> ---


# Back office Ajax-Produktsuche

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul ist so konzipiert, dass es hoch effizient und weitgehend „einmal einrichten und vergessen“ ist. Es integriert sich nahtlos in Ihr Backoffice, ohne komplexe Konfigurationen zu erfordern.

Wenn Sie nach der Installation auf „Konfigurieren“ klicken, finden Sie typischerweise eine einfache Benutzeroberfläche, oft ohne spezifische Einstellungen zum Anpassen. Die Kernfunktionalität des Moduls (AJAX-Produktsuche mit Autovervollständigung) ist standardmäßig nach der Installation aktiviert.

- **Was dieser Bildschirm leistet:** Dies ist der Hauptkonfigurationsbereich für das Modul. Für die „Back office Ajax-Produktsuche“ besteht seine Hauptfunktion jedoch darin, zu bestätigen, dass das Modul installiert und aktiv ist.
- **Auswirkung von Einstellungsänderungen:** Da auf diesem Bildschirm keine spezifischen, vom Benutzer konfigurierbaren Einstellungen angezeigt werden, arbeitet das Modul mit seinem standardmäßigen, optimierten Verhalten.
- **Empfohlener Wert:** Hier sind normalerweise keine spezifischen Aktionen erforderlich. Das Modul ist so konzipiert, dass es sofort einsatzbereit ist.
- **Händlerszenario / Beispiel:** Navigieren Sie nach der Installation einfach zu einer beliebigen Backoffice-Seite. Sie sollten bemerken, dass, wenn Sie in einem Produktsuchfeld zu tippen beginnen, sofort Vorschläge erscheinen und ein Klick darauf Sie direkt zur Produktbearbeitungsseite führt.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | (Keine spezifischen Einstellungen) | N/A | Das Modul erweitert die Produktsuche im Backoffice automatisch mit AJAX-Autovervollständigungsfunktionen nach der Installation. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, aber die Suchleiste scheint nicht anders zu funktionieren.**
A:

1. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal muss der PrestaShop-Cache geleert werden, damit neue Modul-Assets (wie JavaScript und CSS) korrekt geladen werden.
2. **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder in einem Inkognito-/privaten Browserfenster zu testen.
3. **Modulstatus:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** aktiviert ist.
4. **Theme-Kompatibilität:** Obwohl selten bei Backoffice-Modulen, könnte ein stark angepasstes Admin-Theme stören. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F: Wird dieses Modul mein Backoffice verlangsamen?**
A: Nein, ganz im Gegenteil. Durch die Verwendung von AJAX führt das Modul Suchen im Hintergrund ohne vollständige Seitenneuladungen durch, was von Natur aus schneller und effizienter ist als herkömmliche Suchmethoden. Es wurde entwickelt, um die Leistung zu verbessern, nicht zu beeinträchtigen.

**F: Beeinflusst dieses Modul die Front-Office-Suche für meine Kunden?**
A: Nein, dieses Modul ist ausschließlich für das PrestaShop Back Office. Es hat keine Auswirkungen auf Ihren kundenorientierten Shop oder dessen Suchfunktion.

**F: Kann ich die Anzahl der angezeigten Suchergebnisse konfigurieren?**
A: Dieses Modul ist auf Einfachheit und sofortige Funktionalität ausgelegt. Es bietet typischerweise keine konfigurierbaren Optionen für die Anzahl der Ergebnisse. Das Standardverhalten ist normalerweise für eine gute Benutzererfahrung optimiert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

### 4.1 Architekturübersicht

Das Modul `Back office Ajax-Produktsuche` (boproductfinder) ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die Verbesserung der Benutzererfahrung im Backoffice konzentriert. Es erreicht seine Funktionalität, indem es benutzerdefinierte JavaScript- und CSS-Assets in den Backoffice-Header injiziert und dabei das PrestaShop-Hook-System nutzt. Die Kernlogik liegt in clientseitigem JavaScript, das Benutzereingaben in bestimmten Suchfeldern abfängt und AJAX-Anfragen an PrestaShops integrierte Produktsuch-Endpunkte sendet, um dann die Ergebnisse mithilfe einer Autovervollständigungs-Benutzeroberfläche anzuzeigen. Es führt keine neuen Datenbanktabellen oder komplexe serverseitige Logik ein, die über das hinausgeht, was PrestaShop bereits für die Produktsuche bereitstellt.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Es stützt sich auf bestehende PrestaShop-Controller zur Verarbeitung von Produktsuchanfragen (z.B. die AJAX-Methoden von `AdminProductsController`).

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten PHP-Klassen oder `ObjectModel`-Definitionen ein. Seine Funktionalität ist primär clientseitig.

### 4.4 JavaScript-Assets (`views/js/`)

- **`boproductfinder/views/autocomplete.js`**
  - **Geltungsbereich**: Back-Office.
  - **Beschreibung**: Dieses Skript implementiert oder integriert wahrscheinlich eine generische Autovervollständigungsbibliothek. Es bietet die Kernfunktionalität zum Anzeigen von Vorschlägen, während der Benutzer in ein Texteingabefeld tippt. Es handhabt das UI-Rendering der Vorschlagsliste, die Tastaturnavigation innerhalb der Liste und die Auswahl von Elementen. Es ist eine grundlegende Komponente für die interaktive Suche des Moduls.
- **`boproductfinder/views/boproductfinder.js`**
  - **Geltungsbereich**: Back-Office.
  - **Beschreibung**: Dies ist das Hauptskript für das Modul.
  - **Event-Listener**: Es bindet wahrscheinlich an `keyup`- oder `input`-Ereignisse auf spezifischen Produktsuch-Eingabefeldern innerhalb des PrestaShop-Backoffice (z.B. `input[name="product_search"]` oder ähnliche Selektoren).
  - **AJAX-Aufrufe**: Wenn ein Benutzer tippt, löst dieses Skript AJAX-Anfragen an die interne Produktsuch-API von PrestaShop aus (z.B. `admin-ajax.php` oder eine spezifische AJAX-Aktion eines Admin-Controllers für die Produktsuche). Es sendet die Suchanfrage und möglicherweise andere Parameter (z.B. `id_lang`).
  - **DOM-Manipulation**: Es empfängt die JSON-Antwort vom Server (die Produkt-IDs, Namen und möglicherweise Links enthält) und verwendet `autocomplete.js` (oder eine ähnliche Logik), um diese Ergebnisse in einer Dropdown-Liste unter dem Suchfeld anzuzeigen.
  - **Navigation**: Wenn ein Produktvorschlag angeklickt oder ausgewählt wird, konstruiert dieses Skript die URL zur Bearbeitungsseite des Produkts (z.B. `admin/index.php?controller=AdminProducts&id_product=X&updateproduct&token=Y`) und leitet den Browser zu dieser Seite um.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`boproductfinder/views/autocomplete.css`**
  - **Geltungsbereich**: Back-Office-Admin-Formular-Styling.
  - **Beschreibung**: Dieses Stylesheet bietet die visuelle Gestaltung für die Autovervollständigungs-Vorschlagsliste.
  - **Wichtige UI-Komponenten und Container, die es gestaltet**:
    - Der Dropdown-Container für Suchergebnisse.
    - Einzelne Listenelemente innerhalb der Vorschläge.
    - Hervorhebung für den aktuell schwebenden oder ausgewählten Vorschlag.
    - Potenziell Ladeindikatoren oder „keine Ergebnisse“-Meldungen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler können den generierten HTML-Code nach Klassen wie `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` untersuchen, um das Erscheinungsbild in ihrem Admin-Theme anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien (`.tpl`). Seine Funktionalität wird direkt über JavaScript- und CSS-Assets injiziert, die über Hooks geladen werden.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es stützt sich auf die bestehenden PrestaShop-Tabellen `ps_product`, `ps_product_lang` und verwandte Tabellen für Produktdaten. Die Konfiguration wird in `ps_configuration` gespeichert, falls Einstellungen vorhanden waren, aber für dieses Modul ist dies typischerweise minimal oder nicht existent.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich jeder Backoffice-Seite ausgeführt. | Wird verwendet, um die CSS- und JavaScript-Dateien des Moduls (`autocomplete.css`, `autocomplete.js`, `boproductfinder.js`) einzubinden, um sicherzustellen, dass sie auf allen Admin-Seiten geladen werden, auf denen die Suchfunktion benötigt werden könnte. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Ein alternativer oder ergänzender Hook zu `displayBackOfficeHeader` zum Hinzufügen von CSS- und JS-Dateien, um die Kompatibilität über verschiedene PrestaShop-Versionen und Backoffice-Themes hinweg zu gewährleisten. Er stellt sicher, dass die Assets des Moduls ordnungsgemäß registriert und geladen werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Back office Ajax-Produktsuche“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität oder Kompatibilität des Moduls gerne zur Verfügung.
