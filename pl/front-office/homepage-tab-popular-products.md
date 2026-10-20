---
title: "Zakładka popularne produkty na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zakładka popularne produkty na stronie głównej” od MyPresta.eu."
sidebar:
  label: "Zakładka popularne produkty na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage tab popular products na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-popular-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-tab-popular-products/)
>
> ---


# Zakładka popularne produkty na stronie głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij przycisk „Konfiguruj” obok modułu „Zakładka popularne produkty na stronie głównej” w Menedżerze modułów. Spowoduje to przejście do jego głównego ekranu konfiguracji.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ten moduł koncentruje się głównie na wyświetlaniu popularnych produktów. Ekran konfiguracji tego modułu jest dość prosty, często zawiera standardowe ustawienia powiadomień o aktualizacjach MyPresta.eu. Podstawowa funkcjonalność wyświetlania „popularnych produktów” jest zazwyczaj obsługiwana automatycznie przez wewnętrzną logikę PrestaShop do identyfikacji popularnych pozycji (np. na podstawie sprzedaży, wyświetleń lub kombinacji).
-   **Efekt zmiany tego ustawienia:**
    -   **`mypresta_updates` (Włącz/Wyłącz powiadomienia o aktualizacjach MyPresta.eu):**
        -   *Gdy włączone:* Będziesz otrzymywać powiadomienia w panelu administracyjnym PrestaShop, gdy dostępne będą nowe wersje lub ważne aktualizacje dla modułów MyPresta.eu (w tym tego). Pomaga to utrzymać moduły bezpieczne i aktualne z najnowszymi funkcjami i poprawkami błędów.
        -   *Gdy wyłączone:* Nie będziesz otrzymywać tych powiadomień. Musiałbyś ręcznie sprawdzać swoje konto MyPresta.eu pod kątem aktualizacji.
    -   **`update_` i `updatev_` (Wewnętrzne parametry sprawdzania aktualizacji):** Są to zazwyczaj wewnętrzne ustawienia używane przez moduły MyPresta.eu do zarządzania i śledzenia sprawdzania aktualizacji. Zazwyczaj nie są przeznaczone do bezpośredniej interakcji sprzedawcy.
-   **Zalecana wartość:**
    -   Dla `mypresta_updates`: **TAK** (Włączone). Utrzymywanie tego włączonego zapewnia, że zawsze będziesz informowany o krytycznych aktualizacjach, poprawiając bezpieczeństwo i wydajność Twojego sklepu.
    -   Dla `update_` i `updatev_`: Pozostaw jako domyślne. Są to ustawienia wewnętrzne i nie powinny być zmieniane.
-   **Scenariusz sprzedawcy / przykład:**
    -   Chcesz mieć pewność, że Twój sklep zawsze działa na najnowszych, najbezpieczniejszych wersjach modułów MyPresta.eu. Włączając powiadomienia o aktualizacjach, zobaczysz wyraźne ostrzeżenie w panelu administracyjnym PrestaShop, gdy tylko zostanie wydana aktualizacja dla „Zakładka popularne produkty na stronie głównej” (lub dowolnego innego modułu MyPresta.eu). Pozwala to na szybkie pobranie i zainstalowanie nowej wersji, korzystając z ulepszeń bez konieczności ciągłego ręcznego sprawdzania.

#### Ważna uwaga dotycząca logiki „Popularnych produktów”:

Ten moduł wykorzystuje istniejące mechanizmy PrestaShop do określania, co stanowi „popularny produkt”. Zazwyczaj PrestaShop identyfikuje popularne produkty na podstawie danych sprzedażowych (produkty z największą liczbą zamówień) lub wyświetleń. Sam moduł zazwyczaj nie oferuje konkretnych ustawień do definiowania „popularności” (np. „pokaż produkty sprzedane w ciągu ostatnich 30 dni” lub „produkty z X wyświetleniami”). Opiera się na podstawowej funkcjonalności PrestaShop w tym zakresie. Jeśli chcesz wpłynąć na to, które produkty pojawiają się jako „popularne”, zazwyczaj musiałbyś zwiększyć ich sprzedaż lub widoczność poprzez inne działania marketingowe.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Powiadomienia o aktualizacjach MyPresta.eu | Włączone (TAK) | Otrzymuj alerty o aktualizacjach modułów, zapewniając bezpieczeństwo i nowe funkcje. |
| Strona konfiguracji modułu | `update_` | Domyślne | Wewnętrzne ustawienie do śledzenia aktualizacji. Pozostaw bez zmian. |
| Strona konfiguracji modułu | `updatev_` | Domyślne | Wewnętrzne ustawienie do śledzenia aktualizacji. Pozostaw bez zmian. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zakładka „Popularne produkty” nie wyświetla się na mojej stronie głównej.**
O1:

-   **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Zakładka popularne produkty na stronie głównej” jest zainstalowany i włączony.
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop uniemożliwia wyświetlanie nowej zawartości. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”, jeśli jest dostępna).
-   **Kompatybilność z szablonem:** Chociaż moduł jest przeznaczony dla PrestaShop 1.7.x, 8.x i 9.x, niektóre wysoce spersonalizowane szablony mogą wymagać drobnych korekt. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, skontaktuj się z twórcą szablonu lub wsparciem MyPresta.eu.
-   **Sprawdzenie hooka:** Upewnij się, że hook `displayHome` jest aktywny i renderowany przez Twój szablon.

**P2: Produkty wyświetlane w zakładce „Popularne produkty” nie wydają mi się „popularne”.**
O2:

-   **Definicja PrestaShop:** Moduł opiera się na wewnętrznej logice PrestaShop do identyfikacji popularnych produktów, która zazwyczaj bazuje na wolumenie sprzedaży lub wyświetleniach produktów. Jeśli Twój sklep jest nowy lub ma niską sprzedaż, lista „popularnych” może nie być tak dynamiczna.
-   **Odświeżanie danych:** Upewnij się, że Twój sklep ma aktualne dane sprzedażowe. „Popularność” jest obliczana w czasie.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop, jak opisano w Q1.

**P3: Czy mogę zmienić tytuł zakładki (np. z „Popularne produkty” na „Nasze bestsellery”)?**
O3:

-   Ten moduł zazwyczaj używa domyślnego tytułu. Aby go zmienić, zazwyczaj musiałbyś edytować pliki tłumaczeń modułu lub, w niektórych przypadkach, bezpośrednio zmodyfikować plik szablonu.
    -   Przejdź do **Lokalizacja > Tłumaczenia**.
    -   Wybierz „Tłumaczenia zainstalowanych modułów”, swój szablon i swój język.
    -   Znajdź moduł „Zakładka popularne produkty na stronie głównej” i poszukaj ciągu tytułu zakładki.
    -   Jeśli nie można go przetłumaczyć w ten sposób, może to wymagać niewielkiej zmiany kodu w `homepagetabs.tpl` (patrz Sekcja 7).

**P4: Stylizacja produktów w zakładce nie pasuje do mojego szablonu.**
O4:

-   Moduł używa własnego CSS (`homepagetabs.css`). CSS Twojego szablonu może nadpisywać niektóre style, lub style modułu mogą kolidować.
-   **Niestandardowy CSS:** Najlepszym podejściem jest dodanie niestandardowego CSS do pliku `custom.css` Twojego szablonu (lub równoważnego), aby nadpisać style modułu i idealnie dopasować je do Twojego szablonu. Użyj narzędzi deweloperskich przeglądarki, aby zbadać elementy i zidentyfikować selektory CSS używane przez moduł.

**P5: Jak przetłumaczyć tytuł zakładki lub inne teksty modułu na różne języki?**
O5:

-   Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, a następnie wybierz swój szablon i język, na który chcesz przetłumaczyć.
-   Znajdź moduł „Zakładka popularne produkty na stronie głównej” na liście i powinieneś być w stanie edytować powiązane z nim ciągi tekstowe.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Zakładka popularne produkty na stronie głównej”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `Homepage tab popular products` (`homepagetabs`) to prosty moduł PrestaShop, zaprojektowany przede wszystkim do rozszerzania hooka `displayHome`. Postępuje zgodnie ze standardowym wzorcem PrestaShop podobnym do MVC dla modułów, gdzie główny plik modułu (`homepagetabs.php`) obsługuje instalację, deinstalację, konfigurację i rejestrację hooków. Moduł wstrzykuje niestandardową zakładkę i jej zawartość na stronę główną, wykorzystując istniejące mechanizmy pobierania produktów PrestaShop dla „popularnych produktów”.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest hermetyzowana w głównym pliku modułu oraz powiązanych z nim szablonach i zasobach.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Działa poprzez wykorzystanie podstawowych funkcjonalności PrestaShop do pobierania produktów.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`homepagetabs/views/js/homepagetabs.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten plik prawdopodobnie zawiera logikę JavaScript do obsługi funkcji przełączania zakładek na stronie głównej. Może nasłuchiwać zdarzeń kliknięcia na zakładce „Popularne produkty”, pokazywać/ukrywać odpowiednią zawartość produktu i potencjalnie współdziałać z innymi zakładkami strony głównej, aby zapewnić, że widoczna jest tylko zawartość jednej zakładki. Może również zawierać logikę dla responsywnego zachowania lub leniwego ładowania obrazów produktów w zakładce.
    -   **Kluczowa funkcjonalność:**
        -   Słuchacze zdarzeń dla kliknięć zakładek.
        -   Manipulacja DOM w celu przełączania widoczności list produktów.
        -   Potencjalnie integruje się z domyślnym zachowaniem zakładek PrestaShop lub niestandardowymi systemami zakładek szablonu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`homepagetabs/views/css/homepagetabs.css`**
    -   **Zakres:** Stylizacja klienta Front-office.
    -   **Cel:** Ten arkusz stylów definiuje wygląd wizualny zakładki „Popularne produkty” i list produktów w niej. Zapewnia, że zakładka jest prawidłowo umieszczona, ostylowana, a siatka/lista produktów jest schludnie prezentowana.
    -   **Główne komponenty interfejsu użytkownika stylizowane:**
        -   Sam nagłówek zakładki (np. `.homepagetabs-tab-title`).
        -   Kontener dla popularnych produktów (np. `.homepagetabs-products-container`).
        -   Poszczególne elementy produktu w zakładce (np. obrazy produktów, nazwy, ceny, przyciski).
        -   Responsywne dostosowania dla różnych rozmiarów ekranu.
    -   **Kluczowe selektory klas CSS do nadpisywania:** Programiści mogą sprawdzić wygenerowany kod HTML, aby znaleźć konkretne selektory. Typowe mogą obejmować:
        -   `.homepagetabs-tab`
        -   `.homepagetabs-tab-content`
        -   `.homepagetabs-product-list`
        -   `.homepagetabs-product-item`

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   **`homepagetabs/views/templates/hook/homepagetabs.tpl`**
        -   **Hook:** `displayHome`
        -   **Cel:** Jest to główny szablon front-office. Odpowiada za renderowanie nagłówka zakładki „Popularne produkty” i kontenera dla listy produktów. Zazwyczaj będzie iterować po kolekcji popularnych produktów przekazanych mu przez metodę `hookDisplayHome` modułu i renderować każdy produkt za pomocą standardowego fragmentu listy produktów PrestaShop (lub niestandardowego zdefiniowanego w module). Ten szablon jest miejscem, w którym generowana jest rzeczywista struktura HTML dla zakładki i jej zawartości.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   **`homepagetabs/views/templates/admin/homepagetabs.tpl`**
        -   **Cel:** Ten szablon renderuje formularz konfiguracji modułu w panelu administracyjnym PrestaShop. Wyświetla ustawienia powiadomień o aktualizacjach (`mypresta_updates`) i potencjalnie inne opcje specyficzne dla modułu, jeśli miałyby zostać dodane. Wykorzystuje klasy pomocnicze formularzy PrestaShop do generowania pól wejściowych i przycisków zapisu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne (takie jak `mypresta_updates`) w standardowej tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHome` | Renderuje zawartość na stronie głównej sklepu. | Wstrzykuje zakładkę „Popularne produkty” i jej zawartość do głównego obszaru strony głównej. |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Służy do umieszczania plików CSS (`homepagetabs.css`) i JavaScript (`homepagetabs.js`) modułu, zapewniając ich prawidłowe załadowanie dla wyświetlania w front-office. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich zapytań dotyczących modułu „Zakładka popularne produkty na stronie głównej”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia i zasoby są dostępne, aby pomóc w instalacji, konfiguracji i rozwiązywaniu problemów.
