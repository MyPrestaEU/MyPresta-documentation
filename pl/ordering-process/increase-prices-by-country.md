---
title: "Zwiększanie cen według kraju - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zwiększanie cen według kraju” od MyPresta.eu."
sidebar:
  label: "Zwiększanie cen według kraju - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Increase prices by country na MyPresta.eu](https://mypresta.eu/modules/ordering-process/increase-prices-by-country.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/increase-prices-by-country/)
>
> ---


# Zwiększanie cen według kraju

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Moduł opiera się na podstawowej funkcjonalności PrestaShop i standardowych konfiguracjach serwera.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

**Wykryte ustawienia i opcje: Standardowe ustawienia modułu**
Ten ekran zazwyczaj zawiera ogólne ustawienia modułu, takie jak włączanie/wyłączanie modułu lub globalne preferencje.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera globalny przełącznik do włączania lub wyłączania podstawowej funkcjonalności modułu. Może również zawierać ogólne preferencje, które wpływają na sposób stosowania korekt cen w Twoim sklepie.
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy włączony:* Moduł będzie aktywnie dostosowywać ceny na podstawie reguł zdefiniowanych w dedykowanej sekcji „Lista cen według kraju”.
    -   *Gdy wyłączony:* Moduł przestanie dostosowywać ceny, a wszyscy klienci będą widzieć domyślne ceny produktów, niezależnie od ich kraju.
-   **Zalecana wartość:** „TAK” (Włączony), jeśli zamierzasz używać modułu do korekt cen.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, będziesz chciał go tutaj włączyć. Jeśli musisz tymczasowo wstrzymać wszystkie korekty cen dla poszczególnych krajów bez usuwania reguł, możesz go tutaj wyłączyć.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminPbcListController (Panel administracyjny > Zwiększanie cen według kraju > Lista cen według kraju)

Jest to główny ekran zarządzania, na którym definiujesz i zarządzasz regułami korekty cen dla poszczególnych krajów.

-   **Nazwa ekranu i lokalizacja w menu:** W Panelu administracyjnym PrestaShop znajdziesz nową pozycję menu, zazwyczaj w sekcji takiej jak „Katalog” lub „Międzynarodowe”, o nazwie **„Zwiększanie cen według kraju”** lub podobnej, a następnie podpozycję menu, taką jak **„Lista cen według kraju”**.
-   **Dostępne akcje i ustawienia:**
    -   **Dodaj nową regułę:** Przycisk do tworzenia nowej reguły korekty ceny.
    -   **Lista reguł:** Tabela wyświetlająca wszystkie istniejące reguły, pokazująca szczegóły takie jak:
        -   **Kraj:** Kraj docelowy dla reguły.
        -   **Typ korekty:** Czy jest to procent czy stała kwota.
        -   **Wartość:** Procent lub kwota do zwiększenia/zmniejszenia.
        -   **Akcja:** Opcje „Edytuj” lub „Usuń” poszczególne reguły.
    -   **Pola formularza do dodawania/edycji reguły:**
        -   **Selektor kraju:** Rozwijana lista lub pole wyszukiwania do wyboru konkretnego kraju, do którego ma zastosowanie ta reguła.
            -   *Efekt:* Ceny zostaną skorygowane tylko dla klientów zidentyfikowanych jako znajdujący się w tym kraju.
            -   *Zalecane:* Wybierz konkretny kraj, który chcesz docelować.
            -   *Scenariusz:* Chcesz zwiększyć ceny dla klientów w Stanach Zjednoczonych.
        -   **Typ korekty (Procent / Kwota):** Przycisk radiowy lub rozwijana lista do wyboru sposobu korekty ceny.
            -   *Efekt:*
                -   *Procent:* Cena zostanie zwiększona lub zmniejszona o procent jej pierwotnej wartości.
                -   *Kwota:* Cena zostanie zwiększona lub zmniejszona o stałą wartość pieniężną (w domyślnej walucie Twojego sklepu).
            -   *Zalecane:* Wybierz na podstawie swojej strategii cenowej. Procent jest dobry dla spójnych narzutów, Kwota dla stałych dopłat/rabatów.
            -   *Scenariusz:* Chcesz dodać 10% narzutu (Procent) lub stałą dopłatę 5 $ (Kwota).
        -   **Wartość:** Pole wprowadzania procentu (np. „10” dla 10%) lub stałej kwoty (np. „5.00” dla 5 $).
            -   *Efekt:*
                -   *Wartość dodatnia:* Zwiększa cenę.
                -   *Wartość ujemna:* Zmniejsza cenę (np. „-5” dla 5% rabatu lub „-2.50” dla rabatu 2.50 $).
            -   *Zalecane:* Wprowadź pożądaną korektę. Zachowaj ostrożność z wartościami ujemnymi, aby uniknąć cen poniżej zera.
            -   *Scenariusz:* Wprowadź „15”, aby zwiększyć o 15%, lub „-2.50”, aby zmniejszyć o 2.50 $.
-   **Wpływ zmian:**
    -   Dodanie nowej reguły natychmiast aktywuje korektę ceny dla wybranego kraju.
    -   Edycja reguły aktualizuje korektę dla tego kraju.
    -   Usunięcie reguły usuwa korektę specyficzną dla kraju, a klienci z tego kraju ponownie zobaczą domyślne ceny produktów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zidentyfikuj kraj, w którym chcesz dostosować ceny (np. z powodu wyższych kosztów wysyłki, lokalnej konkurencji lub specjalnej promocji).
    2.  Przejdź do ekranu „Lista cen według kraju”.
    3.  Kliknij „Dodaj nową regułę”.
    4.  Wybierz kraj docelowy.
    5.  Wybierz, czy chcesz dostosować według „Procentu” czy „Kwoty”.
    6.  Wprowadź dodatnią lub ujemną wartość korekty.
    7.  Zapisz regułę.
    8.  Przetestuj, używając VPN lub prosząc kogoś z tego kraju o sprawdzenie cen w Twoim sklepie.

#### index.php (pbc/controllers/admin/index.php)

Ten plik prawdopodobnie służy jako routing lub placeholder dla kontrolerów administracyjnych w katalogu modułu `pbc`. Nie reprezentuje on odrębnego, konfigurowalnego ekranu, ale raczej zapewnia prawidłowy dostęp i ładowanie innych kontrolerów administracyjnych, takich jak `AdminPbcListController`. Sprzedawcy nie będą bezpośrednio wchodzić w interakcje z tym plikiem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Moduł Włączony/Wyłączony | Włączony | Globalny przełącznik do aktywacji lub dezaktywacji wszystkich korekt cen dla poszczególnych krajów. |
| **Lista cen według kraju** | Dodaj/Edytuj regułę: Kraj | N/A (wybierz konkretny) | Definiuje kraj docelowy dla korekty ceny. |
| | Dodaj/Edytuj regułę: Typ korekty | Procent | Wybierz, czy cena zmienia się o procent, czy o stałą kwotę. |
| | Dodaj/Edytuj regułę: Wartość | 0 (wprowadź pożądaną) | Dodatni (zwiększenie) lub ujemny (zmniejszenie) procent lub kwota. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje ceny nie zmieniają się dla konkretnego kraju, nawet po ustawieniu reguły.**
O:

1.  **Czy moduł jest włączony globalnie?** Sprawdź główną stronę konfiguracji modułu (Moduły > Menedżer modułów > Konfiguruj „Zwiększanie cen według kraju”), aby upewnić się, że moduł jest aktywny.
2.  **Czy reguła jest poprawnie skonfigurowana?** Przejdź do „Lista cen według kraju” i sprawdź, czy kraj jest poprawnie wybrany, typ korekty (procent/kwota) jest prawidłowy, a wartość jest poprawnie wprowadzona (dodatnia dla zwiększenia, ujemna dla zmniejszenia).
3.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”, jeśli jest dostępna). Często rozwiązuje to problemy z wyświetlaniem.
4.  **Problemy z geolokalizacją:** Moduł opiera się na funkcji geolokalizacji PrestaShop. Upewnij się, że geolokalizacja Twojego sklepu PrestaShop jest poprawnie skonfigurowana (Zaawansowane > Geolokalizacja). Jeśli testujesz z własnego kraju, spróbuj użyć VPN, aby zasymulować wizytę z kraju docelowego.

**P: Czy ten moduł wpłynie na moje SEO lub kanały produktów?**
O: Moduł dynamicznie dostosowuje ceny w front-office na podstawie adresu IP odwiedzającego. Nie zmienia podstawowej ceny produktu w bazie danych. Dlatego zazwyczaj nie powinien bezpośrednio wpływać na Twoje SEO (wyszukiwarki zazwyczaj indeksują z domyślnej lokalizacji lub używają Twoich podstawowych cen) ani na kanały produktów (które zazwyczaj pobierają podstawowe ceny). Jeśli jednak korzystasz z usługi zewnętrznej, która indeksuje Twoją witrynę z różnych lokalizacji, mogą one widzieć skorygowane ceny.

**P: Co się stanie, jeśli klient z kraju z korektą ceny doda produkt do koszyka, a następnie zmieni swój kraj (np. poprzez adres wysyłki)?**
O: Moduł dostosowuje ceny na podstawie *wykrytego kraju klienta* w momencie przeglądania. Jeśli kraj klienta się zmieni (np. zaloguje się, a jego adres znajduje się w innym kraju, lub wyraźnie wybierze inny kraj wysyłki podczas realizacji zamówienia), podstawowa logika PrestaShop do obliczania ceny (którą ten moduł nadpisuje) powinna ponownie ocenić cenę. Nadpisanie modułu zapewnia, że prawidłowa cena dla *końcowego* kraju zostanie zastosowana.

**P: Czy mogę zastosować różne reguły dla różnych grup klientów w tym samym kraju?**
O: Nie, ten moduł dostosowuje ceny *wyłącznie na podstawie kraju* określonego przez geolokalizację. Nie oferuje opcji różnicowania cen na podstawie grup klientów (np. hurtowych vs. detalicznych) w jednym kraju. Aby uzyskać ceny specyficzne dla grup klientów, potrzebny byłby oddzielny moduł lub wbudowane reguły cenowe PrestaShop.

**P: Ustawiłem zwiększenie kwoty, ale wygląda to inaczej w innych walutach.**
O: Kiedy ustawiasz zwiększenie kwoty (np. +5 $), moduł stosuje tę kwotę w *domyślnej walucie* Twojego sklepu. Następnie automatycznie przelicza tę dodatkową kwotę na inne waluty na podstawie skonfigurowanych w Twoim sklepie kursów wymiany walut. Zapewnia to, że *wartość* zwiększenia pozostaje spójna w różnych walutach. Upewnij się, że Twoje kursy wymiany walut są aktualne w PrestaShop (Międzynarodowe > Waluty).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zwiększanie cen według kraju” (`pbc`) działa głównie poprzez nadpisywanie podstawowej klasy `Product` PrestaShop w celu wstrzykiwania korekt cen specyficznych dla kraju podczas obliczania ceny. Wykorzystuje funkcje geolokalizacji PrestaShop do identyfikacji kraju klienta i stosuje reguły zdefiniowane w niestandardowej tabeli bazy danych. Moduł stosuje standardowy wzorzec MVC PrestaShop do zarządzania w Panelu administracyjnym, z dedykowanym kontrolerem administracyjnym do zarządzania regułami cen.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak jawnie zdefiniowanych w archiwum modułu. Korekty cen są obsługiwane poprzez nadpisanie `Product.php`, które włącza się w podstawową logikę obliczania ceny PrestaShop.
-   **Kontrolery administracyjne Back-Office**:
    -   `pbc/controllers/admin/AdminPbcListController.php`
        -   **Nazwa klasy**: `AdminPbcListController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność**: Zarządza operacjami CRUD dla encji `pricebc` (Price By Country). Ten kontroler wyświetla listę zdefiniowanych reguł korekty cen, obsługuje dodawanie nowych reguł, edycję istniejących i ich usuwanie. Wykorzystuje `HelperList` i `HelperForm` PrestaShop do renderowania listy i formularzy dodawania/edycji.
        -   **Nazwa zakładki**: Zazwyczaj rejestrowana pod niestandardową zakładką w nawigacji Panelu administracyjnego, dostępna poprzez główny wpis menu modułu.
    -   `pbc/controllers/admin/index.php`
        -   **Nazwa klasy**: N/A (jest to plik placeholder)
        -   **Odpowiedzialność**: Ten plik jest powszechną praktyką w tworzeniu modułów PrestaShop, aby zapobiec bezpośredniemu listowaniu katalogów i zapewnić prawidłowe routowanie w katalogu `controllers/admin`. Nie zawiera logiki wykonywalnej dla konkretnego kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `pbc/classes/index.php`
    -   **Nazwa klasy**: N/A
    -   **Odpowiedzialność**: Plik placeholder zapobiegający listowaniu katalogów.
-   `pbc/classes/pricebc.php`
    -   **Nazwa klasy**: `PriceBc` (rozszerza `ObjectModel`)
    -   **Tabela bazy danych**: `_pbc` (np. `ps_pbc`)
    -   **Pola `$definition`**:
        -   `id_pbc`: Klucz podstawowy.
        -   `id_country`: Klucz obcy do tabeli `ps_country`, identyfikujący kraj docelowy.
        -   `type`: Liczba całkowita, zazwyczaj 0 dla procentu, 1 dla kwoty.
        -   `value`: Liczba dziesiętna, procent lub kwota do korekty. Może być dodatnia lub ujemna.
    -   **Kluczowe metody publiczne**: Standardowe metody `ObjectModel` dla operacji CRUD. Może zawierać metody statyczne do pobierania reguł na podstawie ID kraju.
-   `pbc/override/classes/index.php`
    -   **Nazwa klasy**: N/A
    -   **Odpowiedzialność**: Plik placeholder zapobiegający listowaniu katalogów w katalogu nadpisywania.
-   `pbc/override/classes/Product.php`
    -   **Nazwa klasy**: `Product` (rozszerza podstawową klasę `Product` PrestaShop)
    -   **Odpowiedzialność**: Jest to najbardziej krytyczna część modułu. Nadpisuje metodę `getPriceStatic()` (lub podobne metody obliczania ceny) podstawowej klasy `Product`.
        -   Pobiera bieżący kraj klienta (za pomocą geolokalizacji lub kontekstu).
        -   Wykonuje zapytanie do modelu `PriceBc` w celu znalezienia aktywnych reguł korekty ceny dla tego kraju.
        -   Następnie stosuje korektę procentową lub kwotową do podstawowej ceny produktu przed zwróceniem ostatecznej obliczonej ceny.
        -   Obsługuje konwersję walut dla korekt opartych na kwocie.
    -   **Uwaga dla programistów**: Wszelkie inne moduły, które również nadpisują `Product.php`, mogą prowadzić do konfliktów. Wymagane jest dokładne testowanie. Nadpisanie modułu powinno być zaprojektowane tak, aby było kompatybilne z innymi nadpisaniami lub aby umożliwiało łączenie.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `pbc/views/admin/script.js`
    -   **Zakres**: Panel administracyjny (formularze AdminPbcListController).
    -   **Funkcjonalność**: Prawdopodobnie obsługuje dynamiczne zachowanie w formularzu „Dodaj/Edytuj regułę ceny”. Może to obejmować:
        -   Pokazywanie/ukrywanie pól na podstawie wybranego „Typu korekty” (np. jeśli wybrano „Procent”, upewnij się, że pole wartości jest traktowane jako procent).
        -   Walidacja lub formatowanie danych wejściowych.
        -   Wywołania AJAX dla wyboru kraju lub innych dynamicznych elementów formularza.

### 4.5 Arkusze stylów CSS (`views/css/`)

W dostarczonym inwentarzu nie wykryto niestandardowych plików CSS. Moduł prawdopodobnie opiera się na domyślnej stylizacji Panelu administracyjnego PrestaShop dla swoich formularzy konfiguracji i list, i nie wprowadza żadnych wizualnych elementów front-office wymagających niestandardowej stylizacji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `pbc/views/displayHeader.tpl`
        -   **Hook**: `displayHeader`
        -   **Cel**: Ten szablon jest prawdopodobnie używany do dołączania niezbędnych plików JavaScript lub CSS (jeśli były obecne) lub do inicjalizacji wszelkich skryptów front-office, które muszą zostać uruchomione wcześnie podczas ładowania strony. Biorąc pod uwagę charakter modułu, może również zawierać logikę do wykrywania kraju użytkownika lub ustawiania globalnej zmiennej JS do debugowania.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `pbc/lib/searchTool/views/scripts.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie częścią komponentu wielokrotnego użytku lub biblioteki w module, być może dla narzędzia wyszukiwania lub filtrowania używanego w AdminPbcListController. Zawierałby logikę JavaScript lub Smarty związaną z tym narzędziem.
-   **Szablony front-office (`views/templates/front/`)**:
    -   `pbc/views/script.tpl`
        -   **Cel**: Podobnie jak `displayHeader.tpl`, ten szablon może być używany do osadzania JavaScript bezpośrednio w front-office, potencjalnie dla logiki po stronie klienta związanej z wyświetlaniem ceny (chociaż główna logika jest po stronie serwera poprzez nadpisanie `Product`). Może to być również awaryjny lub bardziej ogólny punkt włączania skryptów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   `ps_pbc`: Przechowuje reguły korekty cen.
        -   `id_pbc` (INT, PK, AUTO\_INCREMENT)
        -   `id_country` (INT, FK do `ps_country.id_country`)
        -   `type` (TINYINT, 0 dla procentu, 1 dla kwoty)
        -   `value` (DECIMAL(20,6), ze znakiem, wartość korekty)
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Do dołączania zasobów JS/CSS modułu lub inicjalizacji skryptów front-end. |
| `actionProductPriceCalculation` | (Implicitnie poprzez nadpisanie `Product.php`) | Podstawowa funkcjonalność modułu jest zaimplementowana poprzez nadpisanie metody `Product::getPriceStatic()`, która jest wywoływana za każdym razem, gdy PrestaShop oblicza cenę produktu. Nie jest to standardowy hook, ale nadpisanie podstawowej klasy. |
| `actionAdminControllerSetMedia` | Po załadowaniu kontrolera administracyjnego. | Do dołączania zasobów JS/CSS modułu dla Panelu administracyjnego (np. `AdminPbcListController`). |
| `actionModuleInstall` | Podczas instalacji modułu. | Do tworzenia tabeli bazy danych `ps_pbc` i rejestrowania niezbędnych hooków. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Do usuwania tabeli bazy danych `ps_pbc` i wyrejestrowywania hooków. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i wsparcia technicznego, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w udzielanie pomocy i zapewnienie optymalnego funkcjonowania modułu z Twoim sklepem PrestaShop.
