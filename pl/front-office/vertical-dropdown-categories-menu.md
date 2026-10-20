---
title: "Pionowe rozwijane menu kategorii - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Pionowe rozwijane menu kategorii” od MyPresta.eu."
sidebar:
  label: "Pionowe rozwijane menu kategorii - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Vertical dropdown categories menu na MyPresta.eu](https://mypresta.eu/modules/front-office-features/vertical-dropdown-categories-menu.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/vertical-dropdown-categories-menu/)
>
> ---


# Pionowe rozwijane menu kategorii

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Pionowe rozwijane menu kategorii” w Menedżerze modułów. Spowoduje to przejście do jego głównego ekranu konfiguracji.

Strona konfiguracji modułu zawiera standardowe ustawienia do kontrolowania jego zachowania i wyglądu.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera ogólne ustawienia modułu, takie jak włączanie/wyłączanie, wybór miejsca jego wyświetlania lub podstawowe opcje wyświetlania. Chociaż konkretne nazwane ustawienia nie są szczegółowo opisane w dokumentacji, typowe opcje dla modułu tego typu obejmują:

    -   **Włącz/Wyłącz moduł**: Prosty przełącznik do włączania lub wyłączania modułu bez jego odinstalowywania.
    -   **Wyświetl kategorię główną**: Wybierz, czy w menu ma być wyświetlana główna kategoria „Strona główna” lub „Główna”.
    -   **Maksymalna głębokość**: Ogranicz, ile poziomów podkategorii jest wyświetlanych w rozwijanym menu.
    -   **Wybór zaczepu**: Wybierz, do których zaczepów wyświetlania moduł ma się dołączyć (np. `displayLeftColumn`, `displayRightColumn`).
    -   **Ustawienia pamięci podręcznej**: Opcje włączania lub wyłączania pamięci podręcznej dla danych wyjściowych modułu w celu poprawy wydajności.
-   **Wpływ zmiany tego ustawienia:**

    -   *Po włączeniu:* Moduł będzie aktywny i wyświetli pionowe menu kategorii w Twoim panelu front-office zgodnie z innymi ustawieniami.
    -   *Po wyłączeniu:* Moduł nie pojawi się w Twoim sklepie, ale jego konfiguracja zostanie zapisana.
    -   *Wybór zaczepu (np. `displayLeftColumn`):* Blok menu pionowego pojawi się w lewej kolumnie Twojego sklepu.
    -   *Ograniczenie głębokości:* Wyświetlane będą tylko kategorie do określonego poziomu, upraszczając menu dla klientów.
-   **Zalecana wartość:**

    -   **Włącz moduł**: TAK
    -   **Wyświetl kategorię główną**: NIE (zazwyczaj, aby rozpocząć bezpośrednio od głównych kategorii produktów)
    -   **Maksymalna głębokość**: 3 (dobra równowaga dla większości sklepów, zapobiegająca zbyt skomplikowanym menu)
    -   **Wybór zaczepu**: `displayLeftColumn` lub `displayRightColumn` (w zależności od preferencji układu Twojego motywu).
-   **Scenariusz sprzedawcy / przykład:**

    -   *Scenariusz 1 (Upraszczanie nawigacji):* Masz bardzo głęboką strukturę kategorii (np. 5-6 poziomów). Możesz ustawić „Maksymalną głębokość” na 3, aby klienci nie byli przytłoczeni zbyt wieloma opcjami, prowadząc ich najpierw przez wybory najwyższego poziomu.
    -   *Scenariusz 2 (Optymalizacja wydajności):* Jeśli Twój sklep doświadcza dużego ruchu, włączenie pamięci podręcznej dla danych wyjściowych modułu może znacznie przyspieszyć czas ładowania strony, ponieważ menu nie musi być przebudowywane dla każdego odwiedzającego.
    -   *Scenariusz 3 (Dostosowanie układu):* Twój motyw wygląda lepiej z nawigacją po prawej stronie. W ustawieniach zaczepów wybierzesz `displayRightColumn`, aby odpowiednio przesunąć blok menu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Włącz/Wyłącz moduł | Włączony | Kontroluje, czy moduł jest aktywny w Twoim sklepie. |
| Strona konfiguracji modułu | Wyświetl kategorię główną | Nie | Określa, czy wyświetlana jest kategoria najwyższego poziomu „Strona główna”. |
| Strona konfiguracji modułu | Maksymalna głębokość | 3 | Ogranicza liczbę wyświetlanych poziomów podkategorii. |
| Strona konfiguracji modułu | Wybór zaczepu | `displayLeftColumn` | Określa, gdzie pojawia się blok menu (np. lewa lub prawa kolumna). |
| Strona konfiguracji modułu | Buforowanie | Włączone | Poprawia wydajność poprzez przechowywanie wygenerowanego kodu HTML menu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Menu nie wyświetla się w moim sklepie po instalacji.**
**O1:**

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Pionowe rozwijane menu kategorii” jest zainstalowany i włączony.
2.  **Zweryfikuj przypisanie zaczepu:** W konfiguracji modułu upewnij się, że jest on przypisany do aktywnego zaczepu (np. `displayLeftColumn`, `displayRightColumn`). Niektóre motywy mogą nie wyświetlać wszystkich zaczepów domyślnie, lub może być konieczne dostosowanie ustawień układu motywu.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”). Czasami stare treści z pamięci podręcznej uniemożliwiają wyświetlanie nowych modułów.
4.  **Kompatybilność z motywem:** Jeśli używasz mocno dostosowanego motywu, może on nadpisywać domyślne renderowanie zaczepów PrestaShop. Skontaktuj się z twórcą motywu lub ekspertem PrestaShop.

**P2: Efekt rozwijania nie działa lub wygląda na uszkodzony.**
**O2:**

1.  **Konflikty motywu:** Inny moduł lub niestandardowy JavaScript/CSS Twojego motywu może kolidować ze stylizacją lub funkcjonalnością modułu.
2.  **Wyczyść pamięć podręczną:** Zawsze próbuj wyczyścić pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki.
3.  **Sprawdź narzędziami przeglądarki:** Użyj narzędzi deweloperskich przeglądarki (F12), aby sprawdzić konsolę pod kątem błędów JavaScript lub konfliktów CSS. Szukaj czerwonych komunikatów o błędach.
4.  **Ponowna instalacja modułu:** Spróbuj odinstalować i ponownie zainstalować moduł (po wcześniejszym wykonaniu kopii zapasowej ustawień, jeśli to możliwe).

**P3: Jak zmienić kolory lub czcionki menu?**
**O3:** Moduł zawiera własny plik `blockcategories.css` do stylizacji.

1.  **Podstawowa personalizacja:** W przypadku drobnych zmian, często można nadpisać te style w niestandardowym pliku CSS motywu (np. `themes/yourtheme/assets/css/custom.css`). Jest to najbezpieczniejszy sposób wprowadzania zmian bez modyfikowania podstawowych plików modułu.
2.  **Zaawansowana personalizacja:** W przypadku bardziej rozległych zmian, może być konieczne bezpośrednie edytowanie pliku `blockcategories.css` w katalogu `views/css/` modułu. **Należy jednak pamiętać, że te zmiany zostaną utracone podczas aktualizacji modułu.** Zawsze lepiej jest używać nadpisywania motywu.
3.  **Dostosowywanie motywu PrestaShop:** Niektóre motywy oferują „Dostosowywanie motywu” lub „Konfigurator na żywo”, który pozwala na podstawowe zmiany stylizacji bez dotykania kodu. Sprawdź, czy Twój motyw ma tę funkcję.

**P4: Moje kategorie nie wyświetlają się w menu.**
**O4:**

1.  **Status kategorii:** Upewnij się, że Twoje kategorie są aktywne i widoczne w Panelu administracyjnym PrestaShop (**Katalog > Kategorie**).
2.  **Ustawienie kategorii głównej:** Sprawdź konfigurację modułu, aby zobaczyć, czy „Wyświetl kategorię główną” jest włączone czy wyłączone. Jeśli wyłączone, a Twoje kategorie są bezpośrednimi dziećmi kategorii głównej, mogą się nie pojawić.
3.  **Uprawnienia:** Upewnij się, że kategorie mają odpowiednie uprawnienia grup, jeśli używasz grup klientów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Pionowe rozwijane menu kategorii” (`verticalblockcategories`) to standardowy moduł PrestaShop zaprojektowany do wyświetlania dynamicznego bloku nawigacji kategorii. Wykorzystuje on głównie system zaczepów PrestaShop do renderowania swojej zawartości w różnych miejscach front-office. Logika modułu zawarta jest w jego głównym pliku PHP, który obsługuje instalację, deinstalację, rejestrację zaczepów i konfigurację. Prezentacja wizualna jest zarządzana za pomocą szablonów Smarty i dedykowanego pliku CSS. Nie wprowadza niestandardowych kontrolerów ani złożonych ObjectModels, skupiając się na efektywnym renderowaniu istniejących danych kategorii.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest obsługiwana w głównym pliku modułu (`index.php`) i renderowana za pośrednictwem zaczepów.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowe klasy PrestaShop `Category` i `Tools` do pobierania i przetwarzania danych kategorii.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Efekt rozwijania jest zazwyczaj osiągany wyłącznie za pomocą CSS lub opiera się na istniejących bibliotekach jQuery/JavaScript już załadowanych przez PrestaShop lub motyw.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`verticalblockcategories/blockcategories.css`**
    -   **Zakres**: Stylizacja dla klienta w panelu front-office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Ten arkusz stylów odpowiada za układ wizualny, wygląd i animację rozwijania pionowego menu kategorii. Celuje w elementy w wygenerowanej strukturze HTML modułu, takie jak `div#categories_block_left`, `ul.tree`, `li.last`, `a.selected` i `ul.tree li ul`.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie**:
        -   `#categories_block_left` (lub podobny ID/klasa dla głównego kontenera bloku)
        -   `.block_content`
        -   `ul.tree` (dla głównej listy kategorii)
        -   `ul.tree li` (dla poszczególnych elementów kategorii)
        -   `ul.tree li a` (dla linków kategorii)
        -   `ul.tree li ul` (dla rozwijanych podkategorii)
        -   `ul.tree li ul li` (dla poszczególnych elementów podkategorii)
        -   `.selected` (dla aktualnie aktywnej kategorii)
        -   Klasy związane z efektami najechania i przejściami dla rozwijania.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony zaczepów (`views/templates/hook/`)**:
    -   **`verticalblockcategories/blockcategories.tpl`**: Jest to główny plik szablonu renderowany przez moduł po zaczepieniu. Zazwyczaj zawiera ogólną strukturę bloku kategorii, w tym tytuł i główną listę nieuporządkowaną (`<ul>`), która będzie zawierać drzewo kategorii. Prawdopodobnie rekurencyjnie zawiera `category-tree-branch.tpl` w celu zbudowania pełnego menu.
        -   **Zaczepiony w**: `displayLeftColumn`, `displayRightColumn`, `displayHeader`, `displayFooter`, `displayProductExtraContent` (lub inne zaczepy kolumn/zawartości).
        -   **Wyjścia**: Główny blok HTML dla pionowego menu kategorii.
    -   **`verticalblockcategories/category-tree-branch.tpl`**: Ten szablon jest przeznaczony do rekurencyjnego renderowania poszczególnych gałęzi kategorii (kategorii i ich podkategorii). Obsługuje wyświetlanie pojedynczego elementu kategorii i, jeśli ta kategoria ma dzieci, rekurencyjnie wywołuje sam siebie, aby renderować te dzieci jako zagnieżdżoną listę, tworząc strukturę drzewa.
        -   **Dołączony przez**: `blockcategories.tpl` (i potencjalnie sam siebie).
        -   **Wyjścia**: Element `<li>` dla kategorii, potencjalnie zawierający zagnieżdżony `<ul>` dla jej podkategorii.

### 4.7 Schemat bazy danych i mapa zaczepów

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się całkowicie na podstawowych tabelach PrestaShop `ps_category`, `ps_category_lang` i `ps_category_product` dla danych kategorii. Ustawienia konfiguracji są przechowywane w `ps_configuration` przy użyciu kluczy z prefiksem `VERTICALBLOCKCATEGORIES_`.
-   **Tabela zarejestrowanych zaczepów**:

    | Nazwa zaczepu | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayHeader` | W sekcji `<head>` kodu HTML. | Potencjalnie używany do ładowania zasobów CSS/JS, chociaż dla tego modułu CSS jest zazwyczaj rejestrowany za pośrednictwem `install()` lub samego `hookDisplayHeader`. |
    | `displayLeftColumn` | Renderuje zawartość w lewej kolumnie sklepu. | Główny zaczep do wyświetlania bloku pionowego menu kategorii. |
    | `displayRightColumn` | Renderuje zawartość w prawej kolumnie sklepu. | Alternatywny zaczep do wyświetlania bloku pionowego menu kategorii. |
    | `displayHome` | Renderuje zawartość na stronie głównej. | Może być używany do wyświetlania menu na stronie głównej, choć rzadziej dla menu pionowego. |
    | `displayFooter` | Renderuje zawartość w sekcji stopki. | Mniej powszechne dla głównego menu nawigacyjnego, ale możliwe dla dodatkowych linków. |
    | `displayProductExtraContent` | Renderuje zawartość na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Może być używany do wyświetlania powiązanych kategorii dla nawigacji po produktach. |
    | `actionObjectCategoryAddAfter` | Po dodaniu kategorii. | Potencjalnie używany do czyszczenia pamięci podręcznej modułu, jeśli struktura kategorii ulegnie zmianie. |
    | `actionObjectCategoryUpdateAfter` | Po zaktualizowaniu kategorii. | Potencjalnie używany do czyszczenia pamięci podręcznej modułu, jeśli struktura kategorii ulegnie zmianie. |
    | `actionObjectCategoryDeleteAfter` | Po usunięciu kategorii. | Potencjalnie używany do czyszczenia pamięci podręcznej modułu, jeśli struktura kategorii ulegnie zmianie. |
    | `actionShopDataDuplication` | Gdy sklep jest duplikowany (w kontekście wielu sklepów). | Zapewnia skopiowanie konfiguracji modułu do nowego sklepu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Pionowe rozwijane menu kategorii”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
