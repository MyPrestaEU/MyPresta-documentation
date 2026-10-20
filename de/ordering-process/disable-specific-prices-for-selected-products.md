---
title: "Spezifische Preise für ausgewählte Produkte deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Spezifische Preise für ausgewählte Produkte deaktivieren“ von MyPresta.eu."
sidebar:
  label: "Spezifische Preise für ausgewählte Produkte deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable specific prices for selected products auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/disable-specific-prices-for-selected-products/)
>
> ---


# Spezifische Preise für ausgewählte Produkte deaktivieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf die Einstellungen zuzugreifen. Dies ist der Haupt- und einzige Konfigurationsbildschirm für dieses Modul.

#### **Allgemeine Einstellungen**

- **Spezifische Preise für ausgewählte Produkte deaktivieren**
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul verhindert aktiv, dass spezifische Preise auf die unten ausgewählten Produkte und Kategorien angewendet werden.
    - *Wenn deaktiviert (NEIN):* Das Modul ist inaktiv. Alle spezifischen Preise und Katalogpreisregeln gelten für alle Produkte wie gewohnt, unabhängig von Ihren Auswahlen in den Feldern „Kategorien“ oder „Spezifische Produkte“.
  - **Empfohlener Wert:** **JA**, wenn Sie die Funktionalität des Moduls nutzen möchten, um Produkte von Rabatten auszuschließen. **NEIN**, wenn Sie es vorübergehend deaktivieren möchten, ohne Ihre gespeicherten Konfigurationen zu verlieren.
  - **Händlerszenario / Beispiel:** Sie haben gerade eine neue Linie von Premium-Produkten eingeführt und möchten sicherstellen, dass diese niemals rabattiert werden. Sie aktivieren diese Einstellung und fügen diese Produkte dann der Ausschlussliste hinzu.

#### **Ausschlusskriterien**

- **Kategorien**

  - **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, ganze Produktkategorien auszuwählen, deren Produkte von spezifischen Preisen ausgeschlossen werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Kategorien ausgewählt sind:* Alle Produkte, die zu den ausgewählten Kategorien gehören (einschließlich Unterkategorien, abhängig von der PrestaShop-Kategorienstruktur und wie spezifische Preise angewendet werden), erhalten keine spezifischen Preise.
    - *Wenn keine Kategorien ausgewählt sind:* Nur Produkte, die explizit im Feld „Spezifische Produkte“ aufgeführt sind, sind betroffen.
  - **Empfohlener Wert:** Wählen Sie Kategorien aus, die Produkte enthalten, die Sie konsequent vor Rabatten schützen möchten, wie z. B. „Neuheiten“, „Luxusgüter“ oder „Ausverkauf (wenn Sie nur manuelle Rabatte anwenden möchten)“.
  - **Händlerszenario / Beispiel:** Sie haben eine Kategorie „Premium-Marken“. Durch die Auswahl hier werden alle Produkte innerhalb dieser Kategorie automatisch von spezifischen Preisberechnungen ausgeschlossen, wodurch Sie sich das individuelle Auflisten jedes Produkts sparen.
- **Spezifische Produkte**

  - **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, einzelne Produkte zu suchen und auszuwählen, die von spezifischen Preisen ausgeschlossen werden sollen. Es verwendet ein Autocomplete-Suchwerkzeug, um Ihnen zu helfen, Produkte schnell zu finden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Produkte ausgewählt sind:* Die ausgewählten einzelnen Produkte erhalten keine spezifischen Preise, unabhängig von ihrer Kategorie.
    - *Wenn keine Produkte ausgewählt sind:* Nur Produkte innerhalb der ausgewählten „Kategorien“ sind betroffen.
  - **Empfohlener Wert:** Verwenden Sie dies für einzelne Artikel, die nicht in einen breiteren Kategorieausschluss passen, oder für bestimmte Bestseller, die Sie zum vollen Preis halten möchten.
  - **Händlerszenario / Beispiel:** Sie haben ein paar stark nachgefragte Gadgets, die sich immer gut zum vollen Preis verkaufen. Sie suchen nach „iPhone 15“ und „Samsung Galaxy S24“ und fügen sie dieser Liste hinzu, um sicherzustellen, dass sie niemals durch spezifische Preise rabattiert werden.

#### **Ihre Änderungen speichern**

Nachdem Sie Änderungen an den Einstellungen vorgenommen haben, denken Sie daran, unten auf der Konfigurationsseite auf die Schaltfläche **„Speichern“** zu klicken, um sie anzuwenden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Spezifische Preise für ausgewählte Produkte deaktivieren | JA | Hauptschalter zum Aktivieren/Deaktivieren der Modulfunktionalität. JA bedeutet, dass Ausschlüsse aktiv sind. |
| Modulkonfigurationsseite | Kategorien | Keine ausgewählt | Wählen Sie Kategorien aus, deren Produkte von spezifischen Preisen ausgeschlossen werden. |
| Modulkonfigurationsseite | Spezifische Produkte | Keine ausgewählt | Suchen und wählen Sie einzelne Produkte aus, die von spezifischen Preisen ausgeschlossen werden sollen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul konfiguriert, aber spezifische Preise werden immer noch auf meine ausgeschlossenen Produkte angewendet. Was ist falsch?**
A1:

- **Modulstatus prüfen:** Stellen Sie zunächst sicher, dass die Einstellung „Spezifische Preise für ausgewählte Produkte deaktivieren“ auf der Konfigurationsseite des Moduls auf **JA (Aktiviert)** steht.
- **Ausschlüsse überprüfen:** Überprüfen Sie nochmals, ob die spezifischen Produkte oder Kategorien, die Sie ausschließen möchten, in den Moduleinstellungen korrekt ausgewählt sind. Verwenden Sie die Suchfunktion sorgfältig für Produkte.
- **Cache leeren:** PrestaShop speichert oft Preisinformationen im Cache. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie oben rechts auf „Cache leeren“. Leeren Sie auch den Cache Ihres Browsers.
- **Priorität spezifischer Preise:** Stellen Sie sicher, dass die spezifische Preisregel, die Sie testen, das Modul nicht irgendwie überschreibt. Dieses Modul überschreibt die Kernberechnung spezifischer Preise von PrestaShop. Wenn Sie andere Module haben, die ebenfalls die Preisgestaltung ändern, könnte es zu einem Konflikt kommen. Versuchen Sie, andere preisbezogene Module vorübergehend zu deaktivieren, um die Ursache zu finden.

**F2: Wirkt sich dieses Modul auf meine Warenkorbregeln (Gutscheine) aus?**
A2: Ja, indirekt. Dieses Modul verhindert, dass spezifische Preise auf ausgewählte Produkte angewendet werden. Wenn eine Warenkorbregel (Gutschein) einen Rabatt bietet, der auf dem spezifischen Preismechanismus von PrestaShop *basiert* oder mit ihm interagiert (z. B. ein prozentualer Rabatt, der basierend auf dem aktuellen Preis des Produkts *nach* spezifischen Preisen berechnet wird), dann erhalten die ausgeschlossenen Produkte diese spezifische Preisreduzierung nicht, bevor der Gutschein angewendet wird. Der Gutschein wird dann auf den Grundpreis des Produkts (oder seinen Preis nach anderen nicht-spezifischen Preisrabatten) angewendet.

**F3: Funktioniert dieses Modul mit Multi-Store-Setups?**
A3: Die Konfiguration des Moduls ist typischerweise global oder an den Kontext gebunden, in dem Sie es konfigurieren. Wenn Sie ein Multi-Store-Setup haben, testen Sie gründlich, um sicherzustellen, dass die Ausschlüsse wie erwartet in allen relevanten Stores angewendet werden. Der `override`-Mechanismus von PrestaShop gilt normalerweise global, aber spezifische Preisregeln selbst können Store-spezifisch sein.

**F4: Ich habe ein neues Produkt zu einer ausgeschlossenen Kategorie hinzugefügt, aber es erhält immer noch spezifische Preise. Warum?**
A4:

- **Cache:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Performance**), nachdem Sie Änderungen an Kategorien oder Produkten vorgenommen haben, insbesondere wenn Sie neue Artikel hinzufügen oder sie zwischen Kategorien verschieben.
- **Kategorienstruktur:** Stellen Sie sicher, dass die spezifische Preisregel nicht auf eine Weise angewendet wird, die den Kategorieausschluss umgeht (z. B. eine Regel für „alle Produkte“, die die Kategoriehierarchie nicht berücksichtigt). Das Modul sollte die spezifische Preisberechnung unabhängig davon abfangen, aber der Cache ist oft der Übeltäter.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Spezifische Preise für ausgewählte Produkte deaktivieren“ nutzt das PrestaShop-Override-System, um die Kernlogik der Preisgestaltung zu modifizieren. Insbesondere überschreibt es die Klassen `Product` und `SpecificPrice`, um seine Ausschlusslogik direkt in den Preisberechnungsprozess zu injizieren. Dies stellt sicher, dass, wenn PrestaShop versucht, den Preis eines Produkts zu bestimmen, das Modul zuerst prüft, ob das Produkt oder seine Kategorie auf der Ausschlussliste steht, und falls ja, verhindert es die Anwendung spezifischer Preise. Das Modul verwendet eine Standard-PrestaShop-Modulstruktur mit einer Hauptmoduldatei, Overrides und `views` für Assets und Templates.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Seine Konfiguration wird direkt innerhalb der Methode `getContent()` der Hauptmoduldatei gehandhabt, und seine Kernfunktionalität wird über Klassen-Overrides implementiert.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`exsp/override/classes/index.php`**:

  - Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um das Auflisten von Verzeichnissen zu verhindern. Sie hat keine funktionale Auswirkung auf die Logik des Moduls.
- **`exsp/override/classes/Product.php`**:

  - **Klassenname & Elternklasse**: `Product` (überschreibt die Kernklasse `Product` von PrestaShop).
  - **Verantwortlichkeit**: Dieser Override ist der primäre Mechanismus zum Abfangen von Produktpreisberechnungen. Er modifiziert die Methode `getPrice()` (oder verwandte Methoden), um zu prüfen, ob das aktuelle Produkt (oder seine Kategorie) für den Ausschluss konfiguriert ist. Falls ja, wird die spezifische Preiskomponente der Berechnung umgangen, wodurch sichergestellt wird, dass der Grundpreis des Produkts ohne spezifische Preisreduzierungen zurückgegeben wird. Dies ist entscheidend, um die Anwendung spezifischer Preise auf Produktebene zu verhindern.
  - **Wichtige öffentliche Methoden**: Die überschriebene Methode `getPrice()` (oder ähnliche Preisberechnungsmethoden innerhalb der Klasse `Product`) enthält die Logik zur Überprüfung der Konfigurationswerte `exsp_categories` und `exsp_products`.
- **`exsp/override/classes/SpecificPrice.php`**:

  - **Klassenname & Elternklasse**: `SpecificPrice` (überschreibt die Kernklasse `SpecificPrice` von PrestaShop).
  - **Verantwortlichkeit**: Dieser Override beeinflusst direkt, wie spezifische Preise abgerufen und angewendet werden. Er modifiziert Methoden wie `getSpecificPrice()` oder `getSpecificPrices()`, um spezifische Preisregeln für Produkte, die auf der Ausschlussliste stehen, herauszufiltern oder zu ignorieren. Dies dient als sekundäre Verteidigungsebene, die sicherstellt, dass selbst wenn eine spezifische Preisregel existiert, sie für ausgeschlossene Produkte nicht berücksichtigt wird.
  - **Wichtige öffentliche Methoden**: Überschriebene Methoden, die sich auf das Abrufen oder Anwenden spezifischer Preise beziehen, werden Überprüfungen gegen die Ausschlusslisten des Moduls enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- **`exsp/lib/searchTool/views/js/autocomplete.js`**:

  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Beschreibung**: Dieses Skript bietet die Autocomplete-Funktionalität für das Eingabefeld „Spezifische Produkte“ auf der Konfigurationsseite des Moduls. Es verwendet wahrscheinlich AJAX, um die PrestaShop-Produktdatenbank abzufragen, während der Benutzer tippt, und schlägt passende Produktnamen vor. Es handhabt die Anzeige von Vorschlägen und die Auswahl von Produkten, die zur Ausschlussliste hinzugefügt werden sollen.
  - **Event-Listener**: Keyup-Ereignisse im Produktsuchfeld, Klick-Ereignisse auf Autocomplete-Vorschläge.
  - **DOM-Manipulation**: Erstellt und aktualisiert dynamisch die Vorschlagsliste, fügt ausgewählte Produkte einem versteckten Eingabefeld oder Anzeigebereich hinzu.
- **`exsp/views/js/exsp.js`**:

  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Beschreibung**: Dies ist die Haupt-JavaScript-Datei für die Konfigurationsoberfläche des Moduls. Sie handhabt die Initialisierung des Autocomplete-Suchwerkzeugs, verwaltet die Anzeige und Entfernung ausgewählter Produkte/Kategorien und führt möglicherweise andere UI-Interaktionen durch, die spezifisch für die Einstellungen des Moduls sind.
  - **Event-Listener**: Klick-Ereignisse zum Entfernen ausgewählter Produkte/Kategorien, möglicherweise Änderungsereignisse für den Haupt-Ein-/Ausschalter.
  - **DOM-Manipulation**: Verwaltet die visuelle Darstellung ausgewählter Kategorien und Produkte, aktualisiert versteckte Eingabefelder, die die Konfigurationswerte speichern.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`exsp/lib/searchTool/views/css/autocomplete.css`**:
  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Beschreibung**: Dieses Stylesheet bietet die visuelle Gestaltung für das Autocomplete-Suchfeld und seine Vorschlagsliste. Es definiert das Aussehen des Suchfelds, der Dropdown-Vorschläge und möglicherweise Hover-/Active-Zustände für eine bessere Benutzererfahrung.
  - **Haupt-UI-Komponenten**: `.autocomplete-container`, `.autocomplete-suggestions`, `.autocomplete-suggestion`.
  - **Wichtige CSS-Klassenselektoren**: `.exsp-product-search-input`, `.exsp-selected-item`, `.exsp-remove-item`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`exsp/lib/searchTool/views/scripts.tpl`**:

  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Beschreibung**: Dieses Template enthält wahrscheinlich die notwendigen JavaScript- und CSS-Dateien für das Autocomplete-Suchwerkzeug oder es könnte Inline-JavaScript zur Initialisierung des Autocomplete-Widgets mit spezifischen Parametern (z. B. AJAX-URL für die Produktsuche) enthalten.
  - **Gerendert in**: `ActionAdminControllerSetMedia`-Hook oder direkt innerhalb von `getContent()`.
- **`exsp/views/script.tpl`**:

  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Beschreibung**: Dieses Template ist für das Rendern des Hauptkonfigurationsformulars des Moduls verantwortlich. Es enthält die HTML-Struktur für den Ein-/Ausschalter, das Kategorieauswahlfeld und das Produktsuchfeld mit seiner zugehörigen Anzeige für ausgewählte Produkte. Es enthält wahrscheinlich auch die Skripte `exsp.js` und `autocomplete.js`.
  - **Gerendert in**: `getContent()`-Methode von `exsp.php`.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (aktivierter Status, ausgeschlossene Kategorien, ausgeschlossene Produkte) in der PrestaShop-Tabelle `ps_configuration`.
    - `exsp_categories`: Speichert ein serialisiertes Array oder eine kommagetrennte Liste von Kategorie-IDs, die ausgeschlossen werden sollen.
    - `exsp_products`: Speichert ein serialisiertes Array oder eine kommagetrennte Liste von Produkt-IDs, die ausgeschlossen werden sollen.
    - `exsp_enabled`: Speichert den aktivierten/deaktivierten Status des Moduls (z. B. `1` für aktiviert, `0` für deaktiviert).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller geladen wird, bevor sein Inhalt gerendert wird. | Wird verwendet, um die JavaScript- und CSS-Assets des Moduls (z. B. für das Autocomplete-Suchwerkzeug) auf der Konfigurationsseite des Moduls zu registrieren und einzubinden. |
| (Implizite Hooks über Overrides) | Während der Produktpreisberechnung (`Product::getPrice()`) und des Abrufs spezifischer Preise (`SpecificPrice::getSpecificPrices()`). | Die Kernfunktionalität des Moduls wird durch das Überschreiben der PrestaShop-Klassen `Product` und `SpecificPrice` implementiert. Dies bedeutet, dass die Logik des Moduls immer dann ausgeführt wird, wenn diese Kernmethoden aufgerufen werden, wodurch effektiv in den Preisberechnungsprozess „eingehakt“ wird, ohne explizit einen `display`- oder `action`-Hook zu registrieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Spezifische Preise für ausgewählte Produkte deaktivieren“ besuchen Sie bitte Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
