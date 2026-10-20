---
title: "Licznik czasu dostawy wysyłki - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Licznik czasu dostawy wysyłki” od MyPresta.eu."
sidebar:
  label: "Licznik czasu dostawy wysyłki - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Shipping delivery countdown timer na MyPresta.eu](https://mypresta.eu/modules/front-office-features/shipping-delivery-countdown-timer.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/shipping-delivery-countdown-timer/)
>
> ---


# Licznik czasu dostawy wysyłki

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym kontrolujesz wszystkie aspekty licznika czasu dostawy wysyłki.

#### Ustawienia ogólne

-   **Włączony / Wyłączony (Przełącznik)**
    *   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całego modułu w Twoim sklepie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony:* Licznik czasu będzie wyświetlany w Twoim front office zgodnie z innymi ustawieniami.
        *   *Gdy wyłączony:* Licznik czasu nie będzie widoczny nigdzie w Twoim sklepie.
    *   **Zalecana wartość:** **Włączony** (po skonfigurowaniu).
    *   **Scenariusz / przykład dla sprzedawcy:** Konfigurujesz moduł po raz pierwszy i chcesz go w pełni skonfigurować przed uruchomieniem. Będziesz go trzymać w stanie „Wyłączony” do momentu gotowości, a następnie przełączysz na „Włączony”.

#### Wyświetlanie i projekt

-   **Gdzie chcesz wyświetlać licznik? (Pola wyboru)**

    *   **Co robi to ustawienie:** Określa konkretne miejsca (hooki) w Twoim szablonie PrestaShop, gdzie będzie wyświetlany licznik czasu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Zaznaczenie pola (np. `displayProductAdditionalInfo`):* Licznik pojawi się w tym konkretnym obszarze Twojego szablonu.
        *   *Odznaczenie pola:* Licznik zostanie usunięty z tego konkretnego obszaru.
    *   **Zalecana wartość:** Zacznij od `displayProductAdditionalInfo` lub `displayFooterProduct` dla widoczności na stronie produktu. Możesz eksperymentować z innymi, takimi jak `displayNav1` lub `displayReassurance`, w zależności od Twojego szablonu i pożądanego efektu.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby licznik był bardzo widoczny na stronach produktów. Zaznaczyłbyś `displayProductAdditionalInfo` i `displayFooterProduct`. Jeśli chcesz go również w nagłówku, możesz zaznaczyć `displayNav1`.
    *   **Dostępne opcje:**
        *   `displayFooterProduct`
        *   `displayReassurance`
        *   `displayDeliveryTimer` (Niestandardowy hook do zaawansowanej integracji z szablonem)
        *   `displayProductAdditionalInfo`
        *   `displayNav1`
-   **Jaki projekt modułu chcesz użyć? (Przyciski radiowe)**

    *   **Co robi to ustawienie:** Pozwala wybrać wstępnie zaprojektowany styl wizualny dla Twojego licznika czasu. Obejmuje to schematy kolorów i ogólny układ.
    *   **Efekt zmiany tego ustawienia:** Wygląd licznika czasu w Twoim front office natychmiast zmieni się na wybrany projekt.
    *   **Zalecana wartość:** Wybierz projekt, który najlepiej pasuje do brandingu Twojego sklepu i kolorów szablonu.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój sklep używa dużo niebieskiego i białego. Możesz wybrać „Niebieski 400x48” lub „Niebieski 200x100”, aby licznik płynnie komponował się z estetyką Twojej witryny.

#### Godziny graniczne wysyłki

-   **Czas graniczny zakupu (Selektor czasu)**
    *   **Co robi to ustawienie:** Jest to dzienna godzina graniczna, do której zamówienie musi zostać złożone, aby kwalifikować się do wysyłki tego samego dnia.
    *   **Efekt zmiany tego ustawienia:**
        *   *Ustawienie na 14:00:* Jeśli klient zamówi przed 14:00, licznik odlicza do 14:00. Jeśli zamówi po 14:00, licznik pokaże odliczanie do godziny granicznej następnego dostępnego dnia wysyłki.
    *   **Zalecana wartość:** Ustaw to na swoją rzeczywistą dzienną godzinę graniczną wysyłki (np. 15:00 dla 15:00).
    *   **Scenariusz / przykład dla sprzedawcy:** Twój zespół magazynowy przetwarza wszystkie zamówienia otrzymane do 16:00 w celu wysyłki tego samego dnia. Ustawiłbyś to na `16:00`.

#### Codzienne wiadomości i dostępność

-   **Pokaż w niedzielę / poniedziałek / wtorek / środę / czwartek / piątek / sobotę (Pola wyboru)**

    *   **Co robi to ustawienie:** Te pola wyboru kontrolują, czy licznik czasu jest aktywny i wyświetlany w określone dni tygodnia.
    *   **Efekt zmiany tego ustawienia:**
        *   *Zaznaczenie dnia (np. „Pokaż w niedzielę”):* Licznik będzie aktywny i wyświetlany w niedziele.
        *   *Odznaczenie dnia:* Licznik nie będzie wyświetlany w tym konkretnym dniu, a wiadomość dla tego dnia nie zostanie pokazana.
    *   **Zalecana wartość:** Zaznacz wszystkie dni, w które faktycznie wysyłasz. Jeśli nie wysyłasz w weekendy, odznacz sobotę i niedzielę.
    *   **Scenariusz / przykład dla sprzedawcy:** Twoja firma działa od poniedziałku do piątku. Zaznaczyłbyś od poniedziałku do piątku i odznaczył sobotę i niedzielę.
-   **Wiadomość (Pole tekstowe dla każdego dnia: niedziela, poniedziałek, wtorek, środa, czwartek, piątek, sobota)**

    *   **Co robi to ustawienie:** Pozwala dostosować wiadomość wyświetlaną obok licznika czasu dla każdego dnia tygodnia. Możesz używać symboli zastępczych dla dynamicznej zawartości.
    *   **Efekt zmiany tego ustawienia:** Tekst wyświetlany klientowi zmieni się zgodnie z Twoim wpisem dla tego konkretnego dnia.
    *   **Zalecana wartość:** Twórz jasne, zwięzłe wiadomości. Używaj symboli zastępczych, takich jak `{time}` dla pozostałego czasu i `{date}` dla szacowanej daty dostawy.
    *   **Scenariusz / przykład dla sprzedawcy:**
        *   *Wiadomość na poniedziałek:* „Zamów w ciągu najbliższych {time}, aby otrzymać dostawę do wtorku!”
        *   *Wiadomość na sobotę (jeśli nie ma wysyłki):* „Zamówienia złożone w sobotę zostaną wysłane w poniedziałek.”

#### Wykluczenia/Włączenia produktów i kategorii

-   **Pokaż tylko dla produktów dostępnych w magazynie (Przełącznik)**

    *   **Co robi to ustawienie:** Kontroluje, czy licznik czasu jest wyświetlany tylko dla produktów, które są aktualnie dostępne w magazynie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony:* Licznik pojawi się tylko na stronach produktów, które mają dostępny stan magazynowy.
        *   *Gdy wyłączony:* Licznik pojawi się niezależnie od statusu magazynowego (choć może to być mylące dla produktów niedostępnych).
    *   **Zalecana wartość:** **Włączony**. Niewiele sensu ma pokazywanie odliczania do wysyłki dla przedmiotu, który nie może być natychmiast wysłany.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz uniknąć obiecywania szybkiej wysyłki dla przedmiotów, których nie masz. Włączenie tej opcji zapewnia, że licznik wyświetla się tylko dla dostępnych produktów.
-   **Wyklucz moduł z wybranych produktów / Widoczność modułu dla wybranych produktów (Przyciski radiowe)**

    *   **Co robi to ustawienie:** Jest to kluczowe ustawienie, które określa, czy poniższe wybory produktów/kategorii/producentów służą do *wykluczania* modułu, czy do *włączania* go (czyniąc go widocznym tylko dla tych wybranych pozycji).
    *   **Efekt zmiany tego ustawienia:**
        *   *Wyklucz moduł z wybranych produktów:* Licznik będzie wyświetlany wszędzie *oprócz* wybranych pozycji.
        *   *Widoczność modułu dla wybranych produktów:* Licznik będzie wyświetlany *tylko* dla wybranych pozycji i nigdzie indziej.
    *   **Zalecana wartość:** Zależy od Twojej strategii. Jeśli masz kilka konkretnych produktów, które nie mogą korzystać z licznika, wybierz „Wyklucz”. Jeśli chcesz, aby licznik był wyświetlany tylko dla kilku wybranych produktów, wybierz „Widoczność modułu”.
    *   **Scenariusz / przykład dla sprzedawcy:**
        *   *Wyklucz:* Sprzedajesz głównie małe przedmioty z szybką wysyłką, ale także kilka dużych mebli, których wysyłka trwa dłużej. Wybrałbyś „Wyklucz”, a następnie zaznaczył produkty meblowe.
        *   *Widoczność:* Prowadzisz specjalną promocję na konkretną kategorię produktów i chcesz, aby licznik pojawiał się tylko tam. Wybrałbyś „Widoczność modułu” i zaznaczył tę kategorię.
-   **Wykluczenia/Włączenia produktów (Wyszukaj i wybierz)**

    *   **Co robi to ustawienie:** Pozwala wyszukiwać i wybierać konkretne produkty, z których licznik ma być wykluczony lub dla których ma być widoczny (na podstawie ustawienia „Wyklucz moduł z wybranych produktów” powyżej).
    *   **Efekt zmiany tego ustawienia:** Dodaje lub usuwa konkretne produkty z listy wykluczeń/włączeń.
    *   **Zalecana wartość:** Użyj tego do precyzyjnej kontroli nad poszczególnymi produktami.
    *   **Scenariusz / przykład dla sprzedawcy:** Masz nowy produkt, który jest w przedsprzedaży i nie zostanie wysłany przez tygodnie. Dodałbyś go do listy wykluczeń, aby zapobiec wyświetlaniu odliczania.
-   **Wykluczenia/Włączenia kategorii (Wyszukaj i wybierz)**

    *   **Co robi to ustawienie:** Podobnie jak wykluczenia produktów, ale dotyczy całych kategorii.
    *   **Efekt zmiany tego ustawienia:** Dodaje lub usuwa całe kategorie z listy wykluczeń/włączeń.
    *   **Zalecana wartość:** Przydatne do stosowania reguł do dużych grup produktów.
    *   **Scenariusz / przykład dla sprzedawcy:** Wszystkie produkty w Twojej kategorii „Wykonane na zamówienie” mają długie czasy realizacji. Dodałbyś tę kategorię do listy wykluczeń.
-   **Wykluczenia/Włączenia producentów (Wyszukaj i wybierz)**

    *   **Co robi to ustawienie:** Podobnie jak wykluczenia produktów/kategorii, ale dotyczy produktów od konkretnych producentów.
    *   **Efekt zmiany tego ustawienia:** Dodaje lub usuwa producentów z listy wykluczeń/włączeń.
    *   **Zalecana wartość:** Przydatne, jeśli niektóre marki mają różne zasady wysyłki.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeden z Twoich dostawców jest znany z wolniejszej wysyłki. Dodałbyś jego producenta do listy wykluczeń.

#### Inne ustawienia

-   **mypresta\_updates, update\_, updatev\_ (Ustawienia wewnętrzne)**
    *   **Co robi to ustawienie:** Są to wewnętrzne ustawienia używane przez moduły MyPresta.eu do sprawdzania aktualizacji i zarządzania wersjami. Nie są przeznaczone do bezpośredniej interakcji sprzedawcy.
    *   **Efekt zmiany tego ustawienia:** Zmiana tych ustawień może zakłócić zdolność modułu do sprawdzania aktualizacji.
    *   **Zalecana wartość:** Pozostaw je bez zmian.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włączony | Włączony | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | Czas graniczny zakupu | Twój dzienny termin wysyłki | Definiuje dzienny czas, do którego zamówienie musi zostać złożone, aby kwalifikować się do wysyłki tego samego dnia. |
| Konfiguracja modułu | Gdzie chcesz wyświetlać licznik? | `displayProductAdditionalInfo`, `displayFooterProduct` | Wybiera miejsca w szablonie dla licznika. |
| Konfiguracja modułu | Jaki projekt modułu chcesz użyć? | Pasuje do Twojego szablonu | Styl wizualny licznika czasu. |
| Konfiguracja modułu | Pokaż w niedzielę/poniedziałek/…/sobotę | Zaznacz wszystkie dni wysyłki | Kontroluje, w które dni licznik jest aktywny. |
| Konfiguracja modułu | Wiadomość (dla każdego dnia) | „Zamów w ciągu najbliższych {time}, aby otrzymać dostawę do {date}!” | Dostosowywalny tekst wyświetlany z licznikiem. |
| Konfiguracja modułu | Pokaż tylko dla produktów dostępnych w magazynie | Włączony | Licznik pojawia się tylko dla produktów z dostępnym stanem magazynowym. |
| Konfiguracja modułu | Wyklucz moduł z wybranych produktów / Widoczność modułu dla wybranych produktów | Zależy od strategii | Definiuje, czy wybory dotyczą wykluczenia, czy włączenia. |
| Konfiguracja modułu | Wykluczenia/Włączenia produktów | Puste | Wybierz konkretne produkty do włączenia/wykluczenia. |
| Konfiguracja modułu | Wykluczenia/Włączenia kategorii | Puste | Wybierz konkretne kategorie do włączenia/wykluczenia. |
| Konfiguracja modułu | Wykluczenia/Włączenia producentów | Puste | Wybierz konkretnych producentów do włączenia/wykluczenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Licznik nie wyświetla się w moim sklepie lub wyświetla się w niewłaściwym miejscu.**
O1:

-   **Sprawdź status modułu:** Najpierw upewnij się, że moduł jest „Włączony” na stronie konfiguracji.
-   **Sprawdź wybór hooka:** Zweryfikuj, czy zaznaczyłeś prawidłowe pola wyboru „Gdzie chcesz wyświetlać licznik?”. Jeśli Twój szablon jest mocno dostosowany, niektóre standardowe hooki mogą nie być renderowane lub może być konieczne użycie innego hooka.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop buforuje stare pozycje modułów.
-   **Kompatybilność z szablonem:** Jeśli Twój szablon jest wysoce niestandardowy, może nie implementować standardowych hooków PrestaShop w zwykły sposób. Może być konieczne skonsultowanie się z twórcą szablonu lub webmasterem w celu ręcznego wstawienia hooka `displayDeliveryTimer` do plików `.tpl` Twojego szablonu.

**P2: Wiadomość odliczania jest nieprawidłowa lub czas graniczny wydaje się błędny.**
O2:

-   **Zweryfikuj „Czas graniczny zakupu”:** Sprawdź dokładnie, czy „Czas graniczny zakupu” jest poprawnie ustawiony na Twoją dzienną godzinę graniczną wysyłki.
-   **Sprawdź codzienne wiadomości:** Upewnij się, że „Wiadomość” dla bieżącego dnia tygodnia jest poprawnie skonfigurowana i ma sens.
-   **Strefa czasowa serwera:** Upewnij się, że strefa czasowa serwera Twojego sklepu PrestaShop jest poprawnie skonfigurowana. Jeśli czas serwera jest nieprawidłowy, odliczanie będzie niedokładne. Możesz to sprawdzić w **Zaawansowane > Informacje o konfiguracji** lub u swojego dostawcy hostingu.

**P3: Licznik wyświetla się dla produktów niedostępnych w magazynie.**
O3:

-   **Ustawienie „Pokaż tylko dla produktów dostępnych w magazynie”:** Upewnij się, że przełącznik „Pokaż tylko dla produktów dostępnych w magazynie” jest ustawiony na **Włączony** w konfiguracji modułu. Jeśli jest wyłączony, licznik pojawi się niezależnie od statusu magazynowego.

**P4: Chcę zmienić kolory lub czcionki licznika poza predefiniowanymi projektami.**
O4:

-   Moduł oferuje kilka predefiniowanych projektów. W celu głębszej personalizacji (np. konkretne czcionki, dokładne kody kolorów niedostępne w projektach) będziesz potrzebować webmastera lub programisty. Mogą oni nadpisać style CSS modułu, dodając niestandardowy CSS do arkusza stylów Twojego szablonu. Szczegóły dotyczące plików CSS znajdują się w sekcji 7.5.

**P5: Licznik nie tłumaczy się na inne języki.**
O5:

-   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz „Licznik czasu dostawy wysyłki” z rozwijanej listy modułów.
-   Następnie możesz przetłumaczyć wszystkie codzienne wiadomości i inne ciągi modułu na wybrane języki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Licznik czasu dostawy wysyłki` (`deliverycountdown`) to standardowy moduł PrestaShop, który stosuje wzorzec zbliżony do MVC w ramach swojego zakresu. Głównie rozszerza `Module` i wykorzystuje system hooków PrestaShop do wstrzykiwania swojej zawartości i funkcjonalności do front office. Konfiguracja jest obsługiwana za pomocą metody `getContent()`, przechowując ustawienia w `ps_configuration`. Wyświetlanie w front office opiera się na szablonach Smarty i dedykowanym pliku JavaScript dla logiki odliczania.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu. Renderowanie w front office odbywa się bezpośrednio za pomocą hooków i powiązanych szablonów.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Wszystkie dane są przechowywane bezpośrednio w `ps_configuration` za pomocą kluczy konfiguracyjnych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`deliverycountdown/views/js/deliverycountdown.js`**
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Jest to główny plik JavaScript odpowiedzialny za logikę odliczania.
    *   **Szczegóły:**
        *   Prawdopodobnie inicjalizuje licznik czasu na elementach identyfikowanych przez określone klasy CSS lub ID.
        *   Oblicza pozostały czas do „Czasu granicznego zakupu” dla bieżącego dnia lub następnego dostępnego dnia wysyłki.
        *   Dynamicznie aktualizuje wyświetlany czas (godziny, minuty, sekundy) w szablonie front-office.
        *   Obsługuje zmianę wiadomości po osiągnięciu czasu granicznego (np. zmiana z „Zamów w ciągu X czasu” na „Zamówienia złożone teraz zostaną wysłane jutro”).
        *   Może używać `setInterval` lub `setTimeout` do aktualizacji w czasie rzeczywistym.
        *   Prawdopodobnie odczytuje wartości konfiguracyjne (takie jak czas graniczny, codzienne wiadomości i włączone dni) przekazane z szablonu Smarty lub wbudowanego kodu JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera podstawowy plik CSS i kilka plików CSS specyficznych dla szablonu dla różnych projektów wizualnych.

-   **`deliverycountdown/views/css/deliverycountdown.css`**

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Zawiera podstawowe style strukturalne i domyślne dla licznika czasu. Obejmuje to podstawowy układ, rozmiary czcionek i wspólne elementy współdzielone przez wszystkie projekty.
    *   **Kluczowe selektory:** Programiści mogą sprawdzić wyjście HTML licznika, aby zidentyfikować klasy takie jak `.deliverycountdown-container`, `.deliverycountdown-message`, `.deliverycountdown-timer` itp., aby nadpisać style w pliku `custom.css` lub `theme.css` swojego szablonu.
-   **`deliverycountdown/views/css/deliverycountdown-{color}-{size}.css`** (np. `deliverycountdown-black-200x100.css`, `deliverycountdown-blue-400x48.css`)

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Te pliki dostarczają specyficzne schematy kolorów, obrazy tła (jeśli istnieją) i dostosowania rozmiaru dla różnych opcji projektowych wybranych w back office. Zazwyczaj nadpisują lub rozszerzają style zdefiniowane w `deliverycountdown.css`.
    *   **Kluczowe selektory:** Te pliki będą celować w te same podstawowe selektory, ale zastosują specyficzne `background-color`, `color`, `width`, `height`, `border` itp., aby osiągnąć wybrany styl wizualny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    *   **`deliverycountdown/views/hook/displayFooterProduct.tpl`**
        *   **Hook:** `displayFooterProduct` (i potencjalnie inne, takie jak `displayProductAdditionalInfo`, `displayReassurance`, `displayNav1`, `displayDeliveryTimer`, jeśli skonfigurowane).
        *   **Cel:** Jest to główny szablon odpowiedzialny za renderowanie struktury HTML licznika czasu i powiązanej z nim wiadomości w front office.
        *   **Zawartość:**
            *   Będzie zawierać główne elementy `div` dla kontenera licznika.
            *   Będzie wyświetlać dynamiczną wiadomość (np. „Zamów w ciągu…”) i cyfry odliczania.
            *   Prawdopodobnie przekazuje niezbędne zmienne konfiguracyjne (takie jak czas graniczny, codzienne wiadomości, włączone dni, bieżący status magazynowy produktu, reguły wykluczeń/włączeń) do skryptu `deliverycountdown.js`, albo poprzez atrybuty danych, albo wbudowane tagi `<script>`.
            *   Zawiera wybrany plik CSS projektu i skrypt `deliverycountdown.js`.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    *   **`deliverycountdown/views/admin/datepicker.tpl`**
        *   **Cel:** Prawdopodobnie szablon wielokrotnego użytku do renderowania pola wprowadzania daty w konfiguracji back-office modułu. (Chociaż nie jest wyraźnie używany do dat w bieżącej konfiguracji, może być składnikiem biblioteki).
    *   **`deliverycountdown/views/admin/selectedExcludedProducts.tpl`**
        *   **Cel:** Renderuje listę produktów, które zostały wybrane do wykluczenia lub włączenia w konfiguracji modułu. Jest to część interfejsu wyboru produktów/kategorii/producentów.
    *   **`deliverycountdown/views/admin/selectedProducts.tpl`**
        *   **Cel:** Podobnie jak `selectedExcludedProducts.tpl`, ale potencjalnie dla innego kontekstu wyboru (np. gdyby istniały oddzielne listy włączeń i wykluczeń).
    *   **`deliverycountdown/views/admin/timepicker.tpl`**
        *   **Cel:** Renderuje pole wprowadzania czasu używane do ustawiania „Czasu granicznego zakupu” w konfiguracji back-office.
-   **Szablony biblioteczne (`deliverycountdown/lib/searchTool/views/scripts.tpl`)**:

    *   **`deliverycountdown/lib/searchTool/views/scripts.tpl`**
        *   **Cel:** Prawdopodobnie zawiera logikę JavaScript lub Smarty związaną z narzędziem wyszukiwania i wyboru produktów/kategorii/producentów używanym w konfiguracji modułu. Ten skrypt ułatwia wyszukiwanie oparte na AJAX i wyświetlanie wybranych elementów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Ten moduł nie tworzy niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`.
    *   **Kluczowe rekordy konfiguracyjne (przykłady):**
        *   `DC_LAYOUT`: Przechowuje wybrany układ projektu (np. „black-200x100”).
        *   `DC_SUNDAY_MSG`, `DC_MONDAY_MSG` itd.: Przechowuje niestandardową wiadomość dla każdego dnia.
        *   `DC_TIME`: Przechowuje „Czas graniczny zakupu” (np. „16:00”).
        *   `DC_EXCL`: Wartość logiczna dla reguły wykluczenia (0 lub 1).
        *   `DC_INSTOCK`: Wartość logiczna dla „Pokaż tylko dla produktów dostępnych w magazynie”.
        *   `dc_exclusions_products`, `dc_exclusions_cat`, `DC_EXCL_MANUF`: Listy ID w formacie JSON lub oddzielone przecinkami dla wykluczonych/włączonych encji.
        *   `DC_SUNDAY`, `DC_MONDAY` itd.: Wartości logiczne dla włączania/wyłączania licznika w określone dni.
        *   `DC_HOOK_displayFooterProduct`, `DC_HOOK_displayReassurance` itd.: Wartości logiczne wskazujące, które hooki są włączone do wyświetlania.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | W sekcji `<head>` każdej strony. | Służy do globalnego ładowania zasobów CSS i JS modułu lub do ogólnego wyświetlania licznika na całej witrynie. |
| `displayNav1` | Front-office | Zazwyczaj w górnym pasku nawigacyjnym. | Wyświetla licznik w głównym obszarze nawigacji. |
| `displayNav2` | Front-office | Często w drugim pasku nawigacyjnym lub linkach narzędziowych. | Wyświetla licznik w drugim obszarze nawigacji. |
| `displayTop` | Front-office | W głównej sekcji nagłówka, poniżej `displayNav`. | Wyświetla licznik w głównym nagłówku. |
| `displayProductAdditionalInfo` | Front-office | Na stronie produktu, często w pobliżu przycisku „Dodaj do koszyka”. | Strategiczne umiejscowienie dla pilności specyficznej dla produktu. |
| `displayFooterProduct` | Front-office | Na stronie produktu, zazwyczaj poniżej opisu produktu lub szczegółów. | Inne umiejscowienie specyficzne dla produktu dla pilności. |
| `displayReassurance` | Front-office | W bloku uspokajającym (jeśli szablon to obsługuje), często poniżej informacji o produkcie. | Integruje licznik z innymi elementami budującymi zaufanie. |
| `displayDeliveryTimer` | Front-office | Niestandardowy hook. | Pozwala programistom szablonów umieścić licznik dokładnie w dowolnym miejscu w szablonie. |
| `actionAdminControllerSetMedia` | Back-office | Gdy kontroler administracyjny ładuje swoje zasoby multimedialne. | Służy do ładowania CSS/JS specyficznych dla modułu na stronę konfiguracji back-office (np. dla narzędzia wyszukiwania, selektora czasu). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Licznik czasu dostawy wysyłki”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
