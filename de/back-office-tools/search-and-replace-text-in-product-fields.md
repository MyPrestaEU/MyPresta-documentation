---
title: "Text in Produktfeldern suchen und ersetzen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Text in Produktfeldern suchen und ersetzen' von MyPresta.eu."
sidebar:
  label: "Text in Produktfeldern suchen und ersetzen"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Search and replace text in product fields auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/search-and-replace-text-in-product-fields.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/search-and-replace-text-in-product-fields/)
>
> ---


# Text in Produktfeldern suchen und ersetzen

## 1. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul "Text in Produktfeldern suchen und ersetzen" verfügt nicht über eine traditionelle Konfigurationsseite mit Einstellungen wie Schaltern oder Eingabefeldern. Stattdessen integriert es sich direkt in die PrestaShop-Produktliste und bietet eine neue Aktion zum Durchführen von Such- und Ersetzungsoperationen.

### 2.1 Zugriff auf das Such- und Ersetzungstool

Die Funktionalität des Moduls wird direkt über Ihre PrestaShop-Produktliste aufgerufen:

1.  **Navigieren Sie zur Produktliste:**
    -   Gehen Sie in Ihrem PrestaShop Back Office zu **Katalog > Produkte**.
2.  **Produkte auswählen:**
    -   Sie können entweder ein oder mehrere spezifische Produkte auswählen, indem Sie die Kästchen daneben aktivieren, oder Sie können die Such- und Ersetzungsfunktion auf *alle* Produkte anwenden, die derzeit in der Liste angezeigt werden (z. B. wenn Sie die Liste gefiltert haben).
3.  **Zugriff auf das Menü für Massenaktionen:**
    -   Nachdem Sie Produkte ausgewählt haben, erscheint ein Dropdown-Menü "Massenaktionen" (normalerweise oben oder unten in der Produktliste).
4.  **Wählen Sie "Text in Produktfeldern suchen und ersetzen":**
    -   Klicken Sie auf das Dropdown-Menü "Massenaktionen" und wählen Sie die Option **"Text in Produktfeldern suchen und ersetzen"**.

### 2.2 Die Such- und Ersetzungsoberfläche

Sobald Sie die Aktion "Text in Produktfeldern suchen und ersetzen" auswählen, erscheint ein modales Fenster oder eine dedizierte Oberfläche. Hier definieren Sie Ihre Such- und Ersetzungsoperation.

**Verfügbare Felder für Suche und Ersetzung:**
Das Modul ermöglicht es Ihnen, verschiedene Textfelder zu bearbeiten, die mit Ihren Produkten verknüpft sind. Dazu gehören typischerweise:
-   **Produktname:** Der Haupttitel Ihres Produkts.
-   **Kurzbeschreibung:** Die kurze Zusammenfassung, die oft neben dem Produktbild angezeigt wird.
-   **Beschreibung:** Die vollständige, detaillierte Produktbeschreibung.
-   **Meta-Titel:** Der Titel, der in Browser-Tabs und Suchmaschinenergebnissen angezeigt wird.
-   **Meta-Beschreibung:** Die kurze Zusammenfassung, die unter dem Titel in den Suchmaschinenergebnissen angezeigt wird.
-   **SEO-freundliche URL:** Der SEO-freundliche Teil der Webadresse des Produkts.
-   **Tags:** Schlüsselwörter, die mit dem Produkt verknüpft sind.
-   **Merkmale:** Werte von benutzerdefinierten Produktmerkmalen (z. B. "Farbe: Rot" – Sie könnten "Rot" durch "Purpur" ersetzen).
-   **Attributwerte:** Werte für Produktattribute (z. B. "Größe: S" – Sie könnten "S" durch "Klein" ersetzen).
-   **Anpassungsfelder:** Textfelder, die Kunden zur Produktanpassung ausfüllen können.

**Wichtige Einstellungen innerhalb der Oberfläche:**

-   **Suchen nach:**
    -   **Was diese Einstellung bewirkt:** Dies ist die genaue Textphrase, die Sie in den ausgewählten Produktfeldern finden möchten.
    -   **Auswirkung der Änderung dieser Einstellung:** Das Modul sucht nach dieser präzisen Zeichenfolge. Es ist standardmäßig Groß- und Kleinschreibung-sensitiv, es sei denn, eine Option "Groß-/Kleinschreibung ignorieren" ist verfügbar (prüfen Sie die Oberfläche darauf).
    -   **Empfohlener Wert:** Geben Sie den genauen Text ein, den Sie finden möchten.
    -   **Händlerszenario / Beispiel:** Wenn Sie "alter Markenname" in "neuer Markenname" ändern möchten, würden Sie hier "alter Markenname" eingeben.

-   **Ersetzen durch:**
    -   **Was diese Einstellung bewirkt:** Dies ist die neue Textphrase, die jede gefundene Instanz des Textes "Suchen nach" ersetzt.
    -   **Auswirkung der Änderung dieser Einstellung:** Alle Vorkommen des Textes "Suchen nach" werden auf diesen neuen Text aktualisiert. Wenn leer gelassen, wird der Text "Suchen nach" gelöscht.
    -   **Empfohlener Wert:** Geben Sie den neuen Text ein, den Sie verwenden möchten.
    -   **Händlerszenario / Beispiel:** Gemäß dem obigen Beispiel würden Sie hier "neuer Markenname" eingeben.

-   **Felder zum Suchen auswählen:**
    -   **Was diese Einstellung bewirkt:** Dies ist eine Liste von Kontrollkästchen oder ein Mehrfachauswahl-Dropdown, in dem Sie auswählen, welche spezifischen Produkttextfelder (z. B. "Beschreibung", "Kurzbeschreibung", "Meta-Titel") das Modul verarbeiten soll.
    -   **Auswirkung der Änderung dieser Einstellung:** Nur die ausgewählten Felder werden gescannt und geändert. Nicht ausgewählte Felder bleiben unberührt.
    -   **Empfohlener Wert:** Wählen Sie nur die für Ihre aktuelle Aufgabe relevanten Felder aus, um unbeabsichtigte Änderungen zu vermeiden.
    -   **Händlerszenario / Beispiel:** Wenn Sie nur die Hauptproduktbeschreibung aktualisieren möchten, aktivieren Sie nur "Beschreibung". Wenn Sie einen Markennamen überall aktualisieren, könnten Sie "Produktname", "Kurzbeschreibung", "Beschreibung", "Meta-Titel" und "Meta-Beschreibung" aktivieren.

-   **Auf ausgewählte Produkte anwenden / Auf alle gefilterten Produkte anwenden:**
    -   **Was diese Einstellung bewirkt:** Dies bestätigt, ob die Operation nur auf die Produkte angewendet wird, die Sie manuell in der Liste markiert haben, oder auf alle Produkte, die derzeit in der Produktliste sichtbar sind (was eine gefilterte Untermenge sein könnte).
    -   **Auswirkung der Änderung dieser Einstellung:** Bestimmt den Umfang der Operation. Seien Sie sehr vorsichtig mit "alle gefilterten Produkte", um sicherzustellen, dass Ihre Filter korrekt angewendet werden.
    -   **Empfohlener Wert:** Überprüfen Sie immer Ihre Produktauswahl, bevor Sie fortfahren.
    -   **Händlerszenario / Beispiel:** Wenn Sie die Produktliste so gefiltert haben, dass nur Produkte einer bestimmten Kategorie angezeigt werden, und dann "Auf alle gefilterten Produkte anwenden" wählen, wirken sich die Änderungen nur auf Produkte in dieser Kategorie aus.

-   **Groß-/Kleinschreibung beachten / Groß-/Kleinschreibung ignorieren (falls verfügbar):**
    -   **Was diese Einstellung bewirkt:** Bestimmt, ob die Suche zwischen Groß- und Kleinschreibung unterscheiden soll.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Groß-/Kleinschreibung beachten:* "Apple" stimmt nicht mit "apple" überein.
        -   *Groß-/Kleinschreibung ignorieren:* "Apple" stimmt mit "apple", "APPLE", "Apple" usw. überein.
    -   **Empfohlener Wert:** Verwenden Sie Groß-/Kleinschreibung ignorieren für breite Ersetzungen (z. B. Behebung eines häufigen Tippfehlers, der in verschiedenen Schreibweisen auftreten kann). Verwenden Sie Groß-/Kleinschreibung beachten für präzise Ersetzungen, bei denen die Groß-/Kleinschreibung wichtig ist.
    -   **Händlerszenario / Beispiel:** Wenn Sie "ProduktX" durch "Produkt Y" ersetzen möchten, aber einige Beschreibungen "produktX" enthalten könnten, wird die Groß-/Kleinschreibung ignorieren beide erfassen.

-   **Vorschau / Testlauf (falls verfügbar):**
    -   **Was diese Einstellung bewirkt:** Einige erweiterte Such- und Ersetzungstools bieten einen "Vorschau"- oder "Testlauf"-Modus an, der Ihnen zeigt, welche Änderungen *gemacht würden*, ohne sie tatsächlich zu speichern.
    -   **Auswirkung der Änderung dieser Einstellung:** Ermöglicht es Ihnen, die Auswirkungen Ihrer Operation vor der Bestätigung zu überprüfen und versehentlichen Datenverlust zu verhindern.
    -   **Empfohlener Wert:** Verwenden Sie immer eine Vorschau, falls verfügbar, insbesondere bei groß angelegten Operationen.
    -   **Händlerszenario / Beispiel:** Bevor Sie "alt" durch "neu" in 1000 Produkten ersetzen, würde eine Vorschau Ihnen genau zeigen, welche Produkte und Felder betroffen wären.

### 2.3 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Produktliste (Massenaktionen) | Suchen nach | Benutzerdefiniert | Die genaue Textzeichenfolge, die gefunden werden soll. Groß-/Kleinschreibung-sensitiv, sofern nicht anders angegeben. |
| Produktliste (Massenaktionen) | Ersetzen durch | Benutzerdefiniert | Die Textzeichenfolge, durch die der Text 'Suchen nach' ersetzt werden soll. Leer löscht den Text. |
| Produktliste (Massenaktionen) | Felder zum Suchen auswählen | Benutzerdefiniert | Kontrollkästchen zur Auswahl, welche Produktfelder (Beschreibung, Name, Meta usw.) geändert werden sollen. |
| Produktliste (Massenaktionen) | Auf ausgewählte Produkte / alle gefilterten Produkte anwenden | Benutzerdefiniert | Definiert den Umfang der Operation: nur markierte Produkte oder alle aktuell gefilterten Produkte. |
| Produktliste (Massenaktionen) | Groß-/Kleinschreibung beachten / ignorieren | (Moduloberfläche prüfen) | Bestimmt, ob die Suche zwischen Groß- und Kleinschreibung unterscheidet. |
| Produktliste (Massenaktionen) | Vorschau / Testlauf | (Falls verfügbar, immer verwenden) | Zeigt potenzielle Änderungen vor der Anwendung an, um Fehler zu vermeiden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Such- und Ersetzungsfunktion ausgeführt, sehe die Änderungen aber nicht auf meiner Website.**
A: PrestaShop verwendet Caching, um Ihren Shop zu beschleunigen. Nach Änderungen im Back Office müssen Sie oft den Cache leeren, damit sie im Front Office sichtbar werden.
    -   Gehen Sie zu **Erweiterte Einstellungen > Performance**.
    -   Klicken Sie oben rechts auf "Cache leeren".
    -   Wenn Sie ein Drittanbieter-Caching-Modul oder CDN verwenden, leeren Sie auch deren Caches.

**F: Das Modul erscheint nicht im Menü "Massenaktionen" in der Produktliste.**
A:
    1.  **Installation prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** korrekt installiert und aktiviert ist.
    2.  **Berechtigungen:** Überprüfen Sie, ob Ihr Benutzerkonto die erforderlichen Berechtigungen zum Verwalten von Modulen und Produkten besitzt.
    3.  **Modulkonflikte:** Selten kann ein anderes Modul, das die Produktliste oder Massenaktionen stark modifiziert, Konflikte verursachen. Versuchen Sie, andere kürzlich installierte Module vorübergehend zu deaktivieren, um zu sehen, ob das Problem behoben wird.

**F: Ich habe versehentlich den falschen Text ersetzt oder einen Fehler gemacht. Wie kann ich das rückgängig machen?**
A: Leider führt das Modul eine direkte Datenbankaktualisierung durch, und es gibt keine integrierte "Rückgängig"-Schaltfläche. Deshalb sind Backups so wichtig.
    -   **Aus Backup wiederherstellen:** Der sicherste Weg zur Wiederherstellung ist, Ihre Datenbank aus einem Backup wiederherzustellen, das *vor* der Ausführung der Operation erstellt wurde.
    -   **Eine umgekehrte Operation ausführen:** Wenn Sie nur eine einfache Phrase geändert haben, können Sie möglicherweise eine weitere Such- und Ersetzungsoperation ausführen, um sie rückgängig zu machen (z. B. nach "neuem Text" suchen und durch "alten Text" ersetzen). Dies ist riskant und funktioniert nur für einfache, direkte Ersetzungen.

**F: Kann ich dieses Modul für mehrsprachige Shops verwenden?**
A: Ja, das Modul arbeitet mit Produktfeldern, die in PrestaShop oft mehrsprachig sind. Wenn Sie Felder wie "Beschreibung" oder "Produktname" auswählen, wendet das Modul die Such- und Ersetzungsfunktion typischerweise auf alle aktiven Sprachen für diese Felder an. Die Benutzeroberfläche sollte Ihnen ermöglichen, anzugeben, welche Sprachen angesprochen werden sollen, falls diese Option verfügbar ist.

**F: Die Such- und Ersetzungsoperation ist sehr langsam oder bricht bei einer großen Anzahl von Produkten mit einem Timeout ab.**
A:
    1.  **Serverressourcen:** Große Operationen an Tausenden von Produkten können ressourcenintensiv sein. Stellen Sie sicher, dass Ihr Server über ausreichende PHP-Speicherlimits und Ausführungszeit verfügt. Möglicherweise müssen Sie `memory_limit` und `max_execution_time` in Ihrer `php.ini` erhöhen (wenden Sie sich an Ihren Hosting-Anbieter oder Webmaster).
    2.  **In Batches verarbeiten:** Wenn möglich, filtern Sie Ihre Produktliste und führen Sie die Operation in kleineren Batches von Produkten (z. B. nach Kategorie, Marke oder ID-Bereich) aus, anstatt zu versuchen, Ihren gesamten Katalog auf einmal zu verarbeiten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul "Text in Produktfeldern suchen und ersetzen" verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht
Das Modul `snrp` ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Erweiterung der Back Office-Produktlistenfunktionalität konzentriert. Es nutzt das Hook-System von PrestaShop, um eine neue Massenaktion in den `AdminProducts`-Controller einzufügen. Die Kernlogik befindet sich in der Hauptmoduldatei und handhabt die Anzeige des Such-/Ersetzungsformulars und die Ausführung der Datenbankaktualisierungen. Es verwendet keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Admin-Controller, sondern erweitert bestehende PrestaShop-Admin-Ansichten.

### 4.2 Controller (`controllers/`)
Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität ist über Hooks in den bestehenden `AdminProducts`-Controller integriert.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert keine benutzerdefinierten Klassen in einem `classes/`-Verzeichnis. Die gesamte Kernlogik ist in der Hauptmoduldatei `snrp/index.php` enthalten. Das Modul interagiert direkt mit den `Product`- und `ProductLang`-`ObjectModel`s von PrestaShop und potenziell mit `FeatureValue`-, `AttributeGroup`- und `Tag`-Daten, indem es SQL-Updates basierend auf der Benutzereingabe durchführt.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`snrp/views/js/snrp.js`**
    *   **Geltungsbereich:** Back-Office (insbesondere die `AdminProducts`-Listenansicht).
    *   **Verantwortlichkeit:** Dieses Skript ist für das clientseitige Verhalten des Such- und Ersetzungstools verantwortlich.
        *   Es bindet wahrscheinlich einen Event-Listener an die Option "Text in Produktfeldern suchen und ersetzen" innerhalb des Dropdown-Menüs "Massenaktionen".
        *   Bei Auswahl löst es die Anzeige des modalen Fensters oder Formulars aus, in dem der Benutzer den Suchbegriff, den Ersetzungsbegriff und die Zielfelder eingibt.
        *   Es verarbeitet die AJAX-Anfrage an die `getContent()`-Methode des Moduls (oder einen dedizierten AJAX-Endpunkt, falls dieser in `index.php` implementiert wäre), um die Such- und Ersetzungsparameter zu übermitteln.
        *   Es verwaltet das UI-Feedback während und nach der Operation (z. B. Lade-Spinner, Erfolgs-/Fehlermeldungen).
        *   Es könnte Validierungslogik für die Eingabefelder vor der Übermittlung enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`snrp/views/css/snrp.css`**
    *   **Geltungsbereich:** Back-Office (insbesondere die `AdminProducts`-Listenansicht).
    *   **Verantwortlichkeit:** Dieses Stylesheet bietet die visuelle Gestaltung für die Such- und Ersetzungsoberfläche.
        *   Es definiert das Aussehen des modalen Fensters (Größe, Positionierung, Hintergrundüberlagerung).
        *   Es gestaltet die Eingabefelder, Schaltflächen, Kontrollkästchen und alle anderen UI-Elemente innerhalb des Such- und Ersetzungsformulars.
        *   Es stellt sicher, dass die Oberfläche visuell in das PrestaShop Back Office-Theme integriert ist.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler können den generierten HTML-Code des Modals überprüfen, um spezifische Klassennamen (z. B. `.snrp-modal`, `.snrp-form-group`, `.snrp-button`) zu identifizieren und deren Erscheinungsbild in ihren benutzerdefinierten Admin-Themes oder über `override/css/admin.css` anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Die Modulbeschreibung weist darauf hin, dass keine `.tpl`-Dateien in `views/templates/` vorhanden sind. Dies deutet darauf hin, dass das Konfigurationsformular des Moduls und die Such-/Ersetzungs-Modalschnittstelle wahrscheinlich direkt innerhalb der `getContent()`-Methode von `snrp/index.php` unter Verwendung von reinem HTML und PHP oder durch dynamische Generierung der Formularelemente über JavaScript gerendert werden.

Wenn ein Modal verwendet wird, ist es möglich, dass die HTML-Struktur direkt von `snrp.js` in das DOM eingefügt oder als Teil der `getContent()`-Antwort gerendert wird.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
    *   Es modifiziert direkt bestehende PrestaShop-Tabellen, hauptsächlich:
        *   `ps_product_lang`: Für Produktnamen, Kurzbeschreibungen, Beschreibungen, Meta-Titel, Meta-Beschreibungen und SEO-freundliche URLs (sprachspezifische Felder).
        *   `ps_tag`: Für Produkt-Tags.
        *   Potenziell `ps_feature_product` und `ps_product_attribute_lang`, wenn Merkmalswerte und Attributwerte angesprochen werden.
    *   Konfigurationseinstellungen (falls vorhanden) würden typischerweise in `ps_configuration` gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich des Back Office gerendert. | Wird verwendet, um `snrp.js` und `snrp.css` auf relevanten Admin-Seiten (z. B. `AdminProducts`) einzubinden. |
| `displayAdminProductsExtra` | Rendert zusätzlichen Inhalt auf der `AdminProducts`-Listenseite. | Dieser Hook wird wahrscheinlich verwendet, um die HTML-Struktur für die Option "Text in Produktfeldern suchen und ersetzen" in das Dropdown-Menü "Massenaktionen" einzufügen oder einen Button hinzuzufügen, der das Modal auslöst. |
| `actionProductUpdate` / `actionObjectProductUpdateAfter` | Wird nach der Aktualisierung eines Produkts ausgeführt. | Obwohl nicht explizit angegeben, könnte das Modul diese Hooks nutzen, um zusätzliche Aktionen oder Protokollierungen nach einer erfolgreichen Such- und Ersetzungsoperation durchzuführen, obwohl direkte SQL-Updates für die Performance wahrscheinlicher sind. |
| `actionAdminProductsListingResultsModifier` | Modifiziert die Ergebnisse der Produktliste. | Weniger wahrscheinlich für dieses Modul, könnte aber verwendet werden, um eine Spalte hinzuzufügen oder angezeigte Daten zu ändern, bevor die Such-/Ersetzungsaktion ausgelöst wird. |

Die Kernfunktionalität der Durchführung der Such- und Ersetzungslogik wird innerhalb der `getContent()`-Methode des Moduls (oder einer dedizierten AJAX-Methode innerhalb von `index.php`) behandelt, wenn das Formular übermittelt wird, wobei die ausgewählten Produkt-IDs und Felder verarbeitet werden.

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Text in Produktfeldern suchen und ersetzen" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
