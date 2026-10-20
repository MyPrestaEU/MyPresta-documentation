---
title: "Optymalizacja Bazy Danych - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Optymalizacja Bazy Danych od MyPresta.eu."
sidebar:
  label: "Optymalizacja Bazy Danych - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Database Optimization na MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/database-optimization/)
>
> ---


# Optymalizacja Bazy Danych

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu Optymalizacja Bazy Danych. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok „Optymalizacja Bazy Danych”.

#### **Niechciane koszyki**

-   **Co robi to ustawienie:** Ta opcja kontroluje, czy moduł będzie usuwał stare, porzucone koszyki zakupowe z Twojej bazy danych. Są to koszyki, które klienci rozpoczęli, ale nigdy nie ukończyli zamówienia.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Tak”:* Moduł będzie okresowo usuwał te stare, niekompletne koszyki. Zmniejsza to rozmiar bazy danych i może poprawić wydajność, ponieważ PrestaShop nie musi zarządzać danymi dla tysięcy porzuconych koszyków.
    -   *Gdy ustawione na „Nie”:* Stare koszyki zakupowe pozostaną w Twojej bazie danych. Chociaż zachowuje to dane historyczne, może z czasem przyczynić się do rozrostu bazy danych.
-   **Zalecana wartość:** **Tak**. Chyba że masz konkretny powód biznesowy do przechowywania wszystkich danych o porzuconych koszykach (np. do bardzo głębokiej analizy historycznej), ich czyszczenie jest korzystne dla wydajności.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli zauważysz, że Twoja baza danych staje się bardzo duża, a Twój sklep zwalnia, włączenie tej opcji to szybki sposób na usunięcie wspólnego źródła niepotrzebnych danych.

#### **Połączenia**

-   **Co robi to ustawienie:** Ta opcja kontroluje, czy moduł będzie usuwał stare logi połączeń z Twojej bazy danych. PrestaShop rejestruje każde połączenie odwiedzającego z Twoim sklepem, co może szybko się gromadzić.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Tak”:* Moduł będzie okresowo usuwał stare logi połączeń. Znacząco zmniejsza to rozmiar bazy danych, ponieważ logi połączeń mogą być jedną z największych tabel w ruchliwym sklepie.
    -   *Gdy ustawione na „Nie”:* Logi połączeń będą przechowywane w nieskończoność, potencjalnie prowadząc do bardzo dużej bazy danych.
-   **Zalecana wartość:** **Tak**. Dla większości sklepów bardzo stare logi połączeń nie są krytyczne dla codziennych operacji i mogą być bezpiecznie usunięte w celu poprawy wydajności.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep ma duży ruch, logi połączeń mogą rosnąć niezwykle szybko. Włączenie tej opcji pomaga zapobiec nadmiernemu rozrostowi i spowolnieniu bazy danych.

#### **Strona Połączeń**

-   **Co robi to ustawienie:** Ta opcja dotyczy konkretnie logów połączeń związanych z odwiedzanymi stronami. Działa w połączeniu z ustawieniem „Połączenia”.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Tak”:* Jeśli „Połączenia” jest również ustawione na „Tak”, moduł usunie stare logi szczegółowo opisujące, które konkretne strony odwiedzili użytkownicy.
    -   *Gdy ustawione na „Nie”:* Nawet jeśli „Połączenia” jest ustawione na „Tak”, moduł zachowa logi połączeń specyficzne dla stron.
-   **Zalecana wartość:** **Tak**. Podobnie jak ogólne połączenia, logi specyficzne dla stron mogą być bardzo liczne i często nie są potrzebne do długoterminowej analizy, jeśli używasz zewnętrznych narzędzi analitycznych, takich jak Google Analytics.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli polegasz na Google Analytics w zakresie statystyk wyświetleń stron, prawdopodobnie nie potrzebujesz, aby PrestaShop przechowywał te szczegółowe dane w nieskończoność, co sprawia, że ich czyszczenie jest bezpieczne.

#### **Źródło Połączeń**

-   **Co robi to ustawienie:** Ta opcja dotyczy konkretnie logów połączeń związanych ze źródłem odwiedzającego (np. bezpośrednie, wyszukiwarka, odesłanie). Działa w połączeniu z ustawieniem „Połączenia”.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Tak”:* Jeśli „Połączenia” jest również ustawione na „Tak”, moduł usunie stare logi szczegółowo opisujące, skąd pochodzili odwiedzający.
    -   *Gdy ustawione na „Nie”:* Nawet jeśli „Połączenia” jest ustawione na „Tak”, moduł zachowa logi połączeń specyficzne dla źródła.
-   **Zalecana wartość:** **Tak**. Podobnie jak inne dane połączeń, często można to zarządzać za pomocą zewnętrznych narzędzi analitycznych.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój zespół marketingowy używa narzędzi takich jak Google Analytics lub innych systemów CRM do śledzenia źródeł ruchu, wewnętrzne logi PrestaShop mogą być zbędne i mogą zostać wyczyszczone w celu zaoszczędzenia miejsca w bazie danych.

#### **Goście**

-   **Co robi to ustawienie:** Ta opcja kontroluje, czy moduł będzie usuwał stare, nieaktywne konta gości z Twojej bazy danych. Są to konta utworzone dla odwiedzających, którzy rozpoczęli realizację zamówienia jako gość, ale nigdy go nie ukończyli, lub po prostu przeglądali bez rejestracji.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Tak”:* Moduł będzie okresowo usuwał te stare konta gości. Pomaga to utrzymać bazę danych klientów w czystości i skupić się na aktywnych lub zarejestrowanych użytkownikach.
    -   *Gdy ustawione na „Nie”:* Stare konta gości pozostaną w Twojej bazie danych w nieskończoność.
-   **Zalecana wartość:** **Tak**. Chyba że masz konkretną potrzebę zachowania każdego pojedynczego rekordu gościa, ich czyszczenie pomaga utrzymać porządek w bazie danych.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep ma wielu odwiedzających, którzy przeglądają, ale nie rejestrują się ani nie dokonują zakupów, tabela gości może znacznie się rozrosnąć. Czyszczenie ich pomaga utrzymać dane klientów w zarządzalnym stanie.

#### **Sprawdź aktualizacje**

-   **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł będzie automatycznie sprawdzał dostępność nowych wersji i aktualizacji z MyPresta.eu.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Włącz”:* Moduł będzie okresowo łączył się z MyPresta.eu, aby sprawdzić, czy dostępna jest nowsza wersja. Jeśli tak, otrzymasz powiadomienie w Panelu administracyjnym PrestaShop.
    -   *Gdy ustawione na „Wyłącz”:* Moduł nie będzie sprawdzał aktualizacji. Będziesz musiał ręcznie sprawdzić swoje konto MyPresta.eu pod kątem nowych wersji.
-   **Zalecana wartość:** **Włącz**. Zapewnia to, że zawsze będziesz świadomy dostępnych aktualizacji, które często zawierają poprawki błędów, ulepszenia wydajności i nowe funkcje.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz mieć pewność, że Twoje moduły są zawsze aktualne pod względem bezpieczeństwa i wydajności. Włączenie tej opcji zapewnia wygodne powiadomienia.

#### **Powiadomienia o aktualizacjach**

-   **Co robi to ustawienie:** To ustawienie kontroluje, czy otrzymujesz powiadomienia w Panelu administracyjnym PrestaShop, gdy dostępna jest aktualizacja (jeśli „Sprawdź aktualizacje” jest włączone).
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Włącz”:* Zobaczysz powiadomienie w Panelu administracyjnym, gdy zostanie wykryta nowa wersja modułu.
    -   *Gdy ustawione na „Wyłącz”:* Nawet jeśli „Sprawdź aktualizacje” jest włączone i dostępna jest aktualizacja, nie otrzymasz widocznego powiadomienia w Panelu administracyjnym.
-   **Zalecana wartość:** **Włącz**. Działa to w parze z „Sprawdź aktualizacje”, aby informować Cię na bieżąco.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz być natychmiast powiadamiany, gdy aktualizacja jest gotowa, abyś mógł zaplanować jej instalację, zapewniając, że Twój sklep korzysta z najnowszych ulepszeń.

#### **Strona modułu**

-   **Co robi to ustawienie:** To ustawienie jest prawdopodobnie opcją wyświetlania dla własnej strony modułu lub informacji w Panelu administracyjnym. (Na podstawie typowej struktury modułów MyPresta.eu, może to kontrolować link lub konkretny element wyświetlania związany z samym modułem).
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Włącz”:* Prawdopodobnie wyświetla link lub sekcję związaną z informacjami o module lub innymi modułami MyPresta.eu.
    -   *Gdy ustawione na „Wyłącz”:* Ten link lub sekcja zostanie ukryta.
-   **Zalecana wartość:** **Włącz**. Zazwyczaj zapewnia szybki dostęp do wsparcia lub innych przydatnych zasobów.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz mieć łatwy dostęp do zasobów MyPresta.eu bezpośrednio ze strony konfiguracji modułu.

### 2.2 Tabela Szybkiego Odniesienia do Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| Konfiguracja Modułu | Niechciane koszyki | Tak | Usuwa stare, porzucone koszyki zakupowe, aby zmniejszyć rozmiar bazy danych i poprawić wydajność. |
| Konfiguracja Modułu | Połączenia | Tak | Usuwa stare logi połączeń odwiedzających, aby znacząco zmniejszyć rozmiar bazy danych. |
| Konfiguracja Modułu | Strona Połączeń | Tak | Usuwa stare logi konkretnych stron odwiedzonych przez połączenia. |
| Konfiguracja Modułu | Źródło Połączeń | Tak | Usuwa stare logi źródeł ruchu dla połączeń. |
| Konfiguracja Modułu | Goście | Tak | Usuwa stare, nieaktywne konta gości, aby utrzymać dane klientów w czystości. |
| Konfiguracja Modułu | Sprawdź aktualizacje | Włącz | Automatycznie sprawdza MyPresta.eu pod kątem aktualizacji modułu. |
| Konfiguracja Modułu | Powiadomienia o aktualizacjach | Włącz | Wyświetla powiadomienia w Panelu administracyjnym, gdy dostępne są aktualizacje modułu. |
| Konfiguracja Modułu | Strona modułu | Włącz | Kontroluje wyświetlanie linków/informacji związanych z modułem na stronie konfiguracji. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P: Po włączeniu modułu mój sklep nie wydaje się szybszy. Co się dzieje?**
O: Optymalizacja bazy danych to jeden element układanki wydajności. Chociaż usuwa niepotrzebne dane, inne czynniki, takie jak zasoby serwera, optymalizacja obrazów, ciężkie moduły lub niezoptymalizowane niestandardowe motywy, mogą nadal spowalniać Twój sklep. Upewnij się, że po konfiguracji wyczyściłeś również pamięć podręczną PrestaShop (Zaawansowane > Wydajność).

**P: Czy ten moduł usunie ważne dane klientów lub zamówienia?**
O: Nie. Ten moduł jest specjalnie zaprojektowany do usuwania *niechcianych* i *nieaktywnych* danych: porzuconych koszyków, starych logów połączeń i kont gości, które nigdy nie dokonały konwersji. Nie dotyka ukończonych zamówień, aktywnych kont klientów, danych produktów ani innych krytycznych informacji o sklepie.

**P: Jak często moduł czyści bazę danych? Czy jest to automatyczne?**
O: Moduł wykonuje operacje czyszczenia po zapisaniu jego konfiguracji lub po uruchomieniu określonych zadań w tle przez PrestaShop. Nie jest to ciągłe, działające w czasie rzeczywistym czyszczenie. Główna korzyść wynika z usunięcia nagromadzonych starych danych. W celu ciągłego, zaplanowanego czyszczenia, możesz potrzebować połączyć go z zadaniem cron, które okresowo uruchamia logikę czyszczenia modułu (chociaż ten moduł skupia się głównie na jednorazowym czyszczeniu lub czyszczeniu przy zapisie).

**P: Wyłączyłem „Sprawdź aktualizacje” i „Powiadomienia o aktualizacjach”, ale teraz chcę wiedzieć o aktualizacjach. Jak je ponownie włączyć?**
O: Po prostu wróć do strony konfiguracji modułu (Moduły > Menedżer modułów > Konfiguruj Optymalizację Bazy Danych) i ustaw zarówno „Sprawdź aktualizacje”, jak i „Powiadomienia o aktualizacjach” na „Włącz”. Zapisz zmiany, a moduł wznowi sprawdzanie i powiadamianie Cię o nowych wersjach.

## 4. Przewodnik dla Programistów i Webmasterów (Architektura Techniczna i Mapa Kodu)

### 4.1 Przegląd Architektury

Moduł Optymalizacja Bazy Danych to prosty moduł PrestaShop, zaprojektowany głównie do wykonywania operacji czyszczenia bazy danych. Przestrzega standardowej struktury modułów PrestaShop, wykorzystując klasę `Module` oraz jej metody `install()` i `uninstall()` do konfiguracji i deinstalacji. Jego podstawowa funkcjonalność znajduje się w metodzie `getContent()`, która obsługuje formularz konfiguracji w Panelu administracyjnym i uruchamia logikę optymalizacji bazy danych po przesłaniu formularza. Nie wprowadza niestandardowych kontrolerów, modeli ani zasobów front-office, co czyni go lekkim i skoncentrowanym narzędziem.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Wszystkie operacje są obsługiwane w Panelu administracyjnym lub za pośrednictwem głównej klasy modułu.
-   **Kontrolery Administracyjne Back-Office**: Brak. Konfiguracja jest zarządzana bezpośrednio w metodzie `getContent()` pliku `dboptimization.php`.

### 4.3 Klasy i Modele Podstawowe (`classes/`)

-   **Główna Klasa Modułu**: `dboptimization/dboptimization.php`
    -   **Nazwa Klasy**: `DbOptimization`
    -   **Klasa Nadrzędna**: `Module`
    -   **Odpowiedzialność**:
        -   Obsługuje instalację (`install()`) i deinstalację (`uninstall()`) modułu.
        -   Zarządza wyświetlaniem i przesyłaniem formularza konfiguracji w Panelu administracyjnym (`getContent()`).
        -   Zawiera podstawową logikę czyszczenia bazy danych na podstawie skonfigurowanych opcji.
        -   Rejestruje i wyrejestrowuje hooki (chociaż ten moduł używa głównie `displayBackOfficeHeader` do sprawdzania aktualizacji, a nie do wyświetlania w front-office).
        -   Zarządza wartościami konfiguracyjnymi za pomocą `Configuration::get()` i `Configuration::updateValue()`.
        -   Zawiera logikę sprawdzania aktualizacji (`checkforupdates()`) i wyświetlania powiadomień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   Brak. Moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

-   Brak. Moduł renderuje swój formularz konfiguracji bezpośrednio w metodzie `getContent()` za pomocą `HelperForm` PrestaShop (lub podobnej wewnętrznej logiki renderowania), a nie zewnętrznych plików `.tpl`.

### 4.7 Schemat Bazy Danych i Mapa Hooków

-   **Tabele Bazy Danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Wchodzi w interakcje z istniejącymi tabelami PrestaShop, głównie:
        -   `ps_cart`: Dla „Niechcianych koszyków”.
        -   `ps_connections`: Dla „Połączeń”.
        -   `ps_connections_page`: Dla „Strony Połączeń”.
        -   `ps_connections_source`: Dla „Źródła Połączeń”.
        -   `ps_guest`: Dla „Gości”.
    -   Wartości konfiguracyjne są przechowywane w tabeli `ps_configuration`:
        -   `dbopt_cart`
        -   `dbopt_connections`
        -   `dbopt_connections_page`
        -   `dbopt_connections_source`
        -   `dbopt_guest`
        -   `update_dboptimization` (dla znacznika czasu sprawdzania aktualizacji)
        -   `mypresta_updates` (globalne ustawienie powiadomień o aktualizacjach)
        -   `dbopt_check_updates`
        -   `dbopt_updates_notifications`
        -   `dbopt_module_page`
-   **Tabela Zarejestrowanych Hooków**:

| Nazwa Hooka | Plik / Metoda | Czas Wykonania | Cel Techniczny |
| --- | --- | --- | --- |
| `displayBackOfficeHeader` | `dboptimization.php` | Renderuje się w nagłówku stron Panelu administracyjnego. | Używany przez moduł do wstrzykiwania powiadomień o aktualizacjach, jeśli `dbopt_check_updates` i `dbopt_updates_notifications` są włączone. |
| `actionAdminControllerSetMedia` | `dboptimization.php` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Potencjalnie używany do sprawdzania aktualizacji lub do zapewnienia załadowania wszelkich niezbędnych zasobów (gdyby istniały) w panelu administracyjnym. |

## 5. Oficjalne Wsparcie i Aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i kompleksowe wsparcie dla modułu Optymalizacja Bazy Danych, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz dedykowany zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich pytań lub problemów związanych z funkcjonalnością i integracją modułu.
