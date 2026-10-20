---
title: "Bank Łotwy (Latvijas Banka) – kursy wymiany walut – Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Bank Łotwy (Latvijas Banka) – kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Bank Łotwy (Latvijas Banka) – kursy wymiany walut – Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bank of Latvia (Latvijas Banka) - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates/)
>
> ---


# Bank Łotwy (Latvijas Banka) – kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych, które są niemal powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do głównej strony ustawień modułu. To tutaj zdefiniujesz, w jaki sposób moduł pobiera i stosuje kursy wymiany.

Strona konfiguracji modułu „Bank Łotwy (Latvijas Banka) – kursy wymiany walut” jest prosta i zaprojektowana tak, abyś mógł szybko rozpocząć pracę.

**Zrzut ekranu strony konfiguracji (przykład):**
*(Wyobraź sobie zrzut ekranu przedstawiający stronę konfiguracji modułu z polami dla „Adres URL CRON”, „Spread”, „Częstotliwość aktualizacji” i przełącznikiem „Włączony/Wyłączony”)*

#### 2.1.1 Adres URL CRON

-   **Co robi to ustawienie:** Jest to unikalny adres internetowy (URL), który po odwiedzeniu uruchamia moduł w celu pobrania najnowszych kursów wymiany z Banku Łotwy i zaktualizowania ich w Twoim sklepie PrestaShop. Jest on zaprojektowany do automatycznego wywoływania przez „zadanie cron” na Twoim serwerze.
-   **Efekt zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł. Skopiowanie tego adresu URL jest niezbędne do skonfigurowania automatycznych aktualizacji. Jeśli nie skonfigurujesz zadania cron przy użyciu tego adresu URL, kursy wymiany nie będą automatycznie aktualizowane.
-   **Zalecana wartość:** Skopiuj ten adres URL dokładnie tak, jak się pojawia.
-   **Scenariusz/przykład dla sprzedawcy:** Skopiujesz ten adres URL i wkleisz go do sekcji „Zadania Cron” w panelu sterowania hostingu (np. cPanel, Plesk lub podobny interfejs), aby zaplanować codzienne aktualizacje.

#### 2.1.2 Spread (%)

-   **Co robi to ustawienie:** Pozwala to dodać procentowy „bufor” lub marżę do oficjalnych kursów wymiany. Gdy moduł pobierze kurs, zwiększy go o ten procent przed zapisaniem go w Twoim sklepie. Pomaga to chronić Twoje marże zysku przed wahaniami walut i opłatami transakcyjnymi.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy ustawione na 0:* Moduł będzie używał dokładnych kursów wymiany dostarczonych przez Bank Łotwy. Twoje ceny będą bezpośrednio odzwierciedlać oficjalne kursy.
    *   *Gdy ustawione na wartość dodatnią (np. 2%):* Kursy wymiany w Twoim sklepie będą o 2% wyższe niż oficjalne kursy. Oznacza to, że jeśli produkt kosztuje 100 EUR, a oficjalny kurs do USD wynosi 1.10, z 2% spreadem moduł użyje kursu 1.122 (1.10 \* 1.02), co sprawi, że cena w USD wyniesie 112.20.
-   **Zalecana wartość:** Zależy to od Twojego modelu biznesowego, opłat bramki płatniczej i pożądanych marż zysku. Częstym punktem wyjścia może być 0.5% do 2%, aby pokryć koszty transakcji i drobne wahania.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój procesor płatności pobiera 1% opłaty za transakcje międzynarodowe, ustawienie spreadu na 1.5% może pomóc Ci wchłonąć ten koszt i nadal utrzymać pożądaną marżę zysku.

#### 2.1.3 Częstotliwość aktualizacji

-   **Co robi to ustawienie:** To ustawienie określa, jak często moduł *powinien* próbować aktualizować kursy wymiany. Chociaż zadanie cron (patrz Adres URL CRON) faktycznie wyzwala aktualizację, to ustawienie działa jako zabezpieczenie, aby zapobiec zbyt częstym aktualizacjom, które mogą być niepotrzebne lub nawet problematyczne dla niektórych środowisk hostingowych.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy ustawione na „Codziennie”:* Moduł przetworzy aktualizację tylko raz na 24 godziny, nawet jeśli zadanie cron działa częściej.
    *   *Gdy ustawione na „Co godzinę”:* Moduł przetworzy aktualizację raz na godzinę.
    *   *Gdy ustawione na „Co 15 minut”:* Moduł przetworzy aktualizację co 15 minut.
-   **Zalecana wartość:** „Codziennie” jest zazwyczaj wystarczające dla większości sklepów e-commerce, ponieważ oficjalne kursy wymiany zazwyczaj nie wahają się drastycznie w ciągu kilku minut. Jeśli masz bardzo wartościowe przedmioty lub działasz na bardzo niestabilnych rynkach, można rozważyć „Co godzinę”.
-   **Scenariusz/przykład dla sprzedawcy:** Ustawiasz zadanie cron, aby działało co 6 godzin, ale ustawiasz „Częstotliwość aktualizacji” tutaj na „Codziennie”. Moduł wykona faktyczną aktualizację kursu tylko raz w ciągu 24 godzin, mimo że zadanie cron próbuje ją wywołać częściej. Zapobiega to niepotrzebnym wywołaniom API i zużyciu zasobów.

#### 2.1.4 Włącz moduł

-   **Co robi to ustawienie:** Jest to prosty przełącznik włącz/wyłącz dla podstawowej funkcjonalności modułu.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączony (TAK):* Moduł będzie aktywnie pobierał i aktualizował kursy wymiany zgodnie z Twoimi ustawieniami i harmonogramem zadania cron.
    *   *Gdy wyłączony (NIE):* Moduł przestanie pobierać i aktualizować kursy wymiany. Twój sklep będzie nadal używał ostatnio znanych kursów lub domyślnego zachowania PrestaShop dla aktualizacji kursów, jeśli masz inne mechanizmy.
-   **Zalecana wartość:** „TAK”, aby zapewnić automatyczne aktualizacje walut.
-   **Scenariusz/przykład dla sprzedawcy:** Możesz tymczasowo wyłączyć moduł, jeśli musisz przeprowadzić konserwację w swoim sklepie lub jeśli zdecydujesz się ręcznie zarządzać kursami wymiany przez krótki okres. Pamiętaj, aby go ponownie włączyć później.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Adres URL CRON | Skopiuj dokładnie | Adres URL do wyzwalania aktualizacji kursów za pomocą zadania cron serwera. Niezbędny do automatyzacji. |
| Konfiguracja modułu | Spread (%) | 0% - 2% (zależy od biznesu) | Dodaje procentową marżę do pobranych kursów wymiany, aby chronić zyski. |
| Konfiguracja modułu | Częstotliwość aktualizacji | Codziennie | Kontroluje, jak często moduł *faktycznie* przetwarza aktualizację, nawet jeśli cron działa częściej. |
| Konfiguracja modułu | Włącz moduł | TAK | Włącza lub wyłącza funkcjonalność aktualizacji kursów modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy wymiany nie aktualizują się. Co powinienem zrobić?**
O:

1.  **Sprawdź swoje zadanie Cron:** Najczęstszym powodem jest nieprawidłowo skonfigurowane lub brakujące zadanie cron na Twoim serwerze hostingowym. Dokładnie sprawdź, czy skopiowałeś dokładny adres URL CRON ze strony konfiguracji modułu i czy Twoje zadanie cron jest zaplanowane do uruchomienia.
2.  **Moduł włączony?** Upewnij się, że przełącznik „Włącz moduł” na stronie konfiguracji jest ustawiony na „TAK”.
3.  **Częstotliwość aktualizacji:** Sprawdź ustawienie „Częstotliwość aktualizacji”. Jeśli Twoje zadanie cron działa co godzinę, ale częstotliwość jest ustawiona na „Codziennie”, aktualizacja nastąpi tylko raz dziennie.
4.  **Pamięć podręczna PrestaShop:** Czasami wyczyszczenie pamięci podręcznej PrestaShop (w **Zaawansowane > Wydajność**) może pomóc odświeżyć wyświetlane dane, chociaż jest to mniej prawdopodobne, aby wpłynąć na aktualizacje kursów w tle.

**P: Czy mogę ręcznie nadpisać kurs wymiany po jego zaktualizowaniu przez moduł?**
O: Tak, możesz. Moduł aktualizuje kursy w standardowym systemie zarządzania walutami PrestaShop. Jeśli przejdziesz do **Międzynarodowe > Waluty** w swoim Panelu administracyjnym, możesz ręcznie edytować kurs wymiany dla dowolnej waluty. Pamiętaj jednak, że moduł nadpisze Twoje ręczne zmiany przy następnym uruchomieniu zadania cron i wyzwoleniu aktualizacji.

**P: Co się stanie, jeśli usługa Banku Łotwy będzie tymczasowo niedostępna?**
O: Moduł jest zaprojektowany do pobierania kursów z zewnętrznego źródła. Jeśli usługa Banku Łotwy jest niedostępna lub nieosiągalna, moduł prawdopodobnie nie będzie w stanie pobrać nowych kursów. W takich przypadkach Twój sklep będzie nadal używał *ostatnio pomyślnie zaktualizowanych* kursów wymiany. Nie powróci do domyślnych ani nieprawidłowych kursów. Po przywróceniu usługi, następne uruchomienie zadania cron ponownie zaktualizuje kursy.

**P: Czy ten moduł tworzy nowe waluty w moim sklepie?**
O: Nie, ten moduł aktualizuje tylko kursy wymiany dla walut, które *już włączyłeś* w swoim sklepie PrestaShop (w **Międzynarodowe > Waluty**). Musisz najpierw dodać i włączyć pożądane waluty w standardowych ustawieniach PrestaShop, aby ten moduł mógł zarządzać ich kursami.

**P: Mój niestandardowy motyw nie wyświetla poprawnie cen po aktualizacjach.**
O: Ten moduł zmienia tylko podstawowe kursy wymiany. Jeśli ceny są wyświetlane nieprawidłowo, jest bardzo mało prawdopodobne, aby była to bezpośrednia wina modułu.

1.  **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
2.  **Kompatybilność motywu:** Upewnij się, że Twój niestandardowy motyw jest w pełni kompatybilny z Twoją wersją PrestaShop.
3.  **Niestandardowy kod:** Jeśli Twój motyw ma niestandardowy kod do wyświetlania cen, może on nieprawidłowo interpretować zaktualizowane kursy walut PrestaShop. Skonsultuj się z deweloperem motywu lub ekspertem PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Bank Łotwy (Latvijas Banka) – kursy wymiany walut” (`lbrates`) to lekki moduł PrestaShop zaprojektowany przede wszystkim do automatyzacji aktualizacji kursów wymiany walut. Działa w oparciu o prosty wzorzec MVC, gdzie główny plik modułu (`cronjob.php`) pełni rolę głównego kontrolera konfiguracji, a kontroler frontowy (`cronjob.php`) obsługuje rzeczywistą logikę pobierania kursów. Wykorzystuje klasy `Currency` i `Configuration` PrestaShop do zarządzania kursami i ustawieniami. Moduł jest napędzany zewnętrznymi wywołaniami zadań cron, co czyni go asynchronicznym procesem działającym w tle.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `lbrates/controllers/front/cronjob.php`
        -   Nazwa klasy: `LbratesCronjobModuleFrontController`
        -   Klasa nadrzędna: `ModuleFrontController`
        -   Odpowiedzialność: Ten kontroler jest rdzeniem funkcjonalności modułu. Jest zaprojektowany do wywoływania przez zewnętrzne zadanie cron. Po uzyskaniu dostępu pobiera najnowsze referencyjne kursy Euro z oficjalnego API Banku Łotwy, stosuje skonfigurowany spread i aktualizuje kursy wymiany dla wszystkich aktywnych walut w bazie danych PrestaShop. Obsługuje również logowanie i zapobiega zbyt częstym aktualizacjom na podstawie klucza konfiguracji `PS_LBRATES_LAST_UPDATE`.
    -   `lbrates/controllers/front/index.php`
        -   Nazwa klasy: `LbratesIndexModuleFrontController`
        -   Klasa nadrzędna: `ModuleFrontController`
        -   Odpowiedzialność: Jest to standardowy pusty plik `index.php` często dołączany do katalogów kontrolerów frontowych modułów PrestaShop, aby zapobiec listowaniu katalogów. Nie zawiera żadnej logiki funkcjonalnej.
-   **Kontrolery administracyjne Back-Office**:

    -   Brak. Cała administracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   Brak. Moduł bezpośrednio współdziała z podstawowymi klasami `Currency` i `Configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Brak. Moduł nie używa żadnego niestandardowego kodu JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Brak. Moduł nie używa żadnego niestandardowego kodu CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `lbrates/views/admin.tpl`
        -   Ten szablon jest renderowany przez metodę `getContent()` w głównym pliku modułu `cronjob.php`. Wyświetla formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Obejmuje to pola dla adresu URL CRON, spreadu, częstotliwości aktualizacji oraz przełącznika Włącz/Wyłącz. Wykorzystuje standardowe pomocniki formularzy i stylizację PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`:
        -   `PS_LBRATES_SPREAD`: Przechowuje skonfigurowany procent spreadu.
        -   `PS_LBRATES_UPDATE_FREQUENCY`: Przechowuje skonfigurowaną częstotliwość aktualizacji (np. codziennie, co godzinę).
        -   `PS_LBRATES_LAST_UPDATE`: Przechowuje znacznik czasu ostatniej udanej aktualizacji, aby zapobiec zbyt częstym wywołaniom.
        -   `PS_LBRATES_ENABLED`: Przechowuje status włączenia/wyłączenia modułu.
    -   Aktualizuje kolumnę `exchange_rate` w tabeli `ps_currency` dla aktywnych walut.
-   **Tabela zarejestrowanych hooków**:

    -   Moduł nie rejestruje żadnych tradycyjnych hooków wyświetlania (`displayHeader`, `displayFooter` itp.) we front office. Jego główną funkcją jest przetwarzanie w tle.
    -   Implicitnie używa hooka `actionUpdateCurrency` (lub podobnych wewnętrznych mechanizmów) poprzez bezpośrednią modyfikację kursów wymiany walut, ale nie rejestruje się w nim jawnie.
    -   Metoda `install()` modułu zarejestrowałaby sam moduł w systemie modułów PrestaShop, udostępniając jego konfigurację.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Bank Łotwy (Latvijas Banka) – kursy wymiany walut”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań związanych z funkcjonalnością i integracją modułu.
"""
