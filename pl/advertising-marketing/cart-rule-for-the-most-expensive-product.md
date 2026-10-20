---
title: "Zasada koszyka dla najdroższego produktu - instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zasada koszyka dla najdroższego produktu” od MyPresta.eu."
sidebar:
  label: "Zasada koszyka dla najdroższego produktu"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cart rule for the most expensive product na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-rule-for-the-most-expensive-product.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/cart-rule-for-the-most-expensive-product/)
>
> ---


# Zasada koszyka dla najdroższego produktu

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknij „Konfiguruj” obok modułu w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji modułu „Zasada koszyka dla najdroższego produktu”.

#### Ustawienia i opcje:

-   **Aktualizacje na żywo MyPresta.eu (mypresta_updates)**
    -   **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł może sprawdzać aktualizacje bezpośrednio z MyPresta.eu. Pomaga to zapewnić, że zawsze używasz najnowszej wersji z poprawkami błędów i nowymi funkcjami.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie okresowo łączyć się z MyPresta.eu, aby sprawdzić dostępność nowych wersji. Jeśli aktualizacja jest dostępna, możesz zobaczyć powiadomienie w panelu administracyjnym PrestaShop.
        -   *Gdy wyłączone (NIE):* Moduł nie będzie automatycznie sprawdzać aktualizacji. Będziesz musiał ręcznie sprawdzać i pobierać aktualizacje ze swojego konta MyPresta.eu.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia terminowe powiadomienia o krytycznych aktualizacjach, poprawiając bezpieczeństwo i kompatybilność bez ręcznego wysiłku.

-   **Wykluczone produkty (csc_excluded_products)**
    -   **Co robi to ustawienie:** To pole pozwala określić produkty, które *nigdy* nie powinny być brane pod uwagę przy obliczaniu rabatu na „najdroższy produkt”, nawet jeśli są rzeczywiście najdroższymi produktami w koszyku. Jest to przydatne dla produktów o bardzo niskich marżach, specjalnych promocji lub przedmiotów, których nie chcesz przeceniać.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzone są identyfikatory produktów:* Moduł zignoruje te konkretne produkty podczas określania, który produkt jest „najdroższy” dla zasady koszyka. Jeśli jeden z tych wykluczonych produktów jest najdroższy, moduł będzie szukał następnego najdroższego produktu *niewykluczonego*, aby zastosować rabat.
        -   *Gdy pozostawione puste:* Wszystkie produkty w koszyku są kwalifikowane do identyfikacji jako „najdroższe” dla rabatu.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne produkty, które chcesz wykluczyć.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz bardzo popularny produkt o wysokiej marży (ID 123) i kilka produktów „wabików” (ID 456, ID 789). Chcesz, aby rabat na „najdroższy produkt” dotyczył produktów o wysokiej marży, ale nie „wabików”. Wprowadziłbyś `456,789` (identyfikatory produktów oddzielone przecinkami) w tym polu.

#### 2.1.1 Strona edycji zasady koszyka (Panel administracyjny > Katalog > Rabaty > Zasady koszyka > Dodaj nową / Edytuj)
Ten moduł dodaje nową opcję bezpośrednio do standardowej strony tworzenia/edycji zasady koszyka PrestaShop. Znajdziesz tę opcję podczas tworzenia lub modyfikowania zasady koszyka, która wykorzystuje **rabat procentowy**.

-   **Lokalizacja menu:** Panel administracyjny > Katalog > Rabaty > Zasady koszyka. Kliknij „Dodaj nową zasadę koszyka” lub edytuj istniejącą.
-   **Dostępna akcja:** Na zakładce „Akcje” konfiguracji zasady koszyka, po wybraniu „Procent” dla opcji „Zastosuj rabat”, pojawi się nowe pole wyboru.

    -   **Zastosuj rabat tylko do najdroższego produktu**
        -   **Co robi to ustawienie:** Jest to podstawowa funkcjonalność modułu. Gdy włączone dla konkretnej zasady koszyka, rabat procentowy zdefiniowany dla tej zasady zostanie zastosowany tylko do pojedynczego najdroższego produktu w koszyku klienta.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (zaznaczone):* Rabat procentowy zasady koszyka zostanie obliczony wyłącznie na podstawie ceny najdroższego produktu w koszyku (z wyłączeniem produktów, które globalnie wykluczyłeś w głównej konfiguracji modułu).
            -   *Gdy wyłączone (niezaznaczone):* Zasada koszyka będzie działać jak standardowy rabat procentowy PrestaShop, stosując rabat do całej wartości koszyka lub do kwalifikujących się produktów zgodnie z innymi konfiguracjami zasad koszyka (np. wybór produktu, minimalna kwota).
        -   **Zalecana wartość:** Włącz to tylko dla zasad koszyka, w których wyraźnie chcesz celować w najdroższy produkt.
        -   **Scenariusz / przykład dla sprzedawcy:** Chcesz uruchomić promocję „20% zniżki na Twój największy produkt”. Tworzysz nową zasadę koszyka, ustawiasz rabat na 20% (procentowo), a następnie zaznaczasz to pole. Gdy klienci użyją tego vouchera, otrzymają 20% zniżki na swój najdroższy produkt, a nie 20% zniżki na całe zamówienie.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Konfiguracja modułu | Aktualizacje na żywo MyPresta.eu | TAK | Włącza automatyczne sprawdzanie aktualizacji modułu. |
| Konfiguracja modułu | Wykluczone produkty | Puste | Identyfikatory produktów oddzielone przecinkami, które mają być wykluczone z obliczania „najdroższego”. |
| Edycja zasady koszyka (zakładka Akcje) | Zastosuj rabat tylko do najdroższego produktu | Niezaznaczone | Po zaznaczeniu stosuje rabat procentowy tylko do najdroższego produktu w koszyku. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Rabat nie jest stosowany do najdroższego produktu lub w ogóle nie działa.**
O:
1.  **Sprawdź konfigurację zasady koszyka:** Przejdź do **Katalog > Rabaty > Zasady koszyka**, edytuj swoją zasadę i upewnij się, że na zakładce „Akcje” opcja „Zastosuj rabat” jest ustawiona na „Procent”, a pole wyboru „Zastosuj rabat tylko do najdroższego produktu” jest **zaznaczone**.
2.  **Zweryfikuj kwalifikowalność produktu:** Sprawdź główną konfigurację modułu (**Moduły > Menedżer modułów > Konfiguruj** dla „Zasada koszyka dla najdroższego produktu”). Upewnij się, że produkt, do którego spodziewasz się zastosowania rabatu, nie jest wymieniony w polu „Wykluczone produkty”.
3.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
4.  **Konflikty modułów:** Jeśli masz inne moduły, które mocno modyfikują obliczenia koszyka lub rabatów, może wystąpić konflikt. Spróbuj tymczasowo wyłączyć inne moduły związane z rabatami, aby sprawdzić, czy problem zostanie rozwiązany.

**P: Czy mogę zastosować ten rabat tylko do określonej kategorii produktów?**
O: Tak, możesz połączyć funkcjonalność tego modułu ze standardowymi ograniczeniami zasad koszyka PrestaShop. Na zakładce „Warunki” zasady koszyka możesz dodać warunki, takie jak „Wybór produktu”, aby określić, że rabat ma zastosowanie tylko wtedy, gdy w koszyku znajduje się produkt z określonej kategorii. Pamiętaj jednak, że *jeśli* taki produkt jest obecny, moduł nadal wybierze *ogólnie* najdroższy produkt w koszyku (chyba że ten produkt jest wykluczony) i zastosuje do niego rabat, a niekoniecznie najdroższy produkt *z tej konkretnej kategorii*.

**P: Czy ten moduł działa z rabatami o stałej kwocie?**
O: Nie, ten moduł jest specjalnie zaprojektowany do pracy *tylko* z **rabatami procentowymi**. Opcja „Zastosuj rabat tylko do najdroższego produktu” pojawi się i będzie działać tylko wtedy, gdy wybierzesz „Procent” jako typ rabatu na zakładce „Akcje” zasady koszyka.

**P: Mój niestandardowy motyw nie wyświetla rabatu poprawnie.**
O: Moduł przede wszystkim modyfikuje logikę obliczania rabatów, a nie wyświetlanie w front-office. Domyślne szablony PrestaShop powinny poprawnie wyświetlać rabat. Jeśli Twój niestandardowy motyw mocno dostosował podsumowanie koszyka lub kasy, może wymagać drobnych korekt, aby poprawnie odzwierciedlić sposób stosowania rabatów. W większości przypadków wyczyszczenie pamięci podręcznej Smarty (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) powinno rozwiązać problemy z wyświetlaniem. Jeśli nie, skonsultuj się z twórcą swojego motywu.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Zasada koszyka dla najdroższego produktu” (`crexpensive`) rozszerza głównie podstawową klasę PrestaShop `CartRule` poprzez nadpisanie. Pozwala to na wstrzyknięcie niestandardowej logiki do procesu obliczania rabatów bez bezpośredniej modyfikacji plików rdzenia. Moduł zapewnia również minimalny interfejs konfiguracji w Panelu administracyjnym i rejestruje hook, aby wstrzyknąć niezbędny JavaScript dla formularzy administracyjnych.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego funkcjonalność jest zintegrowana bezpośrednio z istniejącymi procesami PrestaShop za pomocą nadpisań i hooków.

### 4.3 Klasy i modele rdzenia (`classes/`)

-   **`crexpensive/override/classes/CartRule.php`**
    *   **Nazwa klasy:** `CartRule` (nadpisuje podstawową klasę `CartRule`)
    *   **Klasa nadrzędna:** `CartRuleCore`
    *   **Odpowiedzialność:** To nadpisanie jest sercem funkcjonalności modułu. Modyfikuje zachowanie sposobu stosowania zasad koszyka, w szczególności celując w obliczenia `reduction_percent`.
    *   **Kluczowe metody i logika:**
        *   Nadpisanie prawdopodobnie przechwytuje lub modyfikuje metody związane z obliczaniem `reduction_percent` w klasie `CartRule`. Będzie zawierać logikę do:
            1.  Sprawdzenia, czy bieżąca zasada koszyka ma włączoną flagę `apply_to_most_expensive_product` (niestandardowe pole dodane przez moduł).
            2.  Jeśli włączone, iterowania przez produkty w koszyku w celu zidentyfikowania najdroższego, biorąc pod uwagę wszelkie globalnie wykluczone produkty skonfigurowane w module.
            3.  Dostosowania zastosowania `reduction_percent` tak, aby dotyczyło tylko zidentyfikowanego najdroższego produktu, zapewniając, że rabat jest obliczany na podstawie jego ceny, a nie całego koszyka lub innych produktów.
        *   Dodaje również nowe pole do definicji `CartRule` (`$definition`) w celu przechowywania flagi `apply_to_most_expensive_product` w tabeli bazy danych `ps_cart_rule`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`crexpensive/views/js/crexpensive.js`**
    *   **Zakres:** Panel administracyjny (w szczególności strona edycji zasady koszyka).
    *   **Odpowiedzialność:** Ten skrypt jest odpowiedzialny za dynamiczne pokazywanie/ukrywanie pola wyboru „Zastosuj rabat tylko do najdroższego produktu” na stronie edycji zasady koszyka.
    *   **Kluczowa logika:**
        *   Prawdopodobnie nasłuchuje zmian w rozwijanej liście/przyciskach radiowych „Zastosuj rabat” (szczególnie, gdy wybrano „Procent”).
        *   Gdy wybrano „Procent”, sprawia, że niestandardowe pole wyboru jest widoczne.
        *   Gdy wybrano inne typy rabatów (np. „Kwota”, „Darmowa wysyłka”), ukrywa pole wyboru, ponieważ moduł dotyczy tylko rabatów procentowych.
        *   Zapewnia, że stan pola wyboru jest poprawnie ładowany podczas edycji istniejącej zasady koszyka.

### 4.5 Arkusze stylów CSS (`views/css/`)
Ten moduł nie zawiera żadnych niestandardowych plików CSS. Opiera się na domyślnej stylizacji PrestaShop dla swoich elementów konfiguracyjnych i wstrzykniętego pola wyboru na stronie zasady koszyka.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Formularz konfiguracji jest renderowany za pomocą `getContent()` w głównym pliku modułu, a niestandardowe pole wyboru jest wstrzykiwane do istniejącej strony edycji zasady koszyka za pomocą JavaScript.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł modyfikuje tabelę `ps_cart_rule`, dodając nową kolumnę, prawdopodobnie nazwaną `apply_to_most_expensive_product` (lub podobnie), która jest polem typu tinyint (boolean) do przechowywania stanu niestandardowego pola wyboru dla każdej zasady koszyka.
    *   Wartości konfiguracyjne (`mypresta_updates`, `csc_excluded_products`) są przechowywane w tabeli `ps_configuration`.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :--------------- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne (JS/CSS). | Ten hook służy do ładowania `crexpensive.js` na stronę edycji zasady koszyka w Panelu administracyjnym, umożliwiając dynamiczne wyświetlanie pola wyboru „Zastosuj rabat tylko do najdroższego produktu”. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Zasada koszyka dla najdroższego produktu” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
