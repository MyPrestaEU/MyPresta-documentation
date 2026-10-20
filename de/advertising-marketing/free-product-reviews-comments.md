---
title: "Kostenlose Produktbewertungen (Kommentare) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kostenlose Produktbewertungen (Kommentare)“ von MyPresta.eu."
sidebar:
  label: "Kostenlose Produktbewertungen (Kommentare)"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free product reviews (comments) auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/free-product-reviews-comments.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/free-product-reviews-comments/)
>
> ---


# Kostenlose Produktbewertungen (Kommentare)

## 1. Anforderungen & Kompatibilität
Dieses Modul ist für eine breite Kompatibilität mit modernen PrestaShop-Versionen und Standard-Hosting-Umgebungen konzipiert.

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in jeder modernen PrestaShop-kompatiblen Hosting-Umgebung verfügbar sind. Es sind keine ungewöhnlichen oder spezialisierten Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für das Modul „Kostenlose Produktbewertungen (Kommentare)“. Hier steuern Sie, wie Bewertungen in Ihrem Shop funktionieren und angezeigt werden.

#### Allgemeine Einstellungen

-   **Bewertungen aktivieren:**
    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Bewertungssystem.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der Bewertungsbereich wird auf den Produktseiten angezeigt, und Kunden können Bewertungen lesen und abgeben.
        *   *Wenn deaktiviert:* Der Bewertungsbereich wird auf den Produktseiten ausgeblendet, und es können keine neuen Bewertungen abgegeben oder angesehen werden.
    *   **Empfohlener Wert:** JA
    *   **Händlerszenario / Beispiel:** Aktivieren Sie dies, um sofort nach der Installation Kundenfeedback zu sammeln und anzuzeigen.

-   **Bewertungen müssen von einem Mitarbeiter genehmigt werden:**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob Bewertungen automatisch veröffentlicht werden oder eine manuelle Genehmigung durch einen Shop-Administrator erfordern.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Alle eingereichten Bewertungen erhalten den Status „ausstehend“ und sind im Front Office erst sichtbar, wenn ein Administrator sie im Bewertungsmanagementbereich des Moduls manuell genehmigt. Dies ermöglicht es Ihnen, Spam, unangemessene Inhalte oder Bewertungen, die Ihren Richtlinien nicht entsprechen, herauszufiltern.
        *   *Wenn deaktiviert:* Bewertungen werden sofort nach dem Absenden ohne menschliches Eingreifen veröffentlicht.
    *   **Empfohlener Wert:** JA (insbesondere für neue Shops oder zur Qualitätssicherung)
    *   **Händlerszenario / Beispiel:** Wenn Sie sicherstellen möchten, dass alle Bewertungen angemessen und konstruktiv sind, bevor sie live gehen, aktivieren Sie diese Option. Dies ist entscheidend für die Aufrechterhaltung Ihres Markenimages und die Verhinderung von Spam.

-   **Gastbewertungen zulassen:**
    *   **Was diese Einstellung bewirkt:** Steuert, ob nicht angemeldete Besucher (Gäste) Bewertungen abgeben können.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Jeder Besucher Ihrer Produktseite kann eine Bewertung abgeben, auch wenn er kein Konto hat oder nicht angemeldet ist. Er wird typischerweise nach einem Namen und einer E-Mail-Adresse gefragt.
        *   *Wenn deaktiviert:* Nur Kunden, die in ihrem PrestaShop-Konto angemeldet sind, können Bewertungen abgeben.
    *   **Empfohlener Wert:** JA (um mehr Bewertungen zu fördern) oder NEIN (um sicherzustellen, dass Bewertungen von tatsächlichen Kunden stammen).
    *   **Händlerszenario / Beispiel:** Wenn Sie die Anzahl der Bewertungen maximieren möchten, auch von Gelegenheitsbesuchern, aktivieren Sie Gastbewertungen. Wenn Sie nur Bewertungen von verifizierten Kunden sammeln möchten, die bei Ihnen gekauft haben, deaktivieren Sie diese Option.

-   **Mindestzeit zwischen 2 Bewertungen desselben Benutzers (in Sekunden):**
    *   **Was diese Einstellung bewirkt:** Legt eine Abklingzeit fest, um zu verhindern, dass ein einzelner Benutzer schnell hintereinander mehrere Bewertungen für dasselbe Produkt abgibt.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn ein Wert festgelegt ist (z. B. 3600 für 1 Stunde):* Ein Benutzer muss mindestens so viele Sekunden warten, nachdem er eine Bewertung abgegeben hat, bevor er eine weitere Bewertung für dasselbe Produkt abgeben kann.
        *   *Wenn auf 0 gesetzt:* Es gibt keine Zeitbegrenzung, und Benutzer können Bewertungen so häufig abgeben, wie sie möchten.
    *   **Empfohlener Wert:** 3600 (1 Stunde) oder 86400 (24 Stunden), um Spamming zu verhindern.
    *   **Händlerszenario / Beispiel:** Um zu verhindern, dass ein einzelner Kunde ein Produkt mit mehreren Bewertungen überflutet, stellen Sie dies auf eine angemessene Dauer wie 3600 Sekunden (1 Stunde) ein.

-   **Bewertungen auf der Produktseite anzeigen:**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob die Bewertungsliste und das Einreichungsformular direkt auf der Produktseite angezeigt werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der Bewertungsbereich ist auf der Produktseite sichtbar, sodass Kunden Bewertungen lesen und schreiben können.
        *   *Wenn deaktiviert:* Der Bewertungsbereich wird auf der Produktseite ausgeblendet. Dies könnte verwendet werden, wenn Sie lieber auf eine separate Bewertungsseite verlinken oder Bewertungen anders verwalten möchten.
    *   **Empfohlener Wert:** JA
    *   **Händlerszenario / Beispiel:** Um Bewertungen für Käufer, die Ihre Produkte durchsuchen, leicht zugänglich zu machen, lassen Sie diese Option aktiviert.

-   **Anzahl der Bewertungen pro Seite:**
    *   **Was diese Einstellung bewirkt:** Steuert, wie viele Bewertungen auf einer einzelnen Seite innerhalb der Bewertungsliste angezeigt werden, bevor die Paginierung angewendet wird.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn ein Wert festgelegt ist (z. B. 5):* Es werden nur 5 Bewertungen gleichzeitig angezeigt, mit „Weiter“- und „Zurück“-Schaltflächen oder Seitenzahlen, um durch den Rest zu navigieren.
        *   *Wenn eine sehr hohe Zahl festgelegt ist:* Alle Bewertungen könnten auf einer Seite geladen werden, was die Seitenladezeit beeinträchtigen kann, wenn es viele Bewertungen gibt.
    *   **Empfohlener Wert:** 5-10
    *   **Händlerszenario / Beispiel:** Wenn ein Produkt viele Bewertungen hat, hält die Einstellung auf 5 oder 10 die Produktseite übersichtlich und lädt schnell, während Kunden dennoch alle Rückmeldungen durchsuchen können.

#### Verwaltung der Bewertungskriterien

Dieser Abschnitt ermöglicht es Ihnen, spezifische Kriterien (z. B. „Qualität“, „Preis“, „Funktionen“) zu definieren, die Kunden zusätzlich zur Gesamtproduktbewertung bewerten können.

-   **Neues Kriterium hinzufügen:**
    *   **Was dies bewirkt:** Ermöglicht Ihnen, einen neuen, spezifischen Aspekt eines Produkts zu erstellen, den Kunden bewerten können (z. B. „Preis-Leistungs-Verhältnis“, „Benutzerfreundlichkeit“, „Haltbarkeit“).
    *   **Auswirkungen einer Änderung dieser Einstellung:** Wenn Sie ein Kriterium hinzufügen, wird es als zusätzliche Bewertungsoption im Bewertungsformular auf der Produktseite angezeigt. Kunden können für jedes von Ihnen definierte Kriterium eine Sternebewertung abgeben.
    *   **Empfohlener Wert:** Fügen Sie Kriterien hinzu, die für Ihre Produkte relevant sind.
    *   **Händlerszenario / Beispiel:** Für einen Elektronikladen könnten Sie Kriterien wie „Leistung“, „Akkulaufzeit“ und „Design“ hinzufügen. Für einen Bekleidungsgeschäft „Passform“, „Materialqualität“ und „Stil“.

-   **Liste der bestehenden Kriterien:**
    *   **Was dies bewirkt:** Zeigt eine Tabelle aller Kriterien an, die Sie zuvor hinzugefügt haben, zusammen mit Optionen zum Bearbeiten oder Löschen.
    *   **Auswirkungen einer Änderung dieser Einstellung:** Sie können den Namen eines Kriteriums ändern (z. B. „Qualität“ in „Produktqualität“) oder ein Kriterium entfernen, wenn es nicht mehr relevant ist. Das Löschen eines Kriteriums entfernt es aus zukünftigen Bewertungseingaben, aber bestehende Bewertungen, die dieses Kriterium verwendet haben, zeigen möglicherweise weiterhin ihre Bewertungen dafür an (abhängig von der Modulimplementierung).
    *   **Empfohlener Wert:** Halten Sie Ihre Kriterienliste aktuell und relevant.
    *   **Händlerszenario / Beispiel:** Wenn Sie eine neue Produktlinie mit einzigartigen Eigenschaften einführen, könnten Sie ein neues Kriterium hinzufügen. Wenn ein Kriterium redundant wird, können Sie es löschen.

#### Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Bewertungen aktivieren | JA | Hauptschalter für das Bewertungssystem. |
| Modulkonfiguration | Bewertungen müssen von einem Mitarbeiter genehmigt werden | JA | Steuert die manuelle Genehmigung von Bewertungen, um Spam/unangemessene Inhalte zu verhindern. |
| Modulkonfiguration | Gastbewertungen zulassen | JA | Ermöglicht nicht angemeldeten Benutzern, Bewertungen abzugeben. |
| Modulkonfiguration | Mindestzeit zwischen 2 Bewertungen desselben Benutzers (in Sekunden) | 3600 (1 Stunde) | Verhindert Bewertungs-Spamming durch einen einzelnen Benutzer. |
| Modulkonfiguration | Bewertungen auf der Produktseite anzeigen | JA | Zeigt oder blendet den Bewertungsbereich auf Produktseiten ein. |
| Modulkonfiguration | Anzahl der Bewertungen pro Seite | 5-10 | Steuert die Paginierung für die Bewertungsliste auf Produktseiten. |
| Modulkonfiguration | Neues Kriterium hinzufügen | N/A | Erstellt spezifische Bewertungsaspekte (z. B. „Qualität“, „Preis“). |
| Modulkonfiguration | Liste der bestehenden Kriterien | N/A | Verwaltet (bearbeiten/löschen) die benutzerdefinierten Bewertungskriterien. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Bewertungen werden nach dem Absenden nicht auf der Produktseite angezeigt.**
A: Überprüfen Sie, ob „Bewertungen müssen von einem Mitarbeiter genehmigt werden“ in der Modulkonfiguration aktiviert ist. Wenn ja, müssen Sie diese manuell in der Administrationsschnittstelle des Moduls genehmigen (normalerweise auf der Konfigurationsseite des Moduls zu finden, wo Sie eine Liste der Bewertungen sehen). Nach der Genehmigung werden sie im Front Office angezeigt.

**F2: Der Bewertungsbereich sieht seltsam aus oder passt nicht zum Design meines Themes.**
A: Dies ist oft ein CSS-Konflikt mit Ihrem benutzerdefinierten PrestaShop-Theme.
    *   **Cache leeren:** Versuchen Sie zuerst, Ihren PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung** zu leeren.
    *   **Theme-Overrides:** Ihr Theme hat möglicherweise eigene Stile für Bewertungselemente oder es fehlen spezifische Stile für dieses Modul. Möglicherweise müssen Sie einen Webmaster beauftragen, das CSS zu überprüfen und benutzerdefinierte Stile anzuwenden, damit es sich nahtlos einfügt. Das Modul stellt eigene CSS-Dateien (`myprestacomments.css` usw.) bereit, aber die Stile Ihres Themes könnten diese überschreiben.

**F3: Kunden beschweren sich, dass sie keine Bewertungen abgeben können oder das Formular nicht angezeigt wird.**
A:
    *   **„Bewertungen aktivieren“ überprüfen:** Stellen Sie sicher, dass der Hauptschalter in der Modulkonfiguration auf JA steht.
    *   **„Bewertungen auf der Produktseite anzeigen“ überprüfen:** Stellen Sie sicher, dass dies ebenfalls aktiviert ist.
    *   **Gastbewertungen:** Wenn nicht angemeldete Benutzer keine Bewertungen abgeben können, überprüfen Sie „Gastbewertungen zulassen“. Wenn es deaktiviert ist, können nur angemeldete Kunden Bewertungen abgeben.
    *   **Mindestzeit zwischen Bewertungen:** Wenn ein bestimmter Benutzer keine Bewertung abgeben kann, erreicht er möglicherweise das Limit „Mindestzeit zwischen 2 Bewertungen“.

**F4: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A: Sie können den Text des Moduls direkt in PrestaShop übersetzen:
    1.  Gehen Sie zu **International > Übersetzungen**.
    2.  Wählen Sie „Übersetzungen installierter Module“ für den „Übersetzungstyp“.
    3.  Wählen Sie Ihr Theme.
    4.  Wählen Sie die Sprache aus, die Sie übersetzen möchten.
    5.  Suchen Sie „Kostenlose Produktbewertungen (Kommentare)“ in der Modulliste und klicken Sie auf „Ändern“. Sie können dann alle übersetzbaren Zeichenfolgen bearbeiten.

**F5: Ich möchte eine unangemessene oder Spam-Bewertung entfernen.**
A: Navigieren Sie zur Konfigurationsseite des Moduls im Back Office. Dort sollten Sie eine Liste aller eingereichten Bewertungen sehen. Von dort aus können Sie Bewertungen typischerweise „Löschen“ oder „Ablehnen“. Wenn Sie „Bewertungen müssen von einem Mitarbeiter genehmigt werden“ aktiviert haben, können Sie sie einfach nicht genehmigen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht
Das Modul „Kostenlose Produktbewertungen (Kommentare)“ (`myprestacomments`) folgt einer Standard-PrestaShop-Modularchitektur, die `ModuleFrontController` für Front-Office-Interaktionen und `Module` für seine Hauptkonfiguration und Hook-Verwaltung nutzt. Es verwendet eine benutzerdefinierte Datenbanktabelle zum Speichern von Bewertungsdaten und stützt sich auf Smarty-Templates für die Darstellung sowohl der Front-Office-Bewertungsanzeigen als auch der Back-Office-Konfigurationsformulare. Das Modul integriert sich in das PrestaShop-Hook-System, um seine Inhalte in Produktseiten einzufügen.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   `controllers/front/default.php`
        *   **Klassenname & Elternklasse**: `MyPrestaCommentsDefaultModuleFrontController` erweitert `ModuleFrontController`
        *   **Verantwortlichkeit**: Dieser Controller handhabt wahrscheinlich die anfängliche Anzeige von Bewertungen auf der Produktseite oder dient als Fallback für allgemeine bewertungsbezogene Aktionen. Er würde typischerweise Bewertungen für ein bestimmtes Produkt abrufen und diese an das Smarty-Template übergeben.
    *   `controllers/front/feedback.php`
        *   **Klassenname & Elternklasse**: `MyPrestaCommentsFeedbackModuleFrontController` erweitert `ModuleFrontController`
        *   **Verantwortlichkeit**: Dieser Controller ist der Einreichung neuer Bewertungen gewidmet. Er verarbeitet POST-Anfragen vom Bewertungsformular, validiert die Eingabe (Bewertung, Kommentar, Kriterien), prüft Gastbewertungsberechtigungen und Zeitlimits und speichert dann die Bewertung in der Datenbank. Er verwaltet auch den Genehmigungsstatus basierend auf der Modulkonfiguration.
    *   `controllers/front/index.php`
        *   **Klassenname & Elternklasse**: `MyPrestaCommentsIndexModuleFrontController` erweitert `ModuleFrontController`
        *   **Verantwortlichkeit**: Dieser Controller könnte als allgemeiner Einstiegspunkt dienen oder AJAX-Anfragen im Zusammenhang mit Bewertungen bearbeiten, wie z. B. das Laden weiterer Bewertungen über Paginierung oder die Handhabung der „Missbrauch melden“-Funktionalität.

-   **Back-Office-Admin-Controller**:
    *   Es sind keine dedizierten benutzerdefinierten Admin-Controller (`controllers/admin/`) aufgeführt. Dies deutet darauf hin, dass die Verwaltung von Bewertungen (Auflistung, Genehmigung, Löschen) direkt innerhalb der Methode `getContent()` der Hauptmoduldatei (`index.php`) oder über einen Standard-`AdminController` erfolgt, den das Modul erweitert oder integriert. Das Vorhandensein der Templates `list_action_approve.tpl` und `list_action_noabuse.tpl` deutet stark darauf hin, dass die Bewertungsverwaltung in eine Standard-PrestaShop-Listenansicht integriert ist, wahrscheinlich innerhalb der eigenen Konfigurationsseite des Moduls.

### 4.3 Kernklassen & Modelle (`classes/`)
Es sind keine benutzerdefinierten Klassen im Verzeichnis `classes/` aufgeführt. Dies impliziert, dass das Modul möglicherweise einen direkteren Ansatz für die Datenbankinteraktion innerhalb seiner Hauptmoduldatei oder Controller verwendet, oder es könnte bestehende PrestaShop `ObjectModel`s nutzen, falls zutreffend (obwohl unwahrscheinlich für benutzerdefinierte Bewertungsdaten). Es ist wahrscheinlich, dass die Bewertungsdatenstruktur direkt in `install.sql` und der `index.php` des Moduls verwaltet wird.

### 4.4 JavaScript-Assets (`views/js/`)

-   `js/jquery.rating.pack.js`
    *   **Geltungsbereich**: Front-Office
    *   **Beschreibung**: Ein jQuery-Plugin zum Erstellen interaktiver Sternebewertungs-Widgets. Es handhabt die visuelle Anzeige von Sternen und erfasst die Bewertungsauswahl des Benutzers im Bewertungsformular.
-   `js/jquery.textareaCounter.plugin.js`
    *   **Geltungsbereich**: Front-Office
    *   **Beschreibung**: Ein jQuery-Plugin zum Zählen von Zeichen oder Wörtern in einem Textbereich, oft verwendet, um Benutzern Echtzeit-Feedback zur Länge ihrer Bewertung zu geben.
-   `js/moderate.js`
    *   **Geltungsbereich**: Back-Office
    *   **Beschreibung**: Dieses Skript handhabt wahrscheinlich AJAX-Aktionen zur Moderation von Bewertungen im Back Office. Es wäre verantwortlich für das Genehmigen, Ablehnen oder Löschen von Bewertungen ohne vollständiges Neuladen der Seite, wobei es mit der `getContent()`-Methode des Moduls oder einem versteckten Admin-Controller interagiert.
-   `js/myprestacomments.js`
    *   **Geltungsbereich**: Front-Office
    *   **Beschreibung**: Das Haupt-JavaScript für das Modul. Es orchestriert die Front-Office-Bewertungsfunktionalität, einschließlich:
        *   Initialisierung von `jquery.rating.pack.js` für Sternebewertungen.
        *   Handhabung der Übermittlung des Bewertungsformulars (potenziell über AJAX).
        *   Anzeige von Erfolgs- oder Fehlermeldungen.
        *   Verwaltung der Paginierung oder „Mehr laden“-Funktionalität für Bewertungen.
        *   Potenziell Handhabung von „Missbrauch melden“-Klicks.
-   `js/productCriterion.js`
    *   **Geltungsbereich**: Back-Office
    *   **Beschreibung**: Dieses Skript wird im Back Office zur Verwaltung von Bewertungskriterien verwendet. Es handhabt wahrscheinlich das dynamische Hinzufügen, Bearbeiten und Löschen von Kriterienfeldern auf der Konfigurationsseite des Moduls, möglicherweise unter Verwendung von AJAX zur Aktualisierung der Datenbank.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `myprestacomments.css`
    *   **Geltungsbereich**: Front-Office & Back-Office
    *   **Beschreibung**: Das primäre Stylesheet für das Modul, das allgemeine Stile für den Bewertungsbereich, Sternebewertungen, Bewertungsformulare und potenziell einige grundlegende Admin-Panel-Stile enthält.
    *   **Wichtige Selektoren**: `.myprestacomments_block`, `.myprestacomments_review_list`, `.myprestacomments_form`, `.star_content`, `.comment_item`, `.review_rating`.
-   `myprestacomments16.css`
    *   **Geltungsbereich**: Front-Office & Back-Office
    *   **Beschreibung**: Wahrscheinlich ein Kompatibilitäts-Stylesheet für PrestaShop 1.6.x, das spezifische Überschreibungen oder Anpassungen für die Standard-Theme-Struktur dieser Version enthält.
-   `myprestacomments24.css`
    *   **Geltungsbereich**: Front-Office & Back-Office
    *   **Beschreibung**: Wahrscheinlich ein Kompatibilitäts-Stylesheet für PrestaShop 1.7.x oder 8.x, das spezifische Überschreibungen oder Anpassungen für die Standard-Theme-Struktur dieser Versionen (z. B. Classic-Theme) enthält.
-   `myprestacomments32.css`
    *   **Geltungsbereich**: Front-Office & Back-Office
    *   **Beschreibung**: Wahrscheinlich ein Kompatibilitäts-Stylesheet für PrestaShop 9.x, das spezifische Überschreibungen oder Anpassungen für die neueste Standard-Theme-Struktur enthält.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `myprestacomments/mypresta_myprestacomments.tpl`
        *   **Hook**: Wahrscheinlich `displayProductButtons` oder `displayProductExtraContent` (oder ähnliche Produktseiten-Hooks).
        *   **Ausgabe**: Dies ist das Haupt-Template zur Anzeige der Bewertungszusammenfassung (durchschnittliche Bewertung, Anzahl der Bewertungen) und des „Bewertung schreiben“-Buttons/Links auf der Produktseite. Es fungiert oft als Wrapper für die vollständige Bewertungsliste und das Formular.
    *   `myprestacomments/mypresta_myprestacomments_reviews_list.tpl`
        *   **Hook**: Wird innerhalb von `mypresta_myprestacomments.tpl` gerendert oder direkt gehookt, wenn das Modul einen separaten Tab verwendet.
        *   **Ausgabe**: Zeigt die tatsächliche Liste der einzelnen Kundenbewertungen an, einschließlich ihrer Bewertungen, Titel, Kommentare und Rezensenteninformationen. Es wird auch die Paginierung behandeln.

-   **Admin-Templates (`views/templates/admin/`)**:
    *   `myprestacomments/views/templates/admin/advert.tpl`
        *   **Ausgabe**: Zeigt wahrscheinlich eine Werbung oder eine Werbebotschaft von MyPresta.eu innerhalb der Konfigurationsseite des Moduls an.
    *   `myprestacomments/views/templates/admin/list_action_approve.tpl`
        *   **Ausgabe**: Ein Template-Fragment für eine „Genehmigen“-Aktionsschaltfläche oder einen Link, der in einer Liste ausstehender Bewertungen im Back Office verwendet wird.
    *   `myprestacomments/views/templates/admin/list_action_noabuse.tpl`
        *   **Ausgabe**: Ein Template-Fragment für eine „Als nicht missbräuchlich markieren“-Aktionsschaltfläche oder einen Link, der in einer Liste gemeldeter Bewertungen im Back Office verwendet wird.
    *   `myprestacomments/views/templates/admin/_configure/helpers/form/form.tpl`
        *   **Ausgabe**: Dies ist ein Standard-PrestaShop-Helfer-Template-Override, das verwendet wird, um das Konfigurationsformular des Moduls (allgemeine Einstellungen, Kriterienverwaltung) im Back Office zu rendern. Es definiert das Layout und die Eingabefelder für die `getContent()`-Methode.
    *   `myprestacomments/views/templates/admin/_configure/helpers/list/list_content.tpl`
        *   **Ausgabe**: Ein weiterer Standard-PrestaShop-Helfer-Template-Override, der verwendet wird, um die Liste der Bewertungen (oder Kriterien) im Back Office zu rendern, einschließlich Spalten für Bewertungsdetails, Status und Aktionsschaltflächen (genehmigen, löschen).

-   **Front-Office-Templates (`views/templates/front/`)**:
    *   `myprestacomments/views/templates/front/feedback.tpl`
        *   **Ausgabe**: Das Template für das Bewertungsformular selbst. Dies umfasst die Sternebewertungseingabe, Textfelder für Titel und Kommentar und potenziell Felder für benutzerdefinierte Kriterienbewertungen. Es wird gerendert, wenn ein Kunde auf „Bewertung schreiben“ klickt.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   `myprestacomments/install.sql`: Diese Datei enthält die SQL-Anweisungen, die während der Modulinstallation ausgeführt werden. Sie definiert mindestens eine benutzerdefinierte Tabelle:
        *   `ps_myprestacomments_reviews`: Speichert die eigentlichen Bewertungsdaten (Produkt-ID, Kunden-ID, Bewertung, Titel, Kommentar, Datum, Genehmigungsstatus, Missbrauchsstatus).
        *   `ps_myprestacomments_criteria`: Speichert die vom Händler definierten benutzerdefinierten Bewertungskriterien (z. B. „Qualität“, „Preis“).
        *   `ps_myprestacomments_review_criterion`: Eine Verknüpfungstabelle, wenn Bewertungen mehrere Kriterien bewerten können.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Um CSS- und JS-Dateien des Moduls global oder bedingt einzubinden. |
| `displayProductExtraContent` | Auf der Produktseite, typischerweise unter der Hauptproduktbeschreibung oder in einem Tab. | Zur Anzeige der Bewertungszusammenfassung, der Liste der Bewertungen und des „Bewertung schreiben“-Formulars. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des „In den Warenkorb“-Buttons. | Um einen schnellen Link oder Button zum Bewertungsbereich anzuzeigen. |
| `displayFooter` | Im Footer jeder Seite. | Weniger verbreitet, könnte aber für einen allgemeinen Link zu Bewertungen oder modulspezifischen Inhalten verwendet werden. |
| `displayLeftColumn` / `displayRightColumn` | In der linken oder rechten Seitenleiste. | Könnte verwendet werden, um einen Block mit aktuellen Bewertungen oder eine Bewertungszusammenfassung anzuzeigen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Potenziell verwendet, um eine E-Mail an den Kunden auszulösen, in der er um eine Bewertung der gekauften Produkte gebeten wird. |
| `actionProductUpdate` | Nachdem ein Produkt im Back Office aktualisiert wurde. | Um bei Bedarf den Cache im Zusammenhang mit Produktbewertungen zu leeren. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Nachdem ein Produkt hinzugefügt oder aktualisiert wurde. | Um die Integrität der Bewertungsdaten oder die Cache-Invalidierung sicherzustellen. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Kostenlose Produktbewertungen (Kommentare)“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei modulbezogenen Problemen zur Seite und sorgt dafür, dass Ihr Shop reibungslos läuft.
