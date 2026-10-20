---
title: "Wyświetlanie ceny w różnych walutach jednocześnie - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyświetlanie ceny w różnych walutach jednocześnie” od MyPresta.eu."
sidebar:
  label: "Wyświetlanie ceny w różnych walutach jednocześnie - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Show price in different currencies at the same time na MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-price-in-different-currencies-at-the-same-time.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/show-price-in-different-currencies-at-the-same-time/)
>
> ---


# Wyświetlanie ceny w różnych walutach jednocześnie

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Wyświetlanie ceny w różnych walutach jednocześnie”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok nazwy modułu.

Strona konfiguracji przedstawi szereg opcji do kontrolowania, jak i gdzie wyświetlane są ceny w wielu walutach.

#### Ustawienia ogólne

-   **Włącz wyświetlanie cen w wielu walutach:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł zacznie wyświetlać ceny w wielu walutach zgodnie z innymi ustawieniami.
        -   *Gdy wyłączone:* Moduł przestanie działać i zostanie wyświetlona tylko cena w walucie podstawowej.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy lub wykonujesz konserwację, możesz go tymczasowo wyłączyć. Do normalnego działania powinien być zawsze włączony.
-   **Wybierz waluty do wyświetlenia:**

    -   **Co robi to ustawienie:** Pozwala wybrać, które dodatkowe waluty, poza podstawową, chcesz wyświetlać ceny. Zazwyczaj zobaczysz listę wszystkich aktywnych walut w Twoim sklepie PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane:* Ceny zostaną wyświetlone w wybranych walutach.
        -   *Gdy niewybrane:* Ceny nie zostaną wyświetlone w tej konkretnej walucie.
    -   **Zalecana wartość:** Wybierz wszystkie waluty istotne dla Twoich docelowych rynków międzynarodowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz klientom w strefie euro, USA i Wielkiej Brytanii, wybierzesz EUR, USD i GBP.
-   **Wyświetlaj na stronach z listą produktów (Kategorie, Wyniki wyszukiwania itp.):**

    -   **Co robi to ustawienie:** Kontroluje, czy ceny w wielu walutach pojawiają się na stronach, które wyświetlają wiele produktów (np. strony kategorii, wyniki wyszukiwania, strony producentów).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Ceny w wielu walutach będą widoczne poniżej głównej ceny na kartach produktów.
        -   *Gdy wyłączone:* Ceny w wielu walutach pojawią się tylko na indywidualnej stronie szczegółów produktu.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia natychmiastową przejrzystość cen, gdy klienci przeglądają, pomagając im szybko porównać produkty w preferowanej walucie.
-   **Wyświetlaj na stronie szczegółów produktu:**

    -   **Co robi to ustawienie:** Kontroluje, czy ceny w wielu walutach pojawiają się na indywidualnej stronie produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Ceny w wielu walutach będą widoczne w pobliżu głównej ceny na stronie produktu.
        -   *Gdy wyłączone:* Ceny w wielu walutach nie zostaną wyświetlone na stronie produktu.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jest to kluczowe dla klientów podejmujących ostateczną decyzję, zwłaszcza przy rozważaniu kombinacji produktów lub rabatów ilościowych, ponieważ moduł zapewnia, że te dynamiczne ceny są również przeliczane.
-   **Format wyświetlania ceny:**

    -   **Co robi to ustawienie:** Definiuje, jak formatowane są dodatkowe ceny walut (np. z symbolem waluty lub bez, liczba miejsc dziesiętnych). Zazwyczaj wykorzystuje to natywne formatowanie walut PrestaShop.
    -   **Efekt zmiany tego ustawienia:** Zmienia wizualną prezentację przeliczonych cen.
    -   **Zalecana wartość:** Użyj formatu, który jest jasny i zgodny z międzynarodowymi standardami dla każdej waluty (np. „100.00 USD” lub „100,00 €”).
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz wybrać wyświetlanie „USD 100.00” zamiast „$100.00”, aby uniknąć pomyłek z innymi walutami denominowanymi w dolarach.
-   **Pozycja dodatkowych cen:**

    -   **Co robi to ustawienie:** Określa, gdzie dodatkowe ceny walut są umieszczane w stosunku do głównej ceny produktu. Opcje mogą obejmować „Poniżej głównej ceny”, „Obok głównej ceny” lub „W osobnym bloku”.
    -   **Efekt zmiany tego ustawienia:** Zmienia wizualny układ cen na stronach produktów.
    -   **Zalecana wartość:** „Poniżej głównej ceny” jest często najjaśniejsze i najmniej inwazyjne.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli układ strony produktu jest bardzo kompaktowy, umieszczenie cen poniżej może być lepsze niż obok, aby uniknąć zagęszczenia.
-   **Aktualizuj ceny z kombinacjami/rabatami ilościowymi:**

    -   **Co robi to ustawienie:** Zapewnia, że gdy klient wybierze inną kombinację produktu (np. większy rozmiar z inną ceną) lub zmieni ilość (wywołując rabat ilościowy), wyświetlane ceny w wielu walutach są dynamicznie aktualizowane, aby odzwierciedlić nową sumę.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł użyje JavaScript do ponownego obliczenia i wyświetlenia prawidłowych przeliczonych cen w czasie rzeczywistym.
        -   *Gdy wyłączone:* Dodatkowe ceny mogą się nie aktualizować, co prowadzi do nieprawidłowych informacji dla klienta.
    -   **Zalecana wartość:** TAK (Kluczowe dla dokładności i zaufania klientów).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient wybiera koszulkę „Dużą” (która kosztuje więcej) lub dodaje 10 sztuk (wywołując rabat hurtowy). To ustawienie zapewnia, że widzi prawidłową przeliczoną cenę za dużą koszulkę lub obniżoną cenę hurtową w wybranych walutach.

#### Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz wyświetlanie cen w wielu walutach | TAK | Aktywuje/dezaktywuje podstawową funkcjonalność modułu. |
| Konfiguracja modułu | Wybierz waluty do wyświetlenia | Wybierz odpowiednie waluty | Określa, które dodatkowe waluty są wyświetlane. |
| Konfiguracja modułu | Wyświetlaj na stronach z listą produktów | TAK | Pokazuje ceny w wielu walutach na stronach kategorii, wyszukiwania itp. |
| Konfiguracja modułu | Wyświetlaj na stronie szczegółów produktu | TAK | Pokazuje ceny w wielu walutach na indywidualnych stronach produktów. |
| Konfiguracja modułu | Format wyświetlania ceny | Różne (użyj domyślnych PrestaShop) | Kontroluje wizualne formatowanie przeliczonych cen. |
| Konfiguracja modułu | Pozycja dodatkowych cen | Poniżej głównej ceny | Ustawia układ dodatkowych cen w stosunku do głównej ceny. |
| Konfiguracja modułu | Aktualizuj ceny z kombinacjami/rabatami ilościowymi | TAK | Zapewnia dynamiczne aktualizacje cen dla kombinacji i rabatów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ceny w wielu walutach nie wyświetlają się w moim sklepie.**
**O1:**

-   **Sprawdź status modułu:** Najpierw upewnij się, że opcja „Włącz wyświetlanie cen w wielu walutach” jest ustawiona na TAK w konfiguracji modułu.
-   **Wybrane waluty:** Sprawdź, czy wybrałeś konkretne waluty, które chcesz wyświetlać w ustawieniach modułu.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki. Czasami stara zawartość pamięci podręcznej uniemożliwia wyświetlanie nowych modułów.
-   **Kompatybilność motywu:** Jeśli używasz mocno dostosowanego motywu, może wystąpić konflikt. Skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P2: Ceny w innych walutach są nieprawidłowe lub nie aktualizują się.**
**O2:**

-   **Kursy wymiany:** Upewnij się, że kursy wymiany walut w PrestaShop są aktualne. Przejdź do **Lokalizacja > Waluty** w Panelu administracyjnym i sprawdź kursy wymiany dla każdej waluty. Zazwyczaj możesz je aktualizować automatycznie lub ręcznie.
-   **Ustawienie dynamicznej aktualizacji:** Upewnij się, że opcja „Aktualizuj ceny z kombinacjami/rabatami ilościowymi” jest włączona w konfiguracji modułu, jeśli oczekujesz, że ceny będą się zmieniać wraz z opcjami produktu.
-   **Pamięć podręczna:** Wyczyść wszystkie pamięci podręczne (PrestaShop i przeglądarki) po zaktualizowaniu kursów wymiany.

**P3: Ceny w wielu walutach wyglądają dziwnie lub nie są poprawnie ostylowane w moim motywie.**
**O3:**

-   **Konfiguracja modułu:** Sprawdź ustawienia „Format wyświetlania ceny” i „Pozycja dodatkowych cen” w module.
-   **CSS motywu:** CSS Twojego niestandardowego motywu może nadpisywać domyślne style modułu. Zazwyczaj wymaga to od webmastera lub programisty sprawdzenia CSS. Często możesz dodać niestandardowy CSS do swojego motywu, aby dostosować wygląd.
-   **Skontaktuj się z pomocą techniczną:** Jeśli nie możesz rozwiązać problemów ze stylizacją, dostarcz zrzuty ekranu i adres URL swojego sklepu do pomocy technicznej MyPresta.eu.

**P4: Czy ten moduł spowolni mój sklep?**
**O4:** Moduł został zaprojektowany tak, aby był lekki. Głównie pobiera istniejące kursy walut i wykonuje proste obliczenia. Dynamiczne aktualizacje dla kombinacji wykorzystują JavaScript, który działa po stronie klienta. W większości przypadków wpływ na wydajność powinien być znikomy. Upewnij się, że Twój serwer spełnia minimalne wymagania PrestaShop dla optymalnej wydajności.

**P5: Jak przetłumaczyć tekst modułu (np. „Cena w USD”)?**
**O5:** Możesz przetłumaczyć dowolne ciągi tekstowe dodane przez moduł za pośrednictwem interfejsu tłumaczeń PrestaShop:

-   Przejdź do **Lokalizacja > Tłumaczenia**.
-   Wybierz „Tłumaczenia zainstalowanych modułów”.
-   Wybierz swój motyw, swój język, a następnie wybierz moduł „Wyświetlanie ceny w różnych walutach jednocześnie”.
-   Następnie możesz edytować tłumaczenia dla wszelkich fraz wprowadzonych przez moduł.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd architektury technicznej modułu „Wyświetlanie ceny w różnych walutach jednocześnie”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `multiprice` (nazwa wewnętrzna `ajax_multiprice`) to standardowy moduł PrestaShop, skupiający się głównie na wyświetlaniu w front-office. Wykorzystuje system hooków PrestaShop do wstrzykiwania informacji o cenach w wielu walutach do list produktów i stron szczegółów produktu. Główna logika znajduje się w głównym pliku modułu, obsługując konfigurację i rejestrację hooków. JavaScript po stronie klienta jest używany do dynamicznych aktualizacji cen, gdy zmieniają się kombinacje produktów lub ilości, zapewniając dokładność w czasie rzeczywistym bez pełnego przeładowywania strony. Nie wprowadza niestandardowych tabel baz danych ani złożonych ObjectModels, opierając się zamiast tego na istniejących mechanizmach walutowych i cenowych produktów PrestaShop.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, a interakcje z front-office są zarządzane za pomocą hooków i JavaScript po stronie klienta.

### 4.3 Główne klasy i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Jego logika jest hermetyzowana w głównym pliku modułu `ajax_multiprice.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`multiprice/lib/searchTool/views/js/autocomplete.js`**

    -   **Zakres:** Potencjalnie Front-office (jeśli używany do funkcji wyszukiwania w module, choć nie bezpośrednio związany z podstawowym wyświetlaniem wielu cen).
    -   **Odpowiedzialność:** Ten plik wydaje się być częścią ogólnej biblioteki narzędzi do wyszukiwania z autouzupełnianiem dołączonej do modułu. Zazwyczaj obsługiwałby żądania AJAX dotyczące sugestii wyszukiwania, wiązałby się z polami wejściowymi i wyświetlał wyniki. Jego bezpośrednie znaczenie dla wyświetlania cen w wielu walutach jest prawdopodobnie minimalne, chyba że moduł integruje funkcję wyszukiwania, która również wyświetla ceny.
    -   **Szczegóły:** Wiąże się z polami wejściowymi, nasłuchuje zdarzeń `keyup`, wykonuje wywołania AJAX do punktu końcowego backendu (niezdefiniowanego w kontrolerach tego modułu, prawdopodobnie ogólnego kontrolera wyszukiwania PrestaShop lub kontrolera dołączonego narzędzia wyszukiwania) i manipuluje DOM, aby wyświetlić listę rozwijaną sugestii.
-   **`multiprice/views/js/multiprice.js`**

    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Jest to główny plik JavaScript do wyświetlania cen w wielu walutach. Jest odpowiedzialny za dynamiczne aktualizowanie wyświetlanych cen, gdy atrybuty produktu (kombinacje) lub ilości zmieniają się na stronie produktu.
    -   **Szczegóły:**
        -   Nasłuchuje zdarzeń `change` na selektorach kombinacji produktów (np. elementy `select` dla atrybutów, przyciski radiowe).
        -   Nasłuchuje zdarzeń `change` lub `blur` na polu wprowadzania ilości.
        -   Wpina się w natywne zdarzenie PrestaShop `prestashop.on('updatedProduct', ...)` (dla PS 1.7+), które jest wyzwalane, gdy dane produktu (w tym cena) są aktualizowane po wyborze kombinacji.
        -   Pobiera nową cenę bazową z zaktualizowanych danych produktu.
        -   Wykonuje obliczenia po stronie klienta, aby przeliczyć nową cenę bazową na skonfigurowane dodatkowe waluty, używając kursów wymiany potencjalnie przekazanych z backendu lub przechowywanych w globalnej zmiennej JS.
        -   Aktualizuje elementy DOM (`<span>`, `<div>`), w których wyświetlane są dodatkowe ceny walut.
        -   Zapewnia prawidłowe formatowanie przeliczonych cen (symbol waluty, miejsca dziesiętne).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`multiprice/lib/searchTool/views/css/autocomplete.css`**

    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Stylizuje rozwijaną listę wyników wyszukiwania z autouzupełnianiem, w tym sugestie, podświetlanie i ogólny układ.
    -   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w klasy takie jak `.autocomplete-results`, `.autocomplete-item`, `.highlighted`. Programiści mogą je nadpisać w pliku `custom.css` lub `theme.css` swojego motywu.
-   **`multiprice/views/css/multiprice.css`**

    -   **Zakres:** Stylizacja klienta Front-office.
    -   **Odpowiedzialność:** Zapewnia domyślne style dla bloków wyświetlania cen w wielu walutach. Obejmuje to rozmiary czcionek, kolory, marginesy i potencjalnie układ (np. układanie cen pionowo).
    -   **Kluczowe selektory klas CSS:** Będą celować w konkretne klasy dodane przez szablony modułu (np. `.multiprice-container`, `.multiprice-currency-item`, `.multiprice-price`). Programiści mogą nadpisać te selektory w CSS swojego motywu, aby dopasować je do projektu swojego sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`multiprice/lib/searchTool/views/scripts.tpl`**

    -   **Zakres:** Front-office.
    -   **Cel:** Ten szablon prawdopodobnie zawiera JavaScript i CSS dla funkcjonalności `autocomplete.js`. Zostałby podłączony do `displayHeader` lub `displayFooter`, aby zapewnić załadowanie niezbędnych zasobów.
-   **`multiprice/views/templates/multiprice-custom.tpl`**

    -   **Zakres:** Front-office (szablon hooka).
    -   **Cel:** Ten szablon jest prawdopodobnie rezerwowym lub alternatywnym szablonem do wyświetlania cen w wielu walutach, być może dla konkretnych hooków lub niestandardowych miejsc. Zawierałby strukturę HTML do renderowania ceny podstawowej, a następnie iterowałby przez dodatkowe waluty, aby wyświetlić ich przeliczone ceny.
-   **`multiprice/views/templates/multiprice.tpl`**

    -   **Zakres:** Front-office (szablon hooka).
    -   **Cel:** Jest to główny szablon odpowiedzialny za renderowanie bloku cen w wielu walutach. Jest wstrzykiwany do elementów listy produktów i strony szczegółów produktu za pośrednictwem hooków PrestaShop. Otrzymuje tablicę walut i ich przeliczonych cen i formatuje je zgodnie z konfiguracją modułu.
    -   **Zmienne:** Oczekuje zmiennych takich jak `$product_price`, `$additional_currencies` (tablica obiektów walut z przeliczonymi cenami), `$currency_format` itp.
-   **`multiprice/views/templates/selectedProducts.tpl`**

    -   **Zakres:** Front-office.
    -   **Cel:** Nazwa tego szablonu sugeruje, że może być używany w kontekście, w którym wyświetlana jest lista wybranych produktów, potencjalnie w podsumowaniu koszyka, na stronie porównania lub w niestandardowym widżecie wyboru produktu. Iterowałby po kolekcji produktów i wyświetlał ich ceny, potencjalnie z funkcją wielu walut.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. status włączenia, wybrane waluty, opcje wyświetlania) w tabeli `ps_configuration`, używając kluczy z prefiksem `MULTIPRICE_` lub podobnym.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Aby dołączyć `multiprice.js` i `multiprice.css` (i potencjalnie zasoby `autocomplete`) na stronach front-office. |
| `displayProductPriceBlock` (typ `after_price`) | Po głównym bloku ceny na stronach produktów. | Aby wstrzyknąć zawartość `multiprice.tpl` lub `multiprice-custom.tpl` wyświetlającą dodatkowe ceny walut na stronie szczegółów produktu. |
| `displayProductListReviews` (lub podobny dla listy produktów) | W elementach listy produktów (np. stronach kategorii). | Aby wstrzyknąć zawartość `multiprice.tpl` lub `multiprice-custom.tpl` wyświetlającą dodatkowe ceny walut poniżej głównej ceny na stronach z listą produktów. Dokładny hook może się różnić w zależności od wersji PrestaShop i struktury motywu (np. `displayProductPriceBlock` może być również używany tutaj, lub niestandardowy hook dostarczony przez motyw). |
| `actionProductUpdate` (lub podobny) | Po zaktualizowaniu produktu w panelu administracyjnym. | (Mniej prawdopodobne dla tego modułu) Może być używany do czyszczenia pamięci podręcznej związanej z cenami produktów, choć nie jest to ściśle konieczne dla jego podstawowej funkcji. |
| `actionFrontControllerSetMedia` | Przed renderowaniem zawartości przez kontroler front-office. | Aby zarejestrować pliki JavaScript i CSS dla front-office, zapewniając ich prawidłowe załadowanie. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich zapytań dotyczących modułu „Wyświetlanie ceny w różnych walutach jednocześnie” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w instalacji, konfiguracji i wszelkich problemach, które mogą się pojawić.
