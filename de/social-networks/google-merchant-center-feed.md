---
title: "Google Merchant Center Feed - Anleitung für den Händler"
sidebar:
  label: "Google Merchant Center Feed - Anleitung für den Händler"
description: "Konfiguration der Katalogdatei, der gespeicherten Dateien und der Katalogadresse in einem Shop, der das Modul bereits hat."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google merchant center feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/google-merchant-center-feed/)
>
> ---


Der technische Name des Moduls ist `gmfeed`, Version 2.4.3. In der Modulliste steht **Google Merchant Center Feed**. Dieser Name steht in der Moduldatei und kommt nicht aus `translations/de.php`.

Die Datei `translations/de.php` speichert für die Konfigurationsseite tschechische Texte. Der Bildschirm zeigt genau diese Texte.

## 1. Wo die Bildschirme liegen

Es gibt zwei Bildschirme.

Module, dann Modul-Manager, dann **Google Merchant Center Feed**, dann Konfigurieren. Diese Seite hat ein Feld, **Zobrazit strom kategorií**.

Katalog, dann **Google Merchant Feed**. Das ist der Controller `AdminExportProductsFeedGoogle`. Die Überschrift lautet **Google Merchant Center-Feeds**. Die Reiter sind **Dashboard**, **Feeds**, **Updates** und **Create / Edit feed**. Der letzte Reiter bleibt deaktiviert, bis **Create new feed** oder ein vorhandener Feed geöffnet wird. **Create / Edit feed** und **Create new feed** stehen in `translations/de.php` nicht, der Bildschirm zeigt die englische Quelle.

Es gibt keinen Importbildschirm und keinen Block auf der Produktbearbeitung. Das Schaufenster zeichnet keinen Kasten. Die öffentliche Wirkung ist die Katalogadresse eines gespeicherten Feeds.

## 2. Was die Installation schreibt

Die Installation führt die Elterninstallation aus, registriert `actionAdminControllerSetMedia`, legt einen Reiter unter Katalog an und erzeugt die Tabellen aus Punkt 8.

Die Reiterklasse ist `AdminExportProductsFeedGoogle`. Die bei der Installation übergebene Beschriftung ist **Google Merchant Feed**. Dieselbe Beschriftung wird für jede Shop-Sprache geschrieben, die zur Installationszeit existiert.

`actionAdminControllerSetMedia` lädt die Plugins fancybox und autocomplete nur, wenn der Controller `AdminExportProductsFeedGoogle` ist.

Die Klasse hat keine Methode `enable()` und keine `disable()`.

## 3. Moduleinstellungen

![Moduleinstellungen](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt die Seite **Moduleinstellungen**. Die Datei `translations/de.php` zeigt auf diesem Bildschirm die tschechischen Texte **Nastavení modulu** und **Zobrazit strom kategorií**.

Die Legende ist **Nastavení modulu**. Der Button ist **Save**. Das einzige Feld ist **Zobrazit strom kategorií** (`pf_tree`). **Ne** ist 0. **Ano** ist 1. Fehlt der Schlüssel, ist `(int)Configuration::get('pf_tree')` gleich 0, die Liste zeigt **Ne**. **Save** hat in `translations/de.php` keinen Eintrag für diese Vorlage, der Button zeigt die englische Quelle.

**Save** sendet `submitgmfeedSettings` und schreibt `pf_tree`. Der Text danach ist **Nastavení bylo úspěšně uloženo**.

**Ano** lässt die Kategoriezuordnung auf dem Feed-Formular übergeordnete Kategorien zeigen. Die Beschreibung verlinkt `https://i.imgur.com/enzXRaJ.png`. Dieselbe Beschreibung verlinkt **Katalog > Google Merchant Feed**.

Diese Seite baut die Katalogdatei nicht.

## 4. Seite im Katalog

![Dashboard](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Reiter **Dashboard**.

![Feeds](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Reiter **Feeds**.

Öffnen Sie **Katalog > Google Merchant Feed**.

**Dashboard** zeigt die Kennzahlen aus `gms` und `gms_log`. Ohne Aufruf einer Adresse zeigt die Seite die englische Quelle **No cron or URL generations yet. Save a feed, then call its catalog URL from a scheduler.**

**Feeds** listet Zeilen aus `gms`, höchste `id_gms` zuerst. **Create new feed** öffnet das Formular. Duplizieren kopiert die gespeicherte Abfrage, entfernt `export_id_gms`, `id_gms` und `gmfeed_write_key` und hängt ` (copy)` an den Namen. Ein leerer Name startet bei **Untitled feed**. Der Text danach ist die englische Quelle **Feed duplicated. Review the copy and save if you need a different filename or URL.** Entfernen löscht diese `gms`-Zeile. Der Text ist **Feed removed.** Die Datei auf der Festplatte wird dabei nicht gelöscht.

![Updates](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Reiter **Updates**.

**Updates** ist das Formular aus `lib/updateChecker.php`. **Check now** sendet `submit_settings_updates_now`. **Save** sendet `submit_settings_updates` und schreibt `mypresta_updates`. Der Konstruktor fragt den entfernten Server, wenn `mypresta_updates` nicht 0 ist und `update_gmfeed` älter als 172800 Sekunden ist. Der Lizenzwert ohne `mkey` ist `nokey`. Eine Warnung erscheint, wenn `updatev_gmfeed` höher als 2.4.3 ist und die Anfrage kein Ajax ist.

## 5. Feed-Formular

![Create feed](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Reiter **Create feed**. Der Ausschnitt zeigt den Anfang des Formulars. Die übrigen Felder folgen darunter.

**Create feed** und **Edit feed** nutzen dasselbe Formular. Der Feed-Name ist erforderlich. **Active** **Yes** / **No** landet in `gms.active`. Ein neuer Feed ist aktiv. **Shop** speichert `gms.id_shop`. Die übrigen Felder landen in `gms.conf` als Abfragezeichenkette.

Ein fehlender Schlüssel auf einem neuen Formular erhält den Wert aus der Tabelle. Beim Bearbeiten erhält ein fehlender Schlüssel denselben Wert und liest nicht die gemeinsame Konfiguration `gm_`.

| Schlüssel | Standard eines neuen Formulars | Was der Code damit macht |
|---|---|---|
| `export_file_format` | `csv` | `csv` oder `xml`. Jede andere Endung setzt `sanitizeExportExtension` auf `csv` zurück. |
| `export_type` | `product` | `sanitizeExportType` behält nur `products` und `combinations`. Das gespeicherte `product` wird daher als `products` behandelt. |
| `export_save_file` | `0` | `0` sendet den Katalog in der Antwort. `1` schreibt eine Datei unter `/modules/gmfeed/`. |
| `export_filename` | leer | Nur beim Speichern in eine Datei. Leer wird zum Exporttyp. Zeichen außer Buchstaben, Ziffern, `_` und `-` werden entfernt. |
| `export_identification` | `id_product` | Produkt-ID, die als Katalog-ID geschrieben wird. |
| `export_delimiter` | senkrechter Strich | Trenner der CSV-Spalten. |
| `export_enclosure` | `0` | Umschließungswert für den CSV-Schreiber. |
| `export_language` | `PS_LANG_DEFAULT` | Sprache von Namen und Beschreibungen. |
| `export_currency` | `PS_CURRENCY_DEFAULT` | Währung der Preise. |
| `export_tax` | `price_tin` | Welche Preisspalte gefüllt wird. |
| `export_specific` | `1` | Weicht die Standardwährung des Shops von der Kontextwährung ab, nutzt ein Wert ungleich null im Preisschritt spezifische Preise. |
| `export_category` | `all` | Kategorien im Katalog. |
| `export_manufacturers` | `all` | Hersteller im Katalog. |
| `export_manufacturers_default` | `Default` | Markentext, wenn das Produkt keinen Hersteller hat. |
| `export_suppliers` | `all` | Lieferanten im Katalog. |
| `export_gtin` | `upc` | Welcher Produktcode als GTIN geschrieben wird. |
| `export_img` | `1` | Bildtyp, der an `getImageLink` geht. Die Liste zeigt Bildtypnamen. |
| `export_what_pictures` | `0` | `0` ist die englische Quelle **Export cover only** und entfernt die Spalte weiterer Bilder. `1` ist **Export all pictures**. |
| `export_active` | false | Geht als Nur-aktive-Flag an `Product::getProducts`. `0` ist **Export all products.** `1` ist **Export only active products**. |
| `export_instock` | false | `1` überspringt eine Zeile bei Menge 0 oder weniger. `0` ist **Export all products.** `1` ist **Export only in-stock products**. |
| `export_igid` | `0` | `0` entfernt `item_group_id`. |
| `export_gender` | `0` | `0` entfernt die Spalte Geschlecht. |
| `export_age_group` | `0` | `0` entfernt die Spalte Altersgruppe. |
| `export_size` | `0` | `0` entfernt die Spalte Größe. |
| `export_color` | `0` | `0` entfernt die Spalte Farbe. |
| `export_shipping_info` | `0` | `0` ist **Do not include**. `1` ist **Include (shipping price calculated for each item separately)**. `2` ist **Set shipping price manually**. |
| `export_product_weight` | `0` | Gewicht bleibt aus, bis dieser Wert geändert wird. |
| `export_product_type` | `0` | Produkttyp bleibt aus, bis dieser Wert geändert wird. |
| `export_removehtml` | `0` | Ein Wert ungleich `0` entfernt HTML aus der Beschreibung. |
| `export_nophoto_exclude` | `0` | `1` lässt ein Produkt ohne Foto weg. |
| `export_adult` | `0` | Adult bleibt aus, bis dieser Wert geändert wird. |
| `export_storecode` | `0` | `0` entfernt die Spalte Store code. |
| `export_country_prices` | `PS_COUNTRY_DEFAULT` | Land für den Preis. |
| `export_group_prices` | `PS_UNIDENTIFIED_GROUP` | Kundengruppe für den Preis. |
| `remember_settings` | true | Ist der gesendete Wert `1`, schreibt derselbe Speichervorgang auch `gm_{Schlüssel}` in Configuration. Schreibschlüssel, Shop, Feed-ID und Aktiv-Flag werden übersprungen. |
| `feed_active` | an bei einem neuen Feed | `gms.active`. `0` lässt die Adresse HTTP 503 und den Text `Feed is disabled` zurückgeben. |

**Save to file** beschreibt das Verzeichnis `modules/gmfeed/` und sagt, dass das Schreiben der Datei über die Adresse den Schlüssel auf diesem Formular verlangt. Der Schlüssel ist `gmfeed_write_key`, ein HMAC aus `gmfeed.write.` und der Shop-ID, mit `_COOKIE_KEY_`. Ein angemeldeter Mitarbeiter schreibt die Datei ohne diesen Schlüssel. Jede andere Person erhält `Access denied`.

Der Text nach dem Speichern ist die englische Quelle **Feed saved. Its catalog URL is ready to use.**

## 6. Katalogadresse und Datei

Die Katalogadresse ist der Front-Controller `feed` plus `?feed=` und die `gms`-ID. `gms::getFeedUrl` hängt `gmfeed_write_key` an, wenn es den Link für das Backoffice baut.

Das Öffnen lädt die gespeicherte Abfrage und ersetzt `export_`- und `gmfeed_`-Werte aus der Anfrage, außer dem Schreibschlüssel und `debug_feed`. Ein fehlender Feed oder ein `conf` mit höchstens 20 Zeichen endet mit `feed does not exists`. Ein Feed mit gesetzter `id_shop`, die nicht der aktuelle Shop ist, endet mit `Feed is not available in this store`.

`debug_feed` gibt die gespeicherten Parameter aus und schreibt keine Datei.

Der Dateiname ist das bereinigte `export_filename` plus `.csv`, `.xml` oder `.txt`. Der Pfad muss in `/modules/gmfeed/` bleiben. `.htaccess` in diesem Verzeichnis verbietet die direkte Ausführung von PHP-Dateien. `index.php` bleibt erlaubt. Den Katalog liefert der Front-Controller, nicht das Öffnen der PHP-Dateien.

Jeder Lauf schreibt `gms_log`: Zeit, Dauer, Positionszahl, Status, ob eine Datei gespeichert wurde, Dateiname, Format und Quelle `url`.

## 7. Google-Kategorien

Das Formular listet Taxonomiedateien aus `/modules/gmfeed/google/`. Eine Shop-Sprache gilt als vorhanden, wenn `google/{language_code}.txt` existiert. Dieses Paket enthält `google/en-us.txt`. Die erste Zeile dieser Datei ist `# Google_Product_Taxonomy_Version: 2015-02-19`.

Das Zuordnen einer Shop-Kategorie schreibt `pixelgoogle`: `id_google`, `id_category`, `id_lang`, `value`. **Zobrazit strom kategorií** ändert nur die Darstellung dieser Liste.

## 8. Tabellen

Die Installation erzeugt drei Tabellen, wenn sie fehlen. Vor jedem Namen steht das Shop-Präfix.

| Tabelle | Was die CREATE-Anweisung schreibt |
|---|---|
| `pixelgoogle` | `id_pixelgoogle` auto increment, Primärschlüssel, `id_google`, `id_category`, `id_lang`, `value` varchar 254. Zeichensatz `utf8`. |
| `gms` | `id_gms` auto increment, `name`, `id_shop` Standard 0, `conf` text, `active` Standard 1. Schlüssel `idtoskey` und `id_shop`. Die CREATE-Anweisung hat keinen Primärschlüssel. |
| `gms_log` | `id_gms_log` auto increment, Primärschlüssel, `id_gms`, `date_add`, `duration_ms`, `items`, `status` Standard `ok`, `save_file`, `file_name`, `format`, `source` Standard `url`. |

Das Öffnen der Katalogseite führt `gms::ensureSchema()` aus. Das ergänzt `gms.active` und `gms.id_shop`, wenn sie fehlen, erzeugt `gms_log`, wenn die Tabelle fehlt, und füllt `id_shop` 0 mit `PS_SHOP_DEFAULT`.

Gemeinsame Konfiguration, die keine Spalte ist: `pf_tree`, `gm_{Feld}` wenn das Formular sie außerhalb eines Feeds schreibt, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed`.

Dateien der Katalogseite: `views/css/admin-app.css`, `views/js/admin-app.js`, fancybox, autocomplete. Die Modulkonfiguration lädt fancybox. Das ID-Suchskript kommt aus `lib/searchTool/`.

## 9. Deinstallation

`uninstall()` löscht den Katalogreiter `AdminExportProductsFeedGoogle` und führt danach die Eltern-Deinstallation aus. Die Elternmethode entfernt das Modul und die Hook-Registrierung.

Die Methode löscht `pixelgoogle`, `gms` und `gms_log` nicht. Sie löscht `pf_tree`, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed` und die Schlüssel `gm_` nicht. Sie löscht Dateien unter `/modules/gmfeed/` nicht. Eine spätere Installation nutzt `CREATE TABLE IF NOT EXISTS`, vorhandene Zeilen bleiben.

## 10. Support

Modulseite: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).
