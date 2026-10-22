---
title: "Eigenschaften der Kombination - Händlerhandbuch"
description: "Konfigurations- und Fehlerbehebungsanleitung für Mitarbeiter, bei denen das Modul bereits installiert ist."
sidebar:
  label: "Eigenschaften der Kombination - Händlerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product combination features auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-combination-features/)
>
> ---


Technischer Name: `combfeat`. Version **1.4.0**. Im Backoffice heißt das Modul **Eigenschaften der Kombination**.

## 1. Anforderungen und Kompatibilität

- **PrestaShop:** 1.7.0.0 bis 9.x (`ps_versions_compliancy` bis 9.99.99).
- **PHP:** die von dieser PrestaShop-Version verlangte Version.
- **Produktseite:** Das Theme muss die gewählte Kombination im Attribut `data-product` von `#product-details` ausgeben (Standard in PrestaShop) und beim Attributwechsel das Ereignis `updatedProduct` auslösen. Classic und darauf aufgebaute Themes tun das.
- **PrestaShop 8 und 9, Registerkarte Module am Produkt:** Die Datei `src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig` muss beim Installieren oder beim ersten Öffnen der Konfiguration beschreibbar sein. Siehe Abschnitt 3.
- **Facettensuche (optional):** `ps_facetedsearch` installiert, Recht zum Anlegen einer SQL-View und Schreibrecht auf `modules/ps_facetedsearch/src/Adapter/MySQL.php`.
- **Update-Prüfung (optional):** `allow_url_fopen`, damit das Modul `https://dev.mypresta.eu` aufrufen kann.

## 2. Wo Sie im Backoffice arbeiten

| Ort | Pfad | Zweck |
| --- | --- | --- |
| Modulkonfiguration | **Module > Modul-Manager**, Suche nach **Eigenschaften der Kombination**, **Konfigurieren** | Schalter, CSS-Selektoren, Titelmodus, Facettensuche, CSV-Import, Update-Prüfung |
| Inhalt der Kombination | **Katalog > Produkte**, Produkt bearbeiten, Registerkarte **Module**, Block **Inhalt der Kombination** | Eigenschaften, Beschreibung und Titel jeder Kombination |
| Eigenschaftskatalog | **Katalog > Attribute & Eigenschaften** (Bezeichnung je nach PrestaShop-Version) | Eigenschaften und Werte anlegen, bevor Sie sie am Produkt zuweisen. Der CSV-Import kann fehlende anlegen |
| Vorlage der Facettensuche | Konfiguration des Moduls Facettensuche | Die Eigenschaft in die Filtervorlage aufnehmen. Dieses Modul tut das nicht von selbst |

Das Modul hat keinen eigenen Menüpunkt und keinen eigenen Front- oder Backoffice-Controller.

## 3. Dateien, die das Modul ändert

### 3.1 Registerkarte Module am Produkt in PrestaShop 8 und 9

Bei der Installation und bei jedem Öffnen der Konfigurationsseite bearbeitet das Modul:

`src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig`

Es ersetzt `{{ module.content|raw_purified }}` durch `{{ module.content|raw }}`. Beim ersten Mal kopiert es die Originaldatei nach `modules-content.html.twig.raw.bak` daneben.

PrestaShop 8 und 9 bereinigen sonst HTML, das Module auf der Produktseite ausgeben. Ohne diese Änderung ist der Editor **Inhalt der Kombination** leer oder seine Felder werden mit dem Produkt nicht gespeichert. In PrestaShop 1.7 gibt es diese Twig-Datei nicht. Das Modul überspringt die Änderung.

Kann die Datei nicht gelesen oder geschrieben werden, zeigt das Modul keinen Fehler. Prüfen Sie die Dateirechte, wenn die Registerkarte Module leer bleibt.

### 3.2 Adapter der Facettensuche

Wenn **Filter combination features in Faceted Search** aktiv ist (Standard), legt das Modul die SQL-View `{prefix}combfeat_feature_product` an und richtet `modules/ps_facetedsearch/src/Adapter/MySQL.php` auf diese View. Die View ist die Eigenschaftenliste des Produkts plus aktive Kombinations-Eigenschaften.

Ausschalten der Option, Deaktivieren des Moduls oder Deinstallieren schreibt die ursprüngliche Adapterquelle zurück. Die Deinstallation löscht die View auch, wenn der Adapter nicht mehr darauf verweist.

Die Konfigurationsseite zeigt eine Warnung, wenn die View nicht angelegt werden kann, die Adapterdatei fehlt, nicht lesbar, nicht beschreibbar ist oder nicht zur erwarteten Faceted-Search-Quelle passt. Die Meldungen (im Modul auf Englisch):

- Could not create the Faceted Search feature view. Combination features will not appear in category filters.
- Faceted Search is installed, but its database adapter was not found. Combination features will not appear in category filters.
- Faceted Search adapter could not be read. Combination features will not appear in category filters.
- This Faceted Search version does not use the expected feature table. Combination features will not appear in category filters.
- Faceted Search adapter is not writable. Make modules/ps_facetedsearch/src/Adapter/MySQL.php writable so combination features can be filtered.
- Faceted Search adapter could not be updated. Combination features will not appear in category filters.

## 4. Modulkonfiguration

Öffnen Sie **Konfigurieren**. Auf der Seite stehen zwei Formulare, darunter das Panel **MyPresta-Updates**. **Speichern** im Einstellungsformular sendet `submitCombfeatSettings`. **Import** sendet `submitCombfeatImport`.

![Einstellungsformular auf der Modulkonfiguration](https://mypresta.eu/docs/images/docs/configure-settings.webp)

Die Abbildung zeigt das englische Backoffice. Die Beschriftungen auf dem Bild sind die englischen Quelltexte. Die deutschen Namen stehen in dieser Anleitung.

### 4.1 Eigenschaften für Kombinationen aktivieren

Schlüssel: `combfeat_p_feat`. Standard: **Aktiviert**.

Wenn aktiv, hat jede Kombination auf der Registerkarte **Module** des Produkts eine Registerkarte **Eigenschaften**. Dort hängen Sie vorhandene Eigenschaftswerte an.

Wenn inaktiv, ist diese Registerkarte ausgeblendet. Das Storefront-Skript ist ein eigener Punkt: Eigenschaften und Beschreibungen aktualisiert dasselbe Skript, beschrieben in Abschnitt 6.

**Speichern eines Produkts bei ausgeschaltetem Schalter löscht die Kombinations-Eigenschaften dieses Produkts.** Das Produktformular enthält die Eigenschaftsfelder nicht mehr. Ein Speichern leert die Eigenschaftszeilen des Moduls für das Produkt und schreibt nur das zurück, was das Formular gesendet hat. Beschreibungen und Titel bleiben. Schalten Sie die Option wieder ein, bevor Sie das Produkt bearbeiten, wenn diese Eigenschaften bleiben sollen.

### 4.2 Datenblatt-CSS-Klasse

Schlüssel: `combfeat_ds`. Standard: `.data-sheet`.

Ein jQuery-Selektor. Das Modul ersetzt das **innere HTML** des getroffenen Elements durch Paare:

```html
<dt class="name">Eigenschaft</dt><dd class="value">Wert</dd>
```

Zeigen Sie auf das `<dl>`, das die Zeilen bereits enthält. Im Theme Classic ist das `dl.data-sheet`, der Standardwert passt also. Ein größerer Block wie `.product-features` oder `#product-details` wird vollständig durch die `<dt>` / `<dd>`-Paare ersetzt.

Trifft der Selektor nichts und hat die gewählte Kombination Eigenschaften, ersetzt das Modul den gesamten Inhalt von `#product-details` durch einen neuen Datenblatt-Abschnitt. Referenz, Marke und alles andere in `#product-details` entfallen. Setzen Sie den Selektor so, dass dieser Fallback nicht läuft.

### 4.3 Arbeitsablauf

Schlüssel: `combfeat_workflow`. Standard: **Bestehende Produkteigenschaften ersetzen** (Wert `0`).

| Option | Wert | Datenblatt nach Auswahl einer Kombination |
| --- | --- | --- |
| **Bestehende Produkteigenschaften ersetzen** | `0` | Kombinations-Eigenschaften ersetzen das Datenblatt. Hat die Kombination keine, werden die Produkteigenschaften zurückgeschrieben. |
| **Zur bestehenden Liste der Produkteigenschaften hinzufügen** | `1` | Produkteigenschaften bleiben vorn. Kombinations-Eigenschaften folgen dahinter. Hat die Kombination keine, sind nur die Produkteigenschaften zu sehen. |

Derselbe Eigenschaftswert auf Produkt und Kombination erscheint im Modus **Hinzufügen** zweimal. Das Modul entfernt keine Duplikate.

Mehrere Werte einer Eigenschaft sind erlaubt. Jeder Wert ist eine eigene Zeile. Die Reihenfolge folgt der Position der Eigenschaft im Katalog.

**Der Arbeitsablauf ändert nur das Datenblatt.** Die Beschreibung wird in beiden Modi ersetzt. Siehe Abschnitt 6.4.

Das Storefront-Skript hängt von dieser Einstellung ab: `views/js/combfeat.js` für Ersetzen, `views/js/combfeat-append.js` für Hinzufügen.

### 4.4 Filter combination features in Faceted Search

Schlüssel: `combfeat_faceted`. Standard: **Enabled**.

Die Beschriftung auf dem Bildschirm ist Englisch: **Filter combination features in Faceted Search**. Dieser Text steht noch nicht in den Übersetzungsdateien des Moduls. Der Hilfetext darunter ist ebenfalls Englisch: Eigenschaftswerte, die nur auf Kombinationen existieren, erscheinen in `ps_facetedsearch`; gezählt wird ein Produkt, wenn der Wert am Produkt oder an irgendeiner Kombination hängt. Die Eigenschaft muss in die Faceted-Search-Vorlage aufgenommen werden. Die Eigenschaftenliste des Produkts ändert sich nicht.

Wenn `ps_facetedsearch` installiert und der Schalter an ist:

- In den Kategoriefiltern können Werte erscheinen, die nur auf Kombinationen existieren.
- Ein Produkt wird gezählt, wenn der Wert am Produkt **oder an irgendeiner seiner Kombinationen** hängt. Der Filter hängt nicht davon ab, welche Kombination der Besucher später wählt. Ein Produkt zählt einmal, auch wenn mehrere Kombinationen den Wert tragen.
- Die Eigenschaft nehmen Sie weiterhin in die Vorlage der Facettensuche auf. Das Modul bearbeitet keine Vorlagen.
- Die Eigenschaftenliste auf der Produktseite im Katalog bleibt unverändert.

Nach dem Speichern von Kombinations-Eigenschaften oder nach einem CSV-Import leert das Modul den Block-Cache der Facettensuche (`layered_filter_block`), damit die Filter neu entstehen.

### 4.5 Beschreibungen für Kombinationen aktivieren

Schlüssel: `combfeat_p_desc`. Standard: **Aktiviert**.

Im englischen Quelltext lautet die Beschriftung **Turn on descriptionsfor combinations** (kein Leerzeichen vor „for“). Die deutsche Übersetzung ist **Beschreibungen für Kombinationen aktivieren**.

Wenn aktiv, hat jede Kombination eine Registerkarte **Beschreibung** mit einem Rich-Text-Feld je Shop-Sprache.

Wenn inaktiv, ist die Registerkarte ausgeblendet und ein Speichern des Produkts ändert gespeicherte Beschreibungen nicht. Sind Eigenschaften noch aktiv, läuft das Storefront-Skript weiter und wendet eine früher gespeicherte Beschreibung an. Leeren Sie die Beschreibungsfelder, speichern Sie, und schalten Sie erst dann aus, wenn die Storefront sie nicht mehr verwenden soll.

### 4.6 Beschreibung der CSS-Klasse / Objekt-ID

Schlüssel: `combfeat_description`. Standard: `#description`.

Ein jQuery-Selektor für den Block, dessen HTML die Kombinationsbeschreibung ersetzt. Im Theme Classic ist `#description` der Tab der langen Beschreibung, der Standard trifft also diesen Block.

Trifft der Selektor nichts, bleibt die Beschreibung auf der Seite unverändert.

Der Text, wenn eine Kombination keine Beschreibung hat, ist die **lange Beschreibung** des Produkts (`description`) in der aktuellen Sprache. Das ist nicht die Kurzbeschreibung und nicht die Meta-Beschreibung. Zeigt der Selektor auf den Kurzbeschreibungsblock, füllt eine Kombination ohne eigenen Text diesen Block mit der langen Beschreibung.

### 4.7 Meta-Titel für Kombinationen aktivieren

Schlüssel: `combfeat_p_title`. Standard: **Aktiviert**.

Wenn aktiv, lädt die Produktseite `views/js/combfeat-title.js`. Die Wahl einer Kombination aktualisiert `document.title` und, falls vorhanden, `<meta property="og:title">`.

Der Titel im vom Server gesendeten HTML bleibt der Meta-Titel des Produkts. Besucher sehen den Kombinationstitel, nachdem JavaScript gelaufen ist. Ein Crawler ohne JavaScript behält den Produkttitel.

Wenn inaktiv, ist die Registerkarte **Meta-Titel** ausgeblendet, das Skript wird nicht geladen, und ein Speichern ändert gespeicherte Titel nicht.

### 4.8 Standard-Titelmodus

Schlüssel: `combfeat_title_default`. Standard: **Attributnamen und -wert hinzufügen (kommagetrennt)** (Wert `1`).

Wird nur verwendet, wenn diese Kombination in der aktuellen Sprache keinen **Vollständigen Titel** und kein **Zum Titel hinzufügen** hat.

Der Ausgangstitel ist der Browsertitel, der beim ersten Laden der Seite gemerkt wird. Spätere Wechsel merken ihn nicht erneut, angehängte Teile stapeln sich also nicht.

| Option | Wert | Ergebnis |
| --- | --- | --- |
| **Titel standardmäßig nicht ändern** | `0` | Der ursprüngliche Dokumenttitel bleibt. |
| **Attributnamen und -wert hinzufügen (kommagetrennt)** | `1` | Ursprünglicher Titel, dann das Trennzeichen, dann Gruppen und Werte wie `Farbe: Rot, Größe: M`. |
| **Nur Attributwerte hinzufügen (kommagetrennt)** | `2` | Ursprünglicher Titel, dann das Trennzeichen, dann nur Werte wie `Rot, M`. |

Gruppennamen und Werte stammen aus der aktuellen Shop-Sprache.

### 4.9 Titel-Trennzeichen

Schlüssel: `combfeat_title_separator`. Standard: ` - ` (Leerzeichen, Bindestrich, Leerzeichen).

Steht zwischen dem ursprünglichen Dokumenttitel und dem hinzugefügten Teil. Der hinzugefügte Teil ist entweder der Text des Standardmodus oder **Zum Titel hinzufügen** der Kombination. Das Trennzeichen wird so verwendet, wie es gespeichert ist, einschließlich Leerzeichen.

**Vollständiger Titel** verwendet das Trennzeichen nicht. Er ersetzt den Dokumenttitel allein.

Ist der ursprüngliche Titel leer, wird nur der hinzugefügte Teil verwendet.

### 4.10 Kurzübersicht der Einstellungen

| Einstellung | Schlüssel | Standard |
| --- | --- | --- |
| Eigenschaften für Kombinationen aktivieren | `combfeat_p_feat` | Aktiviert (`1`) |
| Datenblatt-CSS-Klasse | `combfeat_ds` | `.data-sheet` |
| Arbeitsablauf | `combfeat_workflow` | Ersetzen (`0`) |
| Filter combination features in Faceted Search | `combfeat_faceted` | Aktiviert (`1`) |
| Beschreibungen für Kombinationen aktivieren | `combfeat_p_desc` | Aktiviert (`1`) |
| Beschreibung der CSS-Klasse / Objekt-ID | `combfeat_description` | `#description` |
| Meta-Titel für Kombinationen aktivieren | `combfeat_p_title` | Aktiviert (`1`) |
| Standard-Titelmodus | `combfeat_title_default` | Attributname und Wert (`1`) |
| Titel-Trennzeichen | `combfeat_title_separator` | ` - ` |

## 5. Import der Kombinations-Eigenschaften

Das zweite Formular auf der Konfigurationsseite. Diese Beschriftungen sind derzeit in jeder Sprache die englischen Quelltexte (sie stehen noch nicht in den Übersetzungsdateien).

![Formular Import der Kombinations-Eigenschaften](https://mypresta.eu/docs/images/docs/configure-import.webp)

Der Import weist Kombinationen Eigenschaftswerte zu. Er importiert keine Beschreibungen und keine Titel und schreibt keine Zeilen in die Produkteigenschaftenliste (`feature_product`). Eine fehlende Eigenschaft oder ein fehlender Wert wird im Katalog angelegt.

### 5.1 Import mode

| Modus | Wirkung |
| --- | --- |
| **Append to combination features** (Standard) | Bereits gespeicherte Zuweisungen bleiben. Eine Zeile, die auf dieser Kombination schon liegt, wird übersprungen. |
| **Replace features of listed combinations** | Für jede Kombination, die in der Datei vorkommt, werden deren Modul-Eigenschaften gelöscht und danach die Dateizeilen geschrieben. Kombinationen, die nicht in der Datei stehen, bleiben. Beschreibungen und Titel werden nicht gelöscht. |

### 5.2 Dateiregeln

- UTF-8, Endung `.csv` oder `.txt`. Ein führendes BOM ist zulässig. Maximal **8 MB**.
- Das Trennzeichen wird aus der Kopfzeile erkannt: Semikolon, Komma oder Tabulator. Fehlen alle drei, wird das Semikolon verwendet.
- Der Kopf muss die Kombination über `id_product_attribute` oder `combination_reference` bestimmen.
- Der Kopf muss die Eigenschaft über `feature` und `value` oder über `id_feature_value` bestimmen.
- Leere Zeilen werden übersprungen. Höchstens 30 Zeilenfehler werden aufgeführt, der Rest wird gezählt.

Akzeptierte Spaltennamen (Leerzeichen und Bindestriche werden Unterstriche, Großschreibung wird ignoriert):

| Spalte | Ebenfalls akzeptiert |
| --- | --- |
| `id_product` | `product_id` |
| `id_product_attribute` | `id_combination`, `combination_id` |
| `product_reference` | — |
| `combination_reference` | `combination_ref`, `attribute_reference` |
| `feature` | `feature_name`, `id_feature` |
| `value` | `feature_value` |
| `id_feature_value` | `feature_value_id` |

`id_product` und `product_reference` sind optional. Wenn Sie sie füllen, müssen sie zu dieser Kombination gehören. Eine Abweichung verwirft die Zeile.

Kombination finden:

- `id_product_attribute` wird verwendet, wenn es größer als null ist. Sind ID und `combination_reference` beide gefüllt, muss die Referenz zu dieser Zeile passen.
- Sonst wird die Kombinationsreferenz verwendet. Teilen sich mehrere Kombinationen dieselbe, ergänzen Sie `id_product` oder `id_product_attribute`. Meldung: Combination reference matches more than one combination.

Eigenschaftswert finden:

- `id_feature_value` größer als null lädt diesen Wert. Die Zellen für Name und Wert werden ignoriert.
- Sonst sind `feature` und `value` erforderlich. Eine Eigenschaftszelle, die nur aus Ziffern besteht, ist eine Eigenschafts-ID.
- Namen werden exakt gesucht, danach ohne Rücksicht auf Großschreibung. Passt mehr als eine Eigenschaft oder ein Wert, wird die Zeile verworfen. Es wird nichts geraten.
- Eine nicht vorhandene Eigenschaft wird angelegt. Ihr Name wird in jede Shop-Sprache kopiert. Höchstlänge 128.
- Ein nicht vorhandener Wert wird als normaler (nicht individueller) Wert angelegt, mit demselben Text in jeder Sprache. Höchstlänge 255. Bearbeiten Sie danach **Katalog > Attribute & Eigenschaften**, wenn die Sprachen unterschiedliche Texte brauchen.

**Download sample file** liefert `import/combfeat-features-sample.csv`:

```csv
id_product;id_product_attribute;product_reference;combination_reference;feature;value;id_feature_value
12;45;DEMO-1;DEMO-1-RED;Material;Cotton;
12;46;DEMO-1;DEMO-1-BLUE;Material;Wool;
;;DEMO-2;DEMO-2-XL;Composition;100% cotton;
10;25;;;;;83
```

Die Beispielzeilen bedeuten:

1. Kombination 45 von Produkt 12, Referenzen müssen passen, Eigenschaft Material / Cotton (wird angelegt, falls sie fehlt).
2. Kombination 46 von Produkt 12, Material / Wool.
3. Die Kombination mit der Referenz `DEMO-2-XL` am Produkt mit der Referenz `DEMO-2`, Eigenschaft Composition / 100% cotton. Keine numerischen IDs.
4. Kombination 25 von Produkt 10, vorhandener Eigenschaftswert 83. Name und Wert sind leer.

Nach einem erfolgreichen Import wird der Block-Cache der Facettensuche geleert. Die Bestätigung nennt, wie viele Zuweisungen gespeichert wurden, wie viele schon vorhanden waren und welche Zeilen fehlschlugen.

## 6. Inhalt der Kombination am Produkt

**Katalog > Produkte**, Produkt bearbeiten, Registerkarte **Module**. Blocktitel: **Inhalt der Kombination**. Untertitel: **Eigenschaften, Beschreibungen und Meta-Titel pro Kombination**.

![Inhalt der Kombination auf der Registerkarte Module](https://mypresta.eu/docs/images/docs/product-combination-content.webp)

Die Abbildung zeigt ein Produkt im englischen Backoffice. Der Eigenschaftswert in der geöffneten Zeile gehört zu diesem Produkt. **Description** und **Meta title** auf dem Bild sind die weiteren Registerkarten derselben Zeile. Deutsch heißen sie **Beschreibung** und **Meta-Titel**.

Legen Sie zuerst die Kombinationen an (Registerkarte **Kombinationen** des Produkts). Hat das Produkt keine, sagt der Block das, und es gibt nichts zu bearbeiten.

### 6.1 Die Liste

- **Alle aufklappen** / **Alle einklappen**.
- **Kombinationen filtern…** trifft Kombinationsname, Kombinations-ID und Kombinationsreferenz.
- Jede Zeile zeigt das Kombinationsbild (oder einen Platzhalter), die Attributnamen, **Combination ID**, **Reference** (wenn die Kombination eine hat) und Kennzeichen. Die Kennzeichen **Eigenschaften**, **Beschreibung** und **Titel** leuchten, wenn dieser Teil gefüllt ist. Das Eigenschaften-Kennzeichen nennt die Anzahl der Werte. Combination ID und Reference sind die englischen Quelltexte.
- Die erste Kombination ist offen. **Konfigurieren** öffnet eine Zeile, **Schließen** klappt sie zu.
- In der Zeile stehen die Registerkarten der aktiven Schalter: **Eigenschaften**, **Beschreibung**, **Meta-Titel**.

Sind alle drei Schalter aus, zeigt der Block: Alle Kombinationsoptionen sind deaktiviert. Aktivieren Sie Eigenschaften, Beschreibungen oder Titel in der Modulkonfiguration.

### 6.2 Eigenschaften

Hilfetext: Suchen und fügen Sie Eigenschaftswerte hinzu, die für diese Kombination auf der Produktseite verwendet werden.

Tippen Sie mindestens **2 Zeichen** des Eigenschaftsnamens oder des Werts, in der aktuellen Sprache des Mitarbeiters. Bis zu 20 Treffer erscheinen, beschriftet als `Eigenschaft: Wert`. Ein Treffer fügt einen Token hinzu. Die Suche findet nur Werte, die schon existieren. Legen Sie sie im Katalog an oder über den CSV-Import.

Derselbe Wert kann nicht zweimal hinzugefügt werden. Mehrere Werte derselben Eigenschaft können. **×** entfernt einen Token. Das Entfernen wird mit dem Produkt gespeichert.

### 6.3 Beschreibung

Ein Rich-Text-Feld je Sprache. Die Sprachauswahl erscheint, wenn der Shop mehr als eine Sprache hat. Leeres HTML gilt als keine Beschreibung: In der Storefront erscheint wieder die lange Produktbeschreibung, und beim Speichern wird die Zeile dieser Sprache gelöscht.

### 6.4 Meta-Titel

Beide Felder sind je Sprache, je 512 Zeichen. Ein leeres Feld überspringt diese Überschreibung.

| Feld | Wirkung in der Storefront |
| --- | --- |
| **Vollständiger Titel (gesamten Titel überschreiben)** | Ersetzt den gesamten Dokumenttitel. Trennzeichen und Standardmodus werden nicht verwendet. Sind beide Felder gefüllt, gewinnt dieses. |
| **Zum Titel hinzufügen (Fragment wird am Ende hinzugefügt)** | Ursprünglicher Dokumenttitel, dann das Trennzeichen, dann dieses Fragment. Wird verwendet, wenn der vollständige Titel leer ist. |

Sind beide leer, gilt der Standard-Titelmodus aus Abschnitt 4.8.

### 6.5 Speichern

Änderungen werden mit dem Produkt gespeichert. Verwenden Sie die Schaltfläche **Speichern** des Produkts (einschließlich Speichern und Vorschau, je nach PrestaShop-Version). Im Block gibt es keine eigene Speichern-Schaltfläche.

Beim Speichern:

1. Löscht das Modul jede Kombinations-Eigenschaftszeile dieses Produkts und fügt die Token aus dem Formular ein.
2. Speichert oder löscht es je Sprache die Beschreibung.
3. Speichert es je Sprache die Titelzeile oder löscht sie, wenn beide Titelfelder leer sind.
4. Leert es den Block-Cache der Facettensuche, wenn diese Option an ist.

Das Formular sendet ein verborgenes Feld `combfeat_submitted`. Fehlt das Feld, fasst das Modul die Daten nicht an. In PrestaShop 8 und 9 hängt das von der Twig-Änderung in Abschnitt 3.1 ab.

Das Löschen einer Kombination in PrestaShop löscht ihre Zeilen in diesem Modul nicht. Die Zeilen werden nicht verwendet, weil die Kombination nicht mehr existiert. Eigenschaften entfallen, wenn Sie das Produkt speichern (das Formular sendet nur aktuelle Kombinationen). Beschreibungs- und Titelzeilen einer gelöschten Kombination bleiben, bis Sie sie aus der Datenbank entfernen.

## 7. Storefront

Skripte werden nur auf der Produktseite geladen, nur wenn die Anfrage kein Ajax-Neuaufbau des ganzen Controllers ist, nur wenn das Produkt Kombinationen hat und nur wenn mindestens einer der drei Schalter an ist.

| Schalter | Skript |
| --- | --- |
| Eigenschaften oder Beschreibungen, Arbeitsablauf = Ersetzen | `views/js/combfeat.js` |
| Eigenschaften oder Beschreibungen, Arbeitsablauf = Hinzufügen | `views/js/combfeat-append.js` |
| Meta-Titel | `views/js/combfeat-title.js` |

Beim Wechsel der Kombination gibt es keine weitere Anfrage. Die Daten aller Kombinationen stehen in der Seite für die **aktuelle Sprache**. Das Skript liest die gewählte Kombination aus dem Attribut `data-product` von `#product-details` (`id_product_attribute`) und läuft beim Ereignis `updatedProduct` erneut.

`displayProductAdditionalInfo` gibt außerdem ein verborgenes Element `#product-details-combfeat` mit der für die erste Ansicht aufgelösten Kombination aus (Attributgruppen aus der URL, `id_product_attribute` aus der Anfrage oder die Standardkombination). Nicht verfügbare Kombinationen folgen der Lagereinstellung von PrestaShop und **Nicht verfügbare Attribute anzeigen**. Das verborgene Element wird nur verwendet, wenn `#product-details` selbst fehlt. Themes, die `#product-details` behalten, müssen `data-product` an dieses Element setzen. So ist es in der Standard-Produktvorlage.

Das Modul lädt kein Storefront-Stylesheet. Die neuen `<dt class="name">` und `<dd class="value">` nutzen die Datenblatt-Regeln des Themes.

### 7.1 Eigenschaften und Beschreibungen teilen sich ein Skript

`combfeat.js` und `combfeat-append.js` aktualisieren Datenblatt **und** Beschreibung, sobald sie geladen sind. Sie lesen die beiden Schalter nicht erneut.

- Eigenschaften an, Beschreibungen aus: Eine früher gespeicherte Beschreibung wird weiter angewendet, bis Sie sie leeren und speichern.
- Beschreibungen an, Eigenschaften aus: Noch gespeicherte Eigenschaften werden weiter angewendet. Speichern des Produkts bei ausgeschaltetem Eigenschaftsschalter löscht diese gespeicherten Eigenschaften. Siehe Abschnitt 4.1.

Das Titel-Skript ist getrennt und läuft nur, wenn der Titelschalter an ist.

### 7.2 Datenblatt

Ersetzen und Hinzufügen stehen in Abschnitt 4.3. Bei jedem Lauf baut das Modul die Zeilen neu. Zusätzliches Markup, das das Theme im Datenblatt hatte (Links, zusätzliche Klassen an einem Wert), bleibt nicht erhalten.

### 7.3 Beschreibung

Hat die Kombination eine Beschreibung in der aktuellen Sprache, ersetzt dieses HTML den Inhalt des Beschreibungsselektors. Sonst ersetzt ihn die lange Produktbeschreibung. Der Modus Hinzufügen hängt keinen Beschreibungstext an.

### 7.4 Titel

Reihenfolge für die gewählte Kombination, in der aktuellen Sprache:

1. **Vollständiger Titel**, wenn er nicht leer ist.
2. Sonst **Zum Titel hinzufügen**, verbunden mit dem Trennzeichen aus Abschnitt 4.9.
3. Sonst der Standard-Titelmodus aus Abschnitt 4.8.

`og:title` erhält denselben Text, wenn dieses Meta-Tag vorhanden ist.

## 8. Facettensuche

Bei aktiver Option lesen die Kategoriefilter eine View, die vereint:

- `feature_product` — dem Produkt zugewiesene Eigenschaften;
- `combfeat` — aktive, Kombinationen zugewiesene Eigenschaften, verbunden mit `feature_value`, um die Eigenschafts-ID zu erhalten.

Bauen Sie den Index der Facettensuche neu oder leeren Sie den PrestaShop-Cache, wenn ein Filter veraltet bleibt, nachdem die Warnung auf der Konfigurationsseite behoben ist. Speichern von Kombinations-Eigenschaften und CSV-Import leeren `layered_filter_block` bereits.

Die Produktseite im Shop zeigt die Produkteigenschaften von PrestaShop weiter, bis das Skript dieses Moduls läuft. Filter und Datenblatt sind zwei verschiedene Quellen.

## 9. MyPresta-Updates

Das Panel unter den Formularen:

![Panel MyPresta-Updates](https://mypresta.eu/docs/images/docs/configure-updates.webp)

Die Abbildung zeigt das englische Backoffice. **Check now** ist **Jetzt prüfen**, **Updates notifications** ist **Update-Benachrichtigungen**, **Module page** ist **Modulseite**.

| Steuerung | Verhalten |
| --- | --- |
| **Jetzt prüfen** | Kontaktiert MyPresta und zeigt **Neue Version verfügbar!** oder **Das Modul ist auf dem neuesten Stand!** |
| **Update-Benachrichtigungen** | **Aktivieren** zeigt eine Backoffice-Warnung, wenn eine neuere Version vorliegt, mit dem Text **Neue Version verfügbar, besuchen Sie http://MyPresta.eu für weitere Informationen** und dem Link **Weitere Details im Changelog**. **Deaktivieren** blendet diese Warnung aus. |
| **Modulseite** | Öffnet die Add-on-Seite: [Product combination features](https://mypresta.eu/modules/front-office-features/product-combination-features.html) |

Solange ein Mitarbeiter im Backoffice ist, kontaktiert das Modul den Update-Server höchstens einmal alle 3 Tage. Die Prüfung braucht `allow_url_fopen`. Ist das nicht verfügbar, bleibt die installierte Version, und eine neuere wird nicht gemeldet.

## 10. Fehlersuche

**Der Block auf der Registerkarte Module ist unter PrestaShop 8 oder 9 leer.**  
Prüfen Sie, ob `modules-content.html.twig` `{{ module.content|raw }}` enthält und der Shop die Datei schreiben konnte. Öffnen Sie die Modulkonfiguration erneut, damit der Versuch wiederholt wird. Leeren Sie danach den Symfony-Cache (**Erweiterte Einstellungen > Leistung**).

**Das Datenblatt ändert sich nicht.**  
Das Produkt braucht Kombinationen, der Eigenschaftsschalter muss an sein oder Eigenschaften müssen schon gespeichert sein, und die Kombination braucht mindestens einen Wert (im Modus Ersetzen schreibt eine Kombination ohne Werte die Produkteigenschaften zurück; das kann wie „nichts passiert“ aussehen). Prüfen Sie den Selektor in der Browserkonsole: `document.querySelectorAll('.data-sheet')` mit Ihrem echten Selektor. Das Theme muss `data-product` an `#product-details` aktualisieren und `updatedProduct` auslösen.

**Der ganze Block product-details wurde durch eine kurze Eigenschaftenliste ersetzt.**  
Der Datenblatt-Selektor hat nichts getroffen. Setzen Sie ihn auf das echte `<dl>`, in der Regel `.data-sheet`.

**Die Beschreibung ändert sich nicht, oder die Kurzbeschreibung wurde durch die lange Beschreibung ersetzt.**  
Der Standardselektor `#description` ist in Classic die lange Beschreibung. Der Ersatztext ist immer die lange Beschreibung. Zeigen Sie **Beschreibung der CSS-Klasse / Objekt-ID** auf das Element, das sich ändern soll.

**Beschreibungen sind aus und der alte Text erscheint weiter.**  
Leeren Sie die Felder, speichern Sie das Produkt, und schalten Sie erst dann aus. Oder schalten Sie auch die Eigenschaften aus, damit keines dieser Skripte lädt. Eigenschaften auszuschalten und zu speichern löscht gespeicherte Kombinations-Eigenschaften.

**Eigenschaften sind aus und nach dem Speichern des Produkts verschwunden.**  
So arbeitet das Speichern, wenn die Eigenschaftsfelder nicht im Formular stehen. Schalten Sie die Option wieder ein, bevor Sie bearbeiten, falls die Daten noch gebraucht werden. Importieren Sie die CSV erneut, wenn Sie die Datei haben.

**Der Titel des Browser-Tabs ändert sich nicht.**  
Schalten Sie den Titelschalter ein. Ein leerer vollständiger Titel und ein leeres Feld Zum Titel hinzufügen zusammen bedeuten, dass der Standardmodus gilt. **Titel standardmäßig nicht ändern** lässt den Titel stehen. Die Änderung liegt im Browser: Seite öffnen, Kombination wechseln, Tab-Titel lesen. Der HTML-Quelltext hat weiter den Meta-Titel des Produkts.

**Eine Eigenschaft fehlt im Kategoriefilter.**  
Schalten Sie **Filter combination features in Faceted Search** ein, nehmen Sie die Eigenschaft in die Vorlage der Facettensuche auf und lesen Sie die Warnung auf der Modulkonfiguration. Die Adapterdatei muss beschreibbar sein. Der Wert muss am Produkt oder an einer Kombination gespeichert sein.

**CSV-Zeilenfehler.**

| Meldung | Ursache |
| --- | --- |
| The CSV must contain id_product_attribute or combination_reference | Der Kopf bestimmt keine Kombination |
| The CSV must contain feature and value, or id_feature_value | Der Kopf bestimmt keinen Eigenschaftswert |
| Combination was not found | ID oder Referenz existiert nicht |
| Product ID does not match this combination | `id_product` ist gefüllt und zeigt auf ein anderes Produkt |
| Product reference does not match this combination | `product_reference` passt nicht |
| Combination reference does not match this combination ID | ID und Referenz sind gefüllt und widersprechen sich |
| Combination reference matches more than one combination | Ergänzen Sie `id_product` oder `id_product_attribute` |
| Feature name or value matches more than one | Zwei Katalogeinträge tragen dieselbe Bezeichnung. Verwenden Sie `id_feature_value` |
| Feature and value are required when id_feature_value is empty | Namens- oder Wertzelle ist leer |
| The CSV file is larger than 8 MB | Teilen Sie die Datei |

**Mehrere Sprachen.**  
Beschreibungen und beide Titelfelder werden je Sprache gespeichert. Eigenschaftswerte nutzen die PrestaShop-Übersetzung der Eigenschaft in der Sprache des Besuchers. Die Zuweisung selbst ist nicht je Sprache.

## 11. Technische Referenz

### 11.1 Hooks

| Hook | Wann | Aufgabe |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Backoffice, Controller `AdminProducts` und `AdminModules` | Lädt `views/css/combfeat.css`, `views/js/acplt.js`, `views/js/admin-combfeat.js` und jQuery-Autovervollständigung. Sichert außerdem Konfiguration und Facettensuche |
| `displayAdminProductsExtra` | Produktbearbeitung, Registerkarte Module | Gibt `views/templates/admin/combfeat.tpl` aus |
| `actionProductUpdate` | Produktspeichern | Schreibt Eigenschaften, Beschreibungen und Titel, wenn `combfeat_submitted` vorhanden ist |
| `displayHeader` | Produktseite, kein Ajax | Gibt Kombinationsdaten der aktuellen Sprache aus und hängt die Storefront-Skripte an |
| `displayProductAdditionalInfo` | Produktseite | Gibt das verborgene `views/templates/hook/product-details.tpl` aus |

Bei der Installation registriert: `actionProductUpdate`, `displayProductAdditionalInfo`, `displayAdminProductsExtra`, `actionAdminControllerSetMedia`, `displayHeader`.

Die Konfigurationsseite beantwortet auch die Eigenschaftssuche. Eine Anfrage mit `ajax=1` und `q` liefert JSON-Treffer und endet. Der Produkteditor ruft diese URL über `AdminModules` mit `configure=combfeat` auf.

### 11.2 Datenbank

Der Präfix ist der Shop-Präfix. Die Deinstallation löscht diese Tabellen **nicht**. Kombinationsinhalte überstehen die Deinstallation und sind nach einer späteren Installation noch da (`CREATE TABLE IF NOT EXISTS`).

`combfeat` — eine Zeile je Eigenschaftswert an einer Kombination:

| Spalte | Rolle |
| --- | --- |
| `id_combfeat` | Primärschlüssel |
| `id_product` | Produkt |
| `id_product_attribute` | Kombination |
| `id_feature_value` | Eigenschaftswert aus dem Katalog |
| `active` | `1`, wenn die Zeile verwendet wird. Storefront und Facettensuche-View lesen aktive Zeilen |

`combfeat_details` — Beschreibung, eine Zeile je Kombination und Sprache:

| Spalte | Rolle |
| --- | --- |
| `id_combfeat` | Primärschlüssel |
| `id_product`, `id_product_attribute`, `id_lang` | Ziel |
| `details` | HTML |
| `active` | Gespeichert als `1` |

`combfeat_title` — Titel, eine Zeile je Kombination und Sprache:

| Spalte | Rolle |
| --- | --- |
| `id_combfeat` | Primärschlüssel |
| `id_product`, `id_product_attribute`, `id_lang` | Ziel |
| `title_full` | Bis 512 Zeichen. Ersetzt den Dokumenttitel |
| `title_append` | Bis 512 Zeichen. Wird nach dem ursprünglichen Titel gesetzt |
| `active` | Gespeichert als `1` |

`{prefix}combfeat_feature_product` — SQL-View, keine Inhaltstabelle zum Bearbeiten. Vereinigung von `feature_product` und aktiven `combfeat`-Zeilen. Der Konfigurationswert `COMBFEAT_FEATURE_VIEW` speichert die View-Version (`1`).

Weitere Konfigurationsschlüssel: `update_combfeat` und `updatev_combfeat` (Update-Prüfung), `mypresta_updates` (Benachrichtigungsschalter).

### 11.3 PHP-Klassen

| Datei | Klasse | Rolle |
| --- | --- | --- |
| `combfeat.php` | `combfeat` | Modulklasse: Installation, Konfiguration, Hooks, Daten des Produkteditors, Storefront-Daten |
| `combfeat.php` | `combfeatUpdate` | Versionsvergleich und Anfrage an den Update-Server |
| `classes/CombfeatImporter.php` | `CombfeatImporter` | CSV-Auswertung, Auflösung von Kombination und Eigenschaft, Beispiel-Download |
| `classes/CombfeatFacetedSearch.php` | `CombfeatFacetedSearch` | View, Adapter-Patch, Wiederherstellung, Leeren des Filter-Caches |
| `models/cfeat.php` | `cfeat` | Zeilen von `combfeat`. `getAllByProductId`, `getFeaturesStaticByIdProduct`, `assign`, `insertDatas`, Löschungen |
| `models/cfeatdesc.php` | `cfeatdesc` | Zeilen von `combfeat_details` |
| `models/cfeattitle.php` | `cfeattitle` | Zeilen von `combfeat_title`. `saveTitleRow` löscht die Zeile, wenn beide Titel leer sind |

Es gibt kein Verzeichnis `controllers/`.

### 11.4 Dateien und Templates

| Datei | Wo | Rolle |
| --- | --- | --- |
| `views/js/acplt.js` | Backoffice | Autovervollständigung der Eigenschaftssuche |
| `views/js/admin-combfeat.js` | Backoffice | Akkordeon, Filter, Registerkarten, Sprachflaggen, Token, TinyMCE-Auffrischung, Kopieren des Editorinhalts vor dem Speichern |
| `views/css/combfeat.css` | Nur Backoffice | Layout von **Inhalt der Kombination** |
| `views/js/combfeat.js` | Storefront, Ersetzen | Baut Datenblatt und Beschreibung neu |
| `views/js/combfeat-append.js` | Storefront, Hinzufügen | Gleich, Produkteigenschaften stehen vor den Kombinations-Eigenschaften |
| `views/js/combfeat-title.js` | Storefront | `document.title` und `og:title` |
| `views/templates/admin/combfeat.tpl` | Registerkarte Module des Produkts | Der Editor |
| `views/templates/hook/product-details.tpl` | Produktseite | Verborgenes `#product-details-combfeat` mit `data-product` |
| `import/combfeat-features-sample.csv` | Download aus der Konfiguration | Importbeispiel |

### 11.5 Installation und Deinstallation

Die Installation legt die drei Tabellen an, schreibt die Standardkonfiguration, registriert die fünf Hooks, wendet die Twig-Änderung an und aktiviert die Facettensuche.

`disable` stellt den Facettensuche-Adapter wieder her. `enable` schreibt fehlende Konfigurationsschlüssel und aktiviert die Integration erneut, wenn der Facettensuche-Schalter an ist.

Die Deinstallation stellt den Adapter wieder her, löscht die View, wenn sie nicht mehr referenziert wird, und deinstalliert das Modul. Kombinationszeilen in den drei Tabellen bleiben in der Datenbank.

## 12. Support

Änderungsprotokoll und Updates: [Product combination features auf MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html).

Bestellungen und Support: [Kundenkonto MyPresta.eu](https://mypresta.eu/my-account/orders/). E-Mail: support@mypresta.eu.