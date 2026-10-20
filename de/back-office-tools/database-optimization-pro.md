---
title: "Database Optimization Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Database Optimization Pro von MyPresta.eu."
sidebar:
  label: "Database Optimization Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Database Optimization Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/database-optimization-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/database-optimization-pro/)
>
> ---


# Database Optimization Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Der Zugriff auf Ihr Hosting-Kontrollpanel (cPanel, Plesk usw.) zum Einrichten von Cron-Jobs wird für die vollständigen Automatisierungsfunktionen des Moduls dringend empfohlen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für Database Optimization Pro. Hier richten Sie die automatische Bereinigung ein und erhalten die notwendigen Informationen für Ihren Cron-Job.

Die Konfigurationsseite ist übersichtlich und bietet die wesentlichen Tools zur Verwaltung Ihrer Datenbankoptimierung.

#### **Cron Job URL**

- **Was diese Einstellung bewirkt:** Dies ist die eindeutige Webadresse (URL), die, wenn sie aufgerufen wird, den Datenbankoptimierungsprozess auslöst. Sie ist so konzipiert, dass sie von einem automatisierten System (einem Cron-Job) und nicht von einem menschlichen Benutzer aufgerufen wird.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt über die Modulkonfiguration ändern. Sie wird automatisch vom Modul generiert.
- **Empfohlener Wert:** Kopieren Sie diese URL genau so, wie sie angezeigt wird. Sie benötigen sie, um Ihren Cron-Job auf Ihrem Hosting-Server einzurichten.
- **Händlerszenario / Beispiel:** Sie kopieren diese URL und fügen sie in die Cron-Job-Einrichtungsoberfläche Ihres Webhosts (z. B. cPanel, Plesk oder einen benutzerdefinierten Cron-Job-Manager) ein. Dies weist Ihren Server an: „Besuche alle X Stunden/Tage diese URL, um meine Datenbank zu bereinigen.“

#### **Optimierung jetzt ausführen**

- **Was diese Einstellung bewirkt:** Dies ist ein manueller Auslöser, um den Datenbankoptimierungsprozess sofort auszuführen. Er führt die gleichen Bereinigungsaktionen wie die Cron-Job-URL aus, jedoch auf Abruf.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Beim Klicken:* Das Modul beginnt sofort mit der Bereinigung Ihrer Datenbank. Sie sehen eine Bestätigungsnachricht, sobald der Vorgang abgeschlossen ist.
- **Empfohlener Wert:** Verwenden Sie diese Schaltfläche für erste Tests nach der Installation oder wenn Sie eine sofortige Bereinigung außerhalb Ihrer geplanten Cron-Jobs durchführen müssen.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten es in Aktion sehen, oder Sie haben viele Änderungen an Ihrem Shop vorgenommen (z. B. viele Produkte importiert) und möchten sofort aufräumen, ohne auf den nächsten geplanten Cron-Job zu warten.

#### **Einrichten des Cron-Jobs**

Dies ist der wichtigste Teil der Automatisierung Ihrer Datenbankoptimierung. Ein Cron-Job ist ein zeitbasierter Job-Scheduler in Unix-ähnlichen Betriebssystemen. Er ermöglicht es Ihnen, Befehle oder Skripte so zu planen, dass sie automatisch zu einer bestimmten Zeit oder in einem bestimmten Intervall ausgeführt werden.

**Schritte zum Einrichten eines Cron-Jobs (allgemeine Anleitung – spezifische Schritte können je nach Host variieren):**

1. **Melden Sie sich bei Ihrem Hosting-Kontrollpanel an:** Dies ist normalerweise cPanel, Plesk oder ein benutzerdefiniertes Kontrollpanel, das von Ihrem Host bereitgestellt wird.
2. **Suchen Sie nach „Cron-Jobs“ oder „Geplante Aufgaben“:** Suchen Sie nach einem Abschnitt, der sich auf Cron-Jobs bezieht, oft unter „Erweitert“ oder „Tools“.
3. **Fügen Sie einen neuen Cron-Job hinzu:**
   - Sie müssen in der Regel die Häufigkeit angeben (z. B. einmal täglich, einmal wöchentlich). Ein guter Ausgangspunkt ist einmal täglich oder alle paar Tage.
   - Sie müssen den „Befehl“ oder die „aufzurufende URL“ angeben. Hier fügen Sie die **Cron Job URL** ein, die Sie von der Konfigurationsseite des Moduls kopiert haben.
   - Das Befehlsformat sieht oft so aus:

     Terminalfenster

     ```
     wget -q -O /dev/null "IHRE\_CRON\_JOB\_URL\_HIER"
     ```

     Ersetzen Sie `"IHRE_CRON_JOB_URL_HIER"` durch die genaue URL aus dem Modul. Der `wget`-Befehl ruft die URL ab, und `-q -O /dev/null` stellt sicher, dass er leise ausgeführt wird, ohne die Ausgabe zu speichern, was ideal für Hintergrundaufgaben ist.
4. **Speichern Sie den Cron-Job:** Bestätigen Sie Ihre Einstellungen, um die geplante Aufgabe zu aktivieren.

**Beispiel für Cron-Job-Häufigkeiten:**

- **Einmal täglich (z. B. 3 Uhr morgens):**
  `0 3 * * * wget -q -O /dev/null "IHRE_CRON_JOB_URL_HIER"`
- **Einmal wöchentlich (z. B. jeden Sonntag um 4 Uhr morgens):**
  `0 4 * * 0 wget -q -O /dev/null "IHRE_CRON_JOB_URL_HIER"`

Wählen Sie eine Zeit, in der Ihr Shop typischerweise wenig Traffic hat, um mögliche (wenn auch meist vernachlässigbare) Auswirkungen auf die Leistung während der Bereinigung zu minimieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Cron Job URL | (Automatisch generiert) | Die URL, die vom Cron-Job-System Ihres Hostings aufgerufen werden muss, um die automatische Datenbankoptimierung auszulösen. Kopieren Sie diese genau. |
| Modulkonfiguration | Optimierung jetzt ausführen | Klicken zum Ausführen | Löst manuell eine sofortige Datenbankbereinigung aus. Nützlich zum Testen oder für die bedarfsgesteuerte Optimierung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe den Cron-Job eingerichtet, sehe aber keinen Unterschied in der Geschwindigkeit meines Shops.**
A: Die Datenbankoptimierung bietet inkrementelle Verbesserungen. Wenn Ihr Shop bereits relativ schnell war, ist die Änderung möglicherweise nicht dramatisch.
- **Überprüfen Sie Ihren Cron-Job:** Stellen Sie sicher, dass er auf Ihrem Host korrekt konfiguriert ist und läuft. Einige Hosts stellen Protokolle für die Cron-Job-Ausführung bereit.
- **Manuell ausführen:** Klicken Sie in der Modulkonfiguration auf „Optimierung jetzt ausführen“. Wenn dies funktioniert, liegt das Problem wahrscheinlich bei Ihrer Cron-Job-Einrichtung.
- **Smarty-Cache leeren:** Manchmal erfordern visuelle Änderungen oder Geschwindigkeitsverbesserungen das Leeren des PrestaShop-Caches. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“.

**F: Welche Daten bereinigt dieses Modul tatsächlich?**
A: Das Modul zielt auf verschiedene Arten von temporären und veralteten Daten ab, die sich in Ihrer Datenbank ansammeln, wie zum Beispiel:
- Alte Gast-Warenkörbe, die nie in Bestellungen umgewandelt wurden.
- Abgelaufene Sitzungen.
- Alte Protokolleinträge (Zugriffsprotokolle, Seiten-nicht-gefunden-Protokolle).
- Temporäre Dateien und Cache-Daten, die in der Datenbank gespeichert sind.
Es löscht KEINE Kundendaten, Bestellungen, Produkte oder andere wesentliche Shop-Informationen.

**F: Kann dieses Modul meinen Shop beschädigen?**
A: Dieses Modul ist so konzipiert, dass es nur nicht-essentielle, temporäre oder veraltete Daten sicher entfernt. Es berührt keine kritischen Shop-Daten wie Produkte, Bestellungen, Kunden oder Kategorien. Wie bei jedem Modul, das mit Ihrer Datenbank interagiert, wird jedoch immer empfohlen, ein aktuelles Backup zu haben, bevor Sie es installieren und konfigurieren.

**F: Mein Hosting-Anbieter unterstützt keine Cron-Jobs, oder ich habe Probleme bei der Einrichtung.**
A: Wenn Sie keinen Cron-Job einrichten können, können Sie das Modul weiterhin verwenden, indem Sie manuell auf die Schaltfläche „Optimierung jetzt ausführen“ auf der Konfigurationsseite des Moduls klicken, wann immer Sie der Meinung sind, dass Ihr Shop eine Bereinigung benötigt (z. B. einmal pro Woche oder einmal pro Monat). Obwohl nicht automatisch, bietet es dennoch die Vorteile der Datenbankoptimierung. Wenden Sie sich an den Support Ihres Hosting-Anbieters, um Hilfe bei der Einrichtung von Cron-Jobs zu erhalten; diese sind in der Regel sehr hilfreich bei dieser häufigen Aufgabe.

**F: Beeinflusst dieses Modul meine SEO?**
A: Indirekt ja. Schnellere Seitenladezeiten sind ein positiver Ranking-Faktor für Suchmaschinen wie Google. Durch die Verbesserung der Geschwindigkeit Ihrer Website trägt dieses Modul zu einer besseren Benutzererfahrung bei, was sich positiv auf Ihre SEO-Leistung auswirken kann.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Database Optimization Pro` ist ein leichtgewichtiges Verwaltungstool, das sich hauptsächlich auf die Datenbankwartung konzentriert. Seine Kernfunktionalität besteht in der Ausführung einer Reihe von SQL-Abfragen zur Bereinigung nicht-essentieller Daten. Der „Pro“-Aspekt führt einen automatisierten Mechanismus über einen Front-Office-Controller ein, der durch einen Cron-Job ausgelöst werden soll, um eine geplante, unbeaufsichtigte Optimierung zu ermöglichen. Es hält sich an die PrestaShop-Modulstruktur und verwendet eine Hauptmoduldatei für Installation/Konfiguration und einen dedizierten Front-Controller für die Cron-Ausführung.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/CronCleaner.php`
    - **Klassenname**: `DboptimizationproCronCleanerModuleFrontController`
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dies ist der kritische Controller für die Cron-Job-Funktionalität. Beim Zugriff führt er die Datenbankbereinigungslogik aus. Er ist so konzipiert, dass er extern aufgerufen wird (z. B. durch `wget` über einen Cron-Job) und keine sichtbare Seite für den Benutzer rendert. Er führt die eigentlichen Datenbankoptimierungsabfragen aus.
  - `controllers/front/index.php`
    - **Klassenname**: (Keine Klasse, typischerweise eine leere Datei oder eine Weiterleitung)
    - **Verantwortlichkeit**: Diese Datei ist oft in PrestaShop-Modulen enthalten, um die Verzeichnisauflistung zu verhindern, wenn man `yourstore.com/modules/dboptimizationpro/controllers/front/` durchsucht. Sie enthält typischerweise ein einfaches `header('Location: ../../../index.php'); exit;` oder Ähnliches, um zur Startseite umzuleiten und die Sicherheit zu gewährleisten.
- **Back-Office-Admin-Controller**:

  - Es sind keine dedizierten Admin-Controller vorhanden. Die gesamte Back-Office-Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Die Logik des Moduls ist in der Hauptmoduldatei (`dboptimizationpro/cronjob.php`) und dem `CronCleaner`-Front-Controller gekapselt. Datenbankinteraktionen sind wahrscheinlich direkte SQL-Abfragen, die über `Db::getInstance()->execute()` ausgeführt werden.

### 4.4 JavaScript-Assets (`views/js/`)

Es sind keine benutzerdefinierten JavaScript-Dateien im Modularchiv enthalten. Die Funktionalität des Moduls ist serverseitig.

### 4.5 CSS-Stylesheets (`views/css/`)

Es sind keine benutzerdefinierten CSS-Dateien im Modularchiv enthalten. Die Konfigurationsseite des Moduls verwendet das Standard-PrestaShop-Back-Office-Styling.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Es sind keine benutzerdefinierten Smarty-Template-Dateien (`.tpl`) im Modularchiv enthalten. Das Konfigurationsformular des Moduls wird direkt in der `getContent()`-Methode der Hauptmoduldatei mit PrestaShops Helper-Formularen oder reinem HTML gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es interagiert mit bestehenden PrestaShop-Tabellen, um veraltete Daten zu löschen (z. B. `ps_cart`, `ps_connections`, `ps_log`, `ps_guest`, `ps_pagenotfound`).
  - Konfigurationseinstellungen (wie die Cron-Job-URL oder ein Flag, das den letzten Lauf anzeigt) werden in der Tabelle `ps_configuration` gespeichert, typischerweise mit Schlüsseln, die mit `DBOPTIMIZATIONPRO_` beginnen.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine expliziten Front-Office-Hooks (z. B. `displayHeader`, `displayRightColumn`, `displayFooter`), um Inhalte anzuzeigen. Seine primäre Interaktion mit dem PrestaShop-Hook-System dient der Modulinstallation/-deinstallation und möglicherweise der Back-Office-Menüintegration (obwohl nicht explizit als Admin-Controller aufgeführt, erscheint das Modul selbst in der Modulliste).

  Die Kernfunktionalität des Moduls wird ausgelöst durch:

  - Zugriff auf die `getContent()`-Methode im Back Office für manuelle Konfiguration und Ausführung.
  - Zugriff auf den `CronCleaner`-Front-Controller über einen externen Cron-Job.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Database Optimization Pro“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
