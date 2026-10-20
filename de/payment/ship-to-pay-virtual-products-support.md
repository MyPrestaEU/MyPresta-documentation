---
title: "Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“ von MyPresta.eu."
sidebar:
  label: "Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Ship to pay + virtual products support auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/ship-to-pay-virtual-products-support.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/ship-to-pay-virtual-products-support/)
>
> ---


# Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind normalerweise in jeder kompatiblen Hosting-Umgebung vorhanden.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“. Ihnen wird ein einziger, umfassender Konfigurationsbildschirm präsentiert.

Dieser Bildschirm zeigt eine Matrix (ein Raster), in der Sie Ihre verfügbaren Versanddienstleister mit Ihren installierten Zahlungsmodulen verknüpfen können.

**Verständnis des Konfigurationsrasters:**

- **Zeilen (Versanddienstleister):** Jede Zeile repräsentiert einen Versanddienstleister, den Sie in Ihrem PrestaShop-Shop konfiguriert haben (z. B. „Mein Versanddienstleister“, „PrestaShop Standard-Versanddienstleister“, „DHL“, „UPS“ usw.).
- **Spalten (Zahlungsmodule):** Jede Spalte repräsentiert ein Zahlungsmodul, das Sie in Ihrem PrestaShop-Shop installiert und aktiviert haben (z. B. „Banküberweisung“, „Nachnahme“, „PayPal“, „Stripe“ usw.).
- **Kontrollkästchen:** Am Schnittpunkt jeder Versanddienstleister-Zeile und Zahlungsmodul-Spalte befindet sich ein Kontrollkästchen.

**So konfigurieren Sie:**

1. **Identifizieren Sie Ihre Versanddienstleister:** Schauen Sie in die linke Spalte, um alle Ihre aktiven Versanddienstleister zu sehen.
2. **Identifizieren Sie Ihre Zahlungsmethoden:** Schauen Sie in die obere Zeile, um alle Ihre aktiven Zahlungsmodule zu sehen.
3. **Verknüpfen Sie sie:** Gehen Sie für jeden Versanddienstleister dessen Zeile entlang und **aktivieren Sie das Kontrollkästchen** für jede Zahlungsmethode, die Sie für diesen spezifischen Versanddienstleister zulassen möchten.
   - *Was diese Einstellung bewirkt:* Dieses Kontrollkästchen bestimmt, ob eine bestimmte Zahlungsmethode dem Kunden angeboten wird, wenn er den entsprechenden Versanddienstleister während des Checkouts auswählt.
   - *Auswirkung der Änderung dieser Einstellung:*
     - **Wenn aktiviert:** Die Zahlungsmethode ist sichtbar und vom Kunden wählbar, wenn dieser Versanddienstleister gewählt wird.
     - **Wenn deaktiviert:** Die Zahlungsmethode wird ausgeblendet und ist für den Kunden nicht verfügbar, wenn dieser Versanddienstleister gewählt wird.
   - *Empfohlener Wert:* Aktivieren Sie nur die Kombinationen, die für Ihre Geschäftslogik sinnvoll sind.
   - *Händlerszenario / Beispiel:* Wenn „DHL Express“ ein schneller Premium-Service ist, könnten Sie dafür nur „PayPal“ und „Kreditkarte (Stripe)“ aktivieren und „Banküberweisung“ deaktivieren, um eine schnelle Zahlung für eine schnelle Lieferung zu gewährleisten.

**Spezielle Zeile: „Virtuelle Produkte“**

Dieses Modul enthält eine einzigartige Funktion für virtuelle Produkte. Sie sehen eine spezielle Zeile mit der Bezeichnung **„Virtuelle Produkte“** (oder ähnlich, je nach Ihrer PrestaShop-Version und Sprache).

- **Was diese Einstellung bewirkt:** Diese Zeile ermöglicht es Ihnen festzulegen, welche Zahlungsmethoden verfügbar sind, wenn der Warenkorb eines Kunden *nur* virtuelle Produkte enthält. Da virtuelle Produkte keine traditionelle Versandmethode haben, fungiert diese Zeile als deren „Versanddienstleister“ für die Zuordnung der Zahlungsmethode.
- *Auswirkung der Änderung dieser Einstellung:*
  - **Wenn aktiviert (für eine Zahlungsmethode in der Zeile „Virtuelle Produkte“):** Diese Zahlungsmethode ist verfügbar, wenn der Warenkorb des Kunden ausschließlich aus virtuellen Produkten besteht.
  - **Wenn deaktiviert:** Diese Zahlungsmethode ist für Warenkörbe, die nur virtuelle Produkte enthalten, nicht verfügbar.
- *Empfohlener Wert:* Aktivieren Sie die Zahlungsmethoden, die für die sofortige digitale Lieferung geeignet sind, typischerweise Online-Zahlungs-Gateways wie PayPal, Stripe oder Kreditkartenmodule.
- *Händlerszenario / Beispiel:* Wenn Sie E-Books verkaufen, würden Sie wahrscheinlich „PayPal“ und „Kreditkarte (Stripe)“ in der Zeile „Virtuelle Produkte“ aktivieren, aber „Nachnahme“ oder „Banküberweisung“ deaktivieren, da diese für die sofortige digitale Lieferung ungeeignet sind.

**Speichern Ihrer Konfiguration:**

- Nachdem Sie alle Ihre Auswahlen getroffen haben, denken Sie daran, auf die Schaltfläche **„Speichern“** (normalerweise am unteren Rand der Seite) zu klicken, um Ihre Änderungen zu übernehmen.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Kontrollkästchen für Versanddienstleister X / Zahlung Y | Standardmäßig deaktiviert | **Zweck:** Verknüpft eine bestimmte Zahlungsmethode mit einem bestimmten Versanddienstleister. **Auswirkung:** Wenn aktiviert, ist die Zahlungsmethode verfügbar, wenn Versanddienstleister X gewählt wird. Wenn deaktiviert, ist sie ausgeblendet. |
| Modulkonfigurationsseite | Kontrollkästchen für „Virtuelle Produkte“ / Zahlung Y | Standardmäßig deaktiviert | **Zweck:** Verknüpft eine bestimmte Zahlungsmethode mit Warenkörben, die nur virtuelle Produkte enthalten. **Auswirkung:** Wenn aktiviert, ist die Zahlungsmethode für Warenkörbe mit nur virtuellen Produkten verfügbar. Wenn deaktiviert, ist sie ausgeblendet. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul konfiguriert, aber die Zahlungsmethoden ändern sich im Checkout nicht. Was ist falsch?**
A1:

- **Cache leeren:** Das häufigste Problem. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Modul aktiviert:** Stellen Sie sicher, dass das Modul „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“ tatsächlich unter **Module > Modul-Manager** aktiviert ist.
- **Zahlungsmodule aktiviert:** Stellen Sie sicher, dass die Zahlungsmodule, die Sie verknüpfen möchten, ebenfalls aktiviert und in Ihrem Shop korrekt konfiguriert sind.
- **Theme-Kompatibilität:** Obwohl selten, können einige stark angepasste Themes stören. Wenn das Leeren des Caches nicht funktioniert, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, muss Ihr Theme möglicherweise angepasst werden.

**F2: Warum werden einige Zahlungsmethoden immer noch angezeigt, obwohl ich sie für einen Versanddienstleister deaktiviert habe?**
A2:

- **Mehrere Versanddienstleister im Warenkorb:** Wenn ein Kunde Produkte in seinem Warenkorb hat, die verschiedene Versanddienstleister nutzen würden (z. B. ein Produkt, das von Versanddienstleister A versendet wird, ein anderes von Versanddienstleister B), kann die Checkout-Logik von PrestaShop komplex werden. Dieses Modul funktioniert hauptsächlich, wenn eine einzige Versandmethode für den gesamten Warenkorb ausgewählt ist.
- **Virtuelle Produkte im Warenkorb:** Wenn der Warenkorb eine Mischung aus physischen und virtuellen Produkten enthält, kann die Logik des Moduls für virtuelle Produkte mit der trägerspezifischen Logik interagieren. Stellen Sie sicher, dass Ihre Zeile „Virtuelle Produkte“ wie beabsichtigt konfiguriert ist.
- **Andere Module:** Ein anderes Modul könnte die Zahlungsoptionen überschreiben. Deaktivieren Sie andere zahlungsbezogene Module vorübergehend, um Konflikte zu überprüfen.

**F3: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A3:

- Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann die Sprache, in die Sie übersetzen möchten.
- Suchen Sie das Modul „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“ in der Liste und klicken Sie auf „Ändern“. Sie können dann alle übersetzbaren Zeichenfolgen bearbeiten.

**F4: Ich habe einen neuen Versanddienstleister oder ein neues Zahlungsmodul hinzugefügt, aber es wird nicht im Konfigurationsraster angezeigt.**
A4:

- **Modulkonfiguration aktualisieren:** Manchmal benötigt PrestaShop eine Aktualisierung, um neue Entitäten zu erkennen. Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“ und klicken Sie erneut auf „Konfigurieren“. Dies sollte die Konfigurationsseite neu laden und den neuen Versanddienstleister/das neue Zahlungsmodul anzeigen.
- **Aktivierung sicherstellen:** Stellen Sie sicher, dass der neue Versanddienstleister oder das neue Zahlungsmodul in seinem jeweiligen Bereich des PrestaShop Back Office vollständig aktiviert und konfiguriert ist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“ funktioniert, indem es eine zentrale PrestaShop-Klasse überschreibt, die für die Suche nach verfügbaren Zahlungsoptionen während des Checkouts verantwortlich ist. Dies ermöglicht es, seine benutzerdefinierte Logik basierend auf ausgewählten Versanddienstleistern und dem Vorhandensein virtueller Produkte im Warenkorb einzufügen und die dem Kunden präsentierten Zahlungsmethoden zu filtern. Es nutzt das PrestaShop-Override-System und die Standard-Konfigurationsspeicherung.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Logik wird hauptsächlich über die Hauptmoduldatei und ein Override abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`shiptopay/override/classes/checkout/PaymentOptionsFinder.php`**
  - **Zweck:** Dies ist der Kern der Modulfunktionalität. Es überschreibt die Standardklasse `PaymentOptionsFinder` von PrestaShop, die dafür verantwortlich ist, welche Zahlungsoptionen dem Kunden während des Checkouts zur Verfügung stehen.
  - **Elternklasse:** `PaymentOptionsFinderCore`
  - **Schlüsselmethoden & Logik:**
    - Die überschriebene Methode `find()` (oder ähnlich, je nach PrestaShop-Version) wird abgefangen.
    - Innerhalb dieser Methode ruft das Modul die aktuell ausgewählte Versanddienstleister-ID (aus dem Warenkorb oder der Session) ab und prüft, ob der Warenkorb nur virtuelle Produkte enthält.
    - Anschließend fragt es die Konfiguration des Moduls (gespeichert in `ps_configuration`) ab, um zu bestimmen, welche Zahlungsmodule für den ausgewählten Versanddienstleister oder für virtuelle Produkte erlaubt sind.
    - Die ursprüngliche Liste der Zahlungsoptionen, die von `PaymentOptionsFinderCore` zurückgegeben wird, wird dann gefiltert, wobei alle Zahlungsmethoden entfernt werden, die gemäß der Modulkonfiguration nicht erlaubt sind.
    - Dies stellt sicher, dass dem Kunden nur zulässige Zahlungsmethoden angezeigt werden.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die dynamische Aktualisierung der Zahlungsoptionen wird durch das Kern-Checkout-JavaScript von PrestaShop gehandhabt, das auf Änderungen bei der Auswahl der Versandmethode reagiert und den Zahlungsbereich basierend auf den gefilterten Optionen, die vom überschriebenen `PaymentOptionsFinder` bereitgestellt werden, neu rendert.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Es integriert sich nahtlos in das bestehende PrestaShop-Theme-Styling für Zahlungsoptionen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`shiptopay/views/shiptopay.tpl`**
  - **Zweck:** Dieses Template wird wahrscheinlich zum Rendern des Konfigurationsformulars des Moduls im PrestaShop Back Office verwendet. Es konstruiert die HTML-Matrix (Raster) der Versanddienstleister und Zahlungsmethoden mit Kontrollkästchen, sodass der Händler diese verknüpfen kann.
  - **Geltungsbereich:** Admin-Template.
  - **Variablen:** Es würde typischerweise über die Arrays `$carriers` und `$payment_modules` iterieren und `Configuration::get()` verwenden, um die gespeicherten Einstellungen für jedes Kontrollkästchen abzurufen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen:**

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen (die Verknüpfungen zwischen Versanddienstleistern/virtuellen Produkten und Zahlungsmethoden) werden in der Tabelle `ps_configuration` gespeichert. Jede Einstellung würde typischerweise als Schlüssel-Wert-Paar gespeichert, wobei der Schlüssel `SHIP_TO_PAY_CARRIER_X_PAYMENT_Y` und der Wert `1` (aktiviert) oder `0` (deaktiviert) sein könnte. Die Einstellungen für „Virtuelle Produkte“ würden einer ähnlichen Namenskonvention folgen.
- **Registrierte Hooks-Tabelle:**

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich jeder Seite. | Obwohl als potenzieller Front-Office-Hook aufgeführt, verwendet dieses Modul hauptsächlich ein Override und rendert normalerweise keine sichtbaren Inhalte über `displayHeader`. Es könnte für die interne Modulinitialisierung oder das Laden von Assets verwendet werden, falls vorhanden. |
  | `displayRightColumn` | In der rechten Spalte von Seiten (falls vom Theme aktiviert). | Nicht direkt für die Kernfunktionalität des Moduls verwendet, da seine Auswirkung auf die Checkout-Zahlungsoptionen liegt. |
  | `displayLeftColumn` | In der linken Spalte von Seiten (falls vom Theme aktiviert). | Nicht direkt für die Kernfunktionalität des Moduls verwendet, da seine Auswirkung auf die Checkout-Zahlungsoptionen liegt. |
  | `displayFooter` | Im Footer-Bereich jeder Seite. | Nicht direkt für die Kernfunktionalität des Moduls verwendet, da seine Auswirkung auf die Checkout-Zahlungsoptionen liegt. |
  | `displayModuleConfigureExtraButtons` | Im Modul-Manager, neben dem Konfigurieren-Button. | Nicht explizit für die Kernfunktionalität verwendet, könnte aber für zusätzliche Admin-Aktionen genutzt werden. |
  | `actionPaymentOptionsModifier` | (Implizit/Intern) | Dieses Modul arbeitet hauptsächlich durch das Überschreiben von `PaymentOptionsFinder`, das intern während des Checkout-Prozesses aufgerufen wird, um die Liste der Zahlungsoptionen zu generieren. Obwohl es kein traditioneller `hookDisplay`- oder `action`-Hook ist, fungiert das Override als Abfangpunkt. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Versandart zu Zahlungsart + Unterstützung für virtuelle Produkte“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
