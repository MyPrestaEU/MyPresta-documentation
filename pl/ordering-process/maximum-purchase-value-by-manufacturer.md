---
title: "Maksymalna wartość zakupu według producenta - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Maksymalna wartość zakupu według producenta” od MyPresta.eu."
sidebar:
  label: "Maksymalna wartość zakupu według producenta - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Maximum purchase value by manufacturer na MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-manufacturer.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/maximum-purchase-value-by-manufacturer/)
>
> ---


# Maksymalna wartość zakupu według producenta

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym można włączyć lub wyłączyć moduł oraz uzyskać dostęp do dedykowanego obszaru zarządzania do ustawiania limitów producentów.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera prosty przełącznik do włączania lub wyłączania podstawowej funkcjonalności modułu. Zapewnia również bezpośredni link do dedykowanego ekranu, na którym definiujesz rzeczywiste maksymalne wartości zakupu dla producentów.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączony:* Moduł będzie aktywnie sprawdzał koszyki klientów pod kątem zdefiniowanych limitów producentów i zapobiegał zamówieniom, jeśli limity zostaną przekroczone.
    *   *Gdy wyłączony:* Moduł przestanie działać, a żadne limity zakupu producenta nie będą egzekwowane.
-   **Zalecana wartość:** „TAK” (Włączony), jeśli zamierzasz korzystać z funkcji modułu.
-   **Scenariusz/przykład sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz zacząć ustawiać limity. Włączysz go tutaj, a następnie przejdziesz do sekcji „Zarządzaj limitami producentów”.

### 2.2 Dedykowany ekran administracyjny: Limity producentów (Panel administracyjny > Moduły > Maksymalna wartość zakupu według producenta > Konfiguruj > Przycisk „Zarządzaj limitami producentów” lub dedykowany wpis w menu)

Ten ekran służy do definiowania i zarządzania rzeczywistymi maksymalnymi wartościami zakupu dla każdego producenta. Zazwyczaj przedstawia listę producentów i umożliwia dodawanie, edytowanie lub usuwanie reguł.

**Nazwa ekranu i lokalizacja w menu:**
Dostęp do tego ekranu uzyskasz, klikając przycisk „Konfiguruj” obok modułu w Menedżerze modułów, a następnie prawdopodobnie klikając widoczny przycisk, taki jak „Zarządzaj limitami producentów” lub „Dodaj nową regułę”. Alternatywnie, moduł może utworzyć nową pozycję menu w „Katalogu” lub „Parametrach sklepu” dla bezpośredniego dostępu do `AdminMaobm`.

**Dostępne akcje i ustawienia:**

1.  **Tabela listy istniejących reguł:**

    *   Zobaczysz tabelę zawierającą wszystkie ustawione już limity producentów.
    *   Kolumny zazwyczaj obejmują: Nazwa producenta, Maksymalna wartość oraz akcje takie jak „Edytuj” lub „Usuń”.
    *   **Efekt zmian:** Ta tabela przedstawia przegląd aktywnych reguł. Usunięcie reguły spowoduje usunięcie limitu zakupu dla tego konkretnego producenta.
    *   **Zalecany przepływ pracy:** Regularnie przeglądaj tę tabelę, aby upewnić się, że Twoje limity są zgodne z bieżącymi potrzebami biznesowymi.
2.  **Formularz dodawania/edycji reguły:**

    *   Po kliknięciu „Dodaj nową” lub „Edytuj” istniejącą regułę, zazwyczaj zobaczysz formularz z następującymi polami:
        *   **Producent:** Lista rozwijana lub pole wyszukiwania do wyboru producenta, dla którego chcesz zastosować limit.
            *   **Co robi to ustawienie:** Określa, którego producenta dotyczy ta reguła.
            *   **Efekt zmiany tego ustawienia:** Reguła będzie dotyczyć tylko produktów powiązanych z wybranym producentem.
            *   **Zalecana wartość:** Wybierz konkretnego producenta, którego chcesz ograniczyć.
            *   **Scenariusz/przykład sprzedawcy:** Chcesz ustawić limit dla produktów „Acme Corp.”, więc wybierasz „Acme Corp.” z listy.
        *   **Maksymalna wartość zakupu:** Pole wprowadzania, w którym wprowadzasz maksymalną całkowitą wartość (w domyślnej walucie Twojego sklepu), jaką klient może kupić od wybranego producenta w jednym zamówieniu.
            *   **Co robi to ustawienie:** Definiuje pułap monetarny dla produktów od wybranego producenta.
            *   **Efekt zmiany tego ustawienia:** Jeśli całkowita wartość produktów od tego producenta w koszyku klienta przekroczy tę liczbę, zostanie mu zablokowane złożenie zamówienia.
            *   **Zalecana wartość:** Wartość numeryczna reprezentująca maksymalną dozwoloną sumę, np. „500.00” dla 500 jednostek Twojej domyślnej waluty.
            *   **Scenariusz/przykład sprzedawcy:** Chcesz ograniczyć produkty „Acme Corp.” do maksymalnie 500 USD za zamówienie. Wprowadziłbyś tutaj „500”.
        *   **Przycisk Zapisz:** Aby zastosować zmiany.
            *   **Efekt zmian:** Zapisuje nową regułę lub aktualizuje istniejącą w bazie danych, czyniąc ją natychmiast aktywną.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

-   **Początkowa konfiguracja:** Przejrzyj listę producentów i zidentyfikuj tych, dla których musisz ustawić limity zakupu. Dodaj nową regułę dla każdego z nich.
-   **Monitorowanie:** Obserwuj swoją sprzedaż i zapasy. Jeśli zauważysz, że produkty danego producenta są kupowane w nadmiernych ilościach, lub jeśli zmienią się umowy z dostawcami, wróć do tego ekranu, aby dostosować lub dodać nowe limity.
-   **Aktualizacje:** Gdy do Twojego sklepu zostaną dodani nowi producenci, rozważ, czy wymagają oni reguły limitu zakupu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Status modułu (Włącz/Wyłącz) | Włączony | Aktywuje lub dezaktywuje funkcjonalność modułu. |
| AdminMaobmController (Limity producentów) | Producent | Wybierz z listy | Określa producenta, którego dotyczy limit. |
| AdminMaobmController (Limity producentów) | Maksymalna wartość zakupu | Pożądany limit monetarny (np. 500.00) | Ustawia maksymalną całkowitą wartość produktów od wybranego producenta w jednym zamówieniu. Przekroczenie tego blokuje realizację zamówienia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Klient próbuje zrealizować zamówienie, ale widzi komunikat o przekroczeniu limitu producenta. Co powinienem zrobić?**
O: Oznacza to, że moduł działa zgodnie z przeznaczeniem. Klient ma w koszyku zbyt wiele produktów od konkretnego producenta, a całkowita wartość tych produktów przekracza ustawiony limit. Możesz:
1.  Poradzić klientowi, aby zmniejszył ilość produktów od tego producenta.
2.  Tymczasowo wyłączyć lub dostosować limit dla tego producenta w konfiguracji modułu, jeśli uznasz zamówienie za akceptowalne (ale bądź ostrożny).

**P: Ustawiłem limit, ale wydaje się, że nie działa. Klienci nadal mogą zamawiać więcej niż maksimum.**
O:
1.  **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów** i na jego głównej stronie konfiguracji.
2.  **Zweryfikuj regułę:** Dokładnie sprawdź regułę, którą utworzyłeś na ekranie „Zarządzaj limitami producentów”. Czy wybrano prawidłowego producenta? Czy „Maksymalna wartość zakupu” jest ustawiona prawidłowo?
3.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
4.  **Producent produktu:** Upewnij się, że dane produkty są prawidłowo przypisane do producenta, dla którego ustawiłeś limit. Sprawdź ustawienia produktu w swoim katalogu.

**P: Czy mogę ustawić różne limity dla różnych grup klientów?**
O: Ten moduł, w swojej standardowej formie, stosuje jeden limit na producenta dla wszystkich klientów. Jeśli potrzebujesz limitów specyficznych dla grup klientów, wymagałoby to niestandardowego rozwoju.

**P: Komunikat ostrzegawczy jest niejasny lub nie pasuje do języka/motywu mojego sklepu.**
O:
1.  **Tłumaczenia:** Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, swój motyw i moduł „Maksymalna wartość zakupu według producenta”. Możesz tam dostosować tekst komunikatu ostrzegawczego.
2.  **Stylizacja motywu:** Moduł używa standardowej stylizacji PrestaShop dla swoich komunikatów. Jeśli wygląda nie na miejscu, Twój motyw może mieć niestandardowy CSS, który wymaga dostosowania. Webmaster może sprawdzić plik `maobm.css` i CSS Twojego motywu, aby zapewnić spójność wizualną.

**P: Co się stanie, jeśli produkt nie ma przypisanego producenta?**
O: Produkty bez przypisanego producenta nie będą podlegać żadnym limitom ustawionym przez ten moduł, ponieważ reguły są specyficzne dla producenta.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Maksymalna wartość zakupu według producenta” (`maobm`) jest zgodny ze standardową architekturą modułów PrestaShop. Wykorzystuje głównie klasę `Module` do instalacji i podstawowej konfiguracji, `AdminController` do zarządzania limitami producentów oraz `FrontController` do obsługi żądań AJAX i integracji z procesem koszyka w front-office. Moduł wykorzystuje system hooków PrestaShop do wstrzykiwania swojej logiki do przepływu koszyka i realizacji zamówienia, zapobiegając zamówieniom, jeśli limity zostaną przekroczone. Przechowuje swoją konfigurację w `ps_configuration` i zarządza specyficznymi limitami producentów za pośrednictwem dedykowanej tabeli bazy danych (chociaż nie ma wyraźnie wymienionego `ObjectModel`, co sugeruje bezpośrednią interakcję z bazą danych lub prosty `AdminController` zarządzający konfiguracją).

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa klasy**: `MaobmAjaxModuleFrontController` (domyślna, rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Ten kontroler prawdopodobnie obsługuje żądania AJAX z front-office, takie jak aktualizacja koszyka przez klienta. Ponownie ocenia limity producentów i zwraca odpowiedź (np. komunikat ostrzegawczy lub status wskazujący, czy zamówienie może być kontynuowane). Może być podłączony do `actionCartSave` lub podobnych zdarzeń, aby zapewnić informacje zwrotne w czasie rzeczywistym.
    -   `controllers/front/index.php`
        -   **Nazwa klasy**: `MaobmIndexModuleFrontController` (domyślna, rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Ten kontroler może służyć jako rezerwowy lub prosty punkt wejścia, chociaż jego główna funkcja może być minimalna, jeśli `ajax.php` obsługuje większość interakcji front-endowych. Może potencjalnie wyświetlać ogólny komunikat lub przekierowywać, jeśli jest dostępny bezpośrednio.
-   **Kontrolery Back-Office Admin**:

    -   `controllers/admin/AdminMaobm.php`
        -   **Nazwa klasy**: `AdminMaobmController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki**: Prawdopodobnie niestandardowa zakładka utworzona przez moduł lub dostępna za pośrednictwem strony konfiguracji modułu.
        -   **Zarządzana encja**: Zarządza specyficznymi regułami limitów producentów. Zapewnia interfejs do wyświetlania, dodawania, edytowania i usuwania tych reguł. Ten kontroler będzie bezpośrednio współpracował z bazą danych w celu przechowywania i pobierania identyfikatorów producentów i ich powiązanych maksymalnych wartości. Zazwyczaj używałby `HelperList` dla tabeli przeglądu i `HelperForm` dla formularza dodawania/edycji.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy**: `AdminMaobmIndexController` (domyślna, rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność**: Podobnie jak `index.php` w front-office, może to być symbol zastępczy lub proste przekierowanie. W PrestaShop pliki `index.php` w katalogach kontrolerów często służą jako środki bezpieczeństwa, aby zapobiec bezpośredniemu listowaniu katalogów.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczony spis nie wskazuje na żadne niestandardowe klasy w katalogu `classes/`. Sugeruje to, że moduł:

1.  Bezpośrednio manipuluje tabelami bazy danych (np. `ps_maobm_limits`) za pomocą `Db::getInstance()` w swoich kontrolerach lub głównym pliku modułu.
2.  Przechowuje całą konfigurację w `ps_configuration` za pomocą `Configuration::updateValue()`, a `AdminMaobmController` zarządza tymi wpisami konfiguracji.
    Biorąc pod uwagę funkcję „nieograniczonej liczby reguł”, bardziej prawdopodobna jest bezpośrednia interakcja z bazą danych dla niestandardowej tabeli niż `ps_configuration` do przechowywania wielu limitów producentów.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/maobm.js`
    -   **Zakres**: Prawdopodobnie Front-office.
    -   **Szczegóły**: Ten skrypt byłby odpowiedzialny za interakcje po stronie klienta związane z funkcjonalnością modułu. Może:
        -   Wiązać słuchaczy zdarzeń z akcjami aktualizacji koszyka (np. zmiany ilości, usunięcie produktu).
        -   Wykonywać wywołania AJAX do `controllers/front/ajax.php` w celu ponownej oceny limitów producentów w czasie rzeczywistym bez pełnego przeładowania strony.
        -   Wyświetlać komunikaty ostrzegawcze lub wyłączać przycisk realizacji zamówienia, jeśli limity zostaną przekroczone, na podstawie odpowiedzi AJAX.
        -   Potencjalnie integrować się ze zdarzeniami `prestashop.on` PrestaShop dla lepszej kompatybilności.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `views/css/maobm.css`
    -   **Zakres**: Głównie Front-office, możliwe, że niektóre style Back-office dla niestandardowych elementów.
    -   **Szczegóły**: Ten arkusz stylów zawierałby niezbędne reguły CSS do stylizacji komunikatów ostrzegawczych wyświetlanych klientowi w koszyku lub podczas realizacji zamówienia. Może definiować klasy dla:
        -   `#maobm-warning-message` lub podobnych kontenerów dla tekstu błędu.
        -   Stylizacji wyłączonych przycisków realizacji zamówienia.
        -   Zapewnienia responsywności na różnych rozmiarach ekranu.
    -   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać**: Szukaj klas takich jak `.maobm-alert`, `.maobm-error-message` lub konkretnych identyfikatorów używanych dla kontenera ostrzeżeń.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Hook**: Ten szablon jest prawdopodobnie renderowany w hooku, który pojawia się na stronie koszyka, takim jak `displayShoppingCartFooter` lub `displayShoppingCart`.
        -   **Wyjście**: Byłby odpowiedzialny za wyświetlanie komunikatu ostrzegawczego klientowi, jeśli przekroczy limit zakupu producenta. Otrzymywałby zmienne z modułu wskazujące, czy limit został przekroczony i odpowiedni komunikat do wyświetlenia.
-   **Szablony administracyjne (`views/templates/admin/`)**: (Nie wymienione wyraźnie, ale sugerowane przez `AdminMaobmController`)

    -   `AdminMaobmController` zazwyczaj używałby szablonów `HelperList` i `HelperForm` PrestaShop dla swojego interfejsu, ale może mieć niestandardowe pliki `.tpl` dla konkretnych części swojej konfiguracji lub do wyświetlania listy reguł. Zazwyczaj znajdowałyby się one w `views/templates/admin/maobm/` lub podobnym miejscu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_maobm_limits` (Sugerowane): Niestandardowa tabela do przechowywania limitów producentów.
        -   `id_maobm_limit` (Klucz podstawowy, AUTO\_INCREMENT)
        -   `id_manufacturer` (Klucz obcy do `ps_manufacturer.id_manufacturer`)
        -   `max_value` (Dziesiętne lub zmiennoprzecinkowe, przechowujące maksymalną dozwoloną wartość zakupu)
        -   `date_add`, `date_upd` (Standardowe znaczniki czasu PrestaShop)
    -   `ps_configuration`: Moduł może przechowywać ogólne ustawienia (takie jak status włączenia/wyłączenia modułu) tutaj.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Aby dołączyć zasoby `maobm.css` i `maobm.js`. |
| `displayShoppingCart` lub `displayShoppingCartFooter` | Renderuje zawartość na stronie koszyka. | Aby wyświetlić komunikat ostrzegawczy (`displayShoppingCart.tpl`), jeśli limity zostaną przekroczone. |
| `actionCartSave` | Wykonywane po zapisaniu lub zaktualizowaniu koszyka. | Aby ponownie ocenić limity producentów i potencjalnie zaktualizować status koszyka lub wyświetlić komunikaty. |
| `actionValidateOrder` | Wykonywane przed oficjalnym zatwierdzeniem zamówienia. | **KRYTYCZNE**: Aby wykonać ostateczne sprawdzenie limitów producentów i zapobiec zatwierdzeniu zamówienia, jeśli limity zostaną przekroczone. To tutaj znajdowałaby się logika blokowania zamówienia. |
| `displayAdminProductsExtra` (lub podobne) | Może być używane do wyświetlania informacji o limitach producenta bezpośrednio na stronie edycji produktu w BO. | (Opcjonalnie) Aby zapewnić szybki dostęp do informacji o limitach dla producenta produktu. |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` wszystkich stron back-office. | Aby dołączyć CSS/JS specyficzne dla back-office dla `AdminMaobmController`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Maksymalna wartość zakupu według producenta”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
