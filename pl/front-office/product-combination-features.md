---
title: "Funkcje kombinacji produktów - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop „Funkcje kombinacji produktów” od MyPresta.eu."
sidebar:
  label: "Funkcje kombinacji produktów - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product combination features na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-combination-features/)
>
> ---


# Funkcje kombinacji produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Funkcje kombinacji produktów”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Funkcje kombinacji produktów” i klikając „Konfiguruj”.

#### **Włącz funkcje dla kombinacji**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania podstawowej funkcjonalności przypisywania unikalnych cech do kombinacji produktów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Zobaczysz nową sekcję na stronach edycji produktu (w zakładce „Moduły”), gdzie możesz przypisać konkretne cechy i ich wartości do każdej kombinacji. Gdy klienci wybiorą kombinację w Front Office, karta danych produktu dynamicznie zaktualizuje się, aby pokazać te cechy specyficzne dla kombinacji.
  - *Gdy wyłączone:* Sekcja zarządzania cechami kombinacji nie pojawi się na stronach edycji produktu, a Front Office powróci do wyświetlania tylko cech głównego produktu, niezależnie od wybranej kombinacji.
- **Zalecana wartość:** **Włączone** (jeśli chcesz używać podstawowej funkcji modułu).
- **Scenariusz/przykład sprzedawcy:** Jeśli sprzedajesz koszulki i chcesz, aby „Materiał: 100% Bawełna” był dla białej koszulki, a „Materiał: 50% Bawełna, 50% Poliester” dla szarej koszulki, *musisz* to włączyć.

#### **Klasa CSS karty danych**

- **Co robi to ustawienie:** Pozwala określić klasę CSS lub ID elementu HTML, na który moduł powinien celować podczas aktualizowania sekcji cech na stronie produktu. Jest to kluczowe, aby moduł poprawnie zidentyfikował, gdzie wyświetlić cechy specyficzne dla kombinacji w Twoim motywie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione poprawnie:* Moduł znajdzie określony element i dynamicznie wstawi lub zaktualizuje w nim cechy kombinacji.
  - *Gdy ustawione niepoprawnie lub pozostawione puste:* Cechy kombinacji mogą nie pojawić się w Front Office lub mogą pojawić się w nieoczekiwanym miejscu, ponieważ moduł nie będzie wiedział, gdzie je umieścić.
- **Zalecana wartość:** Zależy to całkowicie od Twojego motywu PrestaShop. Popularną klasą jest `.product-features` lub `.data-sheet`. Może być konieczne sprawdzenie kodu HTML strony produktu, aby znaleźć prawidłowy selektor. W razie wątpliwości skonsultuj się z deweloperem motywu lub webmasterem.
- **Scenariusz/przykład sprzedawcy:** Twój motyw wyświetla cechy produktu wewnątrz `div` z klasą `product-specifications`. Wprowadziłbyś tutaj `.product-specifications`.

#### **Przepływ pracy**

- **Co robi to ustawienie:** Kontroluje, jak moduł obsługuje cechy po wybraniu kombinacji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Dołącz”:* Cechy specyficzne dla kombinacji zostaną *dodane* do cech głównego produktu. Zatem zobaczysz zarówno ogólne cechy produktu, jak i unikalne cechy kombinacji.
  - *Gdy ustawione na „Zastąp”:* Cechy specyficzne dla kombinacji *zastąpią* cechy głównego produktu. Zostaną wyświetlone tylko cechy istotne dla wybranej kombinacji.
- **Zalecana wartość:** **Zastąp** w większości przypadków, ponieważ zapewnia najbardziej precyzyjne informacje. Wybierz „Dołącz”, jeśli masz ogólne cechy, które dotyczą wszystkich kombinacji, plus specyficzne.
- **Scenariusz/przykład sprzedawcy:**
  - *Zastąp:* Dla laptopa możesz chcieć, aby „Procesor: i7”, „RAM: 16GB” całkowicie zastąpiły „Procesor: i5”, „RAM: 8GB”, gdy klient wybierze kombinację i7/16GB.
  - *Dołącz:* Dla koszulki możesz zawsze chcieć, aby wyświetlała się „Marka: MojaMarka” (cecha ogólna), ale następnie *dodać* „Materiał: Bawełna organiczna”, gdy zostanie wybrana konkretna kombinacja.

#### **Włącz opisy dla kombinacji**

- **Co robi to ustawienie:** Włącza lub wyłącza możliwość przypisywania unikalnych opisów do każdej kombinacji produktu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Na stronach edycji produktu (w zakładce „Moduły”) pojawi się nowe pole, umożliwiające wprowadzenie konkretnego opisu dla każdej kombinacji. Gdy klienci wybiorą kombinację, ten opis dynamicznie zastąpi główny opis produktu.
  - *Gdy wyłączone:* Pole opisu kombinacji nie pojawi się, a Front Office zawsze będzie wyświetlać główny opis produktu.
- **Zalecana wartość:** **Włączone** (jeśli potrzebujesz opisów specyficznych dla kombinacji).
- **Scenariusz/przykład sprzedawcy:** Sprzedajesz biżuterię na zamówienie. Produkt „Srebrny pierścionek” może mieć kombinację „Grawerowany: Tak”. Możesz użyć opisu kombinacji, aby wyjaśnić proces grawerowania i limity znaków, co nie jest istotne dla kombinacji „Grawerowany: Nie”.

#### **Klasa CSS / ID obiektu opisu**

- **Co robi to ustawienie:** Podobnie jak „Klasa CSS karty danych”, informuje moduł, który element HTML na stronie produktu zawiera główny opis produktu, który powinien zostać zastąpiony opisem specyficznym dla kombinacji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione poprawnie:* Moduł znajdzie określony element i dynamicznie zaktualizuje jego zawartość opisem kombinacji.
  - *Gdy ustawione niepoprawnie lub pozostawione puste:* Opis kombinacji może nie pojawić się lub może pojawić się w nieoczekiwanym miejscu.
- **Zalecana wartość:** Zależy to od Twojego motywu. Popularne selektory to `.product-description`, `#description_short` lub `#product-description-short`. Będziesz musiał sprawdzić kod HTML strony produktu.
- **Scenariusz/przykład sprzedawcy:** Twój motyw używa `div` z ID `product-description-full` dla głównego opisu. Wprowadziłbyś tutaj `#product-description-full`.

#### **Włącz meta tytuł dla kombinacji**

- **Co robi to ustawienie:** Włącza lub wyłącza możliwość ustawienia unikalnego meta tytułu dla każdej kombinacji produktu. Ten meta tytuł to to, co pojawia się w zakładce przeglądarki i jest używane przez wyszukiwarki.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Na stronach edycji produktu (w zakładce „Moduły”) pojawi się nowe pole, umożliwiające wprowadzenie konkretnego meta tytułu dla każdej kombinacji. Gdy klient wybierze kombinację, tytuł zakładki przeglądarki dynamicznie zaktualizuje się.
  - *Gdy wyłączone:* Pole meta tytułu kombinacji nie pojawi się, a zakładka przeglądarki zawsze będzie wyświetlać główny meta tytuł produktu.
- **Zalecana wartość:** **Włączone** (jeśli chcesz poprawić SEO dla konkretnych kombinacji lub zapewnić jaśniejsze tytuły zakładek przeglądarki).
- **Scenariusz/przykład sprzedawcy:** Dla produktu „Smartfon” możesz mieć kombinację „Kolor: Niebieski, Pamięć: 128GB”. Możesz ustawić jego meta tytuł na „Niebieski Smartfon 128GB - [Nazwa Twojego Sklepu]” dla lepszej widoczności w wyszukiwarkach.

#### **Domyślny tryb tytułu**

- **Co robi to ustawienie:** Definiuje, jak meta tytuł kombinacji jest konstruowany, jeśli nie ustawisz go jawnie dla kombinacji lub jeśli chcesz połączyć tytuł produktu z atrybutami kombinacji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Nazwa produktu + nazwa kombinacji”:* Meta tytuł będzie nazwą głównego produktu, po której nastąpią nazwy atrybutów wybranej kombinacji (np. „T-Shirt - Czerwony, Duży”).
  - *Gdy ustawione na „Nazwa kombinacji + nazwa produktu”:* Meta tytuł będzie nazwami atrybutów wybranej kombinacji, po których nastąpi nazwa głównego produktu (np. „Czerwony, Duży - T-Shirt”).
  - *Gdy ustawione na „Nazwa kombinacji”:* Użyte zostaną tylko nazwy atrybutów kombinacji (np. „Czerwony, Duży”).
  - *Gdy ustawione na „Nazwa produktu”:* Meta tytuł zawsze będzie nazwą głównego produktu, ignorując kombinacje.
- **Zalecana wartość:** **„Nazwa produktu + nazwa kombinacji”** lub **„Nazwa kombinacji + nazwa produktu”** dla dobrej równowagi między tożsamością produktu a specyfiką kombinacji.
- **Scenariusz/przykład sprzedawcy:** Sprzedajesz buty. Jeśli klient wybierze „Rozmiar 10, Kolor Czarny”, a wybrano „Nazwa produktu + nazwa kombinacji”, tytuł staje się „Buty do biegania - Rozmiar 10, Czarny”.

#### **Separator tytułu**

- **Co robi to ustawienie:** Pozwala zdefiniować znak lub ciąg znaków używany do oddzielania różnych części dynamicznie generowanego meta tytułu (np. między nazwą produktu a nazwą kombinacji).
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „-”:* Tytuł może wyglądać tak: „Nazwa produktu - Kombinacja”.
  - *Gdy ustawione na „|”:* Tytuł może wyglądać tak: „Nazwa produktu | Kombinacja”.
  - *Gdy pozostawione puste:* Części tytułu mogą się zlewać bez wyraźnego separatora.
- **Zalecana wartość:** **-** (łącznik) lub **|** (pionowa kreska) to popularne i jasne separatory.
- **Scenariusz/przykład sprzedawcy:** Jeśli domyślny tryb tytułu to „Nazwa produktu + nazwa kombinacji”, a separator jest ustawiony na „|”, tytuł może stać się „Moja Niesamowita Koszulka | Czerwona, Duża”.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie tworzy dedykowanych ekranów administracyjnych najwyższego poziomu. Zamiast tego integruje się bezpośrednio z istniejącą **Stroną edycji produktu** w Panelu administracyjnym PrestaShop.

- **Nazwa ekranu i lokalizacja w menu:**

  - Przejdź do **Katalog > Produkty**.
  - Edytuj istniejący produkt lub utwórz nowy.
  - Na stronie edycji produktu kliknij zakładkę **„Moduły”**.
  - Znajdziesz nową sekcję zatytułowaną **„Funkcje kombinacji produktów”** (lub podobną, w zależności od wersji modułu/tłumaczeń).
- **Dostępne działania i ustawienia:**

  - W tej sekcji zobaczysz listę wszystkich kombinacji skonfigurowanych dla bieżącego produktu.
  - Dla każdej kombinacji będziesz mieć pola do:
    - **Przypisz cechy:** Możesz wybrać istniejące cechy i ich wartości, a nawet tworzyć nowe wartości cech, specjalnie dla tej kombinacji. Moduł obsługuje wiele cech, co oznacza, że kombinacja może mieć kilka wartości dla tej samej cechy (np. „Materiał: Bawełna, Materiał: Spandex”).
    - **Wprowadź opis kombinacji:** Dostępny będzie edytor tekstu sformatowanego (jak standardowy edytor opisu PrestaShop) do wprowadzenia unikalnego opisu dla tej kombinacji.
    - **Wprowadź meta tytuł kombinacji:** Pole tekstowe do wprowadzenia unikalnego meta tytułu dla tej kombinacji.
  - **Zapisywanie zmian:** Pamiętaj, aby kliknąć główny przycisk „Zapisz” dla produktu, aby zastosować wszystkie zmiany specyficzne dla kombinacji.
- **Efekt zmian:**

  - Wszelkie cechy, opisy lub meta tytuły, które ustawisz tutaj, zostaną zapisane w bazie danych i dynamicznie wyświetlone na stronie produktu w Front Office, gdy klient wybierze odpowiednią kombinację.
  - Jeśli usuniesz kombinację, jej powiązane cechy, opisy i meta tytuły również zostaną usunięte.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

  1. Najpierw utwórz swój produkt i jego kombinacje jak zwykle w PrestaShop (w zakładce „Kombinacje”).
  2. Po utworzeniu kombinacji przejdź do zakładki **„Moduły”** na stronie edycji produktu.
  3. Dla każdej kombinacji starannie przypisz odpowiednie cechy, napisz konkretny opis i ustaw zoptymalizowany meta tytuł.
  4. Zapisz produkt.
  5. Zawsze testuj w Front Office, aby upewnić się, że cechy, opisy i tytuły aktualizują się poprawnie po wybraniu kombinacji.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz funkcje dla kombinacji | Włączone | Główny przełącznik dla funkcji kombinacji. |
| Konfiguracja modułu | Klasa CSS karty danych | `.product-features` (zależne od motywu) | Selektor CSS określający, gdzie wyświetlane są cechy kombinacji. |
| Konfiguracja modułu | Przepływ pracy | Zastąp | Jak cechy kombinacji współdziałają z głównymi cechami produktu (dołącz lub zastąp). |
| Konfiguracja modułu | Włącz opisy dla kombinacji | Włączone | Główny przełącznik dla opisów kombinacji. |
| Konfiguracja modułu | Klasa CSS / ID obiektu opisu | `#product-description-short` (zależne od motywu) | Selektor CSS określający, gdzie wyświetlane są opisy kombinacji. |
| Konfiguracja modułu | Włącz meta tytuł dla kombinacji | Włączone | Główny przełącznik dla meta tytułów kombinacji. |
| Konfiguracja modułu | Domyślny tryb tytułu | Nazwa produktu + nazwa kombinacji | Jak generowane są meta tytuły, jeśli nie są jawnie ustawione. |
| Konfiguracja modułu | Separator tytułu | `-` | Znak używany do oddzielania części meta tytułu. |
| Strona edycji produktu > Zakładka Moduły | Przypisz cechy dla kombinacji | N/A | Przypisz unikalne cechy i wartości do każdej kombinacji. |
| Strona edycji produktu > Zakładka Moduły | Opis kombinacji | N/A | Wprowadź unikalny opis w formacie rich text dla każdej kombinacji. |
| Strona edycji produktu > Zakładka Moduły | Meta tytuł kombinacji | N/A | Wprowadź unikalny meta tytuł dla każdej kombinacji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje cechy/opisy kombinacji nie wyświetlają się na stronie produktu.**
O:

1. **Sprawdź konfigurację modułu:** Upewnij się, że „Włącz funkcje dla kombinacji” i/lub „Włącz opisy dla kombinacji” są włączone w konfiguracji modułu.
2. **Zweryfikuj selektory CSS:** Ustawienia „Klasa CSS karty danych” i „Klasa CSS / ID obiektu opisu” są kluczowe. Muszą one dokładnie odpowiadać klasie CSS lub ID elementów w Twoim motywie, gdzie wyświetlane są cechy/opis. Użyj narzędzi deweloperskich przeglądarki (F12), aby sprawdzić stronę produktu i znaleźć prawidłowe selektory. W razie wątpliwości skonsultuj się z deweloperem motywu.
3. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami stare, buforowane treści uniemożliwiają wyświetlanie nowych danych modułu.
4. **Sprawdź ustawienia produktu:** Upewnij się, że faktycznie przypisałeś cechy/opisy do konkretnych kombinacji na stronie edycji produktu w zakładce „Moduły”.

**P: Cechy/opisy kombinacji pojawiają się, ale wyglądają na niestylizowane lub nie na miejscu.**
O: Jest to zazwyczaj konflikt CSS z Twoim motywem.

1. **Sprawdź narzędziami przeglądarki:** Użyj F12, aby zobaczyć, jakie reguły CSS są stosowane do danych wyjściowych modułu.
2. **Dostosuj klasę CSS:** Jeśli dane wyjściowe modułu są opakowane w ogólny `div`, może być konieczne dostosowanie „Klasy CSS karty danych” lub „Klasy CSS / ID obiektu opisu” do bardziej specyficznego kontenera, który Twój motyw już stylizuje.
3. **Niestandardowy CSS:** Może być konieczne dodanie niestandardowego CSS do arkusza stylów Twojego motywu (lub za pośrednictwem modułu niestandardowego CSS), aby ostylować cechy/opisy kombinacji tak, aby pasowały do wyglądu Twojego motywu.

**P: Moje meta tytuły kombinacji nie zmieniają się w zakładce przeglądarki.**
O:

1. **Włącz ustawienie:** Upewnij się, że „Włącz meta tytuł dla kombinacji” jest włączone w konfiguracji modułu.
2. **Ustaw tytuły:** Upewnij się, że wprowadziłeś konkretne meta tytuły dla swoich kombinacji na stronie edycji produktu.
3. **Zachowanie przeglądarki:** Niektóre przeglądarki mogą nie aktualizować natychmiast tytułu zakładki dla już otwartych zakładek. Spróbuj otworzyć stronę produktu w nowej zakładce lub wyczyść pamięć podręczną przeglądarki.
4. **Implikacje SEO:** Chociaż moduł aktualizuje tytuł po stronie klienta, aby wyszukiwarki mogły pobrać te tytuły specyficzne dla kombinacji, muszą być w stanie indeksować dynamicznie generowane treści. Upewnij się, że Twoja witryna jest możliwa do indeksowania i rozważ, czy te dynamiczne tytuły są naprawdę korzystne dla Twojej strategii SEO w porównaniu ze statycznymi tytułami produktów.

**P: Czy mogę używać tego modułu w sklepach wielojęzycznych?**
O: Tak, moduł w pełni obsługuje wiele języków. Podczas edycji cech, opisów lub meta tytułów kombinacji na stronie produktu zobaczysz standardowy selektor języka PrestaShop, umożliwiający wprowadzenie treści dla każdego języka.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Funkcje kombinacji produktów” (`combfeat`) rozszerza podstawowe zarządzanie produktami PrestaShop, wstrzykując niestandardowe pola i logikę do strony edycji produktu w Panelu administracyjnym oraz dynamicznie aktualizując zawartość Front Office w oparciu o wybrane kombinacje produktów. Wykorzystuje system hooków PrestaShop do bezproblemowej integracji bez modyfikowania plików rdzenia. Moduł działa głównie za pośrednictwem JavaScriptu na Front Office w celu dynamicznych aktualizacji oraz PHP na Back Office w celu konfiguracji i zarządzania danymi. Nie wprowadza nowych tabel bazy danych, ale przechowuje swoje dane w istniejących strukturach PrestaShop (prawdopodobnie `ps_product_attribute_feature` dla cech i `ps_product_attribute_lang` dla opisów/tytułów lub `ps_configuration` dla ustawień modułu).

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów Front Office ani Back Office. Jego logika wyświetlania i zapisywania danych kombinacji jest zintegrowana bezpośrednio z głównym plikiem modułu `combfeat.php` i za pośrednictwem JavaScriptu.

### 4.3 Klasy rdzenia i modele (`classes/`)

Ten moduł nie definiuje niestandardowych klas w katalogu `classes/`. Jego podstawowa logika znajduje się w głównym pliku `combfeat.php`, bezpośrednio wchodząc w interakcje z `ObjectModel` PrestaShop `Product` i `Combination` (ProductAttribute).

### 4.4 Zasoby JavaScript (`views/js/`)

- **`combfeat/views/js/acplt.js`**

  - **Zakres:** Prawdopodobnie Back Office (strona produktu w panelu administracyjnym).
  - **Odpowiedzialność:** Ten skrypt wydaje się być niestandardową biblioteką autouzupełniania lub komponentem używanym do wybierania cech i ich wartości dla kombinacji. Obsługiwałby żądania AJAX w celu pobrania dostępnych cech i wartości oraz zarządzał interfejsem użytkownika do ich dodawania/usuwania z kombinacji.
  - **Kluczowe interakcje:** Słuchacze zdarzeń dla pól wejściowych, wywołania AJAX do hooka modułu lub kontrolera administracyjnego w celu pobrania danych, manipulacja DOM w celu wyświetlania sugestii i wybranych elementów.
- **`combfeat/views/js/admin-combfeat.js`**

  - **Zakres:** Back Office (strona produktu w panelu administracyjnym, zakładka „Moduły”).
  - **Odpowiedzialność:** Jest to główny skrypt dla funkcjonalności modułu na stronie edycji produktu w Panelu administracyjnym PrestaShop. Inicjuje pola cech, opisów i meta tytułów kombinacji. Prawdopodobnie nasłuchuje zmian w wyborze kombinacji (jeśli takie są) i zarządza wyświetlaniem i zapisywaniem danych dla każdej kombinacji.
  - **Kluczowe interakcje:** Manipulacja DOM w celu wstrzyknięcia niestandardowych pól, słuchacze zdarzeń dla zmian wejściowych, potencjalnie wywołania AJAX w celu zapisania danych specyficznych dla kombinacji.
- **`combfeat/views/js/combfeat-append.js`**

  - **Zakres:** Front Office (strona produktu).
  - **Odpowiedzialność:** Ten skrypt jest przeznaczony specjalnie dla opcji przepływu pracy „Dołącz”. Po wybraniu kombinacji dynamicznie pobiera i *dodaje* cechy specyficzne dla kombinacji do istniejących cech produktu na Front Office.
  - **Kluczowe interakcje:** Nasłuchuje zdarzeń `updateProduct` lub podobnych (wyzwalanych przez wybór kombinacji), wywołania AJAX w celu pobrania danych kombinacji, manipulacja DOM w celu dołączenia cech do elementu określonego przez `combfeat_ds`.
- **`combfeat/views/js/combfeat-title.js`**

  - **Zakres:** Front Office (strona produktu).
  - **Odpowiedzialność:** Ten skrypt obsługuje dynamiczną aktualizację meta tytułu przeglądarki w oparciu o wybraną kombinację produktu.
  - **Kluczowe interakcje:** Nasłuchuje zdarzeń `updateProduct` lub podobnych, pobiera meta tytuł kombinacji (niestandardowy lub wygenerowany na podstawie ustawień modułu) i aktualizuje `document.title`.
- **`combfeat/views/js/combfeat.js`**

  - **Zakres:** Front Office (strona produktu).
  - **Odpowiedzialność:** Jest to główny skrypt Front Office dla modułu. Koordynuje dynamiczne wyświetlanie cech i opisów specyficznych dla kombinacji. Prawdopodobnie nasłuchuje zmian w kombinacjach produktów (np. wybór atrybutu) i wyzwala aktualizacje odpowiednich elementów DOM. Ten skrypt obsługiwałby przepływ pracy „Zastąp” dla cech i aktualizację opisu.
  - **Kluczowe interakcje:** Nasłuchuje zdarzeń `updateProduct` lub podobnych (np. `prestashop.on('updatedProduct', ...) `), wywołania AJAX w celu pobrania danych kombinacji, manipulacja DOM w celu aktualizacji elementów określonych przez `combfeat_ds` i `combfeat_description`.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`combfeat/views/css/combfeat.css`**
  - **Zakres:** Zarówno Front Office, jak i Back Office.
  - **Odpowiedzialność:** Zapewnia podstawowe style dla wstrzykniętych elementów modułu. Może to obejmować stylizację pól wejściowych cech/opisów kombinacji w Back Office lub dynamicznie aktualizowanych bloków cech/opisów w Front Office.
  - **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w klasy używane przez szablony i JavaScript modułu, takie jak `.combfeat-feature-list`, `.combfeat-description-wrapper` lub specyficzne style dla komponentu autouzupełniania. Programiści mogą potrzebować nadpisać je w pliku `custom.css` lub `theme.css` swojego motywu w celu idealnej integracji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`combfeat/views/templates/admin/combfeat.tpl`**

  - **Zakres:** Szablon administracyjny.
  - **Odpowiedzialność:** Ten szablon renderuje niestandardową sekcję w zakładce „Moduły” na stronie edycji produktu w Panelu administracyjnym. Wyświetla interfejs do zarządzania cechami, opisami i meta tytułami specyficznymi dla kombinacji. Prawdopodobnie iteruje przez wszystkie kombinacje produktów i udostępnia pola wejściowe dla każdej z nich.
  - **Kluczowe elementy:** Pętle dla kombinacji, pola wejściowe do wyboru cech (prawdopodobnie za pomocą komponentu `acplt.js`), edytor tekstu sformatowanego dla opisów, pole tekstowe dla meta tytułów.
- **`combfeat/views/templates/hook/product-details.tpl`**

  - **Zakres:** Szablon hooka Front Office.
  - **Odpowiedzialność:** Ten szablon jest prawdopodobnie podłączony do `displayProductAdditionalInfo` lub podobnych hooków w celu renderowania cech i/lub opisu specyficznych dla kombinacji na stronie produktu w Front Office. Zapewnia strukturę HTML, którą `combfeat.js` i `combfeat-append.js` będą dynamicznie wypełniać i aktualizować.
  - **Kluczowe elementy:** Placeholdery (np. puste `div`y z określonymi ID lub klasami), w których cechy i opisy kombinacji zostaną wstrzyknięte przez JavaScript.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy nowych niestandardowych tabel. Prawdopodobnie przechowuje cechy specyficzne dla kombinacji, rozszerzając relację `ps_product_attribute_feature` lub podobną, oraz opisy/meta tytuły kombinacji w `ps_product_attribute_lang` lub podobnej strukturze, kojarząc je z `id_product_attribute` i `id_lang`.
  - Ustawienia konfiguracji modułu (`combfeat_ds`, `combfeat_description` itp.) są przechowywane w tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayHeader` | Front Office | W sekcji `<head>` wszystkich stron Front Office. | Rejestruje zasoby CSS i JS Front Office (`combfeat.css`, `combfeat.js`, `combfeat-append.js`, `combfeat-title.js`). |
| `DisplayHeader` | Front Office | Alias dla `displayHeader`. | To samo co `displayHeader`. |
| `displayProductAdditionalInfo` | Front Office | Na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Renderuje szablon `product-details.tpl`, zapewniając placeholder dla cech/opisów kombinacji. |
| `ActionAdminControllerSetMedia` | Back Office | Gdy kontroler administracyjny jest ładowany i jego zasoby multimedialne są ustawiane. | Rejestruje zasoby CSS i JS Back Office (`combfeat.css`, `acplt.js`, `admin-combfeat.js`) dla strony edycji produktu. |
| `ActionProductUpdate` | Back Office | Po zaktualizowaniu produktu (w tym kombinacji). | Potencjalnie używane do zapisywania lub synchronizowania danych specyficznych dla kombinacji po przesłaniu formularza produktu. |
| `actionProductUpdate` | Back Office | Alias dla `ActionProductUpdate`. | To samo co `ActionProductUpdate`. |
| `displayAdminProductsExtra` | Back Office | Na stronie edycji produktu, zazwyczaj jako nowa zakładka lub sekcja. | Renderuje szablon `admin/combfeat.tpl`, tworząc sekcję „Funkcje kombinacji produktów” w zakładce „Moduły”. |
| `DisplayAdminProductsExtra` | Back Office | Alias dla `displayAdminProductsExtra`. | To samo co `displayAdminProductsExtra`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Funkcje kombinacji produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
