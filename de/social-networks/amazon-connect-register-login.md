---
title: "Amazon connect (registrieren + anmelden) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Amazon connect (registrieren + anmelden) von MyPresta.eu."
sidebar:
  label: "Amazon connect (registrieren + anmelden) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Amazon connect (register + login) auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/amazon-connect-register-login.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/amazon-connect-register-login/)
>
> ---


# Amazon connect (registrieren + anmelden)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine sichere API-Kommunikation erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Amazon-Login-Modul, auf dem Sie Ihren PrestaShop-Shop mit Ihrem Amazon Developer-Konto verknüpfen.

- **aml\_ClientID (Amazon Client ID)**
  - **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Kennung, die von Amazon bereitgestellt wird, wenn Sie Ihre Anwendung (Ihren PrestaShop-Shop) beim Login with Amazon-Dienst registrieren. Sie teilt Amazon mit, welche Anwendung die Benutzerauthentifizierung anfordert.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Ihr „Login with Amazon“-Button funktioniert korrekt und ermöglicht Kunden die Authentifizierung über ihr Amazon-Konto.
    - *Bei falscher oder leerer Eingabe:* Der „Login with Amazon“-Button funktioniert nicht, oder Kunden erhalten eine Fehlermeldung, wenn sie versuchen, ihn zu verwenden.
  - **Empfohlener Wert:** Die Client ID, die Sie von Ihrer Amazon Developer Console erhalten haben. Dieses Feld darf für die Funktion des Moduls nicht leer bleiben.
  - **Händlerszenario / Beispiel:** Sie haben Ihren PrestaShop-Shop als Anwendung in der Amazon Developer Console registriert. Amazon stellt Ihnen eine „Client ID“ zur Verfügung (z.B. `amzn1.oauth-client.xxxxxxxxxxxxxxxxxxxxxxxxxxxx`). Sie müssen diese genaue ID in dieses Feld kopieren und einfügen.
- **aml\_ClientSecret (Amazon Client Secret)**
  - **Was diese Einstellung bewirkt:** Dies ist ein vertraulicher Schlüssel, der ebenfalls von Amazon bereitgestellt wird und in Verbindung mit der Client ID verwendet wird, um Ihre Anwendung sicher bei den Amazon-Servern zu authentifizieren. Er stellt sicher, dass nur Ihre legitime Anwendung Benutzerdaten anfordern kann.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Ihr Modul kann sicher mit der Amazon-API kommunizieren, um Benutzeridentitäten zu überprüfen.
    - *Bei falscher oder leerer Eingabe:* Der Authentifizierungsprozess schlägt fehl, da Ihr Shop sich nicht sicher bei Amazon identifizieren kann.
  - **Empfohlener Wert:** Das Client Secret, das Sie von Ihrer Amazon Developer Console erhalten haben. Dieses Feld darf für die Funktion des Moduls nicht leer bleiben.
  - **Händlerszenario / Beispiel:** Neben der Client ID gibt Ihnen Amazon auch ein „Client Secret“ (z.B. `yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy`). Dieses Geheimnis muss vertraulich behandelt und hier genau eingegeben werden.
- **aml\_RedirectURI (Amazon Redirect URI)**
  - **Was diese Einstellung bewirkt:** Dies ist die URL in Ihrem PrestaShop-Shop, zu der Amazon den Browser des Benutzers *nachdem* dieser sich erfolgreich auf der Amazon-Website angemeldet oder Ihre Anwendung autorisiert hat, weiterleitet. Sie ist entscheidend für den sicheren Ablauf des Authentifizierungsprozesses.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Bei korrekter Konfiguration auf beiden Seiten (Modul und Amazon Developer Console):* Benutzer werden nach dem Amazon-Login nahtlos zu Ihrem Shop zurückgeleitet.
    - *Bei falscher Eingabe:* Benutzer erhalten nach dem Login mit Amazon eine Fehlermeldung, oder sie werden nicht korrekt zu Ihrem Shop zurückgeleitet. Diese URI muss auch in Ihren Amazon Developer Console-Einstellungen für Ihre Anwendung registriert sein.
  - **Empfohlener Wert:** Dies sollte typischerweise automatisch vom Modul generiert werden oder eine spezifische URL wie `https://ihrshop.com/module/amlogin/ajax_amlogin` sein (überprüfen Sie den genauen Pfad, der vom Modul oder der Amazon-Dokumentation bereitgestellt wird). Stellen Sie sicher, dass er mit der URI übereinstimmt, die Sie in Ihrer Amazon Developer Console registriert haben.
  - **Händlerszenario / Beispiel:** Wenn Sie Ihre Anwendung in der Amazon Developer Console einrichten, werden Sie nach „Zulässigen Rückgabe-URLs“ gefragt. Sie müssen die genaue URL eingeben, die dieses Modul für die Weiterleitung verwendet (z.B. `https://www.ihrshop.com/module/amlogin/ajax_amlogin`).
- **Amazon Login Button im Header anzeigen**
  - **Was diese Einstellung bewirkt:** Steuert, ob der „Login with Amazon“-Button im Header-Bereich Ihres Shops angezeigt wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist im Header sichtbar und bietet sofortigen Zugriff auf den Amazon-Login.
    - *Wenn deaktiviert:* Der Button wird nicht im Header angezeigt.
  - **Empfohlener Wert:** JA, für maximale Sichtbarkeit und einfachen Zugang.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden die Amazon-Login-Option sehen, sobald sie auf Ihrer Website landen, also aktivieren Sie diese.
- **Amazon Login Button in der linken Spalte anzeigen**
  - **Was diese Einstellung bewirkt:** Steuert, ob der „Login with Amazon“-Button in der linken Seitenleiste Ihres Shops angezeigt wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist in der linken Spalte sichtbar, oft neben anderen Navigations- oder Kontoblöcken.
    - *Wenn deaktiviert:* Der Button wird nicht in der linken Spalte angezeigt.
  - **Empfohlener Wert:** JA, wenn Ihr Theme eine linke Spalte verwendet und Sie eine dauerhafte Sichtbarkeit wünschen.
  - **Händlerszenario / Beispiel:** Ihr Shop hat eine prominente linke Spalte, und Sie möchten die Amazon-Login-Option dort anbieten, während Kunden Kategorien durchsuchen.
- **Amazon Login Button in der rechten Spalte anzeigen**
  - **Was diese Einstellung bewirkt:** Steuert, ob der „Login with Amazon“-Button in der rechten Seitenleiste Ihres Shops angezeigt wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist in der rechten Spalte sichtbar.
    - *Wenn deaktiviert:* Der Button wird nicht in der rechten Spalte angezeigt.
  - **Empfohlener Wert:** JA, wenn Ihr Theme eine rechte Spalte verwendet und Sie eine dauerhafte Sichtbarkeit wünschen.
  - **Händlerszenario / Beispiel:** Ähnlich wie bei der linken Spalte, wenn Ihr Theme eine rechte Spalte verwendet, könnten Sie den Button dort zur Sichtbarkeit platzieren.
- **Amazon Login Button auf der Produktseite anzeigen**
  - **Was diese Einstellung bewirkt:** Steuert, ob der „Login with Amazon“-Button auf einzelnen Produktdetailseiten angezeigt wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button wird auf Produktseiten angezeigt, möglicherweise in der Nähe des „In den Warenkorb“-Buttons oder der Produktbeschreibung.
    - *Wenn deaktiviert:* Der Button wird nicht auf Produktseiten angezeigt.
  - **Empfohlener Wert:** JA, da dies eine sofortige Anmeldung oder Registrierung vor dem Hinzufügen zum Warenkorb fördern kann.
  - **Händlerszenario / Beispiel:** Ein Kunde betrachtet ein Produkt und entscheidet sich, es zu kaufen. Der Amazon-Login-Button ermöglicht es ihm, sich schnell anzumelden oder ein Konto zu erstellen, bevor er zur Kasse geht.
- **Amazon Login Button im Footer anzeigen**
  - **Was diese Einstellung bewirkt:** Steuert, ob der „Login with Amazon“-Button im Footer-Bereich Ihres Shops angezeigt wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist im Footer sichtbar und bietet einen alternativen Anmeldepunkt.
    - *Wenn deaktiviert:* Der Button wird nicht im Footer angezeigt.
  - **Empfohlener Wert:** NEIN, es sei denn, Sie haben einen spezifischen Designgrund. Andere Standorte bieten eine bessere Sichtbarkeit.
  - **Händlerszenario / Beispiel:** Sie möchten die Amazon-Login-Option anbieten, bevorzugen aber, dass sie nicht zu prominent ist, also platzieren Sie sie im Footer.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | `aml_ClientID` | Ihre Amazon Client ID | Eindeutige Kennung Ihrer Anwendung bei Amazon. **Für die Funktionalität erforderlich.** |
| Modulkonfigurationsseite | `aml_ClientSecret` | Ihr Amazon Client Secret | Vertraulicher Schlüssel für die sichere Authentifizierung bei Amazon. **Für die Funktionalität erforderlich.** |
| Modulkonfigurationsseite | `aml_RedirectURI` | Automatisch generiert / Spezifische URL | URL, zu der Amazon Benutzer nach dem Login weiterleitet. **Muss mit der Amazon Developer Console übereinstimmen.** |
| Modulkonfigurationsseite | Im Header anzeigen | JA | Zeigt den Button im Header des Shops an. |
| Modulkonfigurationsseite | In der linken Spalte anzeigen | JA | Zeigt den Button in der linken Seitenleiste an. |
| Modulkonfigurationsseite | In der rechten Spalte anzeigen | JA | Zeigt den Button in der rechten Seitenleiste an. |
| Modulkonfigurationsseite | Auf der Produktseite anzeigen | JA | Zeigt den Button auf einzelnen Produktseiten an. |
| Modulkonfigurationsseite | Im Footer anzeigen | NEIN | Zeigt den Button im Footer des Shops an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Amazon-Login-Button erscheint, aber nichts passiert, wenn ich darauf klicke, oder ich erhalte eine Fehlermeldung.**
A: Dies deutet normalerweise auf ein Problem mit Ihrer `aml_ClientID`, `aml_ClientSecret` oder `aml_RedirectURI` hin.
- **Prüfung 1:** Überprüfen Sie nochmals, ob Sie die Client ID und das Client Secret exakt aus Ihrer Amazon Developer Console in die Konfiguration des Moduls kopiert haben. Schon ein einziger Zeichenfehler führt zum Scheitern.
- **Prüfung 2:** Vergewissern Sie sich, dass die `aml_RedirectURI` in der Modulkonfiguration exakt mit einer der „Zulässigen Rückgabe-URLs“ übereinstimmt, die Sie in Ihrer Amazon Developer Console für Ihre Anwendung registriert haben. Achten Sie auf `http` vs. `https` und nachgestellte Schrägstriche.
- **Prüfung 3:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren) und Ihren Browser-Cache.

**F: Meine Kunden werden zu Amazon weitergeleitet, erhalten dann aber einen Fehler oder werden nicht zu meinem Shop zurückgeschickt.**
A: Dies ist fast sicher eine `aml_RedirectURI`-Fehlübereinstimmung. Gehen Sie zu Ihrer Amazon Developer Console, suchen Sie Ihre Anwendung und stellen Sie sicher, dass die Liste der „Zulässigen Rückgabe-URLs“ die *exakte* URL enthält, die Ihr PrestaShop-Modul verwenden soll. Es muss eine exakte Übereinstimmung sein, einschließlich `http/https` und aller Unterverzeichnisse.

**F: Der Amazon-Login-Button erscheint nicht an den von mir aktivierten Stellen.**
A:
- **Prüfung 1:** Stellen Sie sicher, dass das Modul im Back Office aktiviert und korrekt konfiguriert ist.
- **Prüfung 2:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren). Manchmal spiegeln sich Vorlagenänderungen nicht sofort wider.
- **Prüfung 3:** Ihr Theme könnte die Standard-PrestaShop-Hooks überschreiben. Wenn der Button immer noch nicht erscheint, benötigen Sie möglicherweise einen Webentwickler, um den Hook-Aufruf des Moduls manuell in die `.tpl`-Dateien Ihres Themes einzufügen (siehe Abschnitt 7.6 für relevante Templates).

**F: Funktioniert dieses Modul mit mehrsprachigen Shops?**
A: Ja, das Modul sollte die Mehrsprachigkeitsfunktionen von PrestaShop für alle angezeigten Texte übernehmen. Der Amazon-Login-Prozess selbst wird von Amazon gehandhabt und passt sich typischerweise an die Spracheinstellungen des Amazon-Kontos des Benutzers an.

**F: Kann ich das Aussehen des Amazon-Login-Buttons anpassen?**
A: Das Modul verwendet Standard-Amazon-Login-Button-Assets. Obwohl Sie das Kern-Design des Amazon-Buttons (gemäß den Markenrichtlinien von Amazon) nicht ändern können, können Sie benutzerdefiniertes CSS (siehe Abschnitt 7.5) verwenden, um dessen Platzierung, Ränder oder den umgebenden Container besser an Ihr Theme anzupassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

### 4.1 Architekturübersicht

Das Modul „Amazon connect (registrieren + anmelden)“ integriert den Login with Amazon (LWA)-Dienst von Amazon in PrestaShop. Es fungiert hauptsächlich als Standard-PrestaShop-Modul, das Hooks nutzt, um den Login-Button an verschiedenen Front-Office-Standorten anzuzeigen. Die Kernlogik für die Handhabung des Amazon OAuth 2.0-Flows (Weiterleitung zu Amazon, Empfang des Autorisierungscodes, Austausch gegen ein Zugriffstoken und Abrufen von Benutzerprofildaten) ist in der Hauptmoduldatei und ihrem zugehörigen AJAX-Controller gekapselt. Die von Amazon erhaltenen Benutzerdaten werden dann verwendet, um einen bestehenden PrestaShop-Kunden anzumelden oder einen neuen zu erstellen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front- oder Admin-Controller im Verzeichnis `controllers/`. Alle Front-Office-AJAX-Anfragen und die Hauptmodulkonfiguration werden von der Hauptmoduldatei (`amlogin/ajax_amlogin.php`) verarbeitet, die als Pseudo-Controller für AJAX-Aktionen fungiert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält keine benutzerdefinierten Klassen oder Modelle in einem dedizierten `classes/`-Verzeichnis. Die Kernlogik befindet sich in der Hauptmoduldatei `amlogin/ajax_amlogin.php`.

### 4.4 JavaScript-Assets (`views/js/`)

- `amlogin/js/amlogin.js`
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dieses Skript ist für die Initialisierung des Amazon Login SDK, die Behandlung der Klickereignisse auf dem Amazon Login-Button und die Verwaltung des OAuth 2.0-Flows verantwortlich. Es verwendet wahrscheinlich die Methode `amazon.Login.authorize`, um den Anmeldevorgang zu initiieren und den Callback von Amazon zu verarbeiten. Anschließend wird ein AJAX-Aufruf an das Backend des Moduls gesendet, um die Amazon-Benutzerdaten zu verarbeiten und den Kunden in PrestaShop anzumelden. Es kann auch die Benutzeroberfläche aktualisieren (z.B. den angemeldeten Status anzeigen) nach erfolgreicher Authentifizierung.

### 4.5 CSS-Stylesheets (`views/css/`)

- `amlogin/css.css`
  - **Umfang:** Front-Office.
  - **Beschreibung:** Allgemeine Stile für den Amazon Login-Button und alle zugehörigen UI-Elemente. Dies kann grundlegende Layout-, Polster- oder Randeinstellungen enthalten.
- `amlogin/css/amlogin.css`
  - **Umfang:** Front-Office.
  - **Beschreibung:** Spezifische Stile für den Amazon Login-Button, möglicherweise einschließlich responsiver Anpassungen oder themenspezifischer Überschreibungen für PrestaShop 1.6.
- `amlogin/css/amlogin17.css`
  - **Umfang:** Front-Office.
  - **Beschreibung:** Spezifische Stile, die auf PrestaShop 1.7-Themes zugeschnitten sind und potenzielle Unterschiede in den Standard-Theme-Strukturen oder CSS-Frameworks (z.B. Bootstrap 4 vs. Bootstrap 3) berücksichtigen. Entwickler können diese Stile in der `custom.css` ihres Themes oder durch Erstellen eines Child-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet eine umfassende Reihe von Smarty-Templates, um den Amazon-Login-Button über verschiedene PrestaShop-Hooks hinweg zu rendern.

- **Hook-Templates (`views/templates/hook/`)**:
  - `amlogin/ajax-amlogin.tpl`: Wahrscheinlich für AJAX-Antworten oder dynamische Inhalte im Zusammenhang mit dem Amazon-Login-Prozess verwendet.
  - `amlogin/amlogin.tpl`: Ein generisches Template für den Amazon-Login-Button, oft von anderen Hook-Templates eingebunden.
  - `amlogin/createAccountForm.tpl`: Rendert den Amazon-Login-Button innerhalb des Standard-PrestaShop-Kontoerstellungsformulars.
  - `amlogin/createAccountTop.tpl`: Rendert den Amazon-Login-Button oben auf der Kontoerstellungsseite.
  - `amlogin/dashboardZoneOne.tpl`: Rendert den Amazon-Login-Button in der ersten Zone des Kunden-Dashboards (z.B. `displayCustomerAccount`).
  - `amlogin/displayCustomerLoginFormAfter.tpl`: Rendert den Amazon-Login-Button nach dem Standard-Kundenanmeldeformular.
  - `amlogin/displayNav.tpl`: Rendert den Amazon-Login-Button in der Navigationsleiste (z.B. `displayNav`-Hook).
  - `amlogin/displayPopUpLogin.tpl`: Rendert den Amazon-Login-Button innerhalb eines Pop-up-Login-Modals (falls vom Theme oder Modul implementiert).
  - `amlogin/footer.tpl`: Rendert den Amazon-Login-Button im Footer des Shops (`displayFooter`-Hook).
  - `amlogin/header.tpl`: Rendert den Amazon-Login-Button im Header des Shops (`displayHeader`-Hook).
  - `amlogin/home.tpl`: Rendert den Amazon-Login-Button auf der Startseite (`displayHome`-Hook).
  - `amlogin/leftcolumn.tpl`: Rendert den Amazon-Login-Button in der linken Seitenleiste (`displayLeftColumn`-Hook).
  - `amlogin/rightcolumn.tpl`: Rendert den Amazon-Login-Button in der rechten Seitenleiste (`displayRightColumn`-Hook).
  - `amlogin/shoppingCart.tpl`: Rendert den Amazon-Login-Button innerhalb der Warenkorbzusammenfassung.
  - `amlogin/shoppingCartExtra.tpl`: Rendert den Amazon-Login-Button in einem zusätzlichen Bereich des Warenkorbs.
  - `amlogin/top.tpl`: Rendert den Amazon-Login-Button im oberen Bereich der Seite (z.B. `displayTop`-Hook).
  - `amlogin/topColumn.tpl`: Rendert den Amazon-Login-Button im oberen Spaltenbereich (`displayTopColumn`-Hook).

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**: Dieses Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen. Konfigurationseinstellungen (Client ID, Client Secret usw.) werden in der Tabelle `ps_configuration` unter Schlüsseln wie `AML_CLIENT_ID`, `AML_CLIENT_SECRET`, `AML_REDIRECT_URI` und `AML_DISPLAY_HEADER` usw. gespeichert.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich der Seite. | Fügt CSS, JS und möglicherweise den Amazon-Login-Button ein. |
  | `displayNav` | In der oberen Navigationsleiste. | Zeigt den Amazon-Login-Button in der Navigation an. |
  | `displayLeftColumn` | In der linken Seitenleiste. | Zeigt den Amazon-Login-Button in der linken Spalte an. |
  | `displayRightColumn` | In der rechten Seitenleiste. | Zeigt den Amazon-Login-Button in der rechten Spalte an. |
  | `displayProductButtons` (oder ähnlich) | Auf der Produktseite, in der Nähe der Aktionsbuttons. | Zeigt den Amazon-Login-Button auf Produktseiten an. |
  | `displayFooter` | Im Footer des Shops. | Zeigt den Amazon-Login-Button im Footer an. |
  | `displayCustomerAccount` | Im Kundenkonto-Dashboard. | Zeigt den Amazon-Login-Button im Kundenkontobereich an. |
  | `displayCustomerLoginFormAfter` | Nach dem Standard-Login-Formular. | Integriert den Amazon-Login-Button in die Login-Seite. |
  | `displayBeforeBodyClosingTag` | Vor dem `</body>`-Tag. | Kann JavaScript für das Amazon SDK oder Pop-ups einfügen. |
  | `displayShoppingCart` | Auf der Warenkorbzusammenfassungsseite. | Zeigt den Amazon-Login-Button im Warenkorb an. |
  | `displayShoppingCartExtra` | Zusätzlicher Inhaltsbereich im Warenkorb. | Zeigt den Amazon-Login-Button in einem zusätzlichen Warenkorbbereich an. |
  | `displayTop` | Oben auf der Seite, über dem Header. | Zeigt den Amazon-Login-Button im obersten Bereich an. |
  | `displayTopColumn` | Im Hauptbereich der oberen Spalte. | Zeigt den Amazon-Login-Button in der oberen Spalte an. |
  | `displayHome` | Auf der Startseite des Shops. | Zeigt den Amazon-Login-Button auf der Startseite an. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Modul „Amazon connect (registrieren + anmelden)“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul perfekt funktioniert und sich nahtlos in Ihren PrestaShop-Shop integriert.
