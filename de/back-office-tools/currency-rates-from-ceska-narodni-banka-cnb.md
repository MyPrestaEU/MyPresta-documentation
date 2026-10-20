---
title: "Wechselkurse der Česká národní banka (CNB) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Wechselkurse der Česká národní banka (CNB)“ von MyPresta.eu."
sidebar:
  label: "Wechselkurse der Česká národní banka (CNB) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Currency rates from Česká národní banka (CNB) auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/currency-rates-from-ceska-narodni-banka-cnb.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/currency-rates-from-ceska-narodni-banka-cnb/)
>
> ---


# Wechselkurse der Česká národní banka (CNB)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen, um auf dessen Einstellungen zuzugreifen. Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul.

#### **Einstellungen & Optionen**

**1. `mypresta_updates` (MyPresta.eu Updates)**

- **Was diese Einstellung bewirkt:** Dies ist eine Standardeinstellung, die in vielen MyPresta.eu-Modulen zu finden ist. Sie steuert, ob das Modul nach Updates von MyPresta.eu sucht und Benachrichtigungen in Ihrem PrestaShop Back Office anzeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul sucht regelmäßig nach neuen Versionen, die auf MyPresta.eu verfügbar sind. Wenn ein Update gefunden wird, sehen Sie möglicherweise eine Benachrichtigung in Ihrem PrestaShop-Admin-Panel, die Sie auffordert, die neuere Version herunterzuladen und zu installieren. Dies hilft Ihnen, mit Fehlerbehebungen und neuen Funktionen auf dem Laufenden zu bleiben.
  - *Wenn deaktiviert (NEIN):* Das Modul sucht nicht nach Updates. Sie erhalten keine Benachrichtigungen über neue Versionen, was bedeutet, dass Sie Ihr MyPresta.eu-Konto manuell auf Updates überprüfen müssten.
- **Empfohlener Wert:** **JA**. Es wird immer empfohlen, Module für Sicherheit, Kompatibilität und neue Funktionen auf dem neuesten Stand zu halten.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihr Modul immer die neueste, stabilste Version ausführt, ohne ständig manuell nachzusehen. Wenn Sie dies aktivieren, erhalten Sie eine Benachrichtigung, wenn ein Update verfügbar ist.

**2. `update_` (Update-Häufigkeit)**

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt, wie oft das Modul versucht, Wechselkurse vom CNB-Feed abzurufen und zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein kürzeres Intervall eingestellt ist (z. B. „Jede Stunde“):* Ihre Wechselkurse werden häufiger aktualisiert, wodurch Ihre Preise sehr aktuell bleiben, was in volatilen Märkten von Vorteil ist. Dies könnte jedoch die Serverlast leicht erhöhen (obwohl dies für diese Art von Operation typischerweise vernachlässigbar ist).
  - *Wenn ein längeres Intervall eingestellt ist (z. B. „Einmal täglich“):* Die Kurse werden seltener aktualisiert. Dies ist im Allgemeinen ausreichend, da die CNB typischerweise tägliche Kurse bereitstellt. Es reduziert die Serverlast.
- **Empfohlener Wert:** **Einmal täglich**. Die CNB veröffentlicht normalerweise tägliche Kurse, daher ist eine häufigere Aktualisierung als einmal täglich oft unnötig und liefert keine neueren Daten.
- **Händlerszenario / Beispiel:** Sie betreiben einen internationalen Shop, in dem Wechselkursschwankungen Ihre Gewinnmargen beeinflussen können. Wenn Sie dies auf „Einmal täglich“ einstellen, stellen Sie sicher, dass Sie immer die neuesten offiziellen Kurse haben, ohne Ihren Server zu überlasten.

**3. `updatev_` (Update-Methode)**

- **Was diese Einstellung bewirkt:** Diese Einstellung definiert, wie das Modul den Aktualisierungsprozess der Wechselkurse auslöst.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Cron Job“ eingestellt:* Das Modul erwartet, dass Sie einen serverseitigen Cron-Job (eine geplante Aufgabe) einrichten, der regelmäßig eine vom Modul bereitgestellte spezifische URL aufruft. Dies ist die zuverlässigste und empfohlene Methode, da sie sicherstellt, dass Updates genau zum geplanten Zeitpunkt erfolgen, auch wenn niemand Ihren Shop besucht.
  - *Wenn auf „Beim Seitenaufruf“ eingestellt:* Das Modul versucht, die Kurse zu aktualisieren, wenn ein Kunde oder Administrator eine beliebige Seite Ihres Shops besucht. Dies ist weniger zuverlässig, da Updates nur erfolgen, wenn Traffic auf Ihre Website trifft, und wenn Ihre Website wenig Traffic hat, können Updates verzögert werden. Es kann auch den ersten Seitenaufruf für einen Besucher leicht verlangsamen, wenn ein Update fällig ist.
- **Empfohlener Wert:** **Cron Job**. Dies ist die robusteste und effizienteste Methode für geplante Aufgaben. Das Modul stellt Ihnen die genaue URL zur Verfügung, die Sie für Ihren Cron-Job verwenden müssen.
- **Händlerszenario / Beispiel:** Sie möchten garantieren, dass die Wechselkurse jeden Morgen um 3 Uhr aktualisiert werden, unabhängig vom Website-Traffic. Wenn Sie dies auf „Cron Job“ einstellen und den Cron Ihres Servers konfigurieren, wird dies zuverlässig erreicht.

**4. `currency_` (Zu aktualisierende Währungen)**

- **Was diese Einstellung bewirkt:** Hiermit können Sie auswählen, welche spezifischen Währungen in Ihrem PrestaShop-Shop ihre Wechselkurse über den CNB-Feed aktualisieren sollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn bestimmte Währungen ausgewählt sind:* Nur die ausgewählten Währungen erhalten ihre Wechselkurse vom Modul aktualisiert. Andere Währungen (falls vorhanden) behalten ihre manuell eingestellten Kurse oder den Standard-Aktualisierungsmechanismus von PrestaShop (falls aktiv). Dies gibt Ihnen eine detaillierte Kontrolle.
  - *Wenn keine Währungen ausgewählt sind (oder alle ausgewählt sind):* Das Modul versucht, alle aktiven Währungen in Ihrem Shop zu aktualisieren, die im CNB-Feed vorhanden sind.
- **Empfohlener Wert:** Wählen Sie **alle Währungen aus, die Sie aktiv für Transaktionen verwenden und die vom CNB-Feed unterstützt werden**. Typischerweise gehören dazu EUR, USD, GBP und andere wichtige Währungen.
- **Händlerszenario / Beispiel:** Ihr Shop akzeptiert Zahlungen in EUR, USD und CZK. Sie möchten, dass die EUR- und USD-Kurse von der CNB aktualisiert werden, aber CZK ist Ihre Standardwährung und benötigt keine externen Updates. Sie würden EUR und USD aus dieser Liste auswählen.

#### **Cron-Job-URL (Wird nach dem Speichern der Einstellungen angezeigt)**

- **Was dies bewirkt:** Nachdem Sie die Moduleinstellungen konfiguriert und gespeichert haben, insbesondere wenn Sie „Cron Job“ als Update-Methode gewählt haben, zeigt das Modul eine eindeutige URL an. Diese URL ist das, was der Cron-Job Ihres Servers aufrufen muss, um den Aktualisierungsprozess auszulösen.
- **Auswirkung der Verwendung dieser URL:** Wenn auf diese URL zugegriffen wird (entweder durch den Cron-Job Ihres Servers oder manuell in einem Browser), führt das Modul seine Logik aus, um die neuesten Wechselkurse von der CNB abzurufen und sie in Ihrer PrestaShop-Datenbank zu aktualisieren.
- **Empfohlene Aktion:** Kopieren Sie diese URL und richten Sie sie als Cron-Job auf Ihrem Hosting-Server ein. Konsultieren Sie die Dokumentation oder den Support Ihres Hosting-Anbieters, wie Sie einen Cron-Job einrichten. Ein typischer Cron-Job könnte so aussehen: `wget -q -O /dev/null "IHRE_CRON_URL_HIER"`.
- **Händlerszenario / Beispiel:** Sie haben die Update-Häufigkeit auf „Einmal täglich“ und die Methode auf „Cron Job“ eingestellt. Das Modul zeigt `https://ihrshop.com/module/cnbrates/cronjob?token=IHR_EINZIGARTIGER_TOKEN` an. Sie würden dann den Cron Ihres Servers so konfigurieren, dass er `wget -q -O /dev/null "https://ihrshop.com/module/cnbrates/cronjob?token=IHR_EINZIGARTIGER_TOKEN"` einmal alle 24 Stunden ausführt.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MyPresta.eu Updates | JA | Steuert Update-Benachrichtigungen von MyPresta.eu. |
| Modulkonfiguration | Update-Häufigkeit | Einmal täglich | Wie oft das Modul neue Kurse von der CNB abruft. |
| Modulkonfiguration | Update-Methode | Cron Job | Wie der Update-Prozess ausgelöst wird (geplante Aufgabe vs. Seitenaufruf). |
| Modulkonfiguration | Zu aktualisierende Währungen | Alle relevanten auswählen | Legt fest, welche Währungen in Ihrem Shop von der CNB aktualisiert werden. |
| Modulkonfiguration | Cron-Job-URL | (Wird nach dem Speichern angezeigt) | Die URL, die für serverseitige Cron-Jobs zur Auslösung von Updates verwendet wird. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht aktualisiert. Was sollte ich zuerst überprüfen?**
A: Der häufigste Grund ist ein Problem mit dem Cron-Job.

1. Gehen Sie zu **Module > Modul-Manager > Konfigurieren** für das CNB Rates Modul.
2. Überprüfen Sie die Einstellung „Update-Methode“. Wenn sie auf „Cron Job“ steht, stellen Sie sicher, dass Sie den Cron-Job auf Ihrem Hosting-Server mit der bereitgestellten URL korrekt eingerichtet haben. Kontaktieren Sie den Support Ihres Hosting-Anbieters, wenn Sie unsicher sind, wie dies zu tun ist.
3. Wenn „Beim Seitenaufruf“ ausgewählt ist, stellen Sie sicher, dass Ihr Shop regelmäßigen Traffic erhält. Wenn nicht, wechseln Sie zu „Cron Job“ für zuverlässigere Updates.
4. Überprüfen Sie auch, ob die Währungen, die Sie aktualisieren möchten, in der Liste „Zu aktualisierende Währungen“ ausgewählt sind.

**F: Funktioniert dieses Modul, wenn meine Standardwährung nicht CZK ist?**
A: Ja, absolut! Das Modul ist so konzipiert, dass es auch funktioniert, wenn Ihre Standardwährung nicht CZK ist. Es ruft Kurse von der CNB ab, die Wechselkurse für verschiedene Währungen gegenüber der CZK bereitstellt. Das Modul konvertiert diese dann intelligent, um die Nicht-Standardwährungen Ihres Shops relativ zu Ihrer tatsächlichen Standardwährung zu aktualisieren.

**F: Wie oft aktualisiert die CNB ihre Kurse?**
A: Die Česká národní banka (CNB) veröffentlicht ihre offiziellen Wechselkurse typischerweise einmal täglich, normalerweise an Werktagen. Daher ist es im Allgemeinen ausreichend, die „Update-Häufigkeit“ Ihres Moduls auf „Einmal täglich“ einzustellen, um die neuesten verfügbaren Daten zu erfassen.

**F: Ich habe das Modul aktualisiert, sehe aber keine Änderungen. Was kann ich tun?**
A: Manchmal kann das Caching-System von PrestaShop die sofortige Anzeige von Änderungen verhindern.

1. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Performance**.
2. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“, falls verfügbar).
3. Aktualisieren Sie Ihren Browser (Strg+F5 oder Cmd+R), um sicherzustellen, dass Sie keine gecachte Version der Seite sehen.

**F: Kann ich ein Update manuell auslösen?**
A: Ja, wenn Ihre „Update-Methode“ auf „Cron Job“ eingestellt ist, können Sie die Cron-Job-URL (die in der Modulkonfiguration angezeigt wird) manuell in Ihrem Webbrowser aufrufen. Dies löst ein sofortiges Update aus. Dies ist jedoch nur zum Testen/Fehlerbeheben gedacht; für regelmäßige Updates verlassen Sie sich auf den automatisierten Cron-Job.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Wechselkurse der Česká národní banka (CNB)“ ist ein leichtgewichtiges PrestaShop-Modul, das für eine einzige, fokussierte Aufgabe entwickelt wurde: das Abrufen und Aktualisieren von Wechselkursen. Es nutzt hauptsächlich einen Front-Office-Controller, um einen Cron-Job-Endpunkt bereitzustellen, der geplante, automatisierte Updates ermöglicht. Das Modul führt keine neuen Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, sondern stützt sich stattdessen auf PrestaShops vorhandene `Currency`-Klasse und `Configuration` für seine Einstellungen. Es folgt einer grundlegenden PrestaShop-Modulstruktur und integriert sich mit den Methoden `install()` und `uninstall()` für die Einrichtung und Bereinigung.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `CnbratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist der Kern der Modulautomatisierung. Er antwortet auf Anfragen an die Cron-Job-URL (z. B. `ihrshop.com/module/cnbrates/cronjob?token=...`). Seine Methode `initContent()` (oder eine ähnliche Lebenszyklusmethode) enthält die Logik, um:
      1. Den `token`-Parameter gegen die gespeicherte Konfiguration zu validieren, um unbefugten Zugriff zu verhindern.
      2. Die neuesten Wechselkurse aus dem CNB-XML-Feed abzurufen (typischerweise `https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml`).
      3. Die XML-Daten zu parsen.
      4. Die konfigurierten Währungen in PrestaShop zu durchlaufen.
      5. Für jede ausgewählte Währung ihren neuen Wechselkurs basierend auf den CNB-Daten (die normalerweise relativ zur CZK sind) und der Standardwährung des Shops zu berechnen.
      6. Das Feld `exchange_rate` für das entsprechende `Currency`-Objekt in der Tabelle `ps_currency` zu aktualisieren.
      7. Eine einfache Erfolgs- oder Fehlermeldung auszugeben, hauptsächlich für die Cron-Job-Protokollierung.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `CnbratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist ein Platzhalter- oder Fallback-Controller. In vielen Modulen dient ein `index.php`-Front-Controller als Standard-Einstiegspunkt, wenn keine spezifische Aktion angefordert wird. Für dieses Modul besteht seine Hauptfunktion wahrscheinlich darin, zur Startseite umzuleiten oder eine einfache Nachricht anzuzeigen, da die Hauptfunktionalität von `cronjob.php` behandelt wird. Es enthält keine signifikante Geschäftslogik für Währungsaktualisierungen.
- **Back-Office-Admin-Controller**: Keine. Die Modulkonfiguration wird vollständig innerhalb von `cnbrates.php` über `getContent()` gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es gibt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` für dieses Modul. Das Modul interagiert direkt mit PrestaShops Kernklassen `Currency` und `Configuration` für die Datenverwaltung.

### 4.4 JavaScript-Assets (`views/js/`)

Es gibt keine benutzerdefinierten JavaScript-Dateien in diesem Modul. Die gesamte Funktionalität ist serverseitiges PHP.

### 4.5 CSS-Stylesheets (`views/css/`)

Es gibt keine benutzerdefinierten CSS-Dateien in diesem Modul. Das Modul führt keine visuellen Front-Office-Elemente oder komplexe Back-Office-Stile über Standard-PrestaShop-Formularelemente hinaus ein.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine. Das Modul zeigt keine Inhalte über Hooks an.
- **Admin-Templates (`views/templates/admin/`)**:
  - `views/admin.tpl`
    - **Zweck**: Dieses Template wird von der Methode `getContent()` in `cnbrates.php` gerendert, um das Konfigurationsformular des Moduls im PrestaShop Back Office anzuzeigen.
    - **Inhalt**: Es enthält die HTML-Struktur für die in Abschnitt 4.1 beschriebenen Einstellungen, einschließlich Eingabefeldern für Update-Häufigkeit, Update-Methode, Währungsauswahl und die Anzeige der Cron-Job-URL. Es verwendet Standard-PrestaShop-Formularhelfer und -Stile.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt **keine** benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in PrestaShops Tabelle `ps_configuration`. Wichtige Konfigurationsschlüssel sind:
    - `CNBRATES_UPDATE_FREQUENCY`
    - `CNBRATES_UPDATE_METHOD`
    - `CNBRATES_CURRENCIES` (wahrscheinlich eine durch Kommas getrennte Liste von Währungs-IDs)
    - `CNBRATES_CRON_TOKEN` (ein eindeutiger Token für die Cron-Job-Sicherheit)
    - `MYPRESTA_UPDATES_CNBRATES` (für MyPresta.eu-Update-Prüfungen)
  - Es aktualisiert die Spalte `exchange_rate` in der Tabelle `ps_currency` für ausgewählte Währungen.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert die folgenden Hooks, hauptsächlich für seine eigene Lebenszyklusverwaltung und potenziell für Update-Prüfungen, anstatt Inhalte anzuzeigen:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Bei jedem Seitenaufruf im Front Office (vor der HTML-Ausgabe). | Oft für JS/CSS-Einbindung verwendet, oder in diesem Fall potenziell für die Update-Methode „Beim Seitenaufruf“, falls konfiguriert, oder für MyPresta.eu-Update-Prüfungen. |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte des Front Office. | Wird von diesem Modul nicht zur Inhaltsanzeige verwendet, möglicherweise eine Legacy-Hook-Registrierung oder für interne Prüfungen. |
| `displayLeftColumn` | Rendert Inhalte in der linken Spalte des Front Office. | Wird von diesem Modul nicht zur Inhaltsanzeige verwendet, möglicherweise eine Legacy-Hook-Registrierung oder für interne Prüfungen. |
| `displayFooter` | Rendert Inhalte in der Fußzeile des Front Office. | Wird von diesem Modul nicht zur Inhaltsanzeige verwendet, möglicherweise eine Legacy-Hook-Registrierung oder für interne Prüfungen. |
| `displayBackOfficeHeader` | Bei jedem Seitenaufruf im Back Office. | Wird verwendet, um modulspezifisches CSS/JS für die Konfigurationsseite einzubinden oder Update-Benachrichtigungen von MyPresta.eu anzuzeigen. |
| `actionAdminCurrenciesControllerSaveAfter` | Nachdem eine Währung im Back Office gespeichert wurde. | Könnte verwendet werden, um Währungseinstellungen neu zu bewerten oder ein Update auszulösen, wenn sich der Status einer Währung ändert. |
| `actionAdminCurrenciesControllerDeleteAfter` | Nachdem eine Währung im Back Office gelöscht wurde. | Könnte verwendet werden, um die gelöschte Währung aus der Update-Liste des Moduls zu entfernen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „Wechselkurse der Česká národní banka (CNB)“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Integration des Moduls zur Verfügung.
