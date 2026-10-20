---
title: "Kontenaktivierung per E-Mail-Link – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Kontenaktivierung per E-Mail-Link' von MyPresta.eu."
sidebar:
  label: "Kontenaktivierung per E-Mail-Link – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Account activation by email link auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/account-activation-by-email-link.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/account-activation-by-email-link/)
>
> ---


# Kontenaktivierung per E-Mail-Link

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind in der Regel keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Kontenaktivierung per E-Mail-Link“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren und neben dem Modulnamen auf „Konfigurieren“ klicken.

#### **Allgemeine Einstellungen**

- **E-Mail mit Kontenaktivierungslink an den Administrator senden:**

  - **Was diese Einstellung bewirkt:** Steuert, ob auch eine E-Mail-Benachrichtigung an den Shop-Administrator (Sie) gesendet wird, jedes Mal, wenn ein neuer Kunde sich registriert und sein Konto aktivieren muss.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Sie erhalten eine E-Mail-Benachrichtigung an die primäre Kontakt-E-Mail-Adresse Ihres Shops (normalerweise `PS_SHOP_EMAIL`), wenn ein neuer Kunde sich registriert und auf die Aktivierung wartet. Dies kann nützlich sein, um neue Registrierungen zu überwachen.
    - *Wenn deaktiviert („Aus“):* Es wird keine E-Mail-Benachrichtigung an den Administrator bei neuen Kundenregistrierungen gesendet.
  - **Empfohlener Wert:** „Aus“ für die meisten Shops, um E-Mail-Überflutung zu vermeiden, es sei denn, Sie müssen jede neue Registrierung speziell überwachen.
  - **Händlerszenario / Beispiel:** Wenn Sie einen kleinen Nischen-Shop betreiben und jeden neuen Kunden persönlich begrüßen oder überprüfen möchten, kann die Aktivierung dieser Option Sie auf dem Laufenden halten. Für größere Shops ist dies in der Regel unnötig.
- **Titel der E-Mail an den Administrator:**

  - **Was diese Einstellung bewirkt:** Definiert die Betreffzeile der E-Mail, die an den Administrator gesendet wird, wenn ein neues Konto registriert wird (falls „E-Mail mit Kontenaktivierungslink an den Administrator senden“ aktiviert ist).
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Betreffzeile der Admin-Benachrichtigungs-E-Mail.
  - **Empfohlener Wert:** „Neue Kundenregistrierung wartet auf Aktivierung - {shop\_name}“ (oder ähnlich, wobei `{shop_name}` für den Namen Ihres Shops steht).
  - **Händlerszenario / Beispiel:** Sie möchten möglicherweise den Namen Ihres Shops im Titel angeben, um ihn in Ihrem Posteingang leicht identifizieren zu können, z. B. „Neuer Kunde bei Mein Toller Shop - Aktivierung ausstehend.“
- **Kunden nach Aktivierung automatisch anmelden:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob ein Kunde sofort nach dem Klicken auf den Aktivierungslink in seiner E-Mail automatisch in sein Konto eingeloggt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Nach dem Klicken auf den Aktivierungslink wird der Kunde nahtlos in sein neu aktiviertes Konto eingeloggt und typischerweise zu seinem Konten-Dashboard oder der Startseite weitergeleitet. Dies bietet ein reibungsloseres Benutzererlebnis.
    - *Wenn deaktiviert („Aus“):* Nach dem Klicken auf den Aktivierungslink wird das Konto des Kunden aktiviert, aber er wird *nicht* automatisch eingeloggt. Er wird zur Anmeldeseite weitergeleitet und aufgefordert, seine Anmeldeinformationen manuell einzugeben.
  - **Empfohlener Wert:** „An“ für ein besseres Kundenerlebnis, um Reibung zu reduzieren.
  - **Händlerszenario / Beispiel:** Die Aktivierung dieser Option lässt den Aktivierungsprozess vollständiger und benutzerfreundlicher erscheinen, da der Kunde nach der Überprüfung seiner E-Mail keinen zusätzlichen Schritt unternehmen muss.
- **Konto auf spezifischer Seite aktivieren:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, eine bestimmte Seite in Ihrem Shop zu definieren, auf die der Kunde *nachdem* sein Konto erfolgreich aktiviert wurde, weitergeleitet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Das Modul verwendet die im Feld „Link zur spezifischen Aktivierungsseite“ angegebene URL für die Weiterleitung nach der Aktivierung.
    - *Wenn deaktiviert („Aus“):* Der Kunde wird nach der Aktivierung auf die Standardseite (normalerweise die Startseite oder seine Kundenkontoseite) weitergeleitet.
  - **Empfohlener Wert:** Standardmäßig „Aus“, es sei denn, Sie haben eine spezifische Marketing- oder Onboarding-Strategie.
  - **Händlerszenario / Beispiel:** Sie möchten neue Kunden möglicherweise auf eine „Willkommensseite“ mit Sonderangeboten, einem Leitfaden zu Ihrem Shop oder einer bestimmten Produktkategorie weiterleiten, um ihren ersten Kauf zu fördern.
- **Link zur spezifischen Aktivierungsseite:**

  - **Was diese Einstellung bewirkt:** Dieses Feld erscheint nur, wenn „Konto auf spezifischer Seite aktivieren“ aktiviert ist. Hier geben Sie die vollständige URL der Seite ein, auf die Sie Kunden nach der Aktivierung weiterleiten möchten.
  - **Auswirkung der Änderung dieser Einstellung:** Definiert die genaue Ziel-URL für die Weiterleitung nach der Aktivierung.
  - **Empfohlener Wert:** Leer lassen, wenn „Konto auf spezifischer Seite aktivieren“ „Aus“ ist. Wenn aktiviert, geben Sie eine vollständige, gültige URL an (z. B. `https://ihrshop.com/content/1-lieferung`).
  - **Händlerszenario / Beispiel:** Wenn Sie eine „Willkommensseite für neue Kunden“ unter `https://ihrshop.com/willkommen-neue-kunden` haben, würden Sie diese URL hier eingeben.

#### **E-Mail-Inhaltseinstellungen**

- **Titel der E-Mail an den Kunden:**
  - **Was diese Einstellung bewirkt:** Definiert die Betreffzeile der Aktivierungs-E-Mail, die an den Kunden gesendet wird.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Betreffzeile, die Kunden in ihrem Posteingang für die Aktivierungs-E-Mail sehen.
  - **Empfohlener Wert:** „Aktivieren Sie Ihr Konto bei {shop\_name}“ oder „Bitte bestätigen Sie Ihre E-Mail für {shop\_name}“ (wobei `{shop_name}` für den Namen Ihres Shops steht).
  - **Händlerszenario / Beispiel:** Eine klare und prägnante Betreffzeile hilft Kunden, die E-Mail zu identifizieren und ermutigt sie, sie zu öffnen, wodurch die Wahrscheinlichkeit verringert wird, dass sie als Spam markiert wird.

#### **Weitere Einstellungen (Intern / Technisch)**

- **mypresta\_updates, update\_, updatev\_:** Dies sind interne Einstellungen, die von MyPresta.eu-Modulen für Update-Prüfungen und Versionsverwaltung verwendet werden. Sie sollten diese im Allgemeinen **nicht** ändern.
- **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Dies sind Standard-PrestaShop-Konfigurationswerte, die das Modul zur Kontextanzeige lesen oder anzeigen kann, aber nicht direkt im Modul selbst konfigurierbar sind. Sie spiegeln Ihre allgemeinen PrestaShop-Einstellungen wider.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | E-Mail mit Kontenaktivierungslink an den Administrator senden | Aus | Steuert die Admin-Benachrichtigung für neue Registrierungen. |
| Modulkonfiguration | Titel der E-Mail an den Administrator | „Neue Kundenregistrierung wartet auf Aktivierung - {shop\_name}“ | Betreffzeile für die Admin-Benachrichtigungs-E-Mail. |
| Modulkonfiguration | Kunden nach Aktivierung automatisch anmelden | An | Meldet den Kunden nach erfolgreicher Aktivierung automatisch an. |
| Modulkonfiguration | Konto auf spezifischer Seite aktivieren | Aus | Ermöglicht die Weiterleitung zu einer benutzerdefinierten Seite nach der Aktivierung. |
| Modulkonfiguration | Link zur spezifischen Aktivierungsseite | (Leer, wenn deaktiviert) | URL für die Weiterleitung nach der Aktivierung (falls aktiviert). |
| Modulkonfiguration | Titel der E-Mail an den Kunden | „Aktivieren Sie Ihr Konto bei {shop\_name}“ | Betreffzeile für die Kundenaktivierungs-E-Mail. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten die Aktivierungs-E-Mail nicht. Was soll ich tun?**

- **A:**
  1. **Spam-/Junk-Ordner überprüfen:** Raten Sie Kunden, ihre Spam- oder Junk-Mail-Ordner zu überprüfen.
  2. **Shop-E-Mail-Einstellungen überprüfen:** Gehen Sie im PrestaShop Back Office zu **Shop-Parameter > Kontakt > Shops** (oder **Erweiterte Parameter > E-Mail** in älteren Versionen). Stellen Sie sicher, dass die E-Mail-Konfiguration Ihres Shops korrekt ist und dass E-Mails erfolgreich gesendet werden (testen Sie dies, indem Sie eine Test-E-Mail senden).
  3. **Server-Mail-Funktionalität:** Kontaktieren Sie Ihren Hosting-Anbieter, um sicherzustellen, dass die Mail-Funktion Ihres Servers (PHP `mail()` oder SMTP) korrekt funktioniert und nicht blockiert wird.
  4. **Modulkonfiguration:** Überprüfen Sie den „Titel der E-Mail an den Kunden“ in den Moduleinstellungen. Ein sehr generischer oder verdächtig aussehender Titel könnte Spamfilter auslösen.
  5. **Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal können Caching-Probleme das Senden von E-Mails verhindern.

**F2: Ein Kunde hat sein Konto aktiviert, kann sich aber immer noch nicht anmelden.**

- **A:**
  1. **Kundenstatus überprüfen:** Gehen Sie in Ihrem PrestaShop Back Office zu **Kunden > Kunden**. Suchen Sie das Konto des Kunden und überprüfen Sie, ob sein Status „Aktiviert“ auf „Ja“ gesetzt ist. Falls nicht, aktivieren Sie es manuell.
  2. **Passwort zurücksetzen:** Schlagen Sie dem Kunden vor, den Link „Passwort vergessen“ auf Ihrer Anmeldeseite zu verwenden. Dies kann Probleme beheben, wenn er sein Passwort falsch erinnert.
  3. **Browser-Cache/Cookies:** Bitten Sie den Kunden, den Cache und die Cookies seines Browsers zu löschen oder sich von einem anderen Browser oder im Inkognito-Modus anzumelden.
  4. **Modulkonflikt:** Deaktivieren Sie vorübergehend andere Module, die mit Kundenkonten oder Anmeldevorgängen interagieren, um Konflikte auszuschließen.

**F3: Wie kann ich ein Kundenkonto manuell aktivieren, wenn der Kunde die E-Mail nicht erhalten kann?**

- **A:** Sie können ein Kundenkonto manuell über das PrestaShop Back Office aktivieren:
  1. Gehen Sie zu **Kunden > Kunden**.
  2. Suchen Sie den Namen des Kunden in der Liste und klicken Sie auf „Bearbeiten“ (das Bleistiftsymbol).
  3. Auf der Detailseite des Kunden suchen Sie den Schalter „Aktiviert“ und setzen ihn auf „Ja“.
  4. Klicken Sie auf „Speichern“. Der Kunde kann sich nun anmelden.

**F4: Der Aktivierungslink leitet auf die falsche Seite weiter oder zeigt einen Fehler an.**

- **A:**
  1. **„Link zur spezifischen Aktivierungsseite“ überprüfen:** Wenn Sie „Konto auf spezifischer Seite aktivieren“ aktiviert haben, überprüfen Sie, ob die im Feld „Link zur spezifischen Aktivierungsseite“ eingegebene URL absolut korrekt und zugänglich ist. Ein Tippfehler oder eine ungültige URL führt zu Weiterleitungsproblemen.
  2. **Friendly URLs:** Stellen Sie sicher, dass Ihre Friendly URLs aktiviert sind und korrekt funktionieren (**Shop-Parameter > Traffic & SEO**).
  3. **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung**).
  4. **.htaccess überprüfen:** Wenn Sie manuelle Änderungen an Ihrer `.htaccess`-Datei vorgenommen haben, machen Sie diese rückgängig oder stellen Sie sicher, dass sie die URL-Umschreibung nicht beeinträchtigen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Kontenaktivierung per E-Mail-Link“ (`acactiv`) ist ein Standard-PrestaShop-Modul, das hauptsächlich dazu dient, den Kundenregistrierungsprozess abzufangen. Es nutzt das Hook-System von PrestaShop, um das Standardverhalten zu ändern, insbesondere `actionCustomerAccountAdd`, um neue Konten als inaktiv zu markieren und Aktivierungs-E-Mails zu senden, und `displayHeader`, um notwendiges JavaScript einzufügen. Das Modul führt keine neuen Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, sondern verlässt sich auf die Änderung bestehender `Customer`-Objekteigenschaften und die Verwendung von `ps_configuration` für seine Einstellungen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei (`acactiv.php`) und ihrer registrierten Hooks behandelt. Der Aktivierungslink selbst verweist auf den Haupt-Dispatch des Moduls, der dann die Aktivierungslogik verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` ein. Es interagiert direkt mit den Kernklassen `Customer` und `Configuration` von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

- **`acactiv/views/acactiv-compat.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript enthält wahrscheinlich Kompatibilitätskorrekturen oder Polyfills für ältere PrestaShop-Versionen oder Browser, um sicherzustellen, dass die Front-End-Funktionalität des Moduls in einer breiteren Palette von Umgebungen funktioniert. Es könnte Unterschiede in jQuery-Versionen oder DOM-Manipulationsmethoden adressieren.
  - **Event-Listener/DOM-Manipulation:** Spezifika würden eine Code-Überprüfung erfordern, aber typischerweise geht es darum, sicherzustellen, dass Elemente vorhanden sind oder Verhaltensweisen basierend auf der PrestaShop-Version angepasst werden.
- **`acactiv/views/acactiv.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dies ist die Haupt-JavaScript-Datei für Front-Office-Interaktionen. Sie ist verantwortlich für die Anzeige von Nachrichten an den Benutzer nach der Registrierung (z. B. „Überprüfen Sie Ihre E-Mails auf den Aktivierungslink“) und möglicherweise für die Behandlung von clientseitigen Aspekten des Aktivierungsprozesses.
  - **Event-Listener/DOM-Manipulation:**
    - Kann auf Formularübermittlungen auf der Registrierungsseite lauschen, um benutzerdefinierte Nachrichten anzuzeigen.
    - Könnte das DOM manipulieren, um Elemente anzuzeigen/auszublenden, Pop-up-Benachrichtigungen anzuzeigen oder den Benutzer nach bestimmten Aktionen umzuleiten.
    - Könnte `prestashop.on('updatedProduct', function(event) { ... });` oder ähnliche PrestaShop-Event-Listener verwenden, wenn es auf dynamische Inhaltsaktualisierungen reagieren muss, obwohl dies für die Kernfunktion dieses Moduls weniger wahrscheinlich ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`acactiv/views/acactiv.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Zweck:** Bietet grundlegendes Styling für alle benutzerdefinierten Nachrichten oder Elemente, die das Modul im Front Office einführt. Dies könnte das Styling für die Nachricht „Konto wartet auf Aktivierung“ oder die Bestätigung „Konto aktiviert“ umfassen.
  - **Wichtige CSS-Klassenselektoren:** Entwickler sollten den HTML-Output des Moduls überprüfen, um spezifische Klassen (z. B. `.acactiv-message`, `.acactiv-success`, `.acactiv-error`) zu identifizieren, die in der `custom.css` oder `theme.css` ihres Themes überschrieben werden können, um dem Branding des Shops zu entsprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - **`acactiv/views/checkout_notice.tpl`**
    - **Hook:** Nicht explizit als Hook-Template angegeben, aber der Name deutet darauf hin, dass es in einem Kontext im Zusammenhang mit dem Checkout oder der Kontoerstellung gerendert werden könnte, möglicherweise über `displayCustomerAccountForm` oder ähnliches, um einen Hinweis zur Aktivierung anzuzeigen.
    - **Ausgabe:** Gibt wahrscheinlich eine Informationsnachricht an den Kunden nach der Registrierung aus, die ihn anweist, seine E-Mails auf den Aktivierungslink zu überprüfen.
  - **`acactiv/views/displayHeader.tpl`**
    - **Hook:** `displayHeader`
    - **Ausgabe:** Dieses Template wird typischerweise verwendet, um CSS- und JavaScript-Dateien im `<head>`-Bereich der Front-Office-Seiten einzubinden. Es enthält `<link>`-Tags für `acactiv.css` und `<script>`-Tags für `acactiv-compat.js` und `acactiv.js`, um sicherzustellen, dass diese Assets auf relevanten Seiten geladen werden.
- **Admin-Templates (`views/templates/admin/`)**: Keine identifiziert. Die Konfiguration wird direkt in `getContent()` innerhalb von `acactiv.php` behandelt.
- **Front-Office-Templates (`views/templates/front/`)**: Keine als dedizierte eigenständige Seiten identifiziert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es ändert die Spalte `active` der Tabelle `ps_customer` (setzt sie für neue Registrierungen auf `0`, bis sie aktiviert werden).
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` mit Schlüsseln wie `ACACTIV_SENDTOME`, `ACACTIV_SPECURLFEATURE`, `ACACTIV_SPECURL`, `ACACTIV_AUTOLOGIN`, `ACACTIV_ATITLE`, `ACACTIV_CTITLE` gespeichert.
- **Registrierte Hooks-Tabelle**:
