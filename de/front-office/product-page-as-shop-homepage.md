---
title: "Produktseite als Shop-Homepage - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produktseite als Shop-Homepage' von MyPresta.eu."
sidebar:
  label: "Produktseite als Shop-Homepage - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product page as shop homepage auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-page-as-shop-homepage.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-page-as-shop-homepage/)
>
> ---


# Produktseite als Shop-Homepage

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Produktseite als Shop-Homepage“. Sie sehen eine einzige, unkomplizierte Konfigurationsoption.

- **Einstellungsname:** Produkt, das auf der Homepage angezeigt werden soll
  - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie ermöglicht es Ihnen, genau auszuwählen, welches Produkt aus Ihrem Katalog Ihre neue Shop-Homepage werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Produkt ausgewählt ist:* Die Haupt-URL Ihres Shops zeigt die vollständige Produktseite des gewählten Produkts an.
    - *Wenn kein Produkt ausgewählt ist (oder das Modul deaktiviert ist):* Ihr Shop kehrt zu seinem Standard-Homepage-Verhalten zurück (z.B. Anzeige von vorgestellten Produkten, Kategorien oder einer benutzerdefinierten CMS-Seite).
  - **Empfohlener Wert:** Wählen Sie das Produkt aus, das Sie am prominentesten hervorheben möchten. Verwenden Sie die Suchleiste, um Ihr gewünschtes Produkt schnell zu finden.
  - **Händlerszenario / Beispiel:** Sie haben gerade ein revolutionäres neues Gadget auf den Markt gebracht. Sie möchten, dass jeder Besucher Ihres Shops dieses Produkt zuerst sieht. Sie würden den Produktnamen (z.B. „Super Gadget X“) in das Suchfeld eingeben, es aus der Dropdown-Liste auswählen und speichern. Jetzt landet jeder, der `www.ihrshop.com` besucht, direkt auf der Produktseite von „Super Gadget X“.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Produkt, das auf der Homepage angezeigt werden soll | (Anfangs nichts ausgewählt) / Wählen Sie Ihr Schlüsselprodukt | Definiert, welche Produktseite die Standard-Homepage Ihres Shops ersetzt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Homepage zeigt nach der Konfiguration des Moduls immer noch den alten Inhalt an. Was soll ich tun?**
A: Dies ist normalerweise ein Caching-Problem.
1. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Performance**.
2. Klicken Sie oben rechts auf „Cache leeren“.
3. Leeren Sie auch den Cache und die Cookies Ihres Browsers und versuchen Sie dann erneut, auf Ihren Shop zuzugreifen.

**F: Kann ich das vorgestellte Produkt einfach ändern?**
A: Ja! Gehen Sie einfach zurück zu **Module > Modul-Manager**, suchen Sie „Produktseite als Shop-Homepage“, klicken Sie auf „Konfigurieren“ und wählen Sie ein anderes Produkt aus der Dropdown-Liste. Speichern Sie Ihre Änderungen und leeren Sie Ihren Cache.

**F: Was passiert, wenn das ausgewählte Produkt nicht vorrätig oder deaktiviert ist?**
A: Wenn das ausgewählte Produkt nicht vorrätig ist, wird seine Produktseite weiterhin angezeigt, aber der „In den Warenkorb“-Button könnte deaktiviert sein oder eine „Nicht vorrätig“-Meldung anzeigen, abhängig von Ihren PrestaShop-Bestandseinstellungen. Wenn das Produkt vollständig deaktiviert ist, zeigt PrestaShop möglicherweise einen „Seite nicht gefunden“-Fehler an oder kehrt zur Standard-Homepage zurück. Stellen Sie immer sicher, dass das ausgewählte Produkt aktiv und verfügbar ist.

**F: Beeinflusst dieses Modul meine SEO?**
A: Wenn Sie eine Produktseite als Ihre Homepage festlegen, wird die Haupt-URL Ihres Shops (`www.ihrshop.com`) nun den Inhalt dieser Produktseite bereitstellen. Suchmaschinen werden diesen Inhalt für Ihre Hauptdomain indexieren. Wenn Sie zuvor eine reichhaltige, keyword-optimierte Homepage hatten, könnten Sie eine Verschiebung in der Rangfolge Ihrer Hauptdomain feststellen. Stellen Sie sicher, dass die gewählte Produktseite gut für SEO optimiert ist (Titel, Beschreibung, Bilder, Inhalt).

**F: Kann ich dies mit einem benutzerdefinierten Theme verwenden?**
A: Ja, das Modul funktioniert, indem es die Art und Weise überschreibt, wie PrestaShop den `IndexController` versendet. Es sollte mit den meisten benutzerdefinierten Themes kompatibel sein, da es die Standard-Produktseiten-Rendering von PrestaShop nutzt. Wenn Sie Styling-Probleme feststellen, liegt dies wahrscheinlich am CSS Ihres Themes und nicht an der Kernfunktionalität des Moduls.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Produktseite als Shop-Homepage“ funktioniert, indem es die Kern-PrestaShop-Front-Controller überschreibt, um das Verhalten der Standard-Homepage (`IndexController`) umzuleiten. Anstatt das Standard-Homepage-Template zu laden, zwingt es den `ProductController`, die Seite für eine bestimmte Produkt-ID zu rendern, wodurch eine Produktseite effektiv zur Standard-Landingpage für die Root-URL des Shops wird. Dies wird durch eine Reihe von Überschreibungen im Verzeichnis `override/` erreicht.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet hauptsächlich Überschreibungen, um das Controller-Verhalten zu modifizieren.

- **Front-Office-Controller**:
  - `homepageproduct/override/controllers/front/index.php`
    - Diese Datei ist ein Platzhalter oder eine ältere Überschreibung. Im modernen PrestaShop wird der `IndexController` typischerweise direkt überschrieben. Ihre Anwesenheit deutet auf einen Kompatibilitätsmechanismus oder einen älteren Ansatz hin.
  - `homepageproduct/override/controllers/front/IndexController.php`
    - **Klassenname & Elternklasse:** `IndexController` (überschreibt `IndexControllerCore`)
    - **Verantwortlichkeit:** Dies ist die Kernüberschreibung. Wenn die Root-URL des Shops aufgerufen wird, versendet PrestaShop normalerweise den `IndexController`. Diese Überschreibung fängt diesen Versand ab. Sie prüft die Modulkonfiguration auf eine `homepageproduct_product`-ID. Wenn eine Produkt-ID festgelegt ist, leitet sie die Anfrage intern an den `ProductController` für dieses spezifische Produkt weiter oder leitet sie um, wodurch die Produktseite anstelle der Standard-Homepage gerendert wird. Sie stellt sicher, dass der aktuelle Controller-Kontext korrekt auf `ProductController` gesetzt ist und dass die Produktdaten geladen werden.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul verwendet Überschreibungen, um das Verhalten von Kernklassen zu modifizieren, insbesondere in Bezug auf die Controller-Behandlung.

- `homepageproduct/override/classes/controller/FrontController.php`
  - **Klassenname & Elternklasse:** `FrontController` (überschreibt `FrontControllerCore`)
  - **Verantwortlichkeit:** Diese Überschreibung enthält wahrscheinlich Logik, um sicherzustellen, dass die `IndexController`-Überschreibung innerhalb des `FrontController`-Versandprozesses korrekt funktioniert. Sie könnte anpassen, wie der Controller initialisiert wird oder wie Templates zugewiesen werden, wenn die Homepage als Produktseite bereitgestellt wird.
- `homepageproduct/override/classes/controller/index.php`
  - Ähnlich wie `override/controllers/front/index.php` scheint dies ein Platzhalter oder ein älterer Überschreibungsmechanismus zu sein.
- `homepageproduct/override/classes/index.php`
  - Ein weiterer Platzhalter oder eine ältere Überschreibung.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die gesamte Front-Office-Interaktivität für die Produktseite stammt vom Kern-Produktseiten-JS von PrestaShop.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling der Produktseite wird vollständig vom aktiven PrestaShop-Theme übernommen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul führt keine neuen Front-Office-Templates zur Anzeige ein. Es verwendet bestehende PrestaShop-Produktseiten-Templates wieder.

- **Admin-Templates (`views/templates/admin/`)**:
  - `homepageproduct/lib/searchTool/views/scripts.tpl`
    - Dieses Template wird wahrscheinlich innerhalb der `getContent()`-Methode des Moduls im Back Office verwendet. Es enthält wahrscheinlich JavaScript- oder Smarty-Logik, um das Produkt-Suchfeld zu rendern, sodass der Administrator ein Produkt einfach nach Name oder ID für die Homepage finden und auswählen kann. Es könnte AJAX-Aufrufe an `AdminProducts` oder ähnliche Controller für Produktvorschläge enthalten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfiguration in der Tabelle `ps_configuration`:
    - `homepageproduct_product`: Speichert die ID des als Homepage ausgewählten Produkts.
    - `mypresta_updates`, `update_`, `updatev_`: Wird für Modul-Update-Prüfungen durch MyPresta.eu verwendet.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ein standardmäßiger PrestaShop-Konfigurationsschlüssel, der nicht direkt von diesem Modul verwaltet, aber möglicherweise darauf zugegriffen wird.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine explizit neuen Anzeige-Hooks. Seine Funktionalität wird durch Controller-Überschreibungen erreicht. Da es jedoch eine Standard-Produktseite rendert, werden alle Hooks, die normalerweise auf einer Produktseite vorhanden sind (z.B. `displayHeader`, `displayProductButtons`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductExtraContent`, `actionValidateOrder`), ausgeführt, als wäre es eine reguläre Produktseite.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Vor dem Seiteninhalt | Zum Einbinden von CSS, JS, Meta-Tags. |
| `displayLeftColumn` | Linke Spalte der Produktseite | Anzeige von Blöcken wie Kategorien, Filtern. |
| `displayRightColumn` | Rechte Spalte der Produktseite | Anzeige von Blöcken wie Warenkorb, benutzerdefinierte Inhalte. |
| `displayFooter` | Am unteren Ende der Seite | Zum Einbinden von JS, Footer-Inhalten. |
| `displayProductButtons` | In der Nähe des In-den-Warenkorb-Buttons | Hinzufügen von benutzerdefinierten Buttons oder Aktionen auf der Produktseite. |
| `displayProductExtraContent` | Unterhalb der Produktbeschreibung | Hinzufügen zusätzlicher Tabs oder Inhalte zur Produktseite. |
| `actionValidateOrder` | Nach der Validierung einer Bestellung | Für die Nachbearbeitung von Bestellungen (z.B. Tracking). |
| *(Jeder andere Hook, der normalerweise auf einer Produktseite ist)* | Variiert | Standardmäßige Ausführung von PrestaShop-Produktseiten-Hooks. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Produktseite als Shop-Homepage“ verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung unserer Module sicherzustellen.
