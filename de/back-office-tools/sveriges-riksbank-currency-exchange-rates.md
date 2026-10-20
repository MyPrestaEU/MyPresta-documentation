---
title: "Sveriges Riksbank - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Sveriges Riksbank - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Sveriges Riksbank - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Sveriges Riksbank - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/sveriges-riksbank-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/sveriges-riksbank-currency-exchange-rates/)
>
> ---


# Sveriges Riksbank - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für externe API-Aufrufe erforderlich, die in den meisten modernen Hosting-Umgebungen Standard sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Hauptseite der Moduleinstellungen zuzugreifen. Hier legen Sie fest, wie das Modul Wechselkurse abruft und anwendet.

#### **Allgemeine Einstellungen**

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul ist aktiv, und sein Cron-Job sowie die Logik zur Kursaktualisierung funktionieren gemäß Ihren anderen Einstellungen.
    - *Wenn deaktiviert:* Das Modul ist inaktiv, und es erfolgen keine automatischen Kursaktualisierungen. Ihre Währungskurse bleiben so, wie sie zuletzt festgelegt wurden (entweder manuell oder durch eine frühere Modulaktualisierung).
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul gerade einrichten oder Fehler beheben, können Sie es vorübergehend deaktivieren. Für den normalen Betrieb sollte es immer aktiviert sein.
- **Cron-Job-URL:**

  - **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie als „Cron-Job“ auf Ihrem Webhosting-Server einrichten müssen. Ein Cron-Job ist eine geplante Aufgabe, die Ihrem Server mitteilt, diese URL in regelmäßigen Abständen (z.B. einmal täglich) zu besuchen. Wenn die URL besucht wird, ruft das Modul automatisch die neuesten Wechselkurse ab und aktualisiert sie.
  - **Auswirkung der Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert. Die Auswirkung ergibt sich aus der *Verwendung* dieser URL in Ihrem Hosting-Panel.
    - *Wenn korrekt als Cron-Job eingerichtet:* Ihre Wechselkurse werden automatisch in der angegebenen Häufigkeit (z.B. täglich) aktualisiert.
    - *Wenn nicht als Cron-Job eingerichtet:* Die Kurse werden nicht automatisch aktualisiert. Sie müssten diese URL manuell in Ihrem Browser besuchen, um eine Aktualisierung auszulösen, was den Zweck der Automatisierung zunichtemacht.
  - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als täglichen Cron-Job auf Ihrem Server ein.
  - **Händlerszenario / Beispiel:** Sie würden dies typischerweise so einstellen, dass es einmal alle 24 Stunden ausgeführt wird, um sicherzustellen, dass Ihre Kurse immer aktuell sind. Konsultieren Sie die Dokumentation oder den Support Ihres Hosting-Anbieters, wie Sie einen Cron-Job einrichten (oft in cPanel oder Plesk unter „Cron-Jobs“ oder „Geplante Aufgaben“ zu finden).

#### **Währungsspezifische Einstellungen**

Unter den allgemeinen Einstellungen sehen Sie eine Liste aller aktiven Währungen in Ihrem PrestaShop-Store. Für jede Währung können Sie spezifische Einstellungen konfigurieren:

- **Währungsname (z.B. Euro, US-Dollar):**

  - **Was diese Einstellung bewirkt:** Identifiziert die Währung, die Sie konfigurieren.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist nur eine Bezeichnung; Sie können den Währungsnamen hier nicht ändern.
- **Aufschlag / Abschlag (%):**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, eine prozentuale Anpassung des von der Sveriges Riksbank abgerufenen Wechselkurses vorzunehmen.
    - Ein **positiver Wert (Aufschlag)** erhöht den Wechselkurs, was bedeutet, dass Sie mehr der Fremdwährung für Ihre Basiswährung erhalten. Dies ist nützlich, um Transaktionsgebühren zu decken oder Ihre Gewinnmarge zu erhöhen.
    - Ein **negativer Wert (Abschlag)** verringert den Wechselkurs, was bedeutet, dass Sie weniger der Fremdwährung erhalten. Dies könnte für Werbezwecke verwendet werden oder wenn Sie Kunden einen etwas besseren Kurs anbieten möchten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 0 gesetzt:* Der Wechselkurs entspricht genau dem von der Sveriges Riksbank bereitgestellten Kurs.
    - *Wenn auf 2 gesetzt (Aufschlag):* Wenn der Riksbank-Kurs 1 EUR = 10 SEK beträgt, verwendet Ihr Shop mit einem Aufschlag von 2 % 1 EUR = 10,20 SEK. Das bedeutet, wenn ein Kunde in EUR bezahlt, erhalten Sie effektiv mehr SEK.
    - *Wenn auf -1 gesetzt (Abschlag):* Wenn der Riksbank-Kurs 1 EUR = 10 SEK beträgt, verwendet Ihr Shop mit einem Abschlag von 1 % 1 EUR = 9,90 SEK. Das bedeutet, wenn ein Kunde in EUR bezahlt, erhält er einen etwas besseren Kurs.
  - **Empfohlener Wert:** Hängt von Ihrer Geschäftsstrategie ab. Eine gängige Praxis ist es, einen kleinen Aufschlag (z.B. 1-3 %) hinzuzufügen, um Zahlungs-Gateway-Gebühren und Währungsumrechnungskosten zu decken.
  - **Händlerszenario / Beispiel:** Wenn Ihr Zahlungsabwickler eine Gebühr von 1,5 % für die Umrechnung von EUR in SEK berechnet, könnten Sie einen Aufschlag von 2 % für EUR festlegen, um diese Gebühr zu decken und einen kleinen Gewinn zu erzielen.

#### **Speichern-Schaltfläche**

- **Was diese Schaltfläche bewirkt:** Speichert alle Änderungen, die Sie auf der Konfigurationsseite vorgenommen haben.
- **Auswirkung des Klickens auf diese Schaltfläche:** Ihre neuen Einstellungen (aktivieren/deaktivieren, Aufschlag-/Abschlagprozentsätze) werden angewendet. Beim nächsten Ausführen des Cron-Jobs oder wenn Sie eine Aktualisierung manuell auslösen, werden diese neuen Einstellungen verwendet.
- **Empfohlene Aktion:** Klicken Sie immer auf „Speichern“, nachdem Sie Änderungen vorgenommen haben.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren | JA | Aktiviert/deaktiviert die automatischen Kursaktualisierungen des Moduls. |
| Modulkonfiguration | Cron-Job-URL | (Generierte URL) | URL, die als geplante Aufgabe auf Ihrem Server für automatische Aktualisierungen eingerichtet werden muss. |
| Modulkonfiguration | Aufschlag / Abschlag (%) (pro Währung) | 0 | Passt den abgerufenen Wechselkurs um einen Prozentsatz an, um Gebühren zu decken oder den Gewinn zu verwalten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht automatisch aktualisiert. Was sollte ich überprüfen?**
A1:

- **Ist das Modul aktiviert?** Gehen Sie zu Module > Modul-Manager > Sveriges Riksbank - Wechselkurse und stellen Sie sicher, dass „Modul aktivieren“ auf JA gesetzt ist.
- **Ist der Cron-Job korrekt eingerichtet?** Überprüfen Sie Ihr Hosting-Kontrollpanel (cPanel, Plesk usw.), um sicherzustellen, dass die in der Modulkonfiguration angegebene Cron-Job-URL korrekt eingegeben und zur Ausführung geplant ist. Stellen Sie sicher, dass der Befehl korrekt ist (z.B. `wget -q -O /dev/null "IHRE_CRON_URL"` oder `curl -s "IHRE_CRON_URL"`).
- **Gibt es Fehler beim manuellen Besuch der Cron-Job-URL?** Versuchen Sie, die Cron-Job-URL in Ihren Browser einzufügen. Wenn Sie eine Fehlermeldung sehen, könnte dies auf ein Serverproblem oder ein Problem mit der Verbindung des Moduls zur Sveriges Riksbank hinweisen.
- **Serverkonnektivität:** Stellen Sie sicher, dass Ihr Server ausgehende Verbindungen zu externen Websites (API der Sveriges Riksbank) herstellen kann. Manchmal können Firewalls dies blockieren. Kontaktieren Sie Ihren Hosting-Anbieter, wenn Sie dies vermuten.

**F2: Ich habe die Aufschlagsprozentsätze aktualisiert, aber die Preise in meinem Shop haben sich nicht geändert.**
A2:

- **Haben Sie die Einstellungen gespeichert?** Klicken Sie immer auf die Schaltfläche „Speichern“, nachdem Sie Änderungen auf der Modulkonfigurationsseite vorgenommen haben.
- **Ist der Cron-Job seit dem Speichern ausgeführt worden?** Die Änderungen werden erst wirksam, nachdem das Modul seinen nächsten Aktualisierungszyklus durchgeführt hat. Sie können entweder auf Ihren geplanten Cron-Job warten oder eine Aktualisierung manuell auslösen, indem Sie die Cron-Job-URL in Ihrem Browser besuchen.
- **PrestaShop-Cache leeren:** Manchmal kann der PrestaShop-Cache alte Daten enthalten. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.

**F3: Die Wechselkurse scheinen falsch zu sein oder entsprechen nicht dem, was ich von der Sveriges Riksbank erwarte.**
A3:

- **Überprüfen Sie Ihre Aufschlag-/Abschlag-Einstellungen:** Stellen Sie sicher, dass Sie nicht versehentlich einen hohen Aufschlag- oder Abschlagsprozentsatz festgelegt haben, der die Kurse verzerrt.
- **Überprüfen Sie die offiziellen Kurse der Sveriges Riksbank:** Vergleichen Sie die Kurse in Ihrem Shop (nach einer Aktualisierung) mit den offiziellen Kursen, die auf der Website der Sveriges Riksbank veröffentlicht sind, um festzustellen, ob es eine Diskrepanz gibt.
- **Basiswährung des Moduls:** Das Modul ruft Kurse relativ zu SEK ab. Stellen Sie sicher, dass die Standardwährung Ihres PrestaShop korrekt eingerichtet ist, wenn Sie eine andere Basis erwarten.

**F4: Funktioniert dieses Modul mit meinem benutzerdefinierten Theme?**
A4: Ja, dieses Modul arbeitet vollständig im Hintergrund und fügt keine visuellen Elemente hinzu oder ändert keine Templates im Front-Office. Daher ist es vollständig kompatibel mit jedem PrestaShop-Theme, ob benutzerdefiniert oder Standard. Seine Funktion ist rein datengesteuert (Aktualisierung von Wechselkursen).

**F5: Wie füge ich eine neue Währung zu meinem Shop hinzu, damit dieses Modul sie verwalten kann?**
A5:

1. Gehen Sie in Ihrem PrestaShop Back Office zu **International > Währungen**.
2. Klicken Sie auf „Neue Währung hinzufügen“ (oder das Plus-Symbol).
3. Geben Sie die Details für die neue Währung ein (ISO-Code, Symbol, Wechselkurs relativ zu Ihrer Standardwährung).
4. Sobald hinzugefügt und aktiviert, erscheint die neue Währung auf der Konfigurationsseite des Moduls „Sveriges Riksbank - Wechselkurse“, sodass Sie ihren Aufschlag/Abschlag festlegen können.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Sveriges Riksbank - Wechselkurse“ arbeiten.

### 4.1 Architekturübersicht

Das Modul folgt einer Standard-PrestaShop-Modularchitektur, die sich hauptsächlich auf die Back-Office-Konfiguration und die Front-Office-Cron-Job-Ausführung konzentriert. Es nutzt das PrestaShop-Konfigurationssystem zur Speicherung von Einstellungen und `ModuleFrontController` zur Bearbeitung der Cron-Job-Anfrage. Die Kernlogik befindet sich in der Hauptmoduldatei, die Installation, Deinstallation und die `getContent()`-Methode für das Konfigurationsformular handhabt. Die Hauptfunktion des Moduls besteht darin, externe Daten (Währungskurse) abzurufen und die Daten des PrestaShop `Currency`-Objekts zu aktualisieren.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind öffentlich zugänglich, hauptsächlich für die Cron-Job-Funktionalität.

- **`srrates/controllers/front/cronjob.php`**

  - **Klassenname & Elternklasse:** `SrratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der entscheidende Controller für die automatischen Währungsaktualisierungen. Wenn auf diese URL zugegriffen wird (typischerweise durch einen serverseitigen Cron-Job), löst er die Logik des Moduls aus, um die neuesten Wechselkurse von der Sveriges Riksbank abzurufen und sie in der PrestaShop-Datenbank zu aktualisieren. Er gibt keine visuelle Ausgabe zurück, sondern typischerweise eine einfache Erfolgs- oder Fehlermeldung. Er ist leichtgewichtig und effizient für geplante Aufgaben konzipiert.
- **`srrates/controllers/front/index.php`**

  - **Klassenname & Elternklasse:** `SrratesIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Fallback oder als Standard-Einstiegspunkt für das Front-Office-Routing des Moduls. In vielen Modulen wird `index.php` in einem Front-Controller-Verzeichnis verwendet, um die Basisroute für das Modul zu behandeln, wenn keine spezifische Aktion angefordert wird. Er könnte umleiten oder einfach eine leere Seite anzeigen, wenn er nicht explizit für eine Funktion verwendet wird. Für dieses Modul ist seine primäre Funktion wahrscheinlich minimal, da `cronjob.php` die Hauptlogik des Front-Office handhabt.

#### Back-Office-Admin-Controller

Das Modul verwendet keine benutzerdefinierten Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/`. Es interagiert direkt mit den PrestaShop-Kernklassen `Currency` und `Configuration`, um Einstellungen zu verwalten und Kurse zu aktualisieren.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle Interaktionen auf der Konfigurationsseite werden durch Standard-PrestaShop-Formularelemente und potenziell jQuery, falls direkt in der `getContent()`-Methode verwendet, gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling der Konfigurationsseite basiert vollständig auf den Standardstilen des PrestaShop Back Office-Themes.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`srrates/views/admin.tpl`**
  - **Geltungsbereich:** Admin-Template.
  - **Zweck:** Dieses Template wird verwendet, um das Konfigurationsformular des Moduls im PrestaShop Back Office zu rendern. Es zeigt den Schalter „Modul aktivieren“, die „Cron-Job-URL“ und die dynamische Liste der Währungen mit ihren jeweiligen Eingabefeldern für „Aufschlag / Abschlag (%)“ an. Es ist für das visuelle Layout der `getContent()`-Ausgabe verantwortlich.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen (wie `PS_SRRATES_ENABLED` und individuelle Währungsaufschläge) direkt in der PrestaShop-Tabelle `ps_configuration`.

  - `ps_configuration`: Speichert Moduleinstellungen. Schlüssel folgen typischerweise einem Muster wie `PS_SRRATES_ENABLED` für den Hauptschalter und potenziell `PS_SRRATES_MARKUP_EUR` für währungsspezifische Aufschläge.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird von diesem Modul nicht explizit für die Ausgabe verwendet, aber `install()` könnte es als Standardpraxis registrieren. |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Wird von diesem Modul nicht explizit für die Ausgabe verwendet. |
| `displayLeftColumn` | In der linken Spalte der Front-Office-Seiten. | Wird von diesem Modul nicht explizit für die Ausgabe verwendet. |
| `displayFooter` | Im Footer-Bereich jeder Front-Office-Seite. | Wird von diesem Modul nicht explizit für die Ausgabe verwendet. |
| `displayProductExtraContent` | Auf der Produktseite, unterhalb des Hauptinhalts. | Wird von diesem Modul nicht explizit für die Ausgabe verwendet. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird von diesem Modul nicht explizit verwendet, da seine Funktion die Kursaktualisierung und nicht die Auftragsabwicklung ist. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird, vor dem Rendern. | Potenziell zum Laden von CSS/JS für die Konfigurationsseite des Moduls verwendet, obwohl keine benutzerdefinierten Assets vorhanden sind. |
| `actionModuleInstall` | Während der Modulinstallation. | Wird verwendet, um die Ersteinrichtung durchzuführen, Konfigurationseinträge zu erstellen und Hooks zu registrieren. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Wird verwendet, um Konfigurationseinträge zu bereinigen und Hooks zu deregistrieren. |

Die Kernfunktionalität des Moduls (Aktualisierung der Kurse) wird durch den `cronjob.php` Front-Controller ausgelöst, nicht direkt durch einen PrestaShop-Hook, obwohl das Modul selbst über Standard-Modul-Hooks installiert und verwaltet wird.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Sveriges Riksbank - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Dort können Sie die neuesten Versionen aus Ihrer Bestellhistorie herunterladen und auf Support-Ressourcen zugreifen.
