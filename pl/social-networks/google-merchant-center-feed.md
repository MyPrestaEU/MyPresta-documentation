---
title: "Google Merchant Center Feed - instrukcja sprzedawcy"
sidebar:
  label: "Google Merchant Center Feed - instrukcja sprzedawcy"
description: "Konfiguracja pliku katalogu, zapisanych plików i adresu katalogu w sklepie, który ma już ten moduł."
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google merchant center feed na MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/google-merchant-center-feed/)
>
> ---


Nazwa techniczna modułu to `gmfeed`, wersja 2.4.3. Na liście modułów w tym języku widać **Google Merchant Center Feed**. Ta nazwa jest wpisana w pliku modułu i nie pochodzi z `translations/pl.php`.

## 1. Gdzie są ekrany

Są dwa ekrany.

Moduły, potem Menedżer modułów, potem **Google Merchant Center Feed**, potem Konfiguruj. Na tej stronie jest jedno pole, **Pokaż drzewo kategorii**.

Katalog, potem **Google Merchant Feed**. To kontroler `AdminExportProductsFeedGoogle`. Nagłówek brzmi **Pliki danych Google Merchant Center**. Zakładki to **Pulpit**, **Pliki danych**, **Aktualizacje** oraz **Create / Edit feed**. Ostatnia zakładka zostaje wyłączona, dopóki nie otworzysz **Utwórz nowy plik danych** albo istniejącego pliku. Napis **Create / Edit feed** nie ma wpisu w `translations/pl.php`, więc ekran pokazuje źródło angielskie.

Nie ma ekranu importu ani bloku na edycji produktu. Front sklepu nie rysuje ramki. Publicznym efektem jest adres katalogu zapisanego pliku danych.

## 2. Co zapisuje instalacja

Instalacja uruchamia instalację nadrzędną, rejestruje `actionAdminControllerSetMedia`, tworzy zakładkę pod Katalogiem i tworzy tabele z punktu 8.

Klasa zakładki to `AdminExportProductsFeedGoogle`. Etykieta przekazana przy instalacji to **Google Merchant Feed**. Ten sam napis jest zapisany dla każdego języka sklepu istniejącego w chwili instalacji.

`actionAdminControllerSetMedia` ładuje wtyczki fancybox i autocomplete tylko wtedy, gdy kontroler to `AdminExportProductsFeedGoogle`.

Klasa nie ma metody `enable()` ani `disable()`.

## 3. Ustawienia modułu

![Ustawienia modułu](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

Ekran jest po angielsku. W tej instrukcji ten widok to **Ustawienia modułu**.

Legenda to **Ustawienia modułu**. Przycisk to **Save**. Jedyne pole to **Pokaż drzewo kategorii** (`pf_tree`). **Nie** to 0. **Tak** to 1. Gdy klucza nie ma, `(int)Configuration::get('pf_tree')` wynosi 0, więc lista pokazuje **Nie**. Napis **Save** nie ma wpisu pod tym szablonem w `translations/pl.php`, więc przycisk pokazuje źródło angielskie.

**Save** wysyła `submitgmfeedSettings` i zapisuje `pf_tree`. Tekst po zapisie to **Ustawienia zapisano pomyślnie**.

**Tak** sprawia, że lista parowania kategorii na formularzu pliku pokazuje kategorie nadrzędne. Opis prowadzi do `https://i.imgur.com/enzXRaJ.png`. Ten sam opis prowadzi do **Katalog > Google Merchant Feed**.

Ta strona nie buduje pliku katalogu.

## 4. Strona w Katalogu

![Pulpit](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

Ekran jest po angielsku. W tej instrukcji ta zakładka to **Pulpit**.

![Pliki danych](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Ekran jest po angielsku. W tej instrukcji ta zakładka to **Pliki danych**.

Otwórz **Katalog > Google Merchant Feed**.

**Pulpit** pokazuje **Saved feeds**, **Cron runs today**, **Runs last 7 days** i **Saved files**, o ile `translations/pl.php` nie ma tych napisów z szablonu `dashboard`. Liczby pochodzą z `gms` i `gms_log`. Gdy żaden adres nie został wywołany, strona pokazuje źródło angielskie **No cron or URL generations yet. Save a feed, then call its catalog URL from a scheduler.**

**Pliki danych** listują wiersze z `gms`, od najwyższego `id_gms`. **Utwórz nowy plik danych** otwiera formularz. Duplikat kopiuje zapisany ciąg zapytania, usuwa z niego `export_id_gms`, `id_gms` i `gmfeed_write_key` oraz dopisuje ` (copy)` do nazwy. Pusta nazwa startuje od **Untitled feed**. Tekst po duplikacie to źródło angielskie **Feed duplicated. Review the copy and save if you need a different filename or URL.** Usunięcie kasuje ten wiersz `gms`. Tekst to źródło angielskie **Feed removed.** Plik zapisany na dysku nie jest przy tym kasowany.

![Aktualizacje](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

Ekran jest po angielsku. W tej instrukcji ta zakładka to **Aktualizacje**.

**Aktualizacje** to formularz z `lib/updateChecker.php`. **Check now** wysyła `submit_settings_updates_now`. **Save** wysyła `submit_settings_updates` i zapisuje `mypresta_updates`. Konstruktor pyta zdalny serwer, gdy `mypresta_updates` nie jest 0 i `update_gmfeed` jest starsze niż 172800 sekund. Wartość licencji wysyłana przy braku `mkey` to `nokey`. Ostrzeżenie pojawia się, gdy `updatev_gmfeed` jest wyższe niż 2.4.3 i żądanie nie jest ajax.

## 5. Formularz pliku danych

![Utwórz nowy plik danych](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Ekran jest po angielsku. W tej instrukcji ten widok to **Utwórz nowy plik danych**. Zrzut pokazuje górę formularza. Pozostałe pola są niżej.

**Create feed** i **Edit feed** używają tego samego formularza. Te napisy nie mają wpisu w `translations/pl.php`, więc ekran pokazuje źródło angielskie. Nazwa pliku jest wymagana. **Active** **Yes** / **No** trafia do `gms.active`. Nowy plik jest aktywny. **Shop** zapisuje `gms.id_shop`. Pozostałe pola trafiają do `gms.conf` jako ciąg zapytania.

Brakujący klucz na nowym formularzu dostaje wartość z tabeli. Podczas edycji brakujący klucz dostaje tę samą wartość i nie czyta wspólnej konfiguracji `gm_`.

| Klucz | Domyślna wartość nowego formularza | Co robi z nią kod |
|---|---|---|
| `export_file_format` | `csv` | `csv` albo `xml`. Inne rozszerzenie `sanitizeExportExtension` sprowadza do `csv`. |
| `export_type` | `product` | `sanitizeExportType` zostawia tylko `products` i `combinations`. Zapisane `product` jest więc traktowane jako `products`. |
| `export_save_file` | `0` | `0` wysyła katalog w odpowiedzi. `1` zapisuje plik w `/modules/gmfeed/`. |
| `export_filename` | puste | Używane tylko przy zapisie do pliku. Puste staje się typem eksportu. Znaki inne niż litery, cyfry, `_` i `-` są usuwane. |
| `export_identification` | `id_product` | Identyfikator produktu zapisany jako id katalogu. |
| `export_delimiter` | pionowa kreska | Separator kolumn CSV. |
| `export_enclosure` | `0` | Wartość otaczająca przekazana do zapisu CSV. |
| `export_language` | `PS_LANG_DEFAULT` | Język nazw i opisów. |
| `export_currency` | `PS_CURRENCY_DEFAULT` | Waluta cen. |
| `export_tax` | `price_tin` | Która kolumna ceny jest wypełniana. |
| `export_specific` | `1` | Gdy waluta domyślna sklepu różni się od waluty kontekstu, wartość inna niż zero każe krokowi ceny użyć cen specyficznych. |
| `export_category` | `all` | Kategorie włączone do katalogu. |
| `export_manufacturers` | `all` | Producenci włączeni do katalogu. |
| `export_manufacturers_default` | `Default` | Tekst marki, gdy produkt nie ma producenta. |
| `export_suppliers` | `all` | Dostawcy włączeni do katalogu. |
| `export_gtin` | `upc` | Który kod produktu jest zapisany jako GTIN. |
| `export_img` | `1` | Typ obrazu przekazany do `getImageLink`. Lista pokazuje nazwy typów obrazów. |
| `export_what_pictures` | `0` | `0` to źródło **Export cover only** i usuwa kolumnę dodatkowych zdjęć. `1` to **Export all pictures**. |
| `export_active` | false | Trafia do `Product::getProducts` jako flaga tylko aktywnych. `0` to **Export all products.** `1` to **Export only active products**. |
| `export_instock` | false | `1` pomija wiersz, gdy ilość jest 0 albo mniejsza. `0` to **Export all products.** `1` to **Export only in-stock products**. |
| `export_igid` | `0` | `0` usuwa `item_group_id`. |
| `export_gender` | `0` | `0` usuwa kolumnę płci. |
| `export_age_group` | `0` | `0` usuwa kolumnę grupy wiekowej. |
| `export_size` | `0` | `0` usuwa kolumnę rozmiaru. |
| `export_color` | `0` | `0` usuwa kolumnę koloru. |
| `export_shipping_info` | `0` | `0` to **Do not include**. `1` to **Include (shipping price calculated for each item separately)**. `2` to **Set shipping price manually**. |
| `export_product_weight` | `0` | Waga zostaje wyłączona, dopóki ta wartość nie zostanie zmieniona. |
| `export_product_type` | `0` | Typ produktu zostaje wyłączony, dopóki ta wartość nie zostanie zmieniona. |
| `export_removehtml` | `0` | Wartość inna niż `0` usuwa HTML z opisu. |
| `export_nophoto_exclude` | `0` | `1` odrzuca produkt bez zdjęcia. |
| `export_adult` | `0` | Pole adult zostaje wyłączone, dopóki ta wartość nie zostanie zmieniona. |
| `export_storecode` | `0` | `0` usuwa kolumnę kodu sklepu. |
| `export_country_prices` | `PS_COUNTRY_DEFAULT` | Kraj użyty do ceny. |
| `export_group_prices` | `PS_UNIDENTIFIED_GROUP` | Grupa klientów użyta do ceny. |
| `remember_settings` | true | Gdy wysłana wartość to `1`, ten sam zapis wpisuje też `gm_{klucz}` do Configuration. Klucz zapisu, sklep, id pliku i flaga aktywności są pomijane. |
| `feed_active` | włączone dla nowego pliku | `gms.active`. `0` sprawia, że adres zwraca HTTP 503 i tekst `Feed is disabled`. |

**Save to file** opisuje katalog `modules/gmfeed/` i podaje, że zapis pliku z adresu wymaga klucza pokazanego na tym formularzu. Klucz to `gmfeed_write_key`, HMAC z `gmfeed.write.` i id sklepu, z użyciem `_COOKIE_KEY_`. Zalogowany pracownik zapisuje plik bez tego klucza. Inna osoba dostaje `Access denied`.

Tekst po zapisie to źródło angielskie **Feed saved. Its catalog URL is ready to use.**

## 6. Adres katalogu i plik

Adres katalogu to frontowy kontroler modułu `feed` oraz `?feed=` i id z `gms`. `gms::getFeedUrl` dopisuje też `gmfeed_write_key`, gdy buduje link dla zaplecza.

Otwarcie tego adresu wczytuje zapisany ciąg zapytania i podmienia wartości `export_` oraz `gmfeed_` z żądania, z wyjątkiem klucza zapisu i `debug_feed`. Brak pliku albo `conf` o długości 20 znaków lub krótszej kończy się tekstem `feed does not exists`. Plik z ustawionym `id_shop` innym niż bieżący sklep kończy się tekstem `Feed is not available in this store`.

`debug_feed` wypisuje zapisane parametry i nie zapisuje pliku.

Nazwa pliku to oczyszczone `export_filename` plus `.csv`, `.xml` albo `.txt`. Ścieżka musi zostać w `/modules/gmfeed/`. `.htaccess` w tym katalogu zabrania bezpośredniego uruchamiania plików PHP. `index.php` zostaje dozwolony. Katalog podaje kontroler frontowy, nie otwarcie plików PHP.

Każde uruchomienie wstawia `gms_log`: czas, czas trwania, liczbę pozycji, status, informację czy zapisano plik, nazwę pliku, format i źródło `url`.

## 7. Kategorie Google

Formularz listuje pliki taksonomii z `/modules/gmfeed/google/`. Język sklepu jest oznaczony jako obecny, gdy istnieje `google/{language_code}.txt`. Ten pakiet zawiera `google/en-us.txt`. Pierwsza linia tego pliku to `# Google_Product_Taxonomy_Version: 2015-02-19`.

Parowanie kategorii sklepu zapisuje `pixelgoogle`: `id_google`, `id_category`, `id_lang`, `value`. **Pokaż drzewo kategorii** zmienia tylko sposób narysowania tej listy.

## 8. Tabele

Instalacja tworzy trzy tabele, gdy ich nie ma. Przed każdą nazwą jest prefiks sklepu.

| Tabela | Co zapisuje instrukcja CREATE |
|---|---|
| `pixelgoogle` | `id_pixelgoogle` auto increment, klucz główny, `id_google`, `id_category`, `id_lang`, `value` varchar 254. Zestaw znaków `utf8`. |
| `gms` | `id_gms` auto increment, `name`, `id_shop` domyślnie 0, `conf` text, `active` domyślnie 1. Klucze `idtoskey` i `id_shop`. Instrukcja CREATE nie ma klucza głównego. |
| `gms_log` | `id_gms_log` auto increment, klucz główny, `id_gms`, `date_add`, `duration_ms`, `items`, `status` domyślnie `ok`, `save_file`, `file_name`, `format`, `source` domyślnie `url`. |

Otwarcie strony w Katalogu uruchamia `gms::ensureSchema()`. To dodaje `gms.active` i `gms.id_shop`, gdy ich nie ma, tworzy `gms_log`, gdy tabeli nie ma, i wypełnia `id_shop` 0 wartością `PS_SHOP_DEFAULT`.

Wspólna konfiguracja, która nie jest kolumną: `pf_tree`, `gm_{pole}` gdy formularz zapisuje je poza plikiem, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed`.

Zasoby strony w Katalogu: `views/css/admin-app.css`, `views/js/admin-app.js`, fancybox, autocomplete. Strona konfiguracji modułu ładuje fancybox. Skrypt wyszukiwania id pochodzi z `lib/searchTool/`.

## 9. Odinstalowanie

`uninstall()` kasuje zakładkę Katalogu `AdminExportProductsFeedGoogle`, a potem uruchamia odinstalowanie nadrzędne. Nadrzędne usuwa moduł i rejestrację hooka.

Metoda nie kasuje tabel `pixelgoogle`, `gms` ani `gms_log`. Nie kasuje `pf_tree`, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed` ani kluczy `gm_`. Nie kasuje plików zapisanych w `/modules/gmfeed/`. Kolejna instalacja używa `CREATE TABLE IF NOT EXISTS`, więc wiersze zostawione w tabelach zostają.

## 10. Pomoc

Strona modułu: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).
