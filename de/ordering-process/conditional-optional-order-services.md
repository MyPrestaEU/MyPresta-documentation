---
title: "Bedingte optionale Bestelldienste – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bedingte optionale Bestelldienste“ von MyPresta.eu."
sidebar:
  label: "Bedingte optionale Bestelldienste – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Conditional Optional Order Services auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/conditional-optional-order-services.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/conditional-optional-order-services/)
>
> ---


# Bedingte optionale Bestelldienste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Bedingte optionale Bestelldienste“ bietet eine leistungsstarke Reihe von Tools zur Verwaltung Ihrer optionalen Dienste. Sie werden hauptsächlich über die dedizierten Menüeinträge im PrestaShop Back Office mit dem Modul interagieren.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der erste Bildschirm, den Sie nach der Installation des Moduls oder nach dem Klicken auf „Konfigurieren“ im Modul-Manager sehen. Er bietet eine schnelle Möglichkeit, die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren.

- **Einstellungsname:** Bedingte optionale Bestelldienste aktivieren
- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul. Wenn aktiviert, wird die Logik des Moduls ausgeführt und Ihre definierten Dienste werden den Kunden basierend auf Ihren Richtlinien angeboten. Wenn deaktiviert, werden keine Dienste angeboten und das Modul ist im Front-Office effektiv inaktiv.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul beginnt, Ihre Servicerichtlinien zu bewerten und relevante Dienste den Kunden im Front-Office (z. B. Checkout-Seite) anzuzeigen.
  - *Wenn deaktiviert:* Alle bedingten Dienste werden vor Kunden verborgen und die Logik des Moduls wird nicht ausgeführt.
- **Empfohlener Wert:** **JA** (Aktiviert), sobald Sie Ihre Richtlinien konfiguriert haben.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und sind bereit, Ihre Dienste zu definieren. Sie würden diese Einstellung aktivieren, um Ihre Dienste für Kunden sichtbar zu machen, sobald sie konfiguriert sind. Wenn Sie das Anbieten aller Dienste vorübergehend einstellen müssen (z. B. während der Wartung oder einer Feiertagsperiode), können Sie es hier schnell deaktivieren, ohne Ihre Richtlinien zu löschen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Nach der Erstkonfiguration finden Sie neue Menüeinträge unter **Verkaufen > Bestelldienste** (oder einem ähnlichen Ort, je nach Ihrer PrestaShop-Version und Ihrem Theme).

#### 2.2.1 Richtlinien (Back Office > Verkaufen > Bestelldienste > Richtlinien)

Hier definieren und verwalten Sie alle Ihre bedingten optionalen Bestelldienste. Jede „Richtlinie“ repräsentiert einen spezifischen Dienst, den Sie anbieten möchten, zusammen mit den Regeln, die bestimmen, wann und wem er angeboten wird.

- **Bildschirmname & Menüpfad:** Richtlinien (Unter **Verkaufen > Bestelldienste** im Hauptmenü von PrestaShop).
- **Verfügbare Aktionen & Einstellungen:**

  - **Richtlinienliste:** Eine Tabelle, die alle von Ihnen erstellten Richtlinien anzeigt, mit ihrem Namen, Status (aktiv/inaktiv) und anderen wichtigen Informationen.
  - **Neue Richtlinie hinzufügen:** Klicken Sie auf diese Schaltfläche, um einen brandneuen optionalen Dienst zu erstellen.
  - **Richtlinie bearbeiten:** Klicken Sie auf das „Bearbeiten“-Symbol neben einer bestehenden Richtlinie, um deren Details, Bedingungen und Regeln zu ändern.
  - **Richtlinie duplizieren:** Eine sehr nützliche Funktion! Klicken Sie auf das „Duplizieren“-Symbol, um eine exakte Kopie einer bestehenden Richtlinie zu erstellen. Dies spart Zeit, wenn Sie ähnliche Dienste erstellen müssen.
  - **Richtlinie löschen:** Entfernen Sie eine Richtlinie dauerhaft.
  - **Massenaktionen:** Wählen Sie mehrere Richtlinien aus und führen Sie Aktionen wie „Aktivieren“, „Deaktivieren“ oder „Löschen“ gleichzeitig aus.
- **Beim Hinzufügen/Bearbeiten einer Richtlinie konfigurieren Sie:**

  - **Allgemeine Informationen:**
    - **Name:** Ein klarer, interner Name für Ihre Richtlinie (z. B. „Geschenkverpackungsservice“, „Expressversandversicherung“).
    - **Status:** Aktivieren oder deaktivieren Sie diese spezifische Richtlinie. Eine inaktive Richtlinie wird Kunden niemals angezeigt.
    - **Beschreibung:** Der Text, den Kunden sehen werden, um den Dienst zu erklären. Seien Sie prägnant und heben Sie Vorteile hervor.
    - **Preis:** Die Kosten dieses optionalen Dienstes. Dieser wird dem Warenkorb des Kunden hinzugefügt, wenn er ausgewählt wird.
    - **Steuerregel:** Wählen Sie die anwendbare Steuerregel für diesen Dienst aus (z. B. „Standardsatz“, „Ermäßigter Satz“).
    - **Bild/Symbol:** Laden Sie ein Bild oder Symbol hoch, um den Dienst Kunden visuell darzustellen. Dies macht ihn ansprechender und leichter identifizierbar.
  - **Bedingungen:** Dies ist der Kern der Leistungsfähigkeit des Moduls. Hier erstellen Sie Regeln mit einem visuellen Bedingungseditor, um zu bestimmen, *wann* dieser Dienst angeboten werden soll.
    - Sie können mehrere Bedingungen mit „UND“- oder „ODER“-Logik kombinieren.
    - **Beispiele für Bedingungen:**
      - **Warenkorbwert:** Dienst nur anbieten, wenn der Warenkorb-Gesamtbetrag über/unter einem bestimmten Betrag liegt.
      - **Produkt im Warenkorb:** Dienst nur anbieten, wenn bestimmte Produkte oder Produkte aus bestimmten Kategorien/Herstellern im Warenkorb sind.
      - **Kundengruppe:** Dienst nur bestimmten Kundengruppen anbieten (z. B. „Großhändler“, „VIP-Kunden“).
      - **Versanddienstleister:** Dienst nur anbieten, wenn ein bestimmter Versanddienstleister ausgewählt ist.
      - **Datumsbereich:** Dienst nur während eines bestimmten Aktionszeitraums anbieten.
      - **Land/Zone:** Dienst nur Kunden aus bestimmten Ländern oder Versandzonen anbieten.
  - **Anzeigeeinstellungen:** Steuern Sie, wie der Dienst im Front-Office erscheint.
    - **Position:** Wenn mehrere Dienste angeboten werden, können Sie deren Anzeigereihenfolge festlegen.
    - **Sichtbarkeit:** Wo genau im Checkout-Prozess der Dienst erscheint.
- **Auswirkung von Änderungen:**

  - Das Hinzufügen einer neuen Richtlinie macht einen neuen optionalen Dienst für die Anzeige an Kunden verfügbar, vorbehaltlich seiner Bedingungen.
  - Das Bearbeiten einer Richtlinie ändert ihren Namen, Preis, ihre Beschreibung, ihr Bild oder die Bedingungen, unter denen sie angeboten wird. Diese Änderungen werden sofort im Front-Office widergespiegelt.
  - Das Aktivieren/Deaktivieren einer Richtlinie steuert ihre Sichtbarkeit für Kunden.
  - Das Löschen einer Richtlinie entfernt sie vollständig, und sie wird nicht mehr angeboten.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. Beginnen Sie mit der Definition Ihrer gängigsten Dienste (z. B. Geschenkverpackung, Versicherung).
  2. Verwenden Sie den Bedingungseditor, um diese Dienste hochrelevant zu machen. Zum Beispiel könnte Geschenkverpackung nur für physische Produkte angeboten werden, nicht für digitale Downloads.
  3. Überprüfen Sie Ihre Richtlinien regelmäßig, insbesondere vor Aktionen oder saisonalen Verkäufen, um sicherzustellen, dass sie aktiv und korrekt konfiguriert sind.
  4. Nutzen Sie die Funktion „Duplizieren“, um schnell Variationen bestehender Dienste zu erstellen (z. B. „Premium-Geschenkverpackung“ vs. „Standard-Geschenkverpackung“).

#### 2.2.2 Audit-Log (Back Office > Verkaufen > Bestelldienste > Audit-Log)

Dieser Bildschirm bietet eine detaillierte Historie aller Aktionen im Zusammenhang mit den Richtlinien und Diensten des Moduls. Es ist ein unschätzbares Werkzeug zur Nachverfolgung von Änderungen und zur Fehlerbehebung.

- **Bildschirmname & Menüpfad:** Audit-Log (Unter **Verkaufen > Bestelldienste** im Hauptmenü von PrestaShop).
- **Verfügbare Aktionen & Einstellungen:**
  - **Protokollliste:** Eine Tabelle, die eine chronologische Liste von Ereignissen anzeigt.
  - **Spalten umfassen typischerweise:**
    - **Datum:** Wann das Ereignis aufgetreten ist.
    - **Mitarbeiter:** Welcher Back Office-Benutzer die Aktion ausgeführt hat.
    - **Aktion:** Welche Aktion ausgeführt wurde (z. B. „Richtlinie hinzugefügt“, „Richtlinie bearbeitet“, „Richtlinie gelöscht“, „Modul aktiviert/deaktiviert“).
    - **Details:** Spezifische Informationen zur Änderung (z. B. welche Richtlinie betroffen war, welche Werte geändert wurden).
  - **Filtern/Suchen:** Tools zum Filtern des Protokolls nach Datum, Mitarbeiter oder Aktionstyp, um spezifische Ereignisse zu finden.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient nur zur Ansicht; Sie können hier keine direkten Änderungen vornehmen. Er dient als Aufzeichnung aller Änderungen, die an der Konfiguration und den Richtlinien des Moduls vorgenommen wurden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Verwenden Sie das Audit-Log, um nachzuverfolgen, wer Änderungen an Ihren Servicerichtlinien vorgenommen hat, insbesondere in Umgebungen mit mehreren Benutzern.
  - Wenn ein Dienst nicht wie erwartet angezeigt wird, überprüfen Sie das Audit-Log, um festzustellen, ob eine Richtlinie versehentlich deaktiviert oder geändert wurde.
  - Überwachen Sie das Protokoll auf unerwartetes Modulverhalten.

#### 2.2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Bedingte optionale Bestelldienste aktivieren | JA (nach der Einrichtung) | Hauptschalter für die Front-Office-Funktionalität des Moduls. |
| **Richtlinien (Liste)** | Neue Richtlinie hinzufügen | N/A | Erstellen Sie einen neuen optionalen Dienst mit eigenen Regeln und Preisen. |
| **Richtlinien (Liste)** | Richtlinie bearbeiten | N/A | Ändern Sie die Details, Bedingungen oder Anzeige eines bestehenden Dienstes. |
| **Richtlinien (Liste)** | Richtlinie duplizieren | N/A | Erstellen Sie schnell eine Kopie einer bestehenden Richtlinie, um Zeit zu sparen. |
| **Richtlinien (Liste)** | Richtlinie löschen | N/A | Entfernen Sie einen optionalen Dienst dauerhaft. |
| **Richtlinien (Bearbeitungsformular)** | Name | Beschreibender Name | Interne Kennung für den Dienst. |
| **Richtlinien (Bearbeitungsformular)** | Status | Aktiviert | Steuert, ob dieser spezifische Dienst aktiv und für Kunden sichtbar ist. |
| **Richtlinien (Bearbeitungsformular)** | Beschreibung | Klare Erklärung | Text, der Kunden über den Dienst angezeigt wird. |
| **Richtlinien (Bearbeitungsformular)** | Preis | 0.00 (Wert festlegen) | Kosten, die dem Warenkorb hinzugefügt werden, wenn der Dienst ausgewählt wird. |
| **Richtlinien (Bearbeitungsformular)** | Steuerregel | Standard-Steuerregel | Anwendbare Steuer für den Dienst. |
| **Richtlinien (Bearbeitungsformular)** | Bild/Symbol | Hochgeladenes Bild | Visuelle Darstellung des Dienstes für Kunden. |
| **Richtlinien (Bearbeitungsformular)** | Bedingungen (Builder) | Benutzerdefinierte Regeln | Definiert, *wann* und *wem* der Dienst angeboten wird (z. B. Warenkorbwert, Produkt im Warenkorb, Kundengruppe). |
| **Richtlinien (Bearbeitungsformular)** | Position | Auto (Wert festlegen) | Anzeigereihenfolge, wenn mehrere Dienste angeboten werden. |
| **Audit-Log** | (Alle Einträge) | N/A | Bietet eine historische Aufzeichnung aller Änderungen an Moduleinstellungen und Richtlinien. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine optionalen Dienste werden auf der Checkout-Seite nicht angezeigt. Was sollte ich überprüfen?**
A1:

1.  **Modul aktiviert?** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Bedingte optionale Bestelldienste“ und stellen Sie sicher, dass es aktiviert ist.
2.  **Richtlinienstatus?** Gehen Sie zu **Verkaufen > Bestelldienste > Richtlinien**. Stellen Sie sicher, dass die spezifische Richtlinie, die Sie erwarten, „Aktiv“ ist.
3.  **Richtlinienbedingungen erfüllt?** Dies ist der häufigste Grund. Überprüfen Sie sorgfältig die Bedingungen, die Sie für die Richtlinie festgelegt haben. Erfüllt Ihr aktueller Testwarenkorb *alle* „UND“-Bedingungen und *eine* der „ODER“-Bedingungen? Wenn Sie beispielsweise „Warenkorb-Gesamtbetrag > 50 $“ festgelegt haben und Ihr Warenkorb 45 $ beträgt, wird der Dienst nicht angezeigt.
4.  **Cache?** Leeren Sie Ihren PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung**. Manchmal können alte zwischengespeicherte Daten verhindern, dass neue Modulkonfigurationen angezeigt werden.
5.  **Theme-Kompatibilität?** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, können sehr stark angepasste Themes geringfügige Anpassungen erfordern. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler.

**F2: Der Preis meines Dienstes wird nicht korrekt zum Warenkorb-Gesamtbetrag hinzugefügt.**
A2:

1.  **Richtlinienpreis festgelegt?** Überprüfen Sie das Feld „Preis“ in Ihrer Richtlinienkonfiguration.
2.  **Steuerregel angewendet?** Stellen Sie sicher, dass die korrekte „Steuerregel“ für den Dienst ausgewählt ist. Der Endpreis beinhaltet Steuern basierend auf dieser Regel.
3.  **Währung?** Überprüfen Sie, ob der Preis in der Standardwährung Ihres Shops festgelegt ist oder ob die Mehrwährungseinstellungen von PrestaShop korrekt gehandhabt werden.

**F3: Wie übersetze ich die Dienstnamen und Beschreibungen in andere Sprachen?**
A3:

1.  Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2.  Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann Ihre Sprache.
3.  Suchen Sie das Modul „Bedingte optionale Bestelldienste“. Sie sollten die Namen und Beschreibungen Ihrer Richtlinien direkt in den Konfigurationsformularen des Moduls übersetzen können, da sie normalerweise als übersetzbare Felder gespeichert sind. Falls nicht, werden sie hier angezeigt.

**F4: Kann ich die Reihenfolge ändern, in der die Dienste auf der Checkout-Seite erscheinen?**
A4: Ja, innerhalb der Konfiguration jeder Richtlinie sollte es eine Einstellung „Position“ geben. Sie können einen numerischen Wert (z. B. 10, 20, 30) festlegen, um die Anzeigereihenfolge zu steuern. Kleinere Zahlen erscheinen zuerst.

**F5: Das Modul verursacht ein visuelles Problem oder einen Konflikt mit einem anderen Modul.**
A5:

1.  **Problem isolieren:** Deaktivieren Sie vorübergehend andere kürzlich installierte oder aktualisierte Module, um zu sehen, ob der Konflikt verschwindet.
2.  **Auf Fehler prüfen:** Verwenden Sie die Entwicklerkonsole Ihres Browsers (F12), um nach JavaScript- oder CSS-Fehlern zu suchen.
3.  **Support kontaktieren:** Wenn Sie das Problem nicht lösen können, geben Sie dem MyPresta.eu-Support Details zum Problem, Ihrer PrestaShop-Version und allen anderen Modulen, die Sie als Konfliktursache vermuten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Bedingte optionale Bestelldienste“ und richtet sich an Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einem robusten MVC-Muster (Model-View-Controller), das typisch für PrestaShop-Module ist. Es stützt sich stark auf das Hook-System von PrestaShop, um seine Funktionalität an verschiedenen Stellen im Front-Office (Checkout, Produktseite) und Back-Office (Admin-Bestellansicht, Modulkonfiguration) einzuschleusen.
Wichtige Architekturkomponenten sind:

- **Richtlinien (`conorderservicesPolicy`):** Die Kernentität, die einen optionalen Dienst darstellt und `ObjectModel` erweitert.
- **Bedingungen (`conorderservicesCondition`, `conorderservicesConditionGroup`, `conorderservicesConditionTree`):** Ein ausgeklügeltes System zum Erstellen komplexer Regeln zur Bestimmung der Dienstberechtigung.
- **Engine (`conorderservicesEngine`):** Die zentrale Klasse, die für die Bewertung von Bedingungen und die Bestimmung, welche Dienste dem Kunden präsentiert werden sollen, verantwortlich ist.
- **Audit-Log (`conorderservicesAuditLog`):** Zeichnet alle wichtigen Aktionen innerhalb des Moduls zur Nachvollziehbarkeit auf.
- **Kompatibilitätsschicht (`conorderservicesCompatibility`):** Behandelt Unterschiede zwischen PrestaShop 1.7, 8 und 9.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `conorderservices/controllers/front/ajax.php`
  - **Klassenname:** `ConorderservicesAjaxModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Behandelt AJAX-Anfragen vom Front-Office, hauptsächlich für die dynamische Aktualisierung von Dienstauswahlen oder die Neuberechnung von Warenkorb-Gesamtbeträgen, wenn ein Dienst vom Kunden hinzugefügt/entfernt wird. Es leitet wahrscheinlich an die `conorderservicesEngine` weiter, um Berechnungen durchzuführen und JSON-Antworten zurückzugeben.
- `conorderservices/controllers/front/index.php`
  - **Klassenname:** `ConorderservicesIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Ein Platzhalter- oder Fallback-Controller. Wird oft für den direkten Modulzugriff verwendet, falls erforderlich, obwohl die meisten Front-Office-Interaktionen über Hooks oder AJAX erfolgen.

#### Back-Office-Admin-Controller

- `conorderservices/controllers/admin/AdminconorderservicesAuditLog.php`
  - **Klassenname:** `AdminconorderservicesAuditLogController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Audit-Log (unter „Verkaufen > Bestelldienste“)
  - **Verwaltete Entität:** `conorderservicesAuditLog`
  - **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung der Audit-Log-Einträge. Es verwendet PrestaShops `HelperList`, um die Protokolltabelle zu rendern.
- `conorderservices/controllers/admin/AdminconorderservicesPolicies.php`
  - **Klassenname:** `AdminconorderservicesPoliciesController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Richtlinien (unter „Verkaufen > Bestelldienste“)
  - **Verwaltete Entität:** `conorderservicesPolicy`
  - **Verantwortlichkeit:** Der primäre Controller für die Verwaltung optionaler Servicerichtlinien. Er verwaltet das Auflisten, Hinzufügen, Bearbeiten, Duplizieren und Löschen von `conorderservicesPolicy`-Objekten. Er verwendet `HelperList` für die Richtlinienliste und `HelperForm` für die Formulare zum Hinzufügen/Bearbeiten von Richtlinien, einschließlich des komplexen Bedingungseditors.
- `conorderservices/controllers/admin/index.php`
  - **Klassenname:** `AdminconorderservicesIndexController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** (Wahrscheinlich der Haupteinstiegspunkt „Bestelldienste“)
  - **Verwaltete Entität:** Keine direkt, leitet oft zu `AdminconorderservicesPolicies` weiter oder zeigt ein Dashboard an.
  - **Verantwortlichkeit:** Dient als Haupteinstiegspunkt für den Admin-Bereich des Moduls, zeigt möglicherweise ein Dashboard an oder leitet zur Richtlinienliste weiter.

### 4.3 Kernklassen & Modelle (`classes/`)

- `conorderservices/classes/conorderservicesAdmin.php`
  - **Zweck:** Dienstprogrammklasse für admin-spezifische Funktionen, die möglicherweise Berechtigungen, Menügenerierung oder allgemeine Admin-Aufgaben behandelt.
- `conorderservices/classes/conorderservicesAuditLog.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_conorderservices_log`
  - **`$definition`-Felder:** `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`
  - **Zweck:** Repräsentiert einen Eintrag im Audit-Log des Moduls. Bietet Methoden zum Hinzufügen neuer Log-Einträge.
- `conorderservices/classes/conorderservicesCartState.php`
  - **Zweck:** Verwaltet und speichert den Status ausgewählter optionaler Dienste im Warenkorb des Kunden. Interagiert wahrscheinlich mit `Context::getContext()->cart` und speichert Dienstauswahlen.
- `conorderservices/classes/conorderservicesCompatibility.php`
  - **Zweck:** Bietet eine Abstraktionsschicht für PrestaShop-versionsspezifische Funktionen oder Verhaltensweisen, um sicherzustellen, dass das Modul über 1.7, 8 und 9 hinweg funktioniert.
- `conorderservices/classes/conorderservicesCondition.php`
  - **Erweitert:** `ObjectModel` (wahrscheinlich, oder eine Basisklasse für Bedingungen)
  - **Datenbanktabelle:** `ps_conorderservices_condition`
  - **`$definition`-Felder:** `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`
  - **Zweck:** Repräsentiert eine einzelne Bedingung innerhalb einer Bedingungsgruppe (z. B. „Warenkorb-Gesamtbetrag“ „ist größer als“ „100“).
- `conorderservices/classes/conorderservicesConditionEvaluator.php`
  - **Zweck:** Die Logik-Engine zur Bewertung einer Reihe von Bedingungen anhand des aktuellen Warenkorbs, Kunden- und Produktkontexts. Bestimmt, ob die Bedingungen einer Richtlinie erfüllt sind.
- `conorderservices/classes/conorderservicesConditionGroup.php`
  - **Erweitert:** `ObjectModel` (wahrscheinlich)
  - **Datenbanktabelle:** `ps_conorderservices_condition_group`
  - **`$definition`-Felder:** `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR)
  - **Zweck:** Gruppiert mehrere `conorderservicesCondition`-Objekte und definiert die logische Beziehung zwischen ihnen (UND/ODER).
- `conorderservices/classes/conorderservicesConditionTree.php`
  - **Zweck:** Verwaltet die hierarchische Struktur von Bedingungsgruppen und einzelnen Bedingungen, was den Aufbau komplexer Regeln ermöglicht.
- `conorderservices/classes/conorderservicesContext.php`
  - **Zweck:** Ein Wrapper oder eine Erweiterung der PrestaShop-Klasse `Context`, die modulspezifische Kontextdaten (z. B. aktueller Warenkorb, Kunde, Sprache) für die Bedingungsbewertung bereitstellt.
- `conorderservices/classes/conorderservicesDashboard.php`
  - **Zweck:** Bietet Daten und Logik für die Dashboard-Ansicht des Moduls (falls vorhanden), die möglicherweise Analysen oder schnelle Statistiken anzeigt.
- `conorderservices/classes/conorderservicesEngine.php`
  - **Zweck:** Die zentrale Verarbeitungseinheit des Moduls. Sie ruft aktive Richtlinien ab, übergibt sie an den `ConditionEvaluator` und bestimmt, welche Dienste für den aktuellen Warenkorb berechtigt sind. Sie verwaltet auch das Hinzufügen/Entfernen von Dienstprodukten aus dem Warenkorb.
- `conorderservices/classes/conorderservicesListRenderer.php`
  - **Zweck:** Hilfsklasse zum Rendern von Listen im Back Office, möglicherweise erweitert `HelperList` oder bietet benutzerdefinierte Rendering-Logik.
- `conorderservices/classes/conorderservicesLog.php`
  - **Zweck:** Alias oder spezifische Implementierung für die Protokollierung, möglicherweise getrennt von `conorderservicesAuditLog` für verschiedene Arten der Protokollierung.
- `conorderservices/classes/conorderservicesPolicy.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_conorderservices_policy`
  - **`$definition`-Felder:** `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd` (und `_lang`-Felder für übersetzbare `name`, `description`).
  - **Zweck:** Das Kernmodell für einen optionalen Dienst. Speichert alle Konfigurationen für einen Dienst, einschließlich seiner Details, Preise, Bilder und zugehörigen Bedingungsgruppen.
- `conorderservices/classes/conorderservicesPolicyDuplicator.php`
  - **Zweck:** Behandelt die Logik zum Duplizieren einer gesamten Richtlinie, einschließlich ihrer Bedingungen und zugehörigen Daten.
- `conorderservices/classes/conorderservicesPreset.php`
  - **Zweck:** Bietet wahrscheinlich vordefinierte Sätze von Bedingungen oder Richtlinien, die vom Händler schnell geladen werden können.
- `conorderservices/classes/conorderservicesRule.php`
  - **Zweck:** Ein allgemeinerer Begriff für eine Bedingung oder eine Reihe von Bedingungen. Könnte eine abstrakte Basisklasse oder ein spezifischer Regeltyp sein.
- `conorderservices/classes/ConorderservicesRuleImage.php`
  - **Zweck:** Verwaltet die Bilder/Symbole, die mit Richtlinien oder Regeln verknüpft sind.
- `conorderservices/classes/ConorderservicesServiceProduct.php`
  - **Erweitert:** `Product` (oder ein Wrapper darum)
  - **Zweck:** Repräsentiert das „virtuelle Produkt“, das dem Warenkorb hinzugefügt wird, wenn ein Kunde einen optionalen Dienst auswählt. Es stellt sicher, dass der Dienst wie ein reguläres Produkt für die Warenkorb- und Auftragsabwicklung funktioniert.
- `conorderservices/classes/conorderservicesTreeRepository.php`
  - **Zweck:** Verwaltet die Speicherung und den Abruf der Bedingungsbaumstruktur.
- `conorderservices/classes/index.php`
  - **Zweck:** Standardmäßig leere Datei, um das Auflisten von Verzeichnissen zu verhindern.
- `conorderservices/classes/load.php`
  - **Zweck:** Autoloading-Datei oder eine Datei, die andere Klassendefinitionen enthält.

### 4.4 JavaScript-Assets (`views/js/`)

- `conorderservices/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (für Produkt-/Kategorieauswahl im Bedingungseditor)
  - **Details:** Bietet Autocomplete-Funktionalität für Eingabefelder, wahrscheinlich verwendet bei der Auswahl von Produkten, Kategorien oder Herstellern innerhalb des Bedingungseditors.
- `conorderservices/lib/searchTool/views/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (redundant oder spezifisch für eine andere Ansicht des Suchwerkzeugs)
  - **Details:** Ähnlich wie oben, wahrscheinlich eine Duplikat- oder spezifische Version des Autocomplete-Skripts.
- `conorderservices/views/js/adminConditionBuilder.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderservicesPoliciesController`)
  - **Details:** Kern-JS für den visuellen Bedingungseditor. Verwaltet das Hinzufügen/Entfernen von Bedingungen und Bedingungsgruppen, die Verwaltung von Logikoperatoren (UND/ODER) und die Aktualisierung der Benutzeroberfläche basierend auf Benutzereingaben.
- `conorderservices/views/js/adminconorderservicesDashboard.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderservicesIndexController` oder Dashboard-Ansicht)
  - **Details:** Skripte für interaktive Elemente auf dem Dashboard des Moduls, wie Diagramme, Statistiken oder Schnelllinks.
- `conorderservices/views/js/adminconorderservicesSearchTool.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderservicesPoliciesController`)
  - **Details:** Integriert das Suchwerkzeug (Autocomplete) in den Bedingungseditor, sodass Administratoren Entitäten (Produkte, Kategorien usw.) für Bedingungen einfach finden und auswählen können.
- `conorderservices/views/js/adminconorderservicesSimulator.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderservicesPoliciesController` – wahrscheinlich ein dedizierter Tab oder Modal)
  - **Details:** Bietet Funktionalität für einen Richtliniensimulator, der es Administratoren ermöglicht, Bedingungen mit simulierten Warenkorbdaten zu testen, um zu sehen, welche Dienste angeboten würden.
- `conorderservices/views/js/adminPolicyRuleImage.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderservicesPoliciesController`)
  - **Details:** Verwaltet die Bild-Upload- und Vorschaufunktion für Richtliniensymbole/-bilder.
- `conorderservices/views/js/adminPolicyRules.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderservicesPoliciesController`)
  - **Details:** Allgemeine Skripte zur Verwaltung von Richtlinienregeln, möglicherweise einschließlich Drag-and-Drop-Neuordnung oder anderer UI-Interaktionen auf der Richtlinienbearbeitungsseite.
- `conorderservices/views/js/adminSettingsOfferDisplay.js`
  - **Geltungsbereich:** Back-Office (Modul-Hauptkonfiguration oder Richtlinienbearbeitung)
  - **Details:** Skripte zur Konfiguration, wie und wo die optionalen Dienste im Front-Office angezeigt werden.
- `conorderservices/views/js/checkout.js`
  - **Geltungsbereich:** Front-Office (Checkout-Seite)
  - **Details:** Dies ist das kritische Front-Office-Skript. Es überwacht Benutzerinteraktionen (z. B. das Aktivieren/Deaktivieren eines Dienstes), sendet AJAX-Anfragen an `ajax.php`, um den Warenkorb zu aktualisieren, und aktualisiert dynamisch die Warenkorbzusammenfassung und den Gesamtbetrag auf der Checkout-Seite. Es bindet wahrscheinlich an `prestashop.on`-Ereignisse für Warenkorbaktualisierungen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `conorderservices/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office
  - **Details:** Stile für die Autocomplete-Dropdowns und Eingabefelder, die im Admin-Suchwerkzeug verwendet werden.
- `conorderservices/lib/searchTool/views/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office (redundant oder spezifisch für eine andere Ansicht des Suchwerkzeugs)
  - **Details:** Ähnlich wie oben, wahrscheinlich eine Duplikat- oder spezifische Version der Autocomplete-Stile.
- `conorderservices/views/css/admin_conorderservices.css`
  - **Geltungsbereich:** Back-Office
  - **Details:** Allgemeine Stile für die Admin-Seiten des Moduls, einschließlich der Richtlinienliste, des Bedingungseditors und des Audit-Logs. Enthält Stile für Formularelemente, Tabellen und benutzerdefinierte UI-Komponenten.
- `conorderservices/views/css/front.css`
  - **Geltungsbereich:** Front-Office
  - **Details:** Stile für die Anzeige der optionalen Dienste auf der Checkout-Seite. Enthält Stile für den Dienstblock, einzelne Dienstzeilen, Kontrollkästchen, Preise und Symbole. Entwickler können diese Klassen in der `custom.css` oder `theme.css` ihres Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `conorderservices/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Ausgabe:** Zeigt Informationen zu ausgewählten optionalen Diensten in der PrestaShop Back Office Bestellansicht an. Dies ermöglicht Administratoren zu sehen, welche Dienste mit einer Bestellung gekauft wurden.
- `conorderservices/views/templates/hook/checkout_services.tpl`
  - **Hook:** `displayShoppingCart`, `displayShoppingCartFooter` (oder ähnliche Checkout-Hooks)
  - **Ausgabe:** Das Haupttemplate zum Rendern der Liste der verfügbaren optionalen Dienste auf der Front-Office Checkout-Seite. Es durchläuft berechtigte Richtlinien und zeigt sie an.
- `conorderservices/views/templates/hook/partials/checkout_offer_row.tpl`
  - **Hook:** Eingebunden von `checkout_services.tpl`
  - **Ausgabe:** Rendert eine einzelne Zeile oder Karte für einen optionalen Dienst innerhalb der Checkout-Liste, einschließlich seines Namens, seiner Beschreibung, seines Preises und seiner Auswahl-Eingabe (z. B. Kontrollkästchen).

#### Admin-Templates (`views/templates/admin/`)

- `conorderservices/views/templates/admin/auditPreview.tpl`
  - **Zweck:** Rendert eine detaillierte Ansicht oder Vorschau eines Audit-Log-Eintrags.
- `conorderservices/views/templates/admin/dashboard.tpl`
  - **Zweck:** Das Haupttemplate für das Dashboard des Moduls im Back Office, das möglicherweise Analysen oder Zusammenfassungsinformationen anzeigt.
- `conorderservices/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Zweck:** Benutzerdefiniertes Template für die Schaltfläche „Duplizieren“ in `HelperList`-Ansichten (speziell für Richtlinien).
- `conorderservices/views/templates/admin/policiesPreview.tpl`
  - **Zweck:** Rendert eine Vorschau einer Richtlinie, möglicherweise verwendet in einem Simulator oder einer Schnellansicht.
- `conorderservices/views/templates/admin/policyConditionBuilder.tpl`
  - **Zweck:** Das Template für die visuelle Bedingungseditor-Oberfläche innerhalb des Richtlinienbearbeitungsformulars. Dies ist ein komplexes Template, das Bedingungsgruppen und einzelne Bedingungen dynamisch hinzufügt/entfernt.
- `conorderservices/views/templates/admin/policyRuleCard.tpl`
  - **Zweck:** Rendert eine einzelne Regel oder Bedingungsgruppe als Karte innerhalb des Bedingungseditors, wodurch sie visuell unterscheidbar wird.
- `conorderservices/views/templates/admin/policyRulesTable.tpl`
  - **Zweck:** Rendert eine tabellenähnliche Struktur zur Anzeige von Regeln, möglicherweise eine Alternative oder Komponente innerhalb des Bedingungseditors.
- `conorderservices/views/templates/admin/scopeSelector.tpl`
  - **Zweck:** Template zur Auswahl des Geltungsbereichs einer Bedingung (z. B. Produkt, Kategorie, Kunde).

#### Bibliotheks-Templates (`conorderservices/lib/searchTool/views/`)

- `conorderservices/lib/searchTool/views/helpers.tpl`
  - **Zweck:** Hilfs-Templates für das Suchwerkzeug, möglicherweise zum Rendern von Suchergebnissen oder Eingabefeldern.
- `conorderservices/lib/searchTool/views/scripts.tpl`
  - **Zweck:** Enthält JavaScript für das Suchwerkzeug.
- `conorderservices/lib/searchTool/views/views/scripts.tpl`
  - **Zweck:** Duplikat oder spezifische Version der Suchwerkzeug-Skripte.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_conorderservices_policy`
  - Speichert Kernrichtlinieninformationen: `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd`.
  - Enthält auch sprachspezifische Felder für `name` und `description` (z. B. `ps_conorderservices_policy_lang`).
- `ps_conorderservices_condition_group`
  - Speichert Bedingungsgruppen: `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR).
- `ps_conorderservices_condition`
  - Speichert einzelne Bedingungen: `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`.
- `ps_conorderservices_log`
  - Speichert Audit-Log-Einträge: `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`.
- `ps_conorderservices_cart_state` (wahrscheinlich)
  - Speichert, welche Dienste für einen bestimmten Warenkorb ausgewählt sind: `id_cart`, `id_conorderservices_policy`, `date_add`.
- `ps_configuration`
  - `CONORDERSERVICES_ENABLED`: Speichert den Haupt-Aktivierungs-/Deaktivierungsstatus des Moduls.
  - `PS_CURRENCY_DEFAULT`: Wird zur Anzeige von Preisen im Admin verwendet.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `ActionObjectProductInCartDeleteBefore` | Bevor ein Produkt aus dem Warenkorb gelöscht wird. | Stellt sicher, dass, wenn ein für einen Dienst erforderliches Produkt entfernt wird, der Dienst ebenfalls entfernt oder neu bewertet wird. |
| `actionPresentCart` | Wenn die Warenkorbdaten präsentiert werden (z. B. auf der Checkout-Seite). | Fügt die Liste der berechtigten optionalen Dienste in die Warenkorb-Präsentationsdaten ein. |
| `ActionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen und seine Medien (JS/CSS) gesetzt werden. | Fügt modulspezifisches JS und CSS für Back Office-Seiten (Richtlinien, Audit-Log, Bedingungseditor) ein. |
| `ActionPresentProductListing` | Wenn Produktdaten in einer Liste präsentiert werden (z. B. Kategorieseite). | Wird potenziell verwendet, um Dienstverfügbarkeitsindikatoren in Produktlisten anzuzeigen. |
| `ActionValidateOrderBefore` | Bevor eine Bestellung validiert wird. | Führt letzte Überprüfungen der ausgewählten Dienste durch, stellt sicher, dass sie noch gültig sind, und fügt sie als Bestelldetails hinzu. |
| `ActionGetProductPropertiesAfter` | Nachdem Produkteigenschaften abgerufen wurden. | Modifiziert potenziell Produkteigenschaften, wenn ein Dienst diese beeinflusst (z. B. Hinzufügen eines virtuellen Produkts für den Dienst). |
| `DisplayAdminOrder` | Auf der Back Office Bestelldetailseite. | Zeigt die ausgewählten optionalen Dienste an, die mit der Bestellung verknüpft sind. |
| `ActionFrontControllerInitAfter` | Nachdem ein Front-Controller initialisiert wurde. | Initialisiert modulspezifischen Front-Office-Kontext oder Logik. |
| `ActionPresentProduct` | Wenn die Daten eines einzelnen Produkts präsentiert werden (z. B. Produktseite). | Wird potenziell verwendet, um Dienstverfügbarkeitsindikatoren auf Produktseiten anzuzeigen. |
| `ActionPresentCartProduct` | Wenn ein Produkt im Warenkorb präsentiert wird. | Modifiziert die Präsentation von Warenkorbprodukten, wenn Dienste an diese angehängt sind. |
| `ActionProductPriceCalculation` | Während der Produktpreisberechnung. | Stellt sicher, dass Dienstpreise korrekt in den Gesamtbetrag einfließen. |
| `DisplayShoppingCart` | Auf der Warenkorbseite. | Zeigt den Block der optionalen Dienste an. |
| `DisplayShoppingCartFooter` | Im Footer der Warenkorbseite. | Alternative oder zusätzliche Platzierung für den Block der optionalen Dienste. |
| `ActionCartSave` | Nachdem ein Warenkorb gespeichert wurde. | Speichert den Status der ausgewählten optionalen Dienste im Warenkorb. |
| `ActionValidateOrder` | Nachdem eine Bestellung validiert wurde. | Schließt die Bestellung mit den ausgewählten Diensten ab, aktualisiert möglicherweise den Lagerbestand oder löst Folgeaktionen aus. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bedingte optionale Bestelldienste“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
