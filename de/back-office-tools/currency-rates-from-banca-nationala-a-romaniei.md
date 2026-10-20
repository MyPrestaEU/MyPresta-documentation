---
title: "Wechselkurse von der Banca Nationala a Romaniei - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Wechselkurse von der Banca Nationala a Romaniei' von MyPresta.eu."
sidebar:
  label: "Wechselkurse von der Banca Nationala a Romaniei - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Currency rates from Banca Nationala a Romaniei auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/currency-rates-from-banca-nationala-a-romaniei.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/currency-rates-from-banca-nationala-a-romaniei/)
>
> ---


# Wechselkurse von der Banca Nationala a Romaniei

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Datenfeeds erforderlich, die in den meisten modernen Hosting-Umgebungen Standard sind.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf die Einstellungen zuzugreifen.

#### **Einstellungen & Optionen**

1. **Nach Modul-Updates suchen**

   - **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Modul regelmäßig bei MyPresta.eu nach neuen Versionen oder wichtigen Updates sucht.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (JA):* Das Modul verbindet sich gelegentlich mit MyPresta.eu, um zu prüfen, ob eine neuere Version verfügbar ist. Wenn ein Update gefunden wird, kann eine Benachrichtigung in Ihrem PrestaShop Back Office erscheinen, die Sie zum Herunterladen und Installieren auffordert.
     - *Wenn deaktiviert (NEIN):* Das Modul sucht nicht automatisch nach Updates. Sie müssen Ihr MyPresta.eu-Konto manuell auf neue Versionen überprüfen.
   - **Empfohlener Wert:** **JA**. Es wird immer empfohlen, Ihre Module auf dem neuesten Stand zu halten, um von neuen Funktionen, Fehlerbehebungen und Sicherheitsverbesserungen zu profitieren.
   - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihr Wechselkursmodul immer die neueste, stabilste Version ausführt, ohne ständig manuell nachzusehen. Wenn Sie dies aktivieren, erhalten Sie eine Benachrichtigung, wenn ein Update bereit ist.
2. **Wechselkurse aktualisieren**

   - **Was diese Einstellung bewirkt:** Dies ist die Kernfunktion des Moduls. Wenn Sie auf diese Schaltfläche klicken, ruft das Modul sofort die neuesten Wechselkurse von der Banca Naţională a României (BNR) ab und wendet sie auf die in Ihrem PrestaShop-Shop konfigurierten Währungen an.
   - **Auswirkung der Änderung dieser Einstellung:** Das Klicken auf diese Schaltfläche löst eine sofortige Aktualisierung aller Wechselkurse in Ihrem Shop basierend auf dem BNR-Feed aus. Dies ist ein manueller Auslöser für den Aktualisierungsprozess.
   - **Empfohlener Wert:** Dies ist eine Aktionsschaltfläche, keine Einstellung. Klicken Sie darauf, wann immer Sie eine sofortige Aktualisierung benötigen oder nachdem Sie Ihre Währungen konfiguriert haben.
   - **Händlerszenario / Beispiel:** Es ist der Beginn des Handelstages, und Sie möchten sicherstellen, dass alle Ihre Preise die allerneuesten Wechselkurse widerspiegeln, bevor Kunden Bestellungen aufgeben. Sie würden auf diese Schaltfläche klicken.
3. **Cronjob-URL**

   - **Was diese Einstellung bewirkt:** Dieses Feld zeigt eine eindeutige URL an, die Sie verwenden können, um die Wechselkursaktualisierungen zu automatisieren. Diese URL ist dafür gedacht, von einem „Cronjob“ auf Ihrem Webserver aufgerufen zu werden, einer geplanten Aufgabe, die automatisch in festgelegten Intervallen (z. B. einmal täglich, jede Stunde) ausgeführt wird.
   - **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Das Kopieren und Festlegen dieser URL im Cronjob-Scheduler Ihres Hosting-Panels stellt sicher, dass Ihre Wechselkurse automatisch aktualisiert werden, ohne dass Sie manuell auf die Schaltfläche „Wechselkurse aktualisieren“ klicken müssen.
   - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie einen Cronjob auf Ihrem Server ein, um sie mindestens einmal täglich oder häufiger auszuführen, wenn Ihr Geschäft dies erfordert.
   - **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse jeden Morgen um 6 Uhr automatisch aktualisiert werden, auch wenn Sie nicht an Ihrem Computer sind. Sie würden diese URL kopieren und einen Cronjob auf Ihrem Hosting-Server konfigurieren, um sie täglich um 6 Uhr auszuführen.
4. **Zu aktualisierende Währung**

   - **Was diese Einstellung bewirkt:** Diese Dropdown-Liste ermöglicht es Ihnen, auszuwählen, welche spezifischen Währungen in Ihrem PrestaShop-Shop vom BNR-Feed aktualisiert werden sollen. Der BNR-Feed liefert hauptsächlich Kurse gegenüber RON. Das Modul wandelt diese dann in die Standardwährung Ihres Shops und dann in andere ausgewählte Währungen um.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn eine bestimmte Währung ausgewählt ist:* Nur der Wechselkurs dieser Währung wird vom Modul aktualisiert.
     - *Wenn „Alle Währungen“ ausgewählt ist:* Das Modul versucht, alle aktiven Währungen in Ihrem PrestaShop-Shop mithilfe des BNR-Feeds zu aktualisieren.
   - **Empfohlener Wert:** **Alle Währungen**, es sei denn, Sie haben einen bestimmten Grund, nur eine zu aktualisieren. Dies stellt sicher, dass alle Ihre internationalen Preise konsistent sind.
   - **Händlerszenario / Beispiel:** Ihr Shop akzeptiert EUR, USD und GBP. Sie möchten, dass alle diese Währungen täglich basierend auf der Umrechnung des BNR-Feeds in RON und dann in die Standardwährung Ihres Shops aktualisiert werden. Sie würden „Alle Währungen“ auswählen. Wenn Sie aus irgendeinem Grund nur EUR aktualisieren wollten, würden Sie „EUR“ auswählen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Nach Modul-Updates suchen | JA | Ermöglicht automatische Überprüfungen auf neue Modulversionen. |
| Modulkonfiguration | Wechselkurse aktualisieren | N/A (Aktionsschaltfläche) | Löst manuell eine sofortige Aktualisierung aller ausgewählten Wechselkurse von der BNR aus. |
| Modulkonfiguration | Cronjob-URL | N/A (Nur Anzeige) | Bietet die URL zum Einrichten einer automatisierten geplanten Aufgabe für Wechselkursaktualisierungen. |
| Modulkonfiguration | Zu aktualisierende Währung | Alle Währungen | Bestimmt, welche Währungen in Ihrem Shop automatische Kursaktualisierungen von der BNR erhalten. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht aktualisiert. Was sollte ich zuerst überprüfen?**
A1:

1. **Manuelle Aktualisierung:** Gehen Sie zur Konfigurationsseite des Moduls und klicken Sie auf die Schaltfläche „Wechselkurse aktualisieren“. Wenn dies funktioniert, liegt das Problem wahrscheinlich bei Ihrer Cronjob-Einrichtung.
2. **Cronjob:** Überprüfen Sie nochmals, ob Ihr Cronjob auf Ihrem Hosting-Server korrekt konfiguriert ist und die exakte „Cronjob-URL“ verwendet, die vom Modul bereitgestellt wird. Stellen Sie sicher, dass er mit der gewünschten Häufigkeit ausgeführt wird.
3. **Moduleinstellungen:** Überprüfen Sie, ob „Alle Währungen“ oder die spezifischen Währungen, die Sie aktualisieren möchten, im Dropdown-Menü „Zu aktualisierende Währung“ ausgewählt sind.
4. **PrestaShop-Währungen:** Stellen Sie sicher, dass die Währungen, die aktualisiert werden sollen, in Ihrem PrestaShop-Shop aktiv sind (International > Währungen).
5. **Serverkonnektivität:** Stellen Sie sicher, dass Ihr Server auf externe Websites zugreifen kann (insbesondere den BNR-Feed). Manchmal können Firewall-Regeln oder Netzwerkprobleme dies verhindern.

**F2: Das Modul meldet, dass es aktualisiert wurde, aber die Preise in meinem Front Office scheinen nicht zu stimmen.**
A2:

1. **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies stellt sicher, dass Ihr Shop die neuesten Daten anzeigt.
2. **Browser-Cache:** Leeren Sie den Cache und die Cookies Ihres Browsers oder versuchen Sie, Ihren Shop in einem Inkognito-/privaten Browsing-Fenster anzuzeigen, um lokale Caching-Probleme auszuschließen.
3. **Währungsauswahl:** Stellen Sie sicher, dass Sie die Preise im Front Office in der richtigen Währung anzeigen.

**F3: Kann ich die Kurse häufiger als einmal täglich aktualisieren?**
A3: Ja, das können Sie. Beim Einrichten Ihres Cronjobs können Sie ihn so konfigurieren, dass er jede Stunde, alle paar Stunden oder in jedem von Ihrem Hosting-Anbieter unterstützten Cron-Scheduler-Intervall ausgeführt wird. Achten Sie nur auf die potenzielle Serverlast, wenn Sie ihn extrem häufig (z. B. jede Minute) ausführen lassen, obwohl dies bei Währungsaktualisierungen selten ein Problem darstellt.

**F4: Was passiert, wenn der BNR-Feed vorübergehend nicht verfügbar ist?**
A4: Wenn der BNR-Feed nicht verfügbar ist, wird das Modul wahrscheinlich keine neuen Kurse abrufen können. Es werden Ihre bestehenden Kurse nicht gelöscht oder zurückgesetzt; sie bleiben einfach unverändert, bis der Feed wieder verfügbar ist und eine erfolgreiche Aktualisierung stattfindet. Möglicherweise sehen Sie eine Fehlermeldung in den Cronjob-Protokollen Ihres Servers, wenn die Aktualisierung fehlschlägt.

**F5: Die Standardwährung meines Shops ist nicht RON. Funktioniert dieses Modul trotzdem?**
A5: Ja, absolut. Das Modul ist so konzipiert, dass es unabhängig von der Standardwährung Ihres Shops funktioniert. Es ruft die BNR-Kurse (die typischerweise gegenüber RON sind) ab und wandelt sie dann intelligent in die Standardwährung Ihres Shops und anschließend in alle anderen aktiven Währungen um, die Sie für die Aktualisierung aktiviert haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Wechselkurse von der Banca Nationala a Romaniei“ ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf eine einzige Aufgabe konzentriert: das Abrufen und Aktualisieren von Wechselkursen. Es folgt einer grundlegenden PrestaShop-Modulstruktur, die die `Module`-Klasse für Installation und Konfiguration sowie `ModuleFrontController` für seine Cronjob-Funktionalität nutzt. Es führt keine benutzerdefinierten `ObjectModel`-Klassen oder Datenbanktabellen ein, sondern stützt sich stattdessen auf die Kernklasse `Currency` und die `Configuration`-Tabelle von PrestaShop für Einstellungen. Die Kernlogik umfasst das Parsen eines XML-Feeds von der BNR und das Aktualisieren bestehender Wechselkurse.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind für den externen Zugriff konzipiert, hauptsächlich für die Cronjob-Automatisierung.

- `controllers/front/cronjob.php`
  - **Klassenname & übergeordnete Klasse:** `BnrratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der dedizierte Endpunkt für den automatisierten Währungsaktualisierungs-Cronjob. Beim Zugriff löst er die Kernlogik des Moduls aus, um die neuesten Wechselkurse von der BNR abzurufen und in der PrestaShop-Datenbank zu aktualisieren. Er gibt typischerweise eine einfache Erfolgs- oder Fehlermeldung zurück, die für die Cronjob-Protokollierung geeignet ist. Er rendert keine visuelle Ausgabe für einen Browser.
- `controllers/front/index.php`
  - **Klassenname & übergeordnete Klasse:** `BnrratesIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Fallback oder als Standard-Einstiegspunkt, obwohl seine primäre Funktion angesichts des expliziten `cronjob.php`-Controllers minimal sein könnte. In vielen Modulen könnte ein `index.php`-Front-Controller umleiten oder eine einfache Nachricht anzeigen, wenn er direkt ohne spezifische Parameter aufgerufen wird. Für dieses Modul ist seine praktische Verwendung wahrscheinlich begrenzt, wobei `cronjob.php` die Hauptinteraktion im Front-Office übernimmt.

#### Back-Office-Admin-Controller

Das Modul implementiert keine benutzerdefinierten `AdminController`-Klassen. Die gesamte Back-Office-Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` ein. Es interagiert direkt mit den Kernklassen `Currency` und `Configuration` von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `bnrrates/views/admin.tpl`
    - **Zweck:** Dieses Template ist für das Rendern des Konfigurationsformulars des Moduls im PrestaShop Back Office verantwortlich. Es zeigt die Einstellungen wie „Nach Modul-Updates suchen“, die Schaltfläche „Wechselkurse aktualisieren“, die „Cronjob-URL“ und das Dropdown-Menü „Zu aktualisierende Währung“ an.
    - **Variablen:** Es würde typischerweise Variablen von der `getContent()`-Methode der Hauptmoduldatei erhalten, wie z. B. die aktuellen Werte der Konfigurationseinstellungen und die generierte Cronjob-URL.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`. Die relevanten Konfigurationsschlüssel sind:
    - `BNRRATES_MYPRESTA_UPDATES`: Speichert den booleschen Wert für die Überprüfung von Modul-Updates.
    - `BNRRATES_CURRENCY_TO_UPDATE`: Speichert die ID der zu aktualisierenden Währung oder einen speziellen Wert (z. B. `0` oder `all`) für alle Währungen.
    - `BNRRATES_LAST_UPDATE_TIME`: (Wahrscheinlich) Speichert einen Zeitstempel der letzten erfolgreichen Aktualisierung.
    - `BNRRATES_CRON_TOKEN`: Speichert ein eindeutiges Token, das in der Cronjob-URL für die Sicherheit verwendet wird.
- **Registrierte Hooks-Tabelle**:
  Das Modul verwendet hauptsächlich die `action`-Hooks für seine Kernfunktionalität und potenziell `display`-Hooks für Benachrichtigungen oder spezifische Inhalte (obwohl in den bereitgestellten Informationen keine spezifischen Front-Office-Display-Hooks explizit aufgeführt sind, erwähnt die Modulbeschreibung „Header, Spalten, Produkt oder Footer“ als potenzielle Bereiche, was `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons`, `displayFooter` usw. implizieren würde. Angesichts des Zwecks des Moduls wären diese jedoch wahrscheinlich für die Anzeige einer Benachrichtigung oder eines Status, nicht für die Kernfunktionalität).

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionModuleInstall` | Während der Modulinstallation | Registriert die Modulkonfiguration, erstellt Standardeinstellungen. |
| `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt die Modulkonfiguration aus `ps_configuration`. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird | Registriert potenziell CSS/JS für die Admin-Konfigurationsseite (obwohl in diesem Modul keine vorhanden sind). |
| `displayBackOfficeHeader` | Im Header des Back Office | Zeigt potenziell Update-Benachrichtigungen oder andere admin-spezifische Inhalte an. |
| `displayHeader` | Im `<head>`-Bereich des Front Office | Nicht direkt für die Kernfunktionalität verwendet, könnte aber bei Bedarf für Meta-Tags oder JS/CSS verwendet werden. |
| `displayLeftColumn` | In der linken Spalte des Front Office | Nicht direkt für die Kernfunktionalität verwendet, könnte aber für die Anzeige eines Währungsblocks verwendet werden. |
| `displayRightColumn` | In der rechten Spalte des Front Office | Nicht direkt für die Kernfunktionalität verwendet, könnte aber für die Anzeige eines Währungsblocks verwendet werden. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des Warenkorbs | Nicht direkt für die Kernfunktionalität verwendet, könnte aber für währungsbezogene Informationen verwendet werden. |
| `displayFooter` | Im Footer des Front Office | Nicht direkt für die Kernfunktionalität verwendet, könnte aber für währungsbezogene Informationen verwendet werden. |

Die Kernlogik zur Währungsaktualisierung wird durch den Zugriff auf den Front-Controller `cronjob.php` ausgelöst, der kein Standard-PrestaShop-Hook, sondern ein externer Endpunkt ist.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Wechselkurse von der Banca Nationala a Romaniei“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
