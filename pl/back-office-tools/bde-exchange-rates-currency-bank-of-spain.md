---
title: "BdE Kursy walut i waluta (Bank Hiszpanii) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „BdE Kursy walut i waluta (Bank Hiszpanii)” od MyPresta.eu."
sidebar:
  label: "BdE Kursy walut i waluta (Bank Hiszpanii) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł BdE Exchange Rates & Currency (Bank of Spain) na MyPresta.eu](https://mypresta.eu/modules/administration-tools/bde-exchange-rates-currency-bank-of-spain.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/bde-exchange-rates-currency-bank-of-spain/)
>
> ---


# BdE Kursy walut i waluta (Bank Hiszpanii)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP, takie jak cURL (do pobierania danych zewnętrznych), JSON (do przetwarzania danych) i OpenSSL (do bezpiecznych połączeń), są zazwyczaj wymagane i są standardem w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „BdE Kursy walut i waluta (Bank Hiszpanii)”. Tutaj kontrolujesz, w jaki sposób moduł pobiera i stosuje kursy wymiany.

#### **MyPresta.eu Live Updates**

-   **Co robi to ustawienie:** Ta sekcja umożliwia zarządzanie połączeniem modułu z MyPresta.eu w celu automatycznych aktualizacji i wsparcia.
-   **Skutek zmiany tego ustawienia:**
    *   *Wprowadzenie identyfikatora zamówienia MyPresta.eu i adresu e-mail:* Umożliwia modułowi sprawdzanie nowych wersji i otrzymywanie aktualizacji bezpośrednio z MyPresta.eu. Zapewnia to zawsze najnowsze funkcje i poprawki błędów.
    *   *Pozostawienie pustego:* Moduł nie będzie mógł sprawdzać automatycznych aktualizacji. Będziesz musiał ręcznie pobierać i instalować nowe wersje z konta MyPresta.eu.
-   **Zalecana wartość:** Zawsze wprowadzaj identyfikator zamówienia MyPresta.eu i adres e-mail powiązany z Twoim zakupem. Jest to kluczowe dla otrzymywania terminowych aktualizacji i wsparcia.
-   **Scenariusz / przykład dla sprzedawcy:** Kupiłeś moduł używając `twoj.email@example.com`, a Twój identyfikator zamówienia to `MP12345`. Wprowadzenie tych danych tutaj oznacza, że zostaniesz powiadomiony bezpośrednio w panelu administracyjnym PrestaShop, gdy zostanie wydana nowa wersja modułu, i będziesz mógł zaktualizować go jednym kliknięciem.

#### **CRON Job URL**

-   **Co robi to ustawienie:** Wyświetla unikalny adres URL, którego możesz użyć do skonfigurowania „zadania CRON” na swoim serwerze. Zadanie CRON to zaplanowane zadanie, które automatycznie uruchamia określone polecenie lub adres URL w regularnych odstępach czasu (np. raz dziennie).
-   **Skutek zmiany tego ustawienia:**
    *   *Konfiguracja zadania CRON z tym adresem URL:* Moduł będzie automatycznie pobierał najnowsze kursy wymiany z Banku Hiszpanii z częstotliwością, którą zdefiniujesz (np. codziennie). Zapewnia to, że Twoje kursy walut są zawsze aktualne bez żadnej ręcznej interwencji.
    *   *Brak konfiguracji zadania CRON:* Kursy wymiany nie będą automatycznie aktualizowane. Będziesz musiał ręcznie odwiedzać ten adres URL w przeglądarce za każdym razem, gdy chcesz zaktualizować kursy, co jest bardzo niepraktyczne i niweczy cel automatyzacji.
-   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj codzienne zadanie CRON na swoim serwerze hostingowym. Większość paneli sterowania hostingiem (takich jak cPanel, Plesk) ma sekcję „Zadania CRON”, w której możesz łatwo dodać ten adres URL, aby uruchamiał się raz na 24 godziny.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kursy wymiany euro aktualizowały się każdego ranka o 3:00. Kopiujesz podany adres URL CRON, przechodzisz do panelu sterowania hostingiem, tworzysz nowe zadanie CRON, wklejasz adres URL i ustawiasz je na codzienne uruchamianie o 3:00. Od tego momentu Twoje kursy będą automatycznie aktualizowane.

#### **Margin Adjustment (%)**

-   **Co robi to ustawienie:** Umożliwia dodanie niewielkiego procentowego marginesu do pobranych kursów wymiany. Może to być przydatne do pokrycia potencjalnych opłat transakcyjnych, kosztów wymiany walut lub po prostu w celu zapewnienia sobie niewielkiego buforu.
-   **Skutek zmiany tego ustawienia:**
    *   *Ustawienie dodatniego procentu (np. 2%):* Moduł zwiększy oficjalny kurs wymiany o ten procent. Na przykład, jeśli oficjalny kurs wynosi 1 EUR = 1,10 USD, a Ty ustawisz margines 2%, moduł użyje 1 EUR = 1,122 USD (1,10 \* 1,02). Oznacza to, że produkty wycenione w EUR będą wydawać się nieco droższe po przeliczeniu na USD.
    *   *Ustawienie 0% (domyślnie):* Moduł będzie używał dokładnych oficjalnych kursów wymiany bez żadnej korekty.
-   **Zalecana wartość:** 0%, chyba że masz konkretne powody biznesowe (takie jak pokrycie opłat bankowych) do dodania marginesu. Przejrzystość jest często najlepsza dla zaufania klientów.
-   **Scenariusz / przykład dla sprzedawcy:** Twoja bramka płatności pobiera 1,5% opłaty za międzynarodowe konwersje walut. Aby to zrekompensować, możesz ustawić Korektę marży na 1,5%. Zapewnia to, że przeliczone ceny nieznacznie uwzględniają ten koszt.

#### **Update Currency Rates**

-   **Co robi to ustawienie:** Jest to ręczny przycisk wyzwalający natychmiastowe pobranie i aktualizację wszystkich kursów wymiany z Banku Hiszpanii.
-   **Skutek zmiany tego ustawienia:**
    *   *Kliknięcie przycisku:* Moduł natychmiast połączy się z Bankiem Hiszpanii, pobierze najnowsze kursy i zaktualizuje je w Twoim sklepie PrestaShop. Jest to przydatne do testowania lub do natychmiastowej aktualizacji poza harmonogramem zadania CRON.
-   **Zalecana wartość:** Użyj tego przycisku do początkowego testowania konfiguracji lub jeśli potrzebujesz natychmiastowej aktualizacji. Do regularnych aktualizacji polegaj na zadaniu CRON.
-   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz sprawdzić, czy działa poprawnie i pobiera najnowsze kursy. Klikasz ten przycisk, aby zobaczyć natychmiastowy efekt.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | MyPresta.eu Order ID | Twój identyfikator zamówienia | Umożliwia automatyczne aktualizacje modułu i wsparcie. |
| Konfiguracja modułu | MyPresta.eu Email | Twój adres e-mail | Umożliwia automatyczne aktualizacje modułu i wsparcie. |
| Konfiguracja modułu | CRON Job URL | (Unikalny URL) | Skonfiguruj codzienne zadanie CRON z tym adresem URL dla automatycznych aktualizacji kursów. |
| Konfiguracja modułu | Margin Adjustment (%) | 0% | Dodaj procentowy bufor do kursów wymiany (np. na opłaty). |
| Konfiguracja modułu | Update Currency Rates | Kliknij, aby uruchomić | Ręcznie pobierz i natychmiast zaktualizuj kursy wymiany. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy walut nie aktualizują się automatycznie.**
O:

1.  **Sprawdź konfigurację zadania CRON:** Upewnij się, że poprawnie skonfigurowałeś zadanie CRON na swoim serwerze hostingowym, używając dokładnego adresu URL podanego w konfiguracji modułu. Upewnij się, że jest ono zaplanowane do uruchamiania co najmniej raz dziennie.
2.  **Zweryfikuj wykonanie zadania CRON:** Niektóre panele hostingowe udostępniają logi wykonania zadań CRON. Sprawdź te logi, aby zobaczyć, czy zadanie CRON faktycznie działa i czy występują jakieś błędy.
3.  **Łączność z serwerem:** Upewnij się, że Twój serwer ma dostęp wychodzący do zewnętrznych stron internetowych (w szczególności do API Banku Hiszpanii). Czasami zapory ogniowe mogą to blokować. Skontaktuj się z dostawcą hostingu, jeśli podejrzewasz, że to jest problem.
4.  **Konfiguracja modułu:** Upewnij się, że Twoje dane MyPresta.eu są poprawnie wprowadzone w przypadku potencjalnych problemów z aktualizacją.

**P: Ceny w EUR wydają się nieco nieprawidłowe, nawet po aktualizacji.**
O:

1.  **Sprawdź korektę marży:** Sprawdź ustawienie „Korekta marży (%)” w konfiguracji modułu. Jeśli jest ustawione na wartość większą niż 0, Twoje ceny zostaną skorygowane o ten procent. Ustaw na 0%, jeśli chcesz dokładne oficjalne kursy.
2.  **Zaokrąglanie PrestaShop:** PrestaShop ma własne zasady zaokrąglania cen. Upewnij się, że ustawienia waluty w **Międzynarodowe > Waluty** są skonfigurowane do pożądanej precyzji dziesiętnej.
3.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność) i pamięć podręczną przeglądarki.

**P: Co dzieje się w dni wolne od pracy lub weekendy, gdy Bank Hiszpanii nie publikuje nowych kursów?**
O: Moduł jest zaprojektowany tak, aby inteligentnie sobie z tym radzić. Jeśli nowe kursy nie są dostępne dla danego dnia, będzie nadal używał ostatnio pomyślnie pobranych kursów. Po opublikowaniu nowych kursów moduł zaktualizuje je podczas następnego zaplanowanego uruchomienia.

**P: Czy mogę używać tego modułu z innymi modułami walutowymi?**
O: Ten moduł koncentruje się wyłącznie na pobieraniu i stosowaniu oficjalnych kursów Banku Hiszpanii. Ogólnie dobrze współpracuje z natywnymi funkcjami wielowalutowymi PrestaShop. Jednakże, jeśli masz inne moduły, które *również* próbują pobierać lub nadpisywać kursy wymiany z różnych źródeł, mogą wystąpić konflikty. Najlepiej jest używać jednego głównego źródła aktualizacji kursów wymiany, aby uniknąć niespójności.

**P: Widzę sekcję „Aktualizacje MyPresta.eu”. Do czego służy?**
O: Ta sekcja umożliwia wprowadzenie identyfikatora zamówienia MyPresta.eu i adresu e-mail. Umożliwia to modułowi sprawdzanie nowych wersji i otrzymywanie aktualizacji bezpośrednio z MyPresta.eu, zapewniając zawsze najnowsze funkcje i poprawki błędów. Zdecydowanie zaleca się wypełnienie tej sekcji.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `BdE Exchange Rates & Currency` to lekki moduł PrestaShop zaprojektowany przede wszystkim do integracji z oficjalnym API kursów wymiany Banku Hiszpanii. Podąża za standardową strukturą modułu PrestaShop, wykorzystując klasę `Module` do instalacji i konfiguracji oraz `ModuleFrontController` do obsługi żądań zadań CRON. Jego podstawowa funkcjonalność obraca się wokół pobierania danych zewnętrznych, ich parsowania i aktualizowania natywnych kursów wymiany `Currency` PrestaShop.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery front-office

-   **`controllers/front/cronjob.php`**
    *   **Nazwa klasy i klasa nadrzędna:** `BderatesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler jest punktem wejścia dla zaplanowanego zadania CRON. Po uzyskaniu dostępu inicjuje proces pobierania najnowszych kursów wymiany z Banku Hiszpanii. Obsługuje żądanie API, parsuje odpowiedź i aktualizuje kursy wymiany dla skonfigurowanych walut w PrestaShop. Jest zaprojektowany do wywoływania zewnętrznie przez harmonogram CRON po stronie serwera i zazwyczaj zwraca prostą wiadomość o sukcesie/niepowodzeniu.
-   **`controllers/front/index.php`**
    *   **Nazwa klasy i klasa nadrzędna:** `BderatesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    *   **Odpowiedzialność:** Jest to kontroler-placeholder, często dołączany do modułów, ale nieaktywnie używany w podstawowej funkcjonalności tego konkretnego modułu. Może być obecny w celach routingu lub jako domyślny punkt wejścia, ale główna logika aktualizacji kursów znajduje się w `cronjob.php`.

#### Kontrolery administracyjne back-office

Ten moduł nie implementuje żadnych niestandardowych kontrolerów administracyjnych back-office. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Bezpośrednio współdziała z podstawową klasą `Currency` PrestaShop w celu aktualizacji kursów wymiany.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony administracyjne (`views/templates/admin/`)

-   **`views/templates/admin/admin.tpl`**
    *   **Cel:** Ten szablon służy do renderowania formularza konfiguracji modułu w panelu administracyjnym PrestaShop. Wyświetla pola wejściowe dla aktualizacji MyPresta.eu, adresu URL zadania CRON, korekty marży i przycisku ręcznej aktualizacji.
    *   **Kontekst:** Renderowany przez metodę `getContent()` głównego pliku modułu `bderates.php`.
    *   **Kluczowe elementy:** Elementy formularza dla ustawień `mypresta_updates`, `update_`, `updatev_`, `currency_`.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

Ten moduł nie tworzy żadnych niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne bezpośrednio w tabeli `ps_configuration` PrestaShop, używając kluczy takich jak:

-   `BDERATES_MYPRESTA_ID`
-   `BDERATES_MYPRESTA_EMAIL`
-   `BDERATES_MARGIN`
-   `BDERATES_LAST_UPDATE`

#### Tabela zarejestrowanych haków

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Nie jest aktywnie używany do wizualnego wyjścia przez ten moduł, ale często rejestrowany przez moduły do ogólnej konfiguracji lub ładowania zasobów. |
| `displayRightColumn` | W prawej kolumnie stron front-office. | Nie jest aktywnie używany do wizualnego wyjścia przez ten moduł. |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | Nie jest aktywnie używany do wizualnego wyjścia przez ten moduł. |
| `displayFooter` | W sekcji stopki każdej strony front-office. | Nie jest aktywnie używany do wizualnego wyjścia przez ten moduł. |
| `displayProductAdditionalInfo` | Na stronie produktu, poniżej głównych informacji o produkcie. | Nie jest aktywnie używany do wizualnego wyjścia przez ten moduł. |
| `actionUpdateCurrency` | Wyzwalany po zaktualizowaniu kursu wymiany waluty. | Ten moduł *wyzwala* ten hak, gdy aktualizuje kursy walut, umożliwiając innym modułom reagowanie na zmianę. |
| `actionCronJob` | Niestandardowy hak często używany przez moduły do rejestrowania swoich zadań CRON. | Kontroler `cronjob.php` modułu jest głównym mechanizmem zaplanowanych aktualizacji, ale ten hak może być zarejestrowany w celu zapewnienia kompatybilności lub przyszłej rozbudowy. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „BdE Kursy walut i waluta (Bank Hiszpanii)” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
