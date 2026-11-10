---
title: Step by Step - Dokumentation und Benutzerhandbuch
sidebar:
  label: Step by Step - Dokumentation und Benutzerhandbuch
description: Anleitung zur Einrichtung und zur Fehlersuche für Shops, die den Kategoriefilter Step by Step bereits haben.
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Step by step - categories auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/step-by-step-categories/)
>
> ---


## 1. Anforderungen

Das Modul läuft in PrestaShop. Es braucht kein weiteres Modul und kein externes Konto.

- PrestaShop ab 1.6.0.0, einschließlich PrestaShop 8 und 9.
- PHP in der Version, die diese PrestaShop-Version verlangt. Die Update-Prüfung nutzt cURL, wenn PHP es hat, sonst einen normalen Abruf der Adresse. Für die Dropdowns installieren Sie keine extra PHP-Erweiterung.
- Kein anderes Modul ist nötig.
- Im Multishop kann ein Block zu einem Shop oder zu allen Shops gehören.

## 2. Installation

1. Öffnen Sie im Backoffice **Module**, dann **Modul-Manager**.
2. Laden Sie die Zip-Datei hoch und klicken Sie auf **Installieren**.
3. Öffnen Sie **Konfigurieren** bei **Step By Step - categories tree**. Die Seite hat **Blocks**, **Settings** und **Updates**. **Blocks** ist die Liste der Dropdown-Sätze. Der erste Besuch legt die versteckte Seite dieser Liste an. Sie erscheint nicht als eigener Punkt im linken Menü.
4. Die Installation leert den Cache nicht in einem eigenen Schritt. Wenn der Shop nach einem Update noch das alte Layout zeigt, leeren Sie den Cache unter **Erweiterte Parameter**, **Leistung**.

Die Deinstallation entfernt diese versteckte Seite. Blöcke, Titel, Beschriftungen und die beiden globalen Schalter bleiben in der Datenbank. Nach einer erneuten Installation sind dieselben Blöcke da. Öffnen Sie einmal **Konfigurieren**, damit die Listenseite wieder eingetragen wird.

Außer dem normalen Modulschalter im **Modul-Manager** gibt es keine eigene Aktion zum Aktivieren. Wenn Sie das Modul ausschalten, verschwinden die Dropdowns im Shop und die gespeicherten Blöcke bleiben.

## 3. Konfiguration und Arbeit im Backoffice

Sie legen einen Block an, stellen die Tiefe des Kategoriebaums ein und wählen den Platz im Shop. Der Kunde wählt eine Kategorie. Die nächste Liste lädt ihre Kinder. **ok** öffnet die gewählte Kategorie oder ein Produkt, wenn die Produktliste an ist.

Die Bilder in diesem Kapitel zeigen das englische Backoffice. Die Beschriftungen auf dem Bildschirm bleiben Englisch.

### 3.1 Konfigurationsseite des Moduls

Öffnen Sie **Module**, **Modul-Manager**, **Step By Step - categories tree**, **Konfigurieren**.

![Einstellungen](https://mypresta.eu/docs/images/docs/stepbystep-configure-settings.webp)

Oben stehen **Blocks**, **Settings** und **Updates**. **Blocks** verlässt diese Seite und öffnet die Blockliste. **Settings** ist der Startreiter. Unter der Leiste steht, dass diese Optionen für jeden Block gelten und dass Sie Blöcke unter **Blocks** bearbeiten.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Reset search fields** | No | Yes leert die Listen nach einer Suche. No behält die Kategorien, die der Besucher gewählt hat. Der Browser speichert diese Wahl 30 Minuten. |
| **Include Select2 library** | No | Yes lädt das zusätzliche Skript und Stylesheet für **Search inside dropdown** an einem Block. No lässt normale Listen. |

Klicken Sie auf **Save**. Die Seite zeigt **Settings saved.**

![Updates](https://mypresta.eu/docs/images/docs/stepbystep-configure-updates.webp)

**Updates** ist das Formular **MyPresta updates**.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Manual check** | Schaltfläche **Check now** | Fragt MyPresta, ob eine neuere Version existiert. **New version available!** führt zum Änderungsprotokoll. **Module is up to date!** bedeutet, dass diese Installation zur veröffentlichten Version passt. Die Schaltfläche lädt keine Zip-Datei hoch. |
| **Automatic notifications** | Enabled | Enabled wiederholt diese Prüfung etwa alle 3 Tage, während Sie im Backoffice arbeiten. Disabled überspringt sie. |
| **Product page** | Link zur Modulseite | Öffnet die Step-by-Step-Seite auf mypresta.eu. |

**Save** zeigt **Update settings saved.** Laden Sie eine neue Zip-Datei im **Modul-Manager** hoch, wenn eine neuere Version erscheint.

### 3.2 Blockliste

Öffnen Sie **Blocks**. Unter der Leiste steht, dass jeder Block ein Satz von Dropdowns ist.

![Blockliste](https://mypresta.eu/docs/images/docs/stepbystep-blocks-list.webp)

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **ID** | wird beim Speichern vergeben | Nummer des Blocks. Sie dient nur dazu, Zeilen zu unterscheiden. |
| **Title** | Block und die Nummer, bis Sie einen Titel eintragen | Überschrift in der Sprache des Backoffice. |
| **Depth** | 3 bei einem neuen Block | Wie viele Dropdowns der Block zeichnet. |
| **Root category** | Home-Kategorie des Shops bei einem neuen Block | Elternteil der ersten Liste, als Nummer und Name. |
| **Hook** | Top bei einem neuen Block | Platz des Blocks im Shop. |
| **Active** | Yes | Das Symbol schaltet den Block an oder aus. Aus blendet die Dropdowns aus und lässt die Zeile stehen. |
| **Position** | nächste freie Position | Ziehen Sie die Zeile, um die Reihenfolge der Blöcke am selben Hook zu ändern. |

Zeilenaktionen sind **Edit** und **Delete**. **Bulk actions** hat **Enable selection**, **Disable selection** und **Delete selected**. Die Löschfrage lautet **Delete selected blocks?**

**Add new** öffnet ein leeres Formular. Ein neuer Block ist aktiv, Tiefe 3, Wurzel ist die Home-Kategorie, Sortierung nach ID aufsteigend, Produktzähler aus, Schaltfläche nach der letzten Liste, Produkte aus, Auto-Submit aus, Suche in der Liste aus, Beschriftung in der Liste, Hook Top und der aktuelle Shop. Speichern Sie ihn. Das Formular öffnet sich wieder, damit Sie die Beschriftungen füllen. Die Beschriftungen stehen erst im Formular, wenn der Block existiert.

Die Liste zeigt Blöcke des Shops, in dem Sie sind, und Blöcke mit **All shops**.

### 3.3 Blockformular

Öffnen Sie eine Zeile mit **Edit**, oder nutzen Sie **Add new** und danach den Bearbeitungsbildschirm nach dem ersten Speichern.

![Blockformular, oben](https://mypresta.eu/docs/images/docs/stepbystep-block-form.webp)

![Blockformular, Beschriftungen und Position](https://mypresta.eu/docs/images/docs/stepbystep-block-form-bottom.webp)

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Block title** | leer | Überschrift über den Dropdowns. Ein Feld je Shop-Sprache. |
| **Depth** | 3 | Wie viele Dropdowns der Block zeichnet. Speichern Sie den Block und öffnen Sie ihn erneut, um je Stufe eine Beschriftung zu füllen. Das Formular zeigt höchstens 30 Beschriftungsfelder. |
| **Root category** | Home-Kategorie | Die erste Liste zeigt die Kinder dieser Kategorie. |
| **Sort method** | By ID | By ID, By name oder By position. Position ist die Reihenfolge der Kategorie im Katalog. |
| **Sort direction** | Ascending | Ascending oder Descending. |
| **Products counter** | No | Yes schreibt die Produktzahl in Klammern hinter den Kategorienamen. |
| **Submit button** | After last select box | After each select box zeigt **ok** bei der Stufe, auf der der Kunde ist. After last select box zeigt ein **ok** für den ganzen Satz. |
| **Include products** | No | Yes zeigt eine Produktliste aus der zuletzt gewählten Kategorie. |
| **Auto submit** | No | Yes sendet das Formular, sobald die letzte verfügbare Kategorie gewählt ist. Der Shop öffnet diese Kategorie. Das gilt, wenn **Include products** aus ist. Hat die gewählte Kategorie keine Kinder, öffnet der Shop sie ebenfalls. |
| **Search inside dropdown** | No | Yes schaltet die Suche in den Listen ein. In **Settings** muss **Include Select2 library** ebenfalls an sein. |
| **Exclude categories** | leer | Kategorie-IDs, die nicht in den Dropdowns erscheinen sollen. Trennen Sie sie mit Kommas, zum Beispiel 1,2,3,4,5,6. Die Suche neben dem Feld findet eine Kategorie und hängt ihre ID an. |
| **Show on category pages** | leer | Leer zeigt den Block auf jeder Seite, auf der sein Hook liegt. Kategorie-IDs, mit Kommas getrennt, zeigen ihn nur auf diesen Kategorieseiten. |
| **Label position** | Inside select box | Inside select box setzt die Beschriftung als erste Option. Outside select box druckt sie über dem Feld. |
| **Label 1**, **Label 2** und weiter | leer | Ein Feld je Stufe und Sprache. Sie erscheinen erst nach dem Speichern des Blocks. Ändern Sie **Depth** und speichern Sie, wenn Sie mehr oder weniger brauchen. |
| **Module position** | Top | Top, displaySearch, TopColumn, Left column, Right column, Home oder displaySbs. |
| **Position top settings** | Blocks | Blocks stapelt die Dropdowns. Wide horizontal bar legt sie in eine Reihe. Die breite Leiste gilt auf Top und displaySearch. Die anderen Plätze bleiben gestapelt. Auf der breiten Leiste steht **ok** hinter dem letzten Dropdown und rutscht in die nächste Zeile, wenn kein Platz ist. |
| **Shop** | der Shop, den Sie bearbeiten | Ein Shop oder **All shops**. **All shops** lässt den Block in jedem Shop. |
| **Active** | Yes | No blendet den Block im Shop aus. |

Klicken Sie auf **Save**. PrestaShop zeigt seine übliche Bestätigung. Das Löschen eines Blocks löscht auch Titel, die Wahl der breiten Leiste und die Stufenbeschriftungen.

Um einen Block in einer Theme-Datei ohne fertigen Hook zu zeigen, setzen Sie den Hook displaySbs ein und stellen Sie **Module position** auf displaySbs. Die anderen Positionen hängen Sie unter **Design**, **Positionen** ein, wenn das Theme sie nicht selbst ausgibt.

## 4. Shop

Der Kunde sieht den Blocktitel und die Dropdowns.

1. Die erste Liste zeigt die Kinder der Wurzelkategorie. Spätere Listen bleiben inaktiv, bis die vorherige Stufe eine Kategorie hat.
2. Der Kunde wählt eine Kategorie. Ein Spinner liegt über dem Block. Die nächste Liste füllt sich mit den Kindern. Der Spinner verschwindet, wenn die Liste fertig ist, und auch wenn die Anfrage scheitert.
3. Ausgeschlossene Kategorie-IDs fehlen in diesen Listen.
4. Bei **Submit button** auf after each select box steht **ok** bei der aktuellen Stufe. Bei after last select box gibt es ein **ok** für den Satz.
5. **ok** öffnet die gewählte Kategorie.
6. Mit **Include products** kommt auf der letzten Stufe eine Produktliste dazu. Die erste Option ist **- Select Product -**. **ok** nutzt dann das gewählte Produkt.
7. Mit **Auto submit** an und **Include products** aus öffnet die letzte Kategorie sich ohne **ok**. Dieselbe Weiterleitung gilt, wenn die gewählte Kategorie keine Kinder hat.
8. Mit **Reset search fields** aus kann ein späterer Besuch dieselben Kategorien zeigen. Der Browser hält sie 30 Minuten. Mit der Option an starten die Listen leer.
9. Wenn **Search inside dropdown** und **Include Select2 library** an sind, kann der Kunde in der Liste tippen.

In der linken und rechten Spalte stehen die Stufen untereinander, der Titel in Großbuchstaben wie bei Classic. Auf der breiten Leiste stehen die Stufen in einer Reihe. Auf einem schmalen Bildschirm stapelt sich die breite Leiste. Farben, Rahmen und die Schaltfläche **ok** kommen aus dem Theme, auch Hummingbird und Classic unter PrestaShop 9.

Ein Block mit gefülltem **Show on category pages** fehlt auf anderen Seiten. Ein inaktiver Block fehlt. Ein Block eines anderen Shops fehlt ebenfalls.

## 5. Probleme

**Der Block fehlt im Shop.** Öffnen Sie den Block und prüfen Sie **Active**, **Module position** und **Shop**. Leeres **Show on category pages** zeigt ihn auf jeder Seite dieses Hooks. Eine gefüllte Liste zeigt ihn nur auf diesen Kategorieseiten. Unter **Design**, **Positionen** prüfen Sie, ob der Hook auf den erwarteten Seiten liegt. Für einen eigenen Platz muss das Template displaySbs aufrufen, und der Block muss diese Position nutzen.

**Die nächste Liste füllt sich nicht, oder der Spinner bleibt.** Leeren Sie den Shop-Cache, damit der Shop das aktuelle Stylesheet und Skript nimmt. Der Spinner soll verschwinden, wenn die Anfrage endet, auch wenn die Antwort nicht angewendet werden kann. Wenn der Shop noch den alten Gif-Lader zeigt, liegt das vorherige CSS im Cache.

**Die Suche in der Liste tut nichts.** Schalten Sie **Include Select2 library** in **Settings** und **Search inside dropdown** am Block ein. Speichern Sie beides. Leeren Sie den Cache.

**Bei einem neuen Block fehlen die Beschriftungen.** Speichern Sie den Block einmal. Öffnen Sie ihn erneut. **Label 1** und der Rest erscheinen erst, wenn der Block existiert, und nur bis zum gespeicherten **Depth**.

**Eine gewünschte Kategorie fehlt in der Liste.** Entfernen Sie ihre ID aus **Exclude categories**. Prüfen Sie, ob sie ein Kind des gewählten Elternteils ist und im Katalog aktiv ist.

**Die breite Leiste stapelt die Felder weiter.** **Wide horizontal bar** gilt auf Top und displaySearch. Links, rechts, Startseite, TopColumn und displaySbs bleiben gestapelt. Auf dem Telefon stapelt sich die breite Leiste absichtlich.

**Nach einem Update fehlt die Seite Blocks.** Öffnen Sie einmal **Konfigurieren**. Dieser Besuch trägt die Seite ein. Deinstallieren Sie das Modul nicht, wenn Sie die vorhandenen Zeilen weiter nutzen wollen. Die Deinstallation entfernt die Seite und lässt die Zeilen stehen.

**Der alte Konfigurationsbildschirm hat kein Papierkorb-Symbol.** Das ist eine ältere Version. Laden Sie die aktuelle Zip-Datei aus dem Kundenkonto hoch. In der aktuellen Version löschen Sie einen Block in der Liste **Blocks**, mit **Delete** in der Zeile oder mit **Delete selected**.

## 6. Für Entwickler

### 6.1 Überblick

Technischer Name `stepbystep`, Klasse `Stepbystep`, Version 1.9.0, Autor MyPresta.eu, Tab `front_office_features`. Der Name im Backoffice ist **Step By Step - categories tree**.

`AdminStepbystepBlocksController` schreibt Zeilen in `sbs_block` und Titel, Beschriftungen und die Flagge der breiten Leiste in `Configuration`. Shop-Hooks lesen aktive Zeilen des aktuellen Shops oder mit `id_shop = 0`. `controllers/front/tree.php` liefert das Skript, das die nächste Liste füllt.

### 6.2 Dateien

| Datei | Rolle |
|---|---|
| `stepbystep.php` | Installation, Hooks, Einstellungsformular, Dropdown-HTML, Shop-Skript. |
| `controllers/admin/AdminStepbystepBlocksController.php` | Blockliste und Blockformular. |
| `models/SbsBlock.php` | Objektmodell für `sbs_block`. |
| `controllers/front/tree.php` | Front-Controller, der das Skript der nächsten Stufe liefert. |
| `views/templates/hook/front.tpl` | Shop-Markup für jeden Hook. |
| `views/templates/hook/header.tpl` | Gibt das Inline-Skript aus. |
| `views/templates/admin/configure.tpl` | Leiste Blocks, Settings, Updates. |
| `css/sbs-front.css` | Shop-Layout, Theme-Variablen, Spinner. |
| `js/advajax.js` | Anfrage der Dropdowns. |
| `lib/updatesChecker.php` | Update-Prüfung. Klasse `stepbystepUpdate`. |
| `lib/searchTool/searchTool.php` | Suche der Kategorie-ID im Blockformular. Klasse `searchToolstepbystep`. |
| `lib/prestashop9compatibility.php` | Klasse `stepbystepPrestashopNewCompatibility`. |
| `views/css/admin.css` | Leiste im Backoffice. |

`tree.php` im Modulstamm ist die ältere Kopie des Front-Controllers. Der Shop-Link nutzt `controllers/front/tree.php`. `views/templates/hook/block.tpl`, `blockSbs.tpl`, `top.tpl` und `displaySearch.tpl` werden nicht gerendert. `css/sbs-block.css` und `css/sbs-top.css` werden nicht eingebunden.

### 6.3 Controller

`AdminStepbystepBlocksController` erweitert `ModuleAdminController`. `class_name` ist `AdminStepbystepBlocks`. `id_parent` ist `-1`, die Seite ist im Menü versteckt. Der Listenbezeichner ist `id`. Das Ziehen der Position ruft `ajaxProcessUpdatePositions` auf. Der Listenfilter ist `id_shop` des Kontext-Shops oder `0`.

`stepbysteptreeModuleFrontController` ist der Front-Controller `tree`. `initContent` setzt `ajax` und ruft `parent::initContent` nicht auf. Er liest `sbs_block`, `sbs_pid`, `sbs_lvl`, und beim Bestätigen `sbs_blockid` und `sbs_cidlink`. Der Antwortkörper ist JavaScript. Ein fehlender Block beendet die Antwort.

### 6.4 Hooks

Eingetragene Hooks: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayTop`, `displaySearch`, `displayHome`, `displaySbs`, `displayBackOfficeHeader`. Ab PrestaShop 1.6 auch `displaytopColumn`.

| Hook | Wert der Blockposition | Layout |
|---|---|---|
| `displayTop` | 1 | oben, breite Leiste wenn `sbs_top_type{id}` 1 ist |
| `displayLeftColumn` | 2 | gestapelt |
| `displayRightColumn` | 3 | gestapelt |
| `displayHome` | 4 | gestapelt |
| `displaytopColumn` | 5 | gestapelt |
| `displaySearch` | 6 | oben, breite Leiste wenn `sbs_top_type{id}` 1 ist |
| `displaySbs` | 7 | gestapelt |

`displayHeader` lädt `js/advajax.js` und `css/sbs-front.css`. Wenn `SBS_SELECT2` 1 ist, lädt es auch Select2. Es gibt kein Überschreiben von `enable()` oder `disable()`.

### 6.5 Overrides

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `ps_sbs_block` | `id`, `depth`, `root`, `orderby`, `orderway`, `counter`, `each_submit`, `lbl_position`, `block_position`, `position`, `active`, `products`, `last_submit`, `search_inside`, `exclude`, `id_shop`, `on_cat_only`, `id_categories`. |

Das Präfix folgt dem Shop. Die Deinstallation löscht die Tabelle nicht. `inconsistency()` ergänzt eine fehlende Spalte aus dieser Liste, wenn die Modulkonfiguration oder die Blockliste geöffnet wird. `on_cat_only` bleibt und steht nicht im Formular. Der Shop nutzt `id_categories`.

### 6.7 Konfigurationsschlüssel und Übersetzungen

| Schlüssel | Wenn er fehlt |
|---|---|
| `SBS_RESET` | Gilt als 0. Die Wahl bleibt 30 Minuten in Cookies `sbs_selectbox_{block}_{level}`. |
| `SBS_SELECT2` | Gilt als 0. Select2 wird nicht geladen. |
| `sbs_title{id}` | Mehrsprachiger Blocktitel. |
| `{id}sbs_lbl_{n}` | Mehrsprachige Beschriftung der Stufe `n`, von 1 bis zur Tiefe, höchstens 30. |
| `sbs_top_type{id}` | 0 gestapelt, 1 breite Leiste. |

Die Installation schreibt auch `sbs_depth`, `sbs_counter`, `sbs_each_submit`, `sbs_position`, `sbs_lbl_position` und `sbs_root`. Das Blockformular liest diese Schlüssel nicht. Neue Blöcke nutzen die Vorgaben in `prepareObjectDefaults()`.

Übersetzungen liegen in `translations/{iso}.php`. Texte des Block-Controllers haben die Quelle `AdminStepbystepBlocksController`. Der Schaltflächentext ist der Modultext `ok`. Der Produkt-Platzhalter ist `- Select Product -`.

### 6.8 Erweitern

Überschreiben Sie `views/templates/hook/front.tpl` im Theme als `themes/{theme}/modules/stepbystep/views/templates/hook/front.tpl`. Überschreiben Sie `css/sbs-front.css` auf demselben Weg, wenn das Theme das Layout ersetzen soll. Die Position der Schaltfläche auf der breiten Leiste ist die Flex-Reihenfolge in diesem Stylesheet: das sichtbare `.sbs__actions` steht hinter den Dropdowns und bricht mit der Zeile um.

## 7. Hilfe

Modulseite: [Step by Step categories](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html).

Um zu diesem Modul zu schreiben, melden Sie sich im Kundenkonto auf [mypresta.eu](https://mypresta.eu) an, öffnen Sie das Kontaktformular und wählen Sie **Support for paid modules**. Bei diesem Thema steht, dass eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.
