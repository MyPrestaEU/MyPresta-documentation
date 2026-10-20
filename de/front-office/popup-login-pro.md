---
title: "PopUp Login Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul PopUp Login Pro von MyPresta.eu."
sidebar:
  label: "PopUp Login Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul PopUp Login Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/popup-login-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/popup-login-pro/)
>
> ---


# PopUp Login Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für einen PrestaShop-Shop erforderlich, und dieses Modul hat darüber hinaus keine ungewöhnlichen Anforderungen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > PopUp Login Pro)

Dies ist der Hauptkonfigurationsbildschirm für das Modul PopUp Login Pro. Hier können Sie anpassen, wie das Pop-up in Ihrem Shop erscheint und sich verhält.

#### Allgemeine Einstellungen

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **PopUp Login aktivieren** | Dieser Schalter steuert, ob die Pop-up-Login-Funktionalität in Ihrem Shop aktiv ist. | *Wenn aktiviert:* Das Modul fängt Klicks auf Login-Links ab und zeigt das Pop-up an. *Wenn deaktiviert:* Ihr Shop kehrt zu den Standard-PrestaShop-Login-Seitenumleitungen zurück. | JA | Sie möchten die Pop-up-Login-Funktion nutzen. |
| **PopUp-Formulartyp** | Diese Option ermöglicht es Ihnen, aus mehreren vorgefertigten visuellen Stilen für Ihr Login-Pop-up-Formular zu wählen. | *Wenn auf Option A eingestellt:* Das Pop-up wird mit dem Design von Option A angezeigt. *Wenn auf Option B eingestellt:* Das Pop-up wird mit dem Design von Option B angezeigt. Jede Option bietet ein eigenes Aussehen und Gefühl. | Wählen Sie diejenige, die am besten zum Design Ihres Shops passt. | Sie möchten ein minimalistisches Anmeldeformular (Option 1) oder ein visuell ansprechenderes mit einem Bild (Option 3). |
| **PopUp-Breite (Pixel)** | Definiert die Breite des Pop-up-Fensters in Pixeln. | *Wenn auf 400px eingestellt:* Das Pop-up ist 400 Pixel breit. *Wenn auf 600px eingestellt:* Das Pop-up ist 600 Pixel breit. Eine geringere Breite könnte auf Mobilgeräten besser aussehen, während eine größere mehr Inhalt oder ein spezifisches Design aufnehmen kann. | 400-500px (an den ausgewählten Formulartyp anpassen) | Ihr gewählter Formulartyp wirkt bei 400px beengt, daher erhöhen Sie ihn auf 500px für bessere Lesbarkeit. |
| **PopUp-Höhe (Pixel)** | Definiert die Höhe des Pop-up-Fensters in Pixeln. | *Wenn auf 300px eingestellt:* Das Pop-up ist 300 Pixel hoch. *Wenn auf 500px eingestellt:* Das Pop-up ist 500 Pixel hoch. Stellen Sie sicher, dass es hoch genug ist, um alle Formularfelder ohne Scrollen anzuzeigen. | 300-450px (an den ausgewählten Formulartyp anpassen) | Ihr gewählter Formulartyp hat viele Felder, und bei 300px müssen Kunden scrollen. Sie erhöhen es auf 450px, um alles anzuzeigen. |
| **PopUp-Hintergrundfarbe** | Legt die Hintergrundfarbe des Pop-up-Fensters fest. Sie können normalerweise einen Farbwähler verwenden oder einen hexadezimalen Farbcode eingeben (z. B. #FFFFFF für Weiß). | *Wenn auf #FFFFFF eingestellt:* Der Pop-up-Hintergrund ist weiß. *Wenn auf #F0F0F0 eingestellt:* Der Pop-up-Hintergrund ist hellgrau. Dies hilft, das Pop-up an das Farbschema Ihres Shops anzupassen. | #FFFFFF (Weiß) oder eine Farbe, die Ihr Theme ergänzt. | Ihr Shop verwendet ein dunkles Theme, daher stellen Sie den Hintergrund auf ein dunkles Grau (#333333) ein, um Konsistenz zu gewährleisten. |
| **PopUp-Rahmenfarbe** | Legt die Farbe des Rahmens um das Pop-up-Fenster fest. | *Wenn auf #CCCCCC eingestellt:* Der Pop-up-Rahmen ist hellgrau. *Wenn auf transparent eingestellt:* Es wird kein sichtbarer Rahmen angezeigt. | #CCCCCC (Hellgrau) oder transparent | Sie möchten einen subtilen Rahmen, um das Pop-up zu definieren, daher wählen Sie ein Hellgrau. |
| **PopUp-Rahmenradius (Pixel)** | Steuert die Rundung der Ecken des Pop-up-Fensters. Ein Wert von 0 bedeutet scharfe Ecken, höhere Werte erzeugen rundere Ecken. | *Wenn auf 0 eingestellt:* Das Pop-up hat scharfe, quadratische Ecken. *Wenn auf 10 eingestellt:* Das Pop-up hat leicht abgerundete Ecken. | 5-10px | Sie bevorzugen ein weicheres, modernes Aussehen, daher stellen Sie den Rahmenradius auf 8px ein. |
| **Overlay-Hintergrundfarbe** | Legt die Farbe des abgedunkelten Hintergrunds fest, der hinter dem Pop-up erscheint. Dies hilft, die Aufmerksamkeit auf das Pop-up zu lenken. | *Wenn auf #000000 eingestellt:* Das Overlay ist schwarz. *Wenn auf #FFFFFF eingestellt:* Das Overlay ist weiß. | #000000 (Schwarz) | Sie möchten ein dunkles, transparentes Overlay, um das Pop-up klar vom Hauptinhalt zu trennen. |
| **Overlay-Deckkraft (0-1)** | Steuert die Transparenz des Overlay-Hintergrunds. 0 ist vollständig transparent, 1 ist vollständig undurchsichtig. | *Wenn auf 0.5 eingestellt:* Das Overlay ist 50% transparent. *Wenn auf 0.8 eingestellt:* Das Overlay ist 80% undurchsichtig. | 0.7-0.8 | Sie möchten, dass der Hintergrundinhalt leicht sichtbar, aber dennoch deutlich abgedunkelt ist, daher stellen Sie ihn auf 0.7 ein. |
| **Schaltflächenfarbe schließen** | Legt die Farbe der „X“- (Schließen-) Schaltfläche für das Pop-up fest. | *Wenn auf #000000 eingestellt:* Die Schließen-Schaltfläche ist schwarz. *Wenn auf #FF0000 eingestellt:* Die Schließen-Schaltfläche ist rot. | #000000 (Schwarz) | Ihr Shop verwendet eine rote Akzentfarbe, daher machen Sie die Schließen-Schaltfläche rot, um Konsistenz zu gewährleisten. |
| **Hintergrundfarbe der Schaltfläche schließen** | Legt die Hintergrundfarbe der „X“- (Schließen-) Schaltfläche fest. | *Wenn auf #FFFFFF eingestellt:* Der Hintergrund der Schließen-Schaltfläche ist weiß. *Wenn auf transparent eingestellt:* Es wird keine Hintergrundfarbe angewendet. | transparent | Sie möchten, dass die Schließen-Schaltfläche in das Pop-up übergeht, daher stellen Sie ihren Hintergrund auf transparent ein. |
| **Google reCAPTCHA aktivieren** | Aktiviert Google reCAPTCHA für die Anmelde- und Registrierungsformulare innerhalb des Pop-ups, um Spam und Bot-Registrierungen zu verhindern. | *Wenn aktiviert:* reCAPTCHA erscheint auf den Formularen und erfordert, dass Benutzer bestätigen, dass sie keine Roboter sind. *Wenn deaktiviert:* Es ist kein reCAPTCHA vorhanden. | JA (wenn Sie reCAPTCHA-Schlüssel haben) | Sie erhalten viele Spam-Registrierungen, daher aktivieren Sie reCAPTCHA, um diese herauszufiltern. |
| **reCAPTCHA-Site-Schlüssel** | Ihr öffentlicher reCAPTCHA-Site-Schlüssel, von Google erhalten. Erforderlich, wenn reCAPTCHA aktiviert ist. | *Wenn korrekt eingegeben:* reCAPTCHA funktioniert. *Wenn falsch oder leer:* reCAPTCHA funktioniert nicht, was möglicherweise legitime Benutzer blockiert oder Bots nicht verhindert. | Ihr tatsächlicher Google reCAPTCHA-Site-Schlüssel | Sie haben Ihre Website bei Google reCAPTCHA registriert und fügen den bereitgestellten Site-Schlüssel hier ein. |
| **reCAPTCHA-Geheimschlüssel** | Ihr privater reCAPTCHA-Geheimschlüssel, von Google erhalten. Erforderlich, wenn reCAPTCHA aktiviert ist. | *Wenn korrekt eingegeben:* reCAPTCHA funktioniert. *Wenn falsch oder leer:* reCAPTCHA funktioniert nicht. | Ihr tatsächlicher Google reCAPTCHA-Geheimschlüssel | Sie haben Ihre Website bei Google reCAPTCHA registriert und fügen den bereitgestellten Geheimschlüssel hier ein. |

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | PopUp Login aktivieren | JA | Aktiviert/deaktiviert die Pop-up-Login-Funktion. |
| Modulkonfiguration | PopUp-Formulartyp | (Wählen Sie basierend auf dem Design) | Wählt den visuellen Stil des Anmeldeformulars. |
| Modulkonfiguration | PopUp-Breite (Pixel) | 400-500px | Steuert die Breite des Pop-up-Fensters. |
| Modulkonfiguration | PopUp-Höhe (Pixel) | 300-450px | Steuert die Höhe des Pop-up-Fensters. |
| Modulkonfiguration | PopUp-Hintergrundfarbe | #FFFFFF | Legt die Hintergrundfarbe des Pop-ups fest. |
| Modulkonfiguration | PopUp-Rahmenfarbe | #CCCCCC oder transparent | Legt die Rahmenfarbe des Pop-ups fest. |
| Modulkonfiguration | PopUp-Rahmenradius (Pixel) | 5-10px | Steuert die Rundung der Pop-up-Ecken. |
| Modulkonfiguration | Overlay-Hintergrundfarbe | #000000 | Legt die Farbe des abgedunkelten Hintergrunds hinter dem Pop-up fest. |
| Modulkonfiguration | Overlay-Deckkraft (0-1) | 0.7-0.8 | Steuert die Transparenz des Overlay-Hintergrunds. |
| Modulkonfiguration | Schaltflächenfarbe schließen | #000000 | Legt die Farbe der Schließen-Schaltfläche des Pop-ups fest. |
| Modulkonfiguration | Hintergrundfarbe der Schaltfläche schließen | transparent | Legt die Hintergrundfarbe der Schließen-Schaltfläche fest. |
| Modulkonfiguration | Google reCAPTCHA aktivieren | JA (wenn Schlüssel verfügbar) | Aktiviert reCAPTCHA zum Bot-Schutz. |
| Modulkonfiguration | reCAPTCHA-Site-Schlüssel | Ihr tatsächlicher Schlüssel | Öffentlicher Schlüssel für die reCAPTCHA-Verifizierung. |
| Modulkonfiguration | reCAPTCHA-Geheimschlüssel | Ihr tatsächlicher Schlüssel | Privater Schlüssel für die reCAPTCHA-Verifizierung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Pop-up erscheint nicht, wenn ich auf „Anmelden“ klicke. Was soll ich tun?**
A:

1. **Modulstatus prüfen:** Stellen Sie sicher, dass die Einstellung „PopUp Login aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
2. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Modulfunktionen geladen werden.
3. **Theme-Kompatibilität:** Einige stark angepasste Themes verwenden möglicherweise nicht-standardmäßige Methoden zur Handhabung von Login-Links. Prüfen Sie, ob Ihr Theme spezifische Einstellungen oder Überschreibungen für den Login hat. Wenn Probleme weiterhin bestehen, wenden Sie sich an den MyPresta.eu-Support.

**F2: Das Pop-up sieht seltsam aus oder passt nicht zum Stil meines Themes.**
A:

1. **Stileinstellungen anpassen:** Gehen Sie zur Modulkonfiguration und experimentieren Sie mit „PopUp-Hintergrundfarbe“, „PopUp-Rahmenfarbe“, „PopUp-Rahmenradius“, „Overlay-Hintergrundfarbe“ und „Overlay-Deckkraft“.
2. **Formulartyp:** Probieren Sie verschiedene „PopUp-Formulartyp“-Optionen aus, um zu sehen, ob ein anderes Design besser zu Ihrem Theme passt.
3. **Benutzerdefiniertes CSS:** Wenn die Basiseinstellungen nicht ausreichen, muss Ihr Webmaster möglicherweise benutzerdefiniertes CSS zu Ihrem Theme hinzufügen, um die Standardstile des Moduls zu überschreiben (siehe Abschnitt 7.5 für Details zu CSS-Dateien).

**F3: reCAPTCHA funktioniert nicht auf den Pop-up-Formularen.**
A:

1. **reCAPTCHA aktivieren:** Stellen Sie sicher, dass „Google reCAPTCHA aktivieren“ auf JA gesetzt ist.
2. **Schlüssel prüfen:** Überprüfen Sie nochmals, ob Ihr „reCAPTCHA-Site-Schlüssel“ und „reCAPTCHA-Geheimschlüssel“ in der Modulkonfiguration korrekt eingegeben wurden. Diese sind Groß- und Kleinschreibung-sensitiv.
3. **Google reCAPTCHA-Einrichtung:** Stellen Sie sicher, dass Ihre Domain in Ihrem Google reCAPTCHA-Konto korrekt registriert ist.
4. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Änderungen an den reCAPTCHA-Einstellungen vorgenommen haben.

**F4: Das Pop-up ist auf meinem Mobiltelefon zu groß/klein.**
A:

1. **Breite/Höhe anpassen:** Ändern Sie „PopUp-Breite (Pixel)“ und „PopUp-Höhe (Pixel)“ in der Modulkonfiguration. Obwohl dies Pixelwerte sind, ist das Modul responsiv konzipiert, sodass die Anpassung dieser Werte seine Skalierung auf verschiedenen Geräten beeinflusst.
2. **Responsivität testen:** Verwenden Sie die Entwicklertools Ihres Browsers (F12), um verschiedene mobile Geräte zu simulieren und die Abmessungen fein abzustimmen.

**F5: Wie übersetze ich den Text im Pop-up?**
A:

1. **Modul übersetzen:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2. **Optionen auswählen:**
   - Art der Übersetzung: „Übersetzungen installierter Module“
   - Wählen Sie Ihr Theme: Ihr aktuelles Theme
   - Wählen Sie Ihre Sprache: Die Sprache, in die Sie übersetzen möchten
3. **Modul finden:** Suchen Sie nach „PopUp Login Pro“ (oder `popuplogin`).
4. **Felder übersetzen:** Sie finden alle übersetzbaren Zeichenketten, die vom Modul verwendet werden. Geben Sie Ihre Übersetzungen ein und speichern Sie.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul PopUp Login Pro folgt einer standardmäßigen PrestaShop-Modularchitektur, die hauptsächlich Front-Controller für AJAX-Anfragen und Hooks für die Integration in das Theme nutzt. Es verwendet JavaScript, um Klicks auf Standard-Login-Links abzufangen und das Pop-up anzuzeigen, wobei Inhalte dynamisch über AJAX geladen werden. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  - `controllers/front/index.php`
    - **Klassenname**: `PopUpLoginIndexModuleFrontController`
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als allgemeiner Einstiegspunkt oder behandelt die anfängliche Einrichtung für Front-Office-Interaktionen, obwohl seine spezifischen Methoden seine genaue Rolle definieren würden. Er könnte für das Rendern der anfänglichen Pop-up-Struktur oder die Bearbeitung von nicht-Login-bezogenen AJAX-Aufrufen verantwortlich sein.
  - `controllers/front/loginbox.php`
    - **Klassenname**: `PopUpLoginLoginBoxModuleFrontController`
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dies ist der Kern-Controller für die Verarbeitung der Login- und Registrierungsformularlogik. Er antwortet auf AJAX-Anfragen zum Anzeigen des Login-/Registrierungsformularinhalts, zur Verarbeitung von Login-Versuchen, zur Handhabung neuer Registrierungen und zur Verwaltung von „Passwort vergessen“-Anfragen. Er gibt wahrscheinlich HTML-Fragmente oder JSON-Antworten an das JavaScript zur dynamischen Einfügung in das Pop-up zurück.

### 4.3 Kernklassen & Modelle (`classes/`)

Basierend auf dem bereitgestellten Inventar gibt es keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/`. Das Modul nutzt wahrscheinlich bestehende PrestaShop-Kernklassen für die Kundenverwaltung (`Customer`, `Context`, `Tools`) und die Standardspeicherung von Konfigurationen.

### 4.4 JavaScript-Assets (`views/js/`)

- `popuplogin/popuplogin.js`
  - **Umfang**: Front-Office.
  - **Details**: Dies ist die primäre JavaScript-Datei für die Front-End-Funktionalität des Moduls.
    - **Event-Listener**: Sie bindet Event-Listener an verschiedene Elemente, am wichtigsten an Standard-Login-/Konto-Links (z. B. `a[href*="controller=authentication"]`, `a[href*="my-account"]`). Sie fängt Klickereignisse auf diesen Links ab.
    - **AJAX-Aufrufe**: Wenn ein Login-Link geklickt wird, verhindert sie die Standardnavigation und initiiert eine AJAX-Anfrage an `popuplogin/controllers/front/loginbox.php` (oder ähnliches), um das HTML des Login-/Registrierungsformulars abzurufen.
    - **DOM-Manipulation**: Sie erstellt und fügt das Pop-up-Overlay und den Login-Formularinhalt dynamisch in das DOM ein. Sie verwaltet das Anzeigen/Ausblenden des Pop-ups, die Verwaltung des Overlays und möglicherweise das Umschalten zwischen Login- und Registrierungsansichten innerhalb des Pop-ups.
    - **Formularübermittlung**: Sie fängt wahrscheinlich Formularübermittlungen innerhalb des Pop-ups (Login, Registrierung, Passwort vergessen) ab und sendet sie über AJAX an den `loginbox.php`-Controller, wobei die Antworten verarbeitet werden (z. B. Anzeigen von Erfolgs- oder Fehlermeldungen oder Weiterleitung nach erfolgreichem Login).
    - **UI/UX**: Verwaltet die visuellen Effekte des Pop-ups (z. B. Ein-/Ausblenden, Zentrieren).
    - **reCAPTCHA-Integration**: Wenn reCAPTCHA aktiviert ist, ist dieses Skript für das Rendern des reCAPTCHA-Widgets und das Einschließen seines Tokens in AJAX-Formularübermittlungen verantwortlich.

### 4.5 CSS-Stylesheets (`views/css/`)

- `popuplogin/css.css`
  - **Umfang**: Front-Office-Kunden-Styling.
  - **Details**: Diese Datei enthält wahrscheinlich allgemeine, grundlegende Stile für den Pop-up-Container, das Overlay und potenziell gemeinsame Formularelemente. Sie könnte Reset-Stile oder grundlegende Layoutregeln enthalten.
  - **Schlüsselselektoren**: `.popuplogin-overlay`, `.popuplogin-popup`, `.popuplogin-close-btn`.
- `popuplogin/popuplogin.css`
  - **Umfang**: Front-Office-Kunden-Styling.
  - **Details**: Diese Datei enthält wahrscheinlich die spezifischeren und detaillierteren Stile für die verschiedenen Pop-up-Formulartypen, einschließlich Eingabefelder, Schaltflächen, Fehlermeldungen und responsive Anpassungen. Sie definiert die visuellen Unterschiede zwischen den Optionen des „PopUp-Formulartyps“.
  - **Schlüsselselektoren**: `.popuplogin-form-type-1`, `.popuplogin-form-type-2`, `.popuplogin-input`, `.popuplogin-button`, `.popuplogin-error-message`.
  - **Entwickler-Override**: Entwickler können diese Stile in der `custom.css` ihres Themes oder durch Erstellen eines Child-Themes überschreiben, um das Erscheinungsbild zu ändern, ohne die Moduldateien direkt zu bearbeiten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `popuplogin/dashboardZoneOne.tpl`
    - **Hook**: Wahrscheinlich `displayDashboardZoneOne` (oder ähnlicher Dashboard-Hook).
    - **Zweck**: Dieses Template dient wahrscheinlich dazu, einen kleinen Informationsblock oder schnelle Statistiken zum Modul PopUp Login Pro auf dem PrestaShop Back Office Dashboard anzuzeigen. Es ist ein Admin-seitiges Template.
  - `popuplogin/displayPopUpLogin.tpl`
    - **Hook**: Dieses Template wird wahrscheinlich vom `loginbox.php`-Front-Controller gerendert und enthält die eigentliche HTML-Struktur für das Anmelde-/Registrierungsformular, das im Pop-up erscheint. Es ist nicht direkt in einen `display`-Hook im Theme eingebunden, sondern wird dynamisch geladen.
    - **Zweck**: Rendert die Anmelde-, Registrierungs- und Passwort-vergessen-Formulare, einschließlich Eingabefeldern, Schaltflächen und potenziellen reCAPTCHA-Platzhaltern.
  - `popuplogin/header.tpl`
    - **Hook**: Wahrscheinlich `displayHeader`.
    - **Zweck**: Dieses Template ist dafür verantwortlich, die CSS- und JavaScript-Dateien des Moduls (`popuplogin.js`, `css.css`, `popuplogin.css`) in den `<head>`-Bereich der Front-Office-Seiten einzufügen, um sicherzustellen, dass sie geladen werden, bevor die Funktionalität des Moduls ausgelöst wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel typischerweise mit `POPUPLOGIN_` beginnen (z. B. `POPUPLOGIN_ENABLED`, `POPUPLOGIN_FORM_TYPE`, `POPUPLOGIN_WIDTH`, `POPUPLOGIN_RECAPTCHA_SITE_KEY`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt die CSS- und JavaScript-Dateien des Moduls für die Front-End-Funktionalität ein. |
| `displayDashboardZoneOne` | Auf dem PrestaShop Back Office Dashboard. | Zeigt einen Informationsblock oder ein Widget für das Modul im Admin-Panel an. |
| (Implizite Hooks) | Ausgelöst durch JavaScript-Abfangen von Standard-Login-Links. | Das JavaScript des Moduls fängt Klicks auf Elemente ab, die normalerweise zu `authentication`- oder `my-account`-Controllern führen würden, und verwendet dann AJAX, um Inhalte dynamisch von seinen eigenen Front-Controllern zu laden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul PopUp Login Pro verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul perfekt funktioniert und sich nahtlos in Ihren PrestaShop-Shop integriert.
