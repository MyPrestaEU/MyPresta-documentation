---
title: MyFAQ Free - dokumentacja i instrukcja użytkownika
sidebar:
  label: MyFAQ Free - dokumentacja i instrukcja użytkownika
description: Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które mają już MyFAQ Free.
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free Product FAQ na MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-product-faq.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/free-product-faq/)
>
> ---


## 1. Wymagania

MyFAQ Free działa wewnątrz PrestaShop. Nie potrzebuje innego modułu.

- PrestaShop od 1.7.0.0 do PrestaShop 9.
- Taka wersja PHP, jakiej wymaga ta wersja PrestaShop. Moduł nie sprawdza wersji PHP osobno.
- Żadne dodatkowe rozszerzenie PHP nie jest wymagane. Sprawdzenie aktualizacji używa cURL, gdy serwer go ma. Gdy cURL nie ma, sprawdzenie czyta adres tylko wtedy, gdy serwer pozwala czytać zdalne adresy.
- Żaden inny moduł nie jest wymagany. Strona produktu w motywie musi drukować stopkę produktu albo dodatkowe zakładki produktu, żeby klient zobaczył pytania.
- Do zapisania i pokazania trzech pytań nie potrzeba konta w zewnętrznym serwisie. Darowizna PayPal na stronie konfiguracji jest dobrowolna. Sprawdzenie aktualizacji wymaga tylko, żeby sklep doszedł do MyPresta.eu.

Każdy produkt trzyma trzy pytania. Importu nie ma, więc duży katalog nie uruchamia paczki ani nie podnosi pamięci, o którą moduł prosi.

## 2. Instalacja

1. W zapleczu otwórz **Moduły**, potem **Menedżer modułów**.
2. Wgraj paczkę zip i kliknij **Zainstaluj**.
3. Otwórz **Konfiguruj** przy **MyFAQ Free**. Strona otwiera się na **Unlock Pro**. Na pasku są też **Settings** i **Updates**.
4. MyFAQ Free nie dodaje pozycji do lewego menu. Pytania wpisuje się na każdym produkcie.

Instalacja nie czyści pamięci podręcznej PrestaShop. Gdy po aktualizacji strona produktu nadal pokazuje poprzedni układ, wyczyść pamięć podręczną w **Zaawansowane**, **Wydajność**.

Wyłączenie to przełącznik w **Menedżerze modułów**. Strona produktu przestaje drukować pytania, a edycja produktu przestaje pokazywać blok FAQ. Pytania i ustawienie miejsca zostają. Po ponownym włączeniu są używane tak jak wcześniej. Moduł nie ma własnego przycisku włączania ani wyłączania.

Usunięcie: kliknij **Odinstaluj** i potwierdź. Odinstalowanie kasuje pytania, miejsce wyświetlania, tytuł zakładki i nagłówek. Znika ukryta strona, która zapisuje pytania. Pliki modułu zostają na serwerze, dopóki nie usuniesz modułu. Ponowna instalacja startuje z pustymi pytaniami, miejscem **Product footer**, tytułem zakładki FAQ i pustym nagłówkiem. Stare pytania nie wracają. Przełącznik powiadomień o aktualizacji jest wspólny z innymi modułami MyPresta i zostaje taki, jaki go zostawiłeś.

## 3. Konfiguracja i praca w zapleczu

Ekrany w tej instrukcji są po angielsku. Dalej używam nazw z tej instrukcji, a napis z ekranu podaję tak, jak widać go w zapleczu.

Pytania wpisujesz na produkcie, nie na stronie modułu. Otwórz **Katalog**, **Produkty** i edytuj produkt. W sklepie z kilkoma sklepami strona produktu prosi o wybranie jednego sklepu w nagłówku multisklepu. Otwórz zakładkę **Modules**, a w **Module to configure** wybierz **MyFAQ Free**. Wpisz do trzech pytań, zaznacz **Show on the product page** i kliknij **Save these questions**. Slot z pustym pytaniem nie wchodzi na stronę produktu.

Na stronie modułu wybierasz tylko, gdzie ten blok się drukuje i jak się nazywa. **Product footer** drukuje akordeon pod produktem. **Product tab** dodaje jedną zakładkę produktu i zostawia stopkę pustą. Produkt bez pytania nie pokazuje nic w żadnym z tych miejsc.

Klient otwiera produkt, klika pytanie i czyta odpowiedź. Nie ma formularza, w którym klient wysłałby nowe pytanie. Ścieżka kończy się, gdy strona produktu pokazuje akordeon, albo gdy produkt nie ma czego pokazać.

Otwórz **Moduły**, **Menedżer modułów**, **MyFAQ Free**, **Konfiguruj**. Nad paskiem strona podaje **I am developing this module for free - if you want** i przycisk **send me a donation**. Pod tym wierszem jest pasek innych modułów. Notka pod paskiem mówi, że pytania ustawia się na każdym produkcie.

### 3.1 Unlock Pro

![Unlock Pro](https://mypresta.eu/docs/images/docs/myfaqfree-configure-unlock.webp)

Ekran to sekcja **Unlock Pro**, z wierszem darowizny nad paskiem.

**Unlock Pro** nic nie zapisuje i nie wpisuje pytań. Wiersz pod paskiem to **MyFAQ without the three-question limit**. Mówi, że MyFAQ zostawia każde pytanie, które już napisałeś, i dodaje katalog, pisanie z AI oraz API, a pytania na produkcie zostają w darmowym module, dopóki ich nie przeniesiesz.

Ramka **The full FAQ for the catalogue** wymienia to, co dodaje płatny moduł, i kończy się przyciskiem **See MyFAQ**. Przycisk otwiera stronę płatnego modułu w nowej karcie. Ta zakładka nic nie zapisuje dla darmowego modułu.

### 3.2 Settings

![Settings](https://mypresta.eu/docs/images/docs/myfaqfree-configure-settings.webp)

Ekran to sekcja **Settings**. Zdjęcie pokazuje sklep, który już zapisał **Product tab** i nagłówek. Świeża instalacja ma wartości z tabeli.

Wiersz pod paskiem to **Where the three questions are shown**. Mówi, że darmowy moduł zapisuje FAQ na każdym produkcie, najwyżej trzy pytania, a tutaj wybierasz tylko stopkę produktu albo zakładkę produktu oraz nazwy tego bloku.

Tytuł formularza to **Placement**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Show the FAQ** | Product footer | **Product footer** drukuje akordeon pod produktem. **Product tab** dodaje jedną zakładkę produktu i zostawia stopkę pustą. Produkt bez pytania nie pokazuje nic w żadnym z tych miejsc. |
| **Tab title** | FAQ w każdym języku | Nazwa zakładki produktu, gdy **Show the FAQ** to **Product tab**. Przyciskiem języka wypełnij każdy język. Pusty język pokazuje FAQ. |
| **Heading** | puste | Tytuł nad pytaniami, w stopce i w zakładce. Przyciskiem języka wypełnij każdy język. Puste pole pokazuje same pytania. |

Kliknij **Save**. Strona pokazuje **Settings saved.**

Przycisk języka pokazuje języki tego sklepu. Na sklepie ze zdjęcia są to angielski, francuski i polski.

### 3.3 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaqfree-configure-updates.webp)

Ekran to sekcja **Updates**.

Wiersz pod paskiem to **Newer versions of MyFAQ Free**. Mówi, że sprawdzenie podaje wersję, a wgranie paczki zostaje ręcznym pobraniem.

Tytuł formularza to **MyPresta Updates**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Check updates** | **Check now** | Ręcznie sprawdza, czy na serwerach MyPresta.eu jest nowsza wersja tego modułu. Przycisk nie pobiera i nie instaluje paczki. Po sprawdzeniu obok przycisku widać **New version available!** albo **Module is up to date!** |
| **Updates notifications** | Enable | Włączone sprawdza MyPresta.eu automatycznie i pokazuje powiadomienie o nowej wersji tego dodatku. **Disable** zatrzymuje to automatyczne sprawdzenie. Przełącznik jest wspólny: inne moduły MyPresta w tym sklepie używają tego samego przełącznika. Automatyczne sprawdzenie chodzi mniej więcej co trzy dni, gdy zaplecze jest używane. |
| **Module page** | link o nazwie **MyFAQ Free** | Bezpośredni link do oficjalnej strony dodatku, na której można czytać o zmianach w module (changelog). Link otwiera [https://mypresta.eu/](https://mypresta.eu/). |

Kliknij **Save**. Strona pokazuje **Update settings saved.**

Gdy zgłoszono nowszą wersję i powiadomienia są włączone, zaplecze pokazuje **New version available, check http://MyPresta.eu for more informations** oraz link **More details in changelog**. Ten link otwiera ten sam adres co **Module page**.

### 3.4 Pytania na produkcie

![FAQ na produkcie](https://mypresta.eu/docs/images/docs/myfaqfree-product-block.webp)

Ekran to blok **MyFAQ Free** na produkcie, na zakładce **Modules**. Zdjęcie pokazuje produkt, który ma już trzy pytania. Nowy produkt startuje z pustymi polami. Języki EN, FR i PL to języki tego sklepu.

Otwórz **Katalog**, **Produkty**, edytuj produkt, otwórz **Modules** i w **Module to configure** wybierz **MyFAQ Free**.

Na produkcie, który nie został jeszcze zapisany, blok mówi **Save the product first** oraz **The three FAQ slots appear after the product has an id.** Zapisz produkt i wróć do tego bloku.

Ramka **Three questions on this product** powtarza notkę o płatnym module i kończy się **See MyFAQ**. Nie zapisuje darmowych pytań.

Pod nią **FAQ for this product** mówi: trzy pytania, puste pytanie zostaje poza stroną, a **Save these questions** zostawia cię na tym produkcie. Przyciski języka przełączają pytanie i odpowiedź. Pojawiają się, gdy sklep ma więcej niż jeden język.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Question 1**, **Question 2**, **Question 3** | trzy puste sloty, **Show on the product page** zaznaczone | Trzy sloty tego produktu w tym sklepie. Klient widzi je w tej kolejności. |
| **Show on the product page** | zaznaczone | Zaznaczone pokazuje slot, gdy pytanie jest wypełnione. Odznacz, żeby zostawić tekst i ukryć slot. |
| **Question** | puste | Wiersz, który klika klient. Pole przyjmuje 512 znaków. Puste pytanie zostaje poza stroną. Wpisz pytanie w każdym języku, w którym sprzedajesz. Język z pustym pytaniem nie jest pokazywany w tym języku. |
| **Answer** | puste | Tekst pod pytaniem. Koniec wiersza w polu staje się nowym wierszem na stronie produktu. Wpisany tekst jest pokazywany jako tekst. |
| **Save these questions** | przycisk | Zapisuje trzy sloty i zostaje na tym produkcie. W trakcie zapisu wiersz pod przyciskiem mówi **Saving the three questions…** Po udanym zapisie mówi **The three FAQ slots are saved. A slot with an empty question stays off the product page.** |

Poza produktem nie ma listy pytań ani akcji masowej. Usunięcie produktu kasuje jego trzy pytania. Pytania zapisane w jednym sklepie nie pokazują się w innym, dopóki nie wpiszesz ich tam.

## 4. Front sklepu

![Pytania na stronie produktu](https://mypresta.eu/docs/images/docs/myfaqfree-front-tab.webp)

Ekran sklepu jest po angielsku.

Klient widzi blok tylko na stronie produktu i tylko wtedy, gdy ten produkt ma co najmniej jedno pytanie wypełnione, z zaznaczonym **Show on the product page** i napisane w języku klienta.

Gdy **Show the FAQ** to **Product footer**, akordeon siedzi pod produktem. Gdy **Product tab**, ten sam akordeon jest w jednej zakładce produktu, a stopka zostaje pusta. Nazwa zakładki to **Tab title**. Pusty tytuł zakładki widać jako FAQ. Zdjęcie to zakładka w tym sklepie: zakładka nazywa się FAQ, a nagłówek to **Questions before you buy**.

Nagłówek, gdy go wpiszesz, jest nad pytaniami. Pierwsze pytanie jest otwarte po załadowaniu strony. Klient klika pytanie, żeby otworzyć albo zamknąć odpowiedź. Klient bez JavaScript widzi każdą odpowiedź. Pod listą wiersz **Powered by MyFAQ for PrestaShop** prowadzi do płatnego modułu.

Nie ma osobnej strony, adresu do skopiowania ani formularza dla klienta. Produkt, który nie ma czego pokazać, nie drukuje bloku.

## 5. Problemy

**Produkt nie pokazuje pytań.** Pytanie w tym języku jest puste, **Show on the product page** jest odznaczone, moduł jest wyłączony albo motyw nie drukuje miejsca, które wybrałeś. Otwórz produkt i sprawdź slot, a na **Settings** potwierdź **Show the FAQ**. **Product footer** wymaga, żeby motyw drukował stopkę produktu. **Product tab** wymaga, żeby motyw drukował dodatkowe zakładki produktu. Produkt bez wypełnionego pytania nie pokazuje nic w żadnym z tych miejsc.

**Blok na nowym produkcie mówi Save the product first.** Produkt nie ma jeszcze id. Zapisz produkt, otwórz go ponownie i pojawią się trzy sloty. Gdy klikniesz **Save these questions** wcześniej, wiersz mówi **Save the product first, then add the FAQ.**

**Save these questions kończy się The FAQ could not be saved.** Kliknij **Save these questions** jeszcze raz. Gdy nadal się nie uda, sprawdź, czy moduł jest zainstalowany i czy profil pracownika może edytować produkty.

**Wiersz mówi The FAQ could not reach the shop.** Przeglądarka nie doszła do zaplecza. Sprawdź połączenie i kliknij **Save these questions** jeszcze raz. W trakcie zapisu wiersz mówi **Saving the three questions…**

**Pytanie w sklepie jest krótsze niż to, które wpisałeś.** Pole pytania kończy się na 512 znakach.

**Odpowiedź pokazuje tagi, które wpisałeś.** Odpowiedź jest zwykłym tekstem. Koniec wiersza zostaje. Tagi widać jako znaki.

**Stopka jest pusta po wybraniu Product tab.** Tak działa to ustawienie. **Product tab** zostawia stopkę pustą i wkłada akordeon w zakładkę produktu. Wybierz **Product footer** na **Settings** i kliknij **Save**, gdy akordeon ma być pod produktem.

**Inny sklep nie pokazuje pytań.** Trzy sloty należą do sklepu, który edytowałeś. Przełącz nagłówek multisklepu na ten sklep, otwórz produkt i wpisz pytania tam.

**Strona produktu w zapleczu prosi o wybranie sklepu.** Edycja produktu działa w jednym sklepie naraz. Wybierz sklep w nagłówku multisklepu, potem otwórz **Modules**.

**Check now mówi Module is up to date!, a spodziewałeś się nowszej wersji.** Sprawdzenie nie odczytało wersji z MyPresta.eu albo ta paczka jest tą, którą podał serwer. Sprawdź, czy sklep dochodzi do MyPresta.eu, i kliknij **Check now** jeszcze raz. Przycisk nigdy nie instaluje paczki.

**Ostrzeżenie mówi New version available, check http://MyPresta.eu for more informations.** Powiadomienia są włączone i zgłoszono nowszą wersję. Otwórz **Updates**, przeczytaj **Module page** i wgraj paczkę sam, gdy jej chcesz. **Disable** przy **Updates notifications** zatrzymuje ostrzeżenie. Ten przełącznik jest wspólny z innymi modułami MyPresta.

**Pasek darowizny zostaje pusty.** Reszta strony konfiguracji działa. Pytania wpisz na produkcie, a miejsce ustaw na **Settings**.

## 6. Dla developera

### 6.1 Przegląd

Klasa główna `myfaqfree`, wersja `1.0.0`, nazwa na liście **MyFAQ Free**, autor mypresta.eu, zakładka `front_office_features`. Zgodność jest zadeklarowana od `1.7.0.0` do `9.99.99`.

Miejsce jest czytane z `MYFAQFREE_DISPLAY` (`footer`, dopóki wartość nie jest `tab`). Tytuł zakładki i nagłówek są czytane per język z `MYFAQFREE_TAB_TITLE` i `MYFAQFREE_HEADING`. Strona produktu ładuje najwyżej trzy aktywne sloty bieżącego sklepu i języka przez `MyfaqfreeRepository::frontItems()` i renderuje `views/templates/hook/product.tpl`. Pierwsza pozycja dostaje w szablonie `is-open`. Odpowiedź jest escapowana i przepuszczana przez `nl2br`.

### 6.2 Pliki

- `myfaqfree.php` — instalacja, konfiguracja, panel produktu, render frontu.
- `lib/MyfaqfreeRepository.php` — trzy sloty, tabele, zapis i kasowanie.
- `lib/updatesChecker.php` — klasa `myfaqfreeUpdate`, sprawdzenie aktualizacji.
- `lib/prestashop9compatibility.php` — katalogi szablonów HelperForm i `curl_close` na PHP przed 8.
- `controllers/admin/AdminMyfaqfreeController.php` — zapis ajax. Kontroler jest ukrytą zakładką.
- `views/templates/admin/configure.tpl` — Unlock Pro, Settings, Updates.
- `views/templates/admin/_pro.tpl` — ramka płatnego modułu.
- `views/templates/admin/product.tpl` — trzy sloty na produkcie.
- `views/templates/hook/product.tpl` — akordeon. Zmienne: `mff_heading`, `mff_items` (`id`, `question`, `answer`), `mff_pro_url`.
- `views/js/admin.js` — przełącznik języka i zapis na produkcie.
- `views/js/front.js` — otwieranie i zamykanie pytania.
- `views/css/admin.css`, `views/css/front.css`.
- `translations/en.php` — jest i jest pusty. Angielskie napisy są napisami źródłowymi.

### 6.3 Kontrolery

`AdminMyfaqfree` rozszerza `ModuleAdminController`. Zakładka powstaje z `id_parent = -1`, więc nie ma jej w lewym menu. Nazwa klasy zakładki to `AdminMyfaqfree`, etykieta to MyFAQ Free. `ajaxProcessSave` przekazuje do `myfaqfree::ajaxProcessSave()`. Blok produktu wysyła `id_product`, `mff_on_{position}`, `mff_q_{position}_{id_lang}` i `mff_a_{position}_{id_lang}` do `AdminMyfaqfree` z `ajax=1` i `action=Save`.

Kontrolera frontu nie ma. Akordeon jest renderowany z hooków.

`getContent()` to strona konfiguracji. `mff_tab` przyjmuje `unlock`, `settings` i `updates`. Każda inna wartość otwiera `unlock`.

### 6.4 Hooki

Rejestrowane w `install()`:

| Hook | Rola |
|---|---|
| `displayHeader` | CSS i JS tylko na stronie produktu. |
| `displayFooterProduct` | Akordeon, gdy miejsce to stopka. |
| `displayProductFooter` | Ten sam akordeon. Flaga statyczna drukuje go raz na żądanie. |
| `displayProductExtraContent` | Jedna zakładka produktu, gdy miejsce to zakładka. W przeciwnym razie pusta tablica. |
| `displayAdminProductsExtra` | Trzy sloty na edycji produktu. |
| `actionAdminControllerSetMedia` | CSS i JS zaplecza na stronie produktu i na stronie konfiguracji modułu. |
| `actionProductDelete` | Kasuje sloty tego produktu. |

Klasa nie definiuje `enable()` ani `disable()`. Wyłączenie w Menedżerze modułów używa przełącznika rdzenia. Klasa nie wystawia własnego hooka.

`ensureHiddenTab()` i `grantHiddenTabAccess()` chodzą z konstruktora, gdy obiekt jest `myfaqfree`, z `getContent()` i z hooka produktu. Dostęp nadaje `view`, `add`, `edit` i `delete` profilowi 1 oraz bieżącemu profilowi pracownika.

### 6.5 Nadpisania

Moduł nie nadpisuje klasy ani kontrolera.

### 6.6 Baza

| Tabela | Zawartość |
|---|---|
| `ps_myfaqfree_item` | `id_item`, `id_product`, `id_shop`, `position` (1–3), `active`, `date_upd`. Unikalny klucz na produkt, sklep i pozycję. |
| `ps_myfaqfree_item_lang` | `id_item`, `id_lang`, `question` (varchar 512), `answer` (text). |

`uninstall()` kasuje obie tabele, gdy `parent::uninstall()` zwróci true. Gdy `parent::uninstall()` zwróci false, tabele zostają. Zakładka i trzy klucze konfiguracji są kasowane przed tym returnem. Usunięcie produktu kasuje jego wiersze w obu tabelach. Slot, którego każdy język ma puste pytanie, jest kasowany przy zapisie. Język z pustym pytaniem nie jest wstawiany.

Tabele powstają przy instalacji. Wejście na stronę konfiguracji nie dopisuje kolumny.

### 6.7 Klucze i tłumaczenia

| Klucz | Gdy go nie ma albo przy instalacji |
|---|---|
| `MYFAQFREE_DISPLAY` | Instalacja zapisuje `footer`. Każda wartość inna niż `tab` jest traktowana jako stopka. |
| `MYFAQFREE_TAB_TITLE` | Instalacja zapisuje `FAQ` dla każdego języka. Pusty język przy renderze wraca do źródłowego FAQ. |
| `MYFAQFREE_HEADING` | Instalacja zapisuje pusty ciąg dla każdego języka. Pusty nagłówek nie jest drukowany. |
| `mypresta_updates` | Tego modułu go nie tworzy. Brak jest traktowany jako włączone. **Disable** zapisuje `0`. Odinstalowanie go nie kasuje. |
| `update_myfaqfree` | Czas uniksowy ostatniego sprawdzenia. Odinstalowanie go nie kasuje. |
| `updatev_myfaqfree` | Ciąg wersji zwrócony przez sprawdzenie. Odinstalowanie go nie kasuje. |

Adres sprawdzenia to `https://dev.mypresta.eu/update/get.php`. Odstęp to 259200 sekund. cURL jest używany, gdy istnieje `curl_init`, z czasem 3 sekund. W przeciwnym razie `file_get_contents`, gdy włączone jest `allow_url_fopen`. Treść odpowiedzi jest oczyszczona z tagów i zapisana jako dostępna wersja.

Napisy zaplecza idą przez `$this->l()`. Formularz aktualizacji używa źródła `updatesChecker`. Język dodaje się plikiem `translations/{iso}.php`. Napisy, które nie idą przez `$this->l()`: **Saving the three questions…**, **The FAQ could not reach the shop.** oraz zapasowe **The FAQ could not be saved.** i **Saved.** w `views/js/admin.js`. Kredyt na froncie **Powered by MyFAQ for PrestaShop** jest na stałe w `product.tpl`.

Opisy pól to ciągi `desc` w `renderSettingsForm()` i w `renderUpdateForm()`.

### 6.8 Rozszerzanie

Nadpisz `views/templates/hook/product.tpl` z motywu w `themes/{theme}/modules/myfaqfree/views/templates/hook/product.tpl`. Tak samo `views/css/front.css` i `views/js/front.js`. Szablon nie jest renderowany, gdy produkt nie ma widocznego slotu, więc nadpisanie motywu nie ma wtedy czego drukować.

## 7. Pomoc

Strona modułu: [https://mypresta.eu/](https://mypresta.eu/)

W sprawie tego modułu zaloguj się na konto klienta na [mypresta.eu](https://mypresta.eu), przejdź do kontaktu i wybierz temat **Support for paid modules**. Formularz podaje, że przy tym temacie logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów. Ten moduł jest darmowy, więc gdy nie ma go w tej historii, wpisz w wiadomości **MyFAQ Free**.
