---
title: "NBU Currency Exchange & Rates - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop NBU Currency Exchange & Rates od MyPresta.eu."
sidebar:
  label: "NBU Currency Exchange & Rates"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł NBU Currency Exchange & Rates (National Bank of Ukraine) na MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbu-currency-exchange-rates-national-bank-of-ukraine.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/nbu-currency-exchange-rates-national-bank-of-ukraine/)
>
> ---


# NBU Currency Exchange & Rates

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane do pobierania danych z zewnętrznych API. Większość nowoczesnych środowisk hostingowych spełnia te wymagania domyślnie.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do ustawień modułu. Tutaj zdefiniujesz, w jaki sposób kursy NBU są stosowane w Twoim sklepie.

**Nazwa ekranu:** Konfiguracja NBU Currency Exchange & Rates

**Ustawienia i opcje:**

1.  **Adres URL zadania CRON:**
    -   **Co robi to ustawienie:** Wyświetla unikalny adres URL, który harmonogram CRON Twojego serwera musi okresowo wywoływać. Gdy ten adres URL zostanie wywołany, moduł automatycznie pobiera najnowsze kursy wymiany NBU i aktualizuje je w Twoim sklepie PrestaShop.
    -   **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł. Jeśli nie skonfigurujesz zadania CRON do wywoływania tego adresu URL, kursy wymiany nie będą aktualizować się automatycznie, a będziesz musiał ręcznie wywoływać aktualizacje (jeśli taka opcja istnieje, co nie ma miejsca w przypadku głównej funkcji tego modułu).
    -   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go w harmonogramie zadań CRON w panelu sterowania hostingu.
    -   **Scenariusz / przykład dla sprzedawcy:** Kopiujesz `https://twoj-sklep.com/module/nburates/cronjob?token=TWÓJ_BEZPIECZNY_TOKEN` i dodajesz go do zadań CRON w cPanelu lub Plesku, aby uruchamiał się raz dziennie (np. o 3 rano). Zapewnia to, że Twoje ceny w UAH są zawsze aktualne, zanim klienci zaczną robić zakupy.

2.  **Częstotliwość zadania CRON:**
    -   **Co robi to ustawienie:** Jest to zalecenie dotyczące częstotliwości uruchamiania zadania CRON. NBU zazwyczaj aktualizuje kursy raz dziennie.
    -   **Wpływ zmiany tego ustawienia:** Jest to wyłącznie informacyjne. Zmiana rzeczywistej częstotliwości zadania CRON (w panelu hostingu) wpłynie na to, jak często kursy są aktualizowane. Uruchamianie go zbyt często (np. co minutę) jest niepotrzebne i może zużywać zasoby serwera bez korzyści, ponieważ kursy NBU nie zmieniają się tak często. Uruchamianie go zbyt rzadko (np. raz w tygodniu) oznacza, że Twoje kursy mogą być nieaktualne.
    -   **Zalecana wartość:** Raz dziennie.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawiasz zadanie CRON na swoim serwerze, aby uruchamiało się `0 3 * * *` (codziennie o 3 rano), aby dopasować się do codziennych aktualizacji NBU.

3.  **Waluta do aktualizacji (UAH):**
    -   **Co robi to ustawienie:** To pole pozwala określić ID ukraińskiej hrywny (UAH) w Twoim sklepie PrestaShop. Moduł musi wiedzieć, którą walutę ma aktualizować.
    -   **Wpływ zmiany tego ustawienia:** Jeśli ID jest nieprawidłowe lub pozostawione puste, moduł nie będzie w stanie znaleźć i zaktualizować waluty UAH, a Twoje ceny nie będą odzwierciedlać kursów NBU.
    -   **Zalecana wartość:** ID Twojej waluty UAH. Możesz je znaleźć, przechodząc do **Międzynarodowe > Waluty** w Panelu administracyjnym PrestaShop, edytując walutę UAH i patrząc na adres URL (np. `id_currency=3` oznacza, że ID to 3).
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja waluta UAH ma ID `3`. Wprowadzasz `3` w tym polu. Teraz, gdy zadanie CRON się uruchomi, moduł wie, że ma zaktualizować kurs wymiany dla waluty o ID `3`.

4.  **Marża (%):**
    -   **Co robi to ustawienie:** Pozwala to dodać procentową marżę (narzut lub upust) do pobranych kursów wymiany NBU. Wartość dodatnia zwiększa kurs (sprawiając, że ceny w UAH są wyższe), a wartość ujemna zmniejsza go (sprawiając, że ceny w UAH są niższe).
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy ustawione na 0:* Moduł używa dokładnego kursu NBU.
        -   *Gdy ustawione na 2:* Kurs wymiany UAH będzie o 2% wyższy niż oficjalny kurs NBU. Na przykład, jeśli NBU podaje 1 EUR = 40 UAH, z marżą 2%, Twój sklep użyje 1 EUR = 40,8 UAH. Może to pomóc pokryć opłaty transakcyjne lub zapewnić niewielki bufor zysku.
        -   *Gdy ustawione na -1:* Kurs wymiany UAH będzie o 1% niższy niż oficjalny kurs NBU. Może to być używane do cen promocyjnych lub oferowania niewielkiej zniżki.
    -   **Zalecana wartość:** Zależy od Twojej strategii biznesowej. `0` dla dokładnych kursów NBU lub niewielki dodatni procent (np. `1` lub `2`) na pokrycie kosztów.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz nieznacznie zrekompensować opłaty bramki płatniczej za transakcje w UAH. Ustawiasz marżę na `1.5`. Teraz wszystkie ceny w UAH będą obliczane przy użyciu kursu NBU plus dodatkowe 1.5%.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Adres URL zadania CRON | N/A (Generowany) | Adres URL do wyzwalania codziennych aktualizacji kursów. Musi być skonfigurowany w CRON hostingu. |
| Konfiguracja modułu | Częstotliwość zadania CRON | Raz dziennie | Informacyjne zalecenie dotyczące harmonogramowania zadania CRON. |
| Konfiguracja modułu | Waluta do aktualizacji (UAH) | ID waluty UAH | Określa, która waluta w PrestaShop powinna być aktualizowana kursami NBU. Kluczowe dla działania modułu. |
| Konfiguracja modułu | Marża (%) | 0 | Dodaje procentowy narzut/upust do kursu NBU dla elastyczności cenowej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje ceny w UAH nie aktualizują się. Co powinienem zrobić?**
O1:
*   **Sprawdź zadanie CRON:** Najczęstszą przyczyną jest nieprawidłowo skonfigurowane lub brakujące zadanie CRON. Sprawdź, czy adres URL zadania CRON z konfiguracji modułu jest poprawnie dodany do panelu hostingowego i jest zaplanowany do uruchomienia.
*   **Sprawdź ID waluty UAH:** Upewnij się, że ustawienie „Waluta do aktualizacji (UAH)” w konfiguracji modułu odpowiada dokładnemu ID Twojej waluty UAH w PrestaShop (**Międzynarodowe > Waluty**).
*   **Sprawdź dostępność NBU:** Czasami API NBU może być tymczasowo niedostępne. Poczekaj kilka godzin i sprawdź ponownie. Moduł jest zaprojektowany tak, aby używać ostatniego znanego kursu, jeśli API jest niedostępne.
*   **Logi serwera:** Sprawdź logi zadań CRON serwera (jeśli są dostępne) pod kątem błędów podczas wywoływania adresu URL CRON.

**P2: Moduł jest zainstalowany, ale nie widzę żadnych wizualnych zmian w moim sklepie.**
O2: Ten moduł działa w tle, aby aktualizować kursy walut. Nie dodaje nowych bloków ani elementów wizualnych do Twojego sklepu. Jego efekt jest widoczny w dokładnym obliczaniu cen produktów, gdy UAH jest wybraną walutą.

**P3: Czy mogę ręcznie aktualizować kursy, jeśli zadanie CRON zawiedzie?**
O3: Głównym mechanizmem modułu jest zadanie CRON. Chociaż możesz ręcznie aktualizować kursy walut w PrestaShop (**Międzynarodowe > Waluty**), spowodowałoby to nadpisanie kursów NBU. Najlepszą praktyką jest upewnienie się, że zadanie CRON działa poprawnie. Jeśli potrzebujesz natychmiastowej aktualizacji, możesz ręcznie wywołać adres URL CRON raz, odwiedzając go w przeglądarce (chociaż nie jest to zamierzone długoterminowe rozwiązanie).

**P4: Co się dzieje w dni wolne od pracy, gdy NBU nie publikuje nowych kursów?**
O4: Moduł jest zaprojektowany tak, aby inteligentnie to obsługiwać. Jeśli NBU nie publikuje nowych kursów w danym dniu (np. weekendy lub święta państwowe), moduł zazwyczaj zachowa ostatni pomyślnie pobrany kurs. Zapewnia to stabilność i spójność cen w UAH.

**P5: Jak wyczyścić pamięć podręczną Smarty, jeśli wprowadzam zmiany i ich nie widzę?**
O5: Chociaż zmiany w tym module są głównie oparte na danych (kursy walut), a mniej na szablonach wizualnych, wyczyszczenie pamięci podręcznej może czasami pomóc. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Ustaw „Kompilacja szablonów” na „Ponownie kompiluj szablony, jeśli pliki zostały zaktualizowane” lub „Wymuś kompilację” i kliknij „Wyczyść pamięć podręczną”. Pamiętaj, aby po rozwiązaniu problemu przywrócić ustawienie „Nigdy nie kompiluj ponownie plików szablonów” dla wydajności produkcyjnej.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury
Moduł `NBU Currency Exchange & Rates` to lekki moduł PrestaShop zaprojektowany do integracji zewnętrznych kursów wymiany walut z API Narodowego Banku Ukrainy (NBU). Działa w oparciu o prosty wzorzec podobny do MVC w ramach struktury modułu PrestaShop. Główna logika znajduje się w głównym pliku modułu (`cronjob.php`), który obsługuje konfigurację, instalację i wykonanie głównego zadania CRON. Wykorzystuje klasę `Configuration` PrestaShop do przechowywania ustawień i `Currency` ObjectModel do aktualizacji kursów. Główna funkcjonalność modułu jest udostępniana za pośrednictwem kontrolera front-office, specjalnie zaprojektowanego do wywoływania przez zadanie CRON po stronie serwera.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    *   `nburates/controllers/front/cronjob.php`
        *   **Nazwa klasy:** `NburatesCronjobModuleFrontController` (rozszerza `ModuleFrontController`)
        *   **Odpowiedzialność:** Jest to krytyczny punkt końcowy dla zadania CRON. Po uzyskaniu dostępu wykonuje następujące czynności:
            1.  Weryfikuje bezpieczny token (`token`) przekazany w adresie URL, aby zapobiec nieautoryzowanemu dostępowi.
            2.  Pobiera ustawienia konfiguracji modułu (ID waluty UAH, marża).
            3.  Pobiera najnowsze kursy wymiany NBU z oficjalnego API NBU (prawdopodobnie `https://bank.gov.ua/NBUStatService/v1/statdirectory/exchangenew?json`).
            4.  Parsuje odpowiedź JSON w celu wyodrębnienia odpowiednich kursów walut.
            5.  Stosuje skonfigurowaną marżę do pobranych kursów.
            6.  Aktualizuje kurs wymiany dla określonej waluty UAH w tabeli `ps_currency` za pomocą `Currency` ObjectModel PrestaShop.
            7.  Obsługuje warunki błędów (np. niedostępność API, nieprawidłowa odpowiedź) poprzez logowanie lub powrót do poprzednich kursów.
            8.  Wyświetla prostą wiadomość o sukcesie lub błędzie, odpowiednią do logowania zadań CRON.
    *   `nburates/controllers/front/index.php`
        *   **Nazwa klasy:** `NburatesIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        *   **Odpowiedzialność:** Jest to standardowy pusty kontroler front-office `index.php`, często dołączany do modułów w celu zapobiegania listowaniu katalogów lub jako symbol zastępczy. Zazwyczaj nie zawiera specyficznej logiki dla głównej funkcji tego modułu.

-   **Kontrolery administracyjne Back-Office**:
    *   Brak. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Główne klasy i modele (`classes/`)
-   Brak. Moduł bezpośrednio współdziała z podstawowym `Currency` ObjectModel i klasą `Configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)
-   Brak. Moduł nie używa żadnego niestandardowego kodu JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   Brak. Moduł nie używa żadnego niestandardowego kodu CSS. Strona konfiguracji administratora opiera się na domyślnej stylizacji Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `nburates/views/admin.tpl`
        *   **Cel:** Ten szablon renderuje formularz konfiguracji modułu w Panelu administracyjnym PrestaShop.
        *   **Zawartość:** Wyświetla adres URL zadania CRON, zalecenie dotyczące częstotliwości CRON, pola wejściowe dla ID waluty UAH i procent marży. Zazwyczaj używa standardowych pomocników formularzy i stylizacji PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    *   Współdziała z tabelą `ps_configuration` w celu przechowywania swoich ustawień (np. `NBU_RATES_UAH_CURRENCY_ID`, `NBU_RATES_MARGIN`, `NBU_RATES_SECURE_TOKEN`).
    *   Aktualizuje tabelę `ps_currency`, w szczególności kolumnę `conversion_rate` dla waluty UAH.

-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje żadnych tradycyjnych hooków wyświetlania (`displayHeader`, `displayFooter` itp.), które renderują zawartość w front office. Jego głównym „hookiem” jest `action`, którą wykonuje, gdy jego kontroler front-office jest wywoływany przez zadanie CRON.

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionModuleInstall` | Podczas instalacji modułu | Tworzy wpisy konfiguracyjne, generuje bezpieczny token. |
| `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wpisy konfiguracyjne. |
| (Niejawne) `ModuleFrontController::initContent()` dla `NburatesCronjobModuleFrontController` | Gdy adres URL CRON jest wywoływany | Pobiera kursy NBU, stosuje marżę, aktualizuje kurs waluty UAH. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, poprawek błędów i wsparcia dla programistów dla modułu „NBU Currency Exchange & Rates” prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i zapewnienie kompatybilności modułu z najnowszymi wersjami PrestaShop.
