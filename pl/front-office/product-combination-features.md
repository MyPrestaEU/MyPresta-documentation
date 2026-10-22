---
title: "Cechy kombinacji - instrukcja sprzedawcy"
description: "Instrukcja konfiguracji i rozwiązywania problemów dla osób, które mają moduł już zainstalowany."
sidebar:
  label: "Cechy kombinacji - instrukcja sprzedawcy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product combination features na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-combination-features/)
>
> ---


Nazwa techniczna: `combfeat`. Wersja **1.4.0**. W panelu administracyjnym moduł nazywa się **Cechy kombinacji**.

## 1. Wymagania i kompatybilność

- **PrestaShop:** od 1.7.0.0 do 9.x (w module `ps_versions_compliancy` ma górną granicę 9.99.99).
- **PHP:** wersja wymagana przez daną wersję PrestaShop.
- **Karta produktu:** motyw musi wystawiać wybraną kombinację w atrybucie `data-product` elementu `#product-details` (standard PrestaShop) i wysyłać zdarzenie `updatedProduct` po zmianie atrybutów. Classic i motywy na nim oparte tak działają.
- **PrestaShop 8 i 9, zakładka Moduły przy produkcie:** plik `src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig` musi dać się zapisać przy instalacji albo przy pierwszym otwarciu konfiguracji. Patrz [Pliki, które moduł zmienia](#3-pliki-ktore-modul-zmienia).
- **Nawigacja fasetowa (opcjonalnie):** zainstalowany `ps_facetedsearch`, prawo do utworzenia widoku SQL i zapis do `modules/ps_facetedsearch/src/Adapter/MySQL.php`.
- **Sprawdzanie aktualizacji (opcjonalnie):** `allow_url_fopen`, żeby moduł mógł wywołać `https://dev.mypresta.eu`.

## 2. Gdzie pracować w panelu

| Miejsce | Ścieżka | Do czego służy |
| --- | --- | --- |
| Konfiguracja modułu | **Moduły > Menedżer modułów**, szukaj **Cechy kombinacji**, **Konfiguruj** | Przełączniki, selektory CSS, tryb tytułu, nawigacja fasetowa, import CSV, sprawdzanie aktualizacji |
| Zawartość kombinacji | **Katalog > Produkty**, edycja produktu, zakładka **Moduły**, blok **Zawartość kombinacji** | Cechy, opis i tytuły każdej kombinacji |
| Katalog cech | **Katalog > Atrybuty i cechy** (nazwa zależy od wersji PrestaShop) | Utworzenie cech i wartości, zanim przypniesz je na karcie produktu. Import CSV potrafi utworzyć brakujące |
| Szablon nawigacji fasetowej | Konfiguracja modułu Nawigacja fasetowa | Dodanie cechy do szablonu filtrów. Ten moduł nie dodaje jej sam |

Moduł nie ma własnej pozycji w menu i nie ma własnego kontrolera frontu ani zaplecza.

## 3. Pliki, które moduł zmienia

### 3.1 Zakładka Moduły produktu w PrestaShop 8 i 9

Przy instalacji i przy każdym otwarciu strony konfiguracji moduł edytuje:

`src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig`

Podmienia `{{ module.content|raw_purified }}` na `{{ module.content|raw }}`. Za pierwszym razem kopiuje oryginał do `modules-content.html.twig.raw.bak` obok tego pliku.

PrestaShop 8 i 9 oczyszczają HTML wypisywany przez moduły na karcie produktu. Bez tej zmiany edytor **Zawartość kombinacji** jest pusty albo jego pola nie wchodzą w zapis produktu. W PrestaShop 1.7 tego pliku Twig nie ma. Moduł pomija zmianę.

Gdy pliku nie da się odczytać albo zapisać, moduł nie pokazuje błędu. Sprawdź uprawnienia, jeśli zakładka Moduły zostaje pusta.

### 3.2 Adapter nawigacji fasetowej

Gdy opcja **Filter combination features in Faceted Search** jest włączona (domyślnie), moduł tworzy widok SQL `{prefix}combfeat_feature_product` i kieruje na niego `modules/ps_facetedsearch/src/Adapter/MySQL.php`. Widok to lista cech produktu plus aktywne cechy kombinacji.

Wyłączenie opcji, wyłączenie modułu albo odinstalowanie przywraca oryginalne źródło adaptera. Odinstalowanie usuwa też widok, gdy adapter już do niego nie odwołuje się.

Na stronie konfiguracji pojawia się ostrzeżenie, gdy widoku nie da się utworzyć, plik adaptera nie istnieje, nie da się go odczytać, nie da się go zapisać albo nie pasuje do oczekiwanego źródła Faceted Search. Komunikaty (w module są po angielsku):

- Could not create the Faceted Search feature view. Combination features will not appear in category filters.
- Faceted Search is installed, but its database adapter was not found. Combination features will not appear in category filters.
- Faceted Search adapter could not be read. Combination features will not appear in category filters.
- This Faceted Search version does not use the expected feature table. Combination features will not appear in category filters.
- Faceted Search adapter is not writable. Make modules/ps_facetedsearch/src/Adapter/MySQL.php writable so combination features can be filtered.
- Faceted Search adapter could not be updated. Combination features will not appear in category filters.

## 4. Konfiguracja modułu

Otwórz **Konfiguruj**. Na stronie są dwa formularze, a pod nimi panel **Aktualizacje MyPresta**. **Zapisz** w ustawieniach wysyła `submitCombfeatSettings`. **Import** wysyła `submitCombfeatImport`.

### 4.1 Włącz cechy dla kombinacji

Klucz: `combfeat_p_feat`. Domyślnie: **Włączone**.

Gdy opcja jest włączona, każda kombinacja w zakładce **Moduły** produktu ma zakładkę **Cechy**. Przypinasz tam istniejące wartości cech.

Gdy jest wyłączona, tej zakładki nie ma. Skrypt w sklepie to osobna sprawa: cechy i opisy aktualizuje ten sam skrypt, opisany w [Sklep](#6-sklep).

**Zapis produktu przy wyłączonej opcji kasuje cechy kombinacji tego produktu.** Formularz nie zawiera już pól cech. Zapis czyści wiersze cech modułu dla produktu i zapisuje z powrotem tylko to, co formularz przysłał. Opisy i tytuły zostają. Włącz opcję z powrotem, zanim edytujesz produkt, jeśli te cechy mają zostać.

### 4.2 Klasa CSS specyfikacji

Klucz: `combfeat_ds`. Domyślnie: `.data-sheet`.

Selektor jQuery. Moduł podmienia **wewnętrzny HTML** dopasowanego elementu parami:

```html
<dt class="name">Cecha</dt><dd class="value">Wartość</dd>
```

Wskaż element `<dl>`, w którym te wiersze już są. W motywie Classic jest to `dl.data-sheet`, więc wartość domyślna jest właściwa. Wskazanie większego bloku, na przykład `.product-features` albo `#product-details`, podmienia całą zawartość tego bloku na pary `<dt>` / `<dd>`.

Gdy selektor niczego nie znajdzie, a wybrana kombinacja ma cechy, moduł podmienia całą zawartość `#product-details` na nową sekcję specyfikacji. Znika wtedy indeks, marka i wszystko inne, co było w `#product-details`. Ustaw selektor tak, żeby ten zapasowy wariant się nie uruchamiał.

### 4.3 Tryb działania

Klucz: `combfeat_workflow`. Domyślnie: **Zastąp istniejące cechy produktu** (wartość `0`).

| Opcja | Wartość | Specyfikacja po wybraniu kombinacji |
| --- | --- | --- |
| **Zastąp istniejące cechy produktu** | `0` | Cechy kombinacji zastępują specyfikację. Gdy kombinacja nie ma cech, z powrotem trafiają cechy samego produktu. |
| **Dołącz do istniejącej listy cech produktu** | `1` | Najpierw zostają cechy produktu. Cechy kombinacji są dopisywane za nimi. Gdy kombinacja nie ma cech, widać tylko cechy produktu. |

Ta sama wartość cechy na produkcie i na kombinacji w trybie **Dołącz** pojawia się dwa razy. Moduł nie usuwa duplikatów.

Jedna cecha może mieć kilka wartości. Każda wartość to osobny wiersz. Kolejność wynika z pozycji cechy w katalogu.

**Tryb działania zmienia tylko specyfikację.** Opis jest zawsze podmieniany, w obu trybach. Patrz [Opis](#64-opis).

Skrypt w sklepie wynika z tego ustawienia: `views/js/combfeat.js` dla zastępowania, `views/js/combfeat-append.js` dla dołączania.

### 4.4 Filter combination features in Faceted Search

Klucz: `combfeat_faceted`. Domyślnie: **Enabled**.

Etykieta na ekranie jest po angielsku: **Filter combination features in Faceted Search**. Tego napisu nie ma jeszcze w plikach tłumaczeń modułu. Opis pod przełącznikiem też jest po angielsku: wartości cech, które są tylko na kombinacjach, pojawiają się w `ps_facetedsearch`, a licznik obejmuje produkt, gdy wartość jest na produkcie albo na dowolnej kombinacji. Cechę trzeba dodać do szablonu Faceted Search. Lista cech produktu się nie zmienia.

Gdy `ps_facetedsearch` jest zainstalowany i przełącznik jest włączony:

- W filtrach kategorii mogą pojawić się wartości, które istnieją tylko na kombinacjach.
- Produkt jest liczony, gdy wartość jest na produkcie **albo na dowolnej jego kombinacji**. Filtr nie zależy od kombinacji, którą klient wybierze później. Jeden produkt liczy się raz, nawet jeśli wartość ma kilka kombinacji.
- Cechę i tak dodajesz do szablonu nawigacji fasetowej. Moduł nie edytuje szablonów.
- Lista cech na karcie produktu w katalogu zostaje bez zmian.

Po zapisaniu cech kombinacji albo po imporcie CSV moduł opróżnia pamięć bloków nawigacji fasetowej (`layered_filter_block`), żeby filtry zbudowały się od nowa.

Szczegóły zmiany pliku: [Adapter nawigacji fasetowej](#32-adapter-nawigacji-fasetowej) i [Nawigacja fasetowa](#7-nawigacja-fasetowa).

### 4.5 Włącz opisy dla kombinacji

Klucz: `combfeat_p_desc`. Domyślnie: **Włączone**.

W angielskim źródle etykieta to **Turn on descriptionsfor combinations** (brak spacji przed „for”). Polskie tłumaczenie to **Włącz opisy dla kombinacji**.

Gdy opcja jest włączona, każda kombinacja ma zakładkę **Opis** z polem tekstu sformatowanego dla każdego języka sklepu.

Gdy jest wyłączona, zakładki nie ma, a zapis produktu nie zmienia zapisanych opisów. Jeśli cechy nadal są włączone, skrypt w sklepie i tak działa i pokaże opis zapisany wcześniej. Wyczyść pola opisu, zapisz produkt i dopiero wtedy wyłącz przełącznik, jeśli sklep ma przestać z nich korzystać.

### 4.6 Opis klasy CSS / ID obiektu

Klucz: `combfeat_description`. Domyślnie: `#description`.

Selektor jQuery bloku, którego HTML zastępuje opis kombinacji. W motywie Classic `#description` to zakładka długiego opisu, więc wartość domyślna trafia w ten blok.

Gdy selektor niczego nie znajdzie, opis na stronie zostaje bez zmian.

Tekst używany, gdy kombinacja nie ma własnego opisu, to **długi opis** produktu (`description`) w bieżącym języku. To nie jest krótki opis i nie jest to meta opis. Jeśli wskażesz tym selektorem blok krótkiego opisu, kombinacja bez własnego tekstu wypełni ten blok długim opisem.

### 4.7 Włącz meta tytuł dla kombinacji

Klucz: `combfeat_p_title`. Domyślnie: **Włączone**.

Gdy opcja jest włączona, karta produktu ładuje `views/js/combfeat-title.js`. Wybór kombinacji aktualizuje `document.title` oraz, jeśli jest, `<meta property="og:title">`.

Tytuł w HTML wysłanym przez serwer zostaje meta tytułem produktu. Odwiedzający widzą tytuł kombinacji po uruchomieniu JavaScriptu. Robot, który nie uruchamia JavaScriptu, zostaje przy tytule produktu.

Gdy opcja jest wyłączona, zakładka **Meta tytuł** jest ukryta, skrypt się nie ładuje, a zapis produktu nie zmienia zapisanych tytułów.

### 4.8 Domyślny tryb tytułu

Klucz: `combfeat_title_default`. Domyślnie: **Dodaj nazwę atrybutu i wartość (oddzielone przecinkami)** (wartość `1`).

Używany tylko wtedy, gdy ta kombinacja nie ma **Pełnego tytułu** ani **Dołącz do tytułu** w bieżącym języku.

Tytuł wyjściowy to tytuł przeglądarki zapamiętany przy pierwszym załadowaniu strony. Późniejsze zmiany nie zapamiętują go ponownie, więc dopisywane fragmenty się nie kumulują.

| Opcja | Wartość | Wynik |
| --- | --- | --- |
| **Domyślnie nie zmieniaj tytułu** | `0` | Zostaje pierwotny tytuł dokumentu. |
| **Dodaj nazwę atrybutu i wartość (oddzielone przecinkami)** | `1` | Tytuł pierwotny, separator, potem grupy i wartości, na przykład `Kolor: Czerwony, Rozmiar: M`. |
| **Dodaj tylko wartości atrybutów (oddzielone przecinkami)** | `2` | Tytuł pierwotny, separator, potem same wartości, na przykład `Czerwony, M`. |

Nazwy grup i wartości pochodzą z bieżącego języka sklepu.

### 4.9 Separator tytułu

Klucz: `combfeat_title_separator`. Domyślnie: ` - ` (spacja, dywiz, spacja).

Wstawiany między pierwotny tytuł dokumentu a dodawaną część. Dodawaną częścią jest albo tekst trybu domyślnego, albo pole **Dołącz do tytułu** kombinacji. Separator jest używany tak, jak został zapisany, razem ze spacjami.

**Pełny tytuł** nie używa separatora. Sam zastępuje tytuł dokumentu.

Gdy pierwotny tytuł jest pusty, zostaje sama dodawana część.

### 4.10 Szybkie zestawienie ustawień

| Ustawienie | Klucz | Domyślnie |
| --- | --- | --- |
| Włącz cechy dla kombinacji | `combfeat_p_feat` | Włączone (`1`) |
| Klasa CSS specyfikacji | `combfeat_ds` | `.data-sheet` |
| Tryb działania | `combfeat_workflow` | Zastąp (`0`) |
| Filter combination features in Faceted Search | `combfeat_faceted` | Włączone (`1`) |
| Włącz opisy dla kombinacji | `combfeat_p_desc` | Włączone (`1`) |
| Opis klasy CSS / ID obiektu | `combfeat_description` | `#description` |
| Włącz meta tytuł dla kombinacji | `combfeat_p_title` | Włączone (`1`) |
| Domyślny tryb tytułu | `combfeat_title_default` | Nazwa atrybutu i wartość (`1`) |
| Separator tytułu | `combfeat_title_separator` | ` - ` |

## 5. Import cech kombinacji

Drugi formularz na stronie konfiguracji. Te etykiety są na razie angielskimi napisami źródłowymi w każdym języku (nie ma ich w plikach tłumaczeń modułu).

Import przypisuje wartości cech do kombinacji. Nie importuje opisów ani tytułów i nie zapisuje wierszy na liście cech produktu (`feature_product`). Brakująca cecha albo brakująca wartość jest tworzona w katalogu.

### 5.1 Import mode

| Tryb | Działanie |
| --- | --- |
| **Append to combination features** (domyślny) | Zostawia przypisania już zapisane. Wiersz, który już jest na tej kombinacji, jest pomijany. |
| **Replace features of listed combinations** | Dla każdej kombinacji, która jest w pliku, kasuje cechy tej kombinacji w module, a potem zapisuje wiersze z pliku. Kombinacje spoza pliku zostają. Opisy i tytuły nie są kasowane. |

### 5.2 Zasady pliku

- UTF-8, rozszerzenie `.csv` albo `.txt`. Początkowy BOM jest akceptowany. Maksymalny rozmiar **8 MB**.
- Separator jest wykrywany z wiersza nagłówka: średnik, przecinek albo tabulator. Gdy żadnego z nich nie ma, używany jest średnik.
- Nagłówek musi wskazać kombinację przez `id_product_attribute` albo `combination_reference`.
- Nagłówek musi wskazać cechę przez `feature` i `value` albo przez `id_feature_value`.
- Puste wiersze są pomijane. Wypisanych jest najwyżej 30 błędów wierszy. Reszta jest tylko liczona.

Przyjmowane nazwy kolumn (spacje i dywizy stają się podkreśleniami, wielkość liter jest ignorowana):

| Kolumna | Również przyjmowane |
| --- | --- |
| `id_product` | `product_id` |
| `id_product_attribute` | `id_combination`, `combination_id` |
| `product_reference` | — |
| `combination_reference` | `combination_ref`, `attribute_reference` |
| `feature` | `feature_name`, `id_feature` |
| `value` | `feature_value` |
| `id_feature_value` | `feature_value_id` |

`id_product` i `product_reference` są opcjonalne. Gdy je wypełnisz, muszą należeć do tej kombinacji. Niezgodność odrzuca wiersz.

Szukanie kombinacji:

- `id_product_attribute` jest używane, gdy jest większe od zera. Gdy podane są i ID, i `combination_reference`, referencja musi zgadzać się z tym wierszem.
- W przeciwnym razie używana jest referencja kombinacji. Gdy kilka kombinacji ma tę samą, dodaj `id_product` albo `id_product_attribute`. Komunikat: Combination reference matches more than one combination.

Szukanie wartości cechy:

- `id_feature_value` większe od zera wczytuje tę wartość. Komórki nazwy i wartości cechy są ignorowane.
- W przeciwnym razie `feature` i `value` są wymagane. Komórka cechy złożona z samych cyfr to ID cechy.
- Nazwy są dopasowywane dokładnie, a potem bez względu na wielkość liter. Gdy pasuje więcej niż jedna cecha albo wartość, wiersz jest odrzucany. Moduł niczego nie zgaduje.
- Cecha, której nie ma, jest tworzona. Jej nazwa jest kopiowana do każdego języka sklepu. Maksymalna długość 128.
- Wartość, której nie ma, jest tworzona jako zwykła (nie niestandardowa), z tym samym tekstem w każdym języku. Maksymalna długość 255. Potem popraw języki w **Katalog > Atrybuty i cechy**, jeśli mają się różnić.

**Download sample file** wysyła `import/combfeat-features-sample.csv`:

```csv
id_product;id_product_attribute;product_reference;combination_reference;feature;value;id_feature_value
12;45;DEMO-1;DEMO-1-RED;Material;Cotton;
12;46;DEMO-1;DEMO-1-BLUE;Material;Wool;
;;DEMO-2;DEMO-2-XL;Composition;100% cotton;
10;25;;;;;83
```

Kolejne wiersze tego przykładu oznaczają:

1. Kombinacja 45 produktu 12, referencje muszą się zgadzać, cecha Material / Cotton (utworzona, jeśli jej nie ma).
2. Kombinacja 46 produktu 12, Material / Wool.
3. Kombinacja o referencji `DEMO-2-XL` produktu o referencji `DEMO-2`, cecha Composition / 100% cotton. Bez numerycznych ID.
4. Kombinacja 25 produktu 10, istniejąca wartość cechy 83. Nazwa i wartość cechy są puste.

Po udanym imporcie pamięć bloków nawigacji fasetowej jest czyszczona. Potwierdzenie podaje, ile przypisań zapisano, ile już było i które wiersze się nie udały.

## 6. Zawartość kombinacji przy produkcie

**Katalog > Produkty**, edycja produktu, zakładka **Moduły**. Tytuł bloku: **Zawartość kombinacji**. Podtytuł: **Cechy, opisy i meta tytuły dla danej kombinacji**.

Najpierw utwórz kombinacje (zakładka **Kombinacje** produktu). Gdy produkt ich nie ma, blok o tym informuje i nie ma czego edytować.

### 6.1 Lista

- **Rozwiń wszystko** / **Zwiń wszystko**.
- **Filtruj kombinacje…** dopasowuje nazwę kombinacji, ID kombinacji i referencję kombinacji.
- Każdy wiersz pokazuje zdjęcie kombinacji (albo symbol zastępczy), nazwy atrybutów, **Combination ID**, **Reference** (gdy kombinacja ma referencję) oraz znaczniki. Znaczniki **Cechy**, **Opis** i **Tytuł** zapalają się, gdy ta część jest wypełniona. Znacznik cech podaje liczbę wartości. Napisy Combination ID i Reference są angielskim źródłem. Nie ma ich w tłumaczeniu.
- Pierwsza kombinacja jest otwarta. **Konfiguruj** otwiera wiersz, **Zamknij** go zwija.
- W wierszu są zakładki odpowiadające włączonym opcjom: **Cechy**, **Opis**, **Meta tytuł**.

Gdy wszystkie trzy przełączniki są wyłączone, blok pokazuje: Wszystkie opcje kombinacji są wyłączone. Włącz cechy, opisy lub tytuły w konfiguracji modułu.

### 6.2 Cechy

Tekst pomocy: Wyszukaj i dołącz wartości cech używane dla tej kombinacji na stronie produktu.

Wpisz co najmniej **2 znaki** nazwy cechy albo wartości, w bieżącym języku pracownika. Pojawia się do 20 trafień, opisanych jako `Cecha: wartość`. Wybór dodaje token. Wyszukiwanie znajduje tylko wartości, które już istnieją. Utwórz je w katalogu albo importem CSV.

Tej samej wartości nie dodasz drugi raz. Kilka wartości tej samej cechy można. **×** usuwa token. Usunięcie zapisuje się razem z produktem.

### 6.3 Opis

Jedno pole tekstu sformatowanego na język. Lista języków jest widoczna, gdy sklep ma więcej niż jeden język. Pusty HTML oznacza brak opisu: w sklepie wraca długi opis produktu, a przy zapisie wiersz tego języka jest kasowany.

### 6.4 Meta tytuł

Oba pola są osobno dla każdego języka, po 512 znaków. Puste pole pomija to nadpisanie.

| Pole | Efekt w sklepie |
| --- | --- |
| **Pełny tytuł (zastępuje cały tytuł)** | Zastępuje cały tytuł dokumentu. Separator i tryb domyślny nie są używane. Gdy oba pola są wypełnione, wygrywa to. |
| **Dołącz do tytułu (fragment dodawany na końcu)** | Pierwotny tytuł dokumentu, separator, potem ten fragment. Używane, gdy Pełny tytuł jest pusty. |

Gdy oba są puste, działa [Domyślny tryb tytułu](#48-domyslny-tryb-tytulu).

### 6.5 Zapis

Zmiany zapisują się razem z produktem. Użyj przycisku **Zapisz** produktu (w tym zapisu z podglądem, zależnie od wersji PrestaShop). W bloku nie ma osobnego zapisu.

Przy zapisie moduł:

1. Kasuje wszystkie wiersze cech kombinacji tego produktu i wstawia tokeny z formularza.
2. Dla każdego języka zapisuje albo kasuje opis.
3. Dla każdego języka zapisuje wiersz tytułu albo kasuje go, gdy oba pola tytułu są puste.
4. Czyści pamięć bloków nawigacji fasetowej, gdy ta opcja jest włączona.

Formularz wysyła ukryte pole `combfeat_submitted`. Gdy tego pola nie ma, moduł nie rusza danych. W PrestaShop 8 i 9 zależy to od zmiany Twig z [punktu 3.1](#31-zakladka-moduly-produktu-w-prestashop-8-i-9).

Usunięcie kombinacji w PrestaShop nie kasuje jej wierszy w tym module. Wiersze nie są używane, bo kombinacji już nie ma. Cechy znikają przy zapisie produktu (formularz wysyła tylko bieżące kombinacje). Wiersze opisu i tytułu usuniętej kombinacji zostają, dopóki nie usuniesz ich z bazy.

## 7. Sklep

Skrypty są dodawane tylko na karcie produktu, tylko gdy żądanie nie jest ajaxowym odświeżeniem całego kontrolera, tylko gdy produkt ma kombinacje i tylko gdy włączony jest co najmniej jeden z trzech przełączników.

| Przełącznik | Skrypt |
| --- | --- |
| Cechy albo opisy, tryb Zastąp | `views/js/combfeat.js` |
| Cechy albo opisy, tryb Dołącz | `views/js/combfeat-append.js` |
| Meta tytuł | `views/js/combfeat-title.js` |

Przy zmianie kombinacji nie ma dodatkowego żądania. Dane wszystkich kombinacji są wstawione w stronę dla **bieżącego języka**. Skrypt czyta wybraną kombinację z atrybutu `data-product` elementu `#product-details` (`id_product_attribute`) i uruchamia się ponownie przy zdarzeniu `updatedProduct`.

`displayProductAdditionalInfo` wypisuje też ukryty element `#product-details-combfeat` z kombinacją ustaloną dla pierwszego widoku (grupy atrybutów z adresu, `id_product_attribute` z żądania albo kombinacja domyślna). Niedostępne kombinacje idą za ustawieniem stanu magazynowego i opcją **Wyświetl niedostępne atrybuty**. Ukryty element jest używany tylko wtedy, gdy samego `#product-details` nie ma. Motyw, który zostawia `#product-details`, musi mieć na tym elemencie `data-product`. Tak jest w standardowym szablonie produktu.

Moduł nie ładuje arkusza CSS do sklepu. Nowe `<dt class="name">` i `<dd class="value">` biorą style specyfikacji z motywu.

### 7.1 Cechy i opisy używają jednego skryptu

`combfeat.js` i `combfeat-append.js` aktualizują specyfikację **oraz** opis, gdy tylko są załadowane. Nie sprawdzają ponownie obu przełączników.

- Cechy włączone, opisy wyłączone: opis zapisany wcześniej nadal jest stosowany, dopóki go nie wyczyścisz i nie zapiszesz.
- Opisy włączone, cechy wyłączone: cechy, które nadal są w bazie, nadal są stosowane. Zapis produktu przy wyłączonych cechach te zapisane cechy kasuje. Patrz [Włącz cechy](#41-wlacz-cechy-dla-kombinacji).

Skrypt tytułu jest osobny i działa tylko przy włączonym tytule.

### 7.2 Specyfikacja

Tryby Zastąp i Dołącz są opisane przy [Trybie działania](#43-tryb-dzialania). Przy każdym uruchomieniu moduł buduje wiersze od nowa. Dodatkowy kod, który motyw miał wewnątrz specyfikacji (linki, dodatkowe klasy wartości), nie zostaje.

### 7.3 Opis

Gdy kombinacja ma opis w bieżącym języku, ten HTML zastępuje zawartość selektora opisu. W przeciwnym razie zastępuje ją długi opis produktu. Tryb Dołącz nie dopisuje tekstu opisu.

### 7.4 Tytuł

Kolejność dla wybranej kombinacji, w bieżącym języku:

1. **Pełny tytuł**, gdy nie jest pusty.
2. W przeciwnym razie **Dołącz do tytułu**, połączone [separatorem](#49-separator-tytulu).
3. W przeciwnym razie [domyślny tryb tytułu](#48-domyslny-tryb-tytulu).

`og:title` dostaje ten sam tekst, gdy taki znacznik istnieje.

## 8. Nawigacja fasetowa

Przy włączonej opcji filtry kategorii czytają widok, który łączy:

- `feature_product` — cechy przypisane do produktu;
- `combfeat` — aktywne cechy przypisane do kombinacji, połączone z `feature_value`, żeby uzyskać ID cechy.

Przebuduj indeks nawigacji fasetowej albo wyczyść pamięć podręczną PrestaShop, jeśli filtr zostaje nieaktualny po usunięciu ostrzeżenia na stronie konfiguracji. Zapis cech kombinacji i import CSV już opróżniają `layered_filter_block`.

Karta produktu w sklepie nadal pokazuje cechy produktu z PrestaShop, dopóki nie zadziała skrypt tego modułu. Filtr i specyfikacja to dwa różne źródła.

## 9. Aktualizacje MyPresta

Panel pod formularzami:

| Kontrolka | Działanie |
| --- | --- |
| **Sprawdź teraz** | Łączy się z MyPresta i pokazuje **Dostępna nowa wersja!** albo **Moduł jest aktualny!** |
| **Powiadomienia o aktualizacjach** | **Włącz** pokazuje w panelu ostrzeżenie, gdy jest nowsza wersja, z linkiem do dziennika zmian. **Wyłącz** ukrywa to ostrzeżenie. |
| **Strona modułu** | Otwiera stronę dodatku: [Product combination features](https://mypresta.eu/modules/front-office-features/product-combination-features.html) |

Gdy pracownik jest w panelu, moduł odpytuje serwer aktualizacji najwyżej raz na 3 dni. Sprawdzenie wymaga `allow_url_fopen`. Gdy jest niedostępne, zostaje zainstalowana wersja i nowsza nie jest zgłaszana.

## 10. Rozwiązywanie problemów

**Blok w zakładce Moduły jest pusty w PrestaShop 8 lub 9.**  
Sprawdź, czy `modules-content.html.twig` zawiera `{{ module.content|raw }}` i czy sklep mógł zapisać ten plik. Otwórz ponownie konfigurację modułu, żeby zmiana została ponowiona. Potem wyczyść pamięć podręczną Symfony (**Zaawansowane > Wydajność**).

**Specyfikacja się nie zmienia.**  
Produkt musi mieć kombinacje, przełącznik cech musi być włączony albo cechy muszą już być zapisane, a kombinacja musi mieć co najmniej jedną wartość (w trybie Zastąp kombinacja bez wartości przywraca cechy produktu, co wygląda jak brak reakcji). Sprawdź selektor w konsoli przeglądarki: `document.querySelectorAll('.data-sheet')`, podstawiając swój selektor. Motyw musi aktualizować `data-product` na `#product-details` i wysyłać `updatedProduct`.

**Cały blok product-details został zastąpiony krótką listą cech.**  
Selektor specyfikacji niczego nie znalazł. Ustaw go na prawdziwy `<dl>`, zwykle `.data-sheet`.

**Opis się nie zmienia albo krótki opis został zastąpiony długim.**  
Domyślny selektor `#description` to w Classic długi opis. Tekst zapasowy jest zawsze długim opisem. W **Opis klasy CSS / ID obiektu** wskaż element, który ma się zmieniać.

**Wyłączyłem opisy, a stary tekst nadal widać.**  
Wyczyść pola, zapisz produkt, potem wyłącz przełącznik. Albo wyłącz też cechy, żeby żaden z tych skryptów się nie ładował. Pamiętaj, że wyłączenie cech i zapis kasuje zapisane cechy kombinacji.

**Wyłączyłem cechy i po zapisie produktu cechy kombinacji zniknęły.**  
Tak działa zapis, gdy pól cech nie ma w formularzu. Włącz przełącznik z powrotem przed edycją, jeśli dane są jeszcze potrzebne. Zaimportuj CSV ponownie, jeśli masz plik.

**Tytuł karty przeglądarki się nie zmienia.**  
Włącz przełącznik tytułu. Pusty Pełny tytuł i puste Dołącz do tytułu razem oznaczają tryb domyślny. Tryb **Domyślnie nie zmieniaj tytułu** zostawia tytuł bez zmian. Zmiana jest po stronie przeglądarki: otwórz stronę, zmień kombinację i odczytaj tytuł karty. Źródło HTML nadal ma meta tytuł produktu.

**Cechy brakuje w filtrze kategorii.**  
Włącz **Filter combination features in Faceted Search**, dodaj cechę do szablonu nawigacji fasetowej i przeczytaj ostrzeżenie na stronie konfiguracji modułu. Plik adaptera musi dać się zapisać. Wartość musi być zapisana na produkcie albo na kombinacji.

**Błędy wierszy CSV.**

| Komunikat | Przyczyna |
| --- | --- |
| The CSV must contain id_product_attribute or combination_reference | Nagłówek nie wskazuje kombinacji |
| The CSV must contain feature and value, or id_feature_value | Nagłówek nie wskazuje wartości cechy |
| Combination was not found | ID albo referencja nie istnieje |
| Product ID does not match this combination | `id_product` jest wypełnione i wskazuje inny produkt |
| Product reference does not match this combination | `product_reference` się nie zgadza |
| Combination reference does not match this combination ID | ID i referencja są wypełnione i są sprzeczne |
| Combination reference matches more than one combination | Dodaj `id_product` albo `id_product_attribute` |
| Feature name or value matches more than one | Dwa wpisy w katalogu mają tę samą etykietę. Użyj `id_feature_value` |
| Feature and value are required when id_feature_value is empty | Komórka nazwy albo wartości jest pusta |
| The CSV file is larger than 8 MB | Podziel plik |

**Wiele języków.**  
Opisy i oba pola tytułu są zapisywane osobno dla każdego języka. Wartości cech używają tłumaczenia cechy PrestaShop w języku odwiedzającego. Samo przypisanie nie jest osobne dla języka.

## 11. Opis techniczny

### 11.1 Hooki

| Hook | Kiedy | Co robi |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Panel, kontrolery `AdminProducts` i `AdminModules` | Ładuje `views/css/combfeat.css`, `views/js/acplt.js`, `views/js/admin-combfeat.js` oraz autouzupełnianie jQuery. Uzupełnia też konfigurację i integrację z nawigacją fasetową |
| `displayAdminProductsExtra` | Edycja produktu, zakładka Moduły | Renderuje `views/templates/admin/combfeat.tpl` |
| `actionProductUpdate` | Zapis produktu | Zapisuje cechy, opisy i tytuły, gdy jest `combfeat_submitted` |
| `displayHeader` | Karta produktu, bez ajax | Wypisuje dane kombinacji dla bieżącego języka i dodaje skrypty sklepu |
| `displayProductAdditionalInfo` | Karta produktu | Renderuje ukryty `views/templates/hook/product-details.tpl` |

Rejestrowane przy instalacji: `actionProductUpdate`, `displayProductAdditionalInfo`, `displayAdminProductsExtra`, `actionAdminControllerSetMedia`, `displayHeader`.

Strona konfiguracji obsługuje też wyszukiwanie cech. Żądanie z `ajax=1` i `q` zwraca trafienia JSON i kończy działanie. Edytor produktu woła ten adres przez `AdminModules` z `configure=combfeat`.

### 11.2 Baza danych

Prefiks to prefiks sklepu. Odinstalowanie **nie** usuwa tych tabel, więc treść kombinacji przeżywa odinstalowanie i jest na miejscu po ponownej instalacji (`CREATE TABLE IF NOT EXISTS`).

`combfeat` — jeden wiersz na wartość cechy kombinacji:

| Kolumna | Rola |
| --- | --- |
| `id_combfeat` | Klucz główny |
| `id_product` | Produkt |
| `id_product_attribute` | Kombinacja |
| `id_feature_value` | Wartość cechy z katalogu |
| `active` | `1`, gdy wiersz jest używany. Sklep i widok nawigacji fasetowej czytają aktywne wiersze |

`combfeat_details` — opis, jeden wiersz na kombinację i język:

| Kolumna | Rola |
| --- | --- |
| `id_combfeat` | Klucz główny |
| `id_product`, `id_product_attribute`, `id_lang` | Cel |
| `details` | HTML |
| `active` | Zapisywane jako `1` |

`combfeat_title` — tytuły, jeden wiersz na kombinację i język:

| Kolumna | Rola |
| --- | --- |
| `id_combfeat` | Klucz główny |
| `id_product`, `id_product_attribute`, `id_lang` | Cel |
| `title_full` | Do 512 znaków. Zastępuje tytuł dokumentu |
| `title_append` | Do 512 znaków. Dodawany po pierwotnym tytule |
| `active` | Zapisywane jako `1` |

`{prefix}combfeat_feature_product` — widok SQL, nie tabela, którą edytujesz. Suma `feature_product` i aktywnych wierszy `combfeat`. Wartość konfiguracji `COMBFEAT_FEATURE_VIEW` trzyma wersję widoku (`1`).

Inne klucze konfiguracji: `update_combfeat` i `updatev_combfeat` (sprawdzanie aktualizacji), `mypresta_updates` (przełącznik powiadomień).

### 11.3 Klasy PHP

| Plik | Klasa | Rola |
| --- | --- | --- |
| `combfeat.php` | `combfeat` | Klasa modułu: instalacja, konfiguracja, hooki, dane edytora produktu, dane do sklepu |
| `combfeat.php` | `combfeatUpdate` | Porównanie wersji i zapytanie do serwera aktualizacji |
| `classes/CombfeatImporter.php` | `CombfeatImporter` | Parsowanie CSV, rozpoznanie kombinacji i cechy, pobranie przykładu |
| `classes/CombfeatFacetedSearch.php` | `CombfeatFacetedSearch` | Widok, poprawka adaptera, przywrócenie, czyszczenie pamięci filtrów |
| `models/cfeat.php` | `cfeat` | Wiersze `combfeat`. `getAllByProductId`, `getFeaturesStaticByIdProduct`, `assign`, `insertDatas`, kasowanie |
| `models/cfeatdesc.php` | `cfeatdesc` | Wiersze `combfeat_details` |
| `models/cfeattitle.php` | `cfeattitle` | Wiersze `combfeat_title`. `saveTitleRow` kasuje wiersz, gdy oba tytuły są puste |

Katalogu `controllers/` nie ma.

### 11.4 Zasoby i szablony

| Plik | Gdzie | Rola |
| --- | --- | --- |
| `views/js/acplt.js` | Panel | Autouzupełnianie wyszukiwania cech |
| `views/js/admin-combfeat.js` | Panel | Akordeon, filtr, zakładki, flagi języków, tokeny, odświeżenie TinyMCE, skopiowanie treści edytora przed zapisem produktu |
| `views/css/combfeat.css` | Tylko panel | Układ bloku **Zawartość kombinacji** |
| `views/js/combfeat.js` | Sklep, tryb Zastąp | Odbudowuje specyfikację i opis |
| `views/js/combfeat-append.js` | Sklep, tryb Dołącz | To samo, z cechami produktu przed cechami kombinacji |
| `views/js/combfeat-title.js` | Sklep | `document.title` i `og:title` |
| `views/templates/admin/combfeat.tpl` | Zakładka Moduły produktu | Edytor |
| `views/templates/hook/product-details.tpl` | Karta produktu | Ukryty `#product-details-combfeat` z `data-product` |
| `import/combfeat-features-sample.csv` | Pobranie z konfiguracji | Przykład importu |

### 11.5 Instalacja i odinstalowanie

Instalacja tworzy trzy tabele, zapisuje domyślną konfigurację, rejestruje pięć hooków, wykonuje zmianę Twig i włącza integrację z nawigacją fasetową.

`disable` przywraca adapter nawigacji fasetowej. `enable` dopisuje brakujące klucze konfiguracji i ponownie włącza integrację, gdy przełącznik nawigacji fasetowej jest włączony.

Odinstalowanie przywraca adapter, usuwa widok, gdy nie jest już używany, i odinstalowuje moduł. Wiersze kombinacji w trzech tabelach zostają w bazie.

## 12. Wsparcie

Dziennik zmian i aktualizacje: [Product combination features na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html).

Zamówienia i pomoc: [konto klienta MyPresta.eu](https://mypresta.eu/my-account/orders/). E-mail: support@mypresta.eu.
