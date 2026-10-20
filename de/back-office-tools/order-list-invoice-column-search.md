---
title: "Bestellliste Rechnungsspalte & Suche - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bestellliste Rechnungsspalte & Suche“ von MyPresta.eu."
sidebar:
  label: "Bestellliste Rechnungsspalte & Suche - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order List Invoice Column & Search auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/order-list-invoice-column-search.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/order-list-invoice-column-search/)
>
> ---


# Bestellliste Rechnungsspalte & Suche

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Installation hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen „Bestellliste Rechnungsspalte & Suche“. Dieses Modul hat eine sehr einfache und direkte Konfiguration, da seine Kernfunktionalität darin besteht, die bestehende Bestellliste zu erweitern.

Die Konfigurationsseite für „Bestellliste Rechnungsspalte & Suche“ ist unkompliziert. Sie dient hauptsächlich dazu, die Funktionalität des Moduls zu aktivieren oder zu deaktivieren.

- **Einstellungsname:** Rechnungsspalte & Suche aktivieren
- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionen. Wenn aktiviert, fügt das Modul die Spalte „Rechnungsnummer“ zu Ihrer Bestellliste hinzu und integriert die Suchfunktion. Wenn deaktiviert, kehrt Ihre Bestellliste zu ihrem Standard-PrestaShop-Aussehen zurück.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Eine neue Spalte mit dem Titel „Rechnungsnummer“ erscheint in Ihrem Back Office unter **Bestellungen > Bestellungen**. Diese Spalte zeigt die Rechnungsnummer für jede Bestellung an (sofern eine Rechnung generiert wurde). Zusätzlich ermöglicht die Suchleiste auf der Bestellseite nun die Suche nach Rechnungsnummern.
  - *Wenn deaktiviert (NEIN):* Die Spalte „Rechnungsnummer“ wird aus der Bestellliste entfernt, und die Möglichkeit, nach Rechnungsnummern zu suchen, wird deaktiviert. Ihre Bestellliste sieht dann genau so aus wie vor der Installation dieses Moduls.
- **Empfohlener Wert:** **JA**. Um von den Funktionen des Moduls zu profitieren, sollten Sie es aktivieren.
- **Händlerszenario / Beispiel:** Wenn Sie schnell alle Bestellungen zu einer bestimmten Rechnung (z.B. „INV00123“) finden möchten, würden Sie diese Einstellung aktivieren. Dann würden Sie zu **Bestellungen > Bestellungen** navigieren, „INV00123“ in die Suchleiste eingeben, und das System würde die Liste filtern, um nur diese Bestellung anzuzeigen. Wenn Sie es deaktivieren, müssten Sie manuell jede Bestellung anklicken, um ihre Rechnungsnummer zu überprüfen, was sehr zeitaufwendig ist.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Rechnungsspalte & Suche aktivieren | JA | Aktiviert/deaktiviert die Rechnungsspalte und Suchfunktion in der Bestellliste im Back Office. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber ich sehe die Spalte „Rechnungsnummer“ nicht oder die Suche funktioniert nicht.**
A:

1.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie oben rechts auf „Cache leeren“. Manchmal benötigt PrestaShop eine Cache-Aktualisierung, um neue Elemente anzuzeigen.
2.  **Modulstatus überprüfen:** Überprüfen Sie nochmals, ob das Modul auf seiner Konfigurationsseite tatsächlich „Aktiviert“ ist.
3.  **PrestaShop-Version:** Stellen Sie sicher, dass Ihre PrestaShop-Version mit dem Modul kompatibel ist (1.7.x, 8.x, 9.x).
4.  **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder ein Inkognito-Fenster zu verwenden, um browserbezogene Probleme auszuschließen.

**F: Die Rechnungsnummern zeigen „N/A“ an oder sind für einige Bestellungen leer.**
A: Dies bedeutet typischerweise, dass für diese spezifischen Bestellungen in PrestaShop noch keine Rechnung generiert wurde. Das Modul zeigt die Rechnungsnummer nur an, wenn sie in der PrestaShop-Datenbank existiert. Sie müssen die Rechnung für diese Bestellungen manuell über den Standard-PrestaShop-Bestellverwaltungsprozess generieren.

**F: Wird dieses Modul mein Back Office verlangsamen?**
A: Nein, das Modul ist leichtgewichtig und effizient konzipiert. Es erweitert hauptsächlich eine bestehende PrestaShop-Funktion (die Bestellliste), anstatt schwere neue Prozesse hinzuzufügen. Seine Auswirkungen auf die Leistung sollten vernachlässigbar sein.

**F: Kann ich die Position der Spalte „Rechnungsnummer“ anpassen?**
A: Das Modul platziert die Spalte an einer logischen Position innerhalb der Bestellliste. Eine direkte Anpassung der Spaltenreihenfolge ist keine integrierte Funktion dieses Moduls. Für fortgeschrittene Layoutänderungen benötigen Sie in der Regel eine benutzerdefinierte Theme-Entwicklung oder ein anderes spezialisiertes Modul.

**F: Erstellt dieses Modul neue Rechnungen?**
A: Nein, dieses Modul generiert keine Rechnungen. Es zeigt lediglich Rechnungsnummern an und ermöglicht die Suche danach, die bereits durch die Kernfunktionalität von PrestaShop generiert wurden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bestellliste Rechnungsspalte & Suche“ (`olistinv`) ist ein klassisches PrestaShop-Modul, das die Kernfunktionalität erweitert, indem es sich in bestehende Anzeige- und Aktionspunkte im Back Office einklinkt. Es modifiziert hauptsächlich die Listenansicht des `AdminOrders`-Controllers, um eine neue Spalte hinzuzufügen und die Suchfunktionen zu verbessern, ohne neue Datenbanktabellen oder komplexe Front-Office-Interaktionen einzuführen. Seine Einfachheit liegt in der Nutzung des PrestaShop-Hook-Systems und der Überschreibung der Template-Logik, wo dies erforderlich ist.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Logik ist in der Hauptmoduldatei `olistinv/index.php` enthalten und wird über Hooks ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s. Es interagiert direkt mit bestehenden PrestaShop-Kernklassen und Datenbankstrukturen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die Suchfunktion wird durch die Änderung des Verhaltens des bestehenden Suchformulars integriert, was durch das Kern-JS von PrestaShop gehandhabt wird.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Die neue Spalte erbt das Styling der bestehenden PrestaShop Back Office-Tabellen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Es erreicht seine Funktionalität, indem es Inhalte dynamisch über Hooks in bestehende PrestaShop-Templates injiziert, insbesondere durch die Änderung der `AdminOrders`-Listenanzeige.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine neuen Datenbanktabellen. Es liest aus der Tabelle `ps_orders` (insbesondere dem Feld `invoice_number`) und potenziell `ps_order_invoice` für Rechnungsdetails und speichert seine Konfiguration in `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayAdminOrderListHeader` | Wird vor dem Header der Bestelllistentabelle im Back Office gerendert. | Wird verwendet, um den Spaltenkopf „Rechnungsnummer“ zur Bestellliste hinzuzufügen. |
| `displayAdminOrderList` | Wird für jede Zeile (Bestellung) in der Bestelllistentabelle im Back Office gerendert. | Wird verwendet, um die tatsächliche Rechnungsnummer für jede Bestellung in der neu hinzugefügten Spalte anzuzeigen. |
| `actionAdminOrdersListingFieldsModifier` | Modifiziert das Felder-Array, das zum Erstellen der Bestelllistenabfrage und -anzeige verwendet wird. | Wird verwendet, um das Feld `invoice_number` zur Liste der durchsuchbaren und anzeigbaren Felder für den `AdminOrders`-Controller hinzuzufügen. Dies ist entscheidend sowohl für die Anzeige der Spalte als auch für die Aktivierung der Suche. |
| `actionAdminOrdersFilterModifier` | Modifiziert die Filterabfrage für die Bestellliste. | Wird verwendet, um die Suchfunktion zu erweitern, um das Feld `invoice_number` einzuschließen, wenn eine Suchanfrage gesendet wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bestellliste Rechnungsspalte & Suche“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität des Moduls zur Verfügung.
