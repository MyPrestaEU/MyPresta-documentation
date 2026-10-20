---
title: "Wyklucz wybrane produkty z darmowej wysyłki - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Wyklucz wybrane produkty z darmowej wysyłki” od MyPresta.eu."
sidebar:
  label: "Wyklucz wybrane produkty z darmowej wysyłki - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Exclude selected products from free shipping na MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-selected-products-from-free-shipping.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/exclude-selected-products-from-free-shipping/)
>
> ---


# Wyklucz wybrane produkty z darmowej wysyłki

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym zdefiniujesz podstawowe zasady wykluczania produktów z darmowej wysyłki.

#### 2.1.1 Ustawienia ogólne

-   **Usuń kod kuponu z darmową wysyłką**

    -   **Co robi to ustawienie:** Ta opcja określa, czy kupon na darmową wysyłkę (reguła koszyka `CartRule`, która przyznaje darmową wysyłkę) powinien zostać usunięty lub unieważniony z koszyka klienta, jeśli w koszyku znajduje się wykluczony produkt.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Jeśli klient zastosuje kupon na darmową wysyłkę, a następnie doda produkt oznaczony do wykluczenia, moduł spróbuje usunąć ten kupon z jego koszyka. Zapewnia to, że nawet z kuponem, darmowa wysyłka nie zostanie przyznana dla wykluczonych przedmiotów.
        -   *Gdy wyłączone (NIE):* Kupony na darmową wysyłkę pozostaną aktywne, nawet jeśli w koszyku znajduje się wykluczony produkt. Oznacza to, że klient nadal mógłby otrzymać darmową wysyłkę za pomocą kuponu, co unieważniłoby wykluczenie produktu przez moduł.
    -   **Zalecana wartość:** **TAK**. Zapewnia to najbardziej spójną kontrolę nad kosztami wysyłki, zapobiegając darmowej wysyłce nawet w przypadku użycia kuponu.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz duże meble, które zawsze wiążą się z kosztami wysyłki. Oferujesz również kupon „FREESHIP” na zamówienia powyżej 100 USD. Jeśli klient doda sofę (produkt wykluczony) i użyje kuponu „FREESHIP”, włączenie tego ustawienia spowoduje usunięcie kuponu, zapewniając, że zapłaci za wysyłkę sofy.
-   **Wyklucz produkty niedostępne w magazynie**

    -   **Co robi to ustawienie:** Ta opcja pozwala automatycznie wykluczyć produkty, które są obecnie niedostępne w magazynie, z kwalifikowania się do darmowej wysyłki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Jeśli produkt jest niedostępny w magazynie i znajduje się w koszyku klienta, a Ty również oznaczyłeś go do wykluczenia, moduł zastosuje swoje zasady. Jest to ogólnie mniej istotne, ponieważ produkty niedostępne w magazynie często i tak nie mogą być zamawiane, ale zapewnia spójność.
        -   *Gdy wyłączone (NIE):* Moduł nie będzie brał pod uwagę statusu magazynowego podczas stosowania swoich zasad wykluczenia.
    -   **Zalecana wartość:** **NIE**. To ustawienie jest często zbędne, ponieważ produkty niedostępne w magazynie zazwyczaj nie mogą być dodane do koszyka ani zamówione. Pozostaw je wyłączone, chyba że masz konkretny powód, aby go użyć (np. zezwalanie na zamówienia wsteczne, gdzie darmowa wysyłka powinna być nadal blokowana).
    -   **Scenariusz / przykład dla sprzedawcy:** Zezwalasz na zamówienia wsteczne dla niektórych przedmiotów. Jeśli przedmiot jest na zamówieniu wstecznym (niedostępny w magazynie) i jest to również duży, ciężki przedmiot, którego nigdy nie wysyłasz za darmo, włączenie tego ustawienia zapewnia, że nawet w przypadku zamówienia wstecznego, przyczynia się on do wyłączenia darmowej wysyłki.

#### 2.1.2 Zasady wykluczenia darmowej wysyłki

-   **Wyłącz darmową wysyłkę dla wybranych produktów**

    -   **Co robi to ustawienie:** To jest podstawowa funkcjonalność. Pozwala określić pojedyncze produkty, które, gdy znajdą się w koszyku, wyłączą darmową wysyłkę.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie szukał konkretnych produktów, które dodałeś do listy wykluczeń. Jeśli którykolwiek z tych produktów znajduje się w koszyku klienta, darmowa wysyłka zostanie wyłączona.
        -   *Gdy wyłączone (NIE):* Żadne pojedyncze produkty nie wyłączą darmowej wysyłki, niezależnie od tego, co znajduje się na liście wykluczeń.
    -   **Zalecana wartość:** **TAK**. Włącz to, aby użyć podstawowej funkcji modułu.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz biżuterię (małą, lekką, zazwyczaj darmowa wysyłka) oraz duże gabloty (ciężkie, drogie w wysyłce). Włączyłbyś to i dodał gabloty do listy wykluczeń.
-   **Wyłącz darmową wysyłkę dla wybranych kategorii**

    -   **Co robi to ustawienie:** Podobnie jak w przypadku produktów, ta opcja pozwala wybrać całe kategorie produktów. Jeśli *jakikolwiek* produkt z wybranej kategorii znajduje się w koszyku klienta, darmowa wysyłka zostanie wyłączona.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł sprawdzi, czy jakikolwiek produkt w koszyku należy do jednej z kategorii wybranych do wykluczenia. Jeśli tak, darmowa wysyłka zostanie wyłączona.
        -   *Gdy wyłączone (NIE):* Żadne kategorie nie wyłączą darmowej wysyłki.
    -   **Zalecana wartość:** **TAK**, jeśli masz całe grupy produktów, które nigdy nie powinny kwalifikować się do darmowej wysyłki.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz zarówno książki, jak i duże wydruki artystyczne. Wszystkie wydruki artystyczne wymagają specjalnego opakowania i wysyłki. Włączyłbyś to i wybrał kategorię „Wydruki artystyczne”. Każdy wydruk artystyczny w koszyku wyłączy darmową wysyłkę.

#### 2.1.3 Interfejs wyboru produktów i kategorii

Poniżej tych ustawień znajdziesz dwie sekcje:

-   **Produkty do wykluczenia z darmowej wysyłki:** Pasek wyszukiwania i lista aktualnie wykluczonych produktów.
    -   **Jak używać:** Zacznij wpisywać nazwę produktu w pasku wyszukiwania. W miarę pisania pojawi się lista pasujących produktów. Kliknij na produkt, aby dodać go do listy wykluczeń. Aby usunąć produkt, kliknij „X” obok jego nazwy na liście.
-   **Kategorie do wykluczenia z darmowej wysyłki:** Widok drzewa kategorii Twojego sklepu z polami wyboru.
    -   **Jak używać:** Zaznacz pole obok każdej kategorii, którą chcesz wykluczyć. Wszystkie produkty w tej kategorii (i jej podkategoriach, w zależności od zachowania kategorii w Twojej wersji PrestaShop) wyłączą darmową wysyłkę, jeśli znajdą się w koszyku.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja modułu | Usuń kod kuponu z darmową wysyłką | TAK | Zapewnia usunięcie kuponów na darmową wysyłkę, jeśli w koszyku znajdują się wykluczone produkty. |
| Główna konfiguracja modułu | Wyklucz produkty niedostępne w magazynie | NIE | Zazwyczaj niepotrzebne, ponieważ produkty niedostępne w magazynie często nie mogą być zamawiane. |
| Główna konfiguracja modułu | Wyłącz darmową wysyłkę dla wybranych produktów | TAK | Aktywuje wykluczenie darmowej wysyłki dla konkretnych produktów. |
| Główna konfiguracja modułu | Wyłącz darmową wysyłkę dla wybranych kategorii | TAK | Aktywuje wykluczenie darmowej wysyłki dla konkretnych kategorii. |
| Główna konfiguracja modułu | Produkty do wykluczenia z darmowej wysyłki | (Puste) | Dodaj tutaj konkretne produkty za pomocą narzędzia wyszukiwania. |
| Główna konfiguracja modułu | Kategorie do wykluczenia z darmowej wysyłki | (Brak wybranych) | Wybierz kategorie z widoku drzewa. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale darmowa wysyłka nadal jest wyświetlana dla wykluczonego produktu. Co jest nie tak?**
O:

1.  **Sprawdź swoje ustawienia:** Upewnij się, że opcja „Wyłącz darmową wysyłkę dla wybranych produktów” (lub kategorii) jest włączona i że konkretny produkt/kategoria jest poprawnie dodany do listy wykluczeń.
2.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami PrestaShop buforuje obliczenia wysyłki.
3.  **Testuj z nowym koszykiem:** Upewnij się, że testujesz z nowym koszykiem, ponieważ pamięć podręczna przeglądarki lub dane sesji mogą zakłócać działanie. Spróbuj w oknie incognito.
4.  **Konflikt kuponów:** Jeśli używasz kuponu na darmową wysyłkę, upewnij się, że opcja „Usuń kod kuponu z darmową wysyłką” jest włączona.

**P: Czy ten moduł wpływa na moje standardowe stawki wysyłki?**
O: Nie, ten moduł wpływa tylko na *dostępność* opcji „Darmowa wysyłka” (poprzez reguły koszyka lub konkretnych przewoźników oferujących darmową wysyłkę). Nie modyfikuje on Twoich standardowych stawek wysyłki ani innych konfiguracji przewoźników. Jeśli darmowa wysyłka jest wyłączona, klienci po prostu zobaczą i zapłacą za Twoje regularne opcje wysyłki.

**P: Czy mogę wykluczyć produkty na podstawie wagi lub wymiarów zamiast konkretnych produktów/kategorii?**
O: Ten moduł dotyczy konkretnie produktów i kategorii. Wbudowane zasady wysyłki PrestaShop pozwalają definiować progi darmowej wysyłki na podstawie całkowitej wagi koszyka lub ceny. Ten moduł dodaje warstwę *wyjątków* do tych zasad. Jeśli potrzebujesz bardziej złożonych zasad opartych wyłącznie na wadze/wymiarach dla *wszystkich* produktów, możesz potrzebować bardziej zaawansowanego modułu wysyłki lub niestandardowych konfiguracji przewoźników.

**P: Co się stanie, jeśli klient ma w koszyku produkt wykluczony i produkt niewykluczony?**
O: Jeśli *jakikolwiek* produkt w koszyku znajduje się na Twojej liście wykluczeń (bezpośrednio lub poprzez swoją kategorię), darmowa wysyłka zostanie wyłączona dla całego koszyka, nawet jeśli inne produkty w koszyku normalnie by się kwalifikowały. Logika modułu brzmi: „jeśli jakikolwiek wykluczony produkt jest obecny, to brak darmowej wysyłki”.

**P: Używam niestandardowego motywu, a narzędzie wyszukiwania produktów nie działa poprawnie.**
O: Niestandardowe motywy mogą czasami zakłócać działanie JavaScript.

1.  **Sprawdź błędy JavaScript:** Otwórz konsolę programisty w przeglądarce (zazwyczaj F12) i poszukaj błędów w zakładce „Konsola”, gdy próbujesz użyć narzędzia wyszukiwania.
2.  **Kompatybilność motywu:** Upewnij się, że Twój motyw jest w pełni kompatybilny z Twoją wersją PrestaShop.
3.  **Skontaktuj się z pomocą techniczną:** Jeśli widzisz błędy lub problem nadal występuje, dostarcz zrzuty ekranu i logi konsoli do wsparcia MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Wyklucz wybrane produkty z darmowej wysyłki” działa głównie poprzez nadpisywanie podstawowych klas PrestaShop związanych z zarządzaniem koszykiem i regułami koszyka. Pozwala to na przechwytywanie logiki obliczania darmowej wysyłki i stosowanie reguł wykluczenia przed przedstawieniem klientowi ostatecznych opcji wysyłki. Wykorzystuje system nadpisywania PrestaShop dla klas `CartController`, `Cart` i `CartRule`. Moduł zawiera również dedykowany kontroler administracyjny do wyszukiwania i zarządzania wykluczonymi produktami/kategoriami.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `exfreeshipping/override/controllers/front/CartController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CartController` (nadpisuje `CartControllerCore`)
        -   **Odpowiedzialność**: To nadpisanie jest kluczowe dla przechwytywania działań związanych z koszykiem, w szczególności, gdy produkty są dodawane lub usuwane, lub gdy wykonywane są obliczenia wysyłki. Zapewnia, że logika modułu jest stosowana za każdym razem, gdy zmienia się stan koszyka, wpływając na kwalifikowalność do darmowej wysyłki.
-   **Kontrolery administracyjne Back-Office**:

    -   `exfreeshipping/controllers/admin/AdminExfreeshippingSearchController.php`
        -   **Nazwa zakładki i zarządzana encja**: Ten kontroler obsługuje funkcjonalność wyszukiwania AJAX dla produktów w konfiguracji modułu. Nie zarządza bezpośrednio konkretnym `ObjectModel`, ale dostarcza dane dla listy wykluczeń produktów.
        -   **Cel**: Odpowiada na żądania AJAX ze strony konfiguracji modułu w celu wyszukiwania produktów według nazwy, umożliwiając administratorowi łatwe wybieranie produktów do wykluczenia.
    -   `exfreeshipping/controllers/admin/index.php`
        -   **Cel**: Jest to standardowy pusty plik `index.php` często dołączany do katalogów, aby zapobiec listowaniu katalogów na serwerach WWW. Nie zawiera żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `exfreeshipping/override/classes/Cart.php`

    -   **Nazwa klasy i klasa nadrzędna**: `Cart` (nadpisuje `CartCore`)
    -   **Tabela bazy danych**: `ps_cart`
    -   **Odpowiedzialność**: To nadpisanie jest centralne dla funkcjonalności modułu. Prawdopodobnie modyfikuje metody związane z obliczaniem kosztów wysyłki lub kwalifikowalnością do darmowej wysyłki w obiekcie `Cart`. Będzie zawierać logikę sprawdzającą, czy jakikolwiek produkt w koszyku (lub jego kategoria) znajduje się na liście wykluczeń i, jeśli tak, wyłącza flagę darmowej wysyłki dla tego koszyka.
    -   **Kluczowe metody (prawdopodobnie zmodyfikowane/rozszerzone)**: `getProducts()`, `getPackageList()`, `getWsShippingCost()`, `getShippingCost()` lub podobne metody, które określają kwalifikowalność do wysyłki.
-   `exfreeshipping/override/classes/CartRule.php`

    -   **Nazwa klasy i klasa nadrzędna**: `CartRule` (nadpisuje `CartRuleCore`)
    -   **Tabela bazy danych**: `ps_cart_rule`
    -   **Odpowiedzialność**: To nadpisanie jest odpowiedzialne za obsługę ustawienia „Usuń kod kuponu z darmową wysyłką”. Modyfikuje metody związane z zastosowaniem lub walidacją reguł koszyka w celu usunięcia kuponów na darmową wysyłkę, jeśli w koszyku znajduje się wykluczony produkt.
    -   **Kluczowe metody (prawdopodobnie zmodyfikowane/rozszerzone)**: `checkValidity()`, `addCartRule()`, `removeCartRule()` lub podobne metody, które wchodzą w interakcje z regułami koszyka i ich ważnością.
-   `exfreeshipping/override/classes/index.php`

    -   **Cel**: Podobnie jak `index.php` w katalogu admin, jest to pusty plik zapobiegający listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `exfreeshipping/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres**: Back-office (strona konfiguracji modułu).
    -   **Funkcjonalność**: Ten skrypt zasila interfejs wyszukiwania i wyboru produktów na stronie konfiguracji modułu.
    -   **Szczegóły**:
        -   Inicjalizuje pole wprowadzania autouzupełniania do wyszukiwania produktów.
        -   Wiąże słuchaczy zdarzeń (np. `keyup`, `change`, `click`) z polem wyszukiwania i listą wyników.
        -   Wysyła żądania AJAX do `AdminExfreeshippingSearchController` w celu pobrania sugestii produktów na podstawie danych wprowadzonych przez użytkownika.
        -   Obsługuje wyświetlanie wyników wyszukiwania i pozwala administratorom wybierać produkty, dodając je do ukrytego pola wprowadzania lub widocznej listy wykluczonych produktów.
        -   Zarządza usuwaniem wybranych produktów z listy wykluczeń.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `exfreeshipping/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres**: Back-office (strona konfiguracji modułu).
    -   **Stylizacja**: Zapewnia stylizację dla pola wprowadzania autouzupełniania wyszukiwania produktów, rozwijanej listy wyników wyszukiwania i wyświetlania wybranych wykluczonych produktów na stronie konfiguracji modułu.
    -   **Kluczowe selektory**: Prawdopodobnie zawiera style dla `.autocomplete-input`, `.autocomplete-results`, `.selected-product-tag` itp. Programiści mogą je nadpisać w swoich niestandardowych motywach administracyjnych, jeśli zajdzie taka potrzeba.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `exfreeshipping/lib/searchTool/views/scripts.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie dołączany w metodzie `getContent()` modułu w celu renderowania niezbędnej struktury HTML dla narzędzia wyszukiwania produktów, w tym pola wprowadzania wyszukiwania i obszaru, w którym wyświetlane są wybrane produkty. Prawdopodobnie zawiera również tag `<script>` do ładowania `autocomplete.js`.
    -   `exfreeshipping/views/tpl/selectedProducts.tpl`
        -   **Cel**: Ten szablon służy do renderowania listy produktów, które zostały wybrane do wykluczenia z darmowej wysyłki. Jest dynamicznie aktualizowany przez JavaScript, gdy produkty są dodawane lub usuwane.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `exfreeshipping_oos`, `exfreeshipping_vcode`, `exfreeshipping_visibility_rule`, `exfreeshipping_visibility_products`, `exfreeshipping_visibility_cat`.
    -   Listy wykluczonych produktów i kategorii są przechowywane jako serializowane tablice lub ciągi znaków oddzielone przecinkami w `ps_configuration` pod `exfreeshipping_visibility_products` i `exfreeshipping_visibility_cat` odpowiednio.
-   **Tabela zarejestrowanych hooków**:
    Moduł wykorzystuje głównie nadpisywanie, a nie bezpośrednie wywołania hooków dla swojej podstawowej logiki. Może jednak rejestrować niektóre standardowe hooki do celów inicjalizacji lub konkretnego wyświetlania.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje media (CSS/JS). | Potencjalnie używany do ładowania dowolnych CSS/JS specyficznych dla front-office, chociaż główny wpływ modułu to logika backendowa. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Może być używany do początkowej konfiguracji lub ładowania bardzo lekkich skryptów/stylów, jeśli to konieczne, ale nie bezpośrednio do podstawowej logiki. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony back-office. | Używany do ładowania `autocomplete.js` i `autocomplete.css` dla strony konfiguracji modułu. |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka. | To tutaj podstawowa logika modułu do sprawdzania wykluczonych produktów i wyłączania darmowej wysyłki byłaby wyzwalana lub ponownie oceniana. |
| `actionValidateOrder` | Gdy zamówienie jest walidowane. | Zapewnia prawidłowe zastosowanie zasad darmowej wysyłki na końcowym etapie realizacji zamówienia. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i wsparcie techniczne dla modułu „Wyklucz wybrane produkty z darmowej wysyłki”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
