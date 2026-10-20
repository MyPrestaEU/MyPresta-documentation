---
title: "VAT 0% dla wybranych grup klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „VAT 0% dla wybranych grup klientów” od MyPresta.eu."
sidebar:
  label: "VAT 0% dla wybranych grup klientów"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł VAT 0% for selected groups of customers na MyPresta.eu](https://mypresta.eu/modules/ordering-process/vat-0-for-selected-groups-of-customers.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/vat-0-for-selected-groups-of-customers/)
>
> ---


# VAT 0% dla wybranych grup klientów

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i dla sprawdzania aktualizacji modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu „VAT 0% dla wybranych grup klientów”. Strona ta jest podzielona na kilka sekcji.

#### Zakładka Ustawienia

To jest główna zakładka, w której definiujesz, które grupy klientów będą korzystać z 0% VAT.

**1. Grupy klientów, które będą miały 0% VAT**
- **Co robi to ustawienie:** To najważniejsze ustawienie. Pozwala wybrać jedną lub więcej grup klientów z Twojego sklepu PrestaShop, które będą zwolnione z VAT.
- **Efekt zmiany tego ustawienia:**
    - *Gdy wybrano jedną lub więcej grup:* Każdy klient należący do *co najmniej jednej* z wybranych grup będzie miał wszystkie ceny produktów, koszty wysyłki i sumy zamówień obliczone z 0% VAT.
    - *Gdy nie wybrano żadnych grup:* Moduł nie zastosuje żadnych zwolnień z VAT, a wszyscy klienci będą obciążani VAT zgodnie ze standardowymi zasadami podatkowymi PrestaShop.
- **Zalecana wartość:** Wybierz wszystkie grupy klientów, które mają być zwolnione z VAT (np. „Klienci hurtowi”, „Klienci B2B”).
- **Scenariusz / przykład dla sprzedawcy:** Prowadzisz sklep B2B. Masz grupę klientów o nazwie „Klienci hurtowi”, którzy są firmami zarejestrowanymi jako płatnicy VAT. Wybierzesz „Klienci hurtowi” z tej listy. Gdy klient z tej grupy zaloguje się, zobaczy wszystkie ceny bez VAT.

**2. Wybierz regułę podatkową**
- **Co robi to ustawienie:** Ta opcja pozwala określić konkretną regułę podatkową, której moduł powinien używać przy stosowaniu 0% VAT. Chociaż moduł ustawia stawkę podatku na 0%, PrestaShop często wymaga, aby do obliczeń była przypisana prawidłowa reguła podatkowa.
- **Efekt zmiany tego ustawienia:**
    - *Gdy wybrano konkretną regułę podatkową:* Moduł spróbuje użyć tej reguły podatkowej, ale ze stawką 0%, dla grup klientów zwolnionych. Może to być przydatne do zapewnienia kompatybilności z innymi modułami lub specyficznymi ustawieniami księgowymi, które oczekują, że reguła podatkowa zawsze będzie obecna.
    - *Gdy wybrano „Brak” lub nie wybrano żadnej konkretnej reguły (domyślne zachowanie):* Moduł bezpośrednio obsłuży zastosowanie 0% VAT, często poprzez nadpisanie stawki podatku na 0% bez ścisłego przestrzegania predefiniowanej reguły podatkowej, co zazwyczaj jest wystarczające.
- **Zalecana wartość:** Pozostaw jako domyślne, chyba że napotkasz specyficzne problemy z kompatybilnością z innymi modułami lub masz bardzo szczególne wymagania księgowe. Jeśli wybierzesz jedną, wybierz ogólną regułę podatkową 0% (jeśli taką posiadasz) lub standardową regułę podatkową, którą moduł może następnie nadpisać na 0%.
- **Scenariusz / przykład dla sprzedawcy:** Twój księgowy wymaga, aby wszystkie transakcje, nawet te z 0% VAT, były powiązane z konkretnym identyfikatorem reguły podatkowej do celów raportowania. Możesz utworzyć regułę podatkową „VAT 0% (Zwolniony)” w PrestaShop i wybrać ją tutaj.

#### Zakładka Naprawa hooków
Ta zakładka służy do zaawansowanego rozwiązywania problemów i zapewnienia, że hooki modułu są poprawnie zarejestrowane.

- **Co robi to ustawienie:** Ta sekcja zawiera narzędzia do ponownej rejestracji hooków modułu w przypadku, gdy zostaną one wyrejestrowane lub uszkodzone, co czasami może się zdarzyć po zmianach motywu, konfliktach modułów lub problemach z bazą danych.
- **Efekt zmiany tego ustawienia:**
    - *Kliknięcie „Napraw hooki”:* Ta akcja spróbuje ponownie zarejestrować wszystkie niezbędne hooki, których moduł używa do prawidłowego działania. Jeśli moduł nie działał zgodnie z oczekiwaniami (np. VAT nie był usuwany), może to rozwiązać problem.
- **Zalecana wartość:** Używaj tego tylko wtedy, gdy podejrzewasz, że moduł nie działa prawidłowo (np. VAT nadal jest naliczany grupom zwolnionym) i po potwierdzeniu, że Twoje główne ustawienia są poprawne.
- **Scenariusz / przykład dla sprzedawcy:** Właśnie zaktualizowałeś motyw PrestaShop, a teraz Twoi klienci zwolnieni z VAT nagle są obciążani VAT-em. Sprawdziłeś ustawienia grup i są one poprawne. Kliknięcie „Napraw hooki” tutaj może rozwiązać podstawowy problem.

#### Zakładka Aktualizacje
Ta zakładka zawiera informacje o aktualizacjach modułu.

- **Co robi to ustawienie:** Ta sekcja sprawdza dostępność aktualizacji modułu i dostarcza informacji o Twojej bieżącej wersji.
- **Efekt zmiany tego ustawienia:**
    - *Sprawdzanie aktualizacji:* Informuje Cię, czy dostępna jest nowsza wersja modułu, co pozwala na aktualizowanie modułu o najnowsze funkcje i poprawki błędów.
- **Zalecana wartość:** Okresowo sprawdzaj tę zakładkę, aby upewnić się, że używasz najnowszej wersji dla optymalnej wydajności i bezpieczeństwa.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Twój sklep zawsze działa na najbardziej stabilnym i bezpiecznym oprogramowaniu. Odwiedzasz tę zakładkę raz w miesiącu, aby sprawdzić, czy są jakieś nowe aktualizacje dla Twoich modułów MyPresta.eu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | **Grupy klientów, które będą miały 0% VAT** | Wybierz odpowiednie grupy (np. „Klienci hurtowi”) | Definiuje, które grupy klientów będą miały 0% VAT zastosowane do wszystkich cen i sum. |
| Strona konfiguracji modułu | **Wybierz regułę podatkową** | Pozostaw jako domyślne (lub wybierz regułę podatkową 0%, jeśli jest potrzebna do celów księgowych) | Powiązuje obliczenie 0% VAT z konkretną regułą podatkową dla kompatybilności lub raportowania. |
| Zakładka Naprawa hooków | **Przycisk Napraw hooki** | Używaj tylko do rozwiązywania problemów | Ponownie rejestruje hooki modułu, aby rozwiązać problemy z funkcjonalnością (np. brak usunięcia VAT). |
| Zakładka Aktualizacje | **Sprawdź aktualizacje** | Okresowo sprawdzaj | Informuje o dostępnych aktualizacjach modułu w celu uzyskania nowych funkcji i poprawek błędów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: VAT nadal jest naliczany, mimo że wybrałem grupę klientów.**
O1:
*   **Sprawdź przypisanie do grupy:** Upewnij się, że klient, którego testujesz, jest faktycznie przypisany do jednej z wybranych grup zwolnionych z VAT. Zaloguj się jako klient, przejdź do szczegółów jego konta lub sprawdź w Panelu administracyjnym w `Klienci > Klienci`.
*   **Konfiguracja modułu:** Dokładnie sprawdź, czy prawidłowe grupy są wybrane na stronie konfiguracji modułu (`Moduły > Menedżer modułów > Konfiguruj` dla „VAT 0% dla wybranych grup klientów”).
*   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (w `Zaawansowane > Wydajność`) i pamięć podręczną przeglądarki. Czasami mogą być wyświetlane stare dane.
*   **Naprawa hooków:** Przejdź do zakładki „Naprawa hooków” w konfiguracji modułu i kliknij przycisk „Napraw hooki”. Może to rozwiązać problemy, w których punkty integracji modułu z PrestaShop mogły zostać wyrejestrowane.

**P2: Czy ten moduł wpłynie na moje istniejące reguły podatkowe dla klientów niezwolnionych?**
O2: Nie, ten moduł jest zaprojektowany tak, aby *tylko* stosować 0% VAT do klientów należących do wybranych przez Ciebie grup. Dla wszystkich innych klientów będą obowiązywać standardowe reguły podatkowe i konfiguracje PrestaShop.

**P3: Czy ten moduł działa również dla kosztów wysyłki?**
O3: Tak, moduł jest zaprojektowany tak, aby stosować 0% VAT do wszystkich aspektów zamówienia, w tym cen produktów, kosztów wysyłki i wszelkich innych elementów podlegających opodatkowaniu, co skutkuje całkowitą wartością zamówienia z 0% VAT dla wybranych grup klientów.

**P4: Mam niestandardowy motyw. Czy ten moduł będzie z nim działał?**
O4: Tak, ten moduł działa poprzez modyfikowanie podstawowej logiki obliczania podatków w PrestaShop za pomocą hooków, a nie bezpośrednio zmieniając szablony front-office. Dlatego powinien być kompatybilny z większością niestandardowych motywów bez problemów. Jeśli wystąpią problemy z wyświetlaniem (np. ceny nie aktualizują się), prawdopodobnie jest to problem z pamięcią podręczną lub konflikt z innym modułem, który również mocno modyfikuje obliczenia podatkowe.

**P5: Jak przetłumaczyć tekst modułu na inne języki?**
O5: Jeśli moduł wprowadza nowe ciągi tekstowe (chociaż ten moduł działa głównie w tle), możesz je przetłumaczyć za pomocą interfejsu tłumaczeń PrestaShop:
1.  Przejdź do `Lokalizacja > Tłumaczenia`.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
3.  Wybierz swój motyw, język, a następnie wybierz „VAT 0% dla wybranych grup klientów” z listy modułów.
4.  Możesz wtedy modyfikować dowolne przetłumaczalne ciągi.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „VAT 0% dla wybranych grup klientów” działa, wykorzystując system hooków PrestaShop do przechwytywania i modyfikowania obliczeń podatkowych na różnych etapach procesu zamawiania. Wykorzystuje głównie hooki `actionTaxManager` i `actionProductPriceCalculation` do dynamicznego dostosowywania stawki podatku do 0% dla klientów należących do określonych grup. Zawiera również niestandardową klasę `TaxManager` do obsługi logiki nadpisywania podatku. Moduł jest zgodny ze standardową strukturą modułów PrestaShop, z głównym plikiem modułu, dedykowaną klasą do zarządzania podatkami i szablonami Smarty dla konfiguracji w Panelu administracyjnym.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   **`groupvat/classes/GroupvatTaxManager.php`**
    *   **Nazwa klasy:** `GroupvatTaxManager`
    *   **Klasa nadrzędna:** `TaxManager` (podstawowa klasa `TaxManager` PrestaShop)
    *   **Odpowiedzialność:** Ta klasa jest rdzeniem funkcjonalności modułu. Rozszerza domyślny `TaxManager` PrestaShop, aby nadpisać jego zachowanie. Jej główna metoda, `getTaxCalculator()`, jest kluczowa. Gdy klient zostanie zidentyfikowany jako należący do grupy zwolnionej z VAT, ta klasa zapewnia, że `TaxCalculator` zwraca stawkę podatku 0%, skutecznie usuwając VAT z cen. Zawiera również logikę sprawdzającą, czy bieżący klient należy do jednej ze skonfigurowanych grup zwolnionych.
    *   **Kluczowe metody:**
        *   `getTaxCalculator(array $params)`: Nadpisuje domyślny kalkulator podatkowy, aby zwrócić stawkę podatku 0%, jeśli klient należy do grupy zwolnionej.
        *   `isCustomerInGroup(int $id_customer)`: Metoda pomocnicza do określania, czy dany identyfikator klienta należy do którejkolwiek ze skonfigurowanych grup zwolnionych z VAT.

-   **`groupvat/classes/index.php`**
    *   **Odpowiedzialność:** Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)
Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)
Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja konfiguracji Panelu administracyjnego jest obsługiwana przez domyślny motyw administracyjny PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`groupvat/views/templates/admin/configure.tpl`**
    *   **Zakres:** Konfiguracja Panelu administracyjnego.
    *   **Cel:** To jest główny szablon strony konfiguracji modułu, renderowany przez `getContent()` w `groupvat.php`. Zawiera inne szablony dla konkretnych sekcji, takich jak wybór grupy klientów i naprawa hooków. Zazwyczaj obejmuje cały formularz konfiguracji.

-   **`groupvat/views/templates/admin/customerGroups.tpl`**
    *   **Zakres:** Konfiguracja Panelu administracyjnego.
    *   **Cel:** Ten szablon renderuje sekcję, w której sprzedawca wybiera grupy klientów, które będą miały 0% VAT. Wyświetla listę dostępnych grup klientów z polami wyboru.
    *   **Zmienne:** Prawdopodobnie używa `$groups` (tablica grup klientów), `$selected_groups` (tablica identyfikatorów aktualnie wybranych grup), `$tax_rules` (tablica dostępnych reguł podatkowych), `$selected_tax_rule` (identyfikator aktualnie wybranej reguły podatkowej).

-   **`groupvat/views/templates/admin/hooksRepair.tpl`**
    *   **Zakres:** Konfiguracja Panelu administracyjnego.
    *   **Cel:** Ten szablon renderuje sekcję „Naprawa hooków”, udostępniając przycisk do ponownej rejestracji hooków modułu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy niestandardowych tabel bazy danych.
    *   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop.
        *   `groupvat_groups`: Przechowuje listę identyfikatorów grup klientów oddzielonych przecinkami, wybranych do zwolnienia z VAT.
        *   `groupvat_tax`: Przechowuje identyfikator wybranej reguły podatkowej (jeśli istnieje).
        *   `mypresta_updates`: Przechowuje informacje związane z aktualizacjami modułu.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionDispatcher` | Przed wysłaniem kontrolera. | Używany do potencjalnego nadpisywania lub modyfikowania zachowania wysyłki, choć często używany do ogólnej konfiguracji. |
| `ActionDispatcher` | (Alias `actionDispatcher`) | To samo co powyżej. |
| `actionCartGetPackageShippingCost` | Podczas obliczania kosztów wysyłki dla paczki w koszyku. | Kluczowy dla zapewnienia, że koszty wysyłki są również obliczane z 0% VAT dla grup zwolnionych. |
| `displayTaxManager` | (Przestarzałe/mniej powszechne) | Historycznie używane do wyświetlania informacji związanych z podatkami. |
| `ActionGetProductPropertiesAfter` | Po pobraniu właściwości produktu. | Pozwala na modyfikację danych produktu, w tym ceny i podatku, przed wyświetleniem. |
| `taxManager` | (Przestarzałe/mniej powszechne) | Historycznie używane do zarządzania podatkami. |
| `ActionAuthentication` | Po uwierzytelnieniu klienta (zalogowaniu). | Może być używane do ustawiania zmiennych sesji lub wykonywania działań na podstawie grupy klienta po zalogowaniu. |
| `ActionTaxManager` | Gdy klasa `TaxManager` jest instancjonowana lub wywoływane są jej metody. | **Główny hook dla tego modułu.** Pozwala modułowi wstrzyknąć niestandardowy `GroupvatTaxManager` lub zmodyfikować logikę obliczania podatku. |
| `ActionPresentCart` | Przed przedstawieniem koszyka użytkownikowi. | Pozwala na modyfikację danych koszyka, w tym cen i sum, przed renderowaniem. |
| `ActionProductPriceCalculation` | Podczas procesu obliczania ceny produktu. | **Główny hook dla tego modułu.** Pozwala modułowi modyfikować stawkę podatku stosowaną do cen produktów. |
| `actionGetProductPropertiesAfter` | (Alias `ActionGetProductPropertiesAfter`) | To samo co powyżej. |
| `ActionFilterDeliveryOptionList` | Przed wyświetleniem listy opcji dostawy. | Pozwala na modyfikację opcji dostawy, potencjalnie wpływając na ich ceny (a tym samym na podatek). |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnego wsparcia, aktualizacji i najnowszych wersji modułu „VAT 0% dla wybranych grup klientów” prosimy odwiedzić swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
