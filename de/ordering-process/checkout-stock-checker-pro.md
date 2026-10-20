---
title: "Checkout stock checker PRO - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Checkout stock checker PRO von MyPresta.eu."
sidebar:
  label: "Checkout stock checker PRO"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Checkout stock checker PRO auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/checkout-stock-checker-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/checkout-stock-checker-pro/)
>
> ---


# Checkout stock checker PRO

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten modernen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf "Konfigurieren" zum Haupt- und einzigen Konfigurationsbildschirm für das Modul "Checkout stock checker PRO". Dieser Bildschirm ermöglicht es Ihnen, die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren.

#### **Modul aktivieren / deaktivieren**
-   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Bestandsprüfungsfunktion ein- oder auszuschalten.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Das Modul überprüft aktiv die Produktbestände, kurz bevor eine Bestellung aufgegeben wird. Wenn ein Artikel nicht vorrätig ist, wird der Kunde mit einer Benachrichtigung zum Warenkorb umgeleitet.
    -   *Wenn deaktiviert (NEIN):* Das Modul ist inaktiv. Bestandsprüfungen finden nicht statt, und Kunden könnten Bestellungen für nicht vorrätige Artikel aufgeben, wobei sie sich ausschließlich auf das Standard-Bestandsmanagementverhalten von PrestaShop verlassen (das normalerweise nur beim Hinzufügen zum Warenkorb prüft, nicht bei der endgültigen Bestellung).
-   **Empfohlener Wert:** **JA**. Um den vollen Nutzen des Moduls zu ziehen, sollte es immer aktiviert sein.
-   **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten beginnen, Bestellungen für nicht vorrätige Artikel zu verhindern. Sie würden dies auf "JA" setzen. Wenn Sie die Funktion vorübergehend für Wartungsarbeiten oder Tests deaktivieren müssen, würden Sie sie auf "NEIN" setzen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Modul-Konfigurationsseite | Modul aktivieren / deaktivieren | JA | Steuert, ob das Modul den Bestand aktiv vor der Bestellung prüft. Verhindert Bestellungen für nicht vorrätige Artikel, wenn aktiviert. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Das Modul ist aktiviert, aber Kunden geben immer noch Bestellungen für nicht vorrätige Artikel auf. Was ist falsch?**
A:
1.  **Cache leeren:** Versuchen Sie zuerst, Ihren PrestaShop-Cache zu leeren. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf "Cache leeren".
2.  **Modulstatus prüfen:** Überprüfen Sie nochmals, ob das Modul auf seiner Konfigurationsseite tatsächlich aktiviert ist.
3.  **Theme-Konflikte:** Einige stark angepasste Themes oder andere Module, die den Checkout ändern, könnten stören. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic) und testen Sie erneut. Wenn es funktioniert, liegt das Problem wahrscheinlich an einem Theme-Konflikt, und Sie müssen möglicherweise einen Entwickler hinzuziehen.
4.  **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre spezifische PrestaShop-Installation heruntergeladen haben.

**F: Meine Kunden werden zum Warenkorb umgeleitet, aber die Benachrichtigung wird nicht angezeigt oder ist schlecht formatiert.**
A:
1.  **Cache leeren:** Leeren Sie wie immer Ihren PrestaShop-Cache.
2.  **Theme-Styling:** Die Benachrichtigung verwendet Standard-PrestaShop-Alert-Klassen. Wenn Ihr Theme diese Stile stark angepasst oder entfernt hat, könnte die Nachricht unsichtbar oder falsch formatiert sein. Ein Webmaster kann den HTML- und CSS-Code überprüfen, um sicherzustellen, dass die Nachricht vorhanden und korrekt gestylt ist.
3.  **Moduldateien:** Stellen Sie sicher, dass alle Moduldateien korrekt hochgeladen wurden. Manchmal können unvollständige Uploads zu fehlenden Vorlagendateien für Benachrichtigungen führen.

**F: Funktioniert dieses Modul mit mehrsprachigen Shops?**
A: Ja, das Modul verwendet Standard-PrestaShop-Übersetzungsmechanismen. Die den Kunden angezeigten Benachrichtigungen können in alle in Ihrem Shop konfigurierten Sprachen übersetzt werden. Sie können diese Übersetzungen unter **International > Übersetzungen > Installierte Modulübersetzungen** verwalten.

**F: Wird dieses Modul meinen Checkout-Prozess verlangsamen?**
A: Die vom Modul durchgeführte Bestandsprüfung ist sehr schnell und fügt dem Checkout-Prozess typischerweise nur Millisekunden hinzu. Es handelt sich um eine direkte Datenbankabfrage für Lagerbestände, die hochoptimiert ist. Die Leistungsauswirkungen sind vernachlässigbar und werden durch die Vorteile der Verhinderung von Bestellungen für nicht vorrätige Artikel bei weitem aufgewogen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht
Das Modul "Checkout stock checker PRO" (`csc`) ist so konzipiert, dass es sich nahtlos in den PrestaShop-Checkout-Fluss integriert. Es arbeitet hauptsächlich durch das Einhaken in die letzte Phase des Bestellvorgangs und nutzt einen Front-Controller, um eine AJAX-basierte Bestandsprüfung durchzuführen. Dieser Ansatz stellt sicher, dass die Bestandsprüfung in Echtzeit durchgeführt wird, kurz bevor die Bestellung in die Datenbank geschrieben wird, wodurch Race Conditions vermieden werden, bei denen sich der Bestand zwischen der Warenkorbprüfung und der endgültigen Bestellbestätigung ändern könnte. Das Modul folgt dem MVC-Muster von PrestaShop für seine Front-End-Interaktion und Konfiguration.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller
-   `csc/controllers/front/AjaxCheck.php`
    *   **Klassenname & Elternklasse:** `CscAjaxCheckModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller ist der Kern der Modulfunktionalität. Er ist für die Verarbeitung der AJAX-Anfrage verantwortlich, die von der Front-Office-Checkout-Seite initiiert wird. Nach Empfang der Anfrage durchläuft er die Produkte im Warenkorb des Kunden, überprüft deren aktuelle Lagerbestände mit den angeforderten Mengen und gibt eine JSON-Antwort zurück, die angibt, ob alle Artikel auf Lager sind oder welche Artikel nicht auf Lager sind. Er rendert keine vollständige Seite, sondern liefert Daten, auf die das JavaScript reagieren kann.
-   `csc/controllers/front/index.php`
    *   **Klassenname & Elternklasse:** Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in PrestaShop-Modulverzeichnissen enthalten ist, um direkte Verzeichnisauflistungen zu verhindern. Sie enthält keine Klasse oder spezifische Logik.

#### Back-Office-Admin-Controller
Das Modul verwendet keine benutzerdefinierten Admin-Controller. Die Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)
Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierte Geschäftslogikklassen im Verzeichnis `classes/`. Die gesamte Kernlogik ist in der Hauptmoduldatei (`ajax_csc.php`) und dem `AjaxCheck`-Front-Controller gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)
-   `csc/views/js/csc.js`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Diese JavaScript-Datei ist für die Initiierung der AJAX-Bestandsprüfung verantwortlich. Sie hakt sich typischerweise in das Klickereignis der finalen Schaltfläche "Bestellung aufgeben" (oder einer entsprechenden Formularübermittlung) auf der Checkout-Seite ein. Bevor die Formularübermittlung fortgesetzt werden kann, sendet sie eine AJAX-Anfrage an den `AjaxCheck`-Front-Controller. Basierend auf der JSON-Antwort erlaubt sie entweder den Abschluss des Checkouts oder verhindert die Übermittlung, leitet den Benutzer zurück zum Warenkorb und zeigt die entsprechende Fehlermeldung an. Sie verwendet Standard-jQuery oder PrestaShops native JavaScript-Ereignisse (`prestashop.on`), um dies zu erreichen.

### 4.5 CSS-Stylesheets (`views/css/`)
-   `csc/views/css/csc.css`
    *   **Geltungsbereich:** Front-Office-Kunden-Styling.
    *   **Details:** Dieses Stylesheet bietet grundlegendes Styling für die Benachrichtigungen, die auf der Warenkorbseite angezeigt werden, wenn Produkte als nicht vorrätig befunden werden. Es zielt wahrscheinlich auf spezifische CSS-Klassen ab, die den Benachrichtigungs-`div`-Elementen hinzugefügt wurden.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler können die HTML-Ausgabe der Benachrichtigung überprüfen, um die spezifischen Klassen (z.B. `.alert-danger`, `.csc-notification` usw.) zu identifizieren und sie in der `custom.css` oder `theme.css` ihres Themes zu überschreiben, um sie an das Branding ihres Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, was darauf hindeutet, dass die primäre Interaktion des Moduls über AJAX und Umleitung erfolgt, wobei Benachrichtigungen direkt vom `AjaxCheck`-Controller oder dem Hauptmodul gerendert werden.
-   **Admin-Templates (`views/templates/admin/`)**: Keine, da die Konfiguration über `getContent()` erfolgt.
-   **Front-Office-Templates (`views/templates/front/`)**:
    *   `csc/lib/searchTool/views/scripts.tpl`
        *   **Zweck:** Dieses Template enthält wahrscheinlich die JavaScript-Datei `csc.js` und übergibt möglicherweise Konfigurationsvariablen vom Backend des Moduls an das Frontend-JavaScript. Es ist wahrscheinlich in `displayHeader` oder `displayFooter` eingehängt, um sicherzustellen, dass das JS auf relevanten Seiten (z.B. Checkout) geladen wird.
    *   `csc/views/errors.tpl`
        *   **Zweck:** Dieses Template wird gerendert, wenn die Bestandsprüfung fehlschlägt (d.h. Artikel sind nicht vorrätig). Es zeigt die Fehlermeldung an und listet die spezifischen Produkte auf, die nicht mehr verfügbar sind. Dies ist das Template, das für die sichtbare Benachrichtigung auf der Warenkorbseite nach der Umleitung verantwortlich ist.
    *   `csc/views/no-errors.tpl`
        *   **Zweck:** Dieses Template ist wahrscheinlich ein Platzhalter oder ein Template, das gerendert würde, wenn keine Fehler vorliegen, aber die Hauptfunktion des Moduls darin besteht, Fehler anzuzeigen. Es könnte für interne Logik verwendet werden oder einfach ein leeres Template sein.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es verlässt sich vollständig auf die vorhandenen PrestaShop-Tabellen `ps_product`, `ps_stock_available` und `ps_configuration`. Konfigurationseinstellungen (wie der Aktivieren/Deaktivieren-Schalter) werden in `ps_configuration` unter Schlüsseln wie `CSC_ENABLED` gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich jeder Seite. | Wird wahrscheinlich verwendet, um das `csc.js`-Skript und das `csc.css`-Stylesheet einzubinden, um sicherzustellen, dass sie auf den Checkout-Seiten verfügbar sind. |
| `displayFooter` | Rendert Inhalte am Ende des `<body>`-Bereichs jeder Seite. | Alternative Hook zu `displayHeader` zum Einbinden von JS/CSS, oft aus Performancegründen bevorzugt. |
| `displayProductButtons` | Rendert Inhalte in der Nähe von Produktschaltflächen (z.B. zum Warenkorb hinzufügen). | *Nicht explizit für die Kernfunktionalität verwendet, könnte aber für zukünftige Funktionen oder kleinere UI-Elemente sein.* |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte des Shops. | *Nicht explizit für die Kernfunktionalität verwendet, könnte aber für zukünftige Funktionen oder kleinere UI-Elemente sein.* |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (JS/CSS) setzt. | Ein gezielterer Hook zum Hinzufügen von JS/CSS speziell zu relevanten Front-Controllern (z.B. Checkout-Seiten). |
| `actionBeforeUpdateQuantity` | Wird ausgeführt, bevor eine Produktmenge im Warenkorb aktualisiert wird. | *Nicht explizit für die Kernfunktionalität verwendet, könnte aber für zukünftige Funktionen oder kleinere UI-Elemente sein.* |
| `actionCartSave` | Wird ausgeführt, nachdem ein Warenkorb gespeichert wurde. | *Nicht explizit für die Kernfunktionalität verwendet, könnte aber für zukünftige Funktionen oder kleinere UI-Elemente sein.* |
| `actionValidateOrder` | Wird ausgeführt, nachdem eine Bestellung validiert wurde. | *Entscheidend für die Modullogik.* Dies ist der Punkt, an dem das Modul eingreift, um die endgültige Bestandsprüfung durchzuführen, *bevor* die Bestellung vollständig bestätigt wird. Das JavaScript des Moduls verhindert wahrscheinlich die Formularübermittlung, die diesen Hook auslöst, wenn Bestandsprobleme festgestellt werden. |

*Hinweis: Der primäre Mechanismus des Moduls zur Bestandsprüfung erfolgt über seinen `AjaxCheck`-Front-Controller, der durch JavaScript auf der Checkout-Seite ausgelöst wird, anstatt sich ausschließlich auf die nativen Hooks von PrestaShop für die Bestandsprüfung selbst zu verlassen. Hooks werden hauptsächlich zum Laden von Assets und möglicherweise zum Anzeigen von Benachrichtigungen verwendet.*

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Checkout stock checker PRO" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
