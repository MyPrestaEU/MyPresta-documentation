---
title: "Bank von Lettland (Latvijas Banka) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bank von Lettland (Latvijas Banka) - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Bank von Lettland (Latvijas Banka) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bank of Latvia (Latvijas Banka) - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates/)
>
> ---


# Bank von Lettland (Latvijas Banka) - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Hauptseite der Moduleinstellungen zuzugreifen. Hier legen Sie fest, wie das Modul Wechselkurse abruft und anwendet.

Die Konfigurationsseite für das Modul „Bank von Lettland (Latvijas Banka) - Wechselkurse“ ist unkompliziert und darauf ausgelegt, Sie schnell einsatzbereit zu machen.

**Screenshot der Konfigurationsseite (Beispiel):**
*(Stellen Sie sich hier einen Screenshot vor, der die Konfigurationsseite des Moduls mit Feldern für „CRON URL“, „Spread“, „Update-Frequenz“ und „Aktiviert/Deaktiviert“-Schalter zeigt)*

#### 2.1.1 CRON URL

- **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Webadresse (URL), die, wenn sie aufgerufen wird, das Modul dazu veranlasst, die neuesten Wechselkurse von der Bank von Lettland abzurufen und in Ihrem PrestaShop-Store zu aktualisieren. Sie ist dazu gedacht, automatisch von einem „Cron-Job“ auf Ihrem Server aufgerufen zu werden.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert. Das Kopieren dieser URL ist unerlässlich für die Einrichtung der automatisierten Updates. Wenn Sie keinen Cron-Job mit dieser URL einrichten, werden die Wechselkurse nicht automatisch aktualisiert.
- **Empfohlener Wert:** Kopieren Sie diese URL genau so, wie sie erscheint.
- **Händlerszenario / Beispiel:** Sie kopieren diese URL und fügen sie in den Abschnitt „Cron-Jobs“ Ihres Hosting-Kontrollpanels (z. B. cPanel, Plesk oder eine ähnliche Oberfläche) ein, um tägliche Updates zu planen.

#### 2.1.2 Spread (%)

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, einen prozentualen „Puffer“ oder eine Marge zu den offiziellen Wechselkursen hinzuzufügen. Wenn das Modul einen Kurs abruft, erhöht es diesen um diesen Prozentsatz, bevor es ihn in Ihrem Store speichert. Dies hilft, Ihre Gewinnmargen vor Währungsschwankungen und Transaktionsgebühren zu schützen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf 0 gesetzt:* Das Modul verwendet die genauen Wechselkurse, die von der Bank von Lettland bereitgestellt werden. Ihre Preise spiegeln die offiziellen Kurse direkt wider.
  - *Wenn auf einen positiven Wert gesetzt (z. B. 2%):* Die Wechselkurse in Ihrem Store sind 2% höher als die offiziellen Kurse. Das bedeutet, wenn ein Produkt 100 EUR kostet und der offizielle Kurs zu USD 1,10 beträgt, verwendet das Modul mit einem Spread von 2% einen Kurs von 1,122 (1,10 * 1,02), wodurch der USD-Preis 112,20 beträgt.
- **Empfohlener Wert:** Dies hängt von Ihrem Geschäftsmodell, den Gebühren des Zahlungs-Gateways und den gewünschten Gewinnmargen ab. Ein üblicher Ausgangspunkt könnte 0,5% bis 2% sein, um Transaktionskosten und geringfügige Schwankungen abzudecken.
- **Händlerszenario / Beispiel:** Wenn Ihr Zahlungsabwickler eine Gebühr von 1% für internationale Transaktionen erhebt, könnte ein Spread von 1,5% Ihnen helfen, diese Kosten zu absorbieren und dennoch Ihre gewünschte Gewinnmarge zu erhalten.

#### 2.1.3 Update-Frequenz

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt, wie oft das Modul versuchen *sollte*, die Wechselkurse zu aktualisieren. Während der Cron-Job (siehe CRON URL) die Aktualisierung tatsächlich auslöst, dient diese Einstellung als Schutz, um zu häufige Aktualisierungen zu verhindern, die unnötig oder sogar problematisch für einige Hosting-Umgebungen sein könnten.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Täglich“ gesetzt:* Das Modul verarbeitet ein Update nur einmal alle 24 Stunden, selbst wenn der Cron-Job häufiger läuft.
  - *Wenn auf „Stündlich“ gesetzt:* Das Modul verarbeitet ein Update einmal pro Stunde.
  - *Wenn auf „Alle 15 Minuten“ gesetzt:* Das Modul verarbeitet ein Update alle 15 Minuten.
- **Empfohlener Wert:** „Täglich“ ist für die meisten E-Commerce-Stores in der Regel ausreichend, da offizielle Wechselkurse normalerweise nicht innerhalb von Minuten drastisch schwanken. Wenn Sie sehr hochwertige Artikel haben oder in extrem volatilen Märkten tätig sind, könnte „Stündlich“ in Betracht gezogen werden.
- **Händlerszenario / Beispiel:** Sie stellen Ihren Cron-Job so ein, dass er alle 6 Stunden läuft, aber Sie stellen die „Update-Frequenz“ hier auf „Täglich“ ein. Das Modul führt nur einmal innerhalb eines 24-Stunden-Zeitraums eine tatsächliche Kursaktualisierung durch, obwohl der Cron-Job versucht, sie häufiger auszulösen. Dies verhindert unnötige API-Aufrufe und Ressourcenverbrauch.

#### 2.1.4 Modul aktivieren

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher Ein-/Ausschalter für die Kernfunktionalität des Moduls.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul ruft aktiv Wechselkurse ab und aktualisiert sie gemäß Ihren Einstellungen und dem Cron-Job-Zeitplan.
  - *Wenn deaktiviert (NEIN):* Das Modul stoppt das Abrufen und Aktualisieren von Wechselkursen. Ihr Store verwendet weiterhin die zuletzt bekannten Kurse oder das Standardverhalten von PrestaShop für Kursaktualisierungen, falls Sie andere Mechanismen eingerichtet haben.
- **Empfohlener Wert:** „JA“, um automatisierte Währungsaktualisierungen zu gewährleisten.
- **Händlerszenario / Beispiel:** Sie könnten das Modul vorübergehend deaktivieren, wenn Sie Wartungsarbeiten an Ihrem Store durchführen müssen oder wenn Sie sich entscheiden, Wechselkurse für kurze Zeit manuell zu verwalten. Denken Sie daran, es danach wieder zu aktivieren.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | CRON URL | Genau kopieren | URL zum Auslösen von Kursaktualisierungen über den Server-Cron-Job. Wesentlich für die Automatisierung. |
| Modulkonfiguration | Spread (%) | 0% - 2% (abhängig vom Geschäft) | Fügt den abgerufenen Wechselkursen eine prozentuale Marge hinzu, um Gewinne zu schützen. |
| Modulkonfiguration | Update-Frequenz | Täglich | Steuert, wie oft das Modul *tatsächlich* ein Update verarbeitet, auch wenn der Cron häufiger läuft. |
| Modulkonfiguration | Modul aktivieren | JA | Schaltet die Kursaktualisierungsfunktion des Moduls ein oder aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht aktualisiert. Was soll ich tun?**
A:

1.  **Überprüfen Sie Ihren Cron-Job:** Der häufigste Grund ist ein falsch eingerichteter oder fehlender Cron-Job auf Ihrem Hosting-Server. Überprüfen Sie nochmals, ob Sie die exakte CRON URL von der Konfigurationsseite des Moduls kopiert haben und ob Ihr Cron-Job zur Ausführung geplant ist.
2.  **Modul aktiviert?** Stellen Sie sicher, dass der Schalter „Modul aktivieren“ auf der Konfigurationsseite auf „JA“ steht.
3.  **Update-Frequenz:** Überprüfen Sie die Einstellung „Update-Frequenz“. Wenn Ihr Cron-Job stündlich läuft, die Frequenz aber auf „Täglich“ eingestellt ist, wird er nur einmal täglich aktualisiert.
4.  **PrestaShop-Cache:** Manchmal kann das Leeren Ihres PrestaShop-Caches (unter **Erweiterte Parameter > Leistung**) helfen, angezeigte Daten zu aktualisieren, obwohl dies die Backend-Kursaktualisierungen weniger wahrscheinlich beeinflusst.

**F: Kann ich einen Wechselkurs manuell überschreiben, nachdem das Modul ihn aktualisiert hat?**
A: Ja, das können Sie. Das Modul aktualisiert die Kurse im Standard-Währungsverwaltungssystem von PrestaShop. Wenn Sie im Back Office zu **International > Währungen** gehen, können Sie den Wechselkurs für jede Währung manuell bearbeiten. Beachten Sie jedoch, dass das Modul Ihre manuellen Änderungen beim nächsten Lauf des Cron-Jobs und der Auslösung eines Updates überschreiben wird.

**F: Was passiert, wenn der Dienst der Bank von Lettland vorübergehend nicht verfügbar ist?**
A: Das Modul ist darauf ausgelegt, Kurse von einer externen Quelle abzurufen. Wenn der Dienst der Bank von Lettland ausgefallen oder nicht erreichbar ist, wird das Modul wahrscheinlich keine neuen Kurse abrufen können. In solchen Fällen verwendet Ihr Store weiterhin die *zuletzt erfolgreich aktualisierten* Wechselkurse. Es wird nicht auf Standard- oder falsche Kurse zurückgesetzt. Sobald der Dienst wiederhergestellt ist, wird der nächste Cron-Job-Lauf die Kurse erneut aktualisieren.

**F: Erstellt dieses Modul neue Währungen in meinem Store?**
A: Nein, dieses Modul aktualisiert nur die Wechselkurse für Währungen, die Sie *bereits* in Ihrem PrestaShop-Store aktiviert haben (unter **International > Währungen**). Sie müssen die gewünschten Währungen zuerst in den Standardeinstellungen von PrestaShop hinzufügen und aktivieren, damit dieses Modul deren Kurse verwalten kann.

**F: Mein benutzerdefiniertes Theme zeigt die Preise nach Updates nicht korrekt an.**
A: Dieses Modul ändert nur die zugrunde liegenden Wechselkurse. Wenn Preise falsch angezeigt werden, ist es höchst unwahrscheinlich, dass dies ein direktes Problem des Moduls ist.

1.  **Smarty-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“.
2.  **Theme-Kompatibilität:** Stellen Sie sicher, dass Ihr benutzerdefiniertes Theme vollständig mit Ihrer PrestaShop-Version kompatibel ist.
3.  **Benutzerdefinierter Code:** Wenn Ihr Theme benutzerdefinierten Code für die Preisanzeige enthält, interpretiert es möglicherweise die aktualisierten Währungskurse von PrestaShop nicht korrekt. Konsultieren Sie Ihren Theme-Entwickler oder einen PrestaShop-Experten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bank von Lettland (Latvijas Banka) - Wechselkurse“ (`lbrates`) ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich zur Automatisierung von Wechselkursaktualisierungen entwickelt wurde. Es folgt einem einfachen MVC-Muster, bei dem die Hauptmoduldatei (`cronjob.php`) als primärer Controller für die Konfiguration fungiert und der Front-Controller (`cronjob.php`) die eigentliche Logik zum Abrufen der Kurse handhabt. Es nutzt die PrestaShop-Klassen `Currency` und `Configuration`, um Kurse und Einstellungen zu verwalten. Das Modul wird durch externe Cron-Job-Aufrufe gesteuert, was es zu einem asynchronen Hintergrundprozess macht.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `lbrates/controllers/front/cronjob.php`
    - Klassenname: `LbratesCronjobModuleFrontController`
    - Übergeordnete Klasse: `ModuleFrontController`
    - Verantwortung: Dieser Controller ist der Kern der Modulfunktionalität. Er ist dafür konzipiert, von einem externen Cron-Job aufgerufen zu werden. Beim Zugriff ruft er die neuesten Euro-Referenzkurse von der offiziellen API der Bank von Lettland ab, wendet den konfigurierten Spread an und aktualisiert die Wechselkurse für alle aktiven Währungen in der PrestaShop-Datenbank. Er handhabt auch die Protokollierung und verhindert zu häufige Aktualisierungen basierend auf dem Konfigurationsschlüssel `PS_LBRATES_LAST_UPDATE`.
  - `lbrates/controllers/front/index.php`
    - Klassenname: `LbratesIndexModuleFrontController`
    - Übergeordnete Klasse: `ModuleFrontController`
    - Verantwortung: Dies ist eine standardmäßige leere `index.php`-Datei, die oft in PrestaShop-Modul-Front-Controller-Verzeichnissen enthalten ist, um die Verzeichnisauflistung zu verhindern. Sie enthält keine funktionale Logik.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Administration wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul interagiert direkt mit den PrestaShop-Kernklassen `Currency` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul verwendet kein benutzerdefiniertes JavaScript.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul verwendet kein benutzerdefiniertes CSS.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `lbrates/views/admin.tpl`
    - Dieses Template wird von der `getContent()`-Methode in der Hauptmoduldatei `cronjob.php` gerendert. Es zeigt das Konfigurationsformular des Moduls im PrestaShop Back Office an. Dies umfasst Felder für die CRON URL, den Spread, die Update-Frequenz und den Aktivieren/Deaktivieren-Schalter. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration`:
    - `PS_LBRATES_SPREAD`: Speichert den konfigurierten prozentualen Spread.
    - `PS_LBRATES_UPDATE_FREQUENCY`: Speichert die konfigurierte Update-Frequenz (z. B. täglich, stündlich).
    - `PS_LBRATES_LAST_UPDATE`: Speichert den Zeitstempel des letzten erfolgreichen Updates, um zu häufige Aufrufe zu verhindern.
    - `PS_LBRATES_ENABLED`: Speichert den Aktivierungs-/Deaktivierungsstatus des Moduls.
  - Es aktualisiert die Spalte `exchange_rate` in der Tabelle `ps_currency` für aktive Währungen.
- **Registrierte Hooks-Tabelle**:

  - Das Modul registriert keine traditionellen Anzeige-Hooks (`displayHeader`, `displayFooter` usw.) im Front Office. Seine Hauptfunktion ist die Hintergrundverarbeitung.
  - Es verwendet implizit den Hook `actionUpdateCurrency` (oder ähnliche interne Mechanismen), indem es Wechselkurse direkt ändert, registriert sich aber nicht explizit dafür.
  - Die `install()`-Methode des Moduls würde das Modul selbst innerhalb des PrestaShop-Modulsystems registrieren, wodurch seine Konfiguration zugänglich wird.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bank von Lettland (Latvijas Banka) - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
