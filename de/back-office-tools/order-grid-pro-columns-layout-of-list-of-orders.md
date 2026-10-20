---
title: "Order Grid Pro - Spalten & Layout der Bestellliste - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Order Grid Pro - Spalten & Layout der Bestellliste“ von MyPresta.eu."
sidebar:
  label: "Order Grid Pro - Spalten & Layout der Bestellliste - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order Grid Pro - columns & layout of list of orders auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/order-grid-pro-columns-layout-of-list-of-orders.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/order-grid-pro-columns-layout-of-list-of-orders/)
>
> ---


# Order Grid Pro - Spalten & Layout der Bestellliste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für Order Grid Pro. Auf dieser Seite legen Sie fest, welche Spalten in Ihrer Bestellliste erscheinen und deren Anordnung.

Die Konfiguration ist typischerweise in mehrere Registerkarten oder Abschnitte unterteilt, die es Ihnen ermöglichen, verschiedene Aspekte des Bestellrasters zu verwalten.

**Allgemeine Einstellungen / Spaltensichtbarkeit & Reihenfolge:**
Dies ist der Kern des Moduls. Sie sehen normalerweise eine Liste aller verfügbaren Spalten, sowohl die Standard-PrestaShop-Spalten als auch die neuen, die von Order Grid Pro hinzugefügt wurden.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, auszuwählen, welche Spalten in Ihrer Back Office-Bestellliste sichtbar sind, und deren Anzeigereihenfolge festzulegen. Sie sehen normalerweise zwei Listen: „Verfügbare Spalten“ und „Aktive Spalten“ (oder ähnliches).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Verschieben einer Spalte von „Verfügbar“ zu „Aktiv“:* Die Spalte wird in Ihrer Back Office-Bestellliste angezeigt.
  - *Verschieben einer Spalte von „Aktiv“ zu „Verfügbar“:* Die Spalte wird aus Ihrer Back Office-Bestellliste ausgeblendet.
  - *Ziehen und Ablegen von Spalten innerhalb von „Aktive Spalten“:* Ändert die Anzeigereihenfolge der Spalten von links nach rechts in Ihrer Bestellliste.
- **Empfohlener Wert:** Dies hängt vollständig von den Bedürfnissen Ihres Teams ab. Beginnen Sie damit, Spalten zu aktivieren, die Sie häufig überprüfen, und diejenigen auszublenden, die Sie nie verwenden. Ordnen Sie sie in einem logischen Fluss für Ihre täglichen Aufgaben an.
- **Händlerszenario / Beispiel:**
  - **Lagerleiter:** Könnte „Produktminiatur“, „Produktgewicht“, „Sendungsverfolgungsnummer“ und „Versanddienstleister“ aktivieren und diese für eine schnelle Versandabwicklung prominent links platzieren. Er könnte „Kunden-E-Mail“ oder „Zahlungsmethode“ ausblenden, wenn diese für seine Rolle nicht relevant sind.
  - **Kundendienstmitarbeiter:** Würde „Kundentelefon“, „Kunden-E-Mail“, „Ausschnitt aus Kundenservice-Thread“ und „Bestellnachricht“ priorisieren, um Anfragen schnell zu bearbeiten, ohne jede Bestellung öffnen zu müssen.
  - **Finanzabteilung:** Könnte sich auf „Zahlungsmethode“, „Währungs-ISO“, „Gesamtbetrag bezahlt“ und „Warenkorbregeln“ konzentrieren, um Transaktionen und Rabatte zu überprüfen.

**Spezifische Spaltenoptionen (Beispiele für neue Spalten, die Sie aktivieren können):**

- **Kundentelefon:**

  - **Was diese Einstellung bewirkt:** Zeigt die Telefonnummer des Kunden direkt in der Bestellliste an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Telefonnummern werden angezeigt, was es einfach macht, Kunden anzurufen, ohne zu den Bestelldetails navigieren zu müssen.
    - *Wenn deaktiviert:* Telefonnummern werden ausgeblendet.
  - **Empfohlener Wert:** JA, wenn Ihr Kundenservice- oder Versandteam häufig Kunden kontaktieren muss.
  - **Händlerszenario / Beispiel:** Ein Kundendienstmitarbeiter kann einen Kunden bei einem Lieferproblem schnell direkt aus der Bestellliste anrufen.
- **Sendungsverfolgungsnummer:**

  - **Was diese Einstellung bewirkt:** Zeigt die mit der Bestellung verknüpfte Sendungsverfolgungsnummer an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sendungsverfolgungsnummern sind sichtbar, was ein schnelles Kopieren und Einfügen für Sendungsverfolgungsaktualisierungen ermöglicht.
    - *Wenn deaktiviert:* Sendungsverfolgungsnummern werden ausgeblendet.
  - **Empfohlener Wert:** JA, unerlässlich für Lager- und Kundendienstteams.
  - **Händlerszenario / Beispiel:** Lagerpersonal kann schnell überprüfen, ob eine Sendungsverfolgungsnummer vor dem Versand hinzugefügt wurde, oder der Kundendienst kann sie einem Kunden mitteilen.
- **Produktminiatur der ersten Zeile:**

  - **Was diese Einstellung bewirkt:** Zeigt ein kleines Bild des ersten Produkts in der Bestellung an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein visueller Hinweis auf den Inhalt der Bestellung erscheint, der eine schnelle Identifizierung unterstützt.
    - *Wenn deaktiviert:* Es wird kein Produktbild angezeigt.
  - **Empfohlener Wert:** JA, sehr hilfreich für die visuelle Bestätigung, insbesondere bei der Lagerkommissionierung.
  - **Händlerszenario / Beispiel:** Lagerpersonal kann den Produkttyp in einer Bestellung visuell bestätigen, ohne sie öffnen zu müssen, was die Kommissionierung beschleunigt.
- **Bestellgewicht:**

  - **Was diese Einstellung bewirkt:** Zeigt das Gesamtgewicht der Bestellung an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Bestellgewicht wird angezeigt, nützlich für Versandberechnungen oder die Auswahl des Versanddienstleisters.
    - *Wenn deaktiviert:* Das Bestellgewicht wird ausgeblendet.
  - **Empfohlener Wert:** JA, wenn Sie mit physischen Produkten handeln und das Gewicht ein Faktor beim Versand ist.
  - **Händlerszenario / Beispiel:** Versandmanager können schnell Paketgrößen und -gewichte für Massensendungen beurteilen.
- **Ausschnitt aus Kundenservice-Thread:**

  - **Was diese Einstellung bewirkt:** Zeigt einen kurzen Ausschnitt aus der neuesten Kundenservice-Nachricht an, die mit der Bestellung zusammenhängt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Bietet sofortigen Kontext zu den letzten Kundenkommunikationen.
    - *Wenn deaktiviert:* Es wird kein Ausschnitt angezeigt.
  - **Empfohlener Wert:** JA, von unschätzbarem Wert für Kundendienstteams.
  - **Händlerszenario / Beispiel:** Ein Kundendienstmitarbeiter kann sehen, ob ein Kunde kürzlich eine Anfrage zu einer Bestellung gestellt hat, ohne den gesamten Thread öffnen zu müssen.
- **Währungs-ISO:**

  - **Was diese Einstellung bewirkt:** Zeigt den ISO-Code der für die Bestellung verwendeten Währung an (z.B. EUR, USD).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Nützlich für internationale Shops, um die Währung schnell zu identifizieren.
    - *Wenn deaktiviert:* Währungs-ISO wird ausgeblendet.
  - **Empfohlener Wert:** JA, wenn Sie einen Multi-Währungs-Shop betreiben.
  - **Händlerszenario / Beispiel:** Finanzmitarbeiter können Bestellungen schnell nach Währung sortieren oder filtern, um sie abzugleichen.
- **Angewendete Warenkorbregeln (Rabatte):**

  - **Was diese Einstellung bewirkt:** Zeigt an, ob Warenkorbregeln (Rabatte) auf die Bestellung angewendet wurden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Bietet einen schnellen Überblick über rabattierte Bestellungen.
    - *Wenn deaktiviert:* Informationen über angewendete Rabatte werden ausgeblendet.
  - **Empfohlener Wert:** JA, für Finanzen, Marketing oder Kundenservice, um die Preisgestaltung zu verstehen.
  - **Händlerszenario / Beispiel:** Marketing kann schnell Bestellungen identifizieren, die einen bestimmten Aktionscode verwendet haben.

**Änderungen speichern:**
Denken Sie immer daran, nach Änderungen an Ihrer Spaltenauswahl oder -reihenfolge auf die Schaltfläche „Speichern“ oder „Aktualisieren“ zu klicken. Das Modul speichert die Spaltenreihenfolge als JSON, wodurch Ihr benutzerdefiniertes Layout erhalten bleibt.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminMyordergridproAjaxController (Back Office > Module > Konfigurieren > Order Grid Pro)

Dieser Controller verarbeitet hauptsächlich die dynamischen Interaktionen auf der Konfigurationsseite des Moduls. Er hat keinen separaten Menüpunkt in der PrestaShop-Navigation.

- **Bildschirmname & Menüpfad:** Dieser Controller wird aktiviert, wenn Sie sich auf der Seite „Module > Modul-Manager > Order Grid Pro > Konfigurieren“ befinden. Er verarbeitet AJAX-Anfragen, die vom JavaScript auf dieser Seite gestellt werden.
- **Verfügbare Aktionen & Einstellungen:** Er verwaltet das Speichern und Laden Ihrer benutzerdefinierten Rasterkonfigurationen (welche Spalten sichtbar sind und deren Reihenfolge). Wenn Sie Spalten per Drag-and-Drop verschieben oder deren Sichtbarkeit auf der Konfigurationsseite des Moduls umschalten, empfängt dieser Controller die Daten und speichert sie.
- **Auswirkung von Änderungen:** Alle Änderungen, die Sie am Spaltenlayout auf der Konfigurationsseite des Moduls vornehmen, werden an diesen Controller gesendet, der dann die gespeicherten Präferenzen für Ihr Bestellraster aktualisiert. Dies stellt sicher, dass beim Navigieren zu „Bestellungen > Bestellungen“ Ihr benutzerdefiniertes Layout angewendet wird.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Sie interagieren indirekt mit diesem Controller, indem Sie das Modul einfach auf seiner Hauptseite konfigurieren. Es gibt hier keine direkte „Verwaltungsansicht“ für Händler; es ist der Backend-Prozessor für Ihre Konfigurationsentscheidungen.

#### 2.2.2 index.php (myordergridpro/controllers/admin/index.php)

Diese Datei ist ein Standard-Platzhalter oder Einstiegspunkt für Admin-Controller innerhalb eines Moduls, der sicherstellt, dass der direkte Zugriff auf das Verzeichnis verhindert und die Sicherheitsmechanismen von PrestaShop eingehalten werden. Sie stellt keinen eigenständigen, konfigurierbaren Bildschirm für den Händler dar.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | **Spaltensichtbarkeit & Reihenfolge** | Variiert je nach Rolle | Wählt aus, welche Spalten in der Back Office-Bestellliste erscheinen und deren Anzeigereihenfolge. Wirkt sich direkt auf die Teameffizienz aus. |
|  | *Kundentelefon* | JA | Zeigt die Telefonnummer des Kunden für schnelle Kontaktaufnahme an. |
|  | *Sendungsverfolgungsnummer* | JA | Zeigt die Sendungsverfolgungsnummer der Bestellung für Versand/Support an. |
|  | *Produktminiatur der ersten Zeile* | JA | Visueller Hinweis auf das erste Produkt in der Bestellung. |
|  | *Bestellgewicht* | JA (für physische Güter) | Zeigt das Gesamtgewicht der Bestellung für den Versand an. |
|  | *Ausschnitt aus Kundenservice-Thread* | JA | Bietet Kontext zu den letzten Kundenkommunikationen. |
|  | *Währungs-ISO* | JA (für Multi-Währung) | Zeigt den Währungscode für internationale Shops an. |
|  | *Angewendete Warenkorbregeln* | JA | Zeigt an, ob Rabatte auf die Bestellung angewendet wurden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Spalten konfiguriert, sehe die Änderungen aber nicht auf der Bestellseite.**
A:

1. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal speichert PrestaShop Modulkonfigurationen im Cache.
2. **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder das Back Office in einem Inkognito-/privaten Fenster zu öffnen, um sicherzustellen, dass Sie keine alte, zwischengespeicherte Version der Seite sehen.
3. **Konfiguration speichern:** Überprüfen Sie nochmals, ob Sie nach Ihren Änderungen auf der Konfigurationsseite des Moduls auf die Schaltfläche „Speichern“ oder „Aktualisieren“ geklickt haben.

**F: Einige Spalten, die ich aktiviert habe, sind leer oder zeigen „N/A“ an. Warum?**
A: Dies bedeutet normalerweise, dass die Daten für diese spezifische Spalte für diese bestimmte Bestellung nicht verfügbar sind. Zum Beispiel:

- „Sendungsverfolgungsnummer“ ist leer, wenn der Bestellung keine Sendungsverfolgungsnummer hinzugefügt wurde.
- „Ausschnitt aus Kundenservice-Thread“ ist leer, wenn für diese Bestellung keine Kundenservice-Nachrichten vorhanden sind.
- „Bestellgewicht“ kann leer sein, wenn Produktgewichte nicht definiert sind oder wenn die Bestellung nur virtuelle Produkte enthält.
Dies ist ein normales Verhalten und weist auf fehlende Daten hin, nicht auf einen Modulfehler.

**F: Das Drag-and-Drop zum Neuanordnen von Spalten funktioniert nicht.**
A:

1. **JavaScript-Konflikt:** Ein anderes Modul oder Ihr Theme könnte einen JavaScript-Konflikt verursachen. Versuchen Sie, andere kürzlich installierte Module nacheinander zu deaktivieren, um den Übeltäter zu identifizieren.
2. **Browser-Problem:** Testen Sie in einem anderen Browser (Chrome, Firefox, Edge), um ein browserspezifisches Problem auszuschließen.
3. **Cache leeren:** Leeren Sie sowohl den PrestaShop- als auch den Browser-Cache wie oben beschrieben.

**F: Wird dieses Modul mein Back Office verlangsamen?**
A: Das Modul wurde entwickelt, um offizielle PrestaShop-Grid-Hooks zu verwenden und Kernüberschreibungen zu vermeiden, was zur Aufrechterhaltung der Leistung und Kompatibilität beiträgt. Während das Hinzufügen vieler neuer Spalten PrestaShop dazu zwingt, mehr Daten abzurufen, ist die Auswirkung im Allgemeinen minimal. Wenn Sie erhebliche Verlangsamungen bemerken, sollten Sie die Anzahl der aktivierten, hochkomplexen benutzerdefinierten Spalten reduzieren.

**F: Ist dieses Modul mit meinem benutzerdefinierten Theme kompatibel?**
A: Ja, dieses Modul funktioniert innerhalb des PrestaShop-Backoffice, das sein eigenes Standard-Theme (New Classic oder ähnlich) verwendet. Es beeinflusst Ihr Front-Office-Theme nicht, daher sollte es keine Kompatibilitätsprobleme mit benutzerdefinierten Front-Office-Themes geben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Order Grid Pro“ erweitert die Funktionalität der PrestaShop-Backoffice-Bestellliste und zielt speziell auf das Symfony-Grid-System ab, das in PrestaShop 1.7.7+ eingeführt wurde. Es hält sich an die Best Practices der PrestaShop-Modulentwicklung, indem es offizielle Hooks (`actionGet` und `actionSet` für Grid-Definitionen) anstelle direkter Kernüberschreibungen verwendet. Dies gewährleistet Upgrade-Kompatibilität und Stabilität. Das Modul injiziert hauptsächlich neue Spaltendefinitionen und Datenanbieter in das bestehende Bestellraster und speichert Benutzerpräferenzen für Spaltensichtbarkeit und -reihenfolge mithilfe der Standard-PrestaShop-Konfiguration. AJAX-Aufrufe verwalten dynamische Aktualisierungen dieser Präferenzen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Dieses Modul ist rein Back-Office.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMyordergridproAjaxController.php`
    - **Klassenname & Elternklasse**: `AdminMyordergridproAjaxController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dieser Controller ist für die Verarbeitung von AJAX-Anfragen von der Konfigurationsseite des Moduls verantwortlich. Er verarbeitet Anfragen zum Speichern und Laden der benutzerdefinierten Bestellrasterkonfiguration (Spaltensichtbarkeit und -reihenfolge). Er empfängt typischerweise JSON-Daten, die das gewünschte Rasterlayout darstellen, und speichert sie in `Configuration::updateValue()`.
    - **Routen**: Reagiert auf AJAX-Aufrufe an `index.php?controller=AdminMyordergridproAjax&token=...&ajax=1`.
  - `controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Keine Klasse, sondern eine Sicherheitsdatei.
    - **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die in Controller-Verzeichnissen platziert wird, um die Verzeichnisauflistung und den direkten Zugriff zu verhindern und die Sicherheit zu erhöhen. Sie enthält typischerweise `<?php header('Expires: Mon, 26 Jul 1997 05:00:00 GMT'); header('Last-Modified: '.gmdate('D, d M Y H:i:s').' GMT'); header('Cache-Control: no-store, no-cache, must-revalidate'); header('Cache-Control: post-check=0, pre-check=0', false); header('Pragma: no-cache'); header('Location: ../'); exit;`.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten `ObjectModel`-Klassen oder Datenbanktabellen zu definieren. Es funktioniert hauptsächlich durch die Erweiterung bestehender PrestaShop-Grid-Definitionen und die Speicherung von Konfigurationsdaten in `ps_configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/grid_pro.js`

  - **Geltungsbereich**: Back-Office (Bestelllistenseite).
  - **Beschreibung**: Dieses Skript enthält wahrscheinlich die Kernlogik zur Manipulation des PrestaShop Symfony-Grids auf der Seite „Bestellungen > Bestellungen“. Es wäre verantwortlich für:
    - Das Lesen der gespeicherten Spaltenkonfiguration aus `Configuration::get()`.
    - Das dynamische Hinzufügen/Entfernen von Spalten zum Raster basierend auf der Konfiguration.
    - Das Anwenden der benutzerdefinierten Spaltenreihenfolge.
    - Potenziell die Handhabung von Live-Updates oder spezifischer Spalten-Rendering-Logik.
    - Das Binden an PrestaShop-Grid-Ereignisse (z.B. `prestashop.on('grid.loaded', ...)`).
- `views/js/order_grid_admin.js`

  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Beschreibung**: Dieses Skript wird hauptsächlich auf der Konfigurationsseite des Moduls (`getContent()`) verwendet. Es verwaltet die Benutzeroberfläche zur Auswahl und Anordnung von Spalten. Dies beinhaltet:
    - Die Implementierung der Drag-and-Drop-Funktionalität zur Spaltenneuanordnung.
    - Die Verwaltung der Listen „Verfügbare Spalten“ und „Aktive Spalten“.
    - Das Binden von Ereignis-Listenern an Schalter/Kontrollkästchen für die Spaltensichtbarkeit.
    - Das Ausführen von AJAX-Aufrufen an `AdminMyordergridproAjaxController.php`, um die aktualisierte Konfiguration zu speichern.
- `views/js/order_list_live_status.js`

  - **Geltungsbereich**: Back-Office (Bestelllistenseite).
  - **Beschreibung**: Dieses Skript bietet wahrscheinlich Funktionen für Live-Updates oder interaktive Elemente direkt innerhalb der Bestellliste. Dies könnte beinhalten:
    - AJAX-basierte Statusaktualisierungen für Bestellungen ohne Seitenaktualisierung.
    - Tooltips oder Popovers für zusätzliche Informationen zu bestimmten Spalten.
    - Potenziell die Verbesserung der Standard-Dropdowns für Statusänderungen oder das Hinzufügen benutzerdefinierter Schnellaktionen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/order_grid_admin.css`
  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite und potenziell Bestelllistenseite).
  - **Beschreibung**: Dieses Stylesheet bietet die visuelle Gestaltung für die Konfigurationsoberfläche des Moduls und stellt sicher, dass die Drag-and-Drop-Elemente und Spaltenlisten klar dargestellt werden. Es kann auch kleinere Stilkorrekturen für die neuen Spalten enthalten, die in der eigentlichen Bestellliste eingeführt wurden, um eine korrekte Ausrichtung und Lesbarkeit innerhalb des PrestaShop-Backoffice-Themes zu gewährleisten.
  - **Wichtige CSS-Klassenselektoren**: Zielt wahrscheinlich auf spezifische IDs oder Klassen innerhalb des `getContent()`-Templates des Moduls und potenziell auf neue Spaltenklassen, die in das Raster injiziert werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Die Modulinformationen zeigen an, dass keine expliziten `.tpl`-Dateien in `views/templates/` gefunden wurden. Dies deutet darauf hin, dass die Konfigurationsoberfläche des Moduls wahrscheinlich direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei (`index.php`) gerendert wird, wobei PHP zur Generierung des HTML verwendet wird, oder dass es Inhalte dynamisch über Hooks in bestehende PrestaShop-Grid-Templates injiziert.

Wenn Templates vorhanden wären, wären dies typischerweise:

- **Hook-Templates (`views/templates/hook/`)**: Zum Rendern neuer Spalteninhalte innerhalb der Rasterzellen.
- **Admin-Templates (`views/templates/admin/`)**: Für das Konfigurationsformular des Moduls.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen (z.B. der JSON-String, der die Spaltenreihenfolge und -sichtbarkeit darstellt) werden in der Tabelle `ps_configuration` unter Schlüsseln wie `MYORDERGRIDPRO_CONFIG` oder ähnlichem gespeichert.
- **Registrierte Hooks-Tabelle**:
Das Modul stützt sich hauptsächlich auf die Symfony-Grid-Hooks von PrestaShop für seine Funktionalität.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionGet` und `actionSet` (für Grid-Definitionen) | Wenn das Bestellraster im Back Office definiert und gerendert wird. | Dies sind die primären Hooks, die verwendet werden, um neue Spaltendefinitionen und Datenanbieter in das bestehende PrestaShop-Bestellraster zu injizieren. `actionGet` ermöglicht es dem Modul, die aktuelle Grid-Definition abzurufen, und `actionSet` ermöglicht es, neue Spalten zu ändern oder hinzuzufügen, bevor das Raster gerendert wird. |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich jeder Back Office-Seite ausgeführt. | Wird verwendet, um CSS- und JavaScript-Assets (`order_grid_admin.css`, `grid_pro.js`, `order_grid_admin.js`, `order_list_live_status.js`) speziell für das Back Office einzubinden, um sicherzustellen, dass sie bei Bedarf geladen werden. |
| `displayAdminOrderListToolbar` (oder ähnlich) | Rendert Inhalte im Toolbar-Bereich der Bestellliste. | Potenziell verwendet, um Schnellaktionsschaltflächen oder Filter hinzuzufügen, die mit der Funktionalität des Moduls zusammenhängen. |
| `actionAdminOrdersListingFieldsModifier` (oder ähnlich) | Modifiziert die in der Bestelllistenabfrage verfügbaren Felder/Spalten. | Ermöglicht dem Modul, neue Felder zur SQL-Abfrage hinzuzufügen, die Bestelldaten abruft, wodurch die Anzeige benutzerdefinierter Spaltendaten ermöglicht wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für „Order Grid Pro - Spalten & Layout der Bestellliste“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul perfekt funktioniert und Ihnen hilft, die Effizienz Ihres PrestaShop-Shops zu maximieren.
