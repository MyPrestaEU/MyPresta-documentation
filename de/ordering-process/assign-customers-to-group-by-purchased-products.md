---
title: "Kunden Gruppen nach gekauften Produkten zuweisen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kunden Gruppen nach gekauften Produkten zuweisen“ von MyPresta.eu."
sidebar:
  label: "Kunden Gruppen nach gekauften Produkten zuweisen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Assign customers to group by purchased products auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/assign-customers-to-group-by-purchased-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/assign-customers-to-group-by-purchased-products/)
>
> ---


# Kunden Gruppen nach gekauften Produkten zuweisen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Kerneinstellungen des Moduls verwalten.

-   **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise allgemeine Einstellungen für das Modul, wie z. B. das Aktivieren/Deaktivieren seiner Kernfunktionalität.
-   **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul überwacht aktiv Kundenkäufe und wendet Ihre definierten Gruppenzuweisungsregeln an.
    - *Wenn deaktiviert:* Das Modul stoppt die Verarbeitung neuer Bestellungen für Gruppenzuweisungen. Bestehende Zuweisungen bleiben erhalten, aber es werden keine neuen automatisch vorgenommen.
-   **Empfohlener Wert:** **JA** (Aktiviert), damit das Modul funktioniert.
-   **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, möchten Sie es sofort nach der Konfiguration aktivieren. Wenn Sie automatische Zuweisungen vorübergehend stoppen müssen (z. B. während einer größeren Shop-Migration), können Sie es hier deaktivieren.

### 2.2 Dedizierter Admin-Bildschirm: Produkt-Gruppen-Zuordnungen

Dies ist der zentrale Verwaltungsbereich, in dem Sie die Regeln für die Zuweisung von Kunden zu Gruppen basierend auf ihren Käufen definieren.

**Bildschirmname & Menüpfad:**
Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Kunden Gruppen nach gekauften Produkten zuweisen“ finden und auf „Konfigurieren“ klicken. Innerhalb der Modulkonfiguration finden Sie einen Abschnitt oder Tab, der „Produkt-Gruppen-Zuordnungen“ oder Ähnliches gewidmet ist.

**Verfügbare Aktionen & Einstellungen:**
Auf diesem Bildschirm finden Sie typischerweise eine Liste der bestehenden Zuweisungsregeln. Sie haben Optionen zum:

-   **Neue Regel hinzufügen:** Eine neue Bedingung für die Gruppenzuweisung erstellen.
-   **Regel bearbeiten:** Eine bestehende Regel ändern.
-   **Regel löschen:** Eine Regel entfernen.

Beim Hinzufügen oder Bearbeiten einer Regel konfigurieren Sie Folgendes:

1.  **Kundengruppe auswählen:**

    -   **Was diese Einstellung bewirkt:** Dies ist die Zielgruppe, der Kunden zugewiesen werden, wenn sie die Bedingungen der Regel erfüllen.
    -   **Auswirkung der Änderung dieser Einstellung:** Wenn der Kauf eines Kunden diese Regel auslöst, wird er in die ausgewählte Kundengruppe verschoben (oder hinzugefügt).
    -   **Empfohlener Wert:** Wählen Sie die spezifische Kundengruppe, die Sie segmentieren möchten (z. B. „Großhandelskunden“, „VIP-Käufer“, „Elektronik-Enthusiasten“).
    -   **Händlerszenario / Beispiel:** Sie möchten eine Regel erstellen, um Kunden Ihrer Gruppe „VIP-Käufer“ zuzuweisen.
2.  **Produkte / Kategorien auswählen:**

    -   **Was diese Einstellung bewirkt:** Hier definieren Sie, *welche* Produkte oder Produktkategorien beim Kauf die Gruppenzuweisung auslösen. Sie können normalerweise mehrere Produkte oder Kategorien auswählen. Das Modul enthält wahrscheinlich ein Suchwerkzeug, um Produkte leicht zu finden.
    -   **Auswirkung der Änderung dieser Einstellung:** Nur Käufe, die die angegebenen Produkte enthalten oder aus den angegebenen Kategorien stammen, aktivieren diese Regel.
    -   **Empfohlener Wert:** Seien Sie präzise. Verwenden Sie das Suchwerkzeug, um alle relevanten Produkte oder Kategorien auszuwählen.
    -   **Händlerszenario / Beispiel:** Für die Gruppe „VIP-Käufer“ könnten Sie hochwertige Produkte wie „Luxusuhr X“ und „Diamantkette Y“ auswählen. Für „Elektronik-Enthusiasten“ könnten Sie die gesamte Kategorie „Elektronik“ auswählen.
3.  **Mindestmenge (Optional):**

    -   **Was diese Einstellung bewirkt:** Wenn angegeben, muss der Kunde mindestens diese Menge der ausgewählten Produkte/Kategorien in einer einzigen Bestellung kaufen, um der Gruppe zugewiesen zu werden.
    -   **Auswirkung der Änderung dieser Einstellung:** Wenn ein Kunde weniger als die Mindestmenge kauft, wird die Regel nicht angewendet, selbst wenn er die angegebenen Produkte gekauft hat.
    -   **Empfohlener Wert:** Leer lassen für beliebige Menge, oder einen Wert wie „1“ für mindestens einen Artikel oder „5“ für Großabnehmer festlegen.
    -   **Händlerszenario / Beispiel:** Um ein „Großhandelskunde“ zu sein, müssen sie mindestens 10 Einheiten eines Produkts aus der Kategorie „Massenware“ kaufen.
4.  **Bestellstatus zur Auslösung der Zuweisung:**

    -   **Was diese Einstellung bewirkt:** Dies bestimmt, bei welchem Bestellstatus die Kundengruppenzuweisung erfolgen soll. Zum Beispiel möchten Sie Gruppen möglicherweise erst zuweisen, wenn eine Bestellung „Zahlung akzeptiert“ oder „Geliefert“ ist.
    -   **Auswirkung der Änderung dieser Einstellung:** Das Modul verarbeitet die Gruppenzuweisung nur, wenn eine Bestellung den ausgewählten Status erreicht. Wenn eine Bestellung diesen Status nie erreicht (z. B. „Storniert“), erfolgt die Zuweisung nicht.
    -   **Empfohlener Wert:** „Zahlung akzeptiert“ oder „Geliefert“ sind im Allgemeinen sichere Optionen, um sicherzustellen, dass der Kauf bestätigt ist.
    -   **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Kunden tatsächlich bezahlt haben, bevor sie einer speziellen Gruppe hinzugefügt werden, daher wählen Sie „Zahlung akzeptiert“.
5.  **Gruppe zuweisen (Hinzufügen oder Ersetzen):**

    -   **Was diese Einstellung bewirkt:** Diese entscheidende Option bestimmt, wie die Gruppenmitgliedschaft des Kunden gehandhabt wird.
        -   **Zur Gruppe hinzufügen:** Der Kunde wird der ausgewählten Gruppe *zusätzlich* zu allen Gruppen hinzugefügt, in denen er sich bereits befindet.
        -   **Aktuelle Gruppe ersetzen:** Die *primäre* Gruppe des Kunden wird in die ausgewählte Gruppe geändert, wodurch er möglicherweise aus seiner vorherigen primären Gruppe entfernt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Zur Gruppe hinzufügen:* Kunden können mehreren Gruppen angehören, was eine flexible Segmentierung ermöglicht.
        -   *Aktuelle Gruppe ersetzen:* Kunden gehören nur einer primären Gruppe an, was die Verwaltung vereinfacht, aber möglicherweise andere Gruppenzugehörigkeiten verliert.
    -   **Empfohlener Wert:** „Zur Gruppe hinzufügen“ bietet in den meisten Szenarien mehr Flexibilität. Verwenden Sie „Aktuelle Gruppe ersetzen“ mit Vorsicht, insbesondere wenn andere Module auf primäre Gruppenzuweisungen angewiesen sind.
    -   **Händlerszenario / Beispiel:**
        -   *Zur Gruppe hinzufügen:* Ein Kunde, der ein bestimmtes Produkt kauft, wird zu „VIP-Käufern“ hinzugefügt, bleibt aber in „Allgemeine Kunden“.
        -   *Aktuelle Gruppe ersetzen:* Ein Kunde, der ein bestimmtes Produkt kauft, wird von „Allgemeine Kunden“ zu „Großhandelskunden“ verschoben und wird deren neue primäre Gruppe.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1.  **Planen Sie Ihre Kundensegmente:** Bevor Sie Regeln erstellen, entscheiden Sie, welche Kundengruppen Sie haben möchten und welche Kriterien diese definieren.
2.  **Erstellen Sie Ihre Kundengruppen:** Gehen Sie im PrestaShop Back Office zu **Kunden > Gruppen** und erstellen Sie alle neuen Gruppen, die Sie benötigen (z. B. „Großhandel“, „VIP“, „Käufer von Produkt X“).
3.  **Regeln definieren:** Erstellen Sie für jede Kundengruppe eine neue Zuordnungsregel in der Modulkonfiguration.
4.  **Gründlich testen:** Führen Sie einen Testkauf mit einem Testkundenkonto durch, um sicherzustellen, dass die Gruppenzuweisung wie erwartet erfolgt.
5.  **Regelmäßig überprüfen:** Überprüfen Sie regelmäßig Ihre Regeln und Kundengruppenzuweisungen, um sicherzustellen, dass sie weiterhin Ihren Geschäftszielen entsprechen.

### 2.3 Konfigurations-Kurzreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktiviert/deaktiviert | Aktiviert | Steuert, ob das Modul Bestellungen aktiv für Gruppenzuweisungen verarbeitet. |
| **Produkt-Gruppen-Zuordnungen** | Ziel-Kundengruppe | N/A (Benutzerdefiniert) | Die Gruppe, der Kunden zugewiesen werden. |
|  | Produkte / Kategorien | N/A (Benutzerdefiniert) | Die spezifischen Produkte oder Kategorien, deren Kauf die Zuweisung auslöst. |
|  | Mindestmenge | Leer (Beliebige Menge) | Mindestanzahl der Artikel aus den Produkten/Kategorien der Regel, die in einer Bestellung erforderlich sind. |
|  | Bestellstatus zur Auslösung | Zahlung akzeptiert / Geliefert | Der Bestellstatus, bei dem die Gruppenzuweisung verarbeitet wird. |
|  | Zuweisungstyp | Zur Gruppe hinzufügen | Bestimmt, ob der Kunde der Gruppe hinzugefügt wird oder ob seine primäre Gruppe ersetzt wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden werden nach dem Kauf nicht den Gruppen zugewiesen. Was ist falsch?**
A:

1.  **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** und auf seiner Hauptkonfigurationsseite aktiviert ist.
2.  **Bestellstatus überprüfen:** Überprüfen Sie die Einstellung „Bestellstatus zur Auslösung der Zuweisung“ Ihrer Regel. Hat die Bestellung des Kunden tatsächlich diesen spezifischen Status erreicht (z. B. „Zahlung akzeptiert“, „Geliefert“)? Bestellungen im Status „Ausstehend“ oder „Storniert“ lösen die Zuweisung nicht aus, wenn Ihre Regel einen späteren Status angibt.
3.  **Regelbedingungen überprüfen:** Überprüfen Sie die in Ihrer Regel ausgewählten Produkte/Kategorien. Sind sie genau das, was der Kunde gekauft hat? Ist die „Mindestmenge“ erfüllt?
4.  **Cache leeren:** Manchmal kann der PrestaShop-Cache Probleme verursachen. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
5.  **Auf Konflikte prüfen:** Deaktivieren Sie vorübergehend andere Module, die Kundengruppen oder die Bestellverarbeitung ändern, um festzustellen, ob ein Konflikt vorliegt.

**F: Kann ein Kunde in mehreren Gruppen sein?**
A: Ja, wenn Sie die Option „Zur Gruppe hinzufügen“ beim Erstellen Ihrer Regeln verwenden. Dies ermöglicht es Kunden, Gruppenmitgliedschaften basierend auf verschiedenen Kaufverhaltensweisen zu sammeln. Wenn Sie „Aktuelle Gruppe ersetzen“ verwenden, gehören sie nur einer primären Gruppe an.

**F: Was passiert, wenn ein Kunde Produkte kauft, die mehrere Regeln auslösen?**
A: Das Modul verarbeitet alle anwendbaren Regeln. Wenn Regeln „Zur Gruppe hinzufügen“ verwenden, wird der Kunde allen relevanten Gruppen hinzugefügt. Wenn Regeln „Aktuelle Gruppe ersetzen“ verwenden, bestimmt die zuletzt verarbeitete Regel (basierend auf der internen Modullogik oder der Reihenfolge der Regelerstellung) möglicherweise die endgültige primäre Gruppe, aber es ist Best Practice, widersprüchliche „Ersetzen“-Regeln zu vermeiden.

**F: Ich habe eine Regel geändert, aber alte Bestellungen werden nicht aktualisiert. Warum?**
A: Das Modul verarbeitet Gruppenzuweisungen typischerweise, wenn eine Bestellung den angegebenen Status *ändert*. Es wendet Regeln nicht rückwirkend auf bereits abgeschlossene und verarbeitete Bestellungen an. Wenn Sie frühere Kunden neu bewerten müssen, müssen Sie sie möglicherweise manuell zuweisen oder ein benutzerdefiniertes Skript (für Entwickler) in Betracht ziehen, um die Logik erneut auszuführen.

**F: Wie übersetze ich den Text des Moduls?**
A: Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Kunden Gruppen nach gekauften Produkten zuweisen“ aus der Modulliste. Sie können dann alle sichtbaren Zeichenketten übersetzen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Kunden Gruppen nach gekauften Produkten zuweisen“ (`pgroup`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich das MVC-Muster für seine Back-Office-Komponenten nutzt. Es integriert sich in die Kernfunktionalität von PrestaShop über Hooks, insbesondere durch die Reaktion auf Bestellstatusänderungen, um seine Logik zur Kundengruppenzuweisung auszulösen. Das Modul führt keine Front-Office-Controller ein, da seine Funktionalität vollständig Backend-gesteuert ist. Es verwendet einen benutzerdefinierten `AdminController` zur Verwaltung von Produkt-zu-Gruppe-Zuordnungsregeln und stützt sich auf PrestaShops `ObjectModel` für die Datenpersistenz.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**: Keine. Die gesamte Logik wird im Back Office oder über Hooks verarbeitet.
-   **Back-Office-Admin-Controller**:

    -   `pgroup/controllers/admin/AdminProductGroupsAssociationsController.php`
        -   **Klassenname:** `AdminProductGroupsAssociationsController` (erweitert `ModuleAdminController`)
        -   **Verantwortlichkeit:** Dies ist der primäre Controller zur Verwaltung der Produkt-zu-Kundengruppen-Zuordnungsregeln. Er handhabt die Anzeige der Liste der Regeln (mithilfe von `HelperList`) und die Erstellung/Bearbeitung einzelner Regeln (mithilfe von `HelperForm`). Er interagiert mit dem `PgAssign` `ObjectModel`, um die Zuordnungsdaten zu speichern und abzurufen. Dieser Controller ist für das Rendern des Rasters der Zuordnungen und des Formulars zum Hinzufügen/Bearbeiten verantwortlich.
    -   `pgroup/controllers/admin/index.php`
        -   **Klassenname:** Keine Klasse, typischerweise eine leere Datei oder eine einfache Weiterleitung, um den direkten Verzeichniszugriff zu verhindern. In PrestaShop dienen `index.php`-Dateien in Controller-Verzeichnissen normalerweise als Sicherheitsplatzhalter.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das primäre Datenmodell für die Produkt-Gruppen-Zuordnungen wahrscheinlich direkt in der Hauptmoduldatei (`pgroup/index.php`) als `ObjectModel` definiert oder über direkte Datenbankabfragen gehandhabt wird.

-   **Wahrscheinliches Modell (innerhalb von `pgroup/index.php`):**
    -   **Klassenname:** `PgAssign` (oder ähnlich, erweitert `ObjectModel`)
    -   **Datenbanktabelle:** `ps_pgassign` (oder ähnlich, basierend auf dem `AdminProductGroupsAssociationsController`, der die `pgassign`-Entität verwaltet).
    -   **`$definition`-Felder:** Würden typischerweise Felder wie:
        -   `id_pgassign` (Primärschlüssel)
        -   `id_group` (ID der Ziel-Kundengruppe)
        -   `id_product` (ID des Produkts, wenn die Regel produktspezifisch ist)
        -   `id_category` (ID der Kategorie, wenn die Regel kategoriespezifisch ist)
        -   `min_quantity` (Erforderliche Mindestmenge)
        -   `id_order_state` (Bestellstatus zur Auslösung der Zuweisung)
        -   `assignment_type` (z. B. 'add' oder 'replace')
    -   **Wichtige öffentliche Methoden:**
        -   `add()`: Zum Speichern einer neuen Zuordnungsregel.
        -   `update()`: Zum Ändern einer bestehenden Zuordnungsregel.
        -   `delete()`: Zum Entfernen einer Zuordnungsregel.
        -   `getAssociationsByProduct($id_product)`: Zum Abrufen von Regeln basierend auf einem Produkt.
        -   `getAssociationsByCategory($id_category)`: Zum Abrufen von Regeln basierend auf einer Kategorie.

### 4.4 JavaScript-Assets (`views/js/`)

-   `pgroup/lib/searchTool/views/js/autocomplete.js`
    -   **Geltungsbereich:** Back-Office (wahrscheinlich im Formular des `AdminProductGroupsAssociationsController` verwendet).
    -   **Funktionalität:** Implementiert eine Autocomplete-Suchfunktion, wahrscheinlich zur Auswahl von Produkten oder Kategorien beim Erstellen/Bearbeiten einer Zuweisungsregel. Es überwacht Benutzereingaben in einem bestimmten Textfeld, sendet AJAX-Anfragen an einen Backend-Endpunkt (wahrscheinlich einen dedizierten Admin-AJAX-Controller oder die `ajaxProcess`-Methode des Hauptmoduls), um passende Produkte/Kategorien abzurufen, und zeigt Vorschläge an. Anschließend wird die Auswahl eines Elements verarbeitet und versteckte Eingabefelder mit IDs gefüllt.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `pgroup/css.css`
    -   **Geltungsbereich:** Back-Office (allgemeines Modul-Styling).
    -   **Funktionalität:** Enthält allgemeine Styling-Regeln für die Konfigurationsseite des Moduls und möglicherweise die `AdminProductGroupsAssociationsController`-Oberfläche. Dies könnte Stile für Formularelemente, Schaltflächen oder Layoutanpassungen spezifisch für das Modul umfassen.
-   `pgroup/lib/searchTool/views/css/autocomplete.css`
    -   **Geltungsbereich:** Back-Office (Autocomplete-spezifisches Styling).
    -   **Funktionalität:** Bietet Styling für das Autocomplete-Suchfeld, die Dropdown-Liste der Vorschläge und hervorgehobene Elemente innerhalb der Liste. Entwickler können diese Klassen überschreiben, um sie an benutzerdefinierte Back-Office-Themes anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, was darauf hindeutet, dass der Front-Office-Einfluss des Moduls indirekt ist und nicht durch direkte Inhaltseinfügung über Hooks erfolgt.
-   **Admin-Templates (`views/templates/admin/`)**:

    -   `pgroup/lib/searchTool/views/scripts.tpl`
        -   **Geltungsbereich:** Back-Office.
        -   **Funktionalität:** Enthält wahrscheinlich JavaScript-Initialisierungsskripte für die Autocomplete-Funktionalität. Dieses Template würde in das Formular des `AdminProductGroupsAssociationsController` aufgenommen, um das notwendige JS für das Produkt-/Kategorie-Suchwerkzeug zu rendern.
    -   `pgroup/views/templates/admin/orderstates.tpl`
        -   **Geltungsbereich:** Back-Office.
        -   **Funktionalität:** Dieses Template rendert wahrscheinlich eine Dropdown-Liste oder eine Liste von PrestaShop-Bestellstatus, die es dem Händler ermöglicht, auszuwählen, welcher Status die Kundengruppenzuweisung auslösen soll. Es wäre Teil des `HelperForm`, der im `AdminProductGroupsAssociationsController` verwendet wird.
    -   `pgroup/views/templates/admin/script.tpl`
        -   **Geltungsbereich:** Back-Office.
        -   **Funktionalität:** Könnte zusätzliches JavaScript oder Smarty-Logik enthalten, die spezifisch für die Konfigurationsseite des Moduls oder die Formulare des `AdminProductGroupsAssociationsController` ist, wie z. B. die bedingte Anzeige von Feldern oder AJAX-Aufrufe.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   `ps_pgassign`: Diese Tabelle wird vom Modul während der Installation erstellt. Sie speichert die Produkt-zu-Gruppe-Zuordnungsregeln.
        -   `id_pgassign` (INT, PRIMARY KEY, AUTO_INCREMENT)
        -   `id_group` (INT, Fremdschlüssel zu `ps_group`)
        -   `id_product` (INT, Fremdschlüssel zu `ps_product`, nullbar, wenn die Regel kategoriebasiert ist)
        -   `id_category` (INT, Fremdschlüssel zu `ps_category`, nullbar, wenn die Regel produktbasiert ist)
        -   `min_quantity` (INT, Standard 1)
        -   `id_order_state` (INT, Fremdschlüssel zu `ps_order_state`)
        -   `assignment_type` (VARCHAR, z. B. 'add', 'replace')
    -   Konfigurationseinträge in `ps_configuration`: Das Modul könnte seine Haupteinstellung `PS_PGROUP_ENABLED` (oder ähnlich) hier speichern.
-   **Registrierte Hooks-Tabelle**:
    Die Kernfunktionalität des Moduls basiert auf Hooks, die ausgelöst werden, wenn sich ein Bestellstatus ändert.

    | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
    | --- | --- | --- |
    | `actionOrderStatusPostUpdate` | Wird unmittelbar nach der Aktualisierung des Status einer Bestellung ausgeführt. | Dies ist der wahrscheinlichste Hook, der vom Modul verwendet wird, um zu überprüfen, ob eine Bestellung den konfigurierten Status erreicht hat, und dann die Gruppenzuweisungsregeln basierend auf den Produkten in dieser Bestellung anzuwenden. |
    | `actionObjectOrderUpdateAfter` | Wird ausgeführt, nachdem ein Order-Objekt aktualisiert wurde. | Könnte auch verwendet werden, ähnlich wie `actionOrderStatusPostUpdate`, um auf Bestelländerungen zu reagieren. |
    | `displayHeader` | Rendert Inhalte im `<head>`-Bereich von Front-Office-Seiten. | Nicht direkt für die Kernfunktionalität verwendet, könnte aber zum Laden globaler JS/CSS verwendet werden, wenn das Modul Front-Office-Komponenten hätte (was es anscheinend nicht hat). |
    | `displayRightColumn` / `displayLeftColumn` | Rendert Inhalte in den Seitenleisten von Front-Office-Seiten. | Nicht direkt für die Kernfunktionalität verwendet. |
    | `displayProductAdditionalInfo` / `displayProductButtons` | Rendert Inhalte auf der Produktseite. | Nicht direkt für die Kernfunktionalität verwendet. |
    | `displayFooter` | Rendert Inhalte im Footer von Front-Office-Seiten. | Nicht direkt für die Kernfunktionalität verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Kunden Gruppen nach gekauften Produkten zuweisen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
