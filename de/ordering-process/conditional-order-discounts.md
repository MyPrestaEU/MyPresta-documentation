---
title: "Bedingte Bestellrabatte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bedingte Bestellrabatte“ von MyPresta.eu."
sidebar:
  label: "Bedingte Bestellrabatte – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Conditional Order Discounts auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/conditional-order-discounts.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/conditional-order-discounts/)
>
> ---


# Bedingte Bestellrabatte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Moduleinstellungen.

- **Bedingte Bestellrabatte aktivieren:**
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul. Wenn aktiviert, ist die Logik des Moduls zur Anwendung bedingter Rabatte in Ihrem Shop aktiv. Wenn deaktiviert, werden keine bedingten Rabatte angewendet, unabhängig von den von Ihnen erstellten Richtlinien.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, Ihre definierten Rabattrichtlinien zu bewerten und Rabatte oder kostenlose Geschenke auf die Warenkörbe der Kunden anzuwenden, sobald diese qualifiziert sind.
    - *Wenn deaktiviert:* Alle mit diesem Modul erstellten bedingten Rabattrichtlinien werden ignoriert und es werden keine Rabatte angewendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie haben gerade Ihre erste „Kaufe 2, erhalte 1 gratis“-Richtlinie eingerichtet und möchten, dass sie live geht. Sie würden diese Einstellung aktivieren. Wenn Sie alle bedingten Rabatte für einen Shop-weiten Verkauf, der auf andere Weise verwaltet wird, vorübergehend pausieren müssen, würden Sie sie deaktivieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul „Bedingte Bestellrabatte“ fügt Ihrem PrestaShop Back Office einen neuen Hauptmenüpunkt hinzu, normalerweise unter **Katalog** oder **Marketing**, mit dem Namen **„Bedingte Rabatte“**. Dieses Menü enthält mehrere Unterpunkte zur Verwaltung Ihrer Richtlinien und zur Überprüfung von Protokollen.

#### 2.2.1 Bedingte Rabatte > Richtlinien (AdminConorderdisPoliciesController)

Hier definieren und verwalten Sie alle Ihre bedingten Rabattrichtlinien.

- **Bildschirmname & Menüpfad:** Back Office > Bedingte Rabatte > Richtlinien
- **Verfügbare Aktionen & Einstellungen:**

  - **Richtlinienliste:** Sie sehen eine Tabelle mit all Ihren bestehenden Rabattrichtlinien. Jede Richtlinie zeigt ihren Namen, Status (aktiv/inaktiv) und andere wichtige Details.
  - **Neue Richtlinie hinzufügen:** Klicken Sie auf die Schaltfläche „Neue Richtlinie hinzufügen“, um eine brandneue bedingte Rabattregel zu erstellen.
  - **Richtlinie bearbeiten:** Klicken Sie auf das „Bearbeiten“-Symbol neben einer bestehenden Richtlinie, um deren Bedingungen, Werbeaktionen oder Einstellungen zu ändern.
  - **Richtlinie duplizieren:** Dies ist eine sehr nützliche Funktion! Klicken Sie auf das „Duplizieren“-Symbol, um eine exakte Kopie einer bestehenden Richtlinie zu erstellen. Dies spart viel Zeit, wenn Sie ähnliche Werbeaktionen erstellen müssen.
  - **Richtlinie aktivieren/deaktivieren:** Sie können einzelne Richtlinien direkt aus der Liste schnell aktivieren oder deaktivieren.
  - **Richtlinie löschen:** Entfernen Sie eine Richtlinie aus Ihrem Shop.
  - **Richtlinien-Konfigurationsformular (beim Hinzufügen/Bearbeiten):**
    - **Richtlinienname:** Ein beschreibender Name für Ihre interne Referenz (z. B. „BOGO T-Shirts“, „Gib 100 $ aus, erhalte 10 % Rabatt“).
    - **Status (Aktiv/Inaktiv):** Steuert, ob diese spezifische Richtlinie derzeit in Ihrem Shop live ist.
    - **Bedingungs-Builder:** Dies ist der Kern des Moduls. Sie verwenden eine visuelle Oberfläche, um zu definieren, *wann* der Rabatt angewendet wird. Beispiele:
      - „Warenkorb-Gesamtwert ist größer als 100 $“
      - „Kunde ist in Gruppe ‚Großhändler‘“
      - „Produkt ‚X‘ ist im Warenkorb mit Menge >= 2“
      - „Jedes Produkt aus Kategorie ‚Sommer-Sale‘ ist im Warenkorb“
      - Sie können mehrere Bedingungen mit „UND“- oder „ODER“-Logik kombinieren.
    - **Werbeaktions-Builder:** Dies definiert, *welchen* Rabatt oder welches Geschenk der Kunde erhält, wenn die Bedingungen erfüllt sind. Beispiele:
      - „10 % Rabatt auf die gesamte Bestellung anwenden“
      - „Günstigsten Artikel aus Kategorie ‚Accessoires‘ gratis abgeben“
      - „Produkt ‚Geschenkbox‘ kostenlos zum Warenkorb hinzufügen“
      - „50 % Rabatt auf die zweite Einheit von Produkt ‚Y‘ anwenden“
    - **Geltungsbereich-Selektor:** Definieren Sie, für welche Shops (bei Multishop-Einrichtungen), Kundengruppen oder Währungen diese Richtlinie gilt.
    - **Priorität:** Wenn mehrere Richtlinien auf einen einzelnen Warenkorb angewendet werden könnten, bestimmt dies, welche Vorrang hat. Kleinere Zahlen bedeuten höhere Priorität.
    - **Gültigkeitsdaten:** Legen Sie ein Start- und Enddatum für die Werbeaktion fest.
    - **Warenkorb-Simulator:** Ein leistungsstarkes Tool innerhalb des Richtlinien-Editors, mit dem Sie Produkte zu einem simulierten Warenkorb hinzufügen und sofort sehen können, ob Ihre Richtlinie angewendet wird und welcher Rabatt gewährt wird. Dies ist entscheidend für Tests!
- **Auswirkung von Änderungen:**

  - Das Hinzufügen einer neuen Richtlinie macht eine neue Werbeaktion (falls aktiv) in Ihrem Shop verfügbar.
  - Das Bearbeiten einer Richtlinie ändert die Bedingungen oder Werbeaktionen eines bestehenden Angebots.
  - Das Aktivieren/Deaktivieren von Richtlinien steuert direkt deren Sichtbarkeit und Anwendung im Front Office.
  - Das Duplizieren von Richtlinien ermöglicht die schnelle Erstellung ähnlicher Werbeaktionen, ohne von Grund auf neu beginnen zu müssen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. **Planen Sie Ihre Werbeaktion:** Entscheiden Sie sich für das Angebot (z. B. „Kaufe 3, erhalte 1 gratis auf alle Socken“).
  2. **Erstellen Sie eine neue Richtlinie:** Gehen Sie zu „Richtlinien“ und klicken Sie auf „Neue Richtlinie hinzufügen“.
  3. **Definieren Sie Bedingungen:** Verwenden Sie den visuellen Builder, um festzulegen, welche Produkte, Kategorien, Mengen oder Warenkorbwerte den Rabatt auslösen.
  4. **Definieren Sie Werbeaktionen:** Geben Sie den Rabatt-Typ (Prozentsatz, fester Betrag, kostenloses Geschenk) und worauf er angewendet wird, an.
  5. **Gründlich mit dem Warenkorb-Simulator testen:** Fügen Sie vor dem Speichern verschiedene Produkte und Mengen zum Simulator hinzu, um sicherzustellen, dass der Rabatt genau wie beabsichtigt angewendet wird.
  6. **Gültigkeitsdaten und Priorität festlegen:** Stellen Sie sicher, dass die Werbeaktion nur dann läuft, wenn Sie es wünschen, und korrekt mit anderen Werbeaktionen interagiert.
  7. **Richtlinie aktivieren:** Sobald getestet und bereit, setzen Sie ihren Status auf „Aktiv“.
  8. **Mit Audit-Log überwachen:** Überprüfen Sie das Audit-Log (siehe nächster Abschnitt), um zu bestätigen, dass Richtlinien in Live-Warenkörben korrekt angewendet werden.

#### 2.2.2 Bedingte Rabatte > Audit-Log (AdminConorderdisAuditLogController)

Dieser Bildschirm bietet eine detaillierte Historie, wie Ihre bedingten Rabattrichtlinien auf Kundenwarenkörbe angewendet (oder versucht wurden anzuwenden) wurden.

- **Bildschirmname & Menüpfad:** Back Office > Bedingte Rabatte > Audit-Log
- **Verfügbare Aktionen & Einstellungen:**
  - **Protokollliste:** Eine Tabelle, die Einträge für jedes Mal anzeigt, wenn eine Richtlinie ausgewertet wurde. Jeder Eintrag enthält typischerweise:
    - **Datum/Uhrzeit:** Wann das Ereignis aufgetreten ist.
    - **Kunde:** Welcher Kunde (falls angemeldet) beteiligt war.
    - **Warenkorb-ID:** Die ID des Einkaufswagens.
    - **Richtlinienname:** Welche Richtlinie ausgewertet wurde.
    - **Ergebnis:** Ob die Richtlinienbedingungen erfüllt wurden und ob ein Rabatt angewendet wurde.
    - **Details:** Spezifischere Informationen zu den erfüllten Bedingungen, dem angewendeten Rabatt oder warum er nicht angewendet wurde.
  - **Filtern und Suchen:** Sie können das Protokoll nach Datum, Kunde, Richtlinie oder Ergebnis filtern, um bestimmte Ereignisse schnell zu finden.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschützter Bildschirm. Sie nehmen hier keine Änderungen vor, sondern beobachten das Verhalten des Moduls.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - **Fehlerbehebung:** Wenn ein Kunde ein Problem meldet, dass ein Rabatt nicht angewendet wird, oder wenn Sie vermuten, dass eine Richtlinie nicht wie erwartet funktioniert, überprüfen Sie das Audit-Log. Sie können genau sehen, was passiert ist, als sein Warenkorb ausgewertet wurde.
  - **Überwachung:** Überprüfen Sie das Protokoll regelmäßig, um sicherzustellen, dass Ihre Werbeaktionen korrekt ausgelöst werden, und um unerwartetes Verhalten zu identifizieren.
  - **Verständnis der Richtlinieninteraktionen:** Wenn Sie mehrere Richtlinien haben, kann das Protokoll Ihnen helfen zu verstehen, welche Richtlinien berücksichtigt werden und welche letztendlich basierend auf Prioritäten angewendet wird.

#### 2.2.3 Bedingte Rabatte > Dashboard (AdminConorderdisDashboardController)

Dieser Bildschirm bietet einen Überblick und potenziell schnellen Zugriff auf wichtige Modulfunktionen.

- **Bildschirmname & Menüpfad:** Back Office > Bedingte Rabatte > Dashboard
- **Verfügbare Aktionen & Einstellungen:** Dieses Dashboard bietet typischerweise:
  - **Zusammenfassende Statistiken:** Schnelle Zählungen aktiver Richtlinien, aller Richtlinien oder aktueller Audit-Log-Einträge.
  - **Schnelllinks:** Verknüpfungen zu „Neue Richtlinie hinzufügen“, „Richtlinien anzeigen“ oder „Audit-Log anzeigen“.
  - **Simulator-Zugriff:** Ein prominenter Link oder ein eingebettetes Tool für den Warenkorb-Simulator, um Richtlinien schnell zu testen.
  - **Modulstatus:** Angabe, ob das Modul aktiviert oder deaktiviert ist.
- **Auswirkung von Änderungen:** Dies ist primär ein Informations- und Navigationsbildschirm. Änderungen werden über die verknüpften Abschnitte „Richtlinien“ oder „Audit-Log“ vorgenommen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies als Ausgangspunkt für die Verwaltung Ihrer Werbeaktionen, um einen schnellen Überblick über Ihre aktiven Kampagnen zu erhalten und auf den Simulator zum Testen zuzugreifen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Bedingte Bestellrabatte aktivieren | JA | Hauptschalter zum Aktivieren/Deaktivieren aller Modulfunktionen. |
| Richtlinien (Hinzufügen/Bearbeiten) | Richtlinienname | Beschreibender Name | Interne Bezeichnung für Ihre Werbeaktion. |
| Richtlinien (Hinzufügen/Bearbeiten) | Status | Aktiv | Steuert, ob eine bestimmte Richtlinie im Shop live ist. |
| Richtlinien (Hinzufügen/Bearbeiten) | Bedingungs-Builder | Variiert | Definiert Kriterien für die Rabattberechtigung (z. B. Warenkorb-Gesamtwert, Produkte im Warenkorb). |
| Richtlinien (Hinzufügen/Bearbeiten) | Werbeaktions-Builder | Variiert | Definiert den angewendeten Rabatt oder das kostenlose Geschenk (z. B. % Rabatt, kostenloses Produkt). |
| Richtlinien (Hinzufügen/Bearbeiten) | Geltungsbereich-Selektor | Alle Shops/Gruppen/Währungen | Beschränkt die Richtlinienanwendung auf bestimmte Kontexte. |
| Richtlinien (Hinzufügen/Bearbeiten) | Priorität | Kleinere Zahl = höhere Priorität | Bestimmt, welche Richtlinie angewendet wird, wenn mehrere berechtigt sind. |
| Richtlinien (Hinzufügen/Bearbeiten) | Gültigkeitsdaten | Kein Enddatum | Legt den aktiven Zeitraum für die Werbeaktion fest. |
| Richtlinien (Hinzufügen/Bearbeiten) | Warenkorb-Simulator | N/A | Tool zum Testen der Richtlinienanwendung vor dem Speichern. |
| Richtlinien (Liste) | Aktion „Richtlinie duplizieren“ | N/A | Erstellt eine Kopie einer bestehenden Richtlinie und spart Einrichtungszeit. |
| Audit-Log | Protokolleinträge | N/A | Zeichnet jede Richtlinienauswertung auf und zeigt Erfolg/Misserfolg und Details an. |
| Dashboard | Schnelllinks / Zusammenfassung | N/A | Bietet einen Überblick und Verknüpfungen zu wichtigen Modulfunktionen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Rabatt wird nicht angewendet, obwohl ich eine Richtlinie eingerichtet habe.**
A1:

- **Ist das Modul aktiviert?** Überprüfen Sie **Module > Modul-Manager > Bedingte Bestellrabatte** und stellen Sie sicher, dass der Hauptschalter auf EIN steht.
- **Ist die spezifische Richtlinie aktiv?** Gehen Sie zu **Bedingte Rabatte > Richtlinien** und überprüfen Sie die Spalte „Status“ für Ihre Richtlinie.
- **Sind die Bedingungen erfüllt?** Verwenden Sie den **Warenkorb-Simulator** im Richtlinien-Editor. Fügen Sie Produkte genau so zum simulierten Warenkorb hinzu, wie es ein Kunde tun würde. Zeigt der Simulator an, dass der Rabatt angewendet wird? Wenn nicht, überprüfen Sie Ihre Bedingungen sorgfältig.
- **Gültigkeitsdaten überprüfen:** Liegt die Richtlinie innerhalb ihres aktiven Datumsbereichs?
- **Priorität überprüfen:** Wenn mehrere Richtlinien angewendet werden könnten, stellen Sie sicher, dass diejenige, die Sie erwarten, die richtige Priorität hat (kleinere Zahl = höhere Priorität).
- **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal können zwischengespeicherte Daten verhindern, dass neue Regeln sofort wirksam werden.

**F2: Der Rabatt wird angewendet, aber es ist nicht der korrekte Betrag oder das korrekte Produkt.**
A2:

- **Überprüfen Sie Ihren Werbeaktions-Builder:** Überprüfen Sie den Rabatt-Typ (Prozentsatz, fester Betrag), den Wert und worauf er angewendet wird (gesamte Bestellung, bestimmte Produkte, günstigster Artikel usw.).
- **Überprüfen Sie die Bedingungen erneut:** Manchmal kann eine subtile Bedingung zu einem unerwarteten Ergebnis führen. Zum Beispiel, wenn Sie „jedes Produkt aus Kategorie X“ haben, der Kunde aber Produkte aus anderen Kategorien hat, die ebenfalls eine „günstigster Artikel“-Regel erfüllen.
- **Verwenden Sie den Warenkorb-Simulator ausgiebig:** Dies ist Ihr bester Freund, um komplexe Regeln zu überprüfen. Testen Sie Grenzfälle.
- **Audit-Log:** Überprüfen Sie **Bedingte Rabatte > Audit-Log**, um die genauen Details zu sehen, wie das Modul den Warenkorb ausgewertet hat und welchen Rabatt es versucht hat anzuwenden. Dies kann Diskrepanzen aufdecken.

**F3: Mein benutzerdefiniertes Theme zeigt die Rabattnachrichten oder kostenlosen Geschenke nicht deutlich an.**
A3:

- Das Modul integriert sich in die nativen Warenkorbregeln von PrestaShop, sodass der Rabatt selbst in der Warenkorbzusammenfassung erscheinen sollte. Wenn Sie jedoch benutzerdefinierte Nachrichten wie „Sie haben sich für ein kostenloses Geschenk qualifiziert!“ oder „Kaufe 2, erhalte 1 gratis!“ dynamisch auf Produktseiten oder im Warenkorb anzeigen möchten, erfordert dies in der Regel benutzerdefinierte Theme-Anpassungen.
- **Konsultieren Sie einen Entwickler:** Ihr Webmaster oder ein PrestaShop-Entwickler kann Ihnen helfen, dynamische Nachrichten in die `product.tpl`-, `cart.tpl`- oder `checkout.tpl`-Dateien Ihres Themes zu integrieren, möglicherweise unter Verwendung der Hooks des Moduls (siehe Entwicklerhandbuch).

**F4: Kann ich dieses Modul mit anderen Rabattmodulen oder nativen Warenkorbregeln verwenden?**
A4:

- Ja, dieses Modul funktioniert, indem es im Hintergrund native PrestaShop-Warenkorbregeln erstellt und verwaltet. Das bedeutet, dass es im Allgemeinen mit anderen Modulen kompatibel ist, die ebenfalls auf das Kernrabattsystem von PrestaShop angewiesen sind.
- **Priorität ist entscheidend:** Achten Sie auf die Prioritätseinstellungen für Ihre Richtlinien für bedingte Bestellrabatte und alle anderen nativen Warenkorbregeln, die Sie manuell erstellt haben. PrestaShop wendet Rabatte basierend auf ihrer Priorität an. Testen Sie gründlich mit dem Warenkorb-Simulator und überprüfen Sie das Audit-Log, wenn Sie viele überlappende Werbeaktionen haben.

**F5: Wie verwalte ich mehrsprachige Übersetzungen für Richtliniennamen oder Beschreibungen?**
A5:

- Richtliniennamen und alle benutzerdefinierten Texte, die Sie für Bedingungen oder Werbeaktionen eingeben, werden typischerweise direkt im Richtlinien-Bearbeitungsbildschirm verwaltet. Die Standard-Übersetzungsoberfläche von PrestaShop (unter **International > Übersetzungen**) gilt möglicherweise nicht direkt für dynamische Inhalte, die vom Richtlinien-Builder des Moduls generiert werden.
- Wenn das Modul spezifische Felder für verschiedene Sprachen im Richtlinien-Editor bereitstellt, verwenden Sie diese. Andernfalls stellen Sie sicher, dass Ihre Richtliniennamen klar und prägnant sind, oder erwägen Sie, statische Informationsblöcke in Ihrem Theme für verschiedene Sprachen hinzuzufügen, um Werbeaktionen zu erklären.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Architektur des Moduls „Bedingte Bestellrabatte“ und beschreibt dessen Dateistruktur, Klassen, Controller und Integrationspunkte für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Bedingte Bestellrabatte“ ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut. Es nutzt das native `CartRule`-System von PrestaShop stark und fungiert effektiv als erweiterter Regel-Builder und Manager für diese Kernobjekte. Es führt mehrere benutzerdefinierte `ObjectModel`-Klassen zur Verwaltung von Richtlinien, Bedingungen, Werbeaktionen und einem Audit-Log ein. Das Modul verwendet eine robuste Engine, um komplexe Bedingungen anhand des Warenkorbstatus eines Kunden zu bewerten und dann die entsprechenden `CartRule`-Objekte zu materialisieren. Es enthält auch einen ausgeklügelten Bedingungs-Builder und Simulator im Back Office für eine einfache Bedienung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `conorderdis/controllers/front/index.php`
  - **Klassenname:** `ConorderdisIndexModuleFrontController` (oder ähnlich, je nach PrestaShop-Version und Modulstruktur, oft `ModuleFrontController`).
  - **Verantwortlichkeit:** Diese Datei dient typischerweise als Platzhalter oder Standard-Einstiegspunkt für Front-Office-Modulinteraktionen. Im Kontext dieses Moduls sind direkte Front-Office-Controller weniger kritisch, da die meiste Logik über Hooks abgewickelt wird, die mit dem Warenkorb- und Bestellprozess interagieren. Sie könnte AJAX-Anfragen im Zusammenhang mit Warenkorb-Updates oder spezifischen Front-End-Interaktionen verarbeiten, falls implementiert, aber die Kernrabattlogik läuft über Hooks.

#### Back-Office-Admin-Controller

- `conorderdis/controllers/admin/AdminconorderdisAuditLog.php`
  - **Tab-Name:** Bedingte Rabatte > Audit-Log
  - **Verwaltete Entität:** `ConorderdisAuditLog` (bildet auf Tabelle `ps_conorderdis_log` ab).
  - **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung der Audit-Log-Einträge. Erweitert `AdminController` und verwendet `HelperList`, um die Protokolltabelle zu rendern, sodass Administratoren überprüfen können, wie Richtlinien auf Kundenwarenkörbe angewendet oder ausgewertet wurden.
- `conorderdis/controllers/admin/AdminconorderdisPolicies.php`
  - **Tab-Name:** Bedingte Rabatte > Richtlinien
  - **Verwaltete Entität:** `ConorderdisPolicy` (bildet auf Tabelle `ps_conorderdis_policy` ab).
  - **Verantwortlichkeit:** Dies ist der primäre Controller zur Verwaltung von Rabattrichtlinien. Er erweitert `AdminController` und bietet CRUD-Funktionalität (Create, Read, Update, Delete) für Richtlinien. Er integriert die visuellen Bedingungs- und Werbeaktions-Builder, den Produktauswähler und den Warenkorb-Simulator. Er verwendet `HelperList` für die Richtlinienübersicht und `HelperForm` für die Formulare zum Hinzufügen/Bearbeiten von Richtlinien.
- `conorderdis/controllers/admin/index.php`
  - **Verantwortlichkeit:** Dies ist eine Standard-PrestaShop-Praxis, um das Auflisten von Verzeichnissen zu verhindern. Es enthält typischerweise eine einfache `die('No direct script access allowed');`-Anweisung. Es verwaltet keine spezifische Entität und bietet keine Funktionalität über die Sicherheit hinaus.

### 4.3 Kernklassen & Modelle (`classes/`)

- `conorderdis/classes/ConorderdisAdmin.php`
  - **Verantwortlichkeit:** Enthält wahrscheinlich Hilfsmethoden oder Dienstprogramme speziell für die Back-Office-Administration, wie das Rendern spezifischer Formularelemente, die Verarbeitung von AJAX-Anfragen aus Admin-Formularen oder die Verwaltung modulspezifischer Konfigurationen.
- `conorderdis/classes/ConorderdisAuditLog.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_conorderdis_log`
  - **`$definition`-Felder:** Speichert Details zu Richtlinienauswertungen, einschließlich `id_cart`, `id_customer`, `id_policy`, `result`, `details`, `date_add`.
  - **Verantwortlichkeit:** Repräsentiert einen Eintrag im Audit-Log. Bietet Methoden zum Protokollieren von Richtlinienanwendungsereignissen, Erfolgen und Fehlern.
- `conorderdis/classes/ConorderdisCartRuleManager.php`
  - **Verantwortlichkeit:** Verwaltet die Erstellung, Aktualisierung und Löschung nativer PrestaShop `CartRule`-Objekte basierend auf den `ConorderdisPolicy`-Definitionen des Moduls. Diese Klasse ist entscheidend für die Übersetzung der komplexen Regeln des Moduls in Standard-PrestaShop-Rabatte.
- `conorderdis/classes/ConorderdisCartState.php`
  - **Verantwortlichkeit:** Kapselt den aktuellen Status des Warenkorbs eines Kunden und bietet eine Abstraktionsschicht für die Rabatt-Engine zur Bewertung von Bedingungen. Es könnte Methoden zum Abrufen des Warenkorb-Gesamtwerts, der Produktmengen, der Kundengruppe usw. enthalten.
- `conorderdis/classes/ConorderdisCompatibility.php`
  - **Verantwortlichkeit:** Handhabt Kompatibilitätsschichten für verschiedene PrestaShop-Versionen (z. B. 1.7.x, 8.x, 9.x) oder spezifische PHP-Versionen. Es stellt sicher, dass das Modul in allen unterstützten Umgebungen korrekt funktioniert, indem es Polyfills oder alternative Implementierungen für veraltete Funktionen/Methoden bereitstellt.
- `conorderdis/classes/ConorderdisConditionTree.php`
  - **Verantwortlichkeit:** Verwaltet die komplexe logische Struktur von Bedingungen (z. B. „UND“-, „ODER“-Gruppen, verschachtelte Bedingungen). Es parst wahrscheinlich die Bedingungsdaten aus der Datenbank und bietet Methoden zur Bewertung, ob ein gegebener `ConorderdisCartState` die definierten Bedingungen erfüllt.
- `conorderdis/classes/ConorderdisContext.php`
  - **Verantwortlichkeit:** Ein Wrapper um das globale `Context`-Objekt von PrestaShop, der potenziell modulspezifische Kontextdaten hinzufügt oder den Zugriff auf gemeinsame Kontext-Eigenschaften vereinfacht.
- `conorderdis/classes/ConorderdisDashboard.php`
  - **Verantwortlichkeit:** Bietet Daten und Logik für die Back-Office-Dashboard-Ansicht, fasst wichtige Statistiken zusammen und bietet Schnelllinks.
- `conorderdis/classes/ConorderdisEngine.php`
  - **Verantwortlichkeit:** Die Kernlogik-Engine des Moduls. Diese Klasse orchestriert die Bewertung von Richtlinien. Sie nimmt einen `ConorderdisCartState`, iteriert durch aktive `ConorderdisPolicy`-Objekte, bewertet deren `ConorderdisConditionTree` und weist, falls die Bedingungen erfüllt sind, `ConorderdisPromoMaterializer` an, den Rabatt anzuwenden.
- `conorderdis/classes/ConorderdisFreeGift.php`
  - **Verantwortlichkeit:** Handhabt speziell die Logik zum Hinzufügen kostenloser Geschenkprodukte zum Warenkorb, wenn eine Werbeaktion dies vorschreibt. Es interagiert mit dem `Cart`-Objekt, um sicherzustellen, dass das Produkt korrekt hinzugefügt und als kostenlos markiert wird.
- `conorderdis/classes/ConorderdisListRenderer.php`
  - **Verantwortlichkeit:** Eine Hilfsklasse zum Rendern von Listen im Back Office, die möglicherweise `HelperList` erweitert oder benutzerdefinierte Rendering-Logik für bestimmte Spalten oder Aktionen (z. B. die Duplizierungsaktion) bereitstellt.
- `conorderdis/classes/ConorderdisLog.php`
  - **Erweitert:** `ObjectModel` (wahrscheinlich ein Alias oder eine ältere Version von `ConorderdisAuditLog`).
  - **Datenbanktabelle:** `ps_conorderdis_log`
  - **Verantwortlichkeit:** Ähnlich wie `ConorderdisAuditLog` behandelt es die Protokollierung von Modulereignissen.
- `conorderdis/classes/ConorderdisPolicy.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_conorderdis_policy`
  - **`$definition`-Felder:** Speichert alle richtlinienbezogenen Daten, einschließlich `name`, `active`, `conditions_data` (serialisiertes JSON/Array), `promotions_data` (serialisiertes JSON/Array), `priority`, `date_from`, `date_to`, `id_shop`, `id_customer_group`, `id_currency`.
  - **Verantwortlichkeit:** Repräsentiert eine einzelne bedingte Rabattrichtlinie. Bietet Methoden zum Speichern, Laden und Verwalten von Richtliniendaten, einschließlich ihrer Bedingungen und Werbeaktionen.
- `conorderdis/classes/ConorderdisPolicyDuplicator.php`
  - **Verantwortlichkeit:** Handhabt die Logik zum Duplizieren von `ConorderdisPolicy`-Objekten und stellt sicher, dass alle zugehörigen Daten (Bedingungen, Werbeaktionen) korrekt kopiert werden.
- `conorderdis/classes/ConorderdisProductPicker.php`
  - **Verantwortlichkeit:** Bietet Funktionalität zur Auswahl von Produkten, Kategorien oder Herstellern innerhalb des Back-Office-Richtlinien-Builders, wahrscheinlich über ein AJAX-gesteuertes Suchwerkzeug.
- `conorderdis/classes/ConorderdisPromoMaterializer.php`
  - **Verantwortlichkeit:** Nimmt die Ausgabe der `ConorderdisEngine` (d. h. „diese Werbeaktion sollte angewendet werden“) und übersetzt sie in tatsächliche Änderungen im PrestaShop-Warenkorb, hauptsächlich durch Erstellen oder Modifizieren von `CartRule`-Objekten über `ConorderdisCartRuleManager`.
- `conorderdis/classes/ConorderdisPromotionCalculator.php`
  - **Verantwortlichkeit:** Berechnet den genauen Rabattbetrag oder identifiziert das kostenlose Produkt basierend auf den definierten Werberegeln und dem aktuellen Warenkorbstatus.
- `conorderdis/classes/ConorderdisPromotionType.php`
  - **Verantwortlichkeit:** Definiert und verwaltet verschiedene Arten von Werbeaktionen (z. B. prozentualer Rabatt, fester Betrag, kostenloses Geschenk, günstigster Artikel gratis). Es enthält wahrscheinlich Logik, die spezifisch für jeden Werbeaktionstyp ist.
- `conorderdis/classes/ConorderdisRule.php`
  - **Verantwortlichkeit:** Eine generische Klasse, die eine einzelne Regel oder Bedingung innerhalb des `ConorderdisConditionTree` darstellt.
- `conorderdis/classes/ConorderdisSchema.php`
  - **Verantwortlichkeit:** Verwaltet das Datenbankschema des Moduls, einschließlich der Installation und Deinstallation benutzerdefinierter Tabellen (`ps_conorderdis_policy`, `ps_conorderdis_log`).
- `conorderdis/classes/ConorderdisUnitPool.php`
  - **Verantwortlichkeit:** Wahrscheinlich in komplexen „Kaufe N, erhalte M“- oder „günstigster Artikel gratis“-Szenarien verwendet, um einzelne Produkteinheiten im Warenkorb für die Rabattberechnung zu verwalten und zu verfolgen.
- `conorderdis/classes/index.php`
  - **Verantwortlichkeit:** Standard-PrestaShop-Praxis, um das Auflisten von Verzeichnissen zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

- `conorderdis/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (in Admin-Formularen verwendet).
  - **Details:** Bietet Autocomplete-Funktionalität für Eingabefelder, wahrscheinlich im Richtlinien-Builder zur Auswahl von Produkten, Kategorien oder Herstellern verwendet. Bindet an Eingabefelder, führt AJAX-Aufrufe an einen Such-Controller durch und zeigt Vorschläge an.
- `conorderdis/views/js/adminConditionBuilder.js`
  - **Geltungsbereich:** Back-Office (AdminConorderdisPolicies-Controller).
  - **Details:** Treibt die visuelle Bedingungs-Builder-Oberfläche an. Handhabt das Hinzufügen/Entfernen von Bedingungen, das Gruppieren von Bedingungen (UND/ODER), das Auswählen von Bedingungstypen und das dynamische Aktualisieren der Benutzeroberfläche basierend auf Benutzereingaben. Verwaltet die Datenstruktur, die den Bedingungsbaum darstellt.
- `conorderdis/views/js/adminConorderdisDashboard.js`
  - **Geltungsbereich:** Back-Office (AdminConorderdisDashboard-Controller).
  - **Details:** Bietet interaktive Elemente oder dynamische Inhalte für das Modul-Dashboard, wie das Abrufen von Zusammenfassungsstatistiken über AJAX oder das Verarbeiten von Schnelllink-Klicks.
- `conorderdis/views/js/adminConorderdisSearchTool.js`
  - **Geltungsbereich:** Back-Office (AdminConorderdisPolicies-Controller).
  - **Details:** Ein allgemeineres Suchwerkzeug, das möglicherweise für die Produkt-/Kategorieauswahl innerhalb des Richtlinien-Builders verwendet wird, ähnlich wie `autocomplete.js`, aber möglicherweise mit erweiterten Filter- oder Anzeigeoptionen.
- `conorderdis/views/js/adminConorderdisSimulator.js`
  - **Geltungsbereich:** Back-Office (AdminConorderdisPolicies-Controller).
  - **Details:** Implementiert den interaktiven Warenkorb-Simulator. Bindet an Eingabefelder zum Hinzufügen simulierter Produkte, führt AJAX-Aufrufe an einen Simulations-Endpunkt (wahrscheinlich in `AdminConorderdisPolicies`) durch und aktualisiert die Benutzeroberfläche mit dem simulierten Warenkorbstatus und den angewendeten Rabatten.
- `conorderdis/views/js/adminPolicyRules.js`
  - **Geltungsbereich:** Back-Office (AdminConorderdisPolicies-Controller).
  - **Details:** Verwaltet die gesamte Interaktion und Logik für das Formular zur Richtlinienerstellung/-bearbeitung und koordiniert zwischen dem Bedingungs-Builder, dem Werbeaktions-Builder und dem Simulator.
- `conorderdis/views/js/adminPromotionBuilder.js`
  - **Geltungsbereich:** Back-Office (AdminConorderdisPolicies-Controller).
  - **Details:** Treibt die visuelle Werbeaktions-Builder-Oberfläche an. Handhabt das Hinzufügen/Entfernen von Werbeaktionen, das Auswählen von Werbeaktionstypen (z. B. Prozentsatz, kostenloses Geschenk) und das dynamische Aktualisieren der Benutzeroberfläche basierend auf dem gewählten Werbeaktionstyp.

### 4.5 CSS-Stylesheets (`views/css/`)

- `conorderdis/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office (Admin-Formulare).
  - **Details:** Gestaltet die Autocomplete-Dropdowns und Suchergebnisse, die vom `autocomplete.js`-Skript bereitgestellt werden.
- `conorderdis/views/css/admin_conorderdis.css`
  - **Geltungsbereich:** Back-Office (Admin-Formulare und -Seiten).
  - **Details:** Enthält allgemeine Stile für die Back-Office-Oberflächen des Moduls, einschließlich der Richtlinienliste, des Richtlinien-Editors (Bedingungs- und Werbeaktions-Builder), des Dashboards und des Audit-Logs. Definiert Layouts, Farben und spezifische UI-Komponenten für ein konsistentes Erscheinungsbild innerhalb des PrestaShop-Admins.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `conorderdis/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Ausgabe:** Dieses Template wird im Back Office beim Anzeigen einer Bestellung gerendert. Es zeigt wahrscheinlich Informationen zu allen auf diese spezifische Bestellung angewendeten bedingten Rabatten an, möglicherweise mit einem Link zum Audit-Log oder einer Anzeige, welche Richtlinien aktiv waren.

#### Admin-Templates (`views/templates/admin/`)

- `conorderdis/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Enthält JavaScript-Initialisierung oder -Konfiguration für das Suchwerkzeug, oft in Admin-Formularen enthalten, wo das Suchwerkzeug verwendet wird.
- `conorderdis/views/templates/admin/auditPreview.tpl`
  - **Ausgabe:** Rendert eine Vorschau oder Detailansicht eines Audit-Log-Eintrags, möglicherweise innerhalb eines Modals oder eines spezifischen Abschnitts der `AdminconorderdisAuditLog`-Seite.
- `conorderdis/views/templates/admin/dashboard.tpl`
  - **Ausgabe:** Das Haupttemplate für den `AdminConorderdisDashboard`-Controller, das Zusammenfassungsstatistiken, Schnelllinks und möglicherweise den eingebetteten Simulator anzeigt.
- `conorderdis/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Ausgabe:** Ein benutzerdefiniertes Template zum Rendern des „Duplizieren“-Aktionssymbols und -Links innerhalb einer `HelperList`-Tabelle, speziell für Richtlinien.
- `conorderdis/views/templates/admin/policiesPreview.tpl`
  - **Ausgabe:** Rendert eine Vorschau oder Detailansicht einer Richtlinie, möglicherweise innerhalb eines Modals oder eines spezifischen Abschnitts der `AdminconorderdisPolicies`-Seite.
- `conorderdis/views/templates/admin/policyConditionBuilder.tpl`
  - **Ausgabe:** Das Smarty-Template für die visuelle Bedingungs-Builder-Oberfläche innerhalb des Richtlinien-Editors. Es definiert die Struktur zum Hinzufügen, Gruppieren und Konfigurieren von Bedingungen.
- `conorderdis/views/templates/admin/policyRuleCard.tpl`
  - **Ausgabe:** Ein wiederverwendbares Template zum Anzeigen einer einzelnen Regel oder Bedingung innerhalb des Bedingungs-Builders, oft für die dynamische Darstellung über JavaScript verwendet.
- `conorderdis/views/templates/admin/policyRulesTable.tpl`
  - **Ausgabe:** Rendert die Tabelle oder Liste der Regeln/Bedingungen innerhalb des Richtlinien-Editors.
- `conorderdis/views/templates/admin/scopeSelector.tpl`
  - **Ausgabe:** Rendert die Oberfläche zur Auswahl von Shops, Kundengruppen und Währungen für eine Richtlinie.

#### Front-Office-Templates (`views/templates/front/`)

- `conorderdis/controllers/front/index.php` (Keine spezifischen `.tpl`-Dateien für das Front-Office aufgeführt, was auf eine minimale direkte Front-End-Darstellung hindeutet, die sich auf Hooks verlässt, um Inhalte einzufügen oder bestehende Elemente zu ändern.)

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_conorderdis_policy`: Speichert die Definition jeder bedingten Rabattrichtlinie.
  - `id_conorderdis_policy` (Primärschlüssel)
  - `name` (Richtlinienname)
  - `active` (Boolean, 1 für aktiv, 0 für inaktiv)
  - `conditions_data` (TEXT, JSON-kodiertes Array von Bedingungen)
  - `promotions_data` (TEXT, JSON-kodiertes Array von Werbeaktionen)
  - `priority` (INT, kleinere Zahl = höhere Priorität)
  - `date_from` (DATETIME)
  - `date_to` (DATETIME)
  - `id_shop` (INT, für Multishop-Geltungsbereich)
  - `id_customer_group` (INT, für Kundengruppen-Geltungsbereich)
  - `id_currency` (INT, für Währungs-Geltungsbereich)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_conorderdis_log`: Speichert Audit-Log-Einträge für Richtlinienauswertungen.
  - `id_conorderdis_log` (Primärschlüssel)
  - `id_cart` (INT)
  - `id_customer` (INT)
  - `id_policy` (INT, Fremdschlüssel zu `ps_conorderdis_policy`)
  - `result` (VARCHAR, z. B. „applied“, „not\_met“, „error“)
  - `details` (TEXT, JSON-kodierte Details der Auswertung)
  - `date_add` (DATETIME)
- `ps_configuration`: Das Modul speichert seine Haupteinstellung `CONORDERDIS_ENABLED` hier.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um CSS/JS des Moduls für das Front-Office einzubinden, falls vorhanden, oder um Meta-Tags einzufügen. |
| `actionFrontControllerInitAfter` | Nachdem der Front-Controller initialisiert wurde. | Früher Zeitpunkt, um den Kontext zu ändern, Dienste zu registrieren oder sich auf die Warenkorbregel-Auswertung vorzubereiten. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert wurde (z. B. Produkt hinzugefügt/entfernt). | Primärer Hook zur Neubewertung bedingter Rabattrichtlinien basierend auf dem aktualisierten Warenkorbinhalt. |
| `actionValidateCartRule` | Bevor eine Warenkorbregel validiert/angewendet wird. | Ermöglicht dem Modul, einzugreifen oder das native Warenkorbregelverhalten zu ändern, obwohl dies für dieses Modul, das eigene Regeln erstellt, weniger wahrscheinlich ist. |
| `actionValidateOrderBefore` | Bevor eine Bestellung validiert wird. | Letzte Überprüfung auf bedingte Rabatte vor der Bestellerstellung, um sicherzustellen, dass alle Regeln korrekt angewendet werden. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird verwendet, um modulspezifische Aktionen nach der Bestellung abzuschließen, wie das Protokollieren der endgültigen Rabattanwendung oder das Löschen temporärer Daten. |
| `actionObjectProductInCartDeleteBefore` | Bevor ein Produkt aus dem Warenkorb gelöscht wird. | Ermöglicht dem Modul, auf die Produktentfernung zu reagieren und möglicherweise Rabatte oder kostenlose Geschenke anzupassen. |
| `actionObjectProductInCartDeleteAfter` | Nachdem ein Produkt aus dem Warenkorb gelöscht wurde. | Ähnlich wie `DeleteBefore`, aber für die Logik nach dem Löschen, die möglicherweise eine Neubewertung der Warenkorbregeln auslöst. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien (CSS/JS) einstellt. | Wird verwendet, um die Back-Office-CSS- und JavaScript-Dateien des Moduls für seine Konfigurationsseiten und benutzerdefinierten Controller einzubinden. |
| `displayAdminOrder` | Auf der Back-Office-Bestelldetailseite. | Wird verwendet, um modulspezifische Informationen zu bedingten Rabatten anzuzeigen, die auf die angezeigte Bestellung angewendet wurden (z. B. über `admin_order.tpl`). |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Dort finden Sie Ihre gekauften Module und Zugang zu unseren Support-Kanälen.
