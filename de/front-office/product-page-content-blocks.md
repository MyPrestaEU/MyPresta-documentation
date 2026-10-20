---
title: "Produktseiten-Inhaltsblöcke - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produktseiten-Inhaltsblöcke' von MyPresta.eu."
sidebar:
  label: "Produktseiten-Inhaltsblöcke - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product page content blocks auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-page-content-blocks.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-page-content-blocks/)
>
> ---


# Produktseiten-Inhaltsblöcke

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich, und dieses Modul stellt darüber hinaus keine zusätzlichen spezifischen Anforderungen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Produktseiten-Inhaltsblöcke“ wird hauptsächlich über einen dedizierten Tab auf der Bearbeitungsseite jedes Produkts betrieben, anstatt über einen einzigen globalen Konfigurationsbildschirm. Es gibt jedoch eine Hauptkonfigurationsseite des Moduls für die Ersteinrichtung und einen AJAX-Controller zur Verwaltung der Blöcke.

### 2.1 Modul-Konfigurationsseite (Backoffice > Module > Konfigurieren)

Wenn Sie das Modul zum ersten Mal installieren und auf „Konfigurieren“ klicken, gelangen Sie zur Hauptkonfigurationsseite. Diese Seite behandelt typischerweise die Ersteinrichtung oder globale Einstellungen, falls vorhanden.

- **Was diese Einstellung bewirkt:** Diese Seite dient als Einstiegspunkt für das Modul. Während die Kernfunktionalität des Erstellens von Blöcken auf den Produktseiten erfolgt, kann dieser Bildschirm allgemeine Einstellungen oder eine schnelle Übersicht bieten.
- **Auswirkung der Änderung dieser Einstellung:** Alle hier vorgenommenen Einstellungen würden global für das Verhalten des Moduls auf allen Produktseiten gelten, z.B. das vollständige Aktivieren/Deaktivieren des Moduls oder das Festlegen von Standardverhalten.
- **Empfohlener Wert:** Befolgen Sie die Anweisungen auf dem Bildschirm. Wenn keine spezifischen Einstellungen vorhanden sind, bestätigt diese Seite einfach, dass das Modul installiert und einsatzbereit ist.
- **Händlerszenario / Beispiel:** Hier finden Sie möglicherweise einen Schalter zum „Modul aktivieren/deaktivieren“, der alle benutzerdefinierten Inhaltsblöcke in Ihrem Shop deaktiviert, ohne das Modul zu deinstallieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Die primäre Interaktion mit diesem Modul findet auf der Produktbearbeitungsseite statt.

#### 2.2.1 Produktbearbeitungsseite (Katalog > Produkte > Produkt bearbeiten)

Nach der Installation des Moduls finden Sie beim Bearbeiten eines Produkts in Ihrem PrestaShop-Backoffice einen neuen Tab mit der Bezeichnung „Produktseiten-Inhaltsblöcke“ (oder ähnlich).

- **Bildschirmname & Menüpfad:** **Katalog > Produkte > [Produkt auswählen/bearbeiten] > Tab „Produktseiten-Inhaltsblöcke“**
- **Verfügbare Aktionen & Einstellungen:**

  - **Neuen Block hinzufügen:** Sie sehen typischerweise eine Schaltfläche wie „Neuen Block hinzufügen“ oder eine ähnliche Oberfläche, um einen neuen Inhaltsblock für das aktuelle Produkt zu erstellen.
    - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, ein neues Inhaltselement zu definieren.
    - **Auswirkung der Änderung dieser Einstellung:** Ein neuer Inhaltsblock wird für dieses spezifische Produkt erstellt und gespeichert.
    - **Händlerszenario / Beispiel:** Sie möchten ein Video-Tutorial für ein komplexes Produkt hinzufügen. Sie klicken auf „Neuen Block hinzufügen“.
  - **Inhaltseditor:** Für jeden Block haben Sie einen Rich-Text-Editor (WYSIWYG), in dem Sie Text, Bilder, Videos oder sogar benutzerdefiniertes HTML eingeben können.
    - **Was diese Einstellung bewirkt:** Definiert den tatsächlichen Inhalt, der angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird im Frontend gerendert.
    - **Händlerszenario / Beispiel:** Sie tippen „Sehen Sie sich unser Unboxing-Video an!“ und betten einen YouTube-Videolink ein.
  - **Hook-Auswahl:** Ein Dropdown-Menü oder eine Liste der verfügbaren PrestaShop-Hooks (`displayHeader`, `displayFooterProduct`, `displayRightColumnProduct`, etc.).
    - **Was diese Einstellung bewirkt:** Bestimmt die genaue Position, an der Ihr Inhaltsblock auf der Produktseite erscheint.
    - **Auswirkung der Änderung dieser Einstellung:** Der Block wird an der Position des ausgewählten Hooks gerendert.
    - **Empfohlener Wert:** Wählen Sie den Hook, der am besten zum Zweck des Inhalts passt. Für produktspezifische Details sind `displayProductAdditionalInfo` oder `displayFooterProduct` üblich. Für Vertrauenselemente `displayReassurance`.
    - **Händlerszenario / Beispiel:** Sie möchten, dass ein Vertrauenssiegel in der Nähe der Schaltfläche „In den Warenkorb“ erscheint, also wählen Sie `displayReassurance`.
  - **Block-Status (Aktiviert/Deaktiviert):** Ein Schalter zum Aktivieren oder Deaktivieren des Blocks.
    - **Was diese Einstellung bewirkt:** Steuert, ob der Block im Frontend sichtbar ist.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert:* Der Block erscheint auf der Produktseite.
      - *Wenn deaktiviert:* Der Block wird ausgeblendet, aber nicht gelöscht, sodass Sie ihn später wieder aktivieren können.
    - **Empfohlener Wert:** Aktivieren Sie Blöcke, die Sie anzeigen möchten, deaktivieren Sie diejenigen, die Sie vorübergehend ausblenden möchten.
    - **Händlerszenario / Beispiel:** Sie haben einen saisonalen Aktionsblock, den Sie nach Saisonende ausblenden möchten, aber nächstes Jahr wiederverwenden könnten.
  - **Reihenfolge/Position:** Oft eine Drag-and-Drop-Oberfläche oder ein Eingabefeld, um die Anzeigereihenfolge festzulegen, wenn mehrere Blöcke im selben Hook sind.
    - **Was diese Einstellung bewirkt:** Bestimmt die Reihenfolge der Blöcke innerhalb eines einzelnen Hooks.
    - **Auswirkung der Änderung dieser Einstellung:** Blöcke erscheinen in der angegebenen Reihenfolge.
    - **Händlerszenario / Beispiel:** Sie haben drei Vertrauenssiegel in `displayReassurance` und möchten, dass das Siegel „Kostenloser Versand“ zuerst erscheint.
  - **Blöcke bearbeiten/löschen:** Schaltflächen zum Ändern bestehender Blöcke oder zum vollständigen Entfernen.
    - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Inhalt, Hook oder Status zu aktualisieren oder einen Block dauerhaft zu entfernen.
    - **Auswirkung der Änderung dieser Einstellung:** Aktualisiert oder entfernt den Block von der Produktseite.
    - **Händlerszenario / Beispiel:** Eine Produktbeschreibung hat sich geändert, also bearbeiten Sie den Inhalt eines zugehörigen Blocks.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. Navigieren Sie zu **Katalog > Produkte** und wählen Sie das Produkt aus, das Sie verbessern möchten.
  2. Klicken Sie auf den Tab „Produktseiten-Inhaltsblöcke“.
  3. Klicken Sie auf „Neuen Block hinzufügen“, um einen neuen Inhaltsbereich zu erstellen.
  4. Geben Sie Ihren Inhalt mit dem Rich-Text-Editor ein.
  5. Wählen Sie den passenden Hook aus, wo der Inhalt erscheinen soll.
  6. Stellen Sie sicher, dass der Block aktiviert ist.
  7. Speichern Sie Ihre Änderungen für das Produkt.
  8. Wiederholen Sie dies bei Bedarf für andere Produkte. Überprüfen Sie regelmäßig Ihre Produktseiten, um sicherzustellen, dass die Blöcke wie beabsichtigt angezeigt werden.

#### 2.2.2 AdminMegablocksAjaxController (megablocks/controllers/admin/AdminMegablocksAjax.php)

Dieser Controller wird von Händlern nicht direkt über ein Menüelement aufgerufen. Stattdessen verarbeitet er die Hintergrundoperationen (AJAX-Anfragen), wenn Sie mit dem Tab „Produktseiten-Inhaltsblöcke“ auf der Produktbearbeitungsseite interagieren. Wenn Sie beispielsweise einen neuen Block speichern, einen bestehenden bearbeiten oder dessen Reihenfolge ändern, verarbeitet dieser Controller diese Anfragen, ohne dass ein vollständiges Neuladen der Seite erforderlich ist.

- **Bildschirmname & Menüpfad:** Nicht direkt zugänglich. Er arbeitet im Hintergrund auf der Produktbearbeitungsseite.
- **Verfügbare Aktionen & Einstellungen:** Er verwaltet das Erstellen, Aktualisieren, Löschen und Neuanordnen von Inhaltsblöcken für einzelne Produkte.
- **Auswirkung von Änderungen:** Stellt sicher, dass Ihre Änderungen an Inhaltsblöcken auf der Produktbearbeitungsseite in der Datenbank gespeichert und im Frontend widergespiegelt werden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Sie interagieren implizit mit diesem Controller, indem Sie den Tab „Produktseiten-Inhaltsblöcke“ auf der Produktbearbeitungsseite verwenden. Eine direkte Interaktion ist nicht erforderlich.

#### 2.2.3 index.php (megablocks/controllers/admin/index.php)

Diese Datei ist eine Standard-PrestaShop-Praxis zur Sicherung von Admin-Controller-Verzeichnissen und enthält typischerweise nur eine `die('Access Denied');`-Anweisung. Sie stellt keinen funktionalen Bildschirm oder Konfigurationsbereich für den Händler dar.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | (Globale Einstellungen, falls vorhanden) | (Gemäß Modul-Standard) | Ersteinrichtung, globale Aktivierung/Deaktivierung oder allgemeines Modulverhalten. |
| **Produktbearbeitungsseite (Tab)** | Neuen Block hinzufügen | N/A | Erstellt einen neuen Inhaltsblock für das aktuelle Produkt. |
| | Inhaltseditor | Leer | Definiert den HTML/Text-Inhalt des Blocks. |
| | Hook-Auswahl | Variiert (z.B. `displayFooterProduct`) | Bestimmt die Anzeigeposition auf der Produktseite. |
| | Block-Status | Aktiviert | Steuert die Sichtbarkeit des Blocks im Frontend. |
| | Reihenfolge/Position | 1 (oder nächstverfügbar) | Legt die Anzeigereihenfolge der Blöcke innerhalb eines Hooks fest. |
| | Block bearbeiten/löschen | N/A | Ändert oder entfernt bestehende Inhaltsblöcke. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein neuer Inhaltsblock wird auf der Produktseite nicht angezeigt. Was soll ich tun?**
**A1:**

1. **Block-Status überprüfen:** Gehen Sie zur Produktbearbeitungsseite, navigieren Sie zum Tab „Produktseiten-Inhaltsblöcke“ und stellen Sie sicher, dass der von Ihnen erstellte Block auf „Aktiviert“ gesetzt ist.
2. **Cache leeren:** PrestaShop verwendet Caching, um Ihren Shop zu beschleunigen. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“, falls verfügbar).
3. **Hook-Auswahl überprüfen:** Überprüfen Sie nochmals, ob Sie einen Hook ausgewählt haben, der von Ihrem Theme auf der Produktseite tatsächlich gerendert wird. Einige Themes verwenden möglicherweise nicht alle Standard-PrestaShop-Hooks.
4. **Theme-Kompatibilität:** Wenn Ihr Theme stark angepasst ist, kann es Standard-Hook-Platzierungen überschreiben. Kontaktieren Sie Ihren Theme-Entwickler oder einen Webmaster, um die Hook-Struktur des Themes zu bestätigen.

**F2: Der Inhaltsblock sieht auf meiner Produktseite seltsam oder ungestylt aus.**
**A2:**

1. **Inhalt überprüfen:** Wenn Sie benutzerdefiniertes HTML hinzugefügt oder Inhalte aus einer anderen Quelle kopiert haben, kann dies zu widersprüchlichen Stilen führen. Versuchen Sie, Ihren Inhalt zuerst in einen einfachen Texteditor einzufügen, um versteckte Formatierungen zu entfernen, und fügen Sie ihn dann erneut in den Editor des Moduls ein.
2. **Modul-CSS:** Das Modul enthält einige grundlegende CSS-Regeln. Wenn Ihr Theme sehr spezifische Stile hat, kann es die Stile des Moduls überschreiben oder mit ihnen in Konflikt geraten.
3. **Benutzerdefiniertes Theme-Styling:** Für fortgeschrittenes Styling benötigen Sie möglicherweise einen Webmaster, der benutzerdefinierte CSS-Regeln zur Stylesheet-Datei Ihres Themes hinzufügt, um den Block an das Design Ihres Shops anzupassen. Sie können die spezifischen HTML-Elemente ansprechen, die vom Modul generiert werden.

**F3: Kann ich dieses Modul für mehrsprachige Shops verwenden?**
**A3:** Ja, typischerweise unterstützen mit diesem Modul erstellte Inhaltsblöcke die Mehrsprachigkeitsfunktion von PrestaShop. Beim Bearbeiten eines Blocks sollten Sie Sprach-Tabs (z.B. Deutsch, Englisch, Französisch) neben dem Inhaltseditor sehen. Sie können für jede Sprache unterschiedliche Inhalte eingeben, um sicherzustellen, dass Ihre Blöcke für Ihre internationalen Kunden lokalisiert sind.

**F4: Ich möchte denselben Block auf mehreren Produktseiten anzeigen. Muss ich ihn wiederholt erstellen?**
**A4:** Dieses Modul ist für *produktspezifische* Inhalte konzipiert. Wenn Sie den *exakt gleichen* Inhaltsblock auf vielen Produkten benötigen, müssten Sie ihn derzeit für jedes Produkt erstellen. Für wirklich globale Inhalte, die auf *allen* Produktseiten (oder allen Seiten eines bestimmten Typs) erscheinen, wäre ein anderer Modultyp (z.B. ein benutzerdefiniertes HTML-Block-Modul, das global hooked) möglicherweise effizienter. Die Stärke dieses Moduls liegt jedoch in seiner Fähigkeit, Inhalte pro Produkt anzupassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Produktseiten-Inhaltsblöcke“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Produktseiten-Inhaltsblöcke“ (`megablocks`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für Installation und Hook-Registrierung nutzt. Seine Kernfunktionalität dreht sich um die Verwaltung produktspezifischer Inhaltsblöcke, die in einer benutzerdefinierten Datenbanktabelle gespeichert werden. Das Modul erweitert die Backoffice-Funktionalität von PrestaShop, indem es einen benutzerdefinierten Tab in die Produktbearbeitungsseite einfügt, der von einem AJAX-Controller verwaltet wird. Die Frontend-Anzeige wird durch das Einhaken in verschiedene `display*`-Hooks auf der Produktseite und das Rendern spezifischer Smarty-Templates erreicht.

### 4.2 Controller (`controllers/`)

- **Frontend-Controller**: Dieses Modul enthält keine dedizierten Frontend-Controller. Die gesamte Frontend-Inhaltswiedergabe erfolgt direkt über registrierte Hooks innerhalb der Hauptmoduldatei `index.php`, die dann spezifische Templates rendert.
- **Backoffice-Admin-Controller**:

  - `megablocks/controllers/admin/AdminMegablocksAjax.php`
    - **Klassenname & Elternklasse**: `AdminMegablocksAjaxController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dieser Controller verarbeitet alle AJAX-Anfragen, die vom Tab „Produktseiten-Inhaltsblöcke“ auf der Produktbearbeitungsseite stammen. Er ist verantwortlich für:
      - Erstellen neuer Inhaltsblöcke.
      - Aktualisieren bestehender Inhaltsblöcke (Inhalt, Hook, Status, Position).
      - Löschen von Inhaltsblöcken.
      - Abrufen von Inhaltsblockdaten für ein bestimmtes Produkt.
      - Er hat keinen direkten Menüeintrag, wird aber über JavaScript-Aufrufe von der Produktbearbeitungsseite aufgerufen.
  - `megablocks/controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Kein funktionaler Controller.
    - **Verantwortlichkeit**: Dies ist eine Sicherheitsdatei, Standard in PrestaShop-Admin-Verzeichnissen, die `die('Access Denied');` enthält, um direktes Verzeichnis-Listing oder Zugriff zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies impliziert, dass die Datenverarbeitung des Moduls (z.B. Speichern und Abrufen von Inhaltsblöcken) wahrscheinlich direkt in der Hauptdatei `megablocks/index.php` verwaltet wird, möglicherweise unter Verwendung von `Db::getInstance()` für direkte Datenbankinteraktionen oder einer einfachen Array-Struktur für die Konfiguration. Wenn eine benutzerdefinierte Datenbanktabelle verwendet wird, würden deren Schema und Interaktionsmethoden in der Hauptmoduldatei definiert.

### 4.4 JavaScript-Assets (`views/js/`)

- `megablocks/js/script.js`
  - **Umfang**: Wahrscheinlich Frontend.
  - **Details**: Dieses Skript würde jegliche clientseitige Logik enthalten, die für die Frontend-Anzeige der Inhaltsblöcke erforderlich ist. Dies könnte einfache Animationen, responsive Anpassungen oder Interaktionen umfassen, wenn die Blöcke dynamische Elemente enthalten.
- `megablocks/views/admin/megablocks.js`
  - **Umfang**: Backoffice (Produktbearbeitungsseite).
  - **Details**: Dies ist die primäre JavaScript-Datei zur Verwaltung von Inhaltsblöcken im Backoffice. Sie ist verantwortlich für:
    - Initialisieren des Tabs „Produktseiten-Inhaltsblöcke“ auf der Produktbearbeitungsseite.
    - Behandeln von Klickereignissen für die Schaltflächen „Neuen Block hinzufügen“, „Bearbeiten“ und „Löschen“.
    - Verwalten des Rich-Text-Editors (z.B. TinyMCE- oder CKEditor-Integration) für die Inhaltseingabe.
    - Senden von AJAX-Anfragen an `AdminMegablocksAjaxController` zum Erstellen, Aktualisieren und Löschen von Blöcken.
    - Dynamisches Aktualisieren der Benutzeroberfläche basierend auf AJAX-Antworten (z.B. Hinzufügen eines neuen Blocks zur Liste, Entfernen eines gelöschten Blocks).
    - Implementieren der Drag-and-Drop-Funktionalität zum Neuanordnen von Blöcken.
- `megablocks/views/fancybox/script.js`
  - **Umfang**: Backoffice (Produktbearbeitungsseite).
  - **Details**: Dieses Skript integriert sich wahrscheinlich in oder implementiert eine „Fancybox“ (oder eine ähnliche Modal-/Lightbox-Bibliothek) zur Anzeige der Formulare „Neuen Block hinzufügen“ oder „Block bearbeiten“ in einem Popup-Fenster. Es würde das Öffnen/Schließen des Modals, das Laden von Inhalten darin und das Absenden der Formulardaten verwalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `megablocks/views/admin/megablocks.css`
  - **Umfang**: Styling des Backoffice-Admin-Formulars.
  - **Details**: Enthält spezifische CSS-Regeln zum Stylen des Tabs „Produktseiten-Inhaltsblöcke“, der Liste der Blöcke, der Hinzufügen-/Bearbeiten-Formulare und aller benutzerdefinierten UI-Elemente innerhalb des PrestaShop-Backoffice.
  - **Wichtige CSS-Klassenselektoren**: Entwickler können den generierten HTML-Code auf der Produktbearbeitungsseite überprüfen, um spezifische Klassen (z.B. `.megablocks-list`, `.megablock-item`, `.megablock-form`) zu identifizieren, die in ihrem benutzerdefinierten Admin-Theme oder Modul-Overrides überschrieben oder erweitert werden können.
- `megablocks/views/css/milligram.css`
  - **Umfang**: Potenziell sowohl Frontend als auch Backoffice, oder speziell für Modulformulare.
  - **Details**: Milligram ist ein minimalistisches CSS-Framework. Seine Einbindung deutet darauf hin, dass das Modul es für ein grundlegendes, sauberes Styling seiner generierten Inhaltsblöcke im Frontend oder für die Modulformulare im Backoffice (z.B. Fancybox-Inhalte) verwenden könnte. Es bietet eine leichte Basis für Typografie, Formulare und Rasterlayout.
  - **Wichtige CSS-Klassenselektoren**: Standard-Milligram-Klassen (z.B. `.container`, `.row`, `.column`, `.button`, `.input`) wären vorhanden. Entwickler können diese überschreiben oder spezifischere Stile in der CSS-Datei ihres Themes hinzufügen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/front/`)**: Diese Templates werden vom Modul dynamisch eingebunden, wenn ein Inhaltsblock für einen bestimmten Hook konfiguriert ist. Jede `megablock-*.tpl`-Datei dient wahrscheinlich als Wrapper oder Standard-Template zum Rendern des Inhalts eines einzelnen Blocks. Der tatsächliche Inhalt (HTML), der vom Händler definiert wird, wird normalerweise als Smarty-Variable übergeben und direkt gerendert.

  - `megablocks/views/front/megablock-actionProductOutOfStock.tpl`: Rendert Inhalte, wenn ein Produkt nicht vorrätig ist.
  - `megablocks/views/front/megablock-displayAfterProductThumbs.tpl`: Rendert Inhalte nach den Produktbildern/Thumbnails.
  - `megablocks/views/front/megablock-displayBeforeBodyClosingTag.tpl`: Rendert Inhalte direkt vor dem `</body>`-Tag.
  - `megablocks/views/front/megablock-displayFooter.tpl`: Rendert Inhalte im allgemeinen Website-Footer.
  - `megablocks/views/front/megablock-displayFooterBefore.tpl`: Rendert Inhalte vor dem allgemeinen Website-Footer.
  - `megablocks/views/front/megablock-displayFooterProduct.tpl`: Rendert Inhalte im produktspezifischen Footer-Bereich.
  - `megablocks/views/front/megablock-displayHeader.tpl`: Rendert Inhalte im allgemeinen Website-Header.
  - `megablocks/views/front/megablock-displayLeftColumnProduct.tpl`: Rendert Inhalte in der linken Spalte der Produktseite.
  - `megablocks/views/front/megablock-displayNav1.tpl`: Rendert Inhalte im ersten Navigationsbereich.
  - `megablocks/views/front/megablock-displayNav2.tpl`: Rendert Inhalte im zweiten Navigationsbereich.
  - `megablocks/views/front/megablock-displayProductAdditionalInfo.tpl`: Rendert Inhalte im Bereich der zusätzlichen Produktinformationen.
  - `megablocks/views/front/megablock-displayProductPriceBlock.tpl`: Rendert Inhalte in der Nähe des Produktpreisblocks.
  - `megablocks/views/front/megablock-displayReassurance.tpl`: Rendert Inhalte im Vertrauensblock (z.B. Vertrauenssiegel).
  - `megablocks/views/front/megablock-displayRightColumnProduct.tpl`: Rendert Inhalte in der rechten Spalte der Produktseite.
  - `megablocks/views/front/megablock-displayTop.tpl`: Rendert Inhalte im oberen Bereich der Seite.
- **Admin-Templates (`views/templates/admin/`)**:

  - `megablocks/views/admin/li_megablock.tpl`: Dieses Template wird wahrscheinlich verwendet, um ein einzelnes Element in der Liste der Inhaltsblöcke auf der Produktbearbeitungsseite zu rendern. Es würde den Titel des Blocks, den ausgewählten Hook, den Status und die Bearbeiten-/Löschen-Schaltflächen anzeigen.
  - `megablocks/views/admin/tabs.tpl`: Dieses Template definiert wahrscheinlich die Struktur des Tabs „Produktseiten-Inhaltsblöcke“ selbst, einschließlich der Schaltfläche „Neuen Block hinzufügen“ und des Containers für die Liste der Blöcke.
- **Fancybox-Templates (`views/fancybox/`)**: Diese Templates werden für die Modulformulare (Fancybox) im Backoffice verwendet.

  - `megablocks/views/fancybox/edit.tpl`: Das Formular-Template zum Bearbeiten eines bestehenden Inhaltsblocks.
  - `megablocks/views/fancybox/heading.tpl`: Ein Template für die Überschrift oder den Titel des Fancybox-Modals.
  - `megablocks/views/fancybox/new.tpl`: Das Formular-Template zum Erstellen eines neuen Inhaltsblocks.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt wahrscheinlich eine benutzerdefinierte Datenbanktabelle, zum Beispiel `ps_megablocks` (oder ähnlich), um die Inhaltsblöcke zu speichern.
  - Diese Tabelle würde typischerweise Felder wie:
    - `id_megablock`: Primärschlüssel.
    - `id_product`: Fremdschlüssel, der auf `ps_product` verweist.
    - `hook_name`: Der Name des PrestaShop-Hooks, in dem der Block angezeigt wird (z.B. `displayFooterProduct`).
    - `position`: Die Reihenfolge des Blocks innerhalb seines Hooks.
    - `active`: Boolean (0 oder 1) für den Blockstatus.
    - `content`: Der tatsächliche HTML-Inhalt des Blocks (wahrscheinlich ein `TEXT`- oder `LONGTEXT`-Feld).
    - `content_lang`: Wenn der Inhalt mehrsprachig ist, könnte dies eine separate Tabelle (`ps_megablocks_lang`) sein oder über serialisierte Daten in `content` gehandhabt werden.
  - Konfigurationseinträge werden in `ps_configuration` für globale Moduleinstellungen gespeichert (z.B. `MEGABLOCKS_ENABLED`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :--- | :--- | :--- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich des HTML-Dokuments. | Primär zum Einbinden von CSS, JavaScript, Meta-Tags oder anderen Elementen, die das technische Verhalten oder das globale Styling der Seite beeinflussen. |
| `displayNav1` | Rendert Inhalte im ersten Navigationsbereich. | Typischerweise zum Anzeigen von Elementen wie Währungsauswahlen, Sprachauswahlen oder Schnelllinks. |
| `displayNav2` | Rendert Inhalte im zweiten Navigationsbereich. | Oft für Kundenkontolinks, Kontaktinformationen oder andere sekundäre Navigationselemente verwendet. |
| `displayTop` | Rendert Inhalte im oberen Bereich der Seite, normalerweise unterhalb des Headers, aber oberhalb des Hauptinhalts. | Ideal für Banner, Suchleisten oder wichtige Ankündigungen. |
| `displayLeftColumnProduct` | Rendert Inhalte in der linken Seitenleiste der Produktseite. | Geeignet für Produktfilter, verwandte Kategorien oder produktspezifische Werbeblöcke. |
| `displayRightColumnProduct` | Rendert Inhalte in der rechten Seitenleiste der Produktseite. | Ähnlich wie die linke Spalte, kann für Cross-Sells, Kundendienstinformationen oder Vertrauenssiegel verwendet werden. |
| `displayAfterProductThumbs` | Rendert Inhalte unmittelbar nach den Produktbild-Thumbnails. | Gut für schnelle Produkthighlights, kurze Videos oder spezifische Feature-Callouts. |
| `displayProductAdditionalInfo` | Rendert Inhalte innerhalb des Hauptinformationsblocks des Produkts, oft in der Nähe der Beschreibung oder der Merkmale. | Hervorragend für detaillierte Spezifikationen, Gebrauchsanweisungen oder einzigartige Verkaufsargumente. |
| `displayProductPriceBlock` | Rendert Inhalte in der Nähe der Produktpreisanzeige. | Nützlich zum Anzeigen von Finanzierungsoptionen, Preisgarantien oder speziellen Rabattmeldungen. |
| `displayReassurance` | Rendert Inhalte im Produkt-Vertrauensblock, typischerweise in der Nähe des „In den Warenkorb“-Buttons. | Perfekt für Vertrauenssiegel, Lieferinformationen, Rückgaberichtlinien oder sichere Zahlungssymbole. |
| `displayFooterProduct` | Rendert Inhalte im produktspezifischen Footer-Bereich, normalerweise unterhalb der Hauptproduktdetails. | Kann für erweiterte Produktdetails, FAQs oder Kundenbewertungen verwendet werden. |
| `actionProductOutOfStock` | Wird ausgeführt, wenn ein Produkt nicht mehr vorrätig ist. | Ermöglicht die Anzeige spezifischer Nachrichten oder Formulare für nicht vorrätige Produkte. |
| `displayFooterBefore` | Rendert Inhalte direkt vor dem Haupt-Website-Footer. | Geeignet für Last-Minute-Aktionen oder Call-to-Actions vor dem Footer. |
| `displayFooter` | Rendert Inhalte im allgemeinen Website-Footer. | Für websiteweite Informationen, kann aber pro Produkt für einzigartige Footer-Elemente angepasst werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produktseiten-Inhaltsblöcke“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität des Moduls und dessen Integration in Ihren PrestaShop-Shop zur Verfügung.
