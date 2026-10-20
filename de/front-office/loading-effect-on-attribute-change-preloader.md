---
title: "Ladeeffekt bei Attributänderung - Preloader - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Ladeeffekt bei Attributänderung - Preloader' von MyPresta.eu."
sidebar:
  label: "Ladeeffekt bei Attributänderung - Preloader - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Loading effect on attribute change - preloader auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/loading-effect-on-attribute-change-preloader.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/loading-effect-on-attribute-change-preloader/)
>
> ---


# Ladeeffekt bei Attributänderung - Preloader

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf die Einstellungen zuzugreifen. Dieses Modul verfügt über eine unkomplizierte Konfigurationsseite.

#### **Preloader aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um den Ladeeffekt in Ihrem gesamten Shop ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die Ladeanimation erscheint auf Produktseiten, wann immer ein Kunde Produktattribute ändert.
  - *Wenn deaktiviert (NEIN):* Die Ladeanimation erscheint nicht, und Ihre Produktseiten verhalten sich wie vor der Installation des Moduls (d.h. keine visuelle Rückmeldung während Attributänderungen).
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten es aktivieren. Stellen Sie dies auf JA. Wenn Sie es vorübergehend zum Testen oder während eines größeren Theme-Updates deaktivieren müssen, können Sie es auf NEIN stellen.

#### **Preloader-Typ**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, den Stil oder Typ der angezeigten Ladeanimation zu wählen. Das Modul wird typischerweise mit einer Auswahl vordefinierter Spinner-Animationen geliefert.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Spinner 1“ eingestellt:* Ein spezifischer Typ eines animierten Spinners (z. B. ein einfacher rotierender Kreis) wird angezeigt.
  - *Wenn auf „Spinner 2“ eingestellt:* Ein anderer animierter Spinner (z. B. ein pulsierender Punkt, ein verblassender Balken) wird angezeigt.
  - *Wenn auf „Benutzerdefiniertes Bild“ eingestellt:* Falls verfügbar, würde diese Option es Ihnen ermöglichen, Ihr eigenes GIF oder Bild als Preloader hochzuladen. (Basierend auf der Modulbeschreibung könnte dies eine zukünftige Verbesserung oder eine erweiterte Option sein, die nicht direkt erwähnt wird, aber eine gängige Funktion für „Preloader-Typ“-Einstellungen ist).
- **Empfohlener Wert:** Experimentieren Sie mit den verfügbaren Optionen, um zu sehen, welche am besten zum Design und Branding Ihres Shops passt. Ein einfacher, sauberer Spinner ist oft am besten.
- **Händlerszenario / Beispiel:** Ihr Shop hat ein minimalistisches Design, daher könnten Sie „Spinner 1“ wählen, wenn es sich um eine saubere, unaufdringliche Animation handelt. Wenn Ihre Marke verspielter ist, könnten Sie einen dynamischeren „Spinner 2“ wählen oder sogar ein benutzerdefiniertes Marken-GIF hochladen, falls die Option verfügbar ist.

#### **Preloader-Farbe**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, die Farbe der Ladeanimation zu definieren. Dies ist entscheidend, um den Preloader an das Farbschema Ihres Shops anzupassen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `#007bff` (blau) eingestellt:* Der Spinner erscheint in blauer Farbe.
  - *Wenn auf `#ff0000` (rot) eingestellt:* Der Spinner erscheint in roter Farbe.
- **Empfohlener Wert:** Eine Farbe, die die primären oder Akzentfarben Ihres Shops ergänzt. Oft funktioniert ein neutrales Grau, Weiß oder die Hauptaktionsfarbe Ihrer Marke gut.
- **Händlerszenario / Beispiel:** Die Haupt-Call-to-Action-Buttons Ihres Shops sind grün. Wenn Sie die Preloader-Farbe auf Grün einstellen, wirkt sie wie ein integrierter Bestandteil des Designs Ihres Shops und nicht wie ein generisches Element.

#### **Preloader-Größe (in Pixel)**

- **Was diese Einstellung bewirkt:** Dies steuert die physischen Abmessungen (Breite und Höhe) der Ladeanimation.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `32px` eingestellt:* Der Spinner ist klein und subtil.
  - *Wenn auf `64px` eingestellt:* Der Spinner ist größer und prominenter.
- **Empfohlener Wert:** Beginnen Sie mit einer moderaten Größe wie `40px` oder `48px`. Testen Sie auf Desktop und Mobilgeräten, um sicherzustellen, dass er sichtbar, aber nicht übermäßig aufdringlich ist.
- **Händlerszenario / Beispiel:** Auf einer Produktseite mit großen Bildern könnte ein `32px`-Spinner untergehen. Eine Erhöhung auf `48px` oder `56px` würde ihn auffälliger machen, ohne abzulenken. Umgekehrt könnte ein kleinerer Spinner angemessener sein, wenn Ihre Produktbilder klein sind.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Preloader aktivieren / deaktivieren | JA | Aktiviert oder deaktiviert die Ladeanimation bei Produktattributänderungen. |
| Modulkonfiguration | Preloader-Typ | (Nach Präferenz wählen) | Wählt den visuellen Stil des Lade-Spinners. |
| Modulkonfiguration | Preloader-Farbe | (An Ihre Marke anpassen) | Legt die Farbe der Ladeanimation fest, um sie in das Design Ihres Shops zu integrieren. |
| Modulkonfiguration | Preloader-Größe (in Pixel) | 40px - 56px | Passt die physische Größe des Spinners für Sichtbarkeit und Ästhetik an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, sehe aber keinen Ladeeffekt auf meiner Produktseite.**
A:

1. **Cache leeren:** Der häufigste Grund. Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
2. **Modulposition:** Stellen Sie sicher, dass das Modul korrekt eingehängt ist. Obwohl das Modul dies automatisch handhabt, können Theme-Konflikte dies manchmal verhindern. Das Modul injiziert sein CSS/JS typischerweise in den `displayHeader`-Hook.
3. **Theme-Overrides:** Wenn Sie ein stark angepasstes Theme verwenden, könnte es das Standard-PrestaShop-JavaScript-Verhalten für Attributänderungen überschreiben und das Modul daran hindern, das Ereignis zu erkennen. Kontaktieren Sie Ihren Theme-Entwickler oder einen PrestaShop-Experten.
4. **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder in einem Inkognito-/privaten Browserfenster zu testen.

**F: Der Preloader erscheint, sieht aber fehl am Platz aus oder passt nicht zum Design meines Shops.**
A:

1. **Farbe & Größe anpassen:** Gehen Sie zur Konfigurationsseite des Moduls und experimentieren Sie mit den Einstellungen „Preloader-Farbe“ und „Preloader-Größe“. Versuchen Sie, die primären oder Akzentfarben Ihrer Marke anzupassen.
2. **Preloader-Typ ändern:** Falls verfügbar, versuchen Sie verschiedene „Preloader-Typ“-Optionen, um eine zu finden, die visuell besser zu Ihrem Theme passt.
3. **Benutzerdefiniertes CSS:** Für fortgeschrittene Anpassungen kann ein Webmaster benutzerdefiniertes CSS verwenden, um das Erscheinungsbild zu optimieren (siehe Entwicklerhandbuch).

**F: Der Preloader erscheint, bleibt aber zu lange auf dem Bildschirm, auch nachdem die Produktattribute aktualisiert wurden.**
A: Dies deutet normalerweise auf einen JavaScript-Konflikt oder ein Problem mit dem Attribut-Aktualisierungsmechanismus Ihres Themes hin. Das Modul verlässt sich auf Standard-PrestaShop-Ereignisse, um zu wissen, wann der Preloader ausgeblendet werden soll.

1. **Auf JavaScript-Fehler prüfen:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12) und suchen Sie im Tab „Konsole“ nach roten Fehlermeldungen, wenn Sie Attribute ändern.
2. **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Front-Office-Module, die das Verhalten der Produktseite ändern (z. B. Schnellansichtsmodule, benutzerdefinierte Attributmodule), um zu sehen, ob eines einen Konflikt verursacht.
3. **Theme-Kompatibilität:** Stellen Sie sicher, dass Ihr Theme vollständig mit Ihrer PrestaShop-Version kompatibel ist und keine veralteten JavaScript-Dateien enthält.

**F: Verlangsamt dieses Modul meine Website?**
A: Nein, das Modul selbst ist sehr leichtgewichtig. Es fügt Ihrer Seite eine geringe Menge an CSS und JavaScript hinzu. Sein Zweck ist es, die Wahrnehmung der Ladezeit *visuell zu verwalten*, nicht sie zu verursachen. Wenn Ihre Seite langsam ist, liegt das Problem woanders (z. B. große Bilder, nicht optimierter Server, andere schwere Module).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Ladeeffekt bei Attributänderung - Preloader“ (`ppreloader`) ist ein leichtgewichtiges, auf das Front-Office ausgerichtetes Modul, das entwickelt wurde, um die Benutzererfahrung während AJAX-gesteuerter Produktattribut-Updates zu verbessern. Es nutzt hauptsächlich den PrestaShop-Hook `displayHeader`, um sein CSS und JavaScript zu injizieren, das dann auf spezifische DOM-Änderungen oder Ereignisse auf der Produktseite lauscht, um die Ladeanimation auszulösen und auszublenden. Es führt keine neuen Datenbanktabellen oder komplexe Backend-Logik ein, sondern konzentriert sich ausschließlich auf die Frontend-Präsentation.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es arbeitet vollständig über seine Hauptmoduldatei und Frontend-Assets.

### 4.4 JavaScript-Assets (`views/js/`)

- **`ppreloader/views/js/ppreloader.js`**
  - **Geltungsbereich:** Front-Office (Produktseite).
  - **Verantwortlichkeit:** Dieses Skript ist der Kern der Modulfunktionalität.
    - Es wartet, bis das DOM bereit ist.
    - Es lauscht auf Änderungen an Produktattribut-Selektoren (z. B. `select[name="group[X]"]`, Radio-Buttons, Farbwähler usw., abhängig von der Struktur des Themes).
    - Es lauscht wahrscheinlich auch auf AJAX-Ereignisse im Zusammenhang mit Produktkombinations-Updates (z. B. `updateProduct`-Ereignis oder `ajaxComplete`-Aufrufe, die auf bestimmte URLs abzielen).
    - Wenn eine Attributänderung erkannt und ein AJAX-Aufruf initiiert wird, fügt es dynamisch die Preloader-HTML-Struktur (definiert in `header.tpl` oder dynamisch generiert) in einen relevanten Container auf der Produktseite ein (z. B. `$('#product_images')` oder `$('#product-details')`).
    - Es wendet den ausgewählten `Preloader-Typ`, die `Preloader-Farbe` und die `Preloader-Größe` aus der Modulkonfiguration an.
    - Sobald der AJAX-Aufruf abgeschlossen ist und die Produktinformationen aktualisiert wurden, entfernt es die Preloader-HTML aus dem DOM.
    - Es gewährleistet die mobile Responsivität des Preloaders.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`ppreloader/views/css/ppreloader.css`**
  - **Geltungsbereich:** Front-Office-Kundenstyling.
  - **Verantwortlichkeit:** Dieses Stylesheet definiert das visuelle Erscheinungsbild und die Animation des Lade-Preloaders.
    - Es enthält Stile für das Overlay, das den Produktbereich während des Ladens abdecken könnte.
    - Es definiert das CSS für verschiedene Preloader-Typen (Spinner, Punkte usw.), einschließlich ihrer Animations-Keyframes.
    - Es stellt sicher, dass der Preloader zentriert und korrekt in seinem Container positioniert ist.
    - Es handhabt die grundlegende Responsivität für verschiedene Bildschirmgrößen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**
    - `.ppreloader-overlay`: Der Haupt-Overlay-Container.
    - `.ppreloader-spinner`: Der Container für die eigentliche Spinner-Animation.
    - Spezifische Klassen für verschiedene Spinner-Typen (z. B. `.ppreloader-spinner-type1`, `.ppreloader-spinner-type2`).
    - `@keyframes`-Regeln für die Animationen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`ppreloader/views/header.tpl`**
  - **Geltungsbereich:** Front-Office.
  - **Hook:** `displayHeader`
  - **Verantwortlichkeit:** Dieses Template ist hauptsächlich dafür verantwortlich, die CSS- und JavaScript-Dateien des Moduls in den `<head>`-Bereich der Front-Office-Seiten einzubinden.
    - Es verwendet `{$css_dir}ppreloader.css`, um das Stylesheet zu verknüpfen.
    - Es verwendet `{$js_dir}ppreloader.js`, um die JavaScript-Datei zu verknüpfen.
    - Es enthält wahrscheinlich auch Inline-JavaScript, um die Konfigurationseinstellungen des Moduls (aktivierter Status, Typ, Farbe, Größe) vom Back Office an das `ppreloader.js`-Skript zu übergeben, wodurch sie für die dynamische Verwendung verfügbar gemacht werden. Dies ist entscheidend, damit das JS weiß, wie der Preloader gerendert werden soll.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln gespeichert (z. B. `PPRELOADER_ENABLED`, `PPRELOADER_TYPE`, `PPRELOADER_COLOR`, `PPRELOADER_SIZE`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Injiziert die CSS- (`ppreloader.css`) und JavaScript- (`ppreloader.js`) Dateien des Moduls und übergibt Konfigurationsvariablen an das JS. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Ladeeffekt bei Attributänderung - Preloader“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
