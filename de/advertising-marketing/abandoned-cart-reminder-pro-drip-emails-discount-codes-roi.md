---
title: "Abandoned Cart Reminder Pro – Drip-E-Mails, Rabattcodes & ROI - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Abandoned Cart Reminder Pro – Drip-E-Mails, Rabattcodes & ROI“ von MyPresta.eu."
sidebar:
  label: "Abandoned Cart Reminder Pro – Drip-E-Mails, Rabattcodes & ROI - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Abandoned Cart Reminder Pro – drip emails, discount codes & ROI auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi/)
>
> ---


# Abandoned Cart Reminder Pro – Drip-E-Mails, Rabattcodes & ROI

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5 (Das Modul ist für PHP 5.6+ geschrieben, aber PrestaShop 9.x erfordert PHP 8.1+ für den Shop selbst. Wir empfehlen, die höchste stabile PHP-Version zu verwenden, die mit Ihrer PrestaShop-Installation kompatibel ist, bis zu 8.5.)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind erforderlich. Ihre Hosting-Umgebung muss auch Cron-Jobs (geplante Aufgaben) unterstützen, damit das Modul korrekt funktioniert, da es Erinnerungen im Hintergrund verarbeitet.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Abandoned Cart Reminder Pro“ bietet eine umfassende Reihe von Tools zur Verwaltung Ihrer Kampagnen. Sie werden hauptsächlich mit den dedizierten Menüpunkten im PrestaShop Back Office interagieren.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Obwohl das Modul dedizierte Admin-Bildschirme hat, kann die anfängliche Schaltfläche „Konfigurieren“ vom Modul-Manager zu einer grundlegenden Einrichtung oder Weiterleitung führen. Das Modul nutzt den PrestaShop-Konfigurationsschlüssel `PS_SSL_ENABLED`.

-   **Was diese Einstellung bewirkt:** Diese Einstellung wird nicht direkt vom Modul gesteuert, sondern ist eine zentrale PrestaShop-Einstellung, die angibt, ob Ihr Shop HTTPS (sichere Verbindung) verwendet. Das Modul verlässt sich darauf, um korrekte, sichere Links in Ihren Erinnerungs-E-Mails zu generieren.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn `PS_SSL_ENABLED` auf JA steht:* Alle vom Modul generierten Links (z.B. zu abgebrochenen Warenkörben, Abmeldeseiten) verwenden `https://`, was ein sicheres und vertrauenswürdiges Erlebnis für Ihre Kunden gewährleistet.
    *   *Wenn `PS_SSL_ENABLED` auf NEIN steht:* Links könnten mit `http://` generiert werden, was weniger sicher ist und Browserwarnungen auslösen kann, wodurch das Kundenvertrauen und die Konversionsraten potenziell sinken.
-   **Empfohlener Wert:** **JA**. Ihr Shop sollte aus Sicherheits- und SEO-Gründen immer SSL verwenden. Stellen Sie sicher, dass Ihr gesamter Shop über HTTPS läuft.
-   **Händlerszenario / Beispiel:** Wenn Ihre Kunden eine E-Mail mit einem `http://`-Link zu ihrem Warenkorb erhalten, könnte ihr Browser eine „Nicht sicher“-Warnung anzeigen. Dies kann sie zögern lassen, auf den Link zu klicken oder den Kauf abzuschließen, selbst wenn Ihr Checkout sicher ist. Verwenden Sie immer HTTPS.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Sobald das Modul installiert ist, finden Sie einen neuen Menüpunkt in Ihrem PrestaShop Back Office, typischerweise unter **Marketing** oder einem dedizierten Abschnitt für „Abandoned Cart Reminder Pro“. Dieses Menü führt zu mehreren Unterabschnitten:

#### 2.2.1 Kampagnen (Back Office > Abandoned Cart Reminder Pro > Kampagnen)

Hier erstellen, verwalten und optimieren Sie Ihre Kampagnen für abgebrochene Warenkörbe.

-   **Bildschirmname & Menüpfad:** **Abandoned Cart Reminder Pro > Kampagnen**
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Kampagnenliste:** Eine Tabelle, die alle Ihre aktiven und inaktiven Kampagnen anzeigt, einschließlich ihres Namens, Status und wichtiger Statistiken.
    *   **Neue Kampagne hinzufügen:** Klicken Sie hier, um eine neue mehrstufige E-Mail-Sequenz zu erstellen.
        *   **Kampagnenname:** Ein beschreibender Name für Ihre interne Referenz (z.B. „Standard 2-Schritt-Erinnerung“, „Hochwertiger Warenkorb-Rabatt“).
        *   **Zielgruppenregeln:**
            *   **Mindestwert des Warenkorbs:** Legen Sie einen Mindestgesamtwert fest, damit ein Warenkorb für diese Kampagne berechtigt ist.
                *   *Auswirkung:* Warenkörbe unter diesem Wert erhalten keine E-Mails aus dieser Kampagne.
                *   *Händlerszenario:* Erstellen Sie eine Kampagne speziell für hochwertige Warenkörbe, die möglicherweise einen größeren Rabatt bietet.
            *   **Kundengruppen:** Sprechen Sie bestimmte Kundengruppen an (z.B. „Besucher“, „Kunden“, „Großhändler“).
                *   *Auswirkung:* Nur Kunden, die zu den ausgewählten Gruppen gehören, erhalten E-Mails.
                *   *Händlerszenario:* Senden Sie verschiedene Erinnerungen an neue Besucher im Vergleich zu treuen Kunden oder schließen Sie B2B-Kunden aus, wenn diese einen anderen Kaufprozess haben.
            *   **Produkte im Warenkorb:** Sprechen Sie Warenkörbe an, die bestimmte Produkte oder Produkte aus bestimmten Kategorien enthalten.
                *   *Auswirkung:* Nur Warenkörbe mit den angegebenen Produkten lösen die Kampagne aus.
                *   *Händlerszenario:* Erstellen Sie eine Kampagne für Kunden, die einen Warenkorb mit einem bestimmten margenstarken Produkt abgebrochen haben.
        *   **Kampagnenschritte (Drip-E-Mails):** Definieren Sie die Reihenfolge der zu sendenden E-Mails.
            *   **Verzögerung:** Wie lange nach dem Abbruch des Warenkorbs soll diese E-Mail gesendet werden (z.B. 1 Stunde, 24 Stunden, 3 Tage).
                *   *Auswirkung:* Steuert den Zeitpunkt Ihrer Nachverfolgung.
                *   *Händlerszenario:* Senden Sie eine schnelle Erinnerung nach 1 Stunde, eine stärkere mit einem Rabatt nach 24 Stunden und eine letzte nach 3 Tagen.
            *   **E-Mail-Betreff:** Die Betreffzeile der E-Mail (unterstützt mehrere Sprachen).
            *   **E-Mail-Inhalt (E-Mail-Builder):** Gestalten Sie den Hauptteil Ihrer E-Mail mit einem Rich-Text-Editor. Sie können dynamische Platzhalter wie Kundennamen, Warenkorb-Link, Produktliste und Rabattcodes einfügen.
            *   **Rabattcode:** Option zur Generierung eines einzigartigen, einmaligen Rabattcodes für diese spezifische E-Mail.
                *   *Auswirkung:* Ein einzigartiger Gutscheincode wird erstellt und in die E-Mail aufgenommen, um die Konversion zu fördern.
                *   *Händlerszenario:* Bieten Sie einen 10%igen Rabatt in der zweiten Erinnerungs-E-Mail an, um den Abschluss zu incentivieren.
            *   **A/B-Tests:** Erstellen Sie Variationen Ihres E-Mail-Betreffs oder -Inhalts, um zu testen, welche besser abschneidet.
                *   *Auswirkung:* Das Modul teilt die Sendungen zwischen den Variationen auf und verfolgt die Konversionsraten, sodass Sie Ihre Kampagnen optimieren können.
                *   *Händlerszenario:* Testen Sie zwei verschiedene Betreffzeilen, um zu sehen, welche eine höhere Öffnungsrate erzielt.
    *   **Kampagnen bearbeiten/duplizieren/löschen:** Verwalten Sie bestehende Kampagnen. Das Duplizieren ist nützlich, um schnell ähnliche Kampagnen zu erstellen.
-   **Auswirkung von Änderungen:** Änderungen hier wirken sich direkt darauf aus, welche Kunden Erinnerungs-E-Mails erhalten, wann sie diese erhalten, welchen Inhalt sie sehen und ob sie Rabattcodes erhalten. Gut konfigurierte Kampagnen können die Wiederherstellungsrate Ihres Shops erheblich steigern.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Beginnen Sie mit einer einfachen 2-Schritt-Kampagne: eine Erinnerung nach 1-2 Stunden (ohne Rabatt) und eine weitere nach 24 Stunden (mit einem kleinen Rabatt).
    2.  Überwachen Sie Ihr Dashboard (siehe 4.2.2), um zu sehen, welche Kampagnen am besten abschneiden.
    3.  Experimentieren Sie mit A/B-Tests bei Betreffzeilen oder Rabattbeträgen, um die Konversionsraten zu optimieren.
    4.  Erwägen Sie die Erstellung gezielter Kampagnen für bestimmte Kundensegmente oder hochwertige Produkte.

#### 2.2.2 Dashboard (Back Office > Abandoned Cart Reminder Pro > Dashboard)

Dieser Bildschirm bietet einen klaren Überblick über die Leistung Ihres Moduls und wichtige Statistiken.

-   **Bildschirmname & Menüpfad:** **Abandoned Cart Reminder Pro > Dashboard**
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Key Performance Indicators (KPIs):** Zeigt Metriken an wie:
        *   **Abgebrochene Warenkörbe:** Gesamtzahl der abgebrochenen Warenkörbe.
        *   **Gesendete E-Mails:** Anzahl der versendeten Erinnerungs-E-Mails.
        *   **Wiederhergestellte Warenkörbe:** Anzahl der abgebrochenen Warenkörbe, die nach Erhalt einer Erinnerung zu einer abgeschlossenen Bestellung führten.
        *   **Wiederherstellungsrate:** Prozentsatz der wiederhergestellten abgebrochenen Warenkörbe.
        *   **Zugeschriebener Umsatz:** Der Gesamtumsatz, der aus wiederhergestellten Warenkörben generiert wurde.
        *   **ROI:** Return on Investment für Ihre Kampagnen.
    *   **Kampagnenleistungsübersicht:** Eine visuelle Darstellung (z.B. Diagramme, Grafiken) der Leistung einzelner Kampagnen.
    *   **Letzte Aktivitäten:** Ein schneller Überblick über kürzlich abgebrochene Warenkörbe, gesendete E-Mails und wiederhergestellte Bestellungen.
-   **Auswirkung von Änderungen:** Dies ist ein Berichts-Bildschirm; Sie nehmen hier keine direkten Änderungen vor, aber die Daten helfen Ihnen, die Auswirkungen Ihrer Kampagnen zu verstehen und Ihre Optimierungsbemühungen im Abschnitt „Kampagnen“ zu leiten.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Dashboard regelmäßig (z.B. wöchentlich), um Trends zu erkennen, zu sehen, welche Kampagnen am effektivsten sind, und eventuelle Probleme zu identifizieren. Verwenden Sie diese Daten, um Ihre Kampagnenstrategien zu verfeinern.

#### 2.2.3 Protokolle (Back Office > Abandoned Cart Reminder Pro > Protokolle)

Der Abschnitt „Protokolle“ bietet eine detaillierte Historie aller vom Modul durchgeführten Aktionen und hilft Ihnen bei der Fehlerbehebung und Überprüfung des Betriebs.

-   **Bildschirmname & Menüpfad:** **Abandoned Cart Reminder Pro > Protokolle**
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Protokolleinträge-Raster:** Eine durchsuchbare und filterbare Tabelle, die Folgendes anzeigt:
        *   **Zeitstempel:** Wann das Ereignis aufgetreten ist.
        *   **Kunde:** Der mit dem Ereignis verbundene Kunde.
        *   **Warenkorb-ID:** Die ID des abgebrochenen Warenkorbs.
        *   **Kampagne/Schritt:** Welche Kampagne und welcher Schritt das Ereignis ausgelöst hat.
        *   **Ereignistyp:** (z.B. „Warenkorb abgebrochen“, „E-Mail gesendet“, „E-Mail geöffnet“, „Link geklickt“, „Warenkorb wiederhergestellt“, „Rabatt angewendet“).
        *   **Status:** Erfolg oder Misserfolg.
        *   **Details:** Zusätzliche Informationen, wie E-Mail-Inhaltsvorschau oder Fehlermeldungen.
    *   **E-Mail-Vorschau:** Option zur Anzeige des genauen Inhalts einer gesendeten E-Mail.
-   **Auswirkung von Änderungen:** Dies ist ein Diagnose- und Audit-Bildschirm. Sie nehmen hier keine Änderungen vor, aber er ist entscheidend, um zu verstehen, warum ein Kunde möglicherweise keine E-Mail erhalten hat oder wenn eine Kampagne nicht wie erwartet funktioniert.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Wenn ein Kunde meldet, keine E-Mail erhalten zu haben, oder wenn Ihre Wiederherstellungsrate unerwartet sinkt, überprüfen Sie die Protokolle. Sie können sehen, ob E-Mails erfolgreich gesendet wurden, ob Fehler aufgetreten sind oder ob Kunden sich abgemeldet haben.

#### 2.2.4 Einstellungen (Back Office > Abandoned Cart Reminder Pro > Einstellungen)

Dieser Bildschirm enthält globale Einstellungen, die das Gesamtverhalten des Moduls beeinflussen.

-   **Bildschirmname & Menüpfad:** **Abandoned Cart Reminder Pro > Einstellungen**
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Allgemeine Einstellungen:**
        *   **Modul aktivieren:** Schaltet das gesamte Modul ein oder aus.
            *   *Auswirkung:* Wenn deaktiviert, werden keine Warenkörbe verfolgt und keine E-Mails gesendet.
            *   *Empfohlen:* JA, es sei denn, Sie deaktivieren es vorübergehend zur Wartung.
        *   **Mindestwert des Warenkorbs für die Verfolgung:** Legen Sie einen globalen Mindestwert für den Warenkorb fest, damit ein Warenkorb als „abgebrochen“ betrachtet und vom Modul verfolgt wird.
            *   *Auswirkung:* Warenkörbe unter diesem Wert werden von allen Kampagnen ignoriert.
            *   *Händlerszenario:* Vermeiden Sie das Senden von Erinnerungen für sehr kleine Warenkörbe, bei denen der Wiederherstellungsaufwand möglicherweise nicht lohnt.
        *   **Zeit, nach der ein Warenkorb als abgebrochen gilt:** Wie lange nach der letzten Warenkorbaktivität soll ein Warenkorb als abgebrochen gelten (z.B. 30 Minuten, 1 Stunde).
            *   *Auswirkung:* Dies bestimmt, wann das Modul die Verzögerung für die erste Erinnerungs-E-Mail zu zählen beginnt.
            *   *Empfohlen:* 30-60 Minuten. Zu kurz könnte Kunden verärgern, zu lang könnte das Zeitfenster verpassen.
        *   **Anti-Spam-Limits:**
            *   **Max. E-Mails pro Kunde:** Begrenzen Sie die Gesamtzahl der E-Mails für abgebrochene Warenkörbe, die ein einzelner Kunde über einen bestimmten Zeitraum erhalten kann (z.B. 3 E-Mails pro 30 Tage).
                *   *Auswirkung:* Verhindert, dass Kunden von zu vielen E-Mails überfordert werden, wodurch die Abmelderaten reduziert werden.
                *   *Empfohlen:* Legen Sie angemessene Limits fest, um ein positives Kundenerlebnis zu gewährleisten.
            *   **Mindestzeit zwischen E-Mails:** Stellen Sie eine Mindestverzögerung zwischen zwei an denselben Kunden gesendeten E-Mails sicher.
                *   *Auswirkung:* Verhindert, dass mehrere E-Mails aus verschiedenen Kampagnen zu schnell hintereinander gesendet werden.
        *   **DSGVO / Abmelde-Einstellungen:**
            *   **Abmeldelink aktivieren:** Fügen Sie einen Link in Erinnerungs-E-Mails ein, der es Kunden ermöglicht, sich von zukünftigen Erinnerungen abzumelden.
                *   *Auswirkung:* Entscheidend für die Einhaltung der DSGVO und die Achtung der Kundenprivatsphäre.
                *   *Empfohlen:* JA.
            *   **Inhalt der Abmeldeseite:** Passen Sie den Text an, der auf der Abmeldebestätigungsseite angezeigt wird.
        *   **Cron-Job-URL:** Zeigt die genaue URL an, die Sie als Cron-Job auf Ihrem Server einrichten müssen.
            *   *Auswirkung:* Diese URL löst die Hintergrundverarbeitung des Moduls aus, sendet E-Mails und aktualisiert Statistiken.
            *   *Empfohlen:* Kopieren Sie diese URL und konfigurieren Sie den Cron-Job Ihres Servers so, dass er alle 5-15 Minuten ausgeführt wird.
    *   **E-Mail-Einstellungen:**
        *   **Absendername & E-Mail:** Der Name und die E-Mail-Adresse, die als Absender Ihrer Erinnerungs-E-Mails angezeigt werden.
            *   *Auswirkung:* Beeinflusst die E-Mail-Zustellbarkeit und wie Kunden Ihre Marke wahrnehmen.
            *   *Empfohlen:* Verwenden Sie einen wiedererkennbaren Shop-Namen und eine professionelle E-Mail-Adresse (z.B. `sales@ihrshop.com`, `noreply@ihrshop.com`).
        *   **E-Mail-Vorlage:** Wählen Sie eine Basisschablone für Ihre Erinnerungs-E-Mails (falls mehrere verfügbar sind).
            *   *Auswirkung:* Bestimmt das Gesamtdesign und Layout Ihrer E-Mails.
    *   **Erweiterte Einstellungen:**
        *   **Debug-Modus:** Aktivieren Sie ihn für detaillierte Protokollierung (für Entwickler).
            *   *Auswirkung:* Bietet ausführlichere Informationen in den Protokollen, nützlich für die Fehlerbehebung.
            *   *Empfohlen:* NEIN, es sei denn, der Support fordert Sie ausdrücklich dazu auf.
-   **Auswirkung von Änderungen:** Diese Einstellungen steuern das grundlegende Verhalten des Moduls, von der Verfolgung von Warenkörben bis hin zur Achtung der Kundenprivatsphäre und dem Versand von E-Mails. Falsche Einstellungen können zu verpassten Gelegenheiten oder einem schlechten Kundenerlebnis führen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diese Einstellungen während der Ersteinrichtung und regelmäßig, um sicherzustellen, dass sie mit den Richtlinien und der Marketingstrategie Ihres Shops übereinstimmen. Achten Sie besonders auf Anti-Spam- und DSGVO-Einstellungen.

#### 2.2.5 index.php (cartrempro/controllers/admin/index.php)

Diese Datei ist eine Standard-PrestaShop-Praxis, um das direkte Auflisten von Verzeichnissen in Admin-Ordnern zu verhindern, und stellt typischerweise keinen konfigurierbaren Bildschirm selbst dar. Sie gewährleistet die Sicherheit, indem sie umleitet oder eine leere Seite anzeigt, wenn jemand versucht, direkt auf den Ordner zuzugreifen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | `PS_SSL_ENABLED` (PrestaShop Core) | JA | Gewährleistet sichere HTTPS-Links in E-Mails. |
| **Kampagnen** | Kampagnenname | Beschreibend | Interne Identifizierung Ihrer Kampagnen. |
| | Mindestwert des Warenkorbs | 0 (oder Ihr Schwellenwert) | Filtert Warenkörbe nach Wert für bestimmte Kampagnen. |
| | Kundengruppen | Alle (oder spezifisch) | Spricht bestimmte Kundensegmente an. |
| | Produkte im Warenkorb | Keine (oder spezifisch) | Spricht Warenkörbe an, die bestimmte Produkte/Kategorien enthalten. |
| | Kampagnenschritt-Verzögerung | 1h, 24h, 3d | Steuert den Zeitpunkt der Erinnerungs-E-Mails. |
| | E-Mail-Betreff | Ansprechend | Entscheidend für Öffnungsraten. |
| | E-Mail-Inhalt | Personalisiert | Hauptnachricht zur Wiederherstellung des Warenkorbs. |
| | Rabattcode | Optional | Anreiz zur Konversion. |
| | A/B-Tests | Optional | Optimiert die Kampagnenleistung. |
| **Dashboard** | Alle KPIs | N/A (Berichterstattung) | Bietet Leistungsübersicht und ROI. |
| **Protokolle** | Alle Protokolleinträge | N/A (Berichterstattung) | Detaillierte Historie zur Fehlerbehebung und Prüfung. |
| **Einstellungen** | Modul aktivieren | JA | Schaltet das Modul ein/aus. |
| | Mindestwert des Warenkorbs für die Verfolgung | 0 (oder Ihr Schwellenwert) | Globaler Filter für alle verfolgten Warenkörbe. |
| | Zeit, nach der ein Warenkorb als abgebrochen gilt | 30-60 Minuten | Definiert, wann ein Warenkorb „abgebrochen“ ist. |
| | Max. E-Mails pro Kunde | Angemessenes Limit | Verhindert Spamming von Kunden. |
| | Mindestzeit zwischen E-Mails | Angemessenes Limit | Verhindert schnelle E-Mails. |
| | Abmeldelink aktivieren | JA | DSGVO-Konformität, Kundenwahl. |
| | Cron-Job-URL | Vom Modul kopieren | **KRITISCH:** Ermöglicht die Hintergrundverarbeitung. |
| | Absendername & E-Mail | Ihr Shop-Name, professionelle E-Mail | Beeinflusst die Zustellbarkeit und das Markenvertrauen. |
| | Debug-Modus | NEIN | Nur zur Fehlerbehebung für Entwickler. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten keine Erinnerungs-E-Mails. Was soll ich überprüfen?**
A1:

-   **Cron-Job:** Dies ist das häufigste Problem. Stellen Sie sicher, dass Ihr Cron-Job auf Ihrem Server korrekt eingerichtet ist und regelmäßig (alle 5-15 Minuten) ausgeführt wird. Die genaue URL finden Sie unter **Abandoned Cart Reminder Pro > Einstellungen**.
-   **Modul aktiviert:** Überprüfen Sie unter **Abandoned Cart Reminder Pro > Einstellungen**, ob das Modul global aktiviert ist.
-   **Kampagnen aktiv:** Überprüfen Sie, ob Ihre Kampagnen aktiviert sind und aktive Schritte unter **Abandoned Cart Reminder Pro > Kampagnen** haben.
-   **E-Mail-Konfiguration:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (Erweiterte Parameter > E-Mail), um sicherzustellen, dass Ihr Shop generell E-Mails senden kann.
-   **Spam-Filter:** Bitten Sie einen Testkunden, seinen Spam-/Junk-Ordner zu überprüfen. Stellen Sie sicher, dass Ihre Absender-E-Mail-Adresse professionell ist und nicht auf einer Blacklist steht.
-   **Protokolle:** Gehen Sie zu **Abandoned Cart Reminder Pro > Protokolle**, um zu sehen, ob E-Mails in die Warteschlange gestellt, gesendet werden oder ob Fehlermeldungen vorliegen.

**F2: Warum lösen einige abgebrochene Warenkörbe keine Kampagne aus?**
A2:

-   **Mindestwert des Warenkorbs:** Überprüfen Sie den globalen „Mindestwert des Warenkorbs für die Verfolgung“ unter **Abandoned Cart Reminder Pro > Einstellungen** und den spezifischen „Mindestwert des Warenkorbs“ für Ihre Kampagnen unter **Abandoned Cart Reminder Pro > Kampagnen**. Warenkörbe unter diesen Werten werden ignoriert.
-   **Zeit, nach der ein Warenkorb als abgebrochen gilt:** Stellen Sie sicher, dass die unter **Abandoned Cart Reminder Pro > Einstellungen** festgelegte Zeit seit der letzten Warenkorbaktivität verstrichen ist.
-   **Kundengruppen/Produkt-Targeting:** Wenn Ihre Kampagne spezifische Kundengruppen- oder Produkt-Targeting hat, stellen Sie sicher, dass der abgebrochene Warenkorb diese Kriterien erfüllt.
-   **Anti-Spam-Limits:** Der Kunde hat möglicherweise die unter **Abandoned Cart Reminder Pro > Einstellungen** festgelegten Limits für „Max. E-Mails pro Kunde“ oder „Mindestzeit zwischen E-Mails“ erreicht.
-   **Kunden-Abmeldung:** Der Kunde hat sich möglicherweise zuvor vom Empfang von Erinnerungen abgemeldet. Überprüfen Sie die Protokolle.

**F3: Wie stelle ich sicher, dass die Erinnerungs-E-Mails auf mobilen Geräten gut aussehen?**
A3: Das Modul verwendet responsive E-Mail-Vorlagen. Der Inhalt, den Sie im E-Mail-Builder hinzufügen, kann dies jedoch beeinflussen.

-   **Halten Sie es einfach:** Vermeiden Sie übermäßig komplexe Layouts oder sehr breite Bilder.
-   **Testen:** Senden Sie immer eine Test-E-Mail an sich selbst und sehen Sie sie auf verschiedenen Geräten (Desktop, Tablet, Telefon) an, bevor Sie eine Kampagne aktivieren.
-   **PrestaShop-Theme:** Stellen Sie sicher, dass Ihr Haupt-PrestaShop-Theme mobilfreundlich ist, da die Links in den E-Mails zu Ihrem Shop zurückführen.

**F4: Kann ich den E-Mail-Inhalt und die Betreffzeilen übersetzen?**
A4: Ja! Beim Bearbeiten eines Kampagnenschritts sehen Sie Sprachregisterkarten für den Betreff und den E-Mail-Inhalt. Sie können für jede in Ihrem PrestaShop-Shop installierte Sprache unterschiedliche Übersetzungen bereitstellen. Dies ist entscheidend für internationale Shops.

**F5: Ich habe meinen Smarty-Cache geleert, und jetzt sieht etwas seltsam aus. Was ist passiert?**
A5: Das Leeren des Smarty-Caches (unter **Erweiterte Parameter > Leistung**) ist ein gängiger Schritt zur Fehlerbehebung bei Anzeigeproblemen. Obwohl im Allgemeinen sicher, kann es manchmal vorübergehend die Art und Weise beeinflussen, wie Module ihren Inhalt rendern, bis der Cache neu aufgebaut wird. Wenn Sie nach dem Leeren des Caches Anzeigeprobleme bemerken, versuchen Sie, die Seite mehrmals zu aktualisieren oder die Konfiguration des Moduls erneut zu speichern (auch ohne etwas zu ändern), um einen Cache-Neubau für das Modul zu erzwingen. Dieses Modul verwendet eigene Caching-Mechanismen, daher sollte das Leeren des Smarty-Caches seine Kernfunktionalität nicht direkt beeinflussen, sondern eher die Anzeige seiner Admin-Oberfläche.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Abandoned Cart Reminder Pro“ für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul folgt einer robusten, ereignisgesteuerten Architektur, die sich an das MVC-Muster von PrestaShop hält, wo es angebracht ist, aber auch einen benutzerdefinierten Service-Container und Autoloading für eine bessere Organisation und Testbarkeit nutzt. Es stützt sich stark auf Cron-Jobs für die Hintergrundverarbeitung, um sicherzustellen, dass der E-Mail-Versand und die Warenkorbverfolgung die Front-Office-Leistung nicht beeinträchtigen. Zu den Schlüsselkomponenten gehören:

-   **Warenkorbverfolgung:** Greift in `ActionCartSave` und `ActionValidateOrder` ein, um den Warenkorbstatus zu überwachen.
-   **Kampagnen-Engine:** Verwaltet mehrstufige E-Mail-Sequenzen, Zielgruppenansprache und Rabattgenerierung.
-   **Warteschlangenprozessor:** Handhabt den asynchronen Versand von E-Mails über Cron.
-   **Analyse & Attribution:** Verfolgt Wiederherstellungsraten und Umsatz.
-   **Admin-Controller:** Dedizierte Controller zur Verwaltung von Kampagnen, Anzeige von Protokollen und Konfiguration von Einstellungen.
-   **DSGVO-Konformität:** Enthält einen Opt-Out-Mechanismus.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verwalten spezifische Front-Office-Interaktionen, hauptsächlich für die Cron-Ausführung, Verfolgung und Abmeldung.

-   `controllers/front/cron.php`
    *   **Klassenname:** `CartRemProCronModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Dies ist der primäre Endpunkt für den Cron-Job des Moduls. Beim Zugriff löst es den `CartRemProQueueProcessor` aus, um die Warteschlange der abgebrochenen Warenkörbe zu verarbeiten, geplante E-Mails zu senden und Statistiken zu aktualisieren. Es ist so konzipiert, dass es von einem serverseitigen Cron-Task aufgerufen wird, nicht direkt von Benutzern.
-   `controllers/front/index.php`
    *   **Klassenname:** `CartRemProIndexModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Eine Standard-PrestaShop-Praxis zur Verhinderung des direkten Auflistens von Verzeichnissen. Leitet typischerweise zur Startseite des Shops um oder zeigt eine leere Seite an.
-   `controllers/front/optout.php`
    *   **Klassenname:** `CartRemProOptoutModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Behandelt Kundenanfragen zur Abmeldung von Erinnerungen an abgebrochene Warenkörbe. Es verarbeitet die `optout`-Aktion, aktualisiert die Präferenz des Kunden und zeigt eine Bestätigungsseite (`optout.tpl`) an.
-   `controllers/front/track.php`
    *   **Klassenname:** `CartRemProTrackModuleFrontController` (erweitert `ModuleFrontController`)
    *   **Verantwortlichkeit:** Wird zur Verfolgung von E-Mail-Öffnungen und Link-Klicks innerhalb der Erinnerungs-E-Mails verwendet. Es zeichnet diese Ereignisse in den Protokollen des Moduls auf, was Analysen zur E-Mail-Interaktion ermöglicht.

#### Back-Office-Admin-Controller

Diese Controller verwalten die Schnittstelle des Moduls im PrestaShop Back Office.

-   `controllers/admin/AdminCartRemProCampaignsController.php`
    *   **Tab-Name:** Abandoned Cart Reminder Pro > Kampagnen
    *   **Verantwortlichkeit:** Verwaltet die Erstellung, Bearbeitung, Duplizierung und Löschung von Kampagnen für abgebrochene Warenkörbe. Es verarbeitet die Formularübermittlung für Kampagnendetails, Schritte, Zielgruppenregeln und A/B-Testkonfigurationen. Es interagiert mit den Klassen `CartRemProCampaign` und `CartRemProCampaignStep`.
-   `controllers/admin/AdminCartRemProDashboardController.php`
    *   **Tab-Name:** Abandoned Cart Reminder Pro > Dashboard
    *   **Verantwortlichkeit:** Zeigt die Leistungsmetriken des Moduls an, einschließlich abgebrochener Warenkörbe, wiederhergestellter Warenkörbe, zugeschriebenem Umsatz und ROI. Es aggregiert Daten von `CartRemProAnalytics` und `CartRemProAbandoned`, um einen umfassenden Überblick zu präsentieren.
-   `controllers/admin/AdminCartRemProLogsController.php`
    *   **Tab-Name:** Abandoned Cart Reminder Pro > Protokolle
    *   **Verantwortlichkeit:** Bietet ein detailliertes Protokoll aller Modulaktivitäten, wie Warenkorbabbrüche, E-Mail-Versand, Öffnungen, Klicks und Wiederherstellungen. Es ermöglicht das Filtern und Durchsuchen dieser Protokolle zur Fehlerbehebung und Prüfung.
-   `controllers/admin/AdminCartRemProSettingsController.php`
    *   **Tab-Name:** Abandoned Cart Reminder Pro > Einstellungen
    *   **Verantwortlichkeit:** Verwaltet die globalen Konfigurationseinstellungen für das Modul, einschließlich Aktivierung/Deaktivierung, Anti-Spam-Limits, DSGVO-Optionen und Anzeige der Cron-Job-URL. Es interagiert mit der `Configuration`-Klasse von PrestaShop.
-   `controllers/admin/index.php`
    *   **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei zur Verhinderung des direkten Auflistens von Verzeichnissen.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul verwendet eine Vielzahl benutzerdefinierter Klassen für seine Geschäftslogik, viele davon erweitern `ObjectModel` für die Datenbankinteraktion.

-   `classes/CartRemProAbandoned.php`
    *   **Datenbanktabelle:** `ps_cartrempro_abandoned`
    *   **Erweitert:** `ObjectModel`
    *   **`$definition`-Felder:** `id_cart`, `id_customer`, `id_shop`, `id_lang`, `cart_value`, `date_add`, `date_upd`, `is_recovered`, `is_optout`
    *   **Wichtige öffentliche Methoden:** Verwaltet die Verfolgung und den Status abgebrochener Warenkörbe.
-   `classes/CartRemProAbTesting.php`
    *   **Verantwortlichkeit:** Handhabt die Logik für A/B-Tests innerhalb von Kampagnenschritten, einschließlich der Aufteilung des Traffics und der Verfolgung von Konversionsraten für verschiedene Variationen.
-   `classes/CartRemProAdminController.php`
    *   **Erweitert:** `ModuleAdminController`
    *   **Verantwortlichkeit:** Eine Basisklasse für die Admin-Controller des Moduls, die gemeinsame Funktionalitäten und Dienstprogramme speziell für die Back-Office-Schnittstelle des Moduls bereitstellt.
-   `classes/CartRemProAdminUi.php`
    *   **Verantwortlichkeit:** Hilfsklasse zum Generieren und Rendern gängiger UI-Elemente im Admin-Panel, um Konsistenz zu gewährleisten.
-   `classes/CartRemProAnalytics.php`
    *   **Verantwortlichkeit:** Sammelt und verarbeitet Daten für das Dashboard, berechnet KPIs wie Wiederherstellungsrate, zugeschriebenen Umsatz und ROI.
-   `classes/CartRemProAntiSpam.php`
    *   **Verantwortlichkeit:** Implementiert die Logik für Anti-Spam-Limits, um sicherzustellen, dass Kunden nicht zu viele E-Mails innerhalb eines bestimmten Zeitraums erhalten.
-   `classes/CartRemProAttribution.php`
    *   **Verantwortlichkeit:** Bestimmt, ob ein wiederhergestellter Warenkorb einer bestimmten Erinnerungskampagne für abgebrochene Warenkörbe zugeschrieben werden kann.
-   `classes/CartRemProAutoload.php`
    *   **Verantwortlichkeit:** Benutzerdefinierter Autoloader für die Klassen des Moduls, der sicherstellt, dass sie effizient geladen werden, ohne mit dem Standard-Autoloader von PrestaShop zu kollidieren.
-   `classes/CartRemProCampaign.php`
    *   **Datenbanktabelle:** `ps_cartrempro_campaign`
    *   **Erweitert:** `ObjectModel`
    *   **`$definition`-Felder:** `name`, `active`, `min_cart_value`, `customer_groups`, `products`, `categories`, `date_add`, `date_upd`
    *   **Wichtige öffentliche Methoden:** Repräsentiert eine Kampagne für abgebrochene Warenkörbe, verwaltet deren Einstellungen, Zielgruppenregeln und zugehörige Schritte.
-   `classes/CartRemProCampaignEngine.php`
    *   **Verantwortlichkeit:** Die Kernlogik zur Bewertung abgebrochener Warenkörbe anhand aktiver Kampagnen, zur Bestimmung, welche Kampagne (falls vorhanden) ausgelöst werden soll, und zur Planung des nächsten E-Mail-Schritts.
-   `classes/CartRemProCampaignStep.php`
    *   **Datenbanktabelle:** `ps_cartrempro_campaign_step`
    *   **Erweitert:** `ObjectModel`
    *   **`$definition`-Felder:** `id_cartrempro_campaign`, `delay_hours`, `subject`, `content`, `discount_type`, `discount_value`, `ab_test_active`, `ab_test_variations`
    *   **Wichtige öffentliche Methoden:** Definiert einen einzelnen Schritt innerhalb einer Kampagne, einschließlich E-Mail-Inhalt, Verzögerung und Rabatt.
-   `classes/CartRemProCartTracker.php`
    *   **Verantwortlichkeit:** Überwacht Kundenwarenkörbe, identifiziert, wann sie abgebrochen werden, und zeichnet sie in der Tabelle `ps_cartrempro_abandoned` auf.
-   `classes/CartRemProChannelEmail.php`
    *   **Implementiert:** `CartRemProChannelInterface`
    *   **Verantwortlichkeit:** Handhabt den eigentlichen Versand von E-Mail-Erinnerungen, einschließlich des Renderns von E-Mail-Vorlagen und der Integration mit der Mail-Klasse von PrestaShop.
-   `classes/CartRemProChannelInterface.php`
    *   **Verantwortlichkeit:** Definiert eine gemeinsame Schnittstelle für verschiedene Kommunikationskanäle (derzeit nur E-Mail, aber erweiterbar für SMS, Web-Push).
-   `classes/CartRemProCompat.php`
    *   **Verantwortlichkeit:** Bietet Kompatibilitätsschichten für verschiedene PrestaShop-Versionen (1.7, 8.x, 9.x), um einen reibungslosen Betrieb über den unterstützten Bereich hinweg zu gewährleisten.
-   `classes/CartRemProDiscountGenerator.php`
    *   **Verantwortlichkeit:** Erstellt einzigartige, einmalige Rabattcodes (Warenkorbregeln) für Kunden, die eine Erinnerungs-E-Mail mit einem Rabattangebot erhalten.
-   `classes/CartRemProEmailRenderer.php`
    *   **Verantwortlichkeit:** Rendert die Smarty-Vorlagen für Erinnerungs-E-Mails und fügt dynamische Daten wie Warenkorbdetails, Kundeninformationen und Rabattcodes ein.
-   `classes/CartRemProGdpr.php`
    *   **Verantwortlichkeit:** Verwaltet DSGVO-Konformitätsfunktionen, insbesondere den Kunden-Opt-Out-Mechanismus.
-   `classes/CartRemProProductBlocks.php`
    *   **Verantwortlichkeit:** Hilfsklasse zum Generieren produktbezogener Blöcke innerhalb von E-Mail-Vorlagen, wie z.B. Produktlisten für abgebrochene Warenkörbe oder empfohlene Produkte.
-   `classes/CartRemProQueueProcessor.php`
    *   **Verantwortlichkeit:** Das Herzstück des Cron-Jobs. Es ruft geplante Aufgaben aus der Warteschlange ab (z.B. E-Mail senden, Warenkorbstatus prüfen), verarbeitet sie und aktualisiert die Protokolle.
-   `classes/CartRemProScheduleGuard.php`
    *   **Verantwortlichkeit:** Stellt sicher, dass geplante Aufgaben nur einmal und innerhalb ihrer vorgesehenen Zeitrahmen ausgeführt werden, um doppelte E-Mails oder Aktionen zu verhindern.
-   `classes/CartRemProSegmentation.php`
    *   **Verantwortlichkeit:** Implementiert die Logik zur Segmentierung von Kunden und Warenkörben basierend auf Kampagnen-Zielgruppenregeln (z.B. Warenkorbwert, Kundengruppe, Produkte).
-   `classes/CartRemProServiceContainer.php`
    *   **Verantwortlichkeit:** Ein benutzerdefinierter Dependency-Injection-Container zur Verwaltung und Bereitstellung von Instanzen der Kernservices und -klassen des Moduls, wodurch Modularität und Testbarkeit verbessert werden.
-   `classes/CartRemProStockChecker.php`
    *   **Verantwortlichkeit:** Überprüft die Produktbestände vor dem Senden von Erinnerungen, um sicherzustellen, dass Artikel in einem abgebrochenen Warenkorb noch verfügbar sind.
-   `classes/CartRemProTabInstaller.php`
    *   **Verantwortlichkeit:** Handhabt die Installation und Deinstallation der Admin-Menü-Tabs des Moduls im PrestaShop Back Office.
-   `classes/index.php`
    *   **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei zur Verhinderung des direkten Auflistens von Verzeichnissen.

### 4.4 JavaScript-Assets (`views/js/`)

-   `cartrempro/devtools/crp-ab-stats-demo-console.js`
    *   **Geltungsbereich:** Back-Office (Entwicklertools)
    *   **Verantwortlichkeit:** Wahrscheinlich ein Entwicklungszeit-Skript zur Demonstration oder Fehlerbehebung von A/B-Teststatistiken in der Browserkonsole. Nicht für den Produktionseinsatz.
-   `cartrempro/devtools/crp-dashboard-demo-console.js`
    *   **Geltungsbereich:** Back-Office (Entwicklertools)
    *   **Verantwortlichkeit:** Ähnlich wie oben, zur Demonstration oder Fehlerbehebung von Dashboard-Daten. Nicht für den Produktionseinsatz.
-   `cartrempro/lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Back-Office (Admin-Formulare)
    *   **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Eingabefelder, wahrscheinlich verwendet zur Auswahl von Produkten oder Kategorien in der Kampagnen-Zielgruppenansprache. Bindet an Eingabeereignisse und führt AJAX-Aufrufe für Suchvorschläge aus.
-   `cartrempro/views/js/admin-common.js`
    *   **Geltungsbereich:** Back-Office (globaler Admin)
    *   **Verantwortlichkeit:** Enthält gemeinsame JavaScript-Funktionen und Event-Listener, die auf verschiedenen Admin-Bildschirmen des Moduls verwendet werden, wie z.B. allgemeine Formularbehandlung, AJAX-Dienstprogrammfunktionen und UI-Verbesserungen.
-   `cartrempro/views/js/admin-dashboard.js`
    *   **Geltungsbereich:** Back-Office (Dashboard)
    *   **Verantwortlichkeit:** Handhabt die interaktiven Elemente und die Datenvisualisierung auf dem Dashboard des Moduls, möglicherweise das Rendern von Diagrammen oder das dynamische Aktualisieren von Statistiken.
-   `cartrempro/views/js/campaigns-admin.js`
    *   **Geltungsbereich:** Back-Office (Kampagnen)
    *   **Verantwortlichkeit:** Verwaltet die komplexe Benutzeroberfläche für die Kampagnenerstellung und -bearbeitung, einschließlich des Hinzufügens/Entfernens von Kampagnenschritten, der Konfiguration von Zielgruppenregeln, der Handhabung von Rabattoptionen und der Verwaltung von A/B-Testvariationen. Bindet an Klickereignisse auf Schaltflächen, Änderungsereignisse auf Auswahlfeldern und Formularübermittlungen.
-   `cartrempro/views/js/email-builder.js`
    *   **Geltungsbereich:** Back-Office (Kampagnen - E-Mail-Inhalt)
    *   **Verantwortlichkeit:** Verbessert den Rich-Text-Editor, der für den E-Mail-Inhalt verwendet wird, indem möglicherweise benutzerdefinierte Schaltflächen für dynamische Platzhalter (z.B. `{{customer_name}}`, `{{cart_link}}`) hinzugefügt oder Echtzeit-Vorschauen bereitgestellt werden.
-   `cartrempro/views/js/logs-admin.js`
    *   **Geltungsbereich:** Back-Office (Protokolle)
    *   **Verantwortlichkeit:** Bietet interaktive Funktionen für die Protokolltabelle, wie z.B. Filtern, Suchen, Paginierung und möglicherweise modale Popups zur Anzeige von E-Mail-Vorschauen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `cartrempro/lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Back-Office (Admin-Formulare)
    *   **Haupt-UI-Komponenten:** Gestaltet die Autocomplete-Dropdown-Vorschläge und Eingabefelder, die im Suchwerkzeug verwendet werden.
    *   **Wichtige CSS-Klassenselektoren:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`
-   `cartrempro/views/css/admin.css`
    *   **Geltungsbereich:** Back-Office (globaler Admin)
    *   **Haupt-UI-Komponenten:** Bietet das Gesamt-Styling für die Admin-Oberfläche des Moduls, einschließlich Dashboard-Layouts, Kampagnenformularen, Protokolltabellen und allgemeinem Schaltflächen-/Eingabestyling.
    *   **Wichtige CSS-Klassenselektoren:** `.cartrempro-dashboard`, `.cartrempro-campaign-form`, `.cartrempro-logs-table`, `.crp-badge`, `.crp-stat-card`, etc.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

Das Modul listet keine Vorlagen explizit in einem `hook/`-Verzeichnis auf, was darauf hindeutet, dass das Front-Office-Rendering für Hooks direkt in der Hauptmoduldatei oder über spezifische Front-Controller gehandhabt werden könnte.

#### Admin-Vorlagen (`views/templates/admin/`)

Diese Vorlagen rendern die Back-Office-Oberfläche des Moduls.

-   `cartrempro/views/templates/admin/ab_email_preview.tpl`
    *   **Zweck:** Zeigt eine Vorschau einer A/B-Test-E-Mail-Variation an.
-   `cartrempro/views/templates/admin/campaigns.tpl`
    *   **Zweck:** Die Hauptvorlage für den Administrationsbildschirm „Kampagnen“, listet Kampagnen auf und bietet Formulare zum Hinzufügen/Bearbeiten.
-   `cartrempro/views/templates/admin/dashboard.tpl`
    *   **Zweck:** Die Hauptvorlage für den Bildschirm „Dashboard“, zeigt KPIs und Leistungsdiagramme an.
-   `cartrempro/views/templates/admin/logs.tpl`
    *   **Zweck:** Die Hauptvorlage für den Bildschirm „Protokolle“, präsentiert die Tabelle der Modulaktivitäten.
-   `cartrempro/views/templates/admin/logs_email_preview.tpl`
    *   **Zweck:** Zeigt eine Vorschau einer E-Mail aus den Protokollen an.
-   `cartrempro/views/templates/admin/settings.tpl`
    *   **Zweck:** Die Hauptvorlage für den Bildschirm „Einstellungen“, enthält globale Konfigurationsoptionen.
-   `cartrempro/views/templates/admin/_partials/ab_stats.tpl`
    *   **Zweck:** Rendert Statistiken für A/B-Testvariationen innerhalb einer Kampagne.
-   `cartrempro/views/templates/admin/_partials/campaign_form.tpl`
    *   **Zweck:** Wiederverwendbares Partial für das Kampagnenerstellungs-/Bearbeitungsformular, einschließlich Schritte, Zielgruppenansprache und allgemeine Einstellungen.
-   `cartrempro/views/templates/admin/_partials/campaign_list_compact.tpl`
    *   **Zweck:** Rendert eine kompakte Liste von Kampagnen, möglicherweise für Dashboard-Widgets oder schnelle Übersichten.
-   `cartrempro/views/templates/admin/_partials/campaign_targeting.tpl`
    *   **Zweck:** Rendert den Abschnitt der Zielgruppenregeln innerhalb des Kampagnenformulars.
-   `cartrempro/views/templates/admin/_partials/copy_box.tpl`
    *   **Zweck:** Eine wiederverwendbare Komponente zum Anzeigen von Text, der leicht kopiert werden kann (z.B. die Cron-Job-URL).
-   `cartrempro/views/templates/admin/_partials/empty_state.tpl`
    *   **Zweck:** Zeigt eine Meldung an, wenn eine Liste oder ein Abschnitt leer ist (z.B. „Keine Kampagnen gefunden“).
-   `cartrempro/views/templates/admin/_partials/icon_duplicate.tpl`
    *   **Zweck:** Rendert ein Duplikat-Symbol.
-   `cartrempro/views/templates/admin/_partials/icon_edit.tpl`
    *   **Zweck:** Rendert ein Bearbeiten-Symbol.
-   `cartrempro/views/templates/admin/_partials/icon_trash.tpl`
    *   **Zweck:** Rendert ein Müll-/Löschen-Symbol.
-   `cartrempro/views/templates/admin/_partials/page_header.tpl`
    *   **Zweck:** Rendert einen konsistenten Header für Admin-Seiten innerhalb des Moduls.
-   `cartrempro/views/templates/admin/_partials/status_badge.tpl`
    *   **Zweck:** Rendert ein visuelles Abzeichen, das den Status anzeigt (z.B. „Aktiv“, „Inaktiv“).
-   `cartrempro/views/templates/admin/_partials/stat_card.tpl`
    *   **Zweck:** Rendert eine einzelne Statistikkarte für das Dashboard (z.B. „Wiederhergestellte Warenkörbe“).
-   `cartrempro/views/templates/admin/_partials/step_subject_lang.tpl`
    *   **Zweck:** Rendert das Eingabefeld für die Betreffzeile mit Sprachregisterkarten für Kampagnenschritte.
-   `cartrempro/views/templates/admin/_partials/toggle_row.tpl`
    *   **Zweck:** Rendert eine Zeile mit einem Kippschalter (z.B. zum Aktivieren/Deaktivieren einer Einstellung).

#### Front-Office-Vorlagen (`views/templates/front/`)

-   `cartrempro/views/templates/front/optout.tpl`
    *   **Zweck:** Zeigt die Bestätigungsseite an, nachdem ein Kunde sich von Erinnerungen an abgebrochene Warenkörbe abgemeldet hat.

#### E-Mail-Vorlagen (`views/templates/email/`)

-   `cartrempro/views/templates/email/default_recovery.tpl`
    *   **Zweck:** Die Standard-Basisschablone für Erinnerungs-E-Mails an abgebrochene Warenkörbe. Sie enthält Platzhalter für dynamische Inhalte wie Kundennamen, Warenkorb-Link, Produktliste und Rabattcodes. Entwickler können diese Vorlage anpassen oder neue für verschiedene E-Mail-Designs erstellen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt während der Installation die folgenden benutzerdefinierten Tabellen:

-   `ps_cartrempro_abandoned`: Speichert Details zu abgebrochenen Warenkörben.
    *   `id_cartrempro_abandoned` (PK)
    *   `id_cart` (FK zu `ps_cart`)
    *   `id_customer` (FK zu `ps_customer`)
    *   `id_shop` (FK zu `ps_shop`)
    *   `id_lang` (FK zu `ps_lang`)
    *   `cart_value` (decimal)
    *   `date_add` (datetime)
    *   `date_upd` (datetime)
    *   `is_recovered` (tinyint)
    *   `is_optout` (tinyint)
-   `ps_cartrempro_campaign`: Speichert Details zu jeder Erinnerungskampagne.
    *   `id_cartrempro_campaign` (PK)
    *   `name` (varchar)
    *   `active` (tinyint)
    *   `min_cart_value` (decimal)
    *   `customer_groups` (text - serialisiertes Array)
    *   `products` (text - serialisiertes Array)
    *   `categories` (text - serialisiertes Array)
    *   `date_add` (datetime)
    *   `date_upd` (datetime)
-   `ps_cartrempro_campaign_step`: Speichert Details zu jedem Schritt innerhalb einer Kampagne.
    *   `id_cartrempro_campaign_step` (PK)
    *   `id_cartrempro_campaign` (FK zu `ps_cartrempro_campaign`)
    *   `delay_hours` (int)
    *   `subject` (text - mehrsprachig)
    *   `content` (text - mehrsprachig)
    *   `discount_type` (varchar)
    *   `discount_value` (decimal)
    *   `ab_test_active` (tinyint)
    *   `ab_test_variations` (text - serialisiertes Array)
-   `ps_cartrempro_log`: Speichert detaillierte Protokolle der Modulaktivitäten.
    *   `id_cartrempro_log` (PK)
    *   `id_cart`
    *   `id_customer`
    *   `id_cartrempro_campaign`
    *   `id_cartrempro_campaign_step`
    *   `event_type` (varchar)
    *   `details` (text)
    *   `date_add` (datetime)
-   `ps_cartrempro_queue`: Speichert Aufgaben, die für den Cron-Job geplant sind.
    *   `id_cartrempro_queue` (PK)
    *   `id_cart`
    *   `id_cartrempro_campaign`
    *   `id_cartrempro_campaign_step`
    *   `task_type` (varchar)
    *   `scheduled_at` (datetime)
    *   `processed_at` (datetime)
    *   `status` (varchar)
    *   `error_message` (text)

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `ActionObjectCartUpdateAfter` | Nach der Aktualisierung eines `Cart`-Objekts (z.B. Produkt hinzugefügt/entfernt, Menge geändert). | Wird verwendet, um Änderungen an Kundenwarenkörben zu verfolgen und potenzielle Abbrüche zu identifizieren. |
| `actionDispatcher` | Bevor ein Controller versendet wird. | Potenziell für Routing, URL-Rewriting oder frühe Initialisierung verwendet. |
| `ActionCronJob` | Wenn der native PrestaShop-Cron-Job ausgeführt wird (falls konfiguriert). | Löst den `cron.php`-Controller des Moduls aus, um die Warteschlange zu verarbeiten. |
| `ActionFrontControllerInit` | Bevor ein Front-Controller initialisiert wird. | Wird für die frühe Einrichtung verwendet, z.B. zum Registrieren von Modul-Assets oder spezifischem Routing. |
| `moduleRoutes` | Während der URL-Routing-Generierung. | Ermöglicht dem Modul, benutzerdefinierte, freundliche URLs für seine Front-Controller zu definieren (z.B. `/cartrempro/optout`). |
| `displayModuleRoutes` | Ähnlich wie `moduleRoutes`, oft zum Anzeigen oder Debuggen von Routen verwendet. | Weniger gebräuchlich für funktionale Logik, mehr zum Debuggen. |
| `ActionCartSave` | Nachdem ein Warenkorb in der Datenbank gespeichert wurde. | Entscheidend für die Verfolgung der Warenkorbaktivität und die Identifizierung, wann ein Warenkorb abgebrochen wird. |
| `ActionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird verwendet, um einen abgebrochenen Warenkorb als „wiederhergestellt“ zu markieren, wenn er zu einem abgeschlossenen Kauf führt. |
| `ActionCustomerAccountAdd` | Nachdem ein neues Kundenkonto erstellt wurde. | Potenziell für Segmentierung oder anfängliche Kundenverfolgung verwendet, obwohl weniger kritisch für die Kernlogik des abgebrochenen Warenkorbs. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.

-   **MyPresta.eu Bestellhistorie & Downloads:** <https://mypresta.eu/my-account/orders/>
-   **Support-Kontakt:** [support@mypresta.eu](mailto:support@mypresta.eu)
