---
title: "Quote Enterprise - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Quote Enterprise von MyPresta.eu."
sidebar:
  label: "Quote Enterprise - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Quote Enterprise auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/quote-enterprise/)
>
> ---


# Quote Enterprise

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich. Stellen Sie sicher, dass Ihr Server die Mindestanforderungen von PrestaShop erfüllt.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Quote Enterprise)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten und das Erscheinungsbild des Moduls Quote Enterprise definieren.

#### Registerkarte Allgemeine Einstellungen

- **Quote Enterprise aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Angebotssystem wird in Ihrem Shop aktiv, und Kunden können Angebote anfordern.
    - *Wenn deaktiviert:* Die gesamte Angebotsfunktionalität wird im Front Office ausgeblendet, und es können keine neuen Angebote angefordert werden. Bestehende Angebote im Back Office bleiben zur Verwaltung zugänglich.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, wenn Sie bereit sind, Angebotsdienste anzubieten. Deaktivieren Sie es vorübergehend während der Wartung oder wenn Sie sich entscheiden, keine Angebote mehr anzubieten.
- **Angebotsanfragen aus dem Warenkorb zulassen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden ihren gesamten Warenkorb in eine Angebotsanfrage umwandeln können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Schaltfläche oder ein Link „Angebot anfordern“ erscheint in der Warenkorbzusammenfassung, die es Kunden ermöglicht, alle Artikel in ihrem Warenkorb für ein Angebot einzureichen.
    - *Wenn deaktiviert:* Kunden können Angebote nur von einzelnen Produktseiten oder über die schwebende Schaltfläche (falls aktiviert) anfordern, nicht direkt aus ihrem Warenkorb.
  - **Empfohlener Wert:** JA (für die meisten B2B- und Großbestellungsszenarien)
  - **Händlerszenario / Beispiel:** Wenn Sie hauptsächlich mit großen, mehrteiligen Bestellungen zu tun haben, bei denen die Preise oft verhandelt werden, aktivieren Sie dies. Wenn Ihre Angebote normalerweise für einzelne, kundenspezifische Produkte gelten, können Sie dies deaktivieren.
- **Angebotsanfragen von der Produktseite zulassen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob eine Schaltfläche „Angebot anfordern“ auf einzelnen Produktseiten erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können ein bestimmtes Produkt direkt von seiner Seite zu einer Angebotsanfrage hinzufügen, anstatt es in den Warenkorb zu legen.
    - *Wenn deaktiviert:* Die Option zur Angebotsanfrage wird von den Produktseiten entfernt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Unerlässlich für kundenspezifische Produkte, hochwertige Artikel oder wenn Sie eine Alternative zum Direktkauf für jedes Produkt anbieten möchten.
- **Schwebende Angebots-Schaltfläche anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt eine dauerhafte, schwebende Schaltfläche zum Front Office Ihres Shops hinzu, die es Kunden ermöglicht, von fast jeder Seite aus eine Angebotsanfrage zu initiieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine kleine, anklickbare Schaltfläche (oft in einer Ecke des Bildschirms) erscheint, die das Angebotsanfrageformular oder eine Liste bestehender Angebote öffnet.
    - *Wenn deaktiviert:* Die schwebende Schaltfläche ist nicht sichtbar.
  - **Empfohlener Wert:** JA (für hohe Sichtbarkeit und einfachen Zugang)
  - **Händlerszenario / Beispiel:** Verwenden Sie dies, um die Angebotsoption in Ihrem gesamten Shop gut sichtbar zu machen und mehr Anfragen zu fördern.
- **Mindestbestellwert für Angebotsanfrage:**

  - **Was diese Einstellung bewirkt:** Legt einen Mindestgesamtwert (in Ihrer Standardwährung) fest, den eine Angebotsanfrage erreichen muss, um eingereicht zu werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert festgelegt ist (z. B. 100):* Kunden können keine Angebotsanfrage einreichen, wenn der Gesamtwert der Artikel in ihrer Anfrage unter diesem Betrag liegt. Eine Fehlermeldung wird angezeigt.
    - *Wenn auf 0 gesetzt oder leer gelassen:* Es wird kein Mindestwert erzwungen.
  - **Empfohlener Wert:** 0 (oder ein Wert, der triviale Anfragen herausfiltert)
  - **Händlerszenario / Beispiel:** Wenn Sie nur Angebote für bedeutende Bestellungen bearbeiten möchten, legen Sie einen Mindestwert fest (z. B. 500 €), um den Verwaltungsaufwand für kleine Anfragen zu reduzieren.
- **Standard-Angebotsgültigkeit (Tage):**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele Tage ein neu erstelltes Angebot standardmäßig gültig ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine Zahl festgelegt ist (z. B. 30):* Alle neuen Angebote, die von Ihrem Team erstellt werden, haben automatisch ein Ablaufdatum 30 Tage nach ihrer Erstellung.
    - *Wenn auf 0 gesetzt oder leer gelassen:* Angebote haben keine Standardgültigkeitsdauer, und Ihr Team muss diese manuell festlegen oder sie ohne Ablaufdatum verwalten.
  - **Empfohlener Wert:** 30 (oder ein für Ihre Branche typischer Zeitraum)
  - **Händlerszenario / Beispiel:** Eine Gültigkeit von 30 Tagen ermutigt Kunden, innerhalb eines angemessenen Zeitrahmens zu handeln, und schützt Sie vor Preisschwankungen.

#### Registerkarte E-Mail-Vorlagen

Dieser Abschnitt ermöglicht es Ihnen, die vom Modul gesendeten E-Mail-Benachrichtigungen anzupassen.

- **E-Mail-Vorlagen-Manager:**
  - **Was diese Einstellung bewirkt:** Bietet eine visuelle Oberfläche zum Bearbeiten des Inhalts verschiedener E-Mail-Vorlagen, die sich auf Angebote beziehen (z. B. neue Angebotsanfrage, Angebot aktualisiert, Angebot angenommen).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Sie eine Vorlage bearbeiten:* Die entsprechende E-Mail, die an Kunden oder Ihr Team gesendet wird, spiegelt Ihre Änderungen wider, einschließlich Text, Branding und Layout.
  - **Empfohlener Wert:** Anpassen, um Ihre Markenstimme widerzuspiegeln und klare Anweisungen zu geben.
  - **Händlerszenario / Beispiel:** Ändern Sie die E-Mail „Neue Angebotsanfrage“, um spezifische Anweisungen für Ihr Vertriebsteam aufzunehmen oder eine personalisierte Begrüßung für Kunden hinzuzufügen.

#### Registerkarte Erweiterte Einstellungen

- **REST API aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert eine programmatische Schnittstelle (API) für das Modul, die es externen Systemen oder benutzerdefinierten Anwendungen ermöglicht, mit Ihren Angeboten zu interagieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul stellt Endpunkte bereit, die von Entwicklern verwendet werden können, um Angebote programmatisch zu erstellen, zu lesen, zu aktualisieren und zu löschen.
    - *Wenn deaktiviert:* Die API ist inaktiv und kann nicht aufgerufen werden.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben spezifische Integrationsbedürfnisse)
  - **Händlerszenario / Beispiel:** Wenn Sie mit einem CRM, ERP oder einer benutzerdefinierten mobilen App integrieren, ermöglicht die Aktivierung der API diesen Systemen, Angebote in PrestaShop automatisch zu erstellen oder zu aktualisieren. Erfordert Entwicklerkenntnisse.
- **API-Schlüsselverwaltung:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Generieren und Verwalten von API-Schlüsseln, die für die Authentifizierung von Anfragen an die REST-API des Moduls erforderlich sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Sie einen Schlüssel erstellen:* Sie erhalten eine eindeutige Kennung, die externe Anwendungen verwenden müssen, um auf die API zuzugreifen.
    - *Wenn Sie einen Schlüssel widerrufen:* Jede Anwendung, die diesen Schlüssel verwendet, verliert den Zugriff auf die API.
  - **Empfohlener Wert:** Schlüssel nur bei Bedarf für spezifische Integrationen generieren.
  - **Händlerszenario / Beispiel:** Erstellen Sie einen neuen API-Schlüssel für Ihr CRM-System, um neue Leads als Angebotsanfragen in PrestaShop zu übertragen.
- **Cron-Job-URL für Ablauf & Digest:**

  - **Was diese Einstellung bewirkt:** Bietet eine URL, die bei Zugriff Hintergrundaufgaben wie die Überprüfung des Angebotsablaufs und das Senden täglicher Zusammenfassungen an Ihr Team auslöst.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf Ihrem Server konfiguriert:* Das Modul führt diese Aufgaben automatisch in regelmäßigen Abständen (z. B. täglich) aus, um sicherzustellen, dass Angebote als abgelaufen markiert werden und Ihr Team zeitnahe Zusammenfassungen erhält.
    - *Wenn nicht konfiguriert:* Ablaufprüfungen und Digest-E-Mails werden nicht automatisiert.
  - **Empfohlener Wert:** Konfigurieren Sie diese URL als täglichen Cron-Job auf Ihrem Hosting-Server.
  - **Händlerszenario / Beispiel:** Richten Sie einen Cron-Job ein, der diese URL einmal täglich ausführt, um sicherzustellen, dass Kunden über ablaufende Angebote benachrichtigt werden und Ihr Vertriebsteam eine tägliche Zusammenfassung neuer Anfragen erhält.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Angebotsverwaltung (Back Office > Quote Enterprise > Angebote)

Dies ist die zentrale Anlaufstelle für Ihr Vertriebsteam, um alle Angebotsanfragen zu verwalten.

- **Bildschirmname & Menüpfad:** **Quote Enterprise > Angebote**
- **Verfügbare Aktionen & Einstellungen:**
  - **Angebotslistentabelle:** Zeigt alle eingereichten Angebote mit wichtigen Informationen wie Kundennamen, Status, Gesamtwert und Erstellungsdatum an.
  - **Filtern & Suchen:** Tools zum Auffinden spezifischer Angebote nach Kunde, Status, Datumsbereich usw.
  - **Angebot anzeigen/bearbeiten:** Klicken Sie auf ein beliebiges Angebot, um eine detaillierte Ansicht zu öffnen, in der Sie:
    - **Produkte & Mengen anpassen:** Artikel, Mengen und Preise innerhalb des Angebots ändern.
    - **Produkte hinzufügen/entfernen:** Neue Produkte zum Angebot suchen und hinzufügen oder bestehende entfernen.
    - **Rabatte anwenden:** Spezifische Rabatte auf den Gesamtbetrag des Angebots oder einzelne Artikel anbieten.
    - **Gültigkeit festlegen:** Das Ablaufdatum für das Angebot definieren.
    - **Notizen/Nachrichten hinzufügen:** Direkt über die Angebots-Oberfläche mit dem Kunden kommunizieren.
    - **Status ändern:** Den Status des Angebots aktualisieren (z. B. Ausstehend, Gesendet, Angenommen, Abgelehnt, Abgelaufen).
    - **PDF generieren:** Eine professionelle PDF-Proforma-Rechnung für den Kunden erstellen.
    - **In Bestellung umwandeln:** Mit einem einzigen Klick ein angenommenes Angebot in eine Standard-PrestaShop-Bestellung umwandeln, bereit zum Checkout.
    - **E-Mail senden:** Aktualisierte Angebotsdetails oder Nachrichten an den Kunden senden.
  - **Massenaktionen:** Wählen Sie mehrere Angebote aus, um Aktionen wie Statusänderung, Löschen oder Exportieren durchzuführen.
- **Auswirkung von Änderungen:**
  - Das Ändern eines Angebots aktualisiert dessen Details in der Datenbank und kann E-Mail-Benachrichtigungen an den Kunden auslösen.
  - Die Umwandlung in eine Bestellung erstellt eine neue Bestellung im Standard-Bestellverwaltungssystem von PrestaShop, vorab ausgefüllt mit den angebotenen Artikeln und Preisen.
  - Das Ändern des Status aktualisiert die Kundenansicht in deren Konto und kann spezifische E-Mail-Vorlagen auslösen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie regelmäßig die Liste „Angebote“ auf neue „Ausstehende“ Anfragen.
  2. Öffnen Sie jede neue Anfrage, überprüfen Sie die Artikel, passen Sie Preise/Mengen bei Bedarf an und fügen Sie interne Notizen hinzu.
  3. Legen Sie eine Gültigkeitsdauer fest und generieren Sie eine PDF-Proforma-Rechnung.
  4. Ändern Sie den Status auf „Gesendet“ und senden Sie das Angebot per E-Mail an den Kunden.
  5. Verfolgen Sie „Gesendete“ Angebote. Wenn angenommen, in Bestellung umwandeln. Wenn abgelehnt oder abgelaufen, den Status entsprechend aktualisieren.

#### 2.2.2 Audit-Log (Back Office > Quote Enterprise > Audit-Log)

Dieser Bildschirm bietet eine detaillierte Historie aller an Angeboten durchgeführten Aktionen.

- **Bildschirmname & Menüpfad:** **Quote Enterprise > Audit-Log**
- **Verfügbare Aktionen & Einstellungen:**
  - **Protokolllistentabelle:** Zeigt eine chronologische Liste von Ereignissen im Zusammenhang mit Angeboten an, einschließlich wer die Aktion durchgeführt hat, welche Aktion durchgeführt wurde (z. B. „Angebot erstellt“, „Preis geändert“, „Status aktualisiert“) und wann sie stattgefunden hat.
  - **Filtern:** Filtern Sie das Protokoll nach Datum, Benutzer oder Aktionstyp, um spezifische Ereignisse zu finden.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschütztes Protokoll; Sie können hier keine Änderungen vornehmen. Es dient als historische Aufzeichnung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Verwenden Sie das Audit-Log, um Änderungen zu verfolgen, Probleme zu beheben oder die Teamaktivität bei Angeboten zu überprüfen. Es ist von unschätzbarem Wert für die Rechenschaftspflicht und das Verständnis des Lebenszyklus jedes Angebots.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Quote Enterprise aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
|  | Angebotsanfragen aus dem Warenkorb zulassen | JA | Fügt Angebots-Schaltfläche zur Warenkorbseite hinzu. |
|  | Angebotsanfragen von der Produktseite zulassen | JA | Fügt Angebots-Schaltfläche zu Produktseiten hinzu. |
|  | Schwebende Angebots-Schaltfläche anzeigen | JA | Zeigt eine dauerhafte Angebots-Schaltfläche im Front Office an. |
|  | Mindestbestellwert für Angebotsanfrage | 0 | Legt einen Mindestwert für Angebotsabgaben fest. |
|  | Standard-Angebotsgültigkeit (Tage) | 30 | Legt das Standardablaufdatum für neue Angebote fest. |
|  | E-Mail-Vorlagen-Manager | Anpassen | Bearbeiten Sie den E-Mail-Inhalt für verschiedene Angebotsereignisse. |
|  | REST API aktivieren | NEIN | Aktiviert die API für externe Integrationen (nur für Entwickler). |
|  | API-Schlüsselverwaltung | N/A | Verwalten Sie API-Schlüssel für sicheren API-Zugriff (nur für Entwickler). |
|  | Cron-Job-URL für Ablauf & Digest | Konfigurieren | Automatisiert Angebotsablaufprüfungen und Team-Zusammenfassungen. |
| **Angebotsverwaltung** | Angebotsliste | N/A | Alle Angebote anzeigen, filtern und verwalten. |
|  | Angebot anzeigen/bearbeiten | N/A | Artikel, Preise, Status anpassen, PDF generieren, in Bestellung umwandeln. |
|  | Massenaktionen | N/A | Aktionen auf mehrere ausgewählte Angebote anwenden. |
| **Audit-Log** | Protokollliste | N/A | Historische Aktionen zu allen Angeboten überprüfen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Schaltflächen „Angebot anfordern“ werden im Front Office nicht angezeigt.**
A:

1. **Modulstatus überprüfen:** Stellen Sie sicher, dass „Quote Enterprise aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
2. **Spezifische Einstellungen überprüfen:** Vergewissern Sie sich, dass „Angebotsanfragen aus dem Warenkorb zulassen“ und „Angebotsanfragen von der Produktseite zulassen“ bei Bedarf aktiviert sind.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie Ihren PrestaShop-Cache (Smarty-Cache, Dateisystem-Cache). Manchmal werden Änderungen erst nach dem Aktualisieren des Caches angezeigt.
4. **Theme-Kompatibilität:** Wenn Sie ein benutzerdefiniertes Theme verwenden, könnte es ein Kompatibilitätsproblem geben. Kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F: Kunden erhalten keine Angebotsbenachrichtigungs-E-Mails.**
A:

1. **E-Mail-Vorlagen überprüfen:** Gehen Sie in der Modulkonfiguration zur Registerkarte „E-Mail-Vorlagen“ und stellen Sie sicher, dass die Vorlagen korrekt konfiguriert und gespeichert sind.
2. **PrestaShop E-Mail-Einstellungen:** Überprüfen Sie Ihre allgemeinen PrestaShop-E-Mail-Einstellungen (SMTP, PHP-Mail) unter **Erweiterte Einstellungen > E-Mail**. Senden Sie von dort eine Test-E-Mail, um zu bestätigen, dass das Mailsystem Ihres Shops funktioniert.
3. **Spam-Ordner:** Weisen Sie Kunden an, ihre Spam- oder Junk-Ordner zu überprüfen.
4. **Cron-Job (für Digests/Erinnerungen):** Wenn es um Ablauferinnerungen oder tägliche Digests geht, stellen Sie sicher, dass die Cron-Job-URL auf Ihrem Server korrekt konfiguriert ist, um regelmäßig ausgeführt zu werden.

**F: Kann ich das Aussehen des Angebotsanfrageformulars oder der Schaltflächen anpassen?**
A: Ja, das Modul verwendet Standard-PrestaShop-Templates. Für grundlegende Stiländerungen (Farben, Schriftarten) können Sie oft das CSS des Moduls in der benutzerdefinierten CSS-Datei Ihres Themes überschreiben. Für komplexere Layoutänderungen müssten Sie die TPL-Dateien des Moduls in Ihrem Theme überschreiben. Dies erfordert in der Regel einen Webentwickler.

**F: Wie wandle ich ein angenommenes Angebot in eine reguläre Bestellung um?**
A: Navigieren Sie im PrestaShop Back Office zu **Quote Enterprise > Angebote**. Öffnen Sie das spezifische Angebot, das Sie umwandeln möchten. In der Detailansicht des Angebots finden Sie eine Schaltfläche (z. B. „In Bestellung umwandeln“ oder „Bestellung erstellen“). Durch Klicken darauf wird eine neue Bestellung in Ihrer Standard-PrestaShop-Bestellliste generiert, vorab ausgefüllt mit den angebotenen Artikeln und Preisen.

**F: Was passiert, wenn ein Angebot abläuft?**
A: Wenn der Cron-Job konfiguriert ist, markiert das Modul abgelaufene Angebote automatisch als „Abgelaufen“. Kunden können ein abgelaufenes Angebot nicht mehr annehmen oder in eine Bestellung umwandeln. Ihr Vertriebsteam kann abgelaufene Angebote weiterhin einsehen und bei Bedarf reaktivieren oder ein neues Angebot erstellen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Quote Enterprise folgt einer robusten PrestaShop MVC (Model-View-Controller)-Architektur und nutzt `ObjectModel` stark für die Datenpersistenz. Es integriert sich nahtlos in das Hook-System von PrestaShop für die Front-Office-Anzeige und Back-Office-Aktionen. Das Modul enthält dedizierte Admin-Controller zur Verwaltung von Angeboten und Audit-Logs, Front-Controller für die Kundeninteraktion (Anfrage, Liste, Ansicht, API) und eine umfassende Reihe von Hilfsklassen für Geschäftslogik, PDF-Generierung, E-Mail-Verwaltung und mehr. Eine REST-API wird auch für die Integration externer Systeme bereitgestellt.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/api.php`
  - Klassenname: `QuoteenterpriseApiModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Behandelt API-Anfragen vom Front-Office, wahrscheinlich für spezifische kundenorientierte Integrationen oder dynamisches Laden von Inhalten.
- `controllers/front/cron.php`
  - Klassenname: `QuoteenterpriseCronModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Dient als Endpunkt für den Cron-Job und löst Hintergrundaufgaben wie die Überprüfung des Angebotsablaufs und das Senden von Digest-E-Mails aus.
- `controllers/front/index.php`
  - Klassenname: `QuoteenterpriseIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Wahrscheinlich ein Fallback- oder Basis-Controller oder behandelt eine Standardroute für den Front-Office-Bereich des Moduls.
- `controllers/front/list.php`
  - Klassenname: `QuoteenterpriseListModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Zeigt eine Liste von Angeboten für den angemeldeten Kunden in seinem Kontobereich an.
- `controllers/front/pdf.php`
  - Klassenname: `QuoteenterprisePdfModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Generiert und stellt PDF-Versionen von Angeboten für Kunden zum Download bereit.
- `controllers/front/quoteList.php`
  - Klassenname: `QuoteenterpriseQuoteListModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Ähnlich wie `list.php`, potenziell eine alternative oder spezifische Ansicht für Angebotslisten, möglicherweise für AJAX-Laden.
- `controllers/front/request.php`
  - Klassenname: `QuoteenterpriseRequestModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Behandelt die Anzeige und Übermittlung des Angebotsanfrageformulars von Produktseiten, Warenkorb oder schwebender Schaltfläche. Verarbeitet Formulardaten und erstellt neue Angebotseinträge.
- `controllers/front/view.php`
  - Klassenname: `QuoteenterpriseViewModuleFrontController` (erweitert `ModuleFrontController`)
  - Zuständigkeit: Zeigt die Detailansicht eines einzelnen Angebots für den Kunden an, einschließlich Artikel, Preise, Status und Nachrichten.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminQuoteEnterpriseAuditLog.php`
  - Klassenname: `AdminQuoteEnterpriseAuditLogController` (erweitert `ModuleAdminController`)
  - Registerkartenname: Quote Enterprise > Audit-Log
  - Verwaltete Entität: `quote_audit_log` (wahrscheinlich ein benutzerdefiniertes `ObjectModel` für Audit-Einträge)
  - Zuständigkeit: Bietet eine Rasteransicht für Administratoren, um alle historischen Aktionen und Änderungen im Zusammenhang mit Angeboten zu überprüfen.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`
  - Klassenname: `AdminQuoteEnterpriseQuotesController` (erweitert `ModuleAdminController`)
  - Registerkartenname: Quote Enterprise > Angebote
  - Verwaltete Entität: `quote` (wahrscheinlich ein benutzerdefiniertes `ObjectModel` für Angebote)
  - Zuständigkeit: Die primäre Schnittstelle zur Verwaltung von Angeboten, einschließlich Auflistung, Anzeige, Bearbeitung, Umwandlung in Bestellung und Senden von Mitteilungen.
- `controllers/admin/index.php`
  - Klassenname: `QuoteenterpriseAdminIndexModuleFrontController` (erweitert `ModuleAdminController`)
  - Zuständigkeit: Wahrscheinlich ein Platzhalter oder Basis-Admin-Controller, der möglicherweise zur Hauptangebotsliste oder zum Dashboard weiterleitet.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`: Leere Datei, gängige Praxis, um das Auflisten von Verzeichnissen zu verhindern.
- `classes/QuoteAdmin.php`: Enthält Logik für adminspezifische Aufgaben, möglicherweise im Zusammenhang mit der Modulkonfiguration oder allgemeinen Admin-Dienstprogrammen.
- `classes/QuoteAdminAjax.php`: Behandelt AJAX-Anfragen, die vom Back-Office stammen, wie z. B. die dynamische Produktsuche zum Hinzufügen zu einem Angebot.
- `classes/QuoteAdminQuoteForm.php`: Verwaltet die komplexe Formularlogik zum Bearbeiten und Erstellen von Angeboten im Back-Office.
- `classes/QuoteApi.php`: Kernklasse für die REST-API des Moduls, die Authentifizierung, Routing und Daten-Serialisierung handhabt.
- `classes/QuoteApiDocumentation.php`: Bietet Methoden zum Generieren oder Anzeigen der Dokumentation für die API-Endpunkte des Moduls.
- `classes/QuoteBulkActions.php`: Implementiert Logik zum Ausführen von Aktionen auf mehreren ausgewählten Angeboten in der Admin-Liste (z. B. Massenstatusänderung).
- `classes/QuoteConverter.php`: Behandelt die entscheidende Logik der Umwandlung eines angenommenen Angebots in eine Standard-PrestaShop-Bestellung.
- `classes/QuoteDashboard.php`: Stellt Daten und Logik für die Dashboard-Ansicht des Moduls im Back-Office bereit (falls vorhanden), die die Angebotsaktivität zusammenfasst.
- `classes/QuoteDuplicator.php`: Logik zum Duplizieren bestehender Angebote.
- `classes/QuoteenterpriseModuleFrontController.php`: Basisklasse für Front-Office-Controller, die gemeinsame Methoden und Eigenschaften bereitstellt.
- `classes/QuoteExpiry.php`: Verwaltet die Logik zur Überprüfung der Angebotsgültigkeit, zum Markieren von Angeboten als abgelaufen und zum Senden entsprechender Benachrichtigungen.
- `classes/QuoteExporter.php`: Behandelt den Export von Angebotsdaten (z. B. CSV, Excel).
- `classes/QuoteFeeProduct.php`: Wahrscheinlich ein `ObjectModel` oder Helfer zur Verwaltung spezieller „Gebührenprodukte“, die zu Angeboten hinzugefügt werden können (z. B. für Dienstleistungen, kundenspezifische Gebühren).
- `classes/QuoteListHelper.php`: Bietet Dienstprogramm-Methoden zum Anzeigen und Filtern von Angebotslisten im Front- und Back-Office.
- `classes/QuoteMailer.php`: Zentralisierte Klasse zum Senden verschiedener E-Mail-Benachrichtigungen im Zusammenhang mit Angeboten.
- `classes/QuoteNotifyDigest.php`: Logik zum Kompilieren und Senden täglicher oder periodischer Zusammenfassungen der Angebotsaktivität an Administratoren.
- `classes/QuotePdf.php`: Behandelt die Generierung von PDF-Proforma-Rechnungen für Angebote.
- `classes/QuoteProductHelper.php`: Dienstprogramm-Methoden zur Interaktion mit PrestaShop-Produkten im Kontext eines Angebots.
- `classes/QuoteQtyHelper.php`: Unterstützt die Mengenverwaltung und -validierung innerhalb von Angeboten.
- `classes/QuoteQuotesManager.php`: Kern-Geschäftslogik zur Verwaltung von Angeboten, einschließlich Erstellung, Aktualisierungen und Statusänderungen.
- `classes/QuoteReference.php`: Verwaltet die Generierung und Einzigartigkeit von Angebotsreferenznummern.
- `classes/QuoteRequestHelper.php`: Unterstützt die Verarbeitung und Validierung von Angebotsanfragen, die von Kunden eingereicht werden.
- `classes/QuoteSchema.php`: Definiert das Datenbankschema für benutzerdefinierte Tabellen, die vom Modul verwendet werden (z. B. `ps_quote`, `ps_quote_product`, `ps_quote_audit_log`).
- `classes/QuoteSettingDescTrait.php`: Ein PHP-Trait, das wahrscheinlich verwendet wird, um gemeinsame Beschreibungen oder Metadaten für Moduleinstellungen bereitzustellen.
- `classes/QuoteTaxHelper.php`: Behandelt Steuernberechnungen, die spezifisch für Angebote sind.
- `classes/QuoteThemeCompat.php`: Enthält Logik zur Sicherstellung der Kompatibilität mit verschiedenen PrestaShop-Themes, möglicherweise durch Erkennung von Theme-Funktionen oder Bereitstellung von Überschreibungen.
- `classes/QuoteTimeline.php`: Verwaltet und zeigt die Zeitleiste der Ereignisse für ein bestimmtes Angebot an (ähnlich der Bestellhistorie).
- `classes/QuoteValidityHelper.php`: Dienstprogramm-Methoden zur Berechnung und Validierung von Angebotsablaufdaten.
- `classes/QuoteVisibility.php`: Steuert die Sichtbarkeit von angebotsbezogenen Elementen im Front Office (z. B. wer ein Angebot anfordern kann, wo Schaltflächen erscheinen).

### 4.4 JavaScript-Assets (`views/js/`)

- `lib/emailTemplatesManager/js/emailTemplatesManager.js`: Front-End-Logik für den E-Mail-Vorlagen-Editor im Back-Office.
- `lib/searchTool/views/js/autocomplete.js`: Bietet Autocomplete-Funktionalität zum Suchen von Produkten oder Kunden im Back-Office-Angebotseditor.
- `views/js/admin-audience-picker.js`: Behandelt die Logik zur Auswahl von Kundengruppen oder spezifischen Kunden für die Angebotssichtbarkeit oder -zielgruppenansprache im Admin.
- `views/js/adminQuoteApi.js`: JavaScript für den Admin-API-Konfigurationsbildschirm, möglicherweise zur Schlüsselgenerierung oder API-Dokumentationsanzeige.
- `views/js/adminQuoteDashboard.js`: Skripte für interaktive Elemente oder Datenvisualisierung auf dem Admin-Dashboard.
- `views/js/adminQuoteDetail.js`: Behandelt dynamische Interaktionen innerhalb der detaillierten Angebotsansicht im Back-Office (z. B. Hinzufügen von Produkten, Anwenden von Rabatten, Statusänderungen).
- `views/js/adminQuoteEditor.js`: Kern-JavaScript für das Back-Office-Angebots-Erstellungs-/Bearbeitungsformular, einschließlich Produktauswahl, Mengenaktualisierungen und Preisanpassungen.
- `views/js/adminQuoteSelector.js`: Wird zur Auswahl von Angeboten verwendet, möglicherweise in einem Modal oder verknüpften Kontext.
- `views/js/adminQuotesList.js`: Skripte für die Admin-Angebotsliste, einschließlich Filterung, Sortierung und Massenaktionen.
- `views/js/front.js`: Allgemeines Front-Office-JavaScript für das Modul, das Schaltflächenklicks, modale Pop-ups für Angebotsanfragen, Formularübermittlungen und dynamische Aktualisierungen verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

- `lib/emailTemplatesManager/css/emailTemplatesManager.css`: Styling für den E-Mail-Vorlagen-Editor im Back-Office.
- `lib/searchTool/views/css/autocomplete.css`: Stile für die Autocomplete-Suchergebnisse (z. B. Produktsuche).
- `views/css/admin-audience-picker.css`: Styling für die Kunden-/Zielgruppenauswahl-Oberfläche im Admin.
- `views/css/admin_quoteenterprise.css`: Primäres Stylesheet für die Back-Office-Oberflächen des Moduls (Angebotsliste, Detail, Audit-Log).
- `views/css/front-hummingbird.css`: Spezifische Front-Office-Stilanpassungen für das PrestaShop-Standardtheme „Hummingbird“.
- `views/css/front.css`: Allgemeines Front-Office-Styling für Angebots-Schaltflächen, Formulare und Kundenkontoansichten. Entwickler können Klassen wie `.quoteenterprise-button`, `.quoteenterprise-form`, `.quoteenterprise-list` in ihrem Theme überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `hook/adminOrderQuote.tpl`: Rendert einen angebotsbezogenen Block auf der Standard-PrestaShop-Bestelldetailseite im Admin.
- `hook/cartQuoteButton.tpl`: Zeigt die Schaltfläche oder den Link „Angebot anfordern“ auf der Warenkorbseite an.
- `hook/customerAccount-hummingbird.tpl`: Rendert den Angebotslisten-Link im Kundenkontobereich für das Hummingbird-Theme.
- `hook/customerAccount.tpl`: Rendert den Angebotslisten-Link im Kundenkontobereich für klassische Themes.
- `hook/productListQuote.tpl`: Zeigt eine Angebots-Schaltfläche oder -Option auf Produktlistenseiten (Kategorie, Suchergebnisse) an.
- `hook/quoteFloatButton.tpl`: Rendert die dauerhafte schwebende Angebots-Schaltfläche im Front Office.
- `hook/quoteListModal.tpl`: Template für ein modales Fenster, das eine Liste von Angeboten anzeigt.
- `hook/quoteRequestButton.tpl`: Zeigt die Schaltfläche „Angebot anfordern“ auf einzelnen Produktseiten an.
- `hook/quoteRequestModal.tpl`: Template für das modale Fenster, das das Angebotsanfrageformular öffnet.

#### Admin-Templates (`views/templates/admin/`)

- `admin/api.tpl`: Rendert die API-Konfigurations- und Schlüsselverwaltungs-Oberfläche.
- `admin/audience-picker.tpl`: Template für das Kunden-/Gruppenauswahl-Tool im Admin.
- `admin/audit.tpl`: Zeigt die Audit-Log-Tabelle im Back-Office an.
- `admin/dashboard.tpl`: Rendert die Dashboard-Übersicht des Moduls im Back-Office.
- `admin/notifications.tpl`: Zeigt Admin-Benachrichtigungen im Zusammenhang mit Angeboten an.
- `admin/quoteDetail.tpl`: Das umfassende Template zum Anzeigen und Bearbeiten eines einzelnen Angebots im Back-Office.
- `admin/quotes.tpl`: Rendert die Hauptangebotslistentabelle im Back-Office.
- `admin/quotesOverview.tpl`: Ein Zusammenfassungs- oder Übersichtsabschnitt für Angebote, möglicherweise auf dem Dashboard.
- `admin/scopeSelector.tpl`: Template zur Auswahl des Bereichs (z. B. Shop, Sprache) im Admin.
- `admin/visibilityConfigurator.tpl`: Template zur Konfiguration von Angebots-Sichtbarkeitsregeln.
- `admin/_api_documentation_modal.tpl`: Rendert ein modales Fenster mit API-Dokumentation für Entwickler.
- `admin/_bulk_options.tpl`: Template für Dropdowns für Massenaktionen in Admin-Listen.

#### Front-Office-Templates (`views/templates/front/`)

- `front/list.tpl`: Zeigt die Kundenliste der Angebote in deren Konto an.
- `front/request.tpl`: Das Haupttemplate für das Angebotsanfrageformular des Kunden.
- `front/view.tpl`: Zeigt die Detailansicht eines einzelnen Angebots für den Kunden an.
- `front/_requestComplianceFields.tpl`: Partielles Template für zusätzliche Compliance-bezogene Felder im Angebotsanfrageformular.
- `front/_requestLinesTable.tpl`: Partielles Template zur Anzeige der Produktzeilen innerhalb eines Angebotsanfrageformulars.

#### PDF-Templates (`views/templates/pdf/`)

- `pdf/quote.tpl`: Template, das zur Generierung des Inhalts der PDF-Proforma-Rechnung verwendet wird.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt benutzerdefinierte Tabellen, die typischerweise mit `ps_` (oder Ihrem benutzerdefinierten Präfix) beginnen. Wichtige Tabellen sind:

- `ps_quote`: Speichert die Hauptangebotsdetails (Kunden-ID, Status, Gesamtbetrag, Gültigkeit, Referenz usw.).
- `ps_quote_product`: Speichert die einzelnen Produkte und deren Mengen/Preise, die jedem Angebot zugeordnet sind.
- `ps_quote_audit_log`: Zeichnet alle Änderungen und Aktionen auf, die an Angeboten zu Prüfzwecken durchgeführt wurden.
- `ps_quote_api_key`: Speichert API-Schlüssel für externe Integrationen.
- `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `QUOTEENTERPRISE_ENABLE`, `QUOTEENTERPRISE_MIN_VALUE` usw. gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Einfügen von CSS/JS-Assets, Meta-Tags oder globaler Modulinitialisierung. |
| `displayRightColumn` | In der rechten Spalte Ihres Shops (falls vom Theme aktiviert). | Anzeige der schwebenden Angebots-Schaltfläche oder eines statischen Angebotsanfrageblocks. |
| `displayLeftColumn` | In der linken Spalte Ihres Shops (falls vom Theme aktiviert). | Anzeige der schwebenden Angebots-Schaltfläche oder eines statischen Angebotsanfrageblocks. |
| `displayFooter` | Im Fußbereich jeder Seite. | Anzeige der schwebenden Angebots-Schaltfläche oder eines statischen Angebotsanfrageblocks. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe der Schaltfläche „In den Warenkorb“. | Anzeige der Schaltfläche „Angebot anfordern“ auf Produktseiten. |
| `displayShoppingCartFooter` | In der Warenkorbzusammenfassung, unterhalb der Produktliste. | Anzeige der Schaltfläche „Angebot anfordern“, um den Warenkorb in ein Angebot umzuwandeln. |
| `displayCustomerAccount` | Auf der Seite „Mein Konto“ des Kunden. | Hinzufügen eines Links zur Kundenliste der Angebote. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Potenziell verwendet, um ein Angebot mit der resultierenden Bestellung zu verknüpfen oder den Angebotsstatus zu aktualisieren. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Assets lädt. | Einfügen modulspezifischer CSS/JS für Back-Office-Seiten. |
| `displayAdminOrder` | Auf der PrestaShop-Admin-Bestelldetailseite. | Anzeige eines Blocks mit Angebotsinformationen, wenn die Bestellung aus einem Angebot stammt. |
| `actionObjectProductUpdateAfter` | Nach der Aktualisierung eines Produkts. | Potenziell zur Aktualisierung von Angebotspreisen, wenn sich Produktpreise ändern (erweiterte Funktion). |
| `actionObjectProductDeleteAfter` | Nach dem Löschen eines Produkts. | Zum Behandeln von Produkten, die aus Angeboten entfernt wurden. |
| `actionObjectCustomerDeleteAfter` | Nach dem Löschen eines Kunden. | Zum Behandeln von Angeboten, die einem gelöschten Kunden zugeordnet sind. |
| `displayBackOfficeHeader` | Im `<head>` jeder Back-Office-Seite. | Allgemeine Back-Office-Asset-Injektion oder globale Admin-Modul-Einrichtung. |
| `displayBackOfficeTop` | Oben im Back-Office-Inhaltsbereich. | Anzeige modulspezifischer Warnungen oder Dashboard-Widgets. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul Quote Enterprise gerne zur Verfügung.
