---
title: "Gutschein-Erinnerung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Gutschein-Erinnerung von MyPresta.eu."
sidebar:
  label: "Gutschein-Erinnerung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Voucher Reminder auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/voucher-reminder.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/voucher-reminder/)
>
> ---


# Gutschein-Erinnerung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Der Zugriff zum Einrichten eines Cron-Jobs auf Ihrem Server ist für den automatischen Betrieb des Moduls unerlässlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation sehen Sie als ersten Bildschirm die Hauptkonfigurationsseite für das Modul Gutschein-Erinnerung. Diese Seite ist entscheidend für die Einrichtung der Kernfunktionalität.

**Cron-Job-URL:**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die der Cron-Job Ihres Servers regelmäßig aufrufen muss. Diese URL veranlasst das Modul, nach ablaufenden Gutscheinen zu suchen und Erinnerungen zu versenden.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert. Wenn der Cron-Job auf Ihrem Server nicht korrekt eingerichtet ist, um diese URL aufzurufen, sendet das Modul keine Erinnerungen automatisch.
- **Empfohlener Wert:** Kopieren Sie diese URL genau und verwenden Sie sie, um einen Cron-Job auf Ihrem Hosting-Server einzurichten.
- **Händlerszenario / Beispiel:** Sie haben mehrere Erinnerungsregeln erstellt, aber es werden keine E-Mails gesendet. Das erste, was Sie überprüfen sollten, ist, ob Sie den Cron-Job auf Ihrem Server mit dieser URL korrekt eingerichtet haben.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Gutschein-Erinnerungen-Verwaltung (Back Office > Module > Gutschein-Erinnerung > Gutschein-Erinnerungen)

Hier definieren und verwalten Sie die eigentlichen Erinnerungsregeln. Jede Regel legt fest, wann eine Erinnerung gesendet werden soll und welche E-Mail-Vorlage sie verwenden soll.

- **Bildschirmname & Menüposition:** **Gutschein-Erinnerungen** (unter **Module > Gutschein-Erinnerung** im Hauptmenü von PrestaShop).
- **Verfügbare Aktionen & Einstellungen:**
  - **Liste der Erinnerungen:** Sie sehen eine Tabelle mit all Ihren definierten Erinnerungsregeln.
  - **Neue Erinnerung hinzufügen:** Klicken Sie auf die Schaltfläche „Neu hinzufügen“, um eine neue Erinnerungsregel zu erstellen.
    - **Erinnern (Stunden vor Ablauf):**
      - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung für eine Erinnerungsregel. Sie bestimmt, wie viele Stunden *vor* dem Ablaufdatum eines Gutscheins die Erinnerungs-E-Mail gesendet werden soll.
      - **Auswirkung einer Änderung dieser Einstellung:**
        - *Auf 24 gesetzt:* Eine Erinnerungs-E-Mail wird genau 24 Stunden vor Ablauf des Gutscheins gesendet.
        - *Auf 72 gesetzt:* Eine Erinnerungs-E-Mail wird 3 Tage (72 Stunden) vor Ablauf gesendet.
      - **Empfohlener Wert:** Dies hängt von Ihrer Strategie ab. Gängige Werte sind 24, 48, 72 Stunden oder sogar 168 Stunden (1 Woche).
      - **Händlerszenario / Beispiel:** Sie möchten Kunden einen letzten Anstoß einen Tag vor Ablauf ihres Gutscheins geben. Sie würden dies auf `24` setzen. Wenn Sie ihnen eine Woche Vorlaufzeit geben möchten, würden Sie es auf `168` setzen.
    - **Titel:**
      - **Was diese Einstellung bewirkt:** Ein beschreibender Name für Ihre Erinnerungsregel, nur im Back Office sichtbar. Dies hilft Ihnen, verschiedene Erinnerungsregeln zu identifizieren.
      - **Auswirkung einer Änderung dieser Einstellung:** Ändert die Bezeichnung für diese Regel in Ihrem Admin-Panel. Keine Auswirkungen auf das Front Office.
      - **Empfohlener Wert:** Etwas Klares und Beschreibendes, z. B. „24 Stunden vor Ablauf“, „Eine Woche vor Gutscheinablauf“.
      - **Händlerszenario / Beispiel:** Sie haben mehrere Erinnerungen. Wenn Sie sie „1-Tages-Erinnerung“ und „3-Tages-Erinnerung“ nennen, ist die Verwaltung einfach.
    - **E-Mail-Titel:**
      - **Was diese Einstellung bewirkt:** Dies ist die Betreffzeile der E-Mail, die Ihre Kunden erhalten.
      - **Auswirkung einer Änderung dieser Einstellung:** Ändert direkt die Betreffzeile der Erinnerungs-E-Mails.
      - **Empfohlener Wert:** Etwas Ansprechendes und Klares, z. B. „Ihr [Gutscheincode] läuft bald ab!“, „Verpassen Sie Ihren Rabatt nicht!“.
      - **Händlerszenario / Beispiel:** Sie möchten, dass die E-Mail im Posteingang des Kunden auffällt. Ein Betreff wie „Letzte Chance: Ihr Rabatt läuft bald ab!“ ist effektiver als ein generischer.
    - **E-Mail-Vorlagendatei:**
      - **Was diese Einstellung bewirkt:** Gibt an, welche E-Mail-Vorlagendatei (z. B. `voucher_reminder.html` und `voucher_reminder.txt`) das Modul für diese spezifische Erinnerung verwenden soll. Dies ermöglicht Ihnen, unterschiedliche E-Mail-Designs für unterschiedliche Erinnerungszeitpunkte zu haben.
      - **Auswirkung einer Änderung dieser Einstellung:** Bestimmt den Inhalt und das Layout der gesendeten E-Mail. Wenn Sie eine benutzerdefinierte Vorlage erstellen, würden Sie deren Namen hier auswählen.
      - **Empfohlener Wert:** Verwenden Sie die Standardvorlage, es sei denn, Sie haben spezielle Designanforderungen. Wenn Sie benutzerdefinierte Vorlagen erstellen, stellen Sie sicher, dass sie korrekt im `mails`-Verzeichnis Ihres Themes platziert sind.
      - **Händlerszenario / Beispiel:** Sie möchten eine sanfte Erinnerungs-E-Mail eine Woche im Voraus und eine dringendere „letzte Chance“-E-Mail 24 Stunden im Voraus. Sie würden zwei verschiedene E-Mail-Vorlagen erstellen und sie ihren jeweiligen Erinnerungsregeln zuweisen.
    - **Erinnerung senden:**
      - **Was diese Einstellung bewirkt:** Ein einfacher EIN/AUS-Schalter zum Aktivieren oder Deaktivieren dieser spezifischen Erinnerungsregel.
      - **Auswirkung einer Änderung dieser Einstellung:**
        - *Aktiviert (Ja):* Das Modul sendet E-Mails gemäß dieser Regel.
        - *Deaktiviert (Nein):* Diese Regel wird ignoriert, und es werden keine E-Mails dafür gesendet.
      - **Empfohlener Wert:** „Ja“, sobald Sie die Regel konfiguriert haben und bereit sind, sie zu verwenden.
      - **Händlerszenario / Beispiel:** Sie testen eine neue Erinnerungsregel und möchten sicherstellen, dass sie perfekt ist, bevor Sie sie für alle Kunden aktivieren. Sie würden sie während des Tests deaktiviert lassen.
  - **Speichern-Schaltfläche:** Wendet alle an der Erinnerungsregel vorgenommenen Änderungen an.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie mit der Erstellung von ein oder zwei Erinnerungsregeln (z. B. 72 Stunden und 24 Stunden vor Ablauf).
  2. Verwenden Sie klare Titel und überzeugende E-Mail-Betreffzeilen.
  3. Überwachen Sie den „Verlauf der Gutschein-Erinnerungen“, um zu sehen, ob E-Mails wie erwartet gesendet werden.
  4. Erwägen Sie die Erstellung benutzerdefinierter E-Mail-Vorlagen für verschiedene Erinnerungszeitpunkte, um Ihre Nachricht anzupassen.

#### 2.2.2 Verlauf der Gutschein-Erinnerungen (Back Office > Module > Gutschein-Erinnerung > Verlauf)

Dieser Bildschirm bietet ein Protokoll aller Erinnerungs-E-Mails, die vom Modul erfolgreich gesendet wurden.

- **Bildschirmname & Menüposition:** **Verlauf** (unter **Module > Gutschein-Erinnerung** im Hauptmenü von PrestaShop).
- **Verfügbare Aktionen & Einstellungen:**
  - **Liste der gesendeten Erinnerungen:** Eine Tabelle mit:
    - **ID:** Eindeutiger Bezeichner für den Verlaufseintrag.
    - **Datum der E-Mail-Zustellung:** Wann die E-Mail gesendet wurde.
    - **Erinnerung:** Welche Erinnerungsregel (nach Titel) diese E-Mail ausgelöst hat.
    - **Kunde:** Der Kunde, der die Erinnerung erhalten hat.
    - **Gutschein:** Der spezifische Gutscheincode, an den erinnert wurde.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschütztes Protokoll. Sie können hier keine Änderungen vornehmen, aber es ist von unschätzbarem Wert, um den Betrieb des Moduls zu überprüfen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Verlauf regelmäßig, um sicherzustellen, dass Erinnerungen wie erwartet gesendet werden. Wenn Sie Lücken oder unerwartetes Verhalten bemerken, ist dieses Protokoll Ihr erster Anlaufpunkt zur Fehlerbehebung.

#### 2.2.3 Abmeldungen (Back Office > Module > Gutschein-Erinnerung > Abmeldungen)

Dieser Bildschirm listet Kunden auf, die den Empfang von Gutschein-Erinnerungen abbestellt haben.

- **Bildschirmname & Menüposition:** **Abmeldungen** (unter **Module > Gutschein-Erinnerung** im Hauptmenü von PrestaShop).
- **Verfügbare Aktionen & Einstellungen:**
  - **Liste der abgemeldeten Kunden:** Eine Tabelle mit:
    - **ID:** Eindeutiger Bezeichner für den Abmelde-Eintrag.
    - **E-Mail:** Die E-Mail-Adresse des Kunden, der sich abgemeldet hat.
    - **IP:** Die IP-Adresse, von der die Abmeldung erfolgte.
    - **Abmeldedatum:** Wann sich der Kunde abgemeldet hat.
  - **Neue Abmeldung hinzufügen:** Sie können manuell eine E-Mail-Adresse zur Abmeldeliste hinzufügen.
    - **E-Mail des Kunden:** Geben Sie die E-Mail-Adresse ein, die Sie abmelden möchten.
    - **IP:** (Optional) Die IP-Adresse, die mit der Abmeldung verknüpft ist.
    - **Datum:** (Optional) Das Datum der Abmeldung.
    - **Speichern-Schaltfläche:** Fügt den Kunden zur Abmeldeliste hinzu.
- **Auswirkung von Änderungen:** Hier gelistete Kunden erhalten keine Gutschein-Erinnerungs-E-Mails mehr von Ihrem Shop, auch wenn sie ablaufende Gutscheine haben. Das manuelle Hinzufügen einer E-Mail stellt sicher, dass sie abgemeldet sind.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Während Kunden sich selbst abmelden können, ermöglicht Ihnen dieser Bildschirm, Kunden manuell hinzuzufügen, wenn sie Sie direkt kontaktieren und darum bitten, von Erinnerungslisten entfernt zu werden. Es ist auch ein guter Ort, um Abmeldetrends zu überwachen.

#### 2.2.4 index.php (vreminders/controllers/admin/index.php)

Diese Datei ist typischerweise ein Platzhalter oder eine Weiterleitung innerhalb der PrestaShop-Admin-Struktur und stellt keinen direkten, konfigurierbaren Bildschirm für den Händler dar. Ihr Zweck ist normalerweise, den direkten Zugriff auf das Verzeichnis zu beschränken oder zur Hauptmodulkonfiguration umzuleiten.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Cron-Job-URL | (Generierte URL) | Wesentlich für die Einrichtung der serverseitigen Automatisierung zum Senden von Erinnerungen. |
| **Gutschein-Erinnerungen** | Erinnern (Stunden vor Ablauf) | Variiert (z. B. 24, 72) | Definiert den Zeitpunkt der Erinnerungs-E-Mail relativ zum Gutscheinablauf. |
|  | Titel | Beschreibend (z. B. „1-Tages-Erinnerung“) | Interne Bezeichnung zur Identifizierung von Erinnerungsregeln im Back Office. |
|  | E-Mail-Titel | Ansprechende Betreffzeile | Die Betreffzeile der E-Mail, die Kunden erhalten. |
|  | E-Mail-Vorlagendatei | `voucher_reminder` | Gibt die für diese Erinnerung verwendete E-Mail-Vorlage an. |
|  | Erinnerung senden | Ja | Aktiviert oder deaktiviert eine spezifische Erinnerungsregel. |
| **Verlauf der Gutschein-Erinnerungen** | (Alle Felder) | N/A (Schreibgeschützt) | Protokoll aller gesendeten Erinnerungs-E-Mails zur Überprüfung und Fehlerbehebung. |
| **Abmeldungen** | E-Mail des Kunden | N/A | Manuelles Hinzufügen von Kunden-E-Mails, um den Empfang von Erinnerungen zu verhindern. |
|  | IP | N/A | (Optional) IP-Adresse, die mit der Abmeldung verknüpft ist. |
|  | Datum | N/A | (Optional) Datum der Abmeldung. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F: Meine Erinnerungen werden nicht gesendet. Was sollte ich zuerst überprüfen?**
A: Der häufigste Grund ist ein falsch eingerichteter Cron-Job.

1. Gehen Sie zu **Module > Gutschein-Erinnerung > Konfigurieren**.
2. Kopieren Sie die „Cron-Job-URL“ genau.
3. Melden Sie sich in Ihrem Hosting-Kontrollpanel (cPanel, Plesk usw.) an und navigieren Sie zum Abschnitt „Cron-Jobs“.
4. Erstellen Sie einen neuen Cron-Job, der diese URL alle 5-15 Minuten aufruft. Der Befehl sieht normalerweise so aus: `wget -q -O /dev/null "IHRE_CRON_JOB_URL_HIER"` oder `curl -s "IHRE_CRON_JOB_URL_HIER" > /dev/null`.
5. Stellen Sie außerdem sicher, dass die einzelnen Erinnerungsregeln aktiviert sind („Erinnerung senden“ ist auf „Ja“ gesetzt) unter **Module > Gutschein-Erinnerung > Gutschein-Erinnerungen**.

**F: Kunden beschweren sich, dass sie keine Erinnerungen erhalten, aber der Verlauf zeigt, dass sie gesendet wurden.**
A: Dies deutet in der Regel auf Probleme bei der E-Mail-Zustellung hin.

1. **Spam-Ordner überprüfen:** Raten Sie Kunden, ihre Spam- oder Junk-Ordner zu überprüfen.
2. **E-Mail-Server-Konfiguration:** Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres PrestaShop-Shops (unter **Erweiterte Einstellungen > E-Mail**) korrekt konfiguriert sind und Ihr Server nicht auf einer Blacklist steht. Die Verwendung eines SMTP-Servers (wie SendGrid, Mailgun usw.) ist oft zuverlässiger als die PHP-Funktion `mail()`.
3. **Probleme mit E-Mail-Vorlagen:** Stellen Sie sicher, dass Ihre E-Mail-Vorlagen gültiges HTML/Text sind und keine fehlerhaften Links oder Bilder enthalten, die Spamfilter auslösen könnten.

**F: Kann ich die E-Mail-Vorlagen anpassen?**
A: Ja!

1. Das Modul verwendet Standard-PrestaShop-E-Mail-Vorlagen. Sie finden die Standardvorlagendateien in `modules/vreminders/mails/en/` (oder Ihrem Sprachordner).
2. **Best Practice:** Kopieren Sie diese Dateien in das `mails/en/`-Verzeichnis Ihres aktiven Themes (z. B. `themes/ihrtheme/mails/en/`). Auf diese Weise werden Ihre Anpassungen bei Modul-Updates nicht überschrieben.
3. Bearbeiten Sie die `.html`- und `.txt`-Dateien, um sie an Ihr Branding und Ihre Botschaft anzupassen. Sie können Smarty-Variablen verwenden, die in PrestaShop-E-Mail-Vorlagen verfügbar sind.
4. Wenn Sie völlig neue Vorlagendateien erstellen (z. B. `meine_benutzerdefinierte_erinnerung.html`), müssen Sie `meine_benutzerdefinierte_erinnerung` in der Einstellung „E-Mail-Vorlagendatei“ für Ihre Erinnerungsregel auswählen.

**F: Wie teste ich die Erinnerungen, ohne sie an echte Kunden zu senden?**
A:

1. Erstellen Sie ein Testkundenkonto in Ihrem Shop.
2. Erstellen Sie manuell einen Gutscheincode für diesen Testkunden mit einem Ablaufdatum, das einige Stunden oder Tage in der Zukunft liegt.
3. Richten Sie eine Erinnerungsregel mit einer kurzen „Erinnern (Stunden vor Ablauf)“ (z. B. 1 Stunde) ein.
4. Anstatt auf den Cron-Job zu warten, können Sie die Cron-URL manuell in Ihrem Browser aufrufen (obwohl dies für die Produktion nicht empfohlen wird).
5. Überprüfen Sie den „Verlauf der Gutschein-Erinnerungen“ und den E-Mail-Posteingang des Testkunden.
6. Wenn Sie zufrieden sind, löschen Sie den Testgutschein und die Erinnerungsregel und richten Sie Ihre Produktionsregeln ein.

**F: Was passiert, wenn ein Kunde seinen Gutschein nach dem Senden einer Erinnerung, aber vor Ablauf verwendet?**
A: Das Modul ist so konzipiert, dass es nur Erinnerungen für *ungenutzte* Gutscheine sendet. Wenn ein Kunde seinen Gutschein verwendet, wird er nicht mehr als „aktiv“ und „ungenutzt“ betrachtet, sodass keine weiteren Erinnerungen für diesen spezifischen Gutschein gesendet werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Gutschein-Erinnerung“ folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Seine Kernfunktionalität dreht sich um einen Cron-Job, der regelmäßig nach ablaufenden Gutscheinen sucht und E-Mails basierend auf konfigurierten Regeln versendet. Es verwendet PrestaShops `ObjectModel` zur Verwaltung seiner benutzerdefinierten Entitäten (Erinnerungen, Verlauf, Abmeldungen) und Standard-E-Mail-Mechanismen für die Kommunikation. Die Hauptlogik des Moduls befindet sich in `cronjob.php` (das als Hauptmodulklasse fungiert) und dedizierten Admin-Controllern für CRUD-Operationen auf seinen benutzerdefinierten Daten.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/CronJob.php`
    - **Klassenname & Elternklasse**: `VremindersCronJobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist der Einstiegspunkt für den Cron-Job des Moduls. Wenn die Cron-URL (generiert in der Modulkonfiguration) aufgerufen wird, wird dieser Controller ausgeführt. Er enthält die Logik zum Abrufen ablaufender Gutscheine, zum Überprüfen anhand konfigurierter Erinnerungsregeln und zum Versenden von E-Mails. Er rendert typischerweise keine visuelle Ausgabe, sondern führt Hintergrundverarbeitung durch.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: Keine Klasse, typischerweise eine leere Datei oder ein einfaches `die('No direct script access allowed')`, um direkte Verzeichnisauflistung oder Zugriff zu verhindern.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminVoucherReminders.php`
    - **Tab-Name und verwaltete Entität**: Verwaltet die Liste und Formulare der „Gutschein-Erinnerungen“ im Back Office. Es behandelt CRUD-Operationen für die Entität `VoucherReminder` (die der Tabelle `ps_vr` zugeordnet ist).
  - `controllers/admin/AdminVoucherRemindersHistory.php`
    - **Tab-Name und verwaltete Entität**: Verwaltet die Liste „Verlauf der Gutschein-Erinnerungen“ im Back Office. Es zeigt ein schreibgeschütztes Protokoll gesendeter Erinnerungen an, das der Entität `VoucherReminderHistory` (die der Tabelle `ps_vr_history` zugeordnet ist) zugeordnet ist.
  - `controllers/admin/AdminVRemindersUnsub.php`
    - **Tab-Name und verwaltete Entität**: Verwaltet die Liste und Formulare der „Abmeldungen“ im Back Office. Es behandelt CRUD-Operationen für die Entität `VoucherReminderUnsub` (die der Tabelle `ps_vr_vunsub` zugeordnet ist).
  - `controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Keine Klasse, typischerweise eine leere Datei oder ein einfaches `die('No direct script access allowed')`, um direkte Verzeichnisauflistung oder Zugriff zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist kein explizites `classes/`-Verzeichnis aus. Dies impliziert, dass die Kern-`ObjectModel`-Klassen wahrscheinlich direkt in der Hauptmoduldatei (`cronjob.php`) oder in den jeweiligen Admin-Controller-Dateien definiert sind. Basierend auf der typischen PrestaShop-Modulstruktur und den identifizierten Entitäten werden die folgenden `ObjectModel`-Klassen erwartet, die wahrscheinlich in `cronjob.php` oder `AdminVoucherReminders.php`, `AdminVoucherRemindersHistory.php`, `AdminVRemindersUnsub.php` definiert sind:

- **`VoucherReminder` (oder ähnlich)**

  - **Datenbanktabelle**: `ps_vr` (oder `_vreminders_vr`)
  - **Erweitert `ObjectModel`**: Ja.
  - **`$definition`-Felder**: Erwartete Felder sind `id_vr`, `remind_hours`, `title`, `email_title`, `email_template`, `active`.
  - **Wichtige öffentliche Methoden**: Methoden zum Hinzufügen, Aktualisieren, Löschen von Erinnerungsregeln und potenziell Methoden zum Abrufen aktiver Regeln.
- **`VoucherReminderHistory` (oder ähnlich)**

  - **Datenbanktabelle**: `ps_vr_history` (oder `_vreminders_vr_history`)
  - **Erweitert `ObjectModel`**: Ja.
  - **`$definition`-Felder**: Erwartete Felder sind `id_vr_history`, `id_vr`, `id_customer`, `id_cart_rule`, `date_add`.
  - **Wichtige öffentliche Methoden**: Methoden zum Protokollieren gesendeter Erinnerungen.
- **`VoucherReminderUnsub` (oder ähnlich)**

  - **Datenbanktabelle**: `ps_vr_vunsub` (oder `_vreminders_vr_vunsub`)
  - **Erweitert `ObjectModel`**: Ja.
  - **`$definition`-Felder**: Erwartete Felder sind `id_vunsub`, `email`, `ip`, `date_add`.
  - **Wichtige öffentliche Methoden**: Methoden zur Verwaltung von Abmeldungen, einschließlich des Hinzufügens und Überprüfens von abgemeldeten E-Mails.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine JavaScript-Dateien aus. Dies deutet darauf hin, dass das Modul vollständig auf die Kern-JavaScript-Funktionalitäten von PrestaShop für seine Back-Office-Formulare und -Listen angewiesen ist oder dass jegliches minimale JS direkt in den Vorlagen enthalten ist.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine CSS-Dateien aus. Dies deutet darauf hin, dass das Modul vollständig auf das Kern-Back-Office-CSS von PrestaShop für seine Admin-Oberflächen angewiesen ist und jegliches Front-Office-Styling (für E-Mails) innerhalb der E-Mail-Vorlagen selbst gehandhabt wird.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Admin-Vorlagen (`views/templates/admin/`)**:

  - `vreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    - **Zweck**: Diese Vorlage wird wahrscheinlich von `AdminVoucherRemindersController` verwendet, um das Hinzufügen/Bearbeiten-Formular für einzelne Gutschein-Erinnerungsregeln zu rendern. Sie würde die Eingabefelder für „Erinnern (Stunden vor Ablauf)“, „Titel“, „E-Mail-Titel“, „E-Mail-Vorlagendatei“ und „Erinnerung senden“ enthalten.
- **Hook-Vorlagen (`views/templates/hook/`)**:

  - `vreminders/views/templates/hook/form.tpl`
    - **Zweck**: Diese Vorlage könnte eine generische Formularvorlage oder eine spezifische für einen Hook sein, der ein Formular anzeigt. Angesichts der Art des Moduls ist es weniger wahrscheinlich, dass es sich um ein sichtbares Front-Office-Formular handelt, sondern eher um eine interne Komponente oder einen Legacy-Hook. Ohne weiteren Kontext ist seine genaue Front-Office-Platzierung unklar, aber es könnte für ein Abmeldeformular oder Ähnliches sein.
  - `vreminders/views/templates/hook/header.tpl`
    - **Zweck**: Diese Vorlage wird im Hook `displayHeader` gerendert. Sie wird typischerweise verwendet, um CSS- oder JavaScript-Dateien, Meta-Tags oder andere Elemente einzuschließen, die im `<head>`-Abschnitt des HTML-Dokuments geladen werden müssen. Für dieses Modul könnte es verwendet werden, um notwendiges JS für den Cron-Job einzuschließen oder spezifische Meta-Tags einzurichten, obwohl das Dossier keine JS/CSS-Dateien angibt. Es könnte auch ein Platzhalter sein.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_vr` (oder `_vreminders_vr`): Speichert die Konfiguration für jede Gutschein-Erinnerungsregel.
    - `id_vr` (PK, INT)
    - `remind_hours` (INT)
    - `title` (VARCHAR)
    - `email_title` (VARCHAR)
    - `email_template` (VARCHAR)
    - `active` (TINYINT)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_vr_history` (oder `_vreminders_vr_history`): Protokolliert jede gesendete Erinnerungs-E-Mail.
    - `id_vr_history` (PK, INT)
    - `id_vr` (FK zu `ps_vr.id_vr`, INT)
    - `id_customer` (FK zu `ps_customer.id_customer`, INT)
    - `id_cart_rule` (FK zu `ps_cart_rule.id_cart_rule`, INT)
    - `date_add` (DATETIME)
  - `ps_vr_vunsub` (oder `_vreminders_vr_vunsub`): Speichert E-Mail-Adressen von Kunden, die sich von Erinnerungen abgemeldet haben.
    - `id_vunsub` (PK, INT)
    - `email` (VARCHAR)
    - `ip` (VARCHAR)
    - `date_add` (DATETIME)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Zum Einschließen notwendiger Assets (JS/CSS) oder Meta-Tags für das Modul. |
| `actionModuleInstall` | Während der Modulinstallation. | Zum Erstellen von Datenbanktabellen und der Standardkonfiguration. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Entfernen von Datenbanktabellen und der Konfiguration. |
| `displayAdminProductsExtra` (oder ähnlich) | Potenziell auf Produktseiten im BO. | Wenn das Modul produktspezifische Erinnerungseinstellungen hätte, aber nicht im Dossier angegeben. |
| `displayBackOfficeHeader` | Im `<head>`-Abschnitt jeder Back-Office-Seite. | Zum Einschließen von admin-spezifischem JS/CSS oder Kontext für die Modulkonfiguration. |
| `moduleRoutes` | Während der URL-Rewriting-Initialisierung. | Zum Definieren benutzerdefinierter freundlicher URLs für Front-Controller (z. B. Cron-Job-URL, Abmelde-URL). |

Die Kernlogik des Moduls zum Senden von Erinnerungen wird durch den Front-Controller `CronJob.php` ausgelöst, der über einen serverseitigen Cron-Job aufgerufen wird, nicht direkt durch einen PrestaShop-Hook.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung für Ihr Modul „Gutschein-Erinnerung“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, umfassenden Support zu bieten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.
