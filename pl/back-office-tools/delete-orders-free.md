---
title: "Delete Orders Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Delete Orders Free od MyPresta.eu."
sidebar:
  label: "Delete Orders Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Delete Orders Free na MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/delete-orders-free/)
>
> ---


# Delete Orders Free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu. Ta strona przede wszystkim obsługuje powiadomienia o aktualizacjach samego modułu.

-   **Co robi to ustawienie:** Ta sekcja zarządza zdolnością modułu do sprawdzania aktualizacji i wyświetlania powiadomień.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowszych wersji. Jeśli aktualizacja jest dostępna, w panelu administracyjnym PrestaShop może pojawić się powiadomienie, zachęcające do pobrania i zainstalowania najnowszej wersji. Zapewnia to, że zawsze masz najbardziej bezpieczną i bogatą w funkcje wersję modułu.
    -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał aktualizacji. Musiałbyś ręcznie odwiedzić MyPresta.eu, aby sprawdzić nowe wersje. Chociaż może to nieznacznie zmniejszyć liczbę żądań do serwera, oznacza to, że możesz przegapić ważne aktualizacje lub poprawki błędów.
-   **Zalecana wartość:** **Włączone (TAK)**. Utrzymywanie tego włączonego zapewnia, że zawsze jesteś informowany o najnowszych ulepszeniach i poprawkach bezpieczeństwa dla modułu.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz być powiadamiany, jeśli zostanie wydana nowa wersja „Delete Orders Free”, która naprawia błąd lub dodaje nową funkcję. Utrzymywanie tego włączonego zapewnia, że zobaczysz powiadomienie w panelu administracyjnym PrestaShop.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zakładka Usuń zamówienia (Panel administracyjny > Zamówienia > Usuń zamówienia)

Jest to główny interfejs funkcjonalności modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Możesz uzyskać dostęp do tego ekranu, przechodząc do **Zamówienia > Usuń zamówienia** w menu panelu administracyjnego PrestaShop.
-   **Dostępne akcje i ustawienia:**
    -   Po wejściu na tę zakładkę zobaczysz listę wszystkich zamówień w Twoim sklepie PrestaShop, podobną do standardowej listy „Zamówienia”.
    -   Każde zamówienie na liście będzie miało dedykowany przycisk **„Usuń”** lub ikonę (często ikonę kosza na śmieci) obok niego.
    -   **Usuwanie zamówienia:** Kliknięcie przycisku „Usuń” obok dowolnego zamówienia natychmiast i trwale usunie to zamówienie z Twojej bazy danych. Ta akcja jest nieodwracalna.
-   **Efekt zmian:**
    -   Po kliknięciu „Usuń” dla zamówienia, rekord zamówienia, wraz ze wszystkimi powiązanymi danymi (takimi jak szczegóły zamówienia, wiadomości klienta związane z tym zamówieniem, faktury i potencjalnie ruchy magazynowe, jeśli status zamówienia był skonfigurowany tak, aby wpływał na stan magazynowy) zostanie usunięty z Twojej bazy danych PrestaShop.
    -   Zamówienie nie będzie już pojawiać się na liście „Zamówienia” ani nie będzie uwzględniane w żadnych raportach sprzedaży ani statystykach.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie przeglądaj listę „Zamówienia” w poszukiwaniu zamówień testowych, oszukańczych lub zamówień, które zostały całkowicie anulowane i nie wymagają już śledzenia.
    2.  Przejdź do **Zamówienia > Usuń zamówienia**.
    3.  Starannie zidentyfikuj zamówienia, które chcesz usunąć.
    4.  Kliknij przycisk „Usuń” obok każdego konkretnego zamówienia, które chcesz usunąć.
    5.  Potwierdź usunięcie, jeśli zostaniesz o to poproszony.
    6.  **Ważne:** Zachowaj szczególną ostrożność, ponieważ ta akcja jest trwała i nie można jej cofnąć. Zdecydowanie zaleca się wykonanie kopii zapasowej bazy danych przed usunięciem dużej liczby zamówień.

#### 2.2.2 Index.php (deleteordersfree/controllers/admin/index.php)

Ten plik jest standardowym plikiem zastępczym kontrolera PrestaShop i zazwyczaj nie przedstawia bezpośredniego, konfigurowalnego ekranu dla sprzedawcy. Jego celem jest zazwyczaj przekierowanie do głównej konfiguracji modułu lub konkretnej zakładki administracyjnej. W kontekście tego modułu prawdopodobnie zapewnia, że nawigacja do podstawowej ścieżki administracyjnej modułu prawidłowo kieruje do kontrolera `deleteorderstab`.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Sprawdzanie aktualizacji (mypresta\_updates) | Włączone (TAK) | Kontroluje, czy moduł sprawdza nowe wersje i powiadamia Cię. Pozostaw włączone dla aktualizacji. |
| **Zamówienia > Usuń zamówienia** | Przycisk Usuń (dla każdego zamówienia) | N/A | Trwale usuwa wybrane zamówienie i powiązane z nim dane z bazy danych. **Akcja nieodwracalna.** |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Przypadkowo usunąłem zamówienie! Czy mogę je odzyskać?**
O: Niestety nie. Moduł „Delete Orders Free” wykonuje trwałe usunięcie. Dlatego podkreślamy ostrożność. Zawsze miej aktualną kopię zapasową swojej bazy danych, zwłaszcza przed wykonaniem masowych usunięć. Jeśli masz kopię zapasową, możesz być w stanie przywrócić całą bazę danych do poprzedniego stanu, ale to również cofnęłoby wszystkie inne zmiany dokonane od czasu wykonania kopii zapasowej.

**P: Nie widzę zakładki „Usuń zamówienia” w menu „Zamówienia”.**
O:

1.  **Sprawdź instalację modułu:** Przejdź do **Moduły > Menedżer modułów** i wyszukaj „Delete Orders Free”. Upewnij się, że jest zainstalowany i włączony.
2.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna menu PrestaShop wymaga odświeżenia. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”.
3.  **Sprawdź uprawnienia:** Upewnij się, że Twój profil użytkownika ma niezbędne uprawnienia do dostępu i zarządzania modułami i zamówieniami. Przejdź do **Zaawansowane > Zespół > Profile**, wybierz swój profil, a następnie przejdź do **Uprawnienia > Moduły** i **Uprawnienia > Zamówienia**, aby zweryfikować.

**P: Czy usunięcie zamówienia spowoduje również zwrot pieniędzy klientowi lub anulowanie płatności?**
O: Nie. Ten moduł usuwa tylko rekord zamówienia z Twojej bazy danych PrestaShop. NIE wchodzi w interakcje z bramkami płatności (takimi jak PayPal, Stripe itp.) w celu wydania zwrotów lub anulowania transakcji. Musisz samodzielnie obsłużyć wszelkie zwroty płatności lub zwroty pieniędzy bezpośrednio za pośrednictwem interfejsu swojej bramki płatności.

**P: Czy usunięcie zamówienia wpływa na stan magazynowy produktu?**
O: Jeśli konfiguracja PrestaShop dla statusów zamówień jest ustawiona na zmniejszanie stanu magazynowego po złożeniu zamówienia, a Ty usuniesz zamówienie, stan magazynowy NIE zostanie automatycznie zwiększony. Musiałbyś ręcznie dostosować stan magazynowy dla dotkniętych produktów, jeśli chcesz je ponownie umieścić w inwentarzu. Jest to kluczowy punkt do zapamiętania w zarządzaniu zapasami.

**P: Moduł jest zainstalowany, ale nie widzę żadnych przycisków „Usuń” na liście zamówień.**
O: Upewnij się, że jesteś na dedykowanej zakładce **Zamówienia > Usuń zamówienia**, a nie na standardowej liście **Zamówienia > Zamówienia**. Funkcja usuwania jest specjalnie dodana do niestandardowej zakładki modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Delete Orders Free” to prosty moduł PrestaShop, skupiający się głównie na rozszerzaniu funkcjonalności Panelu administracyjnego. Działa zgodnie ze standardowym wzorcem MVC PrestaShop dla swojego interfejsu administracyjnego. Podstawowa logika znajduje się w głównym pliku modułu do instalacji/deinstalacji oraz w dedykowanym AdminControllerze do zarządzania procesem usuwania zamówień. Nie wprowadza nowych tabel bazy danych ani złożonych interakcji z front-office.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Ten moduł nie ma obecności w front-office.
-   **Kontrolery administracyjne Back-Office**:

    -   `deleteordersfree/controllers/admin/deleteorderstab.php`
        -   **Nazwa klasy i klasa nadrzędna**: `DeleteOrdersTabController` rozszerza `ModuleAdminController`.
        -   **Odpowiedzialność**: Jest to główny kontroler funkcjonalności modułu. Renderuje listę zamówień w Panelu administracyjnym, zapewniając akcję „Usuń” dla każdego zamówienia. Obsługuje logikę odbierania żądania usunięcia (np. za pomocą parametru GET lub przesłania POST), a następnie wykonuje usunięcie z bazy danych dla określonego ID zamówienia. Ten kontroler prawdopodobnie nadpisuje lub rozszerza metody z `AdminController`, aby wyświetlić listę zamówień i dodać niestandardową akcję.
    -   `deleteordersfree/controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Jest to zazwyczaj plik zastępczy, który zapewnia prawidłowe routowanie w sekcji administracyjnej. Zazwyczaj zawiera proste przekierowanie `header('Location: ...')` lub pusty plik, aby zapobiec listowaniu katalogów. W PrestaShop pliki `index.php` w podkatalogach `controllers/admin` są często używane do definiowania punktu wejścia dla konkretnej sekcji lub do zapobiegania bezpośredniemu dostępowi. Dla tego modułu prawdopodobnie zapewnia, że dostęp do podstawowej ścieżki `admin/deleteordersfree` prawidłowo kieruje do kontrolera `deleteorderstab`.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Bezpośrednio wchodzi w interakcje z podstawowymi klasami `Order` PrestaShop i powiązanymi klasami `ObjectModel` (np. `OrderInvoice`, `OrderPayment`, `OrderHistory`, `Message`, `Cart`, `CustomerThread`, `SpecificPrice`, `StockAvailable`) w celu wykonania usunięć.

### 4.4 Zasoby JavaScript (`views/js/`)

W tym module nie ma niestandardowych plików JavaScript. Akcja usunięcia jest prawdopodobnie obsługiwana za pomocą standardowego przesłania formularza lub prostego żądania GET z monitem o potwierdzenie.

### 4.5 Arkusze stylów CSS (`views/css/`)

W tym module nie ma niestandardowych plików CSS. Moduł opiera się na domyślnej stylizacji Panelu administracyjnego PrestaShop dla swojego interfejsu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

W inwentarzu modułu nie ma jawnie wymienionych niestandardowych plików szablonów Smarty. Kontroler `deleteorderstab` prawdopodobnie używa domyślnych szablonów PrestaShop `list.tpl` lub podobnych do renderowania siatki zamówień, wstrzykując akcję „Usuń” poprzez logikę kontrolera (np. metodę `renderList()`).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych nowych niestandardowych tabel bazy danych. Działa bezpośrednio na istniejących podstawowych tabelach PrestaShop związanych z zamówieniami, takich jak:

    -   `ps_orders`
    -   `ps_order_detail`
    -   `ps_order_history`
    -   `ps_order_invoice`
    -   `ps_order_payment`
    -   `ps_message` (dla wiadomości związanych z zamówieniem)
    -   `ps_cart` (koszyk powiązany z zamówieniem)
    -   `ps_customer_thread` (wątki obsługi klienta związane z zamówieniem)
    -   `ps_specific_price` (jeśli ceny specyficzne zostały zastosowane za pośrednictwem zamówienia)
    -   `ps_stock_available` (jeśli stan magazynowy został zmniejszony przez zamówienie)
    -   I potencjalnie inne powiązane tabele (np. `ps_order_carrier`, `ps_order_slip`).
    Przechowuje również swoje ustawienia konfiguracyjne (takie jak `mypresta_updates`) w tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:
    Opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, ale funkcjonalność modułu jest wyłącznie administracyjna. Sugeruje to, że te hooki albo nie są aktywnie używane przez podstawową logikę modułu, albo są pozostałościami po ogólnym szablonie modułu. Na podstawie deklarowanego celu modułu i inwentarza plików, jest bardzo mało prawdopodobne, aby renderował cokolwiek w tych hookach front-office.

    Główne zastosowanie hooków dla tego modułu to prawdopodobnie:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionAdminControllerSetMedia` | Wykonywany, gdy AdminController jest inicjalizowany i przed renderowaniem jego zawartości. | Potencjalnie używany do dodawania niestandardowych JS/CSS (chociaż żadne nie są wymienione) lub do rejestrowania specyficznych zasobów związanych z modułem dla strony administracyjnej. |
    | `displayBackOfficeHeader` | Wykonywany w nagłówku każdej strony Panelu administracyjnego. | Może być używany do powiadomień o aktualizacjach lub do wstrzykiwania drobnych skryptów/stylów specyficznych dla administratora. |
    | `actionModuleInstall` | Wykonywany podczas instalacji modułu. | Tworzy zakładkę „Usuń zamówienia” w menu Panelu administracyjnego i ustawia domyślne wartości konfiguracyjne. |
    | `actionModuleUninstall` | Wykonywany podczas deinstalacji modułu. | Usuwa zakładkę „Usuń zamówienia” i czyści wartości konfiguracyjne. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Delete Orders Free”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań związanych z funkcjonalnością modułu.
