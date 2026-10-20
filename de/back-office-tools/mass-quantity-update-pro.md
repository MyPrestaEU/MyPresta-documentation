---
title: "Massenmengen-Update Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Massenmengen-Update Pro“ von MyPresta.eu."
sidebar:
  label: "Massenmengen-Update Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Mass quantity update pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/mass-quantity-update-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/mass-quantity-update-pro/)
>
> ---


# Massenmengen-Update Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Massenmengen-Update Pro“ bietet einen einzigen, intuitiven Konfigurationsbildschirm im PrestaShop Back Office, auf dem Sie die zu aktualisierenden Produkte und die anzuwendenden Mengenänderungen definieren.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Konfiguration des Moduls zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Massenmengen-Update Pro“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

Die Konfigurationsseite ist in zwei Hauptabschnitte unterteilt: **Zielprodukte** und **Was tun?**.

#### 2.1.1 Zielprodukte

Dieser Abschnitt ermöglicht es Ihnen, zu definieren, *welche* Produkte oder Produktkombinationen von der Mengenaktualisierung betroffen sein werden. Sie können Produkte basierend auf verschiedenen Kriterien auswählen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt definiert den Umfang Ihrer Mengenaktualisierung. Sie wählen die spezifische Gruppe von Produkten aus, deren Mengen geändert werden sollen.
- **Auswirkung der Änderung dieser Einstellung:** Nur Produkte, die den ausgewählten Kriterien entsprechen, werden für die Mengenaktualisierung berücksichtigt. Wenn keine Kriterien ausgewählt sind, werden keine Produkte angesprochen.
- **Empfohlener Wert:** Wählen Sie ein oder mehrere Kriterien aus, die die Produkte, die Sie ändern möchten, präzise definieren.

**Verfügbare Kriterien:**

1. **Produkte aus Kategorien:**

   - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl einer oder mehrerer spezifischer Produktkategorien. Alle Produkte (und deren Kombinationen), die zu diesen Kategorien gehören, werden angesprochen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ausgewählt:* Produkte innerhalb der ausgewählten Kategorien werden eingeschlossen.
     - *Wenn nicht ausgewählt:* Produkte werden nicht nach Kategorie gefiltert.
   - **Empfohlener Wert:** Wählen Sie dies, wenn Sie den Lagerbestand für eine gesamte Produktlinie oder Abteilung aktualisieren müssen.
   - **Händlerszenario / Beispiel:** Sie haben eine neue Lieferung für alle Produkte in Ihrer Kategorie „Sommerkollektion“ erhalten. Sie können diese Kategorie auswählen, um deren Lagerbestand zu aktualisieren.
2. **Produkte nach Marke:**

   - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl einer oder mehrerer spezifischer Produktmarken (Hersteller). Alle Produkte (und deren Kombinationen), die mit diesen Marken verbunden sind, werden angesprochen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ausgewählt:* Produkte der ausgewählten Marken werden eingeschlossen.
     - *Wenn nicht ausgewählt:* Produkte werden nicht nach Marke gefiltert.
   - **Empfohlener Wert:** Wählen Sie dies, wenn Sie den Lagerbestand für Produkte eines bestimmten Lieferanten oder einer Marke aktualisieren müssen.
   - **Händlerszenario / Beispiel:** Ihr Lieferant „Fashionista Inc.“ hat neue Ware geliefert. Sie wählen „Fashionista Inc.“ aus, um alle deren Produkte zu aktualisieren.
3. **Produkte nach Merkmalen:**

   - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl von Produkten basierend auf ihren zugewiesenen Merkmalen (z. B. „Farbe: Rot“, „Material: Baumwolle“). Sie können ein Merkmal und dann spezifische Werte für dieses Merkmal auswählen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ausgewählt:* Nur Produkte, die das angegebene Merkmal und den Wert besitzen, werden eingeschlossen.
     - *Wenn nicht ausgewählt:* Produkte werden nicht nach Merkmalen gefiltert.
   - **Empfohlener Wert:** Nützlich für sehr spezifische Aktualisierungen basierend auf Produkteigenschaften.
   - **Händlerszenario / Beispiel:** Sie möchten den Lagerbestand für alle T-Shirts aus „Bio-Baumwolle“ aktualisieren. Sie wählen „Material“ als Merkmal und „Bio-Baumwolle“ als Wert aus.
4. **Produkte nach Attributen:**

   - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl von Produkten basierend auf ihren Attributen (z. B. „Größe: M“, „Farbe: Blau“). Dies ist besonders nützlich für Produktkombinationen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ausgewählt:* Nur Produktkombinationen mit dem angegebenen Attribut und Wert werden eingeschlossen.
     - *Wenn nicht ausgewählt:* Produkte werden nicht nach Attributen gefiltert.
   - **Empfohlener Wert:** Wesentlich für die Bestandsverwaltung spezifischer Produktvarianten.
   - **Händlerszenario / Beispiel:** Sie haben eine neue Lieferung von T-Shirts der „Größe L“ erhalten. Sie wählen „Größe“ als Attribut und „L“ als Wert aus, um nur diese Kombinationen zu aktualisieren.
5. **Produkte nach Steuerregelzuordnungen:**

   - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl von Produkten basierend auf der auf sie angewendeten Steuerregelgruppe.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ausgewählt:* Nur Produkte, die mit der ausgewählten Steuerregelgruppe verbunden sind, werden eingeschlossen.
     - *Wenn nicht ausgewählt:* Produkte werden nicht nach Steuerregel gefiltert.
   - **Empfohlener Wert:** Nützlich für Shops mit komplexen Steuerstrukturen oder wenn Bestandsaktualisierungen an steuerbezogene Bestände gebunden sind.
   - **Händlerszenario / Beispiel:** Sie müssen den Lagerbestand für alle Produkte anpassen, die einer bestimmten Steuerregel „Einfuhrzoll“ unterliegen.
6. **Spezifische Produkte:**

   - **Was diese Einstellung bewirkt:** Bietet ein Autocomplete-Suchfeld, um einzelne Produkte manuell nach Namen auszuwählen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn Produkte hinzugefügt werden:* Nur die explizit ausgewählten Produkte (und deren Kombinationen) werden angesprochen.
     - *Wenn leer:* Auf diese Weise werden keine spezifischen Produkte angesprochen.
   - **Empfohlener Wert:** Verwenden Sie dies für sehr präzise Aktualisierungen einer kleinen, handverlesenen Auswahl von Produkten.
   - **Händlerszenario / Beispiel:** Sie müssen den Lagerbestand für „Produkt A“, „Produkt B“ und „Produkt C“ aktualisieren, die nicht durch Kategorie oder Marke miteinander verbunden sind.

#### 2.1.2 Was tun?

Dieser Abschnitt definiert, *wie* die Mengen der Zielprodukte geändert werden.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt gibt die Art der Mengenänderung (erhöhen, verringern oder auf einen festen Wert setzen) und den Betrag der Änderung an.
- **Auswirkung der Änderung dieser Einstellung:** Die ausgewählte Operation wird auf die Mengen aller Produkte angewendet, die im Abschnitt „Zielprodukte“ definiert sind.
- **Empfohlener Wert:** Wählen Sie die Operation, die Ihre Bestandsanpassung genau widerspiegelt.

**Verfügbare Operationen:**

1. **Menge erhöhen um:**

   - **Was diese Einstellung bewirkt:** Fügt eine angegebene Zahl zur aktuellen Menge jedes Zielprodukts/jeder Zielkombination hinzu.
   - **Auswirkung der Änderung dieser Einstellung:** Der Lagerbestand für jeden Zielartikel erhöht sich um den eingegebenen Betrag.
   - **Empfohlener Wert:** Verwenden Sie dies, wenn neue Ware eintrifft. Geben Sie eine positive ganze Zahl ein (z. B. `10`).
   - **Händlerszenario / Beispiel:** Sie haben 50 Einheiten eines Produkts erhalten. Sie wählen „Menge erhöhen um“ und geben `50` ein.
2. **Menge verringern um:**

   - **Was diese Einstellung bewirkt:** Zieht eine angegebene Zahl von der aktuellen Menge jedes Zielprodukts/jeder Zielkombination ab.
   - **Auswirkung der Änderung dieser Einstellung:** Der Lagerbestand für jeden Zielartikel verringert sich um den eingegebenen Betrag.
   - **Empfohlener Wert:** Verwenden Sie dies, wenn der Lagerbestand aufgrund von Beschädigungen, Rücksendungen oder internem Verbrauch reduziert werden muss. Geben Sie eine positive ganze Zahl ein (z. B. `5`).
   - **Händlerszenario / Beispiel:** 5 Artikel wurden im Lager beschädigt. Sie wählen „Menge verringern um“ und geben `5` ein.
3. **Menge festlegen auf:**

   - **Was diese Einstellung bewirkt:** Ändert die aktuelle Menge jedes Zielprodukts/jeder Zielkombination auf eine spezifische, feste Zahl.
   - **Auswirkung der Änderung dieser Einstellung:** Der Lagerbestand für jeden Zielartikel wird genau der eingegebene Betrag, unabhängig von seiner vorherigen Menge.
   - **Empfohlener Wert:** Verwenden Sie dies, wenn Sie den Lagerbestand mit einem externen System synchronisieren oder eine absolute Bestandszählung korrigieren müssen. Geben Sie eine nicht-negative ganze Zahl ein (z. B. `100`).
   - **Händlerszenario / Beispiel:** Nach einer vollständigen Inventur wissen Sie, dass Sie genau 100 Einheiten eines Produkts haben. Sie wählen „Menge festlegen auf“ und geben `100` ein.

**Wichtiger Hinweis:** Nachdem Sie sowohl „Zielprodukte“ als auch „Was tun?“ definiert haben, müssen Sie auf die Schaltfläche **„Mengen aktualisieren“** klicken, um die Änderungen anzuwenden. Es gibt keine „Rückgängig“-Schaltfläche, überprüfen Sie daher immer Ihre Auswahl, bevor Sie bestätigen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Zielprodukte** | | Definiert, welche Produkte/Kombinationen betroffen sein werden. |
| | Produkte aus Kategorien | Nach Bedarf auswählen | Zielt auf alle Produkte innerhalb der ausgewählten Kategorien ab. |
| | Produkte nach Marke | Nach Bedarf auswählen | Zielt auf alle Produkte der ausgewählten Marken ab. |
| | Produkte nach Merkmalen | Nach Bedarf auswählen | Zielt auf Produkte mit spezifischen Merkmalen/Werten ab. |
| | Produkte nach Attributen | Nach Bedarf auswählen | Zielt auf Produktkombinationen mit spezifischen Attributen/Werten ab. |
| | Produkte nach Steuerregelzuordnungen | Nach Bedarf auswählen | Zielt auf Produkte ab, die mit ausgewählten Steuerregeln verbunden sind. |
| | Spezifische Produkte | Nach Bedarf auswählen | Zielt auf individuell ausgewählte Produkte ab. |
| | **Was tun?** | | Definiert, wie Mengen geändert werden. |
| | Menge erhöhen um | Positive ganze Zahl eingeben | Fügt den angegebenen Betrag zum aktuellen Lagerbestand hinzu. |
| | Menge verringern um | Positive ganze Zahl eingeben | Zieht den angegebenen Betrag vom aktuellen Lagerbestand ab. |
| | Menge festlegen auf | Nicht-negative ganze Zahl eingeben | Setzt den Lagerbestand auf einen exakten, angegebenen Betrag. |
| | **Schaltfläche Mengen aktualisieren** | Klicken zum Anwenden | Führt die definierten Mengenänderungen aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Mengen aktualisiert, aber mein Shop zeigt immer noch die alten Zahlen an. Was ist falsch?**
**A1:** Dies ist normalerweise ein Caching-Problem. PrestaShop verwendet Caching, um Ihren Shop zu beschleunigen.

- **Lösung:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Performance**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ / „Cache leeren“, je nach Ihrer PrestaShop-Version). Dies sollte Ihren Shop dazu zwingen, die aktualisierten Mengen anzuzeigen.

**F2: Ich habe einen Fehler gemacht und die falschen Produkte/Mengen aktualisiert. Kann ich das rückgängig machen?**
**A2:** Das Modul hat keine „Rückgängig“-Schaltfläche. Deshalb ist es wichtig, Ihre Auswahl vor dem Klicken auf „Mengen aktualisieren“ doppelt zu überprüfen.

- **Lösung:** Wenn Sie ein aktuelles Backup Ihrer Datenbank haben, können Sie es wiederherstellen (obwohl dies andere kürzliche Änderungen rückgängig machen könnte). Andernfalls müssen Sie die Mengen für die betroffenen Produkte manuell korrigieren oder das Modul erneut mit den richtigen Einstellungen verwenden, um sie neu anzupassen. Wenn Sie beispielsweise versehentlich um 10 erhöht haben, können Sie um 10 verringern.

**F3: Das Modul findet keine Produkte, wenn ich im Suchfeld „Spezifische Produkte“ tippe.**
**A3:** Stellen Sie sicher, dass Sie den vollständigen oder teilweisen Namen eines vorhandenen Produkts in Ihrem Shop eingeben. Die Autocomplete-Funktion basiert auf JavaScript.

- **Lösung:**
  1. Überprüfen Sie die Konsole Ihres Browsers auf JavaScript-Fehler (F12-Taste, dann Registerkarte „Konsole“).
  2. Versuchen Sie, den Cache Ihres Browsers zu leeren.
  3. Stellen Sie sicher, dass Ihr PrestaShop-Shop auf einer kompatiblen PHP-Version läuft (siehe Abschnitt 3).
  4. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F4: Kann ich Mengen für Produkte mit Kombinationen (Attributen) aktualisieren?**
**A4:** Ja, absolut! Das Modul ist für die Handhabung von Produktkombinationen ausgelegt. Wenn Sie Produkte nach Kategorie, Marke, Merkmal oder spezifischem Produkt auswählen, wird die Mengenänderung auf alle zugehörigen Kombinationen dieser Produkte angewendet. Wenn Sie „Produkte nach Attributen“ verwenden, können Sie sogar bestimmte Kombinationen direkt ansprechen.

**F5: Das Modul scheint langsam zu sein, wenn eine sehr große Anzahl von Produkten aktualisiert wird.**
**A5:** Das Aktualisieren von Tausenden von Produkten kann ressourcenintensiv sein.

- **Lösung:**
  1. Stellen Sie sicher, dass Ihr Server die empfohlenen Spezifikationen von PrestaShop erfüllt.
  2. Erhöhen Sie die PHP-Ausführungszeitlimits (`max_execution_time`) und Speicherlimits (`memory_limit`) in Ihrer `php.ini`-Datei (wenden Sie sich an Ihren Hosting-Anbieter oder Webmaster).
  3. Teilen Sie sehr große Updates, wenn möglich, in kleinere Chargen auf (z. B. aktualisieren Sie eine Kategorie nach der anderen anstatt alle Kategorien).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Massenmengen-Update Pro“ arbeiten.

### 4.1 Architekturübersicht

Das Modul `MassQtyPro` folgt einer Standard-PrestaShop-Modularchitektur, wobei es hauptsächlich die `Module`-Klasse für seine Kernfunktionalität und die `getContent()`-Methode für seine einzelne Back-Office-Konfigurationsoberfläche nutzt. Es integriert ein benutzerdefiniertes Suchwerkzeug für die Produktauswahl, das AJAX für die Autocomplete-Funktionalität verwendet. Das Modul interagiert direkt mit den PrestaShop-Klassen `Product` und `StockAvailable`, um Mengenaktualisierungen durchzuführen.

### 4.2 Controller (`controllers/`)

Das Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfigurations- und Verarbeitungslogik für das Back-Office wird innerhalb der `getContent()`-Methode der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Klassen innerhalb eines `classes/`-Verzeichnisses. Die gesamte Kernlogik befindet sich in der Hauptdatei `massqtypro.php`.

### 4.4 JavaScript-Assets (`views/js/`)

- **`massqtypro/lib/searchTool/views/js/autocomplete.js`**
  - **Umfang:** Back-Office (wird auf der Modulkonfigurationsseite verwendet).
  - **Beschreibung:** Dieses Skript implementiert oder integriert wahrscheinlich eine generische Autocomplete-Funktionalität. Es überwacht Benutzereingaben in Textfeldern (insbesondere für die Produktsuche) und sendet AJAX-Anfragen, um passende Produktnamen abzurufen. Anschließend werden diese Vorschläge in einer Dropdown-Liste angezeigt, sodass der Benutzer Produkte auswählen kann. Es verwaltet die Anzeige und Auswahl von Autocomplete-Ergebnissen.
- **`massqtypro/views/js/jquery.autocomplete.js`**
  - **Umfang:** Back-Office (wird auf der Modulkonfigurationsseite verwendet).
  - **Beschreibung:** Dies scheint ein jQuery-Plugin für die Autocomplete-Funktionalität zu sein. Es bietet das Kernframework für das Produktsuchfeld auf der Konfigurationsseite des Moduls. Es verarbeitet die AJAX-Aufrufe an den Server (wahrscheinlich an die `getContent()`-Methode oder einen spezifischen Hook, der Produktdaten bereitstellt), verarbeitet die JSON-Antwort und rendert die Vorschläge. Es verwaltet auch die Auswahl eines Elements aus der Liste und das Füllen des Eingabefeldes oder eines versteckten Feldes mit der ID des ausgewählten Produkts.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`massqtypro/lib/searchTool/views/css/autocomplete.css`**
  - **Umfang:** Back-Office (Styling für die Modulkonfigurationsseite).
  - **Beschreibung:** Dieses Stylesheet bietet die visuelle Darstellung für das Autocomplete-Suchfeld und seine Vorschlagsliste. Es definiert Stile für das Eingabefeld, den Dropdown-Container, einzelne Vorschlagselemente und potenziell Hover-/Active-Zustände für eine bessere Benutzerinteraktion. Entwickler können diese Stile in ihrem benutzerdefinierten Admin-Theme überschreiben oder spezifische CSS-Regeln hinzufügen, um die Elemente des Moduls anzusprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates zur Darstellung seines Back-Office-Konfigurationsformulars.

- **`massqtypro/lib/searchTool/views/scripts.tpl`**
  - **Umfang:** Back-Office (in der Modulkonfigurationsseite enthalten).
  - **Beschreibung:** Dieses Template enthält wahrscheinlich die notwendigen JavaScript- und CSS-Dateien für das Autocomplete-Suchwerkzeug. Es könnte auch Inline-JavaScript zur Initialisierung des Autocomplete-Plugins auf bestimmten Eingabefeldern, zur Übergabe von Konfigurationsoptionen und zur Definition von Callback-Funktionen für die Produktauswahl enthalten.
- **`massqtypro/views/templates/admin/target_products.tpl`**
  - **Umfang:** Back-Office (Teil des Modulkonfigurationsformulars).
  - **Beschreibung:** Dieses Template rendert den Abschnitt „Zielprodukte“ der Konfigurationsseite des Moduls. Es enthält den HTML-Code für alle Produktauswahlkriterien: Kategorie-Dropdowns, Marken-Dropdowns, Merkmal-/Attribut-Selektoren, Steuerregel-Selektoren und das Autocomplete-Eingabefeld für spezifische Produkte. Es verwendet Standard-PrestaShop-Formularhelfer und möglicherweise benutzerdefinierten HTML-Code für die dynamischen Auswahllemente.
- **`massqtypro/views/templates/admin/wtd.tpl`**
  - **Umfang:** Back-Office (Teil des Modulkonfigurationsformulars).
  - **Beschreibung:** Dieses Template rendert den Abschnitt „Was tun?“ der Konfigurationsseite des Moduls. Es enthält den HTML-Code für die Mengenaktualisierungsoperationen: Radio-Buttons für „Erhöhen“, „Verringern“ oder „Festlegen auf“ und das entsprechende Eingabefeld für den Mengenwert. Es enthält auch die Schaltfläche „Mengen aktualisieren“.
- **`massqtypro/views/templates/hook/form.tpl`**
  - **Umfang:** Back-Office (Hauptkonfigurationsformular).
  - **Beschreibung:** Dies ist das Haupttemplate für die Konfigurationsseite des Moduls. Es umschließt wahrscheinlich die Templates `target_products.tpl` und `wtd.tpl` und kombiniert sie zu einem vollständigen Konfigurationsformular. Es würde auch die gesamte Formularübermittlung und die Anzeige von Erfolgs- oder Fehlermeldungen verwalten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es interagiert hauptsächlich mit vorhandenen PrestaShop-Tabellen, insbesondere `ps_product`, `ps_product_attribute`, `ps_stock_available`, `ps_category_product`, `ps_manufacturer`, `ps_feature_product`, `ps_product_attribute_combination` und `ps_tax_rule_group_product`. Konfigurationseinstellungen werden in `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Die primäre Funktionalität des Moduls wird über seine `getContent()`-Methode im Back-Office ausgeführt. Es registriert sich nicht explizit für Front-Office-Hooks zu Anzeigezwecken. Das Modul könnte jedoch intern Hooks für administrative Aktionen oder Datenabrufe verwenden.

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt des Back Office gerendert. | Potenziell zum Laden modulspezifischer CSS/JS für die Konfigurationsseite verwendet, obwohl dies oft direkt in `getContent()` behandelt wird. |
  | `actionProductUpdate` | Nach der Aktualisierung eines Produkts. | Könnte für interne Protokollierung oder zum Auslösen verwandter Aktionen verwendet werden, obwohl nicht explizit in den Funktionen angegeben. |
  | `actionUpdateQuantity` | Nach der Aktualisierung der Menge eines Produkts. | Könnte für interne Protokollierung oder zum Auslösen verwandter Aktionen verwendet werden, obwohl nicht explizit in den Funktionen angegeben. |

  Die Kernlogik des Moduls für Mengenaktualisierungen manipuliert direkt `StockAvailable`-Einträge, was intern die PrestaShop-Bestandsaktualisierungsmechanismen auslöst.

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen technischen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen zum Modul „Massenmengen-Update Pro“ zur Verfügung.
