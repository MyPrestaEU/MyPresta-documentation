---
title: "Bestellbestätigungsseite für kostenlose Bestellungen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bestellbestätigungsseite für kostenlose Bestellungen“ von MyPresta.eu."
sidebar:
  label: "Bestellbestätigungsseite für kostenlose Bestellungen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order confirmation page for free orders auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/order-confirmation-page-for-free-orders.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/order-confirmation-page-for-free-orders/)
>
> ---


# Bestellbestätigungsseite für kostenlose Bestellungen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Bestellbestätigungsseite für kostenlose Bestellungen)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul. Er ist unkompliziert und ermöglicht es Ihnen, die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren.

![Screenshot der Modulkonfiguration Platzhalter]

- **Bestellbestätigungsseite aktivieren**
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität. Er steuert, ob kostenlose Bestellungen die Standard-Bestätigungsseite anzeigen oder zum Standardverhalten von PrestaShop (Weiterleitung zur Bestellhistorie) zurückkehren.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (ausgewählt „Aktiviert“):* Alle Bestellungen, einschließlich derer mit einem Gesamtwert von 0,00 €, zeigen nach dem Checkout die Standardseite „Bestellbestätigung“ an.
    - *Wenn deaktiviert (ausgewählt „Deaktiviert“):* Kostenlose Bestellungen kehren zum Standardverhalten von PrestaShop zurück, indem Kunden direkt zu ihrer Bestellhistorie weitergeleitet werden, anstatt die Bestätigungsseite anzuzeigen.
  - **Empfohlener Wert:** **Aktiviert**. Dies ist der Hauptzweck des Moduls und bietet ein besseres Kundenerlebnis.
  - **Händlerszenario / Beispiel:** Wenn Sie einen kostenlosen E-Book-Download anbieten, stellt die Aktivierung sicher, dass Kunden eine Bestätigungsseite mit einem Download-Link sehen, anstatt durch eine direkte Weiterleitung zu ihrer Bestellhistorie verwirrt zu werden. Wenn Sie vorübergehend zum Standard-PrestaShop-Verhalten für kostenlose Bestellungen zurückkehren möchten (z. B. für bestimmte Tests), können Sie es deaktivieren.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Bestellbestätigungsseite aktivieren | Aktiviert | Steuert, ob kostenlose Bestellungen die Standard-Bestellbestätigungsseite anzeigen (Aktiviert) oder zur Bestellhistorie weiterleiten (Deaktiviert). |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F: Meine kostenlosen Bestellungen leiten immer noch zur Bestellhistorie weiter, obwohl das Modul aktiviert ist. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Bestellbestätigungsseite für kostenlose Bestellungen“ installiert und aktiviert ist.
2. **Modulkonfiguration überprüfen:** Gehen Sie zu **Module > Modul-Manager > Konfigurieren** für dieses Modul und stellen Sie sicher, dass die Einstellung „Bestellbestätigungsseite aktivieren“ auf **„Aktiviert“** gesetzt ist.
3. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Dies ist oft nach Änderungen an der Modulkonfiguration notwendig.
4. **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder in einem Inkognito-/privaten Browserfenster zu testen, um lokale Caching-Probleme auszuschließen.

**F: Wird dieses Modul meine bezahlten Bestellungen beeinflussen?**
A: Nein, dieses Modul zielt speziell auf das Verhalten von Bestellungen mit einem Gesamtwert von 0,00 € ab. Bezahlte Bestellungen werden weiterhin die Standard-Bestellbestätigungsseite anzeigen, wie sie es immer getan haben.

**F: Benötigt dieses Modul spezielle Theme-Anpassungen?**
A: Nein, das Modul funktioniert, indem es einen PrestaShop-Core-Controller überschreibt. Es nutzt die Bestellbestätigungsseiten-Vorlage Ihres bestehenden Themes. Es sind keine Theme-Anpassungen erforderlich. Wenn Ihre Bestellbestätigungsseite für bezahlte Bestellungen gut aussieht, wird sie auch für kostenlose Bestellungen gut aussehen.

**F: Was, wenn ich unterschiedliche Inhalte auf der Bestätigungsseite für kostenlose Bestellungen im Vergleich zu bezahlten Bestellungen anzeigen möchte?**
A: Dieses Modul stellt sicher, dass die *gleiche* Bestätigungsseite angezeigt wird. Um unterschiedliche Inhalte anzuzeigen, müssten Sie Ihre `order-confirmation.tpl`-Vorlage (normalerweise zu finden unter `themes/your-theme/templates/checkout/`) anpassen, um bedingte Logik basierend auf dem Bestellwert oder der Zahlungsmethode einzufügen. Dies würde Entwicklerunterstützung erfordern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Bestellbestätigungsseite für kostenlose Bestellungen“ erreicht seine Funktionalität durch das Überschreiben eines PrestaShop-Front-Controllers. Insbesondere zielt es auf `OrderConfirmationController` ab, um die Weiterleitungslogik zu ändern, die nach einer kostenlosen Bestellung erfolgt. Dies ist ein Standard-PrestaShop-Override-Mechanismus, der minimale Auswirkungen auf Kerndateien gewährleistet und eine einfache Deinstallation ermöglicht.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  - `freeorderconfirmation/override/controllers/front/index.php`
    - Diese Datei ist ein Platzhalter oder ein Artefakt des Override-Prozesses. In PrestaShop 1.7+ werden Overrides typischerweise durch Platzieren der überschriebenen Klasse direkt im Verzeichnis `override/classes` oder `override/controllers` gehandhabt, und PrestaShops Autoloader erledigt den Rest. Diese `index.php`-Datei selbst enthält keine Klassendefinition oder direkte Logik für die Funktionalität des Moduls. Ihre Anwesenheit stellt sicher, dass der Override-Mechanismus für den `OrderConfirmationController` korrekt ausgelöst wird.
  - `freeorderconfirmation/override/controllers/front/OrderConfirmationController.php`
    - **Klassenname & Elternklasse**: `OrderConfirmationController` (überschreibt die Core-Klasse `OrderConfirmationController`).
    - **Verantwortlichkeit**: Dies ist der Kern der Modulfunktionalität. Es überschreibt die Methode `initContent()` (oder ähnliche Logik innerhalb des Lebenszyklus des Controllers) des ursprünglichen `OrderConfirmationController`. Die ursprüngliche PrestaShop-Logik prüft, ob der Bestellwert null ist, und leitet den Kunden in diesem Fall zu seiner Bestellhistorie weiter. Dieser überschriebene Controller entfernt oder modifiziert diese bedingte Weiterleitung und stellt sicher, dass die Methode `initContent()` des Standard-`OrderConfirmationController` (die die Bestätigungsseite rendert) immer ausgeführt wird, auch bei kostenlosen Bestellungen. Er verhindert effektiv den `Tools::redirect()`-Aufruf für Bestellungen mit Nullwert.

### 4.3 Core-Klassen & Modelle (`classes/`)

In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Das Modul arbeitet rein durch das Überschreiben eines PrestaShop-Core-Controllers.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Modul verlässt sich auf das vorhandene Styling des Themes für die Bestellbestätigungsseite.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Das Modul stellt sicher, dass die *Standard*-PrestaShop-Bestellbestätigungsvorlage (typischerweise `themes/your-theme/templates/checkout/order-confirmation.tpl`) für kostenlose Bestellungen gerendert wird, genau wie für bezahlte Bestellungen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. `freeorderconfirmation_oc`) in der Tabelle `ps_configuration`.
  - Es speichert auch `mypresta_updates`, `update_`, `updatev_` zur internen Update-Verfolgung durch MyPresta.eu.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) setzt. | Wird vom Modul verwendet, um potenziell eigene Assets für die Back-Office-Konfigurationsseite einzubinden. Im Fall dieses Moduls wird es wahrscheinlich verwendet, um sicherzustellen, dass das Konfigurationsformular des Moduls korrekt in der PrestaShop-Admin-Oberfläche gerendert wird, auch wenn keine benutzerdefinierten Assets explizit geladen werden. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und technischen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Bestellbestätigungsseite für kostenlose Bestellungen“ zur Verfügung.
