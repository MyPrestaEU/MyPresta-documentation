---
title: "Bank of Finland – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bank of Finland – Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Bank of Finland – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bank of Finland - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/bank-of-finland-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/bank-of-finland-currency-exchange-rates/)
>
> ---


# Bank of Finland – Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich. Ihre Hosting-Umgebung muss auch CRON-Jobs für automatisierte Updates unterstützen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Einstellungen des Moduls zuzugreifen. Hier legen Sie fest, wie die Wechselkurse aktualisiert und angewendet werden.

#### **1. CRON-URL**

- **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Webadresse (URL), die, wenn sie aufgerufen wird, das Modul dazu veranlasst, die neuesten Wechselkurse von der Bank von Finnland abzurufen und in Ihrem PrestaShop-Shop zu aktualisieren.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert. Diese URL ist entscheidend für die Einrichtung einer automatisierten Aufgabe (CRON-Job) auf Ihrem Webserver.
- **Empfohlener Wert:** Kopieren Sie diese URL genau so, wie sie erscheint.
- **Händlerszenario / Beispiel:** Sie stellen diese URL Ihrem Hosting-Anbieter zur Verfügung oder verwenden sie in Ihrem Hosting-Kontrollpanel (z. B. cPanel, Plesk), um einen CRON-Job einzurichten. Dies stellt sicher, dass Ihre Wechselkurse automatisch aktualisiert werden, zum Beispiel einmal täglich, ohne dass Sie manuell etwas anklicken müssen.

#### **2. Anweisungen zur CRON-Job-Einrichtung**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält Anweisungen zur Einrichtung des CRON-Jobs unter Verwendung der oben angegebenen URL. Ein CRON-Job ist ein zeitbasierter Job-Scheduler in Unix-ähnlichen Computerbetriebssystemen. Er ermöglicht es Ihnen, Befehle oder Skripte so zu planen, dass sie automatisch in bestimmten Intervallen ausgeführt werden.
- **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Informationsabschnitt; Sie ändern hier nichts. Das korrekte Befolgen dieser Anweisungen stellt sicher, dass Ihre Wechselkurse automatisch aktualisiert werden.
- **Empfohlener Wert:** Lesen und befolgen Sie diese Anweisungen sorgfältig.
- **Händlerszenario / Beispiel:** Das Kontrollpanel Ihres Hosting-Anbieters (wie cPanel) verfügt über einen Abschnitt „Cron Jobs“ oder „Geplante Aufgaben“. Sie fügen typischerweise einen neuen Cron-Job hinzu, geben die Häufigkeit an (z. B. einmal täglich um 3 Uhr morgens) und fügen die CRON-URL in das Befehlsfeld ein, oft mit `wget -q -O /dev/null` vorangestellt.

#### **3. Marge (%)**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine prozentuale Marge zu den abgerufenen Wechselkursen hinzuzufügen. Wenn der offizielle Kurs beispielsweise 1 EUR = 1,10 USD beträgt und Sie eine Marge von 2 % festlegen, verwendet das Modul 1 EUR = 1,078 USD (1,10 * 0,98) oder 1 EUR = 1,122 USD (1,10 * 1,02), je nachdem, wie das Modul die Marge anwendet (normalerweise zum Schutz vor Schwankungen, sodass es den Fremdwährungspreis leicht erhöhen könnte).
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf 0 gesetzt:* Wechselkurse werden genau so aktualisiert, wie sie von der Bank von Finnland bereitgestellt werden.
  - *Wenn auf einen positiven Wert gesetzt (z. B. 2):* Das Modul passt den Wechselkurs um diesen Prozentsatz an. Dies kann helfen, Transaktionsgebühren, Währungsumrechnungskosten oder einfach einen kleinen Puffer gegen ungünstige Kursbewegungen abzudecken und sicherzustellen, dass Ihre Gewinnmargen erhalten bleiben.
- **Empfohlener Wert:** Beginnen Sie mit 0. Wenn Sie Probleme mit der Rentabilität aufgrund von Währungsschwankungen oder Umrechnungsgebühren haben, ziehen Sie eine kleine Marge wie 1-3 % in Betracht.
- **Händlerszenario / Beispiel:** Wenn Sie ein Produkt für 100 EUR verkaufen und der Wechselkurs 1 EUR = 1,10 USD beträgt, würde das Produkt 110 USD kosten. Wenn Sie eine Marge von 2 % festlegen, könnte das Modul den Kurs als 1 EUR = 1,078 USD berechnen, wodurch das Produkt 107,80 USD kostet. Dies gibt Ihnen einen kleinen Puffer.

#### **4. Letzte Aktualisierung**

- **Was diese Einstellung bewirkt:** Dies zeigt Datum und Uhrzeit an, wann die Wechselkurse zuletzt erfolgreich vom Modul aktualisiert wurden.
- **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Informationsfeld und kann nicht direkt geändert werden. Es dient als Überprüfung, ob Ihr CRON-Job korrekt funktioniert und das Modul aktiv Kurse aktualisiert.
- **Empfohlener Wert:** Dies sollte ein aktuelles Datum und eine aktuelle Uhrzeit anzeigen, idealerweise innerhalb der letzten 24 Stunden, wenn Ihr CRON-Job täglich ausgeführt wird.
- **Händlerszenario / Beispiel:** Wenn Sie Ihren CRON-Job so einstellen, dass er täglich um 3 Uhr morgens ausgeführt wird, sollten Sie sehen, dass sich der Zeitstempel „Letzte Aktualisierung“ jeden Morgen auf 3 Uhr morgens (oder kurz danach) des aktuellen Tages ändert. Wenn er sich nicht aktualisiert, deutet dies auf ein Problem mit Ihrer CRON-Job-Einrichtung hin.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | CRON-URL | Genau kopieren | Eindeutige URL zum Auslösen von Kursaktualisierungen über CRON-Job. |
| Modulkonfiguration | Anweisungen zur CRON-Job-Einrichtung | Sorgfältig lesen | Anleitung zur Einrichtung automatischer Updates auf Ihrem Server. |
| Modulkonfiguration | Marge (%) | 0 (oder 1-3 % bei Bedarf) | Fügt einen prozentualen Puffer zu den Wechselkursen hinzu, um Gewinnmargen zu schützen. |
| Modulkonfiguration | Letzte Aktualisierung | N/A (informativ) | Zeigt den Zeitstempel der letzten erfolgreichen Kursaktualisierung an. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht aktualisiert. Was soll ich tun?**
A1: Dies hängt fast immer mit der CRON-Job-Einrichtung zusammen.
1. **Überprüfen Sie den Zeitstempel „Letzte Aktualisierung“:** Gehen Sie zur Modulkonfigurationsseite. Wenn dieses Datum alt ist, läuft Ihr CRON-Job nicht.
2. **Überprüfen Sie die CRON-Job-Einrichtung:** Melden Sie sich in Ihrem Hosting-Kontrollpanel (z. B. cPanel, Plesk) an. Navigieren Sie zum Abschnitt „Cron Jobs“ oder „Geplante Aufgaben“.
\* Stellen Sie sicher, dass die CRON-URL, die Sie vom Modul kopiert haben, genau der in Ihrem CRON-Job-Befehl entspricht.
\* Stellen Sie sicher, dass der Befehl korrekt formatiert ist (z. B. `wget -q -O /dev/null "IHRE_CRON_URL_HIER"`).
\* Bestätigen Sie, dass die Häufigkeit wie gewünscht eingestellt ist (z. B. täglich).
\* Überprüfen Sie die mit dem CRON-Job verknüpfte E-Mail-Adresse (falls vorhanden) auf Fehlermeldungen.
3. **Führen Sie die CRON-URL manuell aus:** Kopieren Sie die CRON-URL aus der Modulkonfiguration und fügen Sie sie direkt in die Adressleiste Ihres Webbrowsers ein. Dies sollte eine Aktualisierung auslösen. Wenn es funktioniert, liegt das Problem definitiv bei der CRON-Job-Konfiguration Ihres Servers. Wenn es nicht funktioniert, könnte ein serverseitiges Problem vorliegen, das das Modul am Abrufen von Daten hindert (z. B. Firewall, cURL nicht aktiviert).

**F2: Meine Preise in Fremdwährungen scheinen auch nach Updates leicht abzuweichen.**
A2: Überprüfen Sie die Einstellung „Marge (%)“ in der Modulkonfiguration. Wenn Sie eine Marge festgelegt haben (z. B. 2 %), passt das Modul den Wechselkurs absichtlich um diesen Prozentsatz an. Wenn Sie exakte offizielle Kurse wünschen, setzen Sie die Marge auf 0. Stellen Sie außerdem sicher, dass Ihre Basiswährung in PrestaShop (Lokalisierung > Währungen) korrekt auf EUR eingestellt ist, wenn Sie hauptsächlich mit Kursen der Bank von Finnland arbeiten.

**F3: Funktioniert dieses Modul mit allen Währungen?**
A3: Das Modul ruft offizielle Referenzdaten von der Bank von Finnland ab, die hauptsächlich Kurse gegenüber dem Euro bereitstellt. Es berechnet jedoch intelligent Cross-Rates für Nicht-Euro-Währungen. Das bedeutet, wenn die Bank von Finnland EUR zu USD und EUR zu GBP bereitstellt, kann das Modul den USD zu GBP-Kurs ableiten. Solange die Bank von Finnland einen Kurs für eine Währung gegenüber dem Euro bereitstellt, sollte das Modul in der Lage sein, diesen zu aktualisieren.

**F4: Muss ich meinen Smarty-Cache nach Updates leeren?**
A4: Nein, normalerweise nicht. Dieses Modul aktualisiert Datenbankwerte (Wechselkurse). Der Smarty-Cache von PrestaShop beeinflusst hauptsächlich die Template-Kompilierung und statische Inhalte. Wechselkursänderungen sind dynamisch und sollten sich sofort in der Preisgestaltung Ihres Shops widerspiegeln, ohne dass der Cache geleert werden muss.

**F5: Mein benutzerdefiniertes Theme zeigt die aktualisierten Preise nicht korrekt an.**
A5: Das Modul aktualisiert die zugrunde liegenden Wechselkurse in der PrestaShop-Datenbank. Der Währungswähler und die Preisdarstellungslogik Ihres Themes sollten diese aktualisierten Kurse automatisch übernehmen. Wenn nicht, handelt es sich wahrscheinlich um ein Theme-spezifisches Problem und nicht um ein Modulproblem.
1. **Überprüfen Sie die internen Kurse von PrestaShop:** Gehen Sie im Back Office zu **Lokalisierung > Währungen**. Überprüfen Sie die Spalte „Wechselkurs“ für Ihre Nicht-EUR-Währungen. Wenn diese Kurse korrekt aktualisiert werden, funktioniert das Modul.
2. **Kontaktieren Sie Ihren Theme-Entwickler:** Wenn die Kurse im Back Office korrekt sind, aber nicht im Frontend, hat Ihr Theme möglicherweise ein benutzerdefiniertes Caching oder eine spezifische Art der Währungsanzeige, die die Aufmerksamkeit des Theme-Entwicklers erfordert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Bank of Finland – Wechselkurse“ (`sprates`) ist ein leichtgewichtiges PrestaShop-Modul, das für eine einzige, kritische Aufgabe entwickelt wurde: die Automatisierung von Wechselkursaktualisierungen. Es nutzt einen Front-Office-Controller, um einen CRON-aufrufbaren Endpunkt bereitzustellen, der beim Zugriff XML-Daten von der Bank von Finnland abruft, diese parst und die Tabelle `ps_currency` aktualisiert. Das Modul folgt einem Standard-PrestaShop-MVC-Muster für seine Konfiguration und den Front-End-Trigger.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `sprates/controllers/front/cronjob.php`
  - **Klassenname & Elternklasse:** `SpratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der Kern-Controller für den automatisierten Aktualisierungsprozess. Er reagiert auf Anfragen an die CRON-URL. Bei Ausführung:
    1. Ruft XML-Daten vom offiziellen Wechselkurs-Feed der Bank von Finnland ab.
    2. Parst das XML, um EUR-basierte Wechselkurse zu extrahieren.
    3. Berechnet bei Bedarf Cross-Rates für Nicht-EUR-Währungen.
    4. Wendet die konfigurierte Marge an.
    5. Aktualisiert die Spalte `exchange_rate` in der Tabelle `ps_currency` für alle aktiven Währungen in PrestaShop.
    6. Aktualisiert den Zeitstempel `last_update` in der Konfiguration des Moduls.
    7. Gibt eine einfache Erfolgs- oder Fehlermeldung aus (oft unterdrückt durch `wget -q -O /dev/null`).
- `sprates/controllers/front/index.php`
  - **Klassenname & Elternklasse:** `SpratesIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist ein Platzhalter-Controller, der typischerweise verwendet wird, um die Verzeichnisauflistung zu verhindern oder eine Standardaktion bereitzustellen, wenn der Hauptmodul-Dispatch nicht verwendet wird. Im Kontext dieses Moduls dient er wahrscheinlich als Fallback oder als Standard-PrestaShop-Praxis für Module mit Front-Controllern, aber die primäre Logik befindet sich in `cronjob.php`.

#### Back-Office-Admin-Controller

Dieses Modul verwendet keine dedizierten benutzerdefinierten Admin-Controller. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/`. Es interagiert direkt mit den PrestaShop-Kernklassen `Currency` und `Configuration`, um Wechselkurse und Moduleinstellungen zu verwalten.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `sprates/views/admin.tpl`
    - **Zweck:** Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es zeigt die CRON-URL, die Einrichtungsanweisungen, das Margen-Eingabefeld und den Zeitstempel der letzten Aktualisierung an. Es verwendet Standard-PrestaShop-Helfer-Formularelemente.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es interagiert mit bestehenden PrestaShop-Tabellen:

- `ps_currency`: Aktualisiert die Spalte `exchange_rate` für aktive Währungen.
- `ps_configuration`: Speichert modulspezifische Einstellungen wie `SP_RATES_MARGIN` (für den Margenprozentsatz) und `SP_RATES_LAST_UPDATE` (für den Zeitstempel der letzten Aktualisierung).

#### Registrierte Hooks-Tabelle

Dieses Modul registriert keine traditionellen Anzeige-Hooks (z. B. `displayHeader`, `displayFooter`), da es keine visuellen Front-Office-Komponenten hat. Sein primärer „Hook“-Mechanismus ist der CRON-Job, der seinen Front-Controller auslöst.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionModuleInstall` | Während der Modulinstallation | Setzt Standardkonfigurationswerte. |
| `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationswerte. |
| (CRON-Job über Front-Controller) | Vom Server geplant (z. B. täglich) | Ruft Währungsumrechnungskurse ab, berechnet und aktualisiert sie. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bank of Finland – Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.
