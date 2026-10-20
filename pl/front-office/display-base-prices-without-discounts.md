---
title: "Wyświetlanie cen podstawowych (bez rabatów) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Wyświetlanie cen podstawowych (bez rabatów)” od MyPresta.eu."
sidebar:
  label: "Wyświetlanie cen podstawowych (bez rabatów) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Display base prices (without discounts) na MyPresta.eu](https://mypresta.eu/modules/front-office-features/display-base-prices-without-discounts.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/display-base-prices-without-discounts/)
>
> ---


# Wyświetlanie cen podstawowych (bez rabatów)

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień. Jest to główny ekran, na którym kontrolujesz, jak i gdzie wyświetlane są ceny podstawowe.

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Włącz moduł** | Jest to główny przełącznik do włączania lub wyłączania funkcjonalności modułu. | *Po włączeniu:* Moduł zacznie wyświetlać ceny podstawowe w Twoim front-office zgodnie z innymi ustawieniami. *Po wyłączeniu:* Moduł przestanie wyświetlać ceny podstawowe, a Twój sklep powróci do wyświetlania tylko aktualnych cen. | TAK | Właśnie zainstalowałeś moduł i chcesz aktywować jego funkcje. |
| **Wyświetl na stronie produktu** | Kontroluje, czy cena podstawowa jest wyświetlana na indywidualnych stronach szczegółów produktu. | *Po włączeniu:* Oryginalna cena pojawi się obok ceny po rabacie na stronie każdego produktu. *Po wyłączeniu:* Cena podstawowa nie będzie wyświetlana na stronach produktów, nawet jeśli jest włączona gdzie indziej. | TAK | Chcesz, aby klienci przeglądający konkretny produkt wyraźnie widzieli oszczędności. |
| **Wyświetl na stronach kategorii** | Kontroluje, czy cena podstawowa jest wyświetlana na stronach list produktów (np. stronach kategorii, wynikach wyszukiwania). | *Po włączeniu:* Oryginalna cena pojawi się obok ceny po rabacie dla każdego produktu wymienionego w kategoriach, wynikach wyszukiwania itp. *Po wyłączeniu:* Cena podstawowa nie będzie wyświetlana na stronach list produktów. | TAK | Chcesz, aby klienci przeglądający kategorie szybko identyfikowali przecenione produkty i ich oszczędności. |
| **Wyświetl w podsumowaniu koszyka** | Kontroluje, czy cena podstawowa jest wyświetlana w podsumowaniu koszyka. | *Po włączeniu:* Oryginalna cena będzie widoczna dla każdego produktu w koszyku klienta, wzmacniając całkowite oszczędności. *Po wyłączeniu:* W koszyku będzie wyświetlana tylko aktualna cena po rabacie. | NIE (lub TAK, w zależności od szablonu) | Chcesz przypomnieć klientom o ich całkowitych oszczędnościach przed przejściem do kasy. Jednak niektóre szablony mogą nie mieć odpowiedniego obszaru wyświetlania, lub może to zaśmiecać koszyk. Dokładnie przetestuj. |
| **Niestandardowy CSS dla ceny podstawowej** | Pozwala dodać niestandardowe reguły CSS do stylizacji wyświetlanej ceny podstawowej. | *Po wypełnieniu CSS:* Cena podstawowa zostanie ostylowana zgodnie z Twoim wpisem (np. rozmiar czcionki, kolor, przekreślenie). *Po pozostawieniu pustego:* Moduł użyje domyślnej stylizacji lub odziedziczy style z Twojego szablonu. | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Chcesz, aby cena podstawowa była wyszarzona i przekreślona, aby wyraźnie odróżnić ją od aktualnej ceny. |
| **Pozycja ceny podstawowej** | Określa, gdzie cena podstawowa jest wstrzykiwana względem aktualnej ceny. | *Opcje: Przed aktualną ceną, Po aktualnej cenie.* *Po ustawieniu na „Przed”:* Cena podstawowa pojawi się po lewej stronie aktualnej ceny. *Po ustawieniu na „Po”:* Cena podstawowa pojawi się po prawej stronie aktualnej ceny. | Przed aktualną ceną | Chcesz, aby klient najpierw zobaczył oryginalną cenę, a następnie nową, niższą cenę. |

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł | TAK | Aktywuje/dezaktywuje podstawową funkcjonalność modułu. |
| Konfiguracja modułu | Wyświetl na stronie produktu | TAK | Pokazuje cenę podstawową na indywidualnych stronach produktów. |
| Konfiguracja modułu | Wyświetl na stronach kategorii | TAK | Pokazuje cenę podstawową na stronach list produktów (kategorie, wyszukiwanie). |
| Konfiguracja modułu | Wyświetl w podsumowaniu koszyka | NIE (lub TAK, test) | Pokazuje cenę podstawową w koszyku. |
| Konfiguracja modułu | Niestandardowy CSS dla ceny podstawowej | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Dostosowuje styl wizualny ceny podstawowej. |
| Konfiguracja modułu | Pozycja ceny podstawowej | Przed aktualną ceną | Kontroluje umiejscowienie względem aktualnej ceny. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Ceny podstawowe nie wyświetlają się w moim sklepie, mimo że moduł jest włączony.**
O:

1.  **Sprawdź ustawienia modułu:** Upewnij się, że „Włącz moduł” i konkretne opcje wyświetlania (np. „Wyświetl na stronie produktu”) są ustawione na TAK.
2.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Pamięć podręczna Smarty często wymaga wyczyszczenia, aby zmiany w szablonie były widoczne.
3.  **Sprawdź rabaty:** Upewnij się, że produkty, które testujesz, faktycznie mają zastosowane aktywne rabaty (reguły cen katalogowych, ceny specyficzne lub obniżki procentowe). Moduł wyświetla cenę podstawową tylko wtedy, gdy istnieje różnica.
4.  **Kompatybilność z szablonem:** Niektóre mocno dostosowane szablony mogą nadpisywać podstawowe funkcje wyświetlania cen PrestaShop. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Cena podstawowa jest wyświetlana, ale nie wygląda dobrze z moim szablonem (zły kolor, rozmiar itp.).**
O: Użyj ustawienia „Niestandardowy CSS dla ceny podstawowej” w konfiguracji modułu. Możesz dodać reguły CSS, aby dopasować je do projektu Twojego szablonu. Na przykład, aby była szara i przekreślona: `text-decoration: line-through; color: #999; font-size: 0.9em;`. Jeśli nie jesteś pewien co do CSS, programista stron internetowych może pomóc.

**P: Czy ten moduł spowolni mój sklep?**
O: Moduł jest zaprojektowany tak, aby był lekki. Głównie nadpisuje podstawową klasę PrestaShop (`Product.php`), aby pobrać cenę podstawową i wstrzykuje mały szablon. Wpływ na wydajność powinien być znikomy. Zawsze upewnij się, że pamięć podręczna PrestaShop jest włączona dla optymalnej szybkości.

**P: Czy ten moduł działa ze sklepami wielojęzycznymi?**
O: Tak, moduł działa z funkcjami wielojęzycznymi PrestaShop. Ceny są wyświetlane w walucie i formacie aktywnego języka/kraju.

**P: Widzę błąd „Konflikt nadpisania” po zainstalowaniu modułu.**
O: Ten moduł nadpisuje klasę `Product.php`. Jeśli inny moduł również próbuje nadpisać tę samą klasę, możesz napotkać konflikt. PrestaShop 1.7+ ma lepsze zarządzanie nadpisaniami, ale konflikty nadal mogą wystąpić. Będziesz musiał albo wyłączyć jeden z konfliktujących modułów, albo ręcznie połączyć nadpisania (wymaga wiedzy programistycznej). Skontaktuj się z pomocą techniczną MyPresta.eu w celu uzyskania pomocy.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Wyświetlanie cen podstawowych (bez rabatów)” działa głównie poprzez nadpisanie podstawowej klasy `Product` w celu wprowadzenia metody pobierania ceny podstawowej produktu bez obniżek. Następnie wykorzystuje szablon Smarty do wyświetlania tej ceny w front-office, wstrzykiwany za pomocą niestandardowego mechanizmu hooków. Konfiguracja modułu jest zarządzana za pomocą standardowej metody PrestaShop `getContent()` w głównym pliku modułu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego funkcjonalność jest zintegrowana bezpośrednio z istniejącymi mechanizmami wyświetlania cen PrestaShop i poprzez nadpisanie.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   **`baseprices/override/classes/index.php`**: Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.
-   **`baseprices/override/classes/Product.php`**:
    -   **Nazwa klasy**: `Product` (nadpisuje podstawową klasę `Product`)
    -   **Klasa nadrzędna**: `ProductCore`
    -   **Odpowiedzialność**: To nadpisanie jest rdzeniem funkcjonalności modułu. Wprowadza nową metodę, `getBasePrice()`, która oblicza i zwraca cenę produktu *przed* zastosowaniem jakichkolwiek cen specyficznych, reguł cen katalogowych lub obniżek grupowych. Ta metoda zapewnia, że prawdziwa oryginalna cena jest zawsze dostępna do wyświetlenia. Zazwyczaj polega na omijaniu standardowej logiki obliczania cen, która uwzględnia rabaty.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`baseprices/views/js/baseprices-admin.js`**:
    -   **Zakres**: Back-office (strona konfiguracji modułu).
    -   **Odpowiedzialność**: Ten skrypt prawdopodobnie obsługuje wszelkie dynamiczne zachowania lub walidację na formularzu konfiguracji modułu. Na przykład, może pokazywać/ukrywać ustawienia w zależności od innych wyborów lub zapewniać informacje zwrotne w czasie rzeczywistym dla niestandardowego pola CSS.
-   **`baseprices/views/js/baseprices.js`**:
    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Ten skrypt jest odpowiedzialny za dynamiczne wstrzykiwanie ceny podstawowej do DOM tam, gdzie jest to potrzebne, zwłaszcza dla treści ładowanych przez AJAX lub gdy zmieniają się atrybuty produktu (np. wybór innej kombinacji na stronie produktu). Nasłuchuje zdarzenia `updateProduct` PrestaShop lub podobnych zdarzeń, aby odświeżyć wyświetlanie ceny. Może również obsługiwać stylizację lub przełączanie widoczności elementu ceny podstawowej.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`baseprices/views/css/baseprices.css`**:
    -   **Zakres**: Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Ten arkusz stylów zapewnia domyślną prezentację wizualną ceny podstawowej. Zazwyczaj zawiera reguły dla:
        -   `span.base-price` lub podobnych selektorów.
        -   `text-decoration: line-through;` do przekreślenia ceny.
        -   `color`, `font-size`, `margin`, `padding` do pozycjonowania i stylizacji ceny podstawowej względem aktualnej ceny.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: `span.base-price`, `div.product-price-and-shipping .base-price`, itp. Programiści mogą celować w te klasy w niestandardowym CSS swojego szablonu, aby nadpisać domyślną stylizację modułu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **`baseprices/views/templates/baseprices.tpl`**:
    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Ten szablon jest głównym wyjściem do wyświetlania ceny podstawowej. Jest zaprojektowany do włączania lub renderowania wszędzie tam, gdzie wyświetlana jest cena produktu. Zazwyczaj otrzymuje zmienne takie jak `$base_price` i `$current_price` i formatuje je zgodnie z ustawieniami modułu (np. niestandardowy CSS, pozycja). Będzie zawierał strukturę HTML (np. `<span class="base-price">...</span>`), na którą celuje CSS.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`, używając kluczy z prefiksem `BASEPRICES_`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Używany do ładowania zasobów CSS i JavaScript modułu dla front-office. |
| `displayProductPriceBlock` | W bloku wyświetlania ceny produktu na stronach produktów i listach. | Moduł prawdopodobnie wykorzystuje ten hook (lub podobne hooki związane z cenami) do wstrzykiwania swojego szablonu `baseprices.tpl`, wyświetlając cenę podstawową obok aktualnej ceny. |
| `actionProductUpdate` / `actionProductSave` | Po zaktualizowaniu lub zapisaniu produktu w Panelu administracyjnym. | Chociaż nie jest to wyraźnie wymienione, moduły, które nadpisują `Product.php`, mogą używać takich hooków do czyszczenia pamięci podręcznej lub ponownego indeksowania danych produktu, jeśli to konieczne, chociaż główną funkcją tego modułu jest tylko wyświetlanie. |
| `actionFrontControllerSetMedia` | Przed renderowaniem szablonu przez kontroler front-office. | Używany do rejestrowania plików JavaScript i CSS dla front-office dla bieżącej strony. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Wyświetlanie cen podstawowych (bez rabatów)”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
"""
