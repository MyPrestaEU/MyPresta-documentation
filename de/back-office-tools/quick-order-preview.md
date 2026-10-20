---
title: "Quick Order Preview - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Quick Order Preview von MyPresta.eu."
sidebar:
  label: "Quick Order Preview - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Quick Order Preview auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/quick-order-preview.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/quick-order-preview/)
>
> ---


# Quick Order Preview

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x, 8.x, 1.7.7.x - 1.7.8.x, 1.7.0.0 - 1.7.6.x, 1.6.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modul „Quick Order Preview“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

Es gibt keine spezifischen Konfigurationsoptionen auf diesem Bildschirm für das Modul „Quick Order Preview“. Das Modul funktioniert sofort, indem es die Funktionalität der bestehenden Seite „Bestellungen“ erweitert. Seine Hauptfunktion besteht darin, die notwendigen JavaScript- und Template-Dateien einzufügen, um die Schnellvorschau-Funktion direkt in Ihrer Bestellliste zu aktivieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminPreviewOrderController (Back Office > Bestellungen > Bestellliste)

Dieses Modul fügt Ihrem PrestaShop-Back-Office keinen neuen Menüpunkt hinzu. Stattdessen erweitert es die bestehende Seite **„Bestellungen“** (zu finden unter **Back Office > Bestellungen > Bestellungen**).

- **Bildschirmname & Menüpfad:** Sie greifen auf diese erweiterte Funktionalität zu, indem Sie in Ihrem PrestaShop-Back-Office zu **Bestellungen > Bestellungen** navigieren.
- **Verfügbare Aktionen & Einstellungen:**
  - **Schnellvorschau-Funktionalität:** Wenn Sie sich auf der Seite „Bestellungen“ befinden, klicken Sie einfach auf eine beliebige Bestellzeile. Anstatt zur vollständigen Bestelldetailseite weitergeleitet zu werden, erweitert das Modul die Bestellzeile, um wichtige Informationen direkt darunter anzuzeigen. Dies beinhaltet:
    - **Kundenadresse:** Rechnungs- und Lieferadressen.
    - **Bestellte Produkte:** Eine Liste der gekauften Artikel, einschließlich Mengen und Preise.
    - **Kundennotiz:** Wenn der Kunde während des Checkouts eine Notiz hinterlassen hat, wird diese hier sichtbar sein.
  - **Schaltfläche „Bestellung anzeigen“:** Innerhalb der erweiterten Vorschau finden Sie weiterhin eine Schaltfläche „Bestellung anzeigen“ (oder einen ähnlichen Link), die es Ihnen ermöglicht, zur vollständigen, traditionellen Bestelldetailseite zu navigieren, falls Sie Aktionen wie das Ändern des Bestellstatus, das Hinzufügen von Produkten oder das Generieren von Rechnungen durchführen müssen.
  - **Speichern von Kundennotizen:** Das Modul enthält auch Funktionen zum Speichern von Kundennotizen direkt aus dieser Schnellvorschau. Dies wird durch das Skript `save-customer-note.js` verwaltet.
- **Auswirkung von Änderungen:**
  - Das Klicken auf eine Bestellzeile schaltet nun die Anzeige ihrer detaillierten Informationen direkt auf der Bestelllistenseite um.
  - Sie können wesentliche Bestelldaten schnell überprüfen, ohne die Hauptliste zu verlassen, was Ihren Bestellbearbeitungs-Workflow erheblich beschleunigt.
  - Die Möglichkeit, Kundennotizen direkt aus der Vorschau zu speichern, optimiert die Kommunikation und die Aufzeichnung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Gehen Sie zu **Bestellungen > Bestellungen**.
  2. Um schnell zu überprüfen, was ein Kunde bestellt hat oder seine Lieferadresse, klicken Sie einfach auf die Bestellzeile in der Liste.
  3. Die Details werden unter der Bestellung erweitert. Überprüfen Sie die Informationen.
  4. Wenn Sie den Bestellstatus ändern, eine Rechnung drucken oder andere erweiterte Aktionen durchführen müssen, klicken Sie auf die Schaltfläche „Bestellung anzeigen“ innerhalb der erweiterten Vorschau, um zur vollständigen Bestelldetailseite zu gelangen.
  5. Wenn Sie eine kurze Notiz über den Kunden oder die Bestellung hinzufügen müssen, verwenden Sie das Kundennotizfeld innerhalb der Vorschau und speichern Sie es.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Bestellliste | Bestellzeile anklicken | N/A | Erweitert Bestelldetails (Produkte, Adressen, Notizen) direkt auf der Listenseite und spart Navigationszeit. |
| Bestellliste | Kundennotizfeld | N/A | Ermöglicht das Speichern von Notizen direkt aus der Schnellvorschau. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Die Bestelldetails werden nicht erweitert, wenn ich auf eine Bestellzeile klicke. Was ist falsch?**
A:

1. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal verhindern alte Cache-Dateien das Laden neuer Modulskripte.
2. **Modul aktiviert:** Stellen Sie sicher, dass das Modul „Quick Order Preview“ unter **Module > Modul-Manager** aktiviert ist.
3. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können sehr stark angepasste Themes manchmal stören. Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12) auf JavaScript-Fehler. Wenn Sie Fehler im Zusammenhang mit dem Modul sehen, wenden Sie sich an den MyPresta.eu-Support.
4. **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre spezifische PrestaShop-Installation heruntergeladen und installiert haben.

**F: Kann ich anpassen, welche Informationen in der Schnellvorschau angezeigt werden?**
A: Das Modul zeigt wesentliche Informationen wie Produkte und Adressen an. Das Anpassen der angezeigten Felder würde eine direkte Änderung der Template-Dateien des Moduls (`address.tpl`, `products.tpl`) erfordern. Dies ist eine Aufgabe auf Entwicklerebene.

**F: Beeinträchtigt dieses Modul die Leistung meines Shops?**
A: Nein, das Modul ist leichtgewichtig konzipiert. Es lädt nur zusätzlichen Inhalt, wenn Sie explizit auf eine Bestellzeile im Back-Office klicken. Es verursacht keinen Overhead für Ihr Front-Office oder das allgemeine Back-Office-Browsing.

**F: Ich verwende eine ältere PrestaShop 1.6 Version, wird das funktionieren?**
A: Ja, das Modul ist mit PrestaShop 1.6.x kompatibel. Stellen Sie sicher, dass Sie das richtige Paket für Ihre PrestaShop-Version von Ihrem MyPresta.eu-Konto herunterladen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Quick Order Preview“ (`qov`) ist primär ein Back-Office-Erweiterungsmodul. Es nutzt den `AdminController`-Override-Mechanismus von PrestaShop und Smarty-Templating, um dynamische Inhalte in die bestehende „Bestellungen“-Liste einzufügen. Es verwendet JavaScript, um die AJAX-Anfragen und die DOM-Manipulation zum Erweitern/Zusammenklappen von Bestelldetails zu handhaben. Das Modul führt keine neuen Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, sondern konzentriert sich stattdessen auf die Erweiterung bestehender PrestaShop-Funktionalität.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Dieses Modul ist ausschließlich ein Back-Office-Tool.
- **Back-Office-Admin-Controller**:

  - `qov/controllers/admin/AdminPreviewOrder.php`
    - **Klassenname & Elternklasse**: `AdminPreviewOrderController` erweitert `AdminOrdersController`.
    - **Verantwortlichkeit**: Dieser Controller überschreibt den Standard-`AdminOrdersController`, um das notwendige JavaScript einzufügen und möglicherweise die Methode `renderList()` zu modifizieren, um die Schnellvorschau-Funktionalität zu integrieren. Er ist verantwortlich für die Bearbeitung der AJAX-Anfragen, die die Bestelldetails (Produkte, Adressen) abrufen, wenn eine Bestellzeile angeklickt wird, und für das Rendern der Templates `address.tpl` und `products.tpl` mit den abgerufenen Daten. Er verwaltet auch den Konfigurationsschlüssel `QOV_TRACKING_EMAIL`, obwohl seine direkte Verwendung aus den bereitgestellten Informationen nicht ersichtlich ist.

### 4.3 Kernklassen & Modelle (`classes/`)

Keine. Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder komplexe Geschäftslogik-Klassen. Es interagiert primär mit bestehenden PrestaShop-Kernklassen wie `Order`, `Address`, `Product` usw. über seinen Controller.

### 4.4 JavaScript-Assets (`views/js/`)

- `qov/views/js/177-expand-all-imm.js`

  - **Geltungsbereich**: Back-Office (Bestellliste, PrestaShop 1.7.7+).
  - **Beschreibung**: Dieses Skript handhabt wahrscheinlich die sofortige Erweiterung aller Bestelldetails auf der Bestelllistenseite, möglicherweise für eine bestimmte Ansicht oder Aktion. Es würde Klickereignisse an Bestellzeilen binden und AJAX-Aufrufe auslösen, um Details für mehrere Bestellungen gleichzeitig abzurufen und anzuzeigen.
- `qov/views/js/177-expand-all.js`

  - **Geltungsbereich**: Back-Office (Bestellliste, PrestaShop 1.7.7+).
  - **Beschreibung**: Ähnlich wie `177-expand-all-imm.js` ist dieses Skript für die „Alle erweitern“-Funktionalität verantwortlich. Es würde auf einen bestimmten Auslöser (z.B. einen Button-Klick) warten, um alle sichtbaren Bestelldetails auf der aktuellen Seite zu erweitern, wobei für jede Bestellung AJAX-Anfragen gestellt werden.
- `qov/views/js/177orders-multiple.js`

  - **Geltungsbereich**: Back-Office (Bestellliste, PrestaShop 1.7.7+).
  - **Beschreibung**: Dies ist das Kernskript, das die Schnellvorschau-Funktionalität ermöglicht. Es bindet Klickereignisse an einzelne Bestellzeilen in der `AdminOrders`-Liste. Wenn eine Bestellzeile angeklickt wird, verhindert es die Standardnavigation zur vollständigen Bestellseite. Stattdessen sendet es eine AJAX-Anfrage an den `AdminPreviewOrderController` (oder einen ähnlichen Endpunkt), um die Produkte, Adressen und andere Details der Bestellung abzurufen. Anschließend injiziert es den gerenderten HTML-Code (aus `address.tpl` und `products.tpl`) dynamisch in eine neue Zeile oder einen erweiterten Abschnitt unter der angeklickten Bestellzeile. Es handhabt auch das Zusammenklappen der Details, wenn die Zeile erneut angeklickt wird.
- `qov/views/js/save-customer-note.js`

  - **Geltungsbereich**: Back-Office (Bestellliste, speziell innerhalb der Schnellvorschau).
  - **Beschreibung**: Dieses Skript handhabt die Funktionalität zum Speichern von Kundennotizen direkt aus der Schnellbestellvorschau. Es bindet an Eingabefelder oder Schaltflächen innerhalb der erweiterten Bestelldetails. Wenn eine Notiz eingegeben oder aktualisiert wird, sendet es eine AJAX-Anfrage an einen Back-Office-Endpunkt (wahrscheinlich den `AdminPreviewOrderController` oder den Standard-`AdminOrdersController` mit einer spezifischen Aktion), um die Notiz in der Datenbank zu speichern, typischerweise in der Tabelle `ps_order_note` oder einer ähnlichen.

### 4.5 CSS-Stylesheets (`views/css/`)

Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien. Es verlässt sich wahrscheinlich auf bestehende PrestaShop-Back-Office-Stile oder Inline-Stile für die erweiterten Bestelldetails. Entwickler, die die Vorschau gestalten möchten, sollten die dynamisch eingefügten HTML-Elemente ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `qov/views/templates/admin/address.tpl`
    - **Beschreibung**: Dieses Template wird verwendet, um die Rechnungs- und Lieferadressdetails des Kunden innerhalb der Schnellbestellvorschau zu rendern. Es empfängt Adressdaten vom `AdminPreviewOrderController` und formatiert sie zur Anzeige.
  - `qov/views/templates/admin/products.tpl`
    - **Beschreibung**: Dieses Template ist verantwortlich für das Rendern der Liste der vom Kunden bestellten Produkte innerhalb der Schnellbestellvorschau. Es empfängt Produktdaten (Name, Menge, Preis usw.) und zeigt sie in einem klaren Tabellen- oder Listenformat an.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es liest aus und schreibt (für Kundennotizen) möglicherweise in Standard-PrestaShop-Tabellen wie `ps_orders`, `ps_order_detail`, `ps_address`, `ps_customer` und `ps_order_note`.
  - Konfigurationswerte werden in `ps_configuration` gespeichert, insbesondere `QOV_TRACKING_EMAIL`.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine expliziten Front-Office-Hooks (wie `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`), da es ein Back-Office-Modul ist. Seine Funktionalität wird primär durch das Überschreiben des `AdminOrdersController` und das Hinzufügen von JavaScript und Templates zur bestehenden Back-Office-Seite „Bestellungen“ injiziert.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin Controller seine Medien-Assets setzt. | Wird vom `AdminPreviewOrderController` verwendet, um seine JavaScript-Dateien (`177-expand-all-imm.js`, `177-expand-all.js`, `177orders-multiple.js`, `save-customer-note.js`) für die `AdminOrders`-Seite in die Warteschlange zu stellen. |
| `displayAdminOrder` | Wird auf der Admin-Bestellseite ausgeführt. | Obwohl nicht explizit als Hook aufgeführt, wird die Kernfunktionalität des Moduls durch das Überschreiben des `AdminOrdersController` und das Modifizieren seiner `renderList()`-Methode oder durch das Injizieren von Inhalten über JavaScript in die bestehende Bestellliste erreicht. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Quick Order Preview“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
