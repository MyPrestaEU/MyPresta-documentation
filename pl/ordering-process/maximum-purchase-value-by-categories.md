---
title: "Maksymalna wartość zakupu według kategorii - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Maksymalna wartość zakupu według kategorii” od MyPresta.eu."
sidebar:
  label: "Maksymalna wartość zakupu według kategorii - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Maximum purchase value by categories na MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-categories.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/maximum-purchase-value-by-categories/)
>
> ---


# Maksymalna wartość zakupu według kategorii

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel Administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, gdzie zarządzasz ogólnymi ustawieniami i uzyskujesz dostęp do zasad dotyczących maksymalnych wartości zakupu.

-   **Do czego służy to ustawienie:** Ta strona dostarcza ogólnych informacji o module i często zawiera link lub przycisk do zarządzania rzeczywistymi zasadami.
-   **Wpływ zmiany tego ustawienia:** Chociaż ten konkretny ekran może nie mieć bezpośrednich „ustawień” do zmiany, służy jako punkt wejścia do funkcjonalności modułu.
-   **Zalecana wartość:** N/A (Jest to ekran informacyjny).
-   **Scenariusz / przykład dla sprzedawcy:** Po instalacji wylądujesz tutaj. Następnie klikniesz przycisk lub link (np. „Zarządzaj zasadami” lub „Konfiguruj maksymalne wartości”), aby przejść do dedykowanego ekranu, gdzie zdefiniujesz limity kategorii.

### 2.2 Dedykowany Ekran Administracyjny: Zasady Maksymalnej Wartości Zakupu (Panel Administracyjny > Moduły > Maksymalna wartość zakupu według kategorii > Konfiguruj)

To jest rdzeń modułu, gdzie definiujesz i zarządzasz zasadami maksymalnej wartości zakupu dla różnych kategorii. Zazwyczaj znajdziesz ten ekran, klikając „Konfiguruj” po zainstalowaniu modułu, lub przechodząc do **Moduły > Menedżer modułów**, znajdując moduł i klikając „Konfiguruj”.

**Nazwa Ekranu i Lokalizacja w Menu:**
Dostęp do tego ekranu uzyskasz, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Maksymalna wartość zakupu według kategorii” i klikając przycisk „Konfiguruj”. Spowoduje to przejście do dedykowanego interfejsu administracyjnego do zarządzania zasadami.

**Dostępne Akcje i Ustawienia:**
Na tym ekranie zobaczysz listę (siatkę) wszystkich aktualnie zdefiniowanych zasad maksymalnej wartości zakupu. Dla każdej zasady zazwyczaj zobaczysz:

-   **Nazwa Kategorii:** Nazwa kategorii produktu, do której odnosi się zasada.
-   **Maksymalna Wartość:** Najwyższa łączna wartość (w Twojej domyślnej walucie) dozwolona dla produktów z tej kategorii w jednym zamówieniu.
-   **Akcje:** Przyciski do „Edytuj” istniejącą zasadę lub „Usuń” ją.

Znajdziesz również:

-   **Przycisk „Dodaj Nową Zasadę”:** Widoczny przycisk do tworzenia nowej zasady maksymalnej wartości zakupu.

**Podczas dodawania lub edytowania zasady, zazwyczaj napotkasz następujące pola:**

1.  **Wybierz Kategorię:**

    -   **Do czego służy to ustawienie:** Pozwala wybrać, do której konkretnej kategorii produktów będzie miała zastosowanie ta zasada maksymalnej wartości zakupu. Zazwyczaj zobaczysz rozwijaną listę lub selektor drzewa kategorii.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy kategoria jest wybrana:* Zasada będzie miała zastosowanie do wszystkich produktów w tej kategorii (i często jej podkategoriach, w zależności od logiki modułu).
        -   *Gdy żadna kategoria nie jest wybrana (lub jeśli ją zmienisz):* Zasada będzie nieprawidłowa lub będzie miała zastosowanie do innej kategorii.
    -   **Zalecana wartość:** Wybierz konkretną kategorię, którą chcesz ograniczyć.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz ograniczyć zakupy produktów „Elektronika”. Wybierzesz „Elektronika” z listy.
2.  **Maksymalna Wartość Zakupu:**

    -   **Do czego służy to ustawienie:** Jest to wartość numeryczna (w domyślnej walucie Twojego sklepu), która reprezentuje najwyższą dozwoloną sumę dla produktów z wybranej kategorii w koszyku klienta.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy ustawiona na konkretną wartość (np. 500):* Klienci nie będą mogli mieć w koszyku produktów z wybranej kategorii o wartości przekraczającej 500 jednostek Twojej domyślnej waluty.
        -   *Gdy ustawiona na 0 lub pozostawiona pusta (jeśli dozwolone):* Może to wyłączyć zasadę dla kategorii lub być uznane za nieprawidłowy wpis.
    -   **Zalecana wartość:** Dodatnia wartość numeryczna reprezentująca pożądany limit (np. `250.00`).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz ograniczyć „Limitowane Edycje Druków Artystycznych” do maksymalnie 250 $ za zamówienie. Wprowadzisz tutaj `250`. Moduł automatycznie obliczy równoważne wartości dla innych walut, jeśli Twój sklep je obsługuje.

**Wpływ zmian:**

-   **Dodanie nowej zasady:** Natychmiastowo egzekwuje maksymalną wartość zakupu dla wybranej kategorii w całym Twoim sklepie. Klienci będą mieli uniemożliwione przekroczenie tego limitu.
-   **Edycja zasady:** Aktualizuje maksymalną wartość dla istniejącej kategorii. Nowy limit wchodzi w życie natychmiast.
-   **Usunięcie zasady:** Usuwa ograniczenie dla tej kategorii. Klienci nie będą już ograniczeni w swoich zakupach z tej kategorii.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  Okresowo przeglądaj swoje kategorie produktów i identyfikuj te, które mogą skorzystać z limitu wartości zakupu (np. nowe produkty o wysokim popycie, produkty z ograniczonym zapasem lub produkty z konkretnymi umowami dystrybucyjnymi).
2.  Przejdź do ekranu konfiguracji „Maksymalna wartość zakupu według kategorii”.
3.  Użyj przycisku „Dodaj Nową Zasadę”, aby utworzyć nowe limity.
4.  Monitoruj opinie klientów lub wzorce zamówień, aby dostosować istniejące limity w razie potrzeby, używając akcji „Edytuj”.
5.  Jeśli linia produktów lub kategoria nie wymaga już limitu, użyj akcji „Usuń”, aby usunąć zasadę.

### 2.3 Tabela Szybkiego Odniesienia Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| AdminMaobcController (Zarządzanie Zasadami) | **Wybierz Kategorię** | Konkretna Nazwa Kategorii | Definiuje, do której kategorii produktów ma zastosowanie maksymalna wartość. |
| AdminMaobcController (Zarządzanie Zasadami) | **Maksymalna Wartość Zakupu** | Wartość numeryczna (np. `250.00`) | Ustawia najwyższą łączną wartość dozwoloną dla produktów z wybranej kategorii w jednym zamówieniu (w domyślnej walucie). Automatycznie konwertuje dla innych walut. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P1: Ustawiłem limit, ale klienci nadal mogą go przekroczyć. Co jest nie tak?**
O1:

-   **Sprawdź przypisanie kategorii:** Upewnij się, że produkty są poprawnie przypisane do kategorii, dla której ustawiłeś limit.
-   **Moduł włączony:** Sprawdź, czy moduł „Maksymalna wartość zakupu według kategorii” jest włączony w **Moduły > Menedżer modułów**.
-   **Zasada jest aktywna:** Przejdź do konfiguracji modułu i upewnij się, że zasada dla konkretnej kategorii jest obecna i ma prawidłową maksymalną wartość.
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P2: Moduł pokazuje niewłaściwą walutę lub nie konwertuje poprawnie.**
O2: Moduł automatycznie używa domyślnej waluty Twojego sklepu dla wprowadzonej wartości, a następnie konwertuje ją dla innych walut.

-   **Domyślna waluta:** Upewnij się, że Twoja domyślna waluta jest poprawnie ustawiona w **Lokalizacja > Waluty**. Wartość, którą wprowadzasz w konfiguracji modułu, zawsze powinna być w tej domyślnej walucie.
-   **Kursy wymiany:** Sprawdź swoje kursy wymiany w **Lokalizacja > Waluty**, aby upewnić się, że są aktualne i dokładne dla obsługiwanych walut.

**P3: Czy mogę ustawić różne limity dla różnych grup klientów?**
O3: Ten konkretny moduł ustawia globalny limit dla każdej kategorii, mający zastosowanie do wszystkich klientów. Jeśli potrzebujesz różnych limitów dla konkretnych grup klientów (np. hurtowych vs. detalicznych), potrzebowałbyś bardziej zaawansowanego modułu lub niestandardowego rozwiązania.

**P4: Jak przetłumaczyć komunikaty o błędach wyświetlane klientom?**
O4: Komunikaty front-office modułu są zazwyczaj możliwe do przetłumaczenia za pomocą systemu tłumaczeń PrestaShop:

1.  Przejdź do **Lokalizacja > Tłumaczenia**.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
3.  Wybierz swój szablon, język, a następnie wybierz „Maksymalna wartość zakupu według kategorii” z listy modułów.
4.  Następnie możesz znaleźć i edytować ciągi tekstowe wyświetlane przez moduł Twoim klientom.

**P5: Moduł wydaje się kolidować z innym modułem w moim koszyku/kasie.**
O5: Konflikty modułów mogą czasami występować.

-   **Izoluj problem:** Tymczasowo wyłączaj inne moduły, które wchodzą w interakcję z koszykiem lub stroną produktu, jeden po drugim, aby sprawdzić, czy konflikt ustępuje.
-   **Kompatybilność z szablonem:** Jeśli używasz niestandardowego szablonu, może on mieć specyficzne nadpisania, które kolidują. Sprawdź, czy problem występuje również z domyślnym szablonem PrestaShop.
-   **Skontaktuj się z pomocą techniczną:** Jeśli nie możesz zidentyfikować konfliktu, zbierz szczegóły (które moduły, jaki dokładnie błąd) i skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla Programistów i Webmasterów (Architektura Techniczna i Mapa Kodu)

### 4.1 Przegląd Architektury

Moduł „Maksymalna wartość zakupu według kategorii” (`maobc`) wykorzystuje standardowy wzorzec PrestaShop MVC (Model-View-Controller). Głównie używa kontrolera administracyjnego do zarządzania konfiguracją i zasadami, oraz kontrolera front-office do przechwytywania żądań AJAX związanych z aktualizacjami koszyka. Główna logika znajduje się w głównej klasie modułu, która podłącza się do różnych zdarzeń PrestaShop, aby egzekwować limity wartości oparte na kategoriach. Przechowuje swoją konfigurację w tabeli `ps_configuration` i zarządza swoimi zasadami za pomocą niestandardowej tabeli i kontrolera administracyjnego.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa Klasy**: `MaobcAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Ten kontroler jest odpowiedzialny za obsługę żądań AJAX z front-office, głównie tych związanych z dodawaniem produktów do koszyka lub aktualizacją ilości w koszyku. Przechwytuje te żądania, aby wykonać walidację w czasie rzeczywistym względem zdefiniowanych zasad maksymalnej wartości zakupu, zanim PrestaShop przetworzy aktualizację koszyka. Zwraca odpowiedzi JSON wskazujące na sukces lub niepowodzenie z odpowiednimi komunikatami.
    -   `controllers/front/index.php`
        -   **Nazwa Klasy**: `MaobcIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Ten kontroler może służyć jako rezerwowy lub prosty punkt wejścia, ale biorąc pod uwagę funkcjonalność modułu, `ajax.php` jest głównym punktem interakcji z front-office. Może renderować prostą stronę lub przekierowywać, jeśli jest dostępny bezpośrednio.
-   **Kontrolery Administracyjne Back-Office**:

    -   `controllers/admin/AdminMaobc.php`
        -   **Nazwa Klasy**: `AdminMaobcController` (rozszerza `ModuleAdminController`)
        -   **Nazwa Zakładki**: „Maksymalna wartość zakupu według kategorii” (lub podobna, dostępna poprzez przycisk „Konfiguruj” modułu).
        -   **Zarządzana Encja**: Ten kontroler zarządza niestandardową encją `maobc`, która reprezentuje indywidualne zasady maksymalnych wartości zakupu dla każdej kategorii. Obsługuje operacje CRUD (Create, Read, Update, Delete) dla tych zasad.
        -   **Odpowiedzialność**: Wyświetla listę (siatkę) wszystkich skonfigurowanych zasad, pozwala administratorom dodawać nowe zasady, edytować istniejące (wybierając kategorię i ustawiając maksymalną wartość) oraz usuwać zasady. Współpracuje z wewnętrznym magazynem danych modułu (prawdopodobnie niestandardową tabelą bazy danych lub wpisami `ps_configuration`).
    -   `controllers/admin/index.php`
        -   **Nazwa Klasy**: `AdminMaobcIndexController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność**: Podobnie jak `index.php` front-office, może to być prosty punkt wejścia lub rezerwowy. `AdminMaobcController` jest głównym kontrolerem do zarządzania zasadami modułu.

### 4.3 Klasy Rdzenne i Modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że główna logika modułu i obsługa danych są prawdopodobnie zintegrowane bezpośrednio z głównym plikiem modułu (`maobc/index.php`) lub zarządzane za pomocą standardowej klasy `Configuration` PrestaShop dla ustawień i potencjalnie niestandardowej tabeli bazy danych zarządzanej bezpośrednio przez `AdminMaobcController` bez dedykowanego `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/maobc.js`
    -   **Zakres**: Front-office.
    -   **Szczegóły**: Ten skrypt jest prawdopodobnie odpowiedzialny za interakcje po stronie klienta związane z aktualizacjami koszyka. Może:
        -   Nadpisywać lub rozszerzać domyślne funkcje koszyka AJAX PrestaShop (np. kliknięcia przycisku `dodaj do koszyka`).
        -   Przechwytywać odpowiedzi AJAX z `controllers/front/ajax.php`, aby wyświetlać niestandardowe komunikaty o błędach użytkownikowi, jeśli maksymalna wartość zostanie przekroczona.
        -   Potencjalnie aktualizować interfejs użytkownika (np. wyłączać przyciski, wyświetlać alerty) na podstawie wyników walidacji.
        -   Prawdopodobnie będzie używać `jQuery` lub zdarzeń `prestashop.on` do wiązania swojej logiki.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   `views/css/maobc.css`
    -   **Zakres**: Front-office.
    -   **Szczegóły**: Ten arkusz stylów zapewnia niestandardowe style dla elementów front-office modułu, głównie komunikatów powiadomień wyświetlanych klientom, gdy maksymalna wartość zakupu zostanie przekroczona.
    -   **Kluczowe selektory klas CSS**: Programiści powinni sprawdzić ten plik pod kątem klas takich jak `.maobc-error-message`, `.maobc-alert` lub podobnych, które można nadpisać w pliku `custom.css` lub `theme.css` ich szablonu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   Dossier modułu nie wymienia jawnie szablonów w `views/templates/hook/`. Sugeruje to, że wszelkie komunikaty lub dynamiczna zawartość mogą być wstrzykiwane bezpośrednio za pomocą JavaScriptu lub renderowane przez główny plik modułu za pomocą metod `display()`.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   Dossier modułu nie wymienia jawnie szablonów w `views/templates/admin/`. `AdminMaobcController` prawdopodobnie używa standardowych formularzy pomocniczych PrestaShop (`HelperList`, `HelperForm`) dla swojej siatki i formularzy konfiguracji, które dynamicznie generują swój kod HTML.
-   **Szablony front-office (`views/templates/front/`)**:

    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie używany do wyświetlania niestandardowego komunikatu o błędzie na stronie koszyka, jeśli maksymalna wartość zakupu dla kategorii zostanie przekroczona. Zawierałby strukturę HTML dla alertu lub powiadomienia, które informuje klienta o limicie. Prawdopodobnie jest podłączony do `displayShoppingCartFooter` lub podobnego hooka.

### 4.7 Schemat Bazy Danych i Mapa Hooków

-   **Tabele Bazy Danych**:

    -   Moduł prawdopodobnie tworzy niestandardową tabelę bazy danych (np. `ps_maobc_rules`) do przechowywania ID kategorii i powiązanej maksymalnej wartości zakupu dla każdej zasady.
    -   Wartości konfiguracyjne (np. status włączenia modułu, ogólne ustawienia) są przechowywane w tabeli `ps_configuration`, zazwyczaj z kluczami poprzedzonymi prefiksem `MAOBC_`.
-   **Tabela Zarejestrowanych Hooków**:

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Potencjalnie używany do ładowania zasobów `maobc.js` i `maobc.css` lub do wstrzykiwania zmiennych JavaScript. |
| `displayRightColumn` / `displayLeftColumn` | Renderuje zawartość w bocznych kolumnach. | Mniej prawdopodobne dla tego modułu, ale może być używane do wyświetlania statycznego komunikatu o limitach zakupu. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Renderuje się na stronie produktu. | Może być używany do wyświetlania komunikatu ostrzegawczego na stronie produktu, jeśli przedmiot należy do ograniczonej kategorii. |
| `displayShoppingCartFooter` / `displayShoppingCart` | Renderuje się na stronie koszyka. | Używany do wyświetlania szablonu `displayShoppingCart.tpl` z komunikatami o błędach, jeśli limity zostaną przekroczone. |
| `actionCartSave` | Wykonywany po zapisaniu koszyka (np. dodaniu/usunięciu produktu, zmianie ilości). | Kluczowy dla walidacji zawartości koszyka po stronie serwera względem limitów kategorii. To tutaj główna logika zapobiega nieprawidłowym stanom koszyka. |
| `actionAjaxDieCartController` | Wykonywany przed odpowiedzią AJAX z CartController. | Pozwala modułowi przechwytywać i modyfikować odpowiedzi AJAX, wstrzykując niestandardowe komunikaty o błędach, jeśli limity zostaną przekroczone podczas aktualizacji koszyka AJAX. |
| `actionFrontControllerSetMedia` | Wykonywany przed renderowaniem wyjścia przez kontroler front-office. | Używany do rejestrowania plików CSS i JavaScript front-office. |

## 5. Oficjalne Wsparcie i Aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Maksymalna wartość zakupu według kategorii”, zaloguj się na swoje konto klienta pod adresem [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub integracji modułu.
"""
