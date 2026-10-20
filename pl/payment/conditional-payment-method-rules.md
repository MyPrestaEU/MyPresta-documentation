---
title: "Zasady Warunkowych Metod Płatności - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop „Zasady Warunkowych Metod Płatności” od MyPresta.eu."
sidebar:
  label: "Zasady Warunkowych Metod Płatności - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Conditional Payment Method Rules na MyPresta.eu](https://mypresta.eu/modules/payment-process/conditional-payment-method-rules.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/conditional-payment-method-rules/)
>
> ---


# Zasady Warunkowych Metod Płatności

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każda grupa ustawień pogrupowana według ekranu)

Konfiguracja modułu jest zarządzana głównie za pośrednictwem dedykowanych ekranów administracyjnych, umożliwiających tworzenie i zarządzanie politykami metod płatności.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny punkt wejścia do modułu. Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do pulpitu nawigacyjnego lub ogólnej strony ustawień.

#### Ustawienia ogólne i pulpit nawigacyjny

Ten ekran przedstawia przegląd statusu modułu i szybki dostęp do kluczowych funkcji.

-   **Co robi ten ekran:** Wyświetla podsumowanie aktywnych polityk, ostatnich wpisów w dzienniku audytu oraz szybkie linki do zarządzania politykami lub przeglądania dziennika audytu. Jest to Twoje centrum monitorowania aktywności modułu.
-   **Wpływ zmiany ustawień:** Ten ekran przede wszystkim dostarcza informacji i nawigacji. Wszelkie zmiany, które tu wprowadzisz (np. włączenie/wyłączenie polityki), będą miały bezpośredni wpływ na sposób wyświetlania metod płatności podczas realizacji zamówienia.
-   **Zalecana wartość:** Obserwuj pulpit nawigacyjny pod kątem wszelkich konfliktów polityk lub nieoczekiwanych zachowań.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł wprowadza kilka nowych pozycji menu w sekcji „Płatność” w Twoim Panelu administracyjnym PrestaShop.

#### 2.2.1 Polityki Metod Płatności (Panel administracyjny > Płatność > Zasady Metod Płatności > Polityki)

Tutaj definiujesz i zarządzasz wszystkimi swoimi zasadami dotyczącymi wyświetlania lub ukrywania metod płatności.

-   **Nazwa ekranu i lokalizacja w menu:** **Płatność > Zasady Metod Płatności > Polityki**
-   **Dostępne działania i ustawienia:**

    -   **Lista polityk:** Tabela pokazująca wszystkie utworzone polityki, ich status (włączone/wyłączone) oraz metody płatności, na które wpływają.
    -   **Dodaj nową politykę:** Kliknij ten przycisk, aby utworzyć nową zasadę.
    -   **Edytuj/Usuń politykę:** Zarządzaj poszczególnymi politykami z listy.
    -   **Duplikuj politykę:** Szybko utwórz kopię istniejącej polityki, aby ją zmodyfikować.
    -   **Włącz/Wyłącz politykę:** Przełącz status aktywności polityki bez jej usuwania.
    -   **Importuj/Eksportuj polityki (JSON):** Twórz kopie zapasowe polityk lub przenoś je między sklepami.
-   **Tworzenie/Edytowanie polityki:**
    Podczas dodawania lub edytowania polityki skonfigurujesz kilka kluczowych aspektów:

    1.  **Nazwa polityki:**

        -   **Co robi to ustawienie:** Opisowa nazwa dla Twojej polityki (np. „Ukryj płatność za pobraniem dla zamówień międzynarodowych”).
        -   **Wpływ zmiany tego ustawienia:** Pomaga zidentyfikować politykę na liście.
        -   **Zalecana wartość:** Uczyń ją jasną i zwięzłą.
        -   **Scenariusz sprzedawcy:** Nazwanie polityki „Darmowa wysyłka tylko z PayPal” natychmiast mówi o jej celu.
    2.  **Status (Włączone/Wyłączone):**

        -   **Co robi to ustawienie:** Kontroluje, czy polityka jest aktywna i stosowana podczas realizacji zamówienia.
        -   **Wpływ zmiany tego ustawienia:**
            -   *Gdy włączone:* Zasady w ramach tej polityki zostaną ocenione i wpłyną na widoczność metody płatności.
            -   *Gdy wyłączone:* Polityka jest ignorowana, a jej zasady nie mają żadnego wpływu.
        -   **Zalecana wartość:** Włączaj polityki tylko wtedy, gdy masz pewność, że są poprawnie skonfigurowane.
        -   **Scenariusz sprzedawcy:** Możesz tymczasowo wyłączyć politykę podczas promocji lub jeśli rozwiązujesz problem.
    3.  **Dotknięte metody płatności:**

        -   **Co robi to ustawienie:** Wybierz, które konkretne metody płatności będzie kontrolować ta polityka.
        -   **Wpływ zmiany tego ustawienia:** Tylko wybrane metody płatności będą podlegać zasadom tej polityki.
        -   **Zalecana wartość:** Wybierz wszystkie metody płatności istotne dla tej polityki.
        -   **Scenariusz sprzedawcy:** Jeśli chcesz ukryć „Płatność za pobraniem” i „Przelew bankowy” w określonych warunkach, wybierzesz oba tutaj.
    4.  **Typ polityki (Pokaż/Ukryj):**

        -   **Co robi to ustawienie:** Określa, czy warunki polityki będą *pokazywać* wybrane metody płatności, czy je *ukrywać*.
        -   **Wpływ zmiany tego ustawienia:**
            -   *Gdy ustawione na „Pokaż”:* Wybrane metody płatności będą widoczne *tylko* wtedy, gdy WSZYSTKIE warunki w tej polityce zostaną spełnione. Jeśli warunki nie zostaną spełnione, są one ukryte.
            -   *Gdy ustawione na „Ukryj”:* Wybrane metody płatności zostaną ukryte, jeśli WSZYSTKIE warunki w tej polityce zostaną spełnione. Jeśli warunki nie zostaną spełnione, są one widoczne.
        -   **Zalecana wartość:** Wybierz na podstawie swojego głównego celu. „Ukryj” jest często łatwiejsze dla konkretnych ograniczeń, podczas gdy „Pokaż” jest dobre dla ekskluzywnych ofert.
        -   **Scenariusz sprzedawcy:**
            -   *Ukryj:* „Ukryj płatność za pobraniem, jeśli suma koszyka przekracza 500 USD.”
            -   *Pokaż:* „Pokaż ‘Plan ratalny’ TYLKO jeśli grupa klientów to ‘VIP’ ORAZ suma koszyka przekracza 1000 USD.”
    5.  **Kreator warunków:**

        -   **Co robi to ustawienie:** To jest rdzeń Twojej polityki. Budujesz złożone zasady, używając logiki „AND” i „OR” w oparciu o różne kryteria.
        -   **Wpływ zmiany tego ustawienia:** Zdefiniowane tutaj warunki określają, *kiedy* zostanie wyzwolona akcja „Pokaż” lub „Ukryj” polityki.
        -   **Dostępne warunki (Przykłady):**
            -   **Suma koszyka:** Na podstawie całkowitej wartości koszyka klienta.
            -   **Grupa klientów:** Na podstawie grupy, do której należy klient (np. Gość, Klient, VIP, Hurtownik).
            -   **Kraj:** Na podstawie kraju wysyłki lub rozliczenia klienta.
            -   **Przewoźnik:** Na podstawie wybranego przewoźnika.
            -   **Produkty w koszyku:** Na podstawie konkretnych produktów, kategorii, producentów lub dostawców w koszyku.
            -   **Waluta:** Na podstawie waluty użytej do zamówienia.
            -   **Waga:** Na podstawie całkowitej wagi koszyka.
            -   **Data/Godzina:** Na podstawie konkretnych dat lub godzin (np. dla promocji).
            -   **Sklep:** Dla konfiguracji wielu sklepów.
        -   **Zalecana wartość:** Zacznij od prostych warunków i dokładnie przetestuj. Użyj „AND” dla bardziej rygorystycznych wymagań i „OR” dla szerszego zastosowania.
        -   **Scenariusz sprzedawcy:**
            -   „Ukryj PayPal, jeśli (Kraj JEST ‘USA’ ORAZ Suma koszyka JEST MNIEJSZA NIŻ 10 USD) LUB (Grupa klientów JEST ‘Hurtownik’).”
            -   „Pokaż Przelew bankowy, jeśli (Grupa klientów JEST ‘B2B’) ORAZ (Suma koszyka JEST WIĘKSZA NIŻ 1000 USD).”
    6.  **Komunikat o niedostępności:**

        -   **Co robi to ustawienie:** Niestandardowa wiadomość wyświetlana klientowi, jeśli metoda płatności jest ukryta przez tę politykę.
        -   **Wpływ zmiany tego ustawienia:** Zapewnia jasną komunikację z klientem, dlaczego opcja płatności jest niedostępna, zapobiegając zamieszaniu.
        -   **Zalecana wartość:** Zachowaj uprzejmy i informacyjny ton (np. „Płatność za pobraniem nie jest dostępna dla zamówień powyżej 500 USD. Proszę wybrać inną metodę płatności.”).
        -   **Scenariusz sprzedawcy:** „Ta metoda płatności jest dostępna tylko dla klientów VIP.” lub „Proszę wybrać inną metodę wysyłki, aby skorzystać z tej opcji płatności.”
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zidentyfikuj potrzebę:** „Chcę przestać oferować płatność za pobraniem dla zamówień powyżej 200 USD.”
    2.  **Utwórz nową politykę:** Nazwij ją „Limit płatności za pobraniem 200 USD”.
    3.  **Wybierz „Ukryj”** jako typ polityki.
    4.  **Wybierz „Płatność za pobraniem”** jako dotkniętą metodę płatności.
    5.  **Dodaj warunek:** „Suma koszyka JEST WIĘKSZA NIŻ 200 USD”.
    6.  **Dodaj komunikat o niedostępności:** „Płatność za pobraniem nie jest dostępna dla zamówień przekraczających 200 USD. Proszę wybrać inną metodę płatności.”
    7.  **Włącz i Zapisz.**
    8.  **Przetestuj za pomocą Symulatora** (patrz następna sekcja).

#### 2.2.2 Dziennik Audytu (Panel administracyjny > Płatność > Zasady Metod Płatności > Dziennik Audytu)

Ten ekran przedstawia szczegółową historię stosowania Twoich zasad płatności.

-   **Nazwa ekranu i lokalizacja w menu:** **Płatność > Zasady Metod Płatności > Dziennik Audytu**
-   **Dostępne działania i ustawienia:**
    -   **Lista logów:** Tabela pokazująca każde wystąpienie, w którym widoczność metody płatności została zmieniona przez politykę.
    -   **Szczegóły:** Wyświetl konkretne informacje o każdym wpisie w dzienniku, w tym klienta, szczegóły koszyka, ocenione polityki i ostateczny wynik (które metody płatności zostały pokazane/ukryte).
    -   **Filtrowanie:** Filtruj wpisy w dzienniku według daty, klienta, polityki lub metody płatności, aby szybko znaleźć konkretne zdarzenia.
-   **Wpływ zmian:** Ten ekran służy do przeglądania i audytowania. Nie możesz tu wprowadzać zmian, ale jest on nieoceniony do zrozumienia, dlaczego niektóre metody płatności zostały lub nie zostały pokazane klientowi.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj dziennik audytu, jeśli otrzymujesz zapytania od klientów dotyczące brakujących metod płatności lub jeśli podejrzewasz, że polityka nie działa zgodnie z oczekiwaniami. Jest to Twoje narzędzie do debugowania.

#### 2.2.3 Symulator (Panel administracyjny > Płatność > Zasady Metod Płatności > Symulator)

Symulator to potężne narzędzie do testowania polityk bez składania prawdziwego zamówienia.

-   **Nazwa ekranu i lokalizacja w menu:** **Płatność > Zasady Metod Płatności > Symulator**
-   **Dostępne działania i ustawienia:**
    -   **Pola wejściowe:** Wprowadź różne kryteria, takie jak grupa klientów, kraj, przewoźnik, suma koszyka, a nawet dodaj konkretne produkty do symulowanego koszyka.
    -   **Przycisk Symuluj:** Kliknij, aby zobaczyć, które metody płatności byłyby dostępne na podstawie wprowadzonych kryteriów i aktywnych polityk.
    -   **Wyświetlanie wyników:** Pokazuje listę dostępnych i niedostępnych metod płatności, wraz z powodami (które polityki spowodowały ich ukrycie/pokazanie).
-   **Wpływ zmian:** Ten ekran pozwala eksperymentować z różnymi scenariuszami i natychmiast zobaczyć wpływ Twoich polityk. Nie wpływa on na Twój działający sklep.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** *Zawsze* używaj symulatora po utworzeniu lub zmodyfikowaniu polityki. Testuj przypadki brzegowe i typowe scenariusze, aby upewnić się, że Twoje zasady działają dokładnie tak, jak zamierzasz, zanim zostaną uruchomione.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Polityki (Dodaj/Edytuj)** | Nazwa polityki | Opisowa nazwa | Wewnętrzna identyfikacja zasady. |
| | Status | Włączone | Aktywuje/dezaktywuje politykę. |
| | Dotknięte metody płatności | Wybierz odpowiednie metody | Określa, które bramki płatności kontroluje ta polityka. |
| | Typ polityki | Ukryj | Określa, czy warunki *ukrywają* czy *pokazują* wybrane metody. |
| | Kreator warunków | Zależy od zasady | Definiuje kryteria (np. suma koszyka, grupa klientów) dla zastosowania polityki. |
| | Komunikat o niedostępności | Jasny, informacyjny tekst | Wiadomość wyświetlana klientom, gdy metoda płatności jest ukryta. |
| **Dziennik Audytu** | Wpisy w dzienniku | N/A | Zapewnia historyczny zapis ocen polityk. |
| | Filtry | N/A | Pomaga wyszukiwać i analizować konkretne zdarzenia w dzienniku. |
| **Symulator** | Dane wejściowe symulacji | N/A | Umożliwia testowanie polityk w różnych scenariuszach klienta/koszyka. |
| | Wyniki symulacji | N/A | Pokazuje, które metody płatności byłyby dostępne/niedostępne dla symulowanego scenariusza. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Metoda płatności nie wyświetla się, ale nie mam żadnych polityk ustawionych na jej ukrywanie. Co jest nie tak?**
O: Najpierw sprawdź **Dziennik Audytu** modułu pod kątem wpisów związanych z tą metodą płatności i klientem. Dziennik powie Ci, czy polityka *ukryła* ją. Jeśli nie, problem może leżeć poza tym modułem:
\* Czy sama metoda płatności jest włączona w **Płatność > Metody płatności**?
\* Czy istnieją jakieś ograniczenia ustawione bezpośrednio w module płatności (np. ograniczenia kraju, waluty, grupy w konfiguracji samego modułu płatności)?
\* Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).

**P: Moje polityki wydają się nie działać. Co powinienem zrobić?**
O:
1.  **Sprawdź status polityki:** Upewnij się, że polityka jest „Włączona” na ekranie **Polityki**.
2.  **Użyj Symulatora:** Przejdź do **Płatność > Zasady Metod Płatności > Symulator** i wprowadź dokładnie te warunki, które testujesz. Zobacz, co przewiduje symulator. To najszybszy sposób na debugowanie warunków.
3.  **Przejrzyj warunki:** Dokładnie sprawdź swoją logikę „AND” i „OR”. Pojedynczy nieprawidłowy warunek może uniemożliwić uruchomienie całej polityki.
4.  **Sprawdź dotknięte metody płatności:** Upewnij się, że metoda płatności, której oczekujesz, że zostanie dotknięta, jest faktycznie wybrana w polityce.
5.  **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) po wprowadzeniu znaczących zmian w ustawieniach modułu lub politykach.

**P: Jak radzić sobie z wieloma politykami, które wpływają na tę samą metodę płatności?**
O: Moduł ocenia wszystkie aktywne polityki.
\* Jeśli wiele polityk „Ukryj” dotyczy tej samej metody płatności i *którakolwiek* z nich zostanie uruchomiona, metoda płatności zostanie ukryta.
\* Jeśli wiele polityk „Pokaż” dotyczy tej samej metody płatności i *którakolwiek* z nich zostanie uruchomiona, metoda płatności zostanie pokazana.
\* **Rozwiązywanie konfliktów:** Jeśli jedna polityka mówi „Pokaż”, a inna „Ukryj” dla tej samej metody płatności w tych samych warunkach, moduł ma zdefiniowaną strategię łączenia (zazwyczaj „Ukryj” ma pierwszeństwo, aby zapewnić bezpieczeństwo i zapobiec niezamierzonej dostępności). Użyj **Symulatora** i **Dziennika Audytu**, aby zrozumieć dokładny wynik sprzecznych polityk.

**P: Czy mogę przetłumaczyć „Komunikat o niedostępności” na różne języki?**
O: Tak, podczas edytowania polityki pole „Komunikat o niedostępności” będzie zazwyczaj miało obok siebie selektor języka (ikonę flagi). Kliknij flagę, aby wprowadzić tłumaczenia dla każdego języka włączonego w Twoim sklepie.

**P: Mój niestandardowy motyw nie wyświetla poprawnie komunikatów o niedostępności. Co mogę zrobić?**
O: Zazwyczaj wskazuje to na konflikt CSS lub brakujące nadpisanie szablonu w Twoim motywie.
\* **Sprawdź `front.css`:** Moduł zawiera własny `front.css` do podstawowego stylizowania. Twój motyw może go nadpisywać.
\* **Zbadaj element:** Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać obszar, w którym wiadomość powinna się pojawić. Poszukaj reguł CSS, które mogą ją ukrywać lub źle pozycjonować.
\* **Skontaktuj się z deweloperem motywu:** Jeśli nie czujesz się komfortowo z CSS, skontaktuj się z deweloperem motywu lub ekspertem PrestaShop w celu uzyskania pomocy. Mogą oni pomóc w integracji stylów modułu z Twoim motywem.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Zasady Warunkowych Metod Płatności wykorzystuje solidny, obiektowy wzorzec projektowy w ramach struktury PrestaShop MVC. Intensywnie wykorzystuje `ObjectModel` do zarządzania politykami i dziennikami audytu, dedykowaną strukturę `ConditionTree` do złożonej oceny reguł oraz `PaymethodrulesEngine` do stosowania tych reguł na etapie realizacji zamówienia. Moduł wstrzykuje swoją logikę głównie za pośrednictwem hooków, w szczególności `actionPaymentOptionsModifier` (lub podobnych dla starszych wersji PS) w celu manipulowania listą dostępnych metod płatności. Kontrolery administracyjne zapewniają bogaty interfejs użytkownika do zarządzania politykami, symulacji i audytu.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/index.php`
    -   **Nazwa klasy:** `PaymethodrulesIndexModuleFrontController` (lub podobna, zazwyczaj rozszerzająca `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler może służyć jako rezerwowy lub prosty punkt wejścia, ale podstawowa logika modyfikacji metody płatności jest zazwyczaj obsługiwana za pośrednictwem hooków. Może być używany do specyficznych żądań AJAX związanych z oceną reguł front-office, jeśli jest to potrzebne, chociaż główna ocena odbywa się podczas renderowania opcji płatności.
-   `controllers/front/simulate.php`
    -   **Nazwa klasy:** `PaymethodrulesSimulateModuleFrontController` (lub podobna, rozszerzająca `ModuleFrontController`)
    -   **Odpowiedzialność:** Chociaż główny symulator znajduje się w BO, kontroler frontowy może istnieć dla uproszczonej symulacji front-end lub do udostępniania wyników symulacji za pośrednictwem AJAX w celach debugowania.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminPaymethodrulesAuditLog.php`
    -   **Nazwa klasy:** `AdminPaymethodrulesAuditLogController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Zasady Metod Płatności -> Dziennik Audytu
    -   **Zarządzana encja:** `PaymethodrulesAuditLog` (mapowana na tabelę `ps_paymethodrules_log`)
    -   **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem wpisów w dzienniku audytu. Wykorzystuje `HelperList` do renderowania widoku siatki i udostępnia akcje do przeglądania szczegółów dziennika.
-   `controllers/admin/AdminPaymethodrulesPolicies.php`
    -   **Nazwa klasy:** `AdminPaymethodrulesPoliciesController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Zasady Metod Płatności -> Polityki
    -   **Zarządzana encja:** `PaymethodrulesPolicy` (mapowana na tabelę `ps_paymethodrules_policy`)
    -   **Odpowiedzialność:** Jest to centralny kontroler do zarządzania politykami płatności. Obsługuje:
        -   Wyświetlanie polityk za pomocą `HelperList`.
        -   Dodawanie/edycję polityk za pomocą `HelperForm` ze złożonym renderowaniem pól dla kreatora warunków.
        -   Włączanie/wyłączanie, duplikowanie i usuwanie polityk.
        -   Obsługę importu/eksportu polityk w formacie JSON.
-   `controllers/admin/index.php`
    -   **Nazwa klasy:** `AdminPaymethodrulesDashboardController` (lub podobna, rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Zasady Metod Płatności -> Pulpit nawigacyjny (lub główny link konfiguracji modułu)
    -   **Zarządzana encja:** N/A (widok pulpitu nawigacyjnego)
    -   **Odpowiedzialność:** Zapewnia główny punkt wejścia i widok pulpitu nawigacyjnego dla modułu w Panelu administracyjnym. Agreguje informacje z innych kontrolerów (np. liczbę polityk, ostatnie wpisy w dzienniku) i zapewnia nawigację. Zazwyczaj używa szablonów Smarty do renderowania widżetów pulpitu nawigacyjnego.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/index.php`: Standardowy pusty plik zapobiegający listowaniu katalogów.
-   `classes/PaymethodrulesAdmin.php`: Prawdopodobnie klasa pomocnicza dla wspólnych funkcji związanych z administracją, takich jak rejestracja menu, zarządzanie zakładkami lub współdzielona logika renderowania formularzy.
-   `classes/PaymethodrulesAuditLog.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_paymethodrules_log`
    -   **Pola `$definition`:** `id_paymethodrules_log`, `id_cart`, `id_customer`, `id_shop`, `context_data` (JSON), `policies_applied` (JSON), `payment_methods_before` (JSON), `payment_methods_after` (JSON), `date_add`.
    -   **Kluczowe metody publiczne:** Metody do logowania zdarzeń, pobierania wpisów z dziennika i ewentualnego czyszczenia starych logów.
-   `classes/PaymethodrulesCompatibility.php`: Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop (np. różnice w nazwach hooków, strukturach obiektów lub funkcjach `Tools`).
-   `classes/PaymethodrulesCondition.php`
    -   **Rozszerza:** `ObjectModel` (lub klasę bazową dla warunków)
    -   **Tabela bazy danych:** `ps_paymethodrules_condition` (jeśli warunki są przechowywane indywidualnie)
    -   **Pola `$definition`:** `id_paymethodrules_condition`, `id_paymethodrules_policy`, `type`, `operator`, `value`, `id_parent_group`.
    -   **Kluczowe metody publiczne:** Metody do definiowania typów warunków, operatorów i wartości. Część struktury drzewa warunków.
-   `classes/PaymethodrulesConditionEvaluator.php`: Zawiera podstawową logikę do oceny pojedynczego `PaymethodrulesCondition` względem danego kontekstu (koszyk, klient itp.).
-   `classes/PaymethodrulesConditionGroup.php`
    -   **Rozszerza:** `ObjectModel` (lub klasę bazową dla grup warunków)
    -   **Tabela bazy danych:** `ps_paymethodrules_condition_group` (jeśli grupy są przechowywane indywidualnie)
    -   **Pola `$definition`:** `id_paymethodrules_condition_group`, `id_paymethodrules_policy`, `operator` (`AND`/`OR`), `id_parent_group`.
    -   **Kluczowe metody publiczne:** Zarządza kolekcją warunków lub zagnieżdżonych grup warunków, stosując logikę `AND`/`OR`.
-   `classes/PaymethodrulesConditionTree.php`: Reprezentuje całą hierarchiczną strukturę warunków i grup warunków dla polityki. Udostępnia metody do budowania, przechodzenia i oceny drzewa.
-   `classes/PaymethodrulesContext.php`: Klasa narzędziowa, która hermetyzuje wszystkie istotne dane potrzebne do oceny reguł (bieżący koszyk, klient, adres, przewoźnik, waluta itp.). Działa jako dostawca danych dla `PaymethodrulesEngine`.
-   `classes/PaymethodrulesDashboard.php`: Klasa pomocnicza do pobierania danych i przygotowywania statystyk/podsumowań dla widoku pulpitu nawigacyjnego modułu.
-   `classes/PaymethodrulesEngine.php`: Centralna klasa odpowiedzialna za orkiestrację oceny reguł.
    -   **Kluczowe metody publiczne:** `evaluatePolicies(PaymethodrulesContext $context, array $payment_options)`: Przyjmuje bieżący kontekst i listę dostępnych opcji płatności, stosuje wszystkie aktywne polityki i zwraca zmodyfikowaną listę. Wykorzystuje `PaymethodrulesConditionTree` i `PaymethodrulesConditionEvaluator`.
-   `classes/PaymethodrulesListRenderer.php`: Specjalistyczna pomocnicza klasa do renderowania list w Panelu administracyjnym, potencjalnie rozszerzająca `HelperList` lub zapewniająca niestandardowe renderowanie kolumn.
-   `classes/PaymethodrulesLog.php`: Alias lub specyficzna implementacja dla `PaymethodrulesAuditLog`.
-   `classes/PaymethodrulesPolicy.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_paymethodrules_policy`
    -   **Pola `$definition`:** `id_paymethodrules_policy`, `name`, `active`, `policy_type` (`show`/`hide`), `payment_methods` (tablica JSON nazw modułów), `unavailable_message` (wielojęzyczny), `conditions_tree` (reprezentacja drzewa warunków w formacie JSON), `date_add`, `date_upd`.
    -   **Kluczowe metody publiczne:** Metody do zapisywania/ładowania danych polityki, pobierania powiązanych warunków i dostarczania logiki specyficznej dla polityki.
-   `classes/PaymethodrulesPolicyDuplicator.php`: Klasa narzędziowa specjalnie do duplikowania obiektów `PaymethodrulesPolicy`, zapewniająca poprawne kopiowanie wszystkich powiązanych warunków i grup.
-   `classes/PaymethodrulesPreset.php`: Prawdopodobnie obsługuje predefiniowane zestawy warunków lub polityk, które mogą być szybko ładowane przez sprzedawcę.
-   `classes/PaymethodrulesRule.php`: Może być starszą lub alternatywną nazwą dla `PaymethodrulesCondition` lub `PaymethodrulesPolicy`, lub klasą bazową dla komponentów reguł.
-   `classes/PaymethodrulesTreeRepository.php`: Zarządza trwałością i pobieraniem struktury `PaymethodrulesConditionTree`, prawdopodobnie konwertując ją do/z JSON do przechowywania w obiekcie `PaymethodrulesPolicy`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `paymethodrules/lib/searchTool/views/js/autocomplete.js`: Ogólna funkcjonalność autouzupełniania, prawdopodobnie używana do wybierania produktów, kategorii lub innych encji w kreatorze warunków.
-   `paymethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplikat lub specyficzna wersja skryptu autouzupełniania.
-   `paymethodrules/views/js/adminConditionBuilder.js`:
    -   **Zakres:** Panel administracyjny (ekran tworzenia/edycji polityki).
    -   **Funkcjonalność:** Obsługuje dynamiczne tworzenie, modyfikowanie i usuwanie warunków i grup warunków w formularzu polityki. Zarządza logiką „AND”/„OR”, dodaje nowe wiersze warunków, obsługuje zmiany typu warunku (np. wyświetlanie różnych pól wejściowych dla „Suma koszyka” vs. „Produkt”).
-   `paymethodrules/views/js/adminPaymethodrulesDashboard.js`:
    -   **Zakres:** Panel administracyjny (ekran pulpitu nawigacyjnego).
    -   **Funkcjonalność:** Może obsługiwać wywołania AJAX dla widżetów pulpitu nawigacyjnego, odświeżać dane lub dostarczać interaktywne elementy na pulpicie nawigacyjnym.
-   `paymethodrules/views/js/adminPaymethodrulesSearchTool.js`:
    -   **Zakres:** Panel administracyjny (kreator warunków).
    -   **Funkcjonalność:** Integruje bibliotekę `autocomplete.js` do wyszukiwania i wybierania encji (produktów, kategorii, klientów, przewoźników) podczas budowania warunków.
-   `paymethodrules/views/js/adminPaymethodrulesSimulator.js`:
    -   **Zakres:** Panel administracyjny (ekran symulatora).
    -   **Funkcjonalność:** Przechwytuje dane wejściowe użytkownika dla kryteriów symulacji, wysyła żądania AJAX do kontrolera symulatora i dynamicznie aktualizuje wyświetlanie z symulowaną dostępnością metody płatności.
-   `paymethodrules/views/js/adminPolicyRules.js`:
    -   **Zakres:** Panel administracyjny (ekrany listy i edycji polityk).
    -   **Funkcjonalność:** Ogólny JS do zarządzania politykami, taki jak obsługa przełączników włączania/wyłączania, akcji duplikowania i potencjalnie logiki przesyłania formularzy dla szczegółów polityki.
-   `paymethodrules/views/js/checkout.js`:
    -   **Zakres:** Front-office (strona realizacji zamówienia).
    -   **Funkcjonalność:** To jest kluczowe. Nasłuchuje zmian w procesie realizacji zamówienia (np. wybór metody wysyłki, zmiana adresu, aktualizacja koszyka) i może wywoływać wywołania AJAX w celu ponownej oceny dostępności metody płatności lub dynamicznej aktualizacji wyświetlania komunikatów o niedostępności. Zapewnia, że opcje płatności są zawsze aktualne.
-   `paymethodrules/views/js/unavailableUi.js`:
    -   **Zakres:** Front-office (strona realizacji zamówienia).
    -   **Funkcjonalność:** Zarządza wyświetlaniem i stylizacją „komunikatu o niedostępności” dla ukrytych metod płatności. Może dynamicznie wstrzykiwać wiadomość, stosować klasy CSS lub obsługiwać animacje.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `paymethodrules/lib/searchTool/views/css/autocomplete.css`: Style dla narzędzia wyszukiwania autouzupełniania w Panelu administracyjnym.
-   `paymethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplikat lub specyficzna wersja CSS autouzupełniania.
-   `paymethodrules/views/css/admin_paymethodrules.css`:
    -   **Zakres:** Panel administracyjny (wszystkie ekrany administracyjne modułu).
    -   **Funkcjonalność:** Zapewnia stylizację listy polityk, kreatora warunków, pulpitu nawigacyjnego, symulatora i dziennika audytu. Zawiera style dla elementów formularzy, tabel i niestandardowych komponentów interfejsu użytkownika specyficznych dla modułu.
    -   **Kluczowe selektory klas CSS:** `.paymethodrules-policy-card`, `.condition-group`, `.condition-row`, `.paymethodrules-dashboard-widget`.
-   `paymethodrules/views/css/front.css`:
    -   **Zakres:** Front-office (strona realizacji zamówienia).
    -   **Funkcjonalność:** Zapewnia podstawową stylizację komunikatów o niedostępności metody płatności lub wszelkich wizualnych wskazówek związanych z ukrytymi opcjami płatności na stronie realizacji zamówienia.
    -   **Kluczowe selektory klas CSS:** `.paymethodrules-unavailable-message`, `.paymethodrules-hidden-payment`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `paymethodrules/views/templates/hook/payment_top.tpl`:
    -   **Hook:** `displayPaymentTop` (lub podobny, w zależności od wersji PS)
    -   **Blok wizualny:** Ten szablon może być używany do wyświetlania ogólnej wiadomości lub informacji związanych z zasadami płatności na górze sekcji wyboru płatności. Jednak główna interakcja polega zazwyczaj na bezpośredniej modyfikacji tablicy opcji płatności. Może być również używany do wstrzykiwania skryptów `checkout.js` i `unavailableUi.js`.

#### Szablony administracyjne (`views/templates/admin/`)

-   `paymethodrules/lib/searchTool/views/scripts.tpl`: Zawiera JS/CSS dla narzędzia wyszukiwania w panelu administracyjnym.
-   `paymethodrules/lib/searchTool/views/views/scripts.tpl`: Duplikat lub specyficzna wersja skryptów narzędzia wyszukiwania.
-   `paymethodrules/views/templates/admin/auditPreview.tpl`: Renderuje szczegółowy widok pojedynczego wpisu w dzienniku audytu, pokazując kontekst, zastosowane polityki i zmiany metod płatności.
-   `paymethodrules/views/templates/admin/dashboard.tpl`: Renderuje główny pulpit nawigacyjny modułu, w tym widżety podsumowania polityk, ostatnich logów i szybkich linków.
-   `paymethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Niestandardowy szablon dla przycisku akcji „duplikuj” w `HelperList` dla polityk.
-   `paymethodrules/views/templates/admin/policiesPreview.tpl`: Może być używany do szybkiego podglądu zasad polityki bez wchodzenia w pełny formularz edycji lub do wyświetlania szczegółów polityki w dzienniku audytu.
-   `paymethodrules/views/templates/admin/policyConditionBuilder.tpl`: Główny szablon do renderowania dynamicznego interfejsu kreatora warunków w formularzu dodawania/edycji polityki. Zawiera części dla poszczególnych warunków i grup.
-   `paymethodrules/views/templates/admin/policyRuleCard.tpl`: Renderuje pojedynczą politykę jako kartę lub wiersz na liście, potencjalnie używany na pulpicie nawigacyjnym lub w uproszczonym widoku polityki.
-   `paymethodrules/views/templates/admin/policyRulesTable.tpl`: Renderuje główną tabelę polityk na ekranie `AdminPaymethodrulesPolicies`.
-   `paymethodrules/views/templates/admin/scopeSelector.tpl`: Szablon wielokrotnego użytku do wyboru zakresu (np. sklep, język) w formularzach administracyjnych.

#### Szablony Front-office (`views/templates/front/`)

-   Brak dedykowanych szablonów stron front-office, co wskazuje, że moduł integruje się głównie z istniejącymi szablonami realizacji zamówienia poprzez modyfikację danych, a nie renderowanie całkowicie nowych stron.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_paymethodrules_policy`: Przechowuje główne definicje polityk, w tym nazwę, status, dotknięte metody płatności, typ polityki, komunikaty o niedostępności (wielojęzyczne) oraz reprezentację drzewa warunków w formacie JSON.
-   `ps_paymethodrules_log`: Przechowuje wpisy w dzienniku audytu, w tym `id_cart`, `id_customer`, `context_data`, `policies_applied`, `payment_methods_before`, `payment_methods_after` i `date_add`.
-   (Potencjalnie) `ps_paymethodrules_condition` i `ps_paymethodrules_condition_group`, jeśli drzewo warunków jest przechowywane w sposób znormalizowany, a nie w całości jako JSON w `ps_paymethodrules_policy`. Plik `install.sql` to potwierdzi.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionPaymentOptionsModifier` | Podczas procesu realizacji zamówienia, przed wyświetleniem metod płatności. | **Główny hook:** `PaymethodrulesEngine` modułu jest wywoływany tutaj w celu filtrowania i modyfikowania tablicy dostępnych opcji płatności na podstawie aktywnych polityk i bieżącego kontekstu koszyka. |
| `displayBackOfficeHeader` | Przy każdym ładowaniu strony Panelu administracyjnego. | Wstrzykuje CSS i JS specyficzne dla modułu dla kontrolerów administracyjnych (np. `admin_paymethodrules.css`, `adminConditionBuilder.js`). |
| `displayHeader` | Przy każdym ładowaniu strony front-office. | Wstrzykuje CSS i JS specyficzne dla modułu dla front-office (np. `front.css`, `checkout.js`, `unavailableUi.js`), szczególnie na stronie realizacji zamówienia. |
| `moduleRoutes` | Podczas kompilacji tras PrestaShop. | Rejestruje niestandardowe trasy front-office i back-office dla kontrolerów modułu (np. `/module/paymethodrules/simulate`). |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany. | Wstrzykuje CSS i JS specyficzne dla modułu dla bieżącego kontrolera administracyjnego, zapewniając ładowanie zasobów tylko wtedy, gdy są potrzebne. |
| `actionObject*AddAfter` / `actionObject*UpdateAfter` | Po dodaniu lub zaktualizowaniu obiektu (np. `Cart`, `Customer`). | Potencjalnie używane do czyszczenia wewnętrznych pamięci podręcznych lub wyzwalania ponownej oceny, jeśli moduł utrzymuje jakiekolwiek dane w pamięci podręcznej. |
| `displayAdminProductsExtra` (lub podobny) | Na stronie edycji produktu w BO. | Może być używany do dodawania warunków specyficznych dla produktu bezpośrednio na stronie produktu, chociaż nie jest to wyraźnie wymienione na liście plików. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zasady Warunkowych Metod Płatności”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
