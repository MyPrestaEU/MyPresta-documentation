---
title: "Darmowe recenzje produktów (komentarze) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Darmowe recenzje produktów (komentarze) od MyPresta.eu."
sidebar:
  label: "Darmowe recenzje produktów (komentarze)"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free product reviews (comments) na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/free-product-reviews-comments.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/free-product-reviews-comments/)
>
> ---


# Darmowe recenzje produktów (komentarze)

## 1. Wymagania i kompatybilność
Ten moduł został zaprojektowany z myślą o szerokiej kompatybilności z nowoczesnymi wersjami PrestaShop i standardowymi środowiskami hostingowymi.

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym kompatybilnym z PrestaShop. Nie są potrzebne żadne nietypowe ani specjalistyczne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji, kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu „Darmowe recenzje produktów (komentarze)”. Tutaj kontrolujesz, jak recenzje zachowują się i pojawiają w Twoim sklepie.

#### Ustawienia ogólne

-   **Włącz recenzje:**
    *   **Co robi to ustawienie:** Jest to główny przełącznik dla całego systemu recenzji.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Sekcja recenzji pojawi się na stronach produktów, a klienci będą mogli czytać i przesyłać recenzje.
        *   *Gdy wyłączone:* Sekcja recenzji zostanie ukryta ze stron produktów, a nowe recenzje nie będą mogły być przesyłane ani przeglądane.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz/przykład dla sprzedawcy:** Włącz to, aby rozpocząć zbieranie i wyświetlanie opinii klientów natychmiast po instalacji.

-   **Recenzje muszą być zatwierdzone przez pracownika:**
    *   **Co robi to ustawienie:** Określa, czy recenzje są publikowane automatycznie, czy wymagają ręcznego zatwierdzenia przez administratora sklepu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Wszystkie przesłane recenzje wejdą w stan „oczekujące” i nie będą widoczne w front office, dopóki administrator ręcznie ich nie zatwierdzi w sekcji zarządzania recenzjami modułu. Pozwala to na odfiltrowanie spamu, nieodpowiednich treści lub recenzji, które nie spełniają Twoich wytycznych.
        *   *Gdy wyłączone:* Recenzje są publikowane natychmiast po przesłaniu, bez interwencji człowieka.
    *   **Zalecana wartość:** TAK (zwłaszcza dla nowych sklepów lub w celu utrzymania kontroli jakości)
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz upewnić się, że wszystkie recenzje są odpowiednie i konstruktywne, zanim zostaną opublikowane, włącz to. Jest to kluczowe dla utrzymania wizerunku marki i zapobiegania spamowi.

-   **Zezwól na recenzje gości:**
    *   **Co robi to ustawienie:** Kontroluje, czy niezalogowani odwiedzający (goście) mogą przesyłać recenzje.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Każdy odwiedzający stronę produktu może przesłać recenzję, nawet jeśli nie ma konta lub nie jest zalogowany. Zazwyczaj zostanie poproszony o imię i adres e-mail.
        *   *Gdy wyłączone:* Tylko klienci zalogowani na swoje konto PrestaShop mogą przesyłać recenzje.
    *   **Zalecana wartość:** TAK (aby zachęcić do większej liczby recenzji) lub NIE (aby upewnić się, że recenzje pochodzą od rzeczywistych klientów).
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz zmaksymalizować liczbę recenzji, nawet od przypadkowych przeglądających, włącz recenzje gości. Jeśli wolisz zbierać recenzje tylko od zweryfikowanych klientów, którzy dokonali u Ciebie zakupu, wyłącz to.

-   **Minimalny czas między 2 recenzjami od tego samego użytkownika (w sekundach):**
    *   **Co robi to ustawienie:** Ustawia okres karencji, aby zapobiec przesyłaniu przez jednego użytkownika wielu recenzji w krótkim odstępie czasu dla tego samego produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawiona jest wartość (np. 3600 dla 1 godziny):* Użytkownik musi odczekać co najmniej tyle sekund po przesłaniu recenzji, zanim będzie mógł przesłać kolejną recenzję dla tego samego produktu.
        *   *Gdy ustawiona jest wartość 0:* Nie ma limitu czasu, a użytkownicy mogą przesyłać recenzje tak często, jak chcą.
    *   **Zalecana wartość:** 3600 (1 godzina) lub 86400 (24 godziny), aby zapobiec spamowaniu.
    *   **Scenariusz/przykład dla sprzedawcy:** Aby zapobiec zalewaniu produktu wieloma recenzjami przez jednego klienta, ustaw to na rozsądny czas, np. 3600 sekund (1 godzina).

-   **Wyświetl recenzje na stronie produktu:**
    *   **Co robi to ustawienie:** Określa, czy lista recenzji i formularz przesyłania są wyświetlane bezpośrednio na stronie produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Sekcja recenzji będzie widoczna na stronie produktu, umożliwiając klientom czytanie i pisanie recenzji.
        *   *Gdy wyłączone:* Sekcja recenzji zostanie ukryta ze strony produktu. Może to być używane, jeśli wolisz linkować do oddzielnej strony recenzji lub zarządzać recenzjami inaczej.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz/przykład dla sprzedawcy:** Aby recenzje były łatwo dostępne dla kupujących przeglądających Twoje produkty, pozostaw to włączone.

-   **Liczba recenzji na stronę:**
    *   **Co robi to ustawienie:** Kontroluje, ile recenzji jest wyświetlanych na jednej stronie w liście recenzji przed zastosowaniem paginacji.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawiona jest wartość (np. 5):* Wyświetlanych będzie tylko 5 recenzji naraz, z przyciskami „Następna” i „Poprzednia” lub numerami stron do nawigacji po reszcie.
        *   *Gdy ustawiona jest bardzo wysoka liczba:* Wszystkie recenzje mogą załadować się na jednej stronie, co może wpłynąć na szybkość ładowania strony, jeśli jest wiele recenzji.
    *   **Zalecana wartość:** 5-10
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli produkt ma wiele recenzji, ustawienie tego na 5 lub 10 sprawi, że strona produktu będzie uporządkowana i szybko się załaduje, jednocześnie umożliwiając klientom przeglądanie wszystkich opinii.

#### Zarządzanie kryteriami recenzji

Ta sekcja umożliwia zdefiniowanie konkretnych kryteriów (np. „Jakość”, „Cena”, „Funkcje”), które klienci mogą oceniać oprócz ogólnej oceny produktu.

-   **Dodaj nowe kryterium:**
    *   **Co to robi:** Umożliwia utworzenie nowego, specyficznego aspektu produktu, który klienci mogą oceniać (np. „Wartość za pieniądze”, „Łatwość użycia”, „Trwałość”).
    *   **Efekt zmiany tego ustawienia:** Po dodaniu kryterium pojawi się ono jako dodatkowa opcja oceny w formularzu przesyłania recenzji na stronie produktu. Klienci będą mogli przyznać ocenę gwiazdkową dla każdego zdefiniowanego kryterium.
    *   **Zalecana wartość:** Dodaj kryteria istotne dla Twoich produktów.
    *   **Scenariusz/przykład dla sprzedawcy:** W przypadku sklepu z elektroniką możesz dodać kryteria takie jak „Wydajność”, „Żywotność baterii” i „Design”. W przypadku sklepu odzieżowego „Dopasowanie”, „Jakość materiału” i „Styl”.

-   **Lista istniejących kryteriów:**
    *   **Co to robi:** Wyświetla tabelę wszystkich kryteriów, które wcześniej dodałeś, wraz z opcjami edycji lub usunięcia.
    *   **Efekt zmiany tego ustawienia:** Możesz zmodyfikować nazwę kryterium (np. zmienić „Jakość” na „Jakość produktu”) lub usunąć kryterium, jeśli nie jest już istotne. Usunięcie kryterium usunie je z przyszłych zgłoszeń recenzji, ale istniejące recenzje, które używały tego kryterium, mogą nadal wyświetlać swoje oceny dla niego (w zależności od implementacji modułu).
    *   **Zalecana wartość:** Utrzymuj listę kryteriów aktualną i istotną.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli wprowadzasz nową linię produktów o unikalnych cechach, możesz dodać nowe kryterium. Jeśli kryterium staje się zbędne, możesz je usunąć.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Włącz recenzje | TAK | Główny przełącznik dla systemu recenzji. |
| Konfiguracja modułu | Recenzje muszą być zatwierdzone przez pracownika | TAK | Kontroluje ręczne zatwierdzanie recenzji, aby zapobiec spamowi/nieodpowiednim treściom. |
| Konfiguracja modułu | Zezwól na recenzje gości | TAK | Umożliwia niezalogowanym użytkownikom przesyłanie recenzji. |
| Konfiguracja modułu | Minimalny czas między 2 recenzjami od tego samego użytkownika (w sekundach) | 3600 (1 godzina) | Zapobiega spamowaniu recenzjami przez jednego użytkownika. |
| Konfiguracja modułu | Wyświetl recenzje na stronie produktu | TAK | Pokazuje lub ukrywa sekcję recenzji na stronach produktów. |
| Konfiguracja modułu | Liczba recenzji na stronę | 5-10 | Kontroluje paginację dla listy recenzji na stronach produktów. |
| Konfiguracja modułu | Dodaj nowe kryterium | N/A | Tworzy specyficzne aspekty oceny (np. „Jakość”, „Cena”). |
| Konfiguracja modułu | Lista istniejących kryteriów | N/A | Zarządza (edytuje/usuwa) niestandardowymi kryteriami recenzji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje recenzje nie pojawiają się na stronie produktu po przesłaniu.**
O: Sprawdź, czy w konfiguracji modułu włączona jest opcja „Recenzje muszą być zatwierdzone przez pracownika”. Jeśli tak, musisz je ręcznie zatwierdzić w interfejsie administracyjnym modułu (zazwyczaj znajduje się na stronie konfiguracji modułu, gdzie zobaczysz listę recenzji). Po zatwierdzeniu pojawią się w front office.

**P2: Sekcja recenzji wygląda dziwnie lub nie pasuje do projektu mojego motywu.**
O: Jest to często konflikt CSS z Twoim niestandardowym motywem PrestaShop.
    *   **Wyczyść pamięć podręczną:** Najpierw spróbuj wyczyścić pamięć podręczną PrestaShop w **Zaawansowane > Wydajność**.
    *   **Nadpisania motywu:** Twój motyw może mieć własne style dla elementów recenzji lub może brakować mu specyficznych stylów dla tego modułu. Może być konieczne, aby webmaster sprawdził CSS i zastosował niestandardowe style, aby wszystko płynnie się komponowało. Moduł dostarcza własne pliki CSS (`myprestacomments.css` itp.), ale style Twojego motywu mogą je nadpisywać.

**P3: Klienci skarżą się, że nie mogą przesyłać recenzji lub formularz się nie pojawia.**
O:
    *   **Sprawdź „Włącz recenzje”:** Upewnij się, że główny przełącznik w konfiguracji modułu jest ustawiony na TAK.
    *   **Sprawdź „Wyświetl recenzje na stronie produktu”:** Upewnij się, że ta opcja jest również włączona.
    *   **Recenzje gości:** Jeśli niezalogowani użytkownicy nie mogą przesyłać, sprawdź „Zezwól na recenzje gości”. Jeśli jest wyłączone, tylko zalogowani klienci mogą przesyłać.
    *   **Minimalny czas między recenzjami:** Jeśli konkretny użytkownik nie może przesłać, może osiągnąć limit „Minimalny czas między 2 recenzjami”.

**P4: Jak przetłumaczyć tekst modułu na inne języki?**
O: Możesz przetłumaczyć tekst modułu bezpośrednio w PrestaShop:
    1.  Przejdź do **Lokalizacja > Tłumaczenia**.
    2.  Wybierz „Tłumaczenia zainstalowanych modułów” dla „Typu tłumaczenia”.
    3.  Wybierz swój motyw.
    4.  Wybierz język, na który chcesz przetłumaczyć.
    5.  Znajdź „Darmowe recenzje produktów (komentarze)” na liście modułów i kliknij „Modyfikuj”. Następnie możesz edytować wszystkie przetłumaczalne ciągi znaków.

**P5: Chcę usunąć recenzję, która jest nieodpowiednia lub spamem.**
O: Przejdź do strony konfiguracji modułu w Panelu administracyjnym. Powinieneś zobaczyć listę wszystkich przesłanych recenzji. Stamtąd możesz zazwyczaj „Usunąć” lub „Odrzucić” recenzje. Jeśli masz włączoną opcję „Recenzje muszą być zatwierdzone przez pracownika”, możesz po prostu zdecydować się jej nie zatwierdzać.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury
Moduł „Darmowe recenzje produktów (komentarze)” (`myprestacomments`) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując `ModuleFrontController` do interakcji z front-office i `Module` do głównej konfiguracji i zarządzania hookami. Wykorzystuje niestandardową tabelę bazy danych do przechowywania danych recenzji i opiera się na szablonach Smarty do renderowania zarówno wyświetlania recenzji w front-office, jak i formularzy konfiguracji w back-office. Moduł integruje się z systemem hooków PrestaShop, aby wstrzykiwać swoją zawartość na strony produktów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    *   `controllers/front/default.php`
        *   **Nazwa klasy i klasa nadrzędna**: `MyPrestaCommentsDefaultModuleFrontController` rozszerzający `ModuleFrontController`
        *   **Odpowiedzialność**: Ten kontroler prawdopodobnie obsługuje początkowe wyświetlanie recenzji na stronie produktu lub służy jako rezerwowy dla ogólnych działań związanych z recenzjami. Zazwyczaj pobiera recenzje dla danego produktu i przekazuje je do szablonu Smarty.
    *   `controllers/front/feedback.php`
        *   **Nazwa klasy i klasa nadrzędna**: `MyPrestaCommentsFeedbackModuleFrontController` rozszerzający `ModuleFrontController`
        *   **Odpowiedzialność**: Ten kontroler jest przeznaczony do obsługi przesyłania nowych recenzji. Przetwarza żądania POST z formularza recenzji, waliduje dane wejściowe (ocena, komentarz, kryteria), sprawdza uprawnienia do recenzji gości i limity czasowe, a następnie zapisuje recenzję do bazy danych. Zarządza również statusem zatwierdzenia na podstawie konfiguracji modułu.
    *   `controllers/front/index.php`
        *   **Nazwa klasy i klasa nadrzędna**: `MyPrestaCommentsIndexModuleFrontController` rozszerzający `ModuleFrontController`
        *   **Odpowiedzialność**: Ten kontroler może służyć jako ogólny punkt wejścia lub obsługiwać żądania AJAX związane z recenzjami, takie jak ładowanie większej liczby recenzji za pomocą paginacji lub obsługa funkcji „zgłoś nadużycie”.

-   **Kontrolery administracyjne Back-Office**:
    *   Nie ma wymienionych dedykowanych niestandardowych kontrolerów administracyjnych (`controllers/admin/`). Sugeruje to, że administracja recenzjami (listowanie, zatwierdzanie, usuwanie) jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu (`index.php`) lub za pośrednictwem standardowego `AdminController`, który moduł rozszerza lub z którym się integruje. Obecność szablonów `list_action_approve.tpl` i `list_action_noabuse.tpl` silnie wskazuje, że zarządzanie recenzjami jest zintegrowane ze standardowym widokiem listy PrestaShop, prawdopodobnie na stronie konfiguracji modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)
W katalogu `classes/` nie ma wymienionych niestandardowych klas. Oznacza to, że moduł może używać bardziej bezpośredniego podejścia do interakcji z bazą danych w swoim głównym pliku modułu lub kontrolerach, lub może wykorzystywać istniejące `ObjectModel` PrestaShop, jeśli ma to zastosowanie (choć mało prawdopodobne w przypadku niestandardowych danych recenzji). Prawdopodobnie struktura danych recenzji jest zarządzana bezpośrednio w `install.sql` i `index.php` modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `js/jquery.rating.pack.js`
    *   **Zakres**: Front-office
    *   **Opis**: Wtyczka jQuery do tworzenia interaktywnych widżetów ocen gwiazdkowych. Obsługuje wizualne wyświetlanie gwiazdek i przechwytuje wybór oceny użytkownika w formularzu przesyłania recenzji.
-   `js/jquery.textareaCounter.plugin.js`
    *   **Zakres**: Front-office
    *   **Opis**: Wtyczka jQuery do liczenia znaków lub słów w polu tekstowym, często używana do dostarczania użytkownikom informacji zwrotnych w czasie rzeczywistym na temat długości ich recenzji.
-   `js/moderate.js`
    *   **Zakres**: Back-office
    *   **Opis**: Ten skrypt prawdopodobnie obsługuje działania AJAX do moderowania recenzji w Back Office. Byłby odpowiedzialny za zatwierdzanie, odrzucanie lub usuwanie recenzji bez pełnego przeładowania strony, wchodząc w interakcję z `getContent()` modułu lub ukrytym kontrolerem administracyjnym.
-   `js/myprestacomments.js`
    *   **Zakres**: Front-office
    *   **Opis**: Główny niestandardowy JavaScript dla modułu. Koordynuje funkcjonalność recenzji w front-office, w tym:
        *   Inicjalizację `jquery.rating.pack.js` dla ocen gwiazdkowych.
        *   Obsługę przesyłania formularza recenzji (potencjalnie za pośrednictwem AJAX).
        *   Wyświetlanie komunikatów o sukcesie lub błędach.
        *   Zarządzanie paginacją lub funkcją „załadowania więcej” dla recenzji.
        *   Potencjalnie obsługę kliknięć „zgłoś nadużycie”.
-   `js/productCriterion.js`
    *   **Zakres**: Back-office
    *   **Opis**: Ten skrypt jest używany w Back Office do zarządzania kryteriami recenzji. Prawdopodobnie obsługuje dynamiczne dodawanie, edytowanie i usuwanie pól kryteriów na stronie konfiguracji modułu, być może za pomocą AJAX do aktualizacji bazy danych.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `myprestacomments.css`
    *   **Zakres**: Front-office i Back-office
    *   **Opis**: Główny arkusz stylów dla modułu, zawierający ogólne style dla sekcji recenzji, ocen gwiazdkowych, formularzy recenzji i potencjalnie podstawowe style panelu administracyjnego.
    *   **Kluczowe selektory**: `.myprestacomments_block`, `.myprestacomments_review_list`, `.myprestacomments_form`, `.star_content`, `.comment_item`, `.review_rating`.
-   `myprestacomments16.css`
    *   **Zakres**: Front-office i Back-office
    *   **Opis**: Prawdopodobnie arkusz stylów kompatybilności dla PrestaShop 1.6.x, zawierający specyficzne nadpisania lub dostosowania dla domyślnej struktury motywu tej wersji.
-   `myprestacomments24.css`
    *   **Zakres**: Front-office i Back-office
    *   **Opis**: Prawdopodobnie arkusz stylów kompatybilności dla PrestaShop 1.7.x lub 8.x, zawierający specyficzne nadpisania lub dostosowania dla domyślnej struktury motywu tych wersji (np. motyw Classic).
-   `myprestacomments32.css`
    *   **Zakres**: Front-office i Back-office
    *   **Opis**: Prawdopodobnie arkusz stylów kompatybilności dla PrestaShop 9.x, zawierający specyficzne nadpisania lub dostosowania dla najnowszej domyślnej struktury motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `myprestacomments/mypresta_myprestacomments.tpl`
        *   **Hook**: Prawdopodobnie `displayProductButtons` lub `displayProductExtraContent` (lub podobne hooki strony produktu).
        *   **Wyjście**: Jest to główny szablon do wyświetlania podsumowania recenzji (średnia ocena, liczba recenzji) oraz przycisku/linku „Napisz recenzję” na stronie produktu. Często działa jako opakowanie dla pełnej listy recenzji i formularza.
    *   `myprestacomments/mypresta_myprestacomments_reviews_list.tpl`
        *   **Hook**: Renderowany w `mypresta_myprestacomments.tpl` lub bezpośrednio podłączony, jeśli moduł używa oddzielnej zakładki.
        *   **Wyjście**: Wyświetla rzeczywistą listę indywidualnych recenzji klientów, w tym ich oceny, tytuły, komentarze i informacje o recenzencie. Będzie również obsługiwać paginację.

-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `myprestacomments/views/templates/admin/advert.tpl`
        *   **Wyjście**: Prawdopodobnie wyświetla reklamę lub wiadomość promocyjną od MyPresta.eu na stronie konfiguracji modułu.
    *   `myprestacomments/views/templates/admin/list_action_approve.tpl`
        *   **Wyjście**: Fragment szablonu dla przycisku lub linku akcji „Zatwierdź”, używany w liście oczekujących recenzji w Back Office.
    *   `myprestacomments/views/templates/admin/list_action_noabuse.tpl`
        *   **Wyjście**: Fragment szablonu dla przycisku lub linku akcji „Oznacz jako nieobraźliwe”, używany w liście zgłoszonych recenzji w Back Office.
    *   `myprestacomments/views/templates/admin/_configure/helpers/form/form.tpl`
        *   **Wyjście**: Jest to standardowe nadpisanie szablonu pomocniczego PrestaShop, używane do renderowania formularza konfiguracji modułu (ustawienia ogólne, zarządzanie kryteriami) w Back Office. Definiuje układ i pola wejściowe dla metody `getContent()`.
    *   `myprestacomments/views/templates/admin/_configure/helpers/list/list_content.tpl`
        *   **Wyjście**: Kolejne standardowe nadpisanie szablonu pomocniczego PrestaShop, używane do renderowania listy recenzji (lub kryteriów) w Back Office, w tym kolumn dla szczegółów recenzji, statusu i przycisków akcji (zatwierdź, usuń).

-   **Szablony front-office (`views/templates/front/`)**:
    *   `myprestacomments/views/templates/front/feedback.tpl`
        *   **Wyjście**: Szablon samego formularza przesyłania recenzji. Obejmuje to pole wprowadzania oceny gwiazdkowej, pola tekstowe na tytuł i komentarz oraz potencjalnie pola na niestandardowe oceny kryteriów. Jest renderowany, gdy klient kliknie „Napisz recenzję”.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   `myprestacomments/install.sql`: Ten plik zawiera instrukcje SQL wykonywane podczas instalacji modułu. Zdefiniuje co najmniej jedną niestandardową tabelę:
        *   `ps_myprestacomments_reviews`: Przechowuje rzeczywiste dane recenzji (ID produktu, ID klienta, ocena, tytuł, komentarz, data, status zatwierdzenia, status nadużycia).
        *   `ps_myprestacomments_criteria`: Przechowuje niestandardowe kryteria recenzji zdefiniowane przez sprzedawcę (np. „Jakość”, „Cena”).
        *   `ps_myprestacomments_review_criterion`: Tabela łącząca, jeśli recenzje mogą oceniać wiele kryteriów.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony. | Aby globalnie lub warunkowo dołączyć pliki CSS i JS modułu. |
| `displayProductExtraContent` | Na stronie produktu, zazwyczaj poniżej głównego opisu produktu lub w zakładce. | Aby wyświetlić podsumowanie recenzji, listę recenzji i formularz „Napisz recenzję”. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku „Dodaj do koszyka”. | Aby wyświetlić szybki link lub przycisk do sekcji recenzji. |
| `displayFooter` | W stopce każdej strony. | Mniej powszechne, ale może być używane do ogólnego linku do recenzji lub treści specyficznych dla modułu. |
| `displayLeftColumn` / `displayRightColumn` | W lewej lub prawej kolumnie bocznej. | Może być używane do wyświetlania bloku ostatnich recenzji lub podsumowania recenzji. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Potencjalnie używane do wywołania e-maila do klienta z prośbą o recenzję zakupionych produktów. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Back Office. | Aby w razie potrzeby wyczyścić pamięć podręczną związaną z recenzjami produktów. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Po dodaniu lub zaktualizowaniu produktu. | Aby zapewnić integralność danych recenzji lub unieważnienie pamięci podręcznej. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „Darmowe recenzje produktów (komentarze)” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w rozwiązywaniu problemów związanych z modułem i zapewnić płynne działanie Twojego sklepu.
"""
