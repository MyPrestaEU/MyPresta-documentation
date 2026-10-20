---
title: "Login protection pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Login protection pro od MyPresta.eu."
sidebar:
  label: "Login protection pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Login protection pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/login-protection-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/login-protection-pro/)
>
> ---


# Login protection pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym definiujesz podstawowe zasady ochrony logowania.

- **Lokalizacja w menu:** Panel administracyjny > Moduły > Menedżer modułów > Login protection pro > Konfiguruj

#### Ustawienia i opcje:

1.  **Włącz ochronę logowania:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik modułu. Włącza lub wyłącza cały system ochrony logowania.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł rozpocznie monitorowanie prób logowania, stosując zasady ustawione poniżej.
        -   *Gdy wyłączone:* Moduł będzie nieaktywny, a żadne próby logowania nie będą monitorowane ani blokowane. Twój sklep będzie polegał na domyślnych zabezpieczeniach PrestaShop, które nie obejmują ochrony przed atakami brute-force.
    -   **Zalecana wartość:** **TAK**
    -   **Scenariusz / przykład dla sprzedawcy:** Zawsze utrzymuj to włączone, aby zapewnić ochronę Twojego sklepu. Wyłącz tylko w celu specyficznego debugowania, jeśli zostanie to zlecone przez wsparcie.
2.  **Maksymalna liczba nieudanych prób:**

    -   **Co robi to ustawienie:** Definiuje maksymalną liczbę niepoprawnych prób logowania dozwolonych z jednego adresu IP w określonym przedziale czasowym (zdefiniowanym przez „Okno czasowe prób”) zanim ten adres IP zostanie tymczasowo zablokowany.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawienie niższej liczby (np. 3):* Sprawia, że ochrona jest bardziej agresywna, szybciej blokując podejrzane adresy IP. Może to przypadkowo zablokować legalnych użytkowników, którzy naprawdę zapomną hasła wiele razy.
        -   *Ustawienie wyższej liczby (np. 10):* Sprawia, że ochrona jest mniej agresywna, pozwalając na więcej nieudanych prób. Zmniejsza to szansę na zablokowanie legalnych użytkowników, ale daje hakerom więcej prób.
    -   **Zalecana wartość:** **5**
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli zauważysz, że wielu legalnych klientów jest blokowanych, możesz to zwiększyć. Jeśli widzisz wiele prób brute-force w swoich logach, możesz to zmniejszyć. 5 to dobry balans.
3.  **Okno czasowe prób (minuty):**

    -   **Co robi to ustawienie:** Określa czas trwania (w minutach), w którym aktywna jest liczba „Maksymalna liczba nieudanych prób”. Jeśli adres IP wykona `Maksymalną liczbę nieudanych prób` w tym oknie, zostanie zablokowany. Po upływie tego okna licznik się resetuje.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawienie krótszego okna (np. 5 minut):* Adres IP musi wykonać `Maksymalną liczbę nieudanych prób` bardzo szybko, aby zostać zablokowanym. Jest to dobre dla szybkich ataków brute-force.
        -   *Ustawienie dłuższego okna (np. 60 minut):* Adres IP może wykonać `Maksymalną liczbę nieudanych prób` przez dłuższy czas, aby zostać zablokowanym. To wyłapuje wolniejsze, bardziej rozproszone ataki, ale może również zablokować legalnych użytkowników, którzy próbują się zalogować, rozpraszają się i próbują ponownie później.
    -   **Zalecana wartość:** **15**
    -   **Scenariusz / przykład dla sprzedawcy:** 15-minutowe okno jest zazwyczaj wystarczające do wyłapania zautomatyzowanych ataków, nie karząc nadmiernie ludzkiego użytkownika, który może próbować przypomnieć sobie hasło przez kilka minut.
4.  **Czas trwania blokady (minuty):**

    -   **Co robi to ustawienie:** Określa, jak długo adres IP pozostaje zablokowany po przekroczeniu `Maksymalnej liczby nieudanych prób` w `Oknie czasowym prób`.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawienie krótszego czasu trwania (np. 30 minut):* Adres IP jest odblokowywany szybciej. Jest to mniej uciążliwe dla legalnych użytkowników, którzy mogli zostać przypadkowo zablokowani, ale daje hakerom szybszą ponowną próbę.
        -   *Ustawienie dłuższego czasu trwania (np. 1440 minut = 24 godziny):* Adres IP pozostaje zablokowany przez znaczny okres. Jest to bardzo skuteczne przeciwko zautomatyzowanym atakom, ale może być frustrujące dla legalnych użytkowników, którzy są zablokowani.
    -   **Zalecana wartość:** **60** (1 godzina)
    -   **Scenariusz / przykład dla sprzedawcy:** 60-minutowa blokada jest zazwyczaj wystarczająca, aby odstraszyć zautomatyzowane boty, ponieważ prawdopodobnie przejdą one dalej. Dla człowieka zapewnia rozsądny okres „ochłodzenia”.
5.  **Chroń logowanie administratora:**

    -   **Co robi to ustawienie:** Ten przełącznik stosuje zasady ochrony logowania konkretnie do strony logowania Panelu administracyjnego PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Twoja strona logowania administratora jest chroniona. Jeśli atakujący spróbuje zbyt wiele razy odgadnąć Twoje hasło administratora, jego adres IP zostanie zablokowany.
        -   *Gdy wyłączone:* Monitorowane są tylko próby logowania klientów. Twoja strona logowania administratora pozostaje podatna na ataki brute-force.
    -   **Zalecana wartość:** **TAK**
    -   **Scenariusz / przykład dla sprzedawcy:** Absolutnie kluczowe jest chronienie logowania administratora, ponieważ nieautoryzowany dostęp tutaj może zagrozić całemu Twojemu sklepowi. Zawsze utrzymuj to włączone.
6.  **Chroń logowanie klienta:**

    -   **Co robi to ustawienie:** Ten przełącznik stosuje zasady ochrony logowania konkretnie do strony logowania klienta (front office).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Próby logowania klientów są chronione. Jeśli atakujący spróbuje odgadnąć hasła klientów, ich adres IP zostanie zablokowany.
        -   *Gdy wyłączone:* Monitorowane są tylko próby logowania administratora. Konta klientów pozostają podatne na ataki brute-force.
    -   **Zalecana wartość:** **TAK**
    -   **Scenariusz / przykład dla sprzedawcy:** Ochrona kont klientów jest kluczowa dla bezpieczeństwa danych i utrzymania zaufania klientów. Zawsze utrzymuj to włączone.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz ochronę logowania | TAK | Główny przełącznik funkcjonalności modułu. **Zawsze TAK.** |
| Konfiguracja modułu | Maksymalna liczba nieudanych prób | 5 | Liczba niepoprawnych logowań przed zablokowaniem IP. |
| Konfiguracja modułu | Okno czasowe prób (minuty) | 15 | Czas trwania, w którym liczone są nieudane próby. |
| Konfiguracja modułu | Czas trwania blokady (minuty) | 60 | Jak długo zablokowany IP pozostaje zbanowany. |
| Konfiguracja modułu | Chroń logowanie administratora | TAK | Stosuje ochronę do logowania w Panelu administracyjnym. **Zawsze TAK.** |
| Konfiguracja modułu | Chroń logowanie klienta | TAK | Stosuje ochronę do logowania klienta w Front Office. **Zawsze TAK.** |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia dwa dedykowane ekrany w Panelu administracyjnym PrestaShop do zarządzania i przeglądania prób logowania i blokad.

#### 2.2.1 AdminLproAttemptsController: Dziennik prób logowania

Ten ekran umożliwia przeglądanie szczegółowego dziennika wszystkich nieudanych prób logowania zarejestrowanych przez moduł.

-   **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Moduły > Login Protection Pro > **Próby logowania** (lub podobnie, w zależności od wersji PrestaShop i dostosowania menu).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela listy:** Zobaczysz tabelę wyświetlającą:
        -   **Adres IP:** Adres IP, z którego pochodziła nieudana próba.
        -   **Czas próby:** Dokładna data i godzina nieudanej próby.
        -   **Typ logowania:** Czy była to próba logowania „Admin” czy „Klient”.
        -   **Nazwa użytkownika/Email:** Nazwa użytkownika lub adres e-mail, który był próbowany.
        -   **Status:** Wskazuje, czy próba doprowadziła do blokady, czy była tylko nieudaną próbą.
    -   **Filtrowanie i sortowanie:** Zazwyczaj można filtrować według adresu IP, typu logowania lub zakresu dat, aby znaleźć konkretne próby.
    -   **Brak bezpośrednich działań:** Ten ekran służy głównie do monitorowania i przeglądania. Nie można bezpośrednio blokować ani odblokowywać adresów IP stąd, ale pomaga to identyfikować podejrzane wzorce.
-   **Efekt zmian:** Przeglądanie tego dziennika pomaga zrozumieć częstotliwość i źródło ataków. Jeśli zauważysz, że konkretny adres IP wykonuje wiele prób, możesz ręcznie dodać go do listy blokad za pośrednictwem ekranu „Zablokowane adresy IP”.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj ten dziennik, zwłaszcza jeśli podejrzewasz atak lub jeśli klienci zgłaszają problemy z logowaniem. Szukaj wzorców powtarzających się nieudanych prób z tego samego adresu IP lub zakresu adresów IP.

#### 2.2.2 AdminLproBansController: Zarządzanie zablokowanymi adresami IP

Ten ekran umożliwia przeglądanie, dodawanie i usuwanie adresów IP z listy blokad modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Moduły > Login Protection Pro > **Zablokowane adresy IP** (lub podobnie, w zależności od wersji PrestaShop i dostosowania menu).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela listy:** Wyświetla wszystkie aktualnie zablokowane adresy IP, w tym:
        -   **Adres IP:** Zablokowany adres IP.
        -   **Powód blokady:** (Jeśli dotyczy, np. „Automatyczna blokada z powodu nieudanych prób”).
        -   **Czas rozpoczęcia blokady:** Kiedy blokada została zainicjowana.
        -   **Czas zakończenia blokady:** Kiedy blokada ma wygasnąć (jeśli tymczasowa).
        -   **Akcje:** Zazwyczaj zawiera opcję „Usuń” lub „Odblokuj” konkretny adres IP.
    -   **Przycisk „Dodaj nowy IP”:** Umożliwia ręczne dodanie adresu IP do listy blokad. Jest to przydatne, jeśli zidentyfikujesz złośliwy adres IP z logów serwera lub ekranu „Próby logowania”, który nie został jeszcze automatycznie zablokowany.
        -   Podczas dodawania możesz określić adres IP, powód i opcjonalny czas wygaśnięcia blokady.
-   **Efekt zmian:**
    -   *Dodanie adresu IP:* Natychmiast blokuje wszystkie próby logowania z tego adresu IP na określony czas (lub na stałe, jeśli nie określono czasu).
    -   *Usunięcie adresu IP:* Odblokowuje adres IP, umożliwiając ponowne próby logowania z niego. Używaj tego ostrożnie, upewniając się, że nie odblokowujesz znanego atakującego.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Okresowo przeglądaj tę listę.
    -   Jeśli legalny klient zgłasza, że nie może się zalogować, a Ty potwierdziłeś jego adres IP (np. prosząc go o odwiedzenie strony „jaki jest mój IP”), możesz tymczasowo odblokować jego adres IP tutaj.
    -   Jeśli zidentyfikujesz uporczywe zagrożenie, możesz ręcznie dodać jego adres IP, aby upewnić się, że pozostanie zablokowany.

#### 2.2.3 index.php (lpro/controllers/admin/index.php)

Ten plik zazwyczaj służy jako placeholder lub przekierowanie w katalogu kontrolerów administracyjnych. W PrestaShop pliki `index.php` w katalogach kontrolerów często zapobiegają bezpośredniemu listowaniu katalogów lub działają jako domyślny punkt wejścia, jeśli nie zażądano konkretnego kontrolera. Sam w sobie nie reprezentuje konfigurowalnego ekranu ani zarządzanej jednostki.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci skarżą się, że nie mogą się zalogować, ale używają poprawnego hasła. Co powinienem zrobić?**
O1: Jest to prawdopodobnie spowodowane zablokowaniem ich adresu IP przez moduł po zbyt wielu nieudanych próbach (być może z poprzedniej sesji lub współdzielonej sieci).
1.  Poproś klienta o jego aktualny adres IP (może go znaleźć, wyszukując „jaki jest mój IP” w Google).
2.  Przejdź do **Panel administracyjny > Moduły > Login Protection Pro > Zablokowane adresy IP**.
3.  Wyszukaj jego adres IP na liście.
4.  Jeśli zostanie znaleziony, usuń/odblokuj jego adres IP.
5.  Doradź klientowi, aby spróbował zalogować się ponownie. Możesz również zasugerować mu zresetowanie hasła.

**P2: Jestem zablokowany w moim własnym panelu administracyjnym! Jak mogę odzyskać dostęp?**
O2: Może się to zdarzyć, jeśli wykonałeś zbyt wiele nieudanych prób.
1.  Jeśli masz dostęp FTP do swojego sklepu, możesz tymczasowo wyłączyć moduł. Przejdź do `modules/lpro/` i zmień nazwę pliku `index.php` (np. na `index.php.bak`). Spowoduje to wyłączenie modułu.
2.  Zaloguj się do swojego panelu administracyjnego.
3.  Przejdź do **Moduły > Menedżer modułów**, znajdź „Login protection pro” i kliknij „Konfiguruj”.
4.  Przejdź do **Zablokowane adresy IP** i usuń swój adres IP z listy.
5.  Zmień nazwę `index.php.bak` z powrotem na `index.php` w katalogu `modules/lpro/`.
6.  Włącz moduł ponownie, jeśli wyłączyłeś go w menedżerze modułów.
7.  Dostosuj ustawienia `Maksymalna liczba nieudanych prób` lub `Czas trwania blokady`, jeśli często jesteś blokowany.

**P3: Moduł nie blokuje żadnych adresów IP, nawet po wielu nieudanych próbach. Co może być nie tak?**
O3:
1.  **Sprawdź „Włącz ochronę logowania”:** Upewnij się, że główny przełącznik w konfiguracji modułu jest ustawiony na **TAK**.
2.  **Sprawdź „Chroń logowanie administratora” / „Chroń logowanie klienta”:** Upewnij się, że odpowiednia ochrona (administratora lub klienta) jest włączona.
3.  **Przejrzyj ustawienia:** Sprawdź, czy `Maksymalna liczba nieudanych prób`, `Okno czasowe prób` i `Czas trwania blokady` są ustawione na rozsądne wartości. Jeśli `Okno czasowe prób` jest zbyt krótkie, lub `Maksymalna liczba nieudanych prób` jest zbyt wysoka, może to wymagać bardzo agresywnego ataku, aby wywołać blokadę.
4.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami ustawienia modułu nie są stosowane natychmiast z powodu buforowania.
5.  **Sprawdź logi serwera:** Logi dostępu do serwera Twojego dostawcy hostingu mogą pokazać, czy moduł napotyka jakiekolwiek błędy PHP.

**P4: Czy ten moduł spowolni mój sklep?**
O4: Moduł został zaprojektowany tak, aby był lekki. Wykonuje sprawdzenia tylko podczas prób logowania, które są stosunkowo rzadkie w porównaniu do wyświetleń stron. Wpływ na wydajność powinien być znikomy. Jeśli zauważysz jakiekolwiek spowolnienie, upewnij się, że Twoja instalacja PrestaShop i serwer spełniają minimalne wymagania.

**P5: Jak przetłumaczyć komunikaty modułu na inne języki?**
O5: Chociaż ten moduł działa głównie w tle, wszelkie potencjalne komunikaty w front office (takie jak „Zbyt wiele nieudanych prób”) lub etykiety w back office można przetłumaczyć:
1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
3.  Wybierz swój szablon.
4.  Wybierz język, na który chcesz przetłumaczyć.
5.  Znajdź moduł „Login protection pro” i przetłumacz odpowiednie ciągi tekstowe.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Login protection pro” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `Login protection pro` przestrzega standardowej architektury modułów PrestaShop, wykorzystując głównie kontrolery administracyjne do swojego interfejsu zarządzania i hooki do swojej podstawowej funkcjonalności. Nie wprowadza złożonych kontrolerów front-office ani niestandardowych klas `ObjectModel`, zamiast tego polega na klasie `Configuration` PrestaShop do ustawień i bezpośredniej interakcji z bazą danych do logowania prób i zarządzania blokadami. Logika modułu do wykrywania i blokowania prób jest wstrzykiwana za pośrednictwem hooków PrestaShop, szczególnie wokół procesu uwierzytelniania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

Moduł **nie** zawiera żadnych dedykowanych kontrolerów front-office. Cała logika związana z front-office (monitorowanie prób logowania klientów) jest obsługiwana bezpośrednio w głównym pliku modułu (`lpro/index.php`) poprzez podłączenie się do procesu uwierzytelniania PrestaShop.

#### Kontrolery administracyjne Back Office

Moduł udostępnia dedykowane kontrolery administracyjne do zarządzania próbami logowania i blokadami.

-   **`controllers/admin/AdminLproAttempts.php`**

    -   **Nazwa klasy:** `AdminLproAttemptsController` (rozszerza `ModuleAdminController`)
    -   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za wyświetlanie listy wszystkich zarejestrowanych nieudanych prób logowania. Zapewnia widok siatki tylko do odczytu danych `lattempt`, umożliwiając administratorom monitorowanie podejrzanej aktywności. Zazwyczaj używa `HelperList` do renderowania tabeli.
    -   **Zarządzana jednostka:** `lattempt` (reprezentuje rekord nieudanej próby logowania).
    -   **Nazwa zakładki:** Próby logowania (widoczne pod głównym wpisem menu modułu).
-   **`controllers/admin/AdminLproBans.php`**

    -   **Nazwa klasy:** `AdminLproBansController` (rozszerza `ModuleAdminController`)
    -   **Odpowiedzialność:** Ten kontroler zarządza listą zablokowanych adresów IP. Zapewnia widok siatki danych `lban` i umożliwia administratorom dodawanie nowych blokad, edytowanie istniejących i usuwanie (odblokowywanie) adresów IP. Prawdopodobnie używa `HelperList` do tabeli i `HelperForm` do formularzy dodawania/edycji.
    -   **Zarządzana jednostka:** `lban` (reprezentuje rekord zablokowanego adresu IP).
    -   **Nazwa zakładki:** Zablokowane adresy IP (widoczne pod głównym wpisem menu modułu).
-   **`controllers/admin/index.php`**

    -   **Dokładna ścieżka pliku:** `lpro/controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** Nie jest plikiem klasy.
    -   **Odpowiedzialność:** Jest to standardowy plik placeholder PrestaShop. Jego głównym celem jest zapobieganie listowaniu katalogów, jeśli konfiguracja serwera WWW na to pozwala, a czasami może zawierać proste przekierowanie lub kontrolę bezpieczeństwa. Nie zawiera żadnej logiki funkcjonalnej dla samego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł **nie** zawiera żadnych niestandardowych klas w katalogu `classes/`. Prawdopodobnie obsługuje interakcje z bazą danych bezpośrednio w głównym pliku modułu (`lpro/index.php`) lub jego kontrolerach administracyjnych, używając standardowych metod zapytań do bazy danych PrestaShop. Oznacza to, że jednostki `lattempt` i `lban` są zarządzane bez dedykowanych klas `ObjectModel`, polegając na bezpośrednich zapytaniach SQL lub wywołaniach `Db::getInstance()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Sugeruje to, że jego interfejsy konfiguracji i zarządzania opierają się całkowicie na domyślnych bibliotekach i zachowaniach JavaScript PrestaShop (np. do przesyłania formularzy, filtrowania tabel).

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł **nie** zawiera żadnych niestandardowych plików CSS. Wskazuje to, że jego interfejsy Back Office (konfiguracja, dzienniki prób, listy blokad) dziedziczą styl bezpośrednio z motywu Back Office PrestaShop, zapewniając spójny wygląd i działanie bez wprowadzania niestandardowych elementów wizualnych.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   **`lpro/views/templates/admin/main.tpl`**:
        -   **Cel:** Ten szablon jest prawdopodobnie używany dla głównej strony konfiguracji modułu, renderowanej przez metodę `getContent()` w `lpro/index.php`. Zawiera strukturę HTML dla ustawień opisanych w sekcji 4.1 (Włącz ochronę logowania, Maksymalna liczba nieudanych prób itp.). Zazwyczaj zawiera elementy formularza (przełączniki, pola wejściowe) i potencjalnie linki do kontrolerów `AdminLproAttempts` i `AdminLproBans`.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł tworzy niestandardowe tabele bazy danych podczas swojej metody `install()` (zdefiniowanej w `lpro/index.php`).

-   **`ps_lpro_attempt`**:
    -   **Cel:** Przechowuje rekordy wszystkich nieudanych prób logowania.
    -   **Prawdopodobne pola:**
        -   `id_lpro_attempt` (Klucz podstawowy)
        -   `ip_address` (VARCHAR): Adres IP nieudanej próby.
        -   `attempt_time` (DATETIME): Sygnatura czasowa próby.
        -   `login_type` (VARCHAR): „admin” lub „customer”.
        -   `username` (VARCHAR): Próbowana nazwa użytkownika/e-mail.
        -   `is_banned` (TINYINT): Flaga wskazująca, czy ta próba doprowadziła do blokady.
-   **`ps_lpro_ban`**:
    -   **Cel:** Przechowuje rekordy aktualnie aktywnych blokad IP.
    -   **Prawdopodobne pola:**
        -   `id_lpro_ban` (Klucz podstawowy)
        -   `ip_address` (VARCHAR): Zablokowany adres IP.
        -   `ban_start_time` (DATETIME): Kiedy blokada się rozpoczęła.
        -   `ban_end_time` (DATETIME): Kiedy blokada ma wygasnąć (NULL dla blokad stałych).
        -   `reason` (TEXT): Opcjonalny powód blokady.
        -   `is_permanent` (TINYINT): Flaga dla blokad stałych.

#### Tabela zarejestrowanych hooków

Moduł rejestruje hooki, aby przechwytywać próby logowania i stosować swoją logikę ochrony.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAuthentication` | Po próbie zalogowania się klienta (front office). | Sprawdza, czy próba logowania klienta zakończyła się sukcesem czy niepowodzeniem. W przypadku niepowodzenia rejestruje próbę i sprawdza warunki blokady. |
| `actionAdminLoginController` | Po próbie zalogowania się administratora (back office). | Sprawdza, czy próba logowania administratora zakończyła się sukcesem czy niepowodzeniem. W przypadku niepowodzenia rejestruje próbę i sprawdza warunki blokady. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używany do dołączania CSS/JS (chociaż żadne nie są obecne) lub do wczesnych sprawdzeń, choć mniej prawdopodobne dla podstawowej logiki. Częściej do ogólnej inicjalizacji modułu. |
| `displayRightColumn` | W prawej kolumnie stron front-office. | Nie jest bezpośrednio istotny dla logiki bezpieczeństwa. Jeśli używany, służyłby do wyświetlania wiadomości lub bloku, co jest mało prawdopodobne dla tego modułu. |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | To samo co `displayRightColumn`. |
| `displayFooter` | W stopce każdej strony front-office. | Nie jest bezpośrednio istotny dla logiki bezpieczeństwa. |
| `displayProductExtraContent` | Na stronie produktu, w sekcji „dodatkowa zawartość”. | Nie jest bezpośrednio istotny dla logiki bezpieczeństwa. |

**Uwaga dotycząca hooków:** Podstawowa logika wykrywania i blokowania prób będzie głównie znajdować się w hookach `actionAuthentication` i `actionAdminLoginController`. Inne hooki `display` są prawdopodobnie rejestrowane domyślnie, ale nie są aktywnie używane do podstawowej funkcjonalności bezpieczeństwa modułu.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Login protection pro”.
