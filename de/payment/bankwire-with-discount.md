---
title: "Banküberweisung mit Rabatt – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Banküberweisung mit Rabatt“ von MyPresta.eu."
sidebar:
  label: "Banküberweisung mit Rabatt – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bankwire with discount auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/bankwire-with-discount.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/bankwire-with-discount/)
>
> ---


# Banküberweisung mit Rabatt

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst erforderlich und in der Regel in allen modernen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Banküberweisung mit Rabatt)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie alle Kernfunktionen des Moduls einrichten.

#### **Allgemeine Einstellungen**

- **Banküberweisung aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Zahlungsmethode „Banküberweisung mit Rabatt“ in Ihrem Shop.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen „Per Banküberweisung bezahlen“ als Zahlungsoption während des Checkouts.
    - *Wenn deaktiviert:* Die Banküberweisungsoption wird für Kunden ausgeblendet.
  - **Empfohlener Wert:** JA (um die Funktionen des Moduls zu nutzen).
  - **Händlerszenario:** Sie möchten Banküberweisungen als Zahlungsmethode anbieten.
- **Titel der Banküberweisung:**

  - **Was diese Einstellung bewirkt:** Definiert den Titel, der für die Banküberweisungsoption auf der Checkout-Seite angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert den Text, den Kunden bei der Auswahl dieser Zahlungsmethode sehen.
  - **Empfohlener Wert:** „Per Banküberweisung bezahlen“, „Banküberweisung (mit Rabatt!)“ oder ähnliches.
  - **Händlerszenario:** Sie möchten die Zahlungsmethode für Kunden klar kennzeichnen.
- **Zahlungsanweisungen (Zusammenfassung im Checkout):**

  - **Was diese Einstellung bewirkt:** Ein kurzer Text, der auf der Zahlungsoptionsseite (vor der Bestätigung) angezeigt wird, um Kunden schnelle Anweisungen oder Informationen zur Banküberweisung zu geben.
  - **Auswirkung der Änderung dieser Einstellung:** Bietet dem Kunden sofortigen Kontext zur Banküberweisungsmethode.
  - **Empfohlener Wert:** „Sie erhalten die Bankdaten nach Bestätigung Ihrer Bestellung. Rabatt angewendet!“
  - **Händlerszenario:** Sie möchten Kunden über die nächsten Schritte informieren oder den Rabattvorteil frühzeitig hervorheben.
- **Zahlungsanweisungen (Nach Bestellbestätigung):**

  - **Was diese Einstellung bewirkt:** Detaillierte Anweisungen, die auf der Bestellbestätigungsseite angezeigt werden, nachdem ein Kunde eine Banküberweisungsbestellung aufgegeben hat. Hier geben Sie Ihre Bankkontodaten ein.
  - **Auswirkung der Änderung dieser Einstellung:** Bietet die wesentlichen Informationen für Kunden, um die Banküberweisung durchzuführen.
  - **Empfohlener Wert:** Geben Sie Ihren Banknamen, Kontoinhaber, IBAN, SWIFT/BIC und alle spezifischen Hinweise an (z. B. „Bitte geben Sie Ihre Bestellnummer im Verwendungszweck an“).
  - **Händlerszenario:** Dies ist entscheidend, damit Kunden ihre Zahlung erfolgreich abschließen können.

#### **Bankkontodaten**

Diese Felder werden verwendet, um Ihren Kunden Ihre Bankkontoinformationen zur Verfügung zu stellen.

- **Kontoinhaber:**

  - **Was diese Einstellung bewirkt:** Der Name des Kontoinhabers des Bankkontos.
  - **Auswirkung der Änderung dieser Einstellung:** Zeigt diesen Namen dem Kunden an.
  - **Empfohlener Wert:** Ihr Firmenname oder persönlicher Name.
  - **Händlerszenario:** Wesentlich für die Banküberweisung.
- **Bankname:**

  - **Was diese Einstellung bewirkt:** Der Name Ihrer Bank.
  - **Auswirkung der Änderung dieser Einstellung:** Zeigt diesen Namen dem Kunden an.
  - **Empfohlener Wert:** z. B. „Deutsche Bank“, „Bank of America“.
  - **Händlerszenario:** Wesentlich für die Banküberweisung.
- **Adresse:**

  - **Was diese Einstellung bewirkt:** Die Adresse Ihrer Bank.
  - **Auswirkung der Änderung dieser Einstellung:** Zeigt diese Adresse dem Kunden an.
  - **Empfohlener Wert:** Die Filialadresse Ihrer Bank.
  - **Händlerszenario:** Kann für internationale Überweisungen erforderlich sein.
- **IBAN (International Bank Account Number):**

  - **Was diese Einstellung bewirkt:** Ihre IBAN, eine standardisierte internationale Bankkontonummer.
  - **Auswirkung der Änderung dieser Einstellung:** Zeigt diese Nummer dem Kunden an.
  - **Empfohlener Wert:** Ihre vollständige IBAN.
  - **Händlerszenario:** Entscheidend für Banküberweisungen, insbesondere innerhalb Europas.
- **SWIFT/BIC (Bank Identifier Code):**

  - **Was diese Einstellung bewirkt:** Ihr SWIFT/BIC-Code, der für internationale Banküberweisungen verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Zeigt diesen Code dem Kunden an.
  - **Empfohlener Wert:** Ihr vollständiger SWIFT/BIC-Code.
  - **Händlerszenario:** Wesentlich für internationale Banküberweisungen.
- **Zusätzliche Informationen:**

  - **Was diese Einstellung bewirkt:** Alle zusätzlichen Hinweise oder Anweisungen, die Sie bezüglich der Banküberweisung geben möchten (z. B. „Bitte rechnen Sie mit 1-3 Werktagen Bearbeitungszeit“).
  - **Auswirkung der Änderung dieser Einstellung:** Bietet dem Kunden zusätzliche Orientierung.
  - **Empfohlener Wert:** Alle spezifischen Anweisungen, die nicht durch andere Felder abgedeckt sind.
  - **Händlerszenario:** Sie möchten die Erwartungen der Kunden bezüglich der Überweisungszeiten steuern.

#### **Rabatt- & Zuschlagseinstellungen**

Dieser Abschnitt ermöglicht es Ihnen, Rabatte oder Zuschläge für die Nutzung der Banküberweisung zu konfigurieren.

- **Rabatt-Typ:**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie der Rabatt berechnet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Prozentsatz:* Der Rabatt ist ein Prozentsatz des Gesamtbestellwerts.
    - *Fester Betrag:* Der Rabatt ist ein fester Betrag, unabhängig vom Gesamtbestellwert.
  - **Empfohlener Wert:** Prozentsatz (oft ansprechender für unterschiedliche Bestellwerte).
  - **Händlerszenario:** Sie möchten 5 % Rabatt oder einen festen Rabatt von 10 € anbieten.
- **Rabattwert:**

  - **Was diese Einstellung bewirkt:** Der tatsächliche Wert des Rabatts (z. B. „5“ für 5 % oder „10 €“ für einen festen Betrag).
  - **Auswirkung der Änderung dieser Einstellung:** Wendet den Rabatt direkt auf den Gesamtbestellwert an, wenn die Banküberweisung gewählt wird.
  - **Empfohlener Wert:** Ein Wert, der die Banküberweisung attraktiv macht, ohne Ihre Margen zu beeinträchtigen.
  - **Händlerszenario:** Sie entscheiden sich, 3 % Rabatt oder 5 € Rabatt anzubieten.
- **Prozentsatz-Basis (wenn Rabatt-Typ Prozentsatz ist):**

  - **Was diese Einstellung bewirkt:** Gibt an, auf welchen Teil des Gesamtbestellwerts der prozentuale Rabatt angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert den Basisbetrag für die Rabattberechnung.
    - *Gesamtbestellwert (mit Steuern):* Rabatt wird auf den vollen Preis inklusive Steuern berechnet.
    - *Gesamtbestellwert (ohne Steuern):* Rabatt wird auf den Preis vor Steuern berechnet.
    - *Gesamtproduktwert (mit Steuern):* Rabatt nur auf den Produktwert, inklusive Steuern.
    - *Gesamtproduktwert (ohne Steuern):* Rabatt nur auf den Produktwert, exklusive Steuern.
  - **Empfohlener Wert:** Gesamtbestellwert (mit Steuern) für Einfachheit und Klarheit für den Kunden.
  - **Händlerszenario:** Sie möchten 5 % Rabatt auf den gesamten Endpreis geben, den der Kunde sieht.
- **Mindestwarenkorbwert:**

  - **Was diese Einstellung bewirkt:** Der Mindestgesamtwert, den eine Bestellung haben muss, damit der Banküberweisungsrabatt angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Der Rabatt wird nur angezeigt und angewendet, wenn der Warenkorbwert diesen Wert erreicht oder überschreitet.
  - **Empfohlener Wert:** Leer lassen, wenn kein Minimum, oder einen Wert festlegen, um größere Bestellungen zu fördern.
  - **Händlerszenario:** Sie möchten nur bei Bestellungen über 100 € einen Rabatt anbieten.
- **Maximaler Warenkorbwert:**

  - **Was diese Einstellung bewirkt:** Der maximale Gesamtwert, den eine Bestellung haben kann, damit der Banküberweisungsrabatt angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Der Rabatt wird nicht angewendet, wenn der Warenkorbwert diesen Wert überschreitet.
  - **Empfohlener Wert:** Leer lassen, wenn kein Maximum, oder einen Wert festlegen, um die Rabattgewährung bei sehr großen Bestellungen zu begrenzen.
  - **Händlerszenario:** Sie möchten keinen Rabatt auf Bestellungen über 1000 € geben.
- **Währungen:**

  - **Was diese Einstellung bewirkt:** Wählen Sie aus, für welche Währungen die Banküberweisung (und ihr Rabatt) verfügbar sein soll.
  - **Auswirkung der Änderung dieser Einstellung:** Die Zahlungsoption wird nur für Kunden angezeigt, die in den ausgewählten Währungen einkaufen.
  - **Empfohlener Wert:** Wählen Sie alle Währungen aus, die Sie akzeptieren.
  - **Händlerszenario:** Sie akzeptieren Banküberweisungen nur in EUR und USD.
- **Zonen:**

  - **Was diese Einstellung bewirkt:** Wählen Sie aus, für welche geografischen Zonen die Banküberweisung (und ihr Rabatt) verfügbar sein soll.
  - **Auswirkung der Änderung dieser Einstellung:** Die Zahlungsoption wird nur für Kunden angezeigt, deren Lieferadresse in den ausgewählten Zonen liegt.
  - **Empfohlener Wert:** Wählen Sie alle Zonen aus, in die Sie versenden.
  - **Händlerszenario:** Sie bieten Banküberweisung nur in Europa an.
- **Länder:**

  - **Was diese Einstellung bewirkt:** Wählen Sie spezifische Länder aus, in denen die Banküberweisung (und ihr Rabatt) verfügbar sein soll.
  - **Auswirkung der Änderung dieser Einstellung:** Überschreibt Zoneneinstellungen für bestimmte Länder.
  - **Empfohlener Wert:** Wählen Sie alle Länder aus, in die Sie versenden.
  - **Händlerszenario:** Sie möchten ein bestimmtes Land von Banküberweisungen ausschließen.
- **Kundengruppen:**

  - **Was diese Einstellung bewirkt:** Wählen Sie aus, welche Kundengruppen die Banküberweisung (und ihren Rabatt) sehen und nutzen können.
  - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die zu den ausgewählten Gruppen gehören, sehen diese Zahlungsoption.
  - **Empfohlener Wert:** Wählen Sie alle relevanten Kundengruppen aus (z. B. „Kunde“, „Besucher“, „Gast“).
  - **Händlerszenario:** Sie möchten Banküberweisung nur registrierten Kunden anbieten.

#### **Verwaltung unbezahlter Bestellungen**

Diese Funktionen helfen Ihnen, Bestellungen zu verwalten, die per Banküberweisung aufgegeben, aber noch nicht bezahlt wurden.

- **Erinnerungen für unbezahlte Bestellungen senden:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert automatische E-Mail-Erinnerungen an Kunden für unbezahlte Banküberweisungsbestellungen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul sendet Erinnerungs-E-Mails.
    - *Wenn deaktiviert:* Es werden keine Erinnerungen gesendet.
  - **Empfohlener Wert:** JA (hilft, abgebrochene Zahlungen zu reduzieren).
  - **Händlerszenario:** Sie möchten Kunden sanft daran erinnern, ihre Zahlung abzuschließen.
- **Erste Erinnerung nach (Tagen):**

  - **Was diese Einstellung bewirkt:** Die Anzahl der Tage nach der Bestellung, bevor die erste Erinnerungs-E-Mail gesendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Steuert den Zeitpunkt der ersten Erinnerung.
  - **Empfohlener Wert:** 2-3 Tage (gibt Kunden Zeit zum Bezahlen, aber nicht zu lange).
  - **Händlerszenario:** Sie möchten eine Erinnerung senden, wenn die Zahlung nicht innerhalb von 2 Tagen eingeht.
- **Max. Erinnerungen pro Bestellung:**

  - **Was diese Einstellung bewirkt:** Die maximale Anzahl von Erinnerungs-E-Mails, die eine Bestellung auslösen wird.
  - **Auswirkung der Änderung dieser Einstellung:** Verhindert, dass Kunden mit zu vielen Erinnerungen belästigt werden.
  - **Empfohlener Wert:** 1-2 (ausreichend, um zu erinnern, ohne zu nerven).
  - **Händlerszenario:** Sie möchten nur eine Erinnerungs-E-Mail senden.
- **Unbezahlte Bestellungen automatisch stornieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die automatische Stornierung von Banküberweisungsbestellungen, die nach einer bestimmten Frist unbezahlt bleiben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Bestellungen werden automatisch storniert, wodurch Lagerbestände freigegeben werden.
    - *Wenn deaktiviert:* Bestellungen bleiben auf unbestimmte Zeit im Status „Warten auf Banküberweisung“.
  - **Empfohlener Wert:** JA (automatisiert die Bestandsverwaltung und hält die Bestellliste sauber).
  - **Händlerszenario:** Sie möchten den Lagerbestand nicht zu lange für unbezahlte Bestellungen blockieren.
- **Stornieren nach (Tagen):**

  - **Was diese Einstellung bewirkt:** Die Anzahl der Tage nach der Bestellung, bevor sie bei Nichtzahlung automatisch storniert wird.
  - **Auswirkung der Änderung dieser Einstellung:** Steuert, wann unbezahlte Bestellungen storniert werden.
  - **Empfohlener Wert:** 5-7 Tage (ermöglicht eine angemessene Zeit für die Zahlung, verhindert aber unbegrenzte Blockierungen).
  - **Händlerszenario:** Sie möchten Bestellungen stornieren, wenn die Zahlung nicht innerhalb von 7 Tagen eingeht.
- **Nichtzahler automatisch auf die schwarze Liste setzen:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, werden Kunden, die wiederholt Banküberweisungsbestellungen aufgeben und diese dann wegen Nichtzahlung stornieren lassen, auf eine schwarze Liste gesetzt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden, die den Schwellenwert überschreiten, werden auf die schwarze Liste gesetzt.
    - *Wenn deaktiviert:* Es werden keine Kunden automatisch auf die schwarze Liste gesetzt.
  - **Empfohlener Wert:** JA (hilft, betrügerische oder zeitraubende Kunden abzuschrecken).
  - **Händlerszenario:** Sie möchten verhindern, dass Kunden, die nie bezahlen, zukünftige Banküberweisungsbestellungen aufgeben.
- **Schwellenwert für stornierte Bestellungen:**

  - **Was diese Einstellung bewirkt:** Die Anzahl der stornierten Banküberweisungsbestellungen, die ein Kunde haben kann, bevor er automatisch auf die schwarze Liste gesetzt wird.
  - **Auswirkung der Änderung dieser Einstellung:** Definiert die Toleranz für Nichtzahlung vor der Sperrung.
  - **Empfohlener Wert:** 2-3 (ermöglicht echte Fehler, fängt aber Wiederholungstäter ab).
  - **Händlerszenario:** Sie möchten einen Kunden nach 3 unbezahlten und stornierten Banküberweisungsbestellungen auf die schwarze Liste setzen.

#### **Erweiterte Einstellungen**

- **Cron-Job-Token:**

  - **Was diese Einstellung bewirkt:** Ein eindeutiges Sicherheitstoken, das zur Sicherung der Cron-Job-URL des Moduls verwendet wird. Dies ist unerlässlich, damit die automatischen Erinnerungs- und Stornierungsfunktionen funktionieren.
  - **Auswirkung der Änderung dieser Einstellung:** Der Cron-Job wird nur ausgeführt, wenn dieses Token korrekt in der URL enthalten ist.
  - **Empfohlener Wert:** Belassen Sie es wie generiert. Ändern Sie es nicht, es sei denn, Sie wissen, was Sie tun.
  - **Händlerszenario:** Sie müssen einen Cron-Job auf Ihrem Server einrichten, um die automatisierten Aufgaben des Moduls auszuführen. Die Cron-URL sieht etwa so aus: `ihrshop.com/module/bankwiredis/cron?token=IHR_TOKEN_HIER`.
- **CSS-Selektoren für dynamische Updates:**

  - **Was diese Einstellung bewirkt:** Diese Felder ermöglichen es Ihnen, CSS-Selektoren für Elemente auf Ihrer Checkout-Seite anzugeben, die den Warenkorb-Gesamtbetrag, den Zwischensumme und die Versandkosten anzeigen. Das Modul verwendet diese, um die Preise dynamisch zu aktualisieren, wenn ein Rabatt angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn Ihr Theme nicht-standardmäßige CSS-Klassen für diese Elemente verwendet, stellt die Anpassung dieser Selektoren sicher, dass der Rabatt während des Checkouts korrekt in den angezeigten Preisen widergespiegelt wird.
  - **Empfohlener Wert:** Belassen Sie es bei den Standardeinstellungen, es sei denn, der Rabatt wird auf Ihrer Checkout-Seite nicht korrekt angezeigt. Bei Problemen wenden Sie sich an Ihren Theme-Entwickler oder einen Webmaster.
  - **Händlerszenario:** Ihr benutzerdefiniertes Theme verwendet `.my-custom-total-price` anstelle des Standard-`.cart-total-price`. Sie würden dieses Feld aktualisieren, um sicherzustellen, dass der Rabatt visuell angewendet wird.
- **E-Mail-Vorlage:**

  - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl einer benutzerdefinierten E-Mail-Vorlage für die Banküberweisungsanweisungen und Erinnerungen.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert das Design und den Inhalt der vom Modul gesendeten E-Mails.
  - **Empfohlener Wert:** Standard (es sei denn, Sie haben eine benutzerdefinierte Vorlage).
  - **Händlerszenario:** Sie möchten eine gebrandete E-Mail-Vorlage für Banküberweisungsmitteilungen verwenden.

#### **Sichtbarkeitsregeln (Erweiterte Rabatt-Zielgruppenansprache)**

Dieser Abschnitt ermöglicht es Ihnen, sehr spezifische Regeln dafür zu erstellen, wann der Banküberweisungsrabatt angeboten wird.

- **Regelname:**

  - **Was diese Einstellung bewirkt:** Ein beschreibender Name für Ihre Rabattregel (z. B. „Feiertagsrabatt für Banküberweisung“).
  - **Auswirkung der Änderung dieser Einstellung:** Hilft Ihnen, verschiedene Regeln zu identifizieren und zu verwalten.
  - **Empfohlener Wert:** Klarer und prägnanter Name.
  - **Händlerszenario:** Sie haben mehrere Rabattregeln und müssen diese unterscheiden.
- **Aktiv:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert diese spezifische Rabattregel.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Regel ist aktiv und ihre Bedingungen werden geprüft.
    - *Wenn deaktiviert:* Die Regel wird ignoriert.
  - **Empfohlener Wert:** JA (wenn die Regel angewendet werden soll).
  - **Händlerszenario:** Sie möchten einen saisonalen Rabatt vorübergehend deaktivieren.
- **Position (Priorität):**

  - **Was diese Einstellung bewirkt:** Bestimmt die Reihenfolge, in der Regeln ausgewertet werden, wenn mehrere Regeln zutreffen könnten. Kleinere Zahlen haben eine höhere Priorität.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn der Warenkorb eines Kunden mehreren Regeln entspricht, wird die Regel mit der niedrigsten Position angewendet.
  - **Empfohlener Wert:** Verwenden Sie fortlaufende Zahlen (1, 2, 3…), um die Priorität zu verwalten.
  - **Händlerszenario:** Wenn ein Kunde sowohl für eine Regel „Allgemein 5 % Rabatt“ (Position 10) als auch für eine Regel „VIP 10 % Rabatt“ (Position 5) qualifiziert ist, wird die VIP-Regel angewendet.
- **Rabatt-Typ, Rabattwert, Prozentsatz-Basis, Mindestwarenkorbwert, Maximaler Warenkorbwert, Währungen, Zonen, Länder, Kundengruppen:**

  - **Was diese Einstellung bewirkt:** Dies sind dieselben Einstellungen wie im Abschnitt „Rabatt- & Zuschlagseinstellungen“ oben beschrieben, jedoch speziell auf *diese einzelne Regel* angewendet. Dies ermöglicht es Ihnen, unterschiedliche Rabattbeträge oder Bedingungen für verschiedene Szenarien zu haben.
  - **Auswirkung der Änderung dieser Einstellung:** Der innerhalb dieser Regel definierte Rabatt wird nur angewendet, wenn alle spezifischen Bedingungen erfüllt sind.
  - **Empfohlener Wert:** Konfigurieren Sie dies basierend auf Ihrer spezifischen Werbestrategie.
  - **Händlerszenario:** Sie möchten einen 10 %-Rabatt für Banküberweisungen nur für Kunden der Gruppe „Großhändler“ und nur für Bestellungen über 500 € anbieten.
- **Produkte:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, festzulegen, dass diese Rabattregel nur gilt, wenn bestimmte Produkte im Warenkorb sind.
  - **Auswirkung der Änderung dieser Einstellung:** Der Banküberweisungsrabatt wird nur angeboten, wenn eines oder mehrere der ausgewählten Produkte im Warenkorb des Kunden vorhanden sind.
  - **Empfohlener Wert:** Leer lassen, um auf alle Produkte anzuwenden, oder spezifische Produkte für gezielte Werbeaktionen auswählen.
  - **Händlerszenario:** Sie möchten einen Banküberweisungsrabatt nur anbieten, wenn ein Kunde einen bestimmten hochwertigen Artikel kauft.
- **Kategorien:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, festzulegen, dass diese Rabattregel nur gilt, wenn Produkte aus bestimmten Kategorien im Warenkorb sind.
  - **Auswirkung der Änderung dieser Einstellung:** Der Banküberweisungsrabatt wird nur angeboten, wenn eines oder mehrere Produkte aus den ausgewählten Kategorien im Warenkorb des Kunden vorhanden sind.
  - **Empfohlener Wert:** Leer lassen, um auf alle Kategorien anzuwenden, oder spezifische Kategorien für gezielte Werbeaktionen auswählen.
  - **Händlerszenario:** Sie möchten einen Banküberweisungsrabatt nur für Produkte in Ihrer Kategorie „Elektronik“ anbieten.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Banküberweisung aktivieren | JA | Aktiviert/deaktiviert die Zahlungsmethode. |
|  | Titel der Banküberweisung | „Per Banküberweisung bezahlen“ | Text, der für die Zahlungsoption angezeigt wird. |
|  | Zahlungsanweisungen (Checkout) | Kurzer, klarer Text | Informationen, die auf der Zahlungsoptionsseite angezeigt werden. |
|  | Zahlungsanweisungen (Bestätigung) | Detaillierte Bankinformationen | Bankdaten und Anweisungen nach der Bestellung. |
|  | Kontoinhaber | Ihr Firmenname | Name auf dem Bankkonto. |
|  | Bankname | Ihre Bank | Name Ihrer Bank. |
|  | Adresse | Ihre Bankadresse | Adresse Ihrer Bank. |
|  | IBAN | Ihre IBAN | Internationale Bankkontonummer. |
|  | SWIFT/BIC | Ihr SWIFT/BIC | Bank Identifier Code für internationale Überweisungen. |
|  | Zusätzliche Informationen | Optionale Hinweise | Zusätzliche Anweisungen für Kunden. |
|  | Rabatt-Typ | Prozentsatz | Wie der Rabatt berechnet wird (prozentual/fest). |
|  | Rabattwert | 0 (oder gewünschter Wert) | Der tatsächliche Rabattbetrag oder Prozentsatz. |
|  | Prozentsatz-Basis | Gesamtbestellwert (mit Steuern) | Auf welchen Betrag der prozentuale Rabatt angewendet wird. |
|  | Mindestwarenkorbwert | Leer (oder gewünschter Wert) | Mindestbestellwert für Rabatt. |
|  | Maximaler Warenkorbwert | Leer (oder gewünschter Wert) | Maximaler Bestellwert für Rabatt. |
|  | Währungen | Alle aktiv | Währungen, in denen Banküberweisung verfügbar ist. |
|  | Zonen | Alle aktiv | Geografische Zonen, in denen Banküberweisung verfügbar ist. |
|  | Länder | Alle aktiv | Spezifische Länder, in denen Banküberweisung verfügbar ist. |
|  | Kundengruppen | Alle aktiv | Kundengruppen, die Banküberweisung nutzen können. |
|  | Erinnerungen für unbezahlte Bestellungen senden | JA | Aktiviert E-Mail-Erinnerungen für unbezahlte Bestellungen. |
|  | Erste Erinnerung nach (Tagen) | 2-3 Tage | Verzögerung vor der ersten Erinnerung. |
|  | Max. Erinnerungen pro Bestellung | 1-2 | Maximale Anzahl von Erinnerungs-E-Mails. |
|  | Unbezahlte Bestellungen automatisch stornieren | JA | Storniert unbezahlte Bestellungen automatisch. |
|  | Stornieren nach (Tagen) | 5-7 Tage | Verzögerung vor der automatischen Stornierung. |
|  | Nichtzahler automatisch auf die schwarze Liste setzen | JA | Setzt Kunden mit zu vielen stornierten Bestellungen auf die schwarze Liste. |
|  | Schwellenwert für stornierte Bestellungen | 2-3 | Anzahl der stornierten Bestellungen vor der Sperrung. |
|  | Cron-Job-Token | Automatisch generiert | Sicherheitstoken für Cron-Job. |
|  | CSS-Selektoren | Standard (oder themenspezifisch) | Für dynamische Preisaktualisierungen im Checkout. |
|  | E-Mail-Vorlage | Standard | E-Mail-Vorlage für Banküberweisungsmitteilungen. |
|  | **Sichtbarkeitsregeln** | Regelname | Beschreibender Name |
|  | Aktiv | JA | Aktiviert/deaktiviert eine spezifische Regel. |
|  | Position (Priorität) | 1, 2, 3… | Reihenfolge der Regelauswertung (niedriger = höhere Priorität). |
|  | Produkte | Leer (oder spezifische Produkte) | Rabatt gilt nur, wenn diese Produkte im Warenkorb sind. |
|  | Kategorien | Leer (oder spezifische Kategorien) | Rabatt gilt nur, wenn Produkte aus diesen Kategorien im Warenkorb sind. |

### 2.2 Back-Office Controller-Bildschirm: AdminBankwiredisSearchController

- **Bildschirmname & Menüpfad:** Dieser Controller wird typischerweise zur Verwaltung spezifischer Entitäten im Zusammenhang mit dem Modul verwendet, wie z. B. gesperrte Kunden oder spezifische Rabattregeln, oft zugänglich über einen Unterreiter unter der Hauptmodulkonfiguration oder einen dedizierten Menüpunkt. In diesem Modul wird er wahrscheinlich zur Verwaltung der Sichtbarkeitsregeln oder gesperrten Kunden verwendet.
  - **Menüpfad:** Wahrscheinlich über einen Reiter oder Link innerhalb der Hauptkonfigurationsseite des Moduls „Banküberweisung mit Rabatt“ zugänglich, oder möglicherweise unter **Verkauf > Bestellungen > Banküberweisung mit Rabatt Blacklist** (Beispiel, der tatsächliche Ort kann je nach PrestaShop-Version und Moduldesign variieren).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm bietet eine rasterbasierte Verwaltungsansicht.
  - **Listenansicht:** Zeigt eine Liste von Elementen an (z. B. gesperrte Kunden, Rabattregeln). Jede Zeile zeigt typischerweise relevante Details wie Kunden-ID, Kunden-E-Mail, Grund für die Sperrung, Regelname, Aktiv-Status usw.
  - **Hinzufügen/Bearbeiten-Schaltflächen:** Ermöglicht das manuelle Hinzufügen neuer Einträge (z. B. einen Kunden manuell sperren) oder das Bearbeiten bestehender Einträge.
  - **Massenaktionen:** Optionen zum Ausführen von Aktionen für mehrere ausgewählte Elemente (z. B. mehrere gesperrte Kunden löschen).
  - **Suchen/Filtern:** Tools zum Auffinden spezifischer Einträge innerhalb der Liste.
- **Auswirkung von Änderungen:**
  - **Hinzufügen/Bearbeiten von Blacklist-Einträgen:** Wirkt sich direkt darauf aus, welche Kunden die Banküberweisung nicht nutzen dürfen.
  - **Hinzufügen/Bearbeiten von Rabattregeln:** Ändert die Bedingungen, unter denen Rabatte angewendet werden, was sich auf die Preisgestaltung und Kundenanreize auswirkt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie regelmäßig die Liste der gesperrten Kunden, um sicherzustellen, dass sie aktuell ist.
  2. Wenn Sie einen Kunden manuell sperren müssen (z. B. nach direkter Kommunikation), verwenden Sie hier die Funktion „Hinzufügen“.
  3. Wenn Sie neue Rabattregeln anpassen oder erstellen müssen, verwalten Sie diese hier und stellen Sie sicher, dass sie mit Ihren aktuellen Werbeaktionen übereinstimmen.

### 2.3 Back-Office Controller-Bildschirm: index.php (Admin Controller)

- **Bildschirmname & Menüpfad:** Die Datei `index.php` in einem Admin-Controller-Verzeichnis dient oft als Platzhalter oder Weiterleitung, oder in einigen Fällen kann sie der Einstiegspunkt für ein Dashboard oder eine einfache Auflistung sein. Angesichts der Funktionen des Moduls könnte dies ein Dashboard für Banküberweisungsstatistiken oder eine einfache Auflistung ausstehender Banküberweisungsbestellungen sein.
  - **Menüpfad:** Potenziell ein Unterreiter unter der Hauptmodulkonfiguration oder ein dedizierter Menüpunkt wie **Verkauf > Bestellungen > Banküberweisung mit Rabatt Dashboard**.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm präsentiert wahrscheinlich ein Raster oder ein Dashboard.
  - **Raster / Verwaltungsansicht:** Könnte eine Liste der letzten Banküberweisungsbestellungen, deren Status, gesendete Zahlungserinnerungen oder den Stornierungsstatus anzeigen.
  - **Analysen/Statistiken:** Könnte Diagramme oder Zusammenfassungen im Zusammenhang mit Banküberweisungszahlungen anzeigen, wie z. B. Konversionsraten, durchschnittlich angewendeter Rabatt oder Anzahl unbezahlter Bestellungen.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient typischerweise der Überwachung und Berichterstattung und nicht direkten Konfigurationsänderungen. Alle hier vorgenommenen Aktionen (z. B. das manuelle Markieren einer Bestellung als bezahlt) würden den Bestellstatus in PrestaShop aktualisieren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie dieses Dashboard regelmäßig, um die Leistung Ihrer Banküberweisungszahlungsmethode zu überwachen.
  2. Überprüfen Sie ausstehende Banküberweisungsbestellungen, um sicherzustellen, dass sie wie erwartet bearbeitet oder erinnert/storniert werden.
  3. Nutzen Sie alle verfügbaren Statistiken, um die Wirksamkeit Ihrer Banküberweisungsrabatte und des Erinnerungssystems zu bewerten.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Banküberweisungsoption wird auf meiner Checkout-Seite nicht angezeigt.**

- **A:** Überprüfen Sie zunächst, ob „Banküberweisung aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
- **A:** Überprüfen Sie als Nächstes Ihre Einstellungen für „Währungen“, „Zonen“, „Länder“ und „Kundengruppen“. Wenn der Kontext des Kunden (Währung, Lieferadresse oder Gruppe) nicht mit Ihren Auswahlen übereinstimmt, wird die Zahlungsmethode nicht angezeigt.
- **A:** Wenn Sie spezifische Sichtbarkeitsregeln haben, stellen Sie sicher, dass der Warenkorb des Kunden alle Bedingungen erfüllt (Min./Max. Warenkorbwert, spezifische Produkte/Kategorien).
- **A:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren).

**F2: Der Rabatt wird nicht korrekt angewendet oder angezeigt auf der Checkout-Seite.**

- **A:** Überprüfen Sie Ihre Einstellungen für „Rabatt-Typ“ und „Rabattwert“.
- **A:** Überprüfen Sie alle Einstellungen für „Mindestwarenkorbwert“ oder „Maximaler Warenkorbwert“ – der Warenkorb-Gesamtbetrag muss innerhalb dieser Bereiche liegen.
- **A:** Wenn Sie ein benutzerdefiniertes Theme verwenden, kann das Modul möglicherweise die richtigen CSS-Selektoren nicht finden, um die Preise dynamisch zu aktualisieren. Gehen Sie zum Abschnitt „Erweiterte Einstellungen“ und stellen Sie sicher, dass die „CSS-Selektoren für dynamische Updates“ mit den tatsächlichen Selektoren Ihres Themes für Warenkorb-Gesamtbetrag, Zwischensumme und Versand übereinstimmen. Möglicherweise müssen Sie einen Webmaster konsultieren, um den Code Ihres Themes zu überprüfen.
- **A:** Leeren Sie Ihren PrestaShop-Cache.

**F3: Automatische Erinnerungen oder Stornierungen funktionieren nicht.**

- **A:** Dies ist fast immer ein Cron-Job-Problem. Sie müssen einen Cron-Job auf Ihrem Server einrichten, um die Aufgaben des Moduls regelmäßig auszuführen.
- **A:** Kopieren Sie in den „Erweiterten Einstellungen“ des Moduls das „Cron-Job-Token“ und die vollständige Cron-URL.
- **A:** Greifen Sie auf Ihr Hosting-Kontrollpanel (cPanel, Plesk usw.) zu und suchen Sie den Abschnitt „Cron-Jobs“.
- **A:** Fügen Sie einen neuen Cron-Job hinzu, der die bereitgestellte URL alle paar Stunden ausführt (z. B. `wget -O /dev/null "https://ihrshop.com/module/bankwiredis/cron?token=IHR_TOKEN_HIER"`).
- **A:** Stellen Sie sicher, dass „Erinnerungen für unbezahlte Bestellungen senden“ und „Unbezahlte Bestellungen automatisch stornieren“ aktiviert sind und die Tage korrekt eingestellt sind.

**F4: Wie übersetze ich die Texte des Moduls in andere Sprachen?**

- **A:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- **A:** Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Banküberweisung mit Rabatt“ aus dem Modul-Dropdown.
- **A:** Sie können dann alle übersetzbaren Zeichenfolgen für das Modul bearbeiten. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Ein Kunde wurde auf die schwarze Liste gesetzt, aber ich möchte ihm die Nutzung der Banküberweisung wieder erlauben.**

- **A:** Navigieren Sie zum dedizierten Admin-Bildschirm des Moduls (wahrscheinlich unter **Verkauf > Bestellungen > Banküberweisung mit Rabatt Blacklist** oder ähnlich, oder einem Reiter innerhalb der Modulkonfiguration).
- **A:** Suchen Sie den Kunden in der Liste und löschen Sie entweder seinen Blacklist-Eintrag oder bearbeiten Sie ihn, um die Blacklist für ihn zu deaktivieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Banküberweisung mit Rabatt“ (`bankwiredis`) erweitert die Zahlungsfunktionalität von PrestaShop und folgt dem MVC-Muster. Es integriert sich über `PaymentOptions`-Hooks in den Checkout-Prozess, verwaltet Bestellstatus und implementiert automatisierte Aufgaben (Erinnerungen, Stornierungen, Blacklisting) über einen Cron-Job. Die Rabattlogik wird dynamisch während des Checkouts angewendet und mit der Bestellung persistent gespeichert. Benutzerdefinierte Admin-Controller bieten Verwaltungsoberflächen für Rabattregeln und gesperrte Kunden.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/cron.php`
  - **Klassenname:** `BankwiredisCronModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller handhabt die Ausführung geplanter Aufgaben. Er ist so konzipiert, dass er von einem serverseitigen Cron-Job unter Verwendung eines sicheren Tokens aufgerufen wird. Er verarbeitet Erinnerungen für unbezahlte Bestellungen, automatische Stornierungen und die Sperrung von Kunden basierend auf der Modulkonfiguration. Er rendert keine Front-Office-Inhalte direkt, sondern führt Hintergrundoperationen aus.
- `controllers/front/index.php`
  - **Klassenname:** `BankwiredisIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Oft ein Platzhalter oder ein Standard-Einstiegspunkt. In diesem Modul könnte er Weiterleitungen handhaben oder als Fallback dienen, wenn andere spezifische Front-Controller nicht übereinstimmen. Er hat typischerweise keine direkte benutzerorientierte Funktion.
- `controllers/front/payment.php`
  - **Klassenname:** `BankwiredisPaymentModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist dafür verantwortlich, die Banküberweisungsdetails und -anweisungen dem Kunden anzuzeigen, *nachdem* dieser die Banküberweisung als Zahlungsmethode ausgewählt hat, aber *bevor* die Bestellung vollständig validiert wird. Er bereitet die Daten (Bankdaten, Endbetrag mit Rabatt) für die Vorlage `payment.tpl` oder `validation.tpl` vor.
- `controllers/front/validation.php`
  - **Klassenname:** `BankwiredisValidationModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dies ist der entscheidende Controller, der die endgültige Validierung einer Banküberweisungsbestellung verarbeitet. Nachdem der Kunde seine Wahl bestätigt hat, erstellt dieser Controller die Bestellung in PrestaShop, setzt ihren anfänglichen Status (z. B. „Warten auf Banküberweisung“), wendet den berechneten Rabatt an und leitet den Kunden zur Bestellbestätigungsseite weiter.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminBankwiredisSearchController.php`
  - **Klassenname:** `AdminBankwiredisSearchController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Wahrscheinlich ein Unterreiter unter der Hauptmodulkonfiguration oder ein dedizierter Menüeintrag.
  - **Verwaltete Entität:** Dieser Controller verwaltet die benutzerdefinierten Entitäten des Moduls, insbesondere die Rabatt-Sichtbarkeitsregeln und potenziell die gesperrten Kunden. Er bietet eine Standard-PrestaShop `HelperList`- oder `HelperForm`-Schnittstelle zum Anzeigen, Hinzufügen, Bearbeiten und Löschen dieser Datensätze.
- `controllers/admin/index.php`
  - **Klassenname:** `AdminBankwiredisIndexController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Ähnlich wie `AdminBankwiredisSearchController` wäre dies eine dedizierte Admin-Seite.
  - **Verwaltete Entität:** Angesichts der Funktionen des Moduls dient dieser Controller wahrscheinlich als Dashboard oder Verwaltungsoberfläche für die Kerndaten des Moduls, wie z. B. eine Liste ausstehender Banküberweisungsbestellungen, Statistiken oder eine vereinfachte Ansicht der gesperrten Kunden.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass die Daten des Moduls (wie Rabattregeln, gesperrte Kunden) direkt in `ps_configuration` gespeichert oder über generische `ObjectModel`-Instanzen verwaltet werden, die in der Hauptdatei `bankwiredis.php` oder direkt in den Admin-Controllern definiert sind.

- **Hinweis:** Wenn benutzerdefinierte Tabellen verwendet werden, würden deren `ObjectModel`-Definitionen typischerweise hier liegen. Das Modul verwendet wahrscheinlich `Configuration::get()` und `Configuration::updateValue()` für die meisten Einstellungen und potenziell `Db::getInstance()` für direkte Datenbankinteraktionen für komplexere Datenstrukturen wie Rabattregeln oder gesperrte Kunden, falls diese nicht einem benutzerdefinierten `ObjectModel` zugeordnet sind.

### 4.4 JavaScript-Assets (`views/js/`)

- `bankwiredis/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Bietet Autocomplete-Funktionalität, wahrscheinlich in Admin-Formularen (z. B. `AdminBankwiredisSearchController`) zur Auswahl von Produkten oder Kategorien bei der Definition von Rabatt-Sichtbarkeitsregeln verwendet. Es überwacht Benutzereingaben in spezifischen Textfeldern und sendet AJAX-Anfragen, um passende Elemente vorzuschlagen.
- `bankwiredis/views/js/adminBankwiredisAccounts.js`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Verwaltet wahrscheinlich dynamisches Verhalten auf der Konfigurationsseite des Moduls im Zusammenhang mit Bankkontodaten. Dies könnte das Anzeigen/Ausblenden von Feldern basierend auf ausgewählten Optionen, Eingabevalidierung oder AJAX-Aufrufe zum Speichern von Kontoinformationen umfassen.
- `bankwiredis/views/js/adminBankwiredisDashboard.js`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Verwaltet interaktive Elemente und Datenvisualisierung auf dem Admin-Dashboard des Moduls (z. B. `AdminBankwiredisIndexController`). Dies könnte das Abrufen von Daten über AJAX umfassen, um Diagramme, Tabellen zu füllen oder Statistiken zu aktualisieren, und die Handhabung von Benutzerinteraktionen mit Dashboard-Widgets.
- `bankwiredis/views/js/bankwiredis-checkout.js`
  - **Geltungsbereich:** Front-Office.
  - **Funktionalität:** Dies ist ein kritisches Skript für das Kundenerlebnis. Es überwacht die Auswahl der Banküberweisungsoption auf der Checkout-Seite. Nach der Auswahl sendet es einen AJAX-Aufruf an den Front-Controller des Moduls, um den dynamischen Rabatt zu berechnen und anzuzeigen, wobei die Elemente für den Gesamtbestellwert, die Zwischensumme und die Versandkosten auf der Seite aktualisiert werden. Es verwendet die im Back Office konfigurierten CSS-Selektoren (`BDIS_CSS_PAY_INPUT`, `BDIS_CSS_CART_TOTAL` usw.), um die korrekten DOM-Elemente für die Aktualisierung anzusprechen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `bankwiredis/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Gestaltet die Autocomplete-Dropdown-Vorschläge und Eingabefelder, die in den Admin-Suchwerkzeugen verwendet werden.
- `bankwiredis/views/css/admin_bankwiredis.css`
  - **Geltungsbereich:** Back-Office.
  - **Funktionalität:** Bietet spezifisches Styling für die Konfigurationsseite des Moduls und benutzerdefinierte Admin-Controller-Ansichten, um eine konsistente und benutzerfreundliche Oberfläche innerhalb des PrestaShop Back Office zu gewährleisten.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

- `bankwiredis/views/templates/hook/infos.tpl`
  - **Hook:** Wahrscheinlich `displayPaymentInfo` oder ähnlich.
  - **Ausgabe:** Zeigt allgemeine Informationen oder eine Zusammenfassung zur Banküberweisungsmethode, möglicherweise einschließlich des Rabattangebots, auf der Zahlungsoptionsseite oder in der Bestellzusammenfassung an.
- `bankwiredis/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentOptions` (PrestaShop 1.7+), `displayPayment` (PrestaShop 1.6).
  - **Ausgabe:** Rendert die eigentliche Banküberweisungsoption auf der Checkout-Seite, einschließlich Titel, Beschreibung und des dynamisch berechneten Rabattbetrags. Hier wählt der Kunde „Per Banküberweisung bezahlen“.
- `bankwiredis/views/templates/hook/payment_return.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Ausgabe:** Zeigt die Bankkontodaten und Zahlungsanweisungen auf der Bestellbestätigungsseite an, nachdem ein Kunde erfolgreich eine Banküberweisungsbestellung aufgegeben hat.
- `bankwiredis/views/templates/hook/payment_return_pdf_invoice.tpl`
  - **Hook:** `displayPDFInvoice` (oder ähnlich für die PDF-Generierung).
  - **Ausgabe:** Stellt den notwendigen Inhalt (Bankdaten, Rabattzusammenfassung) bereit, der in die für Banküberweisungsbestellungen generierte PDF-Rechnung aufgenommen werden soll.

#### Admin-Vorlagen (`views/templates/admin/`)

- `bankwiredis/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Enthält wahrscheinlich JavaScript- und CSS-Assets für das Autocomplete-Suchwerkzeug in Admin-Formularen.
- `bankwiredis/views/templates/admin/scopeSelector.tpl`
  - **Ausgabe:** Eine Vorlage zur Auswahl des Geltungsbereichs (z. B. Shop, Gruppe, alle Shops) in einer Multi-Store-Umgebung, oft in Konfigurationsformularen verwendet.
- `bankwiredis/views/templates/admin/selectedProducts.tpl`
  - **Ausgabe:** Zeigt eine Liste von Produkten an, die für eine bestimmte Rabattregel ausgewählt wurden (z. B. in `AdminBankwiredisSearchController` bei der Konfiguration einer regelbasierten Produktregel).

#### Front-Office-Vorlagen (`views/templates/front/`)

- `bankwiredis/views/templates/front/validation.tpl`
  - **Ausgabe:** Diese Vorlage wird von `BankwiredisPaymentModuleFrontController` oder `BankwiredisValidationModuleFrontController` gerendert, um die endgültigen Bankdaten und Anweisungen *vor* der vollständigen Bestätigung der Bestellung oder unmittelbar danach anzuzeigen, wodurch eine dedizierte Seite für Zahlungsanweisungen bereitgestellt wird.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul verwendet hauptsächlich die PrestaShop-Tabelle `ps_configuration` für die meisten seiner Einstellungen (z. B. `BANK_WIRE_DIS_OWNER_`, `BDIS_CRON_TOKEN`, `BANK_WIRE_DIS_CHARGEP`).
Für komplexere Daten wie Rabatt-Sichtbarkeitsregeln und gesperrte Kunden erstellt das Modul wahrscheinlich während seiner `install()`-Methode benutzerdefinierte Tabellen. Basierend auf den Konfigurationsoptionen wären diese Tabellen typischerweise:

- `ps_bankwiredis_rules`: Speichert die Definition jeder Rabattregel (Regelname, Aktiv-Status, Rabatt-Typ, Wert, Min./Max. Warenkorb, Währungen, Zonen, Länder, Kundengruppen, Produkte, Kategorien).
- `ps_bankwiredis_blacklist`: Speichert Datensätze von gesperrten Kunden (Kunden-ID, E-Mail, Grund, Datum der Sperrung).
- `ps_bankwiredis_reminders`: Speichert ein Protokoll der gesendeten Erinnerungs-E-Mails für jede Bestellung, um `Max reminders per order` zu verfolgen.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Wird verwendet, um Front-Office-CSS- und JavaScript-Assets (`bankwiredis-checkout.js`) für die dynamische Rabattanzeige zu laden. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien-Assets lädt. | Wird verwendet, um Back-Office-CSS- und JavaScript-Assets (`admin_bankwiredis.css`, `adminBankwiredisAccounts.js`, `autocomplete.js`) für die Konfigurations- und Admin-Seiten des Moduls zu laden. |
| `displayPaymentOptions` | Auf der Checkout-Seite, wenn Zahlungsoptionen aufgelistet werden. | Rendert die Banküberweisungsoption, einschließlich des berechneten Rabatts, unter Verwendung von `payment.tpl`. |
| `displayPaymentReturn` | Auf der Bestellbestätigungsseite nach einer erfolgreichen Bestellung. | Zeigt Bankkontodaten und Zahlungsanweisungen dem Kunden an, unter Verwendung von `payment_return.tpl`. |
| `displayPDFInvoice` | Wenn eine PDF-Rechnung generiert wird. | Fügt Bankkontodaten und Rabattinformationen in die für Banküberweisungsbestellungen generierte PDF-Rechnung ein, unter Verwendung von `payment_return_pdf_invoice.tpl`. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird verwendet, um Bestelldetails zu erfassen, den endgültigen Rabatt anzuwenden und die Bestellung möglicherweise für die Erinnerungs-/Stornierungsbearbeitung zu protokollieren. |
| `displayPaymentInfo` | (Implizit) Oft verwendet, um zusätzliche Informationen zur Zahlungsauswahl anzuzeigen. | Rendert `infos.tpl` mit allgemeinen Banküberweisungsinformationen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Entwickler-Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Stellen Sie sicher, dass Sie die neueste kompatible Version des Moduls für Ihren PrestaShop-Shop verwenden.
