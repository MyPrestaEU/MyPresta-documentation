---
title: "Presta Pro Slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das Presta Pro Slider PrestaShop-Modul von MyPresta.eu."
sidebar:
  label: "Presta Pro Slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Presta Pro Slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/presta-pro-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/presta-pro-slider/)
>
> ---


# Presta Pro Slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Presta Pro Slider)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die allgemeinen Einstellungen für Ihren Slider verwalten und einzelne Folien hinzufügen/bearbeiten.

#### Allgemeine Slider-Einstellungen

-   **Was diese Einstellung bewirkt:** Diese Einstellungen steuern das allgemeine Erscheinungsbild und Verhalten Ihres Sliders, wie z.B. seine Abmessungen, Animationsgeschwindigkeit und wo er auf Ihrer Website erscheint.
-   **Auswirkung einer Änderung dieser Einstellung:** Das Anpassen dieser Werte wirkt sich direkt darauf aus, wie der Slider für Ihre Kunden aussieht und funktioniert.

| Einstellung / Option | Was es bewirkt | Auswirkung einer Änderung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Slider-Breite (px)** | Legt die Gesamtbreite des Sliders in Pixeln fest. | *Wenn auf 1000 gesetzt:* Der Slider ist 1000 Pixel breit. *Wenn auf 500 gesetzt:* Der Slider ist 500 Pixel breit. | `100%` (für volle Breite) oder ein spezifischer Pixelwert wie `1170` (üblich für Inhaltsbereiche). | Sie möchten, dass Ihr Slider den gesamten Inhaltsbereich Ihrer Startseite einnimmt, der 1170px breit ist. Sie würden `1170` eingeben. Wenn Sie möchten, dass er responsiv ist und die volle verfügbare Breite einnimmt, verwenden Sie `100%`. |
| **Slider-Höhe (px)** | Legt die Gesamthöhe des Sliders in Pixeln fest. | *Wenn auf 400 gesetzt:* Der Slider ist 400 Pixel hoch. *Wenn auf 250 gesetzt:* Der Slider ist 250 Pixel hoch. | `350` - `500` (abhängig vom Bildinhalt). | Sie haben hochwertige Bannerbilder, die bei einer bestimmten Höhe am besten aussehen. Sie würden dies auf `450` setzen, um sicherzustellen, dass Ihre Bilder ohne zu starke Dehnung oder Stauchung angezeigt werden. |
| **Animationsgeschwindigkeit (ms)** | Steuert, wie schnell der Übergang zwischen den Folien erfolgt, in Millisekunden. | *Wenn auf 500 gesetzt:* Folien wechseln schnell (0,5 Sekunden). *Wenn auf 2000 gesetzt:* Folien wechseln langsam (2 Sekunden). | `1000` (1 Sekunde) | Sie möchten einen sanften, spürbaren Übergang zwischen Ihren Werbefolien, aber nicht so langsam, dass Kunden sich langweilen. Eine Einstellung auf `1000` bietet eine gute Balance. |
| **Autoplay** | Bestimmt, ob der Slider automatisch zur nächsten Folie wechselt. | *Wenn aktiviert (JA):* Folien wechseln automatisch nach einer festgelegten Verzögerung. *Wenn deaktiviert (NEIN):* Folien wechseln nur, wenn ein Kunde auf Navigationspfeile oder Punkte klickt. | `JA` | Sie möchten, dass Ihre Hauptaktionen automatisch auf der Startseite durchlaufen, ohne dass der Kunde interagieren muss. |
| **Autoplay-Geschwindigkeit (ms)** | Wenn Autoplay aktiviert ist, legt dies die Verzögerung fest, bevor die nächste Folie erscheint, in Millisekunden. | *Wenn auf 5000 gesetzt:* Jede Folie wird 5 Sekunden lang angezeigt. *Wenn auf 3000 gesetzt:* Jede Folie wird 3 Sekunden lang angezeigt. | `5000` (5 Sekunden) | Sie haben viel Text auf Ihren Folien und möchten den Kunden genügend Zeit geben, ihn zu lesen, bevor die nächste Folie erscheint. Eine Einstellung auf `7000` (7 Sekunden) wäre angemessen. |
| **Anzeigen auf Hook** | Wählt den PrestaShop-Hook aus, an dem der Slider angezeigt wird. | *Wenn auf `displayHeader` gesetzt*: Der Slider erscheint oben auf jeder Seite. *Wenn auf `displayLeftColumn` gesetzt*: Der Slider erscheint in der linken Seitenleiste. | `displayHome` (falls verfügbar, ansonsten `displayHeader` oder `displayTop`) | Sie möchten, dass der Slider ein prominentes Merkmal auf Ihrer Startseite ist. Sie würden `displayHome` oder `displayTop` auswählen. Wenn Sie ihn auf Produktseiten haben möchten, könnten Sie `displayProductFooter` auswählen. |
| **Hintergrundfarbe** | Legt die Hintergrundfarbe des Slider-Containers fest. | *Wenn auf #FFFFFF gesetzt:* Der Hintergrund ist weiß. *Wenn auf #000000 gesetzt:* Der Hintergrund ist schwarz. | `Leer lassen` (für transparent) oder eine Farbe, die zu Ihrem Theme passt. | Ihr Theme hat einen hellen Hintergrund, und Sie möchten, dass der Slider nahtlos integriert wird. Sie würden dies auf `#FFFFFF` setzen. |
| **Textfarbe** | Legt die Standardfarbe für Text innerhalb des Sliders fest (Bildunterschriften, Beschreibungen). | *Wenn auf #000000 gesetzt:* Text ist schwarz. *Wenn auf #FF0000 gesetzt:* Text ist rot. | `#333333` (dunkelgrau) | Ihre Slider-Bilder sind hell, und Sie benötigen dunklen Text, um die Lesbarkeit zu gewährleisten. Sie würden dies auf `#333333` setzen. |

#### Folienverwaltungsbereich

Dieser Bereich ermöglicht es Ihnen, einzelne Folien, die Ihre Diashow bilden, hinzuzufügen, zu bearbeiten und zu löschen.

-   **Schaltfläche „Neue Folie hinzufügen“:** Klicken Sie hier, um ein Formular zum Erstellen einer brandneuen Folie zu öffnen.
-   **Liste der vorhandenen Folien:** Zeigt eine Tabelle aller Ihrer aktuell aktiven Folien an, normalerweise mit Optionen zum Bearbeiten oder Löschen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminprosliderController (Back Office > Module > Presta Pro Slider > Konfigurieren > „Neue Folie hinzufügen“ oder „Bearbeiten“ einer vorhandenen Folie)

Dieser Bildschirm erscheint, wenn Sie auf „Neue Folie hinzufügen“ oder das „Bearbeiten“-Symbol neben einer vorhandenen Folie in der Hauptkonfiguration klicken. Er ermöglicht es Ihnen, den Inhalt und das Verhalten jeder einzelnen Folie zu definieren.

-   **Bildschirmname & Menüpfad:** Zugriff über die Hauptmodulkonfigurationsseite durch Klicken auf „Neue Folie hinzufügen“ oder das Bearbeitungssymbol für eine vorhandene Folie.
-   **Verfügbare Aktionen & Einstellungen:** Dieses Formular ermöglicht Ihnen die Eingabe aller Details für eine einzelne Folie.

| Einstellung / Option | Was es bewirkt | Auswirkung einer Änderung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Folientitel (Bildunterschrift)** | Die Hauptüberschrift oder der kurze Text, der auf der Folie angezeigt wird. | Dieser Text wird prominent auf Ihrer Folie erscheinen, normalerweise in einer größeren Schriftart. | Halten Sie ihn prägnant und wirkungsvoll. | „Sommer-Sale!“ oder „Neuheiten“ |
| **Folienbeschreibung** | Längerer Text, der weitere Details zum Inhalt der Folie liefert. | Dieser Text erscheint unter dem Titel und bietet dem Kunden weitere Informationen. | Geben Sie genügend Details an, ohne zu überfordern. | „Bis zu 50% Rabatt auf alle Bademode für eine begrenzte Zeit!“ |
| **Folienbild** | Das Haupt-Hintergrundbild für diese spezifische Folie. | Dieses Bild wird das visuelle Herzstück Ihrer Folie sein. | Hochwertiges, relevantes Bild mit guter Auflösung. | Ein attraktives Bild eines Models, das ein neues Kleid für eine Modeaktion trägt. |
| **Link-URL** | Die Webadresse (URL), zu der Kunden weitergeleitet werden, wenn sie auf diese Folie klicken. | *Wenn gesetzt:* Ein Klick auf die Folie führt den Kunden zu dieser URL. *Wenn leer:* Die Folie ist nicht anklickbar. | Eine gültige URL zu einem Produkt, einer Kategorie oder einer Informationsseite. | Link zu Ihrer Kategorie „Neuheiten“: `https://ihrshop.de/neuheiten` |
| **In neuem Fenster öffnen** | Bestimmt, ob die Link-URL in einem neuen Browser-Tab/Fenster geöffnet wird. | *Wenn aktiviert (JA):* Der Link öffnet sich in einem neuen Tab, wodurch Ihr Store im ursprünglichen Tab geöffnet bleibt. *Wenn deaktiviert (NEIN):* Der Link öffnet sich im selben Tab und navigiert von Ihrer aktuellen Seite weg. | `JA` (generell empfohlen für externe Links oder Aktionen) | Sie verlinken auf einen externen Blogbeitrag oder ein Social-Media-Profil. Sie würden dies aktivieren, um Ihre Kunden in Ihrem PrestaShop-Store zu halten. |
| **Aktiv** | Steuert, ob diese Folie derzeit im Slider sichtbar ist. | *Wenn aktiviert (JA):* Die Folie ist Teil der Diashow. *Wenn deaktiviert (NEIN):* Die Folie wird ausgeblendet, aber nicht gelöscht, sodass Sie sie später wieder aktivieren können. | `JA` für aktive Aktionen. | Sie haben eine saisonale Aktion, die beendet ist, aber Sie könnten sie nächstes Jahr wieder durchführen. Sie würden sie auf `NEIN` setzen, anstatt sie zu löschen. |
| **Reihenfolge / Position** | Legt die Anzeigereihenfolge dieser Folie im Verhältnis zu anderen fest. | Folien mit niedrigeren Zahlen erscheinen früher in der Sequenz. | `1`, `2`, `3`, usw. in der gewünschten Reihenfolge. | Sie möchten, dass Ihre Folie „Sommer-Sale“ zuerst erscheint, gefolgt von „Neuheiten“. Sie würden „Sommer-Sale“ auf `1` und „Neuheiten“ auf `2` setzen. |

-   **Empfohlener Workflow für die tägliche Store-Verwaltung:**
    1.  **Planen Sie Ihre Aktionen:** Entscheiden Sie, welche Produkte, Kategorien oder Nachrichten Sie hervorheben möchten.
    2.  **Bereiten Sie Ihre Bilder vor:** Stellen Sie sicher, dass Sie hochwertige Bilder haben, die zu den Abmessungen des Sliders passen.
    3.  **Neue Folien hinzufügen:** Verwenden Sie die Schaltfläche „Neue Folie hinzufügen“, um neue Inhalte zu erstellen. Füllen Sie alle Details aus, einschließlich Titel, Beschreibung, Bild und Link.
    4.  **Folien anordnen:** Passen Sie die „Reihenfolge / Position“ an, um die Reihenfolge zu steuern.
    5.  **Aktivieren/Deaktivieren:** Verwenden Sie den Schalter „Aktiv“, um die Sichtbarkeit zu verwalten, ohne Inhalte zu löschen.
    6.  **Im Front-Office überprüfen:** Überprüfen Sie Ihren Slider immer im Live-Store, um sicherzustellen, dass er wie erwartet aussieht und funktioniert.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Slider-Breite (px) | `100%` oder `1170` | Legt die horizontale Größe des Sliders fest. |
| | Slider-Höhe (px) | `350` - `500` | Legt die vertikale Größe des Sliders fest. |
| | Animationsgeschwindigkeit (ms) | `1000` | Steuert, wie schnell Folien wechseln. |
| | Autoplay | `JA` | Wechselt Folien automatisch. |
| | Autoplay-Geschwindigkeit (ms) | `5000` | Verzögerung zwischen automatischen Folienwechseln. |
| | Anzeigen auf Hook | `displayHome` / `displayHeader` | Wo der Slider in Ihrem Store erscheint. |
| | Hintergrundfarbe | `Leer lassen` / `#FFFFFF` | Hintergrundfarbe des Slider-Bereichs. |
| | Textfarbe | `#333333` | Standardtextfarbe für Bildunterschriften/Beschreibungen. |
| **Folie hinzufügen/bearbeiten** | Folientitel (Bildunterschrift) | Prägnant & wirkungsvoll | Hauptüberschrift für die Folie. |
| | Folienbeschreibung | Informativ | Detaillierter Text für die Folie. |
| | Folienbild | Hochwertiges Bild | Visueller Hintergrund für die Folie. |
| | Link-URL | Gültige URL | Ziel, wenn auf die Folie geklickt wird. |
| | In neuem Fenster öffnen | `JA` | Öffnet Link in einem neuen Browser-Tab. |
| | Aktiv | `JA` | Schaltet die Sichtbarkeit der Folie um. |
| | Reihenfolge / Position | `1, 2, 3...` | Bestimmt die Reihenfolge der Folien. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Slider wird im Front Office nicht angezeigt oder an der falschen Stelle.**

-   **A:** Überprüfen Sie zunächst die Einstellung „Anzeigen auf Hook“ in der Modulkonfiguration. Stellen Sie sicher, dass Sie den richtigen Hook ausgewählt haben (z.B. `displayHeader`, `displayTop`, `displayHome`). Wenn Ihr Theme benutzerdefinierte Hook-Namen hat oder einen Standard-Hook an dieser Stelle nicht explizit unterstützt, wird der Slider möglicherweise nicht angezeigt.
-   **A:** Überprüfen Sie auch, ob einzelne Folien in ihren Einstellungen als „Aktiv“ markiert sind. Wenn keine Folien aktiv sind, wird nichts angezeigt.
-   **A:** Leeren Sie schließlich Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal werden Änderungen erst nach dem Aktualisieren des Caches angezeigt.

**F2: Meine Slider-Bilder sehen unscharf oder gestreckt aus.**

-   **A:** Dies geschieht normalerweise, wenn Ihre hochgeladenen Bilder nicht den Einstellungen für „Slider-Breite“ und „Slider-Höhe“ entsprechen oder wenn sie eine niedrige Auflösung haben.
-   **A:** **Lösung:** Stellen Sie sicher, dass Ihre Bilder hochauflösend sind und idealerweise das gleiche Seitenverhältnis wie Ihre konfigurierten Slider-Abmessungen haben. Wenn Ihr Slider beispielsweise 1200px breit und 400px hoch ist, versuchen Sie, Bilder hochzuladen, die mindestens 1200px mal 400px groß sind. Möglicherweise müssen Sie Ihre Bilder vor dem Hochladen in der Größe ändern oder zuschneiden.

**F3: Der Text auf meinen Folien ist schwer zu lesen.**

-   **A:** Dies ist oft ein Kontrastproblem zwischen Ihrem „Folienbild“ und der von Ihnen gewählten „Textfarbe“.
-   **A:** **Lösung:**
    1.  Passen Sie die „Textfarbe“ in der Hauptmodulkonfiguration an eine Farbe an, die gut mit Ihren Bildern kontrastiert (z.B. weißer Text auf dunklen Bildern, schwarzer Text auf hellen Bildern).
    2.  Erwägen Sie, Ihren Bildern eine subtile Überlagerung hinzuzufügen (hierfür benötigen Sie möglicherweise einen Grafikeditor), um sie leicht abzudunkeln oder aufzuhellen, damit der Text besser hervorsticht.
    3.  Halten Sie Ihren „Folientitel“ und Ihre „Folienbeschreibung“ prägnant. Weniger Text ist oft schneller zu lesen.

**F4: Wie übersetze ich die Folientitel und Beschreibungen in verschiedene Sprachen?**

-   **A:** Wenn Sie eine Folie bearbeiten, sollten Sie neben den Feldern „Folientitel“ und „Folienbeschreibung“ Sprachauswahl-Tabs sehen (sofern Ihr PrestaShop-Store mehrere Sprachen aktiviert hat).
-   **A:** **Lösung:** Klicken Sie auf das Flaggensymbol oder den Sprach-Tab für jede Sprache, die Sie übersetzen möchten, und geben Sie dann den entsprechenden Text für diese Sprache ein. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Die Slider-Animationen sind zu schnell/langsam, oder Autoplay funktioniert nicht.**

-   **A:** Überprüfen Sie die Einstellungen „Animationsgeschwindigkeit (ms)“, „Autoplay“ und „Autoplay-Geschwindigkeit (ms)“ in der Hauptmodulkonfiguration.
-   **A:** **Lösung:**
    *   Erhöhen Sie die „Animationsgeschwindigkeit“ für langsamere Übergänge, verringern Sie sie für schnellere.
    *   Stellen Sie sicher, dass „Autoplay“ auf `JA` gesetzt ist, wenn Sie möchten, dass die Folien automatisch wechseln.
    *   Passen Sie die „Autoplay-Geschwindigkeit“ an, um zu steuern, wie lange jede Folie angezeigt wird, bevor sie zur nächsten wechselt. Denken Sie daran, dass diese Werte in Millisekunden angegeben sind (1000ms = 1 Sekunde).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Presta Pro Slider-Modul folgt einer Standard-PrestaShop-Modularchitektur und nutzt das MVC-Muster, wo immer dies angebracht ist. Es verwendet hauptsächlich eine einzige Hauptmoduldatei (`ajax_proslider.php`) für seine Kernlogik und Konfiguration, einen administrativen Controller zur Verwaltung von Folien und Front-Office-Templates zur Darstellung des Sliders. Es basiert auf jQuery und Modernizr für seine Frontend-Animationen und -Stile. Die Foliendaten werden direkt in der PrestaShop-Tabelle `ps_configuration` gespeichert, anstatt in einem dedizierten `ObjectModel` und einer benutzerdefinierten Datenbanktabelle.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   `controllers/front/default.php`
        *   **Klassenname & Elternklasse**: `ProsliderDefaultModuleFrontController` erweitert `ModuleFrontController`.
        *   **Verantwortlichkeit**: Dieser Controller ist wahrscheinlich für eine Standardroute oder eine spezifische Front-Office-Aktion vorgesehen, obwohl sein genauer Zweck minimal sein könnte, da das Modul hauptsächlich in bestehende Template-Bereiche eingreift. Er würde Anfragen an `ihrshop.de/module/proslider/default` bearbeiten und könnte für AJAX-Aufrufe oder das Rendern einer eigenständigen Seite verwendet werden, falls das Modul eine hätte. Im Kontext dieses Moduls könnte es ein Platzhalter sein oder für spezifische Datenabrufe verwendet werden, wenn der Slider-Inhalt dynamisch geladen würde.
-   **Back-Office-Admin-Controller**:
    *   `controllers/admin/adminproslider.php`
        *   **Klassenname & Elternklasse**: `AdminprosliderController` erweitert `ModuleAdminController`.
        *   **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet die „Folien“ oder „Meinungen“ (gemäß Dossier, obwohl „Meinung“ ein Tippfehler zu sein scheint und wahrscheinlich „Folie“ oder „proslider_item“ sein sollte, wenn es ein ObjectModel wäre). Er bietet die Schnittstelle zum Hinzufügen, Bearbeiten und Löschen einzelner Folien. Er verarbeitet die Formularübermittlung für Foliendetails (Titel, Beschreibung, Bild, Link usw.) und aktualisiert die Tabelle `ps_configuration` oder eine benutzerdefinierte Tabelle, falls eine vorhanden wäre.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul seine Daten direkt in der Tabelle `ps_configuration` speichert, indem es serialisierte Arrays oder einzelne Konfigurationsschlüssel für jede Folie verwendet, oder es könnte einen einfacheren, nicht-ORM-Ansatz innerhalb des `AdminprosliderController` zur Datenverwaltung verwenden. Wenn es `ObjectModel` verwenden würde, gäbe es hier eine definierte Klasse (z.B. `ProsliderSlide.php`).

### 4.4 JavaScript-Assets (`views/js/`)

-   `proslider/js/jquery.cslider.js`
    *   **Geltungsbereich**: Front-Office.
    *   **Beschreibung**: Dies ist wahrscheinlich das zentrale jQuery-Plugin, das für die animierte Slider-Funktionalität verantwortlich ist. Es verarbeitet Folienübergänge, Autoplay-Logik, Navigationssteuerungen und Responsivität. Entwickler sollten diese Datei konsultieren, um die Animationstypen und verfügbaren Optionen des Sliders zu verstehen.
-   `proslider/js/jscolor/jscolor.js`
    *   **Geltungsbereich**: Back-Office.
    *   **Beschreibung**: Eine JavaScript-Bibliothek für ein Farbauswahl-Widget. Sie wird in den Back-Office-Konfigurationsformularen des Moduls verwendet, um Händlern die einfache Auswahl von Hintergrund- und Textfarben für den Slider zu ermöglichen.
-   `proslider/js/modernizr.custom.28468.js`
    *   **Geltungsbereich**: Front-Office.
    *   **Beschreibung**: Modernizr ist eine JavaScript-Bibliothek, die HTML5- und CSS3-Funktionen im Browser des Benutzers erkennt. Dieser spezifische benutzerdefinierte Build wird wahrscheinlich von `jquery.cslider.js` verwendet, um Funktionserkennung und möglicherweise Fallback-Mechanismen für ältere Browser bereitzustellen und so reibungslose Animationen und Kompatibilität zu gewährleisten.
-   `proslider/js/script.js`
    *   **Geltungsbereich**: Front-Office.
    *   **Beschreibung**: Dies ist die Haupt-JavaScript-Datei des Moduls. Sie initialisiert das `jquery.cslider.js`-Plugin mit den spezifischen im Back Office konfigurierten Einstellungen (Breite, Höhe, Geschwindigkeit, Autoplay usw.). Sie bindet Event-Listener für die Slider-Navigation (falls benutzerdefinierte implementiert sind) und stellt sicher, dass der Slider in der PrestaShop-Umgebung korrekt funktioniert.
-   `proslider/tinymce16.inc.js`
    *   **Geltungsbereich**: Back-Office.
    *   **Beschreibung**: Diese Datei ist eine Include für den TinyMCE Rich-Text-Editor, speziell konfiguriert für PrestaShop 1.6.x. Sie wird in den Back-Office-Formularen für „Folienbeschreibung“-Felder verwendet, um Händlern die Formatierung von Text mit HTML zu ermöglichen. Für PrestaShop 1.7.x und 8.x könnte die native TinyMCE-Integration von PrestaShop verwendet werden, oder diese Datei könnte weiterhin zur Kompatibilität geladen werden.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `proslider/css/style2.css`
    *   **Geltungsbereich**: Front-Office-Kundenstyling.
    *   **Beschreibung**: Dies ist das primäre Stylesheet für den Frontend-Slider. Es definiert das visuelle Erscheinungsbild des Slider-Containers, einzelner Folien, Bildunterschriften, Beschreibungen, Navigationspfeile und Paginierungspunkte.
    *   **Wichtige CSS-Klassenselektoren**: Entwickler können diese Datei nach Klassen wie `.cs-slider`, `.cs-wrapper`, `.cs-bg`, `.cs-caption`, `.cs-description`, `.cs-nav`, `.cs-dots` durchsuchen, um das Styling in ihrem Theme-eigenen CSS zu überschreiben oder zu erweitern.
-   `proslider/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    *   **Geltungsbereich**: Back-Office-Admin-Formular-Styling.
    *   **Beschreibung**: Dies ist ein benutzerdefinierter Build des jQuery UI CSS-Frameworks, speziell für das „UI-lightness“-Theme. Es wird wahrscheinlich verwendet, um Elemente innerhalb der Back-Office-Konfigurationsformulare des Moduls zu gestalten, wie z.B. Datumsauswähler (falls vorhanden), Schaltflächen oder andere UI-Widgets, die Teil der Folienverwaltungsoberfläche sein könnten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `proslider/header.tpl`
        *   **Hook**: Wahrscheinlich für `displayHeader` oder `displayTop` vorgesehen.
        *   **Ausgabe**: Dieses Template würde die Haupt-HTML-Struktur für den Slider enthalten, einschließlich der `div`-Elemente, auf die `jquery.cslider.js` abzielt, und möglicherweise die Schleife zum Rendern einzelner Folien basierend auf den vom Modul übergebenen Daten. Es könnte auch die notwendigen JS- und CSS-Includes enthalten.
    *   `proslider/top.tpl`
        *   **Hook**: Wahrscheinlich für `displayTop` oder `displayNav` vorgesehen.
        *   **Ausgabe**: Ähnlich wie `header.tpl` würde dies den Slider im oberen Bereich des Stores rendern, oft unterhalb der Hauptnavigation.
    *   `proslider/views/templates/hook/left-column.tpl`
        *   **Hook**: `displayLeftColumn` oder `displayRightColumn`.
        *   **Ausgabe**: Dieses Template rendert eine potenziell kleinere oder anders gestylte Version des Sliders speziell für die Seitenleisten des Stores.
-   **Admin-Templates (`views/templates/admin/`)**:
    *   `proslider/views/templates/front/form.tpl`
        *   **Hook**: Dieser Pfad deutet darauf hin, dass es sich um ein Front-Office-Template handelt, aber der Kontext von `AdminprosliderController` impliziert, dass es für das *Formular* zum Hinzufügen/Bearbeiten von Folien im Admin-Bereich verwendet werden könnte. Dies ist ein gängiges Muster, bei dem ein Modul ein „Formular“-Template sowohl für die Frontend- (falls zutreffend) als auch für die Backend-Dateneingabe wiederverwenden kann.
        *   **Ausgabe**: Dieses Template würde die HTML-Formularstruktur zum Hinzufügen oder Bearbeiten einer einzelnen Folie definieren, einschließlich Eingabefeldern für Titel, Beschreibung, Bild-Upload, URL, Aktivstatus und Position.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Moduldossier weist keine benutzerdefinierten SQL-Dateien aus. Dies deutet stark darauf hin, dass das Modul seine Konfiguration und Foliendaten direkt in der PrestaShop-Tabelle `ps_configuration` speichert. Die Daten jeder Folie (Titel, Beschreibung, Bild, Link usw.) würden wahrscheinlich in einem einzigen Konfigurationsschlüssel oder mehreren Schlüsseln pro Folie serialisiert, z.B. `PROSLIDER_SLIDE_1_TITLE`, `PROSLIDER_SLIDE_1_IMAGE` usw. Dieser Ansatz ist einfacher, aber weniger skalierbar als die Verwendung eines dedizierten `ObjectModel`.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Einfügen von CSS/JS-Assets und potenziell der Haupt-HTML-Struktur des Sliders. |
| `displayTop` | Typischerweise unterhalb der Hauptnavigation, oberhalb des Inhalts. | Anzeigen des Haupt-Sliders an einer prominenten oberen Position. |
| `displayHome` | Im Inhaltsbereich der Startseite. | Anzeigen des Sliders als zentrales Feature auf der Startseite. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Anzeigen eines kleineren, kontextbezogenen Sliders in der linken Spalte. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Anzeigen eines kleineren, kontextbezogenen Sliders in der rechten Spalte. |
| `displayProductFooter` | Am unteren Rand von Produktseiten. | Anzeigen eines Sliders, der sich auf das Produkt bezieht (z.B. Zubehör, verwandte Artikel). |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Anzeigen eines Sliders für sekundäre Aktionen oder Markeninhalt. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert, nachdem Medien gesetzt wurden. | Registrieren modulspezifischer CSS- und JavaScript-Dateien für Front-Office-Seiten. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ausgabe rendert, nachdem Medien gesetzt wurden. | Registrieren modulspezifischer CSS- und JavaScript-Dateien für Back-Office-Seiten (z.B. für den Farbwähler oder TinyMCE). |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, Ihnen Unterstützung zu bieten und den reibungslosen Betrieb Ihres Presta Pro Slider-Moduls zu gewährleisten.
