---
title: "Cart Conditions - dokumentacja i instrukcja użytkownika"
sidebar:
  label: "Cart Conditions - dokumentacja i instrukcja użytkownika"
description: "Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które już mają Cart Conditions."
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cart conditions pro na MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/cart-conditions-pro/)
>
> ---


## 1. Wymagania

Cart Conditions działa w sklepie. Nie potrzebuje innego modułu ani konta w zewnętrznym serwisie.

- PrestaShop 1.7, 8 i 9. Instrukcję sprawdzono na PrestaShop 9.2.0.
- Wersja PHP wymagana przez tę wersję PrestaShop. Moduł nie wymaga dodatkowego rozszerzenia PHP.
- Żaden inny moduł nie jest wymagany.
- Reguły czytają bieżący koszyk. Wielkość katalogu nie zmienia sprawdzenia.

## 2. Instalacja

1. Otwórz **Moduły**, potem **Module Manager**.
2. Wgraj paczkę zip i zainstaluj moduł. Instalacja od razu go włącza.
3. Otwórz **Katalog**. Pojawia się pięć pozycji, w tej kolejności. Nazwy są po angielsku w każdym języku zaplecza:

- **Cart Conditions**
- **Cart Value Conditions**
- **Cart Quantity Conditions**
- **Cart Associations Conditions**
- **Cart value by country conditions**

Instalacja nie czyści pamięci podręcznej sklepu.

Odinstalowanie usuwa te pięć pozycji menu i odpina moduł od sklepu. Zostawia zapisane reguły, listę wykluczeń, ustawienie dat dostępności i ustawienie powiadomień. Ponowna instalacja przywraca menu, a stare reguły nadal są w sklepie.

## 3. Konfiguracja i codzienna praca

Klient składa koszyk. Na stronie koszyka sklep wypisuje każdą złamaną regułę w czerwonym komunikacie. Gdy klient idzie dalej do płatności, sklep wraca go do koszyka, dopóki wszystkie aktywne reguły nie są spełnione. Klient z listy **Exclude customers from conditions** omija każdą regułę i może złożyć zamówienie.

Przygotuj sklep w tej kolejności:

1. Otwórz **Configure** i zdecyduj, kogo oraz które produkty reguły mają pomijać.
2. Zdecyduj, czy wolno mieszać przyszłe daty dostępności.
3. Otwórz każdą listę w **Katalogu**, kliknij **Add new**, wypełnij formularz, ustaw **Active** na **On** i kliknij **Save**.
4. Złóż zamówienie testowe zwykłym klientem i klientem z listy wykluczeń.

Nowy formularz otwiera się z **Active** ustawionym na **Off**. **Save** zapisuje wiersz, a koszyk go pomija, dopóki nie ustawisz **On**. Strona konfiguracji odpowiada **Saved**. Listy reguł pokazują zwykłe potwierdzenie zaplecza po **Save**.

Niebieska notatka na **Configure** mówi: "Management of this module is located under Price Rules menu." Pięć linków w tej notatce oraz pozycje w **Katalogu** otwierają listy. Moduł nie dodaje pozycji w Price Rules.

Ekrany w tej instrukcji są z angielskiego zaplecza. Nazwy przycisków i pól podaję tak, jak widać je na tych ekranach.

![Linki na stronie konfiguracji](https://mypresta.eu/docs/images/docs/cartcon-configure-links.webp)

### 3.1 Strona konfiguracji

Otwórz **Moduły**, **Module Manager**, znajdź **Cart Conditions** i kliknij **Configure**.

#### Wykluczenie klientów i produktów

![Formularz wykluczeń](https://mypresta.eu/docs/images/docs/cartcon-configure-exclude.webp)

Wyszukaj klienta, kliknij wynik, a osoba trafi na listę wykluczeń. Usuń osobę z tej samej listy, zanim zapiszesz. Wykluczeni klienci omijają każdą regułę koszyka, także sprawdzenie dat dostępności.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Exclude customers from conditions** | puste | Klienci z tej listy składają zamówienie bez reguł koszyka. **Save** zapisuje listę. |
| **Exclude products from conditions** | **Do not exclude products** | **Exclude selected products** każe regułom pomijać wybrane produkty i kategorie. **Do not exclude products** liczy każdy produkt. |
| **Categories** | nic nie zaznaczone | Zaznaczone kategorie są pomijane, gdy przełącznik wyżej ma wartość **Exclude selected products**. |
| **Save** | - | Zapisuje klientów, przełącznik, produkty i kategorie. Strona pokazuje **Saved**. |

Wyszukiwarka produktów i drzewo kategorii są na tym samym formularzu. Produkt wybierasz tak jak klienta: szukasz, potem klikasz wynik.

#### Warunki globalne

![Porównanie dat dostępności](https://mypresta.eu/docs/images/docs/cartcon-configure-availability.webp)

Sprawdzenie obejmuje tylko produkty bez stanu magazynowego, których **Availability date** jest nadal w przyszłości. Produkty na stanie, z pustą albo przeszłą datą, oraz produkty wykluczone są pomijane. Jedna przyszła data w koszyku nie blokuje zamówienia. Dwie albo więcej różnych wartości blokują.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Block order of products with Various availabiltiy date** | **Off** | **On** blokuje koszyk, gdy te przyszłe daty nie pasują do porównania poniżej. **Off** pomija to sprawdzenie. PrestaShop i tak pozwala zamówić produkt, który będzie dostępny później. Ten przełącznik decyduje, czy różne daty mogą być w jednym koszyku. |
| **How to compare availability dates** | **Exact date** | **Exact date** blokuje zamówienie, gdy przyszłe daty nie są tym samym dniem. **Same calendar month** pozwala na różne dni tego samego miesiąca i roku, a blokuje, gdy różni się miesiąc albo rok. 5 listopada 2026 i 20 listopada 2026 przechodzą. 2 grudnia 2026 nie. 5 listopada 2027 nie. |
| **Save** | - | Zapisuje przełącznik i sposób porównania. Strona pokazuje **Saved**. Ten przycisk nie tworzy reguły w Katalogu. |

Komunikat koszyka dla **Exact date**: "Availability dates of products in your cart are different. You cant place an order." Dla **Same calendar month**: "Availability months of products in your cart are different. You cant place an order."

#### Aktualizacje MyPresta

![Sprawdzenie aktualizacji](https://mypresta.eu/docs/images/docs/cartcon-configure-updates.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Check updates** / **Check now** | - | Pyta MyPresta, czy jest nowszy plik. **Module is up to date!** znaczy, że ten plik jest aktualny. **New version available!** znaczy, że nowszy plik jest opublikowany. Przycisk go nie instaluje. |
| **Updates notifications** | **Disable** | **Enable** pokazuje ostrzeżenie w zapleczu, gdy wyjdzie nowsza wersja. **Disable** milczy. **Save** zapisuje wybór. |
| **Module page** | link | Otwiera stronę modułu, na której jest lista zmian. |
| **Save** | - | Zapisuje wybór powiadomień. |

### 3.2 Cart Conditions

Otwórz **Katalog**, potem **Cart Conditions**. Te reguły dotyczą każdego klienta, który nie jest wykluczony. Na tej liście nie ma pola grupy klientów.

![Lista Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-list.webp)

Kolumny: **ID**, **Cart condition**, **Target type**, **Target item**, **Active**. Pusty sklep pokazuje **No records found**. Filtry są nad kolumnami. Akcje wiersza: edycja, usunięcie i ikona **Active**. Akcja masowa: usuwanie. **Add new** otwiera formularz.

![Nowa reguła Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-form.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Condition** | **Must have** | **Must have** wymaga celu. **Can't have** go blokuje. |
| **Target type** | **Category** | **Category** to numer kategorii. **Product** to numer produktu. **More than defined number of products** to liczba sztuk całego koszyka. |
| **Target item** | puste | Numer kategorii, numer produktu albo liczba sztuk. Podpowiedź pola każe wpisać numer albo liczbę produktów. |
| **Active** | **Off** | **On** włącza wiersz do sprawdzenia koszyka. **Off** zostawia wiersz i go pomija. |
| **Save** | - | Zapisuje regułę. |

Co widzi klient:

- **Must have** i **Category**: "To place an order you must order product from category: ...".
- **Can't have** i **Category**: "Your cart contains product from forbidden category: .... To continue order please remove it from cart."
- **Must have** i **Product**: "To place an order you must order product: ...".
- **Can't have** i **Product**: "Your cart contains forbidden product: .... To continue order please remove it from cart."
- **Must have** i liczba sztuk: "Your cart contains less products than required (...). To continue order please increase quantity of products in your cart".
- **Can't have** i liczba sztuk: "Your cart contains more products than allowed (...). To continue order please decrease quantity of products in your cart".

Liczba sztuk to suma ilości w koszyku po odjęciu wykluczonych produktów. **Must have** wymaga dojścia do tej liczby. **Can't have** blokuje koszyk powyżej tej liczby.

### 3.3 Cart Value Conditions

Otwórz **Katalog**, potem **Cart Value Conditions**. Każdy wiersz to jedna grupa klientów, jedna kategoria i jedna kwota minimalna.

![Lista wartości](https://mypresta.eu/docs/images/docs/cartcon-value-list.webp)

Kolumny: **ID**, **Customer group**, **Cart condition**, **Target**, **Value**, **Active**. Pusta lista: **No records found**. Akcje wiersza: edycja, usunięcie, ikona **Active**. Akcja masowa: usuwanie. **Add new** otwiera formularz.

![Nowa reguła wartości](https://mypresta.eu/docs/images/docs/cartcon-value-form.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Customer Group** | pierwsza grupa w sklepie (Visitor w sklepie domyślnym) | Sprawdzani są tylko kupujący z tej grupy. Zalogowany klient jest sprawdzany w każdej swojej grupie. |
| **Condition** | **Must order from selected category** | To jedyny wybór. Reguła działa, gdy koszyk już zawiera tę kategorię. |
| **Target item** | puste | Numer kategorii. |
| **Value** | puste | Minimalna suma brutto produktów z tej kategorii. Wpisz ją w domyślnej walucie sklepu. Znak waluty na formularzu to waluta sklepu. |
| **Active** | **Off** | **On** włącza wiersz. **Off** zapisuje go bez użycia. |
| **Save** | - | Zapisuje regułę. |

Gdy kategorii nie ma w koszyku, reguła milczy. Gdy kategoria jest, a jej suma brutto jest niższa niż **Value**, koszyk pokazuje: "To place an order you must order for: ... from category: ...".

### 3.4 Cart Quantity Conditions

Otwórz **Katalog**, potem **Cart Quantity Conditions**.

![Lista ilości](https://mypresta.eu/docs/images/docs/cartcon-quantity-list.webp)

Kolumny: **ID**, **Customer group**, **Cart condition**, **Target**, **Quantity**, **Active**. Pusta lista: **No records found**. Akcje wiersza: edycja, usunięcie, ikona **Active**. Akcja masowa: usuwanie.

![Nowa reguła ilości](https://mypresta.eu/docs/images/docs/cartcon-quantity-form.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Customer Group** | pierwsza grupa w sklepie | Sprawdzana jest tylko ta grupa. |
| **Condition** | **Must order at least X products from selected category** | Wybierz limit. Pełna lista jest poniżej. |
| **Target country** | pierwszy kraj w sklepie | Używany tylko przy dwóch regułach "from Y category". Przy każdym innym warunku strona ukrywa tę listę. |
| **Target item** | puste | Numer kategorii, produktu, producenta albo wartość atrybutu, zależnie od **Condition**. Podpowiedź prosi o numer celu. Przy warunkach całego koszyka strona wpisuje słowo Cart i blokuje pole. |
| **Quantity** | puste | Liczba X z wybranego warunku. |
| **Accept only multiplied qty** | **Off** | **On** przyjmuje tylko wielokrotności **Quantity**, na przykład 6, 12, 18, 24, gdy **Quantity** to 6. **Off** przyjmuje każdą liczbę, która spełnia regułę. |
| **Active** | **Off** | **On** włącza wiersz. |
| **Save** | - | Zapisuje regułę. |

Kolejność **Condition** na formularzu:

- **Must order at least X products from selected category**
- **Can't more than X products from selected category**
- **Must order at least X products from selected manufacturer**
- **Can't more than X products from selected manufacturer**
- **Must order at least X quantity of selected product**
- **Can't order more than X quantity of selected product**
- **Must order at least X quantity of each product**
- **Can't order more than X quantity of each product**
- **Can't order more than X products with the same attribute value**
- **Cart must have at least X products**
- **Cart can't have more than X products**
- **Cart must have at least X different products**
- **Cart can't have more than X different products**
- **Cart of user from selected country must have more than X products**
- **Cart of user from selected country can't have more than X products**
- **Cart of user from selected country must have more than X products from Y category**
- **Cart of user from selected country can't have more than X products from Y category**

Przy dwóch ostatnich ustaw **Target country** i wpisz numer kategorii w **Target item**. Przy dwóch regułach kraju bez kategorii strona ukrywa **Target country**, więc kraju tam nie wybierzesz. Do limitu kwoty użyj **Cart value by country conditions**. Do limitu sztuk z jednej kategorii użyj dwóch ostatnich reguł ilości.

**Search for attribute value** widać tylko przy **Can't order more than X products with the same attribute value**. Wyszukaj, kliknij wartość, a trafi ona do **Target item**.

Tekst koszyka wynika z wyboru. Reguły kategorii i producenta mówią "at least" albo "can't order more than" i podają nazwę. Reguła produktu podaje bieżącą ilość. Reguła całego koszyka mówi "you must order more than" albo "you can't order more than" i podaje bieżącą ilość. Przy włączonym **Accept only multiplied qty** koszyk dopisuje: "We accept only multiplied quantity...".

Na stronie produktu motyw może pokazać "You must order at least: ... quantity of this product" dla **Must order at least X quantity of selected product**, gdy ten produkt jest celem i odwiedzający pasuje do grupy. To informacja. Blokada i tak dzieje się w koszyku.

### 3.5 Cart Associations Conditions

Otwórz **Katalog**, potem **Cart Associations Conditions**. Wiersz łączy jeden element z drugim dla jednej grupy. Reguła startuje dopiero wtedy, gdy pierwszy element jest już w koszyku.

![Lista powiązań](https://mypresta.eu/docs/images/docs/cartcon-associations-list.webp)

Kolumny: **ID**, **Customer group**, **Cart condition**, **Target item (1)**, **Associated item (2)**, **Active**. Pusta lista: **No records found**. Akcje wiersza: edycja, usunięcie, ikona **Active**. Akcja masowa: usuwanie.

![Nowe powiązanie](https://mypresta.eu/docs/images/docs/cartcon-associations-form.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Active** | **Off** | **On** włącza wiersz. |
| **Type of condition** | **Associations between product and product** | **Associations between product and category** albo **Associations between category and category** zmienia znaczenie obu numerów. |
| **For what customer group** | pierwsza grupa w sklepie | Sprawdzana jest tylko ta grupa. |
| **Target item (1)** | puste | Numer produktu albo kategorii. Reguła działa, gdy klient włoży ten obiekt do koszyka. |
| **Condition** | **If customer will add to cart Target item (1) then it must order Associated item (2)** | Wybory są poniżej. |
| **Associated item (2)** | puste | Wymagany albo zakazany numer produktu lub kategorii. |
| **Save** | - | Zapisuje parę. |

Wybory **Condition**:

- **If customer will add to cart Target item (1) then it must order Associated item (2)**. Tekst koszyka: "If your cart has a product: ... you must order also product: ..." albo odpowiednik dla kategorii.
- **If customer will add to cart Target item (1) then cart must have at least one different product**. Widać go tylko przy produkcie i produkcie. Sprawdzenie koszyka nie pokazuje komunikatu dla tego wyboru. Użyj innego wyboru, gdy koszyk ma blokować.
- **If customer will add to cart Target item (1) then it will be forbidden to order Associated item (2)**. Tekst: "If your cart has a product: ... you can't place an order for: ...".
- **If customer will add to cart Target item (1) then it will be forbidden to add any other product to cart**. Strona ukrywa **Associated item (2)**. Tekst: "If your cart has a product: ... you can't place an order for any other product."
- **If customer will add to cart Target item (1) then it will be forbidden to add products from categories other than Target item (1)**. Widać go tylko przy kategorii i kategorii. Strona ukrywa **Associated item (2)**.

Formularz ma też **Include subcategories of Target item (1)** i **Include subcategories of Associated item (2)**. Strona ukrywa oba przełączniki przy każdym typie. Reguła używa numerów, które wpiszesz.

### 3.6 Cart value by country conditions

Otwórz **Katalog**, potem **Cart value by country conditions**. Reguła bierze kraj adresu dostawy.

![Lista kwot według kraju](https://mypresta.eu/docs/images/docs/cartcon-country-list.webp)

Kolumny: **ID**, **Customer group**, **Condition**, **Country**, **Value**, **Active**. Pusta lista: **No records found**. Akcje wiersza: edycja, usunięcie, ikona **Active**. Akcja masowa: usuwanie.

![Nowa kwota kraju](https://mypresta.eu/docs/images/docs/cartcon-country-form.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Customer Group** | pierwsza grupa w sklepie | Sprawdzana jest tylko ta grupa. |
| **Target country** | pierwszy kraj w sklepie | Reguła działa, gdy adres dostawy jest z tego kraju. Lista to kraje sklepu. |
| **Condition** | **Cart must be worth at least ...** | **Cart can't be worth more than ...** to maksimum. |
| **Condition tax** | **Tax included** | **Tax excluded** porównuje sumę bez podatku. Komunikat koszyka powtarza wybrany podpis podatku. |
| **Cart value type** | **Products + shipping** | **Products** wyłącza wysyłkę z porównywanej sumy. |
| **Value** | puste | Kwota w domyślnej walucie sklepu. |
| **Active** | **Off** | **On** włącza wiersz. |
| **Save** | - | Zapisuje regułę. |

Poniżej minimum koszyk pokazuje: "To place an order from country: ... your cart must be worth at least ..., while you cart is worth ...". Powyżej maksimum: "To place an order from country: ... your cart can't be worth more than ..., while you cart is worth ...".

## 4. Front sklepu

Klient nie otwiera osobnej strony. Moduł mówi na stronie produktu i w koszyku.

Na stronie produktu, i tylko przy aktywnej regule **Must order at least X quantity of selected product** wycelowanej w ten produkt, motyw może pokazać: "You must order at least: ... quantity of this product". Motyw musi wyświetlać obszar akcji produktu. Ta instrukcja nie ma zdjęcia sklepu, bo tej linii nie potwierdzono na motywie testowym.

W koszyku każda złamana reguła jest linią jednego czerwonego komunikatu. Nazwy wymaganych i zakazanych produktów oraz kategorii są linkami. Gdy klient otworzy płatność przy złamanej regule, sklep wraca go do koszyka i pokazuje ten sam komunikat.

Klient z listy wykluczeń nie widzi tych komunikatów i nie jest zawracany.

Nie ma adresu frontu do skopiowania. Nie ma formularza, w którym klient akceptuje albo odrzuca regułę.

## 5. Problemy

**W Katalogu nie ma pięciu pozycji.** Moduł nie jest zainstalowany albo został odinstalowany. Zainstaluj go ponownie w **Module Manager**. Stare reguły wracają razem z nim.

**Niebieska notatka mówi o Price Rules, a w Price Rules nie ma Cart Conditions.** Użyj pięciu linków w notatce albo **Katalogu**. Rodzic menu to Katalog.

**Zapisana reguła nic nie robi.** **Active** jest **Off**, klient jest na liście wykluczeń albo nie jest w wybranej grupie. Niezalogowany odwiedzający jest sprawdzany jako grupa Visitor. Otwórz wiersz, ustaw **Active** na **On** i testuj klientem z tej grupy.

**Reguła wartości milczy.** Kategorii nie ma w koszyku. Dodaj produkt z tej kategorii. Porównywana suma jest brutto.

**Dwie ilościowe reguły kraju ignorują kraj.** **Target country** jest ukryte, dopóki **Condition** nie jest jedną z dwóch linii "from Y category". Wybierz jedną z nich albo użyj **Cart value by country conditions** do limitu kwoty.

**Same calendar month nadal blokuje listopad i listopad.** Lata się różnią. 5 listopada 2026 i 5 listopada 2027 to różne wartości. Produkt musi być też bez stanu i z przyszłą datą **Availability date**. Produkty na stanie nie są porównywane.

**Check now nic nie pokazuje albo ostrzeżenie się nie pojawia.** Serwer sklepu nie może otworzyć zdalnego adresu MyPresta. **Check now** tylko podaje wersję. Nie pobiera i nie instaluje pliku. Otwórz **Module page** i weź nowy plik stamtąd.

**W koszyku nie ma komunikatu, a płatność i tak wraca do koszyka.** Motyw nie drukuje bloku koszyka. Powrót do koszyka nadal działa. Nadpisz szablon koszyka w motywie albo sprawdź, czy motyw woła hook koszyka.

**Odinstalowanie zabrało menu, a kolejna instalacja pokazuje stare reguły.** Tak działa odinstalowanie. Usuń wiersze na listach przed odinstalowaniem, jeśli potem moduł ma być pusty.

## 6. Dla developera

### 6.1 Przegląd

Klasa główna `cartcon`, wersja 2.1.9, nazwa na liście **Cart Conditions**, autor MyPresta.eu, zakładka `advertising_marketing`. `cartconPrestashopNewCompatibility` rozszerza `cartcon` do formatowania cen i nie jest instancją modułu. `psversion()` mapuje major 8 i wyższy na gałąź 1.7 przy kilku wyborach znaczników zaplecza. Nie ma nadpisania `enable()` ani `disable()`.

`getRestrictions()` czyta aktywne wiersze bieżącego sklepu, pomija klientów z `CARTCON_CUSTOMERS` i wypełnia `errors_cartcon`. `hookDisplayShoppingCart` drukuje tę listę. `hookDisplayPaymentTop` przekierowuje do koszyka z `cartcon=show`, gdy lista nie jest pusta. `hookDisplayProductActions` drukuje minimum ilości tylko dla `cartcon_quantity.c_type = 2` tego numeru produktu.

### 6.2 Pliki

- `cartcon.php` - instalacja, formularze konfiguracji, sprawdzenia, hooki.
- `lib/prestashop9compatibility.php` - `cartconPrestashopNewCompatibility`.
- `controllers/admin/AdminCartConditionController.php` - must-have i can't-have.
- `controllers/admin/AdminCartValueConditionController.php` - minimum kwoty kategorii.
- `controllers/admin/AdminCartQuantityConditionController.php` - reguły ilości.
- `controllers/admin/AdminCartAssociationsConditionController.php` - pary.
- `controllers/admin/AdminCartCountryConditionController.php` - kwoty kraju.
- `models/CartCondition.php`, `CartValueCondition.php`, `CartQuantityCondition.php`, `CartAssociationsCondition.php`, `CartCountryCondition.php` - modele.
- `views/templates/front/displayShoppingCart.tpl` - czerwony komunikat.
- `views/templates/front/productActions.tpl` - minimum na stronie produktu.
- `views/templates/admin/script.tpl` - zachowanie formularza ilości.
- `views/templates/admin/search-attribute-value.tpl` - szukanie atrybutu, widoczne przy typie ilości 7.
- `lib/searchTool/searchTool.php` - `initTool()` wstrzykuje tylko skrypty. Nie renderuje panelu.

### 6.3 Kontrolery

Pięć kontrolerów admina rozszerza `ModuleAdminController`. `createMenu()` wstawia zakładkę dla każdego języka z angielską nazwą, rodzic `AdminCatalog` (`Sell > Catalog` na PrestaShop 9). Klasy: `AdminCartCondition`, `AdminCartValueCondition`, `AdminCartQuantityCondition`, `AdminCartAssociationsCondition`, `AdminCartCountryCondition`. Nie ma kontrolera frontu. Jedyna flaga frontu czytana przez moduł to `cartcon=show`, dodawana przy przekierowaniu z płatności.

`script.tpl` wyłącza **Target item** i wpisuje słowo `Cart` dla typów ilości 4, 5, 8, 9, 15 i 16. Lista krajów jest pokazywana dla typów 8 i 9, a następny blok ją ukrywa, chyba że typ to 10 albo 11. Widoczny skutek: pole kraju tylko dla typów 10 i 11. Typ 7 pokazuje `.searchAttributeValue`.

Skrypt powiązań ukrywa `.subcatt` i `.subcata` przy każdym typie. Id warunku 4 jest włączone tylko dla kategorii z kategorią (typ 3). Id 5 widać tylko dla produktu z produktem (typ 1). Id 3, 4 i 5 ukrywają **Associated item (2)**. `getRestrictions()` porównuje `c_value` powiązania 1, 2, 3 i 4. Nie porównuje `c_value` 5.

### 6.4 Hooki

- `displayHeader` - CSS i JS frontu oraz ajax `getCartConditions`.
- `displayShoppingCart` - lista komunikatów.
- `displayProductActions` - informacja o minimum ilości.
- `displayPaymentTop` - powrót do koszyka, gdy jest jakikolwiek błąd.
- `actionAdminControllerSetMedia` - assety zaplecza.

Moduł nie rejestruje własnych hooków.

### 6.5 Nadpisania

Brak. Nie ma nadpisania klasy ani kontrolera.

### 6.6 Baza

Tabele z prefiksem sklepu. `inconsistency()` / `maybeUpdateDatabase()` dopisują brakujące kolumny w `installdb()` i z przycisku aktualizacji. Nie chodzą przy każdym wejściu na konfigurację. Odinstalowanie nie kasuje tabel.

| Tabela | Zawartość |
|---|---|
| `cartcon` | `id_cartcon`, `c_type`, `c_value`, `c_option`, `active` domyślnie 1, `id_shop` dopisywane później. Bez grupy klientów. |
| `cartcon_value` | `id_cartcon_value`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` domyślnie 0, `c_group`, `id_shop`. `c_only_if_in_cart` nie ma na formularzu. |
| `cartcon_quantity` | `id_cartcon_quantity`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` domyślnie 0, `c_group`, `id_shop`, `multiply` domyślnie 0, `c_country` domyślnie 0. |
| `cartcon_ass` | `id_cartcon_ass`, `c_type`, `c_target1`, `c_target2`, `c_value`, `active`, `c_group`, `id_shop`, `subcatt` domyślnie 0, `subcata` domyślnie 0. Dopasowanie kategorii czyta `subcatt` i `subcata`, gdy są równe 1. Formularz ukrywa oba przełączniki. |
| `cartcon_country` | `id_cartcon_country`, `c_type`, `c_target`, `c_value`, `active`, `c_group`, `id_shop`, `c_tax` domyślnie 1, `c_cartValueType` domyślnie 1. |

Nowe ekrany HelperForm wysyłają **Active** jako 0, bo zaznaczone jest Off. Domyślne 1 w kolumnie działa tylko wtedy, gdy kolumna jest pominięta.

### 6.7 Klucze i tłumaczenia

| Klucz | Gdy go nie ma |
|---|---|
| `CARTCON_CUSTOMERS` | pusto. Numery klientów po przecinku. Tacy klienci wychodzą z `getRestrictions()` od razu. |
| `ccon_visibility_rule` | `0` oznacza brak wykluczenia. `1` pomija wybrane produkty i kategorie. |
| `ccon_visibility_products` | pusta lista numerów produktów. |
| `ccon_visibility_cat` | pusta lista numerów kategorii. |
| `CARTCON_FUTURE` | brak, traktowany jako wyłączony. `1` uruchamia porównanie dat. |
| `CARTCON_FUTURE_MODE` | brak rzutuje się na `0` (**Exact date**). `1` grupuje przez `date('Y-m')`. Porównywane produkty mają `stock_quantity <= 0` i `available_date` ściśle w przyszłości. Więcej niż jeden różny klucz blokuje zamówienie. |
| `mypresta_updates` | `0` wyłącza automatyczne ostrzeżenie. `1` je włącza. |
| `update_cartcon` | znacznik czasu ostatniego sprawdzenia. |
| `updatev_cartcon` | wersja z ostatniego sprawdzenia. |

Sprawdzenie używa `allow_url_fopen` i `file_get_contents` do `dev.mypresta.eu`. Pliki tłumaczeń sklepu to `translations/{iso}.php`. Nazwy menu są zapisywane po angielsku dla każdego języka w `createMenu()` i nie przechodzą przez plik tłumaczeń. Opisy pól są w wywołaniach `l()` kontrolerów i w `desc` HelperForm w `cartcon.php`. `getCustomerGroups()` mapuje koszyk z `id_customer` 0 na grupę o id 1. Gałąź gościa działa tylko wtedy, gdy `id_customer` nie jest ustawione.

### 6.8 Rozszerzanie

Nadpisz z motywu `views/templates/front/displayShoppingCart.tpl` i `views/templates/front/productActions.tpl`. Jeśli motyw nigdy nie woła `displayShoppingCart` ani `displayProductActions`, nie ma czego nadpisać i klient nie zobaczy komunikatu. Przekierowanie z płatności nadal działa.

## 7. Pomoc

Strona modułu: [Cart Conditions Pro](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html).

W sprawie tego modułu zaloguj się na konto klienta na mypresta.eu, otwórz kontakt i wybierz temat **Support for paid modules**. Formularz podaje, że przy modułach płatnych logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
