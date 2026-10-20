---
title: "Popup Slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Popup Slider von MyPresta.eu."
sidebar:
  label: "Popup Slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Popup Slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/popup-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/popup-slider/)
>
> ---


# Popup Slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul Popup Slider, auf dem Sie festlegen, wie Ihr Popup aussieht und sich verhält.

#### Allgemeine Einstellungen

- **Popup-Breite (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Breite des Popup-Fensters in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf einen bestimmten Wert (z. B. 800) eingestellt:* Das Popup erscheint auf Desktop-Bildschirmen genau 800 Pixel breit.
    - *Wenn auf einen anderen Wert eingestellt:* Das Popup wird entsprechend angepasst.
  - **Empfohlener Wert:** 800px (oder an Ihre Bildgrößen und Ihr Design anpassen).
  - **Händlerszenario / Beispiel:** Wenn Ihre Slider-Bilder 800px breit sind, stellt die Einstellung auf 800px sicher, dass sie perfekt passen, ohne Skalierungsprobleme.
- **Popup-Höhe (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Höhe des Popup-Fensters in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf einen bestimmten Wert (z. B. 500) eingestellt:* Das Popup erscheint genau 500 Pixel hoch.
    - *Wenn auf einen anderen Wert eingestellt:* Das Popup wird entsprechend angepasst.
  - **Empfohlener Wert:** 500px (oder an Ihre Bildgrößen und Ihr Design anpassen).
  - **Händlerszenario / Beispiel:** Wenn Ihre Slider-Bilder 500px hoch sind, stellt die Einstellung auf 500px sicher, dass sie perfekt passen.
- **Popup-Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe des Popup-Fensters selbst fest (der Bereich hinter Ihren Slider-Bildern). Sie können einen Farbwähler verwenden, um eine Farbe auszuwählen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe (z. B. #FFFFFF für Weiß) eingestellt:* Der Hintergrund des Popups wird diese Farbe anzeigen.
    - *Wenn auf eine andere Farbe eingestellt:* Die Hintergrundfarbe ändert sich.
  - **Empfohlener Wert:** #FFFFFF (Weiß) oder eine Farbe, die das Design Ihres Shops ergänzt.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop ein dunkles Thema hat, könnten Sie ein helles Grau (#F5F5F5) für den Popup-Hintergrund wählen, um den Inhalt hervorzuheben.
- **Popup-Rahmenfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Rahmens um das Popup-Fenster fest.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe (z. B. #CCCCCC für Hellgrau) eingestellt:* Das Popup hat einen Rahmen dieser Farbe.
    - *Wenn auf eine andere Farbe eingestellt:* Die Rahmenfarbe ändert sich.
  - **Empfohlener Wert:** #CCCCCC (Hellgrau) oder eine Farbe, die zu Ihrer Marke passt.
  - **Händlerszenario / Beispiel:** Ein subtiler Rahmen kann helfen, das Popup von einem belebten Hintergrund abzugrenzen.
- **Popup-Rahmenbreite (px):**

  - **Was diese Einstellung bewirkt:** Definiert die Dicke des Popup-Rahmens in Pixeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 1 eingestellt:* Der Rahmen ist 1 Pixel dick.
    - *Wenn auf 0 eingestellt:* Es ist kein Rahmen sichtbar.
  - **Empfohlener Wert:** 1px oder 0px.
  - **Händlerszenario / Beispiel:** Ein 0px-Rahmen kann einen nahtloseren, moderneren Look erzeugen, wenn Ihr Design keinen sichtbaren Rahmen erfordert.
- **Popup-Rahmenradius (px):**

  - **Was diese Einstellung bewirkt:** Steuert die Rundung der Ecken des Popups. Ein höherer Wert bedeutet rundere Ecken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 0 eingestellt:* Das Popup hat scharfe, quadratische Ecken.
    - *Wenn auf 10 eingestellt:* Die Ecken sind leicht abgerundet.
  - **Empfohlener Wert:** 5px oder 0px.
  - **Händlerszenario / Beispiel:** Abgerundete Ecken können Ihrem Popup eine weichere, modernere Ästhetik verleihen.
- **Popup-Schatten:**

  - **Was diese Einstellung bewirkt:** Fügt einen Schatteneffekt um das Popup hinzu, wodurch es über der Seite zu schweben scheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Ein subtiler Schatten erscheint um das Popup.
    - *Wenn deaktiviert (NEIN):* Das Popup hat keinen Schatten.
  - **Empfohlener Wert:** JA.
  - **Händlerszenario / Beispiel:** Ein Schatten hilft dem Popup, sich vom Hintergrundinhalt abzuheben, was die Sichtbarkeit und die wahrgenommene Tiefe verbessert.
- **Popup-Overlay-Farbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des halbtransparenten Overlays fest, das den restlichen Shop-Inhalt bedeckt, wenn das Popup aktiv ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe (z. B. #000000 für Schwarz) eingestellt:* Das Overlay hat diese Farbe.
  - **Empfohlener Wert:** #000000 (Schwarz).
  - **Händlerszenario / Beispiel:** Ein dunkles Overlay hilft, die Aufmerksamkeit des Besuchers ausschließlich auf den Popup-Inhalt zu lenken.
- **Popup-Overlay-Deckkraft (0-1):**

  - **Was diese Einstellung bewirkt:** Steuert die Transparenz des Overlays. 0 ist vollständig transparent, 1 ist vollständig undurchsichtig.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 0.5 eingestellt:* Das Overlay ist 50% transparent, sodass ein Teil des Hintergrund-Shop-Inhalts sichtbar ist.
    - *Wenn auf 0.8 eingestellt:* Das Overlay ist 80% undurchsichtig, wodurch der Hintergrundinhalt sehr dunkel wird.
  - **Empfohlener Wert:** 0.7 oder 0.8.
  - **Händlerszenario / Beispiel:** Eine höhere Deckkraft stellt sicher, dass das Popup im Mittelpunkt steht, während eine geringere Deckkraft verwendet werden könnte, wenn Sie subtil auf den Inhalt hinter dem Popup hinweisen möchten.
- **Popup-Wiederanzeigezeit (Stunden):**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie viele Stunden vergehen müssen, bevor das Popup demselben Besucher erneut angezeigt wird, nachdem er es geschlossen hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 0 eingestellt:* Das Popup erscheint jedes Mal, wenn der Besucher eine Seite lädt (nicht empfohlen für die Benutzererfahrung).
    - *Wenn auf 24 eingestellt:* Das Popup erscheint nach 24 Stunden erneut.
    - *Wenn auf eine sehr hohe Zahl (z. B. 8760 für 1 Jahr) eingestellt:* Das Popup wird effektiv nur einmal pro Besucher angezeigt.
  - **Empfohlener Wert:** 24 (für tägliche Aktionen) oder 168 (für wöchentliche Aktionen) oder eine sehr hohe Zahl wie 8760 (für einmal pro Jahr oder effektiv einmalig).
  - **Händlerszenario / Beispiel:** Wenn Sie tägliche Angebote haben, stellt die Einstellung auf 24 Stunden sicher, dass Besucher das neue Angebot jeden Tag sehen. Wenn Sie eine Willkommensnachricht nur einmal anzeigen möchten, stellen Sie sie auf eine sehr hohe Zahl ein.
- **Schließen-Button anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des 'X'-Schließen-Buttons im Popup um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Ein Schließen-Button ist sichtbar, sodass Besucher das Popup leicht schließen können.
    - *Wenn deaktiviert (NEIN):* Es wird kein Schließen-Button angezeigt. Besucher müssen außerhalb des Popups klicken oder wegnavigieren, um es zu schließen.
  - **Empfohlener Wert:** JA.
  - **Händlerszenario / Beispiel:** Bieten Sie immer eine klare Möglichkeit für Benutzer, das Popup zu schließen, um Frustration zu vermeiden und die Benutzererfahrung zu verbessern.
- **Bei Overlay-Klick schließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob das Klicken auf das halbtransparente Overlay (außerhalb des Popup-Inhalts) das Popup schließt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Klicken auf das Overlay schließt das Popup.
    - *Wenn deaktiviert (NEIN):* Nur der Schließen-Button (falls aktiviert) oder das Wegnavigieren schließt das Popup.
  - **Empfohlener Wert:** JA.
  - **Händlerszenario / Beispiel:** Dies bietet eine intuitive und gängige Möglichkeit für Benutzer, Popups zu schließen, was die Benutzerfreundlichkeit verbessert.

#### Slider-Bilder-Konfiguration

Dieser Abschnitt ermöglicht es Ihnen, die Bilder, die in Ihrem Popup-Slider erscheinen, hinzuzufügen, zu bearbeiten und zu verwalten. Sie können eine unbegrenzte Anzahl von Bildern hinzufügen.

Für jeden Bild-Slot finden Sie typischerweise:

- **Bild-Upload-Feld:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Hochladen einer Bilddatei von Ihrem Computer, die im Slider angezeigt werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Bild hochgeladen wird:* Es ersetzt ein vorhandenes Bild in diesem Slot oder fügt ein neues zum Slider hinzu.
  - **Empfohlener Wert:** Verwenden Sie hochwertige, optimierte Bilder, die dem Seitenverhältnis Ihrer Popup-Breite/-Höhe entsprechen.
  - **Händlerszenario / Beispiel:** Laden Sie Ihr neuestes Produktfoto, ein Banner für einen Sale oder eine Grafik hoch, die eine neue Funktion bewirbt.
- **Bild-Link (URL):**

  - **Was diese Einstellung bewirkt:** Gibt die URL an, zu der Besucher weitergeleitet werden, wenn sie auf dieses spezifische Slider-Bild klicken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine URL eingegeben wird:* Das Klicken auf das Bild führt den Besucher zu dieser Seite.
    - *Wenn leer gelassen:* Das Bild ist nicht anklickbar.
  - **Empfohlener Wert:** Verlinken Sie immer auf relevante Seiten (Produkt, Kategorie, Blogbeitrag, Kontaktseite).
  - **Händlerszenario / Beispiel:** Verlinken Sie ein „Neuheiten“-Banner auf Ihre neue Produktkategorieseite oder ein „Sommer-Sale“-Banner auf Ihre Sale-Landingpage.
- **Bildtitel/Alt-Text:**

  - **Was diese Einstellung bewirkt:** Bietet eine Textbeschreibung für das Bild. Dieser Text ist wichtig für SEO (Suchmaschinen) und Barrierefreiheit (Screenreader für sehbehinderte Benutzer).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Text eingegeben wird:* Dieser Text wird von Suchmaschinen verwendet, um den Bildinhalt zu verstehen, und von Screenreadern, um das Bild zu beschreiben.
  - **Empfohlener Wert:** Eine prägnante, beschreibende Phrase, die den Bildinhalt genau beschreibt und relevante Keywords enthält.
  - **Händlerszenario / Beispiel:** Für ein Bild eines neuen Kleides verwenden Sie „Neues Sommerkollektionskleid - Jetzt kaufen“.
- **Bild löschen-Button:**

  - **Was diese Einstellung bewirkt:** Entfernt das ausgewählte Bild aus dem Slider.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Beim Klicken:* Das Bild und die zugehörigen Einstellungen werden aus der Slider-Konfiguration entfernt.
  - **Empfohlener Wert:** Verwenden Sie dies, um veraltete Aktionen oder Bilder zu entfernen.
  - **Händlerszenario / Beispiel:** Löschen Sie nach dem Ende eines Sales das Bannerbild, das diesen Sale beworben hat.
- **Neues Bild hinzufügen-Button:**

  - **Was diese Einstellung bewirkt:** Fügt einen neuen leeren Slot hinzu, damit Sie ein weiteres Bild in den Slider hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Beim Klicken:* Ein neuer Satz von Bild-Upload-, Link- und Titelfeldern erscheint.
  - **Empfohlener Wert:** Verwenden Sie dies, um Ihren Slider-Inhalt zu erweitern.
  - **Händlerszenario / Beispiel:** Fügen Sie einen neuen Slide für eine bevorstehende Feiertagsaktion hinzu.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Popup-Breite (px) | 800 | Legt die Breite des Popup-Fensters fest. |
| Modulkonfiguration | Popup-Höhe (px) | 500 | Legt die Höhe des Popup-Fensters fest. |
| Modulkonfiguration | Popup-Hintergrundfarbe | #FFFFFF | Hintergrundfarbe des Popup-Inhaltsbereichs. |
| Modulkonfiguration | Popup-Rahmenfarbe | #CCCCCC | Farbe des Rahmens um das Popup. |
| Modulkonfiguration | Popup-Rahmenbreite (px) | 1 | Dicke des Popup-Rahmens. |
| Modulkonfiguration | Popup-Rahmenradius (px) | 5 | Rundung der Popup-Ecken. |
| Modulkonfiguration | Popup-Schatten | JA | Fügt einen Schatteneffekt für Tiefe hinzu. |
| Modulkonfiguration | Popup-Overlay-Farbe | #000000 | Farbe des halbtransparenten Hintergrund-Overlays. |
| Modulkonfiguration | Popup-Overlay-Deckkraft (0-1) | 0.7 | Transparenzstufe des Overlays. |
| Modulkonfiguration | Popup-Wiederanzeigezeit (Stunden) | 24 | Wie lange, bevor das Popup einem Besucher erneut angezeigt wird. |
| Modulkonfiguration | Schließen-Button anzeigen | JA | Zeigt einen 'X'-Button zum Schließen des Popups an. |
| Modulkonfiguration | Bei Overlay-Klick schließen | JA | Ermöglicht das Schließen des Popups durch Klicken außerhalb. |
| Modulkonfiguration | Bild-Upload-Feld | N/A | Lädt ein Bild für einen Slide hoch. |
| Modulkonfiguration | Bild-Link (URL) | N/A | URL, zu der beim Klicken auf das Slide-Bild navigiert werden soll. |
| Modulkonfiguration | Bildtitel/Alt-Text | N/A | Beschreibender Text für SEO und Barrierefreiheit. |
| Modulkonfiguration | Bild löschen-Button | N/A | Entfernt einen Slide aus dem Slider. |
| Modulkonfiguration | Neues Bild hinzufügen-Button | N/A | Fügt einen neuen leeren Slide-Slot hinzu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Popup wird überhaupt nicht angezeigt. Was soll ich überprüfen?**
A1:

- **Modul aktiviert:** Stellen Sie zunächst sicher, dass das Modul unter **Module > Modul-Manager** aktiviert ist.
- **Konfiguration gespeichert:** Stellen Sie sicher, dass Sie Ihre Konfigurationseinstellungen nach Änderungen gespeichert haben.
- **Bilder hinzugefügt:** Haben Sie mindestens ein Bild zur Slider-Konfiguration hochgeladen? Der Slider wird nicht angezeigt, wenn keine Bilder vorhanden sind.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**) und Ihren Browser-Cache. Manchmal verhindern alte Cache-Dateien, dass neue Modulinhalte geladen werden.
- **Wiederanzeigezeit:** Wenn Sie Ihre Website zuvor besucht haben, könnte die „Popup-Wiederanzeigezeit“ verhindern, dass es erneut angezeigt wird. Versuchen Sie, Ihren Shop in einem Inkognito-/privaten Browserfenster zu öffnen, um einen Erstbesucher zu simulieren.

**F2: Mein Popup sieht seltsam aus oder ist auf meinem benutzerdefinierten Theme nicht richtig zentriert.**
A2:

- **Theme-Konflikte:** Benutzerdefinierte Themes haben manchmal widersprüchliche CSS-Stile.
- **Breiten-/Höheneinstellungen:** Überprüfen Sie Ihre Einstellungen für „Popup-Breite“ und „Popup-Höhe“ in der Modulkonfiguration. Stellen Sie sicher, dass sie für Ihre Bilder und Bildschirmgrößen geeignet sind.
- **Entwicklerhilfe:** Wenn das Problem weiterhin besteht, könnte eine kleine CSS-Anpassung durch einen Webentwickler erforderlich sein, der mit Ihrem Theme vertraut ist. Dieser kann die Elemente überprüfen und benutzerdefinierte Stile anwenden, um Konflikte zu beheben.

**F3: Die Bilder in meinem Slider sind unscharf oder verzerrt.**
A3:

- **Bildqualität:** Stellen Sie sicher, dass die von Ihnen hochgeladenen Bilder hochauflösend und nicht verpixelt sind.
- **Seitenverhältnis:** Die Bilder sollten idealerweise dem Seitenverhältnis (Breiten- zu Höhenverhältnis) entsprechen, das Sie für Ihre „Popup-Breite“ und „Popup-Höhe“ festgelegt haben. Wenn Ihre Bilder ein anderes Verhältnis haben, könnten sie gestreckt oder gestaucht werden, um zu passen.
- **Bildoptimierung:** Hohe Auflösung ist gut, aber übermäßig große Dateigrößen können Ihre Website verlangsamen. Optimieren Sie Ihre Bilder für die Webnutzung (z. B. komprimieren Sie sie), bevor Sie sie hochladen.

**F4: Kann ich verschiedene Popups für verschiedene Seiten oder Kundengruppen haben?**
A4: Das Modul Popup Slider zeigt in seiner aktuellen Version ein einziges, globales Popup allen Besuchern basierend auf der Wiederanzeige-Logik an. Es unterstützt nicht nativ verschiedene Popups für bestimmte Seiten oder Kundengruppen. Für solch erweiterte Funktionen benötigen Sie typischerweise ein komplexeres Modul oder eine kundenspezifische Entwicklung.

**F5: Wie übersetze ich den Text des Moduls (z. B. den Text des Schließen-Buttons, falls vorhanden)?**
A5: Obwohl dieses Modul hauptsächlich Bilder verwendet, wären alle Standard-Textelemente über das PrestaShop-Übersetzungssystem übersetzbar:

- Navigieren Sie zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“.
- Wählen Sie Ihr Theme, Ihre Sprache und suchen Sie dann „Popup Slider“ in der Modulliste.
- Sie können dann alle übersetzbaren Zeichenfolgen bearbeiten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Einblick in die Architektur des Popup Slider-Moduls, der für Entwickler und Webmaster gedacht ist.

### 4.1 Architekturübersicht

Das Modul Popup Slider (`popupslider/cz.php`) ist ein klassisches PrestaShop 1.4-1.6 Modul, das hauptsächlich die `Module`-Klasse für seine Kernfunktionalität nutzt. Es integriert sich in das Front-Office über einen Hook (typischerweise `displayHeader` oder `displayFooter` implizit, obwohl die Dokumentation `Header, Columns, Product oder Footer` als potenzielle Anzeigebereiche erwähnt, deutet die bereitgestellte Vorlage `header.tpl` darauf hin, dass `displayHeader` der primäre Integrationspunkt ist). Die Konfiguration wird über die Methode `getContent()` verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Die Front-Office-Interaktion wird durch das Injizieren von JavaScript und CSS gehandhabt, das dann den Slider mithilfe der bxSlider-Bibliothek rendert.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Alle Konfigurationsdaten werden direkt in der `ps_configuration`-Tabelle mithilfe der Standardmethoden `Configuration::get()` und `Configuration::updateValue()` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul stützt sich stark auf JavaScript für seine Front-Office-Funktionalität, insbesondere für das Popup- und Slider-Verhalten.

- **`popupslider/jscolor/jscolor.js`**:

  - **Geltungsbereich:** Back-Office (wird innerhalb der Konfigurationsseite des Moduls verwendet).
  - **Verantwortlichkeit:** Bietet eine JavaScript-Farbwählerfunktion für das Konfigurationsformular des Moduls, die es Händlern ermöglicht, Farben für den Popup-Hintergrund, den Rahmen und das Overlay einfach auszuwählen.
  - **Details:** Dies ist eine Drittanbieterbibliothek, die zur UI-Verbesserung im Admin-Panel integriert ist.
- **`popupslider/js/bxslider.js`**:

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dies ist die Kernbibliothek für den animierten Bild-Slider innerhalb des Popups. Sie verwaltet die Übergänge, Navigationssteuerungen (Pfeile, Punkte) und das responsive Verhalten der Diashow.
  - **Details:** Ein weit verbreiteter jQuery-Inhalts-Slider. Das Modul initialisiert diesen Slider auf den Bildern innerhalb des Popups.
- **`popupslider/js/script.js`**:

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses benutzerdefinierte Skript orchestriert das Erscheinungsbild und Verhalten des Popups.
    - **Cookie-Verwaltung:** Überprüft ein Cookie, um festzustellen, ob der Benutzer ein Erstbesucher ist oder ob die Wiederanzeigezeit abgelaufen ist.
    - **Popup-Anzeige:** Löst die Anzeige des Popup-Overlays und des Slider-Inhalts aus.
    - **Ereignisbehandlung:** Bindet Ereignisse zum Schließen des Popups (z. B. Klicken auf den Schließen-Button, Klicken auf das Overlay).
    - **bxSlider-Initialisierung:** Initialisiert den `bxslider.js` auf dem entsprechenden DOM-Element, das die Slider-Bilder enthält.
  - **Details:** Dieses Skript ist entscheidend für die „intelligente“ Anzeigelogik und Benutzerinteraktion des Moduls.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul listet in der bereitgestellten Inventur keine expliziten benutzerdefinierten CSS-Dateien auf. Es ist jedoch sehr wahrscheinlich, dass die `bxslider.js`-Bibliothek ihr eigenes CSS (z. B. `jquery.bxslider.css` oder ähnliches) enthält, das geladen würde, und die `header.tpl` oder `cz.php` des Moduls Inline-Stile basierend auf Konfigurationseinstellungen (Farben, Dimensionen) injizieren könnte.

Wenn CSS-Dateien vorhanden wären, würden sie typischerweise:

- **Geltungsbereich:** Front-Office (für Popup- und Slider-Styling).
- **Haupt-UI-Komponenten:** Gestalten den Popup-Container, das Overlay, den Schließen-Button, die Slider-Navigation (Pfeile, Punkte) und einzelne Slide-Bilder.
- **Wichtige CSS-Klassenselektoren:** Entwickler sollten nach Klassen wie `.popupslider-overlay`, `.popupslider-container`, `.popupslider-close`, `.bx-wrapper`, `.bx-viewport`, `.bx-controls` usw. suchen, um sie in der `custom.css` ihres Themes oder in einem Child-Theme zu überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`popupslider/header.tpl`**:
    - **Hook:** Wahrscheinlich `displayHeader` (oder ähnlich, angesichts des Namens). Dieses Template ist für das Rendern der HTML-Struktur des Popup-Overlays, des Popup-Containers und des Bild-Sliders selbst verantwortlich.
    - **Ausgabe:** Es generiert die notwendigen `div`-Elemente für das Overlay, das Haupt-Popup-Feld, den Schließen-Button und die `ul`-Liste, die `bxslider.js` in eine interaktive Diashow umwandeln wird. Es enthält wahrscheinlich auch Inline-Stile, die von den Konfigurationseinstellungen des Moduls (Breite, Höhe, Farben usw.) abgeleitet sind, und bindet die notwendigen JavaScript- und CSS-Assets ein.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert.
  - **Konfigurationsschlüssel (Beispiele):**
    - `POPUP_SLIDER_WIDTH`
    - `POPUP_SLIDER_HEIGHT`
    - `POPUP_SLIDER_BG_COLOR`
    - `POPUP_SLIDER_BORDER_COLOR`
    - `POPUP_SLIDER_BORDER_WIDTH`
    - `POPUP_SLIDER_BORDER_RADIUS`
    - `POPUP_SLIDER_SHADOW`
    - `POPUP_SLIDER_OVERLAY_COLOR`
    - `POPUP_SLIDER_OVERLAY_OPACITY`
    - `POPUP_SLIDER_REDISPLAY_TIME`
    - `POPUP_SLIDER_SHOW_CLOSE_BTN`
    - `POPUP_SLIDER_CLOSE_ON_OVERLAY_CLICK`
    - `POPUP_SLIDER_IMAGE_X` (wobei X eine inkrementierende ID für jedes Bild ist, die URL, Link, Alt-Text speichert).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Wird verwendet, um die CSS- und JavaScript-Dateien des Moduls sowie potenziell die anfängliche HTML-Struktur für das Popup einzufügen (obwohl das Popup selbst normalerweise ausgeblendet ist, bis es durch JS ausgelöst wird). |
| `displayFooter` (Potenziell) | Wird am Ende des `<body>`-Bereichs jeder Front-Office-Seite ausgeführt. | Könnte als Alternative zu `displayHeader` verwendet werden, um das Popup-HTML und JS einzufügen, oft aus Leistungsgründen bevorzugt, da es das Seiten-Rendering nicht blockiert. |
| `displayRightColumn` (Potenziell) | Wird in der rechten Spalte des Front-Office ausgeführt. | Obwohl in der Händlerbeschreibung erwähnt, ist es unwahrscheinlich, dass ein Vollbild-Popup hier gerendert wird. Eher für ein kleines Banner oder einen Trigger. |
| `displayLeftColumn` (Potenziell) | Wird in der linken Spalte des Front-Office ausgeführt. | Ähnlich wie `displayRightColumn`, unwahrscheinlich für ein Vollbild-Popup. |
| `displayProductButtons` (Potenziell) | Wird auf der Produktseite, in der Nähe des In-den-Warenkorb-Buttons, ausgeführt. | Unwahrscheinlich für ein globales Popup, könnte aber für ein produktspezifisches Popup verwendet werden, wenn das Modul solche erweiterten Funktionen hätte. |

Angesichts der Datei `header.tpl` ist `displayHeader` der wahrscheinlichste Hook zum Einfügen der Assets und der anfänglichen Popup-Struktur des Moduls.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Popup Slider besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, Ihnen Unterstützung zu bieten und sicherzustellen, dass Ihr Modul optimal funktioniert.

- **MyPresta.eu Bestellhistorie & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support-Kontakt:** <https://mypresta.eu/contact>
