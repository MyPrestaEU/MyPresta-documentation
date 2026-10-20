---
title: "Bank of Italy (Banca dItalia) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bank of Italy (Banca dItalia) - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Bank of Italy (Banca dItalia) - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Bank of Italy (Banca dItalia) - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/bank-of-italy-banca-ditalia-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/bank-of-italy-banca-ditalia-currency-exchange-rates/)
>
> ---


# Bank of Italy (Banca dItalia) - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die externe API-Kommunikation erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager auf die Schaltfläche „Konfigurieren“ neben dem Modulnamen. Dies führt Sie zum Hauptkonfigurationsbildschirm für das Modul „Bank of Italy (Banca dItalia) - Wechselkurse“.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, zu steuern, wie das Modul Ihre Währungsumrechnungskurse aktualisiert und seine Kernfunktionalität verwaltet.
- **Auswirkung der Änderung dieser Einstellung:** Diese Einstellungen wirken sich direkt auf die Genauigkeit und Häufigkeit der Wechselkurse Ihres Shops aus.

#### Spezifische Einstellungen & Optionen:

1.  **Schaltfläche „Kurse aktualisieren“**

    - **Was diese Einstellung bewirkt:** Dies ist ein manueller Auslöser, um sofort die neuesten Wechselkurse von der Bank von Italien abzurufen und auf die Währungen Ihres Shops anzuwenden.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Beim Klicken:* Das Modul verbindet sich mit der Datenquelle der Bank von Italien, ruft die aktuellsten Euro-Referenzkurse ab und aktualisiert alle aktiven Währungen in Ihrem PrestaShop-Shop (außer Ihrer Standardwährung, die normalerweise EUR ist). Dies ist nützlich zum Testen oder für eine sofortige Aktualisierung außerhalb Ihrer geplanten Cron-Jobs.
    - **Empfohlener Wert:** Klicken Sie diese Schaltfläche nach der Ersteinrichtung, um sicherzustellen, dass Ihre Kurse aktuell sind. Verwenden Sie sie manuell, wann immer Sie eine sofortige Aktualisierung benötigen.
    - **Händlerszenario / Beispiel:** Sie haben gerade eine neue Währung zu Ihrem Shop hinzugefügt, oder es gab eine signifikante Marktschwankung, und Sie möchten sicherstellen, dass Ihre Preise sofort aktualisiert werden, bevor ein großer Verkauf stattfindet.
2.  **Feld „CRON-URL für automatische Updates“**

    - **Was diese Einstellung bewirkt:** Dieses Feld zeigt eine eindeutige URL an, die Sie mit dem „Cron-Job“-Dienst Ihres Hosting-Anbieters verwenden können. Ein Cron-Job ist eine geplante Aufgabe, die automatisch in festgelegten Intervallen (z. B. einmal täglich, jede Stunde) ausgeführt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Konfiguration mit Ihrem Hosting-Anbieter:* Die Wechselkurse Ihres Shops werden automatisch in der Häufigkeit aktualisiert, die Sie in Ihren Cron-Job-Einstellungen definieren, ohne dass Sie manuell Schaltflächen klicken müssen. Dies stellt sicher, dass Ihre Kurse immer aktuell sind.
      - *Bei Nicht-Konfiguration:* Sie müssen die Schaltfläche „Kurse aktualisieren“ manuell klicken, um Ihre Wechselkurse zu aktualisieren.
    - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie einen Cron-Job auf Ihrem Server ein, der mindestens einmal alle 24 Stunden ausgeführt wird. Eine tägliche Aktualisierung ist für die meisten E-Commerce-Shops in der Regel ausreichend.
    - **Händlerszenario / Beispiel:** Sie möchten, dass die Wechselkurse Ihres Shops jeden Morgen um 3 Uhr aktualisiert werden, um sicherzustellen, dass alle Preise zu Beginn des Geschäftstages aktuell sind, ohne dass Sie daran denken müssen.
3.  **Feld „Marge zu Wechselkursen hinzufügen (%)“**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine prozentuale Marge zu den abgerufenen Wechselkursen hinzuzufügen. Wenn der offizielle Kurs beispielsweise 1 EUR = 1,10 USD beträgt und Sie eine Marge von 2 % festlegen, verwendet das Modul 1 EUR = 1,078 USD (1,10 \* 0,98) oder 1 EUR = 1,122 USD (1,10 \* 1,02), abhängig von der Umrechnungsrichtung. Dies hilft, potenzielle Transaktionsgebühren, Währungsumrechnungskosten abzudecken oder Ihnen einfach einen kleinen Puffer zu geben.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei positivem Wert (z. B. 2):* Das Modul passt die abgerufenen Wechselkurse um diesen Prozentsatz an. Dies bedeutet typischerweise, dass Sie etwas mehr lokale Währung für Ihre Euro-basierten Produkte erhalten oder etwas weniger Euro für lokale Währungsprodukte, was dazu beiträgt, Ihre Gewinnmargen zu schützen.
      - *Bei 0 (oder leer):* Das Modul verwendet die genauen Wechselkurse der Bank von Italien ohne Anpassung.
    - **Empfohlener Wert:** Beginnen Sie mit 0. Wenn Sie aufgrund von Währungsschwankungen oder Transaktionsgebühren Probleme mit der Rentabilität haben, ziehen Sie in Betracht, eine kleine Marge (z. B. 1-3 %) hinzuzufügen.
    - **Händlerszenario / Beispiel:** Ihr Zahlungs-Gateway berechnet eine Gebühr von 1,5 % für internationale Transaktionen. Durch die Festlegung einer Marge von 2 % können Sie diese Kosten absorbieren und sicherstellen, dass Ihre Rentabilität durch Währungsumrechnungen nicht geschmälert wird.
4.  **Schalter „Auf Modul-Updates prüfen“**

    - **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Modul regelmäßig bei MyPresta.eu nach neueren Versionen des Moduls sucht.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Das Modul verbindet sich gelegentlich mit MyPresta.eu, um zu prüfen, ob eine neuere Version verfügbar ist. Wenn ein Update gefunden wird, sehen Sie eine Benachrichtigung in Ihrem PrestaShop Back Office, die Sie auffordert, die neueste Version herunterzuladen und zu installieren. Dies hilft Ihnen, mit Fehlerbehebungen, neuen Funktionen und Kompatibilitätsupdates auf dem Laufenden zu bleiben.
      - *Wenn deaktiviert (NEIN):* Das Modul prüft nicht auf Updates, und Sie werden nicht über neue Versionen benachrichtigt. Sie müssten Ihr MyPresta.eu-Konto manuell auf Updates überprüfen.
    - **Empfohlener Wert:** **JA**. Die Aktualisierung Ihrer Module ist entscheidend für Sicherheit, Leistung und Kompatibilität mit zukünftigen PrestaShop-Versionen.
    - **Händlerszenario / Beispiel:** Sie möchten automatisch informiert werden, wenn eine neue Version des Moduls veröffentlicht wird, damit Sie von den neuesten Verbesserungen profitieren und sicherstellen können, dass Ihr Shop sicher und funktionsfähig bleibt.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Schaltfläche „Kurse aktualisieren“ | Nach Einrichtung klicken / manuell bei Bedarf | Ruft sofort die neuesten Wechselkurse von der Bank von Italien ab und wendet sie an. |
| Modul-Konfigurationsseite | „CRON-URL für automatische Updates“ | Kopieren und auf dem Hosting konfigurieren | Automatisiert tägliche/stündliche Wechselkursaktualisierungen, um konstante Genauigkeit zu gewährleisten. |
| Modul-Konfigurationsseite | „Marge zu Wechselkursen hinzufügen (%)“ | 0 (oder 1-3 % bei Bedarf) | Fügt einen prozentualen Puffer zu den Wechselkursen hinzu, um Gebühren abzudecken oder Gewinnmargen zu schützen. |
| Modul-Konfigurationsseite | „Auf Modul-Updates prüfen“ | JA | Benachrichtigt Sie über neue Modulversionen für Fehlerbehebungen, Funktionen und Kompatibilität. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Wechselkurse werden nicht automatisch aktualisiert. Was soll ich tun?**
A1: Dies hängt fast immer mit der Cron-Job-Einrichtung zusammen.
- **Überprüfen Sie Ihr Hosting:** Melden Sie sich in Ihrem Hosting-Kontrollpanel (cPanel, Plesk usw.) an und überprüfen Sie, ob der Cron-Job für die URL des Moduls korrekt eingerichtet ist und in den angegebenen Intervallen ausgeführt wird. Stellen Sie sicher, dass die aus der Modulkonfiguration kopierte URL exakt ist.
- **Testen Sie die URL manuell:** Kopieren Sie die „CRON-URL für automatische Updates“ aus der Modulkonfiguration und fügen Sie sie direkt in Ihren Webbrowser ein. Wenn sie erfolgreich ausgeführt wird, sollten Sie eine einfache „OK“-Meldung oder Ähnliches sehen. Wenn Sie einen Fehler sehen, könnte es ein serverseitiges Problem oder ein Problem mit der URL selbst geben.
- **Überprüfen Sie den Modulstatus:** Stellen Sie sicher, dass das Modul in Ihrem PrestaShop Back Office aktiviert ist.

**F2: Ich habe auf „Kurse aktualisieren“ geklickt, aber meine Preise in anderen Währungen haben sich nicht geändert.**
A2:
- **PrestaShop-Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). PrestaShop speichert Währungsumrechnungen oft im Cache.
- **Aktive Währungen überprüfen:** Stellen Sie sicher, dass die Währungen, die aktualisiert werden sollen, tatsächlich unter **International > Währungen** aktiviert sind. Das Modul aktualisiert nur aktive Währungen.
- **Standardwährung überprüfen:** Das Modul aktualisiert *andere* Währungen relativ zu Ihrer Standardwährung (normalerweise EUR). Wenn Ihre Standardwährung nicht EUR ist, ruft das Modul trotzdem EUR-Kurse ab und rechnet von dort aus um. Stellen Sie sicher, dass Ihre Standardwährung korrekt eingestellt ist.

**F3: Kann ich verschiedene Margen für verschiedene Währungen festlegen?**
A3: Nein, die Einstellung „Marge zu Wechselkursen hinzufügen (%)“ wendet eine einzige, einheitliche prozentuale Marge auf *alle* vom Modul abgerufenen Wechselkurse an. Wenn Sie hochspezifische, währungsspezifische Margen benötigen, bräuchten Sie eine benutzerdefinierte Entwicklungslösung oder ein fortschrittlicheres Währungsverwaltungsmodul.

**F4: Das Modul gibt an, Kurse von der Banca d’Italia abzurufen. Ist das zuverlässig?**
A4: Ja, die Banca d’Italia (Bank von Italien) ist eine Zentralbank innerhalb des Europäischen Systems der Zentralbanken (ESZB) und stellt offizielle Euro-Referenzkurse bereit. Diese Kurse sind äußerst zuverlässig und werden weithin für Finanztransaktionen in ganz Europa verwendet.

**F5: Nach der Aktualisierung des Moduls sieht mein Shop etwas seltsam aus oder ich sehe Fehler.**
A5:
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) nach jeder Modulaktualisierung.
- **Browser-Cache:** Leeren Sie den Cache und die Cookies Ihres Webbrowsers oder versuchen Sie, Ihren Shop im Inkognito-/Privatmodus aufzurufen.
- **Rückgängig machen (falls nötig):** Wenn das Problem weiterhin besteht, müssen Sie das Modul möglicherweise vorübergehend deaktivieren oder deinstallieren und zu einem früheren Backup Ihres Shops zurückkehren. Kontaktieren Sie dann den MyPresta.eu-Support mit den Details des Problems.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Bank of Italy (Banca dItalia) - Wechselkurse“ (`birates`) ist ein leichtgewichtiges PrestaShop-Modul, das zur Automatisierung von Währungskursaktualisierungen entwickelt wurde. Es folgt einem standardmäßigen PrestaShop MVC-Muster, wo anwendbar, und konzentriert sich hauptsächlich auf eine einzige Konfigurationsoberfläche und einen Front-Controller für die Ausführung von Cron-Jobs. Es nutzt PrestaShops `Currency` `ObjectModel`, um Wechselkurse zu aktualisieren. Die Kernlogik befindet sich in der Hauptmoduldatei und verwaltet Installation, Deinstallation, Konfiguration und den Kursabrufprozess.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `BiratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist dafür konzipiert, von einem externen Cron-Job aufgerufen zu werden. Seine Methode `initContent()` (oder ähnliche Logik innerhalb von `postProcess()`) löst die Methode `updateRates()` des Hauptmoduls `birates` aus. Er rendert keine visuellen Inhalte für den Benutzer; sein Zweck ist rein die Ausführung der Kursaktualisierungslogik im Hintergrund. Er gibt typischerweise eine einfache Erfolgsmeldung oder einen Status aus.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `BiratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist ein Platzhalter oder Fallback-Front-Controller. In vielen Modulen werden `index.php`-Controller verwendet, um eine Standardroute zu definieren oder Fälle zu behandeln, in denen keine spezifische Aktion bereitgestellt wird. Für dieses Modul dient er wahrscheinlich als grundlegender Einstiegspunkt, aber die primäre Funktionalität für Kursaktualisierungen wird von `cronjob.php` gehandhabt. Er könnte umleiten oder einfach eine minimale Seite anzeigen.
- **Back-Office-Admin-Controller**:

  - In diesem Modul sind keine dedizierten Admin-Controller vorhanden. Die gesamte Back-Office-Konfiguration wird direkt in der Methode `getContent()` der Hauptmoduldatei `birates.php` behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Das Modul interagiert direkt mit PrestaShops Kern-`Currency` `ObjectModel`, um bestehende Währungsumrechnungskurse zu aktualisieren.

### 4.4 JavaScript-Assets (`views/js/`)

Es sind keine benutzerdefinierten JavaScript-Dateien im Modul vorhanden.

### 4.5 CSS-Stylesheets (`views/css/`)

Es sind keine benutzerdefinierten CSS-Dateien im Modul vorhanden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `birates/views/admin.tpl`
    - **Zweck**: Dieses Template wird von der Methode `getContent()` der Hauptmoduldatei `birates.php` gerendert. Es zeigt das gesamte Konfigurationsformular für das Modul im PrestaShop Back Office an.
    - **Inhalt**: Es enthält die Schaltfläche „Kurse aktualisieren“, das CRON-URL-Feld, das Eingabefeld „Marge zu Wechselkursen hinzufügen (%)“ und den Schalter „Auf Modul-Updates prüfen“. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.
- **Hook-Templates (`views/templates/hook/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. `mypresta_updates`, `update_`, `updatev_`, `currency_`) in der Tabelle `ps_configuration` (oder `_configuration` je nach Ihrem Tabellenpräfix). Diese Schlüssel sind typischerweise mit dem Modulnamen oder einer eindeutigen Kennung präfixiert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Nicht direkt für die visuelle Ausgabe verwendet, könnte aber zum Laden von Assets verwendet werden (obwohl keine vorhanden sind). |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Nicht für die visuelle Ausgabe verwendet. |
| `displayLeftColumn` | In der linken Spalte der Front-Office-Seiten. | Nicht für die visuelle Ausgabe verwendet. |
| `displayFooter` | Am unteren Rand jeder Front-Office-Seite. | Nicht für die visuelle Ausgabe verwendet. |
| `displayProductExtraContent` | Auf der Produktseite, typischerweise unter den Hauptproduktinformationen. | Nicht für die visuelle Ausgabe verwendet. |
| `actionUpdateCurrency` | Nachdem eine Währung aktualisiert wurde. | Das Modul *löst* selbst Währungsaktualisierungen aus, greift aber nicht explizit für seine eigene Logik darauf zurück. |
| `actionModuleInstall` | Während der Modulinstallation. | Wird verwendet, um Standardkonfigurationswerte festzulegen und Hooks zu registrieren. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Wird verwendet, um Konfigurationswerte zu bereinigen und Hooks abzumelden. |

*Hinweis: Die Hauptfunktion des Moduls (Aktualisierung der Kurse) wird durch seinen `cronjob.php`-Front-Controller initiiert, der extern aufgerufen wird, anstatt über einen Standard-PrestaShop-Hook.*

## 5. Offizieller Support & Updates

Für offiziellen Support, Updates und zum Herunterladen der neuesten Version des Moduls „Bank of Italy (Banca dItalia) - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Konfiguration des Moduls gerne zur Verfügung.
