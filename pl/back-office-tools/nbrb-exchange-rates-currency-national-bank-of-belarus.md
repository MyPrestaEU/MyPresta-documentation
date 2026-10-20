---
title: "Kursy walut i waluta NBRB (Narodowy Bank Białorusi) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop NBRB Exchange Rates & Currency (National Bank of Belarus) od MyPresta.eu."
sidebar:
  label: "Kursy walut i waluta NBRB (Narodowy Bank Białorusi) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł NBRB Exchange Rates & Currency (National Bank of Belarus) na MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbrb-exchange-rates-currency-national-bank-of-belarus.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/nbrb-exchange-rates-currency-national-bank-of-belarus/)
>
> ---


# Kursy walut i waluta NBRB (Narodowy Bank Białorusi)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane i obecne w większości nowoczesnych środowisk hostingowych. Dostęp do konfiguracji zadania CRON jest niezbędny do automatycznych aktualizacji.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „NBRB Exchange Rates & Currency”, aby uzyskać dostęp do jego ustawień.

#### **Włącz kursy wymiany NBRB**

- **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł zacznie pobierać i stosować kursy wymiany NBRB do przeliczania walut BYN w Twoim sklepie.
  - *Gdy wyłączone (NIE):* Moduł przestanie pobierać kursy, a kursy walut BYN powrócą do wartości ustawionych ręcznie w sekcji „Waluty” PrestaShop lub przez inny aktywny moduł walutowy.
- **Zalecana wartość:** TAK
- **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz głównie na Białoruś, włącz to, aby upewnić się, że wszystkie ceny BYN są oficjalne. Jeśli tymczasowo przestaniesz sprzedawać na Białoruś, możesz to wyłączyć.

#### **URL zadania CRON**

- **Co robi to ustawienie:** Wyświetla unikalny URL, który musisz ustawić jako zadanie CRON na swoim serwerze. Po uzyskaniu dostępu do tego URL, moduł automatycznie pobierze najnowsze kursy wymiany z NBRB.
- **Efekt zmiany tego ustawienia:** Jest to pole tylko do wyświetlania. Kopiujesz ten URL i wklejasz go do harmonogramu zadań CRON w panelu sterowania swojego hostingu.
- **Zalecana wartość:** Skopiuj ten URL dokładnie tak, jak jest pokazany.
- **Scenariusz/przykład dla sprzedawcy:** Skopiowałbyś ten URL i ustawił zadanie CRON, aby uruchamiało się, na przykład, raz na 24 godziny (np. o 3 rano czasu lokalnego), aby zapewnić, że Twoje kursy są zawsze świeże. Skonsultuj się z dokumentacją lub wsparciem swojego dostawcy hostingu w celu konfiguracji zadań CRON.

#### **Korekta marży (%)**

- **Co robi to ustawienie:** Pozwala dodać procentową marżę (narzut lub obniżkę) do pobranych kursów wymiany NBRB. Jest to przydatne do pokrywania opłat transakcyjnych, zabezpieczania się przed drobnymi wahaniami lub stosowania niewielkiej zniżki/premii.
- **Efekt zmiany tego ustawienia:**
  - *Wprowadzenie wartości dodatniej (np. 2):* Kurs wymiany BYN zostanie zwiększony o 2%, co efektywnie sprawi, że produkty będą nieco droższe w BYN.
  - *Wprowadzenie wartości ujemnej (np. -1):* Kurs wymiany BYN zostanie zmniejszony o 1%, co sprawi, że produkty będą nieco tańsze w BYN.
  - *Pozostawienie na 0:* Użyty zostanie oficjalny kurs NBRB bez żadnych modyfikacji.
- **Zalecana wartość:** 0 (chyba że masz konkretny powód biznesowy do dostosowania kursów).
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja bramka płatności pobiera 1,5% opłaty za transakcje BYN, możesz ustawić to na „1.5”, aby wchłonąć ten koszt w kurs wymiany.

#### **Ostatnia aktualizacja**

- **Co robi to ustawienie:** To pole wyświetla datę i godzinę ostatniej pomyślnej aktualizacji kursów wymiany przez moduł (ręcznie lub za pośrednictwem zadania CRON).
- **Efekt zmiany tego ustawienia:** Jest to pole informacyjne tylko do odczytu. Pomaga zweryfikować, czy Twoje zadanie CRON działa poprawnie i czy kursy są aktualizowane.
- **Zalecana wartość:** N/A (monitoruj to, aby zapewnić regularne aktualizacje).
- **Scenariusz/przykład dla sprzedawcy:** Jeśli zauważysz, że ta data jest sprzed kilku dni, oznacza to problem z konfiguracją zadania CRON i powinieneś to zbadać.

#### **Przycisk ręcznej aktualizacji kursów**

- **Co robi to ustawienie:** Ten przycisk pozwala ręcznie wywołać natychmiastową aktualizację kursów wymiany z NBRB, poza harmonogramem zadania CRON.
- **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku natychmiast pobierze najnowsze kursy i zaktualizuje je w Twoim sklepie PrestaShop. Pole „Ostatnia aktualizacja” odzwierciedli nowy czas.
- **Zalecana wartość:** Używaj w razie potrzeby do natychmiastowych aktualizacji lub testowania.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli nastąpiło znaczące wydarzenie gospodarcze i chcesz upewnić się, że Twoje kursy są absolutnie aktualne przed następnym zaplanowanym zadaniem CRON, możesz kliknąć ten przycisk.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz kursy wymiany NBRB | TAK | Aktywuje/dezaktywuje pobieranie i stosowanie kursów przez moduł. |
| Konfiguracja modułu | URL zadania CRON | N/A (kopiuj i wklej) | URL do ustawienia automatycznych aktualizacji kursów na Twoim serwerze. |
| Konfiguracja modułu | Korekta marży (%) | 0 | Dodaje procentowy narzut/obniżkę do pobranych kursów NBRB. |
| Konfiguracja modułu | Ostatnia aktualizacja | N/A (tylko do odczytu) | Pokazuje znacznik czasu ostatniej pomyślnej aktualizacji kursów. |
| Konfiguracja modułu | Przycisk ręcznej aktualizacji kursów | N/A (kliknij, aby aktywować) | Wywołuje natychmiastową, ręczną aktualizację kursów wymiany. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje ceny BYN nie aktualizują się lub wydają się nieprawidłowe.**
O:

1.  **Sprawdź „Włącz kursy wymiany NBRB”:** Upewnij się, że to ustawienie jest ustawione na „TAK” w konfiguracji modułu.
2.  **Zweryfikuj zadanie CRON:** Upewnij się, że Twoje zadanie CRON jest poprawnie skonfigurowane na Twoim serwerze przy użyciu podanego URL i działa regularnie. Sprawdź znacznik czasu „Ostatnia aktualizacja” w module.
3.  **Ręczna aktualizacja:** Spróbuj kliknąć przycisk „Ręczna aktualizacja kursów”. Jeśli to zadziała, problem prawdopodobnie dotyczy konfiguracji zadania CRON.
4.  **Sprawdź status waluty BYN:** Przejdź do **Międzynarodowe > Waluty** i upewnij się, że „Rubel białoruski (BYN)” jest włączony, a jego kod ISO to `BYN`.
5.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może przechowywać stare wartości. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P: Co się dzieje w dni wolne od pracy banków lub weekendy, gdy NBRB nie publikuje nowych kursów?**
O: Moduł jest zaprojektowany do inteligentnego obsługiwania takich sytuacji. Jeśli API NBRB nie dostarcza nowych kursów na dany dzień (np. z powodu weekendu lub święta państwowego), moduł będzie nadal używał ostatniego pomyślnie pobranego kursu. Zaktualizuje się dopiero, gdy dostępne będą nowe oficjalne kursy.

**P: Czy mogę używać tego modułu z innymi modułami do przeliczania walut?**
O: Generalnie nie zaleca się jednoczesnego uruchamiania wielu modułów do przeliczania walut, ponieważ mogą one powodować konflikty i prowadzić do nieprzewidywalnych wyników. Ten moduł jest specjalnie przeznaczony do kursów NBRB dla BYN. Jeśli potrzebujesz innych walut, upewnij się, że ten moduł jest głównym źródłem dla BYN, a inne moduły obsługują różne waluty bez nakładania się.

**P: Ustawiłem marżę, ale ceny nie wydają się jej odzwierciedlać.**
O:

1.  **Zapisz zmiany:** Upewnij się, że zapisałeś konfigurację modułu po ustawieniu marży.
2.  **Zaktualizuj kursy:** Marża jest stosowana podczas pobierania kursów. Poczekaj na następne uruchomienie zadania CRON lub kliknij „Ręczna aktualizacja kursów”.
3.  **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
4.  **Sprawdź walutę bazową:** Marża jest stosowana do przeliczenia z waluty bazowej Twojego sklepu na BYN. Upewnij się, że Twoja waluta bazowa jest poprawnie ustawiona w PrestaShop.

**P: Otrzymuję błąd podczas próby instalacji lub konfiguracji modułu.**
O:

1.  **Wersja PrestaShop:** Upewnij się, że pobrałeś prawidłowy plik ZIP modułu dla Twojej konkretnej wersji PrestaShop (1.6, 1.7, 8.x, 9.x).
2.  **Kompatybilność z PHP:** Sprawdź, czy wersja PHP Twojego serwera mieści się w obsługiwanym zakresie (PHP 5.6 - 8.5).
3.  **Logi serwera:** Sprawdź logi błędów PHP Twojego serwera (często znajdujące się w panelu sterowania Twojego hostingu) w poszukiwaniu bardziej szczegółowych komunikatów o błędach. Może to pomóc w zlokalizowaniu dokładnego problemu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł NBRB Exchange Rates & Currency to lekki moduł PrestaShop, skupiający się głównie na jednym, krytycznym zadaniu: pobieraniu i aktualizowaniu kursu wymiany rubla białoruskiego (BYN) z API Narodowego Banku Republiki Białorusi (NBRB). Wykorzystuje obiekt `Currency` PrestaShop do aktualizacji `conversion_rate` dla BYN. Moduł używa zadania CRON do automatycznych aktualizacji i zapewnia ręczny wyzwalacz w panelu administracyjnym. Przestrzega wzorca MVC PrestaShop dla swojej konfiguracji i wykonania zadania cronjob w front-office.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna:** `NbrbratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zewnętrzne zadanie CRON. Po uzyskaniu dostępu, wyzwala logikę pobierania kursów modułu (`$this->module->updateRates()`). Wyświetla prosty komunikat o sukcesie/porażce, co czyni go odpowiednim do automatycznego wykonywania bez przeglądarki. Nie renderuje pełnej strony.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna:** `NbrbratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność:** Jest to kontroler-placeholder, często dołączany do modułów, aby zapobiec listowaniu katalogów lub zapewnić domyślną „pustą” stronę, jeśli kontroler front-office modułu jest dostępny bezpośrednio bez konkretnych akcji. W kontekście tego modułu prawdopodobnie służy jako fallback i nie posiada specyficznej logiki biznesowej.
-   **Kontrolery administracyjne Back-Office**:

    -   Ten moduł nie wykorzystuje dedykowanych kontrolerów administracyjnych. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas w katalogu `classes/`. Jego podstawowa logika pobierania i aktualizowania kursów jest hermetyzowana w głównym pliku modułu `nbrbrates/cronjob.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja strony konfiguracji administratora jest zazwyczaj obsługiwana przez domyślny CSS panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `nbrbrates/views/admin.tpl`
        -   **Cel:** Ten szablon jest renderowany przez metodę `getContent()` w głównym pliku modułu (`nbrbrates/cronjob.php`). Definiuje strukturę i wyświetlanie formularza konfiguracji modułu w panelu administracyjnym PrestaShop. Zawiera pola wejściowe do włączania/wyłączania modułu, korekty marży, wyświetlania URL zadania CRON, czasu ostatniej aktualizacji oraz przycisku ręcznej aktualizacji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Kluczowe klucze konfiguracyjne to:
        -   `Nbrbrates_ENABLED`: (int) 1, jeśli włączony, 0, jeśli wyłączony.
        -   `Nbrbrates_MARGIN`: (float) Procentowa marża do zastosowania.
        -   `Nbrbrates_LAST_UPDATE`: (datetime) Znacznik czasu ostatniej pomyślnej aktualizacji kursów.
-   **Tabela zarejestrowanych hooków**:
    Ten moduł nie rejestruje jawnie hooków, które wyświetlają zawartość w front-office (takich jak `displayHeader`, `displayRightColumn`, `displayFooter`). Jego główna interakcja z PrestaShop odbywa się poprzez:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionModuleInstall` | Wykonywany podczas instalacji modułu. | Inicjalizuje domyślne wartości konfiguracyjne w `ps_configuration`. |
| `actionModuleUninstall` | Wykonywany podczas deinstalacji modułu. | Czyści wartości konfiguracyjne z `ps_configuration`. |
| `actionUpdateCurrency` | (Implicitny) Wyzwalany, gdy waluta jest aktualizowana. | Metoda `updateRates()` modułu bezpośrednio modyfikuje `conversion_rate` obiektu waluty BYN, efektywnie działając na aktualizacje walut. |

Kontroler front-office `cronjob.php` działa jako zewnętrzny punkt wejścia, a nie tradycyjny hook PrestaShop.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu NBRB Exchange Rates & Currency, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub integracji modułu.
