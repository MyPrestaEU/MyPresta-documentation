---
title: "Combinations List Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Combinations List Free von MyPresta.eu."
sidebar:
  label: "Combinations List Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Combinations List Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/combinations-list-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/combinations-list-free/)
>
> ---


# Combinations List Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich, aber dieses Modul hat keine spezifischen exotischen Anforderungen über eine Standard-PrestaShop-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Combinations List Free“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt steuert das Gesamtverhalten und Aussehen der Kombinationsliste auf Ihren Produktseiten.

  - **Kombinationsliste auf Produktseite anzeigen:**

    - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Das Modul versucht, die Kombinationsliste auf Produktseiten gemäß Ihren anderen Einstellungen anzuzeigen.
      - *Wenn deaktiviert (NEIN):* Das Modul ist inaktiv, und Ihre Produktseiten kehren zu den Standard-Kombinationsselektoren (Dropdowns) von PrestaShop zurück.
    - **Empfohlener Wert:** JA (um das Modul zu verwenden).
    - **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder es vorübergehend deaktivieren möchten, ohne es zu deinstallieren, stellen Sie dies auf NEIN.
  - **Hook zum Anzeigen der Kombinationsliste:**

    - **Was diese Einstellung bewirkt:** Bestimmt, wo auf der Produktseite die Kombinationsliste erscheinen wird. Dies ist entscheidend für die visuelle Integration der Liste in Ihr Theme.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf `displayProductButtons` (oder ähnlichen produktbezogenen Hook) eingestellt:* Die Liste erscheint typischerweise in der Nähe des „In den Warenkorb“-Buttons oder des Produktpreises, oft unter den Hauptproduktdetails.
      - *Wenn auf `displayProductExtraContent` (oder ähnlichen tabbezogenen Hook) eingestellt:* Die Liste erscheint innerhalb eines neuen oder bestehenden Produkt-Tabs, wodurch der Hauptproduktbeschreibungsbereich sauberer bleibt.
      - *Wenn auf `displayFooterProduct` (oder ähnlichen Footer-Hook) eingestellt:* Die Liste erscheint ganz unten auf der Produktseite.
    - **Empfohlener Wert:** Experimentieren Sie mit verschiedenen Hooks, um die beste visuelle Integration mit Ihrem spezifischen Theme zu finden. `displayProductButtons` oder `displayProductExtraContent` sind gängige Optionen.
    - **Händlerszenario / Beispiel:** Wenn Ihre Produktseite bereits lang ist, kann das Platzieren der Liste in einem `displayProductExtraContent`-Tab die Seite übersichtlicher machen. Wenn Sie die Liste sofort sichtbar haben möchten, ist ein Hook wie `displayProductButtons` besser.
  - **Kombinationsbild anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob ein kleines, spezifisches Bild für jede Kombination in der Liste angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Wenn Sie spezifische Bilder für jede Produktkombination hochgeladen haben, erscheinen diese neben der jeweiligen Kombination in der Liste.
      - *Wenn deaktiviert (NEIN):* Es werden nur der Kombinationsname, die Referenz und der Preis ohne Bild angezeigt.
    - **Empfohlener Wert:** JA, wenn Sie einzigartige Bilder für Kombinationen haben. Dies hilft Kunden erheblich, das genaue Produkt zu visualisieren, das sie auswählen.
    - **Händlerszenario / Beispiel:** Bei Kleidung ist die Anzeige eines roten T-Shirt-Bildes für die Kombination „Rot - Groß“ viel klarer als nur Text.
  - **Kombinationsreferenz anzeigen:**

    - **Was diese Einstellung bewirkt:** Bestimmt, ob die interne Referenznummer für jede Kombination angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Die Referenz der Kombination (z. B. SKU) ist in der Liste sichtbar.
      - *Wenn deaktiviert (NEIN):* Die Referenznummer wird ausgeblendet.
    - **Empfohlener Wert:** JA, besonders für B2B-Stores oder Produkte, bei denen Kunden oft nach Referenz bestellen.
    - **Händlerszenario / Beispiel:** Ein Kunde, der ein bestimmtes Teil nachbestellt, kennt es möglicherweise unter seiner Referenznummer, was das Auffinden erleichtert.
  - **Kombinationsmengen-Eingabe anzeigen:**

    - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, die Menge für jede Kombination direkt in der Liste anzugeben, anstatt nur einzeln hinzuzufügen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Ein Mengeneingabefeld (z. B. ein Zahlenfeld) erscheint neben jeder Kombination, sodass Kunden eine gewünschte Menge eingeben können, bevor sie auf „In den Warenkorb“ klicken.
      - *Wenn deaktiviert (NEIN):* Der „In den Warenkorb“-Button fügt typischerweise eine Einheit der Kombination zum Warenkorb hinzu.
    - **Empfohlener Wert:** JA, für die meisten Stores, da dies die Effizienz für Kunden verbessert, die mehrere Einheiten derselben Kombination kaufen.
    - **Händlerszenario / Beispiel:** Ein Kunde, der 5 Einheiten „Blau - Mittel“ und 3 Einheiten „Grün - Groß“ kauft, kann dies schnell aus der Liste tun.
  - **Kombinationspreis anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob der Preis jeder einzelnen Kombination in der Liste angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Preis für jede spezifische Kombination wird angezeigt.
      - *Wenn deaktiviert (NEIN):* Der Preis wird ausgeblendet, und Kunden sehen möglicherweise nur den Hauptproduktpreis oder müssen ihn ableiten.
    - **Empfohlener Wert:** JA. Preistransparenz ist entscheidend für das Kundenvertrauen und die Entscheidungsfindung.
    - **Händlerszenario / Beispiel:** Wenn verschiedene Größen oder Farben unterschiedliche Preise haben, ist die Anzeige des genauen Preises für jede Kombination unerlässlich.
  - **Kombinationsverfügbarkeit anzeigen:**

    - **Was diese Einstellung bewirkt:** Zeigt den Lagerstatus (z. B. „Auf Lager“, „Nicht auf Lager“, „Letzte Artikel!“) für jede Kombination an.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Kunden sehen den Verfügbarkeitsstatus für jede Kombination, was ihnen hilft, fundierte Kaufentscheidungen zu treffen.
      - *Wenn deaktiviert (NEIN):* Der Lagerstatus wird in der Liste nicht angezeigt.
    - **Empfohlener Wert:** JA. Dies verhindert, dass Kunden nicht vorrätige Artikel in ihren Warenkorb legen, was Frustration und abgebrochene Warenkörbe reduziert.
    - **Händlerszenario / Beispiel:** Ein Kunde kann sofort sehen, dass das Hemd „Rot - Groß“ nicht auf Lager ist und stattdessen „Blau - Groß“ wählen.
  - **Kombinationsbeschreibung anzeigen:**

    - **Was diese Einstellung bewirkt:** Wenn Sie spezifische Beschreibungen für jede Kombination haben, steuert diese Einstellung deren Anzeige.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Jede einzigartige Beschreibung, die mit einer Kombination verbunden ist, wird in der Liste angezeigt.
      - *Wenn deaktiviert (NEIN):* Kombinationsspezifische Beschreibungen werden ausgeblendet.
    - **Empfohlener Wert:** JA, wenn Ihre Kombinationen unterschiedliche Beschreibungen haben, die dem Kunden bei der Entscheidung einen Mehrwert bieten.
    - **Händlerszenario / Beispiel:** Bei einem anpassbaren Produkt könnte eine Kombinationsbeschreibung die spezifischen Materialien detaillieren, die für diese Variante verwendet werden.
  - **Text des „In den Warenkorb“-Buttons:**

    - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den Text anzupassen, der auf dem „In den Warenkorb“-Button für jede Kombination angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Bei Änderung:* Der Button-Text wird auf Ihre benutzerdefinierte Phrase aktualisiert.
      - *Wenn leer gelassen:* Der Standardtext „In den Warenkorb“ (oder der Standardtext Ihres Themes) wird verwendet.
    - **Empfohlener Wert:** „In den Warenkorb“ oder „Jetzt kaufen“ zur Klarheit. Halten Sie es prägnant.
    - **Händlerszenario / Beispiel:** Sie könnten es in „Auswählen & Kaufen“ ändern, wenn Sie die Auswahl vor dem Kauf betonen möchten.
  - **Kombinationen als Tabelle anzeigen:**

    - **Was diese Einstellung bewirkt:** Schaltet die visuelle Darstellung der Kombinationen von einer einfachen Liste zu einer strukturierten HTML-Tabelle um.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Kombinationen werden in einem Tabellenformat mit Spalten für Bild, Name, Referenz, Preis, Menge und „In den Warenkorb“ präsentiert. Dies ist oft kompakter und organisierter für viele Kombinationen.
      - *Wenn deaktiviert (NEIN):* Kombinationen werden als weniger strukturierte Liste angezeigt, typischerweise eine Kombination pro Zeile.
    - **Empfohlener Wert:** JA, in den meisten Fällen, da eine Tabelle eine bessere Lesbarkeit und Ausrichtung bietet, insbesondere bei vielen Optionen.
    - **Händlerszenario / Beispiel:** Wenn Sie über 20 Kombinationen haben, erleichtert eine Tabelle das Scannen und Vergleichen erheblich.
  - **Kombinationen als Tab anzeigen:**

    - **Was diese Einstellung bewirkt:** Diese Einstellung ist wahrscheinlich ein Legacy-Merkmal oder ein spezifisches Implementierungsdetail. Angesichts der Einstellung `Hook to display the combinations list` könnte dies redundant sein oder sich auf eine bestimmte Vorlage beziehen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Könnte die Kombinationsliste in eine tabähnliche Struktur zwingen, möglicherweise den gewählten Hook überschreiben, wenn dieser Hook nicht natürlich einen Tab erstellt.
      - *Wenn deaktiviert (NEIN):* Die Anzeige folgt dem gewählten Hook direkter.
    - **Empfohlener Wert:** Im Allgemeinen NEIN, es sei denn, Sie möchten ausdrücklich einen Tab und Ihr gewählter Hook bietet ihn nicht. Verlassen Sie sich für die Platzierung auf die Einstellung „Hook zum Anzeigen der Kombinationsliste“.
    - **Händlerszenario / Beispiel:** Wenn Ihr Theme nicht automatisch Tabs für `displayProductExtraContent` erstellt, könnte das Aktivieren dieser Option ein tabähnliches Erscheinungsbild erzwingen.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Kombinationsliste auf Produktseite anzeigen | JA | Hauptschalter zum Aktivieren/Deaktivieren der Front-Office-Anzeige des Moduls. |
| Modulkonfiguration | Hook zum Anzeigen der Kombinationsliste | `displayProductButtons` oder `displayProductExtraContent` | Bestimmt die genaue Position der Liste auf der Produktseite. |
| Modulkonfiguration | Kombinationsbild anzeigen | JA (wenn Bilder vorhanden) | Zeigt einzigartige Bilder für jede Kombination an. |
| Modulkonfiguration | Kombinationsreferenz anzeigen | JA | Zeigt die SKU/Referenznummer für jede Kombination an. |
| Modulkonfiguration | Kombinationsmengen-Eingabe anzeigen | JA | Ermöglicht Kunden die Eingabe von Mengen für jede Kombination. |
| Modulkonfiguration | Kombinationspreis anzeigen | JA | Zeigt den spezifischen Preis für jede Kombination an. |
| Modulkonfiguration | Kombinationsverfügbarkeit anzeigen | JA | Zeigt den Lagerstatus (z. B. „Auf Lager“) für jede Kombination an. |
| Modulkonfiguration | Kombinationsbeschreibung anzeigen | JA (wenn Beschreibungen vorhanden) | Zeigt einzigartige Beschreibungen für jede Kombination an. |
| Modulkonfiguration | Text des „In den Warenkorb“-Buttons | „In den Warenkorb“ | Passt den Text auf den „In den Warenkorb“-Buttons an. |
| Modulkonfiguration | Kombinationen als Tabelle anzeigen | JA | Präsentiert Kombinationen in einem strukturierten Tabellenformat für bessere Lesbarkeit. |
| Modulkonfiguration | Kombinationen als Tab anzeigen | NEIN | (Wahrscheinlich Legacy/spezifisch) Steuert die tabähnliche Anzeige; bevorzugen Sie die Hook-Einstellung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Kombinationsliste wird auf meiner Produktseite nicht angezeigt.**
**A1:**

- Überprüfen Sie zuerst, ob „Kombinationsliste auf Produktseite anzeigen“ in der Modulkonfiguration auf JA eingestellt ist.
- Überprüfen Sie als Nächstes die Einstellung „Hook zum Anzeigen der Kombinationsliste“. Einige Themes rendern möglicherweise nicht alle Standard-PrestaShop-Hooks auf die gleiche Weise. Versuchen Sie, zu einem anderen Hook zu wechseln (z. B. `displayProductButtons`, `displayProductExtraContent`, `displayFooterProduct`), um zu sehen, ob er erscheint.
- Stellen Sie sicher, dass das Produkt, das Sie anzeigen, tatsächlich Kombinationen definiert hat.
- Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Performance > Cache leeren).

**F2: Meine Kombinationsbilder werden in der Liste nicht angezeigt.**
**A2:**

- Stellen Sie sicher, dass „Kombinationsbild anzeigen“ in den Moduleinstellungen aktiviert ist.
- Entscheidend ist, dass Sie spezifische Bilder für jede Kombination im PrestaShop-Produkteditor hochgeladen haben müssen (Produkt > Kombinationen-Tab > Jede Kombination bearbeiten > Bild hinzufügen). Wenn einer Kombination kein spezifisches Bild zugewiesen ist, wird es nicht angezeigt.

**F3: Die Liste sieht unordentlich aus oder passt nicht zum Design meines Themes.**
**A3:**

- Versuchen Sie, „Kombinationen als Tabelle anzeigen“ zu aktivieren, falls dies noch nicht geschehen ist. Dies bietet oft ein strukturierteres und optisch ansprechenderes Layout.
- Das Modul verwendet sein eigenes CSS. Das CSS Ihres Themes könnte es überschreiben oder damit in Konflikt stehen. Möglicherweise müssen Sie einen Webentwickler beauftragen, das CSS des Moduls (`mycombtabfree.css`) anzupassen oder benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um es nach Ihren Wünschen zu gestalten.
- Experimentieren Sie mit verschiedenen Hooks. Einige Hooks könnten eine bessere Standardformatierung von Ihrem Theme haben.

**F4: Kann ich den Text des „In den Warenkorb“-Buttons in andere Sprachen übersetzen?**
**A4:** Ja. Gehen Sie im PrestaShop Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Combinations List Free“ aus dem Modul-Dropdown. Sie können dann den Button-Text und alle anderen modulspezifischen Phrasen übersetzen.

**F5: Warum zeigen einige Kombinationen „Nicht auf Lager“ an, obwohl ich Lagerbestand habe?**
**A5:**

- Überprüfen Sie die Lagerbestands-Einstellungen Ihres Produkts im PrestaShop-Produkteditor. Stellen Sie sicher, dass die spezifische Kombination eine verfügbare Menge hat.
- Überprüfen Sie Ihre globalen Lagerbestandsverwaltungs-Einstellungen (Shop-Parameter > Produkteinstellungen > Produktlager).
- Leeren Sie Ihren PrestaShop-Cache, nachdem Sie Lagerbestandsanpassungen vorgenommen haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Combinations List Free“ (`mycombtabfree`) ist ein Standard-PrestaShop-Modul, das zur Verbesserung der Front-Office-Produktseite entwickelt wurde. Es arbeitet hauptsächlich, indem es sich in verschiedene Anzeigepunkte auf der Produktseite einklinkt, um seine benutzerdefinierte HTML-Struktur für Produktkombinationen zu injizieren. Das Modul folgt einem grundlegenden MVC-ähnlichen Muster innerhalb des PrestaShop-Modul-Frameworks, wobei eine Hauptmodulklasse für die Konfiguration und Hook-Registrierung und Smarty-Templates für die Darstellung der Front-Office-Ausgabe verwendet werden. Es nutzt bestehende PrestaShop-Kernfunktionen zum Abrufen von Produkt- und Kombinationsdaten.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Alle Konfigurationen werden über die Methode `getContent()` der Hauptmodulklasse gehandhabt, und die Front-Office-Darstellung erfolgt direkt über Hooks.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/`. Es verlässt sich vollständig auf die Kernklassen `Product` und `Combination` von PrestaShop, um Daten abzurufen und anzuzeigen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`mycombtabfree/js/atc.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript ist für die „In den Warenkorb“-Funktionalität der vom Modul angezeigten Kombinationen verantwortlich. Es fängt wahrscheinlich Klickereignisse auf den benutzerdefinierten „In den Warenkorb“-Buttons ab, die vom Modul generiert werden.
  - **Funktionalität:**
    - Bindet Event-Listener an die „In den Warenkorb“-Buttons innerhalb der Kombinationsliste/-tabelle.
    - Wenn ein Button geklickt wird, sammelt es die `id_product`, `id_product_attribute` (Kombinations-ID) und möglicherweise die Menge aus dem zugehörigen Eingabefeld.
    - Es sendet dann eine AJAX-Anfrage an den PrestaShop-Kern `cart`-Controller (oder einen ähnlichen Endpunkt), um die ausgewählte Kombination zum Warenkorb hinzuzufügen.
    - Es könnte auch den Warenkorb-Block aktualisieren, Benachrichtigungen (Erfolg/Fehler) anzeigen oder anderes UI-Feedback nach dem AJAX-Aufruf verarbeiten.
    - Es verwendet wahrscheinlich jQuery oder die nativen `prestashop.on`-Ereignisse von PrestaShop für dynamische Updates.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`mycombtabfree/css/admin.css`**

  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Zweck:** Enthält Stile speziell für die Konfigurationsseite des Moduls im PrestaShop Back Office. Dies kann Styling für Formularelemente, Warnungen oder Layoutanpassungen umfassen, um die Konfigurationsoberfläche benutzerfreundlich zu gestalten.
  - **Wichtige Selektoren:** Zielt wahrscheinlich auf Elemente innerhalb der `getContent()`-Ausgabe des Moduls ab, wie z. B. `.panel`, `.form-group`, `.alert` usw., um eine konsistente Admin-Benutzeroberfläche zu gewährleisten.
- **`mycombtabfree/css/mycombtabfree.css`**

  - **Umfang:** Front-Office-Kunden-Styling.
  - **Zweck:** Bietet das Kern-Visual-Styling für die Kombinationsliste/-tabelle, die auf der Produktseite angezeigt wird. Dies umfasst Layout, Typografie, Farben und Responsivität.
  - **Wichtige Selektoren:**
    - `.mycombtabfree-container`: Haupt-Wrapper für die Kombinationsliste.
    - `.mycombtabfree-table`: Stile für das `<table>`-Element, wenn „Kombinationen als Tabelle anzeigen“ aktiviert ist.
    - `.mycombtabfree-row`, `.mycombtabfree-cell`: Stile für Tabellenzeilen und -zellen.
    - `.mycombtabfree-image`, `.mycombtabfree-name`, `.mycombtabfree-reference`, `.mycombtabfree-price`, `.mycombtabfree-qty`, `.mycombtabfree-atc`: Spezifische Stile für jedes Kombinationsdatum.
    - Media Queries für responsive Anpassungen auf kleineren Bildschirmen.
  - **Entwickler-Override:** Entwickler können diese Stile in den CSS-Dateien ihres benutzerdefinierten Themes überschreiben, indem sie spezifischere Selektoren verwenden oder diese Datei direkt ändern (obwohl letzteres für die Update-Freundlichkeit nicht empfohlen wird).

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`mycombtabfree/views/templates/admin/configure.tpl`**

  - **Umfang:** Admin-Konfigurationspanel.
  - **Zweck:** Rendert das HTML-Formular für die Konfigurationseinstellungen des Moduls im PrestaShop Back Office. Dieses Template wird von der Methode `getContent()` der Hauptmodulklasse geladen.
  - **Inhalt:** Enthält Formularfelder (Kontrollkästchen, Texteingaben, Auswahl-Dropdowns), die den in Abschnitt 4.1 beschriebenen Einstellungen entsprechen.
- **`mycombtabfree/views/templates/admin/pro-upsell.tpl`**

  - **Umfang:** Admin-Konfigurationspanel.
  - **Zweck:** Zeigt Werbeinhalte oder ein Upsell-Banner für eine „Pro“-Version des Moduls innerhalb der Back-Office-Konfiguration an. Dies ist eine gängige Praxis für kostenlose Module.
- **`mycombtabfree/views/templates/hook/pro-banner.tpl`**

  - **Umfang:** Front-Office-Hook.
  - **Zweck:** Rendert ein Werbebanner für die „Pro“-Version des Moduls, das wahrscheinlich in einem weniger aufdringlichen Front-Office-Hook (z. B. `displayFooter` oder `displayLeftColumn`) angezeigt wird.
- **`mycombtabfree/views/templates/hook/tab.tpl`**

  - **Umfang:** Front-Office-Hook.
  - **Zweck:** Dieses Template wird wahrscheinlich verwendet, wenn die Einstellung „Kombinationen als Tab anzeigen“ aktiviert ist oder wenn das Modul an einer Position eingehakt ist, die natürlich einen Tab erstellt (z. B. `displayProductExtraContent`). Es würde die Struktur für einen Produkt-Tab enthalten, innerhalb dessen die eigentliche Kombinationsliste/-tabelle gerendert würde.
- **`mycombtabfree/views/templates/hook/table.tpl`**

  - **Umfang:** Front-Office-Hook.
  - **Zweck:** Dies ist das primäre Template, das für das Rendern der eigentlichen Liste oder Tabelle von Produktkombinationen im Front Office verantwortlich ist. Es iteriert durch die verfügbaren Kombinationen für ein bestimmtes Produkt und zeigt jede einzelne gemäß den Konfigurationseinstellungen des Moduls an (z. B. Anzeige von Bild, Referenz, Preis, Mengeneingabe, „In den Warenkorb“-Button).
  - **Logik:** Enthält Smarty-Schleifen (`{foreach}`) zum Iterieren über das `$combinations`-Array, bedingte Anweisungen (`{if}`) zum Anzeigen von Elementen basierend auf Moduleinstellungen und Variablen wie `$combination.id_product_attribute`, `$combination.name`, `$combination.price` usw.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`. Die Konfigurationsschlüssel würden typischerweise einem Muster wie `MYCOMBTABFREE_SETTING_NAME` folgen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS (`mycombtabfree.css`) und JavaScript (`atc.js`) Assets für das Front-Office zu registrieren. |
| `displayProductButtons` | In der Nähe des „In den Warenkorb“-Buttons auf der Produktseite. | Ein gängiger Hook zum Anzeigen der Kombinationsliste direkt unter den Produktdetails. |
| `displayProductExtraContent` | Innerhalb des Produkt-Tabs-Bereichs auf der Produktseite. | Ermöglicht die Anzeige der Kombinationsliste in einem eigenen dedizierten Tab. |
| `displayFooterProduct` | Am unteren Rand des Produktseiteninhalts. | Ein weiterer möglicher Ort für die Kombinationsliste, oft weniger prominent. |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller seine Ausgabe rendert. | Wird verwendet, um modulspezifische CSS- und JS-Dateien zur Seite hinzuzufügen. |
| `moduleRoutes` | Während der Initialisierung der URL-Umschreibung. | (Nicht explizit von diesem Modul verwendet, aber ein gängiger Hook für Module mit benutzerdefinierten URLs). |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwickler-Support für das Modul „Combinations List Free“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Stellen Sie sicher, dass Sie die neueste Version, die mit Ihrer PrestaShop-Installation kompatibel ist, aus Ihrer Bestellhistorie herunterladen.
