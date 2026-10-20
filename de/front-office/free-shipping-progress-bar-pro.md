---
title: "Free Shipping Progress Bar Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Free Shipping Progress Bar Pro von MyPresta.eu."
sidebar:
  label: "Free Shipping Progress Bar Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free Shipping Progress Bar Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/free-shipping-progress-bar-pro/)
>
> ---


# Free Shipping Progress Bar Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel erforderlich und auf den meisten modernen Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbereich, in dem Sie alle Regeln, das Aussehen und das Verhalten Ihrer Free Shipping Progress Bar einrichten. Die Seite ist intuitiv gestaltet und führt Sie durch verschiedene Abschnitte.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Steuert die Gesamtaktivierung und das grundlegende Verhalten der Fortschrittsleiste.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Modul aktivieren/deaktivieren:* Schaltet die gesamte Funktionalität der Fortschrittsleiste für Ihren Shop ein oder aus.
  - *Anzeigeposition:* Bestimmt, wo die Fortschrittsleiste in Ihrem Front Office erscheint (z. B. Header, Footer, Produktseite, Warenkorbseite).
  - *Feste Leiste (Sticky Bar):* Lässt die Leiste am oberen oder unteren Bildschirmrand „kleben“, während der Benutzer scrollt, wodurch sie sichtbar bleibt.
- **Empfohlener Wert:**
  - *Modul aktivieren:* JA (um die Funktion zu aktivieren).
  - *Anzeigeposition:* Header (oft am effektivsten für die Sichtbarkeit).
  - *Feste Leiste (Sticky Bar):* JA (für maximale Wirkung).
- **Händlerszenario / Beispiel:** Sie möchten, dass die Fortschrittsleiste immer oben in Ihrem Shop sichtbar ist, um Kunden ständig an den kostenlosen Versand zu erinnern. Sie würden das Modul aktivieren, die Anzeigeposition auf „Header“ setzen und „Feste Leiste (Sticky Bar)“ aktivieren.

#### Schwellenwerte für kostenlosen Versand

- **Was diese Einstellung bewirkt:** Definiert den Betrag, den Kunden ausgeben müssen, um sich für kostenlosen Versand zu qualifizieren. Dies ist der Kern der Modulfunktionalität. Sie können einen Standardschwellenwert festlegen und diesen dann mit spezifischen Regeln für Länder oder Kundengruppen überschreiben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Standardschwellenwert:* Legt den Basisbetrag für alle Kunden fest, die nicht von spezifischen Regeln abgedeckt sind.
  - *Länderspezifische Schwellenwerte:* Ermöglicht es Ihnen, unterschiedliche Beträge für kostenlosen Versand für Kunden aus bestimmten Ländern festzulegen (z. B. höher für internationalen Versand).
  - *Kundengruppenspezifische Schwellenwerte:* Passen Sie Schwellenwerte für verschiedene Kundengruppen an (z. B. niedriger für VIP-Kunden, höher für Großhändler).
- **Empfohlener Wert:** Beginnen Sie mit einem Standardschwellenwert, der für Ihren durchschnittlichen Bestellwert und Ihre Versandkosten sinnvoll ist. Fügen Sie dann bei Bedarf spezifische Regeln hinzu.
- **Händlerszenario / Beispiel:** Ihr kostenloser Versand beträgt standardmäßig 100 €. Für Kunden in Kanada möchten Sie jedoch 150 € festlegen, da die Versandkosten höher sind. Sie würden den Standard auf 100 € setzen und dann eine Länderregel für Kanada mit 150 € hinzufügen. Für Ihre Kundengruppe „Großhandel“ könnten Sie ihn auf 500 € festlegen.

#### Visueller Designer

- **Was diese Einstellung bewirkt:** Bietet eine benutzerfreundliche Oberfläche zur Anpassung des Aussehens und der Haptik Ihrer Fortschrittsleiste ohne jegliche Programmierung. Sie können Farben, Schriftarten, Leistenstile und mehr ändern.
- **Auswirkung der Änderung dieser Einstellung:** Wirkt sich direkt auf das visuelle Erscheinungsbild der Fortschrittsleiste in Ihrem Front Office aus.
  - *Farben:* Passen Sie Hintergrund-, Text- und Füllfarben der Fortschrittsleiste an Ihre Marke an.
  - *Schriftarten & Größen:* Passen Sie Textstile für Nachrichten an.
  - *Leistenstil:* Wählen Sie zwischen verschiedenen visuellen Stilen für die Fortschrittsleiste selbst (z. B. abgerundet, flach).
  - *Animationen:* Fügen Sie subtile Animationen für ein ansprechenderes Erlebnis hinzu.
- **Empfohlener Wert:** Experimentieren Sie, um ein Design zu finden, das optisch ansprechend, deutlich sichtbar und konsistent mit dem Branding Ihres Shops ist.
- **Händlerszenario / Beispiel:** Ihr Shop verwendet einen bestimmten Blauton und eine klare, moderne Schriftart. Sie würden den visuellen Designer verwenden, um den Hintergrund der Fortschrittsleiste auf dieses Blau, den Text auf Weiß und eine serifenlose Schriftart zu wählen, die zu Ihrem Thema passt.

#### Dynamische Nachrichten

- **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, benutzerdefinierte Nachrichten zu erstellen, die in der Fortschrittsleiste erscheinen und sich je nach Fortschritt des Kunden in Richtung kostenlosem Versand ändern. Sie können Platzhalter verwenden, um dynamische Werte wie den verbleibenden Betrag einzufügen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Nachrichten für „Noch nicht qualifiziert“:* Wird angezeigt, wenn der Kunde den Schwellenwert noch nicht erreicht hat.
  - *Nachrichten für „Qualifiziert“:* Wird angezeigt, sobald der Kunde den Schwellenwert erreicht oder überschritten hat.
  - *Platzhalter:* Die Verwendung von `[amount_left]`, `[total_cart]`, `[free_shipping_threshold]`, `[currency_symbol]` fügt diese Werte dynamisch in Ihre Nachrichten ein.
- **Empfohlener Wert:** Halten Sie Nachrichten klar, prägnant und ermutigend. Verwenden Sie Platzhalter, um sie dynamisch und persönlich zu gestalten.
- **Händlerszenario / Beispiel:**
  - *Nicht qualifiziert:* „Geben Sie [amount\_left] mehr aus, um KOSTENLOSEN Versand zu erhalten!“
  - *Qualifiziert:* „Herzlichen Glückwunsch! Ihre Bestellung qualifiziert sich für KOSTENLOSEN Versand!“
    Dies kommuniziert das Ziel klar und feiert den Erfolg.

#### A/B-Tests & Analysen

- **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, A/B-Tests für verschiedene Fortschrittsleistenkonfigurationen (z. B. verschiedene Nachrichten, Farben oder Schwellenwerte) durchzuführen und deren Leistung zu verfolgen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *A/B-Testmodus aktivieren:* Ermöglicht das Erstellen von Variationen Ihrer Fortschrittsleiste.
  - *Konversionen verfolgen:* Zeichnet auf, wie verschiedene Variationen Ihre Konversionsraten und den durchschnittlichen Bestellwert beeinflussen.
- **Empfohlener Wert:** Aktivieren Sie diese Funktion, sobald Ihre Grundeinrichtung stabil ist. Verwenden Sie sie, um die Effektivität Ihrer Fortschrittsleiste kontinuierlich zu optimieren.
- **Händlerszenario / Beispiel:** Sie möchten testen, ob „Geben Sie X € mehr aus für KOSTENLOSEN Versand!“ besser abschneidet als „Schalten Sie KOSTENLOSEN Versand mit nur X € mehr frei!“. Sie würden zwei Variationen einrichten und das Modul verfolgen lassen, welche zu mehr Verkäufen führt.

#### Erweiterte Einstellungen

- **Was diese Einstellung bewirkt:** Enthält Optionen für technischere Aspekte, wie Caching, Kompatibilität mit bestimmten Themes oder benutzerdefiniertes CSS/JS.
- **Auswirkung der Änderung dieser Einstellung:** Kann die Leistung, die Theme-Integration oder hochspezifische Anpassungen beeinflussen.
  - *Cache-Einstellungen:* Verbessert die Ladegeschwindigkeit durch Caching des Leisteninhalts.
  - *Benutzerdefiniertes CSS/JS:* Ermöglicht Entwicklern, eigene Stile oder Skripte hinzuzufügen.
- **Empfohlener Wert:** Lassen Sie diese im Allgemeinen auf ihren Standardwerten, es sei denn, Sie haben einen spezifischen Bedarf oder werden von einem Entwickler dazu beraten.
- **Händlerszenario / Beispiel:** Ihr benutzerdefiniertes Theme hat eine einzigartige Header-Struktur, und die Fortschrittsleiste richtet sich nicht perfekt aus. Ein Entwickler könnte das Feld „Benutzerdefiniertes CSS“ verwenden, um spezifische Styling-Regeln hinzuzufügen, um die Ausrichtung zu korrigieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Allgemeine Einstellungen** | Modul aktivieren | JA | Aktiviert/deaktiviert die gesamte Fortschrittsleistenfunktion. |
|  | Anzeigeposition | Header | Wo die Leiste erscheint (Header, Footer, Produkt, Warenkorb, Spalten). |
|  | Feste Leiste (Sticky Bar) | JA | Lässt die Leiste am oberen/unteren Bildschirmrand kleben. |
| **Schwellenwerte für kostenlosen Versand** | Standardschwellenwert | Betrag für kostenlosen Versand Ihres Shops | Basisbetrag für kostenlosen Versand. |
|  | Länderregeln | Nach Bedarf | Überschreibt den Standard für bestimmte Länder. |
|  | Kundengruppenregeln | Nach Bedarf | Überschreibt den Standard für bestimmte Kundengruppen. |
| **Visueller Designer** | Hintergrundfarbe der Leiste | Theme-abhängig | Ändert die Hintergrundfarbe der Leiste. |
|  | Füllfarbe des Fortschritts | Theme-abhängig | Ändert die Farbe des gefüllten Fortschrittsbereichs. |
|  | Textfarbe | Theme-abhängig | Ändert die Farbe der Nachrichten. |
|  | Schriftfamilie / Größe | Theme-abhängig | Passt das Erscheinungsbild des Textes an. |
|  | Leistenstil | Standard | Visuelles Design der Fortschrittsleiste selbst. |
| **Dynamische Nachrichten** | Nachricht - Nicht qualifiziert | „Geben Sie [amount\_left] mehr aus, um KOSTENLOSEN Versand zu erhalten!“ | Nachricht, die angezeigt wird, wenn das Ziel nicht erreicht ist. |
|  | Nachricht - Qualifiziert | „Herzlichen Glückwunsch! Ihre Bestellung qualifiziert sich für KOSTENLOSEN Versand!“ | Nachricht, die angezeigt wird, wenn das Ziel erreicht ist. |
| **A/B-Tests & Analysen** | A/B-Tests aktivieren | NEIN (anfangs) | Ermöglicht das Ausführen von Tests mit verschiedenen Leistenkonfigurationen. |
|  | Konversionen verfolgen | JA (bei A/B-Tests) | Zeichnet die Leistung verschiedener Leistenversionen auf. |
| **Erweiterte Einstellungen** | Cache aktivieren | JA | Verbessert die Ladegeschwindigkeit der Leiste. |
|  | Benutzerdefiniertes CSS | Leer lassen | Für erweiterte Stilüberschreibungen durch Entwickler. |
|  | Benutzerdefiniertes JS | Leer lassen | Für erweiterte Skriptergänzungen durch Entwickler. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Fortschrittsleiste wird in meinem Shop nicht angezeigt oder aktualisiert sich nicht.**
**A1:**

- **Modulstatus prüfen:** Stellen Sie zunächst sicher, dass das Modul in Ihrem PrestaShop Back Office unter **Module > Modul-Manager** aktiviert ist.
- **Anzeigeposition überprüfen:** Gehen Sie zur Modulkonfiguration und überprüfen Sie die Einstellung „Anzeigeposition“. Stellen Sie sicher, dass sie auf einen sichtbaren Hook eingestellt ist (z. B. Header, Footer). Wenn Sie einen Spalten-Hook gewählt haben, stellen Sie sicher, dass Ihr Theme diese Spalte tatsächlich anzeigt.
- **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Leeren Sie auch den Cache Ihres Browsers.
- **Theme-Kompatibilität:** Einige stark angepasste Themes erfordern möglicherweise geringfügige Anpassungen. Wenn das Problem nach dem Leeren des Caches weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F2: Die Fortschrittsleiste sieht seltsam aus oder passt nicht zum Design meines Themes.**
**A2:**

- **Visuellen Designer verwenden:** Das Modul enthält einen Abschnitt „Visueller Designer“ in seiner Konfiguration. Verwenden Sie diesen, um Farben, Schriftarten und Stile anzupassen, damit sie besser zu Ihrem Theme passen.
- **Benutzerdefiniertes CSS:** Wenn der visuelle Designer nicht ausreicht, kann Ihr Webmaster oder ein Entwickler das Feld „Benutzerdefiniertes CSS“ in den erweiterten Einstellungen des Moduls verwenden, um spezifische Styling-Regeln hinzuzufügen, die die Standardeinstellungen überschreiben.
- **Theme-Cache:** Leeren Sie nach Designänderungen immer Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung**) und Ihren Browser-Cache.

**F3: Der Betrag für den kostenlosen Versand ist falsch oder ändert sich für bestimmte Kunden nicht.**
**A3:**

- **Schwellenwertregeln überprüfen:** Gehen Sie zum Abschnitt „Schwellenwerte für kostenlosen Versand“ in der Modulkonfiguration.
  - Überprüfen Sie, ob der „Standardschwellenwert“ korrekt ist.
  - Überprüfen Sie, ob „Länderspezifische Schwellenwerte“ oder „Kundengruppenspezifische Schwellenwerte“ den Standard für die betroffenen Kunden überschreiben. Stellen Sie sicher, dass die Regeln für die relevanten Länder/Gruppen korrekt eingerichtet sind.
- **Währung:** Stellen Sie sicher, dass Ihre Standardwährung und die für den Schwellenwert verwendete Währung übereinstimmen.
- **Warenkorbberechnung:** Das Modul basiert auf dem Warenkorbwert von PrestaShop. Stellen Sie sicher, dass Ihre Produkte korrekte Preise haben und die Steuerregeln wie erwartet angewendet werden.

**F4: Wie übersetze ich die Nachrichten für meine internationalen Kunden in verschiedene Sprachen?**
**A4:**

- Das Modul unterstützt das native Übersetzungssystem von PrestaShop.
- Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann das Modul „Free Shipping Progress Bar Pro“.
- Sie können dann alle dynamischen Nachrichten und anderen vom Modul angezeigten Texte in Ihre gewünschten Sprachen übersetzen. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Die Fortschrittsleiste wird auf mobilen Geräten nicht angezeigt oder ist nicht responsiv.**
**A5:**

- Das Modul ist vollständig responsiv konzipiert.
- **Cache leeren:** Leeren Sie wie immer den PrestaShop-Cache (**Erweiterte Parameter > Leistung**) und den Cache Ihres mobilen Browsers.
- **Anzeigeposition überprüfen:** Stellen Sie sicher, dass die gewählte Anzeigeposition (z. B. Header) eine ist, die Ihr Theme auf Mobilgeräten prominent darstellt. Einige Themes blenden bestimmte Elemente auf kleineren Bildschirmen möglicherweise aus.
- **Theme-Konflikte:** Sehr selten kann ein stark angepasstes mobiles Theme widersprüchliches CSS aufweisen. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support oder Ihren Webmaster.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls Free Shipping Progress Bar Pro, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul `Free Shipping Progress Bar Pro` (`smartfreeshippingpro`) folgt der Standard-PrestaShop-Modularchitektur und nutzt hauptsächlich Hooks für die Front-Office-Anzeige und einen dedizierten `ModuleFrontController` für AJAX-Interaktionen. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse verwaltet, die eine Smarty-Vorlage für die Back-Office-Oberfläche rendert. Es verwendet die `Configuration`-Klasse von PrestaShop, um Einstellungen zu speichern, und stützt sich auf die Kern-PrestaShop-Dienste für Warenkorb- und Währungsinformationen. Das Modul legt Wert auf einen visuellen Konfigurationsansatz mit dediziertem JS für die Admin-Oberfläche.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `smartfreeshippingpro/controllers/front/index.php`
    - **Klassenname:** `SmartFreeShippingProIndexModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention)
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Basis oder Einstiegspunkt für Front-Office-Interaktionen, obwohl seine spezifischen Methoden minimal sein könnten, wenn `refresh.php` die primäre AJAX-Verarbeitung übernimmt. Er könnte für die anfängliche Datenkonfiguration oder nicht-AJAX-Front-Office-Logik verantwortlich sein.
  - `smartfreeshippingpro/controllers/front/refresh.php`
    - **Klassenname:** `SmartFreeShippingProRefreshModuleFrontController`
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dies ist der kritische AJAX-Endpunkt. Er antwortet auf Anfragen (z. B. von `front.js`), um die Fortschrittsleiste für den kostenlosen Versand zu aktualisieren. Er ruft den aktuellen Warenkorbwert ab, berechnet den verbleibenden Betrag für den kostenlosen Versand basierend auf den konfigurierten Schwellenwerten (Standard-, Länder-, Gruppenregeln) und gibt die aktualisierten Fortschrittsdaten und Nachrichten zurück, typischerweise im JSON-Format. Dieser Controller ist für die Echtzeit-Updates der Leiste verantwortlich.
- **Back-Office-Admin-Controller**:

  - Es sind keine dedizierten `AdminController`-Dateien vorhanden. Die gesamte Back-Office-Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei (`index.php`) behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es sind keine benutzerdefinierten Klassen, die `ObjectModel` oder andere Kern-PrestaShop-Klassen erweitern, explizit im bereitgestellten Inventar aufgeführt. Das Modul stützt sich wahrscheinlich auf die integrierten PrestaShop-Klassen `Cart`, `Context`, `Configuration`, `Currency` und `Country` für seine Logik.

### 4.4 JavaScript-Assets (`views/js/`)

- `smartfreeshippingpro/views/js/admin-config.js`
  - **Umfang:** Back-Office.
  - **Beschreibung:** Behandelt wahrscheinlich allgemeine Interaktionen mit Konfigurationsformularen, das Speichern von Einstellungen und möglicherweise die Formularvalidierung für die Hauptmodulkonfigurationsseite.
- `smartfreeshippingpro/views/js/admin-placeholders.js`
  - **Umfang:** Back-Office.
  - **Beschreibung:** Verwaltet das dynamische Einfügen von Platzhaltern (z. B. `[amount_left]`, `[total_cart]`) in die Nachrichteneingabefelder innerhalb der Admin-Konfiguration, wodurch es für Händler einfacher wird, dynamische Nachrichten zu erstellen.
- `smartfreeshippingpro/views/js/admin-threshold-picker.js`
  - **Umfang:** Back-Office.
  - **Beschreibung:** Behandelt die Logik zum Hinzufügen, Bearbeiten und Entfernen von länderspezifischen und kundengruppenspezifischen Schwellenwerten für den kostenlosen Versand. Dies würde dynamische Formularelemente zur Auswahl von Ländern/Gruppen und zur Eingabe von Beträgen umfassen.
- `smartfreeshippingpro/views/js/admin-visual-designer.js`
  - **Umfang:** Back-Office.
  - **Beschreibung:** Treibt die visuelle Anpassungsoberfläche an. Es verwendet wahrscheinlich JavaScript, um eine Vorschau der Fortschrittsleiste dynamisch zu aktualisieren, wenn der Administrator Farben, Schriftarten und Stile ändert, und bietet so sofortiges visuelles Feedback.
- `smartfreeshippingpro/views/js/admin.js`
  - **Umfang:** Back-Office.
  - **Beschreibung:** Ein allgemeines Admin-Skript, das andere admin-spezifische JS-Dateien initialisieren, globale Admin-Ereignisse behandeln oder Dienstprogrammfunktionen für die Back-Office-Oberfläche bereitstellen könnte.
- `smartfreeshippingpro/views/js/front.js`
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dies ist das zentrale Frontend-Skript.
    - **Event-Listener:** Bindet an `prestashop.on('updateCart', ...)` oder ähnliche Ereignisse, um Änderungen im Warenkorb zu erkennen (Hinzufügen, Entfernen, Mengenaktualisierung).
    - **AJAX-Aufrufe:** Löst AJAX-Anfragen an den `refresh.php`-Front-Controller aus, um aktualisierte Daten der Fortschrittsleiste zu erhalten.
    - **DOM-Manipulation:** Aktualisiert die Breite der Fortschrittsleiste, Textnachrichten und möglicherweise deren Sichtbarkeit basierend auf der AJAX-Antwort.
    - **Animationen:** Kann Logik für sanfte Übergänge oder Animationen der Fortschrittsleiste enthalten.
    - **Sticky Bar Logik:** Wenn die Sticky Bar-Funktion aktiviert ist, würde dieses Skript die CSS-Positionierung (`position: fixed`) und möglicherweise Scroll-Event-Listener zur Verwaltung ihrer Sichtbarkeit behandeln.

### 4.5 CSS-Stylesheets (`views/css/`)

- `smartfreeshippingpro/views/css/admin-config.css`
  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Beschreibung:** Stile für das allgemeine Layout und die Elemente der Hauptkonfigurationsseite des Moduls.
- `smartfreeshippingpro/views/css/admin-threshold-picker.css`
  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Beschreibung:** Spezifische Stile für die Auswahlmasken für Länder- und Kundengruppenschwellenwerte.
- `smartfreeshippingpro/views/css/admin-visual-designer.css`
  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Beschreibung:** Stile für die visuelle Designer-Oberfläche, einschließlich Farbwähler, Vorschau-Elemente und Layout.
- `smartfreeshippingpro/views/css/admin.css`
  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Beschreibung:** Allgemeine Admin-Stile, möglicherweise einschließlich gemeinsamer Elemente, die in verschiedenen Admin-Bereichen des Moduls verwendet werden.
- `smartfreeshippingpro/views/css/front.css`
  - **Umfang:** Styling für Kunden im Front-Office.
  - **Beschreibung:**
    - Haupt-UI-Komponenten: Stile für den Fortschrittsleisten-Container, die Fortschrittsfüllung und die Textnachrichten.
    - Wichtige CSS-Klassenselektoren: Enthält wahrscheinlich Klassen wie `.smartfreeshippingpro-bar`, `.smartfreeshippingpro-progress`, `.smartfreeshippingpro-message`, `.smartfreeshippingpro-sticky`. Entwickler können diese in der `custom.css` ihres Themes oder durch Hinzufügen von benutzerdefiniertem CSS in den erweiterten Einstellungen des Moduls überschreiben.
    - Responsive Design-Regeln für verschiedene Bildschirmgrößen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Admin-Vorlagen (`views/templates/admin/`)**:

  - `smartfreeshippingpro/views/templates/admin/configure.tpl`
    - **Beschreibung:** Die Hauptvorlage für die Konfigurationsseite des Moduls im Back Office. Sie rendert das gesamte Formular, einschließlich allgemeiner Einstellungen, Links zu anderen Untervorlagen für spezifische Abschnitte (wie visueller Designer, Schwellenwertauswahl).
  - `smartfreeshippingpro/views/templates/admin/country-priority.tpl`
    - **Beschreibung:** Wahrscheinlich eine Untervorlage, die innerhalb von `configure.tpl` verwendet wird, um die Priorität länderspezifischer Regeln zu verwalten, wenn mehrere Regeln anwendbar sein könnten (z. B. ein Kunde befindet sich in einem Land mit einer spezifischen Regel, gehört aber auch zu einer Gruppe mit einer anderen Regel).
  - `smartfreeshippingpro/views/templates/admin/country-rules-picker.tpl`
    - **Beschreibung:** Eine Untervorlage für die Oberfläche, in der Administratoren Schwellenwerte für den kostenlosen Versand basierend auf Kundenländern definieren und verwalten.
  - `smartfreeshippingpro/views/templates/admin/group-rules-picker.tpl`
    - **Beschreibung:** Eine Untervorlage für die Oberfläche, in der Administratoren Schwellenwerte für den kostenlosen Versand basierend auf Kundengruppen definieren und verwalten.
  - `smartfreeshippingpro/views/templates/admin/visual-designer.tpl`
    - **Beschreibung:** Eine Untervorlage für die visuelle Designer-Oberfläche, die die HTML-Struktur für die Vorschauleiste und die Eingabefelder (Farbwähler, Schieberegler, Texteingaben) zur Anpassung enthält.
- **Hook-Vorlagen (`views/templates/hook/`)**:

  - `smartfreeshippingpro/views/templates/hook/progress.tpl`
    - **Beschreibung:** Dies ist die primäre Front-Office-Vorlage. Sie enthält die HTML-Struktur für die Fortschrittsleiste für den kostenlosen Versand selbst (z. B. ein `div` für die Leiste, ein `div` für die Fortschrittsfüllung und ein `span` für die dynamische Nachricht).
    - **Gerendert in Hooks:** Diese Vorlage wird in verschiedenen Front-Office-Hooks wie `displayHeader`, `displayFooter`, `displayProductButtons`, `displayShoppingCart`, `displayLeftColumn`, `displayRightColumn` gerendert, abhängig von der Konfiguration des Händlers.
    - **Visuelle Blockausgabe:** Gibt die vollständige, gestylte Fortschrittsleiste mit ihrer dynamischen Nachricht aus.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul scheint keine benutzerdefinierten SQL-Tabellen basierend auf dem Inventar zu erstellen.
  - Konfigurationsdatensätze werden in der `ps_configuration`-Tabelle von PrestaShop gespeichert. Schlüssel würden typischerweise einem Muster wie `SMARTFREESHIPPINGPRO_ENABLED`, `SMARTFREESHIPPINGPRO_THRESHOLD_DEFAULT`, `SMARTFREESHIPPINGPRO_COLOR_BAR`, `SMARTFREESHIPPINGPRO_MESSAGE_NOT_QUALIFIED` usw. folgen.
  - Länder- und gruppenspezifische Regeln könnten als serialisierte Arrays innerhalb eines einzelnen `ps_configuration`-Eintrags oder möglicherweise in einer einfachen benutzerdefinierten Tabelle gespeichert werden, wenn die Struktur komplex ist, obwohl das Inventar darauf hindeutet, dass `ObjectModel` nicht verwendet wird.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert im `<head>`-Bereich oder ganz oben im `<body>`. | Fügt CSS/JS-Assets und/oder den HTML-Code der Fortschrittsleiste ein (insbesondere für feste Leisten). |
| `displayFooter` | Rendert am Ende des `<body>` vor dem schließenden Tag. | Fügt CSS/JS-Assets und/oder den HTML-Code der Fortschrittsleiste ein. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste des Shops. | Zeigt die Fortschrittsleiste in der linken Spalte an. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste des Shops. | Zeigt die Fortschrittsleiste in der rechten Spalte an. |
| `displayProductButtons` | Rendert in der Nähe der Schaltfläche „In den Warenkorb“ auf Produktseiten. | Zeigt die Fortschrittsleiste direkt auf Produktseiten an. |
| `displayShoppingCart` | Rendert auf der Warenkorb-Übersichtsseite. | Zeigt die Fortschrittsleiste auf der Warenkorbseite an, um weitere Käufe zu fördern. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) festlegt. | Fügt Front-Office-spezifische CSS- und JavaScript-Dateien ein. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) festlegt. | Fügt Back-Office-spezifische CSS- und JavaScript-Dateien für die Konfigurationsseite ein. |
| `actionCartSave` | Wird ausgeführt, nachdem ein Warenkorb gespeichert wurde (z. B. Artikel hinzugefügt/entfernt). | Löst das Front-Office-JS aus, um die Fortschrittsleiste über AJAX zu aktualisieren. |
| `actionObjectCartUpdateAfter` | Wird ausgeführt, nachdem ein Warenkorbobjekt aktualisiert wurde. | Ähnlich wie `actionCartSave`, wird verwendet, um Updates auszulösen. |
| `actionObjectOrderAddAfter` | Wird ausgeführt, nachdem eine neue Bestellung hinzugefügt wurde. | Potenziell für A/B-Testanalysen zur Verfolgung von Konversionen verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Modul Free Shipping Progress Bar Pro wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul reibungslos und effektiv funktioniert.

- **Updates abrufen:** Melden Sie sich in Ihrem MyPresta.eu-Konto an und navigieren Sie zu Ihrem Bestellverlauf und Download-Bereich, um die aktuellste Version des Moduls zu erhalten.
- **Technischer Support:** Wenn Sie auf Probleme stoßen, Fragen haben oder Unterstützung bei der Konfiguration benötigen, eröffnen Sie bitte ein Support-Ticket über Ihr MyPresta.eu-Kundenkonto. Unser Expertenteam hilft Ihnen gerne weiter.
