---
title: "Gutschein für Produktkommentar – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gutschein für Produktkommentar“ von MyPresta.eu."
sidebar:
  label: "Gutschein für Produktkommentar – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Voucher for product comment auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-product-comment.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/voucher-for-product-comment/)
>
> ---


# Gutschein für Produktkommentar

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die korrekte Funktion von PrestaShop erforderlich. Für dieses Modul sind keine spezifischen zusätzlichen Erweiterungen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbereich für das Modul „Gutschein für Produktkommentar“. Hier finden Sie alle Einstellungen zu Kommentarrerinnerungen und Gutscheingenerierung.

#### **Einstellungen für Kommentarrerinnerungen**

- **Um Erlaubnis zum Senden von Erinnerungen bitten**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, erscheint ein Kontrollkästchen in Ihren Kundenregistrierungs- und Identitätsaktualisierungsformularen (Mein Konto > Informationen), das Kunden fragt, ob sie damit einverstanden sind, Kommentarrerinnerungen zu erhalten. Dies ist wichtig für die DSGVO-Konformität und die Achtung der Kundendaten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden müssen sich explizit anmelden, um Erinnerungen zu erhalten. Nur Kunden, die dieses Kontrollkästchen aktivieren, erhalten Erinnerungs-E-Mails.
    - *Wenn deaktiviert:* Alle Kunden, die andere Kriterien erfüllen (z.B. gekaufte Produkte, noch nicht kommentiert), erhalten Erinnerungen, ohne eine explizite Anmeldung.
  - **Empfohlener Wert:** JA (Sehr empfohlen für die DSGVO-Konformität und bessere Kundenbeziehungen).
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihre Marketingpraktiken den Datenschutzbestimmungen entsprechen. Die Aktivierung dieser Option gibt Kunden die Kontrolle über ihre Kommunikationspräferenzen.
- **Kommentarrerinnerung senden**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für die Kommentarrerinnerungsfunktion. Wenn deaktiviert, werden keine Kommentarrerinnerungs-E-Mails gesendet, unabhängig von anderen Einstellungen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul sendet aktiv Erinnerungs-E-Mails basierend auf Ihren anderen Einstellungen.
    - *Wenn deaktiviert:* Es werden keine Erinnerungs-E-Mails gesendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie haben beschlossen, aktiv mehr Bewertungen zu sammeln und möchten beginnen, Erinnerungen zu senden.
- **Nach Kommentaren erinnern nach:**

  - **Was diese Einstellung bewirkt:** Definiert die Anzahl der Tage, nachdem eine Bestellung einen bestimmten Status erreicht hat (unten definiert), an denen die erste Kommentarrerinnerungs-E-Mail gesendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Änderung der Zahl:* Bestimmt die Verzögerung. Eine kürzere Verzögerung bedeutet, dass Kunden früher Erinnerungen erhalten; eine längere Verzögerung gibt ihnen mehr Zeit, bevor sie aufgefordert werden.
  - **Empfohlener Wert:** 7 Tage (Gibt Kunden genügend Zeit, das Produkt zu erhalten und zu verwenden).
  - **Händlerszenario / Beispiel:** Sie möchten Kunden eine Woche Zeit geben, ihr Produkt zu erhalten und sich eine Meinung zu bilden, bevor Sie um eine Bewertung bitten.
- **Erinnerung wiederholen**

  - **Was diese Einstellung bewirkt:** Wenn ein Kunde nach der ersten Erinnerung immer noch keinen Kommentar hinterlassen hat, bestimmt diese Einstellung, ob und wann eine zweite Erinnerung gesendet werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Einstellung einer Zahl (z.B. 14):* Eine zweite Erinnerung wird 14 Tage nach der *ersten* Erinnerung gesendet, wenn kein Kommentar hinterlassen wurde.
    - *Einstellung auf 0 oder leer lassen:* Es wird keine zweite Erinnerung gesendet.
  - **Empfohlener Wert:** 14 (Bietet eine sanfte Nachverfolgung, ohne zu aggressiv zu sein).
  - **Händlerszenario / Beispiel:** Einige Kunden könnten die erste E-Mail verpassen oder einfach vergessen. Eine zweite Erinnerung nach zwei Wochen kann ihre Aufmerksamkeit erneut wecken.
- **E-Mail-Titel**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Betreffzeile der Kommentarrerinnerungs-E-Mails anzupassen. Dies ist entscheidend für die E-Mail-Öffnungsraten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Änderung des Textes:* Ändert direkt die Betreffzeile, die Kunden in ihrem Posteingang sehen.
  - **Empfohlener Wert:** „Wir würden uns über Ihre Meinung zu Ihrem letzten Einkauf freuen!“ oder „Teilen Sie Ihre Erfahrungen und helfen Sie anderen Käufern!“
  - **Händlerszenario / Beispiel:** Sie möchten die E-Mail-Betreffzeile ansprechend und klar gestalten, um Kunden zum Öffnen zu ermutigen.
- **Bestellstatus auswählen**

  - **Was diese Einstellung bewirkt:** Bestimmt, welche Bestellstatus den Kommentarrerinnerungsprozess auslösen. Erinnerungen werden nur für Produkte aus Bestellungen gesendet, die einen der ausgewählten Status erreicht haben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auswahl von Status (z.B. „Geliefert“):* Erinnerungen werden nur für Bestellungen gesendet, die als geliefert markiert sind.
    - *Nichtauswahl eines relevanten Status:* Erinnerungen werden möglicherweise nicht zum geeigneten Zeitpunkt gesendet (z.B. wenn Sie nur „Zahlung akzeptiert“ auswählen, die Produkte aber noch nicht versandt wurden).
  - **Empfohlener Wert:** „Geliefert“ (Dies stellt sicher, dass Kunden ihre Produkte erhalten haben, bevor sie um eine Bewertung gebeten werden).
  - **Händlerszenario / Beispiel:** Sie möchten nur dann um Bewertungen bitten, wenn der Kunde seine Bestellung tatsächlich erhalten hat, daher wählen Sie „Geliefert“ und „Versandt“.
- **Kundengruppe (für Erinnerungen)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bestimmte Kundengruppen für Kommentarrerinnerungen anzusprechen. Nur Kunden, die zu den ausgewählten Gruppen gehören, erhalten Erinnerungen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auswahl von Gruppen (z.B. „Kunden“):* Nur Kunden in der Gruppe „Kunden“ erhalten Erinnerungen.
    - *Keine Gruppe ausgewählt:* Erinnerungen werden an alle Kunden gesendet (es sei denn, es gelten andere Filter).
  - **Empfohlener Wert:** „Kunden“ (Typischerweise möchten Sie alle Ihre Stammkunden erinnern).
  - **Händlerszenario / Beispiel:** Sie haben eine spezielle „VIP“-Kundengruppe und möchten ihnen personalisierte Erinnerungen senden, oder Sie möchten Großhandelskunden von Erinnerungen ausschließen.
- **Erinnerungen zu Kommentaren für Produkte aus Bestellungen senden:**

  - **Was diese Einstellung bewirkt:** Dies ist ein Datumsfilter. Erinnerungen werden nur für Produkte gesendet, die in Bestellungen gekauft wurden, die *nach* diesem angegebenen Datum aufgegeben wurden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Einstellung eines Datums:* Verhindert das Senden von Erinnerungen für sehr alte Bestellungen und konzentriert sich auf aktuelle Käufe.
    - *Leer lassen:* Erinnerungen könnten potenziell für alle vergangenen Bestellungen gesendet werden, was möglicherweise nicht wünschenswert ist.
  - **Empfohlener Wert:** Auf ein aktuelles Datum oder das Installationsdatum des Moduls setzen, um alte Kunden nicht zu spammen.
  - **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten keine Erinnerungen für Bestellungen von vor einem Jahr senden; Sie interessieren sich nur für Bestellungen der letzten 3 Monate.
- **Bildgröße für Produktbilder**

  - **Was diese Einstellung bewirkt:** Bestimmt die Größe der Produktbilder, die in den Erinnerungs-E-Mails enthalten sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auswahl einer Größe (z.B. „home\_default“):* Die Produktbilder in der E-Mail werden in dieser spezifischen Größe gerendert, was das E-Mail-Layout und die Ladezeit beeinflusst.
  - **Empfohlener Wert:** „home\_default“ oder „small\_default“ (Ein mittelgroßes Bild, das gut aussieht, ohne die E-Mail zu schwer zu machen).
  - **Händlerszenario / Beispiel:** Sie möchten, dass die Produktbilder in Ihren Erinnerungs-E-Mails klar, aber nicht übermäßig groß sind, daher wählen Sie eine geeignete, in Ihrem Theme definierte Bildgröße.

#### **Einstellungen zur Gutscheingenerierung**

- **Gutscheincode für Kommentar senden**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für die Gutscheingenerierungsfunktion. Wenn deaktiviert, werden keine Gutscheine generiert oder gesendet, selbst wenn Kommentare hinterlassen werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul generiert und sendet einen einzigartigen Gutscheincode an Kunden, die einen Produktkommentar hinterlassen.
    - *Wenn deaktiviert:* Es werden keine Gutscheine gesendet.
  - **Empfohlener Wert:** JA (Dies ist eine Kernfunktion zur Anreizung von Kommentaren).
  - **Händlerszenario / Beispiel:** Sie möchten Kunden für ihre Mühe, eine Bewertung zu hinterlassen, belohnen und sie zu einem erneuten Einkauf ermutigen.
- **Gutschein nur für Kunden senden, die das Produkt gekauft haben**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, wird ein Gutschein *nur* gesendet, wenn der Kunde, der den Kommentar hinterlassen hat, das Produkt auch gekauft hat. Dies verhindert, dass Personen, die nicht in Ihrem Shop gekauft haben, Gutscheine erhalten, nur indem sie Kommentare hinterlassen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gutscheine sind auf verifizierte Käufer beschränkt.
    - *Wenn deaktiviert:* Jeder, der einen Kommentar hinterlässt (z.B. ein Gast oder jemand, der das Produkt nicht gekauft hat), könnte einen Gutschein erhalten.
  - **Empfohlener Wert:** JA (Sehr empfohlen, um sicherzustellen, dass Gutscheine an tatsächliche Kunden vergeben werden und Missbrauch verhindert wird).
  - **Händlerszenario / Beispiel:** Sie möchten treue Kunden belohnen, die bereits einen Kauf getätigt haben, nicht nur jeden, der einen Kommentar hinterlässt.
- **Wann Gutschein generieren?**

  - **Was diese Einstellung bewirkt:** Bestimmt, wann der Gutschein generiert und an den Kunden gesendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Option 1 (z.B. „Nachdem der Kommentar hinzugefügt wurde“):* Der Gutschein wird sofort gesendet, nachdem der Kunde seinen Kommentar übermittelt hat.
    - *Option 2 (z.B. „Nachdem der Kommentar genehmigt wurde“):* Der Gutschein wird erst gesendet, nachdem ein Administrator den Kommentar im Back Office manuell genehmigt hat.
  - **Empfohlener Wert:** „Nachdem der Kommentar genehmigt wurde“ (Verhindert die Vergabe von Gutscheinen für Spam oder unangemessene Kommentare).
  - **Händlerszenario / Beispiel:** Sie moderieren alle Produktkommentare, um die Qualität zu erhalten. Sie möchten sicherstellen, dass nur genehmigte, wertvolle Kommentare einen Gutschein erhalten.
- **Gutscheine für Kommentare generieren:**

  - **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, die Eigenschaften des zu generierenden Gutscheins zu definieren. Dies umfasst den Rabatttyp (Prozentsatz, Betrag), den Wert, den Mindestkauf, die Gültigkeit und mehr.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Jedes Feld hier (z.B. „Rabatttyp“, „Wert“, „Mindestbetrag“):* Konfiguriert direkt die Regeln und Vorteile des generierten Rabattgutscheins.
    - *Leere oder falsch konfigurierte Felder:* Könnten zu ungültigen Gutscheinen oder Gutscheinen führen, die Ihre Marketingziele nicht erfüllen.
  - **Empfohlener Wert:**
    - **Rabatttyp:** Prozentsatz (z.B. 10 %) oder Betrag (z.B. 5 €).
    - **Wert:** Ein angemessener Anreiz (z.B. 5, 10, 15).
    - **Mindestbetrag:** Legen Sie einen Mindestkauf fest, um die Rentabilität zu gewährleisten (z.B. 50 €).
    - **Gültigkeit:** 30 Tage (Fördert eine schnelle Nutzung).
    - **Beschreibung:** „Vielen Dank für Ihre Produktbewertung!“
  - **Händlerszenario / Beispiel:** Sie möchten einen Rabatt von 10 % auf die nächste Bestellung anbieten, gültig für 30 Tage, mit einem Mindestbestellwert von 50 €, als Dankeschön für die Bewertung.
- **Kundengruppe (für Gutscheine)**

  - **Was diese Einstellung bewirkt:** Ähnlich wie bei der Erinnerungseinstellung können Sie hier die Gutscheingenerierung auf bestimmte Kundengruppen beschränken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auswahl von Gruppen:* Nur Kunden in den ausgewählten Gruppen erhalten Gutscheine.
    - *Keine Gruppe ausgewählt:* Gutscheine werden an alle Kunden gesendet (es sei denn, es gelten andere Filter).
  - **Empfohlener Wert:** „Kunden“
  - **Händlerszenario / Beispiel:** Sie möchten Gutscheine nur an Ihre Standard-„Kunden“-Gruppe vergeben, nicht an „Gäste“ oder „Großhändler“.
- **Anzahl der E-Mails begrenzen**

  - **Was diese Einstellung bewirkt:** Dies ist eine Sicherheitsfunktion, um zu verhindern, dass Ihr Server in kurzer Zeit zu viele E-Mails sendet, was dazu führen könnte, dass Ihre E-Mails als Spam markiert werden oder Ihr Hosting-Anbieter Beschränkungen auferlegt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul berücksichtigt die Einstellung „E-Mail-Limit“.
    - *Wenn deaktiviert:* Das Modul selbst wendet kein E-Mail-Sendelimit an.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie haben eine große Anzahl ausstehender Erinnerungen und möchten diese schrittweise versenden, um Ihren Mailserver nicht zu überlasten.
- **E-Mail-Limit:**

  - **Was diese Einstellung bewirkt:** Gibt die maximale Anzahl von E-Mails (Erinnerungen oder Gutscheine) an, die das Modul in einem einzigen Ausführungszyklus (z.B. wenn der Cron-Job läuft) senden kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Einstellung einer Zahl (z.B. 50):* Das Modul sendet maximal 50 E-Mails pro Cron-Job-Lauf. Wenn es mehr gibt, werden sie in nachfolgenden Läufen gesendet.
  - **Empfohlener Wert:** 50-100 (Anpassung basierend auf den E-Mail-Sendelimits Ihres Hosting-Anbieters und der Serverkapazität).
  - **Händlerszenario / Beispiel:** Ihr Hosting-Anbieter erlaubt 100 E-Mails pro Stunde. Sie setzen dieses Limit auf 50, um die Richtlinien einzuhalten.

#### **Produktfilter (für Erinnerungen & Gutscheine)**

- **Filter aktivieren**

  - **Was diese Einstellung bewirkt:** Aktiviert zusätzliche Filteroptionen für Erinnerungen und Gutscheine, sodass Sie festlegen können, welche Produkte oder Hersteller berechtigt sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Filter „Hersteller“ wird aktiv.
    - *Wenn deaktiviert:* Es werden keine produktspezifischen Filter angewendet.
  - **Empfohlener Wert:** NEIN (Es sei denn, Sie haben einen spezifischen Filterbedarf).
  - **Händlerszenario / Beispiel:** Sie möchten Erinnerungen oder Gutscheine nur für Produkte bestimmter Hersteller senden.
- **Hersteller**

  - **Was diese Einstellung bewirkt:** Wenn „Filter aktivieren“ aktiv ist, können Sie hier bestimmte Hersteller auswählen. Erinnerungen und Gutscheine werden nur für Produkte dieser ausgewählten Hersteller gesendet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auswahl von Herstellern:* Schränkt den Umfang der Moduloperation auf Produkte dieser Marken ein.
  - **Empfohlener Wert:** Alle nicht ausgewählt lassen (es sei denn, Sie haben einen spezifischen Bedarf).
  - **Händlerszenario / Beispiel:** Sie führen eine Aktion mit einer bestimmten Marke durch und möchten nur Kommentare für deren Produkte incentivieren.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Um Erlaubnis zum Senden von Erinnerungen bitten | JA | Gewährleistet DSGVO-Konformität; Kunden melden sich für Erinnerungen an. |
| Modulkonfiguration | Kommentarrerinnerung senden | JA | Hauptschalter für das Senden von Erinnerungs-E-Mails. |
| Modulkonfiguration | Nach Kommentaren erinnern nach: | 7 Tage | Verzögerung (in Tagen) nach Statusänderung der Bestellung für die erste Erinnerung. |
| Modulkonfiguration | Erinnerung wiederholen | 14 Tage | Verzögerung (in Tagen) nach der ersten Erinnerung für eine zweite (0 für keine). |
| Modulkonfiguration | E-Mail-Titel (Erinnerung) | Anpassbar | Betreffzeile für Erinnerungs-E-Mails. |
| Modulkonfiguration | Bestellstatus auswählen | Geliefert | Bestellstatus, die den Erinnerungsprozess auslösen. |
| Modulkonfiguration | Kundengruppe (Erinnerung) | Kunden | Beschränkt Erinnerungen auf ausgewählte Kundengruppen. |
| Modulkonfiguration | Erinnerungen zu Kommentaren für Produkte aus Bestellungen senden: | Aktuelles Datum / Leer | Datumsfilter für berechtigte Bestellungen. |
| Modulkonfiguration | Bildgröße für Produktbilder | home\_default | Größe der Produktbilder in Erinnerungs-E-Mails. |
| Modulkonfiguration | Gutscheincode für Kommentar senden | JA | Hauptschalter für das Generieren und Senden von Gutscheinen. |
| Modulkonfiguration | Gutschein nur für Kunden senden, die das Produkt gekauft haben | JA | Beschränkt Gutscheine auf tatsächliche Käufer. |
| Modulkonfiguration | Wann Gutschein generieren? | Nachdem der Kommentar genehmigt wurde | Zeitpunkt der Gutscheingenerierung (nach Übermittlung oder Genehmigung). |
| Modulkonfiguration | Gutscheine für Kommentare generieren: (Gutscheineigenschaften) | Anpassbar | Definiert den Rabatttyp, Wert, Gültigkeit usw. des Gutscheins. |
| Modulkonfiguration | Kundengruppe (Gutschein) | Kunden | Beschränkt Gutscheine auf ausgewählte Kundengruppen. |
| Modulkonfiguration | Anzahl der E-Mails begrenzen | JA | Aktiviert die Begrenzung der E-Mail-Versandrate. |
| Modulkonfiguration | E-Mail-Limit: | 50-100 | Max. E-Mails pro Cron-Job-Lauf. |
| Modulkonfiguration | Filter aktivieren | NEIN | Aktiviert Produkt-/Herstellerfilterung. |
| Modulkonfiguration | Hersteller | Alle nicht ausgewählt | Filtert berechtigte Produkte nach Hersteller. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul fügt Ihrem PrestaShop Back Office mehrere dedizierte Bildschirme zur Verwaltung von Erinnerungen, Gutscheinen und abgemeldeten Kunden hinzu. Sie finden diese unter dem Menüpunkt **„Gutschein für Kommentar“**, der sich normalerweise unter **„Katalog“** oder **„Marketing“** befindet.

#### **4.2.1 AdminComRemCommentsController: Verwaltung der Kommentarrerinnerungen**

- **Bildschirmname & Menüpfad:** **Gutschein für Kommentar > Kommentarrerinnerungen**
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Liste aller ausstehenden, gesendeten oder fehlgeschlagenen Kommentarrerinnerungen an. Sie sehen Details wie den Namen des Kunden, die E-Mail-Adresse, das Produkt, zu dem er einen Kommentar abgeben muss, die Bestell-ID, das Datum, an dem die Erinnerung gesendet wurde (oder geplant ist), und ihren aktuellen Status.
  - **Raster- / Verwaltungsansicht:** Sie können die Liste der Erinnerungen anzeigen, filtern und durchsuchen. Dies ermöglicht Ihnen, die Aktivität des Moduls zu überwachen.
  - **Massenaktionen:** Je nach Modulversion können Sie möglicherweise Erinnerungen manuell senden oder Einträge löschen.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung. Das Löschen eines Eintrags hier würde verhindern, dass eine geplante Erinnerung gesendet wird. Das manuelle Senden einer Erinnerung würde eine E-Mail an den Kunden auslösen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Bildschirm regelmäßig, um sicherzustellen, dass Erinnerungen wie erwartet gesendet werden. Wenn Sie feststellen, dass ein Kunde keine Erinnerung erhalten hat, können Sie dies untersuchen oder manuell auslösen.

#### **4.2.2 AdminComUnsubController: Abgemeldete Kunden**

- **Bildschirmname & Menüpfad:** **Gutschein für Kommentar > Abgemeldete Kunden**
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm listet Kunden auf, die sich vom Erhalt von Kommentarrerinnerungen abgemeldet haben (wenn die Einstellung „Um Erlaubnis bitten“ aktiviert ist). Sie sehen deren Kunden-ID und E-Mail-Adresse.
  - **Raster- / Verwaltungsansicht:** Ermöglicht Ihnen, die Liste der abgemeldeten Kunden anzuzeigen und zu verwalten.
- **Auswirkung von Änderungen:** Das Entfernen eines Kunden aus dieser Liste würde ihn wieder für den Empfang von Erinnerungen berechtigen (vorausgesetzt, er erfüllt andere Kriterien und hat sich nicht explizit an anderer Stelle abgemeldet).
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Dies ist ein Bildschirm zur Einhaltung von Vorschriften. Sie müssen normalerweise nicht täglich damit interagieren, aber es ist wichtig zu wissen, wo Sie die Opt-out-Präferenzen der Kunden finden und verwalten können.

#### **4.2.3 AdminComVouCommentsController: Gutschein für Kommentare verwalten**

- **Bildschirmname & Menüpfad:** **Gutschein für Kommentar > Gutscheine für Kommentare**
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm bietet eine umfassende Liste aller vom Modul generierten Gutscheine als Reaktion auf Produktkommentare. Sie sehen Details wie den Kunden, der den Gutschein erhalten hat, das Produkt, zu dem er einen Kommentar abgegeben hat, den generierten Gutscheincode, seinen Wert, seine Gültigkeit und ob er verwendet wurde.
  - **Raster- / Verwaltungsansicht:** Sie können Gutscheine filtern, suchen und sortieren. Dies ist nützlich, um die Wirksamkeit Ihres Anreizprogramms zu verfolgen.
  - **Zugehörige Konfigurationsschlüssel:** Die Anzeige- und Filteroptionen hier könnten durch `cvo_filters` und `cvo_fil_manuf` aus der Hauptkonfiguration beeinflusst werden.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung. Sie können sehen, welche Gutscheine ausgestellt wurden und ob sie eingelöst wurden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Bildschirm, um zu verfolgen, wie viele Gutscheine ausgestellt werden und deren Einlösungsraten. Diese Daten können Ihnen helfen, den Erfolg Ihres Bewertungsanreizprogramms zu bewerten.

#### **4.2.4 index.php (Admin Controller Platzhalter)**

- **Bildschirmname & Menüpfad:** Diese `index.php`-Datei dient typischerweise als Platzhalter oder Weiterleitung innerhalb des `controllers/admin`-Verzeichnisses des Moduls, um sicherzustellen, dass der direkte Zugriff auf das Verzeichnis keine sensiblen Informationen preisgibt. Sie stellt keinen benutzerorientierten Bildschirm im PrestaShop Back Office dar.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten keine Erinnerungs-E-Mails. Was sollte ich überprüfen?**
A1:

-   **Modul aktiviert:** Stellen Sie sicher, dass „Kommentarrerinnerung senden“ in der Modulkonfiguration auf JA eingestellt ist.
-   **Bestellstatus:** Überprüfen Sie, ob die betreffenden Bestellungen einen der von Ihnen ausgewählten „Bestellstatus auswählen“ erreicht haben (z.B. „Geliefert“).
-   **Erinnerungsverzögerung:** Überprüfen Sie „Nach Kommentaren erinnern nach:“, um sicherzustellen, dass genügend Tage seit der Statusänderung der Bestellung vergangen sind.
-   **Cron-Job:** Das Modul verwendet den Cron-Job von PrestaShop, um E-Mails zu senden. Stellen Sie sicher, dass Ihr Cron-Job korrekt eingerichtet ist und regelmäßig auf Ihrem Server läuft. Anweisungen zum Cron-Job finden Sie normalerweise in Ihrem Hosting-Panel oder im Abschnitt „Erweiterte Parameter > Informationen“ von PrestaShop.
-   **E-Mail-Konfiguration:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (Erweiterte Parameter > E-Mail), um sicherzustellen, dass E-Mails im Allgemeinen korrekt von Ihrem Shop gesendet werden.
-   **Kunden-Opt-in:** Wenn „Um Erlaubnis zum Senden von Erinnerungen bitten“ aktiviert ist, stellen Sie sicher, dass die Kunden tatsächlich zugestimmt haben.
-   **E-Mail-Limits:** Überprüfen Sie die Einstellungen „Anzahl der E-Mails begrenzen“ und „E-Mail-Limit“. Wenn das Limit erreicht ist, werden E-Mails im nächsten Cron-Lauf gesendet.
-   **Spam-Ordner:** Bitten Sie Kunden, ihre Spam- oder Junk-Ordner zu überprüfen.

**F2: Gutscheine werden nach dem Hinterlassen von Kommentaren nicht gesendet.**
A2:

-   **Modul aktiviert:** Stellen Sie sicher, dass „Gutscheincode für Kommentar senden“ auf JA eingestellt ist.
-   **Zeitpunkt der Gutscheingenerierung:** Überprüfen Sie „Wann Gutschein generieren?“. Wenn es auf „Nachdem der Kommentar genehmigt wurde“ eingestellt ist, stellen Sie sicher, dass die Kommentare in Ihrem PrestaShop Back Office (Katalog > Produktkommentare, wenn Sie das Standardmodul oder Ihr Drittanbieter-Bewertungsmodul verwenden) tatsächlich genehmigt wurden.
-   **Nur Käufer:** Wenn „Gutschein nur für Kunden senden, die das Produkt gekauft haben“ aktiviert ist, überprüfen Sie, ob der Kunde, der den Kommentar hinterlassen hat, dieses spezifische Produkt tatsächlich gekauft hat.
-   **Gutscheinkonfiguration:** Überprüfen Sie alle Einstellungen unter „Gutscheine für Kommentare generieren“, um sicherzustellen, dass ein gültiger Gutschein erstellt werden kann (z.B. Rabattwert, Gültigkeit).
-   **E-Mail-Konfiguration & Cron-Job:** Ähnlich wie bei Erinnerungsproblemen stellen Sie sicher, dass Ihre E-Mail-Einstellungen und der Cron-Job funktionieren.

**F3: Das Modul sendet zu viele E-Mails, oder E-Mails werden verzögert.**
A3:

-   **E-Mail-Limit:** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass „Anzahl der E-Mails begrenzen“ aktiviert ist und „E-Mail-Limit“ auf eine angemessene Zahl (z.B. 50-100) eingestellt ist. Dies verhindert eine Überlastung Ihres Servers.
-   **Cron-Job-Frequenz:** Wenn Ihr Cron-Job sehr häufig (z.B. jede Minute) läuft und Sie ein hohes E-Mail-Limit haben, könnte er schnell viele E-Mails senden. Passen Sie die Cron-Job-Frequenz oder das E-Mail-Limit an.
-   **Hosting-Limits:** Kontaktieren Sie Ihren Hosting-Anbieter, um dessen E-Mail-Sendelimits pro Stunde/Tag zu erfahren. Passen Sie das „E-Mail-Limit“ des Moduls entsprechend an.

**F4: Wie übersetze ich die Texte oder E-Mail-Vorlagen des Moduls?**
A4:

-   **Back Office Übersetzung:** Gehen Sie zu **International > Übersetzungen**.
-   **Art der Übersetzung:** Wählen Sie „Übersetzungen installierter Module“.
-   **Wählen Sie Ihr Theme:** Wählen Sie Ihr aktuelles Theme.
-   **Wählen Sie Ihre Sprache:** Wählen Sie die Sprache, in die Sie übersetzen möchten.
-   **Modul:** Suchen Sie „Gutschein für Produktkommentar“ in der Liste.
-   Sie können dann die Textzeichenfolgen für die Modulkonfiguration, Front-Office-Elemente (wie das Opt-in-Kontrollkästchen) und E-Mail-Vorlagen bearbeiten. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Das Front-Office-Kontrollkästchen des Moduls (für Berechtigungen) sieht in meinem Theme nicht richtig aus.**
A5:

-   **Theme-Kompatibilität:** Benutzerdefinierte Themes erfordern manchmal geringfügige CSS-Anpassungen für neue Modulelemente.
-   **Cache leeren:** Versuchen Sie zuerst, Ihren PrestaShop-Cache zu leeren (Erweiterte Parameter > Leistung > Cache leeren).
-   **Support kontaktieren:** Wenn das Problem weiterhin besteht, könnte eine kleine CSS-Anpassung erforderlich sein. Kontaktieren Sie den MyPresta.eu-Support mit Screenshots und Ihrem Theme-Namen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Gutschein für Produktkommentar“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einer Standard-PrestaShop-Modularchitektur und nutzt gegebenenfalls MVC-Muster. Es integriert sich über Hooks in den PrestaShop-Kern für die Front-Office-Anzeige und Back-Office-Aktionen. Es verwendet benutzerdefinierte AdminController zur Verwaltung seiner Datenentitäten (Erinnerungen, Gutscheine, Abmeldungen) und einen FrontController für die Cron-Job-Ausführung. Die Konfiguration wird über `Configuration::get()` und `Configuration::updateValue()` verwaltet. Das Modul scheint keine benutzerdefinierten `ObjectModel`-Klassen zu verwenden, sondern verwaltet seine Daten wahrscheinlich direkt oder über bestehende PrestaShop-Entitäten (wie `CartRule` für Gutscheine).

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `comvou/controllers/front/CronJob.php`
    -   **Klassenname & Elternklasse:** `ComvouCronJobModuleFrontController` erweitert `ModuleFrontController`.
    -   **Verantwortlichkeit:** Dieser Controller ist für die Ausführung über einen Cron-Job konzipiert. Er verarbeitet die Hintergrundaufgaben des Moduls, wie das Überprüfen auf berechtigte Bestellungen, das Senden von Kommentarrerinnerungen und das Generieren/Senden von Gutscheinen basierend auf neuen Kommentaren. Er rendert typischerweise keine visuelle Seite, sondern führt Aktionen aus und beendet sich. Er ist das Herzstück der Modulautomatisierung.

#### Back-Office-Admin-Controller

-   `comvou/controllers/admin/AdminComRemComments.php`

    -   **Tab-Name und verwaltete Entität:** „Kommentarrerinnerungen“ (unter dem Menü „Gutschein für Kommentar“). Verwaltet `cvor`-Entitäten (Comment Voucher Order Reminder), die geplante oder gesendete Erinnerungen darstellen.
    -   **Verantwortlichkeit:** Bietet eine Liste (Rasteransicht) aller Kommentarrerinnerungen. Ermöglicht Administratoren, den Status von Erinnerungen anzuzeigen, sie zu filtern und potenziell Aktionen wie das manuelle Senden einer Erinnerung oder das Löschen eines Eintrags durchzuführen. Erweitert `AdminController` und verwendet `HelperList` zur Anzeige.
-   `comvou/controllers/admin/AdminComUnsub.php`

    -   **Tab-Name und verwaltete Entität:** „Abgemeldete Kunden“ (unter dem Menü „Gutschein für Kommentar“). Verwaltet `cunsub`-Entitäten (Comment Unsubscribe).
    -   **Verantwortlichkeit:** Zeigt eine Liste von Kunden an, die sich von Kommentarrerinnerungen abgemeldet haben. Dieser Controller bietet eine Schnittstelle zum Anzeigen und Verwalten dieser Opt-out-Präferenzen, typischerweise unter Verwendung von `HelperList`.
-   `comvou/controllers/admin/AdminComVouComments.php`

    -   **Tab-Name und verwaltete Entität:** „Gutscheine für Kommentare“ (unter dem Menü „Gutschein für Kommentar“). Verwaltet `cvov`-Entitäten (Comment Voucher Order Voucher), die generierte Gutscheine darstellen.
    -   **Verantwortlichkeit:** Präsentiert eine Liste aller vom Modul generierten Gutscheine, detailliert, welcher Kunde ihn erhalten hat, für welches Produkt, den Gutscheincode, seinen Wert und den Nutzungsstatus. Verwendet `HelperList` zur Anzeige und ermöglicht das Filtern. Die Anzeige kann Logik basierend auf den Konfigurationsschlüsseln `cvo_filters` und `cvo_fil_manuf` enthalten.
-   `comvou/controllers/admin/index.php`

    -   **Tab-Name und verwaltete Entität:** Kein direkter benutzerorientierter Bildschirm.
    -   **Verantwortlichkeit:** Dies ist eine Standard-Sicherheitsmaßnahme in PrestaShop. Sie enthält typischerweise `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;`, um das Auflisten von Verzeichnissen zu verhindern und zum Shop-Root umzuleiten.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul seine Daten möglicherweise direkt innerhalb der Hauptdatei `comvou.php` oder seiner Controller verarbeitet, möglicherweise unter Verwendung bestehender PrestaShop `ObjectModel`s (wie `Order`, `Customer`, `Product`, `CartRule`) und direkter Datenbankabfragen für seine benutzerdefinierte Datenspeicherung (z.B. für Erinnerungen und Gutscheinaufzeichnungen).

### 4.4 JavaScript-Assets (`views/js/`)

-   `comvou/lib/voucherengine/script.js`
    -   **Geltungsbereich:** Wahrscheinlich Back-Office.
    -   **Details:** Dieses Skript ist wahrscheinlich mit den Gutscheingenerierungseinstellungen innerhalb der Modulkonfiguration oder dem AdminComVouComments-Controller verbunden. Es könnte dynamische Formularelemente, Validierung oder AJAX-Interaktionen im Zusammenhang mit Gutscheinerstellungsparametern (z.B. Anzeigen/Ausblenden von Feldern basierend auf dem Rabatttyp, Berechnen von Werten) verarbeiten. Es könnte auch für allgemeine UI-Verbesserungen auf den Admin-Seiten des Moduls verwendet werden.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `comvou/lib/voucherengine/ps16.css`
    -   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    -   **Details:** Dieses Stylesheet bietet spezifisches Styling für die Konfigurationsseite des Moduls und möglicherweise seine benutzerdefinierten Admin-Controller-Ansichten, um sicherzustellen, dass sie mit dem Back-Office-Design von PrestaShop 1.6 konsistent aussehen. Es könnte Regeln für Formularlayouts, Eingabefelder, Schaltflächen und Rasteranzeigen enthalten. Entwickler, die dies überschreiben, würden bestimmte IDs oder Klassen ansprechen, die von den Admin-Templates des Moduls verwendet werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `comvou/views/templates/hook/form.tpl`

    -   **Hook:** Potenziell `displayAdditionalCustomerFormFields` oder `displayCustomerAccountForm`.
    -   **Ausgabe:** Dieses Template rendert wahrscheinlich das Kontrollkästchen „Um Erlaubnis zum Senden von Erinnerungen bitten“ auf den Kundenregistrierungs- oder Identitätsaktualisierungsformularen im Front Office. Es würde den HTML-Code für das Kontrollkästchen und dessen zugehörige Beschriftung enthalten.
-   `comvou/views/templates/hook/header.tpl`

    -   **Hook:** `displayHeader`
    -   **Ausgabe:** Dieses Template wird typischerweise verwendet, um CSS- oder JavaScript-Dateien einzubinden, die im `<head>`-Bereich der Front-Office-Seiten geladen werden müssen. Es könnte Assets bedingt basierend auf Moduleinstellungen oder der aktuellen Seite laden.
-   `comvou/views/templates/hook/identity.tpl`

    -   **Hook:** Potenziell `displayCustomerAccountForm` oder ähnliche Hooks auf der Kundenidentitätsseite.
    -   **Ausgabe:** Ähnlich wie `form.tpl` rendert dieses Template wahrscheinlich das Opt-in-Kontrollkästchen speziell auf der Seite „Mein Konto > Informationen“ des Kunden, sodass bestehende Kunden ihre Erinnerungspräferenzen verwalten können.

#### Admin-Templates (`views/templates/admin/`)

-   `comvou/views/templates/admin/com_rem_comments/helpers/form/form.tpl`

    -   **Zweck:** Dieses Template wird vom `AdminComRemCommentsController` verwendet, um das Formular (falls vorhanden) zum Hinzufügen/Bearbeiten einer Kommentarrerinnerung zu rendern oder um die Anzeige des Listenhelfers anzupassen.
-   `comvou/views/templates/admin/com_vou_comments/helpers/form/form.tpl`

    -   **Zweck:** Dieses Template wird vom `AdminComVouCommentsController` verwendet, um das Formular (falls vorhanden) zum Hinzufügen/Bearbeiten eines Gutscheineintrags zu rendern oder um die Anzeige des Listenhelfers für generierte Gutscheine anzupassen.
-   `comvou/views/templates/admin/orderstates.tpl`

    -   **Zweck:** Dieses Template wird wahrscheinlich innerhalb der Hauptmodulkonfiguration (`getContent()`) verwendet, um die Mehrfachauswahlliste der Bestellstatus zu rendern, sodass der Händler auswählen kann, welche Status Erinnerungen auslösen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Die Modulbeschreibung und Codeanalyse deuten darauf hin, dass das Modul seine benutzerdefinierten Daten (Erinnerungen, Gutscheine, Abmeldungen) in dedizierten Datenbanktabellen speichert. Obwohl keine spezifischen SQL-Dateien aufgeführt sind, implizieren der `AdminComRemCommentsController`, `AdminComUnsubController` und `AdminComVouCommentsController` die Existenz von Tabellen wie:

-   `ps_cvor`: Speichert Datensätze im Zusammenhang mit Kommentarrerinnerungen (z.B. Kunden-ID, Produkt-ID, Bestell-ID, Erinnerungsstatus, letztes Sendedatum).
-   `ps_cunsub`: Speichert Datensätze von Kunden, die sich von Erinnerungen abgemeldet haben (z.B. Kunden-ID, E-Mail).
-   `ps_cvov`: Speichert Datensätze von generierten Gutscheinen (z.B. Kunden-ID, Produkt-ID, generierte `id_cart_rule`, Gutscheincode, Status).
-   Konfigurationswerte werden in `ps_configuration` mit Schlüsseln wie `cvo_r_d`, `cvo_r`, `cvo_repeat`, `cvo_orderstates`, `CR_ALLOWED`, `cvo_v`, `cvo_v_fn`, `cvo_v_t`, `cvo_filters`, `cvo_fil_manuf`, `CVOR_TITLE`, `CVOV_TITLE`, `cvo_customergroups_reminder`, `cvo_customergroups_voucher`, `cvo_r_fn`, `cvo_r_date`, `cvo_vonlycust`, `cvo_v_date`, `cvo_img_type`, `CVO_LIM_M_V`, `CVO_LIM_M` gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wenn ein AdminController initialisiert wird und seine Medien (JS/CSS) gesetzt werden. | Zum Einfügen modulspezifischer JS/CSS in das Back Office. |
| `actionOrderStatusUpdate` | Nachdem der Status einer Bestellung aktualisiert wurde. | Um zu erkennen, wann eine Bestellung einen „gelieferten“ oder relevanten Status erreicht, wodurch der Erinnerungsprozess ausgelöst wird. |
| `actionCustomerAccountAdd` | Nachdem ein neues Kundenkonto erstellt wurde. | Zum Überprüfen der anfänglichen Opt-in-Präferenzen für neue Kunden. |
| `displayHeader` | Im `<head>`-Bereich der Front-Office-Seiten. | Zum Einbinden von Front-Office-CSS/JS oder Meta-Tags. |
| `displayCustomerAccountForm` | Auf der Seite „Mein Konto > Informationen“ des Kunden. | Zum Anzeigen des Opt-in-Kontrollkästchens für bestehende Kunden. |
| `displayAdditionalCustomerFormFields` | Auf dem Kundenregistrierungsformular. | Zum Anzeigen des Opt-in-Kontrollkästchens für neue Kundenregistrierungen. |
| `validateCustomerFormFields` | Wenn ein Kundenformular (Registrierung/Identität) übermittelt wird. | Zum Verarbeiten der Opt-in-Kontrollkästchenauswahl und Speichern der Kundenpräferenz. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen technischen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Stellen Sie sicher, dass Sie die neueste kompatible Version des Moduls für Ihren PrestaShop-Shop verwenden, um von allen Verbesserungen und Sicherheitspatches zu profitieren.
