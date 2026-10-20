---
title: "NBP Wechselkursaktualisierung - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'NBP Wechselkursaktualisierung' von MyPresta.eu."
sidebar:
  label: "NBP Wechselkursaktualisierung - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul NBP currency rates update auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/nbp-currency-rates-update.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/nbp-currency-rates-update/)
>
> ---


# NBP Wechselkursaktualisierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind typischerweise erforderlich und in den meisten modernen Webhosting-Umgebungen Standard. Ihr Hosting muss auch die Einrichtung von Cron-Jobs unterstützen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „NBP Wechselkursaktualisierung“. Sie gelangen zum Hauptkonfigurationsbildschirm.

#### **Cron-Job-URL**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie verwenden werden, um eine automatisierte Aufgabe (einen „Cron-Job“) auf Ihrem Webserver einzurichten. Wenn diese URL aufgerufen wird, verbindet sich das Modul mit den NBP-Servern, ruft die neuesten Wechselkurse ab und aktualisiert diese in Ihrem PrestaShop-Shop.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert.
- **Empfohlener Wert:** Kopieren Sie diese URL genau so, wie sie angezeigt wird.
- **Händlerszenario / Beispiel:** Sie nehmen diese URL und fügen sie in den Abschnitt „Cron-Jobs“ Ihres Hosting-Kontrollpanels (z. B. cPanel, Plesk oder eine benutzerdefinierte Server-Cron-Konfiguration) ein. Dies weist Ihren Server an, diese URL in bestimmten Intervallen (z. B. täglich um 3 Uhr morgens) aufzurufen, wodurch der Währungsaktualisierungsprozess automatisch ausgelöst wird.

#### **Cron-Job-Frequenz**

- **Was diese Einstellung bewirkt:** Dies ist keine Einstellung, die Sie *innerhalb* von PrestaShop ändern, sondern eine Empfehlung, wie oft Sie den Cron-Job Ihres Servers zum Aufruf der URL einrichten sollten.
- **Auswirkung einer Änderung dieser Einstellung:** Dieser Text dient lediglich als Hinweis. Die tatsächliche Häufigkeit wird durch die Cron-Job-Einrichtung Ihres Servers gesteuert.
- **Empfohlener Wert:** „Einmal täglich“ ist für die meisten Shops im Allgemeinen ausreichend, da die NBP-Kurse typischerweise täglich aktualisiert werden.
- **Händlerszenario / Beispiel:** Wenn Sie den Cron-Job Ihres Servers so einstellen, dass er täglich ausgeführt wird, werden die Wechselkurse Ihres Shops einmal alle 24 Stunden aktualisiert, wodurch sichergestellt wird, dass sie immer mit den NBP-Daten übereinstimmen. Eine häufigere Ausführung (z. B. stündlich) ist normalerweise unnötig und könnte Ihren Server oder die NBP-API übermäßig belasten.

#### **Wichtiger Hinweis zu Cron-Jobs**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält wichtige Anweisungen zur Einrichtung des Cron-Jobs auf Ihrem Server. Es wird erklärt, dass Sie auf Ihr Hosting-Kontrollpanel (wie cPanel oder Plesk) zugreifen und einen neuen Cron-Job hinzufügen müssen.
- **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Informationstext. Sie müssen diese Anweisungen außerhalb von PrestaShop befolgen.
- **Empfohlener Wert:** Lesen Sie dies sorgfältig durch und befolgen Sie die Schritte, die Ihr Hosting-Anbieter für die Einrichtung von Cron-Jobs bereitstellt.
- **Händlerszenario / Beispiel:** Ihr Hosting-Anbieter hat einen Abschnitt, der normalerweise „Cron-Jobs“ oder „Geplante Aufgaben“ genannt wird, in dem Sie einen neuen Befehl hinzufügen können. Sie wählen typischerweise eine Häufigkeit (z. B. „Einmal täglich“) und fügen dann die „Cron-Job-URL“ in das Befehlsfeld ein, oft mit `wget -q -O /dev/null` vorangestellt. Wenn Sie unsicher sind, wenden Sie sich an den Support Ihres Hosting-Anbieters.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Cron-Job-URL | (Eindeutige URL) | Die URL zum Auslösen automatischer Währungsaktualisierungen über einen Server-Cron-Job. Kopieren Sie diese für Ihre Server-Einrichtung. |
| Modulkonfiguration | Cron-Job-Frequenz | Einmal täglich | Empfehlung, wie oft der Cron-Job auf Ihrem Server ausgeführt werden sollte, um die Kurse aktuell zu halten. |
| Modulkonfiguration | Anweisungen zur Cron-Job-Einrichtung | N/A | Anleitung zur Konfiguration des Cron-Jobs auf Ihrem Webhosting-Server. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht aktualisiert, obwohl ich den Cron-Job eingerichtet habe. Was soll ich tun?**
A:

1. **Überprüfen Sie die Cron-Job-URL:** Stellen Sie sicher, dass Sie die URL genau von der Modulkonfigurationsseite kopiert und korrekt in die Cron-Job-Einstellungen Ihres Hosting-Kontrollpanels eingefügt haben.
2. **Überprüfen Sie die Cron-Job-Ausführung:** Überprüfen Sie die Cron-Job-Protokolle Ihres Hosting-Anbieters (falls verfügbar), um zu sehen, ob der Cron-Job tatsächlich zur geplanten Zeit ausgeführt wird. Manchmal ist der Befehl möglicherweise falsch oder der Pfad zu `wget` muss angepasst werden.
3. **Manuell testen:** Versuchen Sie, die „Cron-Job-URL“ direkt in Ihrem Webbrowser aufzurufen. Dies sollte eine sofortige Aktualisierung auslösen. Wenn die Kurse nach einem manuellen Besuch aktualisiert werden, liegt das Problem bei der Cron-Job-Einrichtung Ihres Servers, nicht beim Modul selbst.
4. **PrestaShop-Währungen überprüfen:** Stellen Sie sicher, dass die Währungen, die Sie aktualisieren möchten, in PrestaShop aktiviert sind (**International > Währungen**) und dass sie einen gültigen ISO-Code haben, den die NBP erkennen kann (z. B. USD, EUR, GBP).
5. **Cache leeren:** Manchmal kann der PrestaShop-Cache Sie daran hindern, sofortige Änderungen zu sehen. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.

**F: Aktualisiert dieses Modul alle Währungen in meinem Shop?**
A: Es aktualisiert Währungen, für die die NBP Wechselkurse relativ zum PLN bereitstellt. Das Modul ist intelligent genug, um diese Kurse in die Standardwährung Ihres Shops umzurechnen. Wenn Ihre Standardwährung beispielsweise EUR ist und die NBP USD/PLN und EUR/PLN bereitstellt, kann das Modul USD/EUR berechnen. Wenn die NBP keinen Kurs für eine bestimmte Währung bereitstellt, wird der Kurs dieser Währung von diesem Modul nicht aktualisiert.

**F: Kann ich die Aktualisierungsfrequenz auf häufiger als einmal täglich einstellen?**
A: Obwohl Sie den Cron-Job Ihres Servers so konfigurieren können, dass er häufiger (z. B. stündlich) ausgeführt wird, aktualisieren sich die NBP-Wechselkurse typischerweise einmal täglich. Eine häufigere Ausführung des Cron-Jobs als täglich ist normalerweise unnötig und liefert keine aktuelleren Daten, schadet aber auch nicht.

**F: Ich erhalte eine Fehlermeldung, wenn ich versuche, das Modul zu konfigurieren oder wenn der Cron-Job ausgeführt wird.**
A:

1. **PHP-Version überprüfen:** Stellen Sie sicher, dass Ihre PHP-Version innerhalb des unterstützten Bereichs liegt (PHP 5.6 - 8.5).
2. **Server-Konnektivität:** Das Modul muss sich mit der NBP-Website verbinden, um Kurse abzurufen. Stellen Sie sicher, dass Ihr Server über ausgehenden Internetzugang verfügt und nicht durch eine Firewall am Zugriff auf externe URLs gehindert wird.
3. **PrestaShop-Debug-Modus:** Aktivieren Sie den PrestaShop-Debug-Modus (**Erweiterte Einstellungen > Leistung > Debug-Modus**), um detailliertere Fehlermeldungen anzuzeigen, die bei der Problembehebung helfen können. Denken Sie daran, ihn nach der Fehlerbehebung zu deaktivieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `NBP Wechselkursaktualisierung` ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, eine einzige, kritische Aufgabe auszuführen: das Abrufen und Aktualisieren von Wechselkursen von der Nationalbank von Polen (NBP) über einen geplanten Cron-Job. Es folgt einer Standard-PrestaShop-Modulstruktur, die `ModuleFrontController` für seinen Cron-Endpunkt und die Hauptmodulklasse für Konfiguration und Installation nutzt. Die Kernlogik befindet sich in der Datei `cronjob.php`, die sowohl als Hauptmodulklasse als auch als Einstiegspunkt für die Cron-Ausführung dient.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `nbprates/controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `NbpratesCronjobModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Dieser Controller dient als öffentlicher Endpunkt für den Cron-Job. Wenn er über die vom Modul generierte eindeutige URL aufgerufen wird, löst er die Währungsaktualisierungslogik aus. Er gibt keine visuelle Ausgabe aus, sondern führt den Prozess des Abrufens und Aktualisierens der Kurse aus. Er ist so konzipiert, dass er von `wget` oder `curl` von einem Server-Cron-Scheduler aufgerufen wird.
  - `nbprates/controllers/front/index.php`
    - **Klassenname & Elternklasse**: `NbpratesIndexModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Dies ist ein Platzhalter-Controller, der oft in Modulen enthalten ist, um die Verzeichnisauflistung zu verhindern, wenn `index.php` nicht im Verzeichnis `controllers/front` vorhanden ist. Er tut typischerweise nichts weiter, als auf die Startseite umzuleiten oder einen „404 Not Found“-Fehler anzuzeigen. Er enthält keine spezifische Geschäftslogik für dieses Modul.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Die Logik des Moduls ist hauptsächlich in der Hauptmoduldatei (`nbprates/cronjob.php`) enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul verwendet kein benutzerdefiniertes JavaScript.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul verwendet kein benutzerdefiniertes CSS.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `nbprates/views/admin.tpl`
    - **Zweck**: Dieses Template wird von der `getContent()`-Methode der Hauptmodulklasse (`NbpratesCronjob`) gerendert, um das Konfigurationsformular des Moduls im PrestaShop Back Office anzuzeigen.
    - **Inhalt**: Es zeigt typischerweise die „Cron-Job-URL“ und Anweisungen zur Einrichtung des Cron-Jobs an. Es handelt sich um eine statische Anzeige von Informationen und nicht um ein interaktives Formular mit Eingabefeldern.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfiguration (insbesondere das generierte Cron-Token) in der Tabelle `ps_configuration`. Der Schlüssel für das Cron-Token wäre typischerweise `NBP_CRON_TOKEN`.
  - Es aktualisiert vorhandene Wechselkurse in der Tabelle `ps_currency` (insbesondere die Spalte `conversion_rate`).
- **Registrierte Hooks-Tabelle**:
Das Modul registriert sich nicht explizit bei Standard-PrestaShop-Display-Hooks (wie `displayHeader`, `displayFooter` usw.) für die Front-Office-Darstellung. Sein primärer „Hook“ ist der `ModuleFrontController`-Endpunkt, der extern vom Cron-Job des Servers aufgerufen wird.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `install()` | Während der Modulinstallation | Erstellt das eindeutige Cron-Token und speichert es in `ps_configuration`. |
| `uninstall()` | Während der Moduldeinstallation | Löscht das Cron-Token aus `ps_configuration`. |
| `actionFrontControllerSetMedia` | Nicht explizit registriert, aber `ModuleFrontController` handhabt implizit das Laden von Assets, falls vorhanden. | N/A (keine Assets werden von diesem Modul geladen). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „NBP Wechselkursaktualisierung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Integration des Moduls in Ihren PrestaShop-Shop gerne zur Verfügung.
