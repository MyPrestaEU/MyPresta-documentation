---
title: "Erinnerung an unbezahlte Bestellungen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Erinnerung an unbezahlte Bestellungen“ von MyPresta.eu."
sidebar:
  label: "Erinnerung an unbezahlte Bestellungen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Unpaid order reminder auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/unpaid-order-reminder.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/unpaid-order-reminder/)
>
> ---


# Erinnerung an unbezahlte Bestellungen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Stellen Sie sicher, dass die Cron-Job-Funktionalität Ihres Servers aktiviert und korrekt konfiguriert ist, damit die automatischen Erinnerungen des Moduls funktionieren.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Erinnerung an unbezahlte Bestellungen“ bietet mehrere Konfigurationsbildschirme, um Ihre Erinnerungseinstellungen zu verwalten, den Verlauf anzuzeigen und abgemeldete Kunden zu bearbeiten.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Erinnerung an unbezahlte Bestellungen)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten des Moduls einstellen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, das Modul zu aktivieren oder zu deaktivieren, den Cron-Job zu konfigurieren und die allgemeinen Einstellungen für Ihre Erinnerungs-E-Mails zu verwalten.
- **Auswirkung einer Änderung dieser Einstellung:** Steuert die Gesamtfunktionalität und Automatisierung des Erinnerungssystems.

#### Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Schaltet das gesamte Modul „Erinnerung an unbezahlte Bestellungen“ ein oder aus.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, Erinnerungen gemäß Ihren definierten Regeln und dem Cron-Job zu senden.
    - *Wenn deaktiviert:* Es werden keine Erinnerungen gesendet, und das Modul ist inaktiv.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, nachdem Sie Ihre Erinnerungsregeln eingerichtet haben, um unbezahlte Bestellungen wiederherzustellen. Deaktivieren Sie es, wenn Sie alle Erinnerungen vorübergehend für Wartungsarbeiten oder eine bestimmte Kampagne stoppen müssen.
- **Cron-Job-URL:**

  - **Was diese Einstellung bewirkt:** Zeigt die eindeutige URL an, die der Cron-Job Ihres Servers regelmäßig ausführen muss. Diese URL veranlasst das Modul, nach unbezahlten Bestellungen zu suchen und Erinnerungen zu senden.
  - **Auswirkung einer Änderung dieser Einstellung:** Diese URL ist entscheidend für die Automatisierung des Moduls. Ohne den Aufruf durch einen Cron-Job werden keine Erinnerungen automatisch gesendet.
  - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie im Cron-Job-Manager Ihres Hosting-Kontrollpanels ein.
  - **Händlerszenario / Beispiel:** Sie richten dies typischerweise einmal während der Erstkonfiguration ein. Zum Beispiel könnten Sie Ihren Server so konfigurieren, dass er diese URL jede Stunde aufruft, um zeitnahe Erinnerungen zu gewährleisten.
- **Abmeldelink in E-Mail:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob ein Abmeldelink in den Erinnerungs-E-Mails enthalten ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können auf einen Link in der E-Mail klicken, um sich von zukünftigen Erinnerungen an unbezahlte Bestellungen abzumelden.
    - *Wenn deaktiviert:* Kunden können sich nicht einfach abmelden, was zu Frustration führen oder Ihre E-Mails als Spam markieren könnte.
  - **Empfohlener Wert:** JA (Dringend empfohlen für Compliance und Kundenzufriedenheit).
  - **Händlerszenario / Beispiel:** Fügen Sie dies immer hinzu, um Kunden die Kontrolle zu geben und einen guten Absenderruf zu bewahren.
- **Bestellstatus zur Erinnerung:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl, welche spezifischen Bestellstatus eine Erinnerung auslösen sollen. Typischerweise sind dies Status, die darauf hinweisen, dass eine Bestellung auf Zahlung wartet (z. B. „Warten auf Banküberweisung“, „Warten auf Scheckzahlung“).
  - **Auswirkung einer Änderung dieser Einstellung:** Nur Bestellungen mit den ausgewählten Status werden für Erinnerungen berücksichtigt.
  - **Empfohlener Wert:** Wählen Sie alle Status aus, die eine auf Zahlung wartende Bestellung darstellen.
  - **Händlerszenario / Beispiel:** Wenn Sie „Warten auf Banküberweisung“ und „Warten auf Scheckzahlung“ verwenden, wählen Sie beide aus. Wenn Sie einen benutzerdefinierten Status wie „Zahlungs-Gateway ausstehend“ haben, fügen Sie diesen ebenfalls hinzu.
- **Bestellstatus zum Stoppen von Erinnerungen:**

  - **Was diese Einstellung bewirkt:** Definiert, welche Bestellstatus, wenn sie erreicht werden, weitere Erinnerungen für diese spezifische Bestellung stoppen sollen. Dies umfasst normalerweise Status wie „Zahlung akzeptiert“, „Versandt“ oder „Storniert“.
  - **Auswirkung einer Änderung dieser Einstellung:** Sobald eine Bestellung einen dieser Status erreicht, sendet das Modul keine weiteren Erinnerungen mehr dafür, wodurch unnötige oder verwirrende E-Mails verhindert werden.
  - **Empfohlener Wert:** Wählen Sie alle Status aus, die darauf hinweisen, dass die Zahlung eingegangen ist, die Bestellung bearbeitet wurde oder die Bestellung nicht mehr gültig ist (z. B. „Zahlung akzeptiert“, „Storniert“, „Erstattet“).
  - **Händlerszenario / Beispiel:** Wenn ein Kunde eine Bestellung bezahlt, möchten Sie nicht, dass er eine weitere Erinnerung erhält. Die Auswahl von „Zahlung akzeptiert“ stellt dies sicher.

#### Erinnerungsregeln

In diesem Abschnitt definieren Sie die eigentlichen Erinnerungs-E-Mails. Sie können mehrere Regeln erstellen, jede mit unterschiedlichem Timing und E-Mail-Inhalt.

- **Neue Erinnerungsregel hinzufügen:**
  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Erstellen eines neuen Satzes von Erinnerungsparametern.
  - **Auswirkung einer Änderung dieser Einstellung:** Öffnet ein Formular zur Definition einer neuen Erinnerungs-E-Mail.
  - **Empfohlener Wert:** Erstellen Sie mindestens eine Regel.
  - **Händlerszenario / Beispiel:** Sie möchten möglicherweise eine erste Erinnerung nach 24 Stunden und eine zweite, dringendere nach 72 Stunden senden.

Beim Hinzufügen/Bearbeiten einer Regel konfigurieren Sie:

- **Tage nach Bestellerstellung:**

  - **Was diese Einstellung bewirkt:** Gibt an, wie viele Tage nach der Bestellung diese spezielle Erinnerungs-E-Mail gesendet werden soll.
  - **Auswirkung einer Änderung dieser Einstellung:** Steuert den Zeitpunkt der Erinnerung.
  - **Empfohlener Wert:** Beginnen Sie mit 1 oder 2 Tagen für die erste Erinnerung.
  - **Händlerszenario / Beispiel:** Auf „1“ setzen für eine erste Erinnerung 24 Stunden nach der Bestellung. Auf „3“ setzen für eine zweite Erinnerung 3 Tage nach der Bestellung.
- **E-Mail-Betreff:**

  - **Was diese Einstellung bewirkt:** Die Betreffzeile der Erinnerungs-E-Mail.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies ist, was Kunden in ihrem Posteingang sehen. Ein klarer, prägnanter Betreff erhöht die Öffnungsraten.
  - **Empfohlener Wert:** So etwas wie „Erinnerung: Ihre unbezahlte Bestellung bei [Shop-Name]“ oder „Aktion erforderlich: Schließen Sie Ihre Bestellung #[Bestell-ID] ab“.
  - **Händlerszenario / Beispiel:** „Vergessen Sie Ihre Bestellung bei MyPresta.eu nicht!“
- **E-Mail-Inhalt:**

  - **Was diese Einstellung bewirkt:** Der Hauptteil der Erinnerungs-E-Mail. Sie können Variablen (wie `{customer_name}`, `{order_id}`, `{shop_name}`) verwenden, um die Nachricht zu personalisieren.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies ist die Kernbotschaft an Ihren Kunden. Ein freundlicher, hilfreicher Ton ist am besten.
  - **Empfohlener Wert:** Fügen Sie eine Begrüßung hinzu, erwähnen Sie die unbezahlte Bestellung, geben Sie Anweisungen, wie bezahlt werden kann oder wo Zahlungsdetails zu finden sind, und bieten Sie Hilfe an.
  - **Händlerszenario / Beispiel:** „Sehr geehrte/r {customer\_name}, dies ist eine freundliche Erinnerung an Ihre kürzliche Bestellung #{order\_id} bei {shop\_name}. Es scheint, dass die Zahlung für diese Bestellung noch aussteht. Bitte schließen Sie Ihre Zahlung so bald wie möglich ab, um sicherzustellen, dass Ihre Bestellung bearbeitet wird. Sie können Ihre Bestelldetails hier einsehen: [Link zur Bestellhistorie]. Wenn Sie Fragen haben, kontaktieren Sie uns bitte.“
- **Aktiv:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert diese spezifische Erinnerungsregel.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Diese Erinnerung wird gemäß ihrem Timing gesendet.
    - *Wenn deaktiviert:* Diese Erinnerung wird nicht gesendet, auch wenn das Modul aktiv ist.
  - **Empfohlener Wert:** JA für aktive Regeln.
  - **Händlerszenario / Beispiel:** Sie könnten eine Regel deaktivieren, wenn Sie neue Inhalte testen oder eine bestimmte Erinnerung vorübergehend pausieren möchten.

### 2.2 Verwaltung der Bestellerinnerungen (Back Office > Module > Erinnerung an unbezahlte Bestellungen > Bestellerinnerungen)

Dieser spezielle Bildschirm, der über das Modulmenü im Back Office zugänglich ist, ermöglicht es Ihnen, die Bestellungen anzuzeigen und zu verwalten, die derzeit für Erinnerungen in Frage kommen.

- **Bildschirmname & Menüpfad:** **Bestellerinnerungen** (unter dem Menüpunkt „Erinnerung an unbezahlte Bestellungen“).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Liste von Bestellungen an, die derzeit Ihren Kriterien für „Bestellstatus zur Erinnerung“ entsprechen.
  - **Raster-/Verwaltungsansicht:** Sie sehen eine Tabelle mit Spalten wie Bestell-ID, Kundenname, Bestelldatum, Aktueller Status und möglicherweise das nächste Erinnerungsdatum.
  - **Aktionen:** Sie haben möglicherweise Aktionen, um manuell eine Erinnerung für eine bestimmte Bestellung zu senden oder eine Bestellung von zukünftigen Erinnerungen auszuschließen.
- **Auswirkung von Änderungen:**
  - **Manuelles Senden einer Erinnerung:** Versendet sofort die nächste geplante Erinnerungs-E-Mail für diese Bestellung.
  - **Ausschließen einer Bestellung:** Verhindert, dass das Modul weitere Erinnerungen für diese spezifische Bestellung sendet, auch wenn ihr Status immer noch den Erinnerungskriterien entspricht.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diese Liste regelmäßig, um einen Überblick über ausstehende unbezahlte Bestellungen zu erhalten. Verwenden Sie die Option zum manuellen Senden, wenn ein Kunde anruft und Sie ihm die Zahlungsdetails sofort erneut senden möchten. Schließen Sie Bestellungen aus, wenn Sie eine Sondervereinbarung mit einem Kunden getroffen haben oder wenn eine Bestellung problematisch ist.

### 2.3 Verlauf der Bestellerinnerungen (Back Office > Module > Erinnerung an unbezahlte Bestellungen > Verlauf)

Dieser Bildschirm bietet ein Protokoll aller Erinnerungs-E-Mails, die vom Modul gesendet wurden.

- **Bildschirmname & Menüpfad:** **Verlauf** (unter dem Menüpunkt „Erinnerung an unbezahlte Bestellungen“).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Tabelle mit Details zu jeder gesendeten Erinnerung:
  - Spalten umfassen typischerweise: Bestell-ID, Kundenname, E-Mail-Adresse, Erinnerungsregel (welche Regel sie ausgelöst hat), Sendedatum und möglicherweise den E-Mail-Betreff.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschütztes Protokoll. Es werden hier keine direkten Änderungen vorgenommen, aber es liefert wertvolle Einblicke.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, um zu überprüfen, ob Erinnerungen korrekt gesendet werden. Wenn ein Kunde behauptet, er habe keine Erinnerung erhalten, können Sie diesen Verlauf überprüfen, um zu bestätigen, ob sie versandt wurde.

### 2.4 Abgemeldete Kunden (Back Office > Module > Erinnerung an unbezahlte Bestellungen > Abgemeldete Kunden)

Dieser Bildschirm listet Kunden auf, die sich vom Empfang von Erinnerungen an unbezahlte Bestellungen abgemeldet haben.

- **Bildschirmname & Menüpfad:** **Abgemeldete Kunden** (unter dem Menüpunkt „Erinnerung an unbezahlte Bestellungen“).
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Tabelle mit:
  - Spalten umfassen typischerweise: Kunden-ID, Kundenname, E-Mail-Adresse und Abmeldedatum.
  - **Aktionen:** Sie haben möglicherweise eine Option, einen Kunden manuell aus dieser Liste zu entfernen, wodurch er effektiv wieder für Erinnerungen angemeldet wird (mit Vorsicht und nur auf Anfrage des Kunden verwenden).
- **Auswirkung von Änderungen:**
  - **Entfernen aus der Liste:** Der Kunde ist wieder berechtigt, Erinnerungen zu erhalten, wenn sein Bestellstatus übereinstimmt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überwachen Sie diese Liste, um Kundenpräferenzen zu verstehen. Melden Sie einen Kunden nur dann wieder an, wenn er dies ausdrücklich wünscht.

### 2.5 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Schaltet die Modulfunktionalität ein/aus. |
|  | Cron-Job-URL | Kopieren & Konfigurieren | Wesentlich für den automatischen Versand von Erinnerungen. |
|  | Abmeldelink in E-Mail | JA | Ermöglicht Kunden die Abmeldung, verbessert den Absenderruf. |
|  | Bestellstatus zur Erinnerung | Warten auf Banküberweisung, Warten auf Scheck usw. | Definiert, welche Bestellstatus Erinnerungen auslösen. |
|  | Bestellstatus zum Stoppen von Erinnerungen | Zahlung akzeptiert, Storniert usw. | Verhindert Erinnerungen für bezahlte oder ungültige Bestellungen. |
|  | **Erinnerungsregeln** |  |  |
|  | Tage nach Bestellerstellung | 1, 3, 7 (Beispiel) | Legt den Zeitpunkt für jede Erinnerungs-E-Mail fest. |
|  | E-Mail-Betreff | „Erinnerung: Ihre unbezahlte Bestellung…“ | Betreffzeile der Erinnerungs-E-Mail. |
|  | E-Mail-Inhalt | Personalisierte Nachricht mit Variablen | Hauptteil der Erinnerungs-E-Mail. |
|  | Aktiv (für jede Regel) | JA | Aktiviert/deaktiviert einzelne Erinnerungsregeln. |
| **Bestellerinnerungen** | (Liste der berechtigten Bestellungen) | N/A | Übersicht der auf Zahlung wartenden Bestellungen. |
|  | Manuelle Erinnerung senden | N/A | Sendet sofort die nächste Erinnerung für die ausgewählte Bestellung. |
|  | Bestellung ausschließen | N/A | Verhindert zukünftige Erinnerungen für die ausgewählte Bestellung. |
| **Verlauf** | (Protokoll der gesendeten Erinnerungen) | N/A | Audit-Trail aller versendeten Erinnerungs-E-Mails. |
| **Abgemeldete Kunden** | (Liste der abgemeldeten Kunden) | N/A | Zeigt Kunden, die sich von Erinnerungen abgemeldet haben. |
|  | Aus Abmeldeliste entfernen | N/A | Meldet Kunden wieder für Erinnerungen an (mit Vorsicht verwenden). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Erinnerungen werden nicht gesendet. Was sollte ich zuerst überprüfen?**
**A1:**

- **Modul aktiviert:** Gehen Sie zu **Module > Modul-Manager > Erinnerung an unbezahlte Bestellungen** und stellen Sie sicher, dass die Einstellung „Modul aktivieren“ auf JA steht.
- **Cron-Job:** Das häufigste Problem. Sie *müssen* den Cron-Job auf Ihrem Hosting-Server einrichten. Kopieren Sie die „Cron-Job-URL“ von der Konfigurationsseite des Moduls und fügen Sie sie in den Cron-Job-Manager Ihres Hosting-Kontrollpanels ein. Stellen Sie sicher, dass er häufig ausgeführt wird (z. B. jede Stunde). Wenn Sie unsicher sind, wie das geht, wenden Sie sich an Ihren Hosting-Anbieter.
- **Bestellstatus:** Überprüfen Sie die „Bestellstatus zur Erinnerung“ und „Bestellstatus zum Stoppen von Erinnerungen“ in der Modulkonfiguration. Stellen Sie sicher, dass die Bestellungen, für die Sie Erinnerungen erwarten, einen in der Liste „zur Erinnerung“ ausgewählten Status haben und keinen Status in der Liste „zum Stoppen“ erreicht haben.
- **Erinnerungsregeln aktiv:** Stellen Sie sicher, dass die einzelnen von Ihnen erstellten Erinnerungsregeln als „Aktiv“ markiert sind.

**F2: Kunden erhalten zu viele Erinnerungen oder Erinnerungen, nachdem sie bereits bezahlt haben. Wie behebe ich das?**
**A2:**

- **„Bestellstatus zum Stoppen von Erinnerungen“:** Dies ist entscheidend. Stellen Sie sicher, dass alle Status, die eine bezahlte oder abgeschlossene Bestellung anzeigen (z. B. „Zahlung akzeptiert“, „Versandt“, „Storniert“, „Erstattet“), in dieser Einstellung ausgewählt sind. Dies weist das Modul an, keine weiteren Erinnerungen zu senden, sobald die Bestellung einen dieser Zustände erreicht.
- **Timing der Erinnerungsregel:** Überprüfen Sie die „Tage nach Bestellerstellung“ für jede Erinnerungsregel. Stellen Sie sicher, dass sie angemessen verteilt sind und sich nicht so überschneiden, dass zu viele E-Mails zu schnell gesendet werden.

**F3: Kann ich die E-Mail-Vorlagen anpassen?**
**A3:** Ja, das Modul ermöglicht es Ihnen, den E-Mail-Betreff und -Inhalt direkt in den Einstellungen der Erinnerungsregel anzupassen. Sie können spezifische Variablen (wie `{customer_name}`, `{order_id}`, `{shop_name}`) verwenden, um die Nachricht zu personalisieren. Für eine erweiterte visuelle Anpassung müsste ein Entwickler die zugrunde liegenden E-Mail-Vorlagendateien (im Verzeichnis `mails/` Ihrer PrestaShop-Installation, unter Verwendung der Vorlagenstruktur des Moduls als Leitfaden) ändern.

**F4: Der Abmeldelink funktioniert nicht, oder Kunden erhalten immer noch E-Mails, nachdem sie sich abgemeldet haben.**
**A4:**

- **Abmeldelink aktiviert:** Stellen Sie sicher, dass „Abmeldelink in E-Mail“ in der Hauptkonfiguration des Moduls auf JA gesetzt ist.
- **Liste „Abgemeldete Kunden“ überprüfen:** Gehen Sie zu **Module > Erinnerung an unbezahlte Bestellungen > Abgemeldete Kunden**. Überprüfen Sie, ob die E-Mail-Adresse des Kunden in dieser Liste erscheint. Wenn nicht, hat er sich möglicherweise nicht erfolgreich abgemeldet.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung > Cache leeren**), nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F5: Was passiert, wenn ein Kunde mehrere unbezahlte Bestellungen hat?**
**A5:** Das Modul behandelt jede unbezahlte Bestellung einzeln. Wenn ein Kunde zwei separate unbezahlte Bestellungen hat, erhält er für jede Bestellung Erinnerungen gemäß Ihren definierten Regeln, solange diese Bestellungen die Kriterien erfüllen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Erinnerung an unbezahlte Bestellungen“, der für Entwickler und Webmaster gedacht ist.

### 4.1 Architekturübersicht

Das Modul „Erinnerung an unbezahlte Bestellungen“ (`oreminders`) folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es konzentriert sich hauptsächlich auf die Back-Office-Administration für die Konfiguration und einen Front-Office-Cron-Job für die automatisierte Verarbeitung. Es erweitert `Module` für seine Kernfunktionalität und verwendet benutzerdefinierte `AdminController`-Klassen zur Verwaltung von Erinnerungen, Verlauf und abgemeldeten Kunden. Die E-Mail-Vorlagen werden über einen benutzerdefinierten Manager verwaltet, und die Konfiguration wird in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/CronJob.php`
  - **Klassenname & Elternklasse:** `OremindersCronJobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem serverseitigen Cron-Job aufgerufen zu werden. Er ist der Einstiegspunkt für die automatisierte Logik des Moduls. Bei Ausführung durchläuft er unbezahlte Bestellungen, prüft sie anhand definierter Erinnerungsregeln und versendet Erinnerungs-E-Mails. Er gibt typischerweise eine einfache Erfolgs-/Fehlermeldung oder eine Protokollausgabe zurück.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `OremindersIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist wahrscheinlich ein Platzhalter oder ein Fallback-Controller. In vielen Modulen dient `index.php` in `controllers/front` als Standard- oder einfacher Einstiegspunkt, wenn keine spezifische Aktion angefordert wird. Er könnte die grundlegende Modulanzeige oder Weiterleitung handhaben, wenn das Modul eine Front-Office-Präsenz hätte. Angesichts der Natur des Moduls erfolgt die primäre Front-Office-Interaktion über `CronJob.php`.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminOrderReminders.php`
  - **Klassenname & Elternklasse:** `AdminOrderRemindersController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Verwaltet die Liste „Bestellerinnerungen“. Dieser Controller ist für die Anzeige einer Liste von Bestellungen verantwortlich, die derzeit für Erinnerungen basierend auf der Modulkonfiguration in Frage kommen. Er bietet Aktionen zum manuellen Senden von Erinnerungen oder zum Ausschließen spezifischer Bestellungen.
- `controllers/admin/AdminOrderRemindersHistory.php`
  - **Klassenname & Elternklasse:** `AdminOrderRemindersHistoryController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Verwaltet das Protokoll „Verlauf“. Dieser Controller zeigt eine schreibgeschützte Liste aller Erinnerungs-E-Mails an, die vom Modul erfolgreich gesendet wurden, einschließlich Details wie Bestell-ID, Kunde und Sendedatum.
- `controllers/admin/AdminOrderRemindersUnsub.php`
  - **Klassenname & Elternklasse:** `AdminOrderRemindersUnsubController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Verwaltet die Liste „Abgemeldete Kunden“. Dieser Controller zeigt Kunden an, die sich vom Empfang von Erinnerungen abgemeldet haben, und ermöglicht deren erneute Anmeldung (falls erforderlich).
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse:** `AdminOremindersIndexController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Ähnlich wie der Front-Office `index.php` könnte dies als Standard- oder Fallback-Admin-Controller dienen. Er könnte potenziell die Hauptmodulkonfiguration handhaben, wenn `getContent()` in der Hauptmoduldatei darauf umleitet, oder wenn er für eine spezifische, einfache Admin-Aktion verwendet wird.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar listet keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das Modul möglicherweise `ObjectModel` direkt in seiner Hauptmoduldatei oder in den Admin-Controllern verwendet oder Daten über direkte Datenbankabfragen oder durch Erweiterung bestehender PrestaShop-Kernmodelle (z. B. `Order`, `Customer`) verwaltet.

Wenn benutzerdefinierte Daten gespeichert werden, geschieht dies wahrscheinlich über `ps_configuration` für Einstellungen und möglicherweise benutzerdefinierte Datenbanktabellen, die während der Installation erstellt wurden (obwohl keine SQL-Dateien aufgeführt wurden, würde die Tabellenerstellung inline in `install()` erfolgen).

### 4.4 JavaScript-Assets (`views/js/`)

- `oreminders/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Dieses Skript bietet wahrscheinlich dynamische Funktionen für die E-Mail-Vorlagenverwaltungsoberfläche innerhalb der Modulkonfiguration. Dies könnte umfassen:
    - Dynamisches Hinzufügen/Entfernen von Erinnerungsregeln.
    - Bearbeitung von AJAX-Anfragen zum Speichern/Laden von E-Mail-Vorlagen.
    - Implementierung eines Rich-Text-Editors (z. B. TinyMCE-Integration) für E-Mail-Inhalte.
    - Verwaltung der Variableneinfügung in E-Mail-Vorlagen.
    - Clientseitige Validierung für Formularfelder im Zusammenhang mit E-Mail-Regeln.

### 4.5 CSS-Stylesheets (`views/css/`)

- `oreminders/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Details:** Dieses Stylesheet bietet spezifisches Styling für die E-Mail-Vorlagenverwaltungsoberfläche in der Back-Office-Konfiguration des Moduls. Es würde Stile definieren für:
    - Layout der Formulare für Erinnerungsregeln.
    - Styling von Eingabefeldern, Schaltflächen und Textbereichen innerhalb des Vorlagen-Editors.
    - Sicherstellung eines konsistenten Erscheinungsbilds mit dem PrestaShop Back Office-Theme.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Suchen Sie nach spezifischen Klassen, die mit `oreminders-` oder `email-templates-manager-` in den Admin-Vorlagen des Moduls beginnen, um anpassbare Elemente zu identifizieren.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

- `oreminders/views/templates/hook/form.tpl`
  - **Hook:** Potenziell `displayAdminModuleConfigure` oder ähnlich, wenn für ein kleines Formular in einem Hook-Kontext verwendet. Wahrscheinlicher ist es eine generische Formularvorlage, die intern verwendet wird.
  - **Ausgabe:** Rendert eine generische Formularstruktur.
- `oreminders/views/templates/hook/header.tpl`
  - **Hook:** `displayHeader` (Front-Office).
  - **Ausgabe:** Wird verwendet, um notwendige CSS- oder JavaScript-Dateien im `<head>`-Bereich des Front-Office einzubinden, falls das Modul Front-End-Komponenten hatte (z. B. für die Abmeldeseite).
- `oreminders/views/templates/hook/identity.tpl`
  - **Hook:** Name unklar, aber `displayCustomerAccount` oder ähnlich zur Anzeige kundenspezifischer Informationen, oder vielleicht im Zusammenhang mit dem Abmeldeprozess.
  - **Ausgabe:** Könnte eine Nachricht oder ein Formular im Zusammenhang mit der Kundenidentität oder -präferenzen rendern.

#### Admin-Vorlagen (`views/templates/admin/`)

- `oreminders/lib/emailTemplatesManager/views/buttonManager.tpl`
  - **Kontext:** Wird innerhalb des E-Mail-Vorlagenmanagers verwendet.
  - **Ausgabe:** Rendert Schaltflächen zur Verwaltung von E-Mail-Vorlagen (z. B. „Neue Regel hinzufügen“, „Speichern“, „Löschen“).
- `oreminders/lib/emailTemplatesManager/views/createTemplateForm.tpl`
  - **Kontext:** Wird innerhalb des E-Mail-Vorlagenmanagers verwendet.
  - **Ausgabe:** Rendert das Formular zum Erstellen einer neuen Erinnerungs-E-Mail-Vorlage/Regel.
- `oreminders/lib/emailTemplatesManager/views/editTemplateForm.tpl`
  - **Kontext:** Wird innerhalb des E-Mail-Vorlagenmanagers verwendet.
  - **Ausgabe:** Rendert das Formular zum Bearbeiten einer vorhandenen Erinnerungs-E-Mail-Vorlage/Regel.
- `oreminders/lib/emailTemplatesManager/views/mainForm.tpl`
  - **Kontext:** Wird innerhalb des E-Mail-Vorlagenmanagers verwendet.
  - **Ausgabe:** Die Haupt-Wrapper-Vorlage für die E-Mail-Vorlagenverwaltungsoberfläche, die wahrscheinlich `buttonManager`, `createTemplateForm` und `editTemplateForm` kombiniert.
- `oreminders/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Kontext:** Wird innerhalb des E-Mail-Vorlagenmanagers verwendet.
  - **Ausgabe:** Eine wiederverwendbare Vorlage zum Rendern eines `<select>`-Dropdown-Eingabefeldes, wahrscheinlich zur Auswahl von Bestellstatus oder anderen Optionen.
- `oreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
  - **Kontext:** Wird vom `AdminOrderRemindersController` für seine Formularansichten verwendet (z. B. wenn es ein Hinzufügen-/Bearbeiten-Formular für einen Bestellerinnerungseintrag gibt, obwohl es sich hauptsächlich um einen Listencontroller handelt).
  - **Ausgabe:** Rendert ein Standard-PrestaShop-Admin-Formular.
- `oreminders/views/templates/admin/order_reminders/helpers/list/list_action_email.tpl`
  - **Kontext:** Wird vom `AdminOrderRemindersController` in seiner Listenansicht verwendet.
  - **Ausgabe:** Rendert eine spezifische Aktionsschaltfläche oder einen Link innerhalb der Liste der Bestellerinnerungen, wahrscheinlich für „E-Mail senden“ oder „E-Mail anzeigen“.
- `oreminders/views/templates/admin/script.tpl`
  - **Kontext:** Admin Back Office.
  - **Ausgabe:** Enthält wahrscheinlich Inline-JavaScript-Code oder Konfigurationsvariablen, die von der Back-Office-Oberfläche benötigt werden, möglicherweise für AJAX-Aufrufe oder dynamische UI-Elemente.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Die Modulbeschreibung und das Dateiverzeichnis listen keine SQL-Dateien für die Erstellung benutzerdefinierter Tabellen explizit auf. Basierend auf den Admin-Controllern interagiert das Modul jedoch wahrscheinlich mit den folgenden (entweder benutzerdefinierten Tabellen oder `ps_configuration` für Einstellungen):

- `ps_configuration`: Speichert alle Moduleinstellungen (z. B. `OREMINDERS_ENABLED`, `OREMINDERS_CRON_URL`, `OREMINDERS_UNSUB_LINK`, `OREMINDERS_STATUSES_REMIND`, `OREMINDERS_STATUSES_STOP` und serialisierte Daten für einzelne Erinnerungsregeln).
- `ps_or` (oder ähnlich, verwaltet von `AdminOrderRemindersController`): Wahrscheinlich eine benutzerdefinierte Tabelle zur Speicherung von Informationen über aktuell erinnerte Bestellungen oder zur Markierung von Bestellungen als ausgeschlossen.
- `ps_or_history` (oder ähnlich, verwaltet von `AdminOrderRemindersHistoryController`): Eine benutzerdefinierte Tabelle zur Protokollierung jeder gesendeten Erinnerungs-E-Mail, einschließlich `id_order`, `id_customer`, `email`, `id_reminder_rule`, `date_sent`.
- `ps_or_ounsub` (oder ähnlich, verwaltet von `AdminOrderRemindersUnsubController`): Eine benutzerdefinierte Tabelle zur Speicherung von Kunden-IDs oder E-Mail-Adressen derjenigen, die sich von Erinnerungen abgemeldet haben.

#### Registrierte Hooks-Tabelle

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Im `<head>`-Bereich aller Front-Office-Seiten. | Zum Einbinden modulspezifischer CSS/JS für Front-Office-Komponenten (z. B. Abmeldeseite). |
| `displayAdminModuleConfigure` | Back-Office | Beim Anzeigen der Hauptkonfigurationsseite des Moduls. | Zum Rendern des Hauptkonfigurationsformulars des Moduls (`getContent()`-Methode). |
| `actionValidateOrder` | Back-Office | Nachdem eine Bestellung erfolgreich validiert wurde. | Potenziell zur Initialisierung der Erinnerungsverfolgung für neue Bestellungen verwendet, obwohl der Cron-Job der primäre Auslöser ist. |
| `actionOrderStatusUpdate` | Back-Office | Wenn der Status einer Bestellung geändert wird. | Um zu überprüfen, ob der neue Status einer Bestellung Erinnerungen stoppen sollte (z. B. wenn er „Zahlung akzeptiert“ wird). |
| `actionCronJob` | Back-Office (über Front Controller) | Wird vom Cron-Job des Servers ausgeführt. | Der Kern-Hook, der die Logik des Moduls auslöst, um unbezahlte Bestellungen zu finden und Erinnerungen zu senden. |
| (Implizite Hooks für Admin-Tabs) | Back-Office | Beim Rendern des Back-Office-Menüs. | Zum Hinzufügen der benutzerdefinierten Menüpunkte des Moduls (Bestellerinnerungen, Verlauf, Abgemeldete Kunden). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Erinnerung an unbezahlte Bestellungen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
