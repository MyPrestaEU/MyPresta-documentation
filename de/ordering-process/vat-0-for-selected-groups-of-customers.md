---
title: "0% Mehrwertsteuer für ausgewählte Kundengruppen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „0% Mehrwertsteuer für ausgewählte Kundengruppen“ von MyPresta.eu."
sidebar:
  label: "0% Mehrwertsteuer für ausgewählte Kundengruppen"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul VAT 0% for selected groups of customers auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/vat-0-for-selected-groups-of-customers.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/vat-0-for-selected-groups-of-customers/)
>
> ---


# 0% Mehrwertsteuer für ausgewählte Kundengruppen

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst und für die Update-Prüfungen des Moduls erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls „0% Mehrwertsteuer für ausgewählte Kundengruppen“. Diese Seite ist in mehrere Abschnitte unterteilt.

#### Registerkarte „Einstellungen“

Dies ist die primäre Registerkarte, auf der Sie definieren, welche Kundengruppen von 0% Mehrwertsteuer profitieren.

**1. Kundengruppen, die 0% Mehrwertsteuer erhalten**
- **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie ermöglicht es Ihnen, eine oder mehrere Kundengruppen aus Ihrem PrestaShop-Shop auszuwählen, die von der Mehrwertsteuer befreit werden.
- **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine oder mehrere Gruppen ausgewählt sind:* Jeder Kunde, der zu *mindestens einer* der ausgewählten Gruppen gehört, erhält alle Produktpreise, Versandkosten und Bestellsummen mit 0% Mehrwertsteuer berechnet.
    - *Wenn keine Gruppen ausgewählt sind:* Das Modul wendet keine Mehrwertsteuerbefreiungen an, und allen Kunden wird die Mehrwertsteuer gemäß Ihren Standard-PrestaShop-Steuerregeln berechnet.
- **Empfohlener Wert:** Wählen Sie alle Kundengruppen aus, die Sie von der Mehrwertsteuer befreien möchten (z.B. „Großhandelskunden“, „B2B-Kunden“).
- **Händlerszenario / Beispiel:** Sie betreiben einen B2B-Shop. Sie haben eine Kundengruppe namens „Großhandelskunden“, die alle umsatzsteuerregistrierte Unternehmen sind. Sie würden „Großhandelskunden“ aus dieser Liste auswählen. Wenn ein Kunde aus dieser Gruppe sich anmeldet, sieht er alle Preise ohne Mehrwertsteuer.

**2. Steuervorschrift auswählen**
- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, eine bestimmte Steuervorschrift festzulegen, die das Modul bei der Anwendung der 0% Mehrwertsteuer verwenden soll. Obwohl das Modul den Steuersatz auf 0% setzt, erfordert PrestaShop oft eine gültige Steuervorschrift, die mit der Berechnung verknüpft ist.
- **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine spezifische Steuervorschrift ausgewählt ist:* Das Modul versucht, diese Steuervorschrift, jedoch mit einem Satz von 0%, für die befreiten Kundengruppen zu verwenden. Dies kann nützlich sein, um die Kompatibilität mit anderen Modulen oder spezifischen Buchhaltungseinrichtungen sicherzustellen, die erwarten, dass immer eine Steuervorschrift vorhanden ist.
    - *Wenn „Keine“ oder keine spezifische Regel ausgewählt ist (Standardverhalten):* Das Modul übernimmt die 0%-Mehrwertsteueranwendung direkt, oft indem es den Steuersatz auf 0% überschreibt, ohne sich strikt an eine vordefinierte Steuervorschrift zu halten, was in der Regel ausreichend ist.
- **Empfohlener Wert:** Lassen Sie die Einstellung auf Standard, es sei denn, Sie stoßen auf spezifische Kompatibilitätsprobleme mit anderen Modulen oder haben eine sehr spezielle Buchhaltungsanforderung. Wenn Sie eine auswählen, wählen Sie eine generische 0%-Steuervorschrift, falls Sie eine haben, oder eine Standard-Steuervorschrift, die das Modul dann auf 0% überschreiben kann.
- **Händlerszenario / Beispiel:** Ihr Buchhalter verlangt, dass alle Transaktionen, auch die mit 0% Mehrwertsteuer, für Berichtszwecke mit einer spezifischen Steuervorschrift-ID verknüpft sind. Sie könnten eine Steuervorschrift „0% MwSt. (Befreit)“ in PrestaShop erstellen und hier auswählen.

#### Registerkarte „Hook-Reparatur“
Diese Registerkarte dient zur erweiterten Fehlerbehebung und zur Sicherstellung, dass die Hooks des Moduls korrekt registriert sind.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt bietet Tools zum erneuten Registrieren der Hooks des Moduls, falls diese nicht registriert oder beschädigt werden, was manchmal nach Theme-Änderungen, Modulkonflikten oder Datenbankproblemen passieren kann.
- **Auswirkung der Änderung dieser Einstellung:**
    - *Klicken auf „Hooks reparieren“:* Diese Aktion versucht, alle notwendigen Hooks, die das Modul für seine korrekte Funktion verwendet, erneut zu registrieren. Wenn das Modul nicht wie erwartet funktionierte (z.B. die Mehrwertsteuer wurde nicht entfernt), könnte dies das Problem lösen.
- **Empfohlener Wert:** Verwenden Sie dies nur, wenn Sie vermuten, dass das Modul nicht korrekt funktioniert (z.B. Mehrwertsteuer wird immer noch für befreite Gruppen berechnet) und nachdem Sie bestätigt haben, dass Ihre Haupteinstellungen korrekt sind.
- **Händlerszenario / Beispiel:** Sie haben gerade Ihr PrestaShop-Theme aktualisiert, und jetzt wird Ihren mehrwertsteuerbefreiten Kunden plötzlich Mehrwertsteuer berechnet. Sie haben Ihre Gruppeneinstellungen überprüft, und sie sind korrekt. Das Klicken auf „Hooks reparieren“ hier könnte das zugrunde liegende Problem beheben.

#### Registerkarte „Updates“
Diese Registerkarte bietet Informationen zu Modul-Updates.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt prüft auf verfügbare Updates für das Modul und liefert Informationen zu Ihrer aktuellen Version.
- **Auswirkung der Änderung dieser Einstellung:**
    - *Auf Updates prüfen:* Informiert Sie, ob eine neuere Version des Moduls verfügbar ist, sodass Sie Ihr Modul mit den neuesten Funktionen und Fehlerbehebungen auf dem neuesten Stand halten können.
- **Empfohlener Wert:** Überprüfen Sie diese Registerkarte regelmäßig, um sicherzustellen, dass Sie die neueste Version für optimale Leistung und Sicherheit verwenden.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihr Shop immer die stabilste und sicherste Software verwendet. Sie besuchen diese Registerkarte einmal im Monat, um zu sehen, ob es neue Updates für Ihre MyPresta.eu-Module gibt.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modul-Konfigurationsseite | **Kundengruppen, die 0% Mehrwertsteuer erhalten** | Relevante Gruppen auswählen (z.B. „Großhandelskunden“) | Definiert, welche Kundengruppen 0% Mehrwertsteuer auf alle Preise und Summen erhalten. |
| Modul-Konfigurationsseite | **Steuervorschrift auswählen** | Standard belassen (oder bei Bedarf für die Buchhaltung eine 0%-Steuervorschrift auswählen) | Verknüpft die 0%-Mehrwertsteuerberechnung mit einer spezifischen Steuervorschrift für Kompatibilität oder Berichterstattung. |
| Registerkarte „Hook-Reparatur“ | **Schaltfläche „Hooks reparieren“** | Nur zur Fehlerbehebung verwenden | Registriert Modul-Hooks neu, um Funktionsprobleme zu beheben (z.B. Mehrwertsteuer wird nicht entfernt). |
| Registerkarte „Updates“ | **Auf Updates prüfen** | Regelmäßig prüfen | Informiert über verfügbare Modul-Updates für neue Funktionen und Fehlerbehebungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Mehrwertsteuer wird immer noch berechnet, obwohl ich die Kundengruppe ausgewählt habe.**
A1:
*   **Gruppenzuweisung prüfen:** Stellen Sie sicher, dass der Kunde, mit dem Sie testen, tatsächlich einer der ausgewählten mehrwertsteuerbefreiten Gruppen zugewiesen ist. Melden Sie sich als Kunde an, gehen Sie zu seinen Kontodetails oder überprüfen Sie dies im Back Office unter `Kunden > Kunden`.
*   **Modulkonfiguration:** Überprüfen Sie nochmals, ob die richtigen Gruppen auf der Konfigurationsseite des Moduls (`Module > Modul-Manager > Konfigurieren` für „0% Mehrwertsteuer für ausgewählte Kundengruppen“) ausgewählt sind.
*   **Cache:** Leeren Sie Ihren PrestaShop-Cache (unter `Erweiterte Einstellungen > Leistung`) und Ihren Browser-Cache. Manchmal können alte Daten angezeigt werden.
*   **Hook-Reparatur:** Gehen Sie zur Registerkarte „Hook-Reparatur“ in der Modulkonfiguration und klicken Sie auf die Schaltfläche „Hooks reparieren“. Dies kann Probleme beheben, bei denen die Integrationspunkte des Moduls mit PrestaShop möglicherweise nicht registriert wurden.

**F2: Beeinflusst dieses Modul meine bestehenden Steuerregeln für nicht befreite Kunden?**
A2: Nein, dieses Modul ist so konzipiert, dass es *nur* 0% Mehrwertsteuer auf Kunden anwendet, die zu den von Ihnen ausgewählten spezifischen Gruppen gehören. Für alle anderen Kunden gelten Ihre Standard-PrestaShop-Steuerregeln und -Konfigurationen wie gewohnt.

**F3: Funktioniert dieses Modul auch für Versandkosten?**
A3: Ja, das Modul ist so konzipiert, dass es 0% Mehrwertsteuer auf alle Aspekte der Bestellung anwendet, einschließlich Produktpreise, Versandkosten und alle anderen steuerpflichtigen Elemente, was zu einem Gesamtbestellwert mit 0% Mehrwertsteuer für die ausgewählten Kundengruppen führt.

**F4: Ich habe ein benutzerdefiniertes Theme. Funktioniert dieses Modul damit?**
A4: Ja, dieses Modul funktioniert, indem es die Kernlogik der PrestaShop-Steuerberechnung über Hooks modifiziert, anstatt Front-Office-Templates direkt zu ändern. Daher sollte es mit den meisten benutzerdefinierten Themes ohne Probleme kompatibel sein. Wenn Sie Anzeigeprobleme feststellen (z.B. Preise werden nicht aktualisiert), handelt es sich wahrscheinlich um ein Caching-Problem oder einen Konflikt mit einem anderen Modul, das ebenfalls Steuerberechnungen stark modifiziert.

**F5: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A5: Wenn das Modul neue Textzeichenfolgen einführt (obwohl dieses Modul hauptsächlich im Hintergrund arbeitet), können Sie diese über die PrestaShop-Übersetzungsoberfläche übersetzen:
1.  Gehen Sie zu `International > Übersetzungen`.
2.  Wählen Sie „Übersetzungen installierter Module“.
3.  Wählen Sie Ihr Theme, die Sprache und dann „0% Mehrwertsteuer für ausgewählte Kundengruppen“ aus der Modulliste.
4.  Sie können dann alle übersetzbaren Zeichenfolgen ändern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul „0% Mehrwertsteuer für ausgewählte Kundengruppen“ nutzt das PrestaShop-Hook-System, um Steuerberechnungen in verschiedenen Phasen des Bestellprozesses abzufangen und zu modifizieren. Es verwendet hauptsächlich die Hooks `actionTaxManager` und `actionProductPriceCalculation`, um den Steuersatz für Kunden, die zu bestimmten Gruppen gehören, dynamisch auf 0% anzupassen. Es enthält auch eine benutzerdefinierte `TaxManager`-Klasse, um die Logik zur Steuerüberschreibung zu handhaben. Das Modul folgt einer Standard-PrestaShop-Modulstruktur mit einer Hauptmoduldatei, einer dedizierten Klasse für die Steuerverwaltung und Smarty-Templates für seine Back-Office-Konfiguration.

### 4.2 Controller (`controllers/`)
Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

-   **`groupvat/classes/GroupvatTaxManager.php`**
    *   **Klassenname:** `GroupvatTaxManager`
    *   **Elternklasse:** `TaxManager` (PrestaShops Kernklasse `TaxManager`)
    *   **Verantwortlichkeit:** Diese Klasse ist der Kern der Modulfunktionalität. Sie erweitert PrestaShops Standard-`TaxManager`, um dessen Verhalten zu überschreiben. Ihre primäre Methode, `getTaxCalculator()`, ist entscheidend. Wenn ein Kunde als zu einer mehrwertsteuerbefreiten Gruppe gehörend identifiziert wird, stellt diese Klasse sicher, dass der `TaxCalculator` einen Steuersatz von 0% zurückgibt, wodurch die Mehrwertsteuer effektiv von den Preisen entfernt wird. Sie enthält auch Logik, um zu überprüfen, ob der aktuelle Kunde in einer der konfigurierten befreiten Gruppen ist.
    *   **Schlüsselmethoden:**
        *   `getTaxCalculator(array $params)`: Überschreibt den Standard-Steuerrechner, um einen Steuersatz von 0% zurückzugeben, wenn der Kunde in einer befreiten Gruppe ist.
        *   `isCustomerInGroup(int $id_customer)`: Hilfsmethode, um festzustellen, ob eine gegebene Kunden-ID zu einer der konfigurierten mehrwertsteuerbefreiten Gruppen gehört.

-   **`groupvat/classes/index.php`**
    *   **Verantwortlichkeit:** Standardmäßig leere `index.php`-Datei, um die Verzeichnisauflistung zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)
Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)
Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling für die Back-Office-Konfiguration wird vom Standard-Admin-Theme von PrestaShop übernommen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`groupvat/views/templates/admin/configure.tpl`**
    *   **Geltungsbereich:** Back-Office-Admin-Konfiguration.
    *   **Zweck:** Dies ist das Haupttemplate für die Konfigurationsseite des Moduls, gerendert von `getContent()` in `groupvat.php`. Es enthält andere Templates für spezifische Abschnitte wie die Auswahl der Kundengruppe und die Hook-Reparatur. Es umschließt typischerweise das gesamte Konfigurationsformular.

-   **`groupvat/views/templates/admin/customerGroups.tpl`**
    *   **Geltungsbereich:** Back-Office-Admin-Konfiguration.
    *   **Zweck:** Dieses Template rendert den Abschnitt, in dem der Händler die Kundengruppen auswählt, die 0% Mehrwertsteuer erhalten. Es zeigt eine Liste der verfügbaren Kundengruppen mit Kontrollkästchen an.
    *   **Variablen:** Verwendet wahrscheinlich `$groups` (Array von Kundengruppen), `$selected_groups` (Array von IDs der aktuell ausgewählten Gruppen), `$tax_rules` (Array der verfügbaren Steuervorschriften), `$selected_tax_rule` (ID der aktuell ausgewählten Steuervorschrift).

-   **`groupvat/views/templates/admin/hooksRepair.tpl`**
    *   **Geltungsbereich:** Back-Office-Admin-Konfiguration.
    *   **Zweck:** Dieses Template rendert den Abschnitt „Hook-Reparatur“ und bietet eine Schaltfläche zum erneuten Registrieren der Hooks des Moduls.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
    *   Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`.
        *   `groupvat_groups`: Speichert eine durch Kommas getrennte Liste der für die Mehrwertsteuerbefreiung ausgewählten Kundengruppen-IDs.
        *   `groupvat_tax`: Speichert die ID der ausgewählten Steuervorschrift (falls vorhanden).
        *   `mypresta_updates`: Speichert Informationen zu Modul-Updates.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionDispatcher` | Bevor ein Controller versendet wird. | Wird verwendet, um das Versandverhalten potenziell zu überschreiben oder zu modifizieren, obwohl oft für die allgemeine Einrichtung verwendet. |
| `ActionDispatcher` | (Alias von `actionDispatcher`) | Wie oben. |
| `actionCartGetPackageShippingCost` | Bei der Berechnung der Versandkosten für ein Paket im Warenkorb. | Entscheidend, um sicherzustellen, dass die Versandkosten für befreite Gruppen ebenfalls mit 0% Mehrwertsteuer berechnet werden. |
| `displayTaxManager` | (Veraltet/weniger gebräuchlich) | Historisch zur Anzeige steuerbezogener Informationen verwendet. |
| `ActionGetProductPropertiesAfter` | Nachdem Produkteigenschaften abgerufen wurden. | Ermöglicht die Änderung von Produktdaten, einschließlich Preis und Steuer, vor der Anzeige. |
| `taxManager` | (Veraltet/weniger gebräuchlich) | Historisch zur Steuerverwaltung verwendet. |
| `ActionAuthentication` | Nachdem sich ein Kunde authentifiziert (anmeldet). | Kann verwendet werden, um Sitzungsvariablen festzulegen oder Aktionen basierend auf der Kundengruppe nach der Anmeldung durchzuführen. |
| `ActionTaxManager` | Wenn die Klasse `TaxManager` instanziiert oder ihre Methoden aufgerufen werden. | **Primärer Hook für dieses Modul.** Ermöglicht dem Modul, seinen benutzerdefinierten `GroupvatTaxManager` einzufügen oder die Steuerberechnungslogik zu modifizieren. |
| `ActionPresentCart` | Bevor der Warenkorb dem Benutzer präsentiert wird. | Ermöglicht die Änderung von Warenkorbdaten, einschließlich Preisen und Summen, vor dem Rendern. |
| `ActionProductPriceCalculation` | Während des Produktpreisberechnungsprozesses. | **Primärer Hook für dieses Modul.** Ermöglicht dem Modul, den auf Produktpreise angewendeten Steuersatz zu modifizieren. |
| `actionGetProductPropertiesAfter` | (Alias von `ActionGetProductPropertiesAfter`) | Wie oben. |
| `ActionFilterDeliveryOptionList` | Bevor die Liste der Lieferoptionen angezeigt wird. | Ermöglicht die Änderung von Lieferoptionen, was potenziell deren Preise (und somit die Steuer) beeinflusst. |

## 5. Offizieller Support & Updates
Für offiziellen Support, Updates und die neuesten Versionen des Moduls „0% Mehrwertsteuer für ausgewählte Kundengruppen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
