---
title: "Metody płatności dla produktów - dokumentacja i instrukcja sprzedawcy"
description: "Instrukcja ustawienia metod płatności przy produkcie, łączenia ich w koszyku i naprawy listy płatności, która nadal pokazuje złą metodę."
sidebar:
  label: "Metody płatności dla produktów - dokumentacja i instrukcja sprzedawcy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Payment methods by products na MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/payment-methods-by-products/)
>
> ---


## 1. Wymagania

Sprawdź to przed instalacją.

- PrestaShop 1.7.0.0 lub nowszy, także PrestaShop 8 i 9. Moduł przyjmuje wersje sklepu do 9.99.99.
- Zostaw wersję PHP wymaganą przez tę wersję PrestaShop. Instalator nie sprawdza PHP osobno.
- Włącz rozszerzenie PHP cURL, jeśli sprawdzanie aktualizacji ma łączyć się z MyPresta.eu. Gdy cURL nie ma, sprawdzenie próbuje otworzyć adres ustawieniem serwera do odczytu zdalnych stron. Same reguły płatności cURL nie potrzebują.
- Żaden inny moduł PrestaShop nie jest wymagany. Lista metod powstaje z modułów płatności już zainstalowanych w sklepie. Gdy nie ma żadnego, pola wyboru są puste.
- Zainstaluj i włącz co najmniej jeden moduł płatności, jeśli metoda ma być widoczna przy kasie.
- Moduł nie wymaga konta w zewnętrznym serwisie.

## 2. Instalacja

1. Otwórz **Moduły**, potem **Menedżer modułów**.
2. Kliknij **Załaduj moduł** i wgraj plik ZIP.
3. Kliknij **Zainstaluj** przy **Metody płatności dla produktów**.

Instalacja robi tyle:

- Dodaje **Produkt - Płatność - Powiązania** w **Ulepszenia**, potem **Płatność**. Gdy menu Płatność nie istnieje, pozycja trafia pod **Ulepszenia**.
- Tworzy tabelę: jeden wiersz to produkt, moduł płatności, sklep i kraj.
- Rejestruje filtr kasy i zakładkę na karcie produktu.
- Kopiuje nadpisanie kasy. PrestaShop musi pozwalać na nadpisania. Gdy są wyłączone, zakładka produktu i filtr kasy i tak działają. Żółte ostrzeżenie na stronie konfiguracji o tym mówi.
- Nie czyści pamięci podręcznej sklepu. Wyczyść ją w **Zaawansowane**, **Wydajność**, tylko gdy stary ekran zostaje na stronie.
- Nie tworzy żadnej reguły. Kasa zostaje bez zmian, dopóki nie zapiszesz reguły.

**Konfiguruj** w **Menedżerze modułów** otwiera ustawienia. Pozycja **Produkt - Płatność - Powiązania** otwiera listę reguł.

Odinstalowanie:

- Usuwa pozycję menu **Produkt - Płatność - Powiązania**.
- Usuwa nadpisanie kasy i zarejestrowane hooki.
- Usuwa zapisaną wersję modułu używaną przy aktualizacji.
- Nie kasuje zapisanych reguł produktów. Kolejna instalacja czyta te wiersze znowu.
- Nie wyłącza powiadomień o aktualizacjach wspólnych dla innych modułów MyPresta.
- Zostawia katalog modułu, dopóki nie usuniesz go w **Menedżerze modułów** albo z serwera.

Wyłączenie modułu w **Menedżerze modułów** zatrzymuje filtr kasy. Zapisane reguły zostają w bazie.

## 3. Konfiguracja i praca w zapleczu

Reguła to lista metod płatności dla jednego produktu, w sklepie, który edytujesz, dla jednego kraju dostawy albo dla wszystkich krajów.

Kolejność pracy:

1. Otwórz **Konfiguruj** i wybierz, jak łączyć kilka ograniczonych produktów w jednym koszyku. Kliknij **Zapisz**. Ten krok jest opcjonalny. Zanim zapiszesz, sklep zostawia każdą metodę dozwoloną przez co najmniej jeden ograniczony produkt.
2. Otwórz produkt i zakładkę **Metody płatności** albo **Ulepszenia**, **Płatność**, **Produkt - Płatność - Powiązania** i dodaj wiersz.
3. Zaznacz metody, które mają zostać, gdy ten produkt jest w koszyku. Wybierz **Wszystkie kraje** albo jeden kraj. Zapisz.
4. Przy kasie sklep czyta adres dostawy i chowa metody, których reguły nie dopuszczają.

Produkt bez zapisanej reguły nie usuwa metod płatności. **Darmowe zamówienie** zostaje, gdy jest jedyną metodą przy koszyku za zero.

W tym module nie ma statusu zamówienia. Wynikiem jest lista płatności na stronie kasy.

Zrzuty w tym rozdziale pokazują angielskie zaplecze. Podpisy używają nazw z tej instrukcji.

### 3.1 Konfiguracja modułu

Otwórz **Moduły**, **Menedżer modułów**, **Metody płatności dla produktów**, **Konfiguruj**.

Na górze są dwie informacje. Pierwszy link otwiera **Produkt - Płatność - Powiązania**. Drugi mówi, że to samo ustawisz na karcie produktu, w zakładce **Metody płatności**. Żadna z nich nie zapisuje reguły.

Gdy nadpisania są wyłączone, żółte ostrzeżenie mówi: „Override są wyłączone. Filtrowanie płatności w kasie nadal działa przez hook opcji płatności.” Zostaw nadpisania wyłączone, jeśli używasz tylko PrestaShop 8 lub 9. Włącz je w **Zaawansowane**, **Wydajność**, tylko gdy potrzebujesz też starszego nadpisania kasy.

Panel **Ustawienia** opisuje regułę kraju i sposób łączenia metod. Tekst nad listą wyboru to opis modułu. Sam nic nie zapisuje.

![Ustawienia](https://mypresta.eu/docs/images/docs/pobp-configure-settings.webp)

**Konfiguruj**, panel **Ustawienia**. Niebieski tekst opisuje kraje. Lista to **Jak ustalić metody płatności?**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Jak ustalić metody płatności?** | **Pokaż wszystkie metody płatności z produktów które są w koszyku**, dopóki nie zapiszesz innego wyboru | **Pokaż tylko wspólne metody płatności dla produktów, które są w koszyku** zostawia metodę tylko wtedy, gdy pozwala na nią każdy ograniczony produkt. **Pokaż wszystkie metody płatności z produktów które są w koszyku** zostawia metodę, gdy pozwala na nią co najmniej jeden ograniczony produkt. Produkt bez zapisanej reguły nie usuwa metod. |
| **Zapisz** | — | Zapisuje tylko ten wybór. Nie edytuje reguły produktu. Strona wraca z zaznaczoną wartością. |

### 3.2 Produkt - Płatność - Powiązania

Otwórz **Ulepszenia**, **Płatność**, **Produkt - Płatność - Powiązania**. Notka na górze powtarza, że ta sama reguła jest na produkcie, w zakładce **Metody płatności**.

Lista pokazuje jedną linijkę na produkt w bieżącym sklepie.

![Produkt - Płatność - Powiązania](https://mypresta.eu/docs/images/docs/pobp-associations-list.webp)

**Produkt - Płatność - Powiązania** bez wierszy. Kolumny to **ID**, **Produkt**, **Płatność** i **Kraj**. Plus to **Dodaj nowy**.

| Kolumna | Co widać |
|---|---|
| **ID** | Numer wiersza. To nie jest numer produktu. |
| **Produkt** | Numer i nazwa produktu. |
| **Płatność** | Każda metoda zapisana dla tego produktu, jedna pod drugą. |
| **Kraj** | **Wszystkie kraje** albo kraj dostawy zapisany w wierszu. Opis kolumny mówi, że wybrany kraj działa tylko przy adresie dostawy w tym kraju, a **Wszystkie kraje** działają przy każdym adresie. |

**Dodaj nowy** otwiera pusty formularz. **Edytuj** otwiera formularz tego produktu. **Usuń** kasuje ten jeden wiersz bazy, nie każdą metodę wypisaną w kolumnie **Płatność**. **Usuń wybrane** robi to samo dla zaznaczonych linii. Tu nie da się zdjąć całej reguły przez odznaczenie wszystkiego: formularz odrzuca pusty zapis. Skasuj pozostałe wiersze albo wyczyść regułę na karcie produktu, gdzie puste zaznaczenie jest dozwolone.

Wyszukiwanie i filtry listy to standardowe filtry zaplecza dla tych kolumn.

### 3.3 Formularz powiązania

Na **Dodaj nowy** albo **Edytuj**:

![Formularz powiązania](https://mypresta.eu/docs/images/docs/pobp-associations-form.webp)

**Dodaj nowy**, wypełniony na potrzeby zdjęcia i niezapisany. **ID produktu** to 1. Na formularzu są **Metody płatności** i **Kraj** (**Wszystkie kraje**).

| Pole | Na starcie | Co robi |
|---|---|---|
| **ID produktu** | Puste na nowym wierszu. Wypełnione przy edycji. | Wpisz numer produktu albo użyj **Wyszukaj**, żeby go uzupełnić. Podpowiedź mówi, żeby szukać po nazwie, ID albo referencji. **Zapisz** bez produktu pokazuje „Produkt jest wymagany.” i nie zapisuje reguły. |
| **Metody płatności** | Odznaczone na nowym wierszu. Przy edycji zaznaczone są metody już zapisane dla tego produktu. | Zaznacz metody, które zostają przy kasie, gdy koszyk zawiera ten produkt, a kraj dostawy zgadza się z krajem poniżej. Etykieta pokazuje nazwę modułu płatności. |
| **Kraj** | **Wszystkie kraje** | Jeśli wskażesz kraj, zaznaczone metody obowiązują tylko wtedy, gdy adres dostawy klienta jest w tym kraju. **Wszystkie kraje** oznaczają, że metody obowiązują przy każdym adresie dostawy. |
| **Zapisz** | — | Zamienia wszystkie metody zapisane dla tego produktu w bieżącym sklepie na zaznaczenia i kraj z tego formularza. Gdy nic nie jest zaznaczone, strona pokazuje „Problem z zapisem. Żadna metoda płatności nie została wybrana.” i poprzednie wiersze zostają. |

Jeden produkt ma jeden kraj. Kolejny zapis zastępuje poprzednie metody tego produktu w tym sklepie. Reguły w innym sklepie zostają. Przełącz kontekst sklepu, zanim edytujesz tamten sklep.

### 3.4 Karta produktu

Otwórz **Katalog**, **Produkty**, edycję produktu, potem zakładkę **Metody płatności**.

![Metody płatności na karcie produktu](https://mypresta.eu/docs/images/docs/pobp-product-tab.webp)

Produkt Hummingbird printed t-shirt, zakładka **Metody płatności**. Widać **Kraj** i **Dostępne metody płatności**. Zaznaczenia są tylko na zdjęciu. Produkt nie został zapisany.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Kraj** | **Wszystkie kraje**, gdy produkt nie ma reguły. W przeciwnym razie kraj już zapisany. | Jeśli wskażesz kraj, zaznaczone metody płatności obowiązują tylko wtedy, gdy adres dostawy klienta jest w tym kraju. **Wszystkie kraje** oznaczają, że metody obowiązują przy każdym adresie dostawy. |
| **Dostępne metody płatności** | Odznaczone, gdy produkt nie ma reguły. W przeciwnym razie zaznaczone są metody już zapisane. | Zaznaczone metody pozostają dostępne przy kasie, gdy koszyk zawiera ten produkt, a kraj dostawy zgadza się z krajem powyżej. Odznacz wszystkie, aby zdjąć ograniczenie dla tego produktu. |

Kliknij **Zapisz** na produkcie. PrestaShop potwierdza zapis produktu. Reguła płatności zapisuje się razem z nim, dla sklepu, który edytujesz. Puste zaznaczenie kasuje regułę tego produktu w tym sklepie. To różni się od formularza powiązań, który nie zapisze się, gdy nic nie jest zaznaczone.

Te same dane widać na liście **Produkt - Płatność - Powiązania**.

### 3.5 Aktualizacje MyPresta

Na **Konfiguruj**, pod ustawieniami, panel **Aktualizacje MyPresta** sprawdza, czy jest nowszy plik. Nie instaluje go.

![Aktualizacje MyPresta](https://mypresta.eu/docs/images/docs/pobp-updates.webp)

**Aktualizacje MyPresta**, pod ustawieniami na **Konfiguruj**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Sprawdź aktualizacje** | — | **Sprawdź teraz** pyta MyPresta.eu, czy jest nowszy plik. Linia nad przyciskiem pokazuje, że jest nowa wersja, albo że moduł jest aktualny. Nie pobiera i nie instaluje pliku. |
| **Notyfikacje** | Włączone, dopóki nie zapiszesz **Wyłącz** | **Włącz** pokazuje ostrzeżenie w zapleczu, gdy wyjdzie nowsza wersja. **Wyłącz** zatrzymuje to automatyczne sprawdzanie. **Zapisz** zapisuje wybór i pokazuje „Ustawienia aktualizacji zostały zapisane.” |
| **Strona modułu** | — | Otwiera stronę modułu na MyPresta.eu, gdzie jest changelog. Nie zapisuje ustawienia. |
| **Zapisz** | — | Zapisuje tylko **Notyfikacje**. |

## 4. Front sklepu

Moduł nie dodaje bloku, strony ani komunikatu na produkcie, w koszyku ani na koncie klienta. Na tych stronach nie ma czego zmieniać w motywie.

Klient widzi skutek na kroku płatności przy kasie. Metod, których reguły nie dopuszczają, nie ma na liście. Metody bez reguły oraz **Darmowe zamówienie**, gdy jest jedynym wyborem, zostają.

Kraj to kraj adresu dostawy. Zanim adres dostawy istnieje, działają tylko reguły ustawione na **Wszystkie kraje**. Reguła dla jednego kraju czeka, aż adres dostawy będzie w tym kraju.

## 5. Problemy

**Lista płatności się nie zmieniła.** Produkt nie ma zapisanej reguły albo żaden produkt w koszyku jej nie ma. Otwórz produkt, **Metody płatności**, zaznacz metody i zapisz produkt. Produkt bez zaznaczenia nie ogranicza kasy.

**Metoda zniknęła tylko dla jednego kraju.** Kraj reguły to nie **Wszystkie kraje**, a adres dostawy jest w wybranym kraju. Ustaw **Wszystkie kraje**, jeśli reguła ma działać przy każdym adresie dostawy.

**Metoda nadal jest oferowana.** Inny produkt w koszyku ją dopuszcza, a **Jak ustalić metody płatności?** jest ustawione na **Pokaż wszystkie metody płatności z produktów które są w koszyku**. Przełącz na **Pokaż tylko wspólne metody płatności dla produktów, które są w koszyku**, jeśli metoda ma być dozwolona przez każdy ograniczony produkt. Produkt bez reguły jej nie blokuje.

**Na konfiguracji widać „Override są wyłączone…” i nie wiadomo, czy filtr działa.** W PrestaShop 8 i 9 filtr nadal działa. Żółty tekst mówi, że filtrowanie idzie przez hook kasy. Włącz nadpisania tylko wtedy, gdy polegasz też na starszym pliku nadpisania.

**Zapis na Produkt - Płatność - Powiązania pokazuje „Produkt jest wymagany.”** Pole produktu jest puste. Wyszukaj produkt albo wpisz jego numer i kliknij **Zapisz** jeszcze raz.

**Zapis pokazuje „Problem z zapisem. Żadna metoda płatności nie została wybrana.”** Żadna metoda nie jest zaznaczona. Zaznacz co najmniej jedną. Poprzednia reguła nie została podmieniona. Żeby zdjąć regułę całkowicie, użyj zakładki **Metody płatności** na produkcie i zapisz bez zaznaczeń.

**Usuń na liście skasowało tylko jedną metodę.** **Usuń** kasuje pojedynczy wiersz tej linii, a kolumna **Płatność** wypisuje wszystkie metody. Otwórz **Edytuj** i **Zapisz**, żeby zapisać cały zestaw, albo usuwaj, aż produkt zniknie z listy.

**Darmowe zamówienie jest jedyną metodą, a reguła go nie zawiera.** Koszyk za zero zostawia **Darmowe zamówienie**. Moduł nie usuwa tej jedynej metody.

**Reguła zapisana w jednym sklepie nie ma jej w drugim.** Reguły są zapisane osobno dla sklepu. Przełącz sklep w nagłówku multisklepu i zapisz regułę tam.

## 6. Dla developera

### 6.1 Przegląd

Klasa `pobp`, wersja `1.4.0`, nazwa na liście **Metody płatności dla produktów**, autor MyPresta.eu, zakładka `administration`. Zgodność od `1.7.0.0` do `9.99.99`.

Wiersz w `ps_pobp` to jeden dozwolony moduł płatności dla jednego produktu, jednego sklepu i jednego kraju (`id_country` `0` oznacza każdy kraj). Kasa czyta produkty koszyka i adres dostawy w `pobp::filterPaymentOptions()`. Hook `actionPresentPaymentOptions` usuwa klucze modułów, które filtr odrzucił. Nadpisanie `PaymentOptionsFinder::find()` zwraca ten sam filtr, gdy moduł jest włączony, więc starsza kasa wołająca `find()`, a nie hook, dostaje tę samą listę. `pobp_innerjoin` ustawione na prawdę oznacza część wspólną ograniczonych produktów. Każda inna wartość, także brak klucza, oznacza sumę. Produkty bez pasujących wierszy są pomijane. Klucz `free_order` nigdy nie jest usuwany, a lista zawierająca tylko `free_order` wraca bez zmian.

### 6.2 Pliki

| Plik | Rola |
|---|---|
| `pobp.php` | Instalacja, formularz ustawień, filtr kasy, zakładka produktu. |
| `lib/updatesChecker.php` | Klasa `pobpUpdate`. Sprawdzanie aktualizacji i formularz Aktualizacje MyPresta. |
| `lib/searchTool/searchTool.php` | Wyszukiwanie produktu na formularzu powiązań. |
| `models/pob.php` | ObjectModel `pob` i `replaceForProduct()`. |
| `controllers/admin/AdminPobpController.php` | Lista i formularz powiązań. |
| `override/classes/checkout/PaymentOptionsFinder.php` | `find()` woła `filterPaymentOptions()`. |
| `upgrade/upgrade-1.4.0.php` | Woła `ensureModuleComplements()` i zapisuje `POBP_VERSION`. |
| `translations/pl.php` | Polskie napisy. |

Nie ma kontrolera frontu ani szablonu frontu.

### 6.3 Kontrolery

`AdminPobpController` rozszerza `ModuleAdminController`. Klasa zakładki `AdminPobp`, rodzic `AdminParentPayment`, albo `IMPROVE`, gdy tego rodzica nie ma. Ikona `credit_card`. Nazwa **Produkt - Płatność - Powiązania**.

Lista grupuje podzapytaniem `MIN(id_pobp)` na produkt i sklep, więc widać jedną linię. `processAdd()` i `processUpdate()` wołają `pob::replaceForProduct()`. Pusty zestaw metod albo brak produktu zwraca false i nie podmienia wierszy. Napisy idą przez `$this->module->l(..., 'AdminPobpController')`.

Konfiguracja modułu to `getContent()` w `pobp`, nie osobny kontroler.

### 6.4 Hooki

Rejestruje je `registerHooks()`:

| Hook | Rola |
|---|---|
| `actionPresentPaymentOptions` | Usuwa moduły płatności odrzucone przez filtr. Tablica jest zmieniana w miejscu. |
| `actionProductFormBuilderModifier` | Dodaje zakładkę `pobp` (kraj i płatności) na formularzu produktu. |
| `actionAfterUpdateProductFormHandler` | Zapisuje `form_data['pobp']` dla zapisanego produktu. |
| `actionAfterCreateProductFormHandler` | Ten sam zapis po utworzeniu produktu. |

Nie ma własnych `enable()` ani `disable()`. Wyłączenie modułu wyrejestrowuje hooki. Nadpisanie nadal się ładuje i zwraca listę rodzica, gdy `Module::isEnabled('pobp')` jest fałszem.

Pierwsze wejście do zaplecza po wgraniu plików woła `ensureModuleComplements()`, gdy `POBP_VERSION` różni się od wersji w pliku. To odświeża tabelę, hooki, menu i nadpisanie.

### 6.5 Nadpisania

`override/classes/checkout/PaymentOptionsFinder.php` podmienia tylko `find()`. Nie nadpisuje `present()` ani `findFree()`.

### 6.6 Baza

| Tabela | Zawartość |
|---|---|
| `ps_pobp` | `id_pobp`, `id_product`, `id_payment` (id modułu), `id_shop`, `id_country`. Kolumnę `id_country` dopisuje `inconsistency()`, gdy jej nie ma. `0` oznacza każdy kraj. |

Odinstalowanie nie kasuje `ps_pobp`. Instalacja używa `CREATE TABLE IF NOT EXISTS`, więc nowa instalacja zostawia stare wiersze.

### 6.7 Klucze i tłumaczenia

| Klucz | Gdy go nie ma |
|---|---|
| `pobp_innerjoin` | Traktowany jako wyłączony. Kasa używa sumy ograniczonych produktów. |
| `POBP_VERSION` | Następne żądanie zaplecza uruchamia `ensureModuleComplements()` i potem zapisuje wersję z pliku. |
| `mypresta_updates` | Traktowany jako włączony. Ustaw `0`, żeby zatrzymać automatyczne sprawdzanie. Klucz jest wspólny z innymi modułami MyPresta. |
| `update_pobp` | Czas ostatniego sprawdzenia. |
| `updatev_pobp` | Wersja zwrócona przez serwer aktualizacji. |

Napisy sklepu idą przez `$this->l()`. Panel aktualizacji używa źródła `updatesChecker`. Kontroler powiązań używa źródła `AdminPobpController`. Polski jest w `translations/pl.php`. Kolejny język dodaj jako `translations/{iso}.php` z tym samym kształtem klucza.

`key.php` w katalogu modułu może ustawić `$this->mkey`. Gdy pliku nie ma, sprawdzenie aktualizacji wysyła `nlc`.

### 6.8 Rozszerzanie

Front nie renderuje szablonu modułu, więc motyw nie ma czego nadpisać dla tego modułu. Żeby zmienić listę kasy, zostań przy hooku opcji płatności albo nadpisaniu `PaymentOptionsFinder`. Żeby zmienić zakładkę produktu, rozszerz `hookActionProductFormBuilderModifier` i zostaw klucze formularza `pobp`, inaczej hook zapisu pominie dane.

## 7. Pomoc

Strona modułu: [https://mypresta.eu/modules/payment-process/payment-methods-by-products.html](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)

W sprawie tego modułu zaloguj się na konto klienta na mypresta.eu, otwórz kontakt i wybierz temat **Support for paid modules**. Formularz podaje, że przy tym temacie logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
