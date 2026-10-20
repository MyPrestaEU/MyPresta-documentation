---
title: "USt-IdNr. in VIES validieren und 0% USt. festlegen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'USt-IdNr. in VIES validieren und 0% USt. festlegen' von MyPresta.eu."
sidebar:
  label: "USt-IdNr. in VIES validieren und 0% USt. festlegen"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Validate VAT in VIES and set 0% VAT auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/validate-vat-in-vies-and-set-0-vat.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/validate-vat-in-vies-and-set-0-vat/)
>
> ---


# USt-IdNr. in VIES validieren und 0% USt. festlegen

## 1. Anforderungen & Kompatibilität

Um den reibungslosen Betrieb des Moduls "USt-IdNr. in VIES validieren und 0% USt. festlegen" zu gewährleisten, beachten Sie bitte die folgenden Anforderungen:

*   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
*   **PHP-Kompatibilität**: PHP 7.1 - 8.5
*   **Hosting-Anforderungen**: Ihre Hosting-Umgebung muss Standard-PHP-Erweiterungen wie `cURL` (für die Kommunikation mit dem VIES-System), `JSON` und `OpenSSL` unterstützen. Diese sind in der Regel bei den meisten modernen Hosting-Anbietern standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbereich für das Modul, in dem Sie dessen Verhalten und Aussehen steuern. Navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach "USt-IdNr. in VIES validieren und 0% USt. festlegen" und klicken Sie auf "Konfigurieren".

#### **Allgemeine Einstellungen**

*   **Ihr Land:**
    *   **Was diese Einstellung bewirkt:** Definiert das Land, in dem Ihr Unternehmen registriert ist. Dies ist entscheidend, um festzustellen, ob die USt-IdNr. eines Kunden für 0% Umsatzsteuer qualifiziert ist (d.h., wenn er aus einem *anderen* EU-Land stammt).
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf Ihr Land eingestellt:* Das Modul identifiziert innergemeinschaftliche Verkäufe korrekt.
        *   *Wenn falsch eingestellt:* Die USt-IdNr.-Validierungslogik könnte fehlschlagen oder 0% Umsatzsteuer falsch anwenden.
    *   **Empfohlener Wert:** Das offizielle Registrierungsland Ihres Shops (z. B. "Deutschland").
    *   **Händlerszenario / Beispiel:** Wenn Ihr Shop in Deutschland ansässig ist, würden Sie "Deutschland" auswählen. Ein Kunde aus Frankreich mit einer gültigen französischen USt-IdNr. wäre dann für 0% Umsatzsteuer berechtigt.
*   **Berechtigte Länder:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl, welche EU-Länder für die 0%-Umsatzsteuerregel berechtigt sind. Sie können bestimmte Länder oder alle EU-Länder auswählen.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn bestimmte Länder ausgewählt sind:* Nur Kunden aus diesen Ländern (mit gültiger USt-IdNr.) erhalten 0% Umsatzsteuer.
        *   *Wenn alle EU-Länder ausgewählt sind:* Alle EU-Länder (außer Ihrem eigenen) sind berechtigt.
    *   **Empfohlener Wert:** Wählen Sie alle EU-Länder aus, es sei denn, Sie haben spezifische geschäftliche Gründe, einige auszuschließen.
    *   **Händlerszenario / Beispiel:** Wenn Sie 0% Umsatzsteuer nur Unternehmen in Frankreich, Deutschland und Spanien anbieten möchten, würden Sie nur diese Länder auswählen.
*   **Steuerregel auswählen:**
    *   **Was diese Einstellung bewirkt:** Gibt an, welche PrestaShop-Steuerregel angewendet werden soll, wenn die USt-IdNr. eines Kunden als 0% validiert wird. Sie sollten eine Steuerregel in PrestaShop für 0% Umsatzsteuer eingerichtet haben.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn eine 0%-Steuerregel ausgewählt ist:* Das Modul wendet diese Regel auf berechtigte Bestellungen an.
        *   *Wenn eine falsche Steuerregel ausgewählt ist:* Der falsche Steuersatz könnte angewendet werden, oder das Modul funktioniert möglicherweise nicht wie erwartet.
    *   **Empfohlener Wert:** Eine Steuerregel, die Sie in PrestaShop mit einem Steuersatz von 0% erstellt haben.
    *   **Händlerszenario / Beispiel:** Sie würden eine Steuerregel namens "EU B2B 0% USt." mit einem Satz von 0% erstellen und hier auswählen.
*   **Modul für ausgewählte Sprachen deaktivieren:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die USt-IdNr.-Validierungsfunktion für bestimmte Sprachen in Ihrem Shop zu deaktivieren. Dies kann nützlich sein, wenn Sie in Nicht-EU-Ländern mit unterschiedlichen Steuervorschriften tätig sind, aber dieselbe PrestaShop-Instanz verwenden.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn Sprachen ausgewählt sind:* Das USt-IdNr.-Validierungsformular und die Logik werden für Kunden, die in diesen Sprachen browsen, nicht angezeigt oder angewendet.
        *   *Wenn keine Sprachen ausgewählt sind:* Das Modul ist für alle Sprachen aktiv.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische sprachbasierte Steueranforderungen.
    *   **Händlerszenario / Beispiel:** Wenn Sie eine englische Version Ihres Shops haben, die sowohl EU- als auch US-Kunden anspricht, aber die USt-IdNr.-Validierung nur für EU-Kunden wünschen, würden Sie sie möglicherweise nicht deaktivieren. Wenn Sie jedoch eine separate Shop-Ansicht für ein Nicht-EU-Land (z. B. "Japan") haben, könnten Sie sie für die japanische Sprache deaktivieren.

#### **Anzeigeeinstellungen (Front-Office-Sichtbarkeit)**

Diese Einstellungen steuern, wo das USt-IdNr.-Eingabeformular und die Statusmeldungen Ihren Kunden angezeigt werden.

*   **USt-IdNr.-Änderungsformular in der Kopfzeile anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt ein kleines Formular oder eine Benachrichtigung im Kopfbereich Ihres Shops an, die Kunden auffordert, ihre USt-IdNr. einzugeben.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Eine Leiste erscheint oben auf Ihrer Website.
        *   *Wenn deaktiviert:* Kein USt-IdNr.-Formular/Benachrichtigung im Header.
    *   **Empfohlener Wert:** "Aus", es sei denn, Sie möchten eine hohe Sichtbarkeit für B2B-Kunden.
    *   **Händlerszenario / Beispiel:** Sie könnten dies aktivieren, wenn Ihr Shop hauptsächlich B2B ist und Sie Geschäftskunden sofort über 0% Umsatzsteuer informieren möchten.
*   **USt-IdNr.-Änderungsformular in displayCustomhtml1 anzeigen (benutzerdefiniertes Theme sp_topdeals):**
    *   **Was diese Einstellung bewirkt:** Dies ist ein spezifischer Hook, der oft von benutzerdefinierten Themes (wie 'sp_topdeals') zum Anzeigen von benutzerdefinierten Inhalten verwendet wird. Wenn Sie dies aktivieren, wird das USt-IdNr.-Formular in diesem spezifischen Bereich platziert.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das USt-IdNr.-Formular erscheint im `displayCustomhtml1`-Hook-Bereich.
        *   *Wenn deaktiviert:* Das Formular wird in diesem spezifischen benutzerdefinierten Bereich nicht angezeigt.
    *   **Empfohlener Wert:** "Aus", es sei denn, Ihr Theme verwendet diesen Hook und Sie möchten das Formular dort haben.
    *   **Händlerszenario / Beispiel:** Wenn Ihr Theme einen prominenten Bannerbereich oben hat und Sie das USt-IdNr.-Formular dort haben möchten, würden Sie dies aktivieren.
*   **USt-IdNr.-Statusleiste für angemeldete Kunden anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt angemeldeten Kunden eine Leiste oder Nachricht an, die ihren aktuellen USt-IdNr.-Status angibt (z. B. "Ihre USt-IdNr. ist gültig, 0% angewendet").
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Angemeldete Kunden sehen ihren USt-IdNr.-Status.
        *   *Wenn deaktiviert:* Keine spezifische USt-IdNr.-Statusleiste für angemeldete Benutzer.
    *   **Empfohlener Wert:** "An", um Ihren B2B-Kunden Klarheit und Sicherheit zu bieten.
    *   **Händlerszenario / Beispiel:** Ein wiederkehrender Geschäftskunde meldet sich an und sieht sofort "Ihre USt-IdNr. ist gültig, 0% USt. auf Ihren Warenkorb angewendet", was sein Einkaufserlebnis verbessert.
*   **USt-IdNr.-Leiste im Checkout-Schritt "Persönliche Informationen" anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt das USt-IdNr.-Eingabefeld und den Validierungsstatus im ersten Schritt des Checkout-Prozesses an (wo Kunden ihren Namen, ihre Adresse usw. eingeben). Dies ist der häufigste und empfohlene Ort.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das USt-IdNr.-Feld ist im Schritt "Persönliche Informationen" sichtbar und interaktiv.
        *   *Wenn deaktiviert:* Das USt-IdNr.-Feld wird in diesem Schritt nicht angezeigt, was es Kunden möglicherweise erschwert, 0% Umsatzsteuer anzuwenden.
    *   **Empfohlener Wert:** "An" (Sehr empfohlen).
    *   **Händlerszenario / Beispiel:** Ein Kunde erreicht den Checkout, gibt seine Firmenadresse ein und dann seine USt-IdNr. in das dafür vorgesehene Feld. Das Modul validiert sie, und der Preis wird aktualisiert.
*   **USt-IdNr.-Leiste in der Checkout-Zusammenfassung anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt den USt-IdNr.-Status (z. B. "USt.: 0%") auf der Checkout-Zusammenfassungsseite an, vor der endgültigen Zahlung.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Kunden sehen ihren USt-IdNr.-Status in der Zusammenfassung.
        *   *Wenn deaktiviert:* Kein spezifischer USt-IdNr.-Status in der Zusammenfassung.
    *   **Empfohlener Wert:** "An" für Transparenz.
    *   **Händlerszenario / Beispiel:** Ein Kunde überprüft seine Bestellung vor der Zahlung und sieht eine klare Bestätigung, dass 0% Umsatzsteuer angewendet wurde.
*   **USt-IdNr.-Leiste im Zahlungsschritt anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt den USt-IdNr.-Status im letzten Zahlungsschritt des Checkouts an.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Kunden sehen ihren USt-IdNr.-Status im Zahlungsschritt.
        *   *Wenn deaktiviert:* Kein spezifischer USt-IdNr.-Status im Zahlungsschritt.
    *   **Empfohlener Wert:** "An" zur endgültigen Bestätigung.
    *   **Händlerszenario / Beispiel:** Kurz vor dem Klick auf "Jetzt bezahlen" sieht der Kunde "Gesamt: 100,00 € (USt. 0%)", was die korrekte Steueranwendung bestätigt.
*   **USt-IdNr.-Änderungsleiste auf der Produktseite anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt ein USt-IdNr.-Eingabeformular oder eine Statusmeldung direkt auf einzelnen Produktseiten an.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ein USt-IdNr.-Formular/Nachricht erscheint auf Produktseiten.
        *   *Wenn deaktiviert:* Kein USt-IdNr.-Formular/Nachricht auf Produktseiten.
    *   **Empfohlener Wert:** "Aus", um Unordnung zu vermeiden, es sei denn, Sie haben einen starken B2B-Fokus und möchten frühzeitig umsatzsteuerfreie Preise anzeigen.
    *   **Händlerszenario / Beispiel:** Ein Geschäftskunde, der eine Produktseite durchsucht, kann seine USt-IdNr. eingeben, um sofort den Preis ohne Umsatzsteuer zu sehen, was ihm bei Kaufentscheidungen hilft.
*   **USt-IdNr.-Änderungsformular in displayProductAdditionalInfo anzeigen:**
    *   **Was diese Einstellung bewirkt:** Dies ist ein Standard-PrestaShop-Hook auf der Produktseite, der typischerweise für zusätzliche Informationen verwendet wird. Wenn Sie dies aktivieren, wird das USt-IdNr.-Formular in diesem Bereich platziert.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das USt-IdNr.-Formular erscheint im `displayProductAdditionalInfo`-Hook-Bereich.
        *   *Wenn deaktiviert:* Das Formular wird in diesem spezifischen Bereich nicht angezeigt.
    *   **Empfohlener Wert:** "Aus", es sei denn, Sie möchten es dort speziell haben.
    *   **Händlerszenario / Beispiel:** Ähnlich wie die Einstellung "USt-IdNr.-Änderungsleiste auf der Produktseite anzeigen", aber zielt auf einen spezifischen Hook ab.
*   **USt-IdNr.-Änderungsformular in displayBanner anzeigen:**
    *   **Was diese Einstellung bewirkt:** Zeigt das USt-IdNr.-Formular oder den Status im `displayBanner`-Hook an, der oft für Top-Banner oder Werbebotschaften verwendet wird.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das USt-IdNr.-Formular/Status erscheint im Bannerbereich.
        *   *Wenn deaktiviert:* Kein USt-IdNr.-Formular/Status im Bannerbereich.
    *   **Empfohlener Wert:** "Aus", um Unordnung zu vermeiden, es sei denn, Sie haben ein spezifisches Bannerdesign dafür.
    *   **Händlerszenario / Beispiel:** Sie könnten dies verwenden, um eine Nachricht "Sind Sie ein Unternehmen? Geben Sie Ihre USt-IdNr. für 0% Steuer ein!" in einem prominenten Banner anzuzeigen.
*   **USt-IdNr.-Änderungsformular in displayCustomhtml1 anzeigen (benutzerdefiniertes Theme sp_topdeals):** (Duplikat, bereits oben behandelt)
*   **USt-IdNr.-Statusleiste für angemeldete Kunden anzeigen:** (Duplikat, bereits oben behandelt)
*   **USt-IdNr.-Leiste im Checkout-Schritt "Persönliche Informationen" anzeigen:** (Duplikat, bereits oben behandelt)
*   **USt-IdNr.-Leiste in der Checkout-Zusammenfassung anzeigen:** (Duplikat, bereits oben behandelt)
*   **USt-IdNr.-Leiste im Zahlungsschritt anzeigen:** (Duplikat, bereits oben behandelt)
*   **Reverse Charge Hinweis auf der Rechnung:**
    *   **Was diese Einstellung bewirkt:** Wenn 0% Umsatzsteuer aufgrund einer gültigen VIES-Prüfung angewendet wird, stellt diese Einstellung sicher, dass ein "Reverse Charge"-Hinweis automatisch zur Kundenrechnung hinzugefügt wird. Dies ist eine gesetzliche Vorschrift für innergemeinschaftliche B2B-Verkäufe.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Rechnungen für 0%-Umsatzsteuer-Bestellungen enthalten den Reverse Charge Hinweis.
        *   *Wenn deaktiviert:* Rechnungen enthalten den Hinweis nicht, was möglicherweise zu Nichteinhaltung führt.
    *   **Empfohlener Wert:** "An" (Sehr empfohlen für die Einhaltung gesetzlicher Vorschriften).
    *   **Händlerszenario / Beispiel:** Ein deutscher Geschäftskunde kauft in Ihrem polnischen Shop mit einer gültigen USt-IdNr. Die Rechnung weist automatisch "Reverse Charge - Umsatzsteuer nicht anwendbar gemäß Artikel 196 der Richtlinie 2006/112/EG des Rates" aus.

#### **Erweiterte Einstellungen**

*   **USt-IdNr. des Kunden bei jeder Bestellung erneut validieren:**
    *   **Was diese Einstellung bewirkt:** Wenn aktiviert, überprüft das Modul die USt-IdNr. des Kunden bei jeder Bestellung erneut mit VIES, auch wenn sie zuvor validiert wurde.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Stellt sicher, dass die USt-IdNr. immer aktuell und gültig ist, fügt aber eine leichte Verzögerung beim Checkout hinzu.
        *   *Wenn deaktiviert:* Verlässt sich auf die anfängliche Validierung, was schneller ist, aber Änderungen im USt-IdNr.-Status übersehen könnte.
    *   **Empfohlener Wert:** "An" für maximale Compliance und Genauigkeit.
    *   **Händlerszenario / Beispiel:** Die USt-IdNr. eines Geschäftskunden könnte im Laufe der Zeit ungültig werden. Die erneute Validierung stellt sicher, dass Sie nicht versehentlich 0% Umsatzsteuer auf eine ungültige Nummer anwenden.
*   **VIES-Anfragenflut verhindern (für X Minuten blockieren):**
    *   **Was diese Einstellung bewirkt:** Wenn ein Kunde wiederholt ungültige USt-IdNr. eingibt, blockiert diese Einstellung vorübergehend weitere Validierungsversuche für einen bestimmten Zeitraum, um Missbrauch oder eine Überlastung des VIES-Systems zu verhindern.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Nach mehreren fehlgeschlagenen Versuchen wird der Kunde vorübergehend daran gehindert, es erneut zu versuchen.
        *   *Wenn deaktiviert:* Kein Flutschutz, unbegrenzte Versuche sind erlaubt.
    *   **Empfohlener Wert:** "An" mit einer angemessenen Blockierungszeit (z. B. 5-10 Minuten).
    *   **Händlerszenario / Beispiel:** Ein Bot oder ein böswilliger Benutzer versucht, USt-IdNr. zu erraten. Diese Einstellung verhindert, dass sie die VIES-API kontinuierlich belasten.
*   **VIES-Validierungsergebnisse für X Stunden cachen:**
    *   **Was diese Einstellung bewirkt:** Speichert die Ergebnisse erfolgreicher VIES-Validierungen für eine bestimmte Anzahl von Stunden. Dies reduziert die Anzahl der direkten Aufrufe an das VIES-System, beschleunigt den Prozess und reduziert die Nutzung externer APIs.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Schnellere Validierung für wiederkehrende Kunden oder innerhalb des Cache-Zeitraums.
        *   *Wenn deaktiviert:* Jede Validierung ist ein Live-VIES-Aufruf, was langsamer sein kann.
    *   **Empfohlener Wert:** "An" mit einer Cache-Zeit von 24-72 Stunden (z. B. 48 Stunden).
    *   **Händlerszenario / Beispiel:** Ein Kunde validiert seine USt-IdNr. Wenn er innerhalb von 48 Stunden auf Ihre Website zurückkehrt, verwendet das Modul das zwischengespeicherte Ergebnis, anstatt eine neue VIES-Anfrage zu stellen.
*   **USt-Status des Warenkorbs alle X Sekunden erneut prüfen:**
    *   **Was diese Einstellung bewirkt:** Definiert, wie oft das Modul den USt-Status des Warenkorbs im Hintergrund erneut überprüft, besonders nützlich, wenn Preise dynamisch sind oder wenn der Kunde seine Adresse/USt-IdNr. während des Checkouts ändert.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf einen niedrigen Wert eingestellt:* Häufigere Updates, potenziell reibungsloseres Erlebnis, aber höhere Serverlast.
        *   *Wenn auf einen hohen Wert eingestellt:* Weniger häufige Updates, erfordert möglicherweise eine manuelle Seitenaktualisierung, damit USt-Änderungen wirksam werden.
    *   **Empfohlener Wert:** 5-10 Sekunden.
    *   **Händlerszenario / Beispiel:** Ein Kunde gibt seine USt-IdNr. ein, und innerhalb von 5 Sekunden aktualisiert sich der Warenkorb-Gesamtbetrag, um 0% Umsatzsteuer ohne Seitenneuladung widerzuspiegeln.
*   **Automatische USt-IdNr.-Revalidierung aktivieren (Cron Job):**
    *   **Was diese Einstellung bewirkt:** Aktiviert eine Hintergrundaufgabe (Cron Job), die alle gespeicherten USt-IdNr. der Kunden regelmäßig mit VIES revalidiert. Dies stellt sicher, dass auch alte USt-IdNr. gültig bleiben.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* USt-IdNr. werden regelmäßig auf Gültigkeit überprüft, um die Compliance zu gewährleisten.
        *   *Wenn deaktiviert:* USt-IdNr. werden nur zum Zeitpunkt der Eingabe oder Bestellung überprüft, was möglicherweise zu veralteten Informationen führt.
    *   **Empfohlener Wert:** "An" (Sehr empfohlen für langfristige Compliance).
    *   **Händlerszenario / Beispiel:** Ein Kunde hat vor 6 Monaten eine Bestellung mit einer gültigen USt-IdNr. aufgegeben. Der Cron Job überprüft sie erneut und stellt fest, dass sie jetzt ungültig ist, sodass Sie sie für zukünftige Bestellungen kennzeichnen können.
*   **Cron Job Revalidierungsintervall (Tage):**
    *   **Was diese Einstellung bewirkt:** Legt fest, wie oft der Cron Job zur Revalidierung von USt-IdNr. ausgeführt wird.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf eine niedrige Zahl eingestellt:* Häufigere Revalidierungen, höhere Genauigkeit, aber mehr VIES-Anfragen.
        *   *Wenn auf eine hohe Zahl eingestellt:* Weniger häufige Revalidierungen, geringere Genauigkeit, weniger VIES-Anfragen.
    *   **Empfohlener Wert:** 30-90 Tage (z. B. 60 Tage).
    *   **Händlerszenario / Beispiel:** Wenn Sie es auf 30 Tage einstellen, werden alle USt-IdNr. einmal im Monat erneut überprüft.
*   **VIES API-Schlüssel (Optional):**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Verwendung alternativer USt-IdNr.-Validierungs-APIs (wie Apilayer, AbstractAPI, VATStack) anstelle des Standard-VIES-Systems. Diese können manchmal robustere Funktionen oder Fallback-Optionen bieten.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ein Schlüssel eingegeben wird:* Das Modul versucht, die angegebene Drittanbieter-API zur Validierung zu verwenden.
        *   *Wenn leer:* Das Modul greift auf das offizielle VIES-System zurück.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben Probleme mit VIES oder benötigen spezifische Funktionen einer Drittanbieter-API. Wenn Sie eine verwenden, geben Sie den von diesem Dienst bereitgestellten Schlüssel ein.
    *   **Händlerszenario / Beispiel:** Wenn das VIES-System häufig ausgefallen oder langsam ist, könnten Sie den VAT-Validierungsdienst von Apilayer abonnieren und Ihren API-Schlüssel hier als zuverlässige Alternative eingeben.

#### **API-Schlüssel (Optional - für alternative USt-IdNr.-Validierungsdienste)**

*   **Apilayer API-Schlüssel:**
    *   **Was diese Einstellung bewirkt:** Geben Sie Ihren API-Schlüssel ein, wenn Sie den VAT-Validierungsdienst von Apilayer abonnieren.
    *   **Auswirkung einer Änderung dieser Einstellung:** Aktiviert die Validierung über Apilayer.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben ein Apilayer-Konto.
*   **AbstractAPI-Schlüssel:**
    *   **Was diese Einstellung bewirkt:** Geben Sie Ihren API-Schlüssel ein, wenn Sie den VAT-Validierungsdienst von AbstractAPI abonnieren.
    *   **Auswirkung einer Änderung dieser Einstellung:** Aktiviert die Validierung über AbstractAPI.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben ein AbstractAPI-Konto.
*   **VATStack API-Schlüssel:**
    *   **Was diese Einstellung bewirkt:** Geben Sie Ihren API-Schlüssel ein, wenn Sie den VAT-Validierungsdienst von VATStack abonnieren.
    *   **Auswirkung einer Änderung dieser Einstellung:** Aktiviert die Validierung über VATStack.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben ein VATStack-Konto.

#### **Konfigurations-Schnellreferenztabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Hauptkonfiguration | Ihr Land | Land Ihres Shops | Definiert Ihr Geschäftsland für innergemeinschaftliche Verkäufe. |
| Hauptkonfiguration | Berechtigte Länder | Alle EU-Länder | Wählt EU-Länder aus, in denen 0% Umsatzsteuer gilt. |
| Hauptkonfiguration | Steuerregel auswählen | Ihre 0%-Steuerregel | Gibt die PrestaShop-Steuerregel für 0% Umsatzsteuer an. |
| Hauptkonfiguration | Modul für ausgewählte Sprachen deaktivieren | Leer | Deaktiviert das Modul für bestimmte Sprachen. |
| Hauptkonfiguration | USt-IdNr.-Änderungsformular in der Kopfzeile anzeigen | Aus | Zeigt das USt-IdNr.-Formular im Header an. |
| Hauptkonfiguration | USt-IdNr.-Änderungsformular in displayCustomhtml1 anzeigen | Aus | Zeigt das USt-IdNr.-Formular im benutzerdefinierten Theme-Hook an. |
| Hauptkonfiguration | USt-IdNr.-Statusleiste für angemeldete Kunden anzeigen | An | Zeigt angemeldeten Benutzern den USt-IdNr.-Status an. |
| Hauptkonfiguration | USt-IdNr.-Leiste im Checkout-Schritt "Persönliche Informationen" anzeigen | An (Sehr empfohlen) | Zeigt das USt-IdNr.-Feld im ersten Checkout-Schritt an. |
| Hauptkonfiguration | USt-IdNr.-Leiste in der Checkout-Zusammenfassung anzeigen | An | Zeigt den USt-IdNr.-Status in der Checkout-Zusammenfassung an. |
| Hauptkonfiguration | USt-IdNr.-Leiste im Zahlungsschritt anzeigen | An | Zeigt den USt-IdNr.-Status im Zahlungsschritt an. |
| Hauptkonfiguration | USt-IdNr.-Änderungsleiste auf der Produktseite anzeigen | Aus | Zeigt das USt-IdNr.-Formular auf Produktseiten an. |
| Hauptkonfiguration | USt-IdNr.-Änderungsformular in displayProductAdditionalInfo anzeigen | Aus | Zeigt das USt-IdNr.-Formular im Hook für zusätzliche Produktinformationen an. |
| Hauptkonfiguration | USt-IdNr.-Änderungsformular in displayBanner anzeigen | Aus | Zeigt das USt-IdNr.-Formular im Banner-Hook an. |
| Hauptkonfiguration | Reverse Charge Hinweis auf der Rechnung | An (Sehr empfohlen) | Fügt Rechnungen den gesetzlich vorgeschriebenen "Reverse Charge"-Hinweis hinzu. |
| Hauptkonfiguration | USt-IdNr. des Kunden bei jeder Bestellung erneut validieren | An | Überprüft die USt-IdNr. bei jeder neuen Bestellung erneut. |
| Hauptkonfiguration | VIES-Anfragenflut verhindern (für X Minuten blockieren) | An (5-10 Minuten) | Blockiert wiederholte ungültige USt-IdNr.-Versuche. |
| Hauptkonfiguration | VIES-Validierungsergebnisse für X Stunden cachen | An (24-72 Stunden) | Speichert VIES-Ergebnisse, um die Validierung zu beschleunigen. |
| Hauptkonfiguration | USt-Status des Warenkorbs alle X Sekunden erneut prüfen | 5-10 Sekunden | Wie oft der USt-Status des Warenkorbs aktualisiert wird. |
| Hauptkonfiguration | Automatische USt-IdNr.-Revalidierung aktivieren (Cron Job) | An (Sehr empfohlen) | Aktiviert die Hintergrund-Revalidierung aller USt-IdNr. |
| Hauptkonfiguration | Cron Job Revalidierungsintervall (Tage) | 30-90 Tage (z. B. 60) | Häufigkeit der Cron Job Revalidierung. |
| Hauptkonfiguration | Apilayer API-Schlüssel | Leer | Schlüssel für den Apilayer USt-IdNr.-Validierungsdienst. |
| Hauptkonfiguration | AbstractAPI-Schlüssel | Leer | Schlüssel für den AbstractAPI USt-IdNr.-Validierungsdienst. |
| Hauptkonfiguration | VATStack API-Schlüssel | Leer | Schlüssel für den VATStack USt-IdNr.-Validierungsdienst. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### **USt-IdNr.-Validierungsprüfung (Back Office > Kunden > USt-IdNr.-Validierungsprüfung)**

Dieser spezielle Bereich ermöglicht es Ihnen, alle USt-IdNr.-Validierungsversuche, die über Ihren Shop vorgenommen wurden, zu überprüfen und zu verwalten.

*   **Bildschirmname & Menüpfad:** **Kunden > USt-IdNr.-Validierungsprüfung** (Dieser neue Menüpunkt wird vom Modul hinzugefügt).
*   **Verfügbare Aktionen & Einstellungen:**
    *   **Raster- / Verwaltungsansicht:** Dieser Bildschirm präsentiert eine Tabelle (Raster) aller USt-IdNr.-Validierungsversuche. Für jeden Eintrag sehen Sie typischerweise:
        *   **Kundenname:** Der Name des Kunden, der mit der Validierung verbunden ist.
        *   **USt-IdNr.:** Die eingegebene USt-IdNr.
        *   **Land:** Der Ländercode, der mit der USt-IdNr. verbunden ist.
        *   **Validierungsstatus:** Ob die USt-IdNr. "Gültig", "Ungültig" oder "Fehler" war (z. B. VIES-System nicht verfügbar).
        *   **Validierungsdatum:** Wann der Validierungsversuch stattfand.
        *   **Bestell-ID:** Wenn die Validierung zu einer Bestellung führte, die zugehörige Bestell-ID.
        *   **Quelle:** Wo die Validierung stattfand (z. B. "Checkout", "Kundenkonto").
        *   **Details/Grund:** Weitere Informationen zum Validierungsergebnis, insbesondere bei ungültigen Einträgen.
    *   **Filtern und Sortieren:** Sie können die Liste normalerweise nach Kunde, USt-IdNr., Status oder Datumsbereich filtern, um bestimmte Einträge zu finden. Das Sortieren ermöglicht es Ihnen, die Daten zu organisieren.
    *   **Exportieren:** Das Modul bietet möglicherweise eine Option zum Exportieren dieses Audit-Logs an, was für Buchhaltungs- und Steuerprüfungen nützlich ist.
*   **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Prüfung und Berichterstattung. Sie können den USt-IdNr.-Status eines Kunden hier nicht direkt ändern, aber Sie können die Historie der Validierungen überprüfen. Diese Daten sind entscheidend, um die Compliance bei Steuerprüfungen nachzuweisen.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Überprüfen Sie dieses Audit-Log regelmäßig, insbesondere wenn Sie Unstimmigkeiten bei der Umsatzsteueranwendung feststellen oder Kundenanfragen zur Umsatzsteuer erhalten.
    2.  Suchen Sie nach den Status "Ungültig" oder "Fehler", um potenzielle Probleme mit der Kundeneingabe oder der Verfügbarkeit des VIES-Systems zu identifizieren.
    3.  Verwenden Sie die Exportfunktion, um Ihrem Buchhalter oder den Steuerbehörden bei Bedarf Daten zur Verfügung zu stellen.

### 2.3 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| USt-IdNr.-Validierungsprüfung | Rasteransicht | N/A | Zeigt ein historisches Protokoll aller USt-IdNr.-Validierungsversuche an. |
| USt-IdNr.-Validierungsprüfung | Filter & Sortierung | N/A | Hilft beim Auffinden spezifischer Validierungseinträge. |
| USt-IdNr.-Validierungsprüfung | Daten exportieren | N/A | Ermöglicht den Export des Audit-Logs für Aufzeichnungen und Steuerzwecke. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden geben gültige USt-IdNr. ein, aber 0% Umsatzsteuer wird nicht angewendet.**
*   **A:**
    1.  **Einstellung "Ihr Land" überprüfen:** Stellen Sie sicher, dass sie in der Modulkonfiguration korrekt auf das Land Ihres Shops eingestellt ist.
    2.  **"Berechtigte Länder" überprüfen:** Stellen Sie sicher, dass das Land des Kunden in der Liste der berechtigten Länder ausgewählt ist.
    3.  **"Steuerregel auswählen" bestätigen:** Stellen Sie sicher, dass Sie eine 0%-Steuerregel in PrestaShop (**International > Steuern > Steuerregeln**) erstellt haben und dass diese in den Moduleinstellungen korrekt ausgewählt ist.
    4.  **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren". Manchmal kann ein alter Cache verhindern, dass neue Einstellungen wirksam werden.
    5.  **VIES-Verfügbarkeit prüfen:** Das VIES-System kann manchmal vorübergehend nicht verfügbar sein. Sie können den Status auf der offiziellen Website der Europäischen Kommission überprüfen.

**F2: Das USt-IdNr.-Validierungsformular wird auf meiner Checkout-Seite nicht angezeigt.**
*   **A:**
    1.  **Anzeigeeinstellungen überprüfen:** Stellen Sie in der Modulkonfiguration sicher, dass "USt-IdNr.-Leiste im Checkout-Schritt 'Persönliche Informationen' anzeigen" (und andere relevante Anzeigeoptionen) auf "An" gesetzt ist.
    2.  **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, kann es Standard-PrestaShop-Hooks überschreiben. Überprüfen Sie, ob Ihr Theme spezifische Bereiche für `displayProductAdditionalInfo`, `displayCustomhtml1` oder andere Hooks hat, in denen Sie versucht haben, das Formular zu platzieren. Möglicherweise müssen Sie Ihren Theme-Entwickler konsultieren.
    3.  **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Checkout-bezogene Module, um festzustellen, ob ein Konflikt vorliegt.

**F3: Ich sehe "Fehler" oder "VIES nicht verfügbar" Meldungen während der Validierung.**
*   **A:**
    1.  **VIES-Systemstatus:** Das VIES-System kann Ausfallzeiten haben. Überprüfen Sie die offizielle VIES-Website auf den aktuellen Status.
    2.  **cURL-Erweiterung:** Stellen Sie sicher, dass Ihr Hosting-Anbieter die PHP-Erweiterung `cURL` aktiviert hat. Dies ist unerlässlich, damit das Modul mit externen APIs wie VIES kommunizieren kann. Kontaktieren Sie Ihren Host, wenn Sie unsicher sind.
    3.  **Firewall/Sicherheit:** Die Firewall oder Sicherheitseinstellungen Ihres Servers könnten ausgehende Verbindungen zum VIES-Server blockieren. Wenden Sie sich auch hier an Ihren Hosting-Anbieter.
    4.  **API-Schlüssel:** Wenn Sie versuchen, eine Drittanbieter-API (Apilayer, AbstractAPI, VATStack) zu verwenden, stellen Sie sicher, dass der API-Schlüssel korrekt eingegeben und bei diesem Dienst aktiv ist.

**F4: Wie stelle ich sicher, dass der Cron Job für die Revalidierung läuft?**
*   **A:**
    1.  **Cron Job aktivieren:** Stellen Sie in der Modulkonfiguration sicher, dass "Automatische USt-IdNr.-Revalidierung aktivieren (Cron Job)" auf "An" steht.
    2.  **PrestaShop Cron Modul:** Sie benötigen ein separates PrestaShop Cron Job Modul (z. B. "Cron tasks manager" von PrestaShop), das installiert und konfiguriert ist, um die Cron-Aufgabe des Moduls regelmäßig auszulösen.
    3.  **Hosting Cron:** Alternativ können Sie einen Server-Level-Cron Job (über cPanel, Plesk oder SSH) einrichten, um die Cron-URL des Moduls aufzurufen. Die Modulkonfiguration stellt normalerweise die genaue URL zur Verfügung.
    4.  **Audit-Log überprüfen:** Nachdem der Cron Job hätte laufen sollen, überprüfen Sie den Bildschirm "USt-IdNr.-Validierungsprüfung" im Back Office. Sie sollten neue Validierungseinträge mit der Quelle "Cron" sehen.

**F5: Warum werden einige EU-Länder nicht in der Liste der "Berechtigten Länder" angezeigt?**
*   **A:** Das Modul greift auf die PrestaShop-Länderliste zurück. Stellen Sie sicher, dass alle gewünschten EU-Länder in Ihrem PrestaShop-Shop (**International > Standorte > Länder**) aktiviert sind und dass sie als "Ist ein EU-Land" und "Enthält Bundesstaaten" (falls zutreffend) markiert sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls "USt-IdNr. in VIES validieren und 0% USt. festlegen", konzipiert für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einem Standard-PrestaShop MVC-Muster (Model-View-Controller) und nutzt Hooks stark für die Integration in das Front- und Back-Office. Es führt mehrere benutzerdefinierte Klassen für Geschäftslogik, API-Interaktion und Datenverwaltung ein. Zu den Schlüsselkomponenten gehören:

*   **Hauptmodulklasse (`eurovat.php`):** Verwaltet Installation, Deinstallation, Hook-Registrierung und das primäre Konfigurationsformular (`getContent()`).
*   **Front Controller:** Verwalten AJAX-Anfragen für die USt-IdNr.-Validierung und Formularübermittlungen.
*   **Admin Controller:** Bieten dedizierte Schnittstellen für die USt-IdNr.-Validierungsprüfung.
*   **Core-Klassen:** Kapseln die Geschäftslogik für die VIES-Interaktion, Steuerverwaltung, Analyse und Datenpersistenz (oft erweitern sie `ObjectModel` oder verwenden ein Repository-Muster).
*   **Templates:** Smarty-Templates zum Rendern von Front-Office-Formularen, Back-Office-Konfiguration und Audit-Ansichten.
*   **Hooks:** Umfassende Nutzung von Hooks, um Funktionen an verschiedenen Stellen im PrestaShop-Lebenszyklus einzuschleusen (z. B. Produktseite, Checkout, Auftragsabwicklung, Admin-Kundenansicht).

### 4.2 Controller (`controllers/`)

#### Front-Office Controller

*   `controllers/front/cron.php`
    *   **Klassenname:** `EurovatCronModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Verwaltet die Ausführung des Cron Jobs des Moduls. Dieser Controller wird typischerweise von einem externen Cron-Dienst (z. B. Server-Cron oder PrestaShop's `Cron tasks manager`-Modul) aufgerufen, um Hintergrundaufgaben wie die Revalidierung von USt-IdNr. auszulösen. Er verarbeitet den `ActionCronJob`-Hook.
*   `controllers/front/form.php`
    *   **Klassenname:** `EurovatFormModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Verwaltet wahrscheinlich die Anzeige und Übermittlung des USt-IdNr.-Eingabeformulars in verschiedenen Front-Office-Kontexten (z. B. Produktseite, benutzerdefinierte HTML-Blöcke). Es könnte `views/templates/front/form.tpl` rendern.
*   `controllers/front/index.php`
    *   **Klassenname:** `EurovatIndexModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Ein generischer Front Controller, potenziell für Fallback oder einfache Anzeigelogik verwendet. Oft dient `index.php` in einem Controller-Verzeichnis als Platzhalter oder Basis für andere Controller.
*   `controllers/front/validate.php`
    *   **Klassenname:** `EurovatValidateModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Der zentrale AJAX-Endpunkt für die Echtzeit-USt-IdNr.-Validierung. Er empfängt USt-IdNr.- und Länderdaten, interagiert mit dem VIES-Client und gibt eine JSON-Antwort zurück, die die Gültigkeit anzeigt und möglicherweise den Steuerstatus des Warenkorbs aktualisiert.

#### Back-Office Admin Controller

*   `controllers/admin/AdminEurovatVatValidationAuditController.php`
    *   **Klassenname:** `AdminEurovatVatValidationAuditController` (erweitert `ModuleAdminController`)
    *   **Tab-Name:** "USt-IdNr.-Validierungsprüfung" (unter dem Menü "Kunden")
    *   **Verwaltete Entität:** `EurovatValidation` (benutzerdefinierte Tabelle `ps_eurovat_validation`)
    *   **Verantwortlichkeit:** Bietet die administrative Schnittstelle zum Anzeigen, Filtern und Verwalten des Audit-Logs aller USt-IdNr.-Validierungsversuche. Es verwendet PrestaShop's `HelperList` oder `Grid`-Komponenten, um die Daten aus der Tabelle `ps_eurovat_validation` anzuzeigen.
*   `controllers/admin/index.php`
    *   **Klassenname:** `EurovatIndexAdminController` (erweitert `ModuleAdminController`)
    *   **Verantwortlichkeit:** Ähnlich wie das Front-Office `index.php` ist dies wahrscheinlich ein Platzhalter oder ein Basis-Controller. Er könnte zur Hauptkonfiguration oder zum Audit-Controller weiterleiten.

### 4.3 Core-Klassen & Modelle (`classes/`)

*   `classes/EurovatAlertService.php`
    *   **Verantwortlichkeit:** Verwaltet und zeigt Warnungen oder Benachrichtigungen innerhalb des Moduls an, möglicherweise im Zusammenhang mit dem VIES-Status, API-Schlüsselproblemen oder Konfigurationsproblemen.
*   `classes/EurovatAlertsHelper.php`
    *   **Verantwortlichkeit:** Eine Helferklasse für `EurovatAlertService`, die Dienstfunktionen für die Warnungsverwaltung bereitstellt.
*   `classes/EurovatAnalyticsService.php`
    *   **Verantwortlichkeit:** Sammelt und verarbeitet Daten im Zusammenhang mit der USt-IdNr.-Validierung, wie Erfolgsraten, Fehlertypen und API-Nutzung, möglicherweise zur Anzeige in einem Dashboard-Widget.
*   `classes/EurovatApiUsageHelper.php`
    *   **Verantwortlichkeit:** Verfolgt und verwaltet die Nutzung externer USt-IdNr.-Validierungs-APIs (VIES, Apilayer usw.), möglicherweise unter Implementierung von Ratenbegrenzungen oder Überwachung.
*   `classes/EurovatAuditHelper.php`
    *   **Verantwortlichkeit:** Unterstützt `AdminEurovatVatValidationAuditController` bei der Verwaltung und Abfrage der Tabelle `ps_eurovat_validation`.
*   `classes/EurovatConfiguration.php`
    *   **Verantwortlichkeit:** Eine statische oder Singleton-Klasse zur Zentralisierung des Zugriffs auf Modulkonfigurationswerte (`Configuration::get('EUROVAT_...')`). Bietet eine sauberere Möglichkeit, Einstellungen abzurufen.
*   `classes/EurovatCronHelper.php`
    *   **Verantwortlichkeit:** Enthält die Logik, die vom Cron Job ausgeführt wird, wie das Iterieren durch Kunden-USt-IdNr. und das Initiieren der Revalidierung.
*   `classes/EurovatErrorClassifier.php`
    *   **Verantwortlichkeit:** Kategorisiert und liefert benutzerfreundliche Meldungen für verschiedene Arten von USt-IdNr.-Validierungsfehlern (z. B. ungültiges Format, VIES nicht verfügbar, Länderkonflikt).
*   `classes/EurovatExportService.php`
    *   **Verantwortlichkeit:** Verwaltet den Export von USt-IdNr.-Validierungs-Auditdaten, wahrscheinlich im CSV- oder Excel-Format.
*   `classes/EurovatOrderProofHelper.php`
    *   **Verantwortlichkeit:** Sammelt und bereitet Daten im Zusammenhang mit der USt-IdNr.-Validierung für eine bestimmte Bestellung vor, die zur Erstellung eines Nachweises der 0%-USt-Anwendung verwendet werden.
*   `classes/EurovatOrderTaxNormalizer.php`
    *   **Verantwortlichkeit:** Passt die Steuerdetails der Bestellung an, wenn 0% Umsatzsteuer angewendet wird, um die Konsistenz über Warenkorb, Bestellung und Rechnung hinweg zu gewährleisten.
*   `classes/EurovatProofPackService.php`
    *   **Verantwortlichkeit:** Erstellt möglicherweise ein "Nachweispaket" (z. B. ein PDF-Dokument), das alle notwendigen Beweise für eine 0%-USt-Transaktion enthält.
*   `classes/EurovatTaxManager.php`
    *   **Verantwortlichkeit:** Die zentrale Klasse zum Anwenden und Verwalten von Steueränderungen basierend auf USt-IdNr.-Validierungsergebnissen, die mit dem PrestaShop-Steuersystem interagiert.
*   `classes/EurovatTaxService.php`
    *   **Verantwortlichkeit:** Bietet Dienstmethoden im Zusammenhang mit Steuerberechnungen und -anwendungen innerhalb des Moduls.
*   `classes/EurovatValidationRepository.php`
    *   **Mit welcher Datenbanktabelle es interagiert:** `ps_eurovat_validation`
    *   **Ob es `ObjectModel` erweitert:** Wahrscheinlich nicht direkt, sondern verwaltet `EurovatValidation`-Objekte oder rohe Datenbankabfragen.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** CRUD-Operationen für USt-IdNr.-Validierungsdatensätze, Abfrage der Validierungshistorie, Speichern von Validierungsergebnissen.
*   `classes/EurovatViesClient.php`
    *   **Verantwortlichkeit:** Die primäre Schnittstelle zur Kommunikation mit dem VIES-System (oder alternativen APIs wie Apilayer, AbstractAPI, VATStack). Verwaltet API-Anfragen, -Antworten und Fehlerbehandlung.
*   `classes/index.php`
    *   **Verantwortlichkeit:** Ein Sicherheitsplatzhalter, um das Auflisten von Verzeichnissen zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

*   `eurovat/views/js/adminEurovatAlerts.js`
    *   **Geltungsbereich:** Back-Office
    *   **Beschreibung:** Verwaltet die Anzeige und Interaktion mit Warnungen im Admin-Panel, möglicherweise dynamische Updates oder ausblendbare Nachrichten.
*   `eurovat/views/js/adminEurovatCountries.js`
    *   **Geltungsbereich:** Back-Office
    *   **Beschreibung:** Verwaltet die Länderauswahloberfläche in der Modulkonfiguration, möglicherweise mit Mehrfachauswahlfunktion oder dynamischer Filterung.
*   `eurovat/views/js/adminEurovatCron.js`
    *   **Geltungsbereich:** Back-Office
    *   **Beschreibung:** Bietet UI-Logik für die Cron-Job-Einstellungen, möglicherweise Anzeige der letzten Ausführungszeiten, der nächsten geplanten Ausführung oder manueller Auslöseoptionen.
*   `eurovat/views/js/adminEurovatDashboard.js`
    *   **Geltungsbereich:** Back-Office
    *   **Beschreibung:** Betreibt das Dashboard-Widget (falls vorhanden), das Analysen oder Schlüsselkennzahlen zur USt-IdNr.-Validierung anzeigt. Verwendet AJAX, um Daten abzurufen und möglicherweise Diagrammbibliotheken.
*   `eurovat/views/js/adminEurovatTooltips.js`
    *   **Geltungsbereich:** Back-Office
    *   **Beschreibung:** Initialisiert und verwaltet Tooltips für Konfigurationsoptionen im Admin-Panel, die hilfreichen Kontext bieten.
*   `eurovat/views/js/eurovat.js`
    *   **Geltungsbereich:** Front-Office
    *   **Beschreibung:** Das Haupt-Front-Office-JavaScript.
        *   **Event-Listener:** Bindet an Eingabeereignisse im USt-IdNr.-Feld (z. B. `keyup`, `change`), Formularübermittlungen und möglicherweise `prestashop.on('updateCart')` oder ähnliche Ereignisse.
        *   **DOM-Manipulation:** Zeigt dynamisch Validierungsstatusmeldungen (gültig/ungültig) an, aktualisiert Warenkorb-Gesamtbeträge, zeigt/versteckt Elemente basierend auf dem USt-IdNr.-Status.
        *   **AJAX-Aufrufe:** Sendet USt-IdNr.- und Länderdaten an `controllers/front/validate.php` zur Echtzeit-Validierung.
        *   **Sonstiges:** Implementiert das Intervall "USt-Status des Warenkorbs erneut prüfen", Flutschutzlogik.
*   `eurovat/views/js/eurovatBoMockConsole.js`
    *   **Geltungsbereich:** Back-Office (Entwicklung/Debugging)
    *   **Beschreibung:** Wahrscheinlich ein Dienstprogramm zum Mocken der Konsolenausgabe oder zur Bereitstellung erweiterter Debugging-Funktionen innerhalb des PrestaShop Back Office, wird normalerweise nicht in der Produktion verwendet.

### 4.5 CSS-Stylesheets (`views/css/`)

*   `eurovat/views/css/admin_eurovat.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Haupt-UI-Komponenten und Container, die es stylt:** Konfigurationsseitenelemente, Audit-Listen-Tabelle, Dashboard-Widgets, Warnungen und Tooltips innerhalb der Admin-Oberfläche des Moduls.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** `.eurovat-admin-config`, `.eurovat-alert`, `.eurovat-dashboard-widget`, `.eurovat-audit-table`.
*   `eurovat/views/css/eurovat.css`
    *   **Geltungsbereich:** Front-Office-Kunden-Styling.
    *   **Haupt-UI-Komponenten und Container, die es stylt:** USt-IdNr.-Eingabefelder, Validierungsstatusmeldungen (Erfolg/Fehler), USt-IdNr.-Statusleisten im Header/Produktseite/Checkout, Reverse Charge Hinweise.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** `.eurovat-vat-form`, `.eurovat-status-message.valid`, `.eurovat-status-message.invalid`, `.eurovat-header-bar`, `.eurovat-product-vat-info`, `.eurovat-checkout-vat-status`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

*   `eurovat/views/templates/hook/adminDashboardWidget.tpl`
    *   **Hook:** Potenziell `displayAdminHomeQuickview` oder ein benutzerdefinierter Dashboard-Hook.
    *   **Ausgabe:** Ein Widget für das PrestaShop-Admin-Dashboard, das Analysen oder schnelle Statistiken zur USt-IdNr.-Validierung anzeigt.
*   `eurovat/views/templates/hook/adminOrderProofPack.tpl`
    *   **Hook:** `displayAdminOrder` oder `displayAdminOrderTabContent` (auf der Bestellansichtsseite).
    *   **Ausgabe:** Ein Block oder Tab innerhalb der Admin-Bestelldetailseite, der Administratoren ermöglicht, USt-Nachweisdokumente für eine bestimmte Bestellung anzuzeigen oder zu generieren.
*   `eurovat/views/templates/hook/customerHistory.tpl`
    *   **Hook:** `displayCustomerAccount` oder `displayMyAccountBlock`.
    *   **Ausgabe:** Informationen zur USt-IdNr.-Validierungshistorie oder zum aktuellen Status des Kunden in seinem persönlichen Kontobereich.
*   `eurovat/views/templates/hook/displayBanner.tpl`
    *   **Hook:** `displayBanner` (oder ähnlicher globaler Banner-Hook).
    *   **Ausgabe:** Das USt-IdNr.-Eingabeformular oder eine Werbebotschaft über 0% Umsatzsteuer, typischerweise oben im Shop angezeigt.

#### Admin-Templates (`views/templates/admin/`)

*   `eurovat/views/templates/admin/alerts.tpl`
    *   **Ausgabe:** HTML-Struktur zum Anzeigen verschiedener Warnungen und Benachrichtigungen im Back Office.
*   `eurovat/views/templates/admin/audit.tpl`
    *   **Ausgabe:** Das Haupttemplate für den `AdminEurovatVatValidationAuditController`, das die USt-IdNr.-Validierungsprüfungsliste rendert.
*   `eurovat/views/templates/admin/configure.tpl`
    *   **Ausgabe:** Das primäre Konfigurationsformular für das Modul, gerendert von `getContent()` in `eurovat.php`. Enthält alle in Abschnitt 4.1 beschriebenen Einstellungen.
*   `eurovat/views/templates/admin/countriesSelector.tpl`
    *   **Ausgabe:** Ein wiederverwendbares Template für die Länderauswahloberfläche innerhalb der Konfiguration.
*   `eurovat/views/templates/admin/cron.tpl`
    *   **Ausgabe:** Der Konfigurationsbereich für die Cron-Job-Einstellungen, einschließlich Intervall und Aktivierung.
*   `eurovat/views/templates/admin/dashboard.tpl`
    *   **Ausgabe:** Die vollständige Dashboard-Ansicht, die möglicherweise `adminDashboardWidget.tpl` und andere Analysen integriert.
*   `eurovat/views/templates/admin/hooksRepair.tpl`
    *   **Ausgabe:** Ein Dienstprogramm-Template, möglicherweise zur Diagnose und Reparatur fehlender oder falsch registrierter Hooks.
*   `eurovat/views/templates/admin/proof_pack_view.tpl`
    *   **Ausgabe:** Eine detaillierte Ansicht für ein USt-Nachweispaket, wahrscheinlich innerhalb der Bestelldetailseite.
*   `eurovat/views/templates/admin/vat_audit_list_settings.tpl`
    *   **Ausgabe:** Einstellungen oder Filter speziell für die Anzeige der USt-IdNr.-Prüfungsliste.
*   `eurovat/views/templates/admin/vat_audit_tabs.tpl`
    *   **Ausgabe:** Tab-Navigation für den USt-IdNr.-Prüfungsbereich, falls es mehrere Unterabschnitte gibt (z. B. Audit-Log, Analysen).

#### Front-Office-Templates (`views/templates/front/`)

*   `eurovat/views/templates/front/form.tpl`
    *   **Ausgabe:** Die Kern-HTML-Struktur für das USt-IdNr.-Eingabeformular, das in verschiedenen Front-Office-Hooks (Produktseite, Checkout, Header) verwendet wird.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

*   `ps_eurovat_validation`
    *   **Zweck:** Speichert ein historisches Protokoll aller USt-IdNr.-Validierungsversuche.
    *   **Schlüsselfelder (erwartet):**
        *   `id_eurovat_validation` (Primärschlüssel)
        *   `id_customer` (Fremdschlüssel zu `ps_customer`)
        *   `id_cart` (Fremdschlüssel zu `ps_cart`)
        *   `id_order` (Fremdschlüssel zu `ps_order`)
        *   `vat_number` (Die eingegebene USt-IdNr.)
        *   `country_code` (Der Ländercode, der mit der USt-IdNr. verbunden ist)
        *   `validation_status` (z. B. 'valid', 'invalid', 'error')
        *   `validation_response` (Rohe Antwort von VIES/API)
        *   `validation_date` (Zeitstempel der Validierung)
        *   `source` (z. B. 'checkout', 'customer_account', 'cron')
        *   `ip_address` (IP-Adresse des Benutzers, der die Validierung durchgeführt hat)

*   `ps_configuration`
    *   **Zweck:** Speichert alle Modulkonfigurationseinstellungen.
    *   **Wichtige Konfigurationsschlüssel:**
        *   `EUROVAT_YOUR_COUNTRY`
        *   `EUROVAT_ELIGIBLE_COUNTRIES`
        *   `EUROVAT_TAX_RULE`
        *   `EUROVAT_DISPLAY_HEADER`
        *   `EUROVAT_DISPLAY_CUSTOMHTML1`
        *   `EUROVAT_DISPLAY_LOGGED_STATUS`
        *   `EUROVAT_DISPLAY_CHECKOUT_PERSONAL`
        *   `EUROVAT_DISPLAY_CHECKOUT_SUMMARY`
        *   `EUROVAT_DISPLAY_CHECKOUT_PAYMENT`
        *   `EUROVAT_DISPLAY_PRODUCT_PAGE`
        *   `EUROVAT_REVERSE_CHARGE_NOTE`
        *   `EUROVAT_REVALIDATE_ON_ORDER`
        *   `EUROVAT_FLOOD_OFF_MINUTES`
        *   `EUROVAT_CACHE_TTL_HOURS`
        *   `EUROVAT_CART_RECHECK_INTERVAL`
        *   `EUROVAT_CRON_REVALIDATE_ENABLED`
        *   `EUROVAT_CRON_INTERVAL_DAYS`
        *   `EUROVAT_APILAYER_KEY`
        *   `EUROVAT_ABSTRACTAPI_KEY`
        *   `EUROVAT_VATSTACK_KEY`
        *   `EUROVAT_DISABLED_LANGS`

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS injizieren oder eine globale USt-IdNr.-Statusleiste anzeigen. |
| `displayProductAdditionalInfo` | Auf der Produktseite, typischerweise unter der Produktbeschreibung. | USt-IdNr.-Eingabeformular oder Status auf Produktseiten anzeigen. |
| `displayCustomhtml1` | Benutzerdefinierter Hook, oft im oberen Bereich des Themes (z. B. `sp_topdeals`). | USt-IdNr.-Eingabeformular in spezifischen Theme-Bereichen anzeigen. |
| `displayPaymentTop` | Oben im Zahlungsschritt des Checkouts. | USt-IdNr.-Status oder Formular vor der Zahlung anzeigen. |
| `displayBanner` | In einem Bannerbereich, typischerweise oben auf der Website. | USt-IdNr.-Eingabeformular oder Werbebotschaft anzeigen. |
| `displayAdminCustomers` | Auf der Kundenliste oder Kundendetailseite im BO. | USt-IdNr.-bezogene Informationen oder Aktionen für Kunden hinzufügen. |
| `ActionDispatcher` | Bevor ein Controller versendet wird. | Routing oder Kontext basierend auf dem USt-IdNr.-Status ändern. |
| `ActionGetProductPropertiesAfter` | Nachdem Produkteigenschaften abgerufen wurden. | Produktpreise basierend auf dem USt-IdNr.-Status des Kunden anpassen. |
| `ActionProductPriceCalculation` | Während der Produktpreisberechnung. | 0% Umsatzsteuer auf Produktpreise anwenden, falls berechtigt. |
| `ActionBeforeValidateOrder` | Kurz bevor eine Bestellung validiert wird. | Endgültige USt-IdNr.-Validierung durchführen, Bestellsteuern anpassen. |
| `ActionCronJob` | Ausgelöst durch das PrestaShop-Cron-Modul. | Hintergrundaufgaben wie die USt-IdNr.-Revalidierung ausführen. |
| `ActionObjectAddressUpdateAfter` | Nachdem ein Adressobjekt aktualisiert wurde (z. B. im Kundenkonto). | USt-IdNr. erneut validieren, wenn sich Adressdetails ändern. |
| `ActionTaxManager` | Wenn Steuerregeln verwaltet oder angewendet werden. | Steueranwendung basierend auf der USt-IdNr.-Validierung abfangen und ändern. |
| `ActionPresentCart` | Bevor der Warenkorb angezeigt wird. | Warenkorb-Gesamtbeträge aktualisieren und USt-IdNr.-Status anzeigen. |
| `ActionFilterDeliveryOptionList` | Filtert verfügbare Lieferoptionen. | Möglicherweise Lieferkosten basierend auf dem USt-IdNr.-Status anpassen (weniger häufig). |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal funktioniert und mit den neuesten PrestaShop-Versionen kompatibel bleibt.

*   **MyPresta.eu Bestellhistorie & Downloads:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
*   **MyPresta.eu Support:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
