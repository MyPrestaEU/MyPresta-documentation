---
title: "Punkty lojalnościowe – Zasady stażu (seniority) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Punkty lojalnościowe – Zasady stażu (seniority)” od MyPresta.eu."
sidebar:
  label: "Punkty lojalnościowe – Zasady stażu (seniority) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Loyalty points – Tenure (seniority) rules na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-tenure-seniority-rules.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/loyalty-points-tenure-seniority-rules/)
>
> ---


# Punkty lojalnościowe – Zasady stażu (seniority)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w większości środowisk hostingowych. Ten moduł nie ma dodatkowych specyficznych wymagań poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

**Ustawienia ogólne**

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji całej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Moduł rozpocznie przetwarzanie reguł lojalnościowych na podstawie stażu klienta i przyznawanie punktów zgodnie z konfiguracją.
        -   *Po wyłączeniu:* Moduł przestanie działać. Żadne nowe punkty nie zostaną przyznane na podstawie reguł stażu, a istniejące reguły zostaną zignorowane do czasu ponownego włączenia.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś konfigurację reguł i jesteś gotowy do uruchomienia programu lojalnościowego. Włącz to, aby rozpocząć nagradzanie klientów. Jeśli musisz tymczasowo wstrzymać program w celu konserwacji lub przeglądu, możesz go tutaj wyłączyć.
-   **URL zadania Cron:**

    -   **Co robi to ustawienie:** Wyświetla unikalny adres URL, który należy skonfigurować jako „zadanie cron” na serwerze WWW. Zadanie cron to zaplanowane zadanie, które nakazuje serwerowi automatyczne uruchamianie tego adresu URL w regularnych odstępach czasu (np. raz dziennie). W ten sposób moduł sprawdza staż klienta i przyznaje punkty bez konieczności ręcznego wyzwalania.
    -   **Efekt zmiany tego ustawienia:** Nie można bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł.
        -   *Po prawidłowym skonfigurowaniu jako zadanie cron:* Moduł automatycznie uruchomi swoje sprawdzenia i przyzna punkty zgodnie z Twoimi regułami.
        -   *Po NIE skonfigurowaniu jako zadanie cron:* Automatyczne przyznawanie punktów przez moduł nie nastąpi. Musiałbyś ręcznie odwiedzić ten adres URL w przeglądarce, aby wywołać proces, co niweczy cel automatyzacji.
    -   **Zalecana wartość:** Skopiuj ten adres URL i ustaw go jako codzienne zadanie cron na swoim serwerze.
    -   **Scenariusz / przykład dla sprzedawcy:** Po zainstalowaniu modułu skopiuj ten adres URL. Przejdź do panelu sterowania hostingu (np. cPanel, Plesk) i znajdź sekcję „Zadania Cron” lub „Zaplanowane zadania”. Dodaj nowe zadanie cron, aby wykonywać ten adres URL raz na 24 godziny. Zapewni to, że Twoi klienci otrzymają punkty za staż automatycznie i na czas.

### 2.2 Dedykowany ekran administracyjny: Reguły stażu lojalnościowego (Panel administracyjny > MyPresta.eu > Reguły stażu lojalnościowego)

Ten ekran umożliwia definiowanie i zarządzanie konkretnymi regułami przyznawania punktów lojalnościowych na podstawie stażu klienta.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran można znaleźć, przechodząc do **MyPresta.eu > Reguły stażu lojalnościowego** w menu Panelu administracyjnego PrestaShop.
-   **Dostępne akcje i ustawienia:**

    -   **Tabela z listą reguł:** Ta tabela wyświetla wszystkie Twoje aktywne i nieaktywne reguły stażu. Dla każdej reguły zobaczysz:
        -   **ID:** Unikalny identyfikator reguły.
        -   **Staż (Dni):** Minimalna liczba dni, przez jaką klient musi być zarejestrowany, aby kwalifikować się do tej reguły.
        -   **Punkty do przyznania:** Liczba punktów lojalnościowych, które otrzyma klient.
        -   **Aktywna:** Przełącznik do włączania lub wyłączania reguły.
        -   **Akcje:** Przyciski „Edytuj” lub „Usuń” regułę.
    -   **Przycisk „Dodaj nową regułę”:** Kliknij ten przycisk, aby utworzyć nową regułę stażu.

    **Podczas dodawania/edycji reguły:**
    Zostanie wyświetlony formularz do zdefiniowania parametrów reguły:

    -   **Staż (Dni):**

        -   **Co robi to ustawienie:** Jest to minimalna liczba dni, przez jaką klient musi być zarejestrowany w Twoim sklepie, aby kwalifikować się do tego konkretnego przyznania punktów lojalnościowych.
        -   **Efekt zmiany tego ustawienia:**
            -   *Ustawienie na 365:* Klienci zarejestrowani od co najmniej jednego roku będą kwalifikować się.
            -   *Ustawienie na 730:* Klienci zarejestrowani od co najmniej dwóch lat będą kwalifikować się.
        -   **Zalecana wartość:** Wybierz wartości, które reprezentują znaczące kamienie milowe dla Twoich klientów (np. 365 dni na 1 rok, 730 dni na 2 lata, 1095 dni na 3 lata).
        -   **Scenariusz / przykład dla sprzedawcy:** Chcesz nagrodzić klientów, którzy są z Twoim sklepem od co najmniej jednego roku. Ustawisz to na `365`.
    -   **Punkty do przyznania:**

        -   **Co robi to ustawienie:** Jest to dokładna liczba punktów lojalnościowych, które zostaną przyznane klientowi, który spełnia wymagania „Stażu (Dni)” dla tej reguły.
        -   **Efekt zmiany tego ustawienia:**
            -   *Ustawienie na 100:* Kwalifikujący się klienci otrzymują 100 punktów lojalnościowych.
            -   *Ustawienie na 50:* Kwalifikujący się klienci otrzymują 50 punktów lojalnościowych.
        -   **Zalecana wartość:** Dopasuj to do wartości Twojego istniejącego programu punktów lojalnościowych. Dobrym punktem wyjścia mogą być punkty odpowiadające niewielkiej zniżce (np. 5-10% średniej wartości zamówienia).
        -   **Scenariusz / przykład dla sprzedawcy:** Aby wyrazić znaczące podziękowanie za rok lojalności, możesz przyznać `250` punktów, co może przełożyć się na zniżkę 5 € na ich następny zakup.
    -   **Aktywna:**

        -   **Co robi to ustawienie:** Ten przełącznik określa, czy ta konkretna reguła jest obecnie aktywna i będzie brana pod uwagę przez moduł podczas przyznawania punktów.
        -   **Efekt zmiany tego ustawienia:**
            -   *Po włączeniu:* Reguła zostanie przetworzona przez zadanie cron, a punkty zostaną przyznane kwalifikującym się klientom.
            -   *Po wyłączeniu:* Reguła zostanie zignorowana, a żadne punkty nie zostaną przyznane na podstawie tego konkretnego progu stażu.
        -   **Zalecana wartość:** TAK (dla reguł, które chcesz, aby były aktywne).
        -   **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś regułę dla 5 lat stażu, ale chcesz ją przetestować wewnętrznie, zanim ją uruchomisz. Możesz ją pozostawić wyłączoną, dopóki nie będziesz gotowy do jej aktywacji.
-   **Efekt zmian:**

    -   Dodanie nowej reguły tworzy nowy wpis w bazie danych, który będzie sprawdzany przez zadanie cron modułu.
    -   Edycja reguły modyfikuje jej parametry (staż, punkty, status aktywności), wpływając na przyszłe przyznawanie punktów.
    -   Usunięcie reguły trwale ją usuwa, a żadne dalsze punkty nie zostaną przyznane na podstawie tego konkretnego stażu.
    -   Klucz konfiguracji `PS_LIST_LIMIT` kontroluje liczbę elementów wyświetlanych na stronie w tabeli z listą reguł.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zaplanuj swoje poziomy lojalności:** Zdecyduj, jakie kamienie milowe stażu chcesz nagradzać (np. 1 rok, 2 lata, 5 lat).
    2.  **Oblicz wartości punktów:** Określ, ile punktów chcesz przyznać za każdy poziom, biorąc pod uwagę wartość pieniężną Twoich punktów lojalnościowych.
    3.  **Utwórz reguły:** Przejdź do **MyPresta.eu > Reguły stażu lojalnościowego** i kliknij „Dodaj nową regułę” dla każdego poziomu.
    4.  **Monitoruj:** Okresowo sprawdzaj salda punktów lojalnościowych klientów i upewnij się, że zadanie cron działa poprawnie.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ
Moduł „Punkty lojalnościowe – Zasady stażu (seniority)” został zaprojektowany, aby nagradzać Twoich klientów punktami lojalnościowymi na podstawie czasu, przez jaki są zarejestrowani w Twoim sklepie PrestaShop. Pomaga to rozpoznawać i zatrzymywać najbardziej lojalnych klientów, automatycznie przyznając im punkty bonusowe, gdy osiągną określone kamienie milowe „stażu” (np. 1 rok, 2 lata, 5 lat od rejestracji).

## 3. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w większości środowisk hostingowych. Ten moduł nie ma dodatkowych specyficznych wymagań poza standardową konfiguracją PrestaShop.

## 4. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 4.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

**Ustawienia ogólne**

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji całej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Moduł rozpocznie przetwarzanie reguł lojalnościowych na podstawie stażu klienta i przyznawanie punktów zgodnie z konfiguracją.
        -   *Po wyłączeniu:* Moduł przestanie działać. Żadne nowe punkty nie zostaną przyznane na podstawie reguł stażu, a istniejące reguły zostaną zignorowane do czasu ponownego włączenia.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś konfigurację reguł i jesteś gotowy do uruchomienia programu lojalnościowego. Włącz to, aby rozpocząć nagradzanie klientów. Jeśli musisz tymczasowo wstrzymać program w celu konserwacji lub przeglądu, możesz go tutaj wyłączyć.
-   **URL zadania Cron:**

    -   **Co robi to ustawienie:** Wyświetla unikalny adres URL, który należy skonfigurować jako „zadanie cron” na serwerze WWW. Zadanie cron to zaplanowane zadanie, które nakazuje serwerowi automatyczne uruchamianie tego adresu URL w regularnych odstępach czasu (np. raz dziennie). W ten sposób moduł sprawdza staż klienta i przyznaje punkty bez konieczności ręcznego wyzwalania.
    -   **Efekt zmiany tego ustawienia:** Nie można bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł.
        -   *Po prawidłowym skonfigurowaniu jako zadanie cron:* Moduł automatycznie uruchomi swoje sprawdzenia i przyzna punkty zgodnie z Twoimi regułami.
        -   *Po NIE skonfigurowaniu jako zadanie cron:* Moduł’s automatyczne przyznawanie punktów nie nastąpi. Musiałbyś ręcznie odwiedzić ten adres URL w przeglądarce, aby wywołać proces, co niweczy cel automatyzacji.
    -   **Zalecana wartość:** Skopiuj ten adres URL i ustaw go jako codzienne zadanie cron na swoim serwerze.
    -   **Scenariusz / przykład dla sprzedawcy:** Po zainstalowaniu modułu skopiuj ten adres URL. Przejdź do panelu sterowania hostingu (np. cPanel, Plesk) i znajdź sekcję „Zadania Cron” lub „Zaplanowane zadania”. Dodaj nowe zadanie cron, aby wykonywać ten adres URL raz na 24 godziny. Zapewni to, że Twoi klienci otrzymają punkty za staż automatycznie i na czas.

### 4.2 Dedykowany ekran administracyjny: Reguły stażu lojalnościowego (Panel administracyjny > MyPresta.eu > Reguły stażu lojalnościowego)

Ten ekran umożliwia definiowanie i zarządzanie konkretnymi regułami przyznawania punktów lojalnościowych na podstawie stażu klienta.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran można znaleźć, przechodząc do **MyPresta.eu > Reguły stażu lojalnościowego** w menu Panelu administracyjnego PrestaShop.
-   **Dostępne akcje i ustawienia:**

    -   **Tabela z listą reguł:** Ta tabela wyświetla wszystkie Twoje aktywne i nieaktywne reguły stażu. Dla każdej reguły zobaczysz:
        -   **ID:** Unikalny identyfikator reguły.
        -   **Staż (Dni):** Minimalna liczba dni, przez jaką klient musi być zarejestrowany, aby kwalifikować się do tej reguły.
        -   **Punkty do przyznania:** Liczba punktów lojalnościowych, które otrzyma klient.
        -   **Aktywna:** Przełącznik do włączania lub wyłączania reguły.
        -   **Akcje:** Przyciski „Edytuj” lub „Usuń” regułę.
    -   **Przycisk „Dodaj nową regułę”:** Kliknij ten przycisk, aby utworzyć nową regułę stażu.

    **Podczas dodawania/edycji reguły:**
    Zostanie wyświetlony formularz do zdefiniowania parametrów reguły:

    -   **Staż (Dni):**

        -   **Co robi to ustawienie:** Jest to minimalna liczba dni, przez jaką klient musi być zarejestrowany w Twoim sklepie, aby kwalifikować się do tego konkretnego przyznania punktów lojalnościowych.
        -   **Efekt zmiany tego ustawienia:**
            -   *Ustawienie na 365:* Klienci zarejestrowani od co najmniej jednego roku będą kwalifikować się.
            -   *Ustawienie na 730:* Klienci zarejestrowani od co najmniej dwóch lat będą kwalifikować się.
        -   **Zalecana wartość:** Wybierz wartości, które reprezentują znaczące kamienie milowe dla Twoich klientów (np. 365 dni na 1 rok, 730 dni na 2 lata, 1095 dni na 3 lata).
        -   **Scenariusz / przykład dla sprzedawcy:** Chcesz nagrodzić klientów, którzy są z Twoim sklepem od co najmniej jednego roku. Ustawisz to na `365`.
    -   **Punkty do przyznania:**

        -   **Co robi to ustawienie:** Jest to dokładna liczba punktów lojalnościowych, które zostaną przyznane klientowi, który spełnia wymagania „Stażu (Dni)” dla tej reguły.
        -   **Efekt zmiany tego ustawienia:**
            -   *Ustawienie na 100:* Kwalifikujący się klienci otrzymują 100 punktów lojalnościowych.
            -   *Ustawienie na 50:* Kwalifikujący się klienci otrzymują 50 punktów lojalnościowych.
        -   **Zalecana wartość:** Dopasuj to do wartości Twojego istniejącego programu punktów lojalnościowych. Dobrym punktem wyjścia mogą być punkty odpowiadające niewielkiej zniżce (np. 5-10% średniej wartości zamówienia).
        -   **Scenariusz / przykład dla sprzedawcy:** Aby wyrazić znaczące podziękowanie za rok lojalności, możesz przyznać `250` punktów, co może przełożyć się na zniżkę 5 € na ich następny zakup.
    -   **Aktywna:**

        -   **Co robi to ustawienie:** Ten przełącznik określa, czy ta konkretna reguła jest obecnie aktywna i będzie brana pod uwagę przez moduł podczas przyznawania punktów.
        -   **Efekt zmiany tego ustawienia:**
            -   *Po włączeniu:* Reguła zostanie przetworzona przez zadanie cron, a punkty zostaną przyznane kwalifikującym się klientom.
            -   *Po wyłączeniu:* Reguła zostanie zignorowana, a żadne punkty nie zostaną przyznane na podstawie tego konkretnego progu stażu.
        -   **Zalecana wartość:** TAK (dla reguł, które chcesz, aby były aktywne).
        -   **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś regułę dla 5 lat stażu, ale chcesz ją przetestować wewnętrznie, zanim ją uruchomisz. Możesz ją pozostawić wyłączoną, dopóki nie będziesz gotowy do jej aktywacji.
-   **Efekt zmian:**

    -   Dodanie nowej reguły tworzy nowy wpis w bazie danych, który będzie sprawdzany przez zadanie cron modułu.
    -   Edycja reguły modyfikuje jej parametry (staż, punkty, status aktywności), wpływając na przyszłe przyznawanie punktów.
    -   Usunięcie reguły trwale ją usuwa, a żadne dalsze punkty nie zostaną przyznane na podstawie tego konkretnego stażu.
    -   Klucz konfiguracji `PS_LIST_LIMIT` kontroluje liczbę elementów wyświetlanych na stronie w tabeli z listą reguł.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zaplanuj swoje poziomy lojalności:** Zdecyduj, jakie kamienie milowe stażu chcesz nagradzać (np. 1 rok, 2 lata, 5 lat).
    2.  **Oblicz wartości punktów:** Określ, ile punktów chcesz przyznać za każdy poziom, biorąc pod uwagę wartość pieniężną Twoich punktów lojalnościowych.
    3.  **Utwórz reguły:** Przejdź do **MyPresta.eu > Reguły stażu lojalnościowego** i kliknij „Dodaj nową regułę” dla każdego poziomu.
    4.  **Monitoruj:** Okresowo sprawdzaj salda punktów lojalnościowych klientów i upewnij się, że zadanie cron działa poprawnie.

### 4.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ

## 5. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują punktów lojalnościowych, mimo że ustawiłem reguły.**
O1:

-   **Sprawdź aktywację modułu:** Upewnij się, że ustawienie „Włącz moduł” na głównej stronie konfiguracji jest ustawione na TAK.
-   **Zweryfikuj zadanie Cron:** Najczęstszą przyczyną jest nieprawidłowo skonfigurowane lub niedziałające zadanie cron. Dokładnie sprawdź adres URL zadania Cron na stronie konfiguracji modułu i upewnij się, że jest on prawidłowo skonfigurowany na Twoim serwerze hostingowym do codziennego uruchamiania.
-   **Status reguły:** Upewnij się, że poszczególne reguły stażu lojalnościowego, które utworzyłeś, są oznaczone jako „Aktywne”.
-   **Kwalifikowalność klienta:** Czy klient faktycznie spełnił wymagania „Stażu (Dni)” dla którejkolwiek z Twoich aktywnych reguł? Moduł przyznaje punkty tylko wtedy, gdy klient przekroczy próg.
-   **Pamięć podręczna Smarty:** Czasami pamięć podręczna PrestaShop może powodować problemy z wyświetlaniem. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).

**P2: Jak sprawdzić, czy zadanie cron działa poprawnie?**
O2:

-   **Sprawdź logi hostingu:** Większość dostawców hostingu oferuje możliwość przeglądania logów wykonania zadań cron w panelu sterowania (np. cPanel). Szukaj wpisów związanych z adresem URL zadania cron dostarczonym przez moduł.
-   **Test ręczny:** Możesz ręcznie odwiedzić adres URL zadania Cron w swojej przeglądarce internetowej. Spowoduje to uruchomienie procesu przyznawania punktów w tym momencie. Jeśli punkty zostaną przyznane kwalifikującym się klientom po tej ręcznej wizycie, potwierdza to, że logika modułu działa, a problem dotyczy automatycznej konfiguracji crona.

**P3: Czy mogę przyznać punkty wstecznie klientom, którzy już przekroczyli kamień milowy stażu przed zainstalowaniem modułu?**
O3: Tak, gdy zadanie cron uruchomi się po raz pierwszy po skonfigurowaniu reguł, oceni wszystkich istniejących klientów pod kątem Twoich aktywnych reguł. Jeśli klient spełnia wymagania stażu i nie otrzymał wcześniej punktów za tę konkretną regułę, otrzyma je. Oznacza to, że starsi, lojalni klienci otrzymają zasłużone punkty.

**P4: Mój niestandardowy motyw nie wyświetla poprawnie punktów lojalnościowych lub powiadomienia wyglądają dziwnie.**
O4: Ten moduł przede wszystkim współdziała z podstawowym systemem lojalnościowym PrestaShop. Wszelkie problemy z wyświetlaniem punktów lojalnościowych lub powiadomień są zazwyczaj związane ze stylizacją Twojego motywu lub nadpisaniami dla natywnego modułu lojalnościowego.

-   **Dostosowanie motywu:** Jeśli masz niestandardowy motyw, może on mieć własne szablony lub CSS do wyświetlania informacji o lojalności. Może być konieczne skonsultowanie się z deweloperem motywu lub webmasterem, aby upewnić się, że poprawnie integruje się z funkcjami lojalnościowymi PrestaShop.
-   **Test domyślnego motywu:** Tymczasowo przełącz się na domyślny motyw PrestaShop (Classic), aby sprawdzić, czy problem nadal występuje. Jeśli działa poprawnie na domyślnym motywie, problem jest zdecydowanie związany z Twoim niestandardowym motywem.

**P5: Co się stanie, jeśli zmienię regułę (np. zwiększę punkty) po tym, jak klienci już otrzymali z niej punkty?**
O5: Moduł jest zaprojektowany tak, aby przyznawać punkty *raz* dla każdej reguły, gdy klient po raz pierwszy osiągnie próg stażu. Jeśli zmienisz regułę (np. zwiększysz punkty za 365 dni ze 100 do 150), klienci, którzy już otrzymali 100 punktów za 365 dni, *nie* otrzymają automatycznie dodatkowych 50 punktów. Reguła została już dla nich „spełniona”. Jeśli chcesz im przyznać dodatkowe punkty, musiałbyś ręcznie dostosować ich saldo lojalnościowe lub utworzyć nową, tymczasową regułę.

## 6. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 6.1 Przegląd architektury

Moduł „Punkty lojalnościowe – Zasady stażu (seniority)” (`myprestaloyalty_tenure`) rozszerza funkcjonalność PrestaShop, wprowadzając nową koncepcję przyznawania punktów lojalnościowych na podstawie stażu rejestracji klienta. Opiera się na standardowej architekturze modułu PrestaShop, wykorzystując `ObjectModel` do zarządzania regułami stażu i dedykowany kontroler front-office do wykonywania zadań cron. Moduł integruje się z podstawowym `LoyaltyModule` PrestaShop, aby przyznawać punkty, zapewniając kompatybilność z natywnym systemem lojalnościowym.

### 6.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cron.php`
        -   **Nazwa klasy:** `MyprestaloyaltyTenureCronModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wykonywania za pomocą zadania cron. Po uzyskaniu dostępu, iteruje przez wszystkie aktywne reguły stażu i wszystkich zarejestrowanych klientów. Dla każdego klienta oblicza jego wiek rejestracji i sprawdza, czy kwalifikuje się do którejkolwiek aktywnej reguły, za którą jeszcze nie otrzymał punktów. Jeśli klient się kwalifikuje, przyznaje określone punkty lojalnościowe, korzystając z podstawowej funkcjonalności `LoyaltyModule`. Zazwyczaj zwraca prostą wiadomość o sukcesie lub wynik logu.
    -   `controllers/front/index.php`
        -   **Nazwa klasy:** `MyprestaloyaltyTenureIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Jest to kontroler zastępczy lub domyślny kontroler front-office. W wielu modułach, jeśli nie zdefiniowano konkretnej akcji, `index.php` może obsługiwać domyślny widok lub przekierowanie. Dla tego modułu jego główna interakcja z front-office odbywa się za pośrednictwem kontrolera `cron.php`.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminMyprestaloyaltyTenureController.php`
        -   **Nazwa klasy:** `AdminMyprestaloyaltyTenureController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** „Reguły stażu lojalnościowego” (w menu MyPresta.eu)
        -   **Zarządzana encja:** `MyprestaloyaltyTenureRule` (mapuje na tabelę bazy danych `_myprestaloyalty_tenure_rule`)
        -   **Odpowiedzialność:** Ten kontroler zapewnia interfejs CRUD (Create, Read, Update, Delete) do zarządzania regułami stażu lojalnościowego w Panelu administracyjnym PrestaShop. Wykorzystuje `HelperList` do wyświetlania listy reguł i `HelperForm` do dodawania/edycji poszczególnych reguł. Obsługuje przesyłanie formularzy, walidację i interakcję z `ObjectModel` `MyprestaloyaltyTenureRule`.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy:** (Brak konkretnej klasy, zazwyczaj używana do celów bezpieczeństwa)
        -   **Odpowiedzialność:** Ten plik zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome'); exit;` lub podobne, aby zapobiec bezpośredniemu wyświetlaniu katalogów i zapewnić, że kontrolery administracyjne są dostępne za pośrednictwem dyspozytora PrestaShop.

### 6.3 Klasy i modele podstawowe (`classes/`)

-   `classes/index.php`

    -   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop, zazwyczaj zawierający `header('Location: ../../index.php?controller=AdminHome'); exit;`, aby zapobiec bezpośredniemu dostępowi do katalogu `classes`.
-   `classes/MyprestaloyaltyTenureRule.php`

    -   **Nazwa klasy:** `MyprestaloyaltyTenureRule` (rozszerza `ObjectModel`)
    -   **Tabela bazy danych:** `_myprestaloyalty_tenure_rule`
    -   **Pola `$definition`:**
        -   `id_myprestaloyalty_tenure_rule`: Klucz podstawowy.
        -   `tenure_days`: Liczba całkowita, minimalna liczba dni, przez jaką klient musi być zarejestrowany.
        -   `points_to_award`: Liczba całkowita, liczba punktów lojalnościowych do przyznania.
        -   `active`: Wartość logiczna, czy reguła jest aktywna (0 lub 1).
    -   **Kluczowe metody publiczne:**
        -   `__construct()`: Standardowy konstruktor `ObjectModel`.
        -   `add()`: Nadpisuje `ObjectModel::add()` dla niestandardowej logiki, jeśli jest potrzebna (np. obsługa daty, walidacja).
        -   `update()`: Nadpisuje `ObjectModel::update()`.
        -   `delete()`: Nadpisuje `ObjectModel::delete()`.
        -   `getAllActiveRules()`: Metoda statyczna do pobierania wszystkich aktywnych reguł z bazy danych.
        -   `hasCustomerReceivedPointsForRule($id_customer, $id_rule)`: Metoda statyczna do sprawdzania, czy dany klient otrzymał już punkty za daną regułę. Jest to kluczowe, aby zapobiec podwójnemu przyznawaniu nagród.
        -   `markCustomerAsAwarded($id_customer, $id_rule)`: Metoda statyczna do rejestrowania, że klient otrzymał punkty za regułę.

### 6.4 Zasoby JavaScript (`views/js/`)

Dossier modułu wskazuje, że w `views/js/` nie ma niestandardowych plików JavaScript. Wszystkie interakcje są obsługiwane po stronie serwera lub za pomocą standardowych pomocników formularzy/list PrestaShop.

### 6.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu wskazuje, że w `views/css/` nie ma niestandardowych plików CSS. Interfejs Back Office opiera się na domyślnych stylach motywu administracyjnego PrestaShop.

### 6.6 Struktura szablonów Smarty (`views/templates/`)

Dossier modułu wskazuje, że w `views/templates/` nie ma niestandardowych plików szablonów Smarty. Ekrany konfiguracji modułu i zarządzania regułami są renderowane za pomocą klas `HelperForm` i `HelperList` PrestaShop, które opierają się na podstawowych plikach szablonów PrestaShop.

### 6.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_myprestaloyalty_tenure_rule`: Przechowuje definicje każdej reguły stażu.
        -   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `tenure_days` INT(10) UNSIGNED NOT NULL
        -   `points_to_award` INT(10) UNSIGNED NOT NULL
        -   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        -   PRIMARY KEY (`id_myprestaloyalty_tenure_rule`)
    -   `ps_myprestaloyalty_tenure_awarded`: Rejestruje, którzy klienci otrzymali punkty za które reguły, aby zapobiec podwójnemu przyznawaniu nagród.
        -   `id_myprestaloyalty_tenure_awarded` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_customer` INT(10) UNSIGNED NOT NULL
        -   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL
        -   `date_awarded` DATETIME NOT NULL
        -   PRIMARY KEY (`id_myprestaloyalty_tenure_awarded`)
        -   UNIQUE KEY `customer_rule` (`id_customer`, `id_myprestaloyalty_tenure_rule`)
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie żadnych hooków wyświetlania front-office (takich jak `displayHeader`, `displayRightColumn`, `displayProductExtraContent`, `displayFooter`), ponieważ jego główną funkcją jest przetwarzanie w tle za pomocą crona.
    Niejawnie używa:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionModuleInstall` | Podczas instalacji modułu | Tworzy tabele bazy danych, rejestruje zakładkę administracyjną. |
    | `actionModuleUninstall` | Podczas deinstalacji modułu | Usuwa tabele bazy danych i konfigurację. |
    | `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany | Gdyby moduł miał niestandardowe JS/CSS dla administratora, zarejestrowałby je tutaj. (Nie używane w tym module na podstawie inwentaryzacji) |
    | `displayBackOfficeTop` | Renderuje zawartość na górze Panelu administracyjnego | Używane do wyświetlania adresu URL zadania cron i instrukcji na stronie konfiguracji modułu. |

## 7. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Punkty lojalnościowe – Zasady stażu (seniority)”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i zapewnienie optymalnego działania Twojego modułu.

-   **Dostęp do pobierania i aktualizacji:** Zaloguj się na swoje konto na [MyPresta.eu Historia zamówień i pobieranie](https://mypresta.eu/my-account/orders/).
-   **Skontaktuj się z pomocą techniczną:** Skorzystaj z kanałów wsparcia dostępnych na Twoim koncie MyPresta.eu w przypadku jakichkolwiek problemów technicznych lub pytań.
