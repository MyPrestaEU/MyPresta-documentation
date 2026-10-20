---
title: "Kursy walut z Česká národní banka (CNB) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Kursy walut z Česká národní banka (CNB)” od MyPresta.eu."
sidebar:
  label: "Kursy walut z Česká národní banka (CNB) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Currency rates from Česká národní banka (CNB) na MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-ceska-narodni-banka-cnb.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/currency-rates-from-ceska-narodni-banka-cnb/)
>
> ---


# Kursy walut z Česká národní banka (CNB)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych, które są prawie powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień. Jest to główny i jedyny ekran konfiguracji modułu.

#### **Ustawienia i opcje**

**1. `mypresta_updates` (Aktualizacje MyPresta.eu)**

-   **Co robi to ustawienie:** Jest to standardowe ustawienie występujące w wielu modułach MyPresta.eu. Kontroluje, czy moduł sprawdza dostępność aktualizacji z MyPresta.eu i wyświetla powiadomienia w panelu administracyjnym PrestaShop.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (TAK):* Moduł będzie okresowo sprawdzał dostępność nowych wersji na MyPresta.eu. Jeśli zostanie znaleziona aktualizacja, możesz zobaczyć powiadomienie w panelu administracyjnym PrestaShop, zachęcające do pobrania i zainstalowania nowszej wersji. Pomaga to być na bieżąco z poprawkami błędów i nowymi funkcjami.
    -   *Gdy wyłączone (NIE):* Moduł nie będzie sprawdzał aktualizacji. Nie będziesz otrzymywać żadnych powiadomień o nowych wersjach, co oznacza, że będziesz musiał ręcznie sprawdzać swoje konto MyPresta.eu pod kątem aktualizacji.
-   **Zalecana wartość:** **TAK**. Zawsze zaleca się aktualizowanie modułów ze względów bezpieczeństwa, kompatybilności i nowych funkcji.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Twój moduł zawsze działa w najnowszej, najbardziej stabilnej wersji, bez konieczności ciągłego ręcznego sprawdzania. Włączenie tej opcji powiadomi Cię, gdy aktualizacja będzie dostępna.

**2. `update_` (Częstotliwość aktualizacji)**

-   **Co robi to ustawienie:** To ustawienie określa, jak często moduł próbuje pobierać i aktualizować kursy walut z feedu CNB.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na krótszy interwał (np. „Co godzinę”):* Kursy walut będą odświeżane częściej, zapewniając bardzo aktualne ceny, co jest korzystne na niestabilnych rynkach. Może to jednak nieznacznie zwiększyć obciążenie serwera (choć zazwyczaj jest to pomijalne dla tego typu operacji).
    -   *Gdy ustawione na dłuższy interwał (np. „Raz dziennie”):* Kursy są aktualizowane rzadziej. Jest to zazwyczaj wystarczające, ponieważ CNB zazwyczaj dostarcza dzienne kursy. Zmniejsza to obciążenie serwera.
-   **Zalecana wartość:** **Raz dziennie**. CNB zazwyczaj publikuje dzienne kursy, więc aktualizowanie częściej niż raz dziennie jest często niepotrzebne i nie dostarcza nowszych danych.
-   **Scenariusz / przykład dla sprzedawcy:** Prowadzisz międzynarodowy sklep, w którym wahania kursów wymiany mogą wpływać na Twoje marże zysku. Ustawienie tej opcji na „Raz dziennie” zapewnia, że zawsze masz najnowsze oficjalne kursy bez nadmiernego obciążania serwera.

**3. `updatev_` (Metoda aktualizacji)**

-   **Co robi to ustawienie:** To ustawienie definiuje, w jaki sposób moduł wyzwala proces aktualizacji kursów walut.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Zadanie Cron”:* Moduł oczekuje, że skonfigurujesz zadanie cron po stronie serwera (zaplanowane zadanie), które będzie okresowo wywoływać określony adres URL dostarczony przez moduł. Jest to najbardziej niezawodna i zalecana metoda, ponieważ zapewnia, że aktualizacje odbywają się dokładnie wtedy, gdy są zaplanowane, nawet jeśli nikt nie odwiedza Twojego sklepu.
    -   *Gdy ustawione na „Przy ładowaniu strony”:* Moduł będzie próbował aktualizować kursy, gdy klient lub administrator odwiedzi dowolną stronę Twojego sklepu. Jest to mniej niezawodne, ponieważ aktualizacje następują tylko wtedy, gdy ruch trafia na Twoją witrynę, a jeśli Twoja witryna ma niski ruch, aktualizacje mogą być opóźnione. Może to również nieznacznie spowolnić pierwsze ładowanie strony dla odwiedzającego, jeśli aktualizacja jest należna.
-   **Zalecana wartość:** **Zadanie Cron**. Jest to najbardziej niezawodna i wydajna metoda dla zaplanowanych zadań. Moduł dostarczy Ci dokładny adres URL do użycia w zadaniu cron.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz zagwarantować, że kursy walut są aktualizowane każdego ranka o 3:00, niezależnie od ruchu na stronie. Ustawienie tej opcji na „Zadanie Cron” i skonfigurowanie crona serwera osiągnie to niezawodnie.

**4. `currency_` (Waluty do aktualizacji)**

-   **Co robi to ustawienie:** Pozwala to wybrać, które konkretne waluty w Twoim sklepie PrestaShop powinny mieć swoje kursy wymiany aktualizowane przez feed CNB.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy wybrane są konkretne waluty:* Tylko wybrane waluty będą miały swoje kursy wymiany aktualizowane przez moduł. Inne waluty (jeśli je masz) zachowają swoje ręcznie ustawione kursy lub domyślny mechanizm aktualizacji PrestaShop (jeśli jest aktywny). Daje to szczegółową kontrolę.
    -   *Gdy nie wybrano żadnych walut (lub wybrano wszystkie):* Moduł spróbuje zaktualizować wszystkie aktywne waluty w Twoim sklepie, które są obecne w feedzie CNB.
-   **Zalecana wartość:** Wybierz **wszystkie waluty, których aktywnie używasz do transakcji i które są obsługiwane przez feed CNB**. Zazwyczaj obejmuje to EUR, USD, GBP i inne główne waluty.
-   **Scenariusz / przykład dla sprzedawcy:** Twój sklep akceptuje płatności w EUR, USD i CZK. Chcesz, aby kursy EUR i USD były aktualizowane przez CNB, ale CZK jest Twoją domyślną walutą i nie wymaga zewnętrznych aktualizacji. Wybierzesz EUR i USD z tej listy.

#### **Adres URL zadania Cron (wyświetlany po zapisaniu ustawień)**

-   **Co to robi:** Po skonfigurowaniu i zapisaniu ustawień modułu, zwłaszcza jeśli wybierzesz „Zadanie Cron” jako metodę aktualizacji, moduł wyświetli unikalny adres URL. Ten adres URL jest tym, co zadanie cron Twojego serwera musi wywołać, aby uruchomić proces aktualizacji.
-   **Efekt użycia tego adresu URL:** Gdy ten adres URL zostanie wywołany (przez zadanie cron Twojego serwera lub ręcznie w przeglądarce), moduł wykonuje swoją logikę, aby pobrać najnowsze kursy walut z CNB i zaktualizować je w bazie danych PrestaShop.
-   **Zalecane działanie:** Skopiuj ten adres URL i skonfiguruj go jako zadanie cron na swoim serwerze hostingowym. Skonsultuj się z dokumentacją lub wsparciem swojego dostawcy hostingu, aby dowiedzieć się, jak skonfigurować zadanie cron. Typowe zadanie cron może wyglądać tak: `wget -q -O /dev/null "TWÓJ_ADRES_URL_CRON_TUTAJ"`.
-   **Scenariusz / przykład dla sprzedawcy:** Ustawiono częstotliwość aktualizacji na „Raz dziennie” i metodę na „Zadanie Cron”. Moduł wyświetla `https://twojskep.com/module/cnbrates/cronjob?token=TWÓJ_UNIKALNY_TOKEN`. Następnie skonfigurujesz cron serwera, aby uruchamiał `wget -q -O /dev/null "https://twojskep.com/module/cnbrates/cronjob?token=TWÓJ_UNIKALNY_TOKEN"` raz na 24 godziny.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | TAK | Kontroluje powiadomienia o aktualizacjach z MyPresta.eu. |
| Konfiguracja modułu | Częstotliwość aktualizacji | Raz dziennie | Jak często moduł pobiera nowe kursy z CNB. |
| Konfiguracja modułu | Metoda aktualizacji | Zadanie Cron | Jak wyzwalany jest proces aktualizacji (zaplanowane zadanie vs. ładowanie strony). |
| Konfiguracja modułu | Waluty do aktualizacji | Wybierz wszystkie odpowiednie | Określa, które waluty w Twoim sklepie są aktualizowane przez CNB. |
| Konfiguracja modułu | Adres URL zadania Cron | (Wyświetlany po zapisaniu) | Adres URL do użycia dla zadań cron po stronie serwera w celu wywołania aktualizacji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy walut nie aktualizują się. Co powinienem sprawdzić w pierwszej kolejności?**
O: Najczęstszą przyczyną jest problem z zadaniem cron.

1.  Przejdź do **Moduły > Menedżer modułów > Konfiguruj** dla modułu Kursy CNB.
2.  Sprawdź ustawienie „Metoda aktualizacji”. Jeśli jest to „Zadanie Cron”, upewnij się, że poprawnie skonfigurowałeś zadanie cron na swoim serwerze hostingowym, używając podanego adresu URL. Skontaktuj się z pomocą techniczną swojego dostawcy hostingu, jeśli nie wiesz, jak to zrobić.
3.  Jeśli wybrano „Przy ładowaniu strony”, upewnij się, że Twój sklep otrzymuje regularny ruch. Jeśli nie, przełącz się na „Zadanie Cron” dla bardziej niezawodnych aktualizacji.
4.  Sprawdź również, czy waluty, które mają być aktualizowane, są wybrane na liście „Waluty do aktualizacji”.

**P: Czy ten moduł działa, jeśli domyślna waluta mojego sklepu nie jest CZK?**
O: Tak, absolutnie! Moduł jest zaprojektowany do działania nawet jeśli Twoja domyślna waluta nie jest CZK. Pobiera kursy z CNB, które dostarcza kursy wymiany dla różnych walut w stosunku do CZK. Moduł następnie inteligentnie przelicza je, aby zaktualizować waluty inne niż domyślne w Twoim sklepie w stosunku do Twojej rzeczywistej domyślnej waluty.

**P: Jak często CNB aktualizuje swoje kursy?**
O: Česká národní banka (CNB) zazwyczaj publikuje swoje oficjalne kursy wymiany raz dziennie, zazwyczaj w dni robocze. Dlatego ustawienie „Częstotliwości aktualizacji” modułu na „Raz dziennie” jest zazwyczaj wystarczające, aby pobrać najnowsze dostępne dane.

**P: Zaktualizowałem moduł, ale nie widzę żadnych zmian. Co mogę zrobić?**
A: Czasami system buforowania PrestaShop może uniemożliwić natychmiastowe wyświetlanie zmian.

1.  Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop.
2.  Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”, jeśli jest dostępna).
3.  Odśwież przeglądarkę (Ctrl+F5 lub Cmd+R), aby upewnić się, że nie widzisz buforowanej wersji strony.

**P: Czy mogę ręcznie wywołać aktualizację?**
O: Tak, jeśli Twoja „Metoda aktualizacji” jest ustawiona na „Zadanie Cron”, możesz ręcznie odwiedzić adres URL zadania cron (wyświetlany w konfiguracji modułu) w swojej przeglądarce internetowej. Spowoduje to natychmiastową aktualizację. Jest to jednak tylko do celów testowych/rozwiązywania problemów; w przypadku regularnych aktualizacji polegaj na zautomatyzowanym zadaniu cron.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Kursy walut z Česká národní banka (CNB)” to lekki moduł PrestaShop zaprojektowany do jednego, skoncentrowanego zadania: pobierania i aktualizowania kursów wymiany walut. Wykorzystuje on głównie kontroler front-office do udostępniania punktu końcowego zadania cron, umożliwiając zaplanowane, automatyczne aktualizacje. Moduł nie wprowadza nowych tabel bazy danych ani złożonych struktur `ObjectModel`, opierając się zamiast tego na istniejącej klasie `Currency` PrestaShop i `Configuration` dla swoich ustawień. Przestrzega podstawowej struktury modułu PrestaShop, integrując się z metodami `install()` i `uninstall()` do konfiguracji i czyszczenia.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CnbratesCronjobModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest rdzeniem automatyzacji modułu. Odpowiada na żądania adresu URL zadania cron (np. `twojskep.com/module/cnbrates/cronjob?token=...`). Jego metoda `initContent()` (lub podobna metoda cyklu życia) zawiera logikę do:
            1.  Walidacji parametru `token` względem przechowywanej konfiguracji, aby zapobiec nieautoryzowanemu dostępowi.
            2.  Pobierania najnowszych kursów wymiany z kanału XML CNB (zazwyczaj `https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml`).
            3.  Parsowania danych XML.
            4.  Iterowania przez skonfigurowane waluty w PrestaShop.
            5.  Dla każdej wybranej waluty, obliczania jej nowego kursu wymiany na podstawie danych CNB (które są zazwyczaj względne do CZK) i domyślnej waluty sklepu.
            6.  Aktualizowania pola `exchange_rate` dla odpowiedniego obiektu `Currency` w tabeli `ps_currency`.
            7.  Wyświetlania prostego komunikatu o sukcesie lub błędzie, głównie do logowania zadań cron.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CnbratesIndexModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to kontroler zastępczy lub awaryjny. W wielu modułach kontroler front-office `index.php` służy jako domyślny punkt wejścia, jeśli nie zażądano żadnej konkretnej akcji. Dla tego modułu jego główną funkcją jest prawdopodobnie przekierowanie na stronę główną lub wyświetlenie prostej wiadomości, ponieważ główna funkcjonalność jest obsługiwana przez `cronjob.php`. Nie zawiera znaczącej logiki biznesowej dla aktualizacji walut.
-   **Kontrolery administracyjne Back-Office**: Brak. Konfiguracja modułu jest obsługiwana w całości w `cnbrates.php` za pomocą `getContent()`.

### 4.3 Klasy podstawowe i modele (`classes/`)

W katalogu `classes/` dla tego modułu nie ma niestandardowych klas ani definicji `ObjectModel`. Moduł bezpośrednio współdziała z podstawową klasą `Currency` PrestaShop i klasą `Configuration` do zarządzania danymi.

### 4.4 Zasoby JavaScript (`views/js/`)

W tym module nie ma niestandardowych plików JavaScript. Cała funkcjonalność jest po stronie serwera PHP.

### 4.5 Arkusze stylów CSS (`views/css/`)

W tym module nie ma niestandardowych plików CSS. Moduł nie wprowadza żadnych wizualnych elementów front-office ani złożonego stylu back-office poza standardowymi elementami formularzy PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak. Moduł nie wyświetla treści za pomocą hooków.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` w `cnbrates.php` w celu wyświetlenia formularza konfiguracji modułu w panelu administracyjnym PrestaShop.
        -   **Zawartość**: Zawiera strukturę HTML dla ustawień opisanych w Sekcji 4.1, w tym pola wejściowe dla częstotliwości aktualizacji, metody aktualizacji, wyboru waluty i wyświetlania adresu URL zadania cron. Wykorzystuje standardowe pomocniki formularzy i stylizację PrestaShop.
-   **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł **nie** tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Kluczowe klucze konfiguracyjne to:
        -   `CNBRATES_UPDATE_FREQUENCY`
        -   `CNBRATES_UPDATE_METHOD`
        -   `CNBRATES_CURRENCIES` (prawdopodobnie lista identyfikatorów walut oddzielonych przecinkami)
        -   `CNBRATES_CRON_TOKEN` (unikalny token dla bezpieczeństwa zadania cron)
        -   `MYPRESTA_UPDATES_CNBRATES` (do sprawdzania aktualizacji MyPresta.eu)
    -   Aktualizuje kolumnę `exchange_rate` w tabeli `ps_currency` dla wybranych walut.
-   **Tabela zarejestrowanych hooków**:
    Moduł rejestruje następujące hooki, głównie do własnego zarządzania cyklem życia i potencjalnie do sprawdzania aktualizacji, a nie do wyświetlania treści:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Przy każdym ładowaniu strony w front-office (przed wyjściem HTML). | Często używany do dołączania JS/CSS, lub w tym przypadku, potencjalnie do metody aktualizacji „Przy ładowaniu strony”, jeśli jest skonfigurowana, lub do sprawdzania aktualizacji MyPresta.eu. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie front-office. | Nie używany do wyświetlania treści przez ten moduł, prawdopodobnie dziedziczna rejestracja hooka lub do wewnętrznych sprawdzeń. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie front-office. | Nie używany do wyświetlania treści przez ten moduł, prawdopodobnie dziedziczna rejestracja hooka lub do wewnętrznych sprawdzeń. |
| `displayFooter` | Renderuje zawartość w stopce front-office. | Nie używany do wyświetlania treści przez ten moduł, prawdopodobnie dziedziczna rejestracja hooka lub do wewnętrznych sprawdzeń. |
| `displayBackOfficeHeader` | Przy każdym ładowaniu strony w back-office. | Używany do dołączania CSS/JS specyficznego dla modułu na stronie konfiguracji lub do wyświetlania powiadomień o aktualizacjach z MyPresta.eu. |
| `actionAdminCurrenciesControllerSaveAfter` | Po zapisaniu waluty w back-office. | Może być używany do ponownej oceny ustawień waluty lub wywołania aktualizacji, jeśli status waluty ulegnie zmianie. |
| `actionAdminCurrenciesControllerDeleteAfter` | Po usunięciu waluty w back-office. | Może być używany do usunięcia usuniętej waluty z listy aktualizacji modułu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Kursy walut z Česká národní banka (CNB)” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub integracji modułu.
