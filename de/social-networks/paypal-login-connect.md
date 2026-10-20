---
title: "PayPal Login Connect – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul PayPal Login Connect von MyPresta.eu."
sidebar:
  label: "PayPal Login Connect – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul PayPal login connect auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/paypal-login-connect.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/paypal-login-connect/)
>
> ---


# PayPal Login Connect

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „PayPal Login Connect“, um auf dessen Einstellungen zuzugreifen.

#### **PayPal API-Zugangsdaten**

Diese Einstellungen verbinden Ihren Store mit Ihrem PayPal-Entwicklerkonto, sodass das Modul Benutzer sicher authentifizieren kann.

- **Was diese Einstellung bewirkt:** Diese Felder erfordern Ihre eindeutige Client-ID und Ihr Client-Secret, die Sie von Ihrem PayPal-Entwicklerkonto erhalten haben. Diese Zugangsdaten sind entscheidend, damit Ihr Store mit dem PayPal-Login-Dienst kommunizieren kann.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Der „Mit PayPal anmelden“-Button funktioniert und ermöglicht Kunden die Anmeldung.
  - *Bei falscher oder leerer Eingabe:* Das Modul kann keine Verbindung zu PayPal herstellen, und die Anmeldefunktion schlägt fehl oder wird nicht angezeigt.
- **Empfohlener Wert:** Geben Sie die exakte Client-ID und das Client-Secret ein, die von PayPal bereitgestellt wurden.
- **Händlerszenario / Beispiel:** Sie haben ein PayPal-Entwicklerkonto erstellt und eine „Mit PayPal anmelden“-App eingerichtet. PayPal stellt Ihnen eine Client-ID (eine lange Zeichenfolge) und ein Client-Secret (eine weitere lange, sichere Zeichenfolge) zur Verfügung. Sie kopieren diese und fügen sie in die entsprechenden Felder hier ein.

#### **PayPal-Login aktivieren**

Dies ist der Hauptschalter für die Funktionalität des Moduls.

- **Was diese Einstellung bewirkt:** Steuert, ob die „Mit PayPal anmelden“-Funktion aktiv und in Ihrem Store sichtbar ist.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die PayPal-Login-Buttons werden an den ausgewählten Stellen angezeigt, und die Funktionalität ist aktiv.
  - *Wenn deaktiviert (NEIN):* Die PayPal-Login-Buttons werden ausgeblendet, und Kunden können diese Funktion nicht nutzen.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Sie haben die Einrichtung des Moduls abgeschlossen und möchten es für Ihre Kunden live schalten. Sie stellen dies auf JA. Wenn Sie es vorübergehend für Wartungsarbeiten deaktivieren müssen, können Sie es auf NEIN stellen.

#### **Button anzeigen in**

Dieser Abschnitt ermöglicht es Ihnen, auszuwählen, wo der „Mit PayPal anmelden“-Button in Ihrem Store erscheinen soll.

- **Was diese Einstellung bewirkt:** Bestimmt die spezifischen Orte (Hooks), an denen der PayPal-Login-Button in Ihrem Front Office gerendert wird.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn ein Ort ausgewählt ist:* Der PayPal-Login-Button wird in diesem spezifischen Bereich Ihres Stores angezeigt.
  - *Wenn ein Ort nicht ausgewählt ist:* Der Button wird in diesem Bereich nicht angezeigt.
- **Empfohlener Wert:** Wählen Sie Orte aus, die für die Kundenanmeldung/-registrierung am relevantesten sind, wie z.B. `displayNav` (obere Navigation), `displayCustomerLoginFormAfter` (nach dem Standard-Anmeldeformular) und `createAccountForm` (auf der Registrierungsseite).
- **Händlerszenario / Beispiel:** Sie möchten, dass der Button im Header und auf der Hauptanmeldeseite leicht zugänglich ist. Sie würden `displayNav` und `displayCustomerLoginFormAfter` auswählen. Wenn Ihr Theme ein benutzerdefiniertes Pop-up-Login hat, könnten Sie auch `displayPopUpLogin` auswählen.

#### **Button-Stil**

Passen Sie das visuelle Erscheinungsbild des PayPal-Login-Buttons an.

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl aus verschiedenen vordefinierten Stilen für den „Mit PayPal anmelden“-Button, um das Design Ihres Stores oder die Markenrichtlinien von PayPal anzupassen.
- **Auswirkungen einer Änderung dieser Einstellung:** Ändert das visuelle Erscheinungsbild (z.B. Farbe, Größe, Text) der PayPal-Login-Buttons in Ihrem gesamten Store.
- **Empfohlener Wert:** Wählen Sie einen Stil, der sich am besten in das Design Ihres Stores integriert und gleichzeitig klar als PayPal-Button erkennbar bleibt.
- **Händlerszenario / Beispiel:** Ihr Store verwendet ein dunkles Theme, daher könnten Sie einen weißen PayPal-Button mit dunklem Text für besseren Kontrast wählen. Oder Sie bevorzugen den standardmäßigen blauen PayPal-Button für maximale Markenbekanntheit.

#### **Weiterleitungs-URL nach dem Login**

Geben Sie an, wohin Kunden nach erfolgreicher Anmeldung mit PayPal weitergeleitet werden.

- **Was diese Einstellung bewirkt:** Definiert die Seite, auf die ein Kunde sofort weitergeleitet wird, nachdem er sich erfolgreich mit PayPal authentifiziert und zu Ihrem Store zurückkehrt.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „Mein Konto“ eingestellt:* Kunden landen auf ihrem persönlichen Konto-Dashboard.
  - *Wenn auf „Startseite“ eingestellt:* Kunden werden auf die Hauptseite Ihres Stores zurückgebracht.
  - *Wenn auf „Vorherige Seite“ eingestellt:* Kunden werden auf die Seite zurückgebracht, auf der sie sich befanden, bevor sie die Anmeldung initiierten.
- **Empfohlener Wert:** „Vorherige Seite“ oder „Mein Konto“ für ein nahtloses Erlebnis. „Vorherige Seite“ wird oft während des Checkouts bevorzugt.
- **Händlerszenario / Beispiel:** Ein Kunde befindet sich auf einer Produktseite und klickt auf „Mit PayPal anmelden“. Wenn „Vorherige Seite“ ausgewählt ist, kehrt er zu dieser Produktseite zurück. Befand er sich im Checkout-Prozess, würde er zum Checkout-Schritt zurückkehren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | PayPal Client ID | (Leer) / Ihre PayPal Client ID | Eindeutiger Bezeichner für Ihre PayPal-App. **Erforderlich, damit das Modul funktioniert.** |
| Modulkonfiguration | PayPal Client Secret | (Leer) / Ihr PayPal Client Secret | Geheimer Schlüssel für Ihre PayPal-App. **Erforderlich, damit das Modul funktioniert.** |
| Modulkonfiguration | PayPal-Login aktivieren | JA | Hauptschalter zum Aktivieren/Deaktivieren der PayPal-Login-Funktion. |
| Modulkonfiguration | Button anzeigen in: displayNav | JA | Zeigt den Button in der Hauptnavigationsleiste an. |
| Modulkonfiguration | Button anzeigen in: displayCustomerLoginFormAfter | JA | Zeigt den Button nach dem Standard-Anmeldeformular an. |
| Modulkonfiguration | Button anzeigen in: createAccountForm | JA | Zeigt den Button auf der Kundenregistrierungsseite an. |
| Modulkonfiguration | Button anzeigen in: displayFooter | NEIN | Zeigt den Button im Footer des Stores an. |
| Modulkonfiguration | Button anzeigen in: displayHome | NEIN | Zeigt den Button auf der Startseite an. |
| Modulkonfiguration | Button anzeigen in: displayLeftColumn | NEIN | Zeigt den Button in der linken Spalte an. |
| Modulkonfiguration | Button anzeigen in: displayNav1 | NEIN | Zeigt den Button in einem alternativen Navigations-Hook an (Theme-abhängig). |
| Modulkonfiguration | Button anzeigen in: displayNav2 | NEIN | Zeigt den Button in einem weiteren alternativen Navigations-Hook an (Theme-abhängig). |
| Modulkonfiguration | Button anzeigen in: displayPopUpLogin | JA | Zeigt den Button in Pop-up-Anmeldeformularen an (wenn Ihr Theme diese verwendet). |
| Modulkonfiguration | Button anzeigen in: displayRightColumn | NEIN | Zeigt den Button in der rechten Spalte an. |
| Modulkonfiguration | Button anzeigen in: displayTop | NEIN | Zeigt den Button im obersten Bereich der Seite an (Theme-abhängig). |
| Modulkonfiguration | Button anzeigen in: header | NEIN | Zeigt den Button im HTML `<head>`-Bereich an (weniger üblich für sichtbare Buttons). |
| Modulkonfiguration | Button anzeigen in: shoppingCart | NEIN | Zeigt den Button innerhalb der Warenkorb-Zusammenfassung an. |
| Modulkonfiguration | Button anzeigen in: shoppingCartExtra | NEIN | Zeigt den Button in einem zusätzlichen Bereich des Warenkorbs an (Theme-abhängig). |
| Modulkonfiguration | Button-Stil | (Standard-PayPal-Stil) | Visuelles Erscheinungsbild des PayPal-Login-Buttons. |
| Modulkonfiguration | Weiterleitungs-URL nach dem Login | Vorherige Seite | Zielseite nach erfolgreichem PayPal-Login. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der PayPal-Login-Button wird in meinem Store nicht angezeigt.**
A:

1. **„PayPal-Login aktivieren“ überprüfen:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf JA gesetzt ist.
2. **„Button anzeigen in“-Einstellungen überprüfen:** Stellen Sie sicher, dass Sie mindestens einen Hook (z.B. `displayNav`, `displayCustomerLoginFormAfter`) ausgewählt haben, wo der Button erscheinen soll.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Performance** und leeren Sie Ihren PrestaShop-Cache (Smarty-Cache, Dateisystem-Cache). Ihr Browser-Cache muss möglicherweise ebenfalls geleert werden.
4. **Theme-Kompatibilität:** Einige stark angepasste Themes erfordern möglicherweise geringfügige Anpassungen. Wenn der Button immer noch nicht angezeigt wird, kontaktieren Sie den MyPresta.eu-Support.

**F: Wenn ich auf den PayPal-Button klicke, passiert nichts oder ich erhalte einen Fehler.**
A:

1. **API-Zugangsdaten überprüfen:** Überprüfen Sie Ihre PayPal Client ID und Ihr Client Secret in der Modulkonfiguration. Schon ein einziges falsches Zeichen verhindert die Verbindung.
2. **PayPal App-Konfiguration:** Stellen Sie sicher, dass Ihre „Mit PayPal anmelden“-App in Ihrem PayPal-Entwicklerkonto korrekt konfiguriert ist, insbesondere die „Return URL“ oder „Redirect URI“, die auf die Authentifizierungsseite Ihres Stores zeigen sollte (z.B. `https://ihrshop.com/authentication?paypal_login=1`).
3. **PHP-Kompatibilität:** Überprüfen Sie, ob die PHP-Version Ihres Servers im unterstützten Bereich liegt (PHP 5.6 - 8.5).

**F: Meine Kunden werden nach dem Login auf die falsche Seite weitergeleitet.**
A:

1. **„Weiterleitungs-URL nach dem Login“ überprüfen:** Überprüfen Sie diese Einstellung in der Modulkonfiguration. Wählen Sie die gewünschte Option (z.B. „Mein Konto“, „Vorherige Seite“).
2. **Cache leeren:** Leeren Sie nach dem Ändern dieser Einstellung Ihren PrestaShop- und Browser-Cache.

**F: Kann ich den Text auf dem PayPal-Login-Button ändern?**
A: Das Modul verwendet in der Regel das Standard-PayPal-Branding für den Button-Text und -Stil. Eine direkte Änderung des Textes ist in der Modulkonfiguration selbst normalerweise nicht möglich, da es darauf ausgelegt ist, die PayPal-Richtlinien einzuhalten. Wenn Sie einen benutzerdefinierten Text benötigen, wären Theme-Level-Overrides oder eine Modulanpassung erforderlich (siehe Entwicklerhandbuch).

**F: Funktioniert dieses Modul mit mehrsprachigen Stores?**
A: Ja, das Modul ist so konzipiert, dass es mit den mehrsprachigen Funktionen von PrestaShop kompatibel ist. Die PayPal-Login-Oberfläche selbst wird von PayPal gehandhabt, das sich typischerweise an die Browsersprache des Benutzers anpasst. Alle modulspezifischen Texte (falls vorhanden) können über **International > Übersetzungen** in Ihrem PrestaShop-Back Office übersetzt werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „PayPal Login Connect“ (`plogin`) ist ein Standard-PrestaShop-Modul, das hauptsächlich in seiner Hauptdatei `index.php` implementiert ist, die als Einstiegspunkt und Konfigurationshandler des Moduls fungiert. Es nutzt das PrestaShop-Hook-System, um den „Mit PayPal anmelden“-Button in verschiedene Front-Office-Bereiche einzufügen. Das Modul handhabt den OAuth 2.0-Flow mit PayPal zur Benutzerauthentifizierung, erstellt ein Kundenkonto, falls keines existiert, und meldet den Benutzer an. Es führt keine benutzerdefinierten Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, sondern verlässt sich auf die nativen PrestaShop-Klassen `Customer` und `Configuration`.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller im Verzeichnis `controllers/`. Die gesamte Front-Office-Logik im Zusammenhang mit dem PayPal-Callback wird direkt in der Datei `index.php` (der Hauptmodulklasse) über `$_GET`-Parameter behandelt, und die Back-Office-Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält keine benutzerdefinierten Klassen oder Modelle in einem `classes/`-Verzeichnis. Die gesamte Kernlogik, einschließlich der API-Interaktion und der Kundenverwaltung, ist in der Hauptklasse `plogin` gekapselt, die in `index.php` definiert ist.

### 4.4 JavaScript-Assets (`views/js/`)

- **`plogin/js/plogin.js`**
  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Dieses Skript handhabt wahrscheinlich die clientseitige Interaktion für den PayPal-Login-Button. Dies könnte umfassen:
    - Öffnen des PayPal-Authentifizierungsfensters als Pop-up.
    - Handhabung der Weiterleitung nach der PayPal-Authentifizierung.
    - Potenzielles Verwalten von AJAX-Anfragen für den Login-Status oder die dynamische Button-Darstellung.
    - Binden von Klick-Ereignissen an die PayPal-Login-Buttons.
    - Sicherstellen der Button-Funktionalität über verschiedene Browser und Geräte hinweg.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`plogin/css.css`**

  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Dieses Stylesheet enthält wahrscheinlich allgemeine Stile für den PayPal-Login-Button und alle zugehörigen Elemente. Es könnte grundlegendes Layout, Polsterung, Ränder und Schriftstile definieren.
  - **Schlüsselselektoren:** Entwickler können diese Datei nach Klassennamen (z.B. `.paypal-login-button`, `.plogin-container`) durchsuchen, um Stile in der `custom.css` oder `theme.css` ihres Themes zu überschreiben.
- **`plogin/css/plogin.css`**

  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Ähnlich wie `css.css` bietet diese Datei zusätzliche oder spezifischere Stile für den PayPal-Login-Button, möglicherweise einschließlich verschiedener Button-Stile basierend auf der Konfiguration, Hover-Effekten oder responsiven Anpassungen.
  - **Schlüsselselektoren:** Suchen Sie nach spezifischen Button-Klassen (z.B. `.plogin-btn-blue`, `.plogin-btn-white`), um diese anzusprechen und anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet eine umfassende Reihe von Smarty-Templates, um den PayPal-Login-Button in verschiedene PrestaShop-Hooks einzufügen.

- **Hook-Templates (`views/templates/hook/`)**:
  - `plogin/createAccountForm.tpl`: Rendert den PayPal-Button auf dem Kundenregistrierungsformular.
  - `plogin/displayCustomerLoginFormAfter.tpl`: Rendert den PayPal-Button nach dem Standard-Kundenanmeldeformular.
  - `plogin/displayFooter.tpl`: Rendert den PayPal-Button im Footer des Stores.
  - `plogin/displayHome.tpl`: Rendert den PayPal-Button auf der Startseite.
  - `plogin/displayleftColumn.tpl`: Rendert den PayPal-Button in der linken Spalte.
  - `plogin/displayNav.tpl`: Rendert den PayPal-Button in der Hauptnavigationsleiste (häufiger Hook für Top-Links).
  - `plogin/displayNav1.tpl`: Rendert den PayPal-Button in einem alternativen Navigations-Hook (Theme-abhängig).
  - `plogin/displayNav2.tpl`: Rendert den PayPal-Button in einem weiteren alternativen Navigations-Hook (Theme-abhängig).
  - `plogin/displayPopUpLogin.tpl`: Rendert den PayPal-Button innerhalb eines Pop-up-Anmeldeformulars (wenn vom Theme verwendet).
  - `plogin/displayrightColumn.tpl`: Rendert den PayPal-Button in der rechten Spalte.
  - `plogin/displayTop.tpl`: Rendert den PayPal-Button im obersten Bereich der Seite (Theme-abhängig).
  - `plogin/header.tpl`: Dieses Template wird wahrscheinlich verwendet, um CSS/JS-Assets im `<head>`-Bereich einzubinden, wenn der `displayHeader`-Hook verwendet wird, anstatt einen sichtbaren Button anzuzeigen.
  - `plogin/shoppingCart.tpl`: Rendert den PayPal-Button innerhalb der Warenkorb-Zusammenfassung.
  - `plogin/shoppingCartExtra.tpl`: Rendert den PayPal-Button in einem zusätzlichen Bereich des Warenkorbs (Theme-abhängig).
  - `plogin/top.tpl`: Ähnlich wie `displayTop`, für den oberen Bereich der Seite.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen (Client ID, Client Secret, aktivierter Status, ausgewählte Hooks, Weiterleitungs-URL, Button-Stil) werden in der PrestaShop-Tabelle `ps_configuration` gespeichert, typischerweise mit Schlüsseln, die mit `PLOGIN_` beginnen (z.B. `PLOGIN_CLIENT_ID`, `PLOGIN_ENABLED`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt / Ort | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Zum globalen Einbinden von CSS- und JavaScript-Assets für das Modul. |
| `displayNav` | In der Hauptnavigationsleiste, normalerweise oben auf der Seite. | Zeigt den PayPal-Login-Button in einem prominenten Navigationsbereich an. |
| `displayNav1` | Alternativer Navigations-Hook (Theme-abhängig). | Bietet Flexibilität für Themes mit mehreren Navigationsbereichen. |
| `displayNav2` | Ein weiterer alternativer Navigations-Hook (Theme-abhängig). | Bietet Flexibilität für Themes mit mehreren Navigationsbereichen. |
| `displayTop` | Im obersten Bereich der Seite, über dem Hauptinhalt. | Zeigt den PayPal-Login-Button in der oberen Leiste an. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Zeigt den PayPal-Login-Button in der linken Spalte an. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Zeigt den PayPal-Login-Button in der rechten Spalte an. |
| `displayFooter` | Im Footer-Bereich des Stores. | Zeigt den PayPal-Login-Button im Footer an. |
| `displayHome` | Auf der Startseite des Stores. | Zeigt den PayPal-Login-Button auf der Haupt-Landingpage an. |
| `displayCustomerLoginFormAfter` | Nach dem Standard-Anmeldeformular auf der Authentifizierungsseite. | Bietet die PayPal-Login-Option als Alternative zu E-Mail/Passwort. |
| `createAccountForm` | Auf der Kundenregistrierungsseite. | Bietet PayPal als schnelle Registrierungsmethode an. |
| `displayPopUpLogin` | Innerhalb eines Pop-up-Login-Modals (wenn vom Theme implementiert). | Integriert sich in moderne Theme-Login-Pop-ups. |
| `shoppingCart` | Innerhalb des Warenkorb-Zusammenfassungsblocks. | Bietet Login/Registrierung während der Warenkorbüberprüfung. |
| `shoppingCartExtra` | In einem zusätzlichen Bereich des Warenkorbs (Theme-abhängig). | Bietet zusätzliche Platzierungsflexibilität innerhalb des Warenkorbs. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „PayPal Login Connect“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Modulfunktionalität gerne zur Verfügung.
