---
title: "Barzahlung bei Abholung im Geschäft (+Gebühr) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Barzahlung bei Abholung im Geschäft (+Gebühr) von MyPresta.eu."
sidebar:
  label: "Barzahlung bei Abholung im Geschäft (+Gebühr) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cash on pickup at store (+fee) auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/cash-on-pickup-at-store-fee.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/cash-on-pickup-at-store-fee/)
>
> ---


# Barzahlung bei Abholung im Geschäft (+Gebühr)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel erforderlich und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie alle Optionen für Ihre Zahlungsmethode „Barzahlung bei Abholung im Geschäft“ einrichten.

#### **Allgemeine Einstellungen**

- **Zahlungslogo**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Hochladen eines benutzerdefinierten Bildes (Logos), das während des Bezahlvorgangs neben der Zahlungsoption „Barzahlung bei Abholung im Geschäft“ angezeigt wird. Dies hilft Kunden, die Zahlungsmethode visuell zu identifizieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Bild hochgeladen wird:* Das gewählte Bild wird neben dem Namen der Zahlungsmethode auf der Zahlungsoptionsseite angezeigt.
    - *Wenn kein Bild hochgeladen wird:* Ein Standard- oder kein Logo wird angezeigt, abhängig von Ihrem Theme.
  - **Empfohlener Wert:** Laden Sie ein klares, kleines Logo hoch, das „Abholung“ oder „Barzahlung“ darstellt, um die Wiedererkennung zu verbessern.
  - **Händlerszenario / Beispiel:** Sie könnten ein Symbol einer Einkaufstasche oder einer Ladenfront hochladen, um die Zahlungsoption hervorzuheben.
- **Titel der Zahlungsmethode** (Konfigurationsschlüssel: `COPPRO_TITLE`)

  - **Was diese Einstellung bewirkt:** Definiert den Namen der Zahlungsmethode, wie er den Kunden während des Bezahlvorgangs angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Der neue Titel wird auf der Zahlungsoptionsseite, der Bestellbestätigung und den Rechnungen angezeigt.
  - **Empfohlener Wert:** „Barzahlung bei Abholung im Geschäft“ oder „Bei Abholung im Geschäft bezahlen“.
  - **Händlerszenario / Beispiel:** Wenn Sie einen spezifischen Markennamen für Ihren Abholservice haben, können Sie diesen hier verwenden, z.B. „MyStore Lokale Abholung“.
- **Bestellstatus für neue Bestellungen** (Konfigurationsschlüssel: `COPPRO_OS`)

  - **Was diese Einstellung bewirkt:** Wählt den anfänglichen Status aus, den eine Bestellung in Ihrem Back Office erhält, wenn ein Kunde „Barzahlung bei Abholung im Geschäft“ wählt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Wartet auf Barzahlung bei Abholung“ gesetzt:* Neue Bestellungen erhalten automatisch diesen Status, wodurch Sie leicht Bestellungen identifizieren können, die für die Abholung und Zahlung vorbereitet werden müssen.
  - **Empfohlener Wert:** Erstellen Sie einen benutzerdefinierten Bestellstatus wie „Wartet auf Barzahlung bei Abholung“ oder „Bereit zur Abholung“ zur besseren Übersichtlichkeit.
  - **Händlerszenario / Beispiel:** Sie könnten ihn auf „Wartet auf Barzahlung bei Abholung“ setzen, damit Ihre Mitarbeiter wissen, dass die Artikel vorbereitet, aber nicht versendet werden sollen.
- **Bestellstatus bei Bezahlung** (Konfigurationsschlüssel: `COPPRO_OS_READY`)

  - **Was diese Einstellung bewirkt:** Wählt den Bestellstatus aus, in den eine Bestellung geändert werden soll, sobald der Kunde seine Artikel erfolgreich bezahlt und in Ihrem Geschäft abgeholt hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Zahlung akzeptiert“ gesetzt:* Sobald Sie die Bestellung im Back Office nach Abholung und Zahlung manuell aktualisieren, wechselt sie in diesen Status und wird als abgeschlossen markiert.
  - **Empfohlener Wert:** „Zahlung akzeptiert“ oder „Geliefert“.
  - **Händlerszenario / Beispiel:** Nachdem der Kunde abholt und bezahlt hat, würden Sie den Bestellstatus auf „Zahlung akzeptiert“ ändern, um die Transaktion in Ihrem System abzuschließen.

#### **Warenkorbwert-Beschränkungen**

- **Mindestwert des Warenkorbs** (Konfigurationsschlüssel: `COPPRO_MINCART`, `COPPRO_MINCART_V`)

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einen Mindestgesamtwert für eine Bestellung festzulegen, damit diese für „Barzahlung bei Abholung im Geschäft“ berechtigt ist. Wenn der Warenkorbwert unter diesem Wert liegt, wird die Zahlungsmethode nicht angezeigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert festgelegt wird (z.B. 10 €):* Kunden mit einem Warenkorbwert unter 10 € sehen „Barzahlung bei Abholung im Geschäft“ nicht als Option.
    - *Wenn leer gelassen oder 0:* Es gibt keine Mindestwertbeschränkung für den Warenkorb.
  - **Empfohlener Wert:** Leer lassen oder 0, es sei denn, Sie haben spezifische betriebliche Gründe, einen Mindestwert zu verlangen.
  - **Händlerszenario / Beispiel:** Sie könnten ein Minimum von 5 € festlegen, um sehr kleine Bestellungen zu vermeiden, die für Ihre Mitarbeiter nicht kosteneffizient für die Abholung zu bearbeiten sind.
- **Maximalwert des Warenkorbs** (Konfigurationsschlüssel: `COPPRO_MAXCART`, `COPPRO_MAXCART_V`)

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einen maximalen Gesamtwert für eine Bestellung festzulegen, damit diese für „Barzahlung bei Abholung im Geschäft“ berechtigt ist. Wenn der Warenkorbwert diesen Wert überschreitet, wird die Zahlungsmethode nicht angezeigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert festgelegt wird (z.B. 500 €):* Kunden mit einem Warenkorbwert über 500 € sehen „Barzahlung bei Abholung im Geschäft“ nicht als Option.
    - *Wenn leer gelassen oder 0:* Es gibt keine Maximalwertbeschränkung für den Warenkorb.
  - **Empfohlener Wert:** Leer lassen oder 0, es sei denn, Sie haben spezifische Bedenken hinsichtlich der Handhabung sehr großer Barzahlungen.
  - **Händlerszenario / Beispiel:** Sie könnten ein Maximum von 1000 € festlegen, wenn Sie sich unwohl fühlen, wenn Mitarbeiter sehr große Bargeldbeträge am Abholpunkt handhaben.

#### **Gebühren-/Rabattkonfiguration**

- **Rabatt anwenden (nicht Gebühr)** (Konfigurationsschlüssel: `COPPRO_DISCOUNT`)

  - **Was diese Einstellung bewirkt:** Dies ist ein Umschalter. Wenn aktiviert, wendet das Modul einen *Rabatt* auf den Gesamtbetrag der Bestellung anstelle einer *Gebühr* an, wenn „Barzahlung bei Abholung im Geschäft“ ausgewählt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Wert, den Sie für „Prozentualer Gebührenwert“ oder „Fester Gebührenwert“ festlegen, wird vom Gesamtbetrag der Bestellung abgezogen.
    - *Wenn deaktiviert:* Der von Ihnen festgelegte Wert wird dem Gesamtbetrag der Bestellung als Gebühr hinzugefügt.
  - **Empfohlener Wert:** Deaktiviert (um eine Gebühr anzuwenden), wenn Sie Betriebskosten decken möchten, oder Aktiviert (um einen Rabatt anzuwenden), wenn Sie Abholungen incentivieren möchten.
  - **Händlerszenario / Beispiel:** Sie könnten dies aktivieren und einen Rabatt von 5 % festlegen, um Kunden zur Abholung ihrer Bestellungen zu ermutigen, wodurch Sie Versandkosten sparen.
- **Gebührenwert neben der Zahlungsmethode** (Konfigurationsschlüssel: `COPPRO_FEEPAY`)

  - **Was diese Einstellung bewirkt:** Dies ist ein Umschalter. Wenn aktiviert, wird der Gebühren- oder Rabattbetrag direkt neben dem Namen der Zahlungsmethode auf der Checkout-Seite angezeigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen „Barzahlung bei Abholung im Geschäft (+ X,XX € Gebühr)“ oder „Barzahlung bei Abholung im Geschäft (- X,XX € Rabatt)“.
    - *Wenn deaktiviert:* Nur der Name der Zahlungsmethode wird angezeigt, und die Gebühr/der Rabatt wird auf den Warenkorbwert angewendet, ohne explizite Erwähnung neben der Methode.
  - **Empfohlener Wert:** Aktiviert, zur Transparenz gegenüber Ihren Kunden.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden über alle zusätzlichen Kosten oder Einsparungen im Voraus vollständig informiert sind, daher aktivieren Sie dies.
- **Prozentuale Gebühr** (Konfigurationsschlüssel: `COPPRO_CHARGEP`, `COPPRO_CHARGEP_V`)

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine Gebühr oder einen Rabatt basierend auf einem Prozentsatz des Gesamtbetrags der Bestellung anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert und ein Wert eingegeben wird (z.B. 5):* Eine Gebühr von 5 % (oder ein Rabatt, wenn „Rabatt anwenden“ aktiviert ist) wird dem Gesamtbetrag der Bestellung hinzugefügt/abgezogen.
    - *Wenn deaktiviert:* Es wird keine prozentuale Gebühr/kein Rabatt angewendet.
  - **Empfohlener Wert:** Deaktiviert, es sei denn, Sie möchten ausdrücklich eine prozentuale Gebühr. Wenn aktiviert, ist ein Wert zwischen 1-10 % für Gebühren oder 2-10 % für Rabatte üblich.
  - **Händlerszenario / Beispiel:** Sie möchten eine Gebühr von 3 % erheben, um die Kosten für die Bargeldabwicklung und -bearbeitung zu decken, also aktivieren Sie dies und geben „3“ ein.
- **Feste Gebühr** (Konfigurationsschlüssel: `COPPRO_CHARGEA`, `COPPRO_CHARGEA_V`)

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine feste Gebühr oder einen festen Rabatt auf den Gesamtbetrag der Bestellung anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert und ein Wert eingegeben wird (z.B. 2,50):* Eine feste Gebühr von 2,50 € (oder ein Rabatt, wenn „Rabatt anwenden“ aktiviert ist) wird dem Gesamtbetrag der Bestellung hinzugefügt/abgezogen.
    - *Wenn deaktiviert:* Es wird keine feste Gebühr/kein fester Rabatt angewendet.
  - **Empfohlener Wert:** Aktiviert, mit einem kleinen festen Betrag (z.B. 1,00 € - 3,00 €), wenn Sie eine einfache, konsistente Gebühr wünschen.
  - **Händlerszenario / Beispiel:** Sie möchten eine Pauschalgebühr von 2 € für alle Abholbestellungen erheben, also aktivieren Sie dies und geben „2.00“ ein.

#### **Erweiterte Anzeige- & Kompatibilitätseinstellungen**

- **Warenkorbzusammenfassung** (Konfigurationsschlüssel: `COPPRO_CARTPRESENTER`)

  - **Was diese Einstellung bewirkt:** Dies ist ein Umschalter, der steuert, ob die Gebühr/der Rabatt explizit im Warenkorbzusammenfassungsblock (z.B. in der rechten Spalte oder am unteren Rand der Warenkorbseite) angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Gebühr/der Rabatt wird in der Warenkorbzusammenfassung aufgeführt und zeigt, wie er sich auf den Gesamtbetrag auswirkt.
    - *Wenn deaktiviert:* Die Gebühr/der Rabatt wird auf den Gesamtbetrag angewendet, aber möglicherweise nicht explizit in der Warenkorbzusammenfassung vor dem Zahlungsschritt aufgeschlüsselt.
  - **Empfohlener Wert:** Aktiviert, für volle Transparenz.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden den Posten „Abholgebühr“ in ihrer Warenkorbzusammenfassung sehen, bevor sie überhaupt den Zahlungsschritt erreichen, also aktivieren Sie dies.
- **Adresszusammenfassung** (Konfigurationsschlüssel: `COPPRO_HOWFEE`)

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert, wo die Gebühr/der Rabatt im Abschnitt der Adresszusammenfassung des Checkouts angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Gebühr/der Rabatt wird in der Adresszusammenfassung sichtbar sein, normalerweise in der Nähe der Versandkosten.
    - *Wenn deaktiviert:* Die Gebühr/der Rabatt wird angewendet, aber nicht explizit in der Adresszusammenfassung angezeigt.
  - **Empfohlener Wert:** Aktiviert, für Konsistenz und Transparenz.
  - **Händlerszenario / Beispiel:** Sie möchten, dass die Gebühr in mehreren Phasen des Checkouts, einschließlich der Adresszusammenfassung, sichtbar ist, also aktivieren Sie dies.
- **Aktiviert** (Konfigurationsschlüssel: `COPPRO_EVENTLISTENER`)

  - **Was diese Einstellung bewirkt:** Dies ist ein allgemeiner Umschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Zahlungsmethode „Barzahlung bei Abholung im Geschäft“ ist aktiv und für Kunden verfügbar.
    - *Wenn deaktiviert:* Die Zahlungsmethode wird ausgeblendet und ist nicht verfügbar.
  - **Empfohlener Wert:** Aktiviert, sobald Sie alle anderen Einstellungen konfiguriert haben.
  - **Händlerszenario / Beispiel:** Sie haben die Einrichtung des Moduls abgeschlossen und sind bereit, diese Zahlungsmethode anzubieten, also aktivieren Sie sie.
- **Deaktiviert** (Konfigurationsschlüssel: `PS_ONE_PAGE_CHECKOUT_ENABLED`)

  - **Was diese Einstellung bewirkt:** Diese Einstellung bezieht sich wahrscheinlich auf die Kompatibilität mit PrestaShops One-Page-Checkout. Es könnte eine ältere Einstellung oder ein Anzeigeindikator sein.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist wahrscheinlich ein schreibgeschützter Indikator oder eine Einstellung, die im Allgemeinen auf ihrem Standardwert belassen werden sollte, es sei denn, der Support weist Sie anders an.
  - **Empfohlener Wert:** Als Standard belassen.
  - **Händlerszenario / Beispiel:** Keine direkte Interaktion des Händlers erwartet.
- **CSS-Selektoren für Warenkorbelemente** (Konfigurationsschlüssel: `COPPRO_CSS_CART_TOTAL`, `COPPRO_CSS_CART_SUBTOTAL`, `COPPRO_CSS_CART_SHIPPING`)

  - **Was diese Einstellungen bewirken:** Diese Felder ermöglichen es Ihnen, die CSS-Selektoren für die Warenkorb-Gesamtsumme, Zwischensumme und Versandkosten-Elemente Ihres Themes anzugeben. Dies ist entscheidend, damit das Modul diese Werte korrekt aktualisiert, wenn eine Gebühr/ein Rabatt angewendet wird, insbesondere wenn Ihr Theme nicht-standardmäßige Selektoren verwendet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei korrekter Konfiguration:* Das Modul aktualisiert die angezeigten Warenkorb-Gesamtsummen, Zwischensummen und Versandkosten auf der Checkout-Seite genau, um die Gebühr/den Rabatt widerzuspiegeln.
    - *Bei falscher Konfiguration oder leer gelassen:* Die Warenkorb-Gesamtsummen werden möglicherweise nicht korrekt aktualisiert, was zu Kundenverwirrung oder falsch angezeigten Preisen führt.
  - **Empfohlener Wert:** Zunächst leer lassen. Wenn Sie feststellen, dass die Warenkorb-Gesamtsummen nach Auswahl von „Barzahlung bei Abholung im Geschäft“ nicht korrekt aktualisiert werden, müssen Sie möglicherweise den Entwickler Ihres Themes oder einen Webmaster konsultieren, um die richtigen CSS-Selektoren zu finden.
  - **Händlerszenario / Beispiel:** Nach der Installation des Moduls stellen Sie fest, dass sich der Gesamtpreis auf der Checkout-Seite nicht ändert, wenn die Abholgebühr angewendet wird. Ihr Webmaster würde den Code Ihres Themes überprüfen, um die richtigen CSS-Selektoren (z.B. `#cart-total-price`, `.product-total-price`) zu finden und hier einzugeben.

#### **Ausschlussregeln**

- **Produkte ausschließen** (Konfigurationsschlüssel: `COPPRO_EXCL_PRODUCTS`)

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bestimmte Produkte vom Kauf mit der Zahlungsmethode „Barzahlung bei Abholung im Geschäft“ auszuschließen. Wenn ein ausgeschlossenes Produkt im Warenkorb ist, ist diese Zahlungsmethode nicht verfügbar.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Produkte ausgewählt sind:* Wenn ein Kunde eines dieser Produkte in seinen Warenkorb legt, verschwindet die Option „Barzahlung bei Abholung im Geschäft“ aus den Zahlungsmethoden.
    - *Wenn keine Produkte ausgewählt sind:* Alle Produkte sind berechtigt.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Produkte, die nicht abgeholt oder bar bezahlt werden können.
  - **Händlerszenario / Beispiel:** Sie verkaufen sehr hochwertige Artikel (z.B. teuren Schmuck), für die Sie lieber nur sichere Online-Zahlungen akzeptieren möchten. Sie würden diese Produkte zur Ausschlussliste hinzufügen.
- **Kategorien ausschließen** (Konfigurationsschlüssel: `COPPRO_EXCL_CAT`)

  - **Was diese Einstellung bewirkt:** Ähnlich wie beim Ausschließen von Produkten können Sie hiermit ganze Produktkategorien vom Kauf mit „Barzahlung bei Abholung im Geschäft“ ausschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Kategorien ausgewählt sind:* Wenn ein Kunde ein Produkt aus diesen Kategorien in seinen Warenkorb legt, ist die Option „Barzahlung bei Abholung im Geschäft“ nicht verfügbar.
    - *Wenn keine Kategorien ausgewählt sind:* Alle Kategorien sind berechtigt.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Kategorien, die nicht für die Abholung geeignet sind.
  - **Händlerszenario / Beispiel:** Sie haben eine Kategorie „Digitale Downloads“. Da diese Artikel keine physische Abholung erfordern, würden Sie diese Kategorie ausschließen.
- **Ausschlüsse aktivieren** (Konfigurationsschlüssel: `COPPRO_EXCL_ENABLE`)

  - **Was diese Einstellung bewirkt:** Dies ist ein Hauptschalter zum Aktivieren oder Deaktivieren aller von Ihnen eingerichteten Produkt- und Kategorieausschlussregeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ihre Produkt- und Kategorieausschlussregeln sind aktiv.
    - *Wenn deaktiviert:* Alle Produkte und Kategorien sind für „Barzahlung bei Abholung im Geschäft“ berechtigt, unabhängig davon, was Sie in den Ausschlusslisten ausgewählt haben.
  - **Empfohlener Wert:** Aktiviert, wenn Sie Ausschlussregeln definiert haben.
  - **Händlerszenario / Beispiel:** Sie haben Ausschlüsse für bestimmte Produkte eingerichtet und möchten, dass diese Regeln aktiv sind, also aktivieren Sie diesen Schalter.

#### **Analyse & Interne Einstellungen**

- **Analyseeinstellungen** (Konfigurationsschlüssel: `COPPRO_ANALYTICS_DEFAULT_CHART`, `COPPRO_ANALYTICS_PERIOD`, `COPPRO_ANALYTICS_IMPACT_DAYS`, `COPPRO_ANALYTICS_CHART_WEEKS`, `COPPRO_ANALYTICS_CHART_MONTHS`, `COPPRO_ANALYTICS_CHART_YEARS`)

  - **Was diese Einstellungen bewirken:** Dies sind interne Einstellungen, die sich auf Analyse- oder Berichtsfunktionen des Moduls beziehen und es Ihnen ermöglichen, zu konfigurieren, wie Daten für den internen Gebrauch gesammelt oder angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:** Diese wirken sich typischerweise nur auf die Berichtsansichten im Back Office aus, nicht auf das Kundenerlebnis im Front Office.
  - **Empfohlener Wert:** Als Standard belassen, es sei denn, Sie haben spezifische Berichtsanforderungen.
  - **Händlerszenario / Beispiel:** Keine direkte Interaktion des Händlers für den täglichen Betrieb erwartet.
- **Gebührenänderungsdatum / Snapshot** (Konfigurationsschlüssel: `COPPRO_FEE_CHANGE_DATE`, `COPPRO_FEE_CHANGE_SNAPSHOT`)

  - **Was diese Einstellungen bewirken:** Dies sind wahrscheinlich interne Moduleinstellungen, um zu verfolgen, wann Gebührenkonfigurationen zuletzt geändert wurden, oder um einen Snapshot früherer Gebühreneinstellungen zu speichern. Dies dient normalerweise zu Prüfungs- oder Debugging-Zwecken.
  - **Auswirkung der Änderung dieser Einstellung:** Keine direkte Auswirkung auf das Kundenerlebnis.
  - **Empfohlener Wert:** Als Standard belassen.
  - **Händlerszenario / Beispiel:** Keine direkte Interaktion des Händlers erwartet.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul scheint keine dedizierten benutzerdefinierten Admin-Controller über seine Hauptkonfigurationsseite hinaus zu haben. Alle Einstellungen werden über die `getContent()`-Methode der Hauptmoduldatei verwaltet.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Zahlungslogo | Relevantes Bild hochladen | Visuelle Identifikation der Zahlungsmethode. |
| Modulkonfiguration | Titel der Zahlungsmethode | „Barzahlung bei Abholung im Geschäft“ | Name, der Kunden für die Zahlungsoption angezeigt wird. |
| Modulkonfiguration | Bestellstatus für neue Bestellungen | Benutzerdefiniert „Wartet auf Barzahlung bei Abholung“ | Initialer Status für Bestellungen, die diese Methode verwenden. |
| Modulkonfiguration | Bestellstatus bei Bezahlung | „Zahlung akzeptiert“ / „Geliefert“ | Endgültiger Status, nachdem der Kunde bezahlt und abgeholt hat. |
| Modulkonfiguration | Mindestwert des Warenkorbs | Leer / 0 | Mindestbestellwert, damit diese Zahlungsmethode angezeigt wird. |
| Modulkonfiguration | Maximalwert des Warenkorbs | Leer / 0 | Maximaler Bestellwert, damit diese Zahlungsmethode angezeigt wird. |
| Modulkonfiguration | Rabatt anwenden (nicht Gebühr) | Deaktiviert | Bestimmt, ob ein Rabatt oder eine Gebühr angewendet wird. |
| Modulkonfiguration | Gebührenwert neben der Zahlungsmethode | Aktiviert | Zeigt Gebühr/Rabatt neben dem Namen der Zahlungsmethode an. |
| Modulkonfiguration | Prozentuale Gebühr | Deaktiviert | Wendet eine prozentuale Gebühr/einen Rabatt an. |
| Modulkonfiguration | Prozentualer Gebührenwert | 0 | Der prozentuale Wert für die Gebühr/den Rabatt. |
| Modulkonfiguration | Feste Gebühr | Aktiviert (mit Wert) | Wendet eine feste Gebühr/einen festen Rabatt an. |
| Modulkonfiguration | Fester Gebührenwert | z.B. 2.00 | Der feste Betrag für die Gebühr/den Rabatt. |
| Modulkonfiguration | Warenkorbzusammenfassung | Aktiviert | Zeigt Gebühr/Rabatt detailliert in der Warenkorbzusammenfassung an. |
| Modulkonfiguration | Adresszusammenfassung | Aktiviert | Zeigt Gebühr/Rabatt in der Adresszusammenfassung an. |
| Modulkonfiguration | Aktiviert | Aktiviert | Aktiviert/deaktiviert die Zahlungsmethode. |
| Modulkonfiguration | Produkte ausschließen | Leer | Verhindert, dass bestimmte Produkte diese Methode verwenden. |
| Modulkonfiguration | Kategorien ausschließen | Leer | Verhindert, dass Produkte aus bestimmten Kategorien diese Methode verwenden. |
| Modulkonfiguration | Ausschlüsse aktivieren | Aktiviert (wenn Regeln festgelegt) | Hauptschalter für Produkt-/Kategorieausschlussregeln. |
| Modulkonfiguration | CSS-Selektoren (Warenkorb-Gesamtsumme, Zwischensumme, Versand) | Leer (bei Bedarf anpassen) | Stellt korrekte Aktualisierung der Warenkorb-Gesamtsumme mit dem Theme sicher. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Zahlungsmethode „Barzahlung bei Abholung im Geschäft“ wird während des Checkouts nicht angezeigt.**
A:

- **Einstellung „Aktiviert“ prüfen:** Gehen Sie zu Module > Modul-Manager > Konfigurieren für „Barzahlung bei Abholung im Geschäft (+Gebühr)“ und stellen Sie sicher, dass der Hauptschalter „Aktiviert“ eingeschaltet ist.
- **Warenkorbwert-Beschränkungen prüfen:** Überprüfen Sie Ihre Einstellungen für „Mindestwert des Warenkorbs“ und „Maximalwert des Warenkorbs“. Wenn der Warenkorbwert des Kunden außerhalb dieses Bereichs liegt, wird die Methode nicht angezeigt.
- **Ausschlüsse prüfen:** Wenn Sie Produkt- oder Kategorieausschlüsse eingerichtet haben, stellen Sie sicher, dass der aktuelle Warenkorb keine ausgeschlossenen Artikel enthält. Überprüfen Sie auch, ob „Ausschlüsse aktivieren“ eingeschaltet ist.
- **Geo-Beschränkungen prüfen:** Stellen Sie sicher, dass die Zahlungsmethode in den allgemeinen Zahlungseinstellungen von PrestaShop (Zahlung > Präferenzen) nicht nach Land oder Währung eingeschränkt ist.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Parameter > Performance** und klicken Sie auf „Cache leeren“.

**F2: Die Gebühr/der Rabatt wird auf der Checkout-Seite nicht korrekt angewendet oder angezeigt.**
A:

- **Gebühren-/Rabatteinstellungen überprüfen:** Überprüfen Sie, ob „Prozentuale Gebühr“ oder „Feste Gebühr“ aktiviert ist und der entsprechende Wert korrekt eingegeben wurde. Stellen Sie außerdem sicher, dass „Rabatt anwenden (nicht Gebühr)“ wie beabsichtigt eingestellt ist.
- **Anzeigeeinstellungen prüfen:** Stellen Sie sicher, dass „Gebührenwert neben der Zahlungsmethode“, „Warenkorbzusammenfassung“ und „Adresszusammenfassung“ alle für maximale Sichtbarkeit aktiviert sind.
- **CSS-Selektoren (Erweitert):** Wenn Ihr Theme stark angepasst ist, kann es sein, dass das Modul die richtigen Elemente zum Aktualisieren nicht finden kann. Überprüfen Sie die Einstellungen „CSS-Selektoren für Warenkorbelemente“. Möglicherweise benötigen Sie einen Webmaster, um die richtigen Selektoren für die Warenkorb-Gesamtsumme, Zwischensumme und Versandelemente Ihres Themes zu identifizieren.

**F3: Wie ändere ich den Text „Barzahlung bei Abholung im Geschäft“ in etwas anderes?**
A:

- Sie können den Anzeigenamen direkt in der Modulkonfiguration ändern. Suchen Sie die Einstellung „Titel der Zahlungsmethode“ auf der Hauptkonfigurationsseite.
- Für mehrsprachige Shops stellen Sie sicher, dass Sie die richtige Sprache aus dem Dropdown-Menü oben auf der Modulkonfigurationsseite auswählen (falls verfügbar) oder verwenden Sie das PrestaShop-Übersetzungstool (International > Übersetzungen > Installierte Modulübersetzungen).

**F4: Kann ich diese Zahlungsmethode nur auf bestimmte Versanddienstleister oder Kundengruppen beschränken?**
A:

- **Versanddienstleister:** Ja, die Kernzahlungspräferenzen von PrestaShop ermöglichen es Ihnen, Zahlungsmethoden nach Versanddienstleister einzuschränken. Gehen Sie in Ihrem Back Office zu **Zahlung > Präferenzen**. Stellen Sie im Abschnitt „Versanddienstleister-Beschränkungen“ sicher, dass „Barzahlung bei Abholung im Geschäft (+Gebühr)“ für die Versanddienstleister ausgewählt ist, mit denen Sie es zulassen möchten (z.B. Ihr „Lokale Abholung“-Versanddienstleister).
- **Kundengruppen:** Ebenso können Sie unter **Zahlung > Präferenzen** Zahlungsmethoden nach Kundengruppe einschränken. Stellen Sie sicher, dass die relevanten Kundengruppen (z.B. „Kunde“, „Besucher“) für diese Zahlungsmethode ausgewählt sind.

**F5: Welchen Bestellstatus sollte ich für „Barzahlung bei Abholung“-Bestellungen verwenden?**
A:

- Es wird dringend empfohlen, einen benutzerdefinierten Bestellstatus in PrestaShop (Bestellungen > Bestellstatus) speziell für „Barzahlung bei Abholung“-Bestellungen zu erstellen, z.B. „Wartet auf Barzahlung bei Abholung“ oder „Bereit zur Abholung“. Dies hilft Ihnen, diese Bestellungen in Ihrem Back Office leicht zu identifizieren.
- Legen Sie dann in der Modulkonfiguration „Bestellstatus für neue Bestellungen“ auf diesen benutzerdefinierten Status fest.
- Sobald der Kunde bezahlt und abgeholt hat, ändern Sie den Bestellstatus auf der Bestelldetailseite manuell auf „Zahlung akzeptiert“ oder „Geliefert“.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `Barzahlung bei Abholung im Geschäft (+Gebühr)` (`coppro`) ist ein Standard-PrestaShop-Zahlungsmodul, das dem MVC-Muster folgt. Es erweitert `PaymentModule` und integriert sich hauptsächlich über Hooks, um Zahlungsoptionen anzuzeigen, die Validierung zu verarbeiten und Bestellinformationen anzuzeigen. Das Modul berechnet Gebühren/Rabatte dynamisch basierend auf der Konfiguration und aktualisiert die Warenkorb-Gesamtsummen über JavaScript im Front-Office-Checkout. Es verwendet `Configuration` zur Speicherung von Einstellungen und führt keine benutzerdefinierten `ObjectModel`-Klassen oder Datenbanktabellen ein.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/index.php`
    - Klassenname: `CopproIndexModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
    - Zuständigkeit: Dieser Controller könnte als Standard-Einstiegspunkt dienen oder allgemeine modulbezogene Front-Office-Anfragen bearbeiten, die nicht in spezifische Zahlungsabläufe passen. Angesichts seines Namens könnte es ein Fallback oder ein einfacher Anzeige-Controller sein.
  - `controllers/front/store.php`
    - Klassenname: `CopproStoreModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
    - Zuständigkeit: Behandelt potenziell Logik im Zusammenhang mit Ladenstandorten oder Abholpunkten, obwohl die Modulbeschreibung nicht explizit mehrere Ladenstandorte erwähnt. Es könnte ein Platzhalter oder für zukünftige Erweiterungen sein.
  - `controllers/front/validation.php`
    - Klassenname: `CopproValidationModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
    - Zuständigkeit: Dies ist der kritische Controller für die Zahlungsabwicklung. Er empfängt die Zahlungsbestätigung vom Checkout-Prozess, validiert die Bestellung und leitet den Kunden zur Bestellbestätigungsseite weiter. Er interagiert mit dem Hauptmodul `coppro.php`, um die Bestellung mit dem korrekten Status und den angewendeten Gebühren/Rabatten abzuschließen.
- **Back-Office-Admin-Controller**:

  - Dieses Modul enthält keine benutzerdefinierten Admin-Controller. Die gesamte Back-Office-Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei `coppro.php` behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen in einem `classes/`-Verzeichnis zu definieren. Seine Kernlogik befindet sich in der Hauptmoduldatei `coppro.php`, die `PaymentModule` erweitert.

### 4.4 JavaScript-Assets (`views/js/`)

- `coppro/lib/searchTool/views/js/autocomplete.js`
  - Geltungsbereich: Wahrscheinlich Back-Office.
  - Zuständigkeit: Bietet Autocomplete-Funktionalität, wahrscheinlich für die Produkt- oder Kategorieauswahl in der Modulkonfiguration (z.B. für Ausschlusslisten). Es bindet an Eingabefelder und führt AJAX-Anfragen aus, um Vorschläge abzurufen.
- `coppro/views/js/adminCopproDashboard.js`
  - Geltungsbereich: Back-Office.
  - Zuständigkeit: Verwaltet JavaScript für alle administrativen Dashboard- oder Analysefunktionen innerhalb der Modulkonfigurationsseite. Es könnte die Diagrammdarstellung oder Datenanzeige verwalten.
- `coppro/views/js/adminCopproProductSearch.js`
  - Geltungsbereich: Back-Office.
  - Zuständigkeit: Verwaltet speziell die Produktsuchoberfläche innerhalb der Admin-Konfiguration des Moduls, wahrscheinlich für die Einstellung „Produkte ausschließen“. Es verwaltet die Sucheingabe, die Anzeige der Ergebnisse und die Auswahl.
- `coppro/views/js/adminCopproSelector.js`
  - Geltungsbereich: Back-Office.
  - Zuständigkeit: Verwaltet die Auswahllogik für verschiedene Elemente im Admin-Panel, möglicherweise für Kategorien oder andere konfigurierbare Listen.
- `coppro/views/js/coppro-checkout.js`
  - Geltungsbereich: Front-Office.
  - Zuständigkeit: Dies ist das Haupt-Front-Office-Skript. Es überwacht Änderungen bei der Auswahl der Zahlungsmethode während des Checkouts. Wenn „Barzahlung bei Abholung im Geschäft“ ausgewählt wird, aktualisiert es dynamisch die Warenkorbzusammenfassung (Gesamtsumme, Zwischensumme, Versand), um die berechnete Gebühr oder den Rabatt widerzuspiegeln. Es verwendet die in der Modulkonfiguration definierten CSS-Selektoren (`COPPRO_CSS_CART_TOTAL` usw.), um DOM-Elemente anzusprechen und zu ändern. Es könnte auch AJAX-Aufrufe zur Neuberechnung der Gesamtsummen verarbeiten, falls das Backend benötigt wird.
- `coppro/views/js/copproBoMockConsole.js`
  - Geltungsbereich: Back-Office.
  - Zuständigkeit: Wahrscheinlich ein Debugging- oder Entwicklungsdienstprogramm, möglicherweise zur Simulation von Konsolenausgaben oder Protokollierung innerhalb des Back Office.

### 4.5 CSS-Stylesheets (`views/css/`)

- `coppro/lib/searchTool/views/css/autocomplete.css`
  - Geltungsbereich: Back-Office.
  - Zuständigkeit: Gestaltet die Autocomplete-Dropdowns und Such-Eingabefelder, die in der Admin-Konfiguration verwendet werden.
- `coppro/views/css/admin_coppro.css`
  - Geltungsbereich: Back-Office-Admin-Formulargestaltung.
  - Zuständigkeit: Bietet spezifische Gestaltung für die Konfigurationsseite des Moduls im PrestaShop Back Office, um eine konsistente und benutzerfreundliche Oberfläche zu gewährleisten.
- `coppro/views/css/coppro.css`
  - Geltungsbereich: Front-Office-Kundenstyling.
  - Zuständigkeit: Enthält Stile für die Anzeige der Zahlungsoption „Barzahlung bei Abholung im Geschäft“, potenziell für das Zahlungslogo, den Gebühren-/Rabatttext oder andere vom Modul auf der Checkout-Seite eingeführte benutzerdefinierte Elemente. Entwickler können diese Stile in der `custom.css` ihres Themes oder in einem Child-Theme überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `coppro/views/templates/hook/confirmation.tpl`
    - Hook: Wahrscheinlich `displayPaymentReturn` oder ähnlich.
    - Ausgabe: Inhalt für die Bestellbestätigungsseite nach einer erfolgreichen „Barzahlung bei Abholung“-Bestellung, der den Kunden über die Zahlung bei Abholung informiert.
  - `coppro/views/templates/hook/displayAdminOrder16.tpl`
    - Hook: `displayAdminOrder` (für PrestaShop 1.6.x).
    - Ausgabe: Zusätzliche Informationen oder Aktionen im Zusammenhang mit „Barzahlung bei Abholung“-Bestellungen innerhalb der Back-Office-Bestelldetailseite für PS 1.6.
  - `coppro/views/templates/hook/displayAdminOrder17.tpl`
    - Hook: `displayAdminOrder` (für PrestaShop 1.7.x, 8.x, 9.x).
    - Ausgabe: Ähnlich wie `displayAdminOrder16.tpl`, aber angepasst für die PS 1.7+-Back-Office-Bestelldetailseite, potenziell mit Abholanweisungen oder Gebührendetails.
  - `coppro/views/templates/hook/displayOrderDetail.tpl`
    - Hook: `displayOrderDetail`.
    - Ausgabe: Informationen zur Zahlungsmethode „Barzahlung bei Abholung“ auf der Bestelldetailseite des Kunden im Front Office.
  - `coppro/views/templates/hook/payment.tpl`
    - Hook: `paymentOptions` (oder `displayPaymentOptions`).
    - Ausgabe: Die HTML-Struktur für die Zahlungsoption „Barzahlung bei Abholung im Geschäft“ auf der Checkout-Seite, einschließlich des Zahlungslogos, des Titels und des dynamisch berechneten Gebühren-/Rabatttextes.
- **Admin-Templates (`views/templates/admin/`)**:

  - `coppro/lib/searchTool/views/scripts.tpl`
    - Hook: Wahrscheinlich `actionAdminControllerSetMedia` oder direkt in `getContent()` enthalten.
    - Ausgabe: Enthält JavaScript- und CSS-Assets für das Suchwerkzeug, das in der Admin-Konfiguration verwendet wird.
  - `coppro/views/templates/admin/productSearchTool.tpl`
    - Ausgabe: Die HTML-Struktur für die Produktsuch- und Auswahl-Oberfläche innerhalb der Modulkonfiguration, verwendet für die Einstellung „Produkte ausschließen“.
  - `coppro/views/templates/admin/scopeSelector.tpl`
    - Ausgabe: HTML für einen generischen Bereichsselektor, potenziell verwendet für Kategorien oder andere filterbare Listen in der Admin-Konfiguration.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `coppro/views/templates/front/validation.tpl`
    - Ausgabe: Inhalt, der vom `CopproValidationModuleFrontController` nach der Zahlungsvalidierung angezeigt wird, typischerweise eine Weiterleitung oder eine einfache Nachricht vor der endgültigen Bestätigungsseite.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung der Methoden `Configuration::updateValue()` und `Configuration::get()` gespeichert, wobei die Schlüssel mit `COPPRO_` präfixiert sind.
  Beispiel-Konfigurationsschlüssel:

  - `COPPRO_OS`
  - `COPPRO_OS_READY`
  - `COPPRO_MAXCART_V`
  - `COPPRO_MINCART_V`
  - `COPPRO_FEEPAY`
  - `COPPRO_DISCOUNT`
  - `COPPRO_CHARGEP_V`
  - `COPPRO_CHARGEA_V`
  - `COPPRO_EXCL_PRODUCTS`
  - `COPPRO_EXCL_CAT`
  - `COPPRO_TITLE`
  - `COPPRO_CARTPRESENTER`
  - `COPPRO_HOWFEE`
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Zum Einbinden von Front-Office-CSS (`coppro.css`) und JavaScript (`coppro-checkout.js`) Assets. |
| `displayPaymentOptions` | Während des Checkouts, um verfügbare Zahlungsmethoden aufzulisten. | Zum Anzeigen der Zahlungsoption „Barzahlung bei Abholung im Geschäft“ mit Titel, Logo und berechneter Gebühr/Rabatt. |
| `paymentOptions` | Alias für `displayPaymentOptions` (ältere PS-Versionen). | Gleich wie `displayPaymentOptions`. |
| `displayPaymentReturn` | Auf der Bestellbestätigungsseite nach der Zahlung. | Zum Anzeigen spezifischer Anweisungen oder Bestätigungsmeldungen für „Barzahlung bei Abholung“-Bestellungen. |
| `displayPDFInvoice` | Wenn eine PDF-Rechnung generiert wird. | Um sicherzustellen, dass die Zahlungsmethode „Barzahlung bei Abholung im Geschäft“ korrekt auf der Rechnung angegeben ist. |
| `displayOrderDetail` | Auf der Bestelldetailseite des Kunden im Front Office. | Zum Anzeigen der gewählten Zahlungsmethode und aller zugehörigen Details. |
| `displayAdminOrder` | Auf der Bestelldetailseite im Back Office. | Zum Anzeigen zusätzlicher Informationen oder Verwaltungstools speziell für „Barzahlung bei Abholung“-Bestellungen für Administratoren. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien-Assets lädt. | Zum Einbinden von Back-Office-CSS (`admin_coppro.css`, `autocomplete.css`) und JavaScript (`adminCopproDashboard.js`, `adminCopproProductSearch.js`, `adminCopproSelector.js`, `autocomplete.js`) für die Konfigurationsseite des Moduls. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Zum Ausführen von Aktionen nach der Validierung, wie z.B. das Aktualisieren des Bestellstatus oder das Protokollieren von Details, spezifisch für „Barzahlung bei Abholung“-Bestellungen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen technischen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Barzahlung bei Abholung im Geschäft (+Gebühr)“ zur Verfügung.
