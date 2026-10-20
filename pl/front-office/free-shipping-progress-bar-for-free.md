---
title: "Pasek postępu darmowej wysyłki za darmo - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Pasek postępu darmowej wysyłki za darmo” od MyPresta.eu."
sidebar:
  label: "Pasek postępu darmowej wysyłki za darmo - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free Shipping Progress Bar for free na MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-for-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/free-shipping-progress-bar-for-free/)
>
> ---


# Pasek postępu darmowej wysyłki za darmo

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Pasek postępu darmowej wysyłki za darmo”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok nazwy modułu.

#### Ustawienia ogólne

-   **Włącz pasek postępu darmowej wysyłki:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcjonalności paska postępu dla Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Pasek postępu pojawi się w wybranych pozycjach w Twoim front office, a wszystkie inne ustawienia modułu zaczną obowiązywać.
        -   *Gdy wyłączone (NIE):* Pasek postępu zostanie całkowicie ukryty w Twoim sklepie, niezależnie od innych ustawień.
    -   **Zalecana wartość:** TAK (aby korzystać z funkcji modułu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli tymczasowo prowadzisz inną promocję lub wykonujesz konserwację, możesz go wyłączyć. W przeciwnym razie pozostaw go włączonym, aby zachęcać do sprzedaży.
-   **Próg darmowej wysyłki:**

    -   **Co robi to ustawienie:** Definiuje dokładną kwotę (w domyślnej walucie Twojego sklepu), którą klient musi wydać, aby zakwalifikować się do darmowej wysyłki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretną kwotę (np. 50.00):* Pasek postępu obliczy pozostałą kwotę na podstawie tego progu.
        -   *Gdy zmienione:* Cel darmowej wysyłki aktualizuje się natychmiast dla wszystkich klientów.
    -   **Zalecana wartość:** Ustaw to na rzeczywisty próg darmowej wysyłki w Twoim sklepie. Jeśli oferujesz darmową wysyłkę powyżej 50 €, ustaw na 50.00.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój przewoźnik oferuje darmową wysyłkę dla zamówień powyżej 75 €, ustaw to na 75.00.
-   **Hak wyświetlania (Display Hook):**

    -   **Co robi to ustawienie:** Określa, gdzie na Twojej stronie internetowej zostanie wyświetlony pasek postępu darmowej wysyłki. Możesz wybrać spośród kilku typowych lokalizacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na ‘displayHeader’:* Pasek pojawi się w górnej sekcji Twojej strony internetowej, zazwyczaj powyżej lub poniżej Twojego logo/menu.
        -   *Gdy ustawione na ‘displayLeftColumn’ lub ‘displayRightColumn’:* Pasek pojawi się w odpowiedniej bocznej kolumnie Twojego sklepu.
        -   *Gdy ustawione na ‘displayFooter’:* Pasek pojawi się na dole Twojej strony internetowej.
        -   *Gdy ustawione na ‘displayProductButtons’ (lub podobny hak strony produktu):* Pasek pojawi się na stronach produktów, często w pobliżu przycisku dodaj do koszyka.
    -   **Zalecana wartość:** ‘displayHeader’ lub ‘displayProductButtons’ są często najbardziej efektywne dla widoczności i zachęcania do natychmiastowego działania.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zapewnić maksymalną widoczność, możesz wybrać `displayHeader`. Jeśli chcesz zachęcić do dodawania większej liczby produktów bezpośrednio ze strony produktu, `displayProductButtons` jest dobrym wyborem.
-   **Kolor paska postępu:**

    -   **Co robi to ustawienie:** Pozwala dostosować kolor samego paska postępu. Pomaga to dopasować go do brandingu Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretny kolor (np. #4CAF50 dla zielonego):* Pasek wyświetli się w tym kolorze.
    -   **Zalecana wartość:** Kolor, który dobrze kontrastuje z tłem, ale uzupełnia paletę kolorów Twojej marki.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja marka używa dużo niebieskiego, możesz wybrać odcień niebieskiego lub uzupełniający pomarańcz, aby pasek wyróżniał się.
-   **Kolor tła:**

    -   **Co robi to ustawienie:** Pozwala dostosować kolor tła kontenera paska postępu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretny kolor (np. #F0F0F0 dla jasnoszarego):* Tło za postępem wyświetli się w tym kolorze.
    -   **Zalecana wartość:** Subtelny kolor, który zapewnia dobry kontrast z kolorem paska postępu, często jasnoszary lub biały.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby sam pasek postępu wyróżniał się, możesz użyć jasnego koloru tła, takiego jak biały lub bardzo jasnoszary.
-   **Kolor tekstu:**

    -   **Co robi to ustawienie:** Pozwala dostosować kolor tekstu wyświetlanego wewnątrz lub wokół paska postępu (np. „Brakuje Ci X do darmowej wysyłki!”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretny kolor (np. #333333 dla ciemnoszarego):* Tekst wyświetli się w tym kolorze.
    -   **Zalecana wartość:** Kolor, który jest łatwo czytelny zarówno na tle paska postępu, jak i jego tła.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój pasek postępu jest zielony, a jego tło jasnoszare, ciemnoszary lub czarny kolor tekstu zapewni czytelność.

#### Zapowiedź wersji Pro

Ta sekcja zazwyczaj zawiera informacje i linki do uaktualnienia do wersji „Pro” modułu, która oferuje bardziej zaawansowane funkcje. Nie są to ustawienia konfiguracyjne dla darmowego modułu, lecz treści promocyjne.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz pasek postępu darmowej wysyłki | TAK | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | Próg darmowej wysyłki | Kwota darmowej wysyłki w Twoim sklepie | Definiuje docelową kwotę dla darmowej wysyłki. |
| Konfiguracja modułu | Hak wyświetlania | displayHeader / displayProductButtons | Określa, gdzie pasek pojawia się w Twoim sklepie. |
| Konfiguracja modułu | Kolor paska postępu | Konfigurowalny (np. #4CAF50) | Ustawia kolor wypełnionej części paska postępu. |
| Konfiguracja modułu | Kolor tła | Konfigurowalny (np. #F0F0F0) | Ustawia kolor tła kontenera paska postępu. |
| Konfiguracja modułu | Kolor tekstu | Konfigurowalny (np. #333333) | Ustawia kolor tekstu wyświetlanego z paskiem. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Pasek postępu nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O1:

-   **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Pasek postępu darmowej wysyłki za darmo” jest zainstalowany i włączony.
-   **Sprawdź konfigurację:** Przejdź do strony konfiguracji modułu. Upewnij się, że „Włącz pasek postępu darmowej wysyłki” jest ustawione na TAK. Sprawdź również, czy ustawienie „Hak wyświetlania” jest poprawnie wybrane i czy Twój szablon faktycznie renderuje ten hak (niektóre niestandardowe szablony mogą tego nie robić).
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”). Czasami stara pamięć podręczna uniemożliwia wyświetlanie nowej zawartości modułu.
-   **Kompatybilność z szablonem:** Chociaż moduł jest zaprojektowany dla standardowych szablonów PrestaShop (Classic, Hummingbird), wysoce spersonalizowane szablony mogą wymagać drobnych korekt. Jeśli powyższe kroki nie działają, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Pasek postępu wyświetla się, ale nie aktualizuje się, gdy dodaję produkty do koszyka.**
O2:

-   **Sprawdź JavaScript:** Upewnij się, że na Twojej stronie nie ma błędów JavaScript, które mogłyby uniemożliwiać działanie skryptu modułu. Możesz sprawdzić konsolę programisty w przeglądarce (zazwyczaj F12) pod kątem błędów.
-   **Koszyk AJAX:** Moduł opiera się na funkcjonalności koszyka AJAX PrestaShop. Upewnij się, że mechanizm aktualizacji koszyka w Twoim szablonie jest standardowy i nie nadpisuje podstawowych wywołań AJAX PrestaShop w sposób, który uniemożliwia modułowi wykrywanie zmian.
-   **Konflikty modułów:** Tymczasowo wyłącz inne moduły, które modyfikują zachowanie koszyka lub wyświetlają elementy w tych samych hakach, aby sprawdzić, czy nie ma konfliktów.

**P3: Jak zmienić tekst wyświetlany na pasku postępu (np. „Brakuje Ci X do darmowej wysyłki!”)?**
O3: Darmowa wersja modułu zazwyczaj używa predefiniowanego tekstu. Aby dostosować ten tekst, zazwyczaj musiałbyś edytować plik szablonu modułu (`progress.tpl`). Wymaga to jednak podstawowej znajomości szablonów Smarty. Aby w bardziej przyjazny dla użytkownika sposób dostosować tekst, wersja Pro modułu często zawiera dedykowane pola tekstowe w panelu administracyjnym.

**P4: Pasek postępu wygląda dziwnie lub nie pasuje do stylistyki mojego szablonu.**
O4:

-   **Kolory konfiguracji modułu:** Najpierw użyj ustawień „Kolor paska postępu”, „Kolor tła” i „Kolor tekstu” w konfiguracji modułu, aby spróbować dopasować go do swojego szablonu.
-   **Konflikty CSS:** CSS Twojego szablonu może nadpisywać domyślne style modułu. Webmaster może zbadać element za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować sprzeczne reguły CSS i dodać niestandardowy CSS do Twojego szablonu, aby je nadpisać. Pliki CSS modułu (`front.css`) mogą być dobrym punktem wyjścia do identyfikacji selektorów do celowania.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Pasek postępu darmowej wysyłki za darmo” stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie klasę `Module` do instalacji, deinstalacji i konfiguracji. Wykorzystuje kontrolery front-end do interakcji AJAX w celu dynamicznej aktualizacji paska postępu bez pełnego przeładowania strony. Moduł integruje się z systemem haków PrestaShop, aby wyświetlać swoją zawartość w różnych miejscach front-office i używa szablonów Smarty do renderowania swojego interfejsu użytkownika. Konfiguracja jest przechowywana w tabeli `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery front-office**:

    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna:** `SmartFreeShippingFreeIndexModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako podstawa lub punkt wejścia dla interakcji front-office, chociaż jego specyficzne metody mogą być minimalne, jeśli `refresh.php` obsługuje główny AJAX. Może być używany do początkowego ładowania danych lub ustawiania kontekstu.
    -   `controllers/front/refresh.php`
        -   **Nazwa klasy i klasa nadrzędna:** `SmartFreeShippingFreeRefreshModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność:** Jest to główny kontroler AJAX. Odpowiada na żądania (prawdopodobnie POST lub GET) z JavaScriptu front-office, aby pobrać aktualną sumę koszyka, obliczyć pozostałą kwotę do darmowej wysyłki i zwrócić zaktualizowany kod HTML lub dane paska postępu. Obsługuje konwersję walut i zapewnia, że pasek postępu odzwierciedla zmiany w koszyku w czasie rzeczywistym.
-   **Kontrolery administracyjne back-office**:

    -   Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   Brak. Moduł nie definiuje niestandardowych klas `ObjectModel` ani złożonych klas logiki biznesowej poza tym, co znajduje się w głównym pliku modułu (`index.php`) i kontrolerach front-end.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/front.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Ten skrypt odpowiada za dynamiczne zachowanie paska postępu.
        -   Prawdopodobnie wiąże słuchaczy zdarzeń z wydarzeniami aktualizacji koszyka (np. `prestashop.on('updateCart', ...)` lub niestandardowymi zdarzeniami wyzwalanymi przez koszyk AJAX szablonu).
        -   Po wykryciu aktualizacji koszyka, wykonuje wywołanie AJAX do kontrolera front-end `refresh.php`, aby uzyskać zaktualizowany status paska postępu.
        -   Następnie aktualizuje DOM, aby odzwierciedlić nowy postęp (np. szerokość paska postępu, tekst pozostałej kwoty).
        -   Może zawierać logikę dla początkowego renderowania po załadowaniu strony i obsługi różnych haków wyświetlania.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `views/css/admin-config.css`

    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Szczegóły:** Zawiera style specyficzne dla strony konfiguracji modułu w panelu administracyjnym PrestaShop, zapewniając przejrzysty i przyjazny dla użytkownika układ ustawień.
    -   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w elementy w formularzu konfiguracji modułu, takie jak `.panel`, `.form-group`, `.control-label` itp., specyficzne dla struktury HTML modułu.
-   `views/css/admin-pro-teaser.css`

    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Szczegóły:** Style dla treści promocyjnych związanych z wersją „Pro” modułu, zapewniające atrakcyjny i wyróżniający się wygląd na stronie konfiguracji.
    -   **Kluczowe selektory klas CSS:** Celuje w elementy takie jak `.pro-teaser-block`, `.pro-feature-list` itp.
-   `views/css/front.css`

    -   **Zakres:** Stylizacja klienta front-office.
    -   **Szczegóły:** Zawiera podstawowy CSS dla samego paska postępu darmowej wysyłki, w tym jego układ, kolory, animacje i responsywność.
    -   **Kluczowe selektory klas CSS:** Celuje w elementy takie jak `#smartfreeshippingfree-progress-bar-container`, `.progress-bar-fill`, `.progress-bar-text` itp. Programiści mogą nadpisać te klasy w pliku `custom.css` lub `theme.css` swojego szablonu, aby dopasować je do swojego konkretnego projektu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `views/templates/admin/configure.tpl`
        -   **Cel:** Jest to główny szablon Smarty dla strony konfiguracji modułu w Panelu administracyjnym. Renderuje pola formularza, przełączniki i elementy wejściowe dla wszystkich ustawień modułu. Prawdopodobnie zawiera `get-pro-hero.tpl` i `get-pro.tpl` dla treści promocyjnych.
    -   `views/templates/admin/get-pro-hero.tpl`
        -   **Cel:** Renderuje widoczną sekcję „hero” promującą wersję Pro modułu, często na górze strony konfiguracji.
    -   `views/templates/admin/get-pro.tpl`
        -   **Cel:** Renderuje szczegółową sekcję przedstawiającą funkcje i korzyści z uaktualnienia do wersji Pro, zazwyczaj zawierającą wezwanie do działania.
-   **Szablony haków (`views/templates/hook/`)**:

    -   `views/templates/hook/progress.tpl`
        -   **Cel:** Jest to główny szablon front-office. Renderuje strukturę HTML paska postępu darmowej wysyłki, w tym kontener, wypełnioną sekcję postępu i dynamiczny tekst (np. „Brakuje Ci X do darmowej wysyłki!”). Ten szablon jest renderowany przez metodę `displayHook` głównego pliku modułu.
-   **Szablony front-office (`views/templates/front/`)**:

    -   Brak. Wyświetlanie front-office jest obsługiwane za pośrednictwem `hook/progress.tpl`.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`, używając kluczy z prefiksem `SMARTFREESHIPPINGFREE_` (np. `SMARTFREESHIPPINGFREE_ENABLED`, `SMARTFREESHIPPINGFREE_THRESHOLD`).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony lub na samym początku `<body>`. | Służy do wstrzykiwania zasobów CSS/JS i potencjalnie renderowania paska postępu w nagłówku. |
| `displayLeftColumn` | W lewej kolumnie szablonu. | Alternatywna pozycja do wyświetlania paska postępu. |
| `displayRightColumn` | W prawej kolumnie szablonu. | Alternatywna pozycja do wyświetlania paska postępu. |
| `displayFooter` | W sekcji stopki szablonu. | Alternatywna, mniej inwazyjna pozycja do wyświetlania paska postępu. |
| `displayProductButtons` (lub podobny) | Na stronie produktu, często w pobliżu przycisku dodaj do koszyka. | Specyficzne umiejscowienie, aby zachęcić do dodawania produktów bezpośrednio ze stron produktów. |
| `actionCartSave` | Po zapisaniu koszyka (np. dodaniu/usunięciu produktu). | Hak wewnętrzny (nie do wyświetlania) używany przez moduł do wyzwalania aktualizacji AJAX dla paska postępu. |
| `actionFrontControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler front-end, w celu dodania CSS/JS. | Służy do rejestrowania `front.js` i `front.css` dla stron front-office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Pasek postępu darmowej wysyłki za darmo”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
