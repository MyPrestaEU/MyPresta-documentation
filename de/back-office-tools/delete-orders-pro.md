---
title: "Delete Orders Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Delete Orders Pro von MyPresta.eu."
sidebar:
  label: "Delete Orders Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Delete Orders Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/delete-orders-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/delete-orders-pro/)
>
> ---


# Delete Orders Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls „Delete Orders Pro“. Dieser Bildschirm behandelt hauptsächlich allgemeine Moduleinstellungen und Update-Prüfungen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise Standardeinstellungen für MyPresta.eu-Module, die sich auf Update-Benachrichtigungen und interne Nachverfolgung beziehen.
- **Auswirkungen der Änderung dieser Einstellung:**
  - `mypresta_updates`, `update_`, `updatev_`: Diese Einstellungen steuern, ob das Modul nach Updates von MyPresta.eu sucht und Benachrichtigungen in Ihrem Back Office anzeigt. Wenn sie aktiviert sind, bleiben Sie über neue Versionen und Funktionen informiert. Wenn sie deaktiviert sind, werden diese Benachrichtigungen unterdrückt.
  - `DELETEORDERS_LAST_TAB`: Dies ist eine interne Einstellung, die den zuletzt besuchten Tab oder die Ansicht innerhalb der dedizierten Verwaltungsoberfläche des Moduls verfolgt. Sie hilft dem Modul, Ihre letzte Position zur Bequemlichkeit zu speichern.
- **Empfohlener Wert:**
  - Für Update-bezogene Einstellungen: **JA** (oder Aktiviert). Es wird immer empfohlen, die Update-Prüfungen aktiviert zu lassen, um sicherzustellen, dass Sie die neueste, sicherste und funktionsreichste Version des Moduls verwenden.
  - `DELETEORDERS_LAST_TAB`: Lassen Sie diese Einstellung unverändert; sie wird automatisch vom Modul verwaltet.
- **Händlerszenario / Beispiel:** Wenn Sie die Update-Prüfungen aktiviert lassen, werden Sie direkt in Ihrem PrestaShop Back Office benachrichtigt, wenn eine neue Version von „Delete Orders Pro“ veröffentlicht wird. So können Sie einfach aktualisieren und von Verbesserungen oder Fehlerbehebungen profitieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Bestellungen löschen Tab (Back Office > Bestellungen > Delete Orders Pro)

Dies ist die primäre Schnittstelle, über die Sie Bestellungen verwalten und löschen.

- **Bildschirmname & Menüposition:** Sie können auf diesen Bildschirm zugreifen, indem Sie im PrestaShop Back Office-Menü zu **Bestellungen > Delete Orders Pro** navigieren.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Raster- oder Listenansicht Ihrer Bestellungen, ähnlich der Standard-PrestaShop-Bestellliste, jedoch mit zusätzlichen Funktionen speziell für das Löschen.
  - **Filteroptionen:** Sie werden wahrscheinlich Filter finden, um die Bestellungen, die Sie löschen möchten, einzugrenzen (z.B. nach Bestellstatus, Datumsbereich, Kunde usw.). Dies ist entscheidend, um bestimmte Arten von Bestellungen sicher anzusprechen.
  - **Auswahl-Kontrollkästchen:** Jede Bestellung in der Liste hat ein Kontrollkästchen, mit dem Sie einzelne Bestellungen zum Löschen auswählen können.
  - **Massenaktionen:** Es sollte eine Option geben, mehrere Bestellungen auszuwählen (z.B. „Alle auswählen“ oder „Bestellungen mit Status X auswählen“) und dann eine Massenlöschung durchzuführen.
  - **Löschen-Schaltfläche:** Eine prominente Schaltfläche (z.B. „Ausgewählte Bestellungen löschen“ oder „Bestellungen löschen“) initiiert den Löschvorgang.
- **Auswirkungen von Änderungen:**
  - Wenn Sie Bestellungen auswählen und auf die Löschen-Schaltfläche klicken, entfernt das Modul diese Bestellungen und alle zugehörigen Daten (Bestelldetails, bestellte Produkte, kundenbezogene Nachrichten zur Bestellung, Rechnungen usw.) dauerhaft aus Ihrer PrestaShop-Datenbank.
  - Diese Aktion ist irreversibel.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Überprüfen Sie regelmäßig Ihre Bestellungen:** Identifizieren Sie, welche Bestellstatus typischerweise „unerwünschte“ Bestellungen darstellen (z.B. „Storniert“, „Zahlungsfehler“, „Im Rückstand“, wenn nicht erfüllt, oder benutzerdefinierte Status für Testbestellungen).
  2. **Greifen Sie auf „Delete Orders Pro“ zu:** Gehen Sie zu **Bestellungen > Delete Orders Pro**.
  3. **Bestellungen filtern:** Verwenden Sie die verfügbaren Filter, um nur die Bestellungen anzuzeigen, die Sie löschen möchten (z.B. nach Status „Storniert“ und einem Datumsbereich, der älter als 3 Monate ist).
  4. **Bestellungen sorgfältig auswählen:** Überprüfen Sie die gefilterten Bestellungen noch einmal und wählen Sie sie mit den Kontrollkästchen aus.
  5. **Löschung initiieren:** Klicken Sie auf die Schaltfläche „Ausgewählte Bestellungen löschen“. Bestätigen Sie die Aktion, wenn Sie dazu aufgefordert werden.
  6. **Backups durchführen:** Stellen Sie vor jeder größeren Löschung immer sicher, dass Sie ein aktuelles Datenbank-Backup haben.

#### 2.2.2 Index Controller (deleteorderspro/controllers/admin/index.php)

Diese Datei dient typischerweise als Routing- oder Fallback-Controller innerhalb des Admin-Bereichs des Moduls. Im Kontext von „Delete Orders Pro“ stellt sie wahrscheinlich sicher, dass, wenn ein Benutzer zum Basis-Admin-Pfad des Moduls navigiert, ohne eine bestimmte Aktion oder einen Unter-Controller anzugeben, er zur Hauptschnittstelle `deleteorderstab` weitergeleitet wird.

- **Bildschirmname & Menüposition:** Kein direkter Bildschirm, sondern Teil der internen Navigation des Moduls.
- **Verfügbare Aktionen & Einstellungen:** Keine direkt vom Benutzer konfigurierbaren Einstellungen. Ihr Zweck ist die Verwaltung der internen Weiterleitung.
- **Auswirkungen von Änderungen:** Keine direkten Auswirkungen auf den Händler. Sie sorgt für eine reibungslose Navigation innerhalb des Admin-Bereichs des Moduls.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Kein spezifischer Workflow erforderlich; dies läuft im Hintergrund ab.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | `mypresta_updates` | JA | Aktiviert/deaktiviert Update-Benachrichtigungen von MyPresta.eu. |
|  | `update_` | JA | Internes Flag für den Update-Status. |
|  | `updatev_` | JA | Internes Flag für die Update-Version. |
|  | `DELETEORDERS_LAST_TAB` | (Automatisch verwaltet) | Verfolgt den zuletzt besuchten Tab in der Admin-Oberfläche des Moduls. |
| **Bestellungen löschen Tab** | Filter (Status, Datum, etc.) | Variiert | Grenzt die Liste der zu löschenden Bestellungen ein. |
|  | Auswahl-Kontrollkästchen für Bestellungen | N/A | Ermöglicht die Auswahl einzelner Bestellungen zum Löschen. |
|  | Massenaktion: Ausgewählte löschen | N/A | Entfernt ausgewählte Bestellungen und zugehörige Daten dauerhaft. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe Bestellungen gelöscht, aber die Leistung meines Shops scheint nicht viel schneller zu sein. Warum?**
A: Während das Löschen von Bestellungen die Datenbankgröße reduziert, wird die Leistung von vielen Faktoren beeinflusst (Hosting, andere Module, Theme-Optimierung, Bildgrößen). Das Löschen von Bestellungen ist ein Schritt in der Gesamtoptimierung. Stellen Sie sicher, dass Sie auch den PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) nach dem Löschen geleert haben.

**F: Kann ich Bestellungen wiederherstellen, nachdem ich sie gelöscht habe?**
A: Nein. Sobald Bestellungen mit diesem Modul gelöscht wurden, werden sie dauerhaft aus Ihrer Datenbank entfernt. Deshalb ist es entscheidend, immer ein Backup Ihrer Datenbank zu erstellen, bevor Sie größere Löschungen vornehmen, und Ihre Auswahl sorgfältig zu überprüfen.

**F: Wirkt sich das Löschen von Bestellungen auf meine Kundenkonten oder den Produktbestand aus?**
A: Das Löschen einer Bestellung entfernt den Bestellvorgang selbst und die zugehörigen Details (wie die spezifischen Produkte, die in dieser Transaktion bestellt wurden, Rechnungen, Nachrichten). Es löscht NICHT das mit der Bestellung verbundene Kundenkonto, noch setzt es typischerweise die Lagerbestände zurück (da der Lagerbestand normalerweise zum Zeitpunkt der Auftragserstellung oder Statusänderung angepasst wird, nicht beim Löschen). Überprüfen Sie immer das Verhalten des Moduls in einer Testumgebung, wenn Sie spezifische Bedenken bezüglich des Lagerbestands haben.

**F: Das Modul wird in meinem Back Office-Menü nicht angezeigt.**
A:

1. **Installation überprüfen:** Gehen Sie zu **Module > Modul-Manager** und suchen Sie nach „Delete Orders Pro“. Stellen Sie sicher, dass es als „Installiert“ und „Aktiviert“ aufgeführt ist.
2. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal erfordern Menüänderungen eine Cache-Aktualisierung.
3. **Berechtigungen:** Überprüfen Sie Ihre Benutzerberechtigungen unter **Verwaltung > Berechtigungen**, um sicherzustellen, dass Ihr Profil Zugriff auf den Abschnitt „Bestellungen“ und alle modulspezifischen Berechtigungen hat.

**F: Ich erhalte einen Fehler beim Versuch, Bestellungen zu löschen.**
A:

1. **PrestaShop Debug-Modus überprüfen:** Aktivieren Sie den Debug-Modus (**Erweiterte Einstellungen > Leistung > Debug-Modus**), um zu sehen, ob eine detailliertere Fehlermeldung angezeigt wird.
2. **Server-Fehlerprotokolle:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers (oft in Ihrem Hosting-Kontrollpanel zu finden) auf entsprechende Meldungen.
3. **Support kontaktieren:** Wenn Sie das Problem nicht lösen können, sammeln Sie alle Fehlermeldungen und kontaktieren Sie den MyPresta.eu-Support für Unterstützung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Delete Orders Pro“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Delete Orders Pro“ folgt der Standard-PrestaShop-Modularchitektur und nutzt hauptsächlich Back-Office Admin Controller für seine Funktionalität. Es integriert sich in das PrestaShop-Menüsystem und verwendet PrestaShops Kern-`AdminController` zum Rendern von Listen und zur Bearbeitung von Formularübermittlungen. Das Modul interagiert direkt mit der Datenbank, um Löschvorgänge an bestellbezogenen Tabellen durchzuführen. Es führt keine benutzerdefinierten `ObjectModel`-Klassen ein, sondern arbeitet mit bestehenden PrestaShop-Bestellentitäten.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Dieses Modul hat keine Front-Office-Präsenz.
- **Back-Office Admin Controller**:

  - `deleteorderspro/controllers/admin/deleteorderstab.php`

    - **Klassenname**: `AdminDeleteOrdersProController` (oder ähnlich, typischerweise abgeleitet vom Dateinamen und Modulkontext), erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dies ist der Haupt-Administrationscontroller für das Modul. Er ist verantwortlich für:
      - Anzeige der Bestellliste in einem Rasterformat.
      - Handhabung von Filterung, Sortierung und Paginierung von Bestellungen.
      - Verarbeitung der Löschung ausgewählter Bestellungen.
      - Interaktion mit PrestaShops Kern-`Order` und verwandten `ObjectModel`s, um Datenbanklöschungen durchzuführen.
      - Rendern des Templates für die Bestellliste und die Löschschnittstelle.
    - **PrestaShop-Tab**: Dieser Controller ist als neuer Tab unter dem Menüpunkt „Bestellungen“ im PrestaShop Back Office registriert.
  - `deleteorderspro/controllers/admin/index.php`

    - **Klassenname**: Keine typische Controller-Klasse; oft eine einfache Weiterleitungs- oder Bootstrap-Datei.
    - **Verantwortlichkeit**: Diese Datei dient typischerweise als Fallback oder Einstiegspunkt. In vielen Modulen, wenn ein Benutzer zum Basis-`admin/module_name`-Pfad navigiert, könnte diese `index.php` ihn zum primären Controller (z.B. `deleteorderstab`) weiterleiten, um sicherzustellen, dass die richtige Schnittstelle geladen wird. Sie verhindert den direkten Zugriff auf das Verzeichnis und gewährleistet eine ordnungsgemäße Weiterleitung.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen oder `ObjectModel`s in seinem `classes/`-Verzeichnis einzuführen, basierend auf dem bereitgestellten Inventar. Es arbeitet wahrscheinlich direkt mit PrestaShops Kern-`Order` und verwandten `ObjectModel`s (z.B. `OrderHistory`, `OrderDetail`, `ProductSale`, `Cart` usw.), um eine umfassende Löschung aller zugehörigen Daten zu gewährleisten.

### 4.4 JavaScript-Assets (`views/js/`)

Es wurden keine JavaScript-Dateien im Modularchiv identifiziert. Das Modul verlässt sich wahrscheinlich auf Standard-PrestaShop-Back-Office-JavaScript für Formularübermittlungen und Rasterinteraktionen, oder seine Funktionalität ist vollständig serverseitig.

### 4.5 CSS-Stylesheets (`views/css/`)

Es wurden keine CSS-Dateien im Modularchiv identifiziert. Das Modul erbt wahrscheinlich das Styling direkt vom PrestaShop-Back-Office-Theme, wodurch ein konsistentes Erscheinungsbild ohne benutzerdefinierte Stile gewährleistet wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Es wurden keine `.tpl`-Dateien im Modularchiv identifiziert. Dies deutet darauf hin, dass das Modul möglicherweise die Standard-`list.tpl`- und `form.tpl`-Templates von `AdminController` zum Rendern seines Rasters und seiner Konfiguration verwendet oder seinen HTML-Code direkt im Controller generiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es arbeitet mit bestehenden PrestaShop-Tabellen, die sich auf Bestellungen beziehen, einschließlich, aber nicht beschränkt auf:

  - `ps_orders`
  - `ps_order_detail`
  - `ps_order_history`
  - `ps_order_invoice`
  - `ps_order_payment`
  - `ps_order_return`
  - `ps_order_slip`
  - `ps_cart` (und verwandte `ps_cart_product`)
  - `ps_message` (für Kundenmeldungen zu Bestellungen)
  - `ps_product_sale` (aktualisiert die Verkaufsanzahl)
  - `ps_customer_thread` (für Kundendienst-Threads zu Bestellungen)
  - `ps_configuration` (zum Speichern von Moduleinstellungen wie `mypresta_updates`, `DELETEORDERS_LAST_TAB`).
- **Registrierte Hooks-Tabelle**:
  Basierend auf dem Zweck des Moduls als Back-Office-Verwaltungstool verwendet es hauptsächlich Hooks für die Installation, Deinstallation und möglicherweise das Hinzufügen von Menüpunkten. Es scheint keine Front-Office-Anzeige-Hooks zu verwenden.

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `install()` | Während der Modulinstallation | Erstellt den neuen Tab „Delete Orders Pro“ im PrestaShop Back Office-Menü. Speichert anfängliche Konfigurationswerte in `ps_configuration`. |
  | `uninstall()` | Während der Moduldeinstallation | Entfernt den Tab „Delete Orders Pro“ aus dem Back Office-Menü. Löscht Konfigurationswerte aus `ps_configuration`. |
  | `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Bereich des Back Office | Potenziell verwendet, um notwendige JS/CSS für den Admin-Controller einzubinden, obwohl keine im Inventar identifiziert wurden. |
  | `actionAdminControllerSetMedia` | Ermöglicht das Hinzufügen von JS/CSS zu spezifischen Admin-Controllern | Wird von `AdminDeleteOrdersProController` verwendet, um spezifische Assets hinzuzufügen, die für seine Schnittstelle erforderlich sind. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Updates und zum Herunterladen der neuesten Version des Moduls „Delete Orders Pro“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
