---
title: "Maximale Produktmenge - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Maximale Produktmenge“ von MyPresta.eu."
sidebar:
  label: "Maximale Produktmenge"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Maximum product quantity auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/maximum-product-quantity.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/maximum-product-quantity/)
>
> ---


# Maximale Produktmenge

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Maximale Produktmenge)

Die Hauptkonfigurationsseite des Moduls ist der Ort, an dem Sie die globalen Einstellungen definieren und produktspezifische Mengenbegrenzungen verwalten.

#### **Allgemeine Einstellungen**

-   **Was diese Einstellung bewirkt:** Dies sind die Kerneinstellungen, die die Funktionalität des Moduls aktivieren oder deaktivieren und definieren, wie es sich global verhält.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Modul aktivieren/deaktivieren:* Schaltet das gesamte Mengenbegrenzungssystem ein oder aus.
    -   *Globale maximale Menge:* Legt eine Standard-Maximalmenge für alle Produkte fest, wenn keine spezifische Begrenzung definiert ist.
-   **Empfohlener Wert:** Beginnen Sie mit der Aktivierung des Moduls und legen Sie eine angemessene globale Maximalmenge fest, wenn Sie eine allgemeine Regel anwenden möchten.
-   **Händlerszenario / Beispiel:** Wenn Sie sicherstellen möchten, dass kein Kunde jemals mehr als 100 Einheiten *eines beliebigen* Produkts kaufen kann, setzen Sie die globale Maximalmenge auf 100.

#### **Produktspezifische Mengenbegrenzungen**

Dieser Abschnitt ist normalerweise eine Tabelle oder eine Liste, in der Sie nach Produkten suchen und spezifische Limits für diese definieren können.

-   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die globalen Einstellungen für einzelne Produkte zu überschreiben. Sie können festlegen:
    -   **Maximale Menge pro Bestellung:** Die höchste Anzahl von Einheiten dieses Produkts, die ein Kunde in einen einzelnen Warenkorb legen kann.
    -   **Maximale Menge pro Kunde (gesamt):** Die höchste Anzahl von Einheiten dieses Produkts, die ein bestimmter Kunde *über alle seine Bestellungen hinweg* kaufen kann.
    -   **Kundengruppenspezifische Limits:** Wenden Sie unterschiedliche Limits basierend auf der Kundengruppe an (z. B. „Gäste“, „Kunden“, „Großhändler“).
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn Limits festgelegt sind:* Das Modul erzwingt diese spezifischen Limits für das ausgewählte Produkt und überschreibt alle globalen Einstellungen.
    -   *Wenn Limits entfernt werden:* Das Produkt kehrt zur Verwendung der globalen Maximalmengeneinstellungen zurück.
-   **Empfohlener Wert:** Legen Sie spezifische Limits für Produkte mit hoher Nachfrage, geringem Lagerbestand oder strategisch wichtigen Produkten fest.
-   **Händlerszenario / Beispiel:**
    -   Sie haben ein Produkt in limitierter Auflage. Sie setzen „Maximale Menge pro Bestellung“ auf 1 und „Maximale Menge pro Kunde (gesamt)“ auf 1, um eine Einheit pro Kunde sicherzustellen.
    -   Für einen Großartikel könnten Sie „Maximale Menge pro Bestellung“ für „Kunden“ auf 50, aber für „Großhändler“ auf 500 setzen.

#### **Einstellungen zur Bestellhistorie-Verfolgung**

-   **Was diese Einstellung bewirkt:** Steuert, ob das Modul die früheren Bestellungen eines Kunden berücksichtigt, um die Limits für die „maximale Menge pro Kunde (gesamt)“ durchzusetzen. Sie können oft angeben, welche Bestellstatus für das Limit zählen (z. B. nur „Gelieferte“ Bestellungen oder „Zahlung akzeptiert“).
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert:* Das Modul fragt die Bestellhistorie des Kunden ab, um dessen Gesamtbestellungen eines Produkts zu berechnen.
    -   *Wenn deaktiviert:* Nur die aktuelle Warenkorbmenge wird mit dem Limit für die „maximale Menge pro Bestellung“ verglichen. Limits für die „maximale Menge pro Kunde (gesamt)“ werden effektiv ignoriert.
-   **Empfohlener Wert:** Aktivieren Sie dies, wenn Sie echte Pro-Kunden-Limits über die Zeit durchsetzen möchten. Wählen Sie relevante Bestellstatus (z. B. „Zahlung akzeptiert“, „Geliefert“), um Käufe genau zu verfolgen.
-   **Händlerszenario / Beispiel:** Sie führen eine Aktion durch, bei der jeder Kunde maximal 3 Einheiten eines bestimmten Produkts *jemals* kaufen darf. Sie aktivieren die Bestellhistorie-Verfolgung und wählen die Status „Zahlung akzeptiert“ und „Geliefert“ aus. Wenn ein Kunde bereits 2 gekauft hat, kann er nur noch 1 weiteres in seinen Warenkorb legen.

#### **Anpassung der Fehlermeldung**

-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Meldung anzupassen, die Kunden angezeigt wird, wenn sie eine Mengenbegrenzung überschreiten.
-   **Auswirkung der Änderung dieser Einstellung:** Die standardmäßige, generische Fehlermeldung wird durch Ihren benutzerdefinierten Text ersetzt, der informativer oder markenbezogener sein kann.
-   **Empfohlener Wert:** Geben Sie eine klare, höfliche und hilfreiche Nachricht an. Sie können Platzhalter (falls vom Modul unterstützt) wie `{max_quantity}` verwenden, um die tatsächliche Begrenzung anzuzeigen.
-   **Händlerszenario / Beispiel:** Anstatt „Menge überschreitet Maximum“ könnten Sie festlegen: „Entschuldigung, Sie können maximal {max_quantity} Einheiten dieses Artikels kaufen. Dies hilft uns, einen fairen Zugang für alle unsere Kunden zu gewährleisten!“

#### **CSV / JSON Export & Import (falls verfügbar)**

-   **Was diese Einstellung bewirkt:** Bietet Tools zum Exportieren Ihrer aktuellen Mengenbegrenzungen in eine CSV- oder JSON-Datei und zum Importieren neuer Begrenzungen aus solchen Dateien. Dies ist nützlich für die Massenbearbeitung oder Migration von Einstellungen.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Export:* Erstellt eine Datei mit all Ihren definierten Produktmengenbegrenzungen.
    -   *Import:* Überschreibt oder fügt neue Mengenbegrenzungen basierend auf den Daten in der hochgeladenen Datei hinzu.
-   **Empfohlener Wert:** Verwenden Sie dies für große Updates oder die Ersteinrichtung, wenn Sie viele Produkte mit spezifischen Limits haben. Sichern Sie immer Ihre aktuellen Einstellungen, bevor Sie importieren.
-   **Händlerszenario / Beispiel:** Sie starten einen neuen Katalog mit 500 Produkten, von denen jedes eine einzigartige maximale Menge benötigt. Anstatt jedes manuell einzugeben, bereiten Sie eine CSV-Datei vor und importieren diese.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Modul aktivieren/deaktivieren | Aktiviert | Schaltet alle Mengenbegrenzungsfunktionen ein/aus. |
| Modulkonfiguration | Globale maximale Menge pro Bestellung | Variiert / 100 | Legt eine Standard-Maximalmenge für Produkte ohne spezifische Limits fest. |
| Modulkonfiguration | Produktspezifische maximale Menge pro Bestellung | Variiert / Benutzerdefiniert | Überschreibt das globale Limit für einzelne Produkte in einem einzigen Warenkorb. |
| Modulkonfiguration | Produktspezifische maximale Menge pro Kunde (gesamt) | Variiert / Benutzerdefiniert | Begrenzt die Gesamtmenge eines Produkts, die ein Kunde über alle Bestellungen hinweg kaufen kann. |
| Modulkonfiguration | Kundengruppenspezifische Limits | Variiert / Benutzerdefiniert | Wendet unterschiedliche Limits basierend auf Kundengruppen an (z. B. Großhändler). |
| Modulkonfiguration | Bestellhistorie verfolgen | Aktiviert | Überprüft frühere Bestellungen, um „Maximale Menge pro Kunde (gesamt)“ durchzusetzen. |
| Modulkonfiguration | Bestellstatus für die Verfolgung | Zahlung akzeptiert, Geliefert | Definiert, welche Bestellstatus für die Gesamtmenge der Kundenkäufe zählen. |
| Modulkonfiguration | Benutzerdefinierte Fehlermeldung | „Menge überschreitet Limit“ | Personalisiert die Meldung, die Kunden angezeigt wird, wenn ein Limit erreicht ist. |
| Modulkonfiguration | CSV/JSON exportieren/importieren | N/A | Ermöglicht die Massenverwaltung von Mengenbegrenzungen über Datei-Upload/-Download. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Limits festgelegt, aber Kunden können immer noch mehr als erlaubt hinzufügen. Was ist falsch?**
A1:
*   **Modul aktiviert?** Überprüfen Sie zunächst, ob das Modul in der Hauptkonfiguration aktiviert ist.
*   **Spezifisches Produkt vs. Global:** Stellen Sie sicher, dass Sie die Limits für das *spezifische Produkt* korrekt festgelegt haben oder dass die globalen Limits aktiv sind, wenn keine produktspezifischen Limits existieren.
*   **Kundengruppe:** Überprüfen Sie, ob die Kundengruppe, zu der der Kunde gehört, die korrekten Limits angewendet hat.
*   **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren). Manchmal werden noch alte Einstellungen ausgeliefert.
*   **Theme-Konflikte:** Selten kann ein stark angepasstes Theme die Handhabung von Mengeneingaben beeinträchtigen. Testen Sie mit dem Standard-PrestaShop-Theme, um dies auszuschließen.

**F2: Die „maximale Menge pro Kunde (gesamt)“ funktioniert nicht, obwohl die Bestellhistorie-Verfolgung aktiviert ist.**
A2:
*   **Bestellstatus:** Gehen Sie zur Modulkonfiguration und überprüfen Sie, welche „Bestellstatus für die Verfolgung“ ausgewählt sind. Wenn frühere Bestellungen eines Kunden einen nicht ausgewählten Status haben (z. B. „Ausstehend“ statt „Geliefert“), zählen sie nicht zum Limit. Stellen Sie sicher, dass die relevanten Status ausgewählt sind.
*   **Kundenanmeldung:** Stellen Sie sicher, dass der Kunde angemeldet ist. Das Modul kann frühere Käufe nur für identifizierte Kunden verfolgen, nicht für Gäste.

**F3: Wie übersetze ich die Fehlermeldungen in andere Sprachen?**
A3:
*   Navigieren Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
*   Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann Ihre Sprache.
*   Suchen Sie das Modul „Maximale Produktmenge“ in der Liste. Sie sollten in der Lage sein, die benutzerdefinierten Fehlermeldungen, die Sie festgelegt haben, für jede Sprache zu bearbeiten.

**F4: Das Modul scheint meine Produktseiten oder den Warenkorb zu verlangsamen.**
A4:
*   Obwohl das Modul optimiert ist, kann es bei einer extrem großen Anzahl von Produkten mit komplexen, gruppenspezifischen Limits und umfangreicher Bestellhistorie-Verfolgung zu einem geringfügigen Mehraufwand kommen.
*   **Leistung > CCC:** Stellen Sie sicher, dass Ihre CCC-Einstellungen (Kombinieren, Komprimieren, Caching) für CSS und JavaScript unter **Erweiterte Einstellungen > Leistung** aktiviert sind.
*   **Serverressourcen:** Überprüfen Sie das PHP-Speicherlimit und die Ausführungszeit Ihres Servers. Wenn diese zu niedrig sind, kann dies die Leistung beeinträchtigen.
*   **Datenbankoptimierung:** Stellen Sie sicher, dass Ihre PrestaShop-Datenbank regelmäßig optimiert wird.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Maximale Produktmenge“ arbeiten.

### 4.1 Architekturübersicht
Das Modul `Maximale Produktmenge` (interner Name `mqc`) ist ein Standard-PrestaShop-Modul, das den Kernbestellprozess erweitert. Es arbeitet hauptsächlich, indem es sich an verschiedene Punkte des Front-Office (Produktseite, Warenkorb, Checkout) einhakt, um Produktmengen gegen konfigurierte Limits zu validieren. Die Konfiguration wird über eine einzige `getContent()`-Methode in der Hauptmoduldatei verwaltet, die PrestaShops `Configuration`-Klasse zum Speichern von Einstellungen nutzt. Es verwendet JavaScript für die Front-End-Validierung und Benutzerfeedback sowie Smarty-Templates zur Anzeige von Nachrichten und Konfigurationsformularen.

### 4.2 Controller (`controllers/`)
Dieses Modul enthält keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Front-Office-Logik wird über Hooks und JavaScript abgewickelt, während die Back-Office-Konfiguration direkt in der `getContent()`-Methode der `index.php`-Moduldatei verwaltet wird.

### 4.3 Kernklassen & Modelle (`classes/`)
Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen. Alle Daten werden direkt in der Tabelle `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln gespeichert. Die Kernlogik befindet sich in der Datei `mqc/index.php`.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`mqc/views/js/mqc-17500.js`**:
    *   **Geltungsbereich:** Front-Office (spezifisch für PrestaShop 1.7.5.0+).
    *   **Verantwortlichkeit:** Enthält JavaScript-Logik, die auf neuere PrestaShop 1.7.x- und 8.x-Versionen zugeschnitten ist. Es hakt sich wahrscheinlich in `prestashop.on('updateProduct', ...)` oder ähnliche Ereignisse ein, um Mengen neu zu validieren, wenn Produktattribute geändert werden oder wenn die Mengeneingabe auf der Produktseite geändert wird. Es könnte auch AJAX-Aufrufe an die `index.php` des Moduls verarbeiten, um eine Echtzeit-Mengenvalidierung zu erhalten.
    *   **Interaktion:** Bindet an Mengeneingabefelder, In-den-Warenkorb-Buttons und potenziell Produktattribut-Selektoren, um dem Benutzer sofortiges Feedback zu geben, wenn eine Mengenbegrenzung überschritten wird.

-   **`mqc/views/js/mqc-front.js`**:
    *   **Geltungsbereich:** Front-Office (allgemein, potenziell für ältere PrestaShop-Versionen oder gemeinsame Logik).
    *   **Verantwortlichkeit:** Enthält allgemeine Front-Office-JavaScript-Logik für die Mengenvalidierung. Dies könnte umfassen:
        *   Event-Listener für Änderungen der Mengeneingabe auf der Produktseite oder im Warenkorb.
        *   AJAX-Aufrufe an den Server zur Überprüfung von Mengenbegrenzungen.
        *   Anzeige von Fehlermeldungen für den Benutzer.
        *   Potenzielles Deaktivieren oder Begrenzen von Mengeneingabefeldern.
    *   **Interaktion:** Ähnlich wie `mqc-17500.js`, könnte aber ältere jQuery-basierte Event-Bindungen oder weniger spezifische PrestaShop-Events verwenden.

-   **`mqc/views/js/mqc.js`**:
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Verwaltet JavaScript für die Konfigurationsseite des Moduls im PrestaShop Back Office. Dies könnte umfassen:
        *   Dynamische Formularelemente (z. B. Hinzufügen/Entfernen von produktspezifischen Limitzeilen).
        *   AJAX-Suche nach Produkten beim Festlegen individueller Limits.
        *   Validierung von Eingabefeldern im Konfigurationsformular.
        *   Logik für CSV/JSON-Import-/Exportfunktionen.
    *   **Interaktion:** Bindet an Formularelemente auf der Modulkonfigurationsseite und führt potenziell AJAX-Anfragen an die `getContent()`-Methode des Moduls zur Datenabfrage oder -übermittlung durch.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`mqc/views/css/mqc.css`**:
    *   **Geltungsbereich:** Sowohl Front-Office (für Fehlermeldungen) als auch Back-Office (für das Styling der Konfigurationsseite).
    *   **Wichtige UI-Komponenten und Container, die es stylt:**
        *   Fehlermeldungscontainer (z. B. `div.alert.alert-danger` oder benutzerdefinierte Klassen für modulspezifische Meldungen).
        *   Eingabefelder und Beschriftungen auf der Back-Office-Konfigurationsseite.
        *   Potenzielles Styling für dynamische Elemente, die von `mqc.js` hinzugefügt werden (z. B. Produktsuchergebnisse, Tabellenzeilen für Limits).
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Suchen Sie nach Klassen wie `.mqc-error-message`, `.mqc-limit-table`, `.mqc-product-search-results` innerhalb der Modul-Templates und des generierten HTML. Entwickler können diese in der `custom.css` ihres Themes oder durch Erstellen eines Child-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates sowohl für die Front-Office-Anzeige als auch für die Back-Office-Konfiguration.

-   **Hook-Templates (`views/templates/hook/`)**:
    *   **`product-details.tpl`**:
        *   **Hook:** Wahrscheinlich `displayProductExtraContent` oder `displayProductButtons` (abhängig von der PrestaShop-Version und der spezifischen Implementierung).
        *   **Ausgabe:** Könnte eine kleine Informationsmeldung über Mengenbegrenzungen auf der Produktseite anzeigen oder ein benutzerdefiniertes Mengeneingabefeld rendern, wenn das Modul das Standardfeld ersetzt.
    *   **`productActions.tpl`**:
        *   **Hook:** `displayProductActions` (auf der Produktseite).
        *   **Ausgabe:** Potenziell verwendet, um JavaScript-Variablen oder versteckte Eingaben im Zusammenhang mit Mengenbegrenzungen in der Nähe des In-den-Warenkorb-Buttons einzufügen oder eine Fehlermeldung anzuzeigen, wenn eine Mengenbegrenzung überschritten wird, bevor das Produkt in den Warenkorb gelegt wird.
    *   **`shoppingCart.tpl`**:
        *   **Hook:** `displayShoppingCartFooter` oder `displayShoppingCart` (auf der Warenkorbseite).
        *   **Ausgabe:** Wird verwendet, um Fehlermeldungen direkt im Warenkorb anzuzeigen, wenn Mengen Limits überschreiten, und so den Checkout zu verhindern.

-   **Admin-Templates (`views/templates/admin/`)**: Diese Templates werden innerhalb der `getContent()`-Methode von `mqc/index.php` gerendert, um die Konfigurationsoberfläche des Moduls zu erstellen.
    *   **`admintab.tpl`**: Wahrscheinlich ein Wrapper oder ein gemeinsamer Header/Footer für die Admin-Konfigurationsseite.
    *   **`button-subcategories-purchases.tpl`**: Könnte ein Button oder ein Abschnitt sein, der sich auf die Verwaltung von Käufen nach Unterkategorien bezieht, möglicherweise für erweiterte Berichte oder die Festlegung von Limits.
    *   **`button-subcategories.tpl`**: Ähnlich wie oben, aber für Unterkategorien im Allgemeinen.
    *   **`csv.tpl`**: Template für die CSV-Exportfunktion, das potenziell Formularelemente zur Auswahl von Exportoptionen enthält.
    *   **`csv_file.tpl`**: Template für die CSV-Importfunktion, normalerweise ein Upload-Formular.
    *   **`json.tpl`**: Template für JSON-Export/-Import, ähnlich wie `csv.tpl` und `csv_file.tpl`.
    *   **`main.tpl`**: Das primäre Template für die Konfigurationsseite des Moduls, das die Hauptformularstruktur, allgemeine Einstellungen und potenziell eine Tabelle für produktspezifische Limits enthält.
    *   **`message.tpl`, `message2.tpl`, `message3.tpl`, `message4.tpl`, `message5.tpl`**: Generische Nachrichtentemplates, die verwendet werden, um Erfolgs-, Fehler- oder Informationsmeldungen innerhalb der Back-Office-Konfiguration anzuzeigen.
    *   **`orderstates.tpl`**: Template zur Auswahl, welche Bestellstatus für das Limit „maximale Menge pro Kunde (gesamt)“ zählen.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert. Konfigurationsschlüssel folgen typischerweise einem Muster wie `MQC_GLOBAL_MAX_QTY`, `MQC_PRODUCT_LIMITS_[id_product]`, `MQC_TRACK_HISTORY_STATUSES` usw. Produktspezifische Limits könnten als serialisierte Arrays oder JSON-Strings in einem einzigen Konfigurationsschlüssel oder als individuelle Schlüssel pro Produkt/Gruppe gespeichert werden.
    *   Die Bestellhistorie-Verfolgung basiert auf der Abfrage bestehender PrestaShop-Tabellen: `ps_orders`, `ps_order_detail` und `ps_order_state`.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Registriert CSS- und JavaScript-Assets (`mqc.css`, `mqc-front.js`, `mqc-17500.js`) für die Front-Office-Funktionalität. |
| `displayProductButtons` | In der Nähe des „In den Warenkorb“-Buttons auf der Produktseite. | Fügt Mengenvalidierungslogik ein oder zeigt Meldungen zu produktspezifischen Limits an. |
| `displayProductExtraContent` | Unterhalb der Produktbeschreibung, oberhalb verwandter Produkte. | Kann verwendet werden, um Informationsmeldungen über Mengenbegrenzungen anzuzeigen. |
| `displayShoppingCart` | Innerhalb der Warenkorbzusammenfassung. | Validiert Mengen im Warenkorb und zeigt Fehlermeldungen an, wenn Limits überschritten werden. |
| `displayShoppingCartFooter` | Am unteren Rand der Warenkorbseite. | Ähnlich wie `displayShoppingCart`, für die endgültige Validierung vor dem Checkout. |
| `actionValidateOrder` | Nachdem eine Bestellung validiert und gespeichert wurde. | Potenziell für die Nachbearbeitung oder Protokollierung von Bestellungen verwendet, obwohl die primäre Validierung vor dem Checkout erfolgt. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert oder aktualisiert wurde (z. B. Mengenänderung). | Entscheidend für die Echtzeit-Mengenvalidierung, wenn ein Kunde Mengen im Warenkorb ändert oder neue Produkte hinzufügt. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert. | Registriert Front-Office-Assets, ähnlich wie `displayHeader`, aber spezifischer für den Controller-Kontext. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ausgabe rendert. | Registriert Back-Office-Assets (`mqc.js`, `mqc.css`) für die Konfigurationsseite des Moduls. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Maximale Produktmenge“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Fragen oder Problemen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
