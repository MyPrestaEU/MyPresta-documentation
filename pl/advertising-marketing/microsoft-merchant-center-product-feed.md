---
title: "Microsoft Merchant Center Product Feed - dokumentacja i instrukcja obsługi"
description: "Instrukcja konfiguracji plików produktowych Microsoft Merchant Center oraz rozwiązywania problemów z ich generowaniem i katalogami."
sidebar:
  label: "Microsoft Merchant Center Product Feed - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Microsoft Merchant Center Product Feed na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


## 1. Wymagania

Przed instalacją modułu upewnijcie się, że sklep i hosting spełniają następujące wymagania:

- PrestaShop 1.7, 8 lub 9.
- PHP od 7.1 do 8.5.
- Rozszerzenia PHP: cURL, JSON, hash oraz SimpleXML, jeśli generujecie pliki produktowe XML.
- Aktywne konto Microsoft Merchant Center, na którym można utworzyć katalog i podać adres jego pliku produktowego.
- Żaden inny moduł PrestaShop nie jest wymagany.

Duży katalog wymaga odpowiednio długiego czasu wykonywania skryptów PHP i wystarczającej ilości pamięci do zebrania produktów, obliczenia cen i kosztów wysyłki oraz utworzenia danych wyjściowych. Jeśli jeden pełny plik produktowy przekracza limity hostingu, użyjcie opcji **Limit number of products in feed** razem z **Part of feed**, aby podzielić go na mniejsze pliki.

## 2. Instalacja

1. Otwórzcie **Modules → Module Manager**.
2. Kliknijcie **Upload a module** i prześlijcie plik ZIP modułu.
3. Zainstalujcie **Microsoft Merchant Center Feed**.
4. Otwórzcie **Catalog → Microsoft Merchant Feed**. Jest to obszar roboczy do tworzenia plików produktowych, kopiowania adresów katalogów, monitorowania uruchomień i parowania kategorii.
5. Jeśli nazwy kategorii powtarzają się w różnych gałęziach katalogu, otwórzcie **Modules → Module Manager**, znajdźcie moduł, kliknijcie **Configure** i włączcie **Show categories tree**.

Instalacja nie czyści pamięci podręcznej PrestaShop.

Aby usunąć moduł, odinstalujcie go w **Module Manager**. Odinstalowanie usuwa pozycję **Microsoft Merchant Feed** z menu **Catalog**, ale zachowuje zapisane pliki produktowe, historię generowania, powiązania kategorii, zapamiętane ustawienia formularza, wygenerowane pliki katalogów oraz pobrane dane taksonomii. Po ponownej instalacji moduł może zatem wykorzystać zachowane dane.

## 3. Konfiguracja i praca w panelu administracyjnym

Aby opublikować katalog, wykonajcie następujące czynności:

1. Otwórzcie **Catalog → Microsoft Merchant Feed** i wybierzcie **Create new feed**.
2. Wpiszcie **Feed name**, pozostawcie **Active** ustawione na **Yes**, wybierzcie opcje danych wyjściowych i produktów, powiążcie **Microsoft Categories**, a następnie kliknijcie **Save feed**.
3. Wybierzcie jedną z metod publikacji:
   - W przypadku pliku generowanego na żywo pozostawcie **Save to file** ustawione na **No**. Skopiujcie **Live catalog URL**. Microsoft wywołuje ten adres, a moduł ponownie generuje plik produktowy przy każdym żądaniu.
   - W przypadku pliku statycznego ustawcie **Save to file** na **Yes**. Wywołajcie poufny adres **Generate / cron URL** ręcznie lub za pomocą harmonogramu. Po pierwszym udanym wygenerowaniu skopiujcie **Catalog file URL**. Do Microsoft Merchant Center przekażcie adres pliku katalogu, nigdy adres generowania.
4. Utwórzcie lub otwórzcie właściwy katalog w Microsoft Merchant Center i wklejcie skopiowany adres pliku generowanego na żywo lub pliku katalogu jako źródło danych.
5. Wróćcie do **Dashboard**, aby sprawdzić, czy uruchomienia są rejestrowane oraz czy zapisany plik jest gotowy, gdy używany jest tryb plikowy.
6. Otwórzcie sekcję **Microsoft Categories** danego pliku produktowego, zsynchronizujcie taksonomię dla jego języka i użyjcie **Pair categories**, aby połączyć kategorie sklepu z kategoriami zakupowymi Microsoft.
7. Aby wstrzymać publikację bez zmiany adresu, wyłączcie plik produktowy w sekcji **Feeds**. Ustawienie **Active** na **Off** zatrzymuje generowanie, a ponowne ustawienie na **On** wznawia działanie tego samego pliku pod tym samym adresem.

Zrzuty ekranu w tej instrukcji pochodzą z angielskiej wersji panelu administracyjnego.

### 3.1 Ustawienia modułu

Otwórzcie **Modules → Module Manager**, znajdźcie **Microsoft Merchant Center Feed** i kliknijcie **Configure**.

![Ustawienia modułu z opcją Show categories tree](https://mypresta.eu/docs/images/docs/mmcfeed-module-settings.webp)

| Pole | Wartość początkowa | Działanie |
|---|---|---|
| **Show categories tree** | No | Obszar roboczy plików produktowych znajduje się w **Catalog → Microsoft Merchant Feed**. Można tam powiązać kategorie sklepu z kategoriami Microsoft Shopping. Ustawcie to pole na **Yes**, aby w oknie parowania wyświetlać ścieżkę nadrzędną każdej kategorii. Ścieżki nadrzędne ułatwiają rozróżnienie kategorii o identycznych nazwach. Kliknijcie **Save**; strona potwierdzi zapis komunikatem **Settings saved properly**. |

### 3.2 Lista plików produktowych

Otwórzcie **Catalog → Microsoft Merchant Feed**, a następnie wybierzcie **Feeds**.

![Lista plików produktowych](https://mypresta.eu/docs/images/docs/mmcfeed-feeds.webp)

Jeśli nie istnieje żaden plik produktowy, strona wyświetla **You have no feeds yet** oraz **Create your first feed**. W przeciwnym razie dostępne są następujące kolumny:

| Kolumna | Wyświetlane informacje |
|---|---|
| **Status** | **On** lub **Off**. Użyjcie przełącznika, aby wstrzymać lub wznowić plik produktowy bez usuwania go ani zmiany jego adresu. |
| **Feed** | Nazwa pliku produktowego oraz oznaczenia formatu pliku, eksportu produktów lub wariantów, języka i trybu **Live** albo **File**. |
| **Shop** | Sklep, do którego należy plik produktowy. W trybie multistore plik spoza bieżącego sklepu jest oznaczony jako **Not available in this store**. |
| **Last run** | Liczba wygenerowanych pozycji i czas ostatniego uruchomienia. Przed pierwszym wywołaniem wyświetla **Never** i **No cron call yet**. |
| **Catalog URL** | W trybie na żywo adres **Live catalog**. W trybie plikowym poufny adres **Generate / cron** i publiczny adres **Catalog file**. Skopiujcie adres za pomocą znajdującego się obok przycisku kopiowania. |
| **Actions** | Polecenia dostępne dla danego pliku produktowego. |

Poszczególne działania mają następujące zastosowanie:

- **Edit** otwiera wszystkie zapisane opcje.
- **Duplicate** tworzy kopię i otwiera ją do sprawdzenia. Jeśli kopia ma być niezależna, przed zapisaniem zmieńcie jej nazwę, nazwę pliku, sklep, filtry lub inne ustawienia.
- **Generate** wywołuje generator w trybie plikowym.
- **Open file** otwiera zapisany plik w trybie plikowym.
- **Open** generuje i otwiera plik produktowy działający na żywo.
- **Delete** trwale usuwa rekord pliku produktowego po potwierdzeniu.

Po wykonaniu operacji strona może wyświetlić:

- **Feed saved. Its catalog URL is ready to use.**
- **Feed removed.**
- **Feed duplicated. Review the copy and save if you need a different filename or URL.**

### 3.3 Dashboard

Wybierzcie **Dashboard**, aby monitorować działanie plików produktowych.

![Dashboard](https://mypresta.eu/docs/images/docs/mmcfeed-dashboard.webp)

Podsumowanie pokazuje **Saved feeds**, udane **Cron runs today**, produkty wygenerowane dzisiaj, **Runs last 7 days**, średni czas generowania oraz liczbę gotowych **Saved files**. Wykres **Catalog generation activity** przedstawia ostatnie 14 dni. Lista **Recent runs** zawiera najnowszy plik produktowy, czas, liczbę pozycji, czas trwania, format oraz informację, czy plik został zapisany.

Tabela **Generated files** zawiera każdy plik produktowy działający w trybie plikowym wraz ze sklepem, nazwą pliku, rozmiarem, stanem i czasem ostatniej aktualizacji. **Waiting for first cron** oznacza, że konfiguracja została zapisana, ale adres generowania nie utworzył jeszcze pliku. **On disk** oznacza, że plik jest dostępny pod adresem pliku katalogu.

### 3.4 Karta Updates

Wybierzcie **Updates**, aby porównać zainstalowany moduł z aktualizacjami MyPresta.

![Karta Updates](https://mypresta.eu/docs/images/docs/mmcfeed-updates.webp)

| Pole | Wartość początkowa | Działanie |
|---|---|---|
| **Manual Check** | Brak wyniku do czasu sprawdzenia | Kliknijcie **Check Now** po instalacji lub gdy spodziewacie się nowej wersji. Moduł jednokrotnie łączy się z usługą aktualizacji, porównuje wersje i natychmiast wyświetla **Module is up to date!** albo **New version available!** |
| **Automatic Notifications** | Bieżące wspólne ustawienie aktualizacji MyPresta | Ustawcie **Enabled**, aby panel administracyjny sprawdzał aktualizacje mniej więcej co trzy dni i wyświetlał pracownikom ostrzeżenie o nowszej wersji. Ustawcie **Disabled**, jeśli aktualizacje sprawdzacie ręcznie. Kliknijcie **Save**, aby zastosować ustawienie. |
| **Product Page** | Dostępny odnośnik | Otwiera oficjalną stronę modułu z informacjami i zasobami pomocy. Nie wymaga konfiguracji. |

### 3.5 Tworzenie i edycja pliku produktowego

Wybierzcie **Create new feed** lub kliknijcie **Edit** obok istniejącego pliku produktowego. Pola są wyświetlane w opisanej poniżej kolejności. Opcje zależne od sklepu pochodzą z języków, walut, krajów, grup, typów obrazów, cech, atrybutów, kategorii, producentów, dostawców, stref i sklepów skonfigurowanych w PrestaShop.

Kliknijcie **Save feed**, aby zapisać dane i wrócić do listy. Kliknijcie **Save & download**, aby zapisać ustawienia i natychmiast pobrać nowo wygenerowany plik CSV lub XML. Podczas edycji strona pokazuje również właściwy **Live catalog URL** albo adresy **Generate / cron URL** i **Catalog file URL**.

![Tworzenie lub edycja pliku produktowego: nazwa, stan, format, typ i tryb plikowy](https://mypresta.eu/docs/images/docs/mmcfeed-form-top.webp)

**Tożsamość pliku produktowego i format wyjściowy**

| Pole | Wartość początkowa | Działanie |
|---|---|---|
| **Feed name** | Puste | Wpiszcie wymaganą, łatwo rozpoznawalną nazwę używaną na liście plików produktowych. Jeśli do zapisu trafi pusty formularz, nazwa zostanie zapisana jako **Untitled feed**. |
| **Active** | Yes | Pozostawcie włączone, aby zezwolić na generowanie. Ustawcie **No**, aby wstrzymać plik produktowy z zachowaniem jego adresu i ustawień. |
| **Shop** | Bieżący sklep; widoczne tylko w multistore | Przypiszcie plik produktowy do jednego sklepu. Jego adres katalogu działa tylko dla tego sklepu. |
| **Remember settings** | Yes | Zapisuje wybory z formularza jako wartości początkowe następnego nowego pliku produktowego. Ustawcie **No**, jeśli wybory z tego pliku nie powinny stać się zapamiętanymi wartościami domyślnymi. |
| **Type of file module will generate** | CSV | Wybierzcie **CSV** dla tekstowego pliku produktowego lub **XML** dla pliku zakupowego Atom. Aby uzyskać TSV, wybierzcie **CSV** i ustawcie **Delimiter** na `Tab`; TSV jest wynikiem CSV z tabulatorem jako separatorem. |
| **What you want to export?** | Products | Wybierzcie **Products**, aby wyeksportować jeden wiersz na produkt, albo **All products variants**, aby eksportować kombinacje oddzielnie. |
| **Save to file** | No | **No** generuje dane na żywo i zwraca je przy każdym wywołaniu adresu katalogu. **Yes** powoduje, że adres generowania zapisuje plik statyczny; dodajcie ten poufny adres do harmonogramu, a następnie przekażcie Microsoftowi osobny adres pliku katalogu. |
| **File name** | Puste | Gdy **Save to file** jest włączone, wpiszcie nazwę bazową statycznego pliku produktowego. Jeśli pole pozostanie puste, moduł użyje typu eksportu. Aby uzyskać przewidywalną nazwę, użyjcie liter, cyfr, łączników lub znaków podkreślenia. |
| **How to identify product?** | `id_product` | Wybierzcie `id_product`, `id_combination` lub `id_product-id_attribute`. Ta wartość staje się unikalnym identyfikatorem pozycji w pliku produktowym. Przy osobnym eksporcie wariantów użyjcie opcji uwzględniającej kombinacje. |

**Rozmiar, płeć, kolor i grupa wiekowa**

![Pola rozmiaru, płci, koloru i grupy wiekowej](https://mypresta.eu/docs/images/docs/mmcfeed-form-attributes.webp)

| Pole | Wartość początkowa | Działanie |
|---|---|---|
| **Export size** | No | Ustawcie **Yes**, aby dodać pole `size`. |
| **Size attribute** | None | Wybierzcie grupę atrybutów produktu zawierającą rozmiar. Przytrzymajcie Ctrl podczas klikania, aby wybrać kilka grup. Produkty bez wybranego rozmiaru użyją wartości **Default size value**. |
| **Default size value** | Puste | Wpiszcie zastępczy rozmiar używany, gdy produkt nie ma wartości w wybranej grupie atrybutów rozmiaru. |
| **Export gender** | No | Ustawcie **Yes**, aby dodać pole `gender`. |
| **Export gender value from** | No source selected | Wybierzcie **Attribute** lub **Feature** jako źródło danych o płci. Uzupełnijcie odpowiednie pole źródłowe poniżej. |
| **Gender feature** | No feature selected | Gdy źródłem jest **Feature**, wybierzcie cechę produktu przechowującą płeć. |
| **Gender attribute** | No attribute selected | Gdy źródłem jest **Attribute**, wybierzcie grupę atrybutów produktu przechowującą płeć. |
| **Default gender value** | Puste | Wybierzcie **Male**, **Female** lub **Unisex** jako wartość zastępczą, gdy produkt nie udostępnia płci przez wybrane źródło. |
| **Export color** | No | Ustawcie **Yes**, aby dodać pole `color`. |
| **Export color value from** | No source selected | Wybierzcie **Attribute** lub **Feature** jako źródło danych o kolorze. |
| **Color attribute** | No attribute selected | Gdy źródłem jest **Attribute**, wybierzcie grupę atrybutów produktu przechowującą kolor. |
| **Color feature** | No feature selected | Gdy źródłem jest **Feature**, wybierzcie cechę produktu przechowującą kolor. |
| **Default color value** | Puste | Wpiszcie wartość zastępczą używaną, gdy wybrane źródło koloru jest puste. Użyjcie angielskich nazw kolorów, ponieważ Microsoft akceptuje w tym polu nazwy angielskie. |
| **Export age_group** | No | Ustawcie **Yes**, aby dodać pole `age_group`. |
| **Export age group value from** | No source selected | Wybierzcie **Attribute** lub **Feature** jako źródło danych o grupie wiekowej. |
| **age group feature** | No feature selected | Gdy źródłem jest **Feature**, wybierzcie cechę produktu przechowującą grupę wiekową. |
| **age group attribute** | No attribute selected | Gdy źródłem jest **Attribute**, wybierzcie grupę atrybutów produktu przechowującą grupę wiekową. |
| **Default age group value** | No fallback selected | Wybierzcie wartość zastępczą używaną, gdy produkt nie ma wartości źródłowej: **adult**, **kids**, **toddler**, **infant** lub widoczną na ekranie wartość **newbord**. Przy przygotowywaniu danych produkcyjnych dopasujcie je do wartości grup wiekowych akceptowanych przez Microsoft. |

**Pola pliku produktowego, wysyłka, tekst, stany magazynowe, obrazy i ceny**

![Ustawienia pliku produktowego obejmujące identyfikatory, wysyłkę, opisy, język i separator](https://mypresta.eu/docs/images/docs/mmcfeed-form-feed-settings.webp)

| Pole | Wartość początkowa | Działanie |
|---|---|---|
| **Include item_group_id** | No | Ustawcie **Yes**, aby grupować warianty różniące się szczegółami takimi jak rozmiar, kolor, wzór, grupa wiekowa lub płeć. Dzięki temu Microsoft traktuje je jako warianty jednego produktu, a nie niezależne oferty. |
| **Unique product identifier** | Product UPC barcode | Wybierzcie pole produktu używane jako GTIN lub dane identyfikatora: **Product UPC barcode**, **Product ean13 / JAN barcode**, **Product reference number**, **Product MPN code**, **Product ISBN code** albo **Make this field empty, identifier_exists field will have value false then**. Jeśli identyfikatory nadane przez producenta są dostępne, należy je podać, ponieważ poprawiają dopasowanie produktów i jakość ofert. |
| **Include identifier_exists field** | No | Ustawcie **Yes**, aby dodać `identifier_exists`. Pole informuje Microsoft, czy pozycja ma unikalny identyfikator produktu. |
| **Include adult field** | Do not include | Wybierzcie **Include as true** dla produktów dla dorosłych objętych ograniczeniem wiekowym, **Include as false**, aby przesłać jednoznaczną wartość false, albo **- do not include -**, aby pominąć pole. Formularz wyświetla też niezwiązaną czwartą etykietę **Lowercase all letters, example: product name**; nie używajcie jej dla tego pola. |
| **Include shipping price** | Do not include | Wybierzcie **Do not include**, **Include (shipping price calculated for each item separately)** albo **Set shipping price manually**. Obliczanie automatyczne odbywa się osobno dla każdego produktu, a tryb ręczny stosuje jedną wpisaną kwotę. |
| **Include product's additional shipping cost** | No | Ustawcie **Yes**, aby do eksportowanego kosztu dostawy dodać dodatkową opłatę za wysyłkę przypisaną do produktu. |
| **Manual shipping value** | 0 | Po wybraniu wysyłki ręcznej wpiszcie kwotę wysyłki stosowaną do każdej pozycji. |
| **Automatic shipping price zone select** | Początkowa strefa sklepu | Po wybraniu wysyłki automatycznej wybierzcie strefę docelową używaną do obliczeń. Obliczanie osobno dla każdej pozycji zużywa więcej zasobów hostingu niż jedna ręcznie ustawiona kwota. |
| **Include weight** | No | Ustawcie **Yes**, aby dodać wagę wysyłkową produktu wraz z jednostką wagi używaną przez sklep. |
| **Product type** | No | Ustawcie **Yes**, aby dodać własną strukturę kategorii sklepu jako `product_type`. |
| **Product type - include category ID** | No | Gdy **Product type** jest włączone, ustawcie **Yes**, aby dołączyć identyfikator kategorii i rozróżnić kategorie o tej samej nazwie. |
| **Short description** | Short description | Wybierzcie, czy opis w pliku produktowym ma pochodzić z pola **Short description**, czy **Long description**. |
| **Remove html from descriptions** | Yes | Microsoft wymaga zwykłego tekstu. Znaczniki HTML i zakłócające podziały wierszy są usuwane z opisów nawet po wybraniu **No**, dlatego pozostawcie **Yes** jako zgodną ze skutkiem informację o wyniku. |
| **Product name** | Product name | Wybierzcie **Product name** lub **Meta title** jako źródło tytułu w pliku produktowym. |
| **Format name** | Do not format name | Pozostawcie bez zmian, zmieńcie tylko pierwszą literę na wielką, rozpocznijcie każde słowo wielką literą albo zamieńcie wszystkie litery na małe. Formatowanie przydaje się, gdy tytuły w katalogu są zapisane w całości wielkimi literami, czego Microsoft nie akceptuje. |
| **Remove selected characters from product name** | Puste | Wpiszcie każdy znak, który ma zostać usunięty z tytułów, na przykład `x=,` usuwa `x`, `=` i `,`. Aby niczego nie usuwać, pozostawcie pole całkowicie puste, bez spacji. |
| **Language** | Domyślny język sklepu | Wybierzcie język tytułów, opisów i pozostałych tłumaczonych danych katalogowych produktów. |
| **Delimiter** | `|` | Ustawcie separator danych CSV. Wpiszcie `Tab`, aby uzyskać format TSV zalecany przez Microsoft Merchant Center. W plikach CSV można też używać pionowej kreski lub przecinka. To ustawienie nie wpływa na XML. |
| **Wrap strings in double quotes** | Yes | Pozostawcie włączone, aby tekst zawierający separatory lub znaki specjalne nie uszkodził wierszy CSV. |
| **Information about stock** | Include real stock information | Użyjcie rzeczywistej dostępności albo wymuście dla wszystkich eksportowanych produktów wartość **in-stock**, **out-of-stock** lub **backorder**. Ostatnia opcja zgłasza produkty z włączonymi zamówieniami oczekującymi jako dostępne, a nie jako backorder. |
| **Availability date** | Puste | Wpiszcie zastępczą datę dla produktów dostępnych na zamówienie, które nie mają indywidualnej daty dostępności. Microsoft wymaga tej daty dla ofert backorder. |
| **Include quantity info** | No | Ustawcie **Yes**, aby dodać kolumnę zapasów zawierającą ilość produktu lub kombinacji. |
| **Default manufacturer value** | `Default` | Wpiszcie zastępczą markę używaną, gdy produkt nie ma przypisanego producenta. |
| **Image size for product pictures** | Początkowy typ obrazu zależny od sklepu | Wybierzcie typ obrazu PrestaShop używany do tworzenia adresów zdjęć produktów. |
| **Use default product picture if combination will not have associated photo** | No | Ustawcie **Yes**, aby użyć głównego zdjęcia produktu, gdy eksportowana kombinacja nie ma przypisanego obrazu. |
| **How many pictures you want to export?** | Export cover only | Wybierzcie **Export cover only** lub **Export all pictures**. Eksport wszystkich zdjęć dodaje kolejne odnośniki do obrazów. |
| **Currency** | Domyślna waluta sklepu | Wybierzcie walutę eksportowanych cen. Powinna odpowiadać rynkowi docelowemu katalogu w Microsoft Merchant Center. |
| **Price tax included or excluded** | Price Tax Included | Wybierzcie, czy ceny zwykłe i promocyjne mają zawierać podatek, czy go nie uwzględniać. |
| **Include specific prices** | Yes | Pozostawcie włączone, jeśli ceny specyficzne PrestaShop określają ceny dla walut lub innych kontekstów, które powinny znaleźć się w pliku produktowym. |
| **Export prices for selected group** | Grupa niezidentyfikowanych klientów sklepu | Wybierzcie grupę klientów, której kontekst cenowy ma być używany przez moduł. |
| **Export also unit price** | No | Ustawcie **Yes**, aby w plikach wariantów dodać dostępne informacje o jednostkowej mierze ceny. |
| **Export prices for selected country** | Domyślny kraj sklepu | Wybierzcie kontekst kraju używany do obliczania podatków i rabatów zależnych od kraju. |

**Wybór produktów, wykluczenia, limity, lokalne stany magazynowe i parowanie kategorii**

![Filtry, limity, kod sklepu i Microsoft Categories](https://mypresta.eu/docs/images/docs/mmcfeed-form-filters.webp)

| Pole | Wartość początkowa | Działanie |
|---|---|---|
| **Product Manufacturer** | All | Eksportujcie produkty wszystkich producentów lub tylko wybranego producenta. |
| **Product Supplier** | All | Eksportujcie produkty wszystkich dostawców lub tylko wybranego dostawcy. |
| **Product Category** | All | Eksportujcie wszystkie kategorie lub ograniczcie plik produktowy do wybranej kategorii. |
| **Exclude categories** | Puste | Wyszukajcie kategorie i dodajcie je do listy wykluczeń. Produkty przypisane do wybranej wykluczonej kategorii zostaną pominięte. |
| **Exclude products without pictures** | No | Ustawcie **Yes**, aby pomijać produkty bez użytecznego obrazu. |
| **Products's availability** | Export all products | Wybierzcie **Export only active products**, aby pominąć wyłączone produkty katalogowe. |
| **Products's stock** | Export all products | Wybierzcie **Export only in-stock products**, aby pominąć produkty bez zapasu. |
| **Exclude products with specific reference** | No | Ustawcie **Yes**, aby włączyć filtrowanie według prefiksu numeru referencyjnego. |
| **Exclude product where reference starts with:** | Puste | Wpiszcie prefiks, który ma powodować pominięcie produktu. Dotyczy to produktów i kombinacji, których numery referencyjne zaczynają się od tego tekstu. |
| **Exclude products worth less than defined value** | No | Ustawcie **Yes**, aby pomijać produkty poniżej minimalnej wartości wyrażonej w domyślnej walucie sklepu. |
| **Value of products (worth less) to exclude** | Puste | Wpiszcie minimalną wartość używaną przez poprzedni filtr. Produkty o niższej cenie zostaną pominięte. |
| **Exclude products** | Pusta lista | Zacznijcie wpisywać nazwę produktu i wybierzcie go, aby dodać go do listy wykluczeń. Użyjcie **Add all search results**, aby wykluczyć wszystkie wyniki bieżącego wyszukiwania; produkt można usunąć z listy jego przyciskiem usuwania. |
| **Limit number of products in feed** | 0 | Wpiszcie maksymalną liczbę produktów w tym pliku produktowym. Pozostawcie pole puste lub wpiszcie `0`, aby nie stosować limitu. Limit jest przydatny, gdy duży katalog przekracza dostępny czas wykonywania lub pamięć. |
| **Part of feed** | 0 | Wpiszcie `0`, jeśli plik produktowy nie jest dzielony. W przypadku plików dzielonych utwórzcie osobne konfiguracje z takim samym limitem i kolejnymi numerami części. Dla 3000 produktów i limitu 1000 użyjcie części 1, 2 i 3. |
| **Include store code to feed** | No | Ustawcie **Yes** dla pliku lokalnych stanów magazynowych, który musi identyfikować sklep stacjonarny. Użyjcie tego samego identyfikatora, który skonfigurowano na koncie biznesowym Microsoft. |
| **Store code** | Puste | Wpiszcie dokładny, rozróżniający wielkość liter alfanumeryczny identyfikator sklepu używany przez Microsoft. |
| **Microsoft Categories** | Synchronizacja taksonomii nie jest gwarantowana | Sprawdźcie stan pliku dla każdego języka. Kliknijcie **Synchronize** albo wybierzcie źródło w **Synchronize specific**, jeśli zwykłe źródło nie obsługuje danego języka. Następnie kliknijcie **Pair categories**, wyszukajcie odpowiednią kategorię Microsoft obok każdej kategorii sklepu i zapiszcie powiązanie. Ikona powtarzania stosuje jedną wartość kategorii do wszystkich pól, a ikona usuwania usuwa powiązanie. |

## 4. Front office i adresy plików produktowych

Moduł nie dodaje bloku, przycisku, treści na stronie produktu, formularza klienta, strony konta ani żadnego innego elementu interfejsu sklepu. Klienci nie korzystają z niego bezpośrednio.

Usługi zewnętrzne używają adresu katalogu skopiowanego z sekcji **Feeds**:

- **Live catalog URL** ponownie generuje i zwraca katalog przy każdym żądaniu. Żadne dane nie są zapisywane jako plik statyczny.
- **Generate / cron URL** zawiera poufny klucz wymagany do zapisania pliku statycznego. Wywołujcie go z harmonogramu lub za pomocą **Generate**. Nie przekazujcie go do Microsoft Merchant Center.
- **Catalog file URL** prowadzi do statycznego pliku utworzonego przez adres generowania. Gdy **Save to file** jest włączone, użyjcie tego adresu jako źródła danych w Microsoft Merchant Center.

Otwarcie niedostępnego adresu może wyświetlić:

| Wyświetlany komunikat | Zalecane działanie |
|---|---|
| **Feed is disabled** | Otwórzcie **Feeds** i ustawcie stan pliku produktowego na **On** albo edytujcie go i ustawcie **Active** na **Yes**. |
| **feed does not exists** | Ponownie skopiujcie bieżący adres z sekcji **Feeds**. Zapisany plik produktowy został usunięty, adres jest niepełny lub zapisana konfiguracja jest nieprawidłowa. |
| **Feed is not available in this store** | Przełączcie się na sklep przypisany do pliku produktowego, edytujcie pole **Shop** i skopiujcie adres wygenerowany dla tego sklepu. |
| **Access denied** | W trybie plikowym użyjcie kompletnego adresu **Generate / cron URL** skopiowanego ze strony pliku produktowego. Nie usuwajcie ani nie zmieniajcie jego poufnej części. |

## 5. Problemy i rozwiązania

### 5.1 Plik produktowy zgłasza, że jest wyłączony

**Objaw:** Po otwarciu adresu wyświetla się **Feed is disabled**.

**Przyczyna:** Przełącznik stanu jest wyłączony lub **Active** ma wartość **No**.

**Działanie:** Otwórzcie **Catalog → Microsoft Merchant Feed → Feeds** i ustawcie plik produktowy na **On**. Jego dotychczasowy adres pozostanie prawidłowy.

### 5.2 Plik produktowy nie istnieje

**Objaw:** Po otwarciu adresu wyświetla się **feed does not exists**.

**Przyczyna:** Adres wskazuje usunięty plik produktowy, jest niepełny albo zapisana konfiguracja nie nadaje się do użycia.

**Działanie:** Otwórzcie **Feeds** i ponownie skopiujcie adres. Jeśli pliku produktowego nie ma, utwórzcie go i zapiszcie ponownie.

### 5.3 Plik produktowy należy do innego sklepu

**Objaw:** Na liście widnieje **Not available in this store** albo pod adresem wyświetla się **Feed is not available in this store**.

**Przyczyna:** W trybie multistore plik produktowy jest przypisany do innego sklepu.

**Działanie:** Przełączcie panel administracyjny na przypisany sklep albo edytujcie **Shop**, zapiszcie zmiany i skopiujcie nowy adres.

### 5.4 Generowanie w trybie plikowym zgłasza odmowę dostępu

**Objaw:** Wywołanie generatora pliku wyświetla **Access denied**, a plik nie jest aktualizowany.

**Przyczyna:** W adresie brakuje poufnej autoryzacji zapisu dodawanej przez moduł.

**Działanie:** Ponownie skopiujcie **Generate / cron URL** z sekcji **Feeds** lub strony edycji i użyjcie go w harmonogramie bez żadnych zmian. Zachowajcie ten adres w poufności.

### 5.5 Microsoft otrzymuje odpowiedź generatora zamiast stałego pliku

**Objaw:** Zaplanowane pobieranie przez Microsoft kończy się niepowodzeniem albo nieoczekiwanie uruchamia generowanie przy każdym żądaniu, mimo że **Save to file** jest włączone.

**Przyczyna:** Do Microsoft Merchant Center wklejono adres **Generate / cron URL**.

**Działanie:** Adresu generowania używajcie wyłącznie w harmonogramie. Uruchomcie go raz, sprawdźcie obecność stanu **On disk** w sekcji **Dashboard** i wklejcie **Catalog file URL** do Microsoft Merchant Center.

### 5.6 Plik produktowy jest pusty lub brakuje w nim produktów

**Objaw:** Generowanie kończy się powodzeniem, ale nie zwraca żadnych pozycji lub zwraca ich mniej, niż oczekiwano.

**Przyczyna:** Produkty są usuwane przez ustawienia producenta, dostawcy, kategorii, wykluczonych kategorii, wykluczonych produktów, obrazów, aktywnego stanu, zapasów, prefiksu numeru referencyjnego, minimalnej wartości, limitu lub części.

**Działanie:** Edytujcie plik produktowy i sprawdźcie wszystkie pola wyboru oraz wykluczania produktów. Tymczasowo wybierzcie **All**, wyłączcie przełączniki wykluczeń, wyczyśćcie listy wykluczeń i ustawcie limit oraz część na `0`. Zapiszcie i ponownie wygenerujcie plik, a następnie przywracajcie filtry pojedynczo.

### 5.7 Brakuje kategorii Microsoft

**Objaw:** Plik produktowy nie zawiera przydatnych wartości kategorii Microsoft albo funkcja **Pair categories** nie może przeszukiwać taksonomii.

**Przyczyna:** Taksonomia dla wybranego języka nie została zsynchronizowana albo kategorie sklepu nie zostały powiązane.

**Działanie:** Edytujcie plik produktowy, przewińcie do **Microsoft Categories** i kliknijcie **Synchronize** dla danego języka. Jeśli to źródło jest niedostępne, wybierzcie inne w **Synchronize specific**. Gdy plik zostanie oznaczony jako dostępny, kliknijcie **Pair categories** i uzupełnijcie powiązania.

### 5.8 Duży katalog przekracza czas lub pamięć

**Objaw:** Generowanie zatrzymuje się, trwa zbyt długo albo zapisany plik nie jest aktualizowany.

**Przyczyna:** Hosting nie może przetworzyć w jednym uruchomieniu całego katalogu, kontekstu cen, obrazów i automatycznych obliczeń wysyłki.

**Działanie:** Wpiszcie odpowiednią wartość **Limit number of products in feed** i utwórzcie osobne pliki produktowe z kolejnymi wartościami **Part of feed**. Jeśli jest to właściwe, zamiast automatycznego obliczania wysyłki dla każdej pozycji użyjcie jednej ręcznie ustawionej kwoty, a poszczególne części uruchamiajcie oddzielnie.

### 5.9 Microsoft zgłasza problemy z jakością danych

**Objaw:** Microsoft Merchant Center wyświetla ostrzeżenia dotyczące identyfikatorów, opisów, cen, dostępności, obrazów, wariantów, grup wiekowych, płci, kolorów lub wysyłki.

**Przyczyna:** Wybrane pola źródłowe są puste, zawierają nieobsługiwaną wartość albo nie odpowiadają rynkowi katalogu Microsoft.

**Działanie:** Otwórzcie odpowiedni plik produktowy i dopasujcie **Language**, **Currency**, kraj oraz kontekst podatkowy do katalogu Microsoft. Podajcie prawidłowe dane GTIN, zastępczą markę, opisy w zwykłym tekście, bieżącą dostępność, odpowiednie obrazy i powiązania kategorii. W przypadku odzieży sprawdźcie **size**, **gender**, **color**, **age_group** i **item_group_id**. Ponownie wygenerujcie plik produktowy i jeszcze raz sprawdźcie diagnostykę w Microsoft Merchant Center.

## 6. Informacje dla programistów

### 6.1 Przegląd modułu

| Element | Wartość |
|---|---|
| Nazwa techniczna | `mmcfeed` |
| Wersja | `1.1.0` |
| Nazwa wyświetlana | `Microsoft Merchant Center Feed` |
| Autor | `MyPresta.eu` |
| Karta modułu | `administration` |
| Karta panelu administracyjnego | `AdminExportProductsFeedMicrosoft`, zainstalowana pod `AdminCatalog` |
| Endpoint front office | `controllers/front/feed.php` |

`mmcfeed` rozszerza klasę `Module`. Definicje plików produktowych są przechowywane przez ObjectModel `mmc` jako nazwa, sklep, flaga aktywności i serializowana konfiguracja w postaci ciągu zapytania. Zarówno natychmiastowe pobieranie z panelu administracyjnego, jak i wywołania kontrolera frontowego tworzą dane CSV lub XML z danych produktów PrestaShop. Tryb plikowy zapisuje oczyszczoną nazwę pliku w katalogu modułu, natomiast tryb na żywo strumieniuje odpowiedź.

### 6.2 Ważne pliki i klasy

| Plik | Odpowiedzialność |
|---|---|
| `mmcfeed.php` | Metadane modułu, instalacja i odinstalowanie, globalny formularz konfiguracji, funkcje pomocnicze oczyszczania danych, bezpieczne ścieżki plików i weryfikacja tokena zapisu HMAC. |
| `controllers/admin/AdminExportProductsFeedMicrosoft.php` | Dashboard, lista plików produktowych, formularz tworzenia i edycji, duplikowanie, usuwanie, synchronizacja i parowanie kategorii, natychmiastowe eksporty oraz zapisywanie domyślnych wartości formularza. |
| `controllers/front/feed.php` | Wczytuje zapisany plik produktowy, sprawdza aktywny stan i przynależność do sklepu, stosuje zapisane opcje, strumieniuje dane na żywo albo zapisuje plik statyczny. |
| `model/mmc.php` | ObjectModel `mmc`, migracja schematu, tworzenie adresów plików produktowych, uzupełnianie list, rejestrowanie uruchomień, statystyki panelu i metadane wygenerowanych plików. |
| `model/categorymap.php` | Definiuje ObjectModel `pixelgoogle` używany do mapowania kategorii. |
| `model/google.php` | Powiela tę samą definicję klasy `pixelgoogle` i metody co `model/categorymap.php`; wczytanie obu definicji w jednym żądaniu spowodowałoby ponowną deklarację klasy. |
| `lib/updateChecker.php` | `mmcfeedUpdate`, sprawdzanie aktualizacji, wspólne ustawienie powiadomień oraz formularz Updates. |
| `lib/searchTool/searchTool.php` | Autouzupełnianie produktów i kategorii używane przez pola wykluczeń. |
| `views/templates/admin/layout.tpl` | Nagłówek aplikacji, karty nawigacyjne, komunikaty i wspólne zasoby. |
| `views/templates/admin/feeds.tpl` | Karty plików produktowych, adresy, stany i działania wierszy. |
| `views/templates/admin/dashboard.tpl` | Wskaźniki KPI, wykres aktywności, ostatnie uruchomienia i wygenerowane pliki. |
| `views/templates/admin/form-chrome.tpl` | Nagłówek formularza i prezentacja adresów trybu na żywo oraz plikowego. |
| `views/category_taxonomy.tpl` | Stan taksonomii oraz punkty wejścia synchronizacji i parowania. |
| `views/categories-fancybox.tpl` | Okno mapowania kategorii i opcjonalne ścieżki nadrzędne. |
| `views/exclude-products.tpl` | Autouzupełnianie wykluczeń produktów i lista wybranych produktów. |
| `views/js/admin-app.js` i `views/css/admin-app.css` | Interakcje i stylizacja aplikacji w panelu administracyjnym. |

### 6.3 Kontrolery i przepływ żądań

`AdminExportProductsFeedMicrosoftController` rozszerza `ModuleAdminController`. Widoki aplikacji są wybierane przez `mmcfeed_view`: `dashboard`, `feeds`, `updates` lub `form`. Kontroler obsługuje:

- `saveonly` do zapisywania pliku produktowego i powrotu do listy.
- `submitExport` do zapisywania i natychmiastowego pobierania danych wyjściowych.
- `updatemmc` z `id_mmc` do edycji.
- `duplicatemmc` i `deletemmc` do działań w wierszach.
- AJAX `toggleFeedActive`.
- Synchronizację taksonomii przez AJAX, mapowanie kategorii, autouzupełnianie, zapisywanie powiązań i usuwanie powiązań.

`mmcfeedfeedModuleFrontController` rozszerza `ModuleFrontController`. Przyjmuje identyfikator zapisanego pliku produktowego, wczytuje wyłącznie zapisane parametry, odrzuca brakujący lub wyłączony plik oraz plik należący do innego sklepu, a następnie wywołuje generowanie. W trybie plikowym wymaga również `mmcfeed_write_key`. Parametry debugowania i parametry eksportu otrzymane w żądaniu są usuwane lub ignorowane, dlatego wywołujący nie mogą nadpisać zapisanych ustawień.

Moduł zawiera zastępcze pliki `index.php`, ale nie ma drugiego funkcjonalnego kontrolera frontowego.

### 6.4 Hooki i cykl życia

Jedynym zarejestrowanym hookiem jest `actionAdminControllerSetMedia`. Dla `AdminExportProductsFeedMicrosoft` włącza wtyczki jQuery Fancybox i autocomplete. Metoda hooka nie generuje treści w front office.

Moduł nie definiuje własnych metod `enable()` ani `disable()`. Nie udostępnia też własnych hooków.

`install()` wywołuje instalator klasy nadrzędnej, rejestruje hook, tworzy kartę administracyjną, tworzy tabele i uzupełnia schemat. Nie czyści pamięci podręcznej. `uninstall()` usuwa kartę administracyjną i wywołuje `parent::uninstall()`; nie usuwa tabel modułu, wartości konfiguracji, wygenerowanych plików produktowych ani plików taksonomii.

### 6.5 Nadpisania

Moduł nie instaluje nadpisań klas ani kontrolerów PrestaShop.

### 6.6 Baza danych

Rzeczywisty prefiks tabel jest prefiksem bazy danych skonfigurowanym w sklepie.

| Tabela | Zawartość |
|---|---|
| `pixelgoogle` | Rekordy mapowania kategorii: klucz główny `id_pixelgoogle`, starszy klucz `id_google`, identyfikator PrestaShop `id_category`, `id_lang` i zmapowana wartość taksonomii `value`. |
| `mmc` | Zapisane pliki produktowe: klucz główny `id_mmc`, `name`, właściciel `id_shop`, serializowane `conf` i `active`. Kontrola schematu dodaje `active` oraz `id_shop` do starszych instalacji i przypisuje starsze pliki produktowe do sklepu domyślnego. |
| `mmc_log` | Historia generowania: identyfikator pliku produktowego, znacznik czasu, czas trwania, liczba pozycji, stan, flaga trybu plikowego, nazwa pliku, format i źródło. Wpisy starsze niż 90 dni są usuwane podczas rejestrowania uruchomienia. |

Odinstalowanie zachowuje wszystkie trzy tabele. Zachowuje także rekordy plików produktowych, mapowania i historię uruchomień.

### 6.7 Klucze konfiguracji i wartości domyślne

Klucze globalne i klucze mechanizmu aktualizacji:

| Klucz | Wartość domyślna lub działanie |
|---|---|
| `mmc_pf_tree` | Brakująca wartość działa jak `0`; steruje ścieżkami nadrzędnymi w mapowaniu kategorii. |
| `mypresta_updates` | Wspólne ustawienie aktualizacji MyPresta; brakująca wartość jest traktowana jako wyłączenie okresowego sprawdzania. |
| `update_mmcfeed` | Znacznik czasu ostatniego sprawdzenia aktualizacji; zapisywany podczas sprawdzania. |
| `updatev_mmcfeed` | Najnowsza wersja zwrócona przez usługę aktualizacji. |

Gdy **Remember settings** jest włączone, domyślne wartości formularza są zapisywane z prefiksem `mmc_`. Klucze i wartości zastępcze w kodzie:

| Klucze | Wartości zastępcze |
|---|---|
| `mmc_export_igid`, `mmc_export_active`, `mmc_export_instock`, `mmc_export_product_type`, `mmc_export_product_type_id`, `mmc_export_product_weight`, `mmc_export_shipping_info`, `mmc_export_unit_price`, `mmc_export_save_file`, `mmc_export_nophoto_exclude`, `mmc_export_adult`, `mmc_export_color`, `mmc_export_gender`, `mmc_export_age_group`, `mmc_export_size`, `mmc_export_storecode`, `mmc_export_mainpicture`, `mmc_export_inventory`, `mmc_export_ie` | `0` lub false. |
| `mmc_export_additional_sc`, `mmc_export_exworthless` | False. |
| `mmc_remember_settings`, `mmc_export_specific`, `mmc_export_enclosure`, `mmc_export_removehtml` | `1` lub true. |
| `mmc_export_file_format` | `csv`. |
| `mmc_export_type` | Starsza wartość zastępcza `product`, normalizowana do `products` podczas generowania. |
| `mmc_export_identification` | `id_product`. |
| `mmc_export_gtin` | `upc`. |
| `mmc_export_product_name` | `name`. |
| `mmc_export_product_name_format`, `mmc_export_instock_info`, `mmc_export_what_pictures` | `0`. |
| `mmc_export_short_description_what` | `short`. |
| `mmc_export_delimiter` | `|`. |
| `mmc_export_tax` | `price_tin`. |
| `mmc_export_manufacturers_default` | `Default`. |
| `mmc_export_language`, `mmc_export_currency`, `mmc_export_country_prices`, `mmc_export_group_prices` | Odpowiednie wartości domyślne sklepu. |
| `mmc_export_category`, `mmc_export_manufacturers`, `mmc_export_suppliers` | Starsza wartość zastępcza `all`; widoczny selektor używa opcji **All**. |
| `mmc_export_shipping_info_price`, `mmc_limit_limit`, `mmc_limit_page` | `0`. |
| `mmc_export_shipping_id_zone` | `1`. |
| `mmc_export_filename`, `mmc_export_remove_char_product_name`, `mmc_export_exclude`, `mmc_export_exclude_categories`, `mmc_export_color_type`, `mmc_export_color_default`, `mmc_export_gender_default`, `mmc_export_size_default`, `mmc_export_availability_date`, `mmc_export_exreference`, `mmc_export_exreference_value`, `mmc_export_sc`, `mmc_export_exworthless_value` | Pusty ciąg. |
| `mmc_export_color_attribute`, `mmc_export_color_feature`, `mmc_export_gender_type`, `mmc_export_gender_feature`, `mmc_export_gender_attribute`, `mmc_export_age_group_type`, `mmc_export_age_group_feature`, `mmc_export_age_group_attribute`, `mmc_export_age_group_default` | `0`. |
| `mmc_export_size_attribute` | Identyfikatory rozdzielone przecinkami; domyślnie puste. |
| `mmc_mmcfeed_products` | Identyfikatory wykluczonych produktów rozdzielone przecinkami; domyślnie puste. |

Pętla zapamiętanych ustawień odczytuje również `delete_images` jako `mmc_delete_images`, chociaż ta wersja nie ma dla niego widocznego pola. Odinstalowanie nie usuwa żadnego z tych kluczy.

### 6.8 Wygenerowane pliki, taksonomia, bezpieczeństwo i rozszerzenia

Statyczne pliki produktowe są zapisywane jako `modules/mmcfeed/{sanitized-name}.{csv|xml|txt}`. Nazwy plików są ograniczane do liter, cyfr, łączników i znaków podkreślenia, a kontrola bezpiecznych ścieżek zapobiega wyjściu poza katalog modułu. Pliki taksonomii są przechowywane w `modules/mmcfeed/google/{language-code}.txt`. Żadna z tych grup nie jest usuwana podczas odinstalowania.

Token zapisu pliku to `hash_hmac('sha256', 'mmcfeed.write.' . $idShop, _COOKIE_KEY_)`. Pracownik panelu administracyjnego może zapisywać bezpośrednio; zewnętrzne wywołanie generowania pliku musi przekazać token, a porównanie używa `hash_equals`. Przed zastosowaniem zapisanej konfiguracji kontroler pliku produktowego odrzuca niezaufane parametry wejściowe `export_*`, `mmcfeed_*`, `mmc_*`, `pf_*`, limitu, debugowania i wykluczeń.

CSV używa `fputcsv`, znormalizowanego separatora i podwójnego cudzysłowu jako ogranicznika tekstu. W tekście pliku produktowego dekodowane są encje HTML, normalizowane są białe znaki, usuwane są podziały wierszy, tabulatory i kod HTML. XML używa `SimpleXMLElement`. Sprawdzanie aktualizacji korzysta z cURL, jeśli jest dostępne, a w przeciwnym razie z dostępu do plików obsługującego adresy URL.

Tłumaczenia używają `translations/{iso}.php`. Większość tekstów przechodzi przez wywołania tłumaczeń modułu; niektóre etykiety opcji, takie jak **All**, **Price Tax Included** i **Price Tax Excluded**, są dosłownie zapisane po angielsku. Opisy pól znajdują się bezpośrednio w tablicach HelperForm kontrolera administracyjnego, a opisy aktualizatora w `lib/updateChecker.php`.

Nie istnieje szablon front office, który można nadpisać w motywie. Szablony Smarty panelu administracyjnego można zmienić wyłącznie przez modyfikację lub rozszerzenie modułu. Bezpieczniejszą metodą dostosowania generowania plików produktowych jest utrzymywany fork modułu albo oddzielna integracja zamiast edytowania podstawowych plików PrestaShop; moduł nie udostępnia formalnego hooka rozszerzeń.

## 7. Pomoc

Strona produktu: [Microsoft Merchant Center Product Feed](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-feed.html)

Aby uzyskać pomoc, zalogujcie się na konto klienta w mypresta.eu, otwórzcie stronę kontaktową i wybierzcie **Support for paid modules**. Ten temat wymaga zalogowania; po zalogowaniu wybierzcie moduł z historii zakupów i opiszcie plik produktowy, sklep oraz dokładny wyświetlany komunikat.
