---
title: "Farb-/Textur-Attribut-Zoom – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Farb-/Textur-Attribut-Zoom' von MyPresta.eu."
sidebar:
  label: "Farb-/Textur-Attribut-Zoom – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Color / texture attribute zoom auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/color-texture-attribute-zoom.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/color-texture-attribute-zoom/)
>
> ---


# Farb-/Textur-Attribut-Zoom

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Farb-/Textur-Attribut-Zoom“, der nach der Installation durch Klicken auf die Schaltfläche „Konfigurieren“ zugänglich ist.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Funktionalität des Moduls in Ihrem gesamten Shop ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Die Farb-/Textur-Zoomfunktion ist auf Ihren Produktseiten und in den Schnellansicht-Pop-ups aktiv, gemäß den anderen von Ihnen gewählten Einstellungen.
  - *Wenn deaktiviert:* Die Zoomfunktion wird vollständig deaktiviert, und es werden keine vergrößerten Vorschauen angezeigt.
- **Empfohlener Wert:** **Aktiviert** (um die Funktionen des Moduls zu nutzen).
- **Händlerszenario / Beispiel:** Wenn Sie die Zoomfunktion vorübergehend für Wartungsarbeiten oder Tests deaktivieren möchten, können Sie diese ausschalten, ohne das Modul zu deinstallieren.

#### **Farb-/Texturname (Wert) anzeigen**

- **Was diese Einstellung bewirkt:** Legt fest, ob der Textname der Farbe oder Textur (z. B. „Rot“, „Leder“) neben dem gezoomten Vorschaufenster angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Der Name des Attributs wird neben dem gezoomten Bild angezeigt und bietet dem Kunden zusätzlichen Kontext.
  - *Wenn deaktiviert:* Es wird nur das gezoomte Bild angezeigt, ohne die Textbeschriftung.
- **Empfohlener Wert:** **Aktiviert**. Dies liefert dem Kunden klarere Informationen, insbesondere wenn Farben ähnlich oder Texturen subtil sind.
- **Händlerszenario / Beispiel:** Wenn Sie viele Blautöne haben (z. B. „Himmelblau“, „Marineblau“), hilft die Anzeige des Namens den Kunden, diese klar zu unterscheiden.

#### **Attributwechsel beim Tippen deaktivieren**

- **Was diese Einstellung bewirkt:** Steuert das Verhalten des Moduls auf Touch-Geräten (wie Smartphones und Tablets), wenn ein Kunde auf ein Farb-/Texturfeld tippt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Tippen auf ein Farb-/Texturfeld zeigt nur die Zoom-Vorschau an. Das Hauptproduktbild auf der Seite ändert sich NICHT, um das angetippte Attribut widerzuspiegeln.
  - *Wenn deaktiviert:* Das Tippen auf ein Farb-/Texturfeld zeigt die Zoom-Vorschau an UND aktualisiert auch das Hauptproduktbild, um das Produkt in der ausgewählten Farbe/Textur anzuzeigen.
- **Empfohlener Wert:** **Deaktiviert**. Die meisten Kunden erwarten, dass sich das Hauptproduktbild aktualisiert, wenn sie eine Farbe/Textur auswählen, auch auf Mobilgeräten. Aktivieren Sie dies nur, wenn Sie einen bestimmten Grund haben, das Hauptbild beim Tippen nicht zu ändern.
- **Händlerszenario / Beispiel:** Wenn Ihre Produktbilder generisch sind und sich nicht basierend auf Farbattributen ändern, oder wenn Sie versehentliche Änderungen des Hauptbildes auf Mobilgeräten verhindern möchten, könnten Sie dies aktivieren. Andernfalls lassen Sie es für das Standardverhalten deaktiviert.

#### **Breite des Farbvorschaubereichs**

- **Was diese Einstellung bewirkt:** Legt die Breite (in Pixeln) des Pop-up-Fensters fest, das die gezoomte Farbvorschau anzeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Erhöhung des Wertes:* Macht das Vorschaufenster breiter und zeigt mehr Details.
  - *Verringerung des Wertes:* Macht das Vorschaufenster schmaler.
- **Empfohlener Wert:** Ein Wert zwischen **200px und 300px** ist normalerweise eine gute Balance. Beginnen Sie mit `280` und passen Sie ihn basierend auf Ihren Produktbildern und Ihrem Theme-Design an.
- **Händlerszenario / Beispiel:** Wenn Ihre Farbfelder sehr klein sind und Sie eine deutliche Vergrößerung anzeigen möchten, erhöhen Sie diesen Wert. Wenn Ihr Produktseitenlayout sehr schmal ist, müssen Sie ihn möglicherweise reduzieren.

#### **Höhe des Farbvorschaubereichs**

- **Was diese Einstellung bewirkt:** Legt die Höhe (in Pixeln) des Pop-up-Fensters fest, das die gezoomte Farbvorschau anzeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Erhöhung des Wertes:* Macht das Vorschaufenster höher und zeigt mehr Details.
  - *Verringerung des Wertes:* Macht das Vorschaufenster kürzer.
- **Empfohlener Wert:** Ein Wert zwischen **200px und 300px** ist normalerweise eine gute Balance. Beginnen Sie mit `280` und passen Sie ihn basierend auf Ihren Produktbildern und Ihrem Theme-Design an.
- **Händlerszenario / Beispiel:** Ähnlich wie bei der Breite passen Sie dies an, um sicherzustellen, dass die gezoomte Farbe deutlich sichtbar ist, ohne für Ihre Produktseite übermäßig groß oder klein zu sein.

#### **Zoom in Kombinationstabelle aktivieren**

- **Was diese Einstellung bewirkt:** Legt fest, ob die Zoomfunktion auch für Farb-/Texturattribute gelten soll, die in einer Produktkombinationstabelle angezeigt werden (falls Ihr Theme eine verwendet).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Kunden können auf Farb-/Texturfelder innerhalb einer Kombinationstabelle fahren/tippen, um die gezoomte Vorschau zu sehen.
  - *Wenn deaktiviert:* Die Zoomfunktion funktioniert nur für Farb-/Texturattribute außerhalb von Kombinationstabellen.
- **Empfohlener Wert:** **Aktiviert**. Dies bietet ein konsistentes und hilfreiches Erlebnis in allen Bereichen, in denen Farb-/Texturattribute angezeigt werden.
- **Händlerszenario / Beispiel:** Wenn Sie T-Shirts mit einer Tabelle verkaufen, die Größen und verfügbare Farben anzeigt, können Kunden durch Aktivierung dieser Option direkt aus dieser Tabelle in die Farben zoomen.

#### **Breite des Textur-Vorschaubereichs**

- **Was diese Einstellung bewirkt:** Legt die Breite (in Pixeln) des Pop-up-Fensters fest, das die gezoomte Texturvorschau anzeigt. Dies ist getrennt von der Farbvorschau-Breite, sodass Sie für verschiedene Arten von Attributbildern optimieren können.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Erhöhung des Wertes:* Macht die Texturvorschau breiter.
  - *Verringerung des Wertes:* Macht die Texturvorschau schmaler.
- **Empfohlener Wert:** Ähnlich wie bei der Farbe ist ein Wert zwischen **200px und 300px** oft geeignet. Beginnen Sie mit `280`.
- **Händlerszenario / Beispiel:** Wenn Ihre Texturbilder sehr detailliert sind und eine größere Ansicht erfordern, um sie zu würdigen, könnten Sie hier eine höhere Breite einstellen als für einfache Farbfelder.

#### **Einige Farb-Attributgruppen vom ZOOM ausschließen**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bestimmte Attributgruppen (z. B. „Größe“, „Material“) anzugeben, für die die Zoomfunktion NICHT angewendet werden soll, selbst wenn sie Farb- oder Texturbilder verwenden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn Attributgruppen-IDs eingegeben werden:* Die Zoomfunktion wird für alle Attribute deaktiviert, die zu den angegebenen Gruppen gehören.
  - *Wenn leer gelassen:* Die Zoomfunktion wird auf alle Farb-/Textur-Attributgruppen angewendet.
- **Empfohlener Wert:** Lassen Sie das Feld **leer**, es sei denn, Sie haben einen bestimmten Grund, Gruppen auszuschließen. Wenn Sie ausschließen müssen, geben Sie die numerischen IDs der Attributgruppen durch Kommas getrennt ein (z. B. `1, 5, 12`). Sie finden die Attributgruppen-IDs in Ihrem PrestaShop Back Office unter **Katalog > Attribute & Funktionen > Attributgruppen**.
- **Händlerszenario / Beispiel:** Sie könnten eine Attributgruppe „Verfügbarkeit“ haben, die Farbfelder verwendet (z. B. grün für auf Lager, rot für nicht auf Lager), aber Sie möchten nicht, dass diese einen Zoom auslösen. In diesem Fall würden Sie die ID der Attributgruppe „Verfügbarkeit“ finden und hier eingeben.

#### **Animationstyp**

- **Was diese Einstellung bewirkt:** Wählt den visuellen Effekt aus, der beim Erscheinen des Zoom-Vorschaufensters verwendet wird.
- **Auswirkung der Änderung dieser Einstellung:** Ändert die Art und Weise, wie das Vorschaufenster animiert wird (z. B. Einblenden, Schieben).
- **Empfohlener Wert:** **Fade**. Dies ist im Allgemeinen die subtilste und professionellste Animation. Experimentieren Sie mit anderen, wenn Sie einen anderen Effekt bevorzugen.
- **Händlerszenario / Beispiel:** Sie können eine Animation wählen, die am besten zur gesamten Designästhetik Ihres Shops passt.

#### **Animationstyp aktualisieren**

- **Was diese Einstellung bewirkt:** Wählt den visuellen Effekt aus, der verwendet wird, wenn sich der Inhalt des Zoom-Vorschaufensters ändert (z. B. beim Wechseln zwischen verschiedenen Farben/Texturen, während die Vorschau bereits geöffnet ist).
- **Auswirkung der Änderung dieser Einstellung:** Ändert die Animation für Inhaltsaktualisierungen innerhalb der Vorschau.
- **Empfohlener Wert:** **Fade**. Ähnlich wie bei der anfänglichen Animation ist ein Fade normalerweise glatt und nicht ablenkend.
- **Händlerszenario / Beispiel:** Wenn ein Kunde schnell über mehrere Farbfelder fährt, bestimmt diese Animation, wie reibungslos der Vorschauinhalt übergeht.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | Aktiviert | Hauptschalter für die Modulfunktionalität. |
| Modulkonfiguration | Farb-/Texturname (Wert) anzeigen | Aktiviert | Zeigt Attributnamen mit Zoom-Vorschau an. |
| Modulkonfiguration | Attributwechsel beim Tippen deaktivieren | Deaktiviert | Verhindert Hauptbildwechsel bei mobilem Tippen (falls aktiviert). |
| Modulkonfiguration | Breite des Farbvorschaubereichs | 280 | Breite des Farb-Zoom-Pop-ups in Pixeln. |
| Modulkonfiguration | Höhe des Farbvorschaubereichs | 280 | Höhe des Farb-Zoom-Pop-ups in Pixeln. |
| Modulkonfiguration | Zoom in Kombinationstabelle aktivieren | Aktiviert | Erweitert den Zoom auf Attribute innerhalb von Kombinationstabellen. |
| Modulkonfiguration | Breite des Textur-Vorschaubereichs | 280 | Breite des Textur-Zoom-Pop-ups in Pixeln. |
| Modulkonfiguration | Einige Farb-Attributgruppen vom ZOOM ausschließen | Leer | Kommagetrennte IDs von Attributgruppen, die für den Zoom ignoriert werden sollen. |
| Modulkonfiguration | Animationstyp | Fade | Animation für das Erscheinen der Zoom-Vorschau. |
| Modulkonfiguration | Animationstyp aktualisieren | Fade | Animation für Inhaltsänderungen innerhalb der Zoom-Vorschau. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Zoom erscheint nicht auf meiner Produktseite. Was sollte ich überprüfen?**
A:

1. **Modul aktiviert:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Farb-/Textur-Attribut-Zoom“ aktiviert ist.
2. **Attribut-Setup:** Überprüfen Sie, ob Ihre Produktattribute in **Katalog > Attribute & Funktionen > Attribute** korrekt als „Farbe“ oder „Textur“ eingerichtet sind. Stellen Sie sicher, dass Sie tatsächlich Bilder für diese Attribute hochgeladen haben, nicht nur Farbcodes.
3. **Cache:** Leeren Sie Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“. Leeren Sie auch den Cache Ihres Browsers.
4. **Theme-Kompatibilität:** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, können sehr stark angepasste Themes manchmal stören. Wenn die oben genannten Schritte nicht funktionieren, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob der Zoom erscheint. Wenn ja, benötigt Ihr Theme möglicherweise eine kleine Anpassung.

**F: Das Zoom-Vorschaufenster ist zu klein/groß.**
A: Passen Sie die Einstellungen „Breite des Farbvorschaubereichs“, „Höhe des Farbvorschaubereichs“ und „Breite des Textur-Vorschaubereichs“ auf der Konfigurationsseite des Moduls an. Erhöhen Sie die Werte, um das Fenster größer zu machen, verringern Sie sie, um es kleiner zu machen. Denken Sie daran, Änderungen zu speichern und den Cache zu leeren.

**F: Der Farb-/Texturname wird nicht mit dem Zoom angezeigt.**
A: Überprüfen Sie die Einstellung „Farb-/Texturname (Wert) anzeigen“ in der Modulkonfiguration. Stellen Sie sicher, dass sie auf „Aktiviert“ gesetzt ist.

**F: Auf Mobilgeräten ändert sich das Hauptproduktbild nicht, wenn ich auf eine Farbe tippe, aber ich möchte, dass es sich ändert.**
A: Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass „Attributwechsel beim Tippen deaktivieren“ auf „Deaktiviert“ gesetzt ist. Dadurch wird das Hauptproduktbild aktualisiert, wenn eine Farbe/Textur angetippt wird.

**F: Ich möchte eine bestimmte Attributgruppe von der Zoomfunktion ausschließen.**
A: Navigieren Sie in Ihrem PrestaShop Back Office zu **Katalog > Attribute & Funktionen > Attributgruppen**. Suchen Sie die Attributgruppe, die Sie ausschließen möchten, und notieren Sie deren ID (normalerweise in der URL sichtbar, wenn Sie sie bearbeiten, oder in der Tabelle selbst). Gehen Sie dann zur Modulkonfiguration, suchen Sie „Einige Farb-Attributgruppen vom ZOOM ausschließen“ und geben Sie die ID(s) durch Kommas getrennt ein (z. B. `1,5,12`).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Farb-/Textur-Attribut-Zoom“ (`colorzoom`) ist ein Front-Office-Funktionsmodul, das die Visualisierung von Produktattributen verbessern soll. Es nutzt hauptsächlich das Hook-System von PrestaShop, um seine JavaScript- und CSS-Assets in den Front-Office-Header einzufügen und seine spezifische Zoom-Vorlage auf Produktseiten zu rendern. Es verwendet die `tooltipster`-Bibliothek für die eigentliche Zoom-/Tooltip-Funktionalität und hängt diese dynamisch an Farb- und Textur-Attributelemente an. Die Konfiguration wird über die Standardmethode `getContent()` in der Hauptmoduldatei verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

Das Modul enthält zwei Front-Office-Controller, obwohl deren primäre Funktion in diesem Modul oft minimal ist oder für spezifische AJAX-Anforderungen dient, wobei ein Großteil der Logik clientseitig über JavaScript gehandhabt wird.

- **Front-Office-Controller**:

  - `controllers/front/index.php`
    - Klassenname: `ColorzoomIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - Verantwortung: Dieser Controller dient wahrscheinlich als Fallback oder als generischer Einstiegspunkt. Da die primäre Funktion des Moduls die UI-Verbesserung über JS/CSS ist, hat dieser Controller möglicherweise keine umfangreiche Logik oder wird bei Bedarf vom Frontend für einfache Datenabrufe verwendet.
  - `controllers/front/loader.php`
    - Klassenname: `ColorzoomLoaderModuleFrontController` (erweitert `ModuleFrontController`)
    - Verantwortung: Dieser Controller könnte zum dynamischen Laden spezifischer Ressourcen oder Daten verwendet werden, möglicherweise für AJAX-Anfragen im Zusammenhang mit der Zoom-Funktionalität, obwohl die Kern-Zoom-Logik clientseitig ist.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Geschäftslogikklassen im Verzeichnis `classes/`. Seine Kernfunktionalität ist in der Hauptdatei `colorzoom.php` und über seine JavaScript-Assets implementiert.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul stützt sich stark auf JavaScript für seine interaktive Zoom-Funktionalität, insbesondere auf die `tooltipster`-Bibliothek.

- `colorzoom/lib/tooltipster/dist/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - Geltungsbereich: Front-Office.
  - Details: Ein Plugin für die `tooltipster`-Bibliothek, speziell für die Handhabung von SVG-Elementen innerhalb von Tooltips. Dies könnte verwendet werden, wenn Attributbilder SVG-basiert sind oder wenn das Modul mit SVG-Elementen auf der Seite interagieren muss.
- `colorzoom/lib/tooltipster/dist/js/tooltipster.bundle.js`
  - Geltungsbereich: Front-Office.
  - Details: Die vollständige gebündelte Version der `tooltipster`-Bibliothek, die die Kernfunktionalität zum Erstellen flexibler und anpassbarer Tooltips bereitstellt. Dies ist die primäre Bibliothek, die für die Zoom-Pop-ups verantwortlich ist.
- `colorzoom/lib/tooltipster/dist/js/tooltipster.core.js`
  - Geltungsbereich: Front-Office.
  - Details: Die Kern-JavaScript-Datei für die `tooltipster`-Bibliothek. Es ist möglich, dass `tooltipster.bundle.js` diese bereits enthält, aber sie ist separat aufgeführt, was auf eine modulare Einbindung hinweist.
- `colorzoom/views/js/colorzoom-combinationstable.js`
  - Geltungsbereich: Front-Office.
  - Details: Dieses Skript zielt speziell auf Produktkombinationstabellen ab. Es enthält wahrscheinlich Logik, um Farb-/Texturattribute innerhalb dieser Tabellen zu identifizieren und die `tooltipster`-Zoomfunktionalität auf ihnen zu initialisieren, wobei die Konfigurationseinstellung `cz_ctab` berücksichtigt wird. Es bindet Ereignis-Listener an Elemente innerhalb dieser Tabellen.
- `colorzoom/views/js/colorzoom.js`
  - Geltungsbereich: Front-Office.
  - Details: Dies ist das wichtigste benutzerdefinierte JavaScript für das Modul. Es ist verantwortlich für:
    - Identifizierung von Farb-/Textur-Attributelementen auf der Produktseite (außerhalb von Kombinationstabellen).
    - Initialisierung von `tooltipster` auf diesen Elementen mit modulspezifischen Konfigurationen (Breite, Höhe, Animationstyp, Namensanzeige).
    - Handhabung der Logik „Attributwechsel beim Tippen deaktivieren“ für mobile Geräte.
    - Potenzielles Abhören von `prestashop.on`-Ereignissen wie `updateProduct`, um Tooltips neu zu initialisieren, wenn sich Produktinhalte über AJAX ändern.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält CSS zur Gestaltung der Zoom-Vorschauen und der `tooltipster`-Bibliothek.

- `colorzoom/lib/tooltipster/dist/css/tooltipster.bundle.css`
  - Geltungsbereich: Front-Office-Kundenstyling.
  - Details: Das gebündelte CSS für die `tooltipster`-Bibliothek, das Standard-Styling für die Tooltips (die Zoom-Vorschaufenster) bereitstellt.
- `colorzoom/lib/tooltipster/dist/css/tooltipster.core.css`
  - Geltungsbereich: Front-Office-Kundenstyling.
  - Details: Das Kern-CSS für `tooltipster`, das grundlegende Stile definiert.
- `colorzoom/views/css/colorszoom.css`
  - Geltungsbereich: Front-Office-Kundenstyling.
  - Details: Benutzerdefiniertes CSS speziell für das Modul „Farb-/Textur-Attribut-Zoom“. Diese Datei enthält wahrscheinlich Überschreibungen oder zusätzliche Stile, um die `tooltipster`-Tooltips nahtlos in die PrestaShop-Produktseite zu integrieren und die korrekte Positionierung, Schriftgrößen für Attributnamen und Responsivität sicherzustellen. Entwickler können diese Datei auf wichtige Selektoren überprüfen, die in der benutzerdefinierten CSS ihres Themes überschrieben werden sollen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um sein JavaScript und CSS einzufügen und den Inhalt der Zoom-Vorschau zu rendern.

- **Hook-Templates (`views/templates/hook/`)**:
  - `colorzoom/views/header.tpl`
    - Hook: `displayHeader`
    - Zweck: Dieses Template ist dafür verantwortlich, die CSS- und JavaScript-Dateien des Moduls in den `<head>`-Bereich der Front-Office-Seiten einzubinden. Es übergibt auch Konfigurationsvariablen aus dem Back Office (wie `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_ctab`, `cz_exclusions`) an das Frontend-JavaScript, wodurch sie für die dynamische Initialisierung zugänglich werden.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `colorzoom/views/quickview.tpl`
    - Zweck: Dieses Template ist wahrscheinlich dafür konzipiert, innerhalb eines Produkt-Schnellansicht-Pop-ups gerendert zu werden. Es enthält das notwendige Markup oder die Logik, um sicherzustellen, dass die Zoom-Funktionalität für Attribute, die in Schnellansicht-Modals angezeigt werden, korrekt initialisiert wird.
  - `colorzoom/views/zoom.tpl`
    - Zweck: Dies ist das Kerntemplate für den Inhalt, der in der Zoom-Vorschau (Tooltip) angezeigt wird. Es empfängt dynamisch die URL des Attributbildes und den Attributnamen und rendert diese innerhalb der Tooltip-Struktur. Es ist die visuelle Komponente, die die `tooltipster`-Bibliothek anzeigen wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln gespeichert, die mit `cz_` beginnen (z. B. `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_exclusions`, `cz_ctab`) und `mypresta_updates`, `update_`, `updatev_` für die Update-Verwaltung.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt die CSS- und JavaScript-Dateien des Moduls ein und übergibt Konfigurationsvariablen an das Frontend. |
  | `displayProductAdditionalInfo` | Innerhalb des Produktinformationsblocks auf der Produktseite. | Dieser Hook wird verwendet, um die notwendige JavaScript-Initialisierung oder spezifisches Markup für die Zoom-Funktion auf der Produktseite zu rendern, um sicherzustellen, dass sie für Farb-/Texturattribute aktiv ist. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, zeitnahen Support zu leisten und sicherzustellen, dass Ihr Modul optimal funktioniert.
