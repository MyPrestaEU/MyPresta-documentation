---
title: "PopUp Login Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PopUp Login Pro PrestaShop od MyPresta.eu."
sidebar:
  label: "PopUp Login Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł PopUp Login Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-login-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/popup-login-pro/)
>
> ---


# PopUp Login Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla sklepu PrestaShop, a ten moduł nie ma żadnych nietypowych wymagań poza tymi.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > PopUp Login Pro)

To jest główny ekran konfiguracji modułu PopUp Login Pro. Tutaj możesz dostosować wygląd i zachowanie pop-upu w swoim sklepie.

#### Ustawienia ogólne

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz/przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Włącz logowanie PopUp** | Ten przełącznik kontroluje, czy funkcja logowania pop-up jest aktywna w Twoim sklepie. | *Po włączeniu:* Moduł będzie przechwytywał kliknięcia w linki logowania i wyświetlał pop-up. *Po wyłączeniu:* Twój sklep powróci do domyślnych przekierowań na stronę logowania PrestaShop. | TAK | Chcesz używać funkcji logowania pop-up. |
| **Typ formularza PopUp** | Ta opcja pozwala wybrać spośród kilku wstępnie zaprojektowanych stylów wizualnych dla formularza logowania pop-up. | *Po ustawieniu na Opcja A:* Pop-up wyświetli się z projektem Opcji A. *Po ustawieniu na Opcja B:* Pop-up wyświetli się z projektem Opcji B. Każda opcja oferuje odrębny wygląd i styl. | Wybierz ten, który najlepiej pasuje do projektu Twojego sklepu. | Chcesz minimalistyczny formularz logowania (Opcja 1) lub bardziej angażujący wizualnie z obrazem (Opcja 3). |
| **Szerokość PopUp (piksele)** | Definiuje szerokość okna pop-up w pikselach. | *Po ustawieniu na 400px:* Pop-up będzie miał 400 pikseli szerokości. *Po ustawieniu na 600px:* Pop-up będzie miał 600 pikseli szerokości. Mniejsza szerokość może wyglądać lepiej na urządzeniach mobilnych, podczas gdy większa może pomieścić więcej treści lub konkretny projekt. | 400-500px (dostosuj w zależności od wybranego typu formularza) | Wybrany typ formularza wygląda ciasno przy 400px, więc zwiększasz go do 500px dla lepszej czytelności. |
| **Wysokość PopUp (piksele)** | Definiuje wysokość okna pop-up w pikselach. | *Po ustawieniu na 300px:* Pop-up będzie miał 300 pikseli wysokości. *Po ustawieniu na 500px:* Pop-up będzie miał 500 pikseli wysokości. Upewnij się, że jest wystarczająco wysoki, aby wyświetlić wszystkie pola formularza bez przewijania. | 300-450px (dostosuj w zależności od wybranego typu formularza) | Wybrany typ formularza ma wiele pól, a przy 300px klienci muszą przewijać. Zwiększasz go do 450px, aby wyświetlić wszystko. |
| **Kolor tła PopUp** | Ustawia kolor tła okna pop-up. Zazwyczaj możesz użyć próbnika kolorów lub wprowadzić szesnastkowy kod koloru (np. #FFFFFF dla białego). | *Po ustawieniu na #FFFFFF:* Tło pop-upu będzie białe. *Po ustawieniu na #F0F0F0:* Tło pop-upu będzie jasnoszare. Pomaga to dopasować pop-up do schematu kolorów Twojego sklepu. | #FFFFFF (Biały) lub kolor, który uzupełnia Twój szablon. | Twój sklep używa ciemnego szablonu, więc ustawiasz tło na ciemnoszary (#333333) dla spójności. |
| **Kolor ramki PopUp** | Ustawia kolor ramki wokół okna pop-up. | *Po ustawieniu na #CCCCCC:* Ramka pop-upu będzie jasnoszara. *Po ustawieniu na transparentny:* Nie będzie wyświetlana widoczna ramka. | #CCCCCC (Jasnoszary) lub transparentny | Chcesz subtelnej ramki, aby zdefiniować pop-up, więc wybierasz jasnoszary. |
| **Promień ramki PopUp (piksele)** | Kontroluje zaokrąglenie rogów okna pop-up. Wartość 0 oznacza ostre rogi, wyższe wartości tworzą bardziej zaokrąglone rogi. | *Po ustawieniu na 0:* Pop-up będzie miał ostre, kwadratowe rogi. *Po ustawieniu na 10:* Pop-up będzie miał lekko zaokrąglone rogi. | 5-10px | Wolisz bardziej miękki, nowoczesny wygląd, więc ustawiasz promień ramki na 8px. |
| **Kolor tła nakładki** | Ustawia kolor przyciemnionego tła, które pojawia się za pop-upem. Pomaga to skupić uwagę na pop-upie. | *Po ustawieniu na #000000:* Nakładka będzie czarna. *Po ustawieniu na #FFFFFF:* Nakładka będzie biała. | #000000 (Czarny) | Chcesz ciemnej, przezroczystej nakładki, aby wyraźnie oddzielić pop-up od głównej treści. |
| **Przezroczystość nakładki (0-1)** | Kontroluje przezroczystość tła nakładki. 0 to całkowita przezroczystość, 1 to całkowita nieprzezroczystość. | *Po ustawieniu na 0.5:* Nakładka będzie w 50% przezroczysta. *Po ustawieniu na 0.8:* Nakładka będzie w 80% nieprzezroczysta. | 0.7-0.8 | Chcesz, aby zawartość tła była lekko widoczna, ale nadal wyraźnie przyciemniona, więc ustawiasz ją na 0.7. |
| **Kolor przycisku zamknięcia** | Ustawia kolor przycisku „X” (zamknij) dla pop-upu. | *Po ustawieniu na #000000:* Przycisk zamknięcia będzie czarny. *Po ustawieniu na #FF0000:* Przycisk zamknięcia będzie czerwony. | #000000 (Czarny) | Twój sklep używa czerwonego koloru akcentu, więc ustawiasz przycisk zamknięcia na czerwony dla spójności. |
| **Kolor tła przycisku zamknięcia** | Ustawia kolor tła przycisku „X” (zamknij). | *Po ustawieniu na #FFFFFF:* Tło przycisku zamknięcia będzie białe. *Po ustawieniu na transparentny:* Nie zostanie zastosowany kolor tła. | transparentny | Chcesz, aby przycisk zamknięcia wtapiał się w pop-up, więc ustawiasz jego tło na przezroczyste. |
| **Włącz Google reCAPTCHA** | Aktywuje Google reCAPTCHA dla formularzy logowania i rejestracji w pop-upie, pomagając zapobiegać spamowi i rejestracjom botów. | *Po włączeniu:* reCAPTCHA pojawi się w formularzach, wymagając od użytkowników weryfikacji, że nie są robotami. *Po wyłączeniu:* Nie będzie obecna reCAPTCHA. | TAK (jeśli masz klucze reCAPTCHA) | Doświadczasz wielu rejestracji spamowych, więc włączasz reCAPTCHA, aby je odfiltrować. |
| **Klucz witryny reCAPTCHA** | Twój publiczny klucz witryny reCAPTCHA, uzyskany od Google. Wymagany, jeśli reCAPTCHA jest włączona. | *Po poprawnym wprowadzeniu:* reCAPTCHA będzie działać. *Po niepoprawnym lub pustym:* reCAPTCHA nie będzie działać, potencjalnie blokując legalnych użytkowników lub nie zapobiegając botom. | Twój rzeczywisty klucz witryny Google reCAPTCHA | Zarejestrowałeś swoją witrynę w Google reCAPTCHA i wklejasz tutaj dostarczony klucz witryny. |
| **Tajny klucz reCAPTCHA** | Twój prywatny tajny klucz reCAPTCHA, uzyskany od Google. Wymagany, jeśli reCAPTCHA jest włączona. | *Po poprawnym wprowadzeniu:* reCAPTCHA będzie działać. *Po niepoprawnym lub pustym:* reCAPTCHA nie będzie działać. | Twój rzeczywisty tajny klucz Google reCAPTCHA | Zarejestrowałeś swoją witrynę w Google reCAPTCHA i wklejasz tutaj dostarczony tajny klucz. |

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz logowanie PopUp | TAK | Aktywuje/dezaktywuje funkcję logowania pop-up. |
| Konfiguracja modułu | Typ formularza PopUp | (Wybierz na podstawie projektu) | Wybiera styl wizualny formularza logowania. |
| Konfiguracja modułu | Szerokość PopUp (piksele) | 400-500px | Kontroluje szerokość okna pop-up. |
| Konfiguracja modułu | Wysokość PopUp (piksele) | 300-450px | Kontroluje wysokość okna pop-up. |
| Konfiguracja modułu | Kolor tła PopUp | #FFFFFF | Ustawia kolor tła pop-upu. |
| Konfiguracja modułu | Kolor ramki PopUp | #CCCCCC lub transparentny | Ustawia kolor ramki pop-upu. |
| Konfiguracja modułu | Promień ramki PopUp (piksele) | 5-10px | Kontroluje zaokrąglenie rogów pop-upu. |
| Konfiguracja modułu | Kolor tła nakładki | #000000 | Ustawia kolor przyciemnionego tła za pop-upem. |
| Konfiguracja modułu | Przezroczystość nakładki (0-1) | 0.7-0.8 | Kontroluje przezroczystość tła nakładki. |
| Konfiguracja modułu | Kolor przycisku zamknięcia | #000000 | Ustawia kolor przycisku zamknięcia pop-upu. |
| Konfiguracja modułu | Kolor tła przycisku zamknięcia | transparentny | Ustawia kolor tła przycisku zamknięcia. |
| Konfiguracja modułu | Włącz Google reCAPTCHA | TAK (jeśli klucze dostępne) | Aktywuje reCAPTCHA do ochrony przed botami. |
| Konfiguracja modułu | Klucz witryny reCAPTCHA | Twój rzeczywisty klucz | Klucz publiczny do weryfikacji reCAPTCHA. |
| Konfiguracja modułu | Tajny klucz reCAPTCHA | Twój rzeczywisty klucz | Klucz prywatny do weryfikacji reCAPTCHA. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Pop-up nie pojawia się po kliknięciu „Zaloguj się”. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Upewnij się, że ustawienie „Włącz logowanie PopUp” jest ustawione na TAK w konfiguracji modułu.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają załadowanie nowej funkcjonalności modułu.
3.  **Kompatybilność z szablonem:** Niektóre bardzo dostosowane szablony mogą używać niestandardowych sposobów obsługi linków logowania. Sprawdź, czy Twój szablon ma specyficzne ustawienia lub nadpisania dla logowania. Jeśli problemy nadal występują, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Pop-up wygląda dziwnie lub nie pasuje do stylu mojego szablonu.**
O:

1.  **Dostosuj ustawienia stylizacji:** Przejdź do konfiguracji modułu i eksperymentuj z „Kolorem tła PopUp”, „Kolorem ramki PopUp”, „Promieniem ramki PopUp (piksele)”, „Kolorem tła nakładki” i „Przezroczystością nakładki (0-1)”.
2.  **Typ formularza:** Wypróbuj różne opcje „Typ formularza PopUp”, aby sprawdzić, czy inny projekt lepiej integruje się z Twoim szablonem.
3.  **Niestandardowy CSS:** Jeśli podstawowe ustawienia nie są wystarczające, Twój webmaster może potrzebować dodać niestandardowy CSS do Twojego szablonu, aby nadpisać domyślne style modułu (szczegóły dotyczące pliku CSS w sekcji 7.5).

**P3: reCAPTCHA nie działa w formularzach pop-up.**
O:

1.  **Włącz reCAPTCHA:** Upewnij się, że „Włącz Google reCAPTCHA” jest ustawione na TAK.
2.  **Sprawdź klucze:** Dwukrotnie sprawdź, czy Twoje „Klucz witryny reCAPTCHA” i „Tajny klucz reCAPTCHA” są poprawnie wprowadzone w konfiguracji modułu. Są one wrażliwe na wielkość liter.
3.  **Konfiguracja Google reCAPTCHA:** Upewnij się, że Twoja domena jest poprawnie zarejestrowana w Twoim koncie Google reCAPTCHA.
4.  **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w ustawieniach reCAPTCHA.

**P4: Pop-up jest za duży/mały na moim telefonie komórkowym.**
O:

1.  **Dostosuj szerokość/wysokość:** Zmodyfikuj „Szerokość PopUp (piksele)” i „Wysokość PopUp (piksele)” w konfiguracji modułu. Chociaż są to wartości w pikselach, moduł jest zaprojektowany tak, aby był responsywny, więc dostosowanie ich wpłynie na jego skalowanie na różnych urządzeniach.
2.  **Testuj responsywność:** Użyj narzędzi deweloperskich przeglądarki (F12), aby symulować różne urządzenia mobilne i precyzyjnie dostroić wymiary.

**P5: Jak przetłumaczyć tekst w pop-upie?**
O:

1.  **Tłumacz moduł:** W Panelu administracyjnym PrestaShop przejdź do **Lokalizacja > Tłumaczenia**.
2.  **Wybierz opcje:**
    - Typ tłumaczenia: „Tłumaczenia zainstalowanych modułów”
    - Wybierz swój szablon: Twój aktualny szablon
    - Wybierz swój język: Język, na który chcesz przetłumaczyć
3.  **Znajdź moduł:** Wyszukaj „PopUp Login Pro” (lub `popuplogin`).
4.  **Tłumacz pola:** Znajdziesz wszystkie przetłumaczalne ciągi znaków używane przez moduł. Wprowadź swoje tłumaczenia i zapisz.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł PopUp Login Pro opiera się na standardowej architekturze modułów PrestaShop, wykorzystując głównie kontrolery front-office do żądań AJAX i hooki do integracji z szablonem. Używa JavaScriptu do przechwytywania standardowych kliknięć w linki logowania i wyświetlania pop-upu, dynamicznie ładując zawartość za pomocą AJAX. Konfiguracja jest obsługiwana przez metodę `getContent()` głównej klasy modułu, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:
  - `controllers/front/index.php`
    - **Nazwa klasy**: `PopUpLoginIndexModuleFrontController`
    - **Klasa nadrzędna**: `ModuleFrontController`
    - **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako ogólny punkt wejścia lub obsługuje początkową konfigurację interakcji z front-office, chociaż jego specyficzne metody definiowałyby jego dokładną rolę. Może być odpowiedzialny za renderowanie początkowej struktury pop-upu lub obsługę wywołań AJAX niezwiązanych z logowaniem.
  - `controllers/front/loginbox.php`
    - **Nazwa klasy**: `PopUpLoginLoginBoxModuleFrontController`
    - **Klasa nadrzędna**: `ModuleFrontController`
    - **Odpowiedzialność**: To jest główny kontroler do obsługi logiki formularza logowania i rejestracji. Odpowiada na żądania AJAX dotyczące wyświetlania treści formularza logowania/rejestracji, przetwarzania prób logowania, obsługi nowych rejestracji i zarządzania żądaniami „zapomniałem hasła”. Prawdopodobnie zwraca fragmenty HTML lub odpowiedzi JSON do JavaScriptu w celu dynamicznego wstawienia do pop-upu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Na podstawie dostarczonego spisu, w katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Moduł prawdopodobnie wykorzystuje istniejące klasy rdzeniowe PrestaShop do zarządzania klientami (`Customer`, `Context`, `Tools`) i standardowego przechowywania konfiguracji.

### 4.4 Zasoby JavaScript (`views/js/`)

- `popuplogin/popuplogin.js`
  - **Zakres**: Front-office.
  - **Szczegóły**: To jest główny plik JavaScript dla funkcjonalności front-end modułu.
    - **Słuchacze zdarzeń**: Wiąże słuchaczy zdarzeń z różnymi elementami, najważniejsze z nich to standardowe linki logowania/konta (np. `a[href*="controller=authentication"]`, `a[href*="my-account"]`). Przechwytuje zdarzenia kliknięcia na tych linkach.
    - **Wywołania AJAX**: Po kliknięciu linku logowania, zapobiega domyślnej nawigacji i inicjuje żądanie AJAX do `popuplogin/controllers/front/loginbox.php` (lub podobnego) w celu pobrania HTML formularza logowania/rejestracji.
    - **Manipulacja DOM**: Dynamicznie tworzy i wstawia nakładkę pop-upu oraz zawartość formularza logowania do DOM. Obsługuje pokazywanie/ukrywanie pop-upu, zarządzanie nakładką i potencjalnie przełączanie między widokami logowania i rejestracji w pop-upie.
    - **Przesyłanie formularzy**: Prawdopodobnie przechwytuje przesyłanie formularzy w pop-upie (logowanie, rejestracja, zapomniałem hasła) i wysyła je za pośrednictwem AJAX do kontrolera `loginbox.php`, przetwarzając odpowiedzi (np. wyświetlając komunikaty o sukcesie, komunikaty o błędach lub przekierowując po udanym logowaniu).
    - **UI/UX**: Zarządza efektami wizualnymi pop-upu (np. zanikanie/pojawianie się, centrowanie).
    - **Integracja reCAPTCHA**: Jeśli reCAPTCHA jest włączona, ten skrypt jest odpowiedzialny za renderowanie widżetu reCAPTCHA i dołączanie jego tokena do przesyłanych formularzy AJAX.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `popuplogin/css.css`
  - **Zakres**: Stylizacja klienta front-office.
  - **Szczegóły**: Ten plik prawdopodobnie zawiera ogólne, podstawowe style dla kontenera pop-upu, nakładki i potencjalnie wspólnych elementów formularza. Może zawierać style resetujące lub podstawowe reguły układu.
  - **Kluczowe selektory**: `.popuplogin-overlay`, `.popuplogin-popup`, `.popuplogin-close-btn`.
- `popuplogin/popuplogin.css`
  - **Zakres**: Stylizacja klienta front-office.
  - **Szczegóły**: Ten plik prawdopodobnie zawiera bardziej specyficzne i szczegółowe style dla różnych typów formularzy pop-up, w tym pól wejściowych, przycisków, komunikatów o błędach i responsywnych dostosowań. Zdefiniuje różnice wizualne między opcjami „Typ formularza PopUp”.
  - **Kluczowe selektory**: `.popuplogin-form-type-1`, `.popuplogin-form-type-2`, `.popuplogin-input`, `.popuplogin-button`, `.popuplogin-error-message`.
  - **Nadpisanie przez programistę**: Programiści mogą nadpisać te style w pliku `custom.css` swojego szablonu lub tworząc szablon potomny, aby zmodyfikować wygląd bez bezpośredniej edycji plików modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `popuplogin/dashboardZoneOne.tpl`
    - **Hook**: Prawdopodobnie `displayDashboardZoneOne` (lub podobny hook pulpitu).
    - **Cel**: Ten szablon prawdopodobnie służy do wyświetlania małego bloku informacyjnego lub szybkich statystyk związanych z modułem PopUp Login Pro na pulpicie Panelu administracyjnego PrestaShop. Jest to szablon skierowany do administratora.
  - `popuplogin/displayPopUpLogin.tpl`
    - **Hook**: Ten szablon jest prawdopodobnie renderowany przez kontroler front-office `loginbox.php` i zawiera rzeczywistą strukturę HTML dla formularza logowania/rejestracji, który pojawia się w pop-upie. Nie jest on bezpośrednio podłączony do hooka `display` w szablonie, ale raczej ładowany dynamicznie.
    - **Cel**: Renderuje formularze logowania, rejestracji i zapomniałem hasła, w tym pola wejściowe, przyciski i potencjalnie miejsca na reCAPTCHA.
  - `popuplogin/header.tpl`
    - **Hook**: Prawdopodobnie `displayHeader`.
    - **Cel**: Ten szablon jest odpowiedzialny za dołączanie plików CSS i JavaScript modułu (`popuplogin.js`, `css.css`, `popuplogin.css`) do sekcji `<head>` stron front-office, zapewniając ich załadowanie przed uruchomieniem funkcjonalności modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  - Moduł nie tworzy niestandardowych tabel SQL.
  - Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy zazwyczaj poprzedzonych prefiksem `POPUPLOGIN_` (np. `POPUPLOGIN_ENABLED`, `POPUPLOGIN_FORM_TYPE`, `POPUPLOGIN_WIDTH`, `POPUPLOGIN_RECAPTCHA_SITE_KEY`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS i JavaScript modułu dla funkcjonalności front-end. |
| `displayDashboardZoneOne` | Na pulpicie Panelu administracyjnego PrestaShop. | Wyświetla blok informacyjny lub widżet dla modułu w panelu administracyjnym. |
| (Hooki niejawne) | Wyzwalane przez przechwytywanie JavaScriptem standardowych linków logowania. | JavaScript modułu przechwytuje kliknięcia w elementy, które normalnie prowadziłyby do kontrolerów `authentication` lub `my-account`, a następnie używa AJAX do dynamicznego ładowania treści z własnych kontrolerów front-office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu PopUp Login Pro, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie doskonałego funkcjonowania modułu i jego bezproblemowej integracji z Twoim sklepem PrestaShop.
