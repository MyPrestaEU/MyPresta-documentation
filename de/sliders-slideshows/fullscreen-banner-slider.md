---
title: "Fullscreen Banner Slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Fullscreen Banner Slider von MyPresta.eu."
sidebar:
  label: "Fullscreen Banner Slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Fullscreen Banner Slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/fullscreen-banner-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/fullscreen-banner-slider/)
>
> ---


# Fullscreen Banner Slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Fullscreen Banner Slider“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm, wo Sie alle Aspekte Ihres Sliders verwalten können.

Die Konfiguration des Moduls erfolgt über die Methode `getContent()` in der Hauptmoduldatei und präsentiert ein Standard-PrestaShop-Konfigurationsformular.

#### **Allgemeine Einstellungen**

- **Was diese Einstellung bewirkt:** Diese Einstellungen steuern das Gesamtverhalten und Aussehen Ihres bildschirmfüllenden Sliders.
- **Auswirkung der Änderung dieser Einstellung:** Das Anpassen dieser Werte wirkt sich direkt darauf aus, wie der Slider Ihren Kunden angezeigt wird, seine Größe, Geschwindigkeit und ob er aktiv ist.

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Fullscreen Slider aktivieren** | JA | **Zweck:** Schaltet die gesamte Slider-Funktion ein oder aus.   **Auswirkung:**   *Wenn aktiviert:* Der Fullscreen Slider wird neuen Besuchern angezeigt.   *Wenn deaktiviert:* Der Slider wird in Ihrem Shop nicht angezeigt.   **Empfohlen:** JA, um die Funktion zu aktivieren. |
| **Slider-Breite** | 100% | **Zweck:** Definiert die Breite des Sliders.   **Auswirkung:**   *Auf 100% eingestellt (empfohlen):* Der Slider erstreckt sich über die gesamte Breite des Browserfensters.   *Auf einen festen Pixelwert eingestellt (z.B. 1200px):* Der Slider hat eine feste Breite, wodurch auf sehr breiten Bildschirmen möglicherweise leerer Raum entsteht.   **Empfohlen:** 100% für ein echtes Fullscreen-Erlebnis. |
| **Slider-Höhe** | 100% | **Zweck:** Definiert die Höhe des Sliders.   **Auswirkung:**   *Auf 100% eingestellt (empfohlen):* Der Slider erstreckt sich über die gesamte Höhe des Browserfensters.   *Auf einen festen Pixelwert eingestellt (z.B. 800px):* Der Slider hat eine feste Höhe, wodurch auf sehr hohen oder kurzen Bildschirmen möglicherweise leerer Raum entsteht.   **Empfohlen:** 100% für ein echtes Fullscreen-Erlebnis. |
| **Animationstyp** | (Dropdown mit verschiedenen Optionen) | **Zweck:** Wählt den visuellen Übergangseffekt zwischen den Bannern.   **Auswirkung:** Jede Option bietet einen anderen Animationsstil (z.B. Überblenden, Schieben, Würfel usw.). Experimentieren Sie, um einen zu finden, der zu Ihrer Marke passt.   **Empfohlen:** Wählen Sie eine Animation, die flüssig und nicht zu ablenkend ist. „Überblenden“ oder „Schieben“ sind oft gute Ausgangspunkte. |
| **Animationsgeschwindigkeit (ms)** | 800 | **Zweck:** Steuert, wie schnell der Übergang zwischen den Bannern erfolgt, in Millisekunden (1000ms = 1 Sekunde).   **Auswirkung:**   *Höherer Wert (z.B. 1500):* Langsamere, sanftere Übergänge.   *Niedrigerer Wert (z.B. 400):* Schnellere, knackigere Übergänge.   **Empfohlen:** 800-1000ms für ein ausgewogenes, professionelles Gefühl. |
| **Intervall zwischen den Folien (ms)** | 3000 | **Zweck:** Legt die Dauer fest, für die jedes Banner angezeigt wird, bevor zum nächsten übergegangen wird, in Millisekunden.   **Auswirkung:**   *Höherer Wert (z.B. 5000):* Banner bleiben länger auf dem Bildschirm, was Besuchern mehr Zeit zum Lesen/Ansehen gibt.   *Niedrigerer Wert (z.B. 2000):* Banner wechseln schneller, wodurch ein dynamisches Gefühl entsteht.   **Empfohlen:** 3000-5000ms, abhängig von der Komplexität Ihres Bannerinhalts. |
| **Navigationspfeile anzeigen** | JA | **Zweck:** Bestimmt, ob „Weiter“- und „Zurück“-Pfeile für die manuelle Foliennavigation sichtbar sind.   **Auswirkung:**   *Wenn aktiviert:* Pfeile erscheinen an den Seiten des Sliders, sodass Benutzer durch die Banner klicken können.   *Wenn deaktiviert:* Banner wechseln nur automatisch basierend auf dem Intervall.   **Empfohlen:** JA, für eine bessere Benutzerkontrolle. |
| **Paginierungspunkte anzeigen** | JA | **Zweck:** Bestimmt, ob kleine Punkte (oder Miniaturansichten), die jede Folie darstellen, sichtbar sind, normalerweise am unteren Rand des Sliders.   **Auswirkung:**   *Wenn aktiviert:* Punkte erscheinen, sodass Benutzer sehen können, wie viele Folien es gibt und zu einer bestimmten springen können.   *Wenn deaktiviert:* Keine visuelle Anzeige der Folienanzahl oder direkten Navigation.   **Empfohlen:** JA, für eine bessere Benutzerorientierung und Navigation. |
| **Slider automatisch abspielen** | JA | **Zweck:** Steuert, ob der Slider automatisch durch die Banner blättert.   **Auswirkung:**   *Wenn aktiviert:* Banner wechseln automatisch nach dem festgelegten Intervall.   *Wenn deaktiviert:* Banner wechseln nur, wenn der Benutzer auf Navigationspfeile oder Paginierungspunkte klickt.   **Empfohlen:** JA, um sicherzustellen, dass alle Ihre Nachrichten gesehen werden. |
| **Text des Schließen-Buttons** | Schließen | **Zweck:** Ermöglicht die Anpassung des Textes, der auf der Schaltfläche angezeigt wird, die den Fullscreen Slider schließt.   **Auswirkung:** Ändert den Text auf der Schaltfläche.   **Empfohlen:** „Schließen“, „Überspringen“ oder „Zum Shop fortfahren“. |
| **Cookie-Ablauf (Tage)** | 7 | **Zweck:** Legt fest, wie lange das Modul sich merkt, dass ein Benutzer den Slider gesehen hat, um zu verhindern, dass er erneut angezeigt wird.   **Auswirkung:**   *Auf 7 Tage eingestellt:* Der Slider wird für denselben Benutzer nach 7 Tagen wieder angezeigt.   *Auf 0 eingestellt:* Der Slider wird bei jedem Besuch angezeigt (nicht empfohlen für die Benutzererfahrung).   *Auf eine hohe Zahl eingestellt (z.B. 365):* Der Slider wird für wiederkehrende Besucher nur einmal im Jahr angezeigt.   **Empfohlen:** 7 Tage ist ein gutes Gleichgewicht, um wiederkehrende Besucher regelmäßig mit neuen Angeboten zu erreichen, ohne aufdringlich zu sein. |

#### **Banner-Verwaltung**

Dieser Abschnitt ermöglicht es Ihnen, die einzelnen Banner, die in Ihrem Slider angezeigt werden, hinzuzufügen, zu bearbeiten und zu entfernen.

- **Was diese Einstellung bewirkt:** Jeder Eintrag hier repräsentiert ein Bild (Banner) in Ihrem Slider. Sie können das Bild hochladen, es mit einer bestimmten Seite verknüpfen und seine Anzeigereihenfolge festlegen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Hinzufügen eines neuen Banners:* Fügt eine neue Folie in Ihre Rotation ein.
  - *Bearbeiten eines Banners:* Aktualisiert sein Bild, seinen Link oder seine Position.
  - *Löschen eines Banners:* Entfernt es aus dem Slider.

Für jedes Banner finden Sie typischerweise Felder wie:

- **Banner-Bild:** Laden Sie die Bilddatei für Ihre Folie hoch. Stellen Sie sicher, dass die Bilder hochauflösend und für das Web optimiert sind, um schnelle Ladezeiten zu gewährleisten.
- **Banner-Link (URL):** Die Webadresse (URL), zu der Kunden weitergeleitet werden, wenn sie auf dieses Banner klicken. Lassen Sie das Feld leer, wenn das Banner rein informativ ist.
- **Anzeigereihenfolge:** Ein numerischer Wert, der die Reihenfolge der Banner bestimmt. Banner mit niedrigeren Zahlen erscheinen zuerst.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|
| Modulkonfiguration | Fullscreen Slider aktivieren | JA | Aktiviert/deaktiviert die gesamte Slider-Funktion. |
| Modulkonfiguration | Slider-Breite | 100% | Legt die Breite des Sliders fest (z.B. 100% für volle Breite). |
| Modulkonfiguration | Slider-Höhe | 100% | Legt die Höhe des Sliders fest (z.B. 100% für volle Höhe). |
| Modulkonfiguration | Animationstyp | (Verschiedene) | Wählt den visuellen Übergangseffekt zwischen den Folien. |
| Modulkonfiguration | Animationsgeschwindigkeit (ms) | 800 | Steuert die Geschwindigkeit der Folienübergänge. |
| Modulkonfiguration | Intervall zwischen den Folien (ms) | 3000 | Legt fest, wie lange jedes Banner angezeigt wird. |
| Modulkonfiguration | Navigationspfeile anzeigen | JA | Zeigt/versteckt Pfeile für die manuelle Foliennavigation. |
| Modulkonfiguration | Paginierungspunkte anzeigen | JA | Zeigt/versteckt Punkte/Miniaturansichten für den direkten Folienzugriff. |
| Modulkonfiguration | Slider automatisch abspielen | JA | Aktiviert/deaktiviert den automatischen Folienfortschritt. |
| Modulkonfiguration | Text des Schließen-Buttons | Schließen | Passt den Text auf der Schließen-Schaltfläche des Sliders an. |
| Modulkonfiguration | Cookie-Ablauf (Tage) | 7 | Bestimmt, wie lange ein Benutzer den Slider nach dem Schließen nicht mehr sieht. |
| Modulkonfiguration | Banner-Bild | (Hochladen) | Lädt das Bild für eine einzelne Folie hoch. |
| Modulkonfiguration | Banner-Link (URL) | (Leer) | Legt die Ziel-URL fest, wenn auf ein Banner geklickt wird. |
| Modulkonfiguration | Anzeigereihenfolge | (Nummer) | Definiert die Reihenfolge, in der Banner erscheinen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Slider wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Fullscreen Banner Slider“ installiert und aktiviert ist.
2. **Konfiguration:** Überprüfen Sie, ob „Fullscreen Slider aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
3. **Cookie-Ablauf:** Wenn Sie den Slider zuvor gesehen haben, könnte dies am Cookie liegen. Versuchen Sie, die Cookies Ihres Browsers zu löschen oder Ihren Shop in einem Inkognito-/privaten Browsing-Fenster zu öffnen, um einen erstmaligen Besucher zu simulieren.
4. **Cache:** Leeren Sie Ihren PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung**. Leeren Sie auch den Cache Ihres Browsers.
5. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können benutzerdefinierte Themes manchmal Störungen verursachen. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob der Slider erscheint. Wenn ja, benötigt Ihr Theme möglicherweise eine kleine Anpassung (kontaktieren Sie Ihren Theme-Entwickler oder einen Webmaster).

**F: Meine Bannerbilder sehen unscharf oder verzerrt aus. Wie kann ich das beheben?**
A: Dies geschieht normalerweise, wenn Ihre hochgeladenen Bilder keine ausreichend hohe Auflösung haben oder falsche Seitenverhältnisse für eine Vollbildanzeige aufweisen.

1. **Bildqualität:** Verwenden Sie immer hochauflösende Bilder.
2. **Seitenverhältnis:** Obwohl das Modul skaliert, versuchen Sie, Bilder zu verwenden, die breit und relativ kurz sind, geeignet für ein Vollbild-Banner (z.B. 1920x1080 Pixel oder ähnliche Breitformate). Vermeiden Sie sehr hohe oder schmale Bilder.
3. **Optimierung:** Stellen Sie sicher, dass Ihre Bilder für das Web optimiert (komprimiert) sind, um langsame Ladezeiten zu vermeiden, auch wenn sie hochauflösend sind.

**F: Kann ich verschiedene Slider für verschiedene Seiten oder Kundengruppen haben?**
A: Diese spezifische Version des Fullscreen Banner Slider-Moduls ist für eine einzelne, websiteweite Vollbildanzeige konzipiert, die einmal pro Besuchersitzung/Cookie erscheint. Es bietet keine erweiterten Targeting-Optionen für bestimmte Seiten oder Kundengruppen. Wenn Sie eine solche Funktionalität benötigen, benötigen Sie möglicherweise ein fortschrittlicheres Banner-Management-Modul oder eine kundenspezifische Entwicklung.

**F: Wie übersetze ich den Text der Schaltfläche „Schließen“ in andere Sprachen?**
A:

1. Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“ als Übersetzungstyp.
3. Wählen Sie Ihr Theme aus.
4. Wählen Sie die Sprache aus, in die Sie übersetzen möchten.
5. Suchen Sie das Modul „Fullscreen Banner Slider“ in der Liste. Dort sollten Sie das Feld „Text des Schließen-Buttons“ zur Übersetzung finden. Speichern Sie Ihre Änderungen.

**F: Der Slider erscheint, aber die Animationen funktionieren nicht oder das Layout ist fehlerhaft.**
A:

1. **JavaScript-Konflikte:** Dies liegt oft an Konflikten mit dem JavaScript anderer Module oder dem JavaScript Ihres Themes. Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12-Taste) auf JavaScript-Fehler.
2. **CSS-Konflikte:** Ähnlich wie bei JS kann das CSS Ihres Themes die Stile des Moduls überschreiben.
3. **Modul-Neuinstallation:** Manchmal kann eine Neuinstallation unerwartete Probleme beheben. Deinstallieren Sie das Modul (ohne Daten zu löschen, wenn Sie dazu aufgefordert werden) und installieren Sie es dann erneut.
   Wenn Fehler weiterhin bestehen, wenden Sie sich an einen Webmaster oder kontaktieren Sie den MyPresta.eu-Support mit den Details aus der Entwicklerkonsole Ihres Browsers.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Fullscreen Banner Slider (`fullscreenslider`) ist ein Standard-PrestaShop-Modul, das hauptsächlich in seiner Haupt-PHP-Datei `ajax_fullscreenslider.php` implementiert ist. Es nutzt die `Module`-Klasse von PrestaShop für Installation, Deinstallation und Konfiguration (`getContent()`). Die Front-Office-Anzeige wird durch das Einhaken in `displayHeader` und das Rendern einer Smarty-Vorlage verwaltet. Die Slider-Funktionalität selbst basiert auf externen jQuery-Plugins (`jquery.skitter.js`, `jquery.easing.1.3.js`) für Animationen und `noconflict.js`, um die jQuery-Kompatibilität sicherzustellen. Konfigurationswerte werden in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird innerhalb der Methode `getContent()` der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen im Verzeichnis `classes/`. Alle Daten (Bannerbilder, Links, Reihenfolge) werden direkt über die Konfigurationseinstellungen des Moduls verwaltet, typischerweise serialisiert und in `ps_configuration` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, hauptsächlich für die Kernfunktionalität und Animationen des Sliders. Diese werden typischerweise im Front-Office geladen.

- `fullscreenslider/js/jquery.easing.1.3.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Bietet zusätzliche Easing-Funktionen für jQuery-Animationen, die vielfältigere und flüssigere Übergangseffekte über die Standard-Linear- oder Swing-Animation hinaus ermöglichen. Dies ist eine Abhängigkeit für `jquery.skitter.js`.
- `fullscreenslider/js/jquery.skitter.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dies ist das Haupt-jQuery-Plugin, das für die Funktionalität des Sliders verantwortlich ist. Es verwaltet das Laden von Bildern, Animationsübergänge, Navigation (Pfeile, Paginierung), Autoplay und die Ereignisbindung für Benutzerinteraktionen. Es initialisiert den Slider basierend auf den vom Modul übergebenen Konfigurationseinstellungen.
- `fullscreenslider/js/noconflict.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript ist entscheidend für die Sicherstellung der Kompatibilität, wenn mehrere JavaScript-Bibliotheken (insbesondere verschiedene jQuery-Versionen) auf derselben Seite geladen werden. Es umschließt jQuery-Code typischerweise in einen sofort aufgerufenen Funktionsausdruck (IIFE), der `jQuery` als Argument übergibt, wodurch es lokal als `$` aliased werden kann, ohne mit anderen Bibliotheken zu kollidieren, die ebenfalls `$` verwenden könnten.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält eine primäre CSS-Datei zur Gestaltung des Sliders.

- `fullscreenslider/css/skitter.styles.css`
  - **Geltungsbereich:** Front-Office-Kundenstyling.
  - **Verantwortlichkeit:** Enthält alle notwendigen CSS-Regeln zur Gestaltung des Fullscreen Sliders, einschließlich seines Containers, der Navigationspfeile, der Paginierungspunkte und der visuellen Effekte des gewählten Animationstyps. Es definiert das Standardaussehen und -gefühl des Sliders.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**
    - `.box_skitter` (Haupt-Slider-Container)
    - `.box_skitter ul` (Liste der Folien)
    - `.box_skitter ul li` (einzelne Folie)
    - `.box_skitter .info_slide` (Folienbeschriftungen/Infos, falls verwendet)
    - `.box_skitter .prev_button`, `.box_skitter .next_button` (Navigationspfeile)
    - `.box_skitter .info_slide_dots`, `.box_skitter .info_slide_thumb` (Paginierungselemente)
    - Spezifische Klassen für Animationstypen (z.B. `.cube`, `.fade` usw.)

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um seinen Front-Office-Inhalt zu rendern.

- **Hook-Templates (`views/templates/hook/`)**:

  - `fullscreenslider/header.tpl`
    - **Hook:** `displayHeader` (oder ähnlich, abhängig von der `hook`-Methodenimplementierung des Moduls).
    - **Zweck:** Dieses Template ist wahrscheinlich dafür verantwortlich, die notwendigen CSS- und JavaScript-Dateien in den `<head>`-Bereich des HTML einzufügen und möglicherweise die anfängliche HTML-Struktur für den Slider-Container, die dann vom JavaScript gefüllt und animiert wird. Es könnte auch die Logik enthalten, um das Cookie zu überprüfen, das bestimmt, ob der Slider angezeigt werden soll.
  - `fullscreenslider/top.tpl`
    - **Hook:** Dieses Template wird wahrscheinlich innerhalb des `displayTop`-Hooks gerendert oder direkt von `header.tpl` eingebunden, um die Haupt-HTML-Struktur des Fullscreen Sliders selbst auszugeben.
    - **Zweck:** Es enthält die `div`-Elemente und die `ul/li`-Struktur, die `jquery.skitter.js` erwartet, um den Slider zu initialisieren. Es iteriert durch die konfigurierten Banner und gibt jedes Bild mit seinem zugehörigen Link aus. Es enthält auch den HTML-Code für die Schaltfläche zum Schließen.
- **Admin-Templates (`views/templates/admin/`)**: Dieses Modul scheint keine dedizierten Admin-Templates zu verwenden, da die Konfiguration direkt innerhalb von `getContent()` gehandhabt wird.
- **Front-Office-Templates (`views/templates/front/`)**: Dieses Modul scheint keine dedizierten eigenständigen Front-Office-Seitentemplates zu verwenden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen (einschließlich serialisierter Daten für Banner wie Bildpfade, Links und Reihenfolge) werden in der Tabelle `ps_configuration` gespeichert. Schlüssel folgen typischerweise dem Muster `FULLSCREENSLIDER_SETTING_NAME`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Fügt die CSS- und JavaScript-Dateien des Moduls und möglicherweise die anfängliche HTML-Struktur für den Slider zusammen mit der Cookie-Prüflogik ein. |
| `displayTop` (oder ähnlich) | Wird im oberen Bereich der Front-Office-Seite ausgeführt, oft direkt unter dem Header. | Rendert die Haupt-HTML-Struktur des Fullscreen Sliders, einschließlich der Bannerbilder und Navigationselemente. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Fullscreen Banner Slider verweisen wir auf Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
