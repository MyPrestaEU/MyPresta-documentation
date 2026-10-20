---
title: "Google Login Connect - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Google Login Connect von MyPresta.eu."
sidebar:
  label: "Google Login Connect"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google Login Connect auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/google-login-connect.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/google-login-connect/)
>
> ---


# Google Login Connect

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die sichere Kommunikation mit der Google API erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Google Login Connect)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie Ihre Google API-Anmeldeinformationen einrichten und entscheiden, wo der „Mit Google anmelden“-Button in Ihrem Shop angezeigt wird.

#### **Google API-Anmeldeinformationen**

Bevor Sie das Modul konfigurieren, müssen Sie ein Google API-Projekt erstellen und Ihre Client-ID erhalten. Dies ist entscheidend, damit das Modul sicher mit Google kommunizieren kann.

**So erhalten Sie Ihre Google Client-ID:**
1.  Gehen Sie zur [Google Cloud Console](https://console.cloud.google.com/).
2.  Erstellen Sie ein neues Projekt oder wählen Sie ein bestehendes aus.
3.  Navigieren Sie zu **APIs & Dienste > Anmeldeinformationen**.
4.  Klicken Sie auf **„Anmeldeinformationen erstellen“** und wählen Sie **„OAuth-Client-ID“**.
5.  Wählen Sie **„Webanwendung“** als Anwendungstyp.
6.  Fügen Sie unter **„Autorisierte JavaScript-Ursprünge“** die URL Ihres Shops hinzu (z.B. `https://www.ihrshop.com`).
7.  Fügen Sie unter **„Autorisierte Weiterleitungs-URIs“** die URL Ihres Shops gefolgt vom Callback-Pfad des Moduls hinzu (z.B. `https://www.ihrshop.com/module/glogin/index`).
8.  Nach der Erstellung stellt Google Ihnen eine **Client-ID** zur Verfügung. Kopieren Sie diesen Wert.

-   **Google Client-ID (ggl_appid)**
    -   **Was diese Einstellung bewirkt:** Dies ist der eindeutige Bezeichner für Ihre Anwendung (Ihren PrestaShop-Shop), den Google verwendet, um Ihre Anmeldeanfragen zu erkennen. Er ist unerlässlich, damit die „Mit Google anmelden“-Funktion funktioniert.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Bei korrekter Eingabe:* Ihre Google-Anmeldebuttons funktionieren, sodass Kunden sich über Google authentifizieren können.
        -   *Bei falscher oder leerer Eingabe:* Die Google-Anmeldebuttons funktionieren nicht, oder Kunden stoßen auf Fehler, wenn sie versuchen, sich mit Google anzumelden.
    -   **Empfohlener Wert:** Die Client-ID, die Sie aus Ihrer Google Cloud Console erhalten haben.
    -   **Händlerszenario / Beispiel:** Sie haben gerade Ihr Google API-Projekt erstellt und `1234567890-abcdefg.apps.googleusercontent.com` erhalten. Sie müssen diese genaue Zeichenfolge hier einfügen.

#### **Kundenkontoeinstellungen**

-   **Kundengruppe für Google-Benutzer (glogin_groupid)**
    -   **Was diese Einstellung bewirkt:** Legt fest, welcher Kundengruppe neue Benutzer, die sich über Google registrieren, automatisch zugewiesen werden.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn auf „Kunde“ (Standard) eingestellt:* Neue Google-Benutzer sind Standardkunden.
        -   *Wenn auf „Besucher“ oder eine andere benutzerdefinierte Gruppe eingestellt:* Neue Google-Benutzer werden dieser spezifischen Gruppe zugewiesen, was sich möglicherweise auf ihren Zugang zu Rabatten, Sonderpreisen oder Inhalten auswirkt.
    -   **Empfohlener Wert:** „Kunde“ (oder Ihre Standard-Kundengruppe).
    -   **Händlerszenario / Beispiel:** Sie möchten, dass alle neuen Google-Anmeldungen Teil Ihrer Gruppe „Großhandelskunden“ sind, um ihnen automatisch B2B-Preise zu gewähren. Sie würden „Großhandelskunden“ aus der Dropdown-Liste auswählen.

-   **Willkommens-E-Mail an neue Google-Benutzer senden (glogin_semail)**
    -   **Was diese Einstellung bewirkt:** Steuert, ob PrestaShop eine Standard-Willkommens-E-Mail an Kunden sendet, die sich mit ihrem Google-Konto registrieren.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Neue Google-Benutzer erhalten die Standard-PrestaShop-Willkommens-E-Mail, die ihre Kontoerstellung bestätigt.
        -   *Wenn deaktiviert (NEIN):* Neue Google-Benutzer erhalten keine Willkommens-E-Mail.
    -   **Empfohlener Wert:** JA (um die Kontoerstellung zu bestätigen und einen guten ersten Eindruck zu hinterlassen).
    -   **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass neue Kunden willkommen geheißen werden und ihre Kontodaten bestätigt werden, daher aktivieren Sie diese Option.

#### **Anzeigeoptionen**

-   **Stil des Google-Login-Buttons anzeigen (glogin_button_style)**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den visuellen Stil des „Mit Google anmelden“-Buttons zu wählen. Optionen umfassen typischerweise verschiedene Größen, Formen oder Farbschemata, die von Google bereitgestellt werden.
    -   **Auswirkung einer Änderung dieser Einstellung:** Ändert das Aussehen aller Google-Login-Buttons in Ihrem Shop.
    -   **Empfohlener Wert:** Wählen Sie den Stil, der am besten zum Design Ihres Shops passt.
    -   **Händlerszenario / Beispiel:** Ihr Theme verwendet große, abgerundete Buttons. Sie würden einen Button-Stil wählen, der zu dieser Ästhetik passt, um Konsistenz zu gewährleisten.

-   **Google-Login-Button im Pop-up anzeigen (ggl_popuplogin)**
    -   **Was diese Einstellung bewirkt:** Wenn aktiviert, erscheint beim Klicken auf einen Anmelde-Link ein Pop-up-Fenster mit der Google-Anmeldeoption, anstatt den Benutzer auf eine vollständige Anmeldeseite umzuleiten.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Bietet ein schnelleres, weniger störendes Anmeldeerlebnis über ein modales Pop-up.
        -   *Wenn deaktiviert (NEIN):* Kunden werden auf die Standard-Anmeldeseite weitergeleitet.
    -   **Empfohlener Wert:** JA (für ein modernes, nahtloses Benutzererlebnis).
    -   **Händlerszenario / Beispiel:** Sie möchten Kunden so weit wie möglich auf der aktuellen Seite halten, daher aktivieren Sie die Pop-up-Anmeldung.

#### **Button-Platzierung (Hook-Auswahl)**

Diese Einstellungen steuern, wo der „Mit Google anmelden“-Button in Ihrem Shop erscheint. Sie können den Button für verschiedene PrestaShop-Display-Hooks aktivieren oder deaktivieren.

-   **Im Header anzeigen (ggl_top)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons im Header-Bereich Ihres Shops.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint im Header (z.B. in der Nähe von „Mein Konto“ oder „Anmelden“).
        -   *Deaktiviert:* Button ist im Header ausgeblendet.
    -   **Empfohlener Wert:** JA (für einfachen Zugriff von jeder Seite).

-   **In der Navigationsleiste anzeigen (ggl_displayNav, ggl_displayNav1, ggl_displayNav2)**
    -   **Was diese Einstellungen bewirken:** Steuern die Sichtbarkeit des Google-Login-Buttons an verschiedenen Positionen der Navigationsleiste, abhängig von Ihrer PrestaShop-Version und Ihrem Theme. `displayNav` ist üblich für ältere Themes, während `displayNav1` und `displayNav2` oft in PrestaShop 1.7+ für die Navigation am oberen Seitenrand verwendet werden.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint in der ausgewählten Navigationsleiste.
        -   *Deaktiviert:* Button ist in dieser Navigationsleiste ausgeblendet.
    -   **Empfohlener Wert:** Aktivieren Sie ein oder zwei, die am besten zu Ihrem Theme passen, um Redundanz zu vermeiden.

-   **Im Warenkorb anzeigen (ggl_shoppingCart, ggl_shoppingCartExtra)**
    -   **Was diese Einstellungen bewirken:** Steuern die Sichtbarkeit des Google-Login-Buttons auf der Warenkorbseite. `ggl_shoppingCart` ist typischerweise für den Hauptwarenkorbinhalt, während `ggl_shoppingCartExtra` für zusätzliche Blöcke oder Zusammenfassungen sein könnte.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint auf der Warenkorbseite, ermöglicht eine schnelle Anmeldung vor dem Checkout.
        -   *Deaktiviert:* Button ist auf der Warenkorbseite ausgeblendet.
    -   **Empfohlener Wert:** JA (um eine schnelle Anmeldung zu fördern und Abbrüche zu reduzieren).

-   **In der linken Spalte anzeigen (ggl_leftcolumn)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons in der linken Seitenleiste Ihres Shops.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint in der linken Spalte.
        -   *Deaktiviert:* Button ist in der linken Spalte ausgeblendet.
    -   **Empfohlener Wert:** JA (wenn Ihr Theme eine linke Spalte verwendet und Sie eine prominente Platzierung wünschen).

-   **In der rechten Spalte anzeigen (ggl_rightoclumn)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons in der rechten Seitenleiste Ihres Shops.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint in der rechten Spalte.
        -   *Deaktiviert:* Button ist in der rechten Spalte ausgeblendet.
    -   **Empfohlener Wert:** JA (wenn Ihr Theme eine rechte Spalte verwendet und Sie eine prominente Platzierung wünschen).

-   **Auf der Startseite anzeigen (ggl_home)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons auf der Startseite Ihres Shops.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint auf der Startseite.
        -   *Deaktiviert:* Button ist auf der Startseite ausgeblendet.
    -   **Empfohlener Wert:** JA (für maximale Sichtbarkeit und schnellen Zugriff für neue Besucher).

-   **Nach dem Kunden-Login-Formular anzeigen (ggl_displayCustomerLoginFormAfter)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons direkt nach dem Standard-PrestaShop-Kunden-Login-Formular (z.B. auf der `/my-account`-Seite).
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint unter dem traditionellen Login-Formular.
        -   *Deaktiviert:* Button ist an dieser Position ausgeblendet.
    -   **Empfohlener Wert:** JA (dies ist ein primärer Ort für Social-Login-Buttons).

-   **Auf dem Kontoerstellungsformular anzeigen (ggl_createAccountForm, ggl_createAccountTop)**
    -   **Was diese Einstellungen bewirken:** Steuern die Sichtbarkeit des Google-Login-Buttons auf der Kundenkontoerstellungsseite. `ggl_createAccountForm` platziert ihn typischerweise innerhalb oder in der Nähe des Formulars, während `ggl_createAccountTop` ihn ganz oben auf der Kontoerstellungsseite platziert.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint auf der Kontoerstellungsseite und bietet eine schnelle Registrierungsalternative.
        -   *Deaktiviert:* Button ist auf dieser Seite ausgeblendet.
    -   **Empfohlener Wert:** JA (um die Registrierung neuer Kunden zu vereinfachen).

-   **In der oberen Spalte anzeigen (ggl_topColumn)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons im `displayTopColumn`-Hook, der oft für Banner oder Inhalte direkt unter dem Header verwendet wird.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint in der oberen Spalte.
        -   *Deaktiviert:* Button ist in der oberen Spalte ausgeblendet.
    -   **Empfohlener Wert:** Berücksichtigen Sie dies basierend auf dem Layout Ihres Themes; oft weniger kritisch als andere Positionen.

-   **Persönliche Informationen oben anzeigen (ggl_displayPersonalInformationTop)**
    -   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Google-Login-Buttons auf der Seite „Meine persönlichen Informationen“, normalerweise wenn ein Kunde bereits angemeldet ist. Dies ist möglicherweise weniger üblich für einen Login-Button, könnte aber für die Kontoverknüpfung verwendet werden.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Aktiviert:* Button erscheint auf der Seite mit den persönlichen Informationen.
        -   *Deaktiviert:* Button ist auf dieser Seite ausgeblendet.
    -   **Empfohlener Wert:** NEIN (typischerweise kein primärer Anmeldeort).

#### **Weitere Einstellungen (Intern/Legacy)**

-   **mypresta_updates, update_, update_**: Dies sind interne Einstellungen, die von MyPresta.eu für Modul-Update-Prüfungen und Versionsverwaltung verwendet werden. Sie sollten diese nicht ändern.
-   **PS_CUSTOMER_GROUP, PS_CUSTOMER_CREATION_EMAIL, PS_CART_FOLLOWING**: Dies sind Standard-PrestaShop-Konfigurationsvariablen, auf die das Modul möglicherweise verweist, aber typischerweise keine direkte Änderung über seine Oberfläche zulässt. Sie spiegeln die Kerneinstellungen Ihres Shops wider.
-   **glogin_identity**: Dies ist wahrscheinlich ein interner Bezeichner, der vom Modul verwendet wird. Nicht ändern.
-   **ggl_**: Alle anderen Einstellungen, die mit `ggl_` beginnen und nicht explizit oben aufgeführt sind, sind wahrscheinlich interne Flags oder Legacy-Optionen. Es ist am besten, sie auf ihren Standardwerten zu belassen, es sei denn, der Support weist Sie anders an.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Google Client-ID | Ihre Google Client-ID | Wesentlich für die Google-Anmeldefunktion. |
| Modulkonfiguration | Kundengruppe für Google-Benutzer | Kunde | Weist neuen Google-Benutzern eine bestimmte Kundengruppe zu. |
| Modulkonfiguration | Willkommens-E-Mail an neue Google-Benutzer senden | JA | Sendet eine Willkommens-E-Mail an neue Google-Anmeldungen. |
| Modulkonfiguration | Stil des Google-Login-Buttons anzeigen | (Wählen Sie die beste Passform) | Ändert das visuelle Erscheinungsbild des Buttons. |
| Modulkonfiguration | Google-Login-Button im Pop-up anzeigen | JA | Ermöglicht die Pop-up-Anmeldung für eine reibungslosere UX. |
| Modulkonfiguration | Im Header anzeigen (ggl_top) | JA | Zeigt den Button im Header des Shops an. |
| Modulkonfiguration | In der Navigationsleiste anzeigen (ggl_displayNav, ggl_displayNav1, ggl_displayNav2) | JA (nach Bedarf) | Zeigt den Button in verschiedenen Navigationsleisten an. |
| Modulkonfiguration | Im Warenkorb anzeigen (ggl_shoppingCart, ggl_shoppingCartExtra) | JA | Zeigt den Button auf der Warenkorbseite an. |
| Modulkonfiguration | In der linken Spalte anzeigen (ggl_leftcolumn) | JA (falls zutreffend) | Zeigt den Button in der linken Seitenleiste an. |
| Modulkonfiguration | In der rechten Spalte anzeigen (ggl_rightoclumn) | JA (falls zutreffend) | Zeigt den Button in der rechten Seitenleiste an. |
| Modulkonfiguration | Auf der Startseite anzeigen (ggl_home) | JA | Zeigt den Button auf der Startseite des Shops an. |
| Modulkonfiguration | Nach dem Kunden-Login-Formular anzeigen (ggl_displayCustomerLoginFormAfter) | JA | Zeigt den Button unter dem Standard-Login-Formular an. |
| Modulkonfiguration | Auf dem Kontoerstellungsformular anzeigen (ggl_createAccountForm, ggl_createAccountTop) | JA | Zeigt den Button auf der Kontoerstellungsseite an. |
| Modulkonfiguration | In der oberen Spalte anzeigen (ggl_topColumn) | NEIN (oder nach Bedarf) | Zeigt den Button im oberen Spalten-Hook an. |
| Modulkonfiguration | Persönliche Informationen oben anzeigen (ggl_displayPersonalInformationTop) | NEIN | Zeigt den Button auf der Seite mit den persönlichen Informationen an (weniger üblich). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Google-Login-Button erscheint, aber es passiert nichts, wenn ich darauf klicke, oder ich erhalte einen Fehler.**
A: Dies ist fast immer ein Problem mit Ihrer Google Client-ID oder den autorisierten Weiterleitungs-URIs in Ihrer Google Cloud Console.
    *   **Client-ID überprüfen:** Überprüfen Sie nochmals, ob die in der Modulkonfiguration eingegebene `Google Client-ID` genau der von Google bereitgestellten entspricht, ohne zusätzliche Leerzeichen.
    *   **Autorisierte Weiterleitungs-URIs überprüfen:** Stellen Sie in Ihrer Google Cloud Console sicher, dass Sie `https://www.ihrshop.com/module/glogin/index` (ersetzen Sie `ihrshop.com` durch Ihre tatsächliche Domain) zur Liste der „Autorisierten Weiterleitungs-URIs“ hinzugefügt haben. Es muss eine exakte Übereinstimmung sein, einschließlich `https://`, wenn Ihr Shop SSL verwendet.
    *   **Autorisierte JavaScript-Ursprünge überprüfen:** Stellen Sie außerdem sicher, dass Ihre Haupt-Shop-URL (z.B. `https://www.ihrshop.com`) unter „Autorisierte JavaScript-Ursprünge“ aufgeführt ist.

**F: Neue Kunden registrieren sich mit Google, erhalten aber keine Willkommens-E-Mail.**
A: Überprüfen Sie die Einstellung „Willkommens-E-Mail an neue Google-Benutzer senden“ in der Modulkonfiguration. Stellen Sie sicher, dass sie auf „JA“ eingestellt ist. Überprüfen Sie außerdem, ob die allgemeinen E-Mail-Einstellungen Ihres PrestaShop-Shops korrekt konfiguriert sind und ob andere Transaktions-E-Mails (wie Bestellbestätigungen) erfolgreich gesendet werden.

**F: Der Google-Login-Button erscheint an einem bestimmten Ort (z.B. im Header) nicht, obwohl ich ihn aktiviert habe.**
A:
    *   **Cache leeren:** Leeren Sie zuerst Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung > Cache leeren**).
    *   **Modulposition:** Gehen Sie zu **Design > Positionen** (oder **Module > Positionen** in älteren Versionen). Suchen Sie nach dem Modul `glogin`. Stellen Sie sicher, dass es in die `displayHeader`, `displayNav` oder andere relevante Hooks, die Sie aktiviert haben, eingehängt ist. Manchmal können Themes Standard-Hook-Verhalten überschreiben.
    *   **Theme-Konflikte:** Ihr Theme könnte benutzerdefinierte Templates haben, die nicht explizit alle Standard-PrestaShop-Hooks aufrufen. Wenn der Button nach dem Leeren des Caches und der Überprüfung der Modulpositionen nicht erscheint, müssen Sie möglicherweise einen Webmaster bitten, die `.tpl`-Dateien Ihres Themes zu überprüfen.

**F: Können Kunden ein bestehendes PrestaShop-Konto mit ihrem Google-Konto verknüpfen?**
A: Dieses Modul erleichtert hauptsächlich neue Registrierungen und Anmeldungen. Wenn ein Kunde sich mit Google anmeldet und ein Konto mit dieser E-Mail-Adresse bereits in Ihrem PrestaShop-Shop existiert, meldet das Modul ihn typischerweise in seinem bestehenden Konto an. Es bietet normalerweise keine separate Funktion zum „Verknüpfen eines bestehenden Kontos“ nach der Anmeldung, aber es gleicht intelligent nach E-Mail ab.

**F: Ich möchte den Text oder das Aussehen des Buttons über die Moduloptionen hinaus ändern.**
A: Das Modul bietet Standard-Google-Button-Stile. Für erweiterte Anpassungen (z.B. Text ändern, benutzerdefinierte Icons hinzufügen) benötigen Sie benutzerdefiniertes CSS und möglicherweise JavaScript-Modifikationen, die von einem Webentwickler vorgenommen werden sollten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Google Login Connect Modul arbeiten.

### 4.1 Architekturübersicht
Das `Google Login Connect`-Modul folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Front-Controller für die OAuth 2.0-Callback-Verarbeitung und verschiedene Display-Hooks für die Button-Injektion nutzt. Es stützt sich auf die `Configuration`-Klasse von PrestaShop zur Speicherung von Einstellungen und das `Customer`-`ObjectModel` zur Benutzerverwaltung. Das Modul integriert sich mit der JavaScript-API von Google für die clientseitige Authentifizierung, die dann das Token an einen Modul-Front-Controller zur serverseitigen Überprüfung und Erstellung der Benutzersitzung sendet.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   `glogin/controllers/front/index.php`
        *   **Klassenname & Elternklasse**: `GloginIndexModuleFrontController` erweitert `ModuleFrontController`
        *   **Verantwortlichkeit**: Dies ist der primäre Callback-Endpunkt für den OAuth 2.0-Fluss von Google. Nachdem ein Benutzer sich bei Google authentifiziert hat, leitet Google zu diesem Controller um. Er empfängt das Google ID-Token, überprüft es, extrahiert Benutzerinformationen (E-Mail, Name) und meldet dann entweder einen bestehenden PrestaShop-Kunden an oder erstellt einen neuen. Er verwaltet die Sitzung und leitet den Benutzer zurück zum Shop.
    *   `glogin/controllers/front/loginloader.php`
        *   **Klassenname & Elternklasse**: `GloginLoginloaderModuleFrontController` erweitert `ModuleFrontController`
        *   **Verantwortlichkeit**: Dieser Controller liefert wahrscheinlich ein kleines Stück JavaScript oder initialisiert den Google API-Client auf Seiten, auf denen der Login-Button angezeigt wird. Er könnte verwendet werden, um die Google Platform Library (`platform.js`) dynamisch zu laden oder Konfigurationsvariablen (wie die `ggl_appid`) für das Front-End-JavaScript bereitzustellen.

-   **Back-Office-Admin-Controller**:
    *   Keine. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)
-   Es sind keine benutzerdefinierten `ObjectModel`-Klassen im Verzeichnis `classes/` definiert. Das Modul interagiert direkt mit PrestaShops Kern-`Customer`-`ObjectModel` und der `Configuration`-Klasse.
-   Die Hauptmoduldatei `glogin/glogin.php` fungiert als primäre Klasse, die `Module` erweitert und die gesamte Installations-, Deinstallations- und Konfigurationslogik enthält.

### 4.4 JavaScript-Assets (`views/js/`)

-   `glogin/views/js/glogin.js`
    *   **Geltungsbereich**: Front-Office.
    *   **Verantwortlichkeit**: Dieses Skript ist für die Initialisierung der Google Sign-In-Client-Bibliothek verantwortlich. Es enthält wahrscheinlich:
        *   Laden der Google Platform Library (`https://apis.google.com/js/platform.js`).
        *   Rendern des „Mit Google anmelden“-Buttons mit `gapi.signin2.render()`.
        *   Behandeln der `onSignIn`-Callback-Funktion, die nach einer erfolgreichen Google-Anmeldung ausgelöst wird. Dieser Callback extrahiert das ID-Token und sendet es per AJAX an den Front-Controller des Moduls (`index.php`) zur serverseitigen Verarbeitung.
        *   Potenziell Verwaltung der Pop-up-Anmeldefunktion (`ggl_popuplogin`), die den Google-Button dynamisch in einem Modal anzeigt.
        *   Ereignis-Listener für Klickereignisse auf Google-Login-Buttons.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `glogin/css.css`
    *   **Geltungsbereich**: Front-Office.
    *   **Verantwortlichkeit**: Allgemeine Stilgebung für die Google-Login-Buttons und potenziell alle benutzerdefinierten Container oder Pop-ups, die vom Modul eingeführt werden. Kann grundlegende Layoutanpassungen enthalten.
-   `glogin/views/css/glogin.css`
    *   **Geltungsbereich**: Front-Office.
    *   **Verantwortlichkeit**: Ähnlich wie `css.css`, enthält wahrscheinlich Kern-Styling für die Google-Login-Buttons, um sicherzustellen, dass sie in verschiedenen PrestaShop-Themes richtig ausgerichtet und dimensioniert sind.
-   `glogin/views/css/glogin17-new.css`
    *   **Geltungsbereich**: Front-Office.
    *   **Verantwortlichkeit**: Spezifische CSS-Regeln, die auf PrestaShop 1.7+-Themes zugeschnitten sind und potenzielle Layoutunterschiede oder Styling-Überschreibungen für neuere Versionen berücksichtigen. Dies könnte Flexbox- oder Grid-Anpassungen umfassen.
-   `glogin/views/css/glogin17.css`
    *   **Geltungsbereich**: Front-Office.
    *   **Verantwortlichkeit**: Ein weiteres Stylesheet speziell für PrestaShop 1.7.x, das je nach genauer Theme-Struktur zusätzliche oder alternative Stile im Vergleich zu `glogin17-new.css` enthalten kann.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul nutzt zahlreiche Templates, um den Google-Login-Button in verschiedene PrestaShop-Hooks einzufügen. Die meisten dieser Templates enthalten einen Aufruf der Google Sign-In-Button-Rendering-Logik (z.B. `<div class="g-signin2" data-onsuccess="onSignIn"></div>`) und potenziell etwas umgebendes HTML für die Stilgebung.

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `glogin/views/templates/createAccountForm.tpl`: Rendert den Google-Button innerhalb des Kundenkonto-Erstellungsformulars.
    *   `glogin/views/templates/createAccountTop.tpl`: Rendert den Google-Button oben auf der Kontoerstellungsseite.
    *   `glogin/views/templates/dashboardZoneOne.tpl`: Rendert den Google-Button im `dashboardZoneOne`-Hook (weniger üblich für die Anmeldung, möglicherweise für die Integration in das Admin-Dashboard oder ein spezifisches Theme).
    *   `glogin/views/templates/displayCustomerLoginFormAfter.tpl`: Rendert den Google-Button direkt nach dem Standard-Kunden-Login-Formular.
    *   `glogin/views/templates/displayNav.tpl`: Rendert den Google-Button im `displayNav`-Hook (oft Top-Navigation).
    *   `glogin/views/templates/displayNav1.tpl`: Rendert den Google-Button im `displayNav1`-Hook (PrestaShop 1.7+ Navigation).
    *   `glogin/views/templates/displayNav2.tpl`: Rendert den Google-Button im `displayNav2`-Hook (PrestaShop 1.7+ Navigation).
    *   `glogin/views/templates/displayPopUpLogin.tpl`: Enthält die HTML-Struktur für das Pop-up-Login-Modal, einschließlich des Google-Buttons.
    *   `glogin/views/templates/footer.tpl`: Rendert den Google-Button im `displayFooter`-Hook.
    *   `glogin/views/templates/glogin.tpl`: Ein generisches Template, möglicherweise als Fallback oder für interne Rendering-Logik verwendet.
    *   `glogin/views/templates/header.tpl`: Rendert den Google-Button im `displayHeader`-Hook.
    *   `glogin/views/templates/home.tpl`: Rendert den Google-Button im `displayHome`-Hook.
    *   `glogin/views/templates/leftcolumn.tpl`: Rendert den Google-Button im `displayLeftColumn`-Hook.
    *   `glogin/views/templates/rightcolumn.tpl`: Rendert den Google-Button im `displayRightColumn`-Hook.
    *   `glogin/views/templates/shoppingCart.tpl`: Rendert den Google-Button im `displayShoppingCart`-Hook.
    *   `glogin/views/templates/shoppingCartExtra.tpl`: Rendert den Google-Button im `displayShoppingCartExtra`-Hook.
    *   `glogin/views/templates/top.tpl`: Rendert den Google-Button im `displayTop`-Hook.
    *   `glogin/views/templates/topColumn.tpl`: Rendert den Google-Button im `displayTopColumn`-Hook.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `GLOGIN_GROUPID`, `GLOGIN_SEMAIL`, `GGL_APPID`, `GGL_POPUP_LOGIN`, `GGL_BUTTON_STYLE` und verschiedenen `GGL_DISPLAY[HOOK_NAME]`-Flags gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Abschnitt oder ganz am Anfang des `<body>` | CSS, JS und potenziell den Google-Button im Header einfügen. |
| `displayFooter` | Am Ende des `<body>` | Den Google-Button im Footer einfügen. |
| `displayHome` | Im Inhaltsbereich der Startseite | Den Google-Button auf der Startseite einfügen. |
| `displayShoppingCart` | Auf der Warenkorbseite | Den Google-Button auf der Warenkorbseite einfügen. |
| `displayRightColumn` | In der rechten Seitenleiste | Den Google-Button in der rechten Spalte einfügen. |
| `displayCustomerLoginFormAfter` | Nach dem Standard-Kunden-Login-Formular | Den Google-Button für alternative Anmeldung einfügen. |
| `displayNav` | In der Hauptnavigationsleiste (ältere Themes) | Den Google-Button in die Navigation einfügen. |
| `displayCreateAccountTop` | Oben auf der Kontoerstellungsseite | Den Google-Button für schnelle Registrierung einfügen. |
| `displayTop` | Im oberen Bereich der Seite (oft über dem Header) | Den Google-Button im obersten Bereich einfügen. |
| `displayNav2` | In einer sekundären Navigationsleiste (PS 1.7+) | Den Google-Button in die Navigation einfügen. |
| `displayShoppingCartExtra` | Zusätzlicher Inhaltsbereich auf der Warenkorbseite | Den Google-Button auf der Warenkorbseite einfügen. |
| `displayTopColumn` | Im Inhaltsbereich unter dem Header (oft für Banner) | Den Google-Button in der oberen Spalte einfügen. |
| `displayNav1` | In einer primären Navigationsleiste (PS 1.7+) | Den Google-Button in die Navigation einfügen. |
| `dashboardZoneOne` | In der ersten Zone des Admin-Dashboards | Potenziell für Admin-seitige Informationen oder einen spezifischen Button. |
| `displayLeftColumn` | In der linken Seitenleiste | Den Google-Button in der linken Spalte einfügen. |

## 5. Offizieller Support & Updates
Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Stellen Sie sicher, dass Sie die neueste kompatible Version des Moduls für Ihren PrestaShop-Shop verwenden.
