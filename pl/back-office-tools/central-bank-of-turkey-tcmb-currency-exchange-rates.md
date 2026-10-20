---
title: "Bank Centralny Turcji (TCMB) – kursy wymiany walut – Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Bank Centralny Turcji (TCMB) – kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Bank Centralny Turcji (TCMB) – kursy wymiany walut – Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Central Bank of Turkey (TCMB) - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/central-bank-of-turkey-tcmb-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/central-bank-of-turkey-tcmb-currency-exchange-rates/)
>
> ---


# Bank Centralny Turcji (TCMB) – kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych. Twoje środowisko hostingowe powinno zezwalać na połączenia wychodzące do strony internetowej TCMB.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień.

#### Ustawienia ogólne

-   **Włącz moduł**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł rozpocznie pobieranie kursów wymiany i aktualizowanie cen walut w Twoim sklepie zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Moduł zaprzestanie wszystkich operacji. Kursy wymiany nie będą aktualizowane automatycznie, a Twoje ceny pozostaną statyczne, dopóki nie zostaną zmienione ręcznie lub moduł nie zostanie ponownie włączony.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, włącz go, aby zacząć korzystać z jego funkcji. Jeśli musisz tymczasowo zatrzymać automatyczne aktualizacje (np. w celu konserwacji), możesz go wyłączyć.
-   **Adres URL CRON**

    -   **Co robi to ustawienie:** To pole wyświetla unikalny adres URL, który po wywołaniu uruchamia moduł do pobierania najnowszych kursów wymiany z TCMB i aktualizowania cen walut w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:** Jest to pole tylko do odczytu. Skopiowanie i ustawienie tego adresu URL w harmonogramie zadań CRON Twojego panelu hostingowego zautomatyzuje aktualizacje kursów.
    -   **Zalecana wartość:** Skopiuj ten adres URL.
    -   **Scenariusz / przykład dla sprzedawcy:** Skopiujesz ten adres URL i wkleisz go do panelu sterowania swojego hostingu (np. cPanel, Plesk lub niestandardowy interfejs zadań CRON), aby zaplanować automatyczne aktualizacje. Na przykład, możesz ustawić go tak, aby uruchamiał się raz na 24 godziny, aby zapewnić codzienną dokładność cen.
-   **Marża (%)**

    -   **Co robi to ustawienie:** Pozwala dodać procentową marżę powyżej oficjalnych kursów wymiany pobranych z TCMB. Może to być użyte do pokrycia opłat transakcyjnych, kosztów przeliczenia walut lub po prostu do dostosowania strategii cenowej.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 0:* Twój sklep będzie używał dokładnie oficjalnych kursów wymiany dostarczonych przez TCMB.
        -   *Gdy ustawione na wartość dodatnią (np. 2):* Moduł zwiększy obliczony kurs wymiany o ten procent. Na przykład, jeśli oficjalny kurs wynosi 1 USD = 30 TRY, a Ty ustawisz marżę 2%, moduł użyje 1 USD = 30,6 TRY do przeliczeń. Oznacza to, że produkty wycenione w USD będą wydawać się nieco droższe w TRY, lub odwrotnie, w zależności od Twojej waluty bazowej.
    -   **Zalecana wartość:** 0 (jeśli chcesz dokładne oficjalne kursy) lub niewielki dodatni procent (np. 1-3%), aby pokryć koszty.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja bramka płatności pobiera 1,5% opłaty za przeliczenia walut, możesz ustawić „Marżę (%)” na 1,5, aby pokryć ten koszt i utrzymać swoje marże zysku.
-   **Ostatnia aktualizacja**

    -   **Co robi to ustawienie:** To pole tylko do odczytu pokazuje datę i godzinę ostatniego pomyślnego pobrania i zastosowania aktualizacji kursów wymiany przez moduł.
    -   **Efekt zmiany tego ustawienia:** To pole aktualizuje się automatycznie po każdym pomyślnym wykonaniu zadania CRON lub ręcznej aktualizacji. Pomaga zweryfikować, czy moduł działa poprawnie i kiedy kursy były ostatnio odświeżane.
    -   **Zalecana wartość:** Monitoruj tę wartość, aby zapewnić regularne aktualizacje.
    -   **Scenariusz / przykład dla sprzedawcy:** Po skonfigurowaniu zadania CRON możesz sprawdzić to pole, aby potwierdzić, że automatyczne aktualizacje działają zgodnie z oczekiwaniami. Jeśli data jest stara, wskazuje to na problem z konfiguracją zadania CRON.

#### Ręczna aktualizacja

-   Przycisk **Aktualizuj teraz**
    -   **Co robi to ustawienie:** Ten przycisk pozwala ręcznie uruchomić proces aktualizacji kursów wymiany natychmiast, bez czekania na zadanie CRON.
    -   **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku natychmiast pobierze najnowsze kursy z TCMB i zaktualizuje ceny walut w Twoim sklepie. Jest to przydatne do testowania lub pilnych aktualizacji.
    -   **Zalecana wartość:** Kliknij, gdy potrzebujesz natychmiastowej aktualizacji lub do testowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie wprowadziłeś nowy produkt i chcesz upewnić się, że jego cena jest oparta na najnowszych kursach wymiany, zanim klienci zaczną zamawiać. Możesz kliknąć „Aktualizuj teraz”, aby natychmiast odświeżyć wszystkie kursy.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł | TAK | Aktywuje/dezaktywuje podstawową funkcjonalność modułu. |
| Konfiguracja modułu | Adres URL CRON | Skopiuj ten URL | Adres URL do ustawienia automatycznych aktualizacji kursów wymiany za pomocą zadania CRON na Twoim hostingu. |
| Konfiguracja modułu | Marża (%) | 0-3% | Dodaje procentową marżę powyżej oficjalnych kursów wymiany TCMB dla elastyczności cenowej. |
| Konfiguracja modułu | Ostatnia aktualizacja | Monitoruj | Wyświetla datę/godzinę ostatniej pomyślnej aktualizacji kursów wymiany. |
| Konfiguracja modułu | Przycisk Aktualizuj teraz | Kliknij w razie potrzeby | Ręcznie uruchamia natychmiastową aktualizację kursów wymiany. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje ceny nie aktualizują się, nawet po skonfigurowaniu modułu.**
O1: Najpierw sprawdź, czy ustawienie „Włącz moduł” jest ustawione na TAK. Po drugie, zweryfikuj konfigurację zadania CRON w panelu hostingowym. Upewnij się, że adres URL CRON jest poprawny, a zadanie jest zaplanowane do uruchomienia. Możesz również spróbować kliknąć przycisk „Aktualizuj teraz” w konfiguracji modułu, aby sprawdzić, czy ręczna aktualizacja działa. Jeśli tak, problem prawdopodobnie dotyczy Twojego zadania CRON.

**P2: Pole „Ostatnia aktualizacja” pokazuje starą datę, ale moje zadanie CRON jest skonfigurowane.**
O2: Zazwyczaj oznacza to, że Twoje zadanie CRON nie wykonuje się poprawnie lub moduł napotyka błąd podczas próby pobrania danych.
-   **Sprawdź logi zadań CRON:** Wielu dostawców hostingu oferuje logi dla wykonanych zadań CRON. Poszukaj tam wszelkich błędów.
-   **Dostęp do serwera:** Upewnij się, że Twój serwer ma wychodzący dostęp do internetu do `www.tcmb.gov.tr` (strony internetowej Banku Centralnego Turcji). Zapory ogniowe lub ograniczenia sieciowe mogą to blokować.
-   **Wersja PHP:** Potwierdź, że Twoja wersja PHP mieści się w obsługiwanym zakresie (PHP 5.6 - 8.5).
-   **Ponowna instalacja modułu:** W ostateczności spróbuj odinstalować i ponownie zainstalować moduł (po wykonaniu kopii zapasowej sklepu), aby upewnić się, że wszystkie pliki są poprawnie umieszczone.

**P3: Czy mogę aktualizować kursy częściej niż raz dziennie?**
O3: Tak, możesz skonfigurować swoje zadanie CRON tak, aby uruchamiało się częściej (np. co 6 godzin, co godzinę). Należy jednak wziąć pod uwagę wpływ na zasoby serwera i rzeczywistą częstotliwość zmian kursów TCMB. Codzienne aktualizacje są zazwyczaj wystarczające dla większości sklepów e-commerce, ponieważ oficjalne kursy zazwyczaj zmieniają się raz na dzień roboczy.

**P4: Mam wiele walut. Czy ten moduł zaktualizuje wszystkie?**
O4: Tak, moduł pobiera oficjalne kursy wymiany tureckiej liry (TRY) w stosunku do innych głównych walut. Następnie wykorzystuje te kursy do przeliczania i aktualizowania cen dla wszystkich aktywnych walut w Twoim sklepie PrestaShop, w oparciu o Twoją walutę bazową i pobrane kursy TRY.

**P5: Co się stanie, jeśli strona internetowa TCMB będzie niedostępna lub nieosiągalna?**
O5: Jeśli moduł nie może połączyć się ze stroną internetową TCMB, zazwyczaj nie zaktualizuje kursów. Twoje istniejące kursy walut pozostaną niezmienione, dopóki nie zostanie nawiązane pomyślne połączenie i aktualizacja. Pole „Ostatnia aktualizacja” nie zmieni się, wskazując na problem.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `tcmbrates` został zaprojektowany jako standardowy moduł PrestaShop, wykorzystujący głównie klasę `Module` do swojej podstawowej funkcjonalności. Jego głównym celem jest pobieranie danych zewnętrznych (kursów wymiany TCMB) i aktualizowanie wewnętrznych kursów walut PrestaShop. Wykorzystuje kontroler frontowy do wykonywania zadań CRON, co pozwala na jego zewnętrzne wyzwalanie bez bezpośredniej interakcji z Panelu administracyjnego. Konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, wyświetlając prosty formularz dla ustawień i ręczny wyzwalacz aktualizacji.

### 4.2 Kontrolery (`controllers/`)

Moduł zawiera kontrolery frontowe do obsługi żądań zewnętrznych, w szczególności dla zadań CRON.

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna:** `TcmbratesCronjobModuleFrontController` rozszerzająca `ModuleFrontController`.
        -   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zewnętrzny harmonogram zadań CRON. Po wywołaniu, uruchamia podstawową logikę modułu w celu pobrania najnowszych kursów wymiany z Banku Centralnego Turcji i zaktualizowania kursów walut w bazie danych PrestaShop. Zazwyczaj wyświetla komunikat o sukcesie lub niepowodzeniu.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna:** `TcmbratesIndexModuleFrontController` rozszerzająca `ModuleFrontController`.
        -   **Odpowiedzialność:** Jest to kontroler zastępczy lub domyślny kontroler frontowy, często dołączany do modułów, ale nie zawsze aktywnie używany do konkretnej funkcjonalności. W kontekście tego modułu prawdopodobnie służy jako rezerwowy lub prosty punkt wejścia, jeśli nie jest wymagany żaden inny konkretny kontroler frontowy. Jego główną funkcją jest zazwyczaj przekierowanie lub wyświetlenie ogólnego komunikatu.
-   **Kontrolery administracyjne Back-Office**: Brak. Cała administracja jest obsługiwana za pomocą metody `getContent()` modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie definiuje niestandardowych klas rozszerzających `ObjectModel`. Jego podstawowa logika znajduje się w głównym pliku modułu (`cronjob.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

W tym module nie ma niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

W tym module nie ma niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa jednego szablonu Smarty dla swojego interfejsu konfiguracji w Panelu administracyjnym.

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Cel:** Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu (`cronjob.php`). Wyświetla formularz konfiguracji modułu w Panelu administracyjnym PrestaShop, w tym pola do włączania modułu, ustawiania marży, wyświetlania adresu URL CRON i udostępniania przycisku ręcznej aktualizacji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne (np. `PS_TCMBRATES_ENABLED`, `PS_TCMBRATES_MARGIN`, `PS_TCMBRATES_LAST_UPDATE`) w standardowej tabeli `ps_configuration`. Bezpośrednio współdziała z tabelą `ps_currency` PrestaShop w celu aktualizacji kursów wymiany.
-   **Tabela zarejestrowanych hooków**: Moduł nie rejestruje się jawnie do standardowych hooków wyświetlania, takich jak `displayHeader` lub `displayFooter` dla treści front-office. Jego główna interakcja z systemem PrestaShop odbywa się poprzez wewnętrzną logikę wyzwalaną przez zadanie CRON lub ręczną aktualizację, która następnie modyfikuje istniejące dane walutowe.

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `install()` | Instalacja modułu | Tworzy wpisy konfiguracyjne w `ps_configuration`. |
  | `uninstall()` | Odinstalowanie modułu | Usuwa wpisy konfiguracyjne z `ps_configuration`. |
  | (Brak jawnych hooków wyświetlania front-office) | N/A | Moduł działa w tle, aby aktualizować dane, a nie wyświetlać treści. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Bank Centralny Turcji (TCMB) – kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
