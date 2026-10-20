---
title: "NBRB Wechselkurse & Währung (Nationalbank von Belarus) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul NBRB Wechselkurse & Währung (Nationalbank von Belarus) von MyPresta.eu."
sidebar:
  label: "NBRB Wechselkurse & Währung (Nationalbank von Belarus) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul NBRB Exchange Rates & Currency (National Bank of Belarus) auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/nbrb-exchange-rates-currency-national-bank-of-belarus.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/nbrb-exchange-rates-currency-national-bank-of-belarus/)
>
> ---


# NBRB Wechselkurse & Währung (Nationalbank von Belarus)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel erforderlich und auf den meisten modernen Hosting-Umgebungen vorhanden. Der Zugriff zum Einrichten eines CRON-Jobs ist für automatische Updates unerlässlich.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „NBRB Wechselkurse & Währung“, um auf dessen Einstellungen zuzugreifen.

#### **NBRB Wechselkurse aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul beginnt, NBRB-Wechselkurse für BYN-Währungsumrechnungen in Ihrem Shop abzurufen und anzuwenden.
  - *Wenn deaktiviert (NEIN):* Das Modul stoppt das Abrufen von Kursen, und Ihre BYN-Währungskurse werden auf die manuell im PrestaShop-Bereich „Währungen“ oder durch ein anderes aktives Währungsmodul eingestellten Werte zurückgesetzt.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Wenn Sie hauptsächlich nach Belarus verkaufen, aktivieren Sie dies, um sicherzustellen, dass alle BYN-Preise offiziell sind. Wenn Sie den Verkauf nach Belarus vorübergehend einstellen, können Sie es deaktivieren.

#### **CRON-Job-URL**

- **Was diese Einstellung bewirkt:** Dies zeigt die eindeutige URL an, die Sie als CRON-Job auf Ihrem Server einrichten müssen. Wenn diese URL aufgerufen wird, ruft das Modul automatisch die neuesten Wechselkurse von der NBRB ab.
- **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Sie kopieren diese URL und fügen sie in den CRON-Job-Scheduler Ihres Hosting-Kontrollpanels ein.
- **Empfohlener Wert:** Kopieren Sie diese URL genau wie angezeigt.
- **Händlerszenario / Beispiel:** Sie würden diese URL kopieren und einen CRON-Job einrichten, der beispielsweise einmal alle 24 Stunden (z. B. um 3 Uhr morgens Ortszeit) ausgeführt wird, um sicherzustellen, dass Ihre Kurse immer aktuell sind. Konsultieren Sie die Dokumentation oder den Support Ihres Hosting-Anbieters für die Einrichtung von CRON-Jobs.

#### **Margenanpassung (%)**

- **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, einen prozentualen Aufschlag (Aufschlag oder Abschlag) auf die abgerufenen NBRB-Wechselkurse anzuwenden. Dies ist nützlich, um Transaktionsgebühren zu decken, sich gegen geringfügige Schwankungen abzusichern oder einen leichten Rabatt/Aufschlag anzuwenden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Eingabe eines positiven Wertes (z. B. 2):* Der BYN-Umrechnungskurs wird um 2 % erhöht, wodurch Produkte in BYN effektiv etwas teurer werden.
  - *Eingabe eines negativen Wertes (z. B. -1):* Der BYN-Umrechnungskurs wird um 1 % gesenkt, wodurch Produkte in BYN etwas billiger werden.
  - *Bei 0 belassen:* Der offizielle NBRB-Kurs wird ohne Änderungen verwendet.
- **Empfohlener Wert:** 0 (es sei denn, Sie haben einen spezifischen geschäftlichen Grund, die Kurse anzupassen).
- **Händlerszenario / Beispiel:** Wenn Ihr Zahlungs-Gateway eine Gebühr von 1,5 % für BYN-Transaktionen erhebt, könnten Sie dies auf „1,5“ setzen, um diese Kosten in den Wechselkurs einzubeziehen.

#### **Letzte Aktualisierung**

- **Was diese Einstellung bewirkt:** Dieses Feld zeigt Datum und Uhrzeit an, wann die Wechselkurse zuletzt erfolgreich vom Modul aktualisiert wurden (entweder manuell oder über CRON-Job).
- **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Informationsfeld. Es hilft Ihnen zu überprüfen, ob Ihr CRON-Job korrekt ausgeführt wird und die Kurse aktualisiert werden.
- **Empfohlener Wert:** N/A (überwachen Sie dies, um regelmäßige Updates sicherzustellen).
- **Händlerszenario / Beispiel:** Wenn Sie feststellen, dass dieses Datum mehrere Tage alt ist, deutet dies auf ein Problem mit Ihrer CRON-Job-Einrichtung hin, und Sie sollten dies untersuchen.

#### **Schaltfläche „Kurse manuell aktualisieren“**

- **Was diese Einstellung bewirkt:** Diese Schaltfläche ermöglicht es Ihnen, eine sofortige Aktualisierung der Wechselkurse von der NBRB manuell auszulösen, außerhalb des CRON-Job-Zeitplans.
- **Auswirkung der Änderung dieser Einstellung:** Das Klicken auf diese Schaltfläche ruft sofort die neuesten Kurse ab und aktualisiert sie in Ihrem PrestaShop-Shop. Das Feld „Letzte Aktualisierung“ spiegelt die neue Zeit wider.
- **Empfohlener Wert:** Bei Bedarf für sofortige Updates oder Tests verwenden.
- **Händlerszenario / Beispiel:** Wenn es ein bedeutendes wirtschaftliches Ereignis gibt und Sie sicherstellen möchten, dass Ihre Kurse absolut aktuell sind, bevor Ihr nächster geplanter CRON-Job ausgeführt wird, können Sie diese Schaltfläche klicken.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | NBRB Wechselkurse aktivieren | JA | Aktiviert/deaktiviert das Abrufen und Anwenden von Kursen durch das Modul. |
| Modulkonfiguration | CRON-Job-URL | N/A (kopieren & einfügen) | URL zum Einrichten automatischer Kursaktualisierungen auf Ihrem Server. |
| Modulkonfiguration | Margenanpassung (%) | 0 | Fügt den abgerufenen NBRB-Kursen einen prozentualen Aufschlag/Abschlag hinzu. |
| Modulkonfiguration | Letzte Aktualisierung | N/A (schreibgeschützt) | Zeigt den Zeitstempel der letzten erfolgreichen Kursaktualisierung an. |
| Modulkonfiguration | Schaltfläche „Kurse manuell aktualisieren“ | N/A (zum Aktivieren klicken) | Löst eine sofortige, manuelle Aktualisierung der Wechselkurse aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine BYN-Preise werden nicht aktualisiert oder scheinen falsch zu sein.**
A:

1. **„NBRB Wechselkurse aktivieren“ überprüfen:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf „JA“ gesetzt ist.
2. **CRON-Job überprüfen:** Stellen Sie sicher, dass Ihr CRON-Job auf Ihrem Server mit der bereitgestellten URL korrekt eingerichtet ist und regelmäßig ausgeführt wird. Überprüfen Sie den Zeitstempel „Letzte Aktualisierung“ im Modul.
3. **Manuell aktualisieren:** Versuchen Sie, auf die Schaltfläche „Kurse manuell aktualisieren“ zu klicken. Wenn dies funktioniert, liegt das Problem wahrscheinlich bei Ihrer CRON-Job-Einrichtung.
4. **BYN-Währungsstatus überprüfen:** Gehen Sie zu **International > Währungen** und stellen Sie sicher, dass „Belarussischer Rubel (BYN)“ aktiviert ist und sein ISO-Code `BYN` ist.
5. **Cache leeren:** Manchmal kann der PrestaShop-Cache alte Werte enthalten. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“.

**F: Was passiert an Bankfeiertagen oder Wochenenden, wenn die NBRB keine neuen Kurse veröffentlicht?**
A: Das Modul ist so konzipiert, dass es dies intelligent handhabt. Wenn die NBRB-API an einem bestimmten Tag keine neuen Kurse bereitstellt (z. B. aufgrund eines Wochenendes oder Feiertags), verwendet das Modul weiterhin den zuletzt erfolgreich abgerufenen Kurs. Es wird nur aktualisiert, wenn neue offizielle Kurse verfügbar werden.

**F: Kann ich dieses Modul mit anderen Währungsumrechnungsmodulen verwenden?**
A: Es wird generell nicht empfohlen, mehrere Währungsumrechnungsmodule gleichzeitig zu betreiben, da diese Konflikte verursachen und zu unvorhersehbaren Ergebnissen führen können. Dieses Modul zielt speziell auf NBRB-Kurse für BYN ab. Wenn Sie andere Währungen benötigen, stellen Sie sicher, dass dieses Modul die primäre Quelle für BYN ist und andere Module verschiedene Währungen ohne Überschneidungen handhaben.

**F: Ich habe eine Marge festgelegt, aber die Preise scheinen sie nicht widerzuspiegeln.**
A:

1. **Änderungen speichern:** Stellen Sie sicher, dass Sie die Modulkonfiguration nach dem Festlegen der Marge gespeichert haben.
2. **Kurse aktualisieren:** Die Marge wird angewendet, wenn Kurse abgerufen werden. Warten Sie entweder auf den nächsten CRON-Job-Lauf oder klicken Sie auf „Kurse manuell aktualisieren“.
3. **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Performance**).
4. **Basiswährung überprüfen:** Die Marge wird auf die Umrechnung von der Basiswährung Ihres Shops in BYN angewendet. Stellen Sie sicher, dass Ihre Basiswährung in PrestaShop korrekt eingestellt ist.

**F: Ich erhalte einen Fehler beim Versuch, das Modul zu installieren oder zu konfigurieren.**
A:

1. **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modul-ZIP-Datei für Ihre spezifische PrestaShop-Version (1.6, 1.7, 8.x, 9.x) heruntergeladen haben.
2. **PHP-Kompatibilität:** Überprüfen Sie, ob die PHP-Version Ihres Servers innerhalb des unterstützten Bereichs liegt (PHP 5.6 - 8.5).
3. **Server-Logs:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers (oft in Ihrem Hosting-Kontrollpanel zu finden) auf detailliertere Fehlermeldungen. Dies kann helfen, das genaue Problem zu lokalisieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „NBRB Wechselkurse & Währung“ ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf eine einzige, kritische Aufgabe konzentriert: das Abrufen und Aktualisieren des Wechselkurses für den Belarussischen Rubel (BYN) von der API der Nationalbank der Republik Belarus (NBRB). Es nutzt das PrestaShop `Currency`-Objekt, um den `conversion_rate` für BYN zu aktualisieren. Das Modul verwendet einen CRON-Job für automatisierte Updates und bietet einen manuellen Auslöser im Back Office. Es hält sich an das MVC-Muster von PrestaShop für seine Konfiguration und die Ausführung des Front-Office-CRON-Jobs.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse:** `NbrbratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem externen CRON-Job aufgerufen zu werden. Beim Zugriff löst er die Logik zum Abrufen der Kurse des Moduls (`$this->module->updateRates()`) aus. Er gibt eine einfache Erfolgs-/Fehlermeldung aus, wodurch er für die automatisierte Ausführung ohne Browser geeignet ist. Er rendert keine vollständige Seite.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse:** `NbrbratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dies ist ein Platzhalter-Controller, der oft in Modulen enthalten ist, um die Verzeichnisauflistung zu verhindern oder eine standardmäßige „leere“ Seite bereitzustellen, wenn der Front-Controller des Moduls direkt ohne spezifische Aktionen aufgerufen wird. Im Kontext dieses Moduls dient er wahrscheinlich als Fallback und hat keine spezifische Geschäftslogik.
- **Back-Office-Admin-Controller**:

  - Dieses Modul verwendet keine dedizierten Admin-Controller. Die gesamte Back-Office-Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Seine Kernlogik zum Abrufen und Aktualisieren von Kursen ist in der Hauptmoduldatei `nbrbrates/cronjob.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Die Gestaltung der Admin-Konfigurationsseite wird typischerweise durch die Standard-Back-Office-CSS von PrestaShop gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `nbrbrates/views/admin.tpl`
    - **Zweck:** Dieses Template wird von der `getContent()`-Methode in der Hauptmoduldatei (`nbrbrates/cronjob.php`) gerendert. Es definiert die Struktur und Anzeige des Konfigurationsformulars des Moduls im PrestaShop Back Office. Es enthält Eingabefelder zum Aktivieren/Deaktivieren des Moduls, zur Margenanpassung, zur Anzeige der CRON-Job-URL, der letzten Aktualisierungszeit und der Schaltfläche zur manuellen Aktualisierung.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`. Wichtige Konfigurationsschlüssel sind:
    - `Nbrbrates_ENABLED`: (int) 1, wenn aktiviert, 0, wenn deaktiviert.
    - `Nbrbrates_MARGIN`: (float) Die anzuwendende prozentuale Marge.
    - `Nbrbrates_LAST_UPDATE`: (datetime) Zeitstempel der letzten erfolgreichen Kursaktualisierung.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert keine Hooks, die Inhalte im Front Office anzeigen (wie `displayHeader`, `displayRightColumn`, `displayFooter`). Seine primäre Interaktion mit PrestaShop erfolgt über:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionModuleInstall` | Wird bei der Installation des Moduls ausgeführt. | Initialisiert Standardkonfigurationswerte in `ps_configuration`. |
| `actionModuleUninstall` | Wird bei der Deinstallation des Moduls ausgeführt. | Bereinigt Konfigurationswerte aus `ps_configuration`. |
| `actionUpdateCurrency` | (Implizit) Wird ausgelöst, wenn eine Währung aktualisiert wird. | Die `updateRates()`-Methode des Moduls ändert direkt den `conversion_rate` des BYN-Währungsobjekts und wirkt sich somit auf Währungsaktualisierungen aus. |

Der Front-Office-Controller `cronjob.php` fungiert als externer Einstiegspunkt, nicht als traditioneller PrestaShop-Hook.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und den Zugriff auf die neuesten Versionen des Moduls „NBRB Wechselkurse & Währung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Integration des Moduls zur Verfügung.
