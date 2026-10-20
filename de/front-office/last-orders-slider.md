---
title: "Last orders slider – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Last orders slider von MyPresta.eu."
sidebar:
  label: "Last orders slider – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Last orders slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/last-orders-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/last-orders-slider/)
>
> ---


# Last orders slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.6+, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten PrestaShop-kompatiblen Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Last orders slider“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren und neben dem Modul „Last orders slider“ auf „Konfigurieren“ klicken.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt steuert das grundlegende Verhalten und Aussehen Ihres Bestell-Sliders.
- **Auswirkung der Änderung dieser Einstellung:** Die Anpassung dieser Einstellungen wirkt sich direkt darauf aus, wie der Slider aussieht, wo er erscheint und welche Informationen er Ihren Kunden anzeigt.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Modul aktivieren** | Schaltet die gesamte Slider-Funktionalität ein oder aus. | *Wenn aktiviert:* Der Slider erscheint in Ihrem Front Office basierend auf anderen Einstellungen. *Wenn deaktiviert:* Der Slider ist für Kunden nicht sichtbar. | JA | Sie möchten den Slider vorübergehend für Wartungsarbeiten oder eine spezielle Kampagne ausblenden. |
| **Anzahl der anzuzeigenden Bestellungen** | Bestimmt, wie viele aktuelle Bestellungen der Slider durchläuft. | *Wenn auf 5 gesetzt:* Der Slider zeigt Informationen für die 5 neuesten Bestellungen an. *Wenn auf 10 gesetzt:* Er zeigt 10 an. | 5-10 (abhängig vom Bestellvolumen) | Wenn Sie ein sehr hohes Bestellvolumen haben, könnte die Anzeige von mehr überwältigend sein. Wenn Sie weniger Bestellungen haben, stellt die Anzeige von mehr sicher, dass immer Inhalte vorhanden sind. |
| **Bestellstatus zur Anzeige** | Wählt aus, welche Bestellstatus (z. B. „Zahlung akzeptiert“, „Geliefert“) als „aktuelle Bestellungen“ für den Slider gelten. | *Wenn „Zahlung akzeptiert“ ausgewählt ist:* Nur Bestellungen, die diesen Status erreicht haben, werden angezeigt. *Wenn „Storniert“ ausgewählt ist:* Stornierte Bestellungen könnten erscheinen (nicht empfohlen für Social Proof). | „Zahlung akzeptiert“, „In Bearbeitung“, „Geliefert“ | Sie möchten nur Bestellungen anzeigen, die bestätigt und bearbeitet werden oder erfolgreich geliefert wurden, um positives Vertrauen aufzubauen. |
| **Kundennamen anzeigen** | Steuert, ob der Vorname und der erste Buchstabe des Nachnamens des Kunden angezeigt werden. | *Wenn aktiviert:* „John D. aus New York…“ *Wenn deaktiviert:* „Jemand aus New York…“ | JA | Die Anzeige eines Teilnamens verleiht eine persönliche Note und lässt die Bestellungen realer wirken, was den Social Proof verbessert. |
| **Kundenstadt anzeigen** | Steuert, ob die Stadt des Kunden angezeigt wird. | *Wenn aktiviert:* „…aus New York hat gerade gekauft…“ *Wenn deaktiviert:* „…hat gerade eine Bestellung aufgegeben.“ | JA | Die Anzeige der Stadt fügt eine Ebene der Authentizität hinzu und kann bei lokalen Kunden Anklang finden. |
| **Produktnamen anzeigen** | Steuert, ob der Name des gekauften Produkts angezeigt wird. | *Wenn aktiviert:* „…hat gerade ein T-Shirt gekauft.“ *Wenn deaktiviert:* „…hat gerade eine Bestellung aufgegeben.“ | JA | Die Anzeige des Produktnamens macht den Kauf greifbarer und kann beliebte Artikel hervorheben. |
| **Produktbild anzeigen** | Steuert, ob ein kleines Bild des gekauften Produkts angezeigt wird. | *Wenn aktiviert:* Ein kleines Vorschaubild des Produkts erscheint neben dem Text. *Wenn deaktiviert:* Nur Text wird angezeigt. | JA | Visuelle Elemente sind ansprechend. Ein Produktbild macht den Slider attraktiver und informativer. |
| **Animationsgeschwindigkeit (Millisekunden)** | Legt fest, wie schnell der Slider zwischen verschiedenen Bestellungen wechselt. | *Niedrigerer Wert (z. B. 3000):* Schnellere Übergänge, Bestellungen wechseln alle 3 Sekunden. *Höherer Wert (z. B. 8000):* Langsamere Übergänge, Bestellungen wechseln alle 8 Sekunden. | 5000 (5 Sekunden) | Eine moderate Geschwindigkeit hält den Slider dynamisch, ohne zu schnell zum Lesen oder zu langsam zum Aktualisieren zu sein. |
| **Textfarbe** | Legt die Farbe des im Slider angezeigten Textes fest. | *Wenn auf #000000 (schwarz) gesetzt:* Der Text ist schwarz. *Wenn auf #FF0000 (rot) gesetzt:* Der Text ist rot. | #FFFFFF (weiß) oder eine Farbe, die mit Ihrem Hintergrund kontrastiert | Wählen Sie eine Farbe, die sich von Ihrer gewählten Hintergrundfarbe abhebt und zur Ästhetik Ihrer Marke passt. |
| **Hintergrundfarbe** | Legt die Hintergrundfarbe der Slider-Leiste fest. | *Wenn auf #FFFFFF (weiß) gesetzt:* Der Slider-Hintergrund ist weiß. *Wenn auf #000000 (schwarz) gesetzt:* Der Slider-Hintergrund ist schwarz. | #000000 (schwarz) oder eine Farbe, die mit Ihrem Thema kontrastiert | Wählen Sie eine Farbe, die den Slider sichtbar macht und das Design Ihres Shops ergänzt. |
| **Hook zum Anzeigen des Sliders** | Wählt aus, wo in Ihrem PrestaShop-Theme der Slider erscheinen soll. | *Wenn „displayTop“ ausgewählt ist:* Der Slider erscheint nahe dem oberen Rand Ihres Shops. *Wenn „displayFooter“ ausgewählt ist:* Der Slider erscheint am unteren Rand. | `displayTop` oder `displayNavFullWidth` | Wählen Sie einen prominenten Ort, an dem Kunden ihn leicht sehen können, ohne wichtige Inhalte zu verdecken. |

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren | JA | Schaltet den Slider ein/aus. |
| Modulkonfiguration | Anzahl der anzuzeigenden Bestellungen | 5-10 | Steuert, wie viele aktuelle Bestellungen angezeigt werden. |
| Modulkonfiguration | Bestellstatus zur Anzeige | Zahlung akzeptiert, In Bearbeitung, Geliefert | Filtert Bestellungen nach ihrem Status zur Anzeige. |
| Modulkonfiguration | Kundennamen anzeigen | JA | Zeigt den Vornamen und den ersten Buchstaben des Nachnamens des Kunden an. |
| Modulkonfiguration | Kundenstadt anzeigen | JA | Zeigt die Stadt des Kunden an. |
| Modulkonfiguration | Produktnamen anzeigen | JA | Zeigt den Namen des gekauften Produkts an. |
| Modulkonfiguration | Produktbild anzeigen | JA | Zeigt ein kleines Bild des gekauften Produkts an. |
| Modulkonfiguration | Animationsgeschwindigkeit (Millisekunden) | 5000 | Legt die Übergangsgeschwindigkeit zwischen Bestellungen fest. |
| Modulkonfiguration | Textfarbe | #FFFFFF (weiß) | Definiert die Farbe des Textes im Slider. |
| Modulkonfiguration | Hintergrundfarbe | #000000 (schwarz) | Definiert die Hintergrundfarbe des Sliders. |
| Modulkonfiguration | Hook zum Anzeigen des Sliders | `displayTop` / `displayNavFullWidth` | Bestimmt die Position des Sliders in Ihrem Theme. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Slider wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A:

- **Modulstatus prüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Last orders slider“ installiert und aktiviert ist.
- **Hook-Auswahl überprüfen:** Überprüfen Sie in der Modulkonfiguration, ob Sie einen gültigen „Hook zum Anzeigen des Sliders“ ausgewählt haben (z. B. `displayTop`, `displayNavFullWidth`). Einige Hooks sind möglicherweise nicht in allen Themes vorhanden oder aktiv.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindert der PrestaShop-Cache, dass neue Inhalte sofort angezeigt werden.
- **Bestellstatus prüfen:** Stellen Sie sicher, dass Sie mindestens einen „Bestellstatus zur Anzeige“ ausgewählt haben, dem aktuelle Bestellungen zugeordnet sind. Wenn keine Bestellungen den ausgewählten Status entsprechen, ist der Slider leer.
- **Theme-Kompatibilität:** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, können sehr stark angepasste Themes geringfügige Anpassungen erfordern. Wenn alles andere fehlschlägt, kontaktieren Sie den MyPresta.eu-Support.

**F2: Der Slider wird angezeigt, aber die Farben passen nicht zu meinem Theme.**
A:

- **Farben in der Konfiguration anpassen:** Gehen Sie zur Konfigurationsseite des Moduls. Verwenden Sie die Einstellungen „Textfarbe“ und „Hintergrundfarbe“, um Farben auszuwählen, die das Design Ihres Shops ergänzen. Sie können ein Farbwahl-Tool (online oder als Browser-Erweiterung verfügbar) verwenden, um die genauen Hex-Codes aus Ihrem Theme zu finden.
- **Benutzerdefiniertes CSS (Fortgeschritten):** Wenn die Farboptionen des Moduls nicht ausreichen, kann Ihr Webmaster benutzerdefinierte CSS-Regeln zu Ihrem Theme-Stylesheet hinzufügen, um die Standardstile des Moduls zu überschreiben. (Siehe Abschnitt 7.5 für Entwicklerdetails).

**F3: Der Slider ist leer oder wird nicht mit neuen Bestellungen aktualisiert.**
A:

- **Bestellstatus:** Stellen Sie sicher, dass die Einstellung „Bestellstatus zur Anzeige“ die Status Ihrer neuesten Bestellungen enthält (z. B. „Zahlung akzeptiert“, „Geliefert“). Wenn Ihre neuesten Bestellungen einen nicht ausgewählten Status haben, werden sie nicht angezeigt.
- **Aktuelle Bestellungen:** Das Modul zeigt *aktuelle* Bestellungen an. Wenn Ihr Shop seit einiger Zeit keine Bestellungen hatte oder wenn die „Anzahl der anzuzeigenden Bestellungen“ zu niedrig eingestellt ist, kann er leer erscheinen.
- **Cache:** Auch hier kann das Leeren Ihres PrestaShop-Caches (**Erweiterte Einstellungen > Performance**) dazu beitragen, dass das Modul die neuesten Daten abruft.

**F4: Wie übersetze ich den Text im Slider in andere Sprachen?**
A:

- **PrestaShop-Übersetzungstool:** Gehen Sie zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann Ihre Sprache.
- Suchen Sie das Modul „Last orders slider“ in der Liste. Sie können alle fest codierten Zeichenfolgen (wie „hat gerade gekauft“ oder „aus“), die das Modul verwendet, übersetzen.
- **Dynamischer Inhalt:** Kundennamen, Städte und Produktnamen werden direkt aus den Daten Ihres Shops abgerufen und erscheinen in der Sprache, in der sie eingegeben oder in Ihrem Produktkatalog konfiguriert wurden.

**F5: Der Slider ist zu schnell/langsam oder zeigt zu viele/wenige Bestellungen an.**
A:

- **Animationsgeschwindigkeit:** Passen Sie die Einstellung „Animationsgeschwindigkeit (Millisekunden)“ in der Modulkonfiguration an. Eine höhere Zahl bedeutet langsamere Übergänge.
- **Anzahl der Bestellungen:** Ändern Sie die Einstellung „Anzahl der anzuzeigenden Bestellungen“, um zu steuern, wie viele einzelne Bestellungen durchlaufen werden. Experimentieren Sie mit diesen Werten, um die perfekte Balance für den Traffic und das Bestellvolumen Ihres Shops zu finden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Einblick in das Modul „Last orders slider“, der für Entwickler, Webmaster und technische Agenturen gedacht ist.

### 4.1 Architekturübersicht

Das Modul „Last orders slider“ (`lastord`) ist ein Standard-PrestaShop-Modul, das hauptsächlich zur Anzeige dynamischer Inhalte im Front Office entwickelt wurde. Es nutzt das Hook-System von PrestaShop, um seine Inhalte in verschiedene Teile des Themes einzufügen. Die Kernlogik befindet sich in der Hauptmoduldatei (`index.php`), die die Konfiguration, Datenabfrage und Template-Rendering verwaltet. Es führt keine benutzerdefinierten Controller oder komplexen ObjectModels ein, sondern verlässt sich stattdessen auf direkte Datenbankabfragen (über `Db::getInstance()`), um Bestelldaten abzurufen, und Smarty-Templates für die Präsentation. Das Styling wird über eine dedizierte CSS-Datei verwaltet.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` innerhalb der Hauptmoduldatei gehandhabt, und das Front-Office-Rendering erfolgt direkt über Hook-Methoden.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/`. Die gesamte Datenabfrage und Geschäftslogik ist in der Klasse `Lastord` in `index.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Die Animations- und Slider-Funktionalität wird wahrscheinlich entweder durch CSS-Animationen oder ein sehr leichtes, Inline-Skript innerhalb des Templates oder durch eine bereits von PrestaShop geladene Drittanbieterbibliothek gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`lastord/views/css/lastord.css`**
  - **Umfang:** Front-Office-Kundenstyling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet ist für das visuelle Erscheinungsbild der Bestell-Slider-Leiste selbst verantwortlich, einschließlich ihrer Positionierung, des Hintergrunds, der Textstile und möglicherweise der Animationseigenschaften.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:**
    - `.lastord_wrapper`: Der Hauptcontainer für den gesamten Slider.
    - `.lastord_item`: Einzelnes Bestellelement innerhalb des Sliders.
    - `.lastord_text`: Der Textinhalt (Kunde, Produkt, Stadt).
    - `.lastord_image`: Der Produktbildcontainer.
    - `@keyframes`-Regeln (falls für die Animation definiert).
      Entwickler können diese Selektoren in der `custom.css` oder `theme.css` ihres Themes überschreiben, um ihren spezifischen Designanforderungen zu entsprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - **`lastord/views/templates/hook/lo_orders.tpl`**
    - **Hook:** Dies ist das primäre Template, das von den `hook`-Methoden des Moduls (z. B. `hookDisplayTop`, `hookDisplayNavFullWidth`, `hookDisplayFooter` usw.) gerendert wird.
    - **Zweck:** Es enthält die HTML-Struktur für den Slider-Wrapper und iteriert über die Variable `$orders` (die von der PHP-Logik des Moduls übergeben wird), um jede aktuelle Bestellung anzuzeigen. Es enthält bedingte Logik zum Anzeigen/Ausblenden von Kundennamen, Stadt, Produktnamen und Bild basierend auf der Modulkonfiguration. Es wendet auch Inline-Stile für Text- und Hintergrundfarben an.
  - **`lastord/views/templates/hook/displayBanner.tpl`**
    - **Hook:** `displayBanner`
    - **Zweck:** Dieses Template dient wahrscheinlich als Wrapper oder direkter Einbindungspunkt für `lo_orders.tpl`, wenn das Modul an `displayBanner` gehookt ist. Es stellt sicher, dass der Slider-Inhalt in diesem spezifischen Hook korrekt gerendert wird.
  - **`lastord/views/templates/hook/displayNavFullWidth.tpl`**
    - **Hook:** `displayNavFullWidth`
    - **Zweck:** Ähnlich wie `displayBanner.tpl` wird dieses Template verwendet, um den Inhalt von `lo_orders.tpl` zu rendern, wenn das Modul an `displayNavFullWidth` gehookt ist.
  - **`lastord/views/templates/hook/displayTop.tpl`**
    - **Hook:** `displayTop`
    - **Zweck:** Dieses Template wird verwendet, um den Inhalt von `lo_orders.tpl` zu rendern, wenn das Modul an `displayTop` gehookt ist.
- **Admin-Templates (`views/templates/admin/`)**:

  - **`lastord/views/templates/admin/orderstates.tpl`**
    - **Zweck:** Dieses Template wird innerhalb der `getContent()`-Methode des Moduls verwendet, um die Liste der Bestellstatus-Kontrollkästchen auf der Back-Office-Konfigurationsseite zu rendern. Es iteriert durch die verfügbaren Bestellstatus und zeigt sie mit ihrem aktuellen Auswahlstatus an.
- **Front-Office-Templates (`views/templates/front/`)**: Keine identifiziert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `LASTORD_ENABLED`, `LASTORD_ORDERS_COUNT`, `LASTORD_ORDER_STATES`, `LASTORD_DISPLAY_NAME`, `LASTORD_DISPLAY_CITY`, `LASTORD_DISPLAY_PRODUCT`, `LASTORD_DISPLAY_IMAGE`, `LASTORD_ANIMATION_SPEED`, `LASTORD_TEXT_COLOR`, `LASTORD_BACKGROUND_COLOR`, `LASTORD_HOOK`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich des Front Office. | Wird verwendet, um Assets (CSS) und potenziell Inline-JavaScript zu registrieren. |
| `displayTop` | Typischerweise ganz oben auf der Seite, unterhalb des Headers. | Rendert den Slider an einer prominenten oberen Position. |
| `displayNavFullWidth` | Oft ein vollbreiter Bereich über oder unter der Hauptnavigation. | Rendert den Slider in einem vollbreiten Navigationsbereich. |
| `displayBanner` | Ein gängiger Hook für Banner, oft ganz oben. | Rendert den Slider als Banner. |
| `displayLeftColumn` | In der linken Seitenleiste. | Rendert den Slider in der linken Spalte. |
| `displayRightColumn` | In der rechten Seitenleiste. | Rendert den Slider in der rechten Spalte. |
| `displayFooter` | Im Footer-Bereich der Seite. | Rendert den Slider am unteren Rand der Seite. |
| `displayProductButtons` | Auf der Produktseite, nahe dem „In den Warenkorb“-Button. | Rendert den Slider auf der Produktseite zur Konversionsfokussierung. |
| `displayFooterProduct` | Im Footer-Bereich der Produktseite. | Rendert den Slider am unteren Rand der Produktseite. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Last orders slider“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität und Integration des Moduls gerne zur Verfügung.
