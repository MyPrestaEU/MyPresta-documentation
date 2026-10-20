---
title: "Homefeatured multi slider – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Homefeatured multi slider“ von MyPresta.eu."
sidebar:
  label: "Homefeatured multi slider – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homefeatured multi slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/homefeatured-multi-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/homefeatured-multi-slider/)
>
> ---


# Homefeatured multi slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den korrekten Betrieb eines PrestaShop-Shops erforderlich. Dieses Modul hat keine ungewöhnlichen oder spezifischen Hosting-Anforderungen, die über eine Standard-PrestaShop-Umgebung hinausgehen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Homefeatured multi slider“ bietet zwei Hauptbereiche für die Konfiguration: die Hauptkonfigurationsseite des Moduls für allgemeine Einstellungen und einen dedizierten Administrationsbildschirm zur Verwaltung Ihrer Produkt-Slider und Kategorien.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der primäre Bildschirm, auf dem Sie das allgemeine Verhalten und Aussehen Ihres Multi-Featured-Produkt-Sliders einrichten. Um darauf zuzugreifen, gehen Sie zu **Module > Modul-Manager**, suchen Sie „Homefeatured multi slider“ und klicken Sie auf „Konfigurieren“.

#### Registerkarte „Allgemeine Einstellungen“

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Anzeigen in Hook** | Bestimmt, wo der Slider auf Ihrer Website erscheint. | *Wenn auf `displayHome` (oder ähnlichen Hauptinhalts-Hook) eingestellt:* Der Slider wird ein prominentes Merkmal auf Ihrer Startseite sein. *Wenn auf `displayLeftColumn` oder `displayRightColumn` eingestellt:* Der Slider erscheint in den Seitenleisten, normalerweise kleiner. *Wenn auf `displayFooter` eingestellt:* Der Slider befindet sich am unteren Rand Ihrer Seiten. | `displayHome` für einen prominenten Startseiten-Slider. | Sie möchten, dass Ihre wichtigsten ausgewählten Produkte das Erste sind, was Kunden auf Ihrer Startseite sehen. |
| **Anzahl der anzuzeigenden Produkte** | Steuert, wie viele Produkte gleichzeitig im Slider sichtbar sind. | *Wenn auf `4` eingestellt:* Vier Produkte werden nebeneinander angezeigt (wenn der Platz es zulässt). *Wenn auf `1` eingestellt:* Nur ein Produkt ist sichtbar, oft mit größeren Bildern. | `4` oder `5` für die meisten Themes, abhängig von Ihren Produktbildgrößen und dem Design. | Sie haben große Produktbilder und möchten weniger Artikel gleichzeitig anzeigen, um mehr Details zu zeigen, oder Sie haben kleine Bilder und möchten mehr anzeigen. |
| **Slider-Geschwindigkeit (ms)** | Legt fest, wie schnell der Slider zwischen Produkten oder Slides wechselt. Gemessen in Millisekunden (1000ms = 1 Sekunde). | *Wenn auf `500` eingestellt:* Übergänge sind sehr schnell. *Wenn auf `5000` eingestellt:* Übergänge sind langsam, was Kunden mehr Zeit gibt, jedes Produkt anzusehen. | `3000` (3 Sekunden) bis `5000` (5 Sekunden) für ein angenehmes Seherlebnis. | Sie möchten eine dynamische, schnelle Anzeige von Produkten oder ein entspannteres, besinnlicheres Browsing-Erlebnis. |
| **Autoplay Slider** | Bestimmt, ob der Slider automatisch durch Produkte rotiert, ohne Benutzerinteraktion. | *Wenn aktiviert (JA):* Der Slider wechselt nach der eingestellten „Slider-Geschwindigkeit“ automatisch zum nächsten Produkt. *Wenn deaktiviert (NEIN):* Der Slider wechselt nur die Slides, wenn der Kunde auf Navigationspfeile klickt. | `JA`, um den Inhalt dynamisch und ansprechend zu halten. | Sie möchten sicherstellen, dass alle ausgewählten Produkte sichtbar werden, auch wenn Kunden nicht aktiv durchklicken. |
| **Navigationspfeile anzeigen** | Steuert die Sichtbarkeit von „Weiter“- und „Zurück“-Pfeilen am Slider. | *Wenn aktiviert (JA):* Pfeile erscheinen an den Seiten des Sliders und ermöglichen die manuelle Navigation. *Wenn deaktiviert (NEIN):* Kunden müssen sich auf Autoplay oder andere Navigationsmethoden (falls verfügbar) verlassen. | `JA` für bessere Benutzerkontrolle und Zugänglichkeit. | Sie möchten, dass Kunden Produkte einfach in ihrem eigenen Tempo durchsuchen können. |
| **Paginierungspunkte anzeigen** | Steuert die Sichtbarkeit kleiner Punkte oder Indikatoren, normalerweise am unteren Rand des Sliders, die jeden Slide darstellen. | *Wenn aktiviert (JA):* Punkte erscheinen, die die aktuelle Slide-Position anzeigen und ein direktes Springen zu bestimmten Slides ermöglichen. *Wenn deaktiviert (NEIN):* Punkte sind ausgeblendet. | `JA` für bessere Benutzerorientierung und direkten Zugriff auf Slides. | Sie möchten, dass Kunden wissen, wie viele Slides es gibt und direkt zu einem bestimmten springen können. |
| **Produktbildbreite (px)** | Legt die Breite der Produktbilder innerhalb des Sliders fest. | *Wenn auf `200` eingestellt:* Bilder sind 200 Pixel breit. *Wenn auf `300` eingestellt:* Bilder sind 300 Pixel breit. Dies beeinflusst die Gesamtgröße und das Layout des Sliders. | `250` bis `350` Pixel, abhängig vom Design Ihres Themes und der „Anzahl der anzuzeigenden Produkte“. | Ihre Produktbilder sind hochauflösend und Sie möchten, dass sie größer erscheinen, oder Sie benötigen sie kleiner, um mehr Produkte unterzubringen. |
| **Produktbildhöhe (px)** | Legt die Höhe der Produktbilder innerhalb des Sliders fest. | *Wenn auf `200` eingestellt:* Bilder sind 200 Pixel hoch. *Wenn auf `300` eingestellt:* Bilder sind 300 Pixel hoch. Dies funktioniert in Verbindung mit der Breite, um das Seitenverhältnis beizubehalten oder zuzuschneiden. | `250` bis `350` Pixel, passend zu Ihrer gewählten Breite für quadratische Bilder, oder angepasst für Hoch-/Querformat. | Sie haben Produktbilder mit unterschiedlichen Seitenverhältnissen und möchten deren Anzeigehöhe standardisieren. |
| **Hintergrundfarbe** | Ermöglicht Ihnen, eine benutzerdefinierte Hintergrundfarbe für den gesamten Slider-Block festzulegen. | *Wenn auf `#FFFFFF` (weiß) eingestellt:* Der Slider-Hintergrund ist weiß. *Wenn auf `#F0F0F0` (hellgrau) eingestellt:* Der Hintergrund ist hellgrau. | Leer lassen für transparent oder eine Farbe verwenden, die zu Ihrem Theme passt. | Sie möchten, dass der Slider mit einer markanten Hintergrundfarbe hervorsticht oder nahtlos mit dem Seitenhintergrund verschmilzt. |
| **Textfarbe** | Legt die Farbe für Produktnamen und anderen Text innerhalb des Sliders fest. | *Wenn auf `#000000` (schwarz) eingestellt:* Text ist schwarz. *Wenn auf `#333333` (dunkelgrau) eingestellt:* Text ist dunkelgrau. | Eine Farbe, die einen guten Kontrast zu Ihrer gewählten Hintergrundfarbe bietet. | Sie müssen sicherstellen, dass Produktnamen vor dem Hintergrund des Sliders gut lesbar sind. |
| **Preisfarbe** | Legt die Farbe für die im Slider angezeigten Produktpreise fest. | *Wenn auf `#FF0000` (rot) eingestellt:* Preise sind rot, oft für Verkäufe verwendet. *Wenn auf `#008000` (grün) eingestellt:* Preise sind grün. | Eine Farbe, die Preise hervorhebt, oft die Akzentfarbe Ihrer Marke oder eine Standard-Preisfarbe. | Sie möchten, dass Preise gut sichtbar sind und Aufmerksamkeit erregen. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul enthält einen dedizierten Bereich in Ihrem PrestaShop Back Office, um die Kategorien Ihrer ausgewählten Produkte zu verwalten und Produkte diesen zuzuweisen.

#### Bildschirmname & Menüpfad: „Multi Featured Slider“

Sie finden diesen Bereich, indem Sie navigieren zu:
**Module > Modul-Manager > Homefeatured multi slider > Konfigurieren**
Auf der Konfigurationsseite sehen Sie eine Registerkarte oder einen Link, der zur Verwaltungsoberfläche „Multi Featured Slider“ führt. In PrestaShop 1.7+ könnte dies als neuer Menüpunkt unter „Katalog“ oder „Module“ erscheinen, wenn das Modul eine eigene Registerkarte registriert.

Dieser Bildschirm wird vom `AdminprosliderController` (befindlich unter `multihomefeatured/controllers/admin/adminproslider.php`) verwaltet.

**Verfügbare Aktionen & Einstellungen:**

Dieser Bildschirm präsentiert typischerweise eine Liste Ihrer erstellten „ausgewählten Produktkategorien“ (im zugrunde liegenden Code als „opinion“ bezeichnet, aber funktional als Kategorien für Ihren Slider fungierend).

- **Auflistungstabelle:** Sie sehen eine Tabelle, die alle benutzerdefinierten Kategorien auflistet, die Sie für Ihre ausgewählten Produkte erstellt haben. Jede Zeile zeigt wahrscheinlich:

  - **# (ID):** Eine eindeutige Kennung für die Kategorie.
  - **Kategoriename:** Der Name, den Sie dieser Gruppe von ausgewählten Produkten gegeben haben (z. B. „Bestseller“, „Neuheiten“).
  - **Status:** Ob die Kategorie aktiv (im Slider sichtbar) oder inaktiv ist.
  - **Aktionen:** Schaltflächen zum „Bearbeiten“ (Kategoriename, Status ändern und Produkte zuweisen) oder „Löschen“ der Kategorie.
- **Neue Kategorie hinzufügen:** Es gibt eine Schaltfläche (z. B. „Neue Kategorie hinzufügen“ oder „Neu hinzufügen“), um eine neue Gruppe von ausgewählten Produkten zu erstellen. Beim Hinzufügen oder Bearbeiten einer Kategorie finden Sie typischerweise:

  - **Kategoriename:** Ein Eingabefeld zur Definition des Namens Ihrer ausgewählten Produktkategorie (z. B. „Saisonale Angebote“, „Kundenfavoriten“).
  - **Aktiv/Inaktiv-Schalter:** Ein Umschalter zum Aktivieren oder Deaktivieren der Anzeige dieser spezifischen Kategorie im Front-Office-Slider.
  - **Produktzuweisung:** Dies ist die Kernfunktionalität. Sie sehen wahrscheinlich eine Suchleiste oder eine Liste verfügbarer Produkte. Sie können nach Produkten suchen und diese dieser spezifischen ausgewählten Kategorie hinzufügen. Produkte können normalerweise innerhalb der Kategorie neu angeordnet werden.

**Auswirkung von Änderungen:**

- **Hinzufügen einer neuen Kategorie:** Erstellt eine neue Registerkarte oder einen neuen Abschnitt in Ihrem Front-Office-Slider. Sie können diese dann mit spezifischen Produkten füllen.
- **Bearbeiten einer Kategorie:**
  - Das Ändern des **Kategorienamens** aktualisiert die Bezeichnung, die Kunden im Slider angezeigt wird.
  - Das Umschalten von **Aktiv/Inaktiv** zeigt oder verbirgt diese gesamte Kategorie und ihre Produkte sofort im Front-Office-Slider.
  - **Hinzufügen/Entfernen von Produkten:** Aktualisiert direkt, welche Produkte in dieser spezifischen Slider-Kategorie erscheinen.
  - **Neuanordnung von Produkten:** Ändert die Reihenfolge, in der Produkte innerhalb dieser Kategorie im Slider erscheinen.
- **Löschen einer Kategorie:** Entfernt die Kategorie und alle ihr zugewiesenen Produkte dauerhaft aus dem Slider. Die Produkte selbst werden nicht aus Ihrem Shop gelöscht.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. **Planen Sie Ihre Kategorien:** Bevor Sie Kategorien erstellen, entscheiden Sie sich für logische Gruppen für Ihre ausgewählten Produkte (z. B. „Neuheiten“, „Im Angebot“, „Bestseller“, „Saisonale Empfehlungen“).
2. **Kategorien erstellen:** Verwenden Sie die Schaltfläche „Neu hinzufügen“, um jede Kategorie zu erstellen und ihr einen klaren, beschreibenden Namen zu geben.
3. **Produkte zuweisen:** Verwenden Sie für jede Kategorie die Produktzuweisungs-Oberfläche, um die relevanten Produkte zu suchen und hinzuzufügen. Speichern Sie Ihre Änderungen.
4. **Produkte anordnen:** Ordnen Sie die Produkte innerhalb jeder Kategorie in der gewünschten Reihenfolge an.
5. **Überprüfen & Aktivieren:** Wenn Sie zufrieden sind, stellen Sie sicher, dass die Kategorie auf „Aktiv“ gesetzt ist.
6. **Front-Office überprüfen:** Überprüfen Sie die Änderungen immer in Ihrem Live-Shop, um sicherzustellen, dass der Slider wie erwartet aussieht und funktioniert.
7. **Regelmäßige Updates:** Aktualisieren Sie Ihre ausgewählten Kategorien regelmäßig mit neuen Produkten, saisonalen Artikeln oder Artikeln, die Sie bewerben möchten. Entfernen Sie ältere oder nicht vorrätige Artikel, um den Slider frisch und relevant zu halten.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Anzeigen in Hook | `displayHome` | Steuert, wo der Slider erscheint (Startseite, Spalten, Footer). |
|  | Anzahl der anzuzeigenden Produkte | `4` | Wie viele Produkte gleichzeitig im Slider sichtbar sind. |
|  | Slider-Geschwindigkeit (ms) | `3000` - `5000` | Geschwindigkeit der automatischen Slide-Übergänge. |
|  | Autoplay Slider | `YES` | Slider rotiert Produkte automatisch. |
|  | Navigationspfeile anzeigen | `YES` | Zeigt Pfeile für die manuelle Navigation an. |
|  | Paginierungspunkte anzeigen | `YES` | Zeigt Punkte zur Slide-Anzeige und direktem Zugriff an. |
|  | Produktbildbreite (px) | `250` - `350` | Legt die Breite der Produktbilder im Slider fest. |
|  | Produktbildhöhe (px) | `250` - `350` | Legt die Höhe der Produktbilder im Slider fest. |
|  | Hintergrundfarbe | Leer lassen / Theme-passend | Legt die Hintergrundfarbe des Slider-Blocks fest. |
|  | Textfarbe | Theme-passend / `#333333` | Legt die Farbe für Produktnamen und Beschreibungen fest. |
|  | Preisfarbe | Theme-passend / Akzentfarbe | Legt die Farbe für Produktpreise fest. |
| **„Multi Featured Slider“ Admin-Bildschirm** | Kategorie hinzufügen/bearbeiten Name | Beschreibender Name (z. B. „Bestseller“) | Erstellt/ändert eine Registerkarte/einen Abschnitt im Slider. |
|  | Kategorie-Status (Aktiv/Inaktiv) | `Active` | Zeigt oder verbirgt eine gesamte ausgewählte Produktkategorie. |
|  | Produkte zur Kategorie zuweisen | N/A | Wählt aus, welche Produkte in einer bestimmten Slider-Kategorie erscheinen. |
|  | Produkte neu anordnen | N/A | Ändert die Anzeigereihenfolge der Produkte innerhalb einer Kategorie. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Slider wird nach der Konfiguration nicht auf der Startseite angezeigt.**

- **A:** Überprüfen Sie zunächst, ob das Modul aktiviert und so konfiguriert ist, dass es im richtigen Hook (z. B. `displayHome`) auf der Hauptkonfigurationsseite des Moduls angezeigt wird. Zweitens stellen Sie sicher, dass Sie mindestens eine „Multi Featured Slider“-Kategorie erstellt und Produkte zugewiesen haben und dass die Kategorie im dedizierten Admin-Bildschirm auf „Aktiv“ gesetzt ist. Leeren Sie schließlich Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung > Cache leeren**).

**F2: Der Slider sieht in meinem Shop kaputt oder falsch ausgerichtet aus.**

- **A:** Dies ist oft ein CSS-Konflikt mit Ihrem Theme.
  1. **Bildabmessungen überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls und überprüfen Sie die Einstellungen „Produktbildbreite“ und „Produktbildhöhe“. Stellen Sie sicher, dass sie für Ihr Theme und die Anzahl der Produkte, die Sie anzeigen möchten, geeignet sind.
  2. **Theme-Overrides:** Ihr Theme könnte widersprüchliche Stile haben. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, überschreibt das CSS Ihres Themes wahrscheinlich die Stile des Moduls. Möglicherweise benötigen Sie einen Webentwickler, um einen benutzerdefinierten CSS-Override in der `custom.css`-Datei Ihres Themes zu erstellen.
  3. **Cache leeren:** Leeren Sie immer Ihren Browser-Cache und den PrestaShop Smarty-Cache, nachdem Sie designbezogene Änderungen vorgenommen haben.

**F3: Wie ändere ich die Reihenfolge der Produkte innerhalb einer Slider-Kategorie?**

- **A:** Gehen Sie zum dedizierten Admin-Bildschirm „Multi Featured Slider“. Bearbeiten Sie die spezifische Kategorie, die Sie neu anordnen möchten. Innerhalb der Produktzuweisungs-Oberfläche sollten Sie Produkte per Drag & Drop verschieben können, um ihre Reihenfolge zu ändern, oder es könnten Auf-/Ab-Pfeile neben jedem Produkt vorhanden sein. Denken Sie daran, Ihre Änderungen zu speichern.

**F4: Kann ich die Kategorienamen für verschiedene Sprachen übersetzen?**

- **A:** Ja, PrestaShop-Module unterstützen typischerweise mehrsprachige Eingaben für Felder wie Kategorienamen. Wenn Sie einen Kategorienamen im Admin-Bildschirm „Multi Featured Slider“ bearbeiten, suchen Sie nach einem Sprachwähler (normalerweise ein Flaggensymbol) neben dem Eingabefeld. Klicken Sie darauf, um den Namen für jede installierte Sprache einzugeben.

**F5: Der Slider ist zu schnell/langsam, oder das Autoplay funktioniert nicht.**

- **A:** Passen Sie die Einstellung „Slider-Geschwindigkeit (ms)“ auf der Hauptkonfigurationsseite des Moduls an. Eine höhere Zahl bedeutet einen langsameren Übergang. Stellen Sie sicher, dass „Autoplay Slider“ auf `YES` gesetzt ist, wenn Sie möchten, dass er automatisch rotiert. Denken Sie daran, zu speichern und Ihren Cache zu leeren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Homefeatured multi slider“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `Homefeatured multi slider` (interner Name `multihomefeatured`) folgt einer Standard-PrestaShop-Modularchitektur und nutzt das MVC-Muster. Es besteht hauptsächlich aus:

- Einer Hauptmoduldatei (`ajax_multihomefeatured.php`), die Installation, Deinstallation und das primäre Konfigurationsformular (`getContent()`) handhabt.
- Einem Front-Controller (`default.php`) für potenzielle AJAX-Interaktionen oder spezifische Front-Office-Rendering-Logik.
- Einem Admin-Controller (`AdminprosliderController.php`) zur Verwaltung der benutzerdefinierten „ausgewählten Produktkategorien“ (im Datenbankkontext als `opinion` bezeichnet, aber funktional als Kategorien fungierend).
- Smarty-Templates für das Rendern sowohl der Back-Office-Konfiguration als auch der Front-Office-Slider-Elemente.
- JavaScript für die Slider-Funktionalität und CSS für das Styling.

Das Modul scheint keine benutzerdefinierten `ObjectModel`-Klassen basierend auf dem bereitgestellten Inventar zu verwenden, was darauf hindeutet, dass es seine benutzerdefinierten Kategorie- und Produktzuweisungen direkt in `ps_configuration` oder einer benutzerdefinierten Tabelle speichert, die vom `AdminprosliderController` verwaltet wird.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `multihomefeatured/controllers/front/default.php`
  - **Klassenname & Elternklasse**: `MultihomefeaturedDefaultModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit**: Dieser Controller wird wahrscheinlich für die Bearbeitung spezifischer Front-Office-Anfragen verwendet, potenziell für AJAX-Aufrufe im Zusammenhang mit Slider-Inhalten oder für das Rendern einer eigenständigen Seite, falls das Modul eine solche anböte. Angesichts der primären Funktion des Moduls als Slider könnte es das Laden dynamischer Inhalte oder den Abruf spezifischer Produktdaten für den Slider handhaben.

#### Back-Office-Admin-Controller

- `multihomefeatured/controllers/admin/adminproslider.php`
  - **Registerkartenname und verwaltete Entität**: Dieser Controller verwaltet die benutzerdefinierten „Multi Featured Slider“-Kategorien und ihre zugehörigen Produkte. Er erscheint wahrscheinlich als Unterregisterkarte oder als dedizierter Eintrag im PrestaShop Back Office-Menü, oft unter „Katalog“ oder „Module“. Die verwaltete Entität ist konzeptionell eine „ausgewählte Produktkategorie“, die das Modul intern in seinen Datenbankinteraktionen als `opinion` bezeichnet.
  - **Verantwortlichkeit**: Dieser Controller bietet die CRUD-Schnittstelle (Create, Read, Update, Delete) für diese benutzerdefinierten Kategorien. Er handhabt:
    - Auflistung bestehender Kategorien.
    - Anzeige von Formularen zum Hinzufügen neuer Kategorien.
    - Anzeige von Formularen zum Bearbeiten bestehender Kategorien (einschließlich Zuweisen und Neuanordnen von Produkten).
    - Verarbeitung von Formularübermittlungen für die Erstellung/Aktualisierung von Kategorien.
    - Bearbeitung des Löschens von Kategorien.
    - Verwaltung der Zuordnung zwischen Kategorien und spezifischen PrestaShop-Produkten.

### 4.3 Kernklassen & Modelle (`classes/`)

Basierend auf dem bereitgestellten Inventar sind keine benutzerdefinierten PHP-Klassen explizit im Verzeichnis `classes/` aufgeführt. Dies deutet darauf hin, dass:

1. Das Modul älter sein könnte und Datenbanktabellen direkt ohne ein dediziertes `ObjectModel` manipuliert.
2. Der `AdminprosliderController` die Datenbankinteraktionen für seine `opinion`-Entität direkt handhaben könnte.
3. Die Hauptmoduldatei (`ajax_multihomefeatured.php`) alle notwendige Logik für Konfiguration und grundlegende Datenverarbeitung enthalten könnte.

Wenn benutzerdefinierte Daten (wie die „ausgewählten Produktkategorien“ und ihre Produktzuweisungen) gespeichert werden, geschieht dies entweder in `ps_configuration` (für einfache Schlüssel-Wert-Paare) oder in einer benutzerdefinierten Datenbanktabelle, die direkt vom `AdminprosliderController` ohne eine formale `ObjectModel`-Definition in `classes/` verwaltet wird.

### 4.4 JavaScript-Assets (`views/js/`)

- `multihomefeatured/js/jquery.catslider.16.js`
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Wahrscheinlich eine Version eines „Kategorie-Slider“- oder „Inhalts-Slider“-jQuery-Plugins, speziell angepasst oder vorgesehen für PrestaShop 1.6.x. Es würde die Kern-Slider-Animation, Navigation und Responsivität handhaben.
- `multihomefeatured/js/jquery.catslider.js`
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Ähnlich wie oben, potenziell eine allgemeinere Version oder für andere PrestaShop-Versionen. Dieses Skript würde den Slider initialisieren, Übergänge, Autoplay und Benutzerinteraktion (Klicks, Wischen) verwalten.
- `multihomefeatured/js/jscolor/jscolor.js`
  - **Geltungsbereich**: Back-Office.
  - **Beschreibung**: Dies ist eine JavaScript-Bibliothek für einen Farbwähler. Sie wird im Back-Office-Konfigurationsformular des Moduls verwendet, um eine benutzerfreundliche Oberfläche zur Farbauswahl (z. B. für Hintergrund-, Text-, Preisfarben) bereitzustellen. Sie bindet sich an spezifische Eingabefelder, um den Farbwähler anzuzeigen.
- `multihomefeatured/js/modernizr.custom.63321.js`
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Modernizr ist eine JavaScript-Bibliothek, die HTML5- und CSS3-Funktionen im Browser des Benutzers erkennt. Sie wird oft verwendet, um Funktionserkennung und Fallback-Mechanismen bereitzustellen, um sicherzustellen, dass der Slider in verschiedenen Browsern, insbesondere älteren, die bestimmte CSS3-Übergangs- oder Animationsfunktionen möglicherweise nicht unterstützen, korrekt funktioniert.
- `multihomefeatured/js/script.js`
  - **Geltungsbereich**: Front-Office und/oder Back-Office.
  - **Beschreibung**: Dies ist wahrscheinlich die wichtigste benutzerdefinierte JavaScript-Datei für das Modul. Sie würde enthalten:
    - Initialisierungslogik für das `jquery.catslider`-Plugin, das Konfigurationsoptionen aus den Moduleinstellungen übergibt.
    - Event-Listener für Navigationspfeile, Paginierungspunkte oder benutzerdefinierte Interaktionen.
    - Potenzielle AJAX-Aufrufe an den Front-Controller `default.php` für dynamisches Laden von Inhalten.
    - Jegliche spezifische DOM-Manipulation oder UI-Verbesserungen im Zusammenhang mit dem Slider.
    - Im Back-Office könnte es Skripte für die Produktsuche und -zuweisung innerhalb der Formulare des `AdminprosliderController` enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `multihomefeatured/css/style.css`
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Dies ist das primäre Stylesheet für den Front-Office-Slider. Es definiert das visuelle Erscheinungsbild des Slider-Containers, der Produktelemente, Navigationspfeile, Paginierungspunkte, Produkttitel, Preise und aller anderen im Slider angezeigten Elemente.
  - **Wichtige CSS-Klassenselektoren**: Entwickler können Klassen wie `.multihomefeatured-slider`, `.slider-item`, `.product-image`, `.product-title`, `.product-price`, `.slider-nav-arrow`, `.slider-pagination` usw. erwarten, die in der `custom.css` eines benutzerdefinierten Themes oder über den PrestaShop-Theme-Override-Mechanismus überschrieben werden können.
- `multihomefeatured/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
  - **Geltungsbereich**: Back-Office.
  - **Beschreibung**: Dieses Stylesheet ist Teil der jQuery UI-Bibliothek, speziell des „UI-lightness“-Themes. Es wird wahrscheinlich im Back-Office zum Stylen von Elementen wie Datepickern, Dialogen oder anderen interaktiven Komponenten verwendet, die Teil der Formulare des `AdminprosliderController` sein könnten (z. B. für die Produktsuche-Autovervollständigung, falls mit jQuery UI implementiert).

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `multihomefeatured/header.tpl`
    - **Hook**: Wahrscheinlich `displayHeader` oder `actionFrontControllerSetMedia`.
    - **Ausgabe**: Fügt modulspezifische CSS- und JavaScript-Dateien (`jquery.catslider.js`, `modernizr.custom.63321.js`, `style.css`, `script.js`) in den `<head>`-Bereich des Front-Office ein, um sicherzustellen, dass sie geladen werden, bevor der Slider gerendert wird.
  - `multihomefeatured/home.tpl`
    - **Hook**: Konfigurierbar (z. B. `displayHome`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).
    - **Ausgabe**: Dies ist das Haupttemplate für die Front-Office-Anzeige des Sliders. Es enthält die HTML-Struktur für den gesamten Multi-Kategorie-Slider, einschließlich der Registerkarten für verschiedene Kategorien und des Containers für die Produkt-Slides. Es iteriert durch die konfigurierten Kategorien und Produkte, um den Slider zu erstellen.
  - `multihomefeatured/homeTab.tpl`
    - **Hook**: Intern von `home.tpl` gerendert.
    - **Ausgabe**: Dieses Template rendert wahrscheinlich eine einzelne Registerkarte oder ein Navigationselement für eine der ausgewählten Produktkategorien (z. B. „Bestseller“, „Neuheiten“). Es ist Teil der Navigation zum Wechseln zwischen verschiedenen Produkt-Slidern.
  - `multihomefeatured/homeTabContents.tpl`
    - **Hook**: Intern von `home.tpl` gerendert.
    - **Ausgabe**: Dieses Template rendert die eigentliche Produktliste für eine einzelne ausgewählte Produktkategorie. Es enthält die Schleife, die einzelne Produktbilder, Namen, Preise und potenziell „In den Warenkorb“-Buttons anzeigt, alles verpackt in der Struktur, die vom `jquery.catslider`-Plugin benötigt wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul definiert keine expliziten benutzerdefinierten `ObjectModel`-Klassen, aber der `AdminprosliderController` verwaltet eine Entität, die als `opinion` bezeichnet wird. Dies deutet stark darauf hin, dass das Modul mindestens eine benutzerdefinierte Tabelle erstellt, wahrscheinlich `ps_multihomefeatured_opinion` (oder ähnlich, gemäß der PrestaShop-Präfixkonvention `ps_`), um Folgendes zu speichern:
    - `id_multihomefeatured_opinion` (Primärschlüssel)
    - `name` (für den Kategorienamen, potenziell mehrsprachig)
    - `active` (Boolean für den Kategorienstatus)
    - Weitere Felder im Zusammenhang mit der Kategorienkonfiguration.
  - Zusätzlich gäbe es eine Verknüpfungstabelle, z. B. `ps_multihomefeatured_opinion_product`, um die Many-to-Many-Beziehung zwischen diesen Kategorien und `ps_product`-Einträgen zu speichern, einschließlich eines `position`-Feldes für die Reihenfolge.
  - Modulkonfigurationseinstellungen (wie Slider-Geschwindigkeit, Bildabmessungen, Farben) werden typischerweise in der Tabelle `ps_configuration` mit Schlüsseln gespeichert, die mit dem Modulnamen präfixiert sind (z. B. `MULTIHOMEFEATURED_SLIDER_SPEED`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt die CSS- und JavaScript-Dateien des Moduls für die Front-Office-Funktionalität ein. |
| `displayHome` | Hauptinhaltsbereich der Startseite. | Rendert den primären Multi-Kategorie-Produkt-Slider auf der Startseite. |
| `displayLeftColumn` | Linke Seitenleiste der Front-Office-Seiten. | Rendert eine kleinere Version des Sliders in der linken Spalte. |
| `displayRightColumn` | Rechte Seitenleiste der Front-Office-Seiten. | Rendert eine kleinere Version des Sliders in der rechten Spalte. |
| `displayFooter` | Unterer Bereich jeder Front-Office-Seite. | Rendert den Slider im Footer-Bereich. |
| `displayProductExtraContent` (oder ähnlicher Produktseiten-Hook) | Auf der Produktseite, unter den Produktdetails. | Potenziell verwendet, um verwandte Produkte in einem Slider auf Produktseiten anzuzeigen. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert. | Eine robustere Methode zur Registrierung von Assets (CSS/JS) für bestimmte Seiten oder global. |
| `actionModuleInstall` | Während der Modulinstallation. | Erstellt Datenbanktabellen, setzt Standardkonfigurationswerte, registriert Hooks. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Bereinigt Datenbanktabellen, entfernt Konfigurationswerte, deregistriert Hooks. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Homefeatured multi slider“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Sie können die aktuellsten Versionen des Moduls aus Ihrer Bestellhistorie herunterladen. Für technische Unterstützung oder spezifische Anfragen kontaktieren Sie bitte den MyPresta.eu-Support direkt über Ihr Kundenkonto.
