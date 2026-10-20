---
title: "Advanced Footer - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Advanced Footer von MyPresta.eu."
sidebar:
  label: "Advanced Footer - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Advanced Footer auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/advanced-footer.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/advanced-footer/)
>
> ---


# Advanced Footer

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine ungewöhnlichen Serveranforderungen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie das Erscheinungsbild Ihres erweiterten Footers definieren.

- **Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach „Advanced Footer“ > Klicken Sie auf „Konfigurieren“.

#### **Einstellungen & Optionen:**

1.  **Footer-Breite (`advf_f_width`)**

    - **Was diese Einstellung bewirkt:** Dies steuert die Gesamtbreite Ihres benutzerdefinierten Footer-Bereichs. Sie können einen festen Pixelwert oder einen Prozentsatz festlegen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf einen festen Pixelwert (z.B. `1200px`):* Der Footer hat immer genau diese Breite und ist auf der Seite zentriert. Auf sehr breiten Bildschirmen kann es an den Seiten leeren Raum geben. Auf schmaleren Bildschirmen können horizontale Scrollbalken entstehen, wenn der Wert zu groß ist.
      - *Bei Einstellung auf einen Prozentsatz (z.B. `100%`):* Der Footer dehnt sich aus, um die verfügbare Breite des Bildschirms auszufüllen, und passt sich dynamisch an. Dies wird im Allgemeinen für responsive Designs empfohlen.
    - **Empfohlener Wert:** `100%` für einen vollbreiten, responsiven Footer oder `1200px`, wenn Ihr Haupt-Shop-Inhaltsbereich eine feste Breite hat und Sie möchten, dass der Footer dazu passt.
    - **Händlerszenario / Beispiel:** Wenn der Hauptinhaltsbereich Ihres Shops 1200px breit ist, wird der Footer durch die Einstellung der Breite auf `1200px` perfekt ausgerichtet, wodurch ein kohärentes Design entsteht. Wenn Sie möchten, dass der Footer immer das gesamte Browserfenster einnimmt, ist `100%` die richtige Wahl.
2.  **Footer-Höhe (`advf_f_height`)**

    - **Was diese Einstellung bewirkt:** Dies definiert die Mindesthöhe Ihres Footer-Bereichs. Wenn Ihr Inhalt höher ist, wird der Footer automatisch erweitert.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf einen bestimmten Pixelwert (z.B. `280px`):* Der Footer ist immer mindestens so hoch. Dies kann nützlich sein, um eine konsistente visuelle Präsenz zu gewährleisten, auch wenn einige Seiten weniger Footer-Inhalt haben.
      - *Wenn leer gelassen oder auf `auto` gesetzt (falls verfügbar):* Die Höhe des Footers wird ausschließlich durch seinen Inhalt bestimmt.
    - **Empfohlener Wert:** `280px` oder `300px` ist ein guter Ausgangspunkt, um Ihrem Footer eine substanzielle Präsenz zu verleihen. Sie können dies basierend auf der Menge des Inhalts anpassen, den Sie hineinlegen möchten.
    - **Händlerszenario / Beispiel:** Sie möchten, dass Ihr Footer immer einen auffälligen Platz am unteren Rand der Seite einnimmt, auch wenn Sie nur wenige Links haben. Das Festlegen einer Mindesthöhe stellt sicher, dass er nicht zu dünn aussieht.
3.  **Footer-Hintergrundfarbe (`advf_f_bg`)**

    - **Was diese Einstellung bewirkt:** Hiermit können Sie eine einfarbige Hintergrundfarbe für Ihren gesamten Footer-Bereich auswählen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf eine Farbe (z.B. `#333333` für Dunkelgrau):* Der Footer-Hintergrund zeigt diese Farbe an.
      - *Wenn leer gelassen:* Der Footer könnte einen Hintergrund von Ihrem Theme erben oder transparent sein.
    - **Empfohlener Wert:** Eine Farbe, die zum Branding Ihres Shops passt. Dunklere Farben (wie Dunkelgrau oder Schwarz) sind für Footer üblich, aber eine hellere Farbe kann je nach Design auch funktionieren.
    - **Händlerszenario / Beispiel:** Ihre Marke verwendet einen bestimmten Blauton. Sie können den Footer-Hintergrund auf dieses Blau einstellen, um Ihre Markenidentität zu stärken.
4.  **Footer-Textfarbe (`advf_f_color`)**

    - **Was diese Einstellung bewirkt:** Dies legt die Standardfarbe für den gesamten Text in Ihrem Footer fest, einschließlich Links.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf eine Farbe (z.B. `#ffffff` für Weiß):* Der gesamte Text im Footer wird in dieser Farbe angezeigt.
      - *Wenn leer gelassen:* Die Textfarbe könnte von den Standardeinstellungen Ihres Themes geerbt werden, was möglicherweise nicht lesbar ist vor Ihrem gewählten Footer-Hintergrund.
    - **Empfohlener Wert:** Eine Farbe, die einen guten Kontrast zu Ihrer gewählten `Footer Background Color` bietet. Wenn Ihr Hintergrund dunkel ist, wählen Sie eine helle Textfarbe (z.B. Weiß, Hellgrau). Wenn Ihr Hintergrund hell ist, wählen Sie eine dunkle Textfarbe.
    - **Händlerszenario / Beispiel:** Sie haben einen dunkelgrauen Footer-Hintergrund. Das Einstellen der Textfarbe auf Weiß (`#ffffff`) stellt sicher, dass alle Ihre Links und Informationen leicht lesbar sind.
5.  **Footer-Link-Hover-Farbe (`advf_f_color_hover`)**

    - **Was diese Einstellung bewirkt:** Dies definiert die Farbe, in die Links in Ihrem Footer wechseln, wenn ein Kunde mit der Maus darüberfährt.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf eine Farbe (z.B. `#cccccc` für Hellgrau):* Links ändern ihre Farbe beim Hovern visuell in diese Farbe, was dem Benutzer Feedback gibt, dass das Element interaktiv ist.
      - *Wenn leer gelassen:* Links haben möglicherweise keinen Hover-Effekt, oder sie erben eine Standard-Hover-Farbe von Ihrem Theme, die möglicherweise nicht zu Ihrem Footer-Design passt.
    - **Empfohlener Wert:** Ein leicht anderer Farbton Ihrer `Footer Text Color` oder eine Akzentfarbe aus Ihrer Markenpalette. Es sollte auffällig, aber nicht störend sein.
    - **Händlerszenario / Beispiel:** Ihre Footer-Links sind weiß. Das Einstellen der Hover-Farbe auf ein helles Blau (`#ADD8E6`) bietet eine subtile, gebrandete Interaktion, wenn Kunden mit der Maus darüberfahren.
6.  **Footer-Hintergrundbild-URL (`advf_f_bg_url`)**

    - **Was diese Einstellung bewirkt:** Ermöglicht die Verwendung eines Bildes als Hintergrund für Ihren Footer anstelle oder zusätzlich zu einer Volltonfarbe. Sie müssen die vollständige URL zum Bild angeben.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn eine gültige URL angegeben wird:* Das Bild wird als Hintergrund des Footers angezeigt. Die `Footer Background Color` scheint durch, wenn das Bild transparent ist oder wenn das Bild nicht den gesamten Footer bedeckt.
      - *Wenn leer gelassen:* Es wird kein Hintergrundbild verwendet.
    - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben ein spezifisches, optimiertes Hintergrundbild. Falls verwendet, stellen Sie sicher, dass das Bild leichtgewichtig und relevant ist.
    - **Händlerszenario / Beispiel:** Sie haben ein subtiles Texturbild, das Sie als Hintergrund für Ihren Footer verwenden möchten, um visuelle Tiefe hinzuzufügen. Sie würden dieses Bild auf Ihren Server hochladen und seine URL hier einfügen.
7.  **Footer-Hintergrundbild-Position (`advf_f_bg_pos`)**

    - **Was diese Einstellung bewirkt:** Steuert, wie ein Hintergrundbild (falls festgelegt) innerhalb des Footer-Bereichs positioniert wird. Gängige Werte sind `center center`, `top left`, `bottom right` usw.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf `center center`:* Das Bild wird horizontal und vertikal zentriert.
      - *Bei Einstellung auf `top left`:* Das Bild beginnt in der oberen linken Ecke.
    - **Empfohlener Wert:** `center center` für die meisten Bilder oder `top left`, wenn Ihr Bild ein Muster ist, das von der Ecke aus beginnen soll.
    - **Händlerszenario / Beispiel:** Ihr Hintergrundbild ist ein kleines Logo, das einmal in der Mitte des Footers erscheinen soll. Sie würden dies auf `center center` einstellen.
8.  **Footer-Hintergrundbild-Wiederholung (`advf_f_bg_repeat`)**

    - **Was diese Einstellung bewirkt:** Bestimmt, ob und wie ein Hintergrundbild (falls festgelegt) wiederholt werden soll, um den Footer-Bereich auszufüllen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Einstellung auf `repeat`:* Das Bild wird horizontal und vertikal gekachelt.
      - *Bei Einstellung auf `no-repeat`:* Das Bild wird nur einmal angezeigt.
      - *Bei Einstellung auf `repeat-x`:* Das Bild wird nur horizontal gekachelt.
      - *Bei Einstellung auf `repeat-y`:* Das Bild wird nur vertikal gekachelt.
    - **Empfohlener Wert:** `no-repeat` für einzelne Bilder (wie ein Logo) oder `repeat`, wenn Ihr Bild ein kleines Muster ist, das zum Kacheln konzipiert wurde.
    - **Händlerszenario / Beispiel:** Sie haben ein winziges, nahtloses Musterbild. Wenn Sie dies auf `repeat` einstellen, bedeckt es den gesamten Footer-Bereich mit diesem Muster. Wenn es sich um ein einzelnes dekoratives Element handelt, ist `no-repeat` besser.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Footer-Breite (`advf_f_width`) | `100%` | Legt die Gesamtbreite des Footers fest. `100%` für responsive volle Breite, `1200px` für feste Breite. |
| Modulkonfiguration | Footer-Höhe (`advf_f_height`) | `280px` | Definiert die Mindesthöhe des Footers. Gewährleistet eine konsistente visuelle Präsenz. |
| Modulkonfiguration | Footer-Hintergrundfarbe (`advf_f_bg`) | (Ihre Markenfarbe) | Legt die einfarbige Hintergrundfarbe für den Footer fest. Entscheidend für Branding und Kontrast. |
| Modulkonfiguration | Footer-Textfarbe (`advf_f_color`) | (Kontrastierende Farbe) | Legt die Standardtextfarbe im Footer fest. Gewährleistet die Lesbarkeit vor dem Hintergrund. |
| Modulkonfiguration | Footer-Link-Hover-Farbe (`advf_f_color_hover`) | (Subtiler Akzent) | Definiert die Farbe von Links beim Überfahren mit der Maus. Verbessert das Benutzerinteraktions-Feedback. |
| Modulkonfiguration | Footer-Hintergrundbild-URL (`advf_f_bg_url`) | Leer lassen | URL zu einem Bild, das als Footer-Hintergrund verwendet werden soll. Fügt visuelle Textur oder Branding hinzu. |
| Modulkonfiguration | Footer-Hintergrundbild-Position (`advf_f_bg_pos`) | `center center` | Wie das Hintergrundbild positioniert wird. `center center` für die meisten Einzelbilder. |
| Modulkonfiguration | Footer-Hintergrundbild-Wiederholung (`advf_f_bg_repeat`) | `no-repeat` | Wie das Hintergrundbild gekachelt wird. `no-repeat` für Einzelbilder, `repeat` für Muster. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Footer-Änderungen werden im Front Office nicht angezeigt.**
**A1:** Dies ist normalerweise ein Caching-Problem.
\* Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Performance**.
\* Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
\* Wenn Sie ein Drittanbieter-Caching-Modul oder serverseitiges Caching (wie Varnish) verwenden, leeren Sie auch diese Caches.
\* Versuchen Sie auch, den Cache Ihres Browsers zu leeren (Strg+F5 oder Cmd+Shift+R).

**F2: Der Footer sieht auf Mobilgeräten anders aus als auf dem Desktop.**
**A2:** Das ist zu erwarten und in der Regel gut so! Moderne PrestaShop-Themes sind responsiv, d.h. sie passen das Layout an verschiedene Bildschirmgrößen an. Die Einstellungen des Moduls (wie `Footer Width: 100%`) sind darauf ausgelegt, damit zu funktionieren. Wenn bestimmte Elemente fehlerhaft aussehen, könnte dies ein Konflikt mit dem CSS Ihres Themes sein.
\* **Fehlerbehebung:** Überprüfen Sie das mobil-spezifische CSS Ihres Themes. Wenn Sie benutzerdefinierte HTML-Inhalte zum Footer hinzugefügt haben, stellen Sie sicher, dass diese Inhalte ebenfalls responsiv sind. Möglicherweise müssen Sie einen Webmaster beauftragen, das CSS zu überprüfen.

**F3: Wie füge ich tatsächlichen Inhalt (Links, Text, Bilder) in diesen erweiterten Footer ein?**
**A3:** Dieses Modul bietet hauptsächlich das *Styling*-Framework (Hintergrund, Farben, Abmessungen) für Ihren Footer. Der *Inhalt* des Footers wird typischerweise über die Footer-Hooks Ihres PrestaShop-Themes (wie `displayFooter`) oder über andere Module, die für Inhaltsblöcke konzipiert sind (z.B. ein benutzerdefiniertes HTML-Block-Modul oder PrestaShops integriertes Link-Listen-Modul), verwaltet.
\* **Lösung:** Nachdem Sie den Stil des Advanced Footers konfiguriert haben, müssen Sie die Optionen Ihres Themes oder andere Inhaltsmodule verwenden, um den `displayFooter`-Hook mit Ihren gewünschten Links, Texten und Bildern zu füllen. Das Advanced Footer-Modul wendet dann sein Styling auf diesen Inhalt an.

**F4: Die von mir eingestellten Farben werden nicht auf alle Elemente in meinem Footer angewendet.**
**A4:** Dies kann passieren, wenn Ihr Theme sehr spezifische CSS-Regeln hat, die die Stile des Moduls überschreiben.
\* **Fehlerbehebung:** Das Modul wendet allgemeines Footer-Styling an. Wenn Ihr Theme spezifischere Regeln hat (z.B. für `ul li a` innerhalb des Footers), könnten diese Vorrang haben. Möglicherweise müssen Sie einen Webmaster konsultieren, um benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um bestimmte Elemente zu überschreiben, oder die Einstellungen Ihres Themes anpassen, wenn es einen dedizierten Footer-Anpassungsbereich hat.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul Advanced Footer ist ein Standard-PrestaShop-Modul, das sich hauptsächlich auf das Front-Office-Styling konzentriert. Es nutzt das PrestaShop-Konfigurationssystem (`Configuration::updateValue`), um seine Einstellungen zu speichern, und bindet sich in `displayFooter` ein, um sein benutzerdefiniertes CSS und JavaScript zu injizieren. Es führt keine neuen Datenbanktabellen oder komplexen ObjectModels ein, wodurch es leichtgewichtig und auf seine Kernaufgabe fokussiert ist: die Footer-Anpassung. Das Modul verwendet eine `getContent()`-Methode für seine Back-Office-Konfiguration, die ein Standard-PrestaShop-Formular rendert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul bindet sich direkt in `displayFooter` und `footer` ein, um seinen Inhalt zu rendern und Stile anzuwenden.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/` definiert. Die gesamte Logik ist in der Hauptmoduldatei `advfooter.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `advfooter/js/advajax.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Behandelt wahrscheinlich AJAX-Anfragen im Zusammenhang mit dem Speichern von Modulkonfigurationseinstellungen ohne vollständiges Neuladen der Seite oder bietet dynamisches Feedback innerhalb des Konfigurationsformulars.
- `advfooter/js/foscript.js`:
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript würde jegliche clientseitige Logik oder dynamisches Verhalten enthalten, das spezifisch für den erweiterten Footer auf der kundenorientierten Seite ist. Dies könnte responsive Anpassungen, spezifische Hover-Effekte, die nicht von CSS behandelt werden, oder Interaktionen mit eingebetteten Inhalten umfassen.
- `advfooter/js/jscolor/jscolor.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters, die ein Farbwähler-Widget im Back Office bereitstellt. Sie wird verwendet, um Händlern die visuelle Auswahl von Farben für Hintergrund, Text und Hover-Effekte zu ermöglichen.
- `advfooter/js/script.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Allzweckskript für die Back-Office-Konfigurationsseite des Moduls. Es könnte den `jscolor`-Wähler initialisieren, die Formularvalidierung oder andere UI-Verbesserungen für die Admin-Oberfläche behandeln.

### 4.5 CSS-Stylesheets (`views/css/`)

- `advfooter/css/fancybox.css`:
  - **Umfang:** Front-Office (potenziell, wenn das Modul Fancybox für eingebettete Inhalte oder Bilder verwendet).
  - **Verantwortlichkeit:** Bietet Styling für die Fancybox-Lightbox-Bibliothek, die häufig zum Anzeigen von Bildern, Videos oder anderen Inhalten in einem modalen Overlay verwendet wird. Ihre Präsenz deutet darauf hin, dass das Modul solche Funktionen unterstützen könnte, oder sie ist als allgemeines Dienstprogramm enthalten.
  - **Wichtige CSS-Klassenselektoren:** `.fancybox-overlay`, `.fancybox-wrap`, `.fancybox-inner`, etc. Entwickler können diese überschreiben, um das Erscheinungsbild der Lightbox anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `advfooter/footer.tpl`:
    - **Hook:** `displayFooter` (und potenziell `footer` für ältere Themes).
    - **Ausgabe:** Dieses Template ist für das Rendern der Hauptstruktur des erweiterten Footers verantwortlich. Es wird wahrscheinlich ein `div`- oder `footer`-HTML-Element mit dynamischen Inline-Stilen oder Klassenattributen enthalten, die durch die Konfigurationseinstellungen des Moduls (z.B. `width`, `height`, `background-color`, `background-image`, `color`) gefüllt werden. Es fungiert als Container für alle Inhalte, die andere Module oder das Theme in den `displayFooter`-Hook platzieren.
- **Admin-Templates (`views/templates/admin/`)**: Keine. Das Konfigurationsformular wird wahrscheinlich direkt innerhalb von `getContent()` mit PrestaShops `HelperForm` oder ähnlichem gerendert.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter den Schlüsseln: `ADVF_F_WIDTH`, `ADVF_F_HEIGHT`, `ADVF_F_BG`, `ADVF_F_COLOR`, `ADVF_F_COLOR_HOVER`, `ADVF_F_BG_URL`, `ADVF_F_BG_POS`, `ADVF_F_BG_REPEAT` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Wird verwendet, um CSS- und JavaScript-Assets (`foscript.js`, `fancybox.css`) für das Front-Office zu registrieren und potenziell Inline-Stile basierend auf der Modulkonfiguration einzufügen. |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich jeder Back-Office-Seite ausgeführt. | Wird verwendet, um CSS- und JavaScript-Assets (`advajax.js`, `jscolor.js`, `script.js`) für die Konfigurationsseite des Moduls zu registrieren. |
| `displayFooter` | Wird am unteren Rand der Seite ausgeführt, typischerweise vor dem schließenden `</body>`-Tag. | Rendert das `footer.tpl`-Template, das das benutzerdefinierte Styling anwendet und als Container für den Footer-Inhalt dient. |
| `footer` | (PrestaShop 1.6 und älter, oder für spezifische Theme-Kompatibilität) | Ähnlich wie `displayFooter`, wird zum Rendern von Footer-Inhalten verwendet. Das Modul registriert sich wahrscheinlich für beide, um eine breitere Kompatibilität zu gewährleisten. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Dort finden Sie Ihre gekauften Module und direkten Zugang zu Support-Ressourcen.
