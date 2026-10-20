---
title: "Order Grid Manager Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Order Grid Manager Free od MyPresta.eu."
sidebar:
  label: "Order Grid Manager Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order Grid Manager Free na MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-manager-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/order-grid-manager-free/)
>
> ---


# Order Grid Manager Free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) zazwyczaj dołączone do każdego nowoczesnego środowiska hostingowego.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu. Tutaj znajdziesz listę wszystkich kolumn, które pojawiają się na liście zamówień w Panelu administracyjnym PrestaShop. Każda kolumna ma prosty przełącznik WŁ./WYŁ.

**Nazwa ekranu i lokalizacja w menu:**

- **Ścieżka menu:** Panel administracyjny > Moduły > Menedżer modułów > Order Grid Manager Free > Konfiguruj

**Dostępne ustawienia:**
Zobaczysz listę pól wyboru lub przełączników, z których każdy odpowiada kolumnie na liście zamówień w Panelu administracyjnym. Dokładna lista kolumn może się nieznacznie różnić w zależności od wersji PrestaShop i innych zainstalowanych modułów, ale typowe przykłady obejmują:

-   **ID:** Unikalny identyfikator każdego zamówienia.

    -   **Co robi to ustawienie:** Kontroluje, czy kolumna „ID” jest widoczna na liście zamówień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „ID” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „ID” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Często przydatne do szybkiego odniesienia i wsparcia).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli często odwołujesz się do zamówień za pomocą ich unikalnego ID podczas komunikacji z klientami lub magazynem, pozostaw to włączone. Jeśli używasz głównie innych identyfikatorów, takich jak nazwa klienta lub referencja, możesz to ukryć.
-   **Referencja:** Wewnętrzny numer referencyjny zamówienia.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Referencja”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Referencja” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Referencja” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Kluczowe dla śledzenia i komunikacji wewnętrznej).
    -   **Scenariusz/przykład dla sprzedawcy:** Większość sprzedawców używa referencji zamówienia do listów przewozowych, faktur i obsługi klienta. Pozostaw to widoczne, chyba że masz bardzo specyficzny przepływ pracy, który tego nie używa.
-   **Nowy klient:** Wskazuje, czy zamówienie pochodzi od nowego klienta.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Nowy klient”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Nowy klient” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Nowy klient” zostanie ukryta.
    -   **Zalecana wartość:** NIE (Chyba że konkretnie celujesz w dane nowych klientów w swoim codziennym przepływie pracy).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój zespół marketingowy często przegląda zamówienia w celu identyfikacji trendów pozyskiwania nowych klientów, możesz to pozostawić widoczne. W przeciwnym razie często jest to dobry kandydat do ukrycia dla czystszego widoku.
-   **Klient:** Nazwa klienta, który złożył zamówienie.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Klient”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Klient” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Klient” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Prawie zawsze niezbędne do identyfikacji zamówienia).
    -   **Scenariusz/przykład dla sprzedawcy:** Prawie na pewno musisz widzieć, kto złożył zamówienie. Pozostaw to włączone.
-   **Suma:** Całkowita kwota zamówienia.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Suma”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Suma” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Suma” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Ważne dla przeglądu finansowego).
    -   **Scenariusz/przykład dla sprzedawcy:** Niezbędne do szybkiego zobaczenia wartości każdego zamówienia. Pozostaw to włączone.
-   **Płatność:** Metoda płatności użyta do zamówienia.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Płatność”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Płatność” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Płatność” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Przydatne do uzgadniania płatności).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli musisz szybko zobaczyć, czy zamówienie zostało opłacone kartą kredytową, PayPalem lub przelewem bankowym, pozostaw to włączone.
-   **Status:** Aktualny status zamówienia (np. Płatność zaakceptowana, Wysyłka, Dostarczono).

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Status”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Status” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Status” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Krytyczne dla śledzenia postępu zamówienia).
    -   **Scenariusz/przykład dla sprzedawcy:** Absolutnie niezbędne do zarządzania realizacją zamówień. Pozostaw to włączone.
-   **Data:** Data i godzina złożenia zamówienia.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Data”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Data” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Data” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Ważne dla porządku chronologicznego i starzenia się).
    -   **Scenariusz/przykład dla sprzedawcy:** Przydatne do sortowania zamówień według daty ich złożenia lub identyfikowania starszych zamówień, które wymagają uwagi. Pozostaw to włączone.
-   **Faktura:** Link do podglądu/pobrania faktury.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Faktura”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Faktura” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Faktura” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Wygodne dla szybkiego dostępu do faktur).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój zespół często musi pobierać lub przeglądać faktury bezpośrednio z listy zamówień, pozostaw to włączone.
-   **Dostawa:** Link do podglądu/pobrania dowodu dostawy.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Dostawa”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Dostawa” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Dostawa” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Wygodne dla szybkiego dostępu do dowodów dostawy).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój magazyn lub zespół wysyłkowy używa dowodów dostawy, pozostawienie tego widocznym zapewnia szybki dostęp.
-   **Akcje:** Przyciski do przeglądania, edytowania lub usuwania zamówienia.

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny „Akcje”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kolumna „Akcje” zostanie wyświetlona.
        -   *Gdy wyłączone:* Kolumna „Akcje” zostanie ukryta.
    -   **Zalecana wartość:** TAK (Niezbędne do zarządzania pojedynczymi zamówieniami).
    -   **Scenariusz/przykład dla sprzedawcy:** Prawie zawsze będziesz musiał przeglądać lub edytować zamówienie. Pozostaw to włączone.

**Zapisywanie zmian:**
Po dokonaniu wyboru pamiętaj, aby kliknąć przycisk **„Zapisz”** (zazwyczaj na dole strony konfiguracji), aby zastosować zmiany. Po zapisaniu przejdź do **Zamówienia > Zamówienia** w Panelu administracyjnym, aby zobaczyć zaktualizowany układ kolumn.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | ID | TAK | Pokazuje/ukrywa unikalny identyfikator zamówienia. |
| Konfiguracja modułu | Referencja | TAK | Pokazuje/ukrywa wewnętrzną referencję zamówienia. |
| Konfiguracja modułu | Nowy klient | NIE | Pokazuje/ukrywa wskaźnik dla nowych klientów. |
| Konfiguracja modułu | Klient | TAK | Pokazuje/ukrywa nazwę klienta. |
| Konfiguracja modułu | Suma | TAK | Pokazuje/ukrywa całkowitą kwotę zamówienia. |
| Konfiguracja modułu | Płatność | TAK | Pokazuje/ukrywa używaną metodę płatności. |
| Konfiguracja modułu | Status | TAK | Pokazuje/ukrywa aktualny status zamówienia. |
| Konfiguracja modułu | Data | TAK | Pokazuje/ukrywa datę złożenia zamówienia. |
| Konfiguracja modułu | Faktura | TAK | Pokazuje/ukrywa link do pobrania faktury. |
| Konfiguracja modułu | Dostawa | TAK | Pokazuje/ukrywa link do pobrania dowodu dostawy. |
| Konfiguracja modułu | Akcje | TAK | Pokazuje/ukrywa przyciski akcji (podgląd, edycja, usuwanie). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale siatka zamówień się nie zmieniła.**
O: Po zapisaniu zmian w konfiguracji modułu, może być konieczne wyczyszczenie pamięci podręcznej PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Spróbuj również odświeżyć stronę przeglądarki (Ctrl+F5 lub Cmd+R), aby upewnić się, że nie widzisz buforowanej wersji Panelu administracyjnego.

**P: Czy mogę mieć różne widoki kolumn dla różnych użytkowników administratora?**
O: Moduł „Order Grid Manager Free” stosuje jedno, uniwersalne ustawienie dla wszystkich administratorów. Nie obsługuje indywidualnych preferencji użytkownika dotyczących widoczności kolumn. Jeśli potrzebujesz tej zaawansowanej funkcjonalności, być może będziesz musiał poszukać modułu premium lub niestandardowego rozwiązania.

**P: Czy ten moduł wpłynie na wydajność mojego sklepu?**
O: Nie, ten moduł ma znikomy wpływ na wydajność. Zmienia on tylko to, które kolumny są wyświetlane na liście zamówień w Panelu administracyjnym, co jest dostosowaniem renderowania po stronie klienta (przeglądarki) w oparciu o prostą konfigurację. Nie zmienia zapytań do bazy danych ani czasów ładowania front-office.

**P: Co jeśli przypadkowo ukryję kolumnę, której potrzebuję?**
O: Nie ma problemu! Po prostu wróć do **Moduły > Menedżer modułów > Order Grid Manager Free > Konfiguruj**, ponownie włącz żądaną kolumnę, zaznaczając jej pole, i zapisz zmiany. Następnie wyczyść pamięć podręczną i odśwież przeglądarkę.

**P: Czy ten moduł obsługuje tłumaczenia nazw kolumn na wiele języków?**
O: Sam moduł nie wprowadza nowych ciągów do tłumaczenia dla nazw kolumn. Po prostu kontroluje widoczność istniejących nazw kolumn PrestaShop, które są już obsługiwane przez podstawowy system tłumaczeń PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzyć moduł „Order Grid Manager Free”.

### 4.1 Przegląd architektury

Moduł `Order Grid Manager Free` to prosty moduł PrestaShop zaprojektowany głównie do modyfikowania wyświetlania listy `AdminOrders`. Wykorzystuje system konfiguracji PrestaShop do przechowywania preferencji użytkownika dotyczących widoczności kolumn i wstrzykuje JavaScript, aby dynamicznie ukrywać/pokazywać kolumny w oparciu o te ustawienia. Podąża za podstawową strukturą modułu PrestaShop, a jego podstawowa logika znajduje się w głównym pliku modułu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office. Cała konfiguracja i logika są obsługiwane w ramach głównej klasy modułu i jej metody `getContent()`.

### 4.3 Podstawowe klasy i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Działa bezpośrednio na podstawowej konfiguracji PrestaShop i istniejących strukturach Panelu administracyjnego.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych dedykowanych plików JavaScript w `views/js/`. Logika ukrywania/pokazywania kolumn jest prawdopodobnie wstrzykiwana bezpośrednio do Panelu administracyjnego za pomocą hooka lub w szablonie metody `getContent()`, przy użyciu wbudowanego JavaScriptu lub prostego wstrzyknięcia CSS. Biorąc pod uwagę prostotę modułu i oznaczenie „Free”, jest bardzo prawdopodobne, że ukrywanie kolumn odbywa się poprzez dodanie reguł CSS `display: none;` lub poprzez bezpośrednie manipulowanie DOM po załadowaniu strony, w oparciu o zapisaną konfigurację.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych dedykowanych plików CSS w `views/css/`. Podobnie jak w przypadku JavaScriptu, wszelkie style (głównie `display: none;` dla kolumn) są prawdopodobnie wstrzykiwane wbudowane lub dynamicznie generowane w oparciu o konfigurację.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`myordergridfree/views/templates/admin/advert.tpl`**:
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora).
    -   **Cel:** Ten szablon jest prawdopodobnie używany do wyświetlania reklamy lub komunikatu promocyjnego na stronie konfiguracji modułu w Panelu administracyjnym. Jest to powszechna praktyka w przypadku darmowych modułów, aby zawierać takie elementy. Nie kontroluje on bezpośrednio funkcjonalności siatki zamówień, ale jest częścią wyjścia `getContent()` modułu.

Rzeczywisty formularz konfiguracji widoczności kolumn jest prawdopodobnie renderowany bezpośrednio w metodzie `getContent()` głównego pliku modułu, być może przy użyciu `HelperForm` PrestaShop lub niestandardowego kodu HTML, a następnie `advert.tpl` jest dołączany do treści promocyjnych.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli PrestaShop `ps_configuration`. Każde ustawienie (np. `MYORDERGRIDFREE_HIDE_ID_COLUMN`) będzie odpowiadać wierszowi w tej tabeli, przechowując wartość boolean (0 lub 1) dla widoczności.
-   **Tabela zarejestrowanych hooków**:
    Główna funkcjonalność tego modułu polega na modyfikowaniu wyświetlania Panelu administracyjnego. Biorąc pod uwagę prostotę wersji „Free”, prawdopodobnie wykorzystuje jedno lub więcej z następujących podejść:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` stron Panelu administracyjnego. | Najbardziej prawdopodobny hook do wstrzykiwania wbudowanego CSS lub JavaScriptu w celu ukrycia kolumn na stronie `AdminOrders`. Pozwala to modułowi zastosować `display: none;` do określonych elementów `<th>` i `<td>` w oparciu o zapisaną konfigurację. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administratora ustawia swoje zasoby multimedialne. | Może być używany do rejestrowania małego pliku JS lub wbudowanego skryptu, który działa specjalnie na kontrolerze `AdminOrders` w celu manipulowania DOM. |
| `displayAdminOrderListBefore` / `displayAdminOrderListAfter` | Przed/po renderowaniu tabeli listy zamówień. | Mniej prawdopodobne dla tego modułu, ponieważ modyfikuje on samą listę, a nie tylko dodaje zawartość wokół niej. |

Metoda `install()` modułu zarejestrowałaby te hooki, a metoda `hookDisplayBackOfficeHeader()` (lub podobna) zawierałaby logikę pobierania zapisanej konfiguracji i wyprowadzania niezbędnego CSS/JS w celu ukrycia wybranych kolumn po załadowaniu strony `AdminOrders`.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Order Grid Manager Free”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
