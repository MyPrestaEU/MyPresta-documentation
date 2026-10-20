---
title: "Bloki wielu kategorii - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Bloki wielu kategorii od MyPresta.eu."
sidebar:
  label: "Bloki wielu kategorii - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Multiple Categories Blocks na MyPresta.eu](https://mypresta.eu/modules/front-office-features/multiple-categories-blocks.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/multiple-categories-blocks/)
>
> ---


# Bloki wielu kategorii

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Bloki wielu kategorii)

Jest to główny ekran konfiguracji, na którym będziesz tworzyć i zarządzać wszystkimi swoimi niestandardowymi blokami kategorii.

Po wejściu na stronę konfiguracji zobaczysz listę istniejących bloków kategorii (jeśli takie istnieją) oraz opcje dodawania nowych.

#### **Dodawanie / Edycja bloku kategorii**

Po kliknięciu „Dodaj nowy blok” lub edycji istniejącego, zostaną wyświetlone następujące ustawienia:

-   **Nazwa bloku:**
    *   **Co robi to ustawienie:** Jest to wewnętrzna nazwa dla Twojego odniesienia w Panelu administracyjnym. Pomaga Ci identyfikować różne bloki.
    *   **Wpływ zmiany tego ustawienia:** Wpływa tylko na to, jak widzisz blok w panelu administracyjnym. Nie jest widoczna dla klientów.
    *   **Zalecana wartość:** Opisowa nazwa (np. „Kategorie elektroniki na stronie głównej”, „Odzież w lewej kolumnie”).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz blok dla „Mody męskiej” w lewej kolumnie, nazwij go „Lewa kolumna - Moda męska”.
-   **Wyświetl tytuł bloku:**
    *   **Co robi to ustawienie:** Określa, czy tytuł (np. „Kategorie”) jest wyświetlany nad listą kategorii w front office.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (Tak):* Tytuł pojawi się nad blokiem kategorii. Możesz zdefiniować ten tytuł w polu „Tytuł bloku”.
        *   *Gdy wyłączone (Nie):* Nie zostanie wyświetlony żaden tytuł, tylko lista kategorii.
    *   **Zalecana wartość:** „Tak” dla większości bloków, ponieważ zapewnia kontekst klientowi.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby Twój blok po prostu wtopił się w projekt bez jawnego tytułu, ustaw go na „Nie”.
-   **Tytuł bloku:** (Pojawia się tylko, jeśli „Wyświetl tytuł bloku” jest ustawione na Tak)
    *   **Co robi to ustawienie:** Rzeczywisty tekst, który zostanie wyświetlony jako tytuł bloku w front office. Jest to wielojęzyczne.
    *   **Wpływ zmiany tego ustawienia:** Zmienia widoczny tytuł dla klientów.
    *   **Zalecana wartość:** Jasny, zwięzły tytuł (np. „Kupuj według kategorii”, „Nasze produkty”, „Działy”).
    *   **Scenariusz / przykład dla sprzedawcy:** Dla bloku pokazującego tylko kategorie „Elektronika” możesz ustawić tytuł na „Elektronika”.
-   **Hook do wyświetlania bloku:**
    *   **Co robi to ustawienie:** Wybiera, gdzie w Twoim sklepie pojawi się ten blok kategorii. Hooki to specyficzne punkty wyświetlania w Twoim motywie PrestaShop.
    *   **Wpływ zmiany tego ustawienia:** Określa fizyczną lokalizację bloku na Twojej stronie internetowej.
    *   **Zalecana wartość:** Zależy od Twojego projektu. Typowe wybory to `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`.
    *   **Scenariusz / przykład dla sprzedawcy:** Aby wyświetlić blok w lewym pasku bocznym, wybierz `displayLeftColumn`. Aby wyświetlić go w stopce, wybierz `displayFooter`.
-   **Kategoria główna:**
    *   **Co robi to ustawienie:** Jest to punkt początkowy („rodzic”) dla kategorii wyświetlanych w tym konkretnym bloku. Zostaną wyświetlone tylko ta kategoria i jej podkategorie.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Wybór „Strona główna”:* Blok wyświetli wszystkie kategorie, zaczynając od samego szczytu drzewa kategorii.
        *   *Wybór konkretnej kategorii (np. „Elektronika”):* Blok wyświetli tylko „Elektronikę” i wszystkie jej podkategorie.
    *   **Zalecana wartość:** Wybierz kategorię najwyższego poziomu, która definiuje zakres tego bloku.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz blok specjalnie dla „Odzieży”, wybierz tutaj swoją kategorię „Odzież”.
-   **Maksymalna głębokość:**
    *   **Co robi to ustawienie:** Kontroluje, ile poziomów podkategorii jest wyświetlanych w tym bloku, zaczynając od Kategorii głównej.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Ustawienie na 1:* Zostanie wyświetlona tylko sama Kategoria główna (jeśli „Wyświetl kategorię główną” jest ustawione na Tak).
        *   *Ustawienie na 2:* Zostanie wyświetlona Kategoria główna i jej bezpośrednie podkategorie.
        *   *Ustawienie na 0 (lub puste):* Zostaną wyświetlone wszystkie podkategorie, niezależnie od głębokości.
    *   **Zalecana wartość:** 2 lub 3 dla większości bloków kolumn, aby były łatwe do zarządzania. 0 dla bloków stopki, jeśli chcesz pełną mapę strony.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja kategoria „Elektronika” ma podkategorie takie jak „Aparaty” i „Laptopy”, a „Aparaty” ma „Lustrzanki” i „Bezlusterkowce”, ustawienie głębokości na 2 pokaże „Elektronika > Aparaty, Laptopy”. Ustawienie na 3 pokaże „Elektronika > Aparaty > Lustrzanki, Bezlusterkowce, Laptopy”.
-   **Dynamiczne (otwórz bieżące drzewo kategorii):**
    *   **Co robi to ustawienie:** Gdy klient przechodzi na stronę kategorii, ta opcja określa, czy blok kategorii automatycznie rozwinie się, aby pokazać bieżącą kategorię i jej podkategorie.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (Tak):* Jeśli klient jest na stronie „Lustrzanki”, blok kategorii automatycznie rozwinie „Elektronika > Aparaty > Lustrzanki”, aby pokazać ścieżkę.
        *   *Gdy wyłączone (Nie):* Blok kategorii pozostanie w swoim domyślnym, zwiniętym stanie, niezależnie od bieżącej strony.
    *   **Zalecana wartość:** „Tak” dla lepszego doświadczenia użytkownika, ponieważ pomaga klientom zrozumieć ich bieżącą lokalizację w drzewie kategorii.
    *   **Scenariusz / przykład dla sprzedawcy:** Jest to szczególnie przydatne w bocznych kolumnach, aby nawigacja była zawsze istotna dla bieżącego kontekstu przeglądania przez użytkownika.
-   **Wyświetl kategorię główną:**
    *   **Co robi to ustawienie:** Kontroluje, czy sama „Kategoria główna” (ta, którą wybrałeś powyżej) jest wyświetlana jako najwyższy element w bloku.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (Tak):* Kategoria główna będzie pierwszym klikalnym elementem w bloku.
        *   *Gdy wyłączone (Nie):* Blok zacznie wyświetlać się od bezpośrednich podkategorii Kategorii głównej.
    *   **Zalecana wartość:** „Tak”, jeśli Kategoria główna jest szeroką kategorią, taką jak „Kupuj według działu”. „Nie”, jeśli Kategoria główna jest tylko logicznym grupowaniem i chcesz zacząć bezpośrednio od jej podkategorii (np. blok „Marki”, gdzie sama „Marki” nie jest kategorią produktów).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja Kategoria główna to „Odzież męska” i chcesz, aby to był najwyższy link, ustaw na „Tak”. Jeśli chcesz, aby blok zaczynał się bezpośrednio od „Koszul”, „Spodni” itp., ustaw na „Nie”.
-   **Wyświetl liczbę produktów:**
    *   **Co robi to ustawienie:** Pokazuje liczbę produktów dostępnych w każdej kategorii obok jej nazwy w bloku.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (Tak):* Kategorie pojawią się jako „Nazwa kategorii (X)”.
        *   *Gdy wyłączone (Nie):* Zostanie wyświetlona tylko nazwa kategorii.
    *   **Zalecana wartość:** „Tak” może być pomocne dla klientów w ocenie rozmiaru kategorii, ale „Nie” może prowadzić do czystszego wyglądu. Przetestuj oba, aby zobaczyć, co pasuje do Twojego projektu.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz wyświetlić „T-shirty (125)” obok nazwy kategorii, włącz tę opcję.
-   **Wyświetl kategorie bez produktów:**
    *   **Co robi to ustawienie:** Określa, czy kategorie, które obecnie nie mają przypisanych produktów, są nadal wyświetlane w bloku.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (Tak):* Puste kategorie nadal będą się pojawiać.
        *   *Gdy wyłączone (Nie):* Puste kategorie zostaną ukryte z bloku.
    *   **Zalecana wartość:** „Nie”, aby uniknąć ślepych zaułków dla klientów i utrzymać czystą nawigację. Włącz „Tak” tylko, jeśli masz konkretny powód, aby pokazać nadchodzące kategorie.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli budujesz nową linię produktów i utworzyłeś kategorie, ale nie dodałeś jeszcze produktów, możesz tymczasowo włączyć „Tak” do testów wewnętrznych, ale zazwyczaj „Nie” dla sklepów działających.
-   **Sortuj według:**
    *   **Co robi to ustawienie:** Definiuje kolejność sortowania kategorii w bloku.
    *   **Wpływ zmiany tego ustawienia:** Zmienia kolejność, w jakiej kategorie są wyświetlane.
    *   **Zalecana wartość:** „Pozycja” (domyślna kolejność PrestaShop) lub „Nazwa” (alfabetycznie).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby Twoje kategorie pojawiały się alfabetycznie, wybierz „Nazwa”. Jeśli wolisz sortować je ręcznie w sekcji Kategorie PrestaShop, wybierz „Pozycja”.
-   **Kierunek sortowania:**
    *   **Co robi to ustawienie:** Określa kolejność rosnącą lub malejącą dla ustawienia „Sortuj według”.
    *   **Wpływ zmiany tego ustawienia:**
        *   *ASC:* Rosnąco (A-Z, 1-9).
        *   *DESC:* Malejąco (Z-A, 9-1).
    *   **Zalecana wartość:** „ASC” w większości przypadków.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli sortowałeś według „Nazwy” i chcesz A-Z, wybierz „ASC”.

#### **Zarządzanie istniejącymi blokami**

Po utworzeniu bloków zobaczysz listę z opcjami:

-   **Edytuj:** Modyfikuj ustawienia istniejącego bloku.
-   **Usuń:** Usuń blok ze swojego sklepu.
-   **Przełącz status (Włącz/Wyłącz):** Szybko włącz lub wyłącz blok bez usuwania jego konfiguracji.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Nazwa bloku** | Opisowa | Wewnętrzny identyfikator bloku. |
| | **Wyświetl tytuł bloku** | Tak | Pokazuje/ukrywa tytuł bloku dla klientów. |
| | **Tytuł bloku** | „Kategorie” (przykład) | Widoczny tytuł bloku (wielojęzyczny). |
| | **Hook do wyświetlania bloku** | `displayLeftColumn` | Określa, gdzie blok pojawia się w Twoim motywie. |
| | **Kategoria główna** | Strona główna | Ustawia punkt początkowy dla kategorii w tym bloku. |
| | **Maksymalna głębokość** | 0 (Wszystkie) | Ogranicza liczbę wyświetlanych poziomów podkategorii. |
| | **Dynamiczne (otwórz bieżące drzewo kategorii)** | Tak | Automatycznie rozwija drzewo do bieżącej kategorii. |
| | **Wyświetl kategorię główną** | Tak | Pokazuje/ukrywa samą wybraną kategorię główną. |
| | **Wyświetl liczbę produktów** | Nie | Pokazuje/ukrywa liczbę produktów obok nazw kategorii. |
| | **Wyświetl kategorie bez produktów** | Nie | Pokazuje/ukrywa kategorie, które nie mają produktów. |
| | **Sortuj według** | Pozycja | Sortuje kategorie według pozycji lub nazwy. |
| | **Kierunek sortowania** | ASC | Sortuje kategorie w kolejności rosnącej lub malejącej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój nowy blok kategorii nie wyświetla się w front office.**
O1:

-   **Sprawdź Hook:** Upewnij się, że wybrałeś prawidłowy „Hook do wyświetlania bloku” w konfiguracji modułu.
-   **Pozycja modułu:** Przejdź do **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach). Wyszukaj `Multiple Categories Blocks` i upewnij się, że jest on podpięty do wybranej pozycji i nie jest wyłączony. Może być konieczne przesunięcie jego pozycji w górę lub w dół, jeśli inne moduły się nakładają.
-   **Status modułu:** W konfiguracji modułu upewnij się, że blok jest „Włączony” (zielony znacznik).
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).

**P2: Kategorie w moim bloku nie rozwijają się lub nie wyświetlają się poprawnie.**
O2:

-   **Kategoria główna i maksymalna głębokość:** Dokładnie sprawdź ustawienia „Kategorii głównej” i „Maksymalnej głębokości”. Jeśli Maksymalna głębokość jest zbyt niska, podkategorie nie pojawią się. Jeśli Kategoria główna jest nieprawidłowa, zobaczysz niewłaściwe drzewo.
-   **Opcja dynamiczna:** Jeśli oczekujesz, że drzewo rozwinie się automatycznie podczas nawigacji, upewnij się, że „Dynamiczne (otwórz bieżące drzewo kategorii)” jest ustawione na „Tak”.
-   **Kategorie bez produktów:** Jeśli brakuje kategorii, sprawdź „Wyświetl kategorie bez produktów”. Jeśli jest ustawione na „Nie”, kategorie bez produktów zostaną ukryte.

**P3: Stylizacja bloku kategorii nie pasuje do mojego motywu.**
O3:

-   Moduł próbuje dziedziczyć style z aktywnego motywu PrestaShop. Jednak niestandardowe motywy mogą wymagać drobnych korekt CSS.
-   Często można nadpisać domyślny CSS modułu, dodając reguły do pliku `custom.css` lub `theme.css` Twojego motywu. (Szczegóły dla programistów dotyczące CSS modułu znajdują się w sekcji 7.5).
-   Dla PrestaShop 1.7/8/9 upewnij się, że używasz pliku `multicatblock-prestashop17.css`, jeśli Twój motyw tego wymaga (jest to obsługiwane automatycznie przez moduł).

**P4: Jak przetłumaczyć tytuł bloku na inne języki?**
O4:

-   Podczas edycji bloku, pole „Tytuł bloku” będzie miało obok flagi językowe. Kliknij każdą flagę, aby wprowadzić tytuł dla tego konkretnego języka.
-   Zapisz zmiany po wprowadzeniu wszystkich tłumaczeń.

**P5: Dlaczego niektóre kategorie brakuje w bloku, mimo że mają produkty?**
O5:

-   **Zakres kategorii głównej:** Upewnij się, że brakujące kategorie są faktycznie potomkami (podkategoriami) „Kategorii głównej”, którą wybrałeś dla tego konkretnego bloku. Jeśli znajdują się poza tą gałęzią, nie pojawią się.
-   **Status kategorii:** Sprawdź w **Katalog > Kategorie**, czy brakujące kategorie są „Włączone” i „Wyświetlane” (widoczne).
-   **Powiązanie produktów:** Dokładnie sprawdź, czy produkty są poprawnie powiązane z danymi kategoriami.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Bloki wielu kategorii (`multicatblocks`) stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i konfiguracji. Integruje się z front-office za pomocą różnych hooków wyświetlania i używa szablonów Smarty do renderowania. Moduł przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`, umożliwiając definiowanie wielu, odrębnych bloków kategorii. Wykorzystuje niestandardową logikę renderowania drzewa do budowania nawigacji kategorii.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani back-office. Cała logika konfiguracji i renderowania front-office jest obsługiwana w głównym pliku modułu `index.php` oraz jego powiązanych szablonach i hookach.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje niestandardowych klas `ObjectModel`. Wszystkie manipulacje danymi dla kategorii opierają się na natywnej klasie `Category` PrestaShop.

Główna logika znajduje się w `multicatblocks/index.php`:

-   **Klasa `Multicatblocks`:** Rozszerza `Module`.
    *   **`__construct()`:** Inicjalizuje szczegóły modułu, ustawia zakładki i rejestruje hooki.
    *   **`install()`:** Rejestruje niezbędne hooki (`displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`, `displayProductButtons` - choć ten ostatni może być do użytku dziedziczonego/wewnętrznego, ponieważ nie jest eksponowany w konfiguracji), tworzy domyślne wpisy konfiguracyjne.
    *   **`uninstall()`:** Czyści wpisy konfiguracyjne.
    *   **`getContent()`:** Obsługuje przesyłanie i wyświetlanie formularza konfiguracji Panelu administracyjnego. Zarządza tworzeniem, edycją i usuwaniem bloków kategorii, przechowując ich ustawienia w `Configuration::updateValue()`.
    *   **`hookDisplayHeader()`:** Wstrzykuje zasoby CSS i JavaScript do sekcji `<head>` front office.
    *   **`hookDisplayLeftColumn()`, `hookDisplayRightColumn()`, `hookDisplayFooter()`, `hookDisplayHome()`, `hookDisplayProductButtons()`:** Metody te są odpowiedzialne za pobieranie skonfigurowanych bloków dla ich odpowiednich hooków, pobieranie danych kategorii, przygotowywanie zmiennych Smarty i renderowanie szablonu `multicatblock.tpl` lub `multicatblock-footer.tpl`.
    *   **`getCategoryTree()`:** Kluczowa wewnętrzna metoda, która rekurencyjnie pobiera i strukturyzuje dane kategorii na podstawie konfiguracji bloku (kategoria główna, maksymalna głębokość, liczba produktów itp.).

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`multicatblocks/js/script.js`**:
    *   **Zakres:** Front-office.
    *   **Cel:** Obsługuje podstawowe interaktywne zachowanie drzewa kategorii, takie jak rozwijanie/zwijanie podkategorii. Prawdopodobnie wiąże zdarzenia kliknięcia z linkami kategorii lub ikonami rozwijania/zwijania.
    *   **Szczegóły:** Ten skrypt jest odpowiedzialny za „dynamiczne” zachowanie, zapewniając, że po kliknięciu kategorii jej podkategorie są ujawniane lub ukrywane, a potencjalnie podświetlana jest aktywna ścieżka kategorii.
-   **`multicatblocks/js/tree.js`**:
    *   **Zakres:** Front-office.
    *   **Cel:** Prawdopodobnie zależność lub starsza wersja funkcjonalności drzewa, lub specjalnie obsługuje początkowy stan i renderowanie struktury drzewa.
    *   **Szczegóły:** Może zawierać logikę inicjalizacji drzewa, obsługi wywołań AJAX dla danych kategorii (jeśli dotyczy, choć moduł wydaje się renderować pełne drzewo przy ładowaniu strony) lub zarządzania stanem drzewa.
-   **`multicatblocks/lib/searchTool/views/js/autocomplete.js`**:
    *   **Zakres:** Panel administracyjny (konfiguracja administratora).
    *   **Cel:** Zapewnia funkcjonalność autouzupełniania do wyboru kategorii w formularzu konfiguracji modułu, w szczególności dla ustawienia „Kategoria główna”.
    *   **Szczegóły:** Wiąże się z polem wprowadzania, wykonuje żądania AJAX do kontrolera administratora PrestaShop (prawdopodobnie `AdminCategories` lub niestandardowego, jeśli jest obecny, choć żaden nie jest wymieniony) w celu wyszukania kategorii i wyświetla sugestie.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`multicatblocks/css.css`**:
    *   **Zakres:** Front-office.
    *   **Cel:** Ogólna stylizacja bloków kategorii.
    *   **Szczegóły:** Zawiera podstawowe reguły dla elementów listy, linków i potencjalnie ikon rozwijania/zwijania. Kluczowe selektory mogą obejmować `.multicatblock`, `.multicatblock_list`, `.multicatblock_item`.
-   **`multicatblocks/lib/searchTool/views/css/autocomplete.css`**:
    *   **Zakres:** Panel administracyjny (konfiguracja administratora).
    *   **Cel:** Style dla pola wyszukiwania autouzupełniania i jego rozwijanej listy sugestii.
    *   **Szczegóły:** Zapewnia, że narzędzie wyszukiwania kategorii w panelu administracyjnym jest wizualnie spójne i przyjazne dla użytkownika.
-   **`multicatblocks/multicatblock-prestashop17.css`**:
    *   **Zakres:** Front-office.
    *   **Cel:** Specyficzne nadpisania lub dodatkowe style dostosowane do motywów PrestaShop 1.7.x, 8.x i 9.x (np. motyw Classic).
    *   **Szczegóły:** Rozwiązuje potencjalne niespójności układu lub stylizacji, które mogą pojawić się między starszymi wersjami PrestaShop a nowszymi strukturami motywów. Jest to ładowane warunkowo w zależności od wersji PS.
-   **`multicatblocks/multicatblock.css`**:
    *   **Zakres:** Front-office.
    *   **Cel:** Podstawowa stylizacja bloków kategorii, prawdopodobnie dla starszych wersji PrestaShop (1.5.x, 1.6.x) lub jako rezerwowa.
    *   **Szczegóły:** Podobnie jak `css.css`, ale może zawierać bardziej specyficzne reguły dla starszych struktur motywów.
-   **`multicatblocks/views/css/mcb-admin.css`**:
    *   **Zakres:** Panel administracyjny (konfiguracja administratora).
    *   **Cel:** Stylizacja strony konfiguracji modułu w Panelu administracyjnym PrestaShop.
    *   **Szczegóły:** Zapewnia, że formularz ustawień modułu, lista bloków i inne elementy interfejsu użytkownika administratora są dobrze prezentowane i spójne z motywem administratora PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/` - choć pliki są bezpośrednio w `multicatblocks/`):**
    *   **`multicatblocks/multicatblock.tpl`**:
        *   **Podpięty w:** `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayProductButtons`.
        *   **Wyjście:** Główna struktura bloku kategorii, w tym tytuł (jeśli włączony) i rekurencyjne drzewo kategorii generowane przez `category-tree-branch.tpl`.
    *   **`multicatblocks/multicatblock-footer.tpl`**:
        *   **Podpięty w:** `displayFooter`.
        *   **Wyjście:** Wariant bloku kategorii specjalnie dla stopki, potencjalnie z inną stylizacją lub elementami strukturalnymi. Używa również `category-tree-branch-footer.tpl`.
    *   **`multicatblocks/category-tree-branch.tpl`**:
        *   **Podpięty w:** Dołączony przez `multicatblock.tpl`.
        *   **Wyjście:** Rekurencyjnie renderuje pojedynczą gałąź drzewa kategorii. Iteruje przez podkategorie, obsługuje limity głębokości i wyświetla liczbę produktów.
    *   **`multicatblocks/category-tree-branch-footer.tpl`**:
        *   **Podpięty w:** Dołączony przez `multicatblock-footer.tpl`.
        *   **Wyjście:** Podobnie jak `category-tree-branch.tpl`, ale dostosowany do struktury bloku stopki.
-   **Szablony administratora (`views/templates/admin/` - choć `shell.tpl` jest w `multicatblocks/views/templates/admin/`):**
    *   **`multicatblocks/views/templates/admin/shell.tpl`**:
        *   **Cel:** Główny szablon strony konfiguracji modułu w Panelu administracyjnym.
        *   **Wyjście:** Formularz dodawania/edycji bloków, lista istniejących bloków i potencjalnie zawiera inne elementy specyficzne dla administratora.
-   **Szablony biblioteczne:**
    *   **`multicatblocks/lib/searchTool/views/scripts.tpl`**:
        *   **Cel:** Prawdopodobnie zawiera JavaScript niezbędny do narzędzia wyszukiwania autouzupełniania używanego w konfiguracji administratora.
        *   **Wyjście:** Tagi `<script>` lub wbudowany JavaScript dla funkcjonalności autouzupełniania.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie tworzy niestandardowych tabel SQL.
    *   Cała konfiguracja dla każdego bloku kategorii jest przechowywana w tabeli `ps_configuration`. Ustawienia każdego bloku są serializowane i przechowywane pod unikalnym kluczem konfiguracyjnym (np. `MULTICATBLOCKS_BLOCKS`).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS i JavaScript modułu. |
| `displayLeftColumn` | W lewym pasku bocznym front-office. | Renderuje skonfigurowany blok kategorii w lewej kolumnie. |
| `displayRightColumn` | W prawym pasku bocznym front-office. | Renderuje skonfigurowany blok kategorii w prawej kolumnie. |
| `displayFooter` | W sekcji stopki front-office. | Renderuje skonfigurowany blok kategorii w stopce. |
| `displayHome` | Na stronie głównej (jeśli motyw obsługuje hook `displayHome`). | Renderuje skonfigurowany blok kategorii na stronie głównej. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku dodaj do koszyka. | Renderuje skonfigurowany blok kategorii na stronach produktów (mniej powszechne dla tego modułu, ale dostępne). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Bloki wielu kategorii”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
