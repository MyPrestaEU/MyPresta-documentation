---
title: "Produkte nach Land ausblenden – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produkte nach Land ausblenden“ von MyPresta.eu."
sidebar:
  label: "Produkte nach Land ausblenden – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Hide products by country auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/hide-products-by-country.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/hide-products-by-country/)
>
> ---


# Produkte nach Land ausblenden

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Sie können auf die Modulkonfiguration zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Produkte nach Land ausblenden“ suchen und dann auf „Konfigurieren“ klicken.

#### Allgemeine Einstellungen

-   **Aktiviert / Deaktiviert (Schalter)**

    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul filtert Produkte aktiv basierend auf Ihren Einstellungen.
        -   *Wenn deaktiviert:* Das Modul stoppt das Filtern von Produkten, und alle Produkte sind für alle Kunden unabhängig vom Land sichtbar.
    -   **Empfohlener Wert:** **Aktiviert**, sobald Sie Ihre Regeln konfiguriert haben.
    -   **Händlerszenario / Beispiel:** Sie richten das Modul zum ersten Mal ein und möchten es testen, bevor Sie es live schalten, daher lassen Sie es deaktiviert. Sobald es bereit ist, aktivieren Sie es.
-   **Was möchten Sie tun? (Dropdown)**

    -   **Was diese Einstellung bewirkt:** Definiert die Kernlogik Ihrer Produkt-Ausblendungsregeln.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Produkte für ausgewählte Länder ausblenden:* Produkte, die in den Abschnitten „Kategorien auswählen“ und „Hersteller auswählen“ ausgewählt wurden, werden Kunden in der Liste „Länder auswählen“ ausgeblendet. Dies ist der häufigste Anwendungsfall.
        -   *Produkte nur für ausgewählte Länder anzeigen:* Ausgewählte Produkte sind NUR für Kunden in der Liste „Länder auswählen“ sichtbar. Für alle anderen Länder werden diese Produkte ausgeblendet.
    -   **Empfohlener Wert:** Normalerweise **Produkte für ausgewählte Länder ausblenden**.
    -   **Händlerszenario / Beispiel:**
        -   *Produkte ausblenden:* Sie verkaufen eine bestimmte Marke, die nicht in Deutschland verkauft werden darf. Sie wählen „Produkte für ausgewählte Länder ausblenden“, wählen die Marke und wählen Deutschland aus.
        -   *Produkte nur anzeigen:* Sie haben eine spezielle Kollektion von Produkten exklusiv für den US-Markt. Sie wählen „Produkte nur für ausgewählte Länder anzeigen“, wählen die Kollektion und wählen die Vereinigten Staaten aus.
-   **Länder auswählen (Mehrfachauswahl-Liste)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der spezifischen Länder, auf die Ihre Regel „Was möchten Sie tun?“ angewendet wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die als aus diesen ausgewählten Ländern stammend identifiziert wurden, sind von den von Ihnen festgelegten Produkt-Sichtbarkeitsregeln betroffen.
    -   **Empfohlener Wert:** Wählen Sie alle relevanten Länder für Ihre Regeln aus.
    -   **Händlerszenario / Beispiel:** Wenn Sie Produkte für Kunden in Frankreich und Spanien ausblenden, würden Sie „Frankreich“ und „Spanien“ aus dieser Liste auswählen.
-   **Kategorien auswählen (Kategoriebaum)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl spezifischer Produktkategorien, deren Produkte der Ausblendungs-/Anzeigeregel unterliegen.
    -   **Auswirkung der Änderung dieser Einstellung:** Alle Produkte innerhalb der ausgewählten Kategorien (und deren Unterkategorien, wenn Sie diese einschließen möchten) werden von der Regel „Was möchten Sie tun?“ betroffen.
    -   **Empfohlener Wert:** Wählen Sie die Kategorien aus, die die Produkte enthalten, die Sie steuern möchten.
    -   **Händlerszenario / Beispiel:** Sie möchten alle Produkte in Ihrer Kategorie „Elektronik“ für Kunden in Kanada ausblenden. Sie würden hier „Elektronik“ auswählen.
-   **Hersteller auswählen (Mehrfachauswahl-Liste)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl spezifischer Hersteller, deren Produkte der Ausblendungs-/Anzeigeregel unterliegen.
    -   **Auswirkung der Änderung dieser Einstellung:** Alle Produkte der ausgewählten Hersteller werden von der Regel „Was möchten Sie tun?“ betroffen.
    -   **Empfohlener Wert:** Wählen Sie die Hersteller aus, deren Produkte Sie steuern möchten.
    -   **Händlerszenario / Beispiel:** Sie haben eine Vertriebsvereinbarung, die Sie daran hindert, Produkte der „Marke X“ in Australien zu verkaufen. Sie würden hier „Marke X“ auswählen.
-   **Kundengruppen ausschließen (Mehrfachauswahl-Liste)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bestimmte Kundengruppen von den Produkt-Ausblendungsregeln des Moduls auszunehmen.
    -   **Auswirkung der Änderung dieser Einstellung:** Kunden, die zu den ausgewählten Gruppen gehören, sehen immer alle Produkte, unabhängig von ihrem Land oder den Moduleinstellungen. Dies ist nützlich für B2B-Partner oder VIPs.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Kundengruppen, die die Regeln umgehen müssen.
    -   **Händlerszenario / Beispiel:** Sie haben eine Kundengruppe „Großhändler“, die immer Ihren vollständigen Katalog sehen sollte, auch wenn einige Produkte für normale Kunden in ihrem Land eingeschränkt sind. Sie würden hier „Großhändler“ auswählen.
-   **Kunden ausschließen (Suchfeld)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einzelne Kunden von den Produkt-Ausblendungsregeln des Moduls auszunehmen.
    -   **Auswirkung der Änderung dieser Einstellung:** Spezifische Kunden, die Sie auswählen, sehen immer alle Produkte, unabhängig von ihrem Land oder den Moduleinstellungen.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische einzelne Kunden, die die Regeln umgehen müssen.
    -   **Händlerszenario / Beispiel:** Ein bestimmter Key Account Manager muss alle Produkte für einen Kunden sehen, auch wenn dieser aus einem eingeschränkten Land browsen. Sie würden diesen Kunden hier suchen und auswählen.

#### Geolocation & Simulations-Einstellungen

-   **Priorität der Herkunftsidentifikationsmethoden festlegen (Drag & Drop-Liste)**

    -   **Was diese Einstellung bewirkt:** Bestimmt die Reihenfolge, in der das Modul versucht, das Land eines Kunden zu identifizieren. Dies ist entscheidend, da verschiedene Methoden manchmal unterschiedliche Ergebnisse liefern können.
    -   **Auswirkung der Änderung dieser Einstellung:** Das Modul versucht die Methoden von oben nach unten. Die erste erfolgreiche Identifizierung wird verwendet.
        -   *Lieferadresse:* Verwendet das Land aus der ausgewählten Lieferadresse des Kunden (erfordert, dass der Kunde angemeldet ist und eine Adresse hat).
        -   *IP-Adresse (Geolocation):* Verwendet die IP-Adresse des Kunden, um dessen Land zu bestimmen (am häufigsten für Gäste).
        -   *Browsersprache:* Leitet das Land aus den Browserspracheinstellungen des Kunden ab (weniger zuverlässig für präzise Länderidentifikation).
    -   **Empfohlener Wert:**
        1.  Lieferadresse (wenn die Adresse des angemeldeten Kunden am wichtigsten ist)
        2.  IP-Adresse (für allgemeine Genauigkeit für alle Besucher)
        3.  Browsersprache (als Fallback, weniger präzise)
    -   **Händlerszenario / Beispiel:** Sie möchten die tatsächliche Lieferadresse des Kunden priorisieren, wenn dieser angemeldet ist, da dies die genaueste Angabe für den Versand ist. Für Gäste möchten Sie sich auf die IP-Geolocation verlassen. Sie würden „Lieferadresse“ nach oben ziehen, dann „IP-Adresse“.
-   **Lieferadresse verwenden (Schalter)**

    -   **Was diese Einstellung bewirkt:** Steuert, ob das Modul das Land der gewählten Lieferadresse des Kunden für die Produktfilterung berücksichtigt.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Wenn ein Kunde angemeldet ist und eine Lieferadresse ausgewählt hat, verwendet das Modul das Land dieser Adresse, um die Produktsichtbarkeit zu bestimmen.
        -   *Wenn deaktiviert:* Das Modul ignoriert die Lieferadresse und verlässt sich auf andere Methoden (wie die IP-Adresse), auch für angemeldete Kunden.
    -   **Empfohlener Wert:** **Aktiviert** für angemeldete Kunden, da die Lieferadresse oft der genaueste Indikator dafür ist, wohin das Produkt gehen soll.
    -   **Händlerszenario / Beispiel:** Ein Kunde aus den USA browsen von Kanada aus. Wenn „Lieferadresse verwenden“ aktiviert ist und er eine US-Lieferadresse ausgewählt hat, sieht er Produkte, die in den USA verfügbar sind. Wenn deaktiviert, sieht er möglicherweise Produkte, die in Kanada verfügbar sind (basierend auf seiner IP).
-   **Whitelist aktivieren (Schalter)**

    -   **Was diese Einstellung bewirkt:** Diese Einstellung arbeitet in Verbindung mit der integrierten Geolocation-Funktion von PrestaShop (zu finden unter **Shop-Parameter > Allgemein > Geolocation**). Wenn die Geolocation von PrestaShop aktiviert ist, kann dieses Modul deren Whitelist verwenden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Wenn die native Geolocation von PrestaShop aktiv und mit einer Whitelist (Länder, die browsen dürfen) konfiguriert ist, respektiert dieses Modul diese Whitelist. Besucher aus Ländern, die *nicht* auf der PrestaShop-Whitelist stehen, könnten blockiert oder umgeleitet werden, bevor dieses Modul seine Regeln anwendet.
        -   *Wenn deaktiviert:* Dieses Modul ignoriert die Geolocation-Whitelist von PrestaShop und wendet seine Regeln basierend auf seiner eigenen Länderidentifikation an.
    -   **Empfohlener Wert:** **Deaktiviert**, es sei denn, Sie verwenden und verwalten aktiv die native Geolocation-Whitelist von PrestaShop.
    -   **Händlerszenario / Beispiel:** Sie haben die Geolocation von PrestaShop so eingerichtet, dass nur Besucher aus EU-Ländern zugelassen sind. Wenn Sie hier „Whitelist aktivieren“ aktivieren, werden Besucher von außerhalb der EU vom PrestaShop-Kernsystem behandelt, und dieses Modul wendet dann seine produktspezifischen Regeln auf die zugelassenen EU-Besucher an.
-   **Besuch simulieren (Schalter)**

    -   **Was diese Einstellung bewirkt:** Dies ist ein leistungsstarkes Testwerkzeug, mit dem Sie so tun können, als würden Sie aus einem anderen Land browsen, ohne tatsächlich Ihren Standort zu ändern oder ein VPN zu verwenden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Feld „IP simulieren“ wird aktiv, sodass Sie eine IP-Adresse eingeben können. Das Modul behandelt dann Ihre aktuelle Browsing-Sitzung so, als würden Sie aus dem mit dieser IP verbundenen Land besuchen.
        -   *Wenn deaktiviert:* Das Modul identifiziert Ihr Land normal.
    -   **Empfohlener Wert:** **Deaktiviert** für Live-Shops. Nur vorübergehend zum Testen aktivieren.
    -   **Händlerszenario / Beispiel:** Sie möchten überprüfen, ob Produkte für Kunden in Deutschland korrekt ausgeblendet werden. Sie aktivieren „Besuch simulieren“, geben eine deutsche IP-Adresse ein (z. B. 85.214.132.112) und browsen dann Ihren Shop, um zu sehen, ob die richtigen Produkte ausgeblendet werden.
-   **IP simulieren (Texteingabe)**

    -   **Was diese Einstellung bewirkt:** Wenn „Besuch simulieren“ aktiviert ist, geben Sie hier eine IP-Adresse ein, um einen Besucher aus dem Land dieser IP zu simulieren.
    -   **Auswirkung der Änderung dieser Einstellung:** Ihre aktuelle Browsing-Sitzung verhält sich so, als befänden Sie sich in dem Land, das mit der eingegebenen IP-Adresse verbunden ist, sodass Sie die Regeln zur Produktsichtbarkeit testen können.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, „Besuch simulieren“ ist zum Testen aktiviert.
    -   **Händlerszenario / Beispiel:** Nach dem Aktivieren von „Besuch simulieren“ geben Sie „192.168.1.1“ ein (eine gängige lokale IP, aber Sie würden eine echte öffentliche IP für ein Land verwenden), um zu testen. Für eine deutsche IP könnten Sie „85.214.132.112“ verwenden.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Aktiviert** | Aktiviert | Hauptschalter für die Modulfunktionalität. |
| Modulkonfiguration | **Was möchten Sie tun?** | Produkte für ausgewählte Länder ausblenden | Definiert, ob Produkte für ausgewählte Länder ausgeblendet oder nur für diese angezeigt werden. |
| Modulkonfiguration | **Länder auswählen** | (Leer) / Relevant auswählen | Länder, die von der Produktsichtbarkeitsregel betroffen sind. |
| Modulkonfiguration | **Kategorien auswählen** | (Leer) / Relevant auswählen | Kategorien, deren Produkte betroffen sind. |
| Modulkonfiguration | **Hersteller auswählen** | (Leer) / Relevant auswählen | Hersteller, deren Produkte betroffen sind. |
| Modulkonfiguration | **Kundengruppen ausschließen** | (Leer) | Kundengruppen, die von den Ausblendungsregeln ausgenommen sind. |
| Modulkonfiguration | **Kunden ausschließen** | (Leer) | Einzelne Kunden, die von den Ausblendungsregeln ausgenommen sind. |
| Modulkonfiguration | **Priorität der Herkunftsidentifikationsmethoden festlegen** | Lieferadresse, IP-Adresse, Browsersprache | Reihenfolge der Methoden zur Identifizierung des Kundenlandes. |
| Modulkonfiguration | **Lieferadresse verwenden** | Aktiviert | Verwenden Sie das Land der Lieferadresse des Kunden zur Filterung. |
| Modulkonfiguration | **Whitelist aktivieren** | Deaktiviert | Respektiert die native Geolocation-Whitelist von PrestaShop. |
| Modulkonfiguration | **Besuch simulieren** | Deaktiviert | Aktivieren, um die Produktsichtbarkeit von einer bestimmten IP aus zu testen. |
| Modulkonfiguration | **IP simulieren** | (Leer) | IP-Adresse zur Simulation, wenn „Besuch simulieren“ aktiviert ist. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber die Produkte sind immer noch falsch sichtbar/ausgeblendet. Was sollte ich zuerst überprüfen?**
A:

1.  **Modul aktiviert:** Überprüfen Sie nochmals, ob der Hauptschalter „Aktiviert“ auf der Modulkonfigurationsseite eingeschaltet ist.
2.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“). Der Browser-Cache kann manchmal auch stören, versuchen Sie daher einen Hard-Refresh (Strg+F5 oder Cmd+Shift+R) oder ein Inkognito-/privates Browserfenster.
3.  **Simulation:** Wenn Sie testen, stellen Sie sicher, dass „Besuch simulieren“ aktiviert und „IP simulieren“ korrekt eingestellt ist. Wenn Sie nicht simulieren, stellen Sie sicher, dass „Besuch simulieren“ deaktiviert ist.
4.  **Regellogik:** Überprüfen Sie Ihre Einstellung „Was möchten Sie tun?“ („Produkte für ausgewählte Länder ausblenden“ vs. „Produkte nur für ausgewählte Länder anzeigen“) und stellen Sie sicher, dass sie Ihrer Absicht entspricht.
5.  **Land-/Kategorie-/Hersteller-Auswahl:** Stellen Sie sicher, dass Sie die Länder, Kategorien und Hersteller, die betroffen sein sollen, korrekt ausgewählt haben.

**F: Wie identifiziert das Modul das Land eines Kunden?**
A: Das Modul verwendet ein von Ihnen konfiguriertes Prioritätssystem:

1.  **Lieferadresse:** Wenn der Kunde angemeldet ist und eine Lieferadresse hat, ist dies am genauesten.
2.  **IP-Adresse (Geolocation):** Für Gäste oder wenn keine Lieferadresse verwendet wird, wird die IP-Adresse des Besuchers verwendet, um dessen Land zu bestimmen.
3.  **Browsersprache:** Als Fallback kann das Land aus den Spracheinstellungen des Browsers abgeleitet werden, dies ist jedoch weniger präzise. Sie können die Priorität in den Moduleinstellungen anpassen.

**F: Beeinflusst dieses Modul meine SEO? Wird Google meine ausgeblendeten Produkte weiterhin indexieren?**
A: Das Modul blendet Produkte für bestimmte Länder aus der Front-Office-Anzeige aus. Im Allgemeinen crawlen Suchmaschinen-Crawler (wie Googlebot) oft von spezifischen IP-Adressen (z. B. US-basierte IPs). Wenn Ihre Produkte für die USA ausgeblendet sind, sieht Google sie möglicherweise nicht. Wenn sie für andere Länder ausgeblendet, aber für die USA sichtbar sind, könnte Google sie dennoch indexieren. Bei kritischen SEO-Bedenken sollten Sie die native PrestaShop-Funktion „Produkt deaktivieren“ oder spezifische `robots.txt`-Regeln verwenden, wenn Sie ein Produkt absolut nirgendwo indexiert haben möchten. Dieses Modul dient hauptsächlich der Front-End-Benutzererfahrung und der Compliance, nicht der SEO-Kontrolle.

**F: Kann ich Produkte für bestimmte Kunden oder Kundengruppen ausblenden, unabhängig von ihrem Land?**
A: Ja! Das Modul enthält die Einstellungen „Kundengruppen ausschließen“ und „Kunden ausschließen“. Diese ermöglichen es Ihnen, Gruppen oder einzelne Kunden festzulegen, die *immer* alle Produkte sehen, wodurch die länderbasierten Ausblendungsregeln effektiv umgangen werden. Dies ist nützlich für VIPs, B2B-Partner oder internes Personal.

**F: Was passiert, wenn ein Kunde aus einem eingeschränkten Land versucht, über einen direkten Link auf ein ausgeblendetes Produkt zuzugreifen?**
A: Das Modul ist so konzipiert, dass es den Zugriff verhindert. Typischerweise werden sie auf die Homepage oder eine „Seite nicht gefunden“-Fehlermeldung umgeleitet, um sicherzustellen, dass sie das eingeschränkte Produkt nicht anzeigen oder in den Warenkorb legen können.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Produkte nach Land ausblenden“ (`hbc`) arbeitet hauptsächlich durch das Überschreiben von PrestaShop-Kernklassen und die Nutzung von Hooks, um Produktanfragen abzufangen und zu modifizieren, bevor sie dem Kunden angezeigt werden. Es nutzt PrestaShops `ObjectModel` zur Konfigurationsspeicherung und stützt sich auf IP-Geolocation oder Kundendaten, um das Land des Besuchers zu bestimmen. Die Modullogik wird in den Produktfilterprozess injiziert, um sicherzustellen, dass eingeschränkte Produkte aus Listen, Suchergebnissen und direkten Zugriffsversuchen entfernt werden.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine dedizierten Front-Office- oder Back-Office-Admin-Controller. Seine Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul implementiert Überschreibungen, um das Kernverhalten von PrestaShop zu modifizieren.

-   **`hbc/override/classes/index.php`**: Standardmäßige leere `index.php`-Datei, um die Verzeichnisauflistung zu verhindern.
-   **`hbc/override/classes/shop/index.php`**: Standardmäßige leere `index.php`-Datei, um die Verzeichnisauflistung zu verhindern.
-   **`hbc/override/classes/shop/Shop.php`**:
    -   **Klassenname**: `Shop` (überschreibt die PrestaShop-Kernklasse `Shop`)
    -   **Elternklasse**: `ShopCore`
    -   **Verantwortlichkeit**: Diese Überschreibung ist entscheidend. Sie modifiziert wahrscheinlich, wie der Produktkontext oder der Shop-Kontext bestimmt wird, indem sie möglicherweise länderspezifische Filterlogik auf einer sehr grundlegenden Ebene des PrestaShop-Multi-Shop- und Produktabrufsystems injiziert. Dies stellt sicher, dass die Regeln zur Produktsichtbarkeit konsistent in verschiedenen Teilen des Shops angewendet werden. Entwickler sollten sich bewusst sein, dass das Überschreiben von `Shop.php` weitreichende Auswirkungen haben und mit anderen Modulen kollidieren kann, die ebenfalls diese Kernklasse überschreiben.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`hbc/lib/searchTool/views/js/autocomplete.js`**:
    -   **Geltungsbereich**: Back-Office (wahrscheinlich im Konfigurationsformular des Moduls verwendet).
    -   **Zweck**: Dieses Skript bietet eine Autocomplete-Funktionalität, speziell für das Eingabefeld „Kunden ausschließen“ in der Modulkonfiguration. Es führt wahrscheinlich AJAX-Aufrufe an einen PrestaShop-Admin-Endpunkt durch, um Kunden zu suchen, während der Administrator tippt, was die Benutzerfreundlichkeit bei der Auswahl einzelner Kunden verbessert.
    -   **Hauptfunktionalität**:
        -   Initialisiert ein Autocomplete-Widget auf einem spezifischen Eingabefeld (z. B. `#hbc_exclude_customer`).
        -   Sendet AJAX-Anfragen (z. B. an `admin-ajax.php` oder einen dedizierten Admin-Controller) mit der eingegebenen Abfrage.
        -   Parst JSON-Antworten, die Kundendaten (ID, Name, E-Mail) enthalten.
        -   Zeigt Vorschläge in einer Dropdown-Liste an.
        -   Verarbeitet die Auswahl eines Kunden, füllt ein verstecktes Eingabefeld mit der Kunden-ID und zeigt den Namen an.
        -   Verwaltet das Entfernen ausgewählter Kunden aus der Liste.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`hbc/lib/searchTool/views/css/autocomplete.css`**:
    -   **Geltungsbereich**: Back-Office (gestaltet das Autocomplete-Widget).
    -   **Zweck**: Bietet Styling für das Autocomplete-Suchwerkzeug für Kunden, das in der Modulkonfiguration verwendet wird. Dies umfasst das Styling für das Eingabefeld, die Dropdown-Liste der Vorschläge und möglicherweise die Anzeige ausgewählter Tags/Tokens.
    -   **Hauptselektoren**: Zielt wahrscheinlich auf Klassen und IDs ab, die mit dem Autocomplete-Widget verbunden sind, wie `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item` und Elemente zur Anzeige ausgewählter Tags/Tokens.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`hbc/lib/searchTool/views/scripts.tpl`**:

    -   **Geltungsbereich**: Back-Office.
    -   **Zweck**: Dieses Template enthält wahrscheinlich die notwendigen JavaScript- und CSS-Dateien für das Autocomplete-Suchwerkzeug (`autocomplete.js` und `autocomplete.css`) und initialisiert möglicherweise die JavaScript-Logik. Es ist wahrscheinlich im Hauptkonfigurationstemplate enthalten.
-   **`hbc/views/templates/admin/AdminTab.tpl`**:

    -   **Geltungsbereich**: Back-Office.
    -   **Zweck**: Dieses Template ist wahrscheinlich ein generischer Wrapper oder eine Komponente, die innerhalb der Konfigurationsseite des Moduls verwendet wird. Es könnte die Struktur für eine Registerkartenoberfläche oder einen spezifischen Abschnitt innerhalb der Moduleinstellungen definieren.
-   **`hbc/views/templates/admin/button-subcategories.tpl`**:

    -   **Geltungsbereich**: Back-Office.
    -   **Zweck**: Dieses Template rendert wahrscheinlich einen Button oder ein UI-Element im Zusammenhang mit der Kategorieauswahl, speziell zum Ein- / Ausschließen von Unterkategorien bei der Auswahl von Oberkategorien im Konfigurationsformular.
-   **`hbc/views/templates/admin/configuration.tpl`**:

    -   **Geltungsbereich**: Back-Office.
    -   **Zweck**: Dies ist das Haupt-Smarty-Template für die Konfigurationsseite des Moduls. Es rendert alle Einstellungen, Eingabefelder, Schalter und Listen, die in Abschnitt 4.1 beschrieben sind. Es verwendet PrestaShops Hilfsformular-Komponenten und enthält wahrscheinlich `scripts.tpl` für die Autocomplete-Funktionalität.
-   **`hbc/views/templates/hook/displayHeader.tpl`**:

    -   **Geltungsbereich**: Front-Office.
    -   **Hook**: `displayHeader`
    -   **Zweck**: Dieses Template wird im `<head>`-Bereich jeder Front-Office-Seite gerendert. Es könnte verwendet werden, um:
        -   Inline-JavaScript für die clientseitige Ländererkennung zu injizieren (weniger wahrscheinlich angesichts der serverseitigen Filterung).
        -   JavaScript-Variablen basierend auf der Modulkonfiguration festzulegen (z. B. Simulationsmodus).
        -   Zusätzliche CSS- oder JS-Dateien einzubinden, die global für die Front-Office-Funktionalität des Moduls benötigt werden (obwohl die Kernfilterung serverseitig erfolgt).
        -   Möglicherweise Weiterleitungen oder erste Prüfungen basierend auf der Geolocation zu handhaben, bevor die Seite vollständig geladen wird.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul verwendet hauptsächlich die PrestaShop-Tabelle `ps_configuration`, um seine Einstellungen zu speichern.
    -   Konfigurationsschlüssel umfassen: `HBC_EXCLUDE_GROUP`, `HBC_EXCLUDE_CUSTOMER`, `HBC_SIMULATE_ON`, `HBC_SIMULATE_IP`, `HBC_DELIVERY`, `HBC_WHITELIST_ON`, `HBC_COUNTRY`, `HBC_WTD`, `HBC_MANUFACT`, `HBC_CATEGORIES`, `HBC_PRIORITY`.
    -   Es werden keine benutzerdefinierten SQL-Tabellen von diesem Modul erstellt.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Im `<head>`-Bereich jeder Seite. | Potenziell zum Injizieren von clientseitigen Skripten, Meta-Tags oder ersten Prüfungen. |
| `actionAdminControllerSetMedia` | Back-Office | Wenn ein Admin-Controller seine Medien-Assets festlegt. | Wird verwendet, um CSS/JS für die Konfigurationsseite des Moduls zu laden (z. B. `autocomplete.js`, `autocomplete.css`). |
| `actionDispatcherAfter` | Front-Office | Nachdem der Dispatcher die Anfrage verarbeitet hat. | Könnte verwendet werden, um Weiterleitungen oder abschließende Prüfungen durchzuführen, nachdem eine Seite identifiziert wurde, aber vor dem Rendern. |
| `displayFilterProductSearch` | Front-Office | Während der Produktfiltersuche. | **KRITISCH**: Dieser Hook wird verwendet, um die Modullogik in die Produktsuchabfrage zu injizieren, um sicherzustellen, dass ausgeblendete Produkte aus den Suchergebnissen ausgeschlossen werden. |
| `actionProductUpdate` | Back-Office | Nachdem ein Produkt im Back Office aktualisiert wurde. | Könnte verwendet werden, um den Cache bezüglich der Produktsichtbarkeit zu leeren oder Regeln für das aktualisierte Produkt neu zu bewerten. |
| `displayAdminProductsExtra` | Back-Office | Auf der Produktbearbeitungsseite im Back Office. | Könnte verwendet werden, um zusätzliche Informationen oder Einstellungen zur Produktausblendung für das spezifische bearbeitete Produkt anzuzeigen (obwohl nicht explizit in den Einstellungen identifiziert). |
| `actionCartSave` | Front-Office | Wenn der Warenkorb gespeichert wird (z. B. Produkt hinzugefügt/entfernt). | Könnte verwendet werden, um das Hinzufügen ausgeblendeter Produkte zum Warenkorb zu verhindern oder sie zu entfernen, wenn sich das Land des Kunden ändert. |
| `FilterProductSearch` | Front-Office | Während der Produktfiltersuche (ähnlich wie `displayFilterProductSearch`). | **KRITISCH**: Ein weiterer Hook zum Modifizieren von Produktsuchabfragen, um eine umfassende Filterung über verschiedene Suchkontexte hinweg zu gewährleisten. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produkte nach Land ausblenden“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
