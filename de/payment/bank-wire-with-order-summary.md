---
title: "Banküberweisung mit Bestellübersicht – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Banküberweisung mit Bestellübersicht“ von MyPresta.eu."
sidebar:
  label: "Banküberweisung mit Bestellübersicht – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bank wire with order summary auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/bank-wire-with-order-summary.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/bank-wire-with-order-summary/)
>
> ---


# Banküberweisung mit Bestellübersicht

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind in den meisten Hosting-Umgebungen verfügbar. Für dieses Modul sind keine spezifischen ungewöhnlichen Erweiterungen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie Ihre Bankkontodaten definieren und festlegen, wie die Banküberweisungsmethode in Ihrem Shop funktioniert.

#### **Banküberweisungs-Kontoeinstellungen**

Dieser Abschnitt ermöglicht es Ihnen, mehrere Bankkontoprofile zu definieren. Jedes Profil kann eigene Details haben und unabhängig aktiviert oder deaktiviert werden. Dies ist nützlich, wenn Sie verschiedene Bankkonten für verschiedene Währungen, Länder oder sogar verschiedene Marken haben.

- **Profilname:**

  - **Was diese Einstellung bewirkt:** Dies ist ein interner Name für Ihr Bankkontoprofil, der Ihnen hilft, es im Back Office zu identifizieren. Er ist für Kunden nicht sichtbar.
  - **Auswirkung einer Änderung dieser Einstellung:** Eine Änderung wirkt sich nur darauf aus, wie Sie das Profil im Admin-Panel sehen.
  - **Empfohlener Wert:** Ein beschreibender Name, z. B. „Haupt-Euro-Konto“, „USD-Konto für US-Bestellungen“.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Bankkonto in Deutschland für EUR-Zahlungen und ein weiteres in den USA für USD-Zahlungen haben, würden Sie zwei Profile erstellen und diese entsprechend benennen.
- **Aktiv:**

  - **Was diese Einstellung bewirkt:** Steuert, ob dieses spezifische Bankkontoprofil als Zahlungsoption für Kunden verfügbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Dieses Bankkontoprofil wird Kunden angeboten, wenn es alle anderen Eignungskriterien (Währung, Land usw.) erfüllt.
    - *Wenn deaktiviert (Nein):* Dieses Profil wird nicht als Zahlungsoption angezeigt, unabhängig von anderen Einstellungen.
  - **Empfohlener Wert:** „Ja“ für aktive Konten, „Nein“ für inaktive oder temporäre Konten.
  - **Händlerszenario / Beispiel:** Sie könnten ein Profil deaktivieren, wenn ein Bankkonto vorübergehend nicht verfügbar ist oder wenn Sie eine bestimmte Währung auslaufen lassen.
- **Priorität:**

  - **Was diese Einstellung bewirkt:** Wenn mehrere Banküberweisungsprofile aktiv und für die Bestellung eines Kunden berechtigt sind, bestimmt diese Zahl, welches zuerst angezeigt oder bevorzugt wird. Niedrigere Zahlen bedeuten höhere Priorität.
  - **Auswirkung einer Änderung dieser Einstellung:** Beeinflusst die Reihenfolge, in der berechtigte Banküberweisungsoptionen dem Kunden präsentiert werden.
  - **Empfohlener Wert:** Verwenden Sie fortlaufende Nummern (z. B. 1, 2, 3), um Ihre Präferenzen zu ordnen.
  - **Händlerszenario / Beispiel:** Wenn Sie bevorzugen, dass Kunden Ihr Haupt-EUR-Konto anstelle eines sekundären verwenden, geben Sie dem Hauptkonto eine niedrigere Prioritätsnummer (z. B. 1) als dem sekundären (z. B. 2).
- **Währung:**

  - **Was diese Einstellung bewirkt:** Gibt an, in welcher Währung dieses Bankkontoprofil Zahlungen empfangen soll.
  - **Auswirkung einer Änderung dieser Einstellung:** Dieses Profil wird nur Kunden angeboten, deren Bestellsumme in der ausgewählten Währung ist.
  - **Empfohlener Wert:** Wählen Sie die primäre Währung für dieses Bankkonto.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Bankkonto haben, das nur EUR akzeptiert, wählen Sie „Euro“. Wenn ein Kunde eine Bestellung in USD aufgibt, wird dieses Profil nicht angezeigt.
- **Berechtigte Länder:**

  - **Was diese Einstellung bewirkt:** Bestimmt, für welche Länder dieses Bankkontoprofil verfügbar ist. Sie können mehrere Länder auswählen.
  - **Auswirkung einer Änderung dieser Einstellung:** Dieses Profil wird nur Kunden angeboten, deren Rechnungsadresse in einem der ausgewählten Länder liegt.
  - **Empfohlener Wert:** Wählen Sie alle Länder aus, aus denen Sie Banküberweisungen auf dieses spezifische Konto akzeptieren möchten.
  - **Händlerszenario / Beispiel:** Wenn Ihr deutsches Bankkonto nur für Kunden in Deutschland und Österreich ist, wählen Sie „Deutschland“ und „Österreich“.
- **Berechtigte Zonen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, für welche geografischen Zonen dieses Bankkontoprofil verfügbar ist. Sie können mehrere Zonen auswählen.
  - **Auswirkung einer Änderung dieser Einstellung:** Ähnlich wie bei Ländern wird dieses Profil nur Kunden angeboten, deren Rechnungsadresse in einer der ausgewählten Zonen liegt.
  - **Empfohlener Wert:** Wählen Sie die für dieses Bankkonto relevanten Zonen aus.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Bankkonto speziell für europäische Kunden haben, könnten Sie die Zone „Europa“ auswählen.
- **Berechtigte Kundengruppen:**

  - **Was diese Einstellung bewirkt:** Beschränkt diese Zahlungsoption auf bestimmte Kundengruppen (z. B. „Besucher“, „Gäste“, „Kunden“, „Großhändler“).
  - **Auswirkung einer Änderung dieser Einstellung:** Nur Kunden, die zu den ausgewählten Gruppen gehören, sehen diese Banküberweisungsoption.
  - **Empfohlener Wert:** Typischerweise „Kunden“ und „Gäste“, kann aber für B2B angepasst werden.
  - **Händlerszenario / Beispiel:** Sie möchten Banküberweisung möglicherweise nur Ihrer Gruppe „Großhändler“ für große B2B-Bestellungen anbieten und nicht regulären Einzelhandelskunden.
- **Kontoinhaber:**

  - **Was diese Einstellung bewirkt:** Der vollständige Name des Kontoinhabers (Ihr Firmenname oder persönlicher Name), wie er auf dem Bankkonto erscheint.
  - **Auswirkung einer Änderung dieser Einstellung:** Diese Informationen werden dem Kunden auf der Zahlungsbestätigungsseite angezeigt, damit er weiß, an wen er Geld überweisen soll.
  - **Empfohlener Wert:** Ihr genauer rechtlicher Firmenname oder persönlicher Name.
  - **Händlerszenario / Beispiel:** „MyPresta.eu Sp. z o.o.“
- **IBAN:**

  - **Was diese Einstellung bewirkt:** Ihre Internationale Bankkontonummer. Dies ist eine standardisierte internationale Bankkontokennung.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies sind entscheidende Informationen, die dem Kunden für die Banküberweisung angezeigt werden.
  - **Empfohlener Wert:** Ihre vollständige und korrekte IBAN.
  - **Händlerszenario / Beispiel:** „DE89370400440532013000“
- **BIC / SWIFT:**

  - **Was diese Einstellung bewirkt:** Ihr Bank Identifier Code (BIC) oder SWIFT-Code. Dieser identifiziert Ihre Bank weltweit.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies sind wesentliche Informationen, die dem Kunden für internationale Banküberweisungen angezeigt werden.
  - **Empfohlener Wert:** Ihr vollständiger und korrekter BIC/SWIFT-Code.
  - **Händlerszenario / Beispiel:** „COBADEFFXXX“
- **Kontonummer / Details:**

  - **Was diese Einstellung bewirkt:** Ihre traditionelle Bankkontonummer oder andere spezifische Details, die von Ihrer Bank oder Ihrem Land benötigt werden, falls IBAN/BIC nicht ausreichen oder anwendbar sind.
  - **Auswirkung einer Änderung dieser Einstellung:** Diese Informationen werden dem Kunden angezeigt.
  - **Empfohlener Wert:** Ihre Kontonummer, wenn IBAN nicht verwendet wird, oder andere spezifische Details. Leer lassen, wenn IBAN/BIC ausreichen.
  - **Händlerszenario / Beispiel:** In einigen Ländern wird eine lokale Kontonummer möglicherweise immer noch neben oder anstelle der IBAN bevorzugt.
- **Bank- / Kontoinhaberadresse:**

  - **Was diese Einstellung bewirkt:** Die Adresse Ihrer Bank oder die registrierte Adresse des Kontoinhabers.
  - **Auswirkung einer Änderung dieser Einstellung:** Diese Informationen werden dem Kunden angezeigt, manchmal für Banküberweisungen erforderlich.
  - **Empfohlener Wert:** Die vollständige Adresse Ihrer Bankfiliale oder die registrierte Adresse Ihres Unternehmens.
  - **Händlerszenario / Beispiel:** „Bank of Example, Hauptstraße 123, 10001 Stadt, Land“
- **Zusätzliche Anweisungen:**

  - **Was diese Einstellung bewirkt:** Ein Textfeld, in dem Sie dem Kunden zusätzliche Hinweise zur Banküberweisung geben können (z. B. „Bitte geben Sie Ihre Bestellnummer im Verwendungszweck an“, „Zahlungen dauern in der Regel 1-3 Werktage bis zur Gutschrift“).
  - **Auswirkung einer Änderung dieser Einstellung:** Dieser Text wird dem Kunden auf der Zahlungsbestätigungsseite angezeigt.
  - **Empfohlener Wert:** Klare, prägnante Anweisungen, um Kunden zu helfen, die Überweisung korrekt abzuschließen.
  - **Händlerszenario / Beispiel:** „Wichtig: Bitte verwenden Sie Ihre Bestell-ID # [ORDER\_ID] als Zahlungsreferenz, um eine schnelle Bearbeitung zu gewährleisten.“

#### **Warenkorb-Gesamtbeschränkungen**

Diese Einstellungen ermöglichen es Ihnen, die Mindest- und Höchstbestellwerte zu steuern, für die die Banküberweisungsoption verfügbar ist.

- **Mindest-Warenkorb-Gesamtbetrag:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die Mindest-Warenkorb-Gesamtbetragsbeschränkung für diese Zahlungsmethode.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Feld „Mindest-Warenkorb-Gesamtwert“ wird aktiv, und die Banküberweisung ist nur für Bestellungen über diesem Wert verfügbar.
    - *Wenn deaktiviert:* Es wird keine Mindest-Warenkorb-Gesamtbetragsbeschränkung angewendet.
  - **Empfohlener Wert:** „Aktiviert“, wenn Sie ein Minimum festlegen möchten, andernfalls „Deaktiviert“.
  - **Händlerszenario / Beispiel:** Sie könnten dies aktivieren, wenn Banküberweisungen für größere Bestellungen kostengünstiger sind oder um Banküberweisungen für sehr kleine Einkäufe zu unterbinden.
- **Mindest-Warenkorb-Gesamtwert:**

  - **Was diese Einstellung bewirkt:** Der tatsächliche Geldwert, den der Warenkorb des Kunden überschreiten muss, damit die Banküberweisungsoption angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn der Warenkorb-Gesamtbetrag des Kunden unter diesem Wert liegt, wird die Banküberweisungsoption nicht angezeigt.
  - **Empfohlener Wert:** Ein angemessenes Minimum, z. B. „50.00“.
  - **Händlerszenario / Beispiel:** Auf „50.00“ setzen, wenn Sie Banküberweisung nur für Bestellungen ab 50 € anbieten möchten.
- **Maximaler Warenkorb-Gesamtbetrag:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die maximale Warenkorb-Gesamtbetragsbeschränkung für diese Zahlungsmethode.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Feld „Maximaler Warenkorb-Gesamtwert“ wird aktiv, und die Banküberweisung ist nur für Bestellungen unter diesem Wert verfügbar.
    - *Wenn deaktiviert:* Es wird keine maximale Warenkorb-Gesamtbetragsbeschränkung angewendet.
  - **Empfohlener Wert:** „Aktiviert“, wenn Sie ein Maximum festlegen möchten, andernfalls „Deaktiviert“.
  - **Händlerszenario / Beispiel:** Sie könnten dies aktivieren, wenn Sie für extrem große Bestellungen andere Zahlungsmethoden (wie direkte Verhandlung oder individuelle Rechnungsstellung) bevorzugen.
- **Maximaler Warenkorb-Gesamtwert:**

  - **Was diese Einstellung bewirkt:** Der tatsächliche Geldwert, den der Warenkorb des Kunden unterschreiten muss, damit die Banküberweisungsoption angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn der Warenkorb-Gesamtbetrag des Kunden über diesem Wert liegt, wird die Banküberweisungsoption nicht angezeigt.
  - **Empfohlener Wert:** Ein angemessenes Maximum, z. B. „5000.00“.
  - **Händlerszenario / Beispiel:** Auf „5000.00“ setzen, wenn Sie Banküberweisung für Bestellungen über 5000 € nicht akzeptieren möchten.

#### **Anzeige der Bestellübersicht**

Diese Einstellungen steuern, welche Informationen dem Kunden auf der Zahlungsbestätigungsseite angezeigt werden, bevor er seine Bestellung abschließt. Dies ist entscheidend für die Einhaltung gesetzlicher Vorschriften.

- **Bestellübersicht vor Bestätigung:**

  - **Was diese Einstellung bewirkt:** Steuert, ob eine detaillierte Bestellübersicht dem Kunden auf der Zahlungsbestätigungsseite angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Zusammenfassung der Produkte, Preise und Gesamtbeträge wird angezeigt.
    - *Wenn deaktiviert:* Die detaillierte Zusammenfassung wird nicht angezeigt, was in einigen Regionen die Einhaltung gesetzlicher Vorschriften beeinträchtigen kann.
  - **Empfohlener Wert:** „Aktiviert“, um die Einhaltung gesetzlicher Vorschriften und die Klarheit für den Kunden zu gewährleisten.
  - **Händlerszenario / Beispiel:** Lassen Sie dies immer aktiviert, um Ihren Kunden vor dem Kauf volle Transparenz zu bieten.
- **Kundenübersicht vor Bestätigung anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob die Zusammenfassung der Rechnungs- und Lieferadresse des Kunden auf der Zahlungsbestätigungsseite angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Adressdetails des Kunden werden angezeigt.
    - *Wenn deaktiviert:* Adressdetails werden nicht angezeigt.
  - **Empfohlener Wert:** „Aktiviert“ für volle Transparenz.
  - **Händlerszenario / Beispiel:** Durch die Aktivierung können Kunden ihre Lieferinformationen ein letztes Mal überprüfen, bevor sie die Bestellung aufgeben.

#### **Erweiterte Analysen (Intern)**

Diese Einstellungen dienen typischerweise der internen Modul-Analyse und Berichterstattung und wirken sich nicht direkt auf das Front-Office-Kundenerlebnis aus.

- **BANKWIREPRO\_ANALYTICS\_DEFAULT\_CHART, BANKWIREPRO\_ANALYTICS\_PERIOD, BANKWIREPRO\_ANALYTICS\_CHART\_WEEKS, BANKWIREPRO\_ANALYTICS\_CHART\_MONTHS, BANKWIREPRO\_ANALYTICS\_CHART\_YEARS:**
  - **Was diese Einstellungen bewirken:** Dies sind interne Konfigurationswerte, die sich darauf beziehen, wie das Modul Zahlungsstatistiken innerhalb des PrestaShop Back Office verfolgen oder anzeigen könnte (falls eine solche Funktion implementiert ist). Sie definieren Standarddiagrammtypen, Berichtszeiträume und Zeitrahmen für Analysen.
  - **Auswirkung einer Änderung dieser Einstellungen:** Diese wirken sich nicht auf den kundenorientierten Zahlungsprozess aus. Sie könnten beeinflussen, wie Daten in einem internen Analyse-Dashboard dargestellt werden, falls verfügbar.
  - **Empfohlener Wert:** Als Standard belassen, es sei denn, der Support weist Sie ausdrücklich an.
  - **Händlerszenario / Beispiel:** Nicht direkt anwendbar auf die Entscheidungsfindung des Händlers für die Zahlungsabwicklung.

#### **Spracheinstellungen (Intern)**

- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG:**

  - **Was diese Einstellungen bewirken:** Dies sind Standard-PrestaShop-Konfigurationsvariablen, die die Standardsprache Ihres Shops und die Möglichkeit für Mitarbeiter, die Sprache der Back-Office-Formulare zu ändern, bestimmen. Sie werden hier als Referenz angezeigt, sind aber nicht spezifisch für dieses Modul.
  - **Auswirkung einer Änderung dieser Einstellungen:** Änderungen daran würden in den allgemeinen Einstellungen von PrestaShop vorgenommen, nicht hier. Sie beeinflussen die Standardsprache für Textfelder im Back Office.
  - **Empfohlener Wert:** Die Standardsprache Ihres Shops.
  - **Händlerszenario / Beispiel:** Wenn die primäre Sprache Ihres Shops Englisch ist, wäre `PS_LANG_DEFAULT` auf die ID der englischen Sprache eingestellt.
- **PS\_CURRENCY\_DEFAULT:**

  - **Was diese Einstellung bewirkt:** Dies ist die Standardwährung Ihres PrestaShop-Shops. Sie wird hier als Referenz angezeigt.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies ist eine globale PrestaShop-Einstellung. Eine Änderung würde alle Preise und Währungsanzeigen in Ihrem Shop beeinflussen.
  - **Empfohlener Wert:** Die primäre Betriebswährung Ihres Shops.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop hauptsächlich in Euro handelt, wäre dies auf „Euro“ eingestellt.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Profilname | Beschreibender Name | Interne Identifizierung des Bankkontos. |
| Modulkonfiguration | Aktiv | Ja | Aktiviert/deaktiviert dieses Bankkontoprofil für die Kundennutzung. |
| Modulkonfiguration | Priorität | 1 (oder sequenziell) | Ordnet die Anzeige mehrerer berechtigter Banküberweisungsoptionen. |
| Modulkonfiguration | Währung | Währung Ihres Shops | Beschränkt das Profil auf Bestellungen in dieser Währung. |
| Modulkonfiguration | Berechtigte Länder | Alle Länder | Beschränkt das Profil auf Kunden aus ausgewählten Ländern. |
| Modulkonfiguration | Berechtigte Zonen | Alle Zonen | Beschränkt das Profil auf Kunden aus ausgewählten Zonen. |
| Modulkonfiguration | Berechtigte Kundengruppen | Alle Gruppen | Beschränkt das Profil auf ausgewählte Kundengruppen. |
| Modulkonfiguration | Kontoinhaber | Ihr Unternehmen/Name | Wird dem Kunden für die Banküberweisung angezeigt. |
| Modulkonfiguration | IBAN | Ihre IBAN | Wird dem Kunden für die Banküberweisung angezeigt. |
| Modulkonfiguration | BIC / SWIFT | Ihr BIC/SWIFT | Wird dem Kunden für internationale Banküberweisungen angezeigt. |
| Modulkonfiguration | Kontonummer / Details | (Optional) | Zusätzliche Bankdaten für den Kunden. |
| Modulkonfiguration | Bank- / Kontoinhaberadresse | Ihre Bank-/Firmenadresse | Wird dem Kunden für die Banküberweisung angezeigt. |
| Modulkonfiguration | Zusätzliche Anweisungen | Klare Anweisungen | Zusätzliche Hinweise für den Kunden (z. B. Referenznummer). |
| Modulkonfiguration | Mindest-Warenkorb-Gesamtbetrag | Deaktiviert | Aktiviert/deaktiviert die Mindestbestellwertbeschränkung. |
| Modulkonfiguration | Mindest-Warenkorb-Gesamtwert | 0.00 | Mindestbestellwert, damit Banküberweisung verfügbar ist. |
| Modulkonfiguration | Maximaler Warenkorb-Gesamtbetrag | Deaktiviert | Aktiviert/deaktiviert die Höchstbestellwertbeschränkung. |
| Modulkonfiguration | Maximaler Warenkorb-Gesamtwert | 0.00 | Höchstbestellwert, damit Banküberweisung verfügbar ist. |
| Modulkonfiguration | Bestellübersicht vor Bestätigung | Aktiviert | Zeigt eine detaillierte Produktübersicht auf der Bestätigungsseite an. |
| Modulkonfiguration | Kundenübersicht vor Bestätigung anzeigen | Aktiviert | Zeigt eine Kundenadressübersicht auf der Bestätigungsseite an. |
| Modulkonfiguration | BANKWIREPRO\_ANALYTICS\_\* | Standard | Interne Analyseeinstellungen (keine Front-Office-Auswirkung). |
| Modulkonfiguration | PS\_LANG\_DEFAULT | Shop-Standard | PrestaShops Standardspracheinstellung. |
| Modulkonfiguration | PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG | Shop-Standard | PrestaShops Einstellung für die Mitarbeitersprachen im Formular. |
| Modulkonfiguration | PS\_CURRENCY\_DEFAULT | Shop-Standard | PrestaShops Standardwährungseinstellung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Warum wird die Banküberweisungsoption meinen Kunden nicht angezeigt?**
A1: Überprüfen Sie die folgenden Einstellungen in der Modulkonfiguration:
\* Schalter **„Aktiv“** für das Bankkontoprofil: Stellen Sie sicher, dass er auf „Ja“ steht.
\* **„Währung“**: Stimmt die Bestellwährung des Kunden mit der Währung des Profils überein?
\* **„Berechtigte Länder“ / „Berechtigte Zonen“**: Ist das Land/die Zone der Rechnungsadresse des Kunden enthalten?
\* **„Berechtigte Kundengruppen“**: Darf die Kundengruppe diese Zahlungsmethode verwenden?
\* **„Mindest-Warenkorb-Gesamtbetrag“ / „Maximaler Warenkorb-Gesamtbetrag“**: Liegt der Warenkorbwert des Kunden im zulässigen Bereich?
\* **PrestaShop-Cache**: Manchmal kann das Leeren des Smarty-Caches (Erweiterte Einstellungen > Leistung > Cache leeren) Anzeigeprobleme beheben.

**F2: Meine Bankdaten sind falsch oder veraltet. Wie ändere ich sie?**
A2: Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Banküberweisung mit Bestellübersicht“ und klicken Sie auf „Konfigurieren“. Sie sehen Ihre vorhandenen Bankkontoprofile. Klicken Sie auf die Schaltfläche „Bearbeiten“ (Bleistiftsymbol) neben dem Profil, das Sie aktualisieren möchten, ändern Sie die Felder „Kontoinhaber“, „IBAN“, „BIC / SWIFT“ usw. und speichern Sie dann Ihre Änderungen.

**F3: Die Bestellübersicht wird auf der Bestätigungsseite nicht angezeigt. Stimmt etwas nicht?**
A3: Stellen Sie sicher, dass die Einstellungen „Bestellübersicht vor Bestätigung“ und „Kundenübersicht vor Bestätigung anzeigen“ in der Modulkonfiguration beide auf „Aktiviert“ stehen. Wenn dies der Fall ist und Sie Ihren PrestaShop-Cache geleert haben, könnte ein Theme-Konflikt vorliegen. Testen Sie mit dem Standard-PrestaShop-Theme, um dies auszuschließen.

**F4: Kann ich verschiedene Bankkonten für verschiedene Kundentypen oder Produkte anbieten?**
A4: Ja, absolut! Dieses Modul unterstützt mehrere Bankkontoprofile. Sie können separate Profile erstellen und die Einstellungen „Berechtigte Kundengruppen“, „Währung“, „Berechtigte Länder“ und „Warenkorb-Gesamtbetrag“ verwenden, um zu definieren, wann welches spezifische Bankkonto angeboten wird. Zum Beispiel ein Konto für Privatkunden in EUR, ein anderes für Großhandelskunden in USD.

**F5: Nach der Aktualisierung meines Themes oder PrestaShops sieht die Banküberweisungsseite seltsam aus. Was soll ich tun?**
A5: Dies deutet oft auf einen CSS-Konflikt oder ein Problem mit einer Template-Überschreibung hin.
1. **Cache leeren:** Beginnen Sie immer damit, Ihren PrestaShop-Cache zu leeren (Erweiterte Einstellungen > Leistung).
2. **Modul-Updates prüfen:** Stellen Sie sicher, dass Sie die neueste Version des Moduls „Banküberweisung mit Bestellübersicht“ von MyPresta.eu haben, da Updates oft Kompatibilitätskorrekturen enthalten.
3. **Theme-Konflikt:** Wenn das Problem weiterhin besteht, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (z. B. „Classic“), um zu sehen, ob das Problem verschwindet. Wenn ja, überschreibt oder kollidiert Ihr benutzerdefiniertes Theme wahrscheinlich mit dem Styling oder den Templates des Moduls. Möglicherweise müssen Sie Ihren Theme-Entwickler oder einen Webmaster konsultieren, um die CSS- oder Template-Dateien des Themes anzupassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `bankwirepro` folgt der Standard-PrestaShop-Modularchitektur und nutzt `ModuleFrontController` für Front-Office-Interaktionen und die Hauptklasse `Module` für die Konfiguration. Es integriert sich über Zahlungshooks (`displayPaymentOptions`, `paymentOptions`, `displayPaymentReturn`) in den Checkout-Fluss. Die Konfiguration wird über Einträge in der `Configuration`-Tabelle verwaltet, und Bankkontodaten werden als serialisierte Arrays oder einzelne `Configuration`-Schlüssel gespeichert, was mehrere Profile ermöglicht. Die Hauptfunktion des Moduls besteht darin, dem Kunden vor und nach der Bestellvalidierung Bankdaten und eine Bestellübersicht zu präsentieren.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  - `controllers/front/index.php`
    - **Klassenname**: `BankwireproIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als Standard-Einstiegspunkt oder Fallback. In vielen Modulen leiten `index.php`-Controller zu einem spezifischeren Controller weiter oder handhaben die grundlegende Modulanzeige, wenn keine andere spezifische Aktion angefordert wird. Er könnte die anfängliche Einrichtung oder die Weiterleitung zur Zahlungsauswahl handhaben.
  - `controllers/front/payment.php`
    - **Klassenname**: `BankwireproPaymentModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller ist für das Rendern der Zahlungsauswahlseite verantwortlich, wenn die Banküberweisungsoption gewählt wird. Er sammelt die notwendigen Bankkontodaten basierend auf dem aktuellen Warenkorb, Kunden und der Währung und bereitet sie für die Anzeige im `payment.tpl`-Template vor. Er fungiert als Brücke zwischen der Auswahl der Zahlungsoption und dem letzten Validierungsschritt.
  - `controllers/front/validation.php`
    - **Klassenname**: `BankwireproValidationModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dies ist der kritische Controller, der den letzten Schritt des Banküberweisungszahlungsprozesses handhabt. Er validiert die Bestellung, erstellt die Bestellung in der PrestaShop-Datenbank und rendert dann das `validation.tpl`-Template. Dieses Template zeigt die vollständige Bestellübersicht, die Kundenadressübersicht und die ausgewählten Bankkontodaten zusammen mit zusätzlichen Anweisungen an, bevor der Kunde auf die Standardseite `order-confirmation` weitergeleitet wird. Es stellt sicher, dass alle notwendigen Informationen für die Einhaltung gesetzlicher Vorschriften präsentiert werden.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen in `classes/` aus. Die Kernlogik für die Verwaltung von Bankkontoprofilen und Konfiguration ist wahrscheinlich in der Hauptdatei `bankwirepro.php` enthalten, wobei `Configuration::get()` und `Configuration::updateValue()` zum Speichern von Einstellungen verwendet werden, möglicherweise mit serialisierten Arrays für mehrere Bankkontoprofile.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien aus. Dies deutet darauf hin, dass die Front-Office-Funktionalität des Moduls hauptsächlich serverseitig gerendert wird und für grundlegende Interaktionen auf Standard-PrestaShop-JavaScript angewiesen ist, oder dass jegliches minimale JS in den Templates inline ist.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine benutzerdefinierten CSS-Dateien aus. Dies impliziert, dass das Modul entweder vollständig auf das Styling des Standard-PrestaShop-Themes angewiesen ist oder dass jegliches minimale Styling in den Templates inline ist. Entwickler sollten sich bewusst sein, dass das Erscheinungsbild des Moduls weitgehend durch das CSS des aktiven Themes bestimmt wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `accountSelector.tpl`: Dieses Template wird wahrscheinlich in der Back-Office-Konfiguration des Moduls verwendet, um eine Liste der konfigurierten Bankkontoprofile anzuzeigen, sodass der Administrator diese auswählen, bearbeiten oder löschen kann. Es würde typischerweise eine Tabelle oder Liste mit Profilnamen, Status und Aktionsschaltflächen rendern.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `validation.tpl`: Dies ist ein entscheidendes Template, das vom `BankwireproValidationModuleFrontController` gerendert wird. Es zeigt dem Kunden die umfassende Bestellübersicht (Produkte, Gesamtbeträge), die Kundenadressübersicht und die ausgewählten Bankkontodaten (Kontoinhaber, IBAN, BIC/SWIFT, Anweisungen) an, bevor die Bestellung vollständig bestätigt wird. Dieses Template ist entscheidend für die Einhaltung gesetzlicher Vorschriften.
- **Hook-Templates (`views/templates/hook/`)**:

  - `infos.tpl`: Dieses Template ist wahrscheinlich in `displayPaymentReturn` oder einen ähnlichen Hook auf der `order-confirmation`-Seite eingehängt. Es wiederholt die Banküberweisungsanweisungen und Bankdaten, nachdem die Bestellung erfolgreich aufgegeben wurde, und dient als Erinnerung für den Kunden, die Überweisung abzuschließen.
  - `payment.tpl`: Dieses Template wird wahrscheinlich für den `displayPayment`-Hook (PrestaShop 1.6.x) oder `paymentOptions` (PrestaShop 1.7+, 8.x, 9.x) verwendet. Es rendert die Banküberweisungsoption selbst auf der Zahlungsauswahlseite während des Checkouts und präsentiert sie dem Kunden als verfügbare Zahlungsmethode.
  - `payment_return.tpl`: Ähnlich wie `infos.tpl` ist dieses Template wahrscheinlich auch in `displayPaymentReturn` eingehängt. Es liefert die endgültige Bestätigungsnachricht und die Bankdaten auf der Bestellbestätigungsseite und stellt sicher, dass der Kunde alle Informationen hat, um mit der Banküberweisung fortzufahren.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen, einschließlich mehrerer Bankkontoprofile, werden in der Tabelle `ps_configuration` gespeichert.
  - Verwendete Konfigurationsschlüssel:
    - `BANK_WIRE_PRO_MINCART`, `BANK_WIRE_PRO_MINCART_V`, `BANK_WIRE_PRO_MAXCART`, `BANK_WIRE_PRO_MAXCART_V`: Für Warenkorb-Gesamtbeschränkungen.
    - `BANK_WIRE_PRO_OWNER_`, `BANK_WIRE_PRO_DETAILS_`, `BANK_WIRE_PRO_ADDRESS_`, `BANK_WIRE_PRO_SWIFT_`, `BANK_WIRE_PRO_IBAN_`, `BANK_WIRE_PRO_MORE_`: Dies sind wahrscheinlich Präfixe zum Speichern von Details *jedes* Bankkontoprofils, möglicherweise mit einem Sprach-ID- oder Profil-ID-Suffix (z. B. `BANK_WIRE_PRO_OWNER_1_1` für Profil 1, Sprache 1).
    - `BANK_WIRE_PRO_OWNER_SUMMARY`, `BANK_WIRE_PRO_CSUMMARY`, `BANK_WIRE_PRO_ASUMMARY`: Zur Steuerung der Anzeige von Bestell- und Adressübersichten.
    - `BANKWIREPRO_ANALYTICS_*`: Interne Analyseeinstellungen.
    - Standard-PrestaShop-Schlüssel wie `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `PS_CURRENCY_DEFAULT` werden gelesen, aber nicht vom Modul verwaltet.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Bereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayPayment` | Front-Office | Zahlungsauswahlschritt (PrestaShop 1.6.x) | Rendert die Banküberweisungsoption auf der Checkout-Seite. |
| `paymentOptions` | Front-Office | Zahlungsauswahlschritt (PrestaShop 1.7.x, 8.x, 9.x) | Stellt `PaymentOption`-Objekte für Banküberweisung auf der Checkout-Seite bereit. |
| `displayPaymentReturn` | Front-Office | Bestellbestätigungsseite (`order-confirmation`) | Zeigt Bankdaten und Anweisungen nach der Bestellvalidierung an. |
| `displayPaymentOptions` | Front-Office | Zahlungsauswahlschritt (PrestaShop 1.7.x, 8.x, 9.x) | Alternativer oder ergänzender Hook zum Rendern von Zahlungsoptionen. |
| `actionPaymentConfirmation` | Back-Office | Nachdem eine Bestellung als bezahlt bestätigt wurde | (Impliziert, üblich für Zahlungsmodule) Kann den Bestellstatus aktualisieren oder Aktionen nach der Zahlung ausführen. |
| `actionValidateOrder` | Back-Office | Nachdem eine Bestellung validiert wurde | (Impliziert, üblich für Zahlungsmodule) Wird verwendet, um den anfänglichen Bestellstatus festzulegen, Zahlungsdetails zu speichern. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die sicherste und kompatibelste Version des Moduls „Banküberweisung mit Bestellübersicht“ verwenden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Integration des Moduls gerne zur Verfügung.
