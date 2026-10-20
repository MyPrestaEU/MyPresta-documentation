---
title: "Wyszukiwanie produktów AJAX w panelu administracyjnym - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyszukiwanie produktów AJAX w panelu administracyjnym” od MyPresta.eu."
sidebar:
  label: "Wyszukiwanie produktów AJAX w panelu administracyjnym - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Back office ajax product search na MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-ajax-product-search.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/back-office-ajax-product-search/)
>
> ---


# Wyszukiwanie produktów AJAX w panelu administracyjnym

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł został zaprojektowany tak, aby był wysoce wydajny i w dużej mierze działał na zasadzie „ustaw i zapomnij”. Bezproblemowo integruje się z Twoim panelem administracyjnym, nie wymagając skomplikowanych konfiguracji.

Po kliknięciu „Konfiguruj” po instalacji, zazwyczaj znajdziesz prosty interfejs, często bez konkretnych ustawień do dostosowania. Podstawowa funkcjonalność modułu (wyszukiwanie produktów AJAX z autouzupełnianiem) jest domyślnie włączona po instalacji.

- **Co robi ten ekran:** Jest to główny obszar konfiguracji modułu. Jednak dla „Wyszukiwania produktów AJAX w panelu administracyjnym” jego główną funkcją jest potwierdzenie, że moduł jest zainstalowany i aktywny.
- **Wpływ zmiany ustawień:** Ponieważ na tym ekranie nie ma specyficznych ustawień konfigurowalnych przez użytkownika, moduł będzie działał z domyślnym, zoptymalizowanym zachowaniem.
- **Zalecana wartość:** Zazwyczaj nie są wymagane żadne konkretne działania. Moduł jest zaprojektowany do działania od razu po wyjęciu z pudełka.
- **Scenariusz/przykład dla sprzedawcy:** Po instalacji po prostu przejdź do dowolnej strony panelu administracyjnego. Powinieneś zauważyć, że gdy zaczniesz pisać w polu wyszukiwania produktów, sugestie pojawiają się natychmiast, a kliknięcie na nie przenosi Cię bezpośrednio do strony edycji produktu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | (Brak konkretnych ustawień) | N/A | Moduł automatycznie ulepsza wyszukiwanie produktów w panelu administracyjnym o funkcję autouzupełniania AJAX po instalacji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale pasek wyszukiwania nie działa inaczej.**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami pamięć podręczna PrestaShop musi zostać wyczyszczona, aby nowe zasoby modułu (takie jak JavaScript i CSS) załadowały się poprawnie.
2.  **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub przetestować w oknie incognito/prywatnym.
3.  **Status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**.
4.  **Kompatybilność z motywem:** Chociaż rzadko zdarza się to w przypadku modułów panelu administracyjnego, mocno dostosowany motyw administracyjny może zakłócać działanie. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Czy ten moduł spowolni mój panel administracyjny?**
O: Nie, wręcz przeciwnie. Używając AJAX, moduł wykonuje wyszukiwania w tle bez pełnego przeładowywania stron, co jest z natury szybsze i bardziej wydajne niż tradycyjne metody wyszukiwania. Został zaprojektowany w celu poprawy wydajności, a nie jej utrudniania.

**P: Czy ten moduł wpływa na wyszukiwanie produktów przez klientów w front-office?**
O: Nie, ten moduł jest przeznaczony wyłącznie dla panelu administracyjnego PrestaShop. Nie ma wpływu na sklep widoczny dla klientów ani na jego funkcję wyszukiwania.

**P: Czy mogę skonfigurować liczbę wyświetlanych wyników wyszukiwania?**
O: Ten moduł został zaprojektowany z myślą o prostocie i funkcjonalności „od razu po wyjęciu z pudełka”. Zazwyczaj nie oferuje konfigurowalnych opcji dla liczby wyników. Domyślne zachowanie jest zazwyczaj zoptymalizowane pod kątem dobrego doświadczenia użytkownika.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Back office ajax product search` (boproductfinder) to lekki moduł PrestaShop, skupiający się głównie na poprawie doświadczenia użytkownika w panelu administracyjnym. Osiąga swoją funkcjonalność poprzez wstrzykiwanie niestandardowych zasobów JavaScript i CSS do nagłówka panelu administracyjnego, wykorzystując system hooków PrestaShop. Podstawowa logika znajduje się w klienckim kodzie JavaScript, który przechwytuje dane wejściowe użytkownika w określonych polach wyszukiwania i wykonuje żądania AJAX do wbudowanych punktów końcowych wyszukiwania produktów PrestaShop, a następnie wyświetla wyniki za pomocą interfejsu autouzupełniania. Nie wprowadza nowych tabel baz danych ani złożonej logiki po stronie serwera poza tym, co PrestaShop już zapewnia dla wyszukiwania produktów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Opiera się na istniejących kontrolerach PrestaShop do obsługi zapytań wyszukiwania produktów (np. metody AJAX `AdminProductsController`).

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas PHP ani definicji `ObjectModel`. Jego funkcjonalność jest przede wszystkim po stronie klienta.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`boproductfinder/views/autocomplete.js`**
    -   **Zakres**: Panel administracyjny.
    -   **Opis**: Ten skrypt prawdopodobnie implementuje lub integruje ogólną bibliotekę autouzupełniania. Zapewnia podstawową funkcjonalność wyświetlania sugestii podczas pisania przez użytkownika w polu tekstowym. Obsługuje renderowanie interfejsu listy sugestii, nawigację klawiaturą w obrębie listy i wybór elementów. Jest to podstawowy komponent interaktywnego wyszukiwania modułu.
-   **`boproductfinder/views/boproductfinder.js`**
    -   **Zakres**: Panel administracyjny.
    -   **Opis**: Jest to główny skrypt modułu.
    -   **Nasłuchiwacze zdarzeń**: Prawdopodobnie wiąże się ze zdarzeniami `keyup` lub `input` w określonych polach wyszukiwania produktów w panelu administracyjnym PrestaShop (np. `input[name="product_search"]` lub podobne selektory).
    -   **Wywołania AJAX**: Gdy użytkownik pisze, ten skrypt wyzwala żądania AJAX do wewnętrznego API wyszukiwania produktów PrestaShop (np. `admin-ajax.php` lub akcja AJAX konkretnego kontrolera administracyjnego dla wyszukiwania produktów). Wysyła zapytanie wyszukiwania i potencjalnie inne parametry (np. `id_lang`).
    -   **Manipulacja DOM**: Odbiera odpowiedź JSON z serwera (zawierającą identyfikatory produktów, nazwy i potencjalnie linki) i używa `autocomplete.js` (lub podobnej logiki) do wyświetlania tych wyników na liście rozwijanej pod polem wyszukiwania.
    -   **Nawigacja**: Po kliknięciu lub wybraniu sugestii produktu, ten skrypt konstruuje adres URL do strony edycji produktu (np. `admin/index.php?controller=AdminProducts&id_product=X&updateproduct&token=Y`) i przekierowuje przeglądarkę na tę stronę.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`boproductfinder/views/autocomplete.css`**
    -   **Zakres**: Stylizacja formularzy panelu administracyjnego.
    -   **Opis**: Ten arkusz stylów zapewnia wizualną stylizację listy sugestii autouzupełniania.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**:
        -   Kontener rozwijany dla wyników wyszukiwania.
        -   Poszczególne elementy listy w sugestiach.
        -   Podświetlanie aktualnie najeżdżonej lub wybranej sugestii.
        -   Potencjalnie wskaźniki ładowania lub komunikaty „brak wyników”.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: Programiści mogą sprawdzić wygenerowany kod HTML pod kątem klas takich jak `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, aby dostosować wygląd w swoim motywie administracyjnym.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty (`.tpl`). Jego funkcjonalność jest wstrzykiwana bezpośrednio za pomocą zasobów JavaScript i CSS ładowanych przez hooki.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się na istniejących tabelach PrestaShop `ps_product`, `ps_product_lang` i powiązanych tabelach dla danych produktów. Konfiguracja jest przechowywana w `ps_configuration`, jeśli byłyby jakieś ustawienia, ale dla tego modułu jest to zazwyczaj minimalne lub nieistniejące.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` każdej strony panelu administracyjnego. | Służy do dołączania plików CSS i JavaScript modułu (`autocomplete.css`, `autocomplete.js`, `boproductfinder.js`), aby zapewnić ich załadowanie na wszystkich stronach administracyjnych, gdzie może być potrzebna funkcja wyszukiwania. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Alternatywny lub uzupełniający hook do `displayBackOfficeHeader` do dodawania plików CSS i JS, zapewniający kompatybilność między różnymi wersjami PrestaShop i motywami panelu administracyjnego. Zapewnia prawidłowe zarejestrowanie i załadowanie zasobów modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyszukiwanie produktów AJAX w panelu administracyjnym”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub kompatybilności modułu.
