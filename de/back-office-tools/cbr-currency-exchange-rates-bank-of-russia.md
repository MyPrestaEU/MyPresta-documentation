---
title: "CBR Währungsumtausch & Kurse (Bank von Russland) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul CBR Währungsumtausch & Kurse (Bank von Russland) von MyPresta.eu."
sidebar:
  label: "CBR Währungsumtausch & Kurse (Bank von Russland) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul CBR Currency Exchange & Rates (Bank of Russia) auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/cbr-currency-exchange-rates-bank-of-russia.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/cbr-currency-exchange-rates-bank-of-russia/)
>
> ---


# CBR Währungsumtausch & Kurse (Bank von Russland)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die externe API-Kommunikation erforderlich, die auf den meisten Webhosting-Umgebungen üblich sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls klicken Sie auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen. Dies ist der Hauptbildschirm, auf dem Sie alle Aspekte des Moduls „CBR Währungsumtausch & Kurse“ verwalten.

#### **Allgemeine Einstellungen**

- **Automatische Updates aktivieren:**

  - **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Modul automatisch nach neuen Wechselkursen der Zentralbank von Russland sucht und diese anwendet.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul ruft regelmäßig die neuesten Wechselkurse von der CBR-Website ab. Dies ist entscheidend, um Ihre RUB-Preise ohne manuelles Eingreifen genau zu halten. Sie müssen einen CRON-Job einrichten (unten erklärt), damit dies funktioniert.
    - *Wenn deaktiviert (NEIN):* Das Modul aktualisiert die Kurse nicht automatisch. Sie müssten die Kurse manuell aktualisieren, wenn diese Option deaktiviert ist, was den Zweck des Moduls zunichtemacht.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Preise in RUB immer den aktuellen offiziellen Wechselkurs widerspiegeln, ohne sich täglich anmelden und diese aktualisieren zu müssen. Die Aktivierung stellt sicher, dass Ihr Shop immer auf dem neuesten Stand ist.
- **Update-Frequenz (in Stunden):**

  - **Was diese Einstellung bewirkt:** Definiert, wie oft das Modul versuchen soll, neue Wechselkurse von der CBR abzurufen.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Einstellung einer niedrigeren Zahl (z.B. 1 Stunde):* Die Kurse werden häufiger überprüft und aktualisiert. Dies ist ideal, wenn Ihr Geschäft sehr präzise, nahezu Echtzeit-Umrechnungen erfordert.
    - *Einstellung einer höheren Zahl (z.B. 24 Stunden):* Die Kurse werden seltener überprüft. Dies könnte geeignet sein, wenn Ihre Preise nicht dramatisch schwanken oder wenn Sie die Serverlast durch häufige externe Aufrufe reduzieren möchten.
  - **Empfohlener Wert:** 24 (Tägliche Updates sind in der Regel ausreichend, da sich die CBR-Kurse einmal täglich ändern).
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihre RUB-Preise täglich aktualisiert werden, daher stellen Sie dies auf 24 Stunden ein. Wenn Sie hochwertige Artikel mit geringen Margen verkaufen, könnten Sie es auf 12 Stunden einstellen, um Änderungen am Mittag zu erfassen, falls die CBR diese veröffentlicht (obwohl es typischerweise einmal täglich ist).
- **Marge auf Wechselkurs (%):**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, eine prozentuale Marge zusätzlich zum offiziellen CBR-Wechselkurs hinzuzufügen. Dies kann verwendet werden, um Transaktionsgebühren, Währungsumrechnungskosten oder eine leichte Anpassung Ihrer Preisstrategie abzudecken.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Einstellung eines positiven Werts (z.B. 2):* Das Modul erhöht den berechneten Wechselkurs um 2%. Dies bedeutet, dass Sie für jede Einheit Ihrer Basiswährung etwas mehr RUB erhalten, wodurch Ihre RUB-Preise effektiv steigen.
    - *Einstellung 0 oder leer lassen:* Das Modul verwendet den exakten offiziellen CBR-Wechselkurs ohne Anpassung.
    - *Einstellung eines negativen Werts (z.B. -1):* Das Modul verringert den berechneten Wechselkurs um 1%. Dies bedeutet, dass Sie für jede Einheit Ihrer Basiswährung etwas weniger RUB erhalten, wodurch Ihre RUB-Preise effektiv sinken.
  - **Empfohlener Wert:** 0 (Es sei denn, Sie haben spezifische geschäftliche Gründe, eine Marge hinzuzufügen).
  - **Händlerszenario / Beispiel:** Ihr Zahlungs-Gateway berechnet eine Gebühr von 1,5% für die Umrechnung von RUB in Ihre Basiswährung. Sie können hier eine Marge von 1,5% einstellen, um diese Kosten auszugleichen und Ihre Gewinnmargen zu erhalten.
- **CRON-Job-URL:**

  - **Was diese Einstellung bewirkt:** Dies zeigt die eindeutige URL an, die Sie als CRON-Job auf Ihrem Hosting-Server einrichten müssen. Wenn diese URL aufgerufen wird, löst sie das Modul aus, um die Wechselkurse abzurufen und zu aktualisieren.
  - **Auswirkungen der Änderung dieser Einstellung:** Dies ist keine Einstellung, die Sie ändern, sondern eine URL, die Sie *verwenden*.
    - *Wenn korrekt als CRON-Job konfiguriert:* Das Modul läuft automatisch im Hintergrund mit Ihrer angegebenen Frequenz (basierend auf der Einstellung „Update-Frequenz“), um die Kurse zu aktualisieren.
    - *Wenn nicht als CRON-Job konfiguriert:* Automatische Updates finden nicht statt, selbst wenn „Automatische Updates aktivieren“ auf JA eingestellt ist.
  - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als CRON-Job auf Ihrem Server ein.
  - **Händlerszenario / Beispiel:** Nach der Konfiguration des Moduls kopieren Sie diese URL und fügen sie dem CRON-Job-Scheduler Ihres Hosting-Kontrollpanels hinzu, um sie täglich um 3 Uhr morgens auszuführen, um sicherzustellen, dass die Kurse vor Beginn Ihres Geschäftstages aktualisiert werden.

#### **Währungseinstellungen**

- **Zu aktualisierende Währung:**
  - **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü ermöglicht es Ihnen, auszuwählen, welche spezifische Währung in Ihrem PrestaShop-Shop mit CBR-Kursen aktualisiert werden soll. Es listet alle Währungen auf, die Sie in Ihrem PrestaShop Back Office aktiviert haben.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Auswahl von „Russischer Rubel (RUB)“:* Das Modul zielt speziell auf den Russischen Rubel ab und aktualisiert dessen Wechselkurs gegenüber der Basiswährung Ihres Shops mithilfe von CBR-Daten.
    - *Auswahl einer anderen Währung:* Dieses Modul ist speziell für CBR-Kurse konzipiert, die für den Russischen Rubel gelten. Die Auswahl einer anderen Währung könnte zu unerwartetem Verhalten oder keinen Updates für diese Währung führen.
  - **Empfohlener Wert:** Russischer Rubel (RUB)
  - **Händlerszenario / Beispiel:** Die Basiswährung Ihres Shops ist EUR, und Sie möchten sicherstellen, dass, wenn Kunden RUB auswählen, die Umrechnung von EUR nach RUB auf Basis der CBR-Kurse genau ist. Sie wählen hier „Russischer Rubel (RUB)“ aus.

#### **Speichern-Schaltfläche**

- **Speichern:**
  - **Was dies bewirkt:** Wendet alle Änderungen an, die Sie auf der Konfigurationsseite vorgenommen haben.
  - **Auswirkungen des Klickens:** Ihre Einstellungen werden in der Datenbank gespeichert, und das Modul arbeitet gemäß den neuen Parametern.
  - **Empfohlene Aktion:** Klicken Sie immer auf „Speichern“, nachdem Sie Änderungen vorgenommen haben.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Automatische Updates aktivieren | JA | Steuert das automatische Abrufen von CBR-Kursen. JA für automatische Updates. |
| Modulkonfiguration | Update-Frequenz (in Stunden) | 24 | Wie oft der CRON-Job Kurs-Updates auslösen soll. 24 für täglich. |
| Modulkonfiguration | Marge auf Wechselkurs (%) | 0 | Fügt einen Prozentsatz zum offiziellen Kurs hinzu. Verwenden Sie dies für Gebühren oder Preisstrategien. |
| Modulkonfiguration | CRON-Job-URL | (Eindeutige URL) | URL, die auf Ihrem Server für automatisierte Updates konfiguriert werden muss. |
| Modulkonfiguration | Zu aktualisierende Währung | Russischer Rubel (RUB) | Gibt an, welche PrestaShop-Währung mit CBR-Kursen aktualisiert werden soll. Muss RUB sein. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine RUB-Preise werden nicht automatisch aktualisiert. Was sollte ich überprüfen?**
A1:

- **Ist „Automatische Updates aktivieren“ auf JA eingestellt?** Überprüfen Sie die Modulkonfiguration.
- **Haben Sie den CRON-Job auf Ihrem Hosting-Server eingerichtet?** Dies ist der häufigste Grund. Kopieren Sie die „CRON-Job-URL“ aus der Modulkonfiguration und fügen Sie sie dem CRON-Scheduler Ihres Hosting-Panels hinzu. Stellen Sie sicher, dass sie mindestens so häufig ausgeführt wird wie Ihre Einstellung „Update-Frequenz“.
- **Ist die „Zu aktualisierende Währung“ auf „Russischer Rubel (RUB)“ eingestellt?** Das Modul ist für RUB konzipiert.
- **Überprüfen Sie die CRON-Job-Protokolle Ihres Servers (falls verfügbar):** Ihr Hosting-Anbieter bietet möglicherweise Protokolle an, die zeigen, ob der CRON-Job ausgeführt wird und ob Fehler aufgetreten sind.
- **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“, um sicherzustellen, dass Ihr Shop die neuesten Daten anzeigt.

**F2: Der Wechselkurs scheint falsch zu sein oder hat sich seit einiger Zeit nicht geändert.**
A2:

- **Überprüfen Sie den offiziellen CBR-Kurs:** Überprüfen Sie die offizielle Website der Zentralbank von Russland für den heutigen Wechselkurs, um zu bestätigen, wie er sein sollte.
- **Überprüfen Sie Ihre „Update-Frequenz“:** Wenn sie auf 24 Stunden eingestellt ist, wird sie nur einmal täglich aktualisiert.
- **Bankfeiertage:** Die CBR aktualisiert die Kurse an Bankfeiertagen nicht. Das Modul verwendet intelligent den zuletzt verfügbaren Kurs. Wenn es eine lange Feiertagsperiode gibt, kann der Kurs mehrere Tage lang statisch bleiben.
- **CRON-Job-Probleme:** Siehe F1 zur Fehlerbehebung bei CRON-Jobs.

**F3: Kann ich dieses Modul auch für andere Währungen außer RUB verwenden?**
A3: Nein, dieses Modul ist speziell für die Integration mit den Wechselkursdaten der Zentralbank von Russland konzipiert, die hauptsächlich für den Russischen Rubel gelten. Es wird nur die RUB-Währung in Ihrem Shop genau aktualisieren.

**F4: Ich habe mein Theme geändert, und jetzt sehen die Preise in RUB seltsam aus.**
A4: Dieses Modul verarbeitet nur den *Wert* der Währungsumrechnung. Die *Anzeige* der Preise (Schriftarten, Farben, Layout) wird von Ihrem PrestaShop-Theme übernommen. Wenn die Preise nach einem Theme-Wechsel seltsam aussehen, handelt es sich wahrscheinlich um ein CSS- oder Template-Problem mit Ihrem neuen Theme, nicht um das Modul selbst. Möglicherweise müssen Sie das Styling Ihres Themes anpassen.

**F5: Wie aktualisiere ich die Kurse bei Bedarf manuell?**
A5: Obwohl das Modul für automatische Updates konzipiert ist, können Sie ein Update erzwingen, indem Sie die CRON-Job-URL manuell in Ihrem Webbrowser aufrufen. Dies löst den Update-Prozess einmal aus. Denken Sie daran, danach Ihren PrestaShop-Cache zu leeren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „CBR Währungsumtausch & Kurse“ arbeiten.

### 4.1 Architekturübersicht

Das Modul `cbrrates` folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und Konfiguration nutzt. Es verwendet Front-Controller für die Ausführung von CRON-Jobs und eine einfache `getContent()`-Methode für die Back-Office-Konfiguration. Das Modul ruft XML-Daten von der CBR-API ab, parst sie und aktualisiert die Wechselkurse der PrestaShop-`Currency`.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `CbrratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist dafür konzipiert, von einem externen CRON-Job aufgerufen zu werden. Beim Zugriff initiiert er den Währungskurs-Update-Prozess. Er überprüft die Konfigurationswerte `update_` und `updatev_`, um festzustellen, ob ein Update basierend auf der konfigurierten Frequenz fällig ist. Anschließend ruft er die Logik des Hauptmoduls auf, um die neuesten CBR-Kurse abzurufen und anzuwenden. Er gibt eine einfache Erfolgs- oder Fehlermeldung aus.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `CbrratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist ein Platzhalter oder Standard-Front-Controller. In vielen Modulen, wenn keine spezifische Aktion definiert ist, könnte `index.php` als Fallback dienen oder einfach weiterleiten. Für `cbrrates` ist seine primäre Funktion wahrscheinlich minimal, da die Kern-Front-Office-Interaktion über `cronjob.php` erfolgt. Es könnte vorhanden sein, um sicherzustellen, dass eine gültige Front-Office-Route für das Modul existiert, auch wenn sie nicht aktiv zur Anzeige verwendet wird.
- **Back-Office-Admin-Controller**:

  - In diesem Modul sind keine dedizierten Admin-Controller vorhanden. Die gesamte Back-Office-Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Die gesamte Kernlogik befindet sich in der Hauptdatei `cbrrates.php`.

### 4.4 JavaScript-Assets (`views/js/`)

In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien vorhanden.

### 4.5 CSS-Stylesheets (`views/css/`)

In diesem Modul sind keine benutzerdefinierten CSS-Dateien vorhanden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `cbrrates/views/admin.tpl`
    - **Zweck**: Dieses Template wird von der `getContent()`-Methode in `cbrrates.php` gerendert, um das Konfigurationsformular des Moduls im PrestaShop Back Office anzuzeigen.
    - **Inhalt**: Es enthält typischerweise die HTML-Struktur für die Eingabefelder, Schalter und Schaltflächen für Einstellungen wie `mypresta_updates`, `update_`, `updatev_`, `currency_` und die Anzeige der CRON-Job-URL. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` (oder `_configuration` je nach Präfix).
    - `PS_CBRRATES_UPDATE_ENABLED`: Boolean (0/1) für „Automatische Updates aktivieren“.
    - `PS_CBRRATES_UPDATE_FREQUENCY`: Integer für „Update-Frequenz (in Stunden)“.
    - `PS_CBRRATES_MARGIN`: Float für „Marge auf Wechselkurs (%)“.
    - `PS_CBRRATES_CURRENCY_ID`: Integer, ID der zu aktualisierenden PrestaShop-Währung (z.B. ID für RUB).
    - `PS_CBRRATES_LAST_UPDATE`: Zeitstempel des letzten erfolgreichen Updates.
    - `PS_CBRRATES_CRON_TOKEN`: Ein eindeutiger String, der in der CRON-Job-URL zur Sicherheit verwendet wird.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine Hooks explizit für die Front-Office-Anzeige (z.B. `displayHeader`, `displayFooter`). Seine primäre Interaktion mit dem PrestaShop-Kern erfolgt über den Hook `actionUpdateCurrency` (implizit, durch Aktualisierung der Wechselkurse) und seinen eigenen internen CRON-Mechanismus.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionUpdateCurrency` | Wird ausgelöst, wenn eine Währung aktualisiert wird (implizit durch dieses Modul) | Nicht explizit vom Modul registriert, aber die Kernfunktion des Moduls ist die Aktualisierung von Wechselkursen, was diesen PrestaShop-Kern-Hook auslösen könnte. |
| (Interner CRON) | Über `controllers/front/cronjob.php` | Löst das Abrufen und Aktualisieren von CBR-Wechselkursen basierend auf der konfigurierten Frequenz aus. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „CBR Währungsumtausch & Kurse (Bank von Russland)“ verweisen wir Sie auf Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
