---
title: "Nachnahme mit Bestellübersicht - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Nachnahme mit Bestellübersicht' von MyPresta.eu."
sidebar:
  label: "Nachnahme mit Bestellübersicht"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cash on delivery with order summary auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-order-summary.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/cash-on-delivery-with-order-summary/)
>
> ---


# Nachnahme mit Bestellübersicht

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten und die Gebühren für Ihre Nachnahme-Zahlungsmethode einrichten.

-   **Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach "Nachnahme mit Bestellübersicht" > Klicken Sie auf "Konfigurieren".

#### Allgemeine Einstellungen

1.  **Nachnahme für bestimmte Versanddienstleister deaktivieren**
    -   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Nachnahme-Zahlungsoption zu deaktivieren, wenn ein Kunde bestimmte Versanddienstleister wählt.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (für bestimmte Versanddienstleister angekreuzt):* Wenn ein Kunde einen der ausgewählten Versanddienstleister während des Checkouts wählt, wird die Nachnahme-Zahlungsoption nicht angezeigt.
        -   *Wenn deaktiviert (für alle Versanddienstleister nicht angekreuzt):* Nachnahme ist unabhängig vom gewählten Versanddienstleister verfügbar (es sei denn, es gelten andere Einschränkungen).
    -   **Empfohlener Wert:** Abhängig von Ihrer Versandlogistik. Wenn einige Versanddienstleister keine Nachnahme unterstützen oder übermäßige Gebühren verlangen, aktivieren Sie diese Option.
    -   **Händlerszenario / Beispiel:** Sie nutzen einen bestimmten Kurierdienst, der keine Barzahlungen abwickelt. Sie würden diesen Versanddienstleister in dieser Liste ankreuzen, um die Nachnahme für ihn zu deaktivieren.

2.  **Wie soll die Gebühr einbezogen werden?**
    -   **Was diese Einstellung bewirkt:** Legt fest, wie die Nachnahmegebühr berechnet und auf die Bestellung angewendet wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Zu den Versandkosten hinzufügen:* Die Nachnahmegebühr wird direkt zu den dem Kunden angezeigten Versandkosten hinzugefügt. Dies kann die Checkout-Anzeige vereinfachen, könnte aber die separate Nachnahmegebühr verschleiern.
        -   *Als separates Produkt hinzufügen:* Die Nachnahmegebühr erscheint als separate Position im Warenkorb und in der Bestellübersicht, oft als "Nachnahmegebühr" oder ähnlich bezeichnet. Dies bietet maximale Transparenz.
    -   **Empfohlener Wert:** "Als separates Produkt hinzufügen" für Klarheit und rechtliche Konformität, insbesondere in der EU.
    -   **Händlerszenario / Beispiel:** Um Kunden die genauen Kosten der Nachnahme klar anzuzeigen, würden Sie "Als separates Produkt hinzufügen" wählen.

3.  **Bestellstatus nach dem Kauf mit Nachnahme-Modul**
    -   **Was diese Einstellung bewirkt:** Legt den anfänglichen Status einer Bestellung fest, die mit der Nachnahme-Methode aufgegeben wurde.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf "Zahlung akzeptiert" gesetzt:* Die Bestellung wird sofort als bezahlt markiert, was irreführend sein könnte, da das Geld noch nicht eingezogen wurde.
        -   *Wenn auf "Warten auf Nachnahme-Validierung" (oder ähnlich) gesetzt:* Die Bestellung befindet sich in einem ausstehenden Zustand, was darauf hinweist, dass die Zahlung bei Lieferung erwartet wird. Dies ist im Allgemeinen sicherer und genauer.
    -   **Empfohlener Wert:** Ein ausstehender Status wie "Warten auf Nachnahme-Validierung" oder "Zahlung ausstehend", um den Zahlungsstatus genau widerzuspiegeln.
    -   **Händlerszenario / Beispiel:** Um zu vermeiden, eine Bestellung, die noch nicht bezahlt wurde, vorzeitig zu versenden, würden Sie dies auf einen ausstehenden Status setzen.

4.  **Zusätzliche Zusammenfassung vor der Bestätigung anzeigen**
    -   **Was diese Einstellung bewirkt:** Steuert, ob das Modul die spezielle Seite mit der Bestellübersicht vor der Bestätigung anzeigt. Dies ist die zentrale Konformitätsfunktion des Moduls.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Nach Auswahl der Nachnahme sehen Kunden eine detaillierte Zusammenfassung ihrer Bestellung, einschließlich aller Kosten, bevor sie auf den endgültigen Button "Bestellung bestätigen" klicken können.
        -   *Wenn deaktiviert:* Das Modul überspringt diese Übersichtsseite, und Kunden gelangen direkt zur Standard-PrestaShop-Bestellbestätigung (was in einigen Regionen möglicherweise nicht rechtlich konform ist).
    -   **Empfohlener Wert:** **Aktiviert**. Dies ist eine Schlüsselfunktion für die rechtliche Konformität und das Kundenvertrauen.
    -   **Händlerszenario / Beispiel:** Um die EU-Verbrauchergesetze einzuhalten, die eine klare Bestellübersicht vor der endgültigen Bestätigung erfordern, müssen Sie diese Einstellung **aktivieren**.

#### Warenkorbwert-Einschränkungen

5.  **Mindestwert des Warenkorbs**
    -   **Was diese Einstellung bewirkt:** Legt den Mindestgesamtwert fest, den eine Bestellung haben muss, damit die Nachnahme-Zahlungsoption verfügbar ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ein Wert festgelegt ist (z. B. 10,00):* Wenn der Gesamtbetrag des Warenkorbs des Kunden unter diesem Betrag liegt, wird die Nachnahme nicht als Zahlungsoption angeboten.
        -   *Wenn leer gelassen oder auf 0 gesetzt:* Es gibt keine Mindestwertbeschränkung für die Nachnahme.
    -   **Empfohlener Wert:** Legen Sie einen angemessenen Mindestwert fest, wenn die Betriebskosten für die Bearbeitung kleiner Nachnahmebestellungen zu hoch sind. Andernfalls lassen Sie das Feld leer.
    -   **Händlerszenario / Beispiel:** Wenn die Kosten für die Bearbeitung einer Nachnahmebestellung (Kuriergebühren, Verwaltungsaufwand) 5 € betragen, könnten Sie einen Mindestwarenkorbwert von 10 € festlegen, um die Rentabilität zu gewährleisten.

6.  **Höchstwert des Warenkorbs**
    -   **Was diese Einstellung bewirkt:** Legt den Höchstgesamtwert fest, den eine Bestellung haben kann, damit die Nachnahme-Zahlungsoption verfügbar ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ein Wert festgelegt ist (z. B. 500,00):* Wenn der Gesamtbetrag des Warenkorbs des Kunden diesen Betrag überschreitet, wird die Nachnahme nicht als Zahlungsoption angeboten.
        -   *Wenn leer gelassen oder auf 0 gesetzt:* Es gibt keine Höchstwertbeschränkung für die Nachnahme.
    -   **Empfohlener Wert:** Legen Sie einen Höchstwert fest, wenn Sie Ihr Risiko für sehr hochpreisige Bestellungen begrenzen möchten, die möglicherweise Betrug oder Nichtabholung unterliegen könnten. Andernfalls lassen Sie das Feld leer.
    -   **Händlerszenario / Beispiel:** Um das Risiko der Nichtzahlung bei sehr teuren Bestellungen zu mindern, könnten Sie einen maximalen Warenkorbwert von 200 € für die Nachnahme festlegen.

#### Nachnahmegebühren-Einstellungen

7.  **Nachnahmegebühr-Typ (Prozentsatz oder Betrag)**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob die Nachnahmegebühr ein fester Betrag oder ein Prozentsatz des Bestellwerts ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Prozentsatz:* Die Gebühr wird als Prozentsatz des Bestellwerts berechnet.
        -   *Betrag:* Die Gebühr ist ein fester monetärer Wert.
    -   **Empfohlener Wert:** Wählen Sie basierend auf Ihrer Kostenstruktur. Wenn Ihre Kosten mit dem Bestellwert skalieren, verwenden Sie einen Prozentsatz. Wenn es sich um eine pauschale Bearbeitungsgebühr handelt, verwenden Sie einen Betrag.
    -   **Händlerszenario / Beispiel:** Wenn Ihre Bank einen Prozentsatz des Transaktionswerts für die Bargeldabwicklung berechnet, würden Sie "Prozentsatz" wählen. Wenn Ihr Kurier eine Pauschalgebühr für die Nachnahme berechnet, würden Sie "Betrag" wählen.

8.  **Nachnahmegebühr-Wert (Prozentsatz)** (Erscheint, wenn oben "Prozentsatz" ausgewählt ist)
    -   **Was diese Einstellung bewirkt:** Der Prozentsatz, der als Nachnahmegebühr berechnet wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf 5 gesetzt:* Die Nachnahmegebühr beträgt 5 % des Bestellwerts.
    -   **Empfohlener Wert:** Ein Prozentsatz, der Ihre Kosten deckt, ohne Kunden abzuschrecken.
    -   **Händlerszenario / Beispiel:** Um eine 2%ige Bankgebühr für Bareinzahlungen zu decken, könnten Sie dies auf "2" setzen.

9.  **Nachnahmegebühr-Wert (Betrag)** (Erscheint, wenn oben "Betrag" ausgewählt ist)
    -   **Was diese Einstellung bewirkt:** Der feste monetäre Wert, der als Nachnahmegebühr berechnet wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf 2,50 gesetzt:* Die Nachnahmegebühr beträgt 2,50 € (oder Ihre Standardwährung) unabhängig vom Bestellwert.
    -   **Empfohlener Wert:** Ein fester Betrag, der Ihre pauschalen Bearbeitungskosten deckt.
    -   **Händlerszenario / Beispiel:** Wenn Ihr Kurierdienst eine feste Gebühr von 3 € für den Nachnahmeservice berechnet, würden Sie dies auf "3" setzen.

10. **Mindest-Nachnahmegebühr**
    -   **Was diese Einstellung bewirkt:** Legt einen Mindestbetrag für die Nachnahmegebühr fest, unabhängig von der prozentualen Berechnung.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf 1,00 gesetzt und der Prozentsatz 0,50 berechnet:* Die Gebühr beträgt 1,00.
        -   *Wenn auf 1,00 gesetzt und der Prozentsatz 2,00 berechnet:* Die Gebühr beträgt 2,00.
    -   **Empfohlener Wert:** Nützlich, wenn Sie auch bei kleinen Bestellungen einen Mindestkostenaufwand für die Nachnahme haben.
    -   **Händlerszenario / Beispiel:** Wenn 5 % einer 10 €-Bestellung nur 0,50 € betragen, Ihre Mindestbearbeitungskosten aber 1 € sind, würden Sie dies auf "1,00" setzen.

11. **Höchst-Nachnahmegebühr**
    -   **Was diese Einstellung bewirkt:** Legt einen Höchstbetrag für die Nachnahmegebühr fest, unabhängig von der prozentualen Berechnung.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf 10,00 gesetzt und der Prozentsatz 15,00 berechnet:* Die Gebühr beträgt 10,00.
        -   *Wenn auf 10,00 gesetzt und der Prozentsatz 5,00 berechnet:* Die Gebühr beträgt 5,00.
    -   **Empfohlener Wert:** Nützlich, um zu verhindern, dass die Nachnahmegebühr bei sehr großen Bestellungen übermäßig hoch wird.
    -   **Händlerszenario / Beispiel:** Um sicherzustellen, dass die Nachnahmegebühr bei großen Bestellungen nicht unerschwinglich wird, könnten Sie sie auf 15 € begrenzen.

12. **Steuer auf Nachnahmegebühr anwenden**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob die Nachnahmegebühr selbst der Umsatzsteuer unterliegt.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Sie können eine Steuerregel auswählen, die auf die Nachnahmegebühr angewendet wird.
        -   *Wenn deaktiviert:* Die Nachnahmegebühr ist steuerbefreit.
    -   **Empfohlener Wert:** Konsultieren Sie Ihre lokalen Steuergesetze. In vielen Regionen sind Zahlungsbearbeitungsgebühren steuerpflichtig.
    -   **Händlerszenario / Beispiel:** Wenn die Steuergesetze Ihres Landes vorschreiben, dass Sie Mehrwertsteuer auf Zahlungsdienstleistungsgebühren erheben müssen, würden Sie dies aktivieren und die entsprechende Steuerregel auswählen.

13. **Steuerregel für Nachnahmegebühr** (Erscheint, wenn "Steuer auf Nachnahmegebühr anwenden" aktiviert ist)
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl einer bestehenden Steuerregel aus Ihrem PrestaShop-Shop, die auf die Nachnahmegebühr angewendet wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Der ausgewählte Steuersatz wird auf die berechnete Nachnahmegebühr angewendet.
    -   **Empfohlener Wert:** Wählen Sie die Steuerregel, die den Zahlungsbearbeitungsgebühren in Ihrer Gerichtsbarkeit entspricht.
    -   **Händlerszenario / Beispiel:** Wenn Sie eine Steuerregel "MwSt 20%" haben, würden Sie diese hier auswählen, um 20% MwSt auf die Nachnahmegebühr anzuwenden.

#### Erweiterte Anzeigeeinstellungen

14. **CSS-Selektor für Warenkorb-Gesamtsumme**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den CSS-Selektor für das Element anzugeben, das den gesamten Warenkorbwert auf Ihrer Checkout-Seite anzeigt. Dies hilft dem Modul, die Gesamtsumme genau zu aktualisieren, wenn eine Nachnahmegebühr angewendet wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Wenn korrekt eingestellt, kann das Modul die Gesamtsumme auf der Checkout-Seite dynamisch aktualisieren, um die Nachnahmegebühr einzuschließen. Wenn falsch, wird die Gesamtsumme möglicherweise nicht aktualisiert, was zu Verwirrung führt.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben Anzeigeprobleme, bei denen die Gesamtsumme nicht aktualisiert wird. Falls erforderlich, konsultieren Sie den Entwickler Ihres Themes oder verwenden Sie die Browser-Entwicklertools, um den korrekten Selektor zu finden (z. B. `.cart-total-value`).
    -   **Händlerszenario / Beispiel:** Wenn Ihr Theme eine benutzerdefinierte Klasse wie `.mytheme-total-price` für die Warenkorb-Gesamtsumme verwendet, würden Sie diese hier eingeben.

15. **CSS-Selektor für Warenkorb-Zwischensumme**
    -   **Was diese Einstellung bewirkt:** Ähnlich wie bei der Warenkorb-Gesamtsumme gibt dies den CSS-Selektor für die Warenkorb-Zwischensumme an.
    -   **Auswirkung der Änderung dieser Einstellung:** Hilft dem Modul, die Zwischensummenanzeige korrekt zu identifizieren und potenziell zu aktualisieren.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, es treten Anzeigeprobleme auf.
    -   **Händlerszenario / Beispiel:** Wenn Ihr Theme ein spezifisches Element für die Zwischensumme hat, müssen Sie möglicherweise dessen Selektor hier eingeben.

16. **CSS-Selektor für Warenkorb-Versand**
    -   **Was diese Einstellung bewirkt:** Ähnlich wie bei der Warenkorb-Gesamtsumme gibt dies den CSS-Selektor für die Anzeige der Versandkosten an.
    -   **Auswirkung der Änderung dieser Einstellung:** Hilft dem Modul, die Anzeige der Versandkosten korrekt zu identifizieren und potenziell zu aktualisieren, insbesondere wenn die Nachnahmegebühr in den Versandkosten enthalten ist.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, es treten Anzeigeprobleme auf.
    -   **Händlerszenario / Beispiel:** Wenn Ihr Theme ein spezifisches Element für die Versandkosten hat, müssen Sie möglicherweise dessen Selektor hier eingeben.

17. **Nachnahme-Logo**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Hochladen eines benutzerdefinierten Logos, das neben der Nachnahme-Zahlungsoption während des Checkouts angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn hochgeladen:* Ein visuelles Symbol oder Logo wird angezeigt, wodurch die Nachnahme-Option prominenter und optisch ansprechender wird.
        -   *Wenn leer:* Es wird kein benutzerdefiniertes Logo angezeigt.
    -   **Empfohlener Wert:** Laden Sie ein kleines, klares Logo (z. B. ein Bargeldsymbol) hoch, um die Benutzererfahrung zu verbessern.
    -   **Händlerszenario / Beispiel:** Um die Nachnahme-Option hervorzuheben, könnten Sie ein kleines Bild von Banknoten oder Münzen hochladen.

#### Analyse-Einstellungen (Interne Modulnutzung)

Diese Einstellungen dienen typischerweise der internen Modulanalyse und erfordern in der Regel keine Intervention des Händlers.

18. **`CODPRO_ANALYTICS_DEFAULT_CHART`, `CODPRO_ANALYTICS_PERIOD`, `CODPRO_ANALYTICS_IMPACT_DAYS`, `CODPRO_ANALYTICS_CHART_WEEKS`, `CODPRO_ANALYTICS_CHART_MONTHS`**
    -   **Was diese Einstellungen bewirken:** Dies sind interne Konfigurationsschlüssel, die vom Modul für potenzielle zukünftige Analysefunktionen oder Dashboard-Anzeigen innerhalb der eigenen Administration des Moduls verwendet werden. Sie steuern, wie Daten für die Leistungsüberwachung gesammelt oder angezeigt werden könnten.
    -   **Auswirkung der Änderung dieser Einstellungen:** Es ist unwahrscheinlich, dass sie eine direkte, unmittelbare Auswirkung auf die Front-Office-Kundenerfahrung haben. Betrifft hauptsächlich potenzielle Back-Office-Berichte.
    -   **Empfohlener Wert:** Bei ihren Standardwerten belassen.
    -   **Händlerszenario / Beispiel:** Diese werden typischerweise nicht von Händlern angepasst.

### 2.2 Spezielle Admin-Bildschirme & Controller-Ansichten

Das Modul bietet zwei zusätzliche Administrationsbildschirme für eine granularere Kontrolle über Nachnahmegebühren, besonders nützlich für komplexe Versand- und Preisstrategien.

#### 2.2.1 AdminCodProCarriersFeesController: Versanddienstleister-spezifische Nachnahmegebühren

-   **Bildschirmname & Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach "Nachnahme mit Bestellübersicht" > Klicken Sie auf "Konfigurieren" > Suchen Sie nach einem Tab oder Link mit der Bezeichnung "Versanddienstleister-Gebühren" oder ähnlich (dies kann je nach PrestaShop-Version in die Hauptkonfiguration oder einen separaten Menüpunkt integriert sein).
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm präsentiert typischerweise ein Raster oder eine Tabelle, in der Sie verschiedene Nachnahmegebühren basierend auf dem ausgewählten Versanddienstleister definieren können. Sie können diese versanddienstleister-spezifischen Gebührenregeln hinzufügen, bearbeiten oder löschen.
    -   **Versanddienstleister-Auswahl:** Wählen Sie einen spezifischen Versanddienstleister.
    -   **Gebührentyp:** Wählen Sie, ob die Gebühr ein fester Betrag oder ein Prozentsatz ist.
    -   **Gebührenwert:** Geben Sie den Betrag oder Prozentsatz ein.
    -   **Steuerregel:** Wenden Sie eine spezifische Steuerregel auf die Nachnahmegebühr dieses Versanddienstleisters an.
-   **Auswirkung von Änderungen:** Wenn ein Kunde einen Versanddienstleister wählt, für den Sie hier eine spezifische Nachnahmegebühr definiert haben, überschreibt diese Gebühr die allgemeine Nachnahmegebühr, die in der Hauptmodulkonfiguration festgelegt wurde. Dies ermöglicht eine hochgradig angepasste Preisgestaltung.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
    1.  Greifen Sie auf diesen Bildschirm zu, wenn Sie unterschiedliche Nachnahmegebühren basierend auf dem Kurier, der das Paket liefert, berechnen müssen.
    2.  Klicken Sie auf "Neue Versanddienstleister-Gebühr hinzufügen" (oder ähnliche Schaltfläche).
    3.  Wählen Sie den Versanddienstleister, definieren Sie den Gebührentyp (Betrag/Prozentsatz), den Wert und die Steuerregel.
    4.  Speichern Sie Ihre Änderungen.
    5.  Überprüfen Sie die Liste, um sicherzustellen, dass alle versanddienstleister-spezifischen Gebühren korrekt eingestellt sind.
-   **Händlerszenario / Beispiel:** Ihr nationaler Postdienst berechnet eine Pauschale von 2 € für die Nachnahme, aber ein privater Expresskurier berechnet 3 % des Bestellwerts. Sie würden diesen Bildschirm verwenden, um diese unterschiedlichen Gebühren für jeden Versanddienstleister festzulegen.

#### 2.2.2 AdminCodProCarriersRangeFeesController: Versanddienstleister- & Bereichs-spezifische Nachnahmegebühren

-   **Bildschirmname & Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach "Nachnahme mit Bestellübersicht" > Klicken Sie auf "Konfigurieren" > Suchen Sie nach einem Tab oder Link mit der Bezeichnung "Bereichsgebühren" oder ähnlich.
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm bietet eine noch fortgeschrittenere Gebührenkontrolle. Sie können Nachnahmegebühren definieren, die nicht nur nach Versanddienstleister, sondern auch nach dem *Gesamtwert des Warenkorbs des Kunden* variieren. Dies wird oft als Raster dargestellt, in dem Sie Bereiche definieren (z. B. "Bestellwert von 0 € bis 50 €", "Bestellwert von 50 € bis 100 €").
    -   **Versanddienstleister-Auswahl:** Wählen Sie einen spezifischen Versanddienstleister.
    -   **Mindestbestellwert:** Die untere Grenze des Bestellwertbereichs.
    -   **Höchstbestellwert:** Die obere Grenze des Bestellwertbereichs.
    -   **Gebührentyp:** Fester Betrag oder Prozentsatz.
    -   **Gebührenwert:** Der Betrag oder Prozentsatz für diesen spezifischen Versanddienstleister und Bestellwertbereich.
    -   **Steuerregel:** Wenden Sie eine spezifische Steuerregel an.
-   **Auswirkung von Änderungen:** Diese bereichsbasierten Gebühren haben Vorrang vor der allgemeinen Nachnahmegebühr und den einfachen versanddienstleister-spezifischen Gebühren. Sie ermöglichen hochdynamische Preisstrategien.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
    1.  Verwenden Sie diesen Bildschirm für die komplexesten Nachnahmegebührenstrukturen.
    2.  Klicken Sie auf "Neue Bereichsgebühr hinzufügen" (oder ähnlich).
    3.  Wählen Sie den Versanddienstleister, definieren Sie den Mindest- und Höchstbestellwert für diese Regel.
    4.  Geben Sie den Gebührentyp, den Wert und die Steuerregel für diesen bestimmten Bereich an.
    5.  Speichern Sie und wiederholen Sie dies für alle notwendigen Bereiche und Versanddienstleister.
-   **Händlerszenario / Beispiel:** Für einen bestimmten Versanddienstleister könnten Sie eine Nachnahmegebühr von 3 € für Bestellungen unter 50 € berechnen, aber eine 2%ige Gebühr für Bestellungen zwischen 50 € und 200 € und eine Pauschalgebühr von 5 € für Bestellungen über 200 €. Dieser Bildschirm ermöglicht es Ihnen, solche gestaffelten Preise einzurichten.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| **Modulkonfiguration** | Nachnahme für bestimmte Versanddienstleister deaktivieren | Nein (alle aktiviert) | Beschränkt die Verfügbarkeit der Nachnahme nach gewähltem Versanddienstleister. |
| | Wie soll die Gebühr einbezogen werden? | Als separates Produkt hinzufügen | Legt fest, wie die Nachnahmegebühr im Warenkorb/in der Bestellung erscheint. "Separates Produkt" für Klarheit. |
| | Bestellstatus nach dem Kauf mit Nachnahme-Modul | Warten auf Nachnahme-Validierung | Legt den anfänglichen Bestellstatus fest; "Warten auf Nachnahme-Validierung" wird zur Genauigkeit empfohlen. |
| | Zusätzliche Zusammenfassung vor der Bestätigung anzeigen | Aktiviert | **KRITISCH:** Zeigt die rechtliche Zusammenfassung vor der Bestätigung an. **Aktiviert** für Konformität. |
| | Mindestwert des Warenkorbs | Leer / 0 | Mindestbestellwert für Nachnahme. Festlegen, wenn kleine Bestellungen unrentabel sind. |
| | Höchstwert des Warenkorbs | Leer / 0 | Höchstbestellwert für Nachnahme. Festlegen, um das Risiko bei großen Bestellungen zu mindern. |
| | Nachnahmegebühr-Typ | Betrag | Wählen Sie, ob die Gebühr fest oder prozentual ist. |
| | Nachnahmegebühr-Wert (Prozentsatz) | 0 | Prozentsatz des Bestellwerts für die Nachnahmegebühr. |
| | Nachnahmegebühr-Wert (Betrag) | 0 | Fester monetärer Betrag für die Nachnahmegebühr. |
| | Mindest-Nachnahmegebühr | 0 | Stellt sicher, dass eine Mindestgebühr erhoben wird, auch wenn der Prozentsatz niedrig ist. |
| | Höchst-Nachnahmegebühr | 0 | Begrenzt die Nachnahmegebühr, um zu verhindern, dass sie zu hoch wird. |
| | Steuer auf Nachnahmegebühr anwenden | Nein | Legt fest, ob Steuer auf die Nachnahmegebühr angewendet wird. Konsultieren Sie lokale Steuergesetze. |
| | Steuerregel für Nachnahmegebühr | (Keine) | Wählt die Steuerregel aus, wenn "Steuer anwenden" aktiviert ist. |
| | CSS-Selektor für Warenkorb-Gesamtsumme | Leer | Erweitert: CSS-Selektor für die Anzeige der Warenkorb-Gesamtsumme. Leer lassen, es sei denn, es gibt Probleme. |
| | CSS-Selektor für Warenkorb-Zwischensumme | Leer | Erweitert: CSS-Selektor für die Anzeige der Warenkorb-Zwischensumme. Leer lassen, es sei denn, es gibt Probleme. |
| | CSS-Selektor für Warenkorb-Versand | Leer | Erweitert: CSS-Selektor für die Anzeige der Versandkosten. Leer lassen, es sei denn, es gibt Probleme. |
| | Nachnahme-Logo | Leer | Laden Sie ein benutzerdefiniertes Logo für die Nachnahme-Zahlungsoption hoch. |
| **AdminCodProCarriersFees** | Versanddienstleister-spezifische Gebühren | N/A | Definieren Sie Nachnahmegebühren, die je nach Versanddienstleister variieren. |
| **AdminCodProCarriersRangeFees** | Versanddienstleister- & Bereichs-spezifische Gebühren | N/A | Definieren Sie Nachnahmegebühren, die je nach Versanddienstleister UND Bestellwertbereich variieren. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Nachnahme-Option wird Kunden nicht angezeigt.**
A1: Überprüfen Sie Folgendes:
    *   **Modul aktiviert:** Ist das Modul "Nachnahme mit Bestellübersicht" unter **Module > Modul-Manager** aktiviert?
    *   **Zahlungsbeschränkungen:** Gehen Sie zu **Shop-Parameter > Bestellungen > Zahlungen** (oder **Zahlung > Präferenzen** in älteren Versionen). Stellen Sie sicher, dass "Nachnahme mit Bestellübersicht" nicht durch Kundengruppe, Währung oder Land eingeschränkt ist.
    *   **Versanddienstleister-Beschränkungen:** Überprüfen Sie in der Modulkonfiguration "Nachnahme für bestimmte Versanddienstleister deaktivieren". Ist der vom Kunden gewählte Versanddienstleister versehentlich angekreuzt?
    *   **Warenkorbwert-Beschränkungen:** Überprüfen Sie "Mindestwert des Warenkorbs" und "Höchstwert des Warenkorbs" in der Modulkonfiguration. Fällt der Warenkorb des Kunden innerhalb dieser Grenzen?
    *   **Geografische Zonen:** Stellen Sie sicher, dass das Modul für das Land des Kunden unter **Shop-Parameter > Bestellungen > Zahlungen > Beschränkungen nach Zone/Land** aktiviert ist.

**F2: Die Nachnahmegebühr wird nicht angezeigt oder nicht korrekt berechnet.**
A2:
    *   **Gebühreneinstellungen:** Überprüfen Sie Ihre Einstellungen für "Nachnahmegebühr-Typ" (Prozentsatz/Betrag) und "Nachnahmegebühr-Wert" in der Hauptmodulkonfiguration.
    *   **Versanddienstleister-/Bereichsgebühren:** Wenn Sie `AdminCodProCarriersFees` oder `AdminCodProCarriersRangeFees` verwenden, stellen Sie sicher, dass die Regeln für den spezifischen Versanddienstleister und den Bestellwert korrekt definiert sind. Diese spezifischen Regeln überschreiben die allgemeinen Einstellungen.
    *   **Steuerregeln:** Wenn "Steuer auf Nachnahmegebühr anwenden" aktiviert ist, stellen Sie sicher, dass eine gültige Steuerregel ausgewählt ist.
    *   **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Parameter > Performance > Cache leeren**). Manchmal können alte Daten die Aktualisierung von Gebühren verhindern.

**F3: Die Seite mit der Zusammenfassung vor der Bestätigung wird nicht angezeigt, oder die Bestellung geht direkt zur Bestätigung.**
A3:
    *   **Einstellung "Zusätzliche Zusammenfassung vor der Bestätigung anzeigen":** Stellen Sie in der Hauptkonfiguration des Moduls sicher, dass diese Einstellung **Aktiviert** ist. Dies ist entscheidend, damit die Übersichtsseite angezeigt wird.
    *   **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können einige stark angepasste Themes stören. Wenn die Übersichtsseite immer noch nicht angezeigt wird, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um einen Theme-Konflikt auszuschließen. Wenn es mit dem Standard-Theme funktioniert, wenden Sie sich an Ihren Theme-Entwickler oder einen PrestaShop-Experten.

**F4: Die Nachnahmegebühr wird nicht auf der PDF-Rechnung angezeigt.**
A4:
    *   **Modul ist aktiv:** Stellen Sie sicher, dass das Modul aktiviert ist.
    *   **Rechnungserstellung:** Erstellen Sie die PDF-Rechnung für eine Bestellung, die mit Nachnahme aufgegeben wurde, *nachdem* das Modul korrekt konfiguriert wurde, neu. Alte Rechnungen spiegeln möglicherweise keine neuen Einstellungen wider.
    *   **PrestaShop-Version:** Stellen Sie sicher, dass Ihre PrestaShop-Version vollständig unterstützt wird. Obwohl das Modul auf breite Kompatibilität abzielt, können sehr alte oder sehr neue Versionen geringfügige Anzeigefehler aufweisen.

**F5: Wie ändere ich den Text "Nachnahme" oder die Gebührenbeschreibung?**
A5:
    *   **Übersetzungen:** Gehen Sie zu **International > Übersetzungen**. Wählen Sie "Übersetzungen installierter Module", wählen Sie Ihr Theme und dann "Nachnahme mit Bestellübersicht". Sie können dann alle übersetzbaren Zeichenfolgen, die vom Modul verwendet werden, finden und ändern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul "Nachnahme mit Bestellübersicht" (`codpro`) ist ein Standard-PrestaShop-Zahlungsmodul, das dem MVC-Muster (Model-View-Controller) folgt. Es erweitert `PaymentModule` und nutzt verschiedene PrestaShop-Hooks, um seine Zahlungsoption einzufügen, die Zusammenfassung vor der Bestätigung anzuzeigen und den Bestellstatus sowie die Gebühren zu verwalten. Es verwendet in `ps_configuration` gespeicherte Konfigurationswerte für seine Einstellungen und enthält benutzerdefinierte Admin-Controller für die erweiterte Gebührenverwaltung. Das Modul berechnet und zeigt Nachnahmegebühren dynamisch an und integriert sie in den Warenkorb und die Bestellsummen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller
-   `controllers/front/index.php`
    *   **Klassenname:** `CodProIndexModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dieser Controller könnte ein Platzhalter sein oder die anfängliche Weiterleitung für die Front-Office-Komponenten des Moduls handhaben. Angesichts des `validation.php`-Controllers hat `index.php` möglicherweise keine direkte benutzerseitige Route, könnte aber für interne Modullogik oder Weiterleitungen verwendet werden.
-   `controllers/front/validation.php`
    *   **Klassenname:** `CodProValidationModuleFrontController`
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dies ist der kritische Controller für die Verarbeitung der endgültigen Bestellbestätigung. Er empfängt die POST-Daten von der Seite mit der Zusammenfassung vor der Bestätigung, validiert die Bestellung, erstellt die Bestellung in PrestaShop und leitet den Kunden zur Bestellbestätigungsseite (`paymentReturn`) weiter. Er verarbeitet die Logik zur Anwendung der Nachnahmegebühr auf die Bestellung.

#### Back-Office-Admin-Controller
-   `controllers/admin/AdminCodProCarriersFees.php`
    *   **Klassenname:** `AdminCodProCarriersFeesController`
    *   **Elternklasse:** `ModuleAdminController`
    *   **Tab-Name:** Wahrscheinlich ein Unter-Tab unter der Hauptkonfiguration des Moduls oder ein benutzerdefinierter Menüeintrag.
    *   **Verwaltete Entität:** Verwaltet Konfigurationseinträge im Zusammenhang mit versanddienstleister-spezifischen Nachnahmegebühren.
    *   **Verantwortlichkeit:** Bietet die Schnittstelle (eine `HelperList` oder `HelperForm` basierend auf `AdminController`-Mustern) für Administratoren, um Nachnahmegebühren zu definieren, zu bearbeiten und zu löschen, die spezifisch für einzelne Versanddienstleister sind. Es verarbeitet CRUD-Operationen für diese Gebührenregeln.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    *   **Klassenname:** `AdminCodProCarriersRangeFeesController`
    *   **Elternklasse:** `ModuleAdminController`
    *   **Tab-Name:** Wahrscheinlich ein Unter-Tab unter der Hauptkonfiguration des Moduls.
    *   **Verwaltete Entität:** Verwaltet Einträge in der Tabelle `codprototal` (oder ähnlich, basierend auf den Konfigurationsschlüsseln `CODPRO_MOD_MAXCART_V` und `CODPRO_MOD_MINCART_V`).
    *   **Verantwortlichkeit:** Bietet die Schnittstelle für Administratoren, um Nachnahmegebühren zu definieren, zu bearbeiten und zu löschen, die sowohl vom ausgewählten Versanddienstleister als auch vom Gesamtwert des Warenkorbs des Kunden (d.h. bereichsbasierte Gebühren) abhängen. Es verarbeitet CRUD-Operationen für diese komplexen Gebührenregeln.
-   `controllers/admin/index.php`
    *   **Klassenname:** (Keine typische Controller-Klasse, normalerweise eine Weiterleitung oder Sicherheitsmaßnahme)
    *   **Elternklasse:** N/A
    *   **Verantwortlichkeit:** Oft eine Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen zu verhindern oder zur Hauptmodulkonfiguration umzuleiten. Es enthält typischerweise ein einfaches `header('Location: ../../index.php?controller=AdminModules&token=...')` oder `die('Forbidden');`.

### 4.3 Kernklassen & Modelle (`classes/`)
Die bereitgestellten Modulinformationen zeigen keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass die Kernlogik des Moduls, die Datenverarbeitung und möglicherweise `ObjectModel`-Definitionen (falls benutzerdefinierte Tabellen über `ps_configuration` hinaus verwendet werden) direkt in der Hauptdatei `codpro.php` gekapselt oder über Standard-PrestaShop `ObjectModel`s wie `Order` und `Cart` gehandhabt werden.

### 4.4 JavaScript-Assets (`views/js/`)

-   `codpro/views/js/adminCodProCarriersFees.js`
    *   **Geltungsbereich:** Back-Office (AdminCodProCarriersFeesController)
    *   **Verantwortlichkeit:** Behandelt wahrscheinlich dynamische Interaktionen auf der Administrationsseite für versanddienstleister-spezifische Gebühren. Dies könnte AJAX-Aufrufe zum Hinzufügen/Bearbeiten von Gebühren, Formularvalidierung oder die Aktualisierung der Anzeige der Gebührenliste umfassen.
-   `codpro/views/js/adminCodProDashboard.js`
    *   **Geltungsbereich:** Back-Office (potenziell die Hauptmodulkonfigurationsseite, wenn sie Analysen enthält)
    *   **Verantwortlichkeit:** Angesichts der `CODPRO_ANALYTICS_`-Konfigurationsschlüssel ist dieses Skript wahrscheinlich für das Rendern von Diagrammen, Grafiken oder anderen Analysedaten im Zusammenhang mit Nachnahmebestellungen innerhalb der Back-Office-Oberfläche des Moduls verantwortlich. Es könnte eine Diagrammbibliothek (z. B. Chart.js) verwenden und AJAX-Anfragen zum Abrufen von Daten stellen.
-   `codpro/views/js/codpro-checkout.js`
    *   **Geltungsbereich:** Front-Office (Checkout-Seite)
    *   **Verantwortlichkeit:** Dies ist ein entscheidendes Skript für die Front-Office-Erfahrung. Es überwacht Änderungen im Checkout-Prozess (z. B. Auswahl der Nachnahme als Zahlungsmethode, Änderung des Versanddienstleisters, Aktualisierung der Warenkorbmenge). Es aktualisiert dynamisch die Anzeigen für Warenkorb-Gesamtsumme, Zwischensumme und Versandkosten (unter Verwendung der in der Modulkonfiguration definierten CSS-Selektoren), um die berechnete Nachnahmegebühr widerzuspiegeln. Es könnte auch die Weiterleitung zur Seite mit der Zusammenfassung vor der Bestätigung handhaben.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `codpro/views/css/admin_codpro.css`
    *   **Geltungsbereich:** Back-Office (Admin-Seiten im Zusammenhang mit dem Modul)
    *   **Verantwortlichkeit:** Bietet Styling für die Konfigurationsformulare, Listen und potenziell benutzerdefinierte Dashboard-Elemente des Moduls innerhalb des PrestaShop Back Office. Gewährleistet eine konsistente und benutzerfreundliche Admin-Oberfläche.
    *   **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Elemente innerhalb der `HelperForm`- oder `HelperList`-Templates des Moduls oder auf benutzerdefinierte Elemente ab, die spezifisch für die Admin-Ansichten des Moduls sind.
-   `codpro/views/css/codpro.css`
    *   **Geltungsbereich:** Front-Office (Checkout-Seite, Zusammenfassung vor der Bestätigung, Bestelldetails)
    *   **Verantwortlichkeit:** Gestaltet die Anzeige der Nachnahme-Zahlungsoption, der Seite mit der Zusammenfassung vor der Bestätigung und der Anzeige der Nachnahmegebühr auf Bestelldetailseiten und Rechnungen. Stellt sicher, dass die Elemente des Moduls visuell in das Theme des Shops integriert sind.
    *   **Wichtige CSS-Klassenselektoren:** Zielt auf Elemente wie den Nachnahme-Zahlungsoptionsblock, die Zusammenfassungstabelle, Gebührenpositionen und potenziell benutzerdefinierte Warnungen oder Nachrichten ab, die vom Modul eingeführt wurden. Entwickler können diese in der `custom.css` ihres Themes oder durch die Verwendung spezifischerer Selektoren überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)
-   `codpro/views/templates/hook/confirmation.tpl`
    *   **Hook:** `displayPaymentReturn`
    *   **Ausgabe:** Inhalt, der auf der Bestellbestätigungsseite nach einer erfolgreichen Nachnahmebestellung angezeigt wird. Kann eine Nachricht enthalten, die den Kunden an die Barzahlung bei Lieferung erinnert.
-   `codpro/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook:** `displayAdminOrder` (für PrestaShop 1.6.x)
    *   **Ausgabe:** Fügt spezifische Informationen zur Nachnahme (z. B. Gebührendetails) zur Bestellansichtsseite im PrestaShop 1.6 Back Office hinzu.
-   `codpro/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook:** `displayAdminOrder` (für PrestaShop 1.7.x, 8.x, 9.x)
    *   **Ausgabe:** Ähnlich wie `displayAdminOrder16.tpl`, aber angepasst für die PrestaShop 1.7+ Back Office Bestellansicht, Anzeige von Nachnahme-Zahlungsdetails.
-   `codpro/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook:** `displayOrderDetail`
    *   **Ausgabe:** Zeigt Nachnahme-spezifische Informationen (z. B. die Gebührenaufschlüsselung) auf der Bestelldetailseite des Kunden im Front Office an.
-   `codpro/views/templates/hook/payment.tpl`
    *   **Hook:** `paymentOptions` oder `displayPaymentOptions`
    *   **Ausgabe:** Rendert den "Nachnahme"-Zahlungsoptionsblock auf der Checkout-Seite, einschließlich des Modul-Logos und jeder angezeigten Gebühr.
-   `codpro/views/templates/hook/pdf.tpl`
    *   **Hook:** `displayPDFInvoice`
    *   **Ausgabe:** Fügt die Nachnahmegebühr als Position oder Zusammenfassung in die generierten PDF-Rechnungen ein.

#### Front-Office-Templates (`views/templates/front/`)
-   `codpro/views/templates/front/validation.tpl`
    *   **Ausgabe:** Dies ist das Template für die entscheidende Seite mit der Bestellübersicht vor der Bestätigung. Es zeigt die vollständige Warenkorbzusammenfassung, die Lieferadresse, die Gesamtkosten (einschließlich Nachnahmegebühr) und den endgültigen Button "Bestellung bestätigen" an. Dieses Template wird vom Front-Controller `validation.php` gerendert.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen
Das Modul verwendet hauptsächlich die Standardtabelle `ps_configuration`, um seine Einstellungen zu speichern (z. B. `CODPRO_MOD_MAXCART`, `CODPRO_FEEPAY`, `CODPRO_CHARGEP_V` usw.).

Basierend auf dem `AdminCodProCarriersRangeFeesController`, der die Entität `codprototal` verwaltet, ist es sehr wahrscheinlich, dass das Modul eine benutzerdefinierte Datenbanktabelle erstellt, die wahrscheinlich `ps_codprototal` (oder ähnlich, nach der PrestaShop-Präfixkonvention `ps_`) benannt ist.
-   **`ps_codprototal` (Wahrscheinliche Tabelle):**
    *   **Zweck:** Speichert die bereichsbasierten Nachnahmegebührenregeln, die Versanddienstleister, Mindest-/Höchst-Warenkorbwerte, Gebührenbeträge/-prozentsätze und Steuerregeln verknüpfen.
    *   **Wahrscheinliche Felder:** `id_codprototal` (PK), `id_carrier`, `min_total`, `max_total`, `fee_type` (z. B. 'amount', 'percentage'), `fee_value`, `id_tax_rule`.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Zum Einbinden der CSS/JS-Assets des Moduls (z. B. `codpro-checkout.js`, `codpro.css`) auf relevanten Front-Office-Seiten. |
| `paymentOptions` | Während des Checkout-Prozesses, wenn Zahlungsoptionen aufgelistet werden. | Zum Einfügen der "Nachnahme"-Zahlungsoption in die Liste. |
| `displayPaymentOptions` | (Alias oder Alternative zu `paymentOptions` für einige Versionen) | Zum Einfügen der "Nachnahme"-Zahlungsoption in die Liste. |
| `paymentReturn` | Auf der Bestellbestätigungsseite nach einer erfolgreichen Bestellung. | Zum Anzeigen einer Bestätigungsnachricht, die spezifisch für Nachnahmebestellungen ist. |
| `displayAdminOrder` | Auf der Bestelldetailseite im PrestaShop Back Office. | Zum Anzeigen von Nachnahmegebühren-Details und Zahlungsmethodeninformationen für den Administrator. |
| `displayOrderDetail` | Auf der Bestelldetailseite des Kunden im Front Office. | Zum Anzeigen von Nachnahmegebühren-Details für den Kunden. |
| `displayPDFInvoice` | Wenn eine PDF-Rechnung generiert wird. | Um sicherzustellen, dass die Nachnahmegebühr korrekt in der Rechnung enthalten und angezeigt wird. |
| `ActionAdminControllerSetMedia` | Wenn ein Admin-Controller initialisiert wird und seine Medien-Assets gesetzt werden. | Zum Einbinden der admin-spezifischen CSS/JS-Assets des Moduls (z. B. `admin_codpro.css`, `adminCodProCarriersFees.js`, `adminCodProDashboard.js`). |

## 5. Offizieller Support & Updates
Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Entwickler-Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Stellen Sie sicher, dass Sie immer die Version des Moduls verwenden, die mit Ihrer spezifischen PrestaShop-Installation kompatibel ist.
