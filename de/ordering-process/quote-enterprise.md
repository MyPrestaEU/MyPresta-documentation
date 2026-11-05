---
title: "Quote Enterprise - Händlerhandbuch"
sidebar:
  label: "Quote Enterprise - Händlerhandbuch"
description: "So konfigurieren Sie Quote Enterprise, führen den gesamten Prozess von Angebot bis Bestellung durch und beheben Probleme."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Quote Enterprise auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/quote-enterprise/)
>
> ---


## 1. Requirements

Das Modul läuft auf PrestaShop 1.7, 8 und 9 sowie auf PHP 7.1 bis 8.5.

Der Server benötigt cURL und JSON. Es wird kein weiteres Modul benötigt.

Google-reCAPTCHA-Schlüssel erstellen Sie nur selbst, wenn Sie reCAPTCHA einschalten. Slack- oder Teams-Webhooks sind optional und nur für Mitarbeiter-Digests. Erinnerungs-E-Mails und Digests benötigen einen Server-Cronjob auf der Modul-Cron-URL.

## 2. Installation

1. Laden Sie das Modul unter **Modules**, **Module Manager** hoch und aktivieren Sie es.
2. Nach der Installation hat **Orders** zwei Einträge: **Quotes** und **Audit log**.
3. Das Modul leert den Cache während der Installation nicht.
4. Die Installation erstellt die Angebotstabellen und ein verstecktes virtuelles Produkt für individuelle Servicezeilen. Außerdem schreibt sie die unten beschriebenen Standardeinstellungen.

Die Deinstallation entfernt die Menüeinträge, die Modultabellen und die Konfigurationsschlüssel. Das versteckte Gebührenprodukt im Katalog wird durch die Deinstallation nicht gelöscht.

## 3. Configuration and back-office work

Öffnen Sie **Modules**, **Module Manager**, **Quote Enterprise**, **Configure**. Das Modul öffnet sich auf **Dashboard**. Die obere Leiste enthält: **Dashboard**, **Quotes**, **Audit log**, **Settings**, **PDF**, **Emails**, **API**, **Notifications**, **Updates**.

Die Screenshots in diesem Handbuch stammen aus einem englischen Backoffice.

Die tägliche Angebotsarbeit finden Sie auch unter **Orders**, **Quotes** (vollständige Liste und Editor) sowie **Orders**, **Audit log**.

### 3.1 Full quote process

Nutzen Sie diesen Ablauf als Übersicht. Die Abschnitte darunter erklären jeden Bildschirm.

1. Ein Kunde fordert ein Angebot von einer Produktseite, einer Produktliste, dem Warenkorb oder einer Mehrprodukt-Angebotsliste an. Gäste können Schaltflächen sehen, wenn das erlaubt ist, aber zum Speichern der Anfrage ist immer ein Kundenkonto nötig.
2. Die Anfrage wird zu einem Angebot in **Pending review** (Kundenanfrage), oder Mitarbeiter erstellen einen **Draft** im Backoffice.
3. Mitarbeiter öffnen das Angebot unter **Orders**, **Quotes**, setzen Preise, Rabatte, Versand und Nachrichten und wählen dann **Save** oder **Save & send**.
4. **Save & send** sendet dem Kunden eine E-Mail und setzt das Angebot auf **Sent** (oder behält den Verhandlungsfluss beim erneuten Senden).
5. Der Kunde öffnet **My quotes**, sieht das Angebot, kann das PDF herunterladen, annehmen, ablehnen oder Änderungen anfordern (**Negotiation**).
6. Nach **Accepted** kann der Kunde zur Kasse gehen. Der Checkout baut einen Warenkorb aus dem Angebot und kann zu einer Bestellung werden (**Converted**). Das Angebot wird dann gesperrt.
7. Nach **valid until** werden gesendete oder in Verhandlung befindliche Angebote zu **Expired**, wenn sie geöffnet werden oder wenn der Cron läuft. Erinnerungs-E-Mails benötigen Cron.

Status, die Sie sehen: **Draft**, **Pending review**, **Sent**, **Negotiation**, **Accepted**, **Converted**, **Expired**, **Rejected**, **Cancelled**.

Nur **Sent** und **Negotiation** können vom Kunden angenommen werden. Ändern Sie den Status bei Bedarf manuell im Editor.

### 3.2 Dashboard

Das Dashboard zeigt die Angebotspipeline. Öffnen Sie **Analytics parameters**, um den KPI-Zeitraum und die Diagrammbereiche festzulegen, und klicken Sie dann auf **Save analytics parameters**. Bestätigung: **Tracking parameters updated.**

![Dashboard](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard.webp)

![Dashboard tables](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard-b.webp)

| Field | At the start | What it does |
|---|---|---|
| **KPI period** | **Last 90 days** | Zeitfenster für KPI-Karten, Funnel-Tabelle, Top-Kunden und Mitarbeiter. Wählen Sie 30, 90, 180 oder 365 Tage und speichern Sie. Zählt erstellte, gesendete, angenommene, umgewandelte und abgelehnte Angebote in diesem Zeitraum. |
| **Weekly chart range** | 12 | Anzahl der Wochen im wöchentlichen Funnel-Diagramm (4–52). Die Wochen-Registerkarte zeigt erstellt, gesendet, angenommen und umgewandelt pro ISO-Woche. |
| **Monthly chart range** | 12 | Anzahl der Monate im monatlichen Funnel-Diagramm (3–24). |
| **Yearly chart range** | 5 | Anzahl der Jahre im jährlichen Funnel-Diagramm (2–10). |
| **Default chart tab** | **Monthly** | Welche Diagramm-Registerkarte zuerst geöffnet wird: Weekly, Monthly oder Yearly. Sie können die Registerkarten weiterhin ohne Speichern wechseln. |
| **Expiring soon window** | 7 | Wie viele Tage im Voraus Angebote als bald ablaufend markiert werden. Typischerweise 7 oder 14. Es werden nur gesendete und in Verhandlung befindliche Angebote mit einem valid_until-Datum in diesem Fenster aufgelistet. |

KPI-Karten: offener Pipeline-Wert, Pending review, bald ablaufend, umgewandelter Wert, Conversion-Rate, Win-Rate. Darunter: erstellt, gesendet, angenommen, umgewandelt, abgelehnt, durchschnittliche Tage bis zur Umwandlung, durchschnittlicher Angebotswert. Diagramme zeigen den Funnel über die Zeit. Tabellen: Perioden-Funnel, Alterung der offenen Pipeline, bald ablaufend, aktuelle Aktivität, Top-Kunden und Mitarbeiter. Offene Pipeline bedeutet Angebote in Sent, Negotiation oder Accepted.

### 3.3 Quotes tab in module configuration

Dieser Reiter ist eine kurze Übersicht. Vollständige Filter, Sammelaktionen und der Editor liegen unter **Orders**, **Quotes**.

![Quotes overview](https://mypresta.eu/docs/images/docs/quoteenterprise-quotes.webp)

Zweck dieses Bildschirms: eine schnelle Liste der letzten Angebote aus der Modulkonfiguration. Klicken Sie auf **View**, um den vollständigen Angebotseditor zu öffnen. Nutzen Sie **Manage all quotes** für Filter, Export und Sammeloperationen. Wirkung: Die Moduleinstellungen bleiben schlank, während die volle Angebotsarbeit im eigenen Backoffice-Bildschirm stattfindet.

**Create quote:** Wählen Sie einen Kunden (Suche), geben Sie optional eine **Internal note** ein und klicken Sie auf **Create draft quote**. Sie werden zum vollständigen Editor weitergeleitet. Leerer Kunde zeigt: **Please select a customer.**

**Quote templates** (wenn Vorlagen vorhanden sind): Wählen Sie eine Vorlage und einen Kunden, dann **Create from template**.

**Recent quotes**-Spalten: Reference, Customer, Status, Total. Leer: **No quotes yet.** Links: **Manage all quotes**, **CSV**, **XML**, **Open full quotes list**.

### 3.4 Quotes list (Orders menu)

Öffnen Sie **Orders**, **Quotes**. Das ist der Hauptverwaltungsschirm.

Spalten: **ID**, **Reference**, **Customer**, **Status**, **Total**, **Valid until**, **Assigned**, **Created**. Zeilenaktionen: bearbeiten und duplizieren. Sie können kein leeres Angebot aus der Listen-Symbolleiste hinzufügen; erstellen Sie aus der Modulübersicht, aus einer Vorlage oder durch Duplizieren. Fehler bei Versuch: **Create quotes from module configuration or duplicate an existing quote.**

Sammelaktionen:

| Action | What it does |
|---|---|
| **Assign to employee** | Setzt den zugewiesenen Mitarbeiter für die ausgewählten Angebote. |
| **Extend validity** | Verschiebt valid until für die Auswahl nach vorne. |
| **Send expiry reminder** | Sendet Erinnerungs-E-Mails an die ausgewählten Kunden (Bestätigungsdialog). |
| **Export CSV** | Lädt CSV für die Auswahl herunter. |
| **Export XML** | Lädt XML für die Auswahl herunter. |

Filtern Sie nach Status und suchen Sie wie in einer Standard-PrestaShop-Liste. Öffnen Sie eine Zeile zum Bearbeiten.

### 3.5 Quote editor — how to manage a request

Öffnen Sie ein Angebot aus der Liste. Die Legende zeigt Referenz und Status, zum Beispiel `Q-2026-00001 — Pending review`.

**Typischer Mitarbeiterweg für eine neue Kundenanfrage**

1. Filtern oder öffnen Sie Angebote in **Pending review**.
2. Prüfen Sie **Messages from customer** (Anfragetext, spätere Änderungs- oder Ablehnungsgründe). Schreibgeschützt.
3. Fügen Sie **Line items** hinzu oder passen Sie sie an (Katalogprodukte und individuelle Services).
4. Setzen Sie **Global discount %** / **Global discount amount**, **Shipping label** und Versandbeträge.
5. Schreiben Sie **General message to customer** und optional **Internal note**.
6. Setzen Sie **Validity period** und **Validity unit**, prüfen Sie das aktuelle valid until.
7. Setzen Sie bei Bedarf **Status**, dann **Save** (**Quote saved.**) oder **Save & send** (**Quote sent to customer by e-mail.**).

**Sperren.** Angenommene oder umgewandelte Angebote werden gesperrt. Abgelaufene Angebote zeigen: **This quote has expired. Click Unlock to extend validity and send an updated offer.** Umgewandelt: **This quote is locked because it was converted to an order.** Angenommen: **This quote is locked because the customer accepted it. Click Unlock to make changes.** Entsperren: **Quote unlocked for editing.** Erneut sperren: **Quote locked again.**

| Field | What it does (from field descriptions) |
|---|---|
| **Status** | Aktuelle Stufe im Verkaufsprozess. Draft: nur intern. Pending review: Kunde hat angefragt, wartet auf Ihre Preisgestaltung. Sent: per E-Mail an den Kunden gesendet. Accepted: Kunde hat zugestimmt. Converted: wurde zu einer Bestellung. Nur Sent und Negotiation können vom Kunden angenommen werden. Ändern Sie den Status bei Bedarf manuell. |
| **Validity period** | Wie lange der Kunde zum Annehmen Zeit hat, gezählt ab Speichern/Senden. Beispiele: 15 mit Minutes, 1 mit Hours, 30 mit Days. Speichern berechnet das Ablaufdatum ab jetzt neu. Der Kunde kann nach Ablauf nicht annehmen. Kurze Zeiträume können ablaufen, bevor der tägliche Cron Erinnerungen sendet. |
| **Validity unit** | Minuten, Stunden oder Tage mit der Gültigkeitszahl. |
| **Payment hint** | Kurzer Hinweis zur erwarteten Zahlung, z. B. „30 days net transfer“. Wird in der Kundenansicht und im PDF angezeigt. Erzwingt kein Zahlungsmodul. |
| **Global discount %** | Extra-Rabatt 0–100 auf alle Produktzeilen vor dem Versand. Beim Checkout kann er als Warenkorbregel gelten. |
| **Global discount amount (tax excl.)** | Fester Rabatt auf die Produktzwischensumme. Prozent wird zuerst angewendet, wenn beide gesetzt sind. |
| **Shipping label** | Name im PDF, z. B. „Express delivery“. |
| **Shipping (tax excl.)** / **Shipping (tax incl.)** | Liefergebühr. Tax incl. wird aus excl. automatisch berechnet, wenn in den Moduleinstellungen eine Steuerregel gesetzt ist. Enthalten in der Summe und beim Checkout als fester Versand übergeben. |
| **Messages from customer** | Alles, was der Kunde geschrieben hat (Anfrage, Änderungswunsch, Ablehnung). Schreibgeschützt. Antworten Sie in den Feldern darunter. |
| **General message to customer** | Dauerhafte Nachricht, die dem Kunden immer sichtbar ist (Umfang, Lieferzeit, Bedingungen). Wird in Angebotsansicht, PDF und E-Mails angezeigt. |
| **Internal note** | Private Teamnotiz. Wird dem Kunden nie angezeigt. |
| **Line items** | Produktzeilen und individuelle Servicezeilen. Katalogprodukt hinzufügen (Kombination wählen, wenn nötig). Individuelle Zeile hinzufügen: Beschreibung, Menge, Stückpreis ohne Steuer, Steuer %. Individuelle Zeilen erscheinen im PDF und landen beim Checkout im Gebührenprodukt. Meldungen: **Product line added.**, **Custom line added.**, **Line removed.**, **Select a product to add.**, **Please select a product combination.**, **Enter a service line description.** |
| **Comment for this send** | Einmalige Notiz nur für dieses **Save & send**. Erklärt, was sich geändert hat. Nach dem Senden geleert. Erscheint in der Timeline, optionaler PDF-Historie und der E-Mail dieses Versands. |
| **Version history** | Snapshots früherer Versionen. |
| **Save as template** | Geben Sie einen Vorlagennamen ein und speichern Sie. Später neue Angebote aus dieser Vorlage für einen anderen Kunden erstellen. Meldungen: **Please enter a template name.**, **Template "…" saved.** |
| **Quote timeline** | Chronologie der Mitarbeiter- und Kundenereignisse zu diesem Angebot. |

Duplizieren aus der Liste oder dem Editor: **Unable to duplicate quote.** bei Fehler. Nach dem Duplizieren bearbeiten Sie die Kopie.

### 3.6 Audit log

Modul-Reiter: aktuelle Aktivität (Anfragen, Sendungen, Annehmen/Ablehnen, Verhandlungen). Nutzen Sie **View** für den vollen Kontext. Öffnen Sie **Orders**, **Audit log** für Filter, Export und die vollständige Historie.

Zweck: nur anhängbare Spur für Compliance und Fehlerbehebung. Einträge können nicht bearbeitet oder gelöscht werden. Jede Zeile speichert den Akteur-Namen und die ID (Mitarbeiter oder Kunde) zum Zeitpunkt der Aktion. Akteur-Badges: Employee, Customer, System.

### 3.7 Settings — Theme & display

Öffnen Sie **Settings**. Klicken Sie nach Änderungen unten auf **Save**.

![Theme and display](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-theme.webp)

| Field | At the start | What it does |
|---|---|---|
| **Front theme template** | **Auto-detect (recommended)** | Wählt, welches Template und CSS-Set für My quotes, Angebotsvorschau und den Kundenkonto-Link verwendet wird. Lassen Sie Auto-detect, es sei denn, Ihr Theme-Fork wird falsch erkannt — dann Classic oder Hummingbird erzwingen. |
| **Quantity display format** | **Integer (e.g. 1, 2)** | Wie Mengen in Front Office, Backoffice, PDF und E-Mails angezeigt werden. Oder **Fixed decimals (e.g. 1.000, 2.500)**. Formulareingaben nutzen dasselbe Format für Standardwerte. |
| **Quantity decimal places** | 3 | Stellen nach dem Dezimalpunkt, wenn das Format Fixed decimals ist. Typischerweise 3 für B2B oder 2 für Retail. Im Integer-Modus ignoriert. |

### 3.8 Settings — General

![General](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-general.webp)

| Field | At the start | What it does |
|---|---|---|
| **Module enabled** | **Yes** | Hauptschalter für die gesamte Angebot-bis-Bestellung-Funktion. Yes: Kunden fordern Angebote an und Mitarbeiter verwalten Angebote. No: alle Angebotsschaltflächen und Kundenkonto-Links ausblenden ohne Deinstallation. Wenn deaktiviert: keine neuen Anfragen und keine Schaltflächen auf Warenkorb-, Produkt- oder Kategorieseiten. Bestehende Angebote bleiben im Backoffice. |
| **Product page quote button** | **Yes** | Zeigt **Request a quote** auf jeder Produktseite. Für B2B-Shops, in denen Käufer einen Preis für eine einzelne SKU anfragen. Der Kunde muss angemeldet sein (oder Gastfluss erlaubt) und in einer erlaubten Gruppe. Instant-Modus öffnet das Formular für dieses Produkt. List-Modus fügt Menge und Kombination zur schwebenden Angebotsliste hinzu. |
| **Cart quote button** | **Yes** | Zeigt **Request a quote** im Warenkorb. Aktivieren, wenn Kunden Angebote für mehrere Produkte auf einmal anfordern. Beachtet den Mindestwarenkorbwert unten. Der aktuelle Warenkorbinhalt wird nach Bestätigung zur Basis einer neuen Angebotsanfrage. |
| **Category / list quote button** | **Yes** | Kompaktes **Request quote** auf Listenseiten (Kategorie, Suche, Neuheiten). Dieselben Berechtigungsregeln. Instant-Modus öffnet den Produkt-Angebotsfluss. List-Modus fügt das Produkt (Standardkombination, Menge 1) zur schwebenden Liste hinzu. |
| **Product quote mode** | **Instant — open form for this product** | Instant: Formular für das aktuelle Produkt öffnen. List: zu einem Angebotskorb hinzufügen; schwebende Schaltfläche öffnet ein Formular mit allen Produkten. Warenkorb-Anfragen bleiben unabhängig. Die schwebende Schaltfläche erscheint nur im List-Modus, wenn die Liste nicht leer ist. |
| **Floating quote button position** | **Bottom right** | Oder **Bottom left**. Nur wenn der Produkt-Angebotsmodus List ist. Badge zeigt die Produktanzahl; öffnet das Mehrprodukt-Anfrageformular. |
| **Allow guests** | **No** | Ob Besucher ohne Konto eine Anfrage starten dürfen. Für striktes B2B ausgeschaltet lassen. Aktivieren, wenn Gäste die Schaltfläche sehen sollen — sie werden trotzdem zum Anmelden oder Registrieren aufgefordert, bevor die Anfrage gespeichert wird. Erstellt keine anonymen Angebote. |

### 3.9 Settings — Quote button visibility

![Visibility](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-visibility.webp)

| Field | At the start | What it does |
|---|---|---|
| Customer groups | all groups | Beschränkt, wer Angebotsschaltflächen sieht. Alle Gruppen oder nur ausgewählte Gruppen (z. B. Wholesale). Kunden außerhalb der ausgewählten Gruppen sehen keine Schaltflächen, auch wenn das Modul aktiviert ist. |
| **Enable catalog visibility rules** | **No** | Katalogbasierte Regeln für Angebotsschaltflächen ein- oder ausschalten. Aktivieren, um Angebote auf bestimmte Produkte, Kategorien, Marken oder Lieferanten zu begrenzen. Wenn deaktiviert, kann jedes Produkt angefragt werden (Gruppenregeln gelten weiterhin). Wenn aktiviert, werden Whitelist/Blacklist und die Filter darunter erzwungen. |
| **Catalog rule mode** | **Whitelist — only matching products** | Whitelist: Schaltflächen nur auf passenden Produkten. Blacklist: Schaltflächen auf passenden Produkten ausblenden. Ein Produkt passt, wenn es in der Produktliste ist oder zu einer ausgewählten Kategorie, einem Hersteller oder Lieferanten gehört. |
| Catalog pickers | empty | Kategorien (Baum), Produkte (Suche), Hersteller und Lieferanten. Leer lassen, um nur Hilfsfilter anzuwenden. Regeln kombinieren mit ODER — ein Treffer reicht. |
| **Minimum product price** | 0 | Angebotsschaltflächen unter diesem Shop-Preis inklusive Steuer ausblenden. 0 deaktiviert. Gilt, wenn Katalogregeln aktiviert sind. |
| **Exclude virtual products** | **No** | Verhindert das Anfragen von Download-/virtuellen Produkten, wenn Katalogregeln aktiviert sind. |
| **Exclude out-of-stock products** | **No** | Schaltflächen ausblenden, wenn das Produkt nicht aus dem Lager bestellt werden kann (beachtet das PrestaShop-Verhalten bei Fehlbestand). |
| **Mixed cart (eligible + excluded items)** | **Hide cart quote button** | Wenn der Warenkorb anfragbare und nicht anfragbare Produkte mischt: Show = Schaltfläche sichtbar, nur berechtigte Zeilen importiert; Hide = Schaltfläche ausgeblendet, bis der Warenkorb nur anfragbar ist. Alle berechtigt → immer anzeigen. Alle ausgeschlossen → immer ausblenden. |

### 3.10 Settings — Product quote request form

| Field | At the start | What it does |
|---|---|---|
| **Require privacy policy acceptance** | **Yes** | Pflicht-Datenschutz-Checkbox im Produkt-Angebotsanfrage-Modal (DSGVO). Kunden müssen vor dem Absenden zustimmen. |
| **Privacy policy CMS page** | none | CMS-Seite, die von der Checkbox verlinkt wird. Wenn leer, hat der Checkbox-Text keinen Link. |
| **Enable reCAPTCHA** | **No** | Schützt das Produkt-Angebotsanfrageformular mit Google reCAPTCHA v2. Wenn aktiviert, sind Site- und Secret-Key unten erforderlich. |
| **reCAPTCHA site key** | empty | Öffentlicher Site-Key aus der Google-reCAPTCHA-Verwaltung (v2-Checkbox). |
| **reCAPTCHA secret key** | empty | Secret-Key. In der Shop-Konfiguration gespeichert. |
| **Minimum cart total** | 0 | Mindestwarenkorbwert, bevor die Warenkorb-Angebotsschaltfläche angezeigt wird. Standardwährung des Shops. 0 = kein Minimum. Betrifft nur die Warenkorb-Schaltfläche, nicht Einzelprodukt-Anfragen. Kleine Warenkörbe zeigen die Schaltfläche nicht. |

### 3.11 Settings — Offers & references

| Field | At the start | What it does |
|---|---|---|
| **Default validity** | 30 | Standarddauer, wie lange ein Angebot nach Erstellung gültig bleibt. Zahl plus Einheit: Minuten für Flash-Angebote, Stunden für Tagesentscheidungen, Tage für Standard-B2B. Setzt valid_until bei neuen Angeboten aus Storefront, Backoffice und Duplikaten. Pro Angebot im Editor überschreibbar. |
| **Default validity unit** | **Days** | Minuten, Stunden oder Tage mit der Zahl oben. Erinnerungs-E-Mails und der automatische Status Expired hängen für Erinnerungen weiterhin vom Cron ab. |
| **Expiry reminder (days before)** | 3 | Erinnerungs-E-Mail vor Ablauf. Wird nur vom täglichen Cronjob gesendet. Jedes berechtigte Angebot erhält höchstens eine Erinnerung mit Link zum Ansehen und Annehmen. Ohne Cron keine Erinnerungen. |
| Cron URL | generated token | Automatisierte Ablauf-Erinnerungen und Statusaktualisierungen. Fügen Sie die URL einmal täglich in die crontab ein (Beispiel 08:00). Token neu erzeugen, wenn er preisgegeben wurde. Ablauf wird auch erzwungen, wenn jemand das Angebot öffnet; Erinnerungs-E-Mails brauchen weiterhin Cron. |
| **Reference prefix** | Q | Präfix für Angebotsnummern. Das Modul hängt Jahr und Sequenz an, z. B. Q-2026-00042. Hilft Mitarbeitern und Kunden, Dokumente in E-Mail und PDF zu erkennen. |
| **Notify staff on new request** | **Yes** | E-Mail an Shop-Mitarbeiter, wenn ein Kunde eine Anfrage absendet. Stellen Sie sicher, dass Preferences > Contact-E-Mail korrekt ist. Vorlage: qe-request-staff im Reiter Emails. |

Gelber Hinweis auf dem Bildschirm: Cron ist für die Gültigkeitsautomatisierung erforderlich; Ablauf gilt auch beim Öffnen; Erinnerungen nutzen die Cron-URL.

### 3.12 Settings — Checkout

| Field | At the start | What it does |
|---|---|---|
| **Shipping / service tax rule** | shop default tax rule | MwSt.-Regel für Versand und individuelle Servicezeilen, wenn Sie Beträge ohne Steuer eingeben. Wählen Sie eine Steuerregelgruppe unter Catalog → Products. Wenn ausgewählt, berechnet das Speichern eines Angebots Versand inkl. Steuer aus dem Exkl.-Betrag neu. |
| **Fee product (custom lines)** | created on install | Verstecktes virtuelles Produkt, das individuelle Servicezeilen in den Checkout bringt. Wird automatisch erstellt — nur ändern, wenn Sie individuelle Zeilen auf ein anderes Produkt zeigen müssen. Beim Checkout werden Service-Summen zu einer Warenkorbzeile mit dem gesperrten Angebotspreis. |

### 3.13 PDF

Öffnen Sie den Reiter **PDF**. Legende: **PDF documents**. Wenn PDF deaktiviert ist, sind Download-Schaltflächen ausgeblendet und PDF-URLs liefern „nicht gefunden“.

| Field | At the start | What it does |
|---|---|---|
| **Enable PDF** | **Yes** | Hauptschalter für PDF-Erzeugung und Download-Links. Deaktivieren, wenn Sie keine PDF-Proformas wollen. Wenn aus, sind PDF-Schaltflächen in Backoffice, Storefront und Bestelldetail ausgeblendet; direkte PDF-URLs liefern „nicht gefunden“. E-Mail-Vorlagen erhalten weiterhin einen leeren PDF-URL-Platzhalter. |
| **Use shop logo on PDF** | **Yes** | Nutzt das Shop-Logo aus Preferences > Themes. No: nur ein unten hochgeladenes eigenes Logo verwenden (falls vorhanden). Das Logo erscheint oben auf PDF-/Proforma-Dokumenten. |
| **Add negotiation history to PDF** | **No** | Hängt ein kurzes Kommunikationsprotokoll an (Änderungswünsche, erneutes Senden, Annehmen, Ablehnen). Kompakte Tabelle vor den Bedingungen. Leer, wenn keine Verhandlungsaktivität vorliegt. |
| **Custom PDF logo** | empty | Optionales PNG oder JPG nur für Angebots-PDFs. Überschreibt das Shop-Logo, wenn vorhanden. |
| **PDF terms & conditions** | empty | Rechtliche oder kommerzielle Bedingungen am Ende jedes PDFs. |
| **Authorized signature** | empty | Name oder Zeile des Unterzeichners, z. B. „John Smith, Sales Director“. Leer lassen, um wegzulassen. |

### 3.14 Emails

Öffnen Sie den Reiter **Emails**. Transaktionale E-Mails für den Angebotslebenszyklus. Betreff und Text pro Sprache bearbeiten. Platzhalter aus der Editor-Seitenleiste nutzen (Kundenname, Angebotsreferenz, Link, Summen). Eingebaute Schlüssel: qe-request-staff, qe-quote-sent, qe-quote-accepted, qe-quote-rejected, qe-quote-negotiation, qe-quote-reminder, qe-staff-digest. Kunden und Mitarbeiter erhalten diese, wenn ein Angebot angefragt, gesendet, angenommen wird oder bald abläuft. Nach Änderungen testen.

### 3.15 API

Öffnen Sie den Reiter **API**. CRM, ERP oder Automatisierung anbinden. Geben Sie eine Schlüsselbezeichnung ein und **Generate new API key**. Kopieren Sie den Schlüssel. **Revoke** deaktiviert ihn (Bestätigung). Leer: **No API keys yet.** **API documentation** beschreibt Aktionen: list, get, pending, stats, update_status. Rufen Sie die Modul-API-URL mit dem Schlüssel auf.

### 3.16 Notifications

Öffnen Sie **Notifications** (**Staff digest notifications**). Periodische Zusammenfassung, wenn Angebote Aktion brauchen, ohne eine E-Mail pro Ereignis.

Was als wartend zählt: **Pending review** (neue Anfrage) oder **Negotiation** (Kunde hat Änderungen angefragt). Sent, Accepted, Expired und Converted sind nicht enthalten. Cron läuft nach Ihrem Zeitplan. Wenn Digest aktiviert ist, mindestens ein Angebot wartet und das Intervall abgelaufen ist, geht eine Nachricht an jeden konfigurierten Kanal. Mitarbeiter sehen eine Zusammenfassung mit Referenzen, Status, Kundenname und Backoffice-Links (bis zu 20 Angebote aufgelistet).

| Field | At the start | What it does |
|---|---|---|
| **Enable digest** | **No** | Hauptschalter. Aktivieren, nachdem mindestens ein Kanal gesetzt ist. Cron muss geplant sein — Digests werden nicht durch Seitenbesuche gesendet. Wenn aus, erledigt Cron weiterhin Ablauf-Erinnerungen und Statusaktualisierungen, aber keinen Digest. |
| **Interval (hours)** | 24 | Mindestzeit zwischen Digests (1–168). Cron mindestens so oft wie dieser Wert ausführen. Nach einem erfolgreichen Digest wartet der nächste, bis so viele Stunden vergangen sind. |
| **E-mail recipients** | empty | Durch Komma oder Semikolon getrennt. Leer nutzt die Shop-E-Mail aus Preferences > Contact. Vorlage qe-staff-digest. |
| **Slack webhook URL** | empty | Incoming-Webhook-URL. Leer lassen, um Slack zu überspringen. |
| **Teams webhook URL** | empty | Connector-Webhook-URL. Leer lassen, um Teams zu überspringen. |

**Save** speichert die Einstellungen. **Send test digest now** sendet einen Test, wenn Angebote warten. Dieselbe Cron-URL wie unter Settings.

### 3.17 Updates

Öffnen Sie **Updates**. **Check Now** prüft auf eine neue Version. **Automatic Notifications** aktiviert oder deaktiviert. **Save** speichert die Update-Einstellungen.

### 3.18 Quote block on an order

Bei einer aus einem Angebot erstellten Bestellung zeigt das Backoffice **Source quote** mit Link zum Angebot und optional **View quote PDF**.

## 4. Front office

Kunden sehen Angebotswerkzeuge, wenn das Modul aktiviert ist und ihre Gruppe erlaubt ist.

**Product page.** **Request a quote** öffnet das Formular (Instant) oder fügt zur Angebotsliste hinzu (List-Modus). Datenschutz-Checkbox und reCAPTCHA gelten, wenn aktiviert.

**Product list.** **Request quote** — dieselben Regeln.

**Cart.** **Request a quote** — beachtet Mindestwarenkorbwert und Mixed-Cart-Regeln. Bestätigter Warenkorb wird zu einem Pending-Angebot.

**List mode.** Schwebende Schaltfläche mit Zähler öffnet das Mehrprodukt-Anfrageformular.

**Customer account.** Link zu **My quotes**: Historie, Status, valid until, **View**, PDF wenn aktiviert, **Checkout** nach Annahme, **Request re-opening** wenn abgelaufen/gesperrt. Leer: **You have no quotes yet. Request a quote from a product page or your cart to get started.** Nach dem Absenden: **Your quote request has been submitted. Our team will prepare an offer shortly.**

**Quote view.** Annehmen, ablehnen, Änderungen anfordern, PDF herunterladen, Checkout wenn angenommen. Gesperrt abgelaufen: **Locked — validity expired**.

Gastbesucher können Schaltflächen sehen, wenn **Allow guests** auf **Yes** steht, aber die Anfrage wird nur für einen angemeldeten Kunden gespeichert.

In diesem Paket gibt es keinen Storefront-Screenshot, weil der Testshop beim Fertigstellen der Screens nicht erreichbar war.

## 5. Common problems

**Keine Angebotsschaltfläche auf Produkt oder Warenkorb.** Prüfen Sie **Module enabled**, den passenden Schalter für die Schaltfläche, die Kundengruppe und die Katalogsichtbarkeit. Für den Warenkorb prüfen Sie **Minimum cart total** und **Mixed cart**.

**Gast kann Anfrage nicht abschließen.** Das Absenden braucht immer ein Konto.

**Angebot ist gesperrt / nicht bearbeitbar.** Entsperren, wenn Accepted oder Expired (Gültigkeit verlängern). Umgewandelte Angebote bleiben an die Bestellung gebunden gesperrt.

**Kunde kann nicht annehmen.** Status muss Sent oder Negotiation sein, und valid until muss in der Zukunft liegen.

**Erinnerungs-E-Mails kommen nie an.** Planen Sie die Cron-URL und halten Sie **Expiry reminder** über null. Das Öffnen eines Angebots kann es ohne Cron ablaufen lassen; Erinnerungen brauchen weiterhin Cron.

**PDF-Schaltflächen fehlen.** Schalten Sie **Enable PDF** ein.

**reCAPTCHA blockiert das Formular.** Schalten Sie es aus oder geben Sie beide Schlüssel ein.

**Mitarbeiter-Digest kommt nie an.** Digest aktivieren, einen Kanal setzen, Cron mindestens so oft wie das Intervall ausführen.

**Deinstalliert und Menü ist weg.** Neu installieren. Deinstallation löscht die Angebotstabellen. Das Gebührenprodukt kann im Katalog bleiben.

## 6. Developer guide

### 6.1 Overview

Technischer Name `quoteenterprise`, Version 1.7.6, Klasse `quoteenterprise` erweitert `Module`. Anzeigename über `$this->l('Quote Enterprise')`. Autor MyPresta.eu. Tab `checkout`. Produkt-URL in `$this->mypresta_link`.

Ablauf: Anfrage → `quote`-Zeile → Mitarbeiter bearbeiten/senden → Kunde annehmen/verhandeln → Checkout → Bestellung. Feldtexte für Händler liegen in `QuoteSettingDescTrait` und Angebotseditor-Methoden `desc*`.

### 6.2 Files

- `quoteenterprise.php` — Installation, Hooks, Konfigurationseinstieg, Cron-URL.
- `classes/QuoteAdmin.php` — Konfigurationsreiter und Einstellungsformulare.
- `classes/QuoteAdminQuoteForm.php` — Angebotseditor.
- `classes/QuoteQuotesManager.php` — Übersicht, Speichern/Senden/Zeilen/Vorlagen.
- `classes/QuoteDashboard.php`, `QuoteVisibility.php`, `QuoteListHelper.php`, `QuoteRequestHelper.php`, `QuoteMailer.php`, `QuotePdf.php`, `QuoteApi.php`, `QuoteNotifyDigest.php`, `QuoteExpiry.php`, `QuoteConverter.php`, `QuoteFeeProduct.php`, `QuoteSettingDescTrait.php`.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`, `AdminQuoteEnterpriseAuditLog.php`.
- `controllers/front/` — `list`, `view`, `request`, `quoteList`, `pdf`, `cron`, `api`.
- `models/` — `quote`, `quotedetail`, `quoteauditlog`, `quoterevision`, `quoteapikey`.
- `views/templates/`, `lib/updateChecker.php`, `lib/emailTemplatesManager/`, `lib/searchTool/`.

### 6.3 Controllers

Admin unter **Orders** (`AdminParentOrders`). Front-Controller in `$this->controllers`. Cron erwartet `QE_CRON_TOKEN`. API erwartet einen aktiven Schlüssel und einen Aktionsnamen.

### 6.4 Hooks

Registriert: `displayHeader`, `displayShoppingCart`, `displayCustomerAccount`, `displayProductAdditionalInfo`, `displayProductActions`, `displayFooterProduct`, `displayFooter`, `actionProductPriceCalculation`, `actionValidateOrder`, `actionAdminControllerSetMedia`, `displayProductListFunctionalButtons`, `displayProductListReviews`, `displayProductPriceBlock`, `displayAdminOrderMain`, `displayAdminOrderSide`, `displayAdminOrder`, `actionCartGetPackageShippingCost`. Keine eigenen Hooks freigegeben.

### 6.5 Overrides

Dieses Modul liefert keine Klassen- oder Controller-Overrides.

### 6.6 Database

| Table | Contents |
|---|---|
| `quote` | Angebotskopf. |
| `quote_detail` | Zeilen. |
| `quote_revision` | Versions-Snapshots. |
| `quote_audit_log` | Nur anhängbare Aktivität. |
| `quote_api_key` | API-Schlüssel. |
| `qe_cart_quote` | Warenkorb–Angebot-Verknüpfung. |

Deinstallation löscht diese Tabellen. `QuoteSchema::ensure` und `inconsistency()` reparieren fehlende Teile, wenn die Konfiguration geöffnet wird.

### 6.7 Keys and translations

`QE_*`-Konfigurationsschlüssel. Standardwerte in `installDefaults()`. Neue Sprache: `translations/{iso}.php`. Händler-Feldhilfe: `QuoteSettingDescTrait` und Editor-Methoden `desc*`. Zeichenketten über `$this->l()` und `{l s=... mod='quoteenterprise'}`.

### 6.8 Extending

Front-Templates unter `modules/quoteenterprise/` im Theme überschreiben. Classic und Hummingbird werden unterstützt. Ein anderes PDF-Layout bedeutet Änderung der PDF-Vorlage oder des Modulcodes.

## 7. Support

Modulseite: [Quote Enterprise](https://mypresta.eu/modules/ordering-process/quote-enterprise.html).

Um über dieses Modul zu schreiben, melden Sie sich in Ihrem Kundenkonto auf [mypresta.eu](https://mypresta.eu/) an, öffnen Sie [Contact](https://mypresta.eu/contact.html) und wählen Sie den Betreff **Support for paid modules**. Das Formular sagt, dass die Anmeldung erforderlich ist. Nach der Anmeldung wählen Sie dieses Modul aus Ihrer Kaufhistorie.
