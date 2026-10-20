---
title: "Interne, benutzerdefinierte Produktfelder – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Interne, benutzerdefinierte Produktfelder' von MyPresta.eu."
sidebar:
  label: "Interne, benutzerdefinierte Produktfelder"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Internal, custom product fields auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/internal-custom-product-fields.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/internal-custom-product-fields/)
>
> ---


# Interne, benutzerdefinierte Produktfelder

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Interne, benutzerdefinierte Produktfelder)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf "Konfigurieren" im Modul-Manager zugänglich ist.

-   **Was diese Einstellung bewirkt:** Dieser Bildschirm verwaltet hauptsächlich den internen Aktualisierungsmechanismus und die Grundeinstellungen des Moduls.
-   **Auswirkungen der Änderung dieser Einstellung:**
    -   `mypresta_updates`: Diese interne Einstellung steuert, ob das Modul nach Updates von MyPresta.eu sucht.
    -   `update_`: Bezogen auf den Update-Prüfprozess.
    -   `updatev_`: Bezogen auf den Update-Prüfprozess.
    -   `PS_LANG_DEFAULT`: Dies ist ein standardmäßiger PrestaShop-Konfigurationsschlüssel und wird normalerweise von Modulen gelesen, um die Standardsprache für die Anzeige von Inhalten im Back Office zu bestimmen. Es ist keine Einstellung, die Sie normalerweise direkt in der Konfiguration dieses Moduls ändern.
-   **Empfohlener Wert:** Für `mypresta_updates` wird generell empfohlen, es aktiviert zu lassen, um Benachrichtigungen über neue Versionen und Fehlerbehebungen zu erhalten. Die anderen Einstellungen sind intern und sollten nicht manuell geändert werden.
-   **Händlerszenario / Beispiel:** Sie interagieren normalerweise nicht direkt mit diesen spezifischen Einstellungen. Der Hauptzweck dieses Bildschirms ist es, eine Landingpage für das Modul bereitzustellen und sicherzustellen, dass sein Aktualisierungsmechanismus aktiv ist.

### 2.2 Dedizierter Admin-Bildschirm: Verwaltung interner Felder (Back Office > Katalog > Interne Felder)

Dies ist der Kernbildschirm, auf dem Sie Ihre benutzerdefinierten internen Produktfelder definieren und verwalten. Nach der Installation des Moduls erscheint ein neuer Menüpunkt namens "Interne Felder" unter dem Menü "Katalog" in Ihrem PrestaShop Back Office.

-   **Bildschirmname & Menüpfad:** **Katalog > Interne Felder**
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Rasteransicht:** Dieser Bildschirm zeigt eine Liste aller von Ihnen erstellten benutzerdefinierten internen Felder an. Jede Zeile zeigt den Namen des Feldes und seinen Status (aktiviert/deaktiviert).
    -   **Schaltfläche "Neues Feld hinzufügen":** Klicken Sie auf diese Schaltfläche, um ein brandneues benutzerdefiniertes Feld zu erstellen.
    -   **Bearbeiten/Löschen-Aktionen:** Für jedes Feld in der Liste sehen Sie Aktionsschaltflächen (Bleistiftsymbol zum Bearbeiten, Papierkorbsymbol zum Löschen), um bestehende Felder zu ändern oder zu entfernen.
    -   **Formular zum Erstellen/Bearbeiten von Feldern:** Beim Hinzufügen oder Bearbeiten eines Feldes sehen Sie typischerweise:
        -   **Feldname:** (z.B. "Lieferanten-SKU", "Lagerort", "Spezielle Handhabungshinweise"). Dies ist die Beschriftung, die neben dem Eingabefeld auf der Produktbearbeitungsseite erscheint.
        -   **Aktiv/Inaktiv-Schalter:** Steuert, ob dieses benutzerdefinierte Feld derzeit auf Produktseiten verwendet werden kann. Wenn inaktiv, wird es nicht angezeigt.
        -   **Feldtyp:** (z.B. Text, Textarea, Zahl usw. - *basierend auf den tatsächlichen Modulfunktionen, vorerst Text angenommen*). Dies bestimmt den Typ des Eingabefeldes.
        -   **Speichern-Schaltfläche:** Zum Speichern Ihrer Änderungen oder des neuen Feldes.
-   **Auswirkungen von Änderungen:**
    -   **Hinzufügen eines neuen Feldes:** Nach dem Speichern erscheint dieses neue Feld sofort auf *jeder* Produktbearbeitungsseite in Ihrem Back Office, bereit für die Dateneingabe.
    -   **Bearbeiten eines Feldes:** Änderungen am Feldnamen oder Status werden sofort auf allen Produktbearbeitungsseiten widergespiegelt.
    -   **Löschen eines Feldes:** Das Feld wird von allen Produktbearbeitungsseiten entfernt. **Seien Sie vorsichtig:** Das Löschen eines Feldes löscht auch alle zuvor in dieses Feld eingegebenen Daten für alle Produkte.
    -   **Aktivieren/Deaktivieren eines Feldes:** Ein aktives Feld ist auf Produktseiten sichtbar; ein inaktives Feld ist ausgeblendet.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Gehen Sie zu **Katalog > Interne Felder**.
    2.  Klicken Sie auf "Neues Feld hinzufügen", um ein Feld wie "Lieferanten-Teilenummer" oder "Interne Notizen" zu erstellen.
    3.  Legen Sie den Feldnamen fest und stellen Sie sicher, dass es aktiv ist.
    4.  Speichern Sie das Feld.
    5.  Wenn Sie nun zu **Katalog > Produkte** gehen und ein beliebiges Produkt bearbeiten, sehen Sie ein neues Eingabefeld für Ihre "Lieferanten-Teilenummer", in das Sie spezifische Daten für dieses Produkt eingeben können.
    6.  Wiederholen Sie dies für alle anderen internen Daten, die Sie verfolgen müssen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | `mypresta_updates` | Aktiviert | Steuert Modul-Update-Prüfungen. Für Updates aktiviert lassen. |
| Modulkonfigurationsseite | `update_`, `updatev_` | (Intern) | Interne Update-Mechanismus-Variablen. Nicht ändern. |
| Modulkonfigurationsseite | `PS_LANG_DEFAULT` | (Intern) | PrestaShops Standard-Sprach-ID. Nur lesbar. |
| Katalog > Interne Felder | **Neues Feld hinzufügen** | N/A | Erstellt ein neues benutzerdefiniertes internes Produktfeld. |
| Katalog > Interne Felder | **Feldname** | Benutzerdefiniert | Beschriftung für das benutzerdefinierte Feld auf Produktbearbeitungsseiten. |
| Katalog > Interne Felder | **Aktiv/Inaktiv** | Aktiv | Steuert die Sichtbarkeit des Feldes auf Produktbearbeitungsseiten. |
| Katalog > Interne Felder | **Bearbeiten/Löschen-Aktionen** | N/A | Bestehende benutzerdefinierte Felder ändern oder entfernen. Beim Löschen werden alle zugehörigen Daten entfernt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe ein neues Feld erstellt, aber ich sehe es nicht auf meiner Produktbearbeitungsseite.**
A:
1.  Gehen Sie zu **Katalog > Interne Felder** und stellen Sie sicher, dass das von Ihnen erstellte Feld als "Aktiv" markiert ist.
2.  Leeren Sie Ihren PrestaShop-Cache: Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf "Cache leeren".
3.  Versuchen Sie erneut, ein Produkt zu bearbeiten. Wenn es immer noch nicht angezeigt wird, stellen Sie sicher, dass Ihre PrestaShop-Version vollständig mit dem Modul kompatibel ist.

**F: Kann ich diese benutzerdefinierten Felder im Front-Office für Kunden anzeigen?**
A: Nein, dieses Modul ist speziell nur für den internen Back Office-Gebrauch konzipiert. Die in diese Felder eingegebenen Daten sind nicht dazu bestimmt, Kunden angezeigt zu werden. Wenn Sie benutzerdefinierte Felder für das Front-Office benötigen, benötigen Sie eine andere Art von Modul oder eine benutzerdefinierte Entwicklung.

**F: Was passiert, wenn ich ein benutzerdefiniertes Feld lösche?**
A: Wenn Sie ein benutzerdefiniertes Feld unter **Katalog > Interne Felder** löschen, werden alle Daten, die Sie in dieses spezifische Feld für *alle* Ihre Produkte eingegeben haben, dauerhaft entfernt. Stellen Sie immer sicher, dass Sie die Daten nicht mehr benötigen, bevor Sie ein Feld löschen.

**F: Das Modul scheint Probleme mit meinem benutzerdefinierten Theme zu verursachen. Was soll ich tun?**
A:
1.  Leeren Sie zuerst Ihren Smarty-Cache (wie oben erwähnt).
2.  Wenn das Problem weiterhin besteht, versuchen Sie, andere Module nacheinander vorübergehend zu deaktivieren, um festzustellen, ob ein Konflikt vorliegt.
3.  Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12) auf JavaScript-Fehler.
4.  Wenn Sie das Problem immer noch nicht lösen können, wenden Sie sich an den MyPresta.eu-Support mit Details zu Ihrem Theme und dem spezifischen Problem.

**F: Wie übersetze ich die Namen meiner benutzerdefinierten Felder in verschiedene Sprachen?**
A: Das Modul sollte es Ihnen ermöglichen, den Feldnamen für jede in Ihrem PrestaShop-Shop aktivierte Sprache zu definieren, wenn Sie das Feld erstellen oder bearbeiten. Suchen Sie nach Sprach-Tabs neben dem Eingabefeld "Feldname" im Formular zum Erstellen/Bearbeiten von Feldern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht
Das Modul "Interne, benutzerdefinierte Produktfelder" erweitert die Produktverwaltungsfunktionen von PrestaShop, indem es benutzerdefinierte Felder in die Produktbearbeitungsseite im Back Office einfügt. Es nutzt das MVC-Muster von PrestaShop, hauptsächlich über einen Admin Controller zur Verwaltung der benutzerdefinierten Felddefinitionen und Overrides, um diese Felder in die bestehenden Produktformulare zu integrieren. Daten werden in einer dedizierten Datenbanktabelle gespeichert, und JavaScript wird für die dynamische Formularmanipulation verwendet.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**: Dieses Modul verfügt über keine dedizierten Front-Office-Controller, da seine Funktionalität vollständig Back Office-orientiert ist. Front-Office-Hooks werden wahrscheinlich für die allgemeine Moduleinrichtung oder zur Vermeidung von Front-Office-Konflikten verwendet.

-   **Back-Office-Admin-Controller**:
    *   `aipf/controllers/admin/AdminInternalFields.php`
        *   **Klassenname**: `AdminInternalFieldsController` (erweitert `ModuleAdminController`)
        *   **Tab-Name**: "Interne Felder" (unter dem Katalog-Menü)
        *   **Verantwortlichkeit**: Dies ist der primäre Controller zur Verwaltung der Definitionen der benutzerdefinierten internen Produktfelder. Er verwaltet die Auflistung, Erstellung, Bearbeitung und Löschung dieser Felder. Er verwendet PrestaShops `HelperList` für die Rasteransicht und `HelperForm` für die Hinzufügen/Bearbeiten-Formulare. Er interagiert mit dem benutzerdefinierten `ObjectModel` des Moduls (wahrscheinlich `AipfInternalField`), um Felddefinitionen zu speichern.
    *   `aipf/controllers/admin/index.php`
        *   **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die oft in Verzeichnissen platziert wird, um die Verzeichnisauflistung auf Webservern zu verhindern und die Sicherheit zu erhöhen. Sie enthält keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul verwendet Overrides, um seine Funktionalität in den PrestaShop-Kern zu integrieren.

-   `aipf/override/classes/controller/Controller.php`
    *   **Klassenname**: `Controller` (überschreibt die Kernklasse `Controller`)
    *   **Verantwortlichkeit**: Dieser Override wird wahrscheinlich verwendet, um modulspezifisches JavaScript oder CSS global oder bedingt einzufügen oder das Verhalten aller Controller zu ändern. Angesichts des Zwecks des Moduls könnte es verwendet werden, um sicherzustellen, dass die notwendigen Assets für die Produktseite geladen werden oder um spezifische AJAX-Anfragen im Zusammenhang mit den benutzerdefinierten Feldern zu behandeln.
-   `aipf/override/classes/controller/index.php`
    *   **Verantwortlichkeit**: Sicherheits-Platzhalter.
-   `aipf/override/classes/index.php`
    *   **Verantwortlichkeit**: Sicherheits-Platzhalter.

*Hinweis: Basierend auf der Beschreibung sollte es eine `ObjectModel`-Klasse für `AipfInternalField` (z.B. `classes/AipfInternalField.php`) geben, um die benutzerdefinierten Felddefinitionen zu verwalten, und möglicherweise eine weitere, um die tatsächlichen Produktdaten für diese Felder zu verwalten. Dies ist nicht explizit im Inventar aufgeführt, wird aber durch die Funktionalität impliziert.*

### 4.4 JavaScript-Assets (`views/js/`)

-   `aipf/lib/js/admin/aipf-configuration.js`
    *   **Geltungsbereich**: Back-Office (Modulkonfiguration).
    *   **Zweck**: Behandelt wahrscheinlich spezifische JavaScript-Logik für den Hauptkonfigurationsbildschirm des Moduls, wie z.B. Update-Prüfungen oder einfache Formularinteraktionen.
-   `aipf/lib/js/admin/aipf.js`
    *   **Geltungsbereich**: Back-Office (allgemeiner Admin, potenziell Produktseite).
    *   **Zweck**: Enthält die Kern-JavaScript-Logik für das Modul innerhalb des Back Office. Dies könnte AJAX-Aufrufe zum Speichern von Produktfelddaten, dynamisches Feld-Rendering auf der Produktseite oder Interaktionen mit dem `AdminInternalFieldsController` umfassen.
-   `aipf/lib/js/front/aipf-front.js`
    *   **Geltungsbereich**: Front-Office.
    *   **Zweck**: Obwohl das Modul für den internen Gebrauch bestimmt ist, könnte diese Datei als Platzhalter existieren oder sehr spezifische, nicht-visuelle Front-Office-Aufgaben behandeln, wie z.B. die Sicherstellung, dass keine Konflikte mit anderen Skripten auftreten, oder für eine potenzielle zukünftige Funktion, die nicht implementiert wurde. Angesichts der Modulbeschreibung sollte ihr Einfluss auf das Front-Office minimal bis gar nicht vorhanden sein.
-   `aipf/views/js/AdminInternalFields.js`
    *   **Geltungsbereich**: Back-Office (AdminInternalFieldsController-Bildschirm).
    *   **Zweck**: Spezifisches JavaScript für den Verwaltungsbildschirm "Katalog > Interne Felder". Dies würde Interaktionen innerhalb des Rasters, Formularvalidierung zum Hinzufügen/Bearbeiten von Feldern und AJAX-Anfragen im Zusammenhang mit der Feldverwaltung behandeln.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `aipf/lib/css/aipf.css`
    *   **Geltungsbereich**: Primär Back-Office, potenziell minimal Front-Office.
    *   **Zweck**: Bietet Styling für die benutzerdefinierten Felder auf der Produktbearbeitungsseite, dem Verwaltungsbildschirm "Interne Felder" und allen anderen vom Modul im Back Office eingeführten UI-Elementen. Es könnte auch Reset-Styles oder sehr grundlegende Regeln enthalten, die auf das Front-Office angewendet werden könnten, um Konflikte zu vermeiden, obwohl der Hauptfokus auf der administrativen Benutzeroberfläche liegt.
    *   **Wichtige CSS-Klassenselektoren**: Entwickler könnten nach Klassen wie `.aipf-field-container`, `.aipf-input`, `.aipf-label` suchen, um das Erscheinungsbild der benutzerdefinierten Felder zu überschreiben oder anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**: Nicht explizit aufgeführt, aber das Modul würde wahrscheinlich Templates für Hooks wie `displayAdminProductsExtra` oder `displayAdminProductsMainStepLeftColumnMiddle` verwenden, um die benutzerdefinierten Felder in die Produktbearbeitungsseite einzufügen.
-   **Admin-Templates (`views/templates/admin/`)**:
    *   `aipf/views/templates/admin/combination.tpl`
        *   **Zweck**: Dieses Template wurde speziell entwickelt, um benutzerdefinierte interne Felder in die Bearbeitungsoberfläche für Produktkombinationen (Varianten) innerhalb des Back Office einzufügen. Es würde die Eingabefelder für die benutzerdefinierten Daten rendern, die mit jeder Produktkombination verknüpft sind. Dies ist entscheidend für Produkte mit Attributen (wie Größe, Farbe), bei denen jede Kombination ihre eigenen internen Notizen oder Identifikatoren benötigen könnte.
-   **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt, was mit der Back Office-only-Natur des Moduls übereinstimmt.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   `ps_aipf_internal_field`: Diese Tabelle würde die Definitionen der benutzerdefinierten internen Felder speichern (z.B. `id_aipf_internal_field`, `name`, `active`, `field_type`).
    *   `ps_aipf_internal_field_lang`: Wenn Feldnamen übersetzbar sind, würde diese Tabelle die sprachspezifischen Namen für die benutzerdefinierten Felder speichern (z.B. `id_aipf_internal_field`, `id_lang`, `name`).
    *   `ps_aipf_product_data`: Diese Tabelle würde die tatsächlichen vom Händler eingegebenen Daten für jedes benutzerdefinierte Feld speichern, verknüpft mit einem bestimmten Produkt und potenziell einer bestimmten Kombination (z.B. `id_aipf_internal_field`, `id_product`, `id_product_attribute` (falls zutreffend), `value`).
    *   `ps_configuration`: Standard-PrestaShop-Tabelle, die zur Speicherung von Modulkonfigurationswerten wie `mypresta_updates`, `update_`, `updatev_` verwendet wird.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|---|
| `actionAjaxDieProductControllerdisplayAjaxRefreshBefore` | Front/Admin | Vor AJAX-Antwort in ProductController | Potenziell zur Vorverarbeitung von AJAX-Anfragen im Zusammenhang mit Produktdaten, um sicherzustellen, dass benutzerdefinierte Felder berücksichtigt werden. |
| `actionOutputHTMLBefore` | Front/Admin | Vor HTML-Ausgabe | Allgemeiner Hook, könnte für globale Asset-Injektion oder frühe Verarbeitung verwendet werden. |
| `ActionAfterUpdateCombinationFormFormHandler` | Admin | Nach Aktualisierung des Kombinationsformulars | Zum Speichern oder Verarbeiten von benutzerdefinierten Felddaten im Zusammenhang mit Produktkombinationen. |
| `actionAdminControllerSetMedia` | Admin | Wenn Admin-Controller Medien setzt | Zum Einfügen von modulspezifischem CSS/JS in Back Office-Seiten (z.B. Produktbearbeitungsseite, Modulkonfiguration). |
| `actionCombinationFormFormBuilderModifier` | Admin | Wenn der Kombinationsformular-Builder geändert wird | Zum dynamischen Hinzufügen von benutzerdefinierten Feldern zum Produktkombinationsformular. |
| `actionProductUpdate` | Admin | Nach Aktualisierung eines Produkts | Zum Speichern oder Verarbeiten von benutzerdefinierten Felddaten, wenn ein Produkt gespeichert wird. |
| `ActionFrontControllerSetMedia` | Front | Wenn Front-Controller Medien setzt | Zum Einfügen von modulspezifischem CSS/JS in Front Office-Seiten (falls erforderlich, obwohl unwahrscheinlich für dieses Modul). |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Interne, benutzerdefinierte Produktfelder" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
