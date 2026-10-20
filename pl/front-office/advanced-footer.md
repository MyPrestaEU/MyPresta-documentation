---
title: "Advanced Footer - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Advanced Footer PrestaShop od MyPresta.eu."
sidebar:
  label: "Advanced Footer - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Advanced Footer na MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-footer.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/advanced-footer/)
>
> ---


# Advanced Footer

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak nietypowych wymagań serwerowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran, na którym zdefiniujesz wygląd i styl swojej zaawansowanej stopki.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Advanced Footer” > Kliknij „Konfiguruj”.

#### **Ustawienia i opcje:**

1.  **Szerokość stopki (`advf_f_width`)**

    -   **Co robi to ustawienie:** Kontroluje ogólną szerokość obszaru Twojej niestandardowej stopki. Możesz ustawić ją na stałą wartość w pikselach lub procentach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na stałą wartość w pikselach (np. `1200px`):* Stopka zawsze będzie miała dokładnie taką szerokość, wyśrodkowaną na stronie. Na bardzo szerokich ekranach może pojawić się pusta przestrzeń po bokach. Na węższych ekranach może wprowadzić poziome paski przewijania, jeśli wartość jest zbyt duża.
        -   *Gdy ustawione na procent (np. `100%`):* Stopka rozciągnie się, aby wypełnić dostępną szerokość ekranu, dostosowując się dynamicznie. Jest to ogólnie zalecane dla responsywnych projektów.
    -   **Zalecana wartość:** `100%` dla responsywnej stopki na całą szerokość, lub `1200px`, jeśli główny obszar zawartości Twojego sklepu ma stałą szerokość i chcesz, aby stopka do niej pasowała.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli główny obszar zawartości Twojego sklepu ma szerokość 1200px, ustawienie szerokości stopki na `1200px` sprawi, że będzie idealnie wyrównana, tworząc spójny projekt. Jeśli chcesz, aby stopka zawsze rozciągała się na całe okno przeglądarki, `100%` jest najlepszym rozwiązaniem.
2.  **Wysokość stopki (`advf_f_height`)**

    -   **Co robi to ustawienie:** Definiuje minimalną wysokość obszaru stopki. Jeśli Twoja zawartość jest wyższa niż ta wartość, stopka automatycznie się rozszerzy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretną wartość w pikselach (np. `280px`):* Stopka zawsze będzie miała co najmniej taką wysokość. Może to być przydatne do utrzymania spójnej obecności wizualnej, nawet jeśli niektóre strony mają mniej treści w stopce.
        -   *Gdy pozostawione puste lub ustawione na `auto` (jeśli dostępne):* Wysokość stopki będzie określana wyłącznie przez jej zawartość.
    -   **Zalecana wartość:** `280px` lub `300px` to dobry punkt wyjścia, aby nadać stopce znaczącą obecność. Możesz dostosować tę wartość w zależności od ilości treści, którą planujesz w niej umieścić.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoja stopka zawsze zajmowała zauważalną przestrzeń na dole strony, nawet jeśli masz tylko kilka linków. Ustawienie minimalnej wysokości zapewnia, że nie będzie wyglądać zbyt cienko.
3.  **Kolor tła stopki (`advf_f_bg`)**

    -   **Co robi to ustawienie:** Pozwala wybrać jednolity kolor tła dla całego obszaru stopki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na kolor (np. `#333333` dla ciemnoszarego):* Tło stopki wyświetli ten kolor.
        -   *Gdy pozostawione puste:* Stopka może dziedziczyć tło z Twojego motywu lub być przezroczysta.
    -   **Zalecana wartość:** Kolor, który uzupełnia branding Twojego sklepu. Ciemniejsze kolory (takie jak ciemnoszary lub czarny) są powszechne dla stopek, ale jaśniejszy kolor również może działać w zależności od Twojego projektu.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja marka używa konkretnego odcienia niebieskiego. Możesz ustawić tło stopki na ten niebieski, aby wzmocnić tożsamość swojej marki.
4.  **Kolor tekstu stopki (`advf_f_color`)**

    -   **Co robi to ustawienie:** Ustawia domyślny kolor dla całego tekstu w stopce, w tym linków.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na kolor (np. `#ffffff` dla białego):* Cały tekst w stopce pojawi się w tym kolorze.
        -   *Gdy pozostawione puste:* Kolor tekstu może dziedziczyć z domyślnych ustawień Twojego motywu, co może nie być czytelne na tle wybranego tła stopki.
    -   **Zalecana wartość:** Kolor, który zapewnia dobry kontrast z wybranym `Kolorem tła stopki`. Jeśli Twoje tło jest ciemne, wybierz jasny kolor tekstu (np. biały, jasnoszary). Jeśli Twoje tło jest jasne, wybierz ciemny kolor tekstu.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz ciemnoszare tło stopki. Ustawienie koloru tekstu na biały (`#ffffff`) zapewnia, że wszystkie Twoje linki i informacje są łatwo czytelne.
5.  **Kolor linku stopki po najechaniu myszką (`advf_f_color_hover`)**

    -   **Co robi to ustawienie:** Definiuje kolor, na który zmienią się linki w stopce, gdy klient najedzie na nie myszką.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na kolor (np. `#cccccc` dla jasnoszarego):* Linki wizualnie zmienią się na ten kolor po najechaniu myszką, dostarczając użytkownikowi informacji zwrotnej, że element jest interaktywny.
        -   *Gdy pozostawione puste:* Linki mogą nie mieć efektu najechania myszką, lub mogą dziedziczyć domyślny kolor najechania myszką z Twojego motywu, który może nie pasować do projektu Twojej stopki.
    -   **Zalecana wartość:** Nieco inny odcień `Koloru tekstu stopki` lub kolor akcentujący z palety Twojej marki. Powinien być zauważalny, ale nie rażący.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoje linki w stopce są białe. Ustawienie koloru najechania myszką na jasnoniebieski (`#ADD8E6`) zapewnia subtelną, markową interakcję, gdy klienci przesuwają nad nimi myszkę.
6.  **URL obrazu tła stopki (`advf_f_bg_url`)**

    -   **Co robi to ustawienie:** Pozwala użyć obrazu jako tła dla Twojej stopki zamiast lub oprócz jednolitego koloru. Musisz podać pełny URL do obrazu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy podano prawidłowy URL:* Obraz pojawi się jako tło stopki. `Kolor tła stopki` będzie widoczny, jeśli obraz jest przezroczysty lub jeśli obraz nie pokrywa całej stopki.
        -   *Gdy pozostawione puste:* Nie zostanie użyty żaden obraz tła.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretny, zoptymalizowany obraz tła. Jeśli używasz, upewnij się, że obraz jest lekki i odpowiedni.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz subtelny obraz tekstury, którego chcesz użyć jako tła dla swojej stopki, aby dodać głębi wizualnej. Musisz przesłać ten obraz na swój serwer i wkleić jego URL tutaj.
7.  **Pozycja obrazu tła stopki (`advf_f_bg_pos`)**

    -   **Co robi to ustawienie:** Kontroluje, jak obraz tła (jeśli ustawiony) jest pozycjonowany w obszarze stopki. Typowe wartości to `center center`, `top left`, `bottom right` itp.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na `center center`:* Obraz zostanie wyśrodkowany poziomo i pionowo.
        -   *Gdy ustawione na `top left`:* Obraz rozpocznie się od lewego górnego rogu.
    -   **Zalecana wartość:** `center center` dla większości obrazów, lub `top left`, jeśli Twój obraz to wzór, który ma zaczynać się od rogu.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój obraz tła to małe logo, które chcesz, aby pojawiło się raz na środku stopki. Ustawisz to na `center center`.
8.  **Powtarzanie obrazu tła stopki (`advf_f_bg_repeat`)**

    -   **Co robi to ustawienie:** Określa, czy i jak obraz tła (jeśli ustawiony) powinien się powtarzać, aby wypełnić obszar stopki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na `repeat`:* Obraz będzie kafelkowany poziomo i pionowo.
        -   *Gdy ustawione na `no-repeat`:* Obraz pojawi się tylko raz.
        -   *Gdy ustawione na `repeat-x`:* Obraz będzie kafelkowany tylko poziomo.
        -   *Gdy ustawione na `repeat-y`:* Obraz będzie kafelkowany tylko pionowo.
    -   **Zalecana wartość:** `no-repeat` dla pojedynczych obrazów (jak logo), lub `repeat`, jeśli Twój obraz to mały wzór zaprojektowany do kafelkowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz mały, bezszwowy obraz wzoru. Ustawienie tego na `repeat` sprawi, że pokryje on cały obszar stopki tym wzorem. Jeśli jest to pojedynczy element dekoracyjny, `no-repeat` jest lepsze.

#### Szybka tabela referencyjna konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Szerokość stopki (`advf_f_width`) | `100%` | Ustawia ogólną szerokość stopki. `100%` dla responsywnej pełnej szerokości, `1200px` dla stałej szerokości. |
| Konfiguracja modułu | Wysokość stopki (`advf_f_height`) | `280px` | Definiuje minimalną wysokość stopki. Zapewnia spójną obecność wizualną. |
| Konfiguracja modułu | Kolor tła stopki (`advf_f_bg`) | (Kolor Twojej Marki) | Ustawia jednolity kolor tła dla stopki. Kluczowy dla brandingu i kontrastu. |
| Konfiguracja modułu | Kolor tekstu stopki (`advf_f_color`) | (Kolor kontrastujący) | Ustawia domyślny kolor tekstu w stopce. Zapewnia czytelność na tle. |
| Konfiguracja modułu | Kolor linku stopki po najechaniu myszką (`advf_f_color_hover`) | (Subtelny akcent) | Definiuje kolor linków po najechaniu myszką. Poprawia informację zwrotną dla użytkownika. |
| Konfiguracja modułu | URL obrazu tła stopki (`advf_f_bg_url`) | Pozostaw puste | URL do obrazu, który ma być użyty jako tło stopki. Dodaje teksturę wizualną lub branding. |
| Konfiguracja modułu | Pozycja obrazu tła stopki (`advf_f_bg_pos`) | `center center` | Jak pozycjonowany jest obraz tła. `center center` dla większości pojedynczych obrazów. |
| Konfiguracja modułu | Powtarzanie obrazu tła stopki (`advf_f_bg_repeat`) | `no-repeat` | Jak obraz tła jest kafelkowany. `no-repeat` dla pojedynczych obrazów, `repeat` dla wzorów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje zmiany w stopce nie wyświetlają się w front office.**
**O1:** Zazwyczaj jest to problem z pamięcią podręczną.
\* Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop.
\* Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
\* Jeśli używasz modułu buforowania innej firmy lub buforowania na poziomie serwera (takiego jak Varnish), również wyczyść te pamięci podręczne.
\* Spróbuj także wyczyścić pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+Shift+R).

**P2: Stopka wygląda inaczej na urządzeniach mobilnych niż na komputerach stacjonarnych.**
**O2:** Jest to oczekiwane i zazwyczaj jest to dobra rzecz! Nowoczesne motywy PrestaShop są responsywne, co oznacza, że dostosowują układ do różnych rozmiarów ekranu. Ustawienia modułu (takie jak `Szerokość stopki: 100%`) są zaprojektowane do współpracy z tym. Jeśli konkretne elementy wyglądają na uszkodzone, może to być konflikt z CSS Twojego motywu.
\* **Rozwiązywanie problemów:** Sprawdź CSS Twojego motywu specyficzny dla urządzeń mobilnych. Jeśli dodałeś niestandardową zawartość HTML do stopki, upewnij się, że ta zawartość jest również responsywna. Może być konieczne, aby webmaster sprawdził CSS.

**P3: Jak dodać rzeczywistą zawartość (linki, tekst, obrazy) do tej zaawansowanej stopki?**
**O3:** Ten moduł zapewnia przede wszystkim ramy *stylizacji* (tło, kolory, wymiary) dla Twojej stopki. *Zawartość* stopki jest zazwyczaj zarządzana przez hooki stopki Twojego motywu PrestaShop (takie jak `displayFooter`) lub przez inne moduły przeznaczone do bloków treści (np. moduł niestandardowego bloku HTML lub wbudowany moduł PrestaShop Lista linków).
\* **Rozwiązanie:** Po skonfigurowaniu stylu Advanced Footer, będziesz musiał użyć opcji swojego motywu lub innych modułów treści, aby wypełnić hook `displayFooter` pożądanymi linkami, tekstem i obrazami. Moduł Advanced Footer zastosuje następnie swoją stylizację do tej zawartości.

**P4: Ustawione przeze mnie kolory nie wydają się być stosowane do wszystkich elementów w mojej stopce.**
**O4:** Może się tak zdarzyć, jeśli Twój motyw ma bardzo specyficzne reguły CSS, które nadpisują style modułu.
\* **Rozwiązywanie problemów:** Moduł stosuje ogólną stylizację stopki. Jeśli Twój motyw ma bardziej specyficzne reguły (np. dla `ul li a` wewnątrz stopki), te mogą mieć pierwszeństwo. Może być konieczne skonsultowanie się z webmasterem w celu dodania niestandardowego CSS do Twojego motywu, aby nadpisać konkretne elementy, lub dostosowanie ustawień Twojego motywu, jeśli ma on dedykowaną sekcję dostosowywania stopki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Advanced Footer to standardowy moduł PrestaShop, skupiający się głównie na stylizacji front-office. Wykorzystuje system konfiguracji PrestaShop (`Configuration::updateValue`) do przechowywania swoich ustawień i hookuje się w `displayFooter`, aby wstrzyknąć swój niestandardowy CSS i JavaScript. Nie wprowadza nowych tabel baz danych ani złożonych ObjectModels, co czyni go lekkim i skoncentrowanym na swoim podstawowym zadaniu: dostosowywaniu stopki. Moduł używa metody `getContent()` do konfiguracji w panelu administracyjnym, renderując standardowy formularz PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Moduł bezpośrednio hookuje się w `displayFooter` i `footer`, aby renderować swoją zawartość i stosować style.
-   **Kontrolery Panelu administracyjnego**: Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Główne klasy i modele (`classes/`)

-   W katalogu `classes/` nie są zdefiniowane żadne niestandardowe klasy ani ObjectModels. Cała logika znajduje się w głównym pliku modułu `advfooter.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `advfooter/js/advajax.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Prawdopodobnie obsługuje żądania AJAX związane z zapisywaniem ustawień konfiguracji modułu bez pełnego przeładowania strony lub zapewnia dynamiczną informację zwrotną w formularzu konfiguracji.
-   `advfooter/js/foscript.js`:
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Ten skrypt zawierałby wszelką logikę po stronie klienta lub dynamiczne zachowanie specyficzne dla zaawansowanej stopki po stronie klienta. Może to obejmować responsywne dostosowania, specyficzne efekty najechania myszką nieobsługiwane przez CSS lub interakcje z osadzoną zawartością.
-   `advfooter/js/jscolor/jscolor.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Jest to zewnętrzna biblioteka JavaScript do dostarczania widżetu wyboru koloru w Panelu administracyjnym. Służy do umożliwienia sprzedawcom wizualnego wyboru kolorów dla tła, tekstu i efektów najechania myszką.
-   `advfooter/js/script.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Ogólny skrypt dla strony konfiguracji modułu w Panelu administracyjnym. Może inicjalizować selektor `jscolor`, obsługiwać walidację formularzy lub inne ulepszenia interfejsu użytkownika dla interfejsu administratora.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `advfooter/css/fancybox.css`:
    -   **Zakres:** Front-office (potencjalnie, jeśli moduł używa Fancybox do jakiejkolwiek osadzonej zawartości lub obrazów).
    -   **Odpowiedzialność:** Zapewnia stylizację dla biblioteki lightbox Fancybox, która jest powszechnie używana do wyświetlania obrazów, filmów lub innej zawartości w nakładce modalnej. Jej obecność sugeruje, że moduł może obsługiwać taką funkcjonalność, lub jest dołączona jako ogólne narzędzie.
    -   **Kluczowe selektory klas CSS:** `.fancybox-overlay`, `.fancybox-wrap`, `.fancybox-inner` itp. Programiści mogą je nadpisać, aby dostosować wygląd lightboxa.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `advfooter/footer.tpl`:
        -   **Hook:** `displayFooter` (i potencjalnie `footer` dla starszych motywów).
        -   **Wyjście:** Ten szablon jest odpowiedzialny za renderowanie głównej struktury zaawansowanej stopki. Prawdopodobnie będzie zawierał element HTML `div` lub `footer` z dynamicznymi stylami inline lub atrybutami klas wypełnionymi przez ustawienia konfiguracji modułu (np. `width`, `height`, `background-color`, `background-image`, `color`). Działa jako kontener dla wszelkich treści, które inne moduły lub motyw umieszczają w hooku `displayFooter`.
-   **Szablony administratora (`views/templates/admin/`)**: Brak. Formularz konfiguracji jest prawdopodobnie renderowany bezpośrednio w `getContent()` za pomocą `HelperForm` PrestaShop lub podobnego.
-   **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy: `ADVF_F_WIDTH`, `ADVF_F_HEIGHT`, `ADVF_F_BG`, `ADVF_F_COLOR`, `ADVF_F_COLOR_HOVER`, `ADVF_F_BG_URL`, `ADVF_F_BG_POS`, `ADVF_F_BG_REPEAT`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Służy do rejestrowania zasobów CSS i JavaScript (`foscript.js`, `fancybox.css`) dla front-office oraz potencjalnie wstrzykiwania stylów inline na podstawie konfiguracji modułu. |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` każdej strony Panelu administracyjnego. | Służy do rejestrowania zasobów CSS i JavaScript (`advajax.js`, `jscolor.js`, `script.js`) dla strony konfiguracji modułu. |
| `displayFooter` | Wykonywany na dole strony, zazwyczaj przed zamykającym tagiem `</body>`. | Renderuje szablon `footer.tpl`, który stosuje niestandardową stylizację i działa jako kontener dla zawartości stopki. |
| `footer` | (PrestaShop 1.6 i starsze, lub dla specyficznej kompatybilności z motywami) | Podobnie jak `displayFooter`, używany do renderowania zawartości stopki. Moduł prawdopodobnie rejestruje się w obu dla szerszej kompatybilności. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Znajdziesz tam zakupione moduły i bezpośredni dostęp do zasobów wsparcia.
