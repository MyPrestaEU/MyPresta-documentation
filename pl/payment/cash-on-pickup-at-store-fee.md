---
title: "Płatność gotówką przy odbiorze w sklepie (+opłata) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop „Płatność gotówką przy odbiorze w sklepie (+opłata)” od MyPresta.eu."
sidebar:
  label: "Płatność gotówką przy odbiorze w sklepie (+opłata) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cash on pickup at store (+fee) na MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-pickup-at-store-fee.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/cash-on-pickup-at-store-fee/)
>
> ---


# Płatność gotówką przy odbiorze w sklepie (+opłata)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym ustawisz wszystkie opcje dla metody płatności „Płatność gotówką przy odbiorze w sklepie”.

#### **Ustawienia ogólne**

-   **Logo płatności**

    -   **Co robi to ustawienie:** Pozwala przesłać niestandardowy obraz (logo), który będzie wyświetlany obok opcji płatności „Płatność gotówką przy odbiorze w sklepie” podczas realizacji zamówienia. Pomaga to klientom wizualnie zidentyfikować metodę płatności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy obraz jest przesłany:* Wybrany obraz pojawi się obok nazwy metody płatności na stronie wyboru płatności.
        -   *Gdy żaden obraz nie jest przesłany:* Zostanie wyświetlone domyślne logo lub brak logo, w zależności od Twojego szablonu.
    -   **Zalecana wartość:** Prześlij wyraźne, małe logo, które reprezentuje „odbiór” lub „gotówkę” dla lepszego rozpoznania.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz przesłać ikonę torby na zakupy lub witryny sklepu, aby opcja płatności wyróżniała się.
-   **Tytuł metody płatności** (Klucz konfiguracji: `COPPRO_TITLE`)

    -   **Co robi to ustawienie:** Definiuje nazwę metody płatności, tak jak jest ona wyświetlana klientom podczas realizacji zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Nowy tytuł zostanie wyświetlony na stronie wyboru płatności, potwierdzeniu zamówienia i fakturach.
    -   **Zalecana wartość:** „Płatność gotówką przy odbiorze w sklepie” lub „Zapłać przy odbiorze w sklepie”.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz konkretną nazwę marki dla swojej usługi odbioru, możesz jej użyć tutaj, np. „Odbiór lokalny MyStore”.
-   **Status zamówienia dla nowych zamówień** (Klucz konfiguracji: `COPPRO_OS`)

    -   **Co robi to ustawienie:** Wybiera początkowy status, jaki będzie miało zamówienie w Twoim Panelu administracyjnym, gdy klient wybierze „Płatność gotówką przy odbiorze w sklepie”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Oczekiwanie na płatność gotówką przy odbiorze”:* Nowe zamówienia zostaną automatycznie przypisane do tego statusu, co ułatwi Ci identyfikację zamówień, które należy przygotować do odbioru i płatności.
    -   **Zalecana wartość:** Utwórz niestandardowy status zamówienia, taki jak „Oczekiwanie na płatność gotówką przy odbiorze” lub „Gotowe do odbioru” dla jasności.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz ustawić go na „Oczekiwanie na płatność gotówką przy odbiorze”, aby Twój personel wiedział, że ma przygotować produkty, ale ich nie wysyłać.
-   **Status zamówienia po opłaceniu** (Klucz konfiguracji: `COPPRO_OS_READY`)

    -   **Co robi to ustawienie:** Wybiera status zamówienia, na który zamówienie powinno zostać zmienione, gdy klient pomyślnie zapłaci i odbierze swoje produkty w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Płatność zaakceptowana”:* Po ręcznej aktualizacji zamówienia w Panelu administracyjnym po odbiorze i płatności, przejdzie ono do tego statusu, oznaczając je jako zakończone.
    -   **Zalecana wartość:** „Płatność zaakceptowana” lub „Dostarczono”.
    -   **Scenariusz/przykład dla sprzedawcy:** Po tym, jak klient odbierze i zapłaci, zmieniasz status zamówienia na „Płatność zaakceptowana”, aby sfinalizować transakcję w swoim systemie.

#### **Ograniczenia wartości koszyka**

-   **Minimalna wartość koszyka** (Klucz konfiguracji: `COPPRO_MINCART`, `COPPRO_MINCART_V`)

    -   **Co robi to ustawienie:** Pozwala ustawić minimalną całkowitą wartość zamówienia, aby kwalifikowało się do „Płatności gotówką przy odbiorze w sklepie”. Jeśli całkowita wartość koszyka jest poniżej tej wartości, metoda płatności nie zostanie wyświetlona.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na wartość (np. 10 zł):* Klienci z koszykiem o wartości mniejszej niż 10 zł nie zobaczą „Płatności gotówką przy odbiorze w sklepie” jako opcji.
        -   *Gdy pozostawione puste lub 0:* Nie będzie ograniczenia minimalnej wartości koszyka.
    -   **Zalecana wartość:** Pozostaw puste lub 0, chyba że masz konkretne powody operacyjne, aby wymagać minimum.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz ustawić minimum 5 zł, aby uniknąć bardzo małych zamówień, które nie są opłacalne dla Twojego personelu do przetworzenia do odbioru.
-   **Maksymalna wartość koszyka** (Klucz konfiguracji: `COPPRO_MAXCART`, `COPPRO_MAXCART_V`)

    -   **Co robi to ustawienie:** Pozwala ustawić maksymalną całkowitą wartość zamówienia, aby kwalifikowało się do „Płatności gotówką przy odbiorze w sklepie”. Jeśli całkowita wartość koszyka przekroczy tę wartość, metoda płatności nie zostanie wyświetlona.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na wartość (np. 500 zł):* Klienci z koszykiem o wartości większej niż 500 zł nie zobaczą „Płatności gotówką przy odbiorze w sklepie” jako opcji.
        -   *Gdy pozostawione puste lub 0:* Nie będzie ograniczenia maksymalnej wartości koszyka.
    -   **Zalecana wartość:** Pozostaw puste lub 0, chyba że masz konkretne obawy dotyczące obsługi bardzo dużych płatności gotówkowych.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz ustawić maksimum 1000 zł, jeśli nie czujesz się komfortowo z obsługą przez personel bardzo dużych sum gotówki w punkcie odbioru.

#### **Konfiguracja opłat / rabatów**

-   **Zastosuj rabat (nie opłatę)** (Klucz konfiguracji: `COPPRO_DISCOUNT`)

    -   **Co robi to ustawienie:** Jest to przełącznik. Jeśli włączony, moduł zastosuje *rabat* do całkowitej kwoty zamówienia zamiast *opłaty*, gdy zostanie wybrana opcja „Płatność gotówką przy odbiorze w sklepie”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Wartość ustawiona dla „Wartość opłaty procentowej” lub „Wartość opłaty stałej” zostanie odjęta od całkowitej kwoty zamówienia.
        -   *Gdy wyłączony:* Ustawiona wartość zostanie dodana do całkowitej kwoty zamówienia jako opłata.
    -   **Zalecana wartość:** Wyłączony (aby zastosować opłatę), jeśli chcesz pokryć koszty operacyjne, lub Włączony (aby zastosować rabat), jeśli chcesz zachęcić do odbiorów.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz włączyć to i ustawić 5% rabatu, aby zachęcić klientów do odbioru zamówień, oszczędzając na kosztach wysyłki.
-   **Wartość opłaty przy metodzie płatności** (Klucz konfiguracji: `COPPRO_FEEPAY`)

    -   **Co robi to ustawienie:** Jest to przełącznik. Jeśli włączony, kwota opłaty lub rabatu zostanie wyświetlona bezpośrednio obok nazwy metody płatności na stronie realizacji zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci zobaczą „Płatność gotówką przy odbiorze w sklepie (+ X,XX zł opłaty)” lub „Płatność gotówką przy odbiorze w sklepie (- X,XX zł rabatu)”.
        -   *Gdy wyłączony:* Zostanie wyświetlona tylko nazwa metody płatności, a opłata/rabat zostanie zastosowany do całkowitej kwoty koszyka bez wyraźnego wspomnienia obok metody.
    -   **Zalecana wartość:** Włączony, dla przejrzystości wobec klientów.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby klienci byli w pełni świadomi wszelkich dodatkowych kosztów lub oszczędności z góry, więc włączasz to.
-   **Opłata procentowa** (Klucz konfiguracji: `COPPRO_CHARGEP`, `COPPRO_CHARGEP_V`)

    -   **Co robi to ustawienie:** Pozwala zastosować opłatę lub rabat na podstawie procentu od całkowitej kwoty zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony i wprowadzona wartość (np. 5):* 5% opłaty (lub rabatu, jeśli „Zastosuj rabat” jest włączony) zostanie dodane/odjęte od całkowitej kwoty zamówienia.
        -   *Gdy wyłączony:* Nie zostanie zastosowana żadna opłata/rabat procentowy.
    -   **Zalecana wartość:** Wyłączony, chyba że wyraźnie chcesz zastosować opłatę procentową. Jeśli włączony, wartość między 1-10% jest powszechna dla opłat, lub 2-10% dla rabatów.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz pobrać 3% opłaty, aby pokryć koszty przetwarzania gotówki i obsługi, więc włączasz to i wpisujesz „3”.
-   **Opłata stała** (Klucz konfiguracji: `COPPRO_CHARGEA`, `COPPRO_CHARGEA_V`)

    -   **Co robi to ustawienie:** Pozwala zastosować stałą kwotę opłaty lub rabatu do całkowitej kwoty zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony i wprowadzona wartość (np. 2.50):* Stała opłata w wysokości 2,50 zł (lub rabat, jeśli „Zastosuj rabat” jest włączony) zostanie dodana/odjęta od całkowitej kwoty zamówienia.
        -   *Gdy wyłączony:* Nie zostanie zastosowana żadna opłata/rabat o stałej kwocie.
    -   **Zalecana wartość:** Włączony, z małą stałą kwotą (np. 1,00 zł - 3,00 zł), jeśli chcesz prostą, spójną opłatę.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz pobrać stałą opłatę w wysokości 2 zł za wszystkie zamówienia z odbiorem, więc włączasz to i wpisujesz „2.00”.

#### **Zaawansowane ustawienia wyświetlania i kompatybilności**

-   **Podsumowanie koszyka** (Klucz konfiguracji: `COPPRO_CARTPRESENTER`)

    -   **Co robi to ustawienie:** Jest to przełącznik, który kontroluje, czy opłata/rabat jest wyraźnie wyświetlany w bloku podsumowania koszyka (np. w prawej kolumnie lub na dole strony koszyka).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Opłata/rabat zostanie wyszczególniony w podsumowaniu koszyka, pokazując, jak wpływa na całkowitą kwotę.
        -   *Gdy wyłączony:* Opłata/rabat zostanie zastosowany do całkowitej kwoty, ale może nie być wyraźnie rozbity w podsumowaniu koszyka przed krokiem płatności.
    -   **Zalecana wartość:** Włączony, dla pełnej przejrzystości.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby klienci widzieli pozycję „Opłata za odbiór” w podsumowaniu koszyka, zanim jeszcze dotrą do kroku płatności, więc włączasz to.
-   **Podsumowanie adresu** (Klucz konfiguracji: `COPPRO_HOWFEE`)

    -   **Co robi to ustawienie:** To ustawienie kontroluje, gdzie opłata/rabat jest wyświetlany w sekcji podsumowania adresu podczas realizacji zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Opłata/rabat będzie widoczny w podsumowaniu adresu, zazwyczaj w pobliżu kosztów wysyłki.
        -   *Gdy wyłączony:* Opłata/rabat zostanie zastosowany, ale nie będzie wyraźnie wyświetlony w podsumowaniu adresu.
    -   **Zalecana wartość:** Włączony, dla spójności i przejrzystości.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby opłata była widoczna na wielu etapach realizacji zamówienia, w tym w podsumowaniu adresu, więc włączasz to.
-   **Włączony** (Klucz konfiguracji: `COPPRO_EVENTLISTENER`)

    -   **Co robi to ustawienie:** Jest to ogólny przełącznik do włączania lub wyłączania podstawowej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Metoda płatności „Płatność gotówką przy odbiorze w sklepie” będzie aktywna i dostępna dla klientów.
        -   *Gdy wyłączony:* Metoda płatności zostanie ukryta i niedostępna.
    -   **Zalecana wartość:** Włączony, po skonfigurowaniu wszystkich innych ustawień.
    -   **Scenariusz/przykład dla sprzedawcy:** Zakończyłeś konfigurację modułu i jesteś gotowy, aby zaoferować tę metodę płatności, więc ją włączasz.
-   **Wyłączony** (Klucz konfiguracji: `PS_ONE_PAGE_CHECKOUT_ENABLED`)

    -   **Co robi to ustawienie:** To ustawienie prawdopodobnie dotyczy kompatybilności z jednostronicową realizacją zamówienia w PrestaShop. Może to być ustawienie dziedziczone lub wskaźnik wyświetlania.
    -   **Efekt zmiany tego ustawienia:** Jest to prawdopodobnie wskaźnik tylko do odczytu lub ustawienie, które powinno być zazwyczaj pozostawione w wartości domyślnej, chyba że wsparcie zaleci inaczej.
    -   **Zalecana wartość:** Pozostaw jako domyślne.
    -   **Scenariusz/przykład dla sprzedawcy:** Nie przewiduje się bezpośredniej interakcji sprzedawcy.
-   **Selektory CSS dla elementów koszyka** (Klucze konfiguracji: `COPPRO_CSS_CART_TOTAL`, `COPPRO_CSS_CART_SUBTOTAL`, `COPPRO_CSS_CART_SHIPPING`)

    -   **Co robią te ustawienia:** Te pola pozwalają określić selektory CSS dla elementów całkowitej kwoty koszyka, podsumy i kosztów wysyłki Twojego szablonu. Jest to kluczowe dla modułu, aby poprawnie aktualizować te wartości, gdy zastosowana jest opłata/rabat, zwłaszcza jeśli Twój szablon używa niestandardowych selektorów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy poprawnie skonfigurowane:* Moduł dokładnie zaktualizuje wyświetlane całkowite kwoty koszyka, podsumy i koszty wysyłki na stronie realizacji zamówienia, aby odzwierciedlić opłatę/rabat.
        -   *Gdy niepoprawnie skonfigurowane lub pozostawione puste:* Całkowite kwoty koszyka mogą nie aktualizować się poprawnie, co prowadzi do zamieszania klienta lub niepoprawnych wyświetlanych cen.
    -   **Zalecana wartość:** Początkowo pozostaw puste. Jeśli zauważysz, że całkowite kwoty koszyka nie aktualizują się poprawnie po wybraniu „Płatności gotówką przy odbiorze w sklepie”, może być konieczne skonsultowanie się z deweloperem Twojego szablonu lub webmasterem, aby znaleźć poprawne selektory CSS.
    -   **Scenariusz/przykład dla sprzedawcy:** Po zainstalowaniu modułu zauważasz, że całkowita cena nie zmienia się na stronie realizacji zamówienia, gdy zastosowana jest opłata za odbiór. Twój webmaster sprawdzi kod Twojego szablonu, aby znaleźć poprawne selektory CSS (np. `#cart-total-price`, `.product-total-price`) i wprowadzi je tutaj.

#### **Zasady wykluczeń**

-   **Wyklucz produkty** (Klucz konfiguracji: `COPPRO_EXCL_PRODUCTS`)

    -   **Co robi to ustawienie:** Pozwala zapobiec zakupowi określonych produktów za pomocą metody płatności „Płatność gotówką przy odbiorze w sklepie”. Jeśli jakikolwiek wykluczony produkt znajduje się w koszyku, ta metoda płatności nie będzie dostępna.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy produkty są wybrane:* Jeśli klient doda jeden z tych produktów do koszyka, opcja „Płatność gotówką przy odbiorze w sklepie” zniknie z metod płatności.
        -   *Gdy żadne produkty nie są wybrane:* Wszystkie produkty są kwalifikowalne.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne produkty, których nie można odebrać ani zapłacić gotówką.
    -   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz bardzo wartościowe przedmioty (np. drogą biżuterię), za które wolisz akceptować tylko bezpieczne płatności online. Dodasz te produkty do listy wykluczeń.
-   **Wyklucz kategorie** (Klucz konfiguracji: `COPPRO_EXCL_CAT`)

    -   **Co robi to ustawienie:** Podobnie jak wykluczanie produktów, pozwala to zapobiec zakupowi całych kategorii produktów za pomocą „Płatności gotówką przy odbiorze w sklepie”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy kategorie są wybrane:* Jeśli klient doda jakikolwiek produkt z tych kategorii do koszyka, opcja „Płatność gotówką przy odbiorze w sklepie” nie będzie dostępna.
        -   *Gdy żadne kategorie nie są wybrane:* Wszystkie kategorie są kwalifikowalne.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne kategorie, które nie nadają się do odbioru.
    -   **Scenariusz/przykład dla sprzedawcy:** Masz kategorię „Pobrane pliki cyfrowe”. Ponieważ te przedmioty nie wymagają fizycznego odbioru, wykluczyłbyś tę kategorię.
-   **Włącz wykluczenia** (Klucz konfiguracji: `COPPRO_EXCL_ENABLE`)

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania wszystkich ustawionych reguł wykluczeń produktów i kategorii.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Twoje reguły wykluczeń produktów i kategorii będą aktywne.
        -   *Gdy wyłączony:* Wszystkie produkty i kategorie będą kwalifikowalne do „Płatności gotówką przy odbiorze w sklepie”, niezależnie od tego, co wybrałeś na listach wykluczeń.
    -   **Zalecana wartość:** Włączony, jeśli zdefiniowałeś jakiekolwiek reguły wykluczeń.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustawiłeś wykluczenia dla niektórych produktów i chcesz, aby te reguły były aktywne, więc włączasz ten przełącznik.

#### **Ustawienia analityczne i wewnętrzne**

-   **Ustawienia analityczne** (Klucze konfiguracji: `COPPRO_ANALYTICS_DEFAULT_CHART`, `COPPRO_ANALYTICS_PERIOD`, `COPPRO_ANALYTICS_IMPACT_DAYS`, `COPPRO_ANALYTICS_CHART_WEEKS`, `COPPRO_ANALYTICS_CHART_MONTHS`, `COPPRO_ANALYTICS_CHART_YEARS`)

    -   **Co robią te ustawienia:** Są to wewnętrzne ustawienia związane z wszelkimi funkcjami analitycznymi lub raportowania, które moduł może posiadać, pozwalające skonfigurować sposób zbierania lub wyświetlania danych do użytku wewnętrznego.
    -   **Efekt zmiany tego ustawienia:** Zazwyczaj wpływają one tylko na widoki raportowania w Panelu administracyjnym, a nie na doświadczenie klienta w front-office.
    -   **Zalecana wartość:** Pozostaw jako domyślne, chyba że masz konkretne potrzeby raportowania.
    -   **Scenariusz/przykład dla sprzedawcy:** Nie przewiduje się bezpośredniej interakcji sprzedawcy w codziennych operacjach.
-   **Data zmiany opłaty / migawka** (Klucze konfiguracji: `COPPRO_FEE_CHANGE_DATE`, `COPPRO_FEE_CHANGE_SNAPSHOT`)

    -   **Co robią te ustawienia:** Są to prawdopodobnie wewnętrzne ustawienia modułu do śledzenia, kiedy konfiguracje opłat były ostatnio zmieniane lub do przechowywania migawki poprzednich ustawień opłat. Służy to zazwyczaj do celów audytu lub debugowania.
    -   **Efekt zmiany tego ustawienia:** Brak bezpośredniego wpływu na doświadczenie klienta.
    -   **Zalecana wartość:** Pozostaw jako domyślne.
    -   **Scenariusz/przykład dla sprzedawcy:** Nie przewiduje się bezpośredniej interakcji sprzedawcy.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie wydaje się posiadać dedykowanych niestandardowych kontrolerów administracyjnych poza główną stroną konfiguracji. Wszystkie ustawienia są zarządzane za pomocą metody `getContent()` głównego pliku modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Logo płatności | Prześlij odpowiedni obraz | Wizualna identyfikacja metody płatności. |
| Konfiguracja modułu | Tytuł metody płatności | „Płatność gotówką przy odbiorze w sklepie” | Nazwa wyświetlana klientom dla opcji płatności. |
| Konfiguracja modułu | Status zamówienia dla nowych zamówień | Niestandardowy „Oczekiwanie na płatność gotówką przy odbiorze” | Początkowy status dla zamówień korzystających z tej metody. |
| Konfiguracja modułu | Status zamówienia po opłaceniu | „Płatność zaakceptowana” / „Dostarczono” | Końcowy status po opłaceniu i odbiorze przez klienta. |
| Konfiguracja modułu | Minimalna wartość koszyka | Puste / 0 | Minimalna wartość zamówienia, aby ta metoda płatności się pojawiła. |
| Konfiguracja modułu | Maksymalna wartość koszyka | Puste / 0 | Maksymalna wartość zamówienia, aby ta metoda płatności się pojawiła. |
| Konfiguracja modułu | Zastosuj rabat (nie opłatę) | Wyłączony | Określa, czy zastosowany jest rabat, czy opłata. |
| Konfiguracja modułu | Wartość opłaty przy metodzie płatności | Włączony | Wyświetla opłatę/rabat obok nazwy metody płatności. |
| Konfiguracja modułu | Opłata procentowa | Wyłączony | Stosuje opłatę/rabat procentowy. |
| Konfiguracja modułu | Wartość opłaty procentowej | 0 | Wartość procentowa opłaty/rabatu. |
| Konfiguracja modułu | Opłata stała | Włączony (z wartością) | Stosuje opłatę/rabat o stałej kwocie. |
| Konfiguracja modułu | Wartość opłaty stałej | np. 2.00 | Stała kwota opłaty/rabatu. |
| Konfiguracja modułu | Podsumowanie koszyka | Włączony | Pokazuje opłatę/rabat wyszczególniony w podsumowaniu koszyka. |
| Konfiguracja modułu | Podsumowanie adresu | Włączony | Pokazuje opłatę/rabat w podsumowaniu adresu. |
| Konfiguracja modułu | Włączony | Włączony | Aktywuje/dezaktywuje metodę płatności. |
| Konfiguracja modułu | Wyklucz produkty | Puste | Zapobiega używaniu tej metody przez określone produkty. |
| Konfiguracja modułu | Wyklucz kategorie | Puste | Zapobiega używaniu tej metody przez produkty z określonych kategorii. |
| Konfiguracja modułu | Włącz wykluczenia | Włączony (jeśli ustawiono reguły) | Główny przełącznik dla reguł wykluczeń produktów/kategorii. |
| Konfiguracja modułu | Selektory CSS (Całkowita kwota koszyka, Podsumowanie, Wysyłka) | Puste (dostosuj w razie potrzeby) | Zapewnia poprawne aktualizacje całkowitej kwoty koszyka z szablonem. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Metoda płatności „Płatność gotówką przy odbiorze w sklepie” nie pojawia się podczas realizacji zamówienia.**
O:

-   **Sprawdź ustawienie „Włączony”:** Przejdź do Moduły > Menedżer modułów > Konfiguruj dla „Płatność gotówką przy odbiorze w sklepie (+opłata)” i upewnij się, że główny przełącznik „Włączony” jest włączony.
-   **Sprawdź ograniczenia wartości koszyka:** Zweryfikuj ustawienia „Minimalna wartość koszyka” i „Maksymalna wartość koszyka”. Jeśli całkowita wartość koszyka klienta wykracza poza ten zakres, metoda się nie pojawi.
-   **Sprawdź wykluczenia:** Jeśli ustawiłeś wykluczenia produktów lub kategorii, upewnij się, że aktualny koszyk nie zawiera żadnych wykluczonych pozycji. Sprawdź również, czy „Włącz wykluczenia” jest włączone.
-   **Sprawdź ograniczenia geograficzne:** Upewnij się, że metoda płatności nie jest ograniczona przez kraj lub walutę w ogólnych ustawieniach płatności PrestaShop (Płatność > Preferencje).
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P2: Opłata/rabat nie jest stosowany lub wyświetlany poprawnie na stronie realizacji zamówienia.**
O:

-   **Zweryfikuj ustawienia opłat/rabatów:** Dokładnie sprawdź, czy „Opłata procentowa” lub „Opłata stała” jest włączona, a odpowiednia wartość jest poprawnie wprowadzona. Upewnij się również, że „Zastosuj rabat (nie opłatę)” jest ustawione zgodnie z zamierzeniem.
-   **Sprawdź ustawienia wyświetlania:** Upewnij się, że „Wartość opłaty przy metodzie płatności”, „Podsumowanie koszyka” i „Podsumowanie adresu” są włączone dla maksymalnej widoczności.
-   **Selektory CSS (Zaawansowane):** Jeśli Twój szablon jest mocno dostosowany, moduł może nie być w stanie znaleźć poprawnych elementów do aktualizacji. Sprawdź ustawienia „Selektory CSS dla elementów koszyka”. Może być konieczne, aby webmaster zidentyfikował poprawne selektory dla całkowitej kwoty koszyka, podsumy i elementów wysyłki Twojego szablonu.

**P3: Jak zmienić tekst „Płatność gotówką przy odbiorze w sklepie” na coś innego?**
O:

-   Możesz zmienić nazwę wyświetlaną bezpośrednio w konfiguracji modułu. Poszukaj ustawienia „Tytuł metody płatności” na głównej stronie konfiguracji.
-   W przypadku sklepów wielojęzycznych upewnij się, że wybrałeś poprawny język z rozwijanej listy u góry strony konfiguracji modułu (jeśli dostępna) lub użyj narzędzia tłumaczeń PrestaShop (Lokalizacja > Tłumaczenia > Tłumaczenia zainstalowanych modułów).

**P4: Czy mogę ograniczyć tę metodę płatności tylko do niektórych przewoźników lub grup klientów?**
O:

-   **Przewoźnicy:** Tak, podstawowe preferencje płatności PrestaShop pozwalają ograniczyć metody płatności według przewoźnika. Przejdź do **Płatność > Preferencje** w swoim Panelu administracyjnym. W sekcji „Ograniczenia przewoźników” upewnij się, że „Płatność gotówką przy odbiorze w sklepie (+opłata)” jest wybrana dla przewoźników, z którymi chcesz ją zezwolić (np. Twój przewoźnik „Odbiór lokalny”).
-   **Grupy klientów:** Podobnie, w **Płatność > Preferencje**, możesz ograniczyć metody płatności według grupy klientów. Upewnij się, że odpowiednie grupy klientów (np. „Klient”, „Gość”) są wybrane dla tej metody płatności.

**P5: Jaki status zamówienia powinienem używać dla zamówień „Płatność gotówką przy odbiorze”?**
O:

-   Zdecydowanie zaleca się utworzenie niestandardowego statusu zamówienia w PrestaShop (Zamówienia > Statusy zamówień) specjalnie dla zamówień „Płatność gotówką przy odbiorze”, takich jak „Oczekiwanie na płatność gotówką przy odbiorze” lub „Gotowe do odbioru”. Pomaga to łatwo identyfikować te zamówienia w Twoim Panelu administracyjnym.
-   Następnie, w konfiguracji modułu, ustaw „Status zamówienia dla nowych zamówień” na ten niestandardowy status.
-   Gdy klient zapłaci i odbierze, ręcznie zmień status zamówienia na „Płatność zaakceptowana” lub „Dostarczono” na stronie szczegółów zamówienia.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Cash on pickup at store (+fee)` (`coppro`) to standardowy moduł płatności PrestaShop zgodny z wzorcem MVC. Rozszerza `PaymentModule` i integruje się głównie poprzez hooki, aby wyświetlać opcje płatności, przetwarzać walidację i wyświetlać informacje o zamówieniu. Moduł dynamicznie oblicza opłaty/rabaty na podstawie konfiguracji i aktualizuje sumy koszyka za pomocą JavaScript w front-office podczas realizacji zamówienia. Wykorzystuje `Configuration` do przechowywania ustawień i nie wprowadza niestandardowych klas `ObjectModel` ani tabel bazy danych.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/index.php`
        -   Nazwa klasy: `CopproIndexModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
        -   Odpowiedzialność: Ten kontroler może służyć jako domyślny punkt wejścia lub obsługiwać ogólne żądania front-office związane z modułem, które nie pasują do konkretnych przepływów płatności. Biorąc pod uwagę jego nazwę, może to być rezerwowy lub prosty kontroler wyświetlania.
    -   `controllers/front/store.php`
        -   Nazwa klasy: `CopproStoreModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
        -   Odpowiedzialność: Potencjalnie obsługuje logikę związaną z lokalizacjami sklepów lub punktami odbioru, chociaż opis modułu nie wspomina wyraźnie o wielu lokalizacjach sklepów. Może to być placeholder lub do przyszłej rozbudowy.
    -   `controllers/front/validation.php`
        -   Nazwa klasy: `CopproValidationModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
        -   Odpowiedzialność: Jest to krytyczny kontroler do przetwarzania płatności. Odbiera potwierdzenie płatności z procesu realizacji zamówienia, waliduje zamówienie i przekierowuje klienta na stronę potwierdzenia zamówienia. Współpracuje z głównym modułem `coppro.php`, aby sfinalizować zamówienie z poprawnym statusem i zastosowanymi opłatami/rabatami.
-   **Kontrolery administracyjne Back-Office**:

    -   Ten moduł nie zawiera żadnych niestandardowych kontrolerów administracyjnych. Cała konfiguracja Back Office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu `coppro.php`.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie wydaje się definiować żadnych niestandardowych klas w katalogu `classes/`. Jego podstawowa logika znajduje się w głównym pliku modułu `coppro.php`, który rozszerza `PaymentModule`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `coppro/lib/searchTool/views/js/autocomplete.js`
    -   Zakres: Prawdopodobnie Back-office.
    -   Odpowiedzialność: Zapewnia funkcjonalność autouzupełniania, prawdopodobnie dla wyboru produktów lub kategorii w konfiguracji modułu (np. dla list wykluczeń). Wiąże się z polami wejściowymi i wykonuje żądania AJAX w celu pobrania sugestii.
-   `coppro/views/js/adminCopproDashboard.js`
    -   Zakres: Back-office.
    -   Odpowiedzialność: Zarządza JavaScriptem dla wszelkich funkcji panelu administracyjnego lub analitycznych w ramach strony konfiguracji modułu. Może obsługiwać renderowanie wykresów lub wyświetlanie danych.
-   `coppro/views/js/adminCopproProductSearch.js`
    -   Zakres: Back-office.
    -   Odpowiedzialność: Specjalnie obsługuje interfejs wyszukiwania produktów w konfiguracji administracyjnej modułu, prawdopodobnie dla ustawienia „Wyklucz produkty”. Zarządza wprowadzaniem wyszukiwania, wyświetlaniem wyników i wyborem.
-   `coppro/views/js/adminCopproSelector.js`
    -   Zakres: Back-office.
    -   Odpowiedzialność: Zarządza logiką wyboru dla różnych elementów w panelu administracyjnym, prawdopodobnie dla kategorii lub innych list konfigurowalnych.
-   `coppro/views/js/coppro-checkout.js`
    -   Zakres: Front-office.
    -   Odpowiedzialność: Jest to główny skrypt front-office. Nasłuchuje zmian w wyborze metody płatności podczas realizacji zamówienia. Gdy wybrano „Płatność gotówką przy odbiorze w sklepie”, dynamicznie aktualizuje podsumowanie koszyka (suma, podsumowanie, wysyłka), aby odzwierciedlić obliczoną opłatę lub rabat. Wykorzystuje selektory CSS zdefiniowane w konfiguracji modułu (`COPPRO_CSS_CART_TOTAL` itd.) do celowania i modyfikowania elementów DOM. Może również obsługiwać wywołania AJAX w celu ponownego obliczenia sum, jeśli potrzebny jest backend.
-   `coppro/views/js/copproBoMockConsole.js`
    -   Zakres: Back-office.
    -   Odpowiedzialność: Prawdopodobnie narzędzie do debugowania lub rozwoju, być może do symulacji wyjścia konsoli lub logowania w Back Office.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `coppro/lib/searchTool/views/css/autocomplete.css`
    -   Zakres: Back-office.
    -   Odpowiedzialność: Stylizuje rozwijane listy autouzupełniania i pola wprowadzania wyszukiwania używane w konfiguracji administracyjnej.
-   `coppro/views/css/admin_coppro.css`
    -   Zakres: Stylizacja formularzy administracyjnych Back-office.
    -   Odpowiedzialność: Zapewnia specyficzną stylizację dla strony konfiguracji modułu w Panelu administracyjnym PrestaShop, zapewniając spójny i przyjazny dla użytkownika interfejs.
-   `coppro/views/css/coppro.css`
    -   Zakres: Stylizacja klienta Front-office.
    -   Odpowiedzialność: Zawiera style dla wyświetlania opcji płatności „Płatność gotówką przy odbiorze w sklepie”, potencjalnie dla logo płatności, tekstu opłaty/rabatu lub wszelkich niestandardowych elementów wprowadzonych przez moduł na stronie realizacji zamówienia. Deweloperzy mogą nadpisać te style w pliku `custom.css` swojego szablonu lub w szablonie potomnym.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `coppro/views/templates/hook/confirmation.tpl`
        -   Hook: Prawdopodobnie `displayPaymentReturn` lub podobny.
        -   Wyjście: Treść dla strony potwierdzenia zamówienia po pomyślnym zamówieniu „Płatność gotówką przy odbiorze”, informująca klienta o płatności przy odbiorze.
    -   `coppro/views/templates/hook/displayAdminOrder16.tpl`
        -   Hook: `displayAdminOrder` (dla PrestaShop 1.6.x).
        -   Wyjście: Dodatkowe informacje lub działania związane z zamówieniami „Płatność gotówką przy odbiorze” na stronie szczegółów zamówienia w Back Office dla PS 1.6.
    -   `coppro/views/templates/hook/displayAdminOrder17.tpl`
        -   Hook: `displayAdminOrder` (dla PrestaShop 1.7.x, 8.x, 9.x).
        -   Wyjście: Podobnie jak `displayAdminOrder16.tpl`, ale dostosowane do strony szczegółów zamówienia w Back Office PS 1.7+, potencjalnie pokazujące instrukcje odbioru lub szczegóły opłat.
    -   `coppro/views/templates/hook/displayOrderDetail.tpl`
        -   Hook: `displayOrderDetail`.
        -   Wyjście: Informacje o metodzie płatności „Płatność gotówką przy odbiorze” na stronie szczegółów zamówienia klienta w front-office.
    -   `coppro/views/templates/hook/payment.tpl`
        -   Hook: `paymentOptions` (lub `displayPaymentOptions`).
        -   Wyjście: Struktura HTML dla opcji płatności „Płatność gotówką przy odbiorze w sklepie” na stronie realizacji zamówienia, w tym logo płatności, tytuł i dynamicznie obliczony tekst opłaty/rabatu.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `coppro/lib/searchTool/views/scripts.tpl`
        -   Hook: Prawdopodobnie `actionAdminControllerSetMedia` lub włączony bezpośrednio w `getContent()`.
        -   Wyjście: Zawiera zasoby JavaScript i CSS dla narzędzia wyszukiwania używanego w konfiguracji administracyjnej.
    -   `coppro/views/templates/admin/productSearchTool.tpl`
        -   Wyjście: Struktura HTML dla interfejsu wyszukiwania i wyboru produktów w konfiguracji modułu, używana dla ustawienia „Wyklucz produkty”.
    -   `coppro/views/templates/admin/scopeSelector.tpl`
        -   Wyjście: HTML dla ogólnego selektora zakresu, potencjalnie używanego dla kategorii lub innych list filtrowalnych w konfiguracji administracyjnej.
-   **Szablony Front-office (`views/templates/front/`)**:

    -   `coppro/views/templates/front/validation.tpl`
        -   Wyjście: Treść wyświetlana przez `CopproValidationModuleFrontController` po walidacji płatności, zazwyczaj przekierowanie lub prosta wiadomość przed ostateczną stroną potwierdzenia.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy niestandardowych tabel bazy danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` za pomocą metod `Configuration::updateValue()` i `Configuration::get()`, z kluczami poprzedzonymi `COPPRO_`.
    Przykładowe klucze konfiguracji:

    -   `COPPRO_OS`
    -   `COPPRO_OS_READY`
    -   `COPPRO_MAXCART_V`
    -   `COPPRO_MINCART_V`
    -   `COPPRO_FEEPAY`
    -   `COPPRO_DISCOUNT`
    -   `COPPRO_CHARGEP_V`
    -   `COPPRO_CHARGEA_V`
    -   `COPPRO_EXCL_PRODUCTS`
    -   `COPPRO_EXCL_CAT`
    -   `COPPRO_TITLE`
    -   `COPPRO_CARTPRESENTER`
    -   `COPPRO_HOWFEE`
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Aby dołączyć zasoby CSS (`coppro.css`) i JavaScript (`coppro-checkout.js`) front-office. |
| `displayPaymentOptions` | Podczas realizacji zamówienia, aby wyświetlić dostępne metody płatności. | Aby wyświetlić opcję płatności „Płatność gotówką przy odbiorze w sklepie” z jej tytułem, logo i obliczoną opłatą/rabatem. |
| `paymentOptions` | Alias dla `displayPaymentOptions` (starsze wersje PS). | Tak samo jak `displayPaymentOptions`. |
| `displayPaymentReturn` | Na stronie potwierdzenia zamówienia po płatności. | Aby wyświetlić szczegółowe instrukcje lub komunikaty potwierdzające dla zamówień „Płatność gotówką przy odbiorze”. |
| `displayPDFInvoice` | Gdy generowana jest faktura PDF. | Aby upewnić się, że metoda płatności „Płatność gotówką przy odbiorze w sklepie” jest poprawnie podana na fakturze. |
| `displayOrderDetail` | Na stronie szczegółów zamówienia klienta w front-office. | Aby wyświetlić wybraną metodę płatności i wszelkie związane z nią szczegóły. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w Back Office. | Aby wyświetlić dodatkowe informacje lub narzędzia zarządzania specyficzne dla zamówień „Płatność gotówką przy odbiorze” dla administratorów. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ładuje swoje zasoby multimedialne. | Aby dołączyć zasoby CSS (`admin_coppro.css`, `autocomplete.css`) i JavaScript (`adminCopproDashboard.js`, `adminCopproProductSearch.js`, `adminCopproSelector.js`, `autocomplete.js`) Back-office dla strony konfiguracji modułu. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Aby wykonać wszelkie działania po walidacji, takie jak aktualizacja statusu zamówienia lub logowanie szczegółów, specyficzne dla zamówień „Płatność gotówką przy odbiorze”. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie techniczne, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w wszelkich problemach lub pytaniach dotyczących modułu „Płatność gotówką przy odbiorze w sklepie (+opłata)”.
