---
title: "Mindestbestellwert nach Kundengruppe – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mindestbestellwert nach Kundengruppe“ von MyPresta.eu."
sidebar:
  label: "Mindestbestellwert nach Kundengruppe – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Minimum order value by customer group auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/minimum-order-value-by-customer-group.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/minimum-order-value-by-customer-group/)
>
> ---


# Mindestbestellwert nach Kundengruppe

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Mindestbestellwerte für jede Kundengruppe definieren.

#### Allgemeine Einstellungen

- **Spezifische Kundengruppen von der Mindestbestellwertregel ausschließen:**

  - **Was diese Einstellung bewirkt:** Hiermit können Sie Kundengruppen auswählen, die *keinem* Mindestbestellwert unterliegen, selbst wenn Sie einen für sie festgelegt haben. Sie können immer zur Kasse gehen, unabhängig von ihrem Warenkorbwert.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Gruppen ausgewählt):* Kunden, die zu den ausgewählten Gruppen gehören, umgehen alle Mindestbestellwertprüfungen.
    - *Wenn deaktiviert (keine Gruppen ausgewählt):* Alle Kundengruppen unterliegen den von Ihnen definierten Mindestbestellwerten.
  - **Empfohlener Wert:** Hängt von Ihrem Geschäftsmodell ab. Wenn Sie VIPs oder bestimmte B2C-Kunden haben, die Sie ausnehmen möchten, wählen Sie diese hier aus. Andernfalls lassen Sie das Feld leer.
  - **Händlerszenario / Beispiel:** Sie haben eine Gruppe „VIP-Kunden“, die immer zur Kasse gehen können sollen, auch wenn ihre Bestellung klein ist. Wählen Sie hier „VIP-Kunden“ aus.
- **Steuer in Mindestbestellwert einbeziehen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob der von Ihnen festgelegte Mindestbestellwert den für die Produkte im Warenkorb berechneten Steuerbetrag enthalten oder ausschließen soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul prüft den Warenkorbwert *einschließlich* Steuern gegen Ihr definiertes Minimum.
    - *Wenn deaktiviert (NEIN):* Das Modul prüft den Warenkorbwert *ausschließlich* Steuern gegen Ihr definiertes Minimum.
  - **Empfohlener Wert:** „JA“ für die meisten B2C-Shops, da Kunden in der Regel den Gesamtpreis inklusive Steuern sehen und bezahlen. „NEIN“ könnte für B2B-Shops bevorzugt werden, wo Preise oft exklusive Steuern angegeben werden.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Minimum von 100 € festlegen und dies aktiviert ist, würde ein Warenkorbwert von 90 € (exkl. Steuern) + 10 € (Steuern) = 100 € durchgehen. Wenn deaktiviert, würde derselbe Warenkorb fehlschlagen, da 90 € weniger als 100 € sind.
- **Versandkosten in Mindestbestellwert einbeziehen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob die Versandkosten für die Bestellung zum Warenkorbwert hinzugefügt werden sollen, bevor dieser mit dem Mindestbestellwert verglichen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul prüft (Warenkorbwert + Versandkosten) gegen Ihr definiertes Minimum.
    - *Wenn deaktiviert (NEIN):* Das Modul prüft nur den Warenkorbwert (Produkte) gegen Ihr definiertes Minimum.
  - **Empfohlener Wert:** In den meisten Fällen „NEIN“, da Mindestwerte in der Regel den Produktwert betreffen. Wenn Ihre Versandkosten jedoch sehr hoch sind und Sie einen bestimmten Gesamttransaktionswert sicherstellen möchten, könnten Sie dies aktivieren.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden Produkte im Wert von mindestens 50 € kaufen. Wenn dies „NEIN“ ist, geht ein Warenkorb mit Produkten im Wert von 50 € durch. Wenn dies „JA“ ist und der Versand 10 € beträgt, müsste der Kunde Produkte im Wert von 50 € + 10 € Versand = 60 € insgesamt haben, um durchzugehen, was bedeutet, dass er Produkte im Wert von 60 € bräuchte, um das Minimum von 50 € zu erreichen. Diese Einstellung ist normalerweise „NEIN“, um Verwirrung zu vermeiden.
- **Mindestbestellwert nur für die erste Bestellung anwenden:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, gelten die Mindestbestellwertregeln nur für die allererste Bestellung eines Kunden in Ihrem Shop. Nachfolgende Bestellungen unterliegen nicht den Mindestwerten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nur neue Kunden (die noch keine Bestellung aufgegeben haben) unterliegen den Mindestbestellwertbeschränkungen.
    - *Wenn deaktiviert (NEIN):* Alle Bestellungen, unabhängig davon, ob es sich um die erste oder zehnte Bestellung eines Kunden handelt, werden auf den Mindestbestellwert geprüft.
  - **Empfohlener Wert:** „NEIN“ für die meisten Szenarien, in denen Sie konsistente Mindestwerte wünschen. „JA“ könnte nützlich sein, um anfängliche größere Einkäufe von Neukunden zu fördern und dann die Regeln für wiederkehrende Geschäfte zu lockern.
  - **Händlerszenario / Beispiel:** Sie möchten, dass neue B2B-Kunden eine erhebliche erste Bestellung von 500 € aufgeben, um ihr Konto einzurichten, aber danach können sie beliebige Beträge bestellen. Aktivieren Sie dies und legen Sie den Mindestwert von 500 € für Ihre B2B-Gruppe fest.

#### Mindestbestellwerte nach Kundengruppe

Unter den allgemeinen Einstellungen finden Sie eine Liste aller Ihrer Kundengruppen. Für jede Gruppe können Sie einen Mindestbestellwert definieren.

- **Name der Kundengruppe (z. B. „Besucher“, „Gast“, „Kunde“, „Großhandel“):**
  - **Was diese Einstellung bewirkt:** Hier geben Sie den spezifischen Mindestbestellwert ein, der für Kunden dieser bestimmten Gruppe erforderlich ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert eingegeben wird (z. B. 50.00):* Kunden in dieser Gruppe müssen einen Warenkorbwert haben, der diesem Wert entspricht oder größer ist, um zur Kasse zu gehen.
    - *Wenn leer gelassen oder auf 0.00 gesetzt:* Es gibt keinen Mindestbestellwert für diese Kundengruppe. Sie können mit jedem Warenkorbwert zur Kasse gehen.
  - **Empfohlener Wert:** Legen Sie einen Wert fest, der für jede Gruppe geschäftlich sinnvoll ist. Lassen Sie ihn für Gruppen wie „Besucher“ oder „Gast“ leer, es sei denn, Sie möchten sie ausdrücklich vom Bestellen abhalten.
  - **Händlerszenario / Beispiel:**
    - Für die Gruppe „Kunde“: Auf `25.00` setzen, um etwas größere Einzelhandelskäufe zu fördern.
    - Für die Gruppe „Großhandel“: Auf `200.00` setzen, um die Rentabilität von B2B-Bestellungen sicherzustellen.
    - Für die Gruppe „Gast“: Leer lassen (`0.00`), um schnelle Einkäufe ohne Registrierung zu ermöglichen.

#### Überlegungen zu Multi-Store & Multi-Währung

- **Multi-Store:** Wenn Sie mehrere Shops aktiviert haben, sehen Sie oben auf der Konfigurationsseite (normalerweise neben der Schaltfläche „Speichern“) ein Dropdown-Menü, mit dem Sie auswählen können, welchen Shop Sie konfigurieren. Die Mindestbestellwerte können für jeden Shop unabhängig voneinander festgelegt werden.
- **Multi-Währung:** Die von Ihnen eingegebenen Mindestbestellwerte sind immer in der *Standardwährung* Ihres PrestaShop-Shops. Das Modul wandelt diese Werte beim Überprüfen des Warenkorbwertes automatisch zum aktuellen Wechselkurs in die vom Kunden gewählte Währung um.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Spezifische Kundengruppen ausschließen | Leer | Wählen Sie Gruppen aus, die die Mindestbestellregeln umgehen sollen. |
| Modulkonfiguration | Steuer in Mindestbestellwert einbeziehen | JA | Legt fest, ob die Steuer Teil des Mindestgesamtbetrags ist. |
| Modulkonfiguration | Versandkosten in Mindestbestellwert einbeziehen | NEIN | Legt fest, ob der Versand Teil des Mindestgesamtbetrags ist. |
| Modulkonfiguration | Mindestbestellwert nur für die erste Bestellung anwenden | NEIN | Wendet Mindestwerte nur auf den ersten Einkauf eines Kunden an. |
| Modulkonfiguration | Mindestbestellwert für [Name der Kundengruppe] | 0.00 (leer) | Legen Sie den erforderlichen Warenkorbwert für jede Kundengruppe fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden sehen die Mindestbestellwert-Meldung, obwohl ihr Warenkorbwert korrekt zu sein scheint. Was ist falsch?**
A:

1. **Steuer-/Versandeinstellungen prüfen:** Überprüfen Sie nochmals, ob „Steuer in Mindestbestellwert einbeziehen“ oder „Versandkosten in Mindestbestellwert einbeziehen“ aktiviert sind. Der angezeigte Warenkorbwert könnte sich von dem Wert unterscheiden, gegen den das Modul prüft.
2. **Währungsumrechnung:** Wenn Sie in mehreren Währungen arbeiten, stellen Sie sicher, dass die Wechselkurse aktuell sind. Das Modul wandelt Ihre Standardwährungs-Mindestwerte in die vom Kunden gewählte Währung um.
3. **Kundengruppenzuordnung:** Überprüfen Sie, ob der Kunde der beabsichtigten Kundengruppe korrekt zugeordnet ist und ob der Mindestwert für diese Gruppe wie erwartet festgelegt ist.
4. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal können alte zwischengespeicherte Daten Probleme verursachen.

**F: Ich habe einen Mindestwert festgelegt, aber eine bestimmte Kundengruppe kann immer noch mit beliebigem Betrag zur Kasse gehen. Warum?**
A: Überprüfen Sie die Einstellung „Spezifische Kundengruppen von der Mindestbestellwertregel ausschließen“ auf der Modulkonfigurationsseite. Wenn diese Kundengruppe dort ausgewählt ist, umgeht sie alle Mindestbestellwertprüfungen. Entfernen Sie sie aus dieser Ausschlussliste, wenn der Mindestwert angewendet werden soll.

**F: Die Modulnachricht wird nicht angezeigt oder sieht in meinem benutzerdefinierten Theme seltsam aus.**
A:

1. **Theme-Kompatibilität:** Benutzerdefinierte Themes können Standard-PrestaShop-Vorlagen oder CSS überschreiben, was sich möglicherweise auf die Anzeige von Modulnachrichten auswirkt.
2. **CSS-Konflikte:** Ein anderes Modul oder das CSS Ihres Themes könnte mit dem Styling des Moduls in Konflikt stehen.
3. **Smarty-Cache:** Leeren Sie Ihren Smarty-Cache (Erweiterte Einstellungen > Leistung > Cache leeren), um sicherzustellen, dass die neuesten Vorlagendateien verwendet werden.
   Bei visuellen Problemen müssen Sie möglicherweise einen Webentwickler konsultieren, um das CSS und die Vorlagendateien Ihres Themes zu überprüfen.

**F: Kann ich unterschiedliche Mindestwerte für verschiedene Produkte festlegen?**
A: Nein, dieses Modul legt einen Mindestwert für den *gesamten Warenkorbwert* basierend auf der Kundengruppe fest, nicht für einzelne Produkte. Wenn Sie produktspezifische Mindestwerte benötigen, bräuchten Sie eine andere Art von Modul.

**F: Wie geht dieses Modul mit Multi-Store-Setups um?**
A: Das Modul ist Multi-Store-freundlich. Verwenden Sie beim Konfigurieren den „Shop-Kontext“-Selektor oben im PrestaShop-Backoffice (normalerweise neben der Schaltfläche „Speichern“), um zwischen Ihren Shops zu wechseln. Sie können dann für jede Kundengruppe pro Shop eindeutige Mindestbestellwerte festlegen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Mindestbestellwert nach Kundengruppe“ (`cgma`) ist nach der Standard-Modularchitektur von PrestaShop aufgebaut. Es verwendet hauptsächlich Hooks, um seine Logik in den Front-Office-Warenkorb- und Checkout-Prozess zu integrieren. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Die Front-Office-Interaktion wird von einem dedizierten AJAX-Controller für die Echtzeit-Warenkorbvalidierung übernommen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `cgma/controllers/front/ajax.php`
    - **Klassenname:** `CgmaAjaxModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Dieser Controller verarbeitet AJAX-Anfragen vom Front-Office, hauptsächlich zur Echtzeit-Validierung des Warenkorbwertes gegen den Mindestbestellwert der Kundengruppe. Er gibt wahrscheinlich eine JSON-Antwort zurück, die angibt, ob der Warenkorb die Anforderungen erfüllt und möglicherweise eine Meldung zur Anzeige für den Benutzer. Dies ist entscheidend für dynamische Updates ohne vollständige Seitenneuladungen.
  - `cgma/controllers/front/index.php`
    - **Klassenname:** `CgmaIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Dies ist ein Platzhalter- oder Fallback-Controller. In vielen Modulen fallen Anfragen, wenn eine bestimmte Aktion nicht definiert ist, möglicherweise an einen `index`-Controller. Er könnte auch für einfache Weiterleitungen verwendet werden oder um sicherzustellen, dass eine gültige Modulroute existiert, obwohl seine primäre Funktion in diesem Modul wahrscheinlich minimal im Vergleich zu `ajax.php` ist.
- **Back-Office-Admin-Controller**:

  - Keine explizit im Inventar definiert. Die gesamte Back-Office-Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen explizit im Inventar aufgeführt. Das Modul stützt sich wahrscheinlich auf die PrestaShop-Kernklassen `Customer`, `Group`, `Cart` und `Configuration` für seine Funktionalität. Konfigurationswerte werden direkt in der Tabelle `ps_configuration` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- `cgma/views/js/cgma.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Dieses Skript ist für die clientseitige Interaktion und Validierung verantwortlich. Es lauscht wahrscheinlich auf Änderungen im Warenkorb (z. B. Mengenaktualisierungen, Produktentfernungen) oder Versuche, zur Kasse zu gehen. Es würde dann AJAX-Aufrufe an `cgma/controllers/front/ajax.php` auslösen, um den Warenkorbwert gegen den Mindestbestellwert zu validieren. Nach Erhalt einer Antwort würde es die Warenkorbzusammenfassung oder die Checkout-Schaltflächen dynamisch aktualisieren, Meldungen an den Benutzer anzeigen, wenn das Minimum nicht erreicht wird, und möglicherweise die Schaltfläche „Zur Kasse gehen“ deaktivieren. Es könnte auch die Anzeige der Mindestbestellwert-Meldung an verschiedenen Front-Office-Stellen handhaben.

### 4.5 CSS-Stylesheets (`views/css/`)

- `cgma/css.css`

  - **Geltungsbereich:** Wahrscheinlich Front-Office.
  - **Details:** Dieses Stylesheet bietet das grundlegende Styling für die Front-Office-Meldungen oder -Elemente des Moduls, wie z. B. die Warnmeldung, die angezeigt wird, wenn der Mindestbestellwert nicht erreicht wird.
  - **Wichtige CSS-Klassenselektoren:** Entwickler sollten diese Datei auf Klassen wie `.cgma-warning-message`, `.cgma-disabled-button` oder ähnliche überprüfen, die in einem benutzerdefinierten Theme überschrieben werden können.
- `cgma/views/css/cgma.css`

  - **Geltungsbereich:** Wahrscheinlich Front-Office.
  - **Details:** Ähnlich wie `cgma/css.css` bietet diese Datei zusätzliche oder spezifischere Styling für die Front-Office-Komponenten des Moduls. Sie könnte responsive Anpassungen oder spezifische Layoutregeln enthalten.
  - **Wichtige CSS-Klassenselektoren:** Überprüfen Sie auf Selektoren, die sich auf die Warenkorbzusammenfassung, Checkout-Schaltflächen oder spezifische Nachrichtencontainer beziehen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:

  - Keine explizit im Inventar aufgeführt, aber die `displayShoppingCart`-Hook-Implementierung des Moduls würde wahrscheinlich eine Vorlage rendern. Es ist möglich, dass `displayShoppingCart.tpl` direkt in `views/templates/front/` liegt und vom Hook verwendet wird.
- **Admin-Vorlagen (`views/templates/admin/`)**:

  - `cgma/admin.tpl`
    - **Geltungsbereich:** Back-Office-Konfiguration.
    - **Details:** Diese Vorlage wird von der `getContent()`-Methode der Hauptmodulklasse (`cgma.php`) gerendert. Sie enthält die HTML-Struktur für das Konfigurationsformular des Moduls, einschließlich Eingabefeldern für allgemeine Einstellungen (Gruppen ausschließen, Steuer-/Versandeinbeziehung, nur erste Bestellung) und dynamische Felder zum Festlegen von Mindestbestellwerten für jede Kundengruppe.
- **Front-Office-Vorlagen (`views/templates/front/`)**:

  - `cgma/views/templates/front/displayShoppingCart.tpl`
    - **Geltungsbereich:** Front-Office, speziell die Warenkorbseite.
    - **Details:** Diese Vorlage wird wahrscheinlich gerendert, wenn das Modul in `displayShoppingCart` eingreift. Sie zeigt dem Kunden die Warnmeldung an, wenn sein Warenkorbwert den Mindestbestellwert für seine Gruppe nicht erreicht. Sie könnte auch Logik enthalten, um die Schaltfläche „Zur Kasse gehen“ zu deaktivieren oder Anweisungen zum Erreichen des Minimums zu geben.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `CGMA_EXCV`, `CGMA_TAX`, `CGMA_FREE`, `CGMA_FIRST_ORDER` und `CGMA_[GROUP_ID]_[CURRENCY_ID]` für die Mindestwerte pro Gruppe und Währung gespeichert. `PS_CURRENCY_DEFAULT` wird ebenfalls referenziert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `stepBeforePaymentOPC` | Vor dem Zahlungsschritt im One-Page-Checkout. | Verhindert, dass Kunden zur Zahlung übergehen, wenn der Mindestbestellwert nicht erreicht wird. |
| `displayPaymentTop` | Oben im Bereich der Zahlungsoptionen während des Checkouts. | Zeigt eine Warnmeldung an, wenn der Mindestbestellwert nicht erreicht wird. |
| `displaystepBeforePaymentOPC` | Ähnlich wie `stepBeforePaymentOPC`, oft zur Anzeige von Inhalten oder zusätzlichen Prüfungen verwendet. | Stellt sicher, dass der Mindestbestellwert vor der Zahlung erreicht wird, möglicherweise mit einer Meldung. |
| `displayShoppingCart` | Auf der Warenkorb-Übersichtsseite. | Validiert den Warenkorbwert und zeigt eine Warnmeldung an, wenn das Minimum nicht erreicht wird, möglicherweise mit Deaktivierung der Checkout-Schaltflächen. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt notwendige CSS (`cgma.css`) und JavaScript (`cgma.js`) Dateien für die Front-Office-Funktionalität und das Styling ein. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um die neuesten Versionen des Moduls „Mindestbestellwert nach Kundengruppe“ zu erhalten, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
