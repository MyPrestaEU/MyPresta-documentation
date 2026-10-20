---
title: "Massenänderung des Produkttyps – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Massenänderung des Produkttyps' von MyPresta.eu."
sidebar:
  label: "Massenänderung des Produkttyps – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Mass change product type auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/mass-change-product-type.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/mass-change-product-type/)
>
> ---


# Massenänderung des Produkttyps

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Massenänderung des Produkttyps“ bietet einen einzigen, intuitiven Konfigurationsbildschirm in Ihrem PrestaShop Back Office. Dieser Bildschirm führt Sie durch die Auswahl der Produkte und die anschließende Anwendung der gewünschten Produkttypänderung.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Konfiguration des Moduls zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Massenänderung des Produkttyps“ und klicken Sie auf **„Konfigurieren“**.

Die Konfigurationsseite ist in zwei Hauptabschnitte unterteilt: **1. Produkte auswählen** und **2. Was mit ausgewählten Produkten zu tun ist**.

#### Abschnitt 1: Produkte auswählen

Dieser Abschnitt ermöglicht es Ihnen, zu definieren, welche Produkte von der Massenänderung betroffen sein werden. Sie können Produkte basierend auf verschiedenen Kriterien auswählen.

##### 1.1 Produkte nach Kategorie auswählen

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, alle Produkte auszuwählen, die zu einer oder mehreren spezifischen Kategorien gehören.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn Kategorien ausgewählt sind:* Nur Produkte innerhalb der ausgewählten Kategorien werden für die Typänderung berücksichtigt.
  - *Wenn keine Kategorien ausgewählt sind:* Dieses Kriterium wird nicht zum Filtern von Produkten verwendet.
- **Empfohlener Wert:** Wählen Sie die Kategorien aus, die für Ihren Massenänderungsvorgang relevant sind.
- **Händlerszenario / Beispiel:** Sie möchten alle Produkte in Ihrer Kategorie „Digitale Downloads“ von Standardprodukten in virtuelle Produkte umwandeln. Sie würden hier die Kategorie „Digitale Downloads“ auswählen.

##### 1.2 Produkte nach Marke auswählen

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, alle Produkte auszuwählen, die mit einer oder mehreren spezifischen Marken (Herstellern) verbunden sind.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn Marken ausgewählt sind:* Nur Produkte der ausgewählten Marken werden für die Typänderung berücksichtigt.
  - *Wenn keine Marken ausgewählt sind:* Dieses Kriterium wird nicht zum Filtern von Produkten verwendet.
- **Empfohlener Wert:** Wählen Sie die Marken aus, die für Ihren Massenänderungsvorgang relevant sind.
- **Händlerszenario / Beispiel:** Sie haben beschlossen, alle Produkte von „Marke X“ als Pakete zu verkaufen. Sie würden hier „Marke X“ auswählen.

##### 1.3 Produkte nach Merkmal auswählen

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte auszuwählen, die ein bestimmtes Merkmal und optional einen bestimmten Wert für dieses Merkmal aufweisen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Merkmal (und optional ein Wert) ausgewählt ist:* Nur Produkte, die diesem Merkmal-Kriterium entsprechen, werden berücksichtigt.
  - *Wenn kein Merkmal ausgewählt ist:* Dieses Kriterium wird nicht zum Filtern von Produkten verwendet.
- **Empfohlener Wert:** Wählen Sie das Merkmal und den Wert, die die Produkte, die Sie ändern möchten, präzise identifizieren.
- **Händlerszenario / Beispiel:** Sie möchten alle Produkte mit dem Merkmal „Material“ auf „Digital“ in virtuelle Produkte ändern. Sie würden hier „Material“ und dann „Digital“ auswählen.

##### 1.4 Produkte nach Attribut auswählen

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte auszuwählen, die ein bestimmtes Attribut und optional einen bestimmten Wert für dieses Attribut aufweisen. Dies ist nützlich für Produkte mit Kombinationen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Attribut (und optional ein Wert) ausgewählt ist:* Nur Produkte, die diesem Attribut-Kriterium entsprechen, werden berücksichtigt.
  - *Wenn kein Attribut ausgewählt ist:* Dieses Kriterium wird nicht zum Filtern von Produkten verwendet.
- **Empfohlener Wert:** Wählen Sie das Attribut und den Wert, die die Produkte, die Sie ändern möchten, präzise identifizieren.
- **Händlerszenario / Beispiel:** Sie möchten alle Produkte, die das Attribut „Größe“ auf „Herunterladbar“ gesetzt haben, in virtuelle Produkte umwandeln. Sie würden hier „Größe“ und dann „Herunterladbar“ auswählen.

##### 1.5 Produkte nach Suchbegriff auswählen

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte auszuwählen, deren Namen einen bestimmten Suchbegriff enthalten. Hierfür wird ein Suchwerkzeug verwendet, um Produkte zu finden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Suchbegriff eingegeben wird:* Produkte, deren Namen dem Suchbegriff entsprechen, werden zur Auswahl hinzugefügt.
  - *Wenn kein Suchbegriff eingegeben wird:* Dieses Kriterium wird nicht zum Filtern von Produkten verwendet.
- **Empfohlener Wert:** Geben Sie einen klaren und prägnanten Suchbegriff ein, um Ihre Zielprodukte zu identifizieren.
- **Händlerszenario / Beispiel:** Sie möchten alle Produkte mit „eBook“ im Namen in virtuelle Produkte ändern. Sie würden „eBook“ in das Suchfeld eingeben.

##### 1.6 Liste der ausgewählten Produkte

- **Was diese Einstellung bewirkt:** Nach dem Anwenden der oben genannten Filter wird in diesem Bereich eine Liste der Produkte angezeigt, die Ihren Kriterien entsprechen. Sie können Produkte manuell aus dieser Liste entfernen, wenn Sie nicht möchten, dass sie betroffen sind.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Entfernen eines Produkts:* Dieses spezifische Produkt wird von der Massentypänderung ausgeschlossen.
  - *Produkte in der Liste belassen:* Sie werden in die Massentypänderung einbezogen.
- **Empfohlener Wert:** Überprüfen Sie diese Liste immer sorgfältig, um sicherzustellen, dass nur die beabsichtigten Produkte ausgewählt sind.
- **Händlerszenario / Beispiel:** Sie haben nach „eBook“ gesucht, aber ein physisches Buch mit dem Titel „eBook Reader Handbuch“ ist erschienen. Sie würden dieses spezifische Produkt aus der Liste entfernen.

#### Abschnitt 2: Was mit ausgewählten Produkten zu tun ist

Sobald Sie Ihre Zielprodukte ausgewählt haben, können Sie in diesem Abschnitt den neuen Produkttyp auswählen, den Sie anwenden möchten.

##### 2.1 Produkttyp ändern in:

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü ermöglicht es Ihnen, den neuen Produkttyp für alle in Abschnitt 1 identifizierten Produkte auszuwählen.
- **Optionen:**
  - **Standardprodukt:** Ein reguläres physisches Produkt.
  - **Produktpaket:** Ein Bündel anderer Produkte.
  - **Produkt mit Kombinationen:** Ein Produkt mit Variationen (z. B. Größe, Farbe).
  - **Virtuelles Produkt:** Ein nicht-physisches Produkt (z. B. Dienstleistung, Download).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auswählen einer Option:* Alle ausgewählten Produkte werden in diesen neuen Typ umgewandelt.
- **Empfohlener Wert:** Wählen Sie den Produkttyp, der die neue Natur Ihrer ausgewählten Produkte genau widerspiegelt.
- **Händlerszenario / Beispiel:** Sie haben alle „eBook“-Produkte ausgewählt. Sie würden hier „Virtuelles Produkt“ wählen.

##### 2.2 Änderungen anwenden Schaltfläche

- **Was diese Einstellung bewirkt:** Diese Schaltfläche führt den Massenänderungsvorgang aus.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Klicken auf die Schaltfläche:* Das Modul verarbeitet alle Produkte in der „Liste der ausgewählten Produkte“ und ändert deren Produkttyp in den unter „Produkttyp ändern in:“ gewählten Typ. Eine Bestätigungsmeldung wird normalerweise angezeigt.
- **Empfohlener Wert:** Klicken Sie dies nur, wenn Sie absolut sicher sind bezüglich Ihrer Produktauswahl und des gewünschten neuen Typs.
- **Händlerszenario / Beispiel:** Nachdem Sie Ihre ausgewählten eBooks überprüft und „Virtuelles Produkt“ als neuen Typ bestätigt haben, klicken Sie auf „Änderungen anwenden“, um sie alle umzuwandeln.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Produkte nach Kategorie auswählen** | Relevante Kategorien auswählen | Filtert Produkte nach ihren zugewiesenen Kategorien. |
| Modulkonfiguration | **Produkte nach Marke auswählen** | Relevante Marken auswählen | Filtert Produkte nach ihrem Hersteller/ihrer Marke. |
| Modulkonfiguration | **Produkte nach Merkmal auswählen** | Merkmal & Wert auswählen | Filtert Produkte nach spezifischen Merkmalen und deren Werten. |
| Modulkonfiguration | **Produkte nach Attribut auswählen** | Attribut & Wert auswählen | Filtert Produkte nach spezifischen Attributen und deren Werten (für Kombinationen). |
| Modulkonfiguration | **Produkte nach Suchbegriff auswählen** | Suchbegriff eingeben | Filtert Produkte nach Schlüsselwörtern in ihrem Namen. |
| Modulkonfiguration | **Liste der ausgewählten Produkte** | Sorgfältig überprüfen | Zeigt ausgewählte Produkte an; ermöglicht manuelle Entfernung vor der Verarbeitung. |
| Modulkonfiguration | **Produkttyp ändern in:** | Gewünschten Typ auswählen | Legt den neuen Produkttyp (Standard, Paket, Kombinationen, Virtuell) für alle ausgewählten Produkte fest. |
| Modulkonfiguration | **Änderungen anwenden Schaltfläche** | Klicken zum Ausführen | Startet die Massenänderung des Produkttyps für alle ausgewählten Produkte. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe Produkttypen geändert, aber ich sehe die Änderungen nicht im Front Office meines Shops.**
A: Nach Änderungen im Back Office leeren Sie immer Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Der Cache Ihres Browsers muss möglicherweise ebenfalls geleert werden (Strg+F5 oder Cmd+R).

**F: Einige Produkte wurden nicht geändert, obwohl sie in meiner Auswahl waren.**
A:

1. **Überprüfen Sie die „Liste der ausgewählten Produkte“ erneut:** Haben Sie sie versehentlich aus der Liste entfernt, bevor Sie die Änderungen angewendet haben?
2. **Kriterien überprüfen:** Überprüfen Sie Ihre Auswahlkriterien (Kategorie, Marke, Merkmal, Attribut, Suchbegriff). Stimmen die Produkte wirklich mit allen ausgewählten Filtern überein?
3. **Produktstatus:** Stellen Sie sicher, dass die Produkte aktiv und nicht deaktiviert sind.
4. **Fehler:** Überprüfen Sie, ob Fehlermeldungen während des Prozesses „Änderungen anwenden“ aufgetreten sind.

**F: Kann ich die von diesem Modul vorgenommenen Änderungen rückgängig machen?**
A: Dieses Modul führt direkte Datenbankaktualisierungen durch. Es gibt keine „Rückgängig“-Schaltfläche innerhalb des Moduls selbst. Deshalb ist ein **Datenbank-Backup vor der Verwendung entscheidend**. Wenn Sie Änderungen rückgängig machen müssen, würden Sie normalerweise Ihre Datenbank aus einem Backup wiederherstellen, das *vor* der Verwendung des Moduls erstellt wurde. Alternativ müssten Sie das Modul erneut verwenden, um die Produkttypen in ihren ursprünglichen Zustand zurückzuändern, oder sie manuell bearbeiten.

**F: Beeinflusst dieses Modul die SEO oder URLs meiner Produkte?**
A: Die Änderung des Produkttyps selbst ändert nicht direkt die SEO-freundliche URL. Wenn jedoch die Änderung des Typs zu anderen Modifikationen führt (z. B. Entfernen von Kombinationen, Ändern der Produktstruktur), ist es immer eine gute Idee, Ihre Produktseiten zu überprüfen und gegebenenfalls URLs neu zu generieren (Abschnitt SEO & URLs in PrestaShop), wenn Sie Probleme bemerken, obwohl dies bei einer reinen Typänderung selten vorkommt.

**F: Das Modul zeigt keine Produkte an, wenn ich den Suchbegriff verwende.**
A:

1. **Auf Tippfehler prüfen:** Stellen Sie sicher, dass Ihr Suchbegriff korrekt geschrieben ist.
2. **Groß-/Kleinschreibung:** Produktnamen können je nach Datenbankkonfiguration groß-/kleinschreibungsempfindlich sein, versuchen Sie verschiedene Schreibweisen.
3. **Sprache:** Stellen Sie sicher, dass Sie in der richtigen Sprache suchen, wenn Ihr Shop mehrsprachig ist.
4. **Modulkonflikt:** Deaktivieren Sie vorübergehend andere suchbezogene Module, um Konflikte zu überprüfen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die einen PrestaShop-Shop mit dem Modul „Massenänderung des Produkttyps“ warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Massenänderung des Produkttyps“ (`massptype`) ist ein Standard-PrestaShop-Modul, das hauptsächlich im Back Office arbeitet. Es nutzt PrestaShops `Module`-Klasse und verwendet AJAX für die Produktfilterung und den Massenaktualisierungsprozess. Die Kernlogik befindet sich in der Hauptmoduldatei, die die Konfiguration, Produktauswahl und die Massenaktualisierung der Produkttypen handhabt. Es integriert ein benutzerdefiniertes Suchwerkzeug für die Produktauswahl.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller in den Verzeichnissen `controllers/admin` oder `controllers/front`. Die gesamte Logik wird innerhalb der Hauptmoduldatei `massptype.php` und ihrer `getContent()`-Methode verarbeitet, die als primärer Konfigurationseinstiegspunkt fungiert. AJAX-Anfragen werden über die Datei `ajax_products_list.php` des Hauptmoduls versendet.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen. Es interagiert direkt mit PrestaShops Kernmethoden `Product` und `Product::updateProductFlags()`, um Produkttypen zu ändern.

### 4.4 JavaScript-Assets (`views/js/`)

- `massptype/lib/searchTool/views/js/autocomplete.js`
  - **Umfang:** Back-Office (wird auf der Konfigurationsseite des Moduls verwendet).
  - **Zweck:** Bietet die Kernlogik für die Autocomplete-Funktionalität der Produktsuche. Es sendet wahrscheinlich AJAX-Anfragen an den `ajax_products_list.php`-Endpunkt des Moduls, um Produktvorschläge basierend auf der Benutzereingabe abzurufen.
- `massptype/views/js/jquery.autocomplete.js`
  - **Umfang:** Back-Office (wird auf der Konfigurationsseite des Moduls verwendet).
  - **Zweck:** Dies scheint ein jQuery-Plugin für die Autocomplete-Funktionalität zu sein, wahrscheinlich eine Abhängigkeit oder eine benutzerdefinierte Implementierung, die vom Suchwerkzeug verwendet wird. Es handhabt den UI-Aspekt der Anzeige von Vorschlägen und der Benutzerinteraktion.

### 4.5 CSS-Stylesheets (`views/css/`)

- `massptype/lib/searchTool/views/css/autocomplete.css`
  - **Umfang:** Back-Office (formatiert Elemente auf der Konfigurationsseite des Moduls).
  - **Zweck:** Formatiert das Autocomplete-Dropdown, Eingabefelder und möglicherweise die Liste der ausgewählten Produkte innerhalb der Suchwerkzeugoberfläche des Moduls. Entwickler können diese Stile in ihrem benutzerdefinierten Back Office-Theme überschreiben oder durch Hinzufügen spezifischerer CSS-Regeln.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `massptype/views/templates/hook/form.tpl`
    - **Hook:** Nicht direkt im traditionellen Sinne gehookt, sondern von `getContent()` der Hauptmoduldatei gerendert.
    - **Zweck:** Dies ist das Haupttemplate für das Konfigurationsformular des Moduls im Back Office. Es enthält die HTML-Struktur zum Auswählen von Produkten nach verschiedenen Kriterien und zum Auswählen des neuen Produkttyps.
- **Admin-Templates (`views/templates/admin/`)**:
  - `massptype/views/templates/admin/target_products.tpl`
    - **Zweck:** Dieses Template wird wahrscheinlich verwendet, um die Liste der ausgewählten Produkte anzuzeigen, nachdem die Filterkriterien angewendet wurden. Es wird dynamisch über AJAX aktualisiert, um anzuzeigen, welche Produkte betroffen sein werden.
  - `massptype/views/templates/admin/wtd.tpl` (What To Do)
    - **Zweck:** Dieses Template rendert wahrscheinlich den Abschnitt, in dem der Benutzer den neuen Produkttyp (Standard, Paket, Kombinationen, Virtuell) und die Schaltfläche „Änderungen anwenden“ auswählt.
- **Andere Templates**:
  - `massptype/lib/searchTool/views/scripts.tpl`
    - **Zweck:** Dieses Template enthält wahrscheinlich JavaScript-Code oder initialisiert die JavaScript-Autocomplete-Funktionalität für das Produktsuchwerkzeug. Es könnte in `form.tpl` enthalten sein.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es ändert bestehende PrestaShop-Kerntabellen, insbesondere `ps_product` (und potenziell `ps_product_shop`), indem es die Felder `cache_is_pack`, `cache_has_attachments`, `is_virtual` und `cache_default_attribute` aktualisiert, die den Produkttyp bestimmen. Konfigurationseinstellungen werden in `ps_configuration` unter Verwendung von Standard-Schlüsseln (z. B. `_PS_MASS_PTYPE_...`) gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine traditionellen Front-Office- oder Back-Office-Anzeige-Hooks. Seine Funktionalität ist vollständig in seiner `getContent()`-Methode und AJAX-Aufrufen enthalten.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionModuleInstall` | Während der Modulinstallation | Richtet die Erstkonfiguration ein. |
| `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt die Konfiguration. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Massenänderung des Produkttyps“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
