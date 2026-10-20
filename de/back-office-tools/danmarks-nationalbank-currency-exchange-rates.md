---
title: "Danmarks Nationalbank - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Danmarks Nationalbank - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Danmarks Nationalbank - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Danmarks Nationalbank - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/danmarks-nationalbank-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/danmarks-nationalbank-currency-exchange-rates/)
>
> ---


# Danmarks Nationalbank - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise zum Abrufen externer Daten erforderlich. Diese sind auf modernen Hosting-Umgebungen fast immer verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen, um auf dessen Einstellungen zuzugreifen. Hier verwalten Sie, wie Wechselkurse abgerufen und angewendet werden.

Die Konfigurationsseite zeigt eine Liste aller aktiven Währungen in Ihrem Shop an, sodass Sie den Wechselkurs und die Gewinnmarge für jede Währung verwalten können.

**Für jede gelistete Währung (z. B. USD, EUR, GBP):**

- **Aktueller Wechselkurs:**

  - **Was diese Einstellung bewirkt:** Dieses Feld zeigt den aktuellen Wechselkurs für diese Währung gegenüber der Standardwährung Ihres Shops an (z. B. DKK, wenn Ihr Shop in Dänemark ansässig ist). Dieser Wert wird vom Modul automatisch aktualisiert, wenn der Cronjob ausgeführt wird.
  - **Auswirkung einer Änderung dieser Einstellung:** Sie können dies bei Bedarf manuell anpassen, aber der Hauptzweck des Moduls ist die Automatisierung. Jede manuelle Änderung wird beim nächsten Cronjob-Lauf überschrieben.
  - **Empfohlener Wert:** Lassen Sie das Modul dies automatisch aktualisieren. Nur für temporäre, spezifische Bedürfnisse manuell anpassen.
  - **Händlerszenario / Beispiel:** Wenn das Modul noch nicht ausgeführt wurde oder wenn Sie einen Kurs schnell anpassen müssen, bevor das nächste geplante Update erfolgt, können Sie ihn manuell ändern. Für eine langfristige Genauigkeit sollten Sie sich jedoch auf die automatischen Updates verlassen.
- **Aufschlag / Abschlag (%):**

  - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine prozentuale Gewinnmarge (Aufschlag) oder einen Rabatt (Abschlag) auf den abgerufenen Wechselkurs hinzuzufügen.
    - Ein positiver Wert (z. B. `+2%`) erhöht den Wechselkurs, was bedeutet, dass Kunden in dieser Währung etwas mehr bezahlen, wodurch Sie Umrechnungsgebühren decken oder einen kleinen Gewinn erzielen.
    - Ein negativer Wert (z. B. `-1%`) verringert den Wechselkurs, wodurch der Fremdwährungspreis etwas niedriger wird.
  - **Auswirkung einer Änderung dieser Einstellung:** Dieser Prozentsatz wird *nachdem* der offizielle Kurs von der Danmarks Nationalbank abgerufen wurde, angewendet.
    - *Wenn für USD auf `+2%` eingestellt:* Wenn der offizielle Kurs 1 USD = 6,50 DKK beträgt, verwendet Ihr Shop 1 USD = 6,63 DKK (6,50 * 1,02).
    - *Wenn für EUR auf `-1%` eingestellt:* Wenn der offizielle Kurs 1 EUR = 7,45 DKK beträgt, verwendet Ihr Shop 1 EUR = 7,3755 DKK (7,45 * 0,99).
  - **Empfohlener Wert:** Beginnen Sie mit `0%` und passen Sie ihn basierend auf Ihrem Geschäftsmodell, den Gebühren des Zahlungs-Gateways und den gewünschten Gewinnmargen an. Viele Händler fügen einen kleinen Aufschlag (z. B. `0,5%` bis `2%`) hinzu, um Transaktionskosten zu decken.
  - **Händlerszenario / Beispiel:** Ihr Zahlungsabwickler berechnet eine Gebühr von 1,5% für die Umrechnung von EUR in DKK. Sie können einen Aufschlag von `+1,5%` für EUR festlegen, um diese Kosten effektiv an den Kunden weiterzugeben und Ihre Gewinnmarge zu erhalten.

**Cronjob-URL:**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie als Cronjob auf Ihrem Server einrichten müssen. Wenn auf diese URL zugegriffen wird, verbindet sich das Modul mit der Danmarks Nationalbank, ruft die neuesten Wechselkurse ab, wendet Ihre definierten Aufschläge/Abschläge an und aktualisiert sie in Ihrem PrestaShop-Shop.
- **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie in Ihrem Hosting-Kontrollpanel (cPanel, Plesk usw.) oder mit einem Cron-Dienst ein.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse täglich um 3 Uhr morgens aktualisiert werden. Sie würden diese URL kopieren und einen Cronjob auf Ihrem Server konfigurieren, um sie jeden Tag um 3 Uhr morgens auszuführen.

**Speichern-Schaltfläche:**

- **Was diese Einstellung bewirkt:** Wendet alle Änderungen an, die Sie an den Aufschlag-/Abschlagprozentsätzen vorgenommen haben.
- **Auswirkung einer Änderung dieser Einstellung:** Ihre neuen Gewinnmargen werden gespeichert und beim nächsten Cronjob-Lauf und der Aktualisierung der Kurse angewendet.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | **Aktueller Wechselkurs** (pro Währung) | Automatisch durch Cron aktualisiert | Zeigt den aktuellen Kurs an; manuelle Änderungen sind temporär. |
| Modulkonfigurationsseite | **Aufschlag / Abschlag (%)** (pro Währung) | `0%` (nach Bedarf anpassen) | Fügt einen Prozentsatz zum abgerufenen Kurs hinzu, um Gewinnmargen zu verwalten oder Gebühren zu decken. |
| Modulkonfigurationsseite | **Cronjob-URL** | Eindeutige URL (kopieren & konfigurieren) | Die URL zum Auslösen automatischer Kursaktualisierungen von der Danmarks Nationalbank. |
| Modulkonfigurationsseite | **Speichern-Schaltfläche** | N/A | Speichert Ihre benutzerdefinierten Aufschlag-/Abschlagprozentsätze. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht aktualisiert. Was soll ich tun?**
A:

1. **Cronjob überprüfen:** Der häufigste Grund ist ein falsch eingerichteter oder nicht laufender Cronjob. Überprüfen Sie bei Ihrem Hosting-Anbieter, ob die in der Modulkonfiguration angegebene Cronjob-URL korrekt geplant und ausgeführt wird.
2. **Modulstatus:** Stellen Sie sicher, dass das Modul in Ihrem PrestaShop Back Office aktiviert ist.
3. **Serverkonnektivität:** Bestätigen Sie, dass Ihr Server über ausgehenden Internetzugang verfügt, um eine Verbindung zur API der Danmarks Nationalbank herzustellen.
4. **Cache leeren:** Manchmal kann der PrestaShop-Cache die sofortige Anzeige aktualisierter Kurse verhindern. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.

**F: Kann ich unterschiedliche Aufschläge für verschiedene Währungen festlegen?**
A: Ja, absolut! Das ist eine der Kernfunktionen dieses Moduls. Auf der Modulkonfigurationsseite finden Sie für jede aktive Währung in Ihrem Shop ein separates Feld „Aufschlag / Abschlag (%)“.

**F: Was passiert, wenn der Dienst der Danmarks Nationalbank vorübergehend nicht verfügbar ist?**
A: Das Modul versucht, die Kurse abzurufen. Wenn dies fehlschlägt, behält es in der Regel die zuletzt erfolgreich aktualisierten Kurse bei. Es ist auf Ausfallsicherheit ausgelegt, aber konsistente Fehler könnten auf ein Serverkonnektivitätsproblem auf Ihrer Seite oder einen längeren Ausfall der Quelle hinweisen.

**F: Beeinflusst dieses Modul meine SEO oder Produkt-URLs?**
A: Nein, dieses Modul verwaltet nur Wechselkurse. Es ändert keine Produkt-URLs, Meta-Beschreibungen oder andere SEO-bezogene Elemente. Seine Auswirkung liegt rein in der Preisanzeige.

**F: Mein benutzerdefiniertes Theme scheint die aktualisierten Preise nicht korrekt anzuzeigen.**
A: Dieses Modul aktualisiert die Kern-PrestaShop-Wechselkurse. Wenn Ihr Theme Standard-PrestaShop-Funktionen zur Preisanzeige verwendet, sollte es die Änderungen widerspiegeln. Wenn nicht, könnte es sich um ein Caching-Problem handeln (Cache wie oben leeren) oder um ein stark angepasstes Theme, das die Standard-PrestaShop-Preisdarstellung umgeht. In solch seltenen Fällen benötigen Sie möglicherweise einen Webentwickler, um die Preisdarstellungslogik Ihres Themes zu untersuchen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Danmarks Nationalbank - Wechselkurse“ arbeiten.

### 4.1 Architekturübersicht

Das Modul folgt einer Standard-PrestaShop-Modularchitektur und verwendet hauptsächlich einen Cron-basierten Ansatz zur Aktualisierung von Wechselkursen. Es greift auf das PrestaShop-Konfigurationssystem für Einstellungen zu und nutzt Front-Controller für die Cron-Ausführung. Die Kernlogik befindet sich in der Hauptmoduldatei, die API-Aufrufe an die Danmarks Nationalbank verarbeitet und Einträge in der Tabelle `ps_currency` aktualisiert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `dnbrates/controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `DnbratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist der Einstiegspunkt für den Cronjob. Wenn über die eindeutige URL, die in der Back-Office-Konfiguration des Moduls bereitgestellt wird, darauf zugegriffen wird, löst er den Kursaktualisierungsprozess aus. Er ist so konzipiert, dass er extern von einem serverseitigen Cron-Scheduler aufgerufen wird. Er verarbeitet die Logik zum Abrufen von Daten von der Danmarks Nationalbank und zum Aktualisieren der Tabelle `ps_currency`.
  - `dnbrates/controllers/front/index.php`
    - **Klassenname & Elternklasse**: `DnbratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist ein Platzhalter-Controller, der oft in Modulen enthalten ist, aber im Kontext dieses Moduls nicht aktiv für eine spezifische Front-Office-Anzeige verwendet wird. Er könnte als Standard-Einstiegspunkt oder für zukünftige Erweiterungen dienen.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Back-Office-Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Das Modul interagiert direkt mit den PrestaShop-Kernklassen `Currency` und `Configuration`, um Wechselkurse und Einstellungen zu verwalten.

### 4.4 JavaScript-Assets (`views/js/`)

Es sind keine benutzerdefinierten JavaScript-Dateien im Modularchiv vorhanden.

### 4.5 CSS-Stylesheets (`views/css/`)

Es sind keine benutzerdefinierten CSS-Dateien im Modularchiv vorhanden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `dnbrates/views/admin.tpl`
    - **Zweck**: Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es zeigt die Liste der Währungen, ihre aktuellen Wechselkurse, die Eingabefelder für Aufschlag-/Abschlagprozentsätze und die Cronjob-URL an. Es wird von der `getContent()`-Methode der Hauptmoduldatei gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es interagiert hauptsächlich mit der Tabelle `ps_currency` (insbesondere der Spalte `conversion_rate`), um Wechselkurse zu aktualisieren.
  - Modulspezifische Einstellungen (wie Aufschlag-/Abschlagprozentsätze für jede Währung und die Cron-URL) werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die typischerweise mit `DNBRATES_` beginnen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich von Front-Office-Seiten. | Nicht direkt für die Inhaltsausgabe verwendet, aber Module registrieren sich hier oft für das Laden von Assets oder die Initialisierung. |
| `displayLeftColumn` | Rendert Inhalte in der linken Spalte von Front-Office-Seiten. | Nicht direkt für die Inhaltsausgabe durch dieses Modul verwendet. |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte von Front-Office-Seiten. | Nicht direkt für die Inhaltsausgabe durch dieses Modul verwendet. |
| `displayFooter` | Rendert Inhalte im Footer von Front-Office-Seiten. | Nicht direkt für die Inhaltsausgabe durch dieses Modul verwendet. |
| `displayProductAdditionalInfo` | Rendert Inhalte auf der Produktseite, typischerweise unter den Hauptproduktinformationen. | Nicht direkt für die Inhaltsausgabe durch dieses Modul verwendet. |
| `actionUpdateCurrency` | Wird ausgeführt, nachdem die Details einer Währung aktualisiert wurden. | Das Modul verwendet wahrscheinlich diesen oder einen ähnlichen Hook intern, um sicherzustellen, dass seine Logik angewendet wird, wenn sich Währungsdaten ändern. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (JS/CSS) einstellt. | Könnte verwendet werden, um spezifische Assets für die Konfigurationsseite des Moduls zu laden, obwohl keine benutzerdefinierten JS/CSS-Dateien vorhanden sind. |

*Hinweis: Die Hauptfunktion des Moduls (Aktualisierung der Kurse) wird vom Front-Controller über Cron ausgelöst, nicht durch einen Standard-PrestaShop-Hook innerhalb des Anforderungslebenszyklus.*

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Danmarks Nationalbank - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
