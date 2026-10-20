---
title: "Homefeatured multi slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Homefeatured multi slider od MyPresta.eu."
sidebar:
  label: "Homefeatured multi slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homefeatured multi slider na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homefeatured-multi-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/homefeatured-multi-slider/)
>
> ---


# Homefeatured multi slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do prawidłowego funkcjonowania sklepu PrestaShop. Ten moduł nie ma nietypowych ani specyficznych wymagań hostingowych poza standardowym środowiskiem PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Moduł „Homefeatured multi slider” oferuje dwa główne obszary konfiguracji: główną stronę konfiguracji modułu dla ustawień ogólnych oraz dedykowany ekran administracyjny do zarządzania sliderami produktów i kategoriami.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym ustawisz ogólne zachowanie i wygląd swojego slidera z wieloma wyróżnionymi produktami. Aby uzyskać do niego dostęp, przejdź do **Moduły > Menedżer modułów**, znajdź „Homefeatured multi slider” i kliknij „Konfiguruj”.

#### Zakładka Ustawienia ogólne

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Wyświetl w haku** | Określa, gdzie slider pojawi się na Twojej stronie internetowej. | *Gdy ustawione na `displayHome` (lub podobny hak głównej treści):* Slider będzie widocznym elementem na Twojej stronie głównej. *Gdy ustawione na `displayLeftColumn` lub `displayRightColumn`:* Slider pojawi się w paskach bocznych, zazwyczaj mniejszy. *Gdy ustawione na `displayFooter`:* Slider będzie na dole Twoich stron. | `displayHome` dla widocznego slidera na stronie głównej. | Chcesz, aby Twoje główne wyróżnione produkty były pierwszą rzeczą, którą klienci zobaczą na Twojej stronie głównej. |
| **Liczba produktów do wyświetlenia** | Kontroluje, ile produktów jest widocznych w sliderze w danym momencie. | *Gdy ustawione na `4`:* Cztery produkty będą wyświetlane obok siebie (jeśli pozwala na to miejsce). *Gdy ustawione na `1`:* Tylko jeden produkt będzie widoczny, często z większymi obrazami. | `4` lub `5` dla większości motywów, w zależności od rozmiarów obrazów produktów i projektu. | Masz duże obrazy produktów i chcesz pokazać mniej pozycji naraz, aby uzyskać lepsze szczegóły, lub masz małe obrazy i chcesz pokazać więcej. |
| **Prędkość slidera (ms)** | Ustawia, jak szybko slider przechodzi między produktami lub slajdami. Mierzone w milisekundach (1000ms = 1 sekunda). | *Gdy ustawione na `500`:* Przejścia są bardzo szybkie. *Gdy ustawione na `5000`:* Przejścia są wolne, dając klientom więcej czasu na obejrzenie każdego produktu. | `3000` (3 sekundy) do `5000` (5 sekund) dla komfortowego oglądania. | Chcesz dynamicznego, szybkiego wyświetlania produktów lub bardziej relaksującego, kontemplacyjnego przeglądania. |
| **Autoodtwarzanie slidera** | Określa, czy slider automatycznie obraca się przez produkty bez interakcji użytkownika. | *Gdy włączone (TAK):* Slider automatycznie przejdzie do następnego produktu po upływie ustawionej „Prędkości slidera”. *Gdy wyłączone (NIE):* Slider zmieni slajdy tylko wtedy, gdy klient kliknie strzałki nawigacyjne. | `TAK`, aby utrzymać zawartość dynamiczną i angażującą. | Chcesz zapewnić widoczność wszystkich wyróżnionych produktów, nawet jeśli klienci aktywnie nie klikają. |
| **Pokaż strzałki nawigacyjne** | Kontroluje widoczność strzałek „następny” i „poprzedni” na sliderze. | *Gdy włączone (TAK):* Strzałki pojawiają się po bokach slidera, umożliwiając ręczną nawigację. *Gdy wyłączone (NIE):* Klienci muszą polegać na autoodtwarzaniu lub innych metodach nawigacji (jeśli są dostępne). | `TAK` dla lepszej kontroli użytkownika i dostępności. | Chcesz, aby klienci mogli łatwo przeglądać produkty we własnym tempie. |
| **Pokaż kropki paginacji** | Kontroluje widoczność małych kropek lub wskaźników, zazwyczaj na dole slidera, reprezentujących każdy slajd. | *Gdy włączone (TAK):* Kropki pojawiają się, pokazując aktualną pozycję slajdu i umożliwiając bezpośrednie przejście do konkretnych slajdów. *Gdy wyłączone (NIE):* Kropki są ukryte. | `TAK` dla lepszej orientacji użytkownika i bezpośredniego dostępu do slajdów. | Chcesz, aby klienci wiedzieli, ile jest slajdów i mogli bezpośrednio przejść do konkretnego. |
| **Szerokość obrazu produktu (px)** | Ustawia szerokość obrazów produktów w sliderze. | *Gdy ustawione na `200`:* Obrazy będą miały 200 pikseli szerokości. *Gdy ustawione na `300`:* Obrazy będą miały 300 pikseli szerokości. Wpływa to na ogólny rozmiar i układ slidera. | `250` do `350` pikseli, w zależności od projektu Twojego motywu i „Liczby produktów do wyświetlenia”. | Twoje obrazy produktów są wysokiej rozdzielczości i chcesz, aby wyglądały na większe, lub potrzebujesz ich mniejszych, aby zmieścić więcej produktów. |
| **Wysokość obrazu produktu (px)** | Ustawia wysokość obrazów produktów w sliderze. | *Gdy ustawione na `200`:* Obrazy będą miały 200 pikseli wysokości. *Gdy ustawione na `300`:* Obrazy będą miały 300 pikseli wysokości. Działa to w połączeniu z szerokością, aby zachować proporcje lub przyciąć. | `250` do `350` pikseli, pasujące do wybranej szerokości dla kwadratowych obrazów, lub dostosowane do orientacji pionowej/poziomej. | Masz obrazy produktów o różnych proporcjach i chcesz ujednolicić ich wysokość wyświetlania. |
| **Kolor tła** | Pozwala ustawić niestandardowy kolor tła dla całego bloku slidera. | *Gdy ustawione na `#FFFFFF` (biały):* Tło slidera będzie białe. *Gdy ustawione na `#F0F0F0` (jasnoszary):* Tło będzie jasnoszare. | Pozostaw puste dla przezroczystości lub użyj koloru pasującego do Twojego motywu. | Chcesz, aby slider wyróżniał się wyraźnym kolorem tła lub płynnie wtapiał się w tło strony. |
| **Kolor tekstu** | Ustawia kolor nazw produktów i innego tekstu w sliderze. | *Gdy ustawione na `#000000` (czarny):* Tekst będzie czarny. *Gdy ustawione na `#333333` (ciemnoszary):* Tekst będzie ciemnoszary. | Kolor zapewniający dobry kontrast z wybranym kolorem tła. | Musisz upewnić się, że nazwy produktów są łatwe do odczytania na tle slidera. |
| **Kolor ceny** | Ustawia kolor cen produktów wyświetlanych w sliderze. | *Gdy ustawione na `#FF0000` (czerwony):* Ceny będą czerwone, często używane do wyprzedaży. *Gdy ustawione na `#008000` (zielony):* Ceny będą zielone. | Kolor, który sprawia, że ceny wyróżniają się, często kolor akcentu Twojej marki lub standardowy kolor ceny. | Chcesz, aby ceny były bardzo widoczne i przyciągały uwagę. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł zawiera dedykowaną sekcję w Twoim Panelu administracyjnym PrestaShop do zarządzania kategoriami wyróżnionych produktów i przypisywania do nich produktów.

#### Nazwa ekranu i lokalizacja menu: „Multi Featured Slider”

Tę sekcję znajdziesz, przechodząc do:
**Moduły > Menedżer modułów > Homefeatured multi slider > Konfiguruj**
Na stronie konfiguracji zobaczysz zakładkę lub link prowadzący do interfejsu zarządzania „Multi Featured Slider”. W PrestaShop 1.7+ może to pojawić się jako nowa pozycja menu w „Katalogu” lub „Modułach”, jeśli moduł zarejestruje własną zakładkę.

Ten ekran jest zarządzany przez `AdminprosliderController` (znajdujący się w `multihomefeatured/controllers/admin/adminproslider.php`).

**Dostępne akcje i ustawienia:**

Ten ekran zazwyczaj przedstawia listę utworzonych „kategorii wyróżnionych produktów” (określanych w kodzie jako „opinion”, ale funkcjonalnie działających jako kategorie dla Twojego slidera).

- **Tabela listująca:** Zobaczysz tabelę listującą wszystkie niestandardowe kategorie, które utworzyłeś dla swoich wyróżnionych produktów. Każdy wiersz prawdopodobnie pokaże:

  - **# (ID):** Unikalny identyfikator kategorii.
  - **Nazwa kategorii:** Nazwa, którą nadałeś tej grupie wyróżnionych produktów (np. „Bestsellery”, „Nowości”).
  - **Status:** Czy kategoria jest aktywna (widoczna w sliderze) czy nieaktywna.
  - **Akcje:** Przyciski „Edytuj” (modyfikuj nazwę kategorii, status i przypisuj produkty) lub „Usuń” kategorię.
- **Dodaj nową kategorię:** Będzie przycisk (np. „Dodaj nową kategorię” lub „Dodaj nową”) do tworzenia nowej grupy wyróżnionych produktów. Podczas dodawania lub edytowania kategorii zazwyczaj znajdziesz:

  - **Nazwa kategorii:** Pole wprowadzania do zdefiniowania nazwy kategorii wyróżnionych produktów (np. „Oferty sezonowe”, „Ulubione klientów”).
  - **Przełącznik Aktywny/Nieaktywny:** Przełącznik do włączania lub wyłączania wyświetlania tej konkretnej kategorii w sliderze front-office.
  - **Przypisanie produktu:** To jest podstawowa funkcjonalność. Prawdopodobnie zobaczysz pasek wyszukiwania lub listę dostępnych produktów. Możesz wyszukiwać produkty i dodawać je do tej konkretnej wyróżnionej kategorii. Produkty zazwyczaj można zmieniać kolejność w ramach kategorii.

**Efekt zmian:**

- **Dodanie nowej kategorii:** Tworzy nową zakładkę lub sekcję w sliderze front-office. Możesz następnie wypełnić ją konkretnymi produktami.
- **Edytowanie kategorii:**
  - Zmiana **Nazwy kategorii** aktualizuje etykietę wyświetlaną klientom w sliderze.
  - Przełączanie **Aktywny/Nieaktywny** natychmiast pokazuje lub ukrywa całą tę kategorię i jej produkty ze slidera front-office.
  - **Dodawanie/Usuwanie produktów:** Bezpośrednio aktualizuje, które produkty pojawiają się w tej konkretnej kategorii slidera.
  - **Zmiana kolejności produktów:** Zmienia kolejność, w jakiej produkty pojawiają się w sliderze tej kategorii.
- **Usuwanie kategorii:** Trwale usuwa kategorię i wszystkie przypisane do niej produkty ze slidera. Same produkty nie są usuwane ze sklepu.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1. **Zaplanuj swoje kategorie:** Przed utworzeniem zdecyduj o logicznych grupach dla swoich wyróżnionych produktów (np. „Nowości”, „W promocji”, „Bestsellery”, „Wybory sezonowe”).
2. **Utwórz kategorie:** Użyj przycisku „Dodaj nową”, aby utworzyć każdą kategorię, nadając jej jasną, opisową nazwę.
3. **Przypisz produkty:** Dla każdej kategorii użyj interfejsu przypisywania produktów, aby wyszukać i dodać odpowiednie produkty. Pamiętaj, aby zapisać zmiany.
4. **Uporządkuj produkty:** Ułóż produkty w każdej kategorii w kolejności, w jakiej chcesz, aby się pojawiały.
5. **Przejrzyj i aktywuj:** Gdy będziesz zadowolony, upewnij się, że kategoria jest ustawiona na „Aktywna”.
6. **Sprawdź Front-Office:** Zawsze weryfikuj zmiany w swoim działającym sklepie, aby upewnić się, że slider wygląda i działa zgodnie z oczekiwaniami.
7. **Regularne aktualizacje:** Okresowo aktualizuj swoje wyróżnione kategorie o nowe produkty, artykuły sezonowe lub artykuły, które chcesz promować. Usuwaj starsze lub wyprzedane pozycje, aby slider był świeży i aktualny.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Wyświetl w haku | `displayHome` | Kontroluje, gdzie pojawia się slider (strona główna, kolumny, stopka). |
|  | Liczba produktów do wyświetlenia | `4` | Ile produktów jest widocznych jednocześnie w sliderze. |
|  | Prędkość slidera (ms) | `3000` - `5000` | Prędkość automatycznych przejść slajdów. |
|  | Autoodtwarzanie slidera | `TAK` | Slider automatycznie obraca produkty. |
|  | Pokaż strzałki nawigacyjne | `TAK` | Wyświetla strzałki do ręcznej nawigacji. |
|  | Pokaż kropki paginacji | `TAK` | Wyświetla kropki do wskazywania slajdów i bezpośredniego dostępu. |
|  | Szerokość obrazu produktu (px) | `250` - `350` | Ustawia szerokość obrazów produktów w sliderze. |
|  | Wysokość obrazu produktu (px) | `250` - `350` | Ustawia wysokość obrazów produktów w sliderze. |
|  | Kolor tła | Pozostaw puste / Dopasowany do motywu | Ustawia kolor tła bloku slidera. |
|  | Kolor tekstu | Dopasowany do motywu / `#333333` | Ustawia kolor nazw produktów i opisów. |
|  | Kolor ceny | Dopasowany do motywu / Kolor akcentu | Ustawia kolor cen produktów. |
| **Ekran administracyjny „Multi Featured Slider”** | Dodaj/Edytuj nazwę kategorii | Opisowa nazwa (np. „Bestsellery”) | Tworzy/modyfikuje zakładkę/sekcję w sliderze. |
|  | Status kategorii (Aktywna/Nieaktywna) | `Aktywna` | Pokazuje lub ukrywa całą kategorię wyróżnionych produktów. |
|  | Przypisz produkty do kategorii | N/A | Wybiera, które produkty pojawiają się w konkretnej kategorii slidera. |
|  | Zmień kolejność produktów | N/A | Zmienia kolejność wyświetlania produktów w kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój slider nie wyświetla się na stronie głównej po konfiguracji.**

- **O:** Najpierw sprawdź, czy moduł jest włączony i skonfigurowany do wyświetlania w prawidłowym haku (np. `displayHome`) na głównej stronie konfiguracji modułu. Po drugie, upewnij się, że utworzyłeś co najmniej jedną kategorię „Multi Featured Slider” i przypisałeś do niej produkty, a także, że kategoria jest ustawiona na „Aktywna” na dedykowanym ekranie administracyjnym. Na koniec wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).

**P2: Slider wygląda na uszkodzony lub źle wyrównany w moim sklepie.**

- **O:** Jest to często konflikt CSS z Twoim motywem.
  1. **Sprawdź wymiary obrazu:** Przejdź do strony konfiguracji modułu i zweryfikuj ustawienia „Szerokość obrazu produktu” i „Wysokość obrazu produktu”. Upewnij się, że są one odpowiednie dla Twojego motywu i liczby produktów, które chcesz wyświetlić.
  2. **Nadpisania motywu:** Twój motyw może mieć sprzeczne style. Spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby sprawdzić, czy problem nadal występuje. Jeśli się rozwiąże, prawdopodobnie CSS Twojego motywu nadpisuje style modułu. Może być konieczne, aby programista internetowy utworzył niestandardowe nadpisanie CSS w pliku `custom.css` Twojego motywu.
  3. **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną przeglądarki i pamięć podręczną Smarty PrestaShop po wprowadzeniu zmian związanych z projektem.

**P3: Jak zmienić kolejność produktów w kategorii slidera?**

- **O:** Przejdź do dedykowanego ekranu administracyjnego „Multi Featured Slider”. Edytuj konkretną kategorię, którą chcesz zmienić kolejność. W interfejsie przypisywania produktów powinieneś mieć możliwość przeciągania i upuszczania produktów, aby zmienić ich kolejność, lub mogą być strzałki w górę/w dół obok każdego produktu. Pamiętaj, aby zapisać zmiany.

**P4: Czy mogę przetłumaczyć nazwy kategorii na różne języki?**

- **O:** Tak, moduły PrestaShop zazwyczaj obsługują wprowadzanie wielojęzyczne dla pól takich jak nazwy kategorii. Podczas edytowania nazwy kategorii na ekranie administracyjnym „Multi Featured Slider” poszukaj selektora języka (zazwyczaj ikony flagi) obok pola wprowadzania. Kliknij go, aby wprowadzić nazwę dla każdego zainstalowanego języka.

**P5: Slider jest za szybki/wolny, lub autoodtwarzanie nie działa.**

- **O:** Dostosuj ustawienie „Prędkość slidera (ms)” na głównej stronie konfiguracji modułu. Wyższa liczba oznacza wolniejsze przejście. Upewnij się, że „Autoodtwarzanie slidera” jest ustawione na `TAK`, jeśli chcesz, aby obracał się automatycznie. Pamiętaj, aby zapisać i wyczyścić pamięć podręczną.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Homefeatured multi slider” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `Homefeatured multi slider` (nazwa wewnętrzna `multihomefeatured`) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując wzorzec MVC. Składa się głównie z:

- Głównego pliku modułu (`ajax_multihomefeatured.php`) obsługującego instalację, deinstalację i główny formularz konfiguracji (`getContent()`).
- Kontrolera front-office (`default.php`) dla potencjalnych interakcji AJAX lub specyficznej logiki renderowania front-office.
- Kontrolera administracyjnego (`AdminprosliderController.php`) do zarządzania niestandardowymi „kategoriami wyróżnionych produktów” (określanymi jako `opinion` w kontekście bazy danych, ale funkcjonalnie działającymi jako kategorie).
- Szablonów Smarty do renderowania zarówno konfiguracji back-office, jak i elementów slidera front-office.
- JavaScript dla funkcjonalności slidera i CSS dla stylizacji.

Moduł nie wydaje się używać niestandardowych klas `ObjectModel` na podstawie dostarczonego spisu, co sugeruje, że może przechowywać swoje niestandardowe przypisania kategorii i produktów bezpośrednio w `ps_configuration` lub niestandardowej tabeli zarządzanej przez `AdminprosliderController`.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `multihomefeatured/controllers/front/default.php`
  - **Nazwa klasy i klasa nadrzędna**: `MultihomefeaturedDefaultModuleFrontController` rozszerzający `ModuleFrontController`.
  - **Odpowiedzialność**: Ten kontroler jest prawdopodobnie używany do obsługi specyficznych żądań front-office, potencjalnie dla wywołań AJAX związanych z zawartością slidera, lub do renderowania samodzielnej strony, jeśli moduł taką oferował. Biorąc pod uwagę główną funkcję modułu jako slidera, może on obsługiwać dynamiczne ładowanie treści lub specyficzne pobieranie danych produktów dla slidera.

#### Kontrolery administracyjne Back-Office

- `multihomefeatured/controllers/admin/adminproslider.php`
  - **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza niestandardowymi kategoriami „Multi Featured Slider” i powiązanymi z nimi produktami. Prawdopodobnie pojawia się jako podzakładka lub dedykowany wpis w menu Panelu administracyjnego PrestaShop, często w sekcji „Katalog” lub „Moduły”. Zarządzana encja to koncepcyjnie „kategoria wyróżnionych produktów”, którą moduł wewnętrznie nazywa `opinion` w swoich interakcjach z bazą danych.
  - **Odpowiedzialność**: Ten kontroler zapewnia interfejs CRUD (Create, Read, Update, Delete) dla tych niestandardowych kategorii. Obsługuje:
    - Listowanie istniejących kategorii.
    - Wyświetlanie formularzy do dodawania nowych kategorii.
    - Wyświetlanie formularzy do edycji istniejących kategorii (w tym przypisywanie i zmienianie kolejności produktów).
    - Przetwarzanie przesłanych formularzy do tworzenia/aktualizacji kategorii.
    - Obsługę usuwania kategorii.
    - Zarządzanie powiązaniem między kategoriami a konkretnymi produktami PrestaShop.

### 4.3 Klasy podstawowe i modele (`classes/`)

Na podstawie dostarczonego spisu, w katalogu `classes/` nie ma jawnie wymienionych niestandardowych klas PHP. Sugeruje to, że:

1. Moduł może być starszy i bezpośrednio manipulować tabelami bazy danych bez dedykowanego `ObjectModel`.
2. `AdminprosliderController` może bezpośrednio obsługiwać interakcje z bazą danych dla swojej encji `opinion`.
3. Główny plik modułu (`ajax_multihomefeatured.php`) może zawierać całą niezbędną logikę do konfiguracji i podstawowej obsługi danych.

Jeśli niestandardowe dane (takie jak „kategorie wyróżnionych produktów” i ich przypisania produktów) są przechowywane, to albo w `ps_configuration` (dla prostych par klucz-wartość), albo w niestandardowej tabeli bazy danych, która jest zarządzana bezpośrednio przez `AdminprosliderController` bez formalnej definicji `ObjectModel` w `classes/`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `multihomefeatured/js/jquery.catslider.16.js`
  - **Zakres**: Front-office.
  - **Opis**: Prawdopodobnie wersja wtyczki jQuery „category slider” lub „content slider”, specjalnie dostosowana lub przeznaczona dla PrestaShop 1.6.x. Obsługiwałaby podstawową animację slidera, nawigację i responsywność.
- `multihomefeatured/js/jquery.catslider.js`
  - **Zakres**: Front-office.
  - **Opis**: Podobnie jak powyżej, potencjalnie bardziej ogólna wersja lub dla innych wersji PrestaShop. Ten skrypt inicjowałby slider, zarządzał przejściami, autoodtwarzaniem i interakcją użytkownika (kliknięcia, przeciągnięcia).
- `multihomefeatured/js/jscolor/jscolor.js`
  - **Zakres**: Back-office.
  - **Opis**: Jest to biblioteka JavaScript do wyboru kolorów. Jest używana w formularzu konfiguracji modułu w back-office, aby zapewnić przyjazny dla użytkownika interfejs do wybierania kolorów (np. dla tła, tekstu, kolorów cen). Wiąże się z określonymi polami wejściowymi, aby wyświetlić selektor kolorów.
- `multihomefeatured/js/modernizr.custom.63321.js`
  - **Zakres**: Front-office.
  - **Opis**: Modernizr to biblioteka JavaScript, która wykrywa funkcje HTML5 i CSS3 w przeglądarce użytkownika. Jest często używana do zapewniania wykrywania funkcji i mechanizmów awaryjnych, zapewniając prawidłowe działanie slidera w różnych przeglądarkach, zwłaszcza starszych, które mogą nie mieć pewnych możliwości przejść lub animacji CSS3.
- `multihomefeatured/js/script.js`
  - **Zakres**: Front-office i/lub Back-office.
  - **Opis**: Jest to prawdopodobnie główny niestandardowy plik JavaScript dla modułu. Zawierałby:
    - Logikę inicjalizacji dla wtyczki `jquery.catslider`, przekazując opcje konfiguracji z ustawień modułu.
    - Słuchacze zdarzeń dla strzałek nawigacyjnych, kropek paginacji lub niestandardowych interakcji.
    - Potencjalnie wywołania AJAX do kontrolera front-office `default.php` dla dynamicznego ładowania treści.
    - Wszelkie specyficzne manipulacje DOM lub ulepszenia interfejsu użytkownika związane ze sliderem.
    - W back-office może zawierać skrypty do wyszukiwania i przypisywania produktów w formularzach `AdminprosliderController`.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `multihomefeatured/css/style.css`
  - **Zakres**: Front-office.
  - **Opis**: Jest to główny arkusz stylów dla slidera front-office. Definiuje wygląd wizualny kontenera slidera, elementów produktów, strzałek nawigacyjnych, kropek paginacji, tytułów produktów, cen i wszelkich innych elementów wyświetlanych w sliderze.
  - **Kluczowe selektory klas CSS**: Programiści mogą spodziewać się klas takich jak `.multihomefeatured-slider`, `.slider-item`, `.product-image`, `.product-title`, `.product-price`, `.slider-nav-arrow`, `.slider-pagination` itp., które można nadpisać w pliku `custom.css` niestandardowego motywu lub za pomocą mechanizmu nadpisywania motywu PrestaShop.
- `multihomefeatured/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
  - **Zakres**: Back-office.
  - **Opis**: Ten arkusz stylów jest częścią biblioteki jQuery UI, a konkretnie motywu „UI-lightness”. Jest prawdopodobnie używany w back-office do stylizacji elementów takich jak selektory dat, okna dialogowe lub inne interaktywne komponenty, które mogą być częścią formularzy `AdminprosliderController` (np. do autouzupełniania wyszukiwania produktów, jeśli zaimplementowano za pomocą jQuery UI).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony haków (`views/templates/hook/`)**:
  - `multihomefeatured/header.tpl`
    - **Hak**: Prawdopodobnie `displayHeader` lub `actionFrontControllerSetMedia`.
    - **Wyjście**: Zawiera pliki CSS i JavaScript specyficzne dla modułu (`jquery.catslider.js`, `modernizr.custom.63321.js`, `style.css`, `script.js`) w sekcji `<head>` front-office, zapewniając ich załadowanie przed renderowaniem slidera.
  - `multihomefeatured/home.tpl`
    - **Hak**: Konfigurowalny (np. `displayHome`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).
    - **Wyjście**: Jest to główny szablon dla wyświetlania slidera w front-office. Zawiera strukturę HTML dla całego slidera wielokategorialnego, w tym zakładki dla różnych kategorii i kontener na slajdy produktów. Iteruje przez skonfigurowane kategorie i produkty, aby zbudować slider.
  - `multihomefeatured/homeTab.tpl`
    - **Hak**: Renderowany wewnętrznie przez `home.tpl`.
    - **Wyjście**: Ten szablon prawdopodobnie renderuje pojedynczą zakładkę lub element nawigacyjny dla jednej z kategorii wyróżnionych produktów (np. „Bestsellery”, „Nowości”). Jest częścią nawigacji do przełączania między różnymi sliderami produktów.
  - `multihomefeatured/homeTabContents.tpl`
    - **Hak**: Renderowany wewnętrznie przez `home.tpl`.
    - **Wyjście**: Ten szablon renderuje rzeczywistą listę produktów dla pojedynczej kategorii wyróżnionych produktów. Zawiera pętlę, która wyświetla pojedyncze obrazy produktów, nazwy, ceny i potencjalnie przyciski „Dodaj do koszyka”, wszystko opakowane w strukturę wymaganą przez wtyczkę `jquery.catslider`.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:

  - Moduł nie definiuje jawnie niestandardowych klas `ObjectModel`, ale `AdminprosliderController` zarządza encją określaną jako `opinion`. To silnie sugeruje, że moduł tworzy co najmniej jedną niestandardową tabelę, prawdopodobnie nazwaną `ps_multihomefeatured_opinion` (lub podobną, zgodnie z konwencją prefiksu `ps_` PrestaShop) do przechowywania:
    - `id_multihomefeatured_opinion` (klucz podstawowy)
    - `name` (dla nazwy kategorii, potencjalnie wielojęzycznej)
    - `active` (wartość logiczna dla statusu kategorii)
    - Inne pola związane z konfiguracją kategorii.
  - Dodatkowo, istniałaby tabela łącząca, np. `ps_multihomefeatured_opinion_product`, do przechowywania relacji wiele-do-wielu między tymi kategoriami a wpisami `ps_product`, w tym pola `position` do sortowania.
  - Ustawienia konfiguracji modułu (takie jak prędkość slidera, wymiary obrazu, kolory) są zazwyczaj przechowywane w tabeli `ps_configuration` z kluczami poprzedzonymi nazwą modułu (np. `MULTIHOMEFEATURED_SLIDER_SPEED`).
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS i JavaScript modułu dla funkcjonalności front-office. |
| `displayHome` | Główny obszar treści strony głównej. | Renderuje główny slider produktów wielokategorialnych na stronie głównej. |
| `displayLeftColumn` | Lewy pasek boczny stron front-office. | Renderuje mniejszą wersję slidera w lewej kolumnie. |
| `displayRightColumn` | Prawy pasek boczny stron front-office. | Renderuje mniejszą wersję slidera w prawej kolumnie. |
| `displayFooter` | Dolna sekcja każdej strony front-office. | Renderuje slider w obszarze stopki. |
| `displayProductExtraContent` (lub podobny hak strony produktu) | Na stronie produktu, poniżej szczegółów produktu. | Potencjalnie używany do wyświetlania powiązanych produktów w sliderze na stronach produktów. |
| `actionFrontControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler front-office. | Bardziej solidny sposób rejestrowania zasobów (CSS/JS) dla konkretnych stron lub globalnie. |
| `actionModuleInstall` | Podczas instalacji modułu. | Tworzy tabele bazy danych, ustawia domyślne wartości konfiguracji, rejestruje haki. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Czyści tabele bazy danych, usuwa wartości konfiguracji, wyrejestrowuje haki. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Homefeatured multi slider”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Najnowsze wersje modułu możesz pobrać z historii zamówień. W celu uzyskania pomocy technicznej lub konkretnych zapytań, skontaktuj się bezpośrednio z obsługą MyPresta.eu za pośrednictwem swojego konta klienta.
