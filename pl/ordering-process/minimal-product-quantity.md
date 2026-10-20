---
title: "Minimalna ilość produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Minimalna ilość produktu” od MyPresta.eu."
sidebar:
  label: "Minimalna ilość produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Minimal product quantity na MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-product-quantity.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/minimal-product-quantity/)
>
> ---


# Minimalna ilość produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „Minimalna ilość produktu”. To tutaj definiujesz podstawowe zasady dotyczące minimalnych ilości.

Strona konfiguracji jest zaprojektowana tak, aby była intuicyjna, umożliwiając ustawienie minimalnych ilości dla poszczególnych produktów i określonych grup klientów.

**Jak ustawić minimalną ilość dla produktu:**

1.  **Wyszukaj produkt:**

    *   Zobaczysz pasek wyszukiwania lub listę produktów. Zacznij wpisywać nazwę produktu, który chcesz skonfigurować. W miarę pisania moduł będzie sugerował pasujące produkty.
    *   *Co robi to ustawienie:* Pozwala szybko zlokalizować konkretny produkt, do którego chcesz zastosować regułę minimalnej ilości.
    *   *Wpływ zmiany tego ustawienia:* N/A (funkcja wyszukiwania).
    *   *Zalecana wartość:* Wpisz dokładną nazwę produktu dla precyzji.
    *   *Scenariusz sprzedawcy:* Chcesz ustawić minimum dla „Organicznych ziaren kawy (1kg)”. Wpisz „Organiczna kawa”.
2.  **Wybierz produkt:**

    *   Kliknij na żądany produkt z wyników wyszukiwania. Spowoduje to dodanie go do listy skonfigurowanych produktów poniżej.
    *   *Co robi to ustawienie:* Potwierdza, do którego produktu stosujesz regułę.
    *   *Wpływ zmiany tego ustawienia:* Produkt pojawia się na liście konfiguracji, gotowy do ustawień ilości i grupy.
    *   *Zalecana wartość:* Wybierz prawidłowy produkt.
    *   *Scenariusz sprzedawcy:* Po wpisaniu „Organiczna kawa” klikasz na „Organiczne ziarna kawy (1kg)”.
3.  **Ustaw minimalną ilość:**

    *   Obok wybranego produktu pojawi się pole wprowadzania (np. „Minimalna ilość”). Wprowadź najniższą liczbę jednostek, jaką klient musi kupić dla tego konkretnego produktu.
    *   *Co robi to ustawienie:* Definiuje absolutną minimalną liczbę jednostek dla tego produktu.
    *   *Wpływ zmiany tego ustawienia:*
        *   *Gdy ustawione na 5:* Klienci muszą dodać co najmniej 5 jednostek tego produktu do koszyka. Jeśli spróbują dodać 1, 2, 3 lub 4, otrzymają komunikat o błędzie.
        *   *Gdy ustawione na 1 (lub domyślne zachowanie PrestaShop):* Nie jest wymuszana żadna specjalna minimalna ilość poza domyślną PrestaShop.
    *   *Zalecana wartość:* Liczba większa niż 1, odzwierciedlająca Twoje potrzeby biznesowe (np. 6, 12, 24).
    *   *Scenariusz sprzedawcy:* Sprzedajesz ziarna kawy luzem. Ustawiasz „Minimalną ilość” na 5.
4.  **Wybierz grupę klientów (opcjonalnie):**

    *   Prawdopodobnie zobaczysz rozwijaną listę lub listę grup klientów (np. „Gość”, „Klient”, „Hurtownik”). Możesz wybrać jedną lub więcej grup, dla których ta minimalna ilość ma zastosowanie.
    *   *Co robi to ustawienie:* Pozwala zastosować różne reguły minimalnej ilości w zależności od grupy klienta. Jeśli nie wybrano żadnej grupy, reguła ma zastosowanie do wszystkich klientów.
    *   *Wpływ zmiany tego ustawienia:*
        *   *Gdy wybrano „Hurtownik”:* Tylko klienci należący do grupy „Hurtownik” będą podlegać tej minimalnej ilości. Inne grupy mogą mieć inne minimum (lub brak minimum).
        *   *Gdy nie wybrano konkretnej grupy (lub domyślnie „Wszyscy klienci”):* Minimalna ilość ma zastosowanie do każdego klienta, niezależnie od jego grupy.
    *   *Zalecana wartość:* Wybierz konkretne grupy, jeśli masz dla nich różne strategie cenowe lub sprzedażowe. W przeciwnym razie pozostaw dla „Wszyscy klienci”.
    *   *Scenariusz sprzedawcy:* Chcesz, aby hurtownicy kupowali co najmniej 10 jednostek, ale zwykli klienci potrzebują kupić tylko 5. Utworzyłbyś dwie oddzielne reguły dla tego samego produktu, jedną dla grupy „Hurtownik” z ilością 10, a drugą dla grupy „Klient” z ilością 5.
5.  **Zapisz zmiany:**

    *   Po skonfigurowaniu produktu(ów) i ich minimalnych ilości/grup, pamiętaj, aby kliknąć przycisk „Zapisz” lub „Aktualizuj”, aby zastosować swoje ustawienia.
    *   *Co robi to ustawienie:* Utrwala zmiany konfiguracji w bazie danych.
    *   *Wpływ zmiany tego ustawienia:* Nowe reguły minimalnej ilości stają się aktywne w Twoim sklepie natychmiast.
    *   *Zalecana wartość:* Zawsze zapisuj po wprowadzeniu zmian.
    *   *Scenariusz sprzedawcy:* Ustawiono wszystkie minima; teraz klikasz „Zapisz”, aby je aktywować.

**Ogólne ustawienia modułu (jeśli są obecne):**

Chociaż główną funkcją są minima dla poszczególnych produktów, niektóre moduły mogą zawierać ogólne ustawienia:

-   **Włącz/Wyłącz moduł:**

    *   *Co robi to ustawienie:* Włącza lub wyłącza całą funkcjonalność modułu.
    *   *Wpływ zmiany tego ustawienia:*
        *   *Gdy włączony:* Reguły minimalnej ilości są egzekwowane.
        *   *Gdy wyłączony:* Wszystkie reguły minimalnej ilości są ignorowane, a klienci mogą dodać dowolną ilość.
    *   *Zalecana wartość:* TAK (włączony) po skonfigurowaniu.
    *   *Scenariusz sprzedawcy:* Testujesz moduł i chcesz go tymczasowo wyłączyć bez utraty ustawień.
-   **Typ wyświetlania komunikatu o błędzie (np. Wyskakujące okienko, W tekście):**

    *   *Co robi to ustawienie:* Kontroluje sposób powiadamiania klienta, gdy próbuje dodać mniej niż minimalną ilość.
    *   *Wpływ zmiany tego ustawienia:*
        *   *Gdy ustawione na Wyskakujące okienko:* Pojawia się okno modalne, przerywając przepływ użytkownika, jasno informując o problemie.
        *   *Gdy ustawione na W tekście:* Wiadomość pojawia się bezpośrednio na stronie produktu lub w koszyku, bez wyskakującego okienka.
    *   *Zalecana wartość:* Wyskakujące okienko jest często bardziej skuteczne w przypadku krytycznych błędów, takich jak minimalne ilości, ponieważ wymaga uwagi.
    *   *Scenariusz sprzedawcy:* Chcesz mieć pewność, że klienci nie przegapią wymogu minimalnej ilości, dlatego wybierasz wyskakujące okienko.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Wyszukiwanie produktu | N/A | Lokalizowanie produktów do zastosowania reguł minimalnej ilości. |
| Strona konfiguracji modułu | Minimalna ilość (na produkt) | Różne (np. 5, 10) | Ustawia najniższą liczbę jednostek, jaką klient musi kupić dla tego produktu. |
| Strona konfiguracji modułu | Grupa klientów (na produkt) | Wszyscy klienci | Stosuje regułę minimalnej ilości do określonych grup klientów lub wszystkich klientów. |
| Strona konfiguracji modułu | Przycisk Zapisz | N/A | Stosuje wszystkie skonfigurowane reguły minimalnej ilości do sklepu. |
| Strona konfiguracji modułu | Włącz/Wyłącz moduł | Włączony | Włącza lub wyłącza funkcjonalność modułu globalnie. |
| Strona konfiguracji modułu | Typ komunikatu o błędzie | Wyskakujące okienko | Definiuje sposób wyświetlania błędów minimalnej ilości klientom. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem minimalną ilość, ale nie działa w moim sklepie. Co jest nie tak?**
O:

1.  **Czy moduł jest włączony?** Sprawdź ponownie na głównej stronie konfiguracji, czy moduł „Minimalna ilość produktu” jest aktywny.
2.  **Czy zapisałeś zmiany?** Zawsze kliknij przycisk „Zapisz” lub „Aktualizuj” po wprowadzeniu jakichkolwiek zmian w konfiguracji.
3.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop buforuje stare ustawienia.
4.  **Sprawdź konflikty z szablonem:** Jeśli masz mocno dostosowany szablon, może on kolidować ze sposobem wyświetlania komunikatów przez moduł lub interakcji z przyciskiem „Dodaj do koszyka”. Tymczasowo przełącz się na domyślny szablon PrestaShop (Classic lub Hummingbird), aby sprawdzić, czy problem nadal występuje. Jeśli problem zostanie rozwiązany, Twój szablon wymaga dostosowania.
5.  **Grupa klientów:** Upewnij się, że klient, z którym testujesz, należy do grupy, dla której ustawiono minimalną ilość. Jeśli nie określono grupy, powinno to dotyczyć wszystkich.

**P2: Powiadomienie wyskakujące wygląda dziwnie lub nie pasuje do projektu mojego sklepu.**
O: Moduł używa własnego CSS dla wyskakującego okienka. Jeśli Twój szablon ma bardzo specyficzne reguły stylizacji, mogą one nadpisywać lub kolidować.

1.  **Sprawdź ustawienia modułu:** Zobacz, czy moduł oferuje opcje dostosowania wyglądu wyskakującego okienka lub wyboru innej metody wyświetlania (np. komunikat w tekście zamiast wyskakującego okienka).
2.  **Niestandardowy CSS:** Dla programistów lub webmasterów, niestandardowy CSS można dodać do pliku `custom.css` Twojego szablonu, aby nadpisać domyślne style modułu. (Zobacz sekcję 7.5, aby uzyskać szczegółowe informacje o pliku CSS).

**P3: Czy mogę ustawić minimalną ilość dla kombinacji produktów (atrybutów)?**
O: Moduł zazwyczaj stosuje minimalne ilości na poziomie produktu. Jeśli potrzebujesz konkretnych minimów dla kombinacji (np. „Czerwona koszulka, rozmiar S” vs. „Niebieska koszulka, rozmiar L”), musisz sprawdzić, czy moduł wyraźnie to obsługuje w swojej konfiguracji. Jeśli nie, ustawisz minimum dla produktu nadrzędnego, które będzie miało zastosowanie do dowolnej kombinacji tego produktu.

**P4: Jak przetłumaczyć komunikaty modułu na inne języki?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
3.  Wybierz swój szablon, język, na który chcesz przetłumaczyć, a następnie wybierz „Minimalna ilość produktu” z listy modułów.
4.  Znajdziesz wszystkie przetłumaczalne ciągi znaków używane przez moduł (np. „Musisz dodać co najmniej X jednostek tego produktu”). Przetłumacz je i zapisz.

**P5: Co się stanie, jeśli klient ma produkt w koszyku, do którego później zostanie zastosowana minimalna ilość?**
O: Gdy klient następnym razem odwiedzi swój koszyk lub spróbuje zrealizować zamówienie, moduł wykryje niezgodność. Zostanie mu wyświetlony komunikat o błędzie i zostanie mu uniemożliwione kontynuowanie, dopóki nie dostosuje ilości, aby spełnić nowe minimum.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Minimalna ilość produktu” (`minqc`) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie hooki do wstrzykiwania swojej logiki i zasobów front-endowych. Działa poprzez przechwytywanie zmian ilości i dodawania do koszyka, walidację względem skonfigurowanych minimów i wyświetlanie informacji zwrotnych użytkownikowi. Główna logika modułu znajduje się w jego głównym pliku `index.php`, który obsługuje instalację, deinstalację, konfigurację i rejestrację hooków. Interakcja z front-endem jest zarządzana za pomocą zestawu plików JavaScript dostosowanych do różnych wersji i kontekstów PrestaShop (strona produktu, koszyk, szybki podgląd).

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wydaje się wykorzystywać niestandardowych kontrolerów Front Office ani Back Office. Jego konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu, a interakcje z front-endem są zarządzane za pomocą JavaScript i wywołań AJAX do podstawowych funkcji PrestaShop lub własnego `ajax.php` modułu (jeśli jest obecny, choć nie jest wyraźnie wymieniony jako dedykowany kontroler, jest to powszechny wzorzec dla modułów do obsługi żądań AJAX za pośrednictwem ich głównego pliku lub prostego skryptu).

### 4.3 Klasy podstawowe i modele (`classes/`)

Na podstawie dostarczonego spisu, ten moduł nie definiuje niestandardowych klas `ObjectModel` ani innych złożonych klas PHP w dedykowanym katalogu `classes/`. Jego logika jest prawdopodobnie hermetyzowana w głównym pliku `minqc/index.php`, bezpośrednio wchodząc w interakcje z `Configuration` dla ustawień i potencjalnie `Db` dla niestandardowego przechowywania danych, jeśli minima specyficzne dla produktu są przechowywane poza `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł intensywnie wykorzystuje JavaScript, aby zapewnić dynamiczne doświadczenie użytkownika i egzekwować zasady ilości w czasie rzeczywistym.

-   `minqc/views/js/minqc.js`:
    *   **Zakres:** Prawdopodobnie główny plik JS, potencjalnie ładowany globalnie lub na wielu stronach.
    *   **Odpowiedzialność:** Zawiera ogólne funkcje narzędziowe, wiązanie zdarzeń dla wspólnych elementów i potencjalnie główną logikę sprawdzania minimalnych ilości przed dodaniem do koszyka lub aktualizacją koszyka. Może obsługiwać wyświetlanie powiadomienia wyskakującego.
    *   **Interakcje:** Wiąże się ze zdarzeniami `click` na przyciskach „Dodaj do koszyka”, zdarzeniami `change` na polach wprowadzania ilości i potencjalnie zdarzeniami `prestashop.on` dla aktualizacji koszyka AJAX.
-   `minqc/views/js/minqc-17500.js`:
    *   **Zakres:** Front Office, szczególnie dla PrestaShop 1.7.5.0 i nowszych wersji (lub podobnych zakresów wersji).
    *   **Odpowiedzialność:** Zawiera logikę JavaScript specyficzną dla wersji, aby dostosować się do zmian w strukturze Front Office PrestaShop, zachowaniu koszyka AJAX lub elementach strony produktu wprowadzonych w tych wersjach.
    *   **Interakcje:** Nadpisuje lub rozszerza `minqc.js` dla specyficznych struktur DOM PrestaShop 1.7+ i obsługi zdarzeń.
-   `minqc/views/js/minqc-admin-product.js`:
    *   **Zakres:** Back Office, szczególnie na stronie edycji produktu (`AdminProducts`).
    *   **Odpowiedzialność:** Jeśli moduł pozwala na ustawianie minimalnych ilości bezpośrednio na stronie edycji produktu, ten skrypt obsługiwałby interfejs użytkownika dla tego (np. dodawanie pól wprowadzania, zapisywanie wartości za pomocą AJAX).
    *   **Interakcje:** Wiąże się ze zdarzeniami na elementach formularza produktu, wykonuje wywołania AJAX w celu zapisania minimów specyficznych dla produktu.
-   `minqc/views/js/minqc-cart.js`:
    *   **Zakres:** Front Office, szczególnie na stronie koszyka zakupowego.
    *   **Odpowiedzialność:** Monitoruje zmiany ilości w koszyku, waliduje względem minimów i zapobiega realizacji zamówienia, jeśli zasady są naruszone. Wyświetla komunikaty o błędach lub wyskakujące okienka na stronie koszyka.
    *   **Interakcje:** Wiąże się ze zmianami wprowadzania ilości, kliknięciami przycisku „Przejdź do kasy” i potencjalnie zdarzeniami `prestashop.on` związanymi z aktualizacjami koszyka.
-   `minqc/views/js/minqc-front.js`:
    *   **Zakres:** Ogólne zastosowanie w Front Office.
    *   **Odpowiedzialność:** Może być bardziej ogólnym skryptem front-endowym, potencjalnie obsługującym wyświetlanie informacji o minimalnej ilości na listach produktów lub innych niespecyficznych stronach produktów/koszyka.
    *   **Interakcje:** Manipulacja DOM w celu wyświetlania komunikatów, potencjalnie wywołania AJAX do walidacji.
-   `minqc/views/js/minqc-no-autoadd.js`:
    *   **Zakres:** Front Office.
    *   **Odpowiedzialność:** Sugeruje specyficzne zachowanie związane z zapobieganiem automatycznemu dodawaniu produktów do koszyka, jeśli minima nie są spełnione, lub obsługą scenariuszy, w których produkt może zostać automatycznie dodany, ale następnie nie przechodzi walidacji.
    *   **Interakcje:** Modyfikuje domyślne zachowanie „Dodaj do koszyka”, aby zapewnić, że walidacja następuje *przed* dodaniem elementu.
-   `minqc/views/js/minqc-product-classic.js`:
    *   **Zakres:** Front Office, szczególnie dla szablonów opartych na szablonie PrestaShop Classic (PrestaShop 1.7+).
    *   **Odpowiedzialność:** Dostosowuje egzekwowanie i wyświetlanie minimalnej ilości do struktury DOM i zdarzeń JavaScript specyficznych dla strony produktu szablonu Classic.
    *   **Interakcje:** Wiąże się z przyciskiem „Dodaj do koszyka” i elementami wprowadzania ilości na stronie produktu szablonu Classic.
-   `minqc/views/js/minqc-product-hummingbird.js`:
    *   **Zakres:** Front Office, szczególnie dla szablonów opartych na szablonie PrestaShop Hummingbird (PrestaShop 8+).
    *   **Odpowiedzialność:** Dostosowuje egzekwowanie i wyświetlanie minimalnej ilości do struktury DOM i zdarzeń JavaScript specyficznych dla strony produktu szablonu Hummingbird.
    *   **Interakcje:** Wiąże się z przyciskiem „Dodaj do koszyka” i elementami wprowadzania ilości na stronie produktu szablonu Hummingbird.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `minqc/views/css/minqc.css`:
    *   **Zakres:** Front Office i potencjalnie Back Office dla elementów interfejsu użytkownika specyficznych dla modułu.
    *   **Główne komponenty interfejsu użytkownika:** Style dla powiadomienia wyskakującego (tło modalne, pole zawartości, przycisk zamykania, tekst wiadomości), komunikaty o błędach w tekście i potencjalnie wskaźniki wizualne na stronach produktów.
    *   **Kluczowe selektory klas CSS:** Programiści mogą sprawdzić wyjściowy kod HTML modułu, aby zidentyfikować konkretne klasy (np. `.minqc-popup`, `.minqc-error-message`, `.minqc-quantity-input-error`) i nadpisać je w pliku `custom.css` lub `theme.css` swojego szablonu, aby dopasować je do brandingu swojego sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Niewyraźnie wymienione, ale powszechne dla modułów do używania `displayHeader` dla JS/CSS lub `displayProductActions` dla komunikatów na stronie produktu.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `minqc/views/templates/admin/admin.tpl`: Prawdopodobnie główny szablon konfiguracji modułu, renderowany przez metodę `getContent()`. Zawierałby wyszukiwanie produktów, listę skonfigurowanych produktów i ogólne ustawienia.
    *   `minqc/views/templates/admin/admintab.tpl`: Może być podszablonem dla konkretnej zakładki lub sekcji w konfiguracji administracyjnej, lub starszym szablonem.
    *   `minqc/views/templates/admin/_configure/helpers/list/list_content.tpl`: Sugeruje to, że moduł używa `HelperList` PrestaShop do wyświetlania listy produktów ze skonfigurowanymi minimalnymi ilościami w Panelu administracyjnym. Ten szablon definiowałby, jak renderowany jest każdy wiersz na tej liście.
-   **Szablony Ajax (`views/templates/ajax/`)**:
    *   `minqc/views/templates/ajax/minqcErrors.tpl`: Ten szablon jest prawdopodobnie używany do renderowania zawartości HTML wyskakującego okienka błędu lub komunikatów w tekście wyświetlanych klientowi, gdy minimalna ilość nie jest spełniona. Byłby ładowany za pomocą AJAX.
-   **Szablony Front Office (`views/templates/front/`)**:
    *   `minqc/views/templates/front/beforeShoppingCart.tpl`: Ten szablon jest prawdopodobnie podpięty do pozycji przed główną zawartością koszyka zakupowego, potencjalnie w celu wyświetlenia ostrzeżenia lub podsumowania związanego z minimalnymi ilościami, jeśli koszyk jest nieprawidłowy.
    *   `minqc/views/templates/front/product-details.tpl`: Ten szablon byłby używany do wstrzykiwania informacji o minimalnej ilości lub ostrzeżeń bezpośrednio na stronę szczegółów produktu, często w pobliżu selektora ilości lub przycisku „Dodaj do koszyka”.
    *   `minqc/views/templates/front/productActions.tpl`: Podobnie jak `product-details.tpl`, ten szablon byłby podpięty do hooka `displayProductActions` (lub podobnego) w celu wyświetlania komunikatów lub modyfikowania zachowania przycisku „Dodaj do koszyka” na podstawie reguł minimalnej ilości.
    *   `minqc/views/templates/front/qv.tpl`: Ten szablon jest specjalnie dla funkcji „Szybki podgląd”, wstrzykując informacje o minimalnej ilości lub ostrzeżenia do modalnego okna szybkiego podglądu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł prawdopodobnie przechowuje swoją konfigurację dla minimalnych ilości specyficznych dla produktu i powiązań z grupami klientów w tabeli `ps_configuration` dla prostych ustawień globalnych.
    *   Dla minimów specyficznych dla produktu i grupy, jest bardzo prawdopodobne, że moduł tworzy własną niestandardową tabelę bazy danych (np. `ps_minqc_product_quantity`) do przechowywania wartości `id_product`, `id_customer_group` i `min_quantity`. Tabela ta byłaby tworzona podczas metody `install()` i usuwana podczas `uninstall()`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony Front Office. | Wstrzykuje pliki CSS (`minqc.css`) i JavaScript (`minqc.js`, `minqc-front.js`, JS specyficzne dla wersji, takie jak `minqc-17500.js`, `minqc-product-classic.js`, `minqc-product-hummingbird.js`, `minqc-cart.js`, `minqc-no-autoadd.js`) modułu dla funkcjonalności Front Office. |
| `displayProductActions` | Na stronie produktu, zazwyczaj w pobliżu przycisku „Dodaj do koszyka”. | Wstrzykuje `productActions.tpl` w celu wyświetlenia wymagań dotyczących minimalnej ilości lub ostrzeżeń bezpośrednio na stronie produktu. |
| `displayProductExtraContent` (lub podobny) | Na stronie produktu, dla dodatkowych bloków treści. | Może być używany do wyświetlania `product-details.tpl` lub innych informacji. |
| `displayShoppingCartFooter` (lub podobny) | Na dole podsumowania koszyka zakupowego. | Wstrzykuje `beforeShoppingCart.tpl` lub podobny w celu wyświetlenia ostrzeżeń, jeśli produkty w koszyku nie spełniają minimów, zapobiegając realizacji zamówienia. |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka. | Wyzwala logikę PHP modułu w celu ponownej walidacji wszystkich ilości w koszyku względem skonfigurowanych minimów. |
| `actionValidateOrder` | Przed oficjalnym zatwierdzeniem zamówienia. | Ostateczne sprawdzenie, aby upewnić się, że wszystkie ilości produktów w koszyku spełniają ich minima przed złożeniem zamówienia. |
| `actionProductUpdate` / `actionProductAdd` | Gdy produkt jest aktualizowany lub dodawany w Panelu administracyjnym. | Potencjalnie używany do aktualizacji lub czyszczenia buforowanych danych minimalnej ilości dla tego produktu. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Wstrzykuje elementy interfejsu użytkownika (np. za pośrednictwem `admintab.tpl` lub `admin.tpl`), aby umożliwić ustawienie minimalnych ilości specyficznych dla produktu bezpośrednio z formularza produktu, wykorzystując `minqc-admin-product.js`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań związanych z modułem „Minimalna ilość produktu”.
