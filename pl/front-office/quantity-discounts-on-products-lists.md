---
title: "Rabaty ilościowe na listach produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Rabaty ilościowe na listach produktów” od MyPresta.eu."
sidebar:
  label: "Rabaty ilościowe na listach produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Quantity discounts on products lists na MyPresta.eu](https://mypresta.eu/modules/front-office-features/quantity-discounts-on-products-lists.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/quantity-discounts-on-products-lists/)
>
> ---


# Rabaty ilościowe na listach produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny po instalacji poprzez kliknięcie przycisku „Konfiguruj”.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ta sekcja zawiera podstawowe ustawienia do włączania lub wyłączania funkcjonalności modułu i kontrolowania jego podstawowego zachowania.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączone:* Moduł zacznie wyświetlać rabaty ilościowe na stronach z listami produktów zgodnie z innymi ustawieniami.
    *   *Gdy wyłączone:* Moduł przestanie wyświetlać jakiekolwiek rabaty ilościowe na stronach z listami produktów.
-   **Zalecana wartość:** TAK (chyba że musisz tymczasowo wyłączyć go do konserwacji).
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz specjalną promocję, która zastępuje rabaty ilościowe, możesz tymczasowo wyłączyć moduł. W przeciwnym razie, pozostaw go włączonym, aby wykorzystać jego korzyści.

#### Opcje wyświetlania

-   **Co robi to ustawienie:** Te opcje kontrolują wygląd i umiejscowienie informacji o rabatach ilościowych na listach produktów.
-   **Efekt zmiany tego ustawienia:**
    *   *Przykład: „Wyświetl na stronie produktu”:*
        *   *Gdy włączone:* Rabaty ilościowe będą również wyświetlane na indywidualnej stronie szczegółów produktu.
        *   *Gdy wyłączone:* Rabaty ilościowe pojawią się tylko na stronach z listami produktów (kategorie, wyniki wyszukiwania itp.), zakładając, że są już domyślnie obecne na stronie produktu dzięki funkcjonalności PrestaShop.
    *   *Przykład: „Pozycja informacji o rabacie”:*
        *   *Opcja A (np. „Poniżej ceny produktu”):* Szczegóły rabatu pojawią się bezpośrednio pod główną ceną produktu.
        *   *Opcja B (np. „Powyżej nazwy produktu”):* Szczegóły rabatu pojawią się powyżej nazwy produktu.
-   **Zalecana wartość:** Eksperymentuj z pozycjami, aby znaleźć to, co najlepiej wygląda z Twoim motywem. Często „Poniżej ceny produktu” jest dobrym punktem wyjścia. „Wyświetl na stronie produktu” można włączyć, jeśli Twój motyw nie wyświetla już tam rabatów ilościowych w widocznym miejscu.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje karty produktów są bardzo kompaktowe, możesz wybrać subtelną pozycję. Jeśli chcesz podkreślić rabaty, lepsza może być bardziej widoczna pozycja.

#### Stylizacja i dostosowanie

-   **Co robi to ustawienie:** Te ustawienia pozwalają dostosować wygląd i styl wyświetlania rabatów, aby pasowały do motywu Twojego sklepu. Może to obejmować opcje koloru tekstu, koloru tła, rozmiaru czcionki, a nawet niestandardowego CSS.
-   **Efekt zmiany tego ustawienia:**
    *   *Przykład: „Kolor tekstu”:*
        *   *Gdy ustawione na czerwony:* Tekst rabatu pojawi się na czerwono.
        *   *Gdy ustawione na zielony:* Tekst rabatu pojawi się na zielono.
-   **Zalecana wartość:** Wybierz kolory i style, które uzupełniają Twój istniejący motyw.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja marka używa określonej palety kolorów, chciałbyś, aby informacje o rabatach płynnie się w nią wkomponowały, zamiast się z nią kłócić.

#### Ustawienia zaawansowane

-   **Co robi to ustawienie:** Ta sekcja może zawierać ustawienia dotyczące buforowania, optymalizacji wydajności lub specyficznych opcji integracji.
-   **Efekt zmiany tego ustawienia:**
    *   *Przykład: „Włącz buforowanie”:*
        *   *Gdy włączone:* Moduł będzie przechowywał wygenerowany kod HTML rabatów, aby ładować się szybciej, poprawiając szybkość strony.
        *   *Gdy wyłączone:* Moduł będzie generował kod HTML rabatów przy każdym ładowaniu strony, potencjalnie spowalniając strony, ale zapewniając zawsze najnowsze dane (przydatne podczas rozwoju).
-   **Zalecana wartość:** TAK dla buforowania w sklepach produkcyjnych.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli zauważysz problemy z wydajnością na stronach z wieloma listami produktów, włączenie buforowania może pomóc. Podczas tworzenia motywu możesz wyłączyć buforowanie, aby natychmiast zobaczyć zmiany.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminPlqdSearchController (Panel administracyjny > Moduły > Rabaty ilościowe na listach produktów > Ustawienia wyszukiwania)

Ten kontroler prawdopodobnie zarządza ustawieniami dotyczącymi sposobu, w jaki moduł identyfikuje i przetwarza produkty do wyświetlania rabatów, być może zawierając narzędzie wyszukiwania dla konkretnych produktów lub kategorii.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran może być dostępny za pośrednictwem podzakładki lub dedykowanego linku w głównej stronie konfiguracji modułu, prawdopodobnie oznaczonego jako „Ustawienia wyszukiwania” lub „Wybór produktu”.
-   **Dostępne akcje i ustawienia:** Ten ekran zazwyczaj zawiera siatkę lub formularz do:
    *   **Wyszukiwania produktów:** Umożliwia znajdowanie konkretnych produktów według nazwy, ID lub referencji.
    *   **Wykluczania produktów/kategorii:** Definiowanie konkretnych produktów lub całych kategorii, w których rabaty ilościowe NIE powinny być wyświetlane, nawet jeśli są dla nich skonfigurowane.
    *   **Zarządzania zasadami wyświetlania:** Potencjalnie ustawianie bardziej szczegółowych zasad, kiedy i gdzie rabaty pojawiają się na podstawie atrybutów produktu lub innych kryteriów.
-   **Efekt zmian:**
    *   *Wykluczenie produktu:* Informacje o rabacie ilościowym dla tego konkretnego produktu nie będą już pojawiać się na żadnych stronach z listami produktów.
    *   *Wykluczenie kategorii:* Wszystkie produkty w wybranej kategorii będą miały ukryte informacje o rabacie ilościowym na stronach z listami.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu, jeśli masz konkretne produkty lub kategorie, dla których wyświetlanie rabatów ilościowych na listach nie jest pożądane (np. bardzo drogie przedmioty, produkty na zamówienie lub produkty o złożonych cenach, które mogą wprowadzić klientów w błąd, jeśli zostaną uproszczone).

#### index.php (plqd/controllers/admin/index.php)

Ten plik, choć wymieniony jako kontroler administracyjny, często jest w PrestaShop plikiem zastępczym lub przekierowującym. W kontekście tego modułu, jest bardzo prawdopodobne, że `plqd/index.php` (główny plik modułu) obsługuje główny formularz konfiguracji za pomocą `getContent()`, a `AdminPlqdSearchController.php` obsługuje wszelkie wtórne, bardziej złożone interfejsy administracyjne. Plik `index.php` w katalogu `controllers/admin` może po prostu zapewniać, że bezpośredni dostęp do katalogu jest obsługiwany w sposób łagodny, lub może być plikiem starszej wersji. Dla sprzedawców wszystkie istotne ustawienia znajdą się w głównej konfiguracji modułu lub w `AdminPlqdSearchController`.

### 2.3 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz moduł | TAK | Aktywuje/dezaktywuje podstawową funkcjonalność modułu. |
| | Wyświetl na stronie produktu | TAK/NIE (Zależne od motywu) | Pokazuje rabaty na indywidualnych stronach produktów. |
| | Pozycja informacji o rabacie | Poniżej ceny produktu | Kontroluje, gdzie tekst rabatu pojawia się na kartach produktów. |
| | Kolor tekstu | (Domyślny motywu) | Ustawia kolor tekstu rabatu. |
| | Kolor tła | (Domyślny motywu) | Ustawia kolor tła bloku rabatu. |
| | Włącz buforowanie | TAK | Poprawia wydajność poprzez przechowywanie wygenerowanego kodu HTML. |
| **AdminPlqdSearchController** | Wyklucz produkt (wg ID/Nazwy) | N/A | Zapobiega wyświetlaniu rabatów dla konkretnych produktów. |
| | Wyklucz kategorię | N/A | Zapobiega wyświetlaniu rabatów dla wszystkich produktów w kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Rabaty ilościowe nie wyświetlają się na moich listach produktów po instalacji.**
O:

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Rabaty ilościowe na listach produktów” jest zainstalowany i włączony.
2.  **Skonfiguruj moduł:** Kliknij „Konfiguruj” dla modułu i upewnij się, że główne ustawienie „Włącz moduł” jest ustawione na TAK.
3.  **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
4.  **Sprawdź rabaty produktów:** Upewnij się, że produkty, dla których spodziewasz się rabatów, faktycznie mają skonfigurowane rabaty ilościowe w ich ustawieniach produktu (Panel administracyjny > Katalog > Produkty > Edytuj produkt > zakładka Ceny > Ceny specyficzne).
5.  **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą wymagać drobnych korekt. Jeśli po wyczyszczeniu pamięci podręcznej i sprawdzeniu ustawień nadal się nie pojawia, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P2: Tekst rabatu jest wyświetlany, ale nie wygląda dobrze z moim motywem (niewłaściwe kolory, czcionka lub wyrównanie).**
O:

1.  **Konfiguracja modułu:** Przejdź do strony konfiguracji modułu (**Moduły > Menedżer modułów > Konfiguruj** dla „Rabaty ilościowe na listach produktów”). Poszukaj opcji „Stylizacja i dostosowanie”. Możesz tam bezpośrednio dostosować kolory, rozmiary czcionek lub odstępy.
2.  **Niestandardowy CSS:** Jeśli ustawienia modułu nie oferują wystarczającej kontroli, Twój webmaster lub deweloper może dodać niestandardowy CSS do Twojego motywu, aby zastąpić domyślne style modułu. Pliki CSS modułu (patrz sekcja 7.5) dostarczą im niezbędnych selektorów klas.

**P3: Chcę ukryć rabaty ilościowe dla niektórych produktów lub kategorii, ale nie dla wszystkich.**
O:

1.  **AdminPlqdSearchController:** Przejdź do dedykowanego ekranu administracyjnego modułu (prawdopodobnie podzakładka lub link z głównej konfiguracji, potencjalnie nazwany „Ustawienia wyszukiwania” lub „Wykluczenia”).
2.  **Dodaj wykluczenia:** Użyj narzędzi na tym ekranie, aby wyszukać i dodać konkretne produkty lub całe kategorie do listy wykluczeń. Po dodaniu moduł zignoruje te elementy podczas wyświetlania rabatów na listach produktów.

**P4: Czy ten moduł spowolni mój sklep?**
O: Moduł został zaprojektowany tak, aby był wydajny. Wykorzystuje istniejące dane o rabatach ilościowych PrestaShop.

1.  **Włącz buforowanie:** Upewnij się, że opcja „Włącz buforowanie” w zaawansowanych ustawieniach modułu jest ustawiona na TAK. Znacząco zmniejsza to obciążenie przetwarzania przy kolejnych wyświetleniach strony.
2.  **Wydajność serwera:** Jeśli Twój serwer jest już niedostatecznie wydajny lub mocno obciążony, każdy dodatkowy moduł może mieć niewielki wpływ. Upewnij się, że Twój hosting spełnia zalecane specyfikacje PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Rabaty ilościowe na listach produktów” (`plqd`) to standardowy moduł PrestaShop zgodny ze wzorcem MVC. Głównie rozszerza klasę `Module`, wykorzystując system hooków PrestaShop do wstrzykiwania treści do szablonów list produktów. Nie wprowadza niestandardowych encji `ObjectModel`, ale odczytuje istniejące dane `SpecificPrice`. Moduł używa dedykowanego kontrolera administracyjnego (`AdminPlqdSearchController`) do zarządzania wykluczeniami produktów/kategorii i integruje JavaScript oraz CSS do wyświetlania w front-office.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak jawnie zdefiniowanych jako samodzielne kontrolery frontowe. Moduł prawdopodobnie wstrzykuje swoją zawartość bezpośrednio do szablonów za pomocą hooków i obsługuje wszelkie dynamiczne treści lub AJAX za pomocą metod `displayAjax` w głównej klasie modułu lub za pośrednictwem dołączonego JS.
-   **Kontrolery administracyjne Back-Office**:
    -   `plqd/controllers/admin/AdminPlqdSearchController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminPlqdSearchController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja**: Ten kontroler jest odpowiedzialny za zarządzanie ustawieniami wyszukiwania i wykluczeń dla produktów i kategorii. Prawdopodobnie udostępnia interfejs siatki lub formularza do wyboru produktów/kategorii, które *nie* powinny wyświetlać rabatów ilościowych na listach produktów. Nie zarządza konkretnym `ObjectModel`, ale raczej danymi konfiguracyjnymi (np. `Configuration::updateValue` dla identyfikatorów oddzielonych przecinkami).
    -   `plqd/controllers/admin/index.php`
        -   Ten plik jest zazwyczaj środkiem bezpieczeństwa w PrestaShop, zapobiegającym bezpośredniemu listowaniu katalogów. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome');` lub `die('No direct script access');`. Nie służy jako funkcjonalny kontroler dla logiki modułu ani interfejsu użytkownika.

### 4.3 Klasy podstawowe i modele (`classes/`)

W katalogu `classes/` dla tego modułu nie znaleziono niestandardowych klas ani definicji `ObjectModel`. Moduł bezpośrednio współdziała z podstawowymi klasami PrestaShop `Product` i `SpecificPrice` oraz klasą `Configuration` dla swoich ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `plqd/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres**: Back-office (prawdopodobnie używany w `AdminPlqdSearchController`).
    -   **Cel**: Zapewnia funkcjonalność autouzupełniania do wyszukiwania produktów lub kategorii w interfejsie wykluczeń administracyjnych. Wiąże się z polami wejściowymi, wysyła żądania AJAX do punktu końcowego backendu (prawdopodobnie samego `AdminPlqdSearchController` lub dedykowanego handlera AJAX) i wyświetla sugestie użytkownikowi.
-   `plqd/views/js/plqd.js`
    -   **Zakres**: Front-office.
    -   **Cel**: To jest główny JavaScript front-office dla modułu. Prawdopodobnie:
        -   Skanuje elementy list produktów po załadowaniu strony lub po aktualizacjach AJAX (np. nieskończone przewijanie, filtry kategorii).
        -   Dynamicznie wstrzykuje lub formatuje informacje o rabatach ilościowych do kart produktów.
        -   Może obsługiwać responsywne dostosowania lub drobne interakcje UI związane z wyświetlaniem rabatów.
        -   Może potencjalnie wykonywać wywołania AJAX w celu pobrania danych o rabatach, jeśli nie są one wstępnie renderowane przez Smarty.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `plqd/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres**: Back-office.
    -   **Cel**: Stylizuje rozwijane menu autouzupełniania i pola wejściowe używane w `AdminPlqdSearchController` do wyszukiwania produktów/kategorii.
    -   **Kluczowe selektory**: Prawdopodobnie celuje w klasy takie jak `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` itp.
-   `plqd/views/css/plqd-classic.css`
    -   **Zakres**: Front-office.
    -   **Cel**: Zapewnia domyślną stylizację dla wyświetlania rabatów ilościowych, potencjalnie dostosowaną do starszych motywów PrestaShop lub „klasycznego” wyglądu.
    -   **Kluczowe selektory**: Celuje w główny kontener informacji o rabacie (np. `.plqd-discounts-wrapper`), poszczególne linie rabatów (`.plqd-discount-item`), ilości (`.plqd-quantity`) i ceny (`.plqd-price`).
-   `plqd/views/css/plqd-hide-default.css`
    -   **Zakres**: Front-office.
    -   **Cel**: Ten arkusz stylów prawdopodobnie zawiera reguły ukrywające domyślne wyświetlanie rabatów ilościowych, które mogą być obecne w niektórych motywach, aby zapobiec duplikacji, gdy moduł wstrzykuje swoją własną stylizowaną wersję.
    -   **Kluczowe selektory**: Może celować w typowe elementy motywu, takie jak `.product-price-and-shipping .discount-quantity` lub podobne.
-   `plqd/views/css/plqd.css`
    -   **Zakres**: Front-office.
    -   **Cel**: Główny arkusz stylów front-office dla modułu, zapewniający podstawową stylizację dla wyświetlania rabatów ilościowych. Może to być bardziej nowoczesny lub ogólny arkusz stylów w porównaniu do `plqd-classic.css`.
    -   **Kluczowe selektory**: Podobnie jak w `plqd-classic.css`, celuje w `.plqd-discounts-wrapper`, `.plqd-discount-item` itp. Deweloperzy mogą nadpisać te klasy w pliku `custom.css` lub `theme.css` swojego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `plqd/views/tpl/html.tpl`
        -   **Hook**: Jest to prawdopodobnie główny szablon renderowany przez `hookDisplayProductListFunctionalButtons` modułu (lub podobny hook listy produktów) w celu wyświetlenia kodu HTML rabatu ilościowego dla pojedynczego produktu. Otrzymuje dane produktu i ceny specyficznej z modułu.
        -   **Wyjście**: Renderuje ustrukturyzowany kod HTML dla linii rabatów ilościowych (np. „Od X sztuk: Y $”).
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `plqd/lib/searchTool/views/scripts.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie dołączony do widoku `AdminPlqdSearchController`. Zawiera inicjalizację JavaScript dla funkcji autouzupełniania (np. bloki `$(document).ready()`, definicje zmiennych dla adresów URL AJAX itp.) i potencjalnie dołączenia CSS.
    -   `plqd/views/tpl/selectedProducts.tpl`
        -   **Cel**: Używany w `AdminPlqdSearchController` do wyświetlania listy produktów lub kategorii, które zostały wybrane do wykluczenia. Zazwyczaj renderowałby tabelę lub listę tych elementów, być może z opcjami ich usunięcia.
-   **Szablony front-office (`views/templates/front/`)**:
    -   `plqd/views/tpl/html-product-page.tpl`
        -   **Cel**: Ten szablon jest specjalnie zaprojektowany do wyświetlania rabatów ilościowych na indywidualnej stronie produktu, jeśli moduł jest tak skonfigurowany. Może mieć nieco inną stylizację lub strukturę w porównaniu do szablonu strony listy (`html.tpl`), aby lepiej pasować do układu strony produktu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł nie tworzy niestandardowych tabel SQL. Opiera się na podstawowej tabeli PrestaShop `ps_specific_price` dla danych rabatów ilościowych.
    -   Ustawienia konfiguracji (np. status włączenia, opcje stylizacji, wykluczone identyfikatory produktów/kategorii) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy zazwyczaj poprzedzonych prefiksem `PLQD_`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Używany do dołączania CSS modułu (`plqd.css`, `plqd-classic.css`, `plqd-hide-default.css`) i JavaScript (`plqd.js`). |
| `displayProductListFunctionalButtons` | W elementach listy produktów (np. kategoria, wyniki wyszukiwania). | Główny hook do wstrzykiwania kodu HTML rabatu ilościowego (`html.tpl`) do kart produktów. |
| `displayProductPriceBlock` (typ `after_price`) | Po głównym bloku ceny na stronach produktów. | Używany do wstrzykiwania `html-product-page.tpl`, jeśli skonfigurowano wyświetlanie rabatów na stronach produktów. |
| `displayRightColumn` / `displayLeftColumn` | W prawej/lewej kolumnie bocznej. | Mniej prawdopodobne dla tego modułu, ale mogłoby być użyte do bloku promocyjnego związanego z rabatami ilościowymi, jeśli zaimplementowano. |
| `displayFooter` | Na dole każdej strony front-office. | Może być używany do późno ładowanego JS lub dodatkowych skryptów, jeśli to konieczne. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Może być używany do czyszczenia pamięci podręcznej modułu związanej z tym produktem, zapewniając odzwierciedlenie zaktualizowanych cen specyficznych. |
| `actionModuleInstall` | Podczas instalacji modułu. | Tworzy wpisy konfiguracyjne w `ps_configuration`. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Czyści wpisy konfiguracyjne i potencjalnie wszelkie niestandardowe dane. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia deweloperskiego dla modułu „Rabaty ilościowe na listach produktów”, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół jest dostępny, aby pomóc w wszelkich problemach technicznych lub pytaniach dotyczących funkcjonalności i integracji modułu.
"""
