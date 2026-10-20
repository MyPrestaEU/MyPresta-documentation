---
title: "Slider für kürzlich verkaufte Produkte - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Slider für kürzlich verkaufte Produkte' von MyPresta.eu."
sidebar:
  label: "Slider für kürzlich verkaufte Produkte - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Recently sold products slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/recently-sold-products-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/recently-sold-products-slider/)
>
> ---


# Slider für kürzlich verkaufte Produkte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Slider für kürzlich verkaufte Produkte“. Hier können Sie das Aussehen, das Verhalten und den Inhalt Ihres Produkt-Sliders anpassen.

#### **Hintergrundfarbe (rsps\_c\_bg)**

- **Was diese Einstellung bewirkt:** Dies steuert die Hintergrundfarbe des gesamten Slider-Blocks.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine Farbe eingestellt (z.B. #FFFFFF für Weiß):* Der Hintergrund des Sliders wird in dieser spezifischen Farbe angezeigt, wodurch er sich in Ihr Theme einfügen oder davon abheben kann.
  - *Wenn leer oder ungültig gelassen:* Der Slider könnte Hintergrundstile von Ihrem Theme erben oder standardmäßig einen transparenten Hintergrund verwenden.
- **Empfohlener Wert:** Wählen Sie eine Farbe, die zum Design Ihres Shops passt. Oft ist eine dezente Farbe oder eine, die zu Ihrem Header/Footer passt, am besten.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop einen dunklen Header hat, könnte das Einstellen dieser Farbe auf ein dunkles Grau oder Schwarz den Slider integriert aussehen lassen. Wenn Sie möchten, dass er hervorsticht, könnte eine Kontrastfarbe funktionieren.

#### **Rahmenfarbe (rsps\_c\_border)**

- **Was diese Einstellung bewirkt:** Definiert die Farbe des Rahmens um den gesamten Slider-Block.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine Farbe eingestellt (z.B. #CCCCCC für Hellgrau):* Ein Rahmen dieser Farbe erscheint um den Slider.
  - *Wenn leer oder ungültig gelassen:* Es wird kein expliziter Rahmen durch das Modul angewendet, obwohl Ihr Theme möglicherweise immer noch einen hinzufügt.
- **Empfohlener Wert:** Oft ist ein dezenter Rahmen, der zu den anderen Rahmen Ihres Themes passt, oder ein transparenter Rahmen am besten.
- **Händlerszenario / Beispiel:** Wenn Ihre Website dünne graue Rahmen für andere Elemente verwendet, wird das Einstellen dieser Farbe auf dasselbe Grau die Konsistenz bewahren.

#### **Schriftfarbe (rsps\_c\_font)**

- **Was diese Einstellung bewirkt:** Legt die Farbe des Textes (Produktnamen) fest, der im Slider angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine Farbe eingestellt (z.B. #333333 für Dunkelgrau):* Die Produktnamen werden in der gewählten Farbe angezeigt.
  - *Wenn leer oder ungültig gelassen:* Die Textfarbe könnte standardmäßig die allgemeine Schriftfarbe Ihres Themes sein.
- **Empfohlener Wert:** Wählen Sie eine Farbe, die einen guten Kontrast zur Hintergrundfarbe des Sliders bietet, um die Lesbarkeit zu gewährleisten.
- **Händlerszenario / Beispiel:** Wenn der Hintergrund Ihres Sliders dunkel ist, ist eine helle Schriftfarbe (wie Weiß oder Hellgrau) für die Lesbarkeit erforderlich.

#### **Slider-Abstand (rsps\_s\_padding)**

- **Was diese Einstellung bewirkt:** Steuert den internen Abstand (Padding) zwischen dem Inhalt (Text) und den Rändern des Slider-Blocks.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen Wert eingestellt (z.B. „10px“):* Der Text hat 10 Pixel Abstand auf allen Seiten vom Rahmen des Sliders.
  - *Wenn auf „0px“ oder leer eingestellt:* Der Text sitzt direkt an den Rändern des Sliders.
- **Empfohlener Wert:** „5px“ oder „10px“, um dem Text etwas Raum zum Atmen zu geben und die Ästhetik zu verbessern.
- **Händlerszenario / Beispiel:** Wenn Ihr Text zu gedrängt aussieht, erhöht das Erhöhen des Paddings den Abstand um ihn herum, wodurch er sauberer aussieht.

#### **Slider-Schriftgröße (rsps\_s\_font)**

- **Was diese Einstellung bewirkt:** Bestimmt die Größe der Schrift, die für die Produktnamen im Slider verwendet wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen Wert eingestellt (z.B. „14px“):* Der Text wird in dieser spezifischen Pixelgröße angezeigt.
  - *Wenn leer oder ungültig gelassen:* Die Schriftgröße könnte standardmäßig die allgemeine Schriftgröße Ihres Themes sein.
- **Empfohlener Wert:** „14px“ oder „16px“ für gute Lesbarkeit, ohne zu groß oder zu klein zu sein.
- **Händlerszenario / Beispiel:** Wenn der Slider an einer prominenten Stelle wie dem Header platziert ist, könnte eine etwas größere Schrift angemessen sein. Für eine Seitenleiste könnte eine kleinere Schrift besser passen.

#### **Slider-Rahmen (rsps\_s\_border)**

- **Was diese Einstellung bewirkt:** Definiert die Dicke und den Stil des Rahmens um den *inneren Inhalt* des Sliders (den scrollenden Textbereich selbst), getrennt vom gesamten Blockrahmen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen Wert eingestellt (z.B. „1px solid #CCCCCC“):* Ein 1 Pixel dicker, durchgehender hellgrauer Rahmen erscheint um den scrollenden Text.
  - *Wenn leer oder ungültig gelassen:* Es wird kein expliziter innerer Rahmen angewendet.
- **Empfohlener Wert:** „0px“ oder „none“, wenn Sie nur den äußeren Blockrahmen wünschen. Wenn Sie eine subtile Trennung wünschen, kann „1px solid #EEEEEE“ funktionieren.
- **Händlerszenario / Beispiel:** Sie könnten dies verwenden, um einen deutlichen visuellen Kasten für den scrollenden Text innerhalb des größeren Slider-Bereichs zu erstellen.

#### **Bewegungsrichtung (rsps\_m\_dir)**

- **Was diese Einstellung bewirkt:** Steuert die Richtung, in der die Produktnamen innerhalb des Sliders scrollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „left“ eingestellt:* Der Text scrollt von rechts nach links.
  - *Wenn auf „right“ eingestellt:* Der Text scrollt von links nach rechts.
- **Empfohlener Wert:** „left“ ist eine gängige und natürliche Leserichtung für scrollenden Text.
- **Händlerszenario / Beispiel:** Die meisten Benutzer sind an links scrollenden Text gewöhnt, daher bietet die Einstellung „left“ oft die beste Benutzererfahrung.

#### **Bewegungsverzögerung (rsps\_m\_delay)**

- **Was diese Einstellung bewirkt:** Bestimmt die Geschwindigkeit der Scroll-Animation. Dies wird typischerweise in Millisekunden gemessen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen niedrigeren Wert eingestellt (z.B. „50“):* Der Text scrollt schneller.
  - *Wenn auf einen höheren Wert eingestellt (z.B. „100“):* Der Text scrollt langsamer.
- **Empfohlener Wert:** „70“ bis „100“ bietet eine flüssige, lesbare Geschwindigkeit, ohne zu schnell oder zu langsam zu sein.
- **Händlerszenario / Beispiel:** Wenn der Text zu schnell ist, können Kunden ihn nicht lesen. Wenn er zu langsam ist, zieht er möglicherweise keine Aufmerksamkeit auf sich. Experimentieren Sie, um ein Gleichgewicht zu finden.

#### **Slider-Position (rsps\_position)**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl des PrestaShop-Hooks, in dem der Slider in Ihrem Shop angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `displayHome` eingestellt:* Der Slider wird auf der Startseite Ihres Shops angezeigt.
  - *Wenn auf `displayHeader` eingestellt:* Der Slider wird im Header-Bereich aller Seiten angezeigt.
  - *Wenn auf `displayFooter` eingestellt:* Der Slider wird im Footer-Bereich aller Seiten angezeigt.
  - *Andere Optionen (z.B. `displayLeftColumn`, `displayRightColumn`, `displayTop`):* Der Slider wird in der jeweiligen Spalte oder im oberen Bereich angezeigt.
- **Empfohlener Wert:** `displayHeader` oder `displayHome` für maximale Sichtbarkeit, oder `displayFooter` für einen subtileren Ansatz.
- **Händlerszenario / Beispiel:** Wenn Sie möchten, dass jeder Besucher die aktuellen Verkäufe sofort sieht, wählen Sie `displayHeader`. Wenn Sie möchten, dass es Teil Ihres Startseiteninhalts ist, wählen Sie `displayHome`.

#### **Anzahl der Produkte (rsps\_nb)**

- **Was diese Einstellung bewirkt:** Gibt an, wie viele kürzlich verkaufte Produkte abgerufen und im Slider angezeigt werden sollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine niedrigere Zahl eingestellt (z.B. „5“):* Es werden nur die 5 neuesten Verkäufe angezeigt.
  - *Wenn auf eine höhere Zahl eingestellt (z.B. „20“):* Bis zu 20 aktuelle Verkäufe werden in die scrollende Liste aufgenommen.
- **Empfohlener Wert:** „10“ bis „15“, um eine gute Produktvielfalt zu gewährleisten, ohne die Liste übermäßig lang zu machen.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop viele Verkäufe hat, bietet eine höhere Zahl mehr Social Proof. Wenn die Verkäufe seltener sind, könnte eine niedrigere Zahl ausreichen.

#### **Sortieren nach (rsps\_order)**

- **Was diese Einstellung bewirkt:** Bestimmt die Sortierkriterien für die im Slider angezeigten Produkte.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „date\_add“ eingestellt:* Produkte werden nach dem Datum sortiert, an dem sie der Bestellung hinzugefügt wurden (neueste zuerst).
  - *Wenn auf „product\_name“ eingestellt:* Produkte werden alphabetisch nach Namen sortiert.
  - *Wenn auf „price“ eingestellt:* Produkte werden nach Preis sortiert.
- **Empfohlener Wert:** „date\_add“, um wirklich „kürzlich verkaufte“ Artikel anzuzeigen.
- **Händlerszenario / Beispiel:** Um aktuelle Käufe genau widerzuspiegeln, ist die Sortierung nach `date_add` die logischste Wahl.

#### **Diversität (rsps\_diversity)**

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob der Slider einzigartige Produkte anzeigen oder zulassen soll, dass dasselbe Produkt mehrmals erscheint, wenn es kürzlich verkauft wurde.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (z.B. „Ja“ oder „1“):* Wenn dasselbe Produkt mehrmals verkauft wurde, erscheint es nur einmal in der Liste der anzuzeigenden Produkte, wodurch eine größere Vielfalt an Artikeln gewährleistet wird.
  - *Wenn deaktiviert (z.B. „Nein“ oder „0“):* Dasselbe Produkt könnte mehrmals im Slider erscheinen, wenn es Teil mehrerer aktueller Bestellungen war.
- **Empfohlener Wert:** „Ja“ (oder „1“), um eine größere Auswahl Ihres Katalogs zu präsentieren und zu verhindern, dass der Slider repetitiv wird.
- **Händlerszenario / Beispiel:** Wenn Sie einen sehr beliebten Artikel verkaufen, könnte das Deaktivieren der Diversität bedeuten, dass der Slider nur diesen einen Artikel wiederholt anzeigt. Das Aktivieren stellt sicher, dass auch andere Produkte eine Chance erhalten, gesehen zu werden.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Hintergrundfarbe** (rsps\_c\_bg) | `#FFFFFF` (Weiß) | Legt die Hintergrundfarbe des Slider-Blocks fest. |
| Modulkonfiguration | **Rahmenfarbe** (rsps\_c\_border) | `#CCCCCC` (Hellgrau) | Legt die Rahmenfarbe um den Slider-Block fest. |
| Modulkonfiguration | **Schriftfarbe** (rsps\_c\_font) | `#333333` (Dunkelgrau) | Legt die Farbe des Produktnamen-Textes fest. |
| Modulkonfiguration | **Slider-Abstand** (rsps\_s\_padding) | `10px` | Interner Abstand um den Text innerhalb des Sliders. |
| Modulkonfiguration | **Slider-Schriftgröße** (rsps\_s\_font) | `14px` | Größe der Schrift für Produktnamen. |
| Modulkonfiguration | **Slider-Rahmen** (rsps\_s\_border) | `0px` | Rahmen um den scrollenden Textbereich selbst. |
| Modulkonfiguration | **Bewegungsrichtung** (rsps\_m\_dir) | `left` | Richtung der Scroll-Animation (links oder rechts). |
| Modulkonfiguration | **Bewegungsverzögerung** (rsps\_m\_delay) | `70` | Geschwindigkeit der Scroll-Animation (niedriger = schneller). |
| Modulkonfiguration | **Slider-Position** (rsps\_position) | `displayHeader` | PrestaShop-Hook, in dem der Slider angezeigt wird. |
| Modulkonfiguration | **Anzahl der Produkte** (rsps\_nb) | `10` | Maximale Anzahl der kürzlich verkauften Produkte, die angezeigt werden sollen. |
| Modulkonfiguration | **Sortieren nach** (rsps\_order) | `date_add` | Sortierkriterien für die angezeigten Produkte. |
| Modulkonfiguration | **Diversität** (rsps\_diversity) | `Ja` (1) | Stellt sicher, dass einzigartige Produkte angezeigt werden (verhindert Wiederholungen). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul konfiguriert, aber der Slider wird in meinem Shop nicht angezeigt.**
**A1:**

- **Hook-Position überprüfen:** Gehen Sie in Ihrem PrestaShop Back Office zu **Design > Positionen**. Suchen Sie nach dem Hook, den Sie in der Einstellung „Slider-Position“ des Moduls ausgewählt haben (z.B. `displayHeader`, `displayHome`). Stellen Sie sicher, dass das Modul „Slider für kürzlich verkaufte Produkte“ in diesem Hook aufgeführt und aktiviert ist. Falls nicht, müssen Sie möglicherweise ein Modul in den richtigen Hook „transplantieren“.
- **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
- **Modul aktiviert:** Überprüfen Sie nochmals, ob das Modul unter **Module > Modul-Manager** aktiviert ist.
- **Aktuelle Verkäufe:** Stellen Sie sicher, dass Sie tatsächlich aktuelle Verkäufe in Ihrem Shop haben. Das Modul basiert auf vorhandenen Bestelldaten.

**F2: Der Slider wird angezeigt, aber die Farben oder Schriftgrößen entsprechen nicht meinen Einstellungen.**
**A2:**

- **Cache leeren:** Dies ist der häufigste Grund für Styling-Probleme. Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) und den Cache Ihres Browsers (Strg+F5 oder Cmd+R).
- **Theme-Überschreibungen:** Ihr PrestaShop-Theme könnte eigene CSS-Regeln haben, die die Stile des Moduls überschreiben. Möglicherweise müssen Sie das Element mit den Entwicklertools Ihres Browsers (F12) überprüfen, um zu sehen, welche CSS-Regeln angewendet werden. Wenn es sich um einen Theme-Konflikt handelt, müssen Sie möglicherweise benutzerdefiniertes CSS zu Ihrem Theme hinzufügen, um die Stile des Moduls zu erzwingen.
- **Korrekte Eingabe:** Stellen Sie sicher, dass Sie gültige CSS-Farbcodes (z.B. `#RRGGBB` oder `rgba(R,G,B,A)`) und Pixelwerte (z.B. `14px`) in der Modulkonfiguration verwenden.

**F3: Der Text scrollt zu schnell/langsam, oder er ist schwer zu lesen.**
**A3:**

- **Bewegungsverzögerung:** Passen Sie die Einstellung „Bewegungsverzögerung“ an. Eine höhere Zahl macht es langsamer, eine niedrigere Zahl macht es schneller. Experimentieren Sie, bis Sie eine angenehme Lesegeschwindigkeit gefunden haben.
- **Schriftgröße & Kontrast:** Stellen Sie sicher, dass Ihre „Slider-Schriftgröße“ ausreichend ist und dass Ihre „Schriftfarbe“ einen guten Kontrast zu Ihrer „Hintergrundfarbe“ aufweist.
- **Anzahl der Produkte:** Wenn Sie zu viele Produkte und eine sehr hohe Geschwindigkeit haben, könnte es überwältigend sein. Reduzieren Sie die „Anzahl der Produkte“ oder verlangsamen Sie die „Bewegungsverzögerung“.

**F4: Kann ich den Text „Jemand hat gerade…“ in andere Sprachen übersetzen?**
**A4:** Ja, PrestaShop-Module sind typischerweise übersetzbar.

- Gehen Sie in Ihrem Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“ für den „Übersetzungstyp“.
- Wählen Sie Ihr Theme aus.
- Wählen Sie die Sprache aus, in die Sie übersetzen möchten.
- Suchen Sie das Modul „Slider für kürzlich verkaufte Produkte“ in der Liste, und Sie sollten die übersetzbaren Zeichenfolgen bearbeiten können.

**F5: Der Slider sieht auf dem Desktop gut aus, ist aber auf Mobilgeräten defekt oder schlecht formatiert.**
**A5:**

- **Cache leeren:** Beginnen Sie immer mit dem Leeren des PrestaShop- und Browser-Caches.
- **Theme-Responsivität:** Obwohl das Modul selbst responsiv gestaltet ist, können Konflikte mit dem responsiven CSS Ihres spezifischen Themes auftreten.
- **Abstände/Rahmen überprüfen:** Übermäßige Abstände oder Rahmen könnten Inhalte auf kleineren Bildschirmen aus dem Blickfeld schieben. Versuchen Sie, „Slider-Abstand“ oder „Slider-Rahmen“ vorübergehend zu reduzieren, um zu sehen, ob dies das Problem löst.
- **Auf Mobilgeräten überprüfen:** Verwenden Sie die Entwicklertools Ihres Browsers (F12) und wechseln Sie zur mobilen Ansicht, oder testen Sie direkt auf einem mobilen Gerät, um spezifische Layoutprobleme zu diagnostizieren. Möglicherweise ist benutzerdefiniertes CSS in Ihrem Theme erforderlich, um bei einem Konflikt Anpassungen für Mobilgeräte vorzunehmen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Slider für kürzlich verkaufte Produkte“ für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul „Slider für kürzlich verkaufte Produkte“ (`recentlysoldproducts`) folgt einer Standard-PrestaShop-Modularchitektur. Es ist ein Ein-Datei-Modul (`recentlysoldproducts.php`), das `Module` erweitert und seine eigene Installation, Deinstallation, Konfiguration (`getContent()`) und Front-Office-Anzeige über Hooks handhabt. Es nutzt die `Configuration`-Klasse von PrestaShop zur Speicherung von Einstellungen und Smarty für die Templating. Die Front-Office-Funktionalität wird hauptsächlich durch JavaScript für die Scroll-Animation und das Styling gesteuert.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** dedizierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird innerhalb der Methode `getContent()` der Hauptmoduldatei gehandhabt, und die Front-Office-Darstellung wird direkt über PrestaShop-Hooks verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen in einem `classes/`-Verzeichnis. Es fragt die PrestaShop-Datenbank direkt nach Bestell- und Produktinformationen innerhalb der Hauptmoduldatei ab.

### 4.4 JavaScript-Assets (`views/js/`)

- **`recentlysoldproducts/jscolor/jscolor.js`**

  - **Geltungsbereich:** Back-Office (wird in `getContent()` für Farbwähler verwendet).
  - **Beschreibung:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters, die eine benutzerfreundliche Farbwähler-Oberfläche für Eingabefelder bereitstellt. Sie ist in das Konfigurationsformular des Moduls integriert, um Händlern die einfache Auswahl von Farben für den Hintergrund, den Rahmen und die Schrift des Sliders zu ermöglichen. Sie funktioniert typischerweise, indem sie einem Eingabefeld eine Klasse (z.B. `jscolor`) hinzufügt, die es dann in einen Farbwähler umwandelt.
- **`recentlysoldproducts/js/script.js`**

  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Diese Datei enthält wahrscheinlich die Kernlogik für die Scroll-Slider-Animation. Sie würde typischerweise:
    - Das Slider-Container-Element auswählen (z.B. nach ID oder Klasse).
    - Variablen für Bewegungsrichtung, Geschwindigkeit und Inhalt initialisieren.
    - Eine kontinuierliche Scroll-Animationsschleife implementieren, möglicherweise unter Verwendung von `setInterval` oder `requestAnimationFrame`.
    - Das Klonen von Elementen handhaben, um einen Endlosschleifen-Effekt zu erzeugen.
    - Anpassungen für Responsivität oder Pausen beim Hover vornehmen.
- **`recentlysoldproducts/recentlysoldproducts.js`**

  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Diese Datei könnte zusätzliches Front-Office-JavaScript enthalten, das spezifisch für die Initialisierung oder Interaktion des Moduls ist. Sie könnte verantwortlich sein für:
    - Das dynamische Laden des Slider-Inhalts (obwohl in diesem Modul wahrscheinlich von Smarty gerendert).
    - Das Einrichten von Event-Listenern (z.B. zum Anhalten des Sliders beim Maus-Hover).
    - Sicherstellen, dass der Slider nach dem Laden des DOM korrekt initialisiert wird.
    - Potenziell die Handhabung von AJAX, wenn das Modul Daten asynchron abrufen würde (obwohl dies nicht explizit durch die Modulstruktur angezeigt wird).

### 4.5 CSS-Stylesheets (`views/css/`)

- **`recentlysoldproducts/css.css`**

  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Dies ist wahrscheinlich das primäre Stylesheet für die Front-Office-Anzeige des Sliders. Es würde definieren:
    - Layout und Positionierung des Slider-Containers.
    - Grundlegendes Styling für die scrollenden Textelemente (z.B. `font-size`, `color`, `padding`).
    - Stile für den Hintergrund und die Rahmen basierend auf der Modulkonfiguration.
    - Potenziell responsive Anpassungen für verschiedene Bildschirmgrößen.
    - Wichtige Selektoren: `.recentlysoldproducts_block`, `.recentlysoldproducts_item`, etc.
- **`recentlysoldproducts/recentlysoldproducts.css`**

  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Diese Datei könnte zusätzliche oder spezifische Styling-Regeln enthalten, möglicherweise für fortgeschrittenere visuelle Effekte oder um Standard-Theme-Stile zu überschreiben. Angesichts der Benennung könnte es sich auch um eine redundante oder veraltete Datei handeln oder spezifischere Stile für den Scroll-Mechanismus selbst enthalten, die sich vom allgemeinen Block-Styling in `css.css` unterscheiden. Entwickler sollten auf überlappende Regeln und potenzielle Konflikte achten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`recentlysoldproducts/views/front/rsps.tpl`**
  - **Geltungsbereich:** Front-Office (Hook-Template).
  - **Beschreibung:** Dies ist die Haupt-Template-Datei, die für das Rendern der HTML-Struktur des Sliders für kürzlich verkaufte Produkte verantwortlich ist.
  - **Gerendert in Hooks:** `rightColumn`, `displayrightColumn`, `home`, `top`, `displayleftColumn`, `footer`, `displayhome`, `displayheader`, `displaytop`, `displayfooter`, `header`, `leftColumn`.
  - **Inhalt:** Es empfängt Daten (z.B. eine Liste der kürzlich verkauften Produkte, Modulkonfigurationseinstellungen) von den `hookDisplay*`-Methoden in `recentlysoldproducts.php`. Es iteriert dann durch die Produktliste, um den scrollenden Text zu generieren, wobei Inline-Stile oder Klassen basierend auf den Konfigurationseinstellungen des Moduls (Farben, Schriftgrößen, Abstände usw.) angewendet werden. Es enthält den Haupt-HTML-Wrapper für den Slider und die einzelnen Produkteinträge.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`. Die verwendeten Schlüssel sind:
    - `RSPS_C_BG`
    - `RSPS_C_BORDER`
    - `RSPS_C_FONT`
    - `RSPS_S_PADDING`
    - `RSPS_S_FONT`
    - `RSPS_S_BORDER`
    - `RSPS_M_DIR`
    - `RSPS_M_DELAY`
    - `RSPS_POSITION`
    - `RSPS_NB`
    - `RSPS_ORDER`
    - `RSPS_DIVERSITY`
  - Es fragt vorhandene PrestaShop-Tabellen ab, hauptsächlich `ps_orders`, `ps_order_detail`, `ps_product_lang` und `ps_product`, um Informationen über kürzlich verkaufte Produkte abzurufen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt & Ort | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Registriert CSS/JS-Assets und rendert möglicherweise ein verstecktes Element für die JS-Initialisierung. |
| `header` | Alias für `displayHeader` in älteren PrestaShop-Versionen. | Gleich wie `displayHeader`. |
| `displayHome` | Auf der Startseite, normalerweise im Hauptinhaltsbereich. | Rendert den Slider-Block auf der Startseite des Shops. |
| `home` | Alias für `displayHome` in älteren PrestaShop-Versionen. | Gleich wie `displayHome`. |
| `displayTop` | Im oberen Bereich der Seite, oft unterhalb des Headers. | Rendert den Slider-Block im oberen Inhaltsbereich. |
| `top` | Alias für `displayTop` in älteren PrestaShop-Versionen. | Gleich wie `displayTop`. |
| `displayLeftColumn` | In der linken Seitenleiste der entsprechenden Seiten. | Rendert den Slider-Block in der linken Spalte. |
| `leftColumn` | Alias für `displayLeftColumn` in älteren PrestaShop-Versionen. | Gleich wie `displayLeftColumn`. |
| `displayRightColumn` | In der rechten Seitenleiste der entsprechenden Seiten. | Rendert den Slider-Block in der rechten Spalte. |
| `rightColumn` | Alias für `displayRightColumn` in älteren PrestaShop-Versionen. | Gleich wie `displayRightColumn`. |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Rendert den Slider-Block im Footer. |
| `footer` | Alias für `displayFooter` in älteren PrestaShop-Versionen. | Gleich wie `displayFooter`. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Slider für kürzlich verkaufte Produkte“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
