---
title: "Bank Włoch (Banca dItalia) - kursy wymiany walut - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Bank Włoch (Banca dItalia) - kursy wymiany walut od MyPresta.eu."
sidebar:
  label: "Bank Włoch (Banca dItalia) - kursy wymiany walut - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bank of Italy (Banca dItalia) - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-italy-banca-ditalia-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/bank-of-italy-banca-ditalia-currency-exchange-rates/)
>
> ---


# Bank Włoch (Banca dItalia) - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do komunikacji z zewnętrznym API, które są prawie powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij przycisk „Konfiguruj” obok nazwy modułu w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji modułu „Bank Włoch (Banca dItalia) - kursy wymiany walut”.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ta sekcja pozwala kontrolować, w jaki sposób moduł aktualizuje kursy wymiany walut i zarządzać jego podstawową funkcjonalnością.
-   **Wpływ zmiany tego ustawienia:** Te ustawienia bezpośrednio wpływają na dokładność i częstotliwość kursów wymiany w Twoim sklepie.

#### Specyficzne ustawienia i opcje:

1.  **Przycisk „Aktualizuj kursy”**

    -   **Co robi to ustawienie:** Jest to ręczny wyzwalacz do natychmiastowego pobrania najnowszych kursów wymiany z Banku Włoch i zastosowania ich do walut Twojego sklepu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po kliknięciu:* Moduł połączy się ze źródłem danych Banku Włoch, pobierze najnowsze referencyjne kursy euro i zaktualizuje wszystkie aktywne waluty w Twoim sklepie PrestaShop (z wyjątkiem Twojej domyślnej waluty, którą zazwyczaj jest EUR). Jest to przydatne do testowania lub do natychmiastowej aktualizacji poza zaplanowanymi zadaniami cron.
    -   **Zalecana wartość:** Kliknij ten przycisk po początkowej konfiguracji, aby upewnić się, że Twoje kursy są aktualne. Używaj go ręcznie, gdy potrzebujesz natychmiastowej aktualizacji.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie dodałeś nową walutę do swojego sklepu lub nastąpiła znacząca fluktuacja rynkowa i chcesz upewnić się, że Twoje ceny są natychmiast aktualizowane przed dużą wyprzedażą.
2.  **Pole „Adres URL CRON do automatycznych aktualizacji”**

    -   **Co robi to ustawienie:** To pole wyświetla unikalny adres URL, którego możesz użyć z usługą „cron job” swojego dostawcy hostingu. Zadanie cron to zaplanowane zadanie, które uruchamia się automatycznie w określonych odstępach czasu (np. raz dziennie, co godzinę).
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po skonfigurowaniu u dostawcy hostingu:* Kursy wymiany w Twoim sklepie będą automatycznie aktualizowane z częstotliwością, którą zdefiniujesz w ustawieniach zadania cron, bez konieczności ręcznego klikania jakichkolwiek przycisków. Zapewnia to, że Twoje kursy są zawsze świeże.
        -   *Gdy nie jest skonfigurowane:* Będziesz musiał ręcznie kliknąć przycisk „Aktualizuj kursy”, aby odświeżyć kursy wymiany.
    -   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj zadanie cron na swoim serwerze, aby uruchamiało się co najmniej raz na 24 godziny. Codzienna aktualizacja jest zazwyczaj wystarczająca dla większości sklepów e-commerce.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kursy wymiany w Twoim sklepie były aktualizowane każdego ranka o 3:00, zapewniając, że wszystkie ceny są aktualne na początek dnia roboczego, bez konieczności pamiętania o tym.
3.  **Pole „Dodaj marżę do kursów wymiany (%)”**

    -   **Co robi to ustawienie:** Pozwala to dodać procentową marżę do pobranych kursów wymiany. Na przykład, jeśli oficjalny kurs wynosi 1 EUR = 1,10 USD, a Ty ustawisz marżę 2%, moduł użyje 1 EUR = 1,078 USD (1,10 \* 0,98) lub 1 EUR = 1,122 USD (1,10 \* 1,02) w zależności od kierunku konwersji. Pomaga to pokryć potencjalne opłaty transakcyjne, koszty konwersji walut lub po prostu zapewnić niewielki bufor.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po ustawieniu na wartość dodatnią (np. 2):* Moduł dostosuje pobrane kursy wymiany o ten procent. Zazwyczaj oznacza to, że otrzymasz nieco więcej lokalnej waluty za swoje produkty oparte na euro lub nieco mniej euro za produkty w walucie lokalnej, co pomaga chronić Twoje marże zysku.
        -   *Po ustawieniu na 0 (lub puste):* Moduł użyje dokładnych kursów wymiany dostarczonych przez Bank Włoch bez żadnych korekt.
    -   **Zalecana wartość:** Zacznij od 0. Jeśli napotkasz problemy z rentownością z powodu wahań walutowych lub opłat transakcyjnych, rozważ dodanie niewielkiej marży (np. 1-3%).
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja bramka płatności pobiera 1,5% opłaty za transakcje międzynarodowe. Ustawiając marżę 2%, możesz wchłonąć ten koszt i zapewnić, że Twoja rentowność nie zostanie naruszona przez konwersje walut.
4.  **Przełącznik „Sprawdź aktualizacje modułu”**

    -   **Co robi to ustawienie:** Ten przełącznik kontroluje, czy moduł okresowo sprawdza MyPresta.eu pod kątem nowszych wersji modułu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu (TAK):* Moduł będzie sporadycznie łączyć się z MyPresta.eu, aby sprawdzić, czy dostępna jest nowsza wersja. Jeśli zostanie znaleziona aktualizacja, zobaczysz powiadomienie w panelu administracyjnym PrestaShop, zachęcające do pobrania i zainstalowania najnowszej wersji. Pomaga to być na bieżąco z poprawkami błędów, nowymi funkcjami i aktualizacjami kompatybilności.
        -   *Po wyłączeniu (NIE):* Moduł nie będzie sprawdzał aktualizacji i nie będziesz powiadamiany o nowych wersjach. Będziesz musiał ręcznie sprawdzić swoje konto MyPresta.eu pod kątem aktualizacji.
    -   **Zalecana wartość:** **TAK**. Utrzymywanie modułów w aktualności jest kluczowe dla bezpieczeństwa, wydajności i kompatybilności z przyszłymi wersjami PrestaShop.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz być automatycznie informowany o wydaniu nowej wersji modułu, aby móc korzystać z najnowszych ulepszeń i zapewnić, że Twój sklep pozostaje bezpieczny i funkcjonalny.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Przycisk „Aktualizuj kursy” | Kliknij po konfiguracji / ręcznie w razie potrzeby | Natychmiast pobiera i stosuje najnowsze kursy wymiany z Banku Włoch. |
| Strona konfiguracji modułu | „Adres URL CRON do automatycznych aktualizacji” | Skopiuj i skonfiguruj na hostingu | Automatyzuje codzienne/godzinne aktualizacje kursów wymiany, zapewniając stałą dokładność. |
| Strona konfiguracji modułu | „Dodaj marżę do kursów wymiany (%)” | 0 (lub 1-3% w razie potrzeby) | Dodaje procentowy bufor do kursów wymiany, aby pokryć opłaty lub chronić marże zysku. |
| Strona konfiguracji modułu | „Sprawdź aktualizacje modułu” | TAK | Powiadamia o nowych wersjach modułu w celu poprawek błędów, funkcji i kompatybilności. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy wymiany nie aktualizują się automatycznie. Co powinienem zrobić?**
O1: Jest to prawie zawsze związane z konfiguracją zadania cron.
-   **Sprawdź swój hosting:** Zaloguj się do panelu sterowania swojego hostingu (cPanel, Plesk itp.) i sprawdź, czy zadanie cron dla adresu URL modułu jest poprawnie skonfigurowane i uruchamia się w określonych odstępach czasu. Upewnij się, że adres URL skopiowany z konfiguracji modułu jest dokładny.
-   **Przetestuj adres URL ręcznie:** Skopiuj „Adres URL CRON do automatycznych aktualizacji” z konfiguracji modułu i wklej go bezpośrednio do przeglądarki internetowej. Jeśli uruchomi się pomyślnie, powinieneś zobaczyć prostą wiadomość „OK” lub podobną. Jeśli widzisz błąd, może to być problem po stronie serwera lub problem z samym adresem URL.
-   **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w panelu administracyjnym PrestaShop.

**P2: Kliknąłem „Aktualizuj kursy”, ale moje ceny w innych walutach się nie zmieniły.**
O2:
-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). PrestaShop często buforuje konwersje walut.
-   **Zweryfikuj aktywne waluty:** Upewnij się, że waluty, które mają być aktualizowane, są faktycznie włączone w **Międzynarodowe > Waluty**. Moduł aktualizuje tylko aktywne waluty.
-   **Sprawdź domyślną walutę:** Moduł aktualizuje *inne* waluty w stosunku do Twojej domyślnej waluty (zazwyczaj EUR). Jeśli Twoja domyślna waluta nie jest EUR, moduł nadal będzie pobierał kursy EUR i przeliczał z nich. Upewnij się, że Twoja domyślna waluta jest poprawnie ustawiona.

**P3: Czy mogę ustawić różne marże dla różnych walut?**
O3: Nie, ustawienie „Dodaj marżę do kursów wymiany (%)” stosuje jedną, jednolitą procentową marżę do *wszystkich* kursów wymiany pobranych przez moduł. Jeśli potrzebujesz bardzo specyficznych marż dla poszczególnych walut, będziesz potrzebować niestandardowego rozwiązania deweloperskiego lub bardziej zaawansowanego modułu do zarządzania walutami.

**P4: Moduł twierdzi, że pobiera kursy z Banca d’Italia. Czy to jest wiarygodne?**
O4: Tak, Banca d’Italia (Bank Włoch) jest bankiem centralnym w ramach Europejskiego Systemu Banków Centralnych (ESBC) i dostarcza oficjalne referencyjne kursy euro. Kursy te są bardzo wiarygodne i szeroko stosowane w transakcjach finansowych w całej Europie.

**P5: Po zaktualizowaniu modułu mój sklep wygląda trochę dziwnie lub widzę błędy.**
O5:
-   **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) po każdej aktualizacji modułu.
-   **Pamięć podręczna przeglądarki:** Wyczyść pamięć podręczną i pliki cookie przeglądarki internetowej lub spróbuj uzyskać dostęp do swojego sklepu w trybie incognito/prywatnym.
-   **Przywróć (jeśli to konieczne):** Jeśli problem nadal występuje, może być konieczne tymczasowe wyłączenie lub odinstalowanie modułu i przywrócenie poprzedniej kopii zapasowej sklepu. Następnie skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły problemu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Bank Włoch (Banca dItalia) - kursy wymiany walut” (`birates`) to lekki moduł PrestaShop zaprojektowany do automatyzacji aktualizacji kursów walut. W stosownych przypadkach stosuje standardowy wzorzec PrestaShop MVC, koncentrując się głównie na pojedynczym interfejsie konfiguracji i kontrolerze frontowym do wykonywania zadań cron. Wykorzystuje `ObjectModel` `Currency` PrestaShop do aktualizacji kursów wymiany. Podstawowa logika znajduje się w głównym pliku modułu, obsługując instalację, deinstalację, konfigurację i proces pobierania kursów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `BiratesCronjobModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest przeznaczony do wywoływania przez zewnętrzne zadanie cron. Jego metoda `initContent()` (lub podobna logika w `postProcess()`) wyzwala metodę `updateRates()` głównego modułu `birates`. Nie renderuje żadnej zawartości wizualnej dla użytkownika; jego celem jest wyłącznie wykonanie logiki aktualizacji kursów w tle. Zazwyczaj wyświetla prostą wiadomość o sukcesie lub status.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `BiratesIndexModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to kontroler frontowy zastępczy lub awaryjny. W wielu modułach kontrolery `index.php` są używane do definiowania domyślnej trasy lub obsługi przypadków, w których nie podano konkretnej akcji. Dla tego modułu prawdopodobnie służy jako podstawowy punkt wejścia, ale główna funkcjonalność aktualizacji kursów jest obsługiwana przez `cronjob.php`. Może przekierowywać lub po prostu wyświetlać minimalną stronę.
-   **Kontrolery administracyjne Back-Office**:

    -   W tym module nie ma dedykowanych kontrolerów administracyjnych. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu `birates.php`.

### 4.3 Podstawowe klasy i modele (`classes/`)

W katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Moduł bezpośrednio współdziała z podstawowym `ObjectModel` `Currency` PrestaShop w celu aktualizacji istniejących kursów wymiany walut.

### 4.4 Zasoby JavaScript (`views/js/`)

W module nie ma niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

W module nie ma niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `birates/views/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu `birates.php`. Wyświetla cały formularz konfiguracji modułu w panelu administracyjnym PrestaShop.
        -   **Zawartość**: Zawiera przycisk „Aktualizuj kursy”, pole adresu URL CRON, pole wprowadzania „Dodaj marżę do kursów wymiany (%)” i przełącznik „Sprawdź aktualizacje modułu”. Wykorzystuje standardowe pomocniki formularzy i stylizację PrestaShop.
-   **Szablony hooków (`views/templates/hook/`)**: Brak.
-   **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. `mypresta_updates`, `update_`, `updatev_`, `currency_`) w tabeli `ps_configuration` (lub `_configuration` w zależności od prefiksu tabeli). Te klucze są zazwyczaj poprzedzone nazwą modułu lub unikalnym identyfikatorem.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Nie jest bezpośrednio używany do wyświetlania wizualnego, ale może być używany do ładowania zasobów (chociaż żadne nie są obecne). |
| `displayRightColumn` | W prawej kolumnie stron front-office. | Nie jest używany do wyświetlania wizualnego. |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | Nie jest używany do wyświetlania wizualnego. |
| `displayFooter` | Na dole każdej strony front-office. | Nie jest używany do wyświetlania wizualnego. |
| `displayProductExtraContent` | Na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Nie jest używany do wyświetlania wizualnego. |
| `actionUpdateCurrency` | Po zaktualizowaniu waluty. | Moduł sam *wyzwala* aktualizacje walut, ale nie jest jawnie podłączony do tego w swojej własnej logice. |
| `actionModuleInstall` | Podczas instalacji modułu. | Używany do ustawiania domyślnych wartości konfiguracyjnych i rejestrowania hooków. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Używany do czyszczenia wartości konfiguracyjnych i wyrejestrowywania hooków. |

*Uwaga: Główna funkcja modułu (aktualizacja kursów) jest inicjowana przez jego kontroler frontowy `cronjob.php`, który jest wywoływany zewnętrznie, a nie za pośrednictwem standardowego hooka PrestaShop.*

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji i pobrania najnowszej wersji modułu „Bank Włoch (Banca dItalia) - kursy wymiany walut” odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
