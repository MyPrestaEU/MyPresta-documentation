---
title: "Norges Bank - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Norges Bank - kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Norges Bank - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Norges Bank - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/norges-bank-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/norges-bank-currency-exchange-rates/)
>
> ---


# Norges Bank - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych. Twoje środowisko hostingowe musi również obsługiwać zadania CRON dla automatycznych aktualizacji.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „Norges Bank - kursy wymiany walut”. Tutaj kontrolujesz, jak i kiedy aktualizowane są kursy walut.

#### **Ustawienia i opcje**

1.  **URL CRON do automatycznych aktualizacji:**

    *   **Co robi to ustawienie:** Jest to unikalny adres internetowy (URL), który po odwiedzeniu uruchamia moduł w celu pobrania najnowszych kursów wymiany z Norges Bank i zaktualizowania ich w Twoim sklepie PrestaShop.
    *   **Skutek zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego URL-a. Jest on generowany przez moduł. Potrzebujesz tego URL-a, aby skonfigurować zautomatyzowane zadanie („zadanie CRON”) na swoim serwerze hostingowym.
    *   **Zalecana wartość:** Skopiuj ten URL dokładnie tak, jak się pojawia.
    *   **Scenariusz / przykład dla sprzedawcy:** Udostępnisz ten URL swojemu dostawcy hostingu lub użyjesz go w panelu sterowania hostingu (takim jak cPanel lub Plesk), aby zaplanować zadanie, które regularnie odwiedza ten URL (np. raz dziennie). Zapewnia to, że Twoje kursy są zawsze świeże, bez konieczności ręcznego działania.
2.  **Marża kursu wymiany (%):**

    *   **Co robi to ustawienie:** Pozwala to dodać procentową marżę do kursów wymiany pobranych z Norges Bank. Na przykład, jeśli oficjalny kurs wynosi 1 EUR = 10 NOK, a Ty ustawisz marżę 2%, Twój sklep może używać 1 EUR = 9.8 NOK (lub 10.2 NOK, w zależności od kierunku obliczeń, zazwyczaj sprawiając, że waluta obca jest nieco droższa dla klienta, aby pokryć koszty konwersji).
    *   **Skutek zmiany tego ustawienia:**
        *   *Gdy ustawione na 0:* Twój sklep używa dokładnych oficjalnych kursów wymiany dostarczonych przez Norges Bank.
        *   *Gdy ustawione na wartość dodatnią (np. 2):* Moduł dostosowuje kursy wymiany, aby uwzględnić ten procent, efektywnie dając Ci mały bufor lub marżę zysku na konwersjach walutowych. Może to pomóc pokryć opłaty transakcyjne lub po prostu zwiększyć Twoją rentowność.
    *   **Zalecana wartość:** Zacznij od `0`, jeśli chcesz dokładnych kursów. Jeśli musisz pokryć koszty lub dodać niewielki zysk, wartość między `0.5` a `2` procent jest powszechna.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja bramka płatności pobiera 1% opłaty za transakcje międzynarodowe, ustawienie tutaj 1% marży może pomóc Ci wchłonąć ten koszt bez wpływu na ceny produktów w Twojej walucie bazowej.
3.  **Ostatnia aktualizacja:**

    *   **Co robi to ustawienie:** Wyświetla datę i godzinę ostatniej pomyślnej aktualizacji kursów wymiany w Twoim sklepie przez moduł.
    *   **Skutek zmiany tego ustawienia:** Jest to pole informacyjne i nie można go zmienić. Pomaga zweryfikować, czy Twoje zadanie CRON działa poprawnie i czy Twoje kursy są regularnie aktualizowane.
    *   **Zalecana wartość:** Okresowo sprawdzaj to pole, aby upewnić się, że aktualizacje odbywają się zgodnie z oczekiwaniami.
    *   **Scenariusz / przykład dla sprzedawcy:** Po skonfigurowaniu zadania CRON możesz sprawdzić to pole następnego dnia, aby potwierdzić, że moduł pomyślnie uruchomił się i zaktualizował kursy.

#### **Przycisk ręcznej aktualizacji**

-   **Co robi ten przycisk:** Ten przycisk umożliwia ręczne wywołanie natychmiastowej aktualizacji wszystkich kursów wymiany z Norges Bank.
-   **Skutek kliknięcia tego przycisku:** Moduł natychmiast pobierze najnowsze kursy i zastosuje je w Twoim sklepie. Jest to przydatne do testowania lub jeśli potrzebujesz natychmiastowej aktualizacji poza zaplanowanym zadaniem CRON.
-   **Zalecane użycie:** Użyj tego do początkowego testowania po konfiguracji lub jeśli nastąpiła znacząca, nagła fluktuacja waluty, którą chcesz natychmiast odzwierciedlić.

#### **Instrukcje konfiguracji zadania CRON**

Poniżej ustawień znajdziesz jasne instrukcje, jak skonfigurować zadanie CRON na swoim serwerze. Jest to kluczowe dla „bezobsługowego” działania modułu.

-   **Co robi ta sekcja:** Dostarcza dokładną komendę lub metodę, której musisz użyć z harmonogramem zadań CRON Twojego dostawcy hostingu.
-   **Skutek wykonania tych instrukcji:** Po skonfigurowaniu, Twój serwer będzie automatycznie odwiedzał URL CRON w określonych odstępach czasu (np. raz dziennie), zapewniając, że Twoje kursy wymiany są zawsze aktualne bez ręcznej interwencji.
-   **Zalecana częstotliwość:** Codzienne aktualizacje są zazwyczaj wystarczające. W przypadku walut o dużej zmienności lub dużej liczby międzynarodowych sprzedaży, możesz rozważyć aktualizację dwa razy dziennie.
-   **Scenariusz / przykład dla sprzedawcy:** W cPanelu przejdziesz do „Zadań Cron”, wybierzesz wspólne ustawienie, takie jak „Raz dziennie”, i wkleisz podaną komendę w polu „Komenda”.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | URL CRON do automatycznych aktualizacji | (Wygenerowany URL) | URL do wywołania automatycznych aktualizacji kursów za pomocą zadania CRON. **Kluczowe dla automatyzacji.** |
| Konfiguracja modułu | Marża kursu wymiany (%) | 0 | Dodaje procentowy bufor do kursów wymiany dla rentowności/pokrycia kosztów. |
| Konfiguracja modułu | Ostatnia aktualizacja | (Data/Godzina) | Pole informacyjne pokazujące ostatnią pomyślną aktualizację kursów. |
| Konfiguracja modułu | Przycisk ręcznej aktualizacji | N/A | Natychmiast pobiera i stosuje najnowsze kursy. Przydatne do testowania/pilnych aktualizacji. |
| Konfiguracja modułu | Instrukcje konfiguracji zadania CRON | N/A | Przewodnik po konfiguracji automatycznych aktualizacji na serwerze hostingowym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy wymiany nie aktualizują się automatycznie. Co powinienem zrobić?**
O: Jest to prawie zawsze związane z konfiguracją zadania CRON na Twoim serwerze.
1.  **Zweryfikuj zadanie CRON:** Dokładnie sprawdź swój panel sterowania hostingiem (cPanel, Plesk itp.), aby upewnić się, że zadanie CRON jest poprawnie skonfigurowane z dokładnym adresem URL dostarczonym przez moduł i że jest zaplanowane do uruchomienia.
2.  **Ścieżka CRON:** Czasami ścieżka PHP w poleceniu CRON musi być absolutna (np. `/usr/bin/php` zamiast tylko `php`). Twój dostawca hostingu może to potwierdzić.
3.  **Sprawdź „Ostatnia aktualizacja”:** Jeśli pole „Ostatnia aktualizacja” w konfiguracji modułu nigdy się nie zmienia, potwierdza to, że zadanie CRON nie wykonuje skryptu aktualizacji modułu.
4.  **Ręczna aktualizacja:** Spróbuj kliknąć przycisk „Ręczna aktualizacja” w konfiguracji modułu. Jeśli to działa, potwierdza to, że sam moduł może pobierać kursy, co jednoznacznie wskazuje na problem z zadaniem CRON.

**P: Kursy wymiany wydają się nieprawidłowe lub niewiele się zmieniły.**
O:
1.  **Sprawdź Norges Bank:** Porównaj kursy w swoim sklepie z oficjalnymi kursami opublikowanymi przez Norges Bank (ich strona internetowa jest zazwyczaj dostępna poprzez szybkie wyszukiwanie).
2.  **Ustawienie marży:** Pamiętaj, że Twoje ustawienie „Marża kursu wymiany (%)” nieznacznie dostosuje kursy. Upewnij się, że jest ono ustawione zgodnie z zamierzeniami.
3.  **Ostatnia aktualizacja:** Sprawdź pole „Ostatnia aktualizacja”. Jeśli jest stare, Twoje zadanie CRON nie działa.

**P: Czy ten moduł wpływa na moją domyślną walutę?**
O: Nie, moduł aktualizuje tylko *wartości* kursów wymiany dla walut innych niż domyślna, w stosunku do Twojej domyślnej waluty. Wartość Twojej domyślnej waluty pozostaje niezmieniona.

**P: Zaktualizowałem swój szablon, a teraz selektor walut nie działa poprawnie.**
O: Ten moduł aktualizuje tylko *wartości* kursów wymiany. Wizualne wyświetlanie i funkcjonalność samego selektora walut są obsługiwane przez rdzeń PrestaShop lub Twój szablon. Jeśli selektor nie działa, prawdopodobnie jest to problem z szablonem lub rdzeniem PrestaShop, niezwiązany bezpośrednio z tym modułem. Wyczyść pamięć podręczną Smarty (**Zaawansowane > Wydajność**) i sprawdź konfigurację swojego szablonu.

**P: Czy mogę używać tego modułu z innymi modułami walutowymi?**
O: Ogólnie nie zaleca się uruchamiania wielu modułów, które próbują aktualizować kursy wymiany, ponieważ mogą one kolidować lub nadpisywać swoje dane. Ten moduł jest zaprojektowany jako samodzielne rozwiązanie dla kursów Norges Bank. Jeśli potrzebujesz kursów z innego źródła, powinieneś wyłączyć ten moduł i użyć innego.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Norges Bank - kursy wymiany walut” (`nbrates`) to lekki moduł PrestaShop, skupiający się przede wszystkim na jednym, krytycznym zadaniu: pobieraniu i aktualizowaniu kursów wymiany walut. Wykorzystuje klasę `Module` PrestaShop do instalacji i konfiguracji oraz używa kontrolera frontowego do udostępniania punktu końcowego CRON dla automatycznych aktualizacji. Podstawowa logika obejmuje wykonanie żądania HTTP do API Norges Bank, parsowanie odpowiedzi XML, obliczanie kursów krzyżowych i aktualizowanie tabeli `ps_currency` PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy**: `NbratesCronjobModuleFrontController`
        -   **Klasa nadrzędna**: `ModuleFrontController`
        -   **Odpowiedzialność**: Ten kontroler obsługuje wykonanie zadania CRON. Po uzyskaniu dostępu za pośrednictwem swojego adresu URL (podanego w konfiguracji modułu) wywołuje metodę `cronjob()` w głównej klasie modułu `nbrates`. Jest przeznaczony do wywoływania przez zewnętrzny harmonogram (CRON) i wyświetla prostą wiadomość o sukcesie/niepowodzeniu. Nie renderuje żadnej zawartości wizualnej dla użytkownika.
    -   `controllers/front/index.php`
        -   **Nazwa klasy**: `NbratesIndexModuleFrontController`
        -   **Klasa nadrzędna**: `ModuleFrontController`
        -   **Odpowiedzialność**: Jest to kontroler-placeholder, często dołączany do modułów, ale nieaktywnie używany w podstawowej funkcjonalności tego konkretnego modułu. Zazwyczaj służy jako domyślny punkt wejścia, jeśli moduł ma dedykowaną stronę front-office. W tym module jego głównym celem jest prawdopodobnie zapobieganie listowaniu katalogów, jeśli `cronjob.php` jest dostępny bezpośrednio bez określonej akcji.
-   **Kontrolery administracyjne Back Office**:

    -   Brak. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

-   Brak. Podstawowa logika modułu jest zawarta w głównym pliku `nbrates/cronjob.php`. Jest to powszechne w przypadku prostszych modułów, które nie wymagają złożonych struktur danych ani rozległych interakcji z bazą danych poza standardową konfiguracją.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Brak. Moduł nie zawiera żadnego niestandardowego kodu JavaScript dla funkcjonalności Front Office ani Back Office.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Brak. Moduł nie zawiera żadnych niestandardowych arkuszy stylów CSS. Konfiguracja Back Office opiera się na domyślnej stylizacji panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównej klasy modułu (`nbrates/cronjob.php`) w celu wyświetlenia formularza konfiguracji modułu w Panelu administracyjnym PrestaShop.
        -   **Zawartość**: Zazwyczaj zawiera strukturę HTML do wyświetlania adresu URL CRON, pola wprowadzania marży kursu wymiany, informacji o „Ostatniej aktualizacji”, przycisku ręcznej aktualizacji i instrukcji konfiguracji zadania CRON. Wykorzystuje standardowe pomocniki formularzy i stylizację PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Współpracuje ze standardową tabelą `ps_configuration` PrestaShop w celu przechowywania swoich ustawień (np. `NBS_LAST_UPDATE`, `NBS_MARGIN`).
    -   Aktualizuje tabelę `ps_currency`, w szczególności kolumnę `conversion_rate` dla walut innych niż domyślna.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` Back Office. | Służy do dołączania niezbędnych CSS/JS dla strony konfiguracji modułu (chociaż w tym module nie są używane). |
| `actionAdminControllerSetMedia` | Wywoływany przed renderowaniem kontrolera administracyjnego. | Służy do rejestrowania zasobów (JS/CSS) dla stron administracyjnych. |
| `actionCronJob` | Niestandardowy hook, wywoływany przez kontroler frontowy `cronjob`. | Główny hook, w którym wykonywana jest logika aktualizacji walut modułu. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` Front Office. | (Nie jest jawnie używany przez ten moduł do wyświetlania, ale często rejestrowany przez moduły). |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie Front Office. | (Nie jest jawnie używany przez ten moduł do wyświetlania). |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie Front Office. | (Nie jest jawnie używany przez ten moduł do wyświetlania). |
| `displayFooter` | Renderuje zawartość w stopce Front Office. | (Nie jest jawnie używany przez ten moduł do wyświetlania). |
| `displayProductExtraContent` | Renderuje zawartość na stronie produktu. | (Nie jest jawnie używany przez ten moduł do wyświetlania). |

*Uwaga: Chociaż opis modułu wspomina o hookach Front Office, takich jak nagłówek, kolumny, produkt lub stopka, inwentaryzacja dostarczonego kodu nie pokazuje żadnych szablonów ani konkretnej logiki do renderowania zawartości w tych hookach. Możliwe, że są to ogólne hooki zarejestrowane podczas instalacji, ale nieaktywnie wykorzystywane do wizualnego wyświetlania przez ten konkretny moduł, ponieważ jego funkcja to czysta synchronizacja danych zaplecza.*

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Norges Bank - kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do zasobów wsparcia bezpośrednio z platformy MyPresta.eu.
