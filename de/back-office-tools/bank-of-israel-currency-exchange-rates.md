---
title: "Bank of Israel – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bank of Israel – Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Bank of Israel – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bank of Israel - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/bank-of-israel-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/bank-of-israel-currency-exchange-rates/)
>
> ---


# Bank of Israel – Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich. Ihre Hosting-Umgebung muss auch CRON-Jobs für automatisierte Updates unterstützen.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Einstellungen des Moduls zuzugreifen. Dies ist der Hauptbildschirm, auf dem Sie festlegen, wie das Modul Wechselkurse abruft und anwendet.

#### **MyPresta.eu-Updates**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt bietet Informationen zu Updates von MyPresta.eu, einschließlich der aktuellen Modulversion und verfügbarer Updates. Er hilft Ihnen, Ihr Modul auf dem neuesten Stand zu halten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Update verfügbar ist:* Sie sehen eine Benachrichtigung und einen Link zum Herunterladen der neuesten Version von Ihrem MyPresta.eu-Konto.
  - *Wenn kein Update verfügbar ist:* Der Abschnitt zeigt einfach Ihre aktuelle Version an.
- **Empfohlener Wert:** Halten Sie Ihre Module immer auf dem neuesten Stand, um von neuen Funktionen, Fehlerbehebungen und Sicherheitsverbesserungen zu profitieren.
- **Händlerszenario / Beispiel:** Überprüfen Sie diesen Abschnitt regelmäßig, um sicherzustellen, dass Ihr Modul aktuell ist, insbesondere nach größeren PrestaShop-Versions-Upgrades.

#### **Update-Intervall**

- **Was diese Einstellung bewirkt:** Dies bestimmt, wie oft das Modul versucht, Wechselkurse von der Bank of Israel abzurufen und zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Festlegen eines kürzeren Intervalls (z. B. 1 Stunde):* Wechselkurse werden häufiger aktualisiert, wodurch Ihre Preise immer sehr nah an der Echtzeit sind. Dies ist gut für sehr volatile Währungen oder hohe internationale Verkaufszahlen.
  - *Festlegen eines längeren Intervalls (z. B. 24 Stunden):* Wechselkurse werden seltener aktualisiert. Dies könnte geeignet sein, wenn Währungsschwankungen für Ihr Geschäft kein großes Problem darstellen oder wenn Sie weniger häufige externe Aufrufe bevorzugen.
- **Empfohlener Wert:** „24 Stunden“ für die meisten Shops. Wenn Sie ein hohes Verkaufsvolumen mit internationalen Kunden und häufig wechselnde Wechselkurse haben, ziehen Sie „12 Stunden“ oder „6 Stunden“ in Betracht.
- **Händlerszenario / Beispiel:** Wenn Sie hochwertige Elektronik an internationale Kunden verkaufen, könnten Sie „6 Stunden“ wählen, um sicherzustellen, dass Ihre Preise die neuesten Marktbedingungen widerspiegeln. Für eine lokale Boutique mit gelegentlichen internationalen Verkäufen sind „24 Stunden“ ausreichend.

#### **Update-Marge (%)**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, einen prozentualen Aufschlag auf die von der Bank of Israel abgerufenen Wechselkurse hinzuzufügen. Diese Marge wird zusätzlich zum offiziellen Kurs angewendet.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Festlegen einer positiven Marge (z. B. 2%):* Ihre umgerechneten Preise in anderen Währungen sind etwas höher als der direkte offizielle Wechselkurs, was Ihnen hilft, potenzielle Transaktionsgebühren, Währungsumrechnungskosten zu decken oder einfach Ihre Gewinnmarge zu erhöhen.
  - *Festlegen einer Nullmarge (0%):* Ihre Preise spiegeln den genauen offiziellen Wechselkurs ohne zusätzlichen Aufschlag wider.
- **Empfohlener Wert:** „0“, wenn Sie exakte offizielle Kurse wünschen. Ein kleiner positiver Wert (z. B. „1“ oder „2“) wird oft empfohlen, um potenzielle Bankgebühren zu decken oder einen Puffer gegen geringfügige Schwankungen zu bieten.
- **Händlerszenario / Beispiel:** Wenn Ihr Zahlungs-Gateway eine Gebühr von 1,5% für internationale Transaktionen erhebt, kann das Festlegen einer Marge von „1,5“ oder „2“ Prozent Ihnen helfen, diese Kosten zu absorbieren, ohne den Grundpreis Ihres Produkts in Ihrer Standardwährung zu beeinflussen.

#### **Zu aktualisierende Währungen**

- **Was diese Einstellung bewirkt:** Dies ist eine Liste aller Währungen, die derzeit in Ihrem PrestaShop-Shop aktiv sind. Sie können auswählen, welche dieser Währungen ihre Wechselkurse automatisch von diesem Modul aktualisieren lassen sollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auswählen einer Währung (Kontrollkästchen aktiviert):* Das Modul ruft den Wechselkurs für diese Währung (relativ zu ILS) von der Bank of Israel ab und aktualisiert ihn in Ihrem Shop.
  - *Abwählen einer Währung (Kontrollkästchen deaktiviert):* Das Modul ignoriert diese Währung, und ihr Wechselkurs wird *nicht* automatisch aktualisiert. Sie müssten ihn bei Bedarf manuell aktualisieren.
- **Empfohlener Wert:** Wählen Sie alle Währungen aus, die Sie aktiv für internationale Verkäufe verwenden und die Sie aktuell halten möchten. Stellen Sie sicher, dass Ihre Standardwährung (z. B. ILS) in PrestaShop korrekt konfiguriert ist.
- **Händlerszenario / Beispiel:** Wenn Sie an Kunden in den USA, Europa und Großbritannien verkaufen, würden Sie die Kästchen für USD, EUR und GBP aktivieren. Wenn Sie nur lokal in ILS und gelegentlich in die USA verkaufen, würden Sie möglicherweise nur USD aktivieren.

#### **CRON-Job-URL**

- **Was diese Einstellung bewirkt:** Dies zeigt die eindeutige URL an, die als CRON-Job auf Ihrem Webserver konfiguriert werden muss. Ein CRON-Job ist eine geplante Aufgabe, die Ihrem Server anweist, diese URL in regelmäßigen Abständen zu besuchen, wodurch das Modul ausgelöst wird, die Wechselkurse automatisch abzurufen und zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:** Dies ist keine Einstellung, die Sie ändern, sondern eine URL, die Sie *verwenden*.
  - *Wenn der CRON-Job korrekt eingerichtet ist:* Das Modul läuft automatisch in Ihrem angegebenen „Update-Intervall“ und hält Ihre Wechselkurse ohne manuelles Eingreifen aktuell.
  - *Wenn der CRON-Job NICHT eingerichtet ist:* Wechselkurse werden *nicht* automatisch aktualisiert. Sie müssten diese URL manuell in Ihrem Browser besuchen (was für den regelmäßigen Gebrauch nicht empfohlen wird) oder die Kurse manuell in PrestaShop aktualisieren.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als CRON-Job in Ihrem Hosting-Panel (z. B. cPanel, Plesk oder über SSH) ein. Die Häufigkeit des CRON-Jobs sollte mit Ihrer Einstellung für das „Update-Intervall“ übereinstimmen oder etwas häufiger sein. Wenn Ihr Update-Intervall beispielsweise 24 Stunden beträgt, stellen Sie den CRON-Job so ein, dass er einmal alle 24 Stunden ausgeführt wird.
- **Händlerszenario / Beispiel:** Nachdem Sie alle anderen Einstellungen konfiguriert haben, kopieren Sie diese URL und fügen Sie sie in den CRON-Job-Scheduler Ihres Hosting-Anbieters ein. Stellen Sie ihn so ein, dass er täglich zu einer Zeit mit geringem Datenverkehr (z. B. 3 Uhr morgens) ausgeführt wird.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MyPresta.eu-Updates | N/A | Zeigt Modulversion und Update-Verfügbarkeit an. |
| Modulkonfiguration | Update-Intervall | 24 Stunden | Wie oft Wechselkurse abgerufen werden (z. B. 6, 12, 24 Stunden). |
| Modulkonfiguration | Update-Marge (%) | 0-2% | Fügt einen prozentualen Aufschlag zu den abgerufenen Wechselkursen hinzu. |
| Modulkonfiguration | Zu aktualisierende Währungen | Alle aktiven Währungen | Wählt aus, welche Währungen automatisch aktualisiert werden sollen. |
| Modulkonfiguration | CRON-Job-URL | N/A | URL zur Konfiguration auf Ihrem Server für automatisierte Updates. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht automatisch aktualisiert. Was soll ich tun?**
A:

1.  **CRON-Job überprüfen:** Der häufigste Grund ist ein falsch konfigurierter oder fehlender CRON-Job. Überprüfen Sie die CRON-Job-URL, die in der Modulkonfiguration angegeben ist, und stellen Sie sicher, dass sie auf Ihrem Hosting-Server korrekt eingerichtet ist, um in der gewünschten Häufigkeit ausgeführt zu werden.
2.  **Moduleinstellungen:** Überprüfen Sie, ob das „Update-Intervall“ eingestellt ist und ob die gewünschten „Zu aktualisierenden Währungen“ in der Modulkonfiguration aktiviert sind.
3.  **Serverzugriff:** Stellen Sie sicher, dass Ihr Server externe Anfragen an die API der Bank of Israel stellen kann. Manchmal können Firewalls oder Sicherheitseinstellungen dies blockieren. Kontaktieren Sie Ihren Hosting-Anbieter, wenn Sie dies vermuten.
4.  **PrestaShop-Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren), nachdem Sie Änderungen an den Moduleinstellungen vorgenommen haben.

**F: Kann ich einen Wechselkurs manuell überschreiben, nachdem das Modul ihn aktualisiert hat?**
A: Ja, das können Sie. Nachdem das Modul ausgeführt wurde, werden die Kurse in den Standard-Währungseinstellungen von PrestaShop (International > Währungen) gespeichert. Sie können den Wechselkurs einer bestimmten Währung dort manuell bearbeiten. Beachten Sie jedoch, dass der CRON-Job bei der nächsten Ausführung Ihre manuelle Änderung mit dem neuesten Kurs der Bank of Israel (plus Ihrer Marge) überschreibt.

**F: Was passiert, wenn die API der Bank of Israel vorübergehend nicht verfügbar ist?**
A: Wenn das Modul keine Daten abrufen kann, behält es in der Regel die zuletzt erfolgreich aktualisierten Wechselkurse bei. Es löscht oder setzt Ihre Kurse nicht auf Null zurück. Es versucht einfach beim nächsten geplanten CRON-Job-Lauf erneut.

**F: Meine Preise sehen nach dem Update leicht daneben aus. Warum?**
A:

1.  **Update-Marge:** Überprüfen Sie die Einstellung „Update-Marge (%)“ in der Modulkonfiguration. Wenn Sie eine positive Marge eingestellt haben, sind Ihre Preise etwas höher als der direkte offizielle Kurs.
2.  **Rundung:** Die Währungseinstellungen von PrestaShop haben auch eine Option „Dezimalstellen“. Stellen Sie sicher, dass diese für Ihre Währungen entsprechend eingestellt ist, um unerwartete Rundungsprobleme zu vermeiden.
3.  **Basiswährung:** Stellen Sie sicher, dass Ihre Standardwährung in PrestaShop (International > Währungen) korrekt als israelischer Schekel (ILS) eingestellt ist, wenn dies Ihre Basiswährung für diese Updates ist.

**F: Wie richte ich einen CRON-Job ein?**
A: Dieser Prozess variiert je nach Hosting-Anbieter. Im Allgemeinen melden Sie sich bei Ihrem Hosting-Kontrollpanel (z. B. cPanel, Plesk) an. Suchen Sie nach einem Abschnitt namens „Cron-Jobs“, „Geplante Aufgaben“ oder „Automatisierte Aufgaben“. Sie müssen einen neuen CRON-Job hinzufügen, die Häufigkeit angeben (z. B. einmal täglich) und die vom Modul bereitgestellte „CRON-Job-URL“ einfügen. Wenn Sie unsicher sind, wenden Sie sich an den Support Ihres Hosting-Anbieters und geben Sie ihm die URL und die gewünschte Häufigkeit an.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Bank of Israel – Wechselkurse“ (`boirates`) folgt einer Standard-PrestaShop-Modularchitektur. Es nutzt eine Hauptmodulklasse (`boirates.php`) für Installation, Deinstallation und Konfigurationsverwaltung. Wechselkursaktualisierungen werden hauptsächlich über einen Front-Controller (`cronjob.php`) ausgelöst, der von einem serverseitigen CRON-Job aufgerufen werden soll. Das Modul ruft XML-Daten von der offiziellen API der Bank of Israel ab, parst sie und aktualisiert die Tabelle `ps_currency` von PrestaShop.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname**: `BoiratesCronjobModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller ist dafür konzipiert, von einem externen CRON-Job aufgerufen zu werden. Er enthält die Kernlogik zum Abrufen von Wechselkursen von der API der Bank of Israel, zum Parsen der XML-Antwort, zum Anwenden der konfigurierten Marge und zum Aktualisieren der Tabelle `ps_currency` in PrestaShop. Er rendert keine Front-Office-Inhalte, sondern führt die Hintergrunddatenverarbeitung durch. Er ist entscheidend für die automatisierte Funktionalität des Moduls.
  - `controllers/front/index.php`
    - **Klassenname**: `BoiratesIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dies ist ein Platzhalter oder Standard-Front-Controller. In vielen Modulen könnte `index.php` aufgerufen werden, wenn eine bestimmte Aktion nicht geroutet wird. Für dieses Modul besteht seine Hauptfunktion wahrscheinlich darin, die Verzeichnisauflistung zu verhindern oder eine minimale Standardantwort bereitzustellen, wenn direkt ohne spezifische Parameter darauf zugegriffen wird. Die Kernlogik befindet sich in `cronjob.php`.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Die Logik des Moduls ist hauptsächlich in der Hauptdatei `boirates.php` und dem `BoiratesCronjobModuleFrontController` gekapselt. Die Dateninteraktion erfolgt direkt mit der PrestaShop-Klasse `Currency` und der Tabelle `ps_configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Zweck**: Dieses Template wird von der `getContent()`-Methode der Moduldatei `boirates.php` gerendert. Es definiert die Struktur und das Layout der Konfigurationsseite des Moduls im PrestaShop Back Office. Es enthält die Formularelemente für die Einstellungen `mypresta_updates`, `update_`, `updatev_` und `currency_` sowie die Anzeige der CRON-Job-URL.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es interagiert mit der Standard-PrestaShop-Tabelle `ps_configuration`, um seine Einstellungen zu speichern (z. B. `BOIRATES_UPDATE_INTERVAL`, `BOIRATES_UPDATE_MARGIN`, `BOIRATES_CURRENCIES_TO_UPDATE`).
  - Es aktualisiert die Spalte `exchange_rate` in der Tabelle `ps_currency` für ausgewählte Währungen.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert in seiner `install()`-Methode keine expliziten Front-Office-Anzeige-Hooks (wie `displayHeader`, `displayRightColumn`, `displayProductButtons`, `displayFooter`) zum Rendern von Inhalten. Seine Hauptfunktion ist die Hintergrunddatenverarbeitung.
  Es verwendet wahrscheinlich interne PrestaShop-Hooks für seine Kernfunktionalität, wie zum Beispiel:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionModuleInstall` | Während der Modulinstallation | Richtet Standardkonfigurationswerte ein und registriert notwendige Elemente. |
  | `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationswerte. |
  | `displayBackOfficeHeader` | Rendert Inhalte im Back Office-Header | Potenziell für das Hinzufügen von CSS/JS oder Benachrichtigungen verwendet, obwohl im Inventar nicht explizit erkannt. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Updates und zum Herunterladen der neuesten Versionen des Moduls „Bank of Israel – Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
