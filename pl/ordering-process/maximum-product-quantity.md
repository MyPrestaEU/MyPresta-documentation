---
title: "Maksymalna ilość produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Maksymalna ilość produktu” od MyPresta.eu."
sidebar:
  label: "Maksymalna ilość produktu"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Maximum product quantity na MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-product-quantity.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/maximum-product-quantity/)
>
> ---


# Maksymalna ilość produktu

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są wymagane żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Maksymalna ilość produktu)

Główna strona konfiguracji modułu to miejsce, w którym definiujesz globalne ustawienia i zarządzasz limitami ilościowymi dla poszczególnych produktów.

#### **Ustawienia ogólne**

-   **Co robi to ustawienie:** Są to podstawowe ustawienia, które włączają lub wyłączają funkcjonalność modułu i definiują, jak zachowuje się on globalnie.
-   **Efekt zmiany tego ustawienia:**
    -   *Włącz/Wyłącz moduł:* Włącza lub wyłącza cały system limitowania ilości.
    -   *Globalna maksymalna ilość:* Ustawia domyślną maksymalną ilość dla wszystkich produktów, jeśli nie zdefiniowano konkretnego limitu.
-   **Zalecana wartość:** Zacznij od włączenia modułu i ustawienia rozsądnej globalnej maksymalnej ilości, jeśli chcesz zastosować ogólną zasadę.
-   **Scenariusz / przykład sprzedawcy:** Jeśli chcesz mieć pewność, że żaden klient nigdy nie kupi więcej niż 100 jednostek *jakiegokolwiek* produktu, ustaw globalną maksymalną ilość na 100.

#### **Limity ilościowe dla poszczególnych produktów**

Ta sekcja to zazwyczaj tabela lub lista, w której możesz wyszukiwać produkty i definiować dla nich konkretne limity.

-   **Co robi to ustawienie:** Pozwala nadpisać globalne ustawienia dla poszczególnych produktów. Możesz określić:
    -   **Maksymalna ilość na zamówienie:** Największa liczba jednostek tego produktu, jaką klient może dodać do jednego koszyka.
    -   **Maksymalna ilość na klienta (łącznie):** Największa liczba jednostek tego produktu, jaką konkretny klient może kupić *we wszystkich swoich zamówieniach*.
    -   **Limity specyficzne dla grupy klientów:** Zastosuj różne limity w zależności od grupy klientów (np. „Goście”, „Klienci”, „Hurtownicy”).
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy limity są ustawione:* Moduł będzie egzekwował te konkretne limity dla wybranego produktu, nadpisując wszelkie globalne ustawienia.
    -   *Gdy limity zostaną usunięte:* Produkt powróci do korzystania z globalnych ustawień maksymalnej ilości.
-   **Zalecana wartość:** Ustaw konkretne limity dla produktów o wysokim popycie, niskim stanie magazynowym lub strategicznie ważnych.
-   **Scenariusz / przykład sprzedawcy:**
    -   Masz produkt z edycji limitowanej. Ustawiasz „Maksymalna ilość na zamówienie” na 1 i „Maksymalna ilość na klienta (łącznie)” na 1, aby zapewnić jedną jednostkę na klienta.
    -   Dla produktu hurtowego możesz ustawić „Maksymalna ilość na zamówienie” na 50 dla „Klientów”, ale 500 dla „Hurtowników”.

#### **Ustawienia śledzenia historii zamówień**

-   **Co robi to ustawienie:** Kontroluje, czy moduł przegląda poprzednie zamówienia klienta w celu egzekwowania limitów „maksymalnej ilości na klienta (łącznie)”. Często można określić, które statusy zamówień wliczają się do limitu (np. tylko zamówienia „Dostarczone” lub „Płatność zaakceptowana”).
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Moduł będzie odpytywał historię zamówień klienta, aby obliczyć jego całkowite zakupy produktu.
    -   *Gdy wyłączone:* Tylko bieżąca ilość w koszyku zostanie sprawdzona pod kątem limitu „maksymalnej ilości na zamówienie”. Limity „maksymalnej ilości na klienta (łącznie)” zostaną faktycznie zignorowane.
-   **Zalecana wartość:** Włącz to, jeśli chcesz egzekwować prawdziwe limity na klienta w czasie. Wybierz odpowiednie statusy zamówień (np. „Płatność zaakceptowana”, „Dostarczone”), aby dokładnie śledzić zakupy.
-   **Scenariusz / przykład sprzedawcy:** Prowadzisz promocję, w której każdy klient może kupić maksymalnie 3 jednostki konkretnego produktu *w ogóle*. Włączasz śledzenie historii zamówień i wybierasz statusy „Płatność zaakceptowana” i „Dostarczone”. Jeśli klient kupił już 2, może dodać tylko 1 więcej do koszyka.

#### **Dostosowywanie komunikatu o błędzie**

-   **Co robi to ustawienie:** Pozwala dostosować komunikat wyświetlany klientom, gdy przekroczą limit ilości.
-   **Efekt zmiany tego ustawienia:** Domyślny, ogólny komunikat o błędzie zostanie zastąpiony Twoim niestandardowym tekstem, który może być bardziej informacyjny lub markowy.
-   **Zalecana wartość:** Podaj jasny, uprzejmy i pomocny komunikat. Możesz użyć symboli zastępczych (jeśli są obsługiwane przez moduł), takich jak `{max_quantity}`, aby pokazać rzeczywisty limit.
-   **Scenariusz / przykład sprzedawcy:** Zamiast „Ilość przekracza maksimum”, możesz ustawić: „Przepraszamy, możesz kupić maksymalnie {max_quantity} jednostek tego produktu. Pomaga nam to zapewnić sprawiedliwy dostęp dla wszystkich naszych klientów!”

#### **Eksport i import CSV / JSON (jeśli dostępne)**

-   **Co robi to ustawienie:** Udostępnia narzędzia do eksportowania bieżących limitów ilościowych do pliku CSV lub JSON oraz importowania nowych limitów z takich plików. Jest to przydatne do masowej edycji lub migracji ustawień.
-   **Efekt zmiany tego ustawienia:**
    -   *Eksport:* Tworzy plik ze wszystkimi zdefiniowanymi limitami ilościowymi produktów.
    -   *Import:* Nadpisuje lub dodaje nowe limity ilościowe na podstawie danych w przesłanym pliku.
-   **Zalecana wartość:** Użyj tego do aktualizacji na dużą skalę lub początkowej konfiguracji, jeśli masz wiele produktów z określonymi limitami. Zawsze twórz kopię zapasową bieżących ustawień przed importowaniem.
-   **Scenariusz / przykład sprzedawcy:** Uruchamiasz nowy katalog z 500 produktami, z których każdy potrzebuje unikalnej maksymalnej ilości. Zamiast ręcznie wprowadzać każdy, przygotowujesz plik CSV i importujesz go.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Włącz/Wyłącz moduł | Włączony | Włącza/wyłącza wszystkie funkcje limitowania ilości. |
| Konfiguracja modułu | Globalna maksymalna ilość na zamówienie | Różnie / 100 | Ustawia domyślną maksymalną ilość dla produktów bez określonych limitów. |
| Konfiguracja modułu | Maksymalna ilość na zamówienie dla konkretnego produktu | Różnie / Niestandardowe | Nadpisuje globalny limit dla poszczególnych produktów w jednym koszyku. |
| Konfiguracja modułu | Maksymalna ilość na klienta (łącznie) dla konkretnego produktu | Różnie / Niestandardowe | Ogranicza całkowite zakupy produktu przez klienta we wszystkich zamówieniach. |
| Konfiguracja modułu | Limity specyficzne dla grupy klientów | Różnie / Niestandardowe | Stosuje różne limity w zależności od grup klientów (np. Hurtownicy). |
| Konfiguracja modułu | Śledź historię zamówień | Włączone | Sprawdza poprzednie zamówienia w celu egzekwowania „Maksymalnej ilości na klienta (łącznie)”. |
| Konfiguracja modułu | Statusy zamówień do śledzenia | Płatność zaakceptowana, Dostarczone | Definiuje, które statusy zamówień wliczają się do całkowitych zakupów klienta. |
| Konfiguracja modułu | Niestandardowy komunikat o błędzie | „Ilość przekracza limit” | Personalizuje komunikat wyświetlany klientom, gdy limit zostanie osiągnięty. |
| Konfiguracja modułu | Eksport/Import CSV/JSON | N/A | Umożliwia masowe zarządzanie limitami ilościowymi poprzez przesyłanie/pobieranie plików. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem limity, ale klienci nadal mogą dodawać więcej niż dozwolone. Co jest nie tak?**
O1:
*   **Moduł włączony?** Najpierw dokładnie sprawdź, czy moduł jest włączony w głównej konfiguracji.
*   **Konkretny produkt a globalny:** Upewnij się, że poprawnie ustawiłeś limity dla *konkretnego produktu*, o którym mowa, lub że globalne limity są aktywne, jeśli nie ma limitów dla konkretnego produktu.
*   **Grupa klientów:** Sprawdź, czy grupa klientów, do której należy klient, ma zastosowane prawidłowe limity.
*   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Czasami nadal są serwowane stare ustawienia.
*   **Konflikty motywów:** Rzadko, bardzo dostosowany motyw może zakłócać sposób obsługi wprowadzania ilości. Przetestuj z domyślnym motywem PrestaShop, aby to wykluczyć.

**P2: „Maksymalna ilość na klienta (łącznie)” nie działa, nawet przy włączonym śledzeniu historii zamówień.**
O2:
*   **Statusy zamówień:** Przejdź do konfiguracji modułu i sprawdź, które „Statusy zamówień do śledzenia” są wybrane. Jeśli poprzednie zamówienia klienta mają status, który nie został wybrany (np. „Oczekujące” zamiast „Dostarczone”), nie będą one wliczane do limitu. Upewnij się, że odpowiednie statusy są zaznaczone.
*   **Logowanie klienta:** Upewnij się, że klient jest zalogowany. Moduł może śledzić poprzednie zakupy tylko dla zidentyfikowanych klientów, a nie gości.

**P3: Jak przetłumaczyć komunikaty o błędach na inne języki?**
O3:
*   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
*   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz swój język.
*   Znajdź moduł „Maksymalna ilość produktu” na liście. Powinieneś być w stanie edytować niestandardowe komunikaty o błędach, które ustawiłeś dla każdego języka.

**P4: Moduł wydaje się spowalniać moje strony produktów lub koszyk.**
O4:
*   Chociaż moduł jest zoptymalizowany, jeśli masz bardzo dużą liczbę produktów ze złożonymi, specyficznymi dla grup limitami i rozbudowanym śledzeniem historii zamówień, może to spowodować niewielkie obciążenie.
*   **Wydajność > CCC:** Upewnij się, że ustawienia CCC (Łącz, Kompresuj, Cache) dla CSS i JavaScript są włączone w **Zaawansowane > Wydajność**.
*   **Zasoby serwera:** Sprawdź limit pamięci PHP i czas wykonania serwera. Jeśli są zbyt niskie, może to wpłynąć na wydajność.
*   **Optymalizacja bazy danych:** Upewnij się, że Twoja baza danych PrestaShop jest regularnie optymalizowana.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla deweloperów i webmasterów pracujących z modułem „Maksymalna ilość produktu”.

### 4.1 Przegląd architektury
Moduł `Maksymalna ilość produktu` (nazwa wewnętrzna `mqc`) to standardowy moduł PrestaShop zaprojektowany w celu rozszerzenia podstawowego procesu zamawiania. Działa głównie poprzez podłączanie się do różnych punktów front-office (strona produktu, koszyk, kasa) w celu walidacji ilości produktów w stosunku do skonfigurowanych limitów. Konfiguracja jest zarządzana za pomocą pojedynczej metody `getContent()` w głównym pliku modułu, wykorzystując klasę `Configuration` PrestaShop do przechowywania ustawień. Wykorzystuje JavaScript do walidacji front-end i informacji zwrotnej dla użytkownika, a szablony Smarty do wyświetlania komunikatów i formularzy konfiguracji.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie zawiera dedykowanych kontrolerów front-office ani back-office. Cała logika front-office jest obsługiwana za pomocą hooków i JavaScriptu, podczas gdy konfiguracja back-office jest zarządzana bezpośrednio w metodzie `getContent()` pliku modułu `index.php`.

### 4.3 Klasy i modele podstawowe (`classes/`)
Moduł nie definiuje niestandardowych klas `ObjectModel`. Wszystkie dane są przechowywane bezpośrednio w tabeli `ps_configuration` przy użyciu standardowych kluczy konfiguracyjnych PrestaShop. Podstawowa logika znajduje się w pliku `mqc/index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`mqc/views/js/mqc-17500.js`**:
    *   **Zakres:** Front-office (specyficzne dla PrestaShop 1.7.5.0+).
    *   **Odpowiedzialność:** Zawiera logikę JavaScript dostosowaną do nowszych wersji PrestaShop 1.7.x i 8.x. Prawdopodobnie podłącza się do `prestashop.on('updateProduct', ...)` lub podobnych zdarzeń w celu ponownej walidacji ilości, gdy atrybuty produktu się zmieniają lub gdy dane wejściowe ilości są modyfikowane na stronie produktu. Może również obsługiwać wywołania AJAX do `index.php` modułu w celu uzyskania walidacji ilości w czasie rzeczywistym.
    *   **Interakcja:** Wiąże się z polami wprowadzania ilości, przyciskami dodawania do koszyka i potencjalnie selektorami atrybutów produktu, aby zapewnić użytkownikowi natychmiastową informację zwrotną, jeśli limit ilości zostanie przekroczony.

-   **`mqc/views/js/mqc-front.js`**:
    *   **Zakres:** Front-office (ogólne, potencjalnie dla starszych wersji PrestaShop lub wspólnej logiki).
    *   **Odpowiedzialność:** Zawiera ogólną logikę JavaScript front-office do walidacji ilości. Może to obejmować:
        *   Słuchacze zdarzeń dla zmian wprowadzania ilości na stronie produktu lub w koszyku.
        *   Wywołania AJAX do serwera w celu sprawdzenia limitów ilości.
        *   Wyświetlanie komunikatów o błędach użytkownikowi.
        *   Potencjalne wyłączanie lub ograniczanie pól wprowadzania ilości.
    *   **Interakcja:** Podobnie jak `mqc-17500.js`, ale może używać starszego wiązania zdarzeń opartego na jQuery lub mniej specyficznych zdarzeń PrestaShop.

-   **`mqc/views/js/mqc.js`**:
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Obsługuje JavaScript dla strony konfiguracji modułu w Panelu administracyjnym PrestaShop. Może to obejmować:
        *   Dynamiczne elementy formularza (np. dodawanie/usuwanie wierszy limitów dla konkretnych produktów).
        *   Wyszukiwanie produktów za pomocą AJAX podczas ustawiania indywidualnych limitów.
        *   Walidacja pól wprowadzania w formularzu konfiguracji.
        *   Logika dla funkcji importu/eksportu CSV/JSON.
    *   **Interakcja:** Wiąże się z elementami formularza na stronie konfiguracji modułu, potencjalnie wykonując żądania AJAX do metody `getContent()` modułu w celu pobierania lub przesyłania danych.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`mqc/views/css/mqc.css`**:
    *   **Zakres:** Zarówno Front-office (dla komunikatów o błędach), jak i Back-office (dla stylizacji strony konfiguracji).
    *   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:**
        *   Kontenery komunikatów o błędach (np. `div.alert.alert-danger` lub niestandardowe klasy dla komunikatów specyficznych dla modułu).
        *   Pola wprowadzania i etykiety na stronie konfiguracji back-office.
        *   Potencjalnie stylizacja dla dynamicznych elementów dodanych przez `mqc.js` (np. wyniki wyszukiwania produktów, wiersze tabeli dla limitów).
    *   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać:** Szukaj klas takich jak `.mqc-error-message`, `.mqc-limit-table`, `.mqc-product-search-results` w szablonach modułu i generowanym kodzie HTML. Deweloperzy mogą je nadpisać w pliku `custom.css` swojego motywu lub tworząc motyw potomny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty zarówno do wyświetlania front-office, jak i konfiguracji back-office.

-   **Szablony hooków (`views/templates/hook/`)**:
    *   **`product-details.tpl`**:
        *   **Hook:** Prawdopodobnie `displayProductExtraContent` lub `displayProductButtons` (w zależności od wersji PrestaShop i konkretnej implementacji).
        *   **Wyjście:** Może wyświetlać mały komunikat informacyjny o limitach ilościowych na stronie produktu lub renderować niestandardowe pole wprowadzania ilości, jeśli moduł zastępuje domyślne.
    *   **`productActions.tpl`**:
        *   **Hook:** `displayProductActions` (na stronie produktu).
        *   **Wyjście:** Potencjalnie używane do wstrzykiwania zmiennych JavaScript lub ukrytych pól wprowadzania związanych z limitami ilościowymi w pobliżu przycisku dodawania do koszyka lub do wyświetlania komunikatu o błędzie, jeśli limit ilości zostanie przekroczony przed dodaniem do koszyka.
    *   **`shoppingCart.tpl`**:
        *   **Hook:** `displayShoppingCartFooter` lub `displayShoppingCart` (na stronie koszyka).
        *   **Wyjście:** Używane do wyświetlania komunikatów o błędach bezpośrednio w koszyku, jeśli ilości przekraczają limity, uniemożliwiając przejście do kasy.

-   **Szablony administracyjne (`views/templates/admin/`)**: Te szablony są renderowane w metodzie `getContent()` pliku `mqc/index.php` w celu zbudowania interfejsu konfiguracji modułu.
    *   **`admintab.tpl`**: Prawdopodobnie opakowanie lub wspólny nagłówek/stopka dla strony konfiguracji administratora.
    *   **`button-subcategories-purchases.tpl`**: Może to być przycisk lub sekcja związana z zarządzaniem zakupami według podkategorii, prawdopodobnie do zaawansowanego raportowania lub ustawiania limitów.
    *   **`button-subcategories.tpl`**: Podobnie jak powyżej, ale dla podkategorii ogólnie.
    *   **`csv.tpl`**: Szablon dla funkcji eksportu CSV, potencjalnie zawierający elementy formularza do wyboru opcji eksportu.
    *   **`csv_file.tpl`**: Szablon dla funkcji importu CSV, zazwyczaj formularz przesyłania.
    *   **`json.tpl`**: Szablon dla eksportu/importu JSON, podobny do `csv.tpl` i `csv_file.tpl`.
    *   **`main.tpl`**: Główny szablon dla strony konfiguracji modułu, zawierający główną strukturę formularza, ogólne ustawienia i potencjalnie tabelę dla limitów specyficznych dla produktów.
    *   **`message.tpl`, `message2.tpl`, `message3.tpl`, `message4.tpl`, `message5.tpl`**: Ogólne szablony komunikatów używane do wyświetlania komunikatów o sukcesie, błędzie lub informacyjnych w konfiguracji back-office.
    *   **`orderstates.tpl`**: Szablon do wyboru, które statusy zamówień wliczają się do limitu „maksymalnej ilości na klienta (łącznie)”.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie tworzy niestandardowych tabel SQL.
    *   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`. Klucze konfiguracyjne będą zazwyczaj zgodne ze wzorcem, takim jak `MQC_GLOBAL_MAX_QTY`, `MQC_PRODUCT_LIMITS_[id_product]`, `MQC_TRACK_HISTORY_STATUSES` itp. Limity specyficzne dla produktów mogą być przechowywane jako serializowane tablice lub ciągi JSON w jednym kluczu konfiguracyjnym lub jako indywidualne klucze dla każdego produktu/grupy.
    *   Śledzenie historii zamówień opiera się na odpytywaniu istniejących tabel PrestaShop: `ps_orders`, `ps_order_detail` i `ps_order_state`.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony. | Rejestruje zasoby CSS i JavaScript (`mqc.css`, `mqc-front.js`, `mqc-17500.js`) dla funkcjonalności front-office. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” na stronie produktu. | Wstrzykuje logikę walidacji ilości lub wyświetla komunikaty związane z limitami specyficznymi dla produktu. |
| `displayProductExtraContent` | Poniżej opisu produktu, powyżej produktów powiązanych. | Może być używany do wyświetlania komunikatów informacyjnych o limitach ilościowych. |
| `displayShoppingCart` | W podsumowaniu koszyka. | Waliduje ilości w koszyku i wyświetla komunikaty o błędach, jeśli limity zostaną przekroczone. |
| `displayShoppingCartFooter` | Na dole strony koszyka. | Podobnie jak `displayShoppingCart`, do ostatecznej walidacji przed przejściem do kasy. |
| `actionValidateOrder` | Po walidacji i zapisaniu zamówienia. | Potencjalnie używane do przetwarzania po zamówieniu lub logowania, chociaż główna walidacja odbywa się przed przejściem do kasy. |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka (np. zmiana ilości). | Kluczowe dla walidacji ilości w czasie rzeczywistym, gdy klient modyfikuje ilości w koszyku lub dodaje nowe produkty. |
| `actionFrontControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler front-office. | Rejestruje zasoby front-office, podobnie jak `displayHeader`, ale bardziej specyficzne dla kontekstu kontrolera. |
| `actionAdminControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler administratora. | Rejestruje zasoby back-office (`mqc.js`, `mqc.css`) dla strony konfiguracji modułu. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Maksymalna ilość produktu”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i deweloperom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
"""
