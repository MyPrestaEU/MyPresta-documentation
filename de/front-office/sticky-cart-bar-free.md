---
title: "Sticky Cart Bar FREE - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Sticky Cart Bar FREE von MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar FREE - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Sticky Cart Bar FREE auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/sticky-cart-bar-free/)
>
> ---


# Sticky Cart Bar FREE

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Sticky Cart Bar FREE)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie steuern, wie sich die klebrige Warenkorbleiste auf Ihren Produktseiten verhält und erscheint.

#### **Sticky Cart Bar aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Funktionalität der klebrigen Warenkorbleiste für Ihren Shop ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die klebrige Warenkorbleiste erscheint auf Produktseiten gemäß Ihren anderen Einstellungen, wenn Kunden am Haupt-„In den Warenkorb“-Button vorbeiscrollen.
  - *Wenn deaktiviert (NEIN):* Die klebrige Warenkorbleiste erscheint auf keiner Produktseite, wodurch das Modul effektiv deaktiviert wird.
- **Empfohlener Wert:** JA (um die Vorteile des Moduls zu nutzen).
- **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder es vorübergehend deaktivieren möchten, ohne es zu deinstallieren, stellen Sie dies auf NEIN. Für den Live-Betrieb sollte es auf JA stehen.

#### **Position der Sticky Cart Bar**

- **Was diese Einstellung bewirkt:** Bestimmt, wo die klebrige Leiste auf dem Bildschirm des Kunden „kleben“ bleibt – entweder oben oder unten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Oben“ eingestellt:* Die klebrige Leiste erscheint ganz oben im Browserfenster, unterhalb des Headers.
  - *Wenn auf „Unten“ eingestellt:* Die klebrige Leiste erscheint ganz unten im Browserfenster, oberhalb des Footers.
- **Empfohlener Wert:** „Unten“ (oft weniger aufdringlich, da es die Hauptnavigation oder das Logo nicht verdeckt). „Oben“ kann jedoch prominenter sein. Testen Sie beides, um zu sehen, was für Ihr Theme und Ihre Zielgruppe am besten funktioniert.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop einen sehr belebten Header oder ein oben fixiertes Menü hat, könnte das Platzieren der klebrigen Leiste „Unten“ visuelle Unordnung verhindern. Wenn Sie maximale Sichtbarkeit für den „In den Warenkorb“-Button wünschen, könnte „Oben“ bevorzugt werden.

#### **Auf Mobilgeräten anzeigen**

- **Was diese Einstellung bewirkt:** Steuert, ob die klebrige Warenkorbleiste Kunden angezeigt wird, die Ihren Shop auf Smartphones oder anderen mobilen Geräten durchsuchen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die klebrige Warenkorbleiste ist auf mobilen Produktseiten aktiv und sichtbar.
  - *Wenn deaktiviert (NEIN):* Die klebrige Warenkorbleiste erscheint nicht auf mobilen Geräten, sondern nur auf Desktop/Tablet.
- **Empfohlener Wert:** JA (Mobile Benutzer scrollen viel, und diese Funktion ist für sie sehr vorteilhaft).
- **Händlerszenario / Beispiel:** Angesichts des begrenzten Bildschirmplatzes auf Mobilgeräten ist es noch wichtiger, den „In den Warenkorb“-Button sichtbar zu halten. Deaktivieren Sie dies nur, wenn Sie spezifische Layoutkonflikte mit Ihrem mobilen Theme feststellen.

#### **Auf Desktop-Geräten anzeigen**

- **Was diese Einstellung bewirkt:** Steuert, ob die klebrige Warenkorbleiste Kunden angezeigt wird, die Ihren Shop auf Desktop-Computern oder größeren Tablet-Bildschirmen durchsuchen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die klebrige Warenkorbleiste ist auf Desktop-Produktseiten aktiv und sichtbar.
  - *Wenn deaktiviert (NEIN):* Die klebrige Warenkorbleiste erscheint nicht auf Desktop-Geräten, sondern nur auf Mobilgeräten (falls aktiviert).
- **Empfohlener Wert:** JA (Auch auf dem Desktop profitieren lange Produktseiten von dieser Funktion).
- **Händlerszenario / Beispiel:** Die meisten Shops möchten dies für alle Gerätetypen aktivieren, um das Konversionspotenzial zu maximieren.

#### **Original „In den Warenkorb“-Button ausblenden**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, den ursprünglichen „In den Warenkorb“-Button auf der Produktseite auszublenden, sobald die klebrige Leiste erscheint.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Wenn die klebrige Leiste sichtbar ist, wird der ursprüngliche „In den Warenkorb“-Button auf der Produktseite ausgeblendet. Dies kann visuelle Redundanz reduzieren.
  - *Wenn deaktiviert (NEIN):* Sowohl der „In den Warenkorb“-Button der klebrigen Leiste als auch der ursprüngliche „In den Warenkorb“-Button sind gleichzeitig sichtbar (wenn der ursprüngliche im Blickfeld ist).
- **Empfohlener Wert:** NEIN (Im Allgemeinen ist es sicherer, den ursprünglichen Button sichtbar zu lassen, wenn er im Viewport ist, da einige Kunden ihn bevorzugen könnten. Das Ausblenden könnte Verwirrung stiften, wenn die klebrige Leiste schnell verschwindet).
- **Händlerszenario / Beispiel:** Wenn Sie die doppelten „In den Warenkorb“-Buttons als visuell störend oder verwirrend empfinden, wenn die klebrige Leiste aktiv ist, könnten Sie dies aktivieren. Andernfalls lassen Sie es deaktiviert.

#### **Theme-Kompatibilität**

- **Was diese Einstellung bewirkt:** Diese Einstellung hilft dem Modul, sein Styling und Verhalten an verschiedene PrestaShop-Themes anzupassen, insbesondere Classic und Hummingbird (das Standard-Theme für PrestaShop 8+).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Classic“ eingestellt:* Das Modul lädt CSS und JavaScript, die für das PrestaShop Classic-Theme und darauf basierende Themes optimiert sind.
  - *Wenn auf „Hummingbird“ eingestellt:* Das Modul lädt CSS und JavaScript, die für das PrestaShop Hummingbird-Theme (PrestaShop 8.x und 9.x Standard) und darauf basierende Themes optimiert sind.
- **Empfohlener Wert:** Wählen Sie das Theme, das Ihr Shop derzeit verwendet. Wenn Sie PrestaShop 8.x oder 9.x verwenden, ist es wahrscheinlich „Hummingbird“. Wenn Sie PrestaShop 1.7.x verwenden und das Standard-Theme nutzen, ist es „Classic“. Wenn Sie ein benutzerdefiniertes Theme verwenden, probieren Sie beide aus, um zu sehen, welches besser integriert ist.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop auf PrestaShop 8.1 läuft und Sie „Classic“ auswählen, funktioniert die klebrige Leiste möglicherweise nicht korrekt oder sieht nicht richtig aus. Passen Sie dies immer an Ihr aktives Theme an.

#### **Pro-Version Teaser**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ist ein Werbebereich für das Modul „Sticky Cart Bar PRO“, das erweiterte Funktionen bietet, die in der FREE-Version nicht verfügbar sind. Er beeinflusst nicht die Funktionalität des FREE-Moduls.
- **Auswirkung der Änderung dieser Einstellung:** Keine direkte Auswirkung auf das Verhalten des FREE-Moduls. Es liefert Informationen über ein Upgrade.
- **Empfohlener Wert:** N/A (Nur informativ).
- **Händlerszenario / Beispiel:** Wenn Sie das FREE-Modul als vorteilhaft empfinden und mehr Kontrolle über Targeting, Design oder spezifische Produktausschlüsse benötigen, können Sie hier die Funktionen der PRO-Version überprüfen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Sticky Cart Bar aktivieren | JA | Hauptschalter für das Modul. JA aktiviert die klebrige Leiste. |
| Modulkonfiguration | Position der Sticky Cart Bar | Unten | Bestimmt, ob die Leiste oben oder unten am Bildschirm klebt. |
| Modulkonfiguration | Auf Mobilgeräten anzeigen | JA | Steuert die Sichtbarkeit auf Smartphones/Tablets. JA wird empfohlen. |
| Modulkonfiguration | Auf Desktop-Geräten anzeigen | JA | Steuert die Sichtbarkeit auf Desktop-Computern. JA wird empfohlen. |
| Modulkonfiguration | Original „In den Warenkorb“-Button ausblenden | NEIN | Blendet den ursprünglichen Button aus, wenn die klebrige Leiste aktiv ist. NEIN ist im Allgemeinen sicherer. |
| Modulkonfiguration | Theme-Kompatibilität | Hummingbird (für PS 8/9) | Stellt die korrekte Darstellung und Funktionalität für Ihr aktives Theme sicher. Passen Sie es an Ihr Theme an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die klebrige Warenkorbleiste erscheint nicht auf meinen Produktseiten.**
A:

- **„Sticky Cart Bar aktivieren“ überprüfen**: Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf JA gesetzt ist.
- **„Theme-Kompatibilität“ überprüfen**: Stellen Sie sicher, dass Sie das richtige Theme (Classic oder Hummingbird) ausgewählt haben, das zum aktiven Theme Ihres Shops passt. Eine falsche Auswahl kann verhindern, dass die Leiste geladen wird.
- **Cache leeren**: Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Moduländerungen angezeigt werden.
- **Am Original-Button vorbeiscrollen**: Denken Sie daran, dass die Leiste nur erscheint, wenn Sie am ursprünglichen „In den Warenkorb“-Button vorbeiscrollen. Stellen Sie sicher, dass Sie weit genug auf der Seite nach unten scrollen.
- **Geräteeinstellungen überprüfen**: Stellen Sie sicher, dass „Auf Mobilgeräten anzeigen“ und/oder „Auf Desktop-Geräten anzeigen“ für das Gerät aktiviert sind, auf dem Sie testen.

**F2: Die klebrige Warenkorbleiste sieht seltsam aus oder ist mit meinem benutzerdefinierten Theme nicht ausgerichtet.**
A:

- **Theme-Kompatibilität**: Überprüfen Sie nochmals, ob Sie die richtige Option für die „Theme-Kompatibilität“ in den Moduleinstellungen ausgewählt haben. Wenn Sie ein stark angepasstes Theme haben, könnte es sich anders verhalten. Versuchen Sie, zwischen „Classic“ und „Hummingbird“ zu wechseln, um zu sehen, ob eines besser funktioniert.
- **Benutzerdefiniertes CSS (Entwickler erforderlich)**: Wenn das Problem weiterhin besteht, hat Ihr benutzerdefiniertes Theme möglicherweise widersprüchliche CSS-Stile. Ein Webentwickler kann die Seite mit den Browser-Entwicklertools überprüfen und ein paar Zeilen benutzerdefiniertes CSS schreiben, um das Erscheinungsbild der klebrigen Leiste anzupassen. Dies beinhaltet normalerweise das Überschreiben vorhandener Stile in der `custom.css`-Datei Ihres Themes.

**F3: Der „In den Warenkorb“-Button in der klebrigen Leiste funktioniert nicht.**
A:

- **Cache leeren**: Wie bei Anzeigeproblemen kann das Leeren Ihres PrestaShop-Caches (**Erweiterte Einstellungen > Leistung**) JavaScript-bezogene Probleme beheben.
- **Theme-Kompatibilität**: Stellen Sie sicher, dass das richtige Theme ausgewählt ist. Das JavaScript wird möglicherweise nicht korrekt initialisiert, wenn das falsche Theme ausgewählt ist.
- **Browser-Konsolenfehler (Entwickler erforderlich)**: Bitten Sie Ihren Webentwickler, die JavaScript-Konsole des Browsers auf Fehler zu überprüfen. Konflikte mit anderen Modulen oder Theme-JavaScript können manchmal verhindern, dass der Button funktioniert.

**F4: Kann ich die Farben oder den Inhalt der klebrigen Leiste anpassen?**
A:

- Die FREE-Version des Moduls bietet begrenzte Styling-Optionen (hauptsächlich Anpassung an Ihr Theme). Für erweiterte Anpassungen wie das Ändern von Farben, Schriftarten, Hinzufügen von benutzerdefiniertem Text oder eine granularere Kontrolle darüber, welche Informationen angezeigt werden, müssten Sie normalerweise auf das Modul **Sticky Cart Bar PRO** upgraden.
- Für kleinere visuelle Anpassungen in der FREE-Version kann ein Webentwickler benutzerdefiniertes CSS verwenden, um die Standardstile zu überschreiben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul Sticky Cart Bar FREE folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für Installation, Deinstallation und Konfiguration nutzt. Es integriert sich über Hooks in das Front-Office und injiziert dynamisch eine klebrige Leiste basierend auf dem Scrollverhalten des Benutzers. Das Modul verwendet eine Kombination aus Smarty-Templates für die Struktur, CSS für das Styling und JavaScript für die klebrige Funktionalität und die Interaktion mit dem Haupt-„In den Warenkorb“-Button. Die Kompatibilität mit verschiedenen PrestaShop-Themes (Classic vs. Hummingbird) wird durch das Laden themenspezifischer Assets gehandhabt.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- `stickycartbarfree/classes/index.php`:
  - Dies ist typischerweise eine leere Datei, die verwendet wird, um die Verzeichnisauflistung zu verhindern, eine gängige Sicherheitspraxis in PrestaShop-Modulen. Sie enthält keinen funktionalen Code.
- `stickycartbarfree/classes/ScbfCompatibility.php`:
  - **Klassenname**: `ScbfCompatibility`
  - **Elternklasse**: Keine (eigenständige Dienstprogrammklasse)
  - **Verantwortlichkeit**: Diese Klasse enthält wahrscheinlich statische Hilfsmethoden zur Handhabung von Kompatibilitätsunterschieden zwischen verschiedenen PrestaShop-Versionen oder Themes. Sie könnte Unterschiede in der Art und Weise abstrahieren, wie Produktdaten abgerufen oder Assets registriert werden, um sicherzustellen, dass das Modul in allen unterstützten Umgebungen funktioniert. Sie interagiert nicht direkt mit einer bestimmten Datenbanktabelle, könnte aber `ps_configuration` nach Theme-Informationen abfragen.
  - **Wichtige öffentliche Methoden**: Wahrscheinlich statische Methoden zum Überprüfen des Theme-Kontexts, der PrestaShop-Version oder zum Abrufen von Konfigurationswerten auf kompatible Weise.

### 4.4 JavaScript-Assets (`views/js/`)

- `stickycartbarfree/views/js/front.js`:
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Dies ist die zentrale JavaScript-Datei, die für das klebrige Verhalten der Warenkorbleiste verantwortlich ist.
  - **Funktionalität**:
    - **Event-Listener**: Bindet an das `scroll`-Ereignis des Fensters, um zu erkennen, wann der Benutzer scrollt.
    - **DOM-Manipulation**:
      - Berechnet die Position des ursprünglichen „In den Warenkorb“-Buttons (`#add_to_cart` oder ähnlicher Selektor).
      - Überwacht die Scrollposition relativ zum ursprünglichen Button.
      - Fügt eine CSS-Klasse (z.B. `is-visible`) zum Container der klebrigen Warenkorbleiste (`#sticky-cart-bar`) hinzu/entfernt sie, um sie anzuzeigen oder auszublenden.
      - Blendet möglicherweise den ursprünglichen „In den Warenkorb“-Button aus, wenn die entsprechende Moduleinstellung aktiviert ist.
    - **Interaktion**: Behandelt Klicks auf den „In den Warenkorb“-Button innerhalb der klebrigen Leiste, wahrscheinlich indem das Verhalten des ursprünglichen Buttons nachgeahmt wird (z.B. Absenden des Produktformulars, Ausführen eines AJAX-Aufrufs zum Hinzufügen zum Warenkorb).
    - **Responsivität**: Kann Logik enthalten, um Positionen bei `resize`-Ereignissen neu zu bewerten.
    - **PrestaShop-Ereignisse**: Verwendet wahrscheinlich `prestashop.on('updateProduct', ...)` oder ähnliche Ereignisse, um den Inhalt der klebrigen Leiste (Preis, Menge, Attribute) zu aktualisieren, wenn Produktoptionen auf der Seite geändert werden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `stickycartbarfree/views/css/admin-config.css`:
  - **Geltungsbereich**: Styling des Back-Office-Admin-Formulars.
  - **Beschreibung**: Enthält Stile speziell für die Konfigurationsseite des Moduls im PrestaShop Back Office, um eine konsistente und benutzerfreundliche Admin-Oberfläche zu gewährleisten.
  - **Haupt-UI-Komponenten**: Stile für Formularelemente, Beschriftungen, Schaltflächen und möglicherweise spezifische Layoutelemente innerhalb der `getContent()`-Ausgabe.
- `stickycartbarfree/views/css/admin-pro-teaser.css`:
  - **Geltungsbereich**: Styling des Back-Office-Admin-Formulars.
  - **Beschreibung**: Stile für den Werbeinhalt der PRO-Version des Moduls, der auf der Konfigurationsseite angezeigt wird.
  - **Haupt-UI-Komponenten**: Stile für Teaser-Boxen, Upgrade-Buttons, Feature-Listen und Vorschaubilder für die PRO-Version.
- `stickycartbarfree/views/css/front-classic.css`:
  - **Geltungsbereich**: Front-Office-Kunden-Styling (Classic-Theme).
  - **Beschreibung**: Bietet spezifische Styling-Anpassungen für die klebrige Warenkorbleiste, wenn die Kompatibilitätsoption „Classic“ ausgewählt ist. Dies stellt sicher, dass die Leiste visuell in das Design des Classic-Themes integriert ist.
  - **Wichtige CSS-Klassenselektoren**: Zielt auf Elemente innerhalb von `sticky-cart-bar` ab, um Classic-Theme-Schriftarten, -Farben, -Abstände und -Button-Stile anzupassen.
- `stickycartbarfree/views/css/front-hummingbird.css`:
  - **Geltungsbereich**: Front-Office-Kunden-Styling (Hummingbird-Theme).
  - **Beschreibung**: Bietet spezifische Styling-Anpassungen für die klebrige Warenkorbleiste, wenn die Kompatibilitätsoption „Hummingbird“ ausgewählt ist. Dies stellt sicher, dass die Leiste visuell in das Standard-Theme von PrestaShop 8.x/9.x integriert ist.
  - **Wichtige CSS-Klassenselektoren**: Zielt auf Elemente innerhalb von `sticky-cart-bar` ab, um Hummingbird-Theme-Schriftarten, -Farben, -Abstände und -Button-Stile anzupassen.
- `stickycartbarfree/views/css/front.css`:
  - **Geltungsbereich**: Front-Office-Kunden-Styling (allgemein).
  - **Beschreibung**: Enthält die grundlegenden, gemeinsamen Stile für die klebrige Warenkorbleiste, die unabhängig von der ausgewählten Theme-Kompatibilität gelten. Dies umfasst die Kernpositionierung, Sichtbarkeit und Responsivität.
  - **Wichtige CSS-Klassenselektoren**: Definiert `#sticky-cart-bar`-Eigenschaften wie `position: fixed`, `z-index`, `width`, `padding`, `background-color` und responsive Media Queries.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-classic.tpl`: Wird gerendert, wenn die Theme-Kompatibilität „Classic“ ausgewählt ist. Enthält die Hauptstruktur für die klebrige Leiste, zugeschnitten auf die HTML- und CSS-Erwartungen des Classic-Themes.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-hummingbird.tpl`: Wird gerendert, wenn die Theme-Kompatibilität „Hummingbird“ ausgewählt ist. Enthält die Hauptstruktur für die klebrige Leiste, zugeschnitten auf die HTML- und CSS-Erwartungen des Hummingbird-Themes.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-inner.tpl`: Dieses Template enthält wahrscheinlich den Kerninhalt der klebrigen Leiste (Produktname, Preis, Mengeneingabe, In den Warenkorb-Button). Es wird wahrscheinlich von `sticky-cart-bar-classic.tpl` und `sticky-cart-bar-hummingbird.tpl` eingebunden, um Code-Duplizierung zu vermeiden.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar.tpl`: Dies könnte ein Wrapper-Template oder ein Fallback sein, oder es könnte der Haupteinstiegspunkt sein, der `sticky-cart-bar-classic.tpl` oder `sticky-cart-bar-hummingbird.tpl` bedingt basierend auf der Konfiguration einbindet.
  - **Zweck**: Diese Templates werden typischerweise in `displayFooter` oder `displayBeforeBodyClosingTag` eingehängt, um sicherzustellen, dass der HTML-Code der klebrigen Leiste auf Produktseiten vorhanden ist. Sie geben die HTML-Struktur für die klebrige Leiste aus, gefüllt mit Produktdaten, die vom Modul übergeben werden.
- **Admin-Templates (`views/templates/admin/`)**:

  - `stickycartbarfree/views/templates/admin/configure.tpl`: Dies ist das Haupt-Template für die Konfigurationsseite des Moduls im Back Office. Es rendert alle Einstellungen, Eingabefelder und Optionen, die in der `getContent()`-Methode des Moduls definiert sind.
  - `stickycartbarfree/views/templates/admin/pro-teaser-intro.tpl`: Rendert den Einführungsteil des PRO-Version-Teasers auf der Konfigurationsseite.
  - `stickycartbarfree/views/templates/admin/pro-teaser-preview.tpl`: Rendert eine Vorschau oder visuelle Darstellung der PRO-Version-Funktionen.
  - `stickycartbarfree/views/templates/admin/pro-teaser.tpl`: Das Haupt-Template für den PRO-Version-Teaser-Bereich, das wahrscheinlich die Intro- und Vorschau-Templates enthält.
  - **Zweck**: Diese Templates stellen die Benutzeroberfläche für die Moduleinstellungen und Werbeinhalte innerhalb des PrestaShop Back Office bereit.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert, wobei die Schlüssel typischerweise mit `SCBF_` beginnen (z.B. `SCBF_ENABLE`, `SCBF_POSITION`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS- und JavaScript-Assets (`front.js`, `front.css`, themenspezifisches CSS) für das Front-Office zu registrieren. |
| `displayFooter` | Vor dem schließenden `</body>`-Tag auf jeder Seite. | Wird verwendet, um die Haupt-HTML-Struktur der klebrigen Warenkorbleiste (`sticky-cart-bar.tpl` oder ihre Varianten) in die Seite einzufügen. |
| `actionFrontControllerSetMedia` | Nachdem Medien (CSS/JS) vom Front-Controller gesetzt wurden. | Alternativer Hook zum Registrieren von Assets, um sicherzustellen, dass sie korrekt geladen werden. |
| `actionProductUpdate` | Nachdem ein Produkt im Back Office aktualisiert wurde. | (Wahrscheinlich nicht in der FREE-Version verwendet, aber üblich für Module, die den Cache leeren oder Produktdaten neu indizieren müssen). |
| `actionCartUpdateQuantity` | Wenn eine Produktmenge im Warenkorb aktualisiert wird. | (Wahrscheinlich nicht in der FREE-Version verwendet, könnte aber verwendet werden, um den Mengenwähler der klebrigen Leiste zu aktualisieren, wenn er interaktiver wäre). |
| `actionAjaxDieProduct` | Wenn eine AJAX-Anfrage bezüglich Produktdaten fehlschlägt. | (Könnte für Debugging oder spezifische AJAX-Interaktionen verwendet werden). |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um erweiterte Funktionen der PRO-Version des Moduls zu erkunden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul Sticky Cart Bar FREE zur Verfügung.
