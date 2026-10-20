---
title: "Zahlungsrabatt oder -gebühr – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Zahlungsrabatt oder -gebühr“ von MyPresta.eu."
sidebar:
  label: "Zahlungsrabatt oder -gebühr – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Payment Discount or Fee auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/payment-discount-or-fee.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/payment-discount-or-fee/)
>
> ---


# Zahlungsrabatt oder -gebühr

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Webhosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Zahlungsrabatt oder -gebühr“ bietet eine umfassende Reihe von Optionen, um genau zu steuern, wie Rabatte oder Gebühren angewendet werden.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Zahlungsrabatt oder -gebühr)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten des Moduls aktivieren und einrichten.

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Funktionalität des Moduls in Ihrem gesamten Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, Rabatte oder Gebühren basierend auf Ihren definierten Regeln während des Checkouts anzuwenden.
    - *Wenn deaktiviert:* Das Modul stellt alle Operationen ein, und es werden keine Rabatte oder Gebühren angewendet.
  - **Empfohlener Wert:** JA (sobald Sie Ihre Regeln konfiguriert haben).
  - **Händlerszenario / Beispiel:** Sie haben alle Ihre Regeln eingerichtet und sind bereit, live zu gehen. Aktivieren Sie dies, um das Modul zu aktivieren. Wenn Sie es vorübergehend für Wartungsarbeiten deaktivieren müssen, stellen Sie es auf NEIN.
- **Gebühr/Rabatt in der Warenkorb-Zusammenfassung anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob die Anpassung der Zahlungsmethode als separate Position in der Warenkorb-Zusammenfassung angezeigt wird, *bevor* der Kunde den Zahlungsschritt erreicht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen eine Position wie „Anpassung der Zahlungsmethode“ in ihrer Warenkorb-Zusammenfassung, noch bevor sie eine Zahlungsmethode auswählen, was darauf hinweist, dass sich der Endpreis ändern könnte.
    - *Wenn deaktiviert:* Die Anpassung erscheint erst, wenn der Kunde eine Zahlungsmethode auf der Checkout-Seite auswählt.
  - **Empfohlener Wert:** JA (für Transparenz).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden so früh wie möglich über potenzielle Zahlungsanpassungen vollständig informiert sind. Die Aktivierung bietet maximale Transparenz.
- **Gebühr/Rabatt auf Versandkosten anwenden:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der berechnete Rabatt oder die Gebühr auch auf die Versandkosten der Bestellung oder nur auf die Produktsumme angewendet werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn Sie eine Gebühr von 2 % haben und die Produktsumme 100 $ und der Versand 10 $ beträgt, beträgt die Gebühr 2 % von 110 $ (2,20 $).
    - *Wenn deaktiviert:* Die Gebühr von 2 % würde nur auf die Produktsumme von 100 $ (2,00 $) angewendet, und der Versand bliebe separat.
  - **Empfohlener Wert:** JA (wenn Ihre Zahlungs-Gateway-Gebühren auch für den gesamten Bestellwert einschließlich Versand gelten).
  - **Händlerszenario / Beispiel:** Die meisten Zahlungs-Gateways berechnen eine prozentuale Gebühr auf den *gesamten* Transaktionsbetrag, einschließlich Versand. Die Aktivierung stellt sicher, dass Ihre Gebühr Ihre Kosten genau widerspiegelt.
- **Gebühr/Rabatt auf Steuern anwenden:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der berechnete Rabatt oder die Gebühr auch auf den Steuerbetrag der Bestellung oder nur auf die Produktsumme (und möglicherweise den Versand) angewendet werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn Sie eine Gebühr von 2 % haben und die Produktsumme 100 $, der Versand 10 $ und die Steuer 20 $ beträgt, beträgt die Gebühr 2 % von 130 $ (2,60 $).
    - *Wenn deaktiviert:* Die Gebühr von 2 % würde nur auf die Produktsumme (und den Versand, falls aktiviert) angewendet, und die Steuer bliebe separat.
  - **Empfohlener Wert:** JA (wenn Ihre Zahlungs-Gateway-Gebühren auch für den gesamten Bestellwert einschließlich Steuern gelten).
  - **Händlerszenario / Beispiel:** Ähnlich wie beim Versand berechnen Zahlungs-Gateways typischerweise auf den Gesamtbetrag. Die Aktivierung stellt sicher, dass Ihre Gebührenberechnung umfassend ist.
- **Gebühren-/Rabattbezeichnung im Warenkorb/Bestellung:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Textbezeichnung anzupassen, die neben dem Rabatt- oder Gebührenbetrag in der Warenkorb-Zusammenfassung und den Bestelldetails angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Zahlungsmethoden-Aufschlag“ eingestellt:* Dieser Text wird angezeigt.
    - *Wenn auf „Zahlungsrabatt“ eingestellt:* Dieser Text wird angezeigt.
  - **Empfohlener Wert:** „Anpassung der Zahlungsmethode“ oder „Zahlungsaufschlag“ / „Zahlungsrabatt“, je nach Ihrer primären Verwendung.
  - **Händlerszenario / Beispiel:** Sie verwenden das Modul hauptsächlich, um Gebühren hinzuzufügen. Wenn Sie die Bezeichnung auf „Zahlungsaufschlag“ setzen, ist dies für Kunden klar. Wenn Sie Rabatte anbieten, ist „Zahlungsrabatt“ passender.
- **Cron-Job-URL für die Bereinigung des Audit-Logs:**

  - **Was diese Einstellung bewirkt:** Bietet eine URL, die Sie als Cron-Job auf Ihrem Server einrichten können, um alte Einträge aus dem Audit-Log des Moduls automatisch zu bereinigen und so zu verhindern, dass die Datenbank zu groß wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn als Cron-Job konfiguriert:* Das Audit-Log wird regelmäßig von alten Einträgen bereinigt, was die Datenbankleistung verbessert.
    - *Wenn nicht konfiguriert:* Das Audit-Log wächst unbegrenzt, was Ihr Back Office im Laufe der Zeit potenziell verlangsamen kann.
  - **Empfohlener Wert:** Richten Sie einen Cron-Job ein, der diese URL täglich oder wöchentlich ausführt.
  - **Händlerszenario / Beispiel:** Sie möchten Ihre Datenbank schlank und schnell halten. Kopieren Sie diese URL und fügen Sie sie dem Cron-Job-Scheduler Ihres Hosting-Kontrollpanels hinzu.

### 2.2 Dedizierter Admin-Bildschirm: Zahlungsrabatt- oder Gebührenregeln (Back Office > Zahlung > Zahlungsrabatt- oder Gebührenregeln)

Auf diesem Bildschirm definieren und verwalten Sie alle Regeln für die Anwendung von Rabatten oder Gebühren.

- **Bildschirmname & Menüpfad:** **Zahlungsrabatt- oder Gebührenregeln** (zu finden unter **Zahlung** im Hauptmenü des PrestaShop Back Office).
- **Verfügbare Aktionen & Einstellungen:**

  - **Regel-Auflistungstabelle:** Zeigt alle Ihre aktuell aktiven und inaktiven Regeln an, einschließlich Name, Zahlungsmethode, Typ (Rabatt/Gebühr), Wert und Status.
  - **Schaltfläche „Neue Regel hinzufügen“:** Klicken Sie hier, um eine neue Rabatt- oder Gebührenregel zu erstellen.
  - **Bearbeiten/Löschen-Aktionen:** Für jede Regel in der Liste können Sie klicken, um deren Details zu bearbeiten oder sie zu löschen.
  - **Formularfelder zum Hinzufügen/Bearbeiten einer Regel:**
    - **Regelname:**
      - **Was diese Einstellung bewirkt:** Ein beschreibender Name für Ihre Regel, nur im Back Office sichtbar.
      - **Auswirkung der Änderung dieser Einstellung:** Hilft Ihnen, Ihre Regeln einfach zu identifizieren und zu verwalten.
      - **Empfohlener Wert:** Klar und beschreibend (z. B. „PayPal 2% Gebühr“, „Banküberweisung 5% Rabatt“).
    - **Zahlungsmethode:**
      - **Was diese Einstellung bewirkt:** Wählt aus, für welches spezifische Zahlungs-Gateway oder welche Methode diese Regel gilt.
      - **Auswirkung der Änderung dieser Einstellung:** Die Regel wird nur aktiviert, wenn ein Kunde diese Zahlungsmethode wählt.
      - **Empfohlener Wert:** Wählen Sie die genaue Zahlungsmethode, die Sie ansprechen möchten.
      - **Händlerszenario / Beispiel:** Sie möchten eine Gebühr für „PayPal“ hinzufügen, also wählen Sie „PayPal“ aus dem Dropdown-Menü.
    - **Typ:**
      - **Was diese Einstellung bewirkt:** Bestimmt, ob die Regel einen „Rabatt“ oder eine „Gebühr“ anwendet.
      - **Auswirkung der Änderung dieser Einstellung:**
        - *Rabatt:* Reduziert die Bestellsumme.
        - *Gebühr:* Erhöht die Bestellsumme.
      - **Empfohlener Wert:** Wählen Sie basierend auf Ihrem Ziel (z. B. „Gebühr“ für Kreditkartenbearbeitungskosten).
    - **Wert:**
      - **Was diese Einstellung bewirkt:** Der Betrag oder Prozentsatz des Rabatts/der Gebühr.
      - **Auswirkung der Änderung dieser Einstellung:**
        - *Wenn „Typ“ „Prozentsatz“ ist:* Geben Sie „2“ für 2 % ein.
        - *Wenn „Typ“ „Fester Betrag“ ist:* Geben Sie „5.00“ für 5,00 $ ein.
      - **Empfohlener Wert:** Der genaue Prozentsatz oder feste Betrag, den Sie anwenden möchten.
    - **Werttyp:**
      - **Was diese Einstellung bewirkt:** Wählen Sie, ob der „Wert“ ein „Prozentsatz“ des Bestellwerts oder ein „Fester Betrag“ ist.
      - **Auswirkung der Änderung dieser Einstellung:** Bestimmt, wie das Feld „Wert“ interpretiert wird.
      - **Empfohlener Wert:** Prozentsatz ist üblich für Gebühren; fester Betrag für spezifische Rabatte.
    - **Mindestwarenkorbwert (Optional):**
      - **Was diese Einstellung bewirkt:** Der Mindestbestellwert (vor dem Rabatt/der Gebühr), der für die Anwendung dieser Regel erforderlich ist.
      - **Auswirkung der Änderung dieser Einstellung:** Wenn der Warenkorbwert unter diesem Betrag liegt, wird die Regel nicht angewendet.
      - **Empfohlener Wert:** Leer lassen, wenn kein Minimum erforderlich ist.
      - **Händlerszenario / Beispiel:** Sie möchten eine Gebühr nur für größere Bestellungen anwenden, um Mikrogebühren bei kleinen Einkäufen zu vermeiden.
    - **Maximaler Warenkorbwert (Optional):**
      - **Was diese Einstellung bewirkt:** Der maximale Bestellwert (vor dem Rabatt/der Gebühr), für den diese Regel gilt.
      - **Auswirkung der Änderung dieser Einstellung:** Wenn der Warenkorbwert über diesem Betrag liegt, wird die Regel nicht angewendet.
      - **Empfohlener Wert:** Leer lassen, wenn kein Maximum erforderlich ist.
    - **Kundengruppen (Optional):**
      - **Was diese Einstellung bewirkt:** Beschränkt die Regel auf bestimmte Kundengruppen (z. B. „Großhändler“, „Gäste“).
      - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die zu den ausgewählten Gruppen gehören, werden von dieser Regel betroffen sein.
      - **Empfohlener Wert:** Wählen Sie „Alle Kundengruppen“, es sei denn, Sie haben spezifische gruppenbasierte Preisstrategien.
      - **Händlerszenario / Beispiel:** Sie möchten Ihren „VIP-Kunden“ einen speziellen Rabatt anbieten, wenn sie per Banküberweisung bezahlen.
    - **Länder (Optional):**
      - **Was diese Einstellung bewirkt:** Beschränkt die Regel auf Kunden aus bestimmten Ländern.
      - **Auswirkung der Änderung dieser Einstellung:** Die Regel wird nur angewendet, wenn die Lieferadresse des Kunden in einem der ausgewählten Länder liegt.
      - **Empfohlener Wert:** Wählen Sie „Alle Länder“, es sei denn, Sie haben länderspezifische Zahlungsstrategien.
      - **Händlerszenario / Beispiel:** Sie haben höhere Bearbeitungsgebühren für internationale Kreditkartenzahlungen aus bestimmten Regionen.
    - **Auszuschließende Produkte (Optional):**
      - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einzelne Produkte anzugeben, die *nicht* in die Berechnung des Rabatts oder der Gebühr einbezogen werden sollen.
      - **Auswirkung der Änderung dieser Einstellung:** Der Wert dieser Produkte wird vom Warenkorbwert *vor* der Berechnung des Prozentsatzes oder des festen Betrags abgezogen.
      - **Empfohlener Wert:** Leer lassen, es sei denn, bestimmte Produkte sollen ausgenommen werden.
      - **Händlerszenario / Beispiel:** Sie verkaufen einige Produkte mit geringer Marge, bei denen die Anwendung einer Gebühr sie unrentabel machen würde, daher schließen Sie sie aus.
    - **Status (Aktivieren/Deaktivieren):**
      - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert eine einzelne Regel, ohne sie zu löschen.
      - **Auswirkung der Änderung dieser Einstellung:**
        - *Aktiviert:* Die Regel ist aktiv und wird angewendet.
        - *Deaktiviert:* Die Regel ist inaktiv und wird nicht angewendet.
      - **Empfohlener Wert:** Aktiviert für aktive Regeln.
      - **Händlerszenario / Beispiel:** Sie möchten eine Regel für eine Aktion vorübergehend pausieren, ohne ihre Konfiguration zu verlieren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. Beginnen Sie damit, zu identifizieren, welche Zahlungsmethoden Kosten verursachen oder Vorteile bieten, die Sie weitergeben möchten.
  2. Klicken Sie auf „Neue Regel hinzufügen“.
  3. Geben Sie der Regel einen klaren Namen.
  4. Wählen Sie die Ziel-Zahlungsmethode aus.
  5. Wählen Sie „Gebühr“ oder „Rabatt“ und geben Sie den Wert ein (Prozentsatz oder fester Betrag).
  6. Verfeinern Sie die Regel bei Bedarf mit Mindest-/Maximal-Warenkorbwerten, Kundengruppen, Ländern oder Produktausschlüssen.
  7. Aktivieren Sie die Regel und speichern Sie.
  8. Testen Sie die Regel in Ihrem Front Office, indem Sie eine Testbestellung aufgeben.

### 2.3 Dedizierter Admin-Bildschirm: Zahlungsrabatt- oder Gebühren-Audit-Log (Back Office > Zahlung > Zahlungsrabatt- oder Gebühren-Audit-Log)

Dieser Bildschirm bietet eine historische Aufzeichnung aller Fälle, in denen das Modul einen Rabatt oder eine Gebühr angewendet hat.

- **Bildschirmname & Menüpfad:** **Zahlungsrabatt- oder Gebühren-Audit-Log** (zu finden unter **Zahlung** im Hauptmenü des PrestaShop Back Office).
- **Verfügbare Aktionen & Einstellungen:**
  - **Log-Auflistungstabelle:** Zeigt Einträge mit Details wie:
    - **Bestell-ID:** Die ID der Bestellung, bei der die Anpassung angewendet wurde.
    - **Kundenname:** Der Kunde, der die Bestellung aufgegeben hat.
    - **Zahlungsmethode:** Die gewählte Zahlungsmethode.
    - **Angewandte Regel:** Der Name der Regel, die die Anpassung ausgelöst hat.
    - **Anpassungstyp:** Ob es sich um einen Rabatt oder eine Gebühr handelte.
    - **Anpassungswert:** Der Betrag des Rabatts oder der Gebühr.
    - **Datum:** Wann die Anpassung angewendet wurde.
  - **Filtern und Suchen:** Sie können das Protokoll nach Bestell-ID, Kunde, Zahlungsmethode oder Datum filtern, um schnell bestimmte Einträge zu finden.
  - **Auswirkung von Änderungen:** Dieser Bildschirm dient nur zur Ansicht; Sie können Log-Einträge hier nicht direkt ändern. Er dient als wertvolle Aufzeichnung zur Fehlerbehebung und Analyse.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Überprüfen Sie regelmäßig das Audit-Log, um sicherzustellen, dass die Regeln korrekt angewendet werden.
  - Verwenden Sie es zur Fehlerbehebung bei Kundenanfragen zu Preisabweichungen.
  - Überwachen Sie das Volumen der Anpassungen, um die Auswirkungen Ihrer Regeln zu verstehen.

### 2.4 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
|  | Gebühr/Rabatt in der Warenkorb-Zusammenfassung anzeigen | JA | Zeigt die Anpassung frühzeitig im Warenkorb zur Transparenz an. |
|  | Gebühr/Rabatt auf Versandkosten anwenden | JA | Bezieht den Versand in die Gebühren-/Rabattberechnung ein. |
|  | Gebühr/Rabatt auf Steuern anwenden | JA | Bezieht die Steuern in die Gebühren-/Rabattberechnung ein. |
|  | Gebühren-/Rabattbezeichnung im Warenkorb/Bestellung | „Anpassung der Zahlungsmethode“ | Passt die dem Kunden angezeigte Bezeichnung an. |
|  | Cron-Job-URL für die Bereinigung des Audit-Logs | (URL bereitgestellt) | Automatisiert die Bereinigung alter Audit-Log-Einträge. |
| **Zahlungsrabatt- oder Gebührenregeln** | Regelname | (Beschreibender Name) | Interner Name für die Regel. |
|  | Zahlungsmethode | (Spezifische Methode) | Wählt die Zahlungsmethode für die Regel aus. |
|  | Typ | Gebühr / Rabatt | Bestimmt, ob es sich um eine Erhöhung oder Verringerung handelt. |
|  | Wert | (Numerischer Wert) | Der Betrag oder Prozentsatz der Anpassung. |
|  | Werttyp | Prozentsatz / Fester Betrag | Wie der „Wert“ interpretiert wird. |
|  | Mindestwarenkorbwert | (Leer) | Mindestbestellwert, damit die Regel angewendet wird. |
|  | Maximaler Warenkorbwert | (Leer) | Maximaler Bestellwert, damit die Regel angewendet wird. |
|  | Kundengruppen | Alle Kundengruppen | Beschränkt die Regel auf bestimmte Kundengruppen. |
|  | Länder | Alle Länder | Beschränkt die Regel auf bestimmte Länder. |
|  | Auszuschließende Produkte | (Leer) | Produkte, deren Wert von der Berechnung ausgeschlossen ist. |
|  | Status | Aktiviert | Aktiviert oder deaktiviert die Regel. |
| **Zahlungsrabatt- oder Gebühren-Audit-Log** | (Alle Felder) | (Nur Ansicht) | Bietet eine historische Aufzeichnung der angewendeten Anpassungen. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Rabatte/Gebühren werden auf der Checkout-Seite nicht angezeigt. Was soll ich überprüfen?**
A1:

- **Modul aktiviert?** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Zahlungsrabatt oder -gebühr“ aktiviert ist.
- **Regeln aktiv?** Navigieren Sie zu **Zahlung > Zahlungsrabatt- oder Gebührenregeln** und überprüfen Sie, ob Ihre spezifischen Regeln aktiviert sind (Spalte Status).
- **Regelbedingungen erfüllt?** Überprüfen Sie nochmals, ob die Warenkorb-Gesamtsumme, Kundengruppe, Land oder ausgeschlossene Produkte-Bedingungen Ihrer Regeln durch Ihre Testbestellung erfüllt werden.
- **Zahlungsmethode ausgewählt?** Die Anpassung erscheint erst, *nachdem* eine Zahlungsmethode auf der Checkout-Seite ausgewählt wurde (es sei denn, „Gebühr/Rabatt in der Warenkorb-Zusammenfassung anzeigen“ ist aktiviert).
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oben rechts). Manchmal verhindern alte Cache-Daten, dass Änderungen sofort angezeigt werden.

**F2: Der Rabatt-/Gebührenbetrag scheint falsch zu sein.**
A2:

- **Werttyp (Prozentsatz vs. Festbetrag):** Stellen Sie sicher, dass Sie den korrekten „Werttyp“ (Prozentsatz oder Festbetrag) für Ihre Regel ausgewählt haben.
- **Auf Versand/Steuern anwenden:** Überprüfen Sie in der Hauptmodulkonfiguration, ob „Gebühr/Rabatt auf Versandkosten anwenden“ und „Gebühr/Rabatt auf Steuern anwenden“ aktiviert oder deaktiviert sind, da dies den Basisbetrag für prozentuale Berechnungen beeinflusst.
- **Ausgeschlossene Produkte:** Wenn Sie Produkte von der Berechnung ausgeschlossen haben, stellen Sie sicher, dass deren Wert korrekt abgezogen wird, bevor der Prozentsatz/Festbetrag angewendet wird.
- **Währung:** Stellen Sie sicher, dass die Standardwährung Ihres Shops in PrestaShop korrekt eingestellt ist, da das Modul für feste Beträge darauf angewiesen ist.

**F3: Das Modul verursacht einen Konflikt mit einem anderen Modul oder meinem Theme.**
A3:

- **Konflikt identifizieren:** Versuchen Sie, andere Module nacheinander zu deaktivieren, um herauszufinden, welches den Konflikt verursacht.
- **Theme-Overrides:** Wenn Sie ein stark angepasstes Theme haben, könnte es Kern-PrestaShop-Checkout-Templates überschreiben, auf die das Modul angewiesen ist. Überprüfen Sie den Ordner `templates/checkout/` Ihres Themes auf Dateien wie `payment.tpl` oder `cart-summary.tpl`.
- **Support kontaktieren:** Wenn Sie einen Konflikt vermuten, sammeln Sie Details (Fehlermeldungen, Schritte zur Reproduktion) und kontaktieren Sie den MyPresta.eu-Support.

**F4: Wie übersetze ich die „Gebühren-/Rabattbezeichnung“ in andere Sprachen?**
A4:

- Gehen Sie zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, Ihr Theme und die Sprache, in die Sie übersetzen möchten.
- Suchen Sie das Modul „Zahlungsrabatt oder -gebühr“. Sie sollten das Feld zur Übersetzung der Einstellung „Gebühren-/Rabattbezeichnung im Warenkorb/Bestellung“ sehen.

**F5: Mein Audit-Log wird zu groß. Wie verwalte ich es?**
A5:

- In der Hauptkonfiguration des Moduls finden Sie eine „Cron-Job-URL für die Bereinigung des Audit-Logs“.
- Kopieren Sie diese URL und richten Sie sie als Cron-Job auf Ihrem Hosting-Server ein. Die meisten Hosting-Kontrollpanels (cPanel, Plesk) haben einen Abschnitt „Cron-Jobs“, in dem Sie einen neuen Job hinzufügen können.
- Stellen Sie ihn so ein, dass er täglich oder wöchentlich ausgeführt wird (z. B. `wget -q -O /dev/null "IHRE_CRON_URL_HIER"`). Dies entfernt automatisch alte Log-Einträge und hält Ihre Datenbank optimiert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Zahlungsrabatt oder -gebühr“ für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul „Zahlungsrabatt oder -gebühr“ folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) mit einem starken Fokus auf Hooks zur Integration in den Checkout-Flow. Es verwendet `ObjectModel` zur Verwaltung von Regeln und Audit-Logs sowie benutzerdefinierte Controller sowohl für Front-Office-AJAX-Interaktionen als auch für die Back-Office-Verwaltung. Die Kernlogik zur Berechnung und Anwendung von Gebühren/Rabatten ist in dedizierten Engine-Klassen gekapselt, um die Trennung der Belange zu gewährleisten. Kompatibilitätsklassen werden verwendet, um Unterschiede zwischen PrestaShop 1.7, 8 und 9 zu überbrücken.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/ajax.php`
  - **Klassenname:** `PaydisorfeeAjaxModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Verarbeitet AJAX-Anfragen von der Checkout-Seite. Wenn ein Kunde eine Zahlungsmethode auswählt, empfängt dieser Controller die Anfrage, berechnet den anwendbaren Rabatt/die Gebühr basierend auf den aktiven Regeln und gibt die aktualisierten Warenkorb-Zusammenfassungsdaten (z. B. neue Gesamtsumme, Gebühren-/Rabattposition) zurück, die dynamisch angezeigt werden sollen.
- `controllers/front/cron.php`
  - **Klassenname:** `PaydisorfeeCronModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Bietet den Endpunkt für den Cron-Job zur Bereinigung des Audit-Logs. Beim Zugriff löst es die Bereinigungslogik innerhalb des Moduls aus und entfernt alte Log-Einträge basierend auf konfigurierten Aufbewahrungsrichtlinien.
- `controllers/front/index.php`
  - **Klassenname:** `PaydisorfeeIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Ein Platzhalter-Front-Controller, der typischerweise für Standard-Modulseiten oder zur Verhinderung der Verzeichnisauflistung verwendet wird. In diesem Modul könnte seine Hauptfunktion darin bestehen, die Standard-Routing zu handhaben, wenn keine spezifische Aktion angefordert wird, oder es könnte zur Hauptshop-Seite umleiten.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminPaydisorfeeAuditLog.php`
  - **Klassenname:** `AdminPaydisorfeeAuditLogController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Zahlungsrabatt- oder Gebühren-Audit-Log
  - **Verwaltete Entität:** `PaydisorfeeAuditLog` (bildet die Datenbanktabelle `paydisorfee_log` ab)
  - **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung der Audit-Log-Einträge im PrestaShop Back Office. Es verwendet `HelperList`, um die Rasteransicht der Log-Datensätze zu rendern.
- `controllers/admin/AdminPaydisorfeeRules.php`
  - **Klassenname:** `AdminPaydisorfeeRulesController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Zahlungsrabatt- oder Gebührenregeln
  - **Verwaltete Entität:** `PaydisorfeeRule` (bildet die Datenbanktabelle `paydisorfee_rule` ab)
  - **Verantwortlichkeit:** Bietet die Schnittstelle zum Erstellen, Bearbeiten, Löschen und Auflisten von Zahlungsrabatt-/Gebührenregeln. Es verwendet `HelperList` für die Regelübersicht und `HelperForm` für die Formulare zum Hinzufügen/Bearbeiten von Regeln, einschließlich dynamischer Selektoren für Produkte, Kundengruppen und Länder.
- `controllers/admin/index.php`
  - **Klassenname:** `PaydisorfeeAdminIndexModuleFrontController` (erweitert `ModuleAdminController`)
  - **Verantwortlichkeit:** Ähnlich wie der Front-`index.php` könnte dies als Standard-Admin-Controller oder als Weiterleitung dienen, wenn keine spezifische Aktion für den Admin-Kontext angefordert wird.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`: Standardmäßig leere Datei, um die Verzeichnisauflistung zu verhindern.
- `classes/PaydisorfeeAdmin.php`
  - **Verantwortlichkeit:** Enthält wahrscheinlich Hilfsmethoden oder Dienstprogrammfunktionen, die spezifisch für die Back-Office-Administration sind, möglicherweise zur Handhabung von Formularübermittlungen, Datenvalidierung oder zum Rendern spezifischer Admin-Komponenten.
- `classes/PaydisorfeeAuditLog.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `paydisorfee_log`
  - **`$definition`-Felder:** Definiert die Struktur der Audit-Log-Einträge (z. B. `id_order`, `id_customer`, `payment_method`, `rule_name`, `type`, `value`, `date_add`).
  - **Wichtige öffentliche Methoden:** Methoden zum Hinzufügen neuer Log-Einträge, Abrufen von Log-Daten und möglicherweise für Bereinigungsvorgänge.
- `classes/PaydisorfeeCartState.php`
  - **Verantwortlichkeit:** Verwaltet den Zustand des Warenkorbs während des Checkout-Prozesses, insbesondere in Bezug auf den angewendeten Rabatt/die Gebühr des Moduls. Es speichert und ruft wahrscheinlich die berechnete Anpassung ab, um sicherzustellen, dass sie über verschiedene Schritte des Checkouts hinweg bestehen bleibt und korrekt auf die Bestellung angewendet wird.
- `classes/PaydisorfeeCompatibility.php`
  - **Verantwortlichkeit:** Enthält Methoden zur Behandlung von Kompatibilitätsproblemen über verschiedene PrestaShop-Versionen (1.7.x, 8.x, 9.x) hinweg. Diese Klasse abstrahiert versionsspezifischen Code, wie Unterschiede in Hook-Namen, Klassenstrukturen oder API-Aufrufen, und stellt sicher, dass das Modul auf allen unterstützten Versionen korrekt funktioniert.
- `classes/PaydisorfeeDashboard.php`
  - **Verantwortlichkeit:** Liefert wahrscheinlich Daten oder Logik für eine potenzielle Dashboard- oder Analyseansicht innerhalb der Admin-Oberfläche des Moduls, die die Auswirkungen von Rabatten/Gebühren zusammenfasst.
- `classes/PaydisorfeeEngine.php`
  - **Verantwortlichkeit:** Dies ist die Kernlogikklasse zur Berechnung und Anwendung des Rabatts oder der Gebühr. Sie nimmt den aktuellen Warenkorb, die ausgewählte Zahlungsmethode und die aktiven Regeln als Eingabe entgegen und bestimmt dann den endgültigen Anpassungsbetrag. Sie behandelt prozentuale vs. feste Berechnungen, Mindest-/Maximal-Warenkorbwerte und Produktausschlüsse.
- `classes/PaydisorfeeFeeProduct.php`
  - **Verantwortlichkeit:** Potenziell eine Hilfsklasse zum Erstellen eines „virtuellen Produkts“, um die Gebühr/den Rabatt im Warenkorb darzustellen, sodass es als Position angezeigt werden kann. Dies ist eine gängige Technik in PrestaShop, um dynamische Preisanpassungen in die Warenkorb-Zusammenfassung zu integrieren.
- `classes/PaydisorfeeLog.php`
  - **Verantwortlichkeit:** Dies könnte ein Alias oder eine ältere Version von `PaydisorfeeAuditLog.php` sein oder ein einfacherer Protokollierungsmechanismus für Debugging-Zwecke.
- `classes/PaydisorfeeRule.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `paydisorfee_rule`
  - **`$definition`-Felder:** Definiert die Struktur einer Zahlungsregel (z. B. `name`, `id_payment_module`, `type`, `value`, `value_type`, `min_cart_amount`, `max_cart_amount`, `customer_groups`, `countries`, `excluded_products`, `active`).
  - **Wichtige öffentliche Methoden:** Methoden für CRUD-Operationen auf Regeln, Abrufen aktiver Regeln und Validieren von Regelbedingungen.

### 4.4 JavaScript-Assets (`views/js/`)

- `paydisorfee/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (verwendet in `AdminPaydisorfeeRules` für den Produktausschluss-Selektor).
  - **Beschreibung:** Bietet Autocomplete-Funktionalität zum Suchen von Produkten bei der Konfiguration des Feldes „Auszuschließende Produkte“ in einer Regel. Es sendet wahrscheinlich AJAX-Anfragen an einen Back-Office-Controller, um Produktvorschläge abzurufen.
- `paydisorfee/views/js/adminPaydisorfeeDashboard.js`
  - **Geltungsbereich:** Back-Office (falls eine Dashboard-Ansicht existiert).
  - **Beschreibung:** JavaScript für alle Dashboard- oder Analysefunktionen innerhalb der Admin-Oberfläche des Moduls. Dies könnte Diagramm-Rendering, Datenfilterung oder dynamisches Laden von Inhalten umfassen.
- `paydisorfee/views/js/adminPaydisorfeeSelector.js`
  - **Geltungsbereich:** Back-Office (verwendet in `AdminPaydisorfeeRules`).
  - **Beschreibung:** Verwaltet die dynamische Auswahl von Kundengruppen, Ländern und potenziell Zahlungsmethoden innerhalb des Regelkonfigurationsformulars. Es könnte Mehrfachauswahlfelder verwalten oder interaktive Elemente für diese Felder bereitstellen.
- `paydisorfee/views/js/checkout.js`
  - **Geltungsbereich:** Front-Office (Checkout-Seite).
  - **Beschreibung:** Dies ist ein kritisches Skript für die Front-Office-Funktionalität. Es überwacht Änderungen in der ausgewählten Zahlungsmethode auf der Checkout-Seite. Wenn eine Zahlungsmethode ausgewählt wird, löst es einen AJAX-Aufruf an `controllers/front/ajax.php` aus, um die Warenkorb-Gesamtsumme neu zu berechnen und die Bestellübersicht dynamisch mit der neuen Rabatt-/Gebührenposition zu aktualisieren. Es behandelt auch die Anzeigelogik für diese Updates.

### 4.5 CSS-Stylesheets (`views/css/`)

- `paydisorfee/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Stile für das Autocomplete-Suchfeld und dessen Vorschlags-Dropdown, verwendet im Produktausschluss-Selektor innerhalb der Regelkonfiguration.
- `paydisorfee/views/css/admin_paydisorfee.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Allgemeine Stile für die Back-Office-Seiten des Moduls, einschließlich der Regelliste, des Audit-Logs und der Konfigurationsformulare. Es gewährleistet ein konsistentes Erscheinungsbild mit dem PrestaShop-Admin-Theme.
- `paydisorfee/views/css/front.css`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Stile zur Anzeige der Rabatt-/Gebührenposition und aller zugehörigen Nachrichten auf der Checkout-Seite oder in der Warenkorb-Zusammenfassung. Es stellt sicher, dass die Anpassung deutlich sichtbar und gut in das Design des Shops integriert ist.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `paydisorfee/lib/searchTool/views/scripts.tpl`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Enthält Smarty-Code zum Einbinden von JavaScript und potenziell CSS für das Suchwerkzeug (z. B. `autocomplete.js`). Es ist wahrscheinlich im Formular `AdminPaydisorfeeRules` enthalten.
- `paydisorfee/views/templates/admin/auditPreview.tpl`
  - **Geltungsbereich:** Back-Office (`AdminPaydisorfeeAuditLogController`).
  - **Beschreibung:** Template zum Rendern der Audit-Log-Einträge, typischerweise von `HelperList` zur Anzeige des Datenrasters verwendet.
- `paydisorfee/views/templates/admin/cron_setup.tpl`
  - **Geltungsbereich:** Back-Office (Hauptmodulkonfiguration).
  - **Beschreibung:** Zeigt die Cron-Job-URL und Anweisungen zur Einrichtung an, wie auf der Hauptkonfigurationsseite des Moduls zu sehen.
- `paydisorfee/views/templates/admin/rulesPreview.tpl`
  - **Geltungsbereich:** Back-Office (`AdminPaydisorfeeRulesController`).
  - **Beschreibung:** Template zum Rendern der Liste der Zahlungsregeln, von `HelperList` zur Anzeige des Datenrasters verwendet.
- `paydisorfee/views/templates/admin/scopeSelector.tpl`
  - **Geltungsbereich:** Back-Office (`AdminPaydisorfeeRulesController`).
  - **Beschreibung:** Template für die dynamischen Selektoren (Kundengruppen, Länder, auszuschließende Produkte) innerhalb des Regelkonfigurationsformulars, oft in Verbindung mit `adminPaydisorfeeSelector.js` verwendet.
- `paydisorfee/views/templates/hook/admin_order.tpl`
  - **Geltungsbereich:** Back-Office (Hook `displayAdminOrderTabContent` oder ähnlich).
  - **Beschreibung:** Zeigt Informationen über den angewendeten Zahlungsrabatt oder die Gebühr auf der PrestaShop-Bestelldetailseite im Back Office an. Dies ermöglicht Administratoren, die Anpassung direkt in der Bestellung zu sehen.
- `paydisorfee/views/templates/hook/payment_top.tpl`
  - **Geltungsbereich:** Front-Office (Hook `displayPaymentTop` oder ähnlich).
  - **Beschreibung:** Dieses Template wird wahrscheinlich verwendet, um die dynamischen Rabatt-/Gebühreninformationen auf der Checkout-Seite anzuzeigen, normalerweise über der Auswahl der Zahlungsmethode oder als Teil der Bestellübersicht. Es wird von `checkout.js` über AJAX aktualisiert.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_paydisorfee_log`: Speichert Audit-Log-Einträge für jeden angewendeten Rabatt oder jede Gebühr.
  - `id_paydisorfee_log` (PRIMÄRSCHLÜSSEL)
  - `id_order` (INT)
  - `id_customer` (INT)
  - `payment_method` (VARCHAR)
  - `rule_name` (VARCHAR)
  - `type` (VARCHAR, ‘discount’ oder ‘fee’)
  - `value` (DECIMAL)
  - `date_add` (DATETIME)
- `ps_paydisorfee_rule`: Speichert die Konfiguration für jede Zahlungsrabatt-/Gebührenregel.
  - `id_paydisorfee_rule` (PRIMÄRSCHLÜSSEL)
  - `name` (VARCHAR)
  - `id_payment_module` (INT)
  - `type` (VARCHAR, ‘discount’ oder ‘fee’)
  - `value` (DECIMAL)
  - `value_type` (VARCHAR, ‘percentage’ oder ‘fixed’)
  - `min_cart_amount` (DECIMAL)
  - `max_cart_amount` (DECIMAL)
  - `customer_groups` (TEXT, serialisiertes Array von IDs)
  - `countries` (TEXT, serialisiertes Array von IDs)
  - `excluded_products` (TEXT, serialisiertes Array von IDs)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `PAYDISORFEE_ENABLED`, `PAYDISORFEE_DISPLAY_CART`, `PAYDISORFEE_APPLY_SHIPPING`, `PAYDISORFEE_APPLY_TAX`, `PAYDISORFEE_LABEL` gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Vor dem Rendern des Front-Controllers | Registriert Front-Office-CSS (`front.css`) und JS (`checkout.js`). |
| `actionAdminControllerSetMedia` | Vor dem Rendern des Admin-Controllers | Registriert Back-Office-CSS (`admin_paydisorfee.css`, `autocomplete.css`) und JS (`adminPaydisorfeeDashboard.js`, `adminPaydisorfeeSelector.js`, `autocomplete.js`). |
| `displayHeader` | Im `<head>`-Bereich jeder Seite | Potenziell zum Laden globaler JS/CSS oder Meta-Tags. |
| `displayPaymentTop` | Oben im Zahlungsbereich auf der Checkout-Seite | Zeigt dem Kunden die dynamischen Gebühren-/Rabattinformationen an. |
| `actionCartSummary` | Nach der Generierung der Warenkorb-Zusammenfassung | Wird verwendet, um die Gebühren-/Rabattposition in die Warenkorb-Zusammenfassung einzufügen. |
| `actionPaymentConfirmation` | Nach erfolgreicher Bestellung | Zeichnet den angewendeten Rabatt/die Gebühr im Audit-Log auf. |
| `actionValidateOrder` | Wenn eine Bestellung validiert wird | Stellt sicher, dass die endgültige Bestellsumme die Anpassung der Zahlungsmethode widerspiegelt. |
| `displayAdminOrderTabContent` | Innerhalb der Bestelldetailseite im Back Office | Zeigt die Zahlungsanpassungsdetails für die Bestellung an. |
| `displayAdminOrder` | Auf der Bestelldetailseite im Back Office | Ähnlich wie `displayAdminOrderTabContent`, zur Anzeige bestellspezifischer Moduldaten. |
| `actionGetExtraMailTemplateVars` | Vor dem Senden einer Bestellbestätigungs-E-Mail | Fügt die Gebühren-/Rabattdetails in E-Mail-Templates ein. |
| `actionObjectOrderAddAfter` | Nach dem Hinzufügen eines neuen Bestellobjekts | Potenziell für die endgültige Verarbeitung oder Protokollierung im Zusammenhang mit der Bestellung. |
| `actionObjectOrderUpdateAfter` | Nach dem Aktualisieren eines Bestellobjekts | Potenziell zur Neubewertung von Gebühren, wenn eine Bestellung geändert wird. |
| `actionObjectCartUpdateAfter` | Nach dem Aktualisieren eines Warenkorbobjekts | Löst die Neuberechnung potenzieller Gebühren/Rabatte aus. |
| `actionObjectCartAddAfter` | Nach dem Hinzufügen eines neuen Warenkorbobjekts | Löst die Neuberechnung potenzieller Gebühren/Rabatte aus. |
| `actionAjaxDie` | Vor `die()` im AJAX-Kontext | Ermöglicht dem Modul, Aktionen auszuführen, bevor die AJAX-Antwort gesendet wird. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite | Registriert globale Admin-JS/CSS. |
| `displayModuleConfigureExtraButtons` | Auf der Modulkonfigurationsseite | Fügt zusätzliche Schaltflächen hinzu (z. B. „Regeln verwalten“, „Audit-Log anzeigen“). |
| `displayPaymentOptions` | Zeigt Zahlungsoptionen beim Checkout an | Potenziell Modifizierung der Zahlungsoptionen basierend auf Regeln. |
| `actionPaymentOptionsModifier` | Modifiziert Zahlungsoptionen vor der Anzeige | Ermöglicht dem Modul, Zahlungsoptionen hinzuzufügen/zu entfernen/zu ändern. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Zahlungsrabatt oder -gebühr“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
