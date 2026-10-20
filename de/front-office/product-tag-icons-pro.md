---
title: "Product Tag Icons Pro – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Product Tag Icons Pro“ von MyPresta.eu."
sidebar:
  label: "Product Tag Icons Pro – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product Tag Icons Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-tag-icons-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-tag-icons-pro/)
>
> ---


# Product Tag Icons Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise erforderlich und auf den meisten modernen Hosting-Umgebungen vorhanden. Es ist keine spezielle Server-Einrichtung erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Product Tag Icons Pro“ bietet eine umfassende Reihe von Konfigurationsoptionen, die auf mehrere dedizierte Bildschirme in Ihrem PrestaShop Back Office verteilt sind.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Modul-Manager > Product Tag Icons Pro konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für allgemeine Moduleinstellungen.

- **Was diese Einstellung bewirkt:** Steuert das Gesamtverhalten und die Standardanzeigeoptionen für Ihre Produkt-Icons.
- **Auswirkung der Änderung dieser Einstellung:** Diese Einstellungen beeinflussen, wie Icons in Ihrem gesamten Shop angezeigt werden oder wie das Modul mit anderen Teilen von PrestaShop interagiert.
- **Empfohlener Wert:** Variiert je nach Design Ihres Shops und der gewünschten Funktionalität.

**Konfigurations-Kurzübersichtstabelle (Hauptmodulkonfiguration)**

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Modul aktivieren** | JA | **Zweck:** Schaltet die Funktionalität des Moduls ein oder aus. **Auswirkung:** Wenn deaktiviert, erscheinen keine Icons in Ihrem Front Office, und die Funktionen des Moduls sind inaktiv. Aktiviert lassen, um das Modul zu verwenden. |
| **Icon-Größe (px)** | 32 | **Zweck:** Legt die Standardgröße (Breite und Höhe) für alle im Front Office angezeigten Icons fest. **Auswirkung:** Alle Icons werden in dieser angegebenen Pixelgröße gerendert. Wählen Sie eine Größe, die gut zu Ihren Produktbildern und dem Gesamtdesign passt, ohne zu klein zum Sehen oder zu groß zum Stören zu sein. |
| **Icon-Position (Hook)** | `displayProductAdditionalInfo` (oder ähnlicher Produktdetailseiten-Hook) | **Zweck:** Bestimmt, wo auf der Produktseite die Icons standardmäßig angezeigt werden. Sie können aus einer Liste verfügbarer PrestaShop-Hooks wählen. **Auswirkung:** Icons erscheinen im ausgewählten Bereich der Produktseite. Experimentieren Sie mit verschiedenen Hooks, um die beste visuelle Platzierung für Ihr Theme zu finden. Häufige Optionen sind `displayProductAdditionalInfo`, `displayProductPriceBlock` oder `displayAfterProductThumbs`. |
| **Icons auf Produktliste anzeigen** | JA | **Zweck:** Steuert, ob Icons auf Produktlistenseiten (Kategorien, Suchergebnisse, Startseiten-Produkthighlights) sichtbar sind. **Auswirkung:** Wenn aktiviert, erscheinen den Produkten zugewiesene Icons auf ihren jeweiligen Produktkarten/Miniaturen in Listen. Wenn deaktiviert, werden Icons nur auf einzelnen Produktseiten angezeigt. Empfohlen, um maximale Wirkung zu erzielen. |
| **Tooltip-Typ** | Light | **Zweck:** Wählt das visuelle Thema für den Tooltip aus, der erscheint, wenn ein Kunde mit der Maus über ein Icon fährt. Optionen umfassen normalerweise Light, Noir, Punk, Shadow. **Auswirkung:** Ändert das Erscheinungsbild des Tooltip-Feldes (Hintergrund, Textfarbe, Rahmen), das die Beschreibung des Icons anzeigt. Wählen Sie eines, das zur Ästhetik Ihres Shops passt. |
| **Tooltip-Position** | Oben | **Zweck:** Bestimmt, wo der Tooltip relativ zum Icon erscheint, wenn man mit der Maus darüberfährt (z. B. Oben, Unten, Links, Rechts). **Auswirkung:** Beeinflusst das Benutzererlebnis bei der Interaktion mit Icons. Wählen Sie eine Position, die andere wichtige Informationen auf der Seite nicht verdeckt. |
| **Tooltip-Animationen aktivieren** | JA | **Zweck:** Fügt subtile Animationen (Einblenden, Verschieben) hinzu, wenn Tooltips erscheinen und verschwinden. **Auswirkung:** Lässt die Tooltip-Interaktion moderner und ansprechender wirken. Wenn Sie ein statisches, sofortiges Erscheinungsbild bevorzugen, deaktivieren Sie dies. |
| **Benutzerdefiniertes CSS** | (Leer) | **Zweck:** Ermöglicht Ihnen, benutzerdefinierte CSS-Regeln hinzuzufügen, um Ihre Icons oder Tooltips weiter zu gestalten, ohne Moduldateien zu ändern. **Auswirkung:** Alle hier eingegebenen CSS-Regeln werden auf die Elemente des Moduls angewendet und überschreiben Standardstile. Verwenden Sie dies zur Feinabstimmung von Farben, Rändern oder spezifischen Icon-Verhalten. |

### 2.2 Dedizierter Admin-Bildschirm: Alle Icons verwalten (Back Office > Product Tag Icons Pro > Alle Icons verwalten)

Dieser Bildschirm ermöglicht es Ihnen, die eigentlichen Icon-Definitionen zu erstellen, zu bearbeiten und zu löschen, die Sie später Ihren Produkten zuordnen werden.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Product Tag Icons Pro > Alle Icons verwalten** in Ihrem PrestaShop Back Office Menü.
- **Verfügbare Aktionen & Einstellungen:**
  - **Neues Icon hinzufügen:** Klicken Sie auf die Schaltfläche „Neues Icon hinzufügen“, um ein neues Icon zu erstellen.
    - **Icon-Name:** Ein beschreibender Name für Ihr Icon (z. B. „Kostenloser Versand“, „Neu eingetroffen“). Dies dient Ihrer internen Referenz.
    - **Icon-Bild:** Laden Sie die Bilddatei für Ihr Icon hoch. Dies sollte ein kleines, klares Bild sein (z. B. PNG, JPG, SVG).
    - **Icon-Beschreibung:** Ein kurzer Text, der als Tooltip erscheint, wenn Kunden im Front Office mit der Maus über das Icon fahren. Erklären Sie, was das Icon bedeutet.
    - **Aktiv:** Schalten Sie um, ob dieses Icon derzeit zur Verwendung und Anzeige verfügbar ist.
    - **Sprachspezifische Felder:** Wenn Ihr Shop mehrsprachig ist, können Sie für jede Sprache unterschiedliche Namen und Beschreibungen angeben.
  - **Icon bearbeiten:** Klicken Sie auf die Schaltfläche „Bearbeiten“ neben einem vorhandenen Icon in der Liste, um dessen Details zu ändern.
  - **Icon löschen:** Klicken Sie auf die Schaltfläche „Löschen“, um ein Icon zu entfernen. Seien Sie vorsichtig, da dies auch seine Zuordnungen zu allen Produkten entfernt.
  - **Raster- / Verwaltungsansicht:** Eine Tabelle, die alle Ihre erstellten Icons auflistet und deren Namen, Bild, Beschreibung und aktiven Status anzeigt. Sie können diese Liste sortieren und filtern.
- **Auswirkung von Änderungen:**
  - **Hinzufügen eines Icons:** Macht ein neues Icon zur Zuordnung mit Produkten verfügbar.
  - **Bearbeiten eines Icons:** Aktualisiert das Bild, den Namen oder die Beschreibung für alle Instanzen dieses Icons in Ihrem Shop.
  - **Löschen eines Icons:** Entfernt das Icon vollständig und es wird nicht mehr auf Produkten angezeigt, denen es zuvor zugewiesen war.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Planen Sie Ihre Icons: Entscheiden Sie, welche wichtigen Merkmale oder Aktionen Sie hervorheben möchten.
  2. Erstellen Sie hochwertige, kleine Icon-Bilder (z. B. 32x32px oder 64x64px), die zu Ihrer Marke passen.
  3. Gehen Sie zu „Alle Icons verwalten“ und fügen Sie jedes Icon hinzu, indem Sie einen klaren Namen und eine hilfreiche Tooltip-Beschreibung angeben.
  4. Stellen Sie sicher, dass alle Icons „Aktiv“ sind, wenn Sie sie verwenden möchten.

### 2.3 Dedizierter Admin-Bildschirm: Icon-Zuordnungen verwalten (Back Office > Product Tag Icons Pro > Icon-Zuordnungen verwalten)

Auf diesem Bildschirm verknüpfen Sie Ihre erstellten Icons mit bestimmten Produkten in Ihrem Katalog.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Product Tag Icons Pro > Icon-Zuordnungen verwalten** in Ihrem PrestaShop Back Office Menü.
- **Verfügbare Aktionen & Einstellungen:**
  - **Produktsuche:** Verwenden Sie die Suchleiste, um Produkte nach Namen, ID oder Referenz zu finden.
  - **Produktliste:** Sobald Sie nach Produkten gesucht haben, werden diese in einer Liste angezeigt.
  - **Icons zuweisen:** Für jedes Produkt sehen Sie einen Bereich, in dem Sie auswählen können, welche Ihrer erstellten Icons für dieses spezifische Produkt angezeigt werden sollen. Dies ist normalerweise ein Mehrfachauswahl-Dropdown oder eine Liste von Kontrollkästchen.
  - **Änderungen speichern:** Nachdem Sie Icons für ein Produkt zugewiesen oder entfernt haben, denken Sie daran, Ihre Änderungen zu speichern.
  - **Raster- / Verwaltungsansicht:** Eine Tabelle, die Produkte und ihre aktuell zugeordneten Icons anzeigt.
- **Auswirkung von Änderungen:**
  - **Zuweisen eines Icons zu einem Produkt:** Das ausgewählte Icon wird nun im Front Office für dieses spezifische Produkt angezeigt (auf seiner Produktseite und in Produktlisten, abhängig von Ihren Hauptmoduleinstellungen).
  - **Entfernen eines Icons von einem Produkt:** Das Icon wird für dieses Produkt nicht mehr angezeigt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Nachdem Sie Ihre Icons erstellt haben (unter „Alle Icons verwalten“), rufen Sie diesen Bildschirm auf.
  2. Suchen Sie nach dem Produkt, das Sie taggen möchten.
  3. Wählen Sie die relevanten Icons aus der Liste für dieses Produkt aus.
  4. Wiederholen Sie dies für alle Produkte, die Sie taggen möchten.
  5. Überprüfen Sie regelmäßig Ihre Produkt-Tags, insbesondere beim Start neuer Produkte oder Aktionen.

### 2.4 Konfigurations-Kurzübersichtstabelle (Alle Bildschirme)

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|
| **Modulkonfiguration** | Modul aktivieren | JA | Schaltet das Modul ein/aus. |
| | Icon-Größe (px) | 32 | Legt die Standardanzeigegröße des Icons fest. |
| | Icon-Position (Hook) | `displayProductAdditionalInfo` | Standardplatzierung auf der Produktseite. |
| | Icons auf Produktliste anzeigen | JA | Zeigt Icons auf Kategorie-/Suchseiten an. |
| | Tooltip-Typ | Light | Visuelles Thema für Icon-Beschreibungen. |
| | Tooltip-Position | Oben | Wo der Tooltip relativ zum Icon erscheint. |
| | Tooltip-Animationen aktivieren | JA | Sanfte Animationen für Tooltips. |
| | Benutzerdefiniertes CSS | (Leer) | Fügt benutzerdefiniertes Styling für Icons/Tooltips hinzu. |
| **Alle Icons verwalten** | Neues Icon hinzufügen | N/A | Erstellt eine neue Icon-Definition. |
| | Icon-Name | (Beschreibend) | Interner Name für das Icon. |
| | Icon-Bild | (Datei hochladen) | Visuelle Darstellung des Icons. |
| | Icon-Beschreibung | (Tooltip-Text) | Text, der beim Hovern angezeigt wird. |
| | Aktiv | JA | Aktiviert/deaktiviert das Icon zur Verwendung. |
| | Icon bearbeiten | N/A | Ändert vorhandene Icon-Details. |
| | Icon löschen | N/A | Entfernt eine Icon-Definition. |
| **Icon-Zuordnungen verwalten** | Produktsuche | N/A | Findet Produkte zum Taggen. |
| | Icons zuweisen | N/A | Verknüpft erstellte Icons mit bestimmten Produkten. |
| | Änderungen speichern | N/A | Wendet Icon-Zuordnungen auf Produkte an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Icons werden im Front Office nicht angezeigt, was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Product Tag Icons Pro“ aktiviert ist.
2. **Icon-Status überprüfen:** Gehen Sie zu **Product Tag Icons Pro > Alle Icons verwalten** und überprüfen Sie, ob die spezifischen Icons, die Sie anzeigen möchten, als „Aktiv“ markiert sind.
3. **Produktzuordnungen überprüfen:** Gehen Sie zu **Product Tag Icons Pro > Icon-Zuordnungen verwalten** und bestätigen Sie, dass die Icons den Produkten, auf denen sie erscheinen sollen, korrekt zugewiesen sind.
4. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Smarty-Cache leeren“ und „Cache leeren“ (falls verfügbar). Manchmal verhindern alte Cache-Daten, dass neue Moduländerungen angezeigt werden.
5. **Hook-Position überprüfen:** Stellen Sie in der Hauptmodulkonfiguration sicher, dass Sie einen gültigen und geeigneten Hook für die Icon-Anzeige ausgewählt haben (z. B. `displayProductAdditionalInfo`). Einige Themes haben möglicherweise benutzerdefinierte Hooks oder rendern bestimmte Standard-Hooks nicht.

**F2: Die Icons sehen zu groß/klein aus oder passen nicht zum Design meines Themes.**
A:

1. **Icon-Größe anpassen:** Ändern Sie in der Hauptmodulkonfiguration die Einstellung „Icon-Größe (px)“ auf Ihre gewünschten Abmessungen.
2. **Benutzerdefiniertes CSS:** Wenn eine einfache Größenanpassung nicht ausreicht, verwenden Sie das Feld „Benutzerdefiniertes CSS“ in der Hauptmodulkonfiguration, um das Styling zu verfeinern. Sie können spezifische Icon-Klassen (z. B. `.ticon-image`) ansprechen, um Ränder, Abstände oder sogar Filter anzupassen.
3. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, erfordern einige stark angepasste Themes möglicherweise geringfügige CSS-Anpassungen. Wenn Sie mit CSS vertraut sind, untersuchen Sie die Elemente mit den Entwicklertools Ihres Browsers, um die relevanten Selektoren zu identifizieren.

**F3: Die Tooltips werden nicht angezeigt oder sehen seltsam aus.**
A:

1. **Tooltips aktivieren:** Stellen Sie sicher, dass die Tooltip-Funktion in der Hauptmodulkonfiguration aktiviert ist.
2. **Tooltip-Inhalt überprüfen:** Vergewissern Sie sich, dass Sie für jedes Icon unter **Product Tag Icons Pro > Alle Icons verwalten** eine „Beschreibung“ eingegeben haben. Diese Beschreibung ist das, was im Tooltip erscheint.
3. **Tooltip-Theme/Position:** Experimentieren Sie mit verschiedenen Einstellungen für „Tooltip-Typ“ und „Tooltip-Position“ in der Hauptmodulkonfiguration, um zu sehen, ob eine andere Option das Problem löst oder besser zu Ihrem Theme passt.
4. **JavaScript-Konflikte:** In seltenen Fällen kann das JavaScript eines anderen Moduls Konflikte verursachen. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler. Wenn Sie Fehler finden, versuchen Sie, andere Module nacheinander vorübergehend zu deaktivieren, um den Konflikt zu isolieren.

**F4: Kann ich die Icon-Namen und Beschreibungen für verschiedene Sprachen übersetzen?**
A: Ja! Wenn Sie ein Icon unter **Product Tag Icons Pro > Alle Icons verwalten** erstellen oder bearbeiten, sehen Sie neben den Feldern „Icon-Name“ und „Icon-Beschreibung“ Sprachregisterkarten (z. B. „Deutsch“, „Englisch“, „Französisch“). Wechseln Sie einfach zur gewünschten Sprachregisterkarte und geben Sie die Übersetzung für diese spezifische Sprache ein. Das Modul zeigt automatisch die korrekte Übersetzung basierend auf der vom Kunden ausgewählten Sprache an.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Product Tag Icons Pro“, der für Entwickler, Webmaster und technische Agenturen gedacht ist.

### 4.1 Architekturübersicht

Das Modul „Product Tag Icons Pro“ (`ticons`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich das MVC-Muster nutzt. Es erweitert `Module` für seine Kernfunktionalität und verwendet dedizierte `AdminController`-Instanzen zur Verwaltung von Icons und deren Zuordnungen. Daten werden in benutzerdefinierten Datenbanktabellen gespeichert, und die Front-Office-Anzeige wird durch verschiedene PrestaShop-Hooks und Smarty-Templates erreicht. Das Modul integriert auch Drittanbieterbibliotheken für eine verbesserte Benutzeroberfläche (z. B. Tooltipster für Tooltips, eine benutzerdefinierte Autovervollständigung für die Produktsuche).

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Dieses Modul definiert keine expliziten benutzerdefinierten Front-Office-Controller. Die gesamte Front-Office-Darstellung wird über `hook`-Methoden innerhalb der Hauptmodulklasse (`ajax_ticons.php`) und zugehörige Smarty-Templates gehandhabt.

#### Back-Office-Admin-Controller

- **`ticons/controllers/admin/AdminTiconsAllController.php`**

  - **Klassenname:** `AdminTiconsAllController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** „Alle Icons verwalten“
  - **Verantwortlichkeit:** Verwaltet die Erstellung, Bearbeitung und Löschung einzelner Icon-Definitionen. Es handhabt die CRUD-Operationen für die Entität `ticon`. Dieser Controller verwendet `HelperList` zur Anzeige der Icon-Liste und `HelperForm` für das Hinzufügen/Bearbeiten-Formular. Er verwaltet Icon-Bild-Uploads.
- **`ticons/controllers/admin/AdminTiconsAssociationsController.php`**

  - **Klassenname:** `AdminTiconsAssociationsController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** „Icon-Zuordnungen verwalten“
  - **Verantwortlichkeit:** Verwaltet die Zuordnung von erstellten Icons zu bestimmten Produkten. Es bietet eine Schnittstelle zum Suchen von Produkten und zum Zuweisen/Entfernen mehrerer Icons zu diesen. Dieser Controller verwendet ebenfalls `HelperList` für die Produktanzeige und ein benutzerdefiniertes Formular für die Icon-Auswahl. Er handhabt AJAX-Anfragen für die Produktsuche-Autovervollständigung.
- **`ticons/controllers/admin/index.php`**

  - **Verantwortlichkeit:** Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in PrestaShop-Verzeichnissen vorhanden ist, um die Verzeichnisauflistung zu verhindern. Sie enthält keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine expliziten separaten PHP-Dateien in einem `classes/`-Verzeichnis. Stattdessen enthält die Hauptmoduldatei `ajax_ticons.php` wahrscheinlich die `ObjectModel`-Definitionen für `Ticon` und `TiconProduct` (oder ähnliche Entitäten) direkt in ihrem Umfang, oder sie werden implizit über Datenbankinteraktionen gehandhabt.

- **`Ticon` (Implizites ObjectModel):**

  - **Datenbanktabelle:** `ps_ticons` (oder ähnlich, basierend auf der `install()`-Methode des Moduls).
  - **Felder:** Wahrscheinlich `id_ticon`, `name` (mehrsprachig), `description` (mehrsprachig), `image`, `active`.
  - **Zweck:** Repräsentiert eine einzelne Icon-Definition, einschließlich ihres Bildes, Namens und der Tooltip-Beschreibung.
- **`TiconProduct` (Implizites ObjectModel):**

  - **Datenbanktabelle:** `ps_ticon_products` (oder ähnlich, basierend auf der `install()`-Methode des Moduls).
  - **Felder:** Wahrscheinlich `id_ticon_product`, `id_ticon`, `id_product`.
  - **Zweck:** Repräsentiert die Many-to-Many-Beziehung zwischen Icons und Produkten.

### 4.4 JavaScript-Assets (`views/js/`)

- **`ticons/lib/searchTool/views/js/autocomplete.js`**

  - **Geltungsbereich:** Back-Office (AdminTiconsAssociationsController).
  - **Funktionalität:** Bietet eine Autovervollständigungs-Suchfunktion für Produkte innerhalb des Bildschirms „Icon-Zuordnungen verwalten“. Es sendet wahrscheinlich AJAX-Anfragen an den Admin-Controller, um Produktvorschläge abzurufen, während der Benutzer tippt.
- **`ticons/lib/tooltipster/js/jquery.tooltipster.js`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Dies ist die Kernbibliothek für das Tooltipster-Plugin. Sie handhabt die Erstellung, Positionierung und das Styling der interaktiven Tooltips, die erscheinen, wenn Benutzer mit der Maus über Produkt-Icons fahren. Sie bindet Hover-Ereignisse an Elemente mit spezifischen Klassen (z. B. `.tooltipster`).
- **`ticons/views/js/ticons-front.js`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Enthält benutzerdefiniertes JavaScript speziell für die Front-Office-Anzeige von Icons. Dieses Skript initialisiert wahrscheinlich das Tooltipster-Plugin auf den relevanten Icon-Elementen und übergibt Konfigurationsoptionen (Theme, Position, Animation) basierend auf den Back-Office-Einstellungen des Moduls. Es stellt sicher, dass Icons korrekt gerendert und interaktiv sind.
- **`ticons/views/js/ticons.js`**

  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Enthält allgemeines JavaScript für die Back-Office-Konfiguration und Verwaltungsbildschirme des Moduls. Dies kann Formularvalidierung, dynamische Elementmanipulation oder andere UI-Verbesserungen für die Admin-Oberfläche umfassen.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`ticons/lib/searchTool/views/css/autocomplete.css`**

  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Gestaltet das Autovervollständigungs-Dropdown und das Eingabefeld, die im Bildschirm „Icon-Zuordnungen verwalten“ verwendet werden.
- **`ticons/lib/tooltipster/css/themes/tooltipster-light.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Definiert die Stile für das „Light“-Theme des Tooltipster-Plugins.
- **`ticons/lib/tooltipster/css/themes/tooltipster-noir.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Definiert die Stile für das „Noir“-Theme des Tooltipster-Plugins.
- **`ticons/lib/tooltipster/css/themes/tooltipster-punk.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Definiert die Stile für das „Punk“-Theme des Tooltipster-Plugins.
- **`ticons/lib/tooltipster/css/themes/tooltipster-shadow.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Definiert die Stile für das „Shadow“-Theme des Tooltipster-Plugins.
- **`ticons/lib/tooltipster/css/tooltipster.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Das Kern-CSS für das Tooltipster-Plugin, das Basisstile für alle Tooltips bereitstellt.
- **`ticons/views/css/ticons-admin.css`**

  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Enthält benutzerdefiniertes CSS speziell für die Back-Office-Oberflächen des Moduls (z. B. Styling für Icon-Listen, Formulare und benutzerdefinierte Elemente in den Admin-Controllern).
- **`ticons/views/css/ticons-fontawesome.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Enthält oder importiert wahrscheinlich Font Awesome-Icons, die als Fallback-Icons oder für spezifische UI-Elemente innerhalb der Modulanzeige verwendet werden könnten.
- **`ticons/views/css/ticons-front-24.css`**, **`ticons/views/css/ticons-front-32.css`**, **`ticons/views/css/ticons-front-48.css`**, **`ticons/views/css/ticons-front-64.css`**, **`ticons/views/css/ticons-front-74.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Diese Stylesheets enthalten wahrscheinlich spezifische Regeln für verschiedene Icon-Größen. Wenn der Händler in der Konfiguration eine „Icon-Größe“ auswählt, lädt das Modul dynamisch die entsprechende CSS-Datei, um sicherzustellen, dass die Icons in den richtigen Abmessungen und möglicherweise mit optimiertem Abstand gerendert werden. Sie definieren Klassen wie `.ticon-24`, `.ticon-32` usw.
- **`ticons/views/css/ticons.css`**

  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Allgemeines Front-Office-CSS für das Modul, einschließlich Basisstilen für die Icon-Container, Bilder und das Gesamtlayout. Diese Datei könnte gemeinsame Regeln enthalten, die unabhängig von der ausgewählten Icon-Größe angewendet werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/front/`)

Diese Templates werden gerendert, wenn das Modul in verschiedene Front-Office-Positionen eingehängt wird. Sie erhalten typischerweise ein Array von Icon-Daten von den `hook`-Methoden des Moduls.

- **`ticons/views/templates/front/deliveryTime.tpl`**

  - **Hook:** Potenziell `displayProductDeliveryTime` oder ähnlich.
  - **Ausgabe:** Rendert Icons, die sich auf Lieferinformationen beziehen.
- **`ticons/views/templates/front/displayActions.tpl`**

  - **Hook:** `displayProductActions` oder ähnlich.
  - **Ausgabe:** Rendert Icons in der Nähe von Produktaktionsschaltflächen (z. B. „In den Warenkorb“).
- **`ticons/views/templates/front/displayAfterProductThumbs.tpl`**

  - **Hook:** `displayAfterProductThumbs` (PrestaShop 1.7+).
  - **Ausgabe:** Rendert Icons direkt unter den Produktminiaturansichten auf der Produktseite.
- **`ticons/views/templates/front/displayColumns.tpl`**

  - **Hook:** `displayLeftColumn`, `displayRightColumn`.
  - **Ausgabe:** Rendert Icons innerhalb der linken oder rechten Spaltenmodule.
- **`ticons/views/templates/front/displayLeftColumn.tpl`**

  - **Hook:** `displayLeftColumn`.
  - **Ausgabe:** Rendert Icons speziell in der linken Spalte.
- **`ticons/views/templates/front/displayProductAdditionalInfo.tpl`**

  - **Hook:** `displayProductAdditionalInfo` (PrestaShop 1.7+).
  - **Ausgabe:** Rendert Icons im Abschnitt „Zusätzliche Informationen“ der Produktseite, eine gängige und empfohlene Platzierung.
- **`ticons/views/templates/front/displayProductPriceBlock.tpl`**

  - **Hook:** `displayProductPriceBlock`.
  - **Ausgabe:** Rendert Icons in der Nähe des Preisblocks des Produkts.
- **`ticons/views/templates/front/displayTop.tpl`**

  - **Hook:** `displayTop` (Header).
  - **Ausgabe:** Rendert Icons im Header-Bereich des Shops.
- **`ticons/views/templates/front/listReviews.tpl`**

  - **Hook:** Potenziell `displayProductListReviews` oder ähnlich.
  - **Ausgabe:** Rendert Icons, die sich auf Produktbewertungen oder -ratings beziehen.
- **`ticons/views/templates/front/productFooter.tpl`**

  - **Hook:** `displayFooterProduct` oder ähnlich.
  - **Ausgabe:** Rendert Icons im Footer-Bereich der Produktseite.
- **`ticons/views/templates/front/showIcons.tpl`**

  - **Hook:** Dies ist wahrscheinlich ein generisches Template, das von anderen Hook-Templates eingebunden wird, um die eigentliche Icon-HTML-Struktur (z. B. `<img>`-Tags mit `tooltipster`-Klassen) zu rendern. Es iteriert über die übergebene Variable `$icons`.

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden für die Back-Office-Konfiguration und Verwaltungsbildschirme des Moduls verwendet.

- **`ticons/lib/searchTool/views/scripts.tpl`**

  - **Geltungsbereich:** Back-Office.
  - **Ausgabe:** Enthält JavaScript für das Suchwerkzeug, wahrscheinlich einschließlich jQuery UI Autocomplete-Initialisierung oder ähnliches.
- **`ticons/views/templates/admin/customHook.tpl`**

  - **Geltungsbereich:** Back-Office.
  - **Ausgabe:** Ein generisches Template, das verwendet werden könnte, um Inhalte für benutzerdefinierte Hooks innerhalb der Admin-Oberfläche des Moduls oder zur Anzeige spezifischer Nachrichten zu rendern.
- **`ticons/views/templates/admin/tabs.tpl`**

  - **Geltungsbereich:** Back-Office.
  - **Ausgabe:** Rendert die Navigationsregisterkarten (z. B. „Alle Icons verwalten“, „Icon-Zuordnungen verwalten“) für die Konfigurationsseiten des Moduls.
- **`ticons/views/templates/admin/ticonsSelection.tpl`**

  - **Geltungsbereich:** Back-Office (AdminTiconsAssociationsController).
  - **Ausgabe:** Rendert die Oberfläche zum Auswählen und Zuweisen von Icons zu einem Produkt, typischerweise ein Mehrfachauswahl-Dropdown oder eine Liste von Kontrollkästchen innerhalb des Produktzuordnungsformulars.
- **`ticons/views/templates/admin/ticons_all/helpers/list/list_content.tpl`**

  - **Geltungsbereich:** Back-Office (AdminTiconsAllController).
  - **Ausgabe:** Passt den Inhalt der `HelperList`-Tabelle zur Anzeige der Liste aller erstellten Icons an. Es könnte benutzerdefinierte Spalten für Icon-Bilder oder den aktiven Status enthalten.
- **`ticons/views/templates/admin/ticons_associations/helpers/form/form.tpl`**

  - **Geltungsbereich:** Back-Office (AdminTiconsAssociationsController).
  - **Ausgabe:** Passt das `HelperForm` für den Produktzuordnungsbildschirm an. Dieses Template enthält wahrscheinlich das Produktsuchfeld und das `ticonsSelection.tpl` für die Icon-Zuweisung.
- **`ticons/views/templates/admin/ticons_associations/helpers/list/list_content.tpl`**

  - **Geltungsbereich:** Back-Office (AdminTiconsAssociationsController).
  - **Ausgabe:** Passt den Inhalt der `HelperList`-Tabelle zur Anzeige der Liste der Produkte und ihrer zugeordneten Icons an.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt während seiner `install()`-Methode benutzerdefinierte Tabellen, um Icon-Definitionen und deren Zuordnungen zu speichern:

- **`ps_ticons`**: Speichert die Haupt-Icon-Definitionen.
  - `id_ticon` (PK, INT)
  - `image` (VARCHAR): Dateiname des Icon-Bildes.
  - `active` (TINYINT): 1, wenn aktiv, 0, wenn inaktiv.
- **`ps_ticons_lang`**: Speichert mehrsprachige Felder für Icons.
  - `id_ticon` (PK, INT)
  - `id_lang` (PK, INT)
  - `name` (VARCHAR): Icon-Name für den internen Gebrauch.
  - `description` (TEXT): Tooltip-Text für das Icon.
- **`ps_ticon_products`**: Speichert die Many-to-Many-Beziehung zwischen Icons und Produkten.
  - `id_ticon_product` (PK, INT)
  - `id_ticon` (FK, INT)
  - `id_product` (FK, INT)

Konfigurationseinstellungen werden in `ps_configuration` mit Schlüsseln wie `TICONS_ICON_SIZE`, `TICONS_HOOK_POSITION`, `TICONS_SHOW_IN_LIST` usw. gespeichert.

#### Registrierte Hooks-Tabelle

Das Modul registriert mehrere Hooks, um Icons im Front Office anzuzeigen. Die genauen verwendeten Hooks hängen von der PrestaShop-Version und der Konfiguration des Händlers ab.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Reiht CSS- und JS-Assets ein (Tooltipster, benutzerdefiniertes JS/CSS). |
| `displayProductAdditionalInfo` | Auf der Produktseite, innerhalb des Blocks „Zusätzliche Informationen“ (PS 1.7+). | Rendert Icons, die dem aktuellen Produkt zugeordnet sind. |
| `displayProductPriceBlock` | Auf der Produktseite, in der Nähe des Preises. | Rendert Icons, die dem aktuellen Produkt zugeordnet sind. |
| `displayAfterProductThumbs` | Auf der Produktseite, unter den Produktbildern (PS 1.7+). | Rendert Icons, die dem aktuellen Produkt zugeordnet sind. |
| `displayProductListFunctionalButtons` | Auf Produktlistenelementen (z. B. Kategorieseiten). | Rendert Icons auf Produktkarten/Miniaturen. |
| `displayProductListReviews` | Auf Produktlistenelementen, in der Nähe von Bewertungen. | Rendert Icons auf Produktkarten/Miniaturen. |
| `displayProductDeliveryTime` | Auf der Produktseite, in der Nähe der Lieferinformationen. | Rendert Icons, die dem aktuellen Produkt zugeordnet sind. |
| `displayLeftColumn` | In der linken Spalte von Seiten. | Rendert Icons, wenn für die allgemeine Anzeige konfiguriert. |
| `displayRightColumn` | In der rechten Spalte von Seiten. | Rendert Icons, wenn für die allgemeine Anzeige konfiguriert. |
| `displayFooterProduct` | Am unteren Rand der Produktseite. | Rendert Icons, die dem aktuellen Produkt zugeordnet sind. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Löscht möglicherweise den Cache oder aktualisiert Icon-Zuordnungen. |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Bereinigt zugehörige Icon-Einträge aus `ps_ticon_products`. |
| `actionObjectLanguageAddAfter` | Nach dem Hinzufügen einer neuen Sprache. | Stellt sicher, dass sprachspezifische Felder für Icons behandelt werden. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Product Tag Icons Pro“ gerne zur Verfügung.
