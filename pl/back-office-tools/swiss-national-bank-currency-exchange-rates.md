---
title: "Szwajcarski Bank Narodowy - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Szwajcarski Bank Narodowy - kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Szwajcarski Bank Narodowy - kursy wymiany walut"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Swiss National Bank - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/swiss-national-bank-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/swiss-national-bank-currency-exchange-rates/)
>
> ---


# Szwajcarski Bank Narodowy - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych. Twoje środowisko hostingowe musi również obsługiwać zadania CRON dla automatycznych aktualizacji.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do głównej strony ustawień modułu. Tutaj zdefiniujesz, w jaki sposób moduł pobiera i stosuje kursy wymiany.

#### **1. Adres URL CRON**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, który musisz skonfigurować jako zadanie CRON na swoim serwerze WWW. Po uzyskaniu dostępu do tego adresu URL moduł automatycznie pobierze najnowsze kursy wymiany ze Szwajcarskiego Banku Narodowego i zaktualizuje je w Twoim sklepie PrestaShop.
- **Efekt zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł.
  - *Po prawidłowym skonfigurowaniu jako zadanie CRON:* Twoje kursy wymiany będą automatycznie aktualizowane z częstotliwością, którą zdefiniujesz (np. codziennie, co godzinę).
  - *Po NIE skonfigurowaniu jako zadanie CRON:* Twoje kursy wymiany nie będą automatycznie aktualizowane, a Ty będziesz musiał ręcznie wywołać aktualizację, odwiedzając ten adres URL w swojej przeglądarce, co niweczy cel automatyzacji.
- **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go jako zadanie CRON na swoim serwerze hostingowym.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoje kursy wymiany aktualizowały się każdego ranka o 3:00. Kopiujesz ten adres URL i dodajesz go do harmonogramu zadań CRON w panelu sterowania swojego hostingu, ustawiając go na codzienne uruchamianie o 3:00.

#### **2. Marża kursu wymiany (%)**

- **Co robi to ustawienie:** Pozwala dodać procentową marżę do kursów wymiany pobranych ze Szwajcarskiego Banku Narodowego. Ta marża jest stosowana powyżej kursu bazowego.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na 0 (domyślnie):* Kursy wymiany będą aktualizowane dokładnie tak, jak podane przez SNB.
  - *Gdy ustawione na wartość dodatnią (np. 2):* Kurs wymiany zostanie zwiększony o ten procent. Na przykład, jeśli kurs SNB wynosi 1 EUR = 1.10 CHF, a Ty ustawisz marżę 2%, Twój sklep użyje 1 EUR = 1.122 CHF (1.10 \* 1.02). Oznacza to, że produkty wycenione w CHF będą wydawać się nieco droższe po przeliczeniu na EUR.
- **Zalecana wartość:** Zacznij od 0. Zwiększaj tylko wtedy, gdy musisz uwzględnić opłaty bramki płatniczej, koszty przewalutowania lub wbudować niewielką marżę zysku w swoje międzynarodowe ceny.
- **Scenariusz / przykład dla sprzedawcy:** Twój procesor płatności pobiera 1,5% opłaty za międzynarodowe przewalutowania. Aby pokryć ten koszt, ustawiasz „Marżę kursu wymiany” na 1,5%. Zapewnia to, że Twoje marże zysku nie zostaną zmniejszone przez opłaty za przewalutowanie.

#### **3. Przycisk Zapisz**

- **Co robi to ustawienie:** Ten przycisk zapisuje wszelkie zmiany wprowadzone w ustawieniu „Marża kursu wymiany”.
- **Efekt zmiany tego ustawienia:** Kliknięcie „Zapisz” stosuje ustawienie marży. Adres URL CRON jest statyczny i nie wymaga zapisywania.
- **Zalecana wartość:** Zawsze klikaj „Zapisz” po dostosowaniu marży.
- **Scenariusz / przykład dla sprzedawcy:** Zdecydowałeś się dodać marżę 1%. Po wpisaniu „1” w polu marży klikasz „Zapisz”, aby upewnić się, że to ustawienie zostanie zastosowane do przyszłych aktualizacji kursów.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | Adres URL CRON | Wygenerowany przez moduł | Adres URL do skonfigurowania jako zadanie CRON w celu automatycznej aktualizacji kursów wymiany. |
| Strona konfiguracji modułu | Marża kursu wymiany (%) | 0 | Procentowa marża dodawana do pobranych kursów wymiany. |
| Strona konfiguracji modułu | Przycisk Zapisz | Zawsze klikaj po zmianie marży | Zapisuje zmiany w ustawieniu marży. |

## 3. Często zadawane pytania (FAQ)

**P: Czy moduł obsługuje wszystkie waluty?**
O: Moduł pobiera kursy wymiany ze Szwajcarskiego Banku Narodowego. Obsługuje waluty, dla których SNB dostarcza dane. Zazwyczaj obejmuje to główne waluty światowe (EUR, USD, GBP itp.) w stosunku do CHF.

**P: Czy muszę ręcznie aktualizować kursy wymiany?**
O: Nie, głównym celem modułu jest automatyzacja tego procesu. Po skonfigurowaniu zadania CRON, moduł będzie automatycznie aktualizował kursy wymiany z częstotliwością, którą ustawisz (np. codziennie, co godzinę).

**P: Co to jest zadanie CRON i jak je skonfigurować?**
O: Zadanie CRON to zaplanowane zadanie, które Twój serwer wykonuje automatycznie w określonych odstępach czasu. Aby je skonfigurować, musisz skopiować adres URL CRON z konfiguracji modułu i dodać go do harmonogramu zadań CRON w panelu sterowania swojego hostingu (np. cPanel, Plesk). Dokładne kroki mogą się różnić w zależności od dostawcy hostingu, ale zazwyczaj polega to na dodaniu polecenia `wget -q -O /dev/null "TWÓJ_ADRES_URL_CRON"` lub `curl -s "TWÓJ_ADRES_URL_CRON" > /dev/null`.

**P: Czy mogę dodać marżę do kursów wymiany?**
O: Tak, moduł pozwala ustawić procentową marżę, która zostanie dodana do pobranych kursów wymiany. Jest to przydatne do pokrycia opłat transakcyjnych lub dostosowania strategii cenowej.

**P: Co się stanie, jeśli Szwajcarski Bank Narodowy zmieni swoje API?**
O: Moduł jest zaprojektowany tak, aby był odporny na drobne zmiany. W przypadku większych zmian w API SNB, MyPresta.eu wyda aktualizację modułu, aby zapewnić jego dalsze działanie. Zawsze upewnij się, że używasz najnowszej wersji modułu.

**P: Czy ten moduł wpływa na wydajność mojego sklepu?**
O: Moduł działa w tle i jest wywoływany tylko przez zadanie CRON. Nie ma bezpośredniego wpływu na wydajność front-office Twojego sklepu podczas przeglądania przez klientów. Proces aktualizacji kursów jest szybki i nie powinien obciążać serwera.

**P: Moje kursy wymiany nie aktualizują się. Co powinienem sprawdzić?**
O:
1.  Upewnij się, że zadanie CRON jest poprawnie skonfigurowane na Twoim serwerze hostingowym i że adres URL CRON jest prawidłowy.
2.  Sprawdź logi serwera lub logi CRON pod kątem błędów.
3.  Upewnij się, że waluty, które chcesz aktualizować, są aktywne w Twoim sklepie PrestaShop (Panel administracyjny > Lokalizacja > Waluty).
4.  Sprawdź, czy Twój hosting ma włączone wymagane rozszerzenia PHP (cURL, JSON, OpenSSL).
5.  Upewnij się, że moduł jest włączony i skonfigurowany w Panelu administracyjnym PrestaShop.

**P: Czy moduł używa franka szwajcarskiego (CHF) jako waluty bazowej?**
O: Tak, moduł pobiera dane ze Szwajcarskiego Banku Narodowego, który używa CHF jako waluty bazowej. Moduł inteligentnie przelicza kursy, aby były zgodne z walutą bazową Twojego sklepu PrestaShop.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł przestrzega minimalistycznej architektury modułu PrestaShop. Jego główną funkcją jest okresowe pobieranie kursów wymiany z zewnętrznego API (Szwajcarski Bank Narodowy) i aktualizowanie tabeli `currency` w bazie danych PrestaShop. Główna logika znajduje się w głównym pliku modułu (`snbrates/cronjob.php`) i jest wywoływana przez kontroler front-office, zaprojektowany do wywoływania przez zadanie CRON. Wykorzystuje klasę `Configuration` PrestaShop do przechowywania ustawień i `Currency` ObjectModel do aktualizacji kursów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Te kontrolery są zaprojektowane do zewnętrznego dostępu, głównie przez zadania CRON.

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna:** `SnbratesCronjobModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność:** Jest to główny punkt wejścia dla zautomatyzowanej aktualizacji kursów. Gdy adres URL tego kontrolera zostanie wywołany (np. `twoj_sklep.com/module/snbrates/cronjob`), wykonuje on logikę w celu:
            1.  Pobrania najnowszych kursów wymiany z skonfigurowanego punktu końcowego API SNB.
            2.  Zastosowania skonfigurowanej marży (jeśli istnieje).
            3.  Zaktualizowania `conversion_rate` dla każdej aktywnej waluty w bazie danych PrestaShop, używając CHF jako waluty bazowej.
            4.  Nie renderuje żadnych wizualnych danych wyjściowych do przeglądarki, zazwyczaj zwracając prostą wiadomość o sukcesie/niepowodzeniu lub przekierowując.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna:** `SnbratesIndexModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność:** Jest to kontroler-placeholder, często dołączany do modułów, ale nieużywany bezpośrednio do podstawowej funkcjonalności tego konkretnego modułu. Może być używany do prostych przekierowań lub do zapobiegania listowaniu katalogów, jeśli jest dostępny bezpośrednio, ale nie zawiera specyficznej logiki biznesowej dla aktualizacji kursów.
-   **Kontrolery administracyjne Back-Office**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Moduł nie wprowadza żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowy `Currency` ObjectModel PrestaShop do zarządzania danymi walutowymi i `Configuration` do ustawień modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Brak. Moduł nie używa żadnego niestandardowego JavaScriptu.

### 4.5 Arkusze stylów CSS (`views/css/`)

Brak. Moduł nie używa żadnego niestandardowego CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Cel:** Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu (`snbrates/cronjob.php`) w celu wyświetlenia formularza konfiguracji modułu w Panelu administracyjnym PrestaShop.
        -   **Zawartość:** Zazwyczaj zawiera pola formularza dla „Adresu URL CRON” (tylko wyświetlanie) i „Marży kursu wymiany (%)” (pole wprowadzania), wraz z przyciskiem „Zapisz”. Wykorzystuje standardowe funkcje pomocnicze PrestaShop do renderowania formularzy.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Współpracuje z podstawową tabelą PrestaShop `ps_currency`, w szczególności aktualizując kolumnę `conversion_rate` dla aktywnych walut.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. `SNBRATES_MARGIN`) w tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie żadnych hooków wyświetlania front-office (takich jak `displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductButtons` itp.), ponieważ jego główną funkcją jest przetwarzanie danych w tle. „Hooki Front-Office: Nagłówek, Kolumny, Produkt lub Stopka” wspomniane w zapytaniu mogą odnosić się do ogólnej możliwości lub nieporozumienia, ponieważ podstawowa funkcja modułu nie obejmuje renderowania treści w tych obszarach.

    Moduł niejawnie używa następujących hooków:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | :---------- | :------------- | :------------- |
    | `actionModuleInstall` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne. |
    | `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wartości konfiguracyjne. |
    | (Wewnętrzne) `ModuleFrontController` dispatch | Gdy adres URL CRON jest wywoływany | Wywołuje logikę aktualizacji kursów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz upewnienia się, że używasz najnowszej kompatybilnej wersji modułu „Szwajcarski Bank Narodowy - kursy wymiany walut”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
