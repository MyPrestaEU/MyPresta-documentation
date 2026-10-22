---
title: "Pretty Clean URLs - instrukcja sprzedawcy"
description: "Instrukcja konfiguracji i rozwiązywania problemów dla osób, które ten moduł już mają."
sidebar:
  label: "Pretty Clean URLs - instrukcja sprzedawcy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Pretty / Clean URLs PRO na MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/pretty-clean-urls-pro/)
>
> ---


Nazwa techniczna `purls`, wersja 3.0.0, nazwa w panelu: Pretty Clean URLs.

## Gdzie są ekrany

Wejdź w **Moduły > Menedżer modułów** i skonfiguruj **Pretty Clean URLs**. Strona to formularz ustawień, pod nim panel **Możliwe konflikty**, pod nim panel **Aktualizacje**. Moduł nie dodaje własnej pozycji menu, ekranu importu ani bloku na edycji produktu.

Etykiety poniżej są z `translations/pl.php`. Zdania „on documentation page of this module” nie ma w plikach tłumaczeń, więc ekran pokazuje angielskie źródło.

## Co zapisuje samo otwarcie konfiguracji

`install()` nie zapisuje tych wartości. Przy otwarciu konfiguracji `getContent()` zapisuje schemat, gdy bieżąca wartość jest pusta albo jej nie ma:

| Klucz | Zapisywana wartość |
| --- | --- |
| `PURLS_ROUTE_cms_rule` | `info/{rewrite}.html` |
| `PURLS_ROUTE_cms_category_rule` | `info/{rewrite}` |
| `PURLS_ROUTE_supplier_rule` | `supplier/{rewrite}/` |
| `PURLS_ROUTE_manufacturer_rule` | `manufacturer/{rewrite}/` |
| `PS_ROUTE_category_rule` | `{parent_categories:/}{rewrite}/` |
| `PS_ROUTE_product_rule` | `{category:/}{rewrite}.html` |

`PS_ROUTE_product_rule` i `PS_ROUTE_category_rule` to klucze PrestaShop. Gdy są puste, otwarcie tej strony podmienia je na wartości z tabeli. Przy więcej niż jednym języku cztery klucze `PURLS_ROUTE_*` są zapisywane osobno dla każdego języka. Przy jednym języku są jednym ciągiem.

## Ustawienia

![Ekran jest po angielsku. W tej instrukcji: Ustawienia.](https://mypresta.eu/docs/images/docs/purls-configure-settings.webp)

![Ekran po angielsku, po zapisie. ID produktu: ID of product + ID of attribute. Hash wyłączony. Kategorie, producenci, dostawcy i CMS włączone. Przekierowanie 301 włączone. W tej instrukcji: Ustawienia.](https://mypresta.eu/docs/images/docs/purls-configure-enabled.webp)

Legenda formularza to **Ustawienia**. Opis to **Wybierz strony dla których chcesz włączyć usuwanie ID z adresu**. Przycisk to **Zapisz** (`submitCategoryFeatured`).

`install()` nie tworzy tych kluczy. Do pierwszego zapisu `Configuration::get` zwraca false. Usuwanie ID działa tylko dla wartości z tabeli, więc brak klucza zostawia ID w adresie. Na formularzu false pokrywa się z opcją `0` (**Nie usuwaj ID** / **Wyłączone**).

| Etykieta | Klucz | Wartości |
| --- | --- | --- |
| ID produktu | `purls_products` | `0` Nie usuwaj ID. `1` Usuń id produktu + id atrybutu. `2` Usuń ID atrybutu. `3` Usuń ID produktu. |
| Hashcode a trybutami | `purls_product_hash` | `1` Włączone, `0` Wyłączone. |
| Kategorie | `purls_categories` | `1` Włączone usuwa ID z adresów stron kategorii. `0` Wyłączone. |
| Producenci | `purls_manufacturers` | `1` Włączone usuwa ID z adresów stron producentów. `0` Wyłączone. |
| Dostawcy | `purls_suppliers` | `1` Włączone usuwa ID z adresów stron dostawców. `0` Wyłączone. |
| Strony CMS | `purls_cms` | `1` Włączone usuwa ID z adresów stron CMS. `0` Wyłączone. |
| Przekierowanie 301 ze starych url | `purls_301` | Pole radio. `1` Włączone, `0` Wyłączone. Tekst: Włącz automatyczne przekierowywanie starych adresów (z ID) do nowych adresów (bez ID). |

Pomoc przy **ID produktu** każe zmienić schemat produktu:

- **ID produktu + ID atrybutu**: usuń `{id}` oraz `{-:id_product_attribute}`, gdy nie mają być w adresie.
- **Usuń ID atrybutu**: usuń `{-:id_product_attribute}`.
- **Usuń ID produktu**: usuń `{id}`. W kodzie źródłowym przy tej opcji jest też znacznik `{id_product_attribute:-}`. Tego zdania nie ma w `translations/pl.php` w całości: polski plik kończy się na usunięciu `{id}`.

Ta sama pomoc prowadzi do `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`. Tekst linku to angielskie źródło „on documentation page of this module”. Zdanie przed linkiem w polskim pliku: **Szczegóły o konfiguracji "schema of urls" znajdziesz:**.

**Hashcode a trybutami**: Włączone obcina adres produktu na znaku `#`, więc hash atrybutów nie wchodzi do adresu. Wyłączone, i tylko gdy ID produktu ma wartość `1` albo `2`, zostawia hash w postaci `#/grupa-wartość`. Tekst pomocy: opcja działa, kiedy ID atrybutu produktu jest usunięte z adresów URL. W kodzie `Link::getProductLink()` zostawia hash tylko gdy `purls_product_hash` jest `0`, a `purls_products` jest `1` albo `2`. Przy wartości `3` ta metoda zawsze obcina adres na `#`. Wartość `0` pola ID produktu nie wchodzi w tę metodę i woła metodę PrestaShop.

| Etykieta | Klucz | Pole językowe | Słowa z opisu pola |
| --- | --- | --- | --- |
| Produkty - schemat URL | `PS_ROUTE_product_rule` | Nie | `{rewrite}`, `{category}`, `{categories}`, `{id}`, `{-:id_product_attribute}` |
| Kategorie - schemat URL | `PS_ROUTE_category_rule` | Nie | `{id}`, `{rewrite}`, `{parent_categories}` |
| Dostawca - schemat URL | `PURLS_ROUTE_supplier_rule` | Tak | `{id}`, `{rewrite}` |
| Marki (producenci) - schemat URL | `PURLS_ROUTE_manufacturer_rule` | Tak | `{id}`, `{rewrite}` |
| Strony CMS - schemat URL | `PURLS_ROUTE_cms_rule` | Tak | `{categories:/}`, `{id}`, `{rewrite}` |
| Strony kategorii CMS - schemat URL | `PURLS_ROUTE_cms_category_rule` | Tak | `{id}`, `{rewrite}` |

Przy produktach i kategoriach jest tekst: **To pole jest również dostępne w Parametry > Traffic & seo (ruch & seo)**.

Przy dostawcy, markach, CMS i kategorii CMS, gdy przełącznik jest `0`, widać: **Aby edytować to pole i aby moduł z niego korzystał - musisz włączyć usuwanie numerów ID z tego typu stron**. Pole pozostaje edytowalne. Dispatcher i `Link` biorą schemat modułu tylko przy przełączniku `1`.

### Schematy pól tras

To wzorce ze strony schematów. Do pola **Produkty - schemat URL** wstaw wiersz z grupy zgodnej z **ID produktu**. `{category}` to przyjazna nazwa kategorii domyślnej. `{categories}` to przyjazne nazwy kategorii nadrzędnych połączone `/` (`Link::getProductLink()`). `{rewrite}` to `link_rewrite`. `{id}` to id produktu. `{id_product_attribute:-}` to id kombinacji, z `-` z przodu, gdy to id jest podane. Puste pole produktu dostaje `{category:/}{rewrite}.html` także przy ID produktu `2` i `3`, więc przy tych dwóch opcjach wpisz w pole jeden z ich wierszy.

| Pole | ID produktu | Schemat |
| --- | --- | --- |
| Produkty - schemat URL | `1` | `{rewrite}.html` |
| Produkty - schemat URL | `1` | `{category:/}{rewrite}.html` |
| Produkty - schemat URL | `1` | `{categories}{rewrite}.html` |
| Produkty - schemat URL | `1` | `{categories}{rewrite}` |
| Produkty - schemat URL | `2` | `{id}-{rewrite}.html` |
| Produkty - schemat URL | `2` | `{category:/}{id}-{rewrite}.html` |
| Produkty - schemat URL | `2` | `{categories}{id}-{rewrite}.html` |
| Produkty - schemat URL | `2` | `{categories}{id}-{rewrite}` |
| Produkty - schemat URL | `3` | `{id_product_attribute:-}{rewrite}.html` |
| Produkty - schemat URL | `3` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| Produkty - schemat URL | `3` | `{categories}{id_product_attribute:-}{rewrite}.html` |
| Produkty - schemat URL | `3` | `{categories}{id_product_attribute:-}{rewrite}` |

| Pole | Schemat |
| --- | --- |
| Kategorie - schemat URL | `{parent_categories:/}{rewrite}/` |
| Kategorie - schemat URL | `{rewrite}/` |
| Dostawca - schemat URL | `supplier/{rewrite}/` |
| Dostawca - schemat URL | `any-text/{rewrite}/` |
| Marki (producenci) - schemat URL | `manufacturer/{rewrite}/` |
| Marki (producenci) - schemat URL | `any-text/{rewrite}/` |
| Strony CMS - schemat URL | `info/{rewrite}.html` |
| Strony kategorii CMS - schemat URL | `info/{rewrite}` |

Puste pole kategorii dostaje `{parent_categories:/}{rewrite}/`. Drugi wiersz kategorii to alternatywa. `{parent_categories}` to przyjazne nazwy kategorii nadrzędnych połączone `/`, bez id 1, 2 i samej kategorii. Puste pole dostawcy dostaje `supplier/{rewrite}/`, puste pole marek `manufacturer/{rewrite}/`. `any-text` nie jest słowem trasy. To stały przedrostek, który wpisujesz zamiast tych słów, na przykład `marka/{rewrite}/`. Strona schematów nie podaje alternatywy dla dwóch pól CMS. Puste pola CMS dostają `info/{rewrite}.html` i `info/{rewrite}`.

`parent::loadRoutes()` czyta `PS_ROUTE_` plus id trasy. Gdy ta wartość nie jest pusta, ten ciąg jest kompilowaną regułą, więc zapisany schemat produktu albo kategorii zastępuje regułę ustawioną w `loadRoutes()`. Ten moduł nie zapisuje `PS_ROUTE_supplier_rule_{id_lang}`, `PS_ROUTE_manufacturer_rule_{id_lang}`, `PS_ROUTE_cms_rule_{id_lang}` ani `PS_ROUTE_cms_category_rule_{id_lang}`. Trasy języków zostają wartościami `PURLS_ROUTE_*`. Trasy bazowe `supplier_rule` i `manufacturer_rule` zostają `supplier/{rewrite}/` i `manufacturer/{rewrite}/`.

## Co robi Zapisz

**Zapisz** wykonuje po kolei:

1. Kasuje nazwy konfiguracji `PURLS_ROUTE_cms_category_rule`, `PURLS_ROUTE_cms_rule`, `PURLS_ROUTE_supplier_rule` i `PURLS_ROUTE_manufacturer_rule`. Wartości tych czterech kluczy dla wszystkich języków znikają, zanim zapiszą się nowe.
2. Zapisuje te cztery klucze z pól formularza. Przy kilku językach nazwy pól to `PURLS_ROUTE_..._{id_lang}`. Przy jednym języku pole ma id bieżącego języka kontekstu. Puste pole trafia do bazy jako pusty ciąg.
3. Zapisuje `purls_product_hash`, `PS_ROUTE_category_rule`, `PS_ROUTE_product_rule`, `purls_products`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms` i `purls_301`.

Zapis podmienia schemat produktu i kategorii w PrestaShop. Formularz nie zapisuje `PS_ROUTE_supplier_rule`, `PS_ROUTE_manufacturer_rule`, `PS_ROUTE_cms_rule` ani `PS_ROUTE_cms_category_rule`. Komunikat to **Ustawienia został zapisane**.

## Komunikaty na formularzu

Komunikat pojawia się, gdy dany przełącznik jest wyłączony (`0` albo brak klucza), a `strpos` szukanego fragmentu w schemacie PrestaShop jest `== false`. W PHP to porównanie jest prawdziwe także wtedy, gdy fragment stoi na pozycji 0, więc schemat zaczynający się od `{id}` i tak pokazuje komunikat.

Sprawdzenie czyta klucze PrestaShop, nie pola `PURLS_ROUTE_*`:

- ID produktu jest `0`, a w `PS_ROUTE_product_rule` nie ma `{id}`: „Schemat linku do stron produktu nie zawiera parametru {id}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.
- ID produktu jest `0`, a w `PS_ROUTE_product_rule` nie ma `{-:id_product_attribute}`: „Schemat linku do stron produktu nie zawiera parametru {-:id_product_attribute}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.
- Kategorie są `0`, a w `PS_ROUTE_category_rule` nie ma `{id}`: „Schemat linku do stron kategorii nie zawiera parametru {id}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.
- Producenci są `0`, a w `PS_ROUTE_manufacturer_rule` nie ma `{id}`: „Schemat linku do stron producenta nie zawiera parametru {id}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.
- Dostawcy są `0`, a w `PS_ROUTE_supplier_rule` nie ma `{id}`: „Schemat linku do stron dostawcy nie zawiera parametru {id}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.
- Strony CMS są `0`, a w `PS_ROUTE_cms_category_rule` nie ma `{id}`: „Schemat linku do stron kategorii CMS nie zawiera parametru {id}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.
- Strony CMS są `0`, a w `PS_ROUTE_cms_rule` nie ma `{id}`: „Schemat linku do stron CMS nie zawiera parametru {id}. Jest on wymagany gdy nie chcesz usuwać numerów ID z tego typu stron”.

## Możliwe konflikty

![Ekran jest po angielsku. W tej instrukcji: Możliwe konflikty.](https://mypresta.eu/docs/images/docs/purls-collisions.webp)

Panel **Możliwe konflikty** to szablon `views/purls.tpl` pod formularzem. Dla każdego aktywnego języka i bieżącego sklepu pokazuje powtórzone `link_rewrite`.

Tekst nad adresem to **Dodaj ten url do tablicy zadań cron aby automatycznie poprawiać ewentualne kolizje adresów**. Pod spodem są zdania **Sprawdź te zduplikowane adresy URL (jeżeli występują)** oraz **Jeżeli produkty lub kategorie z takim samym polem "link rewrite" będą miały taką samą kategorię główną lub nadrzędną wówczas może zdarzyć się, że sklep nie rozpozna produktów / kategorii prawidłowo.** Dalej: **Poniższe tabele pokazują produkty oraz kategorie które mają takie same adresy url. Jeżeli produkty będą miały taką samą kategorię główną, lub  kategorie taką samą kategorie nadrzędną - wówczas konieczna jest modyfikacja adresów url tych produktów / kategorii tak aby były unikalne**.

Adres pod pierwszym zdaniem to link frontowy modułu do kontrolera `cron` z parametrem `key` równym `Tools::hash('purls')`. W paczce nie ma pliku `controllers/front/cron.php`. Metoda `cronJob()` wywołuje tę samą naprawę dla produktów i kategorii we wszystkich aktywnych językach, a żaden plik tej paczki `cronJob()` nie woła.

**Adresy URL produktów**. Kolumny: **ID**, **Nazwa**, **Link rewrite**, **Wystąpienia**, **Akcje**. Dla języka menu **Napraw** ma **Napraw wszystkie** i **Napraw w trybie AJAX**. **Pokaż produkty** przeładowuje stronę z `product_rewrite` i `id_lang` i dopisuje pozostałe produkty z tym samym rewrite. Przy pustej liście jest **Brak kolizji**.

**Adresy URL kategorii** ma te same kolumny. Przycisk to **Napraw wszystkie**. **Pokaż kategorie** dokleja `category_rewrite`. Zapytanie `getAllCategoryCollisionsRewrite()` dostaje argument `id_lang`, a w SQL używa id języka kontekstu, nie tego argumentu.

**Napraw wszystkie** (produkty i kategorie) oraz **Napraw w trybie AJAX** wołają `makeUnique()`. Przy każdym powtórzonym rewrite pierwszy wiersz zostaje bez zmiany `link_rewrite`. Każdy następny jest zapisywany z tym rewrite plus `-1`, `-2` i dalej, w języku przycisku. `save()` leci dla każdego wiersza grupy, także pierwszego. Zmienia to `product_lang.link_rewrite` albo `category_lang.link_rewrite`. Odinstalowanie nie przywraca starego rewrite.

**Napraw w trybie AJAX** wysyła jedno żądanie na wiersz produktu (`AjaxCollisions`, `id_lang`, `id_product`) i ukrywa wiersz po odpowiedzi. Każde żądanie uruchamia `makeUnique('products', ...)` dla rewrite tego produktu.

Zapytanie produktów grupuje `link_rewrite` w `product_lang` dla bieżącego sklepu i języka i zostawia grupy o liczbie co najmniej 2. Nie filtruje po kategorii. Kategorie robią to samo na `category_lang`.

## Trasy, przekierowania i hash produktu

Własne dopasowanie w `Dispatcher::getController()` działa, gdy PrestaShop ma włączone przyjazne adresy (`use_routes`), kontroler nie jest jeszcze wybrany i żądanie nie jest z zaplecza. Nadpisanie kopiuje oryginalne trasy i rejestruje je ponownie z przyrostkiem `_original`.

Te ekrany sklepu są po zapisie z sekcji Ustawienia. Język sklepu jest angielski. W ścieżkach nie ma numeru ID.

![Ekran sklepu po angielsku. Ścieżka: men/hummingbird-printed-t-shirt.html#/color-white/size-s. Wybrane Size S i Color White.](https://mypresta.eu/docs/images/docs/purls-front-product.webp)

![Ekran sklepu po angielsku. Ścieżka: clothes/men/. Tytuł strony: Men.](https://mypresta.eu/docs/images/docs/purls-front-category.webp)

![Ekran sklepu po angielsku. Ścieżka: manufacturer/studio-design/. Nagłówek: List of products by brand Studio Design.](https://mypresta.eu/docs/images/docs/purls-front-manufacturer.webp)

![Ekran sklepu po angielsku. Ścieżka: info/delivery.html. Nagłówek: Delivery.](https://mypresta.eu/docs/images/docs/purls-front-cms.webp)

Gdy przełącznik jest `1`, `Dispatcher::loadRoutes()` ustawia poniższe `default_routes` i woła `parent::loadRoutes()`:

| Przełącznik | Id trasy | Reguła ustawiana w nadpisaniu |
| --- | --- | --- |
| `purls_products` = `1` | `product_rule` | `{category:/}{rewrite}.html` |
| `purls_products` = `2` | `product_rule` | `{category:/}{id}-{rewrite}.html` |
| `purls_products` = `3` | `product_rule` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| `purls_categories` = `1` | `category_rule` | `{parent_categories:/}{rewrite}/` |
| `purls_suppliers` = `1` | `supplier_rule` i `supplier_rule_{id_lang}` | baza `supplier/{rewrite}/`, trasa języka z `PURLS_ROUTE_supplier_rule` |
| `purls_manufacturers` = `1` | `manufacturer_rule` i `manufacturer_rule_{id_lang}` | baza `manufacturer/{rewrite}/`, trasa języka z `PURLS_ROUTE_manufacturer_rule` |
| `purls_cms` = `1` | `cms_rule`, `cms_category_rule` oraz te same z `_{id_lang}` | baza `info/{rewrite}.html` i `info/{rewrite}`, trasy języka z `PURLS_ROUTE_cms_rule` i `PURLS_ROUTE_cms_category_rule` |

Pozostałe schematy tych pól są w Ustawieniach, w **Schematy pól tras**. Zapisany schemat produktu albo kategorii zastępuje regułę z tej tabeli.

`Link` buduje adres tylko przy włączonym przełączniku. W przeciwnym razie woła metodę PrestaShop.

- Produkty (`purls_products` `1`, `2` albo `3`): `getProductLink()` używa trasy `product_rule`. Parametry, które nie są słowami tej trasy, są pomijane, więc id spoza schematu nie wchodzi do query. `extraParams`, które nie są słowami trasy, zostają.
- Kategorie (`purls_categories` = `1`): `getCategoryLink()` używa `category_rule`. Gdy trasa ma słowo `parent_categories`, ścieżka powstaje z kategorii nadrzędnych, bez id 1, 2 i samej kategorii.
- Dostawcy, producenci, strony CMS i kategorie CMS używają `supplier_rule_{id_lang}`, `manufacturer_rule_{id_lang}`, `cms_rule_{id_lang}` i `cms_category_rule_{id_lang}`.

Szukanie rekordu, gdy w adresie nie ma id:

- Produkty w trybach `1` i `3`: ostatni segment ścieżki, bez `.html`, jest porównywany z `product_lang.link_rewrite`. Gdy ścieżka ma segment kategorii, porównywany jest też `link_rewrite` kategorii domyślnej. Gdy to nic nie znajdzie, drugie zapytanie używa samego `link_rewrite`. Wynik trafia do `$_GET['id_product']`.
- Kategorie: ścieżka jest porównywana z `category_lang.link_rewrite`, z segmentami nadrzędnymi, gdy ścieżka ma więcej niż jedną część. Gdy to nic nie znajdzie, drugie zapytanie używa `link_rewrite` w bieżącym sklepie.
- Strony CMS: `cms_lang.link_rewrite`, po obcięciu `.html`.
- Kategorie CMS: `cms_category_lang.link_rewrite`.
- Producenci i dostawcy: `Tools::str2url()` od **nazwy**, nie od kolumny `link_rewrite`. Pierwszy segment `supplier` jest odrzucany przy producencie. Gdy kilka nazw daje ten sam slug, zostaje ostatni wiersz pętli.

`purls_301` = `1` wysyła `HTTP/1.1 301 Moved Permanently` tylko w tych przypadkach:

- Trasa dostawcy ma `id_supplier`, a usuwanie ID dostawców jest włączone: przekierowanie na `getSupplierLink()`.
- Trasa producenta ma `id_manufacturer`, a usuwanie ID producentów jest włączone: przekierowanie na `getManufacturerLink()`.
- Trasa CMS ma `id_cms`: przekierowanie na `getCmsLink()`. Ma `id_cms_category`: przekierowanie na `getCmsCategoryLink()`. Usuwanie ID CMS musi być włączone.
- Tryb produktu `1`: dopasowana trasa ma `id_product`, a `isProductLink()` zwróciło false: przekierowanie na `getProductLink()`. Tryby `2` i `3` tego przekierowania nie wołają.
- Usuwanie ID kategorii jest włączone, dopasowana trasa ma `id_category`, a `isCategoryLink()` zwróciło false: przekierowanie na `getCategoryLink()`.

Tryb produktu `3`, gdy dopasowanie ma niepuste `id_product_attribute`, woła `isProductLinkAttribute()`. Ta metoda ustawia `$_GET['id_product']` i `$_GET['id_product_attriubte']` (tak jest zapisany klucz w pliku). Nie ustawia `id_product_attribute`.

Na stronie produktu `displayHeader` dodaje `views/js/purls.js` tylko gdy kontroler to `product`, żądanie nie jest AJAX, jest id produktu, `purls_product_hash` jest `0`, `purls_products` jest `1` albo `2` i produkt ma kombinacje. Skrypt dostaje `purls_attributes`: klucze to segmenty `grupa-wartość` łączone `/`, wartości to `groupId|attributeId-grupa-wartość`. Separator to `PS_ATTRIBUTE_ANCHOR_SEPARATOR`, a gdy tej wartości nie ma albo jest pusta, `-`. Skrypt czyta hash, ustawia `select` albo `radio` `group[groupId]` i emituje `prestashop.updateProduct`, gdy kontrolka się zmieniła.

`CartController::displayAjaxProductRefresh()` buduje adres produktu i dokleja `idpa` z id kombinacji. `ProductController::init()` kopiuje `idpa` do `id_product_attribute`, gdy `id_product_attribute` nie ma. `getIdProductAttributeByRequest()` czyta najpierw `idpa`.

Gdy zainstalowany jest `pm_advancedsearch4`, `hookModuleRoutes()` dodaje trzy trasy z doklejonym `/filter-{id}/s-{id_search}/{as4_sq}` do reguł kategorii, dostawcy i producenta. Gdy tego modułu nie ma, hook nic nie zwraca.

## Hooki

`install()` rejestruje tylko te hooki:

| Hook | Metoda | Działanie |
| --- | --- | --- |
| `displayHeader` | `hookdisplayHeader` | Na stronie produktu, przy warunkach wyżej, dodaje `views/js/purls.js` i mapę `purls_attributes`. |
| `ModuleRoutes` | `hookModuleRoutes` | Zwraca trasy Advanced Search 4, gdy ten moduł jest zainstalowany. |
| `actionAdminControllerSetMedia` | `hookactionAdminControllerSetMedia` | Pusta metoda. |

## Klasy i podmieniane pliki

PrestaShop przy instalacji kopiuje te pliki do katalogu `override/` sklepu:

| Plik | Klasa | Co zmienia nadpisanie |
| --- | --- | --- |
| `override/classes/Dispatcher.php` | `Dispatcher` rozszerza `DispatcherCore` | `loadRoutes()`, `getController()` oraz `isProductLink`, `isProductLinkAttribute`, `isCategoryLink`, `isCmsLink`, `isCmsCategoryLink`, `isManufacturerLink`, `isSupplierLink`. |
| `override/classes/Link.php` | `Link` rozszerza `LinkCore` | `getProductLink`, `getCategoryLink`, `getSupplierLink`, `getManufacturerLink`, `getCMSLink`, `getCMSCategoryLink`, `getPaginationLink`, `getAnchor`. Pomija parametry, które nie są słowami skompilowanej trasy. |
| `override/controllers/front/ProductController.php` | `ProductController` | Czyta `idpa` w `init()`, `getIdProductAttributeByRequest()` i `getIdProductAttribute()`. |
| `override/controllers/front/CartController.php` | `CartController` | `displayAjaxProductRefresh()` dokleja `idpa`. |
| `override/controllers/front/CmsController.php` | `CmsController` | Gdy `purls_cms` jest `1`, ustala `id_cms` / `id_cms_category` z `link_rewrite`. Czyta też stare ścieżki `content/{id}-{rewrite}` i `content/category/{id}-{rewrite}`. |
| `override/controllers/front/listing/CategoryController.php` | `CategoryController` | Gdy `purls_categories` jest `1`, ustala `id_category` z `category_rewrite` i ścieżki. |
| `override/controllers/front/listing/ManufacturerController.php` | `ManufacturerController` | Gdy `purls_manufacturers` jest `1`, ustala `id_manufacturer` z `Tools::str2url(name)`. |
| `override/controllers/front/listing/SupplierController.php` | `SupplierController` | Gdy `purls_suppliers` jest `1`, ustala `id_supplier` z `Tools::str2url(name)`. |
| `override/controllers/admin/AdminProductsController.php` | `AdminProductsController` | Tylko `getPreviewUrl()`. Buduje link produktu w domyślnym języku sklepu, z id kombinacji `0` i `force_routes` równym `PS_REWRITING_SETTINGS`. Nieaktywny produkt dostaje parametry `adtoken`, `ad` i `id_employee`. |

Na formularzu produktu nie ma panelu modułu. Nie ma pliku CSS. Konfiguracja to `views/purls.tpl` oraz helper formularza PrestaShop. Skrypt sklepu to `views/js/purls.js`. W `purls.tpl` jest też funkcja `FixProductsCollisions`.

`Link::psversion()` i `ProductController::psversion()` tną `_PS_VERSION_`. `getCategoryLink()` ma jedną gałąź meta title, gdy wersja pośrednia to 6 albo 7 lub główna to 8 albo wyżej, i drugą gałąź w pozostałych przypadkach. Komentarze w `Dispatcher.php` i `ProductController.php` wymieniają PrestaShop 9, a przy jednej prywatnej metodzie PrestaShop 1.7.

Moduł nie tworzy tabeli SQL. Czyta i zapisuje `configuration` oraz czyta `product_lang`, `category_lang`, `cms_lang`, `cms_category_lang`, `manufacturer`, `supplier` i tabele atrybutów przy budowie hasha. Naprawa kolizji zapisuje `link_rewrite` przez `Product::save()` i `Category::save()`.

W zapleczu konstruktor tworzy `override/controllers/front/listing` z uprawnieniami `0777`, gdy istnieje `override/controllers/front/`, a `listing` nie istnieje.

## Aktualizacje

![Ekran jest po angielsku. W tej instrukcji: Aktualizacje.](https://mypresta.eu/docs/images/docs/purls-updates.webp)

Panel **Aktualizacje** jest między formularzem ustawień a panelem kolizji.

| Etykieta | Kontrolka |
| --- | --- |
| Sprawdź dostępność aktualizacji | Przycisk **Sprawdź** (`submit_settings_updates_now`). Wypisuje **Nowa wersja dostępna!** albo **Moduł aktualny!** |
| Informuj o aktualizacjach | Lista `mypresta_updates`: **-- wybierz --** (`-`), **Włącz** (`1`), **Wyłącz** (`0`). |
| Strona modułu | Link do strony produktu. Adres jest w sekcji wsparcia. |
| Zapisz | `submit_settings_updates` zapisuje tylko `mypresta_updates`. |

Przy każdym żądaniu zaplecza konstruktor woła `checkforupdates()`. Gdy `update_purls` nie istnieje albo ma więcej niż 259200 sekund, `purlsUpdate::verify()` woła `http://dev.mypresta.eu/update/get.php`, o ile są `allow_url_fopen` i `file_get_contents`. Czas Unix zapisuje w `update_purls`, a treść odpowiedzi w `updatev_purls`. Wartość licencji z tej paczki to `nlc` (`$this->mkey`), chyba że plik `key.php` obok modułu ją nadpisze. Tej paczki plik `key.php` nie zawiera.

Gdy `mypresta_updates` nie jest `0` i nie jest false, zapisana wersja zdalna jest wyższa niż 3.0.0, a żądanie nie jest AJAX, zaplecze dostaje ostrzeżenie **Nowa wersja jest dostępna! Sprawdź stronę MyPresta.eu!** oraz **Więcej w changelogu**. Wartość `0` i tak wykonuje zapytanie po czasie i nie dodaje tego ostrzeżenia. Brak klucza to false, a false równa się `0`, więc brak klucza idzie gałęzią bez ostrzeżenia.

## Instalacja, wyłączenie, włączenie, odinstalowanie

`install()` woła `parent::install()` i rejestruje `displayHeader`, `ModuleRoutes` oraz `actionAdminControllerSetMedia`. Gdy któreś z tego się nie uda, instalacja zwraca false. Nie wstawia wartości konfiguracji i nie tworzy tabeli.

Plik nie definiuje `enable()` ani `disable()`. Wyłączenie modułu w panelu nie uruchamia metody z tego pliku. Klasy nadpisań zostają w katalogu `override/` sklepu, bo ten moduł nie ma `disable()`, które by je usuwało. Trzy hooki nie są wykonywane, gdy moduł jest wyłączony.

`uninstall()` zwraca wyłącznie `parent::uninstall()`. To usuwa moduł, wyrejestrowuje hooki i usuwa kopie nadpisań wgrane przez PrestaShop. Nie kasuje konfiguracji. Nie przywraca `PS_ROUTE_product_rule` ani `PS_ROUTE_category_rule`. Nie przywraca `link_rewrite` zmienionego przyciskami kolizji. Zostają klucze: `purls_products`, `purls_product_hash`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, `purls_301`, cztery klucze `PURLS_ROUTE_*`, `mypresta_updates`, `update_purls`, `updatev_purls` oraz dwa klucze `PS_ROUTE_*` zapisane formularzem.

## Gdy strona się nie otwiera

- ID nadal jest w adresie: ID produktu jest `0` albo klucz nie został zapisany, albo schemat produktu/kategorii nadal zawiera `{id}`. Własne dopasowanie `getController()` działa tylko przy włączonych przyjaznych adresach (`use_routes`).
- Czysty adres trafia w kontroler „nie znaleziono”: dwa produkty albo dwie kategorie mają ten sam `link_rewrite`. Panel kolizji pokazuje te wiersze. Przyciski naprawy zmieniają `link_rewrite` w bazie.
- Stary adres z id nie przekierowuje: `purls_301` nie jest `1` albo typ strony to produkt w trybie `2` albo `3` (te gałęzie nie wołają `Tools::redirect`).
- Adres producenta albo dostawcy otwiera zły rekord albo żaden: dopasowanie używa `Tools::str2url()` od nazwy.
- Moduł jest wyłączony, a adresy nadal idą przez ten kod: nadpisania są w `override/` do czasu odinstalowania.
- Po odinstalowaniu schemat produktu i kategorii to wartości ostatnio zapisane tym formularzem.

## Wsparcie

Strona produktu: [https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html). Pole **Strona modułu** w panelu aktualizacji otwiera ten adres. Pomoc w ustawieniach otwiera też `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`.
