---
title: "Nach unten scrollen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Nach unten scrollen“ von MyPresta.eu."
sidebar:
  label: "Nach unten scrollen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Scroll to bottom auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/scroll-to-bottom.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/scroll-to-bottom/)
>
> ---


# Nach unten scrollen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Nach unten scrollen“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Nach unten scrollen“ suchen und dann auf die Schaltfläche „Konfigurieren“ klicken.

#### Einstellungen & Optionen

- **Farbe des Buttons (st\_color)**

  - **Was diese Einstellung bewirkt:** Hiermit können Sie die Farbe des „Nach unten scrollen“-Buttons definieren. Sie können standardmäßige HTML-Farbnamen (wie `red`, `blue`, `green`) oder hexadezimale Farbcodes (wie `#FF0000` für Rot, `#0000FF` für Blau) verwenden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z.B. `#007bff`):* Der Button wird in dieser exakten Farbe in Ihrem Front Office angezeigt.
    - *Wenn leer oder ungültig gelassen:* Der Button wird wahrscheinlich auf eine Standardfarbe zurückgesetzt, die durch das CSS des Moduls definiert ist, was möglicherweise nicht zu Ihrer Marke passt.
  - **Empfohlener Wert:** Wählen Sie eine Farbe, die zum Design Ihres Shops passt und vor Ihrem Hintergrund gut sichtbar, aber nicht übermäßig ablenkend ist. Verwenden Sie die Primär- oder Sekundärfarbe Ihrer Marke.
  - **Händlerszenario / Beispiel:** Wenn Ihre Marke viel Dunkelblau verwendet, würde die Einstellung auf `#000080` (Marineblau) den Button gut integrieren und gleichzeitig funktional bleiben lassen.
- **X-Position des Buttons (st\_x)**

  - **Was diese Einstellung bewirkt:** Dies steuert die horizontale Position des Buttons auf dem Bildschirm. Es bestimmt, wie weit vom rechten Rand des Browserfensters der Button angezeigt wird. Der Wert wird typischerweise in Pixeln angegeben.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf einen niedrigeren Wert eingestellt (z.B. `20`):* Der Button ist näher am rechten Bildschirmrand.
    - *Wenn auf einen höheren Wert eingestellt (z.B. `80`):* Der Button ist weiter vom rechten Rand entfernt und bewegt sich zur Bildschirmmitte.
  - **Empfohlener Wert:** `20` oder `30` Pixel ist eine übliche und unaufdringliche Platzierung. Dies hält ihn außerhalb des Hauptinhaltsbereichs, aber dennoch leicht zugänglich.
  - **Händlerszenario / Beispiel:** Wenn Sie andere feste Elemente auf der rechten Seite Ihres Bildschirms haben (wie ein Chat-Widget), müssen Sie diesen Wert möglicherweise auf `50px` erhöhen, um zu verhindern, dass der „Nach unten scrollen“-Button überlappt.
- **Y-Position des Buttons (st\_y)**

  - **Was diese Einstellung bewirkt:** Dies steuert die vertikale Position des Buttons auf dem Bildschirm. Es bestimmt, wie weit vom oberen Rand des Browserfensters der Button angezeigt wird. Der Wert wird typischerweise in Pixeln angegeben.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf einen niedrigeren Wert eingestellt (z.B. `20`):* Der Button ist näher am oberen Bildschirmrand.
    - *Wenn auf einen höheren Wert eingestellt (z.B. `80`):* Der Button ist weiter unten vom oberen Rand.
  - **Empfohlener Wert:** `20` oder `30` Pixel ist ein guter Ausgangspunkt. Dies platziert ihn in der oberen rechten Ecke, ohne zu hoch oder zu niedrig zu sein.
  - **Händlerszenario / Beispiel:** Wenn der Header Ihres Shops sehr hoch ist oder Sie auch einen „Nach oben scrollen“-Button in der oberen rechten Ecke haben, könnten Sie diesen auf `60px` oder `70px` anpassen, um sicherzustellen, dass beide Buttons genügend Platz haben und sich nicht überlappen.
- **Deckkraft des Buttons (st\_o)**

  - **Was diese Einstellung bewirkt:** Dies steuert die Transparenz des Buttons. Deckkraftwerte reichen von `0` (vollständig transparent/unsichtbar) bis `1` (vollständig undurchsichtig/massiv). Sie können Dezimalwerte wie `0.5` für 50 % Transparenz verwenden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf `1` eingestellt:* Der Button ist vollständig sichtbar und massiv.
    - *Wenn auf `0.5` eingestellt:* Der Button ist halbtransparent, sodass Hintergrundinhalte durchscheinen.
    - *Wenn auf `0` eingestellt:* Der Button ist unsichtbar (aber immer noch anklickbar, wenn Sie wissen, wo er ist).
  - **Empfohlener Wert:** `0.8` oder `0.9` ist oft eine gute Balance. Es macht den Button etwas weniger aufdringlich, während er immer noch deutlich sichtbar ist. `1` ist auch völlig in Ordnung, wenn Sie möchten, dass er stärker hervorsticht.
  - **Händlerszenario / Beispiel:** Wenn Sie den Button als zu prominent oder ablenkend empfinden, kann eine Reduzierung seiner Deckkraft auf `0.7` ihn subtiler in das Design Ihres Shops integrieren, ohne seine Funktionalität zu verlieren.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Farbe des Buttons (st\_color) | `#007bff` (Beispiel) | Legt die Farbe des Buttons fest. Beeinflusst Sichtbarkeit und Markenkonsistenz. |
| Modulkonfiguration | X-Position des Buttons (st\_x) | `20` | Horizontaler Abstand vom rechten Rand. Verhindert Überlappungen mit anderen Elementen. |
| Modulkonfiguration | Y-Position des Buttons (st\_y) | `20` | Vertikaler Abstand vom oberen Rand. Positioniert den Button klar. |
| Modulkonfiguration | Deckkraft des Buttons (st\_o) | `0.8` | Transparenz des Buttons. Steuert, wie aufdringlich oder subtil er erscheint. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

- **F: Der Button wird in meinem Shop nicht angezeigt.**
  - **A:** Stellen Sie zunächst sicher, dass das Modul unter **Module > Modul-Manager** installiert und aktiviert ist. Überprüfen Sie dann die Konfigurationsseite des Moduls, um sicherzustellen, dass alle Einstellungen gespeichert sind. Wenn es immer noch nicht angezeigt wird, versuchen Sie, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung > Cache leeren**). Manchmal können auch benutzerdefinierte Themes stören; wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um dies auszuschließen.
- **F: Der Button wird angezeigt, aber er ist an der falschen Stelle oder sieht seltsam aus.**
  - **A:** Gehen Sie zur Konfigurationsseite des Moduls. Passen Sie die Einstellungen „X-Position“ und „Y-Position“ an, um den Button horizontal und vertikal zu verschieben. Experimentieren Sie mit verschiedenen Werten, bis er sich an einer zufriedenstellenden Position befindet. Bei Darstellungsproblemen überprüfen Sie die Einstellungen „Farbe“ und „Deckkraft“. Wenn es immer noch nicht stimmt, könnte das CSS Ihres Themes die Stile des Moduls überschreiben.
- **F: Die Scroll-Animation ist nicht flüssig oder funktioniert nicht.**
  - **A:** Dieses Modul verwendet JavaScript für den sanften Scrolleffekt. Stellen Sie sicher, dass es keine JavaScript-Fehler auf Ihrer Website gibt (Sie können die Entwicklerkonsole Ihres Browsers auf Fehler überprüfen). Konflikte mit anderen Modulen oder benutzerdefiniertem Theme-JavaScript können manchmal verhindern, dass die Animation korrekt funktioniert. Das Leeren des Caches ist ein guter erster Schritt.
- **F: Kann ich das Icon des Buttons ändern?**
  - **A:** Die aktuelle Version des Moduls bietet keine direkte Einstellung, um das Icon über das Back Office zu ändern. Dies würde benutzerdefiniertes CSS oder Template-Modifikationen erfordern (siehe Entwicklerhandbuch für weitere technische Details).
- **F: Beeinflusst dieses Modul die Leistung oder SEO meines Shops?**
  - **A:** Dieses Modul ist sehr leichtgewichtig und fügt nur minimale CSS- und JavaScript-Dateien hinzu. Es sollte einen vernachlässigbaren Einfluss auf die Ladezeit oder SEO Ihres Shops haben. Die Funktionalität dient ausschließlich der Benutzerfreundlichkeit und ändert den Inhalt nicht auf eine Weise, die die Suchmaschinenindizierung beeinflussen würde.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Nach unten scrollen“ ist eine unkomplizierte Front-Office-Funktion, die als Standard-PrestaShop-Modul implementiert ist. Es nutzt hauptsächlich das Hook-System von PrestaShop, um sein CSS, JavaScript und die HTML-Struktur des Buttons in das Front Office einzufügen. Die Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, wobei die Einstellungen in `ps_configuration` gespeichert werden. Es gibt keine benutzerdefinierten Controller, ObjectModels oder komplexe Datenbankinteraktionen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Funktionalität des Moduls wird direkt über Hooks eingefügt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird innerhalb der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten Klassen oder ObjectModels. Die gesamte Logik ist in `scrollbottom.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `scrollbottom/scrollbottom.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript ist für die Kernfunktionalität des „Nach unten scrollen“-Buttons verantwortlich.
    - Es wartet wahrscheinlich darauf, dass das DOM bereit ist.
    - Es fügt einen Klick-Event-Listener an das Button-Element „Nach unten scrollen“ an.
    - Beim Klicken verwendet es die JavaScript-Methode `window.scrollTo()` oder `element.scrollIntoView()`, oft mit `behavior: 'smooth'`, um das Scrollen zum unteren Ende der Seite (insbesondere zur maximalen Scrollhöhe des `body`- oder `html`-Elements) zu animieren.
    - Es könnte auch die Sichtbarkeit des Buttons steuern, indem es ihn basierend auf der Scrollposition des Benutzers erscheinen oder verschwinden lässt (z.B. nur anzeigen, wenn der Benutzer eine bestimmte Menge nach unten gescrollt hat).

### 4.5 CSS-Stylesheets (`views/css/`)

- `scrollbottom/scrollbottom.css`
  - **Geltungsbereich:** Front-Office-Kundenstyling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet definiert das visuelle Erscheinungsbild und die Positionierung des „Nach unten scrollen“-Buttons.
    - Es wird wahrscheinlich eine bestimmte ID oder Klasse für den Button ansprechen (z.B. `#scrollbottom_button`).
    - Es definiert Eigenschaften wie `position: fixed`, `right`, `top`, `z-index`, `background-color`, `color`, `padding`, `border-radius`, `cursor` und möglicherweise anfänglich `display: none`, wobei JavaScript seine Sichtbarkeit steuert.
    - Es kann auch Stile für das Pfeilsymbol innerhalb des Buttons enthalten (z.B. unter Verwendung eines Schriftart-Icons oder eines Hintergrundbilds).
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** Entwickler können das generierte HTML überprüfen, um die genaue ID/Klasse des Buttons (z.B. `#scrollbottom_button`) zu finden und dessen Stile in der `custom.css` oder einer entsprechenden Datei ihres Themes zu überschreiben, um ein benutzerdefiniertes Aussehen zu erzielen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `scrollbottom/adv.tpl`: Dieses Template wird wahrscheinlich zur Anzeige einer Werbung oder von Werbeinhalten im Zusammenhang mit MyPresta.eu verwendet, oft in einen Hook wie `displayAdminHome` oder ähnliches eingefügt, aber nicht direkt mit der Front-Office-Button-Funktionalität verbunden.
  - `scrollbottom/footer.tpl`: Dies ist das primäre Template für den Front-Office-Button.
    - **Eingehängt in:** `displayFooter` oder `footer` (abhängig von PrestaShop-Version und Theme).
    - **Ausgabe:** Die HTML-Struktur für den „Nach unten scrollen“-Button, einschließlich seiner ID/Klasse, des Pfeilsymbols und potenziell Inline-Stile oder Datenattribute, die von den Konfigurationseinstellungen des Moduls (Farbe, Position, Deckkraft) abgeleitet sind.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln wie `ST_COLOR`, `ST_X`, `ST_Y`, `ST_O` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich des Front Office. | Wird verwendet, um die CSS- (`scrollbottom.css`) und JavaScript-Dateien (`scrollbottom.js`) des Moduls zu registrieren und einzubinden, um sicherzustellen, dass sie vor dem Seiteninhalt geladen werden. |
| `header` | Alias für `displayHeader` in einigen Kontexten. | Gleiches wie `displayHeader`. |
| `displayFooter` | Am Ende des `<body>`-Bereichs, vor dem schließenden `</body>`-Tag. | Wird verwendet, um das `footer.tpl`-Template zu rendern, das die HTML-Struktur für den „Nach unten scrollen“-Button enthält. |
| `footer` | Alias für `displayFooter` in einigen Kontexten. | Gleiches wie `displayFooter`. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um auf die neuesten Versionen des Moduls „Nach unten scrollen“ zuzugreifen, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
