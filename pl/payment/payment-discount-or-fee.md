---
title: "Zniżka lub Opłata za Płatność - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Zniżka lub Opłata za Płatność” od MyPresta.eu."
sidebar:
  label: "Zniżka lub Opłata za Płatność - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Payment Discount or Fee na MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-discount-or-fee.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/payment-discount-or-fee/)
>
> ---


# Zniżka lub Opłata za Płatność

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Zniżka lub Opłata za Płatność” oferuje kompleksowy zestaw opcji do precyzyjnego kontrolowania sposobu stosowania zniżek lub opłat.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Zniżka lub Opłata za Płatność)

Jest to główny ekran konfiguracji, na którym włączasz i ustawiasz podstawowe zachowanie modułu.

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania funkcjonalności modułu w całym Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł zacznie stosować zniżki lub opłaty zgodnie z Twoimi zdefiniowanymi zasadami podczas realizacji zamówienia.
        -   *Gdy wyłączone:* Moduł zaprzestanie wszystkich operacji, a żadne zniżki ani opłaty nie będą stosowane.
    -   **Zalecana wartość:** TAK (po skonfigurowaniu zasad).
    -   **Scenariusz / przykład dla sprzedawcy:** Skończyłeś konfigurować wszystkie swoje zasady i jesteś gotowy do uruchomienia. Włącz to, aby aktywować moduł. Jeśli musisz tymczasowo go wyłączyć do konserwacji, ustaw na NIE.
-   **Wyświetl opłatę/zniżkę w podsumowaniu koszyka:**

    -   **Co robi to ustawienie:** Kontroluje, czy korekta metody płatności jest wyświetlana jako osobna pozycja w podsumowaniu koszyka *zanim* klient dotrze do kroku płatności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci zobaczą pozycję taką jak „Korekta metody płatności” w podsumowaniu koszyka, nawet przed wybraniem metody płatności, wskazując, że ostateczna cena może się zmienić.
        -   *Gdy wyłączone:* Korekta pojawi się dopiero po wybraniu metody płatności na stronie realizacji zamówienia.
    -   **Zalecana wartość:** TAK (dla przejrzystości).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci byli w pełni świadomi potencjalnych korekt płatności jak najwcześniej. Włączenie tego zapewnia maksymalną przejrzystość.
-   **Zastosuj opłatę/zniżkę do kosztów wysyłki:**

    -   **Co robi to ustawienie:** Określa, czy obliczona zniżka lub opłata powinna być również stosowana do kosztów wysyłki zamówienia, czy tylko do sumy produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli masz 2% opłaty, a suma produktów wynosi 100 zł, a wysyłka 10 zł, opłata wyniesie 2% ze 110 zł (2,20 zł).
        -   *Gdy wyłączone:* 2% opłaty dotyczyłoby tylko sumy produktów 100 zł (2,00 zł), a wysyłka pozostałaby oddzielna.
    -   **Zalecana wartość:** TAK (jeśli opłaty Twojej bramki płatności również dotyczą całkowitej wartości zamówienia, włączając wysyłkę).
    -   **Scenariusz / przykład dla sprzedawcy:** Większość bramek płatności pobiera opłatę procentową od *całej* kwoty transakcji, włączając wysyłkę. Włączenie tego zapewnia, że Twoja opłata dokładnie odzwierciedla Twoje koszty.
-   **Zastosuj opłatę/zniżkę do podatku:**

    -   **Co robi to ustawienie:** Określa, czy obliczona zniżka lub opłata powinna być również stosowana do kwoty podatku w zamówieniu, czy tylko do sumy produktów (i potencjalnie wysyłki).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli masz 2% opłaty, a suma produktów wynosi 100 zł, wysyłka 10 zł, a podatek 20 zł, opłata wyniesie 2% ze 130 zł (2,60 zł).
        -   *Gdy wyłączone:* 2% opłaty dotyczyłoby tylko sumy produktów (i wysyłki, jeśli włączone), a podatek pozostałby oddzielny.
    -   **Zalecana wartość:** TAK (jeśli opłaty Twojej bramki płatności również dotyczą całkowitej wartości zamówienia, włączając podatek).
    -   **Scenariusz / przykład dla sprzedawcy:** Podobnie jak w przypadku wysyłki, bramki płatności zazwyczaj pobierają opłatę od całkowitej kwoty. Włączenie tego zapewnia, że Twoje obliczenia opłat są kompleksowe.
-   **Etykieta opłaty/zniżki w koszyku/zamówieniu:**

    -   **Co robi to ustawienie:** Pozwala dostosować tekst etykiety, która pojawia się obok kwoty zniżki lub opłaty w podsumowaniu koszyka i szczegółach zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Dopłata za metodę płatności”:* Ten tekst zostanie wyświetlony.
        -   *Gdy ustawione na „Zniżka za płatność”:* Ten tekst zostanie wyświetlony.
    -   **Zalecana wartość:** „Korekta metody płatności” lub „Dopłata za płatność” / „Zniżka za płatność” w zależności od Twojego głównego zastosowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Głównie używasz modułu do dodawania opłat. Ustawienie etykiety na „Dopłata za płatność” sprawia, że jest to jasne dla klientów. Jeśli oferujesz zniżki, „Zniżka za płatność” jest bardziej odpowiednia.
-   **URL zadania Cron do czyszczenia dziennika audytu:**

    -   **Co robi to ustawienie:** Udostępnia adres URL, który możesz skonfigurować jako zadanie cron na swoim serwerze, aby automatycznie czyścić stare wpisy z dziennika audytu modułu, zapobiegając nadmiernemu rozrostowi bazy danych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy skonfigurowane jako zadanie cron:* Dziennik audytu będzie regularnie oczyszczany ze starych wpisów, poprawiając wydajność bazy danych.
        -   *Gdy nie skonfigurowane:* Dziennik audytu będzie rósł w nieskończoność, potencjalnie spowalniając Twój Panel administracyjny z czasem.
    -   **Zalecana wartość:** Skonfiguruj zadanie cron, aby uruchamiać ten adres URL codziennie lub co tydzień.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoja baza danych była lekka i szybka. Skopiuj ten adres URL i dodaj go do harmonogramu zadań cron w panelu sterowania Twojego hostingu.

### 2.2 Dedykowany ekran administracyjny: Zasady zniżek lub opłat za płatność (Panel administracyjny > Płatności > Zasady zniżek lub opłat za płatność)

Ten ekran służy do definiowania i zarządzania wszystkimi zasadami stosowania zniżek lub opłat.

-   **Nazwa ekranu i lokalizacja w menu:** **Zasady zniżek lub opłat za płatność** (znajduje się w sekcji **Płatności** w głównym menu Panelu administracyjnego PrestaShop).
-   **Dostępne akcje i ustawienia:**

    -   **Tabela z listą zasad:** Wyświetla wszystkie Twoje aktualnie aktywne i nieaktywne zasady, pokazując ich nazwę, metodę płatności, typ (zniżka/opłata), wartość i status.
    -   **Przycisk „Dodaj nową zasadę”:** Kliknij, aby utworzyć nową zasadę zniżki lub opłaty.
    -   **Akcje Edytuj/Usuń:** Dla każdej zasady na liście możesz kliknąć, aby edytować jej szczegóły lub ją usunąć.
    -   **Pola formularza do dodawania/edycji zasady:**
        -   **Nazwa zasady:**
            -   **Co robi to ustawienie:** Opisowa nazwa Twojej zasady, widoczna tylko w Panelu administracyjnym.
            -   **Efekt zmiany tego ustawienia:** Pomaga łatwo identyfikować i zarządzać zasadami.
            -   **Zalecana wartość:** Jasna i opisowa (np. „Opłata PayPal 2%”, „Zniżka za przelew bankowy 5%”).
        -   **Metoda płatności:**
            -   **Co robi to ustawienie:** Wybiera konkretną bramkę płatności lub metodę, do której ta zasada ma zastosowanie.
            -   **Efekt zmiany tego ustawienia:** Zasada zostanie aktywowana tylko wtedy, gdy klient wybierze tę metodę płatności.
            -   **Zalecana wartość:** Wybierz dokładną metodę płatności, którą chcesz objąć.
            -   **Scenariusz / przykład dla sprzedawcy:** Chcesz dodać opłatę za „PayPal”, więc wybierasz „PayPal” z listy rozwijanej.
        -   **Typ:**
            -   **Co robi to ustawienie:** Określa, czy zasada stosuje „Zniżkę” czy „Opłatę”.
            -   **Efekt zmiany tego ustawienia:**
                -   *Zniżka:* Zmniejsza sumę zamówienia.
                -   *Opłata:* Zwiększa sumę zamówienia.
            -   **Zalecana wartość:** Wybierz w zależności od celu (np. „Opłata” za koszty przetwarzania kart kredytowych).
        -   **Wartość:**
            -   **Co robi to ustawienie:** Kwota lub procent zniżki/opłaty.
            -   **Efekt zmiany tego ustawienia:**
                -   *Jeśli „Typ” to „Procent”:* Wprowadź „2” dla 2%.
                -   *Jeśli „Typ” to „Stała kwota”:* Wprowadź „5.00” dla 5,00 zł.
            -   **Zalecana wartość:** Dokładny procent lub stała kwota, którą chcesz zastosować.
        -   **Typ wartości:**
            -   **Co robi to ustawienie:** Wybierz, czy „Wartość” jest „Procentem” całkowitej kwoty zamówienia, czy „Stałą kwotą”.
            -   **Efekt zmiany tego ustawienia:** Określa, jak interpretowane jest pole „Wartość”.
            -   **Zalecana wartość:** Procent jest powszechny dla opłat; stała kwota dla konkretnych zniżek.
        -   **Minimalna kwota koszyka (opcjonalnie):**
            -   **Co robi to ustawienie:** Minimalna suma zamówienia (przed zniżką/opłatą) wymagana do zastosowania tej zasady.
            -   **Efekt zmiany tego ustawienia:** Jeśli suma koszyka jest poniżej tej kwoty, zasada nie zostanie zastosowana.
            -   **Zalecana wartość:** Pozostaw puste, jeśli nie jest wymagane minimum.
            -   **Scenariusz / przykład dla sprzedawcy:** Chcesz stosować opłatę tylko do większych zamówień, aby uniknąć mikro-opłat za małe zakupy.
        -   **Maksymalna kwota koszyka (opcjonalnie):**
            -   **Co robi to ustawienie:** Maksymalna suma zamówienia (przed zniżką/opłatą), dla której ta zasada ma zastosowanie.
            -   **Efekt zmiany tego ustawienia:** Jeśli suma koszyka jest powyżej tej kwoty, zasada nie zostanie zastosowana.
            -   **Zalecana wartość:** Pozostaw puste, jeśli nie jest wymagane maksimum.
        -   **Grupy klientów (opcjonalnie):**
            -   **Co robi to ustawienie:** Ogranicza zasadę do określonych grup klientów (np. „Hurtownicy”, „Goście”).
            -   **Efekt zmiany tego ustawienia:** Tylko klienci należący do wybranych grup zostaną objęci tą zasadą.
            -   **Zalecana wartość:** Wybierz „Wszystkie grupy klientów”, chyba że masz specyficzne strategie cenowe oparte na grupach.
            -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zaoferować specjalną zniżkę dla swoich „Klientów VIP”, gdy płacą przelewem bankowym.
        -   **Kraje (opcjonalnie):**
            -   **Co robi to ustawienie:** Ogranicza zasadę do klientów z określonych krajów.
            -   **Efekt zmiany tego ustawienia:** Zasada zostanie zastosowana tylko wtedy, gdy adres wysyłki klienta znajduje się w jednym z wybranych krajów.
            -   **Zalecana wartość:** Wybierz „Wszystkie kraje”, chyba że masz strategie płatności specyficzne dla kraju.
            -   **Scenariusz / przykład dla sprzedawcy:** Masz wyższe opłaty za przetwarzanie międzynarodowych płatności kartą kredytową z niektórych regionów.
        -   **Produkty do wykluczenia (opcjonalnie):**
            -   **Co robi to ustawienie:** Pozwala określić pojedyncze produkty, które *nie* powinny być uwzględniane w obliczaniu zniżki lub opłaty.
            -   **Efekt zmiany tego ustawienia:** Wartość tych produktów zostanie odjęta od sumy koszyka *przed* obliczeniem procentu lub stałej kwoty.
            -   **Zalecana wartość:** Pozostaw puste, chyba że konkretne produkty powinny być zwolnione.
            -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz niektóre produkty o niskiej marży, gdzie zastosowanie opłaty uczyniłoby je nieopłacalnymi, więc je wykluczasz.
        -   **Status (Włącz/Wyłącz):**
            -   **Co robi to ustawienie:** Aktywuje lub dezaktywuje pojedynczą zasadę bez jej usuwania.
            -   **Efekt zmiany tego ustawienia:**
                -   *Włączone:* Zasada jest aktywna i zostanie zastosowana.
                -   *Wyłączone:* Zasada jest nieaktywna i nie zostanie zastosowana.
            -   **Zalecana wartość:** Włączone dla aktywnych zasad.
            -   **Scenariusz / przykład dla sprzedawcy:** Chcesz tymczasowo wstrzymać zasadę dla promocji bez utraty jej konfiguracji.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  Zacznij od zidentyfikowania, które metody płatności generują koszty lub oferują korzyści, które chcesz przekazać.
    2.  Kliknij „Dodaj nową zasadę”.
    3.  Nadaj zasadzie jasną nazwę.
    4.  Wybierz docelową metodę płatności.
    5.  Wybierz „Opłata” lub „Zniżka” i wprowadź wartość (procentową lub stałą).
    6.  Dopracuj zasadę, dodając minimalne/maksymalne kwoty koszyka, grupy klientów, kraje lub wykluczenia produktów, jeśli to konieczne.
    7.  Włącz zasadę i zapisz.
    8.  Przetestuj zasadę w swoim sklepie, składając zamówienie testowe.

### 2.3 Dedykowany ekran administracyjny: Dziennik audytu zniżek lub opłat za płatność (Panel administracyjny > Płatności > Dziennik audytu zniżek lub opłat za płatność)

Ten ekran zawiera historyczny zapis wszystkich przypadków, w których moduł zastosował zniżkę lub opłatę.

-   **Nazwa ekranu i lokalizacja w menu:** **Dziennik audytu zniżek lub opłat za płatność** (znajduje się w sekcji **Płatności** w głównym menu Panelu administracyjnego PrestaShop).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela z listą dziennika:** Wyświetla wpisy z takimi szczegółami jak:
        -   **ID zamówienia:** ID zamówienia, do którego zastosowano korektę.
        -   **Nazwa klienta:** Klient, który złożył zamówienie.
        -   **Metoda płatności:** Wybrana metoda płatności.
        -   **Zastosowana zasada:** Nazwa zasady, która wywołała korektę.
        -   **Typ korekty:** Czy była to zniżka, czy opłata.
        -   **Wartość korekty:** Kwota zniżki lub opłaty.
        -   **Data:** Kiedy korekta została zastosowana.
    -   **Filtrowanie i wyszukiwanie:** Możesz filtrować dziennik według ID zamówienia, klienta, metody płatności lub daty, aby szybko znaleźć konkretne wpisy.
    -   **Efekt zmian:** Ten ekran służy tylko do przeglądania; nie możesz bezpośrednio modyfikować wpisów dziennika. Służy jako cenne źródło informacji do rozwiązywania problemów i analizy.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Regularnie przeglądaj dziennik audytu, aby upewnić się, że zasady są stosowane prawidłowo.
    -   Używaj go do rozwiązywania zapytań klientów dotyczących rozbieżności w cenach.
    -   Monitoruj liczbę korekt, aby zrozumieć wpływ Twoich zasad.

### 2.4 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Wyświetl opłatę/zniżkę w podsumowaniu koszyka | TAK | Pokazuje korektę wcześnie w koszyku dla przejrzystości. |
| | Zastosuj opłatę/zniżkę do kosztów wysyłki | TAK | Uwzględnia wysyłkę w obliczeniach opłaty/zniżki. |
| | Zastosuj opłatę/zniżkę do podatku | TAK | Uwzględnia podatek w obliczeniach opłaty/zniżki. |
| | Etykieta opłaty/zniżki w koszyku/zamówieniu | „Korekta metody płatności” | Dostosowuje etykietę wyświetlaną klientom. |
| | URL zadania Cron do czyszczenia dziennika audytu | (Podany URL) | Automatyzuje czyszczenie starych wpisów dziennika audytu. |
| **Zasady zniżek lub opłat za płatność** | Nazwa zasady | (Opisowa nazwa) | Wewnętrzna nazwa zasady. |
| | Metoda płatności | (Konkretna metoda) | Wybiera metodę płatności dla zasady. |
| | Typ | Opłata / Zniżka | Określa, czy jest to wzrost, czy spadek. |
| | Wartość | (Wartość numeryczna) | Kwota lub procent korekty. |
| | Typ wartości | Procent / Stała kwota | Jak interpretowana jest „Wartość”. |
| | Minimalna kwota koszyka | (Puste) | Minimalna suma zamówienia do zastosowania zasady. |
| | Maksymalna kwota koszyka | (Puste) | Maksymalna suma zamówienia do zastosowania zasady. |
| | Grupy klientów | Wszystkie grupy klientów | Ogranicza zasadę do określonych grup klientów. |
| | Kraje | Wszystkie kraje | Ogranicza zasadę do określonych krajów. |
| | Produkty do wykluczenia | (Puste) | Produkty, których wartość jest wykluczona z obliczeń. |
| | Status | Włączone | Aktywuje lub dezaktywuje zasadę. |
| **Dziennik audytu zniżek lub opłat za płatność** | (Wszystkie pola) | (Tylko podgląd) | Zapewnia historyczny zapis zastosowanych korekt. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje zniżki/opłaty nie pojawiają się na stronie realizacji zamówienia. Co powinienem sprawdzić?**
O1:

-   **Moduł włączony?** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Zniżka lub Opłata za Płatność” jest włączony.
-   **Zasady aktywne?** Przejdź do **Płatności > Zasady zniżek lub opłat za płatność** i sprawdź, czy Twoje konkretne zasady są włączone (kolumna Status).
-   **Warunki zasady spełnione?** Sprawdź dokładnie, czy warunki dotyczące sumy koszyka, grupy klientów, kraju lub wykluczonych produktów Twoich zasad są spełnione przez Twoje zamówienie testowe.
-   **Metoda płatności wybrana?** Korekta pojawia się *dopiero po* wybraniu metody płatności na stronie realizacji zamówienia (chyba że włączono „Wyświetl opłatę/zniżkę w podsumowaniu koszyka”).
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (prawy górny róg). Czasami stare dane z pamięci podręcznej uniemożliwiają natychmiastowe pojawienie się zmian.

**P2: Kwota zniżki/opłaty wydaje się nieprawidłowa.**
O2:

-   **Typ wartości (procentowa vs. stała):** Upewnij się, że wybrałeś prawidłowy „Typ wartości” (procentowa lub stała kwota) dla swojej zasady.
-   **Zastosuj do wysyłki/podatku:** Sprawdź w głównej konfiguracji modułu, czy „Zastosuj opłatę/zniżkę do kosztów wysyłki” i „Zastosuj opłatę/zniżkę do podatku” są włączone lub wyłączone, ponieważ wpływa to na kwotę bazową dla obliczeń procentowych.
-   **Wykluczone produkty:** Jeśli masz produkty wykluczone z obliczeń, upewnij się, że ich wartość jest prawidłowo odjęta przed zastosowaniem procentu/stałej kwoty.
-   **Waluta:** Upewnij się, że domyślna waluta Twojego sklepu jest prawidłowo ustawiona w PrestaShop, ponieważ moduł opiera się na tym dla stałych kwot.

**P3: Moduł powoduje konflikt z innym modułem lub moim motywem.**
O3:

-   **Zidentyfikuj konflikt:** Spróbuj wyłączać inne moduły jeden po drugim, aby ustalić, który z nich powoduje konflikt.
-   **Nadpisania motywu:** Jeśli masz mocno dostosowany motyw, może on nadpisywać podstawowe szablony realizacji zamówienia PrestaShop, na których opiera się moduł. Sprawdź folder `templates/checkout/` swojego motywu pod kątem plików takich jak `payment.tpl` lub `cart-summary.tpl`.
-   **Skontaktuj się z pomocą techniczną:** Jeśli podejrzewasz konflikt, zbierz szczegóły (komunikaty o błędach, kroki do odtworzenia) i skontaktuj się z pomocą techniczną MyPresta.eu.

**P4: Jak przetłumaczyć „Etykietę opłaty/zniżki” na inne języki?**
O4:

-   Przejdź do **Lokalizacja > Tłumaczenia**.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, swój motyw i język, na który chcesz przetłumaczyć.
-   Znajdź moduł „Zniżka lub Opłata za Płatność”. Powinieneś zobaczyć pole do tłumaczenia ustawienia „Etykieta opłaty/zniżki w koszyku/zamówieniu”.

**P5: Mój dziennik audytu staje się zbyt duży. Jak nim zarządzać?**
O5:

-   W głównej konfiguracji modułu znajdziesz „URL zadania Cron do czyszczenia dziennika audytu”.
-   Skopiuj ten adres URL i skonfiguruj go jako zadanie cron na swoim serwerze hostingowym. Większość paneli sterowania hostingiem (cPanel, Plesk) ma sekcję „Zadania Cron”, w której możesz dodać nowe zadanie.
-   Ustaw go tak, aby uruchamiał się codziennie lub co tydzień (np. `wget -q -O /dev/null "TWÓJ_URL_CRON_TUTAJ"`). Spowoduje to automatyczne usuwanie starych wpisów dziennika i optymalizację bazy danych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Zniżka lub Opłata za Płatność” dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Zniżka lub Opłata za Płatność” stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), z silnym naciskiem na hooki w celu integracji z przepływem realizacji zamówienia. Wykorzystuje `ObjectModel` do zarządzania zasadami i dziennikami audytu oraz niestandardowe kontrolery zarówno do interakcji AJAX w front-office, jak i zarządzania w back-office. Podstawowa logika obliczania i stosowania opłat/zniżek jest hermetyzowana w dedykowanych klasach silnika, zapewniając separację odpowiedzialności. Klasy kompatybilności są używane do niwelowania różnic między PrestaShop 1.7, 8 i 9.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/ajax.php`
    -   **Nazwa klasy:** `PaydisorfeeAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje żądania AJAX ze strony realizacji zamówienia. Gdy klient wybierze metodę płatności, ten kontroler odbiera żądanie, oblicza odpowiednią zniżkę/opłatę na podstawie aktywnych zasad i zwraca zaktualizowane dane podsumowania koszyka (np. nową sumę, pozycję z opłatą/zniżką) do dynamicznego wyświetlenia.
-   `controllers/front/cron.php`
    -   **Nazwa klasy:** `PaydisorfeeCronModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Udostępnia punkt końcowy dla zadania cron do czyszczenia dziennika audytu. Po uzyskaniu dostępu, wyzwala logikę czyszczenia w module, usuwając stare wpisy dziennika na podstawie skonfigurowanych zasad przechowywania.
-   `controllers/front/index.php`
    -   **Nazwa klasy:** `PaydisorfeeIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Kontroler frontowy-placeholder, zazwyczaj używany do domyślnych stron modułu lub do zapobiegania listowaniu katalogów. W tym module jego główną funkcją może być obsługa domyślnego routingu, jeśli nie jest żądana żadna konkretna akcja, lub może przekierowywać do głównej strony sklepu.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminPaydisorfeeAuditLog.php`
    -   **Nazwa klasy:** `AdminPaydisorfeeAuditLogController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Dziennik audytu zniżek lub opłat za płatność
    -   **Zarządzana encja:** `PaydisorfeeAuditLog` (mapuje na tabelę bazy danych `ps_paydisorfee_log`)
    -   **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem wpisów dziennika audytu w Panelu administracyjnym PrestaShop. Używa `HelperList` do renderowania widoku siatki rekordów dziennika.
-   `controllers/admin/AdminPaydisorfeeRules.php`
    -   **Nazwa klasy:** `AdminPaydisorfeeRulesController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Zasady zniżek lub opłat za płatność
    -   **Zarządzana encja:** `PaydisorfeeRule` (mapuje na tabelę bazy danych `ps_paydisorfee_rule`)
    -   **Odpowiedzialność:** Zapewnia interfejs do tworzenia, edytowania, usuwania i listowania zasad zniżek/opłat za płatność. Używa `HelperList` do przeglądu zasad i `HelperForm` do formularzy dodawania/edycji zasad, w tym dynamicznych selektorów dla produktów, grup klientów i krajów.
-   `controllers/admin/index.php`
    -   **Nazwa klasy:** `PaydisorfeeAdminIndexModuleFrontController` (rozszerza `ModuleAdminController`)
    -   **Odpowiedzialność:** Podobnie jak frontowy `index.php`, może służyć jako domyślny kontroler administracyjny lub przekierowujący, jeśli nie jest żądana żadna konkretna akcja dla kontekstu administracyjnego.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   `classes/index.php`: Standardowy pusty plik zapobiegający listowaniu katalogów.
-   `classes/PaydisorfeeAdmin.php`
    -   **Odpowiedzialność:** Prawdopodobnie zawiera metody pomocnicze lub funkcje narzędziowe specyficzne dla administracji Back Office, potencjalnie do obsługi przesyłania formularzy, walidacji danych lub renderowania konkretnych komponentów administracyjnych.
-   `classes/PaydisorfeeAuditLog.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_paydisorfee_log`
    -   **Pola `$definition`:** Definiuje strukturę wpisów dziennika audytu (np. `id_order`, `id_customer`, `payment_method`, `rule_name`, `type`, `value`, `date_add`).
    -   **Kluczowe metody publiczne:** Metody do dodawania nowych wpisów dziennika, pobierania danych dziennika i potencjalnie do operacji czyszczenia.
-   `classes/PaydisorfeeCartState.php`
    -   **Odpowiedzialność:** Zarządza stanem koszyka podczas procesu realizacji zamówienia, w szczególności w odniesieniu do zastosowanej zniżki/opłaty modułu. Prawdopodobnie przechowuje i pobiera obliczoną korektę, aby zapewnić jej trwałość na różnych etapach realizacji zamówienia i prawidłowe zastosowanie do zamówienia.
-   `classes/PaydisorfeeCompatibility.php`
    -   **Odpowiedzialność:** Zawiera metody do obsługi problemów z kompatybilnością między różnymi wersjami PrestaShop (1.7.x, 8.x, 9.x). Ta klasa abstrahuje kod specyficzny dla wersji, taki jak różnice w nazwach hooków, strukturach klas lub wywołaniach API, zapewniając prawidłowe działanie modułu na wszystkich obsługiwanych wersjach.
-   `classes/PaydisorfeeDashboard.php`
    -   **Odpowiedzialność:** Prawdopodobnie dostarcza dane lub logikę dla potencjalnego pulpitu nawigacyjnego lub widoku analitycznego w interfejsie administracyjnym modułu, podsumowując wpływ zniżek/opłat.
-   `classes/PaydisorfeeEngine.php`
    -   **Odpowiedzialność:** Jest to podstawowa klasa logiki do obliczania i stosowania zniżki lub opłaty. Przyjmuje bieżący koszyk, wybraną metodę płatności i aktywne zasady jako dane wejściowe, a następnie określa ostateczną kwotę korekty. Obsługuje obliczenia procentowe vs. stałe, minimalne/maksymalne kwoty koszyka i wykluczenia produktów.
-   `classes/PaydisorfeeFeeProduct.php`
    -   **Odpowiedzialność:** Potencjalnie klasa pomocnicza do tworzenia „wirtualnego produktu” reprezentującego opłatę/zniżkę w koszyku, umożliwiając jej wyświetlanie jako pozycji wiersza. Jest to powszechna technika w PrestaShop do integrowania dynamicznych korekt cen w podsumowaniu koszyka.
-   `classes/PaydisorfeeLog.php`
    -   **Odpowiedzialność:** Może to być alias lub starsza wersja `PaydisorfeeAuditLog.php`, lub prostszy mechanizm logowania do celów debugowania.
-   `classes/PaydisorfeeRule.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_paydisorfee_rule`
    -   **Pola `$definition`:** Definiuje strukturę zasady płatności (np. `name`, `id_payment_module`, `type`, `value`, `value_type`, `min_cart_amount`, `max_cart_amount`, `customer_groups`, `countries`, `excluded_products`, `active`).
    -   **Kluczowe metody publiczne:** Metody do operacji CRUD na zasadach, pobierania aktywnych zasad i walidacji warunków zasad.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `paydisorfee/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Back-office (używane w `AdminPaydisorfeeRules` dla selektora wykluczeń produktów).
    -   **Opis:** Zapewnia funkcjonalność autouzupełniania do wyszukiwania produktów podczas konfigurowania pola „Produkty do wykluczenia” w zasadzie. Prawdopodobnie wysyła żądania AJAX do kontrolera back-office w celu pobrania sugestii produktów.
-   `paydisorfee/views/js/adminPaydisorfeeDashboard.js`
    -   **Zakres:** Back-office (jeśli istnieje widok pulpitu nawigacyjnego).
    -   **Opis:** JavaScript dla wszelkich funkcji pulpitu nawigacyjnego lub analitycznych w interfejsie administracyjnym modułu. Może to obejmować renderowanie wykresów, filtrowanie danych lub dynamiczne ładowanie treści.
-   `paydisorfee/views/js/adminPaydisorfeeSelector.js`
    -   **Zakres:** Back-office (używane w `AdminPaydisorfeeRules`).
    -   **Opis:** Obsługuje dynamiczny wybór grup klientów, krajów i potencjalnie metod płatności w formularzu konfiguracji zasad. Może zarządzać polami wielokrotnego wyboru lub dostarczać interaktywne elementy dla tych pól.
-   `paydisorfee/views/js/checkout.js`
    -   **Zakres:** Front-office (strona realizacji zamówienia).
    -   **Opis:** Jest to krytyczny skrypt dla funkcjonalności front-office. Nasłuchuje zmian w wybranej metodzie płatności na stronie realizacji zamówienia. Gdy metoda płatności zostanie wybrana, wyzwala wywołanie AJAX do `controllers/front/ajax.php` w celu ponownego obliczenia sumy koszyka i dynamicznego zaktualizowania podsumowania zamówienia o nową pozycję zniżki/opłaty. Obsługuje również logikę wyświetlania tych aktualizacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `paydisorfee/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Back-office.
    -   **Opis:** Style dla pola wyszukiwania autouzupełniania i jego rozwijanej listy sugestii, używane w selektorze wykluczeń produktów w konfiguracji zasad.
-   `paydisorfee/views/css/admin_paydisorfee.css`
    -   **Zakres:** Back-office.
    -   **Opis:** Ogólne style dla stron Back Office modułu, w tym listy zasad, dziennika audytu i formularzy konfiguracji. Zapewnia spójny wygląd i działanie z motywem administracyjnym PrestaShop.
-   `paydisorfee/views/css/front.css`
    -   **Zakres:** Front-office.
    -   **Opis:** Style do wyświetlania pozycji zniżki/opłaty i wszelkich powiązanych komunikatów na stronie realizacji zamówienia lub w podsumowaniu koszyka. Zapewnia, że korekta jest wyraźnie widoczna i dobrze zintegrowana z projektem sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   `paydisorfee/lib/searchTool/views/scripts.tpl`
    -   **Zakres:** Back-office.
    -   **Opis:** Zawiera kod Smarty do dołączania JavaScript i potencjalnie CSS dla narzędzia wyszukiwania (np. `autocomplete.js`). Prawdopodobnie jest dołączony do formularza `AdminPaydisorfeeRules`.
-   `paydisorfee/views/templates/admin/auditPreview.tpl`
    -   **Zakres:** Back-office (AdminPaydisorfeeAuditLogController).
    -   **Opis:** Szablon do renderowania wpisów dziennika audytu, zazwyczaj używany przez `HelperList` do wyświetlania siatki danych.
-   `paydisorfee/views/templates/admin/cron_setup.tpl`
    -   **Zakres:** Back-office (Główna konfiguracja modułu).
    -   **Opis:** Wyświetla adres URL zadania cron i instrukcje dotyczące jego konfiguracji, jak widać na głównej stronie konfiguracji modułu.
-   `paydisorfee/views/templates/admin/rulesPreview.tpl`
    -   **Zakres:** Back-office (AdminPaydisorfeeRulesController).
    -   **Opis:** Szablon do renderowania listy zasad płatności, używany przez `HelperList` do wyświetlania siatki danych.
-   `paydisorfee/views/templates/admin/scopeSelector.tpl`
    -   **Zakres:** Back-office (AdminPaydisorfeeRulesController).
    -   **Opis:** Szablon dla dynamicznych selektorów (grup klientów, krajów, produktów do wykluczenia) w formularzu konfiguracji zasad, często używany w połączeniu z `adminPaydisorfeeSelector.js`.
-   `paydisorfee/views/templates/hook/admin_order.tpl`
    -   **Zakres:** Back-office (Hook `displayAdminOrderTabContent` lub podobny).
    -   **Opis:** Wyświetla informacje o zastosowanej zniżce lub opłacie za płatność na stronie szczegółów zamówienia PrestaShop w Back Office. Pozwala to administratorom zobaczyć korektę bezpośrednio w zamówieniu.
-   `paydisorfee/views/templates/hook/payment_top.tpl`
    -   **Zakres:** Front-office (Hook `displayPaymentTop` lub podobny).
    -   **Opis:** Ten szablon jest prawdopodobnie używany do wyświetlania dynamicznych informacji o zniżce/opłacie na stronie realizacji zamówienia, zazwyczaj powyżej wyboru metody płatności lub jako część podsumowania zamówienia. Jest aktualizowany przez `checkout.js` za pośrednictwem AJAX.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_paydisorfee_log`: Przechowuje wpisy dziennika audytu dla każdej zastosowanej zniżki lub opłaty.
    -   `id_paydisorfee_log` (KLUCZ GŁÓWNY)
    -   `id_order` (INT)
    -   `id_customer` (INT)
    -   `payment_method` (VARCHAR)
    -   `rule_name` (VARCHAR)
    -   `type` (VARCHAR, „discount” lub „fee”)
    -   `value` (DECIMAL)
    -   `date_add` (DATETIME)
-   `ps_paydisorfee_rule`: Przechowuje konfigurację dla każdej zasady zniżki/opłaty za płatność.
    -   `id_paydisorfee_rule` (KLUCZ GŁÓWNY)
    -   `name` (VARCHAR)
    -   `id_payment_module` (INT)
    -   `type` (VARCHAR, „discount” lub „fee”)
    -   `value` (DECIMAL)
    -   `value_type` (VARCHAR, „percentage” lub „fixed”)
    -   `min_cart_amount` (DECIMAL)
    -   `max_cart_amount` (DECIMAL)
    -   `customer_groups` (TEXT, serializowana tablica ID)
    -   `countries` (TEXT, serializowana tablica ID)
    -   `excluded_products` (TEXT, serializowana tablica ID)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `PAYDISORFEE_ENABLED`, `PAYDISORFEE_DISPLAY_CART`, `PAYDISORFEE_APPLY_SHIPPING`, `PAYDISORFEE_APPLY_TAX`, `PAYDISORFEE_LABEL`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Przed renderowaniem kontrolera frontowego | Rejestruje CSS (`front.css`) i JS (`checkout.js`) front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem kontrolera administracyjnego | Rejestruje CSS (`admin_paydisorfee.css`, `autocomplete.css`) i JS (`adminPaydisorfeeDashboard.js`, `adminPaydisorfeeSelector.js`, `autocomplete.js`) back-office. |
| `displayHeader` | W sekcji `<head>` każdej strony | Potencjalnie do ładowania globalnego JS/CSS lub tagów meta. |
| `displayPaymentTop` | Na górze bloku wyboru płatności na stronie realizacji zamówienia | Wyświetla dynamiczne informacje o opłacie/zniżce klientowi. |
| `actionCartSummary` | Po wygenerowaniu podsumowania koszyka | Używane do wstrzykiwania pozycji opłaty/zniżki do podsumowania koszyka. |
| `actionPaymentConfirmation` | Po pomyślnym złożeniu zamówienia | Rejestruje zastosowaną zniżkę/opłatę w dzienniku audytu. |
| `actionValidateOrder` | Po zatwierdzeniu zamówienia | Zapewnia, że ostateczna suma zamówienia odzwierciedla korektę metody płatności. |
| `displayAdminOrderTabContent` | Na stronie szczegółów zamówienia w Back Office | Wyświetla szczegóły korekty płatności dla zamówienia. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w Back Office | Podobnie jak `displayAdminOrderTabContent`, do wyświetlania danych modułu specyficznych dla zamówienia. |
| `actionGetExtraMailTemplateVars` | Przed wysłaniem e-maila z potwierdzeniem zamówienia | Wstrzykuje szczegóły opłaty/zniżki do szablonów e-mail. |
| `actionObjectOrderAddAfter` | Po dodaniu nowego obiektu zamówienia | Potencjalnie do końcowego przetwarzania lub logowania związanego z zamówieniem. |
| `actionObjectOrderUpdateAfter` | Po zaktualizowaniu obiektu zamówienia | Potencjalnie do ponownej oceny opłat, jeśli zamówienie zostanie zmodyfikowane. |
| `actionObjectCartUpdateAfter` | Po zaktualizowaniu obiektu koszyka | Wyzwala ponowne obliczenie potencjalnych opłat/zniżek. |
| `actionObjectCartAddAfter` | Po dodaniu nowego obiektu koszyka | Wyzwala ponowne obliczenie potencjalnych opłat/zniżek. |
| `actionAjaxDie` | Przed `die()` w kontekście AJAX | Pozwala modułowi wykonywać akcje przed wysłaniem odpowiedzi AJAX. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony Back Office | Rejestruje globalne JS/CSS administracyjne. |
| `displayModuleConfigureExtraButtons` | Na stronie konfiguracji modułu | Dodaje dodatkowe przyciski (np. „Zarządzaj zasadami”, „Wyświetl dziennik audytu”). |
| `displayPaymentOptions` | Wyświetla opcje płatności przy realizacji zamówienia | Potencjalnie modyfikuje opcje płatności na podstawie zasad. |
| `actionPaymentOptionsModifier` | Modyfikuje opcje płatności przed wyświetleniem | Pozwala modułowi dodawać/usuwać/modyfikować opcje płatności. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zniżka lub Opłata za Płatność”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
