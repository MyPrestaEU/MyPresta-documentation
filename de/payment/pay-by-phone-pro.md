---
title: "Pay By Phone Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Pay By Phone Pro von MyPresta.eu."
sidebar:
  label: "Pay By Phone Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Pay By Phone Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/pay-by-phone-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/pay-by-phone-pro/)
>
> ---


# Pay By Phone Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich, und dieses Modul hat keine zusätzlichen spezifischen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Pay By Phone Pro)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie definieren, wie die Zahlungsmethode „Pay By Phone Pro“ in Ihrem Shop erscheint und sich verhält.

- **Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach „Pay By Phone Pro“ > Klicken Sie auf „Konfigurieren“.

#### Einstellungen & Optionen

1. **Titel der Zahlungsmethode**

   - **Was diese Einstellung bewirkt:** Dies ist der Name der Zahlungsmethode, den Ihre Kunden während des Checkouts sehen werden. Er erscheint in der Liste der Zahlungsoptionen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Telefonische Zahlung“ gesetzt:* Kunden sehen „Telefonische Zahlung“ als Option.
     - *Wenn auf „Rufen Sie uns an, um zu bezahlen“ gesetzt:* Kunden sehen „Rufen Sie uns an, um zu bezahlen“ als Option.
   - **Empfohlener Wert:** Etwas Klares und Professionelles, wie „Telefonische Zahlung“ oder „Anrufen zur Bestellabwicklung“.
   - **Händlerszenario / Beispiel:** Wenn Sie den direkten Kontakt betonen möchten, könnten Sie „Rufen Sie unser Verkaufsteam an, um zu bezahlen“ verwenden. Wenn es eher wie eine Standard-Zahlungsoption klingen soll, ist „Telefonische Zahlung“ besser.
2. **Beschreibung der Zahlungsmethode**

   - **Was diese Einstellung bewirkt:** Dies ist eine kurze Beschreibung, die unter dem Titel der Zahlungsmethode während des Checkouts erscheint. Sie erklärt dem Kunden, was diese Zahlungsmethode beinhaltet.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Rufen Sie uns an, um Ihre Kreditkartendaten anzugeben und Ihre Bestellung abzuschließen.“ gesetzt:* Dieser Text wird angezeigt und leitet den Kunden zu den nächsten Schritten an.
     - *Wenn auf „Kontaktieren Sie unseren Kundenservice, um Zahlungsoptionen zu besprechen.“ gesetzt:* Dieser alternative Text wird angezeigt.
   - **Empfohlener Wert:** Geben Sie klar an, was der Kunde tun muss, z. B. „Bitte rufen Sie uns unter [Ihre Telefonnummer] an, um Ihre Zahlung und Bestelldetails abzuschließen.“
   - **Händlerszenario / Beispiel:** Sie könnten schreiben: „Nachdem Sie Ihre Bestellung aufgegeben haben, rufen Sie uns bitte unter +1-800-123-4567 während der Geschäftszeiten an, um Ihre Zahlung abzuschließen. Halten Sie Ihre Bestellnummer bereit.“
3. **Anweisungen für den Kunden auf der Bestellbestätigungsseite**

   - **Was diese Einstellung bewirkt:** Dies ist eine detailliertere Nachricht, die dem Kunden auf der Bestellbestätigungsseite angezeigt wird, *nachdem* er „Pay By Phone Pro“ ausgewählt und seine Bestellung aufgegeben hat. Hier geben Sie spezifische Anweisungen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Vielen Dank für Ihre Bestellung. Bitte rufen Sie uns an, um Ihre Zahlung abzuschließen.“ gesetzt:* Diese Nachricht wird angezeigt.
     - *Wenn auf „Ihre Bestellung ist ausstehend. Bitte kontaktieren Sie unser Support-Team mit Ihrer Bestellnummer, um die Zahlung zu arrangieren.“ gesetzt:* Diese alternative Nachricht wird angezeigt.
   - **Empfohlener Wert:** Fügen Sie Ihre Telefonnummer, Geschäftszeiten und welche Informationen der Kunde bereithalten sollte (z. B. Bestellnummer) ein.
   - **Händlerszenario / Beispiel:** „Ihre Bestellung #12345 wurde aufgegeben. Bitte rufen Sie unser Verkaufsteam unter +1-800-123-4567 (Mo-Fr, 9-17 Uhr EST) innerhalb von 24 Stunden an, um die Zahlungsdetails anzugeben. Bitte halten Sie Ihre Bestellnummer bereit.“
4. **Bestellstatus für ausstehende Zahlungen**

   - **Was diese Einstellung bewirkt:** Dies bestimmt den anfänglichen Status einer Bestellung, die mit „Pay By Phone Pro“ in Ihrem PrestaShop Back Office aufgegeben wurde. Dieser Status zeigt an, dass die Zahlung noch nicht abgeschlossen ist und Ihre Aktion erfordert.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Warten auf Banküberweisung“ gesetzt:* Bestellungen erscheinen mit diesem Status.
     - *Wenn auf „Zahlung akzeptiert“ gesetzt:* (Nicht empfohlen für dieses Modul) Dies würde die Bestellung fälschlicherweise als bezahlt markieren, bevor Sie sie verarbeitet haben.
   - **Empfohlener Wert:** Wählen Sie einen Status, der eindeutig „Zahlung ausstehend“ oder „Warten auf Zahlung“ anzeigt. Gängige Optionen sind „Warten auf Banküberweisung“, „Zahlung ausstehend“ oder „Warten auf Scheckzahlung“. Wenn Sie einen benutzerdefinierten Bestellstatus wie „Warten auf telefonische Zahlung“ haben, wäre das ideal.
   - **Händlerszenario / Beispiel:** Die Auswahl von „Warten auf Banküberweisung“ stellt sicher, dass diese Bestellungen in Ihrer Bestellliste leicht als solche identifizierbar sind, die eine manuelle Zahlungsabwicklung erfordern.
5. **Für bestimmte Länder aktivieren**

   - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, diese Zahlungsmethode nur auf Kunden aus bestimmten Ländern zu beschränken. Wenn leer gelassen, ist sie für alle Länder verfügbar.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn bestimmte Länder ausgewählt sind (z. B. „Vereinigte Staaten“, „Kanada“):* Nur Kunden mit einer Rechnungsadresse in diesen Ländern sehen „Pay By Phone Pro“ als Option.
     - *Wenn keine Länder ausgewählt sind:* Die Zahlungsmethode ist weltweit verfügbar.
   - **Empfohlener Wert:** Leer lassen, wenn Sie es weltweit anbieten möchten, oder bestimmte Länder auswählen, wenn Sie betriebliche Einschränkungen haben (z. B. nur telefonischen Support in bestimmten Regionen).
   - **Händlerszenario / Beispiel:** Wenn Ihr telefonischer Support nur auf Englisch verfügbar ist und Sie nur in die USA und nach Kanada versenden, würden Sie „Vereinigte Staaten“ und „Kanada“ auswählen, um es Kunden, die Sie nicht bedienen können, nicht anzubieten.
6. **Für bestimmte Währungen aktivieren**

   - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, diese Zahlungsmethode auf Kunden zu beschränken, die in bestimmten Währungen bezahlen. Wenn leer gelassen, ist sie für alle Währungen verfügbar.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn bestimmte Währungen ausgewählt sind (z. B. „USD“, „EUR“):* Nur Kunden, die in diesen Währungen bezahlen, sehen „Pay By Phone Pro“.
     - *Wenn keine Währungen ausgewählt sind:* Die Zahlungsmethode ist für alle in Ihrem Shop konfigurierten Währungen verfügbar.
   - **Empfohlener Wert:** Leer lassen, wenn Sie alle Währungen unterstützen, oder bestimmte auswählen, wenn Ihr manuelles Zahlungsverarbeitungssystem Währungsbeschränkungen hat.
   - **Händlerszenario / Beispiel:** Wenn Ihr Kreditkartenterminal nur USD und EUR verarbeitet, würden Sie diese beiden Währungen auswählen.
7. **Für bestimmte Kundengruppen aktivieren**

   - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, diese Zahlungsmethode auf bestimmte Kundengruppen zu beschränken (z. B. „Gäste“, „Kunden“, „Großhändler“). Wenn leer gelassen, ist sie für alle Kundengruppen verfügbar.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn bestimmte Gruppen ausgewählt sind (z. B. „Großhändler“):* Nur Kunden, die der Gruppe „Großhändler“ angehören, sehen diese Zahlungsoption.
     - *Wenn keine Gruppen ausgewählt sind:* Die Zahlungsmethode ist für alle Kundengruppen verfügbar.
   - **Empfohlener Wert:** Leer lassen für den allgemeinen Gebrauch, oder bestimmte Gruppen auswählen, wenn diese Zahlungsmethode Teil einer Sondervereinbarung ist (z. B. für VIPs oder B2B-Kunden).
   - **Händlerszenario / Beispiel:** Sie könnten dies nur Ihrer Kundengruppe „Großhandel“ anbieten, da diese oft kundenspezifische Zahlungsbedingungen haben, die eine direkte Besprechung erfordern.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Titel der Zahlungsmethode | „Telefonische Zahlung“ | Name, der Kunden während des Checkouts angezeigt wird. |
| Modulkonfiguration | Beschreibung der Zahlungsmethode | „Rufen Sie uns an, um Ihre Kreditkartendaten anzugeben und Ihre Bestellung abzuschließen.“ | Kurze Erklärung unter dem Zahlungstitel. |
| Modulkonfiguration | Anweisungen für den Kunden auf der Bestellbestätigungsseite | „Vielen Dank für Ihre Bestellung. Bitte rufen Sie uns an, um Ihre Zahlung abzuschließen.“ | Detaillierte Anweisungen auf der Bestellbestätigungsseite. |
| Modulkonfiguration | Bestellstatus für ausstehende Zahlungen | „Warten auf Banküberweisung“ (oder ähnlicher ausstehender Status) | Anfangsstatus von Bestellungen, die mit dieser Methode aufgegeben wurden. |
| Modulkonfiguration | Für bestimmte Länder aktivieren | Leer (Alle Länder) | Zahlungsmethode nach Kundenland einschränken. |
| Modulkonfiguration | Für bestimmte Währungen aktivieren | Leer (Alle Währungen) | Zahlungsmethode nach ausgewählter Währung einschränken. |
| Modulkonfiguration | Für bestimmte Kundengruppen aktivieren | Leer (Alle Gruppen) | Zahlungsmethode nach Kundengruppe einschränken. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Option „Pay By Phone Pro“ wird während des Checkouts nicht angezeigt.**
A:

- **Modulstatus prüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Pay By Phone Pro“ installiert und aktiviert ist.
- **Konfigurationseinstellungen:** Überprüfen Sie die Einstellungen „Für bestimmte Länder aktivieren“, „Für bestimmte Währungen aktivieren“ und „Für bestimmte Kundengruppen aktivieren“. Wenn Sie das Modul eingeschränkt haben, stellen Sie sicher, dass der aktuelle Testkunde/Warenkorb diese Kriterien erfüllt.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung**. Manchmal verhindert ein alter Cache, dass neue Module oder Einstellungen angezeigt werden.
- **Theme-Kompatibilität:** Obwohl selten, kann ein stark angepasstes Theme stören. Wechseln Sie vorübergehend zu einem Standard-PrestaShop-Theme (z. B. Classic), um Theme-Konflikte auszuschließen.

**F2: Wie ändere ich den Text, den Kunden für diese Zahlungsmethode sehen?**
A: Alle kundenorientierten Texte (Titel, Beschreibung und Bestätigungsanweisungen) können direkt auf der Konfigurationsseite des Moduls in Ihrem Back Office angepasst werden. Navigieren Sie zu **Module > Modul-Manager**, suchen Sie „Pay By Phone Pro“ und klicken Sie auf „Konfigurieren“. Sie finden Felder wie „Titel der Zahlungsmethode“, „Beschreibung der Zahlungsmethode“ und „Anweisungen für den Kunden auf der Bestellbestätigungsseite“. Denken Sie daran, Ihre Änderungen zu speichern.

**F3: Was passiert, wenn ein Kunde eine Bestellung mit „Pay By Phone Pro“ aufgibt, aber nie anruft?**
A: Die Bestellung bleibt im von Ihnen konfigurierten Status „Zahlung ausstehend“ (z. B. „Warten auf Banküberweisung“). Sie müssen diese Bestellungen in Ihrem Back Office überwachen. Sie können automatisierte Erinnerungen einrichten oder den Kunden nach einer bestimmten Zeit (z. B. 24-48 Stunden) manuell kontaktieren, um nachzuhaken. Wenn kein Kontakt hergestellt wird, müssen Sie die Bestellung möglicherweise irgendwann stornieren.

**F4: Kann ich den Text des Moduls in andere Sprachen übersetzen?**
A: Ja, das PrestaShop-Übersetzungssystem verarbeitet Modultexte. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Pay By Phone Pro“. Sie können dann alle konfigurierbaren Textfelder in die aktiven Sprachen Ihres Shops übersetzen.

**F5: Wie verarbeite ich die Zahlung, sobald ein Kunde anruft?**
A: Dieses Modul verarbeitet Zahlungen nicht selbst. Es erleichtert die Bestellaufgabe. Sobald ein Kunde anruft, verwenden Sie Ihre bestehenden Offline-Zahlungsverarbeitungsmethoden (z. B. ein physisches Kreditkartenterminal, ein virtuelles Terminal Ihrer Bank oder die Erfassung einer Banküberweisung), um deren Zahlungsdetails entgegenzunehmen und die Transaktion abzuschließen. Nach erfolgreicher Zahlung müssen Sie den Bestellstatus in Ihrem PrestaShop Back Office manuell von „Zahlung ausstehend“ auf „Zahlung akzeptiert“ (oder „In Bearbeitung“) aktualisieren, um die Änderung widerzuspiegeln.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Pay By Phone Pro“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Pay By Phone Pro“ folgt einer Standard-PrestaShop-Modularchitektur und nutzt hauptsächlich `PaymentModule` für seine Kernfunktionalität. Es integriert sich in den Checkout-Fluss, indem es Hooks registriert und Front-Controller für die Zahlungsabwicklung und -validierung bereitstellt. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller behandeln die kundenorientierten Aspekte des Zahlungsprozesses.

- **`controllers/front/index.php`**

  - **Klassenname & Elternklasse:** `PayByPhoneIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist typischerweise für die Anzeige des anfänglichen Zahlungsformulars oder die Weiterleitung zur Zahlungsabwicklungsseite verantwortlich. Im Kontext dieses Moduls fungiert er wahrscheinlich als Gateway vor der eigentlichen Zahlungsabwicklung, indem er möglicherweise Sitzungsdaten einrichtet oder zu `payment_execution.tpl` weiterleitet.
- **`controllers/front/validation.php`**

  - **Klassenname & Elternklasse:** `PayByPhoneValidationModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der kritische Controller, der die Bestellung verarbeitet, nachdem der Kunde „Pay By Phone Pro“ ausgewählt hat. Er validiert die Bestellung, erstellt sie in der PrestaShop-Datenbank mit dem konfigurierten ausstehenden Status und leitet den Kunden dann zur Bestellbestätigungsseite weiter, auf der die spezifischen Anweisungen angezeigt werden. Er verwendet die Methode `validateOrder` aus der übergeordneten `PaymentModule`-Klasse.

#### Back-Office-Admin-Controller

Dieses Modul enthält keine benutzerdefinierten Back-Office-Admin-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/`. Es basiert auf den Kernklassen `PaymentModule` und `Configuration` von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Seine Funktionalität ist hauptsächlich serverseitig und templatebasiert.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`paybyphone/css/paybyphone.css`**
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten und Container, die es stylt:** Dieses Stylesheet wird wahrscheinlich verwendet, um grundlegendes Styling für das Erscheinungsbild der Zahlungsmethode während des Checkouts bereitzustellen, wie z. B. den Zahlungsoptionsblock, den Beschreibungstext oder spezifische Elemente innerhalb der Templates `payment.tpl` oder `shopping-cart.tpl`.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler können den generierten HTML-Code für die Zahlungsmethode auf der Checkout-Seite überprüfen, um spezifische Klassen (z. B. `.paybyphone-payment-option`, `.paybyphone-description`) zu identifizieren, die in der `custom.css` ihres Themes oder über die Anpassungsoptionen des Themes überschrieben werden können.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Diese Templates werden gerendert, wenn spezifische PrestaShop-Hooks ausgeführt werden.

- **`views/templates/hook/infos.tpl`**

  - **Hook:** Wahrscheinlich `displayPaymentTop` oder ähnlich, um zusätzliche Informationen zur Zahlungsmethode bereitzustellen.
  - **Visueller Block:** Könnte verwendet werden, um einen allgemeinen Informationsblock über die „Pay By Phone“-Option anzuzeigen, vielleicht auf der Produktseite oder in einer Spalte, bevor der Kunde zum Checkout gelangt.
- **`views/templates/hook/payment.tpl`**

  - **Hook:** `displayPayment` (PrestaShop 1.6) oder `paymentOptions` (PrestaShop 1.7+).
  - **Visueller Block:** Dies ist das primäre Template zur Anzeige der Option „Pay By Phone Pro“ auf der Zahlungs-Auswahlseite während des Checkouts. Es enthält den Titel und die Beschreibung der Zahlungsmethode, wie im Back Office konfiguriert.

#### Admin-Templates (`views/templates/admin/`)

Dieses Modul enthält keine benutzerdefinierten Admin-Templates. Das Konfigurationsformular wird wahrscheinlich direkt innerhalb der `getContent()`-Methode von `index.php` mit PrestaShops `HelperForm` generiert.

#### Front-Office-Templates (`views/templates/front/`)

Diese Templates werden von den Front-Controllern des Moduls gerendert.

- **`views/templates/front/payment_execution.tpl`**

  - **Zweck:** Dieses Template wird wahrscheinlich von `PayByPhoneIndexModuleFrontController` oder direkt nach der Auswahl der Zahlungsmethode durch den Kunden gerendert. Es könnte als Zwischenseite oder Bestätigungsschritt vor der endgültigen Validierung dienen und möglicherweise eine Schaltfläche „Bestellung bestätigen“ anzeigen.
- **`views/templates/front/shopping-cart.tpl`**

  - **Zweck:** Dieses Template ist wahrscheinlich ein Fallback oder eine alternative Anzeige für die Zahlungsoption innerhalb der Warenkorbzusammenfassung, möglicherweise für ältere PrestaShop-Versionen oder spezifische Theme-Integrationen. Es würde die „Pay By Phone“-Option vor Beginn des vollständigen Checkout-Prozesses präsentieren.
- **`views/templates/front/validation.tpl`**

  - **Zweck:** Dies ist das Template der Bestellbestätigungsseite, das gerendert wird, nachdem `PayByPhoneValidationModuleFrontController` die Bestellung erfolgreich validiert und erstellt hat. Es zeigt den Text „Anweisungen für den Kunden auf der Bestellbestätigungsseite“ zusammen mit einer Zusammenfassung der Bestellung an.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul „Pay By Phone Pro“ erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration` unter Schlüsseln wie `PAYBYPHONE_TITLE`, `PAYBYPHONE_DESCRIPTION`, `PAYBYPHONE_INSTRUCTIONS`, `PAYBYPHONE_ORDER_STATUS`, `PAYBYPHONE_COUNTRIES`, `PAYBYPHONE_CURRENCIES` und `PAYBYPHONE_GROUPS`.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayPayment` (PrestaShop 1.6) | Auf der Zahlungs-Auswahlseite während des Checkouts. | Zeigt die Zahlungsoption „Pay By Phone Pro“ an. |
| `paymentOptions` (PrestaShop 1.7+) | Auf der Zahlungs-Auswahlseite während des Checkouts. | Zeigt die Zahlungsoption „Pay By Phone Pro“ an (moderner Hook). |
| `displayPaymentReturn` | Auf der Bestellbestätigungsseite nach der Zahlung. | Zeigt die spezifischen Anweisungen für den Kunden zum Anruf an. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird potenziell zum Laden von CSS-Dateien (`paybyphone.css`) verwendet. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` | In den jeweiligen Spalten-/Fußzeilenbereichen. | Könnte verwendet werden, um Informationsblöcke über die Zahlungsmethode anzuzeigen (über `infos.tpl`). |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert und erstellt wurde. | Ermöglicht dem Modul, zusätzliche Aktionen oder Protokollierungen nach der Bestellerstellung durchzuführen (z. B. Festlegen spezifischer Bestelldetails). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Pay By Phone Pro“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Kompatibilität unserer Module mit den neuesten PrestaShop-Versionen sicherzustellen.
