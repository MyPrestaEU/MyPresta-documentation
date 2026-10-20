---
title: "Wyszukiwanie docelowe - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Wyszukiwanie docelowe” od MyPresta.eu."
sidebar:
  label: "Wyszukiwanie docelowe - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Target search na MyPresta.eu](https://mypresta.eu/modules/front-office-features/target-search.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/target-search/)
>
> ---


# Wyszukiwanie docelowe

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Wyszukiwanie docelowe”, aby uzyskać dostęp do jego ustawień. To tutaj dokładnie definiujesz, gdzie silnik wyszukiwania powinien szukać słów kluczowych.

Strona konfiguracji przedstawi serię pól wyboru, z których każde odpowiada konkretnemu obszarowi danych produktu.

-   **Co robi to ustawienie:** Każde pole wyboru pozwala włączyć lub wyłączyć wyszukiwanie w określonym polu informacji o produkcie.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po zaznaczeniu (włączone):* Silnik wyszukiwania PrestaShop będzie uwzględniał dane z tego konkretnego pola podczas przetwarzania zapytań klientów. Na przykład, jeśli zaznaczono „Nazwa produktu”, wyszukiwanie „sukienka” znajdzie produkty z „sukienka” w nazwie.
    -   *Po odznaczeniu (wyłączone):* Silnik wyszukiwania PrestaShop będzie *ignorował* dane z tego pola. Jeśli „Opis produktu” jest odznaczony, produkt nie pojawi się w wynikach wyszukiwania, jeśli termin wyszukiwania znajduje się tylko w jego opisie.
-   **Zalecana wartość:** Zależy to całkowicie od Twojego katalogu produktów i sposobu, w jaki chcesz, aby klienci znajdowali produkty. Dobrym punktem wyjścia jest włączenie najbardziej krytycznych pól, a następnie dopracowanie na podstawie testów.
-   **Scenariusz sprzedawcy / przykład:**
    -   **Scenariusz 1: Produkty bardzo specyficzne (np. części elektroniczne, książki według ISBN):** Możesz chcieć wyszukiwać tylko w „Nazwie produktu”, „Referencji” i „EAN13/JAN”. Zapewnia to, że klienci szybko znajdą dokładne dopasowania, unikając nieistotnych wyników z długich opisów.
    -   **Scenariusz 2: Moda lub artykuły gospodarstwa domowego (np. „czerwona sukienka”):** Możesz włączyć „Nazwę produktu”, „Krótki opis”, „Długi opis” i „Tagi”. Pozwala to klientom znaleźć produkty na podstawie szerszych terminów, kolorów lub stylów wspomnianych w dowolnym miejscu w szczegółach produktu.
    -   **Scenariusz 3: Produkty markowe:** Włącz „Nazwę producenta”, aby klienci mogli łatwo znaleźć wszystkie produkty konkretnej marki, wpisując nazwę marki w pasek wyszukiwania.

Oto zestawienie typowych ustawień, które znajdziesz:

| Ustawienie / Opcja | Cel i wpływ | Zalecana wartość | Scenariusz sprzedawcy |
| --- | --- | --- | --- |
| **Szukaj w nazwie produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do nazwy produktu. | **TAK** | Niezbędne dla większości sklepów. Klienci często szukają według nazwy produktu. |
| **Szukaj w krótkim opisie produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do krótkiego opisu produktu. | **TAK** | Przydatne do znajdowania produktów na podstawie kluczowych cech lub podsumowań. |
| **Szukaj w długim opisie produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do pełnego, szczegółowego opisu produktu. | **TAK / NIE** | **TAK** dla szerokich wyszukiwań (moda, artykuły gospodarstwa domowego). **NIE** dla bardzo specyficznych przedmiotów (elektronika, części), aby uniknąć szumu. |
| **Szukaj w referencji produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do wewnętrznego numeru referencyjnego produktu. | **TAK / NIE** | **TAK** dla B2B, produktów technicznych lub jeśli klienci znają numery części. **NIE** jeśli referencje są tylko wewnętrzne. |
| **Szukaj w EAN13/JAN produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do kodu kreskowego EAN13 lub JAN produktu. | **TAK / NIE** | **TAK** dla sklepów, w których klienci mogą wyszukiwać według kodu kreskowego (np. książki, artykuły spożywcze). |
| **Szukaj w UPC produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do kodu kreskowego UPC produktu. | **TAK / NIE** | Podobnie jak EAN13/JAN, dla regionów używających UPC. |
| **Szukaj w tagach produktu** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do wszelkich tagów przypisanych do produktu. | **TAK** | Doskonałe do poprawy wykrywalności za pomocą słów kluczowych nieobecnych w nazwach/opisach. |
| **Szukaj w nazwie producenta** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do nazwy producenta produktu. | **TAK** | Kluczowe, jeśli klienci często szukają konkretnych marek. |
| **Szukaj w nazwie dostawcy** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do nazwy dostawcy produktu. | **NIE / TAK** | **NIE** dla większości sklepów B2C. **TAK** dla B2B lub sklepów specjalistycznych, gdzie dostawca jest istotny dla klientów. |
| **Szukaj w nazwie kategorii** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do nazwy kategorii, do których należy produkt. | **TAK** | Pomaga klientom znaleźć produkty według nazwy kategorii (np. „sukienki”, aby znaleźć produkty w kategorii „Sukienki”). |
| **Szukaj w wartości cechy** | Jeśli włączone, zapytania wyszukiwania będą dopasowywane do wartości cech produktu (np. „czerwony” dla cechy „Kolor”). | **TAK** | Wysoce zalecane dla sklepów z bogatymi cechami produktów (np. kolor, rozmiar, materiał). |

**Ważna uwaga:** Po wprowadzeniu jakichkolwiek zmian w tych ustawieniach zawsze kliknij przycisk „Zapisz”. Dobrą praktyką jest również wyczyszczenie pamięci podręcznej PrestaShop (Zaawansowane > Wydajność) i przetestowanie funkcjonalności wyszukiwania w swoim sklepie, aby upewnić się, że zmiany zostały zastosowane zgodnie z oczekiwaniami.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie wprowadza żadnych nowych dedykowanych ekranów administracyjnych ani niestandardowych kontrolerów. Cała konfiguracja jest obsługiwana bezpośrednio na standardowej stronie konfiguracji modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Szukaj w nazwie produktu | TAK | Uwzględnij nazwy produktów w wyszukiwaniu. |
| Strona konfiguracji modułu | Szukaj w krótkim opisie produktu | TAK | Uwzględnij krótkie opisy w wyszukiwaniu. |
| Strona konfiguracji modułu | Szukaj w długim opisie produktu | TAK / NIE | Uwzględnij pełne opisy. |
| Strona konfiguracji modułu | Szukaj w referencji produktu | TAK / NIE | Uwzględnij numery referencyjne produktów. |
| Strona konfiguracji modułu | Szukaj w EAN13/JAN produktu | TAK / NIE | Uwzględnij kody kreskowe EAN13/JAN. |
| Strona konfiguracji modułu | Szukaj w UPC produktu | TAK / NIE | Uwzględnij kody kreskowe UPC. |
| Strona konfiguracji modułu | Szukaj w tagach produktu | TAK | Uwzględnij tagi produktów. |
| Strona konfiguracji modułu | Szukaj w nazwie producenta | TAK | Uwzględnij nazwy producentów. |
| Strona konfiguracji modułu | Szukaj w nazwie dostawcy | NIE / TAK | Uwzględnij nazwy dostawców. |
| Strona konfiguracji modułu | Szukaj w nazwie kategorii | TAK | Uwzględnij nazwy kategorii. |
| Strona konfiguracji modułu | Szukaj w wartości cechy | TAK | Uwzględnij wartości cech produktów. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P1: Zmieniłem ustawienia, ale wyniki wyszukiwania się nie zmieniły. Co jest nie tak?**
O: PrestaShop używa buforowania, aby przyspieszyć działanie Twojego sklepu. Po zmianie ustawień modułu często trzeba wyczyścić pamięć podręczną.

-   **Rozwiązanie:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Następnie ponownie przetestuj wyszukiwanie.

**P2: Pasek wyszukiwania mojego niestandardowego motywu wygląda inaczej. Czy ten moduł nadal będzie działać?**
O: Tak, moduł „Wyszukiwanie docelowe” przede wszystkim nadpisuje *logikę* przetwarzania zapytań wyszukiwania przez PrestaShop, a nie wygląd wizualny samego paska wyszukiwania. Powinien działać bezproblemowo z większością niestandardowych motywów.

-   **Rozwiązanie:** Jeśli napotkasz nieoczekiwane problemy wizualne lub wyszukiwanie nie działa, może to być rzadki konflikt z niestandardowym szablonem wyszukiwania Twojego motywu. Skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P3: Czy ten moduł wpływa na optymalizację pod kątem wyszukiwarek (SEO)?**
O: Bezpośrednio, nie. Ten moduł poprawia *wewnętrzne* doświadczenie wyszukiwania dla Twoich klientów na Twojej stronie internetowej. Nie wpływa bezpośrednio na to, jak zewnętrzne wyszukiwarki (takie jak Google) indeksują lub rankują Twoją stronę. Jednak poprawiając doświadczenie wyszukiwania na stronie, możesz zmniejszyć współczynnik odrzuceń i zwiększyć czas spędzony na stronie, co jest pozytywnym sygnałem dla SEO.

**P4: Czy mogę przetłumaczyć ustawienia lub komunikaty modułu?**
O: Moduł „Wyszukiwanie docelowe” działa głównie w tle i nie wprowadza nowego tekstu w sklepie, który wymagałby tłumaczenia. Opcje konfiguracji w panelu administracyjnym są zazwyczaj w języku angielskim. Gdyby wprowadzono nowy tekst, przetłumaczyłbyś go za pomocą **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop, wybierając „Tłumaczenia zainstalowanych modułów”, a następnie moduł „Wyszukiwanie docelowe”.

**P5: Co jeśli chcę wyszukiwać w polu, którego nie ma na liście ustawień modułu?**
O: Moduł oferuje opcje dla najczęściej używanych i najbardziej wpływowych pól produktu. Jeśli masz bardzo specyficzne niestandardowe pole, które musisz uwzględnić w wyszukiwaniu, będzie to wymagało niestandardowego rozwoju.

-   **Rozwiązanie:** Skontaktuj się z pomocą techniczną MyPresta.eu lub deweloperem PrestaShop, aby omówić niestandardowe modyfikacje.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Wyszukiwanie docelowe” działa głównie poprzez nadpisywanie podstawowej klasy `Search` PrestaShop. Pozwala to na przechwytywanie i modyfikowanie domyślnej logiki zapytań wyszukiwania, zanim trafią one do bazy danych. Moduł wykorzystuje system nadpisywania PrestaShop do wstrzykiwania niestandardowych parametrów wyszukiwania na podstawie konfiguracji sprzedawcy. Jest to lekki moduł, skupiający się na modyfikowaniu istniejącego podstawowego zachowania, a nie na wprowadzaniu złożonych nowych encji lub kontrolerów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front Office ani Back Office. Jego funkcjonalność jest zintegrowana poprzez nadpisanie podstawowej klasy i poprzez standardową metodę `getContent()` modułu do konfiguracji.

### 4.3 Klasy podstawowe i modele (`classes/`)

Rdzeń funkcjonalności tego modułu znajduje się w jego nadpisaniu klasy `Search`.

-   **`targetsearch/override/classes/index.php`**:
    -   Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach w celu zapobiegania listowaniu katalogów ze względów bezpieczeństwa. Nie zawiera żadnego kodu funkcjonalnego.
-   **`targetsearch/override/classes/Search.php`**:
    -   **Nazwa klasy**: `Search` (nadpisuje podstawową `classes/Search.php`)
    -   **Klasa nadrzędna**: `SearchCore`
    -   **Odpowiedzialność**: Ta klasa jest odpowiedzialna za modyfikowanie metody `search` podstawowej klasy `Search`. Odczytuje ustawienia konfiguracyjne przechowywane w `ps_configuration` (np. `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION` itd.) i dynamicznie dostosowuje zapytanie SQL używane do wyszukiwania produktów.
    -   **Kluczowe metody publiczne**:
        -   `search($id_lang, $expr, $page_number = 1, $page_size = 10, $order_by = 'position', $order_way = 'desc', $ajax = false, $use_cookie = true, Context $context = null)`: Ta metoda jest nadpisywana w celu wstrzyknięcia niestandardowych warunków wyszukiwania. Konstruuje klauzulę `WHERE` zapytania SQL na podstawie włączonych celów wyszukiwania. Sprawdza `Configuration::get('TARGETSEARCH_...')` dla każdego celu (nazwa produktu, opis, referencja, EAN13, UPC, tagi, producent, dostawca, kategoria, wartość cechy) i dodaje odpowiednie warunki `LIKE` do zapytania.
    -   **Interakcja z bazą danych**: Nie wchodzi w interakcje z niestandardowymi tabelami bazy danych. Modyfikuje zapytanie, które wchodzi w interakcje ze standardowymi tabelami produktów, kategorii, producentów, dostawców i cech PrestaShop.
    -   **`$definition`**: Nie dotyczy, ponieważ nadpisuje podstawową klasę i nie definiuje nowego `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`targetsearch/targetsearch.js`**:
    -   **Zakres**: Panel administracyjny (potencjalnie, ale zazwyczaj nie używany do logiki wyszukiwania w sklepie).
    -   **Cel**: Ten plik jest zazwyczaj pusty lub zawiera minimalny kod JavaScript, często do podstawowych interakcji UI na stronie konfiguracji modułu, jeśli potrzebna byłaby zaawansowana logika po stronie klienta. Biorąc pod uwagę, że główną funkcją modułu jest logika wyszukiwania po stronie serwera, ten plik raczej nie będzie zawierał złożonego kodu JS związanego z wyszukiwaniem w sklepie. Może to być symbol zastępczy lub dla drobnych ulepszeń formularzy w panelu administracyjnym.
    -   **Słuchacze zdarzeń/manipulacja DOM**: Mało prawdopodobne, aby zawierał znaczące słuchacze zdarzeń w sklepie lub manipulację DOM związaną z wyszukiwaniem. Jego główną rolą byłoby obsługa strony konfiguracji modułu w panelu administracyjnym.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`targetsearch/targetsearch.css`**:
    -   **Zakres**: Panel administracyjny.
    -   **Cel**: Ten arkusz stylów jest zazwyczaj używany do stylizowania strony konfiguracji modułu w Panelu administracyjnym PrestaShop, zapewniając jej spójny wygląd z motywem administracyjnym. Może zawierać style dla elementów formularzy, alertów lub specyficznych dostosowań układu dla ustawień modułu.
    -   **Kluczowe selektory klas CSS**: Prawdopodobnie celuje w standardowe klasy administracyjne PrestaShop lub specyficzne identyfikatory/klasy w ramach danych wyjściowych `getContent()` modułu.
-   **`targetsearch/targetsearch15.css`**:
    -   **Zakres**: Panel administracyjny (specyficznie dla PrestaShop 1.5.x).
    -   **Cel**: Ten plik zapewnia specyficzne dostosowania stylów dla strony konfiguracji modułu podczas działania na PrestaShop 1.5.x, uwzględniając różnice w strukturze i CSS motywu administracyjnego.
    -   **Kluczowe selektory klas CSS**: Podobnie jak `targetsearch.css`, ale dostosowane do środowiska administracyjnego PS 1.5.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`targetsearch/targetsearch-top.tpl`**:
    -   **Zakres**: Front Office.
    -   **Hook**: Ten szablon jest prawdopodobnie zaprojektowany do podłączenia do `displayHeader` lub `displayTop` (lub podobnych hooków, które renderują zawartość w obszarze nagłówka).
    -   **Cel**: Chociaż podstawową funkcją modułu jest logika wyszukiwania, ten szablon może być używany do wyprowadzania ukrytego pola, małego skryptu lub specyficznego elementu wizualnego związanego z obecnością modułu, chociaż nie jest to ściśle konieczne dla samego nadpisania wyszukiwania. Biorąc pod uwagę opis modułu, bardziej prawdopodobne jest, że ten szablon jest symbolem zastępczym lub dla bardzo drobnego, niekrytycznego komponentu wizualnego, ponieważ główny wpływ modułu dotyczy *wyników* wyszukiwania, a nie *pola* wyszukiwania. Może to być również pozostałość po wcześniejszej wersji lub szablon przeznaczony dla przyszłej funkcji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli PrestaShop `ps_configuration`.
        -   Klucze: `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, `TARGETSEARCH_SHORT_DESCRIPTION`, `TARGETSEARCH_REFERENCE`, `TARGETSEARCH_EAN13`, `TARGETSEARCH_UPC`, `TARGETSEARCH_TAGS`, `TARGETSEARCH_MANUFACTURER`, `TARGETSEARCH_SUPPLIER`, `TARGETSEARCH_CATEGORY`, `TARGETSEARCH_FEATURE_VALUE`.
        -   Wartości: `1` (włączone) lub `0` (wyłączone).
-   **Tabela zarejestrowanych hooków**:
    Moduł rejestruje standardowe hooki głównie do instalacji i deinstalacji, a potencjalnie do renderowania swojej konfiguracji. Jego podstawowa funkcjonalność odbywa się poprzez nadpisanie klasy, a nie bezpośrednio przez hooki.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `install` | Podczas instalacji modułu. | Tworzy wpisy konfiguracyjne w `ps_configuration` z wartościami domyślnymi. |
| `uninstall` | Podczas deinstalacji modułu. | Usuwa wpisy konfiguracyjne z `ps_configuration`. |
| `displayHeader` (lub podobny) | Renderuje zawartość w sekcji `<head>` lub na górze strony. | Potencjalnie używany do dołączenia `targetsearch.js` lub `targetsearch.css`, jeśli zawierają zasoby front-office, lub do renderowania `targetsearch-top.tpl`. |
| `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` Panelu administracyjnego. | Używany do dołączenia `targetsearch.css` (i `targetsearch15.css` warunkowo) do stylizowania strony konfiguracji modułu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „Wyszukiwanie docelowe” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
