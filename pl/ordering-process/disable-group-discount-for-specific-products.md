---
title: "Wyłącz rabat grupowy dla wybranych produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Wyłącz rabat grupowy dla wybranych produktów” od MyPresta.eu."
sidebar:
  label: "Wyłącz rabat grupowy dla wybranych produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable group discount for specific products na MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-for-specific-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/disable-group-discount-for-specific-products/)
>
> ---


# Wyłącz rabat grupowy dla wybranych produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Wyłącz rabat grupowy dla wybranych produktów”. Znajdziesz tutaj wszystkie ustawienia, aby kontrolować, które produkty są wykluczone z rabatów grupowych.

**Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > „Wyłącz rabat grupowy dla wybranych produktów” > Konfiguruj

#### 2.1.1 Sekcja „Wyłącz rabaty grupowe dla wybranych produktów”

Ta sekcja zawiera podstawowe ustawienia dotyczące włączania lub wyłączania funkcjonalności modułu oraz definiowania, które produkty są objęte.

-   **Ustawienie: Przełącznik Włączony / Wyłączony**

    -   **Co robi to ustawienie:** Jest to główny przełącznik modułu. Określa, czy logika modułu do wyłączania rabatów grupowych jest aktywna, czy nieaktywna.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł aktywnie sprawdzi, czy produkt lub jego kategoria znajduje się w Twoich regułach wykluczenia. Jeśli tak, wszelkie rabaty grupowe zostaną zignorowane dla tego produktu.
        -   *Gdy wyłączony:* Moduł nie będzie ingerował w domyślne obliczenia rabatów grupowych PrestaShop. Wszystkie produkty będą podlegać rabatom grupowym, jeśli mają zastosowanie.
    -   **Zalecana wartość:** „Włączony”, jeśli zamierzasz korzystać z funkcjonalności modułu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy lub wykonujesz konserwację, włączysz go. Jeśli tymczasowo chcesz, aby wszystkie rabaty grupowe miały zastosowanie bez odinstalowywania modułu, wyłączysz go.
-   **Ustawienie: Kategorie (Pole wyboru)**

    -   **Co robi to ustawienie:** Pozwala wybrać całe kategorie produktów, których produkty powinny być wykluczone z rabatów grupowych. Każdy produkt należący do wybranej kategorii nie otrzyma rabatów grupowych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrano kategorie:* Wszystkie produkty w wybranych kategoriach (i ich podkategoriach, w zależności od struktury kategorii PrestaShop i sposobu przypisywania produktów) będą miały wyłączone rabaty grupowe.
        -   *Gdy nie wybrano kategorii:* Produkty nie są wykluczane na podstawie ich kategorii.
    -   **Zalecana wartość:** Wybierz kategorie, które zawierają produkty, które chcesz wykluczyć z rabatów grupowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz elektronikę. Twoja kategoria „Nowości” często zawiera produkty o wysokim popycie. Chcesz mieć pewność, że nawet Twoi klienci hurtowi płacą pełną cenę za te nowe produkty przez pierwszy miesiąc. Wybierzesz tutaj kategorię „Nowości”.
-   **Ustawienie: Konkretne produkty (Wyszukiwanie i pole wyboru)**

    -   **Co robi to ustawienie:** Pozwala wyszukiwać i wybierać pojedyncze produkty, które powinny być wykluczone z rabatów grupowych. Zapewnia to bardziej szczegółową kontrolę niż kategorie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrano konkretne produkty:* Tylko wyraźnie wybrane produkty będą miały wyłączone rabaty grupowe, niezależnie od ich kategorii.
        -   *Gdy nie wybrano konkretnych produktów:* Produkty nie są wykluczane na podstawie indywidualnego wyboru.
    -   **Zalecana wartość:** Wybierz konkretne produkty, które chcesz wykluczyć z rabatów grupowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz limitowaną edycję wydruku artystycznego (ID produktu 123) i specjalną ofertę pakietową (ID produktu 456), których nigdy nie chcesz przeceniać dla żadnej grupy klientów. Wyszukasz i dodasz „Wydruk artystyczny (edycja limitowana)” i „Specjalna oferta pakietowa” do tej listy.

#### 2.1.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włączony / Wyłączony | Włączony | Główny przełącznik do aktywacji/dezaktywacji funkcjonalności modułu. |
| Konfiguracja modułu | Kategorie | Wybierz odpowiednie kategorie | Wyklucz wszystkie produkty w wybranych kategoriach z rabatów grupowych. |
| Konfiguracja modułu | Konkretne produkty | Wybierz odpowiednie produkty | Wyklucz indywidualnie wybrane produkty z rabatów grupowych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem moduł, ale rabaty grupowe nadal mają zastosowanie do moich wykluczonych produktów. Co jest nie tak?**
O:

-   **Czy moduł jest włączony?** Sprawdź dwukrotnie przełącznik „Włączony / Wyłączony” na stronie konfiguracji modułu. Musi być ustawiony na „Włączony”.
-   **Czy zapisałeś zmiany?** Zawsze kliknij przycisk „Zapisz” po wprowadzeniu jakichkolwiek zmian w konfiguracji.
-   **Wyczyść pamięć podręczną PrestaShop:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
-   **Sprawdź przypisanie produktu/kategorii:** Upewnij się, że produkt jest prawidłowo przypisany do kategorii, którą wykluczyłeś, lub że wybrałeś dokładnie ten produkt, który zamierzasz wykluczyć.
-   **Sprawdź inne moduły:** Inny moduł cenowy lub rabatowy może powodować konflikt. Spróbuj tymczasowo wyłączyć inne moduły związane z rabatami, aby sprawdzić, czy problem zostanie rozwiązany.

**P2: Czy ten moduł wpłynie na moje regularne reguły cen katalogowych lub ceny specyficzne?**
O: Nie, ten moduł dotyczy *rabatów grupowych*. Nie ingeruje w reguły cen katalogowych, ceny specyficzne ustawione dla poszczególnych produktów ani reguły koszyka (kupony). Zapobiega jedynie dodatkowemu rabatowi procentowemu stosowanemu na podstawie grupy klienta.

**P3: Jak ten moduł obsługuje produkty w wielu kategoriach?**
O: Jeśli produkt znajduje się w wielu kategoriach, a *którakolwiek* z tych kategorii jest wybrana do wykluczenia w module, produkt zostanie wykluczony z rabatów grupowych. Moduł sprawdza, czy produkt *należy* do wykluczonej kategorii.

**P4: Używam niestandardowego motywu. Czy ten moduł będzie działał poprawnie?**
O: Tak, ten moduł działa na podstawowym poziomie obliczania cen i nie wprowadza żadnych nowych elementów front-office ani złożonych stylów, które zazwyczaj kolidowałyby z motywami. Powinien być w pełni kompatybilny z każdym motywem PrestaShop.

**P5: Czy mogę wykluczyć produkty dla *niektórych* grup, ale nie dla innych?**
O: Nie, ten moduł wyłącza rabaty grupowe dla wybranych produktów/kategorii *dla wszystkich grup klientów*. Jeśli produkt znajduje się na liście wykluczeń, żadna grupa klientów nie otrzyma na niego rabatu. Podstawowa funkcjonalność PrestaShop pozwala ustawiać rabaty grupowe dla każdej grupy, ale ten moduł działa jako nadpisanie dla konkretnych produktów, czyniąc je zwolnionymi z *jakichkolwiek* rabatów grupowych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzyć moduł „Wyłącz rabat grupowy dla wybranych produktów”.

### 4.1 Przegląd architektury

Moduł działa głównie poprzez nadpisanie podstawowej klasy PrestaShop (`Product.php`) w celu modyfikacji logiki obliczania ceny. Wpina się w metodę `Product::getPriceStatic()`, która jest kluczowa dla sposobu, w jaki PrestaShop określa ostateczną cenę produktu. Gdy ta metoda jest wywoływana, moduł sprawdza, czy bieżący produkt lub jego powiązane kategorie są skonfigurowane do wykluczenia z rabatów grupowych. Jeśli tak, zapewnia, że komponent rabatu grupowego w obliczeniach ceny zostanie pominięty.

Moduł wykorzystuje standardową klasę `Module` PrestaShop dla swojego interfejsu konfiguracyjnego i opiera się na wpisach w tabeli `Configuration` do przechowywania swoich ustawień. Zawiera również proste narzędzie wyszukiwania do wyboru produktów w panelu administracyjnym.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego logika jest głównie zaimplementowana poprzez nadpisanie klasy i metodę `getContent()` głównego pliku modułu do konfiguracji.

### 4.3 Podstawowe klasy i modele (`classes/`)

-   **`exgdisc/override/classes/Product.php`**
    -   **Odpowiedzialność:** Jest to najważniejszy plik w module. Nadpisuje podstawową klasę `Product` w celu modyfikacji metody `getPriceStatic()`.
    -   **Nazwa klasy:** `Product` (nadpisuje oryginalną klasę `Product`)
    -   **Klasa nadrzędna:** `ProductCore`
    -   **Kluczowa logika:**
        -   Nadpisana metoda `getPriceStatic()` najpierw wywołuje `getPriceStatic()` klasy nadrzędnej, aby uzyskać cenę bazową.
        -   Następnie pobiera konfigurację modułu (`exgdisc_categories`, `exgdisc_products`) z `Configuration::get()`.
        -   Sprawdza, czy ID bieżącego produktu (`$id_product`) znajduje się na liście `exgdisc_products`.
        -   Sprawdza również, czy którakolwiek z kategorii powiązanych z `$id_product` znajduje się na liście `exgdisc_categories`.
        -   Jeśli którykolwiek z warunków jest prawdziwy, oznacza to, że produkt powinien być wykluczony z rabatów grupowych. Metoda następnie ponownie oblicza cenę, skutecznie ignorując komponent rabatu grupowego, który normalnie byłby stosowany przez metodę `getPriceStatic()` klasy nadrzędnej.
        -   Oryginalna metoda `Product::getPriceStatic()` ma parametr `$use_group_reduction`. Nadpisanie zapewnia, że nawet jeśli jest on `true`, redukcja grupowa nie jest stosowana, jeśli produkt jest wykluczony przez moduł.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`exgdisc/lib/searchTool/views/js/autocomplete.js`**
    -   **Zakres:** Panel administracyjny (używany na stronie konfiguracji modułu).
    -   **Cel:** Zapewnia funkcjonalność autouzupełniania do wyboru konkretnych produktów w formularzu konfiguracji modułu.
    -   **Kluczowa logika:**
        -   Inicjalizuje pole wejściowe autouzupełniania (prawdopodobnie celując w element o określonym ID, np. `#product_autocomplete_input`).
        -   Wysyła żądania AJAX do kontrolera administracyjnego PrestaShop (np. `AdminProducts` lub niestandardowego kontrolera wyszukiwania) w celu pobrania sugestii produktów na podstawie danych wprowadzonych przez użytkownika.
        -   Obsługuje wybór produktów, dodając je do ukrytego pola wejściowego lub wizualnej listy na stronie konfiguracji.
        -   Zarządza usuwaniem wybranych produktów z listy.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`exgdisc/lib/searchTool/views/css/autocomplete.css`**
    -   **Zakres:** Panel administracyjny (stylizuje narzędzie wyszukiwania autouzupełniania).
    -   **Cel:** Zapewnia stylizację dla pola wyszukiwania produktów i listy wybranych produktów na stronie konfiguracji modułu.
    -   **Kluczowe selektory:** Prawdopodobnie zawiera style dla rozwijanej listy autouzupełniania, znaczników/plakietek wybranych elementów i ewentualnie samego pola wejściowego wyszukiwania. Programiści mogą nadpisać te klasy w swoich niestandardowych motywach administracyjnych, jeśli zajdzie taka potrzeba.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`exgdisc/lib/searchTool/views/scripts.tpl`**

    -   **Zakres:** Panel administracyjny (zawarty na stronie konfiguracji modułu).
    -   **Cel:** Renderuje strukturę HTML dla pola wyszukiwania produktów i obszaru, w którym wyświetlane są wybrane produkty. Prawdopodobnie zawiera również niezbędne wywołania JavaScript do inicjalizacji skryptu `autocomplete.js`.
    -   **Kluczowe elementy:** Pole wejściowe do wyszukiwania produktów, kontener do wyświetlania wybranych produktów (np. jako tagi lub elementy listy) oraz ukryte pola wejściowe do przechowywania identyfikatorów wybranych produktów.
-   **`exgdisc/views/script.tpl`**

    -   **Zakres:** Panel administracyjny (zawarty na stronie konfiguracji modułu).
    -   **Cel:** Ten szablon jest prawdopodobnie używany do wyprowadzania dodatkowego kodu JavaScript lub CSS, który jest specyficzny dla głównego formularza konfiguracji modułu, potencjalnie związanego z walidacją formularza lub dynamicznymi elementami interfejsu użytkownika. Biorąc pod uwagę hook `ActionAdminControllerSetMedia`, może być używany do rejestrowania zasobów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`:
        -   `exgdisc_categories`: Przechowuje serializowany ciąg znaków lub listę identyfikatorów kategorii oddzielonych przecinkami do wykluczenia.
        -   `exgdisc_products`: Przechowuje serializowany ciąg znaków lub listę identyfikatorów produktów oddzielonych przecinkami do wykluczenia.
        -   `mypresta_updates`, `update_`, `updatev_`: Związane z mechanizmem aktualizacji MyPresta.eu.
        -   `exgdisc_groups`: (Nie jest wyraźnie używane w dostarczonych informacjach, ale może być starszym lub przyszłym ustawieniem dla wykluczeń specyficznych dla grup).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny jest ładowany, a jego media (JS/CSS) są ustawiane. | Używany przez moduł do ładowania jego JavaScript (`autocomplete.js`) i CSS (`autocomplete.css`) dla panelu administracyjnego na stronie konfiguracji, zapewniając działanie narzędzia wyszukiwania produktów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Wyłącz rabat grupowy dla wybranych produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnego funkcjonowania modułu z Twoim sklepem PrestaShop.
