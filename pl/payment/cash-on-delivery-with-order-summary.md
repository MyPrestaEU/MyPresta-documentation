---
title: "Płatność za pobraniem z podsumowaniem zamówienia - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop „Płatność za pobraniem z podsumowaniem zamówienia” od MyPresta.eu."
sidebar:
  label: "Płatność za pobraniem z podsumowaniem zamówienia"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cash on delivery with order summary na MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-order-summary.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/cash-on-delivery-with-order-summary/)
>
> ---


# Płatność za pobraniem z podsumowaniem zamówienia

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym ustawiasz podstawowe zachowanie i opłaty dla metody płatności za pobraniem.

-   **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Płatność za pobraniem z podsumowaniem zamówienia” > Kliknij „Konfiguruj”.

#### Ustawienia ogólne

1.  **Wyłącz COD dla określonych przewoźników**
    -   **Co robi to ustawienie:** Pozwala zapobiec dostępności opcji płatności za pobraniem, jeśli klient wybierze określonych przewoźników.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone (zaznaczone dla określonych przewoźników):* Jeśli klient wybierze jednego z wybranych przewoźników podczas realizacji zamówienia, opcja płatności za pobraniem nie pojawi się.
        -   *Gdy wyłączone (odznaczone dla wszystkich przewoźników):* Płatność za pobraniem będzie dostępna niezależnie od wybranego przewoźnika (chyba że obowiązują inne ograniczenia).
    -   **Zalecana wartość:** Zależy od Twojej logistyki wysyłki. Jeśli niektórzy przewoźnicy nie obsługują COD lub pobierają nadmierne opłaty, włącz to ustawienie.
    -   **Scenariusz / przykład dla sprzedawcy:** Korzystasz z konkretnej usługi kurierskiej, która nie obsługuje płatności gotówkowych. Zaznaczyłbyś tego przewoźnika na liście, aby wyłączyć dla niego COD.

2.  **Jak uwzględnić opłatę?**
    -   **Co robi to ustawienie:** Określa, w jaki sposób opłata za pobraniem jest obliczana i stosowana do zamówienia.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włącz do kosztów wysyłki:* Opłata za pobraniem zostanie dodana bezpośrednio do kosztów wysyłki wyświetlanych klientowi. Może to uprościć wyświetlanie w kasie, ale może ukryć oddzielną opłatę za pobraniem.
        -   *Włącz jako osobny produkt:* Opłata za pobraniem pojawi się jako osobna pozycja w koszyku i podsumowaniu zamówienia, często oznaczona jako „Opłata za pobraniem” lub podobnie. Zapewnia to maksymalną przejrzystość.
    -   **Zalecana wartość:** „Włącz jako osobny produkt” dla przejrzystości i zgodności z prawem, zwłaszcza w UE.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby wyraźnie pokazać klientom dokładny koszt korzystania z COD, wybrałbyś „Włącz jako osobny produkt”.

3.  **Status zamówienia po zakupie z modułem COD**
    -   **Co robi to ustawienie:** Ustawia początkowy status zamówienia złożonego metodą płatności za pobraniem.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na „Płatność zaakceptowana”:* Zamówienie zostanie natychmiast oznaczone jako opłacone, co może być mylące, ponieważ gotówka nie została jeszcze pobrana.
        -   *Gdy ustawione na „Oczekiwanie na walidację płatności za pobraniem” (lub podobne):* Zamówienie będzie w stanie oczekującym, wskazując, że płatność jest oczekiwana przy dostawie. Jest to ogólnie bezpieczniejsze i dokładniejsze.
    -   **Zalecana wartość:** Status oczekujący, taki jak „Oczekiwanie na walidację płatności za pobraniem” lub „Płatność oczekująca”, aby dokładnie odzwierciedlić status płatności.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby uniknąć przedwczesnej wysyłki zamówienia, które nie zostało opłacone, ustawiłbyś to na status oczekujący.

4.  **Pokaż dodatkowe podsumowanie przed potwierdzeniem**
    -   **Co robi to ustawienie:** Kontroluje, czy moduł wyświetla dedykowaną stronę podsumowania zamówienia przed potwierdzeniem. Jest to podstawowa funkcja zgodności modułu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Po wybraniu COD, klienci zobaczą szczegółowe podsumowanie swojego zamówienia, w tym wszystkie koszty, zanim będą mogli kliknąć ostateczny przycisk „Potwierdź zamówienie”.
        -   *Gdy wyłączone:* Moduł pominie tę stronę podsumowania, a klienci przejdą bezpośrednio do standardowego potwierdzenia zamówienia PrestaShop (co może nie być zgodne z prawem w niektórych regionach).
    -   **Zalecana wartość:** **Włączone**. Jest to kluczowa funkcja dla zgodności z prawem i zaufania klientów.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby przestrzegać przepisów konsumenckich UE wymagających jasnego podsumowania zamówienia przed ostatecznym potwierdzeniem, **musisz** włączyć to ustawienie.

#### Ograniczenia wartości koszyka

5.  **Minimalna wartość koszyka**
    -   **Co robi to ustawienie:** Ustawia minimalną całkowitą wartość, jaką musi mieć zamówienie, aby opcja płatności za pobraniem była dostępna.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na wartość (np. 10.00):* Jeśli całkowita wartość koszyka klienta jest niższa od tej kwoty, płatność za pobraniem nie będzie oferowana jako opcja płatności.
        -   *Gdy pozostawione puste lub ustawione na 0:* Nie będzie żadnych ograniczeń minimalnej wartości koszyka dla COD.
    -   **Zalecana wartość:** Ustaw rozsądne minimum, jeśli koszt operacyjny przetwarzania małych zamówień COD jest zbyt wysoki. W przeciwnym razie pozostaw puste.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli koszt przetwarzania zamówienia COD (opłaty kurierskie, praca administracyjna) wynosi 5 €, możesz ustawić minimalną wartość koszyka na 10 €, aby zapewnić rentowność.

6.  **Maksymalna wartość koszyka**
    -   **Co robi to ustawienie:** Ustawia maksymalną całkowitą wartość, jaką może mieć zamówienie, aby opcja płatności za pobraniem była dostępna.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na wartość (np. 500.00):* Jeśli całkowita wartość koszyka klienta przekracza tę kwotę, płatność za pobraniem nie będzie oferowana jako opcja płatności.
        -   *Gdy pozostawione puste lub ustawione na 0:* Nie będzie żadnych ograniczeń maksymalnej wartości koszyka dla COD.
    -   **Zalecana wartość:** Ustaw maksimum, jeśli chcesz ograniczyć ryzyko dla bardzo wartościowych zamówień, które mogą być przedmiotem oszustwa lub nieodebrania. W przeciwnym razie pozostaw puste.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zmniejszyć ryzyko braku płatności za bardzo drogie zamówienia, możesz ustawić maksymalną wartość koszyka na 200 € dla COD.

#### Ustawienia opłaty za pobraniem

7.  **Typ opłaty za pobraniem (procent lub kwota)**
    -   **Co robi to ustawienie:** Określa, czy opłata za pobraniem jest stałą kwotą, czy procentem całkowitej wartości zamówienia.
    -   **Skutek zmiany tego ustawienia:**
        -   *Procent:* Opłata zostanie obliczona jako procent całkowitej wartości zamówienia.
        -   *Kwota:* Opłata będzie stałą wartością pieniężną.
    -   **Zalecana wartość:** Wybierz na podstawie swojej struktury kosztów. Jeśli Twoje koszty skalują się z wartością zamówienia, użyj procentu. Jeśli jest to stała opłata manipulacyjna, użyj kwoty.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój bank pobiera procent wartości transakcji za obsługę gotówki, wybrałbyś „Procent”. Jeśli Twój kurier pobiera stałą opłatę za COD, wybrałbyś „Kwota”.

8.  **Wartość opłaty za pobraniem (procent)** (Pojawia się, jeśli powyżej wybrano „Procent”)
    -   **Co robi to ustawienie:** Wartość procentowa, która ma być naliczana jako opłata za pobraniem.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na 5:* Opłata za pobraniem wyniesie 5% całkowitej wartości zamówienia.
    -   **Zalecana wartość:** Procent, który pokrywa Twoje koszty, nie zniechęcając klientów.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby pokryć 2% opłaty bankowej za wpłaty gotówkowe, możesz ustawić to na „2”.

9.  **Wartość opłaty za pobraniem (kwota)** (Pojawia się, jeśli powyżej wybrano „Kwota”)
    -   **Co robi to ustawienie:** Stała wartość pieniężna, która ma być naliczana jako opłata za pobraniem.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na 2.50:* Opłata za pobraniem wyniesie 2.50 € (lub Twoja domyślna waluta) niezależnie od całkowitej wartości zamówienia.
    -   **Zalecana wartość:** Stała kwota, która pokrywa Twoje stałe koszty obsługi.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój kurier pobiera stałe 3 € za usługę COD, ustawiłbyś to na „3”.

10. **Minimalna opłata za pobraniem**
    -   **Co robi to ustawienie:** Ustawia minimalną kwotę opłaty za pobraniem, niezależnie od obliczeń procentowych.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na 1.00, a procent oblicza 0.50:* Opłata wyniesie 1.00.
        -   *Gdy ustawione na 1.00, a procent oblicza 2.00:* Opłata wyniesie 2.00.
    -   **Zalecana wartość:** Przydatne, jeśli masz minimalny koszt związany z COD nawet dla małych zamówień.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli 5% zamówienia o wartości 10 € to tylko 0.50 €, ale Twój minimalny koszt obsługi wynosi 1 €, ustawiłbyś to na „1.00”.

11. **Maksymalna opłata za pobraniem**
    -   **Co robi to ustawienie:** Ustawia maksymalną kwotę opłaty za pobraniem, niezależnie od obliczeń procentowych.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na 10.00, a procent oblicza 15.00:* Opłata wyniesie 10.00.
        -   *Gdy ustawione na 10.00, a procent oblicza 5.00:* Opłata wyniesie 5.00.
    -   **Zalecana wartość:** Przydatne, aby zapobiec nadmiernemu wzrostowi opłaty za pobraniem przy bardzo dużych zamówieniach.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby opłata za pobraniem nie stała się zaporowa dla dużych zamówień, możesz ją ograniczyć do 15 €.

12. **Zastosuj podatek do opłaty za pobraniem**
    -   **Co robi to ustawienie:** Określa, czy sama opłata za pobraniem podlega podatkowi od sprzedaży.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Będziesz mógł wybrać regułę podatkową do zastosowania do opłaty za pobraniem.
        -   *Gdy wyłączone:* Opłata za pobraniem będzie zwolniona z podatku.
    -   **Zalecana wartość:** Skonsultuj się z lokalnymi przepisami podatkowymi. W wielu regionach opłaty za przetwarzanie płatności podlegają opodatkowaniu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli przepisy podatkowe Twojego kraju wymagają naliczania VAT od opłat za usługi płatnicze, włączyłbyś to i wybrał odpowiednią regułę podatkową.

13. **Reguła podatkowa dla opłaty za pobraniem** (Pojawia się, jeśli „Zastosuj podatek do opłaty za pobraniem” jest włączone)
    -   **Co robi to ustawienie:** Pozwala wybrać istniejącą regułę podatkową z Twojego sklepu PrestaShop do zastosowania do opłaty za pobraniem.
    -   **Skutek zmiany tego ustawienia:** Wybrana stawka podatku zostanie zastosowana do obliczonej opłaty za pobraniem.
    -   **Zalecana wartość:** Wybierz regułę podatkową, która odpowiada opłatom za przetwarzanie płatności w Twojej jurysdykcji.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz regułę podatkową „VAT 20%”, wybrałbyś ją tutaj, aby zastosować 20% VAT do opłaty za pobraniem.

#### Zaawansowane ustawienia wyświetlania

14. **Selektor CSS dla sumy koszyka**
    -   **Co robi to ustawienie:** Pozwala określić selektor CSS dla elementu, który wyświetla całkowitą wartość koszyka na stronie realizacji zamówienia. Pomaga to modułowi dokładnie zaktualizować sumę, gdy zastosowana jest opłata za pobraniem.
    -   **Skutek zmiany tego ustawienia:** Jeśli poprawnie ustawione, moduł może dynamicznie aktualizować sumę na stronie realizacji zamówienia, aby uwzględnić opłatę za pobraniem. Jeśli niepoprawne, suma może się nie zaktualizować, co prowadzi do zamieszania.
    -   **Zalecana wartość:** Pozostaw puste, chyba że występują problemy z wyświetlaniem, gdy suma się nie aktualizuje. W razie potrzeby skonsultuj się z deweloperem swojego motywu lub użyj narzędzi deweloperskich przeglądarki, aby znaleźć prawidłowy selektor (np. `.cart-total-value`).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw używa niestandardowej klasy, takiej jak `.mytheme-total-price` dla sumy koszyka, wprowadziłbyś ją tutaj.

15. **Selektor CSS dla podsumy koszyka**
    -   **Co robi to ustawienie:** Podobnie jak w przypadku sumy koszyka, określa selektor CSS dla podsumy koszyka.
    -   **Skutek zmiany tego ustawienia:** Pomaga modułowi prawidłowo zidentyfikować i potencjalnie zaktualizować wyświetlanie podsumy.
    -   **Zalecana wartość:** Pozostaw puste, chyba że występują problemy z wyświetlaniem.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma określony element dla podsumy, być może będziesz musiał wprowadzić jego selektor tutaj.

16. **Selektor CSS dla wysyłki koszyka**
    -   **Co robi to ustawienie:** Podobnie jak w przypadku sumy koszyka, określa selektor CSS dla wyświetlania kosztów wysyłki.
    -   **Skutek zmiany tego ustawienia:** Pomaga modułowi prawidłowo zidentyfikować i potencjalnie zaktualizować wyświetlanie kosztów wysyłki, zwłaszcza jeśli opłata za pobraniem jest wliczona w wysyłkę.
    -   **Zalecana wartość:** Pozostaw puste, chyba że występują problemy z wyświetlaniem.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma określony element dla kosztów wysyłki, być może będziesz musiał wprowadzić jego selektor tutaj.

17. **Logo COD**
    -   **Co robi to ustawienie:** Pozwala przesłać niestandardowe logo, które będzie wyświetlane obok opcji płatności za pobraniem podczas realizacji zamówienia.
    -   **Skutek zmiany tego ustawienia:**
        -   *Po przesłaniu:* Pojawi się ikona wizualna lub logo, dzięki czemu opcja COD będzie bardziej widoczna i atrakcyjna wizualnie.
        -   *Gdy puste:* Nie zostanie wyświetlone żadne niestandardowe logo.
    -   **Zalecana wartość:** Prześlij małe, wyraźne logo (np. ikonę gotówki), aby poprawić doświadczenie użytkownika.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby opcja COD wyróżniała się, możesz przesłać mały obraz banknotów lub monet.

#### Ustawienia analityczne (wewnętrzne użycie modułu)

Te ustawienia są zazwyczaj przeznaczone do wewnętrznej analizy modułu i zazwyczaj nie wymagają interwencji sprzedawcy.

18. **CODPRO_ANALYTICS_DEFAULT_CHART, CODPRO_ANALYTICS_PERIOD, CODPRO_ANALYTICS_IMPACT_DAYS, CODPRO_ANALYTICS_CHART_WEEKS, CODPRO_ANALYTICS_CHART_MONTHS**
    -   **Co robią te ustawienia:** Są to wewnętrzne klucze konfiguracyjne używane przez moduł do potencjalnych przyszłych funkcji analitycznych lub wyświetlania na pulpicie nawigacyjnym w ramach własnej administracji modułu. Kontrolują one sposób gromadzenia lub wyświetlania danych do monitorowania wydajności.
    -   **Skutek zmiany tych ustawień:** Mało prawdopodobne, aby miały bezpośredni, natychmiastowy wpływ na doświadczenie klienta w front-office. Wpływają przede wszystkim na potencjalne raportowanie w back-office.
    -   **Zalecana wartość:** Pozostaw ich wartości domyślne.
    -   **Scenariusz / przykład dla sprzedawcy:** Te ustawienia nie są zazwyczaj dostosowywane przez sprzedawców.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia dwa dodatkowe ekrany administracyjne do bardziej szczegółowej kontroli nad opłatami za pobraniem, szczególnie przydatne w przypadku złożonych strategii wysyłki i cen.

#### 2.2.1 AdminCodProCarriersFeesController: Opłaty za pobraniem specyficzne dla przewoźnika

-   **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Płatność za pobraniem z podsumowaniem zamówienia” > Kliknij „Konfiguruj” > Poszukaj zakładki lub linku o nazwie „Opłaty przewoźnika” lub podobnej (może być zintegrowana z główną konfiguracją lub osobną pozycją menu, w zależności od wersji PrestaShop).
-   **Dostępne działania i ustawienia:** Ten ekran zazwyczaj przedstawia siatkę lub tabelę, w której można zdefiniować różne opłaty za pobraniem w zależności od wybranego przewoźnika. Możesz dodawać, edytować lub usuwać te reguły opłat specyficzne dla przewoźnika.
    -   **Wybór przewoźnika:** Wybierz konkretnego przewoźnika.
    -   **Typ opłaty:** Wybierz, czy opłata jest stałą kwotą, czy procentem.
    -   **Wartość opłaty:** Wprowadź kwotę lub procent.
    -   **Reguła podatkowa:** Zastosuj konkretną regułę podatkową do opłaty za pobraniem tego przewoźnika.
-   **Skutek zmian:** Gdy klient wybierze przewoźnika, dla którego zdefiniowałeś tutaj konkretną opłatę za pobraniem, ta opłata zastąpi ogólną opłatę za pobraniem ustawioną w głównej konfiguracji modułu. Pozwala to na wysoce spersonalizowane ceny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Uzyskaj dostęp do tego ekranu, jeśli musisz naliczać różne opłaty za pobraniem w zależności od tego, który kurier dostarcza paczkę.
    2.  Kliknij „Dodaj nową opłatę przewoźnika” (lub podobny przycisk).
    3.  Wybierz przewoźnika, zdefiniuj typ opłaty (kwota/procent), wartość i regułę podatkową.
    4.  Zapisz zmiany.
    5.  Przejrzyj listę, aby upewnić się, że wszystkie opłaty specyficzne dla przewoźnika są poprawnie ustawione.
-   **Scenariusz / przykład dla sprzedawcy:** Twoja krajowa poczta pobiera stałe 2 € za pobranie, ale prywatny kurier ekspresowy pobiera 3% wartości zamówienia. Użyłbyś tego ekranu, aby ustawić te różne opłaty dla każdego przewoźnika.

#### 2.2.2 AdminCodProCarriersRangeFeesController: Opłaty za pobraniem specyficzne dla przewoźnika i zakresu wartości

-   **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Płatność za pobraniem z podsumowaniem zamówienia” > Kliknij „Konfiguruj” > Poszukaj zakładki lub linku o nazwie „Opłaty zakresowe” lub podobnej.
-   **Dostępne działania i ustawienia:** Ten ekran zapewnia jeszcze bardziej zaawansowany poziom kontroli opłat. Możesz zdefiniować opłaty za pobraniem, które różnią się nie tylko w zależności od przewoźnika, ale także od *całkowitej wartości koszyka klienta*. Jest to często przedstawiane jako siatka, w której definiujesz zakresy (np. „Całkowita wartość zamówienia od 0 € do 50 €”, „Całkowita wartość zamówienia od 50 € do 100 €”).
    -   **Wybór przewoźnika:** Wybierz konkretnego przewoźnika.
    -   **Minimalna wartość zamówienia:** Dolna granica zakresu wartości zamówienia.
    -   **Maksymalna wartość zamówienia:** Górna granica zakresu wartości zamówienia.
    -   **Typ opłaty:** Stała kwota lub procent.
    -   **Wartość opłaty:** Kwota lub procent dla tego konkretnego przewoźnika i zakresu wartości zamówienia.
    -   **Reguła podatkowa:** Zastosuj konkretną regułę podatkową.
-   **Skutek zmian:** Te opłaty oparte na zakresie mają pierwszeństwo zarówno przed ogólną opłatą za pobraniem, jak i prostymi opłatami specyficznymi dla przewoźnika. Pozwalają na wysoce dynamiczne strategie cenowe.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Użyj tego ekranu dla najbardziej złożonych struktur opłat za pobraniem.
    2.  Kliknij „Dodaj nową opłatę zakresową” (lub podobne).
    3.  Wybierz przewoźnika, zdefiniuj minimalną i maksymalną wartość zamówienia dla tej reguły.
    4.  Określ typ opłaty, wartość i regułę podatkową dla tego konkretnego zakresu.
    5.  Zapisz i powtórz dla wszystkich niezbędnych zakresów i przewoźników.
-   **Scenariusz / przykład dla sprzedawcy:** Dla konkretnego przewoźnika możesz naliczać opłatę za pobraniem w wysokości 3 € za zamówienia poniżej 50 €, ale 2% opłaty za zamówienia od 50 € do 200 €, i stałą opłatę w wysokości 5 € za zamówienia powyżej 200 €. Ten ekran pozwala ustawić takie ceny warstwowe.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| **Konfiguracja modułu** | Wyłącz COD dla określonych przewoźników | Nie (wszystkie włączone) | Ogranicz dostępność COD według wybranego przewoźnika. |
| | Jak uwzględnić opłatę? | Włącz jako osobny produkt | Określa, jak opłata za pobraniem pojawia się w koszyku/zamówieniu. „Osobny produkt” dla przejrzystości. |
| | Status zamówienia po zakupie z modułem COD | Oczekiwanie na walidację COD | Ustawia początkowy status zamówienia; „Oczekiwanie na walidację COD” jest zalecane dla dokładności. |
| | Pokaż dodatkowe podsumowanie przed potwierdzeniem | Włączone | **KRYTYCZNE:** Wyświetla prawne podsumowanie przed potwierdzeniem. **Włączone** dla zgodności. |
| | Minimalna wartość koszyka | Puste / 0 | Minimalna wartość zamówienia dla COD. Ustaw, jeśli małe zamówienia są nieopłacalne. |
| | Maksymalna wartość koszyka | Puste / 0 | Maksymalna wartość zamówienia dla COD. Ustaw, aby zmniejszyć ryzyko przy dużych zamówieniach. |
| | Typ opłaty za pobraniem | Kwota | Wybierz, czy opłata jest stała, czy procentowa. |
| | Wartość opłaty za pobraniem (procent) | 0 | Procent całkowitej wartości zamówienia dla opłaty za pobraniem. |
| | Wartość opłaty za pobraniem (kwota) | 0 | Stała kwota pieniężna dla opłaty za pobraniem. |
| | Minimalna opłata za pobraniem | 0 | Zapewnia naliczenie minimalnej opłaty, nawet jeśli procent jest niski. |
| | Maksymalna opłata za pobraniem | 0 | Ogranicza opłatę za pobraniem, aby nie stała się zbyt wysoka. |
| | Zastosuj podatek do opłaty za pobraniem | Nie | Określa, czy podatek jest stosowany do opłaty za pobraniem. Skonsultuj się z lokalnymi przepisami podatkowymi. |
| | Reguła podatkowa dla opłaty za pobraniem | (Brak) | Wybiera regułę podatkową, jeśli „Zastosuj podatek” jest włączone. |
| | Selektor CSS dla sumy koszyka | Puste | Zaawansowane: Selektor CSS dla wyświetlania sumy koszyka. Pozostaw puste, chyba że występują problemy. |
| | Selektor CSS dla podsumy koszyka | Puste | Zaawansowane: Selektor CSS dla wyświetlania podsumy koszyka. Pozostaw puste, chyba że występują problemy. |
| | Selektor CSS dla wysyłki koszyka | Puste | Zaawansowane: Selektor CSS dla wyświetlania kosztów wysyłki. Pozostaw puste, chyba że występują problemy. |
| | Logo COD | Puste | Prześlij niestandardowe logo dla opcji płatności za pobraniem. |
| **AdminCodProCarriersFees** | Opłaty specyficzne dla przewoźnika | N/A | Zdefiniuj opłaty za pobraniem, które różnią się w zależności od przewoźnika. |
| **AdminCodProCarriersRangeFees** | Opłaty specyficzne dla przewoźnika i zakresu | N/A | Zdefiniuj opłaty za pobraniem, które różnią się w zależności od przewoźnika ORAZ zakresu wartości zamówienia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Opcja COD nie pojawia się dla klientów.**
O1: Sprawdź następujące elementy:
    *   **Moduł włączony:** Czy moduł „Płatność za pobraniem z podsumowaniem zamówienia” jest włączony w **Moduły > Menedżer modułów**?
    *   **Ograniczenia płatności:** Przejdź do **Parametry sklepu > Ustawienia zamówień > Płatności** (lub **Płatność > Preferencje** w starszych wersjach). Upewnij się, że „Płatność za pobraniem z podsumowaniem zamówienia” nie jest ograniczona przez grupę klientów, walutę lub kraj.
    *   **Ograniczenia przewoźnika:** W konfiguracji modułu sprawdź „Wyłącz COD dla określonych przewoźników”. Czy wybrany przewoźnik klienta jest przypadkowo zaznaczony?
    *   **Ograniczenia wartości koszyka:** Sprawdź „Minimalna wartość koszyka” i „Maksymalna wartość koszyka” w konfiguracji modułu. Czy koszyk klienta mieści się w tych limitach?
    *   **Strefy geograficzne:** Upewnij się, że moduł jest włączony dla kraju klienta w **Parametry sklepu > Ustawienia zamówień > Płatności > Ograniczenia według strefy/kraju**.

**P2: Opłata za pobraniem nie pojawia się lub nie jest obliczana prawidłowo.**
O2:
    *   **Ustawienia opłat:** Dokładnie sprawdź ustawienia „Typ opłaty za pobraniem” (Procent/Kwota) i „Wartość opłaty za pobraniem” w głównej konfiguracji modułu.
    *   **Opłaty przewoźnika/zakresu:** Jeśli używasz `AdminCodProCarriersFees` lub `AdminCodProCarriersRangeFees`, upewnij się, że reguły są poprawnie zdefiniowane dla konkretnego przewoźnika i całkowitej wartości zamówienia. Te specyficzne reguły zastępują ustawienia ogólne.
    *   **Reguły podatkowe:** Jeśli „Zastosuj podatek do opłaty za pobraniem” jest włączone, upewnij się, że wybrano prawidłową regułę podatkową.
    *   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Czasami stare dane mogą uniemożliwić aktualizację opłat.

**P3: Strona podsumowania przed potwierdzeniem nie wyświetla się, lub zamówienie przechodzi bezpośrednio do potwierdzenia.**
O3:
    *   **Ustawienie „Pokaż dodatkowe podsumowanie przed potwierdzeniem”:** W głównej konfiguracji modułu upewnij się, że to ustawienie jest **Włączone**. Jest to kluczowe dla pojawienia się strony podsumowania.
    *   **Kompatybilność motywu:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, niektóre mocno dostosowane motywy mogą zakłócać jego działanie. Jeśli strona podsumowania nadal się nie pojawia, tymczasowo przełącz się na domyślny motyw PrestaShop, aby wykluczyć konflikt motywu. Jeśli działa na domyślnym motywie, skontaktuj się z deweloperem motywu lub ekspertem PrestaShop.

**P4: Opłata za pobraniem nie jest wyświetlana na fakturze PDF.**
O4:
    *   **Moduł jest aktywny:** Upewnij się, że moduł jest włączony.
    *   **Generowanie faktury:** Wygeneruj ponownie fakturę PDF dla zamówienia złożonego z COD *po* prawidłowym skonfigurowaniu modułu. Stare faktury mogą nie odzwierciedlać nowych ustawień.
    *   **Wersja PrestaShop:** Upewnij się, że Twoja wersja PrestaShop jest w pełni obsługiwana. Chociaż moduł dąży do szerokiej kompatybilności, bardzo stare lub bardzo nowe wersje mogą mieć drobne problemy z wyświetlaniem.

**P5: Jak zmienić tekst „Płatność za pobraniem” lub opis opłaty?**
O5:
    *   **Tłumaczenia:** Przejdź do **Lokalizacja > Tłumaczenia**. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Płatność za pobraniem z podsumowaniem zamówienia”. Następnie możesz znaleźć i zmodyfikować wszystkie przetłumaczalne ciągi używane przez moduł.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Płatność za pobraniem z podsumowaniem zamówienia” (`codpro`) jest standardowym modułem płatności PrestaShop, zgodnym ze wzorcem MVC (Model-View-Controller). Rozszerza `PaymentModule` i wykorzystuje różne hooki PrestaShop do wstrzykiwania opcji płatności, wyświetlania podsumowania przed potwierdzeniem oraz zarządzania statusem zamówienia i opłatami. Wykorzystuje wartości konfiguracyjne przechowywane w `ps_configuration` dla swoich ustawień i zawiera niestandardowe kontrolery administracyjne do zaawansowanego zarządzania opłatami. Moduł dynamicznie oblicza i wyświetla opłaty za pobraniem, integrując je z sumami koszyka i zamówienia.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office
-   `controllers/front/index.php`
    *   **Nazwa klasy:** `CodProIndexModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Ten kontroler może być placeholderem lub obsługiwać początkowe routowanie dla komponentów front-office modułu. Biorąc pod uwagę kontroler `validation.php`, `index.php` może nie mieć bezpośredniej trasy widocznej dla użytkownika, ale może być używany do wewnętrznej logiki modułu lub przekierowań.
-   `controllers/front/validation.php`
    *   **Nazwa klasy:** `CodProValidationModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Jest to krytyczny kontroler do przetwarzania ostatecznego potwierdzenia zamówienia. Odbiera dane POST ze strony podsumowania przed potwierdzeniem, waliduje zamówienie, tworzy zamówienie w PrestaShop i przekierowuje klienta na stronę potwierdzenia zamówienia (`paymentReturn`). Obsługuje logikę stosowania opłaty za pobraniem do zamówienia.

#### Kontrolery administracyjne Back-Office
-   `controllers/admin/AdminCodProCarriersFees.php`
    *   **Nazwa klasy:** `AdminCodProCarriersFeesController`
    *   **Klasa nadrzędna:** `ModuleAdminController`
    *   **Nazwa zakładki:** Prawdopodobnie podzakładka w głównej konfiguracji modułu lub niestandardowa pozycja menu.
    *   **Zarządzana encja:** Zarządza wpisami konfiguracyjnymi związanymi z opłatami za pobraniem specyficznymi dla przewoźnika.
    *   **Odpowiedzialność:** Zapewnia interfejs (oparty na `HelperList` lub `HelperForm` zgodnie ze wzorcami `AdminController`) dla administratorów do definiowania, edytowania i usuwania opłat za pobraniem, które są specyficzne dla poszczególnych przewoźników. Obsługuje operacje CRUD dla tych reguł opłat.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    *   **Nazwa klasy:** `AdminCodProCarriersRangeFeesController`
    *   **Klasa nadrzędna:** `ModuleAdminController`
    *   **Nazwa zakładki:** Prawdopodobnie podzakładka w głównej konfiguracji modułu.
    *   **Zarządzana encja:** Zarządza wpisami w tabeli `codprototal` (lub podobnej, na podstawie kluczy konfiguracyjnych `CODPRO_MOD_MAXCART_V` i `CODPRO_MOD_MINCART_V`).
    *   **Odpowiedzialność:** Zapewnia interfejs dla administratorów do definiowania, edytowania i usuwania opłat za pobraniem, które są zależne zarówno od wybranego przewoźnika, jak i całkowitej wartości koszyka klienta (tj. opłaty oparte na zakresie). Obsługuje operacje CRUD dla tych złożonych reguł opłat.
-   `controllers/admin/index.php`
    *   **Nazwa klasy:** (Nie jest to typowa klasa kontrolera, zazwyczaj przekierowanie lub środek bezpieczeństwa)
    *   **Klasa nadrzędna:** N/A
    *   **Odpowiedzialność:** Często środek bezpieczeństwa zapobiegający bezpośredniemu listowaniu katalogów lub przekierowujący do głównej konfiguracji modułu. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminModules&token=...')` lub `die('Forbidden');`.

### 4.3 Klasy podstawowe i modele (`classes/`)
Dostarczone informacje o module wskazują brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że podstawowa logika modułu, obsługa danych i potencjalnie definicje `ObjectModel` (jeśli używane są niestandardowe tabele poza `ps_configuration`) są hermetyzowane bezpośrednio w głównym pliku `codpro.php` lub obsługiwane za pomocą standardowych `ObjectModel` PrestaShop, takich jak `Order` i `Cart`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `codpro/views/js/adminCodProCarriersFees.js`
    *   **Zakres:** Back-office (AdminCodProCarriersFeesController)
    *   **Odpowiedzialność:** Prawdopodobnie obsługuje dynamiczne interakcje na stronie administracyjnej opłat specyficznych dla przewoźnika. Może to obejmować wywołania AJAX do dodawania/edycji opłat, walidację formularzy lub aktualizację wyświetlania listy opłat.
-   `codpro/views/js/adminCodProDashboard.js`
    *   **Zakres:** Back-office (potencjalnie główna strona konfiguracji modułu, jeśli zawiera analizy)
    *   **Odpowiedzialność:** Biorąc pod uwagę klucze konfiguracyjne `CODPRO_ANALYTICS_`, ten skrypt jest prawdopodobnie odpowiedzialny za renderowanie wykresów, grafów lub innych danych analitycznych związanych z zamówieniami COD w interfejsie back-office modułu. Może używać biblioteki do tworzenia wykresów (np. Chart.js) i wykonywać żądania AJAX w celu pobrania danych.
-   `codpro/views/js/codpro-checkout.js`
    *   **Zakres:** Front-office (strona realizacji zamówienia)
    *   **Odpowiedzialność:** Jest to kluczowy skrypt dla doświadczenia front-office. Nasłuchuje zmian w procesie realizacji zamówienia (np. wybór COD jako metody płatności, zmiana przewoźnika, aktualizacja ilości w koszyku). Dynamicznie aktualizuje wyświetlanie sumy koszyka, podsumy i kosztów wysyłki (używając selektorów CSS zdefiniowanych w konfiguracji modułu), aby odzwierciedlić obliczoną opłatę za pobraniem. Może również obsługiwać przekierowanie na stronę podsumowania przed potwierdzeniem.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `codpro/views/css/admin_codpro.css`
    *   **Zakres:** Back-office (strony administracyjne związane z modułem)
    *   **Odpowiedzialność:** Zapewnia stylizację formularzy konfiguracyjnych modułu, list i potencjalnie wszelkich niestandardowych elementów pulpitu nawigacyjnego w panelu administracyjnym PrestaShop. Zapewnia spójny i przyjazny dla użytkownika interfejs administracyjny.
    *   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w elementy w szablonach `HelperForm` lub `HelperList` modułu, lub niestandardowe elementy specyficzne dla widoków administracyjnych modułu.
-   `codpro/views/css/codpro.css`
    *   **Zakres:** Front-office (strona realizacji zamówienia, podsumowanie przed potwierdzeniem, szczegóły zamówienia)
    *   **Odpowiedzialność:** Stylizuje wyświetlanie opcji płatności za pobraniem, strony podsumowania przed potwierdzeniem oraz wyświetlanie opłaty za pobraniem na stronach szczegółów zamówienia i fakturach. Zapewnia wizualną integrację elementów modułu z motywem sklepu.
    *   **Kluczowe selektory klas CSS:** Będzie celować w elementy takie jak blok opcji płatności za pobraniem, tabela podsumowania, pozycje opłat i potencjalnie wszelkie niestandardowe alerty lub komunikaty wprowadzone przez moduł. Deweloperzy mogą je nadpisać w pliku `custom.css` swojego motywu lub używając bardziej specyficznych selektorów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)
-   `codpro/views/templates/hook/confirmation.tpl`
    *   **Hook:** `displayPaymentReturn`
    *   **Wyjście:** Treść wyświetlana na stronie potwierdzenia zamówienia po pomyślnym zamówieniu COD. Może zawierać wiadomość przypominającą klientowi o płatności gotówką przy odbiorze.
-   `codpro/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook:** `displayAdminOrder` (dla PrestaShop 1.6.x)
    *   **Wyjście:** Dodaje specyficzne informacje związane z płatnością COD (np. szczegóły opłaty) do strony widoku zamówienia w panelu administracyjnym PrestaShop 1.6.
-   `codpro/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook:** `displayAdminOrder` (dla PrestaShop 1.7.x, 8.x, 9.x)
    *   **Wyjście:** Podobnie jak `displayAdminOrder16.tpl`, ale dostosowane do widoku zamówienia w panelu administracyjnym PrestaShop 1.7+, wyświetlając szczegóły płatności COD.
-   `codpro/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook:** `displayOrderDetail`
    *   **Wyjście:** Wyświetla specyficzne informacje COD (np. zestawienie opłat) na stronie szczegółów zamówienia klienta w front-office.
-   `codpro/views/templates/hook/payment.tpl`
    *   **Hook:** `paymentOptions` lub `displayPaymentOptions`
    *   **Wyjście:** Renderuje blok opcji płatności „Płatność za pobraniem” na stronie realizacji zamówienia, w tym logo modułu i wszelkie wyświetlane opłaty.
-   `codpro/views/templates/hook/pdf.tpl`
    *   **Hook:** `displayPDFInvoice`
    *   **Wyjście:** Wstrzykuje opłatę za pobraniem jako pozycję lub podsumowanie do generowanych faktur PDF.

#### Szablony Front-office (`views/templates/front/`)
-   `codpro/views/templates/front/validation.tpl`
    *   **Wyjście:** Jest to szablon dla kluczowej strony podsumowania zamówienia przed potwierdzeniem. Wyświetla pełne podsumowanie koszyka, adres wysyłki, całkowite koszty (w tym opłatę za pobraniem) i ostateczny przycisk „Potwierdź zamówienie”. Ten szablon jest renderowany przez kontroler front-office `validation.php`.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych
Moduł wykorzystuje głównie standardową tabelę `ps_configuration` do przechowywania swoich ustawień (np. `CODPRO_MOD_MAXCART`, `CODPRO_FEEPAY`, `CODPRO_CHARGEP_V` itp.).

Na podstawie `AdminCodProCarriersRangeFeesController` zarządzającego encją `codprototal`, jest bardzo prawdopodobne, że moduł tworzy niestandardową tabelę bazy danych, prawdopodobnie nazwaną `ps_codprototal` (lub podobnie, zgodnie z konwencją prefiksu `ps_` PrestaShop).
-   **`ps_codprototal` (Prawdopodobna tabela):**
    *   **Cel:** Przechowuje reguły opłat za pobraniem oparte na zakresie, łącząc przewoźników, minimalne/maksymalne sumy koszyka, kwoty/procenty opłat i reguły podatkowe.
    *   **Prawdopodobne pola:** `id_codprototal` (PK), `id_carrier`, `min_total`, `max_total`, `fee_type` (np. 'amount', 'percentage'), `fee_value`, `id_tax_rule`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony. | Aby dołączyć zasoby CSS/JS modułu (np. `codpro-checkout.js`, `codpro.css`) na odpowiednich stronach front-office. |
| `paymentOptions` | Podczas procesu realizacji zamówienia, gdy wyświetlane są opcje płatności. | Aby wstrzyknąć opcję płatności „Płatność za pobraniem” do listy. |
| `displayPaymentOptions` | (Alias lub alternatywa dla `paymentOptions` dla niektórych wersji) | Aby wstrzyknąć opcję płatności „Płatność za pobraniem” do listy. |
| `paymentReturn` | Na stronie potwierdzenia zamówienia po pomyślnym zamówieniu. | Aby wyświetlić komunikat potwierdzający specyficzny dla zamówień COD. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w panelu administracyjnym PrestaShop. | Aby wyświetlić szczegóły opłaty za pobraniem i informacje o metodzie płatności dla administratora. |
| `displayOrderDetail` | Na stronie szczegółów zamówienia klienta w front-office. | Aby wyświetlić klientowi szczegóły opłaty za pobraniem. |
| `displayPDFInvoice` | Gdy generowana jest faktura PDF. | Aby upewnić się, że opłata za pobraniem jest prawidłowo uwzględniona i wyświetlona na fakturze. |
| `ActionAdminControllerSetMedia` | Gdy kontroler administracyjny jest inicjowany, a jego zasoby multimedialne są ustawiane. | Aby dołączyć zasoby CSS/JS modułu specyficzne dla administratora (np. `admin_codpro.css`, `adminCodProCarriersFees.js`, `adminCodProDashboard.js`). |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie deweloperskie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Upewnij się, że zawsze używasz wersji modułu kompatybilnej z Twoją konkretną instalacją PrestaShop.
