---
title: "Aktualizacja kursów walut NBP - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop 'Aktualizacja kursów walut NBP' od MyPresta.eu."
sidebar:
  label: "Aktualizacja kursów walut NBP - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł NBP currency rates update na MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbp-currency-rates-update.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/nbp-currency-rates-update/)
>
> ---


# Aktualizacja kursów walut NBP

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL, są zazwyczaj wymagane i są standardem w większości nowoczesnych środowisk hostingowych. Twój hosting musi również obsługiwać konfigurację zadań cron.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Aktualizacja kursów walut NBP”. Zostanie wyświetlony główny ekran konfiguracji.

#### **URL zadania Cron**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, którego użyjesz do skonfigurowania zautomatyzowanego zadania („cron job”) na swoim serwerze WWW. Gdy ten adres URL zostanie wywołany, moduł połączy się z serwerami NBP, pobierze najnowsze kursy walut i zaktualizuje je w Twoim sklepie PrestaShop.
- **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł.
- **Zalecana wartość:** Skopiuj ten adres URL dokładnie tak, jak się pojawia.
- **Scenariusz / przykład sprzedawcy:** Weźmiesz ten adres URL i wkleisz go do sekcji „Zadania Cron” w panelu sterowania swojego hostingu (np. cPanel, Plesk lub niestandardowa konfiguracja crona serwera). To poinformuje Twój serwer, aby odwiedzał ten adres URL w określonych odstępach czasu (np. codziennie o 3 rano), automatycznie uruchamiając proces aktualizacji walut.

#### **Częstotliwość zadania Cron**

- **Co robi to ustawienie:** To nie jest ustawienie, które zmieniasz *wewnątrz* PrestaShop, ale raczej zalecenie, jak często powinieneś ustawić zadanie cron serwera, aby wywoływało ten adres URL.
- **Wpływ zmiany tego ustawienia:** Ten tekst jedynie doradza. Rzeczywista częstotliwość jest kontrolowana przez konfigurację zadania cron Twojego serwera.
- **Zalecana wartość:** „Raz dziennie” jest zazwyczaj wystarczające dla większości sklepów, ponieważ kursy NBP zazwyczaj aktualizują się codziennie.
- **Scenariusz / przykład sprzedawcy:** Jeśli ustawisz zadanie cron serwera tak, aby uruchamiało się codziennie, kursy walut w Twoim sklepie będą odświeżane raz na 24 godziny, zapewniając, że są zawsze aktualne z danymi NBP. Uruchamianie go częściej (np. co godzinę) jest zazwyczaj niepotrzebne i może nadmiernie obciążać Twój serwer lub API NBP.

#### **Ważna uwaga dotycząca zadań Cron**

- **Co robi to ustawienie:** Ta sekcja zawiera kluczowe instrukcje dotyczące konfiguracji zadania cron na Twoim serwerze. Wyjaśnia, że musisz uzyskać dostęp do panelu sterowania swojego hostingu (takiego jak cPanel lub Plesk) i dodać nowe zadanie cron.
- **Wpływ zmiany tego ustawienia:** Jest to tekst informacyjny. Musisz postępować zgodnie z tymi instrukcjami poza PrestaShop.
- **Zalecana wartość:** Przeczytaj to uważnie i postępuj zgodnie z krokami dostarczonymi przez Twojego dostawcę hostingu w celu konfiguracji zadań cron.
- **Scenariusz / przykład sprzedawcy:** Twój dostawca hostingu będzie miał sekcję, zazwyczaj nazywaną „Zadania Cron” lub „Zaplanowane zadania”, gdzie możesz dodać nowe polecenie. Zazwyczaj wybierzesz częstotliwość (np. „Raz dziennie”), a następnie wkleisz „URL zadania Cron” do pola polecenia, często poprzedzonego `wget -q -O /dev/null`. Jeśli nie jesteś pewien, skontaktuj się z pomocą techniczną swojego dostawcy hostingu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | URL zadania Cron | (Unikalny URL) | Adres URL do wyzwalania automatycznych aktualizacji walut za pośrednictwem zadania cron serwera. Skopiuj to do konfiguracji serwera. |
| Konfiguracja modułu | Częstotliwość zadania Cron | Raz dziennie | Zalecenie, jak często wykonywać zadanie cron na serwerze, aby kursy były aktualne. |
| Konfiguracja modułu | Instrukcje konfiguracji zadania Cron | N/A | Wskazówki dotyczące konfiguracji zadania cron na serwerze hostingu WWW. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy walut nie aktualizują się, nawet po skonfigurowaniu zadania cron. Co powinienem zrobić?**
O:

1. **Sprawdź URL zadania Cron:** Upewnij się, że skopiowałeś adres URL dokładnie ze strony konfiguracji modułu i wkleiłeś go poprawnie do ustawień zadania cron w panelu sterowania hostingu.
2. **Zweryfikuj wykonanie zadania Cron:** Sprawdź logi zadań cron swojego dostawcy hostingu (jeśli są dostępne), aby zobaczyć, czy zadanie cron faktycznie działa o zaplanowanej godzinie. Czasami polecenie może być nieprawidłowe lub ścieżka do `wget` może wymagać dostosowania.
3. **Przetestuj ręcznie:** Spróbuj odwiedzić „URL zadania Cron” bezpośrednio w przeglądarce internetowej. Powinno to wywołać natychmiastową aktualizację. Jeśli kursy zaktualizują się po ręcznym odwiedzeniu, problem dotyczy konfiguracji zadania cron Twojego serwera, a nie samego modułu.
4. **Sprawdź waluty PrestaShop:** Upewnij się, że waluty, które chcesz aktualizować, są włączone w PrestaShop (**Międzynarodowe > Waluty**) i że mają prawidłowy kod ISO, który NBP może rozpoznać (np. USD, EUR, GBP).
5. **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe wyświetlenie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P: Czy ten moduł aktualizuje wszystkie waluty w moim sklepie?**
O: Aktualizuje waluty, dla których NBP udostępnia kursy wymiany, w stosunku do PLN. Moduł jest wystarczająco inteligentny, aby przeliczyć te kursy na domyślną walutę Twojego sklepu. Na przykład, jeśli Twoja domyślna waluta to EUR, a NBP udostępnia USD/PLN i EUR/PLN, moduł może obliczyć USD/EUR. Jeśli NBP nie udostępnia kursu dla konkretnej waluty, kurs tej waluty nie zostanie zaktualizowany przez ten moduł.

**P: Czy mogę ustawić częstotliwość aktualizacji na częstszą niż raz dziennie?**
O: Chociaż możesz skonfigurować zadanie cron serwera tak, aby uruchamiało się częściej (np. co godzinę), kursy wymiany NBP zazwyczaj aktualizują się raz dziennie. Uruchamianie zadania cron częściej niż codziennie jest zazwyczaj niepotrzebne i nie dostarczy świeższych danych, ale też nie zaszkodzi.

**P: Otrzymuję komunikat o błędzie, gdy próbuję skonfigurować moduł lub gdy uruchamia się zadanie cron.**
O:

1. **Sprawdź wersję PHP:** Upewnij się, że Twoja wersja PHP mieści się w obsługiwanym zakresie (PHP 5.6 - 8.5).
2. **Łączność z serwerem:** Moduł musi połączyć się ze stroną NBP, aby pobrać kursy. Upewnij się, że Twój serwer ma wychodzący dostęp do Internetu i nie jest blokowany przez zaporę sieciową przed dostępem do zewnętrznych adresów URL.
3. **Tryb debugowania PrestaShop:** Włącz tryb debugowania PrestaShop (**Zaawansowane > Wydajność > Tryb debugowania**), aby zobaczyć bardziej szczegółowe komunikaty o błędach, które mogą pomóc w zlokalizowaniu problemu. Pamiętaj, aby wyłączyć go po zakończeniu rozwiązywania problemów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Aktualizacja kursów walut NBP` to lekki moduł PrestaShop zaprojektowany przede wszystkim do wykonywania jednego, krytycznego zadania: pobierania i aktualizowania kursów wymiany walut z Narodowego Banku Polskiego (NBP) za pośrednictwem zaplanowanego zadania cron. Przestrzega standardowej struktury modułu PrestaShop, wykorzystując `ModuleFrontController` dla swojego punktu końcowego cron i główną klasę modułu do konfiguracji i instalacji. Główna logika znajduje się w pliku `cronjob.php`, który działa zarówno jako główna klasa modułu, jak i punkt wejścia do wykonania crona.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `nbprates/controllers/front/cronjob.php`
    - **Nazwa klasy i klasa nadrzędna**: `NbpratesCronjobModuleFrontController` rozszerza `ModuleFrontController`
    - **Odpowiedzialność**: Ten kontroler służy jako publiczny punkt końcowy dla zadania cron. Po uzyskaniu dostępu za pośrednictwem unikalnego adresu URL wygenerowanego przez moduł, wyzwala logikę aktualizacji walut. Nie renderuje żadnych wizualnych danych wyjściowych, ale wykonuje proces pobierania i aktualizowania kursów. Jest zaprojektowany do wywoływania przez `wget` lub `curl` z harmonogramu cron serwera.
  - `nbprates/controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna**: `NbpratesIndexModuleFrontController` rozszerza `ModuleFrontController`
    - **Odpowiedzialność**: Jest to kontroler-placeholder, często dołączany do modułów, aby zapobiec listowaniu katalogów, jeśli `index.php` nie jest obecny w katalogu `controllers/front`. Zazwyczaj nie robi nic więcej niż przekierowanie na stronę główną lub wyświetlenie błędu „404 Not Found”. Nie zawiera żadnej specyficznej logiki biznesowej dla tego modułu.
- **Kontrolery Back-Office Admin**:

  - Brak. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego modułu.

### 4.3 Główne klasy i modele (`classes/`)

- Brak. Logika modułu jest głównie zawarta w głównym pliku modułu (`nbprates/cronjob.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

- Brak. Moduł nie używa żadnego niestandardowego JavaScriptu.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie używa żadnego niestandardowego CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:
  - `nbprates/views/admin.tpl`
    - **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównej klasy modułu (`NbpratesCronjob`) w celu wyświetlenia formularza konfiguracji modułu w Panelu administracyjnym PrestaShop.
    - **Zawartość**: Zazwyczaj wyświetla „URL zadania Cron” i instrukcje dotyczące konfiguracji zadania cron. Jest to statyczne wyświetlanie informacji, a nie interaktywny formularz z polami wejściowymi.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoją konfigurację (konkretnie wygenerowany token crona) w tabeli `ps_configuration`. Klucz dla tokena crona to zazwyczaj `NBP_CRON_TOKEN`.
  - Aktualizuje istniejące kursy wymiany walut w tabeli `ps_currency` (konkretnie kolumnę `conversion_rate`).
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje się jawnie do żadnych standardowych hooków wyświetlania PrestaShop (takich jak `displayHeader`, `displayFooter` itp.) do renderowania front-office. Jego głównym „hookiem” jest punkt końcowy `ModuleFrontController`, który jest wywoływany zewnętrznie przez zadanie cron serwera.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `install()` | Podczas instalacji modułu | Tworzy unikalny token crona i przechowuje go w `ps_configuration`. |
| `uninstall()` | Podczas deinstalacji modułu | Usuwa token crona z `ps_configuration`. |
| `actionFrontControllerSetMedia` | Niezarejestrowany jawnie, ale `ModuleFrontController` niejawnie obsługuje ładowanie zasobów, jeśli takie byłyby obecne. | N/A (moduł nie ładuje żadnych zasobów). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Aktualizacja kursów walut NBP”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu i integracji z Twoim sklepem PrestaShop.
