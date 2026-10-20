---
title: "Product Grid Pro - kolumny i układ listy produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Product Grid Pro - kolumny i układ listy produktów” od MyPresta.eu."
sidebar:
  label: "Product Grid Pro - kolumny i układ listy produktów"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product Grid Pro - columns & layout of list products na MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-grid-pro-columns-layout-of-list-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/product-grid-pro-columns-layout-of-list-products/)
>
> ---


# Product Grid Pro - kolumny i układ listy produktów

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Ten moduł działa głównie poprzez nadpisywanie domyślnego kontrolera listy produktów PrestaShop. Jego konfiguracja jest zarządzana bezpośrednio w sekcji „Katalog > Produkty”, z prostą opcją „resetowania” dostępną w głównej konfiguracji modułu.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Product Grid Pro” i kliknij „Konfiguruj”.

Ten ekran oferuje jedną, kluczową opcję:

-   **Zresetuj konfigurację modułu**
    -   **Co robi to ustawienie:** Ten przycisk pozwala przywrócić wszystkie zmiany wprowadzone przez moduł do jego domyślnych ustawień. Oznacza to, że wszelkie niestandardowe kolejności kolumn, widoczności lub dodane kolumny, które skonfigurowałeś na liście „Katalog > Produkty”, zostaną zresetowane do początkowego stanu modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po kliknięciu:* Moduł wyczyści swoje zapisane preferencje dotyczące układu siatki produktów. Jest to przydatne, jeśli wprowadziłeś wiele zmian i chcesz zacząć od nowa, lub jeśli napotkasz nieoczekiwany problem z wyświetlaniem i chcesz wykluczyć problemy z konfiguracją.
    -   **Zalecana wartość:** Kliknij to tylko, jeśli wyraźnie chcesz zresetować dostosowanie siatki produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Eksperymentowałeś z różnymi układami kolumn przez miesiące, a teraz Twoja lista produktów wydaje się zagracona lub zdezorganizowana. Kliknięcie „Zresetuj konfigurację modułu” przywróci ją do czystego, domyślnego stanu, umożliwiając ponowną konfigurację od podstaw.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Główna funkcjonalność „Product Grid Pro” jest doświadczana bezpośrednio w sekcji **Katalog > Produkty** w Panelu administracyjnym PrestaShop. Ten moduł ulepsza standardową listę produktów, dodając nowe kolumny i umożliwiając dostosowanie jej układu.

-   **Nazwa ekranu i lokalizacja w menu:** **Katalog > Produkty**
-   **Dostępne akcje i ustawienia:**
    -   **Nowe kolumny:** Moduł wprowadza kilka nowych, bardzo przydatnych kolumn do Twojej listy produktów. Należą do nich:
        -   **EAN13:** Europejski Numer Artykułu (kod kreskowy).
        -   **Referencja dostawcy:** Twoja wewnętrzna referencja dla produktu od dostawcy.
        -   **Producent:** Marka lub producent produktu.
        -   **Kombinacje:** Wskazuje, czy produkt ma warianty (rozmiary, kolory itp.).
        -   **Sprzedane sztuki:** Całkowita liczba sprzedanych sztuk tego produktu.
        -   **Ostatnia sprzedaż:** Data ostatniej sprzedaży jednostki tego produktu.
        -   **Waga:** Waga produktu.
        -   **Hurtowa:** Cena hurtowa produktu.
        -   **Utworzono:** Data dodania produktu do katalogu.
        -   **Stan:** Stan produktu (Nowy, Używany, Odnowiony).
        -   **W promocji:** Wskazuje, czy produkt jest obecnie w promocji.
        -   **Dostępny do zamówienia:** Czy klienci mogą obecnie kupić produkt.
        -   **Pokaż cenę:** Czy cena produktu jest wyświetlana na front-office.
        -   **Tylko online:** Wskazuje, czy produkt jest dostępny tylko online (nie w sklepach fizycznych).
        -   **Widoczność:** Gdzie produkt jest widoczny (Katalog, Wyszukiwanie, Oba, Brak).
        -   **Wirtualny:** Wskazuje, czy produkt jest produktem wirtualnym (np. do pobrania, usługa).
        -   **Pakiet:** Wskazuje, czy produkt jest pakietem produktów.
        -   **Zindeksowany:** Czy produkt jest zindeksowany do wyszukiwania.
        -   **Możliwość dostosowania:** Czy produkt ma pola do dostosowania.
        -   **Dostawca:** Konkretny dostawca związany z produktem.
    -   **Widoczność kolumn:** Możesz wybrać, które z tych nowych i istniejących kolumn są widoczne na Twojej liście produktów. Pomaga to uporządkować widok i skupić się na tym, co ważne.
    -   **Kolejność kolumn (przeciągnij i upuść):** Możesz łatwo zmienić kolejność kolumn, przeciągając je i upuszczając w preferowanej sekwencji. Pozwala to na umieszczenie najważniejszych informacji po lewej stronie dla szybkiego dostępu.
    -   **Filtrowanie i sortowanie:** Każda z nowych kolumn obsługuje filtrowanie i sortowanie, tak jak domyślne kolumny PrestaShop. Oznacza to, że możesz na przykład sortować produkty według „Sprzedanych sztuk”, aby zobaczyć swoje bestsellery, lub filtrować według „Producenta”, aby zarządzać produktami określonej marki.
-   **Efekt zmian:**
    -   **Dodawanie/usuwanie kolumn:** Bezpośrednio zmienia informacje wyświetlane na liście „Katalog > Produkty”. Usunięcie kolumny ukrywa te dane; dodanie jej sprawia, że są widoczne.
    -   **Zmiana kolejności kolumn:** Zmienia wizualny układ listy produktów, pozwalając na priorytetyzację informacji.
    -   **Filtrowanie/sortowanie:** Pomaga szybko zlokalizować i analizować określone grupy produktów na podstawie ustawionych kryteriów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zidentyfikuj swoje kluczowe metryki:** Jakie informacje o produkcie sprawdzasz najczęściej? (np. stan magazynowy, cena, sprzedane sztuki, referencja dostawcy).
    2.  **Włącz niezbędne kolumny:** Przejdź do **Katalog > Produkty**, znajdź opcje dostosowywania kolumn (często ikona koła zębatego lub przycisk „Kolumny”) i włącz tylko te kolumny, których naprawdę potrzebujesz.
    3.  **Uporządkuj dla efektywności:** Przeciągnij i upuść najważniejsze kolumny na lewą stronę siatki, aby były natychmiast widoczne bez przewijania w poziomie.
    4.  **Użyj filtrów:** Podczas zarządzania zapasami użyj filtra „Sprzedane sztuki”, aby zidentyfikować wolno rotujące produkty, lub filtruj według „Ostatnia sprzedaż”, aby znaleźć produkty, które nie sprzedawały się od dłuższego czasu.
    5.  **Regularnie przeglądaj:** Okresowo przeglądaj konfigurację kolumn, aby upewnić się, że nadal spełnia Twoje potrzeby operacyjne.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | Zresetuj konfigurację modułu | N/A (przycisk) | Przywraca wszystkie niestandardowe ustawienia siatki produktów (widoczność kolumn, kolejność) do domyślnych ustawień modułu. Użyj, aby zacząć od nowa lub rozwiązać problemy. |
| Siatka Katalog > Produkty | Kolumna EAN13 | Wyłączone | Wyświetla kod kreskowy EAN13 dla każdego produktu. Przydatne do inwentaryzacji i skanowania. |
| Siatka Katalog > Produkty | Kolumna referencji dostawcy | Wyłączone | Pokazuje wewnętrzną referencję dostawcy dla produktu. Niezbędne do zarządzania dostawcami. |
| Siatka Katalog > Produkty | Kolumna producenta | Wyłączone | Wyświetla producenta/markę produktu. Przydatne do zarządzania specyficznymi markami. |
| Siatka Katalog > Produkty | Kolumna kombinacji | Wyłączone | Wskazuje, czy produkt ma kombinacje. Szybkie sprawdzenie dla złożonych produktów. |
| Siatka Katalog > Produkty | Kolumna sprzedanych sztuk | Wyłączone | Pokazuje całkowitą liczbę sprzedanych sztuk dla każdego produktu. Świetne do identyfikacji bestsellerów. |
| Siatka Katalog > Produkty | Kolumna ostatniej sprzedaży | Wyłączone | Wyświetla datę ostatniej sprzedaży produktu. Pomaga zidentyfikować wolno rotujący towar. |
| Siatka Katalog > Produkty | Kolumna wagi | Wyłączone | Pokazuje wagę produktu. Ważne dla obliczeń wysyłki. |
| Siatka Katalog > Produkty | Kolumna hurtowa | Wyłączone | Wyświetla cenę hurtową. Przydatne do obliczania marży i dla sklepów B2B. |
| Siatka Katalog > Produkty | Kolumna utworzono | Wyłączone | Pokazuje datę dodania produktu. Pomaga śledzić rozwój katalogu. |
| Siatka Katalog > Produkty | Kolumna stanu | Wyłączone | Wyświetla stan produktu (Nowy, Używany, Odnowiony). Istotne dla niektórych typów produktów. |
| Siatka Katalog > Produkty | Kolumna w promocji | Wyłączone | Wskazuje, czy produkt jest obecnie w promocji. Szybki przegląd promocji. |
| Siatka Katalog > Produkty | Kolumna dostępny do zamówienia | Wyłączone | Pokazuje, czy produkt można zamówić. Niezbędne do zarządzania zapasami. |
| Siatka Katalog > Produkty | Kolumna pokaż cenę | Wyłączone | Wskazuje, czy cena jest widoczna na front-office. |
| Siatka Katalog > Produkty | Kolumna tylko online | Wyłączone | Pokazuje, czy produkt jest dostępny wyłącznie w sprzedaży online. |
| Siatka Katalog > Produkty | Kolumna widoczności | Wyłączone | Wyświetla, gdzie produkt jest widoczny (katalog, wyszukiwanie, oba, brak). |
| Siatka Katalog > Produkty | Kolumna wirtualny | Wyłączone | Wskazuje, czy produkt jest wirtualny (do pobrania, usługa). |
| Siatka Katalog > Produkty | Kolumna pakiet | Wyłączone | Pokazuje, czy produkt jest pakietem innych produktów. |
| Siatka Katalog > Produkty | Kolumna zindeksowany | Wyłączone | Wskazuje, czy produkt jest zindeksowany do wyszukiwania. |
| Siatka Katalog > Produkty | Kolumna możliwość dostosowania | Wyłączone | Pokazuje, czy produkt ma opcje dostosowania. |
| Siatka Katalog > Produkty | Kolumna dostawca | Wyłączone | Wyświetla głównego dostawcę produktu. |
| Siatka Katalog > Produkty | Kolejność kolumn (przeciągnij i upuść) | N/A (definiowane przez użytkownika) | Dostosuj wizualną sekwencję kolumn dla optymalnego przepływu pracy. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem nowe kolumny, ale nie pojawiają się na liście produktów.**
O1: Po włączeniu kolumn upewnij się, że zapisałeś zmiany (jeśli istnieje przycisk zapisu w interfejsie dostosowywania kolumn). Czasami wyczyszczenie pamięci podręcznej przeglądarki lub pamięci podręcznej Smarty PrestaShop może pomóc. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.

**P2: Przeciąganie i upuszczanie nie działa, lub układ wygląda dziwnie.**
O2: Może to być konflikt JavaScript z innym modułem lub Twoim motywem.
    1.  Spróbuj wyczyścić pamięć podręczną przeglądarki i pamięć podręczną Smarty PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
    2.  Jeśli problem nadal występuje, spróbuj kliknąć przycisk „Zresetuj konfigurację modułu” na stronie konfiguracji modułu (**Moduły > Menedżer modułów > Product Grid Pro > Konfiguruj**). Spowoduje to przywrócenie domyślnego układu i może rozwiązać konflikt.
    3.  Jeśli problem nadal występuje, tymczasowo wyłącz inne moduły, które również modyfikują listę produktów lub interfejs administratora, aby zidentyfikować konflikt.

**P3: Czy mogę dodać jeszcze więcej niestandardowych pól do siatki produktów?**
O3: Ten moduł zapewnia predefiniowany zestaw często żądanych pól. Nie oferuje ogólnego sposobu dodawania *dowolnego* niestandardowego pola, które mogłeś utworzyć (np. za pomocą innego modułu pól niestandardowych). Jeśli potrzebujesz bardzo specyficznego pola niestandardowego, będzie to wymagało dalszego niestandardowego rozwoju.

**P4: Czy ten moduł spowolni mój Panel administracyjny?**
O4: Moduł został zaprojektowany tak, aby był wydajny. Chociaż dodanie wielu kolumn oznacza ładowanie większej ilości danych, wpływ na wydajność jest zazwyczaj minimalny i przewyższony przez zyski z efektywności. Jeśli zauważysz znaczne spowolnienia, rozważ wyłączenie mniej krytycznych kolumn, aby zmniejszyć ładowane dane.

**P5: Moduł jest zainstalowany, ale nie widzę żadnych nowych opcji w Katalog > Produkty.**
O5: Upewnij się, że moduł jest poprawnie zainstalowany i włączony. Czasami po instalacji może być konieczne odświeżenie przeglądarki lub nawet wylogowanie się i ponowne zalogowanie do Panelu administracyjnego, aby zmiany weszły w życie. Sprawdź również, czy podczas instalacji nie pojawiły się żadne komunikaty o błędach. Jeśli używasz PrestaShop 1.6, interfejs dostosowywania kolumn może być nieco inny niż w 1.7/8/9.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Product Grid Pro”.

### 4.1 Przegląd architektury

Moduł „Product Grid Pro” działa głównie poprzez nadpisywanie podstawowego `AdminProductsController` w PrestaShop. Jest to powszechna i potężna technika w rozwoju modułów PrestaShop, pozwalająca modułom rozszerzać lub modyfikować zachowanie podstawowych funkcji bez bezpośredniej zmiany plików rdzenia. Moduł wstrzykuje dodatkowe kolumny, filtry i możliwości sortowania do tabeli listy produktów, manipulując tablicą `$this->fields_list` w nadpisanym kontrolerze. Wykorzystuje również dedykowany plik JavaScript do obsługi przeciągania i upuszczania kolumn oraz potencjalnie innych dynamicznych ulepszeń interfejsu użytkownika. Konfiguracja jest przechowywana w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza nowych kontrolerów front-office. Jego główna interakcja odbywa się z kontrolerem `AdminProductsController` w Panelu administracyjnym.

-   **Kontrolery Front-Office**: Brak.
-   **Kontrolery Panelu administracyjnego**:
    *   `myproductgridpro/override/controllers/admin/AdminProductsController.php`
        *   **Nazwa klasy i klasa nadrzędna**: `AdminProductsController` (nadpisuje podstawowy `AdminProductsController`).
        *   **Odpowiedzialność**: To jest rdzeń funkcjonalności modułu. Rozszerza domyślną funkcjonalność listy produktów.
            *   Modyfikuje tablicę `$this->fields_list`, aby dodać nowe definicje kolumn (EAN13, Referencja dostawcy, Producent, Sprzedane sztuki, Ostatnia sprzedaż, Waga, Hurtowa, Utworzono, Stan, W promocji, Dostępny do zamówienia, Pokaż cenę, Tylko online, Widoczność, Wirtualny, Pakiet, Zindeksowany, Możliwość dostosowania, Dostawca).
            *   Zapewnia, że te nowe pola są sortowalne i filtrowalne.
            *   Obsługuje logikę pobierania danych dla tych nowych kolumn z bazy danych.
            *   Integruje JavaScript do zmiany kolejności kolumn i zarządzania widocznością.
    *   `myproductgridpro/override/controllers/admin/index.php`
        *   **Nazwa klasy i klasa nadrzędna**: Ten plik jest prawdopodobnie placeholderem lub prostym przekierowaniem w strukturze nadpisywania i nie zawiera pełnej definicji klasy kontrolera dla konkretnej encji. Jego obecność w katalogu `override/controllers/admin/` sugeruje, że może być częścią samego mechanizmu nadpisywania, potencjalnie zapewniając poprawne ładowanie nadpisania `AdminProductsController.php` lub obsługując ogólny kontekst administratora. W większości przypadków rzeczywista logika znajduje się w `AdminProductsController.php`.

### 4.3 Klasy rdzenia i modele (`classes/`)

Ten moduł nie definiuje niestandardowych klas `ObjectModel`. Bezpośrednio współdziała z istniejącymi obiektami `Product` i `Configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `myproductgridpro/views/js/product_grid_admin.js`
    *   **Zakres**: Panel administracyjny (konkretnie strona `Katalog > Produkty`).
    *   **Odpowiedzialność**:
        *   Obsługuje dynamiczną manipulację tabelą listy produktów w Panelu administracyjnym PrestaShop.
        *   Implementuje funkcjonalność przeciągania i upuszczania do zmiany kolejności kolumn, umożliwiając administratorom dostosowanie układu.
        *   Zarządza widocznością kolumn (pokazywanie/ukrywanie ich na podstawie preferencji użytkownika).
        *   Prawdopodobnie przechowuje i pobiera preferencje użytkownika dotyczące kolejności i widoczności kolumn za pomocą wywołań AJAX lub pamięci lokalnej/plików cookie, które są następnie używane przez nadpisany `AdminProductsController` do renderowania siatki.
        *   Może zawierać słuchacze zdarzeń dla elementów interfejsu użytkownika, które kontrolują wybór kolumn (np. ikona koła zębatego lub menu rozwijane do przełączania kolumn).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `myproductgridpro/views/css/product_grid_admin.css`
    *   **Zakres**: Panel administracyjny (konkretnie strona `Katalog > Produkty`).
    *   **Odpowiedzialność**:
        *   Zapewnia stylizację dla ulepszonej siatki produktów, zapewniając, że nowe kolumny i elementy interfejsu użytkownika (takie jak uchwyty do przeciągania lub przełączniki kolumn) są wyświetlane poprawnie i płynnie integrują się z motywem Panelu administracyjnego PrestaShop.
        *   Może zawierać style dla wskaźników przeciągania i upuszczania, stanów ukrytych kolumn lub określonych szerokości dla nowych kolumn.
        *   Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie: Szukaj klas z prefiksem `product-grid-pro` lub podobnych, lub specyficznych klas nagłówków/komórek tabeli, które mogą być celem niestandardowej stylizacji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie wydaje się używać niestandardowych plików `.tpl` na podstawie dostarczonego spisu. Sugeruje to, że modyfikacje siatki produktów są osiągane głównie za pomocą PHP (w nadpisanym kontrolerze) i JavaScript, który dynamicznie manipuluje istniejącą strukturą HTML generowaną przez podstawowe szablony PrestaShop dla `AdminProductsController`. Moduł prawdopodobnie wstrzykuje swoje JS i CSS za pomocą hooków, takich jak `displayBackOfficeHeader`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł przechowuje swoje ustawienia konfiguracyjne (np. preferowaną kolejność kolumn, widoczność) głównie w tabeli `ps_configuration`. Klucze konfiguracyjne byłyby zazwyczaj poprzedzone prefiksem `MYPRODUCTGRIDPRO_` lub podobnym.
    *   Nie tworzy nowych niestandardowych tabel bazy danych.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` Panelu administracyjnego. | Służy do dołączania zasobów `product_grid_admin.js` i `product_grid_admin.css` modułu, zapewniając ich załadowanie na stronie `AdminProductsController`. |
| `actionAdminProductsControllerSave` (lub podobne hooki `actionAdminController`) | Wykonywany, gdy kontroler administratora zapisuje dane. | Chociaż nie jest wyraźnie wymieniony, moduł może używać takich hooków do zapisywania niestandardowych preferencji kolumn (kolejność, widoczność) do `ps_configuration`, gdy użytkownik administratora je modyfikuje. |
| `actionAdminProductsListingFieldsModifier` (PrestaShop 1.7+) | Wykonywany przed renderowaniem pól listy produktów. | Ten hook jest kluczowy dla modułów, które modyfikują `$this->fields_list` `AdminProductsController`. Pozwala modułowi dynamicznie dodawać, usuwać lub modyfikować definicje kolumn. |
| `actionAdminProductsListingResultsModifier` (PrestaShop 1.7+) | Wykonywany po pobraniu danych produktów, ale przed renderowaniem. | Pozwala modułowi modyfikować rzeczywiste wiersze danych dla nowych kolumn (np. obliczanie „Sprzedanych sztuk” lub „Ostatniej sprzedaży”, jeśli nie są bezpośrednio dostępne z głównego zapytania o produkty). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Product Grid Pro - kolumny i układ listy produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
---
