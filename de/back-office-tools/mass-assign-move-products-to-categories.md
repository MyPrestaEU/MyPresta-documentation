---
title: "Produkte massenhaft zuordnen / verschieben - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produkte massenhaft zuordnen / verschieben' von MyPresta.eu."
sidebar:
  label: "Produkte massenhaft zuordnen / verschieben - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Mass assign / move products to categories auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/mass-assign-move-products-to-categories.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/mass-assign-move-products-to-categories/)
>
> ---


# Produkte massenhaft zuordnen / verschieben

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Produkte massenhaft zuordnen / verschieben“ bietet eine assistentenähnliche Oberfläche, die Sie durch den Prozess der Massenverwaltung von Produktkategorien führt.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Modul-Manager > „Produkte massenhaft zuordnen / verschieben“ konfigurieren)

Nach dem Klicken auf „Konfigurieren“ gelangen Sie zur Hauptkonfigurationsseite des Moduls, die als Schritt-für-Schritt-Assistent fungiert.

#### Schritt 1: Produkte zur Verwaltung auswählen

Dieser Abschnitt ermöglicht es Ihnen, zu definieren, welche Produkte Sie ändern möchten.

-   **Was diese Einstellung bewirkt:** Dies ist der erste entscheidende Schritt, in dem Sie die Gruppe von Produkten identifizieren, die von der Massenaktion betroffen sein werden.
-   **Auswirkung der Änderung dieser Einstellung:** Die hier ausgewählten Produkte werden in den nachfolgenden Schritten die einzigen sein, die verarbeitet werden.
-   **Empfohlener Wert:** Verwenden Sie die Suchleiste, um Produkte nach Namen zu finden. Sie können mehrere Produkte zur Liste hinzufügen.
-   **Händler-Szenario / Beispiel:**
    - *Szenario 1: Spezifische Produkte:* Sie möchten „Produkt A“, „Produkt B“ und „Produkt C“ in eine neue Kategorie verschieben. Sie würden jedes Produkt suchen und zur Liste hinzufügen.
    - *Szenario 2: Produkte aus einer bestehenden Kategorie:* Sie möchten alle Produkte, die sich derzeit in Ihrer Kategorie „Alte Kollektion“ befinden, in eine neue Kategorie „Archivierte Artikel“ verschieben. Sie würden hier zuerst alle Produkte aus „Alte Kollektion“ auswählen.

#### Schritt 2: Kategorien auswählen, denen Produkte zugewiesen/verschoben werden sollen

Dieser Abschnitt ermöglicht es Ihnen, die Zielkategorien für Ihre ausgewählten Produkte zu wählen.

-   **Was diese Einstellung bewirkt:** Hier geben Sie die Kategorien an, denen die Produkte aus Schritt 1 zugewiesen oder in die sie verschoben werden sollen.
-   **Auswirkung der Änderung dieser Einstellung:** Die ausgewählten Produkte werden mit diesen Kategorien verknüpft.
-   **Empfohlener Wert:** Verwenden Sie den Kategoriebaum, um eine oder mehrere Zielkategorien auszuwählen.
-   **Händler-Szenario / Beispiel:**
    - *Szenario 1: Einer neuen Kategorie zuweisen:* Sie haben in Schritt 1 5 Produkte ausgewählt. Nun wählen Sie hier „Neuheiten“ und „Bestseller“ aus. Die 5 Produkte werden sowohl „Neuheiten“ als auch „Bestsellern“ zugewiesen.
    - *Szenario 2: In eine einzelne Kategorie verschieben:* Sie haben 10 Produkte ausgewählt. Sie wählen hier „Saisonale Angebote“ aus. Je nach Ihrer Wahl in Schritt 3 werden diese Produkte entweder zu „Saisonale Angebote“ hinzugefügt oder ausschließlich dorthin verschoben.

#### Schritt 3: Was soll mit den ausgewählten Produkten geschehen?

Dies ist der wichtigste Schritt, der die Art der Massenaktion bestimmt.

-   **Was diese Einstellung bewirkt:** Diese Radio-Button-Auswahl bestimmt, ob Produkte *zugewiesen* (zu neuen Kategorien hinzugefügt, während bestehende beibehalten werden) oder *verschoben* (aus bestehenden Kategorien entfernt und nur in die neuen platziert) werden.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   **Produkte ausgewählten Kategorien zuweisen:**
        -   *Wenn ausgewählt:* Die in Schritt 1 ausgewählten Produkte werden den in Schritt 2 ausgewählten Kategorien *hinzugefügt*. Sie behalten alle ihre aktuellen Kategoriezuordnungen bei. Dies ist nützlich, um Produkte in mehreren Listen aufzuführen oder sie zu Werbekategorien hinzuzufügen, ohne ihre primäre Platzierung zu stören.
        -   *Händler-Szenario:* Sie haben ein Produkt in „Elektronik“ und „Gadgets“. Sie möchten es zu „Feiertagsangebote“ hinzufügen, ohne es aus „Elektronik“ oder „Gadgets“ zu entfernen. Sie würden „Zuweisen“ auswählen.
    -   **Produkte in ausgewählte Kategorien verschieben (aus aktuellen Kategorien entfernen):**
        -   *Wenn ausgewählt:* Die in Schritt 1 ausgewählten Produkte werden aus allen Kategorien, denen sie derzeit zugewiesen sind, *entfernt* und dann *nur* den in Schritt 2 ausgewählten Kategorien zugewiesen. Dies ist eine vollständige Neukategorisierung.
        -   *Händler-Szenario:* Sie haben ein Produkt in „Alte Kollektion“ und „Auslaufartikel“. Sie möchten, dass es *nur* in „Archivierte Produkte“ erscheint. Sie würden „Verschieben“ auswählen.
-   **Empfohlener Wert:** Dies hängt vollständig von Ihrem spezifischen Ziel ab. Überlegen Sie sorgfältig, ob Sie Kategorien *hinzufügen* oder *ersetzen* möchten.
-   **Händler-Szenario / Beispiel:**
    -   *Zuweisen:* Sie führen einen „Black Friday“-Verkauf durch. Sie wählen alle Sale-Produkte aus und „weisen“ sie der Kategorie „Black Friday Deals“ zu. Sie erscheinen weiterhin in ihren ursprünglichen Kategorien (z.B. „T-Shirts“, „Laptops“), aber jetzt auch unter „Black Friday Deals“.
    -   *Verschieben:* Sie haben beschlossen, Ihren Bereich „Damenbekleidung“ neu zu strukturieren. Sie wählen alle Produkte aus „Kleider“ und „Röcke“ aus und „verschieben“ sie in eine neue Kategorie „Damen Unterteile & Kleider“. Sie werden nicht mehr in den alten Kategorien „Kleider“ oder „Röcke“ erscheinen.

#### Schaltfläche „Ausführen“

-   **Was diese Einstellung bewirkt:** Diese Schaltfläche initiiert den Massenvorgang basierend auf Ihren Auswahlen in den vorherigen Schritten.
-   **Auswirkung der Änderung dieser Einstellung:** Nach dem Klicken verarbeitet das Modul alle ausgewählten Produkte gemäß Ihrer gewählten Aktion (zuweisen oder verschieben) und Zielkategorien. Eine Bestätigungs- oder Erfolgsmeldung wird typischerweise angezeigt.
-   **Empfohlener Wert:** Klicken Sie dies nur, wenn Sie sich Ihrer Auswahl absolut sicher sind.
-   **Händler-Szenario / Beispiel:** Nachdem Sie Ihre Produkt- und Kategorieauswahlen sorgfältig überprüft und Ihre gewünschte Aktion (zuweisen oder verschieben) bestätigt haben, klicken Sie auf „Ausführen“, um die Änderungen auf den Produktkatalog Ihres Shops anzuwenden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | **Schritt 1: Produkte auswählen** | N/A (Benutzereingabe) | Definiert die spezifischen Produkte, die von der Massenaktion betroffen sein sollen. |
| Hauptkonfiguration | **Schritt 2: Kategorien auswählen** | N/A (Benutzereingabe) | Definiert die Zielkategorien, denen Produkte zugewiesen oder in die sie verschoben werden. |
| Hauptkonfiguration | **Schritt 3: Was tun?** | N/A (Benutzerwahl) | **Zuweisen:** Fügt Produkte zu neuen Kategorien hinzu, behält bestehende bei. **Verschieben:** Entfernt aus allen aktuellen Kategorien, weist nur neuen zu. |
| Hauptkonfiguration | **Schaltfläche Ausführen** | N/A (Benutzeraktion) | Löst den Massenvorgang zum Zuweisen/Verschieben von Kategorien aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe auf „Ausführen“ geklickt, aber es ist nichts passiert, oder ich sehe die Änderungen nicht.**
A:

1.  **Cache leeren:** Nach jeder größeren Änderung in PrestaShop, insbesondere bei Kategorie- oder Produktzuweisungen, sollten Sie immer den Cache Ihres Shops leeren. Gehen Sie zu **Erweiterte Parameter > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
2.  **Produktstatus überprüfen:** Stellen Sie sicher, dass die Produkte, die Sie zuweisen/verschieben möchten, aktiv und sichtbar sind.
3.  **Kategoriestatus überprüfen:** Stellen Sie sicher, dass die Zielkategorien aktiv und sichtbar sind.
4.  **Modul erneut ausführen:** Gehen Sie zurück zum Modul, wählen Sie Ihre Produkte und Kategorien erneut aus und versuchen Sie es noch einmal.

**F: Meine Produkte sind nach der Verwendung des Moduls aus ihren ursprünglichen Kategorien verschwunden!**
A: Dies bedeutet wahrscheinlich, dass Sie in Schritt 3 „Produkte in ausgewählte Kategorien verschieben (aus aktuellen Kategorien entfernen)“ ausgewählt haben. Diese Option ist darauf ausgelegt, bestehende Kategoriezuweisungen durch die neuen zu *ersetzen*. Wenn dies unbeabsichtigt war, müssen Sie Produkte manuell ihren ursprünglichen Kategorien neu zuweisen oder das Modul erneut mit der Option „Produkte zuweisen“ verwenden, um sie wieder hinzuzufügen. Überprüfen Sie immer Schritt 3 sorgfältig, bevor Sie ausführen!

**F: Kann ich eine Massenzuweisung/-verschiebung rückgängig machen?**
A: Das Modul hat keine „Rückgängig“-Schaltfläche. Deshalb ist es entscheidend, **immer ein Backup Ihrer Datenbank zu erstellen, bevor Sie Massenaktionen** in Ihrem Shop durchführen. Wenn Sie einen Fehler gemacht haben, ist das Wiederherstellen eines Backups der sicherste Weg, um die Änderungen rückgängig zu machen. Andernfalls müssen Sie die Kategoriezuweisungen manuell korrigieren oder das Modul erneut verwenden, um Produkte bei Bedarf neu zuzuweisen.

**F: Die Produktsuche findet meine Produkte nicht.**
A:

1.  **Rechtschreibung überprüfen:** Stellen Sie sicher, dass Sie den Produktnamen korrekt eingeben.
2.  **Produktstatus:** Stellen Sie sicher, dass das Produkt in Ihrem Katalog aktiv ist.
3.  **Browser-Cache leeren:** Manchmal kann der Browser-Cache AJAX-Suchfunktionen stören. Versuchen Sie, den Cache Ihres Browsers zu leeren oder ein Inkognito-Fenster zu verwenden.

**F: Beeinflusst dieses Modul die Standardkategorie eines Produkts?**
A: Das Modul verwaltet hauptsächlich die *zugeordneten* Kategorien. Während das Verschieben eines Produkts implizit seine Standardkategorie ändern könnte, wenn die alte Standardkategorie entfernt und nur eine neue Kategorie zugewiesen wird, ist es am besten, die Standardkategorie auf der Produktbearbeitungsseite manuell zu überprüfen und festzulegen, wenn Sie spezifische SEO- oder Navigationsanforderungen für die Standardkategorie haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „Produkte massenhaft zuordnen / verschieben“ verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht

Das Modul `masspc` (Mass Product Categories) ist ein Standard-PrestaShop-Modul, das hauptsächlich im Back Office arbeitet. Es nutzt AJAX für die Produktsuche und Kategorieauswahl und bietet eine assistentenähnliche Benutzererfahrung. Die Kernlogik für die Produkt- und Kategorienmanipulation wird innerhalb der Hauptmodulklasse gehandhabt, die `Module` erweitert. Es führt keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Admin-Controller über seine Hauptkonfigurationsseite hinaus ein.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Admin-Controller im Verzeichnis `controllers/`. Die gesamte Logik wird direkt in der Hauptmoduldatei `masspc.php` (oder `ajax_products_list.php` gemäß dem Dossier, was eine ungewöhnliche Namenskonvention für die Hauptmoduldatei ist, aber impliziert, dass sie die Kernlogik und AJAX-Anfragen verarbeitet) gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder Modelle in einem `classes/`-Verzeichnis ein. Die gesamte Kernlogik ist in der Hauptmoduldatei gekapselt. Die Manipulation von Produkt- und Kategoriedaten basiert auf den nativen `Product`- und `Category`-`ObjectModel`-Klassen von PrestaShop und deren zugehörigen Methoden (z.B. `Product::updateCategories()`).

### 4.4 JavaScript-Assets (`views/js/`)

-   **`masspc/lib/searchTool/views/js/autocomplete.js`**
    -   **Geltungsbereich:** Back-Office (wird auf der Konfigurationsseite des Moduls verwendet).
    -   **Beschreibung:** Dieses Skript bietet wahrscheinlich die Kernfunktionalität für eine AJAX-basierte Autocomplete-Suchfunktion, speziell zum Auffinden von Produkten nach Namen. Es überwacht Benutzereingaben in einem Suchfeld, sendet AJAX-Anfragen an das Backend des Moduls (wahrscheinlich `ajax_products_list.php` selbst oder eine Methode darin) und zeigt Vorschläge an. Es verarbeitet die Auswahl von Produkten und deren Hinzufügen zur Liste zur Verarbeitung.
-   **`masspc/views/js/jquery.autocomplete.js`**
    -   **Geltungsbereich:** Back-Office (wird auf der Konfigurationsseite des Moduls verwendet).
    -   **Beschreibung:** Dies scheint ein jQuery-Plugin oder ein benutzerdefiniertes Skript zu sein, das die Autocomplete-Funktionalität implementiert oder erweitert. Es könnte eine Abhängigkeit für `autocomplete.js` oder eine alternative/ältere Implementierung sein. Es würde die visuelle Darstellung der Autocomplete-Vorschläge und die Interaktion bei der Auswahl eines Elements durch den Benutzer handhaben.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`masspc/lib/searchTool/views/css/autocomplete.css`**
    -   **Geltungsbereich:** Back-Office (gestaltet die Konfigurationsseite des Moduls).
    -   **Beschreibung:** Dieses Stylesheet bietet die visuelle Gestaltung für das Autocomplete-Sucheingabefeld, das Vorschlags-Dropdown und möglicherweise die Liste der ausgewählten Produkte innerhalb der Konfigurationsoberfläche des Moduls. Entwickler können diese Stile in ihrem benutzerdefinierten Admin-Theme überschreiben oder durch Hinzufügen spezifischerer CSS-Regeln.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`masspc/lib/searchTool/views/scripts.tpl`**
    -   **Geltungsbereich:** Back-Office (auf der Konfigurationsseite des Moduls enthalten).
    -   **Beschreibung:** Dieses Template enthält wahrscheinlich JavaScript-Code oder Links zu JS-Dateien (`autocomplete.js`, `jquery.autocomplete.js`) und möglicherweise CSS-Dateien (`autocomplete.css`), die für die Produktsuch- und Auswahl-Oberfläche erforderlich sind. Es wird typischerweise verwendet, um Assets in den `<head>` oder `<body>` der Admin-Seite einzufügen.
-   **`masspc/views/templates/admin/cselection.tpl`**
    -   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
    -   **Beschreibung:** Dieses Template rendert den Abschnitt „Schritt 2: Kategorien auswählen, denen Produkte zugewiesen/verschoben werden sollen“ des Moduls. Es zeigt die Kategoriebaumstruktur an, die es dem Administrator ermöglicht, Zielkategorien auszuwählen. Es verwendet wahrscheinlich eine rekursive Struktur, um Eltern- und Kindkategorien anzuzeigen.
-   **`masspc/views/templates/admin/target_products.tpl`**
    -   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
    -   **Beschreibung:** Dieses Template rendert den Abschnitt „Schritt 1: Produkte zur Verwaltung auswählen“. Es enthält das Produktsucheingabefeld (wo `autocomplete.js` arbeitet) und zeigt die Liste der Produkte an, die für die Massenaktion ausgewählt wurden.
-   **`masspc/views/templates/admin/wtd.tpl`**
    -   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
    -   **Beschreibung:** Dieses Template rendert den Abschnitt „Schritt 3: Was soll mit den ausgewählten Produkten geschehen?“. Es enthält die Radio-Buttons für „Produkte ausgewählten Kategorien zuweisen“ und „Produkte in ausgewählte Kategorien verschieben“, zusammen mit deren Beschreibungen.
-   **`masspc/views/templates/hook/form.tpl`**
    -   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
    -   **Beschreibung:** Dies ist wahrscheinlich das Haupt-Wrapper-Template für das Konfigurationsformular des Moduls, das die anderen `admin/`-Templates (`target_products.tpl`, `cselection.tpl`, `wtd.tpl`) enthält, um die vollständige Assistentenoberfläche zu erstellen. Es würde die gesamte Formularstruktur und die Schaltfläche „Ausführen“ enthalten.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    -   Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es interagiert direkt mit den Kerntabellen von PrestaShop:
        -   `ps_product_category`: Zur Verwaltung von Produkt-Kategorie-Zuordnungen.
        -   `ps_product_shop`: Für produktspezifische Shop-Daten, einschließlich der Standardkategorie.
        -   `ps_category`: Zum Abrufen von Kategorienamen und -struktur.
        -   `ps_product`: Zum Abrufen von Produktnamen und -details für die Suche.
-   **Registrierte Hooks-Tabelle**:
    -   Die primäre Funktionalität des Moduls wird über seine Konfigurationsseite aufgerufen, nicht über Front-Office-Hooks.
    -   Es verwendet wahrscheinlich den Hook `displayBackOfficeHeader`, um seine CSS- und JavaScript-Assets in den Back Office-Header einzufügen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendert im `<head>` der Back Office-Seiten. | Fügt modulspezifische CSS- und JavaScript-Dateien für die Konfigurationsseite ein. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produkte massenhaft zuordnen / verschieben“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
