---
title: "Allani Tracking – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Allani Tracking von MyPresta.eu."
sidebar:
  label: "Allani Tracking – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Allani tracking auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/allani-tracking.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/allani-tracking/)
>
> ---


# Allani Tracking

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5 (Das Modul ist so konzipiert, dass es mit einer breiten Palette von PHP-Versionen funktioniert, bis zur neuesten stabilen Version, die von PrestaShop 1.7.x und zukünftigen Versionen unterstützt wird.)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in jeder modernen PrestaShop-Hosting-Umgebung verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Allani Tracking“, um auf dessen Einstellungen zuzugreifen.

#### Bestellidentifikation

Dieser Abschnitt steuert, wie das Modul Bestelldaten identifiziert und an Allani sendet.

- **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung für das Modul. Sie bestimmt, ob das Modul aktiv ist und Bestelldaten an Allani sendet.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul sendet automatisch Bestelldetails (Produkt-IDs, Bestellwert, Bestell-ID) an die Allani-Plattform, jedes Mal, wenn ein Kunde eine Bestellung in Ihrem PrestaShop-Shop erfolgreich abschließt. Dies ist unerlässlich, damit Allani Ihre Verkäufe verfolgen kann.
  - *Wenn deaktiviert (NEIN):* Das Modul stellt die Übertragung von Bestelldaten an Allani ein. Dies bedeutet, dass Allani keine Echtzeit-Updates zu Ihren Verkäufen erhält, was sich möglicherweise auf Ihre Analysen und Berichte auf deren Plattform auswirkt.
- **Empfohlener Wert:** **JA**. Um den Allani Tracking-Dienst vollständig zu nutzen, sollte diese Einstellung immer aktiviert sein.
- **Händlerszenario / Beispiel:** Wenn Sie sich gerade bei Allani angemeldet haben und sofort mit der Verfolgung Ihrer Verkäufe beginnen möchten, würden Sie diese Einstellung aktivieren. Wenn Sie die Datenübertragung an Allani vorübergehend für Wartungs- oder Testzwecke pausieren möchten, könnten Sie sie deaktivieren, aber denken Sie daran, sie danach wieder zu aktivieren.

#### Andere interne Einstellungen (Nicht direkt vom Händler konfigurierbar)

Möglicherweise sehen Sie andere Konfigurationsschlüssel wie `mypresta_updates`, `update_`, `updatev_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Dies sind interne Einstellungen, die vom Modul für eigene Update-Prüfungen oder zur Interaktion mit den Kernfunktionen von PrestaShop (wie Sprachbehandlung) verwendet werden. Sie müssen diese nicht konfigurieren, und sie sind nicht als benutzerbearbeitbare Optionen verfügbar.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Bestellidentifikation | JA | Steuert, ob Bestelldaten an Allani gesendet werden. **Aktivieren** für Allani Tracking. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber keine Änderungen in meinem Shop. Funktioniert es?**
A: Ja, das ist normal! Das Allani Tracking-Modul arbeitet vollständig im Hintergrund. Es fügt keine sichtbaren Elemente zum Front-Office Ihres Shops hinzu. Seine Funktion ist es, Daten an Allani zu senden, nachdem eine Bestellung aufgegeben wurde. Um zu bestätigen, dass es funktioniert, geben Sie eine Testbestellung auf und überprüfen Sie dann Ihr Allani-Konto auf die neuen Bestelldaten.

**F: Allani empfängt meine Bestelldaten nicht. Was soll ich überprüfen?**
A:

1. **Modul aktiviert:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Allani Tracking“ und stellen Sie sicher, dass es installiert und aktiviert ist.
2. **Konfigurationseinstellung:** Klicken Sie auf „Konfigurieren“ für das Modul und stellen Sie sicher, dass „Bestellidentifikation“ auf **JA** eingestellt ist.
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Einstellungen wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
4. **Allani-Konto:** Überprüfen Sie Ihre Allani-Kontoeinstellungen oder kontaktieren Sie den Allani-Support, um sicherzustellen, dass Ihr Shop auf deren Seite korrekt verknüpft ist.
5. **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Installation heruntergeladen haben (z.B. 1.7.x, 1.6.x).

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Nein, die Auswirkungen auf die Leistung Ihres Shops sind vernachlässigbar. Das Tracking-Skript wird nur auf der Bestellbestätigungsseite ausgeführt, die typischerweise der letzte Schritt im Kundenweg ist. Die Datenübertragung ist schnell und asynchron, was bedeutet, dass sie das Laden der Seite für Ihre Kunden nicht verzögert.

**F: Unterstützt dieses Modul mehrsprachige oder Multi-Store-Setups?**
A: Das Modul sendet hauptsächlich numerische Daten und Produkt-IDs, die sprachunabhängig sind. Für Multi-Store sollte es korrekt funktionieren, solange das Modul für jeden Store-Kontext, in dem Sie Bestellungen verfolgen möchten, aktiviert und konfiguriert ist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Allani Tracking` ist ein leichtgewichtiges PrestaShop-Modul, das für einen einzigen Zweck entwickelt wurde: das Senden von Bestellbestätigungsdaten an die Allani-Plattform. Es folgt einer Standard-PrestaShop-Modulstruktur und verwendet hauptsächlich Hooks, um seine Tracking-Logik zu injizieren. Die Kernfunktionalität liegt in der Hauptmodulklasse (`allanitracking.php`), die Installation, Deinstallation, Konfiguration und Hook-Registrierung handhabt. Es führt keine benutzerdefinierten Controller, Modelle oder komplexen JavaScript/CSS-Assets ein, sondern konzentriert sich ausschließlich auf die Datenübertragung über ein Smarty-Template, das in den `displayOrderConfirmation`-Hook injiziert wird.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Logik des Moduls wird direkt innerhalb des `displayOrderConfirmation`-Hooks über ein Smarty-Template gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird direkt über die `getContent()`-Methode der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es werden keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen von diesem Modul eingeführt. Die gesamte Logik ist in `allanitracking.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- Es werden keine benutzerdefinierten JavaScript-Dateien von diesem Modul eingeschlossen oder verwendet. Das Tracking-Skript ist direkt in das `displayOrderConfirmation.tpl`-Template eingebettet.

### 4.5 CSS-Stylesheets (`views/css/`)

- Es werden keine benutzerdefinierten CSS-Dateien von diesem Modul eingeschlossen oder verwendet, da es keine sichtbaren Front-Office-Komponenten hat.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um das Tracking-Skript in das Front Office zu injizieren.

- **Hook-Templates (`views/templates/hook/`)**:

  - `allanitracking/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Zweck**: Dieses Template wird auf der Bestellbestätigungsseite (nach einem erfolgreichen Kauf) gerendert. Es enthält die Kernlogik zum Senden von Bestelldaten an Allani. Es greift auf die Smarty-Variablen `$order` und `$products` zu, die von PrestaShop an diesen Hook übergeben werden, um `orderValue`, `orderID` und `productIds` zu extrahieren. Das Template konstruiert und führt dann das notwendige JavaScript aus, um diese Daten an die Allani-Plattform zu übertragen.
  - `allanitracking/views/templates/hook/header.tpl`
    - **Hook**: `displayHeader` (oder `header` in älteren Versionen)
    - **Zweck**: Dieses Template wird typischerweise verwendet, um globale JavaScript- oder CSS-Dateien in den `<head>`-Bereich der Seite einzufügen. Im Kontext dieses Moduls könnte es verwendet werden, um notwendige globale Allani-Skripte oder Meta-Tags einzuschließen, obwohl die primäre Datenübertragung von `displayOrderConfirmation.tpl` gehandhabt wird. Angesichts der Modulbeschreibung enthält es wahrscheinlich eine minimale Einrichtung oder einen Platzhalter.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfiguration in der Tabelle `ps_configuration`, speziell den Schlüssel `ALLANI_ORDER_TRACK`.
  - Es verwendet auch Standard-PrestaShop-Konfigurationsschlüssel für Update-Prüfungen (`mypresta_updates`, `update_`, `updatev_`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` / `header` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell für die globale Allani-Skriptinitialisierung oder Meta-Tags verwendet. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite, nach einem erfolgreichen Kauf. | **Primärer Hook für dieses Modul.** Injiziert den JavaScript-Code, um Bestelldetails (Produkt-IDs, Bestellwert, Bestell-ID) an die Allani-Plattform zu senden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Allani Tracking“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
