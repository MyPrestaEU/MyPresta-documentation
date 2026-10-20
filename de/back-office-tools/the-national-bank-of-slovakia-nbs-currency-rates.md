---
title: "Die Nationalbank der Slowakei (NBS) – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Die Nationalbank der Slowakei (NBS) – Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Die Nationalbank der Slowakei (NBS) – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul The National Bank of Slovakia (NBS) - currency rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/the-national-bank-of-slovakia-nbs-currency-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/the-national-bank-of-slovakia-nbs-currency-rates/)
>
> ---


# Die Nationalbank der Slowakei (NBS) – Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen, um auf dessen Einstellungen zuzugreifen.

#### **1. Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist ein Standard-PrestaShop-Schalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul beginnt, Wechselkurse gemäß Ihren Einstellungen abzurufen und zu aktualisieren.
  - *Wenn deaktiviert:* Das Modul stoppt alle Operationen, und Ihre Wechselkurse werden nicht mehr automatisch durch NBS-Daten aktualisiert.
- **Empfohlener Wert:** **JA** (um die Funktionalität des Moduls zu aktivieren).
- **Händlerszenario / Beispiel:** Wenn Sie die automatischen Updates vorübergehend stoppen möchten (z. B. während der Wartung oder wenn Sie auf manuelle Kursverwaltung umstellen), können Sie es deaktivieren. Andernfalls lassen Sie es für kontinuierliche Updates aktiviert.

#### **2. CRON-URL für automatische Updates**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie als „Cron-Job“ auf Ihrem Webhosting-Server einrichten müssen. Ein Cron-Job ist eine geplante Aufgabe, die Ihrem Server anweist, diese URL in regelmäßigen Abständen aufzurufen, wodurch das Modul ausgelöst wird, die neuesten NBS-Wechselkurse automatisch abzurufen und zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn korrekt als Cron-Job eingerichtet:* Ihre Wechselkurse werden automatisch ohne manuelles Eingreifen aktualisiert.
  - *Wenn nicht als Cron-Job eingerichtet:* Das Modul aktualisiert die Kurse nicht automatisch. Sie müssten diese URL manuell in Ihrem Browser aufrufen, um ein Update auszulösen (was den Zweck der Automatisierung zunichtemacht).
- **Empfohlener Wert:** Dies ist eine generierte URL. Sie sollten **diese URL kopieren** und in den Cron-Job-Scheduler Ihres Hosting-Kontrollpanels einfügen.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse jeden Tag um 3 Uhr morgens aktualisiert werden. Sie würden diese URL kopieren, zu Ihrem Hosting-Panel (z. B. cPanel, Plesk, oder fragen Sie Ihren Host um Hilfe) gehen und einen Cron-Job erstellen, der diese URL täglich um 3 Uhr morgens ausführt.

#### **3. Prozentualen Aufschlag zu Wechselkursen hinzufügen**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, einen Prozentwert zusätzlich zu den von der NBS abgerufenen offiziellen Wechselkursen hinzuzufügen. Dieser Aufschlag wird auf alle vom Modul aktualisierten Währungen angewendet.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf 0 gesetzt (oder leer gelassen):* Ihre Wechselkurse entsprechen genau den von der NBS bereitgestellten.
  - *Wenn auf einen positiven Wert gesetzt (z. B. 2):* Das Modul erhöht den NBS-Wechselkurs um diesen Prozentsatz (z. B. wenn der Kurs 1 EUR = 1,10 USD beträgt, wird er mit einem 2%igen Aufschlag zu 1 EUR = 1,122 USD). Dies macht Ihre Produkte effektiv etwas teurer, wenn sie in der Nicht-Basiswährung bezahlt werden.
- **Empfohlener Wert:** **0** (wenn Sie exakte NBS-Kurse wünschen) oder ein kleiner positiver Prozentsatz (z. B. **1-3%**), um Transaktionsgebühren oder Marktvolatilität abzudecken.
- **Händlerszenario / Beispiel:** Sie möchten potenzielle Bankgebühren bei der Umrechnung von Zahlungen berücksichtigen oder einfach einen kleinen Puffer bei Ihren internationalen Verkäufen haben. Wenn Sie dies auf „2“ setzen, wird ein 2%iger Aufschlag auf alle aktualisierten Wechselkurse angewendet.

#### **4. Nur ausgewählte Währungen aktualisieren**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, spezifische Währungen in Ihrem PrestaShop-Store auszuwählen, die vom NBS-Modul aktualisiert werden sollen. Wenn Sie viele Währungen haben, aber nur wenige von der NBS verwaltet werden sollen, ist dies nützlich.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn nicht aktiviert:* Das Modul versucht, alle aktiven Währungen in Ihrem PrestaShop-Store zu aktualisieren, für die ein entsprechender Kurs von der NBS verfügbar ist.
  - *Wenn aktiviert und spezifische Währungen ausgewählt sind:* Nur die ausgewählten Währungen erhalten ihre Wechselkurse vom Modul aktualisiert. Andere Währungen behalten ihre bestehenden Kurse (manuell oder von anderen Quellen).
- **Empfohlener Wert:** **Aktivieren Sie dieses Kontrollkästchen** und wählen Sie nur die Währungen aus, die Sie aktiv mit NBS-Daten verwalten. Dies verhindert unbeabsichtigte Änderungen an anderen Währungen.
- **Händlerszenario / Beispiel:** Ihre Basiswährung ist EUR, und Sie verkaufen auch in USD und CZK. Sie möchten, dass die NBS die USD- und CZK-Kurse aktualisiert, aber Sie verwalten die GBP-Kurse manuell. Sie würden dieses Kontrollkästchen aktivieren und nur USD und CZK aus der Liste auswählen.

#### **5. Liste der zu aktualisierenden Währungen**

- **Was diese Einstellung bewirkt:** Dies ist eine Mehrfachauswahlliste, die nur angezeigt wird, wenn „Nur ausgewählte Währungen aktualisieren“ aktiviert ist. Sie zeigt alle aktiven Währungen in Ihrem PrestaShop-Store an und ermöglicht es Ihnen, auszuwählen, welche das Modul aktualisieren soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auswählen von Währungen:* Diese Währungen erhalten ihre Wechselkurse automatisch vom NBS-Modul aktualisiert.
  - *Abwählen von Währungen:* Diese Währungen werden vom NBS-Modul ignoriert und ihre Kurse werden nicht geändert.
- **Empfohlener Wert:** Wählen Sie alle Währungen aus, für die Sie NBS-Kurse verwenden möchten.
- **Händlerszenario / Beispiel:** Gemäß dem vorherigen Beispiel würden Sie in dieser Liste auf „USD“ und „CZK“ klicken, um sicherzustellen, dass nur diese aktualisiert werden.

#### **6. Speichern-Button**

- **Was diese Einstellung bewirkt:** Übernimmt alle Änderungen, die Sie auf der Konfigurationsseite vorgenommen haben.
- **Auswirkung der Änderung dieser Einstellung:** Ihre Moduleinstellungen werden gespeichert und treten sofort in Kraft (für zukünftige Cron-Job-Läufe oder manuelle Updates).
- **Empfohlener Wert:** Klicken Sie immer auf **„Speichern“**, nachdem Sie Änderungen vorgenommen haben.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | JA | Aktiviert/deaktiviert die Modulfunktionalität. |
| Modulkonfiguration | CRON-URL für automatische Updates | Generierte URL | Kopieren und als Cron-Job für automatisierte Kursaktualisierungen einrichten. |
| Modulkonfiguration | Prozentualen Aufschlag zu Wechselkursen hinzufügen | 0 (oder 1-3%) | Fügt einen prozentualen Puffer zu NBS-Kursen für die Preisstrategie hinzu. |
| Modulkonfiguration | Nur ausgewählte Währungen aktualisieren | Aktivieren & auswählen | Beschränkt NBS-Updates auf spezifisch ausgewählte Währungen. |
| Modulkonfiguration | Liste der zu aktualisierenden Währungen | Gewünschte auswählen | Wählen Sie aus, welche aktiven Währungen NBS-Kursaktualisierungen erhalten. |
| Modulkonfiguration | Speichern-Button | Nach Änderungen klicken | Speichert alle Modulkonfigurationseinstellungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht automatisch aktualisiert. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** aktiviert ist.
2. **Cron-Job überprüfen:** Das häufigste Problem ist ein falsch eingerichteter Cron-Job.
   - Gehen Sie zurück zur Modulkonfigurationsseite und kopieren Sie die „CRON-URL“ erneut.
   - Melden Sie sich in Ihrem Hosting-Kontrollpanel (cPanel, Plesk usw.) an und navigieren Sie zum Abschnitt „Cron-Jobs“ oder „Geplante Aufgaben“.
   - Überprüfen Sie sorgfältig, ob die URL genau der vom Modul bereitgestellten entspricht und ob der Zeitplan (z. B. täglich, stündlich) korrekt ist.
   - Stellen Sie sicher, dass der Befehl `wget` oder `curl` verwendet, um die URL auszuführen (z. B. `wget -O /dev/null "IHRE_CRON_URL_HIER"`).
   - Wenn Sie unsicher sind, wenden Sie sich mit der CRON-URL an den Support Ihres Hosting-Anbieters und bitten Sie ihn, diese für Sie einzurichten.
3. **Serverprotokolle überprüfen:** Ihr Hosting-Anbieter hat möglicherweise Protokolle für die Ausführung von Cron-Jobs, die auf einen Fehler hinweisen können.

**F2: Das Modul ist aktiviert, aber einige Währungen werden nicht aktualisiert.**
A:

1. **„Nur ausgewählte Währungen aktualisieren“ überprüfen:** Gehen Sie zur Modulkonfiguration. Wenn „Nur ausgewählte Währungen aktualisieren“ aktiviert ist, stellen Sie sicher, dass die spezifischen Währungen, die Sie aktualisieren möchten, in der „Liste der zu aktualisierenden Währungen“ ausgewählt sind.
2. **Verfügbarkeit von NBS-Daten:** Die Nationalbank der Slowakei stellt möglicherweise nicht für alle Währungen Kurse bereit. Das Modul kann nur Währungen aktualisieren, für die die NBS Daten veröffentlicht. Überprüfen Sie die offizielle NBS-Website auf verfügbare Währungspaare.
3. **PrestaShop-Währungsstatus:** Stellen Sie sicher, dass die betreffenden Währungen in Ihrem PrestaShop-Store aktiv sind (**International > Währungen**). Inaktive Währungen können nicht aktualisiert werden.

**F3: Wie oft sollte ich den Cron-Job ausführen?**
A: Für die meisten Stores reicht es aus, den Cron-Job einmal täglich auszuführen, um die Kurse aktuell zu halten. Wenn Ihr Geschäft aufgrund von hohen internationalen Transaktionsvolumen oder volatilen Märkten extrem Echtzeit-Kurse erfordert, könnten Sie ihn häufiger ausführen lassen (z. B. alle 6 oder 12 Stunden), aber täglich ist im Allgemeinen ausreichend.

**F4: Ich habe einen Aufschlag hinzugefügt, aber die Preise scheinen ihn nicht widerzuspiegeln.**
A:

1. **Einstellungen speichern:** Stellen Sie sicher, dass Sie nach dem Festlegen des Aufschlags auf die Schaltfläche „Speichern“ geklickt haben.
2. **Update auslösen:** Der Aufschlag wird erst angewendet, wenn die Wechselkurse das nächste Mal aktualisiert werden. Dies geschieht beim nächsten Cron-Job-Lauf, oder Sie können ein Update manuell auslösen, indem Sie die CRON-URL in Ihrem Browser aufrufen.
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache alte Werte enthalten. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).

**F5: Wirkt sich dieses Modul auf meine Basiswährung aus?**
A: Nein, das Modul aktualisiert Wechselkurse *relativ* zu Ihrer Basiswährung. Der Wert Ihrer Basiswährung selbst bleibt konstant. Wenn Ihre Basiswährung beispielsweise EUR ist, aktualisiert das Modul, wie viele USD oder CZK 1 EUR entsprechen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Die Nationalbank der Slowakei (NBS) – Wechselkurse“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich eine Hauptmodulklasse (`cronjob.php`) für Konfiguration und Hook-Verwaltung sowie einen Front-Controller (`cronjob.php`) zur Handhabung der Cron-Job-Ausführung nutzt. Es interagiert mit der PrestaShop-Kernwährungsverwaltung, um Kurse zu aktualisieren. Die Hauptfunktion des Moduls besteht darin, externe Daten (NBS-Kurse) abzurufen und in das `Currency`-Objektmodell von PrestaShop zu integrieren.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse:** `NbsratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dieser Controller ist speziell dafür konzipiert, von einem Cron-Job aufgerufen zu werden. Beim Zugriff initiiert er den Prozess des Abrufens der neuesten Wechselkurse von der Nationalbank der Slowakei und deren Aktualisierung in der PrestaShop-Datenbank. Er rendert keine visuelle Ausgabe an den Browser, sondern führt Hintergrundverarbeitung durch. Er behandelt die Logik für die Anwendung des konfigurierten prozentualen Aufschlags und die Aktualisierung nur ausgewählter Währungen.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse:** Dies ist typischerweise eine leere Datei oder ein Platzhalter, der oft verwendet wird, um die Verzeichnisauflistung zu verhindern oder einen gültigen Einstiegspunkt für ältere PrestaShop-Versionen sicherzustellen. Er enthält keine spezifische Modullogik für NBS-Kurse.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Administration wird über die `getContent()`-Methode des Hauptmoduls abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen. Es interagiert direkt mit der PrestaShop-Kernklasse `Currency`, um Wechselkurse zu aktualisieren.

### 4.4 JavaScript-Assets (`views/js/`)

Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Zweck:** Dieses Template wird gerendert, wenn die Konfigurationsseite des Moduls im PrestaShop Back Office aufgerufen wird. Es zeigt die Eingabefelder zum Aktivieren/Deaktivieren des Moduls, die CRON-URL, den prozentualen Aufschlag und die Währungsauswahloptionen an. Es verwendet Standard-PrestaShop-Formularhelfer und -Elemente.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`.

  - `PS_NBS_RATES_ENABLED`: Speichert den Aktivierungs-/Deaktivierungsstatus des Moduls.
  - `PS_NBS_RATES_MARGIN`: Speichert den anzuwendenden prozentualen Aufschlag.
  - `PS_NBS_RATES_SELECTED_CURRENCIES`: Speichert ein serialisiertes Array von Währungs-IDs, wenn „Nur ausgewählte Währungen aktualisieren“ aktiv ist.
  - `PS_NBS_RATES_CRON_TOKEN`: Speichert ein eindeutiges Token für die Cron-URL zur Sicherheit.
- **Registrierte Hooks-Tabelle**:
  Das Modul verwendet hauptsächlich den Hook `actionFrontControllerSetMedia` (implizit, wenn es Assets laden würde, obwohl es dies nicht tut) und verlässt sich auf seine `install()`- und `uninstall()`-Methoden für Einrichtung und Bereinigung. Seine Kernfunktionalität wird durch den Front-Controller `cronjob.php` ausgelöst und nicht durch einen traditionellen PrestaShop-Hook.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `install()` | Während der Modulinstallation | Richtet Standardkonfigurationswerte in `ps_configuration` ein und registriert das Modul. |
| `uninstall()` | Während der Moduldeinstallation | Bereinigt Konfigurationswerte aus `ps_configuration`. |
| (Cron-Job) | Externe HTTP-Anfrage an `controllers/front/cronjob.php` | Ruft NBS-Kurse ab, wendet den Aufschlag an und aktualisiert die Tabelle `ps_currency`. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Die Nationalbank der Slowakei (NBS) – Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
