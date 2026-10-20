---
title: "Nachnahme mit Gebühr - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Nachnahme mit Gebühr“ von MyPresta.eu."
sidebar:
  label: "Nachnahme mit Gebühr - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cash on delivery with fee auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-fee.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/cash-on-delivery-with-fee/)
>
> ---


# Nachnahme mit Gebühr

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Nachnahme mit Gebühr“, der direkt nach der Installation oder durch Navigation zu **Module > Modul-Manager**, Suche nach „Nachnahme mit Gebühr“ und Klicken auf „Konfigurieren“ zugänglich ist.

#### **Allgemeine Einstellungen**

- **Deaktivieren / Aktiviert / Deaktiviert (Hauptmodulstatus)**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Nachnahme-Zahlungsmethode mit Gebühr in Ihrem Shop zu aktivieren oder zu deaktivieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Nachnahme-Zahlungsoption, zusammen mit ihren konfigurierten Gebühren, steht den Kunden während des Checkouts zur Verfügung.
    - *Wenn deaktiviert:* Die Nachnahme-Zahlungsoption wird den Kunden nicht angezeigt, unabhängig von anderen Einstellungen.
  - **Empfohlener Wert:** `Aktiviert`, wenn Sie Nachnahme anbieten möchten.
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder vorübergehend keine Nachnahme mehr anbieten möchten, würden Sie dies auf `Deaktiviert` setzen.
- **Wert (Nachnahmegebühr-Wert)**

  - **Was diese Einstellung bewirkt:** Dieses Feld bestimmt den Basisbetrag oder Prozentsatz der Nachnahmegebühr. Die genaue Interpretation (fester Betrag oder Prozentsatz) hängt von der Einstellung „Wie soll die Gebühr einbezogen werden?“ ab.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert direkt die Kosten, die zu Nachnahmebestellungen hinzugefügt werden.
  - **Empfohlener Wert:** Beginnen Sie mit `0.00` und passen Sie ihn basierend auf Ihren Spediteurgebühren an.
  - **Händlerszenario / Beispiel:** Wenn Ihr Spediteur 2,50 € für Nachnahme berechnet, könnten Sie `2.50` eingeben. Wenn er 1 % der Bestellung berechnet, könnten Sie `1` eingeben.
- **Wie soll die Gebühr einbezogen werden?**

  - **Was diese Einstellung bewirkt:** Definiert, wie der „Wert“ (aus der vorherigen Einstellung) auf den Gesamtbestellwert angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Zu den Versandkosten hinzufügen:* Die Nachnahmegebühr wird zu den dem Kunden angezeigten Versandkosten hinzugefügt. Dies kann die Checkout-Anzeige vereinfachen, indem Gebühren kombiniert werden.
    - *Als separates Produkt/Dienstleistung hinzufügen:* Die Nachnahmegebühr erscheint als separate Position in der Warenkorbzusammenfassung und auf der Rechnung, oft als „Nachnahmegebühr“ oder ähnlich bezeichnet. Dies bietet maximale Transparenz.
  - **Empfohlener Wert:** `Als separates Produkt/Dienstleistung hinzufügen` für Klarheit und rechtliche Konformität.
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden die Nachnahmegebühr klar als separaten Posten sehen, wählen Sie „Als separates Produkt/Dienstleistung hinzufügen“. Wenn Sie eine sauberere, kombinierte Versandkosten bevorzugen, wählen Sie „Zu den Versandkosten hinzufügen“.
- **Bestellstatus nach dem Kauf mit dem Nachnahme-Modul**

  - **Was diese Einstellung bewirkt:** Legt den anfänglichen Status einer Bestellung fest, die mit der Nachnahme-Zahlungsmethode aufgegeben wurde.
  - **Auswirkung der Änderung dieser Einstellung:** Bestimmt, wie Nachnahmebestellungen in Ihrem Back Office unmittelbar nach ihrer Aufgabe erscheinen.
  - **Empfohlener Wert:** `Zahlung akzeptiert` (oder ein ähnlicher von Ihnen konfigurierter „Zahlung ausstehend“-Status). Dies ermöglicht es Ihnen, Nachnahmebestellungen zu unterscheiden, die bestätigt, aber noch nicht physisch bezahlt wurden.
  - **Händlerszenario / Beispiel:** Sie könnten dies auf „Warten auf Nachnahmezahlung“ (wenn Sie einen solchen Status erstellt haben) setzen, um Nachnahmebestellungen, die auf die physische Zahlung bei Lieferung warten, einfach zu filtern und zu verwalten.
- **Zusätzliche Zusammenfassung vor der Bestätigung anzeigen**

  - **Was diese Einstellung bewirkt:** Steuert, ob ein zusätzlicher Zusammenfassungsblock im letzten Checkout-Schritt angezeigt wird, kurz bevor der Kunde seine Bestellung bestätigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine detaillierte Aufschlüsselung einschließlich Warenkorbwert, Versand und Nachnahmegebühr wird angezeigt.
    - *Wenn deaktiviert:* Die Standard-PrestaShop-Zusammenfassung wird verwendet, die die Nachnahmegebühr möglicherweise nicht explizit als separate Position aufschlüsselt.
  - **Empfohlener Wert:** `Aktiviert` für maximale Transparenz und rechtliche Konformität.
  - **Händlerszenario / Beispiel:** Um sicherzustellen, dass Kunden alle Gebühren vollständig kennen, bevor sie sich verpflichten, insbesondere die Nachnahmegebühr, aktivieren Sie diese Option.
- **Warenkorbzusammenfassung / Adresszusammenfassung / Warenkorb-Gesamtwert min (CSS-Selektoren)**

  - **Was diese Einstellung bewirkt:** Diese Felder ermöglichen es Ihnen, CSS-Selektoren für verschiedene Elemente auf Ihrer Checkout-Seite anzugeben. Das Modul verwendet diese Selektoren, um die Nachnahmegebühr-Informationen korrekt in die Checkout-Zusammenfassung Ihres Themes einzufügen.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn Ihr Theme nicht-standardmäßige CSS-Klassen für diese Elemente verwendet, stellt die Anpassung dieser Selektoren sicher, dass die Nachnahmegebühr korrekt angezeigt wird. Falsche Werte können dazu führen, dass die Gebühr nicht oder an der falschen Stelle erscheint.
  - **Empfohlener Wert:** Leer lassen für automatische Erkennung oder die vom Modul bereitgestellten Standardwerte verwenden. Nur ändern, wenn die Anzeige der Nachnahmegebühr in Ihrem benutzerdefinierten Theme fehlerhaft ist.
  - **Händlerszenario / Beispiel:** Wenn Sie ein benutzerdefiniertes Theme installiert haben und die Nachnahmegebühr nicht in der Warenkorbzusammenfassung angezeigt wird, muss Ihr Webentwickler möglicherweise das HTML Ihres Themes überprüfen und diese Selektoren an die Struktur Ihres Themes anpassen.

#### **Gebührenberechnung & Bedingungen**

- **Deaktivieren / Aktiviert / Deaktiviert (Bedingung für maximalen Warenkorbwert)**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert eine Bedingung, bei der die Nachnahme-Zahlungsmethode nur verfügbar ist, wenn der Warenkorbwert *unter* einem bestimmten Maximalwert liegt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden mit Warenkörben, die den angegebenen Maximalwert überschreiten, sehen Nachnahme nicht als Zahlungsoption.
    - *Wenn deaktiviert:* Es gilt keine maximale Warenkorbwertbeschränkung für Nachnahme.
  - **Empfohlener Wert:** `Deaktiviert`, es sei denn, Sie haben spezifische Gründe, hochpreisige Nachnahmebestellungen zu begrenzen.
  - **Händlerszenario / Beispiel:** Wenn Sie Probleme mit betrügerischen oder nicht abgeholten hochpreisigen Nachnahmebestellungen hatten, könnten Sie dies aktivieren und einen `CODPRO_MOD_MAXCART_V` auf 500 € setzen, um das Risiko zu mindern.
- **CODPRO\_MOD\_MAXCART\_V (Maximaler Warenkorbwert)**

  - **Was diese Einstellung bewirkt:** Der spezifische Geldwert für die Bedingung des maximalen Warenkorbwerts.
  - **Auswirkung der Änderung dieser Einstellung:** Definiert die Obergrenze für die Nachnahmeberechtigung.
  - **Empfohlener Wert:** Setzen Sie einen Wert, der Ihrer Risikobereitschaft für Nachnahmebestellungen entspricht.
  - **Händlerszenario / Beispiel:** Wenn `Deaktivieren / Aktiviert / Deaktiviert (Bedingung für maximalen Warenkorbwert)` aktiviert ist und Sie dies auf `500.00` setzen, können Kunden mit Bestellungen über 500 € keine Nachnahme verwenden.
- **Deaktivieren / Aktiviert / Deaktiviert (Bedingung für minimalen Warenkorbwert)**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert eine Bedingung, bei der die Nachnahme-Zahlungsmethode nur verfügbar ist, wenn der Warenkorbwert *über* einem bestimmten Minimalwert liegt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden mit Warenkörben, die den angegebenen Minimalwert unterschreiten, sehen Nachnahme nicht als Zahlungsoption.
    - *Wenn deaktiviert:* Es gilt keine minimale Warenkorbwertbeschränkung für Nachnahme.
  - **Empfohlener Wert:** `Deaktiviert`, es sei denn, Sie haben spezifische Gründe, sehr kleine Nachnahmebestellungen zu vermeiden.
  - **Händlerszenario / Beispiel:** Wenn die feste Nachnahmegebühr sehr kleine Bestellungen unrentabel macht, könnten Sie dies aktivieren und einen `CODPRO_MOD_MINCART_V` auf 10 € setzen.
- **CODPRO\_MOD\_MINCART\_V (Minimaler Warenkorbwert)**

  - **Was diese Einstellung bewirkt:** Der spezifische Geldwert für die Bedingung des minimalen Warenkorbwerts.
  - **Auswirkung der Änderung dieser Einstellung:** Definiert die Untergrenze für die Nachnahmeberechtigung.
  - **Empfohlener Wert:** Setzen Sie einen Wert, der Nachnahme für Sie rentabel macht.
  - **Händlerszenario / Beispiel:** Wenn `Deaktivieren / Aktiviert / Deaktiviert (Bedingung für minimalen Warenkorbwert)` aktiviert ist und Sie dies auf `10.00` setzen, können Kunden mit Bestellungen unter 10 € keine Nachnahme verwenden.
- **CODPRO\_CHARGEP\_V (Prozentualer Gebührenwert)**

  - **Was diese Einstellung bewirkt:** Dieses Feld definiert den prozentualen Wert der Nachnahmegebühr.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn „Wie soll die Gebühr einbezogen werden?“ auf eine prozentbasierte Option eingestellt ist, wird dieser Wert zur Berechnung der Gebühr verwendet.
  - **Empfohlener Wert:** Zunächst `0.00`, anpassen basierend auf der prozentualen Gebühr Ihres Spediteurs.
  - **Händlerszenario / Beispiel:** Wenn Ihr Spediteur 1,5 % des Bestellwerts für Nachnahme berechnet, würden Sie hier `1.5` eingeben.
- **CODPRO\_PERCENTAGE\_TYPE (Basis für prozentuale Berechnung)**

  - **Was diese Einstellung bewirkt:** Bestimmt, worauf die prozentuale Gebühr berechnet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Warenkorbwert (mit Versand):* Der Prozentsatz wird auf den Gesamtbetrag einschließlich Produkte und Versand berechnet.
    - *Warenkorbwert (ohne Versand):* Der Prozentsatz wird nur auf die Zwischensumme der Produkte berechnet.
  - **Empfohlener Wert:** `Warenkorbwert (mit Versand)`, da dies typischerweise die Art und Weise ist, wie Spediteure ihre Nachnahmegebühren berechnen.
  - **Händlerszenario / Beispiel:** Wenn Ihr Spediteur 1 % des *gesamten* Betrags berechnet, den er vom Kunden einzieht (Produkte + Versand), wählen Sie „Warenkorbwert (mit Versand)“.
- **CODPRO\_CHARGEA\_V (Fester Gebührenbetrag)**

  - **Was diese Einstellung bewirkt:** Dieses Feld definiert den festen Geldbetrag der Nachnahmegebühr.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn „Wie soll die Gebühr einbezogen werden?“ auf eine feste Betragsoption eingestellt ist, wird dieser Wert verwendet.
  - **Empfohlener Wert:** Zunächst `0.00`, anpassen basierend auf der festen Gebühr Ihres Spediteurs.
  - **Händlerszenario / Beispiel:** Wenn Ihr Spediteur eine Pauschale von 3,00 € für Nachnahme berechnet, würden Sie hier `3.00` eingeben.
- **CODPRO\_MIN\_CHARGEV (Mindestgebühr für prozentuale Gebühr)**

  - **Was diese Einstellung bewirkt:** Wenn Sie eine prozentbasierte Gebühr verwenden, legt dies einen festen Mindestbetrag fest, den die Nachnahmegebühr beträgt, auch wenn der berechnete Prozentsatz niedriger ist.
  - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Sie immer mindestens einen bestimmten Betrag für Nachnahme zurückerhalten, insbesondere bei kleinen Bestellungen, bei denen ein Prozentsatz sehr niedrig sein könnte.
  - **Empfohlener Wert:** `0.00` (kein Minimum) oder ein kleiner Betrag wie `1.00` oder `2.00`, wenn Sie Mindestkosten haben.
  - **Händlerszenario / Beispiel:** Wenn Ihre prozentuale Gebühr 1 % beträgt und eine 50-€-Bestellung zu einer Gebühr von 0,50 € führen würde, Sie aber ein Minimum von 1,50 € sicherstellen möchten, würden Sie dies auf `1.50` setzen.
- **CODPRO\_MAX\_CHARGEV (Maximalgebühr für prozentuale Gebühr)**

  - **Was diese Einstellung bewirkt:** Wenn Sie eine prozentbasierte Gebühr verwenden, legt dies einen festen Höchstbetrag fest, den die Nachnahmegebühr beträgt, auch wenn der berechnete Prozentsatz höher ist.
  - **Auswirkung der Änderung dieser Einstellung:** Verhindert, dass die Nachnahmegebühr bei sehr großen Bestellungen übermäßig hoch wird.
  - **Empfohlener Wert:** `0.00` (kein Maximum) oder eine angemessene Obergrenze wie `10.00` oder `15.00`.
  - **Händlerszenario / Beispiel:** Wenn Ihre prozentuale Gebühr 1 % beträgt und eine 2000-€-Bestellung zu einer Gebühr von 20 € führen würde, Sie aber die Nachnahmegebühr auf 10 € begrenzen möchten, würden Sie dies auf `10.00` setzen.
- **CODPRO\_FEETAX (Steuer auf Gebühr anwenden)**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Nachnahmegebühr selbst der Mehrwertsteuer/Steuern unterliegen soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Auf die Nachnahmegebühr wird gemäß der ausgewählten Steuerregel Steuer angewendet.
    - *Wenn deaktiviert:* Die Nachnahmegebühr wird als steuerbefreit behandelt.
  - **Empfohlener Wert:** `Aktiviert`, wenn Ihre lokalen Steuervorschriften die Besteuerung von Gebühren vorschreiben. Konsultieren Sie Ihren Steuerberater.
  - **Händlerszenario / Beispiel:** In vielen Ländern unterliegen Servicegebühren wie Nachnahmegebühren der Mehrwertsteuer. Sie würden dies aktivieren, um die Einhaltung zu gewährleisten.
- **CODPRO\_FEETAXRULE (Steuerregel für Gebühr)**

  - **Was diese Einstellung bewirkt:** Wenn `CODPRO_FEETAX` aktiviert ist, können Sie über dieses Dropdown-Menü auswählen, welche PrestaShop-Steuerregel auf die Nachnahmegebühr angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Der ausgewählte Steuersatz wird auf die Nachnahmegebühr angewendet.
  - **Empfohlener Wert:** Wählen Sie die entsprechende Steuerregel für Dienstleistungen in Ihrem Land.
  - **Händlerszenario / Beispiel:** Wenn Sie eine Steuerregel „Standard-MwSt. (20%)“ für Dienstleistungen haben, würden Sie diese hier auswählen.

#### **Spediteurspezifische Gebühren**

- **codpro\_carrier (Spediteurauswahl)**
  - **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, unterschiedliche Nachnahmegebühren für jeden von Ihnen angebotenen Versanddienstleister zu definieren.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn ein Kunde während des Checkouts einen bestimmten Spediteur auswählt, wird die mit diesem Spediteur verbundene Nachnahmegebühr anstelle der allgemeinen Gebühr angewendet.
  - **Empfohlener Wert:** Konfigurieren Sie Gebühren für alle Spediteure, die Nachnahme anbieten.
  - **Händlerszenario / Beispiel:** Wenn Spediteur A 3,00 € für Nachnahme berechnet und Spediteur B 1,5 % des Bestellwerts, können Sie diese unterschiedlichen Gebühren hier festlegen.

#### **Erweiterte Einstellungen (Normalerweise für Entwickler/Spezifische Szenarien)**

- **PS\_LANG\_DEFAULT / PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG (Spracheinstellungen)**

  - **Was diese Einstellung bewirkt:** Dies sind Standard-PrestaShop-Konfigurationswerte, die sich auf die Standardsprache und die Sprache des Mitarbeiterformulars beziehen. Das Modul zeigt sie möglicherweise als Referenz an, erfordert hier jedoch typischerweise keine Änderung.
  - **Auswirkung der Änderung dieser Einstellung:** Keine direkte Auswirkung auf die Kernfunktionalität des Moduls, stellt aber die korrekte Sprachanzeige im Back Office sicher.
  - **Empfohlener Wert:** Als Standard belassen.
- **CODPRO\_ANALYTICS\_DEFAULT\_CHART / CODPRO\_ANALYTICS\_PERIOD / CODPRO\_ANALYTICS\_IMPACT\_DAYS / CODPRO\_ANALYTICS\_CHART\_WEEKS / CODPRO\_ANALYTICS\_CHART\_MONTHS (Analytik-Einstellungen)**

  - **Was diese Einstellung bewirkt:** Diese Einstellungen beziehen sich auf potenzielle interne Analysen oder Dashboard-Funktionen innerhalb des Moduls (falls implementiert). Sie steuern, wie Daten angezeigt oder gefiltert werden könnten.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert, wie Analysedaten zu Nachnahmebestellungen im Back Office präsentiert werden könnten.
  - **Empfohlener Wert:** Als Standard belassen, es sei denn, Sie haben spezifische Analyseanforderungen.
  - **Händlerszenario / Beispiel:** Wenn das Modul ein Dashboard enthält, könnten diese Einstellungen die Standardansicht (z. B. letzte 7 Tage, letzter Monat) für die Leistung von Nachnahmebestellungen steuern.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### **4.2.1 AdminCodProCarriersFeesController (Back Office > Module > Nachnahme mit Gebühr > Spediteurgebühren)**

- **Bildschirmname & Menüpfad:** „Spediteurgebühren“ (normalerweise unter dem Menüpunkt „Nachnahme mit Gebühr“ im PrestaShop Back Office zu finden).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm bietet eine Raster- oder Listenansicht zur Verwaltung von Nachnahmegebühren speziell für jeden Versanddienstleister. Sie können neue spediteurspezifische Regeln hinzufügen, bestehende bearbeiten oder löschen. Für jeden Spediteur können Sie definieren:
  - Ob die Gebühr ein fester Betrag oder ein Prozentsatz ist.
  - Den spezifischen festen Betrag oder Prozentsatzwert.
  - Mindest- und Höchstgebühren für prozentuale Gebühren.
  - Ob Steuern anfallen und welche Steuerregel verwendet werden soll.
- **Auswirkung von Änderungen:** Alle hier konfigurierten Regeln überschreiben die allgemeinen Nachnahmegebühreneinstellungen für die angegebenen Spediteure. Wenn ein Spediteur hier eine Regel hat, wird die Gebühr dieser Regel angewendet. Wenn ein Spediteur hier nicht aufgeführt ist, gelten die allgemeinen Nachnahmegebühreneinstellungen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Abschnitt regelmäßig, wenn sich Ihre Spediteurverträge oder Nachnahmegebühren ändern. Fügen Sie neue Spediteure hinzu, wenn Sie sie in Ihrem Shop einführen, und konfigurieren Sie deren spezifische Nachnahmegebühren.

#### **4.2.2 AdminCodProCarriersRangeFeesController (Back Office > Module > Nachnahme mit Gebühr > Bereichsgebühren)**

- **Bildschirmname & Menüpfad:** „Bereichsgebühren“ (normalerweise unter dem Menüpunkt „Nachnahme mit Gebühr“ im PrestaShop Back Office zu finden).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm ermöglicht es Ihnen, Nachnahmegebühren basierend auf dem Gesamtwert des Warenkorbs des Kunden zu definieren. Sie können verschiedene Gebührenstrukturen für verschiedene Preisbereiche einrichten (z. B. Bestellungen von 0 € bis 50 €, 50 € bis 100 € usw.). Für jeden Bereich können Sie definieren:
  - Den minimalen und maximalen Warenkorbwert für den Bereich.
  - Ob die Gebühr ein fester Betrag oder ein Prozentsatz ist.
  - Den spezifischen festen Betrag oder Prozentsatzwert.
  - Mindest- und Höchstgebühren für prozentuale Gebühren innerhalb dieses Bereichs.
  - Ob Steuern anfallen und welche Steuerregel verwendet werden soll.
- **Auswirkung von Änderungen:** Diese bereichsbasierten Regeln bieten eine zusätzliche Flexibilitätsebene. Wenn der Warenkorbwert eines Kunden in einen definierten Bereich fällt, wird die für diesen Bereich angegebene Gebühr angewendet. Diese Regeln können mit spediteurspezifischen Regeln interagieren und potenziell eine sehr detaillierte Kontrolle ermöglichen (z. B. Spediteur A berechnet X für Bestellungen unter 50 € und Y für Bestellungen über 50 €).
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Abschnitt, um dynamische Preise für Nachnahme basierend auf dem Bestellwert zu implementieren. Dies ist besonders nützlich, um Risiken bei hochpreisigen Bestellungen zu steuern oder Nachnahme für mittelpreisige Bestellungen attraktiver zu machen.

#### **4.2.3 index.php (Back Office > Module > Nachnahme mit Gebühr > Dashboard/Analytik)**

- **Bildschirmname & Menüpfad:** Dieser `index.php`-Controller dient typischerweise als Platzhalter oder Standard-Einstiegspunkt für den Admin-Bereich eines Moduls. Im Kontext dieses Moduls könnte er verwendet werden, um ein Dashboard oder Analysen zu Nachnahmebestellungen anzuzeigen.
- **Verfügbare Aktionen & Einstellungen:** Wenn dieser Controller für ein Dashboard verwendet wird, würde er wahrscheinlich Diagramme, Statistiken oder Key Performance Indicators (KPIs) zu Nachnahmebestellungen anzeigen (z. B. Anzahl der Nachnahmebestellungen, Gesamtumsatz aus Nachnahme, durchschnittlich erhobene Nachnahmegebühr). Es könnten Filter für Datumsbereiche oder andere Parameter vorhanden sein.
- **Auswirkung von Änderungen:** Die Interaktion mit einem Dashboard hier würde nur die angezeigten Daten ändern, nicht die Konfiguration des Shops.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Dashboard (falls verfügbar) regelmäßig, um die Leistung und den Einfluss Ihrer Nachnahme-Zahlungsmethode zu überwachen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Hauptkonfiguration** | Aktiviert / Deaktiviert | Aktiviert | Hauptschalter für die Nachnahme-Zahlungsmethode. |
| | Wert (Basisgebühr) | 0.00 | Standardgebührenbetrag/-prozentsatz. |
| | Wie soll die Gebühr einbezogen werden? | Als separates Produkt/Dienstleistung | Bestimmt, wie die Gebühr im Warenkorb/auf der Rechnung erscheint. |
| | Bestellstatus nach dem Kauf | Zahlung akzeptiert | Initialer Status für Nachnahmebestellungen. |
| | Zusätzliche Zusammenfassung anzeigen | Aktiviert | Zeigt detaillierte Gebührenaufschlüsselung vor der Bestätigung an. |
| | Max. Warenkorbwert-Bedingung | Deaktiviert | Beschränkt Nachnahme für Bestellungen über einem Wert. |
| | Max. Warenkorbwert | 0.00 | Der spezifische maximale Warenkorbwert. |
| | Min. Warenkorbwert-Bedingung | Deaktiviert | Beschränkt Nachnahme für Bestellungen unter einem Wert. |
| | Min. Warenkorbwert | 0.00 | Der spezifische minimale Warenkorbwert. |
| | Prozentualer Gebührenwert | 0.00 | Der prozentuale Wert für die Nachnahmegebühr. |
| | Basis für prozentuale Berechnung | Warenkorbwert (mit Versand) | Worauf der Prozentsatz berechnet wird. |
| | Fester Gebührenbetrag | 0.00 | Der feste Betrag für die Nachnahmegebühr. |
| | Mindestgebühr (für %) | 0.00 | Stellt eine Mindestgebühr für prozentuale Berechnungen sicher. |
| | Maximalgebühr (für %) | 0.00 | Begrenzt die Gebühr für prozentuale Berechnungen. |
| | Steuer auf Gebühr anwenden | Aktiviert (falls zutreffend) | Bestimmt, ob die Nachnahmegebühr besteuert wird. |
| | Steuerregel für Gebühr | Entsprechende Steuerregel auswählen | Welche Steuerregel auf die Gebühr angewendet wird. |
| **AdminCodProCarriersFees** | Spediteurspezifische Gebührenregeln | Nach Bedarf konfigurieren | Überschreibt die allgemeine Gebühr für bestimmte Spediteure. |
| **AdminCodProCarriersRangeFees** | Bestellwert-Bereichsgebührenregeln | Nach Bedarf konfigurieren | Wendet unterschiedliche Gebühren basierend auf Warenkorbwertbereichen an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Nachnahmegebühr wird auf meiner Checkout-Seite nicht angezeigt oder ist an der falschen Stelle.**
A1: Dies geschieht normalerweise bei benutzerdefinierten Themes.
- **„Zusätzliche Zusammenfassung vor der Bestätigung anzeigen“ überprüfen:** Stellen Sie sicher, dass diese Option in der Hauptkonfiguration des Moduls auf `Aktiviert` gesetzt ist.
- **CSS-Selektoren:** Wenn Ihr Theme nicht-standardmäßige CSS-Klassen verwendet, findet das Modul möglicherweise nicht die richtigen Stellen, um die Gebühr einzufügen. Gehen Sie zur Konfigurationsseite des Moduls und überprüfen Sie die CSS-Selektorfelder „Warenkorbzusammenfassung“, „Adresszusammenfassung“ und „Warenkorb-Gesamtwert min“. Möglicherweise benötigen Sie einen Webentwickler, um das HTML Ihres Themes zu überprüfen und die korrekten Selektoren bereitzustellen.
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren), nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F2: Ich habe eine Gebühr eingerichtet, aber sie wird nicht auf Bestellungen angewendet.**
A2:
- **Modul aktiviert:** Stellen Sie sicher, dass der Hauptschalter „Aktiviert / Deaktiviert“ für das Modul auf `Aktiviert` gesetzt ist.
- **Gebührenwert:** Überprüfen Sie nochmals, ob Sie einen Wert ungleich Null in der Hauptkonfiguration eingegeben haben oder spezifische Gebühren in den Abschnitten „Spediteurgebühren“ oder „Bereichsgebühren“ konfiguriert haben.
- **Bedingungen erfüllt:** Vergewissern Sie sich, dass der Warenkorb des Kunden alle von Ihnen festgelegten „Min. Warenkorbwert“- oder „Max. Warenkorbwert“-Bedingungen erfüllt.
- **Spediteurspezifische Überschreibungen:** Wenn Sie Gebühren in „Spediteurgebühren“ konfiguriert haben, stellen Sie sicher, dass der Kunde einen dieser Spediteure auswählt. Andernfalls sollte die allgemeine Gebühr angewendet werden.
- **Steuerregel:** Wenn Sie eine Steuerregel für die Gebühr verwenden, stellen Sie sicher, dass die Steuerregel selbst in PrestaShop korrekt konfiguriert ist.

**F3: Wie übersetze ich den Text des Moduls (z. B. „Nachnahmegebühr“) in andere Sprachen?**
A3: Sie können Modul-Strings direkt in PrestaShop übersetzen:
- Navigieren Sie zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“.
- Wählen Sie Ihr Theme, Ihre Sprache und dann „Nachnahme mit Gebühr“ aus dem Modul-Dropdown.
- Sie sehen eine Liste aller übersetzbaren Strings des Moduls. Geben Sie Ihre Übersetzungen ein und speichern Sie.

**F4: Kann ich Nachnahme nur für bestimmte Kundengruppen oder Länder anbieten?**
A4: Das Modul „Nachnahme mit Gebühr“ selbst verfügt nicht über integrierte Optionen für Kundengruppen- oder Länderbeschränkungen. Es können jedoch die Kernbeschränkungen für Zahlungsmodule von PrestaShop verwendet werden:
- Gehen Sie zu **Shop-Parameter > Bestellungen > Zahlung**.
- Sie können Zahlungsmethoden nach Währung, Land oder Gruppe einschränken. Suchen Sie „Nachnahme mit Gebühr“ und wenden Sie dort Ihre gewünschten Beschränkungen an.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Nachnahme mit Gebühr“ (`codpro`) folgt einer Standard-PrestaShop-Modularchitektur und erweitert `PaymentModule`, um sich in den Checkout-Fluss zu integrieren. Es verwendet mehrere Front- und Admin-Controller für spezifische Funktionalitäten wie Zahlungsvalidierung, spediteurspezifische Gebührenverwaltung und bereichsbasierte Gebührenkonfigurationen. Das Modul stützt sich stark auf das PrestaShop-Hook-System, um seine Logik und Anzeigeelemente in verschiedenen Phasen des Front-Office (Checkout, Bestellbestätigung, Rechnung) und Back-Office (Bestellansicht) einzufügen. Die Konfiguration wird hauptsächlich in `ps_configuration` gespeichert, wobei wahrscheinlich benutzerdefinierte Tabellen für spediteur- und bereichsbasierte Gebührendefinitionen verwendet werden.

### 4.2 Controller (`controllers/`)

#### **Front-Office-Controller**

- `controllers/front/index.php`
  - Klassenname: `CodProIndexModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - Verantwortung: Dieser Controller könnte als Standard-Einstiegspunkt dienen oder grundlegende Weiterleitungen für Front-Office-Modulaktionen handhaben. Angesichts des Modulzwecks könnte es ein Platzhalter sein oder für einfache AJAX-Anfragen im Zusammenhang mit Gebührenberechnungsaktualisierungen während des Checkouts verwendet werden.
- `controllers/front/validation.php`
  - Klassenname: `CodProValidationModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - Verantwortung: Dies ist der entscheidende Controller für die Zahlungsabwicklung, wenn ein Kunde „Nachnahme mit Gebühr“ wählt. Er übernimmt die endgültige Validierung der Bestellung, wendet die berechnete Nachnahmegebühr auf den Warenkorb an und leitet den Kunden zur Bestellbestätigungsseite weiter. Er interagiert mit der Hauptmodulklasse `codpro.php`, um Gebühreneinstellungen abzurufen und die Bestellung zu aktualisieren.

#### **Back-Office-Admin-Controller**

- `controllers/admin/AdminCodProCarriersFees.php`
  - Klassenname: `AdminCodProCarriersFeesController` (erweitert `ModuleAdminController`)
  - Tab-Name: „Spediteurgebühren“ (oder ähnlich, über das Modulmenü zugänglich).
  - Verwaltete Entität: `Configuration` (obwohl es spezifische Konfigurationseinträge im Zusammenhang mit Spediteuren verwaltet).
  - Verantwortung: Bietet die Schnittstelle zur Verwaltung von Nachnahmegebühren auf Spediteur-Basis. Es zeigt eine Liste der konfigurierten Spediteurgebühren an, ermöglicht das Hinzufügen neuer sowie das Bearbeiten/Löschen bestehender Einträge. Es verwendet wahrscheinlich PrestaShops `HelperList` und `HelperForm` für seine Benutzeroberfläche.
- `controllers/admin/AdminCodProCarriersRangeFees.php`
  - Klassenname: `AdminCodProCarriersRangeFeesController` (erweitert `ModuleAdminController`)
  - Tab-Name: „Bereichsgebühren“ (oder ähnlich, über das Modulmenü zugänglich).
  - Verwaltete Entität: `CodProTotal` (wahrscheinlich ein benutzerdefiniertes `ObjectModel` für bereichsbasierte Gebühren).
  - Verantwortung: Verwaltet Nachnahmegebühren basierend auf Bestellwertbereichen. Es bietet ein Raster zum Definieren, Bearbeiten und Löschen von Gebührenregeln für verschiedene Warenkorbwertbereiche. Dieser Controller nutzt ebenfalls PrestaShops `HelperList` und `HelperForm` für seine administrative Oberfläche.
- `controllers/admin/index.php`
  - Klassenname: `AdminCodProIndexController` (erweitert wahrscheinlich `ModuleAdminController`)
  - Tab-Name: Platzhalter oder Dashboard.
  - Verwaltete Entität: Keine direkt.
  - Verantwortung: Dieser Controller dient wahrscheinlich als Einstiegspunkt für ein Modul-Dashboard oder eine Standardansicht beim Navigieren zum Admin-Bereich des Moduls. Er könnte Analysen oder eine Zusammenfassung der Nachnahmebestellungen anzeigen.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass die Kernlogik für die Verwaltung von Spediteur- und Bereichsgebühren direkt in den Controllern `AdminCodProCarriersFeesController` und `AdminCodProCarriersRangeFeesController` unter Verwendung direkter Datenbankinteraktionen oder durch die Definition einfacher Arrays für die Konfiguration gehandhabt werden könnte. Allerdings impliziert `AdminCodProCarriersRangeFeesController`, der `codprototal` verwaltet, dass es eine `ObjectModel` namens `CodProTotal` (oder ähnlich) im Verzeichnis `classes/` geben *sollte*, auch wenn sie im Dossier nicht explizit aufgeführt ist. Falls nicht, bedeutet dies, dass direkte SQL-Abfragen verwendet werden, was weniger ideal ist.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/adminCodProCarriersFees.js`
  - Geltungsbereich: Back-Office (AdminCodProCarriersFeesController).
  - Funktionalität: Handhabt wahrscheinlich dynamisches Verhalten auf der Konfigurationsseite für Spediteurgebühren. Dies könnte AJAX-Aufrufe zum Speichern/Laden von Daten, Formularvalidierung oder interaktive Elemente zum Hinzufügen/Entfernen von Spediteurgebührenregeln umfassen.
- `views/js/adminCodProDashboard.js`
  - Geltungsbereich: Back-Office (AdminCodProIndexController oder ähnliche Dashboard-Ansicht).
  - Funktionalität: Verantwortlich für das Rendern von Diagrammen, das Aktualisieren von Statistiken und das Handhaben interaktiver Elemente auf dem Modul-Dashboard. Es könnte Diagrammbibliotheken (z. B. Chart.js) verwenden und AJAX-Anfragen stellen, um Analysedaten abzurufen.
- `views/js/codpro-checkout.js`
  - Geltungsbereich: Front-Office (Checkout-Seite).
  - Funktionalität: Dies ist entscheidend für die Front-End-Benutzererfahrung. Es überwacht Änderungen bei der Auswahl der Zahlungsmethode (insbesondere bei „Nachnahme mit Gebühr“), aktualisiert die Bestellübersicht dynamisch, um die Nachnahmegebühr widerzuspiegeln, und verarbeitet möglicherweise AJAX-Anfragen zur Neuberechnung von Gebühren, wenn sich der Versanddienstleister oder der Warenkorbinhalt ändert. Es stellt sicher, dass die Gebühr vor der Bestellbestätigung sichtbar ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/admin_codpro.css`
  - Geltungsbereich: Back-Office (Admin-Panel).
  - Funktionalität: Bietet Styling für die Konfigurationsseiten des Moduls, die Verwaltung von Spediteurgebühren, die Verwaltung von Bereichsgebühren und alle Dashboard-Elemente. Es sorgt für ein konsistentes Erscheinungsbild innerhalb des PrestaShop Back Office.
  - Schlüssel-Selektoren: Zielt wahrscheinlich auf spezifische IDs oder Klassen innerhalb der Admin-Formulare und -Listen des Moduls ab (z. B. `.codpro-admin-form`, `.codpro-dashboard-chart`).
- `views/css/codpro.css`
  - Geltungsbereich: Front-Office (Checkout-Seite, Bestellbestätigung, Rechnung).
  - Funktionalität: Gestaltet die Anzeige der Nachnahmegebühr in der Checkout-Zusammenfassung, den Zahlungsoptionen, der Bestellbestätigungsseite und möglicherweise der PDF-Rechnung. Es stellt sicher, dass die Gebühr deutlich sichtbar und in das Theme des Shops integriert ist.
  - Schlüssel-Selektoren: Zielt auf Elemente ab, in die die Nachnahmegebühr eingefügt wird (z. B. `.codpro-fee-display`, `.payment_option_codpro`, `.order-summary-cod-fee`). Entwickler müssen diese möglicherweise in ihrem Theme überschreiben, um eine perfekte visuelle Integration zu erreichen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### **Hook-Templates (`views/templates/hook/`)**

- `views/templates/hook/confirmation.tpl`
  - Hook: `paymentReturn` oder ähnlich.
  - Ausgabe: Die Details der Nachnahmegebühr auf der Bestellbestätigungsseite nach einer erfolgreichen Nachnahmebestellung.
- `views/templates/hook/displayAdminOrder16.tpl`
  - Hook: `displayAdminOrder` (für PrestaShop 1.6).
  - Ausgabe: Zusätzliche Informationen zur Nachnahmegebühr auf der Bestelldetailseite im PrestaShop 1.6 Back Office.
- `views/templates/hook/displayAdminOrder17.tpl`
  - Hook: `displayAdminOrder` (für PrestaShop 1.7+).
  - Ausgabe: Ähnlich wie `displayAdminOrder16.tpl`, aber angepasst an das Layout der Bestelldetailseite des PrestaShop 1.7+ Back Office.
- `views/templates/hook/displayOrderDetail.tpl`
  - Hook: `displayOrderDetail` (Front-Office Kundenbestellhistorie).
  - Ausgabe: Zeigt die Nachnahmegebühr als Teil der Bestellübersicht an, wenn ein Kunde seine früheren Bestelldetails in seinem „Mein Konto“-Bereich ansieht.
- `views/templates/hook/payment.tpl`
  - Hook: `displayPaymentOptions` oder `paymentOptions`.
  - Ausgabe: Die Zahlungsoption „Nachnahme mit Gebühr“ auf der Checkout-Seite, einschließlich des dynamisch berechneten Gebührenbetrags.
- `views/templates/hook/pdf.tpl`
  - Hook: `displayPDFInvoice`.
  - Ausgabe: Die Nachnahmegebühr als Position auf der generierten PDF-Rechnung für die Bestellung.

#### **Front-Office-Templates (`views/templates/front/`)**

- `views/templates/front/validation.tpl`
  - Zweck: Dieses Template wird wahrscheinlich vom Front-Controller `validation.php` verwendet. Es könnte eine einfache Nachricht während des Zahlungsvalidierungsprozesses anzeigen oder als Weiterleitungsseite dienen.

### 4.7 Datenbankschema & Hooks-Map

#### **Datenbanktabellen**

- `ps_configuration`: Speichert alle allgemeinen Moduleinstellungen (z. B. `CODPRO_MOD_MAXCART_V`, `CODPRO_CHARGEP_V`, `CODPRO_FEETAX`).
- `ps_codpro_carrier_fees` (wahrscheinlich): Eine benutzerdefinierte Tabelle zum Speichern von spediteurspezifischen Nachnahmegebührenregeln.
  - Spalten: `id_codpro_carrier_fee`, `id_carrier`, `fee_type` (fest/prozentual), `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.
- `ps_codpro_range_fees` (wahrscheinlich): Eine benutzerdefinierte Tabelle zum Speichern von Bestellwert-bereichsbasierten Nachnahmegebührenregeln.
  - Spalten: `id_codpro_range_fee`, `min_value`, `max_value`, `fee_type`, `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.

#### **Registrierte Hooks-Tabelle**

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Im `<head>`-Bereich aller Seiten. | Zum Einbinden von Front-Office-CSS (`codpro.css`) und JS (`codpro-checkout.js`) auf relevanten Seiten (z. B. Checkout). |
| `displayPaymentOptions` | Front-Office | Während der Zahlungsmethodenauswahl im Checkout. | Zum Anzeigen von „Nachnahme mit Gebühr“ als Zahlungsoption, einschließlich der berechneten Gebühr. |
| `paymentOptions` | Front-Office | PrestaShop 1.6 Äquivalent von `displayPaymentOptions`. | Zum Anzeigen von „Nachnahme mit Gebühr“ als Zahlungsoption. |
| `paymentReturn` | Front-Office | Auf der Bestellbestätigungsseite nach der Zahlung. | Zum Anzeigen der Nachnahmegebühr-Details auf der Bestätigungsseite. |
| `displayPaymentReturn` | Front-Office | PrestaShop 1.6 Äquivalent von `paymentReturn`. | Zum Anzeigen der Nachnahmegebühr-Details auf der Bestätigungsseite. |
| `displayPDFInvoice` | Front-Office (PDF-Generierung) | Wenn eine PDF-Rechnung generiert wird. | Zum Hinzufügen der Nachnahmegebühr als Position auf der Rechnung. |
| `displayOrderDetail` | Front-Office (Mein Konto) | Wenn ein Kunde seine Bestelldetails ansieht. | Zum Anzeigen der Nachnahmegebühr in der Bestellhistorie des Kunden. |
| `displayAdminOrder` | Back-Office (Bestellansicht) | Wenn ein Administrator eine Bestellung im Back Office ansieht. | Zum Anzeigen der Nachnahmegebühr-Details in der Bestellübersicht für die Administratorprüfung. |
| `ActionAdminControllerSetMedia` | Back-Office (Admin-Seiten) | Bevor ein Admin-Controller seine Ansicht rendert. | Zum Einbinden von Back-Office-CSS (`admin_codpro.css`) und JS (`adminCodProCarriersFees.js`, `adminCodProDashboard.js`) auf den Admin-Seiten des Moduls. |
| `actionValidateOrder` | Back-Office (Bestellverarbeitung) | Nachdem eine Bestellung validiert wurde. | Um potenziell zusätzliche Aktionen oder Datenprotokollierungen im Zusammenhang mit Nachnahmebestellungen durchzuführen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu.

- **MyPresta.eu Bestellhistorie & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support:** <https://mypresta.eu/contact>
