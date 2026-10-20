---
title: "Sveriges Riksbank - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Sveriges Riksbank - kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Sveriges Riksbank - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Sveriges Riksbank - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/sveriges-riksbank-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/sveriges-riksbank-currency-exchange-rates/)
>
> ---


# Sveriges Riksbank - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do zewnętrznych wywołań API, które są standardem w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do głównej strony ustawień modułu. Tutaj ustawisz, w jaki sposób moduł pobiera i stosuje kursy wymiany.

#### **Ustawienia ogólne**

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł będzie aktywny, a jego zadanie cron i logika aktualizacji kursów będą działać zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Moduł będzie nieaktywny i nie będą wykonywane żadne automatyczne aktualizacje kursów. Twoje kursy walut pozostaną takie, jak zostały ostatnio ustawione (ręcznie lub przez poprzednią aktualizację modułu).
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli dopiero konfigurujesz lub rozwiązujesz problem, możesz tymczasowo go wyłączyć. Do normalnego działania powinien być zawsze włączony.
-   **URL zadania Cron:**

    -   **Co robi to ustawienie:** Wyświetla unikalny adres URL, który musisz ustawić jako „zadanie cron” na swoim serwerze hostingowym. Zadanie cron to zaplanowane zadanie, które nakazuje serwerowi odwiedzać ten adres URL w regularnych odstępach czasu (np. raz dziennie). Gdy adres URL zostanie odwiedzony, moduł automatycznie pobiera i aktualizuje kursy walut.
    -   **Skutek zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł. Efekt wynika z *użycia* tego adresu URL w panelu hostingowym.
        -   *Gdy poprawnie ustawiony jako zadanie cron:* Twoje kursy walut będą automatycznie aktualizowane z określoną częstotliwością (np. codziennie).
        -   *Gdy nie ustawiony jako zadanie cron:* Kursy nie będą aktualizowane automatycznie. Musiałbyś ręcznie odwiedzać ten adres URL w przeglądarce, aby wywołać aktualizację, co niweczy cel automatyzacji.
    -   **Zalecana wartość:** Skopiuj ten adres URL i ustaw go jako codzienne zadanie cron na swoim serwerze.
    -   **Scenariusz / przykład dla sprzedawcy:** Zazwyczaj ustawiasz to, aby działało raz na 24 godziny, aby zapewnić, że Twoje kursy są zawsze świeże. Skonsultuj się z dokumentacją lub wsparciem swojego dostawcy hostingu, aby dowiedzieć się, jak skonfigurować zadanie cron (często znajduje się w cPanelu lub Plesku w sekcji „Zadania Cron” lub „Zaplanowane zadania”).

#### **Ustawienia specyficzne dla waluty**

Poniżej ustawień ogólnych zobaczysz listę wszystkich aktywnych walut w Twoim sklepie PrestaShop. Dla każdej waluty możesz skonfigurować specyficzne ustawienia:

-   **Nazwa waluty (np. Euro, Dolar amerykański):**

    -   **Co robi to ustawienie:** Identyfikuje walutę, którą konfigurujesz.
    -   **Skutek zmiany tego ustawienia:** To tylko etykieta; nie możesz zmienić nazwy waluty tutaj.
-   **Narzut / Upust (%):**

    -   **Co robi to ustawienie:** Pozwala zastosować procentową korektę kursu wymiany pobranego ze Sveriges Riksbank.
        -   **Wartość dodatnia (narzut)** zwiększa kurs wymiany, co oznacza, że otrzymujesz więcej waluty obcej za swoją walutę bazową. Jest to przydatne do pokrywania opłat transakcyjnych lub zwiększania marży zysku.
        -   **Wartość ujemna (upust)** zmniejsza kurs wymiany, co oznacza, że otrzymujesz mniej waluty obcej. Może to być używane do celów promocyjnych lub jeśli chcesz zaoferować klientom nieco lepszy kurs.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na 0:* Kurs wymiany będzie dokładnie taki, jaki podaje Sveriges Riksbank.
        -   *Gdy ustawione na 2 (narzut):* Jeśli kurs Riksbanku wynosi 1 EUR = 10 SEK, z 2% narzutem, Twój sklep będzie używał 1 EUR = 10.20 SEK. Oznacza to, że gdy klient płaci w EUR, faktycznie otrzymujesz więcej SEK.
        -   *Gdy ustawione na -1 (upust):* Jeśli kurs Riksbanku wynosi 1 EUR = 10 SEK, z 1% upustem, Twój sklep będzie używał 1 EUR = 9.90 SEK. Oznacza to, że gdy klient płaci w EUR, otrzymuje nieco lepszy kurs.
    -   **Zalecana wartość:** Zależy od Twojej strategii biznesowej. Powszechną praktyką jest dodawanie niewielkiego narzutu (np. 1-3%), aby pokryć opłaty bramki płatniczej i koszty konwersji walut.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój procesor płatności pobiera 1,5% opłaty za konwersję EUR na SEK, możesz ustawić 2% narzut dla EUR, aby upewnić się, że pokryjesz tę opłatę i zachowasz niewielki zysk.

#### **Przycisk Zapisz**

-   **Co robi ten przycisk:** Zapisuje wszystkie zmiany wprowadzone na stronie konfiguracji.
-   **Skutek kliknięcia tego przycisku:** Twoje nowe ustawienia (włącz/wyłącz, procenty narzutu/upustu) zostaną zastosowane. Następnym razem, gdy zadanie cron zostanie uruchomione lub ręcznie wywołasz aktualizację, te nowe ustawienia zostaną użyte.
-   **Zalecane działanie:** Zawsze kliknij „Zapisz” po wprowadzeniu jakichkolwiek zmian.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł | TAK | Aktywuje/dezaktywuje automatyczne aktualizacje kursów modułu. |
| Konfiguracja modułu | URL zadania Cron | (Wygenerowany URL) | URL do ustawienia jako zaplanowane zadanie na Twoim serwerze dla automatycznych aktualizacji. |
| Konfiguracja modułu | Narzut / Upust (%) (na walutę) | 0 | Dostosowuje pobrany kurs wymiany o procent, aby pokryć opłaty lub zarządzać zyskiem. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy walut nie aktualizują się automatycznie. Co powinienem sprawdzić?**
O1:

-   **Czy moduł jest włączony?** Przejdź do Moduły > Menedżer modułów > Sveriges Riksbank - kursy wymiany walut i upewnij się, że „Włącz moduł” jest ustawione na TAK.
-   **Czy zadanie cron jest poprawnie skonfigurowane?** Sprawdź ponownie swój panel sterowania hostingowego (cPanel, Plesk itp.), aby upewnić się, że URL zadania Cron podany w konfiguracji modułu jest poprawnie wprowadzony i zaplanowany do uruchomienia. Upewnij się, że polecenie jest poprawne (np. `wget -q -O /dev/null "TWÓJ_URL_CRON"` lub `curl -s "TWÓJ_URL_CRON"`).
-   **Czy występują jakieś błędy podczas ręcznego odwiedzania URL zadania Cron?** Spróbuj wkleić URL zadania Cron do swojej przeglądarki. Jeśli zobaczysz komunikat o błędzie, może to wskazywać na problem z serwerem lub problem z połączeniem modułu ze Sveriges Riksbank.
-   **Łączność z serwerem:** Upewnij się, że Twój serwer może nawiązywać połączenia wychodzące z zewnętrznymi stronami internetowymi (API Sveriges Riksbank). Czasami zapory ogniowe mogą to blokować. Skontaktuj się z dostawcą hostingu, jeśli podejrzewasz taką sytuację.

**P2: Zaktualizowałem procenty narzutu, ale ceny w moim sklepie się nie zmieniły.**
O2:

-   **Czy zapisałeś ustawienia?** Zawsze kliknij przycisk „Zapisz” po wprowadzeniu zmian na stronie konfiguracji modułu.
-   **Czy zadanie cron zostało uruchomione od czasu zapisania?** Zmiany zaczną obowiązywać dopiero po wykonaniu przez moduł następnego cyklu aktualizacji. Możesz albo poczekać na zaplanowane zadanie cron, albo ręcznie wywołać aktualizację, odwiedzając URL zadania Cron w swojej przeglądarce.
-   **Wyczyść pamięć podręczną PrestaShop:** Czasami pamięć podręczna PrestaShop może przechowywać stare dane. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.

**P3: Kursy wymiany wydają się nieprawidłowe lub nie są tym, czego oczekuję od Sveriges Riksbank.**
O3:

-   **Sprawdź ustawienia narzutu/upustu:** Upewnij się, że nie ustawiłeś przypadkowo wysokiego procentu narzutu lub upustu, który zniekształca kursy.
-   **Zweryfikuj oficjalne kursy Sveriges Riksbank:** Porównaj kursy w swoim sklepie (po aktualizacji) z oficjalnymi kursami opublikowanymi na stronie internetowej Sveriges Riksbank, aby sprawdzić, czy występują rozbieżności.
-   **Waluta bazowa modułu:** Moduł pobiera kursy względem SEK. Upewnij się, że domyślna waluta Twojego PrestaShop jest poprawnie ustawiona, jeśli oczekujesz innej waluty bazowej.

**P4: Czy ten moduł będzie działał z moim niestandardowym szablonem?**
O4: Tak, ten moduł działa całkowicie w tle i nie dodaje żadnych elementów wizualnych ani nie modyfikuje żadnych szablonów w front-office. Dlatego jest w pełni kompatybilny z każdym szablonem PrestaShop, niestandardowym lub domyślnym. Jego funkcja jest czysto oparta na danych (aktualizacja kursów wymiany).

**P5: Jak dodać nową walutę do mojego sklepu, aby ten moduł mógł nią zarządzać?**
O5:

1.  Przejdź do **Lokalizacja > Waluty** w Panelu administracyjnym PrestaShop.
2.  Kliknij „Dodaj nową walutę” (lub ikonę plusa).
3.  Wypełnij szczegóły nowej waluty (kod ISO, symbol, kurs wymiany względem Twojej domyślnej waluty).
4.  Po dodaniu i włączeniu nowa waluta pojawi się na stronie konfiguracji modułu „Sveriges Riksbank - kursy wymiany walut”, umożliwiając ustawienie jej narzutu/upustu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Sveriges Riksbank - kursy wymiany walut”.

### 4.1 Przegląd architektury

Moduł przestrzega standardowej architektury modułów PrestaShop, koncentrując się głównie na konfiguracji w panelu administracyjnym i wykonywaniu zadań cron w front-office. Wykorzystuje system konfiguracji PrestaShop do przechowywania ustawień oraz `ModuleFrontController` do obsługi żądań zadań cron. Główna logika znajduje się w głównym pliku modułu, który obsługuje instalację, deinstalację i metodę `getContent()` dla formularza konfiguracji. Podstawową funkcją modułu jest pobieranie danych zewnętrznych (kursów walut) i aktualizowanie danych obiektu `Currency` PrestaShop.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są zaprojektowane tak, aby były publicznie dostępne, głównie dla funkcji zadań cron.

-   **`srrates/controllers/front/cronjob.php`**

    -   **Nazwa klasy i klasa nadrzędna:** `SrratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to kluczowy kontroler do automatycznych aktualizacji walut. Gdy ten URL jest dostępny (zazwyczaj przez zadanie cron po stronie serwera), wyzwala logikę modułu do pobierania najnowszych kursów wymiany ze Sveriges Riksbank i aktualizowania ich w bazie danych PrestaShop. Nie renderuje żadnych wizualnych danych wyjściowych, ale zazwyczaj zwraca prosty komunikat o sukcesie lub błędzie. Jest zaprojektowany tak, aby był lekki i wydajny dla zaplanowanych zadań.
-   **`srrates/controllers/front/index.php`**

    -   **Nazwa klasy i klasa nadrzędna:** `SrratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako rezerwowy lub domyślny punkt wejścia dla routingu front-office modułu. W wielu modułach `index.php` w katalogu kontrolera front-office jest używany do obsługi podstawowej trasy dla modułu, jeśli nie jest wymagana żadna konkretna akcja. Może przekierowywać lub po prostu wyświetlać pustą stronę, jeśli nie jest wyraźnie używany do funkcji. Dla tego modułu jego podstawowa funkcja jest prawdopodobnie minimalna, ponieważ `cronjob.php` obsługuje główną logikę front-office.

#### Kontrolery administracyjne Back-Office

Moduł nie wykorzystuje żadnych niestandardowych kontrolerów administracyjnych. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Bezpośrednio współdziała z podstawową klasą `Currency` i klasą `Configuration` PrestaShop w celu zarządzania ustawieniami i aktualizacji kursów.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Wszystkie interakcje na stronie konfiguracji są obsługiwane przez standardowe elementy formularzy PrestaShop i potencjalnie jQuery, jeśli jest używane bezpośrednio w metodzie `getContent()`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja strony konfiguracji opiera się wyłącznie na domyślnych stylach szablonu Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`srrates/views/admin.tpl`**
    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Ten szablon służy do renderowania formularza konfiguracji modułu w Panelu administracyjnym PrestaShop. Wyświetla przełącznik „Włącz moduł”, „URL zadania Cron” oraz dynamiczną listę walut z odpowiednimi polami wejściowymi „Narzut / Upust (%)”. Jest odpowiedzialny za wizualny układ danych wyjściowych `getContent()`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne (takie jak `PS_SRRATES_ENABLED` i indywidualne narzuty walut) bezpośrednio w tabeli `ps_configuration` PrestaShop.

    -   `ps_configuration`: Przechowuje ustawienia modułu. Klucze zazwyczaj mają wzorzec taki jak `PS_SRRATES_ENABLED` dla głównego przełącznika i potencjalnie `PS_SRRATES_MARKUP_EUR` dla narzutów specyficznych dla waluty.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Nie jest wyraźnie używany przez ten moduł do wyświetlania danych, ale `install()` może go zarejestrować jako standardową praktykę. |
| `displayRightColumn` | W prawej kolumnie stron front-office. | Nie jest wyraźnie używany przez ten moduł do wyświetlania danych. |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | Nie jest wyraźnie używany przez ten moduł do wyświetlania danych. |
| `displayFooter` | W sekcji stopki każdej strony front-office. | Nie jest wyraźnie używany przez ten moduł do wyświetlania danych. |
| `displayProductExtraContent` | Na stronie produktu, poniżej głównej zawartości. | Nie jest wyraźnie używany przez ten moduł do wyświetlania danych. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Nie jest wyraźnie używany przez ten moduł, ponieważ jego funkcja to aktualizacja kursów, a nie przetwarzanie zamówień. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany, przed renderowaniem. | Potencjalnie używany do ładowania CSS/JS dla strony konfiguracji modułu, chociaż nie ma niestandardowych zasobów. |
| `actionModuleInstall` | Podczas instalacji modułu. | Używany do wykonania początkowej konfiguracji, tworzenia wpisów konfiguracyjnych i rejestrowania hooków. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Używany do czyszczenia wpisów konfiguracyjnych i wyrejestrowywania hooków. |

Główna funkcjonalność modułu (aktualizacja kursów) jest wyzwalana przez kontroler front-office `cronjob.php`, a nie bezpośrednio przez hook PrestaShop, chociaż sam moduł jest instalowany i zarządzany za pomocą standardowych hooków modułów.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Sveriges Riksbank - kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do zasobów wsparcia.
