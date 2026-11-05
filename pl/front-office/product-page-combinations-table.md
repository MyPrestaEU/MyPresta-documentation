---
title: "Combinations Tab Pro - dokumentacja i instrukcja obsługi"
description: "Skonfiguruj macierz kombinacji, codzienne ustawienia strony produktu i rozwiąż typowe problemy na sklepie, jeśli już posiadasz Combinations Tab Pro."
sidebar:
  label: "Combinations Tab Pro - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product page combinations table na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-page-combinations-table/)
>
> ---


Zrzuty ekranu w tej instrukcji pochodzą z angielskiego panelu administracyjnego. Używaj tych samych nazw zakładek i pól poniżej, nawet jeśli język pracownika w sklepie jest inny.

## 1. Wymagania

Combinations Tab Pro pokazuje listę kombinacji lub macierz 2D na stronie produktu, dzięki czemu klienci mogą filtrować, sortować, ustawiać ilości i dodawać warianty do koszyka.

- PrestaShop: 1.7, 8 i 9
- PHP: wersja obsługiwana przez Twój sklep PrestaShop
- Rozszerzenia PHP używane przez moduł: JSON
- Inne moduły: żadne nie są wymagane. Opcjonalny **Product combination features** odblokowuje kolumny opisu kombinacji i cech kombinacji, gdy ten moduł jest zainstalowany w sklepie
- Poza sklepem: nic. Sprawdzanie aktualizacji kontaktuje się z MyPresta, gdy powiadomienia są włączone
- Duże katalogi: wiele kombinacji na produkt spowalnia stronę, jeśli zostawisz wszystkie kolumny oraz dodatki listy i siatki; użyj filtrów, paginacji albo presetu dopasowanego do katalogu

## 2. Instalacja

1. Prześlij ZIP modułu w **Modules** → **Module Manager**, następnie zainstaluj i włącz **Combinations Tab Pro**.
2. Otwórz konfigurację z listy modułów przez **Configure**. Nie ma osobnej pozycji w menu panelu do codziennej pracy; wszystkie ustawienia są na tej stronie konfiguracji.
3. Instalacja sama nie czyści cache PrestaShop. Wyczyść cache Smarty / motywu w **Advanced Parameters** → **Performance**, jeśli tabela nie pojawia się po instalacji.

**Po odinstalowaniu:** moduł znika z Module Manager. Tabele bazy wishlist, alertów o dostępności i profili override per encja są usuwane. Wartości konfiguracji zostają w bazie sklepu, więc późniejsza reinstalacja może przejąć poprzednie przełączniki, dopóki ich nie zmienisz. Nadpisania szablonów motywu dla plików modułu (jeśli je dodałeś) nie są usuwane przy odinstalowaniu.

## 3. Konfiguracja i praca w panelu

Otwórz **Modules** → **Module Manager** → **Combinations Tab Pro** → **Configure**. Strona ma górne zakładki: **Overview**, **Display**, **Cart**, **B2B**, **Visibility**, **Exclusions**, **Integrations**, **Overrides**, **Updates**. Wyszukiwanie produktów na **Visibility**, **Exclusions** i **Overrides** działa w tle (AJAX); ten moduł nie ma osobnego menu Orders.

### 3.1 Pełny przebieg

1. Sprzedawca konfiguruje pozycję, tryb widoku, kolumny lub komórki siatki, reguły koszyka, opcjonalne narzędzia B2B, widoczność, wykluczenia, integracje i override.
2. Klient otwiera produkt z kombinacjami, który przechodzi reguły widoczności.
3. Front pokazuje listę (jeden wiersz na kombinację) albo siatkę 2D (macierz, gdy produkt ma dwie grupy atrybutów i tryb widoku na to pozwala), w stopce produktu albo pod zakładką **Product variants**.
4. Klient może użyć filtrów atrybutów, sortować nagłówki listy, ustawiać ilości i dodawać jedną lub wiele pozycji do koszyka (w tym zbiorcze dodawanie).
5. Opcjonalne narzędzia: serce wishlist, powiadomienie o dostępności, wklejenie ilości CSV, eksport arkusza, uzupełnienie ostatniego zamówienia.
6. Checkout przebiega jak zwykłe zamówienie PrestaShop. Moduł nie używa statusów w stylu ofert; sukces to widoczna tabela, uzupełnione ilości i koszyk z wybranymi kombinacjami.

### 3.2 Overview & presets

![Overview and presets — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overview.webp)

**Overview & presets** to zakładka startowa. Gotowe zestawy włączają lub wyłączają wiele przełączników naraz. Użyj **Preview**, aby zobaczyć planowane wartości, potem **Apply**. Potwierdzenie: *Preset applied. Review Display & Columns and Cart & prices if you want to fine-tune.* Następnie otwórz **Display** i **Cart**, aby dopracować szczegóły.

Główne presety według nazwy:

| Preset | Tag | Co przygotowuje |
|---|---|---|
| **Fashion** | B2C | Zdjęcia, filtry, swatche kolorów, wishlist, karty mobilne dla odzieży z wieloma rozmiarami i kolorami |
| **B2B Wholesale** | B2B | Macierz z SKU na pierwszym planie, zbiorcze dodawanie do koszyka, import CSV, eksport, rabaty ilościowe |
| **Minimal** | Simple | Tylko nazwa kombinacji, cena i dodaj do koszyka |
| **Replace buy block** | UX | Ukrywa domyślny blok kupna PrestaShop, żeby klienci zamawiali z tabeli |
| **2D size × color** | Grid | Wymusza siatkę 2D z bogatą zawartością komórek, gdy produkty mają Color + Size |
| **Detailed list** | List | Pełna lista ze zdjęciami, SKU, EAN, stanem, sortowaniem, paginacją |
| **Electronics** | B2C | Referencja, EAN, cena jednostkowa, daty dostępności dla AGD i gadżetów |
| **Beauty & cosmetics** | B2C | Pole koloru + tekst, zdjęcia, wishlist i alerty o dostępności dla odcieni i zestawów |
| **Catalog only** | Display | Kombinacje bez zamawiania; ceny mogą zostać dla zalogowanych klientów |
| **Logged-in pricing** | B2B | Ceny i dodaj do koszyka tylko dla zalogowanych klientów |
| **Mobile first** | UX | Lista z kartami mobilnymi, +/- ilości, przyklejony zbiorczy Add to cart |
| **Restock & alerts** | Conversion | Wiersze braku stanu z datami i alertami o dostępności |
| **Luxury / lookbook** | B2C | Duże zdjęcia, zoom, ukryty dokładny stan, podkreślenie oszczędności |
| **Food & packaging** | Retail | Cena jednostkowa, waga, min. ilość, rabaty ilościowe |
| **Quick order sheet** | B2B | Siatka + zbiorcze dodawanie + CSV/eksport/ponowne zamówienie bez zdjęć |

### 3.3 Display — Placement

![Display settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-display.webp)

Podzakładka **Placement**. Pozycja na stronie i obramowanie wokół tabeli (lista i siatka 2D). Zapis pokazuje *Display settings saved.*

| Pole | Na start | Co robi |
|---|---|---|
| **Position on the product page** | Product footer (below product content) | Wybiera, gdzie klienci widzą tabelę kombinacji. Użyj **Product footer** poniżej produktu albo **Product tabs section** dla zakładki w stylu **Product variants**. Wybierz miejsce pasujące do motywu — zły wybór może ukryć tabelę albo umieścić ją zbyt nisko. |
| **Tab style (legacy themes)** | Classic tabs (PS 1.5 style) | Ma znaczenie tylko przy pozycji Product tabs na starszych motywach. Zostaw domyślną wartość, chyba że motyw nadal używa zakładek w stylu PrestaShop 1.5. Zmienia sposób wstrzyknięcia tytułu zakładki; nowoczesne motywy 1.7/8/9 zwykle to ignorują. Opcje: Classic tabs (PS 1.5 style) lub Accordion bars (PS 1.6 style). |
| **Custom HTML above the table** | Empty | Wolna treść (uwaga o wysyłce, link do tabeli rozmiarów i podobne) nad macierzą. Opcjonalnie per język. Widoczne nad listą i siatką 2D. |
| **Hide default PrestaShop buy block** | No | Ukrywa klasyczne listy atrybutów i dodaj do koszyka na stronie produktu. Ustaw **Yes**, gdy tabela ma być jedynym sposobem zakupu. Czyściej; upewnij się, że sama tabela pozwala dodać do koszyka. |
| **Hide default buy block only when table has combinations** | No | Zostawia zwykły blok kupna przy produktach prostych; ukrywa go, gdy pokazywana jest macierz. **Yes** jest zwykle najbezpieczniejsze, żeby proste produkty działały normalnie. |
| **Also hide default buy block based on product restrictions** | No | Zaawansowane sparowanie z regułami Visibility. Zostaw **No**, chyba że używasz złożonych list show/hide produktów. Może ukryć natywny blok kupna na wybranych produktach nawet bez tabeli. |

### 3.4 Display — View mode

| Pole | Na start | Co robi |
|---|---|---|
| **View mode** | List (classic table — one row per combination) | Wybiera tabelę listy albo macierz 2D. **List** = zawsze wiersze; **2D grid** = wymuś macierz gdy to możliwe; **Auto** = macierz przy 2 grupach atrybutów, lista w pozostałych przypadkach. Sklepy fashion/B2B z Color+Size pasują do Grid/Auto; produkty z jednym atrybutem zostają jako lista. |
| **Click combination to open that variant** | Off | Klik wiersza/komórki otwiera URL produktu dla tej kombinacji. Ustaw **Yes**, jeśli chcesz przeglądać warianty z tabeli. Przydatne ze zdjęciami; wyłącz, jeśli klik ma tylko zmieniać ilość. |

### 3.5 Display — Filters

Te reguły dotyczą zarówno tabeli listy, jak i siatki 2D.

| Pole | Na start | Co robi |
|---|---|---|
| **Attribute filters above the table / grid** | Off | Pokazuje klikalne chipy (np. Red, XL) do filtrowania wierszy/kolumn. Ustaw **Yes** przy produktach z wieloma kombinacjami. Klienci zawężają listę i macierz bez nieskończonego przewijania. |
| **Hide out-of-stock combinations** | Off | Usuwa niedostępne kombinacje z listy i siatki 2D. Ustaw **Yes**, aby sprzedawać tylko dostępne warianty. Krótsza tabela/macierz; klienci nie widzą brakujących rozmiarów. |
| **Hide combinations with price = 0** | Off | Ukrywa darmowe/zerowe warianty z listy i siatki. Ustaw **Yes**, jeśli zero oznacza „nie na sprzedaż”. Macierze mogą wyglądać niekompletnie, jeśli niektóre komórki są celowo 0. |
| **Show only combinations that have a picture** | Off | Ukrywa kombinacje bez zdjęć na liście i w siatce. Ustaw **Yes** do lookbooków; **No**, jeśli każdy SKU musi być zamawialny. Niepełne katalogi wyglądają lepiej, ale część wariantów znika. |
| **Multistore: disabled attribute values** | Hide the whole combination | Gdy wartość atrybutu jest wyłączona dla bieżącego sklepu. Tylko multistore — wybierz ukrycie kombinacji, pokazanie jako „-” albo ignorowanie. Działa przed zbudowaniem listy i siatki; sklepy single-shop mogą zostawić domyślną wartość. |

### 3.6 Display — Stock format

Jak ilości stanu są pokazywane na liście i w siatce, gdy stan jest widoczny. Widoczność kolumn/komórek jest w List columns lub Grid cells.

| Pole | Na start | Co robi |
|---|---|---|
| **Show negative stock as zero** | Off | Pokazuje 0 zamiast liczb ujemnych. Ustaw **Yes**, jeśli stan może zejść poniżej zera. Czytelniejsze liczby stanu na liście i w siatce. |
| **Hide exact stock above a threshold** | Off | Pokazuje np. „20+” zamiast prawdziwej liczby. Ustaw **Yes** i ustaw próg. Ukrywa duże stany magazynowe przed konkurencją na liście i w siatce. |
| **Stock threshold (show as X+)** | Empty | Gdy ukrywanie dokładnego stanu jest **Yes**, ilości powyżej tego limitu pokazują się jako „N+”. Przykład: 20 sprawia, że stan 45 wygląda jak „20+”. |

### 3.7 Display — Grid axes, images, cells

Siatka 2D to macierz w stylu size×color. Działa, gdy produkt ma dokładnie dwie grupy atrybutów, a View mode to **Grid** lub **Auto**. Złe sparowanie osi (ta sama grupa dwa razy) psuje siatkę i wraca do listy.

**Grid axes**

| Pole | Na start | Co robi |
|---|---|---|
| **Grid rows = attribute group** | -- automatic -- | Który atrybut staje się lewą stroną macierzy (np. Color). Wybierz grupę albo zostaw Automatic (pierwsza grupa atrybutów według pozycji). Zła para psuje siatkę i wraca do listy. |
| **Grid columns = attribute group** | -- automatic -- | Który atrybut staje się górą macierzy (np. Size). Wybierz inną grupę niż wiersze albo Automatic. Każda komórka to jedna kombinacja, w której klienci wpisują ilość. |

**Grid images** (tylko siatka 2D)

| Pole | Na start | Co robi |
|---|---|---|
| **Show image in cells** | Off | Miniatura w każdej komórce macierzy. Ustaw **Yes** dla macierzy fashion color×size. Gęstsze komórki; używa zdjęcia kombinacji albo okładki poniżej. |
| **Use product cover when combination has no image** | Yes | Pokazuje główne zdjęcie produktu jako fallback w komórkach siatki. Ustaw **Yes**, aby nigdy nie pokazywać pustego obrazka w macierzy. Dotyczy tylko siatki 2D, nie listy. |
| **Grid thumbnail image type** | Empty (shop image types) | Rozmiar obrazu PrestaShop używany w komórkach siatki. Wybierz mały typ (np. cart / small_default). Tylko siatka 2D; lista używa List images → Thumbnail type. |

**Grid cells** — przeciągnij **Cell block order** (góra→dół), potem Save. Pojawiają się tylko włączone bloki. Wishlist/BIS nadal wymagają **Integrations**; dodaj do koszyka wymaga głównego przełącznika w **Cart**.

| Pole | Na start | Co robi |
|---|---|---|
| **Cell block order** | Default block order | Kolejność bloków w każdej komórce macierzy. Przeciągnij, potem Save. Pojawiają się tylko włączone bloki poniżej. Włączanie zdjęcia i rozmiar są w Grid images. |
| **Grid: show reference (SKU)** | Off | SKU pod treścią komórki. Ustaw **Yes** dla B2B, żeby kupujący rozpoznawali SKU bez otwierania produktu. |
| **Grid: show price** | Off | Cena w komórce (reguły VAT/rabatów według ustawień Cart). Ustaw **Yes** niemal w każdym sklepie, żeby klienci porównywali warianty ceną w macierzy. |
| **Grid: show unit price** | Off | Cena jednostkowa w komórce. Ustaw **Yes**, jeśli używasz cen jednostkowych. Zwarta linia pod główną ceną. |
| **Grid: show stock quantity** | Off | Dostępna ilość stanu w komórce. Ustaw **Yes** dla przejrzystości; ujawnia stan per rozmiar/kolor. |
| **Grid: show availability** | Off | Etykieta In stock / Out of stock w komórce. Ustaw **Yes**, gdy liczby stanu są ukryte. Czytelny status bez dokładnej ilości. |
| **Grid: show minimal quantity** | Off | Min. ilość zamówienia w komórce. Ustaw **Yes** dla paczek B2B; mniej błędnych ilości w koszyku. |
| **Grid: show savings badge** | Off | % oszczędności względem najdroższej kombinacji. Ustaw **Yes** dla konwersji; podkreśla tańsze rozmiary/kolory. |
| **Grid: quantity input** | Off | Pole ilości w każdej komórce (działa ze zbiorczym Add to cart). Ustaw **Yes** do zamawiania z macierzy, żeby klienci uzupełniali ilości per rozmiar. |
| **Grid: Add to cart button (when bulk ATC is off)** | Off | Przycisk dodawania per komórka, gdy Bulk add to cart jest wyłączone. Ustaw **Yes** do dodawania jednym kliknięciem bez bulk. Ignorowane, gdy bulk ATC jest włączone. |
| **Grid: wishlist heart** | Off | Przycisk serca w komórce. Najpierw włącz Wishlist w Integrations. Klienci zapisują rozmiar/kolor z macierzy. |
| **Grid: back-in-stock alert** | Off | Przycisk powiadomienia na komórkach bez stanu. Najpierw włącz Back in stock w Integrations. Zbiera popyt na brakujące rozmiary. |

### 3.8 Display — List layout, images, columns

Te ustawienia dotyczą tylko klasycznej listy (jeden wiersz na kombinację), nie komórek siatki 2D.

**List layout & sorting**

| Pole | Na start | Co robi |
|---|---|---|
| **Column order (list only)** | Default column order | Ustawia kolejność kolumn od lewej do prawej w widoku listy. Przeciągnij elementy, potem Save. Klienci widzą kolumny w tej kolejności (pojawiają się tylko włączone). |
| **Mobile card layout (list)** | Yes | Na telefonach zamienia szerokie wiersze tabeli w ułożone karty. Ustaw **Yes** dla lepszego UX mobilnego. Każda kombinacja wygląda jak mała karta; desktop zostaje zwykłą tabelą. |
| **Hide table header (list)** | Off | Usuwa górny wiersz z nazwami kolumn. Zwykle zostaw **No**. Czyściej, ale trudniej zrozumieć kolumny. |
| **Paginate long tables (list)** | Off | Dzieli wiele kombinacji na strony. Ustaw **Yes**, jeśli produkt ma dziesiątki wariantów. Szybsze wrażenie strony; ustaw Rows per page poniżej. |
| **Rows per page** | 10 when pagination is used without a custom value | Ile kombinacji na stronę przy włączonej paginacji. Przykład: 10 lub 20. Mniejsza liczba = krótsze strony, więcej kliknięć. |
| **Allow sorting by column headers** | Yes | Klikalne nagłówki do sortowania listy. Ustaw **Yes** przy długich listach. Klienci sortują po cenie, referencji itd. (tylko widok listy). |
| **Default sort by price** | Off | Początkowe sortowanie według ceny. Opcjonalne. Najtańsze/najdroższe pierwsze zależnie od kierunku. |
| **Default sort by attribute** | Off | Początkowe sortowanie według wybranej grupy atrybutów. Ustaw ID atrybutu i kierunek poniżej. Przykład: rozmiary S→XL. |
| **Attribute sort uses** | Attribute value position | Sortuj według pozycji atrybutu (kolejność katalogu) albo nazwy A→Z. Pozycja zwykle najlepiej pasuje do rozmiarów. Zmienia domyślną kolejność wierszy, gdy sortowanie po atrybucie jest włączone. |
| **Attribute group ID to sort by** | Empty | Numeryczne ID grupy atrybutów używane do domyślnego sortowania. W Catalog → Attributes otwórz grupę i odczytaj ID z URL. Złe ID = nieoczekiwana kolejność. |
| **Sort direction** | Ascending | Domyślna kolejność rosnąca lub malejąca. Ascending dla S→XL; Descending dla ceny od wysokiej do niskiej przy sortowaniu po cenie. Steruje pierwszymi wierszami, które widzi klient. |

**List images**

| Pole | Na start | Co robi |
|---|---|---|
| **Show image column** | Yes | Dodaje miniaturę dla każdej kombinacji. Ustaw **Yes**, gdy warianty mają różne zdjęcia, żeby klienci szybciej je rozpoznawali. |
| **Show image column only if at least one combination has a photo** | Off | Ukrywa pustą kolumnę obrazu, gdy żadna kombinacja nie ma zdjęcia. Ustaw **Yes**, aby uniknąć zbędnej pustej kolumny. Tabela zostaje czysta przy produktach bez zdjęć kombinacji. |
| **Use product cover when combination has no image** | Off | Pokazuje główne zdjęcie produktu jako fallback na liście. Ustaw **Yes**, aby nigdy nie pokazywać pustej komórki obrazu. Dotyczy tylko widoku listy, nie siatki 2D. |
| **Click image to zoom** | Off | Otwiera większe zdjęcie w lightboxie. Ustaw **Yes** dla produktów wizualnych; ustaw rozmiar zoom poniżej. Klienci oglądają detale bez opuszczania strony. |
| **Thumbnail image type** | Empty (shop image types) | Rozmiar obrazu PrestaShop używany w kolumnie listy. Wybierz mały typ (np. cart / small_default). Tylko lista; siatka używa Grid images → Thumbnail type. |
| **Zoom image type** | Empty (shop image types) | Rozmiar obrazu otwierany w lightboxie przy włączonym zoom. Wybierz duży typ (np. large_default). Ostrzejszy podgląd zoom w widoku listy. |

**List columns** — widoczność klasycznej listy. Opis / cechy kombinacji wymagają opcjonalnego modułu Combination features; w przeciwnym razie te kontrolki zostają zablokowane z linkiem do sklepu.

| Pole | Na start | Co robi |
|---|---|---|
| **How attributes are shown** | All attributes in one column | Jedna wspólna kolumna „Combination name” vs osobne kolumny per atrybut (Color, Size…). Osobne kolumny łatwiej skanować i sortować. Układ widoku listy zmienia się od razu. |
| **Include attribute label in the name** | Off | Pokazuje „Color: Red, Size: L” zamiast „Red, L”. Ustaw **Yes** dla jasności; dotyczy tylko metody jednej kolumny. Dłuższe, ale czytelniejsze nazwy. |
| **Color attribute display** | Text only | Jak wyglądają wartości koloru (swatch, tekst albo oba). Pole koloru do fashion; Text, jeśli kolory mają specjalne nazwy. Dotyczy tylko atrybutów typu „color”. |
| **Show combination / attribute columns** | Yes | Główny przełącznik kolumn nazw atrybutów. Prawie zawsze **Yes**. **No** ukrywa, czym warianty się różnią — tylko do bardzo specjalnych układów. |
| **Show combination description** | Off (locked without Combination features) | Pokazuje własny opis przypisany do kombinacji przez Combination features. Ustaw **Yes**, gdy warianty mają unikalny tekst. Dodatkowa kolumna listy; puste komórki pokazują „-”. |
| **Show combination features** | Off (locked without Combination features) | Pokazuje wartości cech przypisane do kombinacji przez Combination features. Ustaw **Yes**, gdy warianty mają własną kartę danych. Dodatkowa kolumna listy z nazwą cechy + wartościami. |
| **Show reference (SKU)** | Yes | Pokazuje referencję kombinacji. Ustaw **Yes** dla B2B / hurtu, żeby kupujący szybciej zamawiali po SKU. |
| **Show EAN** | No | Pokazuje kod EAN-13. Ustaw **Yes**, jeśli personel/klienci skanują kody. Dodatkowa kolumna; wyłącz dla B2C fashion, jeśli nieużywane. |
| **Show MPN** | No | Kolumna numeru części producenta. Ustaw **Yes**, gdy uzupełniasz MPN w katalogu. Puste komórki pokazują „-”, jeśli MPN jest puste. |
| **Show weight** | Off | Waga produktu + wpływ kombinacji. Ustaw **Yes** dla towarów wrażliwych na wysyłkę, żeby klienci szacowali koszt dostawy. |
| **Show stock quantity** | Yes | Dostępny stan per kombinacja. Ustaw **Yes** dla przejrzystości; sparuj ze Stock format dla „10+”. Buduje zaufanie; ujawnia stan. |
| **Show total product stock in header** | No | Dodaje sumę stanu obok nagłówka Quantity. Opcjonalny szybki przegląd łącznej dostępności. |
| **Show availability text** | Yes | „In stock” / „Out of stock” (albo etykiety sklepu). Ustaw **Yes** dla jasności, żeby klienci widzieli status bez czytania liczby. |
| **Show availability date when out of stock** | Yes | Drukuje datę dostępności kombinacji pod statusem braku stanu. Ustaw **Yes**, jeśli uzupełniasz daty dostępności. Ustawia oczekiwania przy restocku. |
| **Show minimal quantity** | Off | Pokazuje minimalną ilość zamówienia kombinacji. Ustaw **Yes** dla paczek B2B; mniej błędów add-to-cart. |
| **Show price** | Yes | Kolumna ceny per kombinacja (tylko lista). Ustaw **Yes** niemal w każdym sklepie. Klienci porównują warianty ceną. Siatka używa Grid cells → show price. |
| **Show unit price** | Off | Kolumna ceny jednostkowej (tylko lista). Ustaw **Yes**, jeśli używasz cen jednostkowych. Puste/dziwne wartości, jeśli unity nie jest ustawione na produkcie. |
| **Show savings column** | No | O ile tańsza jest kombinacja względem najdroższej (tylko lista). Ustaw **Yes** dla psychologii upsell. Dodatkowa kolumna z % i kwotą oszczędności. Siatka używa Grid cells → savings badge. |
| **Show volume (quantity) discounts column** | Off | Lista progów rabatu ilościowego per kombinacja (tylko lista). Ustaw **Yes** dla hurtu. Szersza tabela; świetne dla B2B. |
| **Hide volume discount rows that do not apply** | Off | Czyści puste listy rabatów w kolumnie listy. Ustaw **Yes**, aby zmniejszyć szum, żeby zostały tylko sensowne progi. |

### 3.9 Cart — Prices

![Cart settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-cart.webp)

Podzakładka **Prices**. Globalne reguły wyświetlania cen dla listy i siatki 2D. Zapis pokazuje *Cart & price settings saved.*

| Pole | Na start | Co robi |
|---|---|---|
| **Show prices only to logged-in customers** | No | Goście widzą prośbę o logowanie zamiast cen. Ustaw **Yes** dla ukrytych cen B2B. Goście muszą się zalogować, żeby zobaczyć kwoty na liście i w siatce. |
| **Tax display** | Tax included | Z podatkiem, bez podatku albo według ustawienia grupy klienta. Dopasuj do polityki cen sklepu. Zły wybór myli kupujących B2B i B2C. |
| **Show “tax incl./excl.” label next to price** | Off | Mały tekst po cenie. Ustaw **Yes** dla jasności prawnej w UE. Nieco bardziej zajęte komórki. |
| **Show discount % badge on reduced prices** | Off | Pokazuje -X%, gdy istnieje konkretna obniżka. Ustaw **Yes**, aby podkreślić promocje. Przyciąga uwagę do przecenionych kombinacji na liście i w siatce. |
| **Highlight the cheapest combination** | Yes | Oznacza wiersz/komórkę z najniższą ceną. Ustaw **Yes**, aby kierować impulsywne zakupy. Zielone podświetlenie najlepszej ceny na liście i w siatce. |

### 3.10 Cart — Add to cart

| Pole | Na start | Co robi |
|---|---|---|
| **Show add to cart controls** | Yes | Pole ilości i/lub przycisk per kombinacja. Ustaw **Yes**, aby sprzedawać z tabeli. **No** = macierz tylko do podglądu. |
| **Add to cart only for logged-in customers** | Off | Goście nie mogą dodawać z tabeli. Ustaw **Yes** dla B2B. Goście widzą komunikat zamiast przycisków. |
| **Show quantity input** | Yes | Edytowalne pole ilości. **Yes** zawsze zalecane. **No** ukrywa ilość (trudniej kupić wiele sztuk). |
| **Qty box also in the table header (fill all rows)** | Off | Jedna ilość w nagłówku kopiuje się do wszystkich wierszy. Opcjonalna wygoda. Przyspiesza zbiorcze uzupełnianie; używaj ostrożnie. |
| **Plus / minus buttons** | No | Przyciski +/- obok ilości. Ustaw **Yes** dla urządzeń dotykowych. Łatwiejsza zmiana ilości. |
| **Block qty higher than stock** | Off | Blokuje zamówienie powyżej dostępnego stanu (gdy zamówienia bez stanu nie są dozwolone). Ustaw **Yes**, aby uniknąć nadprzedaży. Przycisk + zatrzymuje się na stanie. |
| **AJAX add to cart** | Yes | Dodaje bez pełnego przeładowania strony. Ustaw **Yes** na nowoczesnych motywach. Płynniejszy UX; wyłącz tylko przy konflikcie motywu. |
| **Bulk add to cart (one button for many rows)** | Off | Klient uzupełnia kilka pól ilości, potem jeden **Add to cart** wysyła wszystkie. Ustaw **Yes** dla B2B/fashion. Domyślne przyciski per wiersz mogą być ukryte; na mobile pojawia się przyklejony pasek. |
| **Show live total price of selected quantities** | Off | Liczy sumę wybranych pozycji (respektuje rabaty ilościowe, gdy to możliwe). Ustaw **Yes** ze zbiorczym dodawaniem. Klienci widzą wartość koszyka przed kliknięciem Add. |
| **Tip: how many units until next quantity discount** | Yes | Pod paskiem bulk mówi klientowi „dodaj X więcej, aby odblokować kolejny rabat”. Ustaw **Yes**, jeśli używasz rabatów ilościowych. Zachęca do większych koszyków. |
| **Use Font Awesome cart icon** | Off | Ikona FA zamiast Material. Ustaw **Yes** tylko, jeśli motyw ładuje Font Awesome. Brak FA = zepsuta ikona. |

### 3.11 B2B Tools and Groups

![B2B tools — English back office](https://mypresta.eu/docs/images/docs/combinationstab-b2b.webp)

**Tools** — pomocniki hurtowe. Globalne przełączniki to domyślne wartości; użyj **Groups**, aby zezwolić lub zabronić per grupa klientów PrestaShop. Zapis pokazuje *B2B settings saved.*

| Pole | Na start | Co robi |
|---|---|---|
| **CSV quantity import on product page** | No | Kupujący wklejają linie jak SKU;5 (lub EAN;qty), aby uzupełnić ilości. Ustaw **Yes** dla hurtu; potem zezwól per grupa, jeśli potrzeba. Duża oszczędność czasu przy ponownych zamówieniach. |
| **Export order sheet (CSV / XLSX / PDF)** | No | Pobiera kombinacje z wpisanymi ilościami. Ustaw **Yes** dla kupujących, którzy wysyłają arkusze do księgowości. Przyciski pojawiają się obok zbiorczego dodawania. |
| **Fill last order button** | No | Przywraca ilości z ostatniego zbiorczego dodania / eksportu dla tego produktu. Ustaw **Yes** dla powtarzalnych zamówień hurtowych. Jedno kliknięcie uzupełnia macierz. |

**Groups** — dla każdej grupy klientów ustaw **Show table**, **Add to cart**, **CSV import**, **Export**, **Reorder** (Yes/No). Domyślnie, gdy nie ma własnej reguły: show table Yes, add to cart Yes, CSV/export/reorder według globalnych przełączników Tools (po instalacji wyłączone). Jeśli **Show table** jest No dla grupy odwiedzającego, macierz się nie pojawia. Jeśli **Add to cart** jest No, odwiedzający nie może dodać z tabeli nawet przy włączonych globalnych przełącznikach Cart.

### 3.12 Visibility

![Visibility — English back office](https://mypresta.eu/docs/images/docs/combinationstab-visibility.webp)

Kontroluj, na których produktach klienci widzą tabelę kombinacji. Szukaj produktów pickerem na ekranie (wyszukiwanie AJAX). Potwierdzenie: *Successfully updated*.

| Pole | Na start | Co robi |
|---|---|---|
| **Visibility rule** | Show on all products | Decyduje, czy tabela pojawia się na każdym produkcie, tylko na wybranych, albo wszędzie oprócz wybranych. Wybierz regułę, potem zaznacz kategorie / dodaj produkty w selektorze poniżej. „All products” jest najprostsze; użyj Include/Exclude, gdy macierz potrzebują tylko niektóre pozycje katalogu. |
| **Selected categories & products** | None | Lista kategorii i produktów używana przez regułę powyżej. Zaznacz kategorie i/lub wyszukaj produkty i kliknij Add. Używane tylko przy regule Include lub Exclude — ignorowane przy „all products”. |
| **Hide table when product has too few attribute groups** | Off | Ukrywa tabelę na produktach z tylko kilkoma grupami atrybutów (np. tylko Color, bez Size). Ustaw **Yes** i ustaw liczbę poniżej. Przykład: próg 1 ukrywa produkty z 1 lub mniej grupami atrybutów — przydatne, jeśli chcesz macierz tylko dla produktów Color+Size. |
| **Hide when attribute groups ≤** | Empty | Próg dla przełącznika powyżej. Wpisz 1, aby ukryć produkty z jednym atrybutem; 0 praktycznie nigdy nie ukrywa tą regułą. Porównywane z liczbą grup atrybutów na produkcie. |

### 3.13 Exclusions

Na stałe ukryj wybrane kombinacje z tabeli (wszystkie produkty). Wyszukaj produkt, wybierz kombinacje przez **Select**, potem **Save**. Potwierdzenie: *Settings saved*. Te warianty zostają w PrestaShop, ale nigdy nie pojawiają się w macierzy — przydatne dla przestarzałych rozmiarów lub wewnętrznych SKU. Wyszukiwanie produktu i kombinacji używa tego samego AJAX co Visibility.

| Pole | Na start | Co robi |
|---|---|---|
| **Search for product** | Empty | Znajdź produkt, którego kombinacje chcesz wykluczyć. |
| **Combination** | None selected | Oznacz kombinacje do ukrycia z macierzy na froncie, potem Save. |

### 3.14 Integrations

![Integrations — English back office](https://mypresta.eu/docs/images/docs/combinationstab-integrations.webp)

Zapis pokazuje *Integrations saved.* Formularz informuje o Advanced Stock Management, gdy je wykryje; bez ASM zostaw przełącznik magazynu Off.

| Pole | Na start | Co robi |
|---|---|---|
| **Combination wishlist** | No | Przycisk serca zapisuje wariant do lekkiej wishlist (konto lub cookie). Ustaw **Yes**, jeśli klienci oznaczają rozmiary. Link pojawia się w My Account; to nie pełny suite wishlist. |
| **Back-in-stock email alerts** | No | Wiersze bez stanu dostają przycisk powiadomienia; gdy stan wraca, moduł wysyła e-mail do klienta. Ustaw **Yes** i upewnij się, że sklep potrafi wysyłać maile. Odzyskuje popyt na brakujące rozmiary. |
| **Warehouse stock column** | No | Listuje ilości per magazyn, gdy Advanced Stock jest włączone. Ustaw **Yes** tylko z ASM. Bez ASM kolumna zostaje pusta — trzymaj Off. |

### 3.15 Overrides

![Overrides — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overrides.webp)

Profile kaskadują **Product → deepest Category → Manufacturer → Global**. Tylko nadpisane pola zmieniają warstwę niższą. Filtruj listę przez **All / Products / Categories / Manufacturers**. Twórz przez **Product override**, **Category override** lub **Manufacturer override**.

Na ekranie edycji: wyszukaj i wybierz encję, włącz tylko pola, które chcesz nadpisać, zostaw niezaznaczone do dziedziczenia. Użyj **Copy all from global**, aby zasiać wartości, potem **Save override**. Sukces: *Override profile saved.* Usuwanie pyta *Delete this override profile?* Sukces: *Override profile deleted.*

Typowe powody override: jedna marka zawsze potrzebuje trybu grid; jedna kategoria ukrywa ceny dla gości; jeden produkt potrzebuje dodatkowych kolumn SKU bez zmiany całego sklepu.

### 3.16 Updates

**Check now** pyta MyPresta, czy istnieje nowsza build. Komunikaty: *New version available!* lub *Module is up to date!*

| Pole | Na start | Co robi |
|---|---|---|
| **Check updates** | — | Uruchamia natychmiastowe sprawdzenie i pokazuje, czy istnieje nowa wersja. |
| **Updates notifications** | Select / as previously saved | Włącz tę opcję, jeśli chcesz automatycznie sprawdzać aktualizacje modułu na MyPresta.eu. Ta opcja wyświetli powiadomienie o nowych wersjach tego addonu. |
| **Module page** | Link on screen | Bezpośredni link do oficjalnej strony addonu, gdzie możesz przeczytać o zmianach w module (changelog). O pomoc proś w Support (rozdział 7). |

## 4. Front office

- **Placement:** stopka produktu poniżej treści produktu albo zakładka **Product variants** w obszarze zakładek produktu, zależnie od Display → Placement.
- **List vs 2D grid:** lista to jeden wiersz na kombinację. Siatka to macierz, gdy produkt ma dokładnie dwie grupy atrybutów, a View mode to Grid lub Auto; w przeciwnym razie front wraca do listy.
- **Filters:** chipy atrybutów nad tabelą/siatką, gdy włączone.
- **Sorting / pagination / mobile cards:** tylko lista, gdy te opcje Display są włączone.
- **Add to cart:** kontrolki per wiersz i/lub zbiorczy **Add to cart** z opcjonalną żywą sumą i tipem „jednostki do kolejnego rabatu”.
- **Toolbar:** gdy włączone — **Fill last order**, **Export** (CSV / XLSX / PDF), pole **Import quantities** z liniami jak `REF001;5`, potem **Apply**.
- **Wishlist:** serce na wierszach/komórkach, gdy Integrations + przełączniki kolumn/komórek na to pozwalają. Zalogowani klienci mają **My combination wishlist** na stronie konta klienta.
- **Back in stock:** kontrolka powiadomienia na liniach bez stanu; e-mail gdy stan wraca (mail sklepu musi działać).
- **Guest prices:** przy „ceny tylko dla zalogowanych” goście widzą prośbę o logowanie zamiast kwot; przy „ATC tylko dla zalogowanych” goście nie mogą dodawać z tabeli.

Osobny zrzut frontu nie jest tu wymagany; układ motywu decyduje o dokładnym wyglądzie wokół bloku modułu.

## 5. Typowe problemy

### 5.1 Tabela niewidoczna na stronie produktu

Sprawdź, czy moduł jest włączony, produkt ma kombinacje, reguła **Visibility** obejmuje produkt, grupa klienta ma **Show table** = Yes, a pozycja pasuje do motywu (footer vs tabs). Wyczyść cache. Potwierdź, że Exclusions nie ukryły wszystkich kombinacji.

### 5.2 Zła pozycja lub pusta zakładka

Zmień **Position on the product page**. Na nowoczesnych motywach zignoruj Tab style. Jeśli używasz zakładek, otwórz produkt i szukaj **Product variants**.

### 5.3 Oczekiwana siatka 2D, a widać listę

Siatka wymaga dokładnie dwóch grup atrybutów oraz View mode Grid lub Auto. Jeden atrybut albo trzy i więcej wymusza listę. Ta sama grupa atrybutów na obu osiach też wraca do listy — ustaw różne grupy wierszy i kolumn.

### 5.4 Domyślny blok kupna znika lub nadal jest widoczny

Przejrzyj **Hide default PrestaShop buy block** oraz **Hide default buy block only when table has combinations**. Jeśli natywny blok jest ukryty, a tabela nie ma dodawania do koszyka, klienci nie mogą kupić — włącz Cart → **Show add to cart controls**.

### 5.5 Zbiorcze dodawanie nic nie robi albo źle przeładowuje

Włącz **AJAX add to cart** na nowoczesnych motywach. Potwierdź, że **Bulk add to cart** jest Yes i ilości są uzupełnione. Reguła grupy **Add to cart** musi być Yes dla tej grupy klienta.

### 5.6 Reguły grup blokują dodawanie do koszyka lub ukrywają tabelę

W **B2B** → **Groups** ustaw **Show table** i **Add to cart** na Yes dla grupy odwiedzającego (Guest, Customer albo Twoja grupa hurtowa).

### 5.7 Ceny ukryte dla gości

Oczekiwane, gdy **Show prices only to logged-in customers** jest Yes. Wyłącz na Off dla cen publicznych albo poproś gości o logowanie.

### 5.8 Brak wishlist lub alertu o dostępności

Włącz je w **Integrations**, potem włącz odpowiadające przełączniki kolumn listy lub komórek siatki. Dla BIS potwierdź, że PrestaShop może wysyłać mail i że stan aktualizuje się przy restocku.

### 5.9 Kolumny opisu / cech kombinacji zablokowane

Zainstaluj i włącz opcjonalny moduł **Product combination features**. Do tego czasu te kolumny zostają zablokowane w Display i Overrides.

### 5.10 Brak CSV / eksportu / fill last order

Włącz narzędzia w **B2B** → **Tools** i ustaw Yes dla tej grupy klienta w **Groups**.

## 6. Przewodnik dla programistów

### 6.1 Przegląd

- Technical name: `combinationstab`
- Version: 3.0.5
- Display name: Combinations Tab Pro
- Author: mypresta.eu
- Module tab: `smart_shopping`
- Main class: `Combinationstab`
- BO UI: `CtpAdminBo` (`lib/CtpAdminBo.php`)
- Settings resolution: `CtpSettingsResolver` (Product → Category → Manufacturer → Global)
- Optional: `CtpCombfeat` — plik może nie istnieć; `class_exists('CtpCombfeat')` bramkuje opis/cechy kombinacji. Bez klasy te opcje zostają zablokowane.

Przepływ: Configuration / ustawienia encji → hooki FO renderują szablony listy lub siatki → kontrolery front obsługują AJAX koszyka, wishlist, BIS, CSV, eksport, reorder, kalkulator ceny.

### 6.2 Ważne pliki

| Path | Role |
|---|---|
| `combinationstab.php` | Klasa modułu, install/uninstall, hooki, formularze visibility/exclusions |
| `lib/CtpAdminBo.php` | Zakładki strony Configure i pola HelperForm |
| `lib/CtpColumnRegistry.php` | Kolumny listy, presety, order JSON |
| `lib/CtpGridRegistry.php` | Bloki komórek siatki i order JSON |
| `lib/CtpGrid2d.php` | Budowa macierzy 2D / `shouldUseGrid` |
| `lib/CtpCombinationsData.php` | Wiersze kombinacji dla FO |
| `lib/CtpGroupRules.php` | Per grupa show/atc/csv/export/reorder |
| `lib/CtpWishlist.php` / `CtpBackInStock.php` / `CtpExport.php` / `CtpReorder.php` | Pomocniki funkcji |
| `lib/CtpSettingsResolver.php` | Tabela override i kaskada |
| `views/templates/admin/tabs.tpl` | Chrome zakładek BO |
| `views/templates/hook/productfooter.tpl` / `productfooter_grid.tpl` | Lista / siatka FO |
| `views/templates/hook/_toolbar.tpl` | Pasek bulk / export / CSV |
| `controllers/front/*.php` | Endpointy front |
| `controllers/admin/AdminCombinationstabSearchController.php` | AJAX wyszukiwanie produktów dla pickerów BO |

### 6.3 Kontrolery

**Admin:** `AdminCombinationstabSearchController` — AJAX wyszukiwanie produktu/kombinacji używane przez Visibility, Exclusions, Overrides. To nie jest strona menu dla sprzedawców.

**Front:**

| Controller | Purpose |
|---|---|
| `Wishlist` | Toggle / lista wishlist (JSON + strona konta) |
| `BackInStock` | Subskrypcja alertów OOS (JSON) |
| `CsvImport` | Zastosowanie wklejonych ilości SKU/EAN (JSON) |
| `Export` | Pobranie arkusza CSV/XLSX/PDF |
| `Reorder` | Zapis / przywrócenie ostatnich ilości (JSON) |
| `PriceCalculator` | Żywa suma wybranych / tip volume (body JSON, bez curl) |

### 6.4 Hooki (rejestrowane przy instalacji)

`displayHeader`, `displayProductFooter`, `displayFooterProduct`, `displayProductTab`, `displayProductExtraContent`, `displayProductTabContent`, `CombinationsTable`, `ActionAdminControllerSetMedia`, `displayCustomerAccount`, `actionUpdateQuantity`.

Brak własnego `enable()` / `disable()` poza domyślnymi PrestaShop. Uninstall usuwa tabele funkcji, potem `parent::uninstall()`.

### 6.5 Override

Moduł nie dostarcza override klas/kontrolerów w `override/`. Override szablonów motywu dla `.tpl` modułu są opcjonalne i po stronie sprzedawcy.

### 6.6 Baza danych

Uninstall usuwa te tabele; klucze Configuration zostają.

| Table | Content |
|---|---|
| `ctp_wishlist` | `id_ctp_wishlist`, customer/guest, product, combination, shop, `date_add` |
| `ctp_backinstock` | Subskrypcje e-mail, product/combination, shop, lang, `notified`, dates |
| `ctp_entity_settings` | `entity_type`, `id_entity`, JSON `settings`, `date_upd` |

### 6.7 Klucze Configuration i wartości domyślne (install)

Wybrane domyślne wartości zapisywane przy instalacji: `ctp_position` = `productFooter`, `ctp_where` = `1`, `ctp_view_mode` = `list`, `ctp_image`/`ctp_price`/`ctp_reference`/`ctp_cname`/`ctp_atc`/`ctp_atcq`/`ctp_ajax`/`ctp_sort`/`ctp_quantity`/`ctp_availability`/`ctp_availability_d` = `1`, `ctp_ean`/`ctp_mpn` = `0`, `ctp_wishlist`/`ctp_bis`/`ctp_export`/`ctp_csv_import`/`ctp_reorder` = `0`, `ctp_group_rules` = `{}`, `ctp_column_order` = JSON z `CtpColumnRegistry::defaultKeys()`, plus powiązane klucze tax/hide/grid jak w `install()`. Kolejność kolumn/komórek też używa JSON (`ctp_column_order`, `ctp_grid_cell_order`). Tłumaczenia: `translations/{iso}.php`. Teksty `desc` pól są głównie w `CtpAdminBo`.

### 6.8 Rozszerzanie

Nadpisz szablony FO z motywu pod `modules/combinationstab/...` bez edycji paczki modułu. Motyw nadal musi wywoływać zarejestrowane hooki produktu dla wyjścia. Opcjonalna integracja Combination features wymaga obecności `lib/CtpCombfeat.php` oraz `CtpCombfeat::isAvailable()` = true.

## 7. Wsparcie

Strona produktu: https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html

Aby uzyskać pomoc: zaloguj się na konto klienta na mypresta.eu, otwórz Contact i wybierz **Support for paid modules**. Formularz wymaga logowania dla płatnych modułów; po zalogowaniu wybierz ten moduł z historii zakupów.
