---
title: "Twitter widget free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Twitter widget free von MyPresta.eu."
sidebar:
  label: "Twitter widget free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Twitter widget free auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/twitter-widget-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/twitter-widget-free/)
>
> ---


# Twitter widget free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine besonderen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Twitter widget free“. Hier definieren Sie, wie Ihre Twitter-Timeline in Ihrem Store erscheint und funktioniert.

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Twitter-Benutzername** | `mypresta` (Beispiel) | **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie gibt das Twitter (X)-Konto an, dessen öffentliche Tweets angezeigt werden sollen. Sie müssen den Benutzernamen Ihres Kontos eingeben (z. B. `mypresta`, `ihrstorename`).   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf Ihren Benutzernamen eingestellt:* Das Widget ruft Tweets von Ihrem angegebenen Konto ab und zeigt sie an.   *Wenn leer oder falsch:* Das Widget zeigt entweder keine Tweets oder eine Fehlermeldung an, da es nicht weiß, von welchem Konto Daten abgerufen werden sollen.   **Empfohlener Wert:** Ihr offizieller Twitter (X)-Benutzername, ohne das „@“-Symbol.   **Händlerszenario / Beispiel:** Wenn Ihr Twitter-Handle `@MeinTollerStore` ist, würden Sie hier `MeinTollerStore` eingeben. |
| **Widget-ID** | `(leer)` | **Was diese Einstellung bewirkt:** Dies ist eine erweiterte Einstellung für spezifische Twitter-Widget-Konfigurationen. Twitter ermöglicht es Ihnen, benutzerdefinierte Widgets auf ihrer Plattform zu erstellen, die eine eindeutige ID generieren. Diese ID kann verwendet werden, um eine hochgradig angepasste Timeline anzuzeigen (z. B. eine Timeline bestimmter Listen, Suchergebnisse oder Sammlungen).   **Auswirkung der Änderung dieser Einstellung:**   *Wenn leer gelassen:* Das Modul generiert eine Standard-Timeline basierend auf Ihrem „Twitter-Benutzernamen“. Dies ist in der Regel für die meisten Händler ausreichend.   *Wenn eine gültige Widget-ID eingegeben wird:* Das Modul zeigt die spezifische, angepasste Timeline an, die mit dieser ID verknüpft ist, und überschreibt die Standard-Benutzer-Timeline.   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben ein benutzerdefiniertes Widget auf der Twitter-Entwicklerplattform erstellt und möchten dessen ID speziell verwenden.   **Händlerszenario / Beispiel:** Sie könnten ein benutzerdefiniertes Twitter-Widget erstellen, das nur Tweets mit einem bestimmten Hashtag anzeigt, der sich auf eine Kampagne bezieht. Sie würden dann die ID dieses Widgets von Twitter erhalten und hier eingeben. |
| **Theme** | `light` | **Was diese Einstellung bewirkt:** Steuert das visuelle Theme des Twitter-Widgets.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf `light` (Standard) eingestellt:* Das Widget hat einen hellen Hintergrund und dunklen Text, geeignet für die meisten hellen PrestaShop-Stores.   *Wenn auf `dark` (falls verfügbar) eingestellt:* Das Widget hat einen dunklen Hintergrund und hellen Text, ideal für dunkle Stores oder um einen Kontrast zu erzeugen.   **Empfohlener Wert:** `light` für die meisten Stores. Wählen Sie `dark`, wenn das Design Ihres Stores ein dunkles Farbschema verwendet.   **Händlerszenario / Beispiel:** Wenn Ihre Website einen sauberen, weißen Hintergrund hat, fügt sich das `light`-Theme perfekt ein. Wenn Ihre Website einen anspruchsvollen dunkelgrauen oder schwarzen Hintergrund verwendet, wäre das `dark`-Theme passender. |
| **Linkfarbe** | `(leer)` | **Was diese Einstellung bewirkt:** Ermöglicht die Anpassung der Farbe von Links innerhalb des Twitter-Widgets (z. B. Hashtags, Erwähnungen, URLs).   **Auswirkung der Änderung dieser Einstellung:**   *Wenn leer gelassen:* Das Widget verwendet die Standard-Linkfarbe von Twitter (typischerweise ein Blauton).   *Wenn ein gültiger Hex-Farbcode eingegeben wird (z. B. `#FF0000` für Rot):* Alle Links innerhalb des Widgets werden in dieser benutzerdefinierten Farbe angezeigt.   **Empfohlener Wert:** Leer lassen für Standard, oder einen Hex-Farbcode eingeben, der zum Branding Ihres Stores passt.   **Händlerszenario / Beispiel:** Wenn die Primärfarbe Ihrer Marke Grün ist, könnten Sie `#008000` eingeben, um die Links im Widget an Ihre Marke anzupassen. |
| **Rahmenfarbe** | `(leer)` | **Was diese Einstellung bewirkt:** Ermöglicht die Anpassung der Farbe des Rahmens um das Twitter-Widget.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn leer gelassen:* Das Widget verwendet die Standard-Rahmenfarbe von Twitter.   *Wenn ein gültiger Hex-Farbcode eingegeben wird:* Der Rahmen des Widgets wird in dieser benutzerdefinierten Farbe angezeigt.   **Empfohlener Wert:** Leer lassen für Standard, oder einen Hex-Farbcode eingeben, der zum Branding Ihres Stores passt oder sich in Ihr Layout einfügt.   **Händlerszenario / Beispiel:** Um das Widget mit einem subtilen Rahmen hervorzuheben, könnten Sie einen hellgrauen Rahmen `#CCCCCC` verwenden. |
| **Tweet-Limit** | `20` | **Was diese Einstellung bewirkt:** Bestimmt die maximale Anzahl von Tweets, die in der Timeline angezeigt werden.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf eine niedrigere Zahl eingestellt (z. B. `3`):* Nur die letzten wenigen Tweets sind sichtbar, wodurch das Widget kürzer wird.   *Wenn auf eine höhere Zahl eingestellt (z. B. `20`):* Mehr Tweets werden geladen, wodurch das Widget länger wird und mehr Scrollen ermöglicht.   **Empfohlener Wert:** `3` bis `7` für Seitenleisten, um es prägnant zu halten, `10` bis `20` für breitere Bereiche wie den Footer oder den Hauptinhalt.   **Händlerszenario / Beispiel:** Wenn Sie das Widget in einer schmalen linken Spalte platzieren, könnten Sie es auf `3` einstellen, um die Spalte nicht zu lang zu machen. Im Footer könnten Sie es auf `10` einstellen, um mehr Aktivität anzuzeigen. |
| **Höhe** | `300` | **Was diese Einstellung bewirkt:** Legt die feste Höhe des Twitter-Widgets in Pixeln fest.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf eine niedrigere Zahl eingestellt (z. B. `200`):* Das Widget wird kürzer, was möglicherweise mehr Scrollen erfordert, um alle Tweets zu sehen (bis zum Tweet-Limit).   *Wenn auf eine höhere Zahl eingestellt (z. B. `500`):* Das Widget wird höher und zeigt mehr Tweets gleichzeitig ohne Scrollen an.   **Empfohlener Wert:** `280` bis `400` Pixel, abhängig von der Platzierung und dem verfügbaren Platz.   **Händlerszenario / Beispiel:** Für eine rechte Spalte ist eine Höhe von `300px` oft ein gutes Gleichgewicht. Für eine Footer-Platzierung könnten Sie sie auf `400px` erhöhen, wenn Sie ausreichend vertikalen Platz haben. |
| **Breite** | `(leer)` | **Was diese Einstellung bewirkt:** Legt die feste Breite des Twitter-Widgets in Pixeln fest.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn leer gelassen:* Das Widget versucht, seine Breite automatisch an den Container anzupassen, in dem es platziert ist (responsives Verhalten). Dies wird im Allgemeinen empfohlen.   *Wenn auf eine bestimmte Zahl eingestellt (z. B. `250`):* Das Widget behält diese feste Breite bei, was zu Überlauf oder leerem Raum führen kann, wenn der Container größer oder kleiner ist.   **Empfohlener Wert:** Leer lassen für responsives Verhalten, oder eine bestimmte Breite festlegen, wenn Sie präzise Kontrolle benötigen und die Auswirkungen auf verschiedene Bildschirmgrößen verstehen.   **Händlerszenario / Beispiel:** Wenn Sie es leer lassen, sieht es auf Mobilgeräten gut aus. Wenn Sie unbedingt eine feste Breite für ein sehr spezifisches Layout benötigen, könnten Sie es für eine schmale Spalte auf `280px` einstellen. |
| **Sprache** | `en` | **Was diese Einstellung bewirkt:** Bestimmt die Sprache, in der die Twitter-Widget-Oberfläche (z. B. „Auf Twitter ansehen“-Schaltfläche, Zeitstempel) angezeigt wird.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf `en` (Englisch) eingestellt:* Die Widget-Oberfläche ist auf Englisch.   *Wenn auf einen anderen gültigen Sprachcode eingestellt (z. B. `fr` für Französisch, `es` für Spanisch):* Die Widget-Oberfläche wird in diese Sprache lokalisiert.   **Empfohlener Wert:** Die primäre Sprache Ihres Stores.   **Händlerszenario / Beispiel:** Wenn Ihr Store hauptsächlich Kunden in Frankreich bedient, macht die Einstellung auf `fr` das Widget für sie benutzerfreundlicher. |
| **Header anzeigen** | `YES` | **Was diese Einstellung bewirkt:** Steuert, ob der Header-Bereich des Twitter-Widgets (mit Ihrem Kontonamen und der Bezeichnung „Tweets“) sichtbar ist.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Der Header wird angezeigt und bietet einen klaren Kontext, wessen Tweets angezeigt werden.   *Wenn deaktiviert (NO):* Der Header wird ausgeblendet, was zu einem kompakteren Widget führt, aber möglicherweise weniger klaren Kontext bietet.   **Empfohlener Wert:** `YES` zur Klarheit, es sei denn, Sie benötigen ein sehr minimalistisches Design.   **Händlerszenario / Beispiel:** Wenn das Widget an einem prominenten Ort platziert ist, ist `YES` gut. Wenn es ein kleines Widget in einem überfüllten Bereich ist, könnte `NO` Platz sparen. |
| **Footer anzeigen** | `YES` | **Was diese Einstellung bewirkt:** Steuert, ob der Footer-Bereich des Twitter-Widgets (typischerweise mit dem Link „Auf Twitter ansehen“) sichtbar ist.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Der Footer wird angezeigt und bietet einen direkten Link für Benutzer, um Ihr vollständiges Twitter-Profil zu besuchen.   *Wenn deaktiviert (NO):* Der Footer wird ausgeblendet, wodurch das Widget kompakter wird.   **Empfohlener Wert:** `YES`, um Benutzer zu ermutigen, Ihnen auf Twitter zu folgen.   **Händlerszenario / Beispiel:** `YES` beizubehalten hilft, Traffic auf Ihr Twitter-Profil zu lenken. |
| **Rahmen anzeigen** | `YES` | **Was diese Einstellung bewirkt:** Steuert, ob ein Rahmen um das Twitter-Widget angezeigt wird.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Ein Rahmen umgibt das Widget und hilft ihm, sich von umgebenden Inhalten abzuheben.   *Wenn deaktiviert (NO):* Das Widget hat keinen sichtbaren Rahmen und fügt sich nahtloser in den Hintergrund ein.   **Empfohlener Wert:** `YES` für eine bessere visuelle Trennung, insbesondere in Spalten.   **Händlerszenario / Beispiel:** Wenn Ihre Seite viele Inhalte hat, hilft ein Rahmen, den Platz des Widgets zu definieren. Wenn Sie ein sehr sauberes, integriertes Aussehen wünschen, könnte `NO` bevorzugt werden. |
| **Scrollleiste anzeigen** | `YES` | **Was diese Einstellung bewirkt:** Steuert, ob eine Scrollleiste innerhalb des Widgets erscheint, wenn der Inhalt (Tweets) die eingestellte Höhe überschreitet.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Eine Scrollleiste erscheint, die es Benutzern ermöglicht, durch alle geladenen Tweets innerhalb der festen Höhe zu scrollen.   *Wenn deaktiviert (NO):* Es erscheint keine Scrollleiste. Wenn Tweets die Höhe überschreiten, werden sie abgeschnitten, oder das Widget könnte sich erweitern (abhängig von anderen Einstellungen und dem Browserverhalten). Dies wird im Allgemeinen nicht empfohlen, da es Inhalte verbirgt.   **Empfohlener Wert:** `YES`, um sicherzustellen, dass alle Tweets zugänglich sind.   **Händlerszenario / Beispiel:** Behalten Sie immer `YES` bei, es sei denn, Sie möchten immer nur 1-2 Tweets anzeigen und niemals scrollen. |
| **Transparenter Hintergrund** | `YES` | **Was diese Einstellung bewirkt:** Steuert, ob der Hintergrund des Twitter-Widgets transparent ist.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Der Hintergrund des Widgets ist transparent, sodass die Hintergrundfarbe oder das Bild Ihres Stores durchscheinen kann.   *Wenn deaktiviert (NO):* Das Widget hat einen soliden Hintergrund (weiß für `light`-Theme, dunkel für `dark`-Theme), was möglicherweise ein kastenförmiges Aussehen erzeugt.   **Empfohlener Wert:** `YES` für eine bessere Integration in Ihr Theme.   **Händlerszenario / Beispiel:** Wenn Ihr Store einen strukturierten Hintergrund oder eine bestimmte Hintergrundfarbe hat, lässt `YES` das Widget wie einen natürlichen Teil Ihres Designs aussehen. |
| **Antworten anzeigen** | `YES` | **Was diese Einstellung bewirkt:** Steuert, ob Antworten auf Tweets in der Timeline enthalten sind.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Antworten werden angezeigt und bieten einen vollständigeren Gesprächskontext.   *Wenn deaktiviert (NO):* Nur Original-Tweets und Retweets werden angezeigt, wodurch die Timeline möglicherweise sauberer, aber weniger gesprächig wird.   **Empfohlener Wert:** `YES` für einen aktiveren und ansprechenderen Feed.   **Händlerszenario / Beispiel:** Wenn Sie häufig mit Kunden über Antworten interagieren, ist `YES` wichtig, um diese Interaktion zu zeigen. Wenn Ihr Feed rein für Ankündigungen gedacht ist, könnte `NO` bevorzugt werden. |
| **Videos automatisch abspielen** | `NO` | **Was diese Einstellung bewirkt:** Steuert, ob in Tweets eingebettete Videos innerhalb des Widgets automatisch abgespielt werden.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Videos beginnen automatisch abzuspielen, wenn sie im Sichtfeld erscheinen. Dies kann ansprechend sein, aber Bandbreite verbrauchen und einige Benutzer stören.   *Wenn deaktiviert (NO):* Videos erfordern einen Benutzerklick zum Abspielen.   **Empfohlener Wert:** `NO`, um Kunden nicht mit Ton zu überraschen oder ihre Daten ohne Zustimmung zu verbrauchen.   **Händlerszenario / Beispiel:** Im Allgemeinen ist `NO` besser für die Benutzererfahrung. Wenn Sie ein sehr spezifisches, stilles, kurzes Video hervorheben möchten, könnten Sie `YES` in Betracht ziehen, aber gehen Sie vorsichtig vor. |
| **Scrollleiste ausblenden** | `NO` | **Was diese Einstellung bewirkt:** Diese Einstellung ist wahrscheinlich redundant oder widersprüchlich mit „Scrollleiste anzeigen“. Im Allgemeinen sollte diese Einstellung `NO` sein, wenn „Scrollleiste anzeigen“ auf `YES` steht.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert (YES):* Versucht, die Scrollleiste auszublenden. Dies kann dazu führen, dass Inhalte unzugänglich werden, wenn die Höhe fest ist und Tweets diese überschreiten.   *Wenn deaktiviert (NO):* Ermöglicht die Sichtbarkeit der Scrollleiste, wenn „Scrollleiste anzeigen“ ebenfalls `YES` ist.   **Empfohlener Wert:** `NO`, um sicherzustellen, dass Inhalte immer zugänglich sind.   **Händlerszenario / Beispiel:** Behalten Sie immer `NO` in Verbindung mit `Scrollleiste anzeigen: YES` bei. |
| **In Hook platzieren** | `displayRightColumn` | **Was diese Einstellung bewirkt:** Bestimmt, wo in Ihrem PrestaShop-Store das Twitter-Widget angezeigt wird.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf `displayRightColumn` (Standard) eingestellt:* Das Widget erscheint in der rechten Seitenleiste.   *Wenn auf `displayLeftColumn` (falls verfügbar) eingestellt:* Das Widget erscheint in der linken Seitenleiste.   *Wenn auf `displayFooter` (falls verfügbar) eingestellt:* Das Widget erscheint im Footer-Bereich.   *Wenn auf `displayHeader` (falls verfügbar) eingestellt:* Das Widget erscheint im Header-Bereich.   *Wenn auf `displayProductButtons` oder ähnliches (falls verfügbar) eingestellt:* Das Widget erscheint auf Produktseiten.   **Empfohlener Wert:** `displayRightColumn` oder `displayLeftColumn` für allgemeine Sichtbarkeit, `displayFooter` für eine weniger aufdringliche Platzierung. Wählen Sie basierend auf dem Layout Ihres Themes und wo Sie Aufmerksamkeit erregen möchten.   **Händlerszenario / Beispiel:** Wenn Ihr Theme eine prominente rechte Seitenleiste hat, ist `displayRightColumn` eine gute Wahl. Wenn Sie möchten, dass es auf jeder Seite sichtbar ist, aber nicht viel Platz einnimmt, ist `displayFooter` geeignet. |

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|
| Modulkonfiguration | Twitter-Benutzername | Ihr X-Benutzername | Gibt das Konto an, von dem Tweets angezeigt werden sollen. |
| Modulkonfiguration | Widget-ID | Leer | Erweitert: Für benutzerdefinierte, von Twitter generierte Widgets verwenden. |
| Modulkonfiguration | Theme | `light` | Visuelles Theme des Widgets (hell/dunkel). |
| Modulkonfiguration | Linkfarbe | Leer | Passt die Linkfarben innerhalb des Widgets an. |
| Modulkonfiguration | Rahmenfarbe | Leer | Passt die Rahmenfarbe des Widgets an. |
| Modulkonfiguration | Tweet-Limit | `20` | Maximale Anzahl der anzuzeigenden Tweets. |
| Modulkonfiguration | Höhe | `300` | Feste Höhe des Widgets in Pixeln. |
| Modulkonfiguration | Breite | Leer | Feste Breite des Widgets in Pixeln (leer lassen für responsiv). |
| Modulkonfiguration | Sprache | `en` | Sprache der Widget-Oberfläche. |
| Modulkonfiguration | Header anzeigen | `YES` | Widget-Header (Kontoname) ein-/ausblenden. |
| Modulkonfiguration | Footer anzeigen | `YES` | Widget-Footer (Link „Auf Twitter ansehen“) ein-/ausblenden. |
| Modulkonfiguration | Rahmen anzeigen | `YES` | Äußeren Rahmen des Widgets ein-/ausblenden. |
| Modulkonfiguration | Scrollleiste anzeigen | `YES` | Interne Scrollleiste für Tweets ein-/ausblenden. |
| Modulkonfiguration | Transparenter Hintergrund | `YES` | Widget-Hintergrund transparent machen. |
| Modulkonfiguration | Antworten anzeigen | `YES` | Antworten in der Timeline ein-/ausschließen. |
| Modulkonfiguration | Videos automatisch abspielen | `NO` | Videos in Tweets automatisch abspielen. |
| Modulkonfiguration | Scrollleiste ausblenden | `NO` | (Redundant mit Scrollleiste anzeigen) Auf NO belassen. |
| Modulkonfiguration | In Hook platzieren | `displayRightColumn` | Wo das Widget in Ihrem Store erscheint. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Twitter-Widget wird in meinem Store nicht angezeigt. Was soll ich tun?**
A:

1. **Konfiguration überprüfen:** Gehen Sie zu **Module > Modul-Manager > Twitter widget free > Konfigurieren**. Stellen Sie sicher, dass Sie Ihren korrekten „Twitter-Benutzernamen“ eingegeben und die Einstellungen gespeichert haben.
2. **Hook-Platzierung überprüfen:** Vergewissern Sie sich, dass die Einstellung „In Hook platzieren“ auf einen Hook eingestellt ist, der tatsächlich von Ihrem Theme gerendert wird (z. B. `displayRightColumn`). Einige Themes zeigen möglicherweise nicht alle Standard-Hooks an.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindert der PrestaShop-Cache, dass neue Modulinhalte sofort angezeigt werden.
4. **Theme-Kompatibilität:** Obwohl das Modul weitgehend kompatibel ist, erfordern sehr stark angepasste Themes möglicherweise geringfügige Anpassungen. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F: Das Widget erscheint, ist aber leer oder zeigt eine Fehlermeldung an.**
A:

1. **Falscher Benutzername:** Überprüfen Sie Ihren „Twitter-Benutzernamen“ in der Modulkonfiguration. Schon ein kleiner Tippfehler verhindert das Abrufen von Tweets.
2. **Privates Konto:** Stellen Sie sicher, dass Ihr Twitter-Konto öffentlich ist. Das Widget kann keine Tweets von privaten (geschützten) Konten anzeigen.
3. **Twitter-API-Probleme:** Gelegentlich kann es zu vorübergehenden Problemen mit der Twitter-API selbst kommen. Warten Sie eine Weile und versuchen Sie es erneut.

**F: Wie ändere ich die Sprache des Widgets?**
A: Suchen Sie in der Modulkonfiguration die Einstellung „Sprache“ und wählen Sie den entsprechenden zweistelligen Sprachcode aus (z. B. `fr` für Französisch, `es` für Spanisch).

**F: Das Widget sieht zu breit/schmal oder zu hoch/kurz aus.**
A:

1. **Breite:** Für responsives Verhalten lassen Sie die Einstellung „Breite“ leer. Wenn Sie einen bestimmten Pixelwert festgelegt haben, versuchen Sie, ihn zu entfernen.
2. **Höhe:** Passen Sie die Einstellung „Höhe“ (in Pixeln) an, um das Widget höher oder kürzer zu machen.
3. **Tweet-Limit:** Reduzieren Sie das „Tweet-Limit“, um das Widget kürzer zu machen, wenn Sie eine feste Höhe haben und weniger Tweets anzeigen möchten.

**F: Kann ich Tweets von einem bestimmten Hashtag oder einer Liste anstelle meines Hauptkontos anzeigen?**
A: Ja, dies erfordert jedoch eine erweiterte Einrichtung. Sie müssten ein benutzerdefiniertes eingebettetes Timeline-Widget direkt auf der Twitter-Entwicklerplattform (developer.twitter.com) erstellen, es dort so konfigurieren, dass es einen Hashtag oder eine Liste anzeigt, und dann die eindeutige „Widget-ID“ erhalten, die es bereitstellt. Sie würden diese „Widget-ID“ dann in die Konfiguration des Moduls eingeben und den „Twitter-Benutzernamen“ leer lassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Twitter widget free“ ist ein unkompliziertes PrestaShop-Modul, das die eingebettete Timeline-Funktionalität von Twitter integriert. Es nutzt hauptsächlich die Standard-Modulstruktur von PrestaShop, wobei die Hauptdatei `index.php` sowohl für die Installation/Deinstallation als auch für die Konfiguration (`getContent()`) verwendet wird. Das Modul injiziert ein JavaScript-basiertes Twitter-Widget in das Front-Office mithilfe einer Smarty-Vorlage und einer CSS-Datei für grundlegendes Styling. Es stützt sich auf Twitters eigene `widgets.js` für die Darstellung der Timeline, die asynchron geladen wird.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Anzeige des Moduls wird vollständig über Hooks und eine Smarty-Vorlage abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Die gesamte Logik ist in der Hauptdatei `twitterwidget/index.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- Es sind keine benutzerdefinierten JavaScript-Dateien direkt im Verzeichnis `views/js/` des Moduls enthalten.
- Das Modul stützt sich stark auf das offizielle Twitter-Skript `widgets.js`, das dynamisch in der Front-Office-Vorlage (`rightcolumn.tpl`) geladen wird, um die eingebettete Timeline zu rendern. Dieses Skript übernimmt die gesamte komplexe Logik des Abrufens und Anzeigens von Tweets.

### 4.5 CSS-Stylesheets (`views/css/`)

- `twitterwidget/twitterwidget.css`:
  - **Geltungsbereich**: Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt**: Diese Datei enthält wahrscheinlich minimale Stile, hauptsächlich um sicherzustellen, dass das Twitter-Widget gut mit verschiedenen PrestaShop-Themes harmoniert. Sie könnte Regeln für den `.twitter-widget`-Container, grundlegende Resets oder responsive Anpassungen enthalten.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler können diese Datei inspizieren, um spezifische Selektoren (z. B. `.twitter-widget-container`, `.twitter-timeline`) zu identifizieren und sie in der `custom.css` oder `theme.css` ihres Themes zu überschreiben, um das Erscheinungsbild des Widgets weiter anzupassen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `twitterwidget/rightcolumn.tpl`:
    - **Hook(s), in denen gerendert wird**: Diese Vorlage ist so konzipiert, dass sie in verschiedenen Anzeige-Hooks gerendert wird, wie vom Händler konfiguriert (z. B. `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayHeader`, `displayProductButtons`). Die `hookDisplay*`-Methoden des Moduls rufen diese Vorlage auf.
    - **Visuelle Blockausgabe**: Diese Vorlage gibt die HTML-Struktur aus, die für die eingebettete Timeline von Twitter erforderlich ist. Sie enthält typischerweise ein `<a>`-Tag mit `data-`-Attributen (z. B. `data-tweet-limit`, `data-theme`, `data-link-color`, `data-border-color`, `data-height`, `data-width`, `data-lang`, `data-chrome`, `data-dnt`, `data-show-replies`, `data-autoplay`), die das `widgets.js`-Skript von Twitter liest, um die Timeline zu rendern. Es enthält auch das `<script>`-Tag, um `widgets.js` asynchron zu laden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln (z. B. `TWITTERWIDGET_USERNAME`, `TWITTERWIDGET_WIDGETID`, `TWITTERWIDGET_THEME` usw.) gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Potenziell zum globalen Laden des Twitter-Widget-Skripts oder zur Anzeige des Widgets im Header-Bereich verwendet. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Zeigt das Twitter-Widget in der rechten Spalte an. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Zeigt das Twitter-Widget in der linken Spalte an. |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Zeigt das Twitter-Widget im Footer an. |
| `displayProductButtons` | Auf der Produktseite, typischerweise in der Nähe des „In den Warenkorb“-Buttons oder der Produktbeschreibung. | Zeigt das Twitter-Widget auf Produktseiten an. |
| `actionFrontControllerSetMedia` | Nachdem der Front-Controller seine Medien gesetzt hat, wodurch Module ihre eigenen hinzufügen können. | Wird verwendet, um CSS- und potenziell JS-Dateien des Moduls zu registrieren (obwohl dieses Modul Twitters JS direkt in TPL lädt). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Twitter widget free“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.
