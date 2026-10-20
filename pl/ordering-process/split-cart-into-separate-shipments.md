---
title: "Podziel koszyk na osobne przesyłki - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: ""
sidebar:
  label: "Podziel koszyk na osobne przesyłki - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Split cart into separate shipments na MyPresta.eu](https://mypresta.eu/modules/ordering-process/split-cart-into-separate-shipments.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/split-cart-into-separate-shipments/)
>
> ---


# Podziel koszyk na osobne przesyłki

## 1. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Podziel koszyk na osobne przesyłki” wprowadza kilka potężnych nowych ekranów i opcji w Twoim Panelu administracyjnym PrestaShop.

### 1.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Podziel koszyk na osobne przesyłki)

Jest to główna strona konfiguracji, do której masz dostęp natychmiast po instalacji lub klikając „Konfiguruj” w Menedżerze modułów. Zawiera ogólne ustawienia dotyczące zachowania modułu.

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania funkcjonalności modułu w całym Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie aktywnie dzielić koszyki zgodnie z Twoimi regułami podczas realizacji zamówienia.
        -   *Gdy wyłączone:* Logika dzielenia modułu zostanie pominięta, a PrestaShop powróci do domyślnego zachowania pojedynczej przesyłki.
    -   **Zalecana wartość:** TAK (po skonfigurowaniu reguł).
    -   **Scenariusz / przykład sprzedawcy:** Możesz tymczasowo wyłączyć moduł, jeśli wykonujesz konserwację lub rozwiązujesz problemy z innymi częściami procesu realizacji zamówienia.
-   **Tryb debugowania:**

    -   **Co robi to ustawienie:** Aktywuje specjalny tryb, który może wyświetlać dodatkowe informacje techniczne lub logi, aby pomóc w identyfikacji problemów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Może wyświetlać komunikaty o błędach lub szczegółowe kroki przetwarzania w front-office (widoczne dla klientów) lub w konsoli programisty Twojej przeglądarki. Jest to przydatne dla programistów.
        -   *Gdy wyłączone:* Moduł działa cicho, bez wyświetlania informacji debugowania.
    -   **Zalecana wartość:** NIE (zawsze wyłączaj w działającym sklepie produkcyjnym).
    -   **Scenariusz / przykład sprzedawcy:** Jeśli współpracujesz z programistą, aby zrozumieć, dlaczego konkretny koszyk nie jest dzielony zgodnie z oczekiwaniami, może on poprosić Cię o tymczasowe włączenie tej opcji.
-   **Wyświetl podsumowanie podziału na stronie potwierdzenia zamówienia:**

    -   **Co robi to ustawienie:** Kontroluje, czy klienci widzą podsumowanie, w jaki sposób ich zamówienie zostało podzielone na różne przesyłki na końcowej stronie potwierdzenia zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci zobaczą jasne podsumowanie, które przedmioty trafiły do której grupy przesyłek i wybranego przewoźnika dla każdej z nich, potwierdzając swoje wybory.
        -   *Gdy wyłączone:* Strona potwierdzenia zamówienia wyświetli standardowe podsumowanie bez szczegółowych informacji o podziale.
    -   **Zalecana wartość:** TAK.
    -   **Scenariusz / przykład sprzedawcy:** Włączenie tej opcji poprawia przejrzystość i zapewnia klientów, że ich konkretne wybory wysyłki dla każdej paczki zostały poprawnie zastosowane.
-   **Zezwól klientowi na wybór punktów odbioru (jeśli dotyczy):**

    -   **Co robi to ustawienie:** Jeśli masz przewoźników, którzy oferują dostawę do punktów odbioru (np. Mondial Relay, Colissimo Point Relais), to ustawienie umożliwia klientom wybór konkretnej lokalizacji odbioru dla każdej odpowiedniej grupy przesyłek.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Dla przewoźników skonfigurowanych z punktami odbioru, klienci zobaczą opcję wyboru lokalizacji odbioru podczas realizacji zamówienia dla odpowiedniej przesyłki.
        -   *Gdy wyłączone:* Klienci będą mogli wybrać tylko dostawę do domu lub inne standardowe opcje wysyłki, nawet jeśli przewoźnicy obsługują punkty odbioru.
    -   **Zalecana wartość:** TAK (jeśli korzystasz z przewoźników z punktami odbioru).
    -   **Scenariusz / przykład sprzedawcy:** Jeśli oferujesz Mondial Relay, włączenie tej opcji pozwala klientom na dostarczenie ciężkiego przedmiotu do wygodnego punktu odbioru w pobliżu ich domu lub pracy, poprawiając ich doświadczenie.

### 1.2 Dedykowane ekrany administracyjne: Reguły wysyłki (Panel administracyjny > Wysyłka > Reguły podziału przesyłek)

Ten ekran służy do definiowania logiki grupowania produktów w koszyku na osobne przesyłki. Jest to rdzeń funkcjonalności modułu.

-   **Nazwa ekranu i lokalizacja w menu:** **Reguły podziału przesyłek** (znajduje się w sekcji **Wysyłka** w menu Panelu administracyjnego PrestaShop).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela z listą reguł:** Wyświetla wszystkie zdefiniowane reguły grupowania. Każda reguła ma nazwę, status (aktywna/nieaktywna), priorytet oraz podsumowanie jej warunków i działań.
    -   **Przycisk „Dodaj nową regułę”:** Kliknięcie tego przycisku umożliwia utworzenie nowej reguły.
    -   **Akcje Edytuj/Usuń:** Dla każdej reguły na liście możesz edytować jej szczegóły lub ją usunąć.
    -   **Przełącznik Włącz/Wyłącz:** Szybko aktywuj lub dezaktywuj regułę bez jej usuwania.
    -   **Zmień kolejność przeciągnij i upuść:** Reguły są przetwarzane w kolejności ich priorytetu. Możesz przeciągać i upuszczać reguły, aby zmienić ich kolejność wykonania. Reguły o wyższym priorytecie są przetwarzane jako pierwsze.
-   **Efekt zmian:**
    -   **Dodawanie/Edytowanie reguł:** Bezpośrednio wpływa na sposób dzielenia koszyków podczas realizacji zamówienia. Dobrze zdefiniowana reguła może zapewnić, że określone produkty zawsze będą wysyłane osobno lub razem.
    -   **Włączanie/Wyłączanie reguł:** Kontroluje, czy logika reguły jest stosowana.
    -   **Zmiana priorytetu:** Określa, która reguła ma pierwszeństwo, jeśli wiele reguł może dotyczyć tego samego produktu. Reguły o wyższym priorytecie (pojawiające się wyżej na liście) są oceniane jako pierwsze.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zidentyfikuj potrzeby grupowania:** Pomyśl o swoich produktach. Czy masz przedmioty ponadgabarytowe, delikatne, przedmioty z różnych magazynów lub przedmioty wymagające specjalnej obsługi?
    2.  **Utwórz reguły:** Dla każdej potrzeby grupowania utwórz nową regułę.
        -   **Warunki:** Zdefiniuj, *kiedy* reguła ma zastosowanie. Może to być oparte na:
            -   **Produkcie:** Konkretne produkty, kategorie, producenci, dostawcy lub cechy produktu.
            -   **Koszyku:** Całkowita wartość koszyka, liczba przedmiotów, konkretne grupy klientów.
            -   **Wysyłce:** Konkretni przewoźnicy lub strefy.
        -   **Działania:** Zdefiniuj, *co* robi reguła. Może to być:
            -   **Wymuś osobną przesyłkę:** Zawsze umieszczaj dopasowane przedmioty w ich własnej grupie przesyłek.
            -   **Wymuś tę samą przesyłkę:** Upewnij się, że dopasowane przedmioty zawsze pozostają razem w jednej przesyłce.
            -   **Wyklucz z przetwarzania reguł:** Zapobiegaj wpływowi innych reguł na te przedmioty.
    3.  **Ustaw priorytet:** Uporządkuj swoje reguły od najbardziej szczegółowych (np. „Delikatne szkło zawsze wysyłane osobno”) do najbardziej ogólnych (np. „Wszystkie przedmioty ponadgabarytowe wysyłane osobno”).
    4.  **Dokładnie przetestuj:** Użyj testowego konta klienta, aby dodać różne kombinacje produktów do koszyka i zweryfikować, czy podział działa zgodnie z oczekiwaniami podczas realizacji zamówienia.

### 1.3 Dedykowane ekrany administracyjne: Grupy przesyłek (Panel administracyjny > Wysyłka > Podziały przesyłek)

Ten ekran przedstawia przegląd sposobu, w jaki zamówienia zostały podzielone przez moduł po ich złożeniu. Jest to narzędzie do raportowania i zarządzania.

-   **Nazwa ekranu i lokalizacja w menu:** **Podziały przesyłek** (znajduje się w sekcji **Wysyłka** w menu Panelu administracyjnego PrestaShop).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela z listą podziałów:** Pokazuje listę wszystkich zamówień, które zostały podzielone przez moduł.
    -   **Numer referencyjny zamówienia:** Łączy bezpośrednio z oryginalnym zamówieniem PrestaShop.
    -   **Szczegóły grupy przesyłek:** Zawiera informacje o każdej indywidualnej grupie przesyłek w ramach zamówienia, w tym o produktach, które zawiera, wybranym przewoźniku i jej statusie.
    -   **Wyświetl szczegóły podziału:** Umożliwia zagłębienie się w konkretny podział, aby zobaczyć bardziej szczegółowe informacje.
-   **Efekt zmian:** Ten ekran służy głównie do przeglądania i audytu. Nie zmieniasz tu bezpośrednio sposobu dzielenia przyszłych koszyków. Wszelkie zmiany, które wprowadzasz (np. aktualizacja przewoźnika dla konkretnego podziału), byłyby zazwyczaj wykonywane w głównym widoku zamówienia PrestaShop, a ten moduł odzwierciedlałby te zmiany.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   **Monitoruj podzielone zamówienia:** Regularnie sprawdzaj ten ekran, aby zrozumieć, jak Twoje reguły działają w praktyce.
    -   **Rozwiązywanie problemów:** Jeśli klient ma pytanie dotyczące wysyłki, ten ekran może pomóc szybko sprawdzić, jak jego zamówienie zostało przetworzone na różne przesyłki.
    -   **Integracja z zarządzaniem zamówieniami:** Chociaż moduł tworzy standardowe zamówienia PrestaShop, ten ekran oferuje skonsolidowany widok logiki podziału zastosowanej do każdego zamówienia.

### 1.4 Dedykowane ekrany administracyjne: Pulpit nawigacyjny (Panel administracyjny > Wysyłka > Pulpit nawigacyjny podziału przesyłek)

Ten ekran zapewnia szybki przegląd i statystyki związane z aktywnością modułu.

-   **Nazwa ekranu i lokalizacja w menu:** **Pulpit nawigacyjny podziału przesyłek** (znajduje się w sekcji **Wysyłka** w menu Panelu administracyjnego PrestaShop).
-   **Dostępne akcje i ustawienia:**
    -   **Pasek KPI:** Kluczowe wskaźniki wydajności (KPI), takie jak całkowita liczba podzielonych zamówień, średnia liczba przesyłek na zamówienie lub całkowity przychód z wysyłki z podzielonych zamówień.
    -   **Wykresy i diagramy:** Wizualne przedstawienia trendów, takie jak liczba podzielonych zamówień w czasie, najczęściej używane reguły podziału lub popularni przewoźnicy dla podzielonych przesyłek.
    -   **Ostatnie podziały:** Szybka lista ostatnio podzielonych zamówień.
-   **Efekt zmian:** Jest to pulpit nawigacyjny do raportowania. Nie wprowadza się tu bezpośrednich zmian w zachowaniu modułu. Pomaga zrozumieć wpływ i wykorzystanie modułu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   **Monitorowanie wydajności:** Użyj tego pulpitu nawigacyjnego, aby ocenić skuteczność swoich reguł podziału i zidentyfikować wszelkie wzorce lub anomalie.
    -   **Planowanie strategiczne:** Dane mogą informować o decyzjach dotyczących strategii wysyłki, partnerstw z przewoźnikami lub dostosowań katalogu produktów.

### 1.5 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Tryb debugowania | NIE | Wyświetla informacje techniczne (tylko dla programistów). |
| | Wyświetl podsumowanie podziału na stronie potwierdzenia zamówienia | TAK | Pokazuje klientom, jak ich zamówienie zostało podzielone. |
| | Zezwól klientowi na wybór punktów odbioru | TAK (jeśli dotyczy) | Umożliwia wybór punktów odbioru dla odpowiednich przewoźników. |
| **Reguły podziału przesyłek** | Dodaj/Edytuj regułę (Warunki) | N/A | Definiuje, *kiedy* reguła ma zastosowanie (np. według produktu, kategorii, wartości koszyka). |
| | Dodaj/Edytuj regułę (Działania) | N/A | Definiuje, *co* robi reguła (np. wymuś osobną przesyłkę, wymuś tę samą przesyłkę). |
| | Priorytet reguły | N/A | Określa kolejność przetwarzania reguł (wyższy = pierwszy). |
| | Włącz/Wyłącz regułę | N/A | Aktywuje lub dezaktywuje konkretną regułę grupowania. |
| **Podziały przesyłek** | Wyświetl podzielone zamówienia | N/A | Zawiera listę i szczegóły wszystkich zamówień przetworzonych przez moduł. |
| **Pulpit nawigacyjny podziału przesyłek** | KPI, Wykresy, Ostatnie podziały | N/A | Oferuje przegląd aktywności i wydajności modułu. |

## 2. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

-   **P: Mój koszyk się nie dzieli lub dzieli się nieprawidłowo. Co powinienem zrobić?**

    -   **O:** Najpierw sprawdź, czy moduł jest włączony w jego głównej konfiguracji. Następnie przejdź do **Wysyłka > Reguły podziału przesyłek** i przejrzyj swoje reguły. Upewnij się, że są aktywne, a ich warunki poprawnie pasują do produktów w Twoim testowym koszyku. Zwróć szczególną uwagę na priorytet reguł – bardziej ogólna reguła może nadpisywać bardziej szczegółową. Jeśli masz włączony „Tryb debugowania” w głównej konfiguracji modułu, sprawdź, czy podczas realizacji zamówienia pojawiają się jakieś komunikaty. Na koniec wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
-   **P: Dlaczego niektórzy przewoźnicy nie pojawiają się dla konkretnej grupy przesyłek?**

    -   **O:** Moduł przestrzega standardowych ograniczeń przewoźników PrestaShop. Sprawdź następujące kwestie:
        1.  **Strefy przewoźnika:** Upewnij się, że przewoźnik jest włączony dla strefy wysyłki klienta.
        2.  **Zakresy wagowe/cenowe przewoźnika:** Sprawdź, czy całkowita waga/cena *indywidualnej grupy przesyłek* (nie całego koszyka) mieści się w zdefiniowanych zakresach przewoźnika.
        3.  **Powiązania przewoźnika:** Upewnij się, że przewoźnik jest powiązany z produktami w tej grupie przesyłek (jeśli ustawiłeś ograniczenia przewoźnika dla konkretnych produktów).
        4.  **Kompatybilność modułu:** Niektóre moduły wysyłkowe innych firm mogą mieć własną logikę, która koliduje; sprawdź, czy istnieją znane niekompatybilności lub skontaktuj się z pomocą techniczną.
-   **P: Jak ten moduł wpływa na moje istniejące koszty wysyłki i zasady darmowej wysyłki?**

    -   **O:** Moduł agreguje koszty wysyłki. Jeśli koszyk zostanie podzielony na dwie przesyłki, a każda przesyłka kosztuje 10 zł, klient zobaczy całkowity koszt wysyłki w wysokości 20 zł. W przypadku darmowej wysyłki, Twoje istniejące zasady darmowej wysyłki (np. „darmowa wysyłka powyżej X zł”) będą miały zastosowanie do *każdej indywidualnej grupy przesyłek*, jeśli moduł na to pozwala, lub do *całkowitej wartości koszyka*, w zależności od tego, jak skonfigurowane są Twoje reguły i jak moduł się integruje. Może być konieczne dostosowanie zasad darmowej wysyłki, aby uwzględnić podzielone przesyłki.
-   **P: Czy mogę przetłumaczyć teksty modułu na inne języki?**

    -   **O:** Tak, jak większość modułów PrestaShop, możesz przetłumaczyć jego teksty front-office i back-office. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, wybierz „Podziel koszyk na osobne przesyłki”, a następnie wybierz język, na który chcesz przetłumaczyć.
-   **P: Po instalacji widzę pustą stronę lub błąd. Co jest nie tak?**

    -   **O:** Często wskazuje to na błąd PHP.
        1.  **Sprawdź logi błędów PHP:** Panel sterowania Twojego hostingu zazwyczaj zapewnia dostęp do logów błędów PHP. Poszukaj ostatnich wpisów związanych z PrestaShop.
        2.  **Włącz tryb debugowania PrestaShop:** Przejdź do `config/defines.inc.php` w swojej instalacji PrestaShop, znajdź `define('_PS_MODE_DEV_', false);` i zmień `false` na `true`. Spowoduje to wyświetlenie błędu na ekranie.
        3.  **Kompatybilność modułu:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej wersji PrestaShop (np. PS 8.x, 1.7.x).
        4.  **Skontaktuj się z pomocą techniczną:** Jeśli nie możesz rozwiązać problemu, podaj komunikat o błędzie do pomocy technicznej MyPresta.eu.

## 3. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 3.1 Przegląd architektury

Moduł „Podziel koszyk na osobne przesyłki” (`multishipsplit`) jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop, z znacznym wykorzystaniem hooków i nadpisań w celu głębokiej integracji z procesem realizacji zamówienia. Wprowadza solidny silnik oparty na regułach do dzielenia koszyka, umożliwiając złożone warunki i działania. Podstawowa logika obraca się wokół dzielenia obiektu `Cart` na wiele encji `MultishipShipmentGroup`, z których każda reprezentuje odrębną paczkę z własnym wyborem przewoźnika. Wykorzystuje `ObjectModel` do zarządzania regułami i danymi podziału oraz stosuje serię klas usługowych do obsługi skomplikowanej logiki oceny warunków, budowania działań i prezentacji realizacji zamówienia. Nadpisania są używane do modyfikowania podstawowego zachowania `Cart` i `PaymentModule` w celu obsługi wielu przesyłek.

### 3.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `multishipsplit/controllers/front/groups.php`
    -   **Nazwa klasy:** `MultishipsplitGroupsModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje żądania AJAX związane z grupami przesyłek podczas realizacji zamówienia. Może to obejmować aktualizację wyborów przewoźników dla konkretnej grupy, ponowne obliczanie kosztów wysyłki lub pobieranie opcji punktów odbioru. Przetwarza dane `POST` i zwraca odpowiedzi JSON na stronę realizacji zamówienia.
-   `multishipsplit/controllers/front/index.php`
    -   **Nazwa klasy:** `MultishipsplitIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Kontroler zastępczy lub punkt wejścia. Może być używany do ogólnych działań front-office związanych z modułem lub przekierowań, chociaż jego podstawowa funkcja może być minimalna, jeśli większość interakcji jest oparta na AJAX poprzez `groups.php`.
-   `multishipsplit/controllers/front/pickup.php`
    -   **Nazwa klasy:** `MultishipsplitPickupModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Zarządza interakcjami AJAX specjalnie dla wyboru punktu odbioru. Prawdopodobnie obsługuje żądania wyświetlania dostępnych punktów odbioru dla danego przewoźnika i adresu oraz zapisywania wybranego punktu odbioru do koszyka lub sesji.

#### Kontrolery administracyjne Back-Office

-   `multishipsplit/controllers/admin/AdminMultishipRules.php`
    -   **Nazwa klasy:** `AdminMultishipRulesController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** „Reguły podziału przesyłek”
    -   **Zarządzana encja:** `MultishipGroupingRule` (mapuje na tabelę `mss_grouping_rule`)
    -   **Odpowiedzialność:** Zapewnia interfejs CRUD (Create, Read, Update, Delete) do zarządzania regułami grupowania przesyłek. Obsługuje wyświetlanie listy reguł, formularz dodawania/edycji reguł (w tym konstruktory warunków i działań) oraz zapisywanie/usuwanie danych reguł.
-   `multishipsplit/controllers/admin/AdminMultishipSplits.php`
    -   **Nazwa klasy:** `AdminMultishipSplitsController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** „Podziały przesyłek”
    -   **Zarządzana encja:** `MultishipSplitGroup` (mapuje na tabelę `mss_split_group`)
    -   **Odpowiedzialność:** Wyświetla listę wszystkich zamówień, które zostały przetworzone i podzielone przez moduł. Zapewnia widok tylko do odczytu grup podziału w ramach każdego zamówienia, łącząc z powrotem do oryginalnego zamówienia PrestaShop.
-   `multishipsplit/controllers/admin/index.php`
    -   **Nazwa klasy:** `MultishipsplitIndexModuleAdminController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** „Pulpit nawigacyjny podziału przesyłek”
    -   **Zarządzana encja:** N/A (widok pulpitu nawigacyjnego)
    -   **Odpowiedzialność:** Służy jako kontroler pulpitu nawigacyjnego, wyświetlając KPI, wykresy i ostatnie podzielone zamówienia. Agreguje dane z tabel modułu, aby zapewnić przegląd jego aktywności.

### 3.3 Klasy i modele rdzenia (`classes/`)

-   `multishipsplit/classes/MultishipActionBuilder.php`
    -   **Odpowiedzialność:** Klasa usługowa odpowiedzialna za konstruowanie i interpretowanie działań zdefiniowanych w `MultishipGroupingRule`. Tłumaczy konfigurację działania reguły na logikę wykonywalną.
-   `multishipsplit/classes/MultishipCartSlicer.php`
    -   **Odpowiedzialność:** Centralna klasa dla logiki dzielenia koszyka. Przyjmuje obiekt `Cart` i, używając zdefiniowanych `MultishipGroupingRule`s, dzieli produkty koszyka na tablicę obiektów `MultishipShipmentGroup`.
-   `multishipsplit/classes/MultishipCheckoutPresenter.php`
    -   **Odpowiedzialność:** Przygotowuje dane dla strony realizacji zamówienia w front-office. Przyjmuje `MultishipShipmentGroup`s i formatuje je do wyświetlenia, w tym dostępne przewoźniki, koszty i opcje punktów odbioru, aby były renderowane przez szablony Smarty.
-   `multishipsplit/classes/MultishipCompatibility.php`
    -   **Odpowiedzialność:** Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop lub potencjalnych konfliktów z innymi modułami. Zapewnia prawidłowe działanie modułu w różnych środowiskach.
-   `multishipsplit/classes/MultishipConditionBuilder.php`
    -   **Odpowiedzialność:** Podobnie jak `MultishipActionBuilder`, ale dla warunków reguł. Konstruuje i interpretuje warunki, które określają, kiedy `MultishipGroupingRule` powinien być zastosowany.
-   `multishipsplit/classes/MultishipConditionEvaluator.php`
    -   **Odpowiedzialność:** Ocenia zestaw warunków w danym kontekście (np. produkt, koszyk, klient) w celu określenia, czy reguła powinna zostać uruchomiona.
-   `multishipsplit/classes/MultishipConditionTree.php`
    -   **Odpowiedzialność:** Zarządza hierarchiczną strukturą warunków (np. grupy AND/OR) w ramach reguły, umożliwiając złożone wyrażenia logiczne.
-   `multishipsplit/classes/MultishipConfirmationPresenter.php`
    -   **Odpowiedzialność:** Przygotowuje dane do wyświetlania podsumowania podziału na stronie potwierdzenia zamówienia.
-   `multishipsplit/classes/MultishipDashboardPresenter.php`
    -   **Odpowiedzialność:** Gromadzi i formatuje dane dla pulpitu nawigacyjnego Back Office, w tym KPI i dane wykresów.
-   `multishipsplit/classes/MultishipGroupingEngine.php`
    -   **Odpowiedzialność:** Koordynuje cały proces grupowania oparty na regułach. Pobiera aktywne reguły, stosuje je sekwencyjnie (na podstawie priorytetu) do koszyka i zarządza tworzeniem `MultishipShipmentGroup`s.
-   `multishipsplit/classes/MultishipGroupingRule.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `mss_grouping_rule`
    -   **Pola `$definition`:** Przechowuje konfigurację dla każdej reguły podziału, w tym jej nazwę, priorytet, status aktywności oraz serializowane warunki i działania.
    -   **Kluczowe metody publiczne:** Metody do zapisywania, ładowania i zarządzania danymi reguł.
-   `multishipsplit/classes/MultishipOrderLink.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `mss_order_link`
    -   **Pola `$definition`:** Łączy zamówienie PrestaShop (`Order`) z odpowiadającymi mu `MultishipSplitGroup`s, umożliwiając modułowi śledzenie sposobu podziału zamówienia.
    -   **Kluczowe metody publiczne:** Metody do tworzenia i pobierania tych linków.
-   `multishipsplit/classes/MultishipPaymentBridge.php`
    -   **Odpowiedzialność:** Ułatwia proces płatności, gdy koszyk jest podzielony. Zapewnia, że całkowita kwota należna za wszystkie grupy przesyłek jest poprawnie przekazywana do modułu płatności i że potwierdzenie płatności poprawnie aktualizuje status wszystkich powiązanych zamówień.
-   `multishipsplit/classes/MultishipPayPlugRefundAdapter.php`
    -   **Odpowiedzialność:** Zapewnia specyficzną integrację do zwrotu kosztów podzielonych zamówień przy użyciu modułu płatności PayPlug. Sugeruje to, że moduł może mieć podobne adaptery dla innych bramek płatności.
-   `multishipsplit/classes/MultishipPickupFactory.php`
    -   **Odpowiedzialność:** Klasa fabryczna do tworzenia instancji `MultishipPickupAdapterInterface` na podstawie używanego przewoźnika lub modułu (np. dla Mondial Relay, Colissimo).
-   `multishipsplit/classes/MultishipRefundLog.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `mss_refund_log`
    -   **Pola `$definition`:** Loguje działania zwrotów związane z podzielonymi zamówieniami, szczególnie ważne, gdy w grę wchodzą częściowe zwroty lub zwroty w wielu powiązanych zamówieniach.
-   `multishipsplit/classes/MultishipRuleContext.php`
    -   **Odpowiedzialność:** Hermetyzuje kontekst (np. bieżący koszyk, klient, oceniany produkt) dla oceny reguł, ułatwiając przekazywanie odpowiednich danych do ewaluatorów warunków.
-   `multishipsplit/classes/MultishipShipmentGroup.php`
    -   **Odpowiedzialność:** Reprezentuje pojedynczą logiczną przesyłkę w podzielonym koszyku. Zawiera kolekcję `MultishipShipmentProduct`s, wybranego przewoźnika i związane z tym koszty.
-   `multishipsplit/classes/MultishipShipmentProduct.php`
    -   **Odpowiedzialność:** Reprezentuje element produktu w `MultishipShipmentGroup`, w tym jego ilość i specyficzne atrybuty istotne dla tej przesyłki.
-   `multishipsplit/classes/MultishipShippingCostAggregator.php`
    -   **Odpowiedzialność:** Oblicza całkowity koszt wysyłki, sumując koszty wszystkich indywidualnych `MultishipShipmentGroup`s.
-   `multishipsplit/classes/MultishipSplitGroup.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `mss_split_group`
    -   **Pola `$definition`:** Przechowuje szczegóły dotyczące konkretnej grupy przesyłek, która została utworzona w ramach podzielonego zamówienia. Jest to używane do śledzenia i raportowania w Back Office.
-   `multishipsplit/classes/MultishipSplitOrchestrator.php`
    -   **Odpowiedzialność:** Wysokopoziomowy orkiestrator dla całego procesu podziału, od początkowego dzielenia koszyka po tworzenie zamówień i obsługę płatności.
-   `multishipsplit/classes/Pickup/MultishipColissimoPickupAdapter.php`
    -   **Implementuje:** `MultishipPickupAdapterInterface`
    -   **Odpowiedzialność:** Zapewnia specyficzną logikę integracji z punktami odbioru Colissimo.
-   `multishipsplit/classes/Pickup/MultishipMondialRelayPickupAdapter.php`
    -   **Implementuje:** `MultishipPickupAdapterInterface`
    -   **Odpowiedzialność:** Zapewnia specyficzną logikę integracji z punktami odbioru Mondial Relay.
-   `multishipsplit/classes/Pickup/MultishipPickupAdapterInterface.php`
    -   **Odpowiedzialność:** Definiuje kontrakt dla wszystkich adapterów integracji punktów odbioru, zapewniając spójny interfejs dla różnych przewoźników.
-   `multishipsplit/override/classes/Cart.php`
    -   **Odpowiedzialność:** Nadpisuje podstawowe metody `Cart` w celu przechwytywania i modyfikowania sposobu dodawania, usuwania produktów oraz obliczania kosztów wysyłki, umożliwiając działanie logiki podziału modułu. Jest to krytyczne nadpisanie.
-   `multishipsplit/override/classes/PaymentModule.php`
    -   **Odpowiedzialność:** Nadpisuje podstawowe metody `PaymentModule` w celu obsługi procesu płatności dla wielu zamówień generowanych z jednego podzielonego koszyka. Zapewnia, że pojedyncza płatność pokrywa wszystkie pod-zamówienia i że ich statusy są poprawnie aktualizowane.

### 3.4 Zasoby JavaScript (`views/js/`)

-   `multishipsplit/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania dla pól wyszukiwania, prawdopodobnie używaną w konstruktorze reguł do wybierania produktów, kategorii lub innych encji.
-   `multishipsplit/lib/searchTool/views/views/js/autocomplete.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Prawdopodobnie duplikat lub alternatywna ścieżka dla skryptu autouzupełniania, być może dla kompatybilności lub specyficznych kontekstów widoku.
-   `multishipsplit/views/js/adminActionBuilder.js`
    -   **Zakres:** Back-office (AdminMultishipRulesController).
    -   **Szczegóły:** Zarządza dynamicznym interfejsem do budowania działań reguł (np. „Wymuś osobną przesyłkę”). Obsługuje dodawanie/usuwanie typów działań i ich powiązanych parametrów.
-   `multishipsplit/views/js/adminConditionBuilder.js`
    -   **Zakres:** Back-office (AdminMultishipRulesController).
    -   **Szczegóły:** Zarządza dynamicznym interfejsem do budowania warunków reguł. Umożliwia administratorom dodawanie wielu warunków, grupowanie ich za pomocą logiki AND/OR oraz wybieranie różnych kryteriów (produkt, kategoria itp.).
-   `multishipsplit/views/js/adminMultishipSearchTool.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Integruje narzędzie wyszukiwania autouzupełniania z formularzami administracyjnymi modułu, w szczególności do wybierania konkretnych produktów, kategorii lub innych encji podczas definiowania reguł.
-   `multishipsplit/views/js/admin_dashboard.js`
    -   **Zakres:** Back-office (AdminMultishipIndexController).
    -   **Szczegóły:** Obsługuje dynamiczne elementy i ładowanie danych dla pulpitu nawigacyjnego, potencjalnie w tym renderowanie wykresów (np. za pomocą Chart.js) i aktualizacje KPI.
-   `multishipsplit/views/js/admin_rules.js`
    -   **Zakres:** Back-office (AdminMultishipRulesController).
    -   **Szczegóły:** Ogólny JavaScript dla strony zarządzania regułami, w tym zmiana kolejności reguł metodą przeciągnij i upuść, przełączniki włączania/wyłączania oraz obsługa przesyłania formularzy.
-   `multishipsplit/views/js/checkout.js`
    -   **Zakres:** Front-office (strona realizacji zamówienia).
    -   **Szczegóły:** Jest to krytyczny skrypt dla doświadczenia front-office. Wiąże słuchaczy zdarzeń ze zmianami wyboru przewoźnika dla każdej grupy przesyłek, wysyła żądania AJAX do `groups.php` lub `pickup.php` w celu aktualizacji kosztów wysyłki lub pobrania punktów odbioru oraz dynamicznie aktualizuje całkowite podsumowanie zamówienia na stronie realizacji zamówienia. Prawdopodobnie używa `prestashop.on` dla niestandardowych zdarzeń.

### 3.5 Arkusze stylów CSS (`views/css/`)

-   `multishipsplit/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Style dla rozwijanych list autouzupełniania i pól wyszukiwania używanych w formularzach administracyjnych.
-   `multishipsplit/lib/searchTool/views/views/css/autocomplete.css`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Prawdopodobnie duplikat lub alternatywna ścieżka dla stylów autouzupełniania.
-   `multishipsplit/views/css/admin_condition_builder.css`
    -   **Zakres:** Back-office (AdminMultishipRulesController).
    -   **Szczegóły:** Stylizuje dynamiczny interfejs do budowania warunków w formularzu tworzenia/edycji reguł, zapewniając przejrzysty i uporządkowany układ.
-   `multishipsplit/views/css/admin_dashboard.css`
    -   **Zakres:** Back-office (AdminMultishipIndexController).
    -   **Szczegóły:** Style dla układu pulpitu nawigacyjnego, KPI, wykresów i tabeli ostatnich podziałów.
-   `multishipsplit/views/css/admin_order.css`
    -   **Zakres:** Back-office (strona widoku zamówienia).
    -   **Szczegóły:** Style dla niestandardowego widżetu lub informacji wyświetlanych w standardowym widoku zamówienia PrestaShop, pokazujące, jak zamówienie zostało podzielone.
-   `multishipsplit/views/css/admin_rules.css`
    -   **Zakres:** Back-office (AdminMultishipRulesController).
    -   **Szczegóły:** Ogólne style dla tabeli listy reguł, działań reguł (włącz/wyłącz) i ogólnego układu strony zarządzania regułami.
-   `multishipsplit/views/css/checkout.css`
    -   **Zakres:** Front-office (strona realizacji zamówienia).
    -   **Szczegóły:** Stylizuje prezentację podzielonych grup przesyłek na stronie realizacji zamówienia, w tym sposób wyświetlania przewoźników dla każdej grupy, podsumowanie kosztów i potencjalnie interfejsy wyboru punktów odbioru. Programiści mogą nadpisywać te klasy w pliku `custom.css` swojego szablonu lub modyfikując szablony modułu.

### 3.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `multishipsplit/views/templates/hook/checkout_groups.tpl`
    -   **Hook:** Prawdopodobnie `displayCarrierList` lub niestandardowy hook wstrzyknięty w krok wysyłki podczas realizacji zamówienia.
    -   **Wyniki:** Główny blok wizualny na stronie realizacji zamówienia, który wyświetla pogrupowane produkty i umożliwia klientom wybór przewoźnika dla każdej indywidualnej grupy przesyłek. To tutaj odbywa się główna interakcja front-office.
-   `multishipsplit/views/templates/hook/order_confirmation_split.tpl`
    -   **Hook:** `displayOrderConfirmation` lub podobny hook na stronie potwierdzenia zamówienia.
    -   **Wyniki:** Podsumowanie sposobu podziału zamówienia, pokazujące, które przedmioty znajdowały się w każdej przesyłce i wybranego przewoźnika, zgodnie z ustawieniem „Wyświetl podsumowanie podziału na stronie potwierdzenia zamówienia”.
-   `multishipsplit/views/templates/hook/payment_top.tpl`
    -   **Hook:** `displayPaymentTop`
    -   **Wyniki:** Potencjalnie wyświetla ostrzeżenie lub komunikat informacyjny dla klienta dotyczący podzielonego zamówienia przed przejściem do płatności, zapewniając, że rozumie, że całkowity koszt obejmuje wiele opłat za wysyłkę.

#### Szablony administracyjne (`views/templates/admin/`)

-   `multishipsplit/lib/searchTool/views/scripts.tpl`
    -   **Wyniki:** Blok skryptów Smarty dla narzędzia wyszukiwania, prawdopodobnie zawierający pliki JavaScript i CSS.
-   `multishipsplit/lib/searchTool/views/views/scripts.tpl`
    -   **Wyniki:** Duplikat lub alternatywna ścieżka dla skryptów narzędzia wyszukiwania.
-   `multishipsplit/views/templates/admin/actionBuilder.tpl`
    -   **Wyniki:** Struktura HTML dla dynamicznego interfejsu konstruktora działań w formularzu tworzenia/edycji reguł.
-   `multishipsplit/views/templates/admin/dashboard_chart.tpl`
    -   **Wyniki:** Szablon do renderowania konkretnego wykresu na pulpicie nawigacyjnym, prawdopodobnie przy użyciu biblioteki wykresów JavaScript.
-   `multishipsplit/views/templates/admin/dashboard_kpi_strip.tpl`
    -   **Wyniki:** Szablon dla paska kluczowych wskaźników wydajności (KPI) na górze pulpitu nawigacyjnego.
-   `multishipsplit/views/templates/admin/dashboard_recent_splits.tpl`
    -   **Wyniki:** Szablon do wyświetlania listy ostatnio podzielonych zamówień na pulpicie nawigacyjnym.
-   `multishipsplit/views/templates/admin/dashboard_stats.tpl`
    -   **Wyniki:** Ogólny blok statystyk na pulpicie nawigacyjnym.
-   `multishipsplit/views/templates/admin/menu.tpl`
    -   **Wyniki:** Definiuje niestandardowe elementy menu modułu w nawigacji Panelu administracyjnego PrestaShop (np. w sekcji „Wysyłka”).
-   `multishipsplit/views/templates/admin/order_split_widget.tpl`
    -   **Wyniki:** Niestandardowy widżet lub blok wyświetlany w standardowej stronie szczegółów zamówienia PrestaShop w Back Office, przedstawiający podsumowanie sposobu podziału tego konkretnego zamówienia.
-   `multishipsplit/views/templates/admin/policyConditionBuilder.tpl`
    -   **Wyniki:** Struktura HTML dla dynamicznego interfejsu konstruktora warunków w formularzu tworzenia/edycji reguł.
-   `multishipsplit/views/templates/admin/split_view.tpl`
    -   **Wyniki:** Szczegółowy widok dla konkretnego podzielonego zamówienia, potencjalnie dostępny z listy „Podziały przesyłek”.

### 3.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_mss_grouping_rule`: Przechowuje definicje wszystkich reguł grupowania przesyłek utworzonych przez administratora.
    -   `id_mss_grouping_rule` (PK)
    -   `name` (VARCHAR)
    -   `priority` (INT)
    -   `active` (TINYINT)
    -   `conditions` (TEXT - serializowana tablica/JSON warunków)
    -   `actions` (TEXT - serializowana tablica/JSON działań)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_mss_split_group`: Przechowuje szczegóły każdej indywidualnej grupy przesyłek utworzonej dla podzielonego zamówienia.
    -   `id_mss_split_group` (PK)
    -   `id_order` (FK do `ps_orders`)
    -   `id_cart` (FK do `ps_cart`)
    -   `id_carrier` (FK do `ps_carrier`)
    -   `shipping_cost_tax_excl` (DECIMAL)
    -   `shipping_cost_tax_incl` (DECIMAL)
    -   `products` (TEXT - serializowana tablica produktów w tej grupie)
    -   `pickup_point_data` (TEXT - serializowane dane dla punktu odbioru, jeśli wybrano)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_mss_order_link`: Łączy pojedyncze `id_order` PrestaShop (zamówienie „rodzicielskie”) z wieloma `id_order`s (zamówienia „dziecięce” utworzone dla każdej podzielonej przesyłki).
    -   `id_mss_order_link` (PK)
    -   `id_parent_order` (FK do `ps_orders`)
    -   `id_child_order` (FK do `ps_orders`)
    -   `id_mss_split_group` (FK do `ps_mss_split_group`)
    -   `date_add` (DATETIME)
-   `ps_mss_refund_log`: Loguje zdarzenia zwrotów związane z podzielonymi zamówieniami.
    -   `id_mss_refund_log` (PK)
    -   `id_order` (FK do `ps_orders`)
    -   `id_order_slip` (FK do `ps_order_slip`)
    -   `amount` (DECIMAL)
    -   `reason` (TEXT)
    -   `date_add` (DATETIME)
-   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `MULTISHIPSPLIT_ENABLED`, `MULTISHIPSPLIT_DEBUG_MODE` itp.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` wszystkich stron front-office. | Wstrzykiwanie zasobów CSS i JS dla funkcjonalności front-office (np. `checkout.js`, `checkout.css`). |
| `displayBackOfficeHeader` | W sekcji `<head>` wszystkich stron back-office. | Wstrzykiwanie zasobów CSS i JS dla kontrolerów administracyjnych (np. `admin_rules.js`, `admin_condition_builder.css`). |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Back Office. | Potencjalnie dodaje zakładkę lub sekcję do konfiguracji reguł podziału specyficznych dla produktu lub nadpisań. |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka. | Przechwytuje modyfikacje koszyka, aby wywołać logikę podziału i ponownie obliczyć grupy wysyłkowe. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Przetwarza podzielony koszyk na wiele zamówień PrestaShop, łączy je i przechowuje dane grup podziału. |
| `actionOrderSlipAdd` | Gdy dodawany jest bon zwrotny (zwrot). | Obsługuje logikę zwrotów dla podzielonych zamówień, potencjalnie logując częściowe zwroty w powiązanych zamówieniach. |
| `displayCarrierList` | Na etapie wysyłki podczas realizacji zamówienia, gdzie wyświetlane są opcje przewoźników. | Zastępuje lub uzupełnia standardową listę przewoźników interfejsem wyboru pogrupowanych przesyłek (`checkout_groups.tpl`). |
| `displayOrderConfirmation` | Na końcowej stronie potwierdzenia zamówienia. | Wyświetla podsumowanie podzielonego zamówienia klientowi (`order_confirmation_split.tpl`). |
| `displayPaymentTop` | Przed wyborem metody płatności na stronie realizacji zamówienia. | Może wyświetlać ważne komunikaty lub podsumowania dotyczące podzielonych kosztów wysyłki (`payment_top.tpl`). |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w Back Office. | Wstrzykuje `order_split_widget.tpl`, aby pokazać, jak konkretne zamówienie zostało podzielone. |
| `actionObjectCartUpdateAfter` | Po zaktualizowaniu obiektu Cart. | Podobnie jak `actionCartSave`, zapewnia ponowną ocenę logiki podziału. |
| `actionObjectOrderAddAfter` | Po dodaniu nowego obiektu Order. | Służy do finalizacji łączenia zamówień rodzicielskich/dziecięcych i danych grup podziału. |
| `actionObjectOrderUpdateAfter` | Po zaktualizowaniu obiektu Order. | Potencjalnie aktualizuje statusy grup podziału lub powiązane dane, jeśli zamówienie zostanie zmodyfikowane. |
| `actionFrontControllerSetMedia` | Przed renderowaniem zawartości przez kontroler front-office. | Zapewnia załadowanie niezbędnych plików JS/CSS dla stron front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem zawartości przez kontroler administracyjny. | Zapewnia załadowanie niezbędnych plików JS/CSS dla stron back-office. |
| `displayAdminStatsModules` | Na stronie Moduły > Statystyki. | Potencjalnie dodaje statystyki specyficzne dla modułu do pulpitu nawigacyjnego PrestaShop. |
| `displayDashboardTop` | Na górze pulpitu nawigacyjnego PrestaShop. | Może wyświetlać szybkie podsumowanie lub alert z modułu. |
| `displayDashboardZoneOne` | W pierwszej strefie pulpitu nawigacyjnego PrestaShop. | Może wyświetlać widżet specyficzny dla modułu na pulpicie nawigacyjnym. |
| `displayDashboardZoneTwo` | W drugiej strefie pulpitu nawigacyjnego PrestaShop. | Może wyświetlać widżet specyficzny dla modułu na pulpicie nawigacyjnym. |

## 4. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu.

-   **Aktualizacje modułu:** Zaloguj się na [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/), aby pobrać najnowszą wersję modułu „Podziel koszyk na osobne przesyłki”.
-   **Wsparcie techniczne:** Jeśli napotkasz jakiekolwiek problemy lub masz pytania, które nie są objęte tym przewodnikiem, otwórz zgłoszenie do pomocy technicznej za pośrednictwem swojego konta klienta MyPresta.eu. Nasz zespół jest gotowy do pomocy.

## 5. ## Galeria

![Pulpit nawigacyjny na stronie konfiguracji modułu, który pokazuje statystyki modułu](https://mypresta.eu/docs/images/docs/02-shipping-multi-carrier-order-split_1791740311.webp)
