---
title: "Minimalna wartość zamówienia według kategorii - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Minimalna wartość zamówienia według kategorii” od MyPresta.eu."
sidebar:
  label: "Minimalna wartość zamówienia według kategorii - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Minimal order value by category na MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-category.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/minimal-order-value-by-category/)
>
> ---


# Minimalna wartość zamówienia według kategorii

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne domyślnie w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

-   **Co robi to ustawienie:** Ten ekran służy przede wszystkim jako punkt wejścia. Chociaż podstawowa logika modułu jest zarządzana za pośrednictwem dedykowanego ekranu administracyjnego, ta początkowa strona konfiguracji zapewnia, że moduł jest poprawnie zainstalowany i zawiera link lub przekierowanie do głównego interfejsu zarządzania.
-   **Wpływ zmiany tego ustawienia:** Zazwyczaj ten ekran nie ma bezpośrednich przełączników ani pól wprowadzania dla sprzedawcy. Jego głównym celem jest potwierdzenie statusu modułu i poprowadzenie Cię do następnego kroku.
-   **Zalecana wartość:** Brak bezpośrednich wartości do ustawienia tutaj. Po prostu upewnij się, że moduł jest włączony.
-   **Scenariusz / przykład dla sprzedawcy:** Po zainstalowaniu wylądujesz tutaj. Możesz zobaczyć komunikat potwierdzający instalację i przycisk lub link do „Zarządzaj minimalnymi wartościami zamówień” lub podobny, który przeniesie Cię do dedykowanego ekranu `AdminMobcController`.

### 2.2 Dedykowany ekran administracyjny: Zarządzanie minimalną wartością zamówienia według kategorii (Panel administracyjny > Moduły > Minimalna wartość zamówienia według kategorii)

Jest to główny interfejs zarządzania, w którym definiujesz i kontrolujesz wszystkie minimalne wartości zamówień specyficzne dla kategorii. Zazwyczaj znajdziesz nową pozycję menu pod „Moduły” lub „Katalog” (w zależności od wersji PrestaShop i hooka modułu) o nazwie „Minimalna wartość zamówienia według kategorii” lub podobnej.

**Nazwa ekranu i lokalizacja w menu:**
Ten ekran znajdziesz, przechodząc do **Moduły > Minimalna wartość zamówienia według kategorii** w menu Panelu administracyjnego PrestaShop.

**Dostępne działania i ustawienia:**
Ten ekran przedstawia listę (siatkę) wszystkich aktualnie zdefiniowanych reguł minimalnej wartości zamówienia. Dla każdej reguły zazwyczaj zobaczysz:

-   **Nazwa kategorii:** Nazwa kategorii PrestaShop, do której ma zastosowanie reguła.
-   **Wartość minimalna:** Wymagana minimalna kwota zamówienia dla produktów w tej kategorii.
-   **Waluta:** Waluta, w której ustawiona jest wartość minimalna (zazwyczaj domyślna waluta Twojego sklepu, np. USD, EUR).
-   **Działania:** Przyciski „Edytuj” lub „Usuń” istniejącą regułę.

Znajdziesz również przycisk, zazwyczaj w prawym górnym rogu, **„Dodaj nową regułę”** lub **„Dodaj nową minimalną wartość zamówienia”**. Kliknięcie go otworzy formularz, w którym możesz:

1.  **Wybierz kategorię:**

    -   **Co robi to ustawienie:** Pozwala wybrać, do której istniejącej kategorii PrestaShop będzie miała zastosowanie ta reguła minimalnej wartości zamówienia.
    -   **Wpływ zmiany tego ustawienia:** Wybranie kategorii łączy regułę ze wszystkimi produktami w tej kategorii (i jej podkategoriach, w zależności od logiki modułu).
    -   **Zalecana wartość:** Wybierz konkretną kategorię, do której chcesz zastosować minimalną wartość zamówienia.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz ustawić minimum dla swojej kategorii „Hurt”. Wybierzesz „Hurt” z listy rozwijanej.
2.  **Minimalna wartość zamówienia:**

    -   **Co robi to ustawienie:** Definiuje kwotę pieniężną, którą klienci muszą wydać na produkty *w wybranej kategorii*, zanim będą mogli kontynuować zamówienie.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy ustawiona jest wartość (np. 50.00):* Klienci muszą mieć w koszyku produkty z wybranej kategorii o wartości co najmniej 50.00 jednostek Twojej domyślnej waluty. W przeciwnym razie zostaną zablokowani przy kasie z komunikatem.
        -   *Gdy pozostawiona pusta lub ustawiona na 0:* Ta reguła byłaby faktycznie wyłączona dla kategorii, dopuszczając dowolną wartość. Jednak najlepiej jest usunąć regułę, jeśli jej nie potrzebujesz.
    -   **Zalecana wartość:** Dodatnia wartość liczbowa odzwierciedlająca pożądane minimum (np. `25.00`, `100.00`).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla Twojej kategorii „Hurt” ustawiasz to na `100.00`. Klient z produktami hurtowymi o wartości 90 USD nie może dokonać zakupu, dopóki nie doda kolejnych 10 USD.
3.  **Przycisk Zapisz:**

    -   **Co robi:** Stosuje zmiany lub tworzy nową regułę.
    -   **Efekt:** Nowa reguła będzie aktywna natychmiast, a system zacznie egzekwować minimalną wartość zamówienia dla wybranej kategorii.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Przejrzyj istniejące reguły:** Okresowo sprawdzaj listę reguł, aby upewnić się, że nadal są one zgodne z Twoją strategią biznesową.
2.  **Dodaj nowe reguły:** Jeśli wprowadzasz nowe kategorie produktów, które wymagają określonych minimów (np. nowa linia B2B), dodaj dla nich regułę.
3.  **Edytuj istniejące reguły:** Dostosuj wartości minimalne w oparciu o zmiany cen produktów, warunki rynkowe lub strategie promocyjne.
4.  **Usuń przestarzałe reguły:** Usuń reguły dla kategorii, które nie wymagają już minimum lub zostały wycofane.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | (Brak bezpośrednich ustawień) | N/A | Punkt wejścia do modułu; potwierdza instalację i kieruje do ekranu zarządzania. |
| Zarządzanie minimalną wartością zamówienia według kategorii | Dodaj nową regułę / Edytuj regułę > Wybierz kategorię | N/A | Łączy minimalną wartość zamówienia z konkretną kategorią produktów PrestaShop. |
| Zarządzanie minimalną wartością zamówienia według kategorii | Dodaj nową regułę / Edytuj regułę > Minimalna wartość zamówienia | Twoje pożądane minimum (np. `50.00`) | Ustawia wymaganą kwotę pieniężną dla produktów w wybranej kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem minimalną wartość, ale to nie działa. Klienci nadal mogą dokonać zakupu za mniej.**
O:

-   **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**.
-   **Zweryfikuj konfigurację reguły:** Przejdź do **Moduły > Minimalna wartość zamówienia według kategorii** i upewnij się, że reguła dla konkretnej kategorii jest aktywna, ma wartość większą niż zero i jest poprawnie przypisana do zamierzonej kategorii.
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
-   **Przypisanie kategorii produktu:** Sprawdź dokładnie, czy dane produkty są rzeczywiście przypisane do kategorii, dla której ustawiłeś minimum.

**P2: Wyświetlany komunikat dla klientów jest niejasny lub nie pasuje do języka mojego sklepu.**
O:

-   **Tłumaczenia modułu:** Moduł powinien obsługiwać system tłumaczeń PrestaShop. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz „Minimalna wartość zamówienia według kategorii”. Możesz wtedy dostosować komunikaty ostrzegawcze, aby były bardziej szczegółowe lub przetłumaczyć je na inne języki.
-   **Niestandardowe style szablonu:** Jeśli komunikat się pojawia, ale wygląda nie na miejscu, CSS Twojego szablonu może nadpisywać style modułu. Webmaster może pomóc dostosować plik `mobc.css` lub dodać niestandardowy CSS do Twojego szablonu, aby zapewnić prawidłowe wyświetlanie.

**P3: Czy mogę ustawić różne minima dla różnych grup klientów (np. detalicznych vs. hurtowych)?**
O: Obecna wersja modułu „Minimalna wartość zamówienia według kategorii” koncentruje się na minimach dla całej kategorii, a nie na minimach specyficznych dla grup klientów. Jeśli potrzebujesz tej zaawansowanej funkcjonalności, być może będziesz musiał użyć oddzielnych kategorii dla różnych grup klientów (np. „Produkty hurtowe” vs. „Produkty detaliczne”) i zastosować reguły do tych odrębnych kategorii.

**P4: Co się stanie, jeśli produkt znajduje się w wielu kategoriach, a tylko jedna ma minimum?**
O: Moduł oblicza całkowitą wartość produktów w *każdej* kategorii, która ma regułę minimum. Jeśli produkt znajduje się w Kategorii A (bez minimum) i Kategorii B (minimum 50 USD), jego wartość zostanie wliczona do sumy Kategorii B, jeśli zostanie dodany do koszyka. Klient musi spełnić minimum dla Kategorii B na podstawie sumy wszystkich produktów w jego koszyku, które należą do Kategorii B.

**P5: Usunąłem kategorię, ale reguła dla niej nadal wyświetla się w konfiguracji modułu.**
O: Jeśli usuniesz kategorię bezpośrednio z menu Katalog PrestaShop, reguła modułu związana z tą kategorią może stać się osierocona. Powinieneś ręcznie przejść do **Moduły > Minimalna wartość zamówienia według kategorii** i usunąć odpowiednią regułę z listy, aby zachować czystość konfiguracji.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Minimalna wartość zamówienia według kategorii” (`mobc`) stosuje standardowy wzorzec MVC PrestaShop. Rozszerza on głównie `Module` dla swojej podstawowej funkcjonalności i `AdminController` dla interfejsu zarządzania w panelu administracyjnym. Interakcje w front-office są obsługiwane za pośrednictwem `ModuleFrontController` dla żądań AJAX i renderowania szablonów. Moduł nie używa niestandardowych klas `ObjectModel`, ale opiera się na podstawowych encjach PrestaShop `Category` i `Product` do pobierania danych. Konfiguracja jest przechowywana w `ps_configuration` i niestandardowej tabeli bazy danych dla mapowań kategorii-wartości.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa klasy:** `MobcAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Obsługuje żądania AJAX z front-office, głównie w celu sprawdzenia zawartości koszyka pod kątem zdefiniowanych minimalnych wartości zamówień według kategorii. Prawdopodobnie otrzymuje dane koszyka i zwraca odpowiedź JSON wskazującą, czy minima są spełnione, a jeśli nie, które kategorie są niewystarczające i o ile. Jest to kluczowe dla walidacji w czasie rzeczywistym na stronie koszyka bez pełnego przeładowania strony.
    -   `controllers/front/index.php`
        -   **Nazwa klasy:** `MobcIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Ten kontroler może służyć jako rezerwowy lub prosty punkt wejścia, ale biorąc pod uwagę funkcjonalność modułu, jego główna rola jest prawdopodobnie minimalna, być może przekierowuje lub wyświetla podstawową stronę, jeśli jest bezpośrednio dostępny. Podstawowa logika front-office jest oczekiwana w `ajax.php`.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminMobc.php`
        -   **Nazwa klasy:** `AdminMobcController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** Minimalna wartość zamówienia według kategorii (lub podobna, zazwyczaj pod „Moduły” lub „Katalog”).
        -   **Zarządzana encja:** Zarządza niestandardową encją `mobc`, która reprezentuje mapowania kategorii-minimalnej wartości.
        -   **Odpowiedzialność:** Zapewnia interfejs CRUD (Create, Read, Update, Delete) do zarządzania regułami minimalnej wartości zamówienia. Obsługuje listowanie istniejących reguł w siatce, wyświetlanie formularzy do dodawania/edycji reguł (wybieranie kategorii, wprowadzanie minimalnych wartości) i przetwarzanie przesłanych formularzy. Współpracuje z tabelą bazy danych modułu dla wpisów `mobc`.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy:** `AdminMobcIndexController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność:** Podobnie jak `index.php` w front-office, może to być symbol zastępczy lub prosty przekierowanie. Główna logika administracyjna znajduje się w `AdminMobc.php`.

### 4.3 Podstawowe klasy i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że obsługa danych modułu dla mapowań kategorii-wartości odbywa się bezpośrednio w `AdminMobcController` lub `index.php` (główny plik modułu) za pomocą `Db::getInstance()` lub poprzez rozszerzenie ogólnego `ObjectModel` w samym głównym pliku modułu bez tworzenia dedykowanego pliku klasy.

Biorąc pod uwagę, że `AdminMobcController` zarządza encją „mobc”, jest bardzo prawdopodobne, że `AdminMobcController` definiuje swoje `$this->object` i `$this->fields_list` bezpośrednio, lub istnieje niejawna definicja `ObjectModel` w głównym pliku `mobc.php`, którą kontroler wykorzystuje.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `mobc/views/js/mobc.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Ten skrypt jest kluczowy dla walidacji koszyka w czasie rzeczywistym. Prawdopodobnie:
        -   Wiąże słuchaczy zdarzeń ze zmianami ilości w koszyku, usuwaniem produktów lub ładowaniem stron na stronie koszyka.
        -   Wyzwala wywołania AJAX do `controllers/front/ajax.php` w celu wysłania bieżących danych koszyka.
        -   Odbiera odpowiedź JSON z kontrolera AJAX.
        -   Dynamicznie aktualizuje DOM na stronie koszyka, aby wyświetlać komunikaty ostrzegawcze, jeśli minima nie są spełnione.
        -   Wyłącza/włącza przycisk realizacji zamówienia na podstawie wyniku walidacji.
        -   Może zawierać logikę wyświetlania wyskakujących komunikatów lub podświetlania problematycznych kategorii.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `mobc/views/css/mobc.css`
    -   **Zakres:** Stylizacja klienta w front-office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów jest odpowiedzialny za wizualną prezentację komunikatów ostrzegawczych wyświetlanych na stronie koszyka. Zdefiniuje style dla:
        -   Kontenerów zawierających komunikaty ostrzegawcze (np. `div.mobc-warning-message`).
        -   Elementów tekstowych w ostrzeżeniach (np. `span.mobc-category-name`, `span.mobc-remaining-amount`).
        -   Potencjalnie stylizację dla wyłączonego przycisku realizacji zamówienia lub innych wskazówek wizualnych.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim szablonie:** Programiści mogą sprawdzić wygenerowany kod HTML na stronie koszyka, aby zidentyfikować konkretne nazwy klas (np. `.mobc-alert`, `.mobc-error-list`, `.mobc-checkout-blocked`) i nadpisać je w pliku `custom.css` lub `theme.css` swojego szablonu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `mobc/views/templates/front/displayShoppingCart.tpl`
        -   **Hook:** Ten szablon jest prawdopodobnie renderowany w hooku na stronie koszyka, takim jak `displayShoppingCartFooter` lub `displayShoppingCartExtraContent`.
        -   **Wyjście bloku wizualnego:** Wyświetla strukturę HTML dla komunikatów ostrzegawczych, które informują klientów o niespełnionych minimalnych wartościach zamówień dla kategorii. Ten szablon będzie zawierał symbole zastępcze dla nazw kategorii, wymaganych kwot i pozostałej potrzebnej kwoty, które są wypełniane przez JavaScript i kontroler AJAX.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_mobc_category_value` (lub podobna, na podstawie encji `AdminMobcController`): Ta niestandardowa tabela przechowuje mapowanie między identyfikatorami kategorii a ich odpowiednimi minimalnymi wartościami zamówień.
        -   `id_mobc_category_value` (Klucz podstawowy, INT)
        -   `id_category` (INT, Klucz obcy do `ps_category.id_category`)
        -   `min_value` (DECIMAL, przechowuje minimalną kwotę pieniężną)
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)
    -   `ps_configuration`: Standardowa tabela konfiguracji PrestaShop. Moduł może przechowywać tutaj swoje ogólne ustawienia (jeśli takie istnieją, choć żadne nie zostały wyraźnie wykryte), z prefiksem `MOBC_`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Aby dołączyć `mobc.css` i `mobc.js` dla funkcjonalności front-office. |
| `displayShoppingCart` | Na stronie koszyka, zazwyczaj przed lub po podsumowaniu koszyka. | Aby wyrenderować `displayShoppingCart.tpl` do wyświetlania komunikatów ostrzegawczych. |
| `actionCartSave` | Po zapisaniu koszyka (np. dodaniu/usunięciu produktu, zmianie ilości). | Aby wyzwolić logikę modułu w celu ponownej oceny minimów kategorii i potencjalnie zaktualizować status koszyka lub zmienne sesji. |
| `actionFrontControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler front-office, umożliwiając modułom dodawanie JS/CSS. | Aby zarejestrować pliki JavaScript i CSS specyficzne dla modułu dla front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler administracyjny. | Aby zarejestrować pliki JavaScript i CSS specyficzne dla modułu dla back-office (np. dla `AdminMobcController`). |
| `displayAdminProductsExtra` (lub podobny) | Na stronie edycji produktu w panelu administracyjnym. | Potencjalnie do wyświetlania informacji o minimach kategorii związanych z bieżącym produktem, choć nie zostało to wyraźnie potwierdzone w dossier. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Minimalna wartość zamówienia według kategorii”, prosimy o zapoznanie się z kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
