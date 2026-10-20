---
title: "Cart conditions pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Cart conditions pro od MyPresta.eu."
sidebar:
  label: "Cart conditions pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cart conditions pro na MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/cart-conditions-pro/)
>
> ---


# Cart conditions pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Cart conditions pro)

Jest to główny ekran konfiguracji modułu, na którym ustawiasz globalne zachowania i uzyskujesz dostęp do specyficznych obszarów zarządzania warunkami.

-   **Co robi to ustawienie:** Kontroluje ogólne zachowanie modułu i zapewnia szybkie linki do zarządzania warunkami.
-   **Wpływ zmiany tego ustawienia:** Określa, jak szeroko stosowane są warunki i jak obsługiwane są niektóre przypadki brzegowe.

#### Ustawienia ogólne

1.  **Wyklucz klientów z warunków**

    -   **Co robi to ustawienie:** Pozwala określić pewne grupy klientów lub pojedynczych klientów, którzy będą zwolnieni z wszelkich ustawionych warunków koszyka.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone (i wybrani klienci/grupy):* Wybrani klienci/grupy zawsze będą mogli przejść do kasy, niezależnie od tego, czy ich koszyk spełnia warunki.
        -   *Gdy wyłączone (lub brak wybranych klientów/grup):* Wszyscy klienci będą podlegać warunkom koszyka.
    -   **Zalecana wartość:** Domyślnie „Wyłączone”, chyba że masz konkretnych klientów B2B lub VIP-ów, których chcesz zwolnić.
    -   **Scenariusz/przykład sprzedawcy:** Masz grupę klientów hurtowych, która zawsze otrzymuje specjalne traktowanie i nie powinna być ograniczana minimalnymi wartościami zamówień.
2.  **Wyklucz produkty z warunków**

    -   **Co robi to ustawienie:** Pozwala określić pewne produkty, które nie będą wliczane do ani nie będą objęte żadnymi warunkami koszyka. Jest to przydatne dla darmowych prezentów, próbek lub specyficznych produktów promocyjnych.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone (i wybrane produkty):* Wybrane produkty zostaną zignorowane podczas oceny warunków koszyka. Na przykład, jeśli masz warunek „minimum 3 produkty”, a klient ma 2 zwykłe produkty + 1 wykluczony produkt, warunek może nadal nie zostać spełniony.
        -   *Gdy wyłączone (lub brak wybranych produktów):* Wszystkie produkty w koszyku zostaną uwzględnione podczas oceny warunków.
    -   **Zalecana wartość:** Domyślnie „Wyłączone”. Włącz tylko, jeśli masz konkretne produkty, które powinny być zwolnione z warunków.
    -   **Scenariusz/przykład sprzedawcy:** Oferujesz darmową próbkę produktu do każdego zamówienia. Nie chcesz, aby ta próbka wliczała się do warunku minimalnej ilości produktów.
3.  **Blokuj zamówienia produktów z różnymi datami dostępności**

    -   **Co robi to ustawienie:** Ta opcja dotyczy konkretnie produktów, które mają różne daty dostępności (np. produkty w przedsprzedaży z rozłożonymi datami premiery). Jeśli włączona, zapobiega zamawianiu przez klientów mieszanki produktów dostępnych od razu i produktów dostępnych w przyszłości w tym samym koszyku.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy „Włączone”:* Jeśli koszyk klienta zawiera produkty z różnymi datami dostępności, zostanie zablokowany przed przejściem do kasy. Musieliby złożyć oddzielne zamówienia na produkty z różnymi datami dostępności.
        -   *Gdy „Wyłączone”:* Klienci mogą zamawiać produkty z różnymi datami dostępności w jednym koszyku.
    -   **Zalecana wartość:** „Wyłączone”, chyba że masz konkretne powody logistyczne, aby rozdzielać zamówienia na podstawie dostępności.
    -   **Scenariusz/przykład sprzedawcy:** Sprzedajesz zarówno produkty dostępne w magazynie, jak i produkty w przedsprzedaży. Aby uprościć wysyłkę i uniknąć wstrzymywania zamówień, chcesz, aby klienci składali oddzielne zamówienia na produkty w przedsprzedaży.

#### Linki do zarządzania warunkami

Poniżej ustawień ogólnych znajdziesz linki do zarządzania różnymi typami warunków. Te linki przeniosą Cię do dedykowanych ekranów administracyjnych.

-   **Zarządzaj warunkami (Ogólne):** Tutaj definiujesz ogólne warunki oparte na powiązaniach produktów, kategoriach lub innych ogólnych zasadach.
-   **Zarządzaj warunkami dla krajów:** Definiuj warunki, które mają zastosowanie tylko do klientów z określonych krajów.
-   **Zarządzaj warunkami ilościowymi:** Ustaw minimalne lub maksymalne ilości produktów/kategorii wymagane w koszyku.
-   **Zarządzaj warunkami wartościowymi:** Ustaw minimalne lub maksymalne całkowite wartości koszyka.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminCartConditionController (Panel administracyjny > Moduły > Cart conditions pro > Zarządzaj warunkami)

Ten ekran pozwala definiować ogólne warunki, często oparte na powiązaniach produktów lub kategorii.

-   **Nazwa ekranu i lokalizacja w menu:** „Zarządzaj warunkami” (dostępne z głównej strony konfiguracji modułu).
-   **Dostępne działania i ustawienia:**
    -   **Tabela listująca:** Wyświetla wszystkie istniejące ogólne warunki wraz z ich nazwami, powiązanymi produktami/kategoriami i statusem.
    -   **Przycisk Dodaj nowy warunek:** Pozwala utworzyć nowy warunek.
        -   **Nazwa warunku:** Opisowa nazwa do wewnętrznego odniesienia.
        -   **Produkty/Kategorie:** Wybierz konkretne produkty lub całe kategorie, które muszą być obecne (lub nieobecne) w koszyku.
        -   **Grupy klientów:** Zastosuj ten warunek tylko do określonych grup klientów.
        -   **Minimalna/Maksymalna ilość:** Zdefiniuj zakres dla liczby wybranych produktów/kategorii.
        -   **Minimalna/Maksymalna wartość:** Zdefiniuj zakres dla całkowitej wartości wybranych produktów/kategorii.
        -   **Wiadomość:** Wiadomość wyświetlana klientowi, jeśli warunek nie jest spełniony.
        -   **Aktywny:** Włącz lub wyłącz warunek.
    -   **Przyciski Edytuj/Usuń:** Modyfikuj lub usuwaj istniejące warunki.
-   **Wpływ zmian:**
    -   Dodanie nowego warunku natychmiast stosuje tę regułę do koszyków klientów.
    -   Modyfikacja warunku aktualizuje jego kryteria i wiadomość.
    -   Usunięcie warunku usuwa ograniczenie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie przeglądaj swoje warunki, zwłaszcza po dodaniu nowych produktów, kategorii lub uruchomieniu promocji, aby upewnić się, że są zgodne z Twoją aktualną strategią sprzedaży.

#### 2.2.2 AdminCartAssociationsConditionController (Panel administracyjny > Moduły > Cart conditions pro > Zarządzaj warunkami > (Konkretny warunek) > Powiązania)

Ten ekran jest zazwyczaj dostępny podczas edycji ogólnego warunku i pozwala określić, które produkty lub kategorie są *powiązane* z tym warunkiem.

-   **Nazwa ekranu i lokalizacja w menu:** Dostępne poprzez edycję warunku z „Zarządzaj warunkami”.
-   **Dostępne działania i ustawienia:**
    -   **Wyszukaj i wybierz produkty/kategorie:** Narzędzia do znajdowania i dodawania konkretnych produktów lub całych kategorii, które są częścią tego warunku.
    -   **Lista wybranych produktów/kategorii:** Pokazuje wszystkie elementy aktualnie powiązane z warunkiem.
    -   **Przycisk Usuń:** Usuń element z powiązania.
-   **Wpływ zmian:** Bezpośrednio wpływa na to, które produkty lub kategorie są oceniane przez warunek nadrzędny. Na przykład, jeśli warunek mówi „Koszyk musi zawierać co najmniej 2 produkty z kategorii ‘Elektronika’”, ten ekran jest miejscem, w którym definiujesz, które produkty należą do tej kategorii „Elektronika” dla tego konkretnego warunku.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Podczas tworzenia lub aktualizowania warunku upewnij się, że wszystkie odpowiednie produkty i kategorie są prawidłowo powiązane.

#### 2.2.3 AdminCartCountryConditionController (Panel administracyjny > Moduły > Cart conditions pro > Zarządzaj warunkami dla krajów)

Ten ekran pozwala definiować warunki, które są specyficzne dla kraju wysyłki klienta.

-   **Nazwa ekranu i lokalizacja w menu:** „Zarządzaj warunkami dla krajów” (dostępne z głównej strony konfiguracji modułu).
-   **Dostępne działania i ustawienia:**
    -   **Tabela listująca:** Wyświetla istniejące warunki specyficzne dla kraju.
    -   **Przycisk Dodaj nowy warunek:**
        -   **Kraj:** Wybierz kraj docelowy.
        -   **Minimalna/Maksymalna ilość:** Dla wszystkich produktów w koszyku lub konkretnych produktów/kategorii.
        -   **Minimalna/Maksymalna wartość:** Dla całkowitej wartości koszyka.
        -   **Wiadomość:** Wiadomość wyświetlana, jeśli warunek nie jest spełniony.
        -   **Aktywny:** Włącz lub wyłącz.
-   **Wpływ zmian:** Stosuje specyficzne reguły koszyka tylko do klientów, których adres wysyłki znajduje się w wybranym kraju.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Przydatne dla sklepów międzynarodowych z różnymi kosztami wysyłki, przepisami celnymi lub strategiami rynkowymi dla poszczególnych krajów.

#### 2.2.4 AdminCartQuantityConditionController (Panel administracyjny > Moduły > Cart conditions pro > Zarządzaj warunkami ilościowymi)

Ten ekran koncentruje się na warunkach związanych z całkowitą liczbą produktów w koszyku lub ilością konkretnych produktów/kategorii.

-   **Nazwa ekranu i lokalizacja w menu:** „Zarządzaj warunkami ilościowymi” (dostępne z głównej strony konfiguracji modułu).
-   **Dostępne działania i ustawienia:**
    -   **Tabela listująca:** Pokazuje wszystkie warunki oparte na ilości.
    -   **Przycisk Dodaj nowy warunek:**
        -   **Nazwa warunku:**
        -   **Minimalna/Maksymalna całkowita ilość:** Dla całego koszyka.
        -   **Minimalna/Maksymalna ilość konkretnych produktów/kategorii:** Wybierz produkty i ustaw dla nich reguły ilościowe.
        -   **Grupy klientów:** Zastosuj do konkretnych grup.
        -   **Wiadomość:**
        -   **Aktywny:**
-   **Wpływ zmian:** Wymusza reguły oparte na liczbie produktów w koszyku, co może być użyte do zachęcania do zakupów hurtowych lub zarządzania zapasami.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego do promocji „kup X, otrzymaj Y”, minimalnej ilości zamówienia (MOQ) dla hurtu lub zapewnienia, że klienci spełniają określony próg dla darmowej wysyłki.

#### 2.2.5 AdminCartValueConditionController (Panel administracyjny > Moduły > Cart conditions pro > Zarządzaj warunkami wartościowymi)

Ten ekran służy do ustawiania warunków opartych na całkowitej wartości pieniężnej koszyka klienta.

-   **Nazwa ekranu i lokalizacja w menu:** „Zarządzaj warunkami wartościowymi” (dostępne z głównej strony konfiguracji modułu).
-   **Dostępne działania i ustawienia:**
    -   **Tabela listująca:** Wyświetla istniejące warunki oparte na wartości.
    -   **Przycisk Dodaj nowy warunek:**
        -   **Nazwa warunku:**
        -   **Minimalna/Maksymalna całkowita wartość koszyka:** Ustaw zakres dla wartości całego koszyka.
        -   **Grupy klientów:**
        -   **Wiadomość:**
        -   **Aktywny:**
-   **Wpływ zmian:** Wymusza reguły oparte na wartości pieniężnej koszyka, bezpośrednio wpływając na średnią wartość zamówienia.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Idealne do ustawiania minimalnej wartości zamówienia dla darmowej wysyłki lub ogólnej minimalnej wartości zamówienia w celu zapewnienia rentowności.

#### 2.2.6 index.php (cartcon/controllers/admin/index.php)

Ten plik jest standardową praktyką PrestaShop, aby zapobiec listowaniu katalogów i nie reprezentuje konfigurowalnego ekranu. Zawiera po prostu `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` w celu przekierowania, jeśli ktoś spróbuje bezpośrednio uzyskać dostęp do katalogu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Wyklucz klientów z warunków | Wyłączone | Zwolnij konkretnych klientów/grupy ze wszystkich warunków. |
| | Wyklucz produkty z warunków | Wyłączone | Zwolnij konkretne produkty ze wszystkich warunków. |
| | Blokuj zamówienia produktów z różnymi datami dostępności | Wyłączone | Zapobiegaj mieszanym zamówieniom produktów dostępnych w magazynie i w przedsprzedaży. |
| **Zarządzaj warunkami** | Nazwa warunku | Zdefiniowane przez użytkownika | Wewnętrzna etykieta warunku. |
| | Produkty/Kategorie | Zdefiniowane przez użytkownika | Wybierz wymagane lub ograniczone produkty/kategorie. |
| | Grupy klientów | Wszystkie | Zastosuj warunek do konkretnych segmentów klientów. |
| | Min/Max Ilość | Zdefiniowane przez użytkownika | Ustaw zakres ilości dla wybranych produktów/kategorii. |
| | Min/Max Wartość | Zdefiniowane przez użytkownika | Ustaw zakres wartości dla wybranych produktów/kategorii. |
| | Wiadomość | Zdefiniowane przez użytkownika | Wiadomość dla klienta, gdy warunek nie jest spełniony. |
| | Aktywny | Tak | Włącz/wyłącz warunek. |
| **Zarządzaj warunkami dla krajów** | Kraj | Zdefiniowane przez użytkownika | Celuj w konkretne kraje dla warunków. |
| | Min/Max Ilość | Zdefiniowane przez użytkownika | Zakres ilości dla koszyków z wybranego kraju. |
| | Min/Max Wartość | Zdefiniowane przez użytkownika | Zakres wartości dla koszyków z wybranego kraju. |
| | Wiadomość | Zdefiniowane przez użytkownika | Wiadomość dla klienta w przypadku niepowodzenia specyficznego dla kraju. |
| | Aktywny | Tak | Włącz/wyłącz warunek dla kraju. |
| **Zarządzaj warunkami ilościowymi** | Nazwa warunku | Zdefiniowane przez użytkownika | Wewnętrzna etykieta warunku ilościowego. |
| | Min/Max Całkowita Ilość | Zdefiniowane przez użytkownika | Zakres ilości dla całego koszyka. |
| | Min/Max Ilość konkretnych produktów/kategorii | Zdefiniowane przez użytkownika | Zakres ilości dla wybranych produktów/kategorii. |
| | Grupy klientów | Wszystkie | Zastosuj do konkretnych segmentów klientów. |
| | Wiadomość | Zdefiniowane przez użytkownika | Wiadomość dla klienta w przypadku niepowodzenia ilościowego. |
| | Aktywny | Tak | Włącz/wyłącz warunek ilościowy. |
| **Zarządzaj warunkami wartościowymi** | Nazwa warunku | Zdefiniowane przez użytkownika | Wewnętrzna etykieta warunku wartościowego. |
| | Min/Max Całkowita Wartość Koszyka | Zdefiniowane przez użytkownika | Zakres wartości dla całego koszyka. |
| | Grupy klientów | Wszystkie | Zastosuj do konkretnych segmentów klientów. |
| | Wiadomość | Zdefiniowane przez użytkownika | Wiadomość dla klienta w przypadku niepowodzenia wartościowego. |
| | Aktywny | Tak | Włącz/wyłącz warunek wartościowy. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje warunki są ustawione, ale wydaje się, że nie działają w front office. Co jest nie tak?**
**O1:**

-   **Sprawdź status warunku:** Upewnij się, że przełącznik „Aktywny” dla każdego ustawionego warunku jest ustawiony na „Tak”.
-   **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
-   **Pozycja modułu:** Sprawdź, czy moduł jest poprawnie podpięty. Haki `displayShoppingCart` i `displayPaymentTop` są kluczowe. Jeśli Twój motyw ma niestandardowe haki, może być potrzebna pomoc programisty.
-   **Grupy klientów:** Sprawdź dwukrotnie, czy warunki są stosowane do właściwych grup klientów i czy Twój klient testowy należy do tej grupy.
-   **ID produktów/kategorii:** Podczas wybierania produktów lub kategorii upewnij się, że wybrałeś właściwe. Czasami podobne nazwy mogą powodować zamieszanie.

**P2: Wyświetlana klientom wiadomość jest niejasna lub nie wygląda dobrze z moim motywem.**
**O2:**

-   **Edytuj wiadomość:** Przejdź do konkretnego warunku (np. Zarządzaj warunkami wartościowymi, a następnie edytuj warunek) i zaktualizuj pole „Wiadomość” na jaśniejszy, bardziej pomocny tekst.
-   **Stylizacja motywu:** Wygląd wizualny (czcionka, kolor, rozmiar) wiadomości jest kontrolowany przez CSS Twojego motywu PrestaShop. Jeśli chcesz zmienić stylizację, musisz skonsultować się z projektantem stron internetowych lub programistą, aby dodać niestandardowe reguły CSS do Twojego motywu. Pliki CSS modułu (`cartcon.css`) zapewniają podstawową stylizację.

**P3: Czy mogę ustawić różne warunki dla różnych języków/krajów?**
**O3:**

-   **Warunki specyficzne dla kraju:** Tak, użyj ekranu „Zarządzaj warunkami dla krajów”, aby ustawić reguły, które mają zastosowanie tylko do klientów z określonych krajów.
-   **Wiadomości wielojęzyczne:** Podczas edycji warunku pole „Wiadomość” zazwyczaj ma selektor języka (ikonę flagi). Kliknij go, aby podać tłumaczenia wiadomości we wszystkich aktywnych językach Twojego sklepu.

**P4: Chcę wykluczyć konkretny produkt ze WSZYSTKICH warunków. Jak to zrobić?**
**O4:**

-   Na głównej stronie konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Cart conditions pro) użyj ustawienia „Wyklucz produkty z warunków”. Możesz wyszukać i wybrać konkretne produkty, które chcesz zwolnić.

**P5: Moduł blokuje realizację zamówienia, ale nie mogę znaleźć, który warunek to powoduje.**
**O5:**

-   **Przejrzyj wszystkie warunki:** Przejdź kolejno przez „Zarządzaj warunkami”, „Zarządzaj warunkami dla krajów”, „Zarządzaj warunkami ilościowymi” i „Zarządzaj warunkami wartościowymi”. Sprawdź status „Aktywny” każdego z nich i przejrzyj ich kryteria.
-   **Testuj systematycznie:** Jeśli masz wiele warunków, spróbuj wyłączać je pojedynczo (lub w grupach) i testować koszyk, aż zidentyfikujesz winowajcę. Następnie włącz je ponownie i dostosuj problematyczny warunek.
-   **Sprawdź grupę klientów:** Upewnij się, że Twój klient testowy nie należy do wykluczonej grupy klientów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Cart conditions pro” stosuje standardowy wzorzec MVC (Model-View-Controller) PrestaShop, głównie rozszerzając `Module` dla swojej głównej konfiguracji i `AdminController` dla dedykowanych interfejsów zarządzania. Wykorzystuje system haków PrestaShop do wstrzykiwania logiki i wyświetlania komunikatów w krytycznych punktach front-office (koszyk, płatność) i używa `ObjectModel` niejawnie do zarządzania różnymi encjami warunków. Moduł opiera się na niestandardowych tabelach bazy danych do przechowywania swoich złożonych reguł warunków.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Moduł nie wydaje się mieć dedykowanych kontrolerów frontowych w dostarczonym inwentarzu. Logika i wyświetlanie w front-office są prawdopodobnie obsługiwane bezpośrednio przez główny plik modułu `cartcon.php` za pośrednictwem wywołań zwrotnych haków.

#### Kontrolery administracyjne Back-Office

Wszystkie kontrolery administracyjne rozszerzają `ModuleAdminController` (lub `AdminController` w starszych wersjach PrestaShop) i są odpowiedzialne za zarządzanie różnymi typami warunków.

-   `cartcon/controllers/admin/AdminCartAssociationsConditionController.php`

    -   **Nazwa klasy:** `AdminCartAssociationsConditionController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza powiązaniami (produktami, kategoriami) połączonymi z konkretnym ogólnym warunkiem koszyka. Ten kontroler zapewnia interfejs do wyszukiwania i wybierania produktów/kategorii, które są częścią kryteriów warunku. Współpracuje z tabelą `cartcon_ass`.
-   `cartcon/controllers/admin/AdminCartConditionController.php`

    -   **Nazwa klasy:** `AdminCartConditionController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza głównymi, ogólnymi warunkami koszyka. Jest to podstawowy interfejs do tworzenia, edytowania i usuwania warunków opartych na obecności produktu/kategorii, ilości lub wartości. Współpracuje z tabelą `cartcon`.
-   `cartcon/controllers/admin/AdminCartCountryConditionController.php`

    -   **Nazwa klasy:** `AdminCartCountryConditionController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza warunkami koszyka specyficznie powiązanymi z krajami klientów. Pozwala definiować reguły, które mają zastosowanie tylko wtedy, gdy kraj wysyłki klienta odpowiada określonemu krajowi. Współpracuje z tabelą `cartcon_country`.
-   `cartcon/controllers/admin/AdminCartQuantityConditionController.php`

    -   **Nazwa klasy:** `AdminCartQuantityConditionController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza warunkami opartymi na całkowitej ilości produktów w koszyku lub ilości konkretnych produktów/kategorii. Współpracuje z tabelą `cartcon_quantity`.
-   `cartcon/controllers/admin/AdminCartValueConditionController.php`

    -   **Nazwa klasy:** `AdminCartValueConditionController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza warunkami opartymi na całkowitej wartości pieniężnej koszyka. Współpracuje z tabelą `cartcon_value`.
-   `cartcon/controllers/admin/index.php`

    -   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający listowaniu katalogów. Przekierowuje do katalogu nadrzędnego.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczony inwentarz nie zawiera jawnych plików w katalogu `classes/`. Sugeruje to, że podstawowa logika modułu i definicje `ObjectModel` (jeśli istnieją) są osadzone w głównym pliku `cartcon.php` lub w samych plikach kontrolerów administracyjnych, co jest powszechnym wzorcem dla prostszych modułów lub starszych wersji PrestaShop. Jeśli używane są `ObjectModel`, ich tablice `$definition` znajdowałyby się w odpowiedniej klasie kontrolera lub głównego modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `cartcon/lib/searchTool/views/js/autocomplete.js`

    -   **Zakres:** Back-office.
    -   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania do wyszukiwania produktów, kategorii lub klientów w formularzach administracyjnych (np. podczas ustawiania wykluczeń lub powiązań warunków). Prawdopodobnie wiąże się z polami wejściowymi, wysyła żądania AJAX do punktu końcowego wyszukiwania i wyświetla sugestie.
-   `cartcon/views/js/cartcon.js`

    -   **Zakres:** Front-office i potencjalnie Back-office.
    -   **Odpowiedzialność:**
        -   **Front-office:** Obsługuje dynamiczne wyświetlanie komunikatów o warunkach koszyka, wyłączanie/włączanie przycisku „Przejdź do kasy” na podstawie odpowiedzi AJAX z serwera dotyczących ważności koszyka. Może nasłuchiwać aktualizacji koszyka (`prestashop.on('updateCart', ...)` lub podobnych zdarzeń), aby ponownie ocenić warunki.
        -   **Back-office:** Może zawierać logikę walidacji formularzy, dynamicznej widoczności pól lub innych ulepszeń interfejsu użytkownika specyficznych dla stron konfiguracji modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `cartcon/lib/searchTool/views/css/autocomplete.css`

    -   **Zakres:** Back-office.
    -   **Odpowiedzialność:** Stylizuje rozwijane listy sugestii autouzupełniania i pola wejściowe wyszukiwania używane w formularzach administracyjnych, zapewniając spójne i przyjazne dla użytkownika doświadczenie wyszukiwania.
-   `cartcon/views/css/cartcon.css`

    -   **Zakres:** Front-office i Back-office.
    -   **Odpowiedzialność:**
        -   **Front-office:** Stylizuje komunikaty powiadomień wyświetlane na stronie koszyka, stronie płatności lub stronie produktu, gdy warunki nie są spełnione. Definiuje wygląd pól ostrzegawczych, tekstu i potencjalnie wyłączonego stanu przycisku realizacji zamówienia.
        -   **Back-office:** Zapewnia stylizację formularzy konfiguracji modułu i tabel list, zapewniając ich dobrą integrację z motywem panelu administracyjnego PrestaShop.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Szukaj klas takich jak `.cartcon-alert`, `.cartcon-message`, `.cartcon-disabled-button` lub podobnych w tym pliku, aby docelowo dostosować wyjście modułu w front-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony haków (`views/templates/hook/`)

Logika wyświetlania modułu w front-office jest prawdopodobnie osadzona bezpośrednio w metodach haków głównego pliku `cartcon.php`, które następnie renderują te szablony.

-   `cartcon/views/templates/front/displayShoppingCart.tpl`

    -   **Renderowany w haku:** `displayShoppingCart`
    -   **Cel:** Wyświetla komunikaty o warunkach koszyka i potencjalnie wyłącza przycisk realizacji zamówienia na głównej stronie koszyka, jeśli warunki nie są spełnione. Otrzymuje zmienne z metody `hookDisplayShoppingCart` modułu, wskazujące ważność koszyka i wiadomość do wyświetlenia.
-   `cartcon/views/templates/front/displayShoppingCartEmpty.tpl`

    -   **Renderowany w haku:** Potencjalnie `displayShoppingCart` lub powiązany hak, gdy koszyk jest pusty.
    -   **Cel:** Zapewnia specyficzny szablon do wyświetlania komunikatów lub alternatywnej zawartości, gdy koszyk jest pusty, potencjalnie związanej z minimalnymi wymaganiami zamówienia.
-   `cartcon/views/templates/front/productActions.tpl`

    -   **Renderowany w haku:** `displayProductActions` (zazwyczaj w pobliżu przycisku „Dodaj do koszyka” na stronie produktu).
    -   **Cel:** Może być używany do wyświetlania subtelnych wskazówek lub ostrzeżeń na samej stronie produktu, jeśli dodanie produktu naruszyłoby warunek koszyka lub jeśli produkt wymaga zakupu innych produktów razem z nim.

#### Szablony administracyjne (`views/templates/admin/`)

-   `cartcon/lib/searchTool/views/scripts.tpl`

    -   **Cel:** Prawdopodobnie zawiera zależności JavaScript lub inicjalizuje skrypty autouzupełniania dla formularzy administracyjnych.
-   `cartcon/views/templates/admin/AdminCartAssociationsCondition.tpl`

    -   **Cel:** Główny szablon dla `AdminCartAssociationsConditionController`, wyświetlający interfejs do zarządzania powiązaniami produktów/kategorii dla warunku. Obejmowałby pola wyszukiwania, listy wybranych elementów i przyciski zapisu.
-   `cartcon/views/templates/admin/adminSearchCustomer.tpl`

    -   **Cel:** Szablon dla interfejsu wyszukiwania klientów, używany podczas wykluczania klientów z warunków.
-   `cartcon/views/templates/admin/script.tpl`

    -   **Cel:** Ogólny szablon skryptu administracyjnego, potencjalnie zawierający specyficzny dla modułu JavaScript lub zmienne konfiguracyjne dla back office.
-   `cartcon/views/templates/admin/search-attribute-value-result.tpl`

    -   **Cel:** Szablon do wyświetlania wyników wyszukiwania atrybutów/wartości w panelu administracyjnym, prawdopodobnie używany w połączeniu z wyszukiwaniem produktów.
-   `cartcon/views/templates/admin/search-attribute-value.tpl`

    -   **Cel:** Szablon dla pola wejściowego wyszukiwania i powiązanych elementów interfejsu użytkownika do wyszukiwania atrybutów/wartości produktów w panelu administracyjnym.
-   `cartcon/views/templates/admin/selectedProducts.tpl`

    -   **Cel:** Szablon do wyświetlania listy produktów, które zostały wybrane i powiązane z konkretnym warunkiem w formularzach administracyjnych.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

Moduł tworzy niestandardowe tabele do przechowywania różnych warunków i powiązań. Tabele te są zazwyczaj poprzedzone prefiksem `ps_cartcon_` lub `cartcon_`.

-   `ps_cartcon`: Przechowuje ogólne warunki koszyka (nazwa, wiadomość, status aktywności itp.).
-   `ps_cartcon_ass`: Przechowuje powiązania między warunkami a konkretnymi produktami/kategoriami.
-   `ps_cartcon_country`: Przechowuje warunki specyficzne dla kraju.
-   `ps_cartcon_quantity`: Przechowuje warunki oparte na ilości.
-   `ps_cartcon_value`: Przechowuje warunki oparte na wartości.
-   `ps_configuration`: Ustawienia modułu, takie jak `CARTCON_CUSTOMERS`, `ccon_visibility_rule`, `CARTCON_FUTURE` itp., są przechowywane tutaj.

#### Tabela zarejestrowanych haków

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do ładowania zasobów CSS i JavaScript modułu zarówno dla front-office, jak i back-office. |
| `displayPaymentTop` | Na górze strony wyboru płatności podczas realizacji zamówienia. | Kluczowy do ponownej oceny warunków koszyka tuż przed płatnością i blokowania w razie potrzeby. |
| `displayShoppingCart` | Na głównej stronie koszyka zakupowego. | Główny hak do wyświetlania komunikatów o warunkach i wyłączania przycisku realizacji zamówienia. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany i ustawiane są jego media (JS/CSS). | Służy do ładowania specyficznych zasobów JS/CSS dla stron konfiguracji modułu w back-office. |
| `displayProductActions` | Zazwyczaj w pobliżu przycisku „Dodaj do koszyka” na stronie produktu. | Może być używany do wyświetlania wskazówek lub ostrzeżeń dotyczących warunków specyficznych dla produktu. |
| `actionCartSave` | Po zapisaniu koszyka (np. dodaniu/usunięciu produktu, zmianie ilości). | (Niejawne/Prawdopodobne) Moduł prawdopodobnie używałby haka `actionCartSave` lub podobnego, aby wywołać ponowną ocenę warunków koszyka po stronie serwera, co następnie informuje JS w front-office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Cart conditions pro”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół dokłada wszelkich starań, aby moduł działał optymalnie z Twoim sklepem PrestaShop.
