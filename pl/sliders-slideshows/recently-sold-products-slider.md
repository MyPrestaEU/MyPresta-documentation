---
title: "Suwak ostatnio sprzedanych produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Suwak ostatnio sprzedanych produktów” od MyPresta.eu."
sidebar:
  label: "Suwak ostatnio sprzedanych produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Recently sold products slider na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/recently-sold-products-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/recently-sold-products-slider/)
>
> ---


# Suwak ostatnio sprzedanych produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu „Suwak ostatnio sprzedanych produktów”. Tutaj możesz dostosować wygląd, zachowanie i zawartość suwaka produktów.

#### **Kolor tła (rsps\_c\_bg)**

- **Co robi to ustawienie:** Kontroluje kolor tła całego bloku suwaka.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na kolor (np. #FFFFFF dla białego):* Tło suwaka będzie wyświetlane w tym konkretnym kolorze, pomagając mu wtopić się w motyw lub wyróżnić się z niego.
  - *Gdy pozostawiony pusty lub nieprawidłowy:* Suwak może dziedziczyć style tła z Twojego motywu lub domyślnie przyjmować przezroczyste tło.
- **Zalecana wartość:** Wybierz kolor, który uzupełnia projekt Twojego sklepu. Często najlepszy jest subtelny kolor lub taki, który pasuje do nagłówka/stopki.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep ma ciemny nagłówek, ustawienie tego na ciemnoszary lub czarny może sprawić, że suwak będzie wyglądał na zintegrowany. Jeśli chcesz, aby się wyróżniał, może zadziałać kontrastujący kolor.

#### **Kolor obramowania (rsps\_c\_border)**

- **Co robi to ustawienie:** Definiuje kolor obramowania wokół całego bloku suwaka.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na kolor (np. #CCCCCC dla jasnoszarego):* Wokół suwaka pojawi się obramowanie w tym kolorze.
  - *Gdy pozostawiony pusty lub nieprawidłowy:* Moduł nie zastosuje jawnego obramowania, chociaż Twój motyw może je nadal dodać.
- **Zalecana wartość:** Często najlepsze jest subtelne obramowanie, które pasuje do innych obramowań Twojego motywu, lub przezroczyste obramowanie.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja witryna używa cienkich szarych obramowań dla innych elementów, ustawienie tego na ten sam szary kolor zachowa spójność.

#### **Kolor czcionki (rsps\_c\_font)**

- **Co robi to ustawienie:** Ustawia kolor tekstu (nazw produktów) wyświetlanego w suwaku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na kolor (np. #333333 dla ciemnoszarego):* Nazwy produktów pojawią się w wybranym kolorze.
  - *Gdy pozostawiony pusty lub nieprawidłowy:* Kolor tekstu może domyślnie przyjąć ogólny kolor czcionki Twojego motywu.
- **Zalecana wartość:** Wybierz kolor, który zapewnia dobry kontrast z kolorem tła suwaka, aby zapewnić czytelność.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli tło suwaka jest ciemne, jasny kolor czcionki (jak biały lub jasnoszary) będzie niezbędny dla czytelności.

#### **Wypełnienie suwaka (rsps\_s\_padding)**

- **Co robi to ustawienie:** Kontroluje wewnętrzne odstępy (wypełnienie) między zawartością (tekstem) a krawędziami bloku suwaka.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na wartość (np. „10px”):* Tekst będzie miał 10 pikseli odstępu ze wszystkich stron od obramowania suwaka.
  - *Gdy ustawiony na „0px” lub pusty:* Tekst będzie przylegał bezpośrednio do krawędzi suwaka.
- **Zalecana wartość:** „5px” lub „10px”, aby dać tekstowi trochę przestrzeni i poprawić estetykę.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój tekst wygląda zbyt ciasno, zwiększenie wypełnienia doda więcej miejsca wokół niego, sprawiając, że będzie wyglądał czyściej.

#### **Rozmiar czcionki suwaka (rsps\_s\_font)**

- **Co robi to ustawienie:** Określa rozmiar czcionki używanej dla nazw produktów w suwaku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na wartość (np. „14px”):* Tekst będzie wyświetlany w tym konkretnym rozmiarze pikseli.
  - *Gdy pozostawiony pusty lub nieprawidłowy:* Rozmiar czcionki może domyślnie przyjąć ogólny rozmiar czcionki Twojego motywu.
- **Zalecana wartość:** „14px” lub „16px” dla dobrej czytelności, bez bycia zbyt dużym lub zbyt małym.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli suwak znajduje się w widocznym miejscu, takim jak nagłówek, nieco większa czcionka może być odpowiednia. Dla paska bocznego, mniejsza czcionka może lepiej pasować.

#### **Obramowanie suwaka (rsps\_s\_border)**

- **Co robi to ustawienie:** Definiuje grubość i styl obramowania wokół *wewnętrznej zawartości* suwaka (samego obszaru przewijania tekstu), odrębnego od ogólnego obramowania bloku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na wartość (np. „1px solid #CCCCCC”):* Wokół przewijanego tekstu pojawi się 1-pikselowe, jednolite, jasnoszare obramowanie.
  - *Gdy pozostawiony pusty lub nieprawidłowy:* Nie zostanie zastosowane żadne jawne wewnętrzne obramowanie.
- **Zalecana wartość:** „0px” lub „none”, jeśli chcesz tylko zewnętrzne obramowanie bloku. Jeśli chcesz subtelnego rozdzielenia, „1px solid #EEEEEE” może zadziałać.
- **Scenariusz/przykład dla sprzedawcy:** Możesz użyć tego, aby stworzyć wyraźne wizualne pole dla przewijanego tekstu w większym obszarze suwaka.

#### **Kierunek ruchu (rsps\_m\_dir)**

- **Co robi to ustawienie:** Kontroluje kierunek, w którym nazwy produktów przewijają się w suwaku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na „left” (lewo):* Tekst będzie przewijał się od prawej do lewej.
  - *Gdy ustawiony na „right” (prawo):* Tekst będzie przewijał się od lewej do prawej.
- **Zalecana wartość:** „left” (lewo) to powszechny i naturalny kierunek czytania dla przewijanego tekstu.
- **Scenariusz/przykład dla sprzedawcy:** Większość użytkowników jest przyzwyczajona do tekstu przewijającego się w lewo, więc trzymanie się „left” często zapewnia najlepsze wrażenia użytkownika.

#### **Opóźnienie ruchu (rsps\_m\_delay)**

- **Co robi to ustawienie:** Określa szybkość animacji przewijania. Jest to zazwyczaj mierzone w milisekundach.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na niższą wartość (np. „50”):* Tekst będzie przewijał się szybciej.
  - *Gdy ustawiony na wyższą wartość (np. „100”):* Tekst będzie przewijał się wolniej.
- **Zalecana wartość:** „70” do „100” zapewnia płynną, czytelną szybkość, nie będąc ani za szybkim, ani za wolnym.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli tekst jest za szybki, klienci nie mogą go przeczytać. Jeśli jest za wolny, może nie przyciągnąć uwagi. Eksperymentuj, aby znaleźć równowagę.

#### **Pozycja suwaka (rsps\_position)**

- **Co robi to ustawienie:** Pozwala wybrać hak PrestaShop, w którym suwak będzie wyświetlany w Twoim sklepie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na `displayHome`:* Suwak pojawi się na stronie głównej Twojego sklepu.
  - *Gdy ustawiony na `displayHeader`:* Suwak pojawi się w sekcji nagłówka wszystkich stron.
  - *Gdy ustawiony na `displayFooter`:* Suwak pojawi się w sekcji stopki wszystkich stron.
  - *Inne opcje (np. `displayLeftColumn`, `displayRightColumn`, `displayTop`):* Suwak pojawi się w odpowiedniej kolumnie lub sekcji górnej.
- **Zalecana wartość:** `displayHeader` lub `displayHome` dla maksymalnej widoczności, lub `displayFooter` dla bardziej subtelnego podejścia.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby każdy odwiedzający natychmiast zobaczył ostatnie sprzedaże, wybierz `displayHeader`. Jeśli chcesz, aby był częścią zawartości Twojej strony głównej, wybierz `displayHome`.

#### **Liczba produktów (rsps\_nb)**

- **Co robi to ustawienie:** Określa, ile ostatnio sprzedanych produktów powinno zostać pobranych i wyświetlonych w suwaku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na niższą liczbę (np. „5”):* Wyświetlonych zostanie tylko 5 najnowszych sprzedaży.
  - *Gdy ustawiony na wyższą liczbę (np. „20”):* Do 20 ostatnich sprzedaży zostanie uwzględnionych na liście przewijania.
- **Zalecana wartość:** „10” do „15”, aby zapewnić dobrą różnorodność produktów, nie czyniąc listy nadmiernie długą.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep ma wiele sprzedaży, wyższa liczba zapewnia więcej dowodów społecznych. Jeśli sprzedaż jest mniej częsta, niższa liczba może być wystarczająca.

#### **Sortuj według (rsps\_order)**

- **Co robi to ustawienie:** Określa kryteria sortowania produktów wyświetlanych w suwaku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na „date\_add”:* Produkty będą sortowane według daty dodania do zamówienia (najnowsze najpierw).
  - *Gdy ustawiony na „product\_name”:* Produkty będą sortowane alfabetycznie według nazwy.
  - *Gdy ustawiony na „price”:* Produkty będą sortowane według ceny.
- **Zalecana wartość:** „date\_add”, aby naprawdę pokazać „ostatnio sprzedane” przedmioty.
- **Scenariusz/przykład dla sprzedawcy:** Aby dokładnie odzwierciedlić ostatnie zakupy, sortowanie według `date_add` jest najbardziej logicznym wyborem.

#### **Różnorodność (rsps\_diversity)**

- **Co robi to ustawienie:** To ustawienie kontroluje, czy suwak powinien wyświetlać unikalne produkty, czy też pozwalać na wielokrotne pojawianie się tego samego produktu, jeśli został on ostatnio sprzedany.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (np. „Tak” lub „1”):* Jeśli ten sam produkt został sprzedany wielokrotnie, pojawi się tylko raz na liście produktów do wyświetlenia, zapewniając większą różnorodność pozycji.
  - *Gdy wyłączone (np. „Nie” lub „0”):* Ten sam produkt może pojawić się wielokrotnie w suwaku, jeśli był częścią kilku ostatnich zamówień.
- **Zalecana wartość:** „Tak” (lub „1”), aby zaprezentować szerszą gamę Twojego katalogu i zapobiec powtarzaniu się suwaka.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz bardzo popularny przedmiot, wyłączenie różnorodności może oznaczać, że suwak wyświetla tylko ten jeden przedmiot wielokrotnie. Włączenie go zapewnia, że inne produkty mają szansę zostać zauważone.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Kolor tła** (rsps\_c\_bg) | `#FFFFFF` (Biały) | Ustawia kolor tła bloku suwaka. |
| Konfiguracja modułu | **Kolor obramowania** (rsps\_c\_border) | `#CCCCCC` (Jasnoszary) | Ustawia kolor obramowania wokół bloku suwaka. |
| Konfiguracja modułu | **Kolor czcionki** (rsps\_c\_font) | `#333333` (Ciemnoszary) | Ustawia kolor tekstu nazw produktów. |
| Konfiguracja modułu | **Wypełnienie suwaka** (rsps\_s\_padding) | `10px` | Wewnętrzne odstępy wokół tekstu w suwaku. |
| Konfiguracja modułu | **Rozmiar czcionki suwaka** (rsps\_s\_font) | `14px` | Rozmiar czcionki dla nazw produktów. |
| Konfiguracja modułu | **Obramowanie suwaka** (rsps\_s\_border) | `0px` | Obramowanie wokół samego obszaru przewijania tekstu. |
| Konfiguracja modułu | **Kierunek ruchu** (rsps\_m\_dir) | `left` | Kierunek animacji przewijania (lewo lub prawo). |
| Konfiguracja modułu | **Opóźnienie ruchu** (rsps\_m\_delay) | `70` | Szybkość animacji przewijania (niższa = szybsza). |
| Konfiguracja modułu | **Pozycja suwaka** (rsps\_position) | `displayHeader` | Hak PrestaShop, w którym suwak będzie wyświetlany. |
| Konfiguracja modułu | **Liczba produktów** (rsps\_nb) | `10` | Maksymalna liczba ostatnio sprzedanych produktów do wyświetlenia. |
| Konfiguracja modułu | **Sortuj według** (rsps\_order) | `date_add` | Kryteria sortowania dla wyświetlanych produktów. |
| Konfiguracja modułu | **Różnorodność** (rsps\_diversity) | `Tak` (1) | Zapewnia wyświetlanie unikalnych produktów (zapobiega powtórzeniom). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem moduł, ale suwak nie wyświetla się w moim sklepie.**
**O1:**

-   **Sprawdź pozycję haka:** Przejdź do **Wygląd > Pozycje** w Panelu administracyjnym PrestaShop. Wyszukaj hak, który wybrałeś w ustawieniu „Pozycja suwaka” modułu (np. `displayHeader`, `displayHome`). Upewnij się, że moduł „Suwak ostatnio sprzedanych produktów” jest wymieniony i włączony w tym haku. Jeśli nie, być może będziesz musiał „Przeszczepić moduł” do właściwego haka.
-   **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
-   **Moduł włączony:** Sprawdź dwukrotnie, czy moduł jest włączony w **Moduły > Menedżer modułów**.
-   **Ostatnie sprzedaże:** Upewnij się, że faktycznie masz ostatnie sprzedaże w swoim sklepie. Moduł opiera się na istniejących danych zamówień.

**P2: Suwak się wyświetla, ale kolory lub rozmiary czcionek nie są takie, jak ustawiłem.**
**O2:**

-   **Wyczyść pamięć podręczną:** Jest to najczęstszy powód problemów ze stylizacją. Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+R).
-   **Nadpisywanie motywu:** Twój motyw PrestaShop może mieć własny CSS, który nadpisuje style modułu. Może być konieczne sprawdzenie elementu za pomocą narzędzi deweloperskich przeglądarki (F12), aby zobaczyć, które reguły CSS są stosowane. Jeśli jest to konflikt motywu, być może będziesz musiał dodać niestandardowy CSS do swojego motywu, aby wymusić style modułu.
-   **Prawidłowe dane wejściowe:** Upewnij się, że używasz prawidłowych kodów kolorów CSS (np. `#RRGGBB` lub `rgba(R,G,B,A)`) i wartości pikseli (np. `14px`) w konfiguracji modułu.

**P3: Tekst przewija się za szybko/wolno lub jest trudny do odczytania.**
**O3:**

-   **Opóźnienie ruchu:** Dostosuj ustawienie „Opóźnienie ruchu”. Wyższa liczba sprawia, że jest wolniej, niższa liczba sprawia, że jest szybciej. Eksperymentuj, aż znajdziesz komfortową prędkość czytania.
-   **Rozmiar czcionki i kontrast:** Upewnij się, że „Rozmiar czcionki suwaka” jest odpowiedni, a „Kolor czcionki” ma dobry kontrast z „Kolorem tła”.
-   **Liczba produktów:** Jeśli masz zbyt wiele produktów i bardzo dużą prędkość, może to być przytłaczające. Zmniejsz „Liczbę produktów” lub spowolnij „Opóźnienie ruchu”.

**P4: Czy mogę przetłumaczyć tekst „Ktoś właśnie kupił…” na inne języki?**
**O4:** Tak, moduły PrestaShop są zazwyczaj możliwe do przetłumaczenia.

-   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym.
-   Wybierz „Tłumaczenia zainstalowanych modułów” dla „Typu tłumaczenia”.
-   Wybierz swój motyw.
-   Wybierz język, na który chcesz przetłumaczyć.
-   Znajdź moduł „Suwak ostatnio sprzedanych produktów” na liście i powinieneś móc edytować przetłumaczalne ciągi znaków.

**P5: Suwak wygląda dobrze na komputerze stacjonarnym, ale jest uszkodzony lub źle sformatowany na urządzeniach mobilnych.**
**O5:**

-   **Wyczyść pamięć podręczną:** Zawsze zaczynaj od wyczyszczenia pamięci podręcznej PrestaShop i przeglądarki.
-   **Responsywność motywu:** Chociaż sam moduł jest zaprojektowany tak, aby był responsywny, mogą wystąpić konflikty z CSS responsywnym Twojego konkretnego motywu.
-   **Sprawdź wypełnienie/obramowania:** Nadmierne wypełnienie lub obramowania mogą wypychać zawartość poza widok na mniejszych ekranach. Spróbuj tymczasowo zmniejszyć „Wypełnienie suwaka” lub „Obramowanie suwaka”, aby sprawdzić, czy to rozwiąże problem.
-   **Sprawdź na urządzeniu mobilnym:** Użyj narzędzi deweloperskich przeglądarki (F12) i przełącz się na widok mobilny lub przetestuj bezpośrednio na urządzeniu mobilnym, aby zdiagnozować konkretne problemy z układem. W przypadku konfliktu może być konieczne dodanie niestandardowego CSS do Twojego motywu, aby dostosować go do urządzeń mobilnych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Suwak ostatnio sprzedanych produktów” dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Suwak ostatnio sprzedanych produktów” (`recentlysoldproducts`) jest zgodny ze standardową architekturą modułów PrestaShop. Jest to moduł jednoplikowy (`recentlysoldproducts.php`), który rozszerza `Module`, obsługując własną instalację, deinstalację, konfigurację (`getContent()`) i wyświetlanie w front-office za pomocą haków. Wykorzystuje klasę `Configuration` PrestaShop do przechowywania ustawień i Smarty do szablonowania. Funkcjonalność front-office jest głównie napędzana przez JavaScript do animacji przewijania i stylizacji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych dedykowanych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu, a renderowanie front-office jest zarządzane bezpośrednio za pośrednictwem haków PrestaShop.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł **nie** zawiera żadnych niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Bezpośrednio wysyła zapytania do bazy danych PrestaShop w celu uzyskania informacji o zamówieniach i produktach w głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`recentlysoldproducts/jscolor/jscolor.js`**

    -   **Zakres:** Back-office (używany w `getContent()` do selektorów kolorów).
    -   **Opis:** Jest to zewnętrzna biblioteka JavaScript, która zapewnia przyjazny dla użytkownika interfejs selektora kolorów dla pól wejściowych. Jest zintegrowana z formularzem konfiguracji modułu, aby umożliwić sprzedawcom łatwe wybieranie kolorów dla tła, obramowania i czcionki suwaka. Zazwyczaj działa poprzez dodanie klasy (np. `jscolor`) do pola wejściowego, które następnie przekształca je w selektor kolorów.
-   **`recentlysoldproducts/js/script.js`**

    -   **Zakres:** Front-office.
    -   **Opis:** Ten plik prawdopodobnie zawiera podstawową logikę animacji przewijania suwaka. Zazwyczaj:
        -   Wybiera element kontenera suwaka (np. według ID lub klasy).
        -   Inicjalizuje zmienne dla kierunku ruchu, prędkości i zawartości.
        -   Implementuje ciągłą pętlę animacji przewijania, potencjalnie używając `setInterval` lub `requestAnimationFrame`.
        -   Obsługuje klonowanie elementów w celu stworzenia efektu nieskończonej pętli.
        -   Dostosowuje się do responsywności lub pauzowania po najechaniu myszą.
-   **`recentlysoldproducts/recentlysoldproducts.js`**

    -   **Zakres:** Front-office.
    -   **Opis:** Ten plik może zawierać dodatkowy JavaScript front-office specyficzny dla inicjalizacji lub interakcji modułu. Może być odpowiedzialny za:
        -   Dynamiczne ładowanie zawartości suwaka (chociaż w tym module jest prawdopodobnie renderowany przez Smarty).
        -   Ustawianie słuchaczy zdarzeń (np. do pauzowania suwaka po najechaniu myszą).
        -   Zapewnienie prawidłowej inicjalizacji suwaka po załadowaniu DOM.
        -   Potencjalnie obsługę AJAX, jeśli moduł miałby pobierać dane asynchronicznie (chociaż nie jest to wyraźnie wskazane przez strukturę modułu).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`recentlysoldproducts/css.css`**

    -   **Zakres:** Front-office.
    -   **Opis:** Jest to prawdopodobnie główny arkusz stylów dla wyświetlania suwaka w front-office. Definiowałby:
        -   Układ i pozycjonowanie kontenera suwaka.
        -   Podstawową stylizację elementów przewijanego tekstu (np. `font-size`, `color`, `padding`).
        -   Style dla tła i obramowań na podstawie konfiguracji modułu.
        -   Potencjalnie responsywne dostosowania dla różnych rozmiarów ekranu.
        -   Kluczowe selektory: `.recentlysoldproducts_block`, `.recentlysoldproducts_item` itp.
-   **`recentlysoldproducts/recentlysoldproducts.css`**

    -   **Zakres:** Front-office.
    -   **Opis:** Ten plik może zawierać dodatkowe lub specyficzne reguły stylów, potencjalnie dla bardziej zaawansowanych efektów wizualnych lub do nadpisywania domyślnych stylów motywu. Biorąc pod uwagę nazewnictwo, może to być również plik redundantny lub starszy, lub zawierać bardziej specyficzną stylizację dla samego mechanizmu przewijania, odrębną od ogólnej stylizacji bloku w `css.css`. Programiści powinni sprawdzić pod kątem nakładających się reguł i potencjalnych konfliktów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`recentlysoldproducts/views/front/rsps.tpl`**
    -   **Zakres:** Front-office (szablon haka).
    -   **Opis:** Jest to główny plik szablonu odpowiedzialny za renderowanie struktury HTML suwaka ostatnio sprzedanych produktów.
    -   **Renderowany w hakach:** `rightColumn`, `displayrightColumn`, `home`, `top`, `displayleftColumn`, `footer`, `displayhome`, `displayheader`, `displaytop`, `displayfooter`, `header`, `leftColumn`.
    -   **Zawartość:** Otrzymuje dane (np. listę ostatnio sprzedanych produktów, ustawienia konfiguracji modułu) z metod `hookDisplay*` w `recentlysoldproducts.php`. Następnie iteruje przez listę produktów, aby wygenerować przewijany tekst, stosując style inline lub klasy na podstawie ustawień konfiguracji modułu (kolory, rozmiary czcionek, wypełnienie itp.). Będzie zawierał główny wrapper HTML dla suwaka i poszczególne wpisy produktów.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Używane klucze to:
        -   `RSPS_C_BG`
        -   `RSPS_C_BORDER`
        -   `RSPS_C_FONT`
        -   `RSPS_S_PADDING`
        -   `RSPS_S_FONT`
        -   `RSPS_S_BORDER`
        -   `RSPS_M_DIR`
        -   `RSPS_M_DELAY`
        -   `RSPS_POSITION`
        -   `RSPS_NB`
        -   `RSPS_ORDER`
        -   `RSPS_DIVERSITY`
    -   Wysyła zapytania do istniejących tabel PrestaShop, głównie `ps_orders`, `ps_order_detail`, `ps_product_lang` i `ps_product`, aby pobrać informacje o ostatnio sprzedanych produktach.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas i miejsce wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Rejestruje zasoby CSS/JS i potencjalnie renderuje ukryty element do inicjalizacji JS. |
| `header` | Alias dla `displayHeader` w starszych wersjach PrestaShop. | To samo co `displayHeader`. |
| `displayHome` | Na stronie głównej, zazwyczaj w głównym obszarze zawartości. | Renderuje blok suwaka na stronie głównej sklepu. |
| `home` | Alias dla `displayHome` w starszych wersjach PrestaShop. | To samo co `displayHome`. |
| `displayTop` | W górnej sekcji strony, często poniżej nagłówka. | Renderuje blok suwaka w górnym obszarze zawartości. |
| `top` | Alias dla `displayTop` w starszych wersjach PrestaShop. | To samo co `displayTop`. |
| `displayLeftColumn` | W lewym pasku bocznym odpowiednich stron. | Renderuje blok suwaka w lewej kolumnie. |
| `leftColumn` | Alias dla `displayLeftColumn` w starszych wersjach PrestaShop. | To samo co `displayLeftColumn`. |
| `displayRightColumn` | W prawym pasku bocznym odpowiednich stron. | Renderuje blok suwaka w prawej kolumnie. |
| `rightColumn` | Alias dla `displayRightColumn` w starszych wersjach PrestaShop. | To samo co `displayRightColumn`. |
| `displayFooter` | W sekcji stopki każdej strony. | Renderuje blok suwaka w stopce. |
| `footer` | Alias dla `displayFooter` w starszych wersjach PrestaShop. | To samo co `displayFooter`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Suwak ostatnio sprzedanych produktów”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
