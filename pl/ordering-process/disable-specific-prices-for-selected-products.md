---
title: "Wyłączanie cen specjalnych dla wybranych produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop „Wyłączanie cen specjalnych dla wybranych produktów” od MyPresta.eu."
sidebar:
  label: "Wyłączanie cen specjalnych dla wybranych produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable specific prices for selected products na MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/disable-specific-prices-for-selected-products/)
>
> ---


# Wyłączanie cen specjalnych dla wybranych produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień. Jest to główny i jedyny ekran konfiguracji dla tego modułu.

#### **Ustawienia ogólne**

-   **Wyłączanie cen specjalnych dla wybranych produktów**
    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania podstawowej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie aktywnie zapobiegał stosowaniu cen specjalnych do wybranych produktów i kategorii.
        -   *Gdy wyłączone (NIE):* Moduł będzie nieaktywny. Wszystkie ceny specjalne i reguły cen katalogowych będą stosowane do wszystkich produktów normalnie, niezależnie od Twoich wyborów w polach „Kategorie” lub „Konkretne produkty”.
    -   **Zalecana wartość:** **TAK**, jeśli zamierzasz używać funkcjonalności modułu do wykluczania produktów z rabatów. **NIE**, jeśli chcesz tymczasowo wyłączyć moduł bez utraty zapisanych konfiguracji.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie wprowadziłeś nową linię produktów premium i chcesz mieć pewność, że nigdy nie zostaną przecenione. Włączasz to ustawienie, a następnie dodajesz te produkty do listy wykluczeń.

#### **Kryteria wykluczenia**

-   **Kategorie**

    -   **Co robi to ustawienie:** To pole pozwala wybrać całe kategorie produktów, których produkty powinny być wykluczone z cen specjalnych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są kategorie:* Wszystkie produkty należące do wybranych kategorii (w tym podkategorii, w zależności od struktury kategorii PrestaShop i sposobu stosowania cen specjalnych) będą miały wyłączone ceny specjalne.
        -   *Gdy nie wybrano żadnych kategorii:* Dotyczy to tylko produktów wyraźnie wymienionych w polu „Konkretne produkty”.
    -   **Zalecana wartość:** Wybierz kategorie zawierające produkty, które konsekwentnie chcesz chronić przed rabatami, takie jak „Nowości”, „Towary luksusowe” lub „Wyprzedaż (jeśli chcesz stosować tylko ręczne rabaty)”.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz kategorię „Marki Premium”. Wybierając ją tutaj, wszystkie produkty w tej kategorii zostaną automatycznie wykluczone z obliczeń cen specjalnych, oszczędzając Ci konieczności indywidualnego wymieniania każdego produktu.
-   **Konkretne produkty**

    -   **Co robi to ustawienie:** To pole pozwala wyszukiwać i wybierać pojedyncze produkty, które powinny być wykluczone z cen specjalnych. Wykorzystuje narzędzie wyszukiwania z autouzupełnianiem, aby pomóc Ci szybko znaleźć produkty.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są produkty:* Wybrane pojedyncze produkty będą miały wyłączone ceny specjalne, niezależnie od ich kategorii.
        -   *Gdy nie wybrano żadnych produktów:* Dotyczy to tylko produktów w wybranych „Kategoriach”.
    -   **Zalecana wartość:** Użyj tego dla pojedynczych pozycji, które nie pasują do szerszego wykluczenia kategorii, lub dla konkretnych bestsellerów, które chcesz zachować w pełnej cenie.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz kilka gadżetów o dużym popycie, które zawsze dobrze sprzedają się po pełnej cenie. Wyszukujesz „iPhone 15” i „Samsung Galaxy S24” i dodajesz je do tej listy, aby upewnić się, że nigdy nie zostaną przecenione przez ceny specjalne.

#### **Zapisywanie zmian**

Po wprowadzeniu jakichkolwiek zmian w ustawieniach pamiętaj, aby kliknąć przycisk **„Zapisz”** na dole strony konfiguracji, aby je zastosować.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Wyłączanie cen specjalnych dla wybranych produktów | TAK | Główny przełącznik do włączania/wyłączania funkcjonalności modułu. TAK oznacza, że wykluczenia są aktywne. |
| Strona konfiguracji modułu | Kategorie | Brak wybranych | Wybierz kategorie, których produkty zostaną wykluczone z cen specjalnych. |
| Strona konfiguracji modułu | Konkretne produkty | Brak wybranych | Wyszukaj i wybierz pojedyncze produkty, które mają być wykluczone z cen specjalnych. |

## 3. Rozwiązywanie problemów dla sprzedawcy i często zadawane pytania (FAQ)

**P1: Skonfigurowałem moduł, ale ceny specjalne nadal są stosowane do moich wykluczonych produktów. Co jest nie tak?**
O1:

-   **Sprawdź status modułu:** Najpierw upewnij się, że ustawienie „Wyłączanie cen specjalnych dla wybranych produktów” na stronie konfiguracji modułu jest ustawione na **TAK (Włączone)**.
-   **Zweryfikuj wykluczenia:** Dokładnie sprawdź, czy konkretne produkty lub kategorie, które zamierzasz wykluczyć, są poprawnie wybrane w ustawieniach modułu. Ostrożnie używaj funkcji wyszukiwania produktów.
-   **Wyczyść pamięć podręczną:** PrestaShop często buforuje informacje o cenach. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Wyczyść również pamięć podręczną przeglądarki.
-   **Priorytet ceny specjalnej:** Upewnij się, że reguła ceny specjalnej, którą testujesz, nie nadpisuje w jakiś sposób modułu. Ten moduł działa poprzez nadpisywanie podstawowego obliczania ceny specjalnej PrestaShop. Jeśli masz inne moduły, które również modyfikują ceny, może wystąpić konflikt. Spróbuj tymczasowo wyłączyć inne moduły związane z cenami, aby zdiagnozować problem.

**P2: Czy ten moduł wpłynie na moje reguły koszyka (kupony)?**
O2: Tak, pośrednio. Ten moduł zapobiega stosowaniu cen specjalnych do wybranych produktów. Jeśli reguła koszyka (kupon) oferuje rabat, który *opiera się* na mechanizmie cen specjalnych PrestaShop lub z nim współdziała (np. rabat procentowy, który oblicza się na podstawie aktualnej ceny produktu *po* zastosowaniu cen specjalnych), wówczas wykluczone produkty nie otrzymają tej redukcji ceny specjalnej przed zastosowaniem kuponu. Kupon zostanie następnie zastosowany do ceny bazowej produktu (lub jego ceny po innych rabatach niebędących cenami specjalnymi).

**P3: Czy ten moduł działa z konfiguracjami wielu sklepów?**
O3: Konfiguracja modułu jest zazwyczaj globalna lub związana z kontekstem, w którym ją konfigurujesz. Jeśli masz konfigurację wielu sklepów, dokładnie przetestuj, aby upewnić się, że wykluczenia są stosowane zgodnie z oczekiwaniami we wszystkich odpowiednich sklepach. Mechanizm `override` PrestaShop zazwyczaj działa globalnie, ale same reguły cen specjalnych mogą być specyficzne dla sklepu.

**P4: Dodałem nowy produkt do wykluczonej kategorii, ale nadal otrzymuje ceny specjalne. Dlaczego?**
O4:

-   **Pamięć podręczna:** Zawsze czyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) po wprowadzeniu zmian w kategoriach lub produktach, zwłaszcza jeśli dodajesz nowe elementy lub przenosisz je między kategoriami.
-   **Struktura kategorii:** Upewnij się, że reguła ceny specjalnej nie jest stosowana w sposób, który omija wykluczenie kategorii (np. reguła dla „wszystkich produktów”, która nie respektuje hierarchii kategorii). Moduł powinien przechwytywać obliczanie ceny specjalnej niezależnie, ale pamięć podręczna jest często przyczyną problemu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Wyłączanie cen specjalnych dla wybranych produktów” wykorzystuje system nadpisywania PrestaShop do modyfikacji podstawowej logiki cenowej. W szczególności nadpisuje klasy `Product` i `SpecificPrice`, aby wstrzyknąć swoją logikę wykluczeń bezpośrednio do procesu obliczania ceny. Zapewnia to, że gdy PrestaShop próbuje określić cenę produktu, moduł najpierw sprawdza, czy produkt lub jego kategoria znajduje się na liście wykluczeń, a jeśli tak, zapobiega stosowaniu cen specjalnych. Moduł wykorzystuje standardową strukturę modułu PrestaShop, z głównym plikiem modułu, nadpisaniami i `views` dla zasobów i szablonów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Jego konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu, a jego podstawowa funkcjonalność jest implementowana poprzez nadpisywanie klas.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   **`exsp/override/classes/index.php`**:

    -   Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach, aby zapobiec listowaniu katalogów. Nie ma on wpływu funkcjonalnego na logikę modułu.
-   **`exsp/override/classes/Product.php`**:

    -   **Nazwa klasy i klasa nadrzędna**: `Product` (nadpisuje podstawową klasę `Product` PrestaShop).
    -   **Odpowiedzialność**: To nadpisanie jest głównym mechanizmem przechwytywania obliczeń cen produktów. Modyfikuje metodę `getPrice()` (lub powiązane metody), aby sprawdzić, czy bieżący produkt (lub jego kategoria) jest skonfigurowany do wykluczenia. Jeśli tak, komponent ceny specjalnej obliczenia jest pomijany, zapewniając, że zwracana jest cena bazowa produktu bez żadnych redukcji cen specjalnych. Jest to kluczowe dla zapobiegania stosowaniu cen specjalnych na poziomie produktu.
    -   **Kluczowe metody publiczne**: Nadpisana metoda `getPrice()` (lub podobne metody obliczania ceny w klasie `Product`) będzie zawierać logikę sprawdzania wartości konfiguracji `exsp_categories` i `exsp_products`.
-   **`exsp/override/classes/SpecificPrice.php`**:

    -   **Nazwa klasy i klasa nadrzędna**: `SpecificPrice` (nadpisuje podstawową klasę `SpecificPrice` PrestaShop).
    -   **Odpowiedzialność**: To nadpisanie bezpośrednio wpływa na sposób pobierania i stosowania cen specjalnych. Modyfikuje metody takie jak `getSpecificPrice()` lub `getSpecificPrices()`, aby odfiltrować lub zignorować reguły cen specjalnych dla produktów znajdujących się na liście wykluczeń. Działa to jako druga warstwa obrony, zapewniając, że nawet jeśli istnieje reguła ceny specjalnej, nie będzie ona brana pod uwagę dla wykluczonych produktów.
    -   **Kluczowe metody publiczne**: Nadpisane metody związane z pobieraniem lub stosowaniem cen specjalnych będą zawierać sprawdzenia względem list wykluczeń modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`exsp/lib/searchTool/views/js/autocomplete.js`**:

    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu).
    -   **Opis**: Ten skrypt zapewnia funkcjonalność autouzupełniania dla pola wprowadzania „Konkretne produkty” na stronie konfiguracji modułu. Prawdopodobnie używa AJAX do wysyłania zapytań do bazy danych produktów PrestaShop, gdy użytkownik pisze, sugerując pasujące nazwy produktów. Obsługuje wyświetlanie sugestii i wybór produktów do dodania do listy wykluczeń.
    -   **Słuchacze zdarzeń**: Zdarzenia `keyup` na polu wyszukiwania produktów, zdarzenia `click` na sugestiach autouzupełniania.
    -   **Manipulacja DOM**: Dynamicznie tworzy i aktualizuje listę sugestii, dodaje wybrane produkty do ukrytego pola wprowadzania lub obszaru wyświetlania.
-   **`exsp/views/js/exsp.js`**:

    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu).
    -   **Opis**: Jest to główny plik JavaScript dla interfejsu konfiguracji modułu. Obsługuje inicjalizację narzędzia wyszukiwania z autouzupełnianiem, zarządza wyświetlaniem i usuwaniem wybranych produktów/kategorii oraz potencjalnie wykonuje inne interakcje interfejsu użytkownika specyficzne dla ustawień modułu.
    -   **Słuchacze zdarzeń**: Zdarzenia `click` dla usuwania wybranych produktów/kategorii, potencjalnie zdarzenia `change` dla głównego przełącznika włączania/wyłączania.
    -   **Manipulacja DOM**: Zarządza wizualną reprezentacją wybranych kategorii i produktów, aktualizuje ukryte pola wprowadzania, które przechowują wartości konfiguracji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`exsp/lib/searchTool/views/css/autocomplete.css`**:
    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu).
    -   **Opis**: Ten arkusz stylów zapewnia wizualne style dla pola wyszukiwania z autouzupełnianiem i jego listy sugestii. Definiuje wygląd pola wyszukiwania, rozwijanych sugestii oraz potencjalnie stany najechania/aktywne dla lepszego doświadczenia użytkownika.
    -   **Główne komponenty interfejsu użytkownika**: `.autocomplete-container`, `.autocomplete-suggestions`, `.autocomplete-suggestion`.
    -   **Kluczowe selektory klas CSS**: `.exsp-product-search-input`, `.exsp-selected-item`, `.exsp-remove-item`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`exsp/lib/searchTool/views/scripts.tpl`**:

    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu).
    -   **Opis**: Ten szablon prawdopodobnie zawiera niezbędne pliki JavaScript i CSS dla narzędzia wyszukiwania z autouzupełnianiem, lub może zawierać wbudowany kod JavaScript do inicjalizacji widżetu autouzupełniania z określonymi parametrami (np. URL AJAX do wyszukiwania produktów).
    -   **Renderowany w**: Haku `ActionAdminControllerSetMedia` lub bezpośrednio w `getContent()`.
-   **`exsp/views/script.tpl`**:

    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu).
    -   **Opis**: Ten szablon jest odpowiedzialny za renderowanie głównego formularza konfiguracji modułu. Zawiera strukturę HTML dla przełącznika włączania/wyłączania, pola wyboru kategorii i pola wyszukiwania produktów z powiązanym wyświetlaniem wybranych produktów. Prawdopodobnie zawiera również skrypty `exsp.js` i `autocomplete.js`.
    -   **Renderowany w**: Metodzie `getContent()` pliku `exsp.php`.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne (status włączenia, wykluczone kategorie, wykluczone produkty) w tabeli `ps_configuration` PrestaShop.
        -   `exsp_categories`: Przechowuje serializowaną tablicę lub listę identyfikatorów kategorii oddzielonych przecinkami do wykluczenia.
        -   `exsp_products`: Przechowuje serializowaną tablicę lub listę identyfikatorów produktów oddzielonych przecinkami do wykluczenia.
        -   `exsp_enabled`: Przechowuje status włączenia/wyłączenia modułu (np. `1` dla włączonego, `0` dla wyłączonego).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany po załadowaniu kontrolera administratora, przed renderowaniem jego zawartości. | Służy do rejestrowania i dołączania zasobów JavaScript i CSS modułu (np. dla narzędzia wyszukiwania z autouzupełnianiem) na stronie konfiguracji modułu. |
| (Implicit Hooks via Overrides) | Podczas obliczania ceny produktu (`Product::getPrice()`) i pobierania ceny specjalnej (`SpecificPrice::getSpecificPrices()`). | Podstawowa funkcjonalność modułu jest implementowana poprzez nadpisywanie klas `Product` i `SpecificPrice` PrestaShop. Oznacza to, że logika modułu jest wykonywana za każdym razem, gdy te podstawowe metody są wywoływane, skutecznie „wpinając się” w proces obliczania ceny bez jawnego rejestrowania haka `display` lub `action`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyłączanie cen specjalnych dla wybranych produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
