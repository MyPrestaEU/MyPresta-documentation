---
title: "Export Products Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Export Products Pro od MyPresta.eu."
sidebar:
  label: "Export Products Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Export Products Pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-products-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/export-products-pro/)
>
> ---


# Export Products Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do ogólnego działania PrestaShop, ale ten moduł nie ma żadnych specyficznych egzotycznych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Export Products Pro)

Jest to główny ekran konfiguracji, na którym definiujesz ogólne zachowanie i ustawienia dla eksportu produktów.

#### Ustawienia ogólne

-   **Format eksportu**:
    -   **Co robi to ustawienie:** Określa format pliku dla eksportowanych danych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na CSV:* Moduł wygeneruje plik wartości rozdzielonych przecinkami (Comma Separated Values), który jest szeroko kompatybilny z oprogramowaniem arkuszy kalkulacyjnych, takim jak Excel, Arkusze Google lub LibreOffice Calc. Jest to najczęstszy i najbardziej wszechstronny format.
        -   *Gdy ustawione na XML:* Moduł wygeneruje plik Extensible Markup Language, często używany do bardziej ustrukturyzowanej wymiany danych między systemami lub do specyficznych plików produktowych (np. Google Shopping).
    -   **Zalecana wartość:** CSV do ogólnego użytku i analizy w arkuszach kalkulacyjnych. XML, jeśli masz konkretny system, który tego wymaga.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz otworzyć dane w Excelu, aby analizować ceny, wybierz CSV. Jeśli tworzysz plik dla aplikacji zewnętrznej, która wymaga XML, wybierz XML.
-   **Separator**:
    -   **Co robi to ustawienie:** Ten znak oddziela różne kolumny (pola) w pliku CSV.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na przecinek (,):* Każdy element danych w wierszu będzie oddzielony przecinkiem. Jest to standard dla wielu systemów.
        -   *Gdy ustawione na średnik (;):* Każdy element danych będzie oddzielony średnikiem. Jest to powszechne w niektórych regionach Europy lub gdy przecinki mogą pojawiać się w danych produktu (np. w opisach), powodując problemy z parsowaniem.
    -   **Zalecana wartość:** Przecinek (`,`) w większości przypadków. Jeśli Twoje oprogramowanie arkuszy kalkulacyjnych ma problemy z poprawnym otwarciem pliku CSV, spróbuj średnika (`;`).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli otwierasz plik CSV w Excelu i wszystkie dane pojawiają się w jednej kolumnie, spróbuj zmienić separator na średnik i ponownie wyeksportować.
-   **Eksportuj tylko aktywne produkty**:
    -   **Co robi to ustawienie:** Kontroluje, czy do eksportu włączane są tylko produkty aktualnie widoczne i dostępne do zakupu w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Eksportowane będą tylko produkty, których „Status” jest ustawiony na „Online” lub „Aktywny” w panelu administracyjnym PrestaShop. Jest to przydatne dla bieżących zapasów.
        -   *Gdy wyłączone (Nie):* Eksportowane będą wszystkie produkty, w tym te oznaczone jako nieaktywne lub wyłączone. Jest to przydatne do pełnej kopii zapasowej katalogu lub audytu.
    -   **Zalecana wartość:** Tak, dla większości eksportów operacyjnych.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli generujesz plik produktowy dla Google Shopping, chcesz tylko aktywne produkty, więc włącz to. Jeśli robisz pełną kopię zapasową danych, wyłącz to.
-   **Eksportuj tylko produkty dostępne w magazynie**:
    -   **Co robi to ustawienie:** Filtruje eksport, aby uwzględnić tylko produkty, które aktualnie mają ilość większą niż zero.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Eksportowane będą tylko produkty, które są aktualnie dostępne w magazynie.
        -   *Gdy wyłączone (Nie):* Produkty będą eksportowane niezależnie od ich poziomu zapasów (dostępne w magazynie lub niedostępne).
    -   **Zalecana wartość:** Tak, jeśli tworzysz plik dla sprzedaży lub bieżącej dostępności.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli wysyłasz listę dostępnych produktów do dropshippera, włącz to. Jeśli potrzebujesz zobaczyć wszystkie produkty, w tym te, które musisz ponownie zamówić, wyłącz to.
-   **Eksportuj obrazy produktów**:
    -   **Co robi to ustawienie:** Określa, czy adresy URL Twoich obrazów produktów są uwzględniane w eksporcie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Plik CSV/XML będzie zawierał kolumny z adresami URL do Twoich obrazów produktów.
        -   *Gdy wyłączone (Nie):* Adresy URL obrazów zostaną pominięte, co skutkuje mniejszym rozmiarem pliku, jeśli obrazy nie są potrzebne.
    -   **Zalecana wartość:** Tak, jeśli potrzebujesz obrazów dla marketplace’ów lub zewnętrznych katalogów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli aktualizujesz katalog produktów na innej platformie, która wymaga adresów URL obrazów, włącz to.
-   **Eksportuj krótki opis produktu**:
    -   **Co robi to ustawienie:** Uwzględnia krótki opis (podsumowanie) Twoich produktów w eksporcie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Krótki opis dla każdego produktu zostanie uwzględniony jako kolumna.
        -   *Gdy wyłączone (Nie):* Krótki opis zostanie pominięty.
    -   **Zalecana wartość:** Tak, ponieważ krótkie opisy są często używane do list produktów i wyników wyszukiwania.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli tworzysz plik produktowy dla strony porównującej ceny, która wyświetla krótkie opisy, włącz to.
-   **Eksportuj opis produktu**:
    -   **Co robi to ustawienie:** Uwzględnia pełny, szczegółowy opis Twoich produktów w eksporcie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Pełny opis produktu zostanie uwzględniony jako kolumna.
        -   *Gdy wyłączone (Nie):* Pełny opis zostanie pominięty.
    -   **Zalecana wartość:** Tak, dla pełnego eksportu danych.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli migrujesz swój sklep na nową platformę i potrzebujesz całej zawartości produktu, włącz to.
-   **Zapamiętaj ustawienia**:
    -   **Co robi to ustawienie:** Jeśli włączone, moduł zapisze ostatnio używane ustawienia eksportu (filtry, wybrane pola) dla Twojego następnego eksportu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Moduł wstępnie wypełni formularz eksportu Twoimi poprzednimi wyborami, oszczędzając czas na powtarzające się eksporty.
        -   *Gdy wyłączone (Nie):* Formularz eksportu zawsze będzie resetowany do ustawień domyślnych za każdym razem, gdy go odwiedzisz.
    -   **Zalecana wartość:** Tak, jeśli często wykonujesz podobne eksporty.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli regularnie eksportujesz listę aktywnych, dostępnych produktów z określonymi polami, włączenie tego przyspieszy Twój przepływ pracy.

#### Opcje filtrowania

-   **Eksportuj produkty z kategorii**:
    -   **Co robi to ustawienie:** Pozwala wybrać konkretne kategorie produktów do uwzględnienia w eksporcie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne kategorie:* Eksportowane będą tylko produkty należące do tych kategorii.
        -   *Gdy nie wybrano żadnych kategorii (lub wybrano wszystkie):* Wszystkie produkty, niezależnie od kategorii, zostaną uwzględnione w eksporcie (z zastrzeżeniem innych filtrów).
    -   **Zalecana wartość:** Wybierz konkretne kategorie, jeśli potrzebujesz ukierunkowanego eksportu; w przeciwnym razie pozostaw niewybrane dla pełnego katalogu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz eksportować tylko produkty z kategorii „Elektronika”, wybierz ją tutaj.
-   **Eksportuj tylko kategorie nadrzędne**:
    -   **Co robi to ustawienie:** Jeśli wybrano kategorie, ta opcja dodatkowo precyzuje, czy produkty z podkategorii są również uwzględniane.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Eksportowane będą tylko produkty bezpośrednio przypisane do wybranych kategorii nadrzędnych. Produkty w ich podkategoriach zostaną wykluczone.
        -   *Gdy wyłączone (Nie):* Eksportowane będą produkty z wybranych kategorii nadrzędnych ORAZ wszystkich ich podkategorii.
    -   **Zalecana wartość:** Nie, w większości przypadków, ponieważ zazwyczaj chcesz również produkty z podkategorii. Włącz tylko, jeśli masz konkretny powód, aby wykluczyć produkty z podkategorii.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz „Odzież” jako kategorię nadrzędną i „T-shirty” jako podkategorię, włączenie tego spowodowałoby eksport produktów bezpośrednio w „Odzieży”, ale nie tych w „T-shirtach”.
-   **Eksportuj produkty od producenta**:
    -   **Co robi to ustawienie:** Pozwala filtrować produkty według przypisanego im producenta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrani są konkretni producenci:* Eksportowane będą tylko produkty od tych producentów.
        -   *Gdy nie wybrano żadnych producentów (lub wybrano wszystkich):* Produkty od wszystkich producentów zostaną uwzględnione.
    -   **Zalecana wartość:** Wybierz konkretnych producentów dla ukierunkowanych eksportów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli musisz wysłać listę produktów do konkretnej marki do przeglądu, wybierz ich producenta tutaj.
-   **Eksportuj produkty od dostawcy**:
    -   **Co robi to ustawienie:** Pozwala filtrować produkty według przypisanego im dostawcy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrani są konkretni dostawcy:* Eksportowane będą tylko produkty od tych dostawców.
        -   *Gdy nie wybrano żadnych dostawców (lub wybrano wszystkich):* Produkty od wszystkich dostawców zostaną uwzględnione.
    -   **Zalecana wartość:** Wybierz konkretnych dostawców dla ukierunkowanych eksportów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli musisz dostarczyć listę produktów, które masz w magazynie od konkretnego dostawcy, wybierz go tutaj.

### 2.2 Dedykowany ekran administracyjny: Pulpit Export Products Pro (Panel administracyjny > Katalog > Export Products Pro)

Jest to główny interfejs do inicjowania i zarządzania eksportem produktów.

-   **Nazwa ekranu i lokalizacja w menu:** **Katalog > Export Products Pro**
-   **Dostępne akcje i ustawienia:**
    -   **Przycisk Eksportuj:** Jest to główny przycisk akcji. Kliknięcie go rozpocznie proces eksportu na podstawie ustawień skonfigurowanych na tej stronie.
    -   **Wybór pól:** Poniżej ustawień ogólnych znajdziesz kompleksową listę wszystkich dostępnych pól produktu i kombinacji. Możesz indywidualnie zaznaczyć lub odznaczyć, które pola chcesz uwzględnić w eksporcie.
        -   **Pola produktu:** Obejmuje standardowe szczegóły produktu, takie jak ID, nazwa, referencja, EAN13, UPC, cena, ilość, waga, opisy itp.
        -   **Pola kombinacji:** Jeśli Twoje produkty mają kombinacje (np. rozmiar, kolor), zobaczysz pola specyficzne dla kombinacji, takie jak „ID kombinacji”, „Atrybut (Nazwa:Typ:Pozycja)”, „Wartość (Wartość:Pozycja)”, „Wpływ na cenę”, „Wpływ na wagę”, „Domyślne (0 = Nie, 1 = Tak)”, „Data dostępności kombinacji”.
    -   **Efekt zmian:**
        -   **Zaznaczanie/odznaczanie pól:** Tylko zaznaczone pola pojawią się jako kolumny w wyeksportowanym pliku CSV/XML. Pozwala to na tworzenie wysoce spersonalizowanych eksportów, zawierających tylko potrzebne dane i pomijających niepotrzebne informacje.
    -   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
        1.  Przejdź do **Katalog > Export Products Pro**.
        2.  Przejrzyj „Ustawienia ogólne” i „Opcje filtrowania” na górze strony. Dostosuj je w zależności od tego, czy potrzebujesz aktywnych produktów, produktów dostępnych w magazynie, konkretnych kategorii, producentów lub dostawców.
        3.  Starannie wybierz „Pola produktu” i „Pola kombinacji”, które chcesz uwzględnić w eksporcie. Jeśli nie jesteś pewien, często bezpieczniej jest początkowo wybrać więcej pól, a następnie usunąć niechciane kolumny w oprogramowaniu arkuszy kalkulacyjnych.
        4.  Kliknij przycisk „Eksportuj”. Moduł wygeneruje i poprosi o pobranie pliku CSV lub XML.
        5.  Otwórz pobrany plik w preferowanym oprogramowaniu arkuszy kalkulacyjnych (np. Excel, Arkusze Google), aby zweryfikować dane i format.

### 2.3 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Format eksportu | CSV | Określa typ pliku wyjściowego (CSV lub XML). |
| | Separator | Przecinek (`,`) | Znak oddzielający pola w CSV. Zmień, jeśli wystąpią problemy z parsowaniem. |
| | Eksportuj tylko aktywne produkty | Tak | Uwzględnia tylko aktywne produkty. |
| | Eksportuj tylko produkty dostępne w magazynie | Tak | Uwzględnia tylko produkty z ilością > 0. |
| | Eksportuj obrazy produktów | Tak | Uwzględnia adresy URL obrazów w eksporcie. |
| | Eksportuj krótki opis produktu | Tak | Uwzględnia krótki opis produktu. |
| | Eksportuj opis produktu | Tak | Uwzględnia pełny opis produktu. |
| | Zapamiętaj ustawienia | Tak | Zapisuje ostatnie wybory eksportu dla wygody. |
| | Eksportuj produkty z kategorii | (Brak wybranych) | Filtruje eksport według wybranych kategorii. |
| | Eksportuj tylko kategorie nadrzędne | Nie | Jeśli wybrano kategorie, uwzględnia/wyklucza produkty z podkategorii. |
| | Eksportuj produkty od producenta | (Brak wybranych) | Filtruje eksport według wybranych producentów. |
| | Eksportuj produkty od dostawcy | (Brak wybranych) | Filtruje eksport według wybranych dostawców. |
| **Pulpit Export Products Pro** | **Wybór pól** | Zależy od potrzeb | Wybierz konkretne atrybuty produktu/kombinacji do uwzględnienia jako kolumny w pliku eksportu. |
| | Przycisk Eksportuj | N/A | Inicjuje eksport produktów na podstawie wszystkich skonfigurowanych ustawień. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój wyeksportowany plik CSV wygląda na zniekształcony lub wszystkie dane znajdują się w jednej kolumnie, gdy otwieram go w Excelu.**
**O1:** Jest to zazwyczaj problem z separatorem lub kodowaniem znaków.

-   **Rozwiązanie 1 (Separator):** Wróć do konfiguracji modułu, zmień ustawienie „Separator” z przecinka (`,`) na średnik (`;`) i ponownie wyeksportuj. Spróbuj otworzyć nowy plik.
-   **Rozwiązanie 2 (Kodowanie):** Podczas otwierania pliku CSV w Excelu użyj opcji „Dane > Z tekstu/CSV”. W kreatorze importu upewnij się, że wybierasz prawidłowe „Pochodzenie pliku” lub „Kodowanie” (zazwyczaj `UTF-8`) i określ prawidłowy separator.

**P2: Niektóre produkty brakuje w moim eksporcie, ale wiem, że istnieją w moim sklepie.**
**O2:** Sprawdź ustawienia filtrów w konfiguracji modułu:

-   **Rozwiązanie:** Upewnij się, że „Eksportuj tylko aktywne produkty” i „Eksportuj tylko produkty dostępne w magazynie” są ustawione prawidłowo dla Twoich potrzeb. Jeśli wybrałeś konkretne kategorie, producentów lub dostawców, dokładnie sprawdź, czy brakujące produkty mieszczą się w tych filtrach. Jeśli chcesz wszystko, upewnij się, że żadne filtry nie są wybrane.

**P3: Proces eksportu trwa bardzo długo lub przekracza limit czasu dla dużych katalogów.**
**O3:** Eksportowanie tysięcy produktów może być zasobochłonne.

-   **Rozwiązanie 1:** Spróbuj eksportować mniejsze partie, używając filtrów „Eksportuj produkty z kategorii”, „producenta” lub „dostawcy”.
-   **Rozwiązanie 2:** Jeśli masz dostęp do ustawień serwera, może być konieczne tymczasowe zwiększenie `memory_limit` i `max_execution_time` PHP w pliku `php.ini`. Skontaktuj się z dostawcą hostingu w celu uzyskania pomocy w tej sprawie.
-   **Rozwiązanie 3:** Odznacz niepotrzebne pola, aby zmniejszyć ilość przetwarzanych danych.

**P4: Jak przetłumaczyć nagłówki kolumn w wyeksportowanym pliku?**
**O4:** Nagłówki kolumn w wyeksportowanym pliku są zazwyczaj oparte na wewnętrznych nazwach pól lub domyślnych etykietach PrestaShop i nie są bezpośrednio przetłumaczalne za pośrednictwem interfejsu modułu.

-   **Rozwiązanie:** Najłatwiejszym sposobem jest otwarcie wyeksportowanego pliku CSV w programie arkuszy kalkulacyjnych (takim jak Excel lub Arkusze Google) i ręczne zmienienie nazw nagłówków kolumn na żądany język lub terminologię. Zapisz plik z nowymi nagłówkami.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu Export Products Pro, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `Export Products Pro` jest zgodny ze standardowym wzorcem MVC PrestaShop, koncentrując się głównie na funkcjonalności back-office. Wykorzystuje kontrolery administracyjne dla swojego interfejsu użytkownika i niestandardowe klasy do obsługi danych i generowania plików. Główna logika modułu znajduje się w jego głównym pliku `exportproducts.php` oraz w `AdminExportProductsController`, który zarządza procesem eksportu i konfiguracją. Wykorzystuje `ObjectModel` dla swoich niestandardowych danych, jeśli takie istnieją, chociaż w tym przypadku głównie współdziała z podstawowymi danymi produktów PrestaShop.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/feed.php`
    -   **Nazwa klasy i klasa nadrzędna:** `ExportProductsFeedModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za generowanie pliku danych produktu (np. XML lub CSV), który może być dostępny bezpośrednio za pośrednictwem adresu URL. Obsługiwałby logikę zapytań o produkty na podstawie określonych parametrów i ich wyprowadzania w wybranym formacie. Może to być używane do automatycznego generowania plików danych dla usług zewnętrznych.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `ExportProductsIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler może służyć jako domyślny punkt wejścia lub rezerwowy dla żądań front-office związanych z modułem. Biorąc pod uwagę główną funkcję modułu, może przekierowywać lub wyświetlać prostą wiadomość, lub może być miejscem na przyszłe funkcje front-office.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminExportProducts.php`
    -   **Nazwa zakładki i zarządzana encja:** Ten kontroler zarządza głównym pulpitem „Export Products Pro” w Panelu administracyjnym PrestaShop, dostępnym poprzez **Katalog > Export Products Pro**. Nie zarządza pojedynczą encją `ObjectModel` w tradycyjnym sensie, ale raczej orkiestruje proces eksportu produktów.
    -   **Odpowiedzialność:**
        -   Wyświetla formularz konfiguracji dla ustawień eksportu (filtry, format, separator itp.).
        -   Obsługuje żądanie POST po kliknięciu przycisku „Eksportuj”.
        -   Przetwarza wybrane pola produktu i kombinacji.
        -   Wykonuje zapytania do bazy danych PrestaShop o dane produktów i kombinacji na podstawie zastosowanych filtrów.
        -   Generuje zawartość pliku CSV lub XML.
        -   Inicjuje pobieranie pliku do przeglądarki użytkownika.
        -   Zarządza funkcjonalnością `ep_remember_settings` w celu zachowania wyborów użytkownika.
-   `controllers/admin/index.php`
    -   **Odpowiedzialność:** Jest to zazwyczaj pusty plik lub plik zawierający prostą instrukcję `die('No direct script access');`, służącą jako środek bezpieczeństwa zapobiegający bezpośredniemu dostępowi do katalogu `controllers/admin`. Nie zawiera aktywnej logiki kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/ExportProductsFeed.php`
    -   **Z jakimi tabelami bazy danych współdziała:** Ta klasa prawdopodobnie współdziała z różnymi podstawowymi tabelami PrestaShop, takimi jak `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` itp.
    -   **Czy rozszerza `ObjectModel` i definicja pól `$definition`:** Jest mało prawdopodobne, aby rozszerzała `ObjectModel` bezpośrednio, ponieważ jej główną rolą jest *zapytanie* i *przetwarzanie* istniejących danych produktów, a nie zarządzanie nową encją bazy danych. Zawierałaby metody do pobierania danych produktów, filtrowania ich i formatowania do eksportu.
    -   **Kluczowe metody publiczne i hermetyzowana logika biznesowa:**
        -   Metody do pobierania danych produktów z różnymi połączeniami (kategorie, producenci, dostawcy, obrazy, opisy).
        -   Metody do obsługi kombinacji produktów i ich specyficznych atrybutów.
        -   Logika do stosowania filtrów (aktywne, dostępne w magazynie, kategoria, producent, dostawca).
        -   Metody do formatowania danych w struktury CSV lub XML.
        -   Potencjalnie metody do obsługi dużych zbiorów danych w celu zapobiegania wyczerpaniu pamięci.
-   `classes/index.php`
    -   **Odpowiedzialność:** Podobnie jak `controllers/admin/index.php`, jest to plik bezpieczeństwa zapobiegający bezpośredniemu listowaniu katalogów lub wykonywaniu plików w katalogu `classes/`.

### 4.4 Zasoby JavaScript (`views/js/`)

Dostarczony spis modułów nie wskazuje na niestandardowe pliki JavaScript (`[]`). Sugeruje to, że front-end modułu (konfiguracja Back Office) opiera się całkowicie na natywnych bibliotekach JavaScript PrestaShop (np. jQuery, podstawowy JS PrestaShop) do obsługi formularzy, lub jego interfejs jest wystarczająco prosty, aby nie wymagać złożonych interakcji po stronie klienta poza standardowymi przesyłaniem formularzy.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dostarczony spis modułów nie wskazuje na niestandardowe pliki CSS (`[]`). Oznacza to, że interfejs Back Office modułu wykorzystuje domyślne style back-office PrestaShop, zapewniając spójny wygląd i działanie bez wprowadzania niestandardowych stylów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`exportproducts/script.tpl`**
    -   **Zakres:** Prawdopodobnie ogólny szablon używany do osadzania małych fragmentów JavaScript lub zmiennych konfiguracyjnych bezpośrednio w HTML, być może podłączony do `displayHeader` lub `displayBackOfficeHeader`, jeśli musi działać na określonych stronach. Biorąc pod uwagę brak plików JS, może zawierać wbudowany JS do walidacji formularzy lub dynamicznego zachowania.
-   **`exportproducts/views/templates/admin/dashboard.tpl`**
    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Jest to główny szablon dla `AdminExportProductsController`. Renderuje cały formularz konfiguracji eksportu, w tym ustawienia ogólne, opcje filtrowania oraz obszerną listę pól produktu i kombinacji, które sprzedawca może wybrać do eksportu. Zawiera również przycisk „Eksportuj”.
-   **`exportproducts/views/templates/admin/form_header.tpl`**
    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Ten szablon prawdopodobnie renderuje wspólną sekcję nagłówka dla formularzy konfiguracji administracyjnej, potencjalnie zawierającą tytuł modułu, opis i być może jakiś tekst wprowadzający lub linki. Jest zaprojektowany do włączania na górze innych szablonów administracyjnych (takich jak `dashboard.tpl`) dla spójności.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł nie wydaje się tworzyć własnych niestandardowych tabel bazy danych.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. `ep_export_format`, `ep_export_active`, `ep_remember_settings`, `ep_export_categories_onlycats` itp.) w standardowej tabeli PrestaShop `ps_configuration`. Te klucze są poprzedzone prefiksem `ep_` dla „Export Products”.
    -   Głównie odczytuje dane z podstawowych tabel PrestaShop: `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` itp.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayModuleRoutes` | Podczas generowania tras dla modułów. | Pozwala modułowi rejestrować niestandardowe przyjazne adresy URL dla swoich kontrolerów front-office (np. `/feed` dla `feed.php`). |
| `moduleRoutes` | Podczas generowania tras dla modułów. | Podobnie jak `displayModuleRoutes`, używany do definiowania niestandardowych wzorców URL i kojarzenia ich z kontrolerami modułów. |
| `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` Panelu administracyjnego. | Potencjalnie używany do włączania `script.tpl` dla wbudowanego JS lub CSS, lub do dodawania specyficznych meta tagów lub zmiennych JS potrzebnych przez interfejs administracyjny. |
| `actionAdminControllerSetMedia` | Przed renderowaniem strony przez kontroler administracyjny. | Używany do rejestrowania plików CSS i JavaScript dla Panelu administracyjnego, zapewniając ich ładowanie tylko wtedy, gdy są potrzebne. (Chociaż nie ma wymienionych plików JS/CSS, ten hook byłby standardowym miejscem, gdyby były obecne). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i profesjonalnego wsparcia dla modułu **Export Products Pro**, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania naszych modułów.
