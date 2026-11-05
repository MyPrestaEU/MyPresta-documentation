---
title: "Google Merchant Center Feed - instrukcja sprzedawcy"
sidebar:
  label: "Google Merchant Center Feed - instrukcja sprzedawcy"
description: "Instrukcja konfiguracji pliku produktów dla Google Merchant Center i rozwiązywania problemów z tym plikiem."
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google merchant center feed na MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/google-merchant-center-feed/)
>
> ---


## 1. Wymagania

Moduł działa na PrestaShop 1.6, 1.7, 8 i 9 oraz na PHP od 5.6 do 8.5.

Serwer musi mieć włączone cURL i JSON. Innego modułu nie potrzebuje.

Przy dziesiątkach tysięcy produktów otwarcie adresu pliku trwa dłużej i potrzebuje więcej pamięci.

Konto Google Merchant Center zakładasz sam.

## 2. Instalacja

1. Wgraj moduł w **Moduły**, **Module Manager** i włącz go.
2. Po instalacji w **Katalog** jest pozycja **Google Merchant Feed**.
3. Moduł nie czyści pamięci podręcznej przy instalacji.

Odinstalowanie zabiera tylko pozycję w Katalogu. Lista plików, pary kategorii, pliki zapisane na serwerze i ustawienie drzewa kategorii zostają. Po ponownej instalacji wracają.

## 3. Konfiguracja

Zrzuty są z angielskiego panelu. Poniżej są polskie nazwy, tam gdzie panel po polsku je pokazuje.

### 3.1 Strona konfiguracji modułu

Wejdź w **Moduły**, **Module Manager**, **Google Merchant Center Feed**, **Konfiguruj**. Nagłówek to **Ustawienia modułu**. Jest jedno pole.

![Ustawienia modułu](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pokaż drzewo kategorii** | **Nie** | **Tak** pokazuje kategorie nadrzędne przy parowaniu kategorii Google. Nie wybiera produktów do pliku. |

Kliknij **Zapisz**. Zobaczysz **Ustawienia zapisano pomyślnie**.

### 3.2 Pulpit

Wejdź w **Katalog**, **Google Merchant Feed**. Nagłówek to **Pliki danych Google Merchant Center**. Zakładka **Pulpit**.

![Pulpit](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

Na pulpicie widać liczbę zapisanych plików, ile razy dziś ktoś otworzył adres, ile razy w ostatnich 7 dniach i ile plików leży na serwerze. Wykres i lista ostatnich uruchomień są puste, dopóki nikt nie otworzy adresu. Na dole jest lista plików ustawionych na zapis na serwer.

### 3.3 Lista plików

Zakładka **Pliki danych**.

![Lista plików](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Gdy listy nie ma, widzisz **Nie masz jeszcze żadnych plików danych** i **Utwórz swój pierwszy plik danych**.

Gdy pliki są, wiersz ma status, nazwę, sklep, ostatnie uruchomienie i adres. Przycisk **Utwórz nowy plik danych** jest nad listą.

- Przełącznik włącza i wyłącza plik. Adres zostaje.
- Plik na żywo ma jeden adres. Google czyta ten adres, a lista powstaje przy każdym otwarciu.
- Zapis na serwer ma dwa adresy. Adres generowania buduje listę i zapisuje plik. Do Google wklejasz adres pliku, nie adres generowania. Gdy pliku jeszcze nie ma, najpierw otwórz adres generowania.
- **Edytuj** otwiera formularz. Kopia dopisuje do nazwy oznaczenie kopii. **Usuń** pyta o potwierdzenie i zabiera wiersz z listy. Plik na dysku zostaje.

### 3.4 Aktualizacje

Zakładka **Aktualizacje**.

![Aktualizacje](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

- **Aktualizacje MyPresta**
- **Sprawdź teraz** pyta raz, czy jest nowsza wersja.
- Powiadomienia automatyczne: **Włączone** albo **Wyłączone**. **Włączone** sprawdza mniej więcej co trzy dni i może pokazać ostrzeżenie w panelu.
- **Strona produktu** otwiera stronę modułu.
- **Zapisz** zapisuje te ustawienia.

### 3.5 Formularz pliku

Kliknij **Utwórz nowy plik danych** albo **Edytuj**. Zakładka nazywa się **Utwórz / Edytuj plik danych**. Formularz jest długi. Na dole są dwa przyciski. **Zapisz plik danych** zapisuje ustawienia i wraca do listy. **Zapisz i pobierz** zapisuje je i od razu oddaje plik do pobrania w przeglądarce. Żaden z nich nie wysyła produktów do Google. Google dostaje listę dopiero wtedy, gdy otworzy adres z listy.

Zrzut pokazuje górę formularza: nazwę, aktywność i początek opcji katalogu.

![Góra formularza](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Wpisz nazwę, po której poznasz plik na liście, na przykład język i kraj. Puste pole przy zapisie dostaje nazwę **Plik danych bez tytułu**. **Aktywny** zostaw na **Tak**. **Nie** nie kasuje adresu ani ustawień. Otwarcie takiego adresu mówi, że plik jest wyłączony, a produkty w sklepie zostają bez zmian. Pole **Sklep** widać tylko wtedy, gdy w PrestaShop włączone jest wiele sklepów. Plik należy do wybranego sklepu i jego adres działa w tym sklepie.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Nazwa pliku danych** | puste, wymagane | Nazwa na liście. Po niej odróżnisz kilka plików, na przykład osobny plik na język. |
| **Aktywny** | **Tak** | **Nie** zostawia adres. Google przy otwarciu dostaje informację, że plik jest wyłączony. |
| **Sklep** | bieżący sklep | Pole jest tylko przy wielu sklepach. Adres działa w wybranym sklepie. |

### 3.6 Opcje katalogu

**Zapamiętaj ustawienia** na **Tak** sprawia, że następny nowy plik otwiera się z tymi samymi wyborami. Plik, który właśnie zapisujesz, i tak trzyma własne ustawienia. Wyłącz to, gdy kolejny plik ma być inny, na przykład w innej walucie albo tylko dla jednego producenta.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Zapamiętaj ustawienia** | **Tak** | Następny nowy plik startuje z tymi samymi wyborami. Zapisany plik trzyma swoje. |

### 3.7 Co eksportować

Tu decydujesz, jaki plik powstanie i czy Google ma czytać listę na żywo, czy gotowy plik z serwera.

![Co eksportować](https://mypresta.eu/docs/images/docs/gmfeed-form-export.webp)

Zostaw **CSV**, jeśli Google nie wymaga XML. **Produkty** dają jeden wiersz na produkt. Druga opcja daje jeden wiersz na każdy wariant. Wtedy na formularzu pojawia się też **Combination title**: sama nazwa produktu, nazwa z wartością wariantu albo nazwa z zapisem „etykieta: wartość”. Przy samych produktach tego pola nie ma.

**Zapisz do pliku** na **Nie** oznacza, że adres z listy buduje listę przy każdym otwarciu i nic nie zostaje na dysku. Ustaw **Tak**, gdy chcesz plik na serwerze. Pod polem widać wtedy ostrzeżenie: zapis działa dla adresu z tej strony i ten adres musi mieć klucz. Adres skopiowany z listy już go ma. Adres bez klucza pokazuje **Access denied** i nic nie zapisuje. Zalogowany w panelu możesz wygenerować plik bez wklejania klucza.

W **Nazwa pliku** zostaw litery, cyfry, myślnik i podkreślenie. Inne znaki znikają. Puste pole dostaje nazwę z typu eksportu. **Jak rozpoznać produkt** to kolumna ID, po której Google odróżnia pozycje. Zwykle zostaw numer produktu. Numer wariantu albo połączenie obu ma sens, gdy eksportujesz warianty i każda kombinacja ma być osobną pozycją.

| Pole | Na starcie | Co robi |
|---|---|---|
| Typ pliku | **CSV** | **CSV** albo **XML**. CSV jest lżejszy. XML wybierz, gdy Google ma dostać XML. |
| Co eksportować | **Produkty** | Jeden wiersz na produkt albo jeden wiersz na wariant. |
| **Zapisz do pliku** | **Nie** | **Nie**: adres pokazuje listę od razu. **Tak**: lista zapisuje się też na serwerze. Do zapisu adres musi mieć klucz z tej strony. |
| **Nazwa pliku** | puste | Zostają litery, cyfry, myślnik i podkreślenie. Puste bierze typ eksportu. |
| Jak rozpoznać produkt | id produktu | Numer produktu, numer wariantu albo oba. To kolumna ID w pliku. |

### 3.8 Rozmiar, płeć, kolor i wiek

Te kolumny Google chce przy odzieży i podobnych produktach. Na starcie są wyłączone i do pliku nie wchodzą. Włącz grupę tylko wtedy, gdy w sklepie masz tę cechę albo atrybut.

![Rozmiar, płeć, kolor i wiek](https://mypresta.eu/docs/images/docs/gmfeed-form-attributes.webp)

Przy rozmiarze widać listę atrybutów sklepu. Możesz zaznaczyć kilka: przytrzymaj Ctrl i kliknij. Gdy produkt nie ma wybranego atrybutu, do pliku idzie wartość domyślna. To samo dotyczy płci, koloru i wieku. Dodatkowe pola źródła, cechy i atrybutu pokazują się po ustawieniu danej grupy na **Tak**. Wartości płci to male, female i unisex. Wartości wieku to newborn, infant, toddler, kids i adult. Wpisz je tak, jak wymaga Google, a nie własnym słowem ze sklepu, jeśli Google ma je rozpoznać.

| Grupa | Pola |
|---|---|
| Rozmiar | czy eksportować, atrybut rozmiaru, wartość gdy atrybutu nie ma |
| Płeć | czy eksportować, skąd brać, cecha, atrybut, wartość domyślna |
| Kolor | czy eksportować, skąd brać, atrybut, cecha, wartość domyślna |
| Wiek | czy eksportować, skąd brać, cecha, atrybut, wartość domyślna |

### 3.9 Ustawienia pliku

Tu jest treść wiersza: identyfikatory, wysyłka, opisy, nazwy, stan magazynu, zdjęcia i ceny. Zostaw wartości startowe, jeśli Google ma dostać zwykły katalog. Zmieniaj pole dopiero wtedy, gdy w Merchant Center brakuje konkretnej kolumny albo Google odrzuca wartość.

![Identyfikatory i wysyłka](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-a.webp)

**Include item_group_id** łącz warianty jednego produktu w jedną grupę. Włącz to przy eksporcie wariantów. **Unique product identifier** wskazuje, skąd brać GTIN. Na starcie jest kod UPC. Wybierz EAN-13, referencję, MPN albo ISBN, jeśli tam trzymasz kod kreskowy. Ostatnia opcja zostawia pole puste i mówi Google, że identyfikatora nie ma. **Include identifier_exists field** dodaje kolumnę, która to mówi wprost. **Include adult field** zostaw na „nie wstawiaj”, chyba że sprzedajesz produkty dla dorosłych. Wtedy wstaw true albo false.

**Include shipping price** na starcie nic nie wstawia. Możesz policzyć wysyłkę osobno dla każdej pozycji albo wpisać jedną kwotę. Przy liczeniu wybierz strefę. Na zrzucie widać strefy tego sklepu. Liczenie dla każdej pozycji zużywa więcej zasobów serwera niż jedna kwota. **Include product's additional shipping cost** dolicza dodatkową wysyłkę z karty produktu. **Manual shipping value** to kwota, gdy wybrałeś wysyłkę ręczną. Na starcie jest 0. **Include weight** dodaje wagę.

![Wysyłka, opisy i nazwa](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-b.webp)

**Product type** wstawia twoją ścieżkę kategorii jako product_type. **Product type - include category ID** dopisuje do niej numer kategorii, żeby dwie kategorie o tej samej nazwie nie zlały się w jedną. **Short description** bierze krótki opis albo długi opis. **Remove html from descriptions** na **Yes** zabiera znaczniki. Zostaw **No**, gdy opis ma zostać z formatowaniem. **Product name** to nazwa produktu albo meta tytuł.

![Format nazwy, język i stan](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-c.webp)

**Format name** zostaw bez zmian. Google nie przyjmuje nazwy pisanej samymi wielkimi literami. Jeśli nazwy w sklepie takie są, wybierz małe litery, pierwsze słowo albo każde słowo. **Remove selected characters from product name** wycina wpisane znaki. Przykład z formularza to x, = i przecinek. Zostaw puste, gdy nic nie wycinasz. Nie wstawiaj samej spacji. **Language** to język nazw i opisów. **Delimiter** to separator CSV. Na starcie jest pionowa kreska. Google pozwala jej użyć. **Wrap strings in double quotes** owiń pola cudzysłowem, gdy plik otwierasz w programie, który tego wymaga.

**Information about stock** na starcie podaje prawdziwy stan. Pozostałe opcje wymuszają jeden status na wszystkie produkty: na stanie, brak, backorder, albo backorder pokazany jako „na stanie”. **Availability date** uzupełnia datę dla produktów na zamówienie, które nie mają własnej daty. **Include quantity info** dodaje kolumnę z liczbą sztuk.

![Zdjęcia i ceny](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-d.webp)

**Default manufacturer value** to tekst marki, gdy produkt nie ma producenta. Na starcie jest Default. **Image size for product pictures** to rozmiar zdjęcia w adresie. Lista pochodzi ze sklepu. **Use default product picture if combination will not have associated photo** podstawia zdjęcie produktu, gdy wariant nie ma własnego. **How many pictures you want to export?** na starcie bierze tylko okładkę. **Export all pictures** dodaje resztę zdjęć.

**Currency** to waluta cen. Na starcie jest waluta sklepu. **Price tax included or excluded** na starcie daje cenę z podatkiem. **Include specific prices** na **Yes** uwzględnia ceny specyficzne, gdy waluta pliku nie jest walutą, w której patrzysz na sklep. **Export prices for selected group** liczy ceny dla wybranej grupy klientów. Na starcie jest grupa gościa. **Export also unit price** dodaje cenę za jednostkę. **Export prices for selected country** liczy podatek i rabaty dla kraju. Na starcie jest kraj sklepu. Na zrzucie widać kraj i walutę sklepu testowego, nie stałą wartość modułu.

| Pole | Na starcie | Co robi |
|---|---|---|
| Identyfikator grupy | **Nie** | Łączy warianty jednego produktu. Włącz przy eksporcie wariantów. |
| Unikalny identyfikator | kod UPC | UPC, EAN-13, referencja, MPN, ISBN albo puste. Puste mówi, że kodu nie ma. |
| Pole identifier_exists | **Nie** | Osobna kolumna, czy identyfikator istnieje. |
| Pole adult | nie wstawiaj | Nie wstawiaj, wstaw jako true albo jako false. |
| Cena wysyłki | nie wstawiaj | Liczona osobno dla pozycji albo wpisana ręcznie. |
| Dodatkowy koszt wysyłki produktu | **Nie** | Dolicza dodatkową wysyłkę z karty produktu. |
| Ręczna kwota wysyłki | 0 | Kwota, gdy wysyłka jest ręczna. Waluta przy polu jest walutą sklepu. |
| Strefa do wyliczenia wysyłki | strefy sklepu | Strefa, z której liczona jest wysyłka. |
| Waga | **Nie** | Kolumna wagi. |
| Typ produktu | **Nie** | Twoja ścieżka kategorii w pliku. |
| Do typu dopisz numer kategorii | **Nie** | Numer kategorii obok nazwy. |
| Krótki opis | krótki opis | Krótki opis albo długi opis. |
| Usuń HTML z opisów | **Nie** | **Tak** zabiera znaczniki. |
| Nazwa produktu | nazwa produktu | Albo meta tytuł. |
| Tytuł wariantu | sama nazwa produktu | Widać tylko przy eksporcie wariantów. |
| Format nazwy | bez zmian | Pierwsza litera, każde słowo albo same małe litery. |
| Znaki do wycięcia z nazwy | puste | Wpisywane znaki znikają z nazwy. |
| Język | język sklepu | Nazwy i opisy w pliku. |
| Separator | pionowa kreska | Znak między kolumnami CSV. |
| Cudzysłów wokół tekstu | **Nie** | **Tak** owija pola cudzysłowem. |
| Informacja o stanie | prawdziwy stan | Wszystkie na stanie, wszystkie brak, wszystkie backorder albo backorder jako „na stanie”. |
| Data dostępności | puste | Data dla produktów na zamówienie, gdy produkt nie ma własnej. |
| Liczba sztuk | **Nie** | **Tak** wstawia ilość. |
| Marka, gdy jej nie ma | Default | Tekst marki bez producenta. |
| Rozmiar zdjęcia | rozmiary ze sklepu | Który rozmiar zdjęcia wstawić do adresu. |
| Zdjęcie produktu, gdy wariant nie ma swojego | **Nie** | Przy wariantach bez własnego zdjęcia. |
| Ile zdjęć | tylko okładka | Albo wszystkie zdjęcia. |
| Waluta | waluta sklepu | Ceny w pliku. |
| Podatek w cenie | z podatkiem | Z podatkiem albo bez. |
| Ceny specyficzne | **Tak** | Gdy waluta pliku nie jest walutą, w której patrzysz na sklep. |
| Grupa cen | grupa gościa | Ceny dla tej grupy klientów. |
| Cena jednostkowa | **Nie** | Dodatkowa kolumna ceny za jednostkę. |
| Kraj cen | kraj sklepu | Kraj do podatku i rabatów. |

### 3.10 Wybrane produkty

Zostaw **All**, gdy do pliku mają wejść wszyscy producenci, wszyscy dostawcy i wszystkie kategorie. Wybierz jedną pozycję, gdy Google ma dostać tylko ten wycinek katalogu. To zawęża plik. Nie zastępuje wykluczeń z następnej sekcji.

![Producent, dostawca i kategoria](https://mypresta.eu/docs/images/docs/gmfeed-form-products.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| Producent | **All** | Jeden producent albo wszyscy. |
| Dostawca | **All** | Jeden dostawca albo wszyscy. |
| Kategoria | **All** | Jedna kategoria albo wszystkie. |

### 3.11 Wykluczenia

Tu wyrzucasz produkty, które przeszły filtr z punktu 3.10. Na starcie prawie nic nie jest wykluczone: produkty bez zdjęcia zostają, wyłączone produkty zostają, produkty bez stanu zostają.

![Wykluczenia](https://mypresta.eu/docs/images/docs/gmfeed-form-exclude.webp)

**Exclude categories**: wpisz początek nazwy kategorii i wybierz ją z podpowiedzi. Produkty przypisane do niej wypadają. **Exclude products without pictures** na **Yes** wyrzuca produkty bez zdjęcia. Zostaw **No**, gdy mają zostać. **Products's availability** na „tylko aktywne” pomija produkty wyłączone w sklepie. **Products's stock** na „tylko na stanie” pomija ilość równą zero i mniejszą.

**Exclude products with specific reference** włącz, a potem wpisz początek referencji. Wypadają też warianty, których referencja tak się zaczyna. **Exclude products worth less than defined value** wyrzuca produkty tańsze niż wpisana kwota. Waluta przy polu jest walutą sklepu.

**Exclude products** to wyszukiwarka. Wpisz początek nazwy, wybierz produkt albo kliknij **Add all search results**, żeby dodać całą listę wyników.

| Pole | Na starcie | Co robi |
|---|---|---|
| Kategorie do pominięcia | puste | Wpisz nazwę i wybierz kategorię. Produkty z niej wypadają. |
| Produkty bez zdjęcia | **Nie** | **Tak** pomija produkty bez zdjęcia. |
| Dostępność | wszystkie produkty | Albo tylko włączone w sklepie. |
| Stan magazynu | wszystkie produkty | Albo tylko te na stanie. |
| Pomijaj po referencji | **Nie** | Włącza filtr po początku referencji. Działa też na warianty. |
| Początek referencji | puste | Tekst, od którego referencja wypada. |
| Pomijaj tańsze niż | **Nie** | Próg ceny w walucie sklepu. |
| Kwota progu | puste | Produkty poniżej tej kwoty wypadają. |
| Wskazane produkty | puste | Wyszukiwarka produktów do pominięcia. |

### 3.12 Limit

Zostaw 0, gdy cały katalog ma iść do jednego pliku. Obok pola widać liczbę produktów w sklepie i komunikat, że moduł wyeksportuje je do jednego pliku. Przy słabym hostingu ustaw limit i numer części. Formularz podaje przykład: 3000 produktów i limit 1000 dają trzy pliki, części 1, 2 i 3. Każda część to osobny zapisany plik, ze swoim adresem.

![Limit i kod sklepu](https://mypresta.eu/docs/images/docs/gmfeed-form-limit.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| Limit produktów | 0 | 0 albo puste: bez limitu. Obok widać liczbę produktów w sklepie. |
| Część pliku | 0 | Numer części, gdy jeden katalog dzielisz na kilka plików. |

### 3.13 Kod sklepu stacjonarnego

Ta sekcja jest na tym samym zrzucie, pod limitem. Zostaw **Include store code to feed** na **No**, jeśli nie wystawiasz produktów w sklepie stacjonarnym w Google. **Store code** musi być identyczny z kodem w Google Business, łącznie z wielkością liter.

| Pole | Na starcie | Co robi |
|---|---|---|
| Wstaw kod sklepu | **Nie** | Kolumna kodu sklepu stacjonarnego. |
| Kod sklepu | puste | Ten sam kod co w Google Business. Wielkość liter ma znaczenie. |

### 3.14 Kategorie Google

Na dole formularza jest wiersz dla każdego języka sklepu. **Pair categories** otwiera parowanie kategorii sklepu z kategorią Google. **Synchronize** pobiera listę kategorii Google dla tego języka. Gdy pliku listy nie ma, przycisk przy języku jest czerwony i każe najpierw zsynchronizować. Na zrzucie język en-us ma gotowy plik, a fr jeszcze nie.

![Kategorie Google](https://mypresta.eu/docs/images/docs/gmfeed-form-categories.webp)

**Pokaż drzewo kategorii** z punktu 3.1 zmienia tylko rysunek listy przy parowaniu: widać kategorie nadrzędne. Nie wybiera produktów do pliku. Lista, która jest w module od instalacji, jest po angielsku, dla USA, z lutego 2015. Inny język dostajesz przyciskiem **Synchronize** albo wtedy, gdy plik tej listy już leży w module.

Na dole jeszcze raz **Save & download** i **Save feed**.

## 4. Front sklepu

Klient na stronie sklepu nic nie widzi. Nie ma bloku na produkcie, w koszyku ani w stopce. Dlatego nie ma zrzutu sklepu. Jedyne, co moduł wystawia na zewnątrz, to adres pliku.

Skopiuj adres z listy **Pliki danych**. Nie składaj go sam i nie doklejaj własnych parametrów. Moduł i tak weźmie ustawienia zapisane przy tym pliku.

Gdy **Zapisz do pliku** jest na **Nie**, otwarcie adresu od razu zwraca CSV albo XML. Google wklejasz ten adres. Gdy zapis jest włączony, na liście są dwa adresy. Adres generowania buduje listę i zapisuje plik. Do Google wklejasz adres pliku. Jeśli pliku jeszcze nie ma, najpierw otwórz adres generowania.

Zapis formularza nie wysyła produktów do Google. Lista powstaje przy otwarciu adresu. Potem Google pobiera ją według własnego harmonogramu w Merchant Center.

| Co widać po otwarciu | Co zrobić |
|---|---|
| feed does not exists | Zły numer albo plik usunięty z listy. Skopiuj adres jeszcze raz. |
| Feed is disabled | Włącz **Aktywny**. Adres zostaje ten sam. |
| Feed is not available in this store | Plik należy do innego sklepu. Otwórz adres w tym sklepie albo przypisz plik do właściwego. |
| Access denied | Zapis na serwer jest włączony, a w adresie nie ma klucza. Skopiuj adres z listy. |
| Invalid export path | Skróć nazwę pliku. Zostaw litery, cyfry, myślnik i podkreślenie. |
| Unable to save export file | Serwer nie zapisał pliku. Sprawdź miejsce na dysku i prawo zapisu w katalogu modułu. |

## 5. Problemy

**Google pokazuje wczorajsze produkty.** Moduł nic nie wysyła do Google. Otwórz adres z listy i sprawdź, czy lista jest aktualna. Jeśli zapis na serwer jest włączony, najpierw otwórz adres generowania, a do Google daj adres pliku. Potem w Merchant Center pobierz plik ręcznie. Dalsze pobrania idą według harmonogramu Google.

**W pliku prawie nie ma produktów.** Po kolei sprawdź **Product Manufacturer**, **Product Supplier** i **Product Category**. Potem wykluczenia: tylko aktywne, tylko na stanie, kategorie, początek referencji, próg ceny i ręcznie wskazane produkty. Na końcu limit i numer części. **Pokaż drzewo kategorii** tego nie robi.

**Drzewo kategorii jest włączone, a plik ma te same produkty.** Tak ma być. Drzewo tylko pokazuje kategorie nadrzędne przy **Pair categories**.

**Odinstalowałem moduł i lista zniknęła z menu.** Zainstaluj go ponownie. Lista plików, pary kategorii i pliki na serwerze zostają. Zniknęła tylko pozycja **Google Merchant Feed** w Katalogu.

**Duży katalog urywa się w połowie.** W sekcji limitu ustaw liczbę produktów i numer części. Zrób osobny plik dla każdej części i każdy adres wklej w Google osobno.

**Przy języku kategorii Google jest czerwony napis, że pliku nie ma.** Kliknij **Synchronize** w tym wierszu. Dopiero potem **Pair categories**.

## 6. Dla developera

### 6.1 Przegląd

`gmfeed` 2.4.3. Klasa `gmfeed` rozszerza `Module`. Nazwa na liście modułów to stały tekst `Google Merchant Center Feed`. Autor MyPresta.eu. Zakładka `administration`.

Formularz zapisuje wiersz `gms`. Pole `conf` to query string. Adres frontu czyta ten wiersz, buduje CSV albo XML i kończy odpowiedź. Zapis do pliku pisze plik w `/modules/gmfeed/`.

### 6.2 Pliki

- `gmfeed.php`: install, uninstall, strona konfiguracji, token zapisu, sanityzacja nazwy, rozszerzenia i typu.
- `controllers/admin/AdminExportProductsFeedGoogle.php`: pulpit, lista, formularz, zapis.
- `controllers/front/feed.php`: generowanie. `initContent()` woła `generateFeed()` i `die()`.
- `model/gms.php`: wiersz pliku i adres. Klasa `gms`.
- `model/google.php`: pary kategorii. Klasa `pixelgoogle`.
- `lib/updateChecker.php`: klasa `gmfeedUpdate`.
- `lib/searchTool/searchTool.php`: podpowiedzi kategorii i produktów.
- `views/templates/admin/`: `layout.tpl`, `dashboard.tpl`, `feeds.tpl`, `form-chrome.tpl`.
- `google/en-us.txt`: taksonomia. Pierwsza linia `# Google_Product_Taxonomy_Version: 2015-02-19`.
- `.htaccess` w katalogu modułu blokuje uruchamianie PHP.

### 6.3 Kontrolery

Admin: `AdminExportProductsFeedGoogle`, rodzic `AdminCatalog`. Widoki `gmfeed_view`: `dashboard`, `feeds`, `form`, `updates`.

Front: `gmfeedfeedModuleFrontController`. Adres `module/gmfeed/feed?feed=` i numer.

Klucz zapisu to HMAC-SHA256 z `gmfeed.write.` i id sklepu, sekret `_COOKIE_KEY_`. Zalogowany pracownik zapisuje bez klucza. Parametry `export_` i `gmfeed_` z requestu są wyrzucane i zastępowane zapisanymi. Zostają klucz i `debug_feed`.

Wyłączony plik zwraca HTTP 503 i `Feed is disabled`. Puste albo zbyt krótkie `conf` kończy się `feed does not exists`. Inne `id_shop` kończy się `Feed is not available in this store`.

### 6.4 Hooki

Jest jeden hook: `actionAdminControllerSetMedia`. Ładuje fancybox i autocomplete tylko na `AdminExportProductsFeedGoogle`. Moduł nie wystawia własnych hooków. Nie ma `enable()` ani `disable()`.

### 6.5 Nadpisania

Ten moduł nie nadpisuje klas ani kontrolerów PrestaShop.

### 6.6 Baza

| Tabela | Zawartość |
|---|---|
| `pixelgoogle` | Para kategorii: `id_google`, `id_category`, `id_lang`, `value`. |
| `gms` | Plik: `name`, `id_shop`, `conf`, `active`. `CREATE` nie stawia klucza głównego. |
| `gms_log` | Otwarcie adresu: czas, liczba, status, zapis pliku, nazwa, format, źródło. |

`ensureSchema` na stronie katalogu dopisuje `active` i `id_shop`, tworzy `gms_log`, gdy brak, i uzupełnia `id_shop` 0 sklepem domyślnym. Uninstall tabel nie kasuje.

### 6.7 Klucze i tłumaczenia

`pf_tree`: brak klucza oznacza wyłączone. Reszta formularza jest w `gms.conf`. **Zapamiętaj ustawienia** równe 1 kopiuje pola do `gm_{pole}`, bez klucza zapisu, skrótu, aktywności, sklepu i id pliku. Przy edycji brakujące pole bierze wartość startową formularza, nie kopię `gm_`. Starszy klucz `notepad_products` jest kopiowany do `gmfeed_products`, gdy nowego nie ma.

Aktualizacje: `mypresta_updates`, `update_gmfeed` (przerwa 172800 sekund), `updatev_gmfeed`. Brak `mkey` idzie jako `nokey`.

Nowy język to plik `translations/{iso}.php`. Napisy z `$this->l()` biorą się z angielskiego źródła. Nazwa na liście modułów nie przechodzi przez `$this->l()`. W `translations/de.php` napisy strony konfiguracji są po czesku.

Domyślny typ eksportu zapisany jako `product` przy budowie pliku jest traktowany jako `products`. Dozwolone formaty zapisu nazwy to `csv`, `xml` i `txt`. Formularz pokazuje CSV i XML.

### 6.8 Rozszerzanie

Motyw nie ma czego nadpisać na stronie sklepu, bo front nie renderuje szablonu. Inny układ kolumn wymaga zmiany kodu modułu. Taksonomię w innym języku dokładasz plikiem `google/{kod}.txt`.

## 7. Pomoc

Strona modułu: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).

Żeby napisać w sprawie tego modułu, zaloguj się na konto klienta na [mypresta.eu](https://mypresta.eu/), przejdź do [kontaktu](https://mypresta.eu/contact.html) i wybierz temat **Support for paid modules**. Formularz podaje, że logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
