---
title: "Kunden mit Adresse exportieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kunden mit Adresse exportieren“ von MyPresta.eu."
sidebar:
  label: "Kunden mit Adresse exportieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Export Customers with address auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/export-customers-with-address.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/export-customers-with-address/)
>
> ---


# Kunden mit Adresse exportieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop-Module ausreichend. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ des Moduls zu dessen Hauptkonfigurationsseite. Dieser Bildschirm verwaltet hauptsächlich interne Moduleinstellungen im Zusammenhang mit Updates.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt verwaltet typischerweise interne Modul-Update-Prüfungen und Versionsinformationen. Diese Einstellungen dienen normalerweise dem internen Gebrauch des Moduls, um sicherzustellen, dass Sie die neueste Version verwenden, und um Update-Benachrichtigungen bereitzustellen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *`mypresta_updates`*: Dies ist wahrscheinlich ein internes Flag, um Update-Prüfungen von MyPresta.eu zu aktivieren oder zu deaktivieren.
  - *`update_`*: Dies könnte den Zeitpunkt der letzten Update-Prüfung speichern.
  - *`updatev_`*: Dies könnte die neueste verfügbare Version speichern, die erkannt wurde.
- **Empfohlener Wert:** Es wird generell empfohlen, diese Einstellungen auf ihren Standardwerten zu belassen, um sicherzustellen, dass Sie wichtige Update-Benachrichtigungen erhalten.
- **Händlerszenario / Beispiel:** Sie interagieren normalerweise nicht direkt mit diesen Einstellungen. Sie arbeiten im Hintergrund, um Sie darüber zu informieren, ob eine neue Version des Moduls verfügbar ist, und stellen sicher, dass Sie Zugriff auf die neuesten Funktionen und Fehlerbehebungen haben.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Kunden mit Adresse exportieren (Back Office > Erweiterte Einstellungen > Kunden mit Adresse exportieren)

Dies ist der Hauptbildschirm, auf dem Sie den Kundenexport durchführen werden. Sie finden ihn unter dem Menü „Erweiterte Einstellungen“ in Ihrem PrestaShop Back Office.

- **Bildschirmname & Menüpfad:** **Erweiterte Einstellungen > Kunden mit Adresse exportieren**
- **Verfügbare Aktionen & Einstellungen:**
  - Wenn Sie zu diesem Bildschirm navigieren, sehen Sie eine Schaltfläche oder einen Link, um den Exportvorgang zu starten. Das Modul bereitet automatisch eine CSV-Datei vor, die alle Kundendaten und deren zugehörige Adressen enthält.
  - Die exportierte Datei enthält die folgenden Spalten, formatiert für das PrestaShop-Import-Tool:
    - **Kunden-ID**: Eindeutiger Bezeichner für den Kunden.
    - **Aktiv (0/1)**: Ob das Kundenkonto aktiv (1) oder inaktiv (0) ist.
    - **Anrede-ID (Herr = 1, Frau = 2, sonst 0)**: Die ID, die der Anrede des Kunden entspricht (z. B. Herr, Frau).
    - \*\*E-Mail \*\*\*: Die E-Mail-Adresse des Kunden (obligatorisch).
    - \*\*Passwort \*\*\*: Das Passwort des Kunden (obligatorisch, normalerweise gehasht).
    - **Geburtstag (jjjj-mm-tt)**: Das Geburtsdatum des Kunden.
    - \*\*Nachname \*\*\*: Der Nachname des Kunden (obligatorisch).
    - \*\*Vorname \*\*\*: Der Vorname des Kunden (obligatorisch).
    - **Newsletter (0/1)**: Ob der Kunde den Newsletter abonniert hat (1) oder nicht (0).
    - **Opt-in (0/1)**: Ob der Kunde Partnerangeboten zugestimmt hat (1) oder nicht (0).
    - **Registrierungsdatum**: Das Datum, an dem der Kunde sein Konto registriert hat.
    - **Gruppen (x,y,z…)**: Eine durch Kommas getrennte Liste der IDs der Kundengruppen, denen der Kunde angehört.
    - **Standardgruppen-ID**: Die ID der Standardgruppe des Kunden.
    - **ID / Name des Shops**: Die ID oder der Name des Shops, dem der Kunde zugeordnet ist (nützlich in Multi-Store-Umgebungen).
    - **Adress-ID**: Eindeutiger Bezeichner für die Adresse des Kunden.
    - \*\*Alias \*\*\*: Ein Alias für die Adresse (z. B. „Meine Privatadresse“).
    - \*\*Kunden-E-Mail \*\*\*: Die mit dieser Adresse verknüpfte E-Mail (sollte mit der E-Mail des Kunden übereinstimmen).
    - **Hersteller**: (Falls zutreffend)
    - **Lieferant**: (Falls zutreffend)
    - **Firma**: Der Firmenname, der mit der Adresse verknüpft ist.
    - … und andere Standard-Adressfelder wie `Adresse1`, `Adresse2`, `Postleitzahl`, `Stadt`, `Land`, `Telefon`, `Mobiltelefon`, `USt-IdNr.`, etc.
- **Auswirkung von Änderungen:** Durch Klicken auf die Export-Schaltfläche wird eine CSV-Datei generiert und auf Ihren Computer heruntergeladen. Diese Aktion ändert keine Daten in Ihrem PrestaShop-Shop; sie extrahiert sie nur.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Regelmäßige Backups:** Exportieren Sie Ihre Kundendaten regelmäßig als Backup, insbesondere vor größeren Shop-Updates oder Migrationen.
  2. **Generierung von Marketinglisten:** Exportieren Sie Kundendaten, um Listen für E-Mail-Marketingkampagnen zu erstellen, segmentiert nach Gruppen oder Registrierungsdaten.
  3. **CRM-Updates:** Wenn Sie ein externes CRM verwenden, exportieren Sie Daten, um diese mit Ihrem PrestaShop-Kundenstamm synchron zu halten.

#### 2.2.2 AdminExportCustomersController (index.php)

Diese Datei dient wahrscheinlich als Einstiegspunkt oder Helfer für den `AdminExportCustomersController`, um sicherzustellen, dass die administrative Oberfläche des Moduls im PrestaShop Back Office korrekt funktioniert. Sie präsentiert keinen separaten konfigurierbaren Bildschirm, sondern erleichtert die Anzeige und Funktionalität des Haupt-Exportbildschirms.

### 2.3 Kurzübersicht Konfigurationstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | `mypresta_updates` | Aktiviert | Internes Flag für MyPresta.eu-Update-Prüfungen. Für Benachrichtigungen aktiviert lassen. |
| Modulkonfigurationsseite | `update_` | (Intern) | Speichert den Zeitstempel der letzten Update-Prüfung. |
| Modulkonfigurationsseite | `updatev_` | (Intern) | Speichert die neueste verfügbare Modulversion. |
| Erweiterte Einstellungen > Kunden mit Adresse exportieren | Export-Schaltfläche | N/A | Startet den Download einer CSV-Datei mit allen Kunden- und Adressdaten. |
| Erweiterte Einstellungen > Kunden mit Adresse exportieren | Exportierte CSV-Spalten | N/A | Enthält Kunden-ID, Aktiv, Anrede-ID, E-Mail, Passwort, Geburtstag, Nachname, Vorname, Newsletter, Opt-in, Registrierungsdatum, Gruppen, Standardgruppen-ID, Shop-ID/Name, Adress-ID, Alias, Kunden-E-Mail, Firma und alle Standard-Adressfelder. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe auf die Export-Schaltfläche geklickt, aber es ist nichts passiert oder die Datei ist leer.**
**A1:**

- **Überprüfen Sie Pop-up-Blocker im Browser:** Ihr Browser blockiert möglicherweise den Dateidownload. Suchen Sie nach einer Benachrichtigung oder einem Symbol in der Adressleiste Ihres Browsers und erlauben Sie Downloads von Ihrem PrestaShop-Admin.
- **Modulberechtigungen:** Stellen Sie sicher, dass das Modul die notwendigen Dateisystemberechtigungen zum Erstellen und Bereitstellen der CSV-Datei hat. Obwohl selten, können falsche Berechtigungen die Dateigenerierung verhindern.
- **Server-Speicherlimits:** Wenn Sie eine sehr große Anzahl von Kunden haben, könnte der Exportprozess auf PHP-Speicherlimits auf Ihrem Server stoßen. Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers (oft in `var/logs` oder Ihrem Hosting-Kontrollpanel zu finden) auf speicherbezogene Fehler. Möglicherweise müssen Sie `memory_limit` in Ihrer `php.ini`-Datei vorübergehend erhöhen.
- **Leere Kundendatenbank:** Überprüfen Sie, ob Sie tatsächlich Kunden in Ihrem Shop registriert haben.

**F2: Die exportierte CSV-Datei sieht verzerrt aus oder enthält seltsame Zeichen.**
**A2:** Dies ist oft ein Kodierungsproblem.

- **Mit korrekter Kodierung öffnen:** Wenn Sie die CSV-Datei in einem Tabellenkalkulationsprogramm (wie Excel) öffnen, stellen Sie sicher, dass Sie **UTF-8** als Dateiquelle oder Kodierung auswählen. Die meisten modernen Systeme verwenden UTF-8, und PrestaShop-Exporte sind typischerweise in diesem Format.
- **PrestaShop-Spracheinstellungen überprüfen:** Stellen Sie sicher, dass die Standardsprache und der Zeichensatz Ihres PrestaShop-Shops unter **International > Lokalisierung** korrekt konfiguriert sind.

**F3: Kann ich auswählen, welche Felder exportiert werden sollen?**
**A3:** Dieses Modul exportiert einen vordefinierten Satz von Kunden- und Adressfeldern, die mit dem nativen Import-Tool von PrestaShop kompatibel sind. Es bietet keine Optionen zum Auswählen oder Abwählen einzelner Felder. Wenn Sie einen hochgradig angepassten Export benötigen, benötigen Sie möglicherweise ein fortschrittlicheres Exportmodul oder eine kundenspezifische Entwicklung.

**F4: Beeinträchtigt der Export von Kunden die Leistung meines Shops?**
**A4:** Für die meisten Shops hat ein einmaliger Export eine vernachlässigbare Auswirkung. Bei Shops mit Hunderttausenden von Kunden kann der Exportprozess einige Momente dauern und einige Serverressourcen verbrauchen. Es wird generell empfohlen, große Exporte während der Nebenzeiten durchzuführen, wenn Sie eine sehr lange Verarbeitungszeit erwarten. Das Modul ist auf Effizienz ausgelegt, aber Serverressourcen sind immer ein Faktor.

**F5: Ich möchte die Kunden nach Änderungen erneut importieren. Wie mache ich das?**
**A5:** Dieses Modul übernimmt nur den Export. Zum erneuten Importieren verwenden Sie das native Import-Tool von PrestaShop:

1. Gehen Sie zu **Erweiterte Einstellungen > Importieren**.
2. Wählen Sie „Kunden“ oder „Adressen“ als zu importierende Entität aus.
3. Laden Sie Ihre geänderte CSV-Datei hoch.
4. Ordnen Sie die Spalten aus Ihrer CSV sorgfältig den PrestaShop-Datenbankfeldern zu.

Testen Sie Importe immer zuerst in einer Entwicklungs- oder Staging-Umgebung und stellen Sie sicher, dass Sie ein vollständiges Datenbank-Backup haben, bevor Sie große Importe in Ihrem Live-Shop durchführen. Falsche Importe können zu Datenverlust oder -beschädigung führen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Kunden mit Adresse exportieren“ (`exportcustomers`) ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Back-Office-Funktionalität konzentriert. Es folgt einem Standard-PrestaShop-MVC-Muster für seine administrative Oberfläche. Die Kernlogik befindet sich in der Hauptmoduldatei und einem dedizierten Admin-Controller. Es führt keine neuen Datenbanktabellen ein, sondern nutzt bestehende PrestaShop `Customer`- und `Address`-`ObjectModel`-Strukturen, um Daten für den Export abzurufen und zu formatieren. Die Einfachheit des Moduls bedeutet, dass es keine Front-Office-Komponenten, benutzerdefinierten Klassen oder komplexe JavaScript/CSS-Assets hat.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Dieses Modul hat keine Front-Office-Funktionalität.
- **Back-Office-Admin-Controller**:

  - `exportcustomers/controllers/admin/AdminExportCustomers.php`
    - **Klassenname & Elternklasse**: `AdminExportCustomersController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dies ist der primäre Controller, der für die Exportlogik von Kunden und Adressen verantwortlich ist. Wenn er über das PrestaShop Back Office-Menü aufgerufen wird, initiiert er den Prozess des Abrufens von Kunden- und Adressdaten aus der Datenbank, formatiert sie in einen CSV-String und sendet sie als herunterladbare Datei an den Browser. Er erstellt die CSV-Kopfzeile mit allen angegebenen Feldern (Kunden-ID, E-Mail, Adress-ID, Alias usw.) und iteriert dann durch `Customer`- und `Address`-Objekte, um die Datenzeilen zu füllen.
  - `exportcustomers/controllers/admin/index.php`
    - **Verantwortlichkeit**: Dies ist eine häufige Platzhalterdatei in PrestaShop-Modul-Admin-Controller-Verzeichnissen. Sie enthält typischerweise eine einfache `header('Location: ../../index.php?controller=AdminHome')` oder eine ähnliche Weiterleitung, um direkte Verzeichnisauflistungen oder Zugriffe zu verhindern und so die Sicherheit und das ordnungsgemäße Routing innerhalb des PrestaShop Back Office zu gewährleisten. Sie enthält keine funktionale Logik für das Modul selbst.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` ein. Es verwendet direkt die Kern-`Customer`- und `Address`-`ObjectModel`-Klassen von PrestaShop, um Daten aus der Datenbank abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Der Exportprozess wird typischerweise durch eine einfache Formularübermittlung oder einen direkten Link initiiert, der vollständig vom PHP-Controller verarbeitet wird.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Seine Back-Office-Oberfläche basiert vollständig auf dem Standard-PrestaShop-Back-Office-Styling.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Der `AdminExportCustomersController` rendert wahrscheinlich eine sehr einfache Ansicht, möglicherweise nur eine Schaltfläche oder eine Nachricht, direkt in seiner `renderForm()`- oder `initContent()`-Methode, oder er löst direkt einen Dateidownload aus, ohne ein komplexes Template zu rendern.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es liest Daten aus bestehenden PrestaShop-Tabellen, hauptsächlich `ps_customer` und `ps_address`.

  - `ps_configuration`: Das Modul speichert seine internen Konfigurationseinstellungen (`mypresta_updates`, `update_`, `updatev_`) in der Tabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert keine Front-Office-Hooks. Seine Funktionalität ist vollständig auf das Back Office beschränkt.
  Es verwendet wahrscheinlich den Hook `actionAdminControllerSetMedia` (implizit oder explizit) für seinen Admin-Controller und möglicherweise `displayAdminProductsExtra` oder ähnliches für seinen Back-Office-Menüpunkt.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller initialisiert wird. | Wird von `ModuleAdminController` verwendet, um CSS/JS-Assets hinzuzufügen (obwohl dieses Modul keine hat). |
| `displayAdminAdvancedParameters` | Rendert Inhalte im Abschnitt „Erweiterte Einstellungen“ des Back Office. | Wird wahrscheinlich verwendet, um den Link/Einstiegspunkt des Moduls zum Menü „Erweiterte Einstellungen“ hinzuzufügen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „Kunden mit Adresse exportieren“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Modulfunktionalität und Kompatibilität zur Verfügung.
