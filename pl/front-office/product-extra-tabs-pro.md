---
title: "Product Extra Tabs Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Product Extra Tabs Pro od MyPresta.eu."
sidebar:
  label: "Product Extra Tabs Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product Extra Tabs Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-extra-tabs-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-extra-tabs-pro/)
>
> ---


# Product Extra Tabs Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Product Extra Tabs Pro” jest konfigurowany głównie bezpośrednio ze strony edycji produktu, co pozwala na zarządzanie zakładkami dla każdego produktu z osobna. Główny ekran konfiguracji modułu obsługuje ustawienia globalne.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do głównej konfiguracji, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Product Extra Tabs Pro” i kliknij „Konfiguruj”.

Na tym ekranie znajdziesz ustawienia, które mają zastosowanie globalnie lub definiują zachowanie modułu w całym Twoim sklepie.

-   **Ustawienie: Włącz edytor TinyMCE dla zawartości zakładki**

    *   **Co robi to ustawienie:** Ten przełącznik określa, czy edytor tekstu sformatowanego (TinyMCE, ten sam edytor, którego PrestaShop używa do opisów produktów) jest dostępny podczas tworzenia lub edycji zawartości zakładki.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Zobaczysz przyjazny dla użytkownika edytor z opcjami formatowania (pogrubienie, kursywa, listy, obrazy, linki itp.) podczas dodawania treści do dodatkowych zakładek. Ułatwia to tworzenie atrakcyjnych wizualnie i dobrze ustrukturyzowanych treści bez znajomości HTML.
        *   *Gdy wyłączone:* Będziesz mieć tylko obszar zwykłego tekstu dla zawartości zakładki. Musiałbyś ręcznie pisać tagi HTML, aby sformatować tekst, co jest bardziej złożone dla użytkowników nietechnicznych.
    *   **Zalecana wartość:** **TAK**
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz dodać obrazy, filmy lub stylizowany tekst do swoich zakładek (np. zakładka „Tabela rozmiarów” z obrazem lub zakładka „Gwarancja” z pogrubionymi kluczowymi terminami), włącz to. Jeśli potrzebujesz tylko zwykłego tekstu, możesz to wyłączyć dla prostszego interfejsu.
-   **Ustawienie: Wyświetlaj zakładki globalnie (dla wszystkich produktów)**

    *   **Co robi to ustawienie:** Ta opcja pozwala tworzyć „globalne” zakładki, które automatycznie pojawiają się na *każdej* stronie produktu w Twoim sklepie. Jest to przydatne dla informacji, które mają zastosowanie uniwersalne, takich jak ogólne zasady wysyłki lub historie marki.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Wszelkie zakładki utworzone w interfejsie konfiguracji modułu (nie na poszczególnych stronach produktów) będą wyświetlane na wszystkich stronach produktów. Następnie możesz zarządzać tymi globalnymi zakładkami z głównej konfiguracji modułu.
        *   *Gdy wyłączone:* Zakładki muszą być tworzone i zarządzane indywidualnie dla każdego produktu z jego odpowiedniej strony edycji produktu. Globalne zakładki nie będą wyświetlane.
    *   **Zalecana wartość:** **TAK** (jeśli masz informacje, które dotyczą wszystkich produktów, w przeciwnym razie NIE).
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz dodać zakładkę „Polityka zwrotów”, która jest identyczna dla wszystkich produktów. Włącz to, utwórz zakładkę tutaj, a pojawi się ona na każdej stronie produktu. Jeśli potrzebujesz tylko unikalnych zakładek dla konkretnych produktów, pozostaw to wyłączone.
-   **Ustawienie: Pozycja wyświetlania zakładki**

    *   **Co robi to ustawienie:** To rozwijane menu kontroluje, gdzie dodatkowe zakładki są wyświetlane na stronie produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcja: `displayProductExtraContent` (Domyślna):* Zakładki pojawią się w standardowym obszarze treści produktu, zazwyczaj poniżej głównych szczegółów produktu, obok domyślnych zakładek opisu/karty danych. Jest to najczęstsza i zalecana pozycja.
        *   *Opcja: `displayFooterProduct` (tylko PrestaShop 1.6):* Zakładki pojawią się w sekcji stopki strony produktu. Może to być odpowiednie dla mniej krytycznych, uzupełniających informacji.
        *   *Opcja: `displayRightColumnProduct` (tylko PrestaShop 1.6):* Zakładki pojawią się w prawej kolumnie strony produktu. Jest to mniej powszechne dla zakładek i może zależeć w dużej mierze od układu Twojego motywu.
        *   *Opcja: `displayLeftColumnProduct` (tylko PrestaShop 1.6):* Zakładki pojawią się w lewej kolumnie strony produktu. Podobnie jak w przypadku prawej kolumny, jest to mniej powszechne dla zakładek.
    *   **Zalecana wartość:** `displayProductExtraContent`
    *   **Scenariusz / przykład dla sprzedawcy:** Dla większości sklepów `displayProductExtraContent` zapewnia najlepsze doświadczenie użytkownika, ponieważ grupuje wszystkie informacje związane z produktem. Jeśli Twój motyw ma bardzo specyficzny układ lub chcesz zmniejszyć nacisk na zakładki, możesz eksperymentować z pozycjami w stopce lub kolumnach (chociaż są one mniej powszechne dla zakładek).

#### 2.1.1 Zarządzanie zakładkami globalnymi (jeśli włączono „Wyświetlaj zakładki globalnie”)

Jeśli włączyłeś „Wyświetlaj zakładki globalnie”, ta sekcja pojawi się na stronie konfiguracji modułu. Tutaj możesz dodawać, edytować lub usuwać zakładki, które będą wyświetlane na *wszystkich* stronach produktów.

-   **Przycisk Dodaj nową zakładkę:** Kliknij, aby otworzyć formularz, w którym możesz zdefiniować nową globalną zakładkę.
    *   **Tytuł zakładki:** Tekst, który pojawia się na samej zakładce (np. „Informacje o wysyłce”, „Gwarancja”). Zazwyczaj jest wielojęzyczny.
    *   **Zawartość zakładki:** Rzeczywista zawartość, która pojawia się po kliknięciu zakładki. Użyj edytora TinyMCE, jeśli jest włączony. Jest to również wielojęzyczne.
    *   **Aktywna:** Przełącznik do włączania lub wyłączania zakładki bez jej usuwania.
    *   **Pozycja:** Liczba kontrolująca kolejność zakładki względem innych globalnych zakładek. Niższe liczby pojawiają się jako pierwsze.
-   **Lista istniejących zakładek:** Tabela pokazująca wszystkie aktualnie skonfigurowane globalne zakładki.
    *   **Ikona edycji:** Kliknij, aby zmodyfikować tytuł, zawartość lub ustawienia istniejącej zakładki.
    *   **Ikona usuwania:** Kliknij, aby trwale usunąć globalną zakładkę.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

Głównym sposobem zarządzania dodatkowymi zakładkami specyficznymi dla produktu jest bezpośrednio ze **strony edycji produktu** w Panelu Administracyjnym PrestaShop.

-   **Nazwa ekranu i lokalizacja w menu:**

    1.  Przejdź do **Katalog > Produkty**.
    2.  Edytuj istniejący produkt lub utwórz nowy.
    3.  W interfejsie edycji produktu poszukaj nowej zakładki lub sekcji oznaczonej jako **„Extra Tabs Pro”** (lub podobnej, w zależności od Twojej wersji PrestaShop i motywu).
-   **Dostępne akcje i ustawienia w sekcji „Extra Tabs Pro” na stronie produktu:**

    *   **Przycisk Dodaj nową zakładkę:** Kliknij, aby utworzyć nową zakładkę *specjalnie dla tego produktu*.
        *   **Tytuł zakładki:** Wprowadź tytuł dla tej zakładki specyficznej dla produktu (np. „Specyfikacje techniczne dla Modelu X”). Jest to wielojęzyczne.
        *   **Zawartość zakładki:** Wprowadź zawartość dla tej zakładki. Edytor TinyMCE będzie dostępny, jeśli jest włączony w głównej konfiguracji modułu. Jest to wielojęzyczne.
        *   **Aktywna:** Włącz/wyłącz tę konkretną zakładkę dla tego produktu.
        *   **Pozycja:** Ustaw kolejność wyświetlania tej zakładki względem innych zakładek na tej stronie produktu.
    *   **Lista istniejących zakładek:** Tabela pokazująca wszystkie dodatkowe zakładki, które utworzyłeś dla *tego konkretnego produktu*.
        *   **Ikona edycji:** Zmodyfikuj tytuł, zawartość lub status istniejącej zakładki specyficznej dla produktu.
        *   **Ikona usuwania:** Usuń zakładkę z tego produktu.
-   **Efekt zmian:**

    *   Kiedy dodajesz, edytujesz lub usuwasz zakładkę z sekcji „Extra Tabs Pro” produktu, te zmiany *wpływają tylko na tę konkretną stronę produktu*.
    *   Zawartość i widoczność tych zakładek są natychmiast aktualizowane na stronie produktu w front office po zapisaniu zmian.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zidentyfikuj uniwersalne informacje:** Jeśli masz informacje, które dotyczą WSZYSTKICH produktów (np. ogólna wysyłka, zwroty, historia marki), użyj funkcji **zakładek globalnych** w głównej konfiguracji modułu.
    2.  **Zidentyfikuj informacje specyficzne dla produktu:** W przypadku szczegółów unikalnych dla produktu (np. konkretne wymiary, skład materiału, instrukcje użytkowania, recenzje wideo), przejdź do **indywidualnej strony edycji produktu** i użyj tam sekcji „Extra Tabs Pro”.
    3.  **Użyj edytora TinyMCE:** Zawsze włączaj edytor TinyMCE w głównej konfiguracji modułu, aby ułatwić tworzenie i formatowanie treści.
    4.  **Regularnie przeglądaj:** Okresowo sprawdzaj strony produktów, aby upewnić się, że zakładki wyświetlają się poprawnie, a zawartość jest aktualna.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz edytor TinyMCE | TAK | Zapewnia edytor tekstu sformatowanego dla zawartości zakładki; łatwiejsze formatowanie. |
| | Wyświetlaj zakładki globalnie | NIE (lub TAK, jeśli potrzebne) | TAK: Globalne zakładki pojawiają się na wszystkich produktach. NIE: Zakładki są specyficzne dla produktu. |
| | Pozycja wyświetlania zakładki | `displayProductExtraContent` | Kontroluje, gdzie zakładki pojawiają się na stronie produktu. |
| | **Lista zakładek globalnych** | (N/A) | Dodaj/Edytuj/Usuń zakładki, które pojawiają się na WSZYSTKICH stronach produktów. |
| **Strona edycji produktu** | **Sekcja Extra Tabs Pro** | (N/A) | Dodaj/Edytuj/Usuń zakładki specyficzne dla bieżącego produktu. |
| | Tytuł zakładki | (Zdefiniowany przez użytkownika) | Widoczna nazwa zakładki na stronie produktu. |
| | Zawartość zakładki | (Zdefiniowana przez użytkownika) | Informacje wyświetlane po kliknięciu zakładki. |
| | Aktywna | TAK | Kontroluje, czy zakładka jest widoczna, czy ukryta. |
| | Pozycja | (Zdefiniowana przez użytkownika) | Określa kolejność zakładek na stronie produktu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

-   **P: Moje nowe zakładki nie wyświetlają się na stronie produktu.**
    *   **O:** Po pierwsze, upewnij się, że zakładka jest oznaczona jako „Aktywna” zarówno w globalnej konfiguracji modułu (jeśli jest to zakładka globalna), jak i na indywidualnej stronie produktu (jeśli jest specyficzna dla produktu). Po drugie, wyczyść pamięć podręczną PrestaShop: Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Wyczyść również pamięć podręczną przeglądarki.
-   **P: Edytor TinyMCE nie pojawia się, gdy próbuję dodać zawartość zakładki.**
    *   **O:** Przejdź do głównej strony konfiguracji modułu (**Moduły > Menedżer modułów > Product Extra Tabs Pro > Konfiguruj**) i upewnij się, że ustawienie „Włącz edytor TinyMCE dla zawartości zakładki” jest ustawione na **TAK**. Zapisz zmiany i wyczyść pamięć podręczną.
-   **P: Moje zakładki wyglądają dziwnie lub nie pasują do stylu mojego motywu.**
    *   **O:** Moduł stara się integrować bezproblemowo, ale niestandardowe motywy mogą czasami nadpisywać domyślne style. Jeśli wygląd jest nieprawidłowy, zazwyczaj wymaga to drobnych korekt CSS w Twoim motywie. Skontaktuj się ze swoim webmasterem lub wsparciem MyPresta.eu, dołączając zrzuty ekranu, aby uzyskać pomoc.
-   **P: Czy mogę mieć różne zakładki dla różnych języków?**
    *   **O:** Tak! Pola „Tytuł zakładki” i „Zawartość zakładki” są wielojęzyczne. Podczas edycji zakładki zobaczysz flagi językowe obok tych pól. Kliknij flagę, aby przełączyć się na inny język i wprowadzić przetłumaczoną zawartość.
-   **P: Chcę wyświetlać zakładkę tylko dla niektórych produktów, a nie dla wszystkich.**
    *   **O:** Upewnij się, że ustawienie „Wyświetlaj zakładki globalnie” w głównej konfiguracji modułu jest ustawione na **NIE**. Następnie przejdź do każdego konkretnego produktu, do którego chcesz dodać zakładkę (**Katalog > Produkty > Edytuj produkt > sekcja Extra Tabs Pro**) i utwórz tam zakładki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Product Extra Tabs Pro` został zaprojektowany jako standardowy moduł PrestaShop, głównie rozszerzający klasę `Module`. Wykorzystuje system hooków PrestaShop do wstrzykiwania swojej zawartości na strony produktów i używa niestandardowej tabeli bazy danych do przechowywania danych zakładek. Konfiguracja jest obsługiwana za pomocą `getContent()` w głównym pliku modułu, a zarządzanie zakładkami specyficznymi dla produktu jest zintegrowane bezpośrednio ze stroną administracji produktu za pośrednictwem niestandardowej zakładki. Wykorzystuje AJAX do dynamicznego ładowania i zapisywania treści.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów front-office ani back-office w katalogu `controllers/`. Całe renderowanie front-office jest obsługiwane za pomocą hooków i plików szablonów, a konfiguracja back-office jest zarządzana w metodzie `getContent()` głównego pliku modułu i wywołaniach AJAX.

### 4.3 Klasy i modele rdzenia (`classes/`)

Moduł nie definiuje niestandardowych klas w katalogu `classes/`. Jego główna logika obsługi danych jest osadzona w głównym pliku modułu `extratabspro/ajax_extratabspro.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `extratabspro/js/tinymce16.inc.js`:
    *   **Zakres:** Back-office.
    *   **Cel:** Ten plik prawdopodobnie zawiera inicjalizację i konfigurację edytora tekstu sformatowanego TinyMCE, specjalnie dostosowanego do środowisk PrestaShop 1.6. Zapewnia, że edytor jest ładowany i konfigurowany poprawnie dla pól wprowadzania zawartości zakładki.
-   `extratabspro/lib/searchTool/views/js/autocomplete.js`:
    *   **Zakres:** Back-office.
    *   **Cel:** Ten skrypt jest częścią biblioteki narzędzi wyszukiwania, prawdopodobnie używanej do funkcji autouzupełniania w polu wyszukiwania w interfejsie administracyjnym modułu (np. wyszukiwanie produktów do przypisania zakładek, chociaż ta konkretna funkcja nie jest wyraźnie wymieniona w przewodniku dla sprzedawców, jest to typowy wzorzec dla takiej biblioteki). Wiąże słuchaczy zdarzeń z polami wprowadzania i obsługuje żądania AJAX dotyczące sugestii wyszukiwania.
-   `extratabspro/views/admin/extratabspro.js`:
    *   **Zakres:** Back-office (PrestaShop 1.7.x, 8.x, 9.x).
    *   **Cel:** Jest to główny plik JavaScript dla interfejsu administracyjnego modułu. Obsługuje:
        *   Wywołania AJAX do dodawania, edytowania, usuwania globalnych zakładek.
        *   Wywołania AJAX do dodawania, edytowania, usuwania zakładek specyficznych dla produktu na stronie edycji produktu.
        *   Dynamiczne aktualizacje tabel list zakładek.
        *   Słuchaczy zdarzeń dla przesyłania formularzy, kliknięć przycisków (dodaj/edytuj/usuń) i potencjalnie zmiany kolejności zakładek metodą „przeciągnij i upuść”.
        *   Integrację z TinyMCE dla pól treści.
-   `extratabspro/views/admin/extratabspro8.js`:
    *   **Zakres:** Back-office (PrestaShop 8.x, 9.x).
    *   **Cel:** Podobnie jak `extratabspro.js`, ale prawdopodobnie zawiera specyficzne adaptacje lub poprawki dla środowisk PrestaShop 8.x i 9.x, uwzględniające zmiany w strukturze DOM Back Office lub interfejsach API JavaScript. Wykonuje te same podstawowe funkcje co `extratabspro.js`, ale zapewnia kompatybilność z nowszymi wersjami PrestaShop.
-   `extratabspro/views/js/extratabspro.js`:
    *   **Zakres:** Front-office.
    *   **Cel:** Ten skrypt obsługuje wyświetlanie i interakcję dodatkowych zakładek na stronie produktu w front-endzie. Prawdopodobnie:
        *   Inicjalizuje mechanizm przełączania zakładek (np. zakładki jQuery UI, zakładki Bootstrap lub niestandardowa logika).
        *   Wiąże zdarzenia kliknięcia z nagłówkami zakładek, aby pokazywać/ukrywać odpowiednią zawartość.
        *   Zapewnia płynne przejścia lub ładowanie treści.
        *   Może obsługiwać responsywne zachowanie zakładek na różnych rozmiarach ekranu.
-   `extratabspro/views/js/tinymce16.inc.js`: (Duplikat, prawdopodobnie dla różnych kontekstów lub przeoczenie w pakowaniu)
    *   **Zakres:** Back-office.
    *   **Cel:** To samo co w `extratabspro/js/`, prawdopodobnie do inicjalizacji TinyMCE.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `extratabspro/lib/searchTool/views/css/autocomplete.css`:
    *   **Zakres:** Back-office.
    *   **Cel:** Zapewnia stylizację dla rozwijanej listy sugestii autouzupełniania i powiązanych elementów interfejsu użytkownika biblioteki narzędzi wyszukiwania.
-   `extratabspro/views/admin/extratabspro.css`:
    *   **Zakres:** Back-office.
    *   **Cel:** Stylizuje formularze konfiguracji modułu, tabele list zakładek i wszelkie niestandardowe elementy interfejsu użytkownika w Panelu Administracyjnym PrestaShop, zapewniając spójny wygląd i działanie.
-   `extratabspro/views/css/extratabspro.css`:
    *   **Zakres:** Front-office.
    *   **Cel:** Zapewnia podstawową stylizację dla dodatkowych zakładek na stronie produktu. Obejmuje to wygląd nagłówków zakładek, stany aktywnych zakładek i obszary treści. Programiści mogą nadpisać te style w pliku `custom.css` lub `theme.css` swojego motywu, celując w klasy takie jak `.extratabs-pro-tabs`, `.extratabs-pro-tab-header`, `.extratabs-pro-tab-content` itp.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    *   `extratabspro/views/front/footer.tpl`: Ten szablon jest prawdopodobnie przeznaczony dla hooków `displayFooter` lub `displayFooterProduct` (chociaż moduł głównie używa `displayProductExtraContent`). Wyświetlałby zawartość w obszarze stopki.
    *   `extratabspro/views/front/tab.tpl`: Ten szablon renderuje pojedynczy nagłówek zakładki (część klikalną). Jest używany w pętli do generowania wszystkich nagłówków zakładek.
    *   `extratabspro/views/front/tab16.tpl`: Wersja `tab.tpl` specjalnie dla PrestaShop 1.6, dostosowująca się do jej innej struktury HTML lub klas CSS.
    *   `extratabspro/views/front/tabcontents.tpl`: Ten szablon renderuje obszar zawartości dla wszystkich dodatkowych zakładek. Zazwyczaj zawiera pętlę, która iteruje przez zawartość każdej zakładki, opakowując ją w kontener, który może być pokazywany/ukrywany przez JavaScript.
    *   `extratabspro/views/front/tabcontents16.tpl`: Wersja `tabcontents.tpl` specjalnie dla PrestaShop 1.6.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    *   `extratabspro/lib/searchTool/views/scripts.tpl`: Ten szablon prawdopodobnie zawiera zasoby JavaScript i CSS dla biblioteki narzędzi wyszukiwania w kontekście administracyjnym.
    *   `extratabspro/views/admin/tabs-list.tpl`: Ten szablon renderuje tabelę, która wyświetla wszystkie skonfigurowane zakładki (albo globalne zakładki na stronie konfiguracji modułu, albo zakładki specyficzne dla produktu na stronie edycji produktu). Zawiera kontrolki do edycji i usuwania zakładek.
    *   `extratabspro/views/admin/tabs17.tpl`: Ten szablon jest głównym formularzem konfiguracji lub wyświetlaniem modułu w Panelu Administracyjnym PrestaShop 1.7.x / 8.x / 9.x. Prawdopodobnie zawiera pola formularza dla ustawień globalnych i włączenie `tabs-list.tpl` do zarządzania zakładkami.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   `ps_extratabspro_tab`: Przechowuje główne informacje dla każdej dodatkowej zakładki (ID, ID produktu, pozycja, status aktywności).
    *   `ps_extratabspro_tab_lang`: Przechowuje wielojęzyczną zawartość dla każdej zakładki (tytuł, zawartość), połączoną z `ps_extratabspro_tab` za pomocą `id_extratabspro_tab` i `id_lang`.
    *   `ps_configuration`: Przechowuje globalne ustawienia modułu (np. `EXTRATABSPRO_TINYMCE_ENABLED`, `EXTRATABSPRO_GLOBAL_TABS_ENABLED`, `EXTRATABSPRO_HOOK_POSITION`).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje pliki CSS i JS modułu do wyświetlania w front-office. |
| `displayBackOfficeHeader` | W sekcji `<head>` stron Panelu Administracyjnego. | Wstrzykuje pliki CSS i JS modułu do konfiguracji Panelu Administracyjnego i integracji ze stroną produktu. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu Administracyjnym. | Wstrzykuje sekcję „Extra Tabs Pro” do interfejsu administracji produktu, umożliwiając zarządzanie zakładkami dla każdego produktu. |
| `displayProductExtraContent` | W głównym obszarze treści strony produktu, zazwyczaj poniżej opisu produktu. | Renderuje rzeczywiste dodatkowe zakładki i ich zawartość na stronie produktu w front-office. Jest to główny hook do wyświetlania w front-endzie. |
| `displayFooterProduct` | W sekcji stopki strony produktu. | Alternatywny hook do wyświetlania zakładek, jeśli skonfigurowany przez sprzedawcę. |
| `displayRightColumnProduct` | W prawej kolumnie strony produktu. | Alternatywny hook do wyświetlania zakładek, jeśli skonfigurowany przez sprzedawcę. |
| `displayLeftColumnProduct` | W lewej kolumnie strony produktu. | Alternatywny hook do wyświetlania zakładek, jeśli skonfigurowany przez sprzedawcę. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu Administracyjnym. | Potencjalnie używany do czyszczenia pamięci podręcznej lub wykonywania innych działań związanych ze zmianami danych produktu. |
| `actionProductDelete` | Po usunięciu produktu. | Czyści zakładki specyficzne dla produktu z bazy danych. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Potencjalnie używany do początkowej konfiguracji lub tworzenia domyślnych zakładek dla nowych produktów. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu obiektu produktu. | Podobnie jak `actionProductUpdate`, dla aktualizacji modelu obiektu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich dalszych pytań dotyczących modułu „Product Extra Tabs Pro”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia i programiści są dostępni, aby Ci pomóc.
