---
title: "Udostępnianie produktu na Facebooku + kod rabatowy - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Udostępnianie produktu na Facebooku + kod rabatowy” od MyPresta.eu."
sidebar:
  label: "Udostępnianie produktu na Facebooku + kod rabatowy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook product share + discount code na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-product-share-discount-code.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-product-share-discount-code/)
>
> ---


# Udostępnianie produktu na Facebooku + kod rabatowy

## 1. Wymagania i kompatybilność
-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla PrestaShop i są zwykle dostępne w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji przejdź do **Moduły > Menedżer modułów** i kliknij „Konfiguruj” obok „Udostępnianie produktu na Facebooku + kod rabatowy”. Ten ekran pozwala kontrolować podstawową funkcjonalność i wygląd modułu.

#### **Ustawienia ogólne**

-   **Włącz / Wyłącz moduł:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk udostępniania na Facebooku pojawi się na stronach produktów, a funkcjonalność kodu rabatowego będzie aktywna.
        -   *Gdy wyłączony:* Moduł będzie całkowicie nieaktywny. Przycisk udostępniania nie pojawi się, a kody rabatowe nie będą generowane.
    -   **Zalecana wartość:** TAK (aby aktywować funkcje modułu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy lub wykonujesz konserwację, możesz go tymczasowo wyłączyć. Gdy będzie gotowy, włącz go, aby rozpocząć generowanie udostępnień i rabatów.

-   **ID aplikacji Facebooka:**
    -   **Co robi to ustawienie:** To pole wymaga Twojego unikalnego ID aplikacji Facebooka. Ten ID jest kluczowy dla Facebooka, aby poprawnie zidentyfikować Twoją witrynę i śledzić udostępnienia. Musisz utworzyć aplikację Facebooka na platformie Facebook Developers (developers.facebook.com), aby uzyskać ten ID.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy poprawnie wprowadzony:* Moduł będzie poprawnie komunikować się z Facebookiem, umożliwiając śledzenie udostępnień i działanie mechanizmu rabatowego.
        -   *Gdy niepoprawny lub pusty:* Funkcjonalność udostępniania na Facebooku może nie działać, lub udostępnienia mogą nie być śledzone, uniemożliwiając wydawanie kodów rabatowych.
    -   **Zalecana wartość:** Twój prawidłowy ID aplikacji Facebooka (np. `123456789012345`).
    -   **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś aplikację Facebooka dla swojego sklepu. Skopiuj ID aplikacji z panelu deweloperskiego Facebooka i wklej je tutaj. Jest to jednorazowa konfiguracja.

-   **Typ rabatu:**
    -   **Co robi to ustawienie:** Określa typ rabatu, jaki klienci otrzymują po udostępnieniu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony na „Procentowy”:* Kod rabatowy będzie oferował procentową zniżkę od całkowitej kwoty zamówienia (np. 10% zniżki).
        -   *Gdy ustawiony na „Kwotowy”:* Kod rabatowy będzie oferował stałą wartość pieniężną od całkowitej kwoty zamówienia (np. 5 zł zniżki).
    -   **Zalecana wartość:** „Procentowy” lub „Kwotowy” w zależności od Twojej strategii marketingowej.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zachęcić do większych zamówień, rabat procentowy może być bardziej atrakcyjny. W przypadku mniejszych, częstych zakupów, stała kwota może być bardziej skuteczna.

-   **Wartość rabatu:**
    -   **Co robi to ustawienie:** Określa rzeczywistą wartość rabatu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli „Typ rabatu” to Procentowy:* Wprowadź wartość procentową (np. `10` dla 10%).
        -   *Jeśli „Typ rabatu” to Kwotowy:* Wprowadź wartość pieniężną (np. `5.00` dla 5 zł).
    -   **Zalecana wartość:** Wartość, która jest atrakcyjna dla klientów, ale także opłacalna dla Twojej firmy (np. `10` dla 10% zniżki, lub `5.00` dla 5 zł zniżki).
    -   **Scenariusz / przykład dla sprzedawcy:** Decydujesz się zaoferować 15% rabatu za udostępnienie. Ustawiasz „Typ rabatu” na „Procentowy” i „Wartość rabatu” na `15`.

-   **Minimalna kwota zamówienia dla rabatu:**
    -   **Co robi to ustawienie:** Ustawia minimalną całkowitą kwotę zamówienia (przed wysyłką), którą klient musi spełnić, aby użyć wygenerowanego kodu rabatowego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzona jest wartość (np. `50.00`):* Kod rabatowy będzie ważny tylko wtedy, gdy całkowita kwota koszyka klienta jest równa lub większa od tej kwoty.
        -   *Gdy pozostawione puste lub ustawione na `0`:* Kod rabatowy może być użyty do dowolnego zamówienia, niezależnie od jego całkowitej wartości.
    -   **Zalecana wartość:** Wartość, która zachęca klientów do dodawania większej liczby produktów do koszyka, lub `0`, jeśli nie chcesz żadnego minimum.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zapobiec używaniu 10% rabatu na produkt za 1 zł, możesz ustawić minimalną kwotę na `25.00 zł`.

-   **Ważność kodu rabatowego (w dniach):**
    -   **Co robi to ustawienie:** Określa, ile dni wygenerowany kod rabatowy będzie ważny od momentu jego wydania.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzona jest wartość (np. `7`):* Kod rabatowy wygaśnie po 7 dniach, tworząc poczucie pilności.
        -   *Gdy pozostawione puste lub ustawione na `0`:* Kod rabatowy nie będzie miał daty ważności (niezalecane, ponieważ zmniejsza to pilność).
    -   **Zalecana wartość:** `7` do `30` dni, aby zachęcić do szybkiego użycia.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci szybko wykorzystali swój rabat. Ustawienie tego na `7` dni zachęci ich do dokonania zakupu w ciągu tygodnia.

-   **Prefiks kodu rabatowego:**
    -   **Co robi to ustawienie:** Pozwala dodać niestandardowy prefiks do wszystkich generowanych kodów rabatowych. Pomaga to zidentyfikować kody wygenerowane przez ten moduł w zarządzaniu rabatami w PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzony jest prefiks (np. `FBSHARE-`):* Wszystkie generowane kody będą zaczynać się od tego prefiksu (np. `FBSHARE-XYZ123`).
        -   *Gdy pozostawione puste:* Kody będą generowane bez określonego prefiksu.
    -   **Zalecana wartość:** Krótki, opisowy prefiks (np. `FB-`, `SHARE-`, `SOCIAL-`).
    -   **Scenariusz / przykład dla sprzedawcy:** Aby łatwo śledzić sukces kampanii udostępniania na Facebooku, możesz użyć `FB2023-` jako prefiksu.

-   **Wyświetl przycisk udostępniania na:**
    -   **Co robi to ustawienie:** Określa, gdzie przycisk udostępniania na Facebooku pojawi się na stronach Twoich produktów. Zazwyczaj jest to lista rozwijana lub wybór przycisków radiowych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Nagłówek:* Przycisk pojawia się w nagłówku sklepu (mniej typowe dla udostępnień specyficznych dla produktu).
        -   *Kolumny (Lewa/Prawa):* Przycisk pojawia się w jednej z bocznych kolumn.
        -   *Strona produktu (Główna treść):* Przycisk pojawia się w głównym obszarze informacji o produkcie (najczęściej i zalecane).
        -   *Stopka:* Przycisk pojawia się w stopce sklepu.
    -   **Zalecana wartość:** „Strona produktu (Główna treść)” dla maksymalnej widoczności i trafności.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby przycisk udostępniania był łatwo zauważalny tuż obok obrazu produktu i opisu. Wybranie „Strona produktu (Główna treść)” to zapewnia.

-   **Tekst przycisku udostępniania:**
    -   **Co robi to ustawienie:** Pozwala dostosować tekst wyświetlany na przycisku udostępniania na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzony jest tekst (np. „Udostępnij i otrzymaj rabat!”):* Przycisk wyświetli Twój niestandardowy tekst.
        -   *Gdy pozostawione puste:* Zostanie użyty domyślny tekst (np. „Udostępnij na Facebooku”).
    -   **Zalecana wartość:** Jasny, zorientowany na działanie tekst, który podkreśla korzyść (np. „Udostępnij, aby otrzymać rabat!”, „Otrzymaj X% zniżki – Udostępnij teraz!”).
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zachęcić klientów, możesz zmienić tekst przycisku na „Udostępnij i odblokuj swój rabat!”.

-   **Tytuł wiadomości popup:**
    -   **Co robi to ustawienie:** Ustawia tytuł wyskakującego okna, które pojawia się po pomyślnym udostępnieniu, wyświetlając kod rabatowy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzony jest tytuł (np. „Gratulacje!”):* Wyskakujące okno wyświetli Twój niestandardowy tytuł.
        -   *Gdy pozostawione puste:* Zostanie użyty domyślny tytuł.
    -   **Zalecana wartość:** Powitalny i gratulacyjny tytuł (np. „Twój kod rabatowy!”, „Dziękujemy za udostępnienie!”).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klient poczuł się nagrodzony, więc ustawiasz tytuł na „Oto Twój ekskluzywny rabat!”.

-   **Treść wiadomości popup:**
    -   **Co robi to ustawienie:** Pozwala dostosować główną treść tekstową w wyskakującym oknie z kodem rabatowym. Możesz dołączyć instrukcje lub dodatkowe wiadomości.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzona jest treść:* Wyskakujące okno wyświetli Twoją niestandardową wiadomość.
        -   *Gdy pozostawione puste:* Zostanie użyta domyślna wiadomość.
    -   **Zalecana wartość:** Jasna wiadomość instruująca klienta, aby skopiował kod i jak go użyć (np. „Skopiuj ten kod i zastosuj go przy kasie, aby otrzymać rabat.”).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz przypomnieć klientom, gdzie użyć kodu: „Dziękujemy za udostępnienie! Użyj poniższego kodu przy kasie, aby skorzystać z oszczędności.”

#### **Ustawienia zaawansowane (jeśli dostępne)**

-   **Arkusz stylów CSS dla przycisku/popupu:**
    -   **Co robi to ustawienie:** Pozwala wybrać lub wprowadzić niestandardowy CSS, aby stylizować przycisk udostępniania i/lub wyskakujące okno z rabatem, aby lepiej pasowały do Twojego motywu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy zastosowany jest niestandardowy CSS:* Wygląd wizualny (kolory, czcionki, rozmiary) przycisku i popupu zmieni się zgodnie z Twoimi stylami.
        -   *Gdy używany jest domyślny:* Moduł użyje swojego wbudowanego stylu.
    -   **Zalecana wartość:** Początkowo pozostaw puste, a następnie dostosuj, jeśli domyślne style nie pasują do Twojej marki.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój sklep używa określonego odcienia niebieskiego dla przycisków. Możesz dodać tutaj regułę CSS, aby zmienić kolor tła przycisku udostępniania na ten odcień.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Konfiguracja modułu | Włącz / Wyłącz moduł | TAK | Aktywuje/dezaktywuje wszystkie funkcje modułu. |
| | ID aplikacji Facebooka | Twój ID aplikacji | Łączy Twój sklep z Twoją aplikacją Facebooka w celu śledzenia udostępnień. |
| | Typ rabatu | Procentowy | Określa, czy rabat jest procentowy, czy stałą kwotą. |
| | Wartość rabatu | np. 10 (dla 10%) | Rzeczywista wartość oferowanego rabatu. |
| | Minimalna kwota zamówienia dla rabatu | 0 (bez minimum) | Ustawia minimalną wartość zamówienia dla użycia kodu rabatowego. |
| | Ważność kodu rabatowego (w dniach) | 7-30 dni | Ustawia okres ważności dla generowanych kodów rabatowych. |
| | Prefiks kodu rabatowego | FB- | Dodaje niestandardowy prefiks do generowanych kodów dla łatwej identyfikacji. |
| | Wyświetl przycisk udostępniania na | Strona produktu (Główna treść) | Kontroluje umiejscowienie przycisku udostępniania na stronach produktów. |
| | Tekst przycisku udostępniania | Udostępnij, aby otrzymać rabat! | Dostosowuje tekst wyświetlany na przycisku udostępniania. |
| | Tytuł wiadomości popup | Twój kod rabatowy! | Ustawia tytuł wyskakującego okna z kodem rabatowym. |
| | Treść wiadomości popup | Skopiuj ten kod... | Dostosowuje główną wiadomość w wyskakującym oknie z kodem rabatowym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przycisk udostępniania na Facebooku nie pojawia się na stronach moich produktów.**
**O1:**
*   **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w ustawieniach konfiguracji.
*   **Zweryfikuj ID aplikacji Facebooka:** Dokładnie sprawdź, czy Twój ID aplikacji Facebooka jest poprawnie wprowadzony w konfiguracji modułu. Nieprawidłowy lub brakujący ID uniemożliwi załadowanie przycisku.
*   **Sprawdź umiejscowienie przycisku:** Upewnij się, że ustawienie „Wyświetl przycisk udostępniania na” jest poprawnie wybrane (np. „Strona produktu (Główna treść)”). Jeśli Twój motyw ma mocno dostosowane hooki, może być konieczne wypróbowanie różnych miejsc lub skonsultowanie się z programistą.
*   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty oraz wszystkie pamięci podręczne. Czasami stare pliki pamięci podręcznej uniemożliwiają pojawienie się nowych elementów modułu.

**P2: Klienci udostępniają, ale nie otrzymują kodu rabatowego.**
**O2:**
*   **ID aplikacji Facebooka:** To najczęstsza przyczyna. Moduł opiera się na ID aplikacji Facebooka do śledzenia udanych udostępnień. Upewnij się, że jest on poprawny i że Twoja aplikacja Facebooka jest prawidłowo skonfigurowana (np. dodany adres URL witryny).
*   **Uprawnienia/Prywatność Facebooka:** Czasami ustawienia prywatności Facebooka klienta lub blokery reklam w przeglądarce mogą zakłócać śledzenie udostępnień. Jest to mniej powszechne, ale może się zdarzyć.
*   **Konfiguracja modułu:** Przejrzyj wszystkie ustawienia związane z rabatami (Typ rabatu, Wartość, Ważność). Upewnij się, że są ustawione na prawidłowe wartości.
*   **Ustawienia kuponów PrestaShop:** Upewnij się, że ogólne ustawienia kuponów/reguł koszyka w Twoim sklepie PrestaShop nie uniemożliwiają tworzenia nowych kodów (np. osiągnięta maksymalna liczba kuponów, choć jest to rzadkie).

**P3: Wyskakujące okno z kodem rabatowym wygląda dziwnie lub nie pasuje do wyglądu mojego sklepu.**
**O3:**
*   **Konflikty motywów:** Twój niestandardowy motyw PrestaShop może mieć sprzeczne style CSS.
*   **CSS modułu:** Moduł zawiera własny CSS. Możesz spróbować go nadpisać.
*   **Rozwiązanie:** W konfiguracji modułu poszukaj opcji „Niestandardowy CSS” lub „Arkusz stylów”. Może być konieczne dodanie tam niestandardowych reguł CSS, aby dostosować wygląd wyskakującego okna. Jeśli nie czujesz się komfortowo z CSS, webmaster lub programista może pomóc. Wyczyść pamięć podręczną przeglądarki, co czasami może rozwiązać drobne problemy z wyświetlaniem.

**P4: Czy mogę przetłumaczyć tekst przycisku i wiadomości popup na inne języki?**
**O4:** Tak, system tłumaczeń PrestaShop obsługuje tłumaczenia modułów.
*   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym.
*   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz swój język.
*   Znajdź moduł „Udostępnianie produktu na Facebooku + kod rabatowy” i możesz przetłumaczyć wszystkie teksty widoczne dla użytkownika, w tym tekst przycisku i wiadomości popup.

**P5: Co jeśli klient udostępni produkt wiele razy? Czy otrzyma wiele rabatów?**
**O5:** Moduł jest zaprojektowany tak, aby wydawać unikalny kod rabatowy na *każde udane zdarzenie udostępnienia* dla danego użytkownika. Jednak w zależności od dokładnej implementacji, użytkownik może być w stanie udostępniać różne produkty i otrzymywać wiele kodów. Zazwyczaj najlepszą praktyką jest zachęcanie do unikalnych udostępnień za unikalne nagrody. Jeśli chcesz ograniczyć to do jednego kodu na klienta, niezależnie od udostępnień, może być konieczne niestandardowe opracowanie lub ręczne zarządzanie wygenerowanymi kuponami.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Udostępnianie produktu na Facebooku + kod rabatowy” dla programistów i webmasterów.

### 4.1 Przegląd architektury
Moduł wykorzystuje standardową architekturę modułów PrestaShop, głównie wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji. Integruje się z front-office za pomocą hooków do wyświetlania przycisku udostępniania i wykorzystuje AJAX do obsługi generowania kodu rabatowego po udostępnieniu. Podstawowa logika tworzenia kuponów jest prawdopodobnie hermetyzowana w głównej klasie modułu lub pomocniku.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wydaje się używać dedykowanych plików `ModuleFrontController` ani `AdminController` w katalogu `controllers/` na podstawie dostarczonego spisu. Interakcje AJAX w front-office są prawdopodobnie obsługiwane bezpośrednio w głównym pliku modułu (`ajax_productlike.php`) lub za pośrednictwem ogólnego dyspozytora AJAX PrestaShop.

### 4.3 Główne klasy i modele (`classes/`)
Na podstawie dostarczonego spisu, w katalogu `classes/` nie ma zdefiniowanych niestandardowych klas `ObjectModel`. Moduł prawdopodobnie zarządza swoją konfiguracją bezpośrednio za pomocą `Configuration::get()` i `Configuration::updateValue()` oraz tworzy obiekty `CartRule` PrestaShop dla rabatów.

### 4.4 Zasoby JavaScript (`views/js/`)
Moduł zawiera kilka plików JavaScript, wskazujących na logikę po stronie klienta dla interakcji z Facebookiem i wyświetlania popupów.

-   `productlike/js/productlike.js`:
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Prawdopodobnie obsługuje podstawową logikę inicjowania okna dialogowego udostępniania na Facebooku, nasłuchiwania na zdarzenie zakończenia udostępniania z SDK Facebooka, a następnie wykonywania wywołania AJAX z powrotem do sklepu PrestaShop w celu żądania kodu rabatowego. Zarządzałby również wyświetlaniem wyskakującego okna z kodem rabatowym.
    *   **Kluczowe funkcjonalności:** Inicjalizacja SDK Facebooka, wywołania metody `FB.ui` do udostępniania, żądania AJAX do backendu modułu, manipulacja DOM w celu wyświetlania popupu.

-   `productlike/js/script.js`:
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Może to być ogólny skrypt narzędziowy lub alternatywa dla `productlike.js`. Może zawierać słuchacze zdarzeń dla kliknięcia przycisku udostępniania lub obsługiwać logikę wyświetlania/ukrywania wyskakującego okna z rabatem.
    *   **Kluczowe funkcjonalności:** Wiązanie zdarzeń, potencjalnie proste animacje lub manipulacja DOM.

-   `productlike/lib/voucherengine/script.js`:
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Sugeruje dedykowany skrypt do wyświetlania i interakcji z kuponami. Może obsługiwać kopiowanie kodu kuponu do schowka, zamykanie wyskakującego okna lub inne elementy interfejsu użytkownika związane z rabatem.
    *   **Kluczowe funkcjonalności:** Interakcja z API schowka, zdarzenia zamykania popupu, informacje zwrotne UI.

### 4.5 Arkusze stylów CSS (`views/css/`)
Moduł używa kilku plików CSS do stylizowania swoich komponentów front-office.

-   `productlike/css/css.css`:
    *   **Zakres:** Stylizacja front-office dla klienta.
    *   **Odpowiedzialność:** Zawiera ogólne style dla przycisku udostępniania na Facebooku i potencjalnie wyskakującego okna z kodem rabatowym.
    *   **Kluczowe selektory:** `.productlike-button`, `.productlike-popup`, `.productlike-voucher-code`. Programiści mogą je nadpisać w pliku `custom.css` swojego motywu lub za pomocą niestandardowego wejścia CSS modułu, jeśli jest dostępne.

-   `productlike/css.css`:
    *   **Zakres:** Stylizacja front-office dla klienta.
    *   **Odpowiedzialność:** Potencjalnie starszy lub alternatywny arkusz stylów, lub specyficzne style dla niektórych elementów nieobjętych przez `css.css`.
    *   **Kluczowe selektory:** Podobne do `css.css`, w zależności od jego zawartości.

-   `productlike/lib/voucherengine/ps16.css`:
    *   **Zakres:** Stylizacja front-office dla klienta, specjalnie dla kompatybilności z PrestaShop 1.6.
    *   **Odpowiedzialność:** Zapewnia dostosowania stylów, aby wyskakujące okno z kuponem i przycisk wyglądały poprawnie w motywach PrestaShop 1.6, które mogą mieć inne domyślne style elementów.
    *   **Kluczowe selektory:** Prawdopodobnie celuje w typowe elementy interfejsu użytkownika PrestaShop 1.6, aby zapewnić spójność wizualną.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Moduł wykorzystuje szablony Smarty do renderowania swoich komponentów front-office.

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `productlike/header.tpl`:
        *   **Hook:** `displayHeader`
        *   **Cel:** Ten szablon jest prawdopodobnie odpowiedzialny za inicjalizację SDK JavaScript Facebooka, ładowanie niezbędnych plików JavaScript i potencjalnie przekazywanie zmiennych konfiguracyjnych (takich jak ID aplikacji Facebooka) z backendu modułu do front-endowego JavaScriptu. Zapewnia, że API Facebooka jest gotowe przed renderowaniem przycisku udostępniania.
    *   `productlike/share.tpl`:
        *   **Hook:** `displayProductButtons`, `displayRightColumnProduct`, `displayLeftColumnProduct`, `displayFooterProduct` (lub podobne hooki strony produktu, w zależności od konfiguracji).
        *   **Cel:** Renderuje rzeczywisty przycisk „Udostępnij na Facebooku” na stronie produktu. Będzie zawierał strukturę HTML dla przycisku i potencjalnie placeholder dla wyskakującego okna z kodem rabatowym, który jest następnie dynamicznie wypełniany przez JavaScript.

-   **Szablony administracyjne (`views/templates/admin/`)**: Żadne nie są wyraźnie wymienione, co oznacza, że konfiguracja jest obsługiwana bezpośrednio przez `getContent()` w głównym pliku modułu.

-   **Szablony front-office (`views/templates/front/`)**: Żadne nie są wyraźnie wymienione, ponieważ główna interakcja odbywa się za pośrednictwem hooków i popupów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł prawdopodobnie nie tworzy niestandardowych tabel bazy danych.
    *   Ustawienia konfiguracji (ID aplikacji Facebooka, wartości rabatów itp.) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `PRODUCTLIKE_FACEBOOK_APP_ID`, `PRODUCTLIKE_DISCOUNT_TYPE`, `PRODUCTLIKE_DISCOUNT_VALUE` itp.
    *   Wygenerowane kody rabatowe to standardowe wpisy `CartRule` PrestaShop, przechowywane w `ps_cart_rule` i powiązanych tabelach.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Inicjalizuje SDK Facebooka, ładuje JS/CSS modułu, przekazuje zmienne konfiguracyjne. |
| `displayProductButtons` | Na stronie produktu, zazwyczaj w pobliżu przycisku „Dodaj do koszyka”. | Renderuje przycisk udostępniania na Facebooku. (Powszechne dla PS 1.7+) |
| `displayRightColumnProduct` | W prawej kolumnie strony produktu. | Renderuje przycisk udostępniania na Facebooku (jeśli skonfigurowano). |
| `displayLeftColumnProduct` | W lewej kolumnie strony produktu. | Renderuje przycisk udostępniania na Facebooku (jeśli skonfigurowano). |
| `displayFooterProduct` | W obszarze stopki strony produktu. | Renderuje przycisk udostępniania na Facebooku (jeśli skonfigurowano). |
| `displayProductExtraContent` | Na stronie produktu, dla dodatkowych zakładek/bloków treści. | Alternatywny hook do umieszczania przycisków (PS 1.7+). |
| `actionFrontControllerSetMedia` | Przed renderowaniem strony przez kontroler front-end. | Rejestruje pliki JS i CSS modułu. |
| `actionObjectCartRuleAddAfter` | Po dodaniu nowej reguły koszyka (kuponu). | Potencjalnie używane do logowania lub dalszego przetwarzania wygenerowanych kuponów. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Udostępnianie produktu na Facebooku + kod rabatowy”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół jest zaangażowany w świadczenie pomocy i zapewnienie optymalnego działania modułu.
