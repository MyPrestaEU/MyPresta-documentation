---
title: "Perfect Money – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das Perfect Money PrestaShop-Modul von MyPresta.eu."
sidebar:
  label: "Perfect Money – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Perfect Money auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/perfect-money.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/perfect-money/)
>
> ---


# Perfect Money

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 1.6.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine sichere Kommunikation mit dem Zahlungsgateway erforderlich, die auf modernen Hosting-Umgebungen fast immer verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Perfect Money)

Dies ist der Hauptkonfigurationsbildschirm für das Perfect Money-Modul, auf dem Sie Ihre Perfect Money-Kontodaten eingeben und festlegen, wie die Zahlungsmethode in Ihrem Shop angezeigt und funktioniert.

#### **Perfect Money Kontoeinstellungen**

- **Was diese Einstellung bewirkt:** Diese Felder sind entscheidend, um Ihren PrestaShop-Shop mit Ihrem Perfect Money-Händlerkonto zu verbinden. Sie teilen dem Modul mit, an welches Perfect Money-Konto Zahlungen gesendet werden sollen und wie Transaktionen überprüft werden sollen.
- **Auswirkungen einer Änderung dieser Einstellung:** Falsche Werte verhindern, dass Kunden Zahlungen tätigen können, oder Zahlungen werden möglicherweise nicht korrekt Ihrem Konto zugeordnet.
  - *Bei korrekter Konfiguration:* Zahlungen werden erfolgreich über Ihr Perfect Money-Konto verarbeitet.
  - *Bei inkorrekter Konfiguration:* Zahlungen schlagen fehl, oder Kunden stoßen während des Checkouts auf Fehler.
- **Empfohlener Wert:** Geben Sie die genauen Details ein, die Ihnen von Ihrem Perfect Money-Händlerkonto zur Verfügung gestellt wurden.
- **Händlerszenario / Beispiel:** Sie haben ein Händlerkonto bei Perfect Money registriert. Sie erhalten eine „Perfect Money Account ID“ (z. B. U1234567) und einen „Perfect Money Account Name“ (z. B. MyStorePayments). Sie richten außerdem eine „Perfect Money Alternate Passphrase“ in Ihren Perfect Money-Kontoeinstellungen für erhöhte Sicherheit ein. Sie müssen diese genauen Werte hier eingeben.

#### **Zahlungsanzeigeeinstellungen**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt steuert, wie die Perfect Money-Zahlungsoption Ihren Kunden während des Checkouts präsentiert wird.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Kunden sehen die Perfect Money-Option und können diese zur Zahlung auswählen.
  - *Wenn deaktiviert:* Perfect Money wird nicht als Zahlungsoption angezeigt.
- **Empfohlener Wert:** „JA“ (Aktiviert), wenn Sie Perfect Money als Zahlungsmethode anbieten möchten.
- **Händlerszenario / Beispiel:** Sie möchten Perfect Money als Zahlungsoption anbieten. Sie aktivieren es. Wenn Sie es vorübergehend für Wartungsarbeiten deaktivieren möchten oder Perfect Money nicht mehr akzeptieren möchten, würden Sie es auf „NEIN“ setzen.

#### **Bestellstatus-Einstellungen**

- **Was diese Einstellung bewirkt:** Diese Einstellungen bestimmen den Status, den eine Bestellung in Ihrem PrestaShop Back Office haben wird, nachdem ein Kunde eine Zahlung über Perfect Money abgeschlossen hat.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „Zahlung akzeptiert“ gesetzt:* Bestellungen, die über Perfect Money bezahlt wurden, werden in Ihrem PrestaShop Back Office automatisch als „Zahlung akzeptiert“ markiert, was eine erfolgreiche Transaktion anzeigt.
  - *Wenn auf „Zahlungsfehler“ gesetzt:* Wenn eine Zahlung fehlschlägt oder ein Problem auftritt, wird die Bestellung mit diesem Status markiert.
- **Empfohlener Wert:**
  - **Bestellstatus für eine erfolgreiche Zahlung:** „Zahlung akzeptiert“ (oder ein ähnlicher Status, den Sie für erfolgreiche Zahlungen konfiguriert haben).
  - **Bestellstatus für einen Zahlungsfehler:** „Zahlungsfehler“ (oder ein ähnlicher Status für fehlgeschlagene Zahlungen).
- **Händlerszenario / Beispiel:** Ein Kunde bezahlt erfolgreich mit Perfect Money. Sie möchten diese Bestellungen schnell als bereit zur Bearbeitung identifizieren. Indem Sie den „Bestellstatus für eine erfolgreiche Zahlung“ auf „Zahlung akzeptiert“ setzen, weiß Ihr Team sofort, dass die Zahlung eingegangen ist. Wenn ein Kunde versucht zu zahlen, die Transaktion jedoch fehlschlägt, wird die Bestellung als „Zahlungsfehler“ markiert, sodass Sie nachfassen oder der Kunde es erneut versuchen kann.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Perfect Money Account ID | Ihre Perfect Money Account ID (z. B. U1234567) | Identifiziert Ihr Perfect Money Händlerkonto für den Empfang von Zahlungen. **KRITISCH für die Zahlungsabwicklung.** |
| Modulkonfiguration | Perfect Money Account Name | Ihr Perfect Money Account Name | Der Name, der mit Ihrem Perfect Money Konto verknüpft ist. |
| Modulkonfiguration | Perfect Money Alternate Passphrase | Ihre Perfect Money Alternate Passphrase | Sicherheitsschlüssel zur Überprüfung von Transaktionen. Diesen legen Sie in Ihrem Perfect Money Konto fest. **KRITISCH für die Sicherheit.** |
| Modulkonfiguration | Perfect Money Zahlung aktivieren | JA | Schaltet die Sichtbarkeit von Perfect Money als Zahlungsoption auf Ihrer Checkout-Seite um. |
| Modulkonfiguration | Bestellstatus für eine erfolgreiche Zahlung | Zahlung akzeptiert | Der PrestaShop-Bestellstatus, der Bestellungen zugewiesen wird, die erfolgreich über Perfect Money bezahlt wurden. |
| Modulkonfiguration | Bestellstatus für einen Zahlungsfehler | Zahlungsfehler | Der PrestaShop-Bestellstatus, der Bestellungen zugewiesen wird, bei denen die Perfect Money-Zahlung fehlgeschlagen ist. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden sehen einen Fehler, wenn sie versuchen, mit Perfect Money zu bezahlen.**
A:

-   **Überprüfen Sie Ihre Perfect Money Kontoeinstellungen:** Überprüfen Sie nochmals, ob Ihre „Perfect Money Account ID“, „Perfect Money Account Name“ und „Perfect Money Alternate Passphrase“ *genau* so eingegeben wurden, wie sie in Ihrem Perfect Money Händlerkonto erscheinen. Schon ein kleiner Tippfehler kann Fehler verursachen.
-   **Überprüfen Sie den Perfect Money Kontostatus:** Melden Sie sich direkt in Ihrem Perfect Money Konto an, um sicherzustellen, dass es aktiv, in gutem Zustand und für den Empfang von Zahlungen konfiguriert ist.
-   **Überprüfen Sie die PrestaShop Fehlerprotokolle:** Navigieren Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Protokolle**, um zu sehen, ob spezifische Fehler im Zusammenhang mit dem Perfect Money-Modul aufgezeichnet werden.

**F: Bestellungen werden nach einer erfolgreichen Perfect Money-Zahlung nicht als „Zahlung akzeptiert“ markiert.**
A:

-   **Überprüfen Sie die Bestellstatus-Einstellungen:** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass „Bestellstatus für eine erfolgreiche Zahlung“ auf den korrekten Status (z. B. „Zahlung akzeptiert“) eingestellt ist.
-   **Perfect Money IPN/Callback:** Stellen Sie sicher, dass Ihr Perfect Money-Konto korrekt konfiguriert ist, um Instant Payment Notifications (IPN) oder Callbacks an Ihren PrestaShop-Shop zu senden. Das Modul ist auf diese Benachrichtigungen angewiesen, um Bestellstatus zu aktualisieren. Obwohl das Modul die URL handhabt, können Perfect Money-Kontoeinstellungen manchmal stören.

**F: Perfect Money wird auf meiner Checkout-Seite nicht als Zahlungsoption angezeigt.**
A:

-   **Modul aktiviert:** Stellen Sie in der Modulkonfiguration sicher, dass „Perfect Money Zahlung aktivieren“ auf „JA“ gesetzt ist.
-   **Modul installiert:** Überprüfen Sie, ob das Modul unter **Module > Modul-Manager** korrekt installiert und aktiviert ist.
-   **Cache:** Leeren Sie Ihren PrestaShop-Cache (unter **Erweiterte Parameter > Leistung**) und Ihren Browser-Cache. Manchmal können alte zwischengespeicherte Daten verhindern, dass neue Zahlungsoptionen angezeigt werden.
-   **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können sehr stark angepasste Themes gelegentlich geringfügige Anpassungen erfordern. Wenn Sie einen Theme-Konflikt vermuten, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob die Option angezeigt wird.

**F: Kann ich das Perfect Money-Logo oder den Text auf der Checkout-Seite anpassen?**
A: Das Modul verwendet eine Standardvorlage zur Anzeige der Zahlungsoption. Sie können den Text in der Regel anpassen, indem Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen** gehen, „Übersetzungen installierter Module“ auswählen, Ihr Theme wählen und dann das Modul „Perfect Money“ suchen. Für Logo-Änderungen müssten Sie die Vorlagendatei des Moduls (`perfectmoney.tpl`) ändern oder CSS-Overrides in Ihrem Theme verwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Perfect Money-Modul für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Perfect Money-Modul folgt der Standard-PrestaShop-Modularchitektur und verwendet hauptsächlich eine Hauptmodulklasse (`PerfectMoney`) für Installation, Deinstallation und Konfiguration sowie `ModuleFrontController`-Klassen zur Abwicklung der Zahlungsweiterleitung und Validierungsprozesse. Es integriert sich mit dem Perfect Money-Zahlungsgateway über ein Server-zu-Server-Kommunikationsmodell (IPN/Callback), um Transaktionen zu bestätigen und Bestellstatus zu aktualisieren.

### 4.2 Controller (`controllers/`)

#### Front-Office Controller

Diese Controller behandeln die kundenorientierten Aspekte des Zahlungsprozesses, einschließlich der Weiterleitung zu Perfect Money und der Bearbeitung des Callbacks nach der Zahlung.

-   **`perfectmoney/controllers/front/index.php`**

    -   **Klassenname**: `PerfectMoneyIndexModuleFrontController`
    -   **Elternklasse**: `ModuleFrontController`
    -   **Verantwortlichkeit**: Dieser Controller ist typischerweise für die Initiierung des Zahlungsprozesses verantwortlich. Wenn ein Kunde Perfect Money auswählt und seine Bestellung bestätigt, bereitet dieser Controller die Zahlungsanforderungsparameter (Händler-ID, Betrag, Währung, Bestellbeschreibung, Rückgabe-URLs) vor und leitet den Browser des Kunden zum Perfect Money-Zahlungsgateway weiter. Er sammelt die notwendigen Bestelldetails aus dem Warenkorb und konstruiert das Zahlungsformular.
-   **`perfectmoney/controllers/front/validation.php`**

    -   **Klassenname**: `PerfectMoneyValidationModuleFrontController`
    -   **Elternklasse**: `ModuleFrontController`
    -   **Verantwortlichkeit**: Dies ist der entscheidende Controller, der den Callback (Instant Payment Notification - IPN) von Perfect Money nach der Bearbeitung einer Zahlung handhabt.
        -   Er empfängt POST-Daten von Perfect Money, die Transaktionsdetails und einen Sicherheitshash enthalten.
        -   Er überprüft die Integrität und Authentizität der Zahlungsbenachrichtigung mithilfe der konfigurierten Alternate Passphrase.
        -   Wenn die Zahlung gültig und erfolgreich ist, aktualisiert er den PrestaShop-Bestellstatus (z. B. auf „Zahlung akzeptiert“), erstellt einen Bestellverlaufseintrag und sendet möglicherweise Bestellbestätigungs-E-Mails.
        -   Wenn die Zahlung fehlschlägt oder ungültig ist, aktualisiert er den Bestellstatus entsprechend (z. B. auf „Zahlungsfehler“).
        -   Anschließend leitet er den Kunden zurück zur entsprechenden PrestaShop-Seite (z. B. Bestellbestätigungs- oder Fehlerseite).

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen zu definieren, die `ObjectModel` oder andere PrestaShop-Kernklassen in einem dedizierten `classes/`-Verzeichnis erweitern. Die gesamte Kernlogik ist wahrscheinlich in der Hauptmodulklasse `PerfectMoney` (`index.php`) und den Front-Controllern gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Es wurden keine benutzerdefinierten JavaScript-Dateien im Modularchiv gefunden. Der Zahlungsprozess wird hauptsächlich durch serverseitige Weiterleitungen und die eigene Zahlungsschnittstelle von Perfect Money abgewickelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Es wurden keine benutzerdefinierten CSS-Dateien im Modularchiv gefunden. Die Formatierung der Zahlungsoption auf der Checkout-Seite wird wahrscheinlich vom PrestaShop-Theme oder Inline-Styles innerhalb der Vorlage geerbt.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

-   **`perfectmoney/views/admin.tpl`**

    -   **Geltungsbereich**: Back-Office-Admin-Konfiguration.
    -   **Zweck**: Diese Vorlage wird verwendet, um das Konfigurationsformular des Moduls im PrestaShop Back Office zu rendern. Sie zeigt die Eingabefelder für Perfect Money Account ID, Account Name, Alternate Passphrase und die Dropdown-Menüs zur Auswahl des Bestellstatus an. Sie verwendet Standard-PrestaShop-Formularhelfer und -Styling.
-   **`perfectmoney/views/perfectmoney.tpl`**

    -   **Geltungsbereich**: Front-Office (Checkout-Zahlungsschritt).
    -   **Zweck**: Diese Vorlage ist dafür verantwortlich, die Perfect Money-Zahlungsoption dem Kunden auf der Checkout-Seite anzuzeigen. Sie enthält typischerweise den Titel der Zahlungsmethode, die Beschreibung und möglicherweise das Perfect Money-Logo. Sie wird in einem Zahlungs-Hook gerendert (z. B. `displayPaymentOptions` in PS 1.7+ oder `displayPayment` in PS 1.6).
-   **`perfectmoney/views/success_page.tpl`**

    -   **Geltungsbereich**: Front-Office (Bestellbestätigungs-/Erfolgsseite).
    -   **Zweck**: Diese Vorlage wird wahrscheinlich verwendet, um eine benutzerdefinierte Erfolgsmeldung oder zusätzliche Informationen für den Kunden nach einer erfolgreichen Perfect Money-Zahlung anzuzeigen, vor oder als Teil der Standard-Bestellbestätigungsseite. Sie könnte vom `validation.php`-Controller gerendert werden.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen.
    -   Konfigurationseinstellungen (Perfect Money Account ID, Passphrase usw.) werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel mit `PERFECTMONEY_` präfixiert sind.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayPaymentOptions` (PS 1.7+) | Auf der Checkout-Seite, Zahlungsschritt. | Rendert die Perfect Money-Zahlungsoption mit `perfectmoney.tpl`. |
| `displayPayment` (PS 1.6) | Auf der Checkout-Seite, Zahlungsschritt. | Rendert die Perfect Money-Zahlungsoption mit `perfectmoney.tpl`. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell zum Laden modulspezifischer Assets (JS/CSS), falls vorhanden, oder für Meta-Tags verwendet. (Keine Assets erkannt, daher wahrscheinlich für Modulinitialisierung oder Kompatibilität). |
| `actionPaymentConfirmation` | Nachdem der Zahlungsstatus einer Bestellung bestätigt wurde. | Könnte für die Nachbearbeitung von Zahlungen verwendet werden, obwohl die primäre Statusaktualisierung vom `validation.php`-Controller gehandhabt wird. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert und erstellt wurde. | Wird vom Modul verwendet, um die Bestellung in PrestaShop mit dem ursprünglichen Status vor der Weiterleitung zu Perfect Money zu erstellen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Perfect Money-Modul besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Integration des Moduls gerne zur Verfügung.
