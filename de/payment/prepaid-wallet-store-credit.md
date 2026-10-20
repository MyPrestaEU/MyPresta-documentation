---
title: "Prepaid Wallet & Store Credit - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Prepaid Wallet & Store Credit“ von MyPresta.eu."
sidebar:
  label: "Prepaid Wallet & Store Credit - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Prepaid Wallet & Store Credit auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/prepaid-wallet-store-credit.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/prepaid-wallet-store-credit/)
>
> ---


# Prepaid Wallet & Store Credit

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten Ihres Prepaid-Wallet-Systems einstellen.

#### Registerkarte Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um das gesamte Prepaid-Wallet-System für Ihren Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen Wallet-Optionen, können aufladen, Guthaben verwenden, und Sie können Wallets im Back Office verwalten.
    - *Wenn deaktiviert:* Alle Wallet-Funktionen sind für Kunden ausgeblendet, und sie können ihr Guthaben nicht verwenden oder verwalten. Die Admin-Verwaltung kann weiterhin zugänglich sein, hat aber keine Auswirkungen auf das Front Office.
  - **Empfohlener Wert:** JA (um das Modul zu aktivieren).
  - **Händlerszenario / Beispiel:** Sie sind bereit, Ihr Treueprogramm zu starten. Aktivieren Sie diese Einstellung. Wenn Sie es vorübergehend für Wartungsarbeiten deaktivieren müssen, schalten Sie es aus.
- **Kunden erlauben, Wallet aufzuladen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden selbst aktiv Guthaben zu ihrem Wallet hinzufügen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen eine Option „Wallet aufladen“ in ihrem Konto, die es ihnen ermöglicht, Shop-Guthaben zu kaufen.
    - *Wenn deaktiviert:* Kunden können Guthaben nur über Geschenkcodes oder vom Administrator ausgestellte Rückerstattungen/Boni erhalten. Sie können kein Guthaben direkt kaufen.
  - **Empfohlener Wert:** JA (um Self-Service-Loyalität zu fördern).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden jederzeit Shop-Guthaben kaufen können. Aktivieren Sie dies. Wenn Sie Guthaben nur als Belohnung oder Geschenkkarten ausgeben möchten, deaktivieren Sie es.
- **Mindestaufladebetrag:**

  - **Was diese Einstellung bewirkt:** Legt den niedrigsten Betrag fest, den ein Kunde in einer einzelnen Transaktion zu seinem Wallet hinzufügen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert festgelegt ist (z. B. 10,00):* Kunden können nicht weniger als diesen Betrag aufladen.
    - *Wenn auf 0 oder leer gesetzt:* Es wird kein Mindestaufladebetrag erzwungen.
  - **Empfohlener Wert:** 10,00 (oder ein angemessener Betrag für Ihr Geschäft, um Transaktionsgebühren zu decken und sinnvolle Aufladungen zu fördern).
  - **Händlerszenario / Beispiel:** Sie möchten nicht, dass Kunden 0,50 EUR aufladen. Setzen Sie dies auf 5,00 EUR, um einen Mindestwert zu gewährleisten.
- **Maximaler Aufladebetrag:**

  - **Was diese Einstellung bewirkt:** Legt den höchsten Betrag fest, den ein Kunde in einer einzelnen Transaktion zu seinem Wallet hinzufügen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert festgelegt ist (z. B. 500,00):* Kunden können nicht mehr als diesen Betrag aufladen.
    - *Wenn auf 0 oder leer gesetzt:* Es wird kein maximaler Aufladebetrag erzwungen.
  - **Empfohlener Wert:** 500,00 (oder eine geeignete Obergrenze zur Risikosteuerung und für große Transaktionen).
  - **Händlerszenario / Beispiel:** Sie möchten extrem große Einzelaufladungen aus Sicherheits- oder Liquiditätsgründen verhindern. Setzen Sie dies auf 1000,00 EUR.
- **Kunden erlauben, Geschenkcodes zu kaufen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Kunden Geschenkcodes kaufen können, um sie anderen zu schenken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können Geschenkcodes eines bestimmten Wertes kaufen, die dann von jedem eingelöst werden können.
    - *Wenn deaktiviert:* Geschenkcodes können nur vom Shop-Administrator generiert und ausgegeben werden.
  - **Empfohlener Wert:** JA (um Ihre Geschenkoptionen zu erweitern).
  - **Händlerszenario / Beispiel:** Sie möchten digitale Geschenkkarten anbieten. Aktivieren Sie dies, damit Kunden sie für Freunde und Familie kaufen können.
- **Geschenkcode-Ablauf (Tage):**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele Tage ein Geschenkcode nach dem Kauf oder der Generierung gültig bleibt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine Zahl festgelegt ist (z. B. 365):* Geschenkcodes verfallen nach dieser Anzahl von Tagen.
    - *Wenn auf 0 oder leer gesetzt:* Geschenkcodes verfallen nicht.
  - **Empfohlener Wert:** 365 (eine übliche Dauer für Geschenkkarten, oder 0 für keinen Ablauf).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Geschenkcodes innerhalb eines Jahres verwendet werden. Setzen Sie dies auf 365.
- **Wallet-Guthaben-Ablauf (Tage):**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele Tage Wallet-Guthaben gültig bleibt, nachdem es hinzugefügt wurde (entweder durch Aufladung, Geschenkcode-Einlösung oder Admin-Guthaben).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine Zahl festgelegt ist (z. B. 180):* Guthaben im Wallet des Kunden verfällt nach dieser Anzahl von Tagen.
    - *Wenn auf 0 oder leer gesetzt:* Wallet-Guthaben verfällt nicht.
  - **Empfohlener Wert:** 0 (kein Ablauf, um die Kundenzufriedenheit zu maximieren), oder 180/365, wenn Sie die Nutzung fördern möchten.
  - **Händlerszenario / Beispiel:** Sie möchten Kunden ermutigen, ihr Wallet-Guthaben innerhalb von 6 Monaten zu verwenden. Setzen Sie dies auf 180. Beachten Sie die Verbraucherschutzgesetze bezüglich des Ablaufs von Geschenkkarten in Ihrer Region.
- **Ablauf-Erinnerungs-E-Mail senden (Tage vor Ablauf):**

  - **Was diese Einstellung bewirkt:** Wenn der Ablauf des Wallet-Guthabens aktiviert ist, bestimmt diese Einstellung, wie viele Tage vor dem Ablauf eine E-Mail-Erinnerung an den Kunden gesendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine Zahl festgelegt ist (z. B. 7):* Kunden erhalten 7 Tage vor Ablauf ihres Wallet-Guthabens eine E-Mail.
    - *Wenn auf 0 oder leer gesetzt:* Es werden keine Ablauf-Erinnerungs-E-Mails gesendet.
  - **Empfohlener Wert:** 7 (gibt Kunden genügend Zeit zum Reagieren).
  - **Händlerszenario / Beispiel:** Sie haben einen 180-Tage-Ablauf. Setzen Sie dies auf 7, um Kunden daran zu erinnern, ihr Guthaben zu verwenden, bevor es verfällt.
- **Teilzahlungen mit Wallet erlauben:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Kunden ihr Wallet-Guthaben verwenden können, um nur einen Teil ihrer Bestellung zu bezahlen, indem sie es mit einer anderen Zahlungsmethode kombinieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn das Wallet-Guthaben geringer ist als der Gesamtbetrag der Bestellung, können Kunden das gesamte Guthaben verwenden und den Restbetrag mit einer anderen Methode bezahlen.
    - *Wenn deaktiviert:* Kunden können ihr Wallet nur verwenden, wenn es den *gesamten* Bestellbetrag abdeckt. Andernfalls müssen sie eine andere Zahlungsmethode wählen.
  - **Empfohlener Wert:** JA (um die Wallet-Nutzung zu maximieren und den Warenkorbabbruch zu reduzieren).
  - **Händlerszenario / Beispiel:** Ein Kunde hat 10 EUR in seinem Wallet und eine Bestellung von 50 EUR. Wenn aktiviert, zahlt er 10 EUR mit dem Wallet und 40 EUR mit einer Kreditkarte. Wenn deaktiviert, kann er das Wallet für diese Bestellung überhaupt nicht verwenden.
- **Option „Rückerstattung an Wallet“:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, Kunden die Option anzubieten, Rückerstattungen für zurückgegebene Bestellungen direkt in ihr Shop-Wallet zu erhalten, anstatt auf ihre ursprüngliche Zahlungsmethode.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Beim Bearbeiten einer Rückerstattung im Back Office sehen Sie eine Option, um auf das Wallet des Kunden zurückzuerstatten.
    - *Wenn deaktiviert:* Rückerstattungen müssen über Standard-PrestaShop-Methoden (z. B. zurück auf die Kreditkarte) bearbeitet werden.
  - **Empfohlener Wert:** JA (um Gelder in Ihrem Shop zu halten und Rückerstattungen zu vereinfachen).
  - **Händlerszenario / Beispiel:** Ein Kunde gibt einen Artikel zurück. Anstatt einer Kreditkartenrückerstattung bieten Sie an, das Geld in sein Wallet zu legen, um ihn zu ermutigen, etwas anderes in Ihrem Shop zu kaufen.
- **Multi-Währungs-Unterstützung aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert die Fähigkeit des Moduls, Wallet-Guthaben und Transaktionen in mehreren Währungen zu verwalten, passend zu den konfigurierten Währungen Ihres Shops.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wallet-Guthaben werden pro Währung verwaltet. Ein Kunde, der in EUR auflädt, hat ein EUR-Guthaben, und ein Kunde, der in USD auflädt, hat ein USD-Guthaben.
    - *Wenn deaktiviert:* Alle Wallet-Transaktionen werden in die Standardwährung Ihres Shops umgerechnet, was zu Problemen mit Wechselkursen führen kann.
  - **Empfohlener Wert:** JA (wenn Ihr Shop in mehreren Währungen betrieben wird).
  - **Händlerszenario / Beispiel:** Sie haben Kunden in der EU und den USA. Die Aktivierung stellt sicher, dass ein Kunde, der 50 EUR auflädt, 50 EUR in seinem Wallet hat, und ein Kunde, der 50 USD auflädt, 50 USD hat, wodurch Wechselkursverluste vermieden werden.

#### Registerkarte Auflade-Boni

- **Auflade-Boni aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert das System zur Belohnung von Kunden mit zusätzlichem Guthaben, wenn sie ihr Wallet über bestimmte Schwellenwerte aufladen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die unten definierten Bonusregeln werden auf Kundenaufladungen angewendet.
    - *Wenn deaktiviert:* Es werden keine Boni für Aufladungen gewährt.
  - **Empfohlener Wert:** JA (um größere Aufladungen zu incentivieren und den AOV zu erhöhen).
  - **Händlerszenario / Beispiel:** Sie möchten Kunden einen zusätzlichen 5%igen Bonus geben, wenn sie 100 EUR oder mehr aufladen. Aktivieren Sie dies.
- **Bonusstufen (Hinzufügen/Bearbeiten/Löschen):**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, spezifische Bonusregeln basierend auf dem Aufladebetrag zu definieren. Jede Stufe besteht aus einem Mindestaufladewert und einem Bonusprozentsatz.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Hinzufügen einer Stufe (z. B. „Mindestbetrag: 100, Bonus %: 5“):* Kunden, die 100 EUR oder mehr aufladen, erhalten zusätzlich 5% dieses Betrags in ihrem Wallet.
    - *Bearbeiten einer Stufe:* Ändert die Bonusregeln für diesen spezifischen Schwellenwert.
    - *Löschen einer Stufe:* Entfernt eine Bonusregel.
  - **Empfohlener Wert:** Erstellen Sie 2-3 Stufen (z. B. 5% für 100 EUR, 10% für 200 EUR), um progressiv größere Aufladungen zu fördern.
  - **Händlerszenario / Beispiel:**
    - Stufe 1: Mindestbetrag = 50 EUR, Bonus % = 2% (Kunde lädt 50 EUR auf, erhält 51 EUR im Wallet)
    - Stufe 2: Mindestbetrag = 100 EUR, Bonus % = 5% (Kunde lädt 100 EUR auf, erhält 105 EUR im Wallet)
    - Stufe 3: Mindestbetrag = 200 EUR, Bonus % = 10% (Kunde lädt 200 EUR auf, erhält 220 EUR im Wallet)

#### Registerkarte Anzeigeoptionen

- **Wallet-Guthaben im Header anzeigen:**

  - **Was diese Einstellung bewirkt:** Zeigt das aktuelle Wallet-Guthaben des Kunden prominent im Header-Bereich Ihres Shops an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Angemeldete Kunden sehen ihr Guthaben (z. B. „Ihr Wallet: 25,00 EUR“) in der Nähe ihres Kontolinks.
    - *Wenn deaktiviert:* Das Guthaben ist nur auf der speziellen Seite „Mein Wallet“ sichtbar.
  - **Empfohlener Wert:** JA (für hohe Sichtbarkeit und Bequemlichkeit).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden immer über ihr verfügbares Guthaben informiert sind, um sie zur Nutzung zu ermutigen.
- **Wallet-Link im Kundenkonto-Menü anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt einen direkten Link zur Seite „Mein Wallet“ im Navigationsmenü des Kundenkontos hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link „Mein Wallet“ oder „Shop-Guthaben“ erscheint im linken Menü des Kundenkonto-Dashboards.
    - *Wenn deaktiviert:* Kunden müssten über einen anderen Link (z. B. vom Header, falls aktiviert) zur Wallet-Seite navigieren.
  - **Empfohlener Wert:** JA (unerlässlich für einfachen Zugriff).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden ihre Wallet-Guthaben einfach finden und verwalten können.
- **Wallet-Link im Footer anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt einen Link zur Seite „Mein Wallet“ im Footer-Bereich Ihres Shops hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link „Mein Wallet“ oder „Shop-Guthaben“ erscheint im Footer, von jeder Seite aus zugänglich.
    - *Wenn deaktiviert:* Kein Wallet-Link im Footer.
  - **Empfohlener Wert:** NEIN (normalerweise redundant, wenn im Header/Konto-Menü, kann aber für maximale Sichtbarkeit JA sein).
  - **Händlerszenario / Beispiel:** Wenn Ihr Kundenkonto-Menü nicht sehr prominent ist oder Sie die Wallet-Funktion breiter hervorheben möchten, könnten Sie dies aktivieren.
- **Wallet-Link in linker/rechter Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt einen Link zur Seite „Mein Wallet“ in einer der Seitenleisten Ihres Shops hinzu (sofern Ihr Theme diese unterstützt).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link „Mein Wallet“ oder „Shop-Guthaben“ erscheint in der gewählten Spalte.
    - *Wenn deaktiviert:* Kein Wallet-Link in den Spalten.
  - **Empfohlener Wert:** NEIN (kann das Layout überladen, normalerweise besser im Header/Konto).
  - **Händlerszenario / Beispiel:** Wenn Sie einen sehr minimalistischen Header/Footer haben und eine Spalte für die Navigation verwenden möchten, könnte dies eine Option sein.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Allgemeine Einstellungen** | Modul aktivieren | JA | Aktiviert/deaktiviert alle Wallet-Funktionen. |
| | Kunden erlauben, Wallet aufzuladen | JA | Kunden können Shop-Guthaben kaufen. |
| | Mindestaufladebetrag | 10,00 | Niedrigster Betrag, den der Kunde hinzufügen kann. |
| | Maximaler Aufladebetrag | 500,00 | Höchster Betrag, den der Kunde hinzufügen kann. |
| | Kunden erlauben, Geschenkcodes zu kaufen | JA | Kunden können Geschenkkarten kaufen. |
| | Geschenkcode-Ablauf (Tage) | 365 | Gültigkeitsdauer für Geschenkcodes (0 für keinen Ablauf). |
| | Wallet-Guthaben-Ablauf (Tage) | 0 | Gültigkeitsdauer für Wallet-Guthaben (0 für keinen Ablauf). |
| | Ablauf-Erinnerungs-E-Mail senden (Tage vor Ablauf) | 7 | Tage vor Ablauf, um eine Erinnerungs-E-Mail zu senden. |
| | Teilzahlungen mit Wallet erlauben | JA | Kunden können Wallet mit anderen Zahlungsmethoden kombinieren. |
| | Option „Rückerstattung an Wallet“ | JA | Option zur Rückerstattung von Bestellungen direkt an das Wallet des Kunden. |
| | Multi-Währungs-Unterstützung aktivieren | JA (wenn Multi-Währungs-Shop) | Verwaltet separate Guthaben für jede Währung. |
| **Auflade-Boni** | Auflade-Boni aktivieren | JA | Aktiviert das Bonussystem für Aufladungen. |
| | Bonusstufen | (Benutzerdefiniert) | Definieren Sie Bonusprozentsätze für verschiedene Aufladebeträge. |
| **Anzeigeoptionen** | Wallet-Guthaben im Header anzeigen | JA | Zeigt das Guthaben im Shop-Header für angemeldete Benutzer an. |
| | Wallet-Link im Kundenkonto-Menü anzeigen | JA | Fügt den Link „Mein Wallet“ zur Kundenkonto-Navigation hinzu. |
| | Wallet-Link im Footer anzeigen | NEIN | Fügt den Link „Mein Wallet“ zum Shop-Footer hinzu. |
| | Wallet-Link in linker/rechter Spalte anzeigen | NEIN | Fügt den Link „Mein Wallet“ zu den Seitenleisten hinzu. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet dedizierte Administrationsbildschirme zur Verwaltung von Kunden-Wallets und Geschenkcodes.

#### 2.2.1 Wallet-Verwaltung (Back Office > Module > Prepaid Wallet & Store Credit > Wallets)

- **Bildschirmname & Menüposition:** **Wallets** (zu finden unter dem Menüpunkt „Prepaid Wallet & Store Credit“, der je nach PrestaShop-Version und Menükonfiguration unter „Module“ oder „Zahlung“ erscheint).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Liste aller Kunden mit einem Wallet, zusammen mit ihrem aktuellen Guthaben, den gesamten Aufladungen und anderen relevanten Informationen.
  - **Kundenliste:** Eine durchsuchbare und filterbare Tabelle, die den Namen, die E-Mail-Adresse, das aktuelle Wallet-Guthaben (pro Währung, wenn Multi-Währung aktiviert ist) und den insgesamt aufgeladenen Betrag jedes Kunden anzeigt.
  - **Wallet anzeigen/bearbeiten:** Klicken Sie auf eine Kundenzeile oder ein „Bearbeiten“-Symbol, um den detaillierten Wallet-Verlauf anzuzeigen und Anpassungen vorzunehmen.
    - **Guthaben hinzufügen/entfernen:** Manuelles Hinzufügen oder Abziehen von Guthaben vom Wallet eines Kunden. Dies ist nützlich für die Ausgabe von Kulanzguthaben, Entschädigungen oder die Korrektur von Fehlern.
    - **Transaktionsverlauf anzeigen:** Sehen Sie ein detailliertes Protokoll aller Wallet-Aktivitäten für diesen Kunden (Aufladungen, Käufe, Rückerstattungen, Boni, Ablauf).
    - **Ablaufdatum festlegen:** Manuelles Festlegen oder Anpassen des Ablaufdatums für bestimmte Guthaben im Wallet eines Kunden.
- **Auswirkung von Änderungen:**
  - *Hinzufügen/Entfernen von Guthaben:* Wirkt sich direkt auf das verfügbare Guthaben des Kunden im Front Office aus.
  - *Bearbeiten von Ablaufdaten:* Beeinflusst, wann Guthaben für den Kunden unbrauchbar wird.
  - *Verlauf anzeigen:* Bietet einen vollständigen Audit-Trail für den Kundenservice und die Buchhaltung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1.  **Kundenanfrage:** Wenn ein Kunde nach seinem Guthaben oder einer bestimmten Transaktion fragt, verwenden Sie diesen Bildschirm, um schnell sein Wallet und seinen Verlauf nachzuschlagen.
  2.  **Guthaben ausgeben:** Wenn Sie einem Kunden ein Shop-Guthaben geben müssen (z. B. für eine Beschwerde, eine Treueprämie), navigieren Sie zu seinem Wallet und verwenden Sie die Option „Guthaben hinzufügen“.
  3.  **Rückerstattungen an Wallet:** Beim Bearbeiten einer Rückerstattung für eine Bestellung können Sie auf der Bestelldetailseite wählen, das Geld an das Wallet des Kunden zu senden. Diese Aktion wird hier widergespiegelt.

#### 2.2.2 Geschenkcode-Verwaltung (Back Office > Module > Prepaid Wallet & Store Credit > Codes)

- **Bildschirmname & Menüposition:** **Codes** (zu finden unter dem Menüpunkt „Prepaid Wallet & Store Credit“).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm ermöglicht es Ihnen, alle Geschenkcodes in Ihrem System zu generieren, zu verwalten und zu verfolgen.
  - **Codeliste:** Eine Tabelle, die alle generierten Geschenkcodes, ihren Wert, den aktuellen Status (aktiv, eingelöst, abgelaufen), wer ihn gekauft hat (falls zutreffend), wer ihn eingelöst hat und das Ablaufdatum anzeigt.
  - **Neuen Code generieren:** Erstellen Sie neue Geschenkcodes mit einem bestimmten Wert, einer Währung und einem optionalen Ablaufdatum. Diese können für Werbeaktionen, Giveaways oder manuelle Kundenservice-Guthaben verwendet werden.
  - **Code bearbeiten:** Ändern Sie den Wert, den Status oder den Ablauf eines bestehenden Codes (sofern noch nicht eingelöst).
  - **Code löschen:** Entfernen Sie einen Code (nur wenn nicht eingelöst).
  - **Suchen/Filtern:** Finden Sie bestimmte Codes einfach nach Wert, Status oder Kunde.
- **Auswirkung von Änderungen:**
  - *Generieren eines Codes:* Erstellt einen neuen, verwendbaren Geschenkcode, der einem Kunden gegeben werden kann.
  - *Bearbeiten eines Codes:* Ändert seine Eigenschaften, was seine Einlösbarkeit und seinen Wert beeinflusst.
  - *Löschen eines Codes:* Verhindert dessen Einlösung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1.  **Werbekampagnen:** Generieren Sie eine Reihe von Geschenkcodes für eine Marketingkampagne (z. B. „10 EUR Rabatt für neue Anmeldungen“).
  2.  **Kundenservice:** Wenn ein Kunde ein Problem hat, können Sie schnell einen einzigartigen Geschenkcode generieren, um ihn zu entschädigen.
  3.  **Nutzungsverfolgung:** Überwachen Sie, welche Codes eingelöst wurden und von wem, um die Effektivität von Kampagnen zu analysieren.

#### 2.2.3 Audit-Log (Back Office > Module > Prepaid Wallet & Store Credit > Audit)

- **Bildschirmname & Menüposition:** **Audit** (zu finden unter dem Menüpunkt „Prepaid Wallet & Store Credit“).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm bietet ein umfassendes Protokoll aller Wallet-bezogenen Aktivitäten in Ihrem Shop.
  - **Aktivitätsliste:** Eine detaillierte Tabelle, die jede Transaktion, Aufladung, Einlösung, Admin-Anpassung und jedes Ablaufereignis anzeigt.
  - **Details:** Jeder Eintrag enthält das Datum, den beteiligten Kunden, die Art der Aktivität, den Betrag und alle relevanten Notizen (z. B. Bestell-ID, Administrator, der die Änderung vorgenommen hat).
  - **Suchen/Filtern:** Filtern Sie das Audit-Log nach Kunde, Datumsbereich oder Aktivitätstyp, um bestimmte Ereignisse schnell zu finden.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschütztes Protokoll; hier können keine Änderungen vorgenommen werden. Es dient als wichtige Aufzeichnung für die Rechenschaftspflicht und Fehlerbehebung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1.  **Fehlerbehebung:** Wenn ein Kunde einen falschen Kontostand meldet, verwenden Sie das Audit-Log, um alle Transaktionen zu verfolgen und Unstimmigkeiten zu identifizieren.
  2.  **Compliance:** Führen Sie eine klare Aufzeichnung aller finanziellen Bewegungen im Zusammenhang mit dem Wallet-System für Buchhaltungs- und rechtliche Zwecke.
  3.  **Leistungsüberprüfung:** Analysieren Sie die gesamte Wallet-Aktivität, um die Kundenbindung und Modulnutzung zu verstehen.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden können die Wallet-Optionen im Front Office nicht sehen.**
A1:

-   **Modulaktivierung prüfen:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Prepaid Wallet & Store Credit“ und stellen Sie sicher, dass das Modul aktiviert ist.
-   **Allgemeine Einstellungen prüfen:** Stellen Sie auf der Konfigurationsseite des Moduls sicher, dass „Modul aktivieren“ auf JA gesetzt ist. Überprüfen Sie auch, ob spezifische Anzeigeoptionen wie „Wallet-Link im Kundenkonto-Menü anzeigen“ aktiviert sind.
-   **Kundenanmeldung:** Wallet-Funktionen sind typischerweise nur für angemeldete Kunden sichtbar. Bitten Sie Ihren Kunden, sich anzumelden.
-   **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können einige stark angepasste Themes geringfügige Anpassungen erfordern. Wenn Sie einen Theme-Konflikt vermuten, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob das Problem behoben wird.

**F2: Das Wallet-Guthaben eines Kunden scheint falsch zu sein.**
A2:

-   **Audit-Log prüfen:** Gehen Sie zu **Module > Prepaid Wallet & Store Credit > Audit**. Suchen Sie nach dem Namen des Kunden und überprüfen Sie seinen gesamten Transaktionsverlauf. Dies zeigt alle Aufladungen, Käufe, Rückerstattungen, Boni und Admin-Anpassungen.
-   **Wallet-Details prüfen:** Gehen Sie zu **Module > Prepaid Wallet & Store Credit > Wallets**, suchen Sie den Kunden und klicken Sie, um sein detailliertes Wallet anzuzeigen. Vergleichen Sie das Guthaben mit dem Audit-Log.
-   **Währungsproblem:** Wenn „Multi-Währungs-Unterstützung aktivieren“ aktiv ist, stellen Sie sicher, dass Sie das Guthaben in der richtigen Währung betrachten. Ein Kunde könnte Guthaben in mehreren Währungen haben.
-   **Ablauf:** Prüfen Sie, ob Guthaben abgelaufen ist. Das Audit-Log zeigt Ablaufereignisse an.

**F3: Meine Kunden erhalten keine Ablauf-Erinnerungs-E-Mails.**
A3:

-   **Ablauf-Einstellungen prüfen:** Stellen Sie sicher, dass „Wallet-Guthaben-Ablauf (Tage)“ auf einen Wert größer als 0 und „Ablauf-Erinnerungs-E-Mail senden (Tage vor Ablauf)“ ebenfalls auf einen Wert größer als 0 gesetzt ist.
-   **Cron-Job:** Das Modul verwendet wahrscheinlich einen Cron-Job, um diese E-Mails auszulösen. Stellen Sie sicher, dass Ihr PrestaShop-Cron-Job korrekt konfiguriert ist und regelmäßig ausgeführt wird. (Siehe Abschnitt 7.2 für `cron.php`).
-   **E-Mail-Konfiguration:** Überprüfen Sie, ob Ihre PrestaShop-E-Mail-Einstellungen (**Erweiterte Einstellungen > E-Mail**) korrekt konfiguriert sind und E-Mails erfolgreich versenden. Testen Sie das Senden einer allgemeinen E-Mail von PrestaShop.
-   **Spam-Ordner:** Weisen Sie Kunden an, ihre Spam- oder Junk-Ordner zu überprüfen.

**F4: Wie leere ich den Smarty-Cache, wenn ich alte Inhalte oder Anzeigeprobleme sehe?**
A4:

-   Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Performance**.
-   Stellen Sie im Abschnitt „Smarty“ die „Template-Kompilierung“ auf „Templates neu kompilieren, wenn die Dateien aktualisiert wurden“ (oder vorübergehend auf „Kompilierung erzwingen“).
-   Klicken Sie oben rechts auf „Cache leeren“.
-   Nach dem Leeren können Sie die „Template-Kompilierung“ für eine bessere Leistung wieder auf „Templates niemals neu kompilieren“ zurücksetzen.

**F5: Das Modul sieht auf meinem benutzerdefinierten Theme nicht richtig aus.**
A5:

-   **CSS-Überschreibungen:** Das CSS Ihres benutzerdefinierten Themes könnte die Standardstile des Moduls überschreiben.
-   **Element untersuchen:** Verwenden Sie die Entwicklertools Ihres Browsers (Rechtsklick, „Untersuchen“), um die CSS-Regeln zu identifizieren, die die Elemente des Moduls beeinflussen. Sie können dann benutzerdefiniertes CSS in das Stylesheet Ihres Themes einfügen, um diese zu überschreiben.
-   **Entwickler kontaktieren:** Wenn Sie mit CSS nicht vertraut sind, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support. Stellen Sie Screenshots und den Namen Ihres Themes bereit.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Prepaid Wallet & Store Credit“, konzipiert für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Prepaid Wallet & Store Credit“ folgt dem Standard-PrestaShop-MVC-Muster (Model-View-Controller). Es erweitert die Kernfunktionalitäten von PrestaShop durch Hooks, benutzerdefinierte Controller und dedizierte Klassen.

-   **Controller:** Verwaltet Front-Office-Interaktionen (Aufladungen, Code-Einlösung, Zahlungsabwicklung) und Back-Office-Administration (Wallet-/Code-Verwaltung).
-   **Modelle:** Benutzerdefinierte `ObjectModel`-Klassen (`PrepaidWalletService`, `PrepaidCodeService` usw.) verwalten die Datenpersistenz für Wallets, Codes und Transaktionen und interagieren mit dedizierten Datenbanktabellen.
-   **Views:** Smarty `.tpl`-Dateien rendern sowohl die Front-Office-Kundenoberflächen (Wallet-Seite, Aufladeformulare) als auch die Back-Office-Administrationsraster/-formulare.
-   **Dienste:** Mehrere Hilfsklassen kapseln spezifische Geschäftslogik (z. B. `PrepaidCartCreditService` für die Checkout-Integration, `PrepaidExpiry` für die Verwaltung des Guthabenablaufs).
-   **Hooks:** Das Modul verwendet PrestaShop-Hooks ausgiebig, um seine Funktionalität in verschiedene Teile des Shops (Header, Kundenkonto, Zahlungsprozess, Bestelldetails) zu integrieren.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `prepaidpayment/controllers/front/applycode.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentApplyCodeModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Behandelt die AJAX-Anfrage zum Anwenden eines Geschenkcodes während des Checkout-Prozesses oder auf der dedizierten Einlöseseite. Es validiert den Code und aktualisiert das Guthaben des Warenkorbs.
-   `prepaidpayment/controllers/front/buycode.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentBuyCodeModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Verwaltet den Prozess des Kaufs von Geschenkcodes durch Kunden. Es behandelt die Anzeige des Formulars zum Kauf von Geschenkcodes und die Erstellung des Geschenkcode-Produkts im Warenkorb.
-   `prepaidpayment/controllers/front/cron.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentCronModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem Cron-Job aufgerufen zu werden. Er führt Hintergrundaufgaben aus, wie z. B. die Überprüfung abgelaufener Wallet-Guthaben, das Senden von Ablauf-Erinnerungs-E-Mails und möglicherweise andere geplante Wartungsarbeiten.
-   `prepaidpayment/controllers/front/entercode.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentEnterCodeModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Zeigt die dedizierte Seite an, auf der Kunden einen Geschenkcode eingeben können, um ihn einzulösen und ihrem Wallet Guthaben hinzuzufügen.
-   `prepaidpayment/controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentIndexModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dient wahrscheinlich als Standard- oder Fallback-Front-Controller oder als Basis für andere Front-Controller. In vielen Modulen könnte dies zu einer allgemeinen Modulseite weiterleiten oder diese anzeigen.
-   `prepaidpayment/controllers/front/payment.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentPaymentModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Behandelt den Zahlungsprozess, wenn ein Kunde sich entscheidet, mit seinem Wallet zu bezahlen. Es validiert das Wallet-Guthaben gegen den Bestellwert und verarbeitet die Zahlung.
-   `prepaidpayment/controllers/front/redeempay.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentRedeemPayModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller verwaltet wahrscheinlich die Einlösung eines Geschenkcodes und dessen Anwendung auf den aktuellen Warenkorb, möglicherweise durch Kombination der Logik von `applycode.php` und `payment.php` in einem spezifischen Ablauf.
-   `prepaidpayment/controllers/front/topup.php`
    *   **Klassenname & Elternklasse:** `PrepaidPaymentTopupModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Verwaltet den Aufladeprozess des Kunden-Wallets. Es zeigt das Aufladeformular an, behandelt die Auswahl der Aufladebeträge (und der damit verbundenen Boni) und fügt das Aufladeprodukt dem Warenkorb hinzu.

#### Back-Office-Admin-Controller

-   `prepaidpayment/controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** `AdminPrepaidPaymentController` erweitert `ModuleAdminController`.
    *   **Tab-Name und verwaltete Entität:** Dieser Controller dient als Haupteinstiegspunkt für die Administrationsschnittstelle des Moduls. Er leitet wahrscheinlich zu verschiedenen Ansichten (Wallets, Codes, Audit) weiter und verwaltet die Gesamtkonfiguration und Daten für das Modul. Er verwaltet kein einzelnes `ObjectModel` direkt, sondern orchestriert die Verwaltung von `PrepaidWalletService`- und `PrepaidCodeService`-Daten.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `prepaidpayment/classes/index.php`
    *   **Zweck:** Typischerweise eine leere Datei oder enthält eine einfache `die()`-Anweisung, um die direkte Verzeichnisauflistung zu verhindern, eine gängige Sicherheitspraxis.
-   `prepaidpayment/classes/PrepaidAdmin.php`
    *   **Zweck:** Wahrscheinlich eine Hilfsklasse für administrative Aufgaben, die möglicherweise Methoden zum Rendern von Admin-Formularen, zur Verarbeitung von AJAX-Anfragen innerhalb des Back Office oder spezifische Datenmanipulationen für Admin-Ansichten enthält.
-   `prepaidpayment/classes/PrepaidCartCreditService.php`
    *   **Zweck:** Kapselt die Logik zum Anwenden von Wallet-Guthaben oder Geschenkcodes auf den Warenkorb eines Kunden während des Checkouts. Es behandelt Berechnungen, Validierungen und Aktualisierungen des Warenkorb-Gesamtbetrags.
-   `prepaidpayment/classes/PrepaidCodeService.php`
    *   **Zweck:** Verwaltet den Lebenszyklus von Geschenkcodes.
    *   **ObjectModel-Interaktion:** Erweitert wahrscheinlich `ObjectModel` und interagiert mit einer benutzerdefinierten Datenbanktabelle (z. B. `ps_prepaid_codes`).
    *   **`$definition`-Felder:** Würden Felder wie `id_prepaid_code`, `code`, `value`, `id_currency`, `id_customer_buyer`, `id_customer_redeemer`, `date_add`, `date_redeem`, `date_expiry`, `active` enthalten.
    *   **Wichtige öffentliche Methoden:** `generateCode()`, `redeemCode()`, `getCodeByCode()`, `isCodeValid()`, `getCodesForCustomer()`.
-   `prepaidpayment/classes/PrepaidCurrency.php`
    *   **Zweck:** Eine Hilfsklasse zur Handhabung von Multi-Währungs-Aspekten des Wallets, die korrekte Währungsumrechnungen und -anzeigen gewährleistet. Sie könnte `Currency` erweitern oder Dienstprogramm-Methoden für währungsbezogene Operationen bereitstellen.
-   `prepaidpayment/classes/PrepaidExpiry.php`
    *   **Zweck:** Verwaltet die Ablauflogik für Geschenkcodes und Wallet-Guthaben. Es enthält Methoden zur Berechnung von Ablaufdaten, zur Überprüfung abgelaufener Guthaben und zur potenziellen Auslösung von Ablaufaktionen (z. B. das Inaktivsetzen von Guthaben).
-   `prepaidpayment/classes/PrepaidThemeCompat.php`
    *   **Zweck:** Bietet Kompatibilitätsschichten oder spezifische Anpassungen für verschiedene PrestaShop-Themes (z. B. Classic, Hummingbird) oder Versionen, um sicherzustellen, dass die Front-Office-Elemente des Moduls in verschiedenen Umgebungen korrekt angezeigt werden.
-   `prepaidpayment/classes/PrepaidTopupCart.php`
    *   **Zweck:** Verwaltet die spezifische Warenkorb-Logik, wenn ein Kunde sein Wallet auflädt. Es könnte ein virtuelles Produkt im Warenkorb erstellen, das den Aufladebetrag darstellt, und die damit verbundenen Boni behandeln.
-   `prepaidpayment/classes/PrepaidWalletService.php`
    *   **Zweck:** Die Kernklasse zur Verwaltung von Kunden-Wallets.
    *   **ObjectModel-Interaktion:** Erweitert wahrscheinlich `ObjectModel` und interagiert mit einer benutzerdefinierten Datenbanktabelle (z. B. `ps_prepaid_wallets` für Guthaben und `ps_prepaid_wallet_history` für Transaktionen).
    *   **`$definition`-Felder:** Für `ps_prepaid_wallets`: `id_prepaid_wallet`, `id_customer`, `id_currency`, `balance`, `date_update`. Für `ps_prepaid_wallet_history`: `id_prepaid_wallet_history`, `id_customer`, `id_currency`, `amount`, `type` (topup, purchase, refund, bonus, expiry), `id_order`, `date_add`, `notes`.
    *   **Wichtige öffentliche Methoden:** `getBalance()`, `addFunds()`, `deductFunds()`, `getHistory()`, `getWalletsForCustomer()`, `processRefundToWallet()`.

### 4.4 JavaScript-Assets (`views/js/`)

-   `prepaidpayment/lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Wahrscheinlich Back-Office.
    *   **Details:** Bietet Autocomplete-Funktionalität, wahrscheinlich zum Suchen von Kunden oder Produkten innerhalb der Admin-Oberfläche, zum Beispiel beim Zuweisen eines Geschenkcodes zu einem bestimmten Kunden oder beim Verwalten eines Wallets.
-   `prepaidpayment/views/js/adminPrepaid.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Allgemeines JavaScript für die Admin-Seiten des Moduls. Es könnte Formularübermittlungen, AJAX-Updates für Listen (Wallets, Codes), allgemeine UI-Verbesserungen und Interaktionen auf der Hauptkonfigurationsseite behandeln.
-   `prepaidpayment/views/js/adminPrepaidBonusBuilder.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Behandelt speziell die dynamische Erstellung und Verwaltung von Bonusstufen auf der Konfigurationsseite des Moduls. Es fügt wahrscheinlich Eingabefelder für Bonusprozentsätze und Mindestbeträge hinzu/entfernt diese und validiert diese Eingaben.
-   `prepaidpayment/views/js/adminPrepaidDashboard.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** JavaScript für das Admin-Dashboard oder die Übersichtsseite, das möglicherweise Datenvisualisierung, schnelle Statistiken oder interaktive Elemente im Zusammenhang mit der gesamten Wallet-Nutzung behandelt.
-   `prepaidpayment/views/js/adminPrepaidSelector.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Verwaltet Auswahlkomponenten im Admin, möglicherweise zur Auswahl von Kunden, Währungen oder spezifischen Codes innerhalb verschiedener Formulare oder Listen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `prepaidpayment/lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Back-Office-Admin-Styling.
    *   **Details:** Stile für das Autocomplete-Suchwerkzeug, das im Back Office verwendet wird, um sicherzustellen, dass Dropdowns und Vorschläge visuell konsistent sind.
-   `prepaidpayment/views/css/admin_prepaidpayment.css`
    *   **Geltungsbereich:** Back-Office-Admin-Styling.
    *   **Details:** Kern-CSS für die Administrationsseiten des Moduls, Styling von Formularen, Tabellen, Schaltflächen und dem gesamten Layout innerhalb des PrestaShop Back Office.
-   `prepaidpayment/views/css/front-hummingbird.css`
    *   **Geltungsbereich:** Front-Office-Kunden-Styling (speziell für das Hummingbird-Theme).
    *   **Details:** Bietet spezifische Styling-Anpassungen oder Überschreibungen, um eine optimale visuelle Integration mit dem PrestaShop Hummingbird-Theme zu gewährleisten.
-   `prepaidpayment/views/css/front.css`
    *   **Geltungsbereich:** Front-Office-Kunden-Styling (allgemein).
    *   **Details:** Allgemeines CSS für die Front-Office-Komponenten des Moduls, wie die Seite „Mein Wallet“, Aufladeformulare, Geschenkcode-Einlöseformulare und die Wallet-Anzeige im Header/Checkout.
-   `prepaidpayment/views/css/prepaidpayment.css`
    *   **Geltungsbereich:** Sowohl Front-Office als auch Back-Office (oder allgemeine modulweite Stile).
    *   **Details:** Enthält gemeinsame Stile, die sowohl im Front- als auch im Back-Office verwendet werden, oder grundlegende Stile für die einzigartigen Elemente des Moduls.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `prepaidpayment/views/templates/hook/adminOrder.tpl`
    *   **Hook:** `displayAdminOrder` oder ähnlich.
    *   **Ausgabe:** Zeigt Wallet-bezogene Informationen oder Aktionen auf der PrestaShop-Bestelldetailseite im Back Office an (z. B. Option zur Rückerstattung an Wallet, Wallet-Zahlungsdetails).
-   `prepaidpayment/views/templates/hook/customerAccount-hummingbird.tpl`
    *   **Hook:** `displayCustomerAccount` (speziell für das Hummingbird-Theme).
    *   **Ausgabe:** Fügt einen „Mein Wallet“-Link oder -Block zum Kundenkonto-Dashboard hinzu, im Stil des Hummingbird-Themes.
-   `prepaidpayment/views/templates/hook/customerAccount.tpl`
    *   **Hook:** `displayCustomerAccount`.
    *   **Ausgabe:** Fügt einen „Mein Wallet“-Link oder -Block zum Kundenkonto-Dashboard für allgemeine Themes hinzu.
-   `prepaidpayment/views/templates/hook/orderDetail.tpl`
    *   **Hook:** `displayOrderDetail` oder ähnlich.
    *   **Ausgabe:** Zeigt Wallet-Zahlungsdetails auf der Bestelldetailseite des Kunden im Front Office an.
-   `prepaidpayment/views/templates/hook/payment.tpl`
    *   **Hook:** `displayPayment` (PrestaShop 1.6) oder `paymentOptions` (PrestaShop 1.7+).
    *   **Ausgabe:** Rendert die Option „Mit Wallet bezahlen“ auf der Checkout-Zahlungsauswahlseite.
-   `prepaidpayment/views/templates/hook/paymentReturn.tpl`
    *   **Hook:** `displayPaymentReturn`.
    *   **Ausgabe:** Zeigt Informationen zu Wallet-Zahlungen auf der Bestellbestätigungsseite nach dem Checkout an.
-   `prepaidpayment/views/templates/hook/paymentTop.tpl`
    *   **Hook:** `displayPaymentTop`.
    *   **Ausgabe:** Kann eine Zusammenfassung des Wallet-Guthabens oder eine Option zur Eingabe eines Geschenkcodes oben auf der Zahlungsseite anzeigen.
-   `prepaidpayment/views/templates/hook/walletNav.tpl`
    *   **Hook:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`.
    *   **Ausgabe:** Rendert das Wallet-Guthaben oder einen Link zur Wallet-Seite in verschiedenen Navigationsbereichen des Shops.

#### Admin-Templates (`views/templates/admin/`)

-   `prepaidpayment/views/templates/admin/audit.tpl`
    *   **Ausgabe:** Rendert die Audit-Log-Tabelle und Filteroptionen im Back Office.
-   `prepaidpayment/views/templates/admin/codes.tpl`
    *   **Ausgabe:** Rendert die Liste der Geschenkcodes, das Formular zum Generieren neuer Codes und zum Bearbeiten bestehender Codes im Back Office.
-   `prepaidpayment/views/templates/admin/dashboard.tpl`
    *   **Ausgabe:** Rendert das Haupt-Dashboard oder die Übersichtsseite für das Modul im Back Office, möglicherweise mit Statistiken oder Schnelllinks.
-   `prepaidpayment/views/templates/admin/scopeSelector.tpl`
    *   **Ausgabe:** Ein wiederverwendbares Template zur Auswahl spezifischer Bereiche, wie Währungen oder Kundengruppen, innerhalb von Admin-Formularen.
-   `prepaidpayment/views/templates/admin/wallets.tpl`
    *   **Ausgabe:** Rendert die Liste der Kunden-Wallets, die detaillierte Wallet-Ansicht und Optionen zum Hinzufügen/Entfernen von Guthaben im Back Office.

#### Front-Office-Templates (`views/templates/front/`)

-   `prepaidpayment/views/templates/front/buycode.tpl`
    *   **Ausgabe:** Rendert das Formular und die Oberfläche für Kunden zum Kauf von Geschenkcodes.
-   `prepaidpayment/views/templates/front/entercode.tpl`
    *   **Ausgabe:** Rendert die dedizierte Seite, auf der Kunden einen Geschenkcode eingeben können, um ihn einzulösen.
-   `prepaidpayment/views/templates/front/topup.tpl`
    *   **Ausgabe:** Rendert das Formular und die Optionen für Kunden zum Aufladen ihres Wallets, einschließlich Bonusinformationen.

#### Bibliotheks-Templates (`prepaidpayment/lib/searchTool/views/scripts.tpl`)

-   `prepaidpayment/lib/searchTool/views/scripts.tpl`
    *   **Ausgabe:** Enthält JavaScript- oder Smarty-Logik für das Suchwerkzeug, wahrscheinlich in Admin-Templates enthalten, wo Autocomplete benötigt wird.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

-   `ps_prepaid_wallets`: Speichert das aktuelle Guthaben für jeden Kunden und jede Währung.
    *   `id_prepaid_wallet` (PK)
    *   `id_customer` (FK zu `ps_customer`)
    *   `id_currency` (FK zu `ps_currency`)
    *   `balance` (Dezimal)
    *   `date_upd` (Datum/Uhrzeit)
-   `ps_prepaid_wallet_history`: Protokolliert alle Transaktionen und Änderungen an Kunden-Wallets.
    *   `id_prepaid_wallet_history` (PK)
    *   `id_customer` (FK zu `ps_customer`)
    *   `id_currency` (FK zu `ps_currency`)
    *   `amount` (Dezimal, positiv für Gutschrift, negativ für Lastschrift)
    *   `type` (Varchar, z. B. „topup“, „purchase“, „refund“, „bonus“, „expiry“, „admin_add“, „admin_deduct“)
    *   `id_order` (FK zu `ps_order`, nullable)
    *   `id_prepaid_code` (FK zu `ps_prepaid_codes`, nullable)
    *   `notes` (Text, z. B. „Admin-Anpassung“, „Geschenkcode-Einlösung“)
    *   `date_add` (Datum/Uhrzeit)
    *   `date_expiry` (Datum/Uhrzeit, nullable)
-   `ps_prepaid_codes`: Speichert Informationen über generierte und gekaufte Geschenkcodes.
    *   `id_prepaid_code` (PK)
    *   `code` (Varchar, eindeutig, der eigentliche Geschenkcode-String)
    *   `value` (Dezimal, Anfangswert des Codes)
    *   `id_currency` (FK zu `ps_currency`)
    *   `id_customer_buyer` (FK zu `ps_customer`, nullable, wenn vom Kunden gekauft)
    *   `id_customer_redeemer` (FK zu `ps_customer`, nullable, sobald eingelöst)
    *   `date_add` (Datum/Uhrzeit)
    *   `date_redeem` (Datum/Uhrzeit, nullable)
    *   `date_expiry` (Datum/Uhrzeit, nullable)
    *   `active` (Tinyint, 0 oder 1)
-   `ps_prepaid_bonus_tiers`: Speichert die konfigurierten Auflade-Bonusregeln.
    *   `id_prepaid_bonus_tier` (PK)
    *   `min_amount` (Dezimal)
    *   `bonus_percentage` (Dezimal)
    *   `position` (Int)
-   `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `PREPAIDPAYMENT_ENABLED`, `PREPAIDPAYMENT_MIN_TOPUP` usw. gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS injizieren, Wallet-Guthaben für angemeldete Benutzer anzeigen. |
| `displayLeftColumn` | In der linken Spalte des Shops. | Wallet-Link anzeigen. |
| `displayRightColumn` | In der rechten Spalte des Shops. | Wallet-Link anzeigen. |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Wallet-Link anzeigen. |
| `displayCustomerAccount` | Auf der „Mein Konto“-Seite des Kunden. | „Mein Wallet“-Link/Block hinzufügen. |
| `displayPayment` (PS 1.6) / `paymentOptions` (PS 1.7+) | Auf der Checkout-Zahlungsauswahlseite. | „Mit Wallet bezahlen“-Zahlungsoption anzeigen. |
| `displayPaymentReturn` | Auf der Bestellbestätigungsseite nach dem Checkout. | Wallet-Zahlungsdetails anzeigen. |
| `displayPaymentTop` | Oben auf der Zahlungsseite. | Potenziell Wallet-Guthaben oder Geschenkcode-Eingabe anzeigen. |
| `displayAdminOrder` | Auf der Bestelldetailseite im Back Office. | Option zur Rückerstattung an Wallet hinzufügen, Wallet-Zahlungsinformationen anzeigen. |
| `displayOrderDetail` | Auf der Bestelldetailseite des Kunden im Front Office. | Wallet-Zahlungsdetails anzeigen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Guthaben vom Wallet abziehen, Transaktion aufzeichnen. |
| `actionOrderStatusPostUpdate` | Nachdem der Status einer Bestellung aktualisiert wurde. | Potenziell Rückerstattungen an Wallet basierend auf Statusänderung auslösen. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seinen Inhalt rendert. | Modulspezifisches CSS und JS zu Front-Office-Seiten hinzufügen. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seinen Inhalt rendert. | Modulspezifisches CSS und JS zu Back-Office-Seiten hinzufügen. |
| `actionCronJob` (benutzerdefinierter Hook) | Wird vom Cron-Controller des Moduls ausgelöst. | Geplante Aufgaben wie Ablaufprüfungen und E-Mail-Erinnerungen ausführen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Prepaid Wallet & Store Credit“ wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, umfassenden Support zu bieten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.

-   **MyPresta.eu Bestellverlauf & Downloads:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Support-Kontakt:** <https://mypresta.eu/contact>
