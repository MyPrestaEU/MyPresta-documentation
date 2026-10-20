---
title: "Free Shipping Progress Bar Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop Free Shipping Progress Bar Pro od MyPresta.eu."
sidebar:
  label: "Free Shipping Progress Bar Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free Shipping Progress Bar Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/free-shipping-progress-bar-pro/)
>
> ---


# Free Shipping Progress Bar Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane i domyślnie włączone w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny obszar konfiguracji, w którym ustawisz wszystkie zasady, wygląd i zachowanie paska postępu darmowej wysyłki. Strona została zaprojektowana tak, aby była intuicyjna, prowadząc Cię przez różne sekcje.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Kontroluje ogólną aktywację i podstawowe zachowanie paska postępu.
-   **Efekt zmiany tego ustawienia:**
    -   *Włącz/Wyłącz moduł:* Włącza lub wyłącza całą funkcjonalność paska postępu dla Twojego sklepu.
    -   *Pozycja wyświetlania:* Określa, gdzie pasek postępu pojawia się w Twoim front office (np. Nagłówek, Stopka, Strona produktu, Strona koszyka).
    -   *Pasek przyklejony (Sticky Bar):* Sprawia, że pasek „przykleja się” do góry lub dołu ekranu, gdy użytkownik przewija, utrzymując go widocznym.
-   **Zalecana wartość:**
    -   *Włącz moduł:* TAK (aby aktywować funkcję).
    -   *Pozycja wyświetlania:* Nagłówek (często najbardziej efektywna dla widoczności).
    -   *Pasek przyklejony:* TAK (dla maksymalnego efektu).
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby pasek postępu był zawsze widoczny u góry Twojego sklepu, aby stale przypominać klientom o darmowej wysyłce. Włączysz moduł, ustawisz pozycję wyświetlania na „Nagłówek” i włączysz „Pasek przyklejony”.

#### Progi darmowej wysyłki

-   **Co robi to ustawienie:** Definiuje kwotę, którą klienci muszą wydać, aby zakwalifikować się do darmowej wysyłki. Jest to rdzeń funkcjonalności modułu. Możesz ustawić domyślny próg, a następnie nadpisać go za pomocą konkretnych zasad dla krajów lub grup klientów.
-   **Efekt zmiany tego ustawienia:**
    -   *Domyślny próg:* Ustawia podstawową kwotę dla wszystkich klientów nieobjętych konkretnymi zasadami.
    -   *Progi specyficzne dla kraju:* Pozwala ustawić różne kwoty darmowej wysyłki dla klientów z określonych krajów (np. wyższe dla wysyłki międzynarodowej).
    -   *Progi specyficzne dla grupy klientów:* Dostosuj progi dla różnych grup klientów (np. niższe dla klientów VIP, wyższe dla hurtowników).
-   **Zalecana wartość:** Zacznij od domyślnego progu, który ma sens dla Twojej średniej wartości zamówienia i kosztów wysyłki. Następnie dodaj konkretne zasady w miarę potrzeb.
-   **Scenariusz / przykład dla sprzedawcy:** Twoja domyślna darmowa wysyłka to 100 zł. Jednak dla klientów w Kanadzie chcesz, aby było to 150 zł ze względu na wyższe koszty wysyłki. Ustawisz domyślny próg na 100 zł, a następnie dodasz zasadę dla Kanady na 150 zł. Dla Twojej grupy klientów „Hurtownicy” możesz ustawić go na 500 zł.

#### Projektant wizualny

-   **Co robi to ustawienie:** Zapewnia przyjazny dla użytkownika interfejs do dostosowywania wyglądu i stylu paska postępu bez żadnego kodowania. Możesz zmieniać kolory, czcionki, style paska i wiele więcej.
-   **Efekt zmiany tego ustawienia:** Bezpośrednio wpływa na wygląd wizualny paska postępu w Twoim front office.
    -   *Kolory:* Dostosuj kolory tła, tekstu i wypełnienia paska postępu, aby pasowały do Twojej marki.
    -   *Czcionki i rozmiary:* Dostosuj style tekstu dla wiadomości.
    -   *Styl paska:* Wybierz spośród różnych stylów wizualnych samego paska postępu (np. zaokrąglony, płaski).
    -   *Animacje:* Dodaj subtelne animacje, aby uzyskać bardziej angażujące doświadczenie.
-   **Zalecana wartość:** Eksperymentuj, aby znaleźć projekt, który jest atrakcyjny wizualnie, wyraźnie widoczny i spójny z brandingiem Twojego sklepu.
-   **Scenariusz / przykład dla sprzedawcy:** Twój sklep używa określonego odcienia niebieskiego i czystej, nowoczesnej czcionki. Użyjesz projektanta wizualnego, aby ustawić tło paska postępu na ten niebieski, tekst na biały i wybrać czcionkę bezszeryfową, aby pasowała do Twojego motywu.

#### Dynamiczne wiadomości

-   **Co robi to ustawienie:** Pozwala tworzyć niestandardowe wiadomości, które pojawiają się na pasku postępu, zmieniając się w zależności od postępu klienta w kierunku darmowej wysyłki. Możesz używać symboli zastępczych do wstawiania dynamicznych wartości, takich jak pozostała kwota.
-   **Efekt zmiany tego ustawienia:**
    -   *Wiadomości dla „Jeszcze nie zakwalifikowany”:* Wyświetla się, gdy klient nie osiągnął progu.
    -   *Wiadomości dla „Zakwalifikowany”:* Wyświetla się, gdy klient osiągnął lub przekroczył próg.
    -   *Symbole zastępcze:* Użycie `[amount_left]`, `[total_cart]`, `[free_shipping_threshold]`, `[currency_symbol]` dynamicznie wstawi te wartości do Twoich wiadomości.
-   **Zalecana wartość:** Wiadomości powinny być jasne, zwięzłe i zachęcające. Używaj symboli zastępczych, aby były dynamiczne i osobiste.
-   **Scenariusz / przykład dla sprzedawcy:**
    -   *Nie zakwalifikowany:* „Wydaj jeszcze [amount\_left] na DARMOWĄ wysyłkę!”
    -   *Zakwalifikowany:* „Gratulacje! Twoje zamówienie kwalifikuje się do DARMOWEJ wysyłki!”
        To jasno komunikuje cel i celebruje osiągnięcie.

#### Testy A/B i analityka

-   **Co robi to ustawienie:** Umożliwia przeprowadzanie testów A/B na różnych konfiguracjach paska postępu (np. różne wiadomości, kolory lub progi) i śledzenie ich wydajności.
-   **Efekt zmiany tego ustawienia:**
    -   *Włącza tryb testów A/B:* Pozwala tworzyć warianty paska postępu.
    -   *Śledzi konwersje:* Rejestruje, jak różne warianty wpływają na współczynniki konwersji i średnią wartość zamówienia.
-   **Zalecana wartość:** Włącz tę funkcję, gdy Twoja podstawowa konfiguracja jest stabilna. Używaj jej do ciągłego optymalizowania skuteczności paska postępu.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz sprawdzić, czy „Wydaj X zł więcej na DARMOWĄ wysyłkę!” działa lepiej niż „Odblokuj DARMOWĄ wysyłkę za jedyne X zł!”. Ustawisz dwa warianty i pozwolisz modułowi śledzić, który z nich prowadzi do większej sprzedaży.

#### Ustawienia zaawansowane

-   **Co robi to ustawienie:** Zawiera opcje dotyczące bardziej technicznych aspektów, takich jak buforowanie, kompatybilność z konkretnymi motywami lub niestandardowy CSS/JS.
-   **Efekt zmiany tego ustawienia:** Może wpływać na wydajność, integrację z motywem lub pozwalać na bardzo specyficzne dostosowania.
    -   *Ustawienia pamięci podręcznej:* Poprawia szybkość ładowania poprzez buforowanie zawartości paska.
    -   *Niestandardowy CSS/JS:* Pozwala programistom dodawać własne style lub skrypty.
-   **Zalecana wartość:** Zazwyczaj pozostaw te ustawienia domyślne, chyba że masz konkretną potrzebę lub doradzi Ci programista.
-   **Scenariusz / przykład dla sprzedawcy:** Twój niestandardowy motyw ma unikalną strukturę nagłówka, a pasek postępu nie wyrównuje się idealnie. Programista może użyć pola „Niestandardowy CSS” do dodania specyficznych reguł stylizacji, aby naprawić wyrównanie.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Ustawienia ogólne** | Włącz moduł | TAK | Aktywuje/dezaktywuje całą funkcję paska postępu. |
| | Pozycja wyświetlania | Nagłówek | Gdzie pojawia się pasek (Nagłówek, Stopka, Produkt, Koszyk, Kolumny). |
| | Pasek przyklejony | TAK | Sprawia, że pasek przykleja się do góry/dołu ekranu. |
| **Progi darmowej wysyłki** | Domyślny próg | Kwota darmowej wysyłki Twojego sklepu | Podstawowa kwota dla darmowej wysyłki. |
| | Zasady dla krajów | W zależności od potrzeb | Nadpisuje domyślne dla konkretnych krajów. |
| | Zasady dla grup klientów | W zależności od potrzeb | Nadpisuje domyślne dla konkretnych grup klientów. |
| **Projektant wizualny** | Kolor tła paska | Zależny od motywu | Zmienia kolor tła paska. |
| | Kolor wypełnienia postępu | Zależny od motywu | Zmienia kolor wypełnionej sekcji postępu. |
| | Kolor tekstu | Zależny od motywu | Zmienia kolor wiadomości. |
| | Rodzina / Rozmiar czcionki | Zależny od motywu | Dostosowuje wygląd tekstu. |
| | Styl paska | Domyślny | Wizualny projekt samego paska postępu. |
| **Dynamiczne wiadomości** | Wiadomość - Nie zakwalifikowany | „Wydaj [amount\_left] więcej na DARMOWĄ wysyłkę!” | Wiadomość wyświetlana, gdy cel nie został osiągnięty. |
| | Wiadomość - Zakwalifikowany | „Gratulacje! Twoje zamówienie kwalifikuje się do DARMOWEJ wysyłki!” | Wiadomość wyświetlana, gdy cel został osiągnięty. |
| **Testy A/B i analityka** | Włącz testy A/B | NIE (początkowo) | Umożliwia przeprowadzanie testów na różnych konfiguracjach paska. |
| | Śledź konwersje | TAK (podczas testów A/B) | Rejestruje wydajność różnych wersji paska. |
| **Ustawienia zaawansowane** | Włącz pamięć podręczną | TAK | Poprawia szybkość ładowania paska. |
| | Niestandardowy CSS | Pozostaw puste | Do zaawansowanych nadpisań stylów przez programistów. |
| | Niestandardowy JS | Pozostaw puste | Do zaawansowanych dodatków skryptów przez programistów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Pasek postępu nie wyświetla się w moim sklepie lub nie aktualizuje się.**
**O1:**

-   **Sprawdź status modułu:** Najpierw upewnij się, że moduł jest włączony w Twoim Panelu administracyjnym PrestaShop w sekcji **Moduły > Menedżer modułów**.
-   **Zweryfikuj pozycję wyświetlania:** Przejdź do konfiguracji modułu i sprawdź ustawienie „Pozycja wyświetlania”. Upewnij się, że jest ustawione na widoczny hook (np. Nagłówek, Stopka). Jeśli wybrałeś hook kolumny, upewnij się, że Twój motyw faktycznie wyświetla tę kolumnę.
-   **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Wyczyść również pamięć podręczną przeglądarki.
-   **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą wymagać drobnych korekt. Jeśli problem nadal występuje po wyczyszczeniu pamięci podręcznej, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły dotyczące Twojego motywu.

**P2: Pasek postępu wygląda dziwnie lub nie pasuje do projektu mojego motywu.**
**O2:**

-   **Użyj Projektanta Wizualnego:** Moduł zawiera sekcję „Projektant Wizualny” w swojej konfiguracji. Użyj jej, aby dostosować kolory, czcionki i style, aby lepiej pasowały do Twojego motywu.
-   **Niestandardowy CSS:** Jeśli projektant wizualny nie wystarcza, Twój webmaster lub programista może użyć pola „Niestandardowy CSS” w zaawansowanych ustawieniach modułu, aby dodać specyficzne reguły stylizacji, które nadpisują domyślne.
-   **Pamięć podręczna motywu:** Po wprowadzeniu zmian w projekcie zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki.

**P3: Kwota darmowej wysyłki jest nieprawidłowa lub nie zmienia się dla niektórych klientów.**
**O3:**

-   **Sprawdź zasady progów:** Przejdź do sekcji „Progi darmowej wysyłki” w konfiguracji modułu.
    -   Sprawdź, czy „Domyślny próg” jest poprawny.
    -   Sprawdź, czy jakiekolwiek „Progi specyficzne dla kraju” lub „Progi specyficzne dla grupy klientów” nadpisują domyślny próg dla dotkniętych klientów. Upewnij się, że zasady są poprawnie ustawione dla odpowiednich krajów/grup.
-   **Waluta:** Upewnij się, że Twoja domyślna waluta i waluta używana dla progu są zgodne.
-   **Obliczanie koszyka:** Moduł opiera się na sumie koszyka PrestaShop. Upewnij się, że Twoje produkty mają prawidłowe ceny, a zasady podatkowe są stosowane zgodnie z oczekiwaniami.

**P4: Jak przetłumaczyć wiadomości na różne języki dla moich międzynarodowych klientów?**
**O4:**

-   Moduł obsługuje natywny system tłumaczeń PrestaShop.
-   Przejdź do **Lokalizacja > Tłumaczenia** w swoim Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz moduł „Free Shipping Progress Bar Pro”.
-   Możesz następnie przetłumaczyć wszystkie dynamiczne wiadomości i inne teksty wyświetlane przez moduł na wybrane języki. Pamiętaj, aby zapisać zmiany.

**P5: Pasek postępu nie wyświetla się na urządzeniach mobilnych lub nie jest responsywny.**
**O5:**

-   Moduł został zaprojektowany tak, aby był w pełni responsywny.
-   **Wyczyść pamięć podręczną:** Jak zawsze, wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki mobilnej.
-   **Sprawdź pozycję wyświetlania:** Upewnij się, że wybrana pozycja wyświetlania (np. Nagłówek) jest taka, którą Twój motyw wyraźnie renderuje na urządzeniach mobilnych. Niektóre motywy mogą ukrywać pewne elementy na mniejszych ekranach.
-   **Konflikty motywów:** Bardzo rzadko, wysoce spersonalizowany motyw mobilny może mieć sprzeczne style CSS. Jeśli problem nadal występuje, skonsultuj się z pomocą techniczną MyPresta.eu lub swoim webmasterem.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu Free Shipping Progress Bar Pro, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `Free Shipping Progress Bar Pro` (`smartfreeshippingpro`) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie hooki do wyświetlania w front-office oraz dedykowany `ModuleFrontController` do interakcji AJAX. Konfiguracja jest zarządzana za pomocą metody `getContent()` głównej klasy modułu, renderującej szablon Smarty dla interfejsu back-office. Moduł używa klasy `Configuration` PrestaShop do przechowywania ustawień i opiera się na podstawowych usługach PrestaShop do informacji o koszyku i walucie. Moduł kładzie nacisk na wizualne podejście do konfiguracji z dedykowanym JS dla interfejsu administracyjnego.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `smartfreeshippingpro/controllers/front/index.php`
        -   **Nazwa klasy:** `SmartFreeShippingProIndexModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
        -   **Klasa nadrzędna:** `ModuleFrontController`
        -   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako podstawa lub punkt wejścia dla interakcji front-office, chociaż jego specyficzne metody mogą być minimalne, jeśli `refresh.php` obsługuje główny AJAX. Może być odpowiedzialny za początkowe ustawienie danych lub logikę front-office nieopartą na AJAX.
    -   `smartfreeshippingpro/controllers/front/refresh.php`
        -   **Nazwa klasy:** `SmartFreeShippingProRefreshModuleFrontController`
        -   **Klasa nadrzędna:** `ModuleFrontController`
        -   **Odpowiedzialność:** Jest to krytyczny punkt końcowy AJAX. Odpowiada na żądania (np. z `front.js`) w celu aktualizacji paska postępu darmowej wysyłki. Pobiera aktualną sumę koszyka, oblicza pozostałą kwotę do darmowej wysyłki na podstawie skonfigurowanych progów (domyślne, zasady dla krajów, zasady dla grup) i zwraca zaktualizowane dane postępu oraz wiadomości, zazwyczaj w formacie JSON. Ten kontroler jest odpowiedzialny za aktualizacje paska w czasie rzeczywistym.
-   **Kontrolery administracyjne Back-Office**:

    -   Brak dedykowanych plików `AdminController`. Cała konfiguracja back-office jest obsługiwana w metodzie `getContent()` głównego pliku modułu (`index.php`).

### 4.3 Klasy i modele rdzeniowe (`classes/`)

W dostarczonym spisie nie ma jawnie wymienionych niestandardowych klas rozszerzających `ObjectModel` ani innych klas rdzeniowych PrestaShop. Moduł prawdopodobnie opiera się na wbudowanych klasach PrestaShop `Cart`, `Context`, `Configuration`, `Currency` i `Country` dla swojej logiki.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `smartfreeshippingpro/views/js/admin-config.js`
    -   **Zakres:** Back-office.
    -   **Opis:** Prawdopodobnie obsługuje ogólne interakcje formularza konfiguracji, zapisywanie ustawień i potencjalnie walidację formularza dla głównej strony konfiguracji modułu.
-   `smartfreeshippingpro/views/js/admin-placeholders.js`
    -   **Zakres:** Back-office.
    -   **Opis:** Zarządza dynamicznym wstawianiem symboli zastępczych (np. `[amount_left]`, `[total_cart]`) do pól wprowadzania wiadomości w konfiguracji administracyjnej, ułatwiając sprzedawcom tworzenie dynamicznych wiadomości.
-   `smartfreeshippingpro/views/js/admin-threshold-picker.js`
    -   **Zakres:** Back-office.
    -   **Opis:** Obsługuje logikę dodawania, edytowania i usuwania progów darmowej wysyłki specyficznych dla kraju i grupy klientów. Obejmowałoby to dynamiczne elementy formularza do wyboru krajów/grup i wprowadzania kwot.
-   `smartfreeshippingpro/views/js/admin-visual-designer.js`
    -   **Zakres:** Back-office.
    -   **Opis:** Zasila interfejs wizualnego dostosowywania. Prawdopodobnie używa JavaScript do dynamicznej aktualizacji podglądu paska postępu, gdy administrator zmienia kolory, czcionki i style, zapewniając natychmiastową wizualną informację zwrotną.
-   `smartfreeshippingpro/views/js/admin.js`
    -   **Zakres:** Back-office.
    -   **Opis:** Ogólny skrypt administracyjny, który może inicjalizować inne pliki JS specyficzne dla administratora, obsługiwać globalne zdarzenia administracyjne lub dostarczać funkcji narzędziowych dla interfejsu back-office.
-   `smartfreeshippingpro/views/js/front.js`
    -   **Zakres:** Front-office.
    -   **Opis:** Jest to podstawowy skrypt front-endowy.
        -   **Słuchacze zdarzeń:** Wiąże się z `prestashop.on('updateCart', ...)` lub podobnymi zdarzeniami w celu wykrywania zmian w koszyku (dodawanie, usuwanie, aktualizacja ilości).
        -   **Wywołania AJAX:** Wyzwala żądania AJAX do kontrolera frontowego `refresh.php` w celu uzyskania zaktualizowanych danych paska postępu.
        -   **Manipulacja DOM:** Aktualizuje szerokość paska postępu, wiadomości tekstowe i potencjalnie jego widoczność na podstawie odpowiedzi AJAX.
        -   **Animacje:** Może zawierać logikę dla płynnych przejść lub animacji paska postępu.
        -   **Logika paska przyklejonego:** Jeśli funkcja paska przyklejonego jest włączona, ten skrypt obsługiwałby pozycjonowanie CSS (`position: fixed`) i potencjalnie słuchacze zdarzeń przewijania w celu zarządzania jego widocznością.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `smartfreeshippingpro/views/css/admin-config.css`
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Opis:** Style dla ogólnego układu i elementów głównej strony konfiguracji modułu.
-   `smartfreeshippingpro/views/css/admin-threshold-picker.css`
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Opis:** Specyficzne style dla interfejsów wyboru progów dla krajów i grup klientów.
-   `smartfreeshippingpro/views/css/admin-visual-designer.css`
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Opis:** Style dla interfejsu projektanta wizualnego, w tym próbniki kolorów, elementy podglądu i układ.
-   `smartfreeshippingpro/views/css/admin.css`
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Opis:** Ogólne style administracyjne, potencjalnie obejmujące wspólne elementy używane w różnych sekcjach administracyjnych modułu.
-   `smartfreeshippingpro/views/css/front.css`
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Opis:**
        -   Główne komponenty interfejsu użytkownika: Stylizuje kontener paska postępu, wypełnienie postępu i wiadomości tekstowe.
        -   Kluczowe selektory klas CSS: Prawdopodobnie zawiera klasy takie jak `.smartfreeshippingpro-bar`, `.smartfreeshippingpro-progress`, `.smartfreeshippingpro-message`, `.smartfreeshippingpro-sticky`. Programiści mogą je nadpisywać w pliku `custom.css` swojego motywu lub dodając niestandardowy CSS w zaawansowanych ustawieniach modułu.
        -   Reguły responsywnego projektowania dla różnych rozmiarów ekranu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `smartfreeshippingpro/views/templates/admin/configure.tpl`
        -   **Opis:** Główny szablon strony konfiguracji modułu w Panelu administracyjnym. Renderuje cały formularz, w tym ustawienia ogólne, linki do innych pod-szablonów dla konkretnych sekcji (takich jak projektant wizualny, selektor progów).
    -   `smartfreeshippingpro/views/templates/admin/country-priority.tpl`
        -   **Opis:** Prawdopodobnie pod-szablon używany w `configure.tpl` do zarządzania priorytetem zasad specyficznych dla kraju, jeśli może obowiązywać wiele zasad (np. klient jest w kraju z konkretną zasadą, ale także należy do grupy z inną zasadą).
    -   `smartfreeshippingpro/views/templates/admin/country-rules-picker.tpl`
        -   **Opis:** Pod-szablon dla interfejsu, w którym administratorzy definiują i zarządzają progami darmowej wysyłki na podstawie krajów klientów.
    -   `smartfreeshippingpro/views/templates/admin/group-rules-picker.tpl`
        -   **Opis:** Pod-szablon dla interfejsu, w którym administratorzy definiują i zarządzają progami darmowej wysyłki na podstawie grup klientów.
    -   `smartfreeshippingpro/views/templates/admin/visual-designer.tpl`
        -   **Opis:** Pod-szablon dla interfejsu projektanta wizualnego, zawierający strukturę HTML dla paska podglądu i pól wprowadzania (próbniki kolorów, suwaki, pola tekstowe) do dostosowywania.
-   **Szablony hooków (`views/templates/hook/`)**:

    -   `smartfreeshippingpro/views/templates/hook/progress.tpl`
        -   **Opis:** Jest to główny szablon front-office. Zawiera strukturę HTML dla samego paska postępu darmowej wysyłki (np. `div` dla paska, `div` dla wypełnienia postępu i `span` dla dynamicznej wiadomości).
        -   **Renderowany w hookach:** Ten szablon jest renderowany w różnych hookach front-office, takich jak `displayHeader`, `displayFooter`, `displayProductButtons`, `displayShoppingCart`, `displayLeftColumn`, `displayRightColumn`, w zależności od konfiguracji sprzedawcy.
        -   **Wyjście bloku wizualnego:** Wyświetla kompletny, ostylowany pasek postępu z dynamiczną wiadomością.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie wydaje się tworzyć niestandardowych tabel SQL na podstawie spisu.
    -   Rekordy konfiguracji są przechowywane w tabeli `ps_configuration` PrestaShop. Klucze zazwyczaj będą miały wzorzec taki jak `SMARTFREESHIPPINGPRO_ENABLED`, `SMARTFREESHIPPINGPRO_THRESHOLD_DEFAULT`, `SMARTFREESHIPPINGPRO_COLOR_BAR`, `SMARTFREESHIPPINGPRO_MESSAGE_NOT_QUALIFIED` itp.
    -   Zasady specyficzne dla kraju i grupy mogą być przechowywane jako serializowane tablice w pojedynczym wpisie `ps_configuration` lub potencjalnie w prostej niestandardowej tabeli, jeśli struktura jest złożona, chociaż spis sugeruje, że `ObjectModel` nie jest używany.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` lub na samym początku `<body>`. | Wstrzykuje zasoby CSS/JS i/lub HTML paska postępu (zwłaszcza dla pasków przyklejonych). |
| `displayFooter` | Renderuje się na dole `<body>` przed tagiem zamykającym. | Wstrzykuje zasoby CSS/JS i/lub HTML paska postępu. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie bocznej sklepu. | Wyświetla pasek postępu w lewej kolumnie. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie bocznej sklepu. | Wyświetla pasek postępu w prawej kolumnie. |
| `displayProductButtons` | Renderuje się w pobliżu przycisku „Dodaj do koszyka” na stronach produktów. | Wyświetla pasek postępu bezpośrednio na stronach produktów. |
| `displayShoppingCart` | Renderuje się na stronie podsumowania koszyka. | Wyświetla pasek postępu na stronie koszyka, aby zachęcić do większych zakupów. |
| `actionFrontControllerSetMedia` | Wykonywane, gdy kontroler frontowy ustawia swoje media (CSS/JS). | Wstrzykuje pliki CSS i JavaScript specyficzne dla front-office. |
| `actionAdminControllerSetMedia` | Wykonywane, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Wstrzykuje pliki CSS i JavaScript specyficzne dla back-office dla strony konfiguracji. |
| `actionCartSave` | Wykonywane po zapisaniu koszyka (np. dodaniu/usunięciu produktu). | Wyzwala JS front-office do odświeżenia paska postępu za pośrednictwem AJAX. |
| `actionObjectCartUpdateAfter` | Wykonywane po zaktualizowaniu obiektu koszyka. | Podobnie jak `actionCartSave`, używane do wyzwalania aktualizacji. |
| `actionObjectOrderAddAfter` | Wykonywane po dodaniu nowego zamówienia. | Potencjalnie używane do analityki testów A/B w celu śledzenia konwersji. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Free Shipping Progress Bar Pro, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnienie płynnego i efektywnego działania Twojego modułu.

-   **Dostęp do aktualizacji:** Zaloguj się do swojego konta MyPresta.eu i przejdź do sekcji historii zamówień i pobierania, aby uzyskać najnowszą wersję modułu.
-   **Wsparcie techniczne:** Jeśli napotkasz jakiekolwiek problemy, masz pytania lub potrzebujesz pomocy z konfiguracją, otwórz zgłoszenie do pomocy technicznej za pośrednictwem swojego konta klienta MyPresta.eu. Nasz zespół ekspertów z przyjemnością pomoże.
