---
title: "Facebook Fan Slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Fan Slider von MyPresta.eu."
sidebar:
  label: "Facebook Fan Slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Fan Slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-fan-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-fan-slider/)
>
> ---


# Facebook Fan Slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst erforderlich und in allen modernen Hosting-Umgebungen generell verfügbar. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Einrichtung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Einstellungen des Moduls zuzugreifen, gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Facebook Fan Slider“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

Hier ist eine detaillierte Aufschlüsselung jeder Einstellung:

- **Facebook Page URL (fs\_url)**

  - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie teilt dem Modul mit, welche spezifische Facebook-Seite im gleitenden Feld angezeigt werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf Ihre Facebook-Seiten-URL eingestellt:* Das Modul ruft die Like Box/Seiten-Plugin für genau diese Seite ab und zeigt sie an.
    - *Wenn leer gelassen oder falsch eingestellt:* Das Modul zeigt entweder den Facebook-Inhalt nicht an oder es wird ein Fehler angezeigt, da es nicht weiß, mit welcher Seite es sich verbinden soll.
  - **Empfohlener Wert:** Geben Sie die vollständige URL Ihrer Facebook-Seite ein (z.B. `https://www.facebook.com/MyPresta.eu`).
  - **Händlerszenario / Beispiel:** Wenn Ihre Unternehmensseite `https://www.facebook.com/MyAwesomeShop` ist, würden Sie diese URL hier eingeben.
- **Width (fs\_width)**

  - **Was diese Einstellung bewirkt:** Steuert die Breite der Facebook Like Box/Seiten-Plugin *innerhalb* des Schiebepaneels, in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. 280):* Der Facebook-Inhalt wird genau diese Breite haben.
    - *Wenn auf einen kleineren Wert eingestellt:* Der Inhalt könnte gedrängt erscheinen oder einige Elemente könnten abgeschnitten werden.
    - *Wenn auf einen größeren Wert eingestellt:* Der Inhalt wird sich ausdehnen, aber stellen Sie sicher, dass er die Bildschirmbreite nicht überschreitet oder unverhältnismäßig aussieht.
  - **Empfohlener Wert:** Beginnen Sie mit `280` oder `300` Pixeln. Passen Sie ihn an, je nachdem, wie viel Inhalt Sie anzeigen (z.B. wenn Sie Beiträge anzeigen, benötigen Sie möglicherweise mehr Breite).
  - **Händlerszenario / Beispiel:** Sie möchten, dass das Schiebefeld breit genug ist, um das Titelbild Ihrer Seite und die Schaltfläche „Gefällt mir“ deutlich anzuzeigen, ohne zu klobig zu sein.
- **Height (fs\_height)**

  - **Was diese Einstellung bewirkt:** Steuert die Höhe der Facebook Like Box/Seiten-Plugin *innerhalb* des Schiebepaneels, in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. 400):* Der Facebook-Inhalt wird genau diese Höhe haben.
    - *Wenn auf einen kleineren Wert eingestellt:* Inhalt könnte abgeschnitten werden, was ein Scrollen innerhalb des Feldes erfordert.
    - *Wenn auf einen größeren Wert eingestellt:* Das Feld wird höher, was möglicherweise mehr Bildschirmplatz beansprucht.
  - **Empfohlener Wert:** Beginnen Sie mit `400` oder `500` Pixeln. Wenn Sie „Beiträge anzeigen“ aktivieren, benötigen Sie wahrscheinlich mehr Höhe (z.B. `600-700px`), um einige Beiträge ohne übermäßiges Scrollen anzuzeigen.
  - **Händlerszenario / Beispiel:** Sie möchten einige aktuelle Beiträge von Ihrer Facebook-Seite anzeigen, daher erhöhen Sie die Höhe auf `600px`, um sie sichtbar zu machen.
- **Hide Cover Photo (fs\_hide\_cover)**

  - **Was diese Einstellung bewirkt:** Legt fest, ob das große Titelbild Ihrer Facebook-Seite oben in der Like Box/Seiten-Plugin angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (angekreuzt):* Das Titelbild wird nicht angezeigt, wodurch die Like Box kompakter wird.
    - *Wenn deaktiviert (nicht angekreuzt):* Das Titelbild wird angezeigt, wodurch die Like Box visuell reicher, aber auch höher wird.
  - **Empfohlener Wert:** *Deaktiviert* (nicht angekreuzt), wenn Sie eine visuell ansprechendere Box wünschen. *Aktiviert* (angekreuzt), wenn Sie vertikalen Platz sparen müssen.
  - **Händlerszenario / Beispiel:** Sie haben ein schönes Titelbild auf Facebook und möchten es präsentieren, daher lassen Sie diese Option deaktiviert. Wenn Sie wenig Platz haben, könnten Sie sie aktivieren.
- **Show Friends’ Faces (fs\_show\_facepile)**

  - **Was diese Einstellung bewirkt:** Steuert, ob die Profilbilder von Freunden, die Ihre Seite bereits geliked haben, unter der Schaltfläche „Gefällt mir“ angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (angekreuzt):* Eine Reihe von Profilbildern von gemeinsamen Freunden, die Ihre Seite mögen, wird angezeigt, was sozialen Beweis liefert.
    - *Wenn deaktiviert (nicht angekreuzt):* Diese Profilbilder werden nicht angezeigt.
  - **Empfohlener Wert:** *Aktiviert* (angekreuzt). Sozialer Beweis kann andere dazu ermutigen, Ihre Seite zu liken.
  - **Händlerszenario / Beispiel:** Sie möchten sozialen Beweis nutzen, um neue Likes zu fördern, daher aktivieren Sie diese Option, um Freunde anzuzeigen, die Ihre Seite bereits mögen.
- **Show Posts (fs\_show\_posts)**

  - **Was diese Einstellung bewirkt:** Legt fest, ob aktuelle Beiträge aus der Chronik Ihrer Facebook-Seite innerhalb der Like Box/Seiten-Plugin angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (angekreuzt):* Ihre neuesten Facebook-Beiträge werden angezeigt, wodurch die Box dynamischer und ansprechender wird. Sie müssen wahrscheinlich die Einstellung `Height` erhöhen.
    - *Wenn deaktiviert (nicht angekreuzt):* Es wird nur die grundlegende „Seite liken“-Funktionalität und Freundesgesichter (falls aktiviert) angezeigt.
  - **Empfohlener Wert:** *Aktiviert* (angekreuzt), wenn Sie regelmäßig ansprechende Inhalte posten und diese präsentieren möchten. Denken Sie daran, die `Height` anzupassen.
  - **Händlerszenario / Beispiel:** Sie posten häufig über neue Produkte und Aktionen auf Facebook. Wenn Sie dies aktivieren, können Kunden Ihre neuesten Updates direkt in Ihrem Shop sehen.
- **Hide Call To Action (fs\_hide\_cta)**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der „Call To Action“-Schaltfläche (z.B. „Nachricht senden“, „Jetzt einkaufen“), die Sie möglicherweise auf Ihrer Facebook-Seite konfiguriert haben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (angekreuzt):* Die CTA-Schaltfläche wird in der Like Box nicht angezeigt.
    - *Wenn deaktiviert (nicht angekreuzt):* Die CTA-Schaltfläche (falls auf Ihrer Facebook-Seite konfiguriert) wird sichtbar sein.
  - **Empfohlener Wert:** *Deaktiviert* (nicht angekreuzt), wenn Ihr CTA für Ihre Shop-Besucher relevant ist. *Aktiviert* (angekreuzt), wenn Sie sich nur auf das Erhalten von Likes konzentrieren möchten.
  - **Händlerszenario / Beispiel:** Ihre Facebook-Seite hat eine „Jetzt einkaufen“-Schaltfläche. Sie möchten, dass Kunden diese nutzen, daher lassen Sie diese Option deaktiviert.
- **Small Header (fs\_small\_header)**

  - **Was diese Einstellung bewirkt:** Verwendet eine kleinere Version des Headers für die Facebook Like Box/Seiten-Plugin.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (angekreuzt):* Der Header-Bereich der Like Box wird kompakter, wodurch vertikaler Platz gespart wird.
    - *Wenn deaktiviert (nicht angekreuzt):* Der Standard-Header, der größer ist, wird verwendet.
  - **Empfohlener Wert:** *Aktiviert* (angekreuzt), wenn Sie ein schlankeres Aussehen wünschen oder Platz sparen müssen.
  - **Händlerszenario / Beispiel:** Sie möchten, dass das Schiebefeld so kompakt wie möglich ist, ohne wesentliche Informationen zu verbergen, daher aktivieren Sie den kleinen Header.
- **Slide on (fanslider\_slideon)**

  - **Was diese Einstellung bewirkt:** Bestimmt die Interaktionsmethode, die das Facebook-Feld ausfahren lässt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Klick“ eingestellt:* Das Feld fährt nur aus, wenn der Kunde explizit auf den Tab klickt.
    - *Wenn auf „Hover“ eingestellt:* Das Feld fährt aus, wenn der Kunde den Mauszeiger über den Tab bewegt.
  - **Empfohlener Wert:** „Klick“ ist im Allgemeinen weniger aufdringlich und verhindert versehentliches Ausfahren. „Hover“ kann direkter sein, könnte aber einige Benutzer stören.
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass der Slider nur erscheint, wenn ein Kunde aktiv entscheidet, ihn zu sehen, daher stellen Sie ihn auf „Klick“ ein.
- **Position (fs\_pos)**

  - **Was diese Einstellung bewirkt:** Steuert, wo der Schiebe-Tab auf Ihrer Website erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Links“ eingestellt:* Der Tab erscheint auf der linken Seite des Browserfensters.
    - *Wenn auf „Rechts“ eingestellt:* Der Tab erscheint auf der rechten Seite des Browserfensters.
  - **Empfohlener Wert:** „Links“ oder „Rechts“, je nach Layout Ihres Themes und wo es am wenigsten Interferenzen mit anderen Elementen verursacht.
  - **Händlerszenario / Beispiel:** Ihr Theme hat ein Live-Chat-Widget auf der rechten Seite, daher stellen Sie den Facebook Fan Slider auf „Links“ ein, um Konflikte zu vermeiden.
- **Background Color (fs\_bg\_color)**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe des Schiebepaneels selbst fest (nicht den Facebook-Inhalt, sondern den Container, in dem es gleitet).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z.B. #FFFFFF für Weiß, #0000FF für Blau):* Der Hintergrund des Schiebefeldes ändert sich zu dieser Farbe.
  - **Empfohlener Wert:** Eine Farbe, die zum Branding Ihres Shops passt, oder eine neutrale Farbe wie Weiß (`#FFFFFF`) oder Hellgrau (`#F0F0F0`).
  - **Händlerszenario / Beispiel:** Ihre Marke verwendet einen bestimmten Blauton. Sie geben den Hex-Code für dieses Blau ein, um sicherzustellen, dass der Slider zu Ihrer Markenidentität passt.
- **Border Color (fs\_br\_color)**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Rahmens um das Schiebepaneel fest.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z.B. #CCCCCC für Hellgrau):* Der Rahmen des Schiebefeldes ändert sich zu dieser Farbe.
  - **Empfohlener Wert:** Eine dezente Farbe, die Ihre Hintergrundfarbe ergänzt, oder eine Farbe, die zu Ihrer Marke passt.
  - **Händlerszenario / Beispiel:** Sie möchten einen dezenten Rahmen um den Slider, daher wählen Sie eine hellgraue Farbe (`#DDDDDD`).
- **Language (fs\_langarray)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Sprache für die Facebook Like Box/Seiten-Plugin. Dies stellt sicher, dass die Schaltfläche „Seite liken“ und andere von Facebook generierte Texte in der richtigen Sprache für Ihr Publikum sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Sprache eingestellt (z.B. „en\_US“ für Englisch, „fr\_FR“ für Französisch):* Das Facebook-Plugin wird in dieser Sprache gerendert.
  - **Empfohlener Wert:** Wählen Sie die primäre Sprache Ihres Shops oder Ihres Zielpublikums.
  - **Händlerszenario / Beispiel:** Ihr Shop bedient hauptsächlich Kunden in Frankreich, daher wählen Sie „fr\_FR“, um den Facebook-Inhalt auf Französisch anzuzeigen.
- **Adapt Container Width (fs\_adapt\_container\_width)**

  - **Was diese Einstellung bewirkt:** Weist das Facebook Seiten-Plugin an, seine Breite an die Breite seines übergeordneten Containers (des Schiebefeldes) anzupassen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (angekreuzt):* Der Facebook-Inhalt versucht, die von Ihnen für das Schiebefeld angegebene `Width` auszufüllen, wodurch er innerhalb dieses Containers responsiv wird.
    - *Wenn deaktiviert (nicht angekreuzt):* Der Facebook-Inhalt verwendet möglicherweise seine Standardbreite, was zu Überlauf oder leerem Raum führen kann, wenn er nicht mit Ihrer `Width`-Einstellung übereinstimmt.
  - **Empfohlener Wert:** *Aktiviert* (angekreuzt) für bessere Responsivität und um sicherzustellen, dass der Facebook-Inhalt gut in Ihre angegebene `Width` passt.
  - **Händlerszenario / Beispiel:** Sie möchten, dass der Facebook-Inhalt sich automatisch an die Breite Ihres Sliders anpasst, daher aktivieren Sie dies für ein saubereres Aussehen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook Page URL (fs\_url) | Ihre Facebook-Seiten-URL | Gibt an, welche Facebook-Seite angezeigt werden soll. **KRITISCH!** |
| Modulkonfiguration | Width (fs\_width) | 280-300px | Legt die Breite des Facebook-Inhalts im Slider fest. |
| Modulkonfiguration | Height (fs\_height) | 400-500px (mehr, wenn Beiträge angezeigt werden) | Legt die Höhe des Facebook-Inhalts im Slider fest. |
| Modulkonfiguration | Hide Cover Photo (fs\_hide\_cover) | Deaktiviert (nicht angekreuzt) | Zeigt/versteckt das große Titelbild Ihrer Facebook-Seite. |
| Modulkonfiguration | Show Friends’ Faces (fs\_show\_facepile) | Aktiviert (angekreuzt) | Zeigt Profilbilder von Freunden an, die Ihre Seite mögen (sozialer Beweis). |
| Modulkonfiguration | Show Posts (fs\_show\_posts) | Aktiviert (angekreuzt) | Zeigt aktuelle Beiträge aus Ihrer Facebook-Chronik an. Erfordert mehr Höhe. |
| Modulkonfiguration | Hide Call To Action (fs\_hide\_cta) | Deaktiviert (nicht angekreuzt) | Zeigt/versteckt die auf Ihrer Facebook-Seite konfigurierte CTA-Schaltfläche. |
| Modulkonfiguration | Small Header (fs\_small\_header) | Aktiviert (angekreuzt) | Verwendet einen kompakteren Header für das Facebook-Plugin. |
| Modulkonfiguration | Slide on (fanslider\_slideon) | Klick | Legt fest, ob das Feld bei „Klick“ oder „Hover“ ausfährt. „Klick“ ist weniger aufdringlich. |
| Modulkonfiguration | Position (fs\_pos) | Links / Rechts | Legt die Seite des Bildschirms fest, auf der der Tab erscheint. |
| Modulkonfiguration | Background Color (fs\_bg\_color) | Passt zum Theme / Weiß (#FFFFFF) | Legt die Hintergrundfarbe des Schiebepaneels fest. |
| Modulkonfiguration | Border Color (fs\_br\_color) | Dezentes Grau (#DDDDDD) | Legt die Rahmenfarbe des Schiebepaneels fest. |
| Modulkonfiguration | Language (fs\_langarray) | Primäre Sprache Ihres Shops | Legt die Sprache für den Facebook-Plugin-Text fest. |
| Modulkonfiguration | Adapt Container Width (fs\_adapt\_container\_width) | Aktiviert (angekreuzt) | Macht den Facebook-Inhalt responsiv zur Breite des Sliders. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Facebook-Slider erscheint nicht in meinem Shop. Was sollte ich zuerst überprüfen?**
A1:

- **Modul aktiviert:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Facebook Fan Slider“ installiert und aktiviert ist.
- **Facebook-Seiten-URL:** Überprüfen Sie die `Facebook Page URL (fs_url)` in der Modulkonfiguration. Stellen Sie sicher, dass es die *genaue* URL Ihrer Facebook-Seite ist (z.B. `https://www.facebook.com/MyPresta.eu`) und nicht nur Ihr Profil oder eine Gruppe.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“). Leeren Sie auch den Cache Ihres Browsers.
- **Theme-Konflikte:** Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob der Slider erscheint. Wenn ja, könnte Ihr benutzerdefiniertes Theme CSS- oder JavaScript-Konflikte aufweisen.

**F2: Der Facebook-Inhalt im Slider sieht abgeschnitten oder zu klein/groß aus.**
A2:

- **Breite & Höhe:** Passen Sie die Einstellungen `Width (fs_width)` und `Height (fs_height)` in der Modulkonfiguration an. Wenn Sie Beiträge anzeigen, benötigen Sie definitiv mehr Höhe.
- **Containerbreite anpassen:** Stellen Sie sicher, dass `Adapt Container Width (fs_adapt_container_width)` aktiviert (angekreuzt) ist. Dies hilft dem Facebook-Inhalt, sich responsiv innerhalb des Sliders anzupassen.
- **Kleiner Header:** Wenn Sie vertikalen Platz sparen möchten, versuchen Sie, `Small Header (fs_small_header)` zu aktivieren.

**F3: Die Sprache der Facebook Like Box ist falsch.**
A3:

- **Spracheinstellung:** Gehen Sie zur Modulkonfiguration und überprüfen Sie die Einstellung `Language (fs_langarray)`. Wählen Sie den richtigen Sprachcode für Ihr Zielpublikum (z.B. `en_US` für US-Englisch, `fr_FR` für Französisch).

**F4: Ich habe Einstellungen geändert, aber im Front Office passiert nichts.**
A4:

- **Änderungen speichern:** Klicken Sie immer auf die Schaltfläche „Speichern“, nachdem Sie Änderungen in der Modulkonfiguration vorgenommen haben.
- **Cache leeren:** PrestaShop ist stark auf Caching angewiesen. Leeren Sie nach dem Speichern immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**) und den Cache Ihres Browsers. Dies ist der häufigste Grund, warum Änderungen nicht sofort erscheinen.

**F5: Der Slider überlappt mit einem anderen Element auf meiner Website.**
A5:

- **Position:** Passen Sie die Einstellung `Position (fs_pos)` (Links oder Rechts) an, um zu sehen, ob das Verschieben des Sliders auf die andere Seite den Konflikt löst.
- **CSS-Anpassungen (Entwickler erforderlich):** Wenn das Problem weiterhin besteht, sind möglicherweise benutzerdefinierte CSS-Anpassungen am Slider oder am überlappenden Element erforderlich. Dies würde typischerweise einen Webmaster oder Entwickler erfordern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul Facebook Fan Slider (`fanslider`) ist ein Standard-PrestaShop-Modul, das die `Module`-Klasse implementiert. Es nutzt hauptsächlich das Hook-System von PrestaShop, um sein HTML, CSS und JavaScript in das Front-Office zu injizieren. Die Kernfunktionalität besteht darin, das offizielle Facebook Seiten-Plugin innerhalb eines benutzerdefinierten gleitenden UI-Elements anzuzeigen. Die Konfiguration wird über die Methode `getContent()` verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Das Modul verwendet keine benutzerdefinierten Datenbanktabellen oder `ObjectModel`-Klassen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das gesamte Front-Office-Rendering und die Logik werden direkt in der Hauptmoduldatei (`fanslider.php`) über Hooks und injiziertes JavaScript gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird von der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Die Logik des Moduls ist in `fanslider/fanslider.php` eigenständig enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, hauptsächlich für die gleitende Animation und die Farbauswahlfunktion.

- `fanslider/jscolor/jscolor.js`

  - **Geltungsbereich:** Back-Office (wird in `getContent()` für Farbauswahl-Eingaben verwendet).
  - **Verantwortlichkeit:** Bietet ein JavaScript-Farbauswahl-Dienstprogramm, das Administratoren ermöglicht, Farben für den Hintergrund und den Rahmen des Sliders visuell auszuwählen. Es wird an Eingabefelder mit der Klasse `jscolor` angehängt.
- `fanslider/js/fanslider-click.js`

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript verarbeitet die „Klick“-Interaktion für den Slider. Es lauscht auf Klickereignisse auf dem Slider-Tab und schaltet die Sichtbarkeit und Position des Haupt-Slider-Containers (`#fanslider`) um. Es verwaltet auch die Klasse `fanslider_open`, um den offenen/geschlossenen Zustand zu steuern.
- `fanslider/js/fanslider.js`

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dies ist wahrscheinlich das Hauptskript für die Animation und die anfängliche Einrichtung des Sliders. Es verarbeitet die „Hover“-Interaktion, falls konfiguriert, und berechnet möglicherweise anfängliche Positionen oder wendet CSS-Transformationen für den Gleiteffekt an. Es interagiert mit den Elementen `#fanslider` und `#fanslider_tab`.
- `fanslider/script.js`

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript enthält wahrscheinlich die Kernlogik für die Initialisierung des Facebook Seiten-Plugins (FB.init und FB.XFBML.parse) und möglicherweise andere allgemeine Setup- oder Ereignisbindungen im Zusammenhang mit dem Verhalten des Sliders. Es stellt sicher, dass das Facebook SDK geladen und das Plugin korrekt gerendert wird.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul listet keine CSS-Dateien explizit in `views/css/` auf. Das Styling für den Slider ist wahrscheinlich direkt in der `hookDisplayHeader`-Methode der Datei `fanslider.php` oder innerhalb des `rightcolumn.tpl`-Templates eingebettet oder wird dynamisch basierend auf der Konfiguration generiert. Entwickler sollten den generierten HTML-Code und die Hauptmoduldatei auf Inline-Styles oder `<style>`-Blöcke überprüfen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `fanslider/views/templates/hook/rightcolumn.tpl`
    - **Hook:** Dieses Template ist primär dafür konzipiert, in einem Hook gerendert zu werden, der die Injektion von Inhalten in die Seite ermöglicht, wie z.B. `displayFooter` oder `displayHeader` (obwohl sein Name `displayRightColumn` suggeriert, platziert die Modulimplementierung es als festes Element).
    - **Visueller Block:** Dieses Template gibt die Haupt-HTML-Struktur für den Facebook Fan Slider aus. Es enthält typischerweise:
      - Den Hauptcontainer für den Slider (`#fanslider`).
      - Den anklickbaren Tab (`#fanslider_tab`).
      - Den Container für das Facebook Seiten-Plugin (`<div class="fb-page">`).
      - Es empfängt Konfigurationsvariablen vom Modul, um Attribute für das Facebook Seiten-Plugin dynamisch festzulegen (z.B. `data-href`, `data-width`, `data-height`, `data-hide-cover`, `data-show-facepile`, `data-show-posts`, `data-hide-cta`, `data-small-header`, `data-adapt-container-width`).
      - Es enthält auch das notwendige `div` für das Facebook SDK, um das Plugin zu rendern.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die mit `FS_` oder `FANSIDER_` beginnen (z.B. `FS_WIDTH`, `FANSIDER_SLIDEON`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Injiziert notwendige CSS- und JavaScript-Dateien und möglicherweise das Facebook SDK-Initialisierungsskript. Kann auch Inline-Styles basierend auf der Konfiguration ausgeben. |
| `displayFooter` | Wird am Ende jeder Seite, vor dem schließenden `</body>`-Tag, ausgeführt. | Rendert die Haupt-HTML-Struktur des Facebook Fan Sliders (aus `rightcolumn.tpl`) und stellt sicher, dass das Facebook SDK geladen und das Seiten-Plugin nach dem Laden des DOM initialisiert wird. Hier wird die visuelle Komponente zur Seite hinzugefügt. |

## 5. Offizieller Support & Updates

Für die neuesten Versionen, Updates und professionellen Support für das Modul Facebook Fan Slider besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
