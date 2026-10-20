---
title: "Kelkoo Sales Tracking Integration – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kelkoo Sales Tracking Integration“ von MyPresta.eu."
sidebar:
  label: "Kelkoo Sales Tracking Integration"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Kelkoo sales tracking integration auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/kelkoo-sales-tracking-integration.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/kelkoo-sales-tracking-integration/)
>
> ---


# Kelkoo Sales Tracking Integration

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 8.x, 1.7.x, 1.6.x, 1.5.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die meisten PrestaShop-Module erforderlich und in jeder modernen Hosting-Umgebung verfügbar. Keine speziellen oder ungewöhnlichen Anforderungen für dieses Modul.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Kelkoo Sales Tracking Integration“. Es wird ein einfacher Konfigurationsbildschirm angezeigt.

#### Kelkoo Tracking ID
-   **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Hier geben Sie Ihre eindeutige Tracking-ID ein, die Sie von Kelkoo erhalten haben. Diese ID teilt Kelkoo mit, welchem Händler (Ihrem Shop) die Verkaufsdaten gehören.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Bei korrekter Eingabe:* Das Modul verwendet diese ID, um Verkaufsdaten an Ihr spezifisches Kelkoo-Konto zu senden, sodass Kelkoo Verkäufe Ihren Kampagnen zuordnen kann.
    -   *Bei leerer oder falscher Eingabe:* Die Verkaufsverfolgung funktioniert nicht korrekt, und Kelkoo erhält keine Daten über Käufe, die über deren Plattform getätigt wurden, was es unmöglich macht, Ihre Kampagnenleistung zu messen.
-   **Empfohlener Wert:** Geben Sie die exakte Tracking-ID ein, die Ihnen von Kelkoo zur Verfügung gestellt wurde. Dies ist normalerweise eine numerische oder alphanumerische Zeichenfolge.
-   **Händlerszenario / Beispiel:** Sie haben ein Händlerkonto bei Kelkoo eingerichtet. Kelkoo stellt Ihnen eine eindeutige „Kelkoo Tracking ID“ oder „Merchant ID“ zur Verfügung. Sie müssen diese ID exakt in dieses Feld kopieren und einfügen. Ohne sie ist die Integration unvollständig.

#### Tracking aktivieren
-   **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter, um die Kelkoo-Verkaufsverfolgungsfunktion in Ihrem gesamten Shop zu aktivieren oder zu deaktivieren.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Bei Aktivierung (JA):* Das Modul injiziert aktiv die notwendigen Tracking-Skripte und sendet Verkaufsdaten an Kelkoo auf der Bestellbestätigungsseite.
    -   *Bei Deaktivierung (NEIN):* Das Modul stellt alle Tracking-Aktivitäten ein. Es werden keine Skripte injiziert und keine Verkaufsdaten an Kelkoo gesendet.
-   **Empfohlener Wert:** JA. Sie sollten dies nur deaktivieren, wenn Sie die Verkaufsverfolgung über Kelkoo vorübergehend stoppen möchten oder Fehler beheben.
-   **Händlerszenario / Beispiel:** Sie haben Ihr Kelkoo-Setup abgeschlossen und möchten sofort mit der Verkaufsverfolgung beginnen. Stellen Sie dies auf JA. Wenn Sie Ihre Kelkoo-Kampagnen pausieren oder Wartungsarbeiten durchführen müssen, könnten Sie es vorübergehend auf NEIN setzen.

### 2.2 Konfigurations-Kurzübersichtstabelle
| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Kelkoo Tracking ID | Ihre Kelkoo ID | Eindeutiger Bezeichner für Ihr Kelkoo-Händlerkonto. Wesentlich für die Verkaufszuordnung. |
| Modulkonfiguration | Tracking aktivieren | JA | Aktiviert/deaktiviert die Kelkoo-Verkaufsverfolgungsfunktion. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber Kelkoo zeigt keine Verkäufe an. Was soll ich tun?**
A:
1.  **Überprüfen Sie Ihre Kelkoo Tracking ID:** Stellen Sie sicher, dass sie genau so eingegeben wurde, wie sie von Kelkoo bereitgestellt wurde, ohne zusätzliche Leerzeichen oder Zeichen.
2.  **Stellen Sie sicher, dass „Tracking aktivieren“ auf JA steht:** Dieser Schalter muss aktiv sein, damit das Modul funktioniert.
3.  **Leeren Sie den PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal kann zwischengespeicherter Inhalt verhindern, dass neue Moduleinstellungen wirksam werden.
4.  **Führen Sie einen Testkauf durch:** Schließen Sie eine vollständige Bestellung in Ihrem Shop ab, um das Tracking auszulösen.
5.  **Kontaktieren Sie den Kelkoo-Support:** Wenn alle Einstellungen korrekt sind und Sie den Cache geleert haben, wenden Sie sich an das Support-Team von Kelkoo. Diese können oft auf ihrer Seite überprüfen, ob Daten empfangen werden oder ob ein Problem mit Ihrer Kontoeinrichtung auf deren Plattform vorliegt.

**F: Wird dieses Modul meine Website verlangsamen?**
A: Nein, das Modul ist sehr leichtgewichtig. Es injiziert lediglich ein kleines, nicht-blockierendes JavaScript-Snippet in den Header und sendet Daten auf der Bestellbestätigungsseite. Dieser Prozess ist optimiert, um die Ladezeit Ihres Shops oder das Kundenerlebnis nicht zu beeinträchtigen.

**F: Funktioniert dieses Modul mit Multi-Store-Setups?**
A: Ja, das Modul sollte in einer Multi-Store-Umgebung korrekt funktionieren. Sie konfigurieren die Kelkoo Tracking ID für jeden Shop einzeln, wenn diese separate Kelkoo-Konten haben, oder verwenden dieselbe ID, wenn Sie alle Shops unter einem Kelkoo-Konto verfolgen.

**F: Ich verwende ein benutzerdefiniertes Theme. Funktioniert dieses Modul trotzdem?**
A: Ja, das Modul verwendet Standard-PrestaShop-Hooks (`displayHeader`, `displayOrderConfirmation`), die in allen gut programmierten Themes fast universell vorhanden sind. Es ist nicht auf spezifische Theme-Elemente angewiesen, daher sollte es mit benutzerdefinierten Themes kompatibel sein. Sollten Probleme auftreten, stellen Sie sicher, dass Ihr benutzerdefiniertes Theme diese Kern-PrestaShop-Hooks korrekt implementiert.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul „Kelkoo Sales Tracking Integration“ ist ein unkompliziertes PrestaShop-Modul, das zur Integration des Kelkoo Sales Tracking Pixels entwickelt wurde. Es nutzt hauptsächlich das Hook-System von PrestaShop, um ein globales Tracking-Skript in den Header und ein Conversion-Tracking-Skript auf der Bestellbestätigungsseite einzufügen. Es folgt einer grundlegenden PrestaShop-Modulstruktur, wobei seine Kernlogik in der Hauptmoduldatei und den Template-Dateien für das Hook-Rendering enthalten ist. Es gibt keine benutzerdefinierten Controller, Modelle oder komplexen JavaScript-/CSS-Assets, die über das für den Tracking-Pixel Notwendige hinausgehen.

### 4.2 Controller (`controllers/`)
- **Front-Office-Controller**: Keine. Alle Front-Office-Funktionalitäten werden über Hooks innerhalb der Hauptmoduldatei abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird direkt durch die Methode `getContent()` in der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)
- In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Die gesamte Logik befindet sich in der Hauptmoduldatei `Kelkoo.php` (oder `index.php` in älteren Strukturen).

### 4.4 JavaScript-Assets (`views/js/`)
- Es sind keine dedizierten JavaScript-Dateien im Modul enthalten. Das notwendige Kelkoo-Tracking-Skript wird dynamisch generiert und direkt über Smarty-Templates oder den `displayHeader`-Hook in den HTML-Code eingefügt.

### 4.5 CSS-Stylesheets (`views/css/`)
- Es sind keine dedizierten CSS-Dateien im Modul enthalten. Das Modul hat keine visuellen Front-Office-Komponenten, und seine Back-Office-Konfiguration verwendet Standard-PrestaShop-Formularstile.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
- **Hook-Templates (`views/templates/hook/`)**:
    *   `kelkoo/views/templates/hook/displayOrderConfirmation.tpl`:
        *   **Hook**: `displayOrderConfirmation`
        *   **Zweck**: Dieses Template wird auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf gerendert. Es ist verantwortlich für die Generierung des Kelkoo Sales Tracking Pixels (KST) mit dynamischen Bestelldetails (Bestell-ID, Gesamtbetrag, Produktdetails). Es ruft die an den Hook übergebenen Bestellinformationen ab und formatiert sie gemäß den Kelkoo-Spezifikationen.
    *   `kelkoo/views/templates/hook/header.tpl`:
        *   **Hook**: `displayHeader`
        *   **Zweck**: Dieses Template wird im `<head>`-Bereich jeder Seite gerendert. Es soll alle globalen Kelkoo-Tracking-Skripte oder Initialisierungen enthalten, die auf der gesamten Website vorhanden sein müssen, obwohl für einfaches Sales Tracking die primäre Logik oft in `displayOrderConfirmation` liegt. Es könnte einen grundlegenden Kelkoo-Basispixel oder einen Platzhalter für zukünftige Kelkoo-Funktionen enthalten.

- **Admin-Templates (`views/templates/admin/`)**: Keine. Das Konfigurationsformular wird direkt innerhalb von `getContent()` unter Verwendung der PrestaShop-Helper-Formular-Klassen erstellt.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map
- **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Konfigurationseinstellungen (`Kelkoo Tracking ID`, `Enable Tracking`) werden in der Tabelle `ps_configuration` (oder `_configuration`-Präfix) unter Schlüsseln wie `KELKOO_TRACKING_ID` und `KELKOO_ENABLED` gespeichert.

- **Registrierte Hooks-Tabelle**:
  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  |---|---|---|
  | `displayHeader` | Wird im `<head>`-Bereich jeder Seite gerendert. | Fügt globale Kelkoo-Tracking-Skripte oder Basispixel ein. |
  | `displayOrderConfirmation` | Wird auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf gerendert. | Sendet detaillierte Verkaufsdaten (Bestell-ID, Betrag, Produkte) an Kelkoo zur Conversion-Verfolgung. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und den Zugriff auf die neuesten Versionen des Moduls „Kelkoo Sales Tracking Integration“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
