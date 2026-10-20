---
title: "HM Revenue & Customs (HMRC) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „HM Revenue & Customs (HMRC) - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "HM Revenue & Customs (HMRC) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul HM Revenue & Customs (HMRC) - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/hm-revenue-customs-hmrc-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/hm-revenue-customs-hmrc-currency-exchange-rates/)
>
> ---


# HM Revenue & Customs (HMRC) - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich, die in den meisten Hosting-Umgebungen Standard sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des HMRC-Wechselkursmoduls. Hier legen Sie fest, wie das Modul die offiziellen Wechselkurse abruft und anwendet.

Die Konfigurationsseite zeigt Ihnen die folgenden wichtigen Informationen und Einstellungen:

#### **Cron-Job-URL**

- **Was diese Einstellung bewirkt:** Dies ist eine spezielle Webadresse (URL), die, wenn sie aufgerufen wird, das Modul dazu veranlasst, die neuesten HMRC-Wechselkurse abzurufen und in Ihrem PrestaShop-Shop zu aktualisieren. Sie ist dafür konzipiert, automatisch von einem „Cron-Job“ auf Ihrem Server ausgeführt zu werden.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert.
- **Empfohlener Wert:** Kopieren Sie diese URL genau so, wie sie angezeigt wird.
- **Händlerszenario / Beispiel:** Sie benötigen diese URL, um eine automatisierte Aufgabe (Cron-Job) auf Ihrem Webhosting-Server einzurichten. Diese Aufgabe ruft die URL zu einem geplanten Zeitpunkt (z. B. einmal täglich oder einmal monatlich) auf, um sicherzustellen, dass Ihre Kurse immer aktuell sind, ohne dass Sie manuell etwas anklicken müssen.

#### **Cron-Job-Befehl (für Linux/Unix-Server)**

- **Was diese Einstellung bewirkt:** Dies ist eine Befehlszeilenanweisung, die dasselbe Ergebnis wie das Aufrufen der Cron-Job-URL erzielt, aber speziell für die direkte Verwendung in einem Cron-Job-Scheduler eines Servers formatiert ist (oft in Ihrem Hosting-Kontrollpanel wie cPanel oder Plesk zu finden). Sie verwendet `wget` oder `curl`, um die URL stillschweigend anzufordern.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diesen Befehl nicht direkt ändern. Er wird vom Modul generiert.
- **Empfohlener Wert:** Kopieren Sie diesen Befehl genau so, wie er angezeigt wird.
- **Händlerszenario / Beispiel:** Wenn Ihr Hosting-Anbieter Linux/Unix-Server verwendet (was die meisten tun), verwenden Sie diesen Befehl, um Ihren automatisierten Cron-Job einzurichten. Dies ist im Allgemeinen zuverlässiger, als sich auf webbasierte Cron-Dienste zu verlassen.

#### **Letzter Aktualisierungsstatus**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt zeigt Informationen darüber an, wann das Modul zuletzt erfolgreich die HMRC-Kurse abgerufen und aktualisiert hat. Er zeigt Datum und Uhrzeit der letzten Aktualisierung an.
- **Auswirkung einer Änderung dieser Einstellung:** Dies ist nur eine Informationsanzeige; Sie können sie nicht ändern.
- **Empfohlener Wert:** Überwachen Sie dies, um sicherzustellen, dass Ihr Cron-Job korrekt ausgeführt wird und die Kurse regelmäßig aktualisiert werden.
- **Händlerszenario / Beispiel:** Wenn Sie Ihren Cron-Job so einrichten, dass er täglich ausgeführt wird, sollten Sie sehen, dass sich der „Letzte Aktualisierungsstatus“ täglich ändert, was bestätigt, dass das Modul wie erwartet funktioniert. Wenn er nicht aktualisiert wird, deutet dies auf ein Problem mit Ihrer Cron-Job-Einrichtung hin.

#### **Schaltfläche „Jetzt aktualisieren“**

- **Was diese Einstellung bewirkt:** Diese Schaltfläche ermöglicht es Ihnen, den Kursaktualisierungsprozess sofort manuell direkt von der Modulkonfigurationsseite aus auszulösen.
- **Auswirkung einer Änderung dieser Einstellung:** Durch Klicken auf diese Schaltfläche werden die neuesten HMRC-Kurse sofort abgerufen und auf die Währungen Ihres Shops angewendet.
- **Empfohlener Wert:** Verwenden Sie diese Schaltfläche für erste Tests nach der Installation oder wenn Sie eine sofortige Aktualisierung außerhalb Ihres geplanten Cron-Jobs erzwingen müssen.
- **Händlerszenario / Beispiel:** Klicken Sie nach der Installation des Moduls auf „Jetzt aktualisieren“, um zu sehen, ob die Kurse korrekt abgerufen werden und um Ihren Shop mit den neuesten HMRC-Kursen zu füllen, bevor Ihr erster geplanter Cron-Job ausgeführt wird.

#### **Wichtiger Hinweis zu Cron-Jobs:**

Die Kernfunktionalität dieses Moduls basiert auf einem **Cron-Job**, der auf Ihrem Webserver eingerichtet ist. Ein Cron-Job ist ein zeitbasierter Job-Scheduler in Unix-ähnlichen Computerbetriebssystemen. Er ermöglicht es Benutzern, Jobs (Befehle oder Skripte) so zu planen, dass sie periodisch zu festen Zeiten, Daten oder Intervallen ausgeführt werden.

**So richten Sie einen Cron-Job ein (allgemeine Schritte):**

1. **Greifen Sie auf Ihr Hosting-Kontrollpanel zu:** Melden Sie sich bei Ihrem cPanel, Plesk oder einem anderen Hosting-Kontrollpanel an.
2. **Suchen Sie „Cron-Jobs“ oder „Geplante Aufgaben“:** Suchen Sie nach einem Abschnitt, der normalerweise „Cron-Jobs“, „Geplante Aufgaben“ oder „Automatisierung“ genannt wird.
3. **Fügen Sie einen neuen Cron-Job hinzu:**
   - **Häufigkeit:** Legen Sie die Häufigkeit fest. Für HMRC-Kurse ist monatlich in der Regel ausreichend (z. B. „Einmal im Monat“ am 1. Tag des Monats). Einige Händler bevorzugen täglich für zusätzliche Sicherheit, aber HMRC-Kurse sind monatlich.
   - **Befehl:** Fügen Sie den vom Modul bereitgestellten „Cron-Job-Befehl“ in das Befehlsfeld ein.
   - **E-Mail:** Sie können normalerweise eine E-Mail-Adresse angeben, um die Ausgabe des Cron-Jobs zu erhalten. Dies ist nützlich zur Fehlerbehebung, wenn der Job fehlschlägt.
4. **Speichern:** Speichern Sie den Cron-Job.

Wenn Sie unsicher sind, wie Sie einen Cron-Job einrichten, wenden Sie sich bitte an das Support-Team Ihres Hosting-Anbieters und geben Sie ihm den „Cron-Job-Befehl“ von der Konfigurationsseite des Moduls, mit der Bitte, ihn monatlich (oder täglich, je nach Ihren Präferenzen) auszuführen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Cron-Job-URL | N/A (Kopieren & Verwenden) | URL zum Auslösen der Kursaktualisierung; für webbasierte Cron-Dienste. |
| Modulkonfiguration | Cron-Job-Befehl | N/A (Kopieren & Verwenden) | Befehlszeilenanweisung für serverbasierte Cron-Jobs (z. B. cPanel). |
| Modulkonfiguration | Letzter Aktualisierungsstatus | N/A (Informationszweck) | Zeigt Datum/Uhrzeit der letzten erfolgreichen Kursaktualisierung an. |
| Modulkonfiguration | Schaltfläche „Jetzt aktualisieren“ | Klicken für manuelle Aktualisierung | Ruft sofort die neuesten HMRC-Kurse ab und wendet sie an. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht aktualisiert. Was soll ich tun?**
A: Der häufigste Grund dafür ist ein falsch eingerichteter Cron-Job.
1. **Überprüfen Sie Ihre Cron-Job-Einrichtung:** Melden Sie sich bei Ihrem Hosting-Kontrollpanel (cPanel, Plesk usw.) an und überprüfen Sie, ob der Cron-Job mit dem vom Modul bereitgestellten „Cron-Job-Befehl“ korrekt konfiguriert ist. Stellen Sie sicher, dass die Häufigkeit wie gewünscht eingestellt ist (z. B. monatlich oder täglich).
2. **Manuell testen:** Gehen Sie zur Konfigurationsseite des Moduls in Ihrem PrestaShop-Backoffice und klicken Sie auf die Schaltfläche „Jetzt aktualisieren“. Wenn dies funktioniert, liegt das Problem definitiv bei Ihrer Cron-Job-Einrichtung. Wenn es nicht funktioniert, könnte ein serverseitiges Problem vorliegen, das das Abrufen von Daten durch das Modul verhindert (z. B. Firewall, cURL-Probleme).
3. **Kontaktieren Sie Ihren Host:** Wenn Sie sich bei Cron-Jobs unsicher sind, geben Sie Ihrem Hosting-Support den „Cron-Job-Befehl“ und bitten Sie ihn, ihn für Sie einzurichten.

**F: Beeinflusst dieses Modul die Preise, die Kunden auf meiner Website sehen?**
A: Ja, indirekt. Das Modul aktualisiert die zugrunde liegenden Wechselkurse in PrestaShop. Wenn Ihr Shop es Kunden ermöglicht, zwischen Währungen zu wechseln, spiegeln die in diesen Fremdwährungen angezeigten Preise die aktualisierten Kurse wider. Der Hauptzweck des Moduls ist jedoch die *interne* Buchhaltung und Steuerkonformität, nicht unbedingt dynamische Frontend-Preisstrategien.

**F: Was passiert, wenn HMRC seine Methode zur Veröffentlichung von Wechselkursen ändert?**
A: MyPresta.eu überwacht regelmäßig Änderungen an externen Diensten wie HMRC. Wenn HMRC seine Datenquelle oder sein Format ändert, werden wir ein Update des Moduls veröffentlichen, um die fortgesetzte Kompatibilität sicherzustellen. Halten Sie Ihre Module immer auf dem neuesten Stand.

**F: Kann ich dieses Modul verwenden, wenn meine Basiswährung nicht GBP ist?**
A: Obwohl das Modul HMRC-Kurse abruft, liegt sein Hauptvorteil in der Einhaltung der britischen Mehrwertsteuer, die typischerweise GBP als Berichtswährung annimmt. Wenn Ihre Basiswährung nicht GBP ist, aktualisiert das Modul dennoch die Wechselkurse für andere Währungen relativ zu Ihrer Basiswährung, aber Sie müssen verstehen, wie dies mit Ihren spezifischen Steuerberichtspflichten interagiert. Für die britische Mehrwertsteuer wird im Allgemeinen empfohlen, GBP als Standardwährung zu verwenden.

**F: Ich erhalte eine Fehlermeldung, wenn ich versuche, Kurse manuell zu aktualisieren.**
A: Dies könnte auf mehrere Dinge hindeuten:
1. **Serverkonnektivität:** Ihr Server kann möglicherweise keine Verbindung zur HMRC-Website herstellen, um die Daten abzurufen. Dies könnte an einer Firewall, einem Netzwerkproblem oder einer vorübergehenden Ausfallzeit des HMRC-Servers liegen.
2. **PHP-Erweiterungen:** Stellen Sie sicher, dass Standard-PHP-Erweiterungen wie `cURL` und `JSON` auf Ihrem Server aktiviert sind.
3. **Modulberechtigungen:** Überprüfen Sie, ob die Moduldateien die richtigen Lese-/Schreibberechtigungen haben.
Wenn das Problem weiterhin besteht, wenden Sie sich mit der genauen Fehlermeldung an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die für die Wartung oder Erweiterung des PrestaShop-Shops verantwortlich sind.

### 4.1 Architekturübersicht

Das Modul `hmrcrates` ist ein unkompliziertes PrestaShop-Modul, das entwickelt wurde, um Wechselkurse von der HMRC-Website abzurufen und zu aktualisieren. Es nutzt die Modularchitektur von PrestaShop, hauptsächlich die `Module`-Klasse für Installation/Deinstallation und `ModuleFrontController` für die Bearbeitung von Cron-Job-Anfragen. Die Kernlogik befindet sich in der Hauptmoduldatei `cronjob.php`, die auch als primärer Einstiegspunkt für die Konfiguration und die Cron-Ausführung dient. Es verwendet kein `ObjectModel`, da es direkt bestehende `Currency`-Objekte manipuliert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `HmrcratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist der öffentliche Endpunkt für den Cron-Job. Wenn er über seine URL aufgerufen wird (z. B. `ihrshop.com/module/hmrcrates/cronjob`), löst er die Methode `processUpdateRates()` im Hauptmodul `hmrcrates` aus. Er ist dafür konzipiert, von externen Cron-Diensten oder serverseitigen Cron-Jobs aufgerufen zu werden. Er gibt eine einfache Erfolgs- oder Fehlermeldung aus.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `HmrcratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist ein Platzhalter-Controller, der typischerweise verwendet wird, um einen Standard-Einstiegspunkt für ein Modul bereitzustellen, wenn keine spezifische Aktion angefordert wird. Im Kontext dieses Moduls dient er wahrscheinlich keinem direkten funktionalen Zweck, außer einer Standardroute bereitzustellen, wenn `cronjob.php` nicht explizit aufgerufen wird. Er könnte umleiten oder einfach eine leere Seite anzeigen.
- **Back-Office-Admin-Controller**:

  - Dieses Modul verwendet keine dedizierten `AdminController`-Dateien. Die gesamte Back-Office-Konfiguration wird direkt in der Methode `getContent()` der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Die Kernlogik zum Abrufen und Aktualisieren von Kursen ist in der Hauptmoduldatei `hmrcrates/cronjob.php` gekapselt. Es interagiert direkt mit der integrierten `Currency`-Klasse von PrestaShop, um Wechselkurse zu aktualisieren.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Die Back-Office-Konfiguration basiert auf dem Standard-Back-Office-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Zweck**: Dieses Template wird von der Methode `getContent()` der Hauptmodulklasse (`hmrcrates/cronjob.php`) gerendert, um das Konfigurationsformular des Moduls im PrestaShop-Backoffice anzuzeigen.
    - **Inhalt**: Es enthält typischerweise die HTML-Struktur zur Anzeige der Cron-Job-URL, des Cron-Job-Befehls, des letzten Aktualisierungsstatus und der Schaltfläche „Jetzt aktualisieren“. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. `HMRCRATES_LAST_UPDATE`) in der Standard-PrestaShop-Tabelle `ps_configuration`.
  - Es aktualisiert die Spalte `exchange_rate` in der Tabelle `ps_currency` für relevante Währungen.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert keine expliziten Front-Office-Display-Hooks (wie `displayHeader`, `displayRightColumn`, `displayFooter`), da seine Funktionalität rein Backend-orientiert ist. Sein primärer „Hook“ ist der `action`-Hook, der vom `ModuleFrontController` für den Cron-Job ausgelöst wird.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionModuleInstall` | Während der Modulinstallation | Erstellt Konfigurationseinträge, richtet Initialdaten ein. |
| `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationseinträge. |
| (Implizit) `actionFrontControllerSetMedia` | Wenn ein Front-Controller geladen wird | Wird von diesem Modul nicht explizit verwendet, aber Standard für Module zum Laden von Assets. |
| (Implizit) `actionDispatcher` | Wenn ein Front-Controller versendet wird | Der `ModuleFrontController` `HmrcratesCronjobModuleFrontController` wird versendet, wenn die Cron-URL aufgerufen wird, wodurch die Logik zur Kursaktualisierung ausgelöst wird. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „HM Revenue & Customs (HMRC) - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Konfiguration des Moduls zur Verfügung.
