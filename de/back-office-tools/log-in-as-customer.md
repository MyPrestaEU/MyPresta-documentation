---
title: "Als Kunde anmelden - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Als Kunde anmelden“ von MyPresta.eu."
sidebar:
  label: "Als Kunde anmelden - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Log in as customer auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/log-in-as-customer.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/log-in-as-customer/)
>
> ---


# Als Kunde anmelden

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Das Modul „Als Kunde anmelden“ hat eine sehr unkomplizierte Konfiguration. Nach der Installation, wenn Sie auf „Konfigurieren“ klicken, gelangen Sie zu einem einfachen Bildschirm.

**Bildschirmname & Menüpfad:** Back Office > Module > Modul-Manager > Als Kunde anmelden > Konfigurieren

Auf diesem Bildschirm finden Sie typischerweise eine einfache Bestätigung, dass das Modul installiert und bereit ist. Die Kernfunktionalität dieses Moduls ist direkt in Ihre Kundenliste integriert, anstatt umfangreiche Einstellungen auf einer dedizierten Konfigurationsseite zu erfordern.

- **Was dieser Bildschirm leistet:** Diese Seite bestätigt die Installation des Moduls und bietet grundlegende Informationen oder schnelle Links. Für „Als Kunde anmelden“ besteht der Hauptzweck darin, zu bestätigen, dass das Modul aktiv und einsatzbereit ist.
- **Auswirkung von Einstellungsänderungen:** Es gibt hier keine komplexen Einstellungen zu ändern. Die Funktionalität des Moduls wird bei der Installation aktiviert.
- **Empfohlener Wert:** Keine spezifischen Werte einzustellen. Stellen Sie einfach sicher, dass das Modul installiert und aktiviert ist.
- **Händlerszenario / Beispiel:** Nach der Installation sehen Sie eine Meldung, die bestätigt, dass das Modul aktiv ist. Sie können dann direkt zum Bereich „Kunden“ Ihres Back Office gehen, um dessen Funktionen zu nutzen.

### 2.2 Verwenden der Funktion „Als Kunde anmelden“

Die Hauptfunktionalität dieses Moduls wird direkt über Ihre PrestaShop-Kundenliste aufgerufen.

**Bildschirmname & Menüpfad:** Back Office > Kunden > Kunden

1. **Navigieren Sie zu Kunden:** Gehen Sie in Ihrem PrestaShop Back Office zum Menü **Kunden** und klicken Sie dann auf **Kunden**.
2. **Suchen Sie den Kunden:** Finden Sie den Kunden, als den Sie sich anmelden möchten, in der Kundenliste. Sie können die Such- und Filteroptionen verwenden, um ihn schnell zu finden.
3. **Klicken Sie auf die Schaltfläche „Als Kunde anmelden“:** Für jeden Kunden in der Liste sehen Sie nun eine zusätzliche Schaltfläche (oft ein Symbol wie eine Person oder ein Schlüssel oder eine Textschaltfläche) in der Spalte „Aktionen“. Diese Schaltfläche wird vom Modul „Als Kunde anmelden“ hinzugefügt.
   - **Was diese Schaltfläche leistet:** Wenn Sie auf diese Schaltfläche klicken, führt das Modul einen sicheren Anmeldevorgang durch. Es meldet Sie von Ihrem Administrator-Konto ab (vorübergehend) und meldet Sie dann als den ausgewählten Kunden an.
   - **Auswirkung des Klickens auf diese Schaltfläche:** Sie werden sofort zum Front Office Ihres Shops weitergeleitet. Sie sehen den Shop genau so, wie dieser Kunde ihn sieht, einschließlich seines aktiven Warenkorbs, seiner Bestellhistorie, Adressen und aller personalisierten Inhalte oder Preise.
   - **Händlerszenario / Beispiel:** Ein Kunde meldet ein Problem beim Hinzufügen eines bestimmten Produkts zu seinem Warenkorb. Sie navigieren zu „Kunden“, finden seinen Namen, klicken auf „Als Kunde anmelden“ und werden sofort als dieser Kunde zum Front Office weitergeleitet. Sie können dann versuchen, das Produkt selbst hinzuzufügen, das Problem zu beheben oder den Warenkorbinhalt zu überprüfen.
4. **Abmelden als Kunde:** Um zu Ihrer Back Office-Administrator-Sitzung zurückzukehren, melden Sie sich einfach vom Front Office ab (als wären Sie ein normaler Kunde). Dadurch wird die Kundensitzung beendet, und Sie können sich dann wieder in Ihr Back Office einloggen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | (Keine direkten Einstellungen) | N/A | Bestätigt die Modulinstallation und -bereitschaft. |
| Kundenliste (Back Office) | Schaltfläche „Als Kunde anmelden“ | N/A | Ermöglicht die sofortige Anmeldung im Front Office als ausgewählter Kunde zur Fehlerbehebung und zum Testen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber die Schaltfläche „Als Kunde anmelden“ in der Kundenliste nicht.**
A:

1. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
2. **Modulstatus:** Stellen Sie sicher, dass das Modul aktiviert ist. Gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Als Kunde anmelden“ und überprüfen Sie, ob es aktiv ist.
3. **Theme-Kompatibilität:** Obwohl selten, können einige stark angepasste Themes die Anzeige neuer Schaltflächen beeinträchtigen. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.
4. **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Installation heruntergeladen haben.

**F: Wenn ich auf die Schaltfläche klicke, werde ich zum Front Office weitergeleitet, bin aber nicht als Kunde angemeldet.**
A:

1. **Browser-Cookies:** Stellen Sie sicher, dass Ihr Browser Cookies akzeptiert. Versuchen Sie, den Cache und die Cookies Ihres Browsers zu löschen, und versuchen Sie es dann erneut.
2. **Sitzungskonfiguration:** Überprüfen Sie die Einstellungen `_PS_COOKIE_DOMAIN_` und `_PS_COOKIE_PATH_` in der Datei `config/defines.inc.php` Ihres PrestaShops. Stellen Sie sicher, dass sie für Ihre Domain korrekt konfiguriert sind.
3. **Serverkonfiguration:** Überprüfen Sie, ob die PHP-Sitzungseinstellungen Ihres Servers Standard sind und nicht übermäßig restriktiv.

**F: Kann ich mich als Kunde anmelden und dann Aktionen wie das Aufgeben einer Bestellung für ihn ausführen?**
A: Ja, das können Sie. Seien Sie jedoch äußerst vorsichtig. Holen Sie immer die ausdrückliche Erlaubnis des Kunden ein, bevor Sie in seinem Namen Aktionen ausführen, insbesondere Bestellungen aufgeben oder persönliche Daten ändern. Es ist im Allgemeinen Best Practice, diese Funktion zum Anzeigen und zur Fehlerbehebung zu verwenden, nicht zum Vornehmen von Änderungen ohne Zustimmung.

**F: Ist die Verwendung dieses Moduls sicher? Speichert es Kundenpasswörter?**
A: Das Modul speichert oder greift nicht auf Kundenpasswörter zu. Es verwendet die interne Sitzungsverwaltung von PrestaShop, um eine Kundenanmeldung zu simulieren, ähnlich wie die „Passwort vergessen“-Funktion von PrestaShop durch Generierung einer temporären sicheren Sitzung funktioniert. Es ist auf Sicherheit ausgelegt.

**F: Was passiert, wenn ich mich als Kunde anmelde und dann meinen Browser schließe, ohne mich abzumelden?**
A: Die Kundensitzung läuft schließlich ab, basierend auf den Sitzungs-Timeout-Einstellungen Ihres PrestaShops. Um zu Ihrem Admin-Panel zurückzukehren, navigieren Sie einfach zu Ihrer Back Office-URL und melden sich erneut als Administrator an.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Als Kunde anmelden“ (`lac`) ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die Erweiterung der Funktionalität der Back Office-Kundenliste konzentriert. Es nutzt die Kernklassen `Customer` und `Context` von PrestaShop, um Benutzersitzungen und Weiterleitungen zu verwalten. Das Modul injiziert JavaScript in das Back Office, um die Schaltfläche „Als Kunde anmelden“ hinzuzufügen, und verwendet einen dedizierten Front-Controller, um den sicheren Anmeldevorgang und die Weiterleitung zum Front Office zu handhaben. Es folgt einer Standard-PrestaShop-Modularchitektur und integriert sich nahtlos ohne benutzerdefinierte Datenbanktabellen oder komplexe Objektmodelle.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `lac/controllers/front/index.php`
    - **Klassenname**: `LacIndexModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention)
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als Landepunkt oder Fallback. Angesichts des `login.php`-Controllers könnte `index.php` weniger kritisch sein oder die anfängliche Einrichtung/Weiterleitung handhaben, wenn `login.php` der primäre Aktionshandler ist. Es könnte auch ein Platzhalter sein.
  - `lac/controllers/front/login.php`
    - **Klassenname**: `LacLoginModuleFrontController` (wahrscheinlich)
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dies ist der Kern-Controller für die Funktionalität „Als Kunde anmelden“.
      - Er empfängt die Kunden-ID über einen GET- oder POST-Parameter vom Back Office.
      - Er führt die notwendigen Schritte aus, um die aktuelle Administrator-Sitzung abzumelden.
      - Anschließend meldet er den angegebenen Kunden sicher an, indem er die Objekte `Context` und `Customer` manipuliert (z.B. `Context::getContext()->customer = new Customer($id_customer); Context::getContext()->cookie->id_customer = $id_customer;`).
      - Anschließend leitet er den Browser zur Front Office-Startseite oder einer spezifischen kundenbezogenen Seite (`my-account`, `history`, etc.) weiter.
- **Back-Office-Admin-Controller**:

  - Keine. Das Modul integriert sich direkt in die Ansicht des bestehenden `AdminCustomers`-Controllers über Hooks und JavaScript.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Dieses Modul führt keine benutzerdefinierten `ObjectModel`-Klassen oder Datenbanktabellen ein. Es arbeitet direkt mit den nativen `Customer`- und `Context`-Objekten von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

Diese JavaScript-Dateien sind dafür verantwortlich, die Schaltfläche „Als Kunde anmelden“ in die Back Office-Kundenliste einzufügen und das Klickereignis zu verarbeiten, um den Anmeldevorgang zu initiieren. Die unterschiedlichen Dateinamen deuten auf Kompatibilitätsanpassungen für verschiedene PrestaShop-Versionen hin.

- `lac/views/js/16customers.js`
  - **Umfang**: Back Office (PrestaShop 1.6.x `AdminCustomers`-Liste).
  - **Funktionalität**: Dieses Skript zielt auf die Kundenlistentabelle in PrestaShop 1.6.x ab. Es verwendet wahrscheinlich jQuery-Selektoren, um die Spalte „Aktionen“ für jede Kundenzeile zu finden und eine neue Schaltfläche oder einen Link anzuhängen. Der Klick-Handler für diese Schaltfläche erstellt dann eine URL, die auf den Front-Controller des Moduls (`lac/controllers/front/login.php`) mit der Kunden-ID verweist, und leitet den Browser um.
- `lac/views/js/176orders.js`
  - **Umfang**: Back Office (PrestaShop 1.7.6.x Bestellansicht).
  - **Funktionalität**: Dieses Skript könnte dazu gedacht sein, eine Schaltfläche „Als Kunde anmelden“ direkt aus der Bestellansicht in 1.7.6.x hinzuzufügen, um einen schnellen Zugriff auf den mit einer bestimmten Bestellung verbundenen Kunden zu ermöglichen. Es würde die Kunden-ID von der Bestelldetailseite extrahieren und für die Anmelde-Weiterleitung verwenden.
- `lac/views/js/177orders.js`
  - **Umfang**: Back Office (PrestaShop 1.7.7.x+ Bestellansicht).
  - **Funktionalität**: Ähnlich wie `176orders.js`, aber angepasst an potenzielle DOM-Änderungen oder unterschiedliche Tabellenstrukturen in PrestaShop 1.7.7.x und späteren Versionen der Bestellansicht.
- `lac/views/js/17carts.js`
  - **Umfang**: Back Office (PrestaShop 1.7.x Warenkorbansicht).
  - **Funktionalität**: Dieses Skript fügt wahrscheinlich die Schaltfläche „Als Kunde anmelden“ zur Back Office-Warenkorbdetailseite hinzu, sodass ein Administrator sich als der Kunde anmelden kann, der mit einem bestimmten Warenkorb verbunden ist.
- `lac/views/js/17customersview.js`
  - **Umfang**: Back Office (PrestaShop 1.7.x, 8.x, 9.x `AdminCustomers`-Liste).
  - **Funktionalität**: Dies ist das primäre Skript zum Einfügen der Schaltfläche in die Kundenliste für moderne PrestaShop-Versionen. Es zielt auf die `AdminCustomers`-Liste ab, identifiziert die Kunden-ID für jede Zeile und hängt die Aktionsschaltfläche „Als Kunde anmelden“ an. Es verwendet Ereignisdelegation, um Klicks auf diese dynamisch hinzugefügten Schaltflächen zu verarbeiten und die entsprechende URL für den Controller `lac/controllers/front/login.php` zu erstellen.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien. Es verlässt sich wahrscheinlich auf die Standard-PrestaShop-Formatierung für Schaltflächen oder verwendet bei Bedarf Inline-Styles, oder die Schaltfläche wird vom Back Office-Theme selbst gestylt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Keine. Das Modul verwendet keine benutzerdefinierten Smarty-Templates. Seine Back Office-Integration erfolgt ausschließlich über JavaScript-Injektion, und die Front-Office-Anmeldung wird durch direkte Weiterleitung vom Controller aus gehandhabt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfiguration (falls vorhanden, obwohl keine über den grundlegenden Modulstatus hinaus explizit identifiziert wurden) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich jeder Back Office-Seite ausgeführt. | Wird verwendet, um die notwendigen JavaScript-Dateien (`16customers.js`, `17customersview.js` usw.) in das Back Office einzubinden, insbesondere wenn der `AdminCustomers`-Controller aktiv ist. Dies stellt sicher, dass die Schaltfläche „Als Kunde anmelden“ zur Kundenliste hinzugefügt wird. |
| `displayAdminCustomers` | Wird auf der `AdminCustomers`-Controller-Seite ausgeführt. | Dieser Hook ist speziell für Module konzipiert, um Inhalte oder Aktionen zur Kundenliste hinzuzufügen. Das Modul könnte diesen Hook verwenden, um ein kleines Template zu rendern oder direkt JavaScript einzufügen, um die Schaltfläche hinzuzufügen. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Back Office-Controller seine Medien (JS/CSS) einstellt. | Ein robusterer Hook zum bedingten Hinzufügen von JS/CSS basierend auf dem aktiven Controller. Das Modul würde diesen verwenden, um seine spezifischen JS-Dateien nur auf `AdminCustomers`- oder `AdminOrders`-Seiten zu laden. |
| `displayAdminOrder` | Wird auf der `AdminOrders`-Controller-Seite ausgeführt. | Wenn das Modul eine Schaltfläche „Als Kunde anmelden“ zur Bestellansicht hinzufügt (wie von `176orders.js`, `177orders.js` vorgeschlagen), würde dieser Hook verwendet, um das notwendige JavaScript oder den Schaltflächen-HTML einzufügen. |
| `displayAdminCarts` | Wird auf der `AdminCarts`-Controller-Seite ausgeführt. | Wenn das Modul eine Schaltfläche „Als Kunde anmelden“ zur Warenkorbansicht hinzufügt (wie von `17carts.js` vorgeschlagen), würde dieser Hook verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Als Kunde anmelden“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.
