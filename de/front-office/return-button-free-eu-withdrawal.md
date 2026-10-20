---
title: "Rückgabe-Button Kostenlos - EU-Widerruf - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Rückgabe-Button Kostenlos - EU-Widerruf“ von MyPresta.eu."
sidebar:
  label: "Rückgabe-Button Kostenlos - EU-Widerruf"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Return Button Free - EU Withdrawal auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/return-button-free-eu-withdrawal.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/return-button-free-eu-withdrawal/)
>
> ---


# Rückgabe-Button Kostenlos - EU-Widerruf

## 1. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie dessen allgemeines Verhalten und Aussehen steuern.

#### Registerkarte Allgemeine Einstellungen

-   **Modul aktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität in Ihrem Shop.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Der Widerrufs-Button und die Funktionalität sind für Kunden gemäß Ihren anderen Einstellungen aktiv und sichtbar.
        -   *Wenn deaktiviert:* Die Funktionen des Moduls werden im Front Office vollständig ausgeblendet, und Kunden können darüber keine Widerrufsanfragen stellen.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Sie würden dies aktivieren, wenn Sie bereit sind, die Widerrufsoption Ihren Kunden anzubieten. Sie könnten es vorübergehend während der Wartung oder bei größeren Änderungen Ihrer Rückgaberichtlinien deaktivieren.

-   **Widerrufs-Button anzeigen in:**
    -   **Was diese Einstellung bewirkt:** Legt fest, wo der Haupt-Button „Widerrufsanfrage“ im Front Office Ihres Shops erscheint.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Header:* Der Button erscheint im oberen Bereich Ihrer Website, oft global sichtbar.
        -   *Linke Spalte:* Der Button erscheint in der linken Seitenleiste (falls Ihr Theme eine hat).
        -   *Rechte Spalte:* Der Button erscheint in der rechten Seitenleiste (falls Ihr Theme eine hat).
        -   *Produktseite:* Der Button erscheint auf einzelnen Produktseiten.
        -   *Footer:* Der Button erscheint im unteren Bereich Ihrer Website.
    -   **Empfohlener Wert:** Footer (oft ein guter, unauffälliger Ort für rechtliche Links) oder Header (für maximale Sichtbarkeit). Wählen Sie basierend auf dem Layout Ihres Themes und Ihrer Präferenz für die Prominenz.
    -   **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden die Option leicht finden, ist die Platzierung im Header oder Footer üblich. Wenn Sie es weniger prominent, aber dennoch zugänglich bevorzugen, könnte eine Spalte geeignet sein.

-   **Gast-Widerrufsanfragen zulassen:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob Kunden, die ohne Konto bestellt haben, dennoch eine Widerrufsanfrage stellen können.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Gäste können auf das Widerrufsformular zugreifen, indem sie ihre Bestellreferenz und E-Mail-Adresse angeben.
        -   *Wenn deaktiviert:* Nur registrierte Kunden, die in ihren Konten angemeldet sind, können Widerrufsanfragen stellen.
    -   **Empfohlener Wert:** JA (Sehr empfehlenswert für die EU-Konformität, da das Widerrufsrecht für alle Verbraucher gilt, nicht nur für registrierte).
    -   **Händlerszenario / Beispiel:** Die Aktivierung stellt sicher, dass Sie die Verbraucherrechte für alle Kunden einhalten, unabhängig von ihrer Checkout-Methode, und vermeidet Frustration bei Gästen, die keine Möglichkeit finden, zu widerrufen.

-   **Bestellstatus für Widerrufsberechtigung:**
    -   **Was diese Einstellung bewirkt:** Definiert, welche Bestellstatus eine Bestellung für eine Widerrufsanfrage berechtigen. Zum Beispiel könnten Sie Widerrufe nur für Bestellungen zulassen, die „Geliefert“ oder „Versandt“ wurden.
    -   **Auswirkung der Änderung dieser Einstellung:** Kunden sehen die Widerrufsoption nur für Bestellungen, die einem der ausgewählten Status in ihrer Bestellhistorie entsprechen oder wenn sie eine Gastbestellreferenz eingeben.
    -   **Empfohlener Wert:** Wählen Sie Status wie „Zahlung akzeptiert“, „Vorbereitung läuft“, „Versandt“, „Geliefert“. Vermeiden Sie Status wie „Storniert“ oder „Erstattet“, da Widerrufe dort nicht anwendbar sind.
    -   **Händlerszenario / Beispiel:** Sie möchten Widerrufe für Bestellungen zulassen, die bereits bearbeitet oder geliefert wurden, aber nicht für Bestellungen, die noch auf Zahlung warten oder bereits storniert wurden.

-   **Bestellstatus für Widerrufsbestätigung:**
    -   **Was diese Einstellung bewirkt:** Legt fest, welcher Bestellstatus automatisch auf eine Bestellung angewendet werden soll, sobald eine Widerrufsanfrage vom Kunden erfolgreich eingereicht wurde. Dies hilft Ihnen, Bestellungen mit ausstehenden Widerrufsanfragen schnell zu identifizieren.
    -   **Auswirkung der Änderung dieser Einstellung:** Wenn ein Kunde einen Widerruf einreicht, ändert sich der Status der Bestellung zu dem hier ausgewählten.
    -   **Empfohlener Wert:** Erstellen Sie einen neuen, eindeutigen Bestellstatus wie „Widerruf angefragt“ oder „EU-Widerruf ausstehend“ in Ihren PrestaShop-Bestellstatus-Einstellungen (unter Shop-Parameter > Bestell-Einstellungen > Status) und wählen Sie ihn hier aus.
    -   **Händlerszenario / Beispiel:** Das Festlegen eines spezifischen Status wie „Widerruf angefragt“ ermöglicht es Ihrem Kundenservice-Team, Bestellungen, die für einen Widerrufsprozess Aufmerksamkeit erfordern, einfach zu filtern und zu verwalten.

-   **Bestellstatus für Widerrufsabschluss:**
    -   **Was diese Einstellung bewirkt:** Legt fest, welcher Bestellstatus automatisch auf eine Bestellung angewendet werden soll, sobald Sie als Händler den Widerruf bearbeitet und abgeschlossen haben (z. B. eine Rückerstattung vorgenommen haben).
    -   **Auswirkung der Änderung dieser Einstellung:** Nachdem Sie eine Widerrufsanfrage in der Admin-Oberfläche des Moduls als abgeschlossen markiert haben, wird der Status der zugehörigen Bestellung auf diesen ausgewählten Status aktualisiert.
    -   **Empfohlener Wert:** Wählen Sie einen bestehenden Status wie „Erstattet“ oder erstellen Sie einen neuen wie „EU-Widerruf abgeschlossen“.
    -   **Händlerszenario / Beispiel:** Sobald Sie die Rückerstattung bearbeitet und den Widerrufsfall abgeschlossen haben, bietet die Aktualisierung des Bestellstatus auf „Erstattet“ eine klare Aufzeichnung für Sie und den Kunden.

-   **Statistiken aktivieren:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob das Modul anonyme Statistiken über seine Nutzung sammelt. Diese Daten helfen dem Modulentwickler, das Modul zu verbessern.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul sendet anonyme Nutzungsdaten.
        -   *Wenn deaktiviert:* Es werden keine Nutzungsdaten gesendet.
    -   **Empfohlener Wert:** JA (Hilft, das Modul für alle zu verbessern).
    -   **Händlerszenario / Beispiel:** Sie aktivieren dies, um zur Entwicklung des Moduls beizutragen, oder deaktivieren es, wenn Sie strenge Datenschutzrichtlinien haben, die jegliche externe Datenübertragung verhindern.

#### Registerkarte Rechtliche Informationen

-   **Widerrufsfrist (Tage):**
    -   **Was diese Einstellung bewirkt:** Definiert die Anzahl der Kalendertage, die ein Kunde hat, um sein Widerrufsrecht auszuüben, beginnend mit dem Tag des Wareneingangs.
    -   **Auswirkung der Änderung dieser Einstellung:** Das Modul zeigt diesen Zeitraum den Kunden an und verwendet ihn intern für Datumsberechnungen oder Berechtigungsprüfungen.
    -   **Empfohlener Wert:** 14 (Dies ist die gesetzliche Mindestanforderung in der EU, Sie können jedoch einen längeren Zeitraum anbieten, wenn Sie möchten).
    -   **Händlerszenario / Beispiel:** Sie legen dies auf 14 Tage fest, um dem EU-Recht zu entsprechen. Wenn Sie eine großzügigere Rückgaberichtlinie anbieten, könnten Sie es auf 30 Tage festlegen.

-   **Text des Widerrufsformulars:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den Einleitungstext anzupassen, der oben auf dem Widerrufsanfrageformular angezeigt wird. Dies ist ein mehrsprachiges Feld.
    -   **Auswirkung der Änderung dieser Einstellung:** Der von Ihnen eingegebene Text wird den Kunden angezeigt, wenn sie auf das Widerrufsformular zugreifen.
    -   **Empfohlener Wert:** Geben Sie klare, prägnante Anweisungen oder eine kurze Erklärung des Widerrufsprozesses.
    -   **Händlerszenario / Beispiel:** Sie könnten eine Nachricht hinzufügen wie: „Bitte füllen Sie dieses Formular aus, um Ihr Widerrufsrecht auszuüben. Sie haben 14 Tage ab Erhalt Ihrer Bestellung Zeit, diese Anfrage einzureichen.“

-   **Text der Bestätigungs-E-Mail:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den Text anzupassen, der in der Bestätigungs-E-Mail enthalten ist, die an Kunden gesendet wird, nachdem sie eine Widerrufsanfrage gestellt haben. Dies ist ein mehrsprachiges Feld.
    -   **Auswirkung der Änderung dieser Einstellung:** Der von Ihnen eingegebene Text wird Teil der E-Mail sein, die Kunden erhalten, und dient als dauerhafter Nachweis ihrer Anfrage.
    -   **Empfohlener Wert:** Fügen Sie wichtige Informationen wie die nächsten Schritte, wohin die Ware gesendet werden soll und spezifische Rücksendeanweisungen hinzu.
    -   **Händlerszenario / Beispiel:** Sie könnten schreiben: „Vielen Dank für Ihre Widerrufsanfrage. Ihre Anfrage wurde empfangen und wird in Kürze bearbeitet. Bitte senden Sie die Ware innerhalb von 14 Tagen an [Ihre Rücksendeadresse] zurück. Weitere Details entnehmen Sie bitte unserer Rückgaberichtlinie.“

-   **Link zur Widerrufsbelehrung:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einen Link zu Ihrer detaillierten Widerrufs- oder Rückgaberichtlinienseite bereitzustellen.
    -   **Auswirkung der Änderung dieser Einstellung:** Ein Link wird auf dem Widerrufsformular angezeigt, der Kunden zu Ihrer vollständigen Richtlinie führt.
    -   **Empfohlener Wert:** Geben Sie die URL zu Ihrer dedizierten CMS-Seite für Rücksendungen/Widerrufe an.
    -   **Händlerszenario / Beispiel:** Sie haben eine CMS-Seite mit dem Titel „Rücksendungen & Rückerstattungen“ unter `ihrshop.com/content/returns-refunds`. Sie würden diese URL hier eingeben.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| **Registerkarte Allgemeine Einstellungen** | Modul aktivieren | JA | Aktiviert/deaktiviert die Modulfunktionalität. |
| | Widerrufs-Button anzeigen in | Footer / Header | Legt den Standort des Haupt-Widerrufs-Buttons fest. |
| | Gast-Widerrufsanfragen zulassen | JA | Ermöglicht Widerruf für nicht registrierte Kunden. |
| | Bestellstatus für Widerrufsberechtigung | Zahlung akzeptiert, Versandt, Geliefert | Definiert, welche Bestellstatus Widerrufsanfragen zulassen. |
| | Bestellstatus für Widerrufsbestätigung | „Widerruf angefragt“ (Benutzerdefiniert) | Status, der der Bestellung bei Kundenübermittlung zugewiesen wird. |
| | Bestellstatus für Widerrufsabschluss | „Erstattet“ (Bestehend) / „EU-Widerruf abgeschlossen“ (Benutzerdefiniert) | Status, der der Bestellung bei Händlerabschluss zugewiesen wird. |
| | Statistiken aktivieren | JA | Ermöglicht die Sammlung anonymer Nutzungsdaten zur Modulverbesserung. |
| **Registerkarte Rechtliche Informationen** | Widerrufsfrist (Tage) | 14 | Legt die gesetzliche Frist für den Widerruf fest. |
| | Text des Widerrufsformulars | Anpassbar | Einleitungstext auf dem Widerrufsformular. |
| | Text der Bestätigungs-E-Mail | Anpassbar | Text, der in der Widerrufsbestätigungs-E-Mail enthalten ist. |
| | Link zur Widerrufsbelehrung | Ihre CMS-Seiten-URL | Link zu Ihrer detaillierten Rückgabe-/Widerrufsbelehrung. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### Widerrufsanfragen (Back Office > Module > Rückgabe-Button Kostenlos > Widerrufsanfragen)
Dieser dedizierte Administrationsbildschirm ist der Ort, an dem Sie alle eingehenden Widerrufsanfragen Ihrer Kunden verwalten.

-   **Bildschirmname & Menüpfad:** **Widerrufsanfragen** (zu finden unter dem Hauptmenü „Module“, dann Untermenü „Rückgabe-Button Kostenlos“).
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Auflistungstabelle:** Zeigt eine umfassende Liste aller Widerrufsanfragen an.
        -   **ID:** Eindeutiger Bezeichner für jede Anfrage.
        -   **Eingereicht:** Datum und Uhrzeit der Einreichung der Anfrage.
        -   **Bestellung:** Die zugehörige PrestaShop-Bestellreferenz.
        -   **Vorname, Nachname, E-Mail:** Kontaktdaten des Kunden.
        -   **Umfang:** Zeigt an, ob es sich um einen vollständigen Bestellwiderruf handelt (diese kostenlose Version unterstützt nur den vollständigen Bestellwiderruf).
        -   **Typ:** Die Art des Widerrufs (z. B. „EU-Widerruf“).
        -   **Status:** Der aktuelle Status der Widerrufsanfrage (z. B. „Ausstehend“, „Bearbeitet“, „Storniert“).
    -   **Details anzeigen:** Klicken Sie auf eine beliebige Anfrage in der Liste, um eine detaillierte Ansicht zu öffnen.
        -   Diese Ansicht bietet alle vom Kunden übermittelten Informationen, einschließlich Bestelldetails, Produkte und zusätzliche Notizen.
        -   Sie können interne Notizen hinzufügen, den Status des Widerrufs ändern (z. B. von „Ausstehend“ zu „Bearbeitet“ oder „Storniert“) und den Verlauf der Änderungen verfolgen.
        -   Die Einstellung „Bestellstatus für Widerrufsabschluss“ (aus der Hauptkonfiguration) wird auf die zugehörige Bestellung angewendet, wenn Sie einen Widerruf hier als abgeschlossen markieren.
    -   **Filtern und Suchen:** Sie können die Liste nach Status, Kundennamen, Bestell-ID usw. filtern, um schnell bestimmte Anfragen zu finden.
-   **Auswirkung von Änderungen:**
    -   **Status ändern:** Das Aktualisieren des Status einer Widerrufsanfrage (z. B. auf „Bearbeitet“ oder „Abgeschlossen“) aktualisiert den Datensatz im Modul und, falls konfiguriert, den Status der zugehörigen PrestaShop-Bestellung. Dies hilft Ihnen, den Fortschritt zu verfolgen und mit Kunden zu kommunizieren.
    -   **Notizen hinzufügen:** Interne Notizen dienen als Referenz für Ihr Team und sind für den Kunden nicht sichtbar. Sie helfen bei der Dokumentation der Kommunikation und der für jeden Widerruf ergriffenen Maßnahmen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Überprüfen Sie regelmäßig den Bildschirm „Widerrufsanfragen“ auf neue „Ausstehende“ Anfragen.
    2.  Klicken Sie auf eine Anfrage, um deren Details anzuzeigen.
    3.  Überprüfen Sie die Kundeninformationen und die zugehörige Bestellung.
    4.  Kommunizieren Sie bei Bedarf mit dem Kunden (z. B. geben Sie Anweisungen zur Rücksendung).
    5.  Sobald die Ware eingegangen und geprüft wurde, bearbeiten Sie die Rückerstattung in der PrestaShop-Bestellverwaltung.
    6.  Aktualisieren Sie den Status der Widerrufsanfrage im Modul auf „Bearbeitet“ oder „Abgeschlossen“. Dies aktualisiert auch den Hauptbestellstatus, wenn Sie „Bestellstatus für Widerrufsabschluss“ konfiguriert haben.
    7.  Fügen Sie alle relevanten internen Notizen zur Rückerstattung, Sendungsverfolgungsnummern oder Kommunikation hinzu.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

-   **F: Der Widerrufs-Button wird in meinem Shop nicht angezeigt.**
    -   **A:** Überprüfen Sie zunächst, ob das Modul in seiner Konfiguration „Aktiviert“ ist. Vergewissern Sie sich dann, dass Sie einen Ort für die „Anzeige des Widerrufs-Buttons“ (z. B. Footer, Header) ausgewählt haben. Wenn Ihr Theme stark angepasst ist, wird es möglicherweise nicht korrekt eingehängt. Versuchen Sie, einen anderen Anzeigeort zu wählen. Stellen Sie außerdem sicher, dass Ihr Smarty-Cache geleert ist (Erweiterte Parameter > Leistung > Cache leeren).
-   **F: Kunden reichen Widerrufsanfragen ein, aber der Bestellstatus ändert sich nicht.**
    -   **A:** Gehen Sie zur Modulkonfiguration und überprüfen Sie die Einstellung „Bestellstatus für Widerrufsbestätigung“. Stellen Sie sicher, dass Sie dort einen geeigneten Bestellstatus ausgewählt haben. Wenn Sie einen neuen Status erstellt haben, stellen Sie sicher, dass er in PrestaShop (Shop-Parameter > Bestell-Einstellungen > Status) korrekt konfiguriert ist.
-   **F: Können Kunden mit diesem Modul einzelne Produkte aus einer Bestellung widerrufen?**
    -   **A:** Nein, das kostenlose Modul „Rückgabe-Button Kostenlos - EU-Widerruf“ ist nur für den **vollständigen Bestellwiderruf** gemäß der EU-Richtlinie konzipiert. Wenn Sie Teillieferungen für einzelne Produkte bearbeiten müssen, benötigen Sie ein fortschrittlicheres Retourenmanagement-Modul.
-   **F: Das Modul ist installiert, aber der Text auf dem Formular oder in der E-Mail ist in der falschen Sprache oder sieht generisch aus.**
    -   **A:** Die Einstellungen „Text des Widerrufsformulars“ und „Text der Bestätigungs-E-Mail“ sind mehrsprachige Felder. Stellen Sie sicher, dass Sie den gewünschten Text für jede in Ihrem Shop aktivierte Sprache eingegeben haben. Sie können zwischen den Sprachen wechseln, indem Sie das Flaggen-Symbol neben dem Textbereich in der Modulkonfiguration verwenden.
-   **F: Ich habe das Modul aktualisiert, und jetzt sieht etwas seltsam aus. Was soll ich tun?**
    -   **A:** Nach jedem Modul-Update ist es eine gute Praxis, Ihren PrestaShop-Cache zu leeren. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“. Wenn das Problem weiterhin besteht, überprüfen Sie die Konfigurationseinstellungen des Moduls, um sicherzustellen, dass sie noch Ihren Erwartungen entsprechen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls „Rückgabe-Button Kostenlos - EU-Widerruf“, der für Entwickler und Webmaster gedacht ist.

### 4.1 Architekturübersicht
Das Modul folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller). Es nutzt `ModuleFrontController` für Front-Office-Interaktionen und `AdminController` für die Back-Office-Verwaltung. `ObjectModel` wird für die persistente Datenspeicherung im Zusammenhang mit Widerrufsanfragen verwendet. Wichtige Dienste und Hilfsklassen kapseln die Geschäftslogik und gewährleisten die Kompatibilität über PrestaShop-Versionen hinweg. Das Modul integriert sich mit verschiedenen PrestaShop-Hooks, um seine Funktionalität anzuzeigen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller
Diese Controller verwalten kundenorientierte Interaktionen im Zusammenhang mit Widerrufsanfragen.

-   `rbfree/controllers/front/confirm.php`
    *   Klassenname: `RbfConfirmModuleFrontController` (erweitert `RbfModuleFrontController`)
    *   Verantwortlichkeit: Zeigt den letzten Bestätigungsschritt des Widerrufsformulars an, sodass der Kunde seine Anfrage überprüfen und absenden kann. Verarbeitet die POST-Übermittlung, um einen neuen `RbfWithdrawal`-Eintrag zu erstellen.
-   `rbfree/controllers/front/form.php`
    *   Klassenname: `RbfFormModuleFrontController` (erweitert `RbfModuleFrontController`)
    *   Verantwortlichkeit: Rendert das anfängliche Widerrufsanfrageformular. Verarbeitet die Eingabevalidierung für Bestellreferenz, E-Mail und Kundendaten.
-   `rbfree/controllers/front/print.php`
    *   Klassenname: `RbfPrintModuleFrontController` (erweitert `RbfModuleFrontController`)
    *   Verantwortlichkeit: Bietet eine druckbare Version des Widerrufsanfrageformulars, typischerweise nach der Einreichung, für Kundenunterlagen.
-   `rbfree/controllers/front/RbfModuleFrontController.php`
    *   Klassenname: `RbfModuleFrontController` (erweitert `ModuleFrontController`)
    *   Verantwortlichkeit: Basisklasse für alle Front-Office-Controller des Moduls, die gemeinsame Dienstprogramme, Sicherheitsprüfungen und Smarty-Variablenzuweisungen bereitstellt.
-   `rbfree/controllers/front/status.php`
    *   Klassenname: `RbfStatusModuleFrontController` (erweitert `RbfModuleFrontController`)
    *   Verantwortlichkeit: Zeigt dem Kunden den aktuellen Status einer spezifischen Widerrufsanfrage an.
-   `rbfree/controllers/front/track.php`
    *   Klassenname: `RbfTrackModuleFrontController` (erweitert `RbfModuleFrontController`)
    *   Verantwortlichkeit: Ermöglicht Kunden (einschließlich Gästen), ihre Widerrufsanfrage durch Eingabe einer Bestellreferenz und E-Mail zu verfolgen.

#### Back-Office-Admin-Controller
Diese Controller verwalten die Administrationsoberfläche für Widerrufsanfragen.

-   `rbfree/controllers/admin/AdminRbfWithdrawalController.php`
    *   Klassenname: `AdminRbfWithdrawalController` (erweitert `ModuleAdminController`)
    *   Tab-Name: „Widerrufsanfragen“ (unter „Module > Rückgabe-Button Kostenlos“)
    *   Verwaltete Entität: `RbfWithdrawal`
    *   Verantwortlichkeit: Bietet die CRUD-Schnittstelle (Create, Read, Update, Delete) zur Verwaltung von Widerrufsanfragen. Zeigt eine Liste von Anfragen an, ermöglicht die Anzeige detaillierter Informationen, die Aktualisierung des Status und das Hinzufügen von Notizen. Verarbeitet Formularübermittlungen für Statusänderungen und Notizen.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `rbfree/classes/RbfCompatibility.php`
    *   Klassenname: `RbfCompatibility`
    *   Verantwortlichkeit: Bietet Hilfsmethoden zur Gewährleistung der Kompatibilität über verschiedene PrestaShop-Versionen hinweg (z. B. Umgang mit Unterschieden in `Context`- oder `Tools`-Methoden).
-   `rbfree/classes/RbfSecurity.php`
    *   Klassenname: `RbfSecurity`
    *   Verantwortlichkeit: Enthält sicherheitsrelevante Hilfsmethoden, wie z. B. Token-Generierung und -Validierung, um Formulare vor CSRF-Angriffen zu schützen.
-   `rbfree/classes/RbfSelfHeal.php`
    *   Klassenname: `RbfSelfHeal`
    *   Verantwortlichkeit: Implementiert Logik für Selbstheilungs- oder Diagnoseprüfungen, um die Modulintegrität und Datenkonsistenz zu gewährleisten.
-   `rbfree/classes/RbfStatsService.php`
    *   Klassenname: `RbfStatsService`
    *   Verantwortlichkeit: Verwaltet die Sammlung und Übermittlung anonymer Nutzungsstatistiken, falls vom Händler aktiviert.
-   `rbfree/classes/RbfWithdrawal.php`
    *   Klassenname: `RbfWithdrawal` (erweitert `ObjectModel`)
    *   Datenbanktabelle: `ps_rbf_withdrawal`
    *   `$definition`-Felder: Definiert die Struktur einer Widerrufsanfrage, einschließlich `id_order`, `id_customer`, `firstname`, `lastname`, `email`, `status`, `date_add`, `date_upd` usw.
    *   Wichtige öffentliche Methoden: `add()`, `update()`, `delete()`, Methoden zum Abrufen von Widerrufsdetails, Verwalten von Statusübergängen.
-   `rbfree/classes/RbfWithdrawalAttachment.php`
    *   Klassenname: `RbfWithdrawalAttachment` (erweitert `ObjectModel`)
    *   Datenbanktabelle: `ps_rbf_withdrawal_attachment`
    *   `$definition`-Felder: Speichert Informationen über an eine Widerrufsanfrage angehängte Dateien (falls die Pro-Version dies unterstützt).
    *   Wichtige öffentliche Methoden: Methoden zur Verwaltung von Anhängen.
-   `rbfree/classes/RbfWithdrawalHistory.php`
    *   Klassenname: `RbfWithdrawalHistory` (erweitert `ObjectModel`)
    *   Datenbanktabelle: `ps_rbf_withdrawal_history`
    *   `$definition`-Felder: Zeichnet Änderungen am Status einer Widerrufsanfrage oder anderen wichtigen Attributen auf.
    *   Wichtige öffentliche Methoden: `add()`, Methoden zum Abrufen des Verlaufs.
-   `rbfree/classes/RbfWithdrawalNote.php`
    *   Klassenname: `RbfWithdrawalNote` (erweitert `ObjectModel`)
    *   Datenbanktabelle: `ps_rbf_withdrawal_note`
    *   `$definition`-Felder: Speichert interne Notizen, die von Administratoren zu einer Widerrufsanfrage hinzugefügt wurden.
    *   Wichtige öffentliche Methoden: `add()`, Methoden zum Abrufen von Notizen.
-   `rbfree/classes/RbfWithdrawalProduct.php`
    *   Klassenname: `RbfWithdrawalProduct` (erweitert `ObjectModel`)
    *   Datenbanktabelle: `ps_rbf_withdrawal_product`
    *   `$definition`-Felder: Speichert Details der in einer Widerrufsanfrage enthaltenen Produkte.
    *   Wichtige öffentliche Methoden: Methoden zur Verwaltung zugehöriger Produkte.
-   `rbfree/classes/RbfWithdrawalService.php`
    *   Klassenname: `RbfWithdrawalService`
    *   Verantwortlichkeit: Kapselt die Kern-Geschäftslogik für die Bearbeitung von Widerrufsanfragen, wie z. B. das Erstellen neuer Anfragen, das Aktualisieren von Bestellstatus, das Senden von E-Mails und das Validieren der Berechtigung.

### 4.4 JavaScript-Assets (`views/js/`)

-   `rbfree/views/js/admin-order-state-picker.js`
    *   Geltungsbereich: Back-Office
    *   Details: Verwaltet die interaktive Auswahl von Bestellstatus in der Modulkonfiguration, wahrscheinlich für die Einstellungen „Bestellstatus für Widerrufsberechtigung/Bestätigung/Abschluss“.
-   `rbfree/views/js/front.js`
    *   Geltungsbereich: Front-Office
    *   Details: Enthält allgemeines Front-Office-JavaScript für das Modul. Dies könnte Formularvalidierung, AJAX-Übermittlungen für Widerrufsformulare, dynamisches Laden von Inhalten oder Interaktionen mit dem Widerrufs-Button umfassen.
-   `rbfree/views/js/order-history.js`
    *   Geltungsbereich: Front-Office (Kundenkonto > Bestellhistorie)
    *   Details: Verwaltet speziell die Integration des Widerrufslinks/-buttons auf der Bestellhistorie-Seite des Kunden, möglicherweise durch Hinzufügen von Event-Listenern, um Optionen basierend auf dem Bestellstatus dynamisch anzuzeigen/auszublenden.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `rbfree/views/css/admin-config.css`
    *   Geltungsbereich: Back-Office (Modulkonfiguration)
    *   Details: Stile für die Hauptmodulkonfigurationsseite (`configure.tpl`), die ein konsistentes Aussehen innerhalb des PrestaShop-Admins gewährleisten.
-   `rbfree/views/css/admin-dashboard.css`
    *   Geltungsbereich: Back-Office (AdminRbfWithdrawalController-Dashboard)
    *   Details: Styling für die Dashboard-Ansicht von Widerrufsanfragen, einschließlich Tabellenlayouts, Statusindikatoren und allgemeinem Layout.
-   `rbfree/views/css/admin-order-state-picker.css`
    *   Geltungsbereich: Back-Office
    *   Details: Stile für die Bestellstatus-Auswahloberfläche, die in der Modulkonfiguration verwendet wird.
-   `rbfree/views/css/admin-pro-teaser.css`
    *   Geltungsbereich: Back-Office
    *   Details: Styling für „Pro“-Version-Teaser-Elemente innerhalb der Admin-Oberfläche des kostenlosen Moduls.
-   `rbfree/views/css/admin-searchtool.css`
    *   Geltungsbereich: Back-Office
    *   Details: Stile für Such- und Filterwerkzeuge innerhalb der Admin-Widerrufsliste.
-   `rbfree/views/css/admin-withdrawal-view.css`
    *   Geltungsbereich: Back-Office (AdminRbfWithdrawalController-Ansicht)
    *   Details: Styling für die Detailansicht einer einzelnen Widerrufsanfrage im Admin, einschließlich Notizen, Verlauf und Produktlisten.
-   `rbfree/views/css/front-classic.css`
    *   Geltungsbereich: Front-Office (Classic-Theme)
    *   Details: Spezifische Styling-Anpassungen für das Classic PrestaShop-Theme, die visuelle Konsistenz mit dem Design des Themes gewährleisten.
-   `rbfree/views/css/front-hummingbird.css`
    *   Geltungsbereich: Front-Office (Hummingbird-Theme)
    *   Details: Spezifische Styling-Anpassungen für das Hummingbird PrestaShop-Theme, die visuelle Konsistenz mit dem Design des Themes gewährleisten.
-   `rbfree/views/css/front.css`
    *   Geltungsbereich: Front-Office
    *   Details: Allgemeines Front-Office-Styling für die Widerrufsformulare, Buttons und Statusseiten, das über alle Themes hinweg angewendet wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)
-   `rbfree/views/templates/hook/account-link-classic.tpl`
    *   Hook: `displayCustomerAccount` (oder ähnlich)
    *   Ausgabe: Ein Link im Kundenkonto-Dashboard für das Classic-Theme.
-   `rbfree/views/templates/hook/account-link-hummingbird.tpl`
    *   Hook: `displayCustomerAccount` (oder ähnlich)
    *   Ausgabe: Ein Link im Kundenkonto-Dashboard für das Hummingbird-Theme.
-   `rbfree/views/templates/hook/button-classic.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (oder ähnlich)
    *   Ausgabe: Der Haupt-Widerrufs-Button für das Classic-Theme.
-   `rbfree/views/templates/hook/button-hummingbird.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (oder ähnlich)
    *   Ausgabe: Der Haupt-Widerrufs-Button für das Hummingbird-Theme.
-   `rbfree/views/templates/hook/button.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (oder ähnlich)
    *   Ausgabe: Generischer Haupt-Widerrufs-Button, als Fallback oder für gemeinsame Elemente verwendet.
-   `rbfree/views/templates/hook/order-detail-classic.tpl`
    *   Hook: `displayOrderDetail` (oder ähnlich)
    *   Ausgabe: Ein Widerrufslink/-button innerhalb der Bestelldetailseite für das Classic-Theme.
-   `rbfree/views/templates/hook/order-detail-hummingbird.tpl`
    *   Hook: `displayOrderDetail` (oder ähnlich)
    *   Ausgabe: Ein Widerrufslink/-button innerhalb der Bestelldetailseite für das Hummingbird-Theme.
-   `rbfree/views/templates/hook/order-detail.tpl`
    *   Hook: `displayOrderDetail` (oder ähnlich)
    *   Ausgabe: Generischer Widerrufslink/-button innerhalb der Bestelldetailseite.
-   `rbfree/views/templates/hook/order-withdrawal-notice.tpl`
    *   Hook: `displayAdminOrder` (oder ähnlich)
    *   Ausgabe: Ein Hinweis oder eine Zusammenfassung des Widerrufsstatus auf der Bestellansichtsseite im Back Office.

#### Admin-Templates (`views/templates/admin/`)
-   `rbfree/views/templates/admin/configure.tpl`
    *   Verwendet von: `getContent()` in `rbfree/index.php`
    *   Ausgabe: Das Hauptmodul-Konfigurationsformular im Back Office.
-   `rbfree/views/templates/admin/dashboard.tpl`
    *   Verwendet von: `AdminRbfWithdrawalController`
    *   Ausgabe: Die Dashboard-Ansicht, die alle Widerrufsanfragen auflistet.
-   `rbfree/views/templates/admin/order-state-picker.tpl`
    *   Verwendet von: Modulkonfiguration
    *   Ausgabe: Das interaktive Bestellstatus-Auswahl-Widget.
-   `rbfree/views/templates/admin/order-withdrawal-notice.tpl`
    *   Verwendet von: `displayAdminOrder`-Hook
    *   Ausgabe: Ein Hinweis zum Widerrufsstatus auf der Bestellansichtsseite im Back Office.
-   `rbfree/views/templates/admin/pro-teaser-dashboard-intro.tpl`
    *   Verwendet von: `AdminRbfWithdrawalController`
    *   Ausgabe: Einleitender Teaser für die Pro-Version auf dem Dashboard.
-   `rbfree/views/templates/admin/pro-teaser-dashboard.tpl`
    *   Verwendet von: `AdminRbfWithdrawalController`
    *   Ausgabe: Allgemeiner Pro-Version-Teaser auf dem Dashboard.
-   `rbfree/views/templates/admin/pro-teaser-exclusions.tpl`
    *   Verwendet von: Modulkonfiguration
    *   Ausgabe: Teaser für Pro-Version-Funktionen im Zusammenhang mit Ausschlüssen.
-   `rbfree/views/templates/admin/pro-teaser-order-states.tpl`
    *   Verwendet von: Modulkonfiguration
    *   Ausgabe: Teaser für Pro-Version-Funktionen im Zusammenhang mit Bestellstatus.
-   `rbfree/views/templates/admin/pro-teaser-withdrawal-scope.tpl`
    *   Verwendet von: Modulkonfiguration
    *   Ausgabe: Teaser für Pro-Version-Funktionen im Zusammenhang mit dem Widerrufsumfang.
-   `rbfree/views/templates/admin/pro-teaser.tpl`
    *   Verwendet von: Verschiedene Admin-Bereiche
    *   Ausgabe: Generischer Pro-Version-Teaser.
-   `rbfree/views/templates/admin/updates.tpl`
    *   Verwendet von: Modulkonfiguration
    *   Ausgabe: Zeigt Informationen zu Modul-Updates an.
-   `rbfree/views/templates/admin/view.tpl`
    *   Verwendet von: `AdminRbfWithdrawalController`
    *   Ausgabe: Die Detailansichtsseite für eine einzelne Widerrufsanfrage im Back Office.

#### Front-Office-Templates (`views/templates/front/`)
-   `rbfree/views/templates/front/confirm_step.tpl`
    *   Verwendet von: `RbfConfirmModuleFrontController`
    *   Ausgabe: Der zweite Schritt des Widerrufsformulars zur Bestätigung.
-   `rbfree/views/templates/front/error.tpl`
    *   Verwendet von: Verschiedene Front-Controller
    *   Ausgabe: Eine generische Fehlermeldungsseite.
-   `rbfree/views/templates/front/form.tpl`
    *   Verwendet von: `RbfFormModuleFrontController`
    *   Ausgabe: Das anfängliche Widerrufsanfrageformular.
-   `rbfree/views/templates/front/print.tpl`
    *   Verwendet von: `RbfPrintModuleFrontController`
    *   Ausgabe: Die druckbare Version des Widerrufsformulars.
-   `rbfree/views/templates/front/status.tpl`
    *   Verwendet von: `RbfStatusModuleFrontController`
    *   Ausgabe: Die Seite, die den Status einer spezifischen Widerrufsanfrage anzeigt.
-   `rbfree/views/templates/front/success.tpl`
    *   Verwendet von: `RbfConfirmModuleFrontController`
    *   Ausgabe: Eine Erfolgsmeldung nach dem Absenden einer Widerrufsanfrage.
-   `rbfree/views/templates/front/track.tpl`
    *   Verwendet von: `RbfTrackModuleFrontController`
    *   Ausgabe: Das Formular für Kunden, um ihre Widerrufsanfrage zu verfolgen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen
-   `ps_rbf_withdrawal`: Speichert die Hauptdetails der Widerrufsanfrage (ID, id_order, id_customer, Status, Daten, Kundeninformationen).
-   `ps_rbf_withdrawal_attachment`: Speichert Details zu allen Anhängen einer Widerrufsanfrage.
-   `ps_rbf_withdrawal_history`: Speichert einen Verlauf der Statusänderungen und anderer Aktualisierungen für jede Widerrufsanfrage.
-   `ps_rbf_withdrawal_note`: Speichert interne Notizen, die von Administratoren zu einer Widerrufsanfrage hinzugefügt wurden.
-   `ps_rbf_withdrawal_product`: Speichert Details der in einer Widerrufsanfrage enthaltenen Produkte.
-   `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `RBFREE_ENABLED`, `RBFREE_BUTTON_HOOK`, `RBFREE_ALLOW_GUEST` usw. gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS injizieren oder den Widerrufs-Button rendern, falls konfiguriert. |
| `displayLeftColumn` | In der linken Seitenleiste der zutreffenden Seiten. | Den Widerrufs-Button rendern, falls konfiguriert. |
| `displayRightColumn` | In der rechten Seitenleiste der zutreffenden Seiten. | Den Widerrufs-Button rendern, falls konfiguriert. |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Den Widerrufs-Button rendern, falls konfiguriert. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des In-den-Warenkorb-Buttons. | Den Widerrufs-Button rendern, falls konfiguriert. |
| `displayCustomerAccount` | Im Kunden-Dashboard „Mein Konto“. | Einen Link zum Widerrufsformular hinzufügen. |
| `displayOrderDetail` | Auf der Bestelldetailseite des Kunden. | Einen Link/Button zum Initiieren des Widerrufs für diese spezifische Bestellung hinzufügen. |
| `displayAdminOrder` | Auf der Bestellansichtsseite im Back Office. | Einen Hinweis oder eine Zusammenfassung einer zugehörigen Widerrufsanfrage anzeigen. |
| `actionOrderStatusUpdate` | Wenn der Status einer Bestellung geändert wird. | Potenziell Aktionen wie das Aktualisieren des Widerrufsstatus oder das Senden von Benachrichtigungen auslösen. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller sein Template rendert. | Front-Office-CSS- und JavaScript-Dateien in die Warteschlange stellen. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller sein Template rendert. | Back-Office-CSS- und JavaScript-Dateien in die Warteschlange stellen. |
| `actionModuleInstall` | Während der Modulinstallation. | Datenbanktabellen erstellen, Standardkonfiguration festlegen. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Datenbanktabellen entfernen, Konfiguration löschen. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Rückgabe-Button Kostenlos - EU-Widerruf“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
