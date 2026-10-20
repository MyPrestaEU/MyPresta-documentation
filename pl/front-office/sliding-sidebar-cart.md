---
title: "Wysuwany koszyk boczny - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wysuwany koszyk boczny” od MyPresta.eu."
sidebar:
  label: "Wysuwany koszyk boczny - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Sliding sidebar cart na MyPresta.eu](https://mypresta.eu/modules/front-office-features/sliding-sidebar-cart.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/sliding-sidebar-cart/)
>
> ---


# Wysuwany koszyk boczny

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień. Ta strona pozwala dokładnie kontrolować, jakie informacje są wyświetlane w wysuwanym koszyku bocznym.

-   **Wyświetlaj zdjęcie produktu**

    -   **Co robi to ustawienie:** Kontroluje, czy miniatura każdego produktu w koszyku jest wyświetlana w pasku bocznym.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Małe zdjęcie każdego produktu pojawi się obok jego nazwy w pasku bocznym, ułatwiając klientom wizualną identyfikację produktów.
        -   *Gdy wyłączone („Wył.”):* Wyświetlana będzie tylko nazwa produktu i inne szczegóły tekstowe, co oszczędza miejsce, ale potencjalnie sprawia, że koszyk jest mniej atrakcyjny wizualnie.
    -   **Zalecana wartość:** „Wł.”
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji pomaga klientom szybko potwierdzić, że dodali właściwy produkt, co jest szczególnie przydatne w sklepach z wieloma podobnie brzmiącymi produktami lub wariantami.
-   **Wyświetlaj nazwę produktu**

    -   **Co robi to ustawienie:** Określa, czy nazwa każdego produktu jest widoczna w wysuwanym koszyku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Wyświetlana będzie pełna nazwa każdego produktu.
        -   *Gdy wyłączone („Wył.”):* Nazwy produktów zostaną ukryte. Zazwyczaj nie jest to zalecane, ponieważ utrudnia zrozumienie zawartości koszyka.
    -   **Zalecana wartość:** „Wł.”
    -   **Scenariusz / przykład dla sprzedawcy:** To podstawowa informacja. Zawsze pozostawiaj ją „Wł.”, aby klienci dokładnie wiedzieli, co znajduje się w ich koszyku.
-   **Wyświetlaj wartości atrybutów produktu**

    -   **Co robi to ustawienie:** Jeśli Twoje produkty mają atrybuty (takie jak rozmiar, kolor, materiał), to ustawienie kontroluje, czy wybrane atrybuty są wyświetlane dla każdego produktu w koszyku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Dla produktu takiego jak „T-shirt (Rozmiar: M, Kolor: Niebieski)”, wyświetlone zostanie „Rozmiar: M, Kolor: Niebieski”.
        -   *Gdy wyłączone („Wył.”):* Wyświetlony zostanie tylko „T-shirt”, co może wprowadzać klientów w błąd co do dokładnego wariantu, który dodali.
    -   **Zalecana wartość:** „Wł.” (szczególnie dla sklepów sprzedających produkty konfigurowalne)
    -   **Scenariusz / przykład dla sprzedawcy:** Kluczowe dla sklepów sprzedających odzież, elektronikę z różnymi specyfikacjami lub dowolny produkt z wieloma opcjami. Pomaga klientom zweryfikować, czy wybrali właściwy wariant.
-   **Wyświetlaj cenę produktu**

    -   **Co robi to ustawienie:** Kontroluje, czy indywidualna cena każdego produktu w koszyku jest wyświetlana.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Cena jednostkowa dla każdego produktu będzie widoczna.
        -   *Gdy wyłączone („Wył.”):* Indywidualne ceny produktów zostaną ukryte, chociaż całkowita wartość koszyka nadal będzie wyświetlana.
    -   **Zalecana wartość:** „Wł.”
    -   **Scenariusz / przykład dla sprzedawcy:** Przejrzystość jest kluczowa. Wyświetlanie indywidualnych cen pomaga klientom zrozumieć rozkład kosztów i potwierdza ich wybory.
-   **Wyświetlaj pole wprowadzania ilości**

    -   **Co robi to ustawienie:** Pozwala klientom zmieniać ilość produktu bezpośrednio w koszyku bocznym za pomocą pola wprowadzania.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Obok każdego produktu pojawi się numeryczne pole wprowadzania (np. „1”, „2”, „3”), umożliwiające klientom wpisanie nowej ilości lub użycie przycisków zwiększania/zmniejszania.
        -   *Gdy wyłączone („Wył.”):* Klienci nie mogą zmieniać ilości w pasku bocznym; musieliby przejść do pełnej strony koszyka, aby to zrobić.
    -   **Zalecana wartość:** „Wł.”
    -   **Scenariusz / przykład dla sprzedawcy:** To znacznie poprawia użyteczność. Klient, który przypadkowo dodał 2 produkty zamiast 1, może natychmiast to skorygować bez opuszczania bieżącej strony, zmniejszając frustrację i potencjalne porzucenie koszyka.
-   **Wyświetlaj przycisk usuwania**

    -   **Co robi to ustawienie:** Dodaje przycisk (zazwyczaj „X” lub ikonę kosza na śmieci) obok każdego produktu, umożliwiając klientom usunięcie go z koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Klienci mogą łatwo usuwać niechciane produkty ze swojego koszyka bezpośrednio z paska bocznego.
        -   *Gdy wyłączone („Wył.”):* Klienci nie mogą usuwać produktów z paska bocznego; musieliby przejść do pełnej strony koszyka.
    -   **Zalecana wartość:** „Wł.”
    -   **Scenariusz / przykład dla sprzedawcy:** Niezbędne dla elastycznego doświadczenia zakupowego. Jeśli klient zmieni zdanie co do produktu, może go natychmiast usunąć, zapobiegając porzuceniu całego koszyka z powodu jednego niechcianego produktu.
-   **Wyświetlaj koszt wysyłki**

    -   **Co robi to ustawienie:** Pokazuje szacunkowy lub rzeczywisty koszt wysyłki w podsumowaniu koszyka bocznego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Szacunkowy lub obliczony koszt wysyłki zostanie wyświetlony w podsumowaniu koszyka.
        -   *Gdy wyłączone („Wył.”):* Koszty wysyłki nie będą wyświetlane w pasku bocznym, tylko na pełnej stronie koszyka lub stronie kasy.
    -   **Zalecana wartość:** „Wł.” (jeśli Twoje obliczenia wysyłki są dokładne na wczesnym etapie)
    -   **Scenariusz / przykład dla sprzedawcy:** Przejrzystość kosztów wysyłki z góry może zapobiec „szokowi cenowemu” przy kasie, który jest główną przyczyną porzucania koszyków. Jeśli Twoja wysyłka jest skomplikowana lub w dużym stopniu zależy od adresu klienta, możesz rozważyć pozostawienie jej „Wył.”, aby uniknąć mylących szacunków.
-   **Wyświetlaj sumę częściową (całkowita wartość produktów)**

    -   **Co robi to ustawienie:** Pokazuje całkowitą wartość wszystkich produktów w koszyku, *przed* zastosowaniem jakichkolwiek kosztów wysyłki, podatków lub rabatów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Wyświetlona zostanie suma wszystkich cen produktów.
        -   *Gdy wyłączone („Wył.”):* Ta konkretna linia sumy częściowej zostanie ukryta.
    -   **Zalecana wartość:** „Wł.”
    -   **Scenariusz / przykład dla sprzedawcy:** Zapewnia klientowi jasny podział, pomagając mu zrozumieć koszt samych produktów oddzielnie od innych opłat.
-   **Wyświetlaj podatki sumy częściowej**

    -   **Co robi to ustawienie:** Pokazuje całkowitą kwotę podatków naliczonych od produktów w koszyku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Wł.”):* Całkowita kwota podatku zostanie wyświetlona w podsumowaniu koszyka.
        -   *Gdy wyłączone („Wył.”):* Szczegóły podatkowe nie będą wyświetlane w pasku bocznym.
    -   **Zalecana wartość:** „Wł.” (szczególnie w regionach, gdzie przejrzystość podatkowa jest prawnie wymagana lub oczekiwana przez klientów)
    -   **Scenariusz / przykład dla sprzedawcy:** Ważne dla przejrzystości, szczególnie w krajach, gdzie VAT lub podatek od sprzedaży stanowi znaczący składnik ceny końcowej. Pomaga klientom zrozumieć pełny rozkład kosztów przed przejściem do kasy.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetlaj zdjęcie produktu | Wł. | Pokazuje miniatury produktów dla wizualnej identyfikacji. |
| Konfiguracja modułu | Wyświetlaj nazwę produktu | Wł. | Pokazuje nazwę każdego produktu w koszyku. |
| Konfiguracja modułu | Wyświetlaj wartości atrybutów produktu | Wł. | Pokazuje wybrane atrybuty (rozmiar, kolor) dla produktów konfigurowalnych. |
| Konfiguracja modułu | Wyświetlaj cenę produktu | Wł. | Pokazuje indywidualną cenę każdego produktu. |
| Konfiguracja modułu | Wyświetlaj pole wprowadzania ilości | Wł. | Pozwala klientom zmieniać ilości produktów bezpośrednio w pasku bocznym. |
| Konfiguracja modułu | Wyświetlaj przycisk usuwania | Wł. | Pozwala klientom usuwać produkty z koszyka bezpośrednio w pasku bocznym. |
| Konfiguracja modułu | Wyświetlaj koszt wysyłki | Wł. | Pokazuje szacunkowy/rzeczywisty koszt wysyłki w podsumowaniu. |
| Konfiguracja modułu | Wyświetlaj sumę częściową (całkowita wartość produktów) | Wł. | Pokazuje całkowitą wartość produktów przed wysyłką/podatkami. |
| Konfiguracja modułu | Wyświetlaj podatki sumy częściowej | Wł. | Pokazuje całkowitą kwotę podatku naliczonego od produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Pasek boczny nie wysuwa się, gdy dodaję produkt do koszyka.**
O1:

-   **Sprawdź status modułu:** Upewnij się, że moduł „Wysuwany koszyk boczny” jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają załadowanie nowej funkcjonalności modułu.
-   **Konflikty z szablonem:** Twój szablon może mieć własne potwierdzenie „dodania do koszyka” lub JavaScript, które koliduje z tym modułem. Tymczasowo przełącz się na domyślny szablon PrestaShop (Classic), aby sprawdzić, czy pasek boczny działa. Jeśli tak, problem leży w JavaScript lub CSS Twojego niestandardowego szablonu. Może być konieczne, aby programista zbadał problem.
-   **Błędy JavaScript:** Otwórz konsolę programisty w przeglądarce (zazwyczaj F12) i sprawdź, czy nie ma błędów JavaScript, gdy dodajesz produkt. Te błędy mogą uniemożliwić pojawienie się paska bocznego.

**P2: Pasek boczny pojawia się, ale stylizacja wygląda źle (niewłaściwe kolory, czcionki lub układ).**
O2:

-   **Konflikty CSS szablonu:** Jest to prawie zawsze konflikt CSS z aktywnym szablonem PrestaShop. Arkusze stylów Twojego szablonu mogą nadpisywać style modułu.
-   **Rozwiązanie:** Prawdopodobnie będziesz potrzebować webmastera lub programisty, aby zbadać CSS za pomocą narzędzi deweloperskich przeglądarki. Mogą oni zidentyfikować kolidujące style i dodać niestandardowy CSS do Twojego szablonu (lub pliku niestandardowego CSS modułu, jeśli jest dostępny), aby upewnić się, że pasek boczny wyświetla się poprawnie.

**P3: Ilości lub ceny nie aktualizują się poprawnie, gdy zmieniam je w pasku bocznym.**
O3:

-   **Wyczyść pamięć podręczną:** Ponownie spróbuj wyczyścić pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
-   **Problemy z AJAX:** Moduł używa AJAX do aktualizacji koszyka. Jeśli występują błędy po stronie serwera lub konflikty JavaScript uniemożliwiające ukończenie wywołań AJAX, aktualizacje nie zostaną zarejestrowane. Sprawdź konsolę programisty w przeglądarce pod kątem błędów sieciowych lub błędów JavaScript, gdy próbujesz zmienić ilości.
-   **Konfiguracja modułu:** Sprawdź dwukrotnie, czy „Wyświetlaj pole wprowadzania ilości” jest włączone w konfiguracji modułu.

**P4: Jak przetłumaczyć tekst w pasku bocznym na inne języki?**
O4:

-   **System tłumaczeń PrestaShop:** Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym.
-   **Typ tłumaczenia:** Wybierz „Tłumaczenia zainstalowanych modułów”.
-   **Wybierz moduł:** Wybierz „Wysuwany koszyk boczny” z rozwijanej listy modułów.
-   **Wybierz język:** Wybierz język, na który chcesz przetłumaczyć.
-   **Tłumacz:** Zobaczysz listę ciągów tekstowych z modułu, które można przetłumaczyć. Wprowadź swoje tłumaczenia i zapisz.

**P5: Czy mogę zmienić stronę, z której wysuwa się pasek boczny (lewa vs. prawa)?**
O5:

-   Domyślne zachowanie modułu to zazwyczaj wysuwanie się z prawej strony. Zmiana tego wymagałaby niestandardowych modyfikacji CSS, ponieważ jest to kontrolowane przez pliki `sidcart.css` i `sidcart-right.css`. Programista mógłby dostosować właściwości CSS (np. `right: 0` na `left: 0`) i potencjalnie logikę animacji, aby to osiągnąć.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych zajmujących się utrzymaniem lub rozszerzaniem sklepu.

### 4.1 Przegląd architektury

Moduł „Wysuwany koszyk boczny” (`sidcart`) jest zgodny ze standardową architekturą modułów PrestaShop, koncentrując się głównie na ulepszeniach front-office. Wykorzystuje system hooków PrestaShop do wstrzykiwania swojej funkcjonalności i szablonów do witryny sklepu. Podstawowa logika interakcji z koszykiem (dodawanie, aktualizowanie, usuwanie produktów) jest obsługiwana za pośrednictwem kontrolera front-end AJAX, zapewniając dynamiczne i niezakłócające doświadczenie użytkownika. Konfiguracja jest zarządzana za pomocą metody `getContent()` głównej klasy modułu, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa klasy i klasa nadrzędna**: `SidcartAjaxModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest odpowiedzialny za obsługę wszystkich żądań AJAX związanych z wysuwanym koszykiem. Gdy użytkownik dodaje produkt, aktualizuje ilość lub usuwa element z paska bocznego, JavaScript wysyła żądanie do tego kontrolera. Przetwarza on modyfikację koszyka za pomocą podstawowej klasy `Cart` PrestaShop, a następnie zwraca zaktualizowane podsumowanie koszyka (zazwyczaj fragmenty HTML lub dane JSON) do front-endowego JavaScriptu, który następnie odświeża zawartość paska bocznego. Zapewnia to aktualizacje w czasie rzeczywistym bez pełnego przeładowania strony.
-   **Kontrolery administracyjne Back-Office**: Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani dedykowanych klas w katalogu `classes/`. Jego podstawowa logika znajduje się w pliku `sidcart.php` i kontrolerze front-end `ajax.php`, wchodząc w interakcję bezpośrednio z natywnymi klasami `Cart` i `Product` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `sidcart/views/js/sidcart.js`
    -   **Zakres**: Front-office.
    -   **Szczegóły**: Jest to główny plik JavaScript dla modułu.
        -   Nasłuchuje zdarzeń „dodaj do koszyka” (np. kliknięć na przyciski z określonymi klasami, takimi jak `.add-to-cart`).
        -   Przechwytuje domyślne zachowanie „dodaj do koszyka” i zamiast tego uruchamia wysuwany pasek boczny.
        -   Obsługuje komunikację AJAX z `controllers/front/ajax.php` w celu aktualizacji zawartości koszyka.
        -   Zarządza wyświetlaniem i animacją paska bocznego (wysuwanie/chowanie).
        -   Wiąże słuchaczy zdarzeń dla zmian ilości i przycisków usuwania w samym pasku bocznym, wysyłając dalsze żądania AJAX w celu aktualizacji koszyka.
        -   Prawdopodobnie używa `jQuery` do manipulacji DOM i wywołań AJAX, co jest powszechne w PrestaShop 1.7.x i 8.x.
        -   Może również nasłuchiwać `prestashop.on('updateCart', ...)` lub podobnych zdarzeń, aby upewnić się, że pasek boczny odzwierciedla zmiany wprowadzone przez inne moduły lub podstawową funkcjonalność PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `sidcart/views/css/sidcart-right.css`

    -   **Zakres**: Stylizacja klienta front-office.
    -   **Szczegóły**: Ten arkusz stylów definiuje wygląd wizualny i pozycjonowanie wysuwanego paska bocznego, gdy pojawia się on z prawej strony ekranu.
        -   Zawiera reguły dotyczące szerokości paska bocznego, tła, indeksu z oraz początkowej pozycji `right` (np. `right: -300px;` aby go ukryć).
        -   Definiuje właściwości przejścia dla płynnych animacji przesuwania (np. `transition: right 0.3s ease-in-out;`).
        -   Stylizuje nakładkę, która pojawia się za paskiem bocznym, gdy jest otwarty.
        -   Zawiera specyficzne reguły dotyczące responsywności mobilnej, dostosowując szerokość lub pozycję paska bocznego na mniejszych ekranach.
        -   **Kluczowe selektory klas CSS**: `.sidcart-wrapper`, `.sidcart-content`, `.sidcart-overlay`, `.sidcart-open`.
-   `sidcart/views/css/sidcart.css`

    -   **Zakres**: Stylizacja klienta front-office.
    -   **Szczegóły**: Ten arkusz stylów zawiera ogólne reguły stylizacji dla elementów *wewnątrz* wysuwanego koszyka, niezależnie od tego, czy wysuwa się on z lewej, czy z prawej strony.
        -   Stylizuje elementy listy produktów (`.sidcart-product-line`).
        -   Stylizuje zdjęcia produktów, nazwy, ceny, atrybuty, pola wprowadzania ilości i przyciski usuwania.
        -   Stylizuje sekcje podsumowania koszyka (suma częściowa, wysyłka, suma całkowita).
        -   Stylizuje przyciski „Kontynuuj zakupy” i „Przejdź do kasy”.
        -   **Kluczowe selektory klas CSS**: `.sidcart-product-image`, `.sidcart-product-name`, `.sidcart-product-price`, `.sidcart-qty-input`, `.sidcart-remove-button`, `.sidcart-summary`, `.sidcart-buttons`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `sidcart/views/templates/hook/product-line.tpl`
        -   **Hook**: Ten szablon nie jest bezpośrednio podłączony, ale jest renderowany dynamicznie przez kontroler AJAX (`ajax.php`) w celu reprezentowania pojedynczego wpisu produktu w wysuwanym koszyku.
        -   **Wyjście**: Renderuje HTML dla jednego produktu, w tym jego zdjęcie, nazwę, atrybuty, cenę, pole wprowadzania ilości i przycisk usuwania, w oparciu o ustawienia konfiguracji modułu.
    -   `sidcart/views/templates/hook/sidcart.tpl`
        -   **Hook**: Ten szablon jest prawdopodobnie renderowany przez hook `displayHeader` lub `displayNav2` (lub podobny) w celu wstrzyknięcia głównej struktury wysuwanego paska bocznego do strony. Może być początkowo ukryty, a następnie ujawniony przez JavaScript.
        -   **Wyjście**: Zawiera główną strukturę HTML dla całego wysuwanego paska bocznego, w tym kontener, obszar listy produktów, podsumowanie koszyka i przyciski akcji. Działa jako opakowanie dla dynamicznie ładowanej zawartości `product-line.tpl`.
-   **Szablony administracyjne (`views/templates/admin/`)**: Brak.
-   **Szablony Front-office (`views/templates/front/`)**:

    -   `sidcart/views/templates/modal.tpl`
        -   **Hook**: Ten szablon jest prawdopodobnie rezerwową lub alternatywną strukturą dla wyświetlania modalnego, lub może być używany dla określonej części paska bocznego (np. komunikatu potwierdzającego). Biorąc pod uwagę opis modułu, jest mniej prawdopodobne, aby był to sam główny panel wysuwany, ale może być jego składnikiem lub starszym szablonem.
        -   **Wyjście**: Renderuje ogólną strukturę modalną lub wyskakującą. Programiści powinni zweryfikować jego rzeczywiste użycie w logice `sidcart.js` lub `ajax.php`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` PrestaShop przy użyciu kluczy takich jak `sc_ajaxInfo`, `sc_continueshopping`, `sc_pimage`, `sc_total`, `sc_subtotals_tax`, `sc_subtotals`, `sc_shipping`, `sc_remove`, `sc_qty_change`, `sc_price`, `sc_pname`, `sc_attributes`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do dołączania plików CSS i JavaScript modułu (`sidcart.css`, `sidcart-right.css`, `sidcart.js`) i potencjalnie do wstrzykiwania początkowej, ukrytej struktury HTML paska bocznego. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest inicjowany i jego zasoby multimedialne są ustawiane. | Służy do dołączania wszelkich niezbędnych plików CSS/JS dla strony konfiguracji modułu w Panelu administracyjnym. |
| `displayNav2` | W pasku nawigacyjnym, zazwyczaj w pobliżu ikony koszyka. | Służy do wstrzykiwania małego podsumowania koszyka (np. liczby produktów, całkowitej ceny) lub do dołączania słuchacza zdarzeń do istniejącej ikony koszyka, która uruchamia pasek boczny. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wysuwany koszyk boczny”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
