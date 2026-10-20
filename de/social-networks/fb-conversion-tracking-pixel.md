---
title: "Fb Conversion Tracking Pixel – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Fb Conversion Tracking Pixel“ von MyPresta.eu."
sidebar:
  label: "Fb Conversion Tracking Pixel – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Fb conversion tracking pixel auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/fb-conversion-tracking-pixel.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/fb-conversion-tracking-pixel/)
>
> ---


# Fb Conversion Tracking Pixel

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind für die korrekte Funktion des Moduls erforderlich, insbesondere für die Conversions API (CAPI)-Funktionen. Diese sind typischerweise in allen modernen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation landen Sie auf der Hauptkonfigurationsseite. Hier verbinden Sie Ihren Shop mit Facebook und passen an, wie Ereignisse verfolgt werden.

#### Registerkarte Allgemeine Einstellungen

- **Pixel-ID(s):**

  - **Was diese Einstellung bewirkt:** Dies ist die eindeutige Kennung für Ihren Facebook Pixel. Sie finden diese in Ihrem Facebook Business Manager oder Events Manager. Sie können mehrere Pixel-IDs durch Kommas getrennt eingeben, wenn Sie mehrere Pixel verwalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Das Modul bettet den Facebook Pixel-Code in das Front Office Ihres Shops ein und sendet Daten an die angegebene(n) Pixel-ID(s).
    - *Wenn leer:* Es findet kein Facebook Pixel Tracking statt.
  - **Empfohlener Wert:** Ihre primäre Facebook Pixel-ID.
  - **Händlerszenario / Beispiel:** Sie haben einen Hauptpixel für Ihre Marke und einen sekundären Pixel für eine bestimmte Produktlinie. Geben Sie beide hier ein: `1234567890,9876543210`.
- **CAPI-Zugriffstoken:**

  - **Was diese Einstellung bewirkt:** Dieses Token aktiviert die Facebook Conversions API (CAPI), die Konversionsdaten direkt von Ihrem Server an Facebook sendet und Browserbeschränkungen (wie Adblocker oder Cookie-Einschränkungen) umgeht. Dies verbessert die Datengenauigkeit.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Das Modul versucht, serverseitige Ereignisse über CAPI an Facebook zu senden, zusätzlich zu oder anstelle von browserseitigen Pixel-Ereignissen, abhängig von Ihren anderen Einstellungen.
    - *Wenn leer:* Es findet nur browserseitiges Pixel-Tracking statt (wenn Pixel-ID festgelegt ist).
  - **Empfohlener Wert:** Es wird dringend empfohlen, CAPI für eine bessere Datengenauigkeit zu verwenden. Generieren Sie dieses Token in Ihrem Facebook Events Manager.
  - **Händlerszenario / Beispiel:** Sie möchten maximale Datengenauigkeit für Ihre Kaufereignisse gewährleisten, auch wenn Kunden Adblocker verwenden. Sie generieren ein Zugriffstoken im Facebook Events Manager und fügen es hier ein.
- **Test-Ereigniscode:**

  - **Was diese Einstellung bewirkt:** Dieser Code wird verwendet, um Ihr CAPI-Setup im Facebook Events Manager zu testen. Wenn er eingegeben wird, sendet das Modul Testereignisse, sodass Sie überprüfen können, ob Ihr serverseitiges Tracking korrekt funktioniert.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* CAPI-Ereignisse enthalten diesen Testcode und sind im Tab „Test-Ereignisse“ des Facebook Events Managers sichtbar.
    - *Wenn leer:* CAPI-Ereignisse werden als Live-Ereignisse gesendet.
  - **Empfohlener Wert:** Nur verwenden, wenn Sie Ihr CAPI-Setup aktiv testen. Entfernen Sie ihn, sobald der Test abgeschlossen ist.
  - **Händlerszenario / Beispiel:** Sie haben CAPI gerade eingerichtet und möchten bestätigen, dass Daten gesendet werden. Sie kopieren den Testcode aus dem Facebook Events Manager, fügen ihn hier ein, führen einen Testkauf auf Ihrer Website durch und überprüfen dann den Tab „Test-Ereignisse“ in Facebook.
- **Zustimmungsmodus:**

  - **Was diese Einstellung bewirkt:** Diese Option integriert sich in die Cookie-Zustimmungslösung Ihres Shops (z. B. DSGVO-Module). Sie bestimmt, ob Facebook Pixel-Ereignisse nur ausgelöst werden, nachdem ein Kunde seine Zustimmung gegeben hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Pixel-Ereignisse werden nur ausgelöst, wenn der Kunde Cookies akzeptiert hat.
    - *Wenn deaktiviert:* Pixel-Ereignisse werden unabhängig von der Cookie-Zustimmung ausgelöst (mit Vorsicht verwenden, abhängig von lokalen Datenschutzgesetzen).
  - **Empfohlener Wert:** „Ja“, wenn Sie in Regionen mit strengen Datenschutzgesetzen (wie der DSGVO in Europa) tätig sind.
  - **Händlerszenario / Beispiel:** Ihr Shop richtet sich an Kunden in der EU. Sie aktivieren diese Einstellung, um die DSGVO einzuhalten und sicherzustellen, dass Pixeldaten nur von Benutzern gesammelt werden, die der Cookie-Nutzung ausdrücklich zustimmen.
- **Bezahlte Status:**

  - **Was diese Einstellung bewirkt:** Wählt aus, welche Bestellstatus in PrestaShop ein „Purchase“-Ereignis an Facebook auslösen sollen. Typischerweise gehören dazu Status wie „Zahlung akzeptiert“ oder „Geliefert“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgewählt:* Bestellungen, die diese Status erreichen, senden ein „Purchase“-Ereignis an Facebook.
    - *Wenn nicht ausgewählt:* Bestellungen senden kein „Purchase“-Ereignis, wenn sie diese Status erreichen.
  - **Empfohlener Wert:** Wählen Sie alle Status aus, die tatsächlich eine abgeschlossene und bezahlte Bestellung darstellen.
  - **Händlerszenario / Beispiel:** Sie betrachten eine Bestellung als „bezahlt“, wenn sie „Zahlung akzeptiert“ und „Versandt“ ist. Sie wählen beide Status aus.
- **Rückerstattungs-/Stornierungsstatus:**

  - **Was diese Einstellung bewirkt:** Wählt aus, welche Bestellstatus eine Rückerstattung oder Stornierung anzeigen. Dies ermöglicht es dem Modul, potenziell ein „Refund“- oder „Cancel“-Ereignis zu senden (falls von der Facebook-API und der Modulversion unterstützt) oder falsche positive Kaufverfolgungen zu verhindern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgewählt:* Das Modul erkennt diese Bestellungen als Nicht-Kauf oder erstattet.
    - *Wenn nicht ausgewählt:* Diese Bestellungen könnten immer noch als Käufe gezählt werden, wenn sie zuvor einen „bezahlten Status“ erreicht haben.
  - **Empfohlener Wert:** Wählen Sie Status wie „Storniert“, „Erstattet“, „Zahlungsfehler“.
  - **Händlerszenario / Beispiel:** Ein Kunde storniert eine Bestellung. Sie möchten sicherstellen, dass dies nicht als erfolgreicher Kauf gezählt wird. Sie wählen hier „Storniert“ und „Erstattet“ aus.

#### Registerkarte Erweiterte Einstellungen

- **CSS-Selektor für „In den Warenkorb legen“:**

  - **Was diese Einstellung bewirkt:** Dies ist eine technische Einstellung, die dem Modul hilft, die Schaltfläche „In den Warenkorb legen“ auf Ihren Produktseiten zu identifizieren. Wenn Ihr Theme eine nicht standardmäßige Schaltfläche verwendet, müssen Sie möglicherweise deren CSS-Selektor angeben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn korrekt:* Das „AddToCart“-Ereignis wird zuverlässig ausgelöst, wenn ein Kunde auf die Schaltfläche klickt.
    - *Wenn falsch oder leer (und die automatische Erkennung fehlschlägt):* Das „AddToCart“-Ereignis wird möglicherweise nicht ausgelöst, was zu fehlenden Daten führt.
  - **Empfohlener Wert:** Zuerst leer lassen; das Modul erkennt oft automatisch. Wenn „AddToCart“-Ereignisse fehlen, wenden Sie sich an Ihren Theme-Entwickler oder verwenden Sie den Browser-Inspektor, um den korrekten CSS-Selektor zu finden (z. B. `.add-to-cart-button`).
  - **Händlerszenario / Beispiel:** Ihr benutzerdefiniertes Theme hat eine einzigartige Schaltfläche „In den Warenkorb legen“. Sie inspizieren die Schaltfläche in Ihrem Browser und stellen fest, dass ihre Klasse `my-custom-add-button` ist. Sie geben hier `.my-custom-add-button` ein.
- **CSS-Selektor für Produktpreis:**

  - **Was diese Einstellung bewirkt:** Ähnlich wie der „In den Warenkorb legen“-Selektor hilft dies dem Modul, den Produktpreis auf der Seite genau zu finden, insbesondere bei dynamischen Preisen oder spezifischen Theme-Layouts.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn korrekt:* Der „value“-Parameter für Ereignisse wie „ViewContent“ und „AddToCart“ spiegelt den Produktpreis genau wider.
    - *Wenn falsch oder leer (und die automatische Erkennung fehlschlägt):* Der „value“-Parameter könnte fehlen oder falsch sein, was die Anzeigenoptimierung beeinträchtigt.
  - **Empfohlener Wert:** Zuerst leer lassen. Wenn die Preiswerte im Facebook Events Manager falsch sind, finden Sie den korrekten CSS-Selektor (z. B. `.current-price span[itemprop="price"]`).
  - **Händlerszenario / Beispiel:** Ihre Produktseite zeigt Preise auf nicht standardmäßige Weise an. Sie identifizieren den CSS-Selektor für das Preiselement, um sicherzustellen, dass Facebook den korrekten Wert erhält.
- **Produktidentifikation:**

  - **Was diese Einstellung bewirkt:** Bestimmt, welche Produktkennung (ID) Ihr Shop an Facebook sendet. Optionen umfassen typischerweise `ID` (PrestaShops interne Produkt-ID), `Reference` (Ihre Produkt-SKU) oder `EAN13` / `UPC` (Barcode-Nummern). Dies ist entscheidend für die Zuordnung von Produkten in Ihrem Facebook-Katalog.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn festgelegt:* Facebook erhält den gewählten ID-Typ, der mit den IDs in Ihrem Facebook-Produktkatalog übereinstimmen sollte, damit dynamische Anzeigen funktionieren.
    - *Wenn nicht mit Ihrem Katalog übereinstimmend:* Dynamische Anzeigen zeigen möglicherweise nicht die richtigen Produkte an oder werden überhaupt nicht angezeigt.
  - **Empfohlener Wert:** Wählen Sie die ID, die Sie konsistent in Ihrem Facebook-Produktkatalog verwenden. `Reference` (SKU) ist oft eine gute Wahl, wenn sie eindeutig ist.
  - **Händlerszenario / Beispiel:** Ihr Facebook-Produktkatalog verwendet die SKU Ihres Produkts als eindeutige Kennung. Sie wählen hier „Reference“, um eine perfekte Übereinstimmung zu gewährleisten.
- **Trennzeichen:**

  - **Was diese Einstellung bewirkt:** Wenn Sie eine Kombination aus Produkt-ID und Attribut-ID verwenden (z. B. für verschiedene Größen/Farben), definiert dies das Zeichen, das zur Trennung im Facebook-ID verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn festgelegt:* Die an Facebook gesendete Produkt-ID lautet `ProductID` + `Separator` + `AttributeID`.
    - *Wenn leer:* Es wird möglicherweise nur die Basis-Produkt-ID gesendet, was potenziell Probleme beim Tracking spezifischer Produktvarianten verursachen kann.
  - **Empfohlener Wert:** Ein gängiges Trennzeichen wie `-` oder `_`.
  - **Händlerszenario / Beispiel:** Sie verkaufen ein T-Shirt (ID 123) in verschiedenen Größen (Attribut-ID 10 für S, 11 für M). Wenn Sie das Trennzeichen auf `-` setzen, erhält Facebook `123-10` für ein kleines T-Shirt.
- **Produkt-ID-Präfix / Produkt-ID-Suffix:**

  - **Was diese Einstellung bewirkt:** Ermöglicht das Hinzufügen von Text vor oder nach der an Facebook gesendeten Produkt-ID. Dies ist nützlich, wenn Ihre Facebook-Produktkatalog-IDs ein bestimmtes Format haben, das von Ihren PrestaShop-IDs abweicht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn festgelegt:* Die endgültige an Facebook gesendete Produkt-ID lautet `Prefix` + `ProductID` + `Suffix`.
    - *Wenn leer:* Es wird nur die rohe Produkt-ID (und ggf. Trennzeichen/Attribut-ID) gesendet.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Ihr Facebook-Produktkatalog erfordert dies.
  - **Händlerszenario / Beispiel:** Ihr Facebook-Produktkatalog erfordert, dass alle Produkt-IDs mit „PS\_“ beginnen. Sie geben `PS_` in das Feld „Produkt-ID-Präfix“ ein.
- **Zielwährung:**

  - **Was diese Einstellung bewirkt:** Gibt die Währung an, in der Ereigniswerte (wie der Kaufbetrag) an Facebook gesendet werden. Dies ist entscheidend für eine genaue Berichterstattung und Anzeigenoptimierung, insbesondere für Shops mit mehreren Währungen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn festgelegt:* Alle Ereigniswerte werden in diese Zielwährung umgerechnet und gesendet.
    - *Wenn leer:* Das Modul versucht, die Währung des aktuellen Shop-Kontextes oder die vom Kunden ausgewählte Währung zu verwenden.
  - **Empfohlener Wert:** Ihre primäre Werbewährung (z. B. USD, EUR).
  - **Händlerszenario / Beispiel:** Ihr Shop verkauft in EUR, USD und GBP, aber alle Ihre Facebook-Anzeigen werden in USD verwaltet. Sie stellen „Zielwährung“ auf „USD“ ein, um sicherzustellen, dass alle Konversionswerte konsistent in USD gemeldet werden.

#### Registerkarte Einstellungen zur Ereignisverfolgung

Dieser Abschnitt ermöglicht es Ihnen, spezifische Facebook Pixel-Ereignisse zu aktivieren oder zu deaktivieren. Aktivieren Sie nur die Ereignisse, die Sie aktiv verfolgen möchten.

- **Seitenansichtsereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde eine beliebige Seite auf Ihrer Website ansieht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `PageView`-Ereignis wird bei jedem Seitenaufruf gesendet.
    - *Wenn deaktiviert:* Es werden keine `PageView`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Dies ist ein grundlegendes Ereignis für alle Verfolgungen.
- **Kaufereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde einen Kauf abschließt. Dies ist das wichtigste Konversionsereignis.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `Purchase`-Ereignis wird auf der Bestellbestätigungsseite und/oder über CAPI gesendet, wenn eine Bestellung einen „Bezahlten Status“ erreicht.
    - *Wenn deaktiviert:* Es werden keine `Purchase`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Absolut unerlässlich für E-Commerce-Werbung.
- **ViewContent-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde eine Produktseite ansieht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `ViewContent`-Ereignis wird gesendet, wenn eine Produktseite geladen wird.
    - *Wenn deaktiviert:* Es werden keine `ViewContent`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Wichtig für dynamische Produktanzeigen und Remarketing.
- **AddToCart-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde einen Artikel in seinen Warenkorb legt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `AddToCart`-Ereignis wird gesendet, wenn ein Artikel in den Warenkorb gelegt wird.
    - *Wenn deaktiviert:* Es werden keine `AddToCart`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Entscheidend für Kampagnen zur Wiederherstellung abgebrochener Warenkörbe.
- **RemoveFromCart-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde einen Artikel aus seinem Warenkorb entfernt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `RemoveFromCart`-Ereignis wird gesendet, wenn ein Artikel entfernt wird.
    - *Wenn deaktiviert:* Es werden keine `RemoveFromCart`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Kann Einblicke in das Kundenverhalten und Produktinteresse geben.
- **InitiateCheckout-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde den Checkout-Prozess startet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `InitiateCheckout`-Ereignis wird gesendet, wenn der Kunde den ersten Schritt des Checkouts betritt.
    - *Wenn deaktiviert:* Es werden keine `InitiateCheckout`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Nützlich, um die Leistung des Checkout-Trichters zu verstehen.
- **Suchereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde die interne Suchfunktion Ihres Shops verwendet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `Search`-Ereignis wird mit der Suchanfrage gesendet.
    - *Wenn deaktiviert:* Es werden keine `Search`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Liefert wertvolle Daten darüber, wonach Kunden suchen.
- **AddToWishlist-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde ein Produkt zu seiner Wunschliste hinzufügt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `AddToWishlist`-Ereignis wird gesendet.
    - *Wenn deaktiviert:* Es werden keine `AddToWishlist`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja, wenn Ihr Shop eine Wunschlistenfunktion verwendet.
- **AddPaymentInfo-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde während des Checkouts eine Zahlungsmethode auswählt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `AddPaymentInfo`-Ereignis wird gesendet.
    - *Wenn deaktiviert:* Es werden keine `AddPaymentInfo`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Hilft bei der Analyse von Zahlungsmethodenpräferenzen und potenziellen Abbrüchen.
- **Kontakt-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde Ihre Kontaktseite besucht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `Contact`-Ereignis wird gesendet.
    - *Wenn deaktiviert:* Es werden keine `Contact`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Nützlich zur Verfolgung von Kundendienstanfragen.
- **Lead-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde eine Aktion ausführt, die Interesse an Ihren Produkten oder Dienstleistungen signalisiert, aber kein direkter Kauf ist (z. B. Newsletter-Anmeldung, Kontoerstellung).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `Lead`-Ereignis wird bei der Newsletter-Registrierung und/oder Kontoerstellung gesendet.
    - *Wenn deaktiviert:* Es werden keine `Lead`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Wichtig für Lead-Generierungskampagnen.
- **CompleteRegistration-Ereignis:**

  - **Was diese Einstellung bewirkt:** Verfolgt, wenn ein Kunde erfolgreich ein Konto in Ihrem Shop erstellt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein `CompleteRegistration`-Ereignis wird gesendet.
    - *Wenn deaktiviert:* Es werden keine `CompleteRegistration`-Ereignisse gesendet.
  - **Empfohlener Wert:** Ja. Nützlich zur Verfolgung der Neukundengewinnung.

#### Registerkarte Live-Statistiken

Diese Registerkarte bietet Echtzeit-Einblicke in die Ereignisse, die von Ihrem Shop an Facebook gesendet werden, und hilft Ihnen, den Zustand Ihres Pixels zu überwachen.

- **Ereignisse speichern für (Tage):**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie lange das Modul Ereignisdaten lokal speichert, um sie auf der Registerkarte „Live-Statistiken“ anzuzeigen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn festgelegt:* Ereignisdaten, die älter als diese Anzahl von Tagen sind, werden automatisch gelöscht.
    - *Wenn auf 0 gesetzt:* Ereignisse werden nicht lokal gespeichert (und Live-Statistiken zeigen keine Daten an).
  - **Empfohlener Wert:** 7-30 Tage, je nachdem, wie viele historische Daten Sie überprüfen möchten.
  - **Händlerszenario / Beispiel:** Sie möchten die Ereignisse der letzten Woche überprüfen. Sie stellen dies auf `7` ein.
- **Live-Abfrageintervall (Sekunden):**

  - **Was diese Einstellung bewirkt:** Steuert, wie oft die Registerkarte „Live-Statistiken“ aktualisiert wird, um neue Ereignisse anzuzeigen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn festgelegt:* Die Live-Statistik-Tabelle wird alle X Sekunden aktualisiert.
    - *Wenn auf 0 gesetzt:* Live-Statistiken werden nicht automatisch aktualisiert.
  - **Empfohlener Wert:** 5-10 Sekunden für aktive Überwachung.
  - **Händlerszenario / Beispiel:** Sie testen Ihren Pixel aktiv und möchten, dass Ereignisse fast sofort angezeigt werden. Sie stellen dies auf `5` ein.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Allgemeine Einstellungen | Pixel-ID(s) | Ihre Facebook Pixel-ID | Verbindet Ihren Shop mit Facebook Pixel zur Verfolgung. |
| Allgemeine Einstellungen | CAPI-Zugriffstoken | Ihr CAPI-Zugriffstoken | Ermöglicht serverseitiges Tracking für verbesserte Datengenauigkeit. |
| Allgemeine Einstellungen | Test-Ereigniscode | Leer (nur zum Testen verwenden) | Sendet Testereignisse an den Facebook Events Manager. |
| Allgemeine Einstellungen | Zustimmungsmodus | Ja (für DSGVO-Konformität) | Löst Pixel-Ereignisse nur nach Kundenzustimmung aus. |
| Allgemeine Einstellungen | Bezahlte Status | Zahlung akzeptiert, Geliefert | Definiert, welche Bestellstatus ein „Purchase“-Ereignis auslösen. |
| Allgemeine Einstellungen | Rückerstattungs-/Stornierungsstatus | Storniert, Erstattet | Definiert, welche Bestellstatus als Nicht-Kauf gelten. |
| Erweiterte Einstellungen | CSS-Selektor für „In den Warenkorb legen“ | Leer (automatische Erkennung) | Hilft, die Schaltfläche „In den Warenkorb legen“ für die Verfolgung zu identifizieren. |
| Erweiterte Einstellungen | CSS-Selektor für Produktpreis | Leer (automatische Erkennung) | Hilft, den Produktpreis für Ereigniswerte zu identifizieren. |
| Erweiterte Einstellungen | Produktidentifikation | Reference (SKU) | Bestimmt, welche Produkt-ID an Facebook gesendet wird. |
| Erweiterte Einstellungen | Trennzeichen | - (Bindestrich) | Trennzeichen für Produkt-ID und Attribut-ID. |
| Erweiterte Einstellungen | Produkt-ID-Präfix | Leer | Fügt der an Facebook gesendeten Produkt-ID ein Präfix hinzu. |
| Erweiterte Einstellungen | Produkt-ID-Suffix | Leer | Fügt der an Facebook gesendeten Produkt-ID ein Suffix hinzu. |
| Erweiterte Einstellungen | Zielwährung | Ihre primäre Anzeigenwährung | Konvertiert Ereigniswerte in eine bestimmte Währung. |
| Ereignisverfolgung | Seitenansichtsereignis | Ja | Verfolgt alle Seitenaufrufe. |
| Ereignisverfolgung | Kaufereignis | Ja | Verfolgt abgeschlossene Käufe. |
| Ereignisverfolgung | ViewContent-Ereignis | Ja | Verfolgt Produktseitenaufrufe. |
| Ereignisverfolgung | AddToCart-Ereignis | Ja | Verfolgt in den Warenkorb gelegte Artikel. |
| Ereignisverfolgung | RemoveFromCart-Ereignis | Ja | Verfolgt aus dem Warenkorb entfernte Artikel. |
| Ereignisverfolgung | InitiateCheckout-Ereignis | Ja | Verfolgt den Beginn des Checkouts. |
| Ereignisverfolgung | Suchereignis | Ja | Verfolgt interne Website-Suchen. |
| Ereignisverfolgung | AddToWishlist-Ereignis | Ja (wenn Wunschliste verwendet wird) | Verfolgt zur Wunschliste hinzugefügte Artikel. |
| Ereignisverfolgung | AddPaymentInfo-Ereignis | Ja | Verfolgt hinzugefügte Zahlungsinformationen während des Checkouts. |
| Ereignisverfolgung | Kontakt-Ereignis | Ja | Verfolgt Besuche auf der Kontaktseite. |
| Ereignisverfolgung | Lead-Ereignis | Ja | Verfolgt Newsletter-Anmeldungen/Kontoerstellungen. |
| Ereignisverfolgung | CompleteRegistration-Ereignis | Ja | Verfolgt erfolgreiche Kontoanmeldungen. |
| Live-Statistiken | Ereignisse speichern für (Tage) | 7-30 | Aufbewahrungsfrist für lokale Ereignisdaten. |
| Live-Statistiken | Live-Abfrageintervall (Sekunden) | 5-10 | Aktualisierungsrate für die Anzeige der Live-Statistiken. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminFbpixelAjaxController (Back Office > Module > Fb Conversion Tracking Pixel > Registerkarte Live-Statistiken)

Dieser Controller steuert die Registerkarte „Live-Statistiken“ innerhalb der Modulkonfiguration. Er hat keinen separaten Menüpunkt, ist aber ein integraler Bestandteil der Konfigurationsoberfläche des Moduls.

- **Bildschirmname & Menüpfad:** Zugriff über **Module > Modul-Manager > Fb Conversion Tracking Pixel > Konfigurieren**, dann auf die Registerkarte **„Live-Statistiken“** klicken.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt ein Raster oder eine Tabelle der letzten Facebook Pixel-Ereignisse an, die von Ihrem Shop ausgelöst wurden. Er zeigt Details wie den Ereignisnamen (z. B. `PageView`, `AddToCart`, `Purchase`), den Zeitstempel, die zugehörige Pixel-ID und oft die mit dem Ereignis gesendeten Parameter (z. B. Produkt-ID, Wert, Währung).
- **Auswirkung von Änderungen:** Auf diesem Bildschirm gibt es keine direkten „Einstellungen“ zu ändern. Es ist ein Überwachungstool. Die angezeigten Daten werden durch die Einstellungen „Ereignisse speichern für (Tage)“ und „Live-Abfrageintervall (Sekunden)“ auf derselben Konfigurationsseite beeinflusst.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diese Registerkarte regelmäßig, insbesondere nach Änderungen an Ihrem Shop oder der Einführung neuer Produkte, um sicherzustellen, dass Ihr Facebook Pixel korrekt ausgelöst wird und genaue Daten sendet. Dies ist Ihre erste Verteidigungslinie zur Fehlerbehebung bei Pixel-Problemen, bevor Sie den Facebook Events Manager überprüfen.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Facebook Pixel Helper Chrome-Erweiterung zeigt keinen Pixel oder Fehler an. Was soll ich tun?**

- **A:** Stellen Sie zunächst sicher, dass Sie Ihre „Pixel-ID(s)“ in der Modulkonfiguration korrekt eingegeben haben.
- **A:** Überprüfen Sie, ob der „Zustimmungsmodus“ aktiviert ist. Wenn ja, müssen Sie möglicherweise Cookies in Ihrem Shop akzeptieren, damit der Pixel ausgelöst wird.
- **A:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren).
- **A:** Wenn Sie ein benutzerdefiniertes Theme verwenden, kann es zu Konflikten kommen. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um dies auszuschließen.
- **A:** Verwenden Sie das Facebook-Tool „Test-Ereignisse“ im Events Manager, um zu sehen, ob Ereignisse empfangen werden.

**F2: Meine Kaufereignisse werden im Facebook Events Manager nicht korrekt angezeigt.**

- **A:** Überprüfen Sie, ob Ihre „Bezahlten Status“ in der Modulkonfiguration korrekt ausgewählt sind. Nur Bestellungen, die diese Status erreichen, lösen ein Kaufereignis aus.
- **A:** Wenn Sie CAPI verwenden, stellen Sie sicher, dass Ihr „CAPI Access Token“ korrekt ist und testen Sie es mit der Funktion „Test-Ereigniscode“.
- **A:** Überprüfen Sie, ob Ihre „Zielwährung“ korrekt eingestellt ist, insbesondere bei Shops mit mehreren Währungen.
- **A:** Überprüfen Sie die Registerkarte „Live-Statistiken“ in der Modulkonfiguration, um zu sehen, ob das Modul intern Kaufereignisse protokolliert.

**F3: Dynamische Produktanzeigen zeigen nicht die richtigen Produkte oder überhaupt keine Produkte an.**

- **A:** Der häufigste Grund ist eine Diskrepanz zwischen Ihrer Einstellung „Produktidentifikation“ im Modul und den IDs in Ihrem Facebook-Produktkatalog. Stellen Sie sicher, dass sie identisch sind (z. B. wenn Ihr Katalog SKU verwendet, stellen Sie das Modul auf „Reference“ ein).
- **A:** Stellen Sie sicher, dass Ihr Facebook-Produktkatalog aktuell und fehlerfrei ist.
- **A:** Überprüfen Sie, ob die Ereignisse „ViewContent“ und „AddToCart“ korrekt mit dem Parameter `content_ids` ausgelöst werden, der mit Ihren Katalog-IDs übereinstimmt.

**F4: Wie stelle ich die DSGVO- oder andere Datenschutzkonformität mit diesem Modul sicher?**

- **A:** Aktivieren Sie die Einstellung „Zustimmungsmodus“ im Modul. Dies integriert sich in Ihr vorhandenes Cookie-Zustimmungsmodul (falls korrekt konfiguriert), um den Pixel erst nach ausdrücklicher Benutzerzustimmung auszulösen.
- **A:** Stellen Sie sicher, dass die Datenschutzrichtlinie Ihres Shops klar besagt, dass Sie Facebook Pixel für Werbung und Analysen verwenden und wie Benutzer sich abmelden oder ihre Cookie-Einstellungen verwalten können.

**F5: Das „In den Warenkorb legen“-Ereignis wird auf meiner Produktseite nicht ausgelöst.**

- **A:** Ihr Theme hat möglicherweise eine benutzerdefinierte Schaltfläche „In den Warenkorb legen“, die das Modul nicht automatisch erkennen kann. Versuchen Sie, die Schaltfläche „In den Warenkorb legen“ auf Ihrer Produktseite mit den Entwicklertools Ihres Browsers zu inspizieren (Rechtsklick > Untersuchen), um ihre CSS-Klasse oder ID zu finden. Geben Sie diese dann in das Feld „CSS-Selektor für In den Warenkorb legen“ in der Modulkonfiguration ein (z. B. `.my-custom-atc-button` oder `#add_to_cart_button`).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Fb conversion tracking pixel` folgt einer Standard-PrestaShop-Modularchitektur, die Hooks für die Ereignisinjektion im Front-Office und einen AdminController für Back-Office-AJAX-Interaktionen (Live-Statistiken) nutzt. Es basiert stark auf einem Factory-Muster (`FbpixelTrackerFactory`), um verschiedene Tracking-Mechanismen (browserseitiger Pixel, serverseitige CAPI) zu verwalten. Ereignisdaten werden von dedizierten Klassen (`FbpixelEvents`, `FbpixelPixelTracker`, `FbpixelCapiTracker`) gesammelt und verarbeitet und dann versendet. Die Konfiguration wird in `ps_configuration` gespeichert. Das Modul enthält auch robuste Tools zur Fehlerbehebung und Zustandsprüfung.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajax.php`
    - **Klassenname:** `FbpixelAjaxModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Verarbeitet AJAX-Anfragen vom Front-Office, hauptsächlich zum Sammeln und Protokollieren von Echtzeit-Ereignisdaten für die Live-Statistikfunktion. Es kann auch für spezifische Ereignisauslöser verwendet werden, die nicht rein clientseitig verarbeitet werden können (z. B. `RemoveFromCart` nach einer Warenkorbaktualisierung).
  - `controllers/front/cron.php`
    - **Klassenname:** `FbpixelCronModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Entwickelt, um von einem Cron-Job aufgerufen zu werden. Dieser Controller ist wahrscheinlich für die Verarbeitung von in der Warteschlange befindlichen CAPI-Ereignissen, die Datenbereinigung (z. B. das Löschen alter Live-Statistik-Einträge) oder andere geplante Aufgaben verantwortlich.
  - `controllers/front/index.php`
    - **Klassenname:** `FbpixelIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Ein Platzhalter- oder Fallback-Controller, der oft verwendet wird, um die Verzeichnisauflistung zu verhindern oder eine Standardantwort für modulspezifische Routen bereitzustellen.
  - `controllers/front/sync.php`
    - **Klassenname:** `FbpixelSyncModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Potenziell für Synchronisierungsaufgaben zuständig, wie das Pushen von Produktkatalogaktualisierungen oder anderen Daten an Facebook oder das Empfangen von Daten von Facebook.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminFbpixelAjaxController.php`
    - **Klassenname:** `AdminFbpixelAjaxController` (erweitert `ModuleAdminController`)
    - **Tab-Name:** Kein eigenständiger Tab, sondern in die Modulkonfiguration integriert.
    - **Verwaltete Entität:** Verwaltet AJAX-Anfragen von der Back-Office-Konfigurationsseite des Moduls, speziell zum Abrufen und Anzeigen der Ereignisdaten der „Live-Statistiken“. Es stellt die Daten für das Template `recent-events.tpl` bereit.

### 4.3 Kernklassen & Modelle (`classes/`)

- `fbpixel/classes/autoload.php`: Verwaltet das Laden benutzerdefinierter Klassen für das Modul.
- `fbpixel/classes/FbpixelCapiClient.php`:
  - **Verantwortlichkeit:** Kapselt die Logik für HTTP-Anfragen an die Conversions API von Facebook. Verwaltet Authentifizierung, Anforderungsformatierung und Fehlerbehandlung.
- `fbpixel/classes/FbpixelCapiTracker.php`:
  - **Verantwortlichkeit:** Implementiert das `FbpixelTrackerInterface` für serverseitiges Ereignis-Tracking. Formatiert Ereignisdaten gemäß CAPI-Spezifikationen und versendet sie über `FbpixelCapiClient`.
- `fbpixel/classes/FbpixelCatalogDoctor.php`:
  - **Verantwortlichkeit:** Bietet Tools und Logik zur Diagnose von Problemen im Zusammenhang mit der Produktkatalog-Übereinstimmung und der Datenkonsistenz zwischen PrestaShop und Facebook.
- `fbpixel/classes/FbpixelConsent.php`:
  - **Verantwortlichkeit:** Verwaltet und überprüft den Benutzerzustimmungsstatus, integriert sich in die Cookie-Zustimmungsmechanismen von PrestaShop (falls verfügbar), um die DSGVO-Konformität sicherzustellen.
- `fbpixel/classes/FbpixelCurrencyHelper.php`:
  - **Verantwortlichkeit:** Dienstprogrammklasse für Währungsumrechnung und -formatierung, um sicherzustellen, dass Ereigniswerte in der korrekten Zielwährung gesendet werden.
- `fbpixel/classes/FbpixelEmqCoach.php`:
  - **Verantwortlichkeit:** Bietet wahrscheinlich Anleitungen oder Empfehlungen zur Verbesserung der Event Match Quality (EMQ) für Facebook-Ereignisse.
- `fbpixel/classes/FbpixelEventId.php`:
  - **Verantwortlichkeit:** Generiert und verwaltet eindeutige Ereignis-IDs, entscheidend für die Deduplizierung zwischen browserseitigen und serverseitigen Ereignissen.
- `fbpixel/classes/FbpixelEvents.php`:
  - **Verantwortlichkeit:** Eine zentrale Klasse zur Definition und Verwaltung der verschiedenen Facebook Pixel-Ereignistypen (PageView, Purchase, AddToCart usw.) und ihrer Standardparameter.
- `fbpixel/classes/FbpixelHealthScore.php`:
  - **Verantwortlichkeit:** Berechnet und zeigt einen „Gesundheitswert“ für das Pixel-Setup an, der potenzielle Probleme oder Verbesserungsmöglichkeiten identifiziert.
- `fbpixel/classes/FbpixelLiveStats.php`:
  - **Datenbanktabelle:** `ps_fbpixel_events` (wahrscheinlich, basierend auf der Funktionalität)
  - **Erweitert:** Wahrscheinlich `ObjectModel`
  - **Verantwortlichkeit:** Speichert und ruft Ereignisdaten lokal für die Funktion „Live-Statistiken“ im Back Office ab. Verwaltet Datenaufbewahrung und -bereinigung.
- `fbpixel/classes/FbpixelPixelRules.php`:
  - **Verantwortlichkeit:** Definiert Regeln und Bedingungen, wann bestimmte Pixel-Ereignisse ausgelöst werden sollen, möglicherweise basierend auf Seitentyp, Benutzeraktionen oder Konfiguration.
- `fbpixel/classes/FbpixelPixelTracker.php`:
  - **Verantwortlichkeit:** Implementiert das `FbpixelTrackerInterface` für browserseitiges Ereignis-Tracking. Generiert den JavaScript-Code für `fbq()`-Aufrufe und injiziert ihn in das Front Office.
- `fbpixel/classes/FbpixelProductIdResolver.php`:
  - **Verantwortlichkeit:** Löst die korrekte Produkt-ID und Attribut-ID basierend auf der Modulkonfiguration (Präfix, Suffix, Trennzeichen, gewählter ID-Typ) zur Übermittlung an Facebook auf.
- `fbpixel/classes/FbpixelTrackerFactory.php`:
  - **Verantwortlichkeit:** Eine Factory-Klasse, die den entsprechenden Tracker (z. B. `FbpixelPixelTracker` für den Browser, `FbpixelCapiTracker` für den Server) basierend auf der Modulkonfiguration und dem Kontext instanziiert.
- `fbpixel/classes/FbpixelTrackerInterface.php`:
  - **Verantwortlichkeit:** Definiert eine gemeinsame Schnittstelle für alle Tracking-Klassen, um konsistente Methodensignaturen für die Ereignisversendung zu gewährleisten.
- `fbpixel/classes/FbpixelUserData.php`:
  - **Verantwortlichkeit:** Sammelt und formatiert Benutzerdaten (z. B. E-Mail, Telefon, IP-Adresse) zur Übermittlung mit CAPI-Ereignissen, entscheidend für die Event Match Quality.
- `fbpixel/classes/index.php`: Leere Datei, typischerweise verwendet, um die Verzeichnisauflistung zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

- `fbpixel/lib/searchTool/views/js/autocomplete.js`:
  - **Geltungsbereich:** Back-Office.
  - **Details:** Bietet Autocomplete-Funktionalität für Eingabefelder, wahrscheinlich in der Modulkonfiguration zur Auswahl von Produkten, Kategorien oder anderen Entitäten verwendet.
- `fbpixel/views/js/fbpixel-admin.js`:
  - **Geltungsbereich:** Back-Office.
  - **Details:** Verwaltet die allgemeine administrative Logik für die Konfigurationsseite des Moduls, einschließlich Formularübermittlungen, Tab-Wechsel und potenziell AJAX-Aufrufen an `AdminFbpixelAjaxController`.
- `fbpixel/views/js/fbpixel-debug.js`:
  - **Geltungsbereich:** Front-Office (bedingt).
  - **Details:** Bietet Debugging-Informationen in der Browserkonsole oder einem visuellen Overlay, die anzeigen, welche Pixel-Ereignisse ausgelöst werden und deren Parameter. Wird durch eine Debug-Modus-Einstellung aktiviert.
- `fbpixel/views/js/fbpixel-ghost.js`:
  - **Geltungsbereich:** Front-Office.
  - **Details:** Wahrscheinlich ein clientseitiges Skript, das hilft, Ereignisse zu erkennen und zu verfolgen, die sonst von der Standard-DOM-Beobachtung übersehen werden könnten, wie z. B. dynamisches Laden von Inhalten oder spezifische AJAX-Interaktionen.
- `fbpixel/views/js/fbpixel-live.js`:
  - **Geltungsbereich:** Back-Office.
  - **Details:** Steuert die Registerkarte „Live-Statistiken“, indem es AJAX-Anfragen an `AdminFbpixelAjaxController` sendet, um Echtzeit-Ereignisdaten abzurufen und anzuzeigen, und das Abfrageintervall verwaltet.
- `fbpixel/views/js/fbpixel-wizard.js`:
  - **Geltungsbereich:** Back-Office.
  - **Details:** Verwaltet den Schritt-für-Schritt-Einrichtungsassistenten, der den Händler durch die Erstkonfiguration führt.
- `fbpixel/views/js/fbpixel.js`:
  - **Geltungsbereich:** Front-Office.
  - **Details:** Das primäre clientseitige JavaScript für den Facebook Pixel. Es initialisiert die Funktion `fbq()`, verwaltet Ereignis-Listener für `AddToCart`, `RemoveFromCart`, `Search`, `InitiateCheckout` usw. und versendet Ereignisse an Facebook. Es verwaltet auch die CSS-Selektoren für dynamische Elemente.
- `fbpixel/views/js/mp-collect.js`:
  - **Geltungsbereich:** Front-Office.
  - **Details:** Wahrscheinlich ein Dienstprogramm-Skript zum Sammeln spezifischer Datenpunkte aus dem Front-Office, möglicherweise im Zusammenhang mit dem Benutzerverhalten oder Umgebungsfaktoren, um Ereignisparameter zu verbessern.
- `fbpixel/views/js/mp-front.js`:
  - **Geltungsbereich:** Front-Office.
  - **Details:** Allgemeine JavaScript-Dienstprogramme oder Hilfsfunktionen für das Front-Office, die vom Modul verwendet werden.
- `fbpixel/views/js/mp-inspect.js`:
  - **Geltungsbereich:** Front-Office (bedingt).
  - **Details:** Bietet ein Inspektionswerkzeug, möglicherweise ein visuelles Overlay, um Pixel-Ereignisse direkt im Shop zu debuggen und zu überprüfen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `fbpixel/lib/searchTool/views/css/autocomplete.css`:
  - **Geltungsbereich:** Back-Office.
  - **Details:** Stile für die Autocomplete-Dropdowns und Eingabefelder, die in der Admin-Oberfläche verwendet werden.
- `fbpixel/views/css/fbpixel-admin.css`:
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Details:** Gestaltet die Konfigurationsseite des Moduls, Tabs, Eingabefelder und die Live-Statistik-Tabelle.
- `fbpixel/views/css/fbpixel-debug.css`:
  - **Geltungsbereich:** Front-Office (bedingt).
  - **Details:** Stile für das Debug-Overlay oder die Konsolenausgabe, um Debug-Informationen besser lesbar zu machen.
- `fbpixel/views/css/mp-inspect.css`:
  - **Geltungsbereich:** Front-Office (bedingt).
  - **Details:** Stile für das Front-Office-Inspektionswerkzeug, falls aktiviert.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `fbpixel/views/templates/hook/capi-pageview.tpl`: Wird in einem Hook (wahrscheinlich `displayHeader` oder `actionFrontControllerSetMedia`) gerendert, um ein serverseitiges `PageView`-Ereignis über CAPI auszulösen.
  - `fbpixel/views/templates/hook/debug.tpl`: Rendert das Debug-Overlay oder die Konsolenausgabe für das Front-Office-Debugging.
  - `fbpixel/views/templates/hook/displayOrderConfirmation.tpl`: Rendert das browserseitige `Purchase`-Ereignis auf der Bestellbestätigungsseite.
  - `fbpixel/views/templates/hook/ghost.tpl`: Rendert ein verstecktes Element oder Skript für die `fbpixel-ghost.js`-Funktionalität.
  - `fbpixel/views/templates/hook/header.tpl`: Rendert den Basis-Facebook-Pixel-Initialisierungscode (`fbq('init', ...)` und `fbq('track', 'PageView')`) im `<head>`-Bereich, typischerweise über `displayHeader` oder `actionFrontControllerSetMedia`.
  - `fbpixel/views/templates/hook/payment.tpl`: Potenziell verwendet, um `AddPaymentInfo`-Ereignisse oder andere zahlungsbezogene Interaktionen zu verfolgen.
  - `fbpixel/views/templates/hook/product-details.tpl`: Rendert Skripte oder Daten, die spezifisch für Produktseiten sind, hauptsächlich für `ViewContent`- und `AddToCart`-Ereignisse, wahrscheinlich injiziert über `displayProductFooter` oder `displayProductAdditionalInfo`.
- **Admin-Templates (`views/templates/admin/`)**:

  - `fbpixel/lib/searchTool/views/scripts.tpl`: Enthält JavaScript für das Suchwerkzeug/Autocomplete im Admin.
  - `fbpixel/views/templates/admin/configure.tpl`: Das Haupttemplate für die Konfigurationsseite des Moduls, das alle anderen Admin-Templates orchestriert.
  - `fbpixel/views/templates/admin/doctor.tpl`: Zeigt die Ergebnisse des `FbpixelCatalogDoctor` zur Diagnose von Katalogproblemen an.
  - `fbpixel/views/templates/admin/emq.tpl`: Zeigt Informationen oder Empfehlungen von `FbpixelEmqCoach` bezüglich der Event Match Quality an.
  - `fbpixel/views/templates/admin/health.tpl`: Zeigt den Gesundheitswert des Pixels von `FbpixelHealthScore` an.
  - `fbpixel/views/templates/admin/live-maintain.tpl`: Template zur Verwaltung der Live-Statistik-Einstellungen (Aufbewahrung, Abfrageintervall).
  - `fbpixel/views/templates/admin/live.tpl`: Das Container-Template für die Registerkarte „Live-Statistiken“.
  - `fbpixel/views/templates/admin/mode-context.tpl`: Zeigt kontextspezifische Informationen basierend auf dem Betriebsmodus des Pixels an.
  - `fbpixel/views/templates/admin/mode-note-capi.tpl`: Zeigt Hinweise oder Warnungen speziell für die CAPI-Konfiguration an.
  - `fbpixel/views/templates/admin/mode-note-pixel.tpl`: Zeigt Hinweise oder Warnungen speziell für die browserseitige Pixel-Konfiguration an.
  - `fbpixel/views/templates/admin/mode-picker.tpl`: Ermöglicht dem Händler die Auswahl des Betriebsmodus des Pixels (z. B. Standard, Debug).
  - `fbpixel/views/templates/admin/pixels-list.tpl`: Zeigt eine Liste der konfigurierten Pixel-IDs an.
  - `fbpixel/views/templates/admin/recent-events.tpl`: Rendert die Tabelle der letzten Ereignisse für die Registerkarte „Live-Statistiken“, gefüllt durch `AdminFbpixelAjaxController`.
  - `fbpixel/views/templates/admin/tabs.tpl`: Rendert die Tab-Navigation für die Konfigurationsseite des Moduls.
  - `fbpixel/views/templates/admin/wizard.tpl`: Rendert die Schritt-für-Schritt-Einrichtungsassistenten-Oberfläche.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_configuration`: Speichert alle Moduleinstellungen (z. B. `FBPIXEL_ID`, `FBPIXEL_CAPI_TOKEN`, `FBPIXEL_PAID_STATUSES`).
  - `ps_fbpixel_events` (wahrscheinlich): Eine vom Modul erstellte benutzerdefinierte Tabelle zum Speichern lokaler Ereignisprotokolle für die Funktion „Live-Statistiken“. Spalten würden typischerweise `id_fbpixel_event`, `pixel_id`, `event_name`, `event_data` (JSON), `timestamp`, `ip_address`, `user_agent` umfassen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller rendert, zum Hinzufügen von JS/CSS. | Injiziert den Kern-Facebook-Pixel-JS, Ereignis-Tracking-Skripte und CAPI PageView. |
| `displayContactContent` | Auf der Kontaktseite. | Löst das `Contact`-Ereignis aus. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite. | Löst das browserseitige `Purchase`-Ereignis aus. |
| `actionNewsletterRegistrationAfter` | Nach einer Newsletter-Anmeldung. | Löst das `Lead`-Ereignis aus (und potenziell `CompleteRegistration`, wenn kombiniert). |
| `displayProductFooter` | Am unteren Rand der Produktseiten. | Injiziert produktspezifische Daten und das `ViewContent`-Ereignis. |
| `displayHeader` | Im `<head>`-Bereich aller Front-Office-Seiten. | Injiziert den Basis-Facebook-Pixel-Code und das `PageView`-Ereignis. |
| `DisplayProductButtons` | In der Nähe von Produktaktionsschaltflächen (z. B. In den Warenkorb legen). | Kann JS für den `AddToCart`-Ereignis-Listener injizieren. |
| `ActionObjectProductInCartDeleteBefore` | Bevor ein Produkt aus dem Warenkorb entfernt wird. | Löst potenziell das `RemoveFromCart`-Ereignis aus. |
| `DisplayProductAdditionalInfo` | Im Produktinformationsblock. | Zusätzliche Produkt-Dateninjektion oder Ereignisauslöser. |
| `ActionCronJob` | Während einer geplanten Cron-Ausführung. | Löst die CAPI-Ereignisverarbeitung und Datenbereinigung aus. |
| `ActionObjectProductInCartDeleteAfter` | Nachdem ein Produkt aus dem Warenkorb entfernt wurde. | Löst das `RemoveFromCart`-Ereignis aus. |
| `ActionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Löst das serverseitige `Purchase`-Ereignis über CAPI aus. |
| `DisplayLeftColumnProduct` | In der linken Spalte der Produktseiten. | Weniger üblich für Pixel, möglicherweise für spezifische produktbezogene Ereignisse. |
| `displayExtraLeft` | In der zusätzlichen linken Spalte. | Weniger üblich für Pixel, möglicherweise für spezifische produktbezogene Ereignisse. |
| `ActionCartUpdateQuantityBefore` | Bevor die Warenkorbmenge aktualisiert wird. | Potenziell verwendet, um Änderungen zu verfolgen, die zu `RemoveFromCart` führen könnten. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Fb Conversion Tracking Pixel“ gerne zur Verfügung.
