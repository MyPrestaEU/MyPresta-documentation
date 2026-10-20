---
title: "Bank of Finland - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Bank of Finland - kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Bank of Finland - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bank of Finland - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-finland-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/bank-of-finland-currency-exchange-rates/)
>
> ---


# Bank of Finland - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych. Twoje środowisko hostingowe musi również obsługiwać zadania CRON dla automatycznych aktualizacji.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do ustawień modułu. Tutaj zdefiniujesz, w jaki sposób kursy wymiany są aktualizowane i stosowane.

#### **1. Adres URL CRON**

-   **Co robi to ustawienie:** Jest to unikalny adres internetowy (URL), który po odwiedzeniu wyzwala moduł do pobrania najnowszych kursów wymiany z Banku Finlandii i zaktualizowania ich w Twoim sklepie PrestaShop.
-   **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł. Ten adres URL jest kluczowy do skonfigurowania zautomatyzowanego zadania (zadania CRON) na Twoim serwerze WWW.
-   **Zalecana wartość:** Skopiuj ten adres URL dokładnie tak, jak się pojawia.
-   **Scenariusz / przykład dla sprzedawcy:** Udostępnisz ten adres URL swojemu dostawcy hostingu lub użyjesz go w panelu sterowania hostingu (np. cPanel, Plesk) do skonfigurowania zadania CRON. Zapewni to automatyczną aktualizację kursów wymiany, na przykład raz dziennie, bez konieczności ręcznego klikania czegokolwiek.

#### **2. Instrukcje konfiguracji zadania CRON**

-   **Co robi to ustawienie:** Ta sekcja zawiera instrukcje dotyczące konfiguracji zadania CRON przy użyciu podanego powyżej adresu URL. Zadanie CRON to harmonogram zadań oparty na czasie w systemach operacyjnych typu Unix. Umożliwia planowanie automatycznego uruchamiania poleceń lub skryptów w określonych odstępach czasu.
-   **Wpływ zmiany tego ustawienia:** Jest to sekcja informacyjna; niczego tutaj nie zmieniasz. Prawidłowe przestrzeganie tych instrukcji zapewnia automatyczną aktualizację kursów wymiany.
-   **Zalecana wartość:** Przeczytaj i postępuj zgodnie z tymi instrukcjami.
-   **Scenariusz / przykład dla sprzedawcy:** Panel sterowania Twojego dostawcy hostingu (jak cPanel) będzie miał sekcję „Zadania Cron” lub „Zaplanowane zadania”. Zazwyczaj dodasz nowe zadanie cron, określisz częstotliwość (np. raz dziennie o 3 rano) i wkleisz adres URL CRON do pola polecenia, często poprzedzonego `wget -q -O /dev/null`.

#### **3. Marża (%)**

-   **Co robi to ustawienie:** Pozwala to dodać procentową marżę do pobranych kursów wymiany. Na przykład, jeśli oficjalny kurs wynosi 1 EUR = 1.10 USD, a Ty ustawisz marżę 2%, moduł użyje 1 EUR = 1.078 USD (1.10 \* 0.98) lub 1 EUR = 1.122 USD (1.10 \* 1.02) w zależności od tego, jak moduł stosuje marżę (zazwyczaj w celu ochrony przed wahaniami, więc może nieznacznie zwiększyć cenę w walucie obcej).
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy ustawione na 0:* Kursy wymiany zostaną zaktualizowane dokładnie tak, jak podał Bank Finlandii.
    -   *Gdy ustawione na wartość dodatnią (np. 2):* Moduł dostosuje kurs wymiany o ten procent. Może to pomóc pokryć opłaty transakcyjne, koszty konwersji walut lub po prostu zapewnić niewielki bufor przed niekorzystnymi ruchami kursów, zapewniając utrzymanie marż zysku.
-   **Zalecana wartość:** Zacznij od 0. Jeśli napotkasz problemy z rentownością z powodu wahań walutowych lub opłat za konwersję, rozważ niewielką marżę, taką jak 1-3%.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz produkt za 100 EUR, a kurs wymiany wynosi 1 EUR = 1.10 USD, produkt kosztowałby 110 USD. Jeśli ustawisz marżę 2%, moduł może obliczyć kurs jako 1 EUR = 1.078 USD, co sprawi, że produkt będzie kosztował 107.80 USD. Daje to niewielki bufor.

#### **4. Ostatnia aktualizacja**

-   **Co robi to ustawienie:** Wyświetla datę i godzinę ostatniej pomyślnej aktualizacji kursów wymiany przez moduł.
-   **Wpływ zmiany tego ustawienia:** Jest to pole informacyjne i nie można go bezpośrednio zmienić. Służy jako weryfikacja, że Twoje zadanie CRON działa poprawnie, a moduł aktywnie aktualizuje kursy.
-   **Zalecana wartość:** Powinna wyświetlać aktualną datę i godzinę, idealnie w ciągu ostatnich 24 godzin, jeśli Twoje zadanie CRON działa codziennie.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli ustawisz zadanie CRON na codzienne uruchamianie o 3 rano, powinieneś zobaczyć, że znacznik czasu „Ostatnia aktualizacja” zmienia się, odzwierciedlając 3 rano (lub krótko po) bieżącego dnia każdego ranka. Jeśli się nie aktualizuje, wskazuje to na problem z konfiguracją zadania CRON.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Adres URL CRON | Skopiuj dokładnie | Unikalny adres URL do wyzwalania aktualizacji kursów za pomocą zadania CRON. |
| Konfiguracja modułu | Instrukcje konfiguracji zadania CRON | Przeczytaj uważnie | Wskazówki dotyczące konfiguracji automatycznych aktualizacji na Twoim serwerze. |
| Konfiguracja modułu | Marża (%) | 0 (lub 1-3% w razie potrzeby) | Dodaje procentowy bufor do kursów wymiany w celu ochrony marż zysku. |
| Konfiguracja modułu | Ostatnia aktualizacja | N/A (informacyjne) | Pokazuje znacznik czasu ostatniej pomyślnej aktualizacji kursów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje kursy wymiany nie aktualizują się. Co powinienem zrobić?**
O1: Jest to prawie zawsze związane z konfiguracją zadania CRON.
1.  **Sprawdź znacznik czasu „Ostatnia aktualizacja”:** Przejdź do strony konfiguracji modułu. Jeśli ta data jest stara, Twoje zadanie CRON nie działa.
2.  **Zweryfikuj konfigurację zadania CRON:** Zaloguj się do panelu sterowania hostingu (np. cPanel, Plesk). Przejdź do sekcji „Zadania Cron” lub „Zaplanowane zadania”.
    \* Upewnij się, że adres URL CRON skopiowany z modułu jest dokładnie tym, co znajduje się w poleceniu zadania CRON.
    \* Upewnij się, że polecenie jest poprawnie sformatowane (np. `wget -q -O /dev/null "TWÓJ_ADRES_URL_CRON_TUTAJ"`).
    \* Potwierdź, że częstotliwość jest ustawiona zgodnie z życzeniem (np. codziennie).
    \* Sprawdź adres e-mail powiązany z zadaniem CRON (jeśli istnieje) pod kątem komunikatów o błędach.
3.  **Ręcznie uruchom adres URL CRON:** Skopiuj adres URL CRON z konfiguracji modułu i wklej go bezpośrednio do paska adresu przeglądarki internetowej. Powinno to wywołać aktualizację. Jeśli to zadziała, problem na pewno leży w konfiguracji zadania CRON na Twoim serwerze. Jeśli to nie zadziała, może występować problem po stronie serwera, który uniemożliwia modułowi pobieranie danych (np. zapora sieciowa, cURL nie jest włączony).

**P2: Moje ceny w walutach obcych wydają się nieco nieprawidłowe, nawet po aktualizacjach.**
O2: Sprawdź ustawienie „Marża (%)” w konfiguracji modułu. Jeśli masz ustawioną marżę (np. 2%), moduł celowo dostosuje kurs wymiany o ten procent. Jeśli chcesz uzyskać dokładne oficjalne kursy, ustaw marżę na 0. Upewnij się również, że Twoja waluta bazowa w PrestaShop (Lokalizacja > Waluty) jest poprawnie ustawiona na EUR, jeśli głównie operujesz kursami Banku Finlandii.

**P3: Czy ten moduł działa ze wszystkimi walutami?**
O3: Moduł pobiera oficjalne dane referencyjne z Banku Finlandii, który przede wszystkim dostarcza kursy w stosunku do euro. Jednak inteligentnie oblicza kursy krzyżowe dla walut innych niż euro. Oznacza to, że jeśli Bank Finlandii dostarcza kursy EUR do USD i EUR do GBP, moduł może wyprowadzić kurs USD do GBP. Dopóki Bank Finlandii dostarcza kurs dla waluty w stosunku do euro, moduł powinien być w stanie ją zaktualizować.

**P4: Czy muszę wyczyścić pamięć podręczną Smarty po aktualizacjach?**
O4: Nie, zazwyczaj nie. Ten moduł aktualizuje wartości w bazie danych (kursy wymiany). Pamięć podręczna Smarty w PrestaShop wpływa głównie na kompilację szablonów i zawartość statyczną. Zmiany kursów wymiany są dynamiczne i powinny natychmiast odzwierciedlać się w cenach w Twoim sklepie bez konieczności czyszczenia pamięci podręcznej.

**P5: Mój niestandardowy szablon nie wyświetla poprawnie zaktualizowanych cen.**
O5: Moduł aktualizuje podstawowe kursy wymiany w bazie danych PrestaShop. Selektor walut i logika wyświetlania cen w Twoim szablonie powinny automatycznie pobierać te zaktualizowane kursy. Jeśli tak nie jest, prawdopodobnie jest to problem specyficzny dla szablonu, a nie problem z modułem.
1.  **Zweryfikuj wewnętrzne kursy PrestaShop:** Przejdź do **Lokalizacja > Waluty** w swoim Panelu administracyjnym. Sprawdź kolumnę „Kurs wymiany” dla walut innych niż EUR. Jeśli te kursy są poprawnie zaktualizowane, moduł działa.
2.  **Skontaktuj się z twórcą szablonu:** Jeśli kursy są poprawne w Panelu administracyjnym, ale nie na stronie głównej, Twój szablon może mieć niestandardowe buforowanie lub specyficzny sposób obsługi wyświetlania walut, który wymaga uwagi twórcy szablonu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Bank of Finland - kursy wymiany walut” (`sprates`) to lekki moduł PrestaShop zaprojektowany do jednego, krytycznego zadania: automatyzacji aktualizacji kursów wymiany walut. Wykorzystuje kontroler front-office do udostępnienia punktu końcowego wywoływanego przez CRON, który po uzyskaniu dostępu pobiera dane XML z Banku Finlandii, analizuje je i aktualizuje tabelę `ps_currency`. Moduł stosuje standardowy wzorzec MVC PrestaShop dla swojej konfiguracji i wyzwalacza front-end.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `sprates/controllers/front/cronjob.php`
    -   **Nazwa klasy i klasa nadrzędna:** `SpratesCronjobModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to główny kontroler dla zautomatyzowanego procesu aktualizacji. Odpowiada na żądania wysyłane na adres URL CRON. Po wykonaniu:
        1.  Pobiera dane XML z oficjalnego kanału kursów wymiany Banku Finlandii.
        2.  Analizuje XML w celu wyodrębnienia kursów wymiany opartych na EUR.
        3.  W razie potrzeby oblicza kursy krzyżowe dla walut innych niż EUR.
        4.  Stosuje skonfigurowaną marżę.
        5.  Aktualizuje kolumnę `exchange_rate` w tabeli `ps_currency` dla wszystkich aktywnych walut w PrestaShop.
        6.  Aktualizuje znacznik czasu `last_update` w konfiguracji modułu.
        7.  Wyświetla prosty komunikat o sukcesie lub błędzie (często pomijany przez `wget -q -O /dev/null`).
-   `sprates/controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `SpratesIndexModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to kontroler-placeholder, zazwyczaj używany do zapobiegania listowaniu katalogów lub zapewnienia domyślnej akcji, jeśli główna dyspozycja modułu nie jest używana. W kontekście tego modułu prawdopodobnie służy jako rezerwa lub standardowa praktyka PrestaShop dla modułów z kontrolerami front-end, ale główna logika znajduje się w `cronjob.php`.

#### Kontrolery administracyjne Back-Office

Ten moduł nie wykorzystuje żadnych dedykowanych niestandardowych kontrolerów administracyjnych. Cała konfiguracja jest obsługiwana za pomocą głównej metody `getContent()` modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio współdziała z podstawową klasą `Currency` i klasą `Configuration` PrestaShop w celu zarządzania kursami wymiany i ustawieniami modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `sprates/views/admin.tpl`
        -   **Cel:** Ten szablon renderuje formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Wyświetla adres URL CRON, instrukcje konfiguracji, pole wprowadzania marży i znacznik czasu ostatniej aktualizacji. Wykorzystuje standardowe elementy formularza pomocniczego PrestaShop.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Współdziała z istniejącymi tabelami PrestaShop:

-   `ps_currency`: Aktualizuje kolumnę `exchange_rate` dla aktywnych walut.
-   `ps_configuration`: Przechowuje ustawienia specyficzne dla modułu, takie jak `SP_RATES_MARGIN` (dla procentowej marży) i `SP_RATES_LAST_UPDATE` (dla znacznika czasu ostatniej aktualizacji).

#### Tabela zarejestrowanych haków

Ten moduł nie rejestruje żadnych tradycyjnych haków wyświetlania (np. `displayHeader`, `displayFooter`), ponieważ nie ma żadnych wizualnych komponentów front-office. Jego głównym mechanizmem „haka” jest zadanie CRON, które wyzwala jego kontroler front-end.

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionModuleInstall` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne. |
| `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wartości konfiguracyjne. |
| (Zadanie CRON za pośrednictwem kontrolera front-end) | Zaplanowane przez serwer (np. codziennie) | Pobiera, oblicza i aktualizuje kursy wymiany walut. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Bank of Finland - kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
