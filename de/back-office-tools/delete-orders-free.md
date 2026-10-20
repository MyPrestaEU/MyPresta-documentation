---
title: "Delete Orders Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Delete Orders Free von MyPresta.eu."
sidebar:
  label: "Delete Orders Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Delete Orders Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/delete-orders-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/delete-orders-free/)
>
> ---


# Delete Orders Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls. Diese Seite verwaltet hauptsächlich Update-Benachrichtigungen für das Modul selbst.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt verwaltet die Fähigkeit des Moduls, nach Updates zu suchen und Benachrichtigungen anzuzeigen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul sucht regelmäßig auf MyPresta.eu nach neueren Versionen. Wenn ein Update verfügbar ist, kann eine Benachrichtigung in Ihrem PrestaShop Back Office erscheinen, die Sie auffordert, die neueste Version herunterzuladen und zu installieren. Dies stellt sicher, dass Sie immer die sicherste und funktionsreichste Version des Moduls haben.
  - *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates. Sie müssten MyPresta.eu manuell besuchen, um nach neuen Versionen zu suchen. Obwohl dies die Serveranfragen leicht reduzieren könnte, bedeutet es, dass Sie wichtige Updates oder Fehlerbehebungen verpassen könnten.
- **Empfohlener Wert:** **Aktiviert (JA)**. Wenn diese Option aktiviert bleibt, werden Sie immer über die neuesten Verbesserungen und Sicherheitspatches für das Modul informiert.
- **Händlerszenario / Beispiel:** Sie möchten benachrichtigt werden, wenn eine neue Version von „Delete Orders Free“ veröffentlicht wird, die einen Fehler behebt oder eine neue Funktion hinzufügt. Wenn diese Option aktiviert bleibt, wird eine Benachrichtigung in Ihrem PrestaShop-Admin-Panel angezeigt.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Bestellungen löschen Tab (Back Office > Bestellungen > Bestellungen löschen)

Dies ist die primäre Schnittstelle für die Funktionalität des Moduls.

- **Bildschirmname & Menüposition:** Sie können auf diesen Bildschirm zugreifen, indem Sie im PrestaShop Back Office-Menü zu **Bestellungen > Bestellungen löschen** navigieren.
- **Verfügbare Aktionen & Einstellungen:**
  - Beim Betreten dieses Tabs sehen Sie eine Liste aller Bestellungen in Ihrem PrestaShop-Shop, ähnlich der Standard-„Bestellungen“-Liste.
  - Jede Bestellung in der Liste hat eine dedizierte Schaltfläche oder ein Symbol **„Löschen“** (oft ein Papierkorb-Symbol) daneben.
  - **Eine Bestellung löschen:** Durch Klicken auf die Schaltfläche „Löschen“ neben einer beliebigen Bestellung wird diese Bestellung sofort und dauerhaft aus Ihrer Datenbank entfernt. Diese Aktion ist irreversibel.
- **Auswirkung von Änderungen:**
  - Wenn Sie für eine Bestellung auf „Löschen“ klicken, wird der Bestelldatensatz zusammen mit allen zugehörigen Daten (wie Bestelldetails, kundenbezogene Nachrichten zu dieser Bestellung, Rechnungen und möglicherweise Lagerbewegungen, wenn der Bestellstatus so konfiguriert war, dass er den Lagerbestand beeinflusst) aus Ihrer PrestaShop-Datenbank entfernt.
  - Die Bestellung wird nicht mehr in Ihrer „Bestellungen“-Liste angezeigt und auch nicht in Verkaufsberichten oder Statistiken enthalten sein.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie regelmäßig Ihre „Bestellungen“-Liste auf Testbestellungen, betrügerische Bestellungen oder Bestellungen, die vollständig storniert wurden und nicht mehr verfolgt werden müssen.
  2. Navigieren Sie zu **Bestellungen > Bestellungen löschen**.
  3. Identifizieren Sie sorgfältig die Bestellungen, die Sie entfernen möchten.
  4. Klicken Sie auf die Schaltfläche „Löschen“ neben jeder spezifischen Bestellung, die Sie entfernen möchten.
  5. Bestätigen Sie die Löschung, wenn Sie dazu aufgefordert werden.
  6. **Wichtig:** Seien Sie äußerst vorsichtig, da diese Aktion dauerhaft und nicht rückgängig zu machen ist. Es wird dringend empfohlen, eine Datenbanksicherung durchzuführen, bevor Sie eine große Anzahl von Bestellungen löschen.

#### 2.2.2 Index.php (deleteordersfree/controllers/admin/index.php)

Diese Datei ist ein Standard-PrestaShop-Controller-Platzhalter und bietet dem Händler normalerweise keinen direkten, konfigurierbaren Bildschirm. Ihr Zweck ist es normalerweise, zur Hauptmodulkonfiguration oder einem bestimmten Admin-Tab umzuleiten. Im Kontext dieses Moduls stellt sie wahrscheinlich sicher, dass die Navigation zum Basis-Admin-Pfad des Moduls Sie korrekt zum `deleteorderstab`-Controller leitet.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Update-Prüfung (mypresta\_updates) | Aktiviert (JA) | Steuert, ob das Modul nach neuen Versionen sucht und Sie benachrichtigt. Für Updates aktiviert lassen. |
| **Bestellungen > Bestellungen löschen** | Löschen-Schaltfläche (pro Bestellung) | N/A | Entfernt eine ausgewählte Bestellung und ihre zugehörigen Daten dauerhaft aus der Datenbank. **Irreversible Aktion.** |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe versehentlich eine Bestellung gelöscht! Kann ich sie wiederherstellen?**
A: Leider nein. Das Modul „Delete Orders Free“ führt eine dauerhafte Löschung durch. Deshalb betonen wir die Vorsicht. Haben Sie immer ein aktuelles Backup Ihrer Datenbank, insbesondere bevor Sie Massenlöschungen durchführen. Wenn Sie ein Backup haben, können Sie möglicherweise Ihre gesamte Datenbank in einen früheren Zustand zurückversetzen, aber dies würde auch alle anderen seit dem Backup vorgenommenen Änderungen rückgängig machen.

**F: Ich sehe den Tab „Bestellungen löschen“ nicht unter dem Menü „Bestellungen“.**
A:

1. **Modulinstallation überprüfen:** Gehen Sie zu **Module > Modul-Manager** und suchen Sie nach „Delete Orders Free“. Stellen Sie sicher, dass es installiert und aktiviert ist.
2. **Cache leeren:** Manchmal muss der PrestaShop-Menü-Cache aktualisiert werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“.
3. **Berechtigungen überprüfen:** Stellen Sie sicher, dass Ihr Benutzerprofil die erforderlichen Berechtigungen zum Zugriff und zur Verwaltung von Modulen und Bestellungen hat. Gehen Sie zu **Erweiterte Einstellungen > Team > Profile**, wählen Sie Ihr Profil aus und gehen Sie dann zu **Berechtigungen > Module** und **Berechtigungen > Bestellungen**, um dies zu überprüfen.

**F: Wird das Löschen einer Bestellung auch den Kunden erstatten oder die Zahlung stornieren?**
A: Nein. Dieses Modul entfernt nur den Bestelldatensatz aus Ihrer PrestaShop-Datenbank. Es interagiert NICHT mit Zahlungsgateways (wie PayPal, Stripe usw.), um Rückerstattungen auszustellen oder Transaktionen zu stornieren. Sie müssen alle Zahlungsrückabwicklungen oder Rückerstattungen direkt über die Schnittstelle Ihres Zahlungsgateways abwickeln.

**F: Beeinflusst das Löschen einer Bestellung den Produktbestand?**
A: Wenn Ihre PrestaShop-Konfiguration für Bestellstatus so eingestellt ist, dass der Lagerbestand bei einer Bestellung reduziert wird, und Sie eine Bestellung löschen, wird der Lagerbestand NICHT automatisch wieder erhöht. Sie müssten den Lagerbestand für die betroffenen Produkte manuell anpassen, wenn Sie diese wieder in den Bestand aufnehmen möchten. Dies ist ein wichtiger Punkt, den Sie für die Bestandsverwaltung beachten sollten.

**F: Das Modul ist installiert, aber ich sehe keine „Löschen“-Schaltflächen in der Bestellliste.**
A: Stellen Sie sicher, dass Sie sich auf dem dedizierten Tab **Bestellungen > Bestellungen löschen** befinden und nicht auf der Standardliste **Bestellungen > Bestellungen**. Die Löschfunktion wird speziell zum benutzerdefinierten Tab des Moduls hinzugefügt.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Karte)

### 4.1 Architekturübersicht

Das Modul „Delete Orders Free“ ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Erweiterung der Back-Office-Funktionalität konzentriert. Es folgt einem Standard-PrestaShop-MVC-Muster für seine administrative Schnittstelle. Die Kernlogik befindet sich in der Hauptmoduldatei für die Installation/Deinstallation und in einem dedizierten AdminController für die Verwaltung des Bestelllöschvorgangs. Es führt keine neuen Datenbanktabellen oder komplexen Front-Office-Interaktionen ein.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Dieses Modul hat keine Front-Office-Präsenz.
- **Back-Office-Admin-Controller**:

  - `deleteordersfree/controllers/admin/deleteorderstab.php`
    - **Klassenname & Elternklasse**: `DeleteOrdersTabController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dies ist der Hauptcontroller für die Funktionalität des Moduls. Er rendert die Liste der Bestellungen im Back Office und bietet die Aktion „Löschen“ für jede Bestellung. Er verarbeitet die Logik zum Empfangen der Löschungsanfrage (z. B. über GET-Parameter oder POST-Übermittlung) und führt dann die Datenbanklöschung für die angegebene Bestell-ID aus. Dieser Controller überschreibt oder erweitert wahrscheinlich Methoden von `AdminController`, um die Bestellliste anzuzeigen und die benutzerdefinierte Aktion hinzuzufügen.
  - `deleteordersfree/controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Dies ist typischerweise eine Platzhalterdatei, die eine korrekte Weiterleitung innerhalb des Admin-Bereichs sicherstellt. Sie enthält normalerweise eine einfache `header('Location: ...')`-Umleitung oder eine leere Datei, um die Verzeichnisauflistung zu verhindern. In PrestaShop werden `index.php`-Dateien in Unterverzeichnissen von `controllers/admin` oft verwendet, um den Einstiegspunkt für einen bestimmten Abschnitt zu definieren oder den direkten Zugriff zu verhindern. Für dieses Modul stellt sie wahrscheinlich sicher, dass der Zugriff auf den Basis-Pfad `admin/deleteordersfree` korrekt zum `deleteorderstab`-Controller leitet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es interagiert direkt mit PrestaShops Kernklassen `Order` und verwandten `ObjectModel`-Klassen (z. B. `OrderInvoice`, `OrderPayment`, `OrderHistory`, `Message`, `Cart`, `CustomerThread`, `SpecificPrice`, `StockAvailable`), um Löschungen durchzuführen.

### 4.4 JavaScript-Assets (`views/js/`)

Es sind keine benutzerdefinierten JavaScript-Dateien in diesem Modul enthalten. Die Löschaktion wird wahrscheinlich über eine Standard-Formularübermittlung oder eine einfache GET-Anfrage mit einer Bestätigungsaufforderung abgewickelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Es sind keine benutzerdefinierten CSS-Dateien in diesem Modul enthalten. Das Modul verlässt sich für seine Benutzeroberfläche auf das Standard-Back-Office-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Es sind keine benutzerdefinierten Smarty-Template-Dateien explizit im Modulinventar aufgeführt. Der `deleteorderstab`-Controller verwendet wahrscheinlich PrestaShops Standard `list.tpl` oder ähnliche Templates zum Rendern des Bestellrasters und injiziert die „Löschen“-Aktion über die Controller-Logik (z. B. die Methode `renderList()`).

### 4.7 Datenbankschema & Hooks-Karte

- **Datenbanktabellen**: Dieses Modul erstellt keine neuen benutzerdefinierten Datenbanktabellen. Es arbeitet direkt mit bestehenden PrestaShop-Kerntabellen, die mit Bestellungen zusammenhängen, wie zum Beispiel:

  - `ps_orders`
  - `ps_order_detail`
  - `ps_order_history`
  - `ps_order_invoice`
  - `ps_order_payment`
  - `ps_message` (für Nachrichten, die mit der Bestellung zusammenhängen)
  - `ps_cart` (der Warenkorb, der mit der Bestellung zusammenhängt)
  - `ps_customer_thread` (Kundenservice-Threads, die mit der Bestellung zusammenhängen)
  - `ps_specific_price` (wenn spezifische Preise über die Bestellung angewendet wurden)
  - `ps_stock_available` (wenn der Lagerbestand durch die Bestellung reduziert wurde)
  - Und möglicherweise andere verwandte Tabellen (z. B. `ps_order_carrier`, `ps_order_slip`).
    Es speichert auch seine Konfigurationseinstellungen (wie `mypresta_updates`) in der Tabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:
  Die Modulbeschreibung erwähnt „Front-Office Hooks: Header, Columns, Product, or Footer“, aber die Funktionalität des Moduls ist rein Back-Office-bezogen. Dies deutet darauf hin, dass diese Hooks entweder nicht aktiv von der Kernlogik des Moduls verwendet werden oder Überbleibsel einer generischen Modulvorlage sind. Basierend auf dem angegebenen Zweck des Moduls und dem Dateiverzeichnis ist es höchst unwahrscheinlich, dass es etwas in diesen Front-Office-Hooks rendert.

  Die primäre Hook-Nutzung für dieses Modul ist wahrscheinlich:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein AdminController initialisiert wird und bevor sein Inhalt gerendert wird. | Potenziell verwendet, um benutzerdefinierte JS/CSS hinzuzufügen (obwohl keine aufgeführt sind) oder um spezifische modulbezogene Assets für die Admin-Seite zu registrieren. |
  | `displayBackOfficeHeader` | Wird im Header jeder Back-Office-Seite ausgeführt. | Könnte für Update-Benachrichtigungen oder zum Einfügen kleinerer admin-spezifischer Skripte/Styles verwendet werden. |
  | `actionModuleInstall` | Wird ausgeführt, wenn das Modul installiert wird. | Erstellt den Tab „Bestellungen löschen“ im Back-Office-Menü und setzt Standardkonfigurationswerte. |
  | `actionModuleUninstall` | Wird ausgeführt, wenn das Modul deinstalliert wird. | Entfernt den Tab „Bestellungen löschen“ und bereinigt Konfigurationswerte. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Delete Orders Free“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen zur Funktionalität des Moduls zur Verfügung.
