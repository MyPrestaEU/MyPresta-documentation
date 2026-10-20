---
title: "Notatki samoprzylepne w Panelu administracyjnym - Instrukcja dla sprzedawcy i Przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Notatki samoprzylepne w Panelu administracyjnym” od MyPresta.eu."
sidebar:
  label: "Notatki samoprzylepne w Panelu administracyjnym - Instrukcja dla sprzedawcy i Przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Back office Sticky Notes na MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-sticky-notes.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/back-office-sticky-notes/)
>
> ---


# Notatki samoprzylepne w Panelu administracyjnym

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj preinstalowane w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu „Notatki samoprzylepne w Panelu administracyjnym”. To tutaj zarządzasz swoimi notatkami samoprzylepnymi.

Sama strona konfiguracji nie ma wielu „ustawień” w tradycyjnym sensie (jak przełączniki włącz/wyłącz). Zamiast tego jest to Twoje centralne centrum do tworzenia, edytowania i zarządzania wszystkimi notatkami samoprzylepnymi.

#### **Dodawanie nowej notatki samoprzylepnej**

Na górze strony konfiguracji zazwyczaj znajdziesz formularz lub sekcję do dodawania nowej notatki.

-   **Treść notatki (pole tekstowe):**

    -   **Co robi to ustawienie:** Tutaj wpisujesz rzeczywistą wiadomość lub przypomnienie dla swojej notatki samoprzylepnej.
    -   **Efekt zmiany tego ustawienia:** Cokolwiek wpiszesz tutaj, zostanie wyświetlone na notatce samoprzylepnej w Twoim panelu administracyjnym.
    -   **Zalecana wartość:** Bądź zwięzły i jasny. Używaj punktorów lub krótkich zdań dla czytelności.
    -   **Scenariusz / przykład dla sprzedawcy:** „Pamiętaj, aby skontaktować się z klientem #1234 w sprawie statusu jego zamówienia.” lub „Nowe zdjęcia produktów dla ‘Kolekcji Letniej’ do piątku.”
-   **Kolor notatki (selektor kolorów):**

    -   **Co robi to ustawienie:** Pozwala wybrać kolor tła notatki samoprzylepnej.
    -   **Efekt zmiany tego ustawienia:** Notatka samoprzylepna pojawi się z wybranym kolorem w panelu administracyjnym. Różne kolory mogą pomóc w kategoryzacji notatek lub podkreśleniu pilności.
    -   **Zalecana wartość:** Wybierz kolory, które się wyróżniają, ale nie są zbyt rozpraszające. Możesz użyć czerwonego dla pilnych notatek, żółtego dla ogólnych przypomnień i zielonego dla ukończonych zadań.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustaw notatkę o krytycznym błędzie na czerwono, a notatkę o nowym pomyśle marketingowym na żółto.
-   **Przycisk Zapisz / Dodaj notatkę:**

    -   **Co robi to ustawienie:** Przesyła wybraną treść i kolor, aby utworzyć nową notatkę samoprzylepną.
    -   **Efekt zmiany tego ustawienia:** Zostanie utworzona nowa notatka samoprzylepna, która pojawi się na stronach Twojego panelu administracyjnego. Zostanie również wymieniona w sekcji „Istniejące notatki” poniżej.
    -   **Zalecana wartość:** Kliknij to po sfinalizowaniu treści i koloru notatki.
    -   **Scenariusz / przykład dla sprzedawcy:** Po wpisaniu przypomnienia i wybraniu koloru kliknij „Zapisz”, aby aktywować notatkę.

#### **Zarządzanie istniejącymi notatkami samoprzylepnymi**

Poniżej sekcji „Dodaj nową notatkę” zobaczysz listę lub tabelę wszystkich notatek samoprzylepnych, które już utworzyłeś.

-   **Lista notatek (tabela/wyświetlanie):**

    -   **Co robi to ustawienie:** Pokazuje wszystkie aktywne notatki samoprzylepne, ich treść i przypisany kolor.
    -   **Efekt zmiany tego ustawienia:** Jest to wyświetlanie Twoich bieżących notatek. Możesz je tutaj wizualnie przeglądać.
    -   **Zalecana wartość:** Regularnie przeglądaj tę listę, aby upewnić się, że notatki są nadal aktualne.
    -   **Scenariusz / przykład dla sprzedawcy:** Szybko przeskanuj listę, aby zobaczyć wszystkie oczekujące zadania lub przypomnienia.
-   **Przycisk Edytuj (dla każdej notatki):**

    -   **Co robi to ustawienie:** Pozwala modyfikować treść lub kolor istniejącej notatki samoprzylepnej.
    -   **Efekt zmiany tego ustawienia:** Kliknięcie tego zazwyczaj załaduje treść notatki z powrotem do formularza „Dodaj nową notatkę” (który może zmienić się w tryb „Edytuj notatkę”), umożliwiając wprowadzenie zmian. Po zapisaniu notatka zostanie zaktualizowana w całym panelu administracyjnym.
    -   **Zalecana wartość:** Użyj tego do aktualizacji statusów zadań, dodawania więcej szczegółów lub zmiany pilności.
    -   **Scenariusz / przykład dla sprzedawcy:** Notatka mówi „Sprawdź nowe zdjęcia produktów”. Po sprawdzeniu możesz ją edytować na „Nowe zdjęcia produktów zatwierdzone”.
-   **Przycisk Usuń (dla każdej notatki):**

    -   **Co robi to ustawienie:** Trwale usuwa notatkę samoprzylepną.
    -   **Efekt zmiany tego ustawienia:** Notatka zniknie z Twojego panelu administracyjnego i nie będzie już wymieniona w konfiguracji. Ta akcja jest zazwyczaj nieodwracalna.
    -   **Zalecana wartość:** Usuwaj notatki tylko wtedy, gdy zadanie jest ukończone lub informacja nie jest już aktualna.
    -   **Scenariusz / przykład dla sprzedawcy:** Po rozwiązaniu problemu z zamówieniem usuń notatkę samoprzylepną z nim związaną.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Treść notatki (pole tekstowe)** | Jasny, zwięzły tekst | Rzeczywista wiadomość wyświetlana na notatce samoprzylepnej. |
| Strona konfiguracji modułu | **Kolor notatki (selektor kolorów)** | Wybrany przez użytkownika | Ustawia kolor tła notatki do kategoryzacji/pilności. |
| Strona konfiguracji modułu | **Przycisk Zapisz / Dodaj notatkę** | Kliknij po ustawieniu treści/koloru | Tworzy nową notatkę samoprzylepną widoczną w panelu administracyjnym. |
| Strona konfiguracji modułu | **Przycisk Edytuj (dla każdej notatki)** | Kliknij, aby zmodyfikować | Pozwala na aktualizację treści lub koloru istniejącej notatki. |
| Strona konfiguracji modułu | **Przycisk Usuń (dla każdej notatki)** | Kliknij, aby usunąć | Trwale usuwa notatkę samoprzylepną z panelu administracyjnego. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje notatki samoprzylepne nie pojawiają się w panelu administracyjnym po ich zapisaniu.**
O1:

-   **Wyczyść pamięć podręczną:** Najczęstszą przyczyną problemów z wyświetlaniem jest buforowanie. Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
-   **Sprawdź status modułu:** Upewnij się, że moduł jest nadal zainstalowany i włączony w **Moduły > Menedżer modułów**.
-   **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub otworzyć panel administracyjny w oknie incognito/prywatnym, aby wykluczyć problemy specyficzne dla przeglądarki.

**P2: Czy mogę przesuwać notatki samoprzylepne po ekranie?**
O2: Tak, po wyświetleniu notatki samoprzylepnej w panelu administracyjnym powinieneś móc kliknąć i przeciągnąć ją w dowolne miejsce na stronie. Moduł jest zaprojektowany tak, aby zapamiętywał jej pozycję.

**P3: Czy różni administratorzy mogą widzieć swoje notatki samoprzylepne?**
O3: Tak, domyślnie wszystkie notatki samoprzylepne utworzone za pomocą tego modułu są widoczne dla wszystkich administratorów, którzy mają dostęp do panelu administracyjnego. Jest to kluczowa funkcja do współpracy zespołowej.

**P4: Kolory moich notatek samoprzylepnych wyglądają dziwnie lub nie są stosowane prawidłowo.**
O4:

-   **Sprawdź selektor kolorów:** Upewnij się, że prawidłowo używasz narzędzia do wyboru kolorów na stronie konfiguracji modułu.
-   **Konflikty z niestandardowym motywem:** Jeśli używasz mocno dostosowanego motywu panelu administracyjnego, mogą wystąpić konflikty CSS. Spróbuj tymczasowo przełączyć się na domyślny motyw panelu administracyjnego PrestaShop, aby sprawdzić, czy problem nadal występuje. Jeśli się rozwiąże, prawdopodobnie CSS Twojego motywu nadpisuje style modułu.
-   **Kompatybilność przeglądarki:** Upewnij się, że Twoja przeglądarka jest aktualna.

**P5: Jak przetłumaczyć interfejs modułu na inny język?**
O5:

-   Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz język, na który chcesz przetłumaczyć.
-   Znajdź „Notatki samoprzylepne w Panelu administracyjnym” na liście i przetłumacz dostępne ciągi tekstowe.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Notatki samoprzylepne w Panelu administracyjnym” to klasyczny moduł PrestaShop zaprojektowany głównie dla Panelu administracyjnego. Wykorzystuje architekturę modułów PrestaShop, używając klasy `Module` do instalacji, deinstalacji i konfiguracji. Podstawowa funkcjonalność polega na wyświetlaniu i zarządzaniu tworzonymi przez użytkowników „notatkami samoprzylepnymi” w panelu administracyjnym. W dużym stopniu opiera się na JavaScript do interakcji front-end (przeciąganie, pozycjonowanie) i AJAX do zapisywania danych notatek. Trwałość danych jest obsługiwana za pomocą `ps_configuration` dla ustawień modułu i prawdopodobnie niestandardowych tabel baz danych lub `ps_configuration` dla samych notatek.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wydaje się używać dedykowanych kontrolerów Front-Office ani Back-Office Admin w tradycyjnym sensie MVC PrestaShop (tj. plików w `controllers/front/` lub `controllers/admin/`). Cała konfiguracja i obsługa AJAX wydają się być zarządzane bezpośrednio w głównym pliku modułu (`addstickynote.php`) za pomocą metody `getContent()` do konfiguracji i potencjalnie metod `ajaxProcess` lub bezpośrednich wywołań AJAX do dynamicznego zarządzania notatkami.

### 4.3 Klasy podstawowe i modele (`classes/`)

Na podstawie dostarczonego spisu, w katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Sugeruje to, że dane notatek samoprzylepnych są prawdopodobnie przechowywane bezpośrednio w tabeli `ps_configuration`, gdzie treść, kolor i pozycja każdej notatki mogą być serializowane lub przechowywane jako indywidualne klucze konfiguracyjne.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł w dużym stopniu opiera się na JavaScript w zakresie swoich interaktywnych funkcji w panelu administracyjnym.

-   `stickynotes/js/advajax.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Prawdopodobnie niestandardowy skrypt narzędziowy AJAX, być może wrapper dla funkcji AJAX jQuery lub samodzielna implementacja do obsługi asynchronicznej komunikacji z backendem PHP modułu w celu zapisywania/ładowania notatek.
-   `stickynotes/js/joverlay.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Sugeruje funkcjonalność związaną z nakładkami lub wyskakującymi oknami modalnymi, potencjalnie używanymi do edycji treści notatek w bardziej przyjaznym dla użytkownika interfejsie lub do wyświetlania komunikatów potwierdzających.
-   `stickynotes/js/jscolor/jscolor.js`:
    -   **Zakres:** Panel administracyjny (konkretnie na stronie konfiguracji modułu).
    -   **Odpowiedzialność:** Biblioteka JavaScript innej firmy do udostępniania interfejsu selektora kolorów. Służy do umożliwiania administratorom wyboru koloru tła dla ich notatek samoprzylepnych.
-   `stickynotes/js/script.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Jest to prawdopodobnie główny skrypt dla logiki front-end modułu. Obsługiwałby:
        -   Inicjalizację notatek samoprzylepnych po załadowaniu strony.
        -   Funkcjonalność przeciągania i upuszczania do zmiany pozycji notatek.
        -   Zapisywanie pozycji notatek za pomocą AJAX.
        -   Słuchacze zdarzeń do edycji/usuwania notatek.
        -   Interakcję z `advajax.js` w celu trwałości danych.
        -   Potencjalnie dynamiczne renderowanie nowych notatek.
-   `stickynotes/js/script17.js`:
    -   **Zakres:** Panel administracyjny (specyficzny dla PrestaShop 1.7.x i 8.x).
    -   **Odpowiedzialność:** Ten skrypt prawdopodobnie zawiera adaptacje lub specyficzny kod dla środowisk PrestaShop 1.7+, uwzględniający różnice w strukturze DOM, wersjach jQuery lub zmianach motywu panelu administracyjnego w porównaniu do starszych wersji PrestaShop (1.5/1.6). Zapewniłby kompatybilność i prawidłowe funkcjonowanie na nowszych platformach.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera pliki CSS do stylizacji wyglądu notatek samoprzylepnych.

-   `stickynotes/css/stickynotes-twig-shit.css`:
    -   **Zakres:** Stylizacja panelu administracyjnego.
    -   **Odpowiedzialność:** Nazwa sugeruje, że ten plik zawiera specyficzne dostosowania stylów lub nadpisania dla paneli administracyjnych PrestaShop 1.7+, które wykorzystują szablony Twig. Prawdopodobnie celuje w elementy w nowym motywie panelu administracyjnego, aby zapewnić prawidłowe i spójne wyświetlanie notatek.
    -   **Kluczowe selektory CSS:** `.sticky-note`, `.sticky-note-content`, `.sticky-note-header` (hipotetyczne, oparte na wspólnych konwencjach nazewnictwa).
-   `stickynotes/css/stickynotes.css`:
    -   **Zakres:** Stylizacja panelu administracyjnego.
    -   **Odpowiedzialność:** Jest to główny arkusz stylów dla notatek samoprzylepnych, definiujący ich domyślny wygląd, pozycjonowanie i stany interaktywne (np. podczas przeciągania). Zawierałby ogólne style mające zastosowanie w różnych wersjach PrestaShop.
    -   **Kluczowe selektory CSS:** `.sticky-note`, `.draggable`, `.resizable`, `.note-text`, `.note-controls` (hipotetyczne). Programiści mogą nadpisać te klasy w swoich niestandardowych motywach panelu administracyjnego, jeśli zajdzie taka potrzeba.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa pojedynczego szablonu Smarty do renderowania notatek samoprzylepnych w panelu administracyjnym.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `stickynotes/sticky-notes-back-office.tpl`:
        -   **Renderowane w hooku:** Ten szablon jest prawdopodobnie podłączony do globalnego hooka panelu administracyjnego, takiego jak `displayBackOfficeHeader` lub `displayAdminAfterHeader`, aby wstrzyknąć niezbędną strukturę HTML i inicjalizację JavaScript dla notatek samoprzylepnych na wszystkich stronach administracyjnych.
        -   **Wyjście bloku wizualnego:** Wyświetla kontenery HTML dla notatek samoprzylepnych, potencjalnie zawierające ukryty szablon dla nowych notatek, oraz wywołania JavaScript do inicjalizacji wyświetlania notatek i funkcji przeciągania. Zawierałby również logikę do iteracji przez istniejące notatki i ich renderowania.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:

    -   Ten moduł nie wydaje się tworzyć niestandardowych tabel SQL. Jest bardzo prawdopodobne, że wszystkie dane notatek samoprzylepnych (treść, kolor, pozycja, ID) są przechowywane w tabeli `ps_configuration`. Każda notatka może odpowiadać unikalnemu kluczowi konfiguracyjnemu `PS_STICKY_NOTE_X`, gdzie `X` jest identyfikatorem, a wartość jest serializowaną tablicą lub ciągiem JSON zawierającym właściwości notatki.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` każdej strony panelu administracyjnego. | Wstrzykuje pliki CSS i JavaScript wymagane do funkcjonalności i stylizacji notatek samoprzylepnych. |
| `displayAdminAfterHeader` (lub podobny) | Wykonywany po głównym nagłówku każdej strony panelu administracyjnego. | Renderuje strukturę HTML dla notatek samoprzylepnych i inicjalizuje ich wyświetlanie oraz interaktywne zachowanie. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (JS/CSS). | Potencjalnie używany do warunkowego ładowania zasobów JS/CSS w zależności od bieżącej strony administracyjnej, chociaż `displayBackOfficeHeader` jest bardziej powszechny dla globalnych zasobów. |
| `actionModuleInstall` | Wykonywany podczas instalacji modułu. | Tworzy początkowe wpisy konfiguracyjne w `ps_configuration` (jeśli istnieją) i rejestruje niezbędne hooki. |
| `actionModuleUninstall` | Wykonywany podczas deinstalacji modułu. | Czyści wpisy konfiguracyjne i wyrejestrowuje hooki. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i pobrania najnowszych wersji modułu „Notatki samoprzylepne w Panelu administracyjnym” odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
