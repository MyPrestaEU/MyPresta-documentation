---
title: "Schweizerische Nationalbank – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Schweizerische Nationalbank – Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Schweizerische Nationalbank – Wechselkurse"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Swiss National Bank - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/swiss-national-bank-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/swiss-national-bank-currency-exchange-rates/)
>
> ---


# Schweizerische Nationalbank – Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich. Ihre Hosting-Umgebung muss auch CRON-Jobs für automatisierte Updates unterstützen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um die Hauptseite der Moduleinstellungen aufzurufen. Hier legen Sie fest, wie das Modul Wechselkurse abruft und anwendet.

#### **1. CRON-URL**

- **Was diese Einstellung bewirkt:** Dies zeigt die eindeutige URL an, die Sie als CRON-Job auf Ihrem Webserver einrichten müssen. Wenn diese URL aufgerufen wird, ruft das Modul automatisch die neuesten Wechselkurse von der Schweizerischen Nationalbank ab und aktualisiert sie in Ihrem PrestaShop-Shop.
- **Auswirkung der Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert.
  - *Wenn korrekt als CRON-Job eingerichtet:* Ihre Wechselkurse werden automatisch in der von Ihnen definierten Häufigkeit (z. B. täglich, stündlich) aktualisiert.
  - *Wenn NICHT als CRON-Job eingerichtet:* Ihre Wechselkurse werden nicht automatisch aktualisiert, und Sie müssen die Aktualisierung manuell auslösen, indem Sie diese URL in Ihrem Browser besuchen, was den Zweck der Automatisierung zunichtemacht.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als CRON-Job auf Ihrem Hosting-Server ein.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Wechselkurse jeden Morgen um 3 Uhr aktualisiert werden. Sie kopieren diese URL und fügen sie dem CRON-Job-Scheduler Ihres Hosting-Kontrollpanels hinzu, der täglich um 3 Uhr ausgeführt werden soll.

#### **2. Wechselkursmarge (%)**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, den von der Schweizerischen Nationalbank abgerufenen Wechselkursen eine prozentuale Marge hinzuzufügen. Diese Marge wird zusätzlich zum Basiswechselkurs angewendet.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf 0 (Standard) gesetzt:* Wechselkurse werden genau wie von der SNB bereitgestellt aktualisiert.
  - *Wenn auf einen positiven Wert (z. B. 2) gesetzt:* Der Wechselkurs wird um diesen Prozentsatz erhöht. Wenn der SNB-Kurs beispielsweise 1 EUR = 1,10 CHF beträgt und Sie eine Marge von 2 % festlegen, verwendet Ihr Shop 1 EUR = 1,122 CHF (1,10 \* 1,02). Dies bedeutet, dass in CHF bepreiste Produkte bei der Umrechnung in EUR etwas teurer erscheinen.
- **Empfohlener Wert:** Beginnen Sie mit 0. Erhöhen Sie nur, wenn Sie Gebühren für Zahlungs-Gateways, Währungsumrechnungskosten berücksichtigen oder eine kleine Gewinnmarge in Ihre internationale Preisgestaltung einbauen müssen.
- **Händlerszenario / Beispiel:** Ihr Zahlungsabwickler berechnet eine Gebühr von 1,5 % für internationale Währungsumrechnungen. Um diese Kosten zu decken, stellen Sie die „Wechselkursmarge“ auf 1,5 % ein. Dies stellt sicher, dass Ihre Gewinnmargen nicht durch Umrechnungsgebühren geschmälert werden.

#### **3. Speichern-Schaltfläche**

- **Was diese Einstellung bewirkt:** Diese Schaltfläche speichert alle Änderungen, die Sie an der Einstellung „Wechselkursmarge“ vorgenommen haben.
- **Auswirkung der Änderung dieser Einstellung:** Durch Klicken auf „Speichern“ wird Ihre Margeneinstellung angewendet. Die CRON-URL ist statisch und erfordert kein Speichern.
- **Empfohlener Wert:** Klicken Sie immer auf „Speichern“, nachdem Sie die Marge angepasst haben.
- **Händlerszenario / Beispiel:** Sie haben sich entschieden, eine Marge von 1 % hinzuzufügen. Nachdem Sie „1“ in das Margenfeld eingegeben haben, klicken Sie auf „Speichern“, um sicherzustellen, dass diese Einstellung für zukünftige Kursaktualisierungen angewendet wird.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modul-Konfigurationsseite | CRON-URL | Kopieren & als CRON-Job einrichten | Ermöglicht die automatische Aktualisierung der Wechselkurse durch die SNB. |
| Modul-Konfigurationsseite | Wechselkursmarge (%) | 0 | Fügt den SNB-Wechselkursen eine prozentuale Marge hinzu, um Gebühren zu decken oder die Preisstrategie anzupassen. |
| Modul-Konfigurationsseite | Speichern-Schaltfläche | Immer klicken nach Änderungen | Speichert die eingestellte Wechselkursmarge. |

## 3. Modulübersicht

Das Modul „Schweizerische Nationalbank – Wechselkurse“ ist ein PrestaShop-Modul, das die Wechselkurse in Ihrem Shop automatisch aktualisiert, indem es Daten von der Schweizerischen Nationalbank (SNB) abruft. Es verwendet den Schweizer Franken (CHF) als Basiswährung für Berechnungen und ermöglicht es Ihnen, den Kursen eine benutzerdefinierte Marge hinzuzufügen. Die Aktualisierungen erfolgen vollständig automatisiert über einen CRON-Job.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul folgt einer minimalistischen PrestaShop-Modularchitektur. Seine Hauptfunktion besteht darin, periodisch Wechselkurse von einer externen API (Schweizerische Nationalbank) abzurufen und die `currency`-Tabelle in der PrestaShop-Datenbank zu aktualisieren. Die Kernlogik befindet sich in der Hauptmoduldatei (`snbrates/cronjob.php`) und wird von einem Front-Controller ausgelöst, der für den Aufruf durch einen CRON-Job konzipiert ist. Es verwendet PrestaShops `Configuration`-Klasse zum Speichern von Einstellungen und das `Currency`-ObjectModel zum Aktualisieren von Kursen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Diese Controller sind für den externen Zugriff konzipiert, hauptsächlich durch CRON-Jobs.

  - `controllers/front/cronjob.php`

    - **Klassenname & Elternklasse:** `SnbratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dies ist der Haupteinstiegspunkt für die automatisierte Kursaktualisierung. Wenn die URL dieses Controllers aufgerufen wird (z. B. `ihrshop.com/module/snbrates/cronjob`), führt er die Logik aus, um:
      1. Die neuesten Wechselkurse vom konfigurierten SNB-API-Endpunkt abzurufen.
      2. Die konfigurierte Marge (falls vorhanden) anzuwenden.
      3. Den `conversion_rate` für jede aktive Währung in der PrestaShop-Datenbank zu aktualisieren, wobei CHF als Basis verwendet wird.
      4. Es wird keine visuelle Ausgabe an den Browser gerendert, sondern typischerweise eine einfache Erfolgs-/Fehlermeldung zurückgegeben oder umgeleitet.
  - `controllers/front/index.php`

    - **Klassenname & Elternklasse:** `SnbratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dies ist ein Platzhalter-Controller, der oft in Modulen enthalten ist, aber nicht direkt für die Kernfunktionalität dieses spezifischen Moduls verwendet wird. Er könnte für einfache Weiterleitungen oder zur Verhinderung der Verzeichnisauflistung verwendet werden, wenn direkt darauf zugegriffen wird, enthält aber keine spezifische Geschäftslogik für Kursaktualisierungen.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul führt keine benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/` ein. Es nutzt direkt PrestaShops Kern-`Currency`-ObjectModel zur Verwaltung von Währungsdaten und `Configuration` für Moduleinstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

Keine. Das Modul verwendet kein benutzerdefiniertes JavaScript.

### 4.5 CSS-Stylesheets (`views/css/`)

Keine. Das Modul verwendet kein benutzerdefiniertes CSS.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/admin.tpl`
    - **Zweck:** Dieses Template wird von der `getContent()`-Methode der Hauptmoduldatei (`snbrates/snbrates.php`) gerendert, um das Konfigurationsformular des Moduls im PrestaShop Back Office anzuzeigen.
    - **Inhalt:** Es enthält typischerweise die Formularfelder für die „CRON-URL“ (nur Anzeige) und „Wechselkursmarge (%)“ (Eingabefeld) zusammen mit der Schaltfläche „Speichern“. Es verwendet Standard-PrestaShop-Hilfsfunktionen für die Formularwiedergabe.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es interagiert mit der PrestaShop-Kerntabelle `ps_currency`, insbesondere aktualisiert es die Spalte `conversion_rate` für aktive Währungen.
  - Es speichert seine Konfigurationseinstellungen (z. B. `SNBRATES_MARGIN`) in der Tabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine expliziten Front-Office-Anzeige-Hooks (wie `displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductButtons` usw.), da seine Hauptfunktion die Hintergrunddatenverarbeitung ist. Die im Prompt erwähnten „Front-Office Hooks: Header, Columns, Product, or Footer“ könnten sich auf eine allgemeine Fähigkeit oder ein Missverständnis beziehen, da die Kernfunktion des Moduls keine Inhaltswiedergabe in diesen Bereichen beinhaltet.

  Das Modul verwendet implizit die folgenden:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionModuleInstall` | Während der Modulinstallation | Setzt Standardkonfigurationswerte. |
  | `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationswerte. |
  | (Intern) `ModuleFrontController` Dispatch | Wenn die CRON-URL aufgerufen wird | Löst die Logik zur Kursaktualisierung aus. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die neueste kompatible Version des Moduls „Schweizerische Nationalbank – Wechselkurse“ verwenden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
