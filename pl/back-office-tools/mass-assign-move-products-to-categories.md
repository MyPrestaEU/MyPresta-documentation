---
title: "Masowe przypisywanie / przenoszenie produktów do kategorii - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Masowe przypisywanie / przenoszenie produktów do kategorii” od MyPresta.eu."
sidebar:
  label: "Masowe przypisywanie / przenoszenie produktów do kategorii - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Mass assign / move products to categories na MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-assign-move-products-to-categories.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/mass-assign-move-products-to-categories/)
>
> ---


# Masowe przypisywanie / przenoszenie produktów do kategorii

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Masowe przypisywanie / przenoszenie produktów do kategorii” zapewnia interfejs przypominający kreator, który prowadzi Cię przez proces masowego zarządzania kategoriami produktów.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj „Masowe przypisywanie / przenoszenie produktów do kategorii”)

Po kliknięciu „Konfiguruj” zostaniesz przeniesiony na główną stronę konfiguracji modułu, która działa jak kreator krok po kroku.

#### Krok 1: Wybierz produkty do zarządzania

Ta sekcja pozwala zdefiniować, które produkty chcesz zmodyfikować.

-   **Co robi to ustawienie:** To pierwszy kluczowy krok, w którym identyfikujesz grupę produktów, które zostaną objęte masową akcją.
-   **Efekt zmiany tego ustawienia:** Wybrane tutaj produkty będą jedynymi przetwarzanymi w kolejnych krokach.
-   **Zalecana wartość:** Użyj paska wyszukiwania, aby znaleźć produkty po nazwie. Możesz dodać wiele produktów do listy.
-   **Scenariusz / przykład dla sprzedawcy:**
    -   *Scenariusz 1: Konkretne produkty:* Chcesz przenieść „Produkt A”, „Produkt B” i „Produkt C” do nowej kategorii. Wyszukujesz każdy produkt i dodajesz go do listy.
    -   *Scenariusz 2: Produkty z istniejącej kategorii:* Chcesz przenieść wszystkie produkty znajdujące się obecnie w kategorii „Stara Kolekcja” do nowej kategorii „Archiwalne Przedmioty”. Najpierw wybierasz tutaj wszystkie produkty ze „Starej Kolekcji”.

#### Krok 2: Wybierz kategorie, do których przypisać/przenieść produkty

Ta sekcja pozwala wybrać docelowe kategorie dla wybranych produktów.

-   **Co robi to ustawienie:** Tutaj określasz kategorie, do których produkty z Kroku 1 zostaną przypisane lub przeniesione.
-   **Efekt zmiany tego ustawienia:** Wybrane produkty zostaną połączone z tymi kategoriami.
-   **Zalecana wartość:** Użyj drzewa kategorii, aby wybrać jedną lub więcej kategorii docelowych.
-   **Scenariusz / przykład dla sprzedawcy:**
    -   *Scenariusz 1: Przypisz do nowej kategorii:* W Kroku 1 wybrano 5 produktów. Teraz wybierasz tutaj „Nowości” i „Bestsellery”. 5 produktów zostanie przypisanych zarówno do „Nowości”, jak i „Bestsellerów”.
    -   *Scenariusz 2: Przenieś do jednej kategorii:* Wybrano 10 produktów. Wybierasz tutaj „Wyprzedaż Sezonowa”. W zależności od wyboru w Kroku 3, te produkty zostaną albo dodane do „Wyprzedaży Sezonowej”, albo przeniesione wyłącznie do niej.

#### Krok 3: Co zrobić z wybranymi produktami?

To najważniejszy krok, określający charakter masowej akcji.

-   **Co robi to ustawienie:** Ten wybór przycisku radiowego decyduje, czy produkty są *przypisywane* (dodawane do nowych kategorii przy zachowaniu istniejących) czy *przenoszone* (usuwane z istniejących kategorii i umieszczane tylko w nowych).
-   **Efekt zmiany tego ustawienia:**
    -   **Przypisz produkty do wybranych kategorii:**
        -   *Po wybraniu:* Produkty wybrane w Kroku 1 zostaną *dodane* do kategorii wybranych w Kroku 2. Zachowają wszystkie swoje obecne przypisania do kategorii. Jest to przydatne do krzyżowego listowania produktów lub dodawania ich do kategorii promocyjnych bez zakłócania ich głównego umiejscowienia.
        -   *Scenariusz dla sprzedawcy:* Masz produkt w „Elektronice” i „Gadżetach”. Chcesz dodać go do „Ofert Świątecznych” bez usuwania go z „Elektroniki” lub „Gadżetów”. Wybierasz „Przypisz”.
    -   **Przenieś produkty do wybranych kategorii (usuń z bieżących kategorii):**
        -   *Po wybraniu:* Produkty wybrane w Kroku 1 zostaną *usunięte* ze wszystkich kategorii, do których są obecnie przypisane, a następnie *tylko* przypisane do kategorii wybranych w Kroku 2. Jest to całkowita rekategoryzacja.
        -   *Scenariusz dla sprzedawcy:* Masz produkt w „Starej Kolekcji” i „Wycofanych Przedmiotach”. Chcesz, aby pojawiał się *tylko* w „Produktach Archiwalnych”. Wybierasz „Przenieś”.
-   **Zalecana wartość:** Zależy to całkowicie od Twojego konkretnego celu. Starannie rozważ, czy chcesz *dodać* kategorie, czy je *zastąpić*.
-   **Scenariusz / przykład dla sprzedawcy:**
    -   *Przypisz:* Prowadzisz wyprzedaż „Black Friday”. Wybierasz wszystkie produkty objęte wyprzedażą i „Przypisujesz” je do kategorii „Oferty Black Friday”. Nadal pojawiają się w swoich oryginalnych kategoriach (np. „T-shirty”, „Laptopy”), ale teraz także w „Ofertach Black Friday”.
    -   *Przenieś:* Zdecydowałeś się zreorganizować sekcję „Odzież Damska”. Wybierasz wszystkie produkty z „Sukienek” i „Spódnic” i „Przenosisz” je do nowej kategorii „Damskie doły i sukienki”. Nie będą już pojawiać się w starych kategoriach „Sukienki” ani „Spódnice”.

#### Przycisk „Wykonaj”

-   **Co robi to ustawienie:** Ten przycisk inicjuje operację masową na podstawie Twoich wyborów w poprzednich krokach.
-   **Efekt zmiany tego ustawienia:** Po kliknięciu moduł przetworzy wszystkie wybrane produkty zgodnie z wybraną akcją (przypisz lub przenieś) i kategoriami docelowymi. Zazwyczaj pojawi się komunikat potwierdzający lub o sukcesie.
-   **Zalecana wartość:** Kliknij to tylko wtedy, gdy jesteś absolutnie pewien swoich wyborów.
-   **Scenariusz / przykład dla sprzedawcy:** Po dokładnym przejrzeniu wybranych produktów i kategorii oraz potwierdzeniu pożądanej akcji (przypisz lub przenieś), kliknij „Wykonaj”, aby zastosować zmiany w katalogu produktów Twojego sklepu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | **Krok 1: Wybierz produkty** | N/A (wprowadzane przez użytkownika) | Definiuje konkretne produkty, które zostaną objęte masową akcją. |
| Główna konfiguracja | **Krok 2: Wybierz kategorie** | N/A (wprowadzane przez użytkownika) | Definiuje docelowe kategorie, do których produkty zostaną przypisane lub przeniesione. |
| Główna konfiguracja | **Krok 3: Co zrobić?** | N/A (wybór użytkownika) | **Przypisz:** Dodaje produkty do nowych kategorii, zachowując istniejące. **Przenieś:** Usuwa ze wszystkich bieżących kategorii, przypisuje tylko do nowych. |
| Główna konfiguracja | **Przycisk Wykonaj** | N/A (akcja użytkownika) | Uruchamia masową operację przypisywania/przenoszenia kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Kliknąłem „Wykonaj”, ale nic się nie stało lub nie widzę zmian.**
O:

1.  **Wyczyść pamięć podręczną:** Po każdej znaczącej zmianie w PrestaShop, zwłaszcza przypisaniach kategorii lub produktów, zawsze należy wyczyścić pamięć podręczną sklepu. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
2.  **Sprawdź status produktu:** Upewnij się, że produkty, które próbujesz przypisać/przenieść, są aktywne i widoczne.
3.  **Sprawdź status kategorii:** Upewnij się, że kategorie docelowe są aktywne i widoczne.
4.  **Ponownie uruchom moduł:** Wróć do modułu, ponownie wybierz swoje produkty i kategorie i spróbuj ponownie.

**P: Moje produkty zniknęły z ich oryginalnych kategorii po użyciu modułu!**
O: Prawdopodobnie oznacza to, że w Kroku 3 wybrano opcję „Przenieś produkty do wybranych kategorii (usuń z bieżących kategorii)”. Ta opcja ma na celu *zastąpienie* istniejących przypisań kategorii nowymi. Jeśli było to niezamierzone, będziesz musiał ręcznie ponownie przypisać produkty do ich oryginalnych kategorii lub ponownie użyć modułu z opcją „Przypisz produkty”, aby je przywrócić. Zawsze dokładnie sprawdzaj Krok 3 przed wykonaniem!

**P: Czy mogę cofnąć masowe przypisanie/przeniesienie?**
O: Moduł nie ma przycisku „cofnij”. Dlatego tak ważne jest, aby **zawsze tworzyć kopię zapasową bazy danych przed wykonaniem jakichkolwiek masowych działań** w Twoim sklepie. Jeśli popełniłeś błąd, przywrócenie kopii zapasowej jest najbezpieczniejszym sposobem na cofnięcie zmian. W przeciwnym razie będziesz musiał ręcznie poprawić przypisania kategorii lub ponownie użyć modułu, aby ponownie przypisać produkty w razie potrzeby.

**P: Wyszukiwanie produktów nie znajduje moich produktów.**
O:

1.  **Sprawdź pisownię:** Upewnij się, że poprawnie wpisujesz nazwę produktu.
2.  **Status produktu:** Upewnij się, że produkt jest aktywny w Twoim katalogu.
3.  **Wyczyść pamięć podręczną przeglądarki:** Czasami pamięć podręczna przeglądarki może zakłócać funkcje wyszukiwania AJAX. Spróbuj wyczyścić pamięć podręczną przeglądarki lub użyć okna incognito.

**P: Czy ten moduł wpływa na domyślną kategorię produktu?**
O: Moduł zarządza przede wszystkim kategoriami *powiązanymi*. Chociaż przeniesienie produktu może pośrednio zmienić jego domyślną kategorię, jeśli stara domyślna zostanie usunięta i przypisana zostanie tylko jedna nowa kategoria, najlepszą praktyką jest ręczne zweryfikowanie i ustawienie domyślnej kategorii na stronie edycji produktu, jeśli masz specyficzne wymagania SEO lub nawigacyjne dla domyślnej kategorii.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera techniczny przegląd dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzać moduł „Masowe przypisywanie / przenoszenie produktów do kategorii”.

### 4.1 Przegląd architektury

Moduł `masspc` (Mass Product Categories) to standardowy moduł PrestaShop działający głównie w Panelu administracyjnym. Wykorzystuje AJAX do wyszukiwania produktów i wyboru kategorii, zapewniając interfejs użytkownika przypominający kreator. Główna logika manipulacji produktami i kategoriami jest obsługiwana w głównej klasie modułu, która rozszerza `Module`. Nie wprowadza niestandardowych klas `ObjectModel` ani dedykowanych kontrolerów administracyjnych poza swoją główną stroną konfiguracji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów Front-Office ani Back-Office Admin w katalogu `controllers/`. Cała logika jest obsługiwana bezpośrednio w głównym pliku modułu `masspc.php` (lub `ajax_products_list.php` zgodnie z dossier, co jest nietypową konwencją nazewnictwa dla głównego pliku modułu, ale oznacza, że obsługuje on główną logikę i żądania AJAX).

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani modeli w katalogu `classes/`. Cała logika rdzenia jest hermetyzowana w głównym pliku modułu. Manipulacja danymi produktów i kategorii opiera się na natywnych klasach `ObjectModel` PrestaShop `Product` i `Category` oraz ich powiązanych metodach (np. `Product::updateCategories()`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`masspc/lib/searchTool/views/js/autocomplete.js`**
    -   **Zakres:** Panel administracyjny (używany na stronie konfiguracji modułu).
    -   **Opis:** Ten skrypt prawdopodobnie zapewnia podstawową funkcjonalność dla funkcji wyszukiwania autouzupełniania opartej na AJAX, w szczególności do znajdowania produktów po nazwie. Nasłuchuje danych wprowadzanych przez użytkownika w polu wyszukiwania, wysyła żądania AJAX do backendu modułu (prawdopodobnie do samego `ajax_products_list.php` lub metody w nim) i wyświetla sugestie. Obsługuje wybór produktów i dodawanie ich do listy do przetworzenia.
-   **`masspc/views/js/jquery.autocomplete.js`**
    -   **Zakres:** Panel administracyjny (używany na stronie konfiguracji modułu).
    -   **Opis:** Wydaje się to być wtyczka jQuery lub niestandardowy skrypt, który implementuje lub ulepsza funkcjonalność autouzupełniania. Może być zależnością dla `autocomplete.js` lub alternatywną/starszą implementacją. Obsługiwałby wizualne renderowanie sugestii autouzupełniania i interakcję, gdy użytkownik wybierze element.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`masspc/lib/searchTool/views/css/autocomplete.css`**
    -   **Zakres:** Panel administracyjny (stylizuje stronę konfiguracji modułu).
    -   **Opis:** Ten arkusz stylów zapewnia wizualne style dla pola wyszukiwania autouzupełniania, rozwijanej listy sugestii i potencjalnie listy wybranych produktów w interfejsie konfiguracji modułu. Programiści mogą nadpisać te style w swoim niestandardowym motywie administracyjnym lub dodając bardziej specyficzne reguły CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`masspc/lib/searchTool/views/scripts.tpl`**
    -   **Zakres:** Panel administracyjny (zawarty na stronie konfiguracji modułu).
    -   **Opis:** Ten szablon prawdopodobnie zawiera kod JavaScript lub linki do plików JS (`autocomplete.js`, `jquery.autocomplete.js`) i potencjalnie plików CSS (`autocomplete.css`) wymaganych dla interfejsu wyszukiwania i wyboru produktów. Jest zazwyczaj używany do wstrzykiwania zasobów do `<head>` lub `<body>` strony administracyjnej.
-   **`masspc/views/templates/admin/cselection.tpl`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora).
    -   **Opis:** Ten szablon renderuje sekcję „Krok 2: Wybierz kategorie, do których przypisać/przenieść produkty” modułu. Wyświetla strukturę drzewa kategorii, umożliwiając administratorowi wybór kategorii docelowych. Prawdopodobnie używa rekurencyjnej struktury do wyświetlania kategorii nadrzędnych i podrzędnych.
-   **`masspc/views/templates/admin/target_products.tpl`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora).
    -   **Opis:** Ten szablon renderuje sekcję „Krok 1: Wybierz produkty do zarządzania”. Zawiera pole wprowadzania wyszukiwania produktów (gdzie działa `autocomplete.js`) i wyświetla listę produktów, które zostały wybrane do masowej akcji.
-   **`masspc/views/templates/admin/wtd.tpl`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora).
    -   **Opis:** Ten szablon renderuje sekcję „Krok 3: Co zrobić z wybranymi produktami?”. Zawiera przyciski radiowe dla „Przypisz produkty do wybranych kategorii” i „Przenieś produkty do wybranych kategorii”, wraz z ich opisami.
-   **`masspc/views/templates/hook/form.tpl`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora).
    -   **Opis:** Jest to prawdopodobnie główny szablon opakowujący dla formularza konfiguracji modułu, który zawiera inne szablony `admin/` (`target_products.tpl`, `cselection.tpl`, `wtd.tpl`), aby zbudować kompletny interfejs kreatora. Zawierałby ogólną strukturę formularza i przycisk „Wykonaj”.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Bezpośrednio współdziała z podstawowymi tabelami PrestaShop:
        -   `ps_product_category`: Do zarządzania powiązaniami produktów z kategoriami.
        -   `ps_product_shop`: Do danych specyficznych dla sklepu produktu, w tym domyślnej kategorii.
        -   `ps_category`: Do pobierania nazw i struktury kategorii.
        -   `ps_product`: Do pobierania nazw i szczegółów produktów do wyszukiwania.
-   **Tabela zarejestrowanych hooków**:
    -   Główna funkcjonalność modułu jest dostępna za pośrednictwem jego strony konfiguracji, a nie za pośrednictwem hooków Front-Office.
    -   Prawdopodobnie używa hooka `displayBackOfficeHeader` do wstrzykiwania swoich zasobów CSS i JavaScript do nagłówka Panelu administracyjnego.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderuje się w `<head>` stron Panelu administracyjnego. | Wstrzykuje pliki CSS i JavaScript specyficzne dla modułu na stronę konfiguracji. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Masowe przypisywanie / przenoszenie produktów do kategorii”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
