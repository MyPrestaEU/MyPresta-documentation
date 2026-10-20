---
title: "Dyrektywa Omnibus - Darmowy Dodatek - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Dyrektywa Omnibus - Darmowy Dodatek” od MyPresta.eu."
sidebar:
  label: "Dyrektywa Omnibus - Darmowy Dodatek - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Omnibus Directive - Free Addon na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-free-addon.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/omnibus-directive-free-addon/)
>
> ---


# Dyrektywa Omnibus - Darmowy Dodatek

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5 (Moduł jest zaprojektowany tak, aby był kompatybilny z szerokim zakresem wersji PHP, aż do najnowszych stabilnych wersji obsługiwanych przez PrestaShop 9.x)
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu. Nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do konfiguracji modułu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Dyrektywa Omnibus - Darmowy Dodatek” i kliknij przycisk „Konfiguruj”.

#### Ustawienia ogólne

-   **Włącz zgodność z Dyrektywą Omnibus:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł rozpocznie śledzenie cen produktów i wyświetli najniższą cenę z 30 dni na stronach produktów, gdy aktywna jest zniżka.
        -   *Gdy wyłączone (NIE):* Moduł przestanie śledzić ceny i nie będzie wyświetlał żadnych informacji związanych z Dyrektywą Omnibus w Twoim sklepie.
    -   **Zalecana wartość:** TAK (chyba że nie sprzedajesz klientom z UE lub tymczasowo wyłączasz go w celu konserwacji).
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz upewnić się, że Twój sklep jest zgodny. Ustawisz to na TAK. Jeśli testujesz nowy motyw i chcesz tymczasowo ukryć wyświetlanie, możesz ustawić to na NIE.
-   **Wyświetl tekst najniższej ceny:**

    -   **Co robi to ustawienie:** Pozwala dostosować tekst, który pojawia się przed najniższą ceną z 30 dni.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Tekst wyświetlany klientom będzie odzwierciedlał Twoją niestandardową wiadomość.
        -   *Pozostawione jako domyślne:* Zostanie użyty domyślny tekst (np. „Najniższa cena w ciągu ostatnich 30 dni:”).
    -   **Zalecana wartość:** „Najniższa cena w ciągu ostatnich 30 dni:” lub podobna, zapewniająca przejrzystość dla Twoich klientów.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć użyć nieco innego sformułowania, np. „Nasza najniższa cena ostatnio wynosiła:”, aby dopasować się do tonu Twojej marki.
-   **Wyświetl na stronie produktu (Wybór hooka):**

    -   **Co robi to ustawienie:** To kluczowe ustawienie określa, *gdzie* na stronie produktu będą wyświetlane informacje o najniższej cenie z 30 dni. Moduł oferuje predefiniowane opcje dla typowych struktur motywów (Classic, Hummingbird) oraz opcję niestandardowego hooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu „Profil motywu Classic”:* Moduł spróbuje wstrzyknąć historię cen w odpowiednie miejsce w standardowej strukturze motywu Classic (np. `displayProductPriceBlock` lub `displayProductButtons`).
        -   *Po wybraniu „Profil motywu Hummingbird”:* Moduł spróbuje wstrzyknąć historię cen w odpowiednie miejsce w standardowej strukturze motywu Hummingbird.
        -   *Po wybraniu „Niestandardowy hook”:* Będziesz musiał ręcznie określić hook PrestaShop, w którym moduł powinien wyświetlać swoją zawartość. Wymaga to pewnej wiedzy technicznej lub modyfikacji motywu.
    -   **Zalecana wartość:** Zacznij od „Profil motywu Classic” lub „Profil motywu Hummingbird” w zależności od aktywnego motywu. Jeśli wyświetlanie nie jest zadowalające, skonsultuj się z webmasterem w sprawie integracji „Niestandardowego hooka”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep używa domyślnego motywu PrestaShop Classic, wybierz „Profil motywu Classic”. Jeśli zaktualizowałeś do PrestaShop 8.x i używasz motywu Hummingbird, wybierz „Profil motywu Hummingbird”. Jeśli masz mocno dostosowany motyw, możesz potrzebować użyć „Niestandardowego hooka” i poprosić swojego programistę o dodanie `{hook h='displayMyCustomOmnibusHook'}` do szablonu strony produktu.
-   **Nazwa niestandardowego hooka (jeśli powyżej wybrano „Niestandardowy hook”):**

    -   **Co robi to ustawienie:** Jeśli w poprzednim ustawieniu wybrałeś „Niestandardowy hook”, to pole pozwala określić dokładną nazwę hooka, w którym moduł powinien renderować swoją zawartość.
    -   **Efekt zmiany tego ustawienia:** Moduł wyświetli swoją zawartość tylko wtedy, gdy hook o tej dokładnej nazwie jest obecny w szablonie strony produktu Twojego motywu.
    -   **Zalecana wartość:** Pozostaw puste, chyba że wybrałeś „Niestandardowy hook” powyżej i znasz dokładną nazwę hooka. Przykład: `displayProductExtraContent`.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój webmaster zmodyfikował szablon strony produktu (`product.tpl`), aby zawierał `{hook h='displayMyCustomOmnibusHook'}`. Wtedy wpiszesz `displayMyCustomOmnibusHook` w tym polu.

#### Zarządzanie danymi

-   **Wyczyść dane Omnibus:**
    -   **Co robi to ustawienie:** Ten przycisk pozwala usunąć wszystkie wcześniej zarejestrowane dane historii cen przechowywane przez moduł.
    -   **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku trwale usunie wszystkie historyczne rekordy cen. Moduł rozpocznie wtedy zbieranie danych od nowa od momentu przeglądania lub aktualizacji produktów.
    -   **Zalecana wartość:** Używaj z ostrożnością. Czyść dane tylko wtedy, gdy musisz zresetować historię cen, na przykład po gruntownej przebudowie katalogu produktów lub jeśli podejrzewasz uszkodzenie danych.
    -   **Scenariusz / przykład dla sprzedawcy:** Zaimportowałeś zupełnie nowy zestaw produktów z różnymi strategiami cenowymi i chcesz upewnić się, że dane Omnibus zaczynają się od nowa, bez żadnych starych cen. Kliknąłbyś ten przycisk.

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz zgodność z Dyrektywą Omnibus | TAK | Aktywuje/dezaktywuje śledzenie i wyświetlanie cen dla zgodności z UE. |
| Konfiguracja modułu | Wyświetl tekst najniższej ceny | „Najniższa cena w ciągu ostatnich 30 dni:” | Dostosowuje tekst wyświetlany przed ceną historyczną. |
| Konfiguracja modułu | Wyświetl na stronie produktu (Wybór hooka) | Profil Classic/Hummingbird (w zależności od motywu) | Określa, gdzie historia cen pojawia się na stronie produktu. |
| Konfiguracja modułu | Nazwa niestandardowego hooka | (Puste) | Określa niestandardowy hook do wyświetlania, jeśli wybrano „Niestandardowy hook”. |
| Konfiguracja modułu | Wyczyść dane Omnibus | (Przycisk) | Usuwa całą przechowywaną historię cen, wymuszając nowy start. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Informacje o najniższej cenie nie pojawiają się na moich stronach produktów.**
O:

1.  **Sprawdź „Włącz zgodność z Dyrektywą Omnibus”:** Upewnij się, że jest ustawione na TAK w konfiguracji modułu.
2.  **Zweryfikuj „Wyświetl na stronie produktu (Wybór hooka)”:** Spróbuj przełączać się między „Profilem motywu Classic” a „Profilem motywu Hummingbird”, jeśli nie masz pewności, który z nich najlepiej pasuje do Twojego motywu.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami zmiany motywu lub aktualizacje modułów wymagają odświeżenia pamięci podręcznej.
4.  **Sprawdź zniżki:** Informacje pojawiają się tylko wtedy, gdy produkt jest faktycznie przeceniony. Upewnij się, że testowany produkt ma zastosowaną aktywną cenę specyficzną lub regułę cen katalogowych.
5.  **Niestandardowy motyw:** Jeśli używasz mocno dostosowanego motywu, moduł może nie być w stanie automatycznie wstrzyknąć zawartości. Prawdopodobnie będziesz musiał użyć opcji „Niestandardowy hook” i poprosić swojego webmastera o zintegrowanie go z plikiem `product.tpl` Twojego motywu.

**P: Wyświetlana najniższa cena wydaje się nieprawidłowa lub zbyt wysoka/niska.**
O:

1.  **Czas zbierania danych:** Moduł potrzebuje czasu na zebranie danych. Jeśli właśnie go zainstalowałeś, zacznie śledzić ceny dopiero od tego momentu. Pełna 30-dniowa historia będzie dostępna po 30 dniach.
2.  **Wyczyść dane Omnibus:** Jeśli podejrzewasz, że używane są stare, nieprawidłowe dane, możesz kliknąć przycisk „Wyczyść dane Omnibus” w konfiguracji modułu. Pamiętaj, że spowoduje to usunięcie całej historii, a moduł rozpocznie zbieranie danych od zera.
3.  **Kombinacje produktów/waluty:** Upewnij się, że patrzysz na prawidłową kombinację i walutę. Moduł śledzi ceny dla każdej kombinacji i waluty.

**P: Czy ten moduł spowolni mój sklep?**
O: Moduł został zaprojektowany tak, aby był lekki. Śledzenie cen odbywa się w tle lub podczas przeglądania produktów, a wyświetlanie w front office to proste wyjście tekstowe. Wszelki wpływ na wydajność powinien być znikomy.

**P: Jak ten moduł obsługuje sklepy wielojęzyczne?**
O: Ustawienie „Wyświetl tekst najniższej ceny” jest tłumaczone. Możesz przejść do **Lokalizacja > Tłumaczenia**, wybrać „Tłumaczenia zainstalowanych modułów”, wybrać swój motyw, a następnie wybrać moduł „Dyrektywa Omnibus - Darmowy Dodatek”, aby przetłumaczyć tekst na wszystkie aktywne języki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Dyrektywa Omnibus - Darmowy Dodatek” jest zgodny ze standardową architekturą modułów PrestaShop. Jego podstawowa funkcjonalność znajduje się w głównym pliku `index.php`, który działa jako punkt wejścia modułu i obsługuje instalację, deinstalację, konfigurację i rejestrację hooków. Historia cen jest zarządzana poprzez obserwowanie zmian cen produktów i ich przechowywanie, prawdopodobnie w niestandardowej tabeli lub `ps_configuration` (chociaż dossier wskazuje brak niestandardowego SQL, co sugeruje `ps_configuration` lub dynamiczne generowanie danych). Wyświetlanie w front-office jest realizowane poprzez podłączanie się do standardowych punktów wyświetlania PrestaShop, ze specyficzną logiką dla motywów Classic i Hummingbird.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak jawnie zdefiniowanych w dossier. Logika front-office jest prawdopodobnie obsługiwana bezpośrednio w metodach hooków głównego pliku modułu.
-   **Kontrolery Back-Office Admin**: Brak jawnie zdefiniowanych w dossier. Cała konfiguracja back-office jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

-   Brak jawnie zdefiniowanych w dossier. Logika modułu, w tym śledzenie i przechowywanie cen, jest prawdopodobnie hermetyzowana w klasie `Omnifree` w `index.php`.
    -   **Klasa `Omnifree` (w `omnifree/index.php`)**:
        -   Rozszerza `Module`.
        -   Obsługuje instalację (`install()`) i deinstalację (`uninstall()`) modułu.
        -   Rejestruje niezbędne hooki (np. `displayHeader`, `displayProductPriceBlock`, `displayProductButtons`, `displayFooter`, `actionProductUpdate`, `actionProductSave`).
        -   Zarządza ustawieniami konfiguracji za pomocą `getContent()`.
        -   Zawiera metody do śledzenia i pobierania cen, prawdopodobnie wchodząc w interakcję z `ps_configuration` w celu przechowywania cen historycznych lub dynamicznego ich obliczania na podstawie historii zamówień.
        -   Implementuje metody hooków (`hookDisplayHeader`, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, `hookDisplayFooter` itp.) w celu wstrzykiwania treści do front office.
        -   Implementuje hooki akcji (`hookActionProductUpdate`, `hookActionProductSave`) w celu rejestrowania zmian cen.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`omnifree/views/js/admin-config.js`**:
    -   **Zakres:** Back-office.
    -   **Cel:** Ten skrypt prawdopodobnie obsługuje dynamiczne zachowanie strony konfiguracji modułu. Może to obejmować:
        -   Pokazywanie/ukrywanie pola wejściowego „Nazwa niestandardowego hooka” w zależności od wartości rozwijanej listy „Wyświetl na stronie produktu (Wybór hooka)”.
        -   Wywołania AJAX dla przycisku „Wyczyść dane Omnibus” w celu wykonania czyszczenia danych bez pełnego przeładowania strony.
        -   Walidację danych wejściowych lub inne interaktywne elementy na formularzu konfiguracji.
    -   **Słuchacze zdarzeń:** Prawdopodobnie nasłuchuje zdarzeń `change` na listach rozwijanych i zdarzeń `click` na przyciskach w formularzu konfiguracji modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`omnifree/views/css/admin-config.css`**:
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Cel:** Zapewnia specyficzną stylizację dla elementów na stronie konfiguracji modułu w panelu administracyjnym PrestaShop, zapewniając spójny i przyjazny dla użytkownika interfejs administracyjny.
    -   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w konkretne identyfikatory lub klasy w szablonie `configure.tpl`.
-   **`omnifree/views/css/omnibus-classic.css`**:
    -   **Zakres:** Stylizacja front-office dla klienta (specyficzna dla motywu Classic).
    -   **Cel:** Zawiera reguły CSS, aby zapewnić, że wyświetlane informacje o najniższej cenie są poprawnie stylizowane i pozycjonowane w motywie PrestaShop Classic, unikając konfliktów i zachowując wizualną harmonię.
    -   **Kluczowe selektory klas CSS:** Celuje w elementy takie jak `.product-prices`, `.product-information` lub niestandardowe klasy dodane przez moduł do wyświetlania historii cen.
-   **`omnifree/views/css/omnibus-hummingbird.css`**:
    -   **Zakres:** Stylizacja front-office dla klienta (specyficzna dla motywu Hummingbird).
    -   **Cel:** Zapewnia specyficzne dostosowania stylizacji i pozycjonowania dla informacji o najniższej cenie, gdy aktywny jest motyw Hummingbird (domyślny w PrestaShop 8.x).
    -   **Kluczowe selektory klas CSS:** Celuje w elementy specyficzne dla struktury strony produktu motywu Hummingbird.
-   **`omnifree/views/css/omnibus.css`**:
    -   **Zakres:** Stylizacja front-office dla klienta (ogólna).
    -   **Cel:** Zawiera ogólne, niezależne od motywu reguły CSS dla wyświetlania najniższej ceny. Może to obejmować podstawową stylizację czcionki, kolor lub margines, które mają zastosowanie niezależnie od wybranego profilu motywu.
    -   **Kluczowe selektory klas CSS:** Ogólne klasy używane w `omnibus.tpl`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   **`omnifree/views/templates/hook/omnibus.tpl`**:
        -   **Cel:** Jest to główny szablon front-office odpowiedzialny za renderowanie informacji o najniższej cenie z 30 dni. Będzie renderowany przez metody hooków modułu (np. `hookDisplayProductPriceBlock`, `hookDisplayProductButtons` lub niestandardowy hook).
        -   **Zmienne:** Prawdopodobnie oczekuje zmiennych takich jak `$lowest_price_30_days`, `$currency_symbol`, `$display_text` i potencjalnie `$product_id` lub `$id_product_attribute`.
        -   **Wyjście:** Mały fragment HTML zawierający skonfigurowany tekst i sformatowaną najniższą cenę.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   **`omnifree/views/templates/admin/configure.tpl`**:
        -   **Cel:** Ten szablon renderuje główny formularz konfiguracji modułu w panelu administracyjnym PrestaShop. Zawiera wszystkie ustawienia opisane w Sekcji 4.1.
        -   **Zmienne:** Otrzymuje wartości konfiguracji z `getContent()` do wstępnego wypełniania pól formularza.
        -   **Struktura:** Wykorzystuje strukturę formularza pomocniczego PrestaShop (np. `AdminForm`) do tworzenia pól wejściowych, przełączników i przycisków.
    -   **`omnifree/views/templates/admin/pro-teaser.tpl`**:
        -   **Cel:** Ten szablon prawdopodobnie wyświetla treści promocyjne lub „zwiastun” wersji „Pro” lub płatnej modułu Dyrektywa Omnibus od MyPresta.eu. Może podkreślać dodatkowe funkcje dostępne w wersji premium.
        -   **Umieszczenie:** Prawdopodobnie włączony w `configure.tpl` lub wyświetlany jako oddzielny blok na stronie konfiguracji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Dossier wskazuje brak niestandardowych plików SQL. Sugeruje to, że dane historii cen są albo:
        1.  Przechowywane bezpośrednio w `ps_configuration` jako serializowane tablice (mniej wydajne dla dużych zbiorów danych).
        2.  Dynamicznie obliczane na podstawie tabel `ps_order_detail` i `ps_product_attribute_combination` (bardziej złożone, ale unika niestandardowych tabel).
        3.  Niestandardowa tabela jest tworzona programowo w `install()` bez oddzielnego pliku SQL. Biorąc pod uwagę charakter „Darmowego Dodatku”, opcja 1 lub 2 jest bardziej prawdopodobna ze względu na prostotę.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Przy każdym ładowaniu strony w sekcji `<head>`. | Ładowanie zasobów CSS/JS modułu (np. `omnibus.css`, `omnibus-classic.css`, `omnibus-hummingbird.css`). |
| `displayProductPriceBlock` | Front-Office | Na stronach produktów, zazwyczaj w pobliżu ceny. | Jeden z głównych hooków do wyświetlania informacji o najniższej cenie w motywie Classic. |
| `displayProductButtons` | Front-Office | Na stronach produktów, zazwyczaj w pobliżu przycisku „dodaj do koszyka”. | Inny potencjalny hook do wyświetlania informacji o najniższej cenie w motywie Classic. |
| `displayFooter` | Front-Office | Na dole każdej strony. | Mniej prawdopodobne do wyświetlania cen, ale może być używane do ogólnych komunikatów o zgodności lub jeśli niestandardowy hook jest umieszczony tutaj. |
| `actionProductUpdate` | Back-Office | Gdy produkt jest aktualizowany/zapisywany w back office. | Wywołanie mechanizmu śledzenia cen i rejestrowanie aktualnej ceny produktu dla historii. |
| `actionProductSave` | Back-Office | Gdy produkt jest zapisywany (nowy lub istniejący) w back office. | Podobnie jak `actionProductUpdate`, zapewnia przechwytywanie zmian cen. |
| `actionFrontControllerSetMedia` | Front-Office | Przed renderowaniem wyjścia przez kontroler front-office. | Warunkowe ładowanie specyficznych CSS/JS w zależności od bieżącej strony lub motywu. |
| (Nazwa niestandardowego hooka) | Front-Office | Tam, gdzie sprzedawca umieszcza `{hook h='CustomHookName'}` w swoim szablonie. | Umożliwia elastyczne umieszczanie wyświetlania najniższej ceny dla mocno dostosowanych motywów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Dyrektywa Omnibus - Darmowy Dodatek”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań związanych z funkcjonalnością i integracją modułu.
