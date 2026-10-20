---
title: "Kostenloser Versand Fortschrittsbalken kostenlos - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kostenloser Versand Fortschrittsbalken kostenlos“ von MyPresta.eu."
sidebar:
  label: "Kostenloser Versand Fortschrittsbalken kostenlos - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free Shipping Progress Bar for free auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-for-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/free-shipping-progress-bar-for-free/)
>
> ---


# Kostenloser Versand Fortschrittsbalken kostenlos

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Kostenloser Versand Fortschrittsbalken kostenlos“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren und neben dem Modulnamen auf „Konfigurieren“ klicken.

#### Allgemeine Einstellungen

- **Fortschrittsbalken für kostenlosen Versand aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Fortschrittsbalken-Funktionalität für Ihren Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Fortschrittsbalken wird an den ausgewählten Positionen in Ihrem Front Office angezeigt, und alle anderen Moduleinstellungen werden wirksam.
    - *Wenn deaktiviert (NEIN):* Der Fortschrittsbalken wird unabhängig von anderen Einstellungen vollständig aus Ihrem Shop ausgeblendet.
  - **Empfohlener Wert:** JA (um die Funktionen des Moduls zu nutzen).
  - **Händlerszenario / Beispiel:** Wenn Sie vorübergehend eine andere Aktion durchführen oder Wartungsarbeiten durchführen, könnten Sie ihn deaktivieren. Andernfalls lassen Sie ihn aktiviert, um den Verkauf zu fördern.
- **Schwelle für kostenlosen Versand:**

  - **Was diese Einstellung bewirkt:** Dies definiert den genauen Betrag (in der Standardwährung Ihres Shops), den ein Kunde ausgeben muss, um sich für kostenlosen Versand zu qualifizieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf einen bestimmten Betrag eingestellt (z. B. 50.00):* Der Fortschrittsbalken berechnet den verbleibenden Betrag basierend auf dieser Schwelle.
    - *Wenn geändert:* Das Ziel für den kostenlosen Versand wird für alle Kunden sofort aktualisiert.
  - **Empfohlener Wert:** Stellen Sie dies auf die tatsächliche Schwelle für kostenlosen Versand Ihres Shops ein. Wenn Sie kostenlosen Versand ab 50 € anbieten, stellen Sie es auf 50.00 ein.
  - **Händlerszenario / Beispiel:** Wenn Ihr Versanddienstleister kostenlosen Versand für Bestellungen über 75 € anbietet, würden Sie dies auf 75.00 einstellen.
- **Anzeige-Hook:**

  - **Was diese Einstellung bewirkt:** Dies bestimmt, wo auf Ihrer Website der Fortschrittsbalken für kostenlosen Versand angezeigt wird. Sie können aus mehreren gängigen Standorten wählen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „displayHeader“ eingestellt:* Der Balken wird im oberen Bereich Ihrer Website angezeigt, normalerweise über oder unter Ihrem Logo/Menü.
    - *Wenn auf „displayLeftColumn“ oder „displayRightColumn“ eingestellt:* Der Balken wird in der jeweiligen Seitenleiste Ihres Shops angezeigt.
    - *Wenn auf „displayFooter“ eingestellt:* Der Balken wird am unteren Rand Ihrer Website angezeigt.
    - *Wenn auf „displayProductButtons“ (oder einen ähnlichen Produktseiten-Hook) eingestellt:* Der Balken wird auf Produktseiten angezeigt, oft in der Nähe des „In den Warenkorb“-Buttons.
  - **Empfohlener Wert:** `displayHeader` oder `displayProductButtons` sind oft am effektivsten für Sichtbarkeit und zur Förderung sofortiger Aktionen.
  - **Händlerszenario / Beispiel:** Um maximale Sichtbarkeit zu gewährleisten, könnten Sie `displayHeader` wählen. Wenn Sie das Hinzufügen weiterer Artikel direkt von der Produktseite aus fördern möchten, ist `displayProductButtons` eine gute Wahl.
- **Farbe des Fortschrittsbalkens:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Farbe des Fortschrittsbalkens selbst anzupassen. Dies hilft Ihnen, ihn an das Branding Ihres Shops anzupassen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z. B. #4CAF50 für Grün):* Der Balken wird in dieser Farbe angezeigt.
  - **Empfohlener Wert:** Eine Farbe, die gut mit Ihrem Hintergrund kontrastiert, aber die Farbpalette Ihrer Marke ergänzt.
  - **Händlerszenario / Beispiel:** Wenn Ihre Marke viel Blau verwendet, könnten Sie einen Blauton oder ein komplementäres Orange wählen, um den Balken hervorzuheben.
- **Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Hintergrundfarbe des Fortschrittsbalken-Containers anzupassen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z. B. #F0F0F0 für Hellgrau):* Der Hintergrund hinter dem Fortschritt wird in dieser Farbe angezeigt.
  - **Empfohlener Wert:** Eine dezente Farbe, die einen guten Kontrast zur Farbe des Fortschrittsbalkens bietet, oft ein Hellgrau oder Weiß.
  - **Händlerszenario / Beispiel:** Um den Fortschrittsbalken selbst hervorzuheben, könnten Sie eine helle Hintergrundfarbe wie Weiß oder ein sehr helles Grau verwenden.
- **Textfarbe:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Farbe des Textes anzupassen, der innerhalb oder um den Fortschrittsbalken angezeigt wird (z. B. „Sie sind X vom kostenlosen Versand entfernt!“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z. B. #333333 für Dunkelgrau):* Der Text wird in dieser Farbe angezeigt.
  - **Empfohlener Wert:** Eine Farbe, die sowohl auf dem Fortschrittsbalken als auch auf dessen Hintergrund gut lesbar ist.
  - **Händlerszenario / Beispiel:** Wenn Ihr Fortschrittsbalken grün und sein Hintergrund hellgrau ist, würde eine dunkelgraue oder schwarze Textfarbe die Lesbarkeit gewährleisten.

#### Pro Edition Teaser

Dieser Abschnitt enthält typischerweise Informationen und Links zum Upgrade auf die „Pro“-Version des Moduls, die erweiterte Funktionen bietet. Dies sind keine Konfigurationseinstellungen für das kostenlose Modul, sondern Werbeinhalte.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Fortschrittsbalken für kostenlosen Versand aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
| Modulkonfiguration | Schwelle für kostenlosen Versand | Betrag für kostenlosen Versand Ihres Shops | Definiert den Zielbetrag für kostenlosen Versand. |
| Modulkonfiguration | Anzeige-Hook | `displayHeader` / `displayProductButtons` | Bestimmt, wo der Balken in Ihrem Shop erscheint. |
| Modulkonfiguration | Farbe des Fortschrittsbalkens | Anpassbar (z. B. #4CAF50) | Legt die Farbe des gefüllten Teils des Fortschrittsbalkens fest. |
| Modulkonfiguration | Hintergrundfarbe | Anpassbar (z. B. #F0F0F0) | Legt die Hintergrundfarbe des Fortschrittsbalken-Containers fest. |
| Modulkonfiguration | Textfarbe | Anpassbar (z. B. #333333) | Legt die Farbe des mit dem Balken angezeigten Textes fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Fortschrittsbalken wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A1:

- **Modulstatus prüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Kostenloser Versand Fortschrittsbalken kostenlos“ installiert und aktiviert ist.
- **Konfiguration prüfen:** Navigieren Sie zur Konfigurationsseite des Moduls. Stellen Sie sicher, dass „Fortschrittsbalken für kostenlosen Versand aktivieren“ auf JA eingestellt ist. Überprüfen Sie auch, ob die Einstellung „Anzeige-Hook“ korrekt gewählt ist und Ihr Theme diesen Hook tatsächlich rendert (einige benutzerdefinierte Themes tun dies möglicherweise nicht).
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“). Manchmal verhindert ein alter Cache, dass neue Modulinhalte angezeigt werden.
- **Theme-Kompatibilität:** Obwohl das Modul für Standard-PrestaShop-Themes (Classic, Hummingbird) entwickelt wurde, können stark angepasste Themes geringfügige Anpassungen erfordern. Wenn die oben genannten Schritte nicht funktionieren, wenden Sie sich an den MyPresta.eu-Support.

**F2: Der Fortschrittsbalken wird angezeigt, aktualisiert sich aber nicht, wenn ich Artikel in den Warenkorb lege.**
A2:

- **JavaScript prüfen:** Stellen Sie sicher, dass keine JavaScript-Fehler auf Ihrer Website vorliegen, die die Ausführung des Modulskripts verhindern könnten. Sie können die Entwicklerkonsole Ihres Browsers (normalerweise F12) auf Fehler überprüfen.
- **AJAX-Warenkorb:** Das Modul basiert auf der AJAX-Warenkorbfunktionalität von PrestaShop. Stellen Sie sicher, dass der Warenkorb-Aktualisierungsmechanismus Ihres Themes Standard ist und keine PrestaShop-AJAX-Aufrufe auf eine Weise überschreibt, die das Modul daran hindert, Änderungen zu erkennen.
- **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Module, die das Warenkorbverhalten oder Anzeigeelemente in denselben Hooks ändern, um nach Konflikten zu suchen.

**F3: Wie ändere ich den im Fortschrittsbalken angezeigten Text (z. B. „Sie sind X vom kostenlosen Versand entfernt!“)?**
A3: Die kostenlose Version des Moduls verwendet typischerweise vordefinierten Text. Um diesen Text anzupassen, müssten Sie normalerweise die Template-Datei des Moduls (`progress.tpl`) bearbeiten. Dies erfordert jedoch grundlegende Kenntnisse von Smarty-Templates. Für eine benutzerfreundlichere Möglichkeit zur Textanpassung enthält die Pro-Version des Moduls oft dedizierte Textfelder im Back Office.

**F4: Der Fortschrittsbalken sieht seltsam aus oder passt nicht zum Styling meines Themes.**
A4:

- **Modulkonfigurationsfarben:** Verwenden Sie zunächst die Einstellungen „Farbe des Fortschrittsbalkens“, „Hintergrundfarbe“ und „Textfarbe“ in der Modulkonfiguration, um zu versuchen, sie an Ihr Theme anzupassen.
- **CSS-Konflikte:** Das CSS Ihres Themes könnte die Standardstile des Moduls überschreiben. Ein Webmaster kann das Element mit den Browser-Entwicklertools überprüfen, um widersprüchliche CSS-Regeln zu identifizieren und benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um diese zu überschreiben. Die CSS-Dateien des Moduls (`front.css`) können ein guter Ausgangspunkt sein, um die zu zielenden Selektoren zu identifizieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Kostenloser Versand Fortschrittsbalken kostenlos“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für Installation, Deinstallation und Konfiguration nutzt. Es verwendet Front-Controller für AJAX-Interaktionen, um den Fortschrittsbalken dynamisch ohne vollständige Seitenneuladungen zu aktualisieren. Das Modul integriert sich in das PrestaShop-Hook-System, um seine Inhalte an verschiedenen Front-Office-Positionen anzuzeigen, und verwendet Smarty-Templates zur Darstellung seiner Benutzeroberfläche. Die Konfiguration wird in der Tabelle `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/index.php`
    - **Klassenname & Elternklasse:** `SmartFreeShippingFreeIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Basis oder Einstiegspunkt für Front-Office-Interaktionen, obwohl seine spezifischen Methoden minimal sein könnten, wenn `refresh.php` die primäre AJAX-Verarbeitung übernimmt. Er könnte für die anfängliche Datenladung oder die Einrichtung des Kontexts verwendet werden.
  - `controllers/front/refresh.php`
    - **Klassenname & Elternklasse:** `SmartFreeShippingFreeRefreshModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dies ist der zentrale AJAX-Controller. Er antwortet auf Anfragen (wahrscheinlich POST oder GET) vom Front-Office-JavaScript, um die aktuelle Warenkorbsumme abzurufen, den verbleibenden Betrag für den kostenlosen Versand zu berechnen und den aktualisierten Fortschrittsbalken-HTML oder -Daten zurückzugeben. Er handhabt die Währungsumrechnung und stellt sicher, dass der Fortschrittsbalken Echtzeit-Warenkorbänderungen widerspiegelt.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder komplexe Geschäftslogik-Klassen über das hinaus, was in der Hauptmoduldatei (`index.php`) und den Front-Controllern enthalten ist.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/front.js`
  - **Umfang:** Front-Office.
  - **Details:** Dieses Skript ist für das dynamische Verhalten des Fortschrittsbalkens verantwortlich.
    - Es bindet wahrscheinlich Event-Listener an Warenkorb-Update-Ereignisse (z. B. `prestashop.on('updateCart', ...)` oder benutzerdefinierte Ereignisse, die durch den AJAX-Warenkorb des Themes ausgelöst werden).
    - Wenn ein Warenkorb-Update erkannt wird, führt es einen AJAX-Aufruf an den `refresh.php`-Front-Controller durch, um den aktualisierten Fortschrittsbalkenstatus zu erhalten.
    - Es aktualisiert dann das DOM, um den neuen Fortschritt widerzuspiegeln (z. B. Breite des Fortschrittsbalkens, Text des verbleibenden Betrags).
    - Kann Logik für die anfängliche Darstellung beim Seitenladen und die Handhabung verschiedener Anzeige-Hooks enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/admin-config.css`

  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Details:** Enthält Stile speziell für die Konfigurationsseite des Moduls im PrestaShop Back Office, um ein sauberes und benutzerfreundliches Layout für die Einstellungen zu gewährleisten.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Elemente innerhalb des Konfigurationsformulars des Moduls ab, wie z. B. `.panel`, `.form-group`, `.control-label` usw., spezifisch für die HTML-Struktur des Moduls.
- `views/css/admin-pro-teaser.css`

  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Details:** Stile für die Werbeinhalte, die sich auf die „Pro“-Version des Moduls beziehen, um sicherzustellen, dass sie ansprechend und eigenständig auf der Konfigurationsseite aussehen.
  - **Wichtige CSS-Klassenselektoren:** Zielt auf Elemente wie `.pro-teaser-block`, `.pro-feature-list` usw. ab.
- `views/css/front.css`

  - **Umfang:** Styling für Kunden im Front-Office.
  - **Details:** Enthält das Kern-CSS für den Fortschrittsbalken für kostenlosen Versand selbst, einschließlich seines Layouts, seiner Farben, Animationen und Responsivität.
  - **Wichtige CSS-Klassenselektoren:** Zielt auf Elemente wie `#smartfreeshippingfree-progress-bar-container`, `.progress-bar-fill`, `.progress-bar-text` usw. ab. Entwickler können diese Klassen in der `custom.css` oder `theme.css` ihres Themes überschreiben, um sie an ihr spezifisches Design anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `views/templates/admin/configure.tpl`
    - **Zweck:** Dies ist das Haupt-Smarty-Template für die Konfigurationsseite des Moduls im Back Office. Es rendert die Formularfelder, Schalter und Eingabeelemente für alle Moduleinstellungen. Es enthält wahrscheinlich die `get-pro-hero.tpl` und `get-pro.tpl` für Werbeinhalte.
  - `views/templates/admin/get-pro-hero.tpl`
    - **Zweck:** Rendert einen prominenten „Hero“-Bereich, der die Pro-Version des Moduls bewirbt, oft oben auf der Konfigurationsseite.
  - `views/templates/admin/get-pro.tpl`
    - **Zweck:** Rendert einen detaillierten Abschnitt, der die Funktionen und Vorteile eines Upgrades auf die Pro-Version beschreibt, typischerweise mit einem Call-to-Action.
- **Hook-Templates (`views/templates/hook/`)**:

  - `views/templates/hook/progress.tpl`
    - **Zweck:** Dies ist das primäre Front-Office-Template. Es rendert die HTML-Struktur des Fortschrittsbalkens für kostenlosen Versand, einschließlich des Containers, des gefüllten Fortschrittsbereichs und des dynamischen Textes (z. B. „Sie sind X vom kostenlosen Versand entfernt!“). Dieses Template wird von der `displayHook`-Methode der Hauptmoduldatei gerendert.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Keine. Die Front-Office-Anzeige wird über die `hook/progress.tpl` behandelt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert, wobei die Schlüssel mit `SMARTFREESHIPPINGFREE_` präfixiert sind (z. B. `SMARTFREESHIPPINGFREE_ENABLED`, `SMARTFREESHIPPINGFREE_THRESHOLD`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Seite oder ganz oben im `<body>`. | Wird verwendet, um CSS/JS-Assets einzufügen und möglicherweise den Fortschrittsbalken im Header zu rendern. |
| `displayLeftColumn` | In der linken Spalte des Themes. | Alternative Position zur Anzeige des Fortschrittsbalkens. |
| `displayRightColumn` | In der rechten Spalte des Themes. | Alternative Position zur Anzeige des Fortschrittsbalkens. |
| `displayFooter` | Im Footer-Bereich des Themes. | Alternative, weniger aufdringliche Position zur Anzeige des Fortschrittsbalkens. |
| `displayProductButtons` (oder ähnlich) | Auf der Produktseite, oft in der Nähe des „In den Warenkorb“-Buttons. | Spezifische Platzierung, um das Hinzufügen von Artikeln direkt von Produktseiten aus zu fördern. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert wurde (z. B. Artikel hinzugefügt/entfernt). | Interner Hook (nicht zur Anzeige), der vom Modul verwendet wird, um AJAX-Updates für den Fortschrittsbalken auszulösen. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert, um CSS/JS hinzuzufügen. | Wird verwendet, um `front.js` und `front.css` für Front-Office-Seiten zu registrieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Kostenloser Versand Fortschrittsbalken kostenlos“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.
