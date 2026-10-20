---
title: "Produktseiten-Popup – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktseiten-Popup“ von MyPresta.eu."
sidebar:
  label: "Produktseiten-Popup – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product page popup auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-page-popup.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-page-popup/)
>
> ---


# Produktseiten-Popup

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation werden Sie zur Hauptkonfigurationsseite des Moduls weitergeleitet. Hier können Sie alle Ihre Produktseiten-Popups verwalten.

Die Konfigurationsseite ist in zwei Hauptbereiche unterteilt:

1. Registerkarte **„Neues Popup hinzufügen“**: Zum Erstellen neuer Popup-Fenster.
2. Registerkarte **„Liste der Popups“**: Zum Anzeigen, Bearbeiten oder Löschen bestehender Popups.

#### 2.1.1 Registerkarte „Neues Popup hinzufügen“

Diese Registerkarte ermöglicht es Ihnen, ein neues Popup-Fenster und die zugehörigen Einstellungen zu definieren.

- **Popup-Name:**

  - **Was diese Einstellung bewirkt:** Dies ist ein interner Name für Ihr Popup, der nur in Ihrem PrestaShop Back Office sichtbar ist. Er hilft Ihnen, verschiedene Popups zu identifizieren und zu verwalten.
  - **Auswirkung einer Änderung dieser Einstellung:** Eine Änderung dieses Namens wirkt sich nur darauf aus, wie Sie ihn im Back Office sehen; er hat keine Auswirkungen auf das Front Office oder das Kundenerlebnis.
  - **Empfohlener Wert:** Verwenden Sie einen beschreibenden Namen, z.B. „Sommer-Sale auf T-Shirts“, „Größentabelle für Jeans“, „Video-Tutorial für Produkt X“.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Popup für ein bestimmtes Produkt haben, benennen Sie es nach diesem Produkt, um es später leicht wiederzufinden.
- **Popup-Inhalt:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptinhalt, der im Popup-Fenster angezeigt wird. Es ist ein Rich-Text-Editor (TinyMCE), in dem Sie Text, Bilder, Videos, Links und sogar benutzerdefiniertes HTML hinzufügen können.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies ändert direkt, was Ihre Kunden sehen, wenn das Popup erscheint. Sie können es informativ, werblich oder interaktiv gestalten.
  - **Empfohlener Wert:** Halten Sie es prägnant und visuell ansprechend. Verwenden Sie Überschriften, Aufzählungspunkte und relevante Bilder.
  - **Händlerszenario / Beispiel:** Sie könnten einen Rabattcode, ein eingebettetes YouTube-Video, das das Produkt demonstriert, oder eine detaillierte Größentabelle hinzufügen.
- **Popup-Breite (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Breite des Popup-Fensters in Pixeln.
  - **Auswirkung einer Änderung dieser Einstellung:** Eine größere Breite macht das Popup breiter und kann horizontal mehr Inhalt aufnehmen. Eine kleinere Breite macht es schmaler.
  - **Empfohlener Wert:** Beginnen Sie mit `600px` und passen Sie ihn basierend auf Ihrem Inhalt an. Stellen Sie sicher, dass es auf verschiedenen Bildschirmgrößen gut aussieht.
  - **Händlerszenario / Beispiel:** Wenn Ihr Popup ein breites Bild oder eine Tabelle enthält, benötigen Sie möglicherweise eine größere Breite. Für einfachen Text könnte eine geringere Breite ausreichen.
- **Popup-Höhe (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Höhe des Popup-Fensters in Pixeln.
  - **Auswirkung einer Änderung dieser Einstellung:** Eine größere Höhe macht das Popup höher und ermöglicht mehr vertikalen Inhalt ohne Scrollen. Eine kleinere Höhe macht es kürzer und erfordert möglicherweise Scrollen, wenn der Inhalt die Höhe überschreitet.
  - **Empfohlener Wert:** Beginnen Sie mit `400px` und passen Sie ihn basierend auf Ihrem Inhalt an.
  - **Händlerszenario / Beispiel:** Wenn Sie eine lange Textbeschreibung oder ein hohes Bild haben, erhöhen Sie die Höhe. Wenn der Inhalt kurz ist, sieht eine geringere Höhe sauberer aus.
- **Popup-Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Hintergrundfarbe des Popup-Fensters selbst. Hierfür wird ein Farbwähler verwendet.
  - **Auswirkung einer Änderung dieser Einstellung:** Ändert das visuelle Erscheinungsbild des Popups und hilft ihm, zum Branding Ihres Shops zu passen oder hervorzustechen.
  - **Empfohlener Wert:** Wählen Sie eine Farbe, die das Design Ihres Shops ergänzt und eine gute Lesbarkeit Ihres Inhalts gewährleistet.
  - **Händlerszenario / Beispiel:** Verwenden Sie die Primärfarbe Ihrer Marke für den Hintergrund oder ein neutrales Weiß/Hellgrau für maximale Lesbarkeit.
- **Popup-Rahmenfarbe:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Farbe des Rahmens um das Popup-Fenster.
  - **Auswirkung einer Änderung dieser Einstellung:** Fügt dem Popup einen visuellen Rahmen hinzu, der seine Kanten definiert.
  - **Empfohlener Wert:** Oft eine dezente Rahmenfarbe, die zur Ästhetik Ihres Shops passt, oder eine Kontrastfarbe, um das Popup hervorzuheben.
  - **Händlerszenario / Beispiel:** Ein hellgrauer Rahmen für einen sauberen Look oder eine lebendige Farbe, wenn das Popup sehr aufmerksamkeitsstark sein soll.
- **Popup-Rahmenbreite (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Dicke des Popup-Rahmens in Pixeln.
  - **Auswirkung einer Änderung dieser Einstellung:** Ein höherer Wert macht den Rahmen dicker und prominenter.
  - **Empfohlener Wert:** `1px` oder `2px` für einen dezenten Rahmen.
  - **Händlerszenario / Beispiel:** Ein `5px`-Rahmen könnte für eine sehr auffällige, dringende Nachricht verwendet werden, während `1px` für allgemeine Informationen üblicher ist.
- **Popup-Rahmenradius (px):**

  - **Was diese Einstellung bewirkt:** Steuert die Rundung der Ecken des Popups. Ein Wert von `0` bedeutet scharfe, eckige Ecken. Höhere Werte erzeugen stärker abgerundete Ecken.
  - **Auswirkung einer Änderung dieser Einstellung:** Beeinflusst die Gesamtästhetik des Popups und lässt es weicher oder moderner wirken.
  - **Empfohlener Wert:** `0px` für scharfe Ecken, `5px` bis `10px` für leicht abgerundete Ecken.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop-Design abgerundete Elemente verwendet, würde ein `10px`-Rahmenradius das Popup besser integrieren.
- **Popup-Overlay-Farbe:**

  - **Was diese Einstellung bewirkt:** Dies ist die Farbe der halbtransparenten Ebene, die hinter dem Popup erscheint und den Rest der Produktseite abdunkelt.
  - **Auswirkung einer Änderung dieser Einstellung:** Ändert den visuellen Kontrast zwischen dem Popup und dem Hintergrund. Ein dunkleres Overlay lässt das Popup stärker hervorstechen.
  - **Empfohlener Wert:** Ein halbtransparentes Schwarz (`#000000` mit etwas Transparenz) ist Standard.
  - **Händlerszenario / Beispiel:** Ein etwas helleres Overlay könnte verwendet werden, wenn Sie möchten, dass die Hintergrund-Produktinformationen noch etwas sichtbar sind.
- **Popup-Overlay-Deckkraft (0-100):**

  - **Was diese Einstellung bewirkt:** Steuert die Transparenz der Overlay-Farbe. `0` ist vollständig transparent (unsichtbar), `100` ist vollständig undurchsichtig (durchgehende Farbe, verbirgt den Hintergrund vollständig).
  - **Auswirkung einer Änderung dieser Einstellung:** Bestimmt, wie viel von der darunter liegenden Produktseite durch das Overlay sichtbar ist.
  - **Empfohlener Wert:** `70` bis `80` ist ein gutes Gleichgewicht, das das Popup prominent macht, ohne die Seite vollständig zu verdecken.
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass der Kunde das Produktbild hinter dem Popup noch schwach sehen kann, verwenden Sie eine geringere Deckkraft wie `50`.
- **Produkte für dieses Popup:**

  - **Was diese Einstellung bewirkt:** Dies ist der entscheidende Teil, in dem Sie auswählen, welche spezifischen Produkte dieses Popup auslösen sollen. Sie können Produkte nach Namen suchen.
  - **Auswirkung einer Änderung dieser Einstellung:** Das Popup erscheint *nur* auf den von Ihnen hier ausgewählten Produktseiten. Wenn keine Produkte ausgewählt sind, erscheint das Popup nirgendwo.
  - **Empfohlener Wert:** Wählen Sie alle relevanten Produkte für diese spezifische Nachricht aus.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Popup mit einer Größentabelle für „Herren-T-Shirts“ erstellt haben, würden Sie hier alle Ihre Herren-T-Shirt-Produkte auswählen.

Nachdem Sie alle Einstellungen konfiguriert haben, klicken Sie auf die Schaltfläche **„Speichern“**, um Ihr neues Popup zu erstellen.

#### 2.1.2 Registerkarte „Liste der Popups“

Diese Registerkarte zeigt eine Tabelle aller von Ihnen erstellten Popups an.

- **Tabellenspalten:**
  - **ID:** Eindeutiger Bezeichner für das Popup.
  - **Name:** Der interne Name, den Sie dem Popup gegeben haben.
  - **Produkte:** Listet die Anzahl der mit diesem Popup verknüpften Produkte auf.
  - **Aktionen:**
    - **Bearbeiten:** Klicken Sie auf das Bleistiftsymbol, um zur Registerkarte „Neues Popup hinzufügen“ zurückzukehren, wobei alle Einstellungen des aktuellen Popups vorausgefüllt sind, sodass Sie sie ändern können.
    - **Löschen:** Klicken Sie auf das Mülleimersymbol, um das Popup dauerhaft zu entfernen. Eine Bestätigungsaufforderung wird angezeigt.
- **Auswirkung von Änderungen:**
  - **Bearbeiten:** Ermöglicht Ihnen, Inhalt, Stil oder Produktzuordnungen für ein bestehendes Popup zu aktualisieren, ohne ein neues zu erstellen.
  - **Löschen:** Entfernt das Popup dauerhaft aus Ihrem Shop. Es wird auf keiner Produktseite mehr angezeigt.
- **Empfohlener Arbeitsablauf:** Überprüfen Sie diese Liste regelmäßig, um sicherzustellen, dass alle Ihre Popups aktuell und relevant sind. Löschen Sie veraltete Aktionen oder Informationen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Neues Popup hinzufügen** | Popup-Name | Beschreibender Name | Interne Identifikation für das Back Office. |
| | Popup-Inhalt | Benutzerdefiniertes HTML/Text | Hauptnachricht, die dem Kunden angezeigt wird. |
| | Popup-Breite (px) | 600px | Horizontale Größe des Popups. |
| | Popup-Höhe (px) | 400px | Vertikale Größe des Popups. |
| | Popup-Hintergrundfarbe | Weiß / Markenfarbe | Hintergrundfarbe des Popup-Inhaltsbereichs. |
| | Popup-Rahmenfarbe | Dezent / Markenfarbe | Farbe des Rahmens um das Popup. |
| | Popup-Rahmenbreite (px) | 1px - 2px | Dicke des Popup-Rahmens. |
| | Popup-Rahmenradius (px) | 0px - 10px | Rundung der Popup-Ecken. |
| | Popup-Overlay-Farbe | Halbtransparentes Schwarz | Farbe des abgedunkelten Hintergrunds. |
| | Popup-Overlay-Deckkraft (0-100) | 70 - 80 | Transparenz des Hintergrund-Overlays. |
| | Produkte für dieses Popup | Relevante Produkte auswählen | Bestimmt, auf welchen Produktseiten das Popup erscheint. |
| **Liste der Popups** | Aktion Bearbeiten | N/A | Einstellungen eines bestehenden Popups ändern. |
| | Aktion Löschen | N/A | Ein Popup dauerhaft entfernen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Popup erscheint nicht auf der Produktseite. Was sollte ich überprüfen?**
A:

1. **Ist das Popup dem richtigen Produkt zugeordnet?** Gehen Sie zur Modulkonfiguration, bearbeiten Sie Ihr Popup und stellen Sie sicher, dass das spezifische Produkt, auf dem Sie testen, im Feld „Produkte für dieses Popup“ ausgewählt ist.
2. **Ist das Modul aktiviert?** Stellen Sie unter **Module > Modul-Manager** sicher, dass „Produktseiten-Popup“ installiert und aktiviert ist.
3. **Leeren Sie Ihren PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Ihr Browser-Cache muss möglicherweise ebenfalls geleert werden (Strg+F5 oder Cmd+R).
4. **Überprüfen Sie auf JavaScript-Fehler:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12) und suchen Sie im Tab „Konsole“ nach Fehlern. Wenn Sie Fehler sehen, könnte dies auf einen Konflikt mit einem anderen Modul oder Ihrem Theme hinweisen.

**F: Das Popup sieht seltsam aus oder passt nicht zum Styling meines Themes.**
A:

1. **Überprüfen Sie die Popup-Styling-Einstellungen:** Überprüfen Sie die Einstellungen „Popup-Hintergrundfarbe“, „Popup-Rahmenfarbe“, „Popup-Rahmenbreite“ und „Popup-Rahmenradius“ in der Modulkonfiguration.
2. **Theme-Konflikte:** Das CSS Ihres Themes könnte die Stile des Moduls überschreiben. Wenn Sie mit CSS vertraut sind, können Sie die Popup-Elemente mit den Entwicklertools Ihres Browsers untersuchen, um widersprüchliche Stile zu identifizieren. Bei komplexen Styling-Problemen benötigen Sie möglicherweise die Hilfe eines Webentwicklers.

**F: Kann ich mehrere Popups auf derselben Produktseite haben?**
A: Nein, das Modul ist so konzipiert, dass es ein spezifisches Popup pro Produktseite anzeigt. Wenn ein Produkt mit mehreren Popups verknüpft ist, wird nur eines angezeigt (typischerweise das erste gefundene oder das mit der niedrigsten ID, obwohl dieses Verhalten nicht explizit garantiert ist und vermieden werden sollte). Es ist Best Practice, ein umfassendes Popup pro Produkt oder Produktgruppe zu erstellen.

**F: Wie übersetze ich den Popup-Inhalt in verschiedene Sprachen?**
A: Das Feld „Popup-Inhalt“ in der Modulkonfiguration sollte Sprachregisterkarten anbieten, wenn Ihr PrestaShop-Shop mehrere Sprachen aktiviert hat. Wechseln Sie einfach zur gewünschten Sprachregisterkarte und geben Sie den übersetzten Inhalt für diese Sprache ein.

**F: Der Popup-Inhalt ist zu lang und erfordert Scrollen. Wie kann ich das beheben?**
A:

1. **Popup-Höhe erhöhen:** Erhöhen Sie in der Modulkonfiguration den Wert für „Popup-Höhe (px)“.
2. **Inhalt verdichten:** Versuchen Sie, Ihren Popup-Inhalt prägnanter zu gestalten. Verwenden Sie Aufzählungspunkte, kürzere Absätze und verlinken Sie bei sehr detaillierten Informationen, wenn möglich, auf externe Seiten.
3. **Bilder/Videos optimieren:** Stellen Sie sicher, dass alle Medien in Ihrem Popup für die Webnutzung optimiert sind, um übermäßige Ladezeiten zu vermeiden und die Anzeige zu verbessern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Product page popup` für PrestaShop 1.5.x und 1.6.x folgt einem einfachen, monolithischen Designmuster, das typisch für ältere PrestaShop-Module ist. Es verwendet hauptsächlich die `Module`-Klasse für seine Kernfunktionalität, die Installation, Deinstallation und Konfiguration. Die Front-Office-Anzeige wird durch das Einhaken in Standard-Anzeigepunkte verwaltet, während die Konfiguration über die Methode `getContent()` innerhalb der Hauptmoduldatei erfolgt. Daten werden direkt in `ps_configuration` gespeichert und über Standard-PrestaShop-Datenbankinteraktionen verwaltet. Es gibt keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Front-/Admin-Controller über die Hauptmoduldatei hinaus.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller im Verzeichnis `controllers/`. Die gesamte Front-Office-Logik wird direkt in der Hauptmoduldatei über Hooks behandelt, und die gesamte Back-Office-Konfiguration wird von der Methode `getContent()` der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält keine benutzerdefinierten PHP-Klassen oder Modelle im Verzeichnis `classes/`. Die gesamte Datenverarbeitung und Geschäftslogik ist in der Hauptmoduldatei `ajax_productpopup.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- **`productpopup/js/jscolor/jscolor.js`**
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters, die eine Farbwählerfunktion bereitstellt. Sie wird im Konfigurationsformular des Moduls verwendet, um Händlern die einfache Auswahl von Farben für den Popup-Hintergrund, den Rahmen und das Overlay zu ermöglichen. Sie funktioniert typischerweise, indem sie sich an Eingabefelder mit einer bestimmten Klasse (z.B. `jscolor`) anfügt.
- **`productpopup/js/script.js`**
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Dieses Skript enthält die Kernlogik für die Anzeige des Popups im Front Office.
    - **Ereignis-Listener:** Es lauscht wahrscheinlich auf das `DOMContentLoaded`-Ereignis oder Ähnliches, um sicherzustellen, dass die Seite vollständig geladen ist.
    - **DOM-Manipulation:** Es ist verantwortlich für:
      - Überprüfen, ob die aktuelle Produkt-ID ein zugehöriges Popup hat.
      - Dynamisches Erstellen der Popup-HTML-Struktur (Overlay, Popup-Container, Inhaltsbereich, Schließen-Schaltfläche).
      - Einfügen des Popup-Inhalts (aus der Modulkonfiguration abgerufen).
      - Anwenden der konfigurierten Stile (Breite, Höhe, Farben, Rahmen, Deckkraft).
      - Anzeigen des Popups mit einer Animation (z.B. Einblenden).
      - Binden von Ereignissen zum Schließen des Popups (Klick auf Schließen-Schaltfläche, Klick auf Overlay, ESC-Taste).
- **`productpopup/js/tinymce16.inc.js`**
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Diese Datei ist ein Integrationsskript für den TinyMCE Rich-Text-Editor, speziell zugeschnitten auf PrestaShop 1.6.x Umgebungen. Es initialisiert den TinyMCE-Editor für den Textbereich „Popup-Inhalt“ im Konfigurationsformular des Moduls und bietet dem Händler eine WYSIWYG-Oberfläche zum Erstellen von reichhaltigem HTML-Inhalt für die Popups. Es konfiguriert TinyMCE-Optionen wie verfügbare Schaltflächen, Plugins und Spracheinstellungen.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`productpopup/css/productpopup.css`**
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Dieses Stylesheet definiert das Standard-Erscheinungsbild und Layout des Produktseiten-Popups und seines Overlays.
    - **Haupt-UI-Komponenten:** Stile für das `.productpopup-overlay` (der abgedunkelte Hintergrund) und den `.productpopup-container` (die eigentliche Popup-Box).
    - **Wichtige CSS-Klassenselektoren:**
      - `.productpopup-overlay`: Steuert `position`, `top`, `left`, `width`, `height`, `background-color`, `opacity`, `z-index`.
      - `.productpopup-container`: Steuert `position`, `top`, `left`, `transform` (zum Zentrieren), `background-color`, `border`, `border-radius`, `box-shadow`, `z-index`, `overflow`.
      - `.productpopup-content`: Stile für den inneren Inhaltsbereich, einschließlich `padding`, `font-size`, `line-height`.
      - `.productpopup-close`: Stile für die Schließen-Schaltfläche (z.B. `position`, `top`, `right`, `font-size`, `color`, `cursor`).
    - **Entwickler-Override:** Entwickler können diese Stile im `global.css` ihres Themes oder durch Erstellen eines benutzerdefinierten Stylesheets, das nach diesem geladen wird, überschreiben, indem sie diese spezifischen Klassen ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Dieses Modul definiert keine expliziten Templates für spezifische Hooks in diesem Verzeichnis. Das Front-Office-Popup-HTML wird wahrscheinlich dynamisch von `script.js` basierend auf der Konfiguration generiert.
- **Admin-Templates (`views/templates/admin/`)**:
  - **`productpopup/views/templates/admin/tabs-no-product.tpl`**
    - **Beschreibung:** Dieses Template wird wahrscheinlich innerhalb der `getContent()`-Methode des Moduls verwendet, um das Formular „Neues Popup hinzufügen“ zu rendern, wenn kein spezifisches Popup bearbeitet wird, oder vielleicht eine vereinfachte Version des Formulars. Es enthält die Eingabefelder für Popup-Namen, Inhalt, Abmessungen, Farben und die Produktauswahloberfläche.
  - **`productpopup/views/templates/admin/tabs.tpl`**
    - **Beschreibung:** Dies ist das Haupttemplate für die Back-Office-Konfigurationsseite des Moduls. Es rendert typischerweise die Tab-Struktur (z.B. „Neues Popup hinzufügen“ und „Liste der Popups“) und enthält den Inhalt anderer Admin-Templates (wie `tabs-no-product.tpl`) innerhalb seiner Tab-Bereiche. Es rendert auch die Tabelle zur Auflistung bestehender Popups.
- **Front-Office-Templates (`views/templates/front/`)**:
  - **`productpopup/views/templates/front/footer.tpl`**
    - **Beschreibung:** Dieses Template wird wahrscheinlich verwendet, um einen kleinen, versteckten HTML-Container oder eine JavaScript-Variable auszugeben, die die Popup-Daten (Inhalt, Stile, Produkt-IDs) für das Front-Office-Skript `script.js` enthält, damit es das Popup dynamisch aufnehmen und rendern kann. Es wird typischerweise in `displayFooter` oder `displayHeader` eingehakt, um sicherzustellen, dass die Daten bei jedem Seitenaufruf verfügbar sind.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen und Popup-Daten werden in der Standard-PrestaShop-Konfigurationstabelle gespeichert: `ps_configuration`.
  - **Konfigurationsschlüssel**:
    - `PRODUCTPOPUP_DATA`: Speichert serialisierte Daten für alle erstellten Popups, einschließlich ihres Inhalts, Stylings und der zugehörigen Produkt-IDs. Dieser Schlüssel enthält eine komplexe Array-Struktur.
    - Andere Schlüssel könnten für globale Moduleinstellungen existieren, falls vorhanden, aber die primären Daten befinden sich in `PRODUCTPOPUP_DATA`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Wahrscheinlich zum Einbinden von CSS- und JavaScript-Dateien (`productpopup.css`, `script.js`) für die Front-Office-Popup-Funktionalität verwendet. |
| `displayFooter` | Wird am Ende des `<body>`-Bereichs jeder Seite ausgeführt. | Könnte verwendet werden, um die versteckten Daten für `script.js` auszugeben oder um sicherzustellen, dass die HTML-Struktur des Popups nach allen anderen Inhalten an das DOM angehängt wird. |
| `displayProductTab` (PrestaShop 1.6.x) / `displayProductExtraContent` (PrestaShop 1.7+) | Wird auf der Produktseite ausgeführt, typischerweise innerhalb der Produkt-Tabs oder des zusätzlichen Inhaltsbereichs. | Obwohl die Modulbeschreibung ein modales Fenster impliziert, könnte dieser Hook verwendet werden, um einen Trigger für das Popup einzufügen oder um sicherzustellen, dass sein JS speziell auf Produktseiten geladen wird. |
| `displayRightColumn` / `displayLeftColumn` | Wird in den Seitenleisten des Shops ausgeführt. | Weniger wahrscheinlich für ein Produktseiten-Popup, könnte aber verwendet werden, um einen globalen Trigger oder ein kleines Skript einzufügen, falls erforderlich. |
| `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Wird ausgeführt, wenn ein Produkt hinzugefügt, aktualisiert oder gelöscht wird. | Könnte verwendet werden, um die `PRODUCTPOPUP_DATA` in `ps_configuration` zu aktualisieren oder zu bereinigen, wenn ein mit einem Popup verknüpftes Produkt entfernt wird. |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwicklersupport wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Stellen Sie sicher, dass Sie die neueste Version des Moduls „Produktseiten-Popup“ herunterladen, die mit Ihrer PrestaShop-Installation kompatibel ist. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
