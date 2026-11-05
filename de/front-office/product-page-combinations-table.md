---
title: "Combinations Tab Pro - Dokumentation und Benutzerhandbuch"
description: "Konfigurieren Sie die Kombinationsmatrix, die täglichen Einstellungen der Produktseite und beheben Sie häufige Storefront-Probleme, wenn Sie Combinations Tab Pro bereits besitzen."
sidebar:
  label: "Combinations Tab Pro - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product page combinations table auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-page-combinations-table/)
>
> ---


Screenshots in diesem Handbuch stammen aus einem englischen Back Office. Verwenden Sie dieselben Tab- und Feldnamen unten, auch wenn die Sprache Ihres Mitarbeiters abweicht.

## 1. Anforderungen

Combinations Tab Pro zeigt eine Kombinationsliste oder eine 2D-Matrix auf der Produktseite, damit Kunden filtern, sortieren, Mengen setzen und Varianten in den Warenkorb legen können.

- PrestaShop: 1.7, 8 und 9
- PHP: eine von Ihrem PrestaShop-Shop unterstützte Version
- PHP-Erweiterungen, die das Modul nutzt: JSON
- Andere Module: keine erforderlich. Optional schaltet **Product combination features** die Spalten für Kombinationsbeschreibung und Kombinationsmerkmale frei, wenn dieses Modul im Shop installiert ist
- Außerhalb des Shops: nichts. Update-Prüfungen kontaktieren MyPresta, wenn Benachrichtigungen aktiviert sind
- Große Kataloge: viele Kombinationen pro Produkt verlangsamen die Seite, wenn Sie jede Spalte und sowohl Listen- als auch Grid-Extras aktiviert lassen; nutzen Sie Filter, Paginierung oder ein Preset, das zu Ihrem Katalog passt

## 2. Installation

1. Laden Sie die Modul-ZIP unter **Modules** → **Module Manager** hoch, installieren und aktivieren Sie anschließend **Combinations Tab Pro**.
2. Öffnen Sie die Konfiguration aus der Modulliste mit **Configure**. Es gibt keinen eigenen Back-Office-Menüeintrag für den täglichen Betrieb; alle Einstellungen liegen auf dieser Konfigurationsseite.
3. Die Installation leert den PrestaShop-Cache nicht selbst. Leeren Sie Smarty-/Theme-Cache unter **Advanced Parameters** → **Performance**, wenn die Tabelle nach der Installation nicht erscheint.

**Nach der Deinstallation:** Das Modul wird aus dem Module Manager entfernt. Datenbanktabellen für Wishlist, Benachrichtigungen bei Wiederverfügbarkeit und Override-Profile pro Entität werden gelöscht. Konfigurationswerte bleiben in der Shop-Datenbank, sodass eine spätere Neuinstallation die bisherigen Schalter wieder übernehmen kann, bis Sie sie erneut ändern. Theme-Overrides von Modul-Templates (falls Sie welche hinzugefügt haben) werden durch die Deinstallation nicht entfernt.

## 3. Konfiguration und Arbeit im Back Office

Öffnen Sie **Modules** → **Module Manager** → **Combinations Tab Pro** → **Configure**. Die Seite verwendet obere Tabs: **Overview**, **Display**, **Cart**, **B2B**, **Visibility**, **Exclusions**, **Integrations**, **Overrides**, **Updates**. Die Produktsuche auf **Visibility**, **Exclusions** und **Overrides** läuft im Hintergrund (AJAX); es gibt kein separates Orders-Menü für dieses Modul.

### 3.1 Gesamtablauf

1. Der Händler konfiguriert Platzierung, Ansichtsmodus, Spalten oder Grid-Zellen, Warenkorbregeln, optionale B2B-Werkzeuge, Sichtbarkeit, Ausschlüsse, Integrationen und Overrides.
2. Der Kunde öffnet ein Produkt mit Kombinationen, das die Sichtbarkeitsregeln erfüllt.
3. Der Storefront zeigt eine Liste (eine Zeile pro Kombination) oder ein 2D-Grid (Matrix, wenn das Produkt zwei Attributgruppen hat und der Ansichtsmodus dies erlaubt), im Produkt-Footer oder unter einem Tab **Product variants**.
4. Der Kunde kann Attributfilter nutzen, Listenköpfe sortieren, Mengen setzen und eine oder mehrere Zeilen in den Warenkorb legen (einschließlich Bulk-Hinzufügen).
5. Optionale Werkzeuge: Wishlist-Herz, Benachrichtigung bei Wiederverfügbarkeit, CSV-Mengen-Einfügen, Exportblatt, letzte Bestellung füllen.
6. Der Checkout läuft als normale PrestaShop-Bestellung. Das Modul verwendet keine Angebots-/Quote-Status; Erfolg ist eine sichtbare Tabelle, ausgefüllte Mengen und ein Warenkorb mit den gewählten Kombinationen.

### 3.2 Overview & presets

![Overview and presets — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overview.webp)

**Overview & presets** ist der Start-Tab. Fertige Setups schalten viele Schalter auf einmal ein oder aus. Nutzen Sie **Preview**, um die geplanten Werte zu sehen, dann **Apply**. Bestätigung: *Preset applied. Review Display & Columns and Cart & prices if you want to fine-tune.* Öffnen Sie danach **Display** und **Cart**, um Details anzupassen.

Haupt-Presets nach Name:

| Preset | Tag | What it prepares |
|---|---|---|
| **Fashion** | B2C | Fotos, Filter, Farbswatches, Wishlist, mobile Karten für Bekleidung mit vielen Größen und Farben |
| **B2B Wholesale** | B2B | SKU-first-Matrix, Bulk-Hinzufügen zum Warenkorb, CSV-Import, Export, Mengenrabatte |
| **Minimal** | Simple | Nur Kombinationsname, Preis und In den Warenkorb |
| **Replace buy block** | UX | Blendet den Standard-PrestaShop-Kaufblock aus, damit Kunden aus der Tabelle bestellen |
| **2D size × color** | Grid | Erzwingt 2D-Grid mit reichhaltigem Zelleninhalt, wenn Produkte Farbe + Größe haben |
| **Detailed list** | List | Volle Liste mit Bildern, SKU, EAN, Lager, Sortierung, Paginierung |
| **Electronics** | B2C | Referenz, EAN, Stückpreis, Verfügbarkeitsdaten für Geräte und Gadgets |
| **Beauty & cosmetics** | B2C | Farbbox + Text, Fotos, Wishlist und Wiederverfügbarkeit für Nuancen und Sets |
| **Catalog only** | Display | Kombinationen ohne Bestellung; Preise können für eingeloggte Kunden sichtbar bleiben |
| **Logged-in pricing** | B2B | Preise und In den Warenkorb nur für eingeloggte Kunden |
| **Mobile first** | UX | Liste mit mobilen Karten, Plus/Minus-Menge, sticky Bulk-Hinzufügen |
| **Restock & alerts** | Conversion | Ausverkaufte Zeilen mit Daten und Benachrichtigungen bei Wiederverfügbarkeit |
| **Luxury / lookbook** | B2C | Große Fotos, Zoom, versteckter exakter Bestand, Ersparnis-Highlights |
| **Food & packaging** | Retail | Stückpreis, Gewicht, Mindestmenge, Mengenrabatte |
| **Quick order sheet** | B2B | Grid + Bulk-Hinzufügen + CSV/Export/Nachbestellung ohne Bilder |

### 3.3 Display — Placement

![Display settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-display.webp)

Unter-Tab **Placement**. Seitenplatzierung und Rahmen um die Tabelle (Liste und 2D-Grid). Speichern zeigt *Display settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Position on the product page** | Product footer (below product content) | Wählt, wo Kunden die Kombinationstabelle sehen. Nutzen Sie **Product footer** unter dem Produkt oder **Product tabs section** für einen Tab wie **Product variants**. Wählen Sie den Ort, der zu Ihrem Theme passt — die falsche Wahl kann die Tabelle verstecken oder zu weit nach unten setzen. |
| **Tab style (legacy themes)** | Classic tabs (PS 1.5 style) | Nur relevant, wenn Sie die Position Product tabs auf älteren Themes nutzen. Lassen Sie den Standard, außer Ihr Theme verwendet noch PrestaShop-1.5-Tabs. Ändert, wie der Tab-Titel eingefügt wird; moderne 1.7/8/9-Themes ignorieren dies meist. Optionen: Classic tabs (PS 1.5 style) oder Accordion bars (PS 1.6 style). |
| **Custom HTML above the table** | Empty | Freier Inhalt (Versandhinweis, Link zur Größenberatung u. Ä.) oberhalb der Matrix. Optional pro Sprache. Sichtbar über Liste und 2D-Grid. |
| **Hide default PrestaShop buy block** | No | Blendet die klassischen Attribut-Dropdowns und In den Warenkorb auf der Produktseite aus. Setzen Sie **Yes**, wenn die Tabelle der einzige Kaufweg sein soll. Klarere Seite; stellen Sie sicher, dass die Tabelle selbst In den Warenkorb erlaubt. |
| **Hide default buy block only when table has combinations** | No | Behält den normalen Kaufblock bei einfachen Produkten; blendet ihn aus, wenn die Matrix gezeigt wird. **Yes** ist meist am sichersten, damit einfache Produkte weiter normal funktionieren. |
| **Also hide default buy block based on product restrictions** | No | Erweiterte Kopplung mit Visibility-Regeln. Lassen Sie **No**, außer Sie nutzen komplexe Anzeige-/Ausblendlisten. Kann den nativen Kaufblock auf ausgewählten Produkten auch ohne Tabelle ausblenden. |

### 3.4 Display — View mode

| Field | At the start | What it does |
|---|---|---|
| **View mode** | List (classic table — one row per combination) | Wählt Listentabelle oder 2D-Matrix. **List** = immer Zeilen; **2D grid** = Matrix erzwingen, wenn möglich; **Auto** = Matrix bei 2 Attributgruppen, sonst Liste. Fashion-/B2B-Shops mit Farbe+Größe passen zu Grid/Auto; Produkte mit einem Attribut bleiben Liste. |
| **Click combination to open that variant** | Off | Ein Klick auf Zeile/Zelle öffnet die Produkt-URL dieser Kombination. Setzen Sie **Yes**, wenn Sie Varianten aus der Tabelle browsen möchten. Nützlich mit Fotos; deaktivieren, wenn Klicks nur die Menge ändern sollen. |

### 3.5 Display — Filters

Diese Regeln gelten für die Listentabelle und das 2D-Grid.

| Field | At the start | What it does |
|---|---|---|
| **Attribute filters above the table / grid** | Off | Zeigt klickbare Chips (z. B. Red, XL) zum Filtern von Zeilen/Spalten. Setzen Sie **Yes** bei Produkten mit vielen Kombinationen. Kunden grenzen Liste und Matrix ein, ohne endlos zu scrollen. |
| **Hide out-of-stock combinations** | Off | Entfernt ausverkaufte Kombinationen aus Liste und 2D-Grid. Setzen Sie **Yes**, um nur verfügbare Varianten zu verkaufen. Kürzere Tabelle/Matrix; fehlende Größen sind nicht sichtbar. |
| **Hide combinations with price = 0** | Off | Versteckt kostenlose/Nullpreis-Varianten in Liste und Grid. Setzen Sie **Yes**, wenn Null „nicht verkaufbar“ bedeutet. Matrizen können unvollständig wirken, wenn manche Zellen absichtlich 0 sind. |
| **Show only combinations that have a picture** | Off | Versteckt Kombinationen ohne Bilder in Liste und Grid. Setzen Sie **Yes** für Lookbooks; **No**, wenn jede SKU bestellbar sein muss. Unvollständige Kataloge wirken schöner, aber manche Varianten verschwinden. |
| **Multistore: disabled attribute values** | Hide the whole combination | Wenn ein Attributwert für den aktuellen Shop deaktiviert ist. Nur Multistore — wählen Sie Kombination verstecken, als „-“ anzeigen oder ignorieren. Gilt, bevor Liste und Grid gebaut werden; Ein-Shop-Stores können den Standard belassen. |

### 3.6 Display — Stock format

Wie Lagerbestände in Liste und Grid angezeigt werden, wenn Bestand gezeigt wird. Sichtbarkeit von Spalte/Zelle liegt unter List columns bzw. Grid cells.

| Field | At the start | What it does |
|---|---|---|
| **Show negative stock as zero** | Off | Zeigt 0 statt negativer Zahlen. Setzen Sie **Yes**, wenn Ihr Bestand unter null gehen kann. Klarere Bestandszahlen in Liste und Grid. |
| **Hide exact stock above a threshold** | Off | Zeigt z. B. „20+“ statt der echten Zahl. Setzen Sie **Yes** und den Schwellenwert. Versteckt große Lagerzahlen vor Wettbewerbern in Liste und Grid. |
| **Stock threshold (show as X+)** | Empty | Wenn exakter Bestand verstecken **Yes** ist, erscheinen Mengen darüber als „N+“. Beispiel: 20 macht Bestand 45 zu „20+“. |

### 3.7 Display — Grid axes, images, cells

Ein 2D-Grid ist eine Matrix im Stil Größe×Farbe. Es funktioniert, wenn das Produkt genau zwei Attributgruppen hat und View mode **Grid** oder **Auto** ist. Falsche Achsenpaarung (dieselbe Gruppe zweimal) zerstört das Grid und fällt auf die Liste zurück.

**Grid axes**

| Field | At the start | What it does |
|---|---|---|
| **Grid rows = attribute group** | -- automatic -- | Welches Attribut die linke Seite der Matrix wird (z. B. Color). Gruppe wählen oder Automatic lassen (erste Attributgruppe nach Position). Falsches Paar bricht das Grid und fällt auf die Liste zurück. |
| **Grid columns = attribute group** | -- automatic -- | Welches Attribut die Oberseite der Matrix wird (z. B. Size). Andere Gruppe als Zeilen wählen, oder Automatic. Jede Zelle ist eine Kombination, in die Kunden die Menge tippen. |

**Grid images** (nur 2D-Grid)

| Field | At the start | What it does |
|---|---|---|
| **Show image in cells** | Off | Miniatur in jeder Matrixzelle. Setzen Sie **Yes** für Fashion-Farbe×Größe-Matrizen. Dichtere Zellen; nutzt Kombinationsbild oder Cover-Fallback unten. |
| **Use product cover when combination has no image** | Yes | Zeigt das Hauptproduktfoto als Fallback in Grid-Zellen. Setzen Sie **Yes**, um nie ein leeres Bild in der Matrix zu zeigen. Betrifft nur 2D-Grid, nicht die Liste. |
| **Grid thumbnail image type** | Empty (shop image types) | PrestaShop-Bildgröße in Grid-Zellen. Kleinen Typ wählen (z. B. cart / small_default). Nur 2D-Grid; Liste nutzt List images → Thumbnail type. |

**Grid cells** — **Cell block order** ziehen (oben→unten), dann Save. Nur aktivierte Blöcke erscheinen. Wishlist/BIS brauchen weiterhin **Integrations**; In den Warenkorb braucht den Hauptschalter unter **Cart**.

| Field | At the start | What it does |
|---|---|---|
| **Cell block order** | Default block order | Reihenfolge der Blöcke in jeder Matrixzelle. Ziehen, dann Save. Nur aktivierte Blöcke unten erscheinen. Bild an/aus und Größe unter Grid images. |
| **Grid: show reference (SKU)** | Off | SKU unter dem Zelleninhalt. Setzen Sie **Yes** für B2B, damit Käufer SKUs ohne Produktöffnung erkennen. |
| **Grid: show price** | Off | Preis in der Zelle (Steuer-/Rabattregeln folgen Cart-Einstellungen). Setzen Sie **Yes** für fast jeden Shop, damit Kunden Varianten in der Matrix nach Preis vergleichen. |
| **Grid: show unit price** | Off | Stückpreis in der Zelle. Setzen Sie **Yes**, wenn Sie Stückpreise nutzen. Kompakte Zeile unter dem Hauptpreis. |
| **Grid: show stock quantity** | Off | Verfügbare Bestandszahl in der Zelle. Setzen Sie **Yes** für Transparenz; zeigt Inventar pro Größe/Farbe. |
| **Grid: show availability** | Off | Label In stock / Out of stock in der Zelle. Setzen Sie **Yes**, wenn Bestandszahlen versteckt sind. Klarer Status ohne exakte Menge. |
| **Grid: show minimal quantity** | Off | Mindestbestellmenge in der Zelle. Setzen Sie **Yes** für B2B-Packs; verringert falsche Warenkorbmengen. |
| **Grid: show savings badge** | Off | % gespart gegenüber der teuersten Kombination. Setzen Sie **Yes** für Conversion; hebt günstigere Größen/Farben hervor. |
| **Grid: quantity input** | Off | Mengenfeld in jeder Zelle (arbeitet mit Bulk Add to cart). Setzen Sie **Yes** für Matrix-Bestellung, damit Kunden Mengen pro Größe füllen. |
| **Grid: Add to cart button (when bulk ATC is off)** | Off | Pro-Zelle-Hinzufügen-Button, wenn Bulk add to cart deaktiviert ist. Setzen Sie **Yes** für Ein-Klick-Hinzufügen ohne Bulk. Wird ignoriert, solange Bulk ATC an ist. |
| **Grid: wishlist heart** | Off | Herz-Button in der Zelle. Zuerst Wishlist unter Integrations aktivieren. Kunden speichern Größe/Farbe aus der Matrix. |
| **Grid: back-in-stock alert** | Off | Benachrichtigen-Button auf ausverkauften Zellen. Zuerst Back in stock unter Integrations aktivieren. Erfasst Nachfrage nach fehlenden Größen. |

### 3.8 Display — List layout, images, columns

Diese Einstellungen betreffen nur die klassische Liste (eine Zeile pro Kombination), nicht 2D-Grid-Zellen.

**List layout & sorting**

| Field | At the start | What it does |
|---|---|---|
| **Column order (list only)** | Default column order | Setzt die Links-nach-rechts-Reihenfolge der Spalten in der Listenansicht. Elemente ziehen, dann Save. Kunden sehen Spalten in dieser Reihenfolge (nur aktivierte Spalten erscheinen). |
| **Mobile card layout (list)** | Yes | Auf Handys werden breite Tabellenzeilen zu gestapelten Karten. Setzen Sie **Yes** für bessere mobile UX. Jede Kombination wirkt wie eine kleine Karte; Desktop bleibt normale Tabelle. |
| **Hide table header (list)** | Off | Entfernt die obere Zeile mit Spaltennamen. Meist **No** lassen. Klareres Aussehen, aber Spalten schwerer zu verstehen. |
| **Paginate long tables (list)** | Off | Teilt viele Kombinationen in Seiten. Setzen Sie **Yes**, wenn ein Produkt Dutzende Varianten hat. Schnelleres Seitengefühl; Rows per page unten setzen. |
| **Rows per page** | 10 when pagination is used without a custom value | Wie viele Kombinationen pro Seite bei aktiver Paginierung. Beispiel: 10 oder 20. Kleinere Zahl = kürzere Seiten, mehr Klicken. |
| **Allow sorting by column headers** | Yes | Klickbare Köpfe zum Sortieren der Liste. Setzen Sie **Yes** für lange Listen. Kunden sortieren nach Preis, Referenz u. Ä. (nur Listenansicht). |
| **Default sort by price** | Off | Initiale Sortierung nach Preis. Optional. Günstigste/teuerste zuerst je nach Richtung. |
| **Default sort by attribute** | Off | Initiale Sortierung nach gewählter Attributgruppe. Attribut-ID und Richtung unten setzen. Beispiel: Größen S→XL. |
| **Attribute sort uses** | Attribute value position | Sortieren nach Attributposition (Katalogreihenfolge) oder Name A→Z. Position ist meist am besten für Größen. Ändert die Standard-Zeilenreihenfolge, wenn Attributsortierung aktiv ist. |
| **Attribute group ID to sort by** | Empty | Numerische ID der Attributgruppe für die Standardsortierung. Unter Catalog → Attributes die Gruppe öffnen und die ID aus der URL lesen. Falsche ID = unerwartete Reihenfolge. |
| **Sort direction** | Ascending | Aufsteigende oder absteigende Standardreihenfolge. Ascending für S→XL; Descending für Preis hoch→niedrig bei Preissortierung. Steuert die ersten Zeilen, die Kunden sehen. |

**List images**

| Field | At the start | What it does |
|---|---|---|
| **Show image column** | Yes | Fügt eine Miniatur pro Kombination hinzu. Setzen Sie **Yes**, wenn Varianten unterschiedliche Fotos haben, damit Kunden Varianten schneller erkennen. |
| **Show image column only if at least one combination has a photo** | Off | Versteckt die leere Bildspalte, wenn keine Kombination ein Bild hat. Setzen Sie **Yes**, um eine nutzlose leere Spalte zu vermeiden. Tabelle bleibt sauber bei Produkten ohne Kombinationsbilder. |
| **Use product cover when combination has no image** | Off | Zeigt das Hauptproduktfoto als Fallback in der Liste. Setzen Sie **Yes**, um nie eine leere Bildzelle zu zeigen. Betrifft nur Listenansicht, nicht 2D-Grid. |
| **Click image to zoom** | Off | Öffnet ein größeres Bild in einer Lightbox. Setzen Sie **Yes** für visuelle Produkte; Zoomgröße unten setzen. Kunden prüfen Details ohne die Seite zu verlassen. |
| **Thumbnail image type** | Empty (shop image types) | PrestaShop-Bildgröße in der Listenspalte. Kleinen Typ wählen (z. B. cart / small_default). Nur Liste; Grid nutzt Grid images → Thumbnail type. |
| **Zoom image type** | Empty (shop image types) | Bildgröße in der Lightbox bei aktiviertem Zoom. Großen Typ wählen (z. B. large_default). Schärfere Zoomvorschau in der Listenansicht. |

**List columns** — Sichtbarkeit für die klassische Liste. Kombinationsbeschreibung / Merkmale brauchen das optionale Combination-features-Modul; sonst bleiben diese Steuerelemente mit Shop-Link gesperrt.

| Field | At the start | What it does |
|---|---|---|
| **How attributes are shown** | All attributes in one column | Eine kombinierte Spalte „Combination name“ vs. getrennte Spalten pro Attribut (Color, Size…). Getrennte Spalten sind leichter zu scannen und zu sortieren. Listenlayout ändert sich sofort. |
| **Include attribute label in the name** | Off | Zeigt „Color: Red, Size: L“ statt „Red, L“. Setzen Sie **Yes** für Klarheit; gilt nur für die Ein-Spalten-Methode. Längere, aber klarere Namen. |
| **Color attribute display** | Text only | Wie Farbwerte aussehen (Swatch, Text oder beides). Farbbox für Fashion; Text, wenn Farben besonders benannt sind. Betrifft nur Attribute vom Typ „color“. |
| **Show combination / attribute columns** | Yes | Hauptschalter für Attributnamensspalten. Fast immer **Yes**. **No** versteckt, wie Varianten sich unterscheiden — nur für sehr spezielle Layouts. |
| **Show combination description** | Off (locked without Combination features) | Zeigt die der Kombination durch Combination features zugewiesene Beschreibung. Setzen Sie **Yes**, wenn Varianten eigenen Text haben. Extra-Listenspalte; leere Zellen zeigen „-“. |
| **Show combination features** | Off (locked without Combination features) | Zeigt der Kombination durch Combination features zugewiesene Merkmalswerte. Setzen Sie **Yes**, wenn Varianten ein eigenes Datenblatt haben. Extra-Listenspalte mit Merkmalsname + Werten. |
| **Show reference (SKU)** | Yes | Zeigt die Kombinationsreferenz. Setzen Sie **Yes** für B2B / Großhandel, damit Käufer schneller nach SKU bestellen. |
| **Show EAN** | No | Zeigt Barcode EAN-13. Setzen Sie **Yes**, wenn Mitarbeiter/Kunden Codes scannen. Extra-Spalte; für B2C-Fashion aus, wenn ungenutzt. |
| **Show MPN** | No | Spalte Herstellerteilenummer. Setzen Sie **Yes**, wenn Sie MPN im Katalog pflegen. Leere Zellen zeigen „-“, wenn MPN leer ist. |
| **Show weight** | Off | Produktgewicht + Kombinations-Impact. Setzen Sie **Yes** für versandsensible Waren, damit Kunden Versand einschätzen. |
| **Show stock quantity** | Yes | Verfügbarer Bestand pro Kombination. Setzen Sie **Yes** für Transparenz; mit Stock format für „10+“ koppeln. Schafft Vertrauen; zeigt Inventar. |
| **Show total product stock in header** | No | Fügt die Bestandssumme neben dem Quantity-Header hinzu. Optionale Schnellübersicht der Gesamtverfügbarkeit. |
| **Show availability text** | Yes | „In stock“ / „Out of stock“ (oder Ihre Shop-Labels). Setzen Sie **Yes** für Klarheit, damit Kunden den Status ohne Zahlenlesen sehen. |
| **Show availability date when out of stock** | Yes | Druckt das Verfügbarkeitsdatum der Kombination unter dem Ausverkaufsstatus. Setzen Sie **Yes**, wenn Sie Verfügbarkeitsdaten pflegen. Setzt Erwartungen zur Nachlieferung. |
| **Show minimal quantity** | Off | Zeigt die Mindestbestellmenge der Kombination. Setzen Sie **Yes** für B2B-Packs; verringert Add-to-cart-Fehler. |
| **Show price** | Yes | Preisspalte pro Kombination (nur Liste). Setzen Sie **Yes** für fast jeden Shop. Kunden vergleichen Varianten nach Preis. Grid nutzt Grid cells → show price. |
| **Show unit price** | Off | Stückpreisspalte (nur Liste). Setzen Sie **Yes**, wenn Sie Stückpreise nutzen. Leere/seltsame Werte, wenn Unity am Produkt nicht gesetzt ist. |
| **Show savings column** | No | Wie viel günstiger eine Kombination vs. der teuersten ist (nur Liste). Setzen Sie **Yes** für Upsell-Psychologie. Extra-Spalte mit % und gespartem Betrag. Grid nutzt Grid cells → savings badge. |
| **Show volume (quantity) discounts column** | Off | Listet Mengenrabattstufen pro Kombination (nur Liste). Setzen Sie **Yes** für Großhandel. Breitere Tabelle; gut für B2B. |
| **Hide volume discount rows that do not apply** | Off | Bereinigt leere Rabattlisten in der Listenspalte. Setzen Sie **Yes**, um Rauschen zu reduzieren, sodass nur sinnvolle Stufen bleiben. |

### 3.9 Cart — Prices

![Cart settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-cart.webp)

Unter-Tab **Prices**. Globale Preisanzeigeregeln für Liste und 2D-Grid. Speichern zeigt *Cart & price settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Show prices only to logged-in customers** | No | Gäste sehen statt Preisen einen Login-Hinweis. Setzen Sie **Yes** für versteckte B2B-Preise. Gäste müssen sich einloggen, um Beträge in Liste und Grid zu sehen. |
| **Tax display** | Tax included | Steuer inklusive, exklusive oder Einstellung der Kundengruppe folgen. An Ihre Shop-Preispolitik anpassen. Falsche Wahl verwirrt B2B- vs. B2C-Käufer. |
| **Show “tax incl./excl.” label next to price** | Off | Kleiner Text nach dem Preis. Setzen Sie **Yes** für rechtliche Klarheit in der EU. Etwas vollere Zellen. |
| **Show discount % badge on reduced prices** | Off | Zeigt -X%, wenn eine spezifische Preisreduktion existiert. Setzen Sie **Yes**, um Angebote hervorzuheben. Lenkt Aufmerksamkeit auf rabattierte Kombinationen in Liste und Grid. |
| **Highlight the cheapest combination** | Yes | Markiert die günstigste Zeile/Zelle. Setzen Sie **Yes**, um Impulskäufe zu lenken. Grüne Hervorhebung des besten Preises in Liste und Grid. |

### 3.10 Cart — Add to cart

| Field | At the start | What it does |
|---|---|---|
| **Show add to cart controls** | Yes | Mengenfeld und/oder Button pro Kombination. Setzen Sie **Yes**, um aus der Tabelle zu verkaufen. **No** = nur Anzeige-Matrix. |
| **Add to cart only for logged-in customers** | Off | Gäste können nicht aus der Tabelle hinzufügen. Setzen Sie **Yes** für B2B. Gäste sehen statt Buttons eine Meldung. |
| **Show quantity input** | Yes | Editierbares Mengenfeld. **Yes** immer empfohlen. **No** versteckt die Menge (mehrere Einheiten schwerer zu kaufen). |
| **Qty box also in the table header (fill all rows)** | Off | Eine Header-Menge kopiert auf alle Zeilen. Optionale Bequemlichkeit. Beschleunigt Bulk-Füllen; vorsichtig nutzen. |
| **Plus / minus buttons** | No | +/- Schrittschalter neben der Menge. Setzen Sie **Yes** für Touch-Geräte. Einfachere Mengenänderung. |
| **Block qty higher than stock** | Off | Verhindert Bestellung über den Bestand hinaus (wenn Ausverkaufsbestellungen nicht erlaubt sind). Setzen Sie **Yes**, um Überverkauf zu vermeiden. +-Button stoppt am Bestand. |
| **AJAX add to cart** | Yes | Fügt ohne vollständigen Seitenreload hinzu. Setzen Sie **Yes** bei modernen Themes. Flüssigere UX; nur deaktivieren bei Theme-Konflikt. |
| **Bulk add to cart (one button for many rows)** | Off | Kunde füllt mehrere Mengenfelder, dann sendet ein **Add to cart** alle. Setzen Sie **Yes** für B2B/Fashion. Standard-Buttons pro Zeile können ausgeblendet werden; sticky Bar erscheint mobil. |
| **Show live total price of selected quantities** | Off | Berechnet die Summe der gewählten Zeilen (respektiert Mengenrabatte, wenn möglich). Setzen Sie **Yes** mit Bulk-Hinzufügen. Kunden sehen den Warenwert vor dem Klick auf Add. |
| **Tip: how many units until next quantity discount** | Yes | Unter der Bulk-Leiste sagt es dem Kunden „add X more to unlock the next discount“. Setzen Sie **Yes**, wenn Sie Mengenrabatte nutzen. Fördert größere Warenkörbe. |
| **Use Font Awesome cart icon** | Off | FA-Icon statt Material-Icon. Setzen Sie **Yes** nur, wenn Ihr Theme Font Awesome lädt. Fehlendes FA = kaputtes Icon. |

### 3.11 B2B Tools and Groups

![B2B tools — English back office](https://mypresta.eu/docs/images/docs/combinationstab-b2b.webp)

**Tools** — Großhandelshelfer. Globale Schalter sind Standardwerte; nutzen Sie **Groups**, um pro PrestaShop-Kundengruppe zu erlauben oder zu verweigern. Speichern zeigt *B2B settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **CSV quantity import on product page** | No | Käufer fügen Zeilen wie SKU;5 (oder EAN;qty) ein, um Mengen zu füllen. Setzen Sie **Yes** für Großhandel; dann ggf. pro Gruppe erlauben. Großer Zeitgewinn bei Nachbestellungen. |
| **Export order sheet (CSV / XLSX / PDF)** | No | Lädt die Kombinationen mit getippten Mengen herunter. Setzen Sie **Yes** für Käufer, die Blätter an die Buchhaltung senden. Buttons erscheinen neben Bulk-Hinzufügen. |
| **Fill last order button** | No | Stellt Mengen aus dem letzten Bulk-Hinzufügen / Export für dieses Produkt wieder her. Setzen Sie **Yes** für wiederholte Großhandelsbestellungen. Ein Klick füllt die Matrix neu. |

**Groups** — für jede Kundengruppe **Show table**, **Add to cart**, **CSV import**, **Export**, **Reorder** setzen (Yes/No). Standard ohne eigene Regel: Show table Yes, Add to cart Yes, CSV/Export/Reorder folgen den globalen Tools-Schaltern (nach Installation aus). Wenn **Show table** für die Gruppe des Besuchers No ist, erscheint die Matrix nicht. Wenn **Add to cart** No ist, kann der Besucher nicht aus der Tabelle hinzufügen, auch wenn die globalen Cart-Schalter an sind.

### 3.12 Visibility

![Visibility — English back office](https://mypresta.eu/docs/images/docs/combinationstab-visibility.webp)

Steuern Sie, auf welchen Produkten Kunden die Kombinationstabelle sehen. Produkte mit dem On-Screen-Produktpicker suchen (AJAX-Suche). Bestätigung: *Successfully updated*.

| Field | At the start | What it does |
|---|---|---|
| **Visibility rule** | Show on all products | Entscheidet, ob die Tabelle auf jedem Produkt, nur auf ausgewählten oder überall außer ausgewählten erscheint. Regel wählen, dann Kategorien anhaken / Produkte im Selektor unten hinzufügen. „All products“ ist am einfachsten; Include/Exclude nutzen, wenn nur manche Katalogartikel die Matrix brauchen. |
| **Selected categories & products** | None | Die Liste der Kategorien und Produkte für die Regel oben. Kategorien anhaken und/oder Produkte suchen und Add klicken. Nur bei Regel Include oder Exclude — bei „all products“ ignoriert. |
| **Hide table when product has too few attribute groups** | Off | Versteckt die Tabelle auf Produkten mit nur wenigen Attributgruppen (z. B. nur Color, kein Size). Setzen Sie **Yes** und die Zahl unten. Beispiel: Schwelle 1 versteckt Produkte mit 1 oder weniger Attributgruppen — nützlich, wenn Sie die Matrix nur für Color+Size-Produkte wollen. |
| **Hide when attribute groups ≤** | Empty | Schwelle für den Schalter oben. 1 eingeben, um Ein-Attribut-Produkte zu verstecken; 0 versteckt praktisch nie nach dieser Regel. Vergleich mit der Anzahl Attributgruppen am Produkt. |

### 3.13 Exclusions

Gewählte Kombinationen dauerhaft aus der Tabelle ausblenden (alle Produkte). Produkt suchen, Kombinationen mit **Select** wählen, dann **Save**. Bestätigung: *Settings saved*. Diese Varianten bleiben in PrestaShop, erscheinen aber nie in der Matrix — nützlich für veraltete Größen oder interne SKUs. Produkt- und Kombinationssuche nutzt dieselbe AJAX-Produktsuche wie Visibility.

| Field | At the start | What it does |
|---|---|---|
| **Search for product** | Empty | Finden Sie das Produkt, dessen Kombinationen Sie ausschließen möchten. |
| **Combination** | None selected | Markieren Sie Kombinationen, die aus der Storefront-Matrix ausgeblendet werden sollen, dann Save. |

### 3.14 Integrations

![Integrations — English back office](https://mypresta.eu/docs/images/docs/combinationstab-integrations.webp)

Speichern zeigt *Integrations saved.* Das Formular vermerkt Advanced Stock Management, wenn erkannt; ohne ASM den Warehouse-Schalter auf Off lassen.

| Field | At the start | What it does |
|---|---|---|
| **Combination wishlist** | No | Herz-Button speichert eine Variante in einer leichten Wishlist (Konto oder Cookie). Setzen Sie **Yes**, wenn Kunden Größen merken. Link erscheint in My Account; keine vollständige Wishlist-Suite. |
| **Back-in-stock email alerts** | No | Ausverkaufte Zeilen erhalten einen Benachrichtigen-Button; bei Wiederverfügbarkeit mailt das Modul dem Kunden. Setzen Sie **Yes** und stellen Sie sicher, dass Ihr Shop E-Mails senden kann. Holt Nachfrage nach fehlenden Größen zurück. |
| **Warehouse stock column** | No | Listet Mengen pro Lager, wenn Advanced Stock aktiv ist. Setzen Sie **Yes** nur mit ASM. Ohne ASM bleibt die Spalte leer — Off lassen. |

### 3.15 Overrides

![Overrides — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overrides.webp)

Profile kaskadieren **Product → deepest Category → Manufacturer → Global**. Nur überschriebene Felder ändern die untere Schicht. Liste filtern mit **All / Products / Categories / Manufacturers**. Anlegen mit **Product override**, **Category override** oder **Manufacturer override**.

Auf dem Bearbeitungsbildschirm: Entität suchen und wählen, nur die zu überschreibenden Felder aktivieren, nicht angehakte Felder erben lassen. **Copy all from global** nutzen, um Werte zu befüllen, dann **Save override**. Erfolg: *Override profile saved.* Löschen fragt *Delete this override profile?* Erfolg: *Override profile deleted.*

Typische Gründe für Overrides: eine Marke braucht immer Grid-Modus; eine Kategorie versteckt Preise für Gäste; ein Produkt braucht Extra-SKU-Spalten ohne den ganzen Shop zu ändern.

### 3.16 Updates

**Check now** fragt MyPresta, ob ein neuerer Build existiert. Meldungen: *New version available!* oder *Module is up to date!*

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | — | Führt eine sofortige Prüfung aus und zeigt, ob eine neue Version existiert. |
| **Updates notifications** | Select / as previously saved | Schalten Sie diese Option ein, wenn Sie MyPresta.eu automatisch auf Modul-Updates prüfen möchten. Diese Option zeigt Benachrichtigungen über neue Versionen dieses Addons. |
| **Module page** | Link on screen | Direkter Link zur offiziellen Addon-Seite, auf der Sie Änderungen am Modul (Changelog) nachlesen können. Nutzen Sie Support (Kapitel 7) für Hilfeanfragen. |

## 4. Front Office

- **Placement:** Produkt-Footer unter dem Produktinhalt oder ein Tab **Product variants** im Produkt-Tab-Bereich, abhängig von Display → Placement.
- **List vs 2D grid:** Liste ist eine Zeile pro Kombination. Grid ist eine Matrix, wenn das Produkt genau zwei Attributgruppen hat und View mode Grid oder Auto ist; sonst fällt der Storefront auf die Liste zurück.
- **Filters:** Attribut-Chips über Tabelle/Grid, wenn aktiviert.
- **Sorting / pagination / mobile cards:** nur Liste, wenn diese Display-Optionen an sind.
- **Add to cart:** Steuerelemente pro Zeile und/oder Bulk **Add to cart** mit optionaler Live-Summe und Tipp „units until next discount“.
- **Toolbar:** wenn aktiviert — **Fill last order**, **Export** (CSV / XLSX / PDF), **Import quantities**-Textarea mit Zeilen wie `REF001;5`, dann **Apply**.
- **Wishlist:** Herz auf Zeilen/Zellen, wenn Integrations + Spalten-/Zellen-Schalter es erlauben. Eingeloggte Kunden erhalten **My combination wishlist** auf der Kundenkonto-Seite.
- **Back in stock:** Benachrichtigen-Steuerung auf ausverkauften Zeilen; E-Mail bei Wiederverfügbarkeit (Shop-Mail muss funktionieren).
- **Guest prices:** bei „prices only for logged-in“ sehen Gäste statt Beträgen einen Login-Hinweis; bei „ATC only for logged-in“ können Gäste nicht aus der Tabelle hinzufügen.

Kein separates Storefront-Screenshot ist hier nötig; das Theme-Layout entscheidet über den genauen Rahmen um den Modulblock.

## 5. Häufige Probleme

### 5.1 Tabelle auf der Produktseite nicht sichtbar

Prüfen Sie: Modul aktiviert, Produkt hat Kombinationen, **Visibility**-Regel schließt das Produkt ein, Kundengruppe **Show table** ist Yes, und die Position passt zu Ihrem Theme (Footer vs. Tabs). Cache leeren. Bestätigen Sie, dass Exclusions nicht jede Kombination ausgeblendet hat.

### 5.2 Falsche Position oder leerer Tab

Ändern Sie **Position on the product page**. Bei modernen Themes Tab style ignorieren. Wenn Sie Tabs nutzen, Produkt öffnen und nach **Product variants** suchen.

### 5.3 2D-Grid erwartet, aber Liste sichtbar

Grid braucht genau zwei Attributgruppen und View mode Grid oder Auto. Ein Attribut oder drei oder mehr erzwingen die Liste. Dieselbe Attributgruppe für beide Achsen fällt ebenfalls auf die Liste zurück — unterschiedliche Zeilen- und Spaltengruppen setzen.

### 5.4 Standard-Kaufblock fehlt oder ist noch sichtbar

Prüfen Sie **Hide default PrestaShop buy block** und **Hide default buy block only when table has combinations**. Wenn der native Block ausgeblendet ist, die Tabelle aber kein In den Warenkorb hat, können Kunden nicht kaufen — Cart → **Show add to cart controls** einschalten.

### 5.5 Bulk-Hinzufügen tut nichts oder lädt schlecht neu

**AJAX add to cart** für moderne Themes einschalten. Bestätigen Sie, dass **Bulk add to cart** Yes ist und Mengen gefüllt sind. Gruppenregel **Add to cart** muss für diese Kundengruppe Yes sein.

### 5.6 Gruppenregeln blockieren In den Warenkorb oder verstecken die Tabelle

Unter **B2B** → **Groups** **Show table** und **Add to cart** für die Gruppe des Besuchers (Guest, Customer oder Ihre Großhandelsgruppe) auf Yes setzen.

### 5.7 Preise für Gäste versteckt

Erwartet, wenn **Show prices only to logged-in customers** Yes ist. Für öffentliche Preise auf Off stellen oder Gäste zum Einloggen auffordern.

### 5.8 Wishlist oder Wiederverfügbarkeit fehlt

Unter **Integrations** aktivieren, dann passende Listen-Spalten- oder Grid-Zellen-Schalter einschalten. Für BIS bestätigen, dass PrestaShop Mail senden kann und der Bestand beim Auffüllen aktualisiert wird.

### 5.9 Spalten Kombinationsbeschreibung / Merkmale gesperrt

Optionales Modul **Product combination features** installieren und aktivieren. Bis dahin bleiben diese Spalten in Display und Overrides gesperrt.

### 5.10 CSV / Export / letzte Bestellung füllen fehlt

Werkzeuge unter **B2B** → **Tools** aktivieren und für diese Kundengruppe unter **Groups** auf Yes setzen.

## 6. Entwicklerleitfaden

### 6.1 Überblick

- Technischer Name: `combinationstab`
- Version: 3.0.5
- Anzeigename: Combinations Tab Pro
- Autor: mypresta.eu
- Modul-Tab: `smart_shopping`
- Hauptklasse: `Combinationstab`
- BO-UI: `CtpAdminBo` (`lib/CtpAdminBo.php`)
- Einstellungsauflösung: `CtpSettingsResolver` (Product → Category → Manufacturer → Global)
- Optional: `CtpCombfeat` — Datei kann fehlen; `class_exists('CtpCombfeat')` steuert Kombinationsbeschreibung/-merkmale. Ohne die Klasse bleiben diese Optionen gesperrt.

Ablauf: Configuration / Entity-Einstellungen → FO-Hooks rendern Listen- oder Grid-Templates → Front-Controller behandeln AJAX-Warenkorb-Helfer, Wishlist, BIS, CSV, Export, Nachbestellung, Preisrechner.

### 6.2 Wichtige Dateien

| Path | Role |
|---|---|
| `combinationstab.php` | Modulklasse, Install/Uninstall, Hooks, Visibility-/Exclusions-Formulare |
| `lib/CtpAdminBo.php` | Configure-Seiten-Tabs und HelperForm-Felder |
| `lib/CtpColumnRegistry.php` | Listenspalten, Presets, Order-JSON |
| `lib/CtpGridRegistry.php` | Grid-Zellenblöcke und Order-JSON |
| `lib/CtpGrid2d.php` | 2D-Matrix-Build / `shouldUseGrid` |
| `lib/CtpCombinationsData.php` | Kombinationszeilen für FO |
| `lib/CtpGroupRules.php` | Pro Gruppe show/atc/csv/export/reorder |
| `lib/CtpWishlist.php` / `CtpBackInStock.php` / `CtpExport.php` / `CtpReorder.php` | Feature-Helfer |
| `lib/CtpSettingsResolver.php` | Override-Tabelle und Kaskade |
| `views/templates/admin/tabs.tpl` | BO-Tab-Chrome |
| `views/templates/hook/productfooter.tpl` / `productfooter_grid.tpl` | FO Liste / Grid |
| `views/templates/hook/_toolbar.tpl` | Bulk- / Export- / CSV-Toolbar |
| `controllers/front/*.php` | Front-Endpunkte |
| `controllers/admin/AdminCombinationstabSearchController.php` | AJAX-Produktsuche für BO-Picker |

### 6.3 Controller

**Admin:** `AdminCombinationstabSearchController` — AJAX-Produkt-/Kombinationssuche für Visibility, Exclusions, Overrides. Keine Menüseite für Händler.

**Front:**

| Controller | Purpose |
|---|---|
| `Wishlist` | Wishlist umschalten / listen (JSON + Kontoseite) |
| `BackInStock` | Für OOS-Benachrichtigungen abonnieren (JSON) |
| `CsvImport` | Eingefügte SKU/EAN-Mengen anwenden (JSON) |
| `Export` | CSV/XLSX/PDF-Blatt herunterladen |
| `Reorder` | Letzte Mengen speichern / wiederherstellen (JSON) |
| `PriceCalculator` | Live-Summe der Auswahl / Mengenrabatt-Tipp (JSON-Body, kein curl) |

### 6.4 Hooks (bei Installation registriert)

`displayHeader`, `displayProductFooter`, `displayFooterProduct`, `displayProductTab`, `displayProductExtraContent`, `displayProductTabContent`, `CombinationsTable`, `ActionAdminControllerSetMedia`, `displayCustomerAccount`, `actionUpdateQuantity`.

Kein eigenes `enable()` / `disable()` über PrestaShop-Standards hinaus. Uninstall löscht Feature-Tabellen, dann `parent::uninstall()`.

### 6.5 Overrides

Das Modul liefert keine Klassen-/Controller-Overrides unter `override/`. Theme-Template-Overrides von Modul-`.tpl`-Dateien sind optional und händlerseitig.

### 6.6 Datenbank

Uninstall löscht diese Tabellen; Configuration-Keys bleiben erhalten.

| Table | Content |
|---|---|
| `ctp_wishlist` | `id_ctp_wishlist`, customer/guest, product, combination, shop, `date_add` |
| `ctp_backinstock` | E-Mail-Abonnements, product/combination, shop, lang, `notified`, dates |
| `ctp_entity_settings` | `entity_type`, `id_entity`, JSON `settings`, `date_upd` |

### 6.7 Configuration-Keys und Defaults (Install)

Ausgewählte Defaults bei Installation: `ctp_position` = `productFooter`, `ctp_where` = `1`, `ctp_view_mode` = `list`, `ctp_image`/`ctp_price`/`ctp_reference`/`ctp_cname`/`ctp_atc`/`ctp_atcq`/`ctp_ajax`/`ctp_sort`/`ctp_quantity`/`ctp_availability`/`ctp_availability_d` = `1`, `ctp_ean`/`ctp_mpn` = `0`, `ctp_wishlist`/`ctp_bis`/`ctp_export`/`ctp_csv_import`/`ctp_reorder` = `0`, `ctp_group_rules` = `{}`, `ctp_column_order` = JSON von `CtpColumnRegistry::defaultKeys()`, plus verwandte Tax-/Hide-/Grid-Keys wie in `install()`. Spalten-/Zellenreihenfolge nutzt ebenfalls JSON (`ctp_column_order`, `ctp_grid_cell_order`). Übersetzungen: `translations/{iso}.php`. Feld-`desc`-Texte liegen hauptsächlich in `CtpAdminBo`.

### 6.8 Erweiterung

FO-Templates vom Theme unter `modules/combinationstab/...` überschreiben, ohne das Modulpaket zu bearbeiten. Das Theme muss weiterhin die registrierten Produkthooks für die Ausgabe aufrufen. Optionale Combination-features-Integration erfordert vorhandenes `lib/CtpCombfeat.php` und `CtpCombfeat::isAvailable()` true.

## 7. Support

Produktseite: https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html

Hilfe erhalten: Melden Sie sich in Ihrem Kundenkonto auf mypresta.eu an, öffnen Sie Contact und wählen Sie **Support for paid modules**. Das Formular erfordert Login für kostenpflichtige Module; nach dem Login dieses Modul aus Ihrer Kaufhistorie wählen.
