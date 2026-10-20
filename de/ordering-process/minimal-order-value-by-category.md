---
title: "Mindestbestellwert nach Kategorie – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mindestbestellwert nach Kategorie“ von MyPresta.eu."
sidebar:
  label: "Mindestbestellwert nach Kategorie – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Minimal order value by category auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-category.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/minimal-order-value-by-category/)
>
> ---


# Mindestbestellwert nach Kategorie

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in den meisten Hosting-Umgebungen standardmäßig verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager aufgerufen wird.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm dient hauptsächlich als Einstiegspunkt. Während die Kernlogik des Moduls über einen dedizierten Administrationsbildschirm verwaltet wird, stellt diese anfängliche Konfigurationsseite sicher, dass das Modul korrekt installiert ist, und bietet einen Link oder eine Weiterleitung zur Hauptverwaltungsoberfläche.
- **Auswirkung der Änderung dieser Einstellung:** Typischerweise hat dieser Bildschirm keine direkten Schalter oder Eingabefelder für den Händler. Sein Hauptzweck ist es, den Status des Moduls zu bestätigen und Sie zum nächsten Schritt zu führen.
- **Empfohlener Wert:** Hier sind keine direkten Werte einzustellen. Stellen Sie einfach sicher, dass das Modul aktiviert ist.
- **Händlerszenario / Beispiel:** Nach der Installation landen Sie hier. Möglicherweise sehen Sie eine Nachricht, die die Installation bestätigt, und eine Schaltfläche oder einen Link zu „Mindestbestellwerte verwalten“ oder Ähnlichem, der Sie zum dedizierten `AdminMobcController`-Bildschirm führt.

### 2.2 Dedizierter Admin-Bildschirm: Verwaltung des Mindestbestellwerts nach Kategorie (Back Office > Module > Mindestbestellwert nach Kategorie)

Dies ist die zentrale Verwaltungsoberfläche, in der Sie alle Ihre kategoriespezifischen Mindestbestellwerte definieren und steuern. Sie finden typischerweise einen neuen Menüpunkt unter „Module“ oder „Katalog“ (abhängig von Ihrer PrestaShop-Version und dem Hook des Moduls) mit dem Namen „Mindestbestellwert nach Kategorie“ oder Ähnlichem.

**Bildschirmname & Menüposition:**
Sie finden diesen Bildschirm, indem Sie im PrestaShop Back Office-Menü zu **Module > Mindestbestellwert nach Kategorie** navigieren.

**Verfügbare Aktionen & Einstellungen:**
Dieser Bildschirm zeigt eine Liste (Raster) aller Ihrer derzeit definierten Regeln für den Mindestbestellwert an. Für jede Regel sehen Sie typischerweise:

- **Kategoriename:** Der Name der PrestaShop-Kategorie, für die die Regel gilt.
- **Mindestwert:** Der erforderliche Mindestbestellwert für Produkte innerhalb dieser Kategorie.
- **Währung:** Die Währung, in der der Mindestwert festgelegt ist (normalerweise die Standardwährung Ihres Shops, z. B. USD, EUR).
- **Aktionen:** Schaltflächen zum „Bearbeiten“ oder „Löschen“ einer bestehenden Regel.

Sie finden auch eine Schaltfläche, normalerweise oben rechts, um **„Neue Regel hinzufügen“** oder **„Neuen Mindestbestellwert hinzufügen“**. Wenn Sie darauf klicken, öffnet sich ein Formular, in dem Sie Folgendes tun können:

1. **Kategorie auswählen:**

   - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl, auf welche bestehende PrestaShop-Kategorie diese Regel für den Mindestbestellwert angewendet werden soll.
   - **Auswirkung der Änderung dieser Einstellung:** Die Auswahl einer Kategorie verknüpft die Regel mit allen Produkten innerhalb dieser Kategorie (und ihren Unterkategorien, abhängig von der Modullogik).
   - **Empfohlener Wert:** Wählen Sie die spezifische Kategorie aus, auf die Sie den Mindestbestellwert anwenden möchten.
   - **Händlerszenario / Beispiel:** Sie möchten einen Mindestwert für Ihre Kategorie „Großhandel“ festlegen. Sie würden „Großhandel“ aus dem Dropdown-Menü auswählen.
2. **Mindestbestellwert:**

   - **Was diese Einstellung bewirkt:** Definiert den Geldbetrag, den Kunden für Produkte *innerhalb der ausgewählten Kategorie* ausgeben müssen, bevor sie ihre Bestellung fortsetzen können.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ein Wert festgelegt ist (z. B. 50.00):* Kunden müssen Produkte im Wert von mindestens 50.00 Einheiten Ihrer Standardwährung aus der ausgewählten Kategorie in ihrem Warenkorb haben. Andernfalls werden sie beim Checkout mit einer Nachricht blockiert.
     - *Wenn leer gelassen oder auf 0 gesetzt:* Diese Regel wäre für die Kategorie effektiv deaktiviert und würde jeden Wert zulassen. Es ist jedoch am besten, die Regel zu löschen, wenn Sie sie nicht benötigen.
   - **Empfohlener Wert:** Ein positiver numerischer Wert, der Ihren gewünschten Mindestwert widerspiegelt (z. B. `25.00`, `100.00`).
   - **Händlerszenario / Beispiel:** Für Ihre Kategorie „Großhandel“ setzen Sie diesen Wert auf `100.00`. Ein Kunde mit Großhandelsprodukten im Wert von 90 € kann nicht auschecken, bis er weitere 10 € hinzufügt.
3. **Speichern-Schaltfläche:**

   - **Was dies bewirkt:** Wendet die Änderungen an oder erstellt die neue Regel.
   - **Auswirkung:** Die neue Regel wird sofort aktiv, und das System beginnt, den Mindestbestellwert für die ausgewählte Kategorie durchzusetzen.

**Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**

1. **Bestehende Regeln überprüfen:** Überprüfen Sie regelmäßig Ihre Regelliste, um sicherzustellen, dass sie weiterhin relevant für Ihre Geschäftsstrategie sind.
2. **Neue Regeln hinzufügen:** Wenn Sie neue Produktkategorien einführen, die spezifische Mindestwerte erfordern (z. B. eine neue B2B-Linie), fügen Sie eine Regel dafür hinzu.
3. **Bestehende Regeln bearbeiten:** Passen Sie Mindestwerte basierend auf Produktpreisänderungen, Marktbedingungen oder Werbestrategien an.
4. **Veraltete Regeln löschen:** Entfernen Sie Regeln für Kategorien, die keinen Mindestwert mehr erfordern oder eingestellt wurden.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | (Keine direkten Einstellungen) | N/A | Einstiegspunkt zum Modul; bestätigt die Installation und leitet zum Verwaltungsbildschirm weiter. |
| Verwaltung des Mindestbestellwerts nach Kategorie | Neue Regel hinzufügen / Regel bearbeiten > Kategorie auswählen | N/A | Verknüpft einen Mindestbestellwert mit einer spezifischen PrestaShop-Produktkategorie. |
| Verwaltung des Mindestbestellwerts nach Kategorie | Neue Regel hinzufügen / Regel bearbeiten > Mindestbestellwert | Ihr gewünschter Mindestwert (z. B. `50.00`) | Legt den erforderlichen Geldbetrag für Produkte innerhalb der ausgewählten Kategorie fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe einen Mindestwert festgelegt, aber er funktioniert nicht. Kunden können immer noch mit weniger auschecken.**
A:

- **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** aktiviert ist.
- **Regelkonfiguration überprüfen:** Gehen Sie zu **Module > Mindestbestellwert nach Kategorie** und bestätigen Sie, dass die Regel für die spezifische Kategorie aktiv ist, einen Wert größer als Null hat und der beabsichtigten Kategorie korrekt zugewiesen ist.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Produktkategoriezuweisung:** Überprüfen Sie nochmals, ob die betreffenden Produkte tatsächlich der Kategorie zugewiesen sind, für die Sie den Mindestwert festgelegt haben.

**F2: Die den Kunden angezeigte Nachricht ist nicht klar oder stimmt nicht mit der Sprache meines Shops überein.**
A:

- **Modulübersetzungen:** Das Modul sollte das PrestaShop-Übersetzungssystem unterstützen. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Mindestbestellwert nach Kategorie“. Sie können dann die Warnmeldungen anpassen, um spezifischer zu sein, oder sie in andere Sprachen übersetzen.
- **Benutzerdefinierte Theme-Gestaltung:** Wenn die Nachricht angezeigt wird, aber fehl am Platz aussieht, könnte das CSS Ihres Themes die Stile des Moduls überschreiben. Ein Webmaster kann helfen, die Datei `mobc.css` anzupassen oder benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um eine korrekte Anzeige zu gewährleisten.

**F3: Kann ich unterschiedliche Mindestwerte für verschiedene Kundengruppen festlegen (z. B. Einzelhandel vs. Großhandel)?**
A: Die aktuelle Version des Moduls „Mindestbestellwert nach Kategorie“ konzentriert sich auf kategorieweite Mindestwerte, nicht auf kundengruppenspezifische. Wenn Sie diese erweiterte Funktionalität benötigen, müssen Sie möglicherweise separate Kategorien für verschiedene Kundengruppen verwenden (z. B. „Großhandelsprodukte“ vs. „Einzelhandelsprodukte“) und Regeln auf diese unterschiedlichen Kategorien anwenden.

**F4: Was passiert, wenn ein Produkt in mehreren Kategorien ist und nur eine einen Mindestwert hat?**
A: Das Modul berechnet den Gesamtwert der Produkte *innerhalb jeder* Kategorie, die eine Mindestregel hat. Wenn ein Produkt in Kategorie A (kein Mindestwert) und Kategorie B (Mindestwert 50 €) ist, trägt sein Wert zum Gesamtbetrag von Kategorie B bei, wenn es in den Warenkorb gelegt wird. Der Kunde muss den Mindestwert für Kategorie B basierend auf der Summe aller Produkte in seinem Warenkorb erfüllen, die zu Kategorie B gehören.

**F5: Ich habe eine Kategorie gelöscht, aber die Regel dafür wird immer noch in der Modulkonfiguration angezeigt.**
A: Wenn Sie eine Kategorie direkt aus dem PrestaShop-Katalogmenü löschen, könnte die dem Modul zugeordnete Regel verwaist werden. Sie sollten manuell zu **Module > Mindestbestellwert nach Kategorie** gehen und die entsprechende Regel aus der Liste löschen, um Ihre Konfiguration sauber zu halten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Karte)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Mindestbestellwert nach Kategorie“ (`mobc`) folgt einem Standard-PrestaShop-MVC-Muster. Es erweitert hauptsächlich `Module` für seine Kernfunktionalität und `AdminController` für seine Back-Office-Verwaltungsoberfläche. Front-Office-Interaktionen werden über `ModuleFrontController` für AJAX-Anfragen und Template-Rendering abgewickelt. Das Modul verwendet keine benutzerdefinierten `ObjectModel`-Klassen, sondern verlässt sich auf die PrestaShop-Kernentitäten `Category` und `Product` für die Datenabfrage. Die Konfiguration wird in `ps_configuration` und einer benutzerdefinierten Datenbanktabelle für die Kategorie-Wert-Zuordnungen gespeichert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajax.php`
    - **Klassenname:** `MobcAjaxModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Behandelt AJAX-Anfragen vom Front-Office, hauptsächlich um Warenkorbinhalte mit definierten Mindestbestellwerten nach Kategorie zu überprüfen. Es empfängt wahrscheinlich Warenkorbdaten und gibt eine JSON-Antwort zurück, die angibt, ob die Mindestwerte erfüllt sind und, falls nicht, welche Kategorien mangelhaft sind und um wie viel. Dies ist entscheidend für die Echtzeitvalidierung auf der Warenkorbseite ohne vollständige Seitenneuladungen.
  - `controllers/front/index.php`
    - **Klassenname:** `MobcIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder einfacher Einstiegspunkt dienen, aber angesichts der Funktionalität des Moduls ist seine primäre Rolle wahrscheinlich minimal, möglicherweise Weiterleitung oder Bereitstellung einer einfachen Seite, wenn direkt darauf zugegriffen wird. Die Kernlogik des Front-Office wird in `ajax.php` erwartet.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMobc.php`
    - **Klassenname:** `AdminMobcController` (erweitert `ModuleAdminController`)
    - **Tab-Name:** Mindestbestellwert nach Kategorie (oder ähnlich, typischerweise unter „Module“ oder „Katalog“).
    - **Verwaltete Entität:** Verwaltet die benutzerdefinierte `mobc`-Entität, die die Kategorie-Mindestwert-Zuordnungen darstellt.
    - **Verantwortlichkeit:** Bietet die CRUD-Schnittstelle (Create, Read, Update, Delete) zur Verwaltung von Mindestbestellwertregeln. Es listet bestehende Regeln in einem Raster auf, zeigt Formulare zum Hinzufügen/Bearbeiten von Regeln an (Auswahl von Kategorien, Eingabe von Mindestwerten) und verarbeitet Formularübermittlungen. Es interagiert mit der Datenbanktabelle des Moduls für `mobc`-Einträge.
  - `controllers/admin/index.php`
    - **Klassenname:** `AdminMobcIndexController` (erweitert `ModuleAdminController`)
    - **Verantwortlichkeit:** Ähnlich wie das Front-Office `index.php` könnte dies ein Platzhalter oder ein einfacher Weiterleiter sein. Die Haupt-Admin-Logik befindet sich in `AdminMobc.php`.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass die Datenverarbeitung des Moduls für die Kategorie-Wert-Zuordnungen entweder direkt im `AdminMobcController` oder `index.php` (Hauptmoduldatei) unter Verwendung von `Db::getInstance()` erfolgt oder durch die Erweiterung eines generischen `ObjectModel` innerhalb der Hauptmoduldatei selbst, ohne eine dedizierte Klassendatei zu erstellen.

Angesichts dessen, dass der `AdminMobcController` eine „mobc“-Entität verwaltet, ist es sehr wahrscheinlich, dass der `AdminMobcController` seine `$this->object` und `$this->fields_list` direkt definiert oder es eine implizite `ObjectModel`-Definition innerhalb der Hauptdatei `mobc.php` gibt, die der Controller nutzt.

### 4.4 JavaScript-Assets (`views/js/`)

- `mobc/views/js/mobc.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript ist entscheidend für die Echtzeitvalidierung des Warenkorbs. Es wird wahrscheinlich:
    - Event-Listener an Änderungen der Warenkorbmenge, Produktentfernungen oder Seitenladevorgänge auf der Warenkorbseite binden.
    - AJAX-Aufrufe an `controllers/front/ajax.php` auslösen, um aktuelle Warenkorbdaten zu senden.
    - Die JSON-Antwort vom AJAX-Controller empfangen.
    - Das DOM auf der Warenkorbseite dynamisch aktualisieren, um Warnmeldungen anzuzeigen, wenn Mindestwerte nicht erfüllt sind.
    - Die Checkout-Schaltfläche basierend auf dem Validierungsergebnis deaktivieren/aktivieren.
    - Möglicherweise Logik zum Anzeigen von Pop-up-Nachrichten oder zum Hervorheben problematischer Kategorien enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `mobc/views/css/mobc.css`
  - **Umfang:** Front-Office-Kundenstyling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet ist für die visuelle Darstellung der Warnmeldungen auf der Warenkorbseite verantwortlich. Es definiert Stile für:
    - Container, die die Warnmeldungen enthalten (z. B. `div.mobc-warning-message`).
    - Textelemente innerhalb der Warnungen (z. B. `span.mobc-category-name`, `span.mobc-remaining-amount`).
    - Potenziell Styling für die deaktivierte Checkout-Schaltfläche oder andere visuelle Hinweise.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** Entwickler können den generierten HTML-Code auf der Warenkorbseite überprüfen, um die spezifischen Klassennamen (z. B. `.mobc-alert`, `.mobc-error-list`, `.mobc-checkout-blocked`) zu identifizieren und diese in der `custom.css` oder `theme.css` ihres Themes zu überschreiben, um sie an das Branding des Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `mobc/views/templates/front/displayShoppingCart.tpl`
    - **Hook:** Dieses Template wird wahrscheinlich in einem Hook auf der Warenkorbseite gerendert, z. B. `displayShoppingCartFooter` oder `displayShoppingCartExtraContent`.
    - **Visuelle Blockausgabe:** Es gibt die HTML-Struktur für die Warnmeldungen aus, die Kunden über nicht erfüllte Mindestbestellwerte für Kategorien informieren. Dieses Template enthält Platzhalter für Kategorienamen, erforderliche Beträge und den noch benötigten Betrag, die vom JavaScript und AJAX-Controller gefüllt werden.

### 4.7 Datenbankschema & Hooks-Karte

- **Datenbanktabellen**:

  - `ps_mobc_category_value` (oder ähnlich, basierend auf der Entität des `AdminMobcController`): Diese benutzerdefinierte Tabelle speichert die Zuordnung zwischen Kategorie-IDs und ihren jeweiligen Mindestbestellwerten.
    - `id_mobc_category_value` (Primärschlüssel, INT)
    - `id_category` (INT, Fremdschlüssel zu `ps_category.id_category`)
    - `min_value` (DECIMAL, speichert den monetären Mindestbetrag)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Standard-PrestaShop-Konfigurationstabelle. Das Modul könnte seine allgemeinen Einstellungen (falls vorhanden, obwohl keine explizit erkannt wurden) hier speichern, mit dem Präfix `MOBC_`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Zum Einbinden von `mobc.css` und `mobc.js` für die Front-Office-Funktionalität. |
| `displayShoppingCart` | Auf der Warenkorbseite, typischerweise vor oder nach der Warenkorbzusammenfassung. | Zum Rendern von `displayShoppingCart.tpl` zur Anzeige von Warnmeldungen. |
| `actionCartSave` | Nach dem Speichern eines Warenkorbs (z. B. Produkt hinzugefügt/entfernt, Menge geändert). | Zum Auslösen der Modullogik, um die Kategorie-Mindestwerte neu zu bewerten und möglicherweise den Warenkorbstatus oder Sitzungsvariablen zu aktualisieren. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert, ermöglicht Modulen das Hinzufügen von JS/CSS. | Zum Registrieren modulspezifischer JavaScript- und CSS-Dateien für das Front-Office. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ausgabe rendert. | Zum Registrieren modulspezifischer JavaScript- und CSS-Dateien für das Back-Office (z. B. für den `AdminMobcController`). |
| `displayAdminProductsExtra` (oder ähnlich) | Auf der Produktbearbeitungsseite im Back Office. | Potenziell zur Anzeige von Informationen über Kategorie-Mindestwerte, die mit dem aktuellen Produkt zusammenhängen, obwohl dies im Dossier nicht explizit bestätigt wurde. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Mindestbestellwert nach Kategorie“ verweisen wir Sie auf Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
