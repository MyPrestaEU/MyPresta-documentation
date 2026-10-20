---
title: "EZB-Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „European Central Bank currency rates“ von MyPresta.eu."
sidebar:
  label: "EZB-Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul European Central Bank currency rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/european-central-bank-currency-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/european-central-bank-currency-rates/)
>
> ---


# EZB-Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Haupteinstellungen des Moduls zuzugreifen. Hier steuern Sie, wie und wann Ihre Wechselkurse aktualisiert werden.

Der Konfigurationsbildschirm zeigt typischerweise ein Formular mit Optionen zum Aktivieren/Deaktivieren der Modulfunktionalität und möglicherweise eine Möglichkeit, eine Aktualisierung manuell auszulösen oder einen Cron-Job einzurichten.

**Cronjob-URL:**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die, wenn sie aufgerufen wird, das Modul dazu veranlasst, die neuesten Wechselkurse von der Europäischen Zentralbank abzurufen und diese in Ihrem PrestaShop-Store zu aktualisieren. Dies ist der Kernmechanismus für automatisierte Aktualisierungen.
- **Auswirkung der Änderung dieser Einstellung:** Dies ist eine schreibgeschützte URL, die vom Modul generiert wird. Sie ändern sie nicht direkt.
  - *Bei Verwendung in einem Cron-Job:* Ihre Wechselkurse werden automatisch in regelmäßigen Abständen ohne manuelles Eingreifen aktualisiert.
  - *Bei Nichtverwendung:* Die Kurse werden nur aktualisiert, wenn Sie manuell auf die Schaltfläche „Jetzt aktualisieren“ klicken (falls verfügbar) oder wenn der standardmäßige, weniger zuverlässige Währungsaktualisierungsmechanismus von PrestaShop verwendet wird.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als Cron-Job auf Ihrem Hosting-Server ein. Dies ist der effizienteste und zuverlässigste Weg, Ihre Kurse aktuell zu halten.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse jeden Tag um 3 Uhr morgens aktualisiert werden. Sie kopieren diese URL und fügen sie dem Cron-Job-Scheduler Ihres Hosting-Kontrollpanels hinzu, der so eingestellt ist, dass er täglich um 3 Uhr morgens ausgeführt wird.

**Schaltfläche „Jetzt aktualisieren“ (falls vorhanden):**

- **Was diese Einstellung bewirkt:** Dies ist ein manueller Auslöser, um sofort alle Wechselkurse von der EZB abzurufen und zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beim Klicken:* Das Modul verbindet sich sofort mit der EZB, ruft die neuesten Wechselkurse ab und wendet sie auf die Währungen Ihres Shops an. Dies ist nützlich für sofortige Aktualisierungen oder Tests.
- **Empfohlener Wert:** Verwenden Sie dies für erste Einrichtungstests oder wenn Sie eine sofortige Aktualisierung außerhalb Ihrer geplanten Cron-Jobs benötigen. Für regelmäßige Aktualisierungen verlassen Sie sich auf den Cron-Job.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten sicherstellen, dass es korrekt funktioniert. Sie klicken auf „Jetzt aktualisieren“ und überprüfen dann Ihre Wechselkurse in PrestaShop, um zu bestätigen, dass sie sich geändert haben.

**Allgemeine Modulkonfiguration (falls vorhanden, z. B. Aktivieren/Deaktivieren):**

- **Was diese Einstellung bewirkt:** Dies ist ein Standard-PrestaShop-Modulschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Bei Aktivierung:* Das Modul ist aktiv, und seine Cron-Job-URL funktioniert, was automatische Währungsaktualisierungen ermöglicht.
  - *Bei Deaktivierung:* Das Modul führt keine Aktualisierungen durch, und die Cron-Job-URL funktioniert nicht. Ihre Wechselkurse werden von diesem Modul nicht aktualisiert.
- **Empfohlener Wert:** **JA** (Aktiviert), um sicherzustellen, dass Ihre Wechselkurse automatisch aktualisiert werden.
- **Händlerszenario / Beispiel:** Sie möchten, dass das Modul Ihre Wechselkurse verwaltet, daher stellen Sie sicher, dass es aktiviert ist. Wenn Sie aus irgendeinem Grund die automatischen Aktualisierungen vorübergehend stoppen möchten, würden Sie es deaktivieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul führt keine dedizierten neuen Admin-Bildschirme oder benutzerdefinierten Controller über seine Hauptkonfigurationsseite hinaus ein. Alle Interaktionen erfolgen direkt über das Konfigurationsformular des Moduls.

### 2.3 Konfigurations-Kurzreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Cronjob-URL | Kopieren & auf Hosting einrichten | Löst automatisierte Wechselkursaktualisierungen von der EZB aus. Wesentlich für den automatischen Betrieb. |
| Modulkonfigurationsseite | Schaltfläche „Jetzt aktualisieren“ | Für Tests/manuelle Aktualisierung verwenden | Ruft sofort die neuesten EZB-Kurse ab und wendet sie an. |
| Modulkonfigurationsseite | Modul aktiviert/deaktiviert | Aktiviert (JA) | Aktiviert oder deaktiviert die Währungsaktualisierungsfunktion des Moduls. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht automatisch aktualisiert. Was sollte ich überprüfen?**
A:

1. **Cron-Job-Einrichtung:** Das häufigste Problem ist ein falsch konfigurierter Cron-Job. Überprüfen Sie die URL, die Sie in Ihrem Hosting-Panel verwendet haben, und stellen Sie sicher, dass der Zeitplan aktiv und korrekt ist.
2. **Modul aktiviert:** Stellen Sie sicher, dass das Modul „European Central Bank currency rates“ in Ihrem PrestaShop Back Office (**Module > Modul-Manager**) aktiviert ist.
3. **PHP-Version:** Stellen Sie sicher, dass Ihre PHP-Version innerhalb des Kompatibilitätsbereichs des Moduls liegt (PHP 5.6 - 8.5).
4. **Server-Logs:** Überprüfen Sie die Cron-Job-Logs Ihres Servers (sofern Ihr Host diese bereitstellt) auf Fehler, wenn der Cron-Job versucht, ausgeführt zu werden.
5. **Manuelle Aktualisierung:** Versuchen Sie, auf die Schaltfläche „Jetzt aktualisieren“ auf der Konfigurationsseite des Moduls zu klicken. Wenn dies funktioniert, liegt das Problem definitiv bei Ihrer Cron-Job-Einrichtung.

**F: Die Kurse wurden aktualisiert, aber sie scheinen falsch oder anders zu sein, als ich erwartet hatte.**
A:

1. **EZB-Quelle:** Dieses Modul ruft die Kurse direkt von der Europäischen Zentralbank ab. Dies sind offizielle Interbankenkurse, die aufgrund von Bankgebühren, Spreads oder unterschiedlichen Aktualisierungszeiten geringfügig von den Verbraucherkursen abweichen können, die Sie bei Google oder anderen Finanzseiten sehen.
2. **Basiswährung:** Stellen Sie sicher, dass die Standardwährung Ihres PrestaShops korrekt konfiguriert ist. Das Modul aktualisiert die Kurse relativ zur Basiswährung.
3. **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) nach einer Aktualisierung, um sicherzustellen, dass Sie die aktuellsten Daten sehen.

**F: Funktioniert dieses Modul mit benutzerdefinierten Themes?**
A: Ja, absolut. Dieses Modul arbeitet im Hintergrund, um Daten (Wechselkurse) in Ihrer Datenbank zu aktualisieren. Es gibt keine visuellen Elemente aus und ändert das Design Ihres Themes nicht, daher ist es vollständig mit jedem PrestaShop-Theme kompatibel.

**F: Wie oft sollte ich die Wechselkurse aktualisieren?**
A: Für die meisten E-Commerce-Shops ist eine tägliche Aktualisierung ausreichend. Wenn Sie mit hochwertigen Artikeln handeln oder in sehr volatilen Märkten tätig sind, könnten Sie eine zweimal tägliche Aktualisierung in Betracht ziehen. Die EZB veröffentlicht ihre Referenzkurse typischerweise einmal täglich, gegen 16:00 Uhr MEZ.

**F: Ich sehe einen „500 Internal Server Error“, wenn ich versuche, die Cron-Job-URL direkt aufzurufen.**
A: Dies deutet normalerweise auf einen PHP-Fehler hin. Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers auf spezifischere Details. Häufige Ursachen können falsche Dateiberechtigungen, eine fehlende PHP-Erweiterung oder ein Konflikt mit einem anderen Modul sein. Wenden Sie sich mit den Details des Fehlerprotokolls an Ihren Hosting-Anbieter oder einen Entwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „European Central Bank currency rates“ (`ecbrates`) ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, die Aktualisierung der `ps_currency`-Wechselkurse zu automatisieren. Es folgt einem einfachen Designmuster:

- Eine einzelne Hauptmoduldatei (`cronjob.php`) handhabt die Installation, Deinstallation und die Kernlogik zum Abrufen und Aktualisieren von Wechselkursen.
- Das Modul stellt eine `getContent()`-Methode für seine Back-Office-Konfiguration bereit, die ein grundlegendes Template rendert.
- Die Kernfunktionalität wird über einen direkten Aufruf der `cronjob.php`-Datei des Moduls ausgelöst, typischerweise durch einen serverseitigen Cron-Job, der das Standard-PrestaShop-Front-/Admin-Controller-Routing zur Effizienz umgeht.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine Standard-PrestaShop-Front-Office- oder Back-Office-Admin-Controller. Seine Kernaktualisierungslogik ist direkt über die Datei `cronjob.php` zugänglich, die als eigenständiges Skript fungiert, wenn sie über die Cron-URL aufgerufen wird.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Logik ist in der Hauptdatei `ecbrates/cronjob.php` enthalten. Es interagiert direkt mit den PrestaShop-Kernklassen `Currency` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `ecbrates/views/admin.tpl`: Dieses Template wird von der `getContent()`-Methode der Hauptmoduldatei gerendert. Es zeigt das Konfigurationsformular des Moduls an, einschließlich der Cron-Job-URL und möglicherweise einer manuellen Aktualisierungsschaltfläche. Es ist ein einfaches Template für die Einstellungen des Moduls.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es interagiert mit der Standard-PrestaShop-Tabelle `ps_currency`, um die Spalte `conversion_rate` für aktive Währungen zu aktualisieren.
  - Es speichert seine Konfiguration (z. B. Modul-Aktivierungsstatus) in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `ECBRATES_LAST_UPDATE` oder ähnlichem, obwohl spezifische Schlüssel in den bereitgestellten Informationen nicht explizit detailliert sind.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert sich nicht explizit bei Standard-PrestaShop-Hooks im traditionellen Sinne (z. B. `displayHeader`, `actionValidateOrder`) für seine Kernfunktionalität. Sein primärer Mechanismus ist ein direkter Aufruf seiner `cronjob.php`-Datei.

  Als PrestaShop-Modul verwendet es jedoch implizit:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `install()` | Während der Modulinstallation | Erstellt Konfigurationseinträge, setzt möglicherweise initiale Kurse. |
  | `uninstall()` | Während der Moduldeinstallation | Bereinigt Konfigurationseinträge. |
  | `getContent()` | Beim Zugriff auf die Modulkonfiguration im BO | Rendert das Konfigurationsformular des Moduls. |

  Die Kernfunktionalität des Moduls (Abrufen und Aktualisieren von Kursen) wird durch direkten HTTP-Zugriff auf `cronjob.php` ausgelöst, nicht durch einen PrestaShop-Hook.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „European Central Bank currency rates“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Sie können die neuesten Versionen des Moduls aus Ihrer Bestellhistorie herunterladen. Für Support nutzen Sie bitte die auf der MyPresta.eu-Website bereitgestellten dedizierten Supportkanäle.
