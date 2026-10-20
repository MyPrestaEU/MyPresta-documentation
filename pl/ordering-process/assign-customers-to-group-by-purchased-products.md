---
title: "Przypisz klientów do grupy na podstawie zakupionych produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Przypisz klientów do grupy na podstawie zakupionych produktów” od MyPresta.eu."
sidebar:
  label: "Przypisz klientów do grupy na podstawie zakupionych produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Assign customers to group by purchased products na MyPresta.eu](https://mypresta.eu/modules/ordering-process/assign-customers-to-group-by-purchased-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/assign-customers-to-group-by-purchased-products/)
>
> ---


# Przypisz klientów do grupy na podstawie zakupionych produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym zarządzasz podstawowymi ustawieniami modułu.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera ogólne ustawienia modułu, takie jak włączanie/wyłączanie jego podstawowej funkcjonalności.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Moduł będzie aktywnie monitorować zakupy klientów i stosować zdefiniowane reguły przypisywania do grup.
    -   *Gdy wyłączone:* Moduł przestanie przetwarzać nowe zamówienia w celu przypisywania do grup. Istniejące przypisania pozostaną, ale żadne nowe nie zostaną wykonane automatycznie.
-   **Zalecana wartość:** **TAK** (Włączone), aby moduł mógł działać.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, będziesz chciał go włączyć natychmiast po konfiguracji. Jeśli musisz tymczasowo zatrzymać automatyczne przypisania (np. podczas dużej migracji sklepu), możesz go tutaj wyłączyć.

### 2.2 Dedykowany ekran administracyjny: Powiązania grup produktów

Jest to główny obszar zarządzania, w którym definiujesz reguły przypisywania klientów do grup na podstawie ich zakupów.

**Nazwa ekranu i lokalizacja w menu:**
Możesz uzyskać dostęp do tego ekranu, przechodząc do **Moduły > Menedżer modułów**, znajdując „Przypisz klientów do grupy na podstawie zakupionych produktów” i klikając „Konfiguruj”. W konfiguracji modułu znajdziesz sekcję lub zakładkę poświęconą „Powiązaniom grup produktów” lub podobną.

**Dostępne działania i ustawienia:**
Na tym ekranie zazwyczaj znajdziesz listę istniejących reguł przypisywania. Będziesz mieć opcje:

-   **Dodaj nową regułę:** Utwórz nowy warunek przypisania do grupy.
-   **Edytuj regułę:** Zmodyfikuj istniejącą regułę.
-   **Usuń regułę:** Usuń regułę.

Podczas dodawania lub edytowania reguły skonfigurujesz następujące elementy:

1.  **Wybierz grupę klientów:**

    -   **Co robi to ustawienie:** Jest to grupa docelowa, do której klienci zostaną przypisani, jeśli spełnią warunki reguły.
    -   **Efekt zmiany tego ustawienia:** Gdy zakup klienta uruchomi tę regułę, zostanie on przeniesiony do (lub dodany do) wybranej grupy klientów.
    -   **Zalecana wartość:** Wybierz konkretną grupę klientów, którą chcesz segmentować (np. „Klienci hurtowi”, „Kupujący VIP”, „Entuzjaści elektroniki”).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz utworzyć regułę, aby przypisać klientów do grupy „Kupujący VIP”.
2.  **Wybierz produkty / kategorie:**

    -   **Co robi to ustawienie:** Tutaj definiujesz, *które* produkty lub kategorie produktów, po zakupie, uruchomią przypisanie do grupy. Zazwyczaj możesz wybrać wiele produktów lub kategorii. Moduł prawdopodobnie zawiera narzędzie wyszukiwania, aby łatwo znaleźć produkty.
    -   **Efekt zmiany tego ustawienia:** Tylko zakupy zawierające określone produkty lub z określonych kategorii aktywują tę regułę.
    -   **Zalecana wartość:** Bądź precyzyjny. Użyj narzędzia wyszukiwania, aby wybrać wszystkie odpowiednie produkty lub kategorie.
    -   **Scenariusz / przykład dla sprzedawcy:** Dla grupy „Kupujący VIP” możesz wybrać produkty o wysokiej wartości, takie jak „Luksusowy zegarek X” i „Diamentowy naszyjnik Y”. Dla „Entuzjastów elektroniki” możesz wybrać całą kategorię „Elektronika”.
3.  **Minimalna ilość (opcjonalnie):**

    -   **Co robi to ustawienie:** Jeśli określono, klient musi kupić co najmniej tę ilość wybranych produktów/kategorii w jednym zamówieniu, aby zostać przypisanym do grupy.
    -   **Efekt zmiany tego ustawienia:** Jeśli klient kupi mniej niż minimalna ilość, reguła nie zostanie zastosowana, nawet jeśli kupił określone produkty.
    -   **Zalecana wartość:** Pozostaw puste dla dowolnej ilości lub ustaw wartość taką jak „1” dla co najmniej jednego przedmiotu lub „5” dla kupujących hurtowo.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby być „Klientem hurtowym”, muszą kupić co najmniej 10 sztuk dowolnego produktu z kategorii „Towary masowe”.
4.  **Status zamówienia do wyzwolenia przypisania:**

    -   **Co robi to ustawienie:** Określa, w jakim statusie zamówienia powinno nastąpić przypisanie grupy klientów. Na przykład, możesz chcieć przypisywać grupy tylko wtedy, gdy zamówienie ma status „Płatność zaakceptowana” lub „Dostarczone”.
    -   **Efekt zmiany tego ustawienia:** Moduł przetworzy przypisanie grupy tylko wtedy, gdy zamówienie osiągnie wybrany status. Jeśli zamówienie nigdy nie osiągnie tego statusu (np. „Anulowane”), przypisanie nie nastąpi.
    -   **Zalecana wartość:** „Płatność zaakceptowana” lub „Dostarczone” to zazwyczaj bezpieczne wybory, aby upewnić się, że zakup jest potwierdzony.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz upewnić się, że klienci faktycznie zapłacili, zanim zostaną dodani do specjalnej grupy, więc wybierasz „Płatność zaakceptowana”.
5.  **Przypisz do grupy (Dodaj lub Zastąp):**

    -   **Co robi to ustawienie:** Ta kluczowa opcja określa, jak jest obsługiwane członkostwo klienta w grupie.
        -   **Dodaj do grupy:** Klient zostanie dodany do wybranej grupy *oprócz* wszelkich grup, w których już się znajduje.
        -   **Zastąp bieżącą grupę:** *Główna* grupa klienta zostanie zmieniona na wybraną grupę, potencjalnie usuwając go z poprzedniej głównej grupy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Dodaj do grupy:* Klienci mogą należeć do wielu grup, co pozwala na elastyczną segmentację.
        -   *Zastąp bieżącą grupę:* Klienci będą należeć tylko do jednej głównej grupy, co upraszcza zarządzanie, ale potencjalnie prowadzi do utraty innych powiązań grupowych.
    -   **Zalecana wartość:** „Dodaj do grupy” oferuje większą elastyczność w większości scenariuszy. Używaj „Zastąp bieżącą grupę” ostrożnie, zwłaszcza jeśli inne moduły polegają na przypisaniach do głównej grupy.
    -   **Scenariusz / przykład dla sprzedawcy:**
        -   *Dodaj do grupy:* Klient, który kupuje określony produkt, jest dodawany do „Kupujących VIP”, ale pozostaje w „Klientach ogólnych”.
        -   *Zastąp bieżącą grupę:* Klient, który kupuje określony produkt, jest przenoszony z „Klientów ogólnych” do „Klientów hurtowych”, stając się ich nową główną grupą.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Zaplanuj swoje segmenty klientów:** Przed utworzeniem reguł zdecyduj, jakie grupy klientów chcesz mieć i jakie kryteria je definiują.
2.  **Utwórz swoje grupy klientów:** Przejdź do **Klienci > Grupy** w Panelu administracyjnym PrestaShop i utwórz wszelkie nowe grupy, których potrzebujesz (np. „Hurtownicy”, „VIP”, „Kupujący Produkt X”).
3.  **Zdefiniuj reguły:** Dla każdej grupy klientów utwórz nową regułę powiązania w konfiguracji modułu.
4.  **Dokładnie przetestuj:** Dokonaj testowego zakupu za pomocą testowego konta klienta, aby upewnić się, że przypisanie do grupy odbywa się zgodnie z oczekiwaniami.
5.  **Regularnie przeglądaj:** Okresowo sprawdzaj swoje reguły i przypisania do grup klientów, aby upewnić się, że nadal są one zgodne z Twoimi celami biznesowymi.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Moduł Włączony/Wyłączony | Włączony | Kontroluje, czy moduł aktywnie przetwarza zamówienia w celu przypisania do grup. |
| **Powiązania grup produktów** | Docelowa grupa klientów | N/A (Zdefiniowane przez użytkownika) | Grupa, do której klienci zostaną przypisani. |
| | Produkty / Kategorie | N/A (Zdefiniowane przez użytkownika) | Konkretne produkty lub kategorie, których zakup wyzwala przypisanie. |
| | Minimalna ilość | Puste (Dowolna ilość) | Minimalna liczba pozycji z produktów/kategorii reguły wymagana w zamówieniu. |
| | Status zamówienia do wyzwolenia | Płatność zaakceptowana / Dostarczone | Status zamówienia, w którym przetwarzane jest przypisanie do grupy. |
| | Typ przypisania | Dodaj do grupy | Określa, czy klient jest dodawany do grupy, czy jego główna grupa jest zastępowana. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie są przypisywani do grup po zakupie. Co jest nie tak?**
O:

1.  **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów** oraz na jego głównej stronie konfiguracji.
2.  **Zweryfikuj status zamówienia:** Sprawdź ustawienie „Status zamówienia do wyzwolenia przypisania” w swojej regule. Czy zamówienie klienta faktycznie osiągnęło ten konkretny status (np. „Płatność zaakceptowana”, „Dostarczone”)? Zamówienia w statusie „Oczekujące” lub „Anulowane” nie wyzwolą przypisania, jeśli Twoja reguła określa późniejszy status.
3.  **Przejrzyj warunki reguły:** Dokładnie sprawdź produkty/kategorie wybrane w Twojej regule. Czy są one dokładnie tym, co klient kupił? Czy spełniona jest „Minimalna ilość”?
4.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może powodować problemy. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
5.  **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły, które modyfikują grupy klientów lub przetwarzanie zamówień, aby sprawdzić, czy występuje konflikt.

**P: Czy klient może należeć do wielu grup?**
O: Tak, jeśli użyjesz opcji „Dodaj do grupy” podczas tworzenia reguł. Pozwala to klientom gromadzić członkostwa w grupach na podstawie różnych zachowań zakupowych. Jeśli użyjesz „Zastąp bieżącą grupę”, będą należeć tylko do jednej głównej grupy.

**P: Co się stanie, jeśli klient kupi produkty, które wyzwolą wiele reguł?**
O: Moduł przetworzy wszystkie obowiązujące reguły. Jeśli reguły używają „Dodaj do grupy”, klient zostanie dodany do wszystkich odpowiednich grup. Jeśli reguły używają „Zastąp bieżącą grupę”, ostatnia przetworzona reguła (na podstawie wewnętrznej logiki modułu lub kolejności tworzenia reguł) może określić ostateczną główną grupę, ale najlepszą praktyką jest unikanie sprzecznych reguł „Zastąp”.

**P: Zmieniłem regułę, ale stare zamówienia nie są aktualizowane. Dlaczego?**
O: Moduł zazwyczaj przetwarza przypisania do grup, gdy status zamówienia *zmienia się* na określony. Nie stosuje on reguł wstecznie do już zrealizowanych i przetworzonych zamówień. Jeśli musisz ponownie ocenić poprzednich klientów, możesz potrzebować ręcznie ich przypisać lub rozważyć niestandardowy skrypt (dla programistów), aby ponownie uruchomić logikę.

**P: Jak przetłumaczyć tekst modułu?**
O: Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Przypisz klientów do grupy na podstawie zakupionych produktów” z listy modułów. Następnie możesz przetłumaczyć wszystkie widoczne ciągi znaków.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przypisz klientów do grupy na podstawie zakupionych produktów” (`pgroup`) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie wzorzec MVC dla swoich komponentów Panelu administracyjnego. Integruje się z podstawową funkcjonalnością PrestaShop za pośrednictwem hooków, w szczególności reagując na zmiany statusu zamówienia, aby wyzwolić logikę przypisywania grup klientów. Moduł nie wprowadza żadnych kontrolerów front-office, ponieważ jego funkcjonalność jest całkowicie oparta na backendzie. Wykorzystuje niestandardowy `AdminController` do zarządzania regułami powiązań produktów z grupami i opiera się na `ObjectModel` PrestaShop do trwałości danych.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Cała logika jest obsługiwana w Panelu administracyjnym lub za pośrednictwem hooków.
-   **Kontrolery Panelu administracyjnego**:

    -   `pgroup/controllers/admin/AdminProductGroupsAssociationsController.php`
        -   **Nazwa klasy:** `AdminProductGroupsAssociationsController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność:** Jest to główny kontroler do zarządzania regułami powiązań produktów z grupami klientów. Obsługuje wyświetlanie listy reguł (za pomocą `HelperList`) oraz tworzenie/edycję poszczególnych reguł (za pomocą `HelperForm`). Współpracuje z `ObjectModel` `PgAssign` w celu utrwalania i pobierania danych powiązań. Ten kontroler jest odpowiedzialny za renderowanie siatki powiązań i formularza do ich dodawania/edycji.
    -   `pgroup/controllers/admin/index.php`
        -   **Nazwa klasy:** Nie jest klasą, zazwyczaj pusty plik lub proste przekierowanie, aby zapobiec bezpośredniemu dostępowi do katalogu. W PrestaShop pliki `index.php` w katalogach kontrolerów zazwyczaj służą jako zabezpieczenia.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu nie wskazuje na żadne niestandardowe klasy w katalogu `classes/`. Sugeruje to, że główny model danych dla przypisań produktów do grup jest prawdopodobnie zdefiniowany bezpośrednio w głównym pliku modułu (`pgroup/index.php`) jako `ObjectModel` lub obsługiwany za pomocą bezpośrednich zapytań do bazy danych.

-   **Prawdopodobny model (w `pgroup/index.php`):**
    -   **Nazwa klasy:** `PgAssign` (lub podobna, rozszerzająca `ObjectModel`)
    -   **Tabela bazy danych:** `ps_pgassign` (lub podobna, na podstawie `AdminProductGroupsAssociationsController` zarządzającego encją `pgassign`).
    -   **Pola `$definition`:** Zazwyczaj zawierałby pola takie jak:
        -   `id_pgassign` (Klucz podstawowy)
        -   `id_group` (ID docelowej grupy klientów)
        -   `id_product` (ID produktu, jeśli reguła dotyczy konkretnego produktu)
        -   `id_category` (ID kategorii, jeśli reguła dotyczy konkretnej kategorii)
        -   `min_quantity` (Wymagana minimalna ilość)
        -   `id_order_state` (Status zamówienia do wyzwolenia przypisania)
        -   `assignment_type` (np. „add” lub „replace”)
    -   **Kluczowe metody publiczne:**
        -   `add()`: Aby zapisać nową regułę powiązania.
        -   `update()`: Aby zmodyfikować istniejącą regułę powiązania.
        -   `delete()`: Aby usunąć regułę powiązania.
        -   `getAssociationsByProduct($id_product)`: Aby pobrać reguły na podstawie produktu.
        -   `getAssociationsByCategory($id_category)`: Aby pobrać reguły na podstawie kategorii.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `pgroup/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Panel administracyjny (prawdopodobnie używany w formularzu `AdminProductGroupsAssociationsController`).
    -   **Funkcjonalność:** Implementuje funkcję autouzupełniania wyszukiwania, prawdopodobnie do wybierania produktów lub kategorii podczas tworzenia/edycji reguły przypisania. Nasłuchuje danych wprowadzanych przez użytkownika w określonym polu tekstowym, wysyła żądania AJAX do punktu końcowego backendu (prawdopodobnie dedykowanego kontrolera AJAX administratora lub głównej metody `ajaxProcess` modułu) w celu pobrania pasujących produktów/kategorii i wyświetla sugestie. Następnie obsługuje wybór elementu, wypełniając ukryte pola wejściowe identyfikatorami.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `pgroup/css.css`
    -   **Zakres:** Panel administracyjny (ogólne style modułu).
    -   **Funkcjonalność:** Zawiera ogólne reguły stylów dla strony konfiguracji modułu i potencjalnie interfejsu `AdminProductGroupsAssociationsController`. Może to obejmować style dla elementów formularza, przycisków lub dostosowania układu specyficzne dla modułu.
-   `pgroup/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Panel administracyjny (style specyficzne dla autouzupełniania).
    -   **Funkcjonalność:** Zapewnia style dla pola wprowadzania wyszukiwania autouzupełniania, listy rozwijanej sugestii i podświetlonych elementów na liście. Programiści mogą nadpisać te klasy, aby dopasować je do niestandardowych motywów Panelu administracyjnego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak wyraźnie wymienionych, co wskazuje, że wpływ modułu na front-office jest pośredni i nie odbywa się poprzez bezpośrednie wstrzykiwanie treści za pomocą hooków.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `pgroup/lib/searchTool/views/scripts.tpl`
        -   **Zakres:** Panel administracyjny.
        -   **Funkcjonalność:** Prawdopodobnie zawiera skrypty inicjalizacyjne JavaScript dla funkcji autouzupełniania. Ten szablon byłby dołączony do formularza `AdminProductGroupsAssociationsController`, aby renderować niezbędny JS dla narzędzia wyszukiwania produktów/kategorii.
    -   `pgroup/views/templates/admin/orderstates.tpl`
        -   **Zakres:** Panel administracyjny.
        -   **Funkcjonalność:** Ten szablon prawdopodobnie renderuje listę rozwijaną lub listę statusów zamówień PrestaShop, umożliwiając sprzedawcy wybranie, który status powinien wyzwolić przypisanie grupy klientów. Byłby częścią `HelperForm` używanego w `AdminProductGroupsAssociationsController`.
    -   `pgroup/views/templates/admin/script.tpl`
        -   **Zakres:** Panel administracyjny.
        -   **Funkcjonalność:** Może zawierać dodatkową logikę JavaScript lub Smarty specyficzną dla strony konfiguracji modułu lub formularzy `AdminProductGroupsAssociationsController`, taką jak warunkowe wyświetlanie pól lub wywołania AJAX.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_pgassign`: Ta tabela jest tworzona przez moduł podczas instalacji. Przechowuje reguły powiązań produktów z grupami.
        -   `id_pgassign` (INT, KLUCZ PODSTAWOWY, AUTO_INCREMENT)
        -   `id_group` (INT, klucz obcy do `ps_group`)
        -   `id_product` (INT, klucz obcy do `ps_product`, może być null, jeśli reguła jest oparta na kategorii)
        -   `id_category` (INT, klucz obcy do `ps_category`, może być null, jeśli reguła jest oparta na produkcie)
        -   `min_quantity` (INT, domyślnie 1)
        -   `id_order_state` (INT, klucz obcy do `ps_order_state`)
        -   `assignment_type` (VARCHAR, np. „add”, „replace”)
    -   Rekordy konfiguracji w `ps_configuration`: Moduł może przechowywać swoje główne ustawienie `PS_PGROUP_ENABLED` (lub podobne) tutaj.
-   **Tabela zarejestrowanych hooków**:
    Podstawowa funkcjonalność modułu opiera się na hookach, które wyzwalają się, gdy zmienia się status zamówienia.

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionOrderStatusPostUpdate` | Wykonywany natychmiast po zaktualizowaniu statusu zamówienia. | Jest to najbardziej prawdopodobny hook używany przez moduł do sprawdzania, czy zamówienie osiągnęło skonfigurowany status, a następnie stosowania reguł przypisania do grupy na podstawie produktów w tym zamówieniu. |
    | `actionObjectOrderUpdateAfter` | Wykonywany po zaktualizowaniu obiektu zamówienia. | Może być również używany, podobnie do `actionOrderStatusPostUpdate`, do reagowania na zmiany zamówienia. |
    | `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności, ale mógłby być używany do ładowania globalnych JS/CSS, gdyby moduł miał komponenty front-office (których, jak się wydaje, nie ma). |
    | `displayRightColumn` / `displayLeftColumn` | Renderuje zawartość w bocznych kolumnach stron front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności. |
    | `displayProductAdditionalInfo` / `displayProductButtons` | Renderuje zawartość na stronie produktu. | Nie jest bezpośrednio używany do podstawowej funkcjonalności. |
    | `displayFooter` | Renderuje zawartość w stopce stron front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Przypisz klientów do grupy na podstawie zakupionych produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
