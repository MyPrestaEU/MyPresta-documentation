---
title: "Preise ohne Steuern für nicht angemeldete Benutzer nach Geolokalisierung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Preise ohne Steuern für nicht angemeldete Benutzer nach Geolokalisierung“ von MyPresta.eu."
sidebar:
  label: "Preise ohne Steuern für nicht angemeldete Benutzer nach Geolokalisierung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Tax excluded prices for unlogged users by geolocation auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/tax-excluded-prices-for-unlogged-users-by-geolocation.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/tax-excluded-prices-for-unlogged-users-by-geolocation/)
>
> ---


# Preise ohne Steuern für nicht angemeldete Benutzer nach Geolokalisierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul arbeitet hauptsächlich durch Überschreibungen der PrestaShop-Kernpreislogik, was bedeutet, dass seine Konfiguration normalerweise minimal oder sogar automatisch ist. Die Methode `getContent()` in der Hauptmoduldatei handhabt typischerweise die Anzeige eines Standardkonfigurationsformulars, aber für dieses spezifische Modul wird die Kernfunktionalität durch Klassenüberschreibungen und nicht durch umfangreiche Einstellungen erreicht.

Wenn ein Konfigurationsbildschirm vorhanden ist, würde er typischerweise Optionen zum Aktivieren/Deaktivieren des Moduls oder zur Feinabstimmung seines Geolokalisierungsverhaltens bieten. Basierend auf der Beschreibung und Dateistruktur des Moduls besteht seine Hauptfunktion jedoch darin, Preise *automatisch* basierend auf der Geolokalisierung anzupassen, ohne dass komplexe, vom Händler zu bedienende Einstellungen erforderlich sind.

Daher ist der Konfigurationsbildschirm für dieses Modul wahrscheinlich sehr einfach, möglicherweise nur ein „Aktivieren/Deaktivieren“-Schalter, oder er hat möglicherweise gar kein dediziertes Konfigurationsformular, wenn sein Verhalten nach der Installation vollständig automatisch ist.

**Wenn ein Konfigurationsbildschirm existiert, würde er typischerweise Folgendes enthalten:**

- **Modul aktivieren/deaktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist ein Standardschalter, um die Funktionalität des Moduls ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul erkennt aktiv den Standort nicht angemeldeter Benutzer und passt die Preisanzeige (inkl. Steuern/exkl. Steuern) entsprechend an.
    - *Wenn deaktiviert:* PrestaShop kehrt zu seinem Standardverhalten für nicht angemeldete Benutzer zurück, d.h. es werden Preise basierend auf dem Standardland des Shops oder einer globalen Einstellung angezeigt, ohne Geolokalisierungs-basierte Anpassungen.
  - **Empfohlener Wert:** JA (um die Kernfunktionalität des Moduls zu nutzen).
  - **Händlerszenario / Beispiel:** Wenn Sie vorübergehend ein Preisproblem beheben müssen oder für kurze Zeit das Standardverhalten von PrestaShop bevorzugen, könnten Sie es deaktivieren. Andernfalls lassen Sie es für eine genaue internationale Preisgestaltung aktiviert.
- **Geolokalisierungsdienstleister (Hypothetisch):**

  - **Was diese Einstellung bewirkt:** Wenn das Modul eine Auswahl anbieten würde, könnten Sie hier auswählen, welchen externen Dienst es zur Erkennung von Besucher-IP-Adressen und deren Zuordnung zu Ländern verwendet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf Anbieter A eingestellt:* Das Modul verwendet die Datenbank von Anbieter A für die IP-zu-Land-Zuordnung.
    - *Wenn auf Anbieter B eingestellt:* Das Modul verwendet die Datenbank von Anbieter B, was möglicherweise eine andere Genauigkeit oder Geschwindigkeit bietet.
  - **Empfohlener Wert:** Der Standard- oder von MyPresta.eu empfohlene Anbieter.
  - **Händlerszenario / Beispiel:** Sie könnten den Anbieter wechseln, wenn einer eine bessere Genauigkeit für Ihre Zielregionen bietet oder wenn Sie Probleme mit dem Standardanbieter haben.
- **Caching-Einstellungen (Hypothetisch):**

  - **Was diese Einstellung bewirkt:** Steuert, wie lange Geolokalisierungsdaten für Besucher zwischengespeichert werden, um die Leistung zu verbessern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Längere Cache-Dauer:* Schnellere Seitenladezeiten für wiederkehrende Besucher, aber potenziell langsamere Aktualisierungen, wenn sich die IP eines Besuchers ändert.
    - *Kürzere Cache-Dauer:* Mehr Echtzeit-Geolokalisierung, aber etwas höhere Serverlast.
  - **Empfohlener Wert:** Standard (normalerweise für ein ausgewogenes Verhältnis optimiert).
  - **Händlerszenario / Beispiel:** Wenn Ihre Website sehr viel Traffic hat und Sie Geschwindigkeit priorisieren, könnten Sie die Cache-Dauer erhöhen. Wenn Ihre Kundenbasis sehr mobil ist und häufig ihre IPs wechselt, könnte eine kürzere Dauer bevorzugt werden.

**Wichtiger Hinweis für Händler:**
Dieses Modul funktioniert, indem es zentrale PrestaShop-Klassen (`Product.php`, `Tax.php`, `TaxCalculator.php`) überschreibt. Dies ist eine leistungsstarke Technik, die direkt beeinflusst, wie PrestaShop Preise berechnet und anzeigt. Aus diesem Grund gibt es in der Regel nur sehr wenige, wenn überhaupt, konfigurierbare Optionen auf einem dedizierten Bildschirm. Die Stärke des Moduls liegt in seinen automatischen, im Hintergrund ablaufenden Anpassungen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Modul aktivieren/deaktivieren | Aktiviert | Schaltet die Geolokalisierungs-basierte Preisanpassungsfunktion des Moduls ein oder aus. |
| Modulkonfigurationsseite | *[Weitere Einstellungen, falls vorhanden]* | *[Standardwert]* | *[Zweck & Auswirkung]* |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Preise ändern sich für nicht angemeldete Benutzer nicht, selbst nach der Installation des Moduls.**
A1:

- **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul in Ihrem PrestaShop Back Office unter Module > Modul-Manager installiert und aktiviert ist.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie alle Caches (Smarty-Cache, Dateisystem-Cache usw.). Der Browser-Cache muss möglicherweise ebenfalls geleert werden.
- **Genauigkeit der Geolokalisierung:** Das Modul basiert auf der IP-Geolokalisierung. Obwohl im Allgemeinen genau, ist es nicht 100% perfekt. Testen Sie mit verschiedenen IPs (z. B. mit einem VPN), um dies zu bestätigen.
- **PrestaShop-Steuerregeln:** Überprüfen Sie, ob Ihre PrestaShop-Steuerregeln und Steuergruppen für verschiedene Länder korrekt konfiguriert sind. Das Modul verwendet diese bestehenden Regeln, um zu bestimmen, *welchen* Preis (inkl. oder exkl. Steuern) es anzeigen soll, sobald es das Land kennt.
- **Konflikte bei Überschreibungen:** Wenn Sie andere Module haben, die ebenfalls `Product.php`, `Tax.php` oder `TaxCalculator.php` überschreiben, kann es zu einem Konflikt kommen. Überprüfen Sie Ihren `override/`-Ordner auf andere Module, die diese Dateien ändern. Kontaktieren Sie den MyPresta.eu-Support, wenn Sie einen Konflikt vermuten.

**F2: Mein benutzerdefiniertes Theme scheint die Preise nach der Installation nicht korrekt anzuzeigen.**
A2: Dieses Modul beeinflusst hauptsächlich den *Wert* des angezeigten Preises, nicht dessen visuelle Gestaltung. Wenn Preise falsch ausgerichtet oder falsch gestylt aussehen, handelt es sich wahrscheinlich um ein CSS-Problem mit Ihrem Theme.

- **Theme-Kompatibilität:** Stellen Sie sicher, dass Ihr Theme vollständig mit Ihrer PrestaShop-Version kompatibel ist.
- **Elemente überprüfen:** Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Preiselemente zu überprüfen und festzustellen, ob benutzerdefiniertes CSS Ihres Themes in Konflikt steht.
- **Theme-Entwickler kontaktieren:** Wenn Sie ein benutzerdefiniertes Theme verwenden, wenden Sie sich an Ihren Theme-Entwickler, um Unterstützung bei der Gestaltung zu erhalten. Das Modul selbst führt kein neues CSS ein.

**F3: Betrifft dieses Modul angemeldete Benutzer oder Benutzer, die ihre Adresse eingegeben haben?**
A3: Nein, dieses Modul zielt speziell auf *nicht angemeldete Benutzer* ab, die ihre Adressinformationen noch nicht angegeben haben. Sobald sich ein Benutzer anmeldet oder seine Lieferadresse während des Checkouts eingibt, haben die nativen PrestaShop-Steuerberechnungs- und Anzeigelogiken (die das Land des Kunden bereits kennen) Vorrang. Dieses Modul schließt die Lücke für das anfängliche Browsing-Erlebnis.

**F4: Woher kennt das Modul das Land des Kunden?**
A4: Das Modul verwendet die IP-Adresse des Besuchers, um dessen geografischen Standort zu bestimmen. Dies ist eine Standardmethode für die Geolokalisierung in Webanwendungen. Es verwendet dann dieses erkannte Land, um die entsprechenden PrestaShop-Steuerregeln für die Preisanzeige anzuwenden.

**F5: Wird dieses Modul meinen Shop verlangsamen?**
A5: Das Modul ist auf Effizienz ausgelegt. Geolokalisierungsabfragen sind typischerweise schnell, und das Modul speichert Ergebnisse oft zwischen, um wiederholte Abfragen für denselben Besucher zu minimieren. Die Leistungsauswirkungen sollten vernachlässigbar sein. Wenn Sie eine Verlangsamung bemerken, stellen Sie sicher, dass Ihr Server die Mindestanforderungen von PrestaShop erfüllt und dass Ihre Caching-Mechanismen ordnungsgemäß konfiguriert sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Preise ohne Steuern für nicht angemeldete Benutzer nach Geolokalisierung“ erreicht seine Funktionalität hauptsächlich durch das Überschreibungssystem von PrestaShop. Anstatt sich auf traditionelle Hooks oder benutzerdefinierte Controller zu verlassen, modifiziert es direkt das Verhalten der PrestaShop-Kernklassen, die für die Produktpreisgestaltung und Steuerberechnung verantwortlich sind. Dies ermöglicht es, Geolokalisierungs-basierte Logik in den grundlegenden Preisbestimmungsprozess zu injizieren, um sicherzustellen, dass Preise angepasst werden, bevor sie überhaupt gerendert werden. Das Modul nutzt den `displayHeader`-Hook, um potenziell notwendiges JavaScript oder Styling einzubinden, obwohl seine Kernlogik PHP-basiert ist.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Seine Logik ist direkt in die Überschreibungen der Kernklassen eingebettet.

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernfunktionalität des Moduls liegt in seinen Überschreibungen der grundlegenden Preis- und Produktklassen von PrestaShop.

- **`taxprice/override/classes/Product.php`**

  - **Originalklasse:** `Product`
  - **Verantwortlichkeit:** Diese Überschreibung ist entscheidend. Die `Product`-Klasse ist für das Abrufen und Formatieren von Produktinformationen, einschließlich Preisen, verantwortlich. Diese Überschreibung fängt wahrscheinlich Methoden wie `getPrice()` oder verwandte Preisberechnungsmethoden ab, um die Geolokalisierungslogik *einzufügen, bevor* der Preis zur Anzeige zurückgegeben wird. Sie bestimmt, ob Preise mit oder ohne Steuern angezeigt werden sollen, basierend auf dem erkannten Land für nicht angemeldete Benutzer.
  - **Schlüssellogik:**
    - Erkennt, ob der aktuelle Benutzer ein Gast ist (nicht angemeldet).
    - Ermittelt das Land des Besuchers basierend auf der IP-Adresse (potenziell über eine Hilfsfunktion oder eine Drittanbieter-Dienstintegration).
    - Modifiziert den `TaxManagerFactory`-Kontext oder manipuliert direkt die `price_display_method` basierend auf den Steuerregeln des erkannten Landes und der PrestaShop-Konfiguration für dieses Land.
- **`taxprice/override/classes/tax/Tax.php`**

  - **Originalklasse:** `Tax`
  - **Verantwortlichkeit:** Die `Tax`-Klasse handhabt das Abrufen und Anwenden von Steuersätzen. Diese Überschreibung könnte verwendet werden, um sicherzustellen, dass die korrekten Steuersätze angewendet werden, *nachdem* die Geolokalisierung bestimmt hat, ob Preise mit oder ohne Steuern angezeigt werden sollen. Sie könnte ändern, wie Steuersätze abgerufen werden oder wie der `TaxCalculator` basierend auf dem Land des Gastes initialisiert wird.
- **`taxprice/override/classes/tax/TaxCalculator.php`**

  - **Originalklasse:** `TaxCalculator`
  - **Verantwortlichkeit:** Diese Klasse ist zentral für die Berechnung von Preisen mit und ohne Steuern. Die Überschreibung hier würde die endgültige Preisberechnung direkt beeinflussen. Sie stellt wahrscheinlich sicher, dass, wenn das Land eines Gastes bekannt ist, der `TaxCalculator` die korrekte `price_display_method` (z. B. `PS_TAX_EXC` oder `PS_TAX_INC`) verwendet, die den Steuerregeln des erkannten Landes entspricht, anstatt der Standardeinstellung des Shops.
- **`taxprice/override/classes/index.php`**

  - **Zweck:** Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um die Verzeichnisauflistung aus Sicherheitsgründen zu verhindern. Sie hat keine funktionale Auswirkung auf die Logik des Moduls.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Seine Kernfunktionalität wird serverseitig über PHP-Überschreibungen abgewickelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Es führt keine neuen visuellen Elemente ein, sondern ändert nur vorhandene Preiswerte.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`taxprice/views/displayHeader.tpl`**

  - **Hook:** `displayHeader`
  - **Zweck:** Dieses Template wird im `<head>`-Bereich jeder Front-Office-Seite gerendert. Es wird typischerweise verwendet, um JavaScript, CSS oder Meta-Tags einzubinden. Obwohl die Kernlogik des Moduls PHP-basiert ist, könnte dieses Template verwendet werden, um:
    - Client-seitige Variablen zu initialisieren, falls erforderlich (obwohl unwahrscheinlich angesichts der serverseitigen Natur).
    - Potenziell ein kleines Inline-Skript für Debugging oder sehr spezifische client-seitige Anpassungen einzubinden (z. B. das Setzen eines Cookies mit dem erkannten Land, obwohl dies für diese Art von Modul weniger üblich ist).
    - In Ermangelung dedizierter JS-Dateien könnte es jedes minimale Inline-JS enthalten, das benötigt wird.
- **`taxprice/views/script.tpl`**

  - **Zweck:** Dieser Template-Name deutet darauf hin, dass er JavaScript-Code enthalten könnte. Falls vorhanden, würde er wahrscheinlich über `displayHeader.tpl` oder einen anderen Hook eingebunden.
  - **Potenzieller Inhalt:**
    - Jegliche client-seitige Logik im Zusammenhang mit der Geolokalisierung (z. B. die Verwendung einer client-seitigen IP-Lookup-API, obwohl weniger zuverlässig als serverseitig).
    - Skripte zur Handhabung dynamischer Preisaktualisierungen, wenn das Modul auch client-seitiges Umschalten oder Echtzeitanpassungen unterstützt (unwahrscheinlich angesichts der Beschreibung).
    - Debugging-Skripte oder einfache Datenausgabe für Entwickler.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen.
  - Es stützt sich auf vorhandene PrestaShop-Tabellen für Produkte (`ps_product`, `ps_product_shop`), Steuern (`ps_tax`, `ps_tax_rule`, `ps_tax_rule_group`) und Konfiguration (`ps_configuration`).
  - Konfigurationswerte werden in `ps_configuration` unter Verwendung der Standardmethoden `Configuration::get()` und `Configuration::updateValue()` gespeichert, typischerweise mit dem Präfix `TAXPRICE_`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um `displayHeader.tpl` und potenziell `script.tpl` für notwendige client-seitige Skripte oder Meta-Informationen einzubinden. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts. | (Implizit, nicht explizit aufgeführt, aber üblich für preisbezogene Module) Kann den Cache für Produktpreise leeren, um sicherzustellen, dass Überschreibungen erneut angewendet werden. |
| `actionProductAdd` | Nach dem Hinzufügen eines Produkts. | (Implizit) Ähnlich wie `actionProductUpdate`. |
| `actionTaxManagerFactory` | Wenn `TaxManagerFactory` initialisiert wird. | (Implizit, entscheidend für dieses Modul) Die Überschreibungen in `Tax.php` und `TaxCalculator.php` würden das Verhalten der Steuerberechnung in diesem Stadium effektiv „hooken“ oder modifizieren, auch wenn es keine formale `hook`-Registrierung ist. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung mit dem Modul „Preise ohne Steuern für nicht angemeldete Benutzer nach Geolokalisierung“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, umfassenden Support zu bieten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.
