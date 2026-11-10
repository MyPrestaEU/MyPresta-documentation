---
title: Filtr kategorii krok po kroku - dokumentacja i instrukcja użytkownika
sidebar:
  label: Filtr kategorii krok po kroku - dokumentacja i instrukcja użytkownika
description: Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które mają już filtr kategorii krok po kroku.
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Step by step - categories na MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/step-by-step-categories/)
>
> ---


## 1. Wymagania

Moduł działa w PrestaShop. Nie potrzebuje innego modułu ani konta w zewnętrznym serwisie.

- PrestaShop od 1.6.0.0 wzwyż, w tym PrestaShop 8 i 9.
- PHP w wersji wymaganej przez tę wersję PrestaShop. Sprawdzenie aktualizacji używa cURL, gdy PHP je ma, a w przeciwnym razie pobiera odpowiedź zwykłym odczytem adresu. Do list rozwijanych nie instalujesz osobnego rozszerzenia.
- Żaden inny moduł nie jest wymagany.
- W multisklepie blok może należeć do jednego sklepu albo do wszystkich sklepów.

## 2. Instalacja

1. W zapleczu otwórz **Moduły**, potem **Menedżer modułów**.
2. Wgraj paczkę zip i kliknij **Zainstaluj**.
3. Otwórz **Konfiguruj** przy **Step By Step - categories tree**. Na stronie są **Blocks**, **Settings** i **Updates**. **Blocks** to lista zestawów list. Pierwsze wejście tworzy ukrytą stronę tej listy. Nie pojawia się ona jako własna pozycja w lewym menu.
4. Instalacja nie czyści cache osobnym krokiem. Gdy po aktualizacji sklep dalej pokazuje stary układ, wyczyść cache w **Zaawansowane**, **Wydajność**.

Odinstalowanie usuwa tę ukrytą stronę. Bloki, tytuły, etykiety i dwa przełączniki globalne zostają w bazie. Po ponownej instalacji te same bloki są dostępne. Wejdź raz w **Konfiguruj**, żeby strona listy została zarejestrowana.

Poza zwykłym wyłącznikiem modułu w **Menedżerze modułów** nie ma osobnej akcji włączania. Wyłączenie modułu chowa listy na sklepie i zostawia zapisane bloki.

## 3. Konfiguracja i praca w zapleczu

Tworzysz blok, ustawiasz głębokość drzewa i miejsce na sklepie. Klient wybiera kategorię. Kolejna lista ładuje jej dzieci. **ok** otwiera wybraną kategorię albo produkt, gdy lista produktów jest włączona.

### 3.1 Strona konfiguracji modułu

Wejdź w **Moduły**, **Menedżer modułów**, **Step By Step - categories tree**, **Konfiguruj**.

Zrzuty w tym rozdziale są z angielskiego zaplecza. Napisy na ekranie zostają po angielsku.

![Ustawienia](https://mypresta.eu/docs/images/docs/stepbystep-configure-settings.webp)

Na górze są **Blocks**, **Settings** i **Updates**. **Blocks** wychodzi z tej strony i otwiera listę bloków. **Settings** jest zakładką startową. Pod paskiem jest zdanie, że te opcje dotyczą każdego bloku, a same bloki edytuje się w **Blocks**.

Ekran zaplecza jest po angielsku. Nazwy poniżej są z tego ekranu.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Reset search fields** | No | Yes czyści listy po wyszukaniu. No zostawia kategorie wybrane przez odwiedzającego. Przeglądarka trzyma ten wybór przez 30 minut. |
| **Include Select2 library** | No | Yes ładuje dodatkowy skrypt i arkusz używany przez **Search inside dropdown** na bloku. No zostawia zwykłe listy. |

Kliknij **Save**. Strona pokazuje **Settings saved.**

![Aktualizacje](https://mypresta.eu/docs/images/docs/stepbystep-configure-updates.webp)

**Updates** to formularz **MyPresta updates**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Manual check** | przycisk **Check now** | Pyta MyPresta, czy jest nowsze wydanie. **New version available!** prowadzi do listy zmian. **Module is up to date!** znaczy, że ta instalacja jest zgodna z opublikowanym wydaniem. Przycisk nie wgrywa zipa. |
| **Automatic notifications** | Enabled | Enabled powtarza to sprawdzenie mniej więcej co 3 dni, gdy pracujesz w zapleczu. Disabled je pomija. |
| **Product page** | link do strony modułu | Otwiera stronę Step by Step na mypresta.eu. |

**Save** pokazuje **Update settings saved.** Nowy zip wgrywasz w **Menedżerze modułów**, gdy pojawi się nowsze wydanie.

### 3.2 Lista bloków

Otwórz **Blocks**. Pod paskiem jest zdanie, że każdy blok to jeden zestaw list.

![Lista bloków](https://mypresta.eu/docs/images/docs/stepbystep-blocks-list.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **ID** | nadawane przy zapisie | Numer bloku. Służy do odróżnienia wierszy. |
| **Title** | Block i numer, dopóki nie wpiszesz tytułu | Nagłówek w języku zaplecza. |
| **Depth** | 3 przy nowym bloku | Ile list blok rysuje. |
| **Root category** | kategoria główna sklepu przy nowym bloku | Rodzic pierwszej listy, pokazany jako numer i nazwa. |
| **Hook** | Top przy nowym bloku | Miejsce bloku na sklepie. |
| **Active** | Yes | Ikona włącza albo wyłącza blok. Wyłączony wiersz zostaje, a listy znikają ze sklepu. |
| **Position** | kolejna wolna pozycja | Przeciągnij wiersz, żeby zmienić kolejność bloków na tym samym haku. |

Akcje wiersza to **Edit** i **Delete**. **Bulk actions** ma **Enable selection**, **Disable selection** i **Delete selected**. Potwierdzenie usuwania pyta **Delete selected blocks?**

**Add new** otwiera pusty formularz. Nowy blok jest aktywny, ma głębokość 3, korzeń w kategorii głównej, sortowanie po ID rosnąco, licznik produktów wyłączony, przycisk po ostatniej liście, produkty wyłączone, auto submit wyłączony, szukanie w liście wyłączone, etykietę wewnątrz listy, hak Top i bieżący sklep. Zapisz go. Formularz otwiera się ponownie, żeby uzupełnić etykiety. Etykiet nie ma na formularzu, dopóki blok nie istnieje.

Lista pokazuje bloki sklepu, w którym jesteś, oraz bloki ustawione na **All shops**.

### 3.3 Formularz bloku

Otwórz wiersz przez **Edit** albo użyj **Add new** i ekranu edycji po pierwszym zapisie.

![Formularz bloku, góra](https://mypresta.eu/docs/images/docs/stepbystep-block-form.webp)

![Formularz bloku, etykiety i pozycja](https://mypresta.eu/docs/images/docs/stepbystep-block-form-bottom.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Block title** | puste | Nagłówek nad listami. Osobne pole na każdy język sklepu. |
| **Depth** | 3 | Ile list blok rysuje. Zapisz blok i wejdź w edycję ponownie, żeby uzupełnić etykietę każdego poziomu. Formularz pokazuje najwyżej 30 pól etykiet. |
| **Root category** | kategoria główna | Pierwsza lista pokazuje dzieci tej kategorii. |
| **Sort method** | By ID | By ID, By name albo By position. Position to kolejność kategorii w katalogu. |
| **Sort direction** | Ascending | Ascending albo Descending. |
| **Products counter** | No | Yes dopisuje liczbę produktów w nawiasie za nazwą kategorii. |
| **Submit button** | After last select box | After each select box pokazuje **ok** przy kroku, na którym jest klient. After last select box pokazuje jedno **ok** dla całego zestawu. |
| **Include products** | No | Yes pokazuje listę produktów z ostatniej wybranej kategorii. |
| **Auto submit** | No | Yes wysyła formularz, gdy wybrana jest ostatnia dostępna kategoria. Sklep otwiera tę kategorię. Działa, gdy **Include products** jest wyłączone. Gdy wybrana kategoria nie ma dzieci, sklep też ją otwiera. |
| **Search inside dropdown** | No | Yes włącza szukanie w listach. W **Settings** musi być też włączone **Include Select2 library**. |
| **Exclude categories** | puste | Numery kategorii, które nie mają się pojawić na listach. Rozdziel je przecinkami, na przykład 1,2,3,4,5,6. Szukajka obok pola znajduje kategorię i dopisuje jej numer. |
| **Show on category pages** | puste | Puste pokazuje blok na każdej stronie, na której jest jego hak. Numery kategorii, rozdzielone przecinkami, pokazują go tylko na tych stronach kategorii. |
| **Label position** | Inside select box | Inside select box wstawia etykietę jako pierwszą opcję. Outside select box drukuje etykietę nad polem. |
| **Label 1**, **Label 2** i dalej | puste | Jedno pole na krok i na język. Pojawiają się dopiero po zapisaniu bloku. Zmień **Depth** i zapisz, gdy potrzebujesz ich więcej albo mniej. |
| **Module position** | Top | Top, displaySearch, TopColumn, Left column, Right column, Home albo displaySbs. |
| **Position top settings** | Blocks | Blocks układa listy jedna pod drugą. Wide horizontal bar układa je w rzędzie. Szeroki pasek jest używany na Top i displaySearch. Pozostałe miejsca zostają w kolumnie. Na szerokim pasku **ok** stoi za ostatnią listą i schodzi do następnego wiersza, gdy brakuje miejsca. |
| **Shop** | sklep, który edytujesz | Jeden sklep albo **All shops**. **All shops** zostawia blok w każdym sklepie. |
| **Active** | Yes | No chowa blok na sklepie. |

Kliknij **Save**. PrestaShop pokazuje swoje zwykłe potwierdzenie. Usunięcie bloku kasuje też jego tytuł, wybór szerokiego paska i etykiety kroków.

Żeby pokazać blok w pliku szablonu bez gotowego haka, wstaw hak displaySbs i ustaw **Module position** na displaySbs. Pozostałe pozycje podepnij w **Wygląd**, **Pozycje**, jeśli szablon ich sam nie wyświetla.

## 4. Front sklepu

Klient widzi tytuł bloku i listy.

1. Pierwsza lista pokazuje dzieci kategorii głównej bloku. Dalsze listy są nieaktywne, dopóki poprzedni krok nie ma kategorii.
2. Klient wybiera kategorię. Na bloku pojawia się spinner. Następna lista wypełnia się dziećmi. Spinner znika, gdy lista jest gotowa, i także wtedy, gdy żądanie się nie uda.
3. Wykluczonych numerów kategorii na tych listach nie ma.
4. Przy **Submit button** ustawionym na after each select box **ok** jest przy bieżącym kroku. Przy after last select box jest jedno **ok** dla zestawu.
5. **ok** otwiera wybraną kategorię.
6. Przy włączonym **Include products** ostatni krok dodaje listę produktów. Pierwsza opcja to **- Select Product -**. **ok** używa wtedy wybranego produktu.
7. Przy włączonym **Auto submit** i wyłączonym **Include products** wybór ostatniej kategorii otwiera ją bez **ok**. To samo przekierowanie jest, gdy wybrana kategoria nie ma dzieci.
8. Przy wyłączonym **Reset search fields** kolejna wizyta może pokazać te same kategorie. Przeglądarka trzyma je 30 minut. Przy włączonej opcji listy startują puste.
9. Gdy **Search inside dropdown** i **Include Select2 library** są włączone, klient może pisać w liście.

W lewej i prawej kolumnie kroki są jeden pod drugim, a tytuł jest wielkimi literami, jak w Classic. Na szerokim pasku kroki stoją w rzędzie. Na wąskim ekranie szeroki pasek składa się w kolumnę. Kolory, ramki i przycisk **ok** biorą się z szablonu, także Hummingbird i Classic w PrestaShop 9.

Blok z wypełnionym **Show on category pages** nie pojawia się na innych stronach. Nieaktywny blok się nie pojawia. Blok innego sklepu też nie.

## 5. Problemy

**Bloku nie ma na sklepie.** Otwórz blok i sprawdź **Active**, **Module position** i **Shop**. Puste **Show on category pages** pokazuje go na każdej stronie tego haka. Wypełniona lista pokazuje go tylko na tych stronach kategorii. W **Wygląd**, **Pozycje** sprawdź, czy hak jest na stronach, o które chodzi. Przy własnym miejscu szablon musi wołać displaySbs, a blok musi mieć tę pozycję.

**Następna lista się nie wypełnia albo spinner zostaje.** Wyczyść cache sklepu, żeby sklep wziął bieżący arkusz i skrypt. Spinner ma znikać po zakończeniu żądania, także gdy odpowiedzi nie da się zastosować. Gdy sklep dalej pokazuje stary gif, w cache jest poprzedni CSS.

**Szukanie w liście nic nie robi.** Włącz **Include Select2 library** w **Settings** i **Search inside dropdown** na bloku. Zapisz oba. Wyczyść cache.

**Na nowym bloku nie ma etykiet.** Zapisz blok raz. Otwórz go ponownie. **Label 1** i reszta pojawiają się dopiero, gdy blok istnieje, i tylko do zapisanej wartości **Depth**.

**Kategorii, której szukasz, nie ma na liście.** Usuń jej numer z **Exclude categories**. Sprawdź, czy jest dzieckiem wybranego rodzica i czy jest aktywna w katalogu.

**Szeroki pasek dalej układa pola w kolumnie.** **Wide horizontal bar** działa na Top i displaySearch. Lewa, prawa, strona główna, TopColumn i displaySbs zostają w kolumnie. Na telefonie szeroki pasek składa się w kolumnę celowo.

**Po aktualizacji nie ma strony Blocks.** Wejdź raz w **Konfiguruj**. Ta wizyta rejestruje stronę. Nie odinstalowuj modułu, jeśli chcesz dalej używać istniejących wierszy. Odinstalowanie usuwa stronę i zostawia wiersze.

**Na starej stronie konfiguracji nie ma ikony kosza.** To poprzednie wydanie. Wgraj bieżący zip z konta klienta. W bieżącym wydaniu blok usuwasz z listy **Blocks**, przyciskiem **Delete** w wierszu albo **Delete selected**.

## 6. Dla developera

### 6.1 Przegląd

Nazwa techniczna `stepbystep`, klasa `Stepbystep`, wersja 1.9.0, autor MyPresta.eu, zakładka `front_office_features`. Nazwa w zapleczu to **Step By Step - categories tree**.

`AdminStepbystepBlocksController` zapisuje wiersze w `sbs_block` oraz tytuły, etykiety i flagę szerokiego paska w `Configuration`. Hooki sklepu czytają aktywne wiersze bieżącego sklepu albo z `id_shop = 0`. `controllers/front/tree.php` zwraca skrypt, który wypełnia następną listę.

### 6.2 Pliki

| Plik | Rola |
|---|---|
| `stepbystep.php` | Instalacja, hooki, formularz ustawień, HTML list, skrypt sklepu. |
| `controllers/admin/AdminStepbystepBlocksController.php` | Lista bloków i formularz bloku. |
| `models/SbsBlock.php` | Model obiektu `sbs_block`. |
| `controllers/front/tree.php` | Kontroler frontu, który zwraca skrypt następnego poziomu. |
| `views/templates/hook/front.tpl` | Znacznik sklepu dla każdego haka. |
| `views/templates/hook/header.tpl` | Wypisuje skrypt w nagłówku. |
| `views/templates/admin/configure.tpl` | Pasek Blocks, Settings, Updates. |
| `css/sbs-front.css` | Układ sklepu, zmienne szablonu, spinner. |
| `js/advajax.js` | Żądanie używane przez listy. |
| `lib/updatesChecker.php` | Sprawdzenie aktualizacji. Klasa `stepbystepUpdate`. |
| `lib/searchTool/searchTool.php` | Szukanie numeru kategorii w formularzu. Klasa `searchToolstepbystep`. |
| `lib/prestashop9compatibility.php` | Klasa `stepbystepPrestashopNewCompatibility`. |
| `views/css/admin.css` | Pasek zaplecza. |

`tree.php` w katalogu głównym modułu to starsza kopia kontrolera frontu. Link sklepu używa `controllers/front/tree.php`. `views/templates/hook/block.tpl`, `blockSbs.tpl`, `top.tpl` i `displaySearch.tpl` nie są renderowane. `css/sbs-block.css` i `css/sbs-top.css` nie są dokładane do strony.

### 6.3 Kontrolery

`AdminStepbystepBlocksController` rozszerza `ModuleAdminController`. `class_name` to `AdminStepbystepBlocks`. `id_parent` to `-1`, więc strona jest ukryta w menu. Identyfikator listy to `id`. Przeciąganie pozycji woła `ajaxProcessUpdatePositions`. Filtr listy to `id_shop` sklepu z kontekstu albo `0`.

`stepbysteptreeModuleFrontController` to kontroler frontu `tree`. `initContent` ustawia `ajax` i nie woła `parent::initContent`. Czyta `sbs_block`, `sbs_pid`, `sbs_lvl`, a przy zatwierdzeniu `sbs_blockid` i `sbs_cidlink`. Treść odpowiedzi to JavaScript. Brak bloku kończy odpowiedź.

### 6.4 Hooki

Zarejestrowane hooki: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayTop`, `displaySearch`, `displayHome`, `displaySbs`, `displayBackOfficeHeader`. Od PrestaShop 1.6 także `displaytopColumn`.

| Hook | Wartość pozycji bloku | Układ |
|---|---|---|
| `displayTop` | 1 | góra, szeroki pasek gdy `sbs_top_type{id}` wynosi 1 |
| `displayLeftColumn` | 2 | kolumna |
| `displayRightColumn` | 3 | kolumna |
| `displayHome` | 4 | kolumna |
| `displaytopColumn` | 5 | kolumna |
| `displaySearch` | 6 | góra, szeroki pasek gdy `sbs_top_type{id}` wynosi 1 |
| `displaySbs` | 7 | kolumna |

`displayHeader` ładuje `js/advajax.js` i `css/sbs-front.css`. Gdy `SBS_SELECT2` wynosi 1, ładuje też Select2. Nie ma nadpisania `enable()` ani `disable()`.

### 6.5 Nadpisania

Moduł nie nadpisuje klasy ani kontrolera PrestaShop.

### 6.6 Baza

| Tabela | Zawartość |
|---|---|
| `ps_sbs_block` | `id`, `depth`, `root`, `orderby`, `orderway`, `counter`, `each_submit`, `lbl_position`, `block_position`, `position`, `active`, `products`, `last_submit`, `search_inside`, `exclude`, `id_shop`, `on_cat_only`, `id_categories`. |

Prefiks jest taki jak w sklepie. Odinstalowanie nie kasuje tabeli. `inconsistency()` dopisuje brakującą kolumnę z tej listy przy wejściu w konfigurację albo listę bloków. `on_cat_only` zostaje i nie jest na formularzu. Sklep używa `id_categories`.

### 6.7 Klucze i tłumaczenia

| Klucz | Gdy go nie ma |
|---|---|
| `SBS_RESET` | Traktowany jako 0. Wybory są pamiętane 30 minut w ciasteczkach `sbs_selectbox_{block}_{level}`. |
| `SBS_SELECT2` | Traktowany jako 0. Select2 nie jest ładowany. |
| `sbs_title{id}` | Wielojęzyczny tytuł bloku. |
| `{id}sbs_lbl_{n}` | Wielojęzyczna etykieta kroku `n`, od 1 do głębokości, najwyżej 30. |
| `sbs_top_type{id}` | 0 kolumna, 1 szeroki pasek. |

Instalacja zapisuje też `sbs_depth`, `sbs_counter`, `sbs_each_submit`, `sbs_position`, `sbs_lbl_position` i `sbs_root`. Formularz bloku tych kluczy nie czyta. Nowe bloki biorą wartości z `prepareObjectDefaults()`.

Tłumaczenia są w `translations/{iso}.php`. Napisy kontrolera bloków mają źródło `AdminStepbystepBlocksController`. Tekst przycisku to napis modułu `ok`. Placeholder produktu to `- Select Product -`.

### 6.8 Rozszerzanie

Nadpisz `views/templates/hook/front.tpl` w szablonie jako `themes/{theme}/modules/stepbystep/views/templates/hook/front.tpl`. Tak samo nadpisz `css/sbs-front.css`, gdy szablon ma zastąpić układ. Pozycja przycisku na szerokim pasku jest w kolejności flex w tym arkuszu: widoczne `.sbs__actions` idzie za listami i zawija się z wierszem.

## 7. Pomoc

Strona modułu: [Step by Step categories](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html).

Żeby napisać w sprawie tego modułu, zaloguj się na konto klienta na [mypresta.eu](https://mypresta.eu), przejdź do kontaktu i wybierz temat **Support for paid modules**. Przy tym temacie formularz podaje, że logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
