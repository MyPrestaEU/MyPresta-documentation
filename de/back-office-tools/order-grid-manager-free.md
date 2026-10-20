---
title: "Order Grid Manager Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Order Grid Manager Free von MyPresta.eu."
sidebar:
  label: "Order Grid Manager Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order Grid Manager Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/order-grid-manager-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/order-grid-manager-free/)
>
> ---


# Order Grid Manager Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in jeder modernen Webhosting-Umgebung enthalten sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Moduleinstellungen. Hier finden Sie eine Liste aller Spalten, die in Ihrer PrestaShop Back Office-Bestellliste erscheinen. Jede Spalte hat einen einfachen EIN/AUS-Schalter.

**Bildschirmname & Menüpfad:**

- **Menüpfad:** Back Office > Module > Modul-Manager > Order Grid Manager Free > Konfigurieren

**Verfügbare Einstellungen:**
Sie sehen eine Liste von Kontrollkästchen oder Schaltern, die jeweils einer Spalte in Ihrer Back Office-Bestellliste entsprechen. Die genaue Liste der Spalten kann je nach Ihrer PrestaShop-Version und anderen installierten Modulen leicht variieren, aber gängige Beispiele sind:

- **ID:** Die eindeutige Kennung für jede Bestellung.

  - **Was diese Einstellung bewirkt:** Steuert, ob die Spalte „ID“ in Ihrer Bestellliste sichtbar ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „ID“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „ID“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Oft nützlich für schnelle Referenz und Support).
  - **Händlerszenario / Beispiel:** Wenn Sie häufig Bestellungen anhand ihrer eindeutigen ID referenzieren, wenn Sie mit Kunden oder Ihrem Lager kommunizieren, lassen Sie diese aktiviert. Wenn Sie hauptsächlich andere Kennungen wie Kundennamen oder Referenzen verwenden, können Sie sie ausblenden.
- **Referenz:** Die interne Referenznummer für die Bestellung.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Referenz“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Referenz“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Referenz“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Entscheidend für die Nachverfolgung und interne Kommunikation).
  - **Händlerszenario / Beispiel:** Die meisten Händler verwenden die Bestellreferenz für Lieferscheine, Rechnungen und den Kundenservice. Lassen Sie diese sichtbar, es sei denn, Sie haben einen sehr spezifischen Workflow, der sie nicht verwendet.
- **Neuer Kunde:** Zeigt an, ob die Bestellung von einem neuen Kunden stammt.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Neuer Kunde“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Neuer Kunde“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Neuer Kunde“ wird ausgeblendet.
  - **Empfohlener Wert:** NEIN (Es sei denn, Sie zielen in Ihrem täglichen Workflow speziell auf neue Kundendaten ab).
  - **Händlerszenario / Beispiel:** Wenn Ihr Marketingteam häufig Bestellungen überprüft, um Trends bei der Neukundenakquise zu identifizieren, könnten Sie diese sichtbar lassen. Andernfalls ist sie oft ein guter Kandidat zum Ausblenden für eine sauberere Ansicht.
- **Kunde:** Der Name des Kunden, der die Bestellung aufgegeben hat.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Kunde“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Kunde“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Kunde“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Fast immer unerlässlich zur Bestellidentifikation).
  - **Händlerszenario / Beispiel:** Sie müssen fast immer sehen, wer die Bestellung aufgegeben hat. Lassen Sie diese aktiviert.
- **Gesamt:** Der Gesamtbetrag der Bestellung.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Gesamt“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Gesamt“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Gesamt“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Wichtig für den finanziellen Überblick).
  - **Händlerszenario / Beispiel:** Unerlässlich, um schnell den Wert jeder Bestellung zu sehen. Lassen Sie diese aktiviert.
- **Zahlung:** Die für die Bestellung verwendete Zahlungsmethode.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Zahlung“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Zahlung“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Zahlung“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Nützlich für den Zahlungsabgleich).
  - **Händlerszenario / Beispiel:** Wenn Sie schnell sehen müssen, ob eine Bestellung per Kreditkarte, PayPal oder Banküberweisung bezahlt wurde, lassen Sie diese aktiviert.
- **Status:** Der aktuelle Status der Bestellung (z. B. Zahlung akzeptiert, Versandt, Geliefert).

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Status“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Status“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Status“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Entscheidend für die Verfolgung des Bestellfortschritts).
  - **Händlerszenario / Beispiel:** Absolut unerlässlich für die Verwaltung der Bestellabwicklung. Lassen Sie diese aktiviert.
- **Datum:** Datum und Uhrzeit der Bestellung.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Datum“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Datum“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Datum“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Wichtig für die chronologische Reihenfolge und das Alter).
  - **Händlerszenario / Beispiel:** Nützlich zum Sortieren von Bestellungen nach dem Zeitpunkt ihrer Aufgabe oder zum Identifizieren älterer Bestellungen, die Aufmerksamkeit erfordern. Lassen Sie diese aktiviert.
- **Rechnung:** Link zum Anzeigen/Herunterladen der Rechnung.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Rechnung“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Rechnung“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Rechnung“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Praktisch für den schnellen Zugriff auf Rechnungen).
  - **Händlerszenario / Beispiel:** Wenn Ihr Team häufig Rechnungen direkt aus der Bestellliste herunterladen oder anzeigen muss, lassen Sie diese aktiviert.
- **Lieferung:** Link zum Anzeigen/Herunterladen des Lieferscheins.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Lieferung“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Lieferung“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Lieferung“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Praktisch für den schnellen Zugriff auf Lieferscheine).
  - **Händlerszenario / Beispiel:** Wenn Ihr Lager- oder Versandteam Lieferscheine verwendet, bietet das Sichtbarhalten einen schnellen Zugriff.
- **Aktionen:** Schaltflächen zum Anzeigen, Bearbeiten oder Löschen der Bestellung.

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Spalte „Aktionen“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Spalte „Aktionen“ wird angezeigt.
    - *Wenn deaktiviert:* Die Spalte „Aktionen“ wird ausgeblendet.
  - **Empfohlener Wert:** JA (Unerlässlich für die Verwaltung einzelner Bestellungen).
  - **Händlerszenario / Beispiel:** Sie müssen fast immer eine Bestellung anzeigen oder bearbeiten. Lassen Sie diese aktiviert.

**Speichern Ihrer Änderungen:**
Nachdem Sie Ihre Auswahl getroffen haben, denken Sie daran, auf die Schaltfläche **„Speichern“** (normalerweise am unteren Rand der Konfigurationsseite) zu klicken, um Ihre Änderungen zu übernehmen. Navigieren Sie nach dem Speichern zu **Bestellungen > Bestellungen** in Ihrem Back Office, um das aktualisierte Spaltenlayout zu sehen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | ID | JA | Zeigt/verbirgt die eindeutige Bestell-ID. |
| Modulkonfiguration | Referenz | JA | Zeigt/verbirgt die interne Bestellreferenz. |
| Modulkonfiguration | Neuer Kunde | NEIN | Zeigt/verbirgt den Indikator für neue Kunden. |
| Modulkonfiguration | Kunde | JA | Zeigt/verbirgt den Namen des Kunden. |
| Modulkonfiguration | Gesamt | JA | Zeigt/verbirgt den Gesamtbestellbetrag. |
| Modulkonfiguration | Zahlung | JA | Zeigt/verbirgt die verwendete Zahlungsmethode. |
| Modulkonfiguration | Status | JA | Zeigt/verbirgt den aktuellen Bestellstatus. |
| Modulkonfiguration | Datum | JA | Zeigt/verbirgt das Bestelldatum. |
| Modulkonfiguration | Rechnung | JA | Zeigt/verbirgt den Link zum Herunterladen der Rechnung. |
| Modulkonfiguration | Lieferung | JA | Zeigt/verbirgt den Link zum Herunterladen des Lieferscheins. |
| Modulkonfiguration | Aktionen | JA | Zeigt/verbirgt die Aktionsschaltflächen (anzeigen, bearbeiten, löschen). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber das Bestellraster hat sich nicht geändert.**
A: Nach dem Speichern Ihrer Änderungen in der Modulkonfiguration müssen Sie möglicherweise Ihren PrestaShop-Cache leeren. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Versuchen Sie auch, Ihre Browserseite zu aktualisieren (Strg+F5 oder Cmd+R), um sicherzustellen, dass Sie keine zwischengespeicherte Version des Back Office sehen.

**F: Kann ich unterschiedliche Spaltenansichten für verschiedene Admin-Benutzer haben?**
A: Das Modul „Order Grid Manager Free“ wendet eine einzige, universelle Einstellung für alle Administratoren an. Es unterstützt keine individuellen Benutzereinstellungen für die Spaltensichtbarkeit. Wenn Sie diese erweiterte Funktionalität benötigen, müssen Sie möglicherweise nach einem Premium-Modul oder einer kundenspezifischen Entwicklung suchen.

**F: Beeinträchtigt dieses Modul die Leistung meines Shops?**
A: Nein, dieses Modul hat einen vernachlässigbaren Einfluss auf die Leistung. Es ändert nur, welche Spalten in der Back Office-Bestellliste angezeigt werden, was eine clientseitige (Browser-)Rendering-Anpassung basierend auf einer einfachen Konfiguration ist. Es ändert keine Datenbankabfragen oder Ladezeiten des Front-Office.

**F: Was passiert, wenn ich versehentlich eine Spalte ausblende, die ich benötige?**
A: Kein Problem! Gehen Sie einfach zurück zu **Module > Modul-Manager > Order Grid Manager Free > Konfigurieren**, aktivieren Sie die gewünschte Spalte erneut, indem Sie das Kontrollkästchen aktivieren, und speichern Sie Ihre Änderungen. Leeren Sie dann Ihren Cache und aktualisieren Sie Ihren Browser.

**F: Unterstützt dieses Modul mehrsprachige Übersetzungen für Spaltennamen?**
A: Das Modul selbst führt keine neuen übersetzbaren Zeichenfolgen für Spaltennamen ein. Es steuert lediglich die Sichtbarkeit bestehender PrestaShop-Spaltennamen, die bereits vom Kernübersetzungssystem von PrestaShop verwaltet werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „Order Grid Manager Free“ verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht

Das Modul `Order Grid Manager Free` ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, die Anzeige der `AdminOrders`-Liste zu modifizieren. Es nutzt das PrestaShop-Konfigurationssystem, um Benutzereinstellungen für die Spaltensichtbarkeit zu speichern und injiziert JavaScript, um Spalten basierend auf diesen Einstellungen dynamisch aus-/einzublenden. Es folgt einer grundlegenden PrestaShop-Modulstruktur, wobei seine Kernlogik in der Hauptmoduldatei liegt.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration und Logik wird innerhalb der Hauptmodulklasse und ihrer `getContent()`-Methode gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Es arbeitet direkt mit der PrestaShop-Kernkonfiguration und bestehenden Back Office-Strukturen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine dedizierten JavaScript-Dateien in `views/js/`. Die Logik zum Aus-/Einblenden von Spalten wird wahrscheinlich direkt über einen Hook oder innerhalb des `getContent()`-Methoden-Templates in das Back Office injiziert, unter Verwendung von Inline-JavaScript oder einer einfachen CSS-Injektion. Angesichts der Einfachheit des Moduls und der Bezeichnung „Free“ ist es sehr wahrscheinlich, dass das Ausblenden von Spalten durch Hinzufügen von CSS-Regeln `display: none;` oder durch direkte Manipulation des DOM nach dem Laden der Seite, basierend auf der gespeicherten Konfiguration, erreicht wird.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine dedizierten CSS-Dateien in `views/css/`. Ähnlich wie bei JavaScript wird jegliches Styling (hauptsächlich `display: none;` für Spalten) wahrscheinlich inline injiziert oder dynamisch basierend auf der Konfiguration generiert.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`myordergridfree/views/templates/admin/advert.tpl`**:
  - **Umfang:** Back-Office (Admin-Konfigurationsseite).
  - **Zweck:** Dieses Template wird wahrscheinlich verwendet, um eine Werbung oder Werbebotschaft innerhalb der Konfigurationsseite des Moduls im Back Office anzuzeigen. Es ist eine gängige Praxis für kostenlose Module, solche Elemente einzuschließen. Es steuert nicht direkt die Funktionalität des Bestellrasters, ist aber Teil der `getContent()`-Ausgabe des Moduls.

Das eigentliche Konfigurationsformular für die Spaltensichtbarkeit wird wahrscheinlich direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei gerendert, möglicherweise unter Verwendung von PrestaShops `HelperForm` oder benutzerdefiniertem HTML, und dann wird die `advert.tpl` für Werbeinhalte eingebunden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Standard-PrestaShop-Tabelle `ps_configuration`. Jede Einstellung (z. B. `MYORDERGRIDFREE_HIDE_ID_COLUMN`) entspricht einer Zeile in dieser Tabelle und speichert einen booleschen Wert (0 oder 1) für die Sichtbarkeit.
- **Registrierte Hooks-Tabelle**:
  Die primäre Funktionalität dieses Moduls beruht auf der Änderung der Back Office-Anzeige. Angesichts der Einfachheit der „Free“-Version verwendet es wahrscheinlich einen oder mehrere der folgenden Ansätze:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich der Back Office-Seiten ausgeführt. | Wahrscheinlichster Hook zum Injizieren von Inline-CSS oder JavaScript, um Spalten auf der `AdminOrders`-Seite auszublenden. Dies ermöglicht es dem Modul, `display: none;` auf bestimmte `<th>`- und `<td>`-Elemente basierend auf der gespeicherten Konfiguration anzuwenden. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Könnte verwendet werden, um eine kleine JS-Datei oder ein Inline-Skript zu registrieren, das speziell auf dem `AdminOrders`-Controller ausgeführt wird, um das DOM zu manipulieren. |
| `displayAdminOrderListBefore` / `displayAdminOrderListAfter` | Vor/Nach dem Rendern der Bestelllistentabelle. | Weniger wahrscheinlich für dieses Modul, da es die Liste selbst modifiziert, nicht nur Inhalte darum herum hinzufügt. |

Die `install()`-Methode des Moduls würde diese Hooks registrieren, und die `hookDisplayBackOfficeHeader()`- (oder ähnliche) Methode würde die Logik enthalten, um die gespeicherte Konfiguration abzurufen und das notwendige CSS/JS auszugeben, um die ausgewählten Spalten auszublenden, wenn die `AdminOrders`-Seite geladen wird.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Order Grid Manager Free“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
