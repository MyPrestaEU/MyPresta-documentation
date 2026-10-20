---
title: "Górne menu poziome z rozwijanymi listami - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Górne menu poziome z rozwijanymi listami” od MyPresta.eu."
sidebar:
  label: "Górne menu poziome z rozwijanymi listami - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Top horizontal menu with dropdowns na MyPresta.eu](https://mypresta.eu/modules/front-office-features/top-horizontal-menu-with-dropdowns.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/top-horizontal-menu-with-dropdowns/)
>
> ---


# Górne menu poziome z rozwijanymi listami

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i powinny być dostępne w każdym kompatybilnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do ustawień modułu. Ten ekran umożliwia zarządzanie elementami wyświetlanymi w górnym menu poziomym oraz konfigurację paska wyszukiwania.

Strona konfiguracji jest podzielona na dwie główne sekcje: **Elementy menu** i **Pasek wyszukiwania**.

#### 2.1.1 Zarządzanie elementami menu

Ta sekcja umożliwia zdefiniowanie, które elementy pojawią się w Twoim głównym menu nawigacyjnym. Możesz dodawać linki do kategorii, stron CMS, producentów, dostawców lub niestandardowych adresów URL.

-   **Dodawanie nowego elementu menu:**

    -   **Etykieta:** Jest to tekst, który będzie wyświetlany w Twoim menu (np. „Nowości”, „Kolekcja letnia”, „O nas”). Możesz wprowadzić różne etykiety dla każdego języka obsługiwanego przez Twój sklep.
        -   *Efekt zmiany:* Bezpośrednio zmienia widoczny tekst elementu menu dla klientów.
        -   *Zalecana wartość:* Jasny, zwięzły i opisowy tekst, który dokładnie reprezentuje miejsce docelowe linku.
        -   *Scenariusz sprzedawcy:* Chcesz dodać link do swojej strony „Kontakt”. Wprowadziłbyś tutaj „Kontakt”.
    -   **Link:** Jest to adres URL, do którego będzie prowadził element menu. Możesz wybrać z listy istniejących kategorii, stron CMS, producentów lub dostawców, lub wprowadzić niestandardowy adres URL.
        -   *Efekt zmiany:* Określa, dokąd klient zostanie przeniesiony po kliknięciu tego elementu menu.
        -   *Zalecana wartość:* Zawsze upewnij się, że link jest prawidłowy i prowadzi do właściwej strony. W przypadku stron wewnętrznych użyj dostarczonych narzędzi wyboru. W przypadku linków zewnętrznych upewnij się, że wprowadzono pełny adres URL (np. `https://example.com/blog`).
        -   *Scenariusz sprzedawcy:* Chcesz połączyć się z kategorią „T-shirty”. Wybrałbyś „T-shirty” z rozwijanej listy kategorii. Jeśli chcesz połączyć się z zewnętrznym blogiem, wpisałbyś pełny adres URL bloga.
    -   **Nowe okno:** Przełącznik (Tak/Nie), który określa, czy link otwiera się w nowej karcie lub oknie przeglądarki.
        -   *Po włączeniu (Tak):* Link otworzy się w nowej karcie, pozostawiając bieżącą stronę Twojego sklepu otwartą w oryginalnej karcie.
        -   *Po wyłączeniu (Nie):* Link otworzy się w tej samej karcie, przenosząc klienta z bieżącej strony.
        -   *Zalecana wartość:* „Tak” dla linków zewnętrznych (np. blog, profil w mediach społecznościowych), aby klienci pozostali w Twoim sklepie. „Nie” dla linków wewnętrznych (kategorie, produkty, strony CMS), aby zachować naturalny przepływ przeglądania w Twojej witrynie.
        -   *Scenariusz sprzedawcy:* Łączysz się ze swoją stroną na Facebooku. Ustaw „Nowe okno” na „Tak”, aby klienci mogli łatwo wrócić do Twojego sklepu.
-   **Zarządzanie istniejącymi elementami menu:**

    -   Moduł wyświetla listę Twoich aktualnych elementów menu. Możesz przeciągać i upuszczać elementy, aby zmienić ich kolejność, co bezpośrednio wpływa na ich kolejność wyświetlania we front-office.
    -   Możesz kliknąć „Edytuj”, aby zmodyfikować etykietę, link lub ustawienie nowego okna istniejącego elementu.
    -   Możesz kliknąć „Usuń”, aby usunąć element z menu.
        -   *Efekt zmian:* Zmiana kolejności, edycja lub usunięcie elementów natychmiast aktualizuje strukturę i wygląd menu w Twoim sklepie na żywo.
        -   *Zalecany przepływ pracy:* Regularnie przeglądaj strukturę menu, aby upewnić się, że jest logiczna i aktualna. Priorytetyzuj ważne kategorie lub promocje, umieszczając je wcześniej w menu.

#### 2.1.2 Konfiguracja paska wyszukiwania

Ta sekcja kontroluje widoczność paska wyszukiwania w Twoim górnym menu.

-   **Pasek wyszukiwania:** Przełącznik (Włączony/Wyłączony) do pokazywania lub ukrywania paska wyszukiwania.
    -   *Po włączeniu (Włączony):* Pole wyszukiwania pojawi się w lub w pobliżu Twojego górnego menu poziomego, umożliwiając klientom szybkie wyszukiwanie produktów.
    -   *Po wyłączeniu (Wyłączony):* Pasek wyszukiwania zostanie ukryty z obszaru górnego menu.
    -   *Zalecana wartość:* „Włączony”. Pasek wyszukiwania jest kluczowym narzędziem nawigacyjnym dla większości sklepów e-commerce, zwłaszcza tych z dużym katalogiem produktów. Znacząco poprawia doświadczenie użytkownika.
    -   *Scenariusz sprzedawcy:* Chcesz, aby klienci łatwo znajdowali produkty, wpisując słowa kluczowe. Włącz to ustawienie. Jeśli Twój sklep jest bardzo mały i ma tylko kilka produktów, możesz rozważyć jego wyłączenie, aby zaoszczędzić miejsce, ale ogólnie nie jest to zalecane.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Elementy menu** | | |
| | Etykieta | N/A | Tekst wyświetlany dla elementu menu. |
| | Link | N/A | Adres URL, do którego prowadzi element menu. |
| | Nowe okno | Nie (dla linków wewnętrznych), Tak (dla linków zewnętrznych) | Określa, czy link otwiera się w nowej karcie. |
| | Zmiana kolejności | N/A | Zmienia kolejność wyświetlania elementów menu. |
| | Edytuj/Usuń | N/A | Modyfikuje lub usuwa istniejące elementy menu. |
| Strona konfiguracji modułu | **Pasek wyszukiwania** | Włączony | Pokazuje/ukrywa pole wyszukiwania w górnym menu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje zmiany w menu nie są widoczne we front-office.**
O: Po wprowadzeniu zmian w konfiguracji modułu, może być konieczne wyczyszczenie pamięci podręcznej PrestaShop.
- Przejdź do **Zaawansowane > Wydajność**.
- Kliknij przycisk „Wyczyść pamięć podręczną” w prawym górnym rogu.
- Wyczyść również pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+R), aby upewnić się, że widzisz najnowszą wersję swojej witryny.

**P2: Rozwijane listy wyglądają dziwnie lub nie wyświetlają się poprawnie z moim niestandardowym szablonem.**
O: Ten moduł modyfikuje standardowe górne menu PrestaShop. Niestandardowe szablony często mają własne specyficzne CSS (stylizację) dla menu.
- **Rozwiązanie:** Moduł zawiera własny CSS, aby umożliwić rozwijane listy. CSS Twojego szablonu może go nadpisywać lub powodować konflikty. Może być konieczne, aby programista internetowy zbadał CSS i dostosował style Twojego szablonu lub style modułu, aby zapewnić kompatybilność.
- **Tymczasowe sprawdzenie:** Spróbuj tymczasowo przełączyć się na domyślny szablon PrestaShop (np. Classic), aby sprawdzić, czy rozwijane listy działają tam. Jeśli tak, potwierdza to konflikt CSS związany z szablonem.

**P3: Jak przetłumaczyć etykiety moich elementów menu na inne języki?**
O: Kiedy dodajesz lub edytujesz element menu, zobaczysz selektor języka obok pola „Etykieta”.
- Kliknij ikonę flagi, aby przełączyć się na inny język.
- Wprowadź przetłumaczoną etykietę dla tego konkretnego języka.
- Powtórz dla wszystkich języków obsługiwanych przez Twój sklep.

**P4: Czy mogę mieć wiele poziomów rozwijanych list (np. Kategoria > Podkategoria > Podpodkategoria)?**
O: Moduł ulepsza standardowe menu PrestaShop, które zazwyczaj skutecznie obsługuje jeden lub dwa poziomy rozwijanych list. Chociaż technicznie możliwe jest zagnieżdżanie elementów, zbyt wiele poziomów może stać się uciążliwe dla użytkowników.
- **Najlepsza praktyka:** Celuj w maksymalnie dwa poziomy (główny element > elementy rozwijane). W przypadku głębszych hierarchii rozważ użycie stron docelowych kategorii lub nawigacji fasetowej na stronach kategorii, zamiast nadmiernie złożonych menu rozwijanych.

**P5: Pasek wyszukiwania jest włączony, ale nie wyświetla się.**
O:
- Po pierwsze, upewnij się, że ustawienie „Pasek wyszukiwania” w konfiguracji modułu jest rzeczywiście „Włączone”.
- Po drugie, sprawdź, czy Twój szablon ma specyficzny hook lub stylizację dla paska wyszukiwania w nagłówku. Niektóre szablony mogą umieszczać pasek wyszukiwania w innym miejscu lub wymagać specyficznej konfiguracji w samym szablonie.
- Jeśli problem nadal występuje, wyczyść pamięć podręczną (jak opisano w P1).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Górne menu poziome z rozwijanymi listami” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `blocktopdropdownmenu` został zaprojektowany jako standardowy moduł PrestaShop, głównie rozszerzający funkcjonalność podstawowego modułu `blocktopmenu` (lub jego odpowiednika w nowszych wersjach PS) poprzez wstrzykiwanie niestandardowego kodu JavaScript i CSS w celu umożliwienia zachowania rozwijanych list. Wykorzystuje klasyczny wzorzec MVC PrestaShop do swojej konfiguracji, używając `getContent()` dla formularza w panelu administracyjnym i rejestrując hooki do wyświetlania we front-office. Nie wprowadza nowych tabel baz danych ani złożonych struktur `ObjectModel`, zamiast tego opiera się na wartościach `Configuration` do przechowywania swoich ustawień i wykorzystuje istniejące encje PrestaShop (Kategorie, CMS itp.) do linków elementów menu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas PHP ani definicji `ObjectModel` w katalogu `classes/`. Cała logika zawarta jest w głównym pliku `blocktopdropdownmenu.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł w dużym stopniu opiera się na JavaScript, aby stworzyć funkcjonalność menu rozwijanego.

-   `blocktopdropdownmenu/js/blocktopdropdownmenu.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Jest to główny skrypt inicjalizujący dla menu rozwijanego. Prawdopodobnie zawiera logikę do zastosowania wtyczki Superfish (lub podobnej biblioteki rozwijanych list) do głównego elementu nawigacyjnego. Wiąże słuchaczy zdarzeń dla intencji najechania kursorem, obsługuje rozwijanie/zwijanie elementów menu i zapewnia responsywność mobilną (np. konwertowanie najechania kursorem na dotknięcie dla urządzeń dotykowych lub integrację z menu hamburgerowym). Może również zawierać logikę dla zachowania paska wyszukiwania, jeśli jest on dynamicznie ładowany lub przełączany.
-   `blocktopdropdownmenu/js/hoverIntent.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Wtyczka jQuery, która próbuje określić intencję użytkownika najechania kursorem na element. Pomaga zapobiegać przypadkowemu wyzwalaniu rozwijanych list poprzez wprowadzenie opóźnienia i sprawdzenie ruchu myszy, dzięki czemu menu wydaje się płynniejsze i mniej „migoczące”. Jest to zazwyczaj zależność dla Superfish.
-   `blocktopdropdownmenu/js/superfish-modified.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Jest to prawdopodobnie zmodyfikowana wersja popularnej wtyczki jQuery Superfish, która została zaprojektowana do tworzenia wielopoziomowych menu rozwijanych. Obsługuje podstawowe mechanizmy pokazywania i ukrywania podmenu po najechaniu kursorem, zarządzanie animacjami i potencjalnie dodawanie funkcji dostępności. Sufiks „modified” sugeruje, że może zawierać niestandardowe adaptacje dla struktury DOM PrestaShop lub specyficznej kompatybilności z szablonem.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zapewnia stylizację do wizualnego prezentowania menu rozwijanych.

-   `blocktopdropdownmenu/css/blocktopdropdownmenu.css`
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Odpowiedzialność:** Zawiera niestandardowe reguły CSS specyficzne dla tego modułu, potencjalnie nadpisujące domyślne style szablonu lub dodające nowe style dla elementów takich jak pasek wyszukiwania, specyficzne stany elementów menu lub ogólne dostosowania układu dla rozwijanych list.
    -   **Kluczowe selektory klas CSS:** Programiści powinni sprawdzić ten plik pod kątem klas takich jak `.sf-menu`, `.sf-menu li`, `.sf-menu li ul`, `.sf-menu li li` itp., które są typowymi selektorami Superfish, a także wszelkich niestandardowych klas wprowadzonych przez moduł.
-   `blocktopdropdownmenu/css/superfish-modified.css`
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Odpowiedzialność:** Zapewnia podstawową stylizację wizualną dla struktury menu rozwijanego Superfish. Obejmuje to style dla odstępów między elementami menu, kolorów tła, kolorów tekstu, efektów najechania kursorem, wskaźników strzałek rozwijanych list i pozycjonowania paneli rozwijanych list. Jest to kluczowe dla wizualnego wyglądu menu wielopoziomowego.
    -   **Kluczowe selektory klas CSS:** Podobnie jak `blocktopdropdownmenu.css`, ten plik będzie zawierał podstawowe selektory Superfish. Programiści mogą je nadpisać w pliku `custom.css` lub `theme.css` swojego szablonu, aby dopasować je do estetyki swojej marki.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   `blocktopdropdownmenu/blocktopdropdownmenu.tpl`
    -   **Zakres:** Szablon hooka.
    -   **Hook:** `displayTop` (i potencjalnie `displayNav`, jeśli struktura szablonu na to pozwala).
    -   **Odpowiedzialność:** Jest to główny szablon front-office odpowiedzialny za renderowanie struktury HTML górnego menu poziomego, w tym głównych elementów menu i ich zagnieżdżonych rozwijanych list. Iteruje przez elementy menu skonfigurowane w panelu administracyjnym i generuje strukturę `<ul><li>` wymaganą przez JavaScript Superfish. Zawiera również logikę renderowania paska wyszukiwania, jeśli jest włączony.
-   `blocktopdropdownmenu/views/templates/admin/advert.tpl`
    -   **Zakres:** Szablon administracyjny.
    -   **Odpowiedzialność:** Prawdopodobnie wyświetla reklamę lub wiadomość promocyjną od MyPresta.eu na stronie konfiguracji modułu w Panelu administracyjnym.
-   `blocktopdropdownmenu/views/templates/admin/_configure/helpers/form/form.tpl`
    -   **Zakres:** Szablon administracyjny.
    -   **Odpowiedzialność:** Ten szablon jest standardowym szablonem pomocniczym PrestaShop używanym do renderowania głównego formularza konfiguracji modułu. Definiuje strukturę i pola do zarządzania elementami menu i ustawieniem paska wyszukiwania, zgodnie z konfiguracją w `getContent()`.
-   `blocktopdropdownmenu/views/templates/admin/_configure/helpers/list/list_content.tpl`
    -   **Zakres:** Szablon administracyjny.
    -   **Odpowiedzialność:** Ten szablon jest standardowym szablonem pomocniczym PrestaShop używanym do renderowania listy elementów menu w formularzu konfiguracji, umożliwiając przeciąganie i upuszczanie w celu zmiany kolejności, edycji i usuwania.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel baz danych.
    -   Ustawienia konfiguracji (np. `MOD_blocktopdropdownmenu_ITEMS`, `MOD_blocktopdropdownmenu_SEARCH`) są przechowywane w tabeli `ps_configuration`. `MOD_blocktopdropdownmenu_ITEMS` będzie przechowywać serializowaną tablicę lub ciąg JSON reprezentujący strukturę menu.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje zasoby CSS i JavaScript (`blocktopdropdownmenu.js`, `hoverIntent.js`, `superfish-modified.js`, `blocktopdropdownmenu.css`, `superfish-modified.css`) wymagane do funkcjonalności rozwijanych list. |
| `displayTop` | Zazwyczaj w głównym obszarze nagłówka szablonu. | Renderuje główną strukturę HTML menu poziomego z rozwijanymi listami i paskiem wyszukiwania. |
| `displayNav` | Często w bardzo górnym pasku nawigacyjnym (powyżej `displayTop`). | Może być używany przez niektóre szablony do wyświetlania menu lub do dodatkowych elementów nawigacyjnych. Moduł może się tutaj rejestrować w celu szerszej kompatybilności z szablonami. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu produktu. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do produktów, zapewniając aktualność elementów menu prowadzących do produktów. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu lub usuwania elementów menu prowadzących do usuniętego produktu. |
| `actionObjectManufacturerAddAfter` | Po dodaniu producenta. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do producentów. |
| `actionObjectManufacturerUpdateAfter` | Po zaktualizowaniu producenta. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do producentów. |
| `actionObjectManufacturerDeleteAfter` | Po usunięciu producenta. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu lub usuwania elementów menu prowadzących do usuniętego producenta. |
| `actionObjectSupplierAddAfter` | Po dodaniu dostawcy. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do dostawców. |
| `actionObjectSupplierUpdateAfter` | Po zaktualizowaniu dostawcy. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do dostawców. |
| `actionObjectSupplierDeleteAfter` | Po usunięciu dostawcy. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu lub usuwania elementów menu prowadzących do usuniętego dostawcy. |
| `actionObjectCmsAddAfter` | Po dodaniu strony CMS. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do stron CMS. |
| `actionObjectCmsUpdateAfter` | Po zaktualizowaniu strony CMS. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu związanej z linkami do stron CMS. |
| `actionObjectCmsDeleteAfter` | Po usunięciu strony CMS. | Potencjalnie używane do czyszczenia pamięci podręcznej modułu lub usuwania elementów menu prowadzących do usuniętej strony CMS. |
| `actionShopDataDuplication` | Gdy sklep jest duplikowany (w kontekście wielu sklepów). | Zapewnia prawidłowe duplikowanie konfiguracji modułu (elementy menu, ustawienie paska wyszukiwania) dla nowego sklepu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Górne menu poziome z rozwijanymi listami”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań związanych z funkcjonalnością i kompatybilnością modułu.
