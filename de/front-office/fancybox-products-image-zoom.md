---
title: "Fancybox products image zoom - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Fancybox products image zoom von MyPresta.eu."
sidebar:
  label: "Fancybox products image zoom - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Fancybox products image zoom auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/fancybox-products-image-zoom.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/fancybox-products-image-zoom/)
>
> ---


# Fancybox products image zoom

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Fancybox products image zoom“. Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren, nach „Fancybox products image zoom“ suchen und auf „Konfigurieren“ klicken.

#### Theme-Unterstützung & Selektor-Einstellungen

Diese Einstellungen helfen dem Modul, die richtigen Elemente auf Ihrer Produktseite zu identifizieren, um den Fancybox-Zoom anzuwenden, was besonders wichtig für benutzerdefinierte Themes ist.

- **Theme-Unterstützung**

  - **Was diese Einstellung bewirkt:** Dies ist eine entscheidende Einstellung, die dem Modul mitteilt, welche Theme-Struktur es erwarten soll. Sie hilft dem Modul, das Hauptproduktbild und seine Miniaturansichten auf Ihren Produktseiten korrekt zu identifizieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Classic“ eingestellt:* Das Modul verwendet vordefinierte Selektoren, die perfekt mit dem Standard-„Classic“-Theme von PrestaShop funktionieren. Dies ist die häufigste und empfohlene Einstellung, wenn Sie das Classic-Theme oder ein sehr eng darauf basierendes Theme verwenden.
    - *Wenn auf „Hummingbird“ eingestellt:* Das Modul verwendet vordefinierte Selektoren für das „Hummingbird“-Theme, das das Standard-Theme für PrestaShop 8.1 und neuere Versionen ist.
    - *Wenn auf „Custom“ eingestellt:* Diese Option ermöglicht es Ihnen, die CSS-Selektoren für Ihr Hauptproduktbild und Ihre Miniaturansichten manuell anzugeben. Dies ist unerlässlich, wenn Sie ein stark angepasstes Theme oder ein Drittanbieter-Theme verwenden, das nicht der „Classic“- oder „Hummingbird“-Struktur folgt.
  - **Empfohlener Wert:** „Classic“, wenn Sie PrestaShop 1.7.x bis 8.0.x mit dem Classic-Theme verwenden. „Hummingbird“, wenn Sie PrestaShop 8.1+ mit dem Hummingbird-Theme verwenden. „Custom“, wenn Sie ein einzigartiges Theme haben.
  - **Händlerszenario / Beispiel:** Wenn Ihre Produktbilder nach der Installation nicht korrekt zoomen und Sie ein benutzerdefiniertes Theme verwenden, ist das Umschalten auf „Custom“ und die anschließende Anpassung der Selektoren der nächste Schritt.
- **Erkanntes Theme-Profil**

  - **Was diese Einstellung bewirkt:** Dieses Feld zeigt das Theme-Profil an, das das Modul basierend auf Ihrer Auswahl unter „Theme-Unterstützung“ automatisch erkannt hat. Es ist ein Informationsfeld, das nicht direkt konfigurierbar ist.
  - **Auswirkung der Änderung dieser Einstellung:** Keine direkte Auswirkung, da es sich um ein reines Anzeigefeld handelt. Es bestätigt lediglich, welche Selektoren das Modul derzeit verwendet.
  - **Empfohlener Wert:** N/A (informatorisch).
  - **Händlerszenario / Beispiel:** Sie haben „Theme-Unterstützung“ auf „Classic“ eingestellt, und dieses Feld bestätigt, dass „Classic“ erkannt wurde.
- **Hummingbird Cover-Selektor** (Nur sichtbar, wenn „Theme-Unterstützung“ auf „Hummingbird“ eingestellt ist)

  - **Was diese Einstellung bewirkt:** Gibt den CSS-Selektor für den Hauptprodukt-Cover-Bildcontainer an, wenn das Hummingbird-Theme verwendet wird. Dies hilft dem Modul, den richtigen Bereich für den Zoom anzusprechen.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn falsch, wird der Fancybox-Zoom möglicherweise nicht auf dem Hauptproduktbild aktiviert oder zielt auf das falsche Element ab.
  - **Empfohlener Wert:** Als Standard belassen, es sei denn, Ihr Hummingbird-basiertes Theme hat seine Struktur erheblich geändert.
  - **Händlerszenario / Beispiel:** Ihr Hummingbird-Theme hat eine einzigartige Struktur für das Hauptbild. Möglicherweise müssen Sie den Code Ihres Themes überprüfen, um die richtige CSS-Klasse oder ID für den Hauptbildcontainer zu finden und hier einzugeben.
- **Hummingbird Bild-Selektor** (Nur sichtbar, wenn „Theme-Unterstützung“ auf „Hummingbird“ eingestellt ist)

  - **Was diese Einstellung bewirkt:** Gibt den CSS-Selektor für das eigentliche `<img>`-Tag des Hauptprodukt-Cover-Bildes innerhalb des Hummingbird-Themes an.
  - **Auswirkung der Änderung dieser Einstellung:** Ähnlich wie beim Cover-Selektor verhindert ein falscher Wert, dass der Zoom auf dem Hauptbild funktioniert.
  - **Empfohlener Wert:** Als Standard belassen.
  - **Händlerszenario / Beispiel:** Wenn der Zoom auf dem Hauptbild nicht funktioniert und Sie Hummingbird verwenden, überprüfen Sie diesen Selektor.
- **Hummingbird Miniaturansichten-Selektor** (Nur sichtbar, wenn „Theme-Unterstützung“ auf „Hummingbird“ eingestellt ist)

  - **Was diese Einstellung bewirkt:** Gibt den CSS-Selektor für den Container der Produkt-Miniaturansichten an, wenn das Hummingbird-Theme verwendet wird. Dies ist wichtig, um eine Galerie aus Ihren Miniaturansichten zu erstellen.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn falsch, kann das Modul möglicherweise keine Fancybox-Galerie aus Ihren Miniaturansichten erstellen, oder das Klicken auf Miniaturansichten öffnet die Fancybox möglicherweise nicht.
  - **Empfohlener Wert:** Als Standard belassen.
  - **Händlerszenario / Beispiel:** Wenn das Klicken auf Miniaturansichten die Fancybox-Galerie nicht öffnet, überprüfen Sie diesen Selektor.
- **Haupt-Cover-Bild-Selektor** (Nur sichtbar, wenn „Theme-Unterstützung“ auf „Custom“ eingestellt ist)

  - **Was diese Einstellung bewirkt:** Wenn „Custom“-Theme-Unterstützung ausgewählt ist, können Sie in diesem Feld den CSS-Selektor für das Containerelement manuell eingeben, das Ihr Hauptproduktbild auf der Produktseite enthält.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn dieser Selektor falsch ist, wird der Fancybox-Zoom nicht auf Ihrem Hauptproduktbild aktiviert.
  - **Empfohlener Wert:** Sie müssen die Entwicklertools Ihres Browsers (F12) verwenden, um Ihre Produktseite zu überprüfen und die eindeutige CSS-Klasse oder ID des `<div>` oder eines anderen Containerelements zu finden, das Ihr Hauptproduktbild umschließt.
  - **Händlerszenario / Beispiel:** Ihr benutzerdefiniertes Theme verwendet `<div id="my-custom-main-image-wrapper">` für das Hauptbild. Sie würden hier `#my-custom-main-image-wrapper` eingeben.
- **Haupt-Cover-Bild** (Nur sichtbar, wenn „Theme-Unterstützung“ auf „Custom“ eingestellt ist)

  - **Was diese Einstellung bewirkt:** Wenn „Custom“-Theme-Unterstützung ausgewählt ist, können Sie in diesem Feld den CSS-Selektor für das eigentliche `<img>`-Tag Ihres Hauptproduktbildes manuell eingeben.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn dieser Selektor falsch ist, wird der Fancybox-Zoom nicht auf Ihrem Hauptproduktbild aktiviert.
  - **Empfohlener Wert:** Verwenden Sie die Entwicklertools Ihres Browsers, um die eindeutige CSS-Klasse oder ID des `<img>`-Tags selbst zu finden.
  - **Händlerszenario / Beispiel:** Ihr benutzerdefiniertes Theme verwendet `<img class="product-main-image-src">` für das Hauptbild. Sie würden hier `.product-main-image-src` eingeben.
- **Miniaturansichten-Selektor** (Nur sichtbar, wenn „Theme-Unterstützung“ auf „Custom“ eingestellt ist)

  - **Was diese Einstellung bewirkt:** Wenn „Custom“-Theme-Unterstützung ausgewählt ist, können Sie in diesem Feld den CSS-Selektor für das Containerelement manuell eingeben, das Ihre Produkt-Miniaturansichten enthält.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn dieser Selektor falsch ist, kann das Modul keine Fancybox-Galerie aus Ihren Miniaturansichten erstellen, oder das Klicken auf Miniaturansichten öffnet die Fancybox möglicherweise nicht.
  - **Empfohlener Wert:** Verwenden Sie die Entwicklertools Ihres Browsers, um die eindeutige CSS-Klasse oder ID des `<div>` oder eines anderen Containerelements zu finden, das Ihre Produkt-Miniaturansichten umschließt.
  - **Händlerszenario / Beispiel:** Ihr benutzerdefiniertes Theme verwendet `<ul id="product-thumbnails-list">` für die Miniaturansichten. Sie würden hier `#product-thumbnails-list` eingeben.

#### Fancybox Verhaltens-Einstellungen

Diese Einstellungen steuern, wie der Fancybox-Zoom sich verhält und mit Ihren Kunden interagiert.

- **Galerie erstellen**

  - **Was diese Einstellung bewirkt:** Legt fest, ob alle Produktbilder (Hauptbild und Miniaturansichten) in einer einzigen Fancybox-Galerie gruppiert werden. Wenn aktiviert, öffnet ein Klick auf ein beliebiges Bild die Fancybox, und Kunden können dann mit Pfeilen durch alle Produktbilder navigieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Kunden können in einem Vollbild-Fancybox-Overlay mit Navigationspfeilen durch alle Produktbilder blättern. Dies bietet eine umfassende Ansicht des Produkts.
    - *Wenn deaktiviert („Aus“):* Ein Klick auf ein Bild öffnet nur dieses spezifische Bild in Fancybox. Kunden können innerhalb der Fancybox-Ansicht nicht zu anderen Produktbildern navigieren.
  - **Empfohlener Wert:** „An“ für ein besseres Benutzererlebnis und um Kunden zu ermutigen, alle Produktansichten zu betrachten.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden einfach durch alle Produktbilder blättern können, ohne den Zoom für jedes Bild schließen und wieder öffnen zu müssen. Aktivieren Sie dies.
- **Wischen**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert Wischgesten zum Navigieren in der Fancybox-Galerie auf Touch-fähigen Geräten (Smartphones, Tablets).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Kunden können auf ihren Touch-Geräten nach links oder rechts wischen, um zwischen den Bildern in der Fancybox-Galerie zu wechseln.
    - *Wenn deaktiviert („Aus“):* Wischgesten funktionieren nicht. Kunden müssen die Navigationspfeile verwenden (wenn „Galerie erstellen“ aktiviert ist).
  - **Empfohlener Wert:** „An“ für ein modernes, intuitives mobiles Erlebnis.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Ihre mobilen Benutzer eine nahtlose, natürliche Möglichkeit haben, Produktbilder zu durchsuchen. Lassen Sie dies aktiviert.
- **Doppeltes Cover-Bild in Galerie vermeiden**

  - **Was diese Einstellung bewirkt:** Wenn „Galerie erstellen“ aktiviert ist, kann das Hauptproduktbild manchmal zweimal in der Galerie erscheinen (einmal als Hauptbild und einmal, wenn es auch als Miniaturansicht aufgeführt ist). Diese Einstellung verhindert diese Duplizierung.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Das Modul versucht, ein doppeltes Hauptproduktbild in der Fancybox-Galerie zu erkennen und zu entfernen, um sicherzustellen, dass jedes Bild nur einmal erscheint.
    - *Wenn deaktiviert („Aus“):* Wenn das Hauptproduktbild auch Teil der Miniaturansichtenliste ist, kann es zweimal in der Fancybox-Galerie erscheinen.
  - **Empfohlener Wert:** „An“ für ein saubereres, professionelleres Galerieerlebnis.
  - **Händlerszenario / Beispiel:** Sie bemerken, dass, wenn Kunden die Fancybox-Galerie öffnen, das erste Bild identisch mit dem zweiten ist. Das Aktivieren dieser Option behebt dies.
- **Bildunterschriften anzeigen (Bildtitel)**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Titel/die Bildunterschrift, die jedem Produktbild zugeordnet ist, im Fancybox-Overlay angezeigt wird. Diese Titel werden normalerweise in Ihrer PrestaShop-Produktbildverwaltung festgelegt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Der Bildtitel wird als Bildunterschrift unter oder über dem Bild im Fancybox-Overlay angezeigt.
    - *Wenn deaktiviert („Aus“):* Es wird keine Bildunterschrift angezeigt, was eine sauberere, nur Bild-Ansicht bietet.
  - **Empfohlener Wert:** „An“, wenn Ihre Bildtitel nützliche Informationen liefern (z.B. „Vorderansicht“, „Detailaufnahme“, „Modell trägt Produkt“). „Aus“, wenn Ihre Bildtitel generisch sind oder Sie einen minimalistischen Look bevorzugen.
  - **Händlerszenario / Beispiel:** Sie verwenden beschreibende Titel für Ihre Produktbilder und möchten, dass Kunden diese beim Zoomen sehen. Aktivieren Sie dies.
- **Hauptbild bei Mauszeiger über Miniaturansicht wechseln**

  - **Was diese Einstellung bewirkt:** Legt fest, ob das Überfahren einer Produkt-Miniaturansicht mit der Maus das auf der Produktseite angezeigte Hauptproduktbild automatisch ändert, *bevor* auf Fancybox geklickt wird, um es zu öffnen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Das Bewegen des Mauszeigers über eine Miniaturansicht tauscht sofort das Hauptproduktbild aus, um die überfahrene Miniaturansicht anzuzeigen. Dies ist eine gängige und bequeme Funktion für Käufer.
    - *Wenn deaktiviert („Aus“):* Das Hauptproduktbild ändert sich nur, wenn auf eine Miniaturansicht geklickt wird, nicht nur beim Überfahren.
  - **Empfohlener Wert:** „An“ für ein interaktiveres und benutzerfreundlicheres Browsing-Erlebnis.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden verschiedene Produktbilder schnell in der Vorschau anzeigen können, indem sie einfach die Maus bewegen, ohne klicken zu müssen. Aktivieren Sie dies.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Theme-Unterstützung** | Classic / Hummingbird | Wählt vordefinierte CSS-Selektoren für Ihr Theme (Classic, Hummingbird oder Custom). Entscheidend für die Modulfunktionalität. |
| Modulkonfiguration | **Erkanntes Theme-Profil** | N/A (Informatorisch) | Zeigt an, welches Theme-Profil derzeit aktiv ist. |
| Modulkonfiguration | **Hummingbird Cover-Selektor** | Standard | CSS-Selektor für den Hauptbildcontainer (Hummingbird-Theme). |
| Modulkonfiguration | **Hummingbird Bild-Selektor** | Standard | CSS-Selektor für das Haupt-`<img>`-Tag (Hummingbird-Theme). |
| Modulkonfiguration | **Hummingbird Miniaturansichten-Selektor** | Standard | CSS-Selektor für den Miniaturansichten-Container (Hummingbird-Theme). |
| Modulkonfiguration | **Haupt-Cover-Bild-Selektor** | Custom (Theme prüfen) | CSS-Selektor für den Hauptbildcontainer (Custom-Theme). |
| Modulkonfiguration | **Haupt-Cover-Bild** | Custom (Theme prüfen) | CSS-Selektor für das Haupt-`<img>`-Tag (Custom-Theme). |
| Modulkonfiguration | **Miniaturansichten-Selektor** | Custom (Theme prüfen) | CSS-Selektor für den Miniaturansichten-Container (Custom-Theme). |
| Modulkonfiguration | **Galerie erstellen** | An | Gruppiert alle Produktbilder in einer durchsuchbaren Fancybox-Galerie. |
| Modulkonfiguration | **Wischen** | An | Aktiviert Wischgesten für die Galerienavigation auf Touch-Geräten. |
| Modulkonfiguration | **Doppeltes Cover-Bild in Galerie vermeiden** | An | Verhindert, dass das Hauptbild zweimal in der Galerie erscheint. |
| Modulkonfiguration | **Bildunterschriften anzeigen (Bildtitel)** | An / Aus (Händlerpräferenz) | Zeigt Bildtitel als Bildunterschriften im Fancybox-Overlay an. |
| Modulkonfiguration | **Hauptbild bei Mauszeiger über Miniaturansicht wechseln** | An | Ändert das Hauptproduktbild beim Überfahren einer Miniaturansicht. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Fancybox-Zoom erscheint überhaupt nicht auf meinen Produktseiten.**
A:

1. **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** installiert und aktiviert ist.
2. **Theme-Unterstützungseinstellung:** Gehen Sie zur Konfigurationsseite des Moduls. Wenn Sie das „Classic“-Theme verwenden, stellen Sie sicher, dass „Theme-Unterstützung“ auf „Classic“ eingestellt ist. Wenn Sie PrestaShop 8.1+ mit dem Hummingbird-Theme verwenden, stellen Sie es auf „Hummingbird“ ein. Wenn Sie ein benutzerdefiniertes Theme haben, stellen Sie es auf „Custom“ ein und überprüfen Sie sorgfältig die von Ihnen eingegebenen CSS-Selektoren (siehe nächster Punkt).
3. **Benutzerdefinierte Theme-Selektoren:** Wenn „Theme-Unterstützung“ auf „Custom“ eingestellt ist, ist das häufigste Problem die falschen CSS-Selektoren. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um Ihre Produktseite zu überprüfen. Finden Sie die genauen CSS-Klassen oder IDs für Ihren Hauptproduktbild-Container, das `<img>`-Tag und Ihren Miniaturansichten-Container. Aktualisieren Sie diese in den Moduleinstellungen.

**F: Die Fancybox öffnet sich, zeigt aber das falsche Bild oder nur ein Bild an.**
A:

1. **Einstellung „Galerie erstellen“:** Stellen Sie sicher, dass „Galerie erstellen“ in der Modulkonfiguration auf „An“ eingestellt ist, wenn Sie mehrere Bilder durchsuchen möchten.
2. **Miniaturansichten-Selektoren:** Wenn „Galerie erstellen“ aktiviert ist, aber nur ein Bild angezeigt wird, überprüfen Sie Ihren „Miniaturansichten-Selektor“ (insbesondere wenn „Theme-Unterstützung“ auf „Custom“ eingestellt ist). Das Modul muss alle Ihre Miniaturansichten korrekt identifizieren, um die Galerie zu erstellen.
3. **Bildtitel/Bildunterschriften:** Wenn Bildunterschriften nicht angezeigt werden, stellen Sie sicher, dass „Bildunterschriften anzeigen (Bildtitel)“ auf „An“ steht und dass Ihre Produktbilder tatsächlich Titel im PrestaShop Back Office definiert haben.

**F: Wischgesten funktionieren auf meinem Mobilgerät nicht.**
A:

1. **Einstellung „Wischen“:** Stellen Sie sicher, dass die Option „Wischen“ in der Modulkonfiguration auf „An“ steht.
2. **Galerie aktiviert:** Wischen funktioniert nur, wenn „Galerie erstellen“ ebenfalls auf „An“ steht, da es zum Navigieren zwischen mehreren Bildern dient.
3. **Browser-/Gerätekompatibilität:** Obwohl weit verbreitet, können sehr alte Browser oder spezifische Gerätekonfigurationen Probleme verursachen. Testen Sie mit einem modernen mobilen Browser.

**F: Mein Produktseiten-Layout sieht nach der Installation des Moduls etwas seltsam aus.**
A:

1. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal können alte Cache-Dateien die neue Modul-Formatierung stören.
2. **Theme-Konflikte:** Obwohl das Modul versucht, kompatibel zu sein, können sehr spezifische benutzerdefinierte Theme-CSS-Regeln Konflikte verursachen. Wenn das Leeren des Caches nicht hilft, deaktivieren Sie das Modul vorübergehend, um zu sehen, ob das Problem verschwindet. Wenn ja, benötigen Sie möglicherweise einen Webentwickler, um das CSS Ihres Themes oder die benutzerdefinierten Selektoren des Moduls anzupassen.

**F: Wie finde ich die richtigen CSS-Selektoren für mein benutzerdefiniertes Theme?**
A:

1. Öffnen Sie Ihre Produktseite in einem Webbrowser (Chrome, Firefox, Edge).
2. Klicken Sie mit der rechten Maustaste auf Ihr Hauptproduktbild und wählen Sie „Untersuchen“ oder „Element untersuchen“.
3. Dies öffnet die Entwicklertools des Browsers. Suchen Sie nach dem `<img>`-Tag Ihres Hauptbildes und seinem übergeordneten `<div>` oder einem anderen Container. Notieren Sie sich alle eindeutigen `id`-Attribute (z.B. `id="my-image"`) oder `class`-Attribute (z.B. `class="product-image-wrapper"`).
4. Wiederholen Sie dies für Ihre Produkt-Miniaturansichten.
5. Verwenden Sie diese IDs (mit `#` präfixiert, z.B. `#my-image`) oder Klassen (mit `.` präfixiert, z.B. `.product-image-wrapper`) in den „Custom“-Theme-Einstellungen des Moduls. Möglicherweise müssen Sie ein wenig experimentieren, um die spezifischsten und zuverlässigsten Selektoren zu finden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `fancyzoom` ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, die Standard-Produktbildzoom-Funktionalität durch Fancybox zu ersetzen. Es erreicht dies, indem es sich in `displayHeader` einklinkt, um sein benutzerdefiniertes JavaScript und CSS zu injizieren, und indem es JavaScript verwendet, um Bildelemente zu identifizieren und mit Fancybox neu zu initialisieren. Die Konfiguration des Moduls wird über die Standardmethode `getContent()` in der Hauptmoduldatei gehandhabt, wobei die Einstellungen in `ps_configuration` gespeichert werden. Es führt keine benutzerdefinierten Datenbanktabellen, `ObjectModel`-Klassen oder dedizierte Front-/Admin-Controller über die Hauptmodulkonfiguration hinaus ein.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Alle Front-Office-Funktionalitäten werden über Hooks injiziert und von JavaScript verarbeitet.
- **Back-Office-Admin-Controller**: Keine. Alle Back-Office-Konfigurationen werden von der Methode `getContent()` der Hauptmodulklasse verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Die gesamte Kernlogik befindet sich in der Hauptmoduldatei `fancyzoom.php`.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält zwei JavaScript-Dateien, hauptsächlich für die Front-Office-Funktionalität. Sie werden über den `displayHeader`-Hook registriert.

- `fancyzoom/views/templates/js/fancyzoom.js`

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dies ist das Kernskript, das Fancybox initialisiert. Es identifiziert dynamisch das Hauptproduktbild und die Miniaturansichten basierend auf den konfigurierten CSS-Selektoren (oder den Standard-Classic/Hummingbird-Selektoren). Anschließend bindet es Klickereignisse an diese Bilder, um sie in einer Fancybox-Galerie zu öffnen. Es handhabt auch die Funktionalität „Hauptbild bei Mauszeiger über Miniaturansicht wechseln“. Es ist dafür verantwortlich, den Standard-PrestaShop-Zoom zu deaktivieren.
  - **Schlüsselfunktionalitäten:**
    - Deaktiviert den Standard-PrestaShop-Bildzoom.
    - Erkennt das Theme-Profil (Classic, Hummingbird, Custom) und wendet entsprechende Selektoren an.
    - Initialisiert Fancybox auf Produktbildern.
    - Verwaltet die Erstellung und Optionen der Fancybox-Galerie (Wischen, Bildunterschriften, doppelte Bilder).
    - Handhabt den Miniaturansichten-Hover-Effekt, um das Hauptbild zu ändern.
    - Lauscht auf das `updateProduct`-Ereignis (PrestaShop 1.7+ Produktseiten-Updates), um Fancybox neu zu initialisieren.
- `fancyzoom/views/templates/js/touchswipe.js`

  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dies ist eine Drittanbieterbibliothek, die eine robuste Erkennung von Touch-Wischereignissen bietet. Sie wird von `fancyzoom.js` verwendet, um die Wisch-Navigation innerhalb der Fancybox-Galerie auf Touch-Geräten zu ermöglichen.
  - **Schlüsselfunktionalitäten:** Bietet ein jQuery-Plugin zur Erkennung von Wischgesten (links, rechts, oben, unten) und anderen Touch-Ereignissen.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält eine CSS-Datei für das Front-Office-Styling.

- `fancyzoom/views/templates/css/fancyzoom.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Verantwortlichkeit:** Enthält das notwendige CSS für das Fancybox-Overlay selbst, einschließlich Styling für die Navigationspfeile, den Schließen-Button, Bildunterschriften und das allgemeine Erscheinungsbild. Es stellt sicher, dass das Fancybox-Modal richtig positioniert und gestylt ist.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**
    - `.fancybox-container`: Hauptcontainer für das Fancybox-Overlay.
    - `.fancybox-bg`: Hintergrund-Overlay.
    - `.fancybox-toolbar`: Symbolleiste mit Schließen-Button usw.
    - `.fancybox-caption`: Bildunterschriftenbereich.
    - `.fancybox-button`: Buttons (Schließen, Navigation).
    - `.fancybox-image`: Das Bild selbst innerhalb von Fancybox.
      Entwickler können diese Klassen in der `custom.css` ihres Themes oder einer ähnlichen Datei überschreiben, um sie an das Branding ihres Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `fancyzoom/views/templates/hook/fancyzoom.tpl`
    - **Hook:** `displayHeader`
    - **Zweck:** Dieses Template ist dafür verantwortlich, die notwendigen JavaScript-Variablen sowie die JS- und CSS-Dateien des Moduls in den `<head>`-Bereich des Front-Office zu injizieren. Es übergibt Konfigurationsvariablen aus dem Back Office (wie Selektoren, Galerieoptionen) an das `fancyzoom.js`-Skript.
- **Admin-Templates (`views/templates/admin/`)**:

  - `fancyzoom/views/templates/admin/admin.tpl`
    - **Zweck:** Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es zeigt alle in Abschnitt 4.1 beschriebenen Einstellungen an, einschließlich Eingabefeldern für Selektoren, Checkboxen für Galerieoptionen und die Theme-Profilerkennung.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die mit `FZ_` beginnen (z.B. `FZ_THEME`, `FZ_COVER_DIV`, `FZ_GALLERY`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Injiziert die CSS- und JavaScript-Dateien des Moduls und übergibt Konfigurationsvariablen an die Front-End-Skripte. Hier werden die Fancybox-Bibliothek und ihre Initialisierungslogik geladen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Fancybox products image zoom“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
