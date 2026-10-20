---
title: "Presta Pro Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Presta Pro Slider PrestaShop od MyPresta.eu."
sidebar:
  label: "Presta Pro Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Presta Pro Slider na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/presta-pro-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/presta-pro-slider/)
>
> ---


# Presta Pro Slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Presta Pro Slider)

Jest to główny ekran konfiguracji, na którym zarządzasz ogólnymi ustawieniami slidera oraz dodajesz/edytujesz poszczególne slajdy.

#### Ogólne ustawienia slidera

-   **Co robi to ustawienie:** Te ustawienia kontrolują ogólny wygląd i zachowanie Twojego slidera, takie jak jego wymiary, szybkość animacji i miejsce wyświetlania na Twojej stronie.
-   **Wpływ zmiany tego ustawienia:** Dostosowanie tych wartości bezpośrednio wpłynie na to, jak slider wygląda i działa dla Twoich klientów.

| Ustawienie / Opcja | Co robi | Wpływ zmiany | Zalecana wartość | Scenariusz sprzedawcy / Przykład |
| :----------------- | :------ | :----------- | :---------------- | :------------------------------- |
| **Szerokość slidera (px)** | Ustawia całkowitą szerokość slidera w pikselach. | *Jeśli ustawiono na 1000:* Slider będzie miał 1000 pikseli szerokości. *Jeśli ustawiono na 500:* Slider będzie miał 500 pikseli szerokości. | `100%` (dla pełnej szerokości) lub konkretna wartość w pikselach, np. `1170` (często dla obszarów treści). | Chcesz, aby Twój slider rozciągał się na cały obszar treści Twojej strony głównej, który ma 1170px szerokości. Wprowadziłbyś `1170`. Jeśli chcesz, aby był responsywny i zajmował całą dostępną szerokość, użyj `100%`. |
| **Wysokość slidera (px)** | Ustawia całkowitą wysokość slidera w pikselach. | *Jeśli ustawiono na 400:* Slider będzie miał 400 pikseli wysokości. *Jeśli ustawiono na 250:* Slider będzie miał 250 pikseli wysokości. | `350` - `500` (w zależności od zawartości obrazu). | Masz wysokiej jakości obrazy banerowe, które najlepiej wyglądają na określonej wysokości. Ustawisz to na `450`, aby upewnić się, że Twoje obrazy są wyświetlane bez zbytniego rozciągania lub ściskania. |
| **Szybkość animacji (ms)** | Kontroluje szybkość przejścia między slajdami, w milisekundach. | *Jeśli ustawiono na 500:* Slajdy przechodzą szybko (0.5 sekundy). *Jeśli ustawiono na 2000:* Slajdy przechodzą wolno (2 sekundy). | `1000` (1 sekunda) | Chcesz płynnego, zauważalnego przejścia między slajdami promocyjnymi, ale nie tak wolnego, żeby klienci się nudzili. Ustawienie na `1000` zapewnia dobrą równowagę. |
| **Autoodtwarzanie** | Określa, czy slider automatycznie przechodzi do następnego slajdu. | *Gdy włączone (TAK):* Slajdy będą automatycznie zmieniać się po ustawionym opóźnieniu. *Gdy wyłączone (NIE):* Slajdy będą zmieniać się tylko, gdy klient kliknie strzałki nawigacyjne lub kropki. | `TAK` | Chcesz, aby Twoje główne promocje automatycznie cyklicznie wyświetlały się na stronie głównej bez interakcji klienta. |
| **Szybkość autoodtwarzania (ms)** | Jeśli autoodtwarzanie jest włączone, ustawia opóźnienie przed pojawieniem się następnego slajdu, w milisekundach. | *Jeśli ustawiono na 5000:* Każdy slajd wyświetla się przez 5 sekund. *Jeśli ustawiono na 3000:* Każdy slajd wyświetla się przez 3 sekundy. | `5000` (5 sekund) | Masz dużo tekstu na slajdach i chcesz dać klientom wystarczająco dużo czasu na jego przeczytanie, zanim pojawi się następny slajd. Ustawienie na `7000` (7 sekund) byłoby odpowiednie. |
| **Wyświetl na haku** | Wybiera hak PrestaShop, na którym slider będzie wyświetlany. | *Jeśli ustawiono na `displayHeader`*: Slider pojawia się na górze każdej strony. *Jeśli ustawiono na `displayLeftColumn`*: Slider pojawia się w lewym pasku bocznym. | `displayHome` (jeśli dostępne, w przeciwnym razie `displayHeader` lub `displayTop`) | Chcesz, aby slider był widocznym elementem na Twojej stronie głównej. Wybrałbyś `displayHome` lub `displayTop`. Jeśli chcesz go na stronach produktów, możesz wybrać `displayProductFooter`. |
| **Kolor tła** | Ustawia kolor tła kontenera slidera. | *Jeśli ustawiono na #FFFFFF:* Tło będzie białe. *Jeśli ustawiono na #000000:* Tło będzie czarne. | `Pozostaw puste` (dla przezroczystego) lub kolor pasujący do Twojego motywu. | Twój motyw ma jasne tło i chcesz, aby slider płynnie się w nie wtopił. Ustawisz to na `#FFFFFF`. |
| **Kolor tekstu** | Ustawia domyślny kolor tekstu w sliderze (podpisy, opisy). | *Jeśli ustawiono na #000000:* Tekst będzie czarny. *Jeśli ustawiono na #FF0000:* Tekst będzie czerwony. | `#333333` (ciemnoszary) | Obrazy w Twoim sliderze są jasne i potrzebujesz ciemnego tekstu, aby zapewnić czytelność. Ustawisz to na `#333333`. |

#### Sekcja zarządzania slajdami

Ta sekcja umożliwia dodawanie, edytowanie i usuwanie poszczególnych slajdów, które tworzą Twój pokaz slajdów.

-   **Przycisk Dodaj nowy slajd:** Kliknij, aby otworzyć formularz tworzenia zupełnie nowego slajdu.
-   **Lista istniejących slajdów:** Wyświetla tabelę wszystkich Twoich aktualnie aktywnych slajdów, zazwyczaj z opcjami edycji lub usunięcia.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

#### AdminprosliderController (Panel administracyjny > Moduły > Presta Pro Slider > Konfiguruj > „Dodaj nowy slajd” lub „Edytuj” istniejący slajd)

Ten ekran pojawia się po kliknięciu „Dodaj nowy slajd” lub przycisku „Edytuj” obok istniejącego slajdu w głównej konfiguracji. Pozwala on zdefiniować zawartość i zachowanie każdego pojedynczego slajdu.

-   **Nazwa ekranu i lokalizacja w menu:** Dostępne z głównej strony konfiguracji modułu po kliknięciu „Dodaj nowy slajd” lub ikony edycji dla istniejącego slajdu.
-   **Dostępne akcje i ustawienia:** Ten formularz umożliwia wprowadzenie wszystkich szczegółów dla pojedynczego slajdu.

| Ustawienie / Opcja | Co robi | Wpływ zmiany | Zalecana wartość | Scenariusz sprzedawcy / Przykład |
| :----------------- | :------ | :----------- | :---------------- | :------------------------------- |
| **Tytuł slajdu (podpis)** | Główny nagłówek lub krótki tekst wyświetlany na slajdzie. | Ten tekst pojawi się wyraźnie na Twoim slajdzie, zazwyczaj większą czcionką. | Zachowaj zwięzłość i wyrazistość. | „Letnia wyprzedaż!” lub „Nowości” |
| **Opis slajdu** | Dłuższy tekst zawierający więcej szczegółów na temat zawartości slajdu. | Ten tekst pojawi się pod tytułem, oferując klientowi więcej informacji. | Podaj wystarczająco dużo szczegółów, ale nie przytłaczaj. | „Do 50% zniżki na wszystkie stroje kąpielowe przez ograniczony czas!” |
| **Obraz slajdu** | Główny obraz tła dla tego konkretnego slajdu. | Ten obraz będzie wizualnym centrum Twojego slajdu. | Wysokiej jakości, odpowiedni obraz o dobrej rozdzielczości. | Atrakcyjne zdjęcie modelki w nowej sukience do promocji mody. |
| **Adres URL linku** | Adres internetowy (URL), na który klienci zostaną przekierowani po kliknięciu tego slajdu. | *Jeśli ustawiono:* Kliknięcie slajdu przenosi klienta pod ten adres URL. *Jeśli puste:* Slajd nie będzie klikalny. | Prawidłowy adres URL do produktu, kategorii lub strony informacyjnej. | Link do strony kategorii „Nowości”: `https://twojskep.com/nowosci` |
| **Otwórz w nowym oknie** | Określa, czy adres URL linku otwiera się w nowej karcie/oknie przeglądarki. | *Gdy włączone (TAK):* Link otwiera się w nowej karcie, utrzymując Twój sklep otwarty w oryginalnej karcie. *Gdy wyłączone (NIE):* Link otwiera się w tej samej karcie, nawigując z dala od bieżącej strony. | `TAK` (ogólnie zalecane dla linków zewnętrznych lub promocji) | Linkujesz do zewnętrznego wpisu na blogu lub profilu w mediach społecznościowych. Włączyłbyś to, aby utrzymać klientów w Twoim sklepie PrestaShop. |
| **Aktywny** | Kontroluje, czy ten slajd jest aktualnie widoczny w sliderze. | *Gdy włączone (TAK):* Slajd będzie częścią pokazu slajdów. *Gdy wyłączone (NIE):* Slajd będzie ukryty, ale nie usunięty, co pozwoli na jego ponowne aktywowanie później. | `TAK` dla aktywnych promocji. | Masz promocję sezonową, która się skończyła, ale możesz ją ponownie uruchomić w przyszłym roku. Ustawisz ją na `NIE` zamiast usuwać. |
| **Kolejność / Pozycja** | Ustawia kolejność wyświetlania tego slajdu względem innych. | Slajdy z niższymi numerami pojawiają się wcześniej w sekwencji. | `1`, `2`, `3` itd., w żądanej kolejności. | Chcesz, aby slajd „Letnia wyprzedaż” pojawił się jako pierwszy, a następnie „Nowości”. Ustawisz „Letnia wyprzedaż” na `1`, a „Nowości” na `2`. |

-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zaplanuj promocje:** Zdecyduj, jakie produkty, kategorie lub wiadomości chcesz wyróżnić.
    2.  **Przygotuj obrazy:** Upewnij się, że masz wysokiej jakości obrazy, które pasują do wymiarów slidera.
    3.  **Dodaj nowe slajdy:** Użyj przycisku „Dodaj nowy slajd”, aby utworzyć nową zawartość. Wypełnij wszystkie szczegóły, w tym tytuł, opis, obraz i link.
    4.  **Uporządkuj slajdy:** Dostosuj „Kolejność / Pozycję”, aby kontrolować sekwencję.
    5.  **Aktywuj/Dezaktywuj:** Użyj przełącznika „Aktywny”, aby zarządzać widocznością bez usuwania treści.
    6.  **Sprawdź na front-office:** Zawsze sprawdzaj swój slider w działającym sklepie, aby upewnić się, że wygląda i działa zgodnie z oczekiwaniami.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :----------------- | :------------------ | :---------- |
| **Konfiguracja modułu** | Szerokość slidera (px) | `100%` lub `1170` | Ustawia rozmiar poziomy slidera. |
| | Wysokość slidera (px) | `350` - `500` | Ustawia rozmiar pionowy slidera. |
| | Szybkość animacji (ms) | `1000` | Kontroluje szybkość przejścia slajdów. |
| | Autoodtwarzanie | `TAK` | Automatycznie przewija slajdy. |
| | Szybkość autoodtwarzania (ms) | `5000` | Opóźnienie między automatycznymi zmianami slajdów. |
| | Wyświetl na haku | `displayHome` / `displayHeader` | Gdzie slider pojawia się w Twoim sklepie. |
| | Kolor tła | `Pozostaw puste` / `#FFFFFF` | Kolor tła obszaru slidera. |
| | Kolor tekstu | `#333333` | Domyślny kolor tekstu dla podpisów/opisów. |
| **Dodaj/Edytuj slajd** | Tytuł slajdu (podpis) | Zwięzły i wyrazisty | Główny nagłówek slajdu. |
| | Opis slajdu | Informacyjny | Szczegółowy tekst slajdu. |
| | Obraz slajdu | Wysokiej jakości obraz | Wizualne tło slajdu. |
| | Adres URL linku | Prawidłowy adres URL | Cel po kliknięciu slajdu. |
| | Otwórz w nowym oknie | `TAK` | Otwiera link w nowej karcie przeglądarki. |
| | Aktywny | `TAK` | Przełącza widoczność slajdu. |
| | Kolejność / Pozycja | `1, 2, 3...` | Określa sekwencję slajdów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój slider nie wyświetla się na stronie głównej lub wyświetla się w niewłaściwym miejscu.**

-   **Odp.:** Najpierw sprawdź ustawienie „Wyświetl na haku” w konfiguracji modułu. Upewnij się, że wybrałeś prawidłowy hak (np. `displayHeader`, `displayTop`, `displayHome`). Jeśli Twój motyw ma niestandardowe nazwy haków lub nie obsługuje jawnie standardowego haka w tej lokalizacji, slider może się nie pojawić.
-   **Odp.:** Sprawdź również, czy poszczególne slajdy są oznaczone jako „Aktywne” w ich ustawieniach. Jeśli żadne slajdy nie są aktywne, nic się nie wyświetli.
-   **Odp.:** Na koniec wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami zmiany nie pojawiają się, dopóki pamięć podręczna nie zostanie odświeżona.

**P2: Obrazy w moim sliderze wyglądają na rozmazane lub rozciągnięte.**

-   **Odp.:** Zazwyczaj dzieje się tak, jeśli przesłane obrazy nie pasują do ustawień „Szerokość slidera” i „Wysokość slidera” lub jeśli mają niską rozdzielczość.
-   **Odp.: Rozwiązanie:** Upewnij się, że Twoje obrazy są wysokiej rozdzielczości i idealnie mają ten sam współczynnik proporcji co skonfigurowane wymiary slidera. Na przykład, jeśli Twój slider ma 1200px szerokości i 400px wysokości, spróbuj przesłać obrazy o wymiarach co najmniej 1200px na 400px. Może być konieczne zmniejszenie lub przycięcie obrazów przed ich przesłaniem.

**P3: Tekst na moich slajdach jest trudny do odczytania.**

-   **Odp.:** Jest to często problem z kontrastem między „Obrazem slajdu” a wybranym „Kolorem tekstu”.
-   **Odp.: Rozwiązanie:**
    1.  Dostosuj „Kolor tekstu” w głównej konfiguracji modułu do koloru, który dobrze kontrastuje z Twoimi obrazami (np. biały tekst na ciemnych obrazach, czarny tekst na jasnych obrazach).
    2.  Rozważ dodanie subtelnej nakładki na obrazy (może być potrzebny edytor graficzny), aby je nieco przyciemnić lub rozjaśnić, co sprawi, że tekst będzie bardziej widoczny.
    3.  Zachowaj zwięzłość „Tytułu slajdu” i „Opisu slajdu”. Mniej tekstu jest często łatwiejsze do szybkiego przeczytania.

**P4: Jak przetłumaczyć tytuły i opisy slajdów na różne języki?**

-   **Odp.:** Podczas edycji slajdu powinieneś zobaczyć zakładki wyboru języka obok pól „Tytuł slajdu” i „Opis slajdu” (jeśli w Twoim sklepie PrestaShop włączono wiele języków).
-   **Odp.: Rozwiązanie:** Kliknij ikonę flagi lub zakładkę języka dla każdego języka, na który chcesz przetłumaczyć, a następnie wprowadź odpowiedni tekst dla tego języka. Pamiętaj, aby zapisać zmiany.

**P5: Animacje slidera są zbyt szybkie/wolne lub autoodtwarzanie nie działa.**

-   **Odp.:** Sprawdź ustawienia „Szybkość animacji (ms)”, „Autoodtwarzanie” i „Szybkość autoodtwarzania (ms)” w głównej konfiguracji modułu.
-   **Odp.: Rozwiązanie:**
    *   Zwiększ „Szybkość animacji” dla wolniejszych przejść, zmniejsz dla szybszych.
    *   Upewnij się, że „Autoodtwarzanie” jest ustawione na `TAK`, jeśli chcesz, aby slajdy przewijały się automatycznie.
    *   Dostosuj „Szybkość autoodtwarzania”, aby kontrolować, jak długo każdy slajd jest wyświetlany przed przejściem do następnego. Pamiętaj, że te wartości są w milisekundach (1000ms = 1 sekunda).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Presta Pro Slider stosuje standardową architekturę modułów PrestaShop, wykorzystując wzorzec MVC tam, gdzie jest to stosowne. Głównie używa pojedynczego głównego pliku modułu (`ajax_proslider.php`) dla swojej podstawowej logiki i konfiguracji, kontrolera administracyjnego do zarządzania slajdami oraz szablonów front-office do renderowania slidera. Opiera się na jQuery i Modernizr dla animacji i stylizacji front-endowych. Dane slajdów są przechowywane bezpośrednio w tabeli `ps_configuration` PrestaShop, a nie w dedykowanym `ObjectModel` i niestandardowej tabeli bazy danych.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    *   `controllers/front/default.php`
        *   **Nazwa klasy i klasa nadrzędna**: `ProsliderDefaultModuleFrontController` rozszerzająca `ModuleFrontController`.
        *   **Odpowiedzialność**: Ten kontroler jest prawdopodobnie przeznaczony dla domyślnej trasy lub konkretnej akcji front-office, chociaż jego dokładny cel może być minimalny, biorąc pod uwagę, że moduł głównie włącza się w istniejące obszary szablonów. Obsługiwałby żądania do `twojskep.com/module/proslider/default` i mógłby być używany do wywołań AJAX lub renderowania samodzielnej strony, gdyby moduł taką posiadał. W kontekście tego modułu może to być placeholder lub być używany do pobierania konkretnych danych, jeśli zawartość slidera była ładowana dynamicznie.
-   **Kontrolery administracyjne Back-Office**:

    *   `controllers/admin/adminproslider.php`
        *   **Nazwa klasy i klasa nadrzędna**: `AdminprosliderController` rozszerzająca `ModuleAdminController`.
        *   **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza „slajdami” lub „opiniami” (zgodnie z dossier, chociaż „opinia” wydaje się być literówką i prawdopodobnie powinno być „slajd” lub „proslider\_item”, gdyby był to ObjectModel). Zapewnia interfejs do dodawania, edytowania i usuwania poszczególnych slajdów. Obsługuje przesyłanie formularzy dla szczegółów slajdu (tytuł, opis, obraz, link itp.) i aktualizuje tabelę `ps_configuration` lub niestandardową tabelę, jeśli taka istnieje.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas lub modeli w katalogu `classes/`. Sugeruje to, że moduł przechowuje swoje dane bezpośrednio w tabeli `ps_configuration` za pomocą serializowanych tablic lub indywidualnych kluczy konfiguracyjnych dla każdego slajdu, lub może używać prostszego, nie-ORM-owego podejścia w `AdminprosliderController` do zarządzania danymi. Gdyby używał `ObjectModel`, klasa byłaby zdefiniowana tutaj (np. `ProsliderSlide.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `proslider/js/jquery.cslider.js`
    *   **Zakres**: Front-office.
    *   **Opis**: Jest to prawdopodobnie podstawowy plugin jQuery odpowiedzialny za animowaną funkcjonalność slidera. Obsługuje przejścia slajdów, logikę autoodtwarzania, kontrolki nawigacji i responsywność. Programiści powinni zapoznać się z tym plikiem, aby zrozumieć typy animacji slidera i dostępne opcje.
-   `proslider/js/jscolor/jscolor.js`
    *   **Zakres**: Back-office.
    *   **Opis**: Biblioteka JavaScript dla widżetu wyboru koloru. Jest używana w formularzach konfiguracji modułu w back-office, aby umożliwić sprzedawcom łatwe wybieranie kolorów tła i tekstu dla slidera.
-   `proslider/js/modernizr.custom.28468.js`
    *   **Zakres**: Front-office.
    *   **Opis**: Modernizr to biblioteka JavaScript, która wykrywa funkcje HTML5 i CSS3 w przeglądarce użytkownika. Ta konkretna niestandardowa kompilacja jest prawdopodobnie używana przez `jquery.cslider.js` do zapewnienia wykrywania funkcji i potencjalnie mechanizmów awaryjnych dla starszych przeglądarek, zapewniając płynne animacje i kompatybilność.
-   `proslider/js/script.js`
    *   **Zakres**: Front-office.
    *   **Opis**: Jest to główny niestandardowy plik JavaScript modułu. Inicjalizuje plugin `jquery.cslider.js` z konkretnymi ustawieniami skonfigurowanymi w back-office (szerokość, wysokość, szybkość, autoodtwarzanie itp.). Wiąże słuchaczy zdarzeń dla nawigacji slidera (jeśli zaimplementowano niestandardowe) i zapewnia prawidłowe działanie slidera w środowisku PrestaShop.
-   `proslider/tinymce16.inc.js`
    *   **Zakres**: Back-office.
    *   **Opis**: Ten plik jest dołączany do edytora tekstu sformatowanego TinyMCE, specjalnie skonfigurowanego dla PrestaShop 1.6.x. Jest używany w formularzach back-office dla pól „Opis slajdu”, umożliwiając sprzedawcom formatowanie tekstu za pomocą HTML. W przypadku PrestaShop 1.7.x i 8.x może być używana natywna integracja TinyMCE PrestaShop, lub ten plik może być nadal ładowany dla kompatybilności.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `proslider/css/style2.css`
    *   **Zakres**: Stylizacja klienta front-office.
    *   **Opis**: Jest to główny arkusz stylów dla front-endowego slidera. Definiuje wygląd wizualny kontenera slidera, poszczególnych slajdów, podpisów, opisów, strzałek nawigacyjnych i kropek paginacji.
    *   **Kluczowe selektory klas CSS**: Programiści mogą sprawdzić ten plik pod kątem klas takich jak `.cs-slider`, `.cs-wrapper`, `.cs-bg`, `.cs-caption`, `.cs-description`, `.cs-nav`, `.cs-dots`, aby nadpisać lub rozszerzyć stylizację w niestandardowym CSS swojego motywu.
-   `proslider/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    *   **Zakres**: Stylizacja formularzy administracyjnych back-office.
    *   **Opis**: Jest to niestandardowa kompilacja frameworka CSS jQuery UI, specjalnie dla motywu „UI-lightness”. Jest prawdopodobnie używana do stylizacji elementów w formularzach konfiguracji modułu w back-office, takich jak selektory dat (jeśli istnieją), przyciski lub inne widżety UI, które mogą być częścią interfejsu zarządzania slajdami.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:

    *   `proslider/header.tpl`
        *   **Hak**: Prawdopodobnie przeznaczony dla `displayHeader` lub `displayTop`.
        *   **Wyjście**: Ten szablon zawierałby główną strukturę HTML dla slidera, w tym elementy `div`, które są celem `jquery.cslider.js`, i potencjalnie pętlę do renderowania poszczególnych slajdów na podstawie danych przekazanych z modułu. Może również zawierać niezbędne pliki JS i CSS.
    *   `proslider/top.tpl`
        *   **Hak**: Prawdopodobnie przeznaczony dla `displayTop` lub `displayNav`.
        *   **Wyjście**: Podobnie jak `header.tpl`, ten szablon renderowałby slider w górnej sekcji sklepu, często poniżej głównej nawigacji.
    *   `proslider/views/templates/hook/left-column.tpl`
        *   **Hak**: `displayLeftColumn` lub `displayRightColumn`.
        *   **Wyjście**: Ten szablon renderuje potencjalnie mniejszą lub inaczej stylizowaną wersję slidera specjalnie dla bocznych kolumn sklepu.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    *   `proslider/views/templates/front/form.tpl`
        *   **Hak**: Ta ścieżka sugeruje, że jest to szablon front-office, ale kontekst `AdminprosliderController` implikuje, że może być używany do *formularza* dodawania/edycji slajdów w panelu administracyjnym. Jest to powszechny wzorzec, w którym moduł może ponownie wykorzystywać szablon „formularza” zarówno do wprowadzania danych front-endowych (jeśli dotyczy), jak i back-endowych.
        *   **Wyjście**: Ten szablon definiowałby strukturę formularza HTML do dodawania lub edytowania pojedynczego slajdu, w tym pól wejściowych dla tytułu, opisu, przesyłania obrazu, adresu URL, statusu aktywnego i pozycji.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    *   Dossier modułu wskazuje brak niestandardowych plików SQL. To silnie sugeruje, że moduł przechowuje swoją konfigurację i dane slajdów bezpośrednio w tabeli `ps_configuration` PrestaShop. Dane każdego slajdu (tytuł, opis, obraz, link itp.) byłyby prawdopodobnie serializowane do pojedynczego klucza konfiguracyjnego lub wielu kluczy na slajd, np. `PROSLIDER_SLIDE_1_TITLE`, `PROSLIDER_SLIDE_1_IMAGE` itp. To podejście jest prostsze, ale mniej skalowalne niż użycie dedykowanego `ObjectModel`.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| :--------- | :------------- | :------------- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie zasobów CSS/JS i potencjalnie głównej struktury HTML slidera. |
| `displayTop` | Zazwyczaj poniżej głównej nawigacji, nad treścią. | Wyświetlanie głównego slidera w widocznym miejscu na górze. |
| `displayHome` | W obszarze treści strony głównej. | Wyświetlanie slidera jako centralnego elementu na stronie głównej. |
| `displayLeftColumn` | W lewym pasku bocznym stron, które go posiadają. | Wyświetlanie mniejszego, kontekstowego slidera w lewej kolumnie. |
| `displayRightColumn` | W prawym pasku bocznym stron, które go posiadają. | Wyświetlanie mniejszego, kontekstowego slidera w prawej kolumnie. |
| `displayProductFooter` | Na dole stron produktów. | Wyświetlanie slidera związanego z produktem (np. akcesoria, powiązane elementy). |
| `displayFooter` | W sekcji stopki każdej strony. | Wyświetlanie slidera dla wtórnych promocji lub treści marki. |
| `actionFrontControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler front-endowy, po ustawieniu mediów. | Rejestrowanie plików CSS i JavaScript specyficznych dla modułu dla stron front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler administracyjny, po ustawieniu mediów. | Rejestrowanie plików CSS i JavaScript specyficznych dla modułu dla stron back-office (np. dla selektora kolorów lub TinyMCE). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji modułu, poprawek błędów i oficjalnego wsparcia, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w świadczenie pomocy i zapewnienie płynnego działania modułu Presta Pro Slider.
