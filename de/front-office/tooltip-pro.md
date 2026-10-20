---
title: "Tooltip Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Tooltip Pro von MyPresta.eu."
sidebar:
  label: "Tooltip Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Tooltip Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/tooltip-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/tooltip-pro/)
>
> ---


# Tooltip Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Tooltip Pro)

Dies ist der Hauptkonfigurationsbildschirm für das Modul Tooltip Pro, auf dem Sie dessen Gesamtverhalten und Erscheinungsbild steuern.

- **Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach „Tooltip Pro“ > Klicken Sie auf „Konfigurieren“

#### Einstellungen & Optionen:

1. **Tooltips aktivieren:**

   - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der gesamten Tooltip-Funktionalität in Ihrem Front Office.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (JA):* Tooltips sind in Ihrem Shop gemäß Ihren anderen Einstellungen aktiv.
     - *Wenn deaktiviert (NEIN):* Es werden keine Tooltips in Ihrem Shop angezeigt, unabhängig von den einzelnen Tooltip-Einträgen, die Sie erstellt haben.
   - **Empfohlener Wert:** JA (sobald Sie Ihre Tooltips konfiguriert haben).
   - **Händlerszenario / Beispiel:** Wenn Sie Wartungsarbeiten durchführen oder alle Tooltips vorübergehend deaktivieren möchten, ohne sie zu löschen, stellen Sie dies auf NEIN.
2. **Tooltip-Schlüsselwörter hervorheben:**

   - **Was diese Einstellung bewirkt:** Legt fest, ob der Text, der einen Tooltip auslöst, auf Ihrer Website visuell hervorgehoben werden soll.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (JA):* Die von Ihnen für Tooltips definierten Schlüsselwörter erhalten einen visuellen Stil (z. B. eine gepunktete Unterstreichung, Fettdruck oder eine bestimmte Farbe, abhängig vom CSS Ihres Themes oder der Standardformatierung des Moduls). Dies hilft Kunden, interaktive Elemente zu identifizieren.
     - *Wenn deaktiviert (NEIN):* Die Schlüsselwörter erscheinen als normaler Text, aber das Hovern darüber löst den Tooltip weiterhin aus. Dies kann die Auffindbarkeit von Tooltips verringern.
   - **Empfohlener Wert:** JA.
   - **Händlerszenario / Beispiel:** Wenn Sie dies aktivieren, wird Ihren Kunden klar, welche Wörter interaktiv sind, und sie werden ermutigt, die hilfreichen Informationen zu entdecken. Wenn Sie ein sehr minimalistisches Design bevorzugen und erwarten, dass Benutzer Tooltips auf natürliche Weise entdecken, können Sie es deaktivieren.
3. **Tooltip-Platzierung:**

   - **Was diese Einstellung bewirkt:** Steuert, wo das Tooltip-Popup relativ zum Schlüsselworttext erscheint.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Optionen (z. B. Oben, Unten, Links, Rechts, Auto):* Die Wahl von „Oben“ lässt den Tooltip über dem Text erscheinen, „Unten“ darunter usw. „Auto“ versucht, den Tooltip intelligent zu platzieren, um zu vermeiden, dass er außerhalb des Bildschirms gerät.
   - **Empfohlener Wert:** Auto.
   - **Händlerszenario / Beispiel:** „Auto“ ist im Allgemeinen die beste Wahl, da es sich an verschiedene Bildschirmgrößen und Inhaltslayouts anpasst. Wenn Sie feststellen, dass Tooltips in einem bestimmten Bereich wichtige Inhalte ständig verdecken, können Sie mit einer festen Platzierung wie „Unten“ experimentieren.
4. **Tooltip-Animation:**

   - **Was diese Einstellung bewirkt:** Wählt den Animationseffekt aus, wenn ein Tooltip erscheint und verschwindet.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Optionen (z. B. Fade, Grow, Swing, Slide, Fall):* Jede Option bietet einen anderen visuellen Übergang. „Fade“ ist ein einfaches Ein- und Ausblenden, „Grow“ expandiert usw.
   - **Empfohlener Wert:** Fade oder Grow.
   - **Händlerszenario / Beispiel:** Eine subtile Animation wie „Fade“ oder „Grow“ verleiht ein elegantes Gefühl, ohne abzulenken. Vermeiden Sie übermäßig komplexe Animationen, die die Benutzererfahrung verlangsamen oder nicht zu Ihrer Marke passen könnten.
5. **Tooltip-Theme:**

   - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl eines vordefinierten visuellen Themes für Ihre Tooltips. Dies beeinflusst Farben, Ränder und die allgemeine Gestaltung.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Optionen (z. B. Standard, Hell, Dunkel, Umrandet, Punk):* Jedes Theme wendet einen anderen Satz von CSS-Stilen an.
   - **Empfohlener Wert:** Standard oder Hell.
   - **Händlerszenario / Beispiel:** Wählen Sie ein Theme, das am besten zum Gesamtdesign und Branding Ihres Shops passt. „Hell“ oder „Standard“ sind oft gute Ausgangspunkte. Wenn Sie eine dunkle Website haben, könnte „Dunkel“ passender sein.
6. **Tooltip maximale Breite (Pixel):**

   - **Was diese Einstellung bewirkt:** Legt die maximale Breite für das Tooltip-Popup-Feld in Pixeln fest.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Eingabe eines Wertes (z. B. 300):* Der Tooltip überschreitet diese Breite nicht und bricht den Text bei Bedarf um.
     - *Leer lassen oder 0:* Der Tooltip passt seine Größe automatisch an den Inhalt an, was manchmal zu sehr breiten Tooltips führen kann.
   - **Empfohlener Wert:** 250-350 Pixel.
   - **Händlerszenario / Beispiel:** Das Festlegen einer angemessenen maximalen Breite stellt sicher, dass Tooltips nicht zu breit werden und sich über den Bildschirm erstrecken, insbesondere auf kleineren Geräten oder in schmalen Spaltenlayouts.
7. **Verzögerung vor dem Anzeigen (Millisekunden):**

   - **Was diese Einstellung bewirkt:** Die Zeit (in Millisekunden), die ein Benutzer über einem Schlüsselwort verweilen muss, bevor der Tooltip erscheint.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Höherer Wert (z. B. 500ms):* Tooltips erscheinen nach einer längeren Verzögerung, wodurch verhindert wird, dass sie zu schnell aufpoppen, wenn ein Benutzer nur die Maus über die Seite bewegt.
     - *Niedrigerer Wert (z. B. 0ms):* Tooltips erscheinen sofort.
   - **Empfohlener Wert:** 200-300.
   - **Händlerszenario / Beispiel:** Eine leichte Verzögerung (z. B. 200ms) sorgt für eine reibungslosere Benutzererfahrung, da sie verhindert, dass versehentliche Tooltips schnell erscheinen und verschwinden.
8. **Verzögerung vor dem Ausblenden (Millisekunden):**

   - **Was diese Einstellung bewirkt:** Die Zeit (in Millisekunden), die der Tooltip sichtbar bleibt, nachdem der Benutzer die Maus vom Schlüsselwort wegbewegt hat.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Höherer Wert (z. B. 200ms):* Der Tooltip bleibt für kurze Zeit sichtbar, sodass Benutzer ihre Maus leicht bewegen können, ohne dass der Tooltip sofort verschwindet.
     - *Niedrigerer Wert (z. B. 0ms):* Der Tooltip verschwindet sofort, wenn die Maus das Schlüsselwort verlässt.
   - **Empfohlener Wert:** 100-200.
   - **Händlerszenario / Beispiel:** Eine kleine Verzögerung hier kann hilfreich sein, wenn ein Benutzer versehentlich die Maus vom Schlüsselwort wegbewegt, aber den Tooltip weiterlesen möchte.
9. **Zulässige Seitentypen für Tooltips:**

   - **Was diese Einstellung bewirkt:** Legt fest, auf welchen Seitentypen Tooltips aktiv sein sollen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Kontrollkästchen (z. B. Produktseiten, Kategorieseiten, CMS-Seiten, Alle Seiten):* Wählen Sie die spezifischen Seitentypen aus, auf denen Ihre Tooltips funktionieren sollen.
     - *Auswahl von „Alle Seiten“:* Tooltips sind überall in Ihrem Shop aktiv.
   - **Empfohlener Wert:** Wählen Sie nur die Seitentypen aus, auf denen Sie Tooltips wirklich benötigen, um unnötige Verarbeitung auf anderen Seiten zu vermeiden.
   - **Händlerszenario / Beispiel:** Wenn Sie Tooltips hauptsächlich für Produktspezifikationen verwenden, aktivieren Sie möglicherweise nur „Produktseiten“. Wenn Sie viele Fachbegriffe auf Ihrer gesamten Website haben, könnte „Alle Seiten“ angemessen sein.

### 2.2 Dedizierter Admin-Bildschirm: Tooltip-Liste (Back Office > Tooltip Pro > Tooltips)

Dieser Bildschirm ist der Ort, an dem Sie alle einzelnen Tooltips verwalten, die Sie in Ihrem Shop erstellen und anzeigen möchten. Er dient als zentrale Anlaufstelle zum Hinzufügen, Bearbeiten und Löschen von Tooltip-Einträgen.

- **Bildschirmname & Menüpfad:** Back Office > Tooltip Pro > Tooltips
- **Verfügbare Aktionen & Einstellungen:**
  - **Tooltip-Listen-Tabelle:** Zeigt eine Liste aller Ihrer erstellten Tooltips an, typischerweise mit dem Schlüsselwort, dem Inhalt und seinem Status (aktiviert/deaktiviert).
  - **Neuen Tooltip hinzufügen-Schaltfläche:** Klicken Sie hier, um einen neuen Tooltip-Eintrag zu erstellen.
  - **Bearbeiten/Löschen-Aktionen:** Jeder Tooltip in der Liste hat Aktionsschaltflächen (z. B. ein Bleistiftsymbol für „Bearbeiten“, ein Papierkorbsymbol für „Löschen“), um einzelne Einträge zu verwalten.
  - **Massenaktionen:** Oft gibt es Optionen, um mehrere ausgewählte Tooltips gleichzeitig zu aktivieren, deaktivieren oder zu löschen.

#### Beim Hinzufügen/Bearbeiten eines Tooltips:

1. **Schlüsselwort:**

   - **Was diese Einstellung bewirkt:** Dies ist das genaue Wort oder die Phrase, die, wenn sie auf Ihrer Website gefunden wird, den Tooltip auslöst.
   - **Auswirkung der Änderung dieser Einstellung:** Das Modul sucht auf Ihren aktivierten Seiten nach diesem spezifischen Text. Die Groß-/Kleinschreibung kann je nach interner Logik des Moduls gelten (gehen Sie für beste Ergebnisse von Groß-/Kleinschreibung aus).
   - **Empfohlener Wert:** Seien Sie präzise. Verwenden Sie die genaue Schreibweise und Groß-/Kleinschreibung, wie sie auf Ihrer Website erscheint.
   - **Händlerszenario / Beispiel:** Wenn Sie „Bio-Baumwolle“ erklären möchten, geben Sie „Bio-Baumwolle“ ein. Wenn Sie „bio-baumwolle“ eingeben, wird es möglicherweise nicht bei „Bio-Baumwolle“ ausgelöst.
2. **Tooltip-Inhalt:**

   - **Was diese Einstellung bewirkt:** Dies ist die Information, die im Tooltip-Popup angezeigt wird. Es handelt sich typischerweise um einen Rich-Text-Editor (WYSIWYG), der verschiedene Inhaltstypen zulässt.
   - **Auswirkung der Änderung dieser Einstellung:** Was immer Sie hier eingeben, wird dem Kunden angezeigt, wenn er über das Schlüsselwort fährt.
   - **Empfohlener Wert:** Halten Sie es prägnant und informativ. Verwenden Sie Bilder, Videos oder Links sparsam, um den Benutzer nicht zu überfordern.
   - **Händlerszenario / Beispiel:** Für „Bio-Baumwolle“ könnten Sie hinzufügen: „Bio-Baumwolle wird ohne schädliche Chemikalien, Pestizide oder GVO angebaut, was sie besser für die Umwelt und Ihre Haut macht. [Link zu Blogbeitrag über Nachhaltigkeit].“
3. **Aktiv:**

   - **Was diese Einstellung bewirkt:** Steuert, ob dieser spezifische Tooltip-Eintrag aktiv oder inaktiv ist.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (JA):* Dieser einzelne Tooltip wird in Ihrem Shop angezeigt.
     - *Wenn deaktiviert (NEIN):* Dieser Tooltip wird nicht angezeigt, selbst wenn das Hauptmodul aktiviert ist.
   - **Empfohlener Wert:** JA (für Tooltips, die Sie anzeigen möchten).
   - **Händlerszenario / Beispiel:** Sie könnten einen Tooltip vorübergehend deaktivieren, wenn die Informationen veraltet sind oder wenn eine Produktfunktion, die er beschreibt, nicht mehr verfügbar ist, ohne den gesamten Eintrag zu löschen.

- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie damit, häufige Fragen oder verwirrende Begriffe auf Ihren Produktseiten, Kategorieseiten oder wichtigen CMS-Seiten zu identifizieren.
  2. Gehen Sie zu **Back Office > Tooltip Pro > Tooltips**.
  3. Klicken Sie auf „Neuen Tooltip hinzufügen“.
  4. Geben Sie das genaue **Schlüsselwort** ein, das Sie erklären möchten.
  5. Erstellen Sie einen klaren, prägnanten und hilfreichen **Tooltip-Inhalt**.
  6. Stellen Sie sicher, dass **Aktiv** auf JA gesetzt ist.
  7. Speichern Sie Ihre Änderungen.
  8. Testen Sie den Tooltip in Ihrem Front Office, um sicherzustellen, dass er korrekt angezeigt wird und die gewünschten Informationen liefert.
  9. Überprüfen Sie Ihre Tooltips regelmäßig, um sicherzustellen, dass die Informationen korrekt und relevant bleiben.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Tooltips aktivieren | JA | Hauptschalter für die gesamte Tooltip-Funktionalität. |
|  | Tooltip-Schlüsselwörter hervorheben | JA | Markiert Schlüsselwörter visuell im Front-Office. |
|  | Tooltip-Platzierung | Auto | Position des Tooltip-Popups relativ zum Schlüsselwort. |
|  | Tooltip-Animation | Fade / Grow | Visueller Effekt beim Erscheinen/Verschwinden des Tooltips. |
|  | Tooltip-Theme | Standard / Hell | Styling (Farben, Ränder) des Tooltip-Feldes. |
|  | Tooltip maximale Breite (Pixel) | 250-350 | Verhindert, dass Tooltips zu breit werden. |
|  | Verzögerung vor dem Anzeigen (ms) | 200-300 | Zeit, bevor der Tooltip beim Hovern erscheint. |
|  | Verzögerung vor dem Ausblenden (ms) | 100-200 | Zeit, bevor der Tooltip nach dem Hovern verschwindet. |
|  | Zulässige Seitentypen | Nach Bedarf auswählen | Beschränkt Tooltips auf bestimmte Seitentypen (z. B. Produkt, Kategorie). |
| **Tooltip-Liste (Hinzufügen/Bearbeiten)** | Schlüsselwort | Exakter Text | Das spezifische Wort/die Phrase, die den Tooltip auslöst. |
|  | Tooltip-Inhalt | Prägnant, informativ | Die im Tooltip angezeigten Informationen. |
|  | Aktiv | JA | Aktiviert/deaktiviert einen einzelnen Tooltip-Eintrag. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Tooltips werden im Front Office nicht angezeigt, obwohl ich sie erstellt habe.**
A:

1. **Hauptschalter prüfen:** Gehen Sie zu **Module > Modul-Manager > Tooltip Pro konfigurieren**. Stellen Sie sicher, dass „Tooltips aktivieren“ auf JA gesetzt ist.
2. **Status des einzelnen Tooltips prüfen:** Gehen Sie zu **Tooltip Pro > Tooltips**. Stellen Sie sicher, dass der spezifische Tooltip, den Sie erwarten, auf „Aktiv“ gesetzt ist.
3. **Seitentyp prüfen:** Vergewissern Sie sich, dass die Einstellung „Zulässige Seitentypen für Tooltips“ den Typ der Seite enthält, die Sie gerade anzeigen (z. B. wenn Sie sich auf einer Produktseite befinden, muss „Produktseiten“ aktiviert sein).
4. **Schlüsselwort-Übereinstimmung:** Stellen Sie sicher, dass das von Ihnen für den Tooltip eingegebene „Schlüsselwort“ genau mit dem Text in Ihrem Front Office übereinstimmt, einschließlich Groß-/Kleinschreibung und Leerzeichen.
5. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Inhalte angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.

**F: Der Tooltip-Inhalt sieht seltsam aus oder wird nicht korrekt angezeigt (z. B. defekte Bilder, seltsame Formatierung).**
A:

1. **HTML-Fehler:** Wenn Sie den Rich-Text-Editor verwendet haben, stellen Sie sicher, dass Sie keine defekten HTML-Tags eingefügt haben. Wechseln Sie zur Quellcode-Ansicht im Editor, um nach nicht geschlossenen Tags oder ungültigen Attributen zu suchen.
2. **Bildpfade:** Wenn Bilder nicht angezeigt werden, überprüfen Sie, ob die Bild-URL in Ihrem Tooltip-Inhalt korrekt und zugänglich ist. Verwenden Sie absolute URLs (beginnend mit `http://` oder `https://`) für Bilder, die auf Ihrem Server gehostet werden.
3. **CSS-Konflikte:** Das CSS Ihres Themes könnte die Stile des Moduls überschreiben. Dies ist eher ein Entwicklerproblem, aber Sie können versuchen, das „Tooltip-Theme“ in der Modulkonfiguration zu ändern, um zu sehen, ob ein anderes Theme das Problem löst.

**F: Tooltips erscheinen auf Seiten, auf denen ich sie nicht haben möchte.**
A:

1. **„Zulässige Seitentypen“ überprüfen:** Gehen Sie zu **Module > Modul-Manager > Tooltip Pro konfigurieren**. Überprüfen Sie sorgfältig die „Zulässigen Seitentypen für Tooltips“ und deaktivieren Sie alle Seitentypen, auf denen Sie keine Tooltips anzeigen möchten.
2. **Schlüsselwort-Spezifität:** Wenn ein Schlüsselwort sehr generisch ist (z. B. „Produkt“), kann es auf vielen Seiten erscheinen. Erwägen Sie, Ihre Schlüsselwörter spezifischer zu gestalten oder sie auf bestimmte Seitentypen zu beschränken.

**F: Wie übersetze ich meine Tooltips in andere Sprachen?**
A:

1. **Tooltip bearbeiten:** Gehen Sie zu **Tooltip Pro > Tooltips** und klicken Sie auf „Bearbeiten“ bei dem Tooltip, den Sie übersetzen möchten.
2. **Sprachauswahl:** Innerhalb des Rich-Text-Editors für den „Tooltip-Inhalt“ sollten Sie eine Sprachauswahl sehen (normalerweise ein Flaggensymbol oder ein Dropdown-Menü). Wählen Sie die gewünschte Sprache aus und geben Sie den übersetzten Inhalt für diese Sprache ein. Wiederholen Sie dies für alle Sprachen.
3. **Schlüsselwort-Übersetzung:** Das „Schlüsselwort“ selbst wird normalerweise nicht vom Modul übersetzt, da es nach dem exakten Text auf der Seite sucht. Wenn sich Ihre Schlüsselwörter pro Sprache ändern (z. B. „Größenführer“ vs. „Guide des Tailles“), müssten Sie separate Tooltip-Einträge für das Schlüsselwort jeder Sprache erstellen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul Tooltip Pro folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es besteht hauptsächlich aus:

- Einer Hauptmodulklasse (`index.php`) für Installation, Deinstallation und Konfiguration.
- Dedizierten Admin-Controllern (`AdminTooltipsListController`) zur Verwaltung von Tooltip-Entitäten im Back Office.
- Front-Controllern (`ajax.php`) zur Handhabung dynamischer Inhaltsanfragen bei Bedarf (obwohl die Kern-Tooltip-Rendering clientseitig erfolgt).
- Clientseitigem JavaScript (unter Verwendung der Tooltipster-Bibliothek) zur Erkennung von Schlüsselwörtern und dynamischen Anzeige von Tooltips.
- Einer benutzerdefinierten Datenbanktabelle (`ps_tooltips`) zur Speicherung von Tooltip-Definitionen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/ajax.php`
  - **Klassenname & Elternklasse:** `TooltipsAjaxModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist für die Verarbeitung von AJAX-Anfragen aus dem Front-Office konzipiert. Während der Kern-Tooltip-Inhalt oft direkt in den HTML gerendert wird, könnte dieser Controller für dynamisches Laden von Inhalten, das Abrufen von Tooltip-Daten bei Bedarf oder andere interaktive Funktionen verwendet werden. Er reagiert auf spezifische Routen, die vom Modul definiert werden.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `TooltipsIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder Platzhalter dienen. In vielen einfachen Modulen wird `index.php` im Front-Controller-Verzeichnis nicht direkt zum Rendern einer Seite verwendet, könnte aber für die architektonische Vollständigkeit oder zur Handhabung der Standard-Modul-Routing vorhanden sein, wenn kein anderer spezifischer Front-Controller übereinstimmt. Für Tooltip Pro erfolgt die primäre Front-Office-Interaktion über JavaScript und Hooks.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminTooltipsList.php`
  - **Klassenname & Elternklasse:** `AdminTooltipsListController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Dieser Controller verwaltet die „Tooltips“-Liste im PrestaShop Back Office. Er ist verantwortlich für die Anzeige des Rasters vorhandener Tooltips, die Handhabung von Hinzufüge-/Bearbeitungs-/Löschvorgängen für `Tooltip`-Objekte und das Rendern der zugehörigen Formulare. Er interagiert direkt mit dem `Tooltip` `ObjectModel`.
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse:** `TooltipsAdminIndexModuleFrontController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Ähnlich wie das Front-Office `index.php` könnte dies ein Platzhalter oder ein Standardeinstiegspunkt für den Admin-Bereich des Moduls sein. Die primäre Verwaltung erfolgt durch `AdminTooltipsList.php`.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist kein spezifisches `classes/`-Verzeichnis auf, was impliziert, dass das Haupt-`Tooltip` `ObjectModel` und die zugehörige Logik direkt in der Hauptdatei `tooltips/index.php` definiert oder dynamisch generiert werden könnten.
Unter Annahme einer Standard-PrestaShop-Modulstruktur gäbe es typischerweise eine `Tooltip.php`-Klasse.

- **`Tooltip` (hypothetisch, wahrscheinlich in `index.php` oder einer dedizierten `classes/Tooltip.php`, falls vorhanden):**
  - **Datenbanktabelle:** `ps_tooltips` (oder `_PREFIX_tooltips`)
  - **Erweitert `ObjectModel`:** Ja.
  - **`$definition`-Felder:**
    - `id_tooltip`: Primärschlüssel (INT)
    - `keyword`: Der hervorzuhebende Textstring (VARCHAR)
    - `content`: Der HTML-Inhalt des Tooltips (HTML, TEXT)
    - `active`: Boolean für aktiven/inaktiven Status (TINYINT)
    - `date_add`: Erstellungsdatum (DATETIME)
    - `date_upd`: Letztes Aktualisierungsdatum (DATETIME)
    - `id_shop`: Shop-ID für Multi-Store (INT)
    - `id_lang`: Sprach-ID für mehrsprachigen Inhalt (INT)
  - **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden (`add()`, `update()`, `delete()`, `getFields()`). Benutzerdefinierte Methoden könnten `getTooltipsByShopAndLang()` oder `getKeywordsForPageType()` umfassen.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul nutzt die `Tooltipster`-Bibliothek für seine Tooltip-Funktionalität.

- `tooltips/lib/tooltipster/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Ein Plugin für die Tooltipster-Bibliothek, speziell für die Handhabung von SVG-Elementen. Wenn Ihre Tooltips mit SVG-Grafiken interagieren oder darauf platziert werden müssen, bietet dieses Plugin die notwendige Funktionalität.
- `tooltips/lib/tooltipster/js/tooltipster.bundle.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Die vollständige, gebündelte Version der Tooltipster-Bibliothek, einschließlich ihres Kerns und potenziell anderer gängiger Plugins. Dies bietet die Hauptfunktionalität zum Erstellen und Verwalten von Tooltips.
- `tooltips/lib/tooltipster/js/tooltipster.core.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Die Kernfunktionalität der Tooltipster-Bibliothek. Diese Datei enthält die wesentliche Logik für die Tooltip-Erstellung, Positionierung, Ereignisse und Styling.
- `tooltips/views/js/tooltips.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Dies ist das benutzerdefinierte JavaScript des Moduls.
    - **Ereignis-Listener:** Bindet wahrscheinlich an das `ready`-Ereignis des Dokuments (`$(document).ready()` oder ähnlich), um Tooltips zu initialisieren.
    - **DOM-Manipulation:** Scannt den Seiteninhalt nach definierten Schlüsselwörtern, umschließt sie in einem spezifischen HTML-Element (z. B. `<span class="tooltip-keyword">`) und initialisiert dann die Tooltipster-Bibliothek auf diesen Elementen.
    - **Tooltipster-Initialisierung:** Konfiguriert Tooltipster mit Einstellungen aus dem Back Office des Moduls (Platzierung, Animation, Theme, Verzögerungen, maximale Breite).
    - **AJAX-Aufrufe:** Führt potenziell AJAX-Aufrufe an `controllers/front/ajax.php` durch, um Tooltip-Inhalte dynamisch abzurufen, obwohl die Modulbeschreibung darauf hindeutet, dass Inhalte oft vorgerendert werden.
    - **Mobile Interaktion:** Behandelt Tipp-Ereignisse für mobile Geräte, um Tooltips auszulösen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `tooltips/lib/tooltipster/css/tooltipster.bundle.css`
  - **Geltungsbereich:** Front-Office Kunden-Styling.
  - **Beschreibung:** Das Haupt-Stylesheet für die Tooltipster-Bibliothek, das Standardstile für das Tooltip-Feld, Pfeile und verschiedene Themes enthält.
- `tooltips/lib/tooltipster/css/tooltipster.core.css`
  - **Geltungsbereich:** Front-Office Kunden-Styling.
  - **Beschreibung:** Kern-CSS für die Tooltipster-Bibliothek, das wesentliche visuelle Eigenschaften für Tooltips definiert.
- `tooltips/views/css/tooltips-admin.css`
  - **Geltungsbereich:** Back-Office Admin-Formular-Styling.
  - **Beschreibung:** Enthält spezifische Stile für die Konfigurationsseiten des Moduls und den `AdminTooltipsList`-Controller im PrestaShop Back Office, um eine konsistente und benutzerfreundliche Admin-Oberfläche zu gewährleisten.
- `tooltips/views/css/tooltips.css`
  - **Geltungsbereich:** Front-Office Kunden-Styling.
  - **Beschreibung:** Dies ist das benutzerdefinierte Front-Office-CSS des Moduls.
    - **Haupt-UI-Komponenten:** Stile für die hervorgehobenen Schlüsselwörter (z. B. `span.tooltip-keyword`).
    - **Wichtige CSS-Klassenselektoren:** Entwickler können Stile für `.tooltip-keyword` oder spezifische Tooltipster-Theme-Klassen (z. B. `.tooltipster-base`, `.tooltipster-light`) in der `custom.css` ihres Themes oder durch Erstellen einer Überschreibungsdatei überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `tooltips/views/tooltips.tpl`
  - **Geltungsbereich:** Front-Office Hook-Template.
  - **Beschreibung:** Dieses Template wird wahrscheinlich in `displayHeader` oder `displayFooter` eingehängt, um notwendige JavaScript-Variablen und möglicherweise das Initialisierungsskript für die Datei `tooltips.js` auszugeben. Es könnte Konfigurationseinstellungen aus dem Back Office (z. B. `tooltip_placement`, `tooltip_animation`, `tooltip_theme`) als Smarty-Variablen an das JavaScript übergeben. Es rendert den Tooltip-Inhalt selbst nicht direkt, da dies dynamisch von JavaScript gehandhabt wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_tooltips`: Speichert die Definitionen für jeden Tooltip.
    - `id_tooltip` (PK, INT)
    - `keyword` (VARCHAR)
    - `content` (TEXT, HTML erlaubt)
    - `active` (TINYINT(1))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
    - `id_shop` (INT)
    - `id_lang` (INT)
  - `ps_configuration`: Speichert modulweite Einstellungen (z. B. `TOOLTIPS_PRO_ENABLED`, `TOOLTIPS_PRO_HIGHLIGHT`, `TOOLTIPS_PRO_PLACEMENT` usw.).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Fügt CSS- und JavaScript-Dateien (Tooltipster-Bibliothek, `tooltips.js` und modulspezifische Stile) in die Seite ein. Gibt auch Konfigurationsvariablen für JS aus. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back Office-Seite. | Fügt admin-spezifisches CSS (`tooltips-admin.css`) und potenziell JS für die Konfigurations- und Listenseiten des Moduls ein. |
| `actionFrontControllerSetMedia` | Nachdem Medien für einen Front-Controller festgelegt wurden. | Ermöglicht dem Modul, sein CSS/JS bedingt basierend auf dem aktuellen Seitenkontext hinzuzufügen (z. B. nur auf Produktseiten, wenn konfiguriert). |
| `moduleRoutes` | Während der Router-Initialisierung. | Registriert benutzerdefinierte Front-Office-Routen für `ajax.php`, wenn dynamisches Laden von Inhalten verwendet wird. |
| `actionObjectTooltipAddAfter` | Nachdem ein `Tooltip`-Objekt hinzugefügt wurde. | Kann zum Leeren des Caches oder zur Protokollierung verwendet werden. |
| `actionObjectTooltipUpdateAfter` | Nachdem ein `Tooltip`-Objekt aktualisiert wurde. | Kann zum Leeren des Caches oder zur Protokollierung verwendet werden. |
| `actionObjectTooltipDeleteAfter` | Nachdem ein `Tooltip`-Objekt gelöscht wurde. | Kann zum Leeren des Caches oder zur Protokollierung verwendet werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Tooltip Pro Modul besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul perfekt funktioniert und Ihnen hilft, Ihren PrestaShop-Shop zu verbessern.
