---
title: "HTML Box Pro - instrukcja sprzedawcy"
sidebar:
  label: "HTML Box Pro - instrukcja sprzedawcy"
description: "Konfiguracja boksów HTML, pozycji hooków i warunków widoczności dla sklepu, który ma już ten moduł."
---
> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł HTML Box Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/html-box-pro/)
>
> ---



Nazwa techniczna modułu to `htmlboxpro`, wersja 4.0.5. W tym języku lista modułów pokazuje **HTML Box Pro**.

## 1. Gdzie są ekrany

Moduły, potem Menedżer modułów, potem moduł **HTML Box Pro**, potem Konfiguruj. Strona to konfiguracja modułu (`configure=htmlboxpro`).

Pasek pod tytułem ma dwa przyciski: **Ustawienia** i **Boxy**. **Ustawienia** zapisują `hbp_lasttab` = 1. **Boxy** zapisują `hbp_lasttab` = 2. Gdy klucza nie ma, otwarcie strony zapisuje 1, więc pierwszy widok to **Ustawienia**.

Na tym samym pasku jest **Pomoc**. Otwiera `https://mypresta.eu/contact.html` w nowej karcie. **Aktualizacje** otwierają stronę modułu w MyPresta w nowej karcie. Sprawdzenie wersji jest panelem na dole **Ustawień**, nie tym przyciskiem.

Nie ma ekranu importu i nie ma bloku na edycji produktu. Bok na sklepie pojawia się dopiero wtedy, gdy hook jest włączony, blok ma **Aktywny** i przechodzi filtry opisane niżej.

Gdy `firsttime_hbp` nie jest 1, strona pokazuje alert z adresem `https://www.youtube.com/watch?v=uxzhSr5TrF4`. Zamknięcie wysyła `firsttime_hbp` = 1 i alert nie wraca.

## 2. Co zapisuje instalacja

Instalacja uruchamia instalację rodzica, tworzy tabele, zapisuje `hbp_notinyjs` = 1 i rejestruje `actionAdminControllerSetMedia` oraz każdy hook z listy niżej.

Nie włącza tych hooków. Hook wypisuje boksy tylko wtedy, gdy klucz konfiguracji `hbp_` plus nazwa hooka jest równy 1. Dopóki pole na **Boxach** nie zostanie zapisane, klucza nie ma i hook zwraca pustkę.

Otwarcie konfiguracji zawsze sprawdza kolumny i dopisuje brakujące kolumny w `hbp_block`. Istniejące wiersze zostają.

## 3. Ustawienia

![Ekran w języku angielskim. Settings to Ustawienia. Global module settings to Ustawienia globalne. Updates notifications to Informuj o nowej wersji.](https://mypresta.eu/docs/images/docs/htmlboxpro-settings.webp)

Nagłówek to **Ustawienia globalne**. Przycisk to **Zapisz**. Każdy przełącznik to **On** (1) albo **Off** (0). W pliku `translations/pl.php` te dwa słowa są zapisane jako On i Off.

| Etykieta na ekranie | Klucz | Po instalacji |
| --- | --- | --- |
| Wykorzystaj rozszerzony edytor w module | `hbp_tiny` | brak klucza; formularz pokazuje **Off** |
| Zapobiegnij usuwaniu adresu domeny z linków do obrazków | `hbp_forceurls` | brak klucza; formularz pokazuje **Off** |
| Nie duplikuj bloków na stronie produktu podczas zapytań ajax | `hbp_noajax` | brak klucza; formularz pokazuje **Off** |
| Nie ładuj bibliotek tinyMCE | `hbp_notinyjs` | 1, czyli **On** |

**Zapisz** wysyła nazwy czterech przełączników. Moduł zapisuje każdą wysłaną wartość. `hbp_tiny` = 1 ładuje na tej stronie `views/js/tinymce16.inc.js`. Ten sam przełącznik razem z `hbp_forceurls` = 1 ładuje zamiast tego `views/js/tinymce16-force-urls.inc.js`. `hbp_tiny` = 0 ładuje plik sklepu `js/admin/tinymce.inc.js` i woła `tinySetup()`. `hbp_notinyjs` = 1 pomija `js/tiny_mce/tinymce.min.js`. Strona i tak dołącza `js/tiny_mce/tiny_mce.js`, `views/js/script.js` i `views/css/styles.css`.

`hbp_noajax` = 1 sprawia, że `generateHookContents` zwraca pustkę, gdy żądanie ma `ajax` = 1 i `action` = refresh. Inne żądania nadal wypisują boksy.

Pod przełącznikami strona dokleja panel aktualizacji z `checkforupdates`. Lista **Informuj o nowej wersji** ma `-- select --`, **Włącz** (1) i **Wyłącz** (0). **Sprawdź teraz** to przycisk `submit_settings_updates_now`. **Zapisz** w tym panelu to `submit_settings_updates` i zapisuje tylko `mypresta_updates`.

Konstruktor modułu pyta serwer zdalny, gdy `mypresta_updates` nie jest 0 albo gdy klucza nie ma (`Configuration::get` zwraca false), a `update_htmlboxpro` jest starszy niż 259200 sekund. Zapytanie idzie, gdy włączone jest `allow_url_fopen`. Wartość licencji wysyłana przez tę paczkę to `nlc`. Ostrzeżenie pojawia się, gdy zwrócona wersja jest wyższa niż 4.0.5 i żądanie nie jest ajax. **Wyłącz** (0) nadal wchodzi w gałąź z czasem; warunek ostrzeżenia jest ten z tej gałęzi.

## 4. Boxy

![Ekran w języku angielskim. Boxes to Boxy. Default positions to Standardowe hooki. Search hooks nie ma tłumaczenia w translations/pl.php, więc ekran pokazuje to angielskie źródło.](https://mypresta.eu/docs/images/docs/htmlboxpro-boxes.webp)

**Boxy** to dwie kolumny. Tytuł lewej to **Standardowe hooki**. Nad wierszami jest pole szukania. Placeholder **Search hooks** nie ma wpisu w `translations/pl.php`, więc ekran pokazuje to angielskie źródło. **Własne hooki** to panel pod tą listą, w tej samej lewej kolumnie. Prawa kolumna to bloki wybranego hooka albo pusty stan. Główna kolumna zaczyna się od nagłówka **No box selected** i zdania **Wybierz z listy po lewej stronie blok do edycji, lub utwórz nowy**. Nagłówka **No box selected** nie ma w `translations/pl.php`, więc ekran pokazuje to angielskie źródło. Rozwinięty hook bez bloków pokazuje **No boxes in this position yet**. Tego ciągu też nie ma w pliku tłumaczenia.

Każdy standardowy hook to wiersz: pole wyboru, nazwa hooka i przycisk dodania boksu. Nazwa hooka prowadzi do `https://mypresta.eu/prestashop/hook/` plus nazwa małymi literami. Pole wysyła `togglehook`. Zaznaczenie zapisuje `hbp_{hook}` = 1 i woła `registerHook` jeszcze raz. Odznaczenie nie wysyła `status`, więc klucz staje się 0. Wyłączenie hooka nie wyrejestrowuje go. Tekst sukcesu to **WIdczność hooka zmieniona poprawnie** (tak jest zapisane w pliku tłumaczenia, z wielkim I).

Wiersz bloku ma nazwę wewnętrzną albo **brak nazwy własnej bloku**, gdy nazwa jest pusta. Przyciski to **Edytuj ten blok**, **Zduplikuj ten blok** i **Usuń ten blok**. Sukces przełącznika aktywności to **Widoczność bloku zmieniona poprawnie**. Przeciągnięcie wiersza wysyła `action=updateSlidesPosition` i `elements{hook}[]` oraz zapisuje `hbp_block.position`. Zakładka ładuje jQuery UI sortable. Pusty hook pokazuje **brak zdefiniowanych bloków**. W multisklepie wiersz może pokazać **w tym sklepie**.

**Zduplikuj ten blok** kopiuje blok i dokleja z przodu nazwy `[duplikat] `. Tekst sukcesu to **Blok zduplikowany poprawnie**. **Usuń ten blok** kasuje wiersz przez model obiektu. Tekst sukcesu to **Blok został usunięty**. Przełącznik aktywności na liście puszcza `smart_clean` na treści każdego języka, zapisuje blok i ustawia `active` zapytaniem SQL.

## 5. Dodawanie i edycja bloku

![Ekran w języku angielskim. Create new block to Utwórz nowy blok. Contents to Treść. Name to Nazwa. Smarty templates manager to Zarządzanie szablonami smarty. Placement nie ma tłumaczenia.](https://mypresta.eu/docs/images/docs/htmlboxpro-block-form.webp)

Dodanie boksu otwiera formularz **Utwórz nowy blok**. Edycja otwiera **Edytuj istniejący blok**. Przycisk to **Zapisz**. Dodanie wysyła `submitAddNewHbox`. Edycja wysyła `submitEditHbox`. Tekst dodania to **Blok został utworzony poprawnie**. Tekst zapisu to **Blok został zapisany poprawnie**.

Treść każdego języka sklepu ląduje w `hbp_block_lang.body`. Przed zapisem moduł wykonuje `addslashes(smart_clean(...))`. `smart_clean` zwija powtórzony znak białej spacji do jednej i obcina końce. Ostatnie podstawienie w `prepare()` przepisuje `\'`, `\\` i `\"`. Wcześniejsze linie w `prepare()` biorą oryginalny ciąg i nie zmieniają zwracanej wartości. Funkcja nie usuwa znaczników HTML. To samo czyszczenie leci ponownie, gdy przełącznik na liście zmienia aktywność.

Etykiety pól formularza są w `translations/pl.php`. Nagłówek sekcji produktów to **Produkty**. **Placement**, **Pages**, **Cart**, **Customers** i **Schedule** nie mają wpisu w tym pliku, więc ekran pokazuje to angielskie źródło.

| Sekcja | Co robią pola |
| --- | --- |
| Treść | **Treść** (`hbp_body`, osobno dla każdego języka) i **Nazwa** (`hbp_name`, 150 znaków). Przełącznik edytora w `views/js/script.js` woła `tinyMCE.execCommand('mceToggleEditor')` dla pola tego języka. Pod edytorem jest przycisk **Zarządzanie szablonami smarty**. Otwiera menedżer szablonów z `lib/smartyTemplatesManager/`. |
| Placement | **Shop**, **Position** (hook z listy, `hbp_hook`), **Active** (`hbp_active`, w tabeli domyślnie 0, dopóki zapis nie ustawi 1), **Only on secured (SSL) pages** (`hbp_bssl`), **Active on mobile devices**, **Active on tablet devices**, **Active on PC devices**. Brak wartości urządzenia zapisuje się jako 1. Polskie etykiety tych pól są w `translations/pl.php`. |
| Pages | Strona główna, promocje, potwierdzenie zamówienia, kategoria, kategoria z podkategoriami, wykluczone kategorie, kategoria CMS, strona CMS, strona producenta, dokładny URL i słowa wyszukiwania. Identyfikatory są po przecinku. Pole szukania przy identyfikatorze to narzędzie wyszukiwania modułu (`ajax=1` i `searchType`). |
| Products | Włączenie albo wykluczenie id produktów, wszystkich kart produktu, ceny specjalnej, braku stanu, możliwości zakupu, braku możliwości zakupu, stanu magazynowego, minimalnej i maksymalnej wartości, kategorii produktu, producenta, dostawcy i wartości cechy. |
| Cart | Bok tylko wtedy, gdy koszyk zawiera albo nie zawiera podanych id kategorii lub id produktów. |
| Customers | **All users** (0), **Logged only** (1), **Unlogged only** (2) w `hbp_logged`. Polskie ciągi tych trzech opcji są w `translations/pl.php`. **Show for all groups** i pola grup idą do `hbp_cgroup` jako lista po przecinku. **Hide for (users' groups)** to `hbp_hcgroup`. Geolokalizacja i kraj adresu dostawy są w tej sekcji. |
| Schedule | Waluta, data od / data do, dni tygodnia oraz godzina od / godzina do. |

Pola dni tygodnia wołają tłumaczenie z domeną `forms` (`Sunday` do `Saturday`). Pliki `translations/*.php` trzymają te słowa w domenie `htmlboxpro`, nie `forms`. Ekran pokazuje angielskie źródło: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday.

Tekst geolokalizacji wskazuje `https://mypresta.eu/prestashop-17/geolite2-city-geolocation-download.html` i katalog `/app/Resources/geoip/`. Ten sam tekst mówi, że geolokalizacja nie działa na localhost. Wybrane kraje lądują w `selected_geoip`, rozdzielone średnikiem. Kraje adresu dostawy lądują w `delivery_address_selected`, rozdzielone średnikiem. To inny przełącznik niż geolokalizacja.

## 6. Kiedy sklep ukrywa blok

`generateHookContents` ładuje bloki z `active` = 1 dla bieżącego języka i bieżącego hooka, sortowane po `position`. Gdy multisklep jest włączony, kolumna `shop` musi być id bieżącego sklepu albo 0. Szablon `html.tpl` ukrywa treść, gdy którykolwiek warunek niżej nie pasuje. Przełącznik zostawiony na **Off** nie stosuje tej reguły.

| Włączony warunek | Treść jest ukryta, gdy |
| --- | --- |
| Tylko strona główna | kontroler nie jest `index` |
| Zakres dat | dziś jest przed datą od albo po dacie do (`Y-m-d`) |
| Słowa wyszukiwania | fraza nie jest jednym ze słów po przecinku |
| Tylko strony SSL | `$_SERVER['HTTPS']` nie jest `on` |
| Tylko zalogowani | klient nie jest zalogowany |
| Tylko niezalogowani | klient jest zalogowany |
| Tylko wybrane karty produktu | id produktu nie jest na liście. Pusty pierwszy element listy zostawia blok, gdy id produktu jest w żądaniu |
| Produkt bez stanu | wartość stanu użyta w szablonie jest większa niż 0 |
| Produkt na stanie | ta wartość stanu nie jest większa niż 0 |
| Brak możliwości zakupu / możliwość zakupu | wartość `oos` produktu nie pasuje do reguły deny albo allow w `html.tpl` |
| Cena specjalna albo jej brak | `hook_params.product` nie ma pasującej ceny specjalnej |
| Wybrane kategorie | kontroler nie jest kontrolerem kategorii albo id nie jest wybrane |
| Kategorie i podkategorie | kategoria nie jest wybrana i nie jest dzieckiem według `htmlboxpro::checkIfChildren` |
| Kategoria CMS, strona CMS, strona producenta | bieżące id nie jest na liście albo kontroler jest inną stroną |
| Wybrany URL | `htmlboxpro::currentPageURL()` nie jest na zapisanej liście. Porównanie wycina parametr `rand=` |
| Produkt w kategorii | kategorie produktu nie przecinają się z listą |
| Cecha | na produkcie nie ma wybranej wartości cechy |
| Potwierdzenie zamówienia | kontroler nie jest `orderconfirmation` |
| Producent albo dostawca produktu | producent albo dostawca produktu nie jest wybrany |
| Koszyk: kategoria albo produkt, zawiera albo nie zawiera | koszyk nie pasuje do listy. PHP w `get_blocks` usuwa blok przed szablonem dla tych czterech filtrów |
| Ukryj dla grupy | grupa klienta pasuje do `hbp_hcgroup`. Grupy 1 i 2 są porównywane z grupą domyślną. Inna grupa ukrywa blok, gdy jest wśród grup klienta |
| Urządzenie | `Context::getDevice()` jest 1 i PC jest wyłączony; 2 i tablet jest wyłączony; 4 i telefon jest wyłączony |
| Min. / maks. wartość produktu | przeliczona cena jest poza kwotą albo hook nie ma produktu |
| Dni tygodnia | `hbp_daytype_on` jest 1 i dzisiejsze `%w` nie jest na liście |
| Waluta | `hbp_currency_on` jest 1 i id waluty nie jest `hbp_currency` |
| Adres dostawy | kraj dostawy nie jest w `delivery_address_selected` |
| Geolokalizacja | `hbp_geoip` jest 1 i rozpoznany kraj nie jest w `selected_geoip` |
| Wykluczone produkty, wszystkie karty produktu, wykluczone kategorie | bieżący produkt albo kategoria jest wykluczony |

Filtr godzin działa w PHP, przed szablonem. Gdy `hbp_tim` jest 1, `timfrom` i `timto` są porównywane z `date("H:i:s")` po usunięciu dwukropków. `timto` przechodzi przez `ltrim` z maską znaków `0`, więc z tej granicy znikają zera z lewej. Blok poza oknem wypada z listy.

## 7. Znaczniki w treści boksu

Podstawianie działa, gdy żądanie ma `controller` i nie jest to `AdminModules`. Znacznik, który nie został wypełniony, na końcu staje się pustym ciągiem. Wyjątkiem jest `{current_url}`.

| Znacznik | Kiedy jest wypełniony |
| --- | --- |
| `{currency_iso}` | jest waluta; wartość to kod ISO |
| `{id_lang}` | zawsze w tej gałęzi; wartość to kod ISO języka, nie numeryczne id |
| `{id_customer}`, `{email_customer}`, `{customer_firstname}`, `{customer_lastname}` | klient jest zalogowany |
| `{id_product}`, `{id_product_attribute}`, `{product_name}`, `{product_ean13}`, `{product_isbn}`, `{manufacturer_name}` | kontroler to `product` albo hook dostał `product` |
| `{product_price_tax_incl}`, `{product_price_tax_excl}` | karta produktu; kwota sformatowana helperem cen modułu |
| `{product_price_tax_incl_no_currency}`, `{product_price_tax_excl_no_currency}` | te same kwoty bez znaku waluty |
| `{id_category}`, `{name_category}`, `{path_array_category}` | w żądaniu jest id kategorii |
| `{cart_products_id}`, `{cart_total}`, `{cart_total_with_currency}` | jest koszyk |
| `{order_id}`, `{order_customer_email}`, `{order_currency_iso_code}`, `{order_total_paid}`, `{order_total_paid_tax_excl}`, `{order_total_paid_tax_incl}`, `{order_total_products_tax_included}`, `{order_total_products_tax_excluded}`, `{order_products_id}`, `{order_products_id_google}`, `{order_delivery_date}`, `{order_delivery_country}` | gałąź potwierdzenia zamówienia ma id zamówienia |
| `{current_url}` | każde żądanie, po gałęzi wyżej. Schemat, host i URI |
| `{HOOK:HookName}` | `Hook::exec` tej nazwy, z wyjątkiem sytuacji, gdy nazwa jest hookiem, który właśnie rysuje ten boks — wtedy znacznik jest pusty |
| `{HOOK:HookName:moduleName}` | `Hook::exec` ograniczone do id tego modułu |
| `{smartyTemplate:name}` | szablon z `loadSmartyTemplateFromManager` |

`{shop_name}` dostaje nazwę sklepu, a potem przebieg czyszczący zamienia `{shop_name}` na pusty ciąg. Znacznik nie zostaje jako nazwa sklepu. `{id_product_attribute}` jest pusty, gdy id atrybutu jest 0.

## 8. Własne pozycje

![Ekran w języku angielskim. Custom positions to Własne hooki. Add support of new hook to Dodaj nowy hook do modułu. Hook name to Nazwa hooka. Add new hook to Dodaj nowy hook. regenerate now! to Wygeneruj na nowo.](https://mypresta.eu/docs/images/docs/htmlboxpro-custom-hooks.webp)

**Własne hooki** listują wiersze z `hbp_customhook`. Nagłówek nad polem to **Dodaj nowy hook do modułu**. **Dodaj nowy hook** czyta **Nazwa hooka**. Zapisana nazwa zostawia tylko litery i cyfry (`preg_replace("/[^\da-z]/i", '')`). Gdy sklep nie ma hooka o tej nazwie, moduł tworzy wiersz `Hook` z `live_edit` 1, `position` 1, tytułem równym nazwie i opisem `Custom hook created with usage of HTML BOX PRO module`. Wstawia `hbp_customhook`, gdy wiersza nie ma, przepisuje `htmlboxpro.php` i rejestruje hook.

Gdy hook już jest i metoda `hook{Name}` już jest w `htmlboxpro.php`, strona pokazuje **Hook istnieje już w bazie sklepu** i nie dodaje kolejnego wiersza. Gdy hook jest, a metody nie ma, moduł i tak przepisuje plik i rejestruje hook.

**Wygeneruj na nowo** wysyła `hbp_rh_submit`. Ostrzeżenie przy przycisku to **Skorzystaj z tej opcji w razie problemów z własnymi hookami aby przebudować główny plik modułu**. Przepisanie zamienia fragment `htmlboxpro.php` między znacznikami `//~~explode~~//` na jedną metodę na hook: `hook{Name}` zwraca `generateHookContents("{Name}", $params)`. Plik musi być zapisywalny. Tekst błędu: **Nie można nadpisać głównego pliku modułu. Proszę sprawdzić uprawnienia do pliku /modules/htmlboxpro/htmlboxpro.php**. Tekst sukcesu: **Główny plik modułu został przebudowany poprawnie.**

Przycisk **Remove hook** pyta **Remove this custom hook?** Tych dwóch ciągów nie ma w `translations/pl.php`, więc ekran pokazuje to angielskie źródło. Akcja kasuje wiersz `hbp_customhook` i, gdy id hooka w sklepie istnieje, kasuje ten `Hook`, potem przepisuje plik.

Link **Jak wykorzystywać własne hooki?** otwiera `https://mypresta.eu/en/art/news/html-content-box-custom-hooks.html`. Na formularzu dodawania i edycji blok na własnym hooku pokazuje **This block uses custom hook** oraz dwa fragmenty:

`{hook::exec('HookName') nofilter}`

`{hook h='HookName' product=$product}`

Drugi fragment jest opisany dla listy produktów.

## 9. Hooki rejestrowane przy instalacji

`actionAdminControllerSetMedia` dodaje wtyczkę jQuery autocomplete tylko wtedy, gdy `configure` to `htmlboxpro`. Nie wypisuje boksu.

Te hooki wołają `generateHookContents` z nazwą hooka. Wypisanie nadal zależy od `hbp_{hook}` = 1 i od aktywnego bloku:

`displayHeader`, `displayBanner`, `displayNav1`, `displayNav2`, `displayNavFullWidth`, `displayTop`, `displayHome`, `displayFooterBefore`, `displayFooter`, `displayFooterAfter`, `displayMyAccountBlock`, `displayBeforeBodyClosingTag`, `displayLeftColumn`, `displayLeftColumnProduct`, `displayRightColumn`, `displayRightColumnProduct`, `displayOrderConfirmation`, `displayCustomerAccount`, `displayCustomerAccountForm`, `displayProductAdditionalInfo`, `displayReassurance`, `displayFooterProduct`, `displayAfterProductThumbs`, `displayProductListReviews`, `actionProductOutOfStock`, `displayShoppingCart`, `displayCartExtraProductActions`, `displayShoppingCartFooter`, `displayExpressCheckout`, `displayCustomerLoginFormAfter`, `displayBeforeCarrier`, `displayAfterCarrier`, `displayPaymentTop`, `displayPaymentByBinaries`.

`displayHeader` nie dokleja pliku CSS ani JS na sklepie. Wypisuje boksy tego hooka. Sklep nie dostaje własnego arkusza modułu. HTML, CSS i JavaScript to treść zapisana przez sprzedawcę.

`registerHook` używa metody rodzica, gdy `hook{Name}` już istnieje. W przeciwnym razie wstawia wiersz `Hook`, jeśli go trzeba, i wstawia `hook_module`.

## 10. Tabele i pliki

Instalacja tworzy trzy tabele, jeśli ich nie ma, silnik InnoDB, zestaw znaków `utf8_general_ci`. Przed nazwą jest prefiks sklepu.

| Tabela | Kolumny ze zdania CREATE |
| --- | --- |
| `hbp_block` | `id` (auto increment, klucz główny), `position` domyślnie 1, `hook` varchar(50), `active` domyślnie 0, `logged` domyślnie 0, `name` varchar(150), indeks `indek1` |
| `hbp_customhook` | `id`, `hook` varchar(70) |
| `hbp_block_lang` | `id`, `id_lang`, `body` text. Zdanie CREATE nie ma klucza głównego |

Model `models/hbox.php` mapuje `hbp_block`, a `body` jest polem wielojęzycznym. Następne otwarcie konfiguracji dopisuje kolumny filtrów: `bssl`, `shop` (domyślnie 1), flagi stron i produktów, kolumny tekstowe wybranych id, `datefrom`, `dateto`, `timfrom`, `timto`, `cgroup` (zmieniane na varchar 250), `hcgroup`, `onmobile`, `ontablet`, `onpc` (domyślnie 1), pola cen, `daytype`, `currency`, `geoip` oraz kolumny koszyka i dostawy. `inconsistency()` poszerza też `hook` do varchar(255).

Inne pliki zaplecza: `views/templates/hook/html.tpl` to treść na sklepie, `views/templates/admin/_configure/helpers/form/form.tpl` podmienia formularz helpera tego modułu, `lib/searchTool/` to szukanie id, `lib/smartyTemplatesManager/` obsługuje `{smartyTemplate:name}`, `lib/prestashop9compatibility.php` to helper wyświetlania ceny. `key.php` jest opcjonalny i nie ma go w tej paczce. Licencja aktualizacji w `checkforupdates` to literał `nlc`.

Klucze konfiguracji, które nie są kolumnami: `hbp_notinyjs`, `hbp_tiny`, `hbp_forceurls`, `hbp_noajax`, `hbp_lasttab`, `firsttime_hbp`, `hbp_{hookname}`, `mypresta_updates`, `update_htmlboxpro`, `updatev_htmlboxpro`.

## 11. Wyłączenie, włączenie, odinstalowanie

Klasa nie ma `disable()` ani `enable()`. Wyłączenie używa rodzica PrestaShop: moduł zostaje zainstalowany, tabele i konfiguracja zostają, hooki nie są wykonywane. Włączenie używa włączenia rodzica.

Klasa nie ma `uninstall()`. Odinstalowanie używa metody rodzica: moduł jest wyrejestrowany, a rejestracje hooków zapisane dla niego przez PrestaShop są usuwane. Metoda rodzica nie kasuje `hbp_block`, `hbp_block_lang` ani `hbp_customhook`. Nie kasuje kluczy konfiguracji z listy wyżej. Nie kasuje własnych wierszy `Hook` utworzonych przez **Dodaj nowy hook** i nie przywraca `htmlboxpro.php` po **Wygeneruj na nowo** ani po dodaniu własnego hooka. Kolejna instalacja używa `CREATE TABLE IF NOT EXISTS`, więc wiersze zostawione w tych tabelach zostają.

## 12. Pusta strona pod zakładkami

Kod przyjmuje `selecttab` = 3 i może zapisać `hbp_lasttab` = 3. Pasek nie ma trzeciego przycisku, a renderer formularza nie ma strony dla 3. Przy tej wartości obszar pod paskiem jest pusty. **Ustawienia** albo **Boxy** zapisują z powrotem 1 albo 2.

## 13. Wsparcie

Strona modułu: [HTML Box Pro](https://mypresta.eu/modules/front-office-features/html-box-pro.html).
