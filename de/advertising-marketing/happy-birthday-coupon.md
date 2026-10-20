---
title: "Happy Birthday Coupon - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Happy Birthday Coupon von MyPresta.eu."
sidebar:
  label: "Happy Birthday Coupon - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Happy Birthday Coupon auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/happy-birthday-coupon.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/happy-birthday-coupon/)
>
> ---


# Happy Birthday Coupon

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Stellen Sie sicher, dass die Cron-Job-Funktionalität Ihres Servers für den automatischen Gutscheinversand aktiviert ist.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Happy Birthday Coupon)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie definieren, wie Ihre Geburtstagsgutscheine generiert und versendet werden.

#### Allgemeine Einstellungen

- **Tage vor dem Geburtstag des Kunden, an denen der Gutschein gesendet werden soll (bp\_daysbefore)**

  - **Was diese Einstellung bewirkt:** Dies bestimmt, wie viele Tage *vor* dem tatsächlichen Geburtstag eines Kunden die Gutschein-E-Mail gesendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 0 gesetzt:* Der Gutschein wird am Geburtstag des Kunden gesendet.
    - *Wenn auf 7 gesetzt:* Der Gutschein wird 7 Tage vor dem Geburtstag des Kunden gesendet. Dies gibt ihnen eine Woche Zeit, einen Einkauf zu planen.
  - **Empfohlener Wert:** `7` Tage. Dies gibt Kunden genügend Zeit, Ihren Shop zu durchsuchen und eine Kaufentscheidung zu treffen, anstatt ihn am Tag selbst zu erhalten, wenn sie möglicherweise beschäftigt sind.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden ihr Geburtstagsgeschenk eine Woche im Voraus erhalten, damit sie Zeit haben, es für einen besonderen Geburtstagseinkauf zu nutzen. Wenn Sie dies auf `7` setzen, erhalten sie die E-Mail mit ausreichend Zeit.
- **Newsletter-Option aktivieren (bpro\_nletter)**

  - **Was diese Einstellung bewirkt:** Dies steuert, ob die Geburtstagsgutschein-Funktionalität an den Newsletter-Abonnementstatus des Kunden gebunden ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nur Kunden, die Ihren Newsletter abonniert haben, erhalten einen Geburtstagsgutschein.
    - *Wenn deaktiviert (NEIN):* Alle Kunden mit einem gültigen Geburtsdatum in ihrem Konto erhalten einen Geburtstagsgutschein, unabhängig von ihrem Newsletter-Abonnement.
  - **Empfohlener Wert:** `NEIN`. Um die Wirkung und Reichweite zu maximieren, ist es im Allgemeinen besser, Geburtstagsgutscheine an alle Kunden mit einem Geburtsdatum zu senden, da es sich um eine persönliche Geste handelt. Wenn Sie jedoch gezielt Newsletter-Abonnenten belohnen möchten, setzen Sie es auf `JA`.
  - **Händlerszenario / Beispiel:** Sie möchten alle Ihre treuen Kunden an ihrem Geburtstag belohnen, nicht nur diejenigen, die Ihren Newsletter abonniert haben. Sie würden dies auf `NEIN` setzen.
- **Kundengruppen, die eingeschlossen werden sollen (birthdaypro\_groups)**

  - **Was diese Einstellung bewirkt:** Hier können Sie bestimmte Kundengruppen auswählen, die berechtigt sind, Geburtstagsgutscheine zu erhalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn bestimmte Gruppen ausgewählt sind:* Nur Kunden, die zu diesen ausgewählten Gruppen gehören, erhalten Geburtstagsgutscheine.
    - *Wenn keine Gruppen ausgewählt sind (oder alle ausgewählt sind):* Alle Kunden (vorbehaltlich anderer Einstellungen wie der Newsletter-Option) sind berechtigt.
  - **Empfohlener Wert:** Wählen Sie `Kunde` und alle anderen Gruppen aus, die Sie einschließen möchten. Vermeiden Sie die Auswahl von `Besucher` oder `Gast`, da diese in der Regel keine Konten mit Geburtsdaten haben.
  - **Händlerszenario / Beispiel:** Sie haben eine Gruppe „VIP-Kunden“ und eine Gruppe „Großhandel“. Sie möchten Geburtstagsgutscheine nur an Ihre reguläre Gruppe „Kunde“ und „VIP-Kunden“ senden, aber nicht an Ihre Großhandelspartner. Sie würden „Kunde“ und „VIP-Kunden“ aus der Liste auswählen.
- **Kundenliste (Informationszwecke)**

  - **Was diese Einstellung bewirkt:** Dies ist keine Einstellung zum Ändern, sondern ein Informationsbereich, der wahrscheinlich eine Liste von Kunden anzeigt, die Geburtstagsgutscheine erhalten haben oder dafür berechtigt sind. Es hilft Ihnen, die Aktivität des Moduls zu überwachen.
  - **Auswirkung der Änderung dieser Einstellung:** Keine direkte Auswirkung, da es sich um eine reine Anzeigefunktion handelt.
  - **Empfohlener Wert:** N/A
  - **Händlerszenario / Beispiel:** Sie möchten schnell sehen, welche Kunden Geburtsdaten hinterlegt haben und bald Gutscheine erhalten könnten.

#### Gutscheineinstellungen (Erweiterte Personalisierung)

Das Modul ermöglicht eine umfassende Anpassung der generierten Gutscheine. Diese Einstellungen spiegeln die Standardoptionen für PrestaShop-Warenkorbregeln (Gutscheine) wider.

- **Gutscheincode-Präfix:** (z.B. `GEBURTSTAG-`)

  - **Was diese Einstellung bewirkt:** Definiert ein Präfix für alle generierten Geburtstagsgutscheincodes.
  - **Auswirkung der Änderung dieser Einstellung:** Alle eindeutigen Codes beginnen mit diesem Präfix, wodurch sie leicht identifizierbar sind.
  - **Empfohlener Wert:** `GEBURTSTAG-` oder `BDP-`.
  - **Händlerszenario / Beispiel:** Sie möchten Geburtstagsgutscheine in Ihrer Bestellhistorie leicht von anderen Aktionen unterscheiden.
- **Rabattart:** (z.B. Prozent, Betrag, Kostenloser Versand)

  - **Was diese Einstellung bewirkt:** Bestimmt die Art des Rabatts, den der Gutschein bietet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Prozentsatz:* Wendet einen prozentualen Rabatt auf die Bestellung an.
    - *Betrag:* Wendet einen festen monetären Rabatt an.
    - *Kostenloser Versand:* Bietet kostenlosen Versand.
  - **Empfohlener Wert:** `Prozentsatz` oder `Betrag`, je nach Ihrer Marketingstrategie.
  - **Händlerszenario / Beispiel:** Sie möchten einen 15%igen Rabatt zum Geburtstag anbieten. Sie würden `Prozentsatz` auswählen und den Wert auf `15` setzen.
- **Rabattwert:** (z.B. `15` für Prozentsatz, `10.00` für Betrag)

  - **Was diese Einstellung bewirkt:** Der tatsächliche Wert des Rabatts.
  - **Auswirkung der Änderung dieser Einstellung:** Wirkt sich direkt auf den Rabatt aus, der auf die Bestellung des Kunden angewendet wird.
  - **Empfohlener Wert:** Ein Wert, der attraktiv, aber auch profitabel für Ihren Shop ist (z.B. `10` für 10% oder `5.00` für 5 €).
  - **Händlerszenario / Beispiel:** Im obigen Beispiel würden Sie hier `15` eingeben.
- **Mindestbetrag:**

  - **Was diese Einstellung bewirkt:** Legt einen Mindestbestellwert fest, der für die Gültigkeit des Gutscheins erforderlich ist.
  - **Auswirkung der Änderung dieser Einstellung:** Ermutigt Kunden, mehr auszugeben, um sich für den Rabatt zu qualifizieren.
  - **Empfohlener Wert:** Ein angemessener Betrag, der Upselling fördert, ohne prohibitiv zu sein.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden mindestens 50 € ausgeben, um ihren Geburtstagsgutschein zu verwenden. Sie würden dies auf `50.00` setzen.
- **Gültigkeitsdauer:** (z.B. `30` Tage)

  - **Was diese Einstellung bewirkt:** Definiert, wie viele Tage der Gutschein ab dem Versanddatum gültig ist.
  - **Auswirkung der Änderung dieser Einstellung:** Erzeugt Dringlichkeit für den Kunden, den Gutschein zu verwenden.
  - **Empfohlener Wert:** `30` Tage. Dies gibt Kunden ein gutes Zeitfenster, um ihr Geschenk zu nutzen, ohne sich gehetzt zu fühlen.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden ihren Geburtstagsgutschein innerhalb eines Monats nach Erhalt verwenden. Sie würden dies auf `30` setzen.
- **Auf bestimmte Produkte/Kategorien anwenden:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Verwendung des Gutscheins auf bestimmte Produkte oder Kategorien zu beschränken.
  - **Auswirkung der Änderung dieser Einstellung:** Kann verwendet werden, um bestimmte Artikel zu bewerben oder alte Lagerbestände zu räumen.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben ein bestimmtes Werbeziel.
  - **Händlerszenario / Beispiel:** Sie möchten, dass der Geburtstagsgutschein nur für Artikel in Ihrer Kategorie „Neuheiten“ gültig ist.
- **Weitere Gutscheinoptionen:** (z.B. kumulierbar mit anderen Gutscheinen, Geschenkartikel usw.)

  - **Was diese Einstellung bewirkt:** Das Modul stellt wahrscheinlich weitere erweiterte Warenkorbregel-Optionen von PrestaShop zur Verfügung, z.B. ob der Gutschein mit anderen Rabatten kombiniert werden kann, ob er für bestimmte Versanddienstleister gilt oder ob er ein kostenloses Geschenk bietet.
  - **Auswirkung der Änderung dieser Einstellung:** Gibt Ihnen eine detaillierte Kontrolle über das Verhalten und die Einschränkungen des Gutscheins.
  - **Empfohlener Wert:** Konfigurieren Sie dies basierend auf Ihrer spezifischen Werbestrategie. Seien Sie vorsichtig bei der Kumulierbarkeit, um übermäßige Rabatte zu vermeiden.
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass der Geburtstagsgutschein nicht mit anderen laufenden Aktionen kombiniert werden kann. Sie würden die Option „Kumulierbar mit anderen Gutscheinen“ deaktivieren.

#### E-Mail-Vorlageneinstellungen

- **E-Mail-Betreff:** (z.B. `Alles Gute zum Geburtstag von {shop_name}! Hier ist ein Geschenk für Sie!`)

  - **Was diese Einstellung bewirkt:** Definiert die Betreffzeile der Geburtstags-E-Mail.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist das Erste, was Kunden sehen; ein überzeugender Betreff erhöht die Öffnungsraten.
  - **Empfohlener Wert:** Etwas Warmes, Persönliches und klar ein Geschenk Anzeigendes. Verwenden Sie `{shop_name}` und `{customer_firstname}`, falls verfügbar.
  - **Händlerszenario / Beispiel:** Sie möchten eine eingängige Betreffzeile, die Kunden das Gefühl gibt, etwas Besonderes zu sein.
- **E-Mail-Inhalt:** (HTML-Editor)

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die vollständige Anpassung des Inhalts der Geburtstags-E-Mail.
  - **Auswirkung der Änderung dieser Einstellung:** Hier übermitteln Sie Ihre Geburtstagswünsche, erklären den Rabatt und ermutigen zum Einkaufen.
  - **Empfohlener Wert:** Fügen Sie eine herzliche Begrüßung hinzu, geben Sie den Rabattcode und seinen Wert klar an, erklären Sie, wie er verwendet wird, und fügen Sie einen Call-to-Action hinzu. Verwenden Sie Platzhalter wie `{customer_firstname}`, `{voucher_code}`, `{shop_name}`, `{shop_url}`.
  - **Händlerszenario / Beispiel:** Sie möchten eine herzliche Nachricht verfassen, Ihr Markenlogo einfügen und den Rabattcode deutlich anzeigen.

#### Cron-Job-Informationen

- **Cron-Job-URL:** (z.B. `http://ihrshop.com/modules/birthdaypro/controllers/front/cron.php?token=IHR_SICHERHEITS_TOKEN`)
  - **Was diese Einstellung bewirkt:** Dies zeigt die URL an, die Sie als Cron-Job auf Ihrem Server einrichten müssen. Dieser Cron-Job ist unerlässlich, damit das Modul automatisch nach bevorstehenden Geburtstagen sucht und Gutscheine versendet.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist keine Einstellung zum Ändern, sondern eine Anweisung. Wenn der Cron-Job nicht korrekt eingerichtet ist, werden keine Geburtstagsgutscheine automatisch versendet.
  - **Empfohlener Wert:** Richten Sie einen Cron-Job ein, der diese URL einmal alle 24 Stunden (z.B. täglich um Mitternacht) ausführt.
  - **Händlerszenario / Beispiel:** Sie haben alle Einstellungen konfiguriert, aber es werden keine E-Mails gesendet. Das Erste, was Sie überprüfen sollten, ist, ob Ihr Hosting-Anbieter den Cron-Job mit dieser URL korrekt eingerichtet hat.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Tage vor dem Geburtstag des Kunden, an denen der Gutschein gesendet werden soll | `7` | Sendet Gutschein X Tage vor dem Geburtstag, fördert geplante Käufe. |
| Modulkonfiguration | Newsletter-Option aktivieren | `NEIN` | Bestimmt, ob nur Newsletter-Abonnenten Gutscheine erhalten. `NEIN` für größere Reichweite. |
| Modulkonfiguration | Kundengruppen, die eingeschlossen werden sollen | `Kunde` (und andere nach Bedarf) | Beschränkt den Gutscheinversand auf bestimmte Kundensegmente. |
| Modulkonfiguration | Gutscheincode-Präfix | `GEBURTSTAG-` | Fügt generierten Gutscheincodes ein eindeutiges Präfix zur einfachen Identifizierung hinzu. |
| Modulkonfiguration | Rabattart | `Prozentsatz` oder `Betrag` | Definiert die Art des Rabatts (z.B. 15% Rabatt, 10 € Rabatt). |
| Modulkonfiguration | Rabattwert | `10` (für 10%) oder `5.00` (für 5 €) | Der tatsächliche Wert des Rabatts. |
| Modulkonfiguration | Mindestbetrag | (Leer oder spezifischer Wert) | Legt einen Mindestbestellwert fest, damit der Gutschein gültig ist. |
| Modulkonfiguration | Gültigkeitsdauer | `30` Tage | Wie lange der Gutschein ab dem Versanddatum gültig ist, erzeugt Dringlichkeit. |
| Modulkonfiguration | Auf bestimmte Produkte/Kategorien anwenden | (Leer oder spezifische Auswahl) | Beschränkt die Gutscheinverwendung auf bestimmte Produkte oder Kategorien. |
| Modulkonfiguration | Weitere Gutscheinoptionen | (Je nach Strategie) | Detaillierte Kontrolle über das Gutscheinverhalten (z.B. Kumulierbarkeit). |
| Modulkonfiguration | E-Mail-Betreff | `Alles Gute zum Geburtstag von {shop_name}!` | Die Betreffzeile der Geburtstags-E-Mail. |
| Modulkonfiguration | E-Mail-Inhalt | (Benutzerdefiniertes HTML) | Der Hauptteil der Geburtstags-E-Mail, einschließlich Grüße und Gutscheindetails. |
| Modulkonfiguration | Cron-Job-URL | (Angezeigte URL) | Unerlässlich für automatisierte tägliche Überprüfungen und den Gutscheinversand. Muss auf dem Server eingerichtet werden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten keine Geburtstags-E-Mails. Was sollte ich zuerst überprüfen?**
A1:

1.  **Cron-Job:** Der häufigste Grund. Stellen Sie sicher, dass die in der Modulkonfiguration angegebene Cron-Job-URL auf Ihrem Hosting-Server korrekt eingerichtet ist, um täglich ausgeführt zu werden. Ohne sie kann das Modul keine E-Mails automatisch versenden.
2.  **Geburtsdaten der Kunden:** Überprüfen Sie, ob Ihre Kunden tatsächlich ihre Geburtsdaten in ihren PrestaShop-Konten eingegeben haben. Das Modul ist auf diese Daten angewiesen.
3.  **E-Mail-Konfiguration:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (Erweiterte Parameter > E-Mail), um sicherzustellen, dass Ihr Shop E-Mails erfolgreich versenden kann. Testen Sie das Senden einer allgemeinen E-Mail von PrestaShop.
4.  **Spam-Ordner:** Weisen Sie Kunden an, ihre Spam- oder Junk-Ordner zu überprüfen.
5.  **Moduleinstellungen:** Überprüfen Sie nochmals „Tage vor dem Geburtstag des Kunden“, „Newsletter-Option aktivieren“ und „Kundengruppen, die eingeschlossen werden sollen“, um sicherzustellen, dass Kunden berechtigt sind.

**F2: Der Rabattcode funktioniert für meine Kunden nicht.**
A2:

1.  **Gutscheingültigkeit:** Überprüfen Sie die Einstellung „Gültigkeitsdauer“ im Modul. Ist der Gutschein abgelaufen?
2.  **Mindestbetrag:** Erfüllt der Warenkorb des Kunden die für den Gutschein festgelegte Anforderung „Mindestbetrag“?
3.  **Produkt-/Kategoriebeschränkungen:** Wenn Sie Beschränkungen angewendet haben, versucht der Kunde, ein berechtigtes Produkt zu kaufen?
4.  **Kumulierbar mit anderen Gutscheinen:** Wenn Sie dies deaktiviert haben, stellen Sie sicher, dass der Kunde nicht versucht, ihn mit einem anderen Rabatt zu kombinieren.
5.  **Tippfehler:** Bitten Sie den Kunden, die Eingabe des Codes auf Tippfehler zu überprüfen.

**F3: Wie ändere ich das Aussehen der Geburtstags-E-Mail?**
A3: Sie können den E-Mail-Inhalt vollständig mit dem HTML-Editor in der Einstellung „E-Mail-Inhalt“ auf der Konfigurationsseite des Moduls anpassen. Sie können Ihr Logo hinzufügen, Schriftarten, Farben und Layout ändern. Stellen Sie sicher, dass Sie die verfügbaren Platzhalter (wie `{customer_firstname}`, `{voucher_code}`, `{shop_name}`) verwenden, um die Nachricht zu personalisieren.

**F4: Kann ich verschiedene Geburtstagsgutscheine an verschiedene Kundengruppen senden?**
A4: Das Modul Happy Birthday Coupon sendet in seiner Standardkonfiguration eine Art von Gutschein basierend auf den von Ihnen definierten Einstellungen. Um verschiedene Gutscheine an verschiedene Gruppen zu senden (z.B. 10% Rabatt für Stammkunden und 20% Rabatt für VIPs), müssten Sie entweder:
a) Manuell separate Gutscheine für bestimmte Gruppen erstellen und versenden (was die Automatisierung aufhebt).
b) Die nativen PrestaShop-„Warenkorbregeln“ für bestimmte Gruppen verwenden und diese manuell verwalten.
c) Eine erweiterte Anpassung oder eine komplexere Marketing-Automatisierungslösung in Betracht ziehen, wenn dies eine kritische Anforderung ist.

**F5: Das Modul scheint zu laufen, aber ich sehe keine Hinweise auf generierte Gutscheine im Bereich „Warenkorbregeln“ von PrestaShop.**
A5: Das Modul generiert dynamisch eindeutige Warenkorbregeln (Gutscheine), wenn der Geburtstag eines Kunden naht. Dies sind tatsächliche PrestaShop-Warenkorbregeln. Sie sollten sie unter **Katalog > Rabatte > Warenkorbregeln** (oder **Preisregeln > Warenkorbregeln** in älteren Versionen) sehen können. Suchen Sie nach Regeln mit dem von Ihnen definierten Präfix (z.B. `GEBURTSTAG-`). Wenn sie nicht angezeigt werden, überprüfen Sie Ihre Cron-Job-Einrichtung und die Modulkonfiguration erneut.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul Happy Birthday Coupon arbeiten.

### 4.1 Architekturübersicht

Das Modul Happy Birthday Coupon (`birthdaypro`) folgt einer Standard-PrestaShop-Modularchitektur und verwendet `Module` als Basis. Es funktioniert hauptsächlich über einen Cron-Job, der einen Front-Controller auslöst, um berechtigte Kunden zu identifizieren und PrestaShop `CartRule`-Objekte zu generieren. Das Modul erweitert `ObjectModel` nicht für eigene Daten, sondern stützt sich auf vorhandene PrestaShop-Kundendaten und `CartRule`-Funktionalität. Es verwendet eine benutzerdefinierte Gutschein-Engine und ein Autocomplete-Suchwerkzeug, wahrscheinlich für die Kundenauswahl im Back-Office oder zum Testen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind für den externen Zugriff konzipiert, hauptsächlich über Cron-Jobs.

- **`controllers/front/cron.php`**

  - **Klassenname & Elternklasse:** `BirthdayproCronModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist die Kernlogik für die automatisierte Gutscheingenerierung und den Versand. Sie ist dafür ausgelegt, von einem serverseitigen Cron-Job aufgerufen zu werden.
    - Sie ruft die Geburtsdaten der Kunden ab.
    - Bestimmt, welche Kunden basierend auf den Konfigurationen `bp_daysbefore`, `bpro_nletter` und `birthdaypro_groups` berechtigt sind.
    - Für jeden berechtigten Kunden generiert sie eine eindeutige PrestaShop `CartRule` (Gutschein) mit den konfigurierten Parametern.
    - Sendet eine Geburtstags-E-Mail mit dem Gutscheincode an den Kunden.
    - Enthält eine Sicherheits-Token-Prüfung, um unbefugten Zugriff zu verhindern.
- **`controllers/front/index.php`**

  - **Klassenname & Elternklasse:** `BirthdayproIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Platzhalter oder einfacher Einstiegspunkt, möglicherweise zum Testen oder zur Bearbeitung von Anfragen, die nicht mit anderen spezifischen Front-Controllern übereinstimmen. In vielen Modulen ist eine `index.php` in einem Controller-Verzeichnis ein Fallback oder ein grundlegender „Hello World“-Controller. Er hat möglicherweise keine signifikante Geschäftslogik.

#### Back-Office-Admin-Controller

Das Modul scheint keine dedizierten benutzerdefinierten Admin-Controller basierend auf dem bereitgestellten Inventar zu haben. Die gesamte Back-Office-Konfiguration wird innerhalb der `getContent()`-Methode des Hauptmoduls behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/`. Das Modul nutzt wahrscheinlich direkt die nativen PrestaShop-Klassen `Customer`, `CartRule` und `Mail`. Die in den JS/CSS-Pfaden erwähnten „voucherengine“ und „searchTool“ deuten auf interne Hilfsklassen oder -funktionen innerhalb von `birthdaypro.php` oder seinen enthaltenen Bibliotheken hin, anstatt auf eigenständige `classes/`-Dateien.

### 4.4 JavaScript-Assets (`views/js/`)

- **`lib/searchTool/views/js/autocomplete.js`**

  - **Umfang:** Wahrscheinlich Back-Office.
  - **Details:** Dieses Skript bietet eine Autocomplete-Funktionalität, wahrscheinlich zum Suchen von Kunden oder Produkten innerhalb der Modulkonfiguration oder einer verwandten Admin-Oberfläche. Es würde an Eingabefelder gebunden, AJAX-Anfragen an einen Backend-Endpunkt senden (möglicherweise die Hauptmoduldatei oder einen dedizierten Admin-Controller, falls vorhanden) und Vorschläge anzeigen.
- **`lib/voucherengine/script.js`**

  - **Umfang:** Wahrscheinlich Back-Office.
  - **Details:** Dieses Skript ist Teil der „Gutschein-Engine“ des Moduls. Es verarbeitet wahrscheinlich dynamische Formularelemente im Zusammenhang mit der Gutscheinerstellung auf der Konfigurationsseite des Moduls. Dies könnte das Anzeigen/Ausblenden von Feldern basierend auf der Auswahl des Rabatttyps, die Validierung der Eingabe für Gutscheinwerte oder die Interaktion mit anderen Gutschein-bezogenen Einstellungen umfassen.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`lib/searchTool/views/css/autocomplete.css`**

  - **Umfang:** Wahrscheinlich Back-Office.
  - **Details:** Bietet Styling für das Autocomplete-Vorschlags-Dropdown und möglicherweise das Eingabefeld selbst, um die visuelle Integration in das PrestaShop Back Office zu gewährleisten.
- **`lib/voucherengine/ps16.css`**

  - **Umfang:** Wahrscheinlich Back-Office.
  - **Details:** Dieses Stylesheet bietet spezifisches Styling für die Gutscheinkonfigurationselemente, möglicherweise auf die Ästhetik des PrestaShop 1.6 Back-Office zugeschnitten. Es könnte Stile für Formulargruppen, Eingabefelder und Beschriftungen im Zusammenhang mit den Gutscheineinstellungen enthalten.
- **`views/css/css.css`**

  - **Umfang:** Wahrscheinlich Back-Office.
  - **Details:** Ein allgemeines Stylesheet für das Modul, das möglicherweise Stile für die Hauptkonfigurationsseite (`admin.tpl`) oder benutzerdefinierte Elemente enthält, die vom Modul im Back Office eingeführt wurden. Es könnte grundlegendes Layout-, Schaltflächen- oder Warnungs-Styling umfassen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **`lib/searchTool/views/scripts.tpl`**

  - **Umfang:** Back-Office.
  - **Details:** Diese Vorlage enthält wahrscheinlich JavaScript-Code oder Smarty-Variablen, die für die korrekte Funktion des `autocomplete.js`-Skripts erforderlich sind, wie z.B. AJAX-URLs, Sprachstrings oder Initialdaten. Sie würde in die Haupt-Admin-Konfigurationsvorlage aufgenommen werden.
- **`views/templates/admin.tpl`**

  - **Umfang:** Back-Office.
  - **Details:** Dies ist die primäre Vorlage für die Konfigurationsseite des Moduls, die von der `getContent()`-Methode in `birthdaypro.php` gerendert wird. Sie enthält die HTML-Struktur für alle in Abschnitt 4.1 beschriebenen Einstellungen, einschließlich Formularfeldern, Schaltflächen und möglicherweise Includes für andere Vorlagen wie `scripts.tpl`.
- **`views/templates/script.tpl`**

  - **Umfang:** Back-Office.
  - **Details:** Ähnlich wie `scripts.tpl` in der `searchTool`-Bibliothek enthält diese Vorlage wahrscheinlich modulspezifisches JavaScript oder Smarty-Variablen, die in die Back-Office-Konfigurationsseite injiziert werden. Sie könnte dynamisches Verhalten oder die Datenübergabe für die Gutschein-Engine verwalten.
- **`views/templates/test.tpl`**

  - **Umfang:** Back-Office oder interne Tests.
  - **Details:** Der Zweck dieser Vorlage ist allein aus dem Namen nicht ganz klar. Es könnte eine Vorlage sein, die während der Entwicklung für interne Tests verwendet wird, eine Debug-Ausgabevorlage oder ein einfacher Platzhalter. Es ist unwahrscheinlich, dass sie Teil der standardmäßigen Händlerkonfiguration ist.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt basierend auf dem bereitgestellten Inventar keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen (z.B. `bp_daysbefore`, `bpro_nletter`, `birthdaypro_groups`) in der PrestaShop-Tabelle `ps_configuration`.
  - Es interagiert mit vorhandenen PrestaShop-Tabellen: `ps_customer` (für Geburtsdaten), `ps_cart_rule` (zum Erstellen von Gutscheinen), `ps_cart_rule_lang`, `ps_cart_rule_shop`, `ps_cart_rule_product_rule_group`, etc.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt / Kontext | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird typischerweise zum Hinzufügen von CSS, JS oder Meta-Tags verwendet. Die Modulbeschreibung erwähnt es, aber seine Hauptfunktion ist Cron-basiert, daher könnte dieser Hook für minimale Front-End-Einrichtung verwendet werden oder nicht aktiv für die Kernfunktionalität. |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Zeigt Inhalte in der rechten Seitenleiste an. Unwahrscheinlich, dass dieses Modul dies aufgrund seines Hintergrundbetriebs verwendet. |
| `displayLeftColumn` | In der linken Spalte der Front-Office-Seiten. | Zeigt Inhalte in der linken Seitenleiste an. Unwahrscheinlich, dass dieses Modul dies aufgrund seines Hintergrundbetriebs verwendet. |
| `displayFooter` | Im Footer-Bereich jeder Front-Office-Seite. | Zeigt Inhalte im Footer an. Unwahrscheinlich, dass dieses Modul dies aufgrund seines Hintergrundbetriebs verwendet. |
| `displayProductButtons` / `displayProductExtraContent` (oder ähnliche Produkthooks) | Auf der Produktseite. | Unwahrscheinlich, dass dieses Modul dies verwendet. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Könnte potenziell verwendet werden, um die Gutscheinnutzung oder das Kundenverhalten nach Anwendung eines Geburtstagsgutscheins zu verfolgen, obwohl dies nicht explizit als Kernfunktion aufgeführt ist. |
| `actionCustomerAccountAdd` / `actionCustomerAccountUpdate` | Wenn ein Kundenkonto erstellt oder aktualisiert wird. | Könnte verwendet werden, um die Eingabe des Geburtsdatums zu überprüfen oder die Erstkonfiguration für neue Kunden auszulösen, obwohl der Cron-Job der primäre Auslöser ist. |
| (Implizit) Cron-Job-Ausführung | Täglich, über externen Server-Cron. | **KRITISCH:** Dies ist der primäre „Hook“ für die Kernfunktionalität des Moduls, der `controllers/front/cron.php` auslöst, um Geburtstage zu verarbeiten und E-Mails zu senden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul Happy Birthday Coupon besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul optimal funktioniert und Ihnen hilft, Ihre E-Commerce-Ziele zu erreichen.
