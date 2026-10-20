---
title: "Database Optimization Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Database Optimization Pro od MyPresta.eu."
sidebar:
  label: "Database Optimization Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Database Optimization Pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/database-optimization-pro/)
>
> ---


# Database Optimization Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Dostęp do panelu sterowania hostingu (cPanel, Plesk itp.) w celu konfiguracji zadań cron jest wysoce zalecany dla pełnych możliwości automatyzacji modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po instalacji, kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji Database Optimization Pro. Tutaj ustawisz automatyczne czyszczenie i uzyskasz niezbędne informacje do zadania cron.

Strona konfiguracji jest prosta i zapewnia podstawowe narzędzia do zarządzania optymalizacją bazy danych.

#### **URL zadania Cron**

- **Co robi to ustawienie:** Jest to unikalny adres internetowy (URL), który po odwiedzeniu uruchamia proces optymalizacji bazy danych. Jest on zaprojektowany do wywoływania przez zautomatyzowany system (zadanie cron), a nie przez człowieka przeglądającego go.
- **Wpływ zmiany tego ustawienia:** Nie możesz zmienić tego adresu URL bezpośrednio z konfiguracji modułu. Jest on generowany automatycznie przez moduł.
- **Zalecana wartość:** Skopiuj ten adres URL dokładnie tak, jak się pojawia. Będzie Ci potrzebny do skonfigurowania zadania cron na Twoim serwerze hostingowym.
- **Scenariusz/przykład dla sprzedawcy:** Skopiujesz ten adres URL i wkleisz go do interfejsu konfiguracji zadania cron udostępnionego przez Twojego hosta internetowego (np. cPanel, Plesk lub niestandardowy menedżer zadań cron). To informuje Twój serwer: „co X godzin/dni, odwiedź ten adres URL, aby wyczyścić moją bazę danych”.

#### **Uruchom optymalizację teraz**

- **Co robi to ustawienie:** Jest to ręczny wyzwalacz do natychmiastowego uruchomienia procesu optymalizacji bazy danych. Wykonuje te same działania czyszczące co URL zadania cron, ale na żądanie.
- **Wpływ zmiany tego ustawienia:**
  - *Po kliknięciu:* Moduł natychmiast rozpocznie czyszczenie Twojej bazy danych. Po zakończeniu zobaczysz komunikat potwierdzający.
- **Zalecana wartość:** Użyj tego przycisku do początkowego testowania po instalacji lub jeśli musisz wykonać natychmiastowe czyszczenie poza zaplanowanymi zadaniami cron.
- **Scenariusz/przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz zobaczyć go w akcji, lub wprowadziłeś wiele zmian w swoim sklepie (np. zaimportowałeś wiele produktów) i chcesz natychmiast posprzątać, nie czekając na następne zaplanowane zadanie cron.

#### **Konfiguracja zadania Cron**

To najważniejsza część automatyzacji optymalizacji bazy danych. Zadanie cron to harmonogram zadań oparty na czasie w systemach operacyjnych podobnych do Unix. Pozwala on na automatyczne uruchamianie poleceń lub skryptów w określonym czasie lub interwale.

**Kroki do konfiguracji zadania cron (ogólny przewodnik – konkretne kroki mogą się różnić w zależności od hosta):**

1.  **Zaloguj się do panelu sterowania hostingu:** Zazwyczaj jest to cPanel, Plesk lub niestandardowy panel sterowania dostarczony przez Twojego hosta.
2.  **Znajdź „Zadania Cron” lub „Zaplanowane zadania”:** Poszukaj sekcji związanej z zadaniami cron, często w „Zaawansowane” lub „Narzędzia”.
3.  **Dodaj nowe zadanie Cron:**
    - Zazwyczaj będziesz musiał określić częstotliwość (np. raz dziennie, raz w tygodniu). Dobrym punktem wyjścia jest raz dziennie lub raz na kilka dni.
    - Będziesz musiał podać „Polecenie” lub „URL do wywołania”. Tutaj wklejasz **URL zadania Cron**, który skopiowałeś ze strony konfiguracji modułu.
    - Format polecenia często wygląda tak:

      Terminal window

      ```
      wget -q -O /dev/null "TWÓJ\_URL\_ZADANIA\_CRON\_TUTAJ"
      ```

      Zastąp `"TWÓJ_URL_ZADANIA_CRON_TUTAJ"` dokładnym adresem URL z modułu. Polecenie `wget` pobiera adres URL, a `-q -O /dev/null` zapewnia, że działa cicho bez zapisywania danych wyjściowych, co jest idealne dla zadań w tle.
4.  **Zapisz zadanie Cron:** Potwierdź swoje ustawienia, aby aktywować zaplanowane zadanie.

**Przykładowe częstotliwości zadań Cron:**

-   **Raz dziennie (np. 3:00):**
    `0 3 * * * wget -q -O /dev/null "TWÓJ_URL_ZADANIA_CRON_TUTAJ"`
-   **Raz w tygodniu (np. w każdą niedzielę o 4:00):**
    `0 4 * * 0 wget -q -O /dev/null "TWÓJ_URL_ZADANIA_CRON_TUTAJ"`

Wybierz czas, kiedy Twój sklep ma zazwyczaj niski ruch, aby zminimalizować potencjalny (choć zazwyczaj znikomy) wpływ na wydajność podczas czyszczenia.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | URL zadania Cron | (Generowany automatycznie) | Adres URL, który ma być wywoływany przez system zadań cron Twojego hostingu w celu uruchomienia automatycznej optymalizacji bazy danych. Skopiuj go dokładnie. |
| Konfiguracja modułu | Uruchom optymalizację teraz | Kliknij, aby wykonać | Ręcznie uruchamia natychmiastowe czyszczenie bazy danych. Przydatne do testowania lub optymalizacji na żądanie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem zadanie cron, ale nie widzę żadnej różnicy w szybkości mojego sklepu.**
O: Optymalizacja bazy danych zapewnia stopniowe ulepszenia. Jeśli Twój sklep był już stosunkowo szybki, zmiana może nie być dramatyczna.
- **Sprawdź swoje zadanie cron:** Upewnij się, że jest poprawnie skonfigurowane na Twoim hoście i działa. Niektórzy hosty udostępniają logi wykonania zadań cron.
- **Uruchom ręcznie:** Kliknij „Uruchom optymalizację teraz” w konfiguracji modułu. Jeśli to działa, problem prawdopodobnie leży w konfiguracji zadania cron.
- **Wyczyść pamięć podręczną Smarty:** Czasami zmiany wizualne lub poprawa szybkości wymagają wyczyszczenia pamięci podręcznej PrestaShop. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”.

**P: Jakie dane faktycznie czyści ten moduł?**
O: Moduł celuje w różne typy tymczasowych i przestarzałych danych, które gromadzą się w Twojej bazie danych, takie jak:
- Stare koszyki gości, które nigdy nie zostały przekształcone w zamówienia.
- Wygasłe sesje.
- Stare wpisy w logach (logi dostępu, logi stron nie znalezionych).
- Pliki tymczasowe i dane pamięci podręcznej przechowywane w bazie danych.
NIE usuwa danych klientów, zamówień, produktów ani żadnych istotnych informacji o sklepie.

**P: Czy ten moduł może zepsuć mój sklep?**
O: Ten moduł jest zaprojektowany do bezpiecznego usuwania tylko nieistotnych, tymczasowych lub przestarzałych danych. Nie dotyka krytycznych danych sklepu, takich jak produkty, zamówienia, klienci czy kategorie. Jednak, jak w przypadku każdego modułu, który wchodzi w interakcje z Twoją bazą danych, zawsze zaleca się posiadanie aktualnej kopii zapasowej przed instalacją i konfiguracją.

**P: Mój dostawca hostingu nie obsługuje zadań cron, lub mam problem z ich konfiguracją.**
O: Jeśli nie możesz skonfigurować zadania cron, nadal możesz używać modułu, ręcznie klikając przycisk „Uruchom optymalizację teraz” na stronie konfiguracji modułu, gdy poczujesz, że Twój sklep wymaga czyszczenia (np. raz w tygodniu lub raz w miesiącu). Chociaż nie jest to automatyczne, nadal zapewnia korzyści z optymalizacji bazy danych. Skontaktuj się z pomocą techniczną swojego dostawcy hostingu w celu uzyskania pomocy w konfiguracji zadań cron; zazwyczaj są bardzo pomocni w tej powszechnej kwestii.

**P: Czy ten moduł wpływa na moje SEO?**
O: Pośrednio tak. Szybsze czasy ładowania stron są pozytywnym czynnikiem rankingowym dla wyszukiwarek takich jak Google. Poprawiając szybkość Twojej witryny, ten moduł przyczynia się do lepszego doświadczenia użytkownika, co może pozytywnie wpłynąć na Twoją wydajność SEO.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Database Optimization Pro` to lekkie narzędzie administracyjne, skupiające się głównie na konserwacji bazy danych. Jego podstawowa funkcjonalność polega na wykonywaniu serii zapytań SQL w celu oczyszczenia nieistotnych danych. Aspekt „Pro” wprowadza zautomatyzowany mechanizm za pośrednictwem kontrolera front-office zaprojektowanego do wyzwalania przez zadanie cron, umożliwiając zaplanowaną, bezobsługową optymalizację. Przestrzega struktury modułu PrestaShop, wykorzystując główny plik modułu do instalacji/konfiguracji oraz dedykowany kontroler front-end do wykonywania zadań cron.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/CronCleaner.php`
        -   **Nazwa klasy**: `DboptimizationproCronCleanerModuleFrontController`
        -   **Klasa nadrzędna**: `ModuleFrontController`
        -   **Odpowiedzialność**: Jest to krytyczny kontroler dla funkcjonalności zadań cron. Po uzyskaniu dostępu wykonuje logikę czyszczenia bazy danych. Jest zaprojektowany do wywoływania zewnętrznie (np. przez `wget` za pośrednictwem zadania cron) i nie renderuje widocznej strony dla użytkownika. Wykonuje rzeczywiste zapytania optymalizacyjne bazy danych.
    -   `controllers/front/index.php`
        -   **Nazwa klasy**: (Nie jest klasą, zazwyczaj pusty plik lub przekierowanie)
        -   **Odpowiedzialność**: Ten plik jest często dołączany do modułów PrestaShop, aby zapobiec listowaniu katalogów podczas przeglądania `twojsklep.com/modules/dboptimizationpro/controllers/front/`. Zazwyczaj zawiera proste `header('Location: ../../../index.php'); exit;` lub podobne, aby przekierować do strony głównej, zapewniając bezpieczeństwo.
-   **Kontrolery administracyjne Back-Office**:

    -   Brak dedykowanych kontrolerów administracyjnych. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Brak niestandardowych klas lub definicji `ObjectModel` w katalogu `classes/`. Logika modułu jest hermetyzowana w głównym pliku modułu (`dboptimizationpro/cronjob.php`) i kontrolerze front-end `CronCleaner`. Interakcje z bazą danych są prawdopodobnie bezpośrednimi zapytaniami SQL wykonywanymi za pomocą `Db::getInstance()->execute()`.

### 4.4 Zasoby JavaScript (`views/js/`)

W archiwum modułu nie znaleziono niestandardowych plików JavaScript. Funkcjonalność modułu jest po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

W archiwum modułu nie znaleziono niestandardowych plików CSS. Strona konfiguracji modułu wykorzystuje standardowe style panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

W archiwum modułu nie znaleziono niestandardowych plików szablonów Smarty (`.tpl`). Formularz konfiguracji modułu jest renderowany bezpośrednio w metodzie `getContent()` głównego pliku modułu za pomocą pomocniczych formularzy PrestaShop lub czystego HTML.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Współpracuje z istniejącymi tabelami PrestaShop w celu usunięcia przestarzałych danych (np. `ps_cart`, `ps_connections`, `ps_log`, `ps_guest`, `ps_pagenotfound`).
    -   Ustawienia konfiguracji (takie jak URL zadania cron lub flaga wskazująca ostatnie uruchomienie) są przechowywane w tabeli `ps_configuration`, zazwyczaj z kluczami poprzedzonymi `DBOPTIMIZATIONPRO_`.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie żadnych hooków front-office (np. `displayHeader`, `displayRightColumn`, `displayFooter`) do wyświetlania treści. Jego główna interakcja z systemem hooków PrestaShop dotyczy instalacji/odinstalowania modułu i potencjalnie integracji menu back-office (chociaż nie jest jawnie wymieniony jako kontroler administracyjny, sam moduł pojawia się na liście Modułów).

    Główna funkcjonalność modułu jest wyzwalana przez:

    -   Dostęp do metody `getContent()` w panelu administracyjnym w celu ręcznej konfiguracji i wykonania.
    -   Dostęp do kontrolera front-end `CronCleaner` za pośrednictwem zewnętrznego zadania cron.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i pobrania najnowszych wersji modułu „Database Optimization Pro”, prosimy zalogować się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
