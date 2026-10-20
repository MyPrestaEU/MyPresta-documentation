---
title: "Benutzerdefiniertes Inhalte-Karussell – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Benutzerdefiniertes Inhalte-Karussell“ von MyPresta.eu."
sidebar:
  label: "Benutzerdefiniertes Inhalte-Karussell – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Custom contents carousel auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/custom-contents-carousel.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/custom-contents-carousel/)
>
> ---


# Benutzerdefiniertes Inhalte-Karussell

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind in der Regel keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Benutzerdefiniertes Inhalte-Karussell“ organisiert seine Einstellungen über mehrere Bildschirme in Ihrem PrestaShop Back Office. Sie konfigurieren zuerst globale Einstellungen, erstellen dann „Gruppen“ (Ihre Karussells) und fügen schließlich „Elemente“ (die einzelnen Slides) zu jeder Gruppe hinzu.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Benutzerdefiniertes Inhalte-Karussell)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager zugänglich ist.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm verwaltet hauptsächlich allgemeine Moduleinstellungen und Update-Prüfungen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - `mypresta_updates`, `update_`, `updatev_`: Dies sind interne Einstellungen, die von MyPresta.eu-Modulen zur Verwaltung von Updates und Versionsprüfungen verwendet werden. Sie beeinflussen die Front-Office-Anzeige nicht direkt, stellen aber sicher, dass Ihr Modul auf dem neuesten Stand bleibt.
  - `CCAROUSEL_LIGHTSLIDER`: Diese Einstellung steuert wahrscheinlich die Aktivierung der LightSlider JavaScript-Bibliothek, die die Karussellfunktionalität antreibt.
    - *Wenn aktiviert (JA)*: Die LightSlider-Bibliothek wird in Ihrem Front Office geladen, sodass Karussells korrekt funktionieren.
    - *Wenn deaktiviert (NEIN)*: Die LightSlider-Bibliothek wird möglicherweise nicht geladen, was die Karussellanzeige und -funktionalität potenziell beeinträchtigt.
- **Empfohlener Wert:**
  - `CCAROUSEL_LIGHTSLIDER`: **JA** (Aktiviert). Dies ist entscheidend für die Funktion des Karussells.
  - Andere Einstellungen: Als Standard belassen.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten sicherstellen, dass alle notwendigen Skripte geladen werden. Sie würden überprüfen, ob `CCAROUSEL_LIGHTSLIDER` aktiviert ist. Wenn Sie jemals Probleme haben, dass das Karussell nicht gleitet, wäre dies eine der ersten Stellen, die Sie überprüfen sollten.

### 2.2 Dedizierter Admin-Bildschirm: Benutzerdefinierte Inhaltsgruppen (Back Office > Module > Benutzerdefiniertes Inhalte-Karussell > Benutzerdefinierte Inhaltsgruppen)

Dieser Bildschirm ermöglicht es Ihnen, Ihre individuellen Karussells zu erstellen und zu verwalten. Jede „Gruppe“ repräsentiert ein eigenständiges Karussell, das Sie dann mit Slides füllen können.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Module > Benutzerdefiniertes Inhalte-Karussell > Benutzerdefinierte Inhaltsgruppen** in Ihrem PrestaShop Back Office-Menü.
- **Verfügbare Aktionen & Einstellungen:**
  - **Rasteransicht**: Zeigt eine Liste aller Ihrer bestehenden Karussellgruppen an. Sie können deren Namen, Status (aktiv/inaktiv) und Aktionen sehen.
  - **Neue Gruppe hinzufügen**: Klicken Sie auf die Schaltfläche „Neu hinzufügen“, um ein brandneues Karussell zu erstellen.
  - **Gruppe bearbeiten/löschen**: Für jede Gruppe haben Sie Optionen, um deren Einstellungen (z.B. Name, Anzeigeoptionen) zu bearbeiten oder sie vollständig zu löschen.
  - **Status umschalten**: Aktivieren oder deaktivieren Sie eine Karussellgruppe schnell, ohne sie zu löschen. Eine inaktive Gruppe wird nicht in Ihrem Front Office angezeigt.
- **Auswirkung von Änderungen:**
  - **Hinzufügen einer neuen Gruppe**: Erstellt einen neuen, leeren Karussell-Container. Sie müssen dann Elemente (Slides) hinzufügen.
  - **Bearbeiten einer Gruppe**: Ermöglicht Ihnen, den Namen des Karussells, seine Anzeigeeinstellungen (z.B. Auto-Play, Geschwindigkeit, Anzahl der sichtbaren Slides) und seine Position zu ändern.
  - **Aktivieren/Deaktivieren**: Steuert, ob das Karussell für Ihre Kunden im Front Office sichtbar ist.
  - **Löschen einer Gruppe**: Entfernt das Karussell und alle zugehörigen Elemente (Slides) dauerhaft.
- **Empfohlener Workflow für die tägliche Store-Verwaltung:**
  1. Beginnen Sie mit der Erstellung einer neuen Gruppe für jedes Karussell, das Sie anzeigen möchten (z.B. „Startseiten-Banner-Karussell“, „Neuheiten-Slider“).
  2. Geben Sie jeder Gruppe einen klaren, beschreibenden Namen.
  3. Konfigurieren Sie die Anzeigeeinstellungen der Gruppe (z.B. Auto-Play, Schleife, Pause bei Hover), um das gewünschte Benutzererlebnis zu erzielen.
  4. Sobald die Gruppe erstellt ist, fahren Sie mit dem Bildschirm „Benutzerdefinierte Inhaltselemente“ fort, um Slides hinzuzufügen.

### 2.3 Dedizierter Admin-Bildschirm: Benutzerdefinierte Inhaltselemente (Back Office > Module > Benutzerdefiniertes Inhalte-Karussell > Benutzerdefinierte Inhaltselemente)

Dieser Bildschirm ist der Ort, an dem Sie die einzelnen Slides (Elemente) innerhalb Ihrer Karussells verwalten. Jedes Element kann ein Bild, Video, Text oder eingebetteter Inhalt sein.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Module > Benutzerdefiniertes Inhalte-Karussell > Benutzerdefinierte Inhaltselemente** in Ihrem PrestaShop Back Office-Menü.
- **Verfügbare Aktionen & Einstellungen:**
  - **Rasteransicht**: Listet alle einzelnen Slides auf und zeigt, zu welcher Gruppe sie gehören, ihren Inhaltstyp und Status.
  - **Neues Element hinzufügen**: Klicken Sie auf „Neu hinzufügen“, um eine neue Slide zu erstellen. Sie wählen dann die Gruppe aus, zu der sie gehört, und definieren ihren Inhalt.
  - **Element bearbeiten/löschen**: Ändern Sie den Inhalt, den Link oder die Anzeigereihenfolge einer bestehenden Slide oder entfernen Sie sie.
  - **Status umschalten**: Aktivieren oder deaktivieren Sie einzelne Slides. Eine inaktive Slide wird nicht in ihrem Karussell angezeigt.
  - **Drag-and-Drop-Neuanordnung**: Ändern Sie einfach die Anzeigereihenfolge der Slides innerhalb einer Gruppe.
- **Auswirkung von Änderungen:**
  - **Hinzufügen eines neuen Elements**: Erstellt eine neue Slide. Sie geben ihren Inhalt (Bild-Upload, Video-URL, Text, HTML), einen Link an und weisen sie einer Ihrer bestehenden Karussellgruppen zu.
  - **Bearbeiten eines Elements**: Ermöglicht Ihnen, den Inhalt zu aktualisieren, den Link zu ändern, das Bild zu modifizieren oder seine Position innerhalb des Karussells anzupassen.
  - **Aktivieren/Deaktivieren**: Steuert, ob eine bestimmte Slide innerhalb ihres Karussells sichtbar ist.
  - **Löschen eines Elements**: Entfernt die Slide dauerhaft aus ihrem Karussell.
- **Empfohlener Workflow für die tägliche Store-Verwaltung:**
  1. Wählen Sie die Karussellgruppe aus, der Sie Slides hinzufügen möchten (falls Sie mehrere haben).
  2. Klicken Sie auf „Neues Element hinzufügen“ und wählen Sie den Inhaltstyp (Bild, Video, Text, HTML).
  3. Laden Sie Ihr Bild hoch, fügen Sie Ihre Video-URL ein oder geben Sie Ihren Text/HTML ein.
  4. Fügen Sie einen relevanten Link hinzu, wenn die Slide Kunden zu einem Produkt, einer Kategorie oder einer externen Seite leiten soll.
  5. Legen Sie die Anzeigereihenfolge fest.
  6. Wiederholen Sie dies für alle Slides in Ihrem Karussell.
  7. Verwenden Sie die Drag-and-Drop-Funktion, um die Reihenfolge Ihrer Slides zu optimieren.

### 2.4 Dedizierter Admin-Bildschirm: index.php (ccarousel/controllers/admin/index.php)

Diese Datei ist eine Standard-PrestaShop-Praxis zur Sicherung von Admin-Verzeichnissen. Sie enthält typischerweise eine einfache `die('No direct script access allowed');`-Anweisung und stellt selbst keinen konfigurierbaren Bildschirm oder eine verwaltete Entität dar. Es ist eine Sicherheitsmaßnahme, keine Konfigurationsschnittstelle.

### 2.5 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | `CCAROUSEL_LIGHTSLIDER` | JA | Aktiviert/deaktiviert die Kern-JavaScript-Bibliothek für die Karussellfunktionalität. **Muss auf JA stehen, damit Karussells funktionieren.** |
| Benutzerdefinierte Inhaltsgruppen | Gruppenname | Benutzerdefiniert | Identifiziert Ihr Karussell (z.B. „Startseiten-Banner“). |
| Benutzerdefinierte Inhaltsgruppen | Status | Aktiviert | Steuert die Sichtbarkeit des gesamten Karussells im Front Office. |
| Benutzerdefinierte Inhaltsgruppen | Karussell-Einstellungen | Benutzerdefiniert | Steuert Auto-Play, Geschwindigkeit, Schleife, Navigation usw. für jedes Karussell. |
| Benutzerdefinierte Inhaltselemente | Elementinhalt | Benutzerdefiniert | Der tatsächliche Inhalt der Slide (Bild, Video, Text, HTML). |
| Benutzerdefinierte Inhaltselemente | Element-Link | Optionale URL | Wohin die Slide Kunden beim Klicken leitet. |
| Benutzerdefinierte Inhaltselemente | Status | Aktiviert | Steuert die Sichtbarkeit einzelner Slides innerhalb eines Karussells. |
| Benutzerdefinierte Inhaltselemente | Position | Benutzerdefiniert | Bestimmt die Reihenfolge der Slides innerhalb eines Karussells. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Karussell wird nicht auf der Startseite angezeigt.**

- **A:** Überprüfen Sie zunächst, ob das Modul „Benutzerdefiniertes Inhalte-Karussell“ unter **Module > Modul-Manager** aktiviert ist. Navigieren Sie dann zu **Module > Benutzerdefiniertes Inhalte-Karussell > Benutzerdefinierte Inhaltsgruppen** und stellen Sie sicher, dass Ihre Karussellgruppe aktiv ist (grünes Häkchen). Stellen Sie schließlich sicher, dass mindestens ein aktives „Benutzerdefiniertes Inhaltselement“ dieser Gruppe zugewiesen ist. Überprüfen Sie auch, ob die Einstellung `CCAROUSEL_LIGHTSLIDER` auf der Hauptkonfigurationsseite des Moduls aktiviert ist.

**F2: Meine Karussellbilder sind unscharf oder verzerrt.**

- **A:** Stellen Sie sicher, dass die von Ihnen hochgeladenen Bilder von hoher Qualität und den Abmessungen des Bereichs, in dem das Karussell angezeigt wird, entsprechen. Wenn Ihr Theme spezifische Bildgrößenempfehlungen für Banner oder Slider hat, versuchen Sie, diese zu berücksichtigen. Das Modul skaliert Bilder, aber ein gutes Ausgangsbild ist entscheidend.

**F3: Das Karussell gleitet nicht oder spielt nicht automatisch ab.**

- **A:** Dies ist oft ein JavaScript-Problem.
  1. Gehen Sie zu **Module > Konfigurieren > Benutzerdefiniertes Inhalte-Karussell** und stellen Sie sicher, dass `CCAROUSEL_LIGHTSLIDER` auf „JA“ gesetzt ist.
  2. Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**).
  3. Leeren Sie den Cache Ihres Browsers.
  4. Wenn das Problem weiterhin besteht, könnte es einen JavaScript-Konflikt mit einem anderen Modul oder Ihrem Theme geben. Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12) auf JavaScript-Fehler.

**F4: Wie ändere ich die Reihenfolge der Slides in meinem Karussell?**

- **A:** Gehen Sie zu **Module > Benutzerdefiniertes Inhalte-Karussell > Benutzerdefinierte Inhaltselemente**. Sie sollten eine Liste Ihrer Slides sehen. Suchen Sie nach einer Spalte mit Pfeilen oder einem Drag-and-Drop-Symbol. Sie können die Zeilen normalerweise per Drag-and-Drop neu anordnen, oder es gibt möglicherweise ein Feld „Position“, das Sie bearbeiten können. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Kann ich mehrere Karussells auf verschiedenen Seiten haben?**

- **A:** Das Modul verwendet hauptsächlich den `displayHome`-Hook, was bedeutet, dass es für die Startseite konzipiert ist. Obwohl Sie mehrere *Gruppen* (Karussells) erstellen können, werden diese typischerweise alle an derselben Hook-Position gerendert. Um Karussells auf verschiedenen Seiten oder an verschiedenen Positionen anzuzeigen, wäre eine benutzerdefinierte Theme-Integration oder eine zusätzliche Hook-Registrierung erforderlich (siehe Entwicklerhandbuch).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die das Modul „Benutzerdefiniertes Inhalte-Karussell“ warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Benutzerdefiniertes Inhalte-Karussell“ folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) für seine Back Office-Komponenten. Es nutzt die PrestaShop-Klasse `Module` für die Kernfunktionalität und `AdminController` für die Verwaltung von Inhaltsgruppen und -elementen. Die Front-Office-Anzeige wird hauptsächlich über ein Smarty-Template gehandhabt, das in `displayHome` eingehängt ist, wobei JavaScript- (LightSlider) und CSS-Assets über `displayHeader` geladen werden. Die Datenpersistenz wird durch benutzerdefinierte `ObjectModel`-Klassen verwaltet.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  Das Modul enthält keine dedizierten Front-Office-Controller. Das gesamte Front-Office-Rendering wird direkt über die Hauptmodulklasse (`ccarousel.php`) durch Registrierung von Hooks und Rendern von Templates gehandhabt.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminCustomContentsGroupsController.php`
    - Klassenname: `AdminCustomContentsGroupsController`
    - Übergeordnete Klasse: `ModuleAdminController`
    - Zuständigkeit: Verwaltet die Entität `gcarousel` (Karussellgruppen). Dieser Controller handhabt das Auflisten, Hinzufügen, Bearbeiten und Löschen von Karussellgruppen. Er definiert die Formularfelder für die Gruppenkonfiguration (z.B. Name, Status, Karussell-Einstellungen wie Auto-Play, Geschwindigkeit).
  - `controllers/admin/AdminCustomContentsItemsController.php`
    - Klassenname: `AdminCustomContentsItemsController`
    - Übergeordnete Klasse: `ModuleAdminController`
    - Zuständigkeit: Verwaltet die Entität `gcitem` (einzelne Karussell-Slides/Elemente). Dieser Controller handhabt das Auflisten, Hinzufügen, Bearbeiten und Löschen von Slides. Er definiert die Formularfelder für den Slide-Inhalt (Bild-Upload, Video-URL, Text/HTML, Link, Position, zugehörige Gruppe). Er verwaltet auch die Drag-and-Drop-Neuanordnungsfunktionalität für Slides.
  - `controllers/admin/index.php`
    - Klassenname: N/A (einfache PHP-Datei)
    - Übergeordnete Klasse: N/A
    - Zuständigkeit: Eine Sicherheitsmaßnahme, um direktes Verzeichnis-Listing oder Zugriff zu verhindern. Enthält `die('No direct script access allowed');`.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass die `ObjectModel`-Definitionen für `gcarousel` und `gcitem` wahrscheinlich direkt in der Hauptmoduldatei (`ccarousel.php`) oder in den jeweiligen `AdminController`-Dateien eingebettet sind.

- **`gcarousel` (Karussellgruppen-Modell)**:

  - Erweitert wahrscheinlich `ObjectModel`.
  - Interagiert mit einer benutzerdefinierten Datenbanktabelle (z.B. `ps_gcarousel`).
  - `$definition`-Felder würden umfassen: `id_gcarousel`, `name`, `active`, `settings` (möglicherweise ein serialisiertes Array oder JSON-String für Karussell-Anzeigeoptionen).
  - Schlüsselmethoden: `add()`, `update()`, `delete()`, `getGroups()`.
- **`gcitem` (Karussell-Element/Slide-Modell)**:

  - Erweitert wahrscheinlich `ObjectModel`.
  - Interagiert mit einer benutzerdefinierten Datenbanktabelle (z.B. `ps_gcitem`).
  - `$definition`-Felder würden umfassen: `id_gcitem`, `id_gcarousel` (Fremdschlüssel), `position`, `active`, `type` (image, video, text, html), `content` (Pfad zum Bild, Video-URL, Text), `link`, `title`, `description` (für Mehrsprachigkeit).
  - Schlüsselmethoden: `add()`, `update()`, `delete()`, `getItemsByGroup()`, `updatePosition()`.

### 4.4 JavaScript-Assets (`views/js/`)

- `ccarousel/lib/src/js/lightslider.js`
  - Geltungsbereich: Front-Office.
  - Zuständigkeit: Dies ist die Kernbibliothek LightSlider. Sie initialisiert und verwaltet die Karussellfunktionalität. Sie bindet Event-Listener für die Navigation (Pfeile, Punkte), handhabt Touch-/Wischgesten, Auto-Play, Looping und responsive Anpassungen. Die Methode `hookDisplayHeader` oder `hookDisplayHome` des Moduls würde dieses Skript typischerweise in die Warteschlange stellen, und dann würde ein Inline-Skript oder eine separate Modul-JS-Datei `$('#your-carousel-selector').lightSlider({...});` aufrufen, um spezifische Karussells zu initialisieren.

### 4.5 CSS-Stylesheets (`views/css/`)

- `ccarousel/css.css`
  - Geltungsbereich: Front-Office.
  - Zuständigkeit: Enthält wahrscheinlich benutzerdefinierte Stile, die spezifisch für das Modul „Benutzerdefiniertes Inhalte-Karussell“ sind und die Basis-LightSlider-Stile überschreiben oder erweitern, um dem Standard-Theme von PrestaShop zu entsprechen oder modulspezifische visuelle Anpassungen bereitzustellen.
- `ccarousel/lib/src/css/ccarousel.css`
  - Geltungsbereich: Front-Office.
  - Zuständigkeit: Könnte ein Basis-Stylesheet für die Struktur des Moduls oder ein Platzhalter sein. Angesichts des Namens handelt es sich wahrscheinlich um modulspezifisches Styling.
- `ccarousel/lib/src/css/lightslider.css`
  - Geltungsbereich: Front-Office.
  - Zuständigkeit: Das Standard-Stylesheet für die LightSlider-Bibliothek. Es bietet die wesentliche Gestaltung für den Karussell-Container, Slides, Navigationspfeile und Paginierungspunkte. Entwickler können diese Stile im `custom.css` ihres Themes oder durch Modifikation von `ccarousel/css.css` überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `ccarousel/views/templates/hook/ccarousel.tpl`
    - Gerendert in: `displayHome` (und potenziell andere Hooks, falls im Modul konfiguriert).
    - Ausgabe: Die HTML-Struktur für ein oder mehrere Karussells. Dieses Template iteriert durch die Karussellgruppen und ihre zugehörigen Elemente und generiert die notwendigen `<ul>`- und `<li>`-Elemente, die LightSlider erwartet. Es enthält `<img>`-Tags, Video-Einbettungen oder rohe HTML-Inhalte basierend auf dem Elementtyp, zusammen mit Links. Es enthält wahrscheinlich auch den JavaScript-Initialisierungsaufruf für LightSlider, der Konfigurationsoptionen übergibt, die aus den `gcarousel`-Einstellungen abgerufen wurden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_gcarousel`: Speichert Informationen über jede Karussellgruppe.
    - `id_gcarousel` (PK, INT)
    - `name` (VARCHAR)
    - `active` (TINYINT)
    - `settings` (TEXT oder JSON, für serialisierte LightSlider-Optionen)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_gcitem`: Speichert Informationen über jede einzelne Slide/jedes Element.
    - `id_gcitem` (PK, INT)
    - `id_gcarousel` (FK zu `ps_gcarousel`, INT)
    - `position` (INT)
    - `active` (TINYINT)
    - `type` (VARCHAR, z.B. ‘image’, ‘video’, ‘text’, ‘html’)
    - `content` (TEXT, speichert Bildpfad, Video-URL oder rohen Text/HTML)
    - `link` (VARCHAR)
    - `title` (VARCHAR, für Mehrsprachigkeit)
    - `description` (TEXT, für Mehrsprachigkeit)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Speichert modulspezifische Konfigurationswerte, wie `CCAROUSEL_LIGHTSLIDER`, `MYPRESTA_UPDATES` usw.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Stellt die notwendigen CSS- (`lightslider.css`, `ccarousel.css`) und JavaScript-Dateien (`lightslider.js`) für die Funktion und das Styling des Karussells bereit. |
| `displayHome` | Im Hauptinhaltsbereich der Startseite. | Rendert das `ccarousel.tpl`-Template, das die HTML-Struktur für die aktiven Karussellgruppen und ihre Elemente sowie das LightSlider-Initialisierungsskript generiert. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die neueste, sicherste Version des Moduls „Benutzerdefiniertes Inhalte-Karussell“ verwenden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Fragen zur Modulfunktionalität und Kompatibilität zur Verfügung.
