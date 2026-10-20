---
title: "Płatność za pobraniem z opłatą - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Płatność za pobraniem z opłatą” od MyPresta.eu."
sidebar:
  label: "Płatność za pobraniem z opłatą - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cash on delivery with fee na MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-fee.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/cash-on-delivery-with-fee/)
>
> ---


# Płatność za pobraniem z opłatą

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Płatność za pobraniem z opłatą”, dostępny bezpośrednio po instalacji lub poprzez nawigację do **Moduły > Menedżer modułów**, wyszukanie „Płatność za pobraniem z opłatą” i kliknięcie „Konfiguruj”.

#### **Ustawienia ogólne**

- **Wyłącz \ / Włącz / Wyłącz (Główny status modułu)**

  - **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej metody płatności za pobraniem z opłatą w Twoim sklepie.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Opcja płatności za pobraniem, wraz ze skonfigurowanymi opłatami, będzie dostępna dla klientów podczas realizacji zamówienia.
    - *Gdy wyłączone:* Opcja płatności za pobraniem nie będzie wyświetlana klientom, niezależnie od innych ustawień.
  - **Zalecana wartość:** `Włączone`, jeśli zamierzasz oferować płatność za pobraniem.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz przestać oferować płatność za pobraniem, ustaw to na `Wyłączone`.
- **Wartość (Wartość opłaty za pobraniem)**

  - **Co robi to ustawienie:** To pole określa podstawową kwotę lub procent opłaty za pobraniem. Dokładna interpretacja (stała kwota lub procent) zależy od ustawienia „Jak uwzględnić opłatę?” poniżej.
  - **Wpływ zmiany tego ustawienia:** Bezpośrednio zmienia koszt dodawany do zamówień za pobraniem.
  - **Zalecana wartość:** Zacznij od `0.00` i dostosuj na podstawie opłat przewoźnika.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój przewoźnik pobiera 2,50 € za płatność za pobraniem, możesz wpisać `2.50`. Jeśli pobiera 1% zamówienia, możesz wpisać `1`.
- **Jak uwzględnić opłatę?**

  - **Co robi to ustawienie:** Definiuje, w jaki sposób „Wartość” (z poprzedniego ustawienia) jest stosowana do całkowitej wartości zamówienia.
  - **Wpływ zmiany tego ustawienia:**
    - *Uwzględnij w kosztach wysyłki:* Opłata za pobraniem jest dodawana do kosztów wysyłki wyświetlanych klientowi. Może to uprościć wyświetlanie w koszyku poprzez połączenie opłat.
    - *Uwzględnij jako oddzielny produkt/usługę:* Opłata za pobraniem pojawia się jako oddzielna pozycja w podsumowaniu koszyka i na fakturze, często oznaczona jako „Opłata za pobraniem” lub podobnie. Zapewnia to maksymalną przejrzystość.
  - **Zalecana wartość:** `Uwzględnij jako oddzielny produkt/usługę` dla przejrzystości i zgodności z przepisami.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klienci wyraźnie widzieli opłatę za pobraniem jako oddzielną pozycję, wybierz „Uwzględnij jako oddzielny produkt/usługę”. Jeśli wolisz czystszy, połączony koszt wysyłki, wybierz „Uwzględnij w kosztach wysyłki”.
- **Status zamówienia po zakupie z modułem COD**

  - **Co robi to ustawienie:** Określa początkowy status zamówienia złożonego za pomocą metody płatności za pobraniem.
  - **Wpływ zmiany tego ustawienia:** Określa, jak zamówienia za pobraniem pojawiają się w Twoim Panelu administracyjnym natychmiast po ich złożeniu.
  - **Zalecana wartość:** `Płatność zaakceptowana` (lub podobny status „oczekujące na płatność”, który skonfigurowałeś). Pozwala to odróżnić zamówienia za pobraniem, które są potwierdzone, ale jeszcze fizycznie nieopłacone.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz ustawić to na „Oczekuje na płatność za pobraniem” (jeśli utworzyłeś taki status), aby łatwo filtrować i zarządzać zamówieniami za pobraniem, które oczekują na fizyczną płatność przy dostawie.
- **Pokaż dodatkowe podsumowanie przed potwierdzeniem**

  - **Co robi to ustawienie:** Kontroluje, czy dodatkowy blok podsumowania jest wyświetlany na ostatnim kroku realizacji zamówienia, tuż przed potwierdzeniem zamówienia przez klienta.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Zostanie wyświetlone szczegółowe zestawienie zawierające całkowitą wartość koszyka, wysyłkę i opłatę za pobraniem.
    - *Gdy wyłączone:* Zostanie użyte standardowe podsumowanie PrestaShop, które może nie wyszczególniać opłaty za pobraniem jako oddzielnej pozycji.
  - **Zalecana wartość:** `Włączone` dla maksymalnej przejrzystości i zgodności z przepisami.
  - **Scenariusz / przykład dla sprzedawcy:** Aby upewnić się, że klienci są w pełni świadomi wszystkich opłat przed złożeniem zamówienia, zwłaszcza opłaty za pobraniem, włącz tę opcję.
- **Podsumowanie koszyka / Podsumowanie adresu / Minimalna wartość całkowita koszyka (Selektory CSS)**

  - **Co robi to ustawienie:** Te pola pozwalają określić selektory CSS dla różnych elementów na stronie realizacji zamówienia. Moduł używa tych selektorów do prawidłowego wstrzykiwania informacji o opłacie za pobraniem do podsumowania realizacji zamówienia Twojego motywu.
  - **Wpływ zmiany tego ustawienia:** Jeśli Twój motyw używa niestandardowych klas CSS dla tych elementów, dostosowanie tych selektorów zapewnia prawidłowe wyświetlanie opłaty za pobraniem. Nieprawidłowe wartości mogą prowadzić do tego, że opłata nie pojawi się lub pojawi się w niewłaściwym miejscu.
  - **Zalecana wartość:** Pozostaw puste dla automatycznego wykrywania lub użyj wartości domyślnych dostarczonych przez moduł. Zmieniaj tylko wtedy, gdy wyświetlanie opłaty za pobraniem jest uszkodzone w Twoim niestandardowym motywie.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli zainstalowałeś niestandardowy motyw i opłata za pobraniem nie pojawia się w podsumowaniu koszyka, Twój programista internetowy może potrzebować sprawdzić kod HTML Twojego motywu i zaktualizować te selektory, aby pasowały do struktury Twojego motywu.

#### **Obliczanie opłat i warunki**

- **Wyłącz \ / Włącz / Wyłącz (Warunek maksymalnej wartości koszyka)**

  - **Co robi to ustawienie:** Włącza lub wyłącza warunek, w którym metoda płatności za pobraniem jest dostępna tylko wtedy, gdy całkowita wartość koszyka jest *poniżej* określonej maksymalnej wartości.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Klienci z koszykami przekraczającymi określoną maksymalną wartość nie zobaczą płatności za pobraniem jako opcji płatności.
    - *Gdy wyłączone:* Nie ma ograniczenia maksymalnej wartości koszyka dla płatności za pobraniem.
  - **Zalecana wartość:** `Wyłączone`, chyba że masz konkretne powody, aby ograniczyć zamówienia za pobraniem o wysokiej wartości.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli miałeś problemy z oszukańczymi lub nieodebranymi zamówieniami za pobraniem o wysokiej wartości, możesz to włączyć i ustawić `CODPRO_MOD_MAXCART_V` na 500 €, aby zmniejszyć ryzyko.
- **CODPRO\_MOD\_MAXCART\_V (Maksymalna wartość koszyka)**

  - **Co robi to ustawienie:** Konkretna wartość pieniężna dla warunku maksymalnej wartości koszyka.
  - **Wpływ zmiany tego ustawienia:** Definiuje górny limit kwalifikowalności do płatności za pobraniem.
  - **Zalecana wartość:** Ustaw wartość zgodną z Twoją tolerancją ryzyka dla zamówień za pobraniem.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli `Wyłącz \ / Włącz / Wyłącz (Warunek maksymalnej wartości koszyka)` jest włączone, a Ty ustawisz to na `500.00`, klienci z zamówieniami powyżej 500 € nie mogą korzystać z płatności za pobraniem.
- **Wyłącz \ / Włącz / Wyłącz (Warunek minimalnej wartości koszyka)**

  - **Co robi to ustawienie:** Włącza lub wyłącza warunek, w którym metoda płatności za pobraniem jest dostępna tylko wtedy, gdy całkowita wartość koszyka jest *powyżej* określonej minimalnej wartości.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Klienci z koszykami poniżej określonej minimalnej wartości nie zobaczą płatności za pobraniem jako opcji płatności.
    - *Gdy wyłączone:* Nie ma ograniczenia minimalnej wartości koszyka dla płatności za pobraniem.
  - **Zalecana wartość:** `Wyłączone`, chyba że masz konkretne powody, aby unikać bardzo małych zamówień za pobraniem.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli stała opłata za pobraniem sprawia, że bardzo małe zamówienia są nieopłacalne, możesz to włączyć i ustawić `CODPRO_MOD_MINCART_V` na 10 €.
- **CODPRO\_MOD\_MINCART\_V (Minimalna wartość koszyka)**

  - **Co robi to ustawienie:** Konkretna wartość pieniężna dla warunku minimalnej wartości koszyka.
  - **Wpływ zmiany tego ustawienia:** Definiuje dolny limit kwalifikowalności do płatności za pobraniem.
  - **Zalecana wartość:** Ustaw wartość, która sprawia, że płatność za pobraniem jest dla Ciebie opłacalna.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli `Wyłącz \ / Włącz / Wyłącz (Warunek minimalnej wartości koszyka)` jest włączone, a Ty ustawisz to na `10.00`, klienci z zamówieniami poniżej 10 € nie mogą korzystać z płatności za pobraniem.
- **CODPRO\_CHARGEP\_V (Wartość opłaty procentowej)**

  - **Co robi to ustawienie:** To pole definiuje wartość procentową opłaty za pobraniem.
  - **Wpływ zmiany tego ustawienia:** Jeśli „Jak uwzględnić opłatę?” jest ustawione na opcję opartą na procencie, ta wartość zostanie użyta do obliczenia opłaty.
  - **Zalecana wartość:** Początkowo `0.00`, dostosuj na podstawie procentowej opłaty przewoźnika.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój przewoźnik pobiera 1,5% wartości zamówienia za płatność za pobraniem, wpisz tutaj `1.5`.
- **CODPRO\_PERCENTAGE\_TYPE (Podstawa obliczania procentu)**

  - **Co robi to ustawienie:** Określa, *na czym* obliczana jest opłata procentowa.
  - **Wpływ zmiany tego ustawienia:**
    - *Całkowita wartość koszyka (z wysyłką):* Procent jest obliczany od całkowitej kwoty, wliczając produkty i wysyłkę.
    - *Całkowita wartość koszyka (bez wysyłki):* Procent jest obliczany tylko od sumy produktów.
  - **Zalecana wartość:** `Całkowita wartość koszyka (z wysyłką)`, ponieważ tak zazwyczaj przewoźnicy obliczają swoje opłaty za pobraniem.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój przewoźnik pobiera 1% od *całej* kwoty, którą pobiera od klienta (produkty + wysyłka), wybierz „Całkowita wartość koszyka (z wysyłką)”.
- **CODPRO\_CHARGEA\_V (Wartość opłaty stałej kwoty)**

  - **Co robi to ustawienie:** To pole definiuje stałą kwotę opłaty za pobraniem.
  - **Wpływ zmiany tego ustawienia:** Jeśli „Jak uwzględnić opłatę?” jest ustawione na opcję stałej kwoty, ta wartość zostanie użyta.
  - **Zalecana wartość:** Początkowo `0.00`, dostosuj na podstawie stałej opłaty przewoźnika.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój przewoźnik pobiera stałe 3,00 € za płatność za pobraniem, wpisz tutaj `3.00`.
- **CODPRO\_MIN\_CHARGEV (Minimalna opłata za opłatę procentową)**

  - **Co robi to ustawienie:** Jeśli używasz opłaty procentowej, ustawia to minimalną stałą kwotę, jaką będzie wynosić opłata za pobraniem, nawet jeśli obliczony procent jest niższy.
  - **Wpływ zmiany tego ustawienia:** Zapewnia, że zawsze odzyskasz co najmniej określoną kwotę za płatność za pobraniem, zwłaszcza w przypadku małych zamówień, gdzie procent może być bardzo niski.
  - **Zalecana wartość:** `0.00` (bez minimum) lub niewielka kwota, taka jak `1.00` lub `2.00`, jeśli masz minimalny koszt.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja opłata procentowa wynosi 1%, a zamówienie o wartości 50 € skutkowałoby opłatą 0,50 €, ale chcesz zapewnić minimum 1,50 €, ustaw to na `1.50`.
- **CODPRO\_MAX\_CHARGEV (Maksymalna opłata za opłatę procentową)**

  - **Co robi to ustawienie:** Jeśli używasz opłaty procentowej, ustawia to maksymalną stałą kwotę, jaką będzie wynosić opłata za pobraniem, nawet jeśli obliczony procent jest wyższy.
  - **Wpływ zmiany tego ustawienia:** Zapobiega nadmiernemu wzrostowi opłaty za pobraniem w przypadku bardzo dużych zamówień.
  - **Zalecana wartość:** `0.00` (bez maksimum) lub rozsądny limit, taki jak `10.00` lub `15.00`.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja opłata procentowa wynosi 1%, a zamówienie o wartości 2000 € skutkowałoby opłatą 20 €, ale chcesz ograniczyć opłatę za pobraniem do 10 €, ustaw to na `10.00`.
- **CODPRO\_FEETAX (Zastosuj podatek do opłaty)**

  - **Co robi to ustawienie:** Określa, czy sama opłata za pobraniem powinna podlegać VAT/podatkom.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Do opłaty za pobraniem zostanie zastosowany podatek zgodnie z wybraną regułą podatkową.
    - *Gdy wyłączone:* Opłata za pobraniem będzie traktowana jako zwolniona z podatku.
  - **Zalecana wartość:** `Włączone`, jeśli Twoje lokalne przepisy podatkowe wymagają opodatkowania opłat. Skonsultuj się z księgowym.
  - **Scenariusz / przykład dla sprzedawcy:** W wielu krajach opłaty za usługi, takie jak opłaty za pobraniem, podlegają VAT. Włączyłbyś to, aby zapewnić zgodność.
- **CODPRO\_FEETAXRULE (Reguła podatkowa dla opłaty)**

  - **Co robi to ustawienie:** Jeśli `CODPRO_FEETAX` jest włączone, ta lista rozwijana pozwala wybrać, która reguła podatkowa PrestaShop ma zastosowanie do opłaty za pobraniem.
  - **Wpływ zmiany tego ustawienia:** Wybrana stawka podatku zostanie zastosowana do opłaty za pobraniem.
  - **Zalecana wartość:** Wybierz odpowiednią regułę podatkową dla usług w Twoim kraju.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli masz regułę podatkową „Standardowy VAT (20%)” dla usług, wybierz ją tutaj.

#### **Opłaty specyficzne dla przewoźnika**

- **codpro\_carrier (Wybór przewoźnika)**
  - **Co robi to ustawienie:** Ta sekcja pozwala zdefiniować różne opłaty za pobraniem dla każdego oferowanego przewoźnika.
  - **Wpływ zmiany tego ustawienia:** Gdy klient wybierze konkretnego przewoźnika podczas realizacji zamówienia, zostanie zastosowana opłata za pobraniem związana z tym przewoźnikiem zamiast opłaty ogólnej.
  - **Zalecana wartość:** Skonfiguruj opłaty dla wszystkich przewoźników oferujących płatność za pobraniem.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli przewoźnik A pobiera 3,00 € za płatność za pobraniem, a przewoźnik B pobiera 1,5% wartości zamówienia, możesz ustawić te odrębne opłaty tutaj.

#### **Ustawienia zaawansowane (zazwyczaj dla programistów/specyficznych scenariuszy)**

- **PS\_LANG\_DEFAULT / PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG (Ustawienia języka)**

  - **Co robi to ustawienie:** Są to standardowe wartości konfiguracji PrestaShop związane z domyślnym językiem i językiem formularza pracownika. Moduł może je wyświetlać w celach informacyjnych, ale zazwyczaj nie wymaga modyfikacji w tym miejscu.
  - **Wpływ zmiany tego ustawienia:** Brak bezpośredniego wpływu na podstawową funkcjonalność modułu, ale zapewnia prawidłowe wyświetlanie języka w Panelu administracyjnym.
  - **Zalecana wartość:** Pozostaw jako domyślne.
- **CODPRO\_ANALYTICS\_DEFAULT\_CHART / CODPRO\_ANALYTICS\_PERIOD / CODPRO\_ANALYTICS\_IMPACT\_DAYS / CODPRO\_ANALYTICS\_CHART\_WEEKS / CODPRO\_ANALYTICS\_CHART\_MONTHS (Ustawienia analityczne)**

  - **Co robi to ustawienie:** Te ustawienia dotyczą potencjalnych wewnętrznych funkcji analitycznych lub pulpitu nawigacyjnego w module (jeśli zaimplementowane). Kontrolują, w jaki sposób dane mogą być wyświetlane lub filtrowane.
  - **Wpływ zmiany tego ustawienia:** Zmienia sposób prezentacji danych analitycznych związanych z zamówieniami za pobraniem w Panelu administracyjnym.
  - **Zalecana wartość:** Pozostaw jako domyślne, chyba że masz konkretne wymagania analityczne.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli moduł zawiera pulpit nawigacyjny, te ustawienia mogą kontrolować domyślny widok (np. ostatnie 7 dni, ostatni miesiąc) dla wydajności zamówień za pobraniem.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### **4.2.1 AdminCodProCarriersFeesController (Panel administracyjny > Moduły > Płatność za pobraniem z opłatą > Opłaty przewoźników)**

- **Nazwa ekranu i lokalizacja w menu:** „Opłaty przewoźników” (zazwyczaj znajduje się pod pozycją menu „Płatność za pobraniem z opłatą” w Panelu administracyjnym PrestaShop).
- **Dostępne działania i ustawienia:** Ten ekran zapewnia widok siatki lub listy do zarządzania opłatami za pobraniem specyficznymi dla każdego przewoźnika. Możesz dodawać nowe reguły specyficzne dla przewoźnika, edytować istniejące lub je usuwać. Dla każdego przewoźnika możesz zdefiniować:
  - Czy opłata jest stałą kwotą, czy procentem.
  - Konkretną stałą kwotę lub wartość procentową.
  - Minimalne i maksymalne opłaty dla opłat procentowych.
  - Czy podatek ma zastosowanie i którą regułę podatkową należy zastosować.
- **Wpływ zmian:** Wszelkie reguły skonfigurowane tutaj zastąpią ogólne ustawienia opłat za pobraniem dla określonych przewoźników. Jeśli przewoźnik ma tutaj regułę, zostanie zastosowana opłata z tej reguły. Jeśli przewoźnik nie jest tutaj wymieniony, zastosowane zostaną ogólne ustawienia opłat za pobraniem.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie przeglądaj tę sekcję, jeśli zmieniają się Twoje umowy z przewoźnikami lub opłaty za pobraniem. Dodawaj nowych przewoźników, gdy wprowadzasz ich do swojego sklepu i konfiguruj ich specyficzne opłaty za pobraniem.

#### **4.2.2 AdminCodProCarriersRangeFeesController (Panel administracyjny > Moduły > Płatność za pobraniem z opłatą > Opłaty za zakresy)**

- **Nazwa ekranu i lokalizacja w menu:** „Opłaty za zakresy” (zazwyczaj znajduje się pod pozycją menu „Płatność za pobraniem z opłatą” w Panelu administracyjnym PrestaShop).
- **Dostępne działania i ustawienia:** Ten ekran pozwala zdefiniować opłaty za pobraniem na podstawie całkowitej wartości koszyka klienta. Możesz ustawić różne struktury opłat dla różnych zakresów cen (np. zamówienia od 0 € do 50 €, od 50 € do 100 € itp.). Dla każdego zakresu możesz zdefiniować:
  - Minimalną i maksymalną wartość koszyka dla zakresu.
  - Czy opłata jest stałą kwotą, czy procentem.
  - Konkretną stałą kwotę lub wartość procentową.
  - Minimalne i maksymalne opłaty dla opłat procentowych w tym zakresie.
  - Czy podatek ma zastosowanie i którą regułę podatkową należy zastosować.
- **Wpływ zmian:** Te reguły oparte na zakresach zapewniają dodatkową warstwę elastyczności. Jeśli całkowita wartość koszyka klienta mieści się w zdefiniowanym zakresie, zostanie zastosowana opłata określona dla tego zakresu. Reguły te mogą współdziałać z regułami specyficznymi dla przewoźnika, potencjalnie umożliwiając bardzo szczegółową kontrolę (np. przewoźnik A pobiera X za zamówienia poniżej 50 €, a Y za zamówienia powyżej 50 €).
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tej sekcji do wdrożenia dynamicznego cennika dla płatności za pobraniem na podstawie wartości zamówienia. Jest to szczególnie przydatne do zarządzania ryzykiem w przypadku zamówień o wysokiej wartości lub do uczynienia płatności za pobraniem bardziej atrakcyjną dla zamówień średniej wartości.

#### **4.2.3 index.php (Panel administracyjny > Moduły > Płatność za pobraniem z opłatą > Pulpit nawigacyjny/Analityka)**

- **Nazwa ekranu i lokalizacja w menu:** Ten kontroler `index.php` zazwyczaj służy jako placeholder lub domyślny punkt wejścia do sekcji administracyjnej modułu. W kontekście tego modułu może być używany do wyświetlania pulpitu nawigacyjnego lub analityki związanej z zamówieniami za pobraniem.
- **Dostępne działania i ustawienia:** Jeśli ten kontroler jest używany do pulpitu nawigacyjnego, prawdopodobnie wyświetlałby wykresy, statystyki lub kluczowe wskaźniki wydajności (KPI) związane z zamówieniami za pobraniem (np. liczba zamówień za pobraniem, całkowity przychód z płatności za pobraniem, średnia pobrana opłata za pobraniem). Mogą istnieć filtry dla zakresów dat lub innych parametrów.
- **Wpływ zmian:** Interakcja z pulpitem nawigacyjnym tutaj zmieniłaby tylko wyświetlane dane, a nie konfigurację sklepu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj ten pulpit nawigacyjny (jeśli jest dostępny), aby monitorować wydajność i wpływ Twojej metody płatności za pobraniem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Główna konfiguracja modułu** | Włączone / Wyłączone | Włączone | Główny przełącznik dla metody płatności za pobraniem. |
| | Wartość (Opłata podstawowa) | 0.00 | Domyślna kwota/procent opłaty. |
| | Jak uwzględnić opłatę? | Uwzględnij jako oddzielny produkt/usługę | Określa, jak opłata pojawia się w koszyku/fakturze. |
| | Status zamówienia po zakupie | Płatność zaakceptowana | Początkowy status dla zamówień za pobraniem. |
| | Pokaż dodatkowe podsumowanie | Włączone | Wyświetla szczegółowe zestawienie opłat przed potwierdzeniem. |
| | Warunek maksymalnej wartości koszyka | Wyłączone | Ogranicza płatność za pobraniem dla zamówień powyżej określonej wartości. |
| | Maksymalna wartość koszyka | 0.00 | Konkretna maksymalna wartość koszyka. |
| | Warunek minimalnej wartości koszyka | Wyłączone | Ogranicza płatność za pobraniem dla zamówień poniżej określonej wartości. |
| | Minimalna wartość koszyka | 0.00 | Konkretna minimalna wartość koszyka. |
| | Wartość opłaty procentowej | 0.00 | Wartość procentowa opłaty za pobraniem. |
| | Podstawa obliczania procentu | Całkowita wartość koszyka (z wysyłką) | Na czym obliczany jest procent. |
| | Wartość opłaty stałej kwoty | 0.00 | Wartość stałej kwoty opłaty za pobraniem. |
| | Minimalna opłata (dla %) | 0.00 | Zapewnia minimalną opłatę dla obliczeń procentowych. |
| | Maksymalna opłata (dla %) | 0.00 | Ogranicza opłatę dla obliczeń procentowych. |
| | Zastosuj podatek do opłaty | Włączone (jeśli dotyczy) | Określa, czy opłata za pobraniem jest opodatkowana. |
| | Reguła podatkowa dla opłaty | Wybierz odpowiednią regułę podatkową | Która reguła podatkowa ma zastosowanie do opłaty. |
| **AdminCodProCarriersFees** | Reguły opłat specyficzne dla przewoźnika | Skonfiguruj według potrzeb | Zastępuje ogólną opłatę dla konkretnych przewoźników. |
| **AdminCodProCarriersRangeFees** | Reguły opłat za zakresy wartości zamówienia | Skonfiguruj według potrzeb | Stosuje różne opłaty w zależności od zakresów całkowitej wartości koszyka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Opłata za pobraniem nie pojawia się na mojej stronie realizacji zamówienia lub jest w niewłaściwym miejscu.**
O1: Zazwyczaj dzieje się tak w przypadku niestandardowych motywów.
- **Sprawdź „Pokaż dodatkowe podsumowanie przed potwierdzeniem”:** Upewnij się, że jest to `Włączone` w głównej konfiguracji modułu.
- **Selektory CSS:** Jeśli Twój motyw używa niestandardowych klas CSS, moduł może nie znaleźć odpowiednich miejsc do wstrzyknięcia opłaty. Przejdź do strony konfiguracji modułu i sprawdź pola selektorów CSS „Podsumowanie koszyka”, „Podsumowanie adresu” i „Minimalna wartość całkowita koszyka”. Może być konieczne, aby programista internetowy sprawdził kod HTML Twojego motywu i podał prawidłowe selektory.
- **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) po wprowadzeniu zmian w konfiguracji.

**P2: Skonfigurowałem opłatę, ale nie jest ona stosowana do zamówień.**
O2:
- **Moduł włączony:** Upewnij się, że główny przełącznik „Włączone / Wyłączone” dla modułu jest ustawiony na `Włączone`.
- **Wartość opłaty:** Sprawdź dwukrotnie, czy wprowadziłeś niezerową „Wartość” w głównej konfiguracji lub skonfigurowałeś konkretne opłaty w sekcjach „Opłaty przewoźników” lub „Opłaty za zakresy”.
- **Spełnione warunki:** Sprawdź, czy koszyk klienta spełnia wszelkie ustawione warunki „Minimalna wartość koszyka” lub „Maksymalna wartość koszyka”.
- **Nadpisania specyficzne dla przewoźnika:** Jeśli skonfigurowałeś opłaty w „Opłatach przewoźników”, upewnij się, że klient wybiera jednego z tych przewoźników. W przeciwnym razie powinna zostać zastosowana opłata ogólna.
- **Reguła podatkowa:** Jeśli używasz reguły podatkowej dla opłaty, upewnij się, że sama reguła podatkowa jest poprawnie skonfigurowana w PrestaShop.

**P3: Jak przetłumaczyć tekst modułu (np. „Opłata za pobraniem”) na inne języki?**
O3: Możesz tłumaczyć ciągi modułu bezpośrednio w PrestaShop:
- Przejdź do **Lokalizacja > Tłumaczenia**.
- Wybierz „Tłumaczenia zainstalowanych modułów”.
- Wybierz swój motyw, swój język, a następnie wybierz „Płatność za pobraniem z opłatą” z listy rozwijanej modułów.
- Zobaczysz listę wszystkich przetłumaczalnych ciągów z modułu. Wprowadź swoje tłumaczenia i zapisz.

**P4: Czy mogę oferować płatność za pobraniem tylko dla określonych grup klientów lub krajów?**
O4: Moduł „Płatność za pobraniem z opłatą” sam w sobie nie posiada wbudowanych opcji ograniczeń dla grup klientów lub krajów. Można jednak użyć podstawowych ograniczeń modułów płatności PrestaShop:
- Przejdź do **Parametry sklepu > Ustawienia zamówień > Płatność**.
- Możesz ograniczyć metody płatności według waluty, kraju lub grupy. Znajdź „Płatność za pobraniem z opłatą” i zastosuj tam żądane ograniczenia.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Płatność za pobraniem z opłatą” (`codpro`) przestrzega standardowej architektury modułów PrestaShop, rozszerzając `PaymentModule` w celu integracji z procesem realizacji zamówienia. Wykorzystuje kilka kontrolerów front-office i admin do specyficznych funkcji, takich jak walidacja płatności, zarządzanie opłatami specyficznymi dla przewoźnika i konfiguracje opłat oparte na zakresach. Moduł w dużym stopniu opiera się na systemie hooków PrestaShop, aby wstrzykiwać swoją logikę i elementy wyświetlania na różnych etapach front-office (realizacja zamówienia, potwierdzenie zamówienia, faktura) i back-office (widok zamówienia). Konfiguracja jest głównie przechowywana w `ps_configuration`, z niestandardowymi tabelami prawdopodobnie używanymi do definicji opłat przewoźników i opłat opartych na zakresach.

### 4.2 Kontrolery (`controllers/`)

#### **Kontrolery Front-Office**

- `controllers/front/index.php`
  - Nazwa klasy: `CodProIndexModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
  - Odpowiedzialność: Ten kontroler może służyć jako domyślny punkt wejścia lub obsługiwać podstawowe routowanie dla akcji modułu w front-office. Biorąc pod uwagę cel modułu, może to być placeholder lub być używany do prostych żądań AJAX związanych z aktualizacjami obliczania opłat podczas realizacji zamówienia.
- `controllers/front/validation.php`
  - Nazwa klasy: `CodProValidationModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
  - Odpowiedzialność: Jest to krytyczny kontroler do przetwarzania płatności, gdy klient wybierze „Płatność za pobraniem z opłatą”. Obsługuje ostateczną walidację zamówienia, stosuje obliczoną opłatę za pobraniem do koszyka i przekierowuje klienta na stronę potwierdzenia zamówienia. Współpracuje z główną klasą modułu `codpro.php` w celu pobrania ustawień opłat i aktualizacji zamówienia.

#### **Kontrolery administracyjne Back-Office**

- `controllers/admin/AdminCodProCarriersFees.php`
  - Nazwa klasy: `AdminCodProCarriersFeesController` (rozszerza `ModuleAdminController`)
  - Nazwa zakładki: „Opłaty przewoźników” (lub podobna, dostępna poprzez menu modułu).
  - Zarządzana encja: `Configuration` (chociaż zarządza konkretnymi wpisami konfiguracyjnymi związanymi z przewoźnikami).
  - Odpowiedzialność: Zapewnia interfejs do zarządzania opłatami za pobraniem w zależności od przewoźnika. Wyświetla listę skonfigurowanych opłat przewoźników, umożliwia dodawanie nowych oraz edycję/usuwanie istniejących wpisów. Prawdopodobnie używa `HelperList` i `HelperForm` PrestaShop do swojego interfejsu użytkownika.
- `controllers/admin/AdminCodProCarriersRangeFees.php`
  - Nazwa klasy: `AdminCodProCarriersRangeFeesController` (rozszerza `ModuleAdminController`)
  - Nazwa zakładki: „Opłaty za zakresy” (lub podobna, dostępna poprzez menu modułu).
  - Zarządzana encja: `CodProTotal` (prawdopodobnie niestandardowy `ObjectModel` dla opłat opartych na zakresach).
  - Odpowiedzialność: Zarządza opłatami za pobraniem na podstawie zakresów całkowitej wartości zamówienia. Zapewnia siatkę do definiowania, edytowania i usuwania reguł opłat dla różnych zakresów wartości koszyka. Ten kontroler również wykorzystuje `HelperList` i `HelperForm` PrestaShop do swojego interfejsu administracyjnego.
- `controllers/admin/index.php`
  - Nazwa klasy: `AdminCodProIndexController` (prawdopodobnie rozszerza `ModuleAdminController`)
  - Nazwa zakładki: Placeholder lub Pulpit nawigacyjny.
  - Zarządzana encja: Brak bezpośrednio.
  - Odpowiedzialność: Ten kontroler prawdopodobnie służy jako punkt wejścia dla pulpitu nawigacyjnego modułu lub domyślnego widoku podczas nawigacji do sekcji administracyjnej modułu. Może wyświetlać analizy lub podsumowanie zamówień za pobraniem.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że podstawowa logika zarządzania opłatami przewoźników i opłatami za zakresy może być obsługiwana bezpośrednio w `AdminCodProCarriersFeesController` i `AdminCodProCarriersRangeFeesController` za pomocą bezpośrednich interakcji z bazą danych lub poprzez definiowanie prostych tablic dla konfiguracji. Jednak `AdminCodProCarriersRangeFeesController` zarządzający `codprototal` implikuje, że *powinien* istnieć `ObjectModel` o nazwie `CodProTotal` (lub podobnej) w katalogu `classes/`, nawet jeśli nie jest on wyraźnie wymieniony w dossier. Jeśli nie, oznacza to, że używane są bezpośrednie zapytania SQL, co jest mniej idealne.

### 4.4 Zasoby JavaScript (`views/js/`)

- `views/js/adminCodProCarriersFees.js`
  - Zakres: Back-office (AdminCodProCarriersFeesController).
  - Funkcjonalność: Prawdopodobnie obsługuje dynamiczne zachowanie na stronie konfiguracji opłat przewoźników. Może to obejmować wywołania AJAX do zapisywania/ładowania danych, walidację formularzy lub interaktywne elementy do dodawania/usuwania reguł opłat przewoźników.
- `views/js/adminCodProDashboard.js`
  - Zakres: Back-office (AdminCodProIndexController lub podobny widok pulpitu nawigacyjnego).
  - Funkcjonalność: Odpowiedzialny za renderowanie wykresów, aktualizowanie statystyk i obsługę interaktywnych elementów na pulpicie nawigacyjnym modułu. Może używać bibliotek do tworzenia wykresów (np. Chart.js) i wykonywać żądania AJAX w celu pobrania danych analitycznych.
- `views/js/codpro-checkout.js`
  - Zakres: Front-office (strona realizacji zamówienia).
  - Funkcjonalność: Jest to kluczowe dla doświadczenia użytkownika front-end. Nasłuchuje zmian w wyborze metody płatności (szczególnie dla „Płatność za pobraniem z opłatą”), dynamicznie aktualizuje podsumowanie zamówienia, aby odzwierciedlić opłatę za pobraniem, i potencjalnie obsługuje żądania AJAX w celu ponownego obliczenia opłat, jeśli zmieni się przewoźnik lub zawartość koszyka. Zapewnia, że opłata jest widoczna przed potwierdzeniem zamówienia.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `views/css/admin_codpro.css`
  - Zakres: Back-office (Panel administracyjny).
  - Funkcjonalność: Zapewnia stylizację dla stron konfiguracji modułu, zarządzania opłatami przewoźników, zarządzania opłatami za zakresy i wszelkich elementów pulpitu nawigacyjnego. Zapewnia spójny wygląd i działanie w Panelu administracyjnym PrestaShop.
  - Kluczowe selektory: Prawdopodobnie celuje w konkretne identyfikatory lub klasy w formularzach i listach administracyjnych modułu (np. `.codpro-admin-form`, `.codpro-dashboard-chart`).
- `views/css/codpro.css`
  - Zakres: Front-office (strona realizacji zamówienia, potwierdzenie zamówienia, faktura).
  - Funkcjonalność: Stylizuje wyświetlanie opłaty za pobraniem w podsumowaniu realizacji zamówienia, opcjach płatności, stronie potwierdzenia zamówienia i potencjalnie na fakturze PDF. Zapewnia, że opłata jest wyraźnie widoczna i zintegrowana z motywem sklepu.
  - Kluczowe selektory: Celuje w elementy, w których wstrzykiwana jest opłata za pobraniem (np. `.codpro-fee-display`, `.payment_option_codpro`, `.order-summary-cod-fee`). Programiści mogą potrzebować nadpisać je w swoim motywie dla idealnej integracji wizualnej.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### **Szablony hooków (`views/templates/hook/`)**

- `views/templates/hook/confirmation.tpl`
  - Hook: `paymentReturn` lub podobny.
  - Wyjście: Szczegóły opłaty za pobraniem na stronie potwierdzenia zamówienia po pomyślnym zamówieniu za pobraniem.
- `views/templates/hook/displayAdminOrder16.tpl`
  - Hook: `displayAdminOrder` (dla PrestaShop 1.6).
  - Wyjście: Dodatkowe informacje o opłacie za pobraniem na stronie szczegółów zamówienia w Panelu administracyjnym PrestaShop 1.6.
- `views/templates/hook/displayAdminOrder17.tpl`
  - Hook: `displayAdminOrder` (dla PrestaShop 1.7+).
  - Wyjście: Podobnie jak `displayAdminOrder16.tpl`, ale dostosowane do układu strony szczegółów zamówienia w Panelu administracyjnym PrestaShop 1.7+.
- `views/templates/hook/displayOrderDetail.tpl`
  - Hook: `displayOrderDetail` (historia zamówień klienta w front-office).
  - Wyjście: Wyświetla opłatę za pobraniem jako część podsumowania zamówienia, gdy klient przegląda szczegóły swoich poprzednich zamówień w sekcji „Moje konto”.
- `views/templates/hook/payment.tpl`
  - Hook: `displayPaymentOptions` lub `paymentOptions`.
  - Wyjście: Opcja płatności „Płatność za pobraniem z opłatą” na stronie realizacji zamówienia, w tym dynamicznie obliczona kwota opłaty.
- `views/templates/hook/pdf.tpl`
  - Hook: `displayPDFInvoice`.
  - Wyjście: Opłata za pobraniem jako pozycja na wygenerowanej fakturze PDF dla zamówienia.

#### **Szablony Front-office (`views/templates/front/`)**

- `views/templates/front/validation.tpl`
  - Cel: Ten szablon jest prawdopodobnie używany przez kontroler frontowy `validation.php`. Może wyświetlać prostą wiadomość podczas procesu walidacji płatności lub służyć jako strona przekierowania.

### 4.7 Schemat bazy danych i mapa hooków

#### **Tabele bazy danych**

- `ps_configuration`: Przechowuje wszystkie ogólne ustawienia modułu (np. `CODPRO_MOD_MAXCART_V`, `CODPRO_CHARGEP_V`, `CODPRO_FEETAX`).
- `ps_codpro_carrier_fees` (prawdopodobnie): Niestandardowa tabela do przechowywania reguł opłat za pobraniem specyficznych dla przewoźnika.
  - Kolumny: `id_codpro_carrier_fee`, `id_carrier`, `fee_type` (stała/procentowa), `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.
- `ps_codpro_range_fees` (prawdopodobnie): Niestandardowa tabela do przechowywania reguł opłat za pobraniem opartych na zakresach wartości zamówienia.
  - Kolumny: `id_codpro_range_fee`, `min_value`, `max_value`, `fee_type`, `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.

#### **Tabela zarejestrowanych hooków**

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | W sekcji `<head>` wszystkich stron. | Aby dołączyć CSS front-office (`codpro.css`) i JS (`codpro-checkout.js`) na odpowiednich stronach (np. realizacji zamówienia). |
| `displayPaymentOptions` | Front-Office | Podczas wyboru metody płatności w realizacji zamówienia. | Aby wyświetlić „Płatność za pobraniem z opłatą” jako opcję płatności, w tym obliczoną opłatę. |
| `paymentOptions` | Front-Office | Odpowiednik `displayPaymentOptions` w PrestaShop 1.6. | Aby wyświetlić „Płatność za pobraniem z opłatą” jako opcję płatności. |
| `paymentReturn` | Front-Office | Na stronie potwierdzenia zamówienia po płatności. | Aby wyświetlić szczegóły opłaty za pobraniem na stronie potwierdzenia. |
| `displayPaymentReturn` | Front-Office | Odpowiednik `paymentReturn` w PrestaShop 1.6. | Aby wyświetlić szczegóły opłaty za pobraniem na stronie potwierdzenia. |
| `displayPDFInvoice` | Front-Office (Generowanie PDF) | Podczas generowania faktury PDF. | Aby dodać opłatę za pobraniem jako pozycję na fakturze. |
| `displayOrderDetail` | Front-Office (Moje konto) | Gdy klient przegląda szczegóły swojego zamówienia. | Aby wyświetlić opłatę za pobraniem w historii zamówień klienta. |
| `displayAdminOrder` | Back-Office (Widok zamówienia) | Gdy administrator przegląda zamówienie w Panelu administracyjnym. | Aby wyświetlić szczegóły opłaty za pobraniem w podsumowaniu zamówienia do przeglądu przez administratora. |
| `ActionAdminControllerSetMedia` | Back-Office (Strony administracyjne) | Przed renderowaniem widoku przez kontroler administracyjny. | Aby dołączyć CSS back-office (`admin_codpro.css`) i JS (`adminCodProCarriersFees.js`, `adminCodProDashboard.js`) na stronach administracyjnych modułu. |
| `actionValidateOrder` | Back-Office (Przetwarzanie zamówienia) | Po zatwierdzeniu zamówienia. | Aby potencjalnie wykonać dodatkowe działania lub rejestrowanie danych związanych z zamówieniami za pobraniem. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu.

- **MyPresta.eu Historia zamówień i pobieranie:** <https://mypresta.eu/my-account/orders/>
- **Wsparcie MyPresta.eu:** <https://mypresta.eu/contact>
