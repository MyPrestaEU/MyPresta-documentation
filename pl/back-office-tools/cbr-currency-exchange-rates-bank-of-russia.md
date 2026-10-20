---
title: "CBR Currency Exchange & Rates (Bank of Russia) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop CBR Currency Exchange & Rates (Bank of Russia) od MyPresta.eu."
sidebar:
  label: "CBR Currency Exchange & Rates (Bank of Russia) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł CBR Currency Exchange & Rates (Bank of Russia) na MyPresta.eu](https://mypresta.eu/modules/administration-tools/cbr-currency-exchange-rates-bank-of-russia.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/cbr-currency-exchange-rates-bank-of-russia/)
>
> ---


# CBR Currency Exchange & Rates (Bank of Russia)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do komunikacji z zewnętrznym API, co jest powszechne w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień. Jest to główny ekran, na którym będziesz zarządzać wszystkimi aspektami modułu CBR Currency Exchange & Rates.

#### **Ustawienia ogólne**

-   **Włącz automatyczne aktualizacje:**
    *   **Co robi to ustawienie:** Ten przełącznik kontroluje, czy moduł będzie automatycznie sprawdzał i stosował nowe kursy walut z Centralnego Banku Rosji.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone (TAK):* Moduł będzie okresowo pobierał najnowsze kursy wymiany z witryny CBR. Jest to kluczowe dla utrzymania dokładności cen w RUB bez ręcznej interwencji. Będziesz musiał skonfigurować zadanie CRON (wyjaśnione poniżej), aby to działało.
        *   *Gdy wyłączone (NIE):* Moduł nie będzie automatycznie aktualizował kursów. Musiałbyś ręcznie aktualizować kursy, jeśli ta opcja jest wyłączona, co niweczy cel modułu.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoje ceny w RUB zawsze odzwierciedlały aktualny oficjalny kurs wymiany, bez konieczności codziennego logowania się i ich aktualizowania. Włączenie tej opcji zapewnia, że Twój sklep jest zawsze aktualny.
-   **Częstotliwość aktualizacji (w godzinach):**
    *   **Co robi to ustawienie:** Definiuje, jak często moduł powinien próbować pobierać nowe kursy wymiany z CBR.
    *   **Efekt zmiany tego ustawienia:**
        *   *Ustawienie niższej liczby (np. 1 godzina):* Kursy będą sprawdzane i aktualizowane częściej. Jest to idealne, jeśli Twoja firma wymaga bardzo precyzyjnych, niemal w czasie rzeczywistym konwersji.
        *   *Ustawienie wyższej liczby (np. 24 godziny):* Kursy będą sprawdzane rzadziej. Może to być odpowiednie, jeśli Twoje ceny nie wahają się dramatycznie lub jeśli wolisz zmniejszyć obciążenie serwera z częstych połączeń zewnętrznych.
    *   **Zalecana wartość:** 24 (Codzienne aktualizacje są zazwyczaj wystarczające, ponieważ kursy CBR zmieniają się raz dziennie).
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoje ceny w RUB były aktualizowane codziennie, więc ustawiasz to na 24 godziny. Jeśli sprzedajesz przedmioty o wysokiej wartości z niskimi marżami, możesz ustawić to na 12 godzin, aby uchwycić zmiany w ciągu dnia, jeśli CBR je publikuje (chociaż zazwyczaj jest to raz dziennie).
-   **Marża na kursie wymiany (%):**
    *   **Co robi to ustawienie:** Pozwala dodać procentową marżę do oficjalnego kursu wymiany CBR. Może to być użyte do pokrycia opłat transakcyjnych, kosztów przeliczenia waluty lub do lekkiego dostosowania strategii cenowej.
    *   **Efekt zmiany tego ustawienia:**
        *   *Ustawienie wartości dodatniej (np. 2):* Moduł zwiększy obliczony kurs wymiany o 2%. Oznacza to, że za każdą jednostkę Twojej waluty bazowej otrzymasz nieco więcej RUB, efektywnie zwiększając ceny w RUB.
        *   *Ustawienie 0 lub pozostawienie pustego:* Moduł użyje dokładnego oficjalnego kursu wymiany CBR bez żadnych korekt.
        *   *Ustawienie wartości ujemnej (np. -1):* Moduł zmniejszy obliczony kurs wymiany o 1%. Oznacza to, że otrzymasz nieco mniej RUB za każdą jednostkę Twojej waluty bazowej, efektywnie zmniejszając ceny w RUB.
    *   **Zalecana wartość:** 0 (Chyba że masz konkretne powody biznesowe, aby dodać marżę).
    *   **Scenariusz / przykład dla sprzedawcy:** Twoja bramka płatnicza pobiera 1,5% opłaty za przeliczenie RUB na Twoją walutę bazową. Możesz ustawić tutaj marżę 1,5%, aby zrekompensować ten koszt i utrzymać swoje marże zysku.
-   **Adres URL zadania CRON:**
    *   **Co robi to ustawienie:** Wyświetla unikalny adres URL, który musisz skonfigurować jako zadanie CRON na swoim serwerze hostingowym. Gdy ten adres URL zostanie wywołany, moduł zostanie uruchomiony w celu pobrania i aktualizacji kursów walut.
    *   **Efekt zmiany tego ustawienia:** To nie jest ustawienie, które zmieniasz, ale raczej adres URL, którego *używasz*.
        *   *Gdy poprawnie skonfigurowane jako zadanie CRON:* Moduł będzie automatycznie działał w tle z określoną częstotliwością (na podstawie ustawienia „Częstotliwość aktualizacji”), aby aktualizować kursy.
        *   *Jeśli nie skonfigurowane jako zadanie CRON:* Automatyczne aktualizacje nie będą miały miejsca, nawet jeśli „Włącz automatyczne aktualizacje” jest ustawione na TAK.
    *   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go jako zadanie CRON na swoim serwerze.
    *   **Scenariusz / przykład dla sprzedawcy:** Po skonfigurowaniu modułu kopiujesz ten adres URL i dodajesz go do harmonogramu zadań CRON w panelu sterowania hostingu, aby uruchamiał się codziennie o 3 rano, zapewniając aktualizację kursów przed rozpoczęciem dnia roboczego.

#### **Ustawienia waluty**

-   **Waluta do aktualizacji:**
    *   **Co robi to ustawienie:** Ta lista rozwijana pozwala wybrać, która konkretna waluta w Twoim sklepie PrestaShop powinna być aktualizowana kursami CBR. Wyświetli wszystkie waluty, które masz włączone w Panelu administracyjnym PrestaShop.
    *   **Efekt zmiany tego ustawienia:**
        *   *Wybranie „Rosyjski Rubel (RUB)”:* Moduł będzie konkretnie celował i aktualizował kurs wymiany dla rosyjskiego rubla w stosunku do waluty bazowej Twojego sklepu, używając danych CBR.
        *   *Wybranie innej waluty:* Ten moduł jest specjalnie zaprojektowany dla kursów CBR, które dotyczą rosyjskiego rubla. Wybranie innej waluty może prowadzić do nieoczekiwanego zachowania lub braku aktualizacji dla tej waluty.
    *   **Zalecana wartość:** Rosyjski Rubel (RUB)
    *   **Scenariusz / przykład dla sprzedawcy:** Walutą bazową Twojego sklepu jest EUR, a chcesz zapewnić, że gdy klienci wybiorą RUB, konwersja z EUR na RUB jest dokładna na podstawie CBR. Wybierasz tutaj „Rosyjski Rubel (RUB)”.

#### **Przycisk Zapisz**

-   **Zapisz:**
    *   **Co robi:** Stosuje wszystkie zmiany wprowadzone na stronie konfiguracji.
    *   **Efekt kliknięcia:** Twoje ustawienia zostaną zapisane w bazie danych, a moduł będzie działał zgodnie z nowymi parametrami.
    *   **Zalecane działanie:** Zawsze kliknij „Zapisz” po wprowadzeniu jakichkolwiek zmian.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz automatyczne aktualizacje | TAK | Kontroluje automatyczne pobieranie kursów CBR. TAK dla bezobsługowych aktualizacji. |
| Konfiguracja modułu | Częstotliwość aktualizacji (w godzinach) | 24 | Jak często zadanie CRON powinno wyzwalać aktualizacje kursów. 24 dla codziennych. |
| Konfiguracja modułu | Marża na kursie wymiany (%) | 0 | Dodaje procent do oficjalnego kursu. Użyj dla opłat lub strategii cenowej. |
| Konfiguracja modułu | Adres URL zadania CRON | (Unikalny URL) | Adres URL do skonfigurowania na serwerze dla automatycznych aktualizacji. |
| Konfiguracja modułu | Waluta do aktualizacji | Rosyjski Rubel (RUB) | Określa, którą walutę PrestaShop aktualizować kursami CBR. Musi być RUB. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje ceny w RUB nie aktualizują się automatycznie. Co powinienem sprawdzić?**
O1:

-   **Czy „Włącz automatyczne aktualizacje” jest ustawione na TAK?** Sprawdź konfigurację modułu.
-   **Czy skonfigurowałeś zadanie CRON na swoim serwerze hostingowym?** To najczęstszy powód. Skopiuj „Adres URL zadania CRON” z konfiguracji modułu i dodaj go do harmonogramu CRON w panelu hostingowym. Upewnij się, że jest ustawione na uruchamianie co najmniej tak często, jak ustawienie „Częstotliwość aktualizacji”.
-   **Czy „Waluta do aktualizacji” jest ustawiona na „Rosyjski Rubel (RUB)”?** Moduł jest przeznaczony dla RUB.
-   **Sprawdź logi zadań CRON na swoim serwerze (jeśli dostępne):** Twój dostawca hostingu może oferować logi, które pokazują, czy zadanie CRON działa i czy napotkało jakieś błędy.
-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”, aby upewnić się, że Twój sklep wyświetla najnowsze dane.

**P2: Kurs wymiany wydaje się nieprawidłowy lub nie zmienił się od dłuższego czasu.**
O2:

-   **Zweryfikuj oficjalny kurs CBR:** Sprawdź oficjalną stronę Centralnego Banku Rosji, aby potwierdzić dzisiejszy kurs wymiany.
-   **Sprawdź swoją „Częstotliwość aktualizacji”:** Jeśli jest ustawiona na 24 godziny, będzie aktualizować się tylko raz dziennie.
-   **Święta bankowe:** CBR nie aktualizuje kursów w dni świąt bankowych. Moduł inteligentnie używa ostatniego dostępnego kursu. Jeśli jest długi okres świąteczny, kurs może pozostać statyczny przez kilka dni.
-   **Problemy z zadaniem CRON:** Zapoznaj się z P1, aby rozwiązać problemy z zadaniami CRON.

**P3: Czy mogę używać tego modułu do innych walut niż RUB?**
O3: Nie, ten moduł jest specjalnie zaprojektowany do integracji z danymi kursów wymiany Centralnego Banku Rosji, które dotyczą głównie rosyjskiego rubla. Będzie on dokładnie aktualizować tylko walutę RUB w Twoim sklepie.

**P4: Zmieniłem szablon i teraz ceny w RUB wyglądają dziwnie.**
O4: Ten moduł obsługuje tylko *wartość* przeliczenia waluty. *Wyświetlanie* cen (czcionki, kolory, układ) jest obsługiwane przez Twój szablon PrestaShop. Jeśli ceny wyglądają dziwnie po zmianie szablonu, prawdopodobnie jest to problem z CSS lub szablonem Twojego nowego szablonu, a nie z samym modułem. Może być konieczne dostosowanie stylów Twojego szablonu.

**P5: Jak ręcznie zaktualizować kursy, jeśli zajdzie taka potrzeba?**
O5: Chociaż moduł jest zaprojektowany do automatycznych aktualizacji, możesz wymusić aktualizację, ręcznie odwiedzając adres URL zadania CRON w przeglądarce internetowej. Spowoduje to jednorazowe uruchomienie procesu aktualizacji. Pamiętaj, aby później wyczyścić pamięć podręczną PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem CBR Currency Exchange & Rates.

### 4.1 Przegląd architektury

Moduł `cbrrates` jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i konfiguracji. Wykorzystuje kontrolery front-office do wykonywania zadań CRON oraz prostą metodę `getContent()` do konfiguracji w panelu administracyjnym. Moduł pobiera dane XML z API CBR, parsuje je i aktualizuje kursy wymiany walut w `Currency` PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CbrratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest zaprojektowany do wywoływania przez zewnętrzne zadanie CRON. Po uzyskaniu dostępu inicjuje proces aktualizacji kursów walut. Sprawdza wartości konfiguracyjne `update_` i `updatev_`, aby określić, czy aktualizacja jest wymagana na podstawie skonfigurowanej częstotliwości. Następnie wywołuje główną logikę modułu w celu pobrania i zastosowania najnowszych kursów CBR. Wyświetla prosty komunikat o sukcesie lub błędzie.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CbrratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to kontroler zastępczy lub domyślny kontroler front-office. W wielu modułach, jeśli nie zdefiniowano konkretnej akcji, `index.php` może służyć jako rezerwowy lub po prostu przekierowywać. Dla `cbrrates` jego podstawowa funkcja jest prawdopodobnie minimalna, ponieważ główna interakcja z front-office odbywa się za pośrednictwem `cronjob.php`. Może być obecny, aby zapewnić istnienie prawidłowej trasy front-office dla modułu, nawet jeśli nie jest aktywnie używany do wyświetlania.
-   **Kontrolery administracyjne Back-Office**:

    -   W tym module nie ma dedykowanych kontrolerów administracyjnych. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

W katalogu `classes/` dla tego modułu nie ma niestandardowych klas ani definicji `ObjectModel`. Cała podstawowa logika znajduje się w głównym pliku `cbrrates.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

W module nie ma niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

W module nie ma niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `cbrrates/views/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` w `cbrrates.php` w celu wyświetlenia formularza konfiguracji modułu w Panelu administracyjnym PrestaShop.
        -   **Zawartość**: Zazwyczaj zawiera strukturę HTML dla pól wejściowych, przełączników i przycisków dla ustawień takich jak `mypresta_updates`, `update_`, `updatev_`, `currency_` oraz wyświetlanie adresu URL zadania CRON. Wykorzystuje standardowe pomocniki formularzy i style PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` (lub `_configuration` w zależności od prefiksu).
        -   `PS_CBRRATES_UPDATE_ENABLED`: Wartość logiczna (0/1) dla „Włącz automatyczne aktualizacje”.
        -   `PS_CBRRATES_UPDATE_FREQUENCY`: Liczba całkowita dla „Częstotliwość aktualizacji (w godzinach)”.
        -   `PS_CBRRATES_MARGIN`: Liczba zmiennoprzecinkowa dla „Marża na kursie wymiany (%)”.
        -   `PS_CBRRATES_CURRENCY_ID`: Liczba całkowita, ID waluty PrestaShop do aktualizacji (np. ID dla RUB).
        -   `PS_CBRRATES_LAST_UPDATE`: Sygnatura czasowa ostatniej udanej aktualizacji.
        -   `PS_CBRRATES_CRON_TOKEN`: Unikalny ciąg znaków używany w adresie URL zadania CRON dla bezpieczeństwa.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie hooków do wyświetlania w front-office (np. `displayHeader`, `displayFooter`). Jego podstawowa interakcja z rdzeniem PrestaShop odbywa się poprzez hook `actionUpdateCurrency` (niejawnie, poprzez aktualizację kursów walut) i własny wewnętrzny mechanizm CRON.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionUpdateCurrency` | Wyzwalany, gdy waluta jest aktualizowana (niejawnie przez ten moduł) | Niejawnie zarejestrowany przez moduł, ale podstawową funkcją modułu jest aktualizacja kursów walut, co może wyzwolić ten podstawowy hook PrestaShop. |
| (Wewnętrzny CRON) | Poprzez `controllers/front/cronjob.php` | Wyzwala pobieranie i aktualizację kursów wymiany CBR na podstawie skonfigurowanej częstotliwości. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „CBR Currency Exchange & Rates (Bank of Russia)”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
