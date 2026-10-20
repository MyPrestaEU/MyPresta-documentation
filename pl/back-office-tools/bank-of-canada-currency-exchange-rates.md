---
title: "Bank of Canada - kursy wymiany walut - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Bank of Canada - kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Bank of Canada - kursy wymiany walut - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bank of Canada - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-canada-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/bank-of-canada-currency-exchange-rates/)
>
> ---


# Bank of Canada - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych, które są niemal powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do ustawień modułu. Jest to główny ekran, na którym będziesz zarządzać sposobem aktualizacji kursów wymiany.

#### **1. Ręczna aktualizacja kursów wymiany**

-   **Co robi to ustawienie:** Jest to przycisk, który po kliknięciu natychmiast uruchamia moduł w celu pobrania najnowszych kursów wymiany z Banku Kanady i zaktualizowania ich w Twoim sklepie.
-   **Efekt zmiany tego ustawienia:**
    -   *Po kliknięciu:* Moduł łączy się z Bankiem Kanady, pobiera najbardziej aktualne kursy, oblicza kursy krzyżowe i stosuje je do walut Twojego sklepu. Zazwyczaj pojawi się komunikat potwierdzający.
-   **Zalecana wartość:** Użyj tego przycisku do natychmiastowych aktualizacji lub do przetestowania modułu po wstępnej konfiguracji. Do bieżących aktualizacji zalecane jest zadanie CRON (wyjaśnione poniżej).
-   **Scenariusz / przykład dla sprzedawcy:** Właśnie wprowadziłeś nowy produkt i chcesz upewnić się, że wszystkie ceny międzynarodowe są absolutnie aktualne przed dużą kampanią marketingową. Kliknij ten przycisk, aby wymusić natychmiastową aktualizację.

#### **2. Adres URL zadania CRON**

-   **Co robi to ustawienie:** To pole wyświetla unikalny adres URL, który po uzyskaniu dostępu uruchamia moduł w celu automatycznej aktualizacji kursów wymiany. Ten adres URL jest przeznaczony do użycia z „zadaniem CRON” na Twoim serwerze WWW.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy adres URL jest dostępny (przez zadanie CRON):* Moduł wykonuje ten sam proces aktualizacji kursów, co kliknięcie przycisku ręcznej aktualizacji, ale robi to automatycznie w zaplanowanych odstępach czasu.
-   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go jako zadanie CRON na swoim serwerze hostingowym.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kursy wymiany były aktualizowane codziennie o 3 rano. Kopiujesz ten adres URL i konfigurujesz swój panel hostingowy (cPanel, Plesk itp.), aby odwiedzał ten adres URL codziennie o 3 rano. Zapewnia to, że Twoje kursy są zawsze świeże, bez konieczności kiwnięcia palcem.

#### **3. Marża kursu wymiany (%)**

-   **Co robi to ustawienie:** Pozwala to dodać marżę procentową do kursów wymiany pobranych z Banku Kanady. Na przykład, jeśli kurs BOC wynosi 1.20, a Ty ustawisz marżę 2%, Twój sklep użyje kursu 1.224 (1.20 \* 1.02).
-   **Efekt zmiany tego ustawienia:**
    -   *Po ustawieniu wartości dodatniej (np. 2):* Wszystkie przeliczone ceny w Twoim sklepie będą nieco wyższe, odzwierciedlając dodaną marżę. Może to pomóc pokryć opłaty transakcyjne, koszty przewalutowania lub po prostu zwiększyć marżę zysku ze sprzedaży międzynarodowej.
    -   *Po ustawieniu na 0 (lub pozostawieniu pustego):* Moduł będzie używał dokładnych kursów wymiany dostarczonych przez Bank Kanady bez dodatkowej marży.
-   **Zalecana wartość:** Zacznij od 0% i dostosuj w zależności od potrzeb biznesowych, opłat bramki płatniczej i pożądanych marż zysku. Powszechną praktyką jest 1-3% na pokrycie potencjalnych kosztów.
-   **Scenariusz / przykład dla sprzedawcy:** Twoja bramka płatnicza pobiera 1.5% opłaty za międzynarodowe przewalutowania. Ustawiasz „Marżę kursu wymiany” na 1.5%, aby upewnić się, że ten koszt jest pokryty w cenach produktów, zamiast zmniejszać Twój zysk.

#### **4. Ostatnia aktualizacja**

-   **Co robi to ustawienie:** To pole wyświetla datę i godzinę ostatniej pomyślnej aktualizacji kursów wymiany wykonanej przez moduł.
-   **Efekt zmiany tego ustawienia:** Jest to pole tylko do odczytu i nie można go zmienić. Służy jako wskaźnik informacyjny.
-   **Zalecana wartość:** Monitoruj to pole, aby upewnić się, że zadanie CRON działa poprawnie, a kursy są regularnie aktualizowane.
-   **Scenariusz / przykład dla sprzedawcy:** Zauważasz, że Twoje ceny międzynarodowe wydają się nieaktualne. Sprawdzasz „Ostatnia aktualizacja” i widzisz, że nie była aktualizowana od tygodnia, co wskazuje na potencjalny problem z konfiguracją zadania CRON.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Ręczna aktualizacja kursów wymiany (Przycisk) | Kliknij, aby zaktualizować | Wymusza natychmiastową aktualizację wszystkich kursów wymiany walut z BOC. |
| Konfiguracja modułu | Adres URL zadania CRON | Skopiuj i skonfiguruj na serwerze | Udostępnia adres URL do automatycznych, zaplanowanych aktualizacji za pośrednictwem usługi CRON Twojego hostingu. |
| Konfiguracja modułu | Marża kursu wymiany (%) | 0% | Dodaje procentową marżę do pobranych kursów wymiany, wpływając na wszystkie przeliczone ceny. |
| Konfiguracja modułu | Ostatnia aktualizacja | Tylko do odczytu | Wyświetla znacznik czasu ostatniej pomyślnej aktualizacji kursów wymiany. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy wymiany nie aktualizują się automatycznie. Co powinienem zrobić?**
O1: To prawie zawsze problem z zadaniem CRON.
-   **Sprawdź swój panel hostingowy:** Zaloguj się na swoje konto hostingowe (cPanel, Plesk itp.) i sprawdź, czy zadanie CRON jest poprawnie skonfigurowane z dokładnym adresem URL dostarczonym przez moduł. Upewnij się, że częstotliwość jest prawidłowa (np. codziennie).
-   **Zweryfikuj polecenie CRON:** Polecenie zazwyczaj wygląda mniej więcej tak: `wget -O /dev/null "TWÓJ_ADRES_URL_CRON_TUTAJ"` lub `curl "TWÓJ_ADRES_URL_CRON_TUTAJ"`. Upewnij się, że nie ma literówek.
-   **Sprawdź „Ostatnia aktualizacja” w module:** Jeśli ta data jest stara, potwierdza to, że CRON nie działa.
-   **Ręcznie uruchom adres URL CRON:** Skopiuj adres URL CRON z konfiguracji modułu i wklej go do przeglądarki. Jeśli się zaktualizuje, to sam adres URL jest w porządku, a problem dotyczy wyłącznie konfiguracji CRON Twojego hostingu.

**P2: Ceny w innych walutach wydają się zbyt wysokie/niskie w porównaniu do waluty domyślnej.**
O2:
-   **Sprawdź swoją „Marżę kursu wymiany (%)”:** Jeśli jest ustawiona zbyt wysoko, ceny będą zawyżone. Jeśli jest ujemna (choć niezalecane), ceny byłyby niższe.
-   **Zweryfikuj swoją domyślną walutę:** Upewnij się, że domyślna waluta Twojego sklepu PrestaShop (Lokalizacja > Waluty) jest poprawnie ustawiona na Twoją główną walutę operacyjną (np. CAD, jeśli pobierasz z Banku Kanady). Moduł oblicza kursy względem Twojej domyślnej waluty.
-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare ceny mogą być buforowane.

**P3: Moduł mówi, że „Ostatnia aktualizacja” zakończyła się pomyślnie, ale nie widzę zmian we front-office.**
O3:
-   **Wyczyść pamięć podręczną PrestaShop:** Jest to najczęstszy powód. Zawsze czyść pamięć podręczną po każdej znaczącej aktualizacji danych w PrestaShop.
-   **Sprawdź pamięć podręczną przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub wyświetlić swój sklep w oknie incognito/prywatnym, aby wykluczyć problemy z lokalnym buforowaniem.
-   **Zweryfikuj wybór waluty:** Upewnij się, że faktycznie przeglądasz sklep w walucie innej niż domyślna, w której spodziewasz się zobaczyć przeliczone ceny.

**P4: Czy ten moduł działa z niestandardowymi motywami?**
A4: Tak, ten moduł działa w tle, aktualizując podstawowe kursy wymiany walut PrestaShop. Nie wchodzi bezpośrednio w interakcje z elementami wizualnymi Twojego motywu, więc powinien być kompatybilny z każdym niestandardowym motywem. Selektor walut motywu będzie po prostu wyświetlał ceny na podstawie kursów dostarczonych przez moduł.

**P5: Czy mogę używać tego modułu, jeśli moją domyślną walutą nie jest CAD?**
A5: Tak, możesz. Moduł pobiera podstawowe kursy z Banku Kanady (np. USD do CAD, EUR do CAD). Następnie inteligentnie oblicza kursy krzyżowe względem *domyślnej waluty Twojego sklepu*. Tak więc, jeśli Twoją domyślną walutą jest EUR, a BOC dostarcza USD/CAD, moduł obliczy EUR/USD, EUR/CAD itp., na podstawie dostępnych danych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Bank of Canada - kursy wymiany walut” (`bocrates`) został zaprojektowany jako lekkie, zautomatyzowane rozwiązanie do synchronizacji kursów walut. Wykorzystuje głównie podstawowy `ObjectModel` `Currency` PrestaShop do aktualizacji kursów wymiany. Moduł używa kontrolera frontowego do wykonywania zadań CRON, zapewniając, że aktualizacje kursów odbywają się poza standardowym kontekstem Panelu administracyjnego, co jest idealne dla zaplanowanych zadań. Przestrzega architektury modułów PrestaShop, wykorzystując metody `install()` i `uninstall()` do konfiguracji i czyszczenia, oraz `getContent()` do konfiguracji Panelu administracyjnego.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `BocratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest punktem wejścia dla zautomatyzowanego zadania CRON. Po uzyskaniu dostępu za pośrednictwem unikalnego adresu URL (podanego w konfiguracji modułu), uruchamia metodę `processUpdateExchangeRates()` w głównej klasie modułu. Jest przeznaczony do wywoływania zewnętrznie przez harmonogram CRON po stronie serwera, a nie bezpośrednio przez użytkownika. Zazwyczaj wyświetla prosty komunikat o sukcesie lub błędzie.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `BocratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to kontroler zastępczy lub domyślny kontroler frontowy. W wielu modułach, jeśli konkretna akcja nie jest zdefiniowana, może być używany `index.php`. Dla tego modułu jego główną funkcją jest prawdopodobnie służyć jako rezerwowy lub zapewnić, że routing front-office modułu jest poprawnie ustanowiony, nawet jeśli nie wykonuje on konkretnej akcji skierowanej do użytkownika. `cronjob.php` jest aktywnym kontrolerem frontowym dla funkcjonalności.
-   **Kontrolery administracyjne Back-Office**:

    -   Brak. Cała konfiguracja Panelu administracyjnego jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu `bocrates.php`.

### 4.3 Główne klasy i modele (`classes/`)

-   Brak. Moduł bezpośrednio współdziała z podstawowym `ObjectModel` `Currency` PrestaShop i klasą `Configuration` do przechowywania i manipulacji danymi.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Brak. Moduł nie używa niestandardowego JavaScriptu do swojej funkcjonalności.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Brak. Moduł nie używa niestandardowego CSS do swojej funkcjonalności.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `bocrates/views/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu `bocrates.php`. Wyświetla formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Obejmuje to przycisk ręcznej aktualizacji, adres URL zadania CRON, pole wprowadzania marży kursu wymiany i znacznik czasu ostatniej aktualizacji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` za pomocą kluczy takich jak:
        -   `BOCRATES_MARGIN`: Przechowuje marżę procentową dla kursów wymiany.
        -   `BOCRATES_LAST_UPDATE`: Przechowuje znacznik czasu ostatniej pomyślnej aktualizacji.
        -   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Związane z mechanizmem aktualizacji MyPresta.eu.
-   **Tabela zarejestrowanych hooków**:
    Moduł działa głównie w tle i nie rejestruje hooków do wyświetlania we front-office. Jego podstawowa funkcjonalność jest wyzwalana przez kontroler frontowy `cronjob`.

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionModuleInstall` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne i rejestruje niezbędne hooki (jeśli istnieją). |
    | `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wartości konfiguracyjne. |
    | `displayBackOfficeHeader` | Renderuje w nagłówku Panelu administracyjnego | Potencjalnie używane do dołączania zasobów lub wyświetlania powiadomień w panelu administracyjnym (chociaż nie wymieniono żadnych konkretnych zasobów). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i dedykowane wsparcie techniczne dla modułu „Bank of Canada - kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
