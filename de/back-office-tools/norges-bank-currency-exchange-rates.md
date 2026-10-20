---
title: "Norges Bank - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Norges Bank - Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Norges Bank - Wechselkurse - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Norges Bank - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/norges-bank-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/norges-bank-currency-exchange-rates/)
>
> ---


# Norges Bank - Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich. Ihre Hosting-Umgebung muss auch CRON-Jobs für automatische Updates unterstützen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Einstellungen für das Modul „Norges Bank - Wechselkurse“. Hier steuern Sie, wie und wann Ihre Währungskurse aktualisiert werden.

#### **Einstellungen & Optionen**

1. **CRON-URL für automatische Updates:**

   - **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Webadresse (URL), die, wenn sie aufgerufen wird, das Modul dazu veranlasst, die neuesten Wechselkurse von der Norges Bank abzurufen und in Ihrem PrestaShop-Store zu aktualisieren.
   - **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert. Sie benötigen diese URL, um eine automatisierte Aufgabe (einen „CRON-Job“) auf Ihrem Webhosting-Server einzurichten.
   - **Empfohlener Wert:** Kopieren Sie diese URL genau so, wie sie erscheint.
   - **Händlerszenario / Beispiel:** Sie geben diese URL Ihrem Hosting-Provider oder verwenden sie in Ihrem Hosting-Kontrollpanel (wie cPanel oder Plesk), um eine Aufgabe zu planen, die diese URL regelmäßig (z. B. einmal täglich) aufruft. Dies stellt sicher, dass Ihre Kurse immer aktuell sind, ohne dass Sie manuell etwas tun müssen.
2. **Wechselkursmarge (%):**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine prozentuale Marge zu den von der Norges Bank abgerufenen Wechselkursen hinzuzufügen. Wenn der offizielle Kurs beispielsweise 1 EUR = 10 NOK beträgt und Sie eine Marge von 2 % festlegen, könnte Ihr Store 1 EUR = 9,8 NOK verwenden (oder 10,2 NOK, je nach Berechnungsrichtung, wodurch die Fremdwährung für den Kunden in der Regel etwas teurer wird, um Umrechnungskosten zu decken).
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Wenn auf 0 gesetzt:* Ihr Store verwendet die exakten offiziellen Wechselkurse der Norges Bank.
     - *Wenn auf einen positiven Wert gesetzt (z. B. 2):* Das Modul passt die Wechselkurse an, um diesen Prozentsatz einzuschließen, was Ihnen effektiv einen kleinen Puffer oder eine Gewinnmarge bei Währungsumrechnungen verschafft. Dies kann helfen, Transaktionsgebühren zu decken oder einfach Ihre Rentabilität zu erhöhen.
   - **Empfohlener Wert:** Beginnen Sie mit `0`, wenn Sie exakte Kurse wünschen. Wenn Sie Kosten decken oder einen kleinen Gewinn hinzufügen müssen, ist ein Wert zwischen `0,5` und `2` Prozent üblich.
   - **Händlerszenario / Beispiel:** Wenn Ihr Zahlungs-Gateway eine Gebühr von 1 % für internationale Transaktionen erhebt, kann das Festlegen einer Marge von 1 % hier helfen, diese Kosten zu absorbieren, ohne Ihre Produktpreise in Ihrer Basiswährung zu beeinflussen.
3. **Letzte Aktualisierung:**

   - **Was diese Einstellung bewirkt:** Dies zeigt Datum und Uhrzeit an, wann das Modul die Wechselkurse in Ihrem Store zuletzt erfolgreich aktualisiert hat.
   - **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Informationsfeld und kann nicht geändert werden. Es hilft Ihnen zu überprüfen, ob Ihr CRON-Job korrekt funktioniert und Ihre Kurse regelmäßig aktualisiert werden.
   - **Empfohlener Wert:** Überprüfen Sie dieses Feld regelmäßig, um sicherzustellen, dass die Updates wie erwartet erfolgen.
   - **Händlerszenario / Beispiel:** Nachdem Sie Ihren CRON-Job eingerichtet haben, können Sie dieses Feld am nächsten Tag überprüfen, um zu bestätigen, dass das Modul erfolgreich ausgeführt wurde und die Kurse aktualisiert hat.

#### **Manueller Aktualisierungs-Button**

- **Was dieser Button bewirkt:** Dieser Button ermöglicht es Ihnen, eine sofortige Aktualisierung aller Wechselkurse von der Norges Bank manuell auszulösen.
- **Auswirkung des Klickens auf diesen Button:** Das Modul ruft sofort die neuesten Kurse ab und wendet sie auf Ihren Store an. Dies ist nützlich zum Testen oder wenn Sie eine sofortige Aktualisierung außerhalb Ihres geplanten CRON-Jobs benötigen.
- **Empfohlene Verwendung:** Verwenden Sie dies für erste Tests nach der Konfiguration oder wenn es eine signifikante, plötzliche Währungsschwankung gibt, die Sie sofort widerspiegeln möchten.

#### **Anweisungen zur Einrichtung des CRON-Jobs**

Unterhalb der Einstellungen finden Sie klare Anweisungen zur Einrichtung des CRON-Jobs auf Ihrem Server. Dies ist entscheidend für den „wartungsfreien“ Betrieb des Moduls.

- **Was dieser Abschnitt bewirkt:** Bietet den genauen Befehl oder die Methode, die Sie mit dem CRON-Job-Scheduler Ihres Hosting-Providers verwenden müssen.
- **Auswirkung der Befolgung dieser Anweisungen:** Einmal eingerichtet, ruft Ihr Server die CRON-URL automatisch in festgelegten Intervallen (z. B. einmal täglich) auf, um sicherzustellen, dass Ihre Wechselkurse immer aktuell sind, ohne manuelles Eingreifen.
- **Empfohlene Häufigkeit:** Tägliche Updates sind in der Regel ausreichend. Für sehr volatile Währungen oder hohe internationale Verkaufszahlen könnten Sie zweimal täglich in Betracht ziehen.
- **Händlerszenario / Beispiel:** In cPanel würden Sie zu „Cron-Jobs“ gehen, eine gängige Einstellung wie „Einmal täglich“ auswählen und den bereitgestellten Befehl in das Feld „Befehl“ einfügen.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | CRON-URL für automatische Updates | (Generierte URL) | URL zum Auslösen automatischer Kursaktualisierungen über CRON-Job. **Entscheidend für die Automatisierung.** |
| Modulkonfiguration | Wechselkursmarge (%) | 0 | Fügt einen prozentualen Puffer zu den Wechselkursen für Rentabilität/Kostendeckung hinzu. |
| Modulkonfiguration | Letzte Aktualisierung | (Datum/Uhrzeit) | Informationsfeld, das die letzte erfolgreiche Kursaktualisierung anzeigt. |
| Modulkonfiguration | Manueller Aktualisierungs-Button | N/A | Ruft sofort die neuesten Kurse ab und wendet sie an. Nützlich für Tests/dringende Updates. |
| Modulkonfiguration | Anweisungen zur Einrichtung des CRON-Jobs | N/A | Anleitung zur Einrichtung automatischer Updates auf Ihrem Hosting-Server. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Wechselkurse werden nicht automatisch aktualisiert. Was soll ich tun?**
A: Dies hängt fast immer mit der Einrichtung des CRON-Jobs auf Ihrem Server zusammen.
1. **CRON-Job überprüfen:** Überprüfen Sie Ihr Hosting-Kontrollpanel (cPanel, Plesk usw.), um sicherzustellen, dass der CRON-Job korrekt mit der genauen vom Modul bereitgestellten URL konfiguriert und zur Ausführung geplant ist.
2. **CRON-Pfad:** Manchmal muss der PHP-Pfad im CRON-Befehl absolut sein (z. B. `/usr/bin/php` anstelle von nur `php`). Ihr Hosting-Provider kann dies bestätigen.
3. **„Letzte Aktualisierung“ überprüfen:** Wenn sich das Feld „Letzte Aktualisierung“ in der Modulkonfiguration nie ändert, bestätigt dies, dass der CRON-Job das Aktualisierungsskript des Moduls nicht ausführt.
4. **Manuelle Aktualisierung:** Versuchen Sie, auf die Schaltfläche „Manuelle Aktualisierung“ in der Modulkonfiguration zu klicken. Wenn dies funktioniert, bestätigt dies, dass das Modul selbst Kurse abrufen kann, was definitiv auf ein CRON-Job-Problem hindeutet.

**F: Die Wechselkurse scheinen falsch zu sein oder haben sich nicht stark geändert.**
A:
1. **Norges Bank überprüfen:** Vergleichen Sie die Kurse in Ihrem Store mit den offiziellen Kursen, die von der Norges Bank veröffentlicht werden (deren Website ist normalerweise über eine schnelle Suche zugänglich).
2. **Margeneinstellung:** Denken Sie daran, dass Ihre Einstellung „Wechselkursmarge (%)“ die Kurse leicht anpasst. Stellen Sie sicher, dass dies wie beabsichtigt eingestellt ist.
3. **Letzte Aktualisierung:** Überprüfen Sie das Feld „Letzte Aktualisierung“. Wenn es alt ist, läuft Ihr CRON-Job nicht.

**F: Beeinflusst dieses Modul meine Standardwährung?**
A: Nein, das Modul aktualisiert nur die Wechselkurse für Nicht-Standardwährungen relativ zu Ihrer Standardwährung. Der Wert Ihrer Standardwährung bleibt unverändert.

**F: Ich habe mein Theme aktualisiert, und jetzt funktioniert der Währungswähler nicht mehr richtig.**
A: Dieses Modul aktualisiert nur die *Werte* der Wechselkurse. Die visuelle Anzeige und Funktionalität des Währungswählers selbst werden vom PrestaShop-Core oder Ihrem Theme gehandhabt. Wenn der Wähler nicht funktioniert, handelt es sich wahrscheinlich um ein Theme- oder Core-PrestaShop-Problem, das nicht direkt mit diesem Modul zusammenhängt. Leeren Sie Ihren Smarty-Cache (**Erweiterte Einstellungen > Performance**) und überprüfen Sie die Konfiguration Ihres Themes.

**F: Kann ich dieses Modul mit anderen Währungsmodulen verwenden?**
A: Es wird im Allgemeinen nicht empfohlen, mehrere Module zu betreiben, die versuchen, Wechselkurse zu aktualisieren, da sie sich gegenseitig stören oder Daten überschreiben könnten. Dieses Modul ist als eigenständige Lösung für Norges Bank-Kurse konzipiert. Wenn Sie Kurse aus einer anderen Quelle benötigen, sollten Sie dieses Modul deaktivieren und das andere verwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Norges Bank - Wechselkurse“ (`nbrates`) ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf eine einzige, kritische Aufgabe konzentriert: das Abrufen und Aktualisieren von Wechselkursen. Es nutzt die `Module`-Klasse von PrestaShop für Installation und Konfiguration und verwendet einen Front-Controller, um einen CRON-Endpunkt für automatisierte Updates bereitzustellen. Die Kernlogik umfasst das Senden einer HTTP-Anfrage an die Norges Bank API, das Parsen der XML-Antwort, das Berechnen von Kreuzkursen und das Aktualisieren der PrestaShop-Tabelle `ps_currency`.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname**: `NbratesCronjobModuleFrontController`
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dieser Controller handhabt die Ausführung des CRON-Jobs. Wenn er über seine URL (in der Modulkonfiguration bereitgestellt) aufgerufen wird, löst er die Methode `cronjob()` innerhalb der Hauptmodulklasse `nbrates` aus. Er ist dafür konzipiert, von einem externen Scheduler (CRON) aufgerufen zu werden und gibt eine einfache Erfolgs-/Fehlermeldung aus. Er rendert keine visuellen Inhalte für den Benutzer.
  - `controllers/front/index.php`
    - **Klassenname**: `NbratesIndexModuleFrontController`
    - **Elternklasse**: `ModuleFrontController`
    - **Verantwortlichkeit**: Dies ist ein Platzhalter-Controller, der oft in Modulen enthalten ist, aber in der Kernfunktionalität dieses spezifischen Moduls nicht aktiv verwendet wird. Er dient typischerweise als Standard-Einstiegspunkt, wenn ein Modul eine dedizierte Front-Office-Seite hat. In diesem Modul besteht sein Hauptzweck wahrscheinlich darin, die Verzeichnisauflistung zu verhindern, wenn `cronjob.php` direkt ohne eine spezifische Aktion aufgerufen wird.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Die Kernlogik des Moduls ist in der Hauptdatei `nbrates/cronjob.php` enthalten. Dies ist bei einfacheren Modulen üblich, die keine komplexen Datenstrukturen oder umfangreiche Datenbankinteraktionen über die Standardkonfiguration hinaus erfordern.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul enthält kein benutzerdefiniertes JavaScript für Front-Office- oder Back-Office-Funktionalität.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält keine benutzerdefinierten CSS-Stylesheets. Die Back-Office-Konfiguration basiert auf dem Standard-Admin-Panel-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Zweck**: Dieses Template wird von der `getContent()`-Methode der Hauptmodulklasse (`nbrates/cronjob.php`) gerendert, um das Konfigurationsformular des Moduls im PrestaShop Back Office anzuzeigen.
    - **Inhalt**: Es enthält typischerweise die HTML-Struktur für die Anzeige der CRON-URL, das Eingabefeld für die Wechselkursmarge, die Informationen zur „Letzten Aktualisierung“, den manuellen Aktualisierungs-Button und die Anweisungen zur Einrichtung des CRON-Jobs. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es interagiert mit der Standard-PrestaShop-Tabelle `ps_configuration`, um seine Einstellungen zu speichern (z. B. `NBS_LAST_UPDATE`, `NBS_MARGIN`).
  - Es aktualisiert die Tabelle `ps_currency`, insbesondere die Spalte `conversion_rate` für Nicht-Standardwährungen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendert im `<head>`-Bereich des Back Office. | Wird verwendet, um notwendige CSS/JS für die Konfigurationsseite des Moduls einzubinden (obwohl in diesem Modul keine verwendet werden). |
| `actionAdminControllerSetMedia` | Wird vor dem Rendern eines Admin-Controllers aufgerufen. | Wird verwendet, um Assets (JS/CSS) für Admin-Seiten zu registrieren. |
| `actionCronJob` | Benutzerdefinierter Hook, ausgelöst durch den `cronjob`-Front-Controller. | Der primäre Hook, in dem die Währungsaktualisierungslogik des Moduls ausgeführt wird. |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich des Front Office. | (Wird von diesem Modul nicht explizit für die Ausgabe verwendet, aber oft von Modulen registriert). |
| `displayLeftColumn` | Rendert Inhalte in der linken Spalte des Front Office. | (Wird von diesem Modul nicht explizit für die Ausgabe verwendet). |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte des Front Office. | (Wird von diesem Modul nicht explizit für die Ausgabe verwendet). |
| `displayFooter` | Rendert Inhalte im Footer des Front Office. | (Wird von diesem Modul nicht explizit für die Ausgabe verwendet). |
| `displayProductExtraContent` | Rendert Inhalte auf der Produktseite. | (Wird von diesem Modul nicht explizit für die Ausgabe verwendet). |

*Hinweis: Obwohl die Modulbeschreibung Front-Office-Hooks wie Header, Spalten, Produkt oder Footer erwähnt, zeigt das bereitgestellte Code-Inventar keine Templates oder spezifische Logik zum Rendern von Inhalten in diesen Hooks. Es ist möglich, dass dies generische Hooks sind, die während der Installation registriert, aber von diesem spezifischen Modul nicht aktiv für die visuelle Ausgabe genutzt werden, da seine Funktion rein die Backend-Datensynchronisation ist.*

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Norges Bank - Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Sie können die neuesten Versionen aus Ihrer Bestellhistorie herunterladen und direkt über die MyPresta.eu-Plattform auf Support-Ressourcen zugreifen.
