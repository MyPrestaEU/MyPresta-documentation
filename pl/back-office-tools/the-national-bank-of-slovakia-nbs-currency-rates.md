---
title: "Narodowy Bank Słowacji (NBS) – kursy walut – Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop Narodowy Bank Słowacji (NBS) – kursy walut od MyPresta.eu."
sidebar:
  label: "Narodowy Bank Słowacji (NBS) – kursy walut – Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł The National Bank of Slovakia (NBS) - currency rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/the-national-bank-of-slovakia-nbs-currency-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/the-national-bank-of-slovakia-nbs-currency-rates/)
>
> ---


# Narodowy Bank Słowacji (NBS) – kursy walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych, które są niemal powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień.

#### **1. Włącz / Wyłącz moduł**

- **Co robi to ustawienie:** Jest to standardowy przełącznik PrestaShop do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Moduł rozpocznie pobieranie i aktualizowanie kursów walut zgodnie z Twoimi ustawieniami.
  - *Gdy wyłączony:* Moduł zatrzyma wszystkie operacje, a Twoje kursy walut nie będą już automatycznie aktualizowane danymi z NBS.
- **Zalecana wartość:** **TAK** (aby włączyć funkcjonalność modułu).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli tymczasowo chcesz zatrzymać automatyczne aktualizacje (np. podczas konserwacji lub jeśli przełączysz się na ręczne zarządzanie kursami), możesz go wyłączyć. W przeciwnym razie pozostaw go włączonym dla ciągłych aktualizacji.

#### **2. Adres URL CRON do automatycznych aktualizacji**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, który musisz skonfigurować jako „zadanie cron” na swoim serwerze hostingowym. Zadanie cron to zaplanowane zadanie, które nakazuje serwerowi odwiedzać ten adres URL w regularnych odstępach czasu, co powoduje, że moduł pobiera i automatycznie aktualizuje najnowsze kursy walut NBS.
- **Efekt zmiany tego ustawienia:**
  - *Po prawidłowym skonfigurowaniu jako zadanie cron:* Twoje kursy walut będą aktualizowane automatycznie bez żadnej ręcznej interwencji.
  - *Gdy nie jest skonfigurowane jako zadanie cron:* Moduł nie będzie automatycznie aktualizował kursów. Musiałbyś ręcznie odwiedzić ten adres URL w swojej przeglądarce, aby wywołać aktualizację (co niweczy cel automatyzacji).
- **Zalecana wartość:** Jest to wygenerowany adres URL. Powinieneś **skopiować ten adres URL** i wkleić go do harmonogramu zadań cron w panelu sterowania swojego hostingu.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoje kursy walut aktualizowały się codziennie o 3 rano. Skopiowałbyś ten adres URL, przeszedł do panelu hostingowego (np. cPanel, Plesk lub poprosił o pomoc swojego hosta) i utworzył zadanie cron, które wykonuje ten adres URL codziennie o 3 rano.

#### **3. Dodaj procentową marżę do kursów wymiany**

- **Co robi to ustawienie:** Pozwala dodać wartość procentową do oficjalnych kursów wymiany pobranych z NBS. Ta marża jest stosowana do wszystkich walut aktualizowanych przez moduł.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na 0 (lub pozostawione puste):* Twoje kursy wymiany będą dokładnie takie, jak podane przez NBS.
  - *Gdy ustawione na wartość dodatnią (np. 2):* Moduł zwiększy kurs wymiany NBS o ten procent (np. jeśli kurs wynosi 1 EUR = 1.10 USD, z marżą 2% staje się 1 EUR = 1.122 USD). To skutecznie sprawia, że Twoje produkty są nieco droższe, gdy są płacone w walucie innej niż bazowa.
- **Zalecana wartość:** **0** (jeśli chcesz dokładnych kursów NBS) lub mały dodatni procent (np. **1-3%**) w celu pokrycia opłat transakcyjnych lub zmienności rynkowej.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz uwzględnić potencjalne opłaty bankowe przy konwersji płatności lub po prostu chcesz mieć mały bufor na sprzedaż międzynarodową. Ustawienie tego na „2” doda 2% marży do wszystkich zaktualizowanych kursów wymiany.

#### **4. Aktualizuj tylko wybrane waluty**

- **Co robi to ustawienie:** Ta opcja pozwala wybrać konkretne waluty w Twoim sklepie PrestaShop, które powinny być aktualizowane przez moduł NBS. Jeśli masz wiele walut, ale chcesz, aby NBS zarządzał tylko kilkoma, jest to przydatne.
- **Efekt zmiany tego ustawienia:**
  - *Gdy niezaznaczone:* Moduł spróbuje zaktualizować wszystkie aktywne waluty w Twoim sklepie PrestaShop, dla których dostępny jest odpowiedni kurs z NBS.
  - *Gdy zaznaczone i wybrane są konkretne waluty:* Tylko wybrane waluty będą miały swoje kursy wymiany zaktualizowane przez moduł. Inne waluty zachowają swoje istniejące kursy (ręczne lub z innych źródeł).
- **Zalecana wartość:** **Zaznacz to pole** i wybierz tylko te waluty, którymi aktywnie zarządzasz za pomocą danych NBS. Zapobiega to niezamierzonym zmianom w innych walutach.
- **Scenariusz / przykład dla sprzedawcy:** Twoja waluta bazowa to EUR, a sprzedajesz również w USD i CZK. Chcesz, aby NBS aktualizował kursy USD i CZK, ale ręcznie zarządzasz kursami GBP. Zaznaczyłbyś to pole i wybrał tylko USD i CZK z listy.

#### **5. Lista walut do aktualizacji**

- **Co robi to ustawienie:** Jest to lista wielokrotnego wyboru, która pojawia się tylko wtedy, gdy zaznaczono „Aktualizuj tylko wybrane waluty”. Pokazuje wszystkie aktywne waluty w Twoim sklepie PrestaShop, umożliwiając wybór, które z nich moduł powinien aktualizować.
- **Efekt zmiany tego ustawienia:**
  - *Wybieranie walut:* Te waluty będą miały swoje kursy wymiany automatycznie aktualizowane przez moduł NBS.
  - *Odznaczanie walut:* Te waluty zostaną zignorowane przez moduł NBS, a ich kursy nie zostaną zmienione.
- **Zalecana wartość:** Wybierz wszystkie waluty, dla których chcesz używać kursów NBS.
- **Scenariusz / przykład dla sprzedawcy:** Zgodnie z poprzednim przykładem, kliknąłbyś „USD” i „CZK” na tej liście, aby upewnić się, że tylko te są aktualizowane.

#### **6. Przycisk Zapisz**

- **Co robi to ustawienie:** Stosuje wszystkie zmiany, które wprowadziłeś na stronie konfiguracji.
- **Efekt zmiany tego ustawienia:** Twoje ustawienia modułu zostaną zapisane i zaczną obowiązywać natychmiast (dla przyszłych uruchomień zadań cron lub ręcznych aktualizacji).
- **Zalecana wartość:** Zawsze kliknij **„Zapisz”** po wprowadzeniu jakichkolwiek zmian.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz moduł | TAK | Aktywuje/dezaktywuje funkcjonalność modułu. |
| Konfiguracja modułu | Adres URL CRON do automatycznych aktualizacji | Wygenerowany URL | Skopiuj i skonfiguruj jako zadanie cron dla automatycznych aktualizacji kursów. |
| Konfiguracja modułu | Dodaj procentową marżę do kursów wymiany | 0 (lub 1-3%) | Dodaje procentowy bufor do kursów NBS dla strategii cenowej. |
| Konfiguracja modułu | Aktualizuj tylko wybrane waluty | Zaznacz i wybierz | Ogranicza aktualizacje NBS do konkretnych wybranych walut. |
| Konfiguracja modułu | Lista walut do aktualizacji | Wybierz pożądane | Wybierz, które aktywne waluty otrzymują aktualizacje kursów NBS. |
| Konfiguracja modułu | Przycisk Zapisz | Kliknij po zmianach | Zapisuje wszystkie ustawienia konfiguracji modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy walut nie aktualizują się automatycznie. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**.
2.  **Zweryfikuj zadanie Cron:** Najczęstszym problemem jest nieprawidłowo skonfigurowane zadanie cron.
    - Wróć do strony konfiguracji modułu i ponownie skopiuj „Adres URL CRON”.
    - Zaloguj się do panelu sterowania swojego hostingu (cPanel, Plesk itp.) i przejdź do sekcji „Zadania Cron” lub „Zaplanowane zadania”.
    - Dokładnie sprawdź, czy adres URL jest dokładnie taki, jak podany przez moduł, i czy harmonogram (np. codziennie, co godzinę) jest prawidłowy.
    - Upewnij się, że polecenie używa `wget` lub `curl` do wykonania adresu URL (np. `wget -O /dev/null "TWÓJ_ADRES_URL_CRON_TUTAJ"`).
    - W razie wątpliwości skontaktuj się z pomocą techniczną swojego dostawcy hostingu, podając adres URL CRON i poproś ich o skonfigurowanie go dla Ciebie.
3.  **Sprawdź logi serwera:** Twój dostawca hostingu może mieć logi wykonania zadań cron, które mogą wskazać, czy wystąpił błąd.

**P2: Moduł jest włączony, ale niektóre waluty się nie aktualizują.**
O:

1.  **Sprawdź „Aktualizuj tylko wybrane waluty”:** Przejdź do konfiguracji modułu. Jeśli „Aktualizuj tylko wybrane waluty” jest zaznaczone, upewnij się, że konkretne waluty, które mają być aktualizowane, są wybrane na liście „Lista walut do aktualizacji”.
2.  **Dostępność danych NBS:** Narodowy Bank Słowacji może nie dostarczać kursów dla wszystkich walut. Moduł może aktualizować tylko te waluty, dla których NBS publikuje dane. Sprawdź oficjalną stronę internetową NBS pod kątem dostępnych par walutowych.
3.  **Status waluty w PrestaShop:** Upewnij się, że dane waluty są aktywne w Twoim sklepie PrestaShop (**Międzynarodowe > Waluty**). Nieaktywne waluty nie mogą być aktualizowane.

**P3: Jak często powinienem uruchamiać zadanie cron?**
O: Dla większości sklepów uruchamianie zadania cron raz dziennie jest wystarczające, aby kursy były aktualne. Jeśli Twoja firma wymaga niezwykle aktualnych kursów ze względu na dużą liczbę transakcji międzynarodowych lub niestabilne rynki, możesz ustawić je tak, aby uruchamiało się częściej (np. co 6 lub 12 godzin), ale codziennie jest zazwyczaj wystarczające.

**P4: Dodałem marżę, ale ceny nie wydają się jej odzwierciedlać.**
O:

1.  **Zapisz ustawienia:** Upewnij się, że kliknąłeś przycisk „Zapisz” po ustawieniu marży.
2.  **Wywołaj aktualizację:** Marża zostanie zastosowana dopiero przy następnej aktualizacji kursów wymiany. Nastąpi to przy następnym uruchomieniu zadania cron, lub możesz ręcznie wywołać aktualizację, odwiedzając adres URL CRON w swojej przeglądarce.
3.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może przechowywać stare wartości. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).

**P5: Czy ten moduł wpłynie na moją walutę bazową?**
O: Nie, moduł aktualizuje kursy wymiany *w stosunku* do Twojej waluty bazowej. Wartość Twojej waluty bazowej pozostaje stała. Na przykład, jeśli Twoja waluta bazowa to EUR, moduł zaktualizuje, ile USD lub CZK równa się 1 EUR.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Narodowy Bank Słowacji (NBS) – kursy walut” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie główną klasę modułu (`cronjob.php`) do konfiguracji i zarządzania hookami, oraz kontroler frontowy (`cronjob.php`) do obsługi wykonania zadania cron. Współpracuje z podstawowym zarządzaniem walutami PrestaShop w celu aktualizacji kursów. Główną funkcją modułu jest pobieranie danych zewnętrznych (kursów NBS) i integrowanie ich z modelem obiektu `Currency` PrestaShop.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nazwa klasy i klasa nadrzędna:** `NbsratesCronjobModuleFrontController` rozszerzająca `ModuleFrontController`.
    - **Odpowiedzialność:** Ten kontroler jest specjalnie zaprojektowany do wywoływania przez zadanie cron. Po uzyskaniu dostępu inicjuje proces pobierania najnowszych kursów walut z Narodowego Banku Słowacji i aktualizowania ich w bazie danych PrestaShop. Nie renderuje żadnych wizualnych danych wyjściowych do przeglądarki, ale wykonuje przetwarzanie w tle. Obsługuje logikę stosowania skonfigurowanej marży procentowej i aktualizowania tylko wybranych walut.
  - `controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna:** Jest to zazwyczaj pusty plik lub symbol zastępczy, często używany do zapobiegania listowaniu katalogów lub do zapewnienia prawidłowego punktu wejścia dla starszych wersji PrestaShop. Nie zawiera specyficznej logiki modułu dla kursów NBS.
- **Kontrolery administracyjne Back-Office**: Brak. Cała administracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie definiuje niestandardowych klas `ObjectModel`. Bezpośrednio współpracuje z podstawową klasą `Currency` PrestaShop w celu aktualizacji kursów wymiany.

### 4.4 Zasoby JavaScript (`views/js/`)

Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Brak. Moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Cel:** Ten szablon jest renderowany, gdy strona konfiguracji modułu jest dostępna w Panelu administracyjnym PrestaShop. Wyświetla pola wejściowe do włączania/wyłączania modułu, adres URL CRON, procent marży i opcje wyboru waluty. Wykorzystuje standardowe pomocniki i elementy formularzy PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Moduł nie tworzy niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop.

  - `PS_NBS_RATES_ENABLED`: Przechowuje status włączenia/wyłączenia modułu.
  - `PS_NBS_RATES_MARGIN`: Przechowuje procentową marżę do zastosowania.
  - `PS_NBS_RATES_SELECTED_CURRENCIES`: Przechowuje serializowaną tablicę identyfikatorów walut, jeśli aktywna jest opcja „Aktualizuj tylko wybrane waluty”.
  - `PS_NBS_RATES_CRON_TOKEN`: Przechowuje unikalny token dla adresu URL cron w celach bezpieczeństwa.
- **Tabela zarejestrowanych hooków**:
  Moduł używa głównie hooka `actionFrontControllerSetMedia` (niejawnie, gdyby miał ładować zasoby, choć tego nie robi) i opiera się na swoich metodach `install()` i `uninstall()` do konfiguracji i czyszczenia. Jego podstawowa funkcjonalność jest wywoływana przez kontroler frontowy `cronjob.php`, a nie przez tradycyjny hook PrestaShop.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `install()` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne w `ps_configuration` i rejestruje moduł. |
| `uninstall()` | Podczas deinstalacji modułu | Czyści wartości konfiguracyjne z `ps_configuration`. |
| (Zadanie Cron) | Zewnętrzne żądanie HTTP do `controllers/front/cronjob.php` | Pobiera kursy NBS, stosuje marżę i aktualizuje tabelę `ps_currency`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Narodowy Bank Słowacji (NBS) – kursy walut”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
