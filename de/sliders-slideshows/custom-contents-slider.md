---
title: "Custom contents slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Custom contents slider von MyPresta.eu."
sidebar:
  label: "Custom contents slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Custom contents slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/custom-contents-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/custom-contents-slider/)
>
> ---


# Custom contents slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Einstellungen für das Modul „Custom contents slider“. Hier definieren Sie den Inhalt, das Aussehen und das Verhalten Ihrer Slider.

Die Konfigurationsseite wird von der Bibliothek `SmartyTemplatesManager` betrieben, die es Ihnen ermöglicht, mehrere benutzerdefinierte Inhaltsblöcke zu erstellen und zu verwalten.

#### **Hauptformular (mainForm.tpl)**

Dieser Abschnitt bietet eine Übersicht über Ihre vorhandenen Slider und ermöglicht es Ihnen, neue hinzuzufügen.

- **Was dieser Abschnitt leistet:** Zeigt eine Liste aller von Ihnen erstellten benutzerdefinierten Inhalts-Slider an. Jeder Eintrag zeigt grundlegende Informationen wie den Namen, die Position und den Status des Sliders.
- **Auswirkung der Änderung dieses Abschnitts:** Von hier aus können Sie schnell sehen, welche Slider aktiv sind und wo sie angezeigt werden. Sie können auch klicken, um vorhandene Slider zu bearbeiten oder neue hinzuzufügen.
- **Empfohlene Aktion:** Überprüfen Sie Ihre vorhandenen Slider. Wenn Sie zum ersten Mal einrichten, sollten Sie auf die Schaltfläche „Neues Template hinzufügen“ klicken.

#### **Template erstellen/bearbeiten Formular (createTemplateForm.tpl / editTemplateForm.tpl)**

Wenn Sie auf „Neues Template hinzufügen“ klicken oder einen vorhandenen Slider „Bearbeiten“, gelangen Sie zu einem Formular, in dem Sie alle Details für diesen spezifischen Slider definieren.

- **Template-Name:**

  - **Was diese Einstellung leistet:** Dies ist ein interner Name für Ihren Slider, der nur im Back Office sichtbar ist. Er hilft Ihnen, verschiedene Slider zu identifizieren.
  - **Auswirkung der Änderung dieser Einstellung:** Eine Änderung wirkt sich nur darauf aus, wie Sie es im Admin-Panel sehen; es hat keine Auswirkungen auf das Front Office.
  - **Empfohlener Wert:** Ein beschreibender Name, z.B. „Sommer-Sale Linker Slider“, „Newsletter-Anmeldung Unten“.
  - **Händlerszenario / Beispiel:** Wenn Sie mehrere Aktionen haben, hilft eine klare Benennung bei der Verwaltung.
- **Template-Inhalt:**

  - **Was diese Einstellung leistet:** Dies ist der Kern Ihres Sliders. Sie können hier beliebigen HTML-, Text- oder sogar Smarty-Code eingeben. Dieser Inhalt wird im gleitenden Panel angezeigt.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ändert direkt, was Ihre Kunden sehen, wenn der Slider erweitert wird. Sie können Bilder, Links, Absätze, Formulare usw. einfügen.
  - **Empfohlener Wert:** Verwenden Sie Standard-HTML. Halten Sie es prägnant und visuell ansprechend. Verwenden Sie für Bilder absolute URLs oder den PrestaShop-Bildhelfer.
  - **Händlerszenario / Beispiel:**

    ```
    <h3>Zeitlich begrenztes Angebot!</h3><p>Erhalten Sie <strong>15% RABATT</strong> auf alle Artikel der Sommerkollektion!</p><a href="{$link->getPageLink('category', true, null, ['id\_category' => 123])}" class="button btn btn-primary">Jetzt einkaufen!</a>
    ```

    (Hinweis: Smarty-Variablen wie `{$link->getPageLink(...)` erfordern, dass die Smarty-Verarbeitung für den Inhalt aktiviert ist, was dieses Modul unterstützt.)
- **Position:**

  - **Was diese Einstellung leistet:** Bestimmt, wo der Slider auf dem Bildschirm des Kunden erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Links:* Der Slider erscheint von der linken Kante.
    - *Rechts:* Der Slider erscheint von der rechten Kante.
    - *Unten:* Der Slider erscheint vom unteren Rand.
  - **Empfohlener Wert:** Wählen Sie basierend auf Ihrem Design und anderen Elementen auf Ihrer Seite. Rechts und Unten sind oft weniger aufdringlich als Links.
  - **Händlerszenario / Beispiel:** Verwenden Sie „Rechts“ für ein schnelles Kontaktformular, „Unten“ für ein Cookie-Zustimmungsbanner oder „Links“ für einen speziellen Rabattcode.
- **Öffnen bei:**

  - **Was diese Einstellung leistet:** Definiert, wie der Slider erweitert wird, um seinen Inhalt anzuzeigen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Klick:* Der Slider wird nur erweitert, wenn der Kunde auf seinen Trigger-Tab klickt.
    - *Hover:* Der Slider wird erweitert, wenn der Kunde den Mauszeiger über seinen Trigger-Tab bewegt.
  - **Empfohlener Wert:** „Klick“ ist im Allgemeinen weniger aufdringlich und verhindert versehentliches Öffnen. „Hover“ kann gut für sehr subtile, schnelle Einblicke sein.
  - **Händlerszenario / Beispiel:** Für wichtige Ankündigungen oder Formulare ist „Klick“ besser. Für einen schnellen „Hallo, wie kann ich helfen?“-Chat-Button könnte „Hover“ funktionieren.
- **Aktiv:**

  - **Was diese Einstellung leistet:** Schaltet um, ob dieser spezifische Slider im Front Office sichtbar und aktiv ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert (Ja):* Der Slider erscheint in Ihrem Shop gemäß seinen Einstellungen.
    - *Deaktiviert (Nein):* Der Slider wird in Ihrem Shop ausgeblendet, aber seine Konfiguration wird gespeichert.
  - **Empfohlener Wert:** „Ja“ für aktive Slider, „Nein“ für Slider, die Sie vorübergehend ausblenden oder an denen Sie noch arbeiten möchten.
  - **Händlerszenario / Beispiel:** Sie könnten einen Weihnachtsaktions-Slider nach den Feiertagen deaktivieren und ihn im nächsten Jahr wieder aktivieren.

#### **Button-Manager (buttonManager.tpl)**

Dieser Abschnitt ist Teil des `SmartyTemplatesManager` und ermöglicht es Ihnen, die Schaltflächen oder Trigger für Ihre Slider zu verwalten. Während das Modul hauptsächlich die Einstellung „Öffnen bei“ verwendet, könnte dieser Abschnitt zusätzliche Anpassungsmöglichkeiten für den visuellen Trigger selbst bieten.

- **Was dieser Abschnitt leistet:** Bietet Optionen zur Anpassung des Aussehens des Tabs oder Buttons, mit dem Kunden interagieren, um den Slider zu öffnen. Dies kann Text, Symbole oder grundlegendes Styling umfassen.
- **Auswirkung der Änderung dieses Abschnitts:** Ändert das visuelle Erscheinungsbild des Slider-Triggers im Front Office.
- **Empfohlener Wert:** Halten Sie den Trigger klar und einladend. Verwenden Sie prägnanten Text oder ein relevantes Symbol.
- **Händlerszenario / Beispiel:** Sie könnten den Button-Text auf „Sale!“, „Kontaktieren Sie uns“ setzen oder ein kleines Chat-Symbol verwenden.

#### **Select-Eingabe (selectInput.tpl)**

Dies ist ein generisches Template für Dropdown-Auswahlen innerhalb des `SmartyTemplatesManager`. Es wird für Einstellungen wie „Position“ und „Öffnen bei“ verwendet.

- **Was dieser Abschnitt leistet:** Präsentiert eine Dropdown-Liste vordefinierter Optionen für eine bestimmte Einstellung.
- **Auswirkung der Änderung dieses Abschnitts:** Ermöglicht Ihnen die Auswahl aus einer begrenzten Anzahl von Optionen für eine gegebene Konfiguration.
- **Empfohlener Wert:** Wählen Sie die Option, die am besten zu Ihrem gewünschten Slider-Verhalten passt.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptformular | (Liste der Slider) | N/A | Übersicht aller erstellten Slider; ermöglicht Hinzufügen/Bearbeiten. |
| Template erstellen/bearbeiten | **Template-Name** | Beschreibender Name | Interner Bezeichner für den Slider im Back Office. |
| Template erstellen/bearbeiten | **Template-Inhalt** | Benutzerdefiniertes HTML/Text | Der tatsächliche Inhalt, der im Slider angezeigt wird. |
| Template erstellen/bearbeiten | **Position** | Rechts / Unten | Wo der Slider auf dem Bildschirm erscheint (Links, Rechts, Unten). |
| Template erstellen/bearbeiten | **Öffnen bei** | Klick | Wie der Slider erweitert wird (Klick oder Hover). |
| Template erstellen/bearbeiten | **Aktiv** | Ja | Schaltet die Sichtbarkeit des Sliders im Front Office um. |
| Button-Manager | (Button-Optionen) | N/A | Passt den visuellen Trigger für den Slider an (Text, Symbol, Stil). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Slider wird im Front Office nicht angezeigt. Was soll ich überprüfen?**
A:

1. **Ist der Slider „Aktiv“?** Gehen Sie zur Modulkonfiguration, bearbeiten Sie Ihren Slider und stellen Sie sicher, dass die Einstellung „Aktiv“ auf „Ja“ gesetzt ist.
2. **Ist der Inhalt gültig?** Stellen Sie sicher, dass in Ihrem „Template-Inhalt“ keine ungeschlossenen HTML-Tags oder JavaScript-Fehler vorhanden sind, die die Anzeige stören könnten.
3. **Leeren Sie Ihren Cache:** Gehen Sie im PrestaShop-Back Office zu **Erweiterte Parameter > Leistung** und leeren Sie den Smarty-Cache (und optional den gesamten Cache).
4. **Suchen Sie nach Konflikten:** Deaktivieren Sie vorübergehend andere Module, die möglicherweise schwebende Elemente hinzufügen oder das Seitenlayout ändern, um festzustellen, ob ein Konflikt vorliegt.

**F: Der Slider erscheint, aber das Styling sieht seltsam aus oder passt nicht zu meinem Theme.**
A:

1. **Standard-CSS des Moduls:** Das Modul wird mit eigenem CSS geliefert. Das CSS Ihres Themes könnte es überschreiben oder umgekehrt.
2. **Benutzerdefiniertes Theme-Styling:** Möglicherweise müssen Sie benutzerdefinierte CSS-Regeln zu Ihrem Theme-Stylesheet hinzufügen, um das Aussehen des Sliders anzupassen. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Slider-Elemente zu überprüfen und die CSS-Klassen zu identifizieren, die Sie ansprechen müssen.
3. **Inhalts-Styling:** Wenn Sie reines HTML in den „Template-Inhalt“ einfügen, stellen Sie sicher, dass Sie geeignete Klassen oder Inline-Styles verwenden, die mit Ihrem Theme funktionieren.

**F: Kann ich mehrere Slider gleichzeitig aktiv haben?**
A: Ja, das Modul unterstützt mehrere Slider. Achten Sie jedoch auf die Benutzerfreundlichkeit. Zu viele Slider (z.B. einer links, einer rechts und einer unten) können die Benutzeroberfläche überladen und Kunden überfordern. Es ist im Allgemeinen am besten, ein oder zwei strategisch einzusetzen.

**F: Wie füge ich Bilder oder Links zu meinem Slider-Inhalt hinzu?**
A: Sie können Standard-HTML-Tags im Feld „Template-Inhalt“ verwenden:

- **Bilder:** `<img src="ihr_bild_url.jpg" alt="Beschreibung" style="width:100px;">` (Verwenden Sie absolute URLs für Bilder).
- **Links:** `<a href="ihre_seite_url.html">Hier klicken</a>` (Sie können auch Smarty-Variablen für PrestaShop-Links verwenden, z.B. `<a href="{$link->getPageLink('contact')}">Kontaktieren Sie uns</a>`).

**F: Funktioniert es mit Mehrsprachigkeit und Multi-Store?**
A: Ja, das Modul ist so konzipiert, dass es in mehrsprachigen und Multi-Store-Umgebungen korrekt funktioniert. Sie können verschiedene Slider oder verschiedene Inhalte für denselben Slider für jede Sprache und jeden Shop erstellen, was eine hochgradig zielgerichtete Nachrichtenübermittlung ermöglicht.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Custom contents slider“ (`saslider`) ist als Standard-PrestaShop-Modul aufgebaut und nutzt hauptsächlich die `Module`-Klasse für seinen Lebenszyklus und `SmartyTemplatesManager` für die dynamische Inhaltserstellung und -verwaltung. Es integriert sich in das Hook-System von PrestaShop, um seine Front-Office-Assets und Inhalte einzuschleusen. Die Kernlogik des Moduls befindet sich in seiner Hauptdatei `index.php` und verwaltet Konfiguration, Installation und Front-Office-Rendering. Es verwendet keine dedizierten Front- oder Admin-Controller, sondern verlässt sich auf die Methode `getContent()` für seine Back-Office-Konfiguration und die direkte Hook-Registrierung für die Front-Office-Anzeige.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das gesamte Front-Office-Rendering wird direkt über registrierte Hooks innerhalb der Hauptmoduldatei abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Back-Office-Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen, die `ObjectModel` erweitern. Die primäre Datenspeicherung für Slider-Konfigurationen erfolgt wahrscheinlich über `Configuration::updateValue()` für modulweite Einstellungen und potenziell serialisierte Daten, die in `ps_configuration` für individuelle Slider-Inhalte und -Eigenschaften gespeichert werden, verwaltet von der `SmartyTemplatesManager`-Bibliothek.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, die hauptsächlich für die gleitende Animation und die Interaktionslogik (Klick/Hover) für verschiedene Slider-Positionen verantwortlich sind.

- `saslider/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`

  - **Umfang**: Back-Office.
  - **Verantwortlichkeit**: Dieses Skript ist Teil der `SmartyTemplatesManager`-Bibliothek. Es verwaltet wahrscheinlich die dynamische Erstellung, Bearbeitung und Verwaltung von Templates (Slidern) innerhalb der Konfigurationsoberfläche des Moduls. Es könnte Formularübermittlungen, AJAX-Aufrufe zum Speichern/Laden von Inhalten und UI-Interaktionen für das Template-Managementsystem verwalten.
- `saslider/views/js/saslider-click-bottom.js`

  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Implementiert die JavaScript-Logik für einen unten positionierten Slider, der sich bei einem Klickereignis erweitert/zusammenklappt. Es bindet Klick-Listener an das Trigger-Element des Sliders, schaltet CSS-Klassen um oder manipuliert direkt `style`-Eigenschaften, um die Erweiterung und Kontraktion des Sliders zu animieren.
- `saslider/views/js/saslider-click-left.js`

  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Ähnlich wie `saslider-click-bottom.js`, aber speziell für einen links positionierten Slider, der dessen klickbasierte Erweiterung/Kontraktion handhabt.
- `saslider/views/js/saslider-click-right.js`

  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Ähnlich wie `saslider-click-bottom.js`, aber speziell für einen rechts positionierten Slider, der dessen klickbasierte Erweiterung/Kontraktion handhabt.
- `saslider/views/js/saslider-hover-bottom.js`

  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Implementiert die JavaScript-Logik für einen unten positionierten Slider, der sich bei einem Hover-Ereignis erweitert/zusammenklappt. Es bindet `mouseenter`- und `mouseleave`-Listener an das Trigger-Element des Sliders, um dessen Sichtbarkeit und Position umzuschalten.
- `saslider/views/js/saslider-hover-left.js`

  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Ähnlich wie `saslider-hover-bottom.js`, aber speziell für einen links positionierten Slider, der dessen hoverbasierte Erweiterung/Kontraktion handhabt.
- `saslider/views/js/saslider-hover-right.js`

  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Ähnlich wie `saslider-hover-bottom.js`, aber speziell für einen rechts positionierten Slider, der dessen hoverbasierte Erweiterung/Kontraktion handhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält mehrere CSS-Dateien sowohl für das Styling der Back-Office-Konfiguration als auch für das Erscheinungsbild des Front-Office-Sliders.

- `saslider/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`

  - **Umfang**: Styling des Back-Office-Admin-Formulars.
  - **Haupt-UI-Komponenten**: Stilelemente der `SmartyTemplatesManager`-Oberfläche, einschließlich Formularen, Schaltflächen, Eingabefeldern und potenziell Listentabellen zur Verwaltung von Templates.
  - **Wichtige CSS-Klassenselektoren**: Enthält wahrscheinlich Klassen für Formularlayouts, Eingabegruppen und allgemeine administrative UI-Komponenten.
- `saslider/views/css/saslider-bottom.css`

  - **Umfang**: Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten**: Definiert die spezifische Positionierung, den Anfangszustand (eingeklappt) und die Animationseigenschaften für den unten positionierten Slider.
  - **Wichtige CSS-Klassenselektoren**: `body #saslider_bottom`, `.saslider-bottom-tab`, `.saslider-bottom-content`, Klassen für `open`/`closed`-Zustände.
- `saslider/views/css/saslider-left.css`

  - **Umfang**: Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten**: Definiert die spezifische Positionierung, den Anfangszustand und die Animationseigenschaften für den links positionierten Slider.
  - **Wichtige CSS-Klassenselektoren**: `body #saslider_left`, `.saslider-left-tab`, `.saslider-left-content`, Klassen für `open`/`closed`-Zustände.
- `saslider/views/css/saslider-right.css`

  - **Umfang**: Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten**: Definiert die spezifische Positionierung, den Anfangszustand und die Animationseigenschaften für den rechts positionierten Slider.
  - **Wichtige CSS-Klassenselektoren**: `body #saslider_right`, `.saslider-right-tab`, `.saslider-right-content`, Klassen für `open`/`closed`-Zustände.
- `saslider/views/css/saslider.css`

  - **Umfang**: Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten**: Enthält allgemeine, gemeinsame Stile, die für alle Slider-Positionen gelten, wie z.B. Basis-Container-Stile, Schriftgrößen, Farben, z-Index und Übergangseigenschaften.
  - **Wichtige CSS-Klassenselektoren**: `.saslider-container`, `.saslider-tab`, `.saslider-content` und potenziell responsive Anpassungen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates sowohl für seine Back-Office-Konfigurationsoberfläche als auch für das Front-Office-Content-Rendering.

- **Admin-Templates (`saslider/lib/smartyTemplatesManager/views/`)**:

  - `buttonManager.tpl`: Rendert wahrscheinlich die Benutzeroberfläche zur Verwaltung des Slider-Trigger-Buttons/Tabs.
  - `createTemplateForm.tpl`: Das Formular-Template, das beim Erstellen eines neuen Sliders verwendet wird.
  - `editTemplateForm.tpl`: Das Formular-Template, das beim Bearbeiten eines vorhandenen Sliders verwendet wird.
  - `mainForm.tpl`: Das Hauptkonfigurationsseiten-Template, das wahrscheinlich alle Slider auflistet und die Schaltfläche „Neu hinzufügen“ bereitstellt.
  - `selectInput.tpl`: Ein wiederverwendbares Template zum Rendern von Dropdown-`<select>`-Elementen innerhalb der Admin-Formulare.
- **Hook-Templates (`saslider/views/`)**:

  - `footer-bottom.tpl`: Rendert die HTML-Struktur für einen unten positionierten Slider. Dieses Template ist wahrscheinlich in `displayFooter` oder einen ähnlichen globalen Hook eingehängt. Es enthält die Wrapper-`div`s für den Slider, seinen Trigger-Tab und den Inhaltsbereich.
  - `footer-left.tpl`: Rendert die HTML-Struktur für einen links positionierten Slider. Wahrscheinlich in `displayFooter` oder ähnliches eingehängt.
  - `footer-right.tpl`: Rendert die HTML-Struktur für einen rechts positionierten Slider. Wahrscheinlich in `displayFooter` oder ähnliches eingehängt.
- **Beispiel-/Dienstprogramm-Templates (`saslider/lib/smartyTemplatesManager/tpl/`)**:

  - `example.tpl`: Ein Beispiel-Template, möglicherweise zur Demonstration oder internen Prüfung des `SmartyTemplatesManager`.
  - `MyShortCode.tpl`: Deutet darauf hin, dass der `SmartyTemplatesManager` eine Form von Shortcode oder dynamischer Inhaltseinfügung unterstützen könnte.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul definiert keine expliziten benutzerdefinierten SQL-Tabellen über `install.sql`.
  - Die Konfiguration für einzelne Slider (Inhalt, Position, aktiver Status, Öffnen bei) wird in der Tabelle `ps_configuration` gespeichert, wahrscheinlich als serialisierte Daten unter spezifischen Konfigurationsschlüsseln, die von der `SmartyTemplatesManager`-Bibliothek verwaltet werden. Zum Beispiel `PS_SASLIDER_TEMPLATES` oder ähnliches.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS- und JavaScript-Assets (z.B. `saslider.css`, `saslider-click-right.js`) zu registrieren, die für die Front-Office-Anzeige und Funktionalität des Sliders erforderlich sind. |
| `displayFooter` | Am Ende des `<body>`-Bereichs jeder Seite, vor dem schließenden `</body>`-Tag. | Wird verwendet, um die tatsächliche HTML-Struktur des Sliders (z.B. `footer-bottom.tpl`, `footer-left.tpl`, `footer-right.tpl`) in die Seite zu rendern und sicherzustellen, dass er korrekt schwebt. |
| `displayLeftColumn` | In der linken Spalte des Shops. | *Potenziell* zur Anzeige des Sliders verwendet, obwohl `displayFooter` für schwebende Elemente üblicher ist. |
| `displayRightColumn` | In der rechten Spalte des Shops. | *Potenziell* zur Anzeige des Sliders verwendet, obwohl `displayFooter` für schwebende Elemente üblicher ist. |
| `displayProductAdditionalInfo` | Auf der Produktseite, unterhalb der Hauptproduktinformationen. | *Potenziell* zur Anzeige eines Sliders speziell auf Produktseiten, z.B. für verwandte Angebote. |
| `actionFrontControllerSetMedia` | Nachdem ein Front-Controller seine Medien gesetzt hat, sodass Module ihre eigenen hinzufügen können. | Wird verwendet, um CSS-/JS-Dateien bedingt basierend auf der aktuellen Seite oder anderen Bedingungen hinzuzufügen, um eine optimale Ladung zu gewährleisten. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Custom contents slider“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und sicherzustellen, dass Ihr Modul reibungslos mit Ihrem PrestaShop-Shop funktioniert.
