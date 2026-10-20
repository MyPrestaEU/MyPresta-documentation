---
title: "Datenbank-Backup lokal und in der Cloud - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Datenbank-Backup lokal und in der Cloud' von MyPresta.eu."
sidebar:
  label: "Datenbank-Backup lokal und in der Cloud - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Database backup locally and in cloud auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/database-backup-locally-and-in-cloud.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/database-backup-locally-and-in-cloud/)
>
> ---


# Datenbank-Backup lokal und in der Cloud

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ausreichende Serverressourcen (CPU, Speicher) für den Datenbankexport, insbesondere für sehr große Datenbanken, obwohl das Modul darauf ausgelegt ist, diese Probleme durch Chunking zu mindern. Schreibberechtigungen für das Backup-Verzeichnis auf Ihrem Server.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Datenbank-Backup lokal und in der Cloud“ bietet eine umfassende Oberfläche zur Verwaltung Ihrer Backups. Sie werden hauptsächlich mit zwei Hauptbereichen interagieren: der Hauptkonfigurationsseite des Moduls und dem dedizierten Admin-Bildschirm „Meine Backups“.

### 2.1 Hauptkonfigurationsseite des Moduls (Back Office > Module > Modul-Manager > „Datenbank-Backup lokal und in der Cloud“ konfigurieren)

Diese anfängliche Konfigurationsseite (`mybackups/index.php` über `getContent()`) behandelt die grundlegende Einrichtung und Integration des Moduls.

#### Allgemeine Einstellungen

-   **Was diese Einstellung bewirkt:** Diese Einstellungen steuern grundlegende Aspekte der Funktionsweise des Moduls und seiner Integration in Ihre PrestaShop-Umgebung.
-   **Auswirkung einer Änderung dieser Einstellung:** Anpassungen können die Leistung, Sicherheit und die allgemeine Zuverlässigkeit Ihrer Backups beeinflussen.
-   **Empfohlener Wert:** Halten Sie sich im Allgemeinen an die Standardwerte, es sei denn, Sie haben einen bestimmten Grund oder werden vom Support dazu angewiesen.

#### Cloud-Speicher-Integrationen

-   **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, Ihren PrestaShop-Shop mit verschiedenen Cloud-Speicheranbietern zu verbinden, wo Ihre Backups gespeichert werden. Jeder Anbieter (Google Drive, Dropbox, FTP/FTPS, Amazon S3) hat seine eigenen Verbindungsinformationen.
-   **Auswirkung einer Änderung dieser Einstellung:** Eine erfolgreiche Verbindung zu einem Cloud-Dienst aktiviert diesen Dienst als Backup-Ziel. Falsche Anmeldeinformationen verhindern, dass Backups in diese spezifische Cloud hochgeladen werden.
-   **Empfohlener Wert:** Verbinden Sie sich mit mindestens einem Cloud-Speicheranbieter für Off-Site-Backups. Google Drive und Dropbox sind für die meisten Händler oft am einfachsten einzurichten.
-   **Händlerszenario / Beispiel:** Sie möchten Ihre Backups auf Google Drive speichern. Sie würden auf die Schaltfläche „Mit Google Drive verbinden“ klicken, den Authentifizierungsschritten folgen und dem Modul die Berechtigung erteilen, auf einen bestimmten Ordner in Ihrem Google Drive zuzugreifen. Dies stellt sicher, dass Ihre Backups auch bei einem Serverabsturz in der Cloud sicher sind.

### 2.2 Dedizierter Admin-Bildschirm: Meine Backups (Back Office > Meine Backups)

Dies ist die zentrale Anlaufstelle für die Verwaltung all Ihrer Datenbank-Backups. Sie finden diesen Bildschirm unter einem neuen Menüpunkt, der typischerweise „Meine Backups“ oder ähnlich benannt ist und zur PrestaShop-Back-Office-Navigation hinzugefügt wurde. Dieser Bildschirm wird von `mybackups/controllers/admin/AdminMyBackupsController.php` gesteuert.

#### Dashboard & Backup-Liste

-   **Bildschirmname & Menüposition:** Sie finden „Meine Backups“ im Hauptmenü von PrestaShop, normalerweise gruppiert mit „Verwaltung“ oder „Erweiterte Einstellungen“.
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Backup-Liste:** Diese Tabelle zeigt alle Ihre vorhandenen Datenbank-Backups an, ob lokal oder in der Cloud gespeichert. Jeder Eintrag zeigt typischerweise:
        *   **Datum/Uhrzeit:** Wann das Backup erstellt wurde.
        *   **Größe:** Die Größe der komprimierten Backup-Datei.
        *   **Speicherort:** Wo das Backup gespeichert ist (Lokal, Google Drive, Dropbox, FTP, S3).
        *   **Aktionen:**
            *   **Herunterladen:** Laden Sie die Backup-Datei auf Ihren Computer herunter.
            *   **Wiederherstellen:** Starten Sie einen Datenbank-Wiederherstellungsprozess mit diesem Backup. (Seien Sie bei dieser Aktion äußerst vorsichtig, da sie Ihre aktuelle Datenbank überschreibt!)
            *   **Löschen:** Entfernen Sie die Backup-Datei von ihrem Speicherort.
    *   **Schaltfläche „Neues Backup erstellen“:** Eine prominente Schaltfläche, um manuell ein neues Datenbank-Backup zu initiieren.
    *   **Cloud-Speicherstatus:** Visuelle Indikatoren, die zeigen, welche Cloud-Dienste derzeit verbunden und verfügbar sind.
    *   **Geplante Backups:** Ein Abschnitt zum Anzeigen und Verwalten Ihrer automatisierten Backup-Aufgaben (Cron-Jobs).
-   **Auswirkung von Änderungen:**
    *   **Erstellen eines neuen Backups:** Erzeugt einen neuen komprimierten SQL-Dump Ihrer Datenbank und speichert ihn an den konfigurierten Speicherorten (lokal und/oder Cloud).
    *   **Wiederherstellen eines Backups:** Ersetzt Ihre aktuelle Live-Datenbank durch die Daten aus der ausgewählten Backup-Datei. Dies ist eine mächtige und potenziell destruktive Aktion; stellen Sie immer sicher, dass Sie ein frisches Backup haben, bevor Sie eine Wiederherstellung versuchen.
    *   **Löschen eines Backups:** Entfernt die Backup-Datei dauerhaft von ihrem Speicherort.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  **Ersteinrichtung:** Verbinden Sie sich auf der Konfigurationsseite des Moduls mit Ihren bevorzugten Cloud-Speicheranbietern.
    2.  **Backups planen:** Richten Sie einen Cron-Job ein (siehe „Praktische Anwendungsfälle“ unten), um Backups täglich oder wöchentlich automatisch zu erstellen, abhängig von der Aktivität Ihres Shops. Stellen Sie sicher, dass diese geplanten Backups an mindestens einen Cloud-Speicherort gesendet werden.
    3.  **Regelmäßige Überwachung:** Überprüfen Sie regelmäßig das Dashboard „Meine Backups“, um sicherzustellen, dass Backups erfolgreich erstellt werden und Ihre Cloud-Verbindungen aktiv sind.
    4.  **Manuelles Backup (Optional):** Erstellen Sie ein manuelles Backup vor größeren Shop-Änderungen (z. B. Modulinstallationen, Theme-Updates, Produktimporte).
    5.  **Testwiederherstellung (KRITISCH):** Führen Sie gelegentlich eine Testwiederherstellung in einer *Entwicklungs- oder Staging-Umgebung* durch (NIEMALS in Ihrem Live-Shop ohne extreme Vorsicht), um sicherzustellen, dass Ihre Backups gültig sind und der Wiederherstellungsprozess wie erwartet funktioniert.

#### Backup-Erstellungsformular

Wenn Sie auf „Neues Backup erstellen“ klicken, werden Ihnen typischerweise Optionen präsentiert:

-   **Backup-Name:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, Ihrer Backup-Datei einen benutzerdefinierten Namen zur einfachen Identifizierung zu geben.
    *   **Auswirkung einer Änderung dieser Einstellung:** Die Backup-Datei wird mit diesem Namen gespeichert (z. B. `mein-shop-backup-2023-10-27.sql.zip`).
    *   **Empfohlener Wert:** Verwenden Sie einen beschreibenden Namen, der vielleicht das Datum oder eine kurze Notiz über den Grund des Backups enthält (z. B. „Backup vor Update“).
-   **Speicherorte:**
    *   **Was diese Einstellung bewirkt:** Wählen Sie aus, wo die Backup-Datei gespeichert werden soll. Optionen umfassen typischerweise „Lokaler Server“ und alle verbundenen Cloud-Dienste (Google Drive, Dropbox, FTP, S3).
    *   **Auswirkung einer Änderung dieser Einstellung:** Das Backup wird nur an den ausgewählten Speicherorten gespeichert.
    *   **Empfohlener Wert:** Wählen Sie immer „Lokaler Server“ und mindestens eine Cloud-Speicheroption für Redundanz.
-   **Tabellen ausschließen:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Datenbanktabellen auszuwählen, die *nicht* im Backup enthalten sein sollen. Dies kann nützlich sein für sehr große Tabellen, die nicht-kritische oder leicht regenerierbare Daten enthalten (z. B. Cache-Tabellen, Log-Tabellen).
    *   **Auswirkung einer Änderung dieser Einstellung:** Die ausgewählten Tabellen werden übersprungen, was zu einer kleineren Backup-Datei führt.
    *   **Empfohlener Wert:** Für die meisten Händler lassen Sie dies leer, um die gesamte Datenbank zu sichern. Schließen Sie Tabellen nur aus, wenn Sie die Auswirkungen verstehen und versuchen, die Backup-Größe aufgrund schwerwiegender Hosting-Einschränkungen zu reduzieren.
-   **Schaltfläche „Backup starten“:** Startet den Backup-Prozess. Sie sehen typischerweise einen Fortschrittsbalken oder Statusaktualisierungen, während das Backup erstellt und hochgeladen wird.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Allgemeine Einstellungen | Standard | Steuert grundlegende Moduloperationen, Leistung und Sicherheit. |
| | Google Drive Integration | Verbinden | Aktiviert Google Drive als Backup-Ziel. |
| | Dropbox Integration | Verbinden | Aktiviert Dropbox als Backup-Ziel. |
| | FTP/FTPS Integration | Konfigurieren | Aktiviert FTP/FTPS als Backup-Ziel. |
| | Amazon S3 Integration | Konfigurieren | Aktiviert Amazon S3 als Backup-Ziel. |
| **Meine Backups Dashboard** | Neues Backup erstellen | N/A | Startet manuell ein neues Datenbank-Backup. |
| | Backup-Liste (Herunterladen) | N/A | Lädt eine Backup-Datei auf Ihren lokalen Computer herunter. |
| | Backup-Liste (Wiederherstellen) | N/A | **KRITISCH:** Überschreibt die aktuelle Datenbank mit dem ausgewählten Backup. Mit äußerster Vorsicht verwenden, vorzugsweise auf einer Staging-Umgebung. |
| | Backup-Liste (Löschen) | N/A | Entfernt eine Backup-Datei dauerhaft von ihrem Speicherort. |
| **Backup-Erstellungsformular** | Backup-Name | Automatisch generiert | Benutzerdefinierter Name für die Backup-Datei. |
| | Speicherorte | Lokal + Cloud | Wählt aus, wo das Backup gespeichert wird (lokaler Server, Cloud-Dienste). |
| | Tabellen ausschließen | Keine | Überspringt angegebene Tabellen aus dem Backup, um die Dateigröße zu reduzieren. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Backups schlagen fehl oder dauern zu lange. Was soll ich tun?**
A:

-   **Serverressourcen prüfen:** Große Datenbanken erfordern erheblichen Serverspeicher und Ausführungszeit. Obwohl das Modul Exporte in Chunks aufteilt, können sehr eingeschränkte Hosting-Umgebungen immer noch Probleme haben. Kontaktieren Sie Ihren Host, um die PHP-Speicherlimits (`memory_limit`) und die maximale Ausführungszeit (`max_execution_time`) zu überprüfen.
-   **Cache leeren:** Manchmal kann der PrestaShop-Cache stören. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
-   **Tabellen ausschließen:** Erwägen Sie, nicht-kritische Tabellen (wie Cache- oder Statistiktabellen) aus dem Backup auszuschließen, wenn diese sehr groß sind. Dies kann die Backup-Größe und -Zeit erheblich reduzieren.
-   **Fehlerprotokolle prüfen:** Suchen Sie in Ihren PrestaShop-Fehlerprotokollen (normalerweise `var/logs/` oder `app/logs/` je nach PS-Version) oder den PHP-Fehlerprotokollen Ihres Servers nach spezifischen Fehlermeldungen.

**F: Ich habe mich mit Google Drive/Dropbox verbunden, aber ich sehe meine Backups dort nicht.**
A:

-   **Verbindungsstatus prüfen:** Gehen Sie zur Konfigurationsseite des Moduls und überprüfen Sie, ob Ihr Cloud-Dienst als „Verbunden“ angezeigt wird. Wenn nicht, versuchen Sie, die Verbindung erneut herzustellen.
-   **Ordnerberechtigungen:** Stellen Sie sicher, dass das Modul die notwendigen Berechtigungen zum Schreiben in den angegebenen Ordner in Ihrem Cloud-Speicher hat. Für Google Drive/Dropbox erstellt das Modul normalerweise einen eigenen Ordner.
-   **Manueller Upload-Test:** Versuchen Sie, ein kleines manuelles Backup zu erstellen und den Cloud-Dienst explizit als Ziel auszuwählen, um zu sehen, ob es erfolgreich hochgeladen wird.
-   **Cloud-Speicher direkt prüfen:** Melden Sie sich über deren Website bei Ihrem Google Drive- oder Dropbox-Konto an und durchsuchen Sie die Ordner manuell, um zu sehen, ob die Backups dort vorhanden sind, vielleicht an einem unerwarteten Ort.

**F: Wie stelle ich meine Datenbank aus einem Backup wieder her?**
A:

-   **WARNUNG:** Das Wiederherstellen einer Datenbank überschreibt Ihre aktuelle Live-Datenbank. Dies ist eine hochgradig destruktive Aktion. **Erstellen Sie immer ein frisches Backup Ihrer aktuellen Datenbank, bevor Sie eine Wiederherstellung versuchen.**
-   Gehen Sie zu **Back Office > Meine Backups**.
-   Suchen Sie die Backup-Datei, die Sie wiederherstellen möchten, in der Liste.
-   Klicken Sie auf die Schaltfläche „Wiederherstellen“ neben diesem Backup.
-   Befolgen Sie die Anweisungen auf dem Bildschirm. Das Modul führt Sie durch den Prozess.
-   Wenn Ihr Shop vollständig ausgefallen ist, müssen Sie die Backup-Datei möglicherweise manuell per FTP hochladen und dann die Moduloberfläche oder ein Tool wie phpMyAdmin verwenden, um sie zu importieren. In solchen kritischen Situationen ist es am besten, einen Entwickler oder Ihren Hosting-Anbieter zu konsultieren.

**F: Was passiert, wenn meinem Server während eines lokalen Backups der Speicherplatz ausgeht?**
A: Der Backup-Prozess wird wahrscheinlich fehlschlagen, und Sie erhalten eine Fehlermeldung bezüglich des Speicherplatzes. Stellen Sie sicher, dass Sie ausreichend freien Speicherplatz auf Ihrem Server haben, insbesondere wenn Sie mehrere lokale Backups speichern oder eine sehr große Datenbank haben. Löschen Sie regelmäßig alte lokale Backups, die bereits sicher in die Cloud hochgeladen wurden.

**F: Mein benutzerdefiniertes Theme wird nach einer Wiederherstellung nicht korrekt angezeigt.**
A: Datenbank-Backups stellen hauptsächlich Ihre Daten wieder her. Theme-Dateien, Moduldateien und Bilder werden typischerweise im Dateisystem Ihres Servers gespeichert, nicht direkt in der Datenbank.

-   **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie alle Caches (Smarty, Dateisystem usw.).
-   **Dateisystem prüfen:** Stellen Sie sicher, dass alle Ihre Theme-Dateien, Moduldateien und Bildordner auf dem Server vorhanden sind und die richtigen Berechtigungen haben. Eine Datenbankwiederherstellung hat keinen Einfluss auf diese Dateien. Wenn Sie von einem sehr alten Backup wiederhergestellt haben, müssen einige Modulkonfigurationen möglicherweise im Back Office neu gespeichert werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Architektur und den Code des Moduls „Datenbank-Backup lokal und in der Cloud“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das MyBackups-Modul ist mit einem starken Fokus auf Robustheit, Skalierbarkeit und Fehlertoleranz konzipiert, insbesondere für die Handhabung großer Datenbankoperationen und externer Cloud-Integrationen. Es verfolgt einen modularen, objektorientierten Ansatz, der PrestaShops MVC-Muster nutzt, wo es angebracht ist, aber auch eine eigene interne serviceorientierte Architektur für die Kernlogik von Backup/Restore implementiert.

Wichtige Architekturmuster umfassen:

-   **Chunked Processing:** Datenbankexport und -import werden in kleinere, überschaubare Chunks unterteilt, um PHP-Ausführungszeit- und Speicherlimits zu umgehen.
-   **State Management:** Ein robustes Zustandsverwaltungssystem (`MyBackupsStateManager`) verfolgt den Fortschritt langlaufender Backup-/Restore-Jobs und ermöglicht die Ausführung über Web-Cron und die Wiederherstellung nach Unterbrechungen.
-   **Storage Abstraction:** Ein Schnittstellen-basiertes Design (`MyBackupsStorageInterface`) ermöglicht die einfache Integration neuer Cloud-Speicheranbieter, ohne die Kern-Backup-Logik zu ändern.
-   **OAuth Integration:** Sichere OAuth 2.0-Flows für Google Drive und Dropbox, die die Speicherung und Aktualisierung von Tokens handhaben.
-   **Cron/Job Runner:** Dedizierte Front-Controller und Klassen zum Auslösen und Verwalten von Hintergrundjobs über Cron oder Web-Cron.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller werden hauptsächlich für Hintergrundaufgaben und OAuth-Rückrufe verwendet, nicht zum Rendern von kundenorientierten Inhalten.

-   `mybackups/controllers/front/cron.php`
    *   **Klassenname & Elternklasse:** `MyBackupsCronModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller dient als Einstiegspunkt für geplante Cron-Jobs. Wenn er mit dem korrekten Token aufgerufen wird, löst er den `MyBackupsCronRunner` aus, um ausstehende Backup-Aufgaben zu verarbeiten. Er ist dafür konzipiert, extern von einem Server-Cron-Daemon oder einem Web-Cron-Dienst aufgerufen zu werden.
-   `mybackups/controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `MyBackupsIndexModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Ein Platzhalter oder Standard-Front-Controller, oft für Modul-Routing oder einfache Weiterleitungen verwendet, wenn keine spezifische Aktion angefordert wird. In diesem Modul könnte er als Basis oder Fallback dienen.
-   `mybackups/controllers/front/job.php`
    *   **Klassenname & Elternklasse:** `MyBackupsJobModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Behandelt AJAX-Anfragen im Zusammenhang mit dem Fortschritt und Status laufender Backup-/Restore-Jobs. Er interagiert mit `MyBackupsJobRunner` und `MyBackupsStateManager`, um Echtzeit-Updates für die Back-Office-Benutzeroberfläche bereitzustellen.
-   `mybackups/controllers/front/oauthdropbox.php`
    *   **Klassenname & Elternklasse:** `MyBackupsOauthdropboxModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dies ist die Callback-URI für den Dropbox OAuth 2.0-Flow. Nachdem ein Händler das Modul bei Dropbox autorisiert hat, leitet Dropbox zu diesem Controller um, der dann den Austausch des Autorisierungscodes gegen ein Zugriffstoken handhabt und dieses sicher speichert.
-   `mybackups/controllers/front/oauthgdrive.php`
    *   **Klassenname & Elternklasse:** `MyBackupsOauthgdriveModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Ähnlich wie `oauthdropbox.php` ist dies die Callback-URI für den Google Drive OAuth 2.0-Flow. Sie verarbeitet den Autorisierungscode von Google und erhält/speichert die notwendigen Zugriffs- und Refresh-Tokens.

#### Back-Office-Admin-Controller

Diese Controller verwalten die Schnittstelle des Moduls innerhalb des PrestaShop Back Office.

-   `mybackups/controllers/admin/AdminMyBackupsController.php`
    *   **Klassenname & Elternklasse:** `AdminMyBackupsController` erweitert `ModuleAdminController`.
    *   **Tab-Name und verwaltete Entität:** Dies ist der primäre Admin-Controller für das Dashboard „Meine Backups“. Er verwaltet die Auflistung, Erstellung, den Download, die Wiederherstellung und das Löschen von Backup-Dateien. Er orchestriert Interaktionen mit `MyBackupsCatalog`, `MyBackupsExporter`, `MyBackupsImporter` und den verschiedenen Speicherklassen.
-   `mybackups/controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** Standard PrestaShop `index.php`-Datei für Admin-Controller-Verzeichnisse.
    *   **Verantwortlichkeit:** Verhindert direkte Verzeichnisauflistung und gewährleistet sicheren Zugriff auf die Admin-Controller.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `mybackups/classes/index.php`: Standard leere `index.php`, um Verzeichnisauflistung zu verhindern.
-   `mybackups/classes/MyBackupsAdminAjax.php`: Behandelt verschiedene AJAX-Anfragen von der Admin-Oberfläche, wie das Abrufen von Backup-Listen, das Initiieren spezifischer Aktionen oder das Aktualisieren von UI-Elementen.
-   `mybackups/classes/MyBackupsAdminForms.php`: Wahrscheinlich verantwortlich für das Rendern und Verarbeiten der Konfigurationsformulare des Moduls im Back Office, einschließlich der Cloud-Integrations-Einstellungen.
-   `mybackups/classes/MyBackupsCatalog.php`: Verwaltet den Katalog der Backup-Dateien, ob lokal oder in der Cloud. Es bietet Methoden zum Auflisten, Filtern und Abrufen von Informationen über vorhandene Backups.
-   `mybackups/classes/MyBackupsCloudUi.php`: Hilft bei der Generierung der UI-Elemente und der Logik für die Cloud-Speicherintegration im Back Office (z. B. Verbindungsbuttons, Statusindikatoren).
-   `mybackups/classes/MyBackupsCronRunner.php`: Die Kernlogik für die Ausführung geplanter Backup-Jobs. Sie prüft auf ausstehende Aufgaben und initiiert `MyBackupsJobRunner` für jede.
-   `mybackups/classes/MyBackupsDumpVerifier.php`: Verantwortlich für die Überprüfung der Integrität und Gültigkeit von SQL-Dump-Dateien, möglicherweise durch Überprüfung auf häufige Fehler oder unvollständige Dumps.
-   `mybackups/classes/MyBackupsExporter.php`: Handhabt den eigentlichen Datenbankexportprozess, einschließlich des Chunkings des SQL-Dumps, der Tabellenfilterung und der Komprimierung.
-   `mybackups/classes/MyBackupsImporter.php`: Verwaltet den Datenbankimport (Wiederherstellungsprozess), parst den SQL-Dump und führt Abfragen in Chunks aus.
-   `mybackups/classes/MyBackupsJobLock.php`: Implementiert einen Sperrmechanismus, um zu verhindern, dass mehrere gleichzeitige Backup-/Restore-Jobs gleichzeitig ausgeführt werden, wodurch Datenkonsistenz gewährleistet und Ressourcenkonflikte vermieden werden.
-   `mybackups/classes/MyBackupsJobRunner.php`: Orchestriert den gesamten Backup- oder Restore-Job, verwaltet die Abfolge der Schritte (Export, Komprimieren, Hochladen/Herunterladen, Import) und interagiert mit `MyBackupsStateManager`.
-   `mybackups/classes/MyBackupsMemoryGuard.php`: Eine Dienstprogrammklasse zur Überwachung und Verwaltung der PHP-Speichernutzung während intensiver Operationen, um Out-of-Memory-Fehler zu verhindern.
-   `mybackups/classes/MyBackupsOAuthReturn.php`: Handhabt die letzten Schritte des OAuth-Callback-Prozesses, verarbeitet den zurückgegebenen Autorisierungscode und verwaltet die Token-Speicherung.
-   `mybackups/classes/MyBackupsOAuthState.php`: Verwaltet den Statusparameter während OAuth-Flows, um CSRF-Angriffe zu verhindern.
-   `mybackups/classes/MyBackupsPaths.php`: Bietet eine zentrale Verwaltung von Dateipfaden und Verzeichnissen, die vom Modul verwendet werden (z. B. Backup-Speicherverzeichnis).
-   `mybackups/classes/MyBackupsStateManager.php`: Entscheidend für langlaufende Jobs. Es speichert und ruft den aktuellen Zustand eines Backup-/Restore-Vorgangs ab, wodurch Jobs über mehrere HTTP-Anfragen hinweg angehalten und fortgesetzt werden können (z. B. während der Cron-Ausführung oder webbasierter Fortschrittsaktualisierungen).
-   `mybackups/classes/MyBackupsTableFilter.php`: Implementiert Logik zum Filtern von Datenbanktabellen während des Exports, basierend auf Benutzerauswahlen.
-   `mybackups/classes/MyBackupsTimeBudget.php`: Hilft bei der Verwaltung von Ausführungszeitlimits für langlaufende Prozesse, wodurch das Modul graceful stoppen und den Zustand speichern kann, bevor `max_execution_time` erreicht wird.
-   `mybackups/classes/MyBackupsTokenCrypto.php`: Handhabt die Verschlüsselung und Entschlüsselung sensibler OAuth-Tokens und API-Schlüssel für eine sichere Speicherung.
-   `mybackups/classes/MyBackupsZip.php`: Verwaltet die Komprimierung und Dekomprimierung von Backup-Dateien in ZIP-Archive.

#### Speicher-Unterklassen (`classes/storage/`)

Dieses Verzeichnis enthält Klassen, die das `MyBackupsStorageInterface` für verschiedene Speicher-Backends implementieren.

-   `mybackups/classes/storage/index.php`: Standard leere `index.php`.
-   `mybackups/classes/storage/MyBackupsCloudUploader.php`: Eine generische Klasse zur Verwaltung des Upload-Prozesses in den Cloud-Speicher, die möglicherweise Chunked-Uploads und Fortschrittsverfolgung handhabt.
-   `mybackups/classes/storage/MyBackupsDropboxStorage.php`: Implementiert `MyBackupsStorageInterface` für die Interaktion mit der Dropbox-API.
-   `mybackups/classes/storage/MyBackupsFtpStorage.php`: Implementiert `MyBackupsStorageInterface` für die Interaktion mit FTP/FTPS-Servern.
-   `mybackups/classes/storage/MyBackupsGoogleDriveStorage.php`: Implementiert `MyBackupsStorageInterface` für die Interaktion mit der Google Drive API.
-   `mybackups/classes/storage/MyBackupsHttp.php`: Eine Dienstprogrammklasse zum Ausführen von HTTP-Anfragen, die wahrscheinlich von Cloud-Speicherklassen für API-Aufrufe verwendet wird.
-   `mybackups/classes/storage/MyBackupsLocalStorage.php`: Implementiert `MyBackupsStorageInterface` zum Speichern und Abrufen von Backups im lokalen Server-Dateisystem.
-   `mybackups/classes/storage/MyBackupsS3Storage.php`: Implementiert `MyBackupsStorageInterface` für die Interaktion mit Amazon S3.
-   `mybackups/classes/storage/MyBackupsStorageFactory.php`: Eine Factory-Pattern-Klasse, die für die Instanziierung der korrekten Speicherklasse basierend auf der Konfiguration verantwortlich ist.
-   `mybackups/classes/storage/MyBackupsStorageInterface.php`: Definiert den Vertrag (Methoden), den alle Speicherklassen implementieren müssen (z. B. `upload`, `download`, `delete`, `list_files`).

### 4.4 JavaScript-Assets (`views/js/`)

-   `mybackups/lib/searchTool/views/js/autocomplete.js`:
    *   **Geltungsbereich:** Wahrscheinlich Back-Office.
    *   **Details:** Bietet Autocomplete-Funktionalität, möglicherweise zum Suchen in Datenbanktabellen beim Konfigurieren von Ausschlüssen oder zum Filtern von Backup-Listen.
-   `mybackups/views/js/mybackups-cloud.js`:
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Handhabt clientseitige Interaktionen für die Cloud-Speicherkonfiguration. Dies umfasst AJAX-Aufrufe zum Verbinden/Trennen von Diensten, zur Aktualisierung der Benutzeroberfläche basierend auf dem Verbindungsstatus und möglicherweise zur Ordnernavigation innerhalb von Cloud-Diensten.
-   `mybackups/views/js/mybackups-job.js`:
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Verwaltet die Echtzeit-Fortschrittsanzeige für Backup- und Wiederherstellungsjobs. Es verwendet AJAX, um den `job.php`-Front-Controller nach Updates zum Job-Status abzufragen, Fortschrittsbalken und Statusmeldungen zu aktualisieren und Job-Abschluss- oder Fehlermeldungen zu verarbeiten.
-   `mybackups/views/js/mybackups-table-picker.js`:
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Bietet die interaktive Oberfläche zum Auswählen oder Ausschließen von Datenbanktabellen während der Backup-Erstellung, möglicherweise einschließlich Such- und Mehrfachauswahlfunktionen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `mybackups/lib/searchTool/views/css/autocomplete.css`:
    *   **Geltungsbereich:** Back-Office-Admin-Styling.
    *   **Details:** Stile für die Autocomplete-Eingabefelder und Vorschlagslisten, die im Back Office verwendet werden.
-   `mybackups/views/css/admin.css`:
    *   **Geltungsbereich:** Back-Office-Admin-Styling.
    *   **Details:** Enthält das Haupt-Styling für die Back-Office-Oberfläche des Moduls, einschließlich Dashboard, Backup-Liste, Formularen, Fortschrittsbalken und Cloud-Integrationsbereichen. Entwickler können diese Stile in ihrem benutzerdefinierten Admin-Theme überschreiben oder bei Bedarf über einen Hook benutzerdefiniertes CSS hinzufügen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   `mybackups/lib/searchTool/views/scripts.tpl`:
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Enthält wahrscheinlich JavaScript- und CSS-Assets für das Such-/Autocomplete-Tool, möglicherweise über `displayBackOfficeHeader` oder ähnliches eingebunden.
-   `mybackups/views/templates/admin/backups.tpl`:
    *   **Geltungsbereich:** Admin-Template.
    *   **Details:** Das Haupt-Template zur Anzeige der Liste der vorhandenen Backups, einschließlich Spalten für Datum, Größe, Speicherort und Aktionsschaltflächen (Herunterladen, Wiederherstellen, Löschen). Dies ist der Kern der Anzeige des `AdminMyBackupsController`.
-   `mybackups/views/templates/admin/configure.tpl`:
    *   **Geltungsbereich:** Admin-Template.
    *   **Details:** Rendert das Hauptkonfigurationsformular des Moduls, das typischerweise über `getContent()` in der Hauptmoduldatei aufgerufen wird. Dies umfasst allgemeine Einstellungen und die anfängliche Einrichtung für Cloud-Dienstintegrationen.
-   `mybackups/views/templates/admin/dashboard.tpl`:
    *   **Geltungsbereich:** Admin-Template.
    *   **Details:** Das übergeordnete Dashboard-Template für den Abschnitt „Meine Backups“, das Elemente wie die Backup-Liste, die Schaltfläche „Neues Backup erstellen“, Cloud-Statusindikatoren und möglicherweise Informationen zu geplanten Backups kombiniert.
-   `mybackups/views/templates/admin/job-progress.tpl`:
    *   **Geltungsbereich:** Admin-Template.
    *   **Details:** Zeigt den Fortschrittsbalken und Statusmeldungen für laufende Backup- oder Wiederherstellungsjobs an, dynamisch aktualisiert durch `mybackups-job.js`.
-   `mybackups/views/templates/admin/table-picker.tpl`:
    *   **Geltungsbereich:** Admin-Template.
    *   **Details:** Rendert die Oberfläche zum Auswählen oder Ausschließen von Datenbanktabellen während der Backup-Erstellung.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen zum Speichern von Backup-Daten selbst, da Backups Dateien sind.
    *   Es speichert Konfigurationswerte in der PrestaShop-Tabelle `ps_configuration`, wie zum Beispiel:
        *   Cloud-API-Schlüssel/Geheimnisse (verschlüsselt).
        *   OAuth-Tokens (verschlüsselt).
        *   Modulspezifische Einstellungen (z. B. Standard-Backup-Speicherorte, Cron-Token).
        *   Job-Statusinformationen für `MyBackupsStateManager`.
-   **Registrierte Hooks-Tabelle**:
    Das Modul verwendet hauptsächlich Back-Office-Hooks und Front-Controller für seine Funktionalität. Die aufgeführten Front-Office-Hooks (Header, Columns, Product, Footer) werden von diesem Modul wahrscheinlich *nicht* verwendet, da seine Funktionalität rein administrativ und backend-orientiert ist. Wenn sie verwendet würden, wäre es für sehr spezifische, nicht sichtbare Zwecke, wie das Laden von Assets oder das Durchführen von Hintergrundprüfungen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich der Back-Office-Seiten gerendert. | Wird verwendet, um modulspezifisches CSS (`admin.css`) und JavaScript (`mybackups-cloud.js`, `mybackups-job.js`, `mybackups-table-picker.js`, `autocomplete.js`) in das Admin-Panel einzufügen. |
| `displayAdminProductsExtra` (oder ähnlich) | Potenziell zum Hinzufügen einer Backup-Option auf der Produktbearbeitungsseite, obwohl für dieses Modul unwahrscheinlich. | (Falls verwendet) Zum Hinzufügen einer spezifischen Backup-Aktion oder Informationen zu Produktdaten. |
| `actionModuleInstall` | Wird ausgeführt, wenn das Modul installiert wird. | Erstellt notwendige Verzeichnisse, setzt Standardkonfigurationswerte, registriert Admin-Menü-Tabs und richtet möglicherweise anfängliche Cron-Job-Anweisungen ein. |
| `actionModuleUninstall` | Wird ausgeführt, wenn das Modul deinstalliert wird. | Bereinigt Konfigurationswerte, entfernt Admin-Menü-Tabs und löscht modulspezifische Verzeichnisse (lässt jedoch oft Backup-Dateien zur Sicherheit bestehen). |
| `actionAdminControllerSetMedia` | Wird ausgeführt, bevor ein Admin-Controller seine Seite rendert. | Wird verwendet, um spezifische CSS/JS-Assets nur zu den eigenen Admin-Seiten des Moduls (`AdminMyBackupsController`) hinzuzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Datenbank-Backup lokal und in der Cloud“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität und Konfiguration des Moduls gerne zur Verfügung.
