---
title: "Ukryj wybrane cechy - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Ukryj wybrane cechy” od MyPresta.eu."
sidebar:
  label: "Ukryj wybrane cechy - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Hide selected features na MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-selected-features.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/hide-selected-features/)
>
> ---


# Ukryj wybrane cechy

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Możesz uzyskać dostęp do tej strony, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Ukryj wybrane cechy”, a następnie klikając „Konfiguruj”.

Ten ekran przedstawia listę wszystkich cech produktu aktualnie zdefiniowanych w Twoim sklepie PrestaShop. Dla każdej cechy zobaczysz przełącznik do kontrolowania jej widoczności.

- **Co robi to ustawienie:** Ta sekcja zawiera listę wszystkich istniejących cech produktu (np. „Materiał”, „Kolor”, „Waga”, „Wymiary”). Obok każdej cechy znajduje się przełącznik, który kontroluje, czy ta konkretna cecha będzie wyświetlana na stronach produktów w front office.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (przełącznik jest WŁ.):* Cecha będzie widoczna dla klientów na wszystkich stronach produktów, do których jest przypisana. Jest to domyślne zachowanie PrestaShop.
  - *Gdy wyłączone (przełącznik jest WYŁ.):* Cecha będzie ukryta przed klientami na wszystkich stronach produktów, nawet jeśli jest przypisana do produktu. Nadal będzie istnieć w Twoim panelu administracyjnym do użytku wewnętrznego lub filtrowania.
- **Zalecana wartość:** Zależy to całkowicie od Twoich potrzeb biznesowych.
  - **Włącz** cechy, które są kluczowe dla podejmowania decyzji przez klienta (np. „Materiał” dla odzieży, „Pojemność” dla elektroniki).
  - **Wyłącz** cechy, które są wewnętrznymi notatkami, specyfikacjami technicznymi nieistotnymi dla przeciętnego klienta lub zbędnymi informacjami.
- **Scenariusz / przykład sprzedawcy:**
  - **Scenariusz 1 (Ukrywanie wewnętrznych notatek):** Używasz cechy o nazwie „SKU dostawcy” do śledzenia wewnętrznych kodów produktów. Ta informacja nie jest przydatna dla klientów. W tym miejscu **wyłączysz** cechę „SKU dostawcy”, aby utrzymać strony produktów w czystości.
  - **Scenariusz 2 (Upraszczanie wyświetlania):** Sprzedajesz koszulki i masz cechy takie jak „Materiał: Bawełna”, „Długość rękawa: Krótki”, „Dekolt: Okrągły”. Decydujesz, że „Długość rękawa” i „Dekolt” są zazwyczaj jasne z obrazu produktu i chcesz podkreślić „Materiał”. W tym miejscu **wyłączysz** „Długość rękawa” i „Dekolt” oraz **włączysz** „Materiał”.

**Inne klucze konfiguracyjne (Wewnętrzne/Zaawansowane):**
Możesz zobaczyć inne klucze konfiguracyjne, takie jak `mypresta_updates`, `update_`, `updatev_`, `hidefeatures_OSTATE`, `PS_OS_PREPARATION`, `hidefeatures_MIN_CHARGE`. Są to zazwyczaj wewnętrzne ustawienia modułu związane z aktualizacjami, statusami zamówień lub minimalnymi opłatami i nie są bezpośrednio konfigurowalne przez sprzedawcę za pośrednictwem głównego interfejsu. Zazwyczaj są one zarządzane automatycznie przez moduł lub używane w specyficznych, zaawansowanych scenariuszach, które nie są eksponowane w podstawowym interfejsie użytkownika. W przypadku tego modułu, podstawowa funkcjonalność jest zarządzana przez przełączniki cech.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminFeaturesController (Panel administracyjny > Katalog > Atrybuty i cechy > Cechy)

Ten moduł nadpisuje standardowy ekran zarządzania „Cechami” PrestaShop.

- **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Katalog > Atrybuty i cechy > Cechy**.
- **Dostępne akcje i ustawienia:** Gdy przejdziesz do tego ekranu, zobaczysz listę wszystkich cech produktu. Moduł dodaje nową kolumnę lub wskaźnik do tej listy, zazwyczaj oznaczony jako **„Aktywny w front office”** lub podobnie. Ta kolumna pokaże Ci na pierwszy rzut oka, czy cecha jest aktualnie ustawiona jako widoczna czy ukryta w front office Twojego sklepu, na podstawie ustawień dokonanych na głównej stronie konfiguracji modułu.
- **Efekt zmian:** Chociaż nie możesz bezpośrednio zmieniać widoczności z tego ekranu (robisz to na stronie konfiguracji modułu), ten ekran zapewnia wygodny przegląd. Pomaga szybko zweryfikować status front office każdej cechy bez konieczności wracania do modułu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Używaj tego ekranu jako szybkiego odniesienia podczas zarządzania cechami produktu. Jeśli dodasz nową cechę, pamiętaj, aby odwiedzić stronę konfiguracji modułu „Ukryj wybrane cechy”, aby zdecydować, czy powinna być widoczna dla klientów.

#### 2.2.2 index.php (hidefeatures/override/controllers/admin/index.php)

Ten plik jest częścią struktury nadpisywania i zazwyczaj służy jako symbol zastępczy lub punkt wejścia dla logiki nadpisanego kontrolera. Nie reprezentuje on odrębnego, widocznego dla użytkownika ekranu konfiguracji, ale raczej ułatwia modyfikację istniejących stron administracyjnych PrestaShop przez moduł.

- **Zarządzana tabela / encja:** Ten plik nie zarządza bezpośrednio konkretną tabelą ani encją, ale raczej zapewnia prawidłowe ładowanie i wykonywanie nadpisanego `AdminFeaturesController`.
- **Pola formularza i kolumny:** Ten konkretny plik nie zarządza bezpośrednio żadnymi polami formularza ani kolumnami. Jego celem jest architektura, zapewniająca zastosowanie zmian modułu w siatce/widoku zarządzania „Cechami”.
- **Efekt zmian:** Ten plik zapewnia, że kolumna „Aktywny w front office” (lub podobny wskaźnik) jest poprawnie wyświetlana na liście **Katalog > Atrybuty i cechy > Cechy**, zapewniając ulepszony widok zarządzania.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Lista wszystkich cech z przełącznikami WŁ./WYŁ. | Różni się w zależności od cechy (WŁ. dla nowych cech) | Kontroluje, czy konkretna cecha produktu jest wyświetlana na stronach produktów w front office. WŁ. = Widoczne, WYŁ. = Ukryte. |
| **AdminFeaturesController** (Katalog > Atrybuty i cechy > Cechy) | Kolumna/wskaźnik „Aktywny w front office” | Odzwierciedla konfigurację modułu | Zapewnia szybki przegląd statusu widoczności cechy w front office bezpośrednio na liście cech. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Ukryłem cechę, ale nadal wyświetla się na stronie mojego produktu. Co jest nie tak?**
O:

1.  **Wyczyść pamięć podręczną:** Najczęstszym powodem jest to, że pamięć podręczna PrestaShop (i prawdopodobnie pamięć podręczna przeglądarki) nie została zaktualizowana. Przejdź do **Zaawansowane > Wydajność** w swoim Panelu administracyjnym i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Spróbuj również wyczyścić pamięć podręczną przeglądarki lub wyświetlić stronę w trybie incognito/prywatnym.
2.  **Konfiguracja modułu zapisana?** Sprawdź dwukrotnie, czy kliknąłeś „Zapisz” po wprowadzeniu zmian na stronie konfiguracji modułu.
3.  **Poprawna cecha?** Upewnij się, że wyłączyłeś dokładnie tę cechę, którą zamierzasz ukryć. Nazwy cech mogą być czasami podobne.

**P: Czy mogę ukryć cechy tylko dla konkretnych produktów, a nie globalnie?**
O: Nie, ten moduł ukrywa cechy globalnie dla wszystkich produktów. Jeśli potrzebujesz widoczności cech specyficznych dla produktu, zazwyczaj zarządzasz tym, nie przypisując cechy do produktu w pierwszej kolejności, lub używając bardziej zaawansowanego niestandardowego rozwiązania. Ten moduł zapewnia przełącznik dla typów cech w całym sklepie.

**P: Czy ukrycie cechy wpłynie na moje filtry produktów lub wyniki wyszukiwania?**
O: Nie, ten moduł wpływa tylko na *wyświetlanie* cech na stronie produktu w front office. Same dane cech pozostają w Twojej bazie danych. Jeśli używasz cech do nawigacji warstwowej (filtrów) lub wyszukiwania, powinny one nadal działać zgodnie z oczekiwaniami, o ile cecha jest przypisana do produktu.

**P: Kolumna „Aktywny w front office” nie wyświetla się na mojej liście cech (Katalog > Atrybuty i cechy > Cechy).**
O:

1.  **Moduł zainstalowany i włączony?** Upewnij się, że moduł „Ukryj wybrane cechy” jest poprawnie zainstalowany i włączony w **Moduły > Menedżer modułów**.
2.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop, jak opisano powyżej.
3.  **Kompatybilność z motywem:** W rzadkich przypadkach, bardzo spersonalizowany motyw może kolidować z nadpisaniami. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Jak przetłumaczyć tekst modułu (jeśli istnieje)?**
O: Chociaż ten moduł używa głównie istniejących nazw cech PrestaShop, jeśli istnieją jakiekolwiek teksty lub etykiety specyficzne dla modułu, możesz je przetłumaczyć, przechodząc do **Lokalizacja > Tłumaczenia** w swoim Panelu administracyjnym. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, wybierz swój język, a następnie znajdź moduł „Ukryj wybrane cechy”, aby edytować jego tłumaczenia.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Ukryj wybrane cechy” działa poprzez nadpisywanie podstawowych klas i kontrolerów PrestaShop w celu wstrzyknięcia logiki widoczności. Rozszerza klasy `Feature` i `Product`, aby dodać nową właściwość dla widoczności w front office i modyfikuje `AdminFeaturesController`, aby wyświetlić ten status w panelu administracyjnym. Moduł używa niestandardowego haka (`displayHiddenFeatures`) do renderowania rzeczywistej listy cech na stronie produktu, co pozwala mu odfiltrować ukryte cechy przed wyświetleniem.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office. Cała logika front-office jest obsługiwana za pomocą nadpisań podstawowych klas i haków.
- **Kontrolery administracyjne Back-Office**:

  - `hidefeatures/override/controllers/admin/AdminFeaturesController.php`
    - **Nazwa klasy i klasa nadrzędna**: `AdminFeaturesController` (nadpisuje podstawowy `AdminFeaturesController`)
    - **Odpowiedzialność**: To nadpisanie modyfikuje `AdminFeaturesController`, aby wyświetlić status widoczności każdej cechy w front office na liście cech. Prawdopodobnie dodaje nową kolumnę do tabeli listy, umożliwiając administratorom szybkie sprawdzenie, które cechy są ukryte/widoczne bez przechodzenia do konfiguracji modułu. Wykorzystuje nadpisanie klasy `Feature` do pobierania tego statusu.
  - `hidefeatures/override/controllers/admin/index.php`
    - **Nazwa klasy i klasa nadrzędna**: Nie jest to plik klasy, zazwyczaj pusty `index.php`, aby zapobiec listowaniu katalogów.
    - **Odpowiedzialność**: Standardowa praktyka dla katalogów `override`, aby zapobiec bezpośredniemu dostępowi i zapewnić bezpieczeństwo. Nie zawiera kodu funkcjonalnego.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `hidefeatures/override/classes/Feature.php`

  - **Z jaką tabelą bazy danych wchodzi w interakcje**: `ps_feature` (główna tabela cech) i `ps_configuration` (dla ustawień modułu).
  - **Rozszerza `ObjectModel`**: Tak, rozszerza podstawową klasę `Feature`, która sama rozszerza `ObjectModel`.
  - **Pola `$definition`**: To nadpisanie prawdopodobnie dodaje nowe pole do tablicy `$definition` klasy `Feature`, lub częściej, dodaje dynamiczną właściwość do obiektu `Feature`, aby przechowywać jego status widoczności w front office, który jest następnie pobierany z `ps_configuration` lub niestandardowej tabeli. Zawierałoby również metody do pobierania i ustawiania tego statusu widoczności.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa**:
    - Metody do pobierania statusu widoczności konkretnej cechy.
    - Metody do aktualizacji statusu widoczności, prawdopodobnie wchodzące w interakcje z `Configuration::updateValue()`.
    - Potencjalnie modyfikuje `getFeatures()` lub podobne metody w celu filtrowania wyników na podstawie widoczności.
- `hidefeatures/override/classes/index.php`

  - **Nazwa klasy i klasa nadrzędna**: Nie jest to plik klasy, zazwyczaj pusty `index.php`, aby zapobiec listowaniu katalogów.
  - **Odpowiedzialność**: Standardowa praktyka dla katalogów `override`, aby zapobiec bezpośredniemu dostępowi i zapewnić bezpieczeństwo. Nie zawiera kodu funkcjonalnego.
- `hidefeatures/override/classes/Product.php`

  - **Z jaką tabelą bazy danych wchodzi w interakcje**: `ps_product` i `ps_feature_product`.
  - **Rozszerza `ObjectModel`**: Tak, rozszerza podstawową klasę `Product`, która sama rozszerza `ObjectModel`.
  - **Pola `$definition`**: Nie oczekuje się tutaj bezpośredniej modyfikacji `$definition`.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa**: To nadpisanie jest kluczowe dla filtrowania cech na stronie produktu. Prawdopodobnie modyfikuje metody takie jak `getFeatures()` lub `getFrontFeatures()` (jeśli istnieją w podstawowej klasie `Product`), aby:
    1. Pobrać wszystkie przypisane cechy dla produktu.
    2. Iterować przez te cechy.
    3. Dla każdej cechy sprawdzić jej status widoczności za pomocą logiki z nadpisanej klasy `Feature`.
    4. Zwrócić tylko te cechy, które są oznaczone jako widoczne.
       Zapewnia to, że gdy cechy produktu są pobierane do wyświetlenia, ukryte są automatycznie wykluczane.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie wydaje się zawierać żadnych niestandardowych plików JavaScript. Jego funkcjonalność jest przede wszystkim po stronie serwera za pośrednictwem nadpisań PHP i logiki szablonów Smarty.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie wydaje się zawierać żadnych niestandardowych plików CSS. Wszelkie style dla dodanej kolumny w AdminFeaturesController byłyby zazwyczaj obsługiwane przez domyślny CSS panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony haków (`views/templates/hook/`)**:

  - `hidefeatures/views/templates/front/hook/displayHiddenFeatures.tpl`
    - **Hak**: `displayHiddenFeatures` (niestandardowy hak, prawdopodobnie wywoływany w nadpisanej klasie `Product` lub w pliku `product.tpl` motywu)
    - **Wyjście**: Ten szablon jest odpowiedzialny za renderowanie listy cech produktu na stronie produktu w front office. Otrzymuje przefiltrowaną listę cech (po usunięciu ukrytych przez nadpisanie klasy `Product`) i wyświetla je w standardowym formacie tabeli/listy cech PrestaShop. Programiści mogą zbadać ten szablon, aby zrozumieć, jak cechy są iterowane i wyświetlane.
- **Szablony administracyjne (`views/templates/admin/`)**:

  - `hidefeatures/views/templates/admin/_configure/helpers/list/list_content.tpl`
    - **Cel**: Ten szablon jest nadpisaniem standardowego szablonu zawartości listy PrestaShop, używanego specjalnie w `AdminFeaturesController`. Jest odpowiedzialny za renderowanie wierszy tabeli listy cech w panelu administracyjnym.
    - **Zawartość**: Będzie zawierać logikę wyświetlania kolumny „Aktywny w front office” (lub podobnej) dla każdej cechy, pokazując wizualny wskaźnik (np. znacznik wyboru, czerwony X lub przełącznik) na podstawie statusu widoczności cechy. Ten szablon działa w połączeniu z nadpisaniem `AdminFeaturesController`, aby przedstawić dodatkowe informacje.
- **Szablony front-office (`views/templates/front/`)**:

  - Brak dedykowanych samodzielnych szablonów stron front-office.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:

  - Moduł nie tworzy nowych niestandardowych tabel bazy danych.
  - Przechowuje swoją konfigurację (które cechy są ukryte/widoczne) w tabeli `ps_configuration`. Klucze konfiguracyjne zazwyczaj będą miały wzorzec taki jak `HIDEFEATURES_FEATURE_ID_X` lub podobny, gdzie `X` to `id_feature`.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHiddenFeatures` | Niestandardowy hak, prawdopodobnie wywoływany w `product.tpl` lub za pośrednictwem nadpisania `Product::getFrontFeatures()`. | Renderuje przefiltrowaną listę cech produktu na stronie produktu w front office, zapewniając wyświetlanie tylko widocznych cech. |
| `actionProductUpdate` | Po zaktualizowaniu produktu. | (Implicitne, jeśli moduł musi ponownie ocenić widoczność cech po zapisaniu produktu, choć nie jest jawnie wymieniony jako główny hak dla podstawowej funkcji tego modułu). |
| `actionFeatureSave` / `actionFeatureDelete` | Po zapisaniu lub usunięciu cechy. | (Implicitne, jeśli moduł musi zaktualizować swoją wewnętrzną konfigurację po dodaniu/usunięciu cech). |
| `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` Panelu administracyjnego. | (Możliwe, do wstrzykiwania JS/CSS, jeśli jest to potrzebne dla interfejsu użytkownika administratora, ale nieobecne w inwentarzu). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich zapytań dotyczących modułu „Ukryj wybrane cechy”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
