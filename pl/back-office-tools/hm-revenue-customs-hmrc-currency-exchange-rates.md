---
title: "HM Revenue & Customs (HMRC) - kursy wymiany walut - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop HM Revenue & Customs (HMRC) - kursy wymiany walut od MyPresta.eu."
sidebar:
  label: "HM Revenue & Customs (HMRC) - kursy wymiany walut - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł HM Revenue & Customs (HMRC) - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/hm-revenue-customs-hmrc-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/hm-revenue-customs-hmrc-currency-exchange-rates/)
>
> ---


# HM Revenue & Customs (HMRC) - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych, co jest standardem w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu HMRC Currency Rates. Tutaj ustawisz, w jaki sposób moduł pobiera i stosuje oficjalne kursy wymiany.

Strona konfiguracji przedstawi Ci następujące kluczowe informacje i ustawienia:

#### **URL zadania Cron**

-   **Co robi to ustawienie:** Jest to specjalny adres internetowy (URL), który po odwiedzeniu uruchamia moduł w celu pobrania najnowszych kursów wymiany HMRC i zaktualizowania ich w Twoim sklepie PrestaShop. Jest on zaprojektowany do automatycznego uruchamiania przez „zadanie cron” na Twoim serwerze.
-   **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł.
-   **Zalecana wartość:** Skopiuj ten adres URL dokładnie tak, jak się pojawia.
-   **Scenariusz / przykład dla sprzedawcy:** Będziesz potrzebować tego adresu URL do skonfigurowania zautomatyzowanego zadania (zadania cron) na swoim serwerze hostingowym. To zadanie będzie odwiedzać ten adres URL o zaplanowanej godzinie (np. raz dziennie lub raz w miesiącu), aby zapewnić, że Twoje kursy są zawsze aktualne, bez konieczności ręcznego klikania czegokolwiek.

#### **Polecenie zadania Cron (dla serwerów Linux/Unix)**

-   **Co robi to ustawienie:** Jest to instrukcja wiersza poleceń, która osiąga ten sam rezultat co odwiedzenie adresu URL zadania Cron, ale jest specjalnie sformatowana do bezpośredniego użycia w harmonogramie zadań cron serwera (często znajduje się w panelu sterowania hostingu, takim jak cPanel lub Plesk). Używa `wget` lub `curl` do cichego żądania adresu URL.
-   **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego polecenia. Jest ono generowane przez moduł.
-   **Zalecana wartość:** Skopiuj to polecenie dokładnie tak, jak się pojawia.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój dostawca hostingu używa serwerów Linux/Unix (co robi większość), użyjesz tego polecenia do skonfigurowania zautomatyzowanego zadania cron. Jest to zazwyczaj bardziej niezawodne niż poleganie na usługach cron opartych na sieci.

#### **Status ostatniej aktualizacji**

-   **Co robi to ustawienie:** Ta sekcja wyświetla informacje o tym, kiedy moduł ostatnio pomyślnie pobrał i zaktualizował kursy HMRC. Pokaże datę i godzinę ostatniej aktualizacji.
-   **Wpływ zmiany tego ustawienia:** Jest to tylko wyświetlanie informacji; nie możesz tego zmienić.
-   **Zalecana wartość:** Monitoruj to, aby upewnić się, że Twoje zadanie cron działa poprawnie, a kursy są regularnie aktualizowane.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli skonfigurujesz swoje zadanie cron tak, aby uruchamiało się codziennie, powinieneś widzieć, że „Status ostatniej aktualizacji” zmienia się codziennie, potwierdzając, że moduł działa zgodnie z oczekiwaniami. Jeśli nie aktualizuje się, wskazuje to na problem z konfiguracją zadania cron.

#### **Przycisk „Aktualizuj teraz”**

-   **Co robi to ustawienie:** Ten przycisk umożliwia ręczne natychmiastowe uruchomienie procesu aktualizacji kursów, bezpośrednio ze strony konfiguracji modułu.
-   **Wpływ zmiany tego ustawienia:** Kliknięcie tego przycisku natychmiast pobierze najnowsze kursy HMRC i zastosuje je do walut Twojego sklepu.
-   **Zalecana wartość:** Użyj tego przycisku do wstępnego testowania po instalacji lub jeśli musisz wymusić natychmiastową aktualizację poza zaplanowanym zadaniem cron.
-   **Scenariusz / przykład dla sprzedawcy:** Po zainstalowaniu modułu kliknij „Aktualizuj teraz”, aby sprawdzić, czy poprawnie pobiera kursy i aby wypełnić swój sklep najnowszymi kursami HMRC przed uruchomieniem pierwszego zaplanowanego zadania cron.

#### **Ważna uwaga dotycząca zadań Cron:**

Podstawowa funkcjonalność tego modułu opiera się na **zadaniu cron** skonfigurowanym na Twoim serwerze WWW. Zadanie cron to harmonogram zadań oparty na czasie w systemach operacyjnych typu Unix. Pozwala użytkownikom planować zadania (polecenia lub skrypty) do cyklicznego uruchamiania o stałych godzinach, datach lub interwałach.

**Jak skonfigurować zadanie cron (ogólne kroki):**

1.  **Uzyskaj dostęp do panelu sterowania hostingu:** Zaloguj się do swojego cPanelu, Pleska lub innego panelu sterowania hostingu.
2.  **Znajdź „Zadania Cron” lub „Zaplanowane zadania”:** Poszukaj sekcji zazwyczaj nazywanej „Zadania Cron”, „Zaplanowane zadania” lub „Automatyzacja”.
3.  **Dodaj nowe zadanie Cron:**
    -   **Częstotliwość:** Ustaw częstotliwość. Dla kursów HMRC zazwyczaj wystarczy miesięcznie (np. „Raz w miesiącu” 1. dnia miesiąca). Niektórzy sprzedawcy wolą codziennie dla dodatkowego bezpieczeństwa, ale kursy HMRC są miesięczne.
    -   **Polecenie:** Wklej „Polecenie zadania Cron” dostarczone przez moduł do pola polecenia.
    -   **E-mail:** Zazwyczaj możesz określić adres e-mail, na który będą wysyłane dane wyjściowe z zadania cron. Jest to przydatne do rozwiązywania problemów, jeśli zadanie się nie powiedzie.
4.  **Zapisz:** Zapisz zadanie cron.

Jeśli nie masz pewności, jak skonfigurować zadanie cron, skontaktuj się z zespołem wsparcia swojego dostawcy hostingu i podaj im „Polecenie zadania Cron” ze strony konfiguracji modułu, prosząc ich o skonfigurowanie go tak, aby uruchamiało się co miesiąc (lub codziennie, zgodnie z Twoimi preferencjami).

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | URL zadania Cron | N/A (Kopiuj i używaj) | URL do wyzwalania aktualizacji kursów; dla usług cron opartych na sieci. |
| Konfiguracja modułu | Polecenie zadania Cron | N/A (Kopiuj i używaj) | Instrukcja wiersza poleceń dla zadań cron opartych na serwerze (np. cPanel). |
| Konfiguracja modułu | Status ostatniej aktualizacji | N/A (Informacyjne) | Pokazuje datę/godzinę ostatniej pomyślnej aktualizacji kursów. |
| Konfiguracja modułu | Przycisk „Aktualizuj teraz” | Kliknij, aby ręcznie zaktualizować | Natychmiast pobiera i stosuje najnowsze kursy HMRC. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy wymiany nie aktualizują się. Co powinienem zrobić?**
O: Najczęstszą przyczyną jest nieprawidłowo skonfigurowane zadanie cron.
1.  **Sprawdź konfigurację zadania cron:** Zaloguj się do panelu sterowania hostingu (cPanel, Plesk itp.) i sprawdź, czy zadanie cron jest poprawnie skonfigurowane przy użyciu „Polecenia zadania Cron” dostarczonego przez moduł. Upewnij się, że częstotliwość jest ustawiona zgodnie z życzeniem (np. miesięcznie lub codziennie).
2.  **Przetestuj ręcznie:** Przejdź do strony konfiguracji modułu w panelu administracyjnym PrestaShop i kliknij przycisk „Aktualizuj teraz”. Jeśli to zadziała, problem na pewno dotyczy konfiguracji zadania cron. Jeśli nie zadziała, może występować problem po stronie serwera uniemożliwiający modułowi pobieranie danych (np. zapora sieciowa, problemy z cURL).
3.  **Skontaktuj się z hostem:** Jeśli nie masz pewności co do zadań cron, podaj swojemu wsparciu hostingowemu „Polecenie zadania Cron” i poproś ich o skonfigurowanie go dla Ciebie.

**P: Czy ten moduł wpływa na ceny, które klienci widzą na mojej stronie internetowej?**
O: Tak, pośrednio. Moduł aktualizuje podstawowe kursy wymiany w PrestaShop. Jeśli Twój sklep pozwala klientom przełączać się między walutami, ceny wyświetlane w tych walutach obcych będą odzwierciedlać zaktualizowane kursy. Jednak głównym celem modułu jest *wewnętrzna* księgowość i zgodność podatkowa, a niekoniecznie dynamiczne strategie cenowe na front-endzie.

**P: Co się stanie, jeśli HMRC zmieni metodę publikacji kursów wymiany?**
O: MyPresta.eu regularnie monitoruje zmiany w usługach zewnętrznych, takich jak HMRC. Jeśli HMRC zmieni swoje źródło danych lub format, wydamy aktualizację modułu, aby zapewnić ciągłą kompatybilność. Zawsze aktualizuj swoje moduły do najnowszych wersji.

**P: Czy mogę używać tego modułu, jeśli moją walutą bazową nie jest GBP?**
O: Chociaż moduł pobiera kursy HMRC, jego główną korzyścią jest zgodność z brytyjskim VAT, która zazwyczaj zakłada GBP jako walutę raportowania. Jeśli Twoja waluta bazowa nie jest GBP, moduł nadal będzie aktualizować kursy wymiany dla innych walut w stosunku do Twojej waluty bazowej, ale będziesz musiał zrozumieć, jak to współdziała z Twoimi konkretnymi zobowiązaniami podatkowymi. Dla brytyjskiego VAT, posiadanie GBP jako domyślnej waluty jest ogólnie zalecane.

**P: Widzę komunikat o błędzie podczas próby ręcznej aktualizacji kursów.**
O: Może to wskazywać na kilka rzeczy:
1.  **Łączność z serwerem:** Twój serwer może nie być w stanie połączyć się ze stroną internetową HMRC w celu pobrania danych. Może to być spowodowane zaporą sieciową, problemem z siecią lub tymczasową niedostępnością serwera HMRC.
2.  **Rozszerzenia PHP:** Upewnij się, że standardowe rozszerzenia PHP, takie jak `cURL` i `JSON`, są włączone na Twoim serwerze.
3.  **Uprawnienia modułu:** Sprawdź, czy pliki modułu mają poprawne uprawnienia do odczytu/zapisu.
Jeśli problem będzie się powtarzał, skontaktuj się z pomocą techniczną MyPresta.eu, podając dokładny komunikat o błędzie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów odpowiedzialnych za utrzymanie lub rozszerzanie sklepu PrestaShop.

### 4.1 Przegląd architektury

Moduł `hmrcrates` to prosty moduł PrestaShop zaprojektowany do pobierania i aktualizowania kursów wymiany walut ze strony internetowej HMRC. Wykorzystuje architekturę modułów PrestaShop, głównie klasę `Module` do instalacji/deinstalacji oraz `ModuleFrontController` do obsługi żądań zadań cron. Główna logika znajduje się w głównym pliku modułu, `cronjob.php`, który działa również jako główny punkt wejścia do konfiguracji i wykonywania zadań cron. Nie używa `ObjectModel`, ponieważ bezpośrednio manipuluje istniejącymi obiektami `Currency`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `HmrcratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest publicznym punktem końcowym dla zadania cron. Po uzyskaniu dostępu za pośrednictwem jego adresu URL (np. `twojasklep.com/module/hmrcrates/cronjob`) wyzwala metodę `processUpdateRates()` w głównym module `hmrcrates`. Jest zaprojektowany do wywoływania przez zewnętrzne usługi cron lub zadania cron po stronie serwera. Wyświetla prosty komunikat o sukcesie lub błędzie.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `HmrcratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to kontroler-placeholder, zazwyczaj używany do zapewnienia domyślnego punktu wejścia dla modułu, jeśli nie zażądano żadnej konkretnej akcji. W kontekście tego modułu prawdopodobnie nie służy żadnemu bezpośredniemu celowi funkcjonalnemu poza zapewnieniem domyślnej trasy, jeśli `cronjob.php` nie jest jawnie wywoływany. Może przekierowywać lub po prostu wyświetlać pustą stronę.
-   **Kontrolery administracyjne Back-Office**:

    -   Ten moduł nie wykorzystuje dedykowanych plików `AdminController`. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas w katalogu `classes/`. Główna logika pobierania i aktualizowania kursów jest hermetyzowana w głównym pliku modułu, `hmrcrates/cronjob.php`. Bezpośrednio współdziała z wbudowaną klasą `Currency` PrestaShop w celu aktualizacji kursów wymiany.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Konfiguracja back-office opiera się na domyślnej stylizacji back-office PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównej klasy modułu (`hmrcrates/cronjob.php`) w celu wyświetlenia formularza konfiguracji modułu w panelu administracyjnym PrestaShop.
        -   **Zawartość**: Zazwyczaj zawiera strukturę HTML do wyświetlania adresu URL zadania Cron, polecenia zadania Cron, statusu ostatniej aktualizacji i przycisku „Aktualizuj teraz”. Wykorzystuje standardowe pomocniki formularzy i stylizację PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. `HMRCRATES_LAST_UPDATE`) w standardowej tabeli PrestaShop `ps_configuration`.
    -   Aktualizuje kolumnę `exchange_rate` w tabeli `ps_currency` dla odpowiednich walut.
-   **Tabela zarejestrowanych hooków**:
    Ten moduł nie rejestruje jawnie żadnych hooków wyświetlania front-office (takich jak `displayHeader`, `displayRightColumn`, `displayFooter`), ponieważ jego funkcjonalność jest czysto backendowa. Jego głównym „hookiem” jest hook `action` wyzwalany przez `ModuleFrontController` dla zadania cron.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionModuleInstall` | Podczas instalacji modułu | Tworzy wpisy konfiguracyjne, konfiguruje początkowe dane. |
| `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wpisy konfiguracyjne. |
| (Niejawny) `actionFrontControllerSetMedia` | Gdy kontroler frontowy jest ładowany | Nie jest jawnie używany przez ten moduł, ale standardowy dla modułów do ładowania zasobów. |
| (Niejawny) `actionDispatcher` | Gdy kontroler frontowy jest wysyłany | `ModuleFrontController` `HmrcratesCronjobModuleFrontController` jest wysyłany, gdy uzyskuje się dostęp do adresu URL cron, wyzwalając logikę aktualizacji kursów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i pobrania najnowszych wersji modułu „HM Revenue & Customs (HMRC) - kursy wymiany walut” odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub konfiguracji modułu.
