---
title: "Mindestbestellwert pro Lieferant - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mindestbestellwert pro Lieferant“ von MyPresta.eu."
sidebar:
  label: "Mindestbestellwert pro Lieferant - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Minimal order value by supplier auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-supplier.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/minimal-order-value-by-supplier/)
>
> ---


# Mindestbestellwert pro Lieferant

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls. Hier können Sie das Modul aktivieren oder deaktivieren und auf den zentralen Verwaltungsbildschirm für Ihre Lieferanten-Mindestwerte zugreifen.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm dient als zentrale Anlaufstelle für das Modul. Er ermöglicht es Ihnen, die gesamte Modulfunktionalität zu aktivieren oder zu deaktivieren und bietet einen direkten Link zur Verwaltung Ihrer Mindestbestellwerte für Lieferanten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul überprüft aktiv die Warenkörbe der Kunden anhand Ihrer definierten Mindestbestellwerte pro Lieferant und blockiert den Checkout, wenn die Anforderungen nicht erfüllt sind.
  - *Wenn deaktiviert:* Das Modul funktioniert nicht mehr. Es werden keine Mindestbestellwertprüfungen durchgeführt, und Kunden können unabhängig von den Gesamtbestellungen der Lieferanten zur Kasse gehen.
- **Empfohlener Wert:** „JA“ (Aktiviert), wenn Sie die Funktionen des Moduls nutzen möchten.
- **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, aktivieren Sie es hier. Wenn Sie die Regeln vorübergehend aussetzen müssen (z. B. während einer shopweiten Aktion, bei der Sie alle Bestellungen zulassen möchten), können Sie es hier deaktivieren.

Auf diesem Bildschirm finden Sie auch eine Schaltfläche oder einen Link zu **„Mindestbestellwerte pro Lieferant verwalten“**. Wenn Sie darauf klicken, gelangen Sie zum speziellen Administrationsbildschirm, auf dem Sie die eigentlichen Regeln definieren.

### 2.2 Spezielle Admin-Bildschirme & Controller-Ansichten

#### AdminMobsController (Back Office > Module > Mindestbestellwert pro Lieferant > Mindestbestellwerte verwalten)

Dies ist der Hauptbildschirm, auf dem Sie die Mindestbestellwerte für jeden Ihrer Lieferanten definieren und verwalten.

- **Bildschirmname & Menüpfad:** Sie gelangen zu diesem Bildschirm, indem Sie zu **Module > Modul-Manager** navigieren, „Mindestbestellwert pro Lieferant“ suchen, auf „Konfigurieren“ klicken und dann auf die Schaltfläche/den Link „Mindestbestellwerte pro Lieferant verwalten“ klicken.
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Dieser Bildschirm zeigt eine Tabelle aller aktuell konfigurierten Mindestbestellwerte an. Jede Zeile zeigt typischerweise:
    - **Lieferantenname:** Der Name des Lieferanten, für den die Regel gilt.
    - **Mindestbestellwert:** Der Geldbetrag, den Produkte dieses Lieferanten im Warenkorb erreichen müssen.
    - **Aktionen:** Normalerweise Schaltflächen „Bearbeiten“ und „Löschen“, um eine bestehende Regel zu ändern oder zu entfernen.
  - **Schaltfläche „Neue Regel hinzufügen“:** Eine Schaltfläche (z. B. „Neuen Mindestbestellwert hinzufügen“), um eine neue Regel zu erstellen.
  - **Formular „Hinzufügen/Bearbeiten“:** Beim Hinzufügen einer neuen Regel oder Bearbeiten einer bestehenden sehen Sie typischerweise ein Formular mit den folgenden Feldern:
    - **Lieferantenauswahl:** Ein Dropdown-Menü oder Suchfeld zur Auswahl eines Ihrer bestehenden Lieferanten.
    - **Mindestwert:** Ein Eingabefeld, in das Sie den numerischen Mindestbestellwert eingeben, der für Produkte des ausgewählten Lieferanten erforderlich ist. Dieser Wert wird in der Standardwährung Ihres Shops (z. B. EUR, USD) angegeben.
    - **Schaltfläche „Speichern“:** Um Ihre Änderungen zu übernehmen.
- **Auswirkung von Änderungen:**
  - *Regel hinzufügen:* Nach dem Speichern wird der neue Mindestbestellwert für den ausgewählten Lieferanten sofort aktiv. Kunden müssen diesen Wert für Produkte dieses Lieferanten erreichen.
  - *Regel bearbeiten:* Das Ändern des Mindestwerts oder des Lieferanten für eine bestehende Regel aktualisiert die aktive Anforderung.
  - *Regel löschen:* Entfernt die Mindestbestellwertanforderung für diesen spezifischen Lieferanten. Kunden werden nicht mehr durch einen Mindestkauf bei diesem Lieferanten eingeschränkt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Lieferanten identifizieren:** Bestimmen Sie, welche Lieferanten Mindestbestellwerte benötigen, basierend auf Ihren Geschäftsanforderungen (z. B. hohe Versandkosten, Dropshipping-Vereinbarungen).
  2. **Regeln hinzufügen:** Klicken Sie für jeden identifizierten Lieferanten auf „Neuen Mindestbestellwert hinzufügen“, wählen Sie den Lieferanten aus, geben Sie den Mindestbetrag ein und speichern Sie.
  3. **Überwachen & Anpassen:** Überprüfen Sie regelmäßig Ihre Lieferantenvereinbarungen und Verkaufsdaten. Wenn ein Lieferant seine Bedingungen ändert oder Sie einen Trend unrentabler Kleinbestellungen bemerken, kehren Sie zu diesem Bildschirm zurück, um Regeln anzupassen oder neue hinzuzufügen.
  4. **Testen:** Nach dem Hinzufügen oder Ändern von Regeln testen Sie immer die Funktionalität, indem Sie Produkte der betroffenen Lieferanten in Ihren Warenkorb im Front Office legen und versuchen, zur Kasse zu gehen.

#### index.php (mobs/controllers/admin/index.php)

Diese Datei dient typischerweise als Platzhalter oder Weiterleitung innerhalb des Admin-Controller-Verzeichnisses und präsentiert dem Händler keinen direkten Konfigurationsbildschirm. Ihre Hauptfunktion besteht in der Regel darin, sicherzustellen, dass der direkte Zugriff auf das Verzeichnis ordnungsgemäß behandelt wird, oft durch Weiterleitung zur Hauptmodulkonfiguration oder einer Fehlerseite. Händler werden nicht direkt mit dieser Datei interagieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktivieren/deaktivieren | Aktiviert | Steuert, ob die Funktionalität des Moduls (Mindestbestellwertprüfungen) aktiv oder inaktiv ist. |
| **AdminMobsController** | Neue Regel hinzufügen (Lieferant) | N/A | Wählt einen Lieferanten aus, für den eine Mindestbestellwertregel gelten soll. |
| **AdminMobsController** | Neue Regel hinzufügen (Mindestwert) | N/A | Legt den monetären Schwellenwert für Produkte des ausgewählten Lieferanten fest. |
| **AdminMobsController** | Regel bearbeiten (Lieferant) | N/A | Ändert den Lieferanten, der einer bestehenden Regel zugeordnet ist. |
| **AdminMobsController** | Regel bearbeiten (Mindestwert) | N/A | Ändert den monetären Schwellenwert für eine bestehende Lieferantenregel. |
| **AdminMobsController** | Regel löschen | N/A | Entfernt eine Mindestbestellwertanforderung für einen bestimmten Lieferanten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe einen Mindestwert festgelegt, aber er funktioniert im Warenkorb nicht. Was sollte ich überprüfen?**
A1:

1. **Ist das Modul aktiviert?** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Mindestbestellwert pro Lieferant“ und stellen Sie sicher, dass es aktiviert ist.
2. **Ist die Regel korrekt konfiguriert?** Gehen Sie zum Bildschirm „Mindestbestellwerte pro Lieferant verwalten“ und überprüfen Sie, ob der Lieferant korrekt ausgewählt und der Mindestwert als Zahl (ohne Währungssymbole) eingegeben wurde.
3. **Sind die Produkte dem Lieferanten korrekt zugeordnet?** Überprüfen Sie die Produkte im Warenkorb des Kunden, um sicherzustellen, dass sie tatsächlich dem Lieferanten zugeordnet sind, für den Sie die Regel festgelegt haben.
4. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.

**F2: Die Benachrichtigung wird angezeigt, aber nicht in der Sprache meines Shops.**
A2: Die Front-Office-Nachrichten des Moduls sind übersetzbar.

1. Gehen Sie zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme, wählen Sie Ihre Sprache und klicken Sie auf „Ändern“.
3. Suchen Sie das Modul „mobs“ (Mindestbestellwert pro Lieferant) und übersetzen Sie die relevanten Zeichenketten. Speichern Sie Ihre Änderungen.

**F3: Das Modul blockiert den Checkout, aber ich möchte eine Ausnahme für einen bestimmten Kunden oder eine Bestellung zulassen.**
A3: Das Modul erzwingt Regeln global. Um eine Ausnahme zu machen, müssten Sie die Regel des spezifischen Lieferanten in der Modulkonfiguration (**Module > Mindestbestellwert pro Lieferant > Mindestbestellwerte verwalten**) vorübergehend deaktivieren oder das gesamte Modul deaktivieren, wenn mehrere Regeln aktiv sind. Denken Sie daran, es danach wieder zu aktivieren. Es gibt keine integrierte „Überschreibungsfunktion“ pro Kunde oder Bestellung.

**F4: Das Modul ist aktiv, aber das Styling der Benachrichtigung passt nicht zu meinem Theme.**
A4: Das Modul wird mit einem Basis-Styling geliefert. Wenn es mit Ihrem benutzerdefinierten Theme kollidiert, kann Ihr Webmaster oder Entwickler das CSS des Moduls überschreiben. Die CSS-Datei des Moduls ist `mobs/views/css/mobs.css`. Sie können benutzerdefinierte Stile in die `custom.css` oder `theme.css` Datei Ihres Themes hinzufügen, die die Benachrichtigungselemente des Moduls ansprechen, um sie an Ihr Branding anzupassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Mindestbestellwert pro Lieferant“ (`mobs`) folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es besteht hauptsächlich aus einer Hauptmodulklasse, einem dedizierten Admin-Controller zur Verwaltung von Regeln und einem Front-Controller für AJAX-Interaktionen und die Anzeige von Benachrichtigungen. Es verwendet keine benutzerdefinierten `ObjectModel`-Klassen, sondern speichert die Konfiguration direkt in `ps_configuration` und verwaltet lieferantenspezifische Mindestwerte über den `AdminMobsController`, der wahrscheinlich mit einer benutzerdefinierten Tabelle interagiert oder einen generischen `AdminController` zur Datenverwaltung erweitert. Die Front-Office-Interaktion wird über ein dediziertes Template für den Warenkorb und einen AJAX-Controller für dynamische Prüfungen abgewickelt.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajax.php`
    - **Klassenname & Elternklasse**: `MobsAjaxModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist für die Verarbeitung von AJAX-Anfragen aus dem Front-Office zuständig, die typischerweise von der Warenkorbseite initiiert werden. Er führt wahrscheinlich Echtzeitprüfungen des Warenkorbinhalts gegen die konfigurierten Mindestbestellwerte der Lieferanten durch. Er gibt JSON-Antworten zurück, die angeben, ob die Mindestwerte erfüllt sind, und liefert relevante Nachrichten, falls nicht. Dies ermöglicht dynamische Aktualisierungen der Warenkorbanzeige ohne vollständige Seitenneuladungen.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `MobsIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller könnte als Standardeinstiegspunkt für den Front-Office-Teil des Moduls dienen, obwohl seine Hauptfunktion oft darin besteht, umzuleiten oder eine einfache Seite zu liefern, wenn das Modul keine dedizierte Front-Office-Seite hat. Angesichts der Funktionalität des Moduls ist es wahrscheinlicher, dass der `ajax.php`-Controller die Kernlogik des Front-Office handhabt und `index.php` ein Fallback oder eine minimale Seite ist.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMobs.php`
    - **Klassenname & Elternklasse**: `AdminMobsController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet die Regeln für „Mindestbestellwerte pro Lieferant“. Er bietet die Schnittstelle zum Auflisten, Hinzufügen, Bearbeiten und Löschen dieser Regeln. Er interagiert wahrscheinlich mit einer benutzerdefinierten Datenbanktabelle (z. B. `ps_mobs_rules`), um die Lieferanten-ID und den zugehörigen Mindestwert zu speichern. Die Rasteransicht und die Formularfelder werden mithilfe der PrestaShop-Klassen `HelperList` und `HelperForm` gerendert.
  - `controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Keine spezifische Klasse, typischerweise eine einfache PHP-Datei.
    - **Verantwortlichkeit**: Diese Datei ist normalerweise ein Platzhalter oder eine Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen zu verhindern. Sie enthält oft ein einfaches `header('Location: ../../../index.php?controller=AdminHome');` oder eine ähnliche Weiterleitung zum PrestaShop-Back-Office-Dashboard, um sicherzustellen, dass der direkte Zugriff auf `yourshop.com/modules/mobs/controllers/admin/` keine sensiblen Informationen preisgibt oder Fehler verursacht. Sie präsentiert keinen benutzerorientierten Bildschirm.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul entweder:

1. Seine Konfiguration für einfache Einstellungen direkt in `ps_configuration` speichert.
2. Seine Daten (Lieferanten-Mindestwerte) direkt innerhalb des `AdminMobsController` unter Verwendung standardmäßiger PrestaShop-Datenbankabfragemethoden verwaltet, möglicherweise durch Interaktion mit einer während der Installation erstellten benutzerdefinierten Tabelle, ohne ein dediziertes `ObjectModel`.

Wenn eine benutzerdefinierte Tabelle verwendet wird, wäre ihre Struktur in der `install()`-Methode der Hauptmoduldatei (`mobs/index.php`) definiert.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/mobs.js`
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Diese JavaScript-Datei ist für clientseitige Interaktionen im Zusammenhang mit den Mindestbestellwertprüfungen verantwortlich. Sie wird wahrscheinlich:
    - Event-Listener an Änderungen der Warenkorbmenge, Produktentfernungen oder die Schaltfläche „Zur Kasse gehen“ binden.
    - AJAX-Anfragen an `controllers/front/ajax.php` senden, um den Warenkorb anhand der Lieferanten-Mindestwerte zu validieren.
    - JSON-Antworten vom AJAX-Controller empfangen.
    - Die Anzeige des Warenkorbs dynamisch aktualisieren und Benachrichtigungen anzeigen, wenn die Mindestwerte nicht erreicht werden.
    - Die Schaltfläche „Zur Kasse gehen“ basierend auf den Validierungsergebnissen deaktivieren oder aktivieren.
    - Möglicherweise Logik zur Anzeige von Modal-Popups oder Inline-Fehlermeldungen enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/mobs.css`
  - **Geltungsbereich**: Front-Office-Kunden-Styling.
  - **Beschreibung**: Dieses Stylesheet stellt die visuelle Darstellung für die Front-Office-Elemente des Moduls bereit, hauptsächlich die Benachrichtigungen, die im Warenkorb angezeigt werden.
  - **Wichtige UI-Komponenten und Container, die es stylt**: Es wird wahrscheinlich spezifische CSS-Klassen ansprechen, die vom Modul zum Warenkorb-Template hinzugefügt wurden, wie z. B. `div.mobs-notification`, `p.mobs-error-message` oder ähnliche Elemente, die die Warnungen über nicht erfüllte Mindestbestellwerte anzeigen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler können die HTML-Ausgabe der Modulbenachrichtigungen überprüfen, um die genauen Klassennamen (z. B. `.mobs-alert`, `.mobs-supplier-name`, `.mobs-required-value`) zu identifizieren und sie in der `custom.css` ihres Themes zu überschreiben, um sie an das Branding des Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - Es sind keine spezifischen Hook-Templates im Inventar aufgeführt, was darauf hindeutet, dass die Front-Office-Ausgabe des Moduls hauptsächlich in ein bestehendes Template wie `displayShoppingCart.tpl` oder über ein direktes Template-Rendering innerhalb eines Controllers eingefügt wird.
- **Admin-Templates (`views/templates/admin/`)**:

  - Das Moduldossier listet keine spezifischen Admin-Templates auf. Der `AdminMobsController` verwendet wahrscheinlich die Standard-`HelperList`- und `HelperForm`-Templates von PrestaShop für seine Raster- und Formularansichten, die Teil des PrestaShop-Kernframeworks sind.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Beschreibung**: Dieses Template ist speziell dafür konzipiert, in die Warenkorbseite eingebunden oder dort gerendert zu werden. Es enthält die HTML-Struktur zur Anzeige der Mindestbestellwert-Benachrichtigungen an den Kunden. Es wird wahrscheinlich alle nicht erfüllten Lieferanten-Mindestwerte durchlaufen und für jeden eine Nachricht anzeigen, möglicherweise einschließlich des Lieferantennamens und des noch benötigten Betrags. Dieses Template wird dynamisch durch das `mobs.js`-Skript basierend auf AJAX-Antworten aktualisiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Moduldossier listet keine expliziten benutzerdefinierten Klassen oder SQL-Dateien auf, aber damit der `AdminMobsController` „Mindestbestellwerte pro Lieferant“ verwalten kann, muss er diese Daten speichern. Es ist sehr wahrscheinlich, dass das Modul während seiner `install()`-Methode in `mobs/index.php` eine benutzerdefinierte Tabelle erstellt.
  - **Wahrscheinlicher Tabellenname**: `ps_mobs_rules` (oder ähnlich, z. B. `ps_minimal_order_by_supplier`).
  - **Wahrscheinliche Tabellenstruktur**:
    - `id_mobs_rule` (PRIMÄRSCHLÜSSEL, INT)
    - `id_supplier` (INT, FREMDSCHLÜSSEL zu `ps_supplier.id_supplier`)
    - `min_value` (DECIMAL(20,6))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - **Konfigurationseinträge**: Der Hauptstatus des Moduls (aktivieren/deaktivieren) wird wahrscheinlich in `ps_configuration` mit einem Schlüssel wie `MOBS_ENABLED` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Zum Einbinden von CSS (`mobs.css`) und JavaScript (`mobs.js`) für die Front-Office-Funktionalität. |
| `displayShoppingCartFooter` | Am unteren Rand der Warenkorbseite. | Zum Anzeigen des `displayShoppingCart.tpl`-Templates, das die Benachrichtigungen für nicht erfüllte Mindestbestellwerte enthält. |
| `actionCartSave` | Nach dem Speichern eines Warenkorbs (z. B. Mengenänderung, Produkt hinzufügen/entfernen). | Zum Auslösen der Logik, die Mindestbestellwerte überprüft und möglicherweise den Warenkorbstatus oder Session-Variablen aktualisiert. |
| `actionValidateOrder` | Bevor eine Bestellung offiziell validiert wird. | Zum Durchführen einer abschließenden Überprüfung der Mindestbestellwerte und zum Verhindern der Bestellvalidierung, wenn die Anforderungen nicht erfüllt sind. |
| `displayBeforeCarrier` | Vor dem Schritt zur Auswahl des Versanddienstleisters im Checkout. | Zum Anzeigen von Warnungen oder zum Blockieren des Fortschritts, wenn Mindestwerte in einem früheren Stadium des Checkouts nicht erfüllt sind. |
| `displayPaymentTop` | Am oberen Rand der Zahlungsoptionsseite. | Zum Anzeigen von Warnungen oder zum Blockieren des Fortschritts, wenn Mindestwerte vor der Zahlung nicht erfüllt sind. |

*Hinweis: Das Moduldossier erwähnt „Header, Spalten, Produkt oder Footer“ als Front-Office-Hooks. Während `displayHeader` sicher ist, verwendet das Modul wahrscheinlich `displayShoppingCartFooter` oder einen ähnlichen warenkorbspezifischen Hook für seine Hauptausgabe und `actionCartSave`/`actionValidateOrder` für seine Kernlogik. `displayRightColumn` oder `displayLeftColumn` könnten für optionale statische Blöcke verwendet werden, sind aber für die Kernfunktionalität weniger wahrscheinlich.*

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und den Zugriff auf die neuesten Versionen des Moduls „Mindestbestellwert pro Lieferant“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
