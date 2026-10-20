---
title: "Facebook Warenkorb teilen + Gutscheincode - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Facebook Warenkorb teilen + Gutscheincode' von MyPresta.eu."
sidebar:
  label: "Facebook Warenkorb teilen + Gutscheincode"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook cart share + voucher coupon auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-cart-share-voucher-coupon.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-cart-share-voucher-coupon/)
>
> ---


# Facebook Warenkorb teilen + Gutscheincode

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop- und Facebook-API-Interaktionen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der Hauptkonfigurationsbildschirm für das Modul "Facebook Warenkorb teilen + Gutscheincode". Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren, nach "Facebook Warenkorb teilen + Gutscheincode" suchen und auf "Konfigurieren" klicken.

#### **Allgemeine Einstellungen**

-   **Facebook App ID (cshare_appid / cshare_app_id)**
    -   **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Kennung für Ihre Facebook-Anwendung, die erforderlich ist, damit das Modul mit der Facebook-API interagieren kann. Sie müssen eine Facebook-App auf der Facebook-Entwicklerplattform (developers.facebook.com) erstellen, um diese ID zu erhalten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei korrekter Einstellung:* Das Modul kann erfolgreich eine Verbindung zu Facebook herstellen, sodass Kunden ihre Warenkörbe teilen können und Ihr Shop diese Shares verfolgen kann.
        -   *Wenn leer gelassen oder falsch eingestellt:* Die Facebook-Teilen-Funktion funktioniert nicht, und Kunden können ihre Warenkörbe nicht teilen.
    -   **Empfohlener Wert:** Ihre eindeutige Facebook App ID.
    -   **Händlerszenario / Beispiel:** Sie haben Ihren PrestaShop-Shop als App auf Facebook Developers registriert und eine App ID wie `123456789012345` erhalten. Geben Sie diese ID hier ein.

-   **Teilen-Button anzeigen auf (cshare_lasttab)**
    -   **Was diese Einstellung bewirkt:** Legt fest, wo der Button "Warenkorb auf Facebook teilen" im Front Office Ihres Shops angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf "Warenkorbseite" eingestellt:* Der Button erscheint auf der Seite, auf der Kunden den Inhalt ihres Warenkorbs überprüfen, bevor sie zur Kasse gehen.
        -   *Wenn auf "Bestellbestätigungsseite" eingestellt:* Der Button erscheint, nachdem der Kunde eine Bestellung erfolgreich aufgegeben hat.
        -   *Wenn auf "Beide" eingestellt:* Der Button erscheint auf beiden Seiten.
    -   **Empfohlener Wert:** "Beide", um die Sichtbarkeit und die Möglichkeiten zum Teilen zu maximieren.
    -   **Händlerszenario / Beispiel:** Sie möchten das Teilen sowohl vor als auch nach einem Kauf fördern, daher wählen Sie "Beide".

-   **Facebook Teilen-Button Stil (cshare_button_style)**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den visuellen Stil des Facebook-Teilen-Buttons zu wählen.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert das Aussehen des Teilen-Buttons, um ihn besser an das Design Ihres Shops oder Ihre Präferenz für einen größeren/kleineren Button anzupassen.
    -   **Empfohlener Wert:** Experimentieren Sie, um herauszufinden, was am besten zu Ihrem Thema passt.
    -   **Händlerszenario / Beispiel:** Ihr Thema hat ein minimalistisches Design, daher könnten Sie einen einfachen, textbasierten Teilen-Button anstelle eines großen, grafischen wählen.

#### **Gutschein-Einstellungen**

-   **Gutscheingenerierung aktivieren (cshare_voucher)**
    -   **Was diese Einstellung bewirkt:** Schaltet um, ob ein Rabattgutschein generiert und dem Kunden angeboten wird, nachdem er seinen Warenkorb erfolgreich auf Facebook geteilt hat.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Ein eindeutiger Gutscheincode wird erstellt und dem Kunden nach dem Teilen angezeigt.
        -   *Wenn deaktiviert:* Es wird kein Gutschein generiert oder angeboten, wodurch der direkte Anreiz zum Teilen entfällt.
    -   **Empfohlener Wert:** "JA", um den Anreiz zum Teilen zu nutzen und Konversionen zu steigern.
    -   **Händlerszenario / Beispiel:** Sie möchten Kunden für das Teilen belohnen und Wiederholungskäufe fördern, daher aktivieren Sie dies.

-   **Gutscheingeschenk (cshare_gift)**
    -   **Was diese Einstellung bewirkt:** Definiert die Art und den Wert des Rabattgutscheins, den Kunden erhalten. Dies entspricht den Einstellungen "Rabattart" und "Wert" beim Erstellen einer neuen Warenkorbregel in PrestaShop.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Fester Betrag:* Der Kunde erhält einen bestimmten monetären Rabatt (z.B. 5 € Rabatt).
        -   *Prozentsatz:* Der Kunde erhält einen prozentualen Rabatt (z.B. 10 % Rabatt).
        -   *Kostenloser Versand:* Der Kunde erhält kostenlosen Versand für seine nächste Bestellung.
    -   **Empfohlener Wert:** Ein Wert, der attraktiv genug ist, um zum Teilen anzuregen, aber auch für Ihr Geschäft nachhaltig ist.
    -   **Händlerszenario / Beispiel:** Sie beschließen, einen "10 % Rabatt" anzubieten, um neue Käufe zu fördern, daher wählen Sie "Prozentsatz" und legen den Wert im nächsten Feld fest.

-   **Gutscheinwert (cshare_image)**
    -   **Was diese Einstellung bewirkt:** Legt den spezifischen Wert für den Gutschein fest, abhängig von der gewählten Art des "Gutscheingeschenks".
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn "Fester Betrag" gewählt wurde:* Dies ist der genaue monetäre Wert des Rabatts.
        -   *Wenn "Prozentsatz" gewählt wurde:* Dies ist der Prozentsatz des Rabatts.
    -   **Empfohlener Wert:** Ein überzeugender Rabatt (z.B. 5, 10, 15 für Prozentsatz; 5, 10, 20 für festen Betrag).
    -   **Händlerszenario / Beispiel:** Sie haben "Prozentsatz" für "Gutscheingeschenk" gewählt, daher geben Sie hier "10" für einen 10 % Rabatt ein.

#### **Einstellungen für geteilte Inhalte**

Diese Einstellungen steuern, welche Informationen über den Warenkorb des Kunden in den Facebook-Beitrag aufgenommen werden, wenn dieser geteilt wird.

-   **Preise anzeigen (cshare_show_prices)**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob die Einzelpreise der Produkte im Warenkorb im Facebook-Teilen-Beitrag angezeigt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Jedes im geteilten Warenkorb aufgeführte Produkt zeigt seinen Preis an.
        -   *Wenn deaktiviert:* Produktpreise werden aus dem geteilten Beitrag weggelassen.
    -   **Empfohlener Wert:** "JA", um Transparenz zu schaffen und Klicks zu fördern, es sei denn, Ihre Preisstrategie erfordert etwas anderes.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass potenzielle Kunden den Wert der Artikel sehen, daher aktivieren Sie "Preise anzeigen".

-   **Gesamtsumme anzeigen (cshare_show_total)**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob der Gesamtwert des Warenkorbs im Facebook-Teilen-Beitrag angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Der Gesamtpreis aller Artikel im Warenkorb wird angezeigt.
        -   *Wenn deaktiviert:* Die Warenkorb-Gesamtsumme wird nicht in den Beitrag aufgenommen.
    -   **Empfohlener Wert:** "JA", um einen klaren Überblick über den Wert des Warenkorbs zu geben.
    -   **Händlerszenario / Beispiel:** Ein Kunde hat einen Warenkorb im Wert von 250 €, und Sie möchten, dass seine Freunde diesen bedeutenden Kauf sehen, daher aktivieren Sie "Gesamtsumme anzeigen".

-   **Produkte anzeigen (cshare_show_products)**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob die Namen und Mengen der einzelnen Produkte im Warenkorb im Facebook-Teilen-Beitrag aufgeführt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Eine Liste der Produkte (z.B. "T-Shirt x1, Jeans x1") erscheint im Beitrag.
        -   *Wenn deaktiviert:* Es erscheint nur eine allgemeine Nachricht über das Teilen des Warenkorbs, ohne spezifische Produktdetails.
    -   **Empfohlener Wert:** "JA", um die spezifischen Artikel zu präsentieren und Interesse zu wecken.
    -   **Händlerszenario / Beispiel:** Sie möchten die spezifischen Produkte hervorheben, die ein Kunde kauft, daher aktivieren Sie "Produkte anzeigen".

-   **Produkt-URL anzeigen (cshare_show_product_url)**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob direkte Links zu den einzelnen Produktseiten im Facebook-Teilen-Beitrag enthalten sind.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Jedes aufgeführte Produkt hat einen klickbaren Link zu seiner Seite in Ihrem Shop.
        -   *Wenn deaktiviert:* Produktnamen werden angezeigt, aber ohne direkte Links.
    -   **Empfohlener Wert:** "JA", um Traffic direkt auf Produktseiten zu lenken.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass Freunde des Teilenden einfach klicken und die Produkte ansehen können, daher aktivieren Sie "Produkt-URL anzeigen".

#### **Erweiterte Einstellungen**

-   **HTTPS erzwingen (cshare_http)**
    -   **Was diese Einstellung bewirkt:** Stellt sicher, dass alle für das Facebook-Teilen generierten URLs HTTPS verwenden, auch wenn Ihre PrestaShop-Konfiguration manchmal standardmäßig HTTP verwenden könnte. Dies ist entscheidend für die Sicherheit und die Anforderungen von Facebook.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Alle geteilten Links sind sicher (HTTPS).
        -   *Wenn deaktiviert:* Links könnten manchmal HTTP sein, was zu Problemen mit der Facebook-API und Sicherheitswarnungen führen kann.
    -   **Empfohlener Wert:** "JA", wenn Ihr Shop HTTPS verwendet (was er sollte!).
    -   **Händlerszenario / Beispiel:** Ihr gesamter Shop läuft über HTTPS, daher aktivieren Sie dies, um Konsistenz zu gewährleisten und Browserwarnungen zu vermeiden.

-   **PrestaShop Shop-Name (PS_SHOP_NAME)**
    -   **Was diese Einstellung bewirkt:** Dieses Feld ruft normalerweise den Namen Ihres Shops aus den allgemeinen PrestaShop-Einstellungen ab. Es wird im geteilten Facebook-Beitrag verwendet.
    -   **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass der korrekte Shop-Name im Facebook-Beitrag angezeigt wird.
    -   **Empfohlener Wert:** Als Standard belassen (sollte automatisch aus Ihrer PrestaShop-Konfiguration übernommen werden).
    -   **Händlerszenario / Beispiel:** Ihr Shop heißt "Mein toller Shop", und dieses Feld zeigt "Mein toller Shop" korrekt an.

-   **PrestaShop Shop-E-Mail (PS_SHOP_EMAIL)**
    -   **Was diese Einstellung bewirkt:** Dieses Feld ruft normalerweise die Kontakt-E-Mail Ihres Shops aus den allgemeinen PrestaShop-Einstellungen ab. Es könnte für interne Moduloperationen oder in generierten Inhalten verwendet werden.
    -   **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass die korrekte E-Mail verwendet wird, falls das Modul darauf verweisen muss.
    -   **Empfohlener Wert:** Als Standard belassen (sollte automatisch aus Ihrer PrestaShop-Konfiguration übernommen werden).
    -   **Händlerszenario / Beispiel:** Die Kontakt-E-Mail Ihres Shops ist `info@meintollershop.com`, und dieses Feld zeigt sie korrekt an.

-   **PrestaShop Steuer (PS_TAX)**
    -   **Was diese Einstellung bewirkt:** Dieses Feld ruft normalerweise die Standardsteuereinstellung Ihres Shops ab. Es könnte verwendet werden, um Preise in den geteilten Inhalten korrekt zu berechnen.
    -   **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass steuerliche Aspekte korrekt behandelt werden, wenn Preise angezeigt werden.
    -   **Empfohlener Wert:** Als Standard belassen (sollte automatisch aus Ihrer PrestaShop-Konfiguration übernommen werden).
    -   **Händlerszenario / Beispiel:** Ihr Shop arbeitet mit 20 % Mehrwertsteuer, und dieses Feld spiegelt dies wider.

#### **Interne Moduleinstellungen (Normalerweise als Standard belassen)**

-   **MyPresta.eu Updates (mypresta_updates, update_, updatev_)**
    -   **Was diese Einstellung bewirkt:** Dies sind interne Einstellungen, die von MyPresta.eu-Modulen verwendet werden, um nach Updates zu suchen und die Kompatibilität sicherzustellen.
    -   **Auswirkung der Änderung dieser Einstellung:** Eine Änderung könnte die Fähigkeit des Moduls beeinträchtigen, Updates zu erhalten oder korrekt zu funktionieren.
    -   **Empfohlener Wert:** Als Standard belassen.
    -   **Händlerszenario / Beispiel:** Sie müssen normalerweise nicht mit diesen interagieren.

-   **Facebook Init (cshare_fbinit)**
    -   **Was diese Einstellung bewirkt:** Ein internes Flag, das anzeigt, ob das Facebook SDK initialisiert wurde.
    -   **Auswirkung der Änderung dieser Einstellung:** Eine Änderung könnte verhindern, dass die Facebook-Teilen-Funktion korrekt geladen wird.
    -   **Empfohlener Wert:** Als Standard belassen.
    -   **Händlerszenario / Beispiel:** Dies ist eine technische Einstellung, die nicht für die Interaktion des Händlers gedacht ist.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten
Dieses Modul führt keine dedizierten benutzerdefinierten Admin-Bildschirme oder Controller über seine Hauptkonfigurationsseite hinaus ein. Alle Einstellungen werden direkt über die Standard-Modulkonfigurationsoberfläche verwaltet.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Facebook App ID | Ihre eindeutige App ID | Wesentlich für die Facebook-API-Verbindung; Teilen funktioniert ohne sie nicht. |
| Modulkonfiguration | Teilen-Button anzeigen auf | Beide | Steuert, wo der Teilen-Button erscheint (Warenkorb, Bestellbestätigung oder beides). |
| Modulkonfiguration | Facebook Teilen-Button Stil | (Variiert) | Ändert das visuelle Erscheinungsbild des Teilen-Buttons. |
| Modulkonfiguration | Gutscheingenerierung aktivieren | JA | Schaltet die Erstellung und Anzeige eines Rabattgutscheins nach dem Teilen um. |
| Modulkonfiguration | Gutscheingeschenk | Prozentsatz / Fester Betrag | Definiert die Art des Rabatts (z.B. 10 % Rabatt, 5 € Rabatt, Kostenloser Versand). |
| Modulkonfiguration | Gutscheinwert | (Ihr gewünschter Wert) | Legt den spezifischen Wert für die gewählte Gutscheingeschenk-Art fest. |
| Modulkonfiguration | Preise anzeigen | JA | Enthält Einzelproduktpreise im Facebook-Teilen-Beitrag. |
| Modulkonfiguration | Gesamtsumme anzeigen | JA | Enthält den Gesamtwert des Warenkorbs im Facebook-Teilen-Beitrag. |
| Modulkonfiguration | Produkte anzeigen | JA | Listet einzelne Produktnamen und Mengen im Facebook-Teilen-Beitrag auf. |
| Modulkonfiguration | Produkt-URL anzeigen | JA | Fügt direkte Links zu Produktseiten im Facebook-Teilen-Beitrag hinzu. |
| Modulkonfiguration | HTTPS erzwingen | JA | Stellt sicher, dass alle geteilten Links sicher (HTTPS) sind. |
| Modulkonfiguration | PrestaShop Shop-Name | (Automatisch ausgefüllt) | Zeigt den Namen Ihres Shops im Facebook-Beitrag an. |
| Modulkonfiguration | PrestaShop Shop-E-Mail | (Automatisch ausgefüllt) | Kontakt-E-Mail des Shops. |
| Modulkonfiguration | PrestaShop Steuer | (Automatisch ausgefüllt) | Standardsteuereinstellung des Shops. |
| Modulkonfiguration | MyPresta.eu Updates | (Intern) | Interne Einstellungen für Modul-Updates. |
| Modulkonfiguration | Facebook Init | (Intern) | Internes Flag für die Facebook SDK-Initialisierung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Facebook-Teilen-Button erscheint nicht auf meiner Warenkorb-/Bestellbestätigungsseite.**
*   **A:** Überprüfen Sie zunächst die Modulkonfiguration in Ihrem Back Office (**Module > Modul-Manager > Facebook Warenkorb teilen + Gutscheincode konfigurieren**). Stellen Sie sicher, dass "Teilen-Button anzeigen auf" korrekt eingestellt ist (z.B. "Warenkorbseite", "Bestellbestätigungsseite" oder "Beide"). Vergewissern Sie sich auch, dass Ihre Facebook App ID korrekt eingegeben ist. Wenn es immer noch nicht angezeigt wird, leeren Sie Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung > Cache leeren**).

**F2: Wenn Kunden auf den Teilen-Button klicken, passiert nichts oder sie erhalten eine Fehlermeldung.**
*   **A:** Dies deutet fast immer auf ein Problem mit Ihrer Facebook App ID oder der Facebook App-Konfiguration selbst hin.
    1.  **Überprüfen Sie Ihre Facebook App ID:** Stellen Sie sicher, dass sie in der Modulkonfiguration korrekt eingegeben ist.
    2.  **Überprüfen Sie die Facebook App-Einstellungen:** Melden Sie sich bei [developers.facebook.com](https://developers.facebook.com/) an. Stellen Sie sicher, dass Ihre App "Live" ist (nicht im Entwicklungsmodus). Überprüfen Sie den Abschnitt "Einstellungen > Grundlegend" für Ihre App: Die Felder "App-Domains" und "Website" müssen die Domain Ihres Shops korrekt auflisten (z.B. `ihrshop.com` und `https://www.ihrshop.com`).
    3.  **HTTPS erzwingen:** Stellen Sie sicher, dass die Option "HTTPS erzwingen" in der Modulkonfiguration auf "JA" gesetzt ist, wenn Ihr Shop HTTPS verwendet.

**F3: Gutscheine werden nach einem erfolgreichen Teilen nicht generiert.**
*   **A:**
    1.  **"Gutscheingenerierung aktivieren" überprüfen:** Stellen Sie in der Modulkonfiguration sicher, dass diese Einstellung auf "JA" gesetzt ist.
    2.  **Gutscheingeschenk & Wert:** Stellen Sie sicher, dass Sie eine Art von "Gutscheingeschenk" (z.B. Prozentsatz, Fester Betrag) ausgewählt und einen gültigen "Gutscheinwert" eingegeben haben.
    3.  **PrestaShop Warenkorbregel-Limits:** PrestaShop hat Limits für die Anzahl der Warenkorbregeln. Obwohl für dieses Modul unwahrscheinlich, stellen Sie bei einem extrem hohen Volumen an Shares sicher, dass Ihr Server die Erstellung neuer Warenkorbregeln verarbeiten kann.
    4.  **Fehlerprotokolle:** Überprüfen Sie Ihre PrestaShop-Fehlerprotokolle (normalerweise in `var/logs/` oder `app/logs/` für PS 1.7+) auf verwandte Fehler während des Gutscheingenerierungsprozesses.

**F4: Der geteilte Inhalt auf Facebook sieht nicht richtig aus (z.B. fehlende Preise, falsches Bild).**
*   **A:**
    1.  **Moduleinstellungen:** Überprüfen Sie die "Einstellungen für geteilte Inhalte" in der Modulkonfiguration (Preise anzeigen, Gesamtsumme anzeigen, Produkte anzeigen, Produkt-URL anzeigen). Stellen Sie sicher, dass sie alle auf "JA" gesetzt sind, wenn Sie maximale Details wünschen.
    2.  **Facebook Open Graph:** Facebook verwendet Open Graph (OG)-Tags von Ihren Produktseiten, um Vorschauen zu generieren. Stellen Sie sicher, dass Ihr PrestaShop-Theme und andere Module diese OG-Tags (insbesondere `og:image`, `og:title`, `og:description`) korrekt generieren. Sie können den [Sharing Debugger](https://developers.facebook.com/tools/debug/) von Facebook verwenden, um zu sehen, wie Facebook Ihre URLs scrapt.
    3.  **Cache:** Leeren Sie Ihren PrestaShop-Cache und Ihren Browser-Cache. Facebook speichert auch geteilte Inhalte im Cache, daher verwenden Sie den Sharing Debugger, um "Erneut scrapen", wenn Sie Änderungen vorgenommen haben.

**F5: Das Modul sieht mit meinem benutzerdefinierten Theme nicht gut aus.**
*   **A:** Das Modul verwendet seine eigenen CSS-Dateien (`css.css`, `ps16.css`). Ihr benutzerdefiniertes Theme könnte diese Stile überschreiben oder mit ihnen in Konflikt geraten.
    1.  **Element untersuchen:** Verwenden Sie die Entwicklertools Ihres Browsers (F12), um den Teilen-Button und die Gutscheinanzeige zu untersuchen. Identifizieren Sie die vom Modul und Ihrem Theme angewendeten CSS-Klassen.
    2.  **Benutzerdefiniertes CSS:** Sie können benutzerdefiniertes CSS zu Ihrer Theme-Datei `custom.css` (oder einer entsprechenden Datei) hinzufügen, um die Stile des Moduls zu überschreiben und es besser an Ihr Theme anzupassen. Zielen Sie auf die spezifischen Klassen des Moduls ab, um andere Teile Ihres Shops nicht zu beeinflussen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul "Facebook Warenkorb teilen + Gutscheincode" folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse und `ModuleFrontController` für Front-Office-Interaktionen nutzt. Es integriert sich mit dem JavaScript SDK von Facebook für die Teilen-Funktionalität und verwendet das `CartRule`-Objekt von PrestaShop für die Gutscheingenerierung. Die Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   `cartshare/controllers/front/cartshare.php`
        *   **Klassenname & Elternklasse:** `CartshareCartshareModuleFrontController` erweitert `ModuleFrontController`.
        *   **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die Verarbeitung des AJAX-Callbacks von Facebook nach einem Teilen oder für das Rendern der dedizierten Warenkorb-Teilen-Seite zuständig, falls das Modul eine solche hat. Er würde das Teilen-Ereignis verarbeiten und die Gutscheingenerierungslogik auslösen. Er könnte auch für das Rendern der `cartsharepage.tpl`-Vorlage verantwortlich sein.
    *   `cartshare/controllers/front/index.php`
        *   **Klassenname & Elternklasse:** Dies ist typischerweise eine leere Datei oder eine einfache Weiterleitung, um die Verzeichnisauflistung zu verhindern, was in PrestaShop-Modulen üblich ist. Sie enthält keine spezifische Controller-Klasse.
        *   **Verantwortlichkeit:** Sicherheitsmaßnahme, um den direkten Zugriff auf das `front`-Verzeichnis zu verhindern.

-   **Back-Office-Admin-Controller**:
    *   Keine. Die gesamte Administration wird über die Methode `getContent()` der Hauptmodulklasse abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul scheint keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/` zu definieren. Seine Kernlogik für die Gutscheingenerierung interagiert wahrscheinlich direkt mit der `CartRule`-Klasse von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

-   `cartshare/lib/voucherengine/script.js`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Dieses Skript ist entscheidend für die clientseitige Interaktion. Es initialisiert wahrscheinlich das Facebook JavaScript SDK unter Verwendung der `cshare_appid` aus der Modulkonfiguration. Es bindet Event-Listener an den "Auf Facebook teilen"-Button, handhabt den Facebook-Teilen-Dialog und führt nach erfolgreichem Teilen einen AJAX-Aufruf an den `cartshare.php`-Front-Controller durch, um die Gutscheingenerierung auszulösen und den Gutscheincode dem Benutzer anzuzeigen. Es könnte auch die dynamische Anzeige des Gutscheincodes auf der Seite handhaben.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `cartshare/css.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Enthält allgemeine Stile für die Elemente des Moduls, wie den Teilen-Button, den Gutscheinanzeigebereich und alle anderen vom Modul eingeführten UI-Komponenten.
-   `cartshare/lib/voucherengine/ps16.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Enthält wahrscheinlich spezifische Stil-Anpassungen oder Überschreibungen, die auf PrestaShop 1.6-Themes zugeschnitten sind, um Kompatibilität und korrekte Darstellung auf älteren Versionen zu gewährleisten.
-   `cartshare/views/css/css/css.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Dieser Pfad scheint redundant (`css/css/`). Es ist möglich, dass es sich um eine Duplikat- oder ältere Version von `cartshare/css.css` handelt oder sehr spezifische Stile für bestimmte Elemente enthält. Entwickler sollten den Inhalt überprüfen, um seinen Zweck zu verstehen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `cartshare/views/templates/hook/header.tpl`
        *   **Hook:** `displayHeader`
        *   **Ausgabe:** Dieses Template ist für die Einbindung des Facebook JavaScript SDK-Initialisierungscodes und potenziell der Haupt-JavaScript- (`script.js`) und CSS-Dateien des Moduls verantwortlich. Es stellt sicher, dass die Facebook-API bereit ist, bevor der Teilen-Button gerendert wird.
    *   `cartshare/views/templates/hook/share.tpl`
        *   **Hook:** `displayShoppingcart`, `displayOrderConfirmation` (abhängig von der Modulkonfiguration)
        *   **Ausgabe:** Rendert den "Warenkorb auf Facebook teilen"-Button und den Container zur Anzeige des Gutscheincodes nach einem erfolgreichen Teilen. Dies ist die primäre visuelle Komponente, mit der Kunden interagieren.

-   **Front-Office-Templates (`views/templates/front/`)**:
    *   `cartshare/views/templates/front/cartsharepage.tpl`
        *   **Zweck:** Dieses Template wird wahrscheinlich vom `CartshareCartshareModuleFrontController` gerendert und könnte eine dedizierte Seite oder eine Teilansicht zur Anzeige des zu teilenden Warenkorbinhalts oder des Gutscheincodes sein.
    *   `cartshare/views/templates/front/facebook-share-contents.tpl`
        *   **Zweck:** Dieses Template generiert dynamisch den Inhalt, der an den Facebook-Teilen-Dialog übergeben wird. Es konstruiert den Titel, die Beschreibung, das Bild und die URLs basierend auf dem Warenkorb des Kunden und den Konfigurationseinstellungen des Moduls (z.B. `cshare_show_prices`, `cshare_show_products`).
    *   `cartshare/views/templates/front/shopping-cart.tpl`
        *   **Zweck:** Dieses Template könnte eine Überschreibung oder ein zusätzlicher Block sein, der speziell dafür entwickelt wurde, in die Standard-PrestaShop-Warenkorbseite integriert zu werden, möglicherweise um den Teilen-Button oder andere modulspezifische Inhalte direkt in der Warenkorbzusammenfassung zu rendern.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, unter Verwendung von Schlüsseln wie `CSHARE_APPID`, `CSHARE_VOUCHER`, `CSHARE_SHOW_PRICES` usw.
    *   Gutscheine werden als Standard-PrestaShop `CartRule`-Einträge generiert und in `ps_cart_rule` und verwandten Tabellen gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Initialisiert das Facebook SDK, lädt JS/CSS-Assets des Moduls. |
| `displayShoppingcart` | Auf der Warenkorb-Übersichtsseite. | Rendert den "Warenkorb auf Facebook teilen"-Button und den Gutscheinanzeigebereich. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Rendert den "Warenkorb auf Facebook teilen"-Button und den Gutscheinanzeigebereich. |
| `displayShoppingCart` | (Duplikat von `displayShoppingcart` in den Modulinformationen, bezieht sich wahrscheinlich auf denselben Hook) | Rendert den "Warenkorb auf Facebook teilen"-Button und den Gutscheinanzeigebereich. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul "Facebook Warenkorb teilen + Gutscheincode" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.
