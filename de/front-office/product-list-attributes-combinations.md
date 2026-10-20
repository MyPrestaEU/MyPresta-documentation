---
title: "Produktlistenattribute (Kombinationen) – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produktlistenattribute (Kombinationen)' von MyPresta.eu."
sidebar:
  label: "Produktlistenattribute (Kombinationen)"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product list attributes (combinations) auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-list-attributes-combinations.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-list-attributes-combinations/)
>
> ---


# Produktlistenattribute (Kombinationen)

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Webhosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite für die Einstellungen des Moduls „Produktlistenattribute (Kombinationen)“. Hier steuern Sie, wie Kombinationen in Ihren Produktlisten angezeigt werden.

#### Allgemeine Einstellungen

-   **Kombinationen in der Produktliste anzeigen:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er steuert, ob Produktkombinationen überhaupt auf Produktlistenseiten angezeigt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Das Modul fügt die Kombinationsauswahl-Oberfläche in Ihre Produktlistenvorlagen ein, sodass Kunden Varianten direkt auswählen können.
        -   *Wenn deaktiviert (NEIN):* Das Modul ist im Front Office inaktiv, und Produktlisten verhalten sich wie Standard-PrestaShop, wobei Kunden die Produktseite besuchen müssen, um Kombinationen auszuwählen.
    -   **Empfohlener Wert:** JA (um die Kernfunktionalität des Moduls zu nutzen).
    -   **Händlerszenario / Beispiel:** Wenn Sie ein schnelleres Einkaufserlebnis bieten möchten, aktivieren Sie dies. Wenn Sie es vorziehen, dass Kunden immer auf der Produktseite landen, um weitere Details zu erhalten, deaktivieren Sie es.

-   **„In den Warenkorb“-Button anzeigen:**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob ein „In den Warenkorb“-Button zusammen mit den Kombinationsselektoren in der Produktliste angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Ein „In den Warenkorb“-Button erscheint neben den Kombinationsoptionen. Sobald ein Kunde eine Kombination auswählt, kann er auf diesen Button klicken, um sie in den Warenkorb zu legen.
        -   *Wenn deaktiviert (NEIN):* Die Kombinationsselektoren sind weiterhin sichtbar, aber Kunden müssen auf das Produktbild oder den Namen klicken, um zur Produktseite zu gelangen und es in den Warenkorb zu legen. Dies kann nützlich sein, wenn Sie Optionen anzeigen, aber dennoch Produktseitenbesuche fördern möchten.
    -   **Empfohlener Wert:** JA (für maximalen Komfort und Konversion).
    -   **Händlerszenario / Beispiel:** Für ein schnelles Kauferlebnis aktivieren Sie dies. Wenn Ihre Produkte vor dem Kauf umfangreiches Lesen oder Anpassen erfordern, könnten Sie es deaktivieren, um Kunden auf die Produktseite zu leiten.

-   **Mengenfeld anzeigen:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob ein Mengenfeld neben dem „In den Warenkorb“-Button in der Produktliste angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Kunden können die Menge einer ausgewählten Kombination, die sie in ihren Warenkorb legen möchten, direkt aus der Produktliste angeben.
        -   *Wenn deaktiviert (NEIN):* Der „In den Warenkorb“-Button fügt eine einzelne Einheit der ausgewählten Kombination hinzu. Kunden müssten dann die Mengen im Warenkorb oder auf der Produktseite anpassen.
    -   **Empfohlener Wert:** JA (für die meisten Shops, da es mehr Flexibilität bietet).
    -   **Händlerszenario / Beispiel:** Wenn Kunden oft mehrere Einheiten desselben Artikels kaufen (z. B. Socken, Schreibwaren), aktivieren Sie dies. Wenn Ihre Produkte typischerweise einzeln gekauft werden, könnten Sie es für ein saubereres Aussehen deaktivieren.

-   **Produktreferenz anzeigen:**
    -   **Was diese Einstellung bewirkt:** Zeigt oder verbirgt die Referenznummer (SKU) des Produkts neben den Kombinationsoptionen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Die Produktreferenz ist sichtbar, was für Kunden, die bestimmte Artikel verfolgen, oder für B2B-Kunden hilfreich sein kann.
        -   *Wenn deaktiviert (NEIN):* Die Referenz wird nicht angezeigt, was zu einer saubereren, weniger überladenen Oberfläche führt.
    -   **Empfohlener Wert:** NEIN (es sei denn, Ihre Zielgruppe profitiert speziell von der Anzeige von Referenzen).
    -   **Händlerszenario / Beispiel:** Für B2B-Shops oder technische Produkte, bei denen Kunden oft nach SKU bestellen, aktivieren Sie dies. Für den allgemeinen Einzelhandel ist es normalerweise nicht notwendig.

-   **Produkt EAN13/JAN anzeigen:**
    -   **Was diese Einstellung bewirkt:** Zeigt oder verbirgt die EAN13- oder JAN-Barcode-Nummer des Produkts.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Die EAN13/JAN ist sichtbar, was für Kunden nützlich sein kann, die Produkte anhand dieser Kennungen abgleichen müssen.
        -   *Wenn deaktiviert (NEIN):* Die EAN13/JAN wird nicht angezeigt.
    -   **Empfohlener Wert:** NEIN (ähnlich wie Referenz, nur aktivieren, wenn ein spezifischer Kundenbedarf besteht).
    -   **Händlerszenario / Beispiel:** Selten für die Front-Office-Anzeige benötigt, könnte aber für spezifische Nischen oder B2B nützlich sein.

-   **Produkt UPC anzeigen:**
    -   **Was diese Einstellung bewirkt:** Zeigt oder verbirgt die UPC-Barcode-Nummer des Produkts.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Die UPC ist sichtbar.
        -   *Wenn deaktiviert (NEIN):* Die UPC wird nicht angezeigt.
    -   **Empfohlener Wert:** NEIN (ähnlich wie EAN13/JAN).
    -   **Händlerszenario / Beispiel:** Ähnlich wie EAN13/JAN, typischerweise keine Front-Office-Anforderung für die meisten Einzelhändler.

-   **Produktgewicht anzeigen:**
    -   **Was diese Einstellung bewirkt:** Zeigt oder verbirgt das Gewicht des Produkts neben den Kombinationsoptionen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Das Produktgewicht ist sichtbar, was für Kunden, die sich um Versandkosten oder Handhabung sorgen, wichtig sein kann.
        -   *Wenn deaktiviert (NEIN):* Das Gewicht wird nicht angezeigt.
    -   **Empfohlener Wert:** NEIN (es sei denn, das Gewicht ist ein kritischer Faktor für Ihre Produkte).
    -   **Händlerszenario / Beispiel:** Für Produkte, bei denen das Gewicht ein signifikanter Kauffaktor ist (z. B. Massengüter, schwere Maschinenteile), aktivieren Sie dies.

-   **Produktpreis anzeigen:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob der Preis der ausgewählten Kombination dynamisch aktualisiert und in der Produktliste angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Wenn ein Kunde verschiedene Kombinationen auswählt, wird der angezeigte Preis aktualisiert, um den Preis der spezifischen Kombination widerzuspiegeln (einschließlich etwaiger Attributpreisauswirkungen).
        -   *Wenn deaktiviert (NEIN):* Der in der Produktliste angezeigte Preis bleibt der Basisproduktpreis, und Kunden müssen möglicherweise die Kombinationspreise ableiten oder zur Produktseite gehen.
    -   **Empfohlener Wert:** JA (entscheidend für Transparenz und informierten Kauf).
    -   **Händlerszenario / Beispiel:** Aktivieren Sie dies immer für eine klare Preisgestaltung. Wenn deaktiviert, könnten Kunden durch Preisänderungen an der Kasse verwirrt werden.

-   **Produktverfügbarkeit anzeigen:**
    -   **Was diese Einstellung bewirkt:** Zeigt oder verbirgt den Lagerverfügbarkeitsstatus für die ausgewählte Kombination (z. B. „Auf Lager“, „Nicht auf Lager“, „Letzte Artikel!“).
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Kunden sehen den Lagerstatus, was ihnen bei Kaufentscheidungen hilft und Frustrationen beim Versuch, nicht vorrätige Artikel zu bestellen, verhindert.
        -   *Wenn deaktiviert (NEIN):* Der Lagerstatus wird nicht angezeigt, was dazu führen kann, dass Kunden versuchen, nicht vorrätige Artikel in ihren Warenkorb zu legen.
    -   **Empfohlener Wert:** JA (dringend empfohlen zur Steuerung der Kundenerwartungen).
    -   **Händlerszenario / Beispiel:** Essenziell für jeden Shop, um Bestellungen für nicht verfügbare Artikel zu verhindern. Immer aktivieren.

-   **Produktbeschreibung anzeigen:**
    -   **Was diese Einstellung bewirkt:** Zeigt oder verbirgt eine kurze Beschreibung des Produkts unter den Kombinationen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Eine kurze Produktbeschreibung wird angezeigt, die mehr Kontext bietet, ohne einen Klick auf die Produktseite zu erfordern.
        -   *Wenn deaktiviert (NEIN):* Die Beschreibung wird nicht angezeigt, wodurch die Produktliste prägnant bleibt.
    -   **Empfohlener Wert:** NEIN (Produktlisten dienen normalerweise dem schnellen Durchsuchen; detaillierte Beschreibungen gehören auf die Produktseite).
    -   **Händlerszenario / Beispiel:** Wenn Sie sehr kurze, prägnante Beschreibungen haben, die schnelle Entscheidungen unterstützen, könnten Sie dies aktivieren. Andernfalls lassen Sie es deaktiviert, um Unordnung zu vermeiden.

-   **Kurze Produktbeschreibung anzeigen:**
    -   **Was diese Einstellung bewirkt:** Ähnlich wie „Produktbeschreibung anzeigen“, aber speziell für das Feld der Kurzbeschreibung.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Die kurze Produktbeschreibung ist sichtbar.
        -   *Wenn deaktiviert (NEIN):* Die kurze Beschreibung wird nicht angezeigt.
    -   **Empfohlener Wert:** NEIN (aus den gleichen Gründen wie die vollständige Beschreibung).
    -   **Händlerszenario / Beispiel:** Sparsam verwenden, nur wenn Ihre Kurzbeschreibungen extrem prägnant und für den Kauf in der Listenansicht entscheidend sind.

-   **Produktbilder anzeigen:**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob das Produktbild dynamisch aktualisiert wird, wenn ein Kunde eine andere Kombination auswählt (z. B. Auswahl eines „blauen“ Hemdes zeigt das Bild des blauen Hemdes).
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Das Hauptproduktbild in der Liste ändert sich, um das Bild widerzuspiegeln, das der ausgewählten Kombination zugeordnet ist. Dies bietet ein reichhaltiges visuelles Feedback.
        -   *Wenn deaktiviert (NEIN):* Das Produktbild bleibt statisch und zeigt das Standardproduktbild an, unabhängig von der ausgewählten Kombination.
    -   **Empfohlener Wert:** JA (dringend empfohlen für visuelle Bestätigung und ein besseres Benutzererlebnis).
    -   **Händlerszenario / Beispiel:** Entscheidend für Kleidung, Elektronik oder jedes Produkt, bei dem die visuelle Darstellung der Variante wichtig ist.

-   **Produktattribute anzeigen als:**
    -   **Was diese Einstellung bewirkt:** Dies ist eine entscheidende Einstellung, die definiert, wie die Kombinationsoptionen (z. B. Größe, Farbe) dem Kunden präsentiert werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Dropdown-Liste:* Attribute erscheinen als Standard-HTML-Dropdown-`<select>`-Elemente. Dies ist kompakt und für viele Optionen geeignet.
        -   *Radio-Buttons:* Attribute erscheinen als Radio-Buttons. Gut für eine kleine Anzahl unterschiedlicher Optionen.
        -   *Farbauswahl:* Wenn Ihre Attribute in PrestaShop als „Farbe“ definiert sind, werden sie als anklickbare Farbfelder angezeigt.
    -   **Empfohlener Wert:**
        -   *Farbauswahl* für Farbattribute.
        -   *Dropdown-Liste* für Attribute mit vielen Optionen (z. B. Größen S-XXL).
        -   *Radio-Buttons* für Attribute mit wenigen, unterschiedlichen Optionen (z. B. „Ja/Nein“, „Mit/Ohne“).
    -   **Händlerszenario / Beispiel:** Für ein Bekleidungsgeschäft würden Sie wahrscheinlich „Farbauswahl“ für Farben und „Dropdown-Liste“ für Größen verwenden. Für ein einfaches Produkt mit zwei Optionen wie „Geschenkverpackung: Ja/Nein“ könnten Radio-Buttons am besten sein.

-   **Produktattribute anzeigen für:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen festzulegen, welche Produktattribute ihre Kombinationen in der Produktliste anzeigen sollen. Sie können spezifische Attributgruppen (z. B. „Größe“, „Farbe“, „Material“) auswählen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ausgewählte Attributgruppen:* Nur Kombinationen, die die ausgewählten Attributgruppen betreffen, werden angezeigt. Wenn Sie beispielsweise „Farbe“ und „Größe“ auswählen, sehen Kunden Optionen für Farben und Größen.
        -   *Keine Auswahl:* Wenn nichts ausgewählt ist, kann das Modul standardmäßig alle Attribute oder keine anzeigen, abhängig von der internen Logik des Moduls. Es ist am besten, explizit auszuwählen.
    -   **Empfohlener Wert:** Wählen Sie alle relevanten Attributgruppen aus, die Ihre Produktkombinationen definieren.
    -   **Händlerszenario / Beispiel:** Wenn Sie T-Shirts in verschiedenen Farben und Größen verkaufen, wählen Sie „Farbe“ und „Größe“. Wenn Sie auch ein Attribut „Material“ haben, es aber nicht in der Liste anzeigen möchten, lassen Sie es unselektiert.

-   **Hook zum Anzeigen des Moduls:**
    -   **Was diese Einstellung bewirkt:** Legt fest, wo auf Ihren Produktlistenseiten die Kombinationsselektoren eingefügt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   `displayProductListFunctionalButtons`: Dieser Hook befindet sich typischerweise in der Nähe des „In den Warenkorb“-Buttons oder anderer funktionaler Elemente auf Produktlistenelementen.
        -   `displayProductListReviews`: Oft in der Nähe von Bewertungssternen oder Bewertungsanzahlen.
        -   `displayProductListPrice`: Normalerweise in der Nähe des Produktpreises.
        -   `displayProductListExtraContent`: Ein allgemeiner Hook für zusätzlichen Inhalt, oft am unteren Rand der Produktkarte.
        -   `displayProductListFooter`: Ganz unten auf der Produktkarte.
    -   **Empfohlener Wert:** `displayProductListFunctionalButtons` oder `displayProductListExtraContent` sind gängige Optionen, dies hängt jedoch stark vom Layout Ihres Themes ab. Möglicherweise müssen Sie experimentieren, um die beste visuelle Platzierung zu finden.
    -   **Händlerszenario / Beispiel:** Wenn Ihr Theme einen sauberen Bereich unter dem Produktnamen und Preis hat, könnte `displayProductListFunctionalButtons` gut passen. Wenn Sie möchten, dass die Optionen prominenter erscheinen, könnte `displayProductListExtraContent` besser sein.

-   **Produkte vom Modul ausschließen:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einzelne Produkte anhand ihrer ID anzugeben, die *keine* Kombinationen in der Produktliste anzeigen sollen, auch wenn das Modul generell aktiviert ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Eingabe von Produkt-IDs (kommagetrennt):* Die angegebenen Produkte kehren in den Produktlisten zum Standard-PrestaShop-Verhalten zurück, wobei ein Klick auf die Produktseite für die Kombinationsauswahl erforderlich ist.
        -   *Leer lassen:* Alle Produkte mit Kombinationen zeigen diese in der Liste an.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Produkte, die einen vollständigen Produktseitenbesuch erfordern.
    -   **Händlerszenario / Beispiel:** Sie könnten einige komplexe Produkte mit vielen Attributen oder Produkte haben, die einen detaillierten Konfigurator erfordern, bei denen Sie es vorziehen, dass Kunden zuerst auf der Produktseite landen.

-   **Kategorien vom Modul ausschließen:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Kategorien anhand ihrer ID anzugeben, die *keine* Kombinationen in ihren Produktlisten anzeigen sollen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Eingabe von Kategorie-IDs (kommagetrennt):* Produkte innerhalb dieser Kategorien zeigen keine Kombinationen auf ihren jeweiligen Listenseiten an.
        -   *Leer lassen:* Alle Kategorien zeigen Produktkombinationen an.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Kategorien, in denen diese Funktion nicht gewünscht ist.
    -   **Händlerszenario / Beispiel:** Wenn Sie eine „Ausverkauf“-Kategorie haben, in der alle Produkte Einzelvarianten sind und Sie die Anzeige sehr minimalistisch halten möchten, könnten Sie diese ausschließen.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Kombinationen in der Produktliste anzeigen | JA | Hauptschalter zum Aktivieren/Deaktivieren der Kombinationsanzeige in Produktlisten. |
| Modulkonfiguration | „In den Warenkorb“-Button anzeigen | JA | Zeigt einen „In den Warenkorb“-Button neben Kombinationen für den direkten Kauf an. |
| Modulkonfiguration | Mengenfeld anzeigen | JA | Ermöglicht Kunden, die Menge direkt in der Produktliste auszuwählen. |
| Modulkonfiguration | Produktreferenz anzeigen | NEIN | Zeigt/verbirgt die Produkt-SKU. |
| Modulkonfiguration | Produkt EAN13/JAN anzeigen | NEIN | Zeigt/verbirgt die Produkt-EAN13/JAN. |
| Modulkonfiguration | Produkt UPC anzeigen | NEIN | Zeigt/verbirgt die Produkt-UPC. |
| Modulkonfiguration | Produktgewicht anzeigen | NEIN | Zeigt/verbirgt das Produktgewicht. |
| Modulkonfiguration | Produktpreis anzeigen | JA | Aktualisiert den Preis dynamisch basierend auf der ausgewählten Kombination. |
| Modulkonfiguration | Produktverfügbarkeit anzeigen | JA | Zeigt den Lagerstatus für die ausgewählte Kombination an. |
| Modulkonfiguration | Produktbeschreibung anzeigen | NEIN | Zeigt/verbirgt die vollständige Produktbeschreibung. |
| Modulkonfiguration | Kurze Produktbeschreibung anzeigen | NEIN | Zeigt/verbirgt die kurze Produktbeschreibung. |
| Modulkonfiguration | Produktbilder anzeigen | JA | Aktualisiert das Produktbild dynamisch basierend auf der ausgewählten Kombination. |
| Modulkonfiguration | Produktattribute anzeigen als | Dropdown, Radio, Farbauswahl | Definiert die visuelle Darstellung der Attributoptionen. |
| Modulkonfiguration | Produktattribute anzeigen für | Relevante Gruppen auswählen | Legt fest, welche Attributgruppen angezeigt werden sollen. |
| Modulkonfiguration | Hook zum Anzeigen des Moduls | `displayProductListFunctionalButtons` | Bestimmt die visuelle Platzierung des Moduls auf Produktkarten. |
| Modulkonfiguration | Produkte vom Modul ausschließen | Leer lassen | Kommagetrennte Produkt-IDs, die von der Funktion ausgeschlossen werden sollen. |
| Modulkonfiguration | Kategorien vom Modul ausschließen | Leer lassen | Kommagetrennte Kategorie-IDs, die von der Funktion ausgeschlossen werden sollen. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul verwendet benutzerdefinierte Admin-Controller für die interne Verwaltung, diese werden jedoch normalerweise nicht direkt vom Händler für die tägliche Konfiguration aufgerufen. Sie dienen hauptsächlich internen Moduloperationen oder der erweiterten Fehlerbehebung.

#### 2.2.1 AdminPlaSearchController (Back Office > Module > Produktlistenattribute (Kombinationen) > Suchkonfiguration)
-   **Bildschirmname & Menüpfad:** Dieser Controller wird wahrscheinlich für die interne Suchkonfiguration oder Datenverwaltung verwendet, die sich darauf bezieht, wie Kombinationen indiziert oder abgerufen werden. Er hat möglicherweise keinen direkten, sichtbaren Menüpunkt für den Händler, oder es könnte ein interner Tab innerhalb der Hauptkonfiguration des Moduls sein.
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm würde typischerweise eine Raster- oder Listenansicht von Daten (z. B. indizierte Produkte, Attributzuordnungen) präsentieren und könnte Aktionen wie „Index neu aufbauen“, „Cache leeren“ oder „Sucheinstellungen bearbeiten“ anbieten.
-   **Auswirkung von Änderungen:** Änderungen hier würden die Leistung oder Genauigkeit der Kombinationsanzeige beeinflussen, insbesondere in großen Katalogen. Falsche Einstellungen könnten dazu führen, dass Kombinationen nicht erscheinen oder langsam geladen werden.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Händler müssen in der Regel nicht mit diesem Bildschirm interagieren, es sei denn, dies wird vom Support empfohlen oder für die erweiterte Fehlerbehebung. Die Hauptkonfigurationsseite des Moduls handhabt alle benutzerorientierten Einstellungen.

#### 2.2.2 index.php (pla/controllers/admin/index.php)
-   **Bildschirmname & Menüpfad:** Diese `index.php`-Datei im `admin`-Controller-Verzeichnis ist eine gängige PrestaShop-Praxis, um die Verzeichnisauflistung zu verhindern. Sie stellt typischerweise keinen benutzerorientierten Bildschirm dar, sondern gewährleistet die Sicherheit und das korrekte Routing für andere Admin-Controller innerhalb des Moduls.
-   **Verfügbare Aktionen & Einstellungen:** Keine direkten händlerorientierten Aktionen oder Einstellungen.
-   **Auswirkung von Änderungen:** Keine direkte Auswirkung auf die Shop-Anzeige oder Daten, da es sich um eine strukturelle Datei handelt.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Keine Interaktion erforderlich.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Kombinationen werden in meiner Produktliste nicht angezeigt. Was soll ich tun?**
A:
1.  **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Produktlistenattribute (Kombinationen)“ und stellen Sie sicher, dass es installiert und aktiviert ist.
2.  **Modulkonfiguration überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls. Stellen Sie sicher, dass „Kombinationen in der Produktliste anzeigen“ auf JA gesetzt ist.
3.  **Attributgruppen überprüfen:** Stellen Sie sicher, dass Sie die richtigen „Produktattribute anzeigen für“-Gruppen (z. B. „Größe“, „Farbe“) ausgewählt haben.
4.  **Ausschlüsse überprüfen:** Vergewissern Sie sich, dass das von Ihnen getestete Produkt oder die Kategorie nicht unter „Produkte vom Modul ausschließen“ oder „Kategorien vom Modul ausschließen“ aufgeführt ist.
5.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Modulinhalte angezeigt werden.
6.  **Theme-Kompatibilität:** Ihr Theme ist möglicherweise stark angepasst und verwendet nicht die Standard-PrestaShop-Hooks. Versuchen Sie, die Einstellung „Hook zum Anzeigen des Moduls“ auf einen anderen Hook zu ändern (z. B. `displayProductListExtraContent`) und leeren Sie den Cache. Wenn die Probleme weiterhin bestehen, wenden Sie sich an Ihren Webmaster oder den MyPresta.eu-Support.

**F: Der „In den Warenkorb“-Button oder das Mengenfeld wird nicht angezeigt.**
A:
1.  **Modulkonfiguration überprüfen:** Stellen Sie sicher, dass „„In den Warenkorb“-Button anzeigen“ und „Mengenfeld anzeigen“ in der Modulkonfiguration beide auf JA gesetzt sind.
2.  **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F: Das Produktbild ändert sich nicht, wenn ich eine andere Kombination auswähle.**
A:
1.  **Modulkonfiguration überprüfen:** Stellen Sie sicher, dass „Produktbilder anzeigen“ auf JA gesetzt ist.
2.  **Produktbilder:** Überprüfen Sie, ob Ihre Produktkombinationen tatsächlich zugehörige Bilder haben. Gehen Sie auf der Back-Office-Seite Ihres Produkts zum Tab „Kombinationen“ und stellen Sie sicher, dass jede Kombination Bilder zugeordnet hat.
3.  **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache.

**F: Das Styling (Farben, Ausrichtung) der Kombinationen sieht in meinem Shop seltsam aus.**
A:
Dies ist normalerweise ein CSS-Konflikt mit Ihrem Theme.
1.  **Cache leeren:** Manchmal hilft das Leeren des Caches.
2.  **Theme-Anpassung:** Ihr Theme hat möglicherweise spezifische Styling-Regeln, die das Standard-CSS des Moduls überschreiben oder damit in Konflikt stehen. Dies erfordert, dass ein Webmaster oder Entwickler das CSS überprüft und Anpassungen im Stylesheet Ihres Themes vornimmt. Das Modul stellt seine eigenen CSS-Dateien bereit, aber Themes können diese immer überschreiben.

**F: Funktioniert dieses Modul mit mehrsprachigen Shops?**
A: Ja, das Modul ist so konzipiert, dass es mit den mehrsprachigen Funktionen von PrestaShop kompatibel ist. Attributnamen und -werte werden in der ausgewählten Front-Office-Sprache angezeigt, vorausgesetzt, sie sind in Ihrem PrestaShop-Back-Office (Katalog > Attribute & Funktionen) korrekt übersetzt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Produktlistenattribute (Kombinationen)“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht
Das Modul folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) und erweitert hauptsächlich `Module` für seine Kernfunktionalität und `ModuleFrontController` für AJAX-Interaktionen. Es nutzt das Hook-System von PrestaShop, um seinen Inhalt in Produktlistenvorlagen einzufügen. Die Hauptlogik des Moduls befindet sich in `index.php` (der Hauptmoduldatei), die die Installation, Deinstallation und die `getContent()`-Methode für die Back-Office-Konfiguration handhabt. Die Front-Office-Anzeige wird über Smarty-Vorlagen verwaltet, die über Hooks gerendert werden, wobei dynamische Interaktionen durch JavaScript und AJAX ermöglicht werden.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller
-   `controllers/front/ajax.php`
    *   **Klassenname & Elternklasse:** `PlaAjaxModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller verarbeitet alle AJAX-Anfragen vom Front Office. Wenn ein Kunde mit den Kombinationsselektoren interagiert (z. B. eine Größe oder Farbe ändert), ist dieser Controller dafür verantwortlich, die Anfrage zu empfangen, zu verarbeiten (z. B. aktualisierte Preise, Lagerbestände, Bilder für die ausgewählte Kombination abzurufen) und eine JSON-Antwort zurückzugeben, um das Frontend dynamisch ohne vollständiges Neuladen der Seite zu aktualisieren. Er ist entscheidend für das interaktive Erlebnis des Moduls.
-   `controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `PlaIndexModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dies ist ein Platzhalter-Front-Controller, der oft verwendet wird, um die Verzeichnisauflistung zu verhindern oder als Fallback für modulspezifische Routen. Im Kontext dieses Moduls hat er möglicherweise keine direkte, aktive Routenführung, dient aber als Standard-PrestaShop-Praxis. Die primäre Front-Office-Interaktion erfolgt über `ajax.php`.

#### Back-Office-Admin-Controller
-   `controllers/admin/AdminPlaSearchController.php`
    *   **Klassenname & Elternklasse:** `AdminPlaSearchController` erweitert `ModuleAdminController`.
    *   **Tab-Name und verwaltete Entität:** Dieser Controller verwaltet wahrscheinlich interne Such- oder Indizierungsmechanismen für Produktkombinationen. Er hat möglicherweise keinen direkten Menüeintrag, könnte aber intern vom Modul für Aufgaben wie den Neuaufbau eines Suchindex für Kombinationen aufgerufen werden. Er würde typischerweise eine virtuelle Entität verwalten, die sich auf Suchdaten bezieht, anstatt ein direktes `ObjectModel`.
-   `controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** Keine direkte Controller-Klasse, sondern eine Standard-`index.php`-Datei.
    *   **Tab-Name und verwaltete Entität:** Diese Datei ist eine Sicherheitsmaßnahme, um die Verzeichnisauflistung des `admin`-Ordners zu verhindern. Sie stellt selbst keinen funktionalen Admin-Bildschirm dar.

### 4.3 Kernklassen & Modelle (`classes/`)
Das Moduldossier weist keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das Modul hauptsächlich durch die Erweiterung bestehender PrestaShop-Kernfunktionen (wie `Product`, `Combination`) und die Verwendung direkter Datenbankabfragen oder der PrestaShop-`Db`-Klasse für die Dateninteraktion arbeitet, anstatt eigene `ObjectModel`-Entitäten zu definieren. Die gesamte Kernlogik ist wahrscheinlich in der Hauptmoduldatei (`pla/index.php`) und ihren Controllern gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)
-   `pla/lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Potenziell sowohl Front-Office (für Live-Suchfunktion, falls integriert) als auch Back-Office (für Admin-Suchfelder). Angesichts des Modulfokus ist es wahrscheinlicher für die Back-Office-Suchkonfiguration im Zusammenhang mit `AdminPlaSearchController`.
    *   **Details:** Handhabt die Autocomplete-Funktionalität, wahrscheinlich zum Suchen von Produkten oder Attributen innerhalb der Admin-Konfiguration des Moduls oder einer benutzerdefinierten Suchfunktion. Es würde an Eingabefelder gebunden, auf `keyup`-Ereignisse lauschen und AJAX-Aufrufe tätigen, um Vorschläge abzurufen.
-   `pla/views/templates/js/pla.js`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Dies ist die Haupt-JavaScript-Datei für die Front-Office-Funktionalität.
        *   **Event-Listener:** Bindet `change`-Ereignisse an Kombinationsselektoren (Dropdowns, Radio-Buttons, Farbauswahlen) auf Produktlistenelementen.
        *   **DOM-Manipulation:** Aktualisiert Produktpreise, Lagerstatus, Produktbilder und den Status des „In den Warenkorb“-Buttons basierend auf ausgewählten Kombinationen.
        *   **AJAX-Aufrufe:** Führt AJAX-Anfragen an `controllers/front/ajax.php` aus, um aktualisierte Kombinationsdaten (Preis, Lagerbestand, Bild-URL usw.) abzurufen, wenn sich eine Auswahl ändert.
        *   **Modulinitialisierung:** Enthält wahrscheinlich Code zur Initialisierung der Kombinationsselektoren beim Laden der Seite und zur erneuten Initialisierung nach AJAX-Updates (z. B. Infinite Scroll, Kategoriefilterung).

### 4.5 CSS-Stylesheets (`views/css/`)
-   `pla/css.css`
    *   **Geltungsbereich:** Wahrscheinlich Front-Office.
    *   **Details:** Allgemeine Stilgebung für die Kombinationsanzeigeelemente in Produktlisten. Enthält Basisstile für Dropdowns, Radio-Buttons, Mengenfelder und „In den Warenkorb“-Buttons, wie sie vom Modul gerendert werden.
-   `pla/lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Potenziell sowohl Front-Office als auch Back-Office.
    *   **Details:** Stile für die Autocomplete-Vorschlagsliste und Eingabefelder, wahrscheinlich in Verbindung mit `autocomplete.js` verwendet.
-   `pla/views/templates/css/pla-classic.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Spezifische Stilgebung, die auf ältere PrestaShop-Themes zugeschnitten ist (z. B. Classic-Theme oder ähnliche Strukturen). Könnte explizitere Überschreibungen oder Fallback-Stile enthalten.
-   `pla/views/templates/css/pla.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Primäre Stilgebung für die Front-Office-Elemente des Moduls, potenziell für neuere PrestaShop-Versionen oder einen generischeren Ansatz. Enthält Stile für die Kombinations-Wrapper, Attributoptionen und dynamische Elemente.
    *   **Wichtige CSS-Klassenselektoren:** Entwickler können Klassen wie `.pla-combinations-wrapper`, `.pla-attribute-group`, `.pla-attribute-option`, `.pla-add-to-cart-btn`, `.pla-quantity-input`, `.pla-price-display`, `.pla-availability-status` erwarten und diese in der `custom.css` oder `theme.css` ihres Themes überschreiben.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)
-   `pla/views/templates/hook/pla.tpl`
    *   **Hook:** Hauptsächlich für Hooks wie `displayProductListFunctionalButtons`, `displayProductListExtraContent` usw. vorgesehen.
    *   **Ausgabe:** Dies ist die Hauptvorlage, die für das Rendern der Kombinationsselektoren, des „In den Warenkorb“-Buttons, des Mengenfelds, des Preises und der Verfügbarkeit für jedes Produktelement in der Produktliste verantwortlich ist. Sie iteriert durch verfügbare Attributgruppen und -werte und generiert den entsprechenden HTML-Code (Dropdowns, Radio-Buttons, Farbfelder) basierend auf der Modulkonfiguration.

#### Admin-Vorlagen (`views/templates/admin/`)
-   `pla/views/templates/admin/admin.tpl`
    *   **Zweck:** Diese Vorlage wird für die Hauptkonfigurationsseite des Moduls im PrestaShop-Back-Office verwendet (Zugriff über `getContent()` in `pla/index.php`). Sie enthält die Formulare für alle in Abschnitt 4.1 beschriebenen Einstellungen.
-   `pla/views/templates/admin/selectedCa.tpl`
    *   **Zweck:** Wahrscheinlich eine Teilvorlage, die innerhalb eines Admin-Formulars oder Rasters verwendet wird, um ausgewählte Kategorien anzuzeigen (z. B. für die Einstellung „Kategorien vom Modul ausschließen“). Sie würde eine Liste der ausgewählten Kategorien rendern, möglicherweise mit Optionen zum Entfernen.
-   `pla/views/templates/admin/selectedProducts.tpl`
    *   **Zweck:** Ähnlich wie `selectedCa.tpl`, aber für ausgewählte Produkte (z. B. für die Einstellung „Produkte vom Modul ausschließen“). Sie würde eine Liste der ausgewählten Produkte anzeigen.

#### JavaScript-Vorlagen (`views/templates/js/`)
-   `pla/views/templates/js/pla_admin.tpl`
    *   **Geltungsbereich:** Back-Office.
    *   **Ausgabe:** Diese Vorlage enthält wahrscheinlich JavaScript-Code speziell für das Admin-Panel. Sie könnte Skripte für die Handhabung dynamischer Formularelemente, AJAX-Aufrufe innerhalb des Admin-Bereichs oder die Initialisierung von Komponenten auf der Konfigurationsseite des Moduls enthalten.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen
Das Moduldossier weist keine benutzerdefinierten SQL-Dateien auf. Dies impliziert, dass das Modul seine Konfigurationseinstellungen hauptsächlich in der PrestaShop-Tabelle `ps_configuration` speichert.
-   **`ps_configuration`**: Speichert Moduleinstellungen (z. B. `PLA_DISPLAY_COMBINATIONS`, `PLA_DISPLAY_ADD_TO_CART`, `PLA_EXCLUDE_PRODUCTS`, `PLA_HOOK_NAME` usw.). Diese Schlüssel sind typischerweise mit `PLA_` oder `MYPRESTA_PLA_` präfixiert.

#### Registrierte Hooks-Tabelle
Das Modul registriert und nutzt mehrere PrestaShop-Hooks, um seine Funktionalität zu integrieren.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Zum Einbinden notwendiger CSS- und JavaScript-Dateien für die Front-Office-Funktionalität des Moduls. |
| `displayProductListFunctionalButtons` | Innerhalb jedes Produktelements auf Produktlistenseiten, typischerweise in der Nähe von Aktionsbuttons. | Ein gängiger Hook zum Einfügen der Kombinationsselektoren und des „In den Warenkorb“-Buttons. |
| `displayProductListReviews` | Innerhalb jedes Produktelements auf Produktlistenseiten, oft in der Nähe von Bewertungselementen. | Alternativer Hook zum Anzeigen von Kombinationsoptionen. |
| `displayProductListPrice` | Innerhalb jedes Produktelements auf Produktlistenseiten, in der Nähe des Produktpreises. | Alternativer Hook zum Anzeigen von Kombinationsoptionen. |
| `displayProductListExtraContent` | Ein allgemeiner Hook innerhalb jedes Produktelements für zusätzlichen Inhalt. | Flexibler Hook zum Einfügen der Kombinationsselektoren, oft am unteren Rand der Produktkarte. |
| `displayProductListFooter` | Ganz unten auf jedem Produktelement auf Produktlistenseiten. | Ein weiterer alternativer Hook zum Anzeigen von Kombinationsoptionen. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seinen Inhalt rendert, ermöglicht Modulen das Hinzufügen von Assets. | Um spezifische JS/CSS-Assets nur bei Bedarf durch das Modul auf relevanten Seiten bedingt zu laden. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Potenziell verwendet, um modulspezifische Caches zu leeren oder Produktdaten neu zu indizieren, wenn das Modul einen internen Indizierungsmechanismus hat. |
| `actionAttributeGroupUpdate` / `actionAttributeUpdate` | Nach der Aktualisierung von Attributgruppen oder Attributen. | Ähnlich wie `actionProductUpdate`, zum Leeren des Caches oder zur Neuindizierung. |

## 5. Offizieller Support & Updates
Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, Unterstützung zu leisten und den reibungslosen Betrieb Ihres Moduls zu gewährleisten.
