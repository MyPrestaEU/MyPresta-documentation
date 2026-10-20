---
title: "Benachrichtigung über neues Kundenkonto - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Benachrichtigung über neues Kundenkonto“ von MyPresta.eu."
sidebar:
  label: "Benachrichtigung über neues Kundenkonto - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Notification about new customer account auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/notification-about-new-customer-account.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/notification-about-new-customer-account/)
>
> ---


# Benachrichtigung über neues Kundenkonto

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Benachrichtigung über neues Kundenkonto“. Sie gelangen zur Hauptkonfigurationsseite.

#### **1. Benachrichtigung an den Shop-Inhaber über neues Kundenkonto senden**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob Sie als Shop-Inhaber eine E-Mail-Benachrichtigung erhalten, wenn sich ein neuer Kunde in Ihrem Shop registriert.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Jedes Mal, wenn ein Kunde erfolgreich ein Konto im Front Office Ihres Shops erstellt, wird eine E-Mail an die im Feld „E-Mail-Adresse(n) für Benachrichtigungen“ unten angegebene(n) E-Mail-Adresse(n) gesendet.
  - *Wenn deaktiviert (NEIN):* Sie erhalten keine E-Mail-Benachrichtigungen über neue Kundenregistrierungen.
- **Empfohlener Wert:** JA.
- **Händlerszenario / Beispiel:** Sie möchten sofort über neue Kundenanmeldungen informiert werden, um das Wachstum zu verfolgen oder potenzielle Leads für eine Willkommenskampagne zu identifizieren. Die Aktivierung dieser Option stellt sicher, dass Sie diese wichtigen Informationen erhalten.

#### **2. E-Mail-Adresse(n) für Benachrichtigungen**

- **Was diese Einstellung bewirkt:** Dieses Feld gibt die E-Mail-Adresse(n) an, an die die Benachrichtigungen über neue Kundenregistrierungen gesendet werden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn eine oder mehrere E-Mail-Adressen festgelegt sind:* Benachrichtigungen werden an diese Adressen zugestellt. Wenn Sie mehrere Adressen eingeben, trennen Sie diese durch ein Komma (z. B. `admin@ihrshop.com, support@ihrshop.com`).
  - *Wenn leer gelassen:* Auch wenn „Benachrichtigung an Shop-Inhaber senden“ aktiviert ist, werden keine E-Mails gesendet, da kein Empfänger vorhanden ist.
- **Empfohlener Wert:** Ihre primäre E-Mail-Adresse für die Shop-Verwaltung oder eine dedizierte Team-E-Mail (z. B. `info@ihrshop.com`).
- **Händlerszenario / Beispiel:** Sie möchten, dass sowohl Sie als auch Ihr Kundensupport-Team neue Registrierungsbenachrichtigungen erhalten. Sie würden hier `ihrname@ihrshop.com, support@ihrshop.com` eingeben.

#### **3. Benachrichtigung an Kunden senden, wenn Admin neues Konto erstellt**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob eine Willkommens-E-Mail automatisch an einen Kunden gesendet wird, wenn dessen Konto manuell von einem Administrator im PrestaShop Back Office erstellt wird (z. B. über Kunden > Neuen Kunden hinzufügen).
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Wenn Sie oder ein anderer Administrator ein neues Kundenkonto im Back Office erstellen, erhält der neu erstellte Kunde automatisch eine Willkommens-E-Mail. Diese E-Mail enthält typischerweise seine Anmeldedaten oder eine Bestätigung der Kontoerstellung.
  - *Wenn deaktiviert (NEIN):* Kunden, deren Konten manuell im Back Office erstellt werden, erhalten keine automatische Willkommens-E-Mail vom Modul. Sie müssten sie bei Bedarf manuell informieren.
- **Empfohlener Wert:** JA.
- **Händlerszenario / Beispiel:** Sie erstellen häufig Konten für B2B-Kunden oder für Kunden, die Bestellungen telefonisch aufgeben. Die Aktivierung dieser Option stellt sicher, dass sie eine sofortige, professionelle Willkommens-E-Mail erhalten, ohne dass Sie jedes Mal eine manuell verfassen und senden müssen.

#### **4. Speichern-Schaltfläche**

- **Was dies bewirkt:** Nachdem Sie Änderungen an den oben genannten Einstellungen vorgenommen haben, müssen Sie diese Schaltfläche anklicken, um Ihre neue Konfiguration anzuwenden und zu speichern.
- **Auswirkung des Klicks:** Ihre Änderungen werden in der Datenbank gespeichert, und das Modul beginnt sofort, gemäß den neuen Einstellungen zu arbeiten.
- **Empfohlene Aktion:** Klicken Sie immer auf „Speichern“, nachdem Sie eine Einstellung geändert haben.

### 2.2 Kurzübersicht der Konfigurationstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Benachrichtigung an den Shop-Inhaber über neues Kundenkonto senden | JA | Steuert, ob der Shop-Inhaber eine E-Mail bei Neukundenregistrierung erhält. |
| Modulkonfiguration | E-Mail-Adresse(n) für Benachrichtigungen | Haupt-E-Mail Ihres Shops | Gibt den/die Empfänger für Inhaberbenachrichtigungen an (kommagetrennt). |
| Modulkonfiguration | Benachrichtigung an Kunden senden, wenn Admin neues Konto erstellt | JA | Steuert, ob der Kunde eine Willkommens-E-Mail erhält, wenn der Admin sein Konto erstellt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich erhalte keine Benachrichtigungen über neue Kunden, obwohl das Modul aktiviert ist. Was sollte ich überprüfen?**
A1:

- **E-Mail-Adressen überprüfen:** Überprüfen Sie das Feld „E-Mail-Adresse(n) für Benachrichtigungen“ in der Modulkonfiguration. Stellen Sie sicher, dass es korrekt eingegeben wurde und keine Tippfehler enthält. Wenn mehrere Adressen vorhanden sind, stellen Sie sicher, dass sie kommagetrennt sind.
- **Spam-Ordner:** Überprüfen Sie den Spam- oder Junk-Ordner Ihres E-Mail-Kontos. Die Benachrichtigungen könnten dort gefiltert werden.
- **PrestaShop E-Mail-Einstellungen:** Überprüfen Sie, ob die Haupteinstellungen für E-Mails in Ihrem PrestaShop (Erweiterte Einstellungen > E-Mail) korrekt konfiguriert sind und E-Mails erfolgreich gesendet werden. Sie können von dort aus eine Test-E-Mail senden.
- **Hosting-E-Mail-Probleme:** Kontaktieren Sie Ihren Hosting-Anbieter, um sicherzustellen, dass keine serverseitigen Einschränkungen beim E-Mail-Versand oder Probleme mit Ihrem Mailserver vorliegen.

**F2: Meine Kunden erhalten keine Willkommens-E-Mails, wenn ich ihre Konten im Back Office erstelle.**
A2:

- **Moduleinstellung:** Stellen Sie sicher, dass „Benachrichtigung an Kunden senden, wenn Admin neues Konto erstellt“ in der Modulkonfiguration auf JA gesetzt ist.
- **Kunden-E-Mail:** Überprüfen Sie, ob die im Back Office für den Kunden eingegebene E-Mail-Adresse korrekt und gültig ist.
- **Kunden-Spam-Ordner:** Weisen Sie den Kunden an, seinen Spam- oder Junk-Ordner zu überprüfen.
- **PrestaShop E-Mail-Einstellungen:** Wie oben, stellen Sie sicher, dass die allgemeinen E-Mail-Einstellungen Ihres Shops funktionieren.

**F3: Kann ich den Inhalt der Benachrichtigungs-E-Mails anpassen?**
A3: Dieses Modul sendet in seiner aktuellen Version standardmäßige PrestaShop-System-E-Mails. Das Anpassen des Inhalts würde typischerweise eine direkte Änderung der PrestaShop-E-Mail-Vorlagen (zu finden im Verzeichnis `mails/` für Ihre Sprache) oder des Kerncodes des Moduls erfordern, was für Händler nicht empfohlen wird. Für fortgeschrittene Anpassungen konsultieren Sie einen Entwickler.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
A4: Nein. Dieses Modul führt eine sehr leichte Operation (das Senden einer E-Mail) nur dann aus, wenn ein neues Kundenkonto erstellt wird. Es verursacht keinen zusätzlichen Overhead bei Seitenladevorgängen oder der allgemeinen Shop-Performance.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Benachrichtigung über neues Kundenkonto“ arbeiten.

### 4.1 Architekturübersicht

Das Modul `registernotification` ist ein Standard-PrestaShop-Modul, das dem MVC-ähnlichen Muster folgt. Es nutzt hauptsächlich das Hook-System von PrestaShop, um Ereignisse im Zusammenhang mit der Kundenregistrierung abzufangen, und verwendet dann die PrestaShop-Klasse `Mail`, um Benachrichtigungen zu senden. Es speichert seine Konfiguration direkt in der Tabelle `ps_configuration`.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmodulklasse und ihrer Methode `getContent()` für die Konfiguration gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Die gesamte Kernlogik befindet sich in der Hauptklasse `registernotification`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Es verlässt sich auf die Standard-E-Mail-Vorlagen von PrestaShop für Kundenbenachrichtigungen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die mit `REGISTERNOTIFICATION_` beginnen.

  - `PS_CONFIGURATION`-Einträge:
    - `REGISTERNOTIFICATION_SEND_OWNER`: Speichert den booleschen Wert (0 oder 1) für das Senden von Benachrichtigungen an den Shop-Inhaber.
    - `REGISTERNOTIFICATION_EMAIL_ADDRESSES`: Speichert die kommagetrennte Zeichenfolge der E-Mail-Adressen für Inhaberbenachrichtigungen.
    - `REGISTERNOTIFICATION_SEND_CUSTOMER_ADMIN`: Speichert den booleschen Wert (0 oder 1) für das Senden von Benachrichtigungen an Kunden, wenn diese von einem Administrator erstellt wurden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Wird sofort ausgeführt, nachdem ein neues Kundenkonto erfolgreich zur Datenbank hinzugefügt wurde. | Dieser Hook wird verwendet, um die E-Mail-Benachrichtigung an den Shop-Inhaber auszulösen, wenn sich ein Kunde über das Front Office registriert. Er löst auch die Willkommens-E-Mail an den Kunden aus, wenn dessen Konto von einem Administrator im Back Office erstellt wurde. |
| `displayBackOfficeHeader` | Wird ausgeführt, wenn der Back Office-Header gerendert wird. | Wird typischerweise zum Hinzufügen von CSS/JS oder zum Anzeigen von Warnungen im Back Office verwendet. Obwohl als potenzieller Hook aufgeführt, wäre seine primäre Verwendung in diesem Modul das Anzeigen einer Erfolgs-/Fehlermeldung nach dem Speichern der Konfiguration oder möglicherweise das Hinzufügen modulspezifischer Assets (obwohl keine vorhanden sind). |

### 4.8 Modul-Dateistruktur (`registernotification/`)

- `index.php`: Die Hauptmoduldatei. Diese Datei enthält die Klasse `registernotification`, die `Module` erweitert. Sie behandelt:
  - `__construct()`: Modulinitialisierung, Festlegen von Name, Tab, Version, Autor usw.
  - `install()`: Registriert notwendige Hooks (`actionCustomerAccountAdd`, `displayBackOfficeHeader`) und setzt Standardkonfigurationswerte in `ps_configuration`.
  - `uninstall()`: Deregistriert Hooks und löscht Konfigurationswerte.
  - `getContent()`: Rendert das Konfigurationsformular des Moduls im Back Office, verarbeitet die Formularübermittlung und aktualisiert `ps_configuration`.
  - `hookActionCustomerAccountAdd($params)`: Die Kernlogik zum Senden von E-Mails. Sie überprüft die Modulkonfiguration und verwendet `Mail::Send()`, um E-Mails an den Inhaber und/oder den neuen Kunden basierend auf dem Kontext der Kontoerstellung zu versenden.
  - `hookDisplayBackOfficeHeader()`: Potenziell zur Anzeige von Bestätigungsmeldungen nach dem Speichern der Konfiguration verwendet.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Benachrichtigung über neues Kundenkonto“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
