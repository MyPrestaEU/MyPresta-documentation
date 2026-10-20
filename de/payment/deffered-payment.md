---
title: "Zahlungsaufschub - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Zahlungsaufschub von MyPresta.eu."
sidebar:
  label: "Zahlungsaufschub - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Deffered Payment auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/deffered-payment.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/deffered-payment/)
>
> ---


# Zahlungsaufschub

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und im Allgemeinen ausreichend für dieses Modul. Es werden keine ungewöhnlichen Erweiterungen benötigt.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Zahlungsaufschub)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten des Moduls „Zahlungsaufschub“ definieren.

- **Menüpfad:** Back Office > Module > Modul-Manager > Suche nach „Zahlungsaufschub“ > Klicken Sie auf „Konfigurieren“

#### Allgemeine Einstellungen

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Zahlungsaufschub aktivieren** | JA | **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Die Option „Zahlungsaufschub“ ist beim Checkout für berechtigte Kunden verfügbar.   *Wenn deaktiviert:* Die Option „Zahlungsaufschub“ wird allen Kunden ausgeblendet, unabhängig von anderen Einstellungen.   **Empfohlener Wert:** JA (um das Modul zu verwenden).   **Händlerszenario:** Aktivieren Sie dies, wenn Sie bereit sind, diese Zahlungsmethode anzubieten. |
| **Erlaubte Kundengruppen** | (Wählen Sie relevante Gruppen aus) | **Was diese Einstellung bewirkt:** Bestimmt, welche Kundengruppen die Option „Zahlungsaufschub“ sehen und nutzen können.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn ausgewählt:* Nur Kunden, die zu den ausgewählten Gruppen gehören, sehen „Zahlungsaufschub“ beim Checkout.   *Wenn nicht ausgewählt:* Kunden in nicht ausgewählten Gruppen sehen diese Option nicht.   **Empfohlener Wert:** Wählen Sie spezifische Gruppen aus (z. B. „Großhändler“, „VIP-Kunden“). Vermeiden Sie „Alle Kunden“, es sei denn, Sie möchten jedem Zahlungsaufschub anbieten.   **Händlerszenario:** Sie haben eine Gruppe „B2B-Kunden“. Wählen Sie nur diese Gruppe aus, damit nur Ihre Geschäftskunden den Zahlungsaufschub nutzen können. |
| **Zahlungsfälligkeitstage** | 30 | **Was diese Einstellung bewirkt:** Definiert die Anzahl der Tage nach einer Bestellung, bis die Zahlung fällig ist.   **Auswirkung der Änderung dieser Einstellung:** Dieser Wert wird verwendet, um das dem Kunden angezeigte Zahlungsfälligkeitsdatum und für die interne Nachverfolgung zu berechnen.   **Empfohlener Wert:** 30 (üblich für Netto-30-Tage-Fristen), 7, 14, 60 usw., abhängig von Ihrer Geschäftsrichtlinie.   **Händlerszenario:** Auf 30 setzen für „Netto 30“-Zahlungsbedingungen. |
| **Mindestbestellwert für Zahlungsaufschub** | 0.00 | **Was diese Einstellung bewirkt:** Legt einen Mindestbestellwert (in Ihrer Standardwährung) fest, den eine Bestellung erreichen muss, um für den Zahlungsaufschub in Frage zu kommen.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn der Bestellwert unter diesem Wert liegt:* Zahlungsaufschub ist nicht verfügbar, auch nicht für berechtigte Kundengruppen.   *Wenn der Bestellwert über oder gleich diesem Wert liegt:* Zahlungsaufschub ist verfügbar (wenn andere Bedingungen erfüllt sind).   **Empfohlener Wert:** 0.00 (kein Minimum) oder ein spezifischer Wert (z. B. 100.00 für B2B).   **Händlerszenario:** Sie möchten Zahlungsaufschub nur für große Bestellungen anbieten, daher setzen Sie ihn auf 500.00. |
| **Bestellstatus für Zahlungsaufschub** | Wartet auf Zahlungsaufschub | **Was diese Einstellung bewirkt:** Legt den anfänglichen Bestellstatus fest, der Bestellungen zugewiesen wird, die mit der Methode „Zahlungsaufschub“ aufgegeben wurden.   **Auswirkung der Änderung dieser Einstellung:** Dieser Status ist in Ihrer Back Office-Bestellliste und für den Kunden in seiner Bestellhistorie sichtbar. Er hilft Ihnen, Bestellungen, die auf Zahlung warten, schnell zu identifizieren.   **Empfohlener Wert:** Erstellen Sie einen spezifischen Status wie „Wartet auf Zahlungsaufschub“ oder „Zahlung fällig“ unter **Bestellstatus** (Back Office > Shop-Parameter > Bestell-Einstellungen > Status) und wählen Sie ihn hier aus.   **Händlerszenario:** Sie möchten einen klaren Status, um diese Bestellungen von „Wartet auf Banküberweisung“ oder „Zahlung akzeptiert“ zu unterscheiden. |
| **Cron Job URL** | (Angezeigte URL) | **Was diese Einstellung bewirkt:** Diese URL wird verwendet, um automatisierte Aufgaben im Zusammenhang mit Zahlungsaufschüben auszulösen (z. B. Überprüfung von Fälligkeitsterminen, Senden von Erinnerungen, falls solche Funktionen implementiert oder erweitert sind).   **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Sie sollten einen Cron-Job auf Ihrem Server einrichten, um diese URL regelmäßig (z. B. einmal täglich) aufzurufen.   **Empfohlener Wert:** Kopieren Sie diese URL und fügen Sie sie dem Cron-Job-Scheduler Ihres Servers hinzu.   **Händlerszenario:** Sie möchten alle Hintergrundprozesse des Moduls automatisieren, wie z. B. das Aktualisieren von Bestellstatus oder das Senden von Benachrichtigungen. |

#### Zielprodukte (Spezifische Produktberechtigung)

Dieser Abschnitt ermöglicht es Ihnen, den Zahlungsaufschub auf bestimmte Produkte oder Kategorien zu beschränken.

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Nur auf bestimmte Produkte anwenden** | NEIN | **Was diese Einstellung bewirkt:** Bestimmt, ob die Zahlungsaufschuboption auf Bestellungen beschränkt ist, die nur bestimmte Produkte enthalten.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Die Option „Zahlungsaufschub“ wird nur beim Checkout angezeigt, wenn *alle* Produkte im Warenkorb auf Ihrer genehmigten Liste stehen.   *Wenn deaktiviert:* Das Modul wird basierend auf Kundengruppen und Mindestbestellwert angewendet, unabhängig von spezifischen Produkten.   **Empfohlener Wert:** NEIN (für den allgemeinen Gebrauch) oder JA (für sehr spezifische Szenarien).   **Händlerszenario:** Sie bieten Zahlungsaufschub nur für Ihre hochwertigen „Premium-Dienstleistungen“-Produkte an. Sie aktivieren dies und fügen diese Produkte unten hinzu. |
| **Für Zahlungsaufschub erlaubte Produkte** | (Leer) | **Was diese Einstellung bewirkt:** Wenn „Nur auf bestimmte Produkte anwenden“ aktiviert ist, können Sie in diesem Feld nach bestimmten Produkten suchen und diese hinzufügen.   **Auswirkung der Änderung dieser Einstellung:** Nur Bestellungen, die diese Produkte (und keine anderen) enthalten, sind für den Zahlungsaufschub berechtigt.   **Empfohlener Wert:** Fügen Sie relevante Produkte hinzu, wenn „Nur auf bestimmte Produkte anwenden“ auf JA steht.   **Händlerszenario:** Sie fügen „Produkt A“ und „Produkt B“ hinzu. Wenn der Warenkorb eines Kunden „Produkt A“ und „Produkt C“ enthält, ist der Zahlungsaufschub nicht verfügbar. Wenn er nur „Produkt A“ enthält, ist er verfügbar. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul fügt Ihrem PrestaShop Back Office-Menü mehrere neue Abschnitte hinzu, um Zahlungsaufschübe zu verwalten.

#### 2.2.1 Zahlungsaufschub-Benutzer (Back Office > Zahlungsaufschub > Zahlungsaufschub-Benutzer)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Kundenberechtigungen für den Zahlungsaufschub zu verwalten, wobei die Kundengruppeneinstellungen überschrieben oder ergänzt werden.

- **Bildschirmname & Menüpfad:** Back Office > Zahlungsaufschub > Zahlungsaufschub-Benutzer
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Zeigt eine Liste von Kunden an, denen der Zugang zum Zahlungsaufschub speziell gewährt oder verweigert wurde.
  - **Neu hinzufügen / Benutzer bearbeiten:**
    - **Kundensuche:** Finden Sie einen bestimmten Kunden nach Name oder E-Mail.
    - **Zahlungsaufschub aktivieren:** JA/NEIN-Schalter, um diesem einzelnen Kunden den Zugang zum Zahlungsaufschub zu gewähren oder zu entziehen.
    - **Zahlungsfälligkeitstage (Überschreiben):** Optional eine benutzerdefinierte Anzahl von Zahlungsfälligkeitstagen für diesen spezifischen Kunden festlegen, die die globale Einstellung überschreibt.
    - **Kreditlimit:** Legen Sie einen maximalen ausstehenden Betrag (in Ihrer Standardwährung, basierend auf `PS_CURRENCY_DEFAULT`) fest, den dieser Kunde für Bestellungen mit Zahlungsaufschub haben kann.
  - **Auswirkung von Änderungen:**
    - Das Hinzufügen eines Kunden und das Aktivieren des Zahlungsaufschubs gewährt ihm Zugang, auch wenn seine Gruppe in der Hauptmodulkonfiguration nicht ausgewählt ist.
    - Das Deaktivieren für einen Kunden entzieht ihm den Zugang, auch wenn seine Gruppe ausgewählt ist.
    - Benutzerdefinierte Fälligkeitstage und Kreditlimits gelten nur für diesen spezifischen Kunden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Verwenden Sie diesen Abschnitt, um einzelnen VIP-Kunden spezielle Zahlungsaufschubbedingungen zu gewähren oder problematische Kunden zu blockieren.
  2. Überprüfen Sie regelmäßig die Kreditlimits für Vielnutzer des Zahlungsaufschubs.

#### 2.2.2 Zahlungsaufschub-Aktivitätsprotokoll (Back Office > Zahlungsaufschub > Aktivitätsprotokoll)

Dieser Bildschirm bietet eine historische Aufzeichnung von Aktionen und Ereignissen im Zusammenhang mit Zahlungsaufschüben.

- **Bildschirmname & Menüpfad:** Back Office > Zahlungsaufschub > Aktivitätsprotokoll
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Zeigt ein Protokoll von Ereignissen an, das Folgendes umfassen könnte:
    - Wann eine Bestellung mit Zahlungsaufschub aufgegeben wurde.
    - Wann eine Zahlung als empfangen markiert wurde.
    - Änderungen an den Benutzereinstellungen für den Zahlungsaufschub.
    - Cron-Job-Ausführungen.
  - **Spalten:** Typischerweise Datum/Uhrzeit, Ereignistyp, zugehörige Bestellung/Kunde, Beschreibung.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschütztes Protokoll. Sie können Einträge hier nicht direkt ändern, aber es bietet wertvolle Einblicke für Audits und Fehlerbehebung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie das Protokoll regelmäßig, um die Aktivität des Zahlungsaufschubs zu überwachen und sicherzustellen, dass alles reibungslos läuft.
  2. Verwenden Sie es, um von Kunden gemeldete Probleme bezüglich ihrer Bestellungen mit Zahlungsaufschub zu untersuchen.

#### 2.2.3 Dashboard (Back Office > Zahlungsaufschub > Dashboard)

Dieser Bildschirm (wahrscheinlich dargestellt durch `defpay/controllers/admin/index.php`) würde typischerweise eine Übersicht oder Zusammenfassung der Zahlungsaufschubaktivitäten bieten.

- **Bildschirmname & Menüpfad:** Back Office > Zahlungsaufschub > Dashboard (oder Hauptmenüpunkt „Zahlungsaufschub“)
- **Verfügbare Aktionen & Einstellungen:**
  - **Raster- / Verwaltungsansicht:** Dieser Bildschirm präsentiert wahrscheinlich wichtige Statistiken, ausstehende Zahlungen, überfällige Zahlungen oder eine schnelle Zusammenfassung der Bestellungen mit Zahlungsaufschub. Er könnte Filter- oder Suchfunktionen bieten.
- **Auswirkung von Änderungen:** Dies ist hauptsächlich ein Informations-Dashboard. Alle vorgenommenen Aktionen (z. B. das Markieren einer Bestellung als bezahlt) würden typischerweise zur spezifischen Bestellseite oder einem anderen Verwaltungsbildschirm weiterleiten.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Verwenden Sie dies als Ihre primäre Übersicht, um schnell Bestellungen zu identifizieren, die Aufmerksamkeit erfordern (z. B. sich nähernde Fälligkeitstermine, überfällige Zahlungen).
  2. Überwachen Sie den allgemeinen Zustand Ihres Zahlungsaufschubsystems.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|
| **Modulkonfiguration** | Zahlungsaufschub aktivieren | JA | Hauptschalter für die Zahlungsmethode. |
| | Erlaubte Kundengruppen | (Wählen Sie relevante Gruppen aus) | Beschränkt den Zugang auf bestimmte Kundensegmente. |
| | Zahlungsfälligkeitstage | 30 | Legt die Standardzahlungsfrist in Tagen fest. |
| | Mindestbestellwert für Zahlungsaufschub | 0.00 | Mindestwarenkorbwert für die Berechtigung zum Zahlungsaufschub. |
| | Bestellstatus für Zahlungsaufschub | Wartet auf Zahlungsaufschub | Initialer Status für Bestellungen, die mit dieser Methode aufgegeben wurden. |
| | Cron Job URL | (Angezeigte URL) | URL für serverseitige Automatisierungsaufgaben. |
| | Nur auf bestimmte Produkte anwenden | NEIN | Beschränkt den Zahlungsaufschub auf bestimmte Produkte. |
| | Für Zahlungsaufschub erlaubte Produkte | (Leer) | Liste der berechtigten Produkte, wenn „Nur auf bestimmte Produkte anwenden“ auf JA steht. |
| **Zahlungsaufschub-Benutzer** | Kundensuche | N/A | Individuellen Kundenzugang finden und verwalten. |
| | Zahlungsaufschub aktivieren (pro Benutzer) | JA/NEIN | Individuelle Überschreibung für den Zahlungsaufschubzugang. |
| | Zahlungsfälligkeitstage (Überschreiben) | (Leer für global) | Benutzerdefinierte Zahlungsbedingungen für einen bestimmten Kunden. |
| | Kreditlimit | (Leer für kein Limit) | Maximaler ausstehender Betrag für einen bestimmten Kunden. |
| **Aktivitätsprotokoll** | N/A | N/A | Schreibgeschütztes Protokoll der Zahlungsaufschubereignisse. |
| **Dashboard** | N/A | N/A | Übersicht über Zahlungsaufschubbestellungen und Statistiken. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Warum wird der Zahlungsaufschub meinen Kunden beim Checkout nicht angezeigt?**
A:

1. **Ist das Modul aktiviert?** Überprüfen Sie „Zahlungsaufschub aktivieren“ in der Modulkonfiguration.
2. **Sind die Kundengruppen korrekt?** Stellen Sie sicher, dass der Kunde angemeldet ist und zu einer der in den Moduleinstellungen ausgewählten „Erlaubten Kundengruppen“ gehört.
3. **Mindestbestellwert:** Liegt der Warenkorbwert über dem „Mindestbestellwert für Zahlungsaufschub“?
4. **Spezifische Produkte:** Wenn „Nur auf bestimmte Produkte anwenden“ aktiviert ist, enthält der Warenkorb *nur* Produkte aus Ihrer genehmigten Liste?
5. **Individuelle Benutzereinstellungen:** Überprüfen Sie „Zahlungsaufschub-Benutzer“, um festzustellen, ob der Kunde individuell deaktiviert wurde oder spezifische Überschreibungen hat.
6. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung) und Ihren Browser-Cache.

**F: Wie ändere ich den Bestellstatus, sobald eine aufgeschobene Zahlung eingegangen ist?**
A: Sie müssen den Bestellstatus manuell im PrestaShop Back Office aktualisieren. Gehen Sie zu **Bestellungen > Bestellungen**, suchen Sie die entsprechende Bestellung und ändern Sie ihren Status von „Wartet auf Zahlungsaufschub“ (oder was auch immer Sie konfiguriert haben) auf „Zahlung akzeptiert“ oder „Geliefert“, je nach Bedarf.

**F: Kann ich unterschiedliche Zahlungsfälligkeitstage für verschiedene Kunden festlegen?**
A: Ja! Verwenden Sie den Bildschirm „Zahlungsaufschub-Benutzer“. Sie können nach einem bestimmten Kunden suchen und für diesen eine benutzerdefinierte „Zahlungsfälligkeitstage (Überschreiben)“ festlegen, die Vorrang vor der globalen Einstellung hat.

**F: Wofür ist die Cron Job URL und muss ich sie einrichten?**
A: Die Cron Job URL ist für automatisierte Aufgaben, die das Modul im Hintergrund ausführen könnte (z. B. Überprüfung überfälliger Zahlungen, Senden von Benachrichtigungen, falls implementiert). Obwohl das Modul für die grundlegende Zahlungsabwicklung auch ohne sie funktionieren könnte, wird dringend empfohlen, sie auf Ihrem Server einzurichten, um sicherzustellen, dass alle automatisierten Funktionen korrekt funktionieren. Ihr Webhost oder ein Entwickler kann Ihnen helfen, einen Cron-Job einzurichten, der diese URL täglich aufruft.

**F: Das Modul ist installiert, aber ich sehe den Menüpunkt „Zahlungsaufschub“ im Back Office nicht.**
A:

1. **Berechtigungen:** Überprüfen Sie Ihre Mitarbeiterberechtigungen (Erweiterte Parameter > Team > Mitarbeiter > Ihr Profil bearbeiten > Berechtigungen-Tab). Stellen Sie sicher, dass Sie Zugriff auf das Modul „Zahlungsaufschub“ und die zugehörigen Admin-Controller haben.
2. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Zahlungsaufschub“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Zahlungsaufschub“ folgt dem Standard-MVC-Muster (Model-View-Controller) von PrestaShop. Es integriert sich als Zahlungsmodul, erweitert `PaymentModule` und bietet benutzerdefinierte Admin-Controller zur Verwaltung von Zahlungsaufschub-Benutzern und -Protokollen. Es nutzt das PrestaShop-Konfigurationssystem für Einstellungen und Hooks für die Front-Office-Anzeige und die Back-Office-Bestellintegration. Das Modul führt benutzerdefinierte Datenbanktabellen (`defpay_log`, `defpayuser`) ein, um spezifische Zahlungsaufschubdaten zu speichern.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `defpay/controllers/front/cron.php`
  - **Klassenname:** `DefPayCronModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Verwaltet die Ausführung von Cron-Job-Aufgaben. Dieser Controller wird über die in der Modulkonfiguration angegebene `Cron Job URL` aufgerufen. Er ist so konzipiert, dass er regelmäßig von einem serverseitigen Cron-Scheduler aufgerufen wird, um Hintergrundoperationen wie die Überprüfung von Zahlungsfälligkeitsterminen, die Aktualisierung von Bestellstatus oder das Auslösen von Benachrichtigungen durchzuführen.
- `defpay/controllers/front/index.php`
  - **Klassenname:** `DefPayIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Ein Platzhalter oder Standard-Front-Controller. Wird oft für grundlegendes Modul-Routing verwendet oder wenn das Modul einen Standard-Front-Office-Einstiegspunkt benötigt, der nicht direkt einer bestimmten Aktion entspricht. In diesem Modul hat er möglicherweise keine direkte benutzerorientierte Funktion.
- `defpay/controllers/front/statement.php`
  - **Klassenname:** `DefPayStatementModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Verwaltet wahrscheinlich die Anzeige oder Generierung von Zahlungsaufschub-Abrechnungen für Kunden. Dies könnte eine Seite im Kundenkontobereich sein, die ausstehende Zahlungen anzeigt, oder ein Link zum Herunterladen einer Rechnung.
- `defpay/controllers/front/validation.php`
  - **Klassenname:** `DefPayValidationModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Der Kern-Zahlungsvalidierungs-Controller. Wenn ein Kunde beim Checkout „Zahlungsaufschub“ auswählt und die Bestellung bestätigt, verarbeitet dieser Controller die Bestellung, setzt den entsprechenden Bestellstatus und leitet den Kunden zur Bestellbestätigungsseite weiter.

#### Back-Office-Admin-Controller

- `defpay/controllers/admin/AdminDefPayActivityLog.php`
  - **Klassenname:** `AdminDefPayActivityLogController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** `Zahlungsaufschub-Aktivitätsprotokoll`
  - **Verwaltete Entität:** `defpay_log` (benutzerdefinierte Datenbanktabelle)
  - **Verantwortlichkeit:** Bietet eine Listenverwaltungsoberfläche für die Tabelle `defpay_log`. Zeigt eine historische Aufzeichnung von Ereignissen im Zusammenhang mit Zahlungsaufschüben an, wie z. B. Bestellungen, Statusänderungen oder Cron-Job-Aktionen.
- `defpay/controllers/admin/AdminDefPayUsers.php`
  - **Klassenname:** `AdminDefPayUsersController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** `Zahlungsaufschub-Benutzer`
  - **Verwaltete Entität:** `defpayuser` (benutzerdefinierte Datenbanktabelle)
  - **Verantwortlichkeit:** Verwaltet individuelle Kundeneinstellungen für den Zahlungsaufschub. Ermöglicht Administratoren, den Zahlungsaufschub für bestimmte Kunden zu aktivieren/deaktivieren, benutzerdefinierte Fälligkeitstage festzulegen und Kreditlimits zu definieren. Interagiert mit der Tabelle `ps_currency` (über `PS_CURRENCY_DEFAULT`) für die Kreditlimitwährung.
- `defpay/controllers/admin/index.php`
  - **Klassenname:** `AdminDefPayDashboardController` (wahrscheinlich, erweitert `ModuleAdminController`)
  - **Tab-Name:** `Zahlungsaufschub-Dashboard` (oder Hauptmenüpunkt)
  - **Verwaltete Entität:** Keine direkte einzelne Entität; aggregiert Daten.
  - **Verantwortlichkeit:** Dient als Haupt-Dashboard oder Übersicht für das Modul „Zahlungsaufschub“ im Back Office. Es zeigt wahrscheinlich wichtige Statistiken, Zusammenfassungen ausstehender/überfälliger Zahlungen und schnelle Links zu anderen Verwaltungsbereichen an.

### 4.3 Kernklassen & Modelle (`classes/`)

Die bereitgestellten Modulinformationen zeigen keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass die Kernlogik des Moduls, einschließlich der `ObjectModel`-Definitionen für `defpay_log` und `defpayuser`, direkt in der Hauptdatei `defpay/cronjob.php` oder in den Admin-Controllern selbst eingebettet sein könnte. Dies ist ein weniger verbreiteter, aber manchmal verwendeter Ansatz für einfachere Module.

Wenn `defpay_log` und `defpayuser` tatsächlich benutzerdefinierte Tabellen sind, würden ihre `ObjectModel`-Definitionen (z. B. `DefPayLog`- und `DefPayUser`-Klassen) typischerweise in `classes/` gefunden werden. Andernfalls werden sie wahrscheinlich inline definiert oder direkt über `Db`-Klassenaufrufe verwaltet.

### 4.4 JavaScript-Assets (`views/js/`)

- `defpay/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Bietet wahrscheinlich Funktionen zur Verwaltung von E-Mail-Vorlagen innerhalb der Modulkonfiguration oder spezifischer Admin-Bildschirme. Dies könnte dynamische Formularfelder, das Vorschauen von Vorlagen oder das Speichern von Vorlageninhalten umfassen.
- `defpay/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (z. B. `AdminDefPayUsers` für die Kundensuche oder Modulkonfiguration für die Produktsuche).
  - **Beschreibung:** Implementiert eine Autocomplete-Funktion für Suchfelder, wie z. B. das Finden von Kunden oder Produkten. Es lauscht auf Benutzereingaben, führt AJAX-Aufrufe durch, um Vorschläge abzurufen, und zeigt diese in einem Dropdown an.
- `defpay/tools/browser-demo-simulator.js`
  - **Geltungsbereich:** Potenziell beides, aber wahrscheinlicher für Entwicklung/Tests.
  - **Beschreibung:** Ein Dienstprogramm-Skript, möglicherweise zur Simulation von Browserverhalten oder Modulinteraktionen zu Testzwecken. Wird normalerweise nicht in einer Produktionsumgebung verwendet.
- `defpay/views/js/adminDefPayActivityPreview.js`
  - **Geltungsbereich:** Back-Office (`AdminDefPayActivityLog`).
  - **Beschreibung:** Bietet interaktive Funktionen für das Aktivitätsprotokoll, wie z. B. das Erweitern von Protokolleinträgen, Filtern oder das Vorschauen von Details einer Aktivität.
- `defpay/views/js/adminDefPayCollections.js`
  - **Geltungsbereich:** Back-Office (wahrscheinlich im Zusammenhang mit der Verwaltung von Zahlungsaufschub-Inkasso).
  - **Beschreibung:** Implementiert JavaScript-Logik für eine „Inkasso“-Verwaltungsoberfläche, die das Markieren von Zahlungen als empfangen, das Senden von Erinnerungen oder die Verwaltung überfälliger Konten umfassen könnte.
- `defpay/views/js/adminDefPayDashboard.js`
  - **Geltungsbereich:** Back-Office (Dashboard).
  - **Beschreibung:** Treibt die interaktiven Elemente des Zahlungsaufschub-Dashboards an, wie z. B. dynamische Diagramme, Datenfilterung oder AJAX-Updates für Statistiken.
- `defpay/views/js/adminDefPayPortfolio.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Wahrscheinlich im Zusammenhang mit der Verwaltung eines „Portfolios“ von Zahlungsaufschub-Konten oder -Bestellungen, möglicherweise mit erweiterten Filter-, Berichts- oder Massenaktionen.
- `defpay/views/js/defpay_target_products.js`
  - **Geltungsbereich:** Back-Office (Modulkonfiguration).
  - **Beschreibung:** Bietet die JavaScript-Funktionalität für den Abschnitt „Zielprodukte“ in der Modulkonfiguration, der die Produktsuche, -auswahl und -entfernung für die Zahlungsaufschubberechtigung ermöglicht.

### 4.5 CSS-Stylesheets (`views/css/`)

- `defpay/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Stile für die E-Mail-Vorlagenverwaltungsoberfläche, die ein konsistentes Erscheinungsbild innerhalb des PrestaShop-Admin-Panels gewährleisten.
- `defpay/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Stile für die Autocomplete-Suchvorschläge, die sicherstellen, dass sie visuell unterscheidbar und benutzerfreundlich sind.
- `defpay/views/css/admin_defpay.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Allgemeine Stile für die benutzerdefinierten Admin-Bildschirme des Moduls (Dashboard, Benutzer, Aktivitätsprotokoll), die ein kohärentes Design innerhalb des PrestaShop Back Office gewährleisten.
- `defpay/views/css/defpay.css`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Allgemeine Stile für die Front-Office-Komponenten des Moduls, wie z. B. die Anzeige der Zahlungsoption auf der Checkout-Seite oder in den Kundenkontobereichen.
- `defpay/views/css/statement-document.css`
  - **Geltungsbereich:** Front-Office (für Druck/PDF).
  - **Beschreibung:** Spezifische Stile für die druckbare oder PDF-Version einer Zahlungsaufschub-Abrechnung, optimiert für das Dokumentenlayout.
- `defpay/views/css/statement.css`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Stile für die Bildschirmanzeige von Zahlungsaufschub-Abrechnungen im Kundenkontobereich.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

- `defpay/views/templates/hook/confirmation.tpl`
  - **Hook:** `displayOrderConfirmation` (oder ähnlich).
  - **Ausgabe:** Inhalt, der auf der Bestellbestätigungsseite angezeigt wird, nachdem eine Bestellung mit Zahlungsaufschub aufgegeben wurde, um den Kunden über die Zahlungsbedingungen zu informieren.
- `defpay/views/templates/hook/displayAdminOrder16.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.6).
  - **Ausgabe:** Fügt einen Informations- oder Aktionsblock zum Zahlungsaufschub auf der Bestelldetailseite im PrestaShop 1.6 Back Office hinzu.
- `defpay/views/templates/hook/displayAdminOrder17.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.7+).
  - **Ausgabe:** Ähnlich wie `displayAdminOrder16.tpl`, aber angepasst für die PrestaShop 1.7+ Back Office Bestelldetailseite, zeigt den Zahlungsaufschubstatus, das Fälligkeitsdatum und möglicherweise Zahlungsinkassoaktionen an.
- `defpay/views/templates/hook/displayCustomerAccount.tpl`
  - **Hook:** `displayCustomerAccount` oder `displayMyAccountBlock`.
  - **Ausgabe:** Fügt einen Link oder Block zur Seite „Mein Konto“ des Kunden hinzu, der möglicherweise auf seine Zahlungsaufschub-Abrechnung oder -Historie verweist.
- `defpay/views/templates/hook/displayOrderDetail.tpl`
  - **Hook:** `displayOrderDetail` (Front-Office).
  - **Ausgabe:** Zeigt Zahlungsaufschub-spezifische Informationen (z. B. Fälligkeitsdatum, Zahlungsstatus) auf der Front-Office-Bestelldetailseite des Kunden an.
- `defpay/views/templates/hook/payment.tpl`
  - **Hook:** `displayPayment` (oder `paymentOptions` für PS 1.7+).
  - **Ausgabe:** Rendert die Option „Zahlungsaufschub“ auf der Checkout-Zahlungsauswahlseite.

#### Admin-Vorlagen (`views/templates/admin/`)

- `defpay/views/templates/admin/cron_setup.tpl`
  - **Zweck:** Wahrscheinlich auf der Hauptkonfigurationsseite des Moduls (`getContent()`) verwendet, um die Cron Job URL und Anweisungen anzuzeigen.
- `defpay/views/templates/admin/defpay_target_products.tpl`
  - **Zweck:** Rendert die Oberfläche zur Auswahl spezifischer Produkte, die für den Zahlungsaufschub in der Modulkonfiguration berechtigt sind.

#### Front-Office-Vorlagen (`views/templates/front/`)

- `defpay/views/templates/front/statement_preview.tpl`
  - **Zweck:** Zeigt dem Kunden im Front Office eine Vorschau einer Zahlungsaufschub-Abrechnung an.
- `defpay/views/templates/front/validation.tpl`
  - **Zweck:** Die Vorlage, die vom `validation.php`-Front-Controller gerendert wird, typischerweise eine Bestätigungsnachricht oder eine Zusammenfassung, nachdem eine Bestellung mit Zahlungsaufschub erfolgreich aufgegeben wurde.

#### PDF-Vorlagen (`views/templates/pdf/`)

- `defpay/views/templates/pdf/statement.tpl`
  - **Zweck:** Vorlage zur Generierung einer PDF-Version einer Zahlungsaufschub-Abrechnung oder -Rechnung.

#### Bibliotheksvorlagen (`defpay/lib/emailTemplatesManager/views/` & `defpay/lib/searchTool/views/`)

Diese Vorlagen sind Teil eingebetteter Bibliotheken innerhalb des Moduls:

- `defpay/lib/emailTemplatesManager/views/buttonManager.tpl`
- `defpay/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/mainForm.tpl`
- `defpay/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Zweck:** Diese Vorlagen werden verwendet, um die verschiedenen Komponenten der E-Mail-Vorlagenverwaltungsoberfläche im Back Office zu rendern.
- `defpay/lib/searchTool/views/scripts.tpl`
  - **Zweck:** Enthält wahrscheinlich JavaScript-Initialisierung oder -Konfiguration für das Autocomplete-Suchwerkzeug.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_defpay_log` (oder `defpay_log`):
  - Speichert Aktivitätsprotokolleinträge im Zusammenhang mit Zahlungsaufschüben.
  - Felder umfassen wahrscheinlich: `id_defpay_log`, `id_order`, `id_customer`, `event_type`, `description`, `date_add`.
- `ps_defpayuser` (oder `defpayuser`):
  - Speichert individuelle Zahlungsaufschub-Einstellungen für Kunden.
  - Felder umfassen wahrscheinlich: `id_defpayuser`, `id_customer`, `deferred_payment_enabled` (boolean), `payment_due_days_override` (int), `credit_limit` (decimal), `date_add`, `date_upd`.
- `ps_configuration`:
  - Moduleinstellungen werden hier mit Schlüsseln wie `DEFPAY_ENABLED`, `DEFPAY_GROUPS`, `DEFPAY_DUE_DAYS`, `DEFPAY_MIN_TOTAL`, `DEFPAY_ORDER_STATUS`, `DEFPAY_CRON_URL`, `DEFPAY_TARGET_PRODUCTS_ENABLED`, `DEFPAY_TARGET_PRODUCTS_LIST` gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayPayment` (PS 1.6) | Im Zahlungsauswahlschritt des Checkouts. | Rendert die Option „Zahlungsaufschub“. |
| `paymentOptions` (PS 1.7+) | Im Zahlungsauswahlschritt des Checkouts. | Rendert die Option „Zahlungsaufschub“ (moderner Hook). |
| `displayOrderConfirmation` | Nachdem eine Bestellung erfolgreich aufgegeben wurde. | Zeigt Zahlungsaufschubdetails auf der Bestätigungsseite an. |
| `displayCustomerAccount` / `displayMyAccountBlock` | Auf der Seite „Mein Konto“ des Kunden. | Fügt einen Link zu Zahlungsaufschub-Abrechnungen oder -Historie hinzu. |
| `displayOrderDetail` | Auf der Front-Office-Bestelldetailseite des Kunden. | Zeigt Zahlungsaufschub-spezifische Informationen für eine Bestellung an. |
| `displayAdminOrder` (PS 1.6) | Auf der Bestelldetailseite im Back Office (PS 1.6). | Fügt Zahlungsaufschubstatus und Verwaltungstools ein. |
| `displayAdminOrder` (PS 1.7+) | Auf der Bestelldetailseite im Back Office (PS 1.7+). | Fügt Zahlungsaufschubstatus und Verwaltungstools ein. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird verwendet, um Aktionen wie das Festlegen des anfänglichen Zahlungsaufschub-Bestellstatus, das Protokollieren des Ereignisses oder das Erstellen eines `defpayuser`-Eintrags bei Bedarf durchzuführen. |
| `actionOrderStatusUpdate` | Wenn der Status einer Bestellung geändert wird. | Kann verwendet werden, um Aktionen basierend auf Statusänderungen auszulösen (z. B. Zahlung erhalten, überfällig). |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert. | Wird verwendet, um Front-Office-CSS- und JS-Assets in die Warteschlange zu stellen. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ausgabe rendert. | Wird verwendet, um Back-Office-CSS- und JS-Assets in die Warteschlange zu stellen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Dort finden Sie Ihre gekauften Module und Zugang zu unseren Support-Kanälen.
