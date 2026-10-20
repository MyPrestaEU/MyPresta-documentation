---
title: "Mehrere Kategorieblöcke - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Mehrere Kategorieblöcke' von MyPresta.eu."
sidebar:
  label: "Mehrere Kategorieblöcke - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Multiple Categories Blocks auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/multiple-categories-blocks.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/multiple-categories-blocks/)
>
> ---


# Mehrere Kategorieblöcke

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Mehrere Kategorieblöcke)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie alle Ihre benutzerdefinierten Kategorieblöcke erstellen und verwalten.

Beim Betreten der Konfigurationsseite sehen Sie eine Liste der vorhandenen Kategorieblöcke (falls vorhanden) und Optionen zum Hinzufügen neuer Blöcke.

#### **Hinzufügen / Bearbeiten eines Kategorieblocks**

Wenn Sie auf „Neuen Block hinzufügen“ klicken oder einen vorhandenen bearbeiten, werden Ihnen die folgenden Einstellungen präsentiert:

- **Blockname:**

  - **Was diese Einstellung bewirkt:** Dies ist ein interner Name für Ihre Referenz im Back Office. Er hilft Ihnen, verschiedene Blöcke zu identifizieren.
  - **Auswirkung einer Änderung dieser Einstellung:** Betrifft nur, wie Sie den Block im Admin-Panel sehen. Er ist für Kunden nicht sichtbar.
  - **Empfohlener Wert:** Ein aussagekräftiger Name (z.B. „Startseite Elektronik-Kategorien“, „Linke Spalte Bekleidung“).
  - **Händlerszenario / Beispiel:** Wenn Sie einen Block für „Herrenmode“ in der linken Spalte haben, nennen Sie ihn „Linke Spalte - Herrenmode“.
- **Blocktitel anzeigen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob ein Titel (z.B. „Kategorien“) über der Kategorieliste im Front Office angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Ein Titel erscheint über dem Kategorieblock. Sie können diesen Titel im Feld „Blocktitel“ definieren.
    - *Wenn deaktiviert (Nein):* Es wird kein Titel angezeigt, nur die Kategorieliste.
  - **Empfohlener Wert:** „Ja“ für die meisten Blöcke, da es dem Kunden Kontext bietet.
  - **Händlerszenario / Beispiel:** Wenn Ihr Block einfach in das Design übergehen soll, ohne einen expliziten Titel, stellen Sie ihn auf „Nein“.
- **Blocktitel:** (Erscheint nur, wenn „Blocktitel anzeigen“ auf Ja steht)

  - **Was diese Einstellung bewirkt:** Der tatsächliche Text, der als Titel des Blocks im Front Office angezeigt wird. Dies ist mehrsprachig.
  - **Auswirkung einer Änderung dieser Einstellung:** Ändert den sichtbaren Titel für Kunden.
  - **Empfohlener Wert:** Ein klarer, prägnanter Titel (z.B. „Nach Kategorie einkaufen“, „Unsere Produkte“, „Abteilungen“).
  - **Händlerszenario / Beispiel:** Für einen Block, der nur „Elektronik“-Kategorien anzeigt, könnten Sie den Titel auf „Elektronik“ setzen.
- **Hook zum Anzeigen des Blocks:**

  - **Was diese Einstellung bewirkt:** Wählt aus, wo in Ihrem Shop dieser Kategorieblock erscheinen soll. Hooks sind spezifische Anzeigepunkte in Ihrem PrestaShop-Theme.
  - **Auswirkung einer Änderung dieser Einstellung:** Bestimmt den physischen Standort des Blocks auf Ihrer Website.
  - **Empfohlener Wert:** Abhängig von Ihrem Design. Häufige Optionen sind `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`.
  - **Händlerszenario / Beispiel:** Um einen Block in der linken Seitenleiste anzuzeigen, wählen Sie `displayLeftColumn`. Um ihn im Footer anzuzeigen, wählen Sie `displayFooter`.
- **Stammkategorie:**

  - **Was diese Einstellung bewirkt:** Dies ist der Startpunkt (das „Elternteil“) für die in diesem spezifischen Block angezeigten Kategorien. Nur diese Kategorie und ihre Unterkategorien werden angezeigt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Auswahl von „Startseite“:* Der Block zeigt alle Kategorien an, beginnend ganz oben in Ihrem Kategorienbaum.
    - *Auswahl einer spezifischen Kategorie (z.B. „Elektronik“):* Der Block zeigt nur „Elektronik“ und alle ihre Unterkategorien an.
  - **Empfohlener Wert:** Wählen Sie die höchste Kategorieebene, die den Umfang dieses Blocks definiert.
  - **Händlerszenario / Beispiel:** Wenn Sie einen Block speziell für „Kleidung“ wünschen, wählen Sie hier Ihre Kategorie „Kleidung“ aus.
- **Maximale Tiefe:**

  - **Was diese Einstellung bewirkt:** Steuert, wie viele Ebenen von Unterkategorien innerhalb dieses Blocks angezeigt werden, beginnend bei der Stammkategorie.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Einstellung auf 1:* Nur die Stammkategorie selbst wird angezeigt (wenn „Stammkategorie anzeigen“ auf Ja steht).
    - *Einstellung auf 2:* Die Stammkategorie und ihre direkten Unterkategorien werden angezeigt.
    - *Einstellung auf 0 (oder leer):* Alle Unterkategorien, unabhängig von der Tiefe, werden angezeigt.
  - **Empfohlener Wert:** 2 oder 3 für die meisten Spaltenblöcke, um sie übersichtlich zu halten. 0 für Footer-Blöcke, wenn Sie eine vollständige Sitemap wünschen.
  - **Händlerszenario / Beispiel:** Wenn Ihre Kategorie „Elektronik“ Unterkategorien wie „Kameras“ und „Laptops“ hat und „Kameras“ „DSLRs“ und „Spiegellose“ hat, würde eine Tiefeneinstellung von 2 „Elektronik > Kameras, Laptops“ anzeigen. Eine Einstellung auf 3 würde „Elektronik > Kameras > DSLRs, Spiegellose, Laptops“ anzeigen.
- **Dynamisch (aktuellen Kategorienbaum öffnen):**

  - **Was diese Einstellung bewirkt:** Wenn ein Kunde zu einer Kategorieseite navigiert, bestimmt diese Option, ob der Kategorieblock automatisch erweitert wird, um die aktuelle Kategorie und ihre Unterkategorien anzuzeigen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Wenn ein Kunde auf der Seite „DSLRs“ ist, erweitert der Kategorieblock automatisch „Elektronik > Kameras > DSLRs“, um den Pfad anzuzeigen.
    - *Wenn deaktiviert (Nein):* Der Kategorieblock bleibt in seinem standardmäßigen, zusammengeklappten Zustand, unabhängig von der aktuellen Seite.
  - **Empfohlener Wert:** „Ja“ für eine bessere Benutzererfahrung, da es Kunden hilft, ihren aktuellen Standort im Kategorienbaum zu verstehen.
  - **Händlerszenario / Beispiel:** Dies ist besonders nützlich in Seitenleisten, um die Navigation für den aktuellen Browsing-Kontext des Benutzers relevant zu halten.
- **Stammkategorie anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob die „Stammkategorie“ selbst (die Sie oben ausgewählt haben) als oberstes Element im Block angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Die Stammkategorie ist das erste anklickbare Element im Block.
    - *Wenn deaktiviert (Nein):* Der Block beginnt mit der Anzeige der direkten Unterkategorien der Stammkategorie.
  - **Empfohlener Wert:** „Ja“, wenn die Stammkategorie eine breite Kategorie wie „Nach Abteilung einkaufen“ ist. „Nein“, wenn die Stammkategorie nur eine logische Gruppierung ist und Sie direkt mit ihren Unterkategorien beginnen möchten (z.B. ein „Marken“-Block, bei dem „Marken“ selbst keine Produktkategorie ist).
  - **Händlerszenario / Beispiel:** Wenn Ihre Stammkategorie „Herrenbekleidung“ ist und Sie möchten, dass dies der oberste Link ist, stellen Sie auf „Ja“. Wenn Sie möchten, dass der Block direkt mit „Hemden“, „Hosen“ usw. beginnt, stellen Sie auf „Nein“.
- **Anzahl der Produkte anzeigen:**

  - **Was diese Einstellung bewirkt:** Zeigt die Anzahl der verfügbaren Produkte innerhalb jeder Kategorie neben ihrem Namen im Block an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Kategorien erscheinen als „Kategoriename (X)“.
    - *Wenn deaktiviert (Nein):* Nur der Kategoriename wird angezeigt.
  - **Empfohlener Wert:** „Ja“ kann für Kunden hilfreich sein, um die Größe einer Kategorie einzuschätzen, aber „Nein“ kann zu einem saubereren Aussehen führen. Testen Sie beides, um zu sehen, was zu Ihrem Design passt.
  - **Händlerszenario / Beispiel:** Wenn Sie „T-Shirts (125)“ neben dem Kategorienamen anzeigen möchten, aktivieren Sie dies.
- **Kategorien ohne Produkte anzeigen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob Kategorien, denen derzeit keine Produkte zugewiesen sind, weiterhin im Block angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Leere Kategorien werden weiterhin angezeigt.
    - *Wenn deaktiviert (Nein):* Leere Kategorien werden aus dem Block ausgeblendet.
  - **Empfohlener Wert:** „Nein“, um Sackgassen für Kunden zu vermeiden und Ihre Navigation sauber zu halten. Aktivieren Sie „Ja“ nur, wenn Sie einen bestimmten Grund haben, bevorstehende Kategorien anzuzeigen.
  - **Händlerszenario / Beispiel:** Wenn Sie eine neue Produktlinie aufbauen und Kategorien erstellt, aber noch keine Produkte hinzugefügt haben, könnten Sie „Ja“ vorübergehend für interne Tests aktivieren, aber im Allgemeinen „Nein“ für Live-Shops.
- **Sortieren nach:**

  - **Was diese Einstellung bewirkt:** Definiert die Sortierreihenfolge der Kategorien innerhalb des Blocks.
  - **Auswirkung einer Änderung dieser Einstellung:** Ändert die Reihenfolge, in der Kategorien aufgelistet werden.
  - **Empfohlener Wert:** „Position“ (Standard-PrestaShop-Reihenfolge) oder „Name“ (alphabetisch).
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Ihre Kategorien alphabetisch erscheinen, wählen Sie „Name“. Wenn Sie sie manuell im PrestaShop-Kategoriebereich sortieren möchten, wählen Sie „Position“.
- **Sortierrichtung:**

  - **Was diese Einstellung bewirkt:** Gibt aufsteigende oder absteigende Reihenfolge für die Einstellung „Sortieren nach“ an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *ASC:* Aufsteigend (A-Z, 1-9).
    - *DESC:* Absteigend (Z-A, 9-1).
  - **Empfohlener Wert:** „ASC“ für die meisten Fälle.
  - **Händlerszenario / Beispiel:** Wenn Sie nach „Name“ sortiert haben und A-Z wünschen, wählen Sie „ASC“.

#### **Verwaltung bestehender Blöcke**

Nach dem Erstellen von Blöcken sehen Sie eine Liste mit Optionen zum:

- **Bearbeiten:** Ändern Sie die Einstellungen eines vorhandenen Blocks.
- **Löschen:** Entfernen Sie einen Block aus Ihrem Shop.
- **Status umschalten (Aktivieren/Deaktivieren):** Schalten Sie einen Block schnell ein oder aus, ohne seine Konfiguration zu löschen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Blockname** | Beschreibend | Interner Bezeichner für den Block. |
| | **Blocktitel anzeigen** | Ja | Zeigt/verbirgt den Titel des Blocks für Kunden. |
| | **Blocktitel** | „Kategorien“ (Beispiel) | Der sichtbare Titel für den Block (mehrsprachig). |
| | **Hook zum Anzeigen des Blocks** | `displayLeftColumn` | Bestimmt, wo der Block in Ihrem Theme erscheint. |
| | **Stammkategorie** | Startseite | Legt den Startpunkt für Kategorien in diesem Block fest. |
| | **Maximale Tiefe** | 0 (Alle) | Begrenzt die Anzahl der angezeigten Unterkategorie-Ebenen. |
| | **Dynamisch (aktuellen Kategorienbaum öffnen)** | Ja | Erweitert den Baum automatisch zur aktuellen Kategorie. |
| | **Stammkategorie anzeigen** | Ja | Zeigt/verbirgt die ausgewählte Stammkategorie selbst. |
| | **Anzahl der Produkte anzeigen** | Nein | Zeigt/verbirgt Produktanzahlen neben Kategorienamen. |
| | **Kategorien ohne Produkte anzeigen** | Nein | Zeigt/verbirgt Kategorien, die keine Produkte haben. |
| | **Sortieren nach** | Position | Sortiert Kategorien nach Position oder Name. |
| | **Sortierrichtung** | ASC | Sortiert Kategorien in aufsteigender oder absteigender Reihenfolge. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein neuer Kategorieblock wird im Front Office nicht angezeigt.**
A1:

- **Hook überprüfen:** Stellen Sie sicher, dass Sie den richtigen „Hook zum Anzeigen des Blocks“ in der Modulkonfiguration ausgewählt haben.
- **Modulposition:** Gehen Sie zu **Design > Positionen** (oder **Module > Positionen** in älteren Versionen). Suchen Sie nach `Mehrere Kategorieblöcke` und stellen Sie sicher, dass es an die von Ihnen ausgewählte Position gehängt und nicht deaktiviert ist. Möglicherweise müssen Sie seine Position nach oben oder unten verschieben, wenn andere Module überlappen.
- **Modulstatus:** Stellen Sie in der Modulkonfiguration sicher, dass der Block „Aktiviert“ ist (grünes Häkchen).
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**).

**F2: Die Kategorien in meinem Block werden nicht erweitert oder nicht korrekt angezeigt.**
A2:

- **Stammkategorie & Max. Tiefe:** Überprüfen Sie Ihre Einstellungen für „Stammkategorie“ und „Maximale Tiefe“. Wenn die maximale Tiefe zu niedrig ist, werden Unterkategorien nicht angezeigt. Wenn die Stammkategorie falsch ist, sehen Sie den falschen Baum.
- **Dynamische Option:** Wenn Sie erwarten, dass der Baum beim Navigieren automatisch erweitert wird, stellen Sie sicher, dass „Dynamisch (aktuellen Kategorienbaum öffnen)“ auf „Ja“ eingestellt ist.
- **Kategorien ohne Produkte:** Wenn Kategorien fehlen, überprüfen Sie „Kategorien ohne Produkte anzeigen“. Wenn es „Nein“ ist, werden Kategorien ohne Produkte ausgeblendet.

**F3: Das Styling des Kategorieblocks passt nicht zu meinem Theme.**
A3:

- Das Modul versucht, Stile von Ihrem aktiven PrestaShop-Theme zu erben. Benutzerdefinierte Themes erfordern jedoch möglicherweise geringfügige CSS-Anpassungen.
- Sie können die Standard-CSS des Moduls oft überschreiben, indem Sie Regeln zu den `custom.css`- oder `theme.css`-Dateien Ihres Themes hinzufügen. (Siehe Abschnitt 7.5 für Entwicklerdetails zu Modul-CSS).
- Stellen Sie für PrestaShop 1.7/8/9 sicher, dass Sie die Datei `multicatblock-prestashop17.css` verwenden, falls Ihr Theme dies erfordert (dies wird vom Modul automatisch gehandhabt).

**F4: Wie übersetze ich den Blocktitel in andere Sprachen?**
A4:

- Beim Bearbeiten eines Blocks hat das Feld „Blocktitel“ Sprachflaggen daneben. Klicken Sie auf jede Flagge, um den Titel für die jeweilige Sprache einzugeben.
- Speichern Sie Ihre Änderungen, nachdem Sie alle Übersetzungen eingegeben haben.

**F5: Warum fehlen einige Kategorien im Block, obwohl sie Produkte haben?**
A5:

- **Umfang der Stammkategorie:** Stellen Sie sicher, dass die fehlenden Kategorien tatsächlich Nachkommen (Unterkategorien) der „Stammkategorie“ sind, die Sie für diesen spezifischen Block ausgewählt haben. Wenn sie außerhalb dieses Zweigs liegen, werden sie nicht angezeigt.
- **Kategorienstatus:** Überprüfen Sie unter **Katalog > Kategorien**, ob die fehlenden Kategorien „Aktiviert“ und „Angezeigt“ (sichtbar) sind.
- **Produktzuordnung:** Überprüfen Sie nochmals, ob Produkte den betreffenden Kategorien korrekt zugeordnet sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Mehrere Kategorieblöcke“ (`multicatblocks`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und Konfiguration nutzt. Es integriert sich über verschiedene Anzeige-Hooks in das Front-Office und verwendet Smarty-Templates für die Darstellung. Das Modul speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration`, wodurch mehrere, unterschiedliche Kategorieblöcke definiert werden können. Es verwendet eine benutzerdefinierte Baum-Rendering-Logik, um die Kategorienavigation zu erstellen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Konfigurations- und Front-Office-Rendering-Logik wird innerhalb der Hauptmoduldatei `index.php` und ihrer zugehörigen Templates und Hooks behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen. Die gesamte Datenmanipulation für Kategorien basiert auf PrestaShops nativer `Category`-Klasse.

Die Hauptlogik befindet sich in `multicatblocks/index.php`:

- **`Multicatblocks`-Klasse:** Erweitert `Module`.
  - **`__construct()`:** Initialisiert Moduldetails, richtet Tabs ein und registriert Hooks.
  - **`install()`:** Registriert notwendige Hooks (`displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`, `displayProductButtons` – letzterer könnte jedoch für Legacy/interne Nutzung sein, da er nicht in der Konfiguration exponiert ist), erstellt Standard-Konfigurationseinträge.
  - **`uninstall()`:** Bereinigt Konfigurationseinträge.
  - **`getContent()`:** Behandelt die Übermittlung und Anzeige des Back Office-Konfigurationsformulars. Es verwaltet die Erstellung, Bearbeitung und Löschung von Kategorieblöcken und speichert deren Einstellungen in `Configuration::updateValue()`.
  - **`hookDisplayHeader()`:** Fügt CSS- und JavaScript-Assets in den `<head>`-Bereich des Front Office ein.
  - **`hookDisplayLeftColumn()`, `hookDisplayRightColumn()`, `hookDisplayFooter()`, `hookDisplayHome()`, `hookDisplayProductButtons()`:** Diese Methoden sind verantwortlich für das Abrufen der konfigurierten Blöcke für ihre jeweiligen Hooks, das Abrufen von Kategoriedaten, das Vorbereiten von Smarty-Variablen und das Rendern des `multicatblock.tpl`- oder `multicatblock-footer.tpl`-Templates.
  - **`getCategoryTree()`:** Eine entscheidende interne Methode, die die Kategoriedaten rekursiv abruft und strukturiert, basierend auf der Konfiguration des Blocks (Stammkategorie, maximale Tiefe, Produktanzahl usw.).

### 4.4 JavaScript-Assets (`views/js/`)

- **`multicatblocks/js/script.js`**:

  - **Umfang:** Front-Office.
  - **Zweck:** Handhabt das interaktive Kernverhalten des Kategorienbaums, wie das Erweitern/Zusammenklappen von Unterkategorien. Es bindet wahrscheinlich Klickereignisse an Kategorielinks oder Erweiterungs-/Zusammenklapp-Symbole.
  - **Details:** Dieses Skript ist für das „dynamische“ Verhalten verantwortlich und stellt sicher, dass beim Klicken auf eine Kategorie deren Unterkategorien angezeigt oder ausgeblendet werden und möglicherweise der aktive Kategoriepfad hervorgehoben wird.
- **`multicatblocks/js/tree.js`**:

  - **Umfang:** Front-Office.
  - **Zweck:** Wahrscheinlich eine Abhängigkeit oder eine ältere Version der Baumfunktionalität, oder es handhabt speziell den Anfangszustand und das Rendering der Baumstruktur.
  - **Details:** Könnte Logik für die Initialisierung des Baums, die Handhabung von AJAX-Aufrufen für Kategoriedaten (falls zutreffend, obwohl das Modul den vollständigen Baum beim Laden der Seite zu rendern scheint) oder die Verwaltung des Baumzustands enthalten.
- **`multicatblocks/lib/searchTool/views/js/autocomplete.js`**:

  - **Umfang:** Back-Office (Admin-Konfiguration).
  - **Zweck:** Bietet eine Autocomplete-Funktionalität zur Auswahl von Kategorien im Konfigurationsformular des Moduls, speziell für die Einstellung „Stammkategorie“.
  - **Details:** Bindet an ein Eingabefeld, sendet AJAX-Anfragen an einen PrestaShop-Admin-Controller (wahrscheinlich `AdminCategories` oder einen benutzerdefinierten, falls vorhanden, obwohl keiner aufgeführt ist), um nach Kategorien zu suchen, und zeigt Vorschläge an.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`multicatblocks/css.css`**:

  - **Umfang:** Front-Office.
  - **Zweck:** Allgemeine Stilgebung für die Kategorieblöcke.
  - **Details:** Enthält grundlegende Regeln für Listenelemente, Links und potenziell Erweiterungs-/Zusammenklapp-Symbole. Wichtige Selektoren könnten `.multicatblock`, `.multicatblock_list`, `.multicatblock_item` sein.
- **`multicatblocks/lib/searchTool/views/css/autocomplete.css`**:

  - **Umfang:** Back-Office (Admin-Konfiguration).
  - **Zweck:** Stile für das Autocomplete-Suchfeld und dessen Vorschlags-Dropdown.
  - **Details:** Stellt sicher, dass das Kategoriesuchwerkzeug im Admin-Panel visuell konsistent und benutzerfreundlich ist.
- **`multicatblocks/multicatblock-prestashop17.css`**:

  - **Umfang:** Front-Office.
  - **Zweck:** Spezifische Überschreibungen oder zusätzliche Stile, die auf PrestaShop 1.7.x, 8.x und 9.x Themes (z.B. Classic Theme) zugeschnitten sind.
  - **Details:** Behebt potenzielle Layout- oder Stilinkonsistenzen, die zwischen älteren PrestaShop-Versionen und den neueren Theme-Strukturen auftreten können. Dies wird bedingt basierend auf der PS-Version geladen.
- **`multicatblocks/multicatblock.css`**:

  - **Umfang:** Front-Office.
  - **Zweck:** Kern-Styling für die Kategorieblöcke, wahrscheinlich für ältere PrestaShop-Versionen (1.5.x, 1.6.x) oder als Fallback.
  - **Details:** Ähnlich wie `css.css`, könnte aber spezifischere Regeln für ältere Theme-Strukturen enthalten.
- **`multicatblocks/views/css/mcb-admin.css`**:

  - **Umfang:** Back-Office (Admin-Konfiguration).
  - **Zweck:** Styling für die Konfigurationsseite des Moduls im PrestaShop Back Office.
  - **Details:** Stellt sicher, dass das Einstellungsformular des Moduls, die Liste der Blöcke und andere Admin-UI-Elemente gut präsentiert und mit dem PrestaShop-Admin-Theme konsistent sind.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/` - obwohl Dateien direkt in `multicatblocks/` liegen):**

  - **`multicatblocks/multicatblock.tpl`**:
    - **Eingehängt in:** `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayProductButtons`.
    - **Ausgabe:** Die Hauptstruktur des Kategorieblocks, einschließlich des Titels (falls aktiviert) und des rekursiven Kategorienbaums, der von `category-tree-branch.tpl` generiert wird.
  - **`multicatblocks/multicatblock-footer.tpl`**:
    - **Eingehängt in:** `displayFooter`.
    - **Ausgabe:** Eine Variante des Kategorieblocks speziell für den Footer, möglicherweise mit unterschiedlichen Styling- oder Strukturelementen. Es verwendet auch `category-tree-branch-footer.tpl`.
  - **`multicatblocks/category-tree-branch.tpl`**:
    - **Eingehängt in:** Eingeschlossen von `multicatblock.tpl`.
    - **Ausgabe:** Rendert rekursiv einen einzelnen Zweig des Kategorienbaums. Es iteriert durch Unterkategorien, handhabt Tiefenbegrenzungen und zeigt Produktanzahlen an.
  - **`multicatblocks/category-tree-branch-footer.tpl`**:
    - **Eingehängt in:** Eingeschlossen von `multicatblock-footer.tpl`.
    - **Ausgabe:** Ähnlich wie `category-tree-branch.tpl`, aber auf die Struktur des Footer-Blocks zugeschnitten.
- **Admin-Templates (`views/templates/admin/` - obwohl `shell.tpl` in `multicatblocks/views/templates/admin/` liegt):**

  - **`multicatblocks/views/templates/admin/shell.tpl`**:
    - **Zweck:** Das Haupttemplate für die Konfigurationsseite des Moduls im Back Office.
    - **Ausgabe:** Das Formular zum Hinzufügen/Bearbeiten von Blöcken, die Liste der vorhandenen Blöcke und möglicherweise andere admin-spezifische Elemente.
- **Bibliotheks-Templates:**

  - **`multicatblocks/lib/searchTool/views/scripts.tpl`**:
    - **Zweck:** Enthält wahrscheinlich JavaScript, das für das Autocomplete-Suchwerkzeug in der Admin-Konfiguration erforderlich ist.
    - **Ausgabe:** `<script>`-Tags oder Inline-JavaScript für die Autocomplete-Funktionalität.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Alle Konfigurationen für jeden Kategorieblock werden in der Tabelle `ps_configuration` gespeichert. Die Einstellungen jedes Blocks werden serialisiert und unter einem eindeutigen Konfigurationsschlüssel (z.B. `MULTICATBLOCKS_BLOCKS`) gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt CSS- und JavaScript-Dateien des Moduls ein. |
| `displayLeftColumn` | In der linken Seitenleiste des Front Office. | Rendert einen konfigurierten Kategorieblock in der linken Spalte. |
| `displayRightColumn` | In der rechten Seitenleiste des Front Office. | Rendert einen konfigurierten Kategorieblock in der rechten Spalte. |
| `displayFooter` | Im Footer-Bereich des Front Office. | Rendert einen konfigurierten Kategorieblock im Footer. |
| `displayHome` | Auf der Startseite (wenn das Theme den `displayHome`-Hook unterstützt). | Rendert einen konfigurierten Kategorieblock auf der Startseite. |
| `displayProductButtons` | Auf der Produktseite, nahe dem In-den-Warenkorb-Button. | Rendert einen konfigurierten Kategorieblock auf Produktseiten (weniger üblich für dieses Modul, aber verfügbar). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Mehrere Kategorieblöcke“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.
