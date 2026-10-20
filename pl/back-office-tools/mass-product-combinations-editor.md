---
title: "Masowy edytor kombinacji produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop 'Masowy edytor kombinacji produktów' od MyPresta.eu."
sidebar:
  label: "Masowy edytor kombinacji produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Mass product combinations editor na MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-product-combinations-editor.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/mass-product-combinations-editor/)
>
> ---


# Masowy edytor kombinacji produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań serwerowych poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Masowy edytor kombinacji produktów)

Po kliknięciu „Konfiguruj” dla modułu „Masowy edytor kombinacji produktów” zostaniesz przeniesiony do dedykowanego interfejsu administracyjnego. To tutaj będziesz wykonywać wszystkie masowe edycje kombinacji.

Główna strona konfiguracji tego modułu działa jako jego podstawowy interfejs. Nie posiada tradycyjnego „formularza ustawień” z przełącznikami i polami wprowadzania dla samego modułu, ale raczej JEST narzędziem do edycji kombinacji.

Oto przegląd tego, co zobaczysz i jak tego używać:

**Nazwa ekranu i lokalizacja w menu:**

-   **Ścieżka menu:** Po instalacji zazwyczaj znajdziesz nową pozycję menu w sekcji **Katalog** lub **Moduły** (w zależności od wersji PrestaShop i motywu) lub zawsze możesz uzyskać do niej dostęp poprzez **Moduły > Menedżer modułów** i kliknięcie „Konfiguruj” obok „Masowy edytor kombinacji produktów”.
-   **Tytuł ekranu:** „Masowy edytor kombinacji produktów” lub podobny.

**Dostępne działania i ustawienia:**

Główny interfejs przedstawi Ci potężną siatkę lub tabelę, która wyświetla kombinacje produktów. Dokładny wygląd może się nieznacznie różnić między wersjami PrestaShop, ale podstawowa funkcjonalność pozostaje spójna.

1.  **Wybór / Filtrowanie produktów:**

    -   **Co to robi:** Ten obszar pozwala wybrać, których kombinacji produktów chcesz edytować. Możesz zobaczyć pasek wyszukiwania, rozwijaną listę produktów lub filtry według kategorii, producenta itp.
    -   **Efekt zmiany tego ustawienia:** Wybierając produkt lub stosując filtry, poniższa tabela zostanie wypełniona tylko kombinacjami należącymi do wybranych produktów. Jest to kluczowe dla zawężenia zakresu.
    -   **Zalecana wartość:** Zacznij od wyszukania konkretnego produktu lub filtrowania według kategorii, aby zapoznać się z interfejsem.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zaktualizować stan magazynowy dla wszystkich kombinacji produktu „Letnia koszulka”. Wyszukujesz „Letnia koszulka” i wybierasz ją.
2.  **Tabela listująca kombinacje:**

    -   **Co to robi:** To jest rdzeń modułu. Wyświetla tabelę, gdzie każdy wiersz reprezentuje unikalną kombinację produktu (np. „Koszulka - Czerwona - Mała”). Kolumny reprezentują edytowalne pola, takie jak:
        -   **Referencja:** Wewnętrzny kod produktu dla tej konkretnej kombinacji.
        -   **EAN13 / UPC:** Numery kodów kreskowych.
        -   **Ilość:** Poziom zapasów dla tej kombinacji.
        -   **Wpływ na cenę:** Jak ta kombinacja wpływa na podstawową cenę produktu (np. +5 zł za rozmiar XL).
        -   **Cena hurtowa:** Cena zakupu tej kombinacji.
        -   **Waga:** Jak ta kombinacja wpływa na podstawową wagę produktu.
        -   **Minimalna ilość:** Minimalna liczba tej kombinacji, którą klient musi kupić.
        -   **Domyślna kombinacja:** Pole wyboru do oznaczenia jednej kombinacji jako domyślnej dla produktu.
        -   **Obraz:** Obraz powiązany z tą kombinacją.
    -   **Efekt zmiany tego ustawienia:** Możesz bezpośrednio klikać w komórki tej tabeli i wpisywać nowe wartości. Na przykład, zmiana „Ilości” z 5 na 10 zaktualizuje poziom zapasów dla tej konkretnej kombinacji.
    -   **Zalecana wartość:** Ostrożnie przeglądaj każdą kombinację i jej aktualne wartości przed wprowadzeniem zmian.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie otrzymałeś nową dostawę. Możesz przejść w dół kolumny „Ilość” i zaktualizować poziomy zapasów dla wszystkich odpowiednich kombinacji w ciągu kilku sekund.
3.  **Przycisk Zapisz:**

    -   **Co to robi:** Po wprowadzeniu wszystkich pożądanych zmian w tabeli, **musisz** kliknąć przycisk „Zapisz” lub „Zastosuj zmiany” (zazwyczaj znajdujący się na górze lub na dole tabeli), aby zatwierdzić swoje modyfikacje w bazie danych.
    -   **Efekt zmiany tego ustawienia:** Dopóki nie klikniesz „Zapisz”, Twoje zmiany są widoczne tylko na ekranie i nie są aktywne w Twoim sklepie. Kliknięcie „Zapisz” stosuje wszystkie oczekujące modyfikacje.
    -   **Zalecana wartość:** Zawsze często zapisuj swoją pracę, zwłaszcza po wprowadzeniu partii zmian.
    -   **Scenariusz / przykład dla sprzedawcy:** Zaktualizowałeś ceny dla 20 kombinacji. Kliknij „Zapisz”, aby te nowe ceny były aktywne na stronach Twoich produktów.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Zidentyfikuj swoje zadanie:** Czy musisz zaktualizować stan magazynowy, zmienić ceny, czy zmodyfikować referencje?
2.  **Przejdź do modułu:** Przejdź do **Moduły > Menedżer modułów** i kliknij „Konfiguruj” dla „Masowy edytor kombinacji produktów”.
3.  **Wybierz produkty:** Użyj opcji wyszukiwania lub filtrowania, aby załadować kombinacje, z którymi musisz pracować.
4.  **Wprowadź zmiany:** Bezpośrednio edytuj wartości w komórkach tabeli. Często możesz używać skrótów klawiaturowych (takich jak Tab), aby szybko poruszać się między polami.
5.  **Przejrzyj:** Dokładnie sprawdź swoje zmiany przed zapisaniem.
6.  **Zapisz:** Kliknij przycisk „Zapisz”, aby zastosować wszystkie modyfikacje.
7.  **Wyczyść pamięć podręczną (jeśli to konieczne):** W niektórych przypadkach, zwłaszcza po dużych zmianach cen lub stanów magazynowych, dobrą praktyką jest wyczyszczenie pamięci podręcznej PrestaShop (**Zaawansowane > Wydajność**), aby upewnić się, że zmiany są natychmiast widoczne w front office.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Wybór/Filtr produktów | (Zależy od produktu) | Zawęża wyświetlane kombinacje do edycji. |
| Strona konfiguracji modułu | Tabela listująca kombinacje (np. Ilość, Wpływ na cenę, Referencja, EAN13) | (Zależy od produktu) | Bezpośrednia edycja atrybutów kombinacji. Zmiany są stosowane do wybranej kombinacji. |
| Strona konfiguracji modułu | Przycisk Zapisz | Kliknij po zmianach | Zatwierdza wszystkie widoczne na ekranie modyfikacje w bazie danych, czyniąc je aktywnymi w Twoim sklepie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje zmiany nie pojawiają się w front office po zapisaniu!**
O: Zazwyczaj jest to problem z pamięcią podręczną. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” / „Wyczyść pamięć podręczną” w zależności od Twojej wersji). Twoje zmiany powinny wtedy się pojawić.

**P: Moduł wolno ładuje kombinacje dla produktów z wieloma wariantami.**
O: Dla produktów z setkami lub tysiącami kombinacji, ładowanie wszystkich danych może zająć trochę czasu. Jest to normalne ze względu na ilość przetwarzanych danych. Upewnij się, że Twój serwer spełnia zalecane specyfikacje PrestaShop. Jeśli jest konsekwentnie bardzo wolny, sprawdź limit pamięci PHP i ustawienia czasu wykonania na swoim serwerze (Twój dostawca hostingu może w tym pomóc).

**P: Czy mogę cofnąć zmiany wprowadzone za pomocą tego modułu?**
O: Moduł bezpośrednio aktualizuje Twoją bazę danych. Nie ma wbudowanego przycisku „cofnij”. Dlatego kluczowe jest, aby **zawsze mieć aktualną kopię zapasową swojego sklepu** przed wprowadzeniem masowych zmian. Jeśli popełnisz błąd, musiałbyś ręcznie poprawić wartości lub przywrócić kopię zapasową.

**P: Nie mogę znaleźć modułu w menu po instalacji.**
O: Po instalacji przejdź do **Moduły > Menedżer modułów**. Wyszukaj „Masowy edytor kombinacji produktów” i kliknij przycisk „Konfiguruj” obok niego. To zawsze przeniesie Cię do interfejsu modułu. W zależności od Twojej wersji PrestaShop i motywu, bezpośredni link w menu może pojawić się w sekcji „Katalog” lub „Moduły” dla szybszego dostępu.

**P: Czy ten moduł działa z niestandardowymi motywami?**
O: Tak, ten moduł działa całkowicie w Panelu administracyjnym PrestaShop. Nie generuje żadnych elementów front-office, więc powinien być w pełni kompatybilny z dowolnym niestandardowym motywem bez konfliktów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Masowy edytor kombinacji produktów” (`qce`) jest przede wszystkim narzędziem administracyjnym Back-Office. Wykorzystuje klasę `Module` PrestaShop do swojej podstawowej funkcjonalności i używa niestandardowego punktu końcowego AJAX do obsługi dynamicznego ładowania i zapisywania danych kombinacji produktów. Interfejs modułu jest renderowany za pomocą szablonu Smarty, a JavaScript obsługuje interakcje użytkownika i przesyłanie danych. Bezpośrednio współdziała z podstawowymi strukturami danych produktów i kombinacji PrestaShop, nie wprowadzając nowych klas `ObjectModel` ani tabel bazy danych.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych klas `ModuleFrontController` ani `AdminController` w katalogu `controllers/`. Cała logika Back-Office, w tym punkt końcowy AJAX, jest obsługiwana bezpośrednio w głównym pliku modułu `qce/ajax_qce.php` za pośrednictwem metody `getContent()`.

### 4.3 Klasy i modele rdzenia (`classes/`)

Moduł nie wprowadza żadnych niestandardowych klas w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowe klasy PrestaShop, takie jak `Product`, `Combination`, `Tools`, `Configuration` itp., do pobierania i aktualizowania danych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`qce/views/admin/js/qce.js`**
    -   **Zakres:** Back-office (panel administracyjny).
    -   **Cel:** Jest to główny plik JavaScript dla interfejsu modułu. Obsługuje:
        -   **Wybór produktu:** Prawdopodobnie zarządza rozwijaną listą lub polem wyszukiwania do wyboru produktu.
        -   **Ładowanie danych AJAX:** Wysyła żądania AJAX do metody `getContent()` modułu (lub konkretnego handlera AJAX w niej) w celu pobrania danych kombinacji dla wybranego produktu.
        -   **Renderowanie tabeli:** Dynamicznie wypełnia tabelę HTML danymi kombinacji otrzymanymi z serwera.
        -   **Edycja w miejscu:** Implementuje funkcjonalność umożliwiającą użytkownikom klikanie komórek tabeli i bezpośrednie edytowanie wartości (np. pojawiające się pola wprowadzania po kliknięciu).
        -   **Walidacja danych:** Może zawierać walidację po stronie klienta dla pól wprowadzania (np. upewnienie się, że ilość jest liczbą).
        -   **Zapisywanie danych AJAX:** Zbiera wszystkie zmodyfikowane dane kombinacji z tabeli i wysyła je za pośrednictwem AJAX do metody `getContent()` modułu w celu przetworzenia i zapisania w bazie danych.
        -   **Informacje zwrotne dla użytkownika:** Wyświetla wskaźniki ładowania, komunikaty o sukcesie lub alerty o błędach.
        -   **Słuchacze zdarzeń:** Wiąże słuchaczy z elementami takimi jak rozwijane listy wyboru produktów, pola wprowadzania w tabeli i przycisk „Zapisz”.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`qce/lib/blue/style.css`**
    -   **Zakres:** Back-office (panel administracyjny).
    -   **Cel:** Wydaje się, że jest to arkusz stylów strony trzeciej lub ogólny, prawdopodobnie dla komponentu interfejsu użytkownika lub konkretnego motywu stylów używanego w interfejsie modułu. Prawdopodobnie definiuje ogólne style tabel, style pól wprowadzania lub estetykę przycisków. Programiści powinni zbadać ten plik, aby zrozumieć jego wpływ na wizualną prezentację modułu.
-   **`qce/views/admin/css/qce.css`**
    -   **Zakres:** Back-office (panel administracyjny).
    -   **Cel:** Jest to specyficzny arkusz stylów modułu. Zawiera niestandardowe reguły CSS do stylizacji tabeli edycji kombinacji, elementów wyboru produktów i wszelkich innych unikalnych komponentów interfejsu użytkownika na stronie konfiguracji modułu.
    -   **Kluczowe selektory klas CSS:** Programiści chcący nadpisać lub dostosować wygląd modułu powinni zbadać ten plik pod kątem nazw klas, takich jak `.qce-table`, `.qce-product-selector`, `.qce-input-field` itp., i celować w nie w swoim niestandardowym motywie administracyjnym lub poprzez nadpisanie CSS modułu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **`qce/views/admin/qce.tpl`**
    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Jest to główny plik szablonu Smarty odpowiedzialny za renderowanie całego interfejsu „Masowego edytora kombinacji produktów” w Panelu administracyjnym PrestaShop.
    -   **Zawartość:** Zazwyczaj zawiera:
        -   Strukturę HTML dla obszaru wyboru/filtrowania produktów.
        -   Zastępczy element (np. pusty `<table>` lub `<div>`), gdzie dane kombinacji będą dynamicznie ładowane i renderowane przez `qce.js`.
        -   Przycisk „Zapisz” i wszelkie inne przyciski akcji.
        -   Dołączenia niezbędnych plików JavaScript (`qce.js`) i CSS (`qce.css`, `style.css`).
        -   Wszelkie początkowe komunikaty lub instrukcje dla sprzedawcy.
    -   **Renderowanie:** Ten szablon jest renderowany przez metodę `getContent()` pliku modułu `ajax_qce.php`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł **nie** tworzy żadnych niestandardowych tabel bazy danych.
    -   Bezpośrednio odczytuje i zapisuje dane w podstawowych tabelach PrestaShop związanych z produktami i kombinacjami, głównie:
        -   `ps_product_attribute` (główne dane kombinacji)
        -   `ps_product_attribute_shop` (dane kombinacji specyficzne dla sklepu)
        -   `ps_product_attribute_combination` (łączy atrybuty z kombinacjami)
        -   `ps_product` (dla informacji o produkcie)
        -   `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` (dla definicji atrybutów)
        -   `ps_image`, `ps_image_shop`, `ps_image_lang` (dla obrazów kombinacji)
    -   Ustawienia konfiguracji (jeśli byłyby obecne poza głównym interfejsem) byłyby przechowywane w `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie żadnych hooków wyświetlania front-office ani back-office (`displayHeader`, `actionValidateOrder` itp.) w tradycyjnym sensie. Jego funkcjonalność jest dostępna bezpośrednio poprzez stronę konfiguracji w Panelu administracyjnym. Metoda `install()` modułu zarejestrowałaby go jako moduł administracyjny, czyniąc go dostępnym poprzez Menedżer modułów.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Masowy edytor kombinacji produktów”, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
"""
