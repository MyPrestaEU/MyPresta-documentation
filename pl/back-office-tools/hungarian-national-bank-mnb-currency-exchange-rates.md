---
title: "Węgierski Bank Narodowy (MNB) - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Węgierski Bank Narodowy (MNB) - kursy wymiany walut od MyPresta.eu."
sidebar:
  label: "Węgierski Bank Narodowy (MNB) - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Hungarian National Bank (MNB) - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/hungarian-national-bank-mnb-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/hungarian-national-bank-mnb-currency-exchange-rates/)
>
> ---


# Węgierski Bank Narodowy (MNB) - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do komunikacji z zewnętrznym API, co jest typowe dla modułów kursów wymiany. Upewnij się, że Twoje środowisko hostingowe je obsługuje.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu. Tutaj ustawiasz, w jaki sposób moduł pobiera i stosuje kursy wymiany.

#### **Ustawienia i opcje**

Strona konfiguracji modułu „Węgierski Bank Narodowy (MNB) - kursy wymiany walut” zazwyczaj przedstawia formularz z różnymi opcjami kontrolującymi jego zachowanie. Chociaż konkretne nazwy pól mogą się nieznacznie różnić, podstawowa funkcjonalność koncentruje się na włączaniu procesu aktualizacji i potencjalnym jego planowaniu.

1.  **Włącz aktualizacje kursów wymiany MNB**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji automatycznych aktualizacji kursów wymiany z Węgierskiego Banku Narodowego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie okresowo pobierał najnowsze kursy wymiany z MNB i stosował je do skonfigurowanych walut Twojego sklepu. Zapewnia to, że Twoje ceny są zawsze aktualne.
        -   *Gdy wyłączone (NIE):* Moduł przestanie pobierać i stosować kursy wymiany MNB. Kursy walut w Twoim sklepie pozostaną takie, jakie były ostatnio ustawione (ręcznie lub przez moduł przed jego wyłączeniem).
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby Twój sklep automatycznie odzwierciedlał najnowsze kursy wymiany MNB dla HUF, EUR, USD itp., musisz włączyć to ustawienie. Jeśli wolisz zarządzać kursami ręcznie lub używać innego systemu, wyłączysz je.
2.  **URL zadania Cron (do automatycznych aktualizacji)**

    -   **Co robi to ustawienie:** To pole wyświetla unikalny URL, którego możesz użyć do skonfigurowania „zadania cron” na swoim serwerze WWW. Zadanie cron to zaplanowane zadanie, które nakazuje Twojemu serwerowi odwiedzać ten URL w regularnych odstępach czasu, co powoduje, że moduł automatycznie aktualizuje kursy wymiany.
    -   **Efekt zmiany tego ustawienia:** To nie jest ustawienie, które zmieniasz bezpośrednio, ale raczej URL, który kopiujesz.
        -   *Gdy zadanie cron jest skonfigurowane:* Twój serwer będzie okresowo wywoływał ten URL, a moduł będzie uruchamiał proces aktualizacji w tle, bez konieczności wykonywania przez Ciebie jakichkolwiek czynności.
        -   *Gdy zadanie cron NIE jest skonfigurowane:* Musiałbyś ręcznie odwiedzić ten URL w swojej przeglądarce (lub kliknąć przycisk „Uruchom aktualizację teraz”, jeśli jest dostępny), aby wywołać aktualizację. Nie jest to zalecane do regularnego użytku.
    -   **Zalecana wartość:** Skopiuj ten URL i skonfiguruj zadanie cron w swoim panelu hostingowym (np. cPanel, Plesk lub wiersz poleceń serwera), aby uruchamiało się co najmniej raz dziennie, lub częściej, jeśli wymaga tego Twoja firma.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoje kursy wymiany aktualizowały się każdego ranka o 3:00. Skopiowałbyś ten URL, przeszedł do sekcji „Zadania Cron” w panelu sterowania swojego hostingu i utworzył nowe zadanie cron, które wykonuje `wget -O /dev/null -q "TWÓJ_URL_ZADANIA_CRON_TUTAJ"` (lub podobne polecenie) codziennie o 3:00.
3.  **Czas ostatniej aktualizacji** (Wyświetlanie informacyjne)

    -   **Co robi to ustawienie:** Jest to pole tylko do wyświetlania, które pokazuje, kiedy kursy wymiany zostały ostatnio pomyślnie zaktualizowane przez moduł.
    -   **Efekt zmiany tego ustawienia:** To nie jest konfigurowalne ustawienie. Po prostu dostarcza informacji zwrotnych na temat aktywności modułu.
    -   **Zalecana wartość:** N/A (informacyjne)
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz szybko sprawdzić ten znacznik czasu, aby potwierdzić, że Twoje zadanie cron działa poprawnie i że kursy są aktualizowane zgodnie z oczekiwaniami. Jeśli czas jest stary, wskazuje to na problem z konfiguracją zadania cron.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz aktualizacje kursów wymiany MNB | TAK | Aktywuje/dezaktywuje automatyczne pobieranie i stosowanie kursów wymiany MNB. |
| Konfiguracja modułu | URL zadania Cron | N/A (Kopiuj i konfiguruj) | URL do skonfigurowania zaplanowanego zadania (zadania cron) dla automatycznych aktualizacji kursów. |
| Konfiguracja modułu | Czas ostatniej aktualizacji | N/A (Informacyjne) | Wyświetla znacznik czasu ostatniej udanej aktualizacji kursów wymiany. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy wymiany nie aktualizują się. Co powinienem zrobić?**
O1:

1.  **Sprawdź „Włącz aktualizacje kursów wymiany MNB”:** Upewnij się, że to ustawienie jest ustawione na TAK w konfiguracji modułu.
2.  **Zweryfikuj konfigurację zadania Cron:** Najczęstszą przyczyną braku aktualizacji jest nieprawidłowo skonfigurowane zadanie cron.
    -   Upewnij się, że skopiowałeś dokładny „URL zadania Cron” z modułu.
    -   Sprawdź panel sterowania swojego hostingu (cPanel, Plesk itp.) pod kątem ustawień zadania cron.
    -   Potwierdź, że polecenie jest poprawne (np. `wget -O /dev/null -q "TWÓJ_URL_ZADANIA_CRON"`).
    -   Sprawdź harmonogram (np. `* * * * *` dla każdej minuty, `0 3 * * *` dla 3:00 codziennie).
    -   Poszukaj wszelkich dzienników błędów związanych z zadaniem cron w swoim panelu hostingowym.
3.  **Sprawdź „Czas ostatniej aktualizacji”:** Jeśli ten znacznik czasu jest stary, potwierdza to, że zadanie cron nie działa.
4.  **Łączność z serwerem:** Upewnij się, że Twój serwer może nawiązywać połączenia wychodzące z zewnętrznymi witrynami (takimi jak API MNB). Czasami zapory sieciowe lub ustawienia bezpieczeństwa mogą to blokować. Skontaktuj się z dostawcą hostingu, jeśli podejrzewasz taką sytuację.

**P2: Włączyłem moduł, ale niektóre waluty nie aktualizują się.**
O2:

1.  **Aktywacja waluty:** Przejdź do **Międzynarodowe > Waluty** w Panelu administracyjnym PrestaShop. Upewnij się, że waluty, które mają być aktualizowane, są włączone (aktywne). Moduł aktualizuje tylko aktywne waluty.
2.  **Wsparcie MNB:** MNB dostarcza kursy dla określonych walut. Jeśli waluta nie jest obsługiwana przez MNB, moduł nie może jej zaktualizować. Może być konieczne ręczne ustawienie kursów dla takich walut lub użycie innego modułu.

**P3: Mój niestandardowy motyw nie wyświetla cen poprawnie po aktualizacji.**
O3: Ten moduł przede wszystkim aktualizuje *dane* (kursy wymiany) w bazie danych PrestaShop. Nie wpływa bezpośrednio na sposób *wyświetlania* cen przez Twój motyw. Jeśli widzisz problemy z wyświetlaniem:

1.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”).
2.  **Dostosowanie motywu:** Jeśli Twój motyw ma mocno dostosowaną logikę wyświetlania cen, może to powodować zakłócenia. Sprawdź dokumentację swojego motywu lub skontaktuj się z jego twórcą.
3.  **Pamięć podręczna przeglądarki:** Poproś swoich klientów o wyczyszczenie pamięci podręcznej przeglądarki lub wypróbowanie innej przeglądarki, aby wykluczyć problemy z buforowaniem po stronie klienta.

**P4: Czy mogę ręcznie nadpisać kurs wymiany po jego aktualizacji przez moduł?**
O4: Tak, możesz. Po uruchomieniu modułu kursy są przechowywane w bazie danych PrestaShop. Możesz przejść do **Międzynarodowe > Waluty**, edytować konkretną walutę i ręcznie dostosować jej kurs wymiany. Pamiętaj jednak, że następnym razem, gdy zadanie cron zostanie uruchomione, moduł nadpisze Twoje ręczne zmiany najnowszymi danymi MNB. Jeśli potrzebujesz stałej ręcznej kontroli nad konkretną walutą, możesz rozważyć wyłączenie aktualizacji modułu dla tej waluty (jeśli moduł oferuje takie szczegółowe ustawienie, co jest rzadkością) lub całkowite wyłączenie modułu i ręczne zarządzanie wszystkimi kursami.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Węgierski Bank Narodowy (MNB) - kursy wymiany walut” opiera się na standardowej architekturze modułów PrestaShop, koncentrując się głównie na przetwarzaniu w tle. Wykorzystuje klasę `Module` PrestaShop do instalacji i konfiguracji oraz `ModuleFrontController` do obsługi wykonania zadania cron. Podstawowa logika obejmuje wykonanie żądania HTTP do oficjalnego API kursów wymiany MNB (prawdopodobnie kanału XML), parsowanie odpowiedzi, a następnie aktualizację tabeli `ps_currency` w bazie danych PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `mnbrates/controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MnbratesCronjobModuleFrontController` rozszerzająca `ModuleFrontController`
        -   **Odpowiedzialność**: Ten kontroler jest punktem wejścia dla zaplanowanego zadania cron. Gdy jego URL jest dostępny (np. `twojskep.com/module/mnbrates/cronjob`), wyzwala podstawową logikę modułu do pobierania i aktualizowania kursów wymiany. Zazwyczaj obsługuje żądanie HTTP, wywołuje główną metodę aktualizacji modułu i zwraca prostą wiadomość o sukcesie/niepowodzeniu lub brak danych wyjściowych (dla cichego wykonania crona).
    -   `mnbrates/controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MnbratesIndexModuleFrontController` rozszerzająca `ModuleFrontController`
        -   **Odpowiedzialność**: Jest to standardowy kontroler-placeholder często dołączany do modułów. W wielu przypadkach może po prostu przekierowywać do strony głównej lub służyć jako rezerwowy. Dla tego konkretnego modułu jego głównym celem jest prawdopodobnie zapobieganie listowaniu katalogów, jeśli ktoś spróbuje uzyskać bezpośredni dostęp do `/module/mnbrates/`, lub może to być plik szczątkowy. Jest mało prawdopodobne, aby zawierał podstawową logikę biznesową dla aktualizacji kursów wymiany.
-   **Kontrolery administracyjne Back-Office**:

    -   Nie zidentyfikowano dedykowanych kontrolerów administracyjnych (`controllers/admin/`). Oznacza to, że cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Nie zidentyfikowano żadnych niestandardowych klas ani modeli w katalogu `classes/`. Sugeruje to, że moduł prawdopodobnie wykonuje swoje operacje bezpośrednio w głównym pliku modułu `cronjob.php`, potencjalnie używając podstawowego `ObjectModel` `Currency` PrestaShop do aktualizacji kursów.

### 4.4 Zasoby JavaScript (`views/js/`)

Nie zidentyfikowano żadnych plików JavaScript. Potwierdza to backendowy charakter modułu, bez interaktywnych komponentów front-office ani złożonych formularzy back-office wymagających dynamicznego JS.

### 4.5 Arkusze stylów CSS (`views/css/`)

Nie zidentyfikowano żadnych plików CSS. Wskazuje to, że moduł nie wprowadza żadnych niestandardowych stylów ani dla front-office, ani dla back-office. Konfiguracja back-office będzie dziedziczyć domyślne style motywu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `mnbrates/views/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu (`mnbrates/cronjob.php`). Definiuje strukturę i zawartość strony konfiguracji modułu w Panelu administracyjnym PrestaShop. Będzie zawierał elementy formularza do włączania/wyłączania aktualizacji, wyświetlania URL zadania cron i pokazywania znacznika czasu ostatniej aktualizacji.
-   **Szablony hooków (`views/templates/hook/`)**: Brak zidentyfikowanych.
-   **Szablony front-office (`views/templates/front/`)**: Brak zidentyfikowanych.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL. Współpracuje z podstawową tabelą `ps_currency` PrestaShop, aby zaktualizować pole `conversion_rate` dla każdej waluty.
    -   Ustawienia konfiguracyjne (takie jak `PS_MNBRATES_ENABLED`, `PS_MNBRATES_LAST_UPDATE`) są przechowywane w tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:
    Moduł prawdopodobnie rejestruje hooki podczas swojej metody `install()`. Biorąc pod uwagę jego funkcjonalność, najważniejszym hookiem jest ten dla zadania cron, który jest obsługiwany przez kontroler front-office. Inne hooki mogą służyć celom informacyjnym lub zapewnieniu kompatybilności.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Mało prawdopodobne, aby było używane do podstawowej logiki, być może do dodania meta tagu lub bardzo prostego JS/CSS (chociaż żadne nie zostały zidentyfikowane). |
| `displayRightColumn` | Renderuje się w prawej kolumnie stron, gdzie jest dostępna. | Mało prawdopodobne, aby było używane do podstawowej logiki, być może do małego bloku informacyjnego, gdyby moduł miał komponent front-office. |
| `displayLeftColumn` | Renderuje się w lewej kolumnie stron, gdzie jest dostępna. | Podobnie jak `displayRightColumn`. |
| `displayFooter` | Renderuje się w stopce wszystkich stron front-office. | Podobnie jak `displayHeader`, ale na dole. |
| `displayProductExtraContent` | Renderuje dodatkową zawartość na stronie produktu. | Mało prawdopodobne dla tego modułu. |
| `actionModuleInstall` | Wykonywane podczas instalacji modułu. | Rejestruje niezbędne hooki i ustawia domyślne wartości konfiguracyjne. |
| `actionModuleUninstall` | Wykonywane podczas deinstalacji modułu. | Czyści wartości konfiguracyjne i wyrejestrowuje hooki. |
| `actionModuleUpdate` | Wykonywane podczas aktualizacji modułu. | Obsługuje zmiany schematu lub migracje konfiguracji między wersjami. |
| (Implicit) `frontController` dispatch | Gdy dostęp do `mnbrates/controllers/front/cronjob.php` jest uzyskiwany. | Wyzwala główną logikę aktualizacji kursów wymiany. Jest to główny „hook” dla zadania cron. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Węgierski Bank Narodowy (MNB) - kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół dba o to, aby Twój moduł działał optymalnie, a Twój sklep korzystał z najnowszych funkcji i kompatybilności.
