---
title: "Bank of Canada - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Bank of Canada - Wechselkurse' von MyPresta.eu."
sidebar:
  label: "Bank of Canada - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bank of Canada - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/bank-of-canada-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/bank-of-canada-currency-exchange-rates/)
>
> ---


# Bank of Canada - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Einstellungen des Moduls zuzugreifen. Dies ist der Hauptbildschirm, auf dem Sie verwalten, wie Wechselkurse aktualisiert werden.

#### **1. Wechselkurse manuell aktualisieren**

- **Was diese Einstellung bewirkt:** Dies ist eine Schaltfläche, die, wenn sie angeklickt wird, das Modul sofort dazu veranlasst, die neuesten Wechselkurse von der Bank of Canada abzurufen und in Ihrem Shop zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beim Klicken:* Das Modul verbindet sich mit der Bank of Canada, ruft die aktuellsten Kurse ab, berechnet Kreuzkurse und wendet sie auf die Währungen Ihres Shops an. Eine Bestätigungsmeldung wird normalerweise angezeigt.
- **Empfohlener Wert:** Verwenden Sie diese Schaltfläche für sofortige Updates oder zum Testen des Moduls nach der Ersteinrichtung. Für laufende Updates wird der CRON-Job (unten erklärt) empfohlen.
- **Händlerszenario / Beispiel:** Sie haben gerade ein neues Produkt eingeführt und möchten sicherstellen, dass alle internationalen Preise absolut aktuell sind, bevor Sie eine große Marketingkampagne starten. Klicken Sie auf diese Schaltfläche, um eine sofortige Aktualisierung zu erzwingen.

#### **2. CRON-Job-URL**

- **Was diese Einstellung bewirkt:** Dieses Feld zeigt eine eindeutige URL an, die, wenn sie aufgerufen wird, das Modul dazu veranlasst, Wechselkurse automatisch zu aktualisieren. Diese URL ist für die Verwendung mit einem „CRON-Job“ auf Ihrem Webserver konzipiert.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn die URL aufgerufen wird (durch einen CRON-Job):* Das Modul führt den gleichen Kursaktualisierungsprozess durch wie das Klicken auf die manuelle Aktualisierungsschaltfläche, jedoch automatisch in geplanten Intervallen.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als CRON-Job auf Ihrem Hosting-Server ein.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse jeden Tag um 3 Uhr morgens aktualisiert werden. Sie kopieren diese URL und konfigurieren Ihr Hosting-Panel (cPanel, Plesk usw.), um diese URL täglich um 3 Uhr morgens aufzurufen. Dies stellt sicher, dass Ihre Kurse immer aktuell sind, ohne dass Sie einen Finger rühren müssen.

#### **3. Wechselkursmarge (%)**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, einen prozentualen Aufschlag zu den von der Bank of Canada abgerufenen Wechselkursen hinzuzufügen. Wenn der BOC-Kurs beispielsweise 1,20 beträgt und Sie eine Marge von 2 % festlegen, verwendet Ihr Shop einen Kurs von 1,224 (1,20 * 1,02).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein positiver Wert festgelegt wird (z. B. 2):* Alle umgerechneten Preise in Ihrem Shop werden leicht höher sein, was den hinzugefügten Aufschlag widerspiegelt. Dies kann helfen, Transaktionsgebühren, Währungsumrechnungskosten zu decken oder einfach Ihre Gewinnmarge bei internationalen Verkäufen zu erhöhen.
  - *Wenn auf 0 gesetzt (oder leer gelassen):* Das Modul verwendet die genauen Wechselkurse der Bank of Canada ohne zusätzlichen Aufschlag.
- **Empfohlener Wert:** Beginnen Sie mit 0 % und passen Sie ihn an Ihre Geschäftsanforderungen, Zahlungs-Gateway-Gebühren und gewünschten Gewinnmargen an. Eine gängige Praxis ist 1-3 %, um potenzielle Kosten zu decken.
- **Händlerszenario / Beispiel:** Ihr Zahlungs-Gateway berechnet eine Gebühr von 1,5 % für internationale Währungsumrechnungen. Sie stellen die „Wechselkursmarge“ auf 1,5 % ein, um sicherzustellen, dass diese Kosten in Ihrer Produktpreisgestaltung abgedeckt sind, anstatt Ihren Gewinn zu schmälern.

#### **4. Letzte Aktualisierung**

- **Was diese Einstellung bewirkt:** Dieses Feld zeigt Datum und Uhrzeit der letzten erfolgreichen Wechselkursaktualisierung durch das Modul an.
- **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld und kann nicht geändert werden. Es dient als Informationsindikator.
- **Empfohlener Wert:** Überwachen Sie dieses Feld, um sicherzustellen, dass Ihr CRON-Job korrekt ausgeführt wird und die Kurse regelmäßig aktualisiert werden.
- **Händlerszenario / Beispiel:** Sie bemerken, dass Ihre internationalen Preise veraltet erscheinen. Sie überprüfen „Letzte Aktualisierung“ und sehen, dass es seit einer Woche nicht aktualisiert wurde, was auf ein potenzielles Problem mit Ihrer CRON-Job-Einrichtung hindeutet.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Wechselkurse manuell aktualisieren (Schaltfläche) | Klicken zum Aktualisieren | Erzwingt eine sofortige Aktualisierung aller Wechselkurse von der BOC. |
| Modulkonfiguration | CRON-Job-URL | Kopieren & auf dem Server konfigurieren | Bietet eine URL für automatisierte, geplante Updates über den CRON-Dienst Ihres Hostings. |
| Modulkonfiguration | Wechselkursmarge (%) | 0% | Fügt einen prozentualen Aufschlag zu den abgerufenen Wechselkursen hinzu, der alle umgerechneten Preise beeinflusst. |
| Modulkonfiguration | Letzte Aktualisierung | Schreibgeschützt | Zeigt den Zeitstempel der letzten erfolgreichen Wechselkursaktualisierung an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht automatisch aktualisiert. Was soll ich tun?**
A1: Dies ist fast immer ein CRON-Job-Problem.
- **Überprüfen Sie Ihr Hosting-Panel:** Melden Sie sich bei Ihrem Hosting-Konto (cPanel, Plesk usw.) an und überprüfen Sie, ob der CRON-Job mit der exakten vom Modul bereitgestellten URL korrekt eingerichtet ist. Stellen Sie sicher, dass die Häufigkeit korrekt ist (z. B. täglich).
- **Überprüfen Sie den CRON-Befehl:** Der Befehl sieht normalerweise so aus: `wget -O /dev/null "IHRE_CRON_URL_HIER"` oder `curl "IHRE_CRON_URL_HIER"`. Stellen Sie sicher, dass keine Tippfehler vorhanden sind.
- **Überprüfen Sie „Letzte Aktualisierung“ im Modul:** Wenn dieses Datum alt ist, bestätigt dies, dass der CRON nicht läuft.
- **Führen Sie die CRON-URL manuell aus:** Kopieren Sie die CRON-URL aus der Modulkonfiguration und fügen Sie sie in Ihren Browser ein. Wenn sie aktualisiert wird, ist die URL selbst in Ordnung, und das Problem liegt ausschließlich bei der CRON-Einrichtung Ihres Hostings.

**F2: Die Preise in anderen Währungen scheinen im Vergleich zur Standardwährung zu hoch/niedrig zu sein.**
A2:
- **Überprüfen Sie Ihre „Wechselkursmarge (%)“:** Wenn diese zu hoch eingestellt ist, werden die Preise überhöht. Wenn sie negativ ist (obwohl nicht empfohlen), wären die Preise niedriger.
- **Überprüfen Sie Ihre Standardwährung:** Stellen Sie sicher, dass die Standardwährung Ihres PrestaShop-Shops (Lokalisierung > Währungen) korrekt auf Ihre primäre Betriebswährung eingestellt ist (z. B. CAD, wenn Sie von der Bank of Canada abrufen). Das Modul berechnet die Kurse relativ zu Ihrer Standardwährung.
- **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal können alte Preise zwischengespeichert sein.

**F3: Das Modul meldet „Letzte Aktualisierung“ war erfolgreich, aber ich sehe keine Änderungen im Front Office.**
A3:
- **PrestaShop-Cache leeren:** Dies ist der häufigste Grund. Leeren Sie immer Ihren Cache nach jeder größeren Datenaktualisierung in PrestaShop.
- **Browser-Cache überprüfen:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder Ihren Shop in einem Inkognito-/privaten Fenster anzuzeigen, um lokale Caching-Probleme auszuschließen.
- **Währungsauswahl überprüfen:** Stellen Sie sicher, dass Sie den Shop tatsächlich in der Nicht-Standardwährung anzeigen, in der Sie die umgerechneten Preise erwarten.

**F4: Funktioniert dieses Modul mit benutzerdefinierten Themes?**
A4: Ja, dieses Modul arbeitet im Hintergrund, indem es die Kern-PrestaShop-Wechselkurse aktualisiert. Es interagiert nicht direkt mit den visuellen Elementen Ihres Themes, daher sollte es mit jedem benutzerdefinierten Theme kompatibel sein. Der Währungswähler des Themes zeigt die Preise einfach basierend auf den vom Modul bereitgestellten Kursen an.

**F5: Kann ich dieses Modul verwenden, wenn meine Standardwährung nicht CAD ist?**
A5: Ja, das können Sie. Das Modul ruft Basiskurse von der Bank of Canada ab (z. B. USD zu CAD, EUR zu CAD). Es berechnet dann intelligent Kreuzkurse relativ zu *der Standardwährung Ihres Shops*. Wenn Ihre Standardwährung also EUR ist und die BOC USD/CAD bereitstellt, berechnet das Modul EUR/USD, EUR/CAD usw. basierend auf den verfügbaren Daten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bank of Canada - Wechselkurse“ (`bocrates`) ist als leichte, automatisierte Lösung für die Synchronisierung von Wechselkursen konzipiert. Es nutzt hauptsächlich PrestaShops Kern-`Currency` `ObjectModel`, um Wechselkurse zu aktualisieren. Das Modul verwendet einen Front-Controller für die CRON-Job-Ausführung, um sicherzustellen, dass die Kursaktualisierungen außerhalb des Standard-Back-Office-Kontexts erfolgen, was ideal für geplante Aufgaben ist. Es hält sich an die PrestaShop-Modularchitektur und verwendet `install()`- und `uninstall()`-Methoden für die Einrichtung und Bereinigung sowie `getContent()` für die Back-Office-Konfiguration.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `BocratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist der Einstiegspunkt für den automatisierten CRON-Job. Wenn er über seine eindeutige URL (in der Modulkonfiguration bereitgestellt) aufgerufen wird, löst er die Methode `processUpdateExchangeRates()` innerhalb der Hauptmodulklasse aus. Er ist dafür konzipiert, extern von einem serverseitigen CRON-Scheduler aufgerufen zu werden, nicht direkt von einem Benutzer. Er gibt typischerweise eine einfache Erfolgs- oder Fehlermeldung aus.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `BocratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist ein Platzhalter oder Standard-Front-Controller. In vielen Modulen, wenn eine bestimmte Aktion nicht definiert ist, könnte `index.php` verwendet werden. Für dieses Modul besteht seine Hauptfunktion wahrscheinlich darin, als Fallback zu dienen oder sicherzustellen, dass das Front-Office-Routing des Moduls korrekt eingerichtet ist, auch wenn es keine spezifische benutzerorientierte Aktion ausführt. Der `cronjob.php` ist der aktive Front-Controller für die Funktionalität.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Back-Office-Konfiguration wird direkt innerhalb der Methode `getContent()` der Hauptmoduldatei `bocrates.php` gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul interagiert direkt mit PrestaShops Kern-`Currency` `ObjectModel` und der `Configuration`-Klasse zur Datenspeicherung und -manipulation.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul verwendet kein benutzerdefiniertes JavaScript für seine Funktionalität.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul verwendet kein benutzerdefiniertes CSS für seine Funktionalität.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `bocrates/views/admin.tpl`
    - **Zweck**: Dieses Template wird von der Methode `getContent()` der Hauptmoduldatei `bocrates.php` gerendert. Es zeigt das Konfigurationsformular des Moduls im PrestaShop Back Office an. Dies umfasst die Schaltfläche für die manuelle Aktualisierung, die CRON-Job-URL, das Eingabefeld für die Wechselkursmarge und den Zeitstempel der letzten Aktualisierung.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie:
    - `BOCRATES_MARGIN`: Speichert die prozentuale Marge für Wechselkurse.
    - `BOCRATES_LAST_UPDATE`: Speichert den Zeitstempel der letzten erfolgreichen Aktualisierung.
    - `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Bezogen auf den Update-Mechanismus von MyPresta.eu.
- **Registrierte Hooks-Tabelle**:
  Das Modul arbeitet hauptsächlich im Hintergrund und registriert keine Hooks für die Front-Office-Anzeige. Seine Kernfunktionalität wird durch den `cronjob`-Front-Controller ausgelöst.

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionModuleInstall` | Während der Modulinstallation | Setzt Standardkonfigurationswerte und registriert notwendige Hooks (falls vorhanden). |
  | `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationswerte. |
  | `displayBackOfficeHeader` | Rendert im Back-Office-Header | Potenziell verwendet zum Einbinden von Assets oder Anzeigen von Hinweisen im Admin-Panel (obwohl keine spezifischen Assets aufgeführt sind). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und dedizierten technischen Support für das Modul „Bank of Canada - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
