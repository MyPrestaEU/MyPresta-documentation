---
title: "Preise nach Land erhöhen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Preise nach Land erhöhen“ von MyPresta.eu."
sidebar:
  label: "Preise nach Land erhöhen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Increase prices by country auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/increase-prices-by-country.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/increase-prices-by-country/)
>
> ---


# Preise nach Land erhöhen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Das Modul basiert auf der Kernfunktionalität von PrestaShop und Standard-Serverkonfigurationen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager zugänglich ist.

**Erkannte Einstellungen & Optionen: Standard-Moduleinstellungen**
Dieser Bildschirm enthält typischerweise allgemeine Einstellungen für das Modul, wie das Aktivieren/Deaktivieren des Moduls oder globale Präferenzen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält normalerweise einen globalen Schalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls. Er könnte auch allgemeine Präferenzen enthalten, die beeinflussen, wie die Preisanpassungen in Ihrem Shop angewendet werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul passt die Preise aktiv basierend auf den Regeln an, die Sie im speziellen Abschnitt „Preis nach Land Liste“ definieren.
  - *Wenn deaktiviert:* Das Modul stoppt die Preisanpassungen, und alle Kunden sehen Ihre Standardproduktpreise, unabhängig von ihrem Land.
- **Empfohlener Wert:** „JA“ (Aktiviert), wenn Sie das Modul für Preisanpassungen verwenden möchten.
- **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, möchten Sie es hier aktivieren. Wenn Sie alle länderspezifischen Preisanpassungen vorübergehend pausieren möchten, ohne Ihre Regeln zu löschen, können Sie es hier deaktivieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminPbcListController (Back Office > Preise nach Land erhöhen > Preis nach Land Liste)

Dies ist der zentrale Verwaltungsbildschirm, auf dem Sie Ihre länderspezifischen Preisanpassungsregeln definieren und verwalten.

- **Bildschirmname & Menüposition:** Sie finden einen neuen Menüpunkt in Ihrem PrestaShop Back Office, typischerweise unter einem Abschnitt wie „Katalog“ oder „International“, benannt **„Preise nach Land erhöhen“** oder ähnlich, und dann einen Untermenüpunkt wie **„Preis nach Land Liste“**.
- **Verfügbare Aktionen & Einstellungen:**
  - **Neue Regel hinzufügen:** Eine Schaltfläche zum Erstellen einer neuen Preisanpassungsregel.
  - **Liste der Regeln:** Eine Tabelle, die alle bestehenden Regeln anzeigt, mit Details wie:
    - **Land:** Das Zielland für die Regel.
    - **Anpassungstyp:** Ob es sich um einen Prozentsatz oder einen festen Betrag handelt.
    - **Wert:** Der Prozentsatz oder Betrag zur Erhöhung/Senkung.
    - **Aktion:** Optionen zum „Bearbeiten“ oder „Löschen“ einzelner Regeln.
  - **Formularfelder zum Hinzufügen/Bearbeiten einer Regel:**
    - **Länderauswahl:** Ein Dropdown-Menü oder Suchfeld zur Auswahl des spezifischen Landes, für das diese Regel gilt.
      - *Effekt:* Preise werden nur für Kunden angepasst, die in diesem Land identifiziert wurden.
      - *Empfohlen:* Wählen Sie das spezifische Land aus, das Sie ansprechen möchten.
      - *Szenario:* Sie möchten die Preise für Kunden in den Vereinigten Staaten erhöhen.
    - **Anpassungstyp (Prozentsatz / Betrag):** Ein Optionsfeld oder Dropdown-Menü zur Auswahl, wie der Preis angepasst wird.
      - *Effekt:*
        - *Prozentsatz:* Der Preis wird um einen Prozentsatz seines ursprünglichen Wertes erhöht oder gesenkt.
        - *Betrag:* Der Preis wird um einen festen Geldwert (in der Standardwährung Ihres Shops) erhöht oder gesenkt.
      - *Empfohlen:* Wählen Sie basierend auf Ihrer Preisstrategie. Prozentsatz ist gut für konsistente Aufschläge, Betrag für feste Zuschläge/Rabatte.
      - *Szenario:* Sie möchten einen Aufschlag von 10 % (Prozentsatz) oder einen festen Zuschlag von 5 $ (Betrag) hinzufügen.
    - **Wert:** Ein Eingabefeld zur Eingabe des Prozentsatzes (z. B. „10“ für 10 %) oder des festen Betrags (z. B. „5.00“ für 5 $).
      - *Effekt:*
        - *Positiver Wert:* Erhöht den Preis.
        - *Negativer Wert:* Senkt den Preis (z. B. „-5“ für einen Rabatt von 5 % oder „-2.50“ für einen Rabatt von 2,50 $).
      - *Empfohlen:* Geben Sie die gewünschte Anpassung ein. Seien Sie vorsichtig mit negativen Werten, um zu vermeiden, dass Preise unter Null fallen.
      - *Szenario:* Geben Sie „15“ ein, um um 15 % zu erhöhen, oder „-2.50“, um um 2,50 $ zu senken.
- **Auswirkung von Änderungen:**
  - Das Hinzufügen einer neuen Regel aktiviert sofort die Preisanpassung für das ausgewählte Land.
  - Das Bearbeiten einer Regel aktualisiert die Anpassung für dieses Land.
  - Das Löschen einer Regel entfernt die länderspezifische Anpassung, und Kunden aus diesem Land sehen wieder die Standardproduktpreise.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Identifizieren Sie ein Land, in dem Sie Preise anpassen möchten (z. B. aufgrund höherer Versandkosten, lokaler Konkurrenz oder einer Sonderaktion).
  2. Navigieren Sie zum Bildschirm „Preis nach Land Liste“.
  3. Klicken Sie auf „Neue Regel hinzufügen“.
  4. Wählen Sie das Zielland aus.
  5. Wählen Sie, ob die Anpassung nach „Prozentsatz“ oder „Betrag“ erfolgen soll.
  6. Geben Sie den positiven oder negativen Wert für die Anpassung ein.
  7. Speichern Sie die Regel.
  8. Testen Sie, indem Sie ein VPN verwenden oder jemanden in diesem Land bitten, die Preise in Ihrem Shop zu überprüfen.

#### index.php (pbc/controllers/admin/index.php)

Diese Datei dient wahrscheinlich als Routing oder Platzhalter für die Admin-Controller innerhalb des `pbc`-Modulverzeichnisses. Sie stellt keinen eigenständigen, konfigurierbaren Bildschirm dar, sondern gewährleistet den ordnungsgemäßen Zugriff und das Laden anderer Admin-Controller wie `AdminPbcListController`. Händler werden nicht direkt mit dieser Datei interagieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Modul aktiviert/deaktiviert | Aktiviert | Globaler Schalter zum Aktivieren oder Deaktivieren aller länderspezifischen Preisanpassungen. |
| **Preis nach Land Liste** | Regel hinzufügen/bearbeiten: Land | N/A (spezifisch auswählen) | Definiert das Zielland für die Preisanpassung. |
| | Regel hinzufügen/bearbeiten: Anpassungstyp | Prozentsatz | Wählen Sie, ob sich der Preis um einen Prozentsatz oder einen festen Betrag ändert. |
| | Regel hinzufügen/bearbeiten: Wert | 0 (gewünschten Wert eingeben) | Der positive (Erhöhung) oder negative (Senkung) Prozentsatz oder Betrag. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Preise ändern sich für ein bestimmtes Land nicht, obwohl ich eine Regel eingerichtet habe.**
A:

1.  **Ist das Modul global aktiviert?** Überprüfen Sie die Hauptkonfigurationsseite des Moduls (Module > Modul-Manager > Konfigurieren „Preise nach Land erhöhen“), um sicherzustellen, dass das Modul aktiv ist.
2.  **Ist die Regel korrekt konfiguriert?** Gehen Sie zu „Preis nach Land Liste“ und überprüfen Sie, ob das Land korrekt ausgewählt ist, der Anpassungstyp (Prozentsatz/Betrag) richtig ist und der Wert korrekt eingegeben wurde (positiv für Erhöhung, negativ für Senkung).
3.  **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“, falls verfügbar). Dies löst oft Anzeigeprobleme.
4.  **Geolocation-Probleme:** Das Modul basiert auf der Geolocation-Funktion von PrestaShop. Stellen Sie sicher, dass die Geolocation Ihres PrestaShop-Shops korrekt konfiguriert ist (Erweiterte Einstellungen > Geolocation). Wenn Sie von Ihrem eigenen Land aus testen, versuchen Sie, ein VPN zu verwenden, um einen Besuch aus dem Zielland zu simulieren.

**F: Beeinflusst dieses Modul meine SEO oder Produkt-Feeds?**
A: Das Modul passt die Preise im Front-Office dynamisch basierend auf der IP-Adresse des Besuchers an. Es ändert nicht den Basispreis Ihres Produkts in der Datenbank. Daher sollte es im Allgemeinen Ihre SEO (Suchmaschinen crawlen typischerweise von einem Standardstandort oder verwenden Ihre Basispreise) oder Produkt-Feeds (die normalerweise Basispreise abrufen) nicht direkt beeinflussen. Wenn Sie jedoch einen Drittanbieterdienst verwenden, der Ihre Website von verschiedenen Standorten aus crawlt, könnten diese die angepassten Preise sehen.

**F: Was passiert, wenn ein Kunde aus einem Land mit Preisanpassung ein Produkt in den Warenkorb legt und dann sein Land ändert (z. B. über die Lieferadresse)?**
A: Das Modul passt die Preise basierend auf dem *erkannten Land des Kunden* zum Zeitpunkt des Browsens an. Wenn sich das Land des Kunden ändert (z. B. er meldet sich an und seine Adresse ist in einem anderen Land, oder er wählt während des Checkouts explizit ein anderes Lieferland), sollte die Kernlogik von PrestaShop für die Preisberechnung (die dieses Modul überschreibt) den Preis neu bewerten. Die Überschreibung des Moduls stellt sicher, dass der korrekte Preis für das *endgültige* Land angewendet wird.

**F: Kann ich innerhalb desselben Landes unterschiedliche Regeln für verschiedene Kundengruppen anwenden?**
A: Nein, dieses Modul passt die Preise *ausschließlich basierend auf dem Land* an, das durch Geolocation bestimmt wird. Es bietet keine Optionen zur Differenzierung der Preise basierend auf Kundengruppen (z. B. Großhandel vs. Einzelhandel) innerhalb eines einzelnen Landes. Für kundengruppenspezifische Preise benötigen Sie ein separates Modul oder die integrierten Preisregeln von PrestaShop.

**F: Ich habe eine Betragserhöhung eingestellt, aber sie sieht in anderen Währungen anders aus.**
A: Wenn Sie eine Betragserhöhung (z. B. +5 $) einstellen, wendet das Modul diesen Betrag in der *Standardwährung Ihres Shops* an. Es wandelt diesen zusätzlichen Betrag dann automatisch in andere Währungen um, basierend auf den in Ihrem Shop konfigurierten Wechselkursen. Dies stellt sicher, dass der *Wert* der Erhöhung über alle Währungen hinweg konsistent bleibt. Stellen Sie sicher, dass Ihre Wechselkurse in PrestaShop aktuell sind (International > Währungen).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Preise nach Land erhöhen“ (`pbc`) funktioniert hauptsächlich durch das Überschreiben der Kernklasse `Product` von PrestaShop, um länderspezifische Preisanpassungen während der Preisberechnung einzufügen. Es nutzt die Geolocation-Funktionen von PrestaShop, um das Land des Kunden zu identifizieren und wendet Regeln an, die in einer benutzerdefinierten Datenbanktabelle definiert sind. Das Modul folgt einem Standard-PrestaShop-MVC-Muster für seine Back-Office-Verwaltung, mit einem dedizierten Admin-Controller zur Verwaltung von Preisregeln.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine explizit im Modularchiv definiert. Preisanpassungen werden über die `Product.php`-Überschreibung gehandhabt, die sich in die Kernlogik der Preisberechnung von PrestaShop einklinkt.
- **Back-Office-Admin-Controller**:
  - `pbc/controllers/admin/AdminPbcListController.php`
    - **Klassenname**: `AdminPbcListController` (erweitert `ModuleAdminController`)
    - **Verantwortlichkeit**: Verwaltet die CRUD-Operationen für die Entität `pricebc` (Price By Country). Dieser Controller zeigt die Liste der definierten Preisanpassungsregeln an, handhabt das Hinzufügen neuer Regeln, das Bearbeiten bestehender Regeln und deren Löschen. Er verwendet PrestaShops `HelperList` und `HelperForm` zum Rendern der Liste bzw. der Hinzufüge-/Bearbeitungsformulare.
    - **Tab-Name**: Typischerweise unter einem benutzerdefinierten Tab in der Back-Office-Navigation registriert, zugänglich über den Hauptmenüpunkt des Moduls.
  - `pbc/controllers/admin/index.php`
    - **Klassenname**: N/A (dies ist eine Platzhalterdatei)
    - **Verantwortlichkeit**: Diese Datei ist eine gängige Praxis in der PrestaShop-Modulentwicklung, um direkte Verzeichnisauflistungen zu verhindern und ein ordnungsgemäßes Routing innerhalb des `controllers/admin`-Verzeichnisses sicherzustellen. Sie enthält keine ausführbare Logik für einen spezifischen Controller.

### 4.3 Kernklassen & Modelle (`classes/`)

- `pbc/classes/index.php`
  - **Klassenname**: N/A
  - **Verantwortlichkeit**: Platzhalterdatei zur Verhinderung der Verzeichnisauflistung.
- `pbc/classes/pricebc.php`
  - **Klassenname**: `PriceBc` (erweitert `ObjectModel`)
  - **Datenbanktabelle**: `_pbc` (z. B. `ps_pbc`)
  - **`$definition`-Felder**:
    - `id_pbc`: Primärschlüssel.
    - `id_country`: Fremdschlüssel zur Tabelle `ps_country`, identifiziert das Zielland.
    - `type`: Integer, typischerweise 0 für Prozentsatz, 1 für Betrag.
    - `value`: Dezimal, der Prozentsatz oder Betrag zur Anpassung. Kann positiv oder negativ sein.
  - **Wichtige öffentliche Methoden**: Standard `ObjectModel`-Methoden für CRUD-Operationen. Kann statische Methoden zum Abrufen von Regeln basierend auf der Länder-ID enthalten.
- `pbc/override/classes/index.php`
  - **Klassenname**: N/A
  - **Verantwortlichkeit**: Platzhalterdatei zur Verhinderung der Verzeichnisauflistung innerhalb des Override-Verzeichnisses.
- `pbc/override/classes/Product.php`
  - **Klassenname**: `Product` (erweitert PrestaShops Kernklasse `Product`)
  - **Verantwortlichkeit**: Dies ist der kritischste Teil des Moduls. Es überschreibt die Methode `getPriceStatic()` (oder ähnliche Preisberechnungsmethoden) der Kernklasse `Product`.
    - Es ruft das aktuelle Land des Kunden ab (über Geolocation oder Kontext).
    - Es fragt das `PriceBc`-Modell ab, um aktive Preisanpassungsregeln für dieses Land zu finden.
    - Es wendet dann die prozentuale oder betragsmäßige Anpassung auf den Basispreis des Produkts an, bevor der endgültig berechnete Preis zurückgegeben wird.
    - Handhabt die Währungsumrechnung für betragsbasierte Anpassungen.
  - **Entwicklerhinweis**: Andere Module, die ebenfalls `Product.php` überschreiben, könnten zu Konflikten führen. Sorgfältige Tests sind erforderlich. Die Überschreibung des Moduls sollte so konzipiert sein, dass sie mit anderen Überschreibungen kompatibel ist oder eine Verkettung ermöglicht.

### 4.4 JavaScript-Assets (`views/js/`)

- `pbc/views/admin/script.js`
  - **Geltungsbereich**: Back-Office (AdminPbcListController-Formulare).
  - **Funktionalität**: Behandelt wahrscheinlich dynamisches Verhalten im Formular „Preisregel hinzufügen/bearbeiten“. Dies könnte umfassen:
    - Anzeigen/Ausblenden von Feldern basierend auf dem ausgewählten „Anpassungstyp“ (z. B. wenn „Prozentsatz“ ausgewählt ist, sicherstellen, dass das Wertfeld als Prozentsatz behandelt wird).
    - Eingabevalidierung oder -formatierung.
    - AJAX-Aufrufe für die Länderauswahl oder andere dynamische Formularelemente.

### 4.5 CSS-Stylesheets (`views/css/`)

Es wurden keine benutzerdefinierten CSS-Dateien im bereitgestellten Inventar erkannt. Das Modul verlässt sich wahrscheinlich auf die Standard-Back-Office-Stile von PrestaShop für seine Konfigurationsformulare und Listen und führt keine visuellen Front-Office-Elemente ein, die eine benutzerdefinierte Stilgebung erfordern.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `pbc/views/displayHeader.tpl`
    - **Hook**: `displayHeader`
    - **Zweck**: Dieses Template wird wahrscheinlich verwendet, um notwendige JavaScript- oder CSS-Dateien (falls vorhanden) einzubinden oder Front-Office-Skripte zu initialisieren, die früh beim Seitenaufbau ausgeführt werden müssen. Angesichts der Natur des Moduls könnte es auch Logik zur Erkennung des Benutzerlandes oder zum Setzen einer globalen JS-Variable zum Debuggen enthalten.
- **Admin-Templates (`views/templates/admin/`)**:
  - `pbc/lib/searchTool/views/scripts.tpl`
    - **Zweck**: Dieses Template ist wahrscheinlich Teil einer wiederverwendbaren Komponente oder Bibliothek innerhalb des Moduls, möglicherweise für ein Such- oder Filterwerkzeug, das im AdminPbcListController verwendet wird. Es würde JavaScript- oder Smarty-Logik im Zusammenhang mit diesem Werkzeug enthalten.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `pbc/views/script.tpl`
    - **Zweck**: Ähnlich wie `displayHeader.tpl` könnte dieses Template verwendet werden, um JavaScript direkt in das Front-Office einzubetten, möglicherweise für clientseitige Logik im Zusammenhang mit der Preisanzeige (obwohl die primäre Logik serverseitig über die `Product`-Überschreibung erfolgt). Es könnte auch ein Fallback oder ein allgemeinerer Skript-Einbindungspunkt sein.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - `ps_pbc`: Speichert die Preisanpassungsregeln.
    - `id_pbc` (INT, PK, AUTO\_INCREMENT)
    - `id_country` (INT, FK zu `ps_country.id_country`)
    - `type` (TINYINT, 0 für Prozentsatz, 1 für Betrag)
    - `value` (DECIMAL(20,6), signed, der Anpassungswert)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Zum Einbinden der JS/CSS-Assets des Moduls oder zur Initialisierung von Frontend-Skripten. |
| `actionProductPriceCalculation` | (Implizit über `Product.php`-Überschreibung) | Die Kernfunktionalität des Moduls wird durch Überschreiben der Methode `Product::getPriceStatic()` implementiert, die immer dann aufgerufen wird, wenn PrestaShop den Preis eines Produkts berechnet. Dies ist kein Standard-Hook, sondern eine Kernklassenüberschreibung. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird. | Zum Einbinden der JS/CSS-Assets des Moduls für das Back Office (z. B. `AdminPbcListController`). |
| `actionModuleInstall` | Während der Modulinstallation. | Zum Erstellen der Datenbanktabelle `ps_pbc` und zum Registrieren notwendiger Hooks. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Entfernen der Datenbanktabelle `ps_pbc` und zum Deregistrieren von Hooks. |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und technischen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, Unterstützung zu leisten und sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.
