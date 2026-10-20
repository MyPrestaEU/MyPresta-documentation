---
title: "Dostępność przewoźnika według wartości koszyka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop „Dostępność przewoźnika według wartości koszyka” od MyPresta.eu."
sidebar:
  label: "Dostępność przewoźnika według wartości koszyka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Carrier availability by cart value na MyPresta.eu](https://mypresta.eu/modules/ordering-process/carrier-availability-by-cart-value.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/carrier-availability-by-cart-value/)
>
> ---


# Dostępność przewoźnika według wartości koszyka

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu.

-   **Co robi to ustawienie:** Ten ekran obsługuje głównie ogólne ustawienia modułu, często związane z aktualizacjami lub podstawową funkcjonalnością.
-   **Efekt zmiany tego ustawienia:**
    -   `mypresta_updates`: Jest to wspólne ustawienie dla modułów MyPresta.eu.
        -   *Gdy włączone:* Moduł będzie okresowo sprawdzał dostępność nowych wersji i aktualizacji z MyPresta.eu. Pomaga to być na bieżąco z poprawkami błędów i nowymi funkcjami.
        -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał aktualizacji. Musiałbyś ręcznie sprawdzać dostępność nowych wersji na MyPresta.eu.
    -   `update_` i `updatev_`: Są to wewnętrzne ustawienia używane przez mechanizm aktualizacji modułu do śledzenia ostatniego sprawdzenia i dostępnej wersji. Zazwyczaj nie musisz z nimi bezpośrednio wchodzić w interakcje.
-   **Zalecana wartość:**
    -   Dla `mypresta_updates`: **TAK** (Włączone). Zawsze zaleca się aktualizowanie modułów ze względów bezpieczeństwa, wydajności i nowych funkcji.
-   **Scenariusz sprzedawcy / przykład:** Włączenie aktualizacji zapewnia, że Twój moduł zawsze działa w najnowszej wersji, zapobiegając potencjalnym problemom z kompatybilnością z przyszłymi aktualizacjami PrestaShop lub innymi modułami.

### 2.2 Dedykowany ekran administracyjny: Zasady dostępności przewoźnika

To jest rdzeń modułu, gdzie definiujesz zasady dostępności przewoźnika na podstawie wartości koszyka.

-   **Nazwa ekranu i lokalizacja w menu:**

    -   W Panelu administracyjnym PrestaShop przejdź do **Wysyłka > Dostępność przewoźnika według wartości zamówienia**.
    -   Otworzy się nowy, dedykowany ekran, na którym możesz zarządzać swoimi zasadami.
-   **Dostępne akcje i ustawienia:**
    Ten ekran przedstawia listę istniejących zasad i umożliwia dodawanie nowych lub edytowanie/usuwanie istniejących.

    **Kolumny tabeli listy:**

    -   **ID**: Unikalny identyfikator zasady.
    -   **Przewoźnik**: Nazwa przewoźnika, do którego odnosi się zasada.
    -   **Zamówienie\_od**: Minimalna wartość koszyka, aby ten przewoźnik był dostępny.
    -   **Zamówienie\_do**: Maksymalna wartość koszyka, aby ten przewoźnik był dostępny.
    -   **Aktywny**: Przełącznik do włączania lub wyłączania zasady bez jej usuwania.

    **Dodawanie/Edytowanie zasady (pola formularza):**
    Po kliknięciu „Dodaj nową zasadę” lub edycji istniejącej, zobaczysz formularz z następującymi polami:

    -   **Dostępność przewoźnika według wartości zamówienia**: Jest to lista rozwijana, w której wybierasz konkretnego przewoźnika, do którego chcesz zastosować zasadę.

        -   *Efekt:* Zdefiniowana zasada wpłynie tylko na dostępność wybranego przewoźnika.
        -   *Zalecana wartość:* Wybierz przewoźnika, którym chcesz zarządzać.
        -   *Scenariusz sprzedawcy:* Jeśli chcesz ograniczyć „Dostawę ekspresową” do zamówień o wysokiej wartości, wybierz tutaj „Dostawę ekspresową”.
    -   **Wartość zamówienia od**: Wprowadź minimalną całkowitą wartość koszyka (w Twojej domyślnej walucie), aby ten przewoźnik był dostępny.

        -   *Efekt:* Jeśli wartość koszyka klienta jest poniżej tej kwoty, wybrany przewoźnik nie zostanie wyświetlony podczas realizacji zamówienia.
        -   *Zalecana wartość:* Wprowadź `0`, jeśli nie ma minimum, lub konkretną kwotę (np. `50.00`).
        -   *Scenariusz sprzedawcy:* Ustaw na `50.00` dla „Darmowej wysyłki”, aby pojawiała się tylko dla zamówień powyżej 50 USD.
    -   **Wartość zamówienia do**: Wprowadź maksymalną całkowitą wartość koszyka (w Twojej domyślnej walucie), aby ten przewoźnik był dostępny.

        -   *Efekt:* Jeśli wartość koszyka klienta jest powyżej tej kwoty, wybrany przewoźnik nie zostanie wyświetlony podczas realizacji zamówienia.
        -   *Zalecana wartość:* Pozostaw puste lub ustaw na `0`, jeśli nie ma maksimum, lub konkretną kwotę (np. `200.00`).
        -   *Scenariusz sprzedawcy:* Ustaw na `200.00` dla „Standardowej wysyłki”, aby zapobiec jej wyborowi dla bardzo wysokich zamówień, które powinny korzystać z „Wysyłki ubezpieczonej”.
    -   **Aktywny**: Prosty przełącznik WŁ./WYŁ.

        -   *Efekt:*
            -   *Gdy włączone:* Zasada jest aktywna i będzie filtrować dostępność przewoźnika.
            -   *Gdy wyłączone:* Zasada jest ignorowana, a przewoźnik będzie dostępny na podstawie innych ustawień PrestaShop (waga, cena, strefy) niezależnie od wartości koszyka.
        -   *Zalecana wartość:* **WŁ.** dla aktywnych zasad.
        -   *Scenariusz sprzedawcy:* Tymczasowo wyłącz zasadę podczas promocji bez jej usuwania.
    -   **Zapisz**: Kliknij ten przycisk, aby zastosować zmiany lub utworzyć nową zasadę.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zidentyfikuj swoich przewoźników:** Wypisz wszystkich swoich przewoźników i ich zamierzone zastosowania.
    2.  **Zdefiniuj zakresy wartości:** Dla każdego przewoźnika zdecyduj, czy istnieje określony zakres wartości koszyka, w którym powinien być dostępny.
        -   *Przykład 1:* „Wysyłka ekonomiczna” dla zamówień od 0 do 75 USD.
        -   *Przykład 2:* „Wysyłka standardowa” dla zamówień od 75 do 250 USD.
        -   *Przykład 3:* „Premium ubezpieczona” dla zamówień od 250 USD i więcej (ustaw „Wartość zamówienia od” na 250, pozostaw „Wartość zamówienia do” pustą/0).
    3.  **Dodaj zasady:** Przejdź do **Wysyłka > Dostępność przewoźnika według wartości zamówienia** i kliknij „Dodaj nową zasadę”.
    4.  **Skonfiguruj każdą zasadę:** Wybierz przewoźnika, wprowadź „Wartość zamówienia od” i „Wartość zamówienia do” oraz upewnij się, że „Aktywny” jest WŁ.
    5.  **Dokładnie przetestuj:** Po skonfigurowaniu zasad, wykonaj testowe zakupy z różnymi wartościami koszyka, aby upewnić się, że przewoźnicy są wyświetlani zgodnie z oczekiwaniami.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | `mypresta_updates` | TAK (Włączone) | Włącza automatyczne sprawdzanie aktualizacji modułu. |
| Zasady dostępności przewoźnika | Przewoźnik | Wybierz z listy | Konkretny przewoźnik, do którego odnosi się ta zasada. |
| Zasady dostępności przewoźnika | Wartość zamówienia od | `0` lub konkretna kwota | Minimalna wartość koszyka, aby przewoźnik był dostępny. |
| Zasady dostępności przewoźnika | Wartość zamówienia do | `0` (bez maks.) lub konkretna kwota | Maksymalna wartość koszyka, aby przewoźnik był dostępny. |
| Zasady dostępności przewoźnika | Aktywny | WŁ. | Włącza lub wyłącza konkretną zasadę dostępności przewoźnika. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem zasady, ale przewoźnicy nie zmieniają się w kasie. Co jest nie tak?**
O1:

-   **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji modułu. Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
-   **Konflikty zasad:** Sprawdź, czy nie masz sprzecznych zasad. Na przykład, jeśli Przewoźnik A jest ustawiony od 0 do 100 USD, a Przewoźnik B od 50 do 150 USD, upewnij się, że Twoje zakresy są logiczne.
-   **Status przewoźnika:** Upewnij się, że sami przewoźnicy są aktywni i prawidłowo skonfigurowani w **Wysyłka > Przewoźnicy** w PrestaShop. Ten moduł filtruje tylko *dostępnych* przewoźników, nie aktywuje nieaktywnych.
-   **Inne ograniczenia przewoźnika:** Pamiętaj, że PrestaShop ma własne ograniczenia przewoźników (według strefy, wagi, ceny). Ten moduł *dodaje* kolejną warstwę filtrowania. Jeśli przewoźnik jest już ograniczony wagą, ten moduł nie udostępni go.

**P2: Mój symbol waluty nie wyświetla się poprawnie lub wartości wydają się być błędne.**
O2: Moduł używa domyślnej waluty Twojego sklepu dla pól „Wartość zamówienia od” i „Wartość zamówienia do”. Upewnij się, że Twoja domyślna waluta jest poprawnie ustawiona w **Lokalizacja > Waluty**. Moduł działa na wartości liczbowej, więc symbol wyświetlany w panelu administracyjnym służy do Twojej referencji.

**P3: Czy mogę używać tego modułu z innymi modułami wysyłki?**
O3: Tak, zazwyczaj. Ten moduł integruje się ze standardowym procesem PrestaShop do filtrowania list przewoźników. Zastosuje swoje zasady *po* tym, jak inne podstawowe warunki PrestaShop (takie jak waga, cena, strefa) już zawęziły listę potencjalnych przewoźników. Jeśli inny moduł również filtruje przewoźników, zastosowane zostaną najbardziej restrykcyjne zasady ze wszystkich modułów.

**P4: Jak sprawić, aby przewoźnik był *zawsze* dostępny, niezależnie od wartości koszyka?**
O4: Nie musisz tworzyć zasady dla takiego przewoźnika. Jeśli przewoźnik nie jest wymieniony w Twoich zasadach „Dostępność przewoźnika według wartości zamówienia”, pozostanie dostępny na podstawie domyślnych ustawień przewoźnika PrestaShop (waga, cena, strefa itp.) bez żadnych ograniczeń wartości koszyka z tego modułu.

**P5: Moduł wydaje się spowalniać moją kasę. Czy to normalne?**
O5: Ten moduł został zaprojektowany tak, aby był lekki i nie powinien znacząco wpływać na wydajność. Jeśli zauważysz spowolnienie, upewnij się, że Twoja instalacja PrestaShop jest zoptymalizowana (np. włączone buforowanie, najnowsza wersja PHP, brak nadmiernych modułów). Jeśli problem będzie się utrzymywał, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojej konfiguracji.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Dostępność przewoźnika według wartości koszyka” (`cbp`) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie `AdminController` do konfiguracji i hook Front-Office do modyfikowania listy przewoźników podczas realizacji zamówienia. Używa niestandardowego `ObjectModel` do zarządzania zasadami dostępności przewoźników we własnej tabeli bazy danych.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    Ten moduł nie zawiera żadnych dedykowanych kontrolerów Front-Office. Cała logika Front-Office jest obsługiwana bezpośrednio za pomocą hooka w głównym pliku modułu (`cbp.php`).
-   **Kontrolery Back-Office Admin**:

    -   `cbp/controllers/admin/AdminCbpr.php`

        -   **Nazwa klasy:** `AdminCbprController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność:** Jest to główny interfejs administracyjny do zarządzania zasadami dostępności przewoźników. Obsługuje operacje CRUD (Create, Read, Update, Delete) dla encji `cbpr`.
        -   **Nazwa zakładki:** „Dostępność przewoźnika według wartości zamówienia” (w menu Wysyłka).
        -   **Zarządzana encja:** `Cbpr` (niestandardowy `ObjectModel` dla zasad przewoźników).
        -   **Kluczowe funkcje:**
            -   Wyświetla widok `list` wszystkich skonfigurowanych zasad, w tym ID, nazwę przewoźnika, Order\_from, Order\_to i status Aktywny.
            -   Zapewnia formularze `add` i `edit` dla poszczególnych zasad, umożliwiając wybór przewoźnika i wprowadzenie minimalnych/maksymalnych wartości zamówienia.
            -   Obsługuje przesyłanie formularzy i interakcje z bazą danych w celu zapisywania i aktualizowania zasad.
            -   Wykorzystuje `PS_CURRENCY_DEFAULT` do wyświetlania informacji o walucie w formularzach.
    -   `cbp/controllers/admin/index.php`

        -   **Odpowiedzialność:** Ten plik jest standardowym pustym plikiem `index.php`, zazwyczaj dołączanym do katalogów PrestaShop w celu zapobiegania listowaniu katalogów ze względów bezpieczeństwa. Nie zawiera żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy i modele rdzenia (`classes/`)

Moduł nie posiada dedykowanego katalogu `classes/`. Główny `ObjectModel` do zarządzania zasadami przewoźników jest prawdopodobnie zdefiniowany bezpośrednio w głównym pliku modułu (`cbp/cbp.php`) lub niejawnie obsługiwany przez `AdminCbprController` za pomocą dynamicznej definicji `ObjectModel`.

Biorąc pod uwagę, że `AdminCbprController` zarządza tabelą o nazwie `cbpr`, musi istnieć klasa `ObjectModel`, prawdopodobnie o nazwie `Cbpr`, zdefiniowana gdzieś. Ta klasa definiowałaby strukturę zasad dostępności przewoźników.

**Zakładany `Cbpr` ObjectModel (prawdopodobnie w `cbp.php`):**

-   **Nazwa klasy:** `Cbpr` (rozszerza `ObjectModel`)
-   **Tabela bazy danych:** `ps_cbpr` (lub `_cbpr` z prefiksem)
-   **Pola `$definition` (oczekiwane):**
    -   `id_cbpr`: Klucz podstawowy.
    -   `id_carrier`: Klucz obcy do tabeli `ps_carrier`.
    -   `order_from`: Pole dziesiętne dla minimalnej wartości koszyka.
    -   `order_to`: Pole dziesiętne dla maksymalnej wartości koszyka.
    -   `active`: Pole boolean dla statusu zasady.
-   **Kluczowe metody:** Standardowe metody `ObjectModel` dla `add()`, `update()`, `delete()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript w `views/js/`. Cała logika Front-Office jest obsługiwana po stronie serwera za pomocą hooków PHP. Formularze Back-Office opierają się na domyślnej obsłudze formularzy PrestaShop i jQuery.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS w `views/css/`. Interfejs Back-Office wykorzystuje domyślne style PrestaShop dla formularzy i list `ModuleAdminController`. Zmiany w Front-Office są obsługiwane przez filtrowanie listy przewoźników bezpośrednio w PHP, a nie przez renderowanie nowych szablonów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie zawiera żadnych niestandardowych plików szablonów Smarty w `views/templates/`. Formularze konfiguracji i listy w Back-Office są renderowane przy użyciu domyślnych szablonów `ModuleAdminController` PrestaShop. Zmiany w Front-Office są obsługiwane przez filtrowanie listy przewoźników bezpośrednio w PHP, a nie przez renderowanie nowych szablonów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_cbpr`: Ta tabela przechowuje zasady dostępności przewoźników.

        -   `id_cbpr` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_carrier` INT(10) UNSIGNED NOT NULL
        -   `order_from` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
        -   `order_to` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
        -   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        -   PRIMARY KEY (`id_cbpr`)
        -   KEY `id_carrier` (`id_carrier`)
    -   `ps_configuration`: Moduł przechowuje swoje ogólne ustawienia (takie jak `mypresta_updates`, `update_`, `updatev_`) w tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy `AdminController` jest inicjalizowany i jego media (JS/CSS) są ustawiane. | Używany przez moduł do rejestrowania niestandardowego `AdminController` (`AdminCbprController`) w strukturze menu PrestaShop. |
| `actionFilterDeliveryOptionList` | Wykonywany podczas procesu realizacji zamówienia, w szczególności gdy PrestaShop buduje listę dostępnych opcji dostawy. | Jest to główny hook Front-Office. Moduł używa go do iteracji po liście przewoźników, których PrestaShop już uznał za dostępnych (na podstawie stref, wagi, ceny), a następnie dodatkowo filtruje tę listę na podstawie całkowitej wartości koszyka i zasad zdefiniowanych w `ps_cbpr`. Jeśli zasada przewoźnika nie pasuje do bieżącej wartości koszyka, jest on usuwany z listy prezentowanej klientowi. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Dostępność przewoźnika według wartości koszyka”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania naszych modułów.
