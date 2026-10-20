---
title: "Media / Menedżer plików - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop Media / Menedżer plików od MyPresta.eu."
sidebar:
  label: "Media / Menedżer plików - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Media / Files Manager na MyPresta.eu](https://mypresta.eu/modules/administration-tools/media-files-manager.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/media-files-manager/)
>
> ---


# Media / Menedżer plików

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Moduł wymaga uprawnień do zapisu w katalogach, którymi zarządza, co jest standardem dla instalacji PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji zostaniesz przekierowany na stronę konfiguracji modułu. Strona ta służy przede wszystkim do integracji menedżera plików z panelem administracyjnym PrestaShop i zarządzania jego podstawowymi ustawieniami.

Główny ekran konfiguracji wyświetli bezpośrednio interfejs menedżera plików. Ten interfejs to w pełni funkcjonalna przeglądarka plików, podobna do tej, którą widzisz na swoim komputerze, ale działająca na plikach serwera.

**Kluczowe obszary i funkcjonalność w interfejsie menedżera plików:**

1.  **Panel nawigacji (Lewy pasek boczny):**

    -   **Co to robi:** Pokazuje strukturę katalogów serwera w postaci drzewa, zazwyczaj zaczynając od folderu głównego PrestaShop. Możesz klikać foldery, aby się po nich poruszać.
    -   **Efekt użycia:** Pozwala szybko przechodzić między różnymi częściami instalacji PrestaShop (np. `img/p` dla obrazów produktów, `themes/yourtheme/css` dla arkuszy stylów).
    -   **Zalecana wartość:** Użyj tego do nawigacji do konkretnego folderu, w którym chcesz zarządzać plikami.
2.  **Obszar listy plików (Panel główny):**

    -   **Co to robi:** Wyświetla zawartość (pliki i podfoldery) aktualnie wybranego folderu. Zobaczysz nazwy plików, rozmiary, typy i daty modyfikacji.
    -   **Efekt użycia:** Tutaj będziesz wykonywać większość operacji na plikach.
    -   **Zalecana wartość:** Zapoznaj się z ikonami i informacjami przedstawionymi dla każdego pliku.
3.  **Pasek narzędzi (Góra obszaru listy plików):**

    -   **Co to robi:** Zawiera różne przyciski i narzędzia do operacji na plikach. Typowe narzędzia to:
        -   **Prześlij:** Przesyłaj pliki z komputera do bieżącego folderu serwera.
        -   **Nowy folder:** Utwórz nowy katalog.
        -   **Nowy plik:** Utwórz nowy pusty plik (np. `.txt`, `.html` lub `.css`).
        -   **Kopiuj, Wytnij, Wklej:** Standardowe operacje na plikach.
        -   **Zmień nazwę:** Zmień nazwę pliku lub folderu.
        -   **Usuń:** Usuń pliki lub foldery (używaj z najwyższą ostrożnością!).
        -   **Edytuj:** Otwórz edytor tekstu dla wybranych plików tekstowych (np. `.php`, `.css`, `.js`, `.html`).
        -   **Podgląd:** Wyświetlaj obrazy lub inne obsługiwane typy plików bezpośrednio.
        -   **Szukaj:** Znajdź pliki w bieżącym katalogu lub rekurencyjnie.
        -   **Opcje widoku:** Zmień sposób wyświetlania plików (lista, ikony itp.).
    -   **Efekt użycia tych narzędzi:** Bezpośrednio manipuluje plikami i folderami na serwerze.
    -   **Zalecana wartość:** Zawsze dokładnie sprawdzaj swoje wybory przed wykonaniem działań takich jak „Usuń” lub „Zmień nazwę”.
4.  **Menu kontekstowe (Prawy przycisk myszy):**

    -   **Co to robi:** Kliknięcie prawym przyciskiem myszy na pliku lub folderze często powoduje wyświetlenie menu kontekstowego z szybkim dostępem do typowych operacji, takich jak „Otwórz”, „Edytuj”, „Zmień nazwę”, „Usuń”, „Pobierz”, „Pobierz informacje” itp.
    -   **Efekt użycia:** Zapewnia szybszy sposób wykonywania działań na pojedynczych elementach.
    -   **Zalecana wartość:** Przeglądaj opcje prawego przycisku myszy dla różnych typów plików.

**Specyficzne ustawienia (jeśli istnieją, na podstawie `mypresta_updates`, `update_`, `updatev_`):**

Metoda `getContent()` modułu przede wszystkim renderuje sam interfejs menedżera plików. Klucze konfiguracyjne `mypresta_updates`, `update_` i `updatev_` to standardowe wewnętrzne klucze używane przez moduły MyPresta.eu do zarządzania powiadomieniami o aktualizacjach i sprawdzania wersji. Nie są to ustawienia, z którymi zazwyczaj bezpośrednio wchodzisz w interakcje jako sprzedawca.

-   **Co robią te ustawienia:** Są to wewnętrzne flagi, które pomagają modułowi komunikować się z serwerem aktualizacji MyPresta.eu w celu sprawdzenia nowych wersji i wyświetlania powiadomień w panelu administracyjnym PrestaShop, jeśli dostępna jest aktualizacja.
-   **Efekt zmiany tych ustawień:** Nie możesz ich bezpośrednio zmieniać. Są one zarządzane automatycznie przez moduł. Gdyby zostały ręcznie zmienione (co nie jest zalecane), mogłoby to wpłynąć na zdolność modułu do powiadamiania o nowych wersjach.
-   **Zalecana wartość:** Pozostaw je bez zmian. Służą do wewnętrznego zarządzania modułem.
-   **Scenariusz / przykład dla sprzedawcy:** Nie musisz się tym martwić. Moduł automatycznie poinformuje Cię o wydaniu nowej wersji, zachęcając do pobrania i zainstalowania jej z konta MyPresta.eu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie wprowadza żadnych dodatkowych dedykowanych ekranów administracyjnych ani niestandardowych kontrolerów poza swoją główną stroną konfiguracji. Cała funkcjonalność zarządzania plikami jest osadzona bezpośrednio w interfejsie konfiguracji modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok             | Ustawienie / Opcja                                | Domyślne / Zalecane | Cel i wpływ                                                              |
| :------------------------ | :------------------------------------------------ | :------------------ | :----------------------------------------------------------------------- |
| Strona konfiguracji modułu | **Panel nawigacji**                               | N/A                 | Przeglądaj katalogi serwera.                                            |
| Strona konfiguracji modułu | **Obszar listy plików**                           | N/A                 | Wyświetlaj pliki/foldery i wchodź z nimi w interakcje.                   |
| Strona konfiguracji modułu | **Pasek narzędzi (Prześlij, Nowy folder, Edytuj, Usuń itp.)** | N/A                 | Wykonuj operacje na plikach (przesyłaj, twórz, modyfikuj, usuwaj).      |
| Strona konfiguracji modułu | **Menu kontekstowe (Prawy przycisk myszy)**      | N/A                 | Szybki dostęp do operacji na plikach.                                    |
| Strona konfiguracji modułu | `mypresta_updates`                                | Wewnętrzne           | Wewnętrzna flaga dla powiadomień o aktualizacjach.                      |
| Strona konfiguracji modułu | `update_`                                         | Wewnętrzne           | Wewnętrzna flaga dla powiadomień o aktualizacjach.                      |
| Strona konfiguracji modułu | `updatev_`                                        | Wewnętrzne           | Wewnętrzna flaga dla powiadomień o aktualizacjach.                      |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Przesłałem obraz, ale nie wyświetla się na stronie mojego produktu.**
O:

-   **Sprawdź ścieżkę:** Upewnij się, że przesłałeś obraz do prawidłowego katalogu, którego oczekuje PrestaShop (zazwyczaj `img/p/` z podfolderami).
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop (lub pamięć podręczna przeglądarki) może uniemożliwić natychmiastowe wyświetlenie nowych obrazów. Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym i kliknij „Wyczyść pamięć podręczną”. Spróbuj również wyczyścić pamięć podręczną przeglądarki.
-   **Uprawnienia:** Upewnij się, że folder, do którego przesłałeś obraz, ma prawidłowe uprawnienia do zapisu (zazwyczaj 755 lub 775). Chociaż moduł zazwyczaj to obsługuje, czasami konfiguracje serwera mogą być rygorystyczne.

**P: Edytowałem plik CSS, ale wygląd mojego sklepu się nie zmienił.**
O:

-   **Wyczyść pamięć podręczną:** To najczęstszy powód. Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną PrestaShop. Wyczyść również pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+R zazwyczaj wymusza twarde odświeżenie).
-   **Prawidłowy plik:** Sprawdź dwukrotnie, czy edytowałeś prawidłowy plik CSS, który faktycznie ładuje Twój motyw. Niektóre motywy używają skompilowanego CSS lub wielu arkuszy stylów.
-   **Błędy składni:** Jeśli wprowadziłeś błąd składni w swoim CSS, może to uniemożliwić prawidłowe załadowanie arkusza stylów. Użyj narzędzi deweloperskich przeglądarki (F12), aby sprawdzić błędy CSS.

**P: Przypadkowo usunąłem plik/folder. Czy mogę go odzyskać?**
O:

-   **Natychmiast przywróć z kopii zapasowej:** Dlatego regularne kopie zapasowe są kluczowe. Jeśli masz aktualną kopię zapasową plików serwera, przywróć usunięty element z niej.
-   **Skontaktuj się z dostawcą hostingu:** Niektórzy dostawcy hostingu utrzymują codzienne kopie zapasowe i mogą być w stanie przywrócić pojedyncze pliki.
-   **Ostrzeżenie:** Sam moduł nie ma funkcji „kosza” ani „cofnij”. Usunięcie jest trwałe.

**P: Menedżer plików wygląda na uszkodzony lub nie ładuje się poprawnie.**
O:

-   **Sprawdź konsolę przeglądarki:** Otwórz narzędzia deweloperskie przeglądarki (F12) i poszukaj błędów w zakładce „Konsola”. Może to wskazywać na konflikty JavaScript lub problemy po stronie serwera.
-   **Konflikty modułów:** Spróbuj wyłączyć inne ostatnio zainstalowane moduły, aby sprawdzić, czy występuje konflikt.
-   **Logi błędów serwera:** Sprawdź logi błędów PHP serwera pod kątem wszelkich powiązanych błędów.
-   **Uprawnienia:** Upewnij się, że pliki i foldery modułu mają prawidłowe uprawnienia do odczytu/zapisu.

**P: Czy mogę ograniczyć dostęp do niektórych folderów dla różnych użytkowników administracyjnych?**
O:

-   Ten moduł, w swojej obecnej wersji, zapewnia pojedynczy interfejs menedżera plików z pełnym dostępem. Natywny system uprawnień PrestaShop dla modułów zazwyczaj przyznaje pełny dostęp lub brak dostępu do konfiguracji modułu. Granularne uprawnienia na poziomie folderów dla różnych użytkowników panelu administracyjnego nie są wbudowaną funkcją tego konkretnego modułu. Aby zaimplementować taką funkcję, potrzebne byłyby niestandardowe rozwiązania.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Media / Menedżer plików” (`fmpro`) jest zbudowany wokół popularnego, otwartego menedżera plików **elFinder**. Integruje on elFinder bezpośrednio z panelem administracyjnym PrestaShop, głównie za pośrednictwem metody `getContent()` modułu. Oznacza to, że podstawowa logika zarządzania plikami i interfejs użytkownika są obsługiwane przez solidny backend JavaScript i PHP elFinder, a moduł PrestaShop działa jako opakowanie i punkt wejścia.

Sam moduł jest standardowym modułem PrestaShop, rozszerzającym `Module`. Nie wprowadza niestandardowych tabel baz danych (poza `ps_configuration` dla własnych ustawień wewnętrznych) ani złożonych struktur `ObjectModel`. Jego główną funkcją jest inicjowanie i konfigurowanie biblioteki elFinder w kontekście administratora PrestaShop.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów front-office ani back-office w tradycyjnym sensie PrestaShop (tj. plików w `controllers/front/` lub `controllers/admin/`).
Sama biblioteka elFinder ma własny konektor backendu (zazwyczaj skrypt PHP), który obsługuje operacje na plikach. Ten konektor jest prawdopodobnie zintegrowany lub wywoływany bezpośrednio z głównego pliku modułu `fmpro.php` lub oddzielnego skryptu PHP w katalogu `fmpro/php/`, działającego jako obsługa po stronie serwera dla żądań AJAX elFinder.

### 4.3 Podstawowe klasy i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas ani modeli w katalogu `classes/`. Podstawowa logika zarządzania plikami jest obsługiwana przez zintegrowaną bibliotekę elFinder.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł w dużym stopniu opiera się na JavaScript dla swojego interfejsu front-end, głównie na bibliotece elFinder. Wszystkie pliki JS znajdują się w `fmpro/js/`.

-   `fmpro/js/elfinder.full.js`: Jest to główny plik biblioteki elFinder, zawierający całą podstawową funkcjonalność interfejsu użytkownika menedżera plików, interakcji i komunikacji AJAX z backendem. Jest to kompleksowy skrypt, który zasila cały interfejs.
-   `fmpro/js/extras/editors.default.js`: Zapewnia domyślną funkcjonalność edytora tekstu w elFinder, umożliwiając użytkownikom bezpośrednią edycję plików tekstowych.
-   `fmpro/js/extras/quicklook.googledocs.js`: Ulepsza funkcję „szybkiego podglądu” poprzez integrację z Google Docs w celu podglądu niektórych typów dokumentów.
-   `fmpro/js/i18n/elfinder.*.js`: Duża kolekcja plików internacjonalizacji (i18n), zapewniająca tłumaczenia interfejsu elFinder na różne języki (np. `elfinder.fr.js` dla francuskiego, `elfinder.es.js` dla hiszpańskiego). Są one ładowane na podstawie ustawień językowych użytkownika.
-   `fmpro/js/i18n/help/*.html.js`: Zawiera zlokalizowaną zawartość pomocy dla interfejsu elFinder, osadzoną jako ciągi JavaScript.
-   `fmpro/js/proxy/elFinderSupportVer1.js`: Prawdopodobnie warstwa kompatybilności lub skrypt proxy dla starszych wersji elFinder lub specyficznych konfiguracji serwera.
-   `fmpro/js/worker/calcfilehash.js`: Skrypt web worker do obliczania skrótów plików, potencjalnie używany do sprawdzania integralności lub buforowania.
-   `fmpro/js/worker/quicklook.tiff.js`: Skrypt web worker specjalnie do obsługi podglądów obrazów TIFF.
-   `fmpro/js/worker/quicklook.unzip.js`: Skrypt web worker do obsługi podglądów plików ZIP lub listowania zawartości.

**Uwagi dla programistów:**

-   Biblioteka elFinder jest samodzielna. Programiści rozszerzający moduł będą głównie wchodzić w interakcje z API elFinder, jeśli będą musieli dostosować jego zachowanie lub zintegrować go z innymi komponentami.
-   Do stylizacji zazwyczaj preferowany jest niestandardowy CSS zamiast modyfikowania tych podstawowych plików JS.
-   W przypadku lokalizacji upewnij się, że prawidłowy plik `elfinder.LANG.js` jest ładowany na podstawie języka panelu administracyjnego PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera pliki CSS do stylizacji interfejsu elFinder. Znajdują się one w `fmpro/css/`.

-   `fmpro/css/elfinder.full.css`: Jest to główny arkusz stylów dla interfejsu elFinder, definiujący układ, ikony, kolory i ogólny wygląd menedżera plików.
-   `fmpro/css/theme.css`: Ten plik prawdopodobnie zawiera dodatkowe style lub nadpisania, aby zintegrować elFinder bardziej płynnie z motywem panelu administracyjnego PrestaShop lub aby zapewnić specyficzne dostosowania motywu dla samego elFinder.

**Uwagi dla programistów:**

-   Aby dostosować wygląd menedżera plików, programiści powinni utworzyć własny plik CSS i załadować go *po* `elfinder.full.css` i `theme.css`, aby nadpisać określone style.
-   Kluczowe selektory klas CSS są zazwyczaj poprzedzone prefiksem `elfinder-` (np. `.elfinder-navbar`, `.elfinder-cwd-wrapper`).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie wymienia jawnie żadnych plików `.tpl` w katalogu `views/templates/` w dostarczonym spisie. Sugeruje to, że interfejs elFinder jest renderowany bezpośrednio za pomocą JavaScript i HTML generowanego w metodzie `getContent()` głównego pliku `fmpro.php`, lub że wewnętrzny mechanizm szablonowania elFinder jest używany wewnętrznie, bez udostępniania plików `.tpl` w strukturze `views/templates/` modułu.

Metoda `getContent()` prawdopodobnie wyprowadzi niezbędny kontener HTML (`<div>`), w którym JavaScript elFinder zainicjuje i wyrenderuje menedżera plików.

### 4.7 Schemat bazy danych i mapa hooków

**Tabele baz danych**:
Moduł nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoje wewnętrzne ustawienia konfiguracyjne (takie jak `mypresta_updates`, `update_`, `updatev_`) w standardowej tabeli PrestaShop `ps_configuration`.

-   `ps_configuration`:
    -   `name`: `MYPRESTA_UPDATES_FMPRO` (lub podobne, do sprawdzania aktualizacji)
    -   `name`: `UPDATE_FMPRO` (lub podobne, do sprawdzania aktualizacji)
    -   `name`: `UPDATEV_FMPRO` (lub podobne, do sprawdzania aktualizacji)

**Tabela zarejestrowanych hooków**:
Główną funkcją modułu jest dostarczanie narzędzia administracyjnego, więc zazwyczaj nie rejestruje on wielu hooków front-office. Opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, ale jest to prawdopodobnie ogólne stwierdzenie dla modułów MyPresta.eu i nie dotyczy konkretnej implementacji tego modułu, ponieważ jest to narzędzie administracyjne.

Biorąc pod uwagę jego charakter jako narzędzia administracyjnego, moduł wchodziłby w interakcje głównie z hookami back-office, jeśli w ogóle, w celu dodania pozycji menu lub integracji z istniejącymi stronami administracyjnymi. Jednak dostarczone informacje nie wymieniają jawnie żadnych zarejestrowanych hooków. Najczęstszym punktem integracji dla takiego modułu jest bezpośrednio jego metoda `getContent()`, do której uzyskuje się dostęp po kliknięciu „Konfiguruj” w Menedżerze modułów.

Gdyby miał zarejestrować jakiekolwiek hooki, typowe dla narzędzi administracyjnych mogłyby obejmować:

-   `displayBackOfficeHeader`: Aby dołączyć swoje zasoby CSS/JS w panelu administracyjnym.
-   `displayAdminProductsExtra`: (Mniej prawdopodobne dla ogólnego menedżera plików, ale możliwe dla specyficznych przesyłanych plików związanych z produktami).
-   `actionAdminControllerSetMedia`: Aby załadować zasoby dla swojej strony konfiguracji.

Biorąc pod uwagę projekt modułu, jego głównym punktem wejścia jest strona konfiguracji, gdzie inicjowana jest instancja elFinder.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Media / Menedżer plików” prosimy o zapoznanie się z kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu i integracji z Twoim sklepem PrestaShop.
