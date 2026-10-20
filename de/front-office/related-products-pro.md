---
title: "Related Products Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Related Products Pro von MyPresta.eu."
sidebar:
  label: "Related Products Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Related Products Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/related-products-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/related-products-pro/)
>
> ---


# Related Products Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise erforderlich und in den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Modul-Manager > Related Products Pro > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie alle Aspekte Ihrer Listen verwandter Produkte verwalten. Die Benutzeroberfläche ist intuitiv gestaltet, sodass Sie verwandte Produkte einfach erstellen, bearbeiten und zuweisen können.

Die Konfigurationsseite zeigt typischerweise eine Liste Ihrer vorhandenen Listen verwandter Produkte (falls vorhanden) und Optionen zum Erstellen neuer oder zum Verwalten globaler Einstellungen.

#### **Hauptelemente der Benutzeroberfläche:**

-   **Liste der vorhandenen Blöcke für verwandte Produkte:** Diese Tabelle zeigt alle von Ihnen erstellten Listen verwandter Produkte. Für jede Liste sehen Sie Details wie ihren Namen, die Produkte, denen sie zugewiesen ist, und Optionen zum Bearbeiten oder Löschen.
-   **Schaltfläche „Neuen Block für verwandte Produkte hinzufügen“:** Klicken Sie hier, um einen brandneuen Satz verwandter Produkte zu erstellen.
-   **Globale Einstellungen / Präferenzen:** (Falls verfügbar) Diese Einstellungen könnten allgemeine Anzeigeoptionen oder Standardverhalten für alle Blöcke verwandter Produkte steuern.

#### **Beim Hinzufügen/Bearbeiten eines Blocks für verwandte Produkte:**

Wenn Sie auf „Neuen Block hinzufügen“ oder „Bestehenden bearbeiten“ klicken, sehen Sie typischerweise ein Formular mit den folgenden Einstellungen:

1.  **Blockname:**

    *   **Was diese Einstellung bewirkt:** Dies ist der interne Name für Ihre Liste verwandter Produkte, der nur im Back Office sichtbar ist. Er hilft Ihnen, verschiedene Listen zu identifizieren.
    *   **Auswirkung einer Änderung dieser Einstellung:** Ändert die Bezeichnung für diesen spezifischen Block verwandter Produkte in Ihrem Admin-Panel.
    *   **Empfohlener Wert:** Verwenden Sie einen beschreibenden Namen, z. B. „Produkt X - Ergänzende Artikel“, „Kategorie Y - Bestseller“.
    *   **Händlerszenario / Beispiel:** Sie könnten eine Liste „Sommerkleider - Passende Sandalen“ nennen, um sie später leicht wiederzufinden.
2.  **Anzeigeposition (Hook):**

    *   **Was diese Einstellung bewirkt:** Bestimmt, wo auf der Produktseite dieser spezifische Block verwandter Produkte erscheinen wird. Sie wählen einen PrestaShop „Hook“, der ein festgelegter Anzeigebereich ist.
    *   **Auswirkung einer Änderung dieser Einstellung:** Die verwandten Produkte werden an die gewählte Position auf der Front-Office-Produktseite verschoben.
    *   **Empfohlener Wert:** Experimentieren Sie mit verschiedenen Hooks basierend auf Ihrem Theme. Gängige Optionen sind `displayProductExtraContent` (oft in der Nähe der Produktbeschreibung), `displayProductFooter` (am unteren Rand der Produktseite) oder `displayRightColumnProduct` (wenn Ihr Theme eine rechte Spalte auf Produktseiten hat).
    *   **Händlerszenario / Beispiel:** Wenn Sie möchten, dass die verwandten Produkte direkt unter dem Hauptproduktbild und der Beschreibung erscheinen, könnten Sie `displayProductExtraContent` wählen. Wenn Sie sie ganz unten auf der Seite bevorzugen, wäre `displayProductFooter` besser.
3.  **Anzuzeigende Produkte:**

    *   **Was diese Einstellung bewirkt:** Hier definieren Sie, *welche* Produkte in diesem Block verwandter Produkte angezeigt werden. Sie haben typischerweise mehrere Optionen:
        *   **Spezifische Produkte (Manuelle Auswahl):**
            *   **Was dies bewirkt:** Ermöglicht Ihnen, einzelne Produkte manuell zu suchen und auszuwählen, die in die Liste aufgenommen werden sollen.
            *   **Auswirkung:** Es erscheinen nur die Produkte, die Sie explizit auswählen.
            *   **Empfohlen:** Verwenden Sie dies für hochgradig kuratierte Empfehlungen.
            *   **Szenario:** Für eine bestimmte Kamera könnten Sie manuell ein Stativ, eine Kameratasche und ein zusätzliches Objektiv auswählen.
        *   **Produkte aus ausgewählten Kategorien:**
            *   **Was dies bewirkt:** Zeigt Produkte aus einer oder mehreren von Ihnen ausgewählten Kategorien an.
            *   **Auswirkung:** Die Liste zeigt dynamisch Produkte aus diesen Kategorien an.
            *   **Empfohlen:** Gut, um verwandte Artikel innerhalb einer Produktlinie oder Abteilung anzuzeigen.
            *   **Szenario:** Für ein „Herrenhemd“ könnten Sie die Kategorien „Herrenhosen“ und „Herrenaccessoires“ auswählen.
        *   **Neue Produkte:**
            *   **Was dies bewirkt:** Zeigt automatisch die neuesten Produkte an, die Ihrem Shop hinzugefügt wurden.
            *   **Auswirkung:** Die Liste zeigt immer Ihre neuesten Ergänzungen.
            *   **Empfohlen:** Ideal zur Förderung von Neuheiten.
            *   **Szenario:** Verwenden Sie diesen Block, um Ihre neueste Schmuckkollektion hervorzuheben.
        *   **Bestseller:**
            *   **Was dies bewirkt:** Zeigt automatisch die meistverkauften Produkte Ihres Shops an.
            *   **Auswirkung:** Die Liste wird dynamisch aktualisiert, um Ihre beliebtesten Artikel anzuzeigen.
            *   **Empfohlen:** Hervorragend für Social Proof und die Förderung beliebter Artikel.
            *   **Szenario:** Zeigen Sie „Kunden kauften auch“ Artikel basierend auf der allgemeinen Beliebtheit im Shop an.
    *   **Anzahl der anzuzeigenden Produkte:**
        *   **Was dies bewirkt:** Steuert, wie viele verwandte Produkte im Block angezeigt werden.
        *   **Auswirkung:** Begrenzt die sichtbaren Produkte.
        *   **Empfohlen:** 4-8 Produkte für ein sauberes Aussehen, abhängig von Ihrem Layout.
        *   **Szenario:** Zeigen Sie 5 verwandte Artikel an, um den Abschnitt prägnant zu halten.
4.  **Produkten zuweisen:**

    *   **Was diese Einstellung bewirkt:** Dies ist entscheidend – sie bestimmt, *auf welchen Produktseiten* dieser spezifische Block verwandter Produkte erscheinen wird.
    *   **Auswirkung einer Änderung dieser Einstellung:** Der Block verwandter Produkte ist nur auf den Produktseiten sichtbar, die Sie hier auswählen.
    *   **Empfohlener Wert:** Sie können ihn zuweisen zu:
        *   **Alle Produkte:** Wenn dies ein allgemeiner „Bestseller“- oder „Neuheiten“-Block ist.
        *   **Spezifische Produkte (Manuelle Auswahl):** Für hochgradig zielgerichtete Empfehlungen.
        *   **Produkte aus ausgewählten Kategorien:** Um den Block auf einen gesamten Kategoriebereich anzuwenden.
    *   **Händlerszenario / Beispiel:** Sie erstellen eine Liste von „iPhone-Zubehör“. Sie würden diesen Block dann nur Ihren iPhone-Produktseiten zuweisen. Oder Sie erstellen einen Block „Sommer-Sale-Artikel“ und weisen ihn allen Produkten innerhalb Ihrer Kategorie „Sommerkollektion“ zu.
5.  **Anzeigetyp / Template:**

    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl des visuellen Layouts oder Templates, wie die verwandten Produkte angezeigt werden (z. B. Raster, Karussell, Liste, Tabelle). Das Modul enthält oft verschiedene Templates, von denen einige für bestimmte Themes (wie Panda, Warehouse, Zone Themes) optimiert sein könnten.
    *   **Auswirkung einer Änderung dieser Einstellung:** Ändert die visuelle Darstellung der verwandten Produkte im Front Office.
    *   **Empfohlener Wert:** Experimentieren Sie, um die beste Passform für Ihr Theme und den gewählten Hook zu finden. Ein Karussell ist oft gut, um Platz zu sparen, während ein Raster besser für einen dedizierten Bereich sein könnte.
    *   **Händlerszenario / Beispiel:** Wenn Sie eine schlanke, platzsparende Anzeige wünschen, könnten Sie ein „Karussell“-Template wählen. Wenn Sie viel Platz haben und mehr Details anzeigen möchten, könnte ein „Raster“ oder eine „Tabelle“ besser sein. Einige Templates könnten speziell nach beliebten Themes benannt sein (z. B. `panda-blocksProductsCart.tpl`), um eine bessere Integration zu gewährleisten.
6.  **Karussell-Einstellungen (falls zutreffend):**

    *   **Was diese Einstellung bewirkt:** Wenn Sie einen Karussell-Anzeigetyp wählen, haben Sie möglicherweise zusätzliche Optionen wie:
        *   **Autoplay:** Ob das Karussell automatisch scrollt.
        *   **Loop:** Ob das Karussell nach dem letzten Element von vorne beginnt.
        *   **Elemente pro Ansicht:** Wie viele Produkte gleichzeitig im Karussell sichtbar sind.
        *   **Navigationspfeile/Punkte:** Ob Steuerelemente für manuelles Scrollen angezeigt werden sollen.
    *   **Auswirkung einer Änderung dieser Einstellung:** Steuert das Verhalten und Aussehen des Produktkarussells.
    *   **Empfohlener Wert:** Autoplay kann ansprechend sein, aber auch ablenkend wirken. Berücksichtigen Sie Ihr Publikum. 3-5 Elemente pro Ansicht sind ein häufig gutes Gleichgewicht.
    *   **Händlerszenario / Beispiel:** Sie möchten ein dezentes Karussell, das alle 5 Sekunden automatisch scrollt, 4 Produkte gleichzeitig anzeigt und Navigationspfeile für Benutzer bereitstellt, die manuell blättern möchten.

#### **Ihre Änderungen speichern:**

Denken Sie immer daran, nach Änderungen an einem Block verwandter Produkte auf die Schaltfläche „Speichern“ oder „Aktualisieren“ zu klicken, um sicherzustellen, dass Ihre Einstellungen übernommen werden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | **Blockname** | Beschreibend (z. B. „Produkt X - Cross-Sell“) | Interne Bezeichnung zur Identifizierung des Blocks verwandter Produkte im Back Office. |
| | **Anzeigeposition (Hook)** | `displayProductExtraContent` oder `displayProductFooter` | Bestimmt, wo der Block auf der Front-Office-Produktseite erscheint. |
| | **Anzuzeigende Produkte: Spezifische Produkte** | Manuelle Auswahl | Zeigt nur handverlesene Produkte an. Am besten für hochgradig kuratierte Empfehlungen. |
| | **Anzuzeigende Produkte: Aus ausgewählten Kategorien** | Relevante Kategorien auswählen | Zeigt dynamisch Produkte aus ausgewählten Kategorien an. Gut für verwandte Produktlinien. |
| | **Anzuzeigende Produkte: Neue Produkte** | Automatisch befüllt | Zeigt automatisch die neuesten Produkte in Ihrem Shop an. Ideal für Neuheiten. |
| | **Anzuzeigende Produkte: Bestseller** | Automatisch befüllt | Zeigt automatisch die meistverkauften Produkte Ihres Shops an. Hervorragend für Social Proof. |
| | **Anzahl der anzuzeigenden Produkte** | 4-8 | Begrenzt die Anzahl der im Block angezeigten Produkte für ein sauberes Layout. |
| | **Produkten zuweisen: Alle Produkte** | N/A | Zeigt den Block auf jeder Produktseite an. Verwenden Sie dies für allgemeine Empfehlungen. |
| | **Produkten zuweisen: Spezifische Produkte** | Manuelle Auswahl | Zeigt den Block nur auf ausgewählten Produktseiten an. Für gezielte Cross-Sells. |
| | **Produkten zuweisen: Aus ausgewählten Kategorien** | Relevante Kategorien auswählen | Zeigt den Block auf Produktseiten innerhalb ausgewählter Kategorien an. |
| | **Anzeigetyp / Template** | `accessories.tpl` oder themespezifisch | Steuert das visuelle Layout (Raster, Karussell, Liste). Wählen Sie basierend auf Theme und Hook. |
| | **Karussell-Einstellungen (Autoplay, Loop, Elemente pro Ansicht, Navigation)** | Variiert, oft aktiviert | Steuert das Verhalten von Karussell-Anzeigen. Anpassen für Benutzererfahrung. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine verwandten Produkte werden im Front Office nicht angezeigt.**

-   **A:** Stellen Sie zunächst sicher, dass das Modul aktiviert und konfiguriert ist. Überprüfen Sie, ob Sie den Block für verwandte Produkte tatsächlich den spezifischen Produkten oder Kategorien *zugewiesen* haben, die Sie anzeigen. Vergewissern Sie sich auch, dass der von Ihnen ausgewählte „Anzeigeposition (Hook)“ von Ihrem Theme auf der Produktseite tatsächlich gerendert wird. Leeren Sie abschließend Ihren PrestaShop-Cache (Erweiterte Einstellungen > Performance > Cache leeren).

**F2: Die verwandten Produkte sehen seltsam aus oder passen nicht zum Design meines Themes.**

-   **A:** Dies ist oft ein Styling-Konflikt mit Ihrem benutzerdefinierten Theme.
    *   **Lösung 1:** Probieren Sie verschiedene „Anzeigetyp / Template“-Optionen in der Modulkonfiguration aus. Einige Templates sind für bestimmte beliebte Themes konzipiert (z. B. `panda-blocksProductsCart.tpl`).
    *   **Lösung 2:** Leeren Sie den Cache Ihres Browsers und den Smarty-Cache von PrestaShop (Erweiterte Einstellungen > Performance).
    *   **Lösung 3:** Wenn das Problem weiterhin besteht, sind möglicherweise benutzerdefinierte CSS-Anpassungen erforderlich. Dies ist eine Aufgabe für einen Webmaster oder Entwickler (siehe Abschnitt 7.5).

**F3: Kann ich mehrere Blöcke für verwandte Produkte auf derselben Produktseite haben?**

-   **A:** Ja! Das Modul ist dafür ausgelegt. Sie können mehrere separate Blöcke für verwandte Produkte erstellen, jeder mit seinen eigenen Produkten, Anzeigetyp und zugewiesener Position (Hook). Stellen Sie einfach sicher, dass Sie sie in verschiedenen Hooks platzieren, um Überschneidungen zu vermeiden.

**F4: Wie übersetze ich den Text des Moduls (z. B. „Verwandte Produkte“) in andere Sprachen?**

-   **A:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Related Products Pro“ aus der Modul-Dropdown-Liste. Sie können dann die Textzeichenfolgen für jede Sprache bearbeiten.

**F5: Das Karussell funktioniert nicht oder Produkte sind vertikal gestapelt.**

-   **A:** Dies deutet normalerweise auf einen JavaScript-Konflikt oder eine fehlende JS-Bibliothek hin.
    *   **Lösung 1:** Stellen Sie sicher, dass Ihr Theme auf dem neuesten Stand ist.
    *   **Lösung 2:** Leeren Sie Ihren PrestaShop-Cache und den Browser-Cache.
    *   **Lösung 3:** Suchen Sie in den Entwicklertools Ihres Browsers (F12) nach Konsolenfehlern. Wenn Sie JavaScript-Fehler sehen, könnte dies auf einen Konflikt mit einem anderen Modul oder Ihrem Theme hinweisen. Dies würde eine Untersuchung durch einen Entwickler erfordern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Einblick in das Modul „Related Products Pro“ für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul „Related Products Pro“ (`ppb`) folgt einer Standard-PrestaShop-Modularchitektur und nutzt hauptsächlich die `Module`-Klasse für seine Kernfunktionalität. Es konzentriert sich darauf, das Front-Office-Produkseiten-Erlebnis zu erweitern, indem es benutzerdefinierte Produktlisten in verschiedene Anzeige-Hooks einfügt. Das Modul verwaltet seine Konfiguration und die Daten der verwandten Produkte direkt in der `getContent()`-Methode der `index.php`-Datei, die sowohl die Formularwiedergabe als auch die Datenpersistenz handhabt. Es verwendet ein benutzerdefiniertes Templating-System für eine flexible Front-Office-Anzeige, einschließlich spezifischer Templates für beliebte Themes. JavaScript- und CSS-Assets werden bedingt geladen, um die Benutzeroberfläche zu verbessern und Karussell-Funktionalität bereitzustellen.

### 4.2 Controller (`controllers/`)

Das Modul scheint keine dedizierten `ModuleFrontController`- oder `AdminController`-Klassen zu verwenden. Die gesamte Front-Office-Wiedergabe erfolgt über Hooks, und die Back-Office-Konfiguration wird innerhalb der `getContent()`-Methode der Hauptdatei `index.php` verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen, die `ObjectModel` in einem dedizierten `classes/`-Verzeichnis erweitern. Die Datenpersistenz für die Konfigurationen verwandter Produkte wird wahrscheinlich direkt über `Configuration::updateValue()` oder benutzerdefinierte Datenbanktabellen gehandhabt, die innerhalb der Hauptdatei `index.php` verwaltet werden.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`ppb/lib/searchTool/views/js/autocomplete.js`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Produktauswahlfelder innerhalb der Konfigurationsformulare des Moduls, wahrscheinlich für die manuelle Auswahl spezifischer Produkte, die hinzugefügt oder zugewiesen werden sollen. Es überwacht Benutzereingaben in Textfeldern und schlägt Produkte basierend auf teilweisen Übereinstimmungen vor.
-   **`ppb/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Wahrscheinlich Teil eines generischen Dienstprogramms zur Verwaltung von Smarty-Templates innerhalb der Admin-Oberfläche. Es könnte das dynamische Laden, Speichern oder Vorschauen von Template-Code handhaben, möglicherweise für benutzerdefinierte Template-Erstellungs- oder Änderungsfunktionen innerhalb des Moduls verwendet.
-   **`ppb/lib/src/js/lightslider.js`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Dies ist eine Drittanbieterbibliothek zum Erstellen responsiver Inhaltskarussells. Sie bindet sich an bestimmte HTML-Elemente (wahrscheinlich `<ul>` oder `<div>` mit einer bestimmten Klasse), um sie in einen Slider zu verwandeln. Sie verarbeitet Touch-/Wischereignisse, Navigation, Autoplay und responsive Anpassungen.
-   **`ppb/views/admin/ppb.js`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Enthält die Kern-JavaScript-Logik für die Back-Office-Konfigurationsseite des Moduls. Dies würde Event-Listener für Formularübermittlungen, dynamische Aktualisierungen von Einstellungen basierend auf Benutzerentscheidungen (z. B. Anzeigen/Ausblenden von Karussell-Optionen), AJAX-Aufrufe zum Speichern von Daten und möglicherweise die Verwaltung der Liste der Blöcke für verwandte Produkte umfassen.
-   **`ppb/views/admin/ppb8.js`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Ähnlich wie `ppb.js`, enthält aber wahrscheinlich spezifische Anpassungen oder zusätzliche Funktionalitäten für PrestaShop 8.x-Umgebungen, die API-Änderungen oder UI-Unterschiede in neueren PrestaShop-Versionen berücksichtigen.
-   **`ppb/views/js/accessories.js`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Enthält Front-Office-spezifisches JavaScript für die Blöcke verwandter Produkte. Dies könnte Initialisierungslogik für das `lightslider.js`-Karussell, die Handhabung von Produktklicks oder dynamische Interaktionen innerhalb der angezeigten Listen verwandter Produkte umfassen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`ppb/css.css`**:
    *   **Geltungsbereich:** Sowohl Front-Office als auch Back-Office.
    *   **Verantwortlichkeit:** Allgemeine modulweite Stile. Könnte Basisstile für die Blöcke verwandter Produkte oder gemeinsame Elemente enthalten, die im gesamten Modul verwendet werden.
-   **`ppb/lib/searchTool/views/css/autocomplete.css`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für die Autocomplete-Dropdowns und Eingabefelder, die im Admin-Produktauswahltool verwendet werden.
-   **`ppb/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Styling für die Smarty-Template-Verwaltungsoberfläche innerhalb der Modulkonfiguration.
-   **`ppb/lib/src/css/lightslider.css`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Kern-Styling für das `lightslider.js`-Karussell, das seine Struktur, Navigationspfeile, Punkte und responsives Verhalten definiert. Entwickler können diese Stile überschreiben, um sie an ihr Theme anzupassen.
-   **`ppb/views/admin/ppb.css`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Spezifisches Styling für die Konfigurationsseite des Moduls im PrestaShop-Admin-Panel, um eine gute Integration in die PrestaShop-Back-Office-Benutzeroberfläche zu gewährleisten.
-   **`ppb/views/css/ppb-table.css`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Styling für Listen verwandter Produkte, die in einem Tabellenformat angezeigt werden, wahrscheinlich für spezifische „Tabellenlisten“-Templates verwendet.
-   **`ppb/views/css/ppb.css`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Primäres Front-Office-Styling für die Blöcke verwandter Produkte, einschließlich Produktkarten-Layouts, Abstände und allgemeines Erscheinungsbild.
-   **`ppb/views/css/ppbcarousell.css`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Zusätzliches oder spezifisches Styling für die Karussell-Anzeige verwandter Produkte, das möglicherweise `lightslider.css` für benutzerdefinierte Modulästhetik überschreibt oder erweitert.
-   **`ppb/views/css/ppb_custom.css`**:
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Wahrscheinlich für benutzerdefinierte CSS-Definitionen oder themespezifische Überschreibungen gedacht, um das Erscheinungsbild der Blöcke verwandter Produkte anzupassen, ohne die Kernmoduldateien zu ändern.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul bietet eine Vielzahl von Templates, von denen viele auf spezifische Hooks und beliebte PrestaShop-Themes zugeschnitten sind.

-   **`ppb/lib/searchTool/views/scripts.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Enthält JavaScript-Initialisierung oder -Konfiguration für das Autocomplete-Suchwerkzeug, das im Admin verwendet wird.
-   **`ppb/lib/smartyTemplatesManager/tpl/example.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Ein Beispiel-Template, wahrscheinlich als Referenz oder zur Demonstration der Fähigkeiten des Smarty-Template-Managers verwendet.
-   **`ppb/lib/smartyTemplatesManager/views/buttonManager.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Rendert Schaltflächen oder Steuerelemente zur Verwaltung von Templates innerhalb der Admin-Oberfläche.
-   **`ppb/lib/smartyTemplatesManager/views/createTemplateForm.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Rendert das Formular zum Erstellen neuer benutzerdefinierter Anzeigetemplates für verwandte Produkte.
-   **`ppb/lib/smartyTemplatesManager/views/editTemplateForm.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Rendert das Formular zum Bearbeiten bestehender benutzerdefinierter Anzeigetemplates.
-   **`ppb/lib/smartyTemplatesManager/views/mainForm.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Das Hauptformular für den Smarty-Template-Manager, das wahrscheinlich Templates auflistet und Optionen bereitstellt.
-   **`ppb/lib/smartyTemplatesManager/views/selectInput.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Rendert ein Dropdown-Auswahlfeld, möglicherweise zur Auswahl von Templates oder anderen Optionen verwendet.
-   **`ppb/views/templates/admin/tabs.tpl`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Rendert die Tab-Navigationsstruktur für die Konfigurationsseite des Moduls, falls es mehrere Tabs für verschiedene Einstellungen verwendet.
-   **Hook-Templates (`views/templates/hook/`)**: Diese Templates werden auf der Front-Office-Produktseite über verschiedene PrestaShop-Hooks gerendert. Viele sind themespezifisch, um eine optimale Integration zu gewährleisten.

    *   **`accessories.tpl`**:
        *   **Hook:** Konfigurierbar, oft `displayProductExtraContent` oder `displayProductFooter`.
        *   **Ausgabe:** Ein generisches Template zur Anzeige verwandter Produkte, typischerweise in einem Raster oder Karussell.
    *   **`blocksProductsCart.tpl`**:
        *   **Hook:** Konfigurierbar, oft `displayProductExtraContent` oder `displayProductFooter`.
        *   **Ausgabe:** Ein Block von Produkten, möglicherweise im Stil eines Warenkorbs oder für allgemeine Produktempfehlungen.
    *   **`blocksProductsOrder.tpl`**:
        *   **Hook:** Konfigurierbar.
        *   **Ausgabe:** Ähnlich wie `blocksProductsCart.tpl`, könnte aber für einen anderen Kontext oder ein anderes Layout gestaltet sein.
    *   **`custom-pictures-only.tpl`**:
        *   **Hook:** Konfigurierbar.
        *   **Ausgabe:** Eine minimalistische Anzeige, die nur Produktbilder zeigt, ideal für kompakte Räume oder visuelles Browsing.
    *   **`panda-blocksProductsCart.tpl`**, **`panda-blocksProductsOrder.tpl`**, **`panda-ProductExtraContent.tpl`**, **`panda-productFooter.tpl`**, **`panda-productTab.tpl`**, **`panda-productTabContent.tpl`**:
        *   **Hook:** Konfigurierbar, für das Panda-Theme konzipiert.
        *   **Ausgabe:** Themespezifische Templates, die eine nahtlose Integration und Styling mit der Designsprache des Panda-Themes gewährleisten. Sie rendern verwandte Produkte innerhalb der angegebenen Panda-Theme-Bereiche (z. B. zusätzlicher Produktinhalt, Fußzeile oder dedizierte Tabs).
    *   **`ProductExtraContent.tpl`**:
        *   **Hook:** `displayProductExtraContent`.
        *   **Ausgabe:** Rendert verwandte Produkte innerhalb des `displayProductExtraContent`-Hooks, typischerweise ein prominenter Bereich in der Nähe der Hauptproduktdetails.
    *   **`productFooter.tpl`**:
        *   **Hook:** `displayProductFooter`.
        *   **Ausgabe:** Rendert verwandte Produkte am unteren Rand der Produktseite.
    *   **`productTab.tpl`**:
        *   **Hook:** Konfigurierbar, oft `displayProductButtons` oder `displayProductExtraContent` (um einen neuen Tab hinzuzufügen).
        *   **Ausgabe:** Rendert den *Tab-Header* für einen dedizierten „Verwandte Produkte“-Tab auf der Produktseite.
    *   **`productTabContent.tpl`**:
        *   **Hook:** Konfigurierbar, oft `displayProductContent` oder `displayProductExtraContent` (um Inhalte für einen neuen Tab hinzuzufügen).
        *   **Ausgabe:** Rendert den *Inhalt* für einen dedizierten „Verwandte Produkte“-Tab, der erscheint, wenn der `productTab.tpl`-Header angeklickt wird.
    *   **`table-list.tpl`**:
        *   **Hook:** Konfigurierbar.
        *   **Ausgabe:** Zeigt verwandte Produkte in einem Tabellenformat an, möglicherweise nützlich zum Vergleich von Funktionen oder für eine strukturiertere Liste.
    *   **`warehouse-blocksProductsCart.tpl`**, **`warehouse-blocksProductsOrder.tpl`**, etc. (alle mit `warehouse-` präfixierten Templates):
        *   **Hook:** Konfigurierbar, für das Warehouse-Theme konzipiert.
        *   **Ausgabe:** Themespezifische Templates für das Warehouse-Theme, die eine korrekte Styling- und Layout-Integration gewährleisten.
    *   **`zone-blocksProductsCart.tpl`**, **`zone-blocksProductsOrder.tpl`**, etc. (alle mit `zone-` präfixierten Templates):
        *   **Hook:** Konfigurierbar, für das Zone-Theme konzipiert.
        *   **Ausgabe:** Themespezifische Templates für das Zone-Theme, die eine korrekte Styling- und Layout-Integration gewährleisten.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**: Das Modul speichert seine Konfigurationsdaten (Definitionen der Blöcke für verwandte Produkte, zugewiesene Produkte, Anzeigeeinstellungen) wahrscheinlich in benutzerdefinierten Datenbanktabellen, die während der Installation erstellt werden, oder es könnte sich stark auf `ps_configuration` für einfachere Einstellungen verlassen. Angesichts der Komplexität mehrerer Listen verwandter Produkte sind benutzerdefinierte Tabellen wahrscheinlicher. Entwickler müssten die `install()`-Methode in `ppb/index.php` auf `Db::getInstance()->execute()`-Aufrufe überprüfen, um die Tabellenerstellung zu identifizieren.

    *   **Wahrscheinliche Tabellen (Hypothetisch basierend auf Funktionalität):**
        *   `ps_ppb_blocks`: Speichert die Hauptdefinition jedes Blocks für verwandte Produkte (ID, Name, Hook, Anzeigetyp usw.).
        *   `ps_ppb_block_products`: Eine Many-to-Many-Tabelle, die Blöcke für verwandte Produkte mit den Produkten verknüpft, die sie anzeigen sollen.
        *   `ps_ppb_block_assignments`: Eine Many-to-Many-Tabelle, die Blöcke für verwandte Produkte mit den Produktseiten verknüpft, auf denen sie erscheinen sollen.
        *   `ps_ppb_block_categories`: Eine Tabelle zum Speichern von Kategoriezuweisungen für die dynamische Produktauswahl oder -zuweisung.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS- und JavaScript-Assets (z. B. `lightslider.js`, `ppb.css`) bedingt nur auf Produktseiten oder global zu laden. |
| `displayRightColumnProduct` | In der rechten Spalte der Produktseite. | Rendert Blöcke für verwandte Produkte in der rechten Seitenleiste. |
| `displayLeftColumnProduct` | In der linken Spalte der Produktseite. | Rendert Blöcke für verwandte Produkte in der linken Seitenleiste. |
| `displayProductExtraContent` | Ein flexibler Hook, oft in der Nähe der Produktbeschreibung/des Bildes. | Ein gängiger und sehr empfehlenswerter Hook zum Einfügen von Blöcken für verwandte Produkte direkt in den Hauptinhaltsbereich. |
| `displayProductFooter` | Am unteren Rand der Produktseite, vor der allgemeinen Fußzeile. | Rendert Blöcke für verwandte Produkte in einem dedizierten Abschnitt am Ende des Produktseiteninhalts. |
| `displayProductButtons` | In der Nähe der Schaltfläche „In den Warenkorb“ oder der Produktaktionen. | Könnte verwendet werden, um einen „Verwandte Produkte“-Tab-Header hinzuzufügen. |
| `displayProductContent` | Innerhalb des Hauptproduktinhaltsbereichs. | Könnte verwendet werden, um den Inhalt eines „Verwandte Produkte“-Tabs zu rendern. |
| `displayFooter` | In der globalen Fußzeile des Shops. | Weniger gebräuchlich für verwandte Produkte, aber möglich für sehr allgemeine Empfehlungen. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Potenziell verwendet, um den Cache zu leeren oder verwandte Produktdaten neu zu indizieren, wenn dynamische Listen verwendet werden. |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Zum Bereinigen von Zuweisungen verwandter Produkte, die das gelöschte Produkt betreffen. |
| `actionCategoryUpdate` | Nach der Aktualisierung einer Kategorie. | Zum Neubewerten von Listen verwandter Produkte, die von Kategorieauswahlen abhängen. |
| `actionCategoryDelete` | Nach dem Löschen einer Kategorie. | Zum Bereinigen von Zuweisungen verwandter Produkte, die die gelöschte Kategorie betreffen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Related Products Pro“ zur Verfügung.
