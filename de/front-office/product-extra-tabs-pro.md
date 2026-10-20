---
title: "Product Extra Tabs Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Product Extra Tabs Pro von MyPresta.eu."
sidebar:
  label: "Product Extra Tabs Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product Extra Tabs Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-extra-tabs-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-extra-tabs-pro/)
>
> ---


# Product Extra Tabs Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Product Extra Tabs Pro“ wird hauptsächlich direkt von der Produktbearbeitungsseite aus konfiguriert, sodass Sie Tabs pro Produkt verwalten können. Der Hauptkonfigurationsbildschirm des Moduls behandelt globale Einstellungen.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Hauptkonfiguration zuzugreifen, gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Product Extra Tabs Pro“ und klicken Sie auf „Konfigurieren“.

Auf diesem Bildschirm finden Sie Einstellungen, die global gelten oder definieren, wie sich das Modul in Ihrem Shop verhält.

-   **Einstellung: TinyMCE Editor für Tab-Inhalt aktivieren**

    *   **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob ein Rich-Text-Editor (TinyMCE, derselbe Editor, den PrestaShop für Produktbeschreibungen verwendet) verfügbar ist, wenn Sie Tab-Inhalt erstellen oder bearbeiten.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Sie sehen einen benutzerfreundlichen Editor mit Formatierungsoptionen (fett, kursiv, Listen, Bilder, Links usw.), wenn Sie Inhalt zu Ihren Extra-Tabs hinzufügen. Dies erleichtert die Erstellung visuell ansprechender und gut strukturierter Inhalte, ohne HTML-Kenntnisse zu benötigen.
        *   *Wenn deaktiviert:* Sie haben nur ein einfaches Textfeld für den Tab-Inhalt. Sie müssten HTML-Tags manuell schreiben, um Ihren Text zu formatieren, was für nicht-technische Benutzer komplexer ist.
    *   **Empfohlener Wert:** **JA**
    *   **Händlerszenario / Beispiel:** Wenn Sie Bilder, Videos oder formatierten Text zu Ihren Tabs hinzufügen möchten (z. B. einen „Größentabelle“-Tab mit einem Bild oder einen „Garantie“-Tab mit fettgedruckten Schlüsselbegriffen), aktivieren Sie dies. Wenn Sie nur einfachen Text benötigen, können Sie es für eine einfachere Benutzeroberfläche deaktivieren.
-   **Einstellung: Tabs global anzeigen (für alle Produkte)**

    *   **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, „globale“ Tabs zu erstellen, die automatisch auf *jeder* Produktseite in Ihrem Shop erscheinen. Dies ist nützlich für Informationen, die universell gelten, wie z. B. allgemeine Versandrichtlinien oder Markengeschichten.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Alle Tabs, die Sie innerhalb der Konfigurationsoberfläche des Moduls (nicht auf einzelnen Produktseiten) erstellen, werden auf allen Produktseiten angezeigt. Sie können diese globalen Tabs dann über die Hauptkonfiguration des Moduls verwalten.
        *   *Wenn deaktiviert:* Tabs müssen individuell für jedes Produkt von der jeweiligen Produktbearbeitungsseite aus erstellt und verwaltet werden. Globale Tabs werden nicht angezeigt.
    *   **Empfohlener Wert:** **JA** (wenn Sie Informationen haben, die für alle Produkte gelten, andernfalls NEIN).
    *   **Händlerszenario / Beispiel:** Sie möchten einen „Rückgaberichtlinien“-Tab hinzufügen, der für alle Produkte identisch ist. Aktivieren Sie dies, erstellen Sie den Tab hier, und er wird auf jeder Produktseite angezeigt. Wenn Sie nur einzigartige Tabs für bestimmte Produkte benötigen, lassen Sie dies deaktiviert.
-   **Einstellung: Tab-Anzeigeposition**

    *   **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü steuert, wo die zusätzlichen Tabs auf der Produktseite angezeigt werden.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Option: `displayProductExtraContent` (Standard):* Tabs erscheinen im Standard-Produktinhaltsbereich, normalerweise unter den Hauptproduktdetails, neben den Standard-Beschreibungs-/Datenblatt-Tabs. Dies ist die häufigste und empfohlene Position.
        *   *Option: `displayFooterProduct` (nur PrestaShop 1.6):* Tabs erscheinen im Fußbereich der Produktseite. Dies könnte für weniger kritische, ergänzende Informationen geeignet sein.
        *   *Option: `displayRightColumnProduct` (nur PrestaShop 1.6):* Tabs erscheinen in der rechten Spalte der Produktseite. Dies ist für Tabs weniger üblich und könnte stark vom Layout Ihres Themes abhängen.
        *   *Option: `displayLeftColumnProduct` (nur PrestaShop 1.6):* Tabs erscheinen in der linken Spalte der Produktseite. Ähnlich wie bei der rechten Spalte ist dies für Tabs weniger üblich.
    *   **Empfohlener Wert:** `displayProductExtraContent`
    *   **Händlerszenario / Beispiel:** Für die meisten Shops bietet `displayProductExtraContent` die beste Benutzererfahrung, da alle produktbezogenen Informationen zusammengefasst werden. Wenn Ihr Theme ein sehr spezifisches Layout hat oder Sie die Tabs weniger hervorheben möchten, könnten Sie mit Fuß- oder Spaltenpositionen experimentieren (obwohl diese für Tabs weniger üblich sind).

#### 2.1.1 Globale Tab-Verwaltung (wenn „Tabs global anzeigen“ aktiviert ist)

Wenn Sie „Tabs global anzeigen“ aktiviert haben, erscheint dieser Abschnitt auf der Konfigurationsseite des Moduls. Hier können Sie Tabs hinzufügen, bearbeiten oder löschen, die auf *allen* Produktseiten angezeigt werden.

-   **Schaltfläche „Neuen Tab hinzufügen“:** Klicken Sie hier, um ein Formular zu öffnen, in dem Sie einen neuen globalen Tab definieren können.
    *   **Tab-Titel:** Der Text, der auf dem Tab selbst erscheint (z. B. „Versandinformationen“, „Garantie“). Dies ist normalerweise mehrsprachig.
    *   **Tab-Inhalt:** Der tatsächliche Inhalt, der erscheint, wenn der Tab angeklickt wird. Verwenden Sie den TinyMCE-Editor, falls aktiviert. Dies ist ebenfalls mehrsprachig.
    *   **Aktiv:** Ein Schalter zum Aktivieren oder Deaktivieren des Tabs, ohne ihn zu löschen.
    *   **Position:** Eine Zahl zur Steuerung der Reihenfolge des Tabs im Verhältnis zu anderen globalen Tabs. Kleinere Zahlen erscheinen zuerst.
-   **Liste der vorhandenen Tabs:** Eine Tabelle, die alle Ihre aktuell konfigurierten globalen Tabs anzeigt.
    *   **Bearbeiten-Symbol:** Klicken Sie hier, um den Titel, den Inhalt oder die Einstellungen eines vorhandenen Tabs zu ändern.
    *   **Löschen-Symbol:** Klicken Sie hier, um einen globalen Tab dauerhaft zu entfernen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Die primäre Methode zur Verwaltung produktspezifischer Extra-Tabs erfolgt direkt über die **Produktbearbeitungsseite** in Ihrem PrestaShop Back Office.

-   **Bildschirmname & Menüpfad:**

    1.  Navigieren Sie zu **Katalog > Produkte**.
    2.  Bearbeiten Sie ein bestehendes Produkt oder erstellen Sie ein neues.
    3.  Suchen Sie innerhalb der Produktbearbeitungsoberfläche nach einem neuen Tab oder Abschnitt mit der Bezeichnung **„Extra Tabs Pro“** (oder ähnlich, je nach Ihrer PrestaShop-Version und Ihrem Theme).
-   **Verfügbare Aktionen & Einstellungen im Abschnitt „Extra Tabs Pro“ auf einer Produktseite:**

    *   **Schaltfläche „Neuen Tab hinzufügen“:** Klicken Sie hier, um einen neuen Tab *speziell für dieses Produkt* zu erstellen.
        *   **Tab-Titel:** Geben Sie den Titel für diesen produktspezifischen Tab ein (z. B. „Technische Daten für Modell X“). Dies ist mehrsprachig.
        *   **Tab-Inhalt:** Geben Sie den Inhalt für diesen Tab ein. Der TinyMCE-Editor ist verfügbar, wenn er in der Hauptmodulkonfiguration aktiviert ist. Dies ist mehrsprachig.
        *   **Aktiv:** Aktivieren/Deaktivieren Sie diesen spezifischen Tab für dieses Produkt.
        *   **Position:** Legen Sie die Anzeigereihenfolge für diesen Tab im Verhältnis zu anderen Tabs auf dieser Produktseite fest.
    *   **Liste der vorhandenen Tabs:** Eine Tabelle, die alle Extra-Tabs anzeigt, die Sie für *dieses bestimmte Produkt* erstellt haben.
        *   **Bearbeiten-Symbol:** Ändern Sie den Titel, den Inhalt oder den Status eines vorhandenen produktspezifischen Tabs.
        *   **Löschen-Symbol:** Entfernen Sie einen Tab von diesem Produkt.
-   **Auswirkung von Änderungen:**

    *   Wenn Sie einen Tab im Abschnitt „Extra Tabs Pro“ eines Produkts hinzufügen, bearbeiten oder löschen, wirken sich diese Änderungen *nur auf diese spezifische Produktseite* aus.
    *   Der Inhalt und die Sichtbarkeit dieser Tabs werden nach dem Speichern Ihrer Änderungen sofort auf der Front-Office-Produktseite aktualisiert.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Universelle Informationen identifizieren:** Wenn Sie Informationen haben, die für ALLE Produkte gelten (z. B. allgemeiner Versand, Rücksendungen, Markengeschichte), verwenden Sie die Funktion für **globale Tabs** in der Hauptkonfiguration des Moduls.
    2.  **Produktspezifische Informationen identifizieren:** Für Details, die für ein Produkt einzigartig sind (z. B. spezifische Abmessungen, Materialzusammensetzung, Gebrauchsanweisungen, Video-Rezensionen), gehen Sie zur **einzelnen Produktbearbeitungsseite** und verwenden Sie dort den Abschnitt „Extra Tabs Pro“.
    3.  **TinyMCE-Editor verwenden:** Aktivieren Sie immer den TinyMCE-Editor in der Hauptmodulkonfiguration für eine einfachere Inhaltserstellung und -formatierung.
    4.  **Regelmäßige Überprüfung:** Überprüfen Sie regelmäßig Ihre Produktseiten, um sicherzustellen, dass die Tabs korrekt angezeigt werden und der Inhalt aktuell ist.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | TinyMCE Editor aktivieren | JA | Bietet Rich-Text-Editor für Tab-Inhalt; einfachere Formatierung. |
| | Tabs global anzeigen | NEIN (oder JA bei Bedarf) | JA: Globale Tabs erscheinen auf allen Produkten. NEIN: Tabs sind produktspezifisch. |
| | Tab-Anzeigeposition | `displayProductExtraContent` | Steuert, wo Tabs auf der Produktseite erscheinen. |
| | **Globale Tabs-Liste** | (N/A) | Tabs hinzufügen/bearbeiten/löschen, die auf ALLEN Produktseiten erscheinen. |
| **Produktbearbeitungsseite** | **Extra Tabs Pro Abschnitt** | (N/A) | Tabs hinzufügen/bearbeiten/löschen, die spezifisch für das aktuelle Produkt sind. |
| | Tab-Titel | (Benutzerdefiniert) | Der sichtbare Name des Tabs auf der Produktseite. |
| | Tab-Inhalt | (Benutzerdefiniert) | Die Informationen, die angezeigt werden, wenn der Tab angeklickt wird. |
| | Aktiv | JA | Steuert, ob der Tab sichtbar oder ausgeblendet ist. |
| | Position | (Benutzerdefiniert) | Bestimmt die Reihenfolge der Tabs auf der Produktseite. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

-   **F: Meine neuen Tabs werden auf der Produktseite nicht angezeigt.**
    *   **A:** Stellen Sie zunächst sicher, dass der Tab sowohl in der globalen Konfiguration des Moduls (wenn es ein globaler Tab ist) als auch auf der einzelnen Produktseite (wenn es produktspezifisch ist) als „Aktiv“ markiert ist. Zweitens leeren Sie Ihren PrestaShop-Cache: Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Leeren Sie auch den Cache Ihres Browsers.
-   **F: Der TinyMCE-Editor wird nicht angezeigt, wenn ich Tab-Inhalt hinzufügen möchte.**
    *   **A:** Gehen Sie zur Hauptkonfigurationsseite des Moduls (**Module > Modul-Manager > Product Extra Tabs Pro > Konfigurieren**) und stellen Sie sicher, dass die Einstellung „TinyMCE Editor für Tab-Inhalt aktivieren“ auf **JA** gesetzt ist. Speichern Sie die Änderungen und leeren Sie den Cache.
-   **F: Meine Tabs sehen seltsam aus oder passen nicht zum Styling meines Themes.**
    *   **A:** Das Modul versucht, sich nahtlos zu integrieren, aber benutzerdefinierte Themes können manchmal die Standardstile überschreiben. Wenn das Erscheinungsbild nicht stimmt, sind in der Regel kleinere CSS-Anpassungen in Ihrem Theme erforderlich. Kontaktieren Sie Ihren Webmaster oder den MyPresta.eu-Support mit Screenshots für Unterstützung.
-   **F: Kann ich verschiedene Tabs für verschiedene Sprachen haben?**
    *   **A:** Ja! Die Felder „Tab-Titel“ und „Tab-Inhalt“ sind mehrsprachig. Beim Bearbeiten eines Tabs sehen Sie Sprachflaggen neben diesen Feldern. Klicken Sie auf die Flagge, um zu einer anderen Sprache zu wechseln und den übersetzten Inhalt einzugeben.
-   **F: Ich möchte einen Tab nur für bestimmte Produkte anzeigen, nicht für alle.**
    *   **A:** Stellen Sie sicher, dass die Einstellung „Tabs global anzeigen“ in der Hauptkonfiguration des Moduls auf **NEIN** gesetzt ist. Navigieren Sie dann zu jedem spezifischen Produkt, dem Sie einen Tab hinzufügen möchten (**Katalog > Produkte > Produkt bearbeiten > Abschnitt Extra Tabs Pro**) und erstellen Sie die Tabs dort.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Product Extra Tabs Pro` ist als Standard-PrestaShop-Modul konzipiert, das hauptsächlich die Klasse `Module` erweitert. Es nutzt das Hook-System von PrestaShop, um seinen Inhalt in Produktseiten einzufügen, und verwendet eine benutzerdefinierte Datenbanktabelle zur Speicherung von Tab-Daten. Die Konfiguration wird über `getContent()` in der Hauptmoduldatei gehandhabt, und die produktspezifische Tab-Verwaltung ist direkt über einen benutzerdefinierten Tab in die Produktadministrationsseite integriert. Es verwendet AJAX für dynamisches Laden und Speichern von Inhalten.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller im Verzeichnis `controllers/`. Die gesamte Front-Office-Darstellung wird über Hooks und Template-Dateien gehandhabt, und die Back-Office-Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei und über AJAX-Aufrufe verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Seine primäre Datenverarbeitungslogik ist in der Hauptmoduldatei `extratabspro/ajax_extratabspro.php` eingebettet.

### 4.4 JavaScript-Assets (`views/js/`)

-   `extratabspro/js/tinymce16.inc.js`:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Diese Datei enthält wahrscheinlich die Initialisierung und Konfiguration für den TinyMCE Rich-Text-Editor, speziell zugeschnitten auf PrestaShop 1.6-Umgebungen. Sie stellt sicher, dass der Editor korrekt für die Eingabefelder des Tab-Inhalts geladen und konfiguriert wird.
-   `extratabspro/lib/searchTool/views/js/autocomplete.js`:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Dieses Skript ist Teil einer Suchwerkzeugbibliothek, die wahrscheinlich für die Autocomplete-Funktionalität in einem Suchfeld innerhalb der Admin-Oberfläche des Moduls verwendet wird (z. B. Suche nach Produkten, denen Tabs zugewiesen werden sollen, obwohl diese spezifische Funktion im Händlerhandbuch nicht explizit erwähnt wird, ist es ein gängiges Muster für eine solche Bibliothek). Es bindet Event-Listener an Eingabefelder und verarbeitet AJAX-Anfragen für Suchvorschläge.
-   `extratabspro/views/admin/extratabspro.js`:
    *   **Geltungsbereich:** Back-Office (PrestaShop 1.7.x, 8.x, 9.x).
    *   **Zweck:** Dies ist die Haupt-JavaScript-Datei für die Administrationsschnittstelle des Moduls. Sie verarbeitet:
        *   AJAX-Aufrufe zum Hinzufügen, Bearbeiten, Löschen globaler Tabs.
        *   AJAX-Aufrufe zum Hinzufügen, Bearbeiten, Löschen produktspezifischer Tabs auf der Produktbearbeitungsseite.
        *   Dynamische Aktualisierungen der Tab-Listen-Tabellen.
        *   Event-Listener für Formularübermittlungen, Schaltflächenklicks (Hinzufügen/Bearbeiten/Löschen) und möglicherweise Drag-and-Drop-Neuanordnung von Tabs.
        *   Integration mit TinyMCE für Inhaltsfelder.
-   `extratabspro/views/admin/extratabspro8.js`:
    *   **Geltungsbereich:** Back-Office (PrestaShop 8.x, 9.x).
    *   **Zweck:** Ähnlich wie `extratabspro.js`, enthält aber wahrscheinlich spezifische Anpassungen oder Korrekturen für PrestaShop 8.x- und 9.x-Umgebungen, die Änderungen in der Back-Office-DOM-Struktur oder JavaScript-APIs berücksichtigen. Es führt die gleichen Kernfunktionen wie `extratabspro.js` aus, gewährleistet aber die Kompatibilität mit neueren PrestaShop-Versionen.
-   `extratabspro/views/js/extratabspro.js`:
    *   **Geltungsbereich:** Front-Office.
    *   **Zweck:** Dieses Skript handhabt die Front-End-Anzeige und Interaktion der zusätzlichen Tabs auf der Produktseite. Es wird wahrscheinlich:
        *   Den Tab-Wechselmechanismus initialisieren (z. B. jQuery UI Tabs, Bootstrap Tabs oder benutzerdefinierte Logik).
        *   Klickereignisse an Tab-Header binden, um entsprechende Inhalte anzuzeigen/auszublenden.
        *   Reibungslose Übergänge oder das Laden von Inhalten sicherstellen.
        *   Möglicherweise responsives Verhalten für Tabs auf verschiedenen Bildschirmgrößen handhaben.
-   `extratabspro/views/js/tinymce16.inc.js`: (Duplikat, wahrscheinlich für verschiedene Kontexte oder ein Versehen in der Paketierung)
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Gleicher Zweck wie die Datei in `extratabspro/js/`, wahrscheinlich für die TinyMCE-Initialisierung.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `extratabspro/lib/searchTool/views/css/autocomplete.css`:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Bietet Styling für das Dropdown-Menü der Autocomplete-Vorschläge und verwandte UI-Elemente der Suchwerkzeugbibliothek.
-   `extratabspro/views/admin/extratabspro.css`:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Gestaltet die Konfigurationsformulare des Moduls, die Tab-Listen-Tabellen und alle benutzerdefinierten UI-Elemente innerhalb des PrestaShop Back Office, um ein konsistentes Erscheinungsbild zu gewährleisten.
-   `extratabspro/views/css/extratabspro.css`:
    *   **Geltungsbereich:** Front-Office.
    *   **Zweck:** Bietet das Kern-Styling für die zusätzlichen Tabs auf der Produktseite. Dies umfasst das Erscheinungsbild der Tab-Header, der aktiven Tab-Zustände und der Inhaltsbereiche. Entwickler können diese Stile in der `custom.css` oder `theme.css` ihres Themes überschreiben, indem sie Klassen wie `.extratabs-pro-tabs`, `.extratabs-pro-tab-header`, `.extratabs-pro-tab-content` usw. ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:

    *   `extratabspro/views/front/footer.tpl`: Dieses Template ist wahrscheinlich für `displayFooter` oder `displayFooterProduct` Hooks vorgesehen (obwohl das Modul hauptsächlich `displayProductExtraContent` verwendet). Es würde Inhalte im Fußbereich ausgeben.
    *   `extratabspro/views/front/tab.tpl`: Dieses Template rendert einen einzelnen Tab-Header (den anklickbaren Teil). Es wird innerhalb einer Schleife verwendet, um alle Tab-Header zu generieren.
    *   `extratabspro/views/front/tab16.tpl`: Eine Version von `tab.tpl` speziell für PrestaShop 1.6, angepasst an dessen unterschiedliche HTML-Struktur oder CSS-Klassen.
    *   `extratabspro/views/front/tabcontents.tpl`: Dieses Template rendert den Inhaltsbereich für alle zusätzlichen Tabs. Es enthält typischerweise eine Schleife, die den Inhalt jedes Tabs durchläuft und ihn in einen Container einschließt, der von JavaScript ein-/ausgeblendet werden kann.
    *   `extratabspro/views/front/tabcontents16.tpl`: Eine Version von `tabcontents.tpl` speziell für PrestaShop 1.6.
-   **Admin-Templates (`views/templates/admin/`)**:

    *   `extratabspro/lib/searchTool/views/scripts.tpl`: Dieses Template enthält wahrscheinlich JavaScript- und CSS-Assets für die Suchwerkzeugbibliothek im Admin-Kontext.
    *   `extratabspro/views/admin/tabs-list.tpl`: Dieses Template rendert die Tabelle, die alle konfigurierten Tabs auflistet (entweder globale Tabs auf der Modulkonfigurationsseite oder produktspezifische Tabs auf der Produktbearbeitungsseite). Es enthält Steuerelemente zum Bearbeiten und Löschen von Tabs.
    *   `extratabspro/views/admin/tabs17.tpl`: Dieses Template ist das Hauptkonfigurationsformular oder die Anzeige für das Modul im PrestaShop 1.7.x / 8.x / 9.x Back Office. Es enthält wahrscheinlich die Formularfelder für globale Einstellungen und die Einbindung von `tabs-list.tpl` zur Verwaltung von Tabs.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    *   `ps_extratabspro_tab`: Speichert die Hauptinformationen für jeden zusätzlichen Tab (ID, Produkt-ID, Position, aktiver Status).
    *   `ps_extratabspro_tab_lang`: Speichert mehrsprachigen Inhalt für jeden Tab (Titel, Inhalt), verknüpft mit `ps_extratabspro_tab` über `id_extratabspro_tab` und `id_lang`.
    *   `ps_configuration`: Speichert die globalen Einstellungen des Moduls (z. B. `EXTRATABSPRO_TINYMCE_ENABLED`, `EXTRATABSPRO_GLOBAL_TABS_ENABLED`, `EXTRATABSPRO_HOOK_POSITION`).
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Fügt die CSS- und JS-Dateien des Moduls für die Front-Office-Anzeige ein. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich der Back-Office-Seiten. | Fügt die CSS- und JS-Dateien des Moduls für die Back-Office-Konfiguration und Produktseitenintegration ein. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Fügt den Abschnitt „Extra Tabs Pro“ in die Produktadministrationsschnittstelle ein, um die Verwaltung von Tabs pro Produkt zu ermöglichen. |
| `displayProductExtraContent` | Im Hauptinhaltsbereich der Produktseite, typischerweise unter der Produktbeschreibung. | Rendert die tatsächlichen zusätzlichen Tabs und deren Inhalt auf der Front-Office-Produktseite. Dies ist der primäre Hook für die Front-End-Anzeige. |
| `displayFooterProduct` | Im Fußbereich der Produktseite. | Alternativer Hook zur Anzeige von Tabs, falls vom Händler konfiguriert. |
| `displayRightColumnProduct` | In der rechten Spalte der Produktseite. | Alternativer Hook zur Anzeige von Tabs, falls vom Händler konfiguriert. |
| `displayLeftColumnProduct` | In der linken Spalte der Produktseite. | Alternativer Hook zur Anzeige von Tabs, falls vom Händler konfiguriert. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Potenziell zum Leeren des Caches oder zur Durchführung anderer Aktionen im Zusammenhang mit Produktendatenänderungen verwendet. |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Bereinigt produktspezifische Tabs aus der Datenbank. |
| `actionObjectProductAddAfter` | Nach dem Hinzufügen eines neuen Produkts. | Potenziell für die Erstkonfiguration oder die Erstellung von Standard-Tabs für neue Produkte verwendet. |
| `actionObjectProductUpdateAfter` | Nach der Aktualisierung eines Produktobjekts. | Ähnlich wie `actionProductUpdate`, für Objektmodellaktualisierungen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Fragen zum Modul „Product Extra Tabs Pro“ wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team und unsere Entwickler stehen Ihnen gerne zur Verfügung.
