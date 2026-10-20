---
title: "Peeling Corner Banner – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Peeling Corner Banner von MyPresta.eu."
sidebar:
  label: "Peeling Corner Banner – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Peeling Corner Banner auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/peeling-corner-banner.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/peeling-corner-banner/)
>
> ---


# Peeling Corner Banner

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls klicken Sie auf „Konfigurieren“, um auf die Einstellungen zuzugreifen. Hier passen Sie das Aussehen und Verhalten Ihres Peeling-Banners an.

#### **Bild für die Ecke (Kleines Bild)**

- **Was diese Einstellung bewirkt:** Dies ist das kleine Bild, das auf der eingerollten Ecke Ihrer Seite erscheint. Es ist der anfängliche Teaser, der die Aufmerksamkeit des Kunden auf sich zieht.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Bild hochgeladen wird:* Dieses Bild wird auf der kleinen, eingerollten Ecke angezeigt.
  - *Wenn kein Bild hochgeladen wird:* Die Ecke kann leer erscheinen oder eine Standardformatierung verwenden, was weniger effektiv ist.
- **Empfohlener Wert:** Laden Sie ein kleines, ansprechendes Bild hoch (z. B. ein kleines Symbol, ein „Sale“-Tag oder einen Logo-Ausschnitt), das auf die Promotion hinweist, ohne alles zu verraten.
- **Händlerszenario / Beispiel:** Sie veranstalten einen Sommerschlussverkauf. Sie könnten ein kleines Bild eines Sonnensymbols oder ein winziges „SALE“-Abzeichen für diese Einstellung hochladen.

#### **Bild für das Banner (Großes Bild)**

- **Was diese Einstellung bewirkt:** Dies ist das Hauptbannerbild, das enthüllt wird, wenn ein Kunde über die Ecke fährt. Hier sollte Ihre primäre Nachricht, Ihr Produktbild oder Ihr Call-to-Action platziert werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Bild hochgeladen wird:* Dieses größere Bild wird angezeigt, wenn sich die Ecke zurückrollt.
  - *Wenn kein Bild hochgeladen wird:* Der zurückgerollte Bereich bleibt leer, wodurch das Modul unwirksam wird.
- **Empfohlener Wert:** Laden Sie ein klares, überzeugendes Bild hoch, das Ihre vollständige Werbebotschaft, ein Produktfoto oder einen starken Call-to-Action enthält. Stellen Sie sicher, dass es für ein Banner angemessen dimensioniert ist (z. B. 200-300px breit, ähnliche Höhe).
- **Händlerszenario / Beispiel:** Im Beispiel des Sommerschlussverkaufs wäre dieses Bild ein vollständiges Banner, das „Sommerschlussverkauf! Bis zu 50% Rabatt auf alle Bademode!“ mit attraktiven Produktfotos ankündigt.

#### **Link für das Banner**

- **Was diese Einstellung bewirkt:** Dies ist die URL (Webadresse), zu der Kunden weitergeleitet werden, wenn sie auf das enthüllte Banner klicken.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine gültige URL eingegeben wird:* Ein Klick auf das Banner führt den Kunden zu dieser Seite.
  - *Wenn leer gelassen oder eine ungültige URL eingegeben wird:* Ein Klick auf das Banner tut möglicherweise nichts oder führt zu einer Fehlerseite, was Kunden frustriert.
- **Empfohlener Wert:** Geben Sie immer eine vollständige, gültige URL an (z. B. `https://ihrshop.com/sommer-sale-kategorie`).
- **Händlerszenario / Beispiel:** Sie würden dies mit Ihrer speziellen „Sommerschlussverkauf“-Kategorieseite oder einer bestimmten Produktseite verknüpfen, die Sie hervorheben möchten.

#### **Position des Banners**

- **Was diese Einstellung bewirkt:** Dies steuert, in welcher Ecke Ihrer Website das Peeling-Banner erscheint.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Links:* Das Banner erscheint in der oberen linken Ecke des Browserfensters.
  - *Rechts:* Das Banner erscheint in der oberen rechten Ecke des Browserfensters.
- **Empfohlener Wert:** Wählen Sie die Ecke, die am besten zum Design Ihrer Website passt und keine wichtigen Elemente verdeckt. „Rechts“ ist oft ein guter Standardwert, da dort seltener Navigation oder Logos platziert sind.
- **Händlerszenario / Beispiel:** Wenn Ihr Hauptlogo und Ihre Navigation links sind, würden Sie „Rechts“ wählen, um visuelle Unordnung zu vermeiden.

#### **Modul aktivieren/deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist ein Hauptschalter, um die gesamte Peeling-Banner-Funktion ein- oder auszuschalten, ohne das Modul zu deinstallieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Aktiviert:* Das Peeling-Banner wird gemäß Ihren anderen Einstellungen im Front Office sichtbar sein.
  - *Deaktiviert:* Das Peeling-Banner wird nicht im Front Office erscheinen.
- **Empfohlener Wert:** „Aktiviert“, wenn Sie das Banner verwenden möchten, „Deaktiviert“, wenn Sie es vorübergehend für Wartungsarbeiten oder während bestimmter Zeiträume ausblenden müssen.
- **Händlerszenario / Beispiel:** Sie haben Ihre Feiertagspromotion beendet und möchten das Banner vorübergehend ausblenden, bis Ihre nächste Kampagne beginnt. Sie würden es hier deaktivieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Bild für die Ecke | Kleines Teaser-Bild hochladen | Kleines Bild an der eingerollten Ecke. Erregt Aufmerksamkeit. |
| Modulkonfiguration | Bild für das Banner | Größeres Werbebild hochladen | Hauptbannerbild, das beim Hovern enthüllt wird. Enthält die Kernbotschaft. |
| Modulkonfiguration | Link für das Banner | Vollständige URL (z. B. `https://ihrshop.com/promo`) | Ziel-URL beim Klick auf das Banner. Leitet Traffic um. |
| Modulkonfiguration | Position des Banners | Rechts | Welche Bildschirmecke das Banner erscheint (Links/Rechts). |
| Modulkonfiguration | Modul aktivieren/deaktivieren | Aktiviert | Hauptschalter zum Anzeigen oder Ausblenden des Banners im Shop. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Banner wird nach der Konfiguration nicht angezeigt. Was soll ich tun?**
A:

1. **„Modul aktivieren/deaktivieren“ prüfen:** Stellen Sie sicher, dass das Modul in seiner Konfiguration aktiviert ist.
2. **Bild-Uploads überprüfen:** Stellen Sie sicher, dass sowohl „Bild für die Ecke“ als auch „Bild für das Banner“ erfolgreich hochgeladen wurden.
3. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Modulinhalte angezeigt werden.
4. **Modul-Hook:** Das Modul sollte sich automatisch in `displayHeader` einhaken. Wenn es nicht angezeigt wird, stellen Sie sicher, dass es korrekt eingehakt ist. Sie können dies unter **Design > Positionen** (oder **Module > Positionen**) überprüfen. Suchen Sie nach `peelingcornerbanner` und bestätigen Sie, dass es mit `displayHeader` verknüpft ist.

**F: Die Bannerbilder sehen unscharf oder verzerrt aus.**
A: Dies bedeutet normalerweise, dass die von Ihnen hochgeladenen Bilder nicht für die Anzeigegröße des Banners optimiert sind.

1. **Bildabmessungen:** Überprüfen Sie die tatsächliche Größe des Banners, wenn es sich zurückrollt (Sie müssen möglicherweise die Entwicklertools Ihres Browsers verwenden). Passen Sie dann Ihr „Bild für das Banner“ an diese Abmessungen an oder machen Sie es etwas größer, um eine gute Qualität zu gewährleisten.
2. **Dateigröße:** Obwohl Qualität wichtig ist, halten Sie die Dateigrößen der Bilder so klein wie möglich (unter 100-200 KB), um ein schnelles Laden der Seite zu gewährleisten. Verwenden Sie Tools wie TinyPNG oder Online-Bildoptimierer.

**F: Das Banner erscheint, aber ein Klick darauf bewirkt nichts.**
A:

1. **„Link für das Banner“ überprüfen:** Gehen Sie zurück zur Modulkonfiguration und überprüfen Sie die URL, die Sie für den Banner-Link eingegeben haben. Stellen Sie sicher, dass es sich um eine vollständige und gültige URL handelt (z. B. `https://www.ihrshop.com/kategorie/produkt.html`).
2. **Link testen:** Kopieren Sie den Link und fügen Sie ihn direkt in Ihren Browser ein, um sicherzustellen, dass er außerhalb des Moduls korrekt funktioniert.

**F: Das Banner überlappt mit anderen Elementen auf meiner Seite.**
A:

1. **Position ändern:** Versuchen Sie, die „Position des Banners“ in der Modulkonfiguration von Links nach Rechts (oder umgekehrt) zu ändern.
2. **Theme-Konflikte:** Wenn das Ändern der Position nicht hilft, könnte es ein Konflikt mit dem CSS Ihres spezifischen PrestaShop-Themes sein. Dies erfordert möglicherweise, dass ein Webmaster das CSS des Moduls oder des Themes anpasst (siehe Abschnitt 7 für Entwicklerdetails).

**F: Kann ich mehrere Peeling-Banner haben?**
A: Nein, dieses Modul ist so konzipiert, dass es jeweils nur ein Peeling-Banner anzeigt. Wenn Sie mehrere benötigen, müssten Sie das Modul duplizieren und ändern, was Entwicklerkenntnisse erfordert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul Peeling Corner Banner (`pcb`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, einen JavaScript-gesteuerten visuellen Effekt in das Front-Office zu injizieren. Es folgt einer grundlegenden PrestaShop-Modulstruktur, die die `Module`-Klasse für Installation, Deinstallation und Konfiguration (`getContent()`) verwendet. Die Kernfunktionalität basiert auf einer benutzerdefinierten JavaScript-Datei (`peelback.js`), die die DOM-Manipulation und Animation handhabt, und einem Smarty-Template (`header.tpl`), um die anfängliche HTML-Struktur in den `displayHeader`-Hook zu rendern. Konfigurationseinstellungen werden in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

- Keine benutzerdefinierten Front-Office-Controller.
- Keine benutzerdefinierten Back-Office-Admin-Controller.
  Die Modulkonfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen.
  Alle Konfigurationen werden über `Configuration::get()` und `Configuration::updateValue()` verwaltet.

### 4.4 JavaScript-Assets (`views/js/`)

- `pcb/peelback.js`
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dies ist die zentrale JavaScript-Datei, die für die Peeling-Corner-Animation verantwortlich ist. Sie initialisiert wahrscheinlich ein jQuery-Plugin oder ein benutzerdefiniertes Skript, das:
    - Das Vorhandensein der Banner-HTML-Struktur erkennt (z. B. ein `div` mit einer spezifischen ID wie `#peelback`).
    - Ereignis-Listener, hauptsächlich `mouseover` und `mouseout`, an das Eckelement anhängt.
    - Bei `mouseover` animiert es das größere Bannerbild, um es „zurückzuziehen“ (z. B. durch Ändern von CSS-Eigenschaften wie `width`, `height`, `top`, `left`, `z-index`).
    - Bei `mouseout` animiert es das Banner zurück in seinen ursprünglichen eingerollten Zustand.
    - Behandelt das Klickereignis auf dem Banner, um zur konfigurierten URL umzuleiten.
    - Es verwendet wahrscheinlich die `animate()`-Funktion von jQuery für sanfte Übergänge.

### 4.5 CSS-Stylesheets (`views/css/`)

- Es sind keine dedizierten CSS-Dateien im Modularchiv enthalten.
  Dies impliziert, dass die Stilgebung für das Banner (Anfangsposition, Abmessungen, z-index usw.) entweder:
  1. Direkt über Inline-Styles innerhalb des `header.tpl`-Templates injiziert wird.
  2. Vollständig vom JavaScript gehandhabt wird, das dynamisch CSS-Eigenschaften setzt.
  3. Auf minimale Standard-Browser-Stile angewiesen ist oder erwartet, dass das Theme grundlegende Resets bereitstellt.
     Entwickler, die das Erscheinungsbild anpassen möchten, müssen den generierten HTML- und JavaScript-Code auf Inline-Styles oder dynamisch angewendete Klassen/Stile überprüfen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `pcb/header.tpl`
    - **Hook:** `displayHeader` (oder `displayTop` in älteren Versionen, aber `displayHeader` ist der Standard für das Einfügen globaler Elemente).
    - **Ausgabe:** Dieses Template rendert die anfängliche HTML-Struktur für das Peeling-Banner. Es enthält typischerweise:
      - Ein Container-`div` für das gesamte Banner.
      - Ein `img`-Tag für das kleine Eckbild.
      - Ein `img`-Tag für das größere Bannerbild (anfänglich ausgeblendet oder teilweise ausgeblendet).
      - Ein `<a>`-Tag, das diese Bilder umschließt und mit der konfigurierten URL verknüpft ist.
      - Es wird wahrscheinlich Smarty-Variablen verwenden, die von der `hookDisplayHeader()`-Methode des Moduls übergeben werden, um die Bild-URLs, die Link-URL und die Bannerposition (links/rechts) auszugeben.
      - Kann Inline-`<style>`-Tags enthalten oder sich auf `peelback.js` verlassen, um Stile dynamisch anzuwenden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` (oder `_configuration`-Präfix) mit Schlüsseln wie:
    - `PCB_CORNER_IMAGE` (Pfad zum kleinen Eckbild)
    - `PCB_BANNER_IMAGE` (Pfad zum großen Bannerbild)
    - `PCB_BANNER_LINK` (die URL für das Banner)
    - `PCB_BANNER_POSITION` (z. B. 'left' oder 'right')
    - `PCB_ENABLED` (1 für aktiviert, 0 für deaktiviert)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Fügt die notwendige HTML-Struktur für das Banner ein und registriert das `peelback.js`-Skript. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn Medien (JS/CSS) für einen Front-Controller gesetzt werden. | (Wird implizit von `displayHeader` oder `hookDisplayHeader` verwendet, um JS/CSS zu registrieren, obwohl nicht explizit als separater Hook in der `install()`-Methode des Moduls aufgeführt, ist dies die Art und Weise, wie PrestaShop die Medienregistrierung handhabt). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul Peeling Corner Banner besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung unserer Module sicherzustellen.
