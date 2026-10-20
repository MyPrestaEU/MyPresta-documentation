---
title: "Warenkorb in separate Sendungen aufteilen – Händlerhandbuch & Konfigurationsanleitung"
description: ""
sidebar:
  label: "Warenkorb in separate Sendungen aufteilen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Split cart into separate shipments auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/split-cart-into-separate-shipments.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/split-cart-into-separate-shipments/)
>
> ---


# Warenkorb in separate Sendungen aufteilen

## 1. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Warenkorb in separate Sendungen aufteilen“ führt mehrere leistungsstarke neue Bildschirme und Optionen in Ihrem PrestaShop Back Office ein.

### 1.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Warenkorb in separate Sendungen aufteilen)

Dies ist die Hauptkonfigurationsseite, auf die Sie sofort nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager zugreifen. Sie enthält allgemeine Einstellungen für das Verhalten des Moduls.

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Funktionalität des Moduls in Ihrem Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul teilt Warenkörbe während des Checkouts gemäß Ihren Regeln aktiv auf.
    - *Wenn deaktiviert:* Die Aufteilungslogik des Moduls wird umgangen, und PrestaShop kehrt zu seinem Standardverhalten für Einzelsendungen zurück.
  - **Empfohlener Wert:** JA (sobald Sie Ihre Regeln konfiguriert haben).
  - **Händlerszenario / Beispiel:** Sie könnten es vorübergehend deaktivieren, wenn Sie Wartungsarbeiten durchführen oder andere Teile Ihres Checkout-Prozesses beheben.
- **Debug-Modus:**

  - **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der zusätzliche technische Informationen oder Protokolle anzeigen kann, um Probleme zu identifizieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kann Fehlermeldungen oder detaillierte Verarbeitungsschritte im Front Office (für Kunden sichtbar) oder in der Entwicklerkonsole Ihres Browsers anzeigen. Dies ist nützlich für Entwickler.
    - *Wenn deaktiviert:* Das Modul arbeitet geräuschlos, ohne Debug-Informationen anzuzeigen.
  - **Empfohlener Wert:** NEIN (immer in einem Live-Produktionsshop deaktivieren).
  - **Händlerszenario / Beispiel:** Wenn Sie mit einem Entwickler zusammenarbeiten, um zu verstehen, warum ein bestimmter Warenkorb nicht wie erwartet aufgeteilt wird, könnte er Sie bitten, dies vorübergehend zu aktivieren.
- **Zusammenfassung der Aufteilung auf der Bestellbestätigungsseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Kunden auf der endgültigen Bestellbestätigungsseite eine Zusammenfassung sehen, wie ihre Bestellung in verschiedene Sendungen aufgeteilt wurde.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen eine klare Aufschlüsselung, welche Artikel in welche Versandgruppe gingen und welcher Spediteur für jede Sendung gewählt wurde, was ihre Auswahl bestätigt.
    - *Wenn deaktiviert:* Die Bestellbestätigungsseite zeigt eine Standardzusammenfassung ohne die detaillierten Aufteilungsinformationen.
  - **Empfohlener Wert:** JA.
  - **Händlerszenario / Beispiel:** Das Aktivieren verbessert die Transparenz und versichert den Kunden, dass ihre spezifischen Versandentscheidungen für jedes Paket korrekt angewendet wurden.
- **Kunden erlauben, Abholpunkte zu wählen (falls zutreffend):**

  - **Was diese Einstellung bewirkt:** Wenn Sie Spediteure haben, die die Lieferung an Abholpunkte anbieten (z. B. Mondial Relay, Colissimo Point Relais), ermöglicht diese Einstellung Kunden, einen bestimmten Abholort für jede relevante Versandgruppe auszuwählen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Für Spediteure, die mit Abholpunkten konfiguriert sind, sehen Kunden während des Checkouts eine Option zur Auswahl eines Abholorts für die entsprechende Sendung.
    - *Wenn deaktiviert:* Kunden können nur die Hauszustellung oder andere Standardversandoptionen auswählen, selbst wenn Spediteure Abholpunkte unterstützen.
  - **Empfohlener Wert:** JA (wenn Sie Spediteure mit Abholpunkten verwenden).
  - **Händlerszenario / Beispiel:** Wenn Sie Mondial Relay anbieten, ermöglicht das Aktivieren den Kunden, einen schweren Artikel an einen bequemen Abholpunkt in der Nähe ihres Zuhauses oder Arbeitsplatzes liefern zu lassen, was ihr Erlebnis verbessert.

### 1.2 Dedizierte Admin-Bildschirme: Versandregeln (Back Office > Versand > Regeln zur Sendungsaufteilung)

Auf diesem Bildschirm definieren Sie die Logik, wie Ihre Warenkorbartikel in separate Sendungen gruppiert werden sollen. Dies ist der Kern der Modulfunktionalität.

- **Bildschirmname & Menüpfad:** **Regeln zur Sendungsaufteilung** (zu finden unter **Versand** in Ihrem PrestaShop Back Office Menü).
- **Verfügbare Aktionen & Einstellungen:**
  - **Regel-Auflistungstabelle:** Zeigt alle Ihre definierten Gruppierungsregeln an. Jede Regel hat einen Namen, Status (aktiv/inaktiv), Priorität und eine Zusammenfassung ihrer Bedingungen und Aktionen.
  - **Schaltfläche „Neue Regel hinzufügen“:** Durch Klicken darauf können Sie eine neue Regel erstellen.
  - **Bearbeiten/Löschen-Aktionen:** Für jede Regel in der Liste können Sie deren Details bearbeiten oder sie löschen.
  - **Aktivieren/Deaktivieren-Umschalter:** Eine Regel schnell aktivieren oder deaktivieren, ohne sie zu löschen.
  - **Drag-and-Drop-Neuanordnung:** Regeln werden in der Reihenfolge ihrer Priorität verarbeitet. Sie können Regeln per Drag-and-Drop verschieben, um ihre Ausführungsreihenfolge zu ändern. Regeln mit höherer Priorität werden zuerst verarbeitet.
- **Auswirkung von Änderungen:**
  - **Regeln hinzufügen/bearbeiten:** Wirkt sich direkt darauf aus, wie Warenkörbe während des Checkouts aufgeteilt werden. Eine gut definierte Regel kann sicherstellen, dass bestimmte Produkte immer separat oder zusammen versendet werden.
  - **Regeln aktivieren/deaktivieren:** Steuert, ob die Logik einer Regel angewendet wird.
  - **Priorität ändern:** Bestimmt, welche Regel Vorrang hat, wenn mehrere Regeln auf dasselbe Produkt zutreffen könnten. Regeln mit höherer Priorität (die weiter oben in der Liste erscheinen) werden zuerst ausgewertet.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Gruppierungsbedürfnisse identifizieren:** Denken Sie über Ihre Produkte nach. Haben Sie übergroße Artikel, zerbrechliche Artikel, Artikel aus verschiedenen Lagern oder Artikel, die eine spezielle Handhabung erfordern?
  2. **Regeln erstellen:** Erstellen Sie für jedes Gruppierungsbedürfnis eine neue Regel.
     - **Bedingungen:** Definieren Sie, *wann* die Regel angewendet wird. Dies könnte basieren auf:
       - **Produkt:** Spezifische Produkte, Kategorien, Hersteller, Lieferanten oder Produktmerkmale.
       - **Warenkorb:** Gesamtwert des Warenkorbs, Anzahl der Artikel, spezifische Kundengruppen.
       - **Versand:** Spezifische Spediteure oder Zonen.
     - **Aktionen:** Definieren Sie, *was* die Regel bewirkt. Dies könnte sein:
       - **Separate Sendung erzwingen:** Die passenden Artikel immer in eine eigene Versandgruppe legen.
       - **Gleiche Sendung erzwingen:** Sicherstellen, dass passende Artikel immer zusammen in einer Sendung bleiben.
       - **Von der Regelverarbeitung ausschließen:** Verhindern, dass andere Regeln diese Artikel beeinflussen.
  3. **Priorität festlegen:** Ordnen Sie Ihre Regeln von der spezifischsten (z. B. „Zerbrechliches Glaswaren immer alleine versenden“) zur allgemeinsten (z. B. „Alle übergroßen Artikel separat versenden“) an.
  4. **Gründlich testen:** Verwenden Sie ein Testkundenkonto, um verschiedene Produktkombinationen in den Warenkorb zu legen und zu überprüfen, ob die Aufteilung während des Checkouts wie erwartet funktioniert.

### 1.3 Dedizierte Admin-Bildschirme: Sendungsgruppen (Back Office > Versand > Sendungsaufteilungen)

Dieser Bildschirm bietet einen Überblick darüber, wie Bestellungen vom Modul nach ihrer Platzierung aufgeteilt wurden. Es ist ein Berichts- und Verwaltungstool.

- **Bildschirmname & Menüpfad:** **Sendungsaufteilungen** (zu finden unter **Versand** in Ihrem PrestaShop Back Office Menü).
- **Verfügbare Aktionen & Einstellungen:**
  - **Aufteilungs-Auflistungstabelle:** Zeigt eine Liste aller Bestellungen an, die vom Modul aufgeteilt wurden.
  - **Bestellreferenz:** Verlinkt direkt zur ursprünglichen PrestaShop-Bestellung.
  - **Details der Sendungsgruppe:** Bietet Informationen zu jeder einzelnen Sendungsgruppe innerhalb einer Bestellung, einschließlich der enthaltenen Produkte, des gewählten Spediteurs und ihres Status.
  - **Aufteilungsdetails anzeigen:** Ermöglicht es Ihnen, in eine bestimmte Aufteilung einzutauchen, um detailliertere Informationen zu sehen.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Anzeige und Überprüfung. Sie ändern hier nicht direkt, wie zukünftige Warenkörbe aufgeteilt werden. Alle Änderungen, die Sie vornehmen (z. B. die Aktualisierung eines Spediteurs für eine bestimmte Aufteilung), würden typischerweise in der Haupt-PrestaShop-Bestellansicht vorgenommen, und dieses Modul würde diese Änderungen widerspiegeln.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - **Aufgeteilte Bestellungen überwachen:** Überprüfen Sie diesen Bildschirm regelmäßig, um zu verstehen, wie Ihre Regeln in der Praxis funktionieren.
  - **Fehlerbehebung:** Wenn ein Kunde eine Frage zu seinem Versand hat, kann dieser Bildschirm Ihnen helfen, schnell zu sehen, wie seine Bestellung in verschiedene Sendungen verarbeitet wurde.
  - **Integration mit der Auftragsverwaltung:** Während das Modul Standard-PrestaShop-Bestellungen erstellt, bietet dieser Bildschirm eine konsolidierte Ansicht der auf jede Bestellung angewendeten Aufteilungslogik.

### 1.4 Dedizierte Admin-Bildschirme: Dashboard (Back Office > Versand > Dashboard zur Sendungsaufteilung)

Dieser Bildschirm bietet einen schnellen Überblick und Statistiken zur Aktivität des Moduls.

- **Bildschirmname & Menüpfad:** **Dashboard zur Sendungsaufteilung** (zu finden unter **Versand** in Ihrem PrestaShop Back Office Menü).
- **Verfügbare Aktionen & Einstellungen:**
  - **KPI-Leiste:** Key Performance Indicators (KPIs) wie die Gesamtzahl der aufgeteilten Bestellungen, die durchschnittliche Anzahl der Sendungen pro Bestellung oder der Gesamtumsatz aus aufgeteilten Bestellungen.
  - **Diagramme & Grafiken:** Visuelle Darstellungen von Trends, wie z. B. die Anzahl der aufgeteilten Bestellungen im Zeitverlauf, die am häufigsten verwendeten Aufteilungsregeln oder beliebte Spediteure für aufgeteilte Sendungen.
  - **Aktuelle Aufteilungen:** Eine schnelle Liste der zuletzt aufgeteilten Bestellungen.
- **Auswirkung von Änderungen:** Dies ist ein Berichts-Dashboard. Hier werden keine direkten Änderungen am Modulverhalten vorgenommen. Es hilft Ihnen, die Auswirkungen und die Nutzung des Moduls zu verstehen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - **Leistungsüberwachung:** Verwenden Sie dieses Dashboard, um die Wirksamkeit Ihrer Aufteilungsregeln zu bewerten und Muster oder Anomalien zu identifizieren.
  - **Strategische Planung:** Die Daten können Entscheidungen über Versandstrategien, Spediteurpartnerschaften oder Anpassungen des Produktkatalogs beeinflussen.

### 1.5 Kurzübersicht Konfigurationstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
|  | Debug-Modus | NEIN | Zeigt technische Informationen an (nur für Entwickler). |
|  | Zusammenfassung der Aufteilung auf der Bestellbestätigungsseite anzeigen | JA | Zeigt Kunden, wie ihre Bestellung aufgeteilt wurde. |
|  | Kunden erlauben, Abholpunkte zu wählen | JA (falls zutreffend) | Ermöglicht die Auswahl von Abholpunkten für relevante Spediteure. |
| **Regeln zur Sendungsaufteilung** | Regel hinzufügen/bearbeiten (Bedingungen) | N/A | Definiert, *wann* eine Regel angewendet wird (z. B. nach Produkt, Kategorie, Warenkorbwert). |
|  | Regel hinzufügen/bearbeiten (Aktionen) | N/A | Definiert, *was* die Regel bewirkt (z. B. separate Sendung erzwingen, gleiche Sendung erzwingen). |
|  | Regelpriorität | N/A | Bestimmt die Reihenfolge, in der Regeln verarbeitet werden (höher = zuerst). |
|  | Regel aktivieren/deaktivieren | N/A | Aktiviert oder deaktiviert eine spezifische Gruppierungsregel. |
| **Sendungsaufteilungen** | Aufgeteilte Bestellungen anzeigen | N/A | Bietet eine Liste und Details aller vom Modul verarbeiteten Bestellungen. |
| **Dashboard zur Sendungsaufteilung** | KPIs, Diagramme, Aktuelle Aufteilungen | N/A | Bietet einen Überblick über die Modulaktivität und -leistung. |

## 2. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

- **F: Mein Warenkorb wird nicht aufgeteilt, oder er wird falsch aufgeteilt. Was soll ich tun?**

  - **A:** Überprüfen Sie zunächst, ob das Modul in seiner Hauptkonfiguration aktiviert ist. Gehen Sie dann zu **Versand > Regeln zur Sendungsaufteilung** und überprüfen Sie Ihre Regeln. Stellen Sie sicher, dass sie aktiv sind und ihre Bedingungen korrekt mit den Produkten in Ihrem Testwarenkorb übereinstimmen. Achten Sie genau auf die Regelpriorität – eine allgemeinere Regel könnte eine spezifischere Regel außer Kraft setzen. Wenn Sie den „Debug-Modus“ in der Hauptkonfiguration des Moduls aktiviert haben, suchen Sie während des Checkouts nach Meldungen. Leeren Sie schließlich Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**).
- **F: Warum werden einige Spediteure für eine bestimmte Sendungsgruppe nicht angezeigt?**

  - **A:** Das Modul beachtet die Standard-Spediteur-Beschränkungen von PrestaShop. Überprüfen Sie Folgendes:
    1. **Spediteur-Zonen:** Stellen Sie sicher, dass der Spediteur für die Versandzone des Kunden aktiviert ist.
    2. **Spediteur-Gewichts-/Preisbereiche:** Überprüfen Sie, ob das Gesamtgewicht/der Gesamtpreis der *einzelnen Sendungsgruppe* (nicht des gesamten Warenkorbs) innerhalb der definierten Bereiche des Spediteurs liegt.
    3. **Spediteur-Zuordnungen:** Stellen Sie sicher, dass der Spediteur den Produkten in dieser Sendungsgruppe zugeordnet ist (falls Sie produktspezifische Spediteur-Beschränkungen eingerichtet haben).
    4. **Modulkompatibilität:** Einige Versandmodule von Drittanbietern könnten ihre eigene Logik haben, die Konflikte verursacht; suchen Sie nach bekannten Inkompatibilitäten oder kontaktieren Sie den Support.
- **F: Wie wirkt sich dieses Modul auf meine bestehenden Versandkosten und Regeln für kostenlosen Versand aus?**

  - **A:** Das Modul aggregiert die Versandkosten. Wenn ein Warenkorb in zwei Sendungen aufgeteilt wird und jede Sendung 10 € kostet, sieht der Kunde Gesamtkosten von 20 €. Für den kostenlosen Versand gelten Ihre bestehenden Regeln für kostenlosen Versand (z. B. „kostenloser Versand ab X €“) für *jede einzelne Sendungsgruppe*, wenn das Modul dies zulässt, oder für den *gesamten Warenkorbwert*, je nachdem, wie Ihre Regeln konfiguriert sind und wie das Modul integriert ist. Möglicherweise müssen Sie Ihre Regeln für kostenlosen Versand an die aufgeteilten Sendungen anpassen.
- **F: Kann ich die Texte des Moduls in andere Sprachen übersetzen?**

  - **A:** Ja, wie die meisten PrestaShop-Module können Sie die Texte für das Front Office und Back Office übersetzen. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme, wählen Sie „Warenkorb in separate Sendungen aufteilen“ und dann die Sprache, in die Sie übersetzen möchten.
- **F: Nach der Installation sehe ich eine leere Seite oder einen Fehler. Was ist falsch?**

  - **A:** Dies deutet oft auf einen PHP-Fehler hin.
    1. **PHP-Fehlerprotokolle überprüfen:** Ihr Webhosting-Kontrollpanel bietet normalerweise Zugriff auf PHP-Fehlerprotokolle. Suchen Sie nach aktuellen Einträgen, die sich auf PrestaShop beziehen.
    2. **PrestaShop-Debug-Modus aktivieren:** Gehen Sie zu `config/defines.inc.php` in Ihrer PrestaShop-Installation, suchen Sie `define('_PS_MODE_DEV_', false);` und ändern Sie `false` in `true`. Dies zeigt den Fehler auf dem Bildschirm an.
    3. **Modulkompatibilität:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Version (z. B. PS 8.x, 1.7.x) heruntergeladen haben.
    4. **Support kontaktieren:** Wenn Sie das Problem nicht lösen können, senden Sie die Fehlermeldung an den MyPresta.eu-Support.

## 3. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 3.1 Architekturübersicht

Das Modul „Warenkorb in separate Sendungen aufteilen“ (`multishipsplit`) wurde nach dem MVC-Muster (Model-View-Controller) von PrestaShop entwickelt, wobei Hooks und Overrides intensiv genutzt werden, um tief in den Checkout-Prozess zu integrieren. Es führt eine robuste regelbasierte Engine für die Warenkorbaufteilung ein, die komplexe Bedingungen und Aktionen ermöglicht. Die Kernlogik dreht sich um das Aufteilen des `Cart`-Objekts in mehrere `MultishipShipmentGroup`-Entitäten, wobei jede ein separates Paket mit eigener Spediteurauswahl darstellt. Es nutzt `ObjectModel` zur Verwaltung von Regeln und Aufteilungsdaten und verwendet eine Reihe von Dienstklassen, um die komplexe Logik der Bedingungsbewertung, Aktionserstellung und Checkout-Präsentation zu handhaben. Overrides werden verwendet, um das Kernverhalten von `Cart` und `PaymentModule` zu ändern, um mehrere Sendungen zu unterstützen.

### 3.2 Controller (`controllers/`)

#### Front-Office-Controller

- `multishipsplit/controllers/front/groups.php`
  - **Klassenname:** `MultishipsplitGroupsModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Behandelt AJAX-Anfragen im Zusammenhang mit Sendungsgruppen während des Checkouts. Dies kann das Aktualisieren von Spediteurauswahlen für eine bestimmte Gruppe, das Neuberechnen von Versandkosten oder das Abrufen von Abholpunktoptionen umfassen. Es verarbeitet `POST`-Daten und gibt JSON-Antworten an die Checkout-Seite zurück.
- `multishipsplit/controllers/front/index.php`
  - **Klassenname:** `MultishipsplitIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Ein Platzhalter oder Einstiegspunkt-Controller. Er könnte für allgemeine modulbezogene Front-Office-Aktionen oder Weiterleitungen verwendet werden, obwohl seine primäre Funktion minimal sein könnte, wenn die meisten Interaktionen AJAX-gesteuert über `groups.php` erfolgen.
- `multishipsplit/controllers/front/pickup.php`
  - **Klassenname:** `MultishipsplitPickupModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Verwaltet AJAX-Interaktionen speziell für die Auswahl von Abholpunkten. Es verarbeitet wahrscheinlich Anfragen zur Anzeige verfügbarer Abholpunkte für einen bestimmten Spediteur und eine Adresse und zum Speichern des ausgewählten Abholpunkts im Warenkorb oder in der Sitzung.

#### Back-Office-Admin-Controller

- `multishipsplit/controllers/admin/AdminMultishipRules.php`
  - **Klassenname:** `AdminMultishipRulesController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** „Regeln zur Sendungsaufteilung“
  - **Verwaltete Entität:** `MultishipGroupingRule` (bildet auf die Tabelle `mss_grouping_rule` ab)
  - **Verantwortlichkeit:** Bietet die CRUD-Schnittstelle (Create, Read, Update, Delete) zur Verwaltung von Regeln zur Sendungsgruppierung. Es behandelt die Anzeige der Regelliste, das Formular zum Hinzufügen/Bearbeiten von Regeln (einschließlich der Bedingungs- und Aktions-Builder) sowie das Speichern/Löschen von Regeldaten.
- `multishipsplit/controllers/admin/AdminMultishipSplits.php`
  - **Klassenname:** `AdminMultishipSplitsController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** „Sendungsaufteilungen“
  - **Verwaltete Entität:** `MultishipSplitGroup` (bildet auf die Tabelle `mss_split_group` ab)
  - **Verantwortlichkeit:** Zeigt eine Liste aller Bestellungen an, die vom Modul verarbeitet und aufgeteilt wurden. Es bietet eine schreibgeschützte Ansicht der aufgeteilten Gruppen innerhalb jeder Bestellung, die auf die ursprüngliche PrestaShop-Bestellung zurückverlinkt.
- `multishipsplit/controllers/admin/index.php`
  - **Klassenname:** `MultishipsplitIndexModuleAdminController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** „Dashboard zur Sendungsaufteilung“
  - **Verwaltete Entität:** N/A (Dashboard-Ansicht)
  - **Verantwortlichkeit:** Dient als Dashboard-Controller und zeigt KPIs, Diagramme und aktuelle aufgeteilte Bestellungen an. Es aggregiert Daten aus den Modultabellen, um einen Überblick über seine Aktivität zu geben.

### 3.3 Kernklassen & Modelle (`classes/`)

- `multishipsplit/classes/MultishipActionBuilder.php`
  - **Verantwortlichkeit:** Eine Dienstklasse, die für die Konstruktion und Interpretation der in einer `MultishipGroupingRule` definierten Aktionen verantwortlich ist. Sie übersetzt die Aktionskonfiguration der Regel in ausführbare Logik.
- `multishipsplit/classes/MultishipCartSlicer.php`
  - **Verantwortlichkeit:** Die zentrale Klasse für die Warenkorbaufteilungslogik. Sie nimmt ein `Cart`-Objekt und teilt die Produkte des Warenkorbs mithilfe der definierten `MultishipGroupingRule`s in ein Array von `MultishipShipmentGroup`-Objekten auf.
- `multishipsplit/classes/MultishipCheckoutPresenter.php`
  - **Verantwortlichkeit:** Bereitet die Daten für die Front-Office-Checkout-Seite vor. Sie nimmt die `MultishipShipmentGroup`s und formatiert sie für die Anzeige, einschließlich verfügbarer Spediteure, Kosten und Abholpunktoptionen, die von Smarty-Templates gerendert werden sollen.
- `multishipsplit/classes/MultishipCompatibility.php`
  - **Verantwortlichkeit:** Handhabt Kompatibilitätsschichten für verschiedene PrestaShop-Versionen oder potenzielle Konflikte mit anderen Modulen. Sie stellt sicher, dass das Modul in verschiedenen Umgebungen korrekt funktioniert.
- `multishipsplit/classes/MultishipConditionBuilder.php`
  - **Verantwortlichkeit:** Ähnlich wie `MultishipActionBuilder`, aber für Regelbedingungen. Sie konstruiert und interpretiert die Bedingungen, die bestimmen, wann eine `MultishipGroupingRule` angewendet werden soll.
- `multishipsplit/classes/MultishipConditionEvaluator.php`
  - **Verantwortlichkeit:** Bewertet eine Reihe von Bedingungen anhand eines gegebenen Kontexts (z. B. ein Produkt, ein Warenkorb, ein Kunde), um festzustellen, ob eine Regel ausgelöst werden soll.
- `multishipsplit/classes/MultishipConditionTree.php`
  - **Verantwortlichkeit:** Verwaltet die hierarchische Struktur von Bedingungen (z. B. UND/ODER-Gruppen) innerhalb einer Regel, was komplexe logische Ausdrücke ermöglicht.
- `multishipsplit/classes/MultishipConfirmationPresenter.php`
  - **Verantwortlichkeit:** Bereitet Daten für die Anzeige der Aufteilungszusammenfassung auf der Bestellbestätigungsseite vor.
- `multishipsplit/classes/MultishipDashboardPresenter.php`
  - **Verantwortlichkeit:** Sammelt und formatiert Daten für das Back Office Dashboard, einschließlich KPIs und Diagrammdaten.
- `multishipsplit/classes/MultishipGroupingEngine.php`
  - **Verantwortlichkeit:** Orchestriert den gesamten regelbasierten Gruppierungsprozess. Sie ruft aktive Regeln ab, wendet sie sequenziell (basierend auf Priorität) auf den Warenkorb an und verwaltet die Erstellung von `MultishipShipmentGroup`s.
- `multishipsplit/classes/MultishipGroupingRule.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `mss_grouping_rule`
  - **`$definition`-Felder:** Speichert die Konfiguration für jede Aufteilungsregel, einschließlich ihres Namens, ihrer Priorität, ihres aktiven Status sowie serialisierter Bedingungen und Aktionen.
  - **Wichtige öffentliche Methoden:** Methoden zum Speichern, Laden und Verwalten von Regeldaten.
- `multishipsplit/classes/MultishipOrderLink.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `mss_order_link`
  - **`$definition`-Felder:** Verknüpft eine PrestaShop `Order` mit ihren entsprechenden `MultishipSplitGroup`s, sodass das Modul verfolgen kann, wie eine Bestellung aufgeteilt wurde.
  - **Wichtige öffentliche Methoden:** Methoden zum Erstellen und Abrufen dieser Links.
- `multishipsplit/classes/MultishipPaymentBridge.php`
  - **Verantwortlichkeit:** Erleichtert den Zahlungsprozess, wenn ein Warenkorb aufgeteilt wird. Sie stellt sicher, dass der Gesamtbetrag für alle Sendungsgruppen korrekt an das Zahlungsmodul übergeben wird und dass die Zahlungsbestätigung den Status aller zugehörigen Bestellungen korrekt aktualisiert.
- `multishipsplit/classes/MultishipPayPlugRefundAdapter.php`
  - **Verantwortlichkeit:** Bietet eine spezifische Integration für die Rückerstattung aufgeteilter Bestellungen bei Verwendung des PayPlug-Zahlungsmoduls. Dies deutet darauf hin, dass das Modul ähnliche Adapter für andere Zahlungsgateways haben könnte.
- `multishipsplit/classes/MultishipPickupFactory.php`
  - **Verantwortlichkeit:** Eine Factory-Klasse zum Erstellen von Instanzen von `MultishipPickupAdapterInterface` basierend auf dem verwendeten Spediteur oder Modul (z. B. für Mondial Relay, Colissimo).
- `multishipsplit/classes/MultishipRefundLog.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `mss_refund_log`
  - **`$definition`-Felder:** Protokolliert Rückerstattungsaktionen im Zusammenhang mit aufgeteilten Bestellungen, besonders wichtig, wenn Teilerstattungen oder Erstattungen über mehrere verknüpfte Bestellungen hinweg involviert sind.
- `multishipsplit/classes/MultishipRuleContext.php`
  - **Verantwortlichkeit:** Kapselt den Kontext (z. B. aktueller Warenkorb, Kunde, zu bewertendes Produkt) für die Regelauswertung, wodurch es einfacher wird, relevante Daten an Bedingungsprüfer zu übergeben.
- `multishipsplit/classes/MultishipShipmentGroup.php`
  - **Verantwortlichkeit:** Repräsentiert eine einzelne logische Sendung innerhalb eines aufgeteilten Warenkorbs. Sie enthält eine Sammlung von `MultishipShipmentProduct`s, den ausgewählten Spediteur und die damit verbundenen Kosten.
- `multishipsplit/classes/MultishipShipmentProduct.php`
  - **Verantwortlichkeit:** Repräsentiert einen Produktartikel innerhalb einer `MultishipShipmentGroup`, einschließlich seiner Menge und spezifischer Attribute, die für diese Sendung relevant sind.
- `multishipsplit/classes/MultishipShippingCostAggregator.php`
  - **Verantwortlichkeit:** Berechnet die gesamten Versandkosten durch Summierung der Kosten aller einzelnen `MultishipShipmentGroup`s.
- `multishipsplit/classes/MultishipSplitGroup.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `mss_split_group`
  - **`$definition`-Felder:** Speichert Details zu einer bestimmten Sendungsgruppe, die als Teil einer aufgeteilten Bestellung erstellt wurde. Dies wird für die Nachverfolgung und Berichterstattung im Back Office verwendet.
- `multishipsplit/classes/MultishipSplitOrchestrator.php`
  - **Verantwortlichkeit:** Der übergeordnete Orchestrator für den gesamten Aufteilungsprozess, vom anfänglichen Warenkorb-Slicing bis zur Auftragserstellung und Zahlungsabwicklung.
- `multishipsplit/classes/Pickup/MultishipColissimoPickupAdapter.php`
  - **Implementiert:** `MultishipPickupAdapterInterface`
  - **Verantwortlichkeit:** Bietet spezifische Logik für die Integration mit Colissimo-Abholpunkten.
- `multishipsplit/classes/Pickup/MultishipMondialRelayPickupAdapter.php`
  - **Implementiert:** `MultishipPickupAdapterInterface`
  - **Verantwortlichkeit:** Bietet spezifische Logik für die Integration mit Mondial Relay-Abholpunkten.
- `multishipsplit/classes/Pickup/MultishipPickupAdapterInterface.php`
  - **Verantwortlichkeit:** Definiert den Vertrag für alle Abholpunkt-Integrationsadapter, um eine konsistente Schnittstelle für verschiedene Spediteure zu gewährleisten.
- `multishipsplit/override/classes/Cart.php`
  - **Verantwortlichkeit:** Überschreibt Kernmethoden von `Cart`, um das Hinzufügen, Entfernen von Produkten und die Berechnung der Versandkosten abzufangen und zu ändern, wodurch die Aufteilungslogik des Moduls wirksam wird. Dies ist eine kritische Überschreibung.
- `multishipsplit/override/classes/PaymentModule.php`
  - **Verantwortlichkeit:** Überschreibt Kernmethoden von `PaymentModule`, um den Zahlungsprozess für mehrere Bestellungen zu handhaben, die aus einem einzigen aufgeteilten Warenkorb generiert wurden. Es stellt sicher, dass eine einzige Zahlung alle Unterbestellungen abdeckt und deren Status korrekt aktualisiert werden.

### 3.4 JavaScript-Assets (`views/js/`)

- `multishipsplit/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Bietet Autocomplete-Funktionalität für Suchfelder, wahrscheinlich im Regel-Builder zur Auswahl von Produkten, Kategorien oder anderen Entitäten verwendet.
- `multishipsplit/lib/searchTool/views/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Wahrscheinlich ein Duplikat oder alternativer Pfad für das Autocomplete-Skript, möglicherweise für Kompatibilität oder spezifische Ansichtskontexte.
- `multishipsplit/views/js/adminActionBuilder.js`
  - **Geltungsbereich:** Back-Office (AdminMultishipRulesController).
  - **Details:** Verwaltet die dynamische Oberfläche zum Erstellen von Regelaktionen (z. B. „Separate Sendung erzwingen“). Es handhabt das Hinzufügen/Entfernen von Aktionstypen und deren zugehörigen Parametern.
- `multishipsplit/views/js/adminConditionBuilder.js`
  - **Geltungsbereich:** Back-Office (AdminMultishipRulesController).
  - **Details:** Verwaltet die dynamische Oberfläche zum Erstellen von Regelbedingungen. Es ermöglicht Administratoren, mehrere Bedingungen hinzuzufügen, sie mit UND/ODER-Logik zu gruppieren und verschiedene Kriterien (Produkt, Kategorie usw.) auszuwählen.
- `multishipsplit/views/js/adminMultishipSearchTool.js`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Integriert das Autocomplete-Suchwerkzeug in die Admin-Formulare des Moduls, insbesondere zur Auswahl spezifischer Produkte, Kategorien oder anderer Entitäten beim Definieren von Regeln.
- `multishipsplit/views/js/admin_dashboard.js`
  - **Geltungsbereich:** Back-Office (AdminMultishipIndexController).
  - **Details:** Handhabt dynamische Elemente und Datenladung für das Dashboard, potenziell einschließlich Diagrammrendering (z. B. mit Chart.js) und KPI-Updates.
- `multishipsplit/views/js/admin_rules.js`
  - **Geltungsbereich:** Back-Office (AdminMultishipRulesController).
  - **Details:** Allgemeines JavaScript für die Regelnverwaltungsseite, einschließlich Drag-and-Drop-Neuanordnung von Regeln, Aktivieren/Deaktivieren-Umschaltern und Formularübermittlungsbehandlung.
- `multishipsplit/views/js/checkout.js`
  - **Geltungsbereich:** Front-Office (Checkout-Seite).
  - **Details:** Dies ist ein kritisches Skript für das Front-Office-Erlebnis. Es bindet Event-Listener an Änderungen der Spediteurauswahl für jede Sendungsgruppe, sendet AJAX-Anfragen an `groups.php` oder `pickup.php`, um Versandkosten zu aktualisieren oder Abholpunkte abzurufen, und aktualisiert dynamisch die gesamte Bestellübersicht auf der Checkout-Seite. Es verwendet wahrscheinlich `prestashop.on` für benutzerdefinierte Ereignisse.

### 3.5 CSS-Stylesheets (`views/css/`)

- `multishipsplit/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Stile für die Autocomplete-Dropdowns und Suchfelder, die in den Admin-Formularen verwendet werden.
- `multishipsplit/lib/searchTool/views/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Wahrscheinlich ein Duplikat oder alternativer Pfad für die Autocomplete-Stile.
- `multishipsplit/views/css/admin_condition_builder.css`
  - **Geltungsbereich:** Back-Office (AdminMultishipRulesController).
  - **Details:** Gestaltet die dynamische Oberfläche zum Erstellen von Bedingungen innerhalb des Formulars zur Regelerstellung/-bearbeitung und sorgt für ein klares und organisiertes Layout.
- `multishipsplit/views/css/admin_dashboard.css`
  - **Geltungsbereich:** Back-Office (AdminMultishipIndexController).
  - **Details:** Stile für das Dashboard-Layout, KPIs, Diagramme und die Tabelle der letzten Aufteilungen.
- `multishipsplit/views/css/admin_order.css`
  - **Geltungsbereich:** Back-Office (Bestellansichtsseite).
  - **Details:** Stile für das benutzerdefinierte Widget oder die Informationen, die in der Standard-PrestaShop-Bestellansicht angezeigt werden und zeigen, wie die Bestellung aufgeteilt wurde.
- `multishipsplit/views/css/admin_rules.css`
  - **Geltungsbereich:** Back-Office (AdminMultishipRulesController).
  - **Details:** Allgemeine Stile für die Regellistentabelle, Regelaktionen (aktivieren/deaktivieren) und das Gesamtlayout der Regelnverwaltungsseite.
- `multishipsplit/views/css/checkout.css`
  - **Geltungsbereich:** Front-Office (Checkout-Seite).
  - **Details:** Gestaltet die Darstellung der aufgeteilten Sendungsgruppen auf der Checkout-Seite, einschließlich der Anzeige der Spediteure für jede Gruppe, der Kostenübersicht und potenziell der Schnittstellen zur Auswahl von Abholpunkten. Entwickler können diese Klassen in der `custom.css` ihres Themes oder durch Ändern der Modul-Templates überschreiben.

### 3.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `multishipsplit/views/templates/hook/checkout_groups.tpl`
  - **Hook:** Wahrscheinlich `displayCarrierList` oder ein benutzerdefinierter Hook, der in den Checkout-Versandschritt eingefügt wird.
  - **Ausgabe:** Der Hauptvisualisierungsblock auf der Checkout-Seite, der die gruppierten Produkte anzeigt und es Kunden ermöglicht, einen Spediteur für jede einzelne Sendungsgruppe auszuwählen. Hier findet die Kerninteraktion im Front-Office statt.
- `multishipsplit/views/templates/hook/order_confirmation_split.tpl`
  - **Hook:** `displayOrderConfirmation` oder ein ähnlicher Hook auf der Bestellbestätigungsseite.
  - **Ausgabe:** Die Zusammenfassung, wie die Bestellung aufgeteilt wurde, zeigt, welche Artikel in welcher Sendung waren und der gewählte Spediteur, wie in der Einstellung „Zusammenfassung der Aufteilung auf der Bestellbestätigungsseite anzeigen“ konfiguriert.
- `multishipsplit/views/templates/hook/payment_top.tpl`
  - **Hook:** `displayPaymentTop`
  - **Ausgabe:** Zeigt möglicherweise eine Warnung oder Informationsmeldung an den Kunden bezüglich der aufgeteilten Bestellung an, bevor er zur Zahlung übergeht, um sicherzustellen, dass er versteht, dass die Gesamtkosten mehrere Versandgebühren enthalten.

#### Admin-Templates (`views/templates/admin/`)

- `multishipsplit/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Smarty-Skriptblock für das Suchwerkzeug, wahrscheinlich einschließlich JavaScript- und CSS-Includes.
- `multishipsplit/lib/searchTool/views/views/scripts.tpl`
  - **Ausgabe:** Duplikat oder alternativer Pfad für Suchwerkzeugskripte.
- `multishipsplit/views/templates/admin/actionBuilder.tpl`
  - **Ausgabe:** Die HTML-Struktur für die dynamische Aktions-Builder-Oberfläche innerhalb des Formulars zur Regelerstellung/-bearbeitung.
- `multishipsplit/views/templates/admin/dashboard_chart.tpl`
  - **Ausgabe:** Template zum Rendern eines spezifischen Diagramms auf dem Dashboard, wahrscheinlich unter Verwendung einer JavaScript-Diagrammbibliothek.
- `multishipsplit/views/templates/admin/dashboard_kpi_strip.tpl`
  - **Ausgabe:** Template für die Key Performance Indicator (KPI)-Leiste oben auf dem Dashboard.
- `multishipsplit/views/templates/admin/dashboard_recent_splits.tpl`
  - **Ausgabe:** Template zum Anzeigen einer Liste der zuletzt aufgeteilten Bestellungen auf dem Dashboard.
- `multishipsplit/views/templates/admin/dashboard_stats.tpl`
  - **Ausgabe:** Allgemeiner Statistikblock auf dem Dashboard.
- `multishipsplit/views/templates/admin/menu.tpl`
  - **Ausgabe:** Definiert die benutzerdefinierten Menüpunkte des Moduls in der PrestaShop Back Office Navigation (z. B. unter „Versand“).
- `multishipsplit/views/templates/admin/order_split_widget.tpl`
  - **Ausgabe:** Ein benutzerdefiniertes Widget oder Block, der innerhalb der Standard-PrestaShop-Bestelldetailseite im Back Office angezeigt wird und eine Zusammenfassung darüber liefert, wie diese spezifische Bestellung aufgeteilt wurde.
- `multishipsplit/views/templates/admin/policyConditionBuilder.tpl`
  - **Ausgabe:** Die HTML-Struktur für die dynamische Bedingungs-Builder-Oberfläche innerhalb des Formulars zur Regelerstellung/-bearbeitung.
- `multishipsplit/views/templates/admin/split_view.tpl`
  - **Ausgabe:** Eine detaillierte Ansicht für eine spezifische aufgeteilte Bestellung, die möglicherweise über die Liste „Sendungsaufteilungen“ aufgerufen wird.

### 3.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_mss_grouping_rule`: Speichert die Definitionen aller vom Administrator erstellten Regeln zur Sendungsgruppierung.
  - `id_mss_grouping_rule` (PK)
  - `name` (VARCHAR)
  - `priority` (INT)
  - `active` (TINYINT)
  - `conditions` (TEXT – serialisiertes Array/JSON von Bedingungen)
  - `actions` (TEXT – serialisiertes Array/JSON von Aktionen)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_mss_split_group`: Speichert Details jeder einzelnen Sendungsgruppe, die für eine aufgeteilte Bestellung erstellt wurde.
  - `id_mss_split_group` (PK)
  - `id_order` (FK zu `ps_orders`)
  - `id_cart` (FK zu `ps_cart`)
  - `id_carrier` (FK zu `ps_carrier`)
  - `shipping_cost_tax_excl` (DECIMAL)
  - `shipping_cost_tax_incl` (DECIMAL)
  - `products` (TEXT – serialisiertes Array von Produkten in dieser Gruppe)
  - `pickup_point_data` (TEXT – serialisierte Daten für Abholpunkt, falls ausgewählt)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_mss_order_link`: Verknüpft eine einzelne PrestaShop `id_order` (die „Eltern“-Bestellung) mit mehreren `id_order`s (den „Kind“-Bestellungen, die für jede aufgeteilte Sendung erstellt wurden).
  - `id_mss_order_link` (PK)
  - `id_parent_order` (FK zu `ps_orders`)
  - `id_child_order` (FK zu `ps_orders`)
  - `id_mss_split_group` (FK zu `ps_mss_split_group`)
  - `date_add` (DATETIME)
- `ps_mss_refund_log`: Protokolliert Rückerstattungsereignisse im Zusammenhang mit aufgeteilten Bestellungen.
  - `id_mss_refund_log` (PK)
  - `id_order` (FK zu `ps_orders`)
  - `id_order_slip` (FK zu `ps_order_slip`)
  - `amount` (DECIMAL)
  - `reason` (TEXT)
  - `date_add` (DATETIME)
- `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `MULTISHIPSPLIT_ENABLED`, `MULTISHIPSPLIT_DEBUG_MODE` usw. gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich aller Front-Office-Seiten. | Einfügen von CSS- und JS-Assets für die Front-Office-Funktionalität (z. B. `checkout.js`, `checkout.css`). |
| `displayBackOfficeHeader` | Im `<head>`-Bereich aller Back-Office-Seiten. | Einfügen von CSS- und JS-Assets für Admin-Controller (z. B. `admin_rules.js`, `admin_condition_builder.css`). |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Fügt möglicherweise einen Tab oder Abschnitt hinzu, um produktspezifische Aufteilungsregeln oder Überschreibungen zu konfigurieren. |
| `actionCartSave` | Nach dem Speichern oder Aktualisieren eines Warenkorbs. | Fängt Warenkorbänderungen ab, um die Aufteilungslogik auszulösen und Versandgruppen neu zu berechnen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Verarbeitet den aufgeteilten Warenkorb in mehrere PrestaShop-Bestellungen, verknüpft sie und speichert die Daten der aufgeteilten Gruppe. |
| `actionOrderSlipAdd` | Wenn ein Bestellschein (Rückerstattung) hinzugefügt wird. | Handhabt die Rückerstattungslogik für aufgeteilte Bestellungen, protokolliert möglicherweise Teilerstattungen über verknüpfte Bestellungen hinweg. |
| `displayCarrierList` | Im Checkout-Versandschritt, wo Spediteur-Optionen angezeigt werden. | Ersetzt oder erweitert die Standard-Spediteurliste durch die gruppierte Sendungsauswahloberfläche (`checkout_groups.tpl`). |
| `displayOrderConfirmation` | Auf der endgültigen Bestellbestätigungsseite. | Zeigt dem Kunden die Zusammenfassung der aufgeteilten Bestellung an (`order_confirmation_split.tpl`). |
| `displayPaymentTop` | Vor der Auswahl der Zahlungsmethode auf der Checkout-Seite. | Kann wichtige Nachrichten oder Zusammenfassungen zu aufgeteilten Versandkosten anzeigen (`payment_top.tpl`). |
| `displayAdminOrder` | Auf der Bestelldetailseite im Back Office. | Fügt das `order_split_widget.tpl` ein, um zu zeigen, wie die spezifische Bestellung aufgeteilt wurde. |
| `actionObjectCartUpdateAfter` | Nachdem ein Cart-Objekt aktualisiert wurde. | Ähnlich wie `actionCartSave`, stellt sicher, dass die Aufteilungslogik neu bewertet wird. |
| `actionObjectOrderAddAfter` | Nachdem ein neues Order-Objekt hinzugefügt wurde. | Wird verwendet, um die Verknüpfung von Eltern-/Kind-Bestellungen und aufgeteilten Gruppendaten abzuschließen. |
| `actionObjectOrderUpdateAfter` | Nachdem ein Order-Objekt aktualisiert wurde. | Aktualisiert möglicherweise den Status der aufgeteilten Gruppe oder verwandte Daten, wenn eine Bestellung geändert wird. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seinen Inhalt rendert. | Stellt sicher, dass die notwendigen JS/CSS für Front-Office-Seiten geladen werden. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seinen Inhalt rendert. | Stellt sicher, dass die notwendigen JS/CSS für Back-Office-Seiten geladen werden. |
| `displayAdminStatsModules` | Auf der Seite Module > Statistiken. | Fügt möglicherweise modulspezifische Statistiken zum PrestaShop-Dashboard hinzu. |
| `displayDashboardTop` | Oben auf dem PrestaShop-Dashboard. | Kann eine schnelle Zusammenfassung oder Warnung vom Modul anzeigen. |
| `displayDashboardZoneOne` | In der ersten Zone des PrestaShop-Dashboards. | Kann ein modulspezifisches Widget auf dem Dashboard anzeigen. |
| `displayDashboardZoneTwo` | In der zweiten Zone des PrestaShop-Dashboards. | Kann ein modulspezifisches Widget auf dem Dashboard anzeigen. |

## 4. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu.

- **Modul-Updates:** Melden Sie sich unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) an, um die aktuellste Version des Moduls „Warenkorb in separate Sendungen aufteilen“ herunterzuladen.
- **Technischer Support:** Wenn Sie auf Probleme stoßen oder Fragen haben, die in diesem Handbuch nicht behandelt werden, eröffnen Sie bitte ein Support-Ticket über Ihr MyPresta.eu-Kundenkonto. Unser Team steht Ihnen gerne zur Verfügung.

## 5. ## Galerie

![Dashboard auf der Modulkonfigurationsseite, das Modulstatistiken anzeigt](https://mypresta.eu/docs/images/docs/02-shipping-multi-carrier-order-split_1791740311.webp)
