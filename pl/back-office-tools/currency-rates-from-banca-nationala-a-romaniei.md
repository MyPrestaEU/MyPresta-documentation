---
title: "Kursy walut z Banca Nationala a Romaniei - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop „Kursy walut z Banca Nationala a Romaniei” od MyPresta.eu."
sidebar:
  label: "Kursy walut z Banca Nationala a Romaniei - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Currency rates from Banca Nationala a Romaniei na MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-banca-nationala-a-romaniei.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/currency-rates-from-banca-nationala-a-romaniei/)
>
> ---


# Kursy walut z Banca Nationala a Romaniei

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania zewnętrznych kanałów danych, które są standardem w większości nowoczesnych środowisk hostingowych.

## 2. Pełny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień.

#### **Ustawienia i opcje**

1.  **Sprawdź aktualizacje modułu**

    *   **Co robi to ustawienie:** Ten przełącznik kontroluje, czy moduł okresowo sprawdza MyPresta.eu pod kątem nowych wersji lub ważnych aktualizacji.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone (TAK):* Moduł będzie sporadycznie łączyć się z MyPresta.eu, aby sprawdzić, czy dostępna jest nowsza wersja. Jeśli zostanie znaleziona aktualizacja, w panelu administracyjnym PrestaShop może pojawić się powiadomienie, zachęcające do pobrania i zainstalowania jej.
        *   *Gdy wyłączone (NIE):* Moduł nie będzie automatycznie sprawdzać aktualizacji. Będziesz musiał ręcznie sprawdzić swoje konto MyPresta.eu pod kątem nowych wersji.
    *   **Zalecana wartość:** **TAK**. Zawsze zaleca się aktualizowanie modułów, aby korzystać z nowych funkcji, poprawek błędów i ulepszeń bezpieczeństwa.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że moduł kursów walut zawsze działa w najnowszej, najbardziej stabilnej wersji, bez konieczności ciągłego ręcznego sprawdzania. Włączenie tej opcji powiadomi Cię, gdy aktualizacja będzie gotowa.
2.  **Aktualizuj kursy walut**

    *   **Co robi to ustawienie:** To jest podstawowa funkcja modułu. Po kliknięciu tego przycisku moduł natychmiast pobierze najnowsze kursy wymiany z Banca Naţională a României (BNR) i zastosuje je do walut skonfigurowanych w Twoim sklepie PrestaShop.
    *   **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku powoduje natychmiastową aktualizację wszystkich kursów wymiany w Twoim sklepie na podstawie kanału BNR. Jest to ręczne wyzwalanie procesu aktualizacji.
    *   **Zalecana wartość:** To jest przycisk akcji, a nie ustawienie. Kliknij go, gdy potrzebujesz natychmiastowej aktualizacji lub po skonfigurowaniu walut.
    *   **Scenariusz / przykład dla sprzedawcy:** Jest początek dnia handlowego i chcesz upewnić się, że wszystkie Twoje ceny odzwierciedlają najnowsze kursy wymiany, zanim klienci zaczną składać zamówienia. Kliknąłbyś ten przycisk.
3.  **Adres URL zadania cron**

    *   **Co robi to ustawienie:** To pole wyświetla unikalny adres URL, którego możesz użyć do automatyzacji aktualizacji kursów walut. Ten adres URL jest przeznaczony do wywoływania przez „zadanie cron” na Twoim serwerze WWW, które jest zaplanowanym zadaniem uruchamianym automatycznie w określonych odstępach czasu (np. raz dziennie, co godzinę).
    *   **Efekt zmiany tego ustawienia:** To jest pole tylko do wyświetlania. Skopiowanie i ustawienie tego adresu URL w harmonogramie zadań cron w panelu hostingowym zapewni, że kursy walut będą aktualizowane automatycznie, bez konieczności ręcznego klikania przycisku „Aktualizuj kursy walut”.
    *   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj zadanie cron na swoim serwerze, aby uruchamiało je co najmniej raz dziennie lub częściej, jeśli wymaga tego Twoja firma.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kursy walut aktualizowały się automatycznie każdego ranka o 6:00, nawet gdy nie ma Cię przy komputerze. Skopiowałbyś ten adres URL i skonfigurował zadanie cron na swoim serwerze hostingowym, aby wykonywało je codziennie o 6:00.
4.  **Waluta do aktualizacji**

    *   **Co robi to ustawienie:** Ta lista rozwijana pozwala wybrać, które konkretne waluty w Twoim sklepie PrestaShop powinny być aktualizowane przez kanał BNR. Kanał BNR dostarcza głównie kursy w stosunku do RON. Moduł następnie przeliczy je na domyślną walutę Twojego sklepu, a następnie na inne wybrane waluty.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrana jest konkretna waluta:* Tylko kurs wymiany tej waluty zostanie zaktualizowany przez moduł.
        *   *Gdy wybrane jest „Wszystkie waluty”:* Moduł spróbuje zaktualizować wszystkie aktywne waluty w Twoim sklepie PrestaShop przy użyciu kanału BNR.
    *   **Zalecana wartość:** **Wszystkie waluty**, chyba że masz konkretny powód, aby aktualizować tylko jedną. Zapewnia to spójność wszystkich Twoich międzynarodowych cen.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój sklep akceptuje EUR, USD i GBP. Chcesz, aby wszystkie te waluty były codziennie aktualizowane na podstawie przeliczenia BNR na RON, a następnie na domyślną walutę Twojego sklepu. Wybrałbyś „Wszystkie waluty”. Gdybyś z jakiegoś powodu chciał aktualizować tylko EUR, wybrałbyś „EUR”.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Sprawdź aktualizacje modułu | TAK | Włącza automatyczne sprawdzanie nowych wersji modułu. |
| Konfiguracja modułu | Aktualizuj kursy walut | N/A (przycisk akcji) | Ręcznie wyzwala natychmiastową aktualizację wszystkich wybranych kursów walut z BNR. |
| Konfiguracja modułu | Adres URL zadania cron | N/A (tylko wyświetlanie) | Udostępnia adres URL do skonfigurowania zautomatyzowanego zadania cyklicznego dla aktualizacji kursów walut. |
| Konfiguracja modułu | Waluta do aktualizacji | Wszystkie waluty | Określa, które waluty w Twoim sklepie otrzymają automatyczne aktualizacje kursów z BNR. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy walut nie aktualizują się. Co powinienem sprawdzić w pierwszej kolejności?**
O1:

1.  **Ręczna aktualizacja:** Przejdź do strony konfiguracji modułu i kliknij przycisk „Aktualizuj kursy walut”. Jeśli to zadziała, problem prawdopodobnie leży w konfiguracji zadania cron.
2.  **Zadanie Cron:** Dokładnie sprawdź, czy zadanie cron jest poprawnie skonfigurowane na Twoim serwerze hostingowym, używając dokładnego „Adresu URL zadania cron” dostarczonego przez moduł. Upewnij się, że jest ustawione na uruchamianie z pożądaną częstotliwością.
3.  **Ustawienia modułu:** Sprawdź, czy w rozwijanej liście „Waluta do aktualizacji” wybrano „Wszystkie waluty” lub konkretne waluty, które chcesz aktualizować.
4.  **Waluty PrestaShop:** Upewnij się, że waluty, które mają być aktualizowane, są aktywne w Twoim sklepie PrestaShop (Międzynarodowe > Waluty).
5.  **Łączność z serwerem:** Upewnij się, że Twój serwer ma dostęp do zewnętrznych stron internetowych (konkretnie do kanału BNR). Czasami reguły zapory sieciowej lub problemy z siecią mogą to uniemożliwić.

**P2: Moduł twierdzi, że zaktualizował, ale ceny w moim front-office nie wydają się prawidłowe.**
O2:

1.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Zapewnia to, że Twój sklep wyświetla najnowsze dane.
2.  **Pamięć podręczna przeglądarki:** Wyczyść pamięć podręczną i pliki cookie przeglądarki lub spróbuj wyświetlić swój sklep w oknie incognito/prywatnym, aby wykluczyć problemy z lokalną pamięcią podręczną.
3.  **Wybór waluty:** Upewnij się, że przeglądasz ceny w prawidłowej walucie w front-office.

**P3: Czy mogę aktualizować kursy częściej niż raz dziennie?**
O3: Tak, możesz. Konfigurując zadanie cron, możesz ustawić je tak, aby uruchamiało się co godzinę, co kilka godzin lub w dowolnym interwale obsługiwanym przez harmonogram zadań cron Twojego dostawcy hostingu. Pamiętaj tylko o potencjalnym obciążeniu serwera, jeśli ustawisz je na uruchamianie bardzo często (np. co minutę), chociaż w przypadku aktualizacji walut rzadko stanowi to problem.

**P4: Co się stanie, jeśli kanał BNR będzie tymczasowo niedostępny?**
O4: Jeśli kanał BNR będzie niedostępny, moduł prawdopodobnie nie będzie w stanie pobrać nowych kursów. Nie usunie ani nie zresetuje Twoich istniejących kursów; po prostu pozostaną one niezmienione, dopóki kanał nie stanie się ponownie dostępny i nie nastąpi pomyślna aktualizacja. W dziennikach zadań cron Twojego serwera może pojawić się komunikat o błędzie, jeśli aktualizacja się nie powiedzie.

**P5: Domyślna waluta mojego sklepu nie jest RON. Czy ten moduł nadal będzie działać?**
O5: Tak, absolutnie. Moduł jest zaprojektowany tak, aby działał niezależnie od domyślnej waluty Twojego sklepu. Pobiera kursy BNR (które są zazwyczaj w stosunku do RON), a następnie inteligentnie przelicza je na domyślną walutę Twojego sklepu, a następnie na wszelkie inne aktywne waluty, które włączyłeś do aktualizacji.

## 4. Przewodnik dla deweloperów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Kursy walut z Banca Nationala a Romaniei” to prosty moduł PrestaShop, skupiający się głównie na jednym zadaniu: pobieraniu i aktualizowaniu kursów wymiany walut. Przestrzega podstawowej struktury modułu PrestaShop, wykorzystując klasę `Module` do instalacji i konfiguracji oraz `ModuleFrontController` do funkcji zadania cron. Nie wprowadza niestandardowych klas `ObjectModel` ani tabel baz danych, opierając się zamiast tego na podstawowej klasie `Currency` PrestaShop i tabeli `Configuration` dla ustawień. Podstawowa logika obejmuje parsowanie kanału XML z BNR i aktualizowanie istniejących kursów walut.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są zaprojektowane do dostępu zewnętrznego, głównie do automatyzacji zadań cron.

-   `controllers/front/cronjob.php`
    *   **Nazwa klasy i klasa nadrzędna:** `BnrratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
    *   **Odpowiedzialność:** Jest to dedykowany punkt końcowy dla zautomatyzowanego zadania cron aktualizacji walut. Po uzyskaniu dostępu, wyzwala podstawową logikę modułu, aby pobrać najnowsze kursy wymiany z BNR i zaktualizować je w bazie danych PrestaShop. Zazwyczaj zwraca prosty komunikat o sukcesie lub błędzie, odpowiedni do logowania zadań cron. Nie renderuje żadnego wizualnego wyjścia dla przeglądarki.
-   `controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** `BnrratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako rezerwowy lub domyślny punkt wejścia, chociaż jego podstawowa funkcja może być minimalna, biorąc pod uwagę jawny kontroler `cronjob.php`. W wielu modułach kontroler front-office `index.php` może przekierowywać lub wyświetlać prosty komunikat, jeśli jest dostępny bezpośrednio bez określonych parametrów. W przypadku tego modułu jego praktyczne zastosowanie jest prawdopodobnie ograniczone, a `cronjob.php` obsługuje główną interakcję z front-office.

#### Kontrolery administracyjne Back-Office

Moduł nie implementuje żadnych niestandardowych klas `AdminController`. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Podstawowe klasy i modele (`classes/`)

Moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Bezpośrednio współdziała z podstawowymi klasami PrestaShop `Currency` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `bnrrates/views/admin.tpl`
        *   **Cel:** Ten szablon jest odpowiedzialny za renderowanie formularza konfiguracji modułu w Panelu administracyjnym PrestaShop. Wyświetla ustawienia takie jak „Sprawdź aktualizacje modułu”, przycisk „Aktualizuj kursy walut”, „Adres URL zadania cron” i rozwijaną listę „Waluta do aktualizacji”.
        *   **Zmienne:** Zazwyczaj otrzymuje zmienne z metody `getContent()` głównego pliku modułu, takie jak bieżące wartości ustawień konfiguracji i wygenerowany adres URL zadania cron.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    *   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Odpowiednie klucze konfiguracyjne to:
        *   `BNRRATES_MYPRESTA_UPDATES`: Przechowuje wartość logiczną dla sprawdzania aktualizacji modułu.
        *   `BNRRATES_CURRENCY_TO_UPDATE`: Przechowuje ID waluty do aktualizacji lub specjalną wartość (np. `0` lub `all`) dla wszystkich walut.
        *   `BNRRATES_LAST_UPDATE_TIME`: (Prawdopodobnie) Przechowuje znacznik czasu ostatniej udanej aktualizacji.
        *   `BNRRATES_CRON_TOKEN`: Przechowuje unikalny token używany w adresie URL zadania cron dla bezpieczeństwa.
-   **Tabela zarejestrowanych hooków**:
    Moduł wykorzystuje głównie hooki `action` do swojej podstawowej funkcjonalności i potencjalnie hooki `display` do powiadomień lub określonej zawartości (chociaż w dostarczonych informacjach nie ma wyraźnie wymienionych żadnych konkretnych hooków wyświetlania front-office, opis modułu wspomina o „Nagłówku, Kolumnach, Produkcie lub Stopce” jako potencjalnych obszarach, co oznaczałoby `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons`, `displayFooter` itp. Jednakże, biorąc pod uwagę cel modułu, byłyby one prawdopodobnie używane do wyświetlania powiadomienia lub statusu, a nie do podstawowej funkcjonalności).

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionModuleInstall` | Podczas instalacji modułu | Rejestruje konfigurację modułu, tworzy domyślne ustawienia. |
| `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści konfigurację modułu z `ps_configuration`. |
| `actionAdminControllerSetMedia` | Po załadowaniu kontrolera administracyjnego | Potencjalnie rejestruje CSS/JS dla strony konfiguracji administracyjnej (chociaż w tym module ich nie ma). |
| `displayBackOfficeHeader` | W nagłówku Panelu administracyjnego | Potencjalnie wyświetla powiadomienia o aktualizacjach lub inną zawartość specyficzną dla administratora. |
| `displayHeader` | W sekcji `<head>` front-office | Nie jest bezpośrednio używany do podstawowej funkcjonalności, ale może być używany do meta tagów lub JS/CSS, jeśli jest to potrzebne. |
| `displayLeftColumn` | W lewej kolumnie front-office | Nie jest bezpośrednio używany do podstawowej funkcjonalności, ale może być używany do wyświetlania bloku walut. |
| `displayRightColumn` | W prawej kolumnie front-office | Nie jest bezpośrednio używany do podstawowej funkcjonalności, ale może być używany do wyświetlania bloku walut. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku dodaj do koszyka | Nie jest bezpośrednio używany do podstawowej funkcjonalności, ale może być używany do informacji związanych z walutą. |
| `displayFooter` | W stopce front-office | Nie jest bezpośrednio używany do podstawowej funkcjonalności, ale może być używany do informacji związanych z walutą. |

Podstawowa logika aktualizacji walut jest wyzwalana przez dostęp do kontrolera front-office `cronjob.php`, który nie jest standardowym hookiem PrestaShop, ale zewnętrznym punktem końcowym.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Kursy walut z Banca Nationala a Romaniei”, prosimy zalogować się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
