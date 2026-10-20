---
title: "Responsive Popup-Gutscheine - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Responsive Popup-Gutscheine“ von MyPresta.eu."
sidebar:
  label: "Responsive Popup-Gutscheine - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Responsive popup coupons auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/responsive-popup-coupons.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/responsive-popup-coupons/)
>
> ---


# Responsive Popup-Gutscheine

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie alle Parameter für Ihre Popup-Gutscheine einrichten.

#### Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Popup-Gutschein-Funktionalität für Ihren Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Popup wird auf Ihren ausgewählten Seiten gemäß Ihren anderen Einstellungen angezeigt.
    - *Wenn deaktiviert:* Das Popup wird nirgendwo in Ihrem Shop angezeigt, unabhängig von anderen Einstellungen.
  - **Empfohlener Wert:** JA (wenn Sie das Modul verwenden möchten).
  - **Händlerszenario / Beispiel:** Sie führen eine Feiertagsaktion durch und möchten das Popup für eine begrenzte Zeit aktivieren. Sie aktivieren es zu Beginn und deaktivieren es, sobald die Aktion endet.
- **Anzeigen auf:**

  - **Was diese Einstellung bewirkt:** Hier können Sie auswählen, auf welchen Seitentypen das Popup Ihren Kunden angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Startseite:* Popup erscheint nur auf der Hauptseite Ihres Shops.
    - *Kategorieseiten:* Popup erscheint, wenn Kunden Produktkategorien durchsuchen.
    - *Produktseiten:* Popup erscheint, wenn Kunden einzelne Produktdetails ansehen.
    - *CMS-Seiten:* Popup erscheint auf Informationsseiten wie „Über uns“ oder „Kontakt“.
    - *Alle Seiten:* Popup erscheint auf jeder Seite Ihres Shops.
  - **Empfohlener Wert:** Produktseiten oder Alle Seiten (abhängig von Ihrer Marketingstrategie).
  - **Händlerszenario / Beispiel:** Sie möchten Käufe direkt auf Produktseiten fördern, daher wählen Sie „Produktseiten“. Wenn Sie maximale Sichtbarkeit wünschen, könnten Sie „Alle Seiten“ wählen.
- **Verzögerung (in Sekunden) vor dem Erscheinen des Popups:**

  - **Was diese Einstellung bewirkt:** Steuert, wie lange nach dem Laden einer Seite das Popup wartet, bevor es erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 0 gesetzt:* Popup erscheint sofort beim Laden der Seite.
    - *Auf 5 gesetzt:* Popup erscheint 5 Sekunden nach dem Laden der Seite.
  - **Empfohlener Wert:** 3-5 Sekunden (ermöglicht Kunden, zuerst den Inhalt zu sehen).
  - **Händlerszenario / Beispiel:** Sie möchten Kunden nicht sofort überfordern. Eine Verzögerung von 3 Sekunden gibt ihnen einen Moment Zeit, sich zu orientieren, bevor das Angebot erscheint.
- **Popup nur einmal pro Sitzung anzeigen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob ein Kunde das Popup während eines einzigen Besuchs in Ihrem Shop mehrmals sieht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sobald ein Kunde das Popup sieht (und es möglicherweise schließt), wird er es erst wieder sehen, wenn er seinen Browser schließt und eine neue Sitzung beginnt.
    - *Wenn deaktiviert:* Das Popup könnte jedes Mal erscheinen, wenn er eine Seite besucht, auf der es konfiguriert ist.
  - **Empfohlener Wert:** JA (um Kunden nicht zu nerven).
  - **Händlerszenario / Beispiel:** Ein Kunde besucht mehrere Produktseiten. Wenn dies aktiviert ist, sieht er das Gutscheinangebot nur einmal, was Irritationen verhindert.
- **Popup nur einmal pro Kunde anzeigen (für immer):**

  - **Was diese Einstellung bewirkt:** Dies ist eine dauerhaftere Einstellung, die verhindert, dass ein eingeloggter Kunde das Popup jemals wieder sieht, sobald er es einmal gesehen hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul merkt sich, dass ein bestimmter Kunde (über sein Konto) das Popup gesehen hat und zeigt es ihm auch in zukünftigen Sitzungen nicht mehr an.
    - *Wenn deaktiviert:* Die Regel „einmal pro Sitzung“ gilt, oder wenn diese ausgeschaltet ist, wird es wiederholt angezeigt.
  - **Empfohlener Wert:** JA (für ein weniger aufdringliches Erlebnis für treue Kunden).
  - **Händlerszenario / Beispiel:** Sie möchten jedem Kunden die Möglichkeit geben, den Gutschein zu erhalten, ihn aber nicht ständig daran erinnern, wenn er ihn bereits gesehen oder verwendet hat.
- **Popup nur für Gäste anzeigen (nicht eingeloggte Kunden):**

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des Popups nur auf Besucher, die nicht in einem Kundenkonto angemeldet sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Nur neue oder wiederkehrende, nicht eingeloggte Besucher sehen das Popup. Eingeloggte Kunden nicht.
    - *Wenn deaktiviert:* Sowohl Gäste als auch eingeloggte Kunden sehen das Popup (vorbehaltlich anderer Anzeigeregeln).
  - **Empfohlener Wert:** JA (oft möchten Sie neue Besucher konvertieren, nicht unbedingt bestehenden treuen Kunden Rabatte anbieten).
  - **Händlerszenario / Beispiel:** Ihr Ziel ist es, neue Kunden zu gewinnen oder Erstkäufe zu fördern. Sie aktivieren dies, um Ihr Angebot auf potenzielle Neukunden zu konzentrieren.
- **Popup nur für ausgewählte Kundengruppen anzeigen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Kundengruppen (z.B. „Besucher“, „Kunden“, „Gäste“ oder von Ihnen erstellte benutzerdefinierte Gruppen) mit dem Popup anzusprechen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Gruppen ausgewählt sind:* Nur Kunden, die zu diesen Gruppen gehören, sehen das Popup.
    - *Wenn keine Gruppen ausgewählt sind (oder alle ausgewählt sind):* Alle Kunden sehen das Popup (vorbehaltlich anderer Regeln).
  - **Empfohlener Wert:** Wählen Sie „Gäste“ und „Besucher“, wenn Ihr Ziel die Neukundengewinnung ist.
  - **Händlerszenario / Beispiel:** Sie möchten Ihrer VIP-Kundengruppe einen Sonderrabatt anbieten. Sie würden hier nur diese Gruppe auswählen.
- **Popup nur für ausgewählte Länder anzeigen:**

  - **Was diese Einstellung bewirkt:** Beschränkt das Erscheinen des Popups basierend auf dem geografischen Standort des Kunden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Länder ausgewählt sind:* Nur Kunden aus diesen Ländern sehen das Popup.
    - *Wenn keine Länder ausgewählt sind (oder alle ausgewählt sind):* Alle Kunden sehen das Popup.
  - **Empfohlener Wert:** Wählen Sie bestimmte Länder aus, wenn Sie geografisch gezielte Aktionen haben, andernfalls lassen Sie es leer.
  - **Händlerszenario / Beispiel:** Sie führen eine Aktion durch, die exklusiv für Kunden in Frankreich und Deutschland ist. Sie würden nur diese beiden Länder auswählen.
- **Popup nur für ausgewählte Währungen anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Popups basierend auf der Währung, die der Kunde derzeit in Ihrem Shop verwendet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Währungen ausgewählt sind:* Nur Kunden, die diese Währungen verwenden, sehen das Popup.
    - *Wenn keine Währungen ausgewählt sind (oder alle ausgewählt sind):* Alle Kunden sehen das Popup.
  - **Empfohlener Wert:** Wählen Sie bestimmte Währungen aus, wenn Ihre Aktion währungsabhängig ist, andernfalls lassen Sie es leer.
  - **Händlerszenario / Beispiel:** Sie haben ein Sonderangebot für Kunden, die in USD bezahlen. Sie würden hier nur USD auswählen.
- **Popup nur für ausgewählte Sprachen anzeigen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob das Popup basierend auf der Sprache erscheint, die der Kunde für Ihren Shop ausgewählt hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Sprachen ausgewählt sind:* Nur Kunden, die Ihren Shop in diesen Sprachen anzeigen, sehen das Popup.
    - *Wenn keine Sprachen ausgewählt sind (oder alle ausgewählt sind):* Alle Kunden sehen das Popup.
  - **Empfohlener Wert:** Wählen Sie bestimmte Sprachen aus, wenn Ihr Popup-Inhalt nur für bestimmte Sprachen übersetzt ist, andernfalls lassen Sie es leer.
  - **Händlerszenario / Beispiel:** Ihre Popup-Nachricht ist nur auf Englisch und Spanisch verfügbar. Sie würden diese beiden Sprachen auswählen, um sicherzustellen, dass Kunden eine relevante Nachricht sehen.

#### Gutschein-Einstellungen

- **Gutscheinwert:**

  - **Was diese Einstellung bewirkt:** Definiert den Rabattbetrag oder Prozentsatz, der vom Gutschein angeboten wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 10 gesetzt:* Der Gutschein gewährt einen Rabatt von 10 Einheiten (z.B. 10 $, 10 €).
    - *Auf 15% gesetzt:* Der Gutschein gewährt einen Rabatt von 15%.
  - **Empfohlener Wert:** Ein überzeugender Rabatt (z.B. 10%, 5 $, 10 €).
  - **Händlerszenario / Beispiel:** Sie möchten einen Rabatt von 10% anbieten, also geben Sie hier „10%“ ein.
- **Gutscheintyp:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob der Gutschein ein fester Betrag oder ein Prozentsatz ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Prozentsatz:* Der „Gutscheinwert“ wird als Prozentsatz des Gesamtbestellwerts behandelt.
    - *Betrag:* Der „Gutscheinwert“ wird als fester Geldbetrag behandelt.
  - **Empfohlener Wert:** Prozentsatz (oft ansprechender für unterschiedliche Bestellgrößen).
  - **Händlerszenario / Beispiel:** Sie möchten 10% Rabatt geben, also wählen Sie „Prozentsatz“. Wenn Sie einen pauschalen Rabatt von 5 $ geben möchten, wählen Sie „Betrag“.
- **Gutschein Mindestbetrag:**

  - **Was diese Einstellung bewirkt:** Legt einen Mindestbestellwert fest, den ein Kunde erreichen muss, um den Gutschein verwenden zu können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 50 gesetzt:* Der Gutschein kann nur verwendet werden, wenn der Warenkorbwert 50 $ oder mehr beträgt.
    - *Auf 0 gesetzt (oder leer):* Es ist kein Mindestbestellwert erforderlich.
  - **Empfohlener Wert:** Ein angemessener Mindestbetrag, um Ihre Margen zu schützen, oder 0, wenn Sie jeden Kauf fördern möchten.
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass der Rabatt nur auf Bestellungen über 50 $ angewendet wird, also geben Sie „50“ ein.
- **Gutscheinablauf (in Tagen):**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele Tage der generierte Gutscheincode ab dem Zeitpunkt seiner Ausstellung gültig ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 7 gesetzt:* Der Gutschein läuft 7 Tage nach Erhalt durch den Kunden ab.
    - *Auf 0 gesetzt (oder leer):* Der Gutschein läuft nicht ab.
  - **Empfohlener Wert:** 7-30 Tage (schafft Dringlichkeit, ohne zu restriktiv zu sein).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden den Gutschein schnell verwenden, also legen Sie ein Ablaufdatum von 7 Tagen fest.
- **Gutscheinbeschreibung:**

  - **Was diese Einstellung bewirkt:** Bietet einen beschreibenden Namen für den Gutschein in Ihrem PrestaShop Back Office (z.B. im Bereich „Warenkorbregeln“). Dies dient Ihrer internen Referenz.
  - **Auswirkung der Änderung dieser Einstellung:** Dieser Text wird in Ihrem PrestaShop-Admin-Panel angezeigt, wenn Sie die generierten Warenkorbregeln anzeigen, und hilft Ihnen, deren Herkunft zu identifizieren. Er wird dem Kunden nicht angezeigt.
  - **Empfohlener Wert:** „Popup-Gutschein - [Datum]“ oder „Facebook Like Rabatt“.
  - **Händlerszenario / Beispiel:** Sie geben „Facebook Like Popup Rabatt“ ein, damit Sie genau wissen, woher diese Gutscheine stammen, wenn Sie Ihre Warenkorbregeln überprüfen.
- **Gutschein kostenloser Versand:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der Gutschein auch kostenlosen Versand für die Bestellung gewährt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Dem Kunden werden bei Verwendung dieses Gutscheins keine Versandkosten berechnet.
    - *Wenn deaktiviert:* Es fallen die Standardversandkosten an.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten kostenlosen Versand als starken Anreiz anbieten).
  - **Händlerszenario / Beispiel:** Sie möchten ein sehr attraktives Angebot machen, also aktivieren Sie kostenlosen Versand zusammen mit dem Rabatt.
- **Gutschein auf bestimmte Produkte anwenden:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Verwendung des Gutscheins auf bestimmte Produkte in Ihrem Shop zu beschränken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Produkte ausgewählt sind:* Der Gutschein funktioniert nur, wenn diese Produkte im Warenkorb sind.
    - *Wenn keine Produkte ausgewählt sind:* Der Gutschein gilt für alle Produkte im Warenkorb.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben eine spezifische Produktaktion.
  - **Händlerszenario / Beispiel:** Sie bewerben eine neue Schuhlinie. Sie wählen hier nur diese Schuhe aus, damit der Gutschein nur für diese funktioniert.
- **Gutschein auf bestimmte Kategorien anwenden:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Verwendung des Gutscheins auf Produkte innerhalb bestimmter Kategorien zu beschränken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Kategorien ausgewählt sind:* Der Gutschein funktioniert nur, wenn Produkte aus diesen Kategorien im Warenkorb sind.
    - *Wenn keine Kategorien ausgewählt sind:* Der Gutschein gilt für alle Produkte.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben eine spezifische Kategorieaktion.
  - **Händlerszenario / Beispiel:** Sie möchten alte Lagerbestände in Ihrer Kategorie „Sommerkollektion“ abverkaufen. Sie wählen hier diese Kategorie aus.
- **Gutschein auf bestimmte Hersteller anwenden:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Verwendung des Gutscheins auf Produkte bestimmter Marken/Hersteller zu beschränken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Hersteller ausgewählt sind:* Der Gutschein funktioniert nur, wenn Produkte dieser Hersteller im Warenkorb sind.
    - *Wenn keine Hersteller ausgewählt sind:* Der Gutschein gilt für alle Produkte.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben eine spezifische Markenaktion.
  - **Händlerszenario / Beispiel:** Sie haben eine Partnerschaft mit einer bestimmten Marke und möchten einen Rabatt nur auf deren Produkte anbieten.

#### Popup-Design & Inhalt

- **Popup-Breite (in Pixel):**

  - **Was diese Einstellung bewirkt:** Steuert die horizontale Größe des Popup-Fensters.
  - **Auswirkung der Änderung dieser Einstellung:** Eine größere Zahl macht das Popup breiter, eine kleinere Zahl macht es schmaler.
  - **Empfohlener Wert:** 600px - 800px (für gute Sichtbarkeit auf dem Desktop, responsives Design kümmert sich um Mobilgeräte).
  - **Händlerszenario / Beispiel:** Sie möchten, dass das Popup prominent, aber nicht zu breit ist, also stellen Sie es auf 700px ein.
- **Popup-Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe des Popup-Fensters fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert das visuelle Erscheinungsbild des Popups, um es an Ihre Marke anzupassen oder hervorzuheben.
  - **Empfohlener Wert:** Eine Farbe, die gut mit Ihrem Text und Ihrer Marke kontrastiert (z.B. #FFFFFF für Weiß, #F0F0F0 für Hellgrau).
  - **Händlerszenario / Beispiel:** Ihre Marke verwendet viel Blau, also wählen Sie einen hellblauen Hex-Code wie #E0F2F7.
- **Popup-Textfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des im Popup angezeigten Textes fest.
  - **Auswirkung der Änderung dieser Einstellung:** Gewährleistet die Lesbarkeit vor Ihrer gewählten Hintergrundfarbe.
  - **Empfohlener Wert:** Eine Farbe, die einen guten Kontrast bietet (z.B. #000000 für Schwarz, #333333 für Dunkelgrau).
  - **Händlerszenario / Beispiel:** Bei einem hellen Hintergrund wählen Sie eine dunkle Textfarbe wie #333333 für optimale Lesbarkeit.
- **Popup-Rahmenfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Rahmens um das Popup-Fenster fest.
  - **Auswirkung der Änderung dieser Einstellung:** Fügt dem Popup einen visuellen Rahmen hinzu.
  - **Empfohlener Wert:** Eine dezente Farbe, die Ihr Design ergänzt, oder eine kräftige Farbe, um es hervorzuheben (z.B. #CCCCCC für Hellgrau oder Ihre Markenakzentfarbe).
  - **Händlerszenario / Beispiel:** Sie möchten einen sauberen Look, also wählen Sie einen dezenten grauen Rahmen #DDDDDD.
- **Popup-Rahmenbreite (in Pixel):**

  - **Was diese Einstellung bewirkt:** Steuert die Dicke des Popup-Rahmens.
  - **Auswirkung der Änderung dieser Einstellung:** Eine höhere Zahl macht den Rahmen dicker.
  - **Empfohlener Wert:** 1-3px.
  - **Händlerszenario / Beispiel:** Sie möchten einen dünnen, eleganten Rahmen, also stellen Sie ihn auf 1px ein.
- **Popup-Rahmenradius (in Pixel):**

  - **Was diese Einstellung bewirkt:** Steuert die Rundung der Popup-Ecken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 0 gesetzt:* Scharfe, quadratische Ecken.
    - *Auf 10 gesetzt:* Leicht abgerundete Ecken.
    - *Auf 50 gesetzt (oder höher):* Sehr abgerundete, pillenartige Ecken.
  - **Empfohlener Wert:** 5-10px (für einen modernen, weichen Look).
  - **Händlerszenario / Beispiel:** Sie bevorzugen eine weichere Ästhetik, also stellen Sie den Rahmenradius auf 8px ein.
- **Popup-Schatten:**

  - **Was diese Einstellung bewirkt:** Fügt dem Popup einen Schatteneffekt hinzu, wodurch es über der Seite zu schweben scheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Popup hat einen dezenten Schatten, der ihm Tiefe verleiht.
    - *Wenn deaktiviert:* Das Popup hat keinen Schatten.
  - **Empfohlener Wert:** JA (fügt einen professionellen, modernen Touch hinzu).
  - **Händlerszenario / Beispiel:** Sie möchten, dass das Popup sich visuell vom Hintergrund abhebt, also aktivieren Sie den Schatten.
- **Popup-Schaltflächenfarbe schließen:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des „X“-Buttons fest, den Kunden zum Schließen des Popups verwenden.
  - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass der Schließen-Button sichtbar ist und zu Ihrem Design passt.
  - **Empfohlener Wert:** Eine kontrastierende Farbe für die Sichtbarkeit (z.B. #000000, #FF0000).
  - **Händlerszenario / Beispiel:** Sie möchten, dass der Schließen-Button deutlich sichtbar ist, also stellen Sie ihn auf Schwarz #000000 ein.
- **Popup-Inhalt (HTML erlaubt):**

  - **Was diese Einstellung bewirkt:** Hier geben Sie die Hauptnachricht und den Inhalt für Ihr Popup ein. Sie können HTML verwenden, um Text zu formatieren, Bilder hinzuzufügen und Ihre Social-Media-Buttons einzufügen.
  - **Auswirkung der Änderung dieser Einstellung:** Dieser Text und HTML werden im Popup angezeigt.
  - **Empfohlener Wert:** Klare, prägnante Nachricht mit einem starken Call-to-Action. Fügen Sie Ihren Facebook-Like-Button-Code oder ein ähnliches Social-Media-Widget ein.
  - **Händlerszenario / Beispiel:** Sie könnten eingeben: `<p>Liken Sie uns auf Facebook und erhalten Sie <strong>10% RABATT</strong> auf Ihre nächste Bestellung!</p><div class="fb-like" data-href="IHRE_FACEBOOK_SEITEN_URL" data-layout="button_count" data-action="like" data-size="large" data-show-faces="false" data-share="false"></div>` (Denken Sie daran, `IHRE_FACEBOOK_SEITEN_URL` zu ersetzen).
- **Popup-Gutschein-Nachricht (HTML erlaubt):**

  - **Was diese Einstellung bewirkt:** Dies ist die Nachricht, die *nachdem* der Kunde die erforderliche Aktion ausgeführt hat (z.B. Ihre Seite geliked hat) und seinen Gutscheincode erhalten hat, angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:** Diese Nachricht wird im Popup angezeigt, typischerweise über dem generierten Gutscheincode.
  - **Empfohlener Wert:** Eine Dankesnachricht und Anweisungen zur Verwendung des Gutscheins.
  - **Händlerszenario / Beispiel:** Sie könnten eingeben: `<p>Vielen Dank für Ihr Like! Hier ist Ihr exklusiver Rabattcode:</p><p>Verwenden Sie den Code <strong>{coupon_code}</strong> an der Kasse.</p>` (Der Platzhalter `{coupon_code}` wird automatisch ersetzt).

#### Erweiterte Einstellungen

- **Benutzerdefinierter CSS-Code:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, Ihre eigenen benutzerdefinierten CSS-Regeln hinzuzufügen, um das Popup weiter zu gestalten oder Standardstile zu überschreiben.
  - **Auswirkung der Änderung dieser Einstellung:** Jedes CSS, das Sie hier eingeben, wird auf das Popup angewendet und gibt Ihnen eine feine Kontrolle über dessen Erscheinungsbild.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen.
  - **Händlerszenario / Beispiel:** Sie möchten die Schriftgröße des Gutscheincodes ändern. Sie könnten hinzufügen: `.coupon-code { font-size: 24px !important; }`
- **Benutzerdefinierter JavaScript-Code:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, Ihren eigenen benutzerdefinierten JavaScript-Code hinzuzufügen, um mit dem Popup zu interagieren oder es mit anderen Diensten zu integrieren.
  - **Auswirkung der Änderung dieser Einstellung:** Jedes JavaScript, das Sie hier eingeben, wird ausgeführt, wenn das Popup angezeigt oder interagiert wird.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Skriptanforderungen (z.B. Google Analytics Event-Tracking).
  - **Händlerszenario / Beispiel:** Sie möchten ein Ereignis an Google Analytics senden, wenn das Popup angezeigt wird. Sie könnten hinzufügen: `ga('send', 'event', 'Popup', 'Displayed', 'Coupon Offer');`

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Popup-Funktionalität. |
| | Anzeigen auf | Produktseiten / Alle Seiten | Wählen Sie, wo das Popup erscheint (Startseite, Kategorie, Produkt, CMS, Alle). |
| | Verzögerung (in Sekunden) vor dem Erscheinen des Popups | 3-5 Sekunden | Zeit, bevor das Popup nach dem Laden der Seite angezeigt wird. |
| | Popup nur einmal pro Sitzung anzeigen | JA | Verhindert, dass das Popup mehrmals in einer Browsersitzung angezeigt wird. |
| | Popup nur einmal pro Kunde anzeigen (für immer) | JA | Verhindert, dass eingeloggte Kunden das Popup erneut sehen. |
| | Popup nur für Gäste anzeigen | JA | Zielt auf nicht eingeloggte Besucher ab. |
| | Popup nur für ausgewählte Kundengruppen anzeigen | Gäste, Besucher | Beschränkt das Popup auf bestimmte Kundengruppen. |
| | Popup nur für ausgewählte Länder anzeigen | Leer lassen | Beschränkt das Popup auf bestimmte Länder. |
| | Popup nur für ausgewählte Währungen anzeigen | Leer lassen | Beschränkt das Popup auf bestimmte Währungen. |
| | Popup nur für ausgewählte Sprachen anzeigen | Leer lassen | Beschränkt das Popup auf bestimmte Sprachen. |
| | Gutscheinwert | z.B. 10% | Der Rabattbetrag oder Prozentsatz. |
| | Gutscheintyp | Prozentsatz / Betrag | Definiert, ob der Gutschein ein % oder ein fester Betrag ist. |
| | Gutschein Mindestbetrag | 0 (oder angemessener Wert) | Mindestbestellwert für die Gutscheinverwendung. |
| | Gutscheinablauf (in Tagen) | 7-30 Tage | Gültigkeitsdauer des generierten Gutscheins. |
| | Gutscheinbeschreibung | „Facebook Like Popup Rabatt“ | Interner Name für den Gutschein im BO. |
| | Gutschein kostenloser Versand | NEIN | Gewährt kostenlosen Versand mit dem Gutschein. |
| | Gutschein auf bestimmte Produkte anwenden | Leer lassen | Beschränkt den Gutschein auf bestimmte Produkte. |
| | Gutschein auf bestimmte Kategorien anwenden | Leer lassen | Beschränkt den Gutschein auf bestimmte Kategorien. |
| | Gutschein auf bestimmte Hersteller anwenden | Leer lassen | Beschränkt den Gutschein auf bestimmte Hersteller. |
| | Popup-Breite (in Pixel) | 600px - 800px | Horizontale Größe des Popups. |
| | Popup-Hintergrundfarbe | #FFFFFF (weiß) | Hintergrundfarbe des Popups. |
| | Popup-Textfarbe | #000000 (schwarz) | Textfarbe innerhalb des Popups. |
| | Popup-Rahmenfarbe | #DDDDDD (hellgrau) | Farbe des Popup-Rahmens. |
| | Popup-Rahmenbreite (in Pixel) | 1-3px | Dicke des Popup-Rahmens. |
| | Popup-Rahmenradius (in Pixel) | 5-10px | Rundung der Popup-Ecken. |
| | Popup-Schatten | JA | Fügt dem Popup einen Schatteneffekt hinzu. |
| | Popup-Schaltflächenfarbe schließen | #000000 (schwarz) | Farbe des „X“-Schließen-Buttons. |
| | Popup-Inhalt (HTML erlaubt) | Ansprechende Nachricht + Social Widget | Hauptinhalt, der im Popup angezeigt wird. |
| | Popup-Gutschein-Nachricht (HTML erlaubt) | Dankesnachricht + {coupon\_code} | Nachricht, die nach der Generierung des Gutscheins angezeigt wird. |
| | Benutzerdefinierter CSS-Code | Leer lassen | Benutzerdefinierte CSS-Stile hinzufügen. |
| | Benutzerdefinierter JavaScript-Code | Leer lassen | Benutzerdefinierten JavaScript-Code hinzufügen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Popup erscheint nicht in meinem Shop. Was sollte ich zuerst überprüfen?**
A1:

- **Ist das Modul aktiviert?** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Responsive Popup-Gutscheine“ installiert und aktiviert ist.
- **Überprüfen Sie die Einstellung „Modul aktivieren“:** Stellen Sie in der Modulkonfiguration sicher, dass der Schalter „Modul aktivieren“ auf JA steht.
- **Überprüfen Sie die Einstellungen „Anzeigen auf“:** Stellen Sie sicher, dass Sie die richtigen Seitentypen (z.B. Startseite, Produktseiten) ausgewählt haben, auf denen das Popup erscheinen soll.
- **Leeren Sie Ihren Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Der Browser-Cache muss möglicherweise ebenfalls geleert werden (Strg+F5 oder Cmd+Shift+R).
- **Suchen Sie nach Konflikten:** Deaktivieren Sie vorübergehend andere Module, die mit Popups oder Seiteninhalten interagieren könnten, um Konflikte auszuschließen.

**F2: Das Popup erscheint, aber der Facebook-Like-Button (oder ein anderes soziales Widget) funktioniert nicht oder wird nicht richtig angezeigt.**
A2:

- **Falsches HTML:** Überprüfen Sie den HTML-Code, den Sie im Feld „Popup-Inhalt“ eingegeben haben. Schon ein kleiner Tippfehler kann ihn beschädigen. Stellen Sie sicher, dass Ihre Facebook-Seiten-URL korrekt ist.
- **Facebook SDK:** Damit Facebook-Like-Buttons funktionieren, muss das Facebook JavaScript SDK geladen werden. PrestaShop-Themes enthalten dies oft, aber wenn nicht, müssen Sie es möglicherweise über benutzerdefinierten Code hinzufügen oder sicherstellen, dass Ihr Theme es unterstützt.
- **Werbeblocker:** Einige Werbeblocker können das Laden von sozialen Widgets verhindern. Testen Sie in einem Inkognito-Fenster ohne Erweiterungen.

**F3: Der Gutscheincode wird generiert, funktioniert aber an der Kasse nicht.**
A3:

- **Überprüfen Sie die Gutscheineinstellungen:** Überprüfen Sie alle „Gutschein“-Einstellungen in der Modulkonfiguration:
  - **Mindestbetrag:** Liegt der Warenkorbwert des Kunden über dem „Gutschein Mindestbetrag“?
  - **Ablauf:** Ist das „Gutscheinablauf“-Datum abgelaufen?
  - **Spezifische Produkte/Kategorien/Hersteller:** Enthält der Warenkorb des Kunden die erforderlichen Artikel, wenn diese Einstellungen verwendet werden?
  - **Kundengruppen/Länder/Währungen/Sprachen:** Erfüllt der Kunde die Kriterien für diese Einschränkungen?
- **PrestaShop Warenkorbregeln:** Das Modul erstellt eine „Warenkorbregel“ in PrestaShop. Gehen Sie zu **Katalog > Rabatte > Warenkorbregeln** (oder **Preisregeln > Warenkorbregeln** in älteren Versionen) und suchen Sie nach dem Gutscheincode. Überprüfen Sie dessen Details, um festzustellen, ob Einschränkungen falsch angewendet wurden.

**F4: Das Design des Popups passt nicht perfekt zu meinem Shop-Theme.**
A4:

- **Verwenden Sie die Designeinstellungen des Moduls:** Passen Sie „Popup-Hintergrundfarbe“, „Popup-Textfarbe“, „Popup-Rahmenfarbe“, „Popup-Rahmenbreite“ und „Popup-Rahmenradius“ an, um sie besser an Ihr Theme anzupassen.
- **Benutzerdefiniertes CSS:** Für fortgeschrittenes Styling verwenden Sie das Feld „Benutzerdefinierter CSS-Code“ in der Modulkonfiguration. Sie können die Popup-Elemente mit den Entwicklertools Ihres Browsers (F12) überprüfen, um die richtigen CSS-Selektoren zum Ansprechen zu finden.
- **Theme-Overrides:** Wenn Sie sich mit Codierung auskennen, können Sie das CSS des Moduls auch in der `custom.css` oder `theme.css` Ihres Themes überschreiben.

**F5: Wie übersetze ich den Popup-Inhalt in mehrere Sprachen?**
A5:

- Die Felder „Popup-Inhalt“ und „Popup-Gutschein-Nachricht“ sind typischerweise so konzipiert, dass sie einmal eingegeben werden. Für mehrsprachige Unterstützung müssten Sie das Übersetzungssystem von PrestaShop verwenden.
- Gehen Sie zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Responsive Popup-Gutscheine“. Dort sollten Sie die Textfelder zur Übersetzung finden.
- Wenn die Felder nicht direkt über die Standard-PrestaShop-Oberfläche übersetzbar sind, müssen Sie möglicherweise separate Popups für jede Sprache erstellen (wenn das Modul mehrere Instanzen unterstützt) oder eine benutzerdefinierte Lösung mit Smarty-Variablen und bedingter Logik innerhalb des HTML-Inhalts verwenden, was Entwicklerunterstützung erfordert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Responsive Popup-Gutscheine“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Responsive Popup-Gutscheine“ (`popcoupon`) ist ein Standard-PrestaShop-Modul, das hauptsächlich in seiner Haupt-PHP-Datei `ajax_popcoupon.php` implementiert ist. Es nutzt das Hook-System von PrestaShop für die Front-Office-Anzeige und die `Configuration`-Klasse für die Speicherung von Einstellungen. Die Kernfunktionalität des Moduls umfasst die Anzeige eines Popups, die Verarbeitung von Benutzerinteraktionen (z.B. Social-Media-Aktionen) und die dynamische Generierung von PrestaShop `CartRule` (Gutschein)-Codes. Es verwendet clientseitiges JavaScript für die Popup-Anzeigelogik und das Styling sowie ein minimales Template für das Rendern der Popup-Struktur.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine dedizierten Front-Office- oder Back-Office-Admin-Controller in separaten Dateien. Die gesamte Back-Office-Konfigurationslogik wird innerhalb der `getContent()`-Methode der Hauptmodulklasse behandelt. Die Front-Office-Anzeige wird über Hooks und clientseitiges JavaScript verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder andere Kern-PHP-Klassen in einem `classes/`-Verzeichnis. Die gesamte Logik ist in der Hauptmoduldatei `ajax_popcoupon.php` enthalten. Das Modul interagiert direkt mit der `Configuration`-Klasse von PrestaShop für Einstellungen und der `CartRule`-Klasse für die Gutscheingenerierung.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien:

- **`popcoupon/jscolor/jscolor.js`**

  - **Umfang:** Back-Office.
  - **Zweck:** Dies ist eine Drittanbieter-JavaScript-Bibliothek für einen Farbwähler. Sie wird im Back-Office-Konfigurationsformular des Moduls verwendet, um Händlern die einfache Auswahl von Farben für den Hintergrund, Text, Rahmen und Schließen-Button des Popups zu ermöglichen. Sie bindet an Eingabefelder mit spezifischen Klassen, um eine visuelle Farbauswahloberfläche bereitzustellen.
- **`popcoupon/lib/voucherengine/script.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dies ist die primäre JavaScript-Datei, die für die Front-Office-Popup-Funktionalität verantwortlich ist.
    - **Event-Listener:** Sie lauscht auf Seitenladeereignisse, um das Popup nach der konfigurierten Verzögerung auszulösen. Sie verarbeitet auch Ereignisse im Zusammenhang mit dem Schließen des Popups (z.B. Klicken auf den „X“-Button oder außerhalb des Popups).
    - **DOM-Manipulation:** Sie injiziert dynamisch die Popup-HTML-Struktur in die Seite, verwaltet deren Sichtbarkeit (anzeigen/ausblenden) und aktualisiert deren Inhalt (z.B. Anzeige des Gutscheincodes nach einer sozialen Aktion).
    - **AJAX-Aufrufe:** Sie führt wahrscheinlich AJAX-Aufrufe an die `ajax_popcoupon.php` des Moduls (oder einen ähnlichen Einstiegspunkt) durch, um:
      1. Zu überprüfen, ob das Popup für den aktuellen Benutzer/die aktuelle Sitzung angezeigt werden soll.
      2. Einen eindeutigen Gutscheincode zu generieren, nachdem der Benutzer die erforderliche Aktion abgeschlossen hat (z.B. Facebook-Like).
      3. Benutzer-/Sitzungsdaten (z.B. ein Cookie) zu speichern, um eine wiederholte Popup-Anzeige basierend auf Konfigurationseinstellungen („einmal pro Sitzung“, „einmal pro Kunde“) zu verhindern.
    - **Drittanbieter-SDKs:** Wenn der „Popup-Inhalt“ einen Facebook-Like-Button enthält, könnte dieses Skript mit dem Facebook JavaScript SDK (falls vom Theme geladen) interagieren, um zu erkennen, wann die „Like“-Aktion abgeschlossen ist.
- **`popcoupon/trusted.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Der genaue Zweck dieser Datei ist in den bereitgestellten Informationen nicht explizit definiert, aber basierend auf gängigen Modulpraktiken könnte sie sein:
    - Ein kleines Dienstprogramm-Skript für Tracking oder Analysen.
    - Ein Skript im Zusammenhang mit Vertrauensabzeichen oder Sicherheitsfunktionen.
    - Ein Fallback- oder Ergänzungsskript für die Haupt-`script.js`.
    - Es könnte Logik im Zusammenhang mit der Cookie-Behandlung oder dem lokalen Speicher für die „einmal anzeigen“-Funktionen enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält die folgenden CSS-Dateien:

- **`popcoupon/css.css`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dies ist das Haupt-Stylesheet für das Popup-Fenster.
    - **UI-Komponenten:** Stile für den gesamten Popup-Container, dessen Overlay, den Schließen-Button und möglicherweise den Inhaltsbereich.
    - **Schlüsselselektoren:** Entwickler können Selektoren wie `.popcoupon-overlay`, `.popcoupon-modal`, `.popcoupon-close` usw. erwarten. Diese können in der `custom.css` eines benutzerdefinierten Themes oder über die Einstellung „Benutzerdefinierter CSS-Code“ des Moduls überschrieben werden.
    - **Responsivität:** Enthält Medienabfragen oder flexible Box-/Grid-Eigenschaften, um sicherzustellen, dass sich das Popup gut an verschiedene Bildschirmgrößen anpasst.
- **`popcoupon/lib/voucherengine/ps16.css`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Stylesheet enthält wahrscheinlich spezifische Styling-Anpassungen oder Überschreibungen, die auf PrestaShop 1.6-Themes zugeschnitten sind. Es könnte Layoutunterschiede oder Standardelementstile beheben, die in PS 1.6 vorherrschen, um sicherzustellen, dass das Popup über verschiedene PrestaShop-Versionen hinweg konsistent aussieht. Für PS 1.7/8 könnten einige dieser Stile durch `css.css` oder das Theme selbst überschrieben werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet ein einziges Smarty-Template:

- **`popcoupon/views/header.tpl`**
  - **Hook:** `displayHeader` (oder ähnlich, je nachdem, wie es in `ajax_popcoupon.php` registriert ist).
  - **Zweck:** Dieses Template ist wahrscheinlich dafür verantwortlich, die notwendige HTML-Struktur für das Popup (die anfänglich ausgeblendet ist) und möglicherweise die JavaScript- und CSS-Assets in den `<head>` oder `<body>` der Front-Office-Seite einzufügen. Es könnte enthalten:
    - Das grundlegende HTML-Skelett für das Popup-Modal und dessen Overlay.
    - Bedingte Logik, um die JavaScript- und CSS-Dateien nur dann einzuschließen, wenn das Modul aktiviert ist.
    - Platzhalter für dynamische Inhalte, die von JavaScript gefüllt werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen:**

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der `ps_configuration`-Tabelle von PrestaShop. Konfigurationsschlüssel beginnen typischerweise mit `POPCOUPON_` (z.B. `POPCOUPON_ENABLED`, `POPCOUPON_DELAY`, `POPCOUPON_VOUCHER_VALUE`).
  - Es nutzt die `ps_cart_rule`- und `ps_cart_rule_lang`-Tabellen von PrestaShop zur Generierung und Verwaltung der eindeutigen Gutscheincodes.
  - Für die Funktionen „einmal pro Kunde/Sitzung anzeigen“ verwendet es wahrscheinlich Cookies oder `ps_customer`-spezifische Konfigurationseinträge.
- **Registrierte Hooks-Tabelle:**

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Einfügen von CSS, JavaScript und der anfänglichen (versteckten) HTML-Struktur für das Popup. |
| `displayFooter` | Am Ende des `<body>`-Bereichs jeder Front-Office-Seite. | Alternativer Hook zum Einfügen von JS/CSS oder des Popup-HTML, oft aus Leistungsgründen bevorzugt. |
| `displayLeftColumn` | In der linken Spalte des Front-Office. | Weniger üblich für Popups, könnte aber zum Auslösen oder Anzeigen eines kleineren Popup-Elements verwendet werden. |
| `displayRightColumn` | In der rechten Spalte des Front-Office. | Ähnlich wie `displayLeftColumn`. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des In-den-Warenkorb-Buttons. | Könnte verwendet werden, um ein produktspezifisches Popup auszulösen oder ein kleines Gutscheinangebot anzuzeigen. |
| `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien (JS/CSS) setzt. | Eine robustere Methode zur Registrierung von JS/CSS-Assets, um sicherzustellen, dass sie korrekt geladen werden. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | (Weniger wahrscheinlich für dieses Modul, könnte aber für Nachkaufaktionen im Zusammenhang mit Gutscheinen verwendet werden). |

*Hinweis: Die genauen verwendeten Hooks werden durch die `hook`-Methoden bestimmt, die in `ajax_popcoupon.php` implementiert sind (z.B. `hookDisplayHeader()`). Die Modulbeschreibung erwähnt „Header, Spalten, Produkt oder Footer“, was darauf hindeutet, dass es sich für mindestens einen dieser Anzeige-Hooks registriert.*

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Responsive Popup-Gutscheine“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
