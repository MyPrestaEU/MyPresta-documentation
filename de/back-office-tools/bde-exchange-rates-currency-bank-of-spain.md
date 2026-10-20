---
title: "BdE Wechselkurse & Währung (Bank von Spanien) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul BdE Wechselkurse & Währung (Bank von Spanien) von MyPresta.eu."
sidebar:
  label: "BdE Wechselkurse & Währung (Bank von Spanien) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul BdE Exchange Rates & Currency (Bank of Spain) auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/bde-exchange-rates-currency-bank-of-spain.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/bde-exchange-rates-currency-bank-of-spain/)
>
> ---


# BdE Wechselkurse & Währung (Bank von Spanien)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL (zum Abrufen externer Daten), JSON (zur Datenverarbeitung) und OpenSSL (für sichere Verbindungen) sind in der Regel erforderlich und auf den meisten modernen Hosting-Umgebungen Standard.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Einstellungen für das Modul „BdE Wechselkurse & Währung (Bank von Spanien)“. Hier steuern Sie, wie das Modul Wechselkurse abruft und anwendet.

#### **MyPresta.eu Live-Updates**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, die Verbindung des Moduls zu MyPresta.eu für automatische Updates und Support zu verwalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Eingabe Ihrer MyPresta.eu Bestell-ID und E-Mail-Adresse:* Ermöglicht dem Modul, nach neuen Versionen zu suchen und Updates direkt von MyPresta.eu zu erhalten. Dies stellt sicher, dass Sie immer die neuesten Funktionen und Fehlerbehebungen haben.
  - *Leerlassen:* Das Modul kann nicht nach automatischen Updates suchen. Sie müssten neue Versionen manuell von Ihrem MyPresta.eu-Konto herunterladen und installieren.
- **Empfohlener Wert:** Geben Sie immer Ihre MyPresta.eu Bestell-ID und die E-Mail-Adresse ein, die mit Ihrem Kauf verknüpft ist. Dies ist entscheidend für den Erhalt zeitnaher Updates und Support.
- **Händlerszenario / Beispiel:** Sie haben das Modul mit `ihre.email@example.com` gekauft und Ihre Bestell-ID war `MP12345`. Die Eingabe dieser Details hier bedeutet, dass Sie direkt in Ihrem PrestaShop Back Office benachrichtigt werden, wenn eine neue Version des Moduls veröffentlicht wird, und Sie können mit einem einzigen Klick aktualisieren.

#### **CRON Job URL**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie verwenden können, um einen „CRON-Job“ auf Ihrem Server einzurichten. Ein CRON-Job ist eine geplante Aufgabe, die automatisch einen bestimmten Befehl oder eine URL in regelmäßigen Abständen (z. B. einmal täglich) ausführt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Einrichten eines CRON-Jobs mit dieser URL:* Das Modul ruft die neuesten Wechselkurse der Bank von Spanien automatisch in der von Ihnen definierten Häufigkeit (z. B. täglich) ab. Dies stellt sicher, dass Ihre Währungskurse immer aktuell sind, ohne manuelles Eingreifen.
  - *Kein Einrichten eines CRON-Jobs:* Die Wechselkurse werden nicht automatisch aktualisiert. Sie müssten diese URL jedes Mal manuell in Ihrem Browser aufrufen, wenn Sie die Kurse aktualisieren möchten, was sehr unpraktisch ist und den Zweck der Automatisierung zunichtemacht.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie einen täglichen CRON-Job auf Ihrem Hosting-Server ein. Die meisten Hosting-Kontrollpanels (wie cPanel, Plesk) haben einen Abschnitt „Cron Jobs“, in dem Sie diese URL einfach hinzufügen können, um sie einmal alle 24 Stunden auszuführen.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihre Euro-Wechselkurse jeden Morgen um 3:00 Uhr aktualisiert werden. Sie kopieren die bereitgestellte CRON-URL, gehen zu Ihrem Hosting-Kontrollpanel, erstellen einen neuen CRON-Job, fügen die URL ein und stellen ihn so ein, dass er täglich um 3:00 Uhr ausgeführt wird. Von da an werden Ihre Kurse automatisch aktualisiert.

#### **Margenanpassung (%)**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, einen kleinen prozentualen Aufschlag auf die abgerufenen Wechselkurse zu addieren. Dies kann nützlich sein, um potenzielle Transaktionsgebühren, Währungsumrechnungskosten oder einfach einen kleinen Puffer abzudecken.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Einstellen eines positiven Prozentsatzes (z. B. 2%):* Das Modul erhöht den offiziellen Wechselkurs um diesen Prozentsatz. Wenn der offizielle Kurs beispielsweise 1 EUR = 1,10 USD beträgt und Sie eine Marge von 2% einstellen, verwendet das Modul 1 EUR = 1,122 USD (1,10 * 1,02). Dies bedeutet, dass in EUR bepreiste Produkte bei der Umrechnung in USD etwas teurer erscheinen.
  - *Einstellen von 0% (Standard):* Das Modul verwendet die exakten offiziellen Wechselkurse ohne Anpassung.
- **Empfohlener Wert:** 0%, es sei denn, Sie haben spezifische geschäftliche Gründe (wie die Deckung von Bankgebühren), eine Marge hinzuzufügen. Transparenz ist oft am besten für das Kundenvertrauen.
- **Händlerszenario / Beispiel:** Ihr Zahlungs-Gateway berechnet eine Gebühr von 1,5% für internationale Währungsumrechnungen. Um dies auszugleichen, könnten Sie die Margenanpassung auf 1,5% einstellen. Dies stellt sicher, dass Ihre umgerechneten Preise diese Kosten leicht berücksichtigen.

#### **Währungskurse aktualisieren**

- **Was diese Einstellung bewirkt:** Dies ist eine manuelle Auslösetaste, um alle Wechselkurse sofort von der Bank von Spanien abzurufen und zu aktualisieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Klicken auf die Schaltfläche:* Das Modul verbindet sich sofort mit der Bank von Spanien, ruft die neuesten Kurse ab und aktualisiert sie in Ihrem PrestaShop-Shop. Dies ist nützlich zum Testen oder für eine sofortige Aktualisierung außerhalb Ihres CRON-Job-Zeitplans.
- **Empfohlener Wert:** Verwenden Sie diese Schaltfläche für erste Einrichtungstests oder wenn Sie eine sofortige Aktualisierung benötigen. Für regelmäßige Updates verlassen Sie sich auf den CRON-Job.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten überprüfen, ob es korrekt funktioniert und die neuesten Kurse abruft. Sie klicken auf diese Schaltfläche, um den sofortigen Effekt zu sehen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MyPresta.eu Bestell-ID | Ihre Bestell-ID | Ermöglicht automatische Modul-Updates und Support. |
| Modulkonfiguration | MyPresta.eu E-Mail | Ihre E-Mail | Ermöglicht automatische Modul-Updates und Support. |
| Modulkonfiguration | CRON Job URL | (Eindeutige URL) | Richten Sie einen täglichen CRON-Job mit dieser URL für automatische Kursaktualisierungen ein. |
| Modulkonfiguration | Margenanpassung (%) | 0% | Fügen Sie einen prozentualen Puffer zu den Wechselkursen hinzu (z. B. für Gebühren). |
| Modulkonfiguration | Währungskurse aktualisieren | Klicken zum Auslösen | Manuelles sofortiges Abrufen und Aktualisieren der Wechselkurse. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Währungskurse werden nicht automatisch aktualisiert.**
A:

1. **Überprüfen Sie Ihre CRON-Job-Einrichtung:** Überprüfen Sie nochmals, ob Sie den CRON-Job auf Ihrem Hosting-Server korrekt mit der genauen URL eingerichtet haben, die in der Modulkonfiguration angegeben ist. Stellen Sie sicher, dass er mindestens einmal täglich ausgeführt werden soll.
2. **Überprüfen Sie die CRON-Job-Ausführung:** Einige Hosting-Panels bieten Protokolle für die CRON-Job-Ausführung. Überprüfen Sie diese Protokolle, um festzustellen, ob der CRON-Job tatsächlich ausgeführt wird und ob Fehler auftreten.
3. **Serverkonnektivität:** Stellen Sie sicher, dass Ihr Server ausgehenden Zugriff auf externe Websites (insbesondere die API der Bank von Spanien) hat. Manchmal können Firewalls dies blockieren. Kontaktieren Sie Ihren Hosting-Anbieter, wenn Sie vermuten, dass dies das Problem ist.
4. **Modulkonfiguration:** Stellen Sie sicher, dass Ihre MyPresta.eu-Details korrekt eingegeben sind, um potenzielle Update-Probleme zu vermeiden.

**F: Die Preise in EUR scheinen auch nach einem Update leicht abzuweichen.**
A:

1. **Margenanpassung überprüfen:** Überprüfen Sie die Einstellung „Margenanpassung (%)“ in der Modulkonfiguration. Wenn sie auf einen Wert größer als 0 eingestellt ist, werden Ihre Preise um diesen Prozentsatz angepasst. Stellen Sie sie auf 0% ein, wenn Sie exakte offizielle Kurse wünschen.
2. **PrestaShop-Rundung:** PrestaShop hat eigene Rundungsregeln für Preise. Stellen Sie sicher, dass Ihre Währungseinstellungen unter **International > Währungen** auf die gewünschte Dezimalgenauigkeit konfiguriert sind.
3. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Performance) und Ihren Browser-Cache.

**F: Was passiert an Feiertagen oder Wochenenden, wenn die Bank von Spanien keine neuen Kurse veröffentlicht?**
A: Das Modul ist so konzipiert, dass es dies intelligent handhabt. Wenn für einen bestimmten Tag keine neuen Kurse verfügbar sind, werden die zuletzt erfolgreich abgerufenen Kurse weiterhin verwendet. Sobald neue Kurse veröffentlicht werden, aktualisiert das Modul diese beim nächsten geplanten Lauf.

**F: Kann ich dieses Modul mit anderen Währungsmodulen verwenden?**
A: Dieses Modul konzentriert sich speziell auf das Abrufen und Anwenden offizieller Kurse der Bank von Spanien. Es funktioniert im Allgemeinen gut mit den nativen Mehrwährungsfunktionen von PrestaShop. Wenn Sie jedoch andere Module haben, die *ebenfalls* versuchen, Wechselkurse aus verschiedenen Quellen abzurufen oder zu überschreiben, kann es zu Konflikten kommen. Es ist am besten, eine primäre Quelle für Wechselkursaktualisierungen zu verwenden, um Inkonsistenzen zu vermeiden.

**F: Ich sehe einen Abschnitt „MyPresta.eu Updates“. Wofür ist er?**
A: In diesem Abschnitt können Sie Ihre MyPresta.eu Bestell-ID und E-Mail-Adresse eingeben. Dies ermöglicht dem Modul, nach neuen Versionen zu suchen und Updates direkt von MyPresta.eu zu erhalten, wodurch Sie immer die neuesten Funktionen und Fehlerbehebungen erhalten. Es wird dringend empfohlen, dies auszufüllen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `BdE Exchange Rates & Currency` ist ein leichtgewichtiges PrestaShop-Modul, das primär für die Integration mit der offiziellen Wechselkurs-API der Bank von Spanien entwickelt wurde. Es folgt einer Standard-PrestaShop-Modulstruktur, die die `Module`-Klasse für Installation und Konfiguration sowie `ModuleFrontController` für die Bearbeitung von CRON-Job-Anfragen nutzt. Seine Kernfunktionalität dreht sich um das Abrufen externer Daten, deren Parsen und das Aktualisieren der nativen `Currency`-Wechselkurse von PrestaShop.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- **`controllers/front/cronjob.php`**
  - **Klassenname & Elternklasse:** `BderatesCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist der Einstiegspunkt für den geplanten CRON-Job. Beim Zugriff initiiert er den Prozess des Abrufens der neuesten Wechselkurse von der Bank von Spanien. Er verarbeitet die API-Anfrage, parst die Antwort und aktualisiert die Wechselkurse für die konfigurierten Währungen in PrestaShop. Er ist so konzipiert, dass er extern von einem serverseitigen CRON-Scheduler aufgerufen wird und gibt typischerweise eine einfache Erfolgs-/Fehlermeldung zurück.
- **`controllers/front/index.php`**
  - **Klassenname & Elternklasse:** `BderatesIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist ein Platzhalter-Controller, der oft in Modulen enthalten ist, aber in der Kernfunktionalität dieses spezifischen Moduls nicht aktiv verwendet wird. Er könnte für Routing-Zwecke oder als Standard-Einstiegspunkt vorhanden sein, aber die primäre Logik für Kursaktualisierungen befindet sich in `cronjob.php`.

#### Back-Office-Admin-Controller

Dieses Modul implementiert keine benutzerdefinierten Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/`. Es interagiert direkt mit der Kernklasse `Currency` von PrestaShop, um Wechselkurse zu aktualisieren.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Admin-Templates (`views/templates/admin/`)

- **`views/templates/admin/admin.tpl`**
  - **Zweck:** Dieses Template wird verwendet, um das Konfigurationsformular des Moduls im PrestaShop Back Office zu rendern. Es zeigt die Eingabefelder für MyPresta.eu-Updates, die CRON-Job-URL, die Margenanpassung und die manuelle Aktualisierungsschaltfläche an.
  - **Kontext:** Gerendert durch die `getContent()`-Methode der Hauptmoduldatei `bderates.php`.
  - **Schlüsselelemente:** Formularelemente für `mypresta_updates`, `update_`, `updatev_`, `currency_` Einstellungen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen direkt in der PrestaShop-Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie:

- `BDERATES_MYPRESTA_ID`
- `BDERATES_MYPRESTA_EMAIL`
- `BDERATES_MARGIN`
- `BDERATES_LAST_UPDATE`

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird von diesem Modul nicht aktiv für die visuelle Ausgabe verwendet, aber oft von Modulen für die allgemeine Einrichtung oder das Laden von Assets registriert. |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Wird von diesem Modul nicht aktiv für die visuelle Ausgabe verwendet. |
| `displayLeftColumn` | In der linken Spalte der Front-Office-Seiten. | Wird von diesem Modul nicht aktiv für die visuelle Ausgabe verwendet. |
| `displayFooter` | Im Footer-Bereich jeder Front-Office-Seite. | Wird von diesem Modul nicht aktiv für die visuelle Ausgabe verwendet. |
| `displayProductAdditionalInfo` | Auf der Produktseite, unterhalb der Hauptproduktinformationen. | Wird von diesem Modul nicht aktiv für die visuelle Ausgabe verwendet. |
| `actionUpdateCurrency` | Wird ausgelöst, nachdem der Wechselkurs einer Währung aktualisiert wurde. | Dieses Modul *löst* diesen Hook aus, wenn es Währungskurse aktualisiert, wodurch andere Module auf die Änderung reagieren können. |
| `actionCronJob` | Ein benutzerdefinierter Hook, der oft von Modulen verwendet wird, um ihre CRON-Aufgaben zu registrieren. | Der `cronjob.php`-Controller des Moduls ist der primäre Mechanismus für geplante Updates, aber dieser Hook könnte für Kompatibilität oder zukünftige Erweiterungen registriert werden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „BdE Wechselkurse & Währung (Bank von Spanien)“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
