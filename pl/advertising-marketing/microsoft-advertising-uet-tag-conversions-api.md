---
title: "Microsoft Advertising UET Tag & Conversions API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Microsoft Advertising UET Tag & Conversions API od MyPresta.eu."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Microsoft Advertising UET Tag & Conversions API na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


# Microsoft Advertising UET Tag & Conversions API

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL, są wymagane do prawidłowego działania modułu, zwłaszcza w przypadku funkcji Conversions API. Są one zazwyczaj domyślnie włączone w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To główne centrum do ustawiania śledzenia Microsoft Advertising. Znajdziesz tu serię zakładek i ustawień zaprojektowanych, aby poprowadzić Cię przez ten proces.

#### Główna zakładka konfiguracji (Widok początkowy)

-   **Co robi to ustawienie:** Ta zakładka zazwyczaj zawiera przegląd i początkowe opcje konfiguracji, często w tym kreator, aby uprościć pierwszą konfigurację.
-   **Efekt zmiany tego ustawienia:** Ukończenie kreatora lub wypełnienie początkowych danych włączy podstawową funkcjonalność śledzenia i przygotuje moduł do bardziej zaawansowanych ustawień.
-   **Zalecana wartość:** Postępuj zgodnie z instrukcjami kreatora.
-   **Scenariusz / przykład dla sprzedawcy:** Po pierwszej instalacji modułu kreator poprosi o Twój UET Tag ID i poprowadzi Cię przez wybór metody śledzenia (UET Tag, Conversions API lub obie).

#### UET Tag ID

-   **Co robi to ustawienie:** To Twój unikalny identyfikator dostarczony przez Microsoft Advertising. Informuje Microsoft, z którym kontem powiązać dane śledzenia.
-   **Efekt zmiany tego ustawienia:**
    -   *Po poprawnym wprowadzeniu:* Moduł osadzi UET Tag w Twoim sklepie, umożliwiając Microsoft Advertising śledzenie zachowań użytkowników.
    -   *Po pozostawieniu pustym lub niepoprawnym:* Nie będzie śledzenia UET Tag, a Twoje kampanie Microsoft Advertising nie otrzymają danych konwersji z front-office.
-   **Zalecana wartość:** Twój dokładny UET Tag ID z konta Microsoft Advertising.
-   **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś konto Microsoft Advertising i skonfigurowałeś UET Tag. Kopiujesz ID (np. `12345678`) i wklejasz je tutaj.

#### Tryb śledzenia (UET Tag, Conversions API lub oba)

-   **Co robi to ustawienie:** Określa, w jaki sposób dane konwersji są wysyłane do Microsoft Advertising.
    -   **Tylko UET Tag:** Tradycyjne śledzenie po stronie klienta za pomocą JavaScript w przeglądarce klienta.
    -   **Tylko Conversions API:** Śledzenie po stronie serwera, wysyłanie danych bezpośrednio z Twojego serwera PrestaShop do Microsoftu. Bardziej odporne na ustawienia prywatności przeglądarki.
    -   **Oba (Hybrydowy):** Wykorzystuje zarówno UET Tag, jak i Conversions API, z mechanizmem deduplikacji zdarzeń, zapewniając dokładne liczenie, nawet jeśli obie metody zgłaszają tę samą konwersję.
-   **Efekt zmiany tego ustawienia:**
    -   *Tylko UET Tag:* Opiera się wyłącznie na śledzeniu opartym na przeglądarce, na które mogą wpływać blokery reklam lub ustawienia prywatności.
    -   *Tylko Conversions API:* Zapewnia bardziej niezawodne śledzenie, ale wymaga konfiguracji po stronie serwera i może nie przechwytywać wszystkich zdarzeń po stronie klienta (takich jak wyświetlenia stron) tak łatwo.
    -   *Oba (Hybrydowy):* Oferuje najbardziej kompleksowe i niezawodne śledzenie, łącząc mocne strony obu metod, jednocześnie zapobiegając duplikowaniu konwersji.
-   **Zalecana wartość:** **Oba (Hybrydowy)** jest ogólnie zalecane dla maksymalnej dokładności i odporności.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz uzyskać jak najdokładniejsze dane, więc wybierasz „Oba (Hybrydowy)”, aby zapewnić śledzenie konwersji, nawet jeśli klient używa blokera reklam.

#### Token dostępu do Conversions API

-   **Co robi to ustawienie:** To bezpieczny token wygenerowany na Twoim koncie Microsoft Advertising, autoryzujący Twój sklep PrestaShop do wysyłania danych bezpośrednio do serwerów Microsoftu za pośrednictwem Conversions API.
-   **Efekt zmiany tego ustawienia:**
    -   *Po poprawnym wprowadzeniu:* Włącza śledzenie po stronie serwera dla Conversions API.
    -   *Po pozostawieniu pustym lub niepoprawnym:* Conversions API nie będzie działać, a dane konwersji po stronie serwera nie zostaną wysłane.
-   **Zalecana wartość:** Twój dokładny Token dostępu do Conversions API z konta Microsoft Advertising.
-   **Scenariusz / przykład dla sprzedawcy:** Wygenerowałeś Token dostępu na swoim koncie Microsoft Advertising (np. w sekcji „Narzędzia” > „Śledzenie konwersji” > „Conversions API”). Wklejasz ten długi ciąg znaków tutaj.

#### Włącz rozszerzone konwersje

-   **Co robi to ustawienie:** Po włączeniu ta funkcja wysyła zaszyfrowane dane klienta (takie jak adresy e-mail) wraz ze zdarzeniami konwersji. Pomaga to Microsoftowi dokładniej dopasowywać konwersje, zwłaszcza gdy pliki cookie są ograniczone, poprawiając wydajność Twojej kampanii.
-   **Efekt zmiany tego ustawienia:**
    -   *Po włączeniu:* Dokładniejsze dopasowywanie konwersji, potencjalnie prowadzące do lepszej optymalizacji kampanii reklamowych.
    -   *Po wyłączeniu:* Konwersje opierają się wyłącznie na standardowych metodach śledzenia, które mogą być mniej dokładne w niektórych środowiskach przeglądarek skoncentrowanych na prywatności.
-   **Zalecana wartość:** **TAK** (Włączone), ponieważ znacznie poprawia dopasowywanie danych.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz dostarczyć Microsoft Advertising najlepsze możliwe dane do optymalizacji swoich kampanii, więc włączasz Rozszerzone konwersje.

#### Integracja z zarządzaniem zgodą

-   **Co robi to ustawienie:** Ten moduł może integrować się z istniejącymi modułami zgody na pliki cookie (takimi jak moduły RODO), aby zapewnić, że UET Tag uruchamia się tylko po wyrażeniu zgody przez klienta.
-   **Efekt zmiany tego ustawienia:**
    -   *Po włączeniu i zintegrowaniu:* UET Tag będzie szanować wybory zgody klienta. Jeśli klient odrzuci pliki cookie śledzące, UET Tag nie zostanie załadowany.
    -   *Po wyłączeniu lub braku integracji:* UET Tag może zostać załadowany niezależnie od zgody, potencjalnie prowadząc do problemów z zgodnością.
-   **Zalecana wartość:** **TAK** (Włączone), jeśli używasz modułu zgody na pliki cookie i musisz przestrzegać przepisów dotyczących prywatności (np. RODO, CCPA).
-   **Scenariusz / przykład dla sprzedawcy:** Twój sklep używa modułu RODO. Włączasz to ustawienie, aby upewnić się, że Twoje śledzenie Microsoft Advertising jest zgodne z przepisami dotyczącymi prywatności.

#### Tryb debugowania

-   **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla szczegółowe informacje o UET Tag i zdarzeniach Conversions API bezpośrednio na stronach front-office (widoczne tylko dla Ciebie, administratora lub określonych adresów IP). Jest to nieocenione do weryfikacji prawidłowej konfiguracji śledzenia.
-   **Efekt zmiany tego ustawienia:**
    -   *Po włączeniu:* Zobaczysz nakładkę debugowania lub komunikaty konsoli na front-office Twojego sklepu, pokazujące, które zdarzenia są śledzone i jakie dane są wysyłane.
    -   *Po wyłączeniu:* Moduł działa cicho, bez widocznych informacji debugowania.
-   **Zalecana wartość:** **NIE** (Wyłączone) dla działających sklepów produkcyjnych. **TAK** (Włączone) tymczasowo podczas konfiguracji i rozwiązywania problemów.
-   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz potwierdzić, że zdarzenia „Dodaj do koszyka” są wysyłane poprawnie. Włączasz Tryb debugowania, dodajesz produkt do koszyka i sprawdzasz dane wyjściowe debugowania.

#### Mapowanie zdarzeń (Zaawansowane)

-   **Co robi to ustawienie:** Pozwala dostosować sposób mapowania konkretnych działań PrestaShop (np. „Produkt dodany do koszyka”) na nazwy zdarzeń Microsoft Advertising (np. „add\_to\_cart”). Możesz również zdefiniować niestandardowe parametry do wysyłania z każdym zdarzeniem.
-   **Efekt zmiany tego ustawienia:**
    -   *Po skonfigurowaniu:* Zapewnia, że Twoje zdarzenia są poprawnie kategoryzowane i wzbogacone o odpowiednie dane w Microsoft Advertising.
    -   *Po błędnej konfiguracji:* Zdarzenia mogą nie być śledzone, lub wysyłane dane mogą być niedokładne, co prowadzi do słabej optymalizacji kampanii.
-   **Zalecana wartość:** Użyj domyślnych mapowań, chyba że masz konkretny powód, aby je zmienić na podstawie konfiguracji Microsoft Advertising.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz wysłać markę produktu jako niestandardowy parametr z każdym zdarzeniem „view\_item”. Skonfigurowałbyś to mapowanie tutaj.

#### Domeny łączące (Zaawansowane)

-   **Co robi to ustawienie:** Jeśli masz wiele subdomen lub powiązanych stron internetowych, które współdzielą ten sam UET Tag, to ustawienie pomaga zapewnić prawidłowe łączenie sesji użytkowników między tymi domenami.
-   **Efekt zmiany tego ustawienia:**
    -   *Po skonfigurowaniu:* Umożliwia płynne śledzenie podróży użytkowników przez wiele domen pod Twoją kontrolą.
    -   *Po braku konfiguracji (i potrzebie):* Sesje użytkowników mogą zostać przerwane, co prowadzi do niedokładnej atrybucji konwersji.
-   **Zalecana wartość:** Pozostaw puste, chyba że prowadzisz wiele subdomen lub powiązanych witryn, które wymagają śledzenia między domenami.
-   **Scenariusz / przykład dla sprzedawcy:** Masz swój główny sklep pod adresem `shop.example.com` i blog pod adresem `blog.example.com`, oba używające tego samego UET Tag. Dodałbyś `blog.example.com` do listy domen łączących.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | UET Tag ID | Twój Tag ID | Włącza śledzenie UET Tag. Niezbędne dla danych po stronie klienta. |
| Główna konfiguracja | Tryb śledzenia | Oba (Hybrydowy) | Wybiera UET Tag, Conversions API lub oba do przesyłania danych. Hybrydowy jest najbardziej niezawodny. |
| Główna konfiguracja | Token dostępu do Conversions API | Twój Token dostępu | Autoryzuje wysyłanie danych po stronie serwera do Microsoftu. |
| Główna konfiguracja | Włącz rozszerzone konwersje | TAK | Poprawia dokładność dopasowywania konwersji poprzez wysyłanie zaszyfrowanych danych klienta. |
| Główna konfiguracja | Integracja z zarządzaniem zgodą | TAK (jeśli dotyczy) | Zapewnia, że UET Tag szanuje wybory prywatności klienta (RODO, CCPA). |
| Główna konfiguracja | Tryb debugowania | NIE (TAK do testowania) | Wyświetla dane śledzenia na front-office do weryfikacji. |
| Główna konfiguracja | Mapowanie zdarzeń | Domyślne | Dostosowuje sposób mapowania działań PrestaShop na zdarzenia Microsoftu. |
| Główna konfiguracja | Domeny łączące | Puste (jeśli niepotrzebne) | Włącza śledzenie między domenami dla powiązanych stron internetowych. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminMybingAjaxController (Panel administracyjny > Moduły > Microsoft Advertising UET Tag & Conversions API > Statystyki na żywo / Wynik zdrowia / Doktor / Jakość danych)

Ten kontroler zasila dynamiczne, interaktywne sekcje konfiguracji modułu, dostarczając w czasie rzeczywistym wglądu i narzędzi diagnostycznych. Nie będziesz nawigować do oddzielnego elementu menu, ale raczej wchodzić w interakcje z konkretnymi zakładkami w ramach głównej konfiguracji modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Są to zazwyczaj podzakładki w ramach głównej strony konfiguracji modułu (np. „Statystyki na żywo”, „Wynik zdrowia”, „Trener jakości danych”, „Doktor katalogu”).
-   **Dostępne działania i ustawienia:**
    -   **Statystyki na żywo:** Wyświetla ostatnie zdarzenia wysłane do Microsoft Advertising, pokazując wyświetlenia stron, dodania do koszyka, zakupy itp., niemal w czasie rzeczywistym. Pomaga to potwierdzić, że zdarzenia są prawidłowo uruchamiane.
    -   **Wynik zdrowia:** Analizuje konfigurację śledzenia i dostarcza wynik oparty na najlepszych praktykach, wskazując potencjalne problemy lub obszary do poprawy.
    -   **Trener jakości danych:** Oferuje konkretne rekomendacje, aby poprawić jakość i kompletność danych wysyłanych do Microsoftu, zwłaszcza w przypadku rozszerzonych konwersji.
    -   **Doktor katalogu:** Pomaga diagnozować problemy z danymi produktów, które mogą wpływać na reklamę w kanałach produktów lub dynamiczny remarketing.
-   **Efekt zmian:** Interakcja z tymi ekranami przede wszystkim dostarcza informacji i diagnostycznych informacji zwrotnych. Nie ma tu bezpośrednich „ustawień” do zmiany, ale uzyskane spostrzeżenia będą informować o korektach, które możesz wprowadzić w głównej konfiguracji lub katalogu produktów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Regularnie sprawdzaj **Statystyki na żywo** po wprowadzeniu zmian lub uruchomieniu nowych kampanii, aby upewnić się, że zdarzenia są śledzone.
    -   Okresowo przeglądaj **Wynik zdrowia** i **Trener jakości danych** w poszukiwaniu rekomendacji dotyczących optymalizacji konfiguracji śledzenia.
    -   Jeśli napotkasz problemy z reklamami związanymi z produktami, skonsultuj się z **Doktorem katalogu**.

#### 2.2.2 index.php (Panel administracyjny > Moduły > Microsoft Advertising UET Tag & Conversions API)

Odwołuje się to do głównego punktu wejścia do interfejsu administracyjnego modułu, czyli samej strony konfiguracji. Wszystkie ustawienia opisane w sekcji 4.1 są zarządzane za pośrednictwem tego głównego widoku. Nie ma oddzielnego ekranu „index.php”, do którego można by nawigować poza początkową konfiguracją modułu.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje konwersje nie pojawiają się w Microsoft Advertising. Co powinienem zrobić?**
O:

1.  **Sprawdź UET Tag ID i Token dostępu:** Dokładnie sprawdź, czy Twój UET Tag ID i Token dostępu do Conversions API są poprawnie wprowadzone w konfiguracji modułu. Nawet pojedyncza literówka może uniemożliwić śledzenie.
2.  **Zweryfikuj tryb śledzenia:** Upewnij się, że Twój „Tryb śledzenia” jest ustawiony na „Oba (Hybrydowy)” dla maksymalnej niezawodności.
3.  **Włącz tryb debugowania:** Aktywuj „Tryb debugowania” w ustawieniach modułu i wykonaj testowy zakup w swoim sklepie. Szukaj nakładki debugowania lub komunikatów konsoli, aby sprawdzić, czy zdarzenia są uruchamiane.
4.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty oraz wszelkie inne pamięci podręczne. Czasami stare ustawienia mogą się utrzymywać.
5.  **Sprawdź konto Microsoft Advertising:** Zaloguj się do swojego konta Microsoft Advertising i sprawdź status UET Tag oraz konfigurację celu konwersji. Upewnij się, że Twoje cele konwersji są poprawnie skonfigurowane, aby pasowały do zdarzeń wysyłanych przez moduł (np. „Zakup”).

**P: Moduł mówi, że „Integracja z zarządzaniem zgodą” jest włączona, ale nie mam modułu RODO. Czy to problem?**
O: Jeśli nie masz zainstalowanego i skonfigurowanego dedykowanego modułu zgody na pliki cookie, to ustawienie nie będzie miało żadnego praktycznego efektu. Moduł domyślnie założy zgodę. Jednak dla zgodności prawnej (np. RODO, CCPA) zdecydowanie zaleca się użycie odpowiedniego modułu zgody na pliki cookie. Jeśli zainstalujesz go później, ten moduł automatycznie się z nim zintegruje.

**P: Mój niestandardowy motyw wygląda trochę dziwnie po zainstalowaniu modułu, albo widzę pustą stronę.**
O: Ten moduł działa głównie w tle i nie powinien wpływać na wygląd wizualny Twojego motywu.

1.  **Wyczyść pamięć podręczną:** Najczęstszym rozwiązaniem problemów z wyświetlaniem po instalacji modułu jest wyczyszczenie pamięci podręcznej PrestaShop (**Zaawansowane > Wydajność**).
2.  **Sprawdź konflikty:** Jeśli problem nadal występuje, tymczasowo wyłącz inne ostatnio zainstalowane moduły, aby sprawdzić, czy nie ma konfliktów.
3.  **Błędy PHP:** Jeśli widzisz pustą stronę, włącz raportowanie błędów PHP na swoim serwerze (lub sprawdź logi błędów serwera), aby zidentyfikować wszelkie krytyczne błędy.
    Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu i wszelkie komunikaty o błędach.

**P: Jak przetłumaczyć teksty modułu na inne języki?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów” jako typ tłumaczenia.
3.  Wybierz swój motyw, język, na który chcesz przetłumaczyć, a następnie wybierz „Microsoft Advertising UET Tag & Conversions API” z listy modułów.
4.  Możesz wtedy przetłumaczyć wszystkie widoczne ciągi znaków używane przez moduł.

**P: Dlaczego „Trener jakości danych” lub „Wynik zdrowia” wyświetla ostrzeżenia?**
O: Te narzędzia zostały zaprojektowane, aby pomóc Ci zoptymalizować śledzenie. Ostrzeżenia często wskazują na:

-   **Brakujące dane rozszerzonych konwersji:** Upewnij się, że dane klienta (takie jak e-mail) są dostępne i wysyłane.
-   **Problemy z danymi produktów:** Twój katalog produktów może mieć brakujące numery GTIN, MPN lub inne identyfikatory kluczowe dla reklamy w kanałach produktów.
-   **Niska liczba zdarzeń:** Jeśli Twój sklep ma bardzo mały ruch, narzędzia mogą nie mieć wystarczającej ilości danych, aby zapewnić kompleksową analizę.
    Zastosuj się do konkretnych zaleceń dostarczonych przez narzędzia, aby poprawić jakość danych i stan śledzenia.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Microsoft Advertising UET Tag & Conversions API` (`mybing`) jest zbudowany zgodnie ze wzorcem MVC (Model-View-Controller) PrestaShop, z silnym naciskiem na modułowość i rozszerzalność. Wykorzystuje wzorzec fabryki do tworzenia instancji trackera (`MybingTrackerFactory`) w celu obsługi różnych trybów śledzenia (UET, CAPI, Hybrydowy) i wykorzystuje solidny system zdarzeń (`MybingEvents`) do przechwytywania różnych działań e-commerce. Jakość danych i diagnostyka są obsługiwane przez dedykowane klasy (`MybingHealthScore`, `MybingDataQualityCoach`, `MybingCatalogDoctor`). Moduł integruje się z systemem hooków PrestaShop do wstrzykiwania zdarzeń do front-office i używa dedykowanych kontrolerów administracyjnych do zaawansowanej konfiguracji i narzędzi diagnostycznych.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `mybing/controllers/front/ajax.php`
    -   **Nazwa klasy:** `MybingAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje żądania AJAX z front-office, głównie do wysyłania zdarzeń po stronie klienta lub danych, które nie mogą być bezpośrednio obsługiwane przez tag UET (np. do integracji zarządzania zgodą lub specyficznego zbierania danych przed przekierowaniem strony). Może być również używany do wysyłania zdarzeń CAPI, które są wyzwalane po stronie klienta, ale wymagają przetwarzania po stronie serwera.
-   `mybing/controllers/front/cron.php`
    -   **Nazwa klasy:** `MybingCronModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Zapewnia punkt końcowy dla zadania cron. Jest to zazwyczaj używane do zadań po stronie serwera, które muszą być uruchamiane okresowo, takich jak wysyłanie odroczonych zdarzeń Conversions API, synchronizacja danych lub wykonywanie zadań konserwacyjnych związanych z funkcjonalnością modułu.
-   `mybing/controllers/front/index.php`
    -   **Nazwa klasy:** `MybingIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ogólny kontroler front-office, często używany jako rezerwowy lub do prostych, nie-AJAXowych interakcji z front-office. W tym module może być używany do konkretnych przekierowań lub do obsługi początkowych żądań związanych z konfiguracją śledzenia.

#### Kontrolery administracyjne Back-Office

-   `mybing/controllers/admin/AdminMybingAjaxController.php`
    -   **Nazwa klasy:** `AdminMybingAjaxController` (rozszerza `AdminController`)
    -   **Nazwa zakładki:** Nie jest to samodzielna zakładka, ale punkt końcowy AJAX dla głównej konfiguracji modułu.
    -   **Zarządzana jednostka:** Obsługuje dynamiczne ładowanie i przetwarzanie danych dla zakładek diagnostycznych i statystycznych modułu (Statystyki na żywo, Wynik zdrowia, Trener jakości danych, Doktor katalogu). Przetwarza żądania dotyczące logów zdarzeń, kontroli stanu i raportów jakości danych, zwracając odpowiedzi JSON do JavaScriptu administratora.
-   `mybing/controllers/admin/index.php`
    -   **Nazwa klasy:** `AdminMybingIndexController` (rozszerza `AdminController`)
    -   **Nazwa zakładki:** Nie jest to samodzielna zakładka. Jest to symbol zastępczy lub ogólny kontroler administracyjny, który może być używany do konkretnych wewnętrznych przekierowań lub działań w interfejsie administracyjnym modułu, ale główna konfiguracja jest obsługiwana przez metodę `getContent()` głównej klasy modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

-   `mybing/classes/autoload.php`: Standardowy plik autoload PrestaShop, zapewniający prawidłowe ładowanie klas modułu.
-   `mybing/classes/index.php`: Plik zastępczy, często zapobiegający listowaniu katalogów.
-   `mybing/classes/MybingCapiClient.php`: Obsługuje komunikację z punktem końcowym Microsoft Advertising Conversions API. Hermetyzuje żądania HTTP, uwierzytelnianie (Token dostępu) i formatowanie danych do przesyłania zdarzeń po stronie serwera.
-   `mybing/classes/MybingCapiTracker.php`: Implementuje `MybingTrackerInterface` dla śledzenia po stronie serwera (Conversions API). Odpowiedzialny za zbieranie danych zdarzeń, przygotowywanie ich dla klienta CAPI i wysyłanie.
-   `mybing/classes/MybingCatalogDoctor.php`: Dostarcza logikę diagnostyczną do analizy jakości danych produktów, identyfikując problemy, które mogą wpływać na kanały produktów lub dynamiczny remarketing w Microsoft Advertising.
-   `mybing/classes/MybingConsent.php`: Zarządza integracją z modułami zgody na pliki cookie. Określa, czy użytkownik wyraził zgodę na śledzenie i odpowiednio kontroluje uruchamianie tagu UET.
-   `mybing/classes/MybingCurrencyHelper.php`: Klasa narzędziowa do obsługi konwersji i formatowania walut, zapewniająca prawidłowe wysyłanie wartości zdarzeń do Microsoft Advertising.
-   `mybing/classes/MybingDataQualityCoach.php`: Analizuje jakość i kompletność danych wysyłanych dla zdarzeń, zwłaszcza dla rozszerzonych konwersji, i dostarcza rekomendacje dotyczące poprawy.
-   `mybing/classes/MybingEventId.php`: Generuje i zarządza unikalnymi identyfikatorami zdarzeń do deduplikacji, kluczowymi dla śledzenia hybrydowego (UET + CAPI).
-   `mybing/classes/MybingEventMap.php`: Definiuje mapowanie między działaniami PrestaShop (np. `actionCartSave`) a nazwami zdarzeń Microsoft Advertising (np. `add_to_cart`), w tym niestandardowe parametry.
-   `mybing/classes/MybingEvents.php`: Centralna klasa do definiowania i wyzwalania wszystkich śledzonych zdarzeń e-commerce (np. `PageView`, `AddToCart`, `Purchase`). Działa jako dyspozytor zdarzeń w module.
-   `mybing/classes/MybingHealthScore.php`: Oblicza „wynik zdrowia” dla ogólnej konfiguracji śledzenia, oceniając konfigurację, jakość danych i uruchamianie zdarzeń.
-   `mybing/classes/MybingHybridTracker.php`: Implementuje `MybingTrackerInterface` dla śledzenia hybrydowego. Koordynuje śledzenie zarówno UET Tag, jak i Conversions API, zapewniając deduplikację zdarzeń za pomocą `event_id`.
-   `mybing/classes/MybingLiveStats.php`: Zbieranie i dostarczanie statystyk w czasie rzeczywistym na temat śledzonych zdarzeń, wyświetlanych w interfejsie administracyjnym.
-   `mybing/classes/MybingProductIdResolver.php`: Pomaga rozwiązywać i formatować identyfikatory produktów zgodnie z wymaganiami Microsoft Advertising (np. GTIN, MPN, custom\_label).
-   `mybing/classes/MybingPropertyRules.php`: Definiuje reguły i logikę do wyodrębniania i formatowania różnych właściwości zdarzeń (np. cena produktu, ilość, kategoria) dla Microsoft Advertising.
-   `mybing/classes/MybingTrackerFactory.php`: Klasa fabryczna odpowiedzialna za tworzenie odpowiedniej instancji trackera (`MybingUetTracker`, `MybingCapiTracker` lub `MybingHybridTracker`) na podstawie konfiguracji modułu.
-   `mybing/classes/MybingTrackerInterface.php`: Definiuje kontrakt dla wszystkich klas trackera, zapewniając spójny interfejs dla metod śledzenia zdarzeń.
-   `mybing/classes/MybingUetTracker.php`: Implementuje `MybingTrackerInterface` dla śledzenia po stronie klienta (UET Tag). Odpowiedzialny za generowanie kodu JavaScript do wstrzyknięcia do front-office.
-   `mybing/classes/MybingUserData.php`: Zbieranie i formatowanie danych specyficznych dla użytkownika (np. e-mail, telefon, adres) dla rozszerzonych konwersji, w tym haszowanie.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `mybing/views/js/mybing-admin.js`: JavaScript dla back-office do ogólnej funkcjonalności administracyjnej, interakcji z formularzami i dynamicznych aktualizacji na stronie konfiguracji modułu.
-   `mybing/views/js/mybing-debug.js`: JavaScript dla front-office specjalnie dla trybu debugowania, wyświetlający informacje o śledzeniu i ładunki zdarzeń administratorowi.
-   `mybing/views/js/mybing-ghost.js`: JavaScript dla front-office, potencjalnie do obsługi zdarzeń „duchów” lub specyficznych interakcji po stronie klienta, które muszą być śledzone bez bezpośredniej akcji użytkownika.
-   `mybing/views/js/mybing-live.js`: JavaScript dla back-office dla zakładki „Statystyki na żywo”, obsługujący żądania AJAX do `AdminMybingAjaxController` i aktualizujący strumień zdarzeń na żywo.
-   `mybing/views/js/mybing-tcf.js`: JavaScript dla front-office do integracji z Transparency and Consent Framework (TCF) lub innymi platformami zarządzania zgodą, zapewniający, że UET Tag uruchamia się tylko za zgodą.
-   `mybing/views/js/mybing-wizard.js`: JavaScript dla back-office dla kreatora początkowej konfiguracji, prowadzący sprzedawcę przez kroki konfiguracji.
-   `mybing/views/js/mybing.js`: Główny plik JavaScript dla front-office. Zawiera podstawową logikę do inicjalizacji UET Tag, przechwytywania zdarzeń po stronie klienta (np. `add_to_cart`) i wysyłania danych do UET Tag lub kontrolera AJAX modułu do przetwarzania CAPI. Wiąże się z różnymi zdarzeniami DOM i zdarzeniami `prestashop.on` PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `mybing/views/css/mybing-admin.css`: CSS dla back-office do stylizacji strony konfiguracji modułu, narzędzi diagnostycznych i kreatora, zapewniając spójny i przyjazny dla użytkownika interfejs administracyjny.
-   `mybing/views/css/mybing-debug.css`: CSS dla front-office do stylizacji nakładki debugowania, dzięki czemu informacje o śledzeniu są wyraźnie widoczne dla administratora bez zakłócania projektu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `mybing/views/templates/hook/capi-pageview.tpl`: Renderuje ukryty element lub skrypt do wyzwalania zdarzenia PageView po stronie serwera za pośrednictwem CAPI, często używany, gdy tag UET może być zablokowany.
-   `mybing/views/templates/hook/debug.tpl`: Renderuje strukturę HTML dla nakładki debugowania front-office, wyświetlając dane zdarzeń.
-   `mybing/views/templates/hook/displayOrderConfirmation.tpl`: Wstrzykiwany do hooka `displayOrderConfirmation`. Renderuje skrypt zdarzenia zakupu UET Tag i/lub wyzwala zdarzenie zakupu CAPI po pomyślnym zamówieniu.
-   `mybing/views/templates/hook/ghost.tpl`: Renderuje ukryty skrypt lub element do śledzenia „duchów”, potencjalnie dla specyficznych zdarzeń w tle lub zbierania danych.
-   `mybing/views/templates/hook/header.tpl`: Wstrzykiwany do hooka `displayHeader`. Renderuje główny skrypt bazowy UET Tag, integrację zarządzania zgodą i początkowe zdarzenia PageView.
-   `mybing/views/templates/hook/payment.tpl`: Potencjalnie używany do śledzenia zdarzeń związanych z wyborem lub inicjacją metody płatności, chociaż `displayOrderConfirmation` jest bardziej powszechne dla ostatecznego zakupu.
-   `mybing/views/templates/hook/product-details.tpl`: Wstrzykiwany do hooka strony produktu (np. `displayProductButtons` lub `displayProductExtraContent`). Renderuje skrypty dla zdarzeń `view_item` i słuchaczy zdarzeń `add_to_cart`.

#### Szablony administracyjne (`views/templates/admin/`)

-   `mybing/views/templates/admin/consent-guide.tpl`: Wyświetla wskazówki i informacje dotyczące integracji zarządzania zgodą.
-   `mybing/views/templates/admin/doctor.tpl`: Renderuje interfejs dla narzędzia diagnostycznego „Doktor katalogu”.
-   `mybing/views/templates/admin/dq.tpl`: Renderuje interfejs dla rekomendacji „Trenera jakości danych”.
-   `mybing/views/templates/admin/health.tpl`: Renderuje interfejs dla przeglądu „Wyniku zdrowia”.
-   `mybing/views/templates/admin/linker-domains.tpl`: Renderuje pole wprowadzania i wyjaśnienie dotyczące konfiguracji domen łączących.
-   `mybing/views/templates/admin/live-maintain.tpl`: Renderuje komunikat o konserwacji lub status funkcji statystyk na żywo.
-   `mybing/views/templates/admin/live.tpl`: Renderuje interfejs dla „Statystyk na żywo”, wyświetlając ostatnie zdarzenia.
-   `mybing/views/templates/admin/mode-context.tpl`: Dostarcza kontekstowe informacje o wybranym trybie śledzenia.
-   `mybing/views/templates/admin/mode-note-both.tpl`: Wyświetla konkretną notatkę lub wyjaśnienie, gdy wybrany jest tryb „Oba (Hybrydowy)”.
-   `mybing/views/templates/admin/mode-note-capi.tpl`: Wyświetla konkretną notatkę lub wyjaśnienie, gdy wybrany jest tryb „Tylko Conversions API”.
-   `mybing/views/templates/admin/mode-note-uet.tpl`: Wyświetla konkretną notatkę lub wyjaśnienie, gdy wybrany jest tryb „Tylko UET Tag”.
-   `mybing/views/templates/admin/mode-picker.tpl`: Renderuje przyciski radiowe lub listę rozwijaną do wyboru trybu śledzenia.
-   `mybing/views/templates/admin/properties-list.tpl`: Renderuje listę lub tabelę właściwości zdarzeń i ich wartości do konfiguracji lub wyświetlania.
-   `mybing/views/templates/admin/recent-events.tpl`: Renderuje tabelę lub listę ostatnio śledzonych zdarzeń, często będącą częścią „Statystyk na żywo”.
-   `mybing/views/templates/admin/tabs.tpl`: Renderuje strukturę nawigacji po zakładkach dla strony konfiguracji modułu (np. Ogólne, Statystyki na żywo, Wynik zdrowia).
-   `mybing/views/templates/admin/tag-chips.tpl`: Renderuje wizualne „chipy” lub wskaźniki dla skonfigurowanych identyfikatorów UET Tag.
-   `mybing/views/templates/admin/tag-ids.tpl`: Renderuje pole wprowadzania dla identyfikatorów UET Tag.
-   `mybing/views/templates/admin/wizard.tpl`: Renderuje interfejs krok po kroku dla kreatora początkowej konfiguracji.

#### Szablony front-office (`views/templates/front/`)

-   Brak zidentyfikowanych dedykowanych szablonów stron. Renderowanie front-office jest głównie obsługiwane za pośrednictwem szablonów hooków.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł nie tworzy jawnie niestandardowych tabel SQL na podstawie dostarczonego spisu. Rekordy konfiguracji są przechowywane w tabeli `ps_configuration` PrestaShop, używając kluczy z prefiksem `MYBING_` (np. `MYBING_UET_ID`, `MYBING_CAPI_TOKEN`, `MYBING_TRACKING_MODE`).

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje podstawowy JavaScript UET Tag, inicjalizuje zarządzanie zgodą i wyzwala zdarzenia `PageView`. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po pomyślnym zakupie. | Wyzwala zdarzenia `Purchase` zarówno dla UET Tag, jak i Conversions API, w tym szczegóły zamówienia. |
| `actionFrontControllerSetMedia` | Gdy kontroler front-office ustawia swoje zasoby multimedialne. | Wstrzykuje JavaScript i CSS specyficzne dla modułu do front-office. |
| `actionCartSave` | Gdy produkt jest dodawany lub usuwany z koszyka. | Wyzwala zdarzenia `AddToCart` lub `RemoveFromCart`. |
| `actionProductAdd` | Gdy produkt jest dodawany do koszyka (specyficzne dla niektórych motywów/modułów). | Alternatywny lub uzupełniający hook dla zdarzeń `AddToCart`. |
| `actionProductUpdate` | Gdy produkt jest aktualizowany w Panelu administracyjnym. | Potencjalnie używany przez `Catalog Doctor` do ponownej oceny jakości danych produktów. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu `ObjectModel` produktu. | Podobnie jak `actionProductUpdate`, do sprawdzania jakości danych lub unieważniania pamięci podręcznej. |
| `actionObjectOrderAddAfter` | Po dodaniu `ObjectModel` zamówienia. | Wyzwala zdarzenia `Purchase` po stronie serwera za pośrednictwem Conversions API, zapewniając niezawodne śledzenie. |
| `actionObjectOrderUpdateAfter` | Po zaktualizowaniu `ObjectModel` zamówienia. | Potencjalnie do śledzenia zmian statusu zamówienia (np. zwrot, anulowanie), jeśli skonfigurowano w Microsoft Ads. |
| `displayProductExtraContent` | Na stronie produktu, często poniżej głównej treści. | Może być używany do wstrzykiwania skryptów śledzących specyficznych dla produktu lub danych dla zdarzeń `ViewItem`. |
| `displayFooter` | Na końcu sekcji `<body>` na każdej stronie front-office. | Może być używany do odroczonego ładowania skryptów lub dodatkowych elementów śledzących. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Wstrzykuje JavaScript i CSS specyficzne dla modułu do Panelu administracyjnego dla strony konfiguracji. |
| `actionAdminMybingAjaxController` | Niestandardowy hook dla `AdminMybingAjaxController` do obsługi specyficznych akcji AJAX. | Używany wewnętrznie do dynamicznych aktualizacji i pobierania danych w zakładkach diagnostycznych modułu. |
| `actionModuleInstall` | Podczas instalacji modułu. | Wykonuje początkową konfigurację, tworzy wpisy konfiguracyjne i rejestruje hooki. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Czyści wpisy konfiguracyjne i wyrejestrowuje hooki. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie deweloperskie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
