---
title: "Facebook Fan Coupons - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Fan Coupons von MyPresta.eu."
sidebar:
  label: "Facebook Fan Coupons - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Fan Coupons auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-fan-coupons.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-fan-coupons/)
>
> ---


# Facebook Fan Coupons

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss in der Lage sein, mit der Facebook-API zu kommunizieren.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Facebook Fan Coupons Modul, auf dem Sie definieren, wie die Coupons generiert werden und wie sich das Modul verhält.

#### Allgemeine Einstellungen

-   **Was diese Einstellung bewirkt:** Diese Einstellungen steuern das Gesamtverhalten des Moduls, einschließlich Updates und grundlegender Funktionalität.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   `mypresta_updates`, `update_`, `updatev_`: Dies sind interne Einstellungen, die sich auf Modul-Updates und Versionsprüfungen von MyPresta.eu beziehen. Sie müssen diese im Allgemeinen nicht ändern.
-   **Empfohlener Wert:** Belassen Sie diese bei ihren Standardwerten.
-   **Händlerszenario / Beispiel:** Diese Einstellungen stellen sicher, dass Ihr Modul aktuell und mit den MyPresta.eu-Diensten kompatibel ist.

#### Coupon-Generierungs-Einstellungen

-   **FANCOUPON\_FONTSTYLE**

    -   **Was diese Einstellung bewirkt:** Definiert den Schriftstil, der für den generierten Coupon-Code verwendet wird, der dem Kunden auf Ihrem Facebook-Tab angezeigt wird. Dies dient rein der visuellen Darstellung.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn auf eine bestimmte Schriftart eingestellt:* Der Coupon-Code wird in dieser Schriftart angezeigt, wodurch er optisch ansprechender wird oder zu Ihrer Marke passt.
        -   *Wenn Standard belassen:* Eine Standard-, lesbare Schriftart wird verwendet.
    -   **Empfohlener Wert:** Wählen Sie eine klare, lesbare Schriftart, die zur Ästhetik Ihrer Marke passt.
    -   **Händlerszenario / Beispiel:** Wenn Ihre Marke eine bestimmte stilvolle Schriftart verwendet, können Sie deren Namen hier eingeben (z. B. „Arial Black“, „Verdana“), damit der Coupon integrierter aussieht.
-   **FANCOUPON\_VOUCHERCODE**

    -   **Was diese Einstellung bewirkt:** Dies ist das *Präfix* für die automatisch generierten Gutscheincodes. Jeder Code beginnt mit diesem Text, gefolgt von zufälligen Zeichen.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn auf „FANCOUPON“ eingestellt:* Alle generierten Codes sehen aus wie „FANCOUPONABCD123“.
        -   *Wenn auf „FBPROMO“ eingestellt:* Alle generierten Codes sehen aus wie „FBPROMOXYZ789“.
    -   **Empfohlener Wert:** Ein kurzes, einprägsames Präfix, das sich auf Facebook oder Ihre Promotion bezieht (z. B. „FBPROMO“, „FAN2024“, „MYFAN“).
    -   **Händlerszenario / Beispiel:** Die Verwendung von „FBPROMO“ hilft Ihnen, in Ihrer PrestaShop-Bestellhistorie leicht zu erkennen, welche Bestellungen aus dieser Facebook-Kampagne stammen.
-   **FANCOUPON\_MODE**

    -   **Was diese Einstellung bewirkt:** Bestimmt die Art des Rabatts, den der generierte Gutscheincode bietet (z. B. Prozentsatz, fester Betrag, kostenloser Versand).
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Prozentualer Rabatt:* Der Coupon reduziert den Gesamtbetrag der Bestellung um einen Prozentsatz (z. B. 10 % Rabatt).
        -   *Fester Betrag Rabatt:* Der Coupon reduziert den Gesamtbetrag der Bestellung um einen festen monetären Wert (z. B. 10 $ Rabatt).
        -   *Kostenloser Versand:* Der Coupon macht den Versand für die Bestellung kostenlos.
    -   **Empfohlener Wert:** Dies hängt von Ihrer Marketingstrategie ab. Prozentuale Rabatte sind oft beliebt für allgemeine Aktionen.
    -   **Händlerszenario / Beispiel:** Um neuen Facebook-Fans 15 % Rabatt anzubieten, würden Sie hier „Prozentualer Rabatt“ auswählen und dann „15“ in das entsprechende Wertfeld eingeben (das nach Auswahl des Modus erscheint).
-   **FANCOUPON\_CHARS**

    -   **Was diese Einstellung bewirkt:** Gibt die Arten von Zeichen (Buchstaben, Zahlen) an, die im *zufälligen Teil* des generierten Gutscheincodes verwendet werden.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Buchstaben und Zahlen:* Codes sind eine Mischung aus alphanumerischen Zeichen (z. B. „ABC123“).
        -   *Nur Zahlen:* Codes enthalten nur Ziffern (z. B. „123456“).
        -   *Nur Buchstaben:* Codes enthalten nur Buchstaben (z. B. „ABCDEF“).
    -   **Empfohlener Wert:** „Buchstaben und Zahlen“ für maximale Einzigartigkeit und Sicherheit.
    -   **Händlerszenario / Beispiel:** Um Codes leichter lesbar zu machen, könnten Sie „Nur Buchstaben“ wählen, aber dies reduziert die Anzahl der möglichen einzigartigen Kombinationen für eine gegebene Länge.
-   **FANCOUPON\_LENGTH**

    -   **Was diese Einstellung bewirkt:** Definiert die Länge des *zufälligen Teils* des generierten Gutscheincodes (ohne Präfix).
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Kürzere Länge (z. B. 4):* Codes sind schneller einzugeben, aber weniger einzigartig (z. B. „FBPROMOABCD“).
        -   *Längere Länge (z. B. 8):* Codes sind sicherer und einzigartiger, aber länger einzugeben (z. B. „FBPROMOABCD12345“).
    -   **Empfohlener Wert:** 6-8 Zeichen für ein gutes Gleichgewicht zwischen Einzigartigkeit und Benutzerfreundlichkeit.
    -   **Händlerszenario / Beispiel:** Wenn Sie ein sehr hohes Volumen an Coupon-Generierungen erwarten, gewährleistet eine längere Länge, dass jeder Code wirklich einzigartig ist und versehentliche Duplikate verhindert werden.
-   **FANCOUPON\_VOUCHER\_CAT**

    -   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, den generierten Gutscheincode so einzuschränken, dass er nur für Produkte innerhalb bestimmter Kategorien in Ihrem Shop gilt.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn bestimmte Kategorien ausgewählt sind:* Der Coupon funktioniert nur, wenn der Kunde Produkte aus diesen Kategorien in seinem Warenkorb hat.
        -   *Wenn keine Kategorien ausgewählt sind:* Der Coupon gilt für alle Produkte im Shop.
    -   **Empfohlener Wert:** Leer lassen, wenn der Coupon shopweit gelten soll. Kategorien auswählen, wenn Sie bestimmte Produktlinien bewerben möchten.
    -   **Händlerszenario / Beispiel:** Wenn Sie eine Aktion speziell für Ihre „Sommerkollektion“ durchführen, würden Sie diese Kategorie hier auswählen, damit der Coupon nur für diese Artikel funktioniert.
-   **PS\_LANG\_DEFAULT**

    -   **Was diese Einstellung bewirkt:** Dies ist die Standard-Sprach-ID Ihres PrestaShop-Shops. Sie wird intern vom Modul verwendet, um sicherzustellen, dass Coupon-Beschreibungen und andere sprachabhängige Elemente korrekt erstellt werden.
    -   **Auswirkung einer Änderung dieser Einstellung:** Eine falsche Änderung könnte zu Problemen bei der Erstellung von Coupons in der Standardsprache Ihres Shops führen.
    -   **Empfohlener Wert:** Belassen Sie den von PrestaShop automatisch erkannten Standardwert.
    -   **Händlerszenario / Beispiel:** Dies stellt sicher, dass bei der Generierung eines Coupons dessen interne Beschreibung (z. B. „Facebook Fan Coupon“) in Ihrer primären Shop-Sprache korrekt eingestellt wird.

#### Einstellungen für Werbeblöcke (Optional)

-   **FANCOUPON\_ADV\_POS1**

    -   **Was diese Einstellung bewirkt:** Steuert das Bild/Banner, das in der **linken Spalte** Ihres PrestaShop-Shops angezeigt wird, um das Facebook-Coupon-Angebot zu bewerben.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn eine Bild-URL eingegeben wird:* Das angegebene Bild wird in der linken Spalte angezeigt.
        -   *Wenn leer gelassen:* Es wird kein Bild in der linken Spalte angezeigt.
    -   **Empfohlener Wert:** Ein ansprechendes Bannerbild (z. B. 200px breit), das das Angebot „Like uns auf Facebook, erhalte einen Coupon!“ klar bewirbt.
    -   **Händlerszenario / Beispiel:** Sie laden ein benutzerdefiniertes Bannerbild auf Ihren Server hoch (z. B. `img/cms/fb-coupon-left.jpg`) und geben dessen vollständige URL hier ein.
-   **FANCOUPON\_ADV\_POS2**

    -   **Was diese Einstellung bewirkt:** Steuert das Bild/Banner, das in der **rechten Spalte** Ihres PrestaShop-Shops angezeigt wird, um das Facebook-Coupon-Angebot zu bewerben.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn eine Bild-URL eingegeben wird:* Das angegebene Bild wird in der rechten Spalte angezeigt.
        -   *Wenn leer gelassen:* Es wird kein Bild in der rechten Spalte angezeigt.
    -   **Empfohlener Wert:** Ähnlich wie `FANCOUPON_ADV_POS1`, ein ansprechendes Bannerbild (z. B. 200px breit).
    -   **Händlerszenario / Beispiel:** Sie könnten ein anderes Design für das Banner in der rechten Spalte verwenden oder einfach das der linken Spalte duplizieren.
-   **FANCOUPON\_ADV\_POS3**

    -   **Was diese Einstellung bewirkt:** Steuert das Bild/Banner, das in der **Fußzeile** Ihres PrestaShop-Shops angezeigt wird, um das Facebook-Coupon-Angebot zu bewerben.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn eine Bild-URL eingegeben wird:* Das angegebene Bild wird in der Fußzeile angezeigt.
        -   *Wenn leer gelassen:* Es wird kein Bild in der Fußzeile angezeigt.
    -   **Empfohlener Wert:** Ein ansprechendes Bannerbild, das für den Fußzeilenbereich geeignet ist.
    -   **Händlerszenario / Beispiel:** Ein breiteres, kürzeres Banner (z. B. 900px breit, 100px hoch), das gut in die Fußzeile passt.
-   **FANCOUPON\_ADV\_URL**

    -   **Was diese Einstellung bewirkt:** Dies ist die URL, zu der alle Werbebanner (`FANCOUPON_ADV_POS1`, `POS2`, `POS3`) verlinken, wenn sie angeklickt werden. Dies sollte die direkte URL zu Ihrem Facebook-Fanseiten-Tab sein, auf dem der Coupon generiert werden kann.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn auf Ihre Facebook-Tab-URL eingestellt:* Das Klicken auf eines der Banner führt den Kunden direkt zum Coupon-Generierungs-Tab auf Ihrer Facebook-Seite.
        -   *Wenn leer oder falsch:* Die Banner sind nicht anklickbar oder führen zu einer falschen Seite.
    -   **Empfohlener Wert:** Die genaue URL Ihres Facebook-Fanseiten-Tabs, auf dem das Coupon-Modul eingebettet ist.
    -   **Händlerszenario / Beispiel:** Nach dem Einrichten des Facebook-Tabs erhalten Sie eine eindeutige URL dafür (z. B. `https://www.facebook.com/IHRESEITE/app_1234567890`). Geben Sie diese URL hier ein.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | `FANCOUPON_FONTSTYLE` | Standard-Systemschriftart | Schriftstil für den angezeigten Coupon-Code auf Facebook. |
| Modulkonfiguration | `FANCOUPON_VOUCHERCODE` | `FANCOUPON` | Präfix für generierte Gutscheincodes. Hilft bei der Kampagnenidentifikation. |
| Modulkonfiguration | `FANCOUPON_MODE` | Prozentualer Rabatt | Art des Rabatts (Prozentsatz, fester Betrag, kostenloser Versand). |
| Modulkonfiguration | `FANCOUPON_CHARS` | Buchstaben und Zahlen | Zeichensatz für den zufälligen Teil des Codes. |
| Modulkonfiguration | `FANCOUPON_LENGTH` | 6-8 Zeichen | Länge des zufälligen Teils des Codes. Beeinflusst die Einzigartigkeit. |
| Modulkonfiguration | `FANCOUPON_VOUCHER_CAT` | Leer (alle Produkte) | Beschränkt die Coupon-Nutzung auf bestimmte Produktkategorien. |
| Modulkonfiguration | `FANCOUPON_ADV_POS1` | Leer | URL des Bannerbildes für die linke Spalte. |
| Modulkonfiguration | `FANCOUPON_ADV_POS2` | Leer | URL des Bannerbildes für die rechte Spalte. |
| Modulkonfiguration | `FANCOUPON_ADV_POS3` | Leer | URL des Bannerbildes für die Fußzeile. |
| Modulkonfiguration | `FANCOUPON_ADV_URL` | Leer | Ziel-URL für alle Werbebanner (Ihr Facebook-Tab). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Coupons funktionieren nach der Generierung nicht.**
A: Überprüfen Sie Folgendes:
1.  **PrestaShop Warenkorbregeln:** Gehen Sie in Ihrem PrestaShop-Backoffice zu **Katalog > Rabatte > Warenkorbregeln**. Suchen Sie nach Coupons mit dem von Ihnen definierten Präfix (`FANCOUPON_VOUCHERCODE`). Stellen Sie sicher, dass sie aktiv und nicht abgelaufen sind. Das Modul erstellt diese automatisch, aber manchmal kann es zu manuellen Eingriffen oder Konflikten kommen.
2.  **Modulkonfiguration:** Überprüfen Sie Ihre Einstellungen für `FANCOUPON_MODE` und `FANCOUPON_VOUCHER_CAT`. Wenn Sie den Coupon auf eine Kategorie beschränkt haben, stellen Sie sicher, dass der Kunde versucht, ihn für Produkte aus dieser Kategorie zu verwenden.
3.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) und Ihren Browser-Cache.

**F: Die Werbebanner werden in meinem Shop nicht angezeigt.**
A:
1.  **Modul-Hooks:** Stellen Sie sicher, dass das Modul korrekt gehookt ist. Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Facebook Fan Coupons“ und klicken Sie auf „Konfigurieren“. Überprüfen Sie den Tab „Positionen“ (oder „Hooks“ in älteren Versionen), um zu sehen, ob es `displayLeftColumn`, `displayRightColumn` oder `displayFooter` zugewiesen ist. Falls nicht, müssen Sie es möglicherweise manuell über **Design > Positionen** (oder **Module > Positionen**) hooken.
2.  **Bild-URLs:** Überprüfen Sie, ob die für `FANCOUPON_ADV_POS1`, `POS2`, `POS3` eingegebenen URLs korrekt sind und die Bilder an diesen Speicherorten existieren.
3.  **Theme-Kompatibilität:** Einige benutzerdefinierte Themes können Standard-Hook-Positionen überschreiben. Wenn die Banner immer noch nicht angezeigt werden, müssen Sie möglicherweise einen Webmaster bitten, die Template-Dateien Ihres Themes zu überprüfen.

**F: Der Facebook-Tab funktioniert nicht oder zeigt den Coupon-Generator nicht an.**
A: Dieses Modul bietet die Backend-Logik für die Coupon-Generierung. Die eigentliche Einrichtung des Facebook-Tabs erfolgt *innerhalb der Facebook-Entwicklertools* oder einer Drittanbieter-App, die benutzerdefinierte Inhalte einbettet.
1.  **Facebook-App-Einrichtung:** Stellen Sie sicher, dass Sie eine Facebook-App korrekt eingerichtet und mit Ihrer Fanseite verknüpft haben, die auf die URL des Moduls verweist (was typischerweise die Domain Ihres PrestaShop-Shops mit einem spezifischen Pfad oder eine dedizierte Seite ist, die Sie zum Hosten der Modulausgabe eingerichtet haben). Dieses Modul bietet die *Logik* für den Coupon, aber die *Anzeige auf Facebook* erfordert eine korrekte Facebook-App-Konfiguration.
2.  **Facebook-Seitenberechtigungen:** Stellen Sie sicher, dass Ihre Facebook-Seite die erforderlichen Berechtigungen für benutzerdefinierte Tabs hat.
3.  **Sichere (HTTPS) Verbindung:** Facebook verlangt, dass alle eingebetteten Anwendungen über HTTPS ausgeführt werden. Stellen Sie sicher, dass Ihr PrestaShop-Shop vollständig mit einem SSL-Zertifikat gesichert ist.

**F: Wie übersetze ich den Text des Moduls?**
A: Sie können die Phrasen des Moduls über das PrestaShop-Backoffice übersetzen:
1.  Gehen Sie zu **International > Übersetzungen** (oder **Lokalisierung > Übersetzungen** in älteren Versionen).
2.  Wählen Sie „Übersetzungen installierter Module“.
3.  Wählen Sie Ihr Theme, Ihre Sprache und dann „Facebook Fan Coupons“ aus der Modulliste.
4.  Sie können dann alle übersetzbaren Zeichenketten bearbeiten, die vom Modul verwendet werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Facebook Fan Coupons Modul (`fancoupon`) ist ein Standard-PrestaShop-Modul, das sich hauptsächlich auf die Backend-Logik für die Coupon-Generierung und grundlegende Front-Office-Werbung konzentriert. Es nutzt die PrestaShop-Klassen `Module` und `Configuration`, um Einstellungen zu speichern. Die Kernfunktionalität umfasst die dynamische Erstellung von `CartRule`-Objekten (Gutscheinen) basierend auf Benutzerinteraktionen auf einem Facebook-Tab (der extern zu PrestaShop ist, aber mit der Logik des Moduls interagiert). Front-Office-Komponenten beschränken sich auf einfache Bildbanner, die in Standard-Anzeigepositionen gehookt sind.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse abgewickelt. Jede Interaktion zur Coupon-Generierung würde typischerweise von einer externen Facebook-Anwendung gehandhabt, die auf eine URL auf der PrestaShop-Seite verweist, welche dann die Logik des Moduls auslöst (wahrscheinlich über einen Hook oder einen benutzerdefinierten Einstiegspunkt, der im bereitgestellten Inventar nicht explizit als `ModuleFrontController` definiert ist, sondern von der Kernlogik des Moduls bei Aufruf verarbeitet wird).

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält **keine** benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/`. Es verwendet direkt die PrestaShop-Kernklassen `CartRule` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

-   `fancoupon/lib/voucherengine/script.js`
    -   **Geltungsbereich:** Wahrscheinlich Front-Office (für die Facebook-Tab-Oberfläche vorgesehen).
    -   **Verantwortlichkeit:** Dieses Skript soll die clientseitige Logik für den Coupon-Generierungsprozess handhaben. Dies würde umfassen:
        -   Erkennen, ob ein Benutzer die Facebook-Seite „geliked“ hat (über die Facebook-API).
        -   Auslösen einer AJAX-Anfrage an das PrestaShop-Backend (oder den Einstiegspunkt des Moduls), um einen Coupon zu generieren.
        -   Anzeigen des generierten Coupon-Codes für den Benutzer.
        -   Potenzielles Handling von UI-Elementen wie Lade-Spinnern oder Erfolgs-/Fehlermeldungen.
-   `fancoupon/views/js/voucherengine/script.js`
    -   **Geltungsbereich:** Wahrscheinlich Front-Office (für die Facebook-Tab-Oberfläche vorgesehen).
    -   **Verantwortlichkeit:** Dies scheint eine Duplizierung oder eine Version des Skripts in `lib/` zu sein. Es würde denselben Zweck wie oben beschrieben erfüllen und die interaktiven Elemente der Coupon-Generierung auf dem Facebook-Tab handhaben. Entwickler sollten überprüfen, welches `script.js` tatsächlich geladen und verwendet wird.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `fancoupon/lib/voucherengine/ps16.css`
    -   **Geltungsbereich:** Front-Office-Kundenstyling.
    -   **Verantwortlichkeit:** Bietet grundlegendes Styling für die Coupon-Generierungs-Oberfläche, wahrscheinlich innerhalb des Facebook-Tabs. Das `ps16` im Dateinamen deutet darauf hin, dass es Stile enthalten könnte, die speziell auf die Standard-Theme-Struktur von PrestaShop 1.6 zugeschnitten sind, aber es sollte im Allgemeinen kompatibel oder leicht anpassbar sein.
    -   **Wichtige CSS-Klassenselektoren:** Würden typischerweise Stile für Schaltflächen, Eingabefelder, Textanzeigebereiche für den Coupon-Code und das Gesamtlayout des Coupon-Generators umfassen. Entwickler können das gerenderte HTML auf dem Facebook-Tab überprüfen, um spezifische Selektoren zum Überschreiben zu identifizieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/advert-*.tpl`)**:
    -   `fancoupon/views/templates/advert-footer.tpl`
        -   **Hook:** `displayFooter` (oder `footer` in älteren Versionen).
        -   **Ausgabe:** Rendert ein Werbebanner/Bild in der Fußzeile des Shops, das auf den Facebook-Fanseiten-Tab verlinkt. Es verwendet `FANCOUPON_ADV_POS3` als Bildquelle und `FANCOUPON_ADV_URL` für den Link.
    -   `fancoupon/views/templates/advert-left.tpl`
        -   **Hook:** `displayLeftColumn` (oder `leftcolumn` in älteren Versionen).
        -   **Ausgabe:** Rendert ein Werbebanner/Bild in der linken Spalte des Shops, das auf den Facebook-Fanseiten-Tab verlinkt. Es verwendet `FANCOUPON_ADV_POS1` als Bildquelle und `FANCOUPON_ADV_URL` für den Link.
    -   `fancoupon/views/templates/advert-right.tpl`
        -   **Hook:** `displayRightColumn` (oder `rightcolumn` in älteren Versionen).
        -   **Ausgabe:** Rendert ein Werbebanner/Bild in der rechten Spalte des Shops, das auf den Facebook-Fanseiten-Tab verlinkt. Es verwendet `FANCOUPON_ADV_POS2` als Bildquelle und `FANCOUPON_ADV_URL` für den Link.
-   **Admin-Templates (`views/templates/admin/`)**: Keine identifiziert.
-   **Front-Office-Templates (`views/templates/front/`)**: Keine identifiziert. Die Kern-UI zur Coupon-Generierung wird wahrscheinlich dynamisch über JavaScript oder direkt innerhalb der `fancoupon.php`-Logik gerendert, wenn sie von Facebook aufgerufen wird.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    -   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    -   Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `FANCOUPON_FONTSTYLE`, `FANCOUPON_VOUCHERCODE` usw.
    -   Es erstellt Einträge in `ps_cart_rule` und verwandten Tabellen (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group` usw.) für jeden generierten Coupon.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste des Shops. | Zeigt das Werbebanner der linken Spalte an. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste des Shops. | Zeigt das Werbebanner der rechten Spalte an. |
| `displayFooter` | Rendert Inhalte im Fußzeilenbereich des Shops. | Zeigt das Fußzeilen-Werbebanner an. |
| `leftcolumn` | (PrestaShop 1.6.x und älter) Rendert Inhalte in der linken Seitenleiste. | Legacy-Hook für das Werbebanner der linken Spalte. |
| `rightcolumn` | (PrestaShop 1.6.x und älter) Rendert Inhalte in der rechten Seitenleiste. | Legacy-Hook für das Werbebanner der rechten Spalte. |
| `footer` | (PrestaShop 1.6.x und älter) Rendert Inhalte im Fußzeilenbereich. | Legacy-Hook für das Fußzeilen-Werbebanner. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, technischen Support und alle Anfragen bezüglich des Facebook Fan Coupons Moduls wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser engagiertes Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen zur Verfügung.
