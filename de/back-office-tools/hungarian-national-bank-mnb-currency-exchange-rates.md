---
title: "Ungarische Nationalbank (MNB) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Ungarische Nationalbank (MNB) - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Ungarische Nationalbank (MNB) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Hungarian National Bank (MNB) - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/hungarian-national-bank-mnb-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/hungarian-national-bank-mnb-currency-exchange-rates/)
>
> ---


# Ungarische Nationalbank (MNB) - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die externe API-Kommunikation erforderlich, was bei Wechselkursmodulen üblich ist. Stellen Sie sicher, dass Ihre Hosting-Umgebung diese unterstützt.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls. Hier legen Sie fest, wie das Modul Wechselkurse abruft und anwendet.

#### **Einstellungen & Optionen**

Die Konfigurationsseite für das Modul „Ungarische Nationalbank (MNB) - Wechselkurse“ präsentiert typischerweise ein Formular mit verschiedenen Optionen zur Steuerung seines Verhaltens. Während spezifische Feldnamen leicht variieren können, dreht sich die Kernfunktionalität um die Aktivierung des Aktualisierungsprozesses und dessen mögliche Zeitplanung.

1. **MNB-Wechselkursaktualisierungen aktivieren**

   - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der automatischen Wechselkursaktualisierungen von der Ungarischen Nationalbank.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (JA):* Das Modul ruft regelmäßig die neuesten Wechselkurse von der MNB ab und wendet sie auf die konfigurierten Währungen Ihres Shops an. Dies stellt sicher, dass Ihre Preise immer aktuell sind.
     - *Wenn deaktiviert (NEIN):* Das Modul stoppt das Abrufen und Anwenden von MNB-Wechselkursen. Die Wechselkurse Ihres Shops bleiben so, wie sie zuletzt festgelegt wurden (entweder manuell oder vom Modul, bevor es deaktiviert wurde).
   - **Empfohlener Wert:** JA
   - **Händlerszenario / Beispiel:** Wenn Ihr Shop die neuesten MNB-Wechselkurse für HUF, EUR, USD usw. automatisch widerspiegeln soll, müssen Sie diese Einstellung aktivieren. Wenn Sie die Kurse lieber manuell verwalten oder ein anderes System verwenden möchten, würden Sie sie deaktivieren.
2. **Cron-Job-URL (für automatische Updates)**

   - **Was diese Einstellung bewirkt:** Dieses Feld zeigt eine eindeutige URL an, die Sie verwenden können, um einen „Cron-Job“ auf Ihrem Webserver einzurichten. Ein Cron-Job ist eine geplante Aufgabe, die Ihrem Server anweist, diese URL in regelmäßigen Abständen zu besuchen, wodurch das Modul zur automatischen Aktualisierung der Wechselkurse ausgelöst wird.
   - **Auswirkung der Änderung dieser Einstellung:** Dies ist keine Einstellung, die Sie direkt ändern, sondern eine URL, die Sie kopieren.
     - *Wenn der Cron-Job eingerichtet ist:* Ihr Server ruft diese URL regelmäßig auf, und das Modul führt seinen Aktualisierungsprozess im Hintergrund aus, ohne dass Sie etwas tun müssen.
     - *Wenn der Cron-Job NICHT eingerichtet ist:* Sie müssten diese URL manuell in Ihrem Browser besuchen (oder auf eine Schaltfläche „Jetzt aktualisieren“ klicken, falls verfügbar), um eine Aktualisierung auszulösen. Dies wird für den regelmäßigen Gebrauch nicht empfohlen.
   - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie einen Cron-Job in Ihrem Hosting-Panel (z. B. cPanel, Plesk oder Server-Befehlszeile) ein, der mindestens einmal täglich oder häufiger ausgeführt wird, wenn Ihr Geschäft dies erfordert.
   - **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse jeden Morgen um 3 Uhr aktualisiert werden. Sie würden diese URL kopieren, zum Abschnitt „Cron-Jobs“ Ihres Hosting-Kontrollpanels gehen und einen neuen Cron-Job erstellen, der `wget -O /dev/null -q "IHRE_CRON_JOB_URL_HIER"` (oder einen ähnlichen Befehl) täglich um 3 Uhr ausführt.
3. **Letzte Aktualisierungszeit** (Informationsanzeige)

   - **Was diese Einstellung bewirkt:** Dies ist ein nur zur Anzeige bestimmtes Feld, das Ihnen anzeigt, wann die Wechselkurse zuletzt erfolgreich vom Modul aktualisiert wurden.
   - **Auswirkung der Änderung dieser Einstellung:** Dies ist keine konfigurierbare Einstellung. Sie liefert lediglich Feedback zur Aktivität des Moduls.
   - **Empfohlener Wert:** N/A (informativ)
   - **Händlerszenario / Beispiel:** Sie können diesen Zeitstempel schnell überprüfen, um zu bestätigen, dass Ihr Cron-Job korrekt ausgeführt wird und die Kurse wie erwartet aktualisiert werden. Wenn die Zeit alt ist, deutet dies auf ein Problem mit Ihrer Cron-Job-Einrichtung hin.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MNB-Wechselkursaktualisierungen aktivieren | JA | Aktiviert/deaktiviert das automatische Abrufen und Anwenden von MNB-Wechselkursen. |
| Modulkonfiguration | Cron-Job-URL | N/A (Kopieren & Konfigurieren) | URL zum Einrichten einer geplanten Aufgabe (Cron-Job) für automatische Kursaktualisierungen. |
| Modulkonfiguration | Letzte Aktualisierungszeit | N/A (Informativ) | Zeigt den Zeitstempel der letzten erfolgreichen Wechselkursaktualisierung an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht aktualisiert. Was soll ich tun?**
A1:

1. **„MNB-Wechselkursaktualisierungen aktivieren“ prüfen:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf JA gesetzt ist.
2. **Cron-Job-Einrichtung überprüfen:** Der häufigste Grund für Nicht-Updates ist ein falsch konfigurierter Cron-Job.
   - Stellen Sie sicher, dass Sie die genaue „Cron-Job-URL“ aus dem Modul kopiert haben.
   - Überprüfen Sie Ihr Hosting-Kontrollpanel (cPanel, Plesk usw.) auf die Cron-Job-Einstellungen.
   - Bestätigen Sie, dass der Befehl korrekt ist (z. B. `wget -O /dev/null -q "IHRE_CRON_JOB_URL"`).
   - Überprüfen Sie den Zeitplan (z. B. `* * * * *` für jede Minute, `0 3 * * *` für täglich um 3 Uhr morgens).
   - Suchen Sie in Ihrem Hosting-Panel nach Fehlerprotokollen im Zusammenhang mit dem Cron-Job.
3. **„Letzte Aktualisierungszeit“ prüfen:** Wenn dieser Zeitstempel alt ist, bestätigt dies, dass der Cron-Job nicht ausgeführt wird.
4. **Serverkonnektivität:** Stellen Sie sicher, dass Ihr Server ausgehende Verbindungen zu externen Websites (wie der MNB-API) herstellen kann. Manchmal können Firewalls oder Sicherheitseinstellungen dies blockieren. Kontaktieren Sie Ihren Hosting-Anbieter, wenn Sie dies vermuten.

**F2: Ich habe das Modul aktiviert, aber einige Währungen werden nicht aktualisiert.**
A2:

1. **Währungsaktivierung:** Gehen Sie im PrestaShop Back Office zu **International > Währungen**. Stellen Sie sicher, dass die Währungen, die aktualisiert werden sollen, aktiviert (aktiv) sind. Das Modul aktualisiert nur aktive Währungen.
2. **MNB-Unterstützung:** Die MNB stellt Kurse für bestimmte Währungen bereit. Wenn eine Währung von der MNB nicht unterstützt wird, kann das Modul sie nicht aktualisieren. Möglicherweise müssen Sie die Kurse für solche Währungen manuell festlegen oder ein anderes Modul dafür verwenden.

**F3: Mein benutzerdefiniertes Theme zeigt die Preise nach dem Update nicht korrekt an.**
A3: Dieses Modul aktualisiert hauptsächlich die *Daten* (Wechselkurse) in Ihrer PrestaShop-Datenbank. Es beeinflusst nicht direkt, wie Preise von Ihrem Theme *angezeigt* werden. Wenn Sie Anzeigeprobleme feststellen:

1. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“).
2. **Theme-Anpassung:** Wenn Ihr Theme eine stark angepasste Preis-Anzeigelogik hat, könnte dies stören. Überprüfen Sie die Dokumentation Ihres Themes oder kontaktieren Sie Ihren Theme-Entwickler.
3. **Browser-Cache:** Bitten Sie Ihre Kunden, ihren Browser-Cache zu leeren oder einen anderen Browser zu verwenden, um clientseitige Cache-Probleme auszuschließen.

**F4: Kann ich einen Wechselkurs manuell überschreiben, nachdem das Modul ihn aktualisiert hat?**
A4: Ja, das können Sie. Nachdem das Modul ausgeführt wurde, werden die Kurse in der PrestaShop-Datenbank gespeichert. Sie können zu **International > Währungen** gehen, eine bestimmte Währung bearbeiten und ihren Wechselkurs manuell anpassen. Beachten Sie jedoch, dass das Modul beim nächsten Ausführen des Cron-Jobs Ihre manuellen Änderungen mit den neuesten MNB-Daten überschreibt. Wenn Sie eine dauerhafte manuelle Kontrolle über eine bestimmte Währung benötigen, sollten Sie die Updates des Moduls für diese Währung deaktivieren (falls das Modul eine solche granulare Einstellung bietet, was selten ist) oder das Modul vollständig deaktivieren und alle Kurse manuell verwalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Ungarische Nationalbank (MNB) - Wechselkurse“ folgt einer Standard-PrestaShop-Modularchitektur, die sich hauptsächlich auf die Hintergrundverarbeitung konzentriert. Es nutzt die `Module`-Klasse von PrestaShop für Installation und Konfiguration und `ModuleFrontController` für die Ausführung des Cron-Jobs. Die Kernlogik umfasst das Senden einer HTTP-Anfrage an die offizielle Wechselkurs-API der MNB (wahrscheinlich ein XML-Feed), das Parsen der Antwort und anschließend das Aktualisieren der Tabelle `ps_currency` in der PrestaShop-Datenbank.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `mnbrates/controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `MnbratesCronjobModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Dieser Controller ist der Einstiegspunkt für den geplanten Cron-Job. Wenn seine URL aufgerufen wird (z. B. `ihrshop.com/module/mnbrates/cronjob`), löst er die Kernlogik des Moduls aus, um Wechselkurse abzurufen und zu aktualisieren. Er verarbeitet typischerweise die HTTP-Anfrage, ruft die Update-Methode des Hauptmoduls auf und gibt eine einfache Erfolgs-/Fehlermeldung oder keine Ausgabe zurück (für die stille Cron-Ausführung).
  - `mnbrates/controllers/front/index.php`
    - **Klassenname & Elternklasse**: `MnbratesIndexModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Dies ist ein Standard-Platzhalter-Controller, der oft in Modulen enthalten ist. In vielen Fällen leitet er möglicherweise einfach zur Startseite weiter oder dient als Fallback. Für dieses spezifische Modul besteht sein Hauptzweck wahrscheinlich darin, die Verzeichnisauflistung zu verhindern, wenn jemand versucht, direkt auf `/module/mnbrates/` zuzugreifen, oder es könnte eine rudimentäre Datei sein. Es ist unwahrscheinlich, dass es die Kern-Geschäftslogik für Wechselkursaktualisierungen enthält.
- **Back-Office-Admin-Controller**:

  - Es sind keine dedizierten Admin-Controller (`controllers/admin/`) identifiziert. Dies bedeutet, dass die gesamte Back-Office-Konfiguration direkt in der `getContent()`-Methode der Hauptmoduldatei gehandhabt wird.

### 4.3 Kernklassen & Modelle (`classes/`)

Es sind keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` identifiziert. Dies deutet darauf hin, dass das Modul seine Operationen wahrscheinlich direkt in der Hauptmoduldatei `cronjob.php` ausführt, möglicherweise unter Verwendung des PrestaShop-Kern-`Currency`-`ObjectModel` zur Aktualisierung der Kurse.

### 4.4 JavaScript-Assets (`views/js/`)

Es sind keine JavaScript-Dateien identifiziert. Dies bestätigt den Backend-fokussierten Charakter des Moduls, ohne interaktive Front-Office-Komponenten oder komplexe Back-Office-Formulare, die dynamisches JS erfordern.

### 4.5 CSS-Stylesheets (`views/css/`)

Es sind keine CSS-Dateien identifiziert. Dies deutet darauf hin, dass das Modul keine benutzerdefinierten Stile für das Front-Office oder Back-Office einführt. Die Back-Office-Konfiguration erbt die Standard-Admin-Theme-Stile von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `mnbrates/views/admin.tpl`
    - **Zweck**: Dieses Template wird von der `getContent()`-Methode der Hauptmoduldatei (`mnbrates/cronjob.php`) gerendert. Es definiert die Struktur und den Inhalt der Konfigurationsseite des Moduls im PrestaShop Back Office. Es enthält die Formularelemente zum Aktivieren/Deaktivieren von Updates, zum Anzeigen der Cron-Job-URL und zum Anzeigen des Zeitstempels der letzten Aktualisierung.
- **Hook-Templates (`views/templates/hook/`)**: Keine identifiziert.
- **Front-Office-Templates (`views/templates/front/`)**: Keine identifiziert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es interagiert mit der PrestaShop-Kerntabelle `ps_currency`, um das Feld `conversion_rate` für jede Währung zu aktualisieren.
  - Konfigurationseinstellungen (wie `PS_MNBRATES_ENABLED`, `PS_MNBRATES_LAST_UPDATE`) werden in der Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert Hooks wahrscheinlich während seiner `install()`-Methode. Angesichts seiner Funktionalität ist der wichtigste Hook für den Cron-Job, der von einem Front-Controller gehandhabt wird. Andere Hooks könnten zu Informationszwecken oder zur Sicherstellung der Kompatibilität dienen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich aller Front-Office-Seiten gerendert. | Unwahrscheinlich für die Kernlogik verwendet, möglicherweise zum Hinzufügen eines Meta-Tags oder eines sehr einfachen JS/CSS (obwohl keines identifiziert wurde). |
| `displayRightColumn` | Wird in der rechten Spalte von Seiten gerendert, wo sie verfügbar ist. | Unwahrscheinlich für die Kernlogik verwendet, möglicherweise für einen kleinen Informationsblock, wenn das Modul eine Front-Office-Komponente hätte. |
| `displayLeftColumn` | Wird in der linken Spalte von Seiten gerendert, wo sie verfügbar ist. | Ähnlich wie `displayRightColumn`. |
| `displayFooter` | Wird im Footer aller Front-Office-Seiten gerendert. | Ähnlich wie `displayHeader`, aber am unteren Ende. |
| `displayProductExtraContent` | Rendert zusätzlichen Inhalt auf der Produktseite. | Unwahrscheinlich für dieses Modul. |
| `actionModuleInstall` | Wird ausgeführt, wenn ein Modul installiert wird. | Registriert notwendige Hooks und setzt Standardkonfigurationswerte. |
| `actionModuleUninstall` | Wird ausgeführt, wenn ein Modul deinstalliert wird. | Bereinigt Konfigurationswerte und deregistriert Hooks. |
| `actionModuleUpdate` | Wird ausgeführt, wenn ein Modul aktualisiert wird. | Behandelt Schemaänderungen oder Konfigurationsmigrationen zwischen Versionen. |
| (Implizit) `frontController` Dispatch | Wenn `mnbrates/controllers/front/cronjob.php` aufgerufen wird. | Löst die Hauptlogik zur Aktualisierung der Wechselkurse aus. Dies ist der primäre „Hook“ für den Cron-Job. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Ungarische Nationalbank (MNB) - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul optimal funktioniert und Ihr Shop von den aktuellsten Funktionen und der besten Kompatibilität profitiert.
