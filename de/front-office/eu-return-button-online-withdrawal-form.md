---
title: "Return Button Pro - Dokumentation und Benutzerhandbuch"
description: "EU-Widerrufsformular konfigurieren, Fälle im Backoffice verwalten und typische Probleme beheben – für Händler, die Return Button Pro bereits nutzen."
sidebar:
  label: "Return Button Pro - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul EU Return Button – Online Withdrawal Form auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/eu-return-button-online-withdrawal-form/)
>
> ---



Screenshots in diesem Handbuch zeigen das englische Backoffice. Verwenden Sie dieselben Menünamen und Bezeichnungen wie hier geschrieben.

## 1. Anforderungen

Return Button Pro funktioniert mit PrestaShop 1.6, 1.7, 8 und 9. Verwenden Sie das Paket, das zu Ihrem Shop passt: den speziellen Build für PrestaShop 1.6 bei 1.6-Shops und den Build für PrestaShop 1.7–9 bei neueren Shops. Wenn in Ihrer MyPresta.eu-Bestellhistorie beide Pakete liegen, laden Sie die passende ZIP herunter.

- PrestaShop: 1.6.x, 1.7.x, 8.x und 9.x
- PHP: die Versionen, auf denen Ihr PrestaShop bereits läuft, einschließlich älterer Stacks mit PrestaShop 1.6 (PHP 5.6 und PHP 7.x) sowie der von PrestaShop 1.7–9 geforderten Versionen (PHP 7.1+ / PHP 8.x je nach Hosting und Shop). Das Modul wird auch für PHP-7.x-Umgebungen und aktuelles Shop-PHP gepflegt.
- Vom Modul genutzte PHP-Erweiterungen: JSON, curl (Update-Prüfungen), fileinfo (MIME-Prüfungen von Anhängen), hash (Tokens und Gast-Sicherheit)
- Andere Module: nicht erforderlich. Wenn das kostenlose Modul Return Button installiert und aktiviert ist, deaktivieren Sie es, bevor Sie Return Button Pro konfigurieren oder nutzen. Beide können nicht gleichzeitig laufen.
- Externe Konten: keine. Optionale Update-Prüfungen von MyPresta.eu nutzen das Internet über den Reiter **Updates**.

## 2. Installation

1. Laden Sie die Modul-ZIP unter **Modules** → **Module Manager** hoch, installieren und aktivieren Sie dann **Return Button Pro**.
2. Nach der Installation erscheint unter **Customers** der Eintrag **Withdrawals**. Öffnen Sie die Konfiguration über **Module Manager** → **Return Button Pro** → **Configure** (Reiter: **Dashboard**, **Settings**, **Updates**).
3. Die Installation leert den PrestaShop-Cache nicht. Leeren Sie den Cache selbst nach Theme- oder Hook-Änderungen, wenn der Storefront noch falsch aussieht.

Deinstallation: Der Menüeintrag **Withdrawals** wird entfernt und Konfigurationswerte gelöscht. Widerrufs-Tabellen und Falldatensätze bleiben in der Datenbank als rechtlicher Nachweis. Eine Neuinstallation löscht diese Datensätze nicht; das Modul kann sie wieder nutzen, wenn die Tabellen bereits existieren. Hochgeladene Mitarbeiter-Anhänge im Modulordner werden bei der Deinstallation nicht entfernt.

Wenn Sie vom kostenlosen Modul Return Button upgraden, kann Pro kompatible Einstellungen kopieren und leere Pro-Tabellen aus den Daten des kostenlosen Moduls migrieren, wenn Pro noch keine Zeilen hat. Deaktivieren Sie zuerst das kostenlose Modul.

## 3. Konfiguration und Arbeit im Backoffice

### 3.1 Vollständiger Widerrufsprozess

Ende-zu-Ende-Ablauf vom Storefront bis zur Bearbeitung durch Mitarbeiter:

1. Der Kunde findet den Widerrufseinstieg: Footer-Button, Link im Kundenkonto, Button auf der Bestelldetailseite oder die Formular-URL, wenn der Gastzugriff aktiv ist.
2. **Schritt 1 – Bestellung:** Eingeloggte Kunden sehen ihre Bestellungen mit Eignungshinweisen (verbleibende Tage, Gründe für Nichtverfügbarkeit). Gäste geben Bestellreferenz und E-Mail ein. Der Kunde wählt eine berechtigte Bestellung, wählt **Full order** oder **Partial** (mit Mengen bei erlaubten Positionen), fügt optional eine Nachricht und IBAN hinzu und fährt fort.
3. **Schritt 2 – Bestätigung:** Der Kunde prüft die Zusammenfassung der Erklärung. Wenn **Require legal confirmation checkbox** aktiv ist, muss er den Rechtstext anhaken und dann absenden.
4. Das Modul speichert den Fall, setzt ihn auf **Registered** und sendet die Kundenbestätigung (dauerhafter Datenträger) sowie eine Shop-Benachrichtigung (und **Notification email**, wenn gesetzt). Die Erfolgsseite zeigt die Widerrufsreferenz.
5. Mitarbeiter öffnen **Customers** → **Withdrawals** (oder das Seitenpanel der Bestellung), öffnen **View**, setzen den Status (**In progress**, **Refunded**, **Rejected** usw.) und geben bei Bedarf eine Kundennachricht ein.
6. Der Kunde verfolgt den Status über **Track withdrawal status**, die Statusseite und **Print / save PDF**. Mitarbeiternachrichten aus Statusänderungen erscheinen in der Widerrufshistorie des Kunden.

Vom Modul verwendete Statuswerte:

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Pending** | Kurzer Zustand, wenn die Erklärung erstmals gespeichert wird | Offener Fall, bevor die rechtliche Bestätigung des Kunden abgeschlossen ist, oder wenn Mitarbeiter diesen Status später setzen. Zählt bei aktiver Duplikatsperre zusammen mit anderen offenen Status. |
| **Registered** | Nach Bestätigung des Kunden in Schritt 2 | Erklärung erfasst; Bestätigungs-E-Mails wurden versucht. Standardstatus nach dem Absenden. |
| **In progress** | Aktion der Mitarbeiter | Der Shop bearbeitet den Fall (Rücksendungen, Prüfungen, Erstattungsvorbereitung). Blockiert weiterhin eine zweite aktive Anfrage, wenn die Duplikatsperre aktiv ist. |
| **Refunded** | Aktion der Mitarbeiter | Fall mit Erstattung abgeschlossen. Sichtbar auf der Kunden-Statusseite. |
| **Rejected** | Aktion der Mitarbeiter | Fall ohne Erstattung abgeschlossen. Verwenden Sie eine klare Kundennachricht, wenn die Einstellung dies verlangt. |

Umfang im Formular: **Full order** oder **Partial**. Typ: **Contract withdrawal** (bezahlt) oder **Contract cancellation (unpaid order)**, wenn die Bestellung nie bezahlt wurde.

### 3.2 Dashboard

Öffnen Sie **Modules** → **Module Manager** → **Return Button Pro** → **Configure** → **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/rbpro-dashboard.webp)

Filtern Sie mit **From** / **To** und **Apply**, oder setzen Sie mit **Last 30 days** zurück. Das Panel zeigt Gesamtsummen aller Zeiten, ausstehenden Rückstand, erkanntes Theme-Profil, aktiven Footer-Hook, KPIs (Widerrufe im Zeitraum, Quote vs. Bestellungen, Anteil E-Mail-Bestätigungen, durchschnittliche Tage von Bestellung bis Widerruf, Anteil Teil-/Vollwiderruf, Stornierungen, Erstattungsanteil abgeschlossener Fälle, Ablehnungsquote), ein Diagramm täglicher Einreichungen, Statusaufschlüsselung, am häufigsten widerrufene Produkte und älteste ausstehende Fälle mit **Open**.

Nutzen Sie **Manage all withdrawals** für die Liste unter Customers oder **Export CSV** für einen Download der Fälle im aktuellen Shop.

### 3.3 Settings

Öffnen Sie den Reiter **Settings** und klicken Sie nach Änderungen auf **Save**.

![Settings](https://mypresta.eu/docs/images/docs/rbpro-settings.webp)

#### Theme-Integration

Passen Sie das Modul an Classic, Hummingbird oder ein individuelles Theme an. Ändern Sie diese Einstellungen, wenn Buttons oder Formulare nach einem Theme-Update ungestylt wirken.

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Storefront theme profile** | Auto-detect | Wählt, welche Front-Office-Templates und CSS das Modul lädt (Classic vs. Hummingbird). Korrektes Button-Styling, Formularlayout und Erscheinung des My-Account-Links. Belassen Sie Auto-detect, sofern der Button nach einem Theme-Wechsel falsch aussieht; erzwingen Sie dann Classic-type oder Hummingbird-type passend zu Ihrem aktiven Theme. Nach der Änderung PrestaShop-Cache leeren und den Storefront aktualisieren. |
| **Footer button hook** | Auto (by theme profile) | Definiert, wo im Seitenfooter der Widerrufs-Button eingefügt wird. Auto folgt dem Theme-Profil (Hummingbird → displayFooterBefore, Classic → displayFooter). Fehlt der Button oder ist er falsch ausgerichtet, versuchen Sie manuell displayFooterBefore oder displayFooter, speichern, Cache leeren und den Shop-Footer prüfen. Für manuelle Platzierung setzen Sie den Custom-Hook in ein Theme-Template und wählen Sie hier displayRbproButton; lassen Sie **Footer button** aktiviert, damit der Button nur in diesem Template erscheint. |

#### Allgemein & Zugriff

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Module enabled** | Yes | Hauptschalter für das gesamte Modul. Wenn deaktiviert, sind Widerrufs-Buttons, Formular, Gastzugriff und Tracking im Storefront ausgeblendet; bestehende Widerrufsdatensätze im Backoffice bleiben. Nutzen Sie dies für Wartung oder rechtliche Prüfung ohne Deinstallation. |
| **Public status tracking page** | Yes | Aktiviert eine öffentliche Seite, auf der Kunden den Widerrufsstatus mit Widerrufsreferenz + E-Mail prüfen (ohne Login). Reduziert Tickets vom Typ „Wo ist meine Rücksendung?“. Aktivieren, wenn Sie neben dem Footer-Button einen Link **Track withdrawal status** möchten; kommunizieren Sie die Referenz aus der Bestätigungs-E-Mail. Deaktivieren, wenn Sie den Status nur per Konto-E-Mail oder Telefon handhaben. |
| **Guest access (order ref + email)** | Yes | Ermöglicht nicht eingeloggten Kunden, das Formular zu öffnen, indem sie in Schritt 1 Bestellreferenz und E-Mail eingeben. Empfohlen für B2C-EU-Fernabsatz. Ausschalten, wenn nur eingeloggte Kunden widerrufen dürfen. Gastsitzungen nutzen ein signiertes Cookie. |
| **Block duplicate active requests** | Yes | Verhindert einen zweiten offenen Widerruf für dieselbe Bestellung, solange einer bereits Pending, Registered oder In progress ist. Vermeidet Duplikate und widersprüchliche Erstattungen. In Produktion aktiv lassen. Nur zum Testen oder bei ungewöhnlichen Teilanspruch-Prozessen deaktivieren. |
| **Require legal confirmation checkbox (step 2)** | Yes | Zwingt den Kunden, vor dem Absenden ein rechtlich formuliertes Kontrollkästchen zu setzen. Explizite Einwilligungsaufzeichnung im Einklang mit EU-Widerrufsregeln. Den Checkbox-Text pro Sprache unter Texts & SEO bearbeiten. Wenn deaktiviert, wird die Einreichung ohne Pflicht-Häkchen dennoch protokolliert. |
| **Require message to customer when changing status** | Yes | Mitarbeiter müssen eine Nachricht an den Kunden eingeben, bevor ein Widerrufsstatus aktualisiert werden kann. Die Nachricht wird im Audit-Trail gespeichert und auf der Kunden-Statusseite angezeigt. Nur ausschalten, wenn Sie schnelle Statuswechsel ohne jedes Mal Schreiben brauchen. |
| **Show deadline countdown to customer** | Yes | Zeigt, wie viele Tage der gesetzlichen Widerrufsfrist verbleiben (Bestellliste und Formular). Benötigt eine korrekte Zuordnung **Order state = delivered** und die Widerrufsfrist. Wenn Daten falsch wirken, Bestellhistorie und den Lieferstatus prüfen. |
| **Optional IBAN field** | No | Fügt ein optionales IBAN-Feld im Formular für Erstattungsauszahlungen hinzu. Nur aktivieren, wenn Sie per Banküberweisung erstatten und Ihre Datenschutzrichtlinie dies abdeckt. Aus lassen, wenn Sie nur auf die ursprüngliche Zahlungsmethode erstatten. |
| **Notification email** | Empty | Zusätzliche Adresse, die Benachrichtigungen zu neuen Widerrufen erhält (zusätzlich zum Shop-Kontakt). Beispiel: returns@yourshop.com. Leer lassen, um nur den Standard-Mailfluss von PrestaShop ohne diesen Empfänger zu nutzen. |

#### Widerrufsregeln

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Withdrawal period (days from delivery)** | 14 | Kalendertage, die Kunden nach als geliefert geltender Bestellung zum Widerruf haben. Standard 14 für EU-Fernabsatzverträge. Nur ändern, wenn Recht oder Ihre AGB einen anderen Wert verlangen. Der Countdown startet ab dem Lieferdatum aus der Bestellhistorie und **Order state = delivered**. |
| **Order state = delivered** | Auto | Bestellstatus, der Waren als geliefert markiert (Beginn der Widerrufsfrist). Wählen Sie den Status, den Sie setzen, wenn das Paket geliefert ist (z. B. Delivered, oder Shipped, wenn das Ihr Endstatus ist). Auto nutzt eine sinnvolle Vorgabe Ihres Shops; überschreiben, wenn Fristen das falsche Datum nutzen. |
| **Allowed order statuses** | All order statuses | Steuert, wann Kunden basierend auf dem aktuellen Bestellstatus einen Widerruf einreichen dürfen. Wählen Sie **All order statuses**, um den Filter zu überspringen, oder **Only selected statuses** und verschieben Sie Status von der linken Spalte nach **Allowed for withdrawal**. Bestellungen außerhalb der Liste erscheinen in der Kontoliste als nicht verfügbar. |
| **Excluded products** | Empty | Bestimmte Produkte, die nicht widerrufen werden können (versiegelte Ware, Sonderanfertigungen u. Ä.). Nach Name suchen oder IDs behalten; ausgeschlossene Positionen zeigen die Ausschlussmeldung im Formular. |
| **Excluded product variants** | Empty | Bestimmte Varianten vom Widerruf ausgeschlossen. Produkt suchen, dann Variante wählen. |
| **Excluded categories** | Empty | Alle Produkte in diesen Kategorien sind nicht widerrufbar. |
| **Excluded manufacturers** | Empty | Produkte dieser Hersteller können nicht widerrufen werden. |
| **Excluded suppliers** | Empty | Produkte, die mit diesen Lieferanten verknüpft sind, können nicht widerrufen werden. |
| **Excluded customer groups** | Empty | Kunden in diesen Gruppen können Widerruf überhaupt nicht nutzen (kein Formularzugriff, Buttons ausgeblendet). |

#### Footer & Erscheinungsbild

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Footer button** | Yes | Zeigt den Haupt-Call-to-Action für den Widerruf im Shop-Footer (Hook wie oben konfiguriert). Deaktivieren, wenn Sie nur My-Account- und Bestelldetail-Links möchten. Erfordert **Module enabled** und einen korrekten Footer-Hook. |
| **Footer theme** | Light footer (dark text) | Farbschema für Footer-Text und Links (nicht den Button-Hintergrund). Light bei hellen Footern, Dark bei schwarzen/dunklen Footern wählen, damit **Track withdrawal status** lesbar bleibt. Nach Änderung Cache leeren. |
| **Footer alignment** | Center | Horizontale Ausrichtung des Footer-Button-Blocks: Left, Center oder Right. Betrifft nur die Ausgabe des Footer-Hooks. |
| **Button color** | #2563eb | Hintergrundfarbe der Widerrufs-Buttons (Footer, Bestelldetail u. Ä.). Hex-Farbe mit genug Kontrast zu weißem Text wählen. Ändert die Theme-Primärfarbe nicht global. |
| **Custom CSS** | Empty | Zusätzliches CSS auf Seiten mit Modul-Buttons. Für Abstände, Schriften oder Ausblenden von Elementen ohne Theme-Dateien zu bearbeiten. Zuerst auf Staging testen. |
| **Link in customer account** | Yes | Fügt einen Widerrufseintrag in My Account hinzu. Empfohlen aktiv. Nur deaktivieren, wenn Sie ausschließlich Footer- oder Bestell-Links nutzen. |
| **Link on order detail** | Yes | Zeigt die Widerrufsaktion auf der Bestelldetailseite, wenn die Bestellung berechtigt ist. Gesperrte Bestellungen zeigen statt des Buttons eine kurze Begründung. |

#### Texts & SEO

Füllen Sie jede aktive Shopsprache aus.

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Noindex on form page** | Yes | Fügt robots noindex,nofollow auf der Widerrufsformular-URL hinzu, damit Rechts-/Formularseiten aus Suchergebnissen bleiben. Nur ausschalten, wenn Sie das Formular bewusst indexieren wollen. |
| **Button label** | Withdraw from contract | Text auf allen Widerrufs-Buttons und Links. Kurze Bezeichnung funktioniert im Footer am besten. Wichtigste kundennahe Formulierung des Moduls. |
| **Exclusion message** | This product is excluded from the statutory right of withdrawal. | Neben ausgeschlossenen Produkten im Formular angezeigt. Erklären Sie, warum der Artikel nicht wählbar ist; erwähnen Sie bei Bedarf Ihre AGB. |
| **SEO title** | Withdraw from contract | HTML-Seitentitel des Widerrufsformulars (Browser-Tab). Pro Sprache unter ca. 60 Zeichen halten. |
| **SEO description** | Online withdrawal form for distance contracts. | Meta-Beschreibung für das Formular. Bei aktivem noindex meist ohne Ranking-Wirkung. Leer lassen zum Weglassen. |
| **Legal confirmation checkbox text** | I confirm that I am submitting a withdrawal statement and understand the legal consequences. | Beschriftung neben dem Pflicht-Kontrollkästchen in Schritt 2. Klare, ländergerechte Formulierung verwenden. Erforderlich, wenn **Require legal confirmation checkbox** aktiv ist. |

### 3.4 Updates

Öffnen Sie den Reiter **Updates**.

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **Manual Check** | — | Prüft bei MyPresta.eu auf eine neuere Modulversion. Sie sehen **New version available!** oder **Module is up to date!**. Benötigt curl und ausgehendes HTTPS. |
| **Automatic Notifications** | Enabled (module default for update prefs) | Wenn aktiviert, kann das Backoffice einen Hinweis auf eine neue Version anzeigen. Mit **Save** speichern. |
| **Product Page** | Link on form | Öffnet die offizielle Produktseite mit Release-Informationen. Für Hilfe zu bezahlten Modulen Support (§7) nach Login nutzen. |

Wenn das kostenlose Modul Return Button noch aktiviert ist, sind Einstellungen und Update-Aktionen gesperrt, bis Sie es deaktivieren.

### 3.5 Widerrufsliste

Gehen Sie zu **Customers** → **Withdrawals**.

![Withdrawals list](https://mypresta.eu/docs/images/docs/rbpro-withdrawals.webp)

Standardsortierung ist neueste Einreichung zuerst. Spalten:

| Feld | Zu Beginn | Funktion |
|---|---|---|
| **ID** | Auto | Interne Fall-ID. |
| **Submitted** | From form | Datum und Uhrzeit der Kundeneinreichung. |
| **Order** | From order | PrestaShop-Bestellreferenz. |
| **First name** / **Last name** / **Email** | From customer | Kontaktidentität zum Fall. |
| **Scope** | Full order or Partial | Ob die gesamte Bestellung oder ausgewählte Positionen widerrufen wurden. |
| **Type** | Contract withdrawal or cancellation | Bezahlter Widerruf vs. Stornierung einer unbezahlten Bestellung. |
| **Status** | Registered after confirm | Aktueller Fallstatus (Pending, Registered, In progress, Refunded, Rejected). |
| **Email** | Yes/No | Ob die Bestätigungs-E-Mail als gesendet erfasst wurde. |

Nutzen Sie Suche und Sortierung in der Liste. Öffnen Sie einen Fall mit **View**. Es gibt keine Aktion **Add new**: Anfragen werden nur von Kunden im Storefront erstellt. Wenn jemand versucht, einen Fall im Backoffice zu erstellen, erklärt die Warnung, dass Widerrufe nicht manuell angelegt werden können, und die Liste wird erneut angezeigt.

Exportieren Sie CSV vom **Dashboard** (**Export CSV**), wenn Sie eine Tabellenkalkulation der Fälle für den Shop brauchen.

### 3.6 Fallansicht Widerruf

Öffnen Sie eine Zeile mit **View**.

Der Kopf zeigt Referenz, ID, Einreichungsdatum, Status, Typ, Umfang, E-Mail-gesendet-Flag und Zeit, Frist, IP, User-Agent, Kundenname und E-Mail sowie einen Link zur PrestaShop-Bestellung. Der Produktblock listet jede widerrufene Position mit Menge und Stückpreis. IBAN und Kundennachricht erscheinen, wenn der Kunde sie angegeben hat.

**Update status**

1. Wählen Sie **New status**.
2. Schreiben Sie **Message to customer** (erforderlich, wenn diese Einstellung aktiv ist; sonst optional). Der Hilfetext erklärt, dass die Nachricht in der Storefront-Widerrufshistorie erscheint.
3. Klicken Sie auf **Update status**.

Erfolg: **Status updated.** Andere Meldungen: **Please enter a message for the customer when changing the status.**, **Status is already set to this value.**, **Invalid status.**, **Could not update status.**

**Resend confirmation email** sendet die Kundenbestätigung erneut, aktualisiert bei Erfolg das Gesendet-Flag und protokolliert das Ereignis. Erfolg: **Confirmation email sent.** Fehler: **Could not send email.**

**Internal notes** sind nur für Mitarbeiter. Text eingeben und **Add note** klicken. Notizen erscheinen unter **Internal notes** und im Audit-Trail; sie ersetzen nicht die kundenorientierte Statusnachricht.

**Attachments** akzeptieren Mitarbeiter-Uploads (PDF und gängige Bilder, max. 10 MB). Download per Klick auf den Dateinamen. Meldungen: **Attachment uploaded.**, **Invalid file or size over 10 MB.**, **File type not allowed.**, **Upload failed.**

**Audit trail** listet Datum, Ereignis, Mitarbeiter und Details (Statusübergänge und Nachrichten). Typische Ereignisse: Kunde hat die Erklärung eingereicht, Kunde hat die rechtliche Erklärung bestätigt, Status aktualisiert, Bestätigungs-E-Mail gesendet, Dokument hinzugefügt, interne Notiz hinzugefügt.

Nutzen Sie **Back to list**, um zu **Withdrawals** zurückzukehren.

### 3.7 Bestell-Seitenpanel im Backoffice

Unter PrestaShop 1.7.7 und neuer öffnen Sie eine Bestellung im Backoffice. Wenn diese Bestellung Widerrufsfälle hat, listet ein Seitenblock **Withdrawal requests** jede Referenz, Status-Badge, Datum und **View** (öffnet den Fall). Bei älteren 1.7-Builds ohne Side-Order-Hook nutzen Sie **Customers** → **Withdrawals** und filtern nach Bestellreferenz.

Ausstehende Fälle können auch eine Backoffice-Warnung mit der Anzahl zur Prüfung ausstehender Anfragen und einem Link zur Liste auslösen.

## 4. Storefront

Hier sind keine Storefront-Screenshots enthalten; Theme verdrahten und den Live-Shop nach dem Speichern der Settings und dem Leeren des Caches prüfen.

### 4.1 Footer

Mit aktivem **Footer button** und korrektem Hook zeigen Seiten den Widerrufs-Button (Label aus **Button label**), gestylt mit **Button color**, plus **Track withdrawal status**, wenn öffentliches Tracking aktiv ist. **Footer alignment** und **Footer theme** steuern Layout und Textkontrast. Ruft das Theme den gewählten Footer-Hook nie auf, ändern Sie den Hook oder platzieren Sie den Custom-Hook in einem Template und wählen Sie diese Option unter **Footer button hook**.

### 4.2 Kundenkonto

Mit aktivem **Link in customer account** zeigt My Account den Widerrufseintrag (und den Track-Link, wo das Konto-Template ihn enthält). Ausgeschlossene Kundengruppen sehen keine Einstiegspunkte.

### 4.3 Bestelldetail

Mit aktivem **Link on order detail** zeigen berechtigte Bestellungen den Widerrufs-Button vorausgefüllt für diese Bestellung. Bestehende Fälle zur Bestellung werden mit Status aufgelistet. Nicht berechtigte Bestellungen zeigen statt des Buttons eine kurze Begründung, z. B. Frist abgelaufen, Status nicht erlaubt, doppelte aktive Anfrage oder keine berechtigten Produkte.

### 4.4 Gastzugriff

Wenn **Guest access** aktiv ist, öffnet ein Besucher das Formular, gibt Bestellreferenz und E-Mail ein und fährt für diese Bestellung wie ein eingeloggter Kunde fort. Wenn der Gastzugriff aus ist, sehen Gäste, dass sie sich anmelden müssen (oder Sie den Gastzugriff in Settings aktivieren müssen). Ungültige Sicherheitstoken und zu viele Versuche zeigen klare Warte-/Wiederholungs-Meldungen.

### 4.5 Status verfolgen

**Track withdrawal status** fragt nach Widerrufsreferenz (Format wie RBP-…) und E-Mail und zeigt dann Status, Einreichungsdatum, Umfang, Zustand der Bestätigungs-E-Mail sowie Links zu Details und Druck. Falsches Paar: **No withdrawal found for these details.**

### 4.6 Statusseite und Druck

Nach dem Absenden zeigt **Withdrawal submitted** die Referenz, eine Checkliste (Erklärung gespeichert, Bestätigungs-E-Mail, Shop bearbeitet), dann **View withdrawal details**, **Track status** und **Print / save PDF**. Die Statusseite listet Produkte, Mengen, Preise, Summen und **Withdrawal history** einschließlich Mitarbeiternachrichten aus Statusaktualisierungen. Druck öffnet eine druckbare Nachweisseite mit sicherem Token aus dem Bestätigungsfluss.

## 5. Probleme

### 5.1 Kostenloses Return Button noch aktiviert

**Symptom:** Konfiguration ist gesperrt; Hinweis, dass das andere Rücksende-Modul aktiviert ist; Speichern kann melden, dass Änderungen nicht gespeichert wurden, bis dieses Modul deaktiviert ist.

**Was tun:** **Modules** → **Module Manager** → kostenloses Modul Return Button finden → **Disable**. Dann Return Button Pro erneut öffnen.

### 5.2 Footer-Button fehlt

**Symptom:** kein Widerrufs-Button im Footer.

**Was tun:** Bestätigen Sie, dass **Module enabled** und **Footer button** aktiv sind. Unter **Settings** setzen Sie **Footer button hook** auf Auto oder versuchen Sie die anderen Footer-Positionen nacheinander. Cache leeren und Shop hart neu laden. Bei Custom-Themes den Custom-Modul-Hook im Template platzieren und diese Option unter **Footer button hook** wählen. Öffnen Sie **Dashboard**: Es zeigt das erkannte Theme-Profil und den Namen des aktiven Footer-Hooks zum Abgleich mit dem Theme.

### 5.3 „Return not available — the withdrawal period has ended.“

**Symptom:** Bestelldetail oder Formular blockiert den Widerruf mit dieser Meldung.

**Was tun:** Prüfen Sie **Withdrawal period** und **Order state = delivered**. Bestellhistorie korrigieren, wenn die Lieferung nie erfasst wurde. Frist nur verlängern, wenn Ihre AGB es erlauben.

### 5.4 „An active withdrawal request already exists for this order.“

**Symptom:** Kunde kann keinen zweiten Fall öffnen.

**Was tun:** Bestehenden Fall abschließen oder schließen (**Refunded** / **Rejected**), oder **Block duplicate active requests** vorübergehend ausschalten, nur wenn Ihr Prozess wirklich mehrere offene Ansprüche erlaubt.

### 5.5 „This order status does not allow withdrawal.“

**Symptom:** Bestellung liegt außerhalb des erlaubten Statusfilters.

**Was tun:** Unter **Settings** **Allowed order statuses** auf **All order statuses** setzen oder den aktuellen Bestellstatus zu **Allowed for withdrawal** hinzufügen.

### 5.6 „No products in this order are eligible for withdrawal.“ / Ausschlussmeldung bei Positionen

**Symptom:** jede Position ausgeschlossen oder ausgewählte Teilpositionen ungültig.

**Was tun:** Ausgeschlossene Produkte, Varianten, Kategorien, Hersteller und Lieferanten prüfen. **Exclusion message** anpassen, damit Kunden verstehen warum.

### 5.7 „Withdrawal is not available for your customer account.“

**Symptom:** Formular oder Buttons für einen eingeloggten Kunden ausgeblendet.

**Was tun:** Die Gruppe des Kunden aus **Excluded customer groups** entfernen oder den Kunden in eine erlaubte Gruppe verschieben.

### 5.8 „Please enter a message for the customer when changing the status.“

**Symptom:** Statusaktualisierung in der Fallansicht schlägt fehl.

**Was tun:** **Message to customer** ausfüllen oder **Require message to customer when changing status** ausschalten, wenn Ihr Prozess leere Nachrichten erlaubt.

### 5.9 Bestätigungs-E-Mail nicht gesendet

**Symptom:** Fall zeigt E-Mail nicht gesendet; Kunde hat keine dauerhafte Bestätigung.

**Was tun:** PrestaShop-Mail-Einstellungen korrigieren, Spam prüfen, **Resend confirmation email** nutzen. **Notification email** für Mitarbeiterkopien setzen. Bestätigen, dass die Shop-Kontakt-E-Mail funktioniert.

### 5.10 Gast findet die Bestellung nicht

**Symptom:** **No order found for the given details.** oder Rate-Limit-Wartezeit.

**Was tun:** Exakte Bestellreferenz und Bestell-E-Mail abgleichen. Bei zu vielen Versuchen warten. Bestätigen, dass **Guest access** aktiv ist.

### 5.11 Update-Prüfung schlägt fehl oder bleibt still

**Symptom:** manuelle Prüfung meldet keine Version.

**Was tun:** Sicherstellen, dass curl funktioniert und der Server MyPresta.eu erreicht. Kostenloses Modul deaktivieren, wenn Pro gesperrt ist. **Manual Check** auf dem Reiter **Updates** erneut versuchen.

## 6. Für Entwickler

### 6.1 Überblick

- Technischer Name: `rbpro`
- Version: aktuelles 1.7–9-Paket (z. B. 1.4.6); PrestaShop 1.6 als separates Paket (z. B. 1.4.5) mit `ps_versions_compliancy` min `1.6.0.0`
- Anzeigename: Return Button Pro
- Autor: MyPresta.eu
- Tab: `front_office_features`
- Hauptklasse: `Rbpro`
- `ps_versions_compliancy` im 1.7–9-Paket: min `1.7.0.0`; im 1.6-Paket: min `1.6.0.0`
- Service-Schicht: `RbpWithdrawalService`; Sicherheit: `RbpSecurity`; Theme/Hooks: `RbpCompatibility`; Analytics: `RbpStatsService`
- Ablauf: Konfigurationsschlüssel → Hooks / Front-Controller → Tabellen `rbp_withdrawal*` → Admin `AdminRbpWithdrawal` → Kundenstatus/Track/Druck

### 6.2 Wichtige Dateien

| Pfad | Rolle |
|---|---|
| `rbpro.php` | Modul-Bootstrap, Install/Uninstall, Configure-Reiter, Hooks, Defaults |
| `classes/RbpWithdrawal.php` | Fallobjektmodell und Statuswerte |
| `classes/RbpWithdrawalService.php` | Eignung, Fristen, Create/Confirm, E-Mails, Statusupdates |
| `classes/RbpSecurity.php` | CSRF, Gast-Grant, Rate-Limit, IBAN-Sanitizing |
| `classes/RbpCompatibility.php` | Theme-Profil, Footer-Hook-Auflösung, Admin-URLs, erforderliche Hooks |
| `controllers/admin/AdminRbpWithdrawalController.php` | Liste und Fallansicht |
| `controllers/front/form.php` | Zweistufiges Formular |
| `controllers/front/confirm.php` | Erfolgsseite |
| `controllers/front/track.php` | Öffentliches Tracking |
| `controllers/front/status.php` | Falldetails für Kunden |
| `controllers/front/print.php` | Druckbarer Nachweis |
| `sql/install.sql` | Erstellt `rbp_*`-Tabellen |
| `sql/uninstall.sql` | Nur Kommentar — Tabellen bleiben |
| `lib/updateChecker.php` | MyPresta-Update-UI (`rbproUpdate`) |
| `views/templates/admin/*` | Dashboard, Configure-Shell, Fallansicht, Bestell-Seitenhinweis |
| `views/templates/front/*` | Formular, Confirm, Track, Status, Print, Error |
| `views/templates/hook/*` | Footer-/Konto-/Bestell-Buttons (classic / hummingbird) |
| `mails/*` | Templates `rbf_withdrawal_customer` / `rbf_withdrawal_admin` |
| `translations/*.php` | Paketübersetzungen |

### 6.3 Controller

| Controller | Parent / Einstieg | Hinweise |
|---|---|---|
| Configure (`getContent`) | Module Manager | Reiter `rbp_tab`: `dashboard`, `settings`, `updates` |
| `AdminRbpWithdrawal` | Customers → Withdrawals | `add`/`edit` false; nur Ansicht ohne manuelles Anlegen; CSV-Export; Anhang-Download |
| Front `form` | Module link | Schritte 1–2; Gast-Lookup; Draft-Cookie |
| Front `confirm` | Module link | Erfolg nach Absenden |
| Front `track` | Module link | Referenz + E-Mail |
| Front `status` | Module link | Zeitlinie + Produkte |
| Front `print` | Module link | HMAC-Token auf Referenz |

Berechtigungen folgen dem Admin-Tab. Front-Controller erfordern für das Formular ein aktiviertes Modul; Tracking respektiert `RBP_ENABLE_STATUS_TRACK`.

### 6.4 Hooks

Registriert: `displayHeader`, `actionFrontControllerSetMedia`, `displayCustomerAccount`, `displayOrderDetail`, `actionPresentOrder`, `displayFooter`, `displayFooterBefore`, `displayFooterAfter`, `displayRbproButton`; bei PS ≥ 1.7.7 auch `displayBackOfficeHeader`, `displayAdminOrderSide`.

Vom Modul ausgeführt: `actionRbpWithdrawalCreated`, `actionRbpWithdrawalConfirmed` (und statusbezogene Hooks aus dem Service, wo definiert).

Footer-Ausgabe läuft nur für den Hook-Namen, den `RbpCompatibility::getFooterHookName()` auflöst.

### 6.5 Overrides

Keine Klassen- oder Controller-Overrides. Theme-Integration nur über Hooks und wählbare Templates.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `PREFIX_rbp_withdrawal` | Fallkopf: Shop, Bestellung, Kunde, Referenz, Umfang, Typ, Status, IBAN, Nachricht, IP, UA, Sprache, E-Mail-Flags, Frist, Daten |
| `PREFIX_rbp_withdrawal_product` | Ausgewählte Positionen und Mengen |
| `PREFIX_rbp_withdrawal_note` | Interne Mitarbeiternotizen |
| `PREFIX_rbp_withdrawal_attachment` | Metadaten von Mitarbeiter-Uploads |
| `PREFIX_rbp_withdrawal_history` | Audit-Ereignisse |

Deinstallation löscht diese Tabellen **nicht**. `ensureDatabase()` erstellt fehlende Tabellen und kann von `rbf_*` migrieren, wenn Pro-Tabellen leer sind und Free-Tabellen Zeilen haben.

### 6.7 Konfigurationsschlüssel und Übersetzungen

Defaults aus `Rbpro::CONFIG`:

| Schlüssel | Default |
|---|---|
| `RBP_ENABLED` | 1 |
| `RBP_GUEST_ENABLED` | 1 |
| `RBP_IBAN_ENABLED` | 0 |
| `RBP_WITHDRAWAL_DAYS` | 14 |
| `RBP_DELIVERED_STATUS` | 0 (Auto) |
| `RBP_EXCLUDED_PRODUCTS` / `_COMBINATIONS` / `_CATEGORIES` / `_MANUFACTURERS` / `_SUPPLIERS` / `_CUSTOMER_GROUPS` | empty |
| `RBP_ALLOWED_ORDER_STATES` | empty |
| `RBP_ALLOWED_ORDER_STATES_RESTRICT` | 0 |
| `RBP_FOOTER_ENABLED` | 1 |
| `RBP_FOOTER_THEME` | light |
| `RBP_FOOTER_POSITION` | center |
| `RBP_BUTTON_COLOR` | `#2563eb` |
| `RBP_CUSTOM_CSS` | empty |
| `RBP_SHOW_ACCOUNT` / `RBP_SHOW_ORDER` | 1 |
| `RBP_SEO_NOINDEX` | 1 |
| `RBP_ADMIN_EMAIL` | empty |
| `RBP_BLOCK_DUPLICATE` | 1 |
| `RBP_SHOW_DEADLINE` | 1 |
| `RBP_REQUIRE_CHECKBOX` | 1 |
| `RBP_REQUIRE_STATUS_MESSAGE` | 1 |
| `RBP_THEME_TYPE` | auto |
| `RBP_FOOTER_HOOK` | auto |
| `RBP_ENABLE_STATUS_TRACK` | 1 |

Mehrsprachig (nicht im `CONFIG`-Array, per Defaults installiert): `RBP_BUTTON_TEXT`, `RBP_EXCLUSION_MSG`, `RBP_SEO_TITLE`, `RBP_SEO_DESC`, `RBP_LEGAL_CHECKBOX`. Runtime: `RBP_ADMIN_FOLDER`. Update-Prefs nutzen MyPresta-Update-Checker-Schlüssel. Free-Modul-Migration mappt `RBF_*` → `RBP_*`, wenn Pro-Schlüssel leer sind.

Übersetzungen: `translations/{iso}.php`. Feld-`desc`-Strings leben in `renderConfigurationForm()` über `$this->l()`.

Statuswerte: `pending`, `confirmed` (Label Registered), `processing`, `refunded`, `rejected`.

### 6.8 Erweiterung

Hook-TPL/CSS im Theme für `modules/rbpro/...` überschreiben, ohne das Modul zu bearbeiten. `{hook h='displayRbproButton'}` für individuelle Button-Platzierung setzen. Auf `actionRbpWithdrawalCreated` / `actionRbpWithdrawalConfirmed` hören. Nicht auf Overrides verlassen — es gibt keine zum Cascaden.

## 7. Support

Produktseite: https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html

Hilfe zu diesem bezahlten Modul: Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an, öffnen Sie Contact und wählen Sie **Support for paid modules**. Das Formular erfordert Login für bezahlte Module; nach dem Login wählen Sie Return Button Pro aus Ihrer Kaufhistorie.