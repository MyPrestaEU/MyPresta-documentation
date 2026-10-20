---
title: "Danmarks Nationalbank - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Danmarks Nationalbank - kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Danmarks Nationalbank - kursy wymiany walut - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Danmarks Nationalbank - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/danmarks-nationalbank-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/danmarks-nationalbank-currency-exchange-rates/)
>
> ---


# Danmarks Nationalbank - kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych. Są one prawie zawsze dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień. To tutaj będziesz zarządzać sposobem pobierania i stosowania kursów wymiany.

Strona konfiguracji wyświetli listę wszystkich aktywnych walut w Twoim sklepie, umożliwiając zarządzanie kursem wymiany i marżą zysku dla każdej z nich.

**Dla każdej wymienionej waluty (np. USD, EUR, GBP):**

- **Aktualny kurs wymiany:**

  - **Co robi to ustawienie:** To pole wyświetla aktualny kurs wymiany dla tej waluty w stosunku do domyślnej waluty Twojego sklepu (np. DKK, jeśli Twój sklep ma siedzibę w Danii). Wartość ta jest automatycznie aktualizowana przez moduł, gdy uruchomione zostanie zadanie cron.
  - **Wpływ zmiany tego ustawienia:** Możesz ręcznie dostosować tę wartość, jeśli zajdzie taka potrzeba, ale głównym celem modułu jest automatyzacja tego procesu. Wszelkie ręczne zmiany zostaną nadpisane przez następne uruchomienie zadania cron.
  - **Zalecana wartość:** Pozwól modułowi aktualizować to automatycznie. Ręcznie dostosowuj tylko w przypadku tymczasowych, specyficznych potrzeb.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli moduł jeszcze się nie uruchomił lub jeśli musisz szybko dostosować kurs przed następną zaplanowaną aktualizacją, możesz zmienić go ręcznie. Jednak dla długoterminowej dokładności polegaj na automatycznych aktualizacjach.
- **Narzut / Upust (%):**

  - **Co robi to ustawienie:** Pozwala to dodać procentową marżę zysku (narzut) lub rabat (upust) do pobranego kursu wymiany.
    - Wartość dodatnia (np. `+2%`) zwiększy kurs wymiany, co oznacza, że klienci zapłacą nieco więcej w tej walucie, zapewniając pokrycie opłat za konwersję lub niewielki zysk.
    - Wartość ujemna (np. `-1%`) zmniejszy kurs wymiany, sprawiając, że cena w walucie obcej będzie nieco niższa.
  - **Wpływ zmiany tego ustawienia:** Ten procent jest stosowany *po* pobraniu oficjalnego kursu z Danmarks Nationalbank.
    - *Gdy ustawiono `+2%` dla USD:* Jeśli oficjalny kurs wynosi 1 USD = 6.50 DKK, Twój sklep będzie używał 1 USD = 6.63 DKK (6.50 \* 1.02).
    - *Gdy ustawiono `-1%` dla EUR:* Jeśli oficjalny kurs wynosi 1 EUR = 7.45 DKK, Twój sklep będzie używał 1 EUR = 7.3755 DKK (7.45 \* 0.99).
  - **Zalecana wartość:** Zacznij od `0%` i dostosuj w oparciu o swój model biznesowy, opłaty bramki płatniczej i pożądane marże zysku. Wielu sprzedawców dodaje niewielki narzut (np. od `0.5%` do `2%`), aby pokryć koszty transakcji.
  - **Scenariusz / przykład dla sprzedawcy:** Twój procesor płatności pobiera 1.5% opłaty za konwersję EUR na DKK. Możesz ustawić narzut `+1.5%` dla EUR, aby skutecznie przerzucić ten koszt na klienta i utrzymać swoją marżę zysku.

**URL zadania Cron:**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, który musisz ustawić jako zadanie cron na swoim serwerze. Gdy ten adres URL zostanie wywołany, moduł łączy się z Danmarks Nationalbank, pobiera najnowsze kursy wymiany, stosuje zdefiniowane narzuty/upusty i aktualizuje je w Twoim sklepie PrestaShop.
- **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł.
- **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go w panelu sterowania swojego hostingu (cPanel, Plesk itp.) lub za pomocą usługi cron.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kursy wymiany aktualizowały się codziennie o 3 rano. Skopiujesz ten adres URL i skonfigurujesz zadanie cron na swoim serwerze, aby wykonywało je codziennie o 3 rano.

**Przycisk Zapisz:**

- **Co robi to ustawienie:** Stosuje wszelkie zmiany, które wprowadziłeś w procentach narzutu/upustu.
- **Wpływ zmiany tego ustawienia:** Twoje nowe marże zysku zostaną zapisane i zastosowane przy następnym uruchomieniu zadania cron i aktualizacji kursów.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Aktualny kurs wymiany** (dla każdej waluty) | Automatycznie aktualizowane przez cron | Wyświetla aktualny kurs; ręczne zmiany są tymczasowe. |
| Strona konfiguracji modułu | **Narzut / Upust (%)** (dla każdej waluty) | `0%` (dostosuj w razie potrzeby) | Dodaje procent do pobranego kursu, aby zarządzać marżami zysku lub pokrywać opłaty. |
| Strona konfiguracji modułu | **URL zadania Cron** | Unikalny URL (skopiuj i skonfiguruj) | URL do wyzwalania automatycznych aktualizacji kursów z Danmarks Nationalbank. |
| Strona konfiguracji modułu | **Przycisk Zapisz** | N/A | Zapisuje Twoje niestandardowe procenty narzutu/upustu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy wymiany nie aktualizują się. Co powinienem zrobić?**
O:

1. **Sprawdź zadanie Cron:** Najczęstszą przyczyną jest nieprawidłowo skonfigurowane lub nieuruchomione zadanie cron. Zweryfikuj u swojego dostawcy hostingu, czy adres URL zadania cron podany w konfiguracji modułu jest poprawnie zaplanowany i wykonywany.
2. **Status modułu:** Upewnij się, że moduł jest włączony w Panelu administracyjnym PrestaShop.
3. **Łączność z serwerem:** Potwierdź, że Twój serwer ma dostęp do Internetu, aby połączyć się z API Danmarks Nationalbank.
4. **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe wyświetlanie zaktualizowanych kursów. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P: Czy mogę ustawić różne narzuty dla różnych walut?**
O: Tak, absolutnie! To jedna z podstawowych funkcji tego modułu. Na stronie konfiguracji modułu znajdziesz oddzielne pole „Narzut / Upust (%)” dla każdej aktywnej waluty w Twoim sklepie.

**P: Co się stanie, jeśli usługa Danmarks Nationalbank będzie tymczasowo niedostępna?**
O: Moduł spróbuje pobrać kursy. Jeśli mu się to nie uda, zazwyczaj zachowa ostatnie pomyślnie zaktualizowane kursy. Jest zaprojektowany tak, aby był odporny, ale stałe awarie mogą wskazywać na problem z łącznością serwera po Twojej stronie lub długotrwałą awarię źródła.

**P: Czy ten moduł wpłynie na moje SEO lub adresy URL produktów?**
O: Nie, ten moduł zarządza tylko kursami wymiany walut. Nie zmienia adresów URL produktów, opisów meta ani żadnych innych elementów związanych z SEO. Jego wpływ dotyczy wyłącznie wyświetlania cen.

**P: Mój niestandardowy motyw nie wyświetla poprawnie zaktualizowanych cen.**
O: Ten moduł aktualizuje podstawowe kursy wymiany PrestaShop. Jeśli Twój motyw używa standardowych funkcji PrestaShop do wyświetlania cen, powinien odzwierciedlać zmiany. Jeśli nie, może to być problem z pamięcią podręczną (wyczyść pamięć podręczną jak powyżej) lub wysoce dostosowany motyw, który omija standardowe renderowanie cen PrestaShop. W takich rzadkich przypadkach może być konieczne, aby programista internetowy zbadał logikę wyświetlania cen w Twoim motywie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Danmarks Nationalbank - kursy wymiany walut”.

### 4.1 Przegląd architektury

Moduł jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie podejście oparte na cronie do aktualizacji kursów wymiany walut. Wykorzystuje system konfiguracji PrestaShop do ustawień i kontrolery frontowe do wykonywania zadań cron. Główna logika znajduje się w głównym pliku modułu, obsługując wywołania API do Danmarks Nationalbank i aktualizując wpisy w tabeli `ps_currency`.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `dnbrates/controllers/front/cronjob.php`
    - **Nazwa klasy i klasa nadrzędna**: `DnbratesCronjobModuleFrontController` rozszerzający `ModuleFrontController`.
    - **Odpowiedzialność**: Ten kontroler jest punktem wejścia dla zadania cron. Po uzyskaniu dostępu za pośrednictwem unikalnego adresu URL podanego w konfiguracji modułu w Panelu administracyjnym, wyzwala proces aktualizacji kursów. Jest zaprojektowany do wywoływania zewnętrznie przez harmonogram cron po stronie serwera. Obsługuje logikę pobierania danych z Danmarks Nationalbank i aktualizacji tabeli `ps_currency`.
  - `dnbrates/controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna**: `DnbratesIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    - **Odpowiedzialność**: Jest to kontroler-placeholder, często dołączany do modułów, ale nieaktywnie używany do konkretnego wyświetlania w front-office w kontekście tego modułu. Może służyć jako domyślny punkt wejścia lub do przyszłej rozbudowy.
- **Kontrolery administracyjne Back-Office**: Brak. Cała konfiguracja Panelu administracyjnego jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

W katalogu `classes/` nie znaleziono żadnych niestandardowych klas ani definicji `ObjectModel`. Moduł bezpośrednio współdziała z podstawową klasą `Currency` i klasą `Configuration` PrestaShop w celu zarządzania kursami wymiany i ustawieniami.

### 4.4 Zasoby JavaScript (`views/js/`)

W archiwum modułu nie znaleziono żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

W archiwum modułu nie znaleziono żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:
  - `dnbrates/views/admin.tpl`
    - **Cel**: Ten szablon renderuje formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Wyświetla listę walut, ich aktualne kursy wymiany, pola wprowadzania procentów narzutu/upustu oraz adres URL zadania cron. Jest renderowany przez metodę `getContent()` głównego pliku modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Głównie współdziała z tabelą `ps_currency` (konkretnie z kolumną `conversion_rate`) w celu aktualizacji kursów wymiany.
  - Ustawienia specyficzne dla modułu (takie jak procenty narzutu/upustu dla każdej waluty i adres URL crona) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy zazwyczaj poprzedzonych prefiksem `DNBRATES_`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front-office. | Niewykorzystywany bezpośrednio do wyświetlania treści, ale moduły często rejestrują się tutaj w celu ładowania zasobów lub inicjalizacji. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie stron front-office. | Niewykorzystywany bezpośrednio do wyświetlania treści przez ten moduł. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie stron front-office. | Niewykorzystywany bezpośrednio do wyświetlania treści przez ten moduł. |
| `displayFooter` | Renderuje zawartość w stopce stron front-office. | Niewykorzystywany bezpośrednio do wyświetlania treści przez ten moduł. |
| `displayProductAdditionalInfo` | Renderuje zawartość na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Niewykorzystywany bezpośrednio do wyświetlania treści przez ten moduł. |
| `actionUpdateCurrency` | Wykonywany po zaktualizowaniu szczegółów waluty. | Moduł prawdopodobnie używa tego lub podobnego hooka wewnętrznie, aby zapewnić zastosowanie jego logiki, gdy dane waluty ulegną zmianie. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (JS/CSS). | Może być używany do ładowania określonych zasobów dla strony konfiguracji modułu, chociaż nie ma niestandardowych plików JS/CSS. |

*Uwaga: Główna funkcja modułu (aktualizacja kursów) jest wyzwalana przez kontroler frontowy za pośrednictwem crona, a nie przez standardowy hook PrestaShop w cyklu życia żądania.*

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Danmarks Nationalbank - kursy wymiany walut”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
