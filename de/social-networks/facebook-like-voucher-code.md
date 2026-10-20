---
title: "Facebook Like Gutscheincode - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Facebook Like Gutscheincode' von MyPresta.eu."
sidebar:
  label: "Facebook Like Gutscheincode"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook like voucher code auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-like-voucher-code.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-like-voucher-code/)
>
> ---


# Facebook Like Gutscheincode

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und jedes Modul, das mit externen APIs wie Facebook interagiert, erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der Hauptkonfigurationsbildschirm für das Modul „Facebook Like Gutscheincode“, der nach der Installation durch Klicken auf die Schaltfläche „Konfigurieren“ zugänglich ist. Hier definieren Sie, wie der Facebook Like-Button angezeigt wird und wie die Gutscheincodes generiert werden.

#### **Facebook Seiten-URL**
- **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie teilt dem Modul mit, welche Facebook-Seite Ihre Kunden „liken“ sollen, um den Gutschein zu erhalten.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf die URL Ihrer Facebook-Seite eingestellt (z.B. `https://www.facebook.com/MyPresta.eu`):* Der „Gefällt mir“-Button in Ihrem Shop wird direkt auf diese spezifische Facebook-Seite verlinken und Likes dafür verfolgen.
  - *Wenn leer gelassen oder falsch eingestellt:* Der „Gefällt mir“-Button funktioniert nicht korrekt oder verlinkt möglicherweise auf eine nicht existierende Seite, wodurch Kunden keine Gutscheine erhalten können.
- **Empfohlener Wert:** Geben Sie die vollständige URL Ihrer offiziellen Facebook-Unternehmensseite ein.
- **Händlerszenario / Beispiel:** Wenn Ihre Facebook-Seite `https://www.facebook.com/myawesomestore` ist, würden Sie genau diese URL hier eingeben.

#### **Gutscheincode-Präfix**
- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, allen von diesem Modul generierten Gutscheincodes ein benutzerdefiniertes Präfix hinzuzufügen. Dies hilft Ihnen, leicht zu erkennen, welche Gutscheine aus Ihrer Facebook-Promotion stammen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „FB“ eingestellt:* Alle generierten Gutscheincodes beginnen mit „FB“ (z.B. FB123456).
  - *Wenn leer gelassen:* Gutscheincodes werden ohne ein spezifisches Präfix generiert, wodurch sie schwerer von anderen Gutscheinarten zu unterscheiden sind.
- **Empfohlener Wert:** Ein kurzes, einprägsames Präfix wie „FB“, „LIKE“ oder „SOCIAL“.
- **Händlerszenario / Beispiel:** Die Verwendung von „FB“ ermöglicht es Ihnen, Ihre Gutscheincodes im PrestaShop Back Office schnell zu filtern, um zu sehen, wie viele durch dieses Modul generiert wurden.

#### **Gutscheincode-Wert**
- **Was diese Einstellung bewirkt:** Definiert den Rabattwert des Gutscheincodes. Dies kann ein fester Betrag oder ein Prozentsatz sein.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „10“ und „Prozentsatz“ eingestellt:* Kunden erhalten einen Rabatt von 10%.
  - *Wenn auf „5“ und „Betrag“ eingestellt:* Kunden erhalten einen Rabatt von 5 $ (oder Ihrer Standardwährung).
- **Empfohlener Wert:** Ein Wert, der attraktiv genug ist, um einen Kauf zu fördern, aber auch nachhaltig für Ihre Gewinnmargen (z.B. 5, 10, 15).
- **Händlerszenario / Beispiel:** Das Anbieten von „10“ und „Prozentsatz“ für einen 10%igen Rabatt ist eine gängige und effektive Strategie, um Erstkäufer zu ermutigen.

#### **Gutscheincode-Typ**
- **Was diese Einstellung bewirkt:** Bestimmt, ob der Gutscheincode einen prozentualen Rabatt oder einen festen Betragsrabatt bietet.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Prozentsatz“ eingestellt:* Der „Gutscheincode-Wert“ wird als Prozentsatz interpretiert (z.B. 10% Rabatt).
  - *Wenn auf „Betrag“ eingestellt:* Der „Gutscheincode-Wert“ wird als fester Geldbetrag interpretiert (z.B. 10 $ Rabatt).
- **Empfohlener Wert:** „Prozentsatz“ ist oft ansprechender, da er mit dem Bestellwert skaliert, aber „Betrag“ kann für preisgünstigere Artikel oder spezifische Aktionen effektiv sein.
- **Händlerszenario / Beispiel:** Wenn Sie einen pauschalen Rabatt von 5 $ unabhängig von der Bestellgröße geben möchten, wählen Sie „Betrag“. Wenn Sie einen Rabatt geben möchten, der mit dem Bestellwert steigt, wählen Sie „Prozentsatz“.

#### **Gutscheincode Mindestbetrag**
- **Was diese Einstellung bewirkt:** Legt einen Mindestbestellwert (vor Versand) fest, den ein Kunde erreichen muss, um den Gutscheincode verwenden zu können.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „50“ eingestellt:* Der Gutschein kann nur verwendet werden, wenn der Warenkorbwert 50 $ oder mehr beträgt.
  - *Wenn leer gelassen oder auf „0“ eingestellt:* Der Gutschein kann für jeden Bestellbetrag verwendet werden.
- **Empfohlener Wert:** Ein Wert, der Kunden dazu anregt, mehr Artikel in ihren Warenkorb zu legen, wodurch der durchschnittliche Bestellwert steigt (z.B. 25, 50).
- **Händlerszenario / Beispiel:** Wenn Ihr durchschnittlicher Bestellwert 40 $ beträgt, ermutigt ein Mindestbetrag von 50 $ für einen 10%igen Gutschein Kunden, einen zusätzlichen Artikel hinzuzufügen, um sich für den Rabatt zu qualifizieren.

#### **Gutscheincode Ablaufdatum (Tage)**
- **Was diese Einstellung bewirkt:** Definiert, wie viele Tage der generierte Gutscheincode ab dem Zeitpunkt seiner Ausstellung gültig ist.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „7“ eingestellt:* Der Gutscheincode läuft 7 Tage nach Erhalt durch den Kunden ab.
  - *Wenn leer gelassen oder auf „0“ eingestellt:* Der Gutscheincode hat kein Ablaufdatum (oder ein sehr langes Standarddatum, das von PrestaShop festgelegt wird).
- **Empfohlener Wert:** Ein angemessener Zeitrahmen, um Dringlichkeit zu erzeugen, ohne zu restriktiv zu sein (z.B. 7, 14, 30 Tage).
- **Händlerszenario / Beispiel:** Die Einstellung auf „7“ Tage ermutigt Kunden, einen Kauf eher früher als später zu tätigen, um zu verhindern, dass sie den Gutschein vergessen.

#### **Gutscheincode-Beschreibung**
- **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, dem generierten Gutscheincode in Ihrem PrestaShop Back Office eine benutzerdefinierte Beschreibung hinzuzufügen. Dies hilft Ihnen, den Zweck des Gutscheins zu verfolgen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Facebook Like Promotion“ eingestellt:* Diese Beschreibung ist sichtbar, wenn Sie die Gutscheindetails in Ihrem PrestaShop Back Office anzeigen, wodurch klar wird, woher der Gutschein stammt.
  - *Wenn leer gelassen:* Der Gutschein hat keine spezifische Beschreibung, wodurch es schwieriger wird, seine Quelle zu identifizieren.
- **Empfohlener Wert:** Eine klare, prägnante Beschreibung wie „Facebook Like Gutschein“ oder „Social Media Promo“.
- **Händlerszenario / Beispiel:** Die Verwendung von „Facebook Like Promotion“ hilft Ihrem Kundenservice-Team, den Kontext des Gutscheins zu verstehen, falls ein Kunde Fragen dazu hat.

#### **Block anzeigen in**
- **Was diese Einstellung bewirkt:** Bestimmt, wo der Facebook „Gefällt mir“-Button-Block im Front Office Ihres Shops angezeigt wird.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Header“ ausgewählt ist:* Der Block erscheint oben auf jeder Seite.
  - *Wenn „Linke Spalte“ ausgewählt ist:* Der Block erscheint in der linken Seitenleiste.
  - *Wenn „Rechte Spalte“ ausgewählt ist:* Der Block erscheint in der rechten Seitenleiste.
  - *Wenn „Produktseite“ ausgewählt ist:* Der Block erscheint auf einzelnen Produktseiten.
  - *Wenn „Footer“ ausgewählt ist:* Der Block erscheint am unteren Rand jeder Seite.
- **Empfohlener Wert:** „Header“ oder „Produktseite“ für maximale Sichtbarkeit und Wirkung, oder „Linke/Rechte Spalte“, wenn Sie eine weniger aufdringliche Platzierung bevorzugen.
- **Händlerszenario / Beispiel:** Die Platzierung im „Header“ stellt sicher, dass jeder Besucher ihn sieht. Die Platzierung auf der „Produktseite“ zielt auf Kunden ab, die bereits an einem Kauf interessiert sind.

#### **Gutscheincode Popup-Nachricht**
- **Was diese Einstellung bewirkt:** Dies ist die Nachricht, die Kunden im Popup-Fenster zusammen mit ihrem Gutscheincode sehen, nachdem sie Ihre Facebook-Seite „geliked“ haben.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Vielen Dank für Ihr Like! Hier ist Ihr Rabattcode: {voucher_code}“ eingestellt:* Der Kunde sieht genau diese Nachricht mit seinem einzigartigen Code.
  - *Wenn leer gelassen:* Der Kunde sieht möglicherweise nur den Code ohne begleitenden Text, was verwirrend sein könnte.
- **Empfohlener Wert:** Eine freundliche, klare Nachricht, die dem Kunden dankt und explizit angibt, dass der Code für einen Rabatt ist. **Fügen Sie immer `{voucher_code}` ein**, damit der tatsächliche Code angezeigt wird.
- **Händlerszenario / Beispiel:** „Vielen Dank, dass Sie unserer Community beigetreten sind! Hier ist ein besonderes Geschenk für Sie: {voucher_code}. Viel Spaß beim Einkaufen!“

#### **Gutscheincode Popup-Titel**
- **Was diese Einstellung bewirkt:** Legt den Titel des Popup-Fensters fest, das den Gutscheincode anzeigt.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Ihr exklusiver Rabatt!“ eingestellt:* Dieser Titel erscheint oben im Popup-Fenster.
  - *Wenn leer gelassen:* Das Popup hat möglicherweise einen generischen oder keinen Titel, was weniger professionell ist.
- **Empfohlener Wert:** Ein eingängiger und klarer Titel, der die Belohnung verstärkt (z.B. „Ihr kostenloser Gutschein!“, „Vielen Dank für Ihr Like!“).
- **Händlerszenario / Beispiel:** „Ihr exklusiver Rabatt!“ teilt dem Kunden sofort mit, dass er eine wertvolle Belohnung erhalten hat.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung
"""
