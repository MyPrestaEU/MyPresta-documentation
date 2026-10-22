---
title: "SEO-freundliche URLs - Anleitung für den Händler"
description: "Anleitung zur Konfiguration und zur Fehlersuche für Händler, die dieses Modul bereits haben."
sidebar:
  label: "SEO-freundliche URLs - Anleitung für den Händler"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Pretty / Clean URLs PRO auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/pretty-clean-urls-pro/)
>
> ---


Technischer Name `purls`, Version 3.0.0, Name im Backoffice: SEO-freundliche URLs.

## Wo die Bildschirme liegen

Öffnen Sie **Module > Modul-Manager** und konfigurieren Sie **SEO-freundliche URLs**. Die Seite ist ein Formular **Einstellungen**, darunter das Panel **Mögliche Kollisionen**, darunter das Panel **MyPresta-Updates**. Das Modul legt keinen eigenen Menüpunkt an, keinen Import und keinen Block auf der Produktbearbeitung.

Die Beschriftungen stammen aus `translations/de.php`. Der Satz „on documentation page of this module“ steht nicht in den Übersetzungsdateien, der Bildschirm zeigt daher die englische Quelle.

## Was das Öffnen der Konfiguration schreibt

`install()` schreibt diese Werte nicht. Beim Öffnen der Konfiguration schreibt `getContent()` eine Route, wenn der aktuelle Wert fehlt oder leer ist:

| Schlüssel | Geschriebener Wert |
| --- | --- |
| `PURLS_ROUTE_cms_rule` | `info/{rewrite}.html` |
| `PURLS_ROUTE_cms_category_rule` | `info/{rewrite}` |
| `PURLS_ROUTE_supplier_rule` | `supplier/{rewrite}/` |
| `PURLS_ROUTE_manufacturer_rule` | `manufacturer/{rewrite}/` |
| `PS_ROUTE_category_rule` | `{parent_categories:/}{rewrite}/` |
| `PS_ROUTE_product_rule` | `{category:/}{rewrite}.html` |

`PS_ROUTE_product_rule` und `PS_ROUTE_category_rule` sind PrestaShop-Schlüssel. Sind sie leer, ersetzt das Öffnen dieser Seite sie durch die Werte oben. Bei mehr als einer Sprache werden die vier Schlüssel `PURLS_ROUTE_*` je Sprache gespeichert. Bei einer Sprache als einzelner Text.

## Einstellungen

![Der Bildschirm ist auf Englisch. In dieser Anleitung: Einstellungen.](https://mypresta.eu/docs/images/docs/purls-configure-settings.webp)

![Bildschirm auf Englisch, nach dem Speichern. Produkt-ID: ID of product + ID of attribute. Hash aus. Kategorien, Hersteller, Lieferanten und CMS an. 301 an. In dieser Anleitung: Einstellungen.](https://mypresta.eu/docs/images/docs/purls-configure-enabled.webp)

Die Legende heißt **Einstellungen**. Die Beschreibung lautet **Wählen Sie aus, von welchen URLs Sie die ID entfernen möchten**. Die Schaltfläche heißt **Speichern** (`submitCategoryFeatured`).

`install()` legt diese Schlüssel nicht an. Bis zum ersten Speichern gibt `Configuration::get` false zurück. Das Entfernen läuft nur für die Werte unten, ein fehlender Schlüssel lässt die ID im Pfad. Im Formular trifft false die Option `0` (**ID-Nummern nicht entfernen** / **Deaktiviert**).

| Beschriftung | Schlüssel | Werte |
| --- | --- | --- |
| Produkt-ID | `purls_products` | `0` ID-Nummern nicht entfernen. `1` Produkt-ID + Attribut-ID. `2` Nur Attribut-ID. `3` Nur Produkt-ID. |
| Hashcode mit Attributen | `purls_product_hash` | `1` Aktiviert, `0` Deaktiviert. |
| Kategorien | `purls_categories` | `1` Aktiviert entfernt die ID aus Kategorie-Links. `0` Deaktiviert. |
| Hersteller | `purls_manufacturers` | `1` Aktiviert entfernt die ID aus Hersteller-Links. `0` Deaktiviert. |
| Lieferanten | `purls_suppliers` | `1` Aktiviert entfernt die ID aus Lieferanten-Links. `0` Deaktiviert. |
| CMS | `purls_cms` | `1` Aktiviert entfernt die ID aus CMS-Links. `0` Deaktiviert. |
| 301-Weiterleitung von alten URLs | `purls_301` | Radio. `1` Aktiviert, `0` Deaktiviert. Text: Automatische Weiterleitung von alten URLs (mit ID) zu neuen URLs (ohne ID) aktivieren. |

Die Hilfe bei **Produkt-ID** nennt das Schema „Route zu Produkten“:

- **Produkt-ID + Attribut-ID**: `{id}` und `{id_product_attribute}` entfernen.
- **Nur Attribut-ID**: `{id_product_attribute}` entfernen.
- **Nur Produkt-ID**: `{id}` entfernen und als Attribut-ID `{id_product_attribute:-}` verwenden.

Dieselbe Hilfe öffnet `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`. Der Linktext ist die englische Quelle „on documentation page of this module“.

**Hashcode mit Attributen**: Aktiviert schneidet die Produkt-URL bei `#` ab. Deaktiviert, und nur wenn Produkt-ID `1` oder `2` ist, behält einen Hash wie `#/size-s/color-white`. Der Hilfetext sagt, die Option wirkt, wenn die Produktattribut-ID aus der URL entfernt ist. Im Code behält `Link::getProductLink()` den Hash nur, wenn `purls_product_hash` `0` ist und `purls_products` `1` oder `2` ist. Bei Wert `3` schneidet dieselbe Methode die URL immer bei `#`. Wert `0` der Produkt-ID ruft die PrestaShop-Elternmethode auf.

| Beschriftung | Schlüssel | Sprachfeld | Schlüsselwörter auf dem Formular |
| --- | --- | --- | --- |
| Produktregel | `PS_ROUTE_product_rule` | Nein | `{rewrite}`, `{category}`, `{categories}`, `{id}`, `{-:id_product_attribute}` |
| Kategorieregel | `PS_ROUTE_category_rule` | Nein | `{id}`, `{rewrite}`, `{parent_categories}` |
| Lieferantenregel | `PURLS_ROUTE_supplier_rule` | Ja | `{id}`, `{rewrite}` |
| Markenregel | `PURLS_ROUTE_manufacturer_rule` | Ja | `{id}`, `{rewrite}` |
| CMS-Seitenregel | `PURLS_ROUTE_cms_rule` | Ja | `{categories:/}`, `{id}`, `{rewrite}` |
| CMS-Kategorieseitenregel | `PURLS_ROUTE_cms_category_rule` | Ja | `{id}`, `{rewrite}` |

Bei Produktregel und Kategorieregel steht: Dieses Feld ist auch im Abschnitt „Schema der URLs“ unter: Shop-Parameter > Traffic & SEO konfigurierbar.

Bei Lieferant, Marke, CMS-Seite und CMS-Kategorie steht bei Schalter `0`: **Um dieses Feld zu bearbeiten, müssen Sie die Option zum Entfernen der ID von diesem URL-Typ aktivieren**. Das Feld bleibt editierbar. Dispatcher und `Link` nutzen die Modulroute nur bei Schalter `1`.

### Schemata für die Routenfelder

Das sind die Muster von der Schema-Seite. In **Produktregel** gehört eine Zeile aus der Gruppe, die zu **Produkt-ID** passt. `{category}` ist der Rewrite der Standardkategorie. `{categories}` sind die Rewrites der Elternkategorien, mit `/` verbunden (`Link::getProductLink()`). `{rewrite}` ist `link_rewrite`. `{id}` ist die Produkt-ID. `{id_product_attribute:-}` ist die Kombinations-ID, mit `-` davor, wenn diese ID gesetzt ist. Ein leeres Produktfeld wird mit `{category:/}{rewrite}.html` gefüllt, auch bei Produkt-ID `2` oder `3`. Für diese beiden Optionen eine Zeile ihrer Gruppe in **Produktregel** eintragen.

| Feld | Produkt-ID | Schema |
| --- | --- | --- |
| Produktregel | `1` | `{rewrite}.html` |
| Produktregel | `1` | `{category:/}{rewrite}.html` |
| Produktregel | `1` | `{categories}{rewrite}.html` |
| Produktregel | `1` | `{categories}{rewrite}` |
| Produktregel | `2` | `{id}-{rewrite}.html` |
| Produktregel | `2` | `{category:/}{id}-{rewrite}.html` |
| Produktregel | `2` | `{categories}{id}-{rewrite}.html` |
| Produktregel | `2` | `{categories}{id}-{rewrite}` |
| Produktregel | `3` | `{id_product_attribute:-}{rewrite}.html` |
| Produktregel | `3` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| Produktregel | `3` | `{categories}{id_product_attribute:-}{rewrite}.html` |
| Produktregel | `3` | `{categories}{id_product_attribute:-}{rewrite}` |

| Feld | Schema |
| --- | --- |
| Kategorieregel | `{parent_categories:/}{rewrite}/` |
| Kategorieregel | `{rewrite}/` |
| Lieferantenregel | `supplier/{rewrite}/` |
| Lieferantenregel | `any-text/{rewrite}/` |
| Markenregel | `manufacturer/{rewrite}/` |
| Markenregel | `any-text/{rewrite}/` |
| CMS-Seitenregel | `info/{rewrite}.html` |
| CMS-Kategorieseitenregel | `info/{rewrite}` |

Ein leeres Kategoriefeld wird mit `{parent_categories:/}{rewrite}/` gefüllt. Die andere Kategorienzeile ist die Alternative. `{parent_categories}` sind die Rewrites der Elternkategorien, mit `/` verbunden, ohne die IDs 1, 2 und die Kategorie selbst. Ein leeres Lieferantenfeld wird mit `supplier/{rewrite}/` gefüllt, ein leeres Markenfeld mit `manufacturer/{rewrite}/`. `any-text` ist kein Schlüsselwort. Es ist ein fester Vorsatz, den Sie anstelle dieser Wörter eintragen, zum Beispiel `marke/{rewrite}/`. Die Schema-Seite nennt keine Alternative für die beiden CMS-Regeln. Leere CMS-Felder werden mit `info/{rewrite}.html` und `info/{rewrite}` gefüllt.

`parent::loadRoutes()` liest `PS_ROUTE_` plus die Routen-ID. Ist dieser Wert nicht leer, ist diese Zeichenkette die kompilierte Regel. Ein gespeichertes Produkt- oder Kategorieschema ersetzt damit die Regel, die `loadRoutes()` gesetzt hat. Dieses Modul schreibt nicht `PS_ROUTE_supplier_rule_{id_lang}`, `PS_ROUTE_manufacturer_rule_{id_lang}`, `PS_ROUTE_cms_rule_{id_lang}` oder `PS_ROUTE_cms_category_rule_{id_lang}`. Diese Sprachrouten bleiben die Werte von `PURLS_ROUTE_*`. Die Basisrouten `supplier_rule` und `manufacturer_rule` bleiben `supplier/{rewrite}/` und `manufacturer/{rewrite}/`.

## Was Speichern tut

**Speichern** macht der Reihe nach:

1. Löscht die Konfigurationsnamen `PURLS_ROUTE_cms_category_rule`, `PURLS_ROUTE_cms_rule`, `PURLS_ROUTE_supplier_rule` und `PURLS_ROUTE_manufacturer_rule`. Alle Sprachwerte dieser vier Schlüssel sind weg, bevor die neuen Werte geschrieben werden.
2. Schreibt diese vier Schlüssel aus den gesendeten Feldern neu. Bei mehreren Sprachen heißen die Felder `PURLS_ROUTE_..._{id_lang}`. Bei einer Sprache nutzt das Feld die aktuelle Kontextsprache. Ein leeres Feld wird als leerer Text gespeichert.
3. Schreibt `purls_product_hash`, `PS_ROUTE_category_rule`, `PS_ROUTE_product_rule`, `purls_products`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms` und `purls_301`.

Das Speichern ersetzt das Produkt- und Kategorieschema von PrestaShop. Das Formular schreibt nicht `PS_ROUTE_supplier_rule`, `PS_ROUTE_manufacturer_rule`, `PS_ROUTE_cms_rule` oder `PS_ROUTE_cms_category_rule`. Der Text danach lautet **Ihre Einstellungen wurden aktualisiert.**

## Meldungen auf dem Formular

Die Meldung erscheint, wenn der passende Schalter aus ist (`0` oder fehlend) und `strpos` des Suchworts in der PrestaShop-Route `== false` ist. In PHP ist dieser Vergleich auch wahr, wenn das Wort an Position 0 steht. Ein Schema, das mit `{id}` beginnt, zeigt die Meldung trotzdem.

Die Prüfung liest PrestaShop-Schlüssel, nicht die Felder `PURLS_ROUTE_*`:

- Produkt-ID ist `0` und `PS_ROUTE_product_rule` enthält kein `{id}`: „Ihre Produkt-Rewrite-URL enthält nicht die Variable {id}. Sie ist erforderlich, wenn Sie die ID nicht aus der URL von Produktseiten entfernen möchten.“
- Produkt-ID ist `0` und `PS_ROUTE_product_rule` enthält kein `{-:id_product_attribute}`: „Ihre Produkt-Rewrite-URL enthält nicht die Variable {-:id_product_attribute}. Sie ist erforderlich, wenn Sie die ID des Produktattributs nicht aus der URL von Produktseiten entfernen möchten.“
- Kategorien ist `0` und `PS_ROUTE_category_rule` enthält kein `{id}`: „Ihre Kategorie-Rewrite-URL enthält nicht die Variable {id}. Sie ist erforderlich, wenn Sie die ID nicht aus der URL von Kategorieseiten entfernen möchten.“
- Hersteller ist `0` und `PS_ROUTE_manufacturer_rule` enthält kein `{id}`: „Ihre Hersteller-Rewrite-URL enthält nicht die Variable {id}. Sie ist erforderlich, wenn Sie die ID nicht aus der URL von Herstellerseiten entfernen möchten.“
- Lieferanten ist `0` und `PS_ROUTE_supplier_rule` enthält kein `{id}`: „Ihre Lieferanten-Rewrite-URL enthält nicht die Variable {id}. Sie ist erforderlich, wenn Sie die ID nicht aus der URL von Lieferantenseiten entfernen möchten.“
- CMS ist `0` und `PS_ROUTE_cms_category_rule` enthält kein `{id}`: „Ihre CMS-Kategorie-Rewrite-URL enthält nicht die Variable {id}. Sie ist erforderlich, wenn Sie die ID nicht aus der URL von Lieferantenseiten entfernen möchten.“
- CMS ist `0` und `PS_ROUTE_cms_rule` enthält kein `{id}`: „Ihre CMS-Rewrite-URL enthält nicht die Variable {id}. Sie ist erforderlich, wenn Sie die ID nicht aus der URL von Lieferantenseiten entfernen möchten.“

Die letzten beiden Texte nennen Lieferantenseiten. So steht es in `translations/de.php`.

## Mögliche Kollisionen

![Der Bildschirm ist auf Englisch. In dieser Anleitung: Mögliche Kollisionen.](https://mypresta.eu/docs/images/docs/purls-collisions.webp)

Das Panel **Mögliche Kollisionen** ist `views/purls.tpl` unter dem Formular. Es listet doppelte `link_rewrite` je aktiver Sprache für den aktuellen Shop.

Darüber steht **Fügen Sie diese URL zu Ihrer Cron-Job-Tabelle hinzu, um Kollisionen automatisch zu beheben**, dann **Bitte überprüfen Sie diese doppelten URLs unten (falls vorhanden).** Die URL ist ein Front-Office-Link des Moduls auf den Controller `cron` mit `key` = `Tools::hash('purls')`. Dieses Paket enthält keine Datei `controllers/front/cron.php`. Die Methode `cronJob()` ruft dieselbe Bereinigung für Produkte und Kategorien in jeder aktiven Sprache auf, und keine Datei dieses Pakets ruft `cronJob()` auf.

**Produkt-URLs**. Spalten: **ID**, **Name**, **Link-Rewrite**, **Vorkommen**, **Aktion**. Je Sprache hat das Menü **Alle Kollisionen beheben** die Einträge **Alle auf einmal beheben** und **Teilweise beheben**. **Produkte anzeigen** lädt die Seite mit `product_rewrite` und `id_lang` neu. Leer: **Keine Kollisionen gefunden**.

**Kategorie-URLs** hat dieselben Spalten. Die Schaltfläche heißt **Rewrite-Felder eindeutig machen**. **Kategorien anzeigen** hängt `category_rewrite` an. `getAllCategoryCollisionsRewrite()` erhält ein Argument `id_lang` und führt das SQL mit der Kontextsprache aus, nicht mit diesem Argument.

**Alle auf einmal beheben**, **Rewrite-Felder eindeutig machen** und **Teilweise beheben** rufen `makeUnique()` auf. Bei jedem doppelten Rewrite behält die erste Zeile `link_rewrite`. Jede folgende Zeile wird mit diesem Rewrite plus `-1`, `-2` und so weiter gespeichert, in der Sprache der Schaltfläche. `save()` läuft für jede Zeile der Gruppe, auch die erste. Das ändert `product_lang.link_rewrite` oder `category_lang.link_rewrite`. Die Deinstallation stellt den alten Rewrite nicht wieder her.

**Teilweise beheben** sendet eine AJAX-Anfrage je Produktzeile (`AjaxCollisions`, `id_lang`, `id_product`) und blendet die Zeile nach der Antwort aus.

Die Produktabfrage gruppiert `link_rewrite` in `product_lang` für den aktuellen Shop und die Sprache und behält Gruppen mit Anzahl ab 2. Sie filtert nicht nach Kategorie. Kategorien machen dasselbe auf `category_lang`.

## Routen, Weiterleitungen und der Produkt-Hash

Das eigene Matching in `Dispatcher::getController()` läuft, wenn PrestaShop freundliche URLs nutzt (`use_routes`), der Controller noch nicht feststeht und die Anfrage nicht aus dem Backoffice kommt. Das Override kopiert die Originalrouten und registriert sie erneut mit dem Suffix `_original`.

Diese Shop-Bildschirme sind nach dem Speichern aus Einstellungen. Die Shopsprache ist Englisch. In den Pfaden steht keine numerische ID.

![Shop auf Englisch. Pfad: men/hummingbird-printed-t-shirt.html#/color-white/size-s. Gewählt sind Size S und Color White.](https://mypresta.eu/docs/images/docs/purls-front-product.webp)

![Shop auf Englisch. Pfad: clothes/men/. Seitentitel: Men.](https://mypresta.eu/docs/images/docs/purls-front-category.webp)

![Shop auf Englisch. Pfad: manufacturer/studio-design/. Überschrift: List of products by brand Studio Design.](https://mypresta.eu/docs/images/docs/purls-front-manufacturer.webp)

![Shop auf Englisch. Pfad: info/delivery.html. Überschrift: Delivery.](https://mypresta.eu/docs/images/docs/purls-front-cms.webp)

Bei Schalter `1` setzt `Dispatcher::loadRoutes()` diese `default_routes` und ruft danach `parent::loadRoutes()` auf:

| Schalter | Routen-ID | Im Override gesetzte Regel |
| --- | --- | --- |
| `purls_products` = `1` | `product_rule` | `{category:/}{rewrite}.html` |
| `purls_products` = `2` | `product_rule` | `{category:/}{id}-{rewrite}.html` |
| `purls_products` = `3` | `product_rule` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| `purls_categories` = `1` | `category_rule` | `{parent_categories:/}{rewrite}/` |
| `purls_suppliers` = `1` | `supplier_rule` und `supplier_rule_{id_lang}` | Basis `supplier/{rewrite}/`, Sprachregel aus `PURLS_ROUTE_supplier_rule` |
| `purls_manufacturers` = `1` | `manufacturer_rule` und `manufacturer_rule_{id_lang}` | Basis `manufacturer/{rewrite}/`, Sprachregel aus `PURLS_ROUTE_manufacturer_rule` |
| `purls_cms` = `1` | `cms_rule`, `cms_category_rule` und dieselben mit `_{id_lang}` | Basis `info/{rewrite}.html` und `info/{rewrite}`, Sprachregeln aus `PURLS_ROUTE_cms_rule` und `PURLS_ROUTE_cms_category_rule` |

Die übrigen Schemata dieser Felder stehen unter Einstellungen, bei **Schemata für die Routenfelder**. Ein gespeichertes Produkt- oder Kategorieschema ersetzt die Regel in dieser Tabelle.

`Link` baut die Adresse nur bei eingeschaltetem Schalter. Sonst ruft es die PrestaShop-Elternmethode auf.

- Produkte (`purls_products` `1`, `2` oder `3`): `getProductLink()` nutzt `product_rule`. Parameter, die keine Schlüsselwörter dieser Route sind, fallen weg. `extraParams`, die keine Schlüsselwörter sind, bleiben.
- Kategorien (`purls_categories` = `1`): `getCategoryLink()` nutzt `category_rule`. Hat die Route das Schlüsselwort `parent_categories`, entsteht der Pfad aus Elternkategorien, ohne die IDs 1, 2 und die Kategorie selbst.
- Lieferanten, Hersteller, CMS-Seiten und CMS-Kategorien nutzen `supplier_rule_{id_lang}`, `manufacturer_rule_{id_lang}`, `cms_rule_{id_lang}` und `cms_category_rule_{id_lang}`.

Suche, wenn die ID nicht in der URL steht:

- Produkte in den Modi `1` und `3`: das letzte Pfadsegment ohne `.html` wird mit `product_lang.link_rewrite` verglichen. Hat der Pfad ein Kategoriesegment, wird auch `link_rewrite` der Standardkategorie verglichen. Findet das nichts, nutzt eine zweite Abfrage nur `link_rewrite`. Das Ergebnis landet in `$_GET['id_product']`.
- Kategorien: der Pfad wird mit `category_lang.link_rewrite` verglichen, mit Elternsegmenten, wenn der Pfad mehr als einen Teil hat.
- CMS-Seiten: `cms_lang.link_rewrite`, `.html` entfernt.
- CMS-Kategorien: `cms_category_lang.link_rewrite`.
- Hersteller und Lieferanten: `Tools::str2url()` des **Namens**, nicht der Spalte `link_rewrite`. Das erste Segment `supplier` lehnt die Herstellerprüfung ab. Ergeben mehrere Namen denselben Slug, bleibt die letzte Zeile der Schleife.

`purls_301` = `1` sendet `HTTP/1.1 301 Moved Permanently` nur in diesen Fällen:

- Lieferantenroute enthält `id_supplier` und das Entfernen für Lieferanten ist an: Weiterleitung auf `getSupplierLink()`.
- Herstellerroute enthält `id_manufacturer` und das Entfernen für Hersteller ist an: Weiterleitung auf `getManufacturerLink()`.
- CMS-Route enthält `id_cms`: Weiterleitung auf `getCmsLink()`. Enthält `id_cms_category`: Weiterleitung auf `getCmsCategoryLink()`. CMS-Entfernen muss an sein.
- Produktmodus `1`: die Route enthält `id_product` und `isProductLink()` gab false zurück: Weiterleitung auf `getProductLink()`. Die Modi `2` und `3` rufen diese Weiterleitung nicht auf.
- Kategorien-Entfernen ist an, die Route enthält `id_category` und `isCategoryLink()` gab false zurück: Weiterleitung auf `getCategoryLink()`.

Produktmodus `3` ruft bei nicht leerem `id_product_attribute` `isProductLinkAttribute()` auf. Die Methode setzt `$_GET['id_product']` und `$_GET['id_product_attriubte']` (so ist der Schlüssel in der Datei geschrieben). Sie setzt nicht `id_product_attribute`.

Auf der Produktseite hängt `displayHeader` `views/js/purls.js` nur an, wenn der Controller `product` ist, die Anfrage kein AJAX ist, eine Produkt-ID da ist, `purls_product_hash` `0` ist, `purls_products` `1` oder `2` ist und das Produkt Kombinationen hat. Das Skript bekommt `purls_attributes`. Der Trenner ist `PS_ATTRIBUTE_ANCHOR_SEPARATOR`, oder `-`, wenn dieser Wert fehlt oder leer ist. Das Skript liest den Hash, setzt `select` oder `radio` `group[groupId]` und sendet `prestashop.updateProduct`, wenn sich ein Feld geändert hat.

`CartController::displayAjaxProductRefresh()` baut die Produkt-URL neu und hängt `idpa` mit der Kombinations-ID an. `ProductController::init()` kopiert `idpa` nach `id_product_attribute`, wenn `id_product_attribute` fehlt. `getIdProductAttributeByRequest()` liest zuerst `idpa`.

Ist `pm_advancedsearch4` installiert, hängt `hookModuleRoutes()` drei Routen mit `/filter-{id}/s-{id_search}/{as4_sq}` an die Kategorie-, Lieferanten- und Herstellerregel. Ist das Modul nicht installiert, gibt der Hook nichts zurück.

## Hooks

`install()` registriert nur diese Hooks:

| Hook | Methode | Wirkung |
| --- | --- | --- |
| `displayHeader` | `hookdisplayHeader` | Auf der Produktseite, unter den Bedingungen oben, `views/js/purls.js` und die Map `purls_attributes`. |
| `ModuleRoutes` | `hookModuleRoutes` | Routen von Advanced Search 4, wenn das Modul installiert ist. |
| `actionAdminControllerSetMedia` | `hookactionAdminControllerSetMedia` | Leere Methode. |

## Klassen und ersetzte Dateien

PrestaShop kopiert diese Dateien bei der Installation nach `override/`:

| Datei | Klasse | Änderung |
| --- | --- | --- |
| `override/classes/Dispatcher.php` | `Dispatcher` erweitert `DispatcherCore` | `loadRoutes()`, `getController()` und `isProductLink`, `isProductLinkAttribute`, `isCategoryLink`, `isCmsLink`, `isCmsCategoryLink`, `isManufacturerLink`, `isSupplierLink`. |
| `override/classes/Link.php` | `Link` erweitert `LinkCore` | `getProductLink`, `getCategoryLink`, `getSupplierLink`, `getManufacturerLink`, `getCMSLink`, `getCMSCategoryLink`, `getPaginationLink`, `getAnchor`. Parameter, die keine Schlüsselwörter der Route sind, fallen weg. |
| `override/controllers/front/ProductController.php` | `ProductController` | Liest `idpa` in `init()`, `getIdProductAttributeByRequest()` und `getIdProductAttribute()`. |
| `override/controllers/front/CartController.php` | `CartController` | `displayAjaxProductRefresh()` hängt `idpa` an. |
| `override/controllers/front/CmsController.php` | `CmsController` | Bei `purls_cms` = `1` ermittelt `id_cms` / `id_cms_category` aus `link_rewrite`. Liest auch alte Pfade `content/{id}-{rewrite}` und `content/category/{id}-{rewrite}`. |
| `override/controllers/front/listing/CategoryController.php` | `CategoryController` | Bei `purls_categories` = `1` ermittelt `id_category` aus `category_rewrite` und dem Pfad. |
| `override/controllers/front/listing/ManufacturerController.php` | `ManufacturerController` | Bei `purls_manufacturers` = `1` ermittelt `id_manufacturer` aus `Tools::str2url(name)`. |
| `override/controllers/front/listing/SupplierController.php` | `SupplierController` | Bei `purls_suppliers` = `1` ermittelt `id_supplier` aus `Tools::str2url(name)`. |
| `override/controllers/admin/AdminProductsController.php` | `AdminProductsController` | Nur `getPreviewUrl()`. Baut den Produktlink in der Standard-Shopsprache, Kombinations-ID `0`, `force_routes` gleich `PS_REWRITING_SETTINGS`. Ein inaktives Produkt bekommt `adtoken`, `ad` und `id_employee`. |

Auf dem Produktformular gibt es kein Modul-Panel. Es gibt keine CSS-Datei. Die Konfiguration ist `views/purls.tpl` plus der PrestaShop-Formularhelfer. Das Front-Skript ist `views/js/purls.js`. In `purls.tpl` steht zusätzlich die Funktion `FixProductsCollisions`.

`Link::psversion()` und `ProductController::psversion()` zerlegen `_PS_VERSION_`. `getCategoryLink()` nutzt einen Meta-Titel-Zweig, wenn die Nebenversion 6 oder 7 ist oder die Hauptversion 8 oder höher, sonst den anderen Zweig. Kommentare in `Dispatcher.php` und `ProductController.php` nennen PrestaShop 9 und, bei einer privaten Methode, PrestaShop 1.7.

Das Modul legt keine SQL-Tabelle an. Es liest und schreibt `configuration` und liest `product_lang`, `category_lang`, `cms_lang`, `cms_category_lang`, `manufacturer`, `supplier` und die Attributtabellen für den Hash. Die Kollisionsreparatur schreibt `link_rewrite` über `Product::save()` und `Category::save()`.

Im Backoffice legt der Konstruktor `override/controllers/front/listing` mit Modus `0777` an, wenn `override/controllers/front/` existiert und `listing` nicht.

## MyPresta-Updates

![Der Bildschirm ist auf Englisch. In dieser Anleitung: MyPresta-Updates.](https://mypresta.eu/docs/images/docs/purls-updates.webp)

Das Panel **MyPresta-Updates** steht zwischen dem Formular Einstellungen und dem Panel Mögliche Kollisionen.

| Beschriftung | Element |
| --- | --- |
| Updates prüfen | Schaltfläche **Jetzt prüfen** (`submit_settings_updates_now`). Zeigt **Neue Version verfügbar!** oder **Das Modul ist auf dem neuesten Stand!** |
| Update-Benachrichtigungen | Liste `mypresta_updates`: **-- auswählen --** (`-`), **Aktivieren** (`1`), **Deaktivieren** (`0`). |
| Modulseite | Link zur Produktseite. Die Adresse steht im Abschnitt Support. |
| Speichern | `submit_settings_updates` schreibt nur `mypresta_updates`. |

Bei jeder Backoffice-Anfrage ruft der Konstruktor `checkforupdates()` auf. Fehlt `update_purls` oder ist der Wert älter als 259200 Sekunden, ruft `purlsUpdate::verify()` `http://dev.mypresta.eu/update/get.php` auf, wenn `allow_url_fopen` und `file_get_contents` verfügbar sind. Die Unix-Zeit landet in `update_purls`, der Antworttext in `updatev_purls`. Der Lizenzwert aus diesem Paket ist `nlc` (`$this->mkey`), sofern keine Datei `key.php` neben dem Modul ihn überschreibt. Dieses Paket enthält kein `key.php`.

Ist `mypresta_updates` nicht `0` und nicht false, die gespeicherte Remote-Version höher als 3.0.0 und die Anfrage kein AJAX, erscheint die Warnung **Neue Version verfügbar, besuchen Sie http://MyPresta.eu für weitere Informationen** plus **Weitere Details im Changelog**. Der Wert `0` führt die zeitgesteuerte Anfrage trotzdem aus und setzt diese Warnung nicht. Ein fehlender Schlüssel ist false, und false ist gleich `0`, also ohne Warnung.

## Installation, Deaktivieren, Aktivieren, Deinstallation

`install()` ruft `parent::install()` auf und registriert `displayHeader`, `ModuleRoutes` und `actionAdminControllerSetMedia`. Schlägt eines davon fehl, gibt die Installation false zurück. Sie schreibt keine Konfiguration und legt keine Tabelle an.

Die Datei definiert kein `enable()` und kein `disable()`. Das Deaktivieren im Backoffice führt keine Methode aus dieser Datei aus. Die Override-Klassen bleiben im Shop-Verzeichnis `override/`, weil dieses Modul kein `disable()` hat, das sie entfernt. Die drei Hooks laufen nicht, solange das Modul deaktiviert ist.

`uninstall()` gibt nur `parent::uninstall()` zurück. Das entfernt das Modul, meldet die Hooks ab und löscht die von PrestaShop installierten Override-Kopien. Es löscht keine Konfiguration. Es stellt `PS_ROUTE_product_rule` und `PS_ROUTE_category_rule` nicht wieder her. Es stellt `link_rewrite` aus den Kollisions-Schaltflächen nicht wieder her. Es bleiben: `purls_products`, `purls_product_hash`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, `purls_301`, die vier `PURLS_ROUTE_*`-Schlüssel, `mypresta_updates`, `update_purls`, `updatev_purls` und die beiden vom Formular geschriebenen `PS_ROUTE_*`-Schlüssel.

## Wenn eine Seite nicht aufgeht

- Die ID steht noch in der URL: Produkt-ID ist `0` oder der Schlüssel wurde nie gespeichert, oder das Produkt-/Kategorieschema enthält noch `{id}`. Das eigene `getController()`-Matching läuft nur bei eingeschalteten freundlichen URLs (`use_routes`).
- Eine bereinigte URL landet im Not-found-Controller: zwei Produkte oder Kategorien teilen `link_rewrite`. Das Kollisionspanel zeigt diese Zeilen. Die Reparatur-Schaltflächen ändern `link_rewrite` in der Datenbank.
- Eine alte URL mit ID leitet nicht weiter: `purls_301` ist nicht `1`, oder der Seitentyp ist Produktmodus `2` oder `3` (diese Zweige rufen `Tools::redirect` nicht auf).
- Hersteller- oder Lieferanten-URL öffnet den falschen Datensatz oder keinen: der Vergleich nutzt `Tools::str2url()` des Namens.
- Das Modul ist deaktiviert und die URLs laufen weiter durch diesen Code: die Overrides liegen bis zur Deinstallation in `override/`.
- Nach der Deinstallation sind Produkt- und Kategorieschema die zuletzt von diesem Formular gespeicherten Werte.

## Support

Produktseite: [https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html). Das Feld **Modulseite** im Update-Panel öffnet diese Adresse. Die Hilfe in den Einstellungen öffnet außerdem `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`.
