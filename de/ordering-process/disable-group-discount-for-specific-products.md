---
title: "Gruppenrabatt für bestimmte Produkte deaktivieren - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gruppenrabatt für bestimmte Produkte deaktivieren“ von MyPresta.eu."
sidebar:
  label: "Gruppenrabatt für bestimmte Produkte deaktivieren - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable group discount for specific products auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/disable-group-discount-for-specific-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/disable-group-discount-for-specific-products/)
>
> ---


# Gruppenrabatt für bestimmte Produkte deaktivieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Gruppenrabatt für bestimmte Produkte deaktivieren“. Hier finden Sie alle Einstellungen, um zu steuern, welche Produkte von Gruppenrabatten ausgeschlossen werden.

**Menüpfad:** Back Office > Module > Modul-Manager > „Gruppenrabatt für bestimmte Produkte deaktivieren“ > Konfigurieren

#### 2.1.1 Abschnitt „Gruppenrabatt für bestimmte Produkte deaktivieren“

Dieser Abschnitt enthält die Kerneinstellungen zum Aktivieren oder Deaktivieren der Modulfunktionalität und zum Definieren, welche Produkte betroffen sind.

- **Einstellung: Aktiviert / Deaktiviert Schalter**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er bestimmt, ob die Logik des Moduls zum Deaktivieren von Gruppenrabatten aktiv oder inaktiv ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul prüft aktiv, ob ein Produkt oder seine Kategorie in Ihren Ausschlussregeln aufgeführt ist. Wenn ja, werden alle Gruppenrabatte für dieses Produkt ignoriert.
    - *Wenn deaktiviert:* Das Modul greift nicht in die Standardberechnungen der PrestaShop-Gruppenrabatte ein. Alle Produkte unterliegen gegebenenfalls Gruppenrabatten.
  - **Empfohlener Wert:** „Aktiviert“, wenn Sie die Funktionalität des Moduls nutzen möchten.
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten oder Wartungsarbeiten durchführen, würden Sie es aktivieren. Wenn Sie vorübergehend möchten, dass alle Gruppenrabatte angewendet werden, ohne das Modul zu deinstallieren, würden Sie es deaktivieren.
- **Einstellung: Kategorien (Auswahlfeld)**

  - **Was diese Einstellung bewirkt:** Hier können Sie ganze Produktkategorien auswählen, deren Produkte von Gruppenrabatten ausgeschlossen werden sollen. Jedes Produkt, das zu einer ausgewählten Kategorie gehört, erhält keine Gruppenrabatte.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Kategorien ausgewählt sind:* Alle Produkte innerhalb der ausgewählten Kategorien (und deren Unterkategorien, abhängig von der PrestaShop-Kategorienstruktur und der Produktzuweisung) erhalten keine Gruppenrabatte.
    - *Wenn keine Kategorien ausgewählt sind:* Produkte werden nicht aufgrund ihrer Kategorie ausgeschlossen.
  - **Empfohlener Wert:** Wählen Sie die Kategorien aus, die Produkte enthalten, die Sie von Gruppenrabatten ausschließen möchten.
  - **Händlerszenario / Beispiel:** Sie verkaufen Elektronik. Ihre Kategorie „Neuheiten“ enthält oft stark nachgefragte Artikel. Sie möchten sicherstellen, dass selbst Ihre Großhandelskunden für diese neuen Produkte im ersten Monat den vollen Preis zahlen. Sie würden hier die Kategorie „Neuheiten“ auswählen.
- **Einstellung: Spezifische Produkte (Such- und Auswahlfeld)**

  - **Was diese Einstellung bewirkt:** Hier können Sie einzelne Produkte suchen und auswählen, die von Gruppenrabatten ausgeschlossen werden sollen. Dies bietet eine granularere Kontrolle als Kategorien.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn spezifische Produkte ausgewählt sind:* Nur die explizit ausgewählten Produkte erhalten keine Gruppenrabatte, unabhängig von ihrer Kategorie.
    - *Wenn keine spezifischen Produkte ausgewählt sind:* Produkte werden nicht aufgrund individueller Auswahl ausgeschlossen.
  - **Empfohlener Wert:** Wählen Sie spezifische Produkte aus, die Sie von Gruppenrabatten ausschließen möchten.
  - **Händlerszenario / Beispiel:** Sie haben einen Kunstdruck in limitierter Auflage (Produkt-ID 123) und ein spezielles Bundle-Angebot (Produkt-ID 456), die Sie niemals für eine Kundengruppe rabattieren möchten. Sie würden „Kunstdruck (Limitierte Auflage)“ und „Spezial-Bundle-Angebot“ suchen und zu dieser Liste hinzufügen.

#### 2.1.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Aktiviert / Deaktiviert | Aktiviert | Hauptschalter zum Aktivieren/Deaktivieren der Modulfunktionalität. |
| Modulkonfiguration | Kategorien | Relevante Kategorien auswählen | Schließt alle Produkte innerhalb ausgewählter Kategorien von Gruppenrabatten aus. |
| Modulkonfiguration | Spezifische Produkte | Relevante Produkte auswählen | Schließt individuell ausgewählte Produkte von Gruppenrabatten aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul konfiguriert, aber Gruppenrabatte werden immer noch auf meine ausgeschlossenen Produkte angewendet. Was ist falsch?**
A:

- **Ist das Modul aktiviert?** Überprüfen Sie den Schalter „Aktiviert / Deaktiviert“ auf der Konfigurationsseite des Moduls. Er muss auf „Aktiviert“ stehen.
- **Haben Sie Ihre Änderungen gespeichert?** Klicken Sie immer auf die Schaltfläche „Speichern“, nachdem Sie Änderungen an der Konfiguration vorgenommen haben.
- **Leeren Sie Ihren PrestaShop-Cache:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Überprüfen Sie die Produkt-/Kategoriezuweisung:** Stellen Sie sicher, dass das Produkt der Kategorie korrekt zugewiesen ist, die Sie ausgeschlossen haben, oder dass Sie genau das Produkt ausgewählt haben, das Sie ausschließen möchten.
- **Überprüfen Sie andere Module:** Ein anderes Preis- oder Rabattmodul könnte Konflikte verursachen. Versuchen Sie, andere rabattbezogene Module vorübergehend zu deaktivieren, um zu sehen, ob sich das Problem löst.

**F2: Beeinflusst dieses Modul meine regulären Katalogpreisregeln oder spezifischen Preise?**
A: Nein, dieses Modul zielt speziell auf *Gruppenrabatte* ab. Es greift nicht in Katalogpreisregeln, spezifische Preise, die Sie für einzelne Produkte festlegen, oder Warenkorbregeln (Gutscheine) ein. Es verhindert lediglich den zusätzlichen prozentualen Rabatt, der basierend auf der Kundengruppe angewendet wird.

**F3: Wie geht dieses Modul mit Produkten in mehreren Kategorien um?**
A: Wenn ein Produkt in mehreren Kategorien ist und *eine* dieser Kategorien für den Ausschluss im Modul ausgewählt ist, wird das Produkt von Gruppenrabatten ausgeschlossen. Das Modul prüft, ob das Produkt zu einer ausgeschlossenen Kategorie *gehört*.

**F4: Ich verwende ein benutzerdefiniertes Theme. Wird dieses Modul korrekt funktionieren?**
A: Ja, dieses Modul arbeitet auf der Ebene der Kernpreisberechnung und führt keine neuen Front-Office-Elemente oder komplexe Stile ein, die typischerweise mit Themes in Konflikt geraten würden. Es sollte vollständig mit jedem PrestaShop-Theme kompatibel sein.

**F5: Kann ich Produkte für *einige* Gruppen, aber nicht für andere ausschließen?**
A: Nein, dieses Modul deaktiviert Gruppenrabatte für die ausgewählten Produkte/Kategorien *für alle Kundengruppen*. Wenn ein Produkt auf der Ausschlussliste steht, erhält keine Kundengruppe einen Rabatt darauf. Die Kernfunktionalität von PrestaShop ermöglicht es Ihnen, Gruppenrabatte pro Gruppe festzulegen, aber dieses Modul fungiert als Überschreibung für bestimmte Produkte, wodurch diese von *jedem* Gruppenrabatt ausgenommen werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die das Modul „Gruppenrabatt für bestimmte Produkte deaktivieren“ verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht

Das Modul funktioniert hauptsächlich, indem es eine zentrale PrestaShop-Klasse (`Product.php`) überschreibt, um die Preisberechnungslogik zu ändern. Es greift in die Methode `Product::getPriceStatic()` ein, die zentral für die Bestimmung des Endpreises eines Produkts in PrestaShop ist. Wenn diese Methode aufgerufen wird, prüft das Modul, ob das aktuelle Produkt oder seine zugehörigen Kategorien für den Ausschluss von Gruppenrabatten konfiguriert sind. Wenn dies der Fall ist, stellt es sicher, dass die Gruppenrabattkomponente der Preisberechnung umgangen wird.

Das Modul verwendet die Standard-`Module`-Klasse von PrestaShop für seine Konfigurationsoberfläche und stützt sich auf Einträge in der `Configuration`-Tabelle, um seine Einstellungen zu speichern. Es enthält auch ein einfaches Suchwerkzeug für die Produktauswahl im Back Office.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Logik wird hauptsächlich durch eine Klassenüberschreibung und die `getContent()`-Methode der Hauptmoduldatei für die Konfiguration implementiert.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`exgdisc/override/classes/Product.php`**
  - **Verantwortlichkeit:** Dies ist die wichtigste Datei im Modul. Sie überschreibt die Kernklasse `Product`, um die Methode `getPriceStatic()` zu ändern.
  - **Klassenname:** `Product` (überschreibt die ursprüngliche `Product`-Klasse)
  - **Elternklasse:** `ProductCore`
  - **Schlüssellogik:**
    - Die überschriebene `getPriceStatic()`-Methode ruft zuerst die `getPriceStatic()` der Elternklasse auf, um den Basispreis zu erhalten.
    - Sie ruft dann die Modulkonfiguration (`exgdisc_categories`, `exgdisc_products`) von `Configuration::get()` ab.
    - Sie prüft, ob die ID des aktuellen Produkts (`$id_product`) in der Liste `exgdisc_products` enthalten ist.
    - Sie prüft auch, ob eine der mit `$id_product` verknüpften Kategorien in der Liste `exgdisc_categories` enthalten ist.
    - Wenn eine der Bedingungen wahr ist, bedeutet dies, dass das Produkt von Gruppenrabatten ausgeschlossen werden soll. Die Methode berechnet dann den Preis neu und ignoriert dabei effektiv die Gruppenrabattkomponente, die normalerweise von der `getPriceStatic()`-Methode der Elternklasse angewendet würde.
    - Die ursprüngliche `Product::getPriceStatic()`-Methode hat einen Parameter `$use_group_reduction`. Die Überschreibung stellt sicher, dass selbst wenn dieser `true` ist, die Gruppenreduzierung nicht angewendet wird, wenn das Produkt vom Modul ausgeschlossen ist.

### 4.4 JavaScript-Assets (`views/js/`)

- **`exgdisc/lib/searchTool/views/js/autocomplete.js`**
  - **Geltungsbereich:** Back-Office (wird auf der Modulkonfigurationsseite verwendet).
  - **Zweck:** Bietet die Autocomplete-Funktionalität zur Auswahl spezifischer Produkte im Konfigurationsformular des Moduls.
  - **Schlüssellogik:**
    - Initialisiert ein Autocomplete-Eingabefeld (wahrscheinlich zielt es auf ein Element mit einer bestimmten ID ab, z. B. `#product_autocomplete_input`).
    - Sendet AJAX-Anfragen an einen PrestaShop-Admin-Controller (z. B. `AdminProducts` oder einen benutzerdefinierten Suchcontroller), um Produktvorschläge basierend auf der Benutzereingabe abzurufen.
    - Behandelt die Auswahl von Produkten, indem sie diese einem versteckten Eingabefeld oder einer visuellen Liste auf der Konfigurationsseite hinzufügt.
    - Verwaltet das Entfernen ausgewählter Produkte aus der Liste.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`exgdisc/lib/searchTool/views/css/autocomplete.css`**
  - **Geltungsbereich:** Back-Office (formatiert das Autocomplete-Suchwerkzeug).
  - **Zweck:** Bietet Styling für das Produktsuchfeld und die Liste der ausgewählten Produkte auf der Konfigurationsseite des Moduls.
  - **Schlüsselselektoren:** Enthält wahrscheinlich Stile für das Autocomplete-Dropdown, ausgewählte Element-Tags/-Badges und möglicherweise das Suchfeld selbst. Entwickler können diese Klassen bei Bedarf in ihren benutzerdefinierten Admin-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`exgdisc/lib/searchTool/views/scripts.tpl`**

  - **Geltungsbereich:** Back-Office (auf der Modulkonfigurationsseite enthalten).
  - **Zweck:** Rendert die HTML-Struktur für das Produktsuchfeld und den Bereich, in dem ausgewählte Produkte angezeigt werden. Es enthält wahrscheinlich auch die notwendigen JavaScript-Aufrufe zur Initialisierung des `autocomplete.js`-Skripts.
  - **Schlüsselelemente:** Eingabefeld zum Suchen von Produkten, ein Container zum Anzeigen ausgewählter Produkte (z. B. als Tags oder Listenelemente) und versteckte Eingabefelder zum Speichern der IDs ausgewählter Produkte.
- **`exgdisc/views/script.tpl`**

  - **Geltungsbereich:** Back-Office (auf der Modulkonfigurationsseite enthalten).
  - **Zweck:** Dieses Template wird wahrscheinlich verwendet, um zusätzliches JavaScript oder CSS auszugeben, das spezifisch für das Hauptmodul-Konfigurationsformular ist, möglicherweise im Zusammenhang mit Formularvalidierung oder dynamischen UI-Elementen. Angesichts des `ActionAdminControllerSetMedia`-Hooks könnte es zur Registrierung von Assets verwendet werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert:
    - `exgdisc_categories`: Speichert eine serialisierte Zeichenfolge oder eine kommagetrennte Liste von Kategorie-IDs, die ausgeschlossen werden sollen.
    - `exgdisc_products`: Speichert eine serialisierte Zeichenfolge oder eine kommagetrennte Liste von Produkt-IDs, die ausgeschlossen werden sollen.
    - `mypresta_updates`, `update_`, `updatev_`: Bezogen auf den Update-Mechanismus von MyPresta.eu.
    - `exgdisc_groups`: (Nicht explizit in den bereitgestellten Informationen verwendet, könnte aber eine alte oder zukünftige Einstellung für gruppenspezifische Ausschlüsse sein).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller geladen wird und seine Medien (JS/CSS) gesetzt werden. | Wird vom Modul verwendet, um seine Back-Office-JavaScript (`autocomplete.js`) und CSS (`autocomplete.css`) für die Konfigurationsseite zu laden und so die Funktion des Produktsuchwerkzeugs sicherzustellen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Gruppenrabatt für bestimmte Produkte deaktivieren“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.
