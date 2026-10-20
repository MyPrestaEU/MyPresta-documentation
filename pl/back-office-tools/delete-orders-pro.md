---
title: "Delete Orders Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Delete Orders Pro od MyPresta.eu."
sidebar:
  label: "Delete Orders Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Delete Orders Pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/delete-orders-pro/)
>
> ---


# Delete Orders Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu „Delete Orders Pro”. Ten ekran głównie obsługuje ogólne ustawienia modułu i sprawdzanie aktualizacji.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera standardowe ustawienia modułów MyPresta.eu związane z powiadomieniami o aktualizacjach i wewnętrznym śledzeniem.
-   **Efekt zmiany tego ustawienia:**
    -   `mypresta_updates`, `update_`, `updatev_`: Te ustawienia kontrolują, czy moduł sprawdza aktualizacje z MyPresta.eu i wyświetla powiadomienia w Twoim panelu administracyjnym. Włączenie ich zapewnia informowanie o nowych wersjach i funkcjach. Wyłączenie ich zatrzyma te powiadomienia.
    -   `DELETEORDERS_LAST_TAB`: Jest to wewnętrzne ustawienie, które śledzi ostatnią zakładkę lub widok, na którym byłeś w dedykowanym interfejsie administracyjnym modułu. Pomaga modułowi zapamiętać Twoją ostatnią pozycję dla wygody.
-   **Zalecana wartość:**
    -   Dla ustawień związanych z aktualizacjami: **TAK** (lub Włączone). Zawsze zaleca się utrzymywanie włączonych kontroli aktualizacji, aby upewnić się, że używasz najnowszej, najbezpieczniejszej i najbardziej funkcjonalnej wersji modułu.
    -   `DELETEORDERS_LAST_TAB`: Pozostaw to ustawienie bez zmian; jest ono zarządzane automatycznie przez moduł.
-   **Scenariusz / przykład dla sprzedawcy:** Utrzymywanie włączonych kontroli aktualizacji oznacza, że będziesz powiadamiany bezpośrednio w panelu administracyjnym PrestaShop, gdy zostanie wydana nowa wersja „Delete Orders Pro”, co zapewni łatwą aktualizację i skorzystanie z ulepszeń lub poprawek błędów.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zakładka Usuń zamówienia (Panel administracyjny > Zamówienia > Delete Orders Pro)

Jest to główny interfejs, w którym będziesz zarządzać i usuwać zamówienia.

-   **Nazwa ekranu i lokalizacja w menu:** Dostęp do tego ekranu można uzyskać, przechodząc do **Zamówienia > Delete Orders Pro** w menu panelu administracyjnego PrestaShop.
-   **Dostępne akcje i ustawienia:** Ten ekran przedstawia widok siatki lub listy Twoich zamówień, podobny do standardowej listy zamówień PrestaShop, ale z dodatkową funkcjonalnością specjalnie do usuwania.
    -   **Opcje filtrowania:** Prawdopodobnie znajdziesz filtry do zawężenia zamówień, które chcesz usunąć (np. według statusu zamówienia, zakresu dat, klienta itp.). Jest to kluczowe dla bezpiecznego celowania w określone typy zamówień.
    -   **Pola wyboru:** Każde zamówienie na liście będzie miało pole wyboru, umożliwiające zaznaczenie pojedynczych zamówień do usunięcia.
    -   **Akcje masowe:** Powinna istnieć opcja zaznaczenia wielu zamówień (np. „Zaznacz wszystko” lub „Zaznacz zamówienia o statusie X”), a następnie wykonania masowego usunięcia.
    -   **Przycisk Usuń:** Widoczny przycisk (np. „Usuń wybrane zamówienia” lub „Usuń zamówienia”) rozpocznie proces usuwania.
-   **Efekt zmian:**
    -   Po wybraniu zamówień i kliknięciu przycisku usuwania, moduł trwale usunie te zamówienia i wszystkie powiązane dane (szczegóły zamówienia, zamówione produkty, wiadomości klienta związane z zamówieniem, faktury itp.) z Twojej bazy danych PrestaShop.
    -   Ta akcja jest nieodwracalna.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Regularnie przeglądaj swoje zamówienia:** Zidentyfikuj, które statusy zamówień zazwyczaj reprezentują „niechciane” zamówienia (np. „Anulowane”, „Błąd płatności”, „W oczekiwaniu” jeśli nie zostały zrealizowane, lub niestandardowe statusy dla zamówień testowych).
    2.  **Dostęp do „Delete Orders Pro”:** Przejdź do **Zamówienia > Delete Orders Pro**.
    3.  **Filtruj zamówienia:** Użyj dostępnych filtrów, aby wyświetlić tylko te zamówienia, które zamierzasz usunąć (np. filtruj według statusu „Anulowane” i zakresu dat starszych niż 3 miesiące).
    4.  **Ostrożnie wybierz zamówienia:** Dokładnie sprawdź przefiltrowane zamówienia i zaznacz je za pomocą pól wyboru.
    5.  **Rozpocznij usuwanie:** Kliknij przycisk „Usuń wybrane zamówienia”. Potwierdź akcję, gdy zostaniesz o to poproszony.
    6.  **Wykonaj kopie zapasowe:** Przed każdym większym usunięciem zawsze upewnij się, że masz aktualną kopię zapasową bazy danych.

#### 2.2.2 Kontroler Index (deleteorderspro/controllers/admin/index.php)

Ten plik zazwyczaj służy jako kontroler routingu lub awaryjny w sekcji administracyjnej modułu. W kontekście „Delete Orders Pro” prawdopodobnie zapewnia, że jeśli użytkownik nawiguje do podstawowej ścieżki administracyjnej modułu bez określania konkretnej akcji lub podkontrolera, zostanie przekierowany do głównego interfejsu `deleteorderstab`.

-   **Nazwa ekranu i lokalizacja w menu:** Nie jest to bezpośredni ekran, ale część wewnętrznej nawigacji modułu.
-   **Dostępne akcje i ustawienia:** Brak bezpośrednich ustawień konfigurowalnych przez użytkownika. Jego celem jest zarządzanie wewnętrznym routingiem.
-   **Efekt zmian:** Brak bezpośredniego wpływu na sprzedawcę. Zapewnia płynne doświadczenie nawigacji w sekcji administracyjnej modułu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Nie jest potrzebny żaden konkretny przepływ pracy; działa to w tle.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | `mypresta_updates` | TAK | Włącza/wyłącza powiadomienia o aktualizacjach z MyPresta.eu. |
| | `update_` | TAK | Wewnętrzna flaga statusu aktualizacji. |
| | `updatev_` | TAK | Wewnętrzna flaga wersji aktualizacji. |
| | `DELETEORDERS_LAST_TAB` | (Zarządzane automatycznie) | Śledzi ostatnio odwiedzoną zakładkę w interfejsie administracyjnym modułu. |
| **Zakładka Usuń zamówienia** | Filtry (Status, Data itp.) | Różne | Zawęża listę zamówień do usunięcia. |
| | Pola wyboru zamówień | N/D | Umożliwia wybór pojedynczych zamówień do usunięcia. |
| | Akcja masowa: Usuń wybrane | N/D | Trwale usuwa wybrane zamówienia i powiązane dane. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Usunąłem zamówienia, ale wydajność mojego sklepu nie wydaje się znacznie szybsza. Dlaczego?**
O: Chociaż usuwanie zamówień zmniejsza rozmiar bazy danych, na wydajność wpływa wiele czynników (hosting, inne moduły, optymalizacja szablonu, rozmiary obrazów). Usuwanie zamówień to jeden z kroków w ogólnej optymalizacji. Upewnij się, że po usunięciu wyczyściłeś również pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).

**P: Czy mogę odzyskać zamówienia po ich usunięciu?**
O: Nie. Po usunięciu zamówień za pomocą tego modułu są one trwale usuwane z Twojej bazy danych. Dlatego tak ważne jest, aby zawsze tworzyć kopię zapasową bazy danych przed wykonaniem jakiegokolwiek większego usunięcia i dokładnie przeglądać swoje wybory.

**P: Czy usunięcie zamówień wpłynie na konta klientów lub stan magazynowy produktów?**
O: Usunięcie zamówienia usuwa sam rekord zamówienia i powiązane z nim szczegóły (takie jak konkretne produkty zamówione w ramach tej transakcji, faktury, wiadomości). NIE usuwa konta klienta powiązanego z zamówieniem, ani zazwyczaj nie przywraca poziomów zapasów (ponieważ zapasy są zazwyczaj korygowane w momencie tworzenia zamówienia lub zmiany statusu, a nie usunięcia). Zawsze weryfikuj zachowanie modułu w środowisku testowym, jeśli masz konkretne obawy dotyczące zapasów.

**P: Moduł nie pojawia się w moim menu Panelu administracyjnego.**
O:

1.  **Sprawdź instalację:** Przejdź do **Moduły > Menedżer modułów** i wyszukaj „Delete Orders Pro”. Upewnij się, że jest on wymieniony jako „Zainstalowany” i „Włączony”.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami zmiany w menu wymagają odświeżenia pamięci podręcznej.
3.  **Uprawnienia:** Sprawdź swoje uprawnienia użytkownika w **Administracja > Uprawnienia**, aby upewnić się, że Twój profil ma dostęp do sekcji „Zamówienia” i wszelkich uprawnień specyficznych dla modułu.

**P: Otrzymuję błąd podczas próby usunięcia zamówień.**
O:

1.  **Włącz tryb debugowania PrestaShop:** Włącz tryb debugowania (**Zaawansowane > Wydajność > Tryb debugowania**), aby sprawdzić, czy pojawi się bardziej szczegółowy komunikat o błędzie.
2.  **Logi błędów serwera:** Sprawdź logi błędów PHP na swoim serwerze (często znajdują się w panelu sterowania hostingu) pod kątem wszelkich powiązanych komunikatów.
3.  **Skontaktuj się z pomocą techniczną:** Jeśli nie możesz rozwiązać problemu, zbierz wszelkie komunikaty o błędach i skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów pracujących z modułem „Delete Orders Pro”.

### 4.1 Przegląd architektury

Moduł „Delete Orders Pro” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie kontrolery administracyjne Back-Office do swojej funkcjonalności. Integruje się z systemem menu PrestaShop i używa podstawowego `AdminController` PrestaShop do renderowania list i obsługi przesyłania formularzy. Moduł bezpośrednio wchodzi w interakcje z bazą danych w celu wykonywania operacji usuwania na tabelach związanych z zamówieniami. Nie wprowadza niestandardowych klas `ObjectModel`, ale działa na istniejących encjach zamówień PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Ten moduł nie ma obecności w Front-Office.
-   **Kontrolery administracyjne Back-Office**:

    -   `deleteorderspro/controllers/admin/deleteorderstab.php`

        -   **Nazwa klasy**: `AdminDeleteOrdersProController` (lub podobna, zazwyczaj pochodząca od nazwy pliku i kontekstu modułu) rozszerzająca `ModuleAdminController`.
        -   **Odpowiedzialność**: Jest to główny kontroler administracyjny modułu. Jest odpowiedzialny za:
            -   Wyświetlanie listy zamówień w formacie siatki.
            -   Obsługę filtrowania, sortowania i paginacji zamówień.
            -   Przetwarzanie usuwania wybranych zamówień.
            -   Interakcję z podstawowymi `Order` PrestaShop i powiązanymi `ObjectModel`ami w celu wykonania usunięć z bazy danych.
            -   Renderowanie szablonu dla listy zamówień i interfejsu usuwania.
        -   **Zakładka PrestaShop**: Ten kontroler jest zarejestrowany jako nowa zakładka w menu „Zamówienia” w panelu administracyjnym PrestaShop.
    -   `deleteorderspro/controllers/admin/index.php`

        -   **Nazwa klasy**: Nie jest to typowa klasa kontrolera; często prosty plik przekierowania lub bootstrap.
        -   **Odpowiedzialność**: Ten plik zazwyczaj służy jako awaryjny punkt wejścia. W wielu modułach, jeśli użytkownik nawiguje do podstawowej ścieżki `admin/nazwa_modułu`, ten `index.php` może przekierować go do głównego kontrolera (np. `deleteorderstab`), aby zapewnić załadowanie prawidłowego interfejsu. Zapobiega bezpośredniemu dostępowi do katalogu i zapewnia prawidłowe routowanie.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie wydaje się wprowadzać żadnych niestandardowych klas ani `ObjectModel` w swoim katalogu `classes/` na podstawie dostarczonego spisu. Prawdopodobnie działa bezpośrednio na podstawowych `Order` PrestaShop i powiązanych `ObjectModel`ach (np. `OrderHistory`, `OrderDetail`, `ProductSale`, `Cart` itp.), aby zapewnić kompleksowe usunięcie wszystkich powiązanych danych.

### 4.4 Zasoby JavaScript (`views/js/`)

W archiwum modułu nie zidentyfikowano żadnych plików JavaScript. Moduł prawdopodobnie opiera się na standardowym JavaScript Back Office PrestaShop do przesyłania formularzy i interakcji z siatką, lub jego funkcjonalność jest całkowicie po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

W archiwum modułu nie zidentyfikowano żadnych plików CSS. Moduł prawdopodobnie dziedziczy styl bezpośrednio z motywu Back Office PrestaShop, zapewniając spójny wygląd i działanie bez niestandardowych stylów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

W archiwum modułu nie zidentyfikowano żadnych plików `.tpl`. Sugeruje to, że moduł może używać domyślnych szablonów `list.tpl` i `form.tpl` dostarczonych przez `AdminController` do renderowania swojej siatki i konfiguracji, lub generuje swój kod HTML bezpośrednio w kontrolerze.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy niestandardowych tabel bazy danych. Działa na istniejących tabelach PrestaShop związanych z zamówieniami, w tym między innymi:

    -   `ps_orders`
    -   `ps_order_detail`
    -   `ps_order_history`
    -   `ps_order_invoice`
    -   `ps_order_payment`
    -   `ps_order_return`
    -   `ps_order_slip`
    -   `ps_cart` (i powiązane `ps_cart_product`)
    -   `ps_message` (dla wiadomości klienta związanych z zamówieniami)
    -   `ps_product_sale` (aktualizuje liczbę sprzedaży)
    -   `ps_customer_thread` (dla wątków obsługi klienta związanych z zamówieniami)
    -   `ps_configuration` (do przechowywania ustawień modułu, takich jak `mypresta_updates`, `DELETEORDERS_LAST_TAB`).
-   **Tabela zarejestrowanych hooków**:
    Na podstawie przeznaczenia modułu jako narzędzia administracyjnego Back Office, używa on głównie hooków do instalacji, deinstalacji i potencjalnie dodawania elementów menu. Nie wydaje się używać hooków wyświetlania Front Office.

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `install()` | Podczas instalacji modułu | Tworzy nową zakładkę „Delete Orders Pro” w menu panelu administracyjnego PrestaShop. Przechowuje początkowe wartości konfiguracji w `ps_configuration`. |
    | `uninstall()` | Podczas deinstalacji modułu | Usuwa zakładkę „Delete Orders Pro” z menu panelu administracyjnego. Usuwa wartości konfiguracji z `ps_configuration`. |
    | `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` Back Office | Potencjalnie używany do dołączania wszelkich niezbędnych JS/CSS dla kontrolera administracyjnego, chociaż żadnych nie zidentyfikowano w spisie. |
    | `actionAdminControllerSetMedia` | Umożliwia dodawanie JS/CSS do konkretnych kontrolerów administracyjnych | Używany przez `AdminDeleteOrdersProController` do dodawania wszelkich specyficznych zasobów wymaganych dla jego interfejsu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji i pobrania najnowszej wersji modułu „Delete Orders Pro” odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
