---
title: "Prestashop Popup Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Prestashop Popup Pro von MyPresta.eu."
sidebar:
  label: "Prestashop Popup Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Prestashop Popup Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/prestashop-popup-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/prestashop-popup-pro/)
>
> ---


# Prestashop Popup Pro

## 1. Anforderungen & Kompatibilität

Um sicherzustellen, dass das Modul Prestashop Popup Pro reibungslos in Ihrem Shop läuft, überprüfen Sie bitte die folgenden Anforderungen:

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den allgemeinen PrestaShop-Betrieb erforderlich und sollten in jeder modernen Hosting-Umgebung verfügbar sein. Für dieses Modul sind keine speziellen oder ungewöhnlichen Erweiterungen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Die Hauptkonfigurationsseite für Prestashop Popup Pro ist der Ort, an dem Sie alles über Ihr Popup definieren: seinen Inhalt, sein Aussehen und sein Verhalten.

**Registerkarte „Allgemeine Einstellungen“**

- **Popup Pro aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, Popups gemäß Ihren anderen Einstellungen anzuzeigen.
    - *Wenn deaktiviert:* Es werden keine Popups in Ihrem Shop angezeigt, unabhängig von anderen Konfigurationen.
  - **Empfohlener Wert:** JA (wenn Sie Popups verwenden möchten).
  - **Händlerszenario / Beispiel:** Sie führen eine Kampagne durch und möchten Ihr Popup aktivieren. Sie aktivieren es. Nach der Kampagne deaktivieren Sie es, ohne Ihre Einstellungen zu verlieren.
- **Popup-Inhalt (HTML-Editor):**

  - **Was diese Einstellung bewirkt:** Dies ist der Kern Ihres Popups. Es ist ein leistungsstarker HTML-Editor, in dem Sie gestalten, was im Popup-Fenster erscheint. Sie können Text, Bilder, Links, Videos und sogar Formulare (z.B. Newsletter-Anmeldung) einbetten.
  - **Auswirkung der Änderung dieser Einstellung:** Alle Änderungen hier aktualisieren direkt den visuellen Inhalt, der Ihren Kunden im Popup angezeigt wird.
  - **Empfohlener Wert:** Ihre gewünschte Werbebotschaft, Ihr Bild oder Ihre Handlungsaufforderung.
  - **Händlerszenario / Beispiel:** Sie möchten einen Rabatt von 15 % ankündigen. Sie würden „Erhalten Sie 15 % Rabatt auf Ihre erste Bestellung! Verwenden Sie den Code: SPARE15“ eingeben und vielleicht ein Bild beliebter Produkte hinzufügen.
- **Popup-Breite (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Breite Ihres Popup-Fensters in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Erhöhung des Wertes:* Macht das Popup breiter.
    - *Verringerung des Wertes:* Macht das Popup schmaler.
  - **Empfohlener Wert:** Beginnen Sie mit `600px` bis `800px` für den Desktop und passen Sie ihn dann basierend auf Ihrem Inhalt und Design an.
  - **Händlerszenario / Beispiel:** Sie haben ein großes Bannerbild in Ihrem Popup. Sie könnten die Breite auf `800px` einstellen, um sicherzustellen, dass das Bild gut angezeigt wird. Für eine einfache Textnachricht könnten `400px` ausreichen.
- **Popup-Höhe (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Höhe Ihres Popup-Fensters in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Erhöhung des Wertes:* Macht das Popup höher.
    - *Verringerung des Wertes:* Macht das Popup kürzer.
  - **Empfohlener Wert:** `auto` (leer lassen) oder ein spezifischer Pixelwert, wenn Ihr Inhalt eine feste Höhe hat.
  - **Händlerszenario / Beispiel:** Wenn Ihr Popup-Inhalt dynamisch oder kurz ist, ermöglicht das Leerlassen (`auto`), dass das Popup seine Höhe an den Inhalt anpasst. Wenn Sie ein Video haben, das ein bestimmtes Seitenverhältnis erfordert, könnten Sie eine feste Höhe einstellen.
- **Popup anzeigen bei:**

  - **Was diese Einstellung bewirkt:** Bestimmt, *wann* das Popup erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Seitenaufruf:* Popup erscheint nach dem Laden der Seite.
    - *Exit Intent:* Popup erscheint, wenn der Mauszeiger des Benutzers sich außerhalb des Browserfensters bewegt (was darauf hindeutet, dass er möglicherweise die Seite verlassen möchte).
    - *Scrollen:* Popup erscheint, nachdem der Benutzer einen bestimmten Prozentsatz der Seite nach unten gescrollt hat.
    - *Zeitverzögerung:* Popup erscheint nach einer bestimmten Anzahl von Sekunden.
  - **Empfohlener Wert:** Hängt von Ihrem Ziel ab. „Exit Intent“ ist oft effektiv, um abspringende Besucher zu erfassen. „Seitenaufruf“ mit einer kurzen Verzögerung (z.B. 3-5 Sekunden) ist gut für allgemeine Ankündigungen.
  - **Händlerszenario / Beispiel:** Um den Warenkorbabbruch zu reduzieren, würden Sie „Exit Intent“ wählen und einen Rabattcode anbieten. Um eine neue Produktlinie anzukündigen, könnten Sie „Seitenaufruf“ mit einer 3-sekündigen Verzögerung verwenden.
- **Verzögerung vor dem Erscheinen des Popups (Sekunden):**

  - **Was diese Einstellung bewirkt:** Wenn „Popup anzeigen bei“ auf „Seitenaufruf“ oder „Zeitverzögerung“ eingestellt ist, gibt dies an, wie viele Sekunden gewartet werden soll, bevor das Popup angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:** Ein höherer Wert bedeutet, dass das Popup später erscheint, was dem Kunden mehr Zeit zum Stöbern gibt. Ein niedrigerer Wert bedeutet, dass es früher erscheint.
  - **Empfohlener Wert:** `3` bis `5` Sekunden. Zu schnell kann aufdringlich sein, zu langsam könnte den Kunden verpassen.
  - **Händlerszenario / Beispiel:** Sie möchten Kunden einen Moment Zeit geben, Ihre Startseite zu sehen, bevor Sie eine Newsletter-Anmeldung anzeigen. Sie stellen dies auf `5` Sekunden ein.
- **Popup-Häufigkeit (Tage):**

  - **Was diese Einstellung bewirkt:** Steuert, wie oft ein *wiederkehrender* Kunde das Popup sieht. Sobald ein Kunde das Popup schließt, bestimmt diese Einstellung, wie viele Tage vergehen, bevor er es erneut sieht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *0:* Popup erscheint bei jedem Besuch (kann störend sein).
    - *Höherer Wert:* Popup erscheint seltener für wiederkehrende Besucher.
  - **Empfohlener Wert:** `7` bis `30` Tage. Vermeiden Sie es, Ihre treuen Kunden zu verärgern.
  - **Händlerszenario / Beispiel:** Sie führen einen einmonatigen Sale durch. Sie stellen dies auf `7` Tage ein, damit Kunden wöchentlich erinnert werden, aber nicht bei jedem einzelnen Besuch.
- **Popup auf mobilen Geräten anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des Popups auf Smartphones und Tablets um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Popup erscheint auf mobilen Geräten und passt sich responsiv an.
    - *Deaktiviert:* Popup erscheint nur auf Desktop-Computern.
  - **Empfohlener Wert:** JA, aber stellen Sie sicher, dass Ihr Popup-Inhalt mobilfreundlich ist.
  - **Händlerszenario / Beispiel:** Sie haben ein einfaches, textbasiertes Popup, das auf Mobilgeräten gut aussieht. Sie aktivieren dies, um alle Ihre Kunden zu erreichen. Wenn Ihr Popup komplexe Bilder oder Formulare enthält, die auf Mobilgeräten nicht funktionieren, könnten Sie es deaktivieren.
- **Popup-Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe des Popup-Fensters selbst fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die visuelle Farbe hinter Ihrem Inhalt.
  - **Empfohlener Wert:** Eine Farbe, die Ihre Marke ergänzt und Ihren Inhalt hervorhebt. Oft Weiß (`#FFFFFF`) oder eine helle neutrale Farbe.
  - **Händlerszenario / Beispiel:** Ihre Marke verwendet viel Blau. Sie könnten einen hellblauen Hintergrund für das Popup wählen, um dazu zu passen.
- **Popup-Rahmenfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Rahmens um das Popup-Fenster fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die visuelle Farbe des Popup-Randes.
  - **Empfohlener Wert:** Oft eine dezente Farbe oder transparent, wenn Sie keinen Rahmen bevorzugen.
  - **Händlerszenario / Beispiel:** Sie möchten ein sauberes Aussehen, daher stellen Sie dies auf ein sehr helles Grau oder transparent ein.
- **Popup-Rahmenbreite (px):**

  - **Was diese Einstellung bewirkt:** Legt die Dicke des Rahmens um das Popup-Fenster fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ein höherer Wert macht den Rahmen dicker.
  - **Empfohlener Wert:** `0` bis `2` Pixel für einen dezenten Effekt.
  - **Händlerszenario / Beispiel:** Sie möchten ein sehr definiertes Popup, daher stellen Sie einen `2px`-Rahmen ein. Für ein minimalistisches Design stellen Sie es auf `0`.
- **Popup-Rahmenradius (px):**

  - **Was diese Einstellung bewirkt:** Steuert die Rundung der Ecken des Popups.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *0:* Scharfe, eckige Ecken.
    - *Höherer Wert:* Stärker abgerundete Ecken.
  - **Empfohlener Wert:** `0` bis `10` Pixel für einen modernen Look.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Ihr Popup weiche, moderne Kanten hat, daher stellen Sie dies auf `8px` ein.
- **Overlay-Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe der halbtransparenten Ebene fest, die *hinter* dem Popup erscheint und den Rest Ihres Shop-Inhalts abdunkelt.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Farbe des Overlays. Oft eine dunkle Farbe mit Transparenz.
  - **Empfohlener Wert:** Schwarz (`#000000`) mit etwas Transparenz (z.B. `rgba(0,0,0,0.7)`, wenn Sie RGBA eingeben können).
  - **Händlerszenario / Beispiel:** Sie möchten, dass das Popup der absolute Fokus ist, daher wählen Sie ein dunkles, fast undurchsichtiges Overlay.
- **Overlay-Deckkraft (0-100):**

  - **Was diese Einstellung bewirkt:** Steuert, wie transparent oder undurchsichtig der Overlay-Hintergrund ist. `0` ist vollständig transparent (unsichtbar), `100` ist vollständig undurchsichtig (durchgehende Farbe).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Höherer Wert:* Undurchsichtiger, dunklerer Hintergrund, mehr Fokus auf das Popup.
    - *Niedrigerer Wert:* Transparenter, hellerer Hintergrund, mehr von Ihrem Shop-Inhalt sichtbar.
  - **Empfohlener Wert:** `50` bis `80`.
  - **Händlerszenario / Beispiel:** Sie möchten den Hintergrund leicht abdunkeln, aber den Kunden trotzdem erlauben, Ihren Shop hinter dem Popup zu sehen. Sie stellen dies auf `60` ein.
- **Schließen-Button anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des standardmäßigen „X“-Schließen-Buttons auf dem Popup um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Ein Schließen-Button erscheint, der es Kunden ermöglicht, das Popup einfach zu schließen.
    - *Deaktiviert:* Kein „X“-Button. Kunden müssen außerhalb des Popups klicken oder ESC drücken (falls aktiviert), um es zu schließen.
  - **Empfohlener Wert:** JA, für eine gute Benutzererfahrung.
  - **Händlerszenario / Beispiel:** Sie möchten es Kunden leicht machen, das Popup zu schließen, daher aktivieren Sie den Schließen-Button.
- **Schließen durch Klicken außerhalb erlauben:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob ein Klick irgendwo auf das Overlay (außerhalb des Popup-Inhalts) das Popup schließt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Klicken auf das Overlay schließt das Popup.
    - *Deaktiviert:* Nur der Schließen-Button oder die ESC-Taste schließen das Popup.
  - **Empfohlener Wert:** JA, für eine gute Benutzererfahrung.
  - **Händlerszenario / Beispiel:** Sie möchten mehrere Möglichkeiten bieten, damit Kunden das Popup schließen können, daher aktivieren Sie dies.
- **Schließen durch ESC-Taste erlauben:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob das Drücken der ESC-Taste auf der Tastatur das Popup schließt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* ESC-Taste schließt das Popup.
    - *Deaktiviert:* ESC-Taste hat keine Auswirkung auf das Popup.
  - **Empfohlener Wert:** JA, für eine gute Benutzererfahrung.
  - **Händlerszenario / Beispiel:** Sie möchten eine zugängliche Möglichkeit bieten, damit Kunden das Popup schließen können, daher aktivieren Sie dies.
- **Benutzerdefiniertes CSS:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eigene benutzerdefinierte CSS-Regeln hinzuzufügen, um das Popup oder seinen Inhalt weiter zu gestalten. Dies ist für fortgeschrittene Benutzer oder Entwickler gedacht.
  - **Auswirkung der Änderung dieser Einstellung:** Alle gültigen CSS-Regeln, die Sie hier hinzufügen, werden auf das Popup angewendet und überschreiben möglicherweise Standardstile.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen.
  - **Händlerszenario / Beispiel:** Sie möchten die Schriftgröße eines bestimmten Absatzes in Ihrem Popup ändern oder einen einzigartigen Schatteneffekt hinzufügen, der in anderen Einstellungen nicht verfügbar ist. Sie würden das CSS hier hinzufügen.

**Registerkarte „Erweiterte Einstellungen“ (oder ähnliche Gruppierung, falls verfügbar)**

- **Popup-Animation (Eintrittseffekt):**

  - **Was diese Einstellung bewirkt:** Wählt einen Animationseffekt für das Erscheinen des Popups auf dem Bildschirm.
  - **Auswirkung der Änderung dieser Einstellung:** Das Popup wird mit dem gewählten Effekt (z.B. Einblenden, Heruntergleiten, Zoomen) animiert.
  - **Empfohlener Wert:** „Einblenden“ oder „Heruntergleiten“ sind im Allgemeinen dezent und professionell.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Ihr Popup sanft erscheint, anstatt sofort aufzuspringen, daher wählen Sie „Einblenden“.
- **Popup-Animation (Austrittseffekt):**

  - **Was diese Einstellung bewirkt:** Wählt einen Animationseffekt für das Verschwinden des Popups vom Bildschirm.
  - **Auswirkung der Änderung dieser Einstellung:** Das Popup wird mit dem gewählten Effekt animiert.
  - **Empfohlener Wert:** „Ausblenden“ oder „Hochgleiten“, passend zum Eintrittseffekt.
  - **Händlerszenario / Beispiel:** Um eine konsistente und reibungslose Benutzererfahrung zu gewährleisten, wählen Sie „Ausblenden“ als Austrittsanimation.
- **Popup auf bestimmten Seiten anzeigen (URLs):**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, genaue URLs oder URL-Muster anzugeben, auf denen das Popup erscheinen soll (oder nicht).
  - **Auswirkung der Änderung dieser Einstellung:** Das Popup wird nur auf den Seiten angezeigt, die Ihren Kriterien entsprechen, oder von diesen ausgeblendet.
  - **Empfohlener Wert:** Verwenden Sie dies, um Ihre Popups effektiv auszurichten.
  - **Händlerszenario / Beispiel:** Sie haben ein Sonderangebot für eine bestimmte Produktkategorie. Sie würden die URL dieser Kategorieseite hier eingeben, um sicherzustellen, dass das Popup nur für relevante Besucher erscheint.
- **Popup auf bestimmten Seiten nicht anzeigen (URLs):**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, genaue URLs oder URL-Muster anzugeben, auf denen das Popup *nicht* erscheinen soll.
  - **Auswirkung der Änderung dieser Einstellung:** Das Popup wird auf den Seiten ausgeblendet, die Ihren Kriterien entsprechen.
  - **Empfohlener Wert:** Verwenden Sie dies, um die Anzeige von Popups auf sensiblen Seiten wie dem Checkout oder der Anmeldung zu vermeiden.
  - **Händlerszenario / Beispiel:** Sie möchten nicht, dass das Popup den Checkout-Prozess unterbricht. Sie würden hier die URL Ihrer Checkout-Seite (z.B. `/order`) hinzufügen.
- **Popup für bestimmte Kundengruppen anzeigen:**

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des Popups auf bestimmte Kundengruppen (z.B. Besucher, Kunden, Gäste, Großhändler).
  - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die den ausgewählten Gruppen angehören, sehen das Popup.
  - **Empfohlener Wert:** Hängt von Ihrer Zielgruppe ab. „Besucher“ und „Gäste“ sind üblich für die Lead-Generierung.
  - **Händlerszenario / Beispiel:** Sie haben ein Sonderangebot exklusiv für Ihre registrierten Kunden. Sie würden hier „Kunden“ auswählen.
- **Popup für bestimmte Sprachen anzeigen:**

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des Popups auf Kunden, die in bestimmten Sprachen browsen.
  - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die die ausgewählte Sprache verwenden, sehen das Popup.
  - **Empfohlener Wert:** Alle Sprachen oder spezifische, wenn Ihr Popup-Inhalt sprachabhängig ist.
  - **Händlerszenario / Beispiel:** Sie haben ein Popup mit Inhalt, der nur ins Englische und Französische übersetzt wurde. Sie würden hier „Englisch“ und „Französisch“ auswählen.
- **Popup für bestimmte Währungen anzeigen:**

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des Popups auf Kunden, die mit bestimmten Währungen browsen.
  - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die die ausgewählte Währung verwenden, sehen das Popup.
  - **Empfohlener Wert:** Alle Währungen oder spezifische, wenn Ihr Popup-Inhalt währungsabhängig ist.
  - **Händlerszenario / Beispiel:** Sie haben ein Sonderangebot, das nur für Kunden gilt, die in USD bezahlen. Sie würden hier „USD“ auswählen.
- **Popup für bestimmte Länder anzeigen:**

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des Popups auf Kunden aus bestimmten Ländern.
  - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die aus den ausgewählten Ländern stammen, sehen das Popup.
  - **Empfohlener Wert:** Alle Länder oder spezifische für geozielgerichtete Kampagnen.
  - **Händlerszenario / Beispiel:** Sie führen eine Aktion ausschließlich für Kunden in Frankreich durch. Sie würden hier „Frankreich“ auswählen.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Popup Pro aktivieren | JA | Hauptschalter zum Aktivieren/Deaktivieren des Popups. |
|  | Popup-Inhalt (HTML-Editor) | (Leer) | Gestalten Sie, was im Popup erscheint (Text, Bilder, Links). |
|  | Popup-Breite (px) | 600-800px | Legt die horizontale Größe des Popups fest. |
|  | Popup-Höhe (px) | auto (leer) | Legt die vertikale Größe des Popups fest oder passt sie automatisch an. |
|  | Popup anzeigen bei | Exit Intent / Seitenaufruf (3-5s Verzögerung) | Bestimmt den Auslöser für das Erscheinen des Popups. |
|  | Verzögerung vor dem Erscheinen des Popups (Sekunden) | 3-5 | Zeitverzögerung, bevor das Popup angezeigt wird (wenn „Seitenaufruf“ ausgewählt). |
|  | Popup-Häufigkeit (Tage) | 7-30 | Wie oft ein wiederkehrender Kunde das Popup sieht. |
|  | Popup auf mobilen Geräten anzeigen | JA | Steuert die Sichtbarkeit des Popups auf Telefonen/Tablets. |
|  | Popup-Hintergrundfarbe | #FFFFFF (Weiß) | Farbe des Hintergrunds des Popup-Fensters. |
|  | Popup-Rahmenfarbe | Transparent / Hellgrau | Farbe des Rahmens des Popups. |
|  | Popup-Rahmenbreite (px) | 0-2 | Dicke des Rahmens des Popups. |
|  | Popup-Rahmenradius (px) | 0-10 | Rundung der Ecken des Popups. |
|  | Overlay-Hintergrundfarbe | #000000 (Schwarz) | Farbe des halbtransparenten Hintergrunds hinter dem Popup. |
|  | Overlay-Deckkraft (0-100) | 50-80 | Transparenzstufe des Overlays. |
|  | Schließen-Button anzeigen | JA | Zeigt den 'X'-Button zum Schließen des Popups an. |
|  | Schließen durch Klicken außerhalb erlauben | JA | Ermöglicht das Schließen durch Klicken auf das Overlay. |
|  | Schließen durch ESC-Taste erlauben | JA | Ermöglicht das Schließen durch Drücken der ESC-Taste. |
|  | Benutzerdefiniertes CSS | (Leer) | Fügen Sie benutzerdefiniertes CSS für erweiterte Gestaltung hinzu. |
|  | Popup-Animation (Eintrittseffekt) | Einblenden / Heruntergleiten | Visueller Effekt beim Erscheinen des Popups. |
|  | Popup-Animation (Austrittseffekt) | Ausblenden / Hochgleiten | Visueller Effekt beim Verschwinden des Popups. |
|  | Popup auf bestimmten Seiten anzeigen (URLs) | (Leer) | Popup nur auf angegebenen URLs anzeigen. |
|  | Popup auf bestimmten Seiten nicht anzeigen (URLs) | (Leer) | Popup auf angegebenen URLs ausblenden (z.B. Checkout). |
|  | Popup für bestimmte Kundengruppen anzeigen | Alle | Popup auf bestimmte Kundentypen ausrichten. |
|  | Popup für bestimmte Sprachen anzeigen | Alle | Popup auf bestimmte Sprachen ausrichten. |
|  | Popup für bestimmte Währungen anzeigen | Alle | Popup auf bestimmte Währungen ausrichten. |
|  | Popup für bestimmte Länder anzeigen | Alle | Popup auf bestimmte Länder ausrichten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Popup wird überhaupt nicht angezeigt. Was sollte ich zuerst überprüfen?**
**A1:**

1.  **Ist das Modul aktiviert?** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Prestashop Popup Pro“ installiert und aktiviert ist.
2.  **Ist „Popup Pro aktivieren“ in der Modulkonfiguration auf JA eingestellt?** Dies ist der Hauptschalter.
3.  **Überprüfen Sie Ihre Einstellungen unter „Popup anzeigen bei“:** Wenn es auf „Zeitverzögerung“ eingestellt ist, stellen Sie sicher, dass die Verzögerung nicht zu lang ist. Wenn „Exit Intent“, stellen Sie sicher, dass Sie es korrekt auslösen (Maus aus dem Browserfenster bewegen).
4.  **Leeren Sie Ihren PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten und klicken Sie auf „Cache leeren“. Manchmal verhindern alte Cache-Dateien, dass neue Moduleinstellungen wirksam werden.
5.  **Suchen Sie nach Konflikten:** Deaktivieren Sie vorübergehend andere Popup- oder Overlay-Module, um festzustellen, ob ein Konflikt vorliegt.

**F2: Mein Popup sieht auf mobilen Geräten seltsam oder kaputt aus.**
**A2:**

1.  **Ist „Popup auf mobilen Geräten anzeigen“ aktiviert?** Wenn nicht, wird es überhaupt nicht angezeigt.
2.  **Überprüfen Sie Ihren „Popup-Inhalt“:** Komplexes HTML, sehr große Bilder oder Inhalte, die nicht für kleine Bildschirme konzipiert sind, können Probleme verursachen. Versuchen Sie, den Inhalt zu vereinfachen oder kleinere, optimierte Bilder zu verwenden.
3.  **Überprüfen Sie „Popup-Breite“ und „Popup-Höhe“:** Obwohl das Modul responsiv ist, können feste Pixelwerte auf sehr kleinen Bildschirmen manchmal Probleme verursachen. Erwägen Sie, „Popup-Höhe“ für `auto` leer zu lassen.
4.  **Benutzerdefiniertes CSS:** Wenn Sie benutzerdefiniertes CSS hinzugefügt haben, ist es möglicherweise nicht mobilfreundlich. Testen Sie Ihr CSS mit den Browser-Entwicklertools (Element untersuchen) auf verschiedenen Bildschirmgrößen.

**F3: Das Popup erscheint zu oft für meine Kunden. Wie kann ich das steuern?**
**A3:**

1.  **Passen Sie die „Popup-Häufigkeit (Tage)“ an:** Dies ist die Schlüsseleinstellung. Eine höhere Zahl bedeutet, dass Kunden das Popup seltener sehen. Wenn Sie es beispielsweise auf `30` einstellen, sehen sie es nach dem Schließen nur einmal im Monat.
2.  **Berücksichtigen Sie Ihre Einstellung „Popup anzeigen bei“:** Wenn es „Seitenaufruf“ mit einer kurzen Verzögerung ist, kann es aufdringlicher wirken als „Exit Intent“.

**F4: Ich möchte meinen Popup-Inhalt in mehrere Sprachen übersetzen. Wie mache ich das?**
**A4:** Der HTML-Editor für „Popup-Inhalt“ sollte die mehrsprachige Eingabe von PrestaShop unterstützen. Suchen Sie beim Bearbeiten des Inhalts nach Sprachregisterkarten oder Dropdowns (normalerweise oben rechts im Editor), um zwischen den Sprachen zu wechseln und für jede Sprache unterschiedliche Inhalte bereitzustellen. Stellen Sie sicher, dass die gewünschten Sprachen in PrestaShop installiert sind. Wenn der Editor keine Sprachregisterkarten anzeigt, müssen Sie den Inhalt für jede Sprache möglicherweise manuell eingeben, indem Sie Ihre Back-Office-Sprache wechseln.

**F5: Der Popup-Inhalt ist zu klein/groß, oder die Schrift ist falsch.**
**A5:**

1.  **Verwenden Sie den HTML-Editor:** Der integrierte HTML-Editor bietet normalerweise Optionen zum Ändern von Schriftgröße, Farbe und anderen Stilen für Ihren Text.
2.  **Benutzerdefiniertes CSS:** Für eine präzisere Kontrolle verwenden Sie das Feld „Benutzerdefiniertes CSS“. Um beispielsweise die Schriftgröße aller Texte im Popup zu ändern, könnten Sie Folgendes hinzufügen:

   ```
   .popuppro-content p { font-size: 16px !important;}
   ```

   (Möglicherweise müssen Sie das Popup in Ihrem Browser untersuchen, um die richtigen CSS-Selektoren wie `.popuppro-content` zu finden).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul Prestashop Popup Pro, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul Prestashop Popup Pro folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die Klasse `Module` für ihre Kernfunktionalität und `ModuleFrontController` für AJAX-Interaktionen nutzt. Es stützt sich stark auf JavaScript für die Front-Office-Anzeigelogik, Animationen und Ereignisbehandlung (wie Exit Intent). Die Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Das Modul integriert einen Smarty Templates Manager für flexible Inhaltserstellung und einen Farbwähler für die UI-Anpassung.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `popuppro/controllers/front/index.php`
    - **Klassenname:** `PopupproIndexModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention)
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dieser Controller könnte als allgemeiner Einstiegspunkt oder als Fallback für modulbezogene Front-Office-Anfragen dienen. Er könnte für das anfängliche Laden von Daten oder das Rendern einer grundlegenden Modulansicht verantwortlich sein, wenn keine spezifische Aktion angefordert wird.
  - `popuppro/controllers/front/popuploader.php`
    - **Klassenname:** `PopupproPopuploaderModuleFrontController`
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dieser Controller ist höchstwahrscheinlich für das dynamische Laden des Popup-Inhalts und der Konfiguration über AJAX verantwortlich. Wenn ein Benutzer eine Seite besucht, würde ein JavaScript-Skript eine AJAX-Anfrage an diesen Controller senden, um das HTML, die Stile und die Verhaltens-Einstellungen des Popups basierend auf der Modulkonfiguration abzurufen. Es würde eine JSON- oder HTML-Nutzlast zurückgeben.
  - `popuppro/controllers/front/popupstat.php`
    - **Klassenname:** `PopupproPopupstatModuleFrontController`
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dieser Controller ist darauf ausgelegt, statistische Daten im Zusammenhang mit dem Popup zu verarbeiten. Er würde AJAX-Anfragen vom Front-Office-JavaScript empfangen, um Popup-Impressionen, Klicks auf den Schließen-Button oder andere Interaktionen aufzuzeichnen, wodurch das Modul die Leistung verfolgen kann (obwohl eine dedizierte Statistikansicht nicht explizit in den Admin-Controllern aufgeführt ist, könnten diese Daten für die zukünftige Verwendung oder interne Protokollierung gespeichert werden).
- **Back-Office-Admin-Controller**: Keine explizit aufgeführt, was darauf hindeutet, dass die gesamte Administration über die Methode `getContent()` der Hauptmoduldatei erfolgt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` aufgeführt. Dies deutet darauf hin, dass das Modul seine Konfiguration hauptsächlich direkt in der Tabelle `ps_configuration` mithilfe von `Configuration::updateValue()` und `Configuration::get()` speichert und keine komplexen benutzerdefinierten Datenentitäten verwaltet, die dedizierte Datenbanktabellen oder `ObjectModel`-Mapping erfordern.

### 4.4 JavaScript-Assets (`views/js/`)

- `popuppro/js/popup-engine.js`:
  - **Umfang:** Front-Office.
  - **Detail:** Dies ist wahrscheinlich die zentrale JavaScript-Datei, die für die grundlegende Mechanik des Popups verantwortlich ist. Sie würde die Erstellung der Popup-DOM-Elemente (das Overlay, den Popup-Container, den Schließen-Button), das Einfügen des Inhalts, die Verwaltung von Animationen (Eintritts-/Austrittseffekte) und die Positionierung des Popups auf dem Bildschirm übernehmen. Sie definiert wahrscheinlich das Hauptobjekt `PopupPro` oder Ähnliches.
- `popuppro/js/popup-events.js`:
  - **Umfang:** Front-Office.
  - **Detail:** Dieses Skript würde alle Event-Listener verwalten, die das Popup auslösen. Dazu gehören:
    - `DOMContentLoaded` oder `window.load` für die initiale Einrichtung.
    - `setTimeout` für zeitverzögerte Popups.
    - Scroll-Event-Listener für scroll-ausgelöste Popups.
    - `mouseleave` oder ähnliche Events auf `document.body` zur Erkennung von Exit-Intent.
    - Klick-Listener für den Schließen-Button und das Schließen durch Klicken außerhalb.
    - `keyup`-Listener für die ESC-Taste.
    - AJAX-Aufrufe an `popuploader.php` zum Abrufen von Inhalten und an `popupstat.php` zum Aufzeichnen von Ereignissen.
- `popuppro/js/popup-scripts.js`:
  - **Umfang:** Front-Office.
  - **Detail:** Diese Datei könnte zusätzliche, vielleicht spezifischere Skripte enthalten, die sich auf das Popup-Verhalten oder Interaktionen beziehen, möglicherweise die Verarbeitung von Formularübermittlungen innerhalb des Popups, dynamische Inhaltsaktualisierungen oder die Integration mit anderen Front-Office-Elementen.
- `popuppro/js/script.js`:
  - **Umfang:** Front-Office/Back-Office (generischer Name, könnte beides sein).
  - **Detail:** Angesichts seines generischen Namens könnte dies ein allgemeines Dienstprogramm-Skript sein, oder es könnte die Initialisierungslogik für das Popup im Front-Office oder sogar einige kleinere Back-Office-Skripte enthalten, wenn es dort geladen wird. Es ist üblich, dass Module eine `script.js` für allgemeine Zwecke haben.
- `popuppro/js/tinymce16-force-urls.inc.js`, `popuppro/js/tinymce16.inc.js`:
  - **Umfang:** Back-Office.
  - **Detail:** Diese Dateien beziehen sich auf den TinyMCE Rich-Text-Editor, speziell Version 1.6. Sie sind enthalten, um die HTML-Editor-Funktionalität für das Feld „Popup-Inhalt“ in der Back-Office-Konfiguration des Moduls bereitzustellen. `tinymce16-force-urls.inc.js` stellt wahrscheinlich sicher, dass URLs innerhalb des Editors korrekt formatiert werden.
- `popuppro/jscolor/jscolor.js`:
  - **Umfang:** Back-Office.
  - **Detail:** Dies ist die JavaScript-Bibliothek für die Farbwählerfunktionalität, die in der Back-Office-Konfiguration verwendet wird (z.B. für Popup-Hintergrundfarbe, Rahmenfarbe, Overlay-Farbe). Sie bietet die interaktive Farbauswahl-Oberfläche.
- `popuppro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`:
  - **Umfang:** Back-Office.
  - **Detail:** Dieses Skript ist Teil einer internen Bibliothek zur Verwaltung von Smarty-Templates innerhalb der Modulkonfiguration. Es bietet wahrscheinlich Funktionen zum Vorschau von Templates, deren Auswahl oder zum dynamischen Einfügen von Template-basierten Inhalten in den HTML-Editor.

### 4.5 CSS-Stylesheets (`views/css/`)

- `popuppro/css.css`:
  - **Umfang:** Front-Office.
  - **Detail:** Dies ist wahrscheinlich das primäre Stylesheet für das Front-Office-Popup, das sein Standardaussehen definiert: Positionierung, Größe, Rahmen, Schatten, Styling des Schließen-Buttons und potenziell responsive Anpassungen.
  - **Wichtige Selektoren:** `.popuppro-overlay`, `.popuppro-popup`, `.popuppro-close-btn`, `.popuppro-content`.
- `popuppro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`:
  - **Umfang:** Back-Office.
  - **Detail:** Stylesheets für die Smarty Templates Manager-Oberfläche innerhalb der Back-Office-Konfiguration des Moduls. Es würde die Template-Auswahl, Vorschau-Bereiche und verwandte UI-Elemente gestalten.
- `popuppro/popuppro.css`:
  - **Umfang:** Front-Office.
  - **Detail:** Ähnlich wie `css.css` könnte dies zusätzliche oder spezifische Stile für das Popup enthalten, möglicherweise für verschiedene Animationszustände oder spezifische Inhaltselemente. Es könnte eine Überschneidung oder Trennung der Verantwortlichkeiten zwischen `css.css` und `popuppro.css` geben.
  - **Wichtige Selektoren:** Wahrscheinlich ähnlich wie `css.css`, mit Fokus auf die Haupt-Popup-Komponenten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: (Keine explizit in `views/templates/hook/` aufgeführt, aber `views/header.tpl` ist wahrscheinlich gehookt)

  - `popuppro/views/header.tpl`:
    - **Hook:** `displayHeader`
    - **Ausgabe:** Dieses Template ist mit ziemlicher Sicherheit in `displayHeader` gehookt. Es wäre dafür verantwortlich, die notwendigen JavaScript- und CSS-Dateien in den `<head>`-Bereich des Front-Office einzufügen und möglicherweise eine anfängliche HTML-Struktur oder Konfigurationsdaten für die Verwendung durch JavaScript zu initialisieren.
  - `popuppro/views/header_address.tpl`, `popuppro/views/header_carrier.tpl`:
    - **Hook:** Potenziell `displayHeader` oder andere spezifische Hooks im Zusammenhang mit Adress-/Versandinformationen.
    - **Ausgabe:** Dies scheinen spezialisierte Header-Templates zu sein, möglicherweise zur Anzeige dynamischer Inhalte im Zusammenhang mit Kundenadress- oder Versandinformationen *innerhalb* eines Popups oder für spezifische Popup-Szenarien. Ihre genaue Verwendung hängt von der Modullogik ab.
  - `popuppro/views/popup.tpl`:
    - **Hook:** Nicht direkt gehookt, sondern von JavaScript gerendert.
    - **Ausgabe:** Dies ist das Haupttemplate für die Front-Office-Popup-Struktur. Es definiert das HTML für das Overlay, den Popup-Container, den Schließen-Button und einen Platzhalter für den dynamischen Inhalt, der über AJAX geladen wird.
- **Admin-Templates (`views/templates/admin/`)**:

  - `popuppro/views/admin/admin.tpl`:
    - **Zweck:** Das Haupttemplate für die Konfigurationsseite des Moduls im Back Office. Es würde das Gesamtlayout, die Registerkarten und die Struktur für die Einstellungsformulare enthalten.
  - `popuppro/views/admin/boscript.tpl`:
    - **Zweck:** Back-Office-JavaScript-Template. Dies injiziert wahrscheinlich spezifischen JavaScript-Code, der für die Admin-Konfigurationsseite benötigt wird, wie z.B. die Initialisierung von TinyMCE, dem Farbwähler oder benutzerdefinierter Formularvalidierung.
  - `popuppro/views/admin/popup_preview.tpl`:
    - **Zweck:** Template zur Anzeige einer Live- oder simulierten Vorschau des Popups innerhalb der Back-Office-Konfiguration, damit Händler Änderungen sofort sehen können.
  - `popuppro/views/admin/presets.tpl`:
    - **Zweck:** Template zur Verwaltung oder Anzeige vordefinierter Popup-Templates oder -Stile.
  - `popuppro/views/admin/shadow_editor.tpl`:
    - **Zweck:** Ein spezialisiertes Template zur Konfiguration von Schatteneffekten für das Popup, das möglicherweise erweiterte Steuerelemente über einfache Farbe/Deckkraft hinaus bietet.
  - `popuppro/views/admin/stats.tpl`:
    - **Zweck:** Wenn das Modul Statistiken sammelt (wie von `popupstat.php` vorgeschlagen), würde dieses Template verwendet, um diese Statistiken im Back Office anzuzeigen.
  - `popuppro/views/templates/admin/_configure/helpers/form/form.tpl`:
    - **Zweck:** Dies ist ein Standard-PrestaShop-Override-Template für die Klasse `HelperForm`, speziell für das Konfigurationsformular des Moduls. Es ermöglicht dem Modul, die Darstellung seines Einstellungsformulars anzupassen, möglicherweise durch Hinzufügen benutzerdefinierter Felder oder Layouts.
- **SmartyTemplatesManager-Bibliotheks-Templates (`popuppro/lib/smartyTemplatesManager/tpl/` und `views/`)**:

  - `popuppro/lib/smartyTemplatesManager/tpl/cartMini.tpl`, `example.tpl`, `freeShippingBar.tpl`, `helloCustomer.tpl`, `lastOrder.tpl`, `productHighlight.tpl`, `showReachedQtyInCart.tpl`:
    - **Zweck:** Dies sind vordefinierte Inhaltstemplates, die der Händler auswählen oder als Ausgangspunkt für seinen Popup-Inhalt verwenden kann. Sie bieten gängige Anwendungsfälle wie Mini-Warenkorb-Anzeigen, Ankündigungen für kostenlosen Versand, Willkommensnachrichten, Details zur letzten Bestellung, Produkthighlights oder Meldungen über erreichte Mengen im Warenkorb. Diese würden dynamisch in den Haupt-Popup-Inhaltsbereich gerendert.
  - `popuppro/lib/smartyTemplatesManager/views/buttonManager.tpl`, `buttonManagerNoJs.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`:
    - **Zweck:** Diese Templates sind Teil der internen Smarty Templates Manager-Bibliothek, die innerhalb der Back-Office-Konfiguration verwendet wird, um die Inhaltstemplates zu verwalten und mit ihnen zu interagieren. Sie bieten eine Benutzeroberfläche zum Erstellen, Bearbeiten und Auswählen dieser vordefinierten Inhaltsblöcke.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen.
  - Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert. Die Namen der Schlüsselkonfigurationen folgen typischerweise dem Muster `POPUPPRO_SETTING_NAME`. Beispiele sind:
    - `POPUPPRO_ENABLED`
    - `POPUPPRO_CONTENT` (wahrscheinlich mehrsprachig)
    - `POPUPPRO_WIDTH`
    - `POPUPPRO_DISPLAY_ON`
    - `POPUPPRO_FREQUENCY`
    - `POPUPPRO_BG_COLOR`
    - …und so weiter für alle Konfigurationsoptionen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Fügt die notwendigen CSS- und JavaScript-Dateien für die Funktion des Popups ein und initialisiert möglicherweise globale JavaScript-Variablen oder Konfigurationsdaten. |
| `displayRightColumn` | Wird in der rechten Spalte von Seiten ausgeführt (falls vom Theme aktiviert). | Obwohl die Modulbeschreibung „Spalten“ erwähnt, ist dies für ein Vollbild-Popup weniger wahrscheinlich. Falls verwendet, könnte es einen Auslöser für das Popup oder ein kleineres, nicht-überlagerndes Element rendern. |
| `displayLeftColumn` | Wird in der linken Spalte von Seiten ausgeführt (falls vom Theme aktiviert). | Ähnlich wie `displayRightColumn`, weniger wahrscheinlich für das Haupt-Popup, könnte aber für einen Auslöser verwendet werden. |
| `displayFooter` | Wird am Ende jeder Front-Office-Seite, vor dem schließenden `</body>`-Tag, ausgeführt. | Könnte verwendet werden, um JavaScript einzufügen, das nach dem vollständigen Laden des DOM ausgeführt werden muss, oder um die HTML-Struktur des Popups ganz am Ende des Dokuments zu platzieren. |
| `displayProductAdditionalInfo` (oder ähnlicher Produktdetailseiten-Hook) | Wird auf der Produktseite ausgeführt, typischerweise unterhalb der Hauptproduktdetails. | Wenn das Modul produktspezifische Popups unterstützt, könnte es diesen Hook verwenden, um einen Auslöser oder eine spezifische Popup-Logik einzufügen, die für das Produkt relevant ist. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) festlegt. | Ein gängiger Hook für Module, um ihre Assets (CSS/JS) effizient zu registrieren und sicherzustellen, dass sie nur bei Bedarf geladen werden. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung mit Ihrem Prestashop Popup Pro Modul besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser engagiertes Support-Team hilft Ihnen gerne dabei, das Potenzial Ihres Moduls optimal zu nutzen.
