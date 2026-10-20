---
title: "Sprzedawaj klucze CD / klucze licencyjne - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Sprzedawaj klucze CD / klucze licencyjne” od MyPresta.eu."
sidebar:
  label: "Sprzedawaj klucze CD / klucze licencyjne - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Sell CDKeys / License keys na MyPresta.eu](https://mypresta.eu/modules/ordering-process/sell-cdkeys-license-keys.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/sell-cdkeys-license-keys/)
>
> ---


# Sprzedawaj klucze CD / klucze licencyjne

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Sprzedawaj klucze CD / klucze licencyjne)

Jest to główny obszar konfiguracji, w którym definiujesz, jak moduł się zachowuje, kiedy wysyłać klucze i ogólne ustawienia.

#### Zakładka Ustawienia ogólne

-   **Włączony:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł będzie przetwarzał zamówienia, wysyłał klucze CD i wyświetlał klucze klienta w front office zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Moduł zatrzyma wszystkie swoje operacje. Żadne klucze nie zostaną wysłane automatycznie, a sekcja „Moje klucze” klienta może zniknąć lub stać się nieaktywna.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włącz to po skonfigurowaniu wszystkiego, aby rozpocząć sprzedaż kluczy. Wyłącz tymczasowo, jeśli musisz przeprowadzić konserwację lub przestać sprzedawać klucze cyfrowe.
-   **Wybierz statusy zamówień:**
    -   **Co robi to ustawienie:** Określa, które statusy zamówień spowodują automatyczne wysłanie kluczy CD do klientów. Możesz wybrać wiele statusów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy osiągnięty zostanie wybrany status:* Moduł sprawdzi zamówienie pod kątem produktów z kluczami CD i wyśle klucze.
        -   *Gdy osiągnięty zostanie niewybrany status:* Żadne klucze nie zostaną wysłane, nawet jeśli zamówienie zawiera produkty z kluczami CD.
    -   **Zalecana wartość:** „Płatność zaakceptowana” i ewentualnie „Dostarczono”, jeśli chcesz najpierw upewnić się, że produkty fizyczne również zostały dostarczone.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klucze zostały wysłane natychmiast po płatności, wybierz „Płatność zaakceptowana”. Jeśli używasz ręcznej metody płatności, takiej jak przelew bankowy, możesz wybrać „Płatność zaakceptowana” po ręcznym potwierdzeniu płatności.
-   **Grupy klientów uprawnione do otrzymania klucza CD:**
    -   **Co robi to ustawienie:** Pozwala ograniczyć dostawę kluczy CD do określonych grup klientów (np. „Klienci”, „Odwiedzający”, „Goście”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy klient należy do wybranej grupy:* Otrzyma klucze CD, jeśli wszystkie inne warunki zostaną spełnione.
        -   *Gdy klient NIE należy do wybranej grupy:* Nie otrzyma kluczy CD, nawet jeśli zakupi produkt z kluczem CD.
    -   **Zalecana wartość:** „Klient” (i „Gość”, jeśli zezwalasz na zakupy jako gość dla produktów cyfrowych).
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz ograniczyć to do „Klientów”, jeśli chcesz zachęcić do tworzenia konta lub jeśli masz specjalne grupy B2B, które otrzymują różne typy kluczy.
-   **Maksymalna wartość zamówienia:**
    -   **Co robi to ustawienie:** Ustawia górny limit całkowitej wartości zamówienia, dla którego klucze CD zostaną automatycznie wysłane. Zamówienia przekraczające tę wartość nie spowodują automatycznej dostawy kluczy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Całkowita wartość zamówienia poniżej lub równa maksimum:* Klucze są wysyłane automatycznie.
        -   *Całkowita wartość zamówienia powyżej maksimum:* Klucze NIE są wysyłane automatycznie. Musiałbyś wysłać je ręcznie.
    -   **Zalecana wartość:** Pozostaw puste lub ustaw bardzo wysoką wartość (np. 999999), jeśli nie chcesz żadnych ograniczeń wartości.
    -   **Scenariusz / przykład dla sprzedawcy:** Użyj tego jako środka zapobiegania oszustwom. Jeśli zauważysz wiele oszukańczych zamówień o wysokiej wartości, możesz ustawić limit, aby ręcznie je przeglądać przed wydaniem drogich kluczy.
-   **Wyślij wiele kodów w jednym e-mailu:**
    -   **Co robi to ustawienie:** Kontroluje, czy wiele kluczy CD dla tego samego produktu w jednym zamówieniu jest wysyłanych w jednym e-mailu, czy w oddzielnych e-mailach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli klient kupi 3 sztuki „Gry X”, otrzyma jeden e-mail zawierający wszystkie 3 klucze do „Gry X”.
        -   *Gdy wyłączone:* Jeśli klient kupi 3 sztuki „Gry X”, otrzyma 3 oddzielne e-maile, każdy z jednym kluczem do „Gry X”.
    -   **Zalecana wartość:** TAK (ogólnie lepsze dla doświadczenia klienta i zmniejsza bałagan w skrzynce odbiorczej).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli klient kupuje „pakiet 4” gry, wysłanie wszystkich 4 kluczy w jednym e-mailu jest znacznie jaśniejsze niż 4 oddzielne e-maile.
-   **Tytuł e-maila:**
    -   **Co robi to ustawienie:** Pozwala dostosować temat e-maila wysyłanego do klientów zawierającego ich klucze CD.
    -   **Efekt zmiany tego ustawienia:** Temat e-maila będzie odzwierciedlał Twój niestandardowy tytuł, ułatwiając klientom identyfikację e-maila.
    -   **Zalecana wartość:** Coś jasnego i profesjonalnego, np. „Twoje klucze CD / licencje ze sklepu [Nazwa Twojego sklepu] - Zamówienie #[ID zamówienia]”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jasny temat, taki jak „Twoje klucze do gry dla zamówienia #12345”, pomaga klientom szybko znaleźć swoje klucze.
-   **Zmień status zamówienia:**
    -   **Co robi to ustawienie:** Po pomyślnym wysłaniu kluczy CD, ta opcja pozwala automatycznie zmienić status zamówienia na nowy, określony status.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone i wybrany status:* Status zamówienia zostanie automatycznie zaktualizowany (np. z „Płatność zaakceptowana” na „Klucze CD wysłane”).
        -   *Gdy wyłączone:* Status zamówienia pozostanie taki, jaki był po początkowym wyzwoleniu (np. „Płatność zaakceptowana”).
    -   **Zalecana wartość:** TAK, i wybierz wyraźny status, taki jak „Klucze CD wysłane” (może być konieczne utworzenie tego statusu w PrestaShop > Statusy zamówień).
    -   **Scenariusz / przykład dla sprzedawcy:** Pomaga to szybko zidentyfikować zamówienia, dla których klucze zostały już dostarczone, poprawiając przepływ pracy zarządzania zamówieniami.
-   **Wybierz status zamówienia (dla zmiany statusu):**
    -   **Co robi to ustawienie:** Jeśli „Zmień status zamówienia” jest włączone, ta lista rozwijana pozwala wybrać konkretny status zamówienia do zastosowania po wysłaniu kluczy.
    -   **Efekt zmiany tego ustawienia:** Wybrany status zostanie zastosowany do zamówienia.
    -   **Zalecana wartość:** Niestandardowy status, taki jak „Klucze CD wysłane” lub „Produkt cyfrowy dostarczony”.
    -   **Scenariusz / przykład dla sprzedawcy:** Utworzenie konkretnego statusu, takiego jak „Klucze CD wysłane”, pozwala filtrować zamówienia i dokładnie zobaczyć, które z nich miały swoje produkty cyfrowe zrealizowane.
-   **Dołącz klucze do faktury:**
    -   **Co robi to ustawienie:** Określa, czy dostarczone klucze CD powinny być również wydrukowane na fakturze klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klucze pojawią się na fakturze PDF wygenerowanej dla zamówienia.
        -   *Gdy wyłączone:* Klucze zostaną wysłane tylko e-mailem i/lub pojawią się w sekcji „Moje klucze”, ale nie na fakturze.
    -   **Zalecana wartość:** TAK (zapewnia dodatkowy zapis dla klienta).
    -   **Scenariusz / przykład dla sprzedawcy:** Niektórzy klienci wolą mieć wszystkie szczegóły zakupu, w tym klucze, na swojej fakturze do celów ewidencji lub podatkowych.
-   **Włącz paginację:**
    -   **Co robi to ustawienie:** Włącza paginację dla listy kluczy CD wyświetlanych w sekcji „Moje klucze” klienta w front office.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli klient ma wiele kluczy, zostaną one wyświetlone na wielu stronach, poprawiając czas ładowania i czytelność.
        -   *Gdy wyłączone:* Wszystkie klucze zostaną wyświetlone na jednej stronie.
    -   **Zalecana wartość:** TAK (zwłaszcza jeśli klienci mogą gromadzić wiele kluczy).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient, który regularnie kupuje klucze do gier, doceni paginację, aby szybko znaleźć konkretne klucze bez przewijania bardzo długiej listy.
-   **Liczba elementów paginacji:**
    -   **Co robi to ustawienie:** Jeśli paginacja jest włączona, ustawia, ile kluczy CD jest wyświetlanych na stronie w sekcji „Moje klucze” klienta.
    -   **Efekt zmiany tego ustawienia:** Kontroluje gęstość listy kluczy na każdej stronie.
    -   **Zalecana wartość:** 10-20 (dobra równowaga dla czytelności).
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawienie tej wartości na 15 oznacza, że klient z 30 kluczami zobaczy 2 strony kluczy.

#### Zakładka Ustawienia importu CSV

-   **Separator wierszy pliku CSV:**
    -   **Co robi to ustawienie:** Określa znak używany do oddzielania poszczególnych wierszy (linii) w pliku CSV podczas importowania kluczy CD.
    -   **Efekt zmiany tego ustawienia:** Moduł używa tego znaku do prawidłowego parsowania pliku CSV na pojedyncze wpisy kluczy. Nieprawidłowy separator doprowadzi do błędów importu.
    -   **Zalecana wartość:** `\n` (znak nowej linii, standard dla większości plików CSV).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja lista kluczy to `klucz1\nklucz2\nklucz3`, moduł musi wiedzieć, że `\n` oddziela każdy klucz.
-   **Separator kolumn pliku CSV:**
    -   **Co robi to ustawienie:** Określa znak używany do oddzielania kolumn (pól) w każdym wierszu pliku CSV podczas importowania kluczy CD.
    -   **Efekt zmiany tego ustawienia:** Moduł używa tego znaku do prawidłowego identyfikowania różnych punktów danych (np. klucz, ID grupy) w każdym wierszu. Nieprawidłowy separator doprowadzi do błędów importu.
    -   **Zalecana wartość:** `;` (średnik) lub `,` (przecinek), w zależności od sposobu generowania plików CSV.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój plik CSV to `klucz1;id_produktu_1;id_grupy_1`, moduł musi wiedzieć, że `;` oddziela pola.

#### Zakładka Analityka i oszustwa

-   **CDKEYS\_ANALYTICS\_DEFAULT\_CHART, CDKEYS\_ANALYTICS\_PERIOD, CDKEYS\_ANALYTICS\_CHART\_DAYS, CDKEYS\_ANALYTICS\_CHART\_WEEKS, CDKEYS\_ANALYTICS\_CHART\_MONTHS, CDKEYS\_ANALYTICS\_PREDICTION\_DAYS, CDKEYS\_ANALYTICS\_TOP\_LIMIT, CDKEYS\_ANALYTICS\_MIN\_SALES, CDKEYS\_ANALYTICS\_SHOW\_EMPTY\_GROUPS, CDKEYS\_ANALYTICS\_INCLUDE\_INACTIVE:**
    -   **Co robią te ustawienia:** Są to wewnętrzne klucze konfiguracyjne związane z panelem analitycznym i wykrywaniem oszustw modułu. Kontrolują sposób wyświetlania, agregowania i filtrowania danych w sekcji analitycznej panelu administracyjnego modułu.
    -   **Efekt zmiany tych ustawień:** Dostosowuje wizualną reprezentację i punkty danych wyświetlane w panelu modułu, pomagając monitorować kluczowe sprzedaże i potencjalne wzorce oszustw.
    -   **Zalecana wartość:** Wartości domyślne są zazwyczaj w porządku. Dostosuj tylko, jeśli potrzebujesz konkretnych widoków raportowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz dostosować `CDKEYS_ANALYTICS_PERIOD`, aby wyświetlać trendy sprzedaży w ciągu tygodnia zamiast miesiąca, lub `CDKEYS_ANALYTICS_TOP_LIMIT`, aby zobaczyć więcej najlepiej sprzedających się grup kluczy.
-   **CDKEYS\_ALERT\_COOLDOWN\_HOURS:**
    -   **Co robi to ustawienie:** Definiuje okres odświeżania w godzinach dla alertów o oszustwach. Jeśli alert zostanie wyzwolony dla klienta, kolejny alert dla tego samego klienta nie zostanie wyzwolony w tym okresie odświeżania.
    -   **Efekt zmiany tego ustawienia:** Zapobiega spamowaniu alertami w przypadku powtarzających się prób oszustwa od tego samego klienta w krótkim czasie.
    -   **Zalecana wartość:** 24-48 godzin (aby dać czas na ręczny przegląd bez ciągłego ponownego alertowania).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli klient próbuje wielu oszukańczych zamówień w ciągu godziny, zapobiega to otrzymywaniu alertu dla każdej próby, konsolidując go w jeden początkowy alert.
-   **CDKEYS\_EXPORT\_MASK\_CODES:**
    -   **Co robi to ustawienie:** Podczas eksportowania danych kluczy CD, to ustawienie określa, czy rzeczywiste kody kluczy powinny być maskowane (ukryte) ze względów bezpieczeństwa.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Eksportowane dane będą wyświetlać zamaskowane kody (np. `*****`).
        -   *Gdy wyłączone:* Eksportowane dane będą wyświetlać pełne, niezamaskowane kody kluczy.
    -   **Zalecana wartość:** TAK (dla bezpieczeństwa, zwłaszcza jeśli udostępniasz pliki eksportu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli musisz udostępnić listę użytych kluczy dostawcy, ale nie chcesz ujawniać rzeczywistych wartości kluczy, włącz maskowanie.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł dodaje kilka nowych sekcji do menu Panelu administracyjnego PrestaShop, zazwyczaj pod główną zakładką „Klucze CD” lub „Licencje”.

#### 2.2.1 Klucze CD > Grupy (AdminCdKeysGroupsController)

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Klucze CD > Grupy**
-   **Cel:** Ten ekran pozwala tworzyć i zarządzać grupami kluczy CD. Grupa to zasadniczo pula kluczy, które można przypisać do jednego lub więcej produktów. Jest to kluczowe dla zarządzania zapasami kluczy.
-   **Dostępne działania i ustawienia:**
    -   **Dodaj nową grupę:** Utwórz nową grupę z nazwą (np. „Klucze Windows 11 Pro”, „Gra X Edycja Deluxe”).
    -   **Edytuj grupę:** Zmodyfikuj nazwę istniejącej grupy.
    -   **Usuń grupę:** Usuń grupę (upewnij się, że żadne aktywne produkty nie są z nią powiązane i żadne klucze nie są przypisane).
    -   **Wyświetl klucze w grupie:** Przejdź bezpośrednio do listy kluczy powiązanych z konkretną grupą.
-   **Efekt zmian:**
    -   Utworzenie grupy pozwala kategoryzować klucze i łączyć je z produktami.
    -   Usunięcie grupy spowoduje usunięcie jej powiązania z produktami i kluczami, co może spowodować problemy, jeśli klucze są nadal potrzebne.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Przed zaimportowaniem jakichkolwiek kluczy utwórz grupę dla każdego odrębnego produktu lub wersji produktu, która wymaga klucza.
    2.  Przypisz odpowiednią grupę do swoich produktów (odbywa się to na stronie edycji produktu, w zakładce „Moduły” lub dedykowanej zakładce „Klucze CD” dodanej przez moduł).

#### 2.2.2 Klucze CD > Lista (AdminCdKeysListController)

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Klucze CD > Lista**
-   **Cel:** To Twoje centralne repozytorium wszystkich indywidualnych kluczy CD. Tutaj możesz importować, przeglądać i zarządzać statusem każdego klucza.
-   **Dostępne działania i ustawienia:**
    -   **Importuj CSV:** Prześlij plik CSV zawierający Twoje klucze. Podczas procesu importu określisz grupę, do której należą te klucze.
    -   **Dodaj nowy klucz:** Ręcznie dodaj pojedynczy klucz, przypisz go do grupy i ustaw jego status (np. „Dostępny”, „Użyty”).
    -   **Edytuj klucz:** Zmodyfikuj wartość, grupę lub status istniejącego klucza.
    -   **Usuń klucz:** Usuń klucz z inwentarza.
    -   **Filtruj/Szukaj:** Znajdź konkretne klucze według wartości, grupy lub statusu.
    -   **Eksportuj:** Eksportuj swój inwentarz kluczy (z opcjonalnym maskowaniem).
-   **Efekt zmian:**
    -   Importowanie kluczy uzupełnia Twój inwentarz, udostępniając je do sprzedaży.
    -   Zmiana statusu klucza (np. na „Użyty”) zapobiega jego przypisaniu do nowych zamówień.
    -   Usunięcie klucza usuwa go na stałe.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie importuj nowe partie kluczy od swoich dostawców do odpowiednich grup.
    2.  Monitoruj status „Użyty”, aby upewnić się, że klucze są prawidłowo przypisywane.
    3.  Jeśli klient zgłosi problem z kluczem, możesz go tutaj znaleźć, zweryfikować jego status i potencjalnie przypisać nowy.

#### 2.2.3 Klucze CD > Archiwum (AdminCdKeysArchiveController)

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Klucze CD > Archiwum**
-   **Cel:** Ten ekran zapewnia historyczny zapis wszystkich kluczy CD, które zostały przypisane do zamówień klientów. Działa jako dziennik audytu dystrybucji kluczy.
-   **Dostępne działania i ustawienia:**
    -   **Wyświetl przypisane klucze:** Zobacz, który klucz został przypisany do którego zamówienia, dla którego produktu i do którego klienta.
    -   **Filtruj/Szukaj:** Znajdź konkretne zarchiwizowane klucze według ID zamówienia, nazwy klienta, produktu lub wartości klucza.
    -   **Wyślij ponownie e-mail:** Opcja ponownego wysłania e-maila z kluczem CD do klienta (przydatne, jeśli twierdzi, że go nie otrzymał).
-   **Efekt zmian:** Ten ekran służy głównie do przeglądania i audytu. Działania tutaj nie zmieniają statusu kluczy w sekcji „Lista”, ale pozwalają na działania wsparcia klienta, takie jak ponowne wysyłanie e-maili.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Użyj tego ekranu, aby szybko wyszukać zakupione klucze klienta, jeśli skontaktuje się z pomocą techniczną.
    2.  Sprawdź, czy klucze zostały prawidłowo wysłane dla konkretnych zamówień.
    3.  Wyślij ponownie klucze, jeśli e-mail klienta został zgubiony lub przypadkowo usunięty.

#### 2.2.4 Strona edycji produktu (Panel administracyjny > Katalog > Produkty > Edytuj produkt)

-   **Nazwa ekranu i lokalizacja w menu:** Podczas edycji produktu poszukaj nowej zakładki lub sekcji związanej z „Kluczami CD” lub „Modułami”.
-   **Cel:** Tutaj łączysz konkretny produkt z grupą kluczy CD, oznaczając go jako „produkt z kluczem CD”.
-   **Dostępne działania i ustawienia:**
    -   **Włącz klucz CD dla tego produktu:** Przełącznik lub pole wyboru wskazujące, że ten produkt wymaga dostawy klucza CD.
    -   **Wybierz grupę kluczy CD:** Lista rozwijana do wyboru grupy kluczy, z której ten produkt powinien pobierać klucze po złożeniu zamówienia.
-   **Efekt zmian:**
    -   *Gdy włączone i wybrana grupa:* Każdy zakup tego produktu automatycznie spowoduje, że moduł przypisze dostępny klucz z wybranej grupy i wyśle go do klienta.
    -   *Gdy wyłączone:* Produkt będzie traktowany jako zwykły produkt PrestaShop, a żadne klucze nie zostaną przypisane ani wysłane.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Dla każdego sprzedawanego produktu cyfrowego, który wymaga unikalnego klucza, przejdź do jego strony edycji.
    2.  Włącz opcję Klucz CD i wybierz prawidłową grupę kluczy, którą utworzyłeś wcześniej.
    3.  Upewnij się, że masz wystarczającą liczbę kluczy w wybranej grupie, aby pokryć potencjalne sprzedaże.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włączony | TAK | Główny przełącznik funkcjonalności modułu. |
| | Wybierz statusy zamówień | Płatność zaakceptowana | Wyzwala dostawę klucza, gdy zamówienie osiągnie ten status. |
| | Grupy klientów uprawnione do otrzymania klucza CD | Klient, Gość | Ogranicza dostawę klucza do określonych grup klientów. |
| | Maksymalna wartość zamówienia | Puste (bez limitu) | Ustawia limit wartości dla automatycznej dostawy klucza (zapobieganie oszustwom). |
| | Wyślij wiele kodów w jednym e-mailu | TAK | Łączy wiele kluczy dla tego samego produktu w jeden e-mail. |
| | Tytuł e-maila | Twoje klucze CD ze sklepu [Nazwa sklepu] | Dostosowuje temat e-maili z dostawą kluczy. |
| | Zmień status zamówienia | TAK | Automatycznie aktualizuje status zamówienia po dostarczeniu klucza. |
| | Wybierz status zamówienia (dla zmiany statusu) | „Klucze CD wysłane” (niestandardowy) | Konkretny status do zastosowania po wysłaniu kluczy. |
| | Dołącz klucze do faktury | TAK | Drukuje dostarczone klucze na fakturze PDF klienta. |
| | Włącz paginację | TAK | Włącza paginację dla „Moich kluczy” na koncie klienta. |
| | Liczba elementów paginacji | 10-20 | Liczba kluczy wyświetlanych na stronie w „Moich kluczach”. |
| | Separator wierszy pliku CSV | `\n` | Znak oddzielający wiersze w imporcie kluczy CSV. |
| | Separator kolumn pliku CSV | `;` lub `,` | Znak oddzielający kolumny w imporcie kluczy CSV. |
| | CDKEYS\_EXPORT\_MASK\_CODES | TAK | Maskuje kody kluczy w plikach eksportu dla bezpieczeństwa. |
| **Klucze CD > Grupy** | Dodaj/Edytuj nazwę grupy | N/A | Zarządza kategoriami/pulami kluczy. |
| **Klucze CD > Lista** | Importuj CSV | N/A | Masowo przesyła klucze do grup. |
| | Dodaj/Edytuj klucz | N/A | Ręcznie zarządza indywidualnymi wartościami kluczy i statusem. |
| **Klucze CD > Archiwum** | Wyślij ponownie e-mail | N/A | Ponownie wysyła e-mail z dostawą klucza dla konkretnego zamówienia. |
| **Strona edycji produktu** | Włącz klucz CD dla tego produktu | TAK | Oznacza produkt jako wymagający dostawy klucza CD. |
| | Wybierz grupę kluczy CD | (Konkretna grupa) | Łączy produkt z pulą kluczy do realizacji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują kluczy CD. Co powinienem najpierw sprawdzić?**
O1:

1.  **Moduł włączony?** Przejdź do `Moduły > Menedżer modułów > Sprzedawaj klucze CD / klucze licencyjne` i upewnij się, że moduł jest „Włączony”.
2.  **Status zamówienia:** Sprawdź konfigurację modułu w sekcji „Wybierz statusy zamówień”. Czy bieżący status zamówienia klienta (np. „Płatność zaakceptowana”) jest wybrany na tej liście?
3.  **Produkt powiązany z grupą:** Na stronie edycji produktu (`Katalog > Produkty > Edytuj produkt`) upewnij się, że opcja „Włącz klucz CD dla tego produktu” jest zaznaczona i wybrana jest prawidłowa „Grupa kluczy CD”.
4.  **Klucze w grupie:** Przejdź do `Klucze CD > Lista` i sprawdź, czy w grupie przypisanej do produktu są dostępne (nieużywane) klucze. Jeśli nie, zaimportuj więcej kluczy.
5.  **Grupa klientów:** Sprawdź, czy grupa klienta ma prawo do otrzymywania kluczy w sekcji „Grupy klientów uprawnione do otrzymania klucza CD” w konfiguracji modułu.
6.  **Konfiguracja e-maila:** Sprawdź ustawienia e-maila w PrestaShop (`Zaawansowane > E-mail`), aby upewnić się, że e-maile są prawidłowo wysyłane ze Twojego sklepu. Poproś również klienta o sprawdzenie folderu spam/śmieci.

**P2: Zaimportowałem plik CSV, ale klucze się nie wyświetlają lub są nieprawidłowe.**
O2:

1.  **Ustawienia separatorów:** Dokładnie sprawdź ustawienia „Separator wierszy pliku CSV” i „Separator kolumn pliku CSV” w konfiguracji modułu. Muszą one dokładnie odpowiadać strukturze Twojego pliku CSV. Częste problemy to użycie przecinka (`,`) zamiast średnika (`;`) lub odwrotnie.
2.  **Format pliku:** Upewnij się, że Twój plik CSV jest zwykłym tekstem, a nie plikiem Excela zapisanym jako CSV ze złożonym formatowaniem.
3.  **Grupa docelowa:** Czy podczas importu wybrałeś prawidłową grupę kluczy CD?

**P3: Sekcja „Moje klucze” nie pojawia się na koncie klienta.**
O3:

1.  **Moduł włączony:** Upewnij się, że moduł jest aktywny.
2.  **Kompatybilność z motywem:** Chociaż moduł używa standardowych hooków PrestaShop, niektóre mocno dostosowane motywy mogą nadpisywać domyślny hook `displayCustomerAccount`. Sprawdź, czy Twój motyw zmodyfikował ten obszar. Jeśli tak, może być konieczne niewielkie dostosowanie motywu (patrz sekcja 7.6 dla szablonów hooków).
3.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (`Zaawansowane > Wydajność > Wyczyść pamięć podręczną`).

**P4: Jak utworzyć nowy status zamówienia, taki jak „Klucze CD wysłane”?**
O4:

1.  Przejdź do `Parametry sklepu > Ustawienia zamówień > Statusy`.
2.  Kliknij „Dodaj nowy status zamówienia”.
3.  Nadaj mu jasną nazwę (np. „Klucze CD wysłane”).
4.  Wybierz wyraźny kolor (np. jasnoniebieski), aby łatwo go zidentyfikować na liście zamówień.
5.  Upewnij się, że opcja „Uważaj powiązane zamówienie za zatwierdzone” jest zaznaczona, jeśli chcesz, aby było ono traktowane jako zrealizowane zamówienie.
6.  Zapisz nowy status, a następnie wróć do konfiguracji modułu, aby wybrać go dla opcji „Wybierz status zamówienia (dla zmiany statusu)”.

**P5: Czy mogę ręcznie przypisać klucz do zamówienia lub klienta?**
O5: Moduł przede wszystkim automatyzuje ten proces. Jeśli musisz ręcznie przypisać klucz (np. w celu wymiany), zazwyczaj wykonujesz następujące czynności:

1.  Przejdź do `Klucze CD > Lista`, znajdź dostępny klucz i zanotuj jego wartość.
2.  Przejdź do zamówienia klienta (`Zamówienia > Zamówienia`) i dodaj prywatną notatkę z kluczem.
3.  Ręcznie wyślij klucz e-mailem do klienta.
4.  Następnie wróć do `Klucze CD > Lista`, znajdź ten klucz i ręcznie zmień jego status na „Użyty”, aby zapobiec jego ponownemu przypisaniu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Sprzedawaj klucze CD / klucze licencyjne”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł wykorzystuje standardowy wzorzec PrestaShop MVC (Model-View-Controller). Rozszerza `Module` dla swojej podstawowej funkcjonalności i `AdminController` dla swoich interfejsów Panelu administracyjnego. Wykorzystuje `ObjectModel` PrestaShop do zarządzania grupami kluczy CD, indywidualnymi kluczami i ich historią użycia. Dostawa kluczy jest głównie sterowana zdarzeniami, wyzwalana przez hooki `actionOrderStatusPostUpdate` i `actionOrderStatusUpdate`. Interakcja z front office jest minimalna, głównie zapewniając sekcję „Moje klucze” dla klienta.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

-   `controllers/front/index.php`:
    -   **Nazwa klasy:** `CdkeysIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Prawdopodobnie placeholder lub kontroler przekierowujący. W wielu modułach `index.php` w katalogu kontrolerów front office może obsługiwać domyślne routowanie lub po prostu przekierowywać do bardziej specyficznego kontrolera.
-   `controllers/front/mykeys.php`:
    -   **Nazwa klasy:** `CdkeysMykeysModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje wyświetlanie zakupionych kluczy CD klienta w sekcji „Moje konto”. Pobiera rekordy `cdkey_used` powiązane z bieżącym klientem, stosuje paginację, jeśli jest włączona, i renderuje `views/templates/front/mykeys.tpl`.

#### Kontrolery Panelu administracyjnego

-   `controllers/admin/AdminCdKeysArchiveController.php`:
    -   **Nazwa zakładki:** Klucze CD > Archiwum
    -   **Zarządzana encja:** `cdkey_used` (rekordy przypisanych kluczy)
    -   **Odpowiedzialność:** Zapewnia interfejs zarządzania listą dla wszystkich kluczy CD, które zostały przypisane do zamówień. Umożliwia przeglądanie, filtrowanie i potencjalne ponowne wysyłanie e-maili z kluczami. Wykorzystuje `HelperList` do wyświetlania.
-   `controllers/admin/AdminCdKeysGroupsController.php`:
    -   **Nazwa zakładki:** Klucze CD > Grupy
    -   **Zarządzana encja:** `cdkey_group`
    -   **Odpowiedzialność:** Zarządza tworzeniem, edycją i usuwaniem grup kluczy CD. Te grupy działają jako kategorie dla Twoich kluczy i są powiązane z produktami. Wykorzystuje `HelperList` i `HelperForm` do swoich interfejsów.
-   `controllers/admin/AdminCdKeysListController.php`:
    -   **Nazwa zakładki:** Klucze CD > Lista
    -   **Zarządzana encja:** `cdkey`
    -   **Odpowiedzialność:** Zarządza inwentarzem indywidualnych kluczy CD. Obejmuje to importowanie plików CSV, dodawanie/edycję/usuwanie kluczy i przeglądanie ich statusu (dostępne, użyte). Wykorzystuje `HelperList` i `HelperForm`.
-   `controllers/admin/index.php`:
    -   **Nazwa zakładki:** Klucze CD (Główny pulpit nawigacyjny)
    -   **Zarządzana encja:** N/A (Pulpit nawigacyjny)
    -   **Odpowiedzialność:** Prawdopodobnie służy jako główny pulpit nawigacyjny modułu, wyświetlając analizy, statystyki kluczy i potencjalne alerty o oszustwach. Agreguje dane z tabel `cdkey_used` i `cdkey`.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu nie wskazuje na istnienie jawnego katalogu `classes/`. Sugeruje to, że podstawowe definicje `ObjectModel` i główna logika biznesowa są prawdopodobnie zawarte w samym pliku `cdkeys.php` lub w odpowiednich plikach kontrolerów.

Jeśli definicje `ObjectModel` są obecne w `cdkeys.php`, zazwyczaj wyglądałyby następująco:

-   `CdKeyGroup` (dla tabeli `ps_cdkey_group`): Zarządza grupami kluczy.
    -   `$definition` zawierałoby `id_cdkey_group`, `name`.
-   `CdKey` (dla tabeli `ps_cdkey`): Zarządza indywidualnymi kluczami.
    -   `$definition` zawierałoby `id_cdkey`, `id_cdkey_group`, `key_value`, `status` (np. „available”, „used”).
-   `CdKeyUsed` (dla tabeli `ps_cdkey_used`): Zarządza przypisanymi kluczami.
    -   `$definition` zawierałoby `id_cdkey_used`, `id_cdkey`, `id_order`, `id_customer`, `id_product`, `date_add`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `cdkeys/lib/emailTemplatesManager/js/emailTemplatesManager.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Zarządza interfejsem użytkownika do tworzenia, edycji i wyboru szablonów e-maili w konfiguracji modułu. Prawdopodobnie obsługuje wywołania AJAX do zapisywania treści szablonów, podglądu e-maili i przełączania między różnymi wersjami szablonów.
-   `cdkeys/lib/searchTool/views/js/autocomplete.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wyszukiwania w interfejsach administracyjnych modułu (np. wyszukiwanie produktów, klientów lub grup kluczy). Wiąże się z polami wejściowymi i wykonuje żądania AJAX w celu pobrania sugestii.
-   `cdkeys/views/js/adminCdKeysDashboard.js`:
    -   **Zakres:** Panel administracyjny (AdminCdKeysDashboardController lub główny pulpit nawigacyjny modułu).
    -   **Odpowiedzialność:** Obsługuje interaktywne elementy głównego pulpitu nawigacyjnego modułu. Może to obejmować renderowanie wykresów (np. za pomocą Chart.js lub podobnej biblioteki), filtrowanie danych i dynamiczne aktualizacje statystyk.
-   `cdkeys/views/js/cdkeys-dashboard-demo-console.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Prawdopodobnie skrypt deweloperski/debugowania lub konsola demonstracyjna dla pulpitu nawigacyjnego, ewentualnie logująca zdarzenia lub dostarczająca dane testowe. Nie powinien być aktywny w środowisku produkcyjnym.
-   `cdkeys/views/js/cdkeys-fraud-demo-console.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Podobnie jak konsola demonstracyjna pulpitu nawigacyjnego, jest to prawdopodobnie skrypt deweloperski/debugowania dla funkcji wykrywania oszustw. Nie powinien być aktywny w środowisku produkcyjnym.
-   `cdkeys/views/js/cdkeys-pagination.js`:
    -   **Zakres:** Front Office (`mykeys.tpl`).
    -   **Odpowiedzialność:** Obsługuje logikę po stronie klienta dla paginacji w sekcji „Moje klucze” klienta. Może to obejmować wywołania AJAX w celu załadowania nowych stron kluczy bez pełnego przeładowania strony lub po prostu zarządzanie wyświetlaniem numerów stron i nawigacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `cdkeys/lib/emailTemplatesManager/css/emailTemplatesManager.css`:
    -   **Zakres:** Panel administracyjny.
    -   **Główne komponenty interfejsu użytkownika:** Stylizuje interfejs zarządzania szablonami e-maili, w tym formularze, przyciski i obszary podglądu.
    -   **Kluczowe selektory klas CSS:** `.email-template-manager`, `.template-form`, `.template-preview`.
-   `cdkeys/lib/searchTool/views/css/autocomplete.css`:
    -   **Zakres:** Panel administracyjny.
    -   **Główne komponenty interfejsu użytkownika:** Stylizuje rozwijane listy autouzupełniania i pola wejściowe.
    -   **Kluczowe selektory klas CSS:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
-   `cdkeys/views/css/admin_cdkeys.css`:
    -   **Zakres:** Panel administracyjny.
    -   **Główne komponenty interfejsu użytkownika:** Ogólne style dla stron administracyjnych modułu, w tym list, formularzy i elementów pulpitu nawigacyjnego.
    -   **Kluczowe selektory klas CSS:** `.cdkeys-admin-panel`, `.cdkeys-table`, `.cdkeys-form-group`.
-   `cdkeys/views/css/cdkeys-admin.css`:
    -   **Zakres:** Panel administracyjny.
    -   **Główne komponenty interfejsu użytkownika:** Dodatkowe lub specyficzne style dla interfejsów administracyjnych, potencjalnie nadpisujące lub rozszerzające `admin_cdkeys.css`.
    -   **Kluczowe selektory klas CSS:** `.cdkeys-dashboard-widget`, `.cdkeys-alert`.
-   `cdkeys/views/css/css.css`:
    -   **Zakres:** Potencjalnie zarówno Front Office, jak i Panel administracyjny, lub ogólne style użytkowe.
    -   **Główne komponenty interfejsu użytkownika:** Może zawierać podstawowe style dla elementów używanych w różnych częściach modułu.
    -   **Kluczowe selektory klas CSS:** Ogólne klasy, które mogą być stosowane do różnych elementów modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `cdkeys/views/templates/hook/adminOrder.tpl`:
    -   **Hook:** `displayAdminOrder`
    -   **Wyjście:** Wyświetla informacje o kluczu CD bezpośrednio na stronie szczegółów zamówienia w Panelu administracyjnym PrestaShop. Pozwala to administratorom szybko zobaczyć, które klucze zostały przypisane do zamówienia.
-   `cdkeys/views/templates/hook/adminOrderFraud.tpl`:
    -   **Hook:** `displayAdminOrderTop` (lub podobny, potencjalnie `displayAdminOrder`)
    -   **Wyjście:** Wyświetla informacje lub alerty związane z oszustwami dla zamówienia na stronie szczegółów zamówienia w Panelu administracyjnym.
-   `cdkeys/views/templates/hook/my-account-16.tpl`:
    -   **Hook:** `displayCustomerAccount` (dla PrestaShop 1.6.x)
    -   **Wyjście:** Dodaje link lub blok do strony „Moje konto” klienta, kierując go do sekcji „Moje klucze”.
-   `cdkeys/views/templates/hook/my-account-17.tpl`:
    -   **Hook:** `displayCustomerAccount` (dla PrestaShop 1.7.x, 8.x, 9.x)
    -   **Wyjście:** Podobnie jak `my-account-16.tpl`, ale dostosowane do innej struktury szablonów nowszych wersji PrestaShop, dodając link do sekcji „Moje klucze”.
-   `cdkeys/views/templates/hook/orderDetailDisplayed.tpl`:
    -   **Hook:** `displayOrderDetailDisplayed`
    -   **Wyjście:** Wyświetla informacje o kluczu CD na stronie szczegółów zamówienia klienta w front office.

#### Szablony administracyjne (`views/templates/admin/`)

-   `cdkeys/lib/emailTemplatesManager/views/buttonManager.tpl`:
    -   **Cel:** Renderuje przyciski lub kontrolki dla menedżera szablonów e-maili.
-   `cdkeys/lib/emailTemplatesManager/views/createTemplateForm.tpl`:
    -   **Cel:** Renderuje formularz do tworzenia nowych szablonów e-maili.
-   `cdkeys/lib/emailTemplatesManager/views/editTemplateForm.tpl`:
    -   **Cel:** Renderuje formularz do edycji istniejących szablonów e-maili.
-   `cdkeys/lib/emailTemplatesManager/views/mainForm.tpl`:
    -   **Cel:** Główny kontener lub formularz dla interfejsu zarządzania szablonami e-maili.
-   `cdkeys/lib/emailTemplatesManager/views/selectInput.tpl`:
    -   **Cel:** Renderuje rozwijane pole wyboru, prawdopodobnie do wyboru szablonów e-maili lub języków.
-   `cdkeys/lib/searchTool/views/scripts.tpl`:
    -   **Cel:** Zawiera skrypty JavaScript dla narzędzia wyszukiwania/funkcji autouzupełniania.
-   `cdkeys/views/templates/admin/cdkeys/helpers/list/list_action_email.tpl`:
    -   **Cel:** Renderuje konkretny przycisk akcji (np. „Wyślij ponownie e-mail”) w tabeli `HelperList` w kontrolerach administracyjnych (np. `AdminCdKeysArchiveController`).
-   `cdkeys/views/templates/admin/customerGroups.tpl`:
    -   **Cel:** Renderuje interfejs wyboru grup klientów w konfiguracji modułu.
-   `cdkeys/views/templates/admin/getCombinations.tpl`:
    -   **Cel:** Potencjalnie używane do wyświetlania lub wybierania kombinacji produktów związanych z kluczami CD (np. jeśli różne kombinacje wymagają różnych grup kluczy).
-   `cdkeys/views/templates/admin/orderstates.tpl`:
    -   **Cel:** Renderuje rozwijaną listę wielokrotnego wyboru dla „Wybierz statusy zamówień” w konfiguracji modułu.
-   `cdkeys/views/templates/admin/orderstatesRadio.tpl`:
    -   **Cel:** Renderuje wybór przycisków radiowych dla „Wybierz status zamówienia” (dla zmiany statusu) w konfiguracji modułu.
-   `cdkeys/views/templates/admin/script.tpl`:
    -   **Cel:** Ogólne włączenie skryptów dla stron administracyjnych, prawdopodobnie dla JS specyficznego dla modułu.

#### Szablony Front Office (`views/templates/front/`)

-   `cdkeys/views/templates/front/mykeys.tpl`:
    -   **Cel:** Główny szablon do wyświetlania listy zakupionych kluczy CD klienta w sekcji „Moje konto”. Będzie iterował przez dane `cdkey_used` i prezentował klucze, szczegóły zamówienia i potencjalnie kontrolki paginacji.

#### Szablony e-maili (`views/templates/email/`)

-   `cdkeys/views/templates/email/multikey-instance.tpl`:
    -   **Cel:** To jest podstawowy szablon e-maila wysyłanego do klientów zawierającego ich klucze CD. Będzie dynamicznie wypełniany imieniem klienta, szczegółami zamówienia i rzeczywistymi kluczami.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_cdkey_group`: Przechowuje informacje o grupach kluczy CD.
    -   `id_cdkey_group` (PK)
    -   `name`
    -   `date_add`
    -   `date_upd`
-   `ps_cdkey`: Przechowuje indywidualne klucze CD.
    -   `id_cdkey` (PK)
    -   `id_cdkey_group` (FK do `ps_cdkey_group`)
    -   `key_value` (rzeczywisty ciąg klucza CD)
    -   `status` (np. „available”, „used”)
    -   `date_add`
    -   `date_upd`
-   `ps_cdkey_used`: Przechowuje rekordy kluczy CD przypisanych do zamówień.
    -   `id_cdkey_used` (PK)
    -   `id_cdkey` (FK do `ps_cdkey`)
    -   `id_order` (FK do `ps_orders`)
    -   `id_customer` (FK do `ps_customer`)
    -   `id_product` (FK do `ps_product`)
    -   `date_add`

#### Rekordy konfiguracji (`ps_configuration`)

-   `CDKEYS_ENABLED`: (bool) Główny przełącznik.
-   `CDKEYS_OSTATES`: (string) Lista statusów zamówień oddzielonych przecinkami dla dostawy klucza.
-   `CDKEYS_GROUPS`: (string) Lista grup klientów oddzielonych przecinkami dla dostawy klucza.
-   `CDKEYS_MAX_ORDERTOTAL`: (float) Maksymalna wartość zamówienia dla automatycznej dostawy.
-   `CDKEY_HOWDELIVER`: (bool) Wyślij wiele kodów w jednym e-mailu.
-   `CDKEYS_MULTITITLE`: (string) Tytuł tematu e-maila.
-   `CDKEY_STATUSCHANGE`: (bool) Zmień status zamówienia po dostawie.
-   `CDKEYS_OSTATES_RADIO`: (int) ID statusu zamówienia, na który ma zostać zmieniony.
-   `CDKEY_INC_INV`: (bool) Dołącz klucze do faktury.
-   `CDKEY_PAGINATION`: (bool) Włącz paginację dla Moich kluczy.
-   `CDKEY_PAGINATION_NB`: (int) Elementy na stronę dla paginacji Moich kluczy.
-   `IV_ROW_DELIMITER`: (string) Separator wierszy CSV.
-   `IV_COL_DELIMITER`: (string) Separator kolumn CSV.
-   `CDKEYS_ANALYTICS_*`: Różne ustawienia dla analityki pulpitu nawigacyjnego.
-   `CDKEYS_ALERT_COOLDOWN_HOURS`: (int) Czas odświeżania dla alertów o oszustwach.
-   `CDKEYS_EXPORT_MASK_CODES`: (bool) Maskuj kody podczas eksportu.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Po zaktualizowaniu (i zapisaniu) statusu zamówienia. | Główny wyzwalacz dostawy klucza CD. Sprawdza, czy nowy status odpowiada skonfigurowanym stanom i wysyła klucze. |
| `displayAdminOrder` | Renderuje zawartość na stronie szczegółów zamówienia w Panelu administracyjnym. | Wyświetla przypisane klucze CD dla bieżącego zamówienia w panelu administracyjnym. |
| `ActionAdminControllerSetMedia` | Gdy kontroler administracyjny jest inicjalizowany i ustawiane są media (JS/CSS). | Wstrzykuje pliki JS i CSS specyficzne dla modułu do Panelu administracyjnego dla kontrolerów administracyjnych. |
| `displayCustomerAccount` | Renderuje zawartość na stronie „Moje konto” klienta. | Dodaje link lub blok dla „Moich kluczy” na koncie klienta w front office. |
| `DisplayAdminOrderTop` | Renderuje zawartość na górze strony szczegółów zamówienia w Panelu administracyjnym. | Potencjalnie używane do wyświetlania alertów o oszustwach lub informacji podsumowujących związanych z kluczami CD dla zamówienia. |
| `actionOrderStatusUpdate` | Przed aktualizacją statusu zamówienia (starszy hook, preferowany jest `actionOrderStatusPostUpdate`). | Drugorzędny lub awaryjny wyzwalacz dostawy klucza CD, zapewniający kompatybilność ze starszymi wersjami PrestaShop lub specyficznymi scenariuszami. |
| `DisplayBackOfficeHeader` | Renderuje zawartość w nagłówku wszystkich stron Panelu administracyjnego. | Wstrzykuje globalne JS/CSS Panelu administracyjnego lub elementy menu dla modułu. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front office. | Wstrzykuje JS/CSS specyficzne dla front office lub meta tagi. |
| `displayOrderDetailDisplayed` | Renderuje zawartość na stronie szczegółów zamówienia klienta w front office. | Wyświetla przypisane klucze CD bezpośrednio na stronie podsumowania zamówienia klienta. |
| `actionOrderHistoryAddAfter` | Po dodaniu wpisu historii zamówienia (zmiana statusu). | Może być używany jako alternatywny wyzwalacz dostawy klucza lub do celów logowania związanych ze zmianami statusu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Znajdziesz tam dostęp do zakupionych modułów i dedykowanych kanałów wsparcia.
