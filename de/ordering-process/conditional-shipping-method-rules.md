---
title: "Regeln für bedingte Versandmethoden - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Conditional Shipping Method Rules' von MyPresta.eu."
sidebar:
  label: "Regeln für bedingte Versandmethoden"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Conditional Shipping Method Rules auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/conditional-shipping-method-rules.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/conditional-shipping-method-rules/)
>
> ---


# Regeln für bedingte Versandmethoden

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen PrestaShop-Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach "Conditional Shipping Method Rules" suchen und auf "Konfigurieren" klicken.

Diese Seite bietet allgemeine Einstellungen für das Verhalten des Moduls.

-   **Modul aktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Funktionalität des Moduls ein- oder auszuschalten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Alle Ihre definierten Versandregeln sind aktiv und beeinflussen die im Checkout angezeigten Versandmethoden.
        -   *Wenn deaktiviert:* Das Modul ist inaktiv, und die Standardauswahl der Versandmethode von PrestaShop wird angewendet, wobei alle Ihre benutzerdefinierten Regeln ignoriert werden.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Sie könnten es vorübergehend während der Wartung deaktivieren oder wenn Sie schnell zum Standardversandverhalten zurückkehren müssen. Für den normalen Betrieb lassen Sie es aktiviert.

-   **Zusammenführungsstrategie für mehrere Regeln:**
    -   **Was diese Einstellung bewirkt:** Legt fest, wie das Modul die Ergebnisse mehrerer aktiver Regeln kombiniert, wenn diese auf dieselbe Versandmethode angewendet werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Option A (Priorisiere "ANZEIGEN"):* Wenn *irgendeine* aktive Regel besagt, einen Spediteur "ANZEIGEN", wird er angezeigt, auch wenn andere Regeln besagen, ihn "AUSBLENDEN". Dies ist eine nachsichtigere Strategie.
        -   *Option B (Priorisiere "AUSBLENDEN"):* Wenn *irgendeine* aktive Regel besagt, einen Spediteur "AUSBLENDEN", wird er ausgeblendet, auch wenn andere Regeln besagen, ihn "ANZEIGEN". Dies ist eine restriktivere Strategie.
        -   *Option C (Benutzerdefinierte Zusammenführungsstrategie 1):* [Detaillierte Erklärung der spezifischen Logik, z. B. "Nur anzeigen, wenn ALLE anwendbaren Regeln ANZEIGEN sagen"]
        -   *Option D (Benutzerdefinierte Zusammenführungsstrategie 2):* [Detaillierte Erklärung der spezifischen Logik]
        -   *Option E (Benutzerdefinierte Zusammenführungsstrategie 3):* [Detaillierte Erklärung der spezifischen Logik]
    -   **Empfohlener Wert:** Priorisiere "AUSBLENDEN" (zur Sicherheit, um sicherzustellen, dass keine unerwünschten Spediteure angezeigt werden). Dies hängt jedoch stark von Ihrer spezifischen Regeleinrichtung ab.
    -   **Händlerszenario / Beispiel:** Wenn Sie eine Regel haben, die besagt, kostenlosen Versand für Bestellungen über 100 € "ANZEIGEN", aber eine andere Regel, die besagt, kostenlosen Versand für ein bestimmtes Produkt "AUSBLENDEN", bestimmt die Zusammenführungsstrategie, welche Regel gewinnt. "Priorisiere AUSBLENDEN" würde den kostenlosen Versand für dieses Produkt ausblenden, auch wenn die Bestellung über 100 € liegt.

-   **Nachrichten für nicht verfügbare Versandmethoden anzeigen:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob Kunden eine Erklärung sehen, wenn eine Versandmethode durch eine Regel ausgeblendet wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Wenn ein Spediteur ausgeblendet wird, wird dem Kunden eine Nachricht (die Sie pro Regel definieren) angezeigt, die erklärt, warum er nicht verfügbar ist.
        -   *Wenn deaktiviert:* Ausgeblendete Spediteure verschwinden einfach aus der Liste ohne Erklärung.
    -   **Empfohlener Wert:** JA (Verbessert das Kundenerlebnis und reduziert Verwirrung).
    -   **Händlerszenario / Beispiel:** Wenn "Expressversand" ausgeblendet ist, weil der Warenkorb des Kunden einen "Zerbrechlichen Artikel" enthält, der nicht per Express versendet werden kann, wird durch Aktivierung dieser Option eine Nachricht wie "Expressversand ist für zerbrechliche Artikel nicht verfügbar" angezeigt.

-   **Aufbewahrungsdauer des Audit-Logs (Tage):**
    -   **Was diese Einstellung bewirkt:** Definiert, wie lange das Modul Aufzeichnungen von Regelbewertungen und deren Ergebnissen im Audit-Log speichert.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Einstellung einer Zahl (z. B. 30):* Das Modul löscht automatisch Log-Einträge, die älter als diese Anzahl von Tagen sind.
        -   *Einstellung auf 0 oder leer:* Das Modul behält alle Log-Einträge auf unbestimmte Zeit (kann im Laufe der Zeit zu einer großen Datenbank führen).
    -   **Empfohlener Wert:** 30-90 Tage (ausreichend für die Fehlerbehebung ohne übermäßiges Datenbankwachstum).
    -   **Händlerszenario / Beispiel:** Wenn ein Kunde sich beschwert, eine bestimmte Versandmethode nicht gesehen zu haben, können Sie das Audit-Log nach aktuellen Bewertungen durchsuchen. Das Speichern von Logs für 30 Tage ermöglicht es Ihnen, aktuelle Probleme zu untersuchen, ohne jahrelange Daten zu speichern.

-   **Checkout-Simulator aktivieren:**
    -   **Was diese Einstellung bewirkt:** Aktiviert ein Tool im Back Office, mit dem Sie Ihre Versandregeln testen können, indem Sie verschiedene Kunden- und Warenkorbszenarien simulieren.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Der Tab "Checkout-Simulator" erscheint in der Modulkonfiguration und bietet eine leistungsstarke Testumgebung.
        -   *Wenn deaktiviert:* Der Simulator ist nicht verfügbar.
    -   **Empfohlener Wert:** JA (Unerlässlich zum Testen komplexer Regeln vor der Bereitstellung).
    -   **Händlerszenario / Beispiel:** Vor dem Start einer neuen Versandaktion können Sie den Simulator verwenden, um sicherzustellen, dass Ihre Regeln den Aktionsversand für verschiedene Warenkorbwerte, Kundengruppen und Adressen korrekt anzeigen/ausblenden.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Versandrichtlinien (Back Office > Module > Conditional Shipping Method Rules > Versandrichtlinien)
Dies ist der Kernbildschirm, auf dem Sie alle Ihre Versandregeln definieren und verwalten.

-   **Bildschirmname & Menüpfad:** **Conditional Shipping Method Rules > Versandrichtlinien** (zu finden unter dem Abschnitt "Module" in Ihrem PrestaShop Back Office Menü).
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Richtlinienliste:** Eine Tabelle, die alle Ihre erstellten Versandrichtlinien anzeigt. Jede Richtlinie hat einen Namen, Status (aktiviert/deaktiviert) und Aktionen.
    -   **Neue Richtlinie hinzufügen:** Eine Schaltfläche zum Erstellen einer neuen Versandrichtlinie.
    -   **Richtlinie bearbeiten:** Klicken Sie auf eine bestehende Richtlinie, um deren Regeln, Bedingungen und Einstellungen zu ändern.
    -   **Richtlinie duplizieren:** Erstellen Sie schnell eine Kopie einer bestehenden Richtlinie, nützlich für geringfügige Variationen.
    -   **Richtlinie aktivieren/deaktivieren:** Schalten Sie den aktiven Status einer Richtlinie um, ohne sie zu löschen.
    -   **Richtlinie löschen:** Entfernen Sie eine Richtlinie dauerhaft.
    -   **Richtlinien-Konfigurationsformular (beim Hinzufügen/Bearbeiten):**
        -   **Richtlinienname:** Ein beschreibender Name für Ihr Regelwerk (z. B. "Kostenloser Versand über 100 €", "Expressversand-Beschränkungen").
        -   **Status:** Aktivieren oder deaktivieren Sie diese spezifische Richtlinie.
        -   **Priorität:** Wenn mehrere Richtlinien zutreffen, bestimmt dies die Reihenfolge, in der sie ausgewertet werden. Kleinere Zahlen bedeuten höhere Priorität.
        -   **Ziel-Spediteure:** Wählen Sie aus, welche spezifischen Versandspediteure von dieser Richtlinie betroffen sind.
        -   **Aktion (ANZEIGEN/AUSBLENDEN):** Wählen Sie, ob diese Richtlinie die ausgewählten Spediteure *anzeigen* oder *ausblenden* soll, wenn die Bedingungen erfüllt sind.
        -   **Nachricht bei Nichtverfügbarkeit:** Wenn Sie "AUSBLENDEN" gewählt haben und "Nachrichten für nicht verfügbare Versandmethoden anzeigen" in der Hauptkonfiguration aktiviert ist, ist dies die Nachricht, die Kunden sehen werden (mehrsprachig).
        -   **Bedingungs-Builder:** Hier definieren Sie den "WENN"-Teil Ihrer Regel. Sie können mehrere Bedingungsgruppen (UND/ODER-Logik) hinzufügen, basierend auf:
            -   Warenkorb-Gesamtwert, Gewicht, Menge
            -   Spezifische Produkte oder Kategorien im Warenkorb
            -   Kundengruppe, Land, Bundesland, Postleitzahl
            -   Datum und Uhrzeit
            -   Und viele weitere Kriterien.
-   **Auswirkung von Änderungen:**
    -   Das Hinzufügen, Bearbeiten oder Löschen von Richtlinien wirkt sich direkt darauf aus, welche Versandmethoden den Kunden im Checkout präsentiert werden, basierend auf den definierten Bedingungen.
    -   Das Ändern des Status einer Richtlinie (aktivieren/deaktivieren) aktiviert oder deaktiviert deren Wirkung im Front Office sofort.
    -   Das Anpassen der Priorität kann Konflikte lösen, wenn mehrere Richtlinien auf denselben Spediteur zutreffen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  **Planen Sie Ihre Regel:** Definieren Sie klar, was Sie erreichen möchten (z. B. "Wenn Warenkorb-Gesamtwert > 50 € UND Kunde in den USA ist, DANN 'Standardversand' ANZEIGEN").
    2.  **Erstellen Sie eine neue Richtlinie:** Geben Sie ihr einen klaren Namen.
    3.  **Wählen Sie Ziel-Spediteure:** Wählen Sie die Spediteure aus, die von dieser Richtlinie betroffen sein sollen.
    4.  **Legen Sie die Aktion fest:** Entscheiden Sie, ob die Richtlinie diese Spediteure ANZEIGEN oder AUSBLENDEN soll.
    5.  **Bedingungen erstellen:** Verwenden Sie den intuitiven Bedingungs-Builder, um Ihre "WENN"-Anweisungen einzurichten. Verwenden Sie "Bedingungsgruppe hinzufügen" für ODER-Logik und "Bedingung hinzufügen" innerhalb einer Gruppe für UND-Logik.
    6.  **Mit Simulator testen:** Verwenden Sie unbedingt den "Checkout-Simulator" (siehe nächster Abschnitt), um zu überprüfen, ob Ihre Regeln für verschiedene Szenarien wie erwartet funktionieren.
    7.  **Aktivieren:** Sobald getestet, aktivieren Sie die Richtlinie.

#### 2.2.2 Audit-Log (Back Office > Module > Conditional Shipping Method Rules > Audit-Log)
Dieser Bildschirm bietet eine historische Aufzeichnung darüber, wie Ihre Versandregeln ausgewertet wurden.

-   **Bildschirmname & Menüpfad:** **Conditional Shipping Method Rules > Audit-Log** (zu finden unter dem Abschnitt "Module" in Ihrem PrestaShop Back Office Menü).
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Log-Tabelle:** Eine detaillierte Liste jedes Mal, wenn das Modul Versandregeln für den Warenkorb eines Kunden ausgewertet hat.
    -   **Spalten:** Enthält Informationen wie:
        -   Datum und Uhrzeit der Auswertung
        -   Kunden-ID (falls angemeldet)
        -   Warenkorb-ID
        -   Angewandte Richtlinien: Welche Richtlinien berücksichtigt wurden.
        -   Ergebnis: Welche Spediteure angezeigt/ausgeblendet wurden und warum.
        -   Bestell-Snapshot: Ein Link zur Ansicht des genauen Zustands des Warenkorbs zum Zeitpunkt der Auswertung.
    -   **Filtern & Sortieren:** Standardmäßige PrestaShop-Listenfunktionen zum Filtern nach Datum, Kunde oder Warenkorb-ID.
-   **Auswirkung von Änderungen:** Dies ist ein schreibgeschützter Bildschirm zur Überwachung und Fehlerbehebung. Sie können hier keine direkten Änderungen vornehmen, aber die Daten helfen Ihnen zu verstehen, wie Ihre Regeln funktionieren.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    -   Verwenden Sie dieses Protokoll, um von Kunden gemeldete Probleme zu diagnostizieren (z. B. "Ich habe keinen kostenlosen Versand gesehen"). Sie können deren Warenkorb-ID oder Kunden-ID finden und genau sehen, welche Regeln angewendet wurden und was das Ergebnis war.
    -   Überprüfen Sie das Protokoll regelmäßig, um sicherzustellen, dass die Regeln wie erwartet ausgelöst werden, insbesondere nach Änderungen an Richtlinien.

#### 2.2.3 Checkout-Simulator (Back Office > Module > Conditional Shipping Method Rules > Checkout-Simulator)
Dieses leistungsstarke Tool ermöglicht es Ihnen, Ihre Versandregeln zu testen, ohne eine echte Bestellung aufzugeben.

-   **Bildschirmname & Menüpfad:** **Conditional Shipping Method Rules > Checkout-Simulator** (zu finden unter dem Abschnitt "Module" in Ihrem PrestaShop Back Office Menü, nur sichtbar, wenn "Checkout-Simulator aktivieren" in der Hauptkonfiguration aktiv ist).
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Kundenauswahl:** Wählen Sie einen bestehenden Kunden aus Ihrem Shop oder simulieren Sie einen Gast.
    -   **Adressauswahl:** Wählen Sie eine bestimmte Adresse für den ausgewählten Kunden oder geben Sie Adressdetails manuell ein.
    -   **Warenkorbinhalt:** Fügen Sie bestimmte Produkte, Mengen und Kombinationen hinzu, um den Warenkorb eines Kunden zu simulieren.
    -   **Simulieren-Schaltfläche:** Klicken Sie hier, um die Simulation auszuführen.
    -   **Ergebnisanzeige:** Zeigt an, welche Versandmethoden für das simulierte Szenario verfügbar wären (und welche mit ihren Nachrichten ausgeblendet würden). Es werden auch die angewendeten Richtlinien und deren Begründung detailliert aufgeführt.
-   **Auswirkung von Änderungen:** Dieser Bildschirm ändert keine Live-Shop-Daten. Es ist ausschließlich eine Testumgebung.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    -   **Vor der Aktivierung neuer Richtlinien:** Testen Sie diese immer gründlich hier.
    -   **Fehlerbehebung:** Stellen Sie ein vom Kunden gemeldetes Problem nach, indem Sie dessen genauen Warenkorb und seine Adresse simulieren, um zu sehen, warum ein Spediteur angezeigt oder nicht angezeigt wurde.
    -   **Komplexe Szenarien:** Testen Sie Grenzfälle, wie Mindest-/Höchstbestellwerte, spezifische Produktkombinationen oder verschiedene Kundengruppen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
| | Zusammenführungsstrategie für mehrere Regeln | Priorisiere "AUSBLENDEN" | Wie widersprüchliche Regeln gelöst werden (ANZEIGEN vs. AUSBLENDEN). |
| | Nachrichten für nicht verfügbare Versandmethoden anzeigen | JA | Erklärungen für ausgeblendete Spediteure für Kunden anzeigen. |
| | Aufbewahrungsdauer des Audit-Logs (Tage) | 30-90 | Wie lange die Protokolle der Regelbewertung aufbewahrt werden. |
| | Checkout-Simulator aktivieren | JA | Aktiviert das Testtool im Back Office. |
| **Versandrichtlinien** | Richtlinienname | Beschreibender Name | Identifiziert das Regelwerk. |
| | Status | Aktiviert | Aktiviert/deaktiviert diese spezifische Richtlinie. |
| | Priorität | Kleinere Zahl = höhere Priorität | Bestimmt die Auswertungsreihenfolge für widersprüchliche Richtlinien. |
| | Ziel-Spediteure | Spezifische Spediteure | Welche Versandmethoden diese Richtlinie betrifft. |
| | Aktion (ANZEIGEN/AUSBLENDEN) | ANZEIGEN/AUSBLENDEN | Ob Ziel-Spediteure angezeigt oder ausgeblendet werden sollen, wenn Bedingungen erfüllt sind. |
| | Nachricht bei Nichtverfügbarkeit | Benutzerdefinierter Text (mehrsprachig) | Nachricht, die angezeigt wird, wenn der Spediteur ausgeblendet ist (falls aktiviert). |
| | Bedingungs-Builder | Variiert | Definiert die "WENN"-Kriterien für die Anwendung der Richtlinie. |
| **Audit-Log** | (Alle Spalten) | N/A (Nur-Lesezugriff) | Bietet historische Aufzeichnungen von Regelbewertungen zur Fehlerbehebung. |
| **Checkout-Simulator** | (Alle Felder) | N/A (Testtool) | Ermöglicht die Simulation von Kunden-/Warenkorbszenarien zum Testen von Regeln. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Regeln funktionieren nicht, oder ich sehe unerwartete Versandoptionen. Was soll ich tun?**
A1:
1.  **Modulstatus prüfen:** Stellen Sie sicher, dass die Einstellung "Modul aktivieren" auf der Hauptkonfigurationsseite auf JA gesetzt ist.
2.  **Richtlinienstatus prüfen:** Gehen Sie zu "Versandrichtlinien" und überprüfen Sie, ob die spezifischen Richtlinien, die Sie erwarten, aktiv sind, aktiviert sind.
3.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren". Manchmal speichert PrestaShop alte Konfigurationen im Cache.
4.  **Checkout-Simulator verwenden:** Dies ist Ihr bester Freund! Erstellen Sie das genaue Szenario (Kunde, Adresse, Warenkorbinhalt) im Simulator nach. Er zeigt Ihnen genau, welche Regeln angewendet wurden und warum, und hilft Ihnen, das Problem zu lokalisieren.
5.  **Audit-Log überprüfen:** Wenn ein Kunde ein Problem gemeldet hat, überprüfen Sie das "Audit-Log" für dessen Warenkorb-/Kunden-ID, um zu sehen, wie die Regeln für dessen spezifische Bestellung ausgewertet wurden.
6.  **Zusammenführungsstrategie:** Überprüfen Sie Ihre Einstellung "Zusammenführungsstrategie für mehrere Regeln". Wenn Sie widersprüchliche ANZEIGEN- und AUSBLENDEN-Regeln haben, bestimmt diese Einstellung das Ergebnis.

**F2: Warum wird meine benutzerdefinierte "Nachricht bei Nichtverfügbarkeit" nicht angezeigt?**
A2:
1.  **Nachrichtenanzeige aktivieren:** Stellen Sie auf der Hauptkonfigurationsseite des Moduls sicher, dass "Nachrichten für nicht verfügbare Versandmethoden anzeigen" auf JA gesetzt ist.
2.  **Richtlinienaktion:** Überprüfen Sie, ob die "Aktion" der Richtlinie für den Ziel-Spediteur auf "AUSBLENDEN" gesetzt ist. Nachrichten werden nur angezeigt, wenn ein Spediteur ausgeblendet ist.
3.  **Nachrichteninhalte:** Stellen Sie sicher, dass Sie tatsächlich eine Nachricht in das Feld "Nachricht bei Nichtverfügbarkeit" für die spezifische Richtlinie eingegeben haben und dass diese für die relevanten Sprachen übersetzt ist.

**F3: Das Modul verlangsamt meinen Checkout. Ist das normal?**
A3: Das Modul ist hochoptimiert, aber sehr komplexe Regeln (z. B. Hunderte von Bedingungen, viele Richtlinien) können einen geringen Overhead verursachen.
1.  **Regeln vereinfachen:** Überprüfen Sie Ihre Richtlinien. Können einige kombiniert oder vereinfacht werden?
2.  **Priorisieren:** Stellen Sie sicher, dass Ihre am häufigsten ausgelösten Regeln eine höhere Priorität (kleinere Zahl) haben, damit sie zuerst ausgewertet werden.
3.  **Datenbankgröße:** Überprüfen Sie Ihre Einstellung "Aufbewahrungsdauer des Audit-Logs". Wenn sie auf unbegrenzte Speicherung von Protokollen eingestellt ist, kann eine sehr große Protokolltabelle die Leistung beeinträchtigen. Stellen Sie sie auf eine angemessene Anzahl von Tagen (z. B. 30-90) ein.

**F4: Wie stelle ich sicher, dass mein benutzerdefiniertes Theme die Versandoptionen korrekt anzeigt?**
A4: Das Modul integriert sich in den Standard-Checkout-Prozess von PrestaShop.
1.  **Standard-Hooks:** Das Modul verwendet Standard-PrestaShop-Hooks. Wenn Ihr Theme den Checkout stark anpasst, stellen Sie sicher, dass es immer noch korrekt die `displayCarrierList` oder ähnliche Hooks aufruft, wo die Versandoptionen gerendert werden.
2.  **CSS-Konflikte:** Wenn die Anzeige fehlerhaft aussieht (z. B. Nachrichten sind falsch ausgerichtet), könnte es einen CSS-Konflikt mit Ihrem Theme geben. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Elemente zu überprüfen und widersprüchliche CSS-Regeln zu identifizieren. Möglicherweise müssen Sie Ihrem Theme benutzerdefiniertes CSS hinzufügen, um Modul- oder Theme-Stile zu überschreiben.
3.  **Support kontaktieren:** Wenn Sie ein stark angepasstes Theme verwenden und auf anhaltende Anzeigeprobleme stoßen, geben Sie Details an den MyPresta.eu-Support weiter.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul "Conditional Shipping Method Rules" (`shipmethodrules`) ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut, wobei `ObjectModel` für die Datenpersistenz und eine benutzerdefinierte Richtlinien-Engine für die Regelauswertung stark genutzt werden. Es führt mehrere benutzerdefinierte Admin-Controller zur Verwaltung von Richtlinien, zur Anzeige von Audit-Logs und zur Simulation von Checkout-Szenarien ein. Die Kernlogik dreht sich um `ShipmethodrulesPolicy`-Objekte, die `ShipmethodrulesConditionGroup`- und `ShipmethodrulesCondition`-Entitäten kapseln und eine komplexe verschachtelte UND/ODER-Logik ermöglichen. Die `ShipmethodrulesEngine` ist für die Auswertung dieser Richtlinien anhand eines gegebenen `ShipmethodrulesContext` (der den aktuellen Warenkorb, Kunden und die Adresse repräsentiert) und die Bestimmung der Sichtbarkeit von Versandspediteuren verantwortlich.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller
-   `controllers/front/index.php`:
    -   Klassenname: `ShipmethodrulesIndexModuleFrontController`
    -   Elternklasse: `ModuleFrontController`
    -   Verantwortlichkeit: Wahrscheinlich ein Platzhalter oder Basis-Controller. In vielen Modulen könnte dies die anfängliche Einrichtung oder Weiterleitung handhaben, wenn eine dedizierte Front-Office-Seite benötigt wird. Für dieses Modul ist die primäre Front-Office-Logik über Hooks in den Checkout-Prozess integriert.
-   `controllers/front/simulate.php`:
    -   Klassenname: `ShipmethodrulesSimulateModuleFrontController`
    -   Elternklasse: `ModuleFrontController`
    -   Verantwortlichkeit: Behandelt AJAX-Anfragen im Zusammenhang mit dem Checkout-Simulator. Es empfängt simulierte Warenkorb-, Kunden- und Adressdaten, verwendet dann die `ShipmethodrulesEngine`, um Richtlinien auszuwerten und gibt die resultierende Spediteur-Sichtbarkeit zurück.
-   `controllers/front/visibility.php`:
    -   Klassenname: `ShipmethodrulesVisibilityModuleFrontController`
    -   Elternklasse: `ModuleFrontController`
    -   Verantwortlichkeit: Dieser Controller ist entscheidend für Echtzeit-Updates auf der Checkout-Seite. Er reagiert auf AJAX-Anfragen (z. B. wenn ein Kunde die Adresse oder den Warenkorbinhalt ändert), um die Versandregeln neu zu bewerten und die aktualisierte Liste der verfügbaren Spediteure und deren zugehörige Nachrichten zurückzugeben.

#### Back-Office-Admin-Controller
-   `controllers/admin/AdminShipmethodrulesAuditLog.php`:
    -   Klassenname: `AdminShipmethodrulesAuditLogController`
    -   Elternklasse: `ModuleAdminController`
    -   Tab-Name: "Audit-Log"
    -   Verwaltete Entität: `ShipmethodrulesLog`
    -   Verantwortlichkeit: Verwaltet die Anzeige und Filterung der Tabelle `ps_shipmethodrules_log`. Es bietet eine Rasteransicht aller Regelauswertungen, einschließlich Details zum Warenkorb, Kunden, angewandten Richtlinien und dem Endergebnis (welche Spediteure angezeigt/ausgeblendet wurden).
-   `controllers/admin/AdminShipmethodrulesPolicies.php`:
    -   Klassenname: `AdminShipmethodrulesPoliciesController`
    -   Elternklasse: `ModuleAdminController`
    -   Tab-Name: "Versandrichtlinien"
    -   Verwaltete Entität: `ShipmethodrulesPolicy`
    -   Verantwortlichkeit: Dies ist der primäre Controller zur Verwaltung von Versandrichtlinien. Er handhabt das Auflisten, Hinzufügen, Bearbeiten, Duplizieren, Aktivieren/Deaktivieren und Löschen von `ShipmethodrulesPolicy`-Objekten. Er orchestriert auch die Bedingungs-Builder-Oberfläche.
-   `controllers/admin/index.php`:
    -   Klassenname: `ShipmethodrulesAdminController` (oder ähnlich, wenn es ein Basis-Controller für den Admin-Bereich des Moduls ist)
    -   Elternklasse: `ModuleAdminController`
    -   Verantwortlichkeit: Fungiert oft als Dispatcher oder Standard-Controller für den Haupteintrag des Modul-Admin-Menüs und leitet zur primären Konfiguration oder Richtlinienliste weiter.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `classes/ShipmethodrulesAdmin.php`: Wahrscheinlich eine Hilfsklasse für allgemeine Admin-bezogene Funktionen oder Dashboard-Statistiken.
-   `classes/ShipmethodrulesAuditLog.php`: Erweitert `ObjectModel`. Bildet die Tabelle `ps_shipmethodrules_log` ab. Speichert Details jedes Regelauswertungsereignisses zu Prüfzwecken.
    -   `$definition`-Felder: `id_cart`, `id_customer`, `id_address_delivery`, `policies_applied`, `carriers_visibility`, `timestamp`.
-   `classes/ShipmethodrulesCompatibility.php`: Bietet Methoden zur Handhabung von Unterschieden zwischen PrestaShop 1.7, 8 und 9, um die Kompatibilität über Versionen hinweg für Kernfunktionen (z. B. Hook-Registrierung, Konfigurationszugriff) sicherzustellen.
-   `classes/ShipmethodrulesCondition.php`: Erweitert `ObjectModel`. Repräsentiert eine einzelne Bedingung innerhalb einer Bedingungsgruppe (z. B. "Warenkorb-Gesamtwert > 100 €").
    -   `$definition`-Felder: `id_shipmethodrules_condition_group`, `type`, `operator`, `value`, `id_product`, `id_category`, etc.
-   `classes/ShipmethodrulesConditionEvaluator.php`: Enthält die Logik zur Auswertung einer einzelnen `ShipmethodrulesCondition` anhand des aktuellen `ShipmethodrulesContext`.
-   `classes/ShipmethodrulesConditionGroup.php`: Erweitert `ObjectModel`. Repräsentiert eine Gruppe von Bedingungen, die durch einen UND-Operator verknüpft sind. Mehrere Gruppen können innerhalb einer Richtlinie durch einen ODER-Operator verknüpft werden.
    -   `$definition`-Felder: `id_shipmethodrules_policy`, `logic_operator` (implizit UND für Bedingungen innerhalb, ODER für Gruppen).
-   `classes/ShipmethodrulesConditionTree.php`: Verwaltet die hierarchische Struktur von Bedingungen und Bedingungsgruppen für eine Richtlinie und erleichtert deren Speicherung und Abruf.
-   `classes/ShipmethodrulesContext.php`: Ein Objekt, das alle relevanten Daten für die Regelauswertung kapselt: aktueller `Cart`, `Customer`, `Address`, `Currency`, `Language`, etc. Dies bietet eine konsistente Schnittstelle für die `ShipmethodrulesEngine`.
-   `classes/ShipmethodrulesDashboard.php`: Hilfsklasse zum Generieren von Dashboard-Statistiken oder Zusammenfassungen im Zusammenhang mit der Modulaktivität.
-   `classes/ShipmethodrulesEngine.php`: Die zentrale Klasse für die Regelauswertung. Sie nimmt einen `ShipmethodrulesContext` und eine Liste von `ShipmethodrulesPolicy`-Objekten entgegen, wendet die konfigurierte Zusammenführungsstrategie an und gibt den endgültigen Sichtbarkeitsstatus für jeden Spediteur zurück.
-   `classes/ShipmethodrulesListRenderer.php`: Benutzerdefinierter Renderer für Admin-Listen, der möglicherweise spezifische Aktionen (wie Duplizieren) oder benutzerdefinierte Spaltenformatierungen hinzufügt.
-   `classes/ShipmethodrulesLog.php`: Alias oder spezifische Implementierung für `ShipmethodrulesAuditLog`.
-   `classes/ShipmethodrulesOrderSnapshot.php`: Erfasst und speichert einen Snapshot des Zustands einer Bestellung (Warenkorb, Kunde, Adresse) zum Zeitpunkt der Regelauswertung, nützlich für das Debugging.
-   `classes/ShipmethodrulesPolicy.php`: Erweitert `ObjectModel`. Das Hauptmodell für eine Versandregel. Es enthält den Namen, Status, Priorität, Ziel-Spediteure, Aktion (ANZEIGEN/AUSBLENDEN), Nachricht bei Nichtverfügbarkeit und eine Sammlung von `ShipmethodrulesConditionGroup`-Objekten.
    -   `$definition`-Felder: `name`, `active`, `priority`, `action`, `unavailable_message`, `target_carriers`.
-   `classes/ShipmethodrulesPolicyDuplicator.php`: Behandelt die Logik zum Duplizieren einer `ShipmethodrulesPolicy`, einschließlich aller zugehörigen Bedingungsgruppen und Bedingungen.
-   `classes/ShipmethodrulesPreset.php`: Verwaltet wahrscheinlich vordefinierte Sätze von Bedingungen oder Richtlinien, die schnell angewendet werden können.
-   `classes/ShipmethodrulesRule.php`: Eine allgemeinere Darstellung einer Regel, möglicherweise eine abstrakte Basisklasse oder eine ältere Iteration von `ShipmethodrulesPolicy`.
-   `classes/ShipmethodrulesTreeRepository.php`: Verwaltet die Persistenz und den Abruf der Bedingungsbaumstruktur.

### 4.4 JavaScript-Assets (`views/js/`)

-   `shipmethodrules/lib/searchTool/views/js/autocomplete.js`: Generische Autocomplete-Funktionalität, wahrscheinlich verwendet zum Suchen von Produkten, Kategorien oder Kunden im Bedingungs-Builder.
-   `shipmethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplikat oder spezifische Instanz des Autocomplete-Skripts.
-   `shipmethodrules/views/js/adminConditionBuilder.js`: Behandelt die dynamische Erstellung, Änderung und Löschung von Bedingungen und Bedingungsgruppen innerhalb der Richtlinienbearbeitungsoberfläche. Verwaltet die komplexe Benutzeroberfläche zum Erstellen von Regeln.
-   `shipmethodrules/views/js/adminPolicyRules.js`: Spezifisches JS für den `AdminShipmethodrulesPolicies`-Controller, das die Liste der Richtlinien, Massenaktionen und potenziell Interaktionen mit dem Bedingungs-Builder verwaltet.
-   `shipmethodrules/views/js/adminShipmethodrulesDashboard.js`: Skripte für alle Dashboard-Widgets oder Statistiken, die im Admin-Bereich des Moduls angezeigt werden.
-   `shipmethodrules/views/js/adminShipmethodrulesSearchTool.js`: Integriert das Suchwerkzeug (Autocomplete) speziell für die Admin-Formulare des Moduls.
-   `shipmethodrules/views/js/adminShipmethodrulesSimulator.js`: Betreibt die Oberfläche des "Checkout-Simulators", verarbeitet Benutzereingaben für Kunde, Adresse und Warenkorb und führt AJAX-Aufrufe an `controllers/front/simulate.php` aus.
-   `shipmethodrules/views/js/checkout.js`: Front-Office-Skript, das in den Checkout-Prozess injiziert wird. Es überwacht Änderungen im Warenkorb oder in der Lieferadresse und führt dann AJAX-Aufrufe an `controllers/front/visibility.php` aus, um die angezeigten Versandmethoden dynamisch zu aktualisieren.
-   `shipmethodrules/views/js/unavailableUi.js`: Behandelt die Anzeige und Gestaltung von Nachrichten für nicht verfügbare Versandmethoden auf der Front-Office-Checkout-Seite.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `shipmethodrules/lib/searchTool/views/css/autocomplete.css`: Stile für das Autocomplete-Suchwerkzeug.
-   `shipmethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplikat oder spezifische Instanz von Autocomplete-Stilen.
-   `shipmethodrules/views/css/admin_order_snapshot.css`: Stile zur Anzeige der Bestelldetails im Audit-Log oder Simulator.
-   `shipmethodrules/views/css/admin_shipmethodrules.css`: Allgemeine Stile für die Back-Office-Oberflächen des Moduls, einschließlich Richtlinienlisten, Bedingungs-Builder und Simulator.
-   `shipmethodrules/views/css/front.css`: Front-Office-Stile zur Anzeige von Nachrichten für nicht verfügbare Versandmethoden oder zur Hervorhebung spezifischer Versandoptionen auf der Checkout-Seite.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)
-   `shipmethodrules/views/templates/hook/carrier_guard.tpl`: Rendert ein verstecktes Eingabefeld oder Skript, um ungültige Spediteurauswahlen zu "schützen" und sicherzustellen, dass nur erlaubte Spediteure übermittelt werden können.
-   `shipmethodrules/views/templates/hook/carrier_list.tpl`: Überschreibt oder erweitert das Standard-Spediteurlisten-Template im Checkout, um Sichtbarkeitsregeln anzuwenden und Nachrichten bei Nichtverfügbarkeit anzuzeigen. Hier wird die gefilterte Liste der Spediteure tatsächlich gerendert.

#### Admin-Templates (`views/templates/admin/`)
-   `shipmethodrules/views/templates/admin/auditPreview.tpl`: Template zur Anzeige einer detaillierten Vorschau eines Audit-Log-Eintrags.
-   `shipmethodrules/views/templates/admin/dashboard.tpl`: Template für die Hauptkonfiguration oder Dashboard-Ansicht des Moduls.
-   `shipmethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Benutzerdefiniertes Template für die Schaltfläche "Duplizieren" in Admin-Listen (z. B. für Richtlinien).
-   `shipmethodrules/views/templates/admin/policiesPreview.tpl`: Template zur Anzeige einer Vorschau einer Versandrichtlinie.
-   `shipmethodrules/views/templates/admin/policyConditionBuilder.tpl`: Das komplexe Template, das die Benutzeroberfläche zum Erstellen von Bedingungen (Dropdowns, Eingabefelder, UND/ODER-Logik) rendert.
-   `shipmethodrules/views/templates/admin/policyRuleCard.tpl`: Rendert eine einzelne Regel oder Richtlinie als Karte in einer Listenansicht.
-   `shipmethodrules/views/templates/admin/policyRulesTable.tpl`: Rendert die Tabelle der Versandrichtlinien.
-   `shipmethodrules/views/templates/admin/scopeSelector.tpl`: Template zur Auswahl des Geltungsbereichs einer Bedingung (z. B. "Warenkorb-Gesamtwert", "Kundengruppe").

#### Andere Templates
-   `shipmethodrules/lib/searchTool/views/scripts.tpl`: Enthält JavaScript für das Suchwerkzeug.
-   `shipmethodrules/lib/searchTool/views/views/scripts.tpl`: Duplikat oder spezifische Instanz von Suchwerkzeug-Skripten.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen
-   `ps_shipmethodrules_policy`: Speichert die Hauptdefinitionen der Versandrichtlinien (Name, aktiver Status, Priorität, Aktion, Nachricht bei Nichtverfügbarkeit, Ziel-Spediteure).
-   `ps_shipmethodrules_condition_group`: Speichert Bedingungsgruppen, die einer Richtlinie zugeordnet sind.
-   `ps_shipmethodrules_condition`: Speichert einzelne Bedingungen (Typ, Operator, Wert, zugehörige Entitäten wie Produkt-/Kategorie-IDs).
-   `ps_shipmethodrules_log`: Speichert Audit-Log-Einträge von Regelauswertungen (Warenkorb-ID, Kunden-ID, Zeitstempel, angewandte Richtlinien, Spediteur-Sichtbarkeit).
-   `ps_shipmethodrules_order_snapshot`: Speichert detaillierte Snapshots von Warenkorb-/Bestelldaten für Audit-Log-Einträge.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Abschnitt aller Front-Office-Seiten. | Injiziert notwendige CSS- und JS-Dateien für die Front-Office-Funktionalität (z. B. `checkout.js`, `front.css`). |
| `displayCarrierList` | Auf der Checkout-Seite, wo die Versandmethoden aufgelistet sind. | Der primäre Hook zum Filtern und Rendern der verfügbaren Versandmethoden basierend auf definierten Richtlinien. |
| `actionCarrierProcess` | Nachdem ein Spediteur ausgewählt wurde, aber bevor die Bestellung validiert wird. | Fungiert als "Schutz", um den ausgewählten Spediteur erneut anhand der Regeln zu validieren und die Übermittlung einer ungültigen Auswahl zu verhindern. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Protokolliert möglicherweise die endgültig gewählte Versandmethode und die angewandten Regeln im Audit-Log. |
| `actionAdminControllerSetMedia` | Im Back Office, wenn ein Admin-Controller geladen wird. | Injiziert CSS und JS für die Admin-Oberflächen des Moduls (Richtlinien-Builder, Simulator, Audit-Log). |
| `actionObjectCarrierAddAfter` | Nachdem ein neuer Spediteur hinzugefügt wurde. | Aktualisiert möglicherweise interne Moduldaten oder Caches im Zusammenhang mit Spediteuren. |
| `actionObjectCarrierUpdateAfter` | Nachdem ein Spediteur aktualisiert wurde. | Aktualisiert möglicherweise interne Moduldaten oder Caches im Zusammenhang mit Spediteuren. |
| `actionObjectCarrierDeleteAfter` | Nachdem ein Spediteur gelöscht wurde. | Bereinigt alle Verweise auf den gelöschten Spediteur in Richtlinien. |
| `displayBackOfficeHeader` | Im Header aller Back-Office-Seiten. | Injiziert globale Admin-CSS/JS oder spezifische Skripte für die Admin-Seiten des Moduls. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Conditional Shipping Method Rules" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Fragen und Problemen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
