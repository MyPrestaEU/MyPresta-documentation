---
title: "Google Kundenrezensionen für PrestaShop - Opt-in & Umfrage (GCR) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Google Kundenrezensionen für PrestaShop - Opt-in & Umfrage (GCR) von MyPresta.eu."
sidebar:
  label: "Google Kundenrezensionen für PrestaShop - Opt-in & Umfrage (GCR) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google Customer Reviews for PrestaShop - opt-in & survey (GCR) auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr/)
>
> ---


# Google Kundenrezensionen für PrestaShop - Opt-in & Umfrage (GCR)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Einstellungen des Moduls zuzugreifen, gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Google Kundenrezensionen“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

#### **Google Merchant ID**

- **Was diese Einstellung bewirkt:** Dies ist die eindeutige Kennung für Ihr Google Merchant Center-Konto. Google verwendet diese ID, um die gesammelten Bewertungen Ihrem spezifischen Unternehmen zuzuordnen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Das Google Kundenrezensionen Opt-in-Skript funktioniert ordnungsgemäß und sendet Bewertungsdaten an Ihr Google Merchant Center-Konto.
  - *Bei falscher oder leerer Eingabe:* Das Opt-in-Skript funktioniert nicht, und Google sammelt keine Bewertungen für Ihren Shop.
- **Empfohlener Wert:** Ihre genaue Google Merchant Center ID. Sie finden diese ID, indem Sie sich in Ihrem Google Merchant Center-Konto (merchant.google.com) anmelden – sie wird normalerweise oben rechts angezeigt.
- **Händlerszenario / Beispiel:** Wenn Ihre Google Merchant Center ID `123456789` ist, würden Sie `123456789` in dieses Feld eingeben. Ohne sie weiß Google nicht, welchem Händler die Bewertungen zugeordnet werden sollen.

#### **GTIN-Liste der Produkte in GCR-Nutzdaten aufnehmen**

- **Was diese Einstellung bewirkt:** Diese Option steuert, ob die Global Trade Item Numbers (GTINs) der Produkte in der Kundenbestellung enthalten sind, wenn die Opt-in-Daten an Google gesendet werden. GTINs (wie EAN, UPC, ISBN) helfen Google, bestimmte Produkte für produktbezogene Bewertungen zu identifizieren.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (Ja):* Das Modul versucht, die GTINs für jedes Produkt in der Bestellung abzurufen und einzuschließen. Dies ermöglicht es Google, potenziell produktspezifische Bewertungen zu sammeln, die auf Produktseiten und in Google Shopping erscheinen können.
  - *Wenn deaktiviert (Nein):* Es werden nur Verkäuferbewertungen gesammelt. Produktspezifische GTINs werden nicht gesendet, was bedeutet, dass Google Kunden nicht um Bewertungen für einzelne Produkte aus dieser Bestellung bitten wird.
- **Empfohlener Wert:** **Ja**. Das Einschließen von GTINs wird dringend empfohlen, wenn Sie produktbezogene Bewertungen sammeln möchten, die für die Produktsichtbarkeit und das Vertrauen sehr wertvoll sind. Stellen Sie sicher, dass Ihre Produkte in PrestaShop die EAN/UPC-Felder korrekt ausgefüllt haben.
- **Händlerszenario / Beispiel:** Wenn Sie ein „Blaues T-Shirt“ mit der EAN `1234567890123` verkaufen, stellt die Aktivierung dieser Option sicher, dass Google weiß, *welches* Produkt der Kunde gekauft hat, sodass er diesen spezifischen Artikel bewerten kann. Wenn deaktiviert, würde Google nur nach einer allgemeinen Bewertung Ihres Shops fragen.

#### **Standard-Lieferverzögerung (Tage)**

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt die geschätzte Anzahl von Tagen nach einer Bestellung, an denen der Kunde seine Lieferung voraussichtlich erhält. Google verwendet dieses Datum, um den Zeitpunkt für den Versand der Bewertungs-E-Mail festzulegen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf eine bestimmte Zahl eingestellt (z.B. 7):* Das Modul berechnet das geschätzte Lieferdatum, indem es diese Anzahl von Tagen zum Bestelldatum addiert. Google sendet die Umfrage-E-Mail dann um dieses berechnete Lieferdatum herum.
  - *Wenn auf 0 oder eine sehr niedrige Zahl eingestellt:* Google könnte die Umfrage zu früh senden, bevor der Kunde sein Produkt erhalten hat, was zu irrelevanten oder negativen Bewertungen führen kann.
  - *Wenn auf eine sehr hohe Zahl eingestellt:* Google könnte die Umfrage zu spät senden, und der Kunde könnte Details seines Kauferlebnisses vergessen haben.
- **Empfohlener Wert:** Dies hängt von Ihren durchschnittlichen Versandzeiten ab. Ein gängiger Ausgangspunkt sind **7 Tage**. Passen Sie dies an Ihre tatsächliche Lieferleistung an.
- **Händlerszenario / Beispiel:** Wenn Ihre durchschnittliche Lieferzeit 5-7 Werktage beträgt, ist die Einstellung auf `7` Tage angemessen. Wenn Sie international versenden und Lieferungen 2-3 Wochen dauern, könnten Sie sie auf `14` oder `21` Tage einstellen. Dies stellt sicher, dass die Umfrage ankommt, wenn der Kunde Zeit hatte, das Produkt zu erhalten und zu erleben.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Google Merchant ID | Ihre Merchant ID | Verknüpft gesammelte Bewertungen mit Ihrem Google Merchant Center-Konto. **KRITISCH für die Funktion.** |
| Modulkonfiguration | GTIN-Liste der Produkte in GCR-Nutzdaten aufnehmen | Ja | Ermöglicht die Erfassung produktspezifischer Bewertungen durch Senden von Produktkennungen. |
| Modulkonfiguration | Standard-Lieferverzögerung (Tage) | 7 | Legt das geschätzte Lieferdatum für die Umfrageplanung fest. An die durchschnittliche Versandzeit anpassen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber ich sehe das Google Kundenrezensionen Opt-in nicht auf meiner Bestellbestätigungsseite.**
A:

1. **Überprüfen Sie Ihre Google Merchant ID:** Überprüfen Sie nochmals, ob Sie die korrekte Google Merchant ID in der Modulkonfiguration eingegeben haben. Eine falsche ID verhindert das Laden des Skripts.
2. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal kann zwischengespeicherter Inhalt verhindern, dass neue Modulskripte angezeigt werden.
3. **Auf JavaScript-Fehler prüfen:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (normalerweise F12) auf der Bestellbestätigungsseite. Suchen Sie nach JavaScript-Fehlern, die auf einen Konflikt mit einem anderen Modul oder Ihrem Theme hinweisen könnten.
4. **Hook-Ausführung überprüfen:** Stellen Sie sicher, dass Ihr Theme den `displayOrderConfirmation`-Hook korrekt aufruft. Obwohl dies Standard ist, könnten einige stark angepasste Themes Hooks weglassen oder umbenennen.

**F: Das Opt-in erscheint, aber ich sehe keine Bewertungen in meinem Google Merchant Center.**
A:

1. **Google Merchant Center Status:** Melden Sie sich in Ihrem Google Merchant Center-Konto an und navigieren Sie zum Abschnitt „Google Kundenrezensionen“. Stellen Sie sicher, dass das Programm aktiv ist und keine Probleme gemeldet werden. Es kann einige Zeit dauern, bis Bewertungen nach der Ersteinrichtung erscheinen.
2. **Kunden-Opt-in-Rate:** Nicht jeder Kunde wird sich für die Umfrage anmelden. Ein bestimmter Prozentsatz der Kunden muss zustimmen, die Umfrage-E-Mail von Google zu erhalten.
3. **Umfrageabschluss:** Selbst wenn ein Kunde sich anmeldet, muss er die von Google gesendete Umfrage noch ausfüllen.

**F: Kann ich das Aussehen des Google Kundenrezensionen Opt-ins oder Badges anpassen?**
A: Das Aussehen der Opt-in-Aufforderung und des Google Kundenrezensionen-Badges wird von Google gesteuert und kann nicht direkt über das PrestaShop-Modul angepasst werden. Google pflegt ein konsistentes Markenerlebnis für diese Elemente. Sie können jedoch über Ihre Google Merchant Center-Einstellungen wählen, wo das Badge auf Ihrer Website angezeigt werden soll (z.B. Footer, Sidebar).

**F: Meine Produkte haben GTINs, aber ich erhalte keine produktspezifischen Bewertungen.**
A:

1. **GTINs im Modul aktivieren:** Stellen Sie sicher, dass die Option „GTIN-Liste der Produkte in GCR-Nutzdaten aufnehmen“ in der Modulkonfiguration auf „Ja“ eingestellt ist.
2. **Korrekte GTIN-Formatierung:** Überprüfen Sie, ob Ihre Produkt-GTINs (EAN, UPC, ISBN) korrekt auf Ihren PrestaShop-Produktseiten eingegeben wurden und den Standardformaten entsprechen. Falsch formatierte GTINs könnten von Google ignoriert werden.
3. **Googles Ermessen:** Auch wenn GTINs bereitgestellt werden, entscheidet Google letztendlich, ob produktspezifische Bewertungen angefordert werden. Faktoren wie Produktpopularität und Bewertungsvolumen können dies beeinflussen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `gcroptin` ist ein leichtgewichtiges PrestaShop-Modul, das entwickelt wurde, um das offizielle Google Kundenrezensionen Opt-in-Skript in den `displayOrderConfirmation`-Hook zu injizieren. Es nutzt die `Module`-Klasse von PrestaShop und die `Smarty`-Templating-Engine. Die Kernlogik befindet sich in der Hauptmoduldatei und verwaltet die Konfigurationsspeicherung und die dynamische Dateninjektion in die Smarty-Vorlage. Es führt keine benutzerdefinierten Controller, Modelle oder komplexen JavaScript/CSS-Assets ein, sondern konzentriert sich ausschließlich auf die erforderliche Skriptinjektion mit dynamischen Bestelldaten.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul arbeitet, indem es sich in `displayOrderConfirmation` einklinkt und direkt eine Vorlage rendert.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen definiert. Die gesamte Logik ist in `gcroptin.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul gibt den Google Kundenrezensionen JavaScript-Snippet direkt innerhalb einer Smarty-Vorlage aus.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Die Google Kundenrezensionen Opt-in-Benutzeroberfläche wird vom Google-Skript gerendert und erfordert keine benutzerdefinierte Formatierung vom Modul.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `gcroptin/views/templates/hook/gcroptin-order-confirmation.tpl`
    - **Zweck:** Diese Vorlage wird gerendert, wenn der `displayOrderConfirmation`-Hook ausgeführt wird. Sie enthält den Kern-JavaScript-Snippet für das Google Kundenrezensionen Opt-in.
    - **Verfügbare Daten:** Diese Vorlage empfängt verschiedene bestellspezifische Variablen vom Modul, darunter:
      - `{$gcr_merchant_id}`: Die im Back Office konfigurierte Google Merchant Center ID.
      - `{$gcr_order_id}`: Die PrestaShop-Bestell-ID.
      - `{$gcr_currency_iso_code}`: ISO-Code der Bestellwährung.
      - `{$gcr_total_paid}`: Gesamtbetrag der Bestellung.
      - `{$gcr_customer_email}`: E-Mail-Adresse des Kunden.
      - `{$gcr_delivery_country}`: ISO-Code des Lieferlandes.
      - `{$gcr_delivery_date}`: Berechnetes geschätztes Lieferdatum.
      - `{$gcr_product_gtins_json}`: JSON-kodiertes Array von Produkt-GTINs (falls aktiviert).
    - **Ausgabe:** Es gibt ein `<script>`-Tag aus, das den Google Kundenrezensionen Opt-in-Code enthält, dynamisch mit den Bestelldetails gefüllt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `GCROPTIN_MERCHANT_ID`, `GCROPTIN_INCLUDE_GTIN` und `GCROPTIN_DELIVERY_OFFSET`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayOrderConfirmation` | Wird auf der Bestellbestätigungsseite nach einem erfolgreichen Checkout ausgeführt. | Injiziert den Google Kundenrezensionen Opt-in-JavaScript-Snippet mit dynamischen Bestelldaten. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich des Moduls „Google Kundenrezensionen für PrestaShop - Opt-in & Umfrage (GCR)“ gerne zur Verfügung.
