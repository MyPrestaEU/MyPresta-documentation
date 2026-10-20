---
title: "Rewards - Gutscheincodes nach Bestellungen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Rewards - Gutscheincodes nach Bestellungen“ von MyPresta.eu."
sidebar:
  label: "Rewards - Gutscheincodes nach Bestellungen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Rewards - Voucher codes after orders auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/rewards-voucher-codes-after-orders.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/rewards-voucher-codes-after-orders/)
>
> ---


# Rewards - Gutscheincodes nach Bestellungen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den korrekten Betrieb eines PrestaShop-Shops erforderlich. Dieses Modul hat keine ungewöhnlichen oder zusätzlichen Hosting-Anforderungen über eine Standard-PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Rewards - Gutscheincodes nach Bestellungen)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Regeln für die Generierung und den Versand von Gutscheincodes definieren.

#### Allgemeine Einstellungen

-   **Modul aktivieren:**

    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das Modul überwacht aktiv Bestellungen und generiert/versendet Gutscheine gemäß Ihren Regeln.
        *   *Wenn deaktiviert:* Das Modul ist inaktiv, und es werden keine Gutscheine generiert oder versendet, unabhängig von anderen Einstellungen.
    *   **Empfohlener Wert:** JA
    *   **Händlerszenario / Beispiel:** Sie haben alle Ihre Regeln eingerichtet und sind bereit, Ihr Prämienprogramm zu starten. Aktivieren Sie dies, um Gutscheine zu versenden. Wenn Sie das Programm vorübergehend für Wartungsarbeiten pausieren müssen, deaktivieren Sie es.
-   **Bestellstatus für Gutscheingenerierung:**

    *   **Was diese Einstellung bewirkt:** Legt fest, welche Bestellstatus den Gutscheingenerierungsprozess auslösen. Nur Bestellungen, die einen dieser ausgewählten Status erreichen, qualifizieren sich für eine Prämie.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ausgewählt:* Bestellungen mit diesen Status werden auf Gutscheinberechtigung geprüft.
        *   *Wenn nicht ausgewählt:* Bestellungen mit diesen Status werden vom Modul ignoriert.
    *   **Empfohlener Wert:** Typischerweise „Zahlung akzeptiert“ und „Geliefert“. Sie könnten auch „Versandt“ einschließen, wenn Sie den Gutschein früher versenden möchten.
    *   **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Kunden einen Gutschein erst erhalten, nachdem ihre Zahlung bestätigt und die Bestellung bearbeitet oder geliefert wurde. Wählen Sie „Zahlung akzeptiert“ und „Geliefert“, um den Versand von Gutscheinen für stornierte oder ausstehende Bestellungen zu verhindern.
-   **Mindestbestellwert für Gutschein:**

    *   **Was diese Einstellung bewirkt:** Legt einen Mindestgesamtwert (ohne Versand) fest, den eine Bestellung erreichen muss, um sich für einen Gutschein zu qualifizieren.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ein Wert festgelegt ist (z. B. 50):* Nur Bestellungen mit einem Gesamtbetrag von 50 oder mehr lösen einen Gutschein aus.
        *   *Wenn auf 0 (oder leer) gesetzt:* Alle Bestellungen, unabhängig vom Wert, sind berechtigt (wenn andere Bedingungen erfüllt sind).
    *   **Empfohlener Wert:** Ein Wert, der für Ihren durchschnittlichen Bestellwert geschäftlich sinnvoll ist, oder 0, wenn Sie alle Bestellungen belohnen möchten.
    *   **Händlerszenario / Beispiel:** Sie möchten größere Einkäufe fördern. Setzen Sie dies auf 50 €, damit nur Kunden, die 50 € oder mehr ausgeben, einen Rabatt erhalten, wodurch der Gutschein eine Belohnung für höherwertige Transaktionen wird.

#### Gutscheincode-Einstellungen

-   **Gutscheincode-Präfix:**

    *   **Was diese Einstellung bewirkt:** Eine Zeichenfolge, die am Anfang jedes generierten Gutscheincodes erscheint. Dies hilft Ihnen, Gutscheine aus diesem Modul zu identifizieren.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn festgelegt (z. B. „REWARD“):* Codes sehen dann wie „REWARDABCD123“ aus.
        *   *Wenn leer:* Codes bestehen ausschließlich aus zufälligen Zeichen.
    *   **Empfohlener Wert:** Ein kurzes, beschreibendes Präfix wie „REWARD“, „THANKYOU“ oder die Initialen Ihres Shops.
    *   **Händlerszenario / Beispiel:** Sie führen mehrere Aktionen durch. Die Verwendung von „REWARD“ als Präfix hilft Ihnen, in Ihren PrestaShop-Rabattregeln schnell zu erkennen, welche Gutscheine von diesem Modul stammen.
-   **Gutscheincode-Länge:**

    *   **Was diese Einstellung bewirkt:** Definiert die Gesamtzahl der Zeichen im generierten Gutscheincode (einschließlich des Präfixes).
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf 10 mit einem „REWARD“-Präfix gesetzt:* Der zufällige Teil ist 4 Zeichen lang (10 - 6 für „REWARD“).
        *   *Wenn auf eine niedrigere Zahl gesetzt:* Kürzere Codes, potenziell einfacher einzugeben, aber weniger einzigartig.
        *   *Wenn auf eine höhere Zahl gesetzt:* Längere Codes, sicherer, aber schwieriger einzugeben.
    *   **Empfohlener Wert:** 8-12 Zeichen (einschließlich Präfix) für ein gutes Gleichgewicht zwischen Sicherheit und Benutzerfreundlichkeit.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass Codes leicht zu merken, aber dennoch einzigartig sind. Eine Länge von 10-12 Zeichen ist in der Regel ausreichend.
-   **Gutscheinwert-Typ:**

    *   **Was diese Einstellung bewirkt:** Legt fest, ob der Gutschein einen prozentualen Rabatt oder einen festen Betrag bietet.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Prozentsatz:* Der Gutschein zieht einen Prozentsatz des Bestellwerts ab.
        *   *Fester Betrag:* Der Gutschein zieht einen bestimmten Geldbetrag ab.
    *   **Empfohlener Wert:** Hängt von Ihrer Marketingstrategie ab. Prozentsatz ist gut, um größere Bestellungen zu fördern, fester Betrag ist einfacher und klarer.
    *   **Händlerszenario / Beispiel:** Sie möchten 10 % Rabatt auf die nächste Bestellung geben, also wählen Sie „Prozentsatz“. Wenn Sie einen pauschalen Rabatt von 5 € geben möchten, wählen Sie „Fester Betrag“.
-   **Gutscheinwert:**

    *   **Was diese Einstellung bewirkt:** Der tatsächliche Rabattwert. Dies ist ein Prozentsatz (z. B. 10) oder ein fester Betrag (z. B. 5,00), abhängig von der Einstellung „Gutscheinwert-Typ“.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf 10 und „Prozentsatz“ gesetzt:* Kunden erhalten 10 % Rabatt.
        *   *Wenn auf 5,00 und „Fester Betrag“ gesetzt:* Kunden erhalten 5 € Rabatt.
    *   **Empfohlener Wert:** Ein Wert, der das Angebot attraktiv macht, aber für Ihr Geschäft nachhaltig ist.
    *   **Händlerszenario / Beispiel:** Sie entscheiden sich, einen Rabatt von 15 % anzubieten, also geben Sie hier „15“ ein, nachdem Sie oben „Prozentsatz“ ausgewählt haben.
-   **Mindestbestellwert für Gutscheinnutzung:**

    *   **Was diese Einstellung bewirkt:** Legt einen Mindestbestellwert fest, der erforderlich ist, damit der Kunde den generierten Gutscheincode verwenden kann.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf 20 gesetzt:* Der Kunde muss mindestens 20 € für seine nächste Bestellung ausgeben, um den Gutschein anwenden zu können.
        *   *Wenn auf 0 (oder leer) gesetzt:* Der Gutschein kann für jede Bestellung verwendet werden, unabhängig von ihrem Wert.
    *   **Empfohlener Wert:** Ein Wert, der etwas höher ist als Ihr durchschnittlicher Bestellwert, um Upselling zu fördern, oder 0, wenn Sie maximale Benutzerfreundlichkeit wünschen.
    *   **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass der Gutschein einen neuen Kauf fördert, nicht nur eine kleine Ergänzung. Setzen Sie dies auf 25 €, damit der Kunde etwas Wesentliches kaufen muss, um seinen 5 € Gutschein zu verwenden.
-   **Gutscheingültigkeit (Tage):**

    *   **Was diese Einstellung bewirkt:** Definiert, wie viele Tage der generierte Gutscheincode ab dem Erstellungsdatum gültig ist.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf 30 gesetzt:* Der Gutschein läuft 30 Tage nach dem Versand ab.
        *   *Wenn auf 0 (oder leer) gesetzt:* Der Gutschein ist unbegrenzt gültig (nicht empfohlen, da dies die Dringlichkeit aufhebt).
    *   **Empfohlener Wert:** 30-90 Tage, um Dringlichkeit zu schaffen, ohne zu restriktiv zu sein.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass Kunden ihren Gutschein innerhalb eines angemessenen Zeitrahmens verwenden. Setzen Sie dies auf 60 Tage, um ihnen zwei Monate Zeit für einen weiteren Einkauf zu geben.
-   **Gutschein auf bestimmte Kundengruppen anwenden:**

    *   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Nutzung des generierten Gutscheins auf bestimmte Kundengruppen (z. B. „VIP-Kunden“, „Großhändler“) zu beschränken.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ausgewählt:* Nur Kunden, die zu den ausgewählten Gruppen gehören, können den Gutschein verwenden.
        *   *Wenn nicht ausgewählt (oder alle Gruppen ausgewählt):* Jeder Kunde kann den Gutschein verwenden.
    *   **Empfohlener Wert:** Lassen Sie alle ausgewählt, es sei denn, Sie haben eine spezifische Segmentierungsstrategie.
    *   **Händlerszenario / Beispiel:** Sie möchten einen speziellen Rabatt nur Ihrer Gruppe „Registrierte Kunden“ anbieten. Wählen Sie hier nur diese Gruppe aus.
-   **Gutschein auf bestimmte Produkte/Kategorien anwenden:**

    *   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Anwendbarkeit des Gutscheins auf bestimmte Produkte oder Produktkategorien zu beschränken.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ausgewählt:* Der Gutschein gilt nur für Artikel aus den ausgewählten Produkten/Kategorien.
        *   *Wenn nicht ausgewählt (oder keine ausgewählt):* Der Gutschein gilt für alle Produkte im Warenkorb.
    *   **Empfohlener Wert:** Lassen Sie dies für allgemeine shopweite Rabatte nicht ausgewählt. Verwenden Sie dies für gezielte Aktionen.
    *   **Händlerszenario / Beispiel:** Sie möchten eine bestimmte neue Kollektion bewerben. Sie können den Gutschein so konfigurieren, dass er nur für Produkte innerhalb dieser Kategorie gilt.
-   **Reduzierte Produkte ausschließen:**

    *   **Was diese Einstellung bewirkt:** Wenn aktiviert, kann der Gutschein nicht für Produkte verwendet werden, die bereits im Angebot sind oder einen speziellen Preis haben.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Verhindert das „Stapeln“ von Rabatten und stellt sicher, dass Kunden keine doppelten Rabatte erhalten.
        *   *Wenn deaktiviert:* Gutscheine können auf bereits reduzierte Artikel angewendet werden.
    *   **Empfohlener Wert:** JA, um Ihre Gewinnmargen zu schützen.
    *   **Händlerszenario / Beispiel:** Sie führen einen shopweiten 20 %-Sale durch. Sie möchten nicht, dass Kunden ihren Prämiengutschein zusätzlich verwenden, wodurch sie effektiv 30 % Rabatt erhalten. Aktivieren Sie dies, um dies zu verhindern.
-   **Versand ausschließen:**

    *   **Was diese Einstellung bewirkt:** Legt fest, ob der Gutscheinrabatt auf die Versandkosten der Bestellung angewendet wird.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der Gutschein reduziert nur den Produktgesamtbetrag, nicht die Versandkosten.
        *   *Wenn deaktiviert:* Der Gutschein kann den gesamten Bestellwert, einschließlich Versand, reduzieren.
    *   **Empfohlener Wert:** JA, da Versandkosten oft fest sind und nicht Teil Ihrer Produktmarge.
    *   **Händlerszenario / Beispiel:** Sie bieten kostenlosen Versand ab einem bestimmten Schwellenwert an. Sie möchten, dass der Gutschein nur die Produktpreise beeinflusst, nicht die Versandkosten. Aktivieren Sie dies.
-   **Gutschein für die N-te Bestellung:**

    *   **Was diese Einstellung bewirkt:** Dies ist eine leistungsstarke Funktion, mit der Sie festlegen können, für welche Bestellnummer (1., 2., 3. usw.) ein Kunde einen Gutschein erhält.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf 1 gesetzt:* Nur die allererste Bestellung des Kunden löst einen Gutschein aus.
        *   *Wenn auf 2 gesetzt:* Nur seine zweite Bestellung löst einen Gutschein aus.
        *   *Wenn auf 0 (oder leer) gesetzt:* Jede qualifizierende Bestellung löst einen Gutschein aus (wenn andere Bedingungen erfüllt sind).
    *   **Empfohlener Wert:** 1 für ein „Willkommens-Zurück“-Angebot oder 0 für ein allgemeines Treueprogramm. Sie können auch mehrere Regeln (siehe Abschnitt 4.2) für verschiedene N-te Bestellungen erstellen.
    *   **Händlerszenario / Beispiel:** Sie möchten Erstkäufern ein besonderes „Dankeschön“ zukommen lassen. Setzen Sie dies auf „1“. Für ein allgemeines Treueprogramm lassen Sie es auf „0“ oder erstellen Sie spezifische Regeln für die 2., 3. usw. Bestellungen.

#### E-Mail-Vorlagen-Einstellungen

-   **E-Mail-Betreff:**

    *   **Was diese Einstellung bewirkt:** Die Betreffzeile der E-Mail, die Kunden mit ihrem Gutscheincode erhalten.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist, was Kunden in ihrem Posteingang sehen. Eine überzeugende Betreffzeile erhöht die Öffnungsraten.
    *   **Empfohlener Wert:** Etwas Ansprechendes wie „Ihr spezieller Rabatt für Ihre nächste Bestellung!“ oder „Vielen Dank! Hier ist ein Geschenk von uns.“
    *   **Händlerszenario / Beispiel:** Sie möchten deutlich machen, dass dies eine Belohnung ist. Setzen Sie den Betreff auf „Ihr exklusiver Gutschein von [Ihr Shop-Name]!“
-   **E-Mail-Inhalt:**

    *   **Was diese Einstellung bewirkt:** Der Hauptteil der E-Mail. Sie können Platzhalter wie `{customer_name}`, `{voucher_code}`, `{voucher_value}`, `{min_order_total}`, `{validity_days}` verwenden, um die Nachricht zu personalisieren.
    *   **Auswirkung einer Änderung dieser Einstellung:** Hier kommunizieren Sie den Wert des Gutscheins und wie er verwendet wird. Eine klare, freundliche Nachricht fördert die Nutzung.
    *   **Empfohlener Wert:** Eine einladende Nachricht, klare Anweisungen und alle relevanten Gutscheindetails.
    *   **Händlerszenario / Beispiel:** „Liebe/r {customer\_name}, vielen Dank für Ihren letzten Einkauf! Als Zeichen unserer Wertschätzung erhalten Sie hier einen {voucher\_value} Rabattcode für Ihre nächste Bestellung: **{voucher\_code}**. Dieser Gutschein ist {validity\_days} Tage gültig und kann für Bestellungen über {min\_order\_total} verwendet werden. Viel Spaß beim Einkaufen!“
-   **E-Mail an Kunden senden:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob die E-Mail mit dem Gutschein tatsächlich an den Kunden gesendet wird.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Kunden erhalten die E-Mail.
        *   *Wenn deaktiviert:* Gutscheine werden weiterhin generiert (wenn aktiviert), aber Kunden erhalten keine E-Mail-Benachrichtigung. Sie müssten den Gutscheincode dann über einen anderen Kanal kommunizieren.
    *   **Empfohlener Wert:** JA, da E-Mail die primäre Zustellmethode für dieses Modul ist.
    *   **Händlerszenario / Beispiel:** Sie haben alles eingerichtet und möchten, dass Kunden ihre Prämien erhalten. Aktivieren Sie dies. Wenn Sie testen oder Codes manuell versenden möchten, können Sie es vorübergehend deaktivieren.

#### Cron-Job-Einstellungen

-   **Cron-Job-URL:**
    *   **Was diese Einstellung bewirkt:** Dies ist eine eindeutige URL, die, wenn sie aufgerufen wird, das Modul dazu veranlasst, nach neuen qualifizierenden Bestellungen zu suchen und Gutscheine zu generieren/zu versenden.
    *   **Auswirkung einer Änderung dieser Einstellung:** Diese URL ist entscheidend für die Automatisierung des Moduls. Sie muss regelmäßig aufgerufen werden.
    *   **Empfohlener Wert:** Ändern Sie diese URL NICHT. Kopieren Sie sie und richten Sie sie in Ihrem Hosting-Kontrollpanel ein.
    *   **Händlerszenario / Beispiel:** Sie kopieren diese URL und fügen sie in den Cron-Job-Manager Ihres Hosting-Anbieters (z. B. cPanel, Plesk) ein, um sie alle 15-30 Minuten auszuführen. Dies stellt sicher, dass Gutscheine umgehend nach der Bearbeitung von Bestellungen versendet werden.

### 2.2 Dedizierter Admin-Bildschirm: Prämienliste (Back Office > Rewards > Rewards List)

Dieser Bildschirm bietet einen umfassenden Überblick über alle vom Modul generierten Gutscheincodes. Er dient als Protokoll- und Verwaltungsoberfläche für Ihr Prämienprogramm.

-   **Bildschirmname & Menüpfad:** **Prämienliste** (zu finden unter einem neuen Menüpunkt „Rewards“ in Ihrem PrestaShop Back Office oder möglicherweise unter „Katalog“ oder „Marketing“, abhängig von Ihrer PrestaShop-Version und Ihrem Theme).
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Tabellenspalten:** Sie sehen eine Tabelle mit den folgenden Spalten:
        *   **ID:** Die eindeutige Kennung für den Prämieneintrag.
        *   **Bestell-ID:** Die ID der PrestaShop-Bestellung, die diese Prämie ausgelöst hat.
        *   **Kunde:** Der Name des Kunden, der den Gutschein erhalten hat.
        *   **E-Mail:** Die E-Mail-Adresse des Kunden.
        *   **Bestellreferenz:** Die eindeutige Referenznummer der Bestellung.
        *   **Prämiencode:** Der tatsächlich generierte und an den Kunden gesendete Gutscheincode.
        *   **Generierungsdatum:** Datum und Uhrzeit der Gutscheingenerierung.
    *   **Filtern & Suchen:** Sie können typischerweise nach jeder dieser Spalten filtern oder suchen (z. B. nach einer bestimmten Kunden-E-Mail, Bestell-ID oder einem Gutscheincode), um bestimmte Prämieneinträge zu finden.
    *   **Keine „Hinzufügen/Bearbeiten“-Schaltflächen:** Dieser Bildschirm dient hauptsächlich zur Anzeige generierter Prämien. Gutscheine werden automatisch basierend auf Ihrer Konfiguration erstellt, nicht manuell hier hinzugefügt.
-   **Auswirkung von Änderungen:** Dieser Bildschirm ist ein schreibgeschütztes Protokoll. Änderungen an der Modulkonfiguration (Abschnitt 4.1) wirken sich auf *zukünftige* Gutscheingenerierungen aus, aber bestehende Einträge hier spiegeln vergangene Ereignisse wider.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    *   Überprüfen Sie diese Liste regelmäßig, um die Aktivität Ihres Prämienprogramms zu überwachen.
    *   Wenn ein Kunde behauptet, keinen Gutschein erhalten zu haben, können Sie seine Bestellung hier schnell nachschlagen, den „Prämiencode“ finden und das Generierungsdatum bestätigen. Sie können den Code dann bei Bedarf manuell an den Kunden weitergeben.
    *   Verwenden Sie die Filteroptionen, um zu analysieren, welche Bestellungen Prämien auslösen, oder um spezifische Kundenanfragen zu beheben.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Funktionalität des Moduls. |
| | Bestellstatus für Gutscheingenerierung | Zahlung akzeptiert, Geliefert | Definiert, welche Bestellstatus die Gutscheingenerierung auslösen. |
| | Mindestbestellwert für Gutschein | 0 (oder Ihr gewünschter Wert) | Mindestbestellwert, damit eine Bestellung für einen Gutschein qualifiziert ist. |
| | Gutscheincode-Präfix | REWARD (oder Ihre Wahl) | Präfix für generierte Gutscheincodes. |
| | Gutscheincode-Länge | 8-12 | Gesamtlänge des Gutscheincodes. |
| | Gutscheinwert-Typ | Prozentsatz / Fester Betrag | Wählen Sie zwischen einem prozentualen oder festen Rabatt. |
| | Gutscheinwert | Ihr gewünschter Wert (z. B. 10 oder 5,00) | Der tatsächliche Rabattwert des Gutscheins. |
| | Mindestbestellwert für Gutscheinnutzung | 0 (oder Ihr gewünschter Wert) | Mindestbestellwert, der zur *Nutzung* des Gutscheins erforderlich ist. |
| | Gutscheingültigkeit (Tage) | 30-90 | Wie viele Tage der Gutschein nach der Generierung gültig ist. |
| | Gutschein auf bestimmte Kundengruppen anwenden | Alle ausgewählt | Beschränkt die Gutscheinnutzung auf ausgewählte Kundengruppen. |
| | Gutschein auf bestimmte Produkte/Kategorien anwenden | Keine ausgewählt | Beschränkt die Gutscheinnutzung auf ausgewählte Produkte/Kategorien. |
| | Reduzierte Produkte ausschließen | JA | Verhindert, dass Gutscheine auf bereits reduzierte Artikel angewendet werden. |
| | Versand ausschließen | JA | Verhindert, dass Gutscheine die Versandkosten reduzieren. |
| | Gutschein für N-te Bestellung | 0 (oder 1 für erste Bestellung) | Legt fest, für welche Bestellnummer (1., 2. usw.) ein Gutschein generiert wird. |
| | E-Mail-Betreff | Ihr spezieller Rabatt! | Betreffzeile der E-Mail mit dem Gutschein. |
| | E-Mail-Inhalt | Personalisierte Nachricht mit Platzhaltern | Hauptteil der E-Mail, einschließlich Gutscheindetails. |
| | E-Mail an Kunden senden | JA | Steuert, ob die Gutschein-E-Mail an den Kunden gesendet wird. |
| | Cron-Job-URL | NICHT ändern | Essentielle URL für die automatisierte Gutscheingenerierung. |
| **Prämienliste** | ID, Bestell-ID, Kunde, E-Mail, Bestellreferenz, Prämiencode, Generierungsdatum | N/A (schreibgeschützt) | Zeigt ein Protokoll aller generierten Gutscheine zur Überwachung und Fehlerbehebung an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten keine Gutschein-E-Mails. Was soll ich überprüfen?**
A:

1.  **Modul aktiviert?** Überprüfen Sie nochmals, ob „Modul aktivieren“ in der Modulkonfiguration auf JA eingestellt ist.
2.  **Bestellstatus:** Stellen Sie sicher, dass der Status der Bestellung mit einem der von Ihnen ausgewählten „Bestellstatus für Gutscheingenerierung“ übereinstimmt.
3.  **Cron-Job:** Überprüfen Sie, ob Ihr Cron-Job korrekt eingerichtet ist und regelmäßig auf Ihrem Hosting ausgeführt wird. Die „Cron-Job-URL“ muss aufgerufen werden, damit das Modul Bestellungen verarbeiten kann.
4.  **E-Mail-Versand aktiviert:** Stellen Sie sicher, dass „E-Mail an Kunden senden“ auf JA eingestellt ist.
5.  **Spam-Ordner:** Bitten Sie Kunden, ihre Spam- oder Junk-Ordner zu überprüfen.
6.  **PrestaShop-E-Mail-Einstellungen:** Überprüfen Sie die Haupt-E-Mail-Konfiguration Ihres PrestaShops (Erweiterte Einstellungen > E-Mail), um sicherzustellen, dass E-Mails erfolgreich von Ihrem Shop gesendet werden.

**F: Gutscheine werden generiert, aber sie scheinen für Kunden nicht zu funktionieren.**
A:

1.  **Gutscheingültigkeit:** Überprüfen Sie die Einstellung „Gutscheingültigkeit (Tage)“. Ist der Gutschein abgelaufen?
2.  **Mindestbestellwert für Nutzung:** Erfüllt der aktuelle Warenkorb des Kunden den „Mindestbestellwert für Gutscheinnutzung“?
3.  **Kundengruppen:** Gehört der Kunde zu den ausgewählten „Gutschein auf bestimmte Kundengruppen anwenden“?
4.  **Produkt-/Kategoriebeschränkungen:** Sind die Produkte im Warenkorb des Kunden gemäß „Gutschein auf bestimmte Produkte/Kategorien anwenden“ berechtigt?
5.  **Reduzierte Produkte ausgeschlossen:** Versucht der Kunde, den Gutschein für ein bereits reduziertes Produkt zu verwenden, und „Reduzierte Produkte ausschließen“ ist aktiviert?
6.  **Tippfehler:** Bitten Sie den Kunden, den Gutscheincode auf Tippfehler zu überprüfen.

**F: Ich möchte verschiedene Gutscheine für verschiedene Bestellnummern anbieten (z. B. 1., 2., 5. Bestellung). Wie mache ich das?**
A: Die Modulbeschreibung weist auf die Unterstützung von „vielen Arten von Aktionen wie: Gutschein für die erste Bestellung, Gutschein für die zweite Bestellung, fünfte, sechste usw.“ hin. Dies impliziert, dass das Modul einen Mechanismus zur Definition mehrerer Regeln basierend auf der N-ten Bestellung besitzt.

-   **Prüfen Sie auf mehrere Regel-Tabs:** Suchen Sie nach zusätzlichen Tabs oder Abschnitten innerhalb der Modulkonfiguration, die es Ihnen ermöglichen, „Neue Regel hinzufügen“ oder separate Konfigurationen für verschiedene „N-te Bestellung“-Werte zu definieren. Wenn eine solche Oberfläche existiert, würden Sie für jede N-te Bestellung eine separate Regel mit ihren spezifischen Gutscheineinstellungen erstellen.
-   **Wenn nur ein Feld „Gutschein für N-te Bestellung“ existiert:** Wenn das Modul nur ein einziges Feld „Gutschein für N-te Bestellung“ auf der Hauptkonfigurationsseite anzeigt, bedeutet dies, dass Sie nur *eine* solche Regel gleichzeitig festlegen können. Um ein gestaffeltes System zu implementieren, müssten Sie diese Einstellung nach einer bestimmten Zeit manuell ändern oder prüfen, ob die aktuelle Version des Moduls diese erweiterte Funktionalität über eine weniger offensichtliche Schnittstelle unterstützt. Für die meisten Benutzer ist die Einstellung auf `0` (jede Bestellung) oder `1` (nur erste Bestellung) der primäre Anwendungsfall.

**F: Das Modul verlangsamt mein Back Office / Front Office.**
A: Dieses Modul arbeitet hauptsächlich im Hintergrund über einen Cron-Job und hat minimale Auswirkungen auf die Front-Office-Leistung. Wenn Sie Verlangsamungen bemerken:

1.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie Ihren PrestaShop-Cache.
2.  **Serverressourcen prüfen:** Überwachen Sie die CPU- und Speichernutzung Ihres Servers, insbesondere wenn der Cron-Job ausgeführt wird. Wenn Ihr Server unterdimensioniert ist, können selbst einfache Aufgaben zu Verlangsamungen führen.
3.  **Andere Module:** Deaktivieren Sie vorübergehend andere kürzlich installierte Module, um zu sehen, ob es einen Konflikt gibt.

**F: Kann ich die E-Mail-Vorlage weiter anpassen?**
A: Ja, das Modul bietet die Felder „E-Mail-Betreff“ und „E-Mail-Inhalt“ mit Platzhaltern für grundlegende Anpassungen. Für fortgeschrittene Designänderungen (z. B. Hinzufügen Ihres Shop-Logos, Ändern von Schriftarten/Farben) müssten Sie typischerweise die E-Mail-Vorlagendateien des Moduls direkt ändern. Dies erfordert normalerweise einen Webmaster oder Entwickler. Die interne Struktur des Moduls deutet darauf hin, dass es `lib/emailTemplatesManager` verwendet, was möglicherweise eine erweiterte Vorlagenverwaltung innerhalb des Moduls selbst bietet, aber die primäre Konfiguration erfolgt über die Textfelder.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Rewards - Gutscheincodes nach Bestellungen“ folgt einer Standard-PrestaShop-Modularchitektur und nutzt, wo anwendbar, MVC-Prinzipien. Seine Kernfunktionalität dreht sich um einen Cron-Job-Mechanismus, der regelmäßig nach qualifizierenden Bestellungen sucht und, sobald er diese findet, PrestaShop `CartRule`-Objekte (Gutscheine) generiert und E-Mails versendet. Das Modul erweitert `Module` für seine Hauptfunktionalität und verwendet `AdminController` für seine Back-Office-Verwaltungsoberfläche. Es integriert auch mehrere Dienstprogrammbibliotheken für die E-Mail-Vorlagenverwaltung und Suchfunktionalität.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `controllers/front/cronJob.php`
    *   **Klassenname:** `OrdercouponsCronJobModuleFrontController` (wahrscheinlich, basierend auf dem Dateinamen)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dieser Controller ist so konzipiert, dass er über die in der Modulkonfiguration bereitgestellte Cron-Job-URL aufgerufen wird. Wenn er aufgerufen wird, löst er die Hauptlogik innerhalb der Moduldatei `cronjob.php` aus, um Bestellungen zu verarbeiten, Gutscheine zu generieren und E-Mails zu versenden. Er rendert typischerweise keinen Front-Office-Inhalt, sondern führt Hintergrundaufgaben aus.
-   `controllers/front/index.php`
    *   **Klassenname:** `OrdercouponsIndexModuleFrontController` (wahrscheinlich)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dies ist oft ein Platzhalter oder ein einfacher Umleitungs-Controller. In vielen Modulen stellt `index.php` in einem Controller-Verzeichnis lediglich sicher, dass der direkte Zugriff auf das Verzeichnis nicht zu einer Verzeichnisauflistung führt, oder es könnte minimale Logik für eine Standard-Front-Office-Ansicht enthalten, falls das Modul eine hätte. Für dieses Modul ist es unwahrscheinlich, dass es eine signifikante Front-Office-Rendering-Verantwortung hat.

#### Back-Office-Admin-Controller

-   `controllers/admin/AdminOrderCouponsRewards.php`
    *   **Klassenname:** `AdminOrderCouponsRewardsController`
    *   **Elternklasse:** `ModuleAdminController` (oder `AdminController` in älteren Versionen)
    *   **Tab-Name:** „Prämienliste“ (unter einem Menüpunkt „Rewards“)
    *   **Verwaltete Entität:** `orewards_list` (wahrscheinlich eine benutzerdefinierte Datenbanktabelle zum Protokollieren generierter Prämien).
    *   **Verantwortlichkeit:** Dieser Controller verwaltet die „Prämienliste“ im PrestaShop Back Office. Er zeigt eine Liste aller generierten Gutscheincodes, zugehörigen Bestell-IDs, Kundendetails und Generierungsdaten an. Er verwendet `HelperList` zum Rendern der Tabelle und bietet Filterfunktionen. Er erlaubt keine manuelle Erstellung oder Bearbeitung von Prämien, da diese automatisch generiert werden.
-   `controllers/admin/index.php`
    *   **Klassenname:** `AdminOrdercouponsIndexController` (wahrscheinlich)
    *   **Elternklasse:** `ModuleAdminController` (oder `AdminController`)
    *   **Verantwortlichkeit:** Ähnlich wie die Front-Office-`index.php` ist dies wahrscheinlich ein Platzhalter oder ein Standard-Controller für den Admin-Bereich, der den Verzeichnisschutz gewährleistet oder eine Fallback-Ansicht bereitstellt. Die primäre Admin-Funktionalität wird von `AdminOrderCouponsRewards.php` gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass die Kernlogik des Moduls zur Gutscheingenerierung direkt in der Hauptmoduldatei `cronjob.php` enthalten sein oder PrestaShops integriertes `CartRule` (Rabatt) `ObjectModel` und dessen zugehörige Methoden nutzen könnte.

-   **`CartRule`-Interaktion:** Das Modul würde direkt mit der PrestaShop-Klasse `CartRule` interagieren, um neue Rabattcodes zu erstellen. Dies beinhaltet das Setzen von Eigenschaften wie `code`, `value`, `reduction_type`, `minimum_amount`, `date_from`, `date_to`, `quantity`, `quantity_per_user`, `id_customer`, `id_group`, `id_product`, `id_category`, `reduction_exclude_special`, `free_shipping` usw., basierend auf der Modulkonfiguration.
-   **Benutzerdefinierte Tabelle `orewards_list`:** Obwohl kein `ObjectModel` explizit aufgeführt ist, verwaltet der `AdminOrderCouponsRewardsController` `orewards_list`. Dies impliziert stark, dass eine benutzerdefinierte Datenbanktabelle `ps_orewards_list` (oder ein ähnliches Präfix) existiert, um die generierten Prämien zu protokollieren. Der Controller würde diese Tabelle direkt abfragen oder eine einfache Datenzugriffsschicht verwenden.

### 4.4 JavaScript-Assets (`views/js/`)

-   `ordercoupons/js/script.js`
    *   **Geltungsbereich:** Wahrscheinlich Back-Office.
    *   **Verantwortlichkeit:** Allgemeines JavaScript für die Konfigurationsseite des Moduls oder Admin-Bildschirme. Dies könnte Formularvalidierung, AJAX-Aufrufe zum Speichern von Einstellungen, dynamische UI-Updates oder Event-Listener für spezifische Konfigurationsoptionen umfassen.
-   `ordercoupons/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Verwaltet die Bearbeitungsoberfläche für E-Mail-Vorlagen. Dieses Skript würde die dynamische Einfügung von Platzhaltern, Rich-Text-Bearbeitungsfunktionen, Vorschaufunktionen und das Speichern von E-Mail-Inhalten handhaben.
-   `ordercoupons/lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Eingabefelder, wahrscheinlich verwendet zur Auswahl spezifischer Produkte, Kategorien oder Kundengruppen innerhalb der Konfigurationsformulare des Moduls. Es würde AJAX-Anfragen zur Abfrage von Suchergebnissen und deren Anzeige für den Benutzer handhaben.
-   `ordercoupons/lib/voucherengine/script.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Spezifisches JavaScript im Zusammenhang mit der Gutscheingenerierungs-Engine. Dies könnte Logik für die dynamische Berechnung der Gutscheincode-Länge, die Validierung von Gutscheinwerten oder die Interaktion mit den `CartRule`-Einstellungen im Konfigurationsformular umfassen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `ordercoupons/css.css`
    *   **Geltungsbereich:** Primär Back-Office, potenziell auch Front-Office, wenn das Modul sichtbare Elemente hätte. Angesichts der Natur des Moduls hauptsächlich für Admin-Styling.
    *   **Haupt-UI-Komponenten:** Allgemeine Gestaltung für die Konfigurationsseite des Moduls und die Tabelle „Prämienliste“.
    *   **Wichtige CSS-Klassenselektoren:** `.ordercoupons-config`, `.ordercoupons-table`, `.ordercoupons-form-group`.
-   `ordercoupons/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Haupt-UI-Komponenten:** Stile für die E-Mail-Vorlagen-Editor-Oberfläche, einschließlich Textbereichen, Schaltflächen und Vorschauabschnitten.
    *   **Wichtige CSS-Klassenselektoren:** `.email-template-editor`, `.template-preview`.
-   `ordercoupons/lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Haupt-UI-Komponenten:** Styling für die Autocomplete-Dropdowns und Eingabefelder.
    *   **Wichtige CSS-Klassenselektoren:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `ordercoupons/lib/voucherengine/ps16.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Haupt-UI-Komponenten:** Spezifische Stil-Anpassungen für PrestaShop 1.6-Kompatibilität oder spezifische Elemente im Zusammenhang mit der Gutschein-Engine, um ein konsistentes Erscheinungsbild über verschiedene PS-Versionen hinweg zu gewährleisten.
    *   **Wichtige CSS-Klassenselektoren:** `.voucher-engine-settings`, `.ps16-compat`.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

Das Inventar listet keine Vorlagen direkt unter `views/templates/hook/` auf. Dies bestätigt, dass das Modul keine visuellen Inhalte direkt in Standard-PrestaShop-Hooks wie `displayHeader`, `displayRightColumn`, `displayFooter` usw. rendert. Die Front-Office-Interaktion erfolgt ausschließlich per E-Mail.

#### Admin-Vorlagen (`views/templates/admin/`)

-   `ordercoupons/views/templates/admin/admin.tpl`
    *   **Zweck:** Die Hauptvorlage für die Konfigurationsseite des Moduls (zugänglich über `getContent()` in `cronjob.php`). Sie würde die Formularstruktur für alle in Abschnitt 4.1 beschriebenen Einstellungen enthalten.
-   `ordercoupons/views/templates/admin/customerGroups.tpl`
    *   **Zweck:** Eine Teilvorlage, die wahrscheinlich innerhalb von `admin.tpl` verwendet wird, um die Auswahl-Oberfläche für „Gutschein auf bestimmte Kundengruppen anwenden“ zu rendern.
-   `ordercoupons/views/templates/admin/orderstates.tpl`
    *   **Zweck:** Eine Teilvorlage, die wahrscheinlich innerhalb von `admin.tpl` verwendet wird, um die Auswahl-Oberfläche für „Bestellstatus für Gutscheingenerierung“ zu rendern.
-   `ordercoupons/views/templates/admin/scripts.tpl`
    *   **Zweck:** Eine Teilvorlage, die verwendet wird, um JavaScript-Dateien oder Inline-JavaScript speziell für die Admin-Konfigurationsseite einzubinden. Dies ist eine gängige Praxis, um JS von der Haupt-HTML-Struktur getrennt zu halten.

#### Front-Office-Vorlagen (`views/templates/front/`)

Das Inventar listet keine Vorlagen direkt unter `views/templates/front/` auf. Dies stimmt mit dem Verhalten des Moduls überein, keine Front-Office-Inhalte anzuzeigen.

#### Bibliotheksvorlagen

-   `ordercoupons/lib/emailTemplatesManager/views/buttonManager.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/createTemplateForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/editTemplateForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/mainForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/selectInput.tpl`
    *   **Zweck:** Diese Vorlagen sind Teil der `emailTemplatesManager`-Bibliothek und werden verwendet, um die Oberfläche zur Verwaltung und Bearbeitung von E-Mail-Vorlagen innerhalb der Modulkonfiguration zu rendern. `mainForm.tpl` wäre wahrscheinlich der primäre Einstiegspunkt, wobei die anderen Teilstücke für spezifische UI-Elemente sind.
-   `ordercoupons/lib/searchTool/views/scripts.tpl`
    *   **Zweck:** Eine Vorlage zum Einbinden von JavaScript-Dateien oder Inline-Skripten für die `searchTool`-Bibliothek, speziell für die Autocomplete-Funktionalität.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

-   **`ps_configuration`**: Das Modul speichert seine Konfigurationseinstellungen (z. B. `ORDERCOUPONS_ENABLED`, `ORDERCOUPONS_ORDER_STATES`, `ORDERCOUPONS_VOUCHER_VALUE`) in der Standard-PrestaShop-Tabelle `ps_configuration`.
-   **`ps_orewards_list` (Implizite benutzerdefinierte Tabelle)**: Basierend auf dem `AdminOrderCouponsRewardsController`, der `orewards_list` verwaltet, ist es sehr wahrscheinlich, dass das Modul eine benutzerdefinierte Datenbanktabelle, wahrscheinlich `ps_orewards_list` genannt, erstellt, um jeden generierten Gutschein zu protokollieren.
    *   **Schema (Wahrscheinliche Felder):**
        *   `id_orewards_list` (PRIMÄRSCHLÜSSEL, INT)
        *   `id_order` (INT)
        *   `id_customer` (INT)
        *   `customer_email` (VARCHAR)
        *   `order_reference` (VARCHAR)
        *   `reward_code` (VARCHAR)
        *   `date_add` (DATETIME)

#### Registrierte Hooks-Tabelle

Die Modulbeschreibung erwähnt „Front-Office-Hooks: Header, Spalten, Produkt oder Footer“. Die Dateiliste und die Kernfunktion des Moduls (E-Mail-Versand von Gutscheinen) deuten jedoch darauf hin, dass diese wahrscheinlich *nicht* zur Anzeige von Inhalten verwendet werden, sondern möglicherweise für die interne Verarbeitung oder das Laden von Assets, falls das Modul Front-End-Komponenten hätte. Angesichts der Natur des Moduls sind die kritischsten Hooks Aktions-Hooks.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert und in der Datenbank gespeichert wurde. | Dies ist der wahrscheinlichste Hook für das Modul, um neue Bestellungen zu erkennen, die für die Gutscheingenerierung verarbeitet werden müssen. Das Modul würde auf dieses Ereignis hören, um potenzielle Kandidaten zu identifizieren. |
| `actionOrderStatusPostUpdate` | Nachdem der Status einer Bestellung im Back Office geändert wurde. | Entscheidend für das Modul, um zu prüfen, ob eine Bestellung einen der konfigurierten „Bestellstatus für Gutscheingenerierung“ erreicht hat (z. B. „Zahlung akzeptiert“, „Geliefert“). Hier würde der Cron-Job wahrscheinlich die Gutscheingenerierungslogik auslösen. |
| `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Bereich des Back Office. | Wird verwendet, um modulspezifische CSS- und JavaScript-Dateien für die Admin-Konfigurationsseiten und den Bildschirm „Prämienliste“ einzubinden. |
| `moduleRoutes` | Ermöglicht Modulen, benutzerdefinierte freundliche URLs zu definieren. | Weniger wahrscheinlich für dieses Modul, aber möglich, wenn es eine spezifische Route für seinen Cron-Job oder andere interne Prozesse benötigte. |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich des Front Office. | Wenn das Modul globale JS/CSS für potenzielle zukünftige Front-End-Funktionen oder zu Tracking-Zwecken laden müsste. (Unwahrscheinlich für die aktuelle Funktionalität). |
| `displayRightColumn` / `displayLeftColumn` | Rendert Inhalte in den Seitenleisten des Front Office. | Wird für die aktuelle Funktionalität dieses Moduls nicht verwendet. |
| `displayFooter` | Rendert Inhalte im Footer des Front Office. | Wird für die aktuelle Funktionalität dieses Moduls nicht verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und den offiziellen Support für das Modul „Rewards - Gutscheincodes nach Bestellungen“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Sie können die neuesten Versionen aus Ihrer Bestellhistorie herunterladen und auf dedizierte Supportkanäle für technische Unterstützung oder Anfragen zugreifen.
