---
title: "Produktmerkmalsliste – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produktmerkmalsliste' von MyPresta.eu."
sidebar:
  label: "Produktmerkmalsliste – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product features list auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-features-list.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-features-list/)
>
> ---


# Produktmerkmalsliste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Produktmerkmalsliste)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager aufgerufen wird.

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, wo die Liste der Produktmerkmale visuell auf Ihren Produktlistenseiten (Kategorieseiten, Suchergebnisse usw.) angezeigt wird.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „displayProductListReviews“ eingestellt:* Die Merkmale erscheinen in der Nähe des Produktbewertungsbereichs auf der Produktliste. Dies ist oft ein guter Ort, um Social Proof mit wichtigen Produktattributen zu gruppieren.
  - *Wenn auf „displayProductDeliveryTime“ eingestellt:* Die Merkmale erscheinen in der Nähe der angezeigten Lieferzeitinformationen. Dies kann nützlich sein für Produkte, bei denen Merkmale eng mit Logistik oder Verfügbarkeit verbunden sind.
  - *Wenn auf „displayHeader“ eingestellt:* Diese Option ist für die visuelle Anzeige auf Produktlisten weniger üblich und könnte die Merkmale im Seitenkopf platzieren, was im Allgemeinen nicht der Ort ist, an dem Sie produktspezifische Merkmale anzeigen möchten. Es ist primär ein technischer Hook.
- **Empfohlener Wert:** „displayProductListReviews“ oder „displayProductDeliveryTime“. Wählen Sie die Option, die am besten in das Layout Ihres Themes integriert ist und bei der Sie das Gefühl haben, dass die Merkmale am sichtbarsten sind, ohne zu überladen.
- **Händlerszenario / Beispiel:** Wenn Ihr Theme Sternbewertungen und Bewertungszahlen prominent anzeigt, würde „displayProductListReviews“ die Merkmale direkt daneben platzieren und einen reichhaltigen Informationsblock schaffen. Wenn Ihre Produkte oft spezifische Lieferdetails haben (z. B. „Versand in 24h“), könnte die Platzierung von Merkmalen mit „displayProductDeliveryTime“ sinnvoll sein.

### 2.2 Dedizierter Admin-Bildschirm: Merkmalszuordnung (Back Office > Module > Produktmerkmalsliste > Konfigurieren > „Merkmalszuordnungen verwalten“ oder ähnlicher Link)

Dieser Bildschirm ist entscheidend, um zu definieren, *welche* Merkmale für *welche* Produkte und Kategorien erscheinen. Hier ordnen Sie spezifische Produktmerkmale Kategorien zu.

- **Bildschirmname & Menüposition:** Nach der Konfiguration des Hauptmoduls finden Sie in der Regel einen Link oder eine Schaltfläche auf der Konfigurationsseite des Moduls (oder einen neuen Menüpunkt unter „Katalog“), der zu „Merkmalszuordnungen verwalten“ oder „Produktmerkmalsliste“ führt. Der genaue Pfad kann je nach Ihrer PrestaShop-Version leicht variieren, wird aber von der Hauptkonfiguration des Moduls aus verlinkt sein.
- **Verfügbare Aktionen & Einstellungen:**
  - **Raster-/Verwaltungsansicht:** Sie sehen eine Tabelle mit Ihren vorhandenen Produktmerkmalen (dies sind die Standardmerkmale, die Sie unter **Katalog > Attribute & Merkmale > Merkmale** definieren).
  - **Bearbeiten-/Zuordnen-Schaltfläche:** Für jedes Merkmal gibt es eine Schaltfläche „Bearbeiten“ oder „Zuordnen“. Durch Klicken darauf wird ein Formular geöffnet, in dem Sie:
    - **Kategorien auswählen:** Wählen Sie eine oder mehrere Kategorien aus, für die dieses spezifische Merkmal auf Produktlisten angezeigt werden soll. Wenn Sie beispielsweise ein Merkmal „Material“ haben, könnten Sie es den Kategorien „T-Shirts“, „Kleider“ und „Jacken“ zuordnen.
    - **Aktivieren/Deaktivieren:** Sie haben möglicherweise die Option, die Anzeige dieses Merkmals auf Produktlisten global oder pro Kategorie zu aktivieren oder zu deaktivieren.
- **Auswirkungen von Änderungen:**
  - *Wenn Sie ein Merkmal einer Kategorie zuordnen:* Produkte innerhalb dieser Kategorie, die dieses Merkmal besitzen, zeigen es in ihrem Produktlisteneintrag an.
  - *Wenn Sie eine Zuordnung entfernen:* Das Merkmal wird für Produkte in dieser Kategorie nicht mehr auf Produktlisten angezeigt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Stellen Sie zunächst sicher, dass alle Ihre Produktmerkmale unter **Katalog > Attribute & Merkmale > Merkmale** korrekt eingerichtet sind.
  2. Navigieren Sie zum Bildschirm „Merkmalszuordnungen verwalten“ des Moduls „Produktmerkmalsliste“.
  3. Gehen Sie jedes relevante Merkmal durch.
  4. Wählen Sie für jedes Merkmal die Kategorien aus, in denen dieses Merkmal auf den Produktlistenseiten sichtbar sein soll.
  5. Speichern Sie Ihre Änderungen.
  6. Überprüfen Sie diese Zuordnungen regelmäßig, insbesondere wenn Sie neue Produkte, Kategorien oder Merkmale hinzufügen, um sicherzustellen, dass Ihre Produktlisten informativ bleiben.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Position der Tags (fplist\_position) | displayProductListReviews | Bestimmt, wo Merkmale auf Produktlistenseiten erscheinen (z. B. in der Nähe von Bewertungen, in der Nähe der Lieferzeit). |
| Merkmalszuordnung | Merkmalsname (z. B. „Material“) | N/A | Standard-PrestaShop-Merkmal, das verwaltet werden soll. |
| Merkmalszuordnung | Zugeordnete Kategorien | N/A | Wählen Sie Kategorien aus, in denen dieses Merkmal auf Produktlisten sichtbar sein soll. |
| Merkmalszuordnung | Merkmal aktivieren/deaktivieren | Aktiviert | Steuert, ob ein Merkmal für seine zugeordneten Kategorien aktiv angezeigt wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber die Merkmale werden auf meinen Kategorieseiten nicht angezeigt.**
A:

1. **Merkmalszuordnungen überprüfen:** Gehen Sie zum Bildschirm „Merkmalszuordnungen verwalten“ und stellen Sie sicher, dass die Merkmale, die Sie erwarten, tatsächlich den Kategorien zugeordnet sind, die Sie anzeigen.
2. **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“, falls verfügbar).
3. **Modulposition:** Überprüfen Sie die Einstellung „Position der Tags“ in der Hauptkonfiguration des Moduls. Stellen Sie sicher, dass sie auf einen Hook eingestellt ist, den Ihr Theme im Kontext der Produktliste tatsächlich rendert (z. B. `displayProductListReviews` oder `displayProductDeliveryTime`). Einige benutzerdefinierte Themes rufen möglicherweise nicht alle Standard-Hooks explizit auf.
4. **Produktdaten:** Überprüfen Sie, ob die betreffenden Produkte tatsächlich Werte für die Merkmale *haben*, die Sie anzeigen möchten (z. B. wenn Sie „Material“ anzeigen möchten, stellen Sie sicher, dass dem Produkt ein Material zugewiesen ist).

**F: Die Merkmale werden angezeigt, aber sie sehen unordentlich aus oder passen nicht zum Design meines Themes.**
A:

1. **CSS-Konflikt:** Dies ist wahrscheinlich ein Styling-Konflikt mit Ihrem Theme. Das Modul enthält sein eigenes CSS (`fplist/views/css/fplist.css`), aber die Stile Ihres Themes könnten es überschreiben oder Layoutprobleme verursachen.
2. **Benutzerdefiniertes Theme:** Wenn Sie ein stark angepasstes Theme verwenden, benötigen Sie möglicherweise einen Webmaster oder Entwickler, um das CSS des Moduls oder das CSS Ihres Themes anzupassen, um eine ordnungsgemäße Integration zu gewährleisten.
3. **Positionierung:** Versuchen Sie, die Einstellung „Position der Tags“ zu ändern, um zu sehen, ob ein anderer Hook visuell besser in Ihr Theme integriert ist.

**F: Kann ich verschiedene Merkmale für verschiedene Kategorien anzeigen?**
A: Ja, absolut! Dies ist eine der Kernstärken des Moduls. Verwenden Sie den Bildschirm „Merkmalszuordnungen verwalten“, um spezifische Kategorien für jedes Merkmal auszuwählen. Dies ermöglicht es Ihnen, die angezeigten Informationen präzise an den Kontext der Produktliste anzupassen.

**F: Beeinflusst dieses Modul meine Produktseiten?**
A: Nein, dieses Modul zielt speziell auf Produkt-*Listenseiten* (Kategorie, Suchergebnisse usw.) ab. Es ändert nicht, wie Merkmale auf einzelnen Produktdetailseiten angezeigt werden.

**F: Mein Shop ist mehrsprachig. Werden die Merkmalsnamen übersetzt?**
A: Ja, die Standard-PrestaShop-Merkmale (die dieses Modul verwendet) sind vollständig übersetzbar. Stellen Sie sicher, dass Sie Übersetzungen für Ihre Merkmalsnamen und -werte unter **Katalog > Attribute & Merkmale > Merkmale** für alle aktiven Sprachen in Ihrem Shop bereitgestellt haben. Das Modul zeigt dann die korrekte Übersetzung im Front Office an.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Produktmerkmalsliste“ (`fplist`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich `Module` für seine Kernfunktionalität und `AdminController` für seine Back-Office-Verwaltungsoberfläche erweitert. Es nutzt das Hook-System von PrestaShop, um Inhalte in Produktlistenseiten einzufügen, und verwendet ein `ObjectModel` (implizit über `AdminFplistAssociationController`), um die Zuordnung zwischen Merkmalen und Kategorien zu verwalten. Die Front-Office-Anzeige des Moduls wird durch ein Smarty-Template über einen Hook gerendert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine dedizierten Front-Office-Controller. Die gesamte Front-Office-Anzeigelogik wird direkt in der Hauptmoduldatei (`fplist.php`) über registrierte Hooks behandelt.
- **Back-Office-Admin-Controller**:

  - `fplist/controllers/admin/AdminFplistAssociation.php`
    - **Klassenname:** `AdminFplistAssociationController` (erweitert `ModuleAdminController`)
    - **Verantwortlichkeit:** Dieser Controller verwaltet die Zuordnung zwischen PrestaShop-Merkmalen und Kategorien. Er bietet die Back-Office-Oberfläche (eine Liste und möglicherweise ein Bearbeitungsformular) für Administratoren, um auszuwählen, welche Merkmale auf Produktlisten für bestimmte Kategorien angezeigt werden sollen. Er interagiert mit dem internen Datenspeicher des Moduls (wahrscheinlich die Tabelle `ps_fplist_association`, obwohl kein explizites `ObjectModel` im Dossier bereitgestellt wird, impliziert der Controller dessen Existenz und Verwaltung).
  - `fplist/controllers/admin/index.php`
    - **Klassenname:** N/A (dies ist typischerweise eine leere Datei oder eine Weiterleitung, um direkten Verzeichniszugriff zu verhindern, kein funktionaler Controller).
    - **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsmaßnahme zur Verhinderung von Verzeichnislisten.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Der `AdminFplistAssociationController` impliziert die Existenz eines Datenmodells für Merkmals-Kategorie-Zuordnungen, das wahrscheinlich direkt im Controller oder in der Hauptmoduldatei mithilfe von `Db::getInstance()`-Abfragen behandelt wird, anstatt eines dedizierten `ObjectModel`. Wenn ein `ObjectModel` vorhanden wäre, würde es typischerweise `FplistAssociation` oder ähnlich benannt sein.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien aus. Jedes dynamische Verhalten oder AJAX-Interaktionen müssten direkt in den PHP- oder Template-Dateien des Moduls implementiert werden oder auf das Kern-JS von PrestaShop zurückgreifen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `fplist/views/css/fplist.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet ist für die visuelle Darstellung der Produktmerkmalsliste auf Kategorie- und Listenseiten verantwortlich. Es definiert Stile für den Container, der die Merkmale enthält, einzelne Merkmalselemente und potenziell damit verbundene Symbole oder Beschriftungen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler sollten das gerenderte HTML inspizieren, um spezifische Klassen (z. B. `.fplist-container`, `.fplist-item`, `.fplist-feature-name`, `.fplist-feature-value`) zu identifizieren, die in der `custom.css` oder `theme.css` ihres Themes überschrieben werden können, um eine nahtlose Integration zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `fplist/views/templates/fplist-front.tpl`
    - **Hook:** Dieses Template wird innerhalb der Hooks `displayProductListReviews` und `displayProductDeliveryTime` gerendert (wie durch `fplist_position` konfiguriert).
    - **Ausgabe:** Es gibt die HTML-Struktur für die Merkmalsliste eines einzelnen Produkts auf einer Produktlistenseite aus. Es iteriert durch die vom Modul für das aktuelle Produkt und die Kategorie abgerufenen Merkmale und zeigt deren Namen und Werte an.
  - `fplist/views/templates/fplist.tpl`
    - **Hook:** Dieses Template wird wahrscheinlich für die Hauptkonfigurationsseite des Moduls im Back Office verwendet (über `getContent()`).
    - **Ausgabe:** Es rendert das Formular für die Einstellung „Position der Tags“ und möglicherweise Links zum `AdminFplistAssociationController` zur Verwaltung von Merkmalszuordnungen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_fplist_association` (impliziert): Diese Tabelle ist im Dossier nicht explizit definiert, aber für den `AdminFplistAssociationController` notwendig, um die Many-to-Many-Beziehung zwischen PrestaShop-Merkmalen und Kategorien zu speichern. Sie würde typischerweise Spalten wie `id_feature`, `id_category` und potenziell `id_shop` enthalten.
  - Konfigurationseinträge in `ps_configuration`:
    - `mypresta_updates`: Speichert Update-Informationen für MyPresta.eu-Module.
    - `update_`: Bezogen auf Modul-Update-Prüfungen.
    - `updatev_`: Bezogen auf Modul-Update-Prüfungen.
    - `fplist_position`: Speichert den ausgewählten Hook-Namen für die Anzeige von Merkmalen (z. B. `displayProductListReviews`).
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standard-PrestaShop-Konfiguration für die Mitarbeitersprachen im Formular.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Hauptsächlich zum Laden von CSS/JS-Assets oder Meta-Tags verwendet. Das Modul verwendet es als konfigurierbare Position für Merkmale, obwohl dies für die visuelle Anzeige weniger üblich ist. |
| `displayProductListReviews` | Innerhalb des Produktlisteneintrags, typischerweise in der Nähe von Produktbewertungen. | Fügt den HTML-Code der Merkmalsliste in jeden Produkteintrag auf Kategorie-/Suchseiten ein. |
| `displayProductDeliveryTime` | Innerhalb des Produktlisteneintrags, typischerweise in der Nähe von Lieferzeitinformationen. | Fügt den HTML-Code der Merkmalsliste in jeden Produkteintrag auf Kategorie-/Suchseiten ein. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | (Von diesem Modul nicht explizit verwendet, aber ein häufiger Hook für bestellbezogene Aktionen). |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Produktmerkmalsliste“ gerne zur Verfügung.
