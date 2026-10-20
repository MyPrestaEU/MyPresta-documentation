---
title: "Pretty / Clean URLs PRO - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Pretty / Clean URLs PRO PrestaShop od MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Pretty / Clean URLs PRO na MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/pretty-clean-urls-pro/)
>
> ---


# Pretty / Clean URLs PRO

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twój serwer musi mieć również włączony `mod_rewrite` dla Apache lub równoważną funkcjonalność przepisywania URL dla Nginx, co jest standardem dla większości instalacji PrestaShop.
-   **Przyjazne adresy URL PrestaShop**: Natywna opcja „Przyjazny URL” PrestaShop (znajdująca się w **Parametry sklepu > SEO i URL**) *musi być włączona*, aby ten moduł działał poprawnie. Ten moduł rozszerza natywną funkcjonalność PrestaShop, nie zastępuje jej.

## 2. Kompletny przewodnik konfiguracji

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu „Pretty / Clean URLs PRO”. Tutaj kontrolujesz podstawowe zachowanie modułu.

**Ustawienia ogólne**

-   **Włącz ładne adresy URL:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik modułu. Kontroluje, czy moduł aktywnie generuje i używa czystych adresów URL w całym Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł zacznie generować i przekierowywać do czystych adresów URL dla wszystkich obsługiwanych typów stron (produktów, kategorii, CMS itp.).
        -   *Gdy wyłączone:* Moduł będzie nieaktywny, a PrestaShop powróci do swojej domyślnej struktury URL (która może zawierać identyfikatory).
    -   **Zalecana wartość:** **TAK** (Jest to podstawowa funkcja modułu).
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz aktywować jego korzyści SEO. Włączyłbyś to ustawienie. Jeśli potrzebujesz tymczasowo rozwiązać problem lub powrócić do domyślnego zachowania PrestaShop, możesz je wyłączyć.
-   **Usuń identyfikatory z adresów URL:**
    -   **Co robi to ustawienie:** Ta opcja kontroluje, czy numeryczny identyfikator (np. `123` w `twojasklep.com/123-moj-produkt`) jest usuwany z adresów URL.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Adresy URL będą krótsze i czystsze, np. `twojasklep.com/moj-produkt`. Jest to ogólnie lepsze dla SEO i estetyki.
        -   *Gdy wyłączone:* Adresy URL nadal będą „ładne”, ale zachowają identyfikator, np. `twojasklep.com/123-moj-produkt`. Może to być przydatne, jeśli masz zewnętrzne systemy, które polegają na obecności identyfikatora w adresie URL, choć jest to mniej powszechne.
    -   **Zalecana wartość:** **TAK** (Dla maksymalnych korzyści SEO i czystej estetyki).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć absolutnie najczystsze adresy URL dla lepszego indeksowania przez wyszukiwarki i czytelności dla użytkowników. Włączyłbyś to.
-   **Automatyczne przekierowanie 301:**
    -   **Co robi to ustawienie:** To krytyczne ustawienie nakazuje modułowi automatyczne tworzenie stałych przekierowań 301 ze starych adresów URL opartych na identyfikatorach do nowych, czystych adresów URL.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Każdy odwiedzający lub bot wyszukiwarki próbujący uzyskać dostęp do starego adresu URL (np. takiego, który był indeksowany przed aktywacją modułu) zostanie płynnie przekierowany do nowego, czystego adresu URL. Zapobiega to błędom 404 i zachowuje wartość SEO Twoich linków.
        -   *Gdy wyłączone:* Stare adresy URL będą prowadzić do błędów 404 „Strona nie znaleziona”, co jest złe dla doświadczenia użytkownika i może poważnie zaszkodzić Twojemu SEO.
    -   **Zalecana wartość:** **TAK** (Absolutnie niezbędne do utrzymania SEO i doświadczenia użytkownika podczas i po przejściu na czyste adresy URL).
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie aktywowałeś moduł w istniejącym sklepie z wieloma indeksowanymi stronami. Włączenie tego zapewnia, że wszystkie Twoje stare linki nadal działają i przekazują swoją wartość SEO nowym linkom.
-   **Wymuś ukośnik na końcu (Trailing Slash):**
    -   **Co robi to ustawienie:** Określa, czy ukośnik (`/`) jest zawsze dodawany na końcu Twoich adresów URL (np. `twojasklep.com/kategoria/` vs. `twojasklep.com/kategoria`).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Wszystkie wygenerowane adresy URL będą kończyć się ukośnikiem. Może to pomóc w spójności adresów URL, a niektóre narzędzia SEO to preferują.
        -   *Gdy wyłączone:* Adresy URL niekoniecznie będą kończyć się ukośnikiem, w zależności od domyślnego zachowania PrestaShop dla danego typu strony.
    -   **Zalecana wartość:** **TAK** (Dla spójności i aby uniknąć potencjalnych problemów z duplikacją treści, jeśli wyszukiwarki traktują `url` i `url/` jako różne strony).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby wszystkie adresy URL Twoich kategorii i stron CMS konsekwentnie kończyły się ukośnikiem dla lepszego zarządzania SEO i zapobiegania potencjalnym problemom z duplikacją treści.
-   **Usuń rozszerzenie .html:**
    -   **Co robi to ustawienie:** Ta opcja kontroluje, czy rozszerzenie `.html` jest usuwane z adresów URL stron produktów i CMS.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Adresy URL będą jeszcze krótsze, np. `twojasklep.com/moj-produkt` zamiast `twojasklep.com/moj-produkt.html`. Jest to ogólnie preferowane dla nowoczesnego projektowania stron internetowych i SEO.
        -   *Gdy wyłączone:* Adresy URL stron produktów i CMS zachowają rozszerzenie `.html`.
    -   **Zalecana wartość:** **TAK** (Dla najczystszej, najbardziej nowoczesnej struktury URL).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoje strony produktów wyglądały jak `twojasklep.com/moj-produkt` zamiast `twojasklep.com/moj-produkt.html` dla bardziej eleganckiego wyglądu i lepszego SEO.

**Przycisk Zapisz:**

-   Zawsze kliknij przycisk „Zapisz” po wprowadzeniu jakichkolwiek zmian, aby zastosować je w swoim sklepie.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł działa głównie poprzez nadpisywanie podstawowych klas i kontrolerów PrestaShop w celu modyfikacji generowania i routingu adresów URL. Chociaż nie wprowadza nowej, dedykowanej pozycji menu w Panelu administracyjnym do zarządzania listą „Ładnych adresów URL”, integruje się bezpośrednio z istniejącymi funkcjonalnościami PrestaShop.

**Integracja z AdminProductsController (Panel administracyjny > Katalog > Produkty)**

-   **Nazwa ekranu i lokalizacja menu:** **Katalog > Produkty**
-   **Dostępne akcje i ustawienia:**
    -   Podczas edycji lub tworzenia produktu moduł wpływa na zachowanie pola „Przyjazny URL”. Zamiast wymagać ręcznego usuwania identyfikatorów lub zapewniania czystej struktury, logika modułu automatycznie wygeneruje i zasugeruje czysty, wolny od identyfikatorów adres URL na podstawie nazwy produktu i ustawień modułu.
    -   Moduł zapewnia, że po zapisaniu produktu jego adres URL jest generowany zgodnie z ustawieniami modułu „Pretty / Clean URLs PRO” (np. bez identyfikatora, bez rozszerzenia `.html`, jeśli tak skonfigurowano).
-   **Efekt zmian:**
    -   Po zapisaniu produktu adres URL wygenerowany i używany przez PrestaShop będzie odzwierciedlał czystą strukturę URL zdefiniowaną w konfiguracji modułu.
    -   Jeśli zmienisz nazwę produktu, moduł pomoże zapewnić czystą aktualizację przyjaznego adresu URL.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Kontynuuj zarządzanie produktami jak zwykle w sekcji **Katalog > Produkty**. Moduł działa w tle, aby zapewnić optymalizację adresów URL.
    -   Podczas tworzenia lub edycji produktów upewnij się, że nazwy produktów są opisowe, ponieważ są one używane do generowania przyjaznych adresów URL.
    -   Nadal możesz ręcznie dostosować pole „Przyjazny URL” dla produktu, jeśli potrzebujesz konkretnego adresu URL, ale logika modułu będzie kierować początkowym generowaniem.

**Inne kontrolery administracyjne (integracja niejawna)**

Moduł wpływa również niejawnie na inne obszary, w których generowane są adresy URL, takie jak:

-   **Katalog > Kategorie**: Podczas tworzenia lub edycji kategorii.
-   **Katalog > Producenci**: Podczas tworzenia lub edycji producentów.
-   **Katalog > Dostawcy**: Podczas tworzenia lub edycji dostawców.
-   **Wygląd > Strony (CMS)**: Podczas tworzenia lub edycji stron CMS.

We wszystkich tych przypadkach moduł zapewnia, że przyjazne adresy URL generowane przez PrestaShop są zgodne z ustawieniami „Pretty / Clean URLs PRO”, usuwając identyfikatory i rozszerzenia zgodnie z konfiguracją.

### 2.3 Integracja ustawień SEO i URL PrestaShop

Moduł "Pretty / Clean URLs PRO" od wersji 2.8.3 i wyższych posiada własną dedykowaną sekcję do definiowania schematów URL, co sprawia, że ręczna konfiguracja tych ustawień w natywnej sekcji PrestaShop **Parametry sklepu > SEO i URL** jest zbędna. Kluczowe jest jednak zrozumienie interakcji.

:::caution Ważna uwaga
Chociaż moduł zarządza schematem URL, natywna opcja **Przyjazny URL** PrestaShop w sekcji **Parametry sklepu > SEO i URL** *musi być włączona*, aby moduł działał. Moduł rozszerza tę podstawową funkcjonalność PrestaShop.
:::

**Schemat adresów URL (zarządzany przez moduł)**

Historycznie, użytkownicy PrestaShop definiowali wzorce adresów URL (trasy) dla produktów, kategorii, stron CMS itp. w sekcji **Parametry sklepu > SEO i URL**. Moduł "Pretty / Clean URLs PRO" przejmuje teraz tę odpowiedzialność, umożliwiając konfigurację tych ustawień bezpośrednio ze swojej własnej strony konfiguracji.

Moduł zapewnia, że trasy są ustawione tak, aby usuwać `{id}` z adresów URL, co jest niezbędne dla prawdziwie czystych adresów URL. Jeśli z jakiegoś powodu okaże się, że trasy w **Parametry sklepu > SEO i URL** nadal zawierają `{id}` po zainstalowaniu i skonfigurowaniu modułu, może to wskazywać na problem z nadpisaniami modułu (patrz Sekcja 6 w celu rozwiązania problemów).

Dla odniesienia, oto zalecane struktury tras, które moduł ma na celu zaimplementować:

| Typ trasy           | Domyślna wartość PrestaShop (Przykład) | Pożądana wartość modułu (Czysta) |
| :------------------ | :--------------------------------- | :----------------------------- |
| Trasa do produktu   | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (lub `{rewrite}.html`) |
| Trasa do kategorii  | `{id}-{rewrite}`                   | `{parent_categories:/}{rewrite}/` (lub `{rewrite}/`) |
| Trasa do dostawcy   | `{id}__{rewrite}`                  | `supplier/{rewrite}/`          |
| Trasa do producenta | `{id}_{rewrite}`                   | `manufacturer/{rewrite}/`      |
| Trasa do strony CMS | `content/{id}-{rewrite}`           | `info/{rewrite}.html`          |
| Trasa do strony kategorii CMS | `content/category/{id}-{rewrite}` | `info/{rewrite}`               |

:::tip Środowisko Multistore
Jeśli prowadzisz PrestaShop Multistore, pamiętaj, aby zweryfikować i, jeśli to konieczne, dostosować ustawienia schematu URL dla każdego indywidualnego sklepu. Możesz wybrać sklep, który chcesz skonfigurować z menu kontekstowego sklepu w Panelu administracyjnym.
:::

### 2.4 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz ładne adresy URL | TAK | Aktywuje/dezaktywuje podstawową funkcjonalność modułu. |
| Konfiguracja modułu | Usuń identyfikatory z adresów URL | TAK | Usuwa numeryczne identyfikatory z adresów URL (np. `123-produkt` staje się `produkt`). |
| Konfiguracja modułu | Automatyczne przekierowanie 301 | TAK | Przekierowuje stare adresy URL oparte na identyfikatorach do nowych, czystych adresów URL, zachowując SEO. |
| Konfiguracja modułu | Wymuś ukośnik na końcu | TAK | Zapewnia, że wszystkie adresy URL kończą się `/` dla spójności i SEO. |
| Konfiguracja modułu | Usuń rozszerzenie .html | TAK | Usuwa `.html` z adresów URL stron produktów/CMS dla czystszych linków. |
| Katalog > Produkty (Edycja) | Pole Przyjazny URL | Automatycznie generowane | Moduł wpływa na automatyczne generowanie czystych adresów URL dla produktów. |
| Katalog > Kategorie (Edycja) | Pole Przyjazny URL | Automatycznie generowane | Moduł wpływa na automatyczne generowanie czystych adresów URL dla kategorii. |
| Wygląd > Strony (Edycja) | Pole Przyjazny URL | Automatycznie generowane | Moduł wpływa na automatyczne generowanie czystych adresów URL dla stron CMS. |
| Parametry sklepu > SEO i URL | Przyjazny URL | TAK | **KRYTYCZNE:** Musi być włączone, aby moduł działał. |

## 3. Rozwiązywanie problemów dla sprzedawcy i często zadawane pytania (FAQ)

**P1: Po instalacji moje adresy URL nadal wyglądają tak samo lub otrzymuję błędy 404.**

-   **Odp.:** Po pierwsze, upewnij się, że opcja „Włącz ładne adresy URL” jest ustawiona na TAK w konfiguracji modułu.
-   Po drugie, przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
-   Po trzecie, upewnij się, że natywna opcja „Przyjazny URL” PrestaShop jest włączona w **Parametry sklepu > SEO i URL**. Ten moduł rozszerza natywną funkcjonalność przyjaznych adresów URL PrestaShop, nie zastępuje jej całkowicie.
-   Na koniec sprawdź plik `.htaccess` swojego serwera (jeśli używasz Apache) lub konfigurację Nginx. Moduł opiera się na przepisywaniu adresów URL po stronie serwera (mod_rewrite dla Apache), aby działać poprawnie. Jeśli nie masz pewności, skontaktuj się ze swoim dostawcą hostingu.

**P2: Mój niestandardowy motyw ma dziwne problemy z wyświetlaniem po włączeniu modułu.**

-   **Odp.:** Ten moduł wpływa głównie na generowanie i przekierowywanie adresów URL, a nie na wyświetlanie wizualne. Jest mało prawdopodobne, aby bezpośrednio powodował problemy z wyświetlaniem motywu. Jeśli jednak wyczyściłeś pamięć podręczną, CSS lub JS Twojego motywu mogą wymagać ponownego załadowania. Spróbuj wyczyścić pamięć podręczną przeglądarki. Jeśli problem nadal występuje, może to być konflikt z innym modułem lub niestandardową modyfikacją motywu. Tymczasowo wyłącz „Pretty / Clean URLs PRO”, aby sprawdzić, czy problem zostanie rozwiązany. Jeśli tak, skontaktuj się z pomocą techniczną MyPresta.eu.

**P3: Czy ten moduł będzie działał z moimi istniejącymi niestandardowymi adresami URL lub przekierowaniami?**

-   **Odp.:** Moduł koncentruje się na generowaniu czystych adresów URL dla podstawowych encji PrestaShop (produktów, kategorii, CMS itp.). Jeśli ręcznie utworzyłeś niestandardowe przekierowania lub specyficzne przyjazne adresy URL poza standardowym systemem PrestaShop, automatyczne przekierowanie 301 modułu będzie priorytetowo traktować własne wygenerowane czyste adresy URL. Ogólnie najlepiej jest pozwolić modułowi zarządzać wszystkimi adresami URL podstawowych encji dla spójności. Jeśli masz bardzo specyficzne niestandardowe przekierowania, być może będziesz musiał przetestować, jak one współdziałają.

**P4: Zmieniłem nazwę produktu, ale adres URL nie zaktualizował się automatycznie.**

-   **Odp.:** Kiedy zmieniasz nazwę produktu, PrestaShop zazwyczaj sugeruje nowy przyjazny adres URL. Musisz wyraźnie zapisać produkt, aby zmiany weszły w życie i aby moduł przetworzył nowy adres URL. Jeśli pole przyjaznego adresu URL nie aktualizuje się automatycznie, być może będziesz musiał ręcznie kliknąć „Generuj URL” obok pola przyjaznego adresu URL na stronie edycji produktu, a następnie zapisać produkt. Moduł zapewni wtedy, że ten nowy adres URL jest czysty i obsłuży przekierowanie ze starego.

**P5: Czy ten moduł wpływa na moje wielojęzyczne adresy URL?**

-   **Odp.:** Nie, on je ulepsza! Moduł współpracuje z funkcjami wielojęzycznymi PrestaShop. Wygeneruje czyste adresy URL dla każdego języka, respektując kod języka w adresie URL (np. `/en/my-product` i `/fr/mon-produit`). Upewnij się, że nazwy produktów, kategorii i stron CMS są przetłumaczone dla każdego języka, aby uzyskać najlepsze przyjazne adresy URL.

**P6: Widzę komunikat o błędzie "keyword {id} is required for route (...)" podczas próby zapisania schematów URL.**

-   **Odp.:** Ten błąd zazwyczaj występuje, jeśli nadpisania modułu (kluczowa część jego funkcjonalności) nie są poprawnie zainstalowane lub są wyłączone w Twoim sklepie PrestaShop. Moduł opiera się na tych nadpisaniach, aby modyfikować domyślne zachowanie routingu URL PrestaShop, umożliwiając mu usuwanie `{id}` z tras.
    -   **Rozwiązanie:**
        1.  **Sprawdź nadpisania:** Upewnij się, że system nadpisań PrestaShop jest włączony. Zazwyczaj to ustawienie można znaleźć w **Zaawansowane > Wydajność**. Poszukaj opcji związanej z „Wyłącz moduły inne niż PrestaShop” lub „Wyłącz nadpisania” i upewnij się, że jest ustawiona na „Nie”.
        2.  **Ponowna instalacja modułu:** Czasami ponowna instalacja modułu może rozwiązać problemy z nadpisaniami. Odinstaluj moduł, wyczyść pamięć podręczną PrestaShop, a następnie zainstaluj go ponownie.
        3.  **Ręczne sprawdzenie nadpisań:** Sprawdź, czy pliki nadpisań modułu są obecne w katalogach `override/classes/` i `override/controllers/` (np. `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). Jeśli ich brakuje, oznacza to problem z instalacją.
    -   Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Pretty / Clean URLs PRO” działa poprzez nadpisywanie podstawowych klas PrestaShop, w szczególności `Dispatcher` i `Link`, w celu modyfikacji sposobu generowania i parsowania adresów URL. Przechwytuje domyślną logikę routingu i generowania adresów URL, aby usuwać identyfikatory i rozszerzenia na podstawie ustawień konfiguracji. Moduł wykorzystuje system nadpisywania PrestaShop (`/override/`) do wstrzykiwania swojej niestandardowej logiki bez bezpośredniej modyfikacji podstawowych plików, zapewniając kompatybilność z aktualizacjami. Zawiera również nadpisanie kontrolera administracyjnego dla `AdminProductsController`, aby zapewnić, że generowanie przyjaznych adresów URL w panelu administracyjnym jest zgodne z ustawieniami modułu.

### 4.2 Kontrolery (`controllers/`)

Moduł wykorzystuje głównie nadpisania kontrolerów front-office do modyfikacji generowania i routingu adresów URL.

-   **Kontrolery Front-Office**:

    -   `purls/override/controllers/front/CartController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CartController` (nadpisuje `CartControllerCore`)
        -   **Odpowiedzialność**: Modyfikuje generowanie adresów URL dla linków związanych z koszykiem, aby zapewnić, że są one czyste i wolne od identyfikatorów, tam gdzie ma to zastosowanie.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CmsController` (nadpisuje `CmsControllerCore`)
        -   **Odpowiedzialność**: Modyfikuje generowanie adresów URL dla stron CMS, usuwając identyfikatory i rozszerzenia `.html` zgodnie z konfiguracją.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CategoryController` (nadpisuje `CategoryControllerCore`)
        -   **Odpowiedzialność**: Modyfikuje generowanie adresów URL dla stron kategorii, usuwając identyfikatory i zapewniając czyste adresy URL.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Nie jest to bezpośredni kontroler, prawdopodobnie pusty plik lub placeholder. Autoloader PrestaShop może pobierać inne pliki z tego katalogu.
        -   **Odpowiedzialność**: Brak bezpośredniej odpowiedzialności; służy jako znacznik katalogu.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `ManufacturerController` (nadpisuje `ManufacturerControllerCore`)
        -   **Odpowiedzialność**: Modyfikuje generowanie adresów URL dla stron producentów, usuwając identyfikatory i zapewniając czyste adresy URL.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `SupplierController` (nadpisuje `SupplierControllerCore`)
        -   **Odpowiedzialność**: Modyfikuje generowanie adresów URL dla stron dostawców, usuwając identyfikatory i zapewniając czyste adresy URL.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `ProductController` (nadpisuje `ProductControllerCore`)
        -   **Odpowiedzialność**: Modyfikuje generowanie adresów URL dla stron produktów, usuwając identyfikatory i rozszerzenia `.html` zgodnie z konfiguracją.
-   **Kontrolery administracyjne Back-Office**:

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminProductsController` (nadpisuje `AdminProductsControllerCore`)
        -   **Odpowiedzialność**: Integruje się z interfejsem zarządzania produktami, aby zapewnić, że gdy przyjazne adresy URL są generowane lub aktualizowane w panelu administracyjnym, są one zgodne z ustawieniami modułu (np. usuwanie identyfikatorów). Prawdopodobnie modyfikuje metodę `generateFriendlyUrl` lub podobną logikę.

### 4.3 Klasy podstawowe i modele (`classes/`)

Podstawowa logika modułu znajduje się w jego nadpisaniach klas, które są fundamentalne dla sposobu, w jaki PrestaShop obsługuje adresy URL.

-   `purls/override/classes/Dispatcher.php`
    -   **Nazwa klasy i klasa nadrzędna**: `Dispatcher` (nadpisuje `DispatcherCore`)
    -   **Interakcja z bazą danych**: Brak bezpośredniej, ale współdziała z `ps_configuration` w celu uzyskania ustawień modułu.
    -   **Kluczowe metody publiczne i logika biznesowa**: Ta klasa jest odpowiedzialna za routing przychodzących żądań do właściwego kontrolera i za generowanie adresów URL. Nadpisanie prawdopodobnie modyfikuje metody takie jak `getFriendlyUrl` lub `createUrl` w celu usunięcia identyfikatorów i rozszerzeń oraz obsługi logiki przekierowania 301 dla starych adresów URL. Jest to centralny punkt parsowania i generowania adresów URL.
-   `purls/override/classes/Link.php`
    -   **Nazwa klasy i klasa nadrzędna**: `Link` (nadpisuje `LinkCore`)
    -   **Interakcja z bazą danych**: Brak bezpośredniej, ale współdziała z `ps_configuration` w celu uzyskania ustawień modułu.
    -   **Kluczowe metody publiczne i logika biznesowa**: Klasa `Link` jest używana w całym PrestaShop do konstruowania adresów URL dla różnych encji (produktów, kategorii, CMS itp.). Nadpisanie w tym module modyfikuje metody takie jak `getProductLink`, `getCategoryLink`, `getCMSLink` itp., aby generować adresy URL, które są czyste, wolne od identyfikatorów i bez rozszerzeń `.html` zgodnie z konfiguracją modułu. Działa w połączeniu z nadpisaniem `Dispatcher`, aby zapewnić spójne generowanie adresów URL.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Zakres**: Panel administracyjny (prawdopodobnie na stronach edycji produktów/kategorii/CMS).
    -   **Szczegóły**: Ten skrypt prawdopodobnie zawiera logikę po stronie klienta, aby usprawnić proces generowania przyjaznych adresów URL w Panelu administracyjnym PrestaShop. Może:
        -   Nasłuchiwać zmian w nazwach produktów/kategorii/CMS i automatycznie aktualizować pole „Przyjazny URL” na podstawie ustawień modułu.
        -   Zapewniać informacje zwrotne w czasie rzeczywistym lub walidację dla wygenerowanych adresów URL.
        -   Potencjalnie współdziałać z wywołaniami AJAX do serwera w celu uzyskania sugerowanych przyjaznych adresów URL.
        -   Zapewnić, że przycisk „Generuj URL” (jeśli jest obecny) wyzwala logikę modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

W archiwum modułu nie znaleziono niestandardowych plików CSS, co wskazuje, że moduł nie wprowadza nowych elementów wizualnych wymagających specyficznego stylu. Opiera się na domyślnym stylu Panelu administracyjnego PrestaShop dla swojej strony konfiguracji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `purls/views/purls.tpl`
        -   **Zakres**: Panel administracyjny, strona konfiguracji modułu.
        -   **Szczegóły**: Ten szablon renderuje główny formularz konfiguracji modułu „Pretty / Clean URLs PRO”. Zawiera strukturę HTML dla wszystkich ustawień opisanych w Sekcji 4.1, w tym przełączniki do włączania/wyłączania funkcji oraz przycisk „Zapisz”. Wykorzystuje standardowe pomocniki formularzy i stylizację PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli PrestaShop `ps_configuration`. Klucze konfiguracyjne zazwyczaj będą miały wzorzec taki jak `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT` itp.
-   **Tabela zarejestrowanych hooków**:
    Moduł działa głównie poprzez nadpisania klas, a nie bezpośrednią rejestrację hooków dla swojej podstawowej funkcjonalności. Może jednak niejawnie współdziałać z hookami, które wyzwalają generowanie lub przekierowywanie adresów URL.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Przy każdym ładowaniu strony we front office, w sekcji `<head>`. | Chociaż nie rejestruje bezpośrednio elementu wizualnego, nadpisania `Dispatcher` i `Link` modułu są aktywne podczas renderowania strony, wpływając na wszelkie adresy URL generowane w nagłówku (np. kanoniczne adresy URL, przełączniki języka). |
| `actionDispatcherBefore` | Przed przetworzeniem żądania przez dispatcher. | Nadpisanie `Dispatcher` jest aktywne na tym etapie, umożliwiając modułowi przechwytywanie i modyfikowanie logiki parsowania i routingu adresów URL, zanim PrestaShop określi, który kontroler ma załadować. Jest to kluczowe dla obsługi przekierowań 301 ze starych adresów URL. |
| `actionDispatcherAfter` | Po przetworzeniu żądania przez dispatcher. | Nadpisanie `Dispatcher` może być również aktywne tutaj, potencjalnie do post-processingu lub logowania związanego z obsługą adresów URL. |
| `actionProductUpdate` / `actionProductAdd` | Po zaktualizowaniu lub dodaniu produktu w Panelu administracyjnym. | Nadpisanie `AdminProductsController` zapewnia, że po zapisaniu produktu jego przyjazny adres URL jest generowany zgodnie z ustawieniami modułu. Jest to niejawna interakcja, a nie bezpośrednia rejestracja hooka przez sam moduł. |
| `actionCategoryUpdate` / `actionCategoryAdd` | Po zaktualizowaniu lub dodaniu kategorii w Panelu administracyjnym. | Podobnie jak w przypadku produktów, moduł zapewnia czyste adresy URL dla kategorii. |
| `actionCmsUpdate` / `actionCmsAdd` | Po zaktualizowaniu lub dodaniu strony CMS w Panelu administracyjnym. | Podobnie jak w przypadku produktów, moduł zapewnia czyste adresy URL dla stron CMS. |

## 5. Oficjalne wsparcie i zasoby

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich zapytań dotyczących modułu „Pretty / Clean URLs PRO”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
"""
