---
title: "Producent (marka) na liście produktów w panelu administracyjnym - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Producent (marka) na liście produktów w panelu administracyjnym” od MyPresta.eu."
sidebar:
  label: "Producent (marka) na liście produktów w panelu administracyjnym - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Manufacturer (brand) on products list in back office na MyPresta.eu](https://mypresta.eu/modules/administration-tools/manufacturer-brand-on-products-list-in-back-office.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/manufacturer-brand-on-products-list-in-back-office/)
>
> ---


# Producent (marka) na liście produktów w panelu administracyjnym

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.0.0 - 1.7.7.x, 1.7.8.x, 8.x (lista standardowa), 8.x (eksperymentalna lista produktów), 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu. Strona ta głównie obsługuje powiadomienia o aktualizacjach i ogólne utrzymanie modułu.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zarządza tym, jak moduł sprawdza aktualizacje i wyświetla powiadomienia.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowych wersji i informował Cię, jeśli aktualizacja jest dostępna. Pomaga to utrzymać moduł w aktualnym stanie z najnowszymi funkcjami i poprawkami błędów.
    -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał aktualizacji, a Ty nie będziesz otrzymywać powiadomień o nowych wersjach. Będziesz musiał ręcznie sprawdzać swoje konto MyPresta.eu pod kątem aktualizacji.
-   **Zalecana wartość:** **Włączone (Tak)**. Utrzymywanie tego ustawienia włączonego zapewnia, że zawsze jesteś świadomy dostępnych aktualizacji, co jest kluczowe dla bezpieczeństwa i kompatybilności z przyszłymi wersjami PrestaShop.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz być powiadamiany, gdy zostanie wydana nowa wersja modułu, która obsługuje najnowsze funkcje PrestaShop 8.x. Włączenie tego ustawienia zapewnia, że otrzymasz to powiadomienie bezpośrednio w swoim panelu administracyjnym.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie wprowadza nowych, oddzielnych pozycji menu ani dedykowanych ekranów administracyjnych do zarządzania jego podstawową funkcjonalnością. Zamiast tego, jego zmiany są zintegrowane bezpośrednio z istniejącą stroną **Katalog > Produkty**.

**Nazwa ekranu i lokalizacja w menu:**

-   **Katalog > Produkty** (Standardowa strona listy produktów PrestaShop)

**Dostępne działania i ustawienia:**
Po przejściu do **Katalog > Produkty** natychmiast zauważysz zmiany wprowadzone przez moduł:

-   **Nowa kolumna: Producent/Marka:** Na liście produktów pojawi się nowa kolumna wyświetlająca nazwę producenta powiązanego z każdym produktem.
-   **Logo producenta (opcjonalnie):** W zależności od wewnętrznej logiki modułu, może on również wyświetlać logo producenta obok nazwy, jeśli jest dostępne i skonfigurowane.
-   **Filtruj według producenta:** Nad listą produktów znajdziesz nową opcję filtrowania, zazwyczaj rozwijane menu, umożliwiające wybranie konkretnego producenta. Po wybraniu lista produktów natychmiast zaktualizuje się, aby pokazać tylko produkty tej marki.

**Efekt zmian:**

-   **Dodanie kolumny Producent:** Zapewnia natychmiastową wizualną wskazówkę dotyczącą marki każdego produktu, eliminując potrzebę otwierania pojedynczych stron produktów w celu sprawdzenia tych informacji.
-   **Filtrowanie według producenta:** Dramatycznie przyspiesza zadania, w których musisz pracować z produktami konkretnej marki. Na przykład, jeśli producent ogłasza podwyżkę cen, możesz szybko odfiltrować wszystkie jego produkty i zaktualizować ceny. Lub jeśli musisz sprawdzić poziomy zapasów dla pozycji konkretnej marki.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Szybka identyfikacja marki:** Podczas przeglądania listy produktów użyj nowej kolumny „Producent”, aby szybko zidentyfikować marki.
2.  **Ukierunkowane zarządzanie:** Jeśli musisz wykonać działanie na wszystkich produktach konkretnej marki (np. zaktualizować opisy, dostosować ceny, sprawdzić zapasy), użyj nowego rozwijanego menu „Filtruj według producenta” na górze listy produktów. Wybierz żądaną markę, a Twoja lista zostanie natychmiast zawężona.
3.  **Działania masowe:** Połącz filtr producenta ze standardowymi działaniami masowymi PrestaShop (np. wybieranie wielu produktów i stosowanie zmiany) w celu bardzo efektywnego zarządzania specyficznego dla marki.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Powiadomienia o aktualizacjach | Włączone | Powiadamia o nowych wersjach modułu w celu zapewnienia bezpieczeństwa i funkcji. |
| Katalog > Lista produktów | Kolumna Producent | N/A (Zawsze włączona) | Wyświetla markę produktu bezpośrednio na liście produktów w celu szybkiej identyfikacji. |
| Katalog > Lista produktów | Filtruj według producenta | N/A (Zawsze włączona) | Umożliwia filtrowanie listy produktów według konkretnej marki, usprawniając zadania zarządzania specyficzne dla marki. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę kolumny producenta ani filtra na mojej liście produktów.**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop potrzebuje odświeżenia pamięci podręcznej, aby wyświetlić nowe elementy.
2.  **Moduł włączony:** Sprawdź dwukrotnie, czy moduł jest rzeczywiście włączony w **Moduły > Menedżer modułów**.
3.  **Kompatybilność wersji PrestaShop:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej konkretnej instalacji PrestaShop. Jeśli używasz PrestaShop 8.x, upewnij się, że przypadkowo nie zainstalowałeś wersji 1.7.x, na przykład.
4.  **Nadpisywanie motywu:** Chociaż moduł jest zaprojektowany bez nadpisywania, mocno dostosowany motyw lub inny moduł może powodować konflikt. Jeśli problem nadal występuje, spróbuj wyłączyć inne moduły jeden po drugim, aby zidentyfikować konflikt.

**P: Nazwa producenta się pojawia, ale logo nie.**
O: Moduł koncentruje się przede wszystkim na wyświetlaniu nazwy producenta. Jeśli obsługuje logo, upewnij się, że:

1.  **Logo producenta zostało przesłane:** Faktycznie przesłałeś logo dla tego producenta w **Katalog > Producenci** w panelu administracyjnym PrestaShop.
2.  **Ustawienie modułu:** Może istnieć wewnętrzne ustawienie (choć nie jest ono dostępne w podstawowej konfiguracji tego modułu), które kontroluje wyświetlanie logo. Jeśli nie, oznacza to, że moduł jest zaprojektowany do wyświetlania tylko nazwy.

**P: Czy mogę zmienić pozycję kolumny producenta na liście produktów?**
O: Ten moduł integruje się bezpośrednio z systemem siatki produktów PrestaShop. Dokładna pozycja kolumny jest określana przez podstawową konfigurację listy produktów PrestaShop. Chociaż ten moduł dodaje kolumnę, zazwyczaj nie oferuje opcji przeciągania i upuszczania pozycji kolumn. Może być potrzebny bardziej zaawansowany moduł do dostosowywania siatki lub niestandardowe rozwiązanie, aby zmienić kolejność kolumn.

**P: Czy ten moduł spowalnia mój panel administracyjny?**
O: Nie, moduł jest zaprojektowany tak, aby był lekki i wydajny. Wykorzystuje natywny system hooków PrestaShop do dodawania danych producenta bez ciężkiego przetwarzania. Nie powinieneś doświadczyć żadnych zauważalnych spowolnień.

**P: Czy ten moduł będzie działał z nową eksperymentalną stroną produktu w PrestaShop 8.x?**
O: Tak, opis modułu wyraźnie stwierdza kompatybilność z „8.x-eksperymentalna lista produktów”, co oznacza, że jest on zaprojektowany do pracy zarówno ze standardowymi, jak i nowszymi, eksperymentalnymi interfejsami list produktów w PrestaShop 8.x.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Producent (marka) na liście produktów w panelu administracyjnym` (nazwa wewnętrzna `dpmypresta`) został zaprojektowany w celu ulepszenia strony listy produktów w panelu administracyjnym PrestaShop poprzez dodanie informacji o producencie. Przestrzega podejścia bez nadpisywania, opierając się w dużej mierze na systemie hooków PrestaShop, w szczególności na hookach `actionProductGrid*` wprowadzonych w PrestaShop 1.7.x do modyfikowania siatki katalogu produktów. Dzięki temu jest odporny na aktualizacje rdzenia PrestaShop. Moduł przede wszystkim wstrzykuje nowe kolumny i możliwości filtrowania do istniejących danych siatki produktów i procesu renderowania.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa kontrolerów front-office. Zawiera dwa pliki kontrolerów administracyjnych, ale `AdminDpMyPrestaController.php` wydaje się być placeholderem lub pozostałością, a `index.php` jest standardowym pustym plikiem zapobiegającym listowaniu katalogów. Podstawowa logika modułu do konfiguracji jest obsługiwana w metodzie `getContent()` pliku `dpmypresta.php`, a modyfikacje siatki produktów są obsługiwane za pomocą hooków.

-   **Kontrolery front-office**: Brak. Cała funkcjonalność jest specyficzna dla panelu administracyjnego.
-   **Kontrolery administracyjne back-office**:
    -   `controllers/admin/AdminDpMyPrestaController.php`
        -   Nazwa klasy: `AdminDpMyPrestaController` (rozszerza `ModuleAdminController`)
        -   Odpowiedzialność: Ten kontroler jest obecny, ale wydaje się być placeholderem. Jego metoda `__construct` konfiguruje podstawowy kontekst modułu. Nie definiuje żadnych konkretnych działań ani nie renderuje żadnych unikalnych widoków poza tym, co może być dziedziczone z `ModuleAdminController`. Nie jest bezpośrednio powiązany z podstawową funkcjonalnością dodawania danych producenta do listy produktów, która jest sterowana hookami.
    -   `controllers/admin/index.php`
        -   Standardowy pusty plik `index.php` dla bezpieczeństwa, aby zapobiec listowaniu katalogów.

### 4.3 Klasy rdzenia i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Jego operacje są bezpośrednio zintegrowane z istniejącymi strukturami danych i mechanizmami siatki PrestaShop za pośrednictwem hooków.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Wszystkie interakcje i logika wyświetlania dla kolumny producenta i filtra są obsługiwane przez natywne komponenty siatki PrestaShop i logikę PHP modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja dla dodanej kolumny producenta i filtra jest dziedziczona z motywu panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje nowy system szablonów Twig używany w PrestaShop 1.7+ dla siatek panelu administracyjnego.

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`
        -   Ten szablon Twig prawdopodobnie rozszerza lub modyfikuje podstawowy szablon listy produktów PrestaShop. Jest odpowiedzialny za renderowanie całej strony katalogu produktów, w tym siatki. Moduł wstrzykuje kolumnę producenta i filtr do tej struktury.
    -   `views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`
        -   Ten szablon Twig konkretnie renderuje tabelę produktów na stronie katalogu. Moduł modyfikuje ten szablon, aby dodać dane producenta do każdego wiersza produktu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się na istniejących tabelach PrestaShop, głównie `ps_product`, `ps_manufacturer` i `ps_configuration` dla swoich ustawień.

    -   Wartości konfiguracyjne (`mypresta_updates`, `update_`, `updatev_`) są przechowywane w tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionProductGridDataModifier` | Po pobraniu danych produktu dla siatki. | Modyfikuje surową tablicę danych dla każdego produktu, wstrzykując ID i nazwę producenta. |
| `actionAdminProductsListingFieldsModifier` | Przed zdefiniowaniem pól siatki produktów. | Dodaje definicję kolumny „Producent” do siatki produktów. |
| `actionProductGridDefinitionModifier` | Modyfikuje definicję samej siatki produktów. | Potencjalnie dodaje filtr producenta do kolekcji filtrów siatki. |
| `actionAdminProductsListingResultsModifier` | Po przygotowaniu wyników listy produktów. | Dalsze modyfikowanie wyników, zapewniając prawidłowe formatowanie danych producenta do wyświetlania. |
| `actionProductGridQueryBuilderModifier` | Modyfikuje Doctrine Query Builder dla siatki produktów. | Łączy tabelę `ps_manufacturer` z zapytaniem o produkty i dodaje warunki filtrowania według producenta. |
| `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` panelu administracyjnego. | Używane do ładowania zasobów specyficznych dla modułu (choć w tym module ich brak) lub do sprawdzania aktualizacji. |
| `displayAdminProductsExtra` | Renderuje dodatkową zawartość na stronie produktu (nie jest bezpośrednio używane do modyfikacji listy). | Nie jest bezpośrednio związane z podstawową funkcjonalnością tego modułu, ale jest to powszechny hook dla rozszerzeń strony produktu w panelu administracyjnym. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Producent (marka) na liście produktów w panelu administracyjnym” prosimy odwiedzić swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest gotowy pomóc w przypadku wszelkich pytań lub problemów, które mogą się pojawić.
