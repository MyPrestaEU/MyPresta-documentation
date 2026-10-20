---
title: "Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen' von MyPresta.eu."
sidebar:
  label: "Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Limit quantity of products in cart for unlogged users auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users/)
>
> ---


# Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul. Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren, nach „Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen“ suchen und auf „Konfigurieren“ klicken.

#### **Maximale Anzahl von Produkten im Warenkorb für nicht eingeloggte Benutzer**

- **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die absolute maximale Gesamtmenge an Artikeln, die ein nicht eingeloggter Kunde in seinem Warenkorb haben kann.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf 0 gesetzt:* Das Modul wird effektiv deaktiviert, und nicht eingeloggte Benutzer können eine unbegrenzte Menge an Produkten in ihren Warenkorb legen, genau wie eingeloggte Benutzer.
  - *Wenn auf eine Zahl größer als 0 gesetzt (z.B. 5):* Ein nicht eingeloggter Kunde kann Artikel in seinen Warenkorb legen, bis die Gesamtmenge aller Artikel diese Zahl erreicht. Wenn er versucht, einen weiteren Artikel hinzuzufügen, der diese Grenze überschreiten würde, verhindert das Modul das Hinzufügen und zeigt das Warn-Popup an.
- **Empfohlener Wert:** Dies hängt vollständig von Ihrer Geschäftsstrategie ab.
  - *Für B2C-Shops, die eine sanfte Anmeldung fördern möchten:* Ein Wert wie `3` oder `5` kann effektiv sein.
  - *Für B2B-Shops oder Shops mit hochwertigen Artikeln:* Ein niedrigerer Wert wie `1` oder `2` könnte angemessen sein, um sicherzustellen, dass nur ernsthafte, eingeloggte Käufer Lagerbestände reservieren können.
  - *Wenn Sie keine Grenzen wünschen:* Setzen Sie auf `0`.
- **Händlerszenario / Beispiel:** Sie verkaufen individuell bedruckte T-Shirts. Sie möchten, dass gelegentliche Browser ein paar Designs in ihrem Warenkorb sehen, aber für eine größere Bestellung bevorzugen Sie, dass sie sich anmelden. Sie setzen dies auf `3`. Ein nicht eingeloggter Kunde fügt ein T-Shirt (Menge 1) hinzu, dann ein weiteres (Menge 1), dann ein drittes (Menge 1). Sein Warenkorb enthält nun 3 Artikel. Wenn er versucht, ein viertes T-Shirt hinzuzufügen, sieht er die Popup-Nachricht, die ihn zur Anmeldung auffordert.

#### **Nachricht für nicht eingeloggte Benutzer**

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, den Text der Popup-Nachricht anzupassen, die erscheint, wenn ein nicht eingeloggter Benutzer versucht, die definierte Warenkorb-Mengenbegrenzung zu überschreiten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn Sie es als Standard belassen:* Die Standardnachricht „Als nicht eingeloggter Kunde können Sie keine weiteren Produkte in den Warenkorb legen. Bitte melden Sie sich an, um den Vorgang fortzusetzen.“ wird angezeigt.
  - *Wenn Sie es anpassen:* Ihre benutzerdefinierte Nachricht wird stattdessen angezeigt. Dies ermöglicht es Ihnen, den Ton anzupassen, spezifische Anweisungen hinzuzufügen oder sogar einen Link einzufügen (obwohl direkte Links in Popups ohne weitere Anpassung schwierig sein können).
- **Empfohlener Wert:** Die Standardnachricht ist klar und effektiv. Ändern Sie sie nur, wenn Sie eine spezifische Markenstimme oder zusätzliche Anweisungen vermitteln möchten. Halten Sie sie prägnant.
- **Händlerszenario / Beispiel:** Sie möchten einen etwas sanfteren Ton. Sie ändern die Nachricht in: „Um weitere Artikel in Ihren Warenkorb zu legen, melden Sie sich bitte an oder erstellen Sie ein Konto. Wir würden uns freuen, Sie in unserer Community begrüßen zu dürfen!“

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Maximale Anzahl von Produkten im Warenkorb für nicht eingeloggte Benutzer** | `0` (deaktiviert) / `3-5` (für B2C empfohlen) | Legt die Gesamtzahl der Artikel fest, die ein nicht eingeloggter Kunde in seinen Warenkorb legen kann. Verhindert weitere Hinzufügungen und zeigt ein Popup an, wenn die Grenze überschritten wird. |
| Modulkonfiguration | **Nachricht für nicht eingeloggte Benutzer** | „Als nicht eingeloggter Kunde können Sie keine weiteren Produkte in den Warenkorb legen. Bitte melden Sie sich an, um den Vorgang fortzusetzen.“ | Passt den Text an, der im Popup angezeigt wird, wenn ein nicht eingeloggter Benutzer die Warenkorbgrenze erreicht. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe ein Limit festgelegt, aber nicht eingeloggte Benutzer können immer noch unbegrenzt Produkte hinzufügen. Was ist falsch?**
A:

1.  **Überprüfen Sie die Einstellung „Maximale Menge“:** Stellen Sie sicher, dass sie auf eine Zahl größer als `0` eingestellt ist. Wenn sie `0` ist, ist das Modul deaktiviert.
2.  **Leeren Sie Ihren Browser-Cache:** Ihr Browser zeigt Ihnen möglicherweise eine alte Version der Seite an. Versuchen Sie, den Cache und die Cookies Ihres Browsers zu leeren, oder testen Sie in einem Inkognito-/privaten Browserfenster.
3.  **Leeren Sie den PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
4.  **Stellen Sie sicher, dass Sie wirklich nicht angemeldet sind:** Überprüfen Sie noch einmal, ob Sie in Ihrem Browser nicht in einem Kundenkonto angemeldet sind. Der einfachste Weg zum Testen ist, ein neues Inkognito-/privates Browserfenster zu öffnen.

**F: Die Popup-Nachricht wird nicht angezeigt oder sieht seltsam aus.**
A:

1.  **Überprüfen Sie die Einstellung „Nachricht für nicht eingeloggte Benutzer“ des Moduls:** Stellen Sie sicher, dass sie nicht leer ist, wenn Sie eine benutzerdefinierte Nachricht erwarten.
2.  **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können sehr stark angepasste Themes manchmal JavaScript oder CSS stören. Wenn das Popup überhaupt nicht erscheint, überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler (F12-Taste, dann Registerkarte Konsole). Wenn es seltsam aussieht, könnte es ein CSS-Konflikt sein. Kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F: Betrifft dieses Modul eingeloggte Kunden?**
A: Nein, dieses Modul richtet sich speziell an *nicht eingeloggte* Benutzer. Sobald sich ein Kunde in seinem Konto anmeldet, gilt die von diesem Modul auferlegte Mengenbegrenzung nicht mehr für ihn.

**F: Kann ich unterschiedliche Limits für verschiedene Produktkategorien festlegen?**
A: Nein, dieses Modul wendet eine einzige, globale Mengenbegrenzung für alle Produkte im Warenkorb für nicht eingeloggte Benutzer an. Es unterstützt keine kategorie- oder produktspezifischen Limits.

**F: Was passiert, wenn ein nicht eingeloggter Benutzer 3 Artikel hinzufügt, sich dann anmeldet und dann versucht, weitere hinzuzufügen?**
A: Sobald sich der Benutzer anmeldet, gilt er nicht mehr als „nicht eingeloggter“ Benutzer. Die Beschränkung des Moduls wird aufgehoben, und er kann weiterhin Produkte in seinen Warenkorb legen, ohne eine Mengenbegrenzung durch dieses Modul.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen“ (`lqfu`) ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich durch eine Hauptmodulklasse (`lqfu/index.php`) und eine benutzerdefinierte JavaScript-Datei (`lqfu/views/js/lqfu.js`) implementiert wird. Es nutzt das Hook-System von PrestaShop, um sein JavaScript in das Front Office zu injizieren, und verwendet AJAX, um mit der serverseitigen Logik zu kommunizieren, um die Warenkorb-Mengenbegrenzung für Gastbenutzer zu überprüfen und durchzusetzen. Das Modul speichert seine Konfiguration in `ps_configuration`.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Logik des Moduls wird direkt über die `hookDisplayHeader` der Hauptmoduldatei und AJAX-Anfragen abgewickelt, die vom PrestaShop-Kern `CartController` oder `ProductController` verarbeitet und von der Modullogik abgefangen werden.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- In diesem Modul sind keine benutzerdefinierten Klassen, die `ObjectModel` erweitern, definiert. Die gesamte Logik befindet sich innerhalb der Hauptklasse `Lqfu` in `index.php`.

### 4.4 JavaScript-Assets (`views/js/`)

- **`lqfu/views/js/lqfu.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript ist dafür verantwortlich, „In den Warenkorb legen“-Aktionen abzufangen, die aktuelle Warenkorbmenge für nicht eingeloggte Benutzer zu überprüfen und die benutzerdefinierte Popup-Nachricht anzuzeigen, wenn das Limit überschritten wird.
  - **Hauptfunktionalität:**
    - Bindet Event-Listener an „In den Warenkorb legen“-Schaltflächen (oder Formulare) im gesamten Shop (z.B. Produktseite, Kategorieauflistungen).
    - Bei einem „In den Warenkorb legen“-Versuch prüft es zuerst, ob der Benutzer angemeldet ist.
    - Wenn der Benutzer nicht angemeldet ist, ruft es die aktuelle Warenkorbmenge ab (entweder von einem versteckten Element oder durch einen AJAX-Aufruf, falls erforderlich).
    - Vergleicht die aktuelle Warenkorbmenge + die hinzugefügte Menge mit dem konfigurierten Höchstlimit.
    - Wenn das Limit überschritten wird, verhindert es die Standardaktion „In den Warenkorb legen“, zeigt ein benutzerdefiniertes Modal/Popup mit der konfigurierten Nachricht an und deaktiviert möglicherweise vorübergehend die Schaltfläche „In den Warenkorb legen“.
    - Das Skript verwendet wahrscheinlich jQuery für DOM-Manipulation und Ereignisbehandlung, was im PrestaShop-Front-Office üblich ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`lqfu/views/css/lqfu.css`**
  - **Umfang:** Front-Office-Kundenstyling.
  - **Zweck:** Bietet grundlegendes Styling für die Popup-Nachricht, die erscheint, wenn ein nicht eingeloggter Benutzer die Warenkorb-Mengenbegrenzung überschreitet.
  - **Wichtige CSS-Klassenselektoren:** Entwickler können Klassen erwarten, die sich auf den Popup-Container, den Nachrichtentext und möglicherweise Schaltflächen zum Schließen beziehen. Diese können in der `custom.css` oder `theme.css` eines benutzerdefinierten Themes überschrieben werden, um dem Branding des Shops zu entsprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, aber das Modul könnte implizit Inhalte über `displayHeader` oder ähnliche Hooks rendern, wenn es versteckte Daten oder anfängliche JS-Variablen injizieren muss.
- **Admin-Templates (`views/templates/admin/`)**:
  - **`lqfu/views/templates/admin/json.tpl`**: Dieses Template wird wahrscheinlich zum Rendern von JSON-Daten in einer strukturierten Weise innerhalb des Back Office verwendet, möglicherweise zum Debuggen oder für spezifische AJAX-Antworten von der Konfigurationsseite des Moduls, obwohl seine direkte Verwendung für die Hauptkonfiguration weniger üblich ist. Es könnte ein Überbleibsel sein oder für eine spezifische interne Modulfunktion verwendet werden.
- **Front-Office-Templates (`views/templates/front/`)**: Keine. Das Popup wird wahrscheinlich dynamisch über JavaScript generiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert:
    - `PS_LQFU_MAX_QUANTITY`: Speichert den ganzzahligen Wert für die maximale Produktmenge für nicht eingeloggte Benutzer.
    - `PS_LQFU_MESSAGE`: Speichert den Zeichenfolgenwert für die benutzerdefinierte Nachricht, die im Popup angezeigt wird.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Injiziert die CSS- (`lqfu.css`) und JavaScript-Dateien (`lqfu.js`) des Moduls in das Front Office. Kann auch Konfigurationsvariablen (wie die maximale Menge und Nachricht) an das JavaScript übergeben. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert wurde (z.B. Produkt hinzugefügt/entfernt). | Das Modul fängt diesen Hook (oder einen ähnlichen wie `actionObjectCartAddAfter`) wahrscheinlich ab, um die Warenkorbmenge neu zu bewerten und möglicherweise das Hinzufügen von Artikeln zu verhindern, wenn das Limit für einen nicht eingeloggten Benutzer überschritten wird. Hier würde die serverseitige Validierung erfolgen, bevor das JS-Popup ausgelöst wird. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung für das Modul „Menge der Produkte im Warenkorb für nicht eingeloggte Benutzer begrenzen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
