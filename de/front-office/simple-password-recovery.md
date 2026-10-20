---
title: "Einfache Passwortwiederherstellung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Einfache Passwortwiederherstellung“ von MyPresta.eu."
sidebar:
  label: "Einfache Passwortwiederherstellung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Simple password recovery auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/simple-password-recovery.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/simple-password-recovery/)
>
> ---


# Einfache Passwortwiederherstellung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Das Modul „Einfache Passwortwiederherstellung“ ist weitgehend als Plug-and-Play konzipiert und ersetzt den standardmäßigen PrestaShop-Passwortwiederherstellungsablauf mit minimalem Konfigurationsaufwand.

Wenn Sie zu **Module > Modul-Manager** navigieren und neben „Einfache Passwortwiederherstellung“ auf „Konfigurieren“ klicken, finden Sie in der Regel eine unkomplizierte Konfigurationsoberfläche.

**Was diese Einstellung bewirkt:** Dieser Bildschirm ermöglicht es Ihnen, die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren und möglicherweise kleinere Verhaltensweisen anzupassen. Der Hauptzweck ist die Aktivierung des vereinfachten Passwortwiederherstellungsprozesses.

**Auswirkung der Änderung dieser Einstellung:**

- **Wenn aktiviert:** Das Modul übernimmt den standardmäßigen PrestaShop-Passwortwiederherstellungsmechanismus. Wenn ein Kunde eine Passwortzurücksetzung anfordert, erhält er eine E-Mail mit einem einzigartigen, sicheren Link, der ihn zu einer dedizierten Seite führt, um sein neues Passwort festzulegen. Dies vereinfacht die Benutzererfahrung erheblich.
- **Wenn deaktiviert:** Die Funktionalität des Moduls wird deaktiviert. Ihr PrestaShop-Shop kehrt zu seinem standardmäßigen Passwortwiederherstellungsprozess zurück, der möglicherweise mehr Schritte oder andere Verifizierungsmethoden für den Kunden beinhaltet.

**Empfohlener Wert:** **Aktiviert (JA)**. Der Hauptvorteil dieses Moduls besteht darin, den Passwortwiederherstellungsprozess zu vereinfachen. Wenn es aktiviert bleibt, profitieren Ihre Kunden von dieser verbesserten Erfahrung.

**Händlerszenario / Beispiel:**
Sie haben bemerkt, dass Kunden häufig den Support kontaktieren, weil sie Schwierigkeiten mit der standardmäßigen Passwortwiederherstellung haben. Durch die Aktivierung dieses Moduls bieten Sie einen direkten Ein-Klick-Link in der E-Mail, der es ihnen ermöglicht, sofort ein neues Passwort festzulegen. Dies reduziert Verwirrung und bringt sie schneller zum Einkaufen zurück.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Modulstatus (Aktivieren/Deaktivieren) | Aktiviert | Aktiviert oder deaktiviert den vereinfachten Passwortwiederherstellungsprozess. Wenn aktiviert, erhalten Kunden einen direkten Link zum Festlegen eines neuen Passworts. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten die E-Mails zur Passwortzurücksetzung nicht.**
A:

- **Spam-Ordner überprüfen:** Raten Sie Kunden, ihre Spam- oder Junk-Mail-Ordner zu überprüfen.
- **E-Mail-Konfiguration:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen unter **Erweiterte Einstellungen > E-Mail**. Stellen Sie sicher, dass Ihre SMTP-Einstellungen korrekt sind oder dass die PHP-Funktion `mail()` funktioniert.
- **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Module, die das Senden von E-Mails oder die Kundenkontoverwaltung beeinträchtigen könnten, um Konflikte auszuschließen.
- **Server-Logs:** Überprüfen Sie die Mail-Logs Ihres Servers auf Fehler im Zusammenhang mit ausgehenden E-Mails.

**F: Der Link zur Passwortzurücksetzung führt Kunden zu einer leeren Seite oder einem Fehler.**
A:

- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie Ihren Smarty-Cache, Browser-Cache und Modul-Cache.
- **URL-Umschreibung:** Stellen Sie sicher, dass die URL-Umschreibung in PrestaShop aktiviert ist (**Shop-Parameter > SEO & URLs**) und dass Ihre `.htaccess`-Datei korrekt konfiguriert ist.
- **Modul-Integrität:** Laden Sie die Moduldateien erneut per FTP hoch, um sicherzustellen, dass keine Dateien beschädigt oder fehlen.
- **Theme-Kompatibilität:** Obwohl selten, könnte ein stark angepasstes Theme JavaScript-Konflikte aufweisen. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler.

**F: Kann ich das Erscheinungsbild der neuen Passwortseite anpassen?**
A: Ja, das Modul verwendet Standard-PrestaShop-Templating. Das Erscheinungsbild wird hauptsächlich durch das CSS Ihres aktiven PrestaShop-Themes und das eigene CSS des Moduls (`spreset/views/css/spreset.css`) gesteuert. Entwickler können diese Stile im benutzerdefinierten CSS Ihres Themes überschreiben oder durch Ändern der Modul-Template-Dateien (`views/templates/front/password-change-form.tpl`, `views/templates/front/simple-reset-page.tpl`, `views/templates/front/simple-reset.tpl`).

**F: Funktioniert dieses Modul mit mehrsprachigen Shops?**
A: Ja, wie die meisten PrestaShop-Module sind die Textzeichenfolgen übersetzbar. Sie können die Phrasen des Moduls über **International > Übersetzungen** in Ihrem Back Office übersetzen, indem Sie „Übersetzungen installierter Module“ auswählen und dann „Einfache Passwortwiederherstellung“ finden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Einfache Passwortwiederherstellung“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Einfache Passwortwiederherstellung“ überschreibt den standardmäßigen PrestaShop-Passwortwiederherstellungsmechanismus, indem es benutzerdefinierte Front-Controller einführt, um die Token-Generierung, den E-Mail-Versand und den Prozess zur Festlegung des neuen Passworts zu handhaben. Es nutzt das MVC-Muster von PrestaShop mit dedizierten Controllern für verschiedene Phasen der Wiederherstellung. Die Hauptdatei des Moduls (`index.php`) handhabt die Installation, Deinstallation und das primäre Konfigurationsformular.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/changepass.php`
    - **Klassenname**: `SpresetChangepassModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller ist dafür verantwortlich, das Formular anzuzeigen, in dem ein Kunde sein neues Passwort festlegen kann, nachdem er auf den sicheren Zurücksetzungslink geklickt hat. Er validiert das in der URL bereitgestellte Token und verarbeitet die Übermittlung des neuen Passworts.
  - `controllers/front/index.php`
    - **Klassenname**: `SpresetIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als Fallback oder als allgemeiner Einstiegspunkt für die Front-Office-Funktionalität des Moduls, möglicherweise zur Weiterleitung oder zur Bearbeitung anfänglicher Anfragen im Zusammenhang mit dem Passwortzurücksetzungsprozess. In vielen Fällen könnte es ein Platzhalter sein oder für spezifisches Routing verwendet werden.
  - `controllers/front/simplereset.php`
    - **Klassenname**: `SpresetSimpleresetModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller ist der Kern des vereinfachten Zurücksetzungsprozesses. Er empfängt die anfängliche Passwortzurücksetzungsanfrage (z. B. vom Standard-PrestaShop-Formular „Passwort vergessen“), generiert das sichere Token, sendet die E-Mail mit dem eindeutigen Zurücksetzungslink und handhabt die anfängliche Validierung der E-Mail-Adresse des Kunden.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird direkt in der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen zu definieren, die `ObjectModel` oder andere PrestaShop-Kernklassen in einem dedizierten `classes/`-Verzeichnis erweitern. Seine Logik ist hauptsächlich in der Hauptmoduldatei und ihren Front-Controllern gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/spreset.js`
  - **Umfang**: Front-Office.
  - **Details**: Dieses Skript handhabt wahrscheinlich die clientseitige Validierung für das neue Passwortformular (z. B. Überprüfung, ob Passwörter übereinstimmen, Mindestlängenanforderungen) und möglicherweise AJAX-Übermittlungen für die Passwortänderung. Es könnte auch UI-Verbesserungen oder Interaktionen enthalten, die spezifisch für die Passwortzurücksetzungsseite sind. Entwickler sollten diese Datei auf spezifische Event-Listener (z. B. `submit` im Passwortformular) und benutzerdefinierte Funktionen überprüfen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/spreset.css`
  - **Umfang**: Front-Office-Kunden-Styling.
  - **Details**: Dieses Stylesheet bietet spezifisches Styling für die Front-Office-Komponenten des Moduls, hauptsächlich das Formular zur Eingabe des neuen Passworts und die zugehörigen Seiten. Es stellt sicher, dass die Passwortwiederherstellungsoberfläche ansprechend aussieht und sich einigermaßen gut in verschiedene Themes integriert. Entwickler können diese Datei überprüfen, um wichtige CSS-Klassenselektoren (z. B. `.spreset-form`, `.spreset-input`, `.spreset-button`) zu identifizieren, die in der benutzerdefinierten CSS-Datei ihres Themes überschrieben werden können, um dem Branding des Shops zu entsprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Front-Office-Templates (`views/templates/front/`)**:

  - `views/templates/front/password-change-form.tpl`
    - **Zweck**: Dieses Template rendert wahrscheinlich das eigentliche Formular, in dem der Kunde sein neues Passwort eingibt und bestätigt. Es würde Eingabefelder für „Neues Passwort“ und „Neues Passwort bestätigen“ sowie einen Absende-Button enthalten.
  - `views/templates/front/simple-reset-page.tpl`
    - **Zweck**: Dieses Template könnte als Haupt-Wrapper oder Layout für den vereinfachten Passwortzurücksetzungsprozess dienen, möglicherweise Nachrichten, Anweisungen und das Einbetten anderer Teil-Templates wie `password-change-form.tpl` enthalten.
  - `views/templates/front/simple-reset.tpl`
    - **Zweck**: Ähnlich wie `simple-reset-page.tpl` ist dieses Template Teil der Front-Office-Anzeige für den Passwortzurücksetzungsablauf. Es könnte für das anfängliche Formular „E-Mail eingeben“ oder zur Anzeige von Erfolgs-/Fehlermeldungen im Zusammenhang mit der Zurücksetzungsanfrage verwendet werden.
- **Modulspezifische Templates (`views/templates/`)**:

  - `views/templates/spreset.tpl`
    - **Zweck**: Dieses Template wird wahrscheinlich für die Hauptmodulkonfiguration im Back Office verwendet (wenn `getContent()` ein Template rendert) oder für einen generischen Anzeige-Hook, wenn das Modul eine einfache Ausgabe für einen Hook hat. Angesichts der Art des Moduls ist es wahrscheinlicher für die Back-Office-Konfiguration.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen. Es verwendet wahrscheinlich vorhandene PrestaShop-Tabellen (z. B. `ps_customer` für Kundendaten, `ps_configuration` für Moduleinstellungen) und generiert temporäre Tokens ohne dauerhafte Speicherung in einer dedizierten Tabelle. Tokens werden typischerweise in der Sitzung gespeichert oder über URL-Parameter mit kurzer Gültigkeitsdauer übergeben.
- **Registrierte Hooks-Tabelle**:
  Das Modul listet in den bereitgestellten Informationen keine explizit registrierten Hooks auf, aber basierend auf seiner Funktionalität würde es implizit mit dem Standard-PrestaShop-Passwortwiederherstellungsablauf interagieren, der oft durch die Hooks `displayCustomerAccountForm` oder `actionAuthenticationBefore` ausgelöst wird oder durch Überschreiben von PrestaShop-Kern-Controllern.
  Die Hauptdatei des Moduls (`index.php`) würde ihre Front-Controller registrieren, um spezifische Routen zu handhaben, wodurch sie effektiv in das URL-Routing-System „eingehängt“ wird, anstatt traditionelle `display`- oder `action`-Hooks für die visuelle Ausgabe zu verwenden.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Einfache Passwortwiederherstellung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, die optimale Leistung und Kompatibilität unserer Module mit den neuesten PrestaShop-Versionen sicherzustellen.
