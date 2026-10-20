---
title: "Kombinationen in separate Produkte aufteilen - Händlerhandbuch & Konfigurationsanleitung"
description: ""
sidebar:
  label: "Kombinationen in separate Produkte aufteilen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Split combinations into separate products auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/split-combinations-into-separate-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/split-combinations-into-separate-products/)
>
> ---


# Kombinationen in separate Produkte aufteilen

## 1. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 1.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der durch Klicken auf „Konfigurieren“ nach der Installation aufgerufen wird.

#### Allgemeine Einstellungen

-   **Modul aktivieren:**
    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Die Funktionen des Moduls, einschließlich der Möglichkeit, Produkte aufzuteilen, und seine Anzeigelogik werden aktiv.
        *   *Wenn deaktiviert:* Die Funktionalität des Moduls ist vollständig ausgeschaltet. Es werden keine Kombinationen aufgeteilt, und vorhandene aufgeteilte Produkte kehren in ihren ursprünglichen Zustand zurück oder werden je nach interner Modullogik als reguläre Produkte verwaltet.
    *   **Empfohlener Wert:** JA (sobald Sie bereit sind, das Modul zu verwenden).
    *   **Händlerszenario / Beispiel:** Sie richten das Modul zum ersten Mal ein und möchten es testen. Sie aktivieren es, um seine Auswirkungen zu sehen. Wenn Sie es vorübergehend für Wartungsarbeiten deaktivieren müssen, können Sie es ausschalten.
-   **Aufteilungsmodus:**
    *   **Was diese Einstellung bewirkt:** Bestimmt, wie das Modul mit Produktkombinationen umgeht. Sie können wählen, ob für jede Kombination tatsächlich neue Produkte erstellt oder nur deren Anzeige auf Listenseiten geändert werden soll.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn auf „Separate Produkte für jede Kombination erstellen“ eingestellt:* Das Modul erstellt physisch neue Produkteinträge in Ihrer Datenbank für jede Kombination. Jedes neue Produkt erhält eine eigene ID, URL, Lagerbestand, Preis usw. Dies ist die leistungsstärkste Option für SEO und detaillierte Kontrolle.
        *   *Wenn auf „Eine Kachel pro Kombination auf Kategorie-, Marken-, Lieferanten-, Such- und Bestsellerlisten anzeigen (virtuelle Aufteilung)“ eingestellt:* Das Modul erstellt *keine* neuen Produkte. Stattdessen ändert es die Anzeige bestehender Produkte mit Kombinationen auf Listenseiten, sodass es *scheint*, als wäre jede Kombination ein separates Produkt. Der tatsächliche Produktkatalog bleibt unverändert. Dies hat weniger Auswirkungen auf SEO, kann aber das Browsing-Erlebnis verbessern.
    *   **Empfohlener Wert:** „Separate Produkte für jede Kombination erstellen“ für maximale SEO und Kontrolle, oder „Eine Kachel pro Kombination anzeigen…“ für eine einfachere Anzeigeoptimierung.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass jede Farbe und Größe Ihres T-Shirts eine eigene Produktseite hat und bei Google rankt. Sie wählen „Separate Produkte erstellen“. Wenn Sie Ihre Kategorieseiten nur übersichtlicher gestalten möchten, indem Sie jede Variante anzeigen, ohne neue Produkte zu erstellen, wählen Sie „Eine Kachel pro Kombination anzeigen“.
-   **Nur aktive Produkte aufteilen:**
    *   **Was diese Einstellung bewirkt:** Steuert, ob das Modul nur Produkte verarbeiten soll, die derzeit in Ihrem Shop aktiviert sind, oder alle Produkte unabhängig von ihrem aktiven Status.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Nur Produkte, die derzeit in Ihrem PrestaShop-Katalog auf „aktiv“ gesetzt sind, werden in ihren Kombinationen aufgeteilt. Inaktive Produkte werden ignoriert.
        *   *Wenn deaktiviert:* Das Modul versucht, Kombinationen für alle Produkte aufzuteilen, einschließlich derer, die derzeit inaktiv sind.
    *   **Empfohlener Wert:** JA (um die Erstellung unnötiger Produkte für Artikel zu vermeiden, die Sie nicht verkaufen).
    *   **Händlerszenario / Beispiel:** Sie haben viele alte, inaktive Produkte in Ihrem Katalog. Sie möchten Kombinationen nur für Ihr aktuelles, aktives Inventar aufteilen, um Ihren Shop organisiert zu halten. Sie aktivieren diese Einstellung.
-   **Aktion für Quellprodukt nach Aufteilung:**
    *   **Was diese Einstellung bewirkt:** Definiert, was mit dem Originalprodukt (dem mit Kombinationen) geschieht, nachdem seine Kombinationen in neue, einzelne Produkte aufgeteilt wurden.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn auf „Quellprodukt deaktivieren“ eingestellt:* Das Originalprodukt wird in Ihrem Katalog als inaktiv markiert. Es wird im Front Office nicht mehr sichtbar sein.
        *   *Wenn auf „Quellprodukt aktiv lassen“ eingestellt:* Das Originalprodukt bleibt aktiv und in Ihrem Shop sichtbar. Sie müssen möglicherweise dessen Anzeige oder Inhalt manuell anpassen, um Verwechslungen mit den neuen aufgeteilten Produkten zu vermeiden.
        *   *Wenn auf „Quellprodukt löschen“ eingestellt:* Das Originalprodukt wird dauerhaft aus Ihrem Katalog entfernt. Mit äußerster Vorsicht verwenden!
    *   **Empfohlener Wert:** „Quellprodukt deaktivieren“ oder „Quellprodukt aktiv lassen“ (abhängig von Ihrer Strategie). „Quellprodukt löschen“ wird im Allgemeinen nicht empfohlen, es sei denn, Sie sind absolut sicher.
    *   **Händlerszenario / Beispiel:** Sie haben ein „T-Shirt“-Produkt in „T-Shirt - Rot - S“, „T-Shirt - Blau - M“ usw. aufgeteilt. Sie möchten, dass Kunden nur die einzelnen Varianten sehen, daher wählen Sie „Quellprodukt deaktivieren“ für das ursprüngliche „T-Shirt“.
-   **Produktbilder kopieren:**
    *   **Was diese Einstellung bewirkt:** Bestimmt, ob die Bilder, die mit dem Originalprodukt und seinen Kombinationen verknüpft sind, auf die neu erstellten aufgeteilten Produkte kopiert werden sollen.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Die Bilder des Originalprodukts und seiner spezifischen Kombination werden dupliziert und dem neuen aufgeteilten Produkt zugewiesen. Dies stellt sicher, dass jedes neue Produkt relevante Bilder hat.
        *   *Wenn deaktiviert:* Neue aufgeteilte Produkte werden ohne Bilder erstellt. Sie müssten dann manuell Bilder für jedes neue Produkt hochladen, was sehr zeitaufwendig ist.
    *   **Empfohlener Wert:** JA.
    *   **Händlerszenario / Beispiel:** Sie haben eine „Rotes T-Shirt“-Kombination mit einem spezifischen Bild. Wenn Sie es in „T-Shirt - Rot - Klein“ aufteilen, möchten Sie, dass dieses rote T-Shirt-Bild automatisch dem neuen Produkt zugewiesen wird.
-   **Mindestanzahl Kombinationen zum Aufteilen:**
    *   **Was diese Einstellung bewirkt:** Legt einen Schwellenwert für die Anzahl der Kombinationen fest, die ein Produkt haben muss, bevor das Modul es zum Aufteilen in Betracht zieht. Produkte mit weniger Kombinationen als diesem Wert werden ignoriert.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn auf einen Wert (z. B. 2) eingestellt:* Nur Produkte, die 2 oder mehr Kombinationen haben, werden verarbeitet. Produkte mit nur 1 Kombination (oder ohne Kombinationen) werden übersprungen.
        *   *Wenn auf 0 oder 1 eingestellt:* Alle Produkte mit mindestens einer Kombination werden zum Aufteilen in Betracht gezogen.
    *   **Empfohlener Wert:** 2 (um das Aufteilen einfacher Produkte zu vermeiden, die davon möglicherweise nicht profitieren).
    *   **Händlerszenario / Beispiel:** Sie haben einige Produkte mit nur einer Kombination (z. B. ein „Einheitsgröße“-T-Shirt). Sie möchten diese nicht aufteilen, aber Sie möchten Produkte mit mehreren Farben und Größen aufteilen. Sie stellen dies auf 2 ein.

#### Namensgenerator-Einstellungen

Diese Einstellungen steuern, wie die Namen der neuen aufgeteilten Produkte generiert werden.

-   **Namensgenerator-Vorlage:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine benutzerdefinierte Vorlage zum Generieren der Namen der neuen aufgeteilten Produkte zu definieren. Sie können Platzhalter für Produktname, Attributgruppennamen und Attributnamen verwenden.
    *   **Auswirkung der Änderung dieser Einstellung:** Das Modul verwendet diese Vorlage, um das `name`-Feld für jedes neue Produkt zu erstellen.
    *   **Empfohlener Wert:** `[product_name] - [attribute_group_name]: [attribute_name]` (oder ähnlich, je nach Ihrem Markenstil).
    *   **Händlerszenario / Beispiel:** Ihr Originalprodukt ist „Fancy Dress“. Es hat Kombinationen wie „Farbe: Rot“ und „Größe: Klein“. Wenn Ihre Vorlage `[product_name] - [attribute_name]` ist, wäre der neue Produktname „Fancy Dress - Rot“.
-   **URL-Generator-Vorlage:**
    *   **Was diese Einstellung bewirkt:** Ähnlich wie der Namensgenerator ermöglicht dies die Definition einer benutzerdefinierten Vorlage zum Generieren der sprechenden URLs (Slugs) der neuen aufgeteilten Produkte.
    *   **Auswirkung der Änderung dieser Einstellung:** Das Modul verwendet diese Vorlage, um das `link_rewrite`-Feld für jedes neue Produkt zu erstellen.
    *   **Empfohlener Wert:** `[product_name]-[attribute_name]` (oder ähnlich, um sicherzustellen, dass es SEO-freundlich und einzigartig ist).
    *   **Händlerszenario / Beispiel:** Im Beispiel „Fancy Dress“ könnte die neue URL, wenn Ihre URL-Vorlage `[product_name]-[attribute_name]` ist, `/fancy-dress-red` lauten.
-   **Trennzeichen für mehrere Attribute:**
    *   **Was diese Einstellung bewirkt:** Gibt das Zeichen oder die Zeichenfolge an, die verwendet wird, um mehrere Attributnamen zu trennen, wenn sie im Produktnamen oder in der URL kombiniert werden.
    *   **Auswirkung der Änderung dieser Einstellung:** Dieses Zeichen wird zwischen Attributnamen eingefügt, wenn ein Produkt Kombinationen aus mehreren Attributgruppen (z. B. Farbe und Größe) hat.
    *   **Empfohlener Wert:** `-` (Bindestrich) für URLs, `,` (Komma Leerzeichen) für Namen.
    *   **Händlerszenario / Beispiel:** Wenn ein Produkt „T-Shirt - Rot - Klein“ ist, ist der Bindestrich das Trennzeichen. Sie können es in einen Schrägstrich `/` ändern, wenn Sie dies bevorzugen.

#### Erweiterte Einstellungen

-   **Alte URLs umleiten:**
    *   **Was diese Einstellung bewirkt:** Wenn aktiviert, erstellt das Modul 301-Weiterleitungen von der URL des Originalprodukts (und potenziell kombinationsspezifischen URLs) zur URL des neuen aufgeteilten Produkts. Dies ist entscheidend für SEO.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Suchmaschinen und Benutzer, die auf alte URLs zugreifen, werden automatisch zur korrekten neuen Produktseite weitergeleitet, wodurch der SEO-Wert erhalten bleibt und defekte Links verhindert werden.
        *   *Wenn deaktiviert:* Alte URLs führen zu 404 „Seite nicht gefunden“-Fehlern, was Ihrer SEO und dem Benutzererlebnis schadet.
    *   **Empfohlener Wert:** JA.
    *   **Händlerszenario / Beispiel:** Sie haben „T-Shirt“ in „T-Shirt - Rot - Klein“ aufgeteilt. Wenn ein Kunde oder eine Suchmaschine versucht, auf die alte „T-Shirt“-Seite zuzugreifen, wird er automatisch zur relevantesten neuen aufgeteilten Produktseite weitergeleitet.
-   **Cache nach Aufteilung leeren:**
    *   **Was diese Einstellung bewirkt:** Leert automatisch den PrestaShop-Cache, nachdem ein Aufteilungsvorgang durchgeführt wurde.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Stellt sicher, dass Änderungen, die vom Modul vorgenommen wurden (neue Produkte, Weiterleitungen), sofort im Front Office sichtbar sind, ohne dass der Cache manuell geleert werden muss.
        *   *Wenn deaktiviert:* Sie müssen den Cache möglicherweise manuell leeren (Erweiterte Einstellungen > Leistung), damit die Änderungen angezeigt werden.
    *   **Empfohlener Wert:** JA.
    *   **Händlerszenario / Beispiel:** Sie haben gerade eine große Anzahl von Produkten aufgeteilt. Wenn Sie dies aktivieren, stellen Sie sicher, dass Ihre Kunden die neuen Produktlisten sofort sehen, ohne dass Sie den Cache manuell leeren müssen.

### 1.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminMySplitProductsController (Back Office > Module > Kombinationen in separate Produkte aufteilen > Aufteilungen verwalten)

Dieser Bildschirm bietet die Oberfläche zum Initiieren, Verwalten und Rückgängigmachen von Produktaufteilungsvorgängen.

-   **Bildschirmname & Menüposition:** „Aufteilungen verwalten“ (zugänglich über die Hauptkonfigurationsseite des Moduls oder möglicherweise einen neuen Menüpunkt unter „Katalog“ oder „Module“).
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Produktsuche & -auswahl:** Eine Suchleiste und eine Autocomplete-Funktion, um bestimmte Produkte zu finden, die Sie aufteilen möchten.
    *   **„Produkt aufteilen“-Button:** Startet den Aufteilungsprozess für das ausgewählte Produkt.
    *   **„Rückgängig machen“-Button:** Ermöglicht es Ihnen, einen vorherigen Aufteilungsvorgang für ein bestimmtes Produkt rückgängig zu machen, das Originalprodukt wiederherzustellen und die aufgeteilten Produkte zu entfernen.
    *   **Verlaufstabelle:** Eine Liste aller Produkte, die aufgeteilt wurden, mit Anzeige von:
        *   Originalproduktname
        *   Datum der Aufteilung
        *   Anzahl der aufgeteilten Kombinationen
        *   Status (z. B. „Abgeschlossen“, „Rückgängig gemacht“)
        *   Aktionsschaltflächen (z. B. „Rückgängig machen“, „Aufgeteilte Produkte anzeigen“)
-   **Auswirkung von Änderungen:**
    *   **Aufteilen eines Produkts:** Erstellt neue Produkteinträge in Ihrem Katalog basierend auf den Kombinationen des ausgewählten Produkts und den Konfigurationseinstellungen des Moduls (Namen, URLs, Bilder usw.). Der Status des Originalprodukts kann sich ändern (z. B. deaktiviert).
    *   **Rückgängigmachen einer Aufteilung:** Löscht die während der Aufteilung erstellten Produkte und stellt das Originalprodukt in seinen Zustand vor der Aufteilung wieder her (z. B. aktiviert es wieder, stellt seine Kombinationen wieder her). Dies ist eine leistungsstarke Rückgängig-Funktion.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Verwenden Sie die Suchleiste, um das Produkt zu finden, das Sie aufteilen möchten.
    2.  Überprüfen Sie die vorgeschlagenen Namen und URLs (falls eine Vorschau verfügbar ist).
    3.  Klicken Sie auf „Produkt aufteilen“.
    4.  Überwachen Sie die Verlaufstabelle für den Status.
    5.  Wenn Sie einen Fehler machen oder Ihre Meinung ändern, verwenden Sie die „Rückgängig machen“-Funktion aus der Verlaufstabelle.

#### index.php (mysplitproducts/controllers/admin/index.php)

Diese Datei dient wahrscheinlich als Platzhalter oder Basis für die Admin-Controller des Moduls, um die Sicherheitsbestimmungen von PrestaShop zu gewährleisten, indem sie die direkte Verzeichnisauflistung verhindert. Sie stellt keinen eigenständigen, benutzerorientierten Bildschirm dar, sondern ist Teil der internen Struktur des Moduls.

### 1.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
| | Aufteilungsmodus | „Separate Produkte erstellen“ | Wie Kombinationen behandelt werden (neue Produkte vs. virtuelle Anzeige). |
| | Nur aktive Produkte aufteilen | JA | Nur aktive Produkte verarbeiten. |
| | Aktion für Quellprodukt nach Aufteilung | „Quellprodukt deaktivieren“ | Was mit dem Originalprodukt geschieht. |
| | Produktbilder kopieren | JA | Bilder auf neue aufgeteilte Produkte duplizieren. |
| | Mindestanzahl Kombinationen zum Aufteilen | 2 | Schwellenwert für die Produktaufteilung. |
| | Namensgenerator-Vorlage | `[product_name] - [attribute_group_name]: [attribute_name]` | Definiert neue Produktnamen. |
| | URL-Generator-Vorlage | `[product_name]-[attribute_name]` | Definiert neue sprechende Produkt-URLs. |
| | Trennzeichen für mehrere Attribute | `-` (für URL), `,` (für Namen) | Zeichen zum Trennen mehrerer Attribute. |
| | Alte URLs umleiten | JA | Erstellt 301-Weiterleitungen für SEO. |
| | Cache nach Aufteilung leeren | JA | Leert den PrestaShop-Cache automatisch. |
| **Aufteilungen verwalten (AdminMySplitProductsController)** | Produktsuche & Aufteilung | N/A | Produkte finden und Aufteilung initiieren. |
| | Aufteilung rückgängig machen | N/A | Einen vorherigen Aufteilungsvorgang rückgängig machen. |
| | Verlaufstabelle | N/A | Vergangene Aufteilungsvorgänge anzeigen und verwalten. |

## 2. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Nachdem ich Produkte aufgeteilt habe, sehe ich die neuen Produkte nicht in meinen Kategorien oder Suchergebnissen.**

-   **A:** Der häufigste Grund ist das Caching.
    *   **Lösung:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ und „Cache leeren“ für alle Caches). Wenn die Moduleinstellung „Cache nach Aufteilung leeren“ aktiviert ist, sollte dies automatisch geschehen, aber manchmal ist ein manuelles Leeren erforderlich. Stellen Sie außerdem sicher, dass die neuen Produkte auf „aktiv“ gesetzt und Kategorien zugeordnet sind.

**F2: Meine alten Produkt-URLs zeigen jetzt „Seite nicht gefunden“ (404-Fehler) an.**

-   **A:** Dies bedeutet normalerweise, dass die Weiterleitungsfunktion nicht aktiv ist oder nicht richtig funktioniert.
    *   **Lösung:** Gehen Sie zur Konfigurationsseite des Moduls und stellen Sie sicher, dass „Alte URLs umleiten“ auf JA gesetzt ist. Wenn es bereits aktiviert ist, leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung). Wenn das Problem weiterhin besteht, überprüfen Sie die `.htaccess`-Datei Ihres Servers auf widersprüchliche Rewrite-Regeln oder kontaktieren Sie den Support.

**F3: Die Namen oder URLs meiner neuen aufgeteilten Produkte sehen seltsam aus oder entsprechen nicht meinen Erwartungen.**

-   **A:** Dies wird durch die Einstellungen „Namensgenerator-Vorlage“ und „URL-Generator-Vorlage“ gesteuert.
    *   **Lösung:** Gehen Sie zur Konfigurationsseite des Moduls und überprüfen Sie diese Vorlagen. Stellen Sie sicher, dass Sie die richtigen Platzhalter (`[product_name]`, `[attribute_name]`, `[attribute_group_name]`) verwenden und dass die Trennzeichen angemessen sind. Sie können verschiedene Vorlagen zuerst an einem einzelnen Produkt testen. Denken Sie daran, den Cache nach Änderungen an Vorlagen zu leeren.

**F4: Einige Produkte mit Kombinationen wurden nicht aufgeteilt, obwohl ich den Prozess initiiert habe.**

-   **A:** Überprüfen Sie die Einstellung „Mindestanzahl Kombinationen zum Aufteilen“ in der Modulkonfiguration.
    *   **Lösung:** Wenn ein Produkt weniger Kombinationen als dieser Schwellenwert hat, wird es übersprungen. Passen Sie diese Einstellung an, wenn Sie Produkte mit weniger Varianten aufteilen möchten. Stellen Sie außerdem sicher, dass „Nur aktive Produkte aufteilen“ nicht verhindert, dass inaktive Produkte verarbeitet werden, falls dies Ihre Absicht ist.

**F5: Was passiert mit Kundenwarenkörben, wenn ich ein Produkt aufteile, das sie bereits hinzugefügt haben?**

-   **A:** Das Modul ist so konzipiert, dass es dies elegant handhabt. Bestehende offene Warenkörbe, die eine Kombination eines aufgeteilten Produkts enthalten, werden typischerweise aktualisiert, um die neue, eindeutige Produkt-ID widerzuspiegeln. Dies bedeutet, dass der Warenkorb des Kunden weiterhin den korrekten Artikel enthält, der nun mit seinem neuen, individuellen Produkteintrag verknüpft ist. Es ist jedoch immer am besten, Aufteilungen in verkehrsarmen Zeiten durchzuführen oder gründlich zu testen.

## 3. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 3.1 Architekturübersicht

Das Modul „Kombinationen in separate Produkte aufteilen“ (`mysplitproducts`) ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut. Es nutzt `ObjectModel` stark für die Datenpersistenz, einen benutzerdefinierten `AdminController` für seine Back-Office-Oberfläche und eine Reihe dedizierter Dienstklassen, um die komplexe Logik der Produktaufteilung, Benennung und Weiterleitung zu kapseln. Das Modul erweitert die Kernfunktionalität von PrestaShop durch dynamisches Erstellen und Verwalten von Produktentitäten, die Handhabung von URL-Rewrites und die Integration in den Modulmanager. Es basiert auf einem robusten internen Protokollierungssystem und einem Finder-Muster für eine effiziente Datenabfrage.

### 3.2 Controller (`controllers/`)

-   **Front-Office-Controller**: Keine explizit im bereitgestellten Inventar definiert. Die Front-Office-Anzeigelogik für virtuelle Aufteilungen oder Weiterleitungen wird wahrscheinlich über Hooks innerhalb der Hauptdatei `mysplitproducts.php` oder über Overrides gehandhabt.
-   **Back-Office-Admin-Controller**:
    *   `controllers/admin/AdminMySplitProductsController.php`
        *   **Klassenname & Elternklasse:** `AdminMySplitProductsController` erweitert `ModuleAdminController`.
        *   **Tab-Name und verwaltete Entität:** Dieser Controller verwaltet die Kernfunktionalität des Aufteilens und Rückgängigmachens von Produkten. Er präsentiert eine Raster-/Verwaltungsansicht für verarbeitete Produkte und ermöglicht Administratoren, neue Aufteilungen zu initiieren oder bestehende rückgängig zu machen. Er interagiert mit den Klassen `MspSplitEngine`, `MspLogger` und `MspRedirector`.
        *   **Verantwortlichkeit:** Verwaltet die Anzeige der „Aufteilungen verwalten“-Oberfläche, verarbeitet AJAX-Anfragen für die Produktsuche, initiiert den Produktaufteilungsprozess und verwaltet Rückgängig-Operationen. Es ist die zentrale Anlaufstelle für die administrativen Aufgaben des Moduls.
    *   `controllers/admin/index.php`
        *   **Klassenname & Elternklasse:** N/A (keine Klassendatei).
        *   **Verantwortlichkeit:** Dies ist eine standardmäßige leere `index.php`-Datei, die in Unterverzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern und die Sicherheit zu erhöhen. Sie enthält keine funktionale Logik für das Modul.

### 3.3 Kernklassen & Modelle (`classes/`)

-   `classes/index.php`
    *   **Verantwortlichkeit:** Standardmäßige leere `index.php` zur Sicherheit, verhindert Verzeichnisauflistung.
-   `classes/MspAliasStore.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** Wahrscheinlich `ps_mysplitproducts_alias` (benutzerdefinierte Tabelle) oder `ps_configuration` zum Speichern von Aliasen/Weiterleitungen.
    *   **Ob es ObjectModel erweitert:** Unwahrscheinlich, dass es `ObjectModel` direkt erweitert, verwaltet aber Daten im Zusammenhang mit Aliasen.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Verwaltet die Zuordnung zwischen ursprünglichen Produkt-/Kombinations-IDs und ihren neu erstellten aufgeteilten Produkt-IDs. Entscheidend für die Weiterleitungs- und Rückgängig-Funktionalität.
-   `classes/MspCatalog.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc. (PrestaShop-Kernprodukttabellen).
    *   **Ob es ObjectModel erweitert:** Nein, wahrscheinlich eine Dienstklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Bietet Methoden zum Abfragen und Bearbeiten von PrestaShop-Kernproduktdaten. Wird von `MspSplitEngine` verwendet, um Produktdetails, Kombinationen abzurufen und Produktstatus zu aktualisieren.
-   `classes/MspCombinationSearchProvider.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** `ps_product`, `ps_product_lang`, `ps_product_attribute`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`.
    *   **Ob es ObjectModel erweitert:** Nein, wahrscheinlich eine Dienstklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Bietet Funktionen zum Suchen nach Produkten und deren Kombinationen, oft verwendet für die Autocomplete-Funktion im Admin-Controller.
-   `classes/MspFinder.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** Verschiedene PrestaShop-Tabellen, abhängig vom Suchkontext.
    *   **Ob es ObjectModel erweitert:** Nein, wahrscheinlich eine Dienst-/Hilfsklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Eine allgemeine Datenabrufklasse, die gängige Datenbankabfragen für Produkte, Attribute und andere vom Modul benötigte Entitäten abstrahiert.
-   `classes/MspLogger.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** Wahrscheinlich `ps_mysplitproducts_log` (benutzerdefinierte Tabelle).
    *   **Ob es ObjectModel erweitert:** Ja, oder verwaltet eine benutzerdefinierte Tabelle direkt.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Zeichnet alle Aufteilungs- und Rückgängig-Operationen auf, einschließlich Zeitstempel, betroffener Produkte und Status. Wesentlich für die Verlaufstabelle in `AdminMySplitProductsController` und zur Fehlerbehebung.
-   `classes/MspNameBuilder.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** N/A (reine Logik).
    *   **Ob es ObjectModel erweitert:** Nein, eine Hilfsklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Implementiert die Logik zum Generieren neuer Produktnamen und sprechender URLs basierend auf den konfigurierten Vorlagen (`MSP_NAME_BUILDER_TEMPLATE`, `MSP_URL_BUILDER_TEMPLATE`) und Attributdaten.
-   `classes/MspProductCloner.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc.
    *   **Ob es ObjectModel erweitert:** Nein, eine Dienstklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Die Kernklasse, die für die Duplizierung eines Produkts und seiner zugehörigen Daten (Bilder, Lagerbestand, Kategorien, Merkmale usw.) verantwortlich ist, um ein neues, eigenständiges Produkt für eine bestimmte Kombination zu erstellen. Sie handhabt den komplexen Prozess des Kopierens von Daten über mehrere PrestaShop-Tabellen hinweg.
-   `classes/MspRedirector.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** `ps_mysplitproducts_redirect` (benutzerdefinierte Tabelle) oder `ps_url_rewrite` (PrestaShop-Kern).
    *   **Ob es ObjectModel erweitert:** Nein, eine Dienstklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Verwaltet die Erstellung und Entfernung von 301-Weiterleitungen von ursprünglichen Produkt-/Kombinations-URLs zu den neuen aufgeteilten Produkt-URLs. Integriert sich in das URL-Rewrite-System von PrestaShop oder implementiert eine eigene Weiterleitungslogik.
-   `classes/MspSplitEngine.php`
    *   **Mit welcher Datenbanktabelle interagiert es:** Orchestriert Interaktionen mit `MspCatalog`, `MspProductCloner`, `MspNameBuilder`, `MspRedirector`, `MspLogger`.
    *   **Ob es ObjectModel erweitert:** Nein, die Haupt-Orchestrator-Dienstklasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:** Die zentrale Klasse, die den gesamten Aufteilungsprozess koordiniert. Sie nimmt eine Produkt-ID entgegen, ruft deren Kombinationen ab, verwendet `MspNameBuilder` zur Generierung neuer Details, `MspProductCloner` zur Erstellung neuer Produkte, `MspRedirector` für URLs und `MspLogger` zur Aufzeichnung des Vorgangs. Handhabt auch die Rückgängig-Logik.

### 3.4 JavaScript-Assets (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Welche Event-Listener es bindet:** Eingabeereignisse auf Suchfeldern.
    *   **Welche DOM-Manipulation, modalen Popups, Animationen oder externen Drittanbieter-SDK-Aufrufe es ausführt:** Bietet eine Autocomplete-Funktionalität für Produktsuchfelder in der Admin-Oberfläche, wahrscheinlich unter Verwendung von AJAX-Aufrufen an `AdminMySplitProductsController`, um Produktvorschläge abzurufen.
-   `views/js/admin.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Welche Event-Listener es bindet:** Klickereignisse auf Schaltflächen (z. B. „Produkt aufteilen“, „Rückgängig machen“), Formularübermittlungen.
    *   **Welche DOM-Manipulation, modalen Popups, Animationen oder externen Drittanbieter-SDK-Aufrufe es ausführt:** Verwaltet die interaktiven Elemente des `AdminMySplitProductsController`-Dashboards, einschließlich der Initiierung von Aufteilungs-/Rückgängig-Aktionen, der Aktualisierung der Verlaufstabelle und der Anzeige von Ladeindikatoren oder Erfolgs-/Fehlermeldungen.
-   `views/js/configure.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Welche Event-Listener es bindet:** Änderungsereignisse auf Konfigurationsfeldern, Formularübermittlungen.
    *   **Welche DOM-Manipulation, modalen Popups, Animationen oder externen Drittanbieter-SDK-Aufrufe es ausführt:** Verwaltet das Hauptkonfigurationsformular des Moduls. Kann Logik zum Anzeigen/Ausblenden von Feldern basierend auf anderen Auswahlen (z. B. Aufteilungsmodus), Formularvalidierung und AJAX-Speicherung von Konfigurationseinstellungen enthalten.
-   `views/js/listing.js`
    *   **Geltungsbereich:** Front-Office (für den virtuellen Aufteilungsmodus).
    *   **Welche Event-Listener es bindet:** Potenziell `prestashop.on`-Ereignisse für Produktlistenaktualisierungen, DOM ready.
    *   **Welche DOM-Manipulation, modalen Popups, Animationen oder externen Drittanbieter-SDK-Aufrufe es ausführt:** Wenn der „virtuelle Aufteilungs“-Modus aktiv ist, würde dieses Skript Produktlisten auf Kategorie-, Such- und anderen Seiten dynamisch ändern, um einzelne Kombinationen als Kacheln anzuzeigen. Dies könnte das Klonen vorhandener Produktelemente, das Aktualisieren ihres Inhalts (Name, Bild, Preis) und das erneute Rendern von Teilen des Produktgitters umfassen.

### 3.5 CSS-Stylesheets (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Back-Office Admin-Formular-Styling.
    *   **Wichtige UI-Komponenten und Container, die es stylt:** Stile für das Autocomplete-Dropdown, Such-Eingabefelder und Vorschlagslisten innerhalb des Admin-Panels.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`.
-   `views/css/admin.css`
    *   **Geltungsbereich:** Back-Office Admin-Formular-Styling.
    *   **Wichtige UI-Komponenten und Container, die es stylt:** Allgemeine Stile für die Konfigurationsseiten des Moduls und das „Aufteilungen verwalten“-Dashboard, einschließlich Tabellen, Schaltflächen, Formularelemente und Statusindikatoren.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** `.mysplitproducts-config`, `.mysplitproducts-dashboard`, `.mysplitproducts-table`, `.mysplitproducts-status-success`, `.mysplitproducts-status-error`.

### 3.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, aber das Modul könnte Hooks für die Front-Office-Anzeige im virtuellen Aufteilungsmodus verwenden (z. B. `displayProductList`, `displayProductExtraContent`), die von der Hauptdatei `mysplitproducts.php` behandelt würden.
-   **Admin-Templates (`views/templates/admin/`)**:
    *   `views/templates/admin/configure_shell.tpl`
        *   **Zweck:** Dieses Template dient wahrscheinlich als Haupt-Wrapper oder Shell für die Konfigurationsseite des Moduls, einschließlich der allgemeinen Einstellungen und möglicherweise Tabs oder Abschnitte für andere Einstellungen. Es bietet das Gesamtlayout für `getContent()`.
    *   `views/templates/admin/dashboard.tpl`
        *   **Zweck:** Dieses Template rendert das „Aufteilungen verwalten“-Dashboard, einschließlich des Produktsuchfeldes, des „Produkt aufteilen“-Buttons und der Verlaufstabelle der Aufteilungsvorgänge. Es ist die Ansicht für `AdminMySplitProductsController`.
-   **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt. Das Front-Office-Rendering für virtuelle Aufteilungen würde wahrscheinlich die Änderung bestehender Theme-Templates über Hooks oder Overrides oder das dynamische Einfügen von Inhalten über JavaScript (`listing.js`) beinhalten.

### 3.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   `ps_mysplitproducts_log`: Speichert einen Verlauf aller Aufteilungs- und Rückgängig-Operationen, einschließlich `id_product_original`, `id_product_split`, `action` (split/rollback), `date_add`, `status`.
    *   `ps_mysplitproducts_redirect`: Speichert 301-Weiterleitungszuordnungen von alten URLs zu neuen aufgeteilten Produkt-URLs, einschließlich `old_url`, `new_url`, `id_product_original`, `id_product_split`.
    *   `ps_mysplitproducts_alias`: Speichert Zuordnungen zwischen ursprünglichen Produkt-/Kombinations-IDs und den neuen aufgeteilten Produkt-IDs, entscheidend für interne Suchvorgänge und Rückgängigmachen.
    *   Konfigurationsdatensätze gespeichert in `ps_configuration`:
        *   `MSP_MODE`: (int) 0 für virtuell, 1 für reale Aufteilung.
        *   `MSP_ACTIVE_ONLY`: (bool) Nur aktive Produkte aufteilen.
        *   `MSP_SOURCE_ACTION`: (int) Aktion für Quellprodukt (deaktivieren, aktiv lassen, löschen).
        *   `MSP_IMAGE_COPY`: (bool) Bilder auf neue Produkte kopieren.
        *   `MSP_MIN_COMBINATIONS`: (int) Mindestanzahl Kombinationen zum Aufteilen.
        *   `MSP_NAME_BUILDER_TEMPLATE`: (string) Vorlage für neue Produktnamen.
        *   `MSP_URL_BUILDER_TEMPLATE`: (string) Vorlage für neue Produkt-URLs.
        *   `MSP_SEPARATOR_MULTIPLE_ATTRIBUTES`: (string) Trennzeichen für mehrere Attribute.
        *   `MSP_REDIRECT_OLD_URLS`: (bool) 301-Weiterleitungen aktivieren.
        *   `MSP_CLEAR_CACHE_AFTER_SPLIT`: (bool) Cache automatisch leeren.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Potenziell Injektion von CSS/JS für das Front-Office im virtuellen Aufteilungsmodus oder Meta-Tags für SEO. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite. | Injektion von CSS/JS für die Admin-Seiten des Moduls (`admin.css`, `admin.js`, `autocomplete.css`, `autocomplete.js`). |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts. | Potenziell erneute Bewertung für die Aufteilung oder Aktualisierungen im Zusammenhang mit aufgeteilten Produkten. |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Bereinigt aufgeteilte Produkte oder Weiterleitungen, wenn das Originalprodukt gelöscht wird. |
| `actionProductSave` | Vor oder nach dem Speichern eines Produkts. | Fängt Produktspeicherungen ab, um aufgeteilte Produkte oder verwandte Daten zu verwalten. |
| `actionObjectProductAddAfter` | Nach dem Hinzufügen eines neuen Produkts. | Potenziell Auslösen der Aufteilung für neu hinzugefügte Produkte, falls konfiguriert. |
| `actionObjectProductUpdateAfter` | Nach der Aktualisierung eines Produkts. | Aktualisiert verwandte aufgeteilte Produkte oder Weiterleitungen. |
| `actionObjectProductDeleteAfter` | Nach dem Löschen eines Produkts. | Bereinigt zugehörige aufgeteilte Produkte und Weiterleitungen. |
| `displayProductList` | Wenn eine Produktliste gerendert wird (Kategorie, Suche usw.). | **Entscheidend für den virtuellen Aufteilungsmodus.** Ändert die Produktliste, um einzelne Kombinationen als Kacheln anzuzeigen. |
| `displayProductExtraContent` | Auf der Produktseite, unterhalb des Hauptinhalts. | Könnte verwendet werden, um Links zu anderen Kombinationen oder eine Nachricht über aufgeteilte Produkte anzuzeigen. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Fügt einen benutzerdefinierten Tab oder Abschnitt zur Produktbearbeitungsseite hinzu, um Aufteilungen im Zusammenhang mit diesem spezifischen Produkt zu verwalten. |
| `actionAdminProductsListingResultsModifier` | Ändert die Ergebnisse der Produktliste im Back Office. | Passt die Produktliste an, um Originalprodukte anzuzeigen/auszublenden oder aufgeteilte Produkte hervorzuheben. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller sein Template rendert. | Registriert Front-Office-JavaScript (`listing.js`) und CSS für den virtuellen Aufteilungsmodus. |
| `moduleRoutes` | Während der URL-Routing-Initialisierung. | Registriert benutzerdefinierte Routen für aufgeteilte Produkte oder Weiterleitungen. |

## 4. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und umfassenden Support verweisen wir auf Ihr Kundenkonto bei MyPresta.eu.

-   **Modul-Updates:** Melden Sie sich in Ihrem Konto unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) an, um die aktuellste Version von „Kombinationen in separate Produkte aufteilen“ herunterzuladen.
-   **Technischer Support:** Wenn Sie Probleme haben oder Fragen, die in diesem Handbuch nicht behandelt werden, eröffnen Sie bitte ein Support-Ticket über Ihr MyPresta.eu-Kundenkonto. Unser Expertenteam steht Ihnen gerne zur Verfügung.
