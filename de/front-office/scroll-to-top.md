---
title: "Scroll to top – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Scroll to top“ von MyPresta.eu."
sidebar:
  label: "Scroll to top – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Scroll to top auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/scroll-to-top.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/scroll-to-top/)
>
> ---


# Scroll to top

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständiger Konfigurationsdurchgang (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls navigieren Sie zu **Module > Modul-Manager** und klicken Sie neben „Scroll to top“ auf „Konfigurieren“. Auf dieser Seite können Sie das Erscheinungsbild und die Positionierung des Scroll-to-top-Buttons anpassen.

#### **Visuelle Positionierung**

- **Was diese Einstellung bewirkt:** Dies ist eine visuelle Darstellung, wo der Button in Ihrem Shop erscheinen wird. Es ist keine direkte Einstellung, sondern eine visuelle Hilfe, die sich basierend auf Ihren Einstellungen für „Position X“ und „Position Y“ ändert.
- **Auswirkung der Änderung dieser Einstellung:** Wenn Sie „Position X“ und „Position Y“ anpassen, bewegt sich die Vorschau des Buttons auf dieser Konfigurationsseite, was Ihnen hilft, seine endgültige Position im Front Office zu visualisieren.
- **Empfohlener Wert:** Dies ist dynamisch.
- **Händlerszenario / Beispiel:** Wenn Sie möchten, dass der Button näher an der unteren rechten Ecke ist, sehen Sie, wie sich die Vorschau dorthin bewegt, während Sie die X- und Y-Werte anpassen.

#### **Farbschema**

- **Was diese Einstellung bewirkt:** Dies steuert die Hintergrundfarbe des Scroll-to-top-Buttons.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine bestimmte Farbe eingestellt (z. B. #007bff für Blau):* Der Button wird mit dieser Hintergrundfarbe in Ihrem Front Office angezeigt.
  - *Wenn auf eine andere Farbe eingestellt:* Der Hintergrund des Buttons ändert sich entsprechend.
- **Empfohlener Wert:** Wählen Sie eine Farbe, die zum Branding Ihres Shops passt und vor dem Hintergrund Ihrer Website deutlich sichtbar, aber nicht zu ablenkend ist.
- **Händlerszenario / Beispiel:** Wenn Ihre Markenfarben Blau und Weiß sind, könnten Sie dies auf einen Blauton einstellen, um zu Ihrem Thema zu passen.

#### **Deckkraft**

- **Was diese Einstellung bewirkt:** Dies bestimmt, wie transparent oder undurchsichtig der Scroll-to-top-Button ist. Eine geringere Deckkraft macht ihn transparenter, sodass Hintergrundinhalte durchscheinen können.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen hohen Wert eingestellt (z. B. 1.0 oder 100%):* Der Button ist vollständig undurchsichtig, ohne Transparenz.
  - *Wenn auf einen niedrigeren Wert eingestellt (z. B. 0.7 oder 70%):* Der Button ist halbtransparent und fügt sich subtil in den Hintergrund Ihres Shops ein.
- **Empfohlener Wert:** Ein Wert zwischen 0.8 und 1.0 (80%-100%) ist normalerweise gut. Zu niedrig, und er könnte schwer zu sehen sein; zu hoch, und er könnte zu prominent wirken.
- **Händlerszenario / Beispiel:** Wenn Sie möchten, dass der Button vorhanden, aber nicht übermäßig dominant ist, könnte eine Deckkraft von 0.8 eine gute Wahl sein.

#### **Position X (von rechts)**

- **Was diese Einstellung bewirkt:** Dies steuert die horizontale Position des Buttons, insbesondere seinen Abstand vom rechten Rand des Browserfensters.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Erhöhen des Wertes (z. B. von 20px auf 50px):* Bewegt den Button weiter nach links, weg vom rechten Rand.
  - *Verringern des Wertes (z. B. von 50px auf 20px):* Bewegt den Button näher an den rechten Rand.
- **Empfohlener Wert:** Beginnen Sie mit einem Wert wie `20px` oder `30px`, um ihn bequem vom Rand entfernt zu halten, ohne zu weit in den Inhaltsbereich hineinzuragen.
- **Händlerszenario / Beispiel:** Wenn Sie ein Chat-Widget oder ein anderes festes Element auf der rechten Seite Ihres Shops haben, könnten Sie diesen Wert auf `60px` erhöhen, um zu verhindern, dass der Scroll-to-top-Button es überlappt.

#### **Position Y (von unten)**

- **Was diese Einstellung bewirkt:** Dies steuert die vertikale Position des Buttons, insbesondere seinen Abstand vom unteren Rand des Browserfensters.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Erhöhen des Wertes (z. B. von 20px auf 50px):* Bewegt den Button weiter nach oben, weg vom unteren Rand.
  - *Verringern des Wertes (z. B. von 50px auf 20px):* Bewegt den Button näher an den unteren Rand.
- **Empfohlener Wert:** Beginnen Sie mit einem Wert wie `20px` oder `30px`, um ihn bequem vom unteren Rand entfernt, oberhalb des Footers, zu halten.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop einen Sticky Footer oder eine Cookie-Zustimmungsleiste ganz unten hat, könnten Sie diesen Wert auf `70px` erhöhen, um sicherzustellen, dass der Scroll-to-top-Button immer über diesen Elementen sichtbar ist.

#### **Konfigurations-Schnellreferenztabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Visuelle Positionierung | Dynamisch | Visuelle Hilfe für die Button-Platzierung basierend auf X/Y-Einstellungen. |
| Modulkonfiguration | Farbschema | Variiert (z. B. #007bff) | Legt die Hintergrundfarbe des Scroll-to-top-Buttons fest. |
| Modulkonfiguration | Deckkraft | 0.8 - 1.0 | Steuert die Transparenz des Buttons (0.0 = vollständig transparent, 1.0 = vollständig undurchsichtig). |
| Modulkonfiguration | Position X (von rechts) | 20px - 30px | Definiert den horizontalen Abstand des Buttons vom rechten Bildschirmrand. |
| Modulkonfiguration | Position Y (von unten) | 20px - 30px | Definiert den vertikalen Abstand des Buttons vom unteren Bildschirmrand. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Scroll-to-top-Button erscheint nicht in meinem Shop. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Scroll to top“ installiert und aktiviert ist.
2. **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“. Aktualisieren Sie dann Ihr Front Office.
3. **Nach unten scrollen:** Denken Sie daran, dass der Button nur erscheint, wenn Sie die Seite nach unten scrollen. Stellen Sie sicher, dass Sie ausreichend gescrollt haben, damit er sichtbar wird.
4. **Positionen überprüfen:** Stellen Sie sicher, dass „Position X“ und „Position Y“ nicht auf extrem hohe Werte eingestellt sind, die den Button möglicherweise außerhalb des Bildschirms verschieben könnten. Versuchen Sie, sie testweise auf jeweils `20px` einzustellen.
5. **Theme-Kompatibilität:** Obwohl selten, können einige stark angepasste Themes CSS-Konflikte aufweisen. Wenn die oben genannten Schritte nicht funktionieren, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic), um zu sehen, ob der Button erscheint. Wenn ja, muss möglicherweise der Entwickler Ihres Themes helfen.

**F: Der Button ist sichtbar, scrollt aber beim Klicken nicht nach oben.**
A:

1. **JavaScript überprüfen:** Dies deutet normalerweise auf einen JavaScript-Konflikt oder -Fehler hin. Öffnen Sie die Entwicklerkonsole Ihres Browsers (normalerweise F12, dann zum Tab „Konsole“) und suchen Sie nach roten Fehlermeldungen.
2. **Modulreihenfolge:** Stellen Sie sicher, dass kein anderes Modul die Kern-JavaScript-Funktionalität stört.
3. **Neu installieren:** Versuchen Sie, das Modul zu deinstallieren und neu zu installieren. Dies kann manchmal beschädigte Dateien beheben.

**F: Wie kann ich das Icon des Buttons ändern (z. B. von einem Pfeil zu etwas anderem)?**
A: Das Modul verwendet ein Standard-Pfeilsymbol. Eine Änderung erfordert eine direkte Modifikation der CSS- oder Template-Dateien des Moduls, was unter Entwickleranpassung fällt. Es ist keine Option, die in der Modulkonfiguration verfügbar ist.

**F: Der Button sieht auf dem Desktop gut aus, ist aber auf Mobilgeräten zu groß/klein/falsch platziert.**
A:

1. **X & Y anpassen:** Verwenden Sie die Einstellungen „Position X“ und „Position Y“, um die Platzierung speziell für Mobilgeräte zu optimieren. Möglicherweise benötigen Sie unterschiedliche Werte, um Konflikte mit mobilspezifischen UI-Elementen zu vermeiden.
2. **Theme-Responsivität:** Das CSS des Moduls ist responsiv gestaltet, aber die allgemeine Responsivität Ihres Themes kann beeinflussen, wie es erscheint. Testen Sie auf tatsächlichen Geräten oder verwenden Sie die Entwicklertools Ihres Browsers, um verschiedene Bildschirmgrößen zu simulieren.
3. **Benutzerdefiniertes CSS (Entwickleraufgabe):** Für fortgeschrittene Größen- oder Stiländerungen, die spezifisch für Mobilgeräte sind, müsste ein Webmaster benutzerdefinierte CSS-Regeln zu Ihrem Theme hinzufügen, die den Button nur auf kleineren Bildschirmen ansprechen.

**F: Wird dieses Modul meine Website verlangsamen?**
A: Nein, das Modul „Scroll to top“ ist sehr leichtgewichtig. Es fügt minimale CSS- und JavaScript-Dateien hinzu, die effizient geladen werden. Jegliche Leistungsauswirkungen wären vernachlässigbar.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler, Webmaster und Agenturen, die das Modul „Scroll to top“ verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht

Das Modul „Scroll to top“ ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Verbesserung der Front-Office-Benutzeroberfläche konzentriert. Es folgt einer klassischen PrestaShop-Modulstruktur und nutzt Hooks, um seine HTML-, CSS- und JavaScript-Assets in das Front Office zu injizieren. Es führt keine benutzerdefinierten Controller oder komplexen Datenmodelle ein, sondern verlässt sich stattdessen auf das Konfigurationssystem von PrestaShop für seine Einstellungen. Die Kernfunktionalität wird clientseitig über JavaScript abgewickelt.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Funktionalität des Moduls wird vollständig durch das Injizieren von Assets und einem Template über Hooks abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Alle Konfigurationen werden über die `getContent()`-Methode des Hauptmoduls verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Die gesamte Logik befindet sich in der Hauptdatei `scrolltop.php`.

### 4.4 JavaScript-Assets (`views/js/`)

- **`scrolltop/scrolltop.js`**
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript verarbeitet die clientseitige Kernlogik für den Scroll-to-top-Button.
  - **Details:**
    - Es wartet, bis das DOM vollständig geladen ist (`$(document).ready()`).
    - Es fügt einen Event-Listener an das `$(window).scroll()`-Ereignis an.
    - Innerhalb des Scroll-Event-Handlers prüft es `$(this).scrollTop()`. Wenn die Scroll-Position größer als ein bestimmter Schwellenwert ist (z. B. 100px), zeigt es den Scroll-to-top-Button an; andernfalls blendet es ihn aus.
    - Es fügt einen Klick-Event-Listener an das Scroll-to-top-Button-Element an.
    - Beim Klicken verwendet es `$('html, body').animate({scrollTop: 0}, 'slow');`, um das Seiten-Scrollen sanft nach oben zu animieren.
    - Es verhindert das Standard-Link-Verhalten (`return false;`).
  - **Abhängigkeiten:** jQuery (das typischerweise im PrestaShop Front Office verfügbar ist).

### 4.5 CSS-Stylesheets (`views/css/`)

- **`scrolltop/scrolltop.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Verantwortlichkeit:** Definiert das visuelle Erscheinungsbild und die feste Positionierung des Scroll-to-top-Buttons.
  - **Details:**
    - Zielt auf das Element `#scroll-to-top` ab.
    - Verwendet `position: fixed;`, um den Button in einer statischen Position relativ zum Viewport zu halten.
    - Wendet `bottom`- und `right`-Eigenschaften an, die dynamisch durch die Modulkonfiguration festgelegt werden, um seine genaue Platzierung zu steuern.
    - Definiert `z-index`, um sicherzustellen, dass der Button über anderen Inhalten erscheint.
    - Setzt `display: none;` anfänglich, da das JavaScript seine Sichtbarkeit steuert.
    - Stile für `background-color`, `border-radius`, `padding`, `width`, `height`, `line-height`, `text-align`, `color` (für das Pfeilsymbol), `font-size` und `cursor`.
    - Enthält eine `transition`-Eigenschaft für sanfte visuelle Änderungen (z. B. beim Hovern oder beim Erscheinen/Verschwinden).
    - Kann responsive Anpassungen mithilfe von Media Queries enthalten, um das Erscheinungsbild auf verschiedenen Bildschirmgrößen zu optimieren.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** `#scroll-to-top`, `#scroll-to-top i` (für das Symbol).

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`scrolltop/footer.tpl`**
    - **Hook:** `displayFooter` (oder `displayHeader` für das Laden von Assets).
    - **Zweck:** Dieses Template rendert die HTML-Struktur für den Scroll-to-top-Button.
    - **Inhalt:** Enthält typischerweise ein `<a>`-Tag oder `<div>` mit einer ID wie `#scroll-to-top` und ein `<i>`-Tag (oft unter Verwendung von Font Awesome oder einer ähnlichen Icon-Schriftart) für das Pfeilsymbol.
    - Es enthält auch Inline-Stilattribute oder Datenattribute, um die konfigurierten Werte für `color`, `opacity`, `position X` und `position Y` aus den Moduleinstellungen an das Front-End-CSS oder JavaScript zur dynamischen Gestaltung zu übergeben.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen (`st_color`, `st_x`, `st_y`, `st_o`, `mypresta_updates`, `update_`, `updatev_`) werden in der PrestaShop-Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um die CSS- (`scrolltop.css`) und JavaScript- (`scrolltop.js`) Assets des Moduls zu registrieren und zu laden. |
| `displayFooter` | Am Ende des `<body>`-Bereichs jeder Front-Office-Seite, direkt vor dem schließenden `</body>`-Tag. | Wird verwendet, um die HTML-Struktur des Scroll-to-top-Buttons (`footer.tpl`) zu rendern. Dies stellt sicher, dass der HTML-Code des Buttons im DOM vorhanden ist, damit das JavaScript ihn manipulieren kann. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „Scroll to top“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
