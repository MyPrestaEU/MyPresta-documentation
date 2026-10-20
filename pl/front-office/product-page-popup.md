---
title: "Wyskakujące okienko na stronie produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Wyskakujące okienko na stronie produktu” od MyPresta.eu."
sidebar:
  label: "Wyskakujące okienko na stronie produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product page popup na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-popup.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-page-popup/)
>
> ---


# Wyskakujące okienko na stronie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji zostaniesz przekierowany na główną stronę konfiguracji modułu. Tutaj możesz zarządzać wszystkimi swoimi wyskakującymi okienkami na stronach produktów.

Strona konfiguracji jest podzielona na dwie główne sekcje:

1.  Zakładka **„Dodaj nowe wyskakujące okienko”**: Do tworzenia nowych okienek pop-up.
2.  Zakładka **„Lista wyskakujących okienek”**: Do przeglądania, edytowania lub usuwania istniejących pop-upów.

#### 2.1.1 Zakładka „Dodaj nowe wyskakujące okienko”

Ta zakładka pozwala zdefiniować nowe okno pop-up i związane z nim ustawienia.

-   **Nazwa wyskakującego okienka:**
    *   **Co robi to ustawienie:** Jest to wewnętrzna nazwa Twojego pop-upu, widoczna tylko w panelu administracyjnym PrestaShop. Pomaga identyfikować i zarządzać różnymi pop-upami.
    *   **Wpływ zmiany tego ustawienia:** Zmiana tej nazwy wpływa tylko na to, jak ją widzisz w panelu administracyjnym; nie ma wpływu na front-office ani doświadczenie klienta.
    *   **Zalecana wartość:** Użyj opisowej nazwy, np. „Letnia wyprzedaż koszulek”, „Przewodnik po rozmiarach dżinsów”, „Samouczek wideo dla produktu X”.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz pop-up dla konkretnego produktu, nazwij go tak, aby łatwo go później znaleźć.
-   **Treść wyskakującego okienka:**
    *   **Co robi to ustawienie:** Jest to główna treść, która zostanie wyświetlona w oknie pop-up. Jest to edytor tekstu sformatowanego (TinyMCE), w którym możesz dodawać tekst, obrazy, filmy, linki, a nawet niestandardowy kod HTML.
    *   **Wpływ zmiany tego ustawienia:** Bezpośrednio zmienia to, co widzą Twoi klienci, gdy pojawi się pop-up. Możesz uczynić go informacyjnym, promocyjnym lub interaktywnym.
    *   **Zalecana wartość:** Zachowaj zwięzłość i atrakcyjność wizualną. Używaj nagłówków, punktorów i odpowiednich obrazów.
    *   **Scenariusz / przykład dla sprzedawcy:** Możesz dodać kod rabatowy, osadzone wideo z YouTube demonstrujące produkt lub szczegółową tabelę rozmiarów.
-   **Szerokość wyskakującego okienka (px):**
    *   **Co robi to ustawienie:** Definiuje szerokość okna pop-up w pikselach.
    *   **Wpływ zmiany tego ustawienia:** Większa szerokość sprawi, że pop-up będzie szerszy, potencjalnie mieszcząc więcej treści w poziomie. Mniejsza szerokość sprawi, że będzie węższy.
    *   **Zalecana wartość:** Zacznij od `600px` i dostosuj w zależności od treści. Upewnij się, że wygląda dobrze na różnych rozmiarach ekranu.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój pop-up zawiera szeroki obraz lub tabelę, możesz potrzebować większej szerokości. Dla prostego tekstu węższa szerokość może być wystarczająca.
-   **Wysokość wyskakującego okienka (px):**
    *   **Co robi to ustawienie:** Definiuje wysokość okna pop-up w pikselach.
    *   **Wpływ zmiany tego ustawienia:** Większa wysokość sprawi, że pop-up będzie wyższy, umożliwiając więcej treści w pionie bez przewijania. Mniejsza wysokość sprawi, że będzie krótszy, potencjalnie wymagając przewijania, jeśli treść przekroczy wysokość.
    *   **Zalecana wartość:** Zacznij od `400px` i dostosuj w zależności od treści.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz długi opis tekstowy lub wysoki obraz, zwiększ wysokość. Jeśli treść jest krótka, mniejsza wysokość wygląda czyściej.
-   **Kolor tła wyskakującego okienka:**
    *   **Co robi to ustawienie:** Pozwala wybrać kolor tła samego okna pop-up. Używa narzędzia do wyboru kolorów.
    *   **Wpływ zmiany tego ustawienia:** Zmienia wygląd wizualny pop-upu, pomagając mu dopasować się do brandingu Twojego sklepu lub wyróżnić się.
    *   **Zalecana wartość:** Wybierz kolor, który uzupełnia projekt Twojego sklepu i zapewnia dobrą czytelność treści.
    *   **Scenariusz / przykład dla sprzedawcy:** Użyj głównego koloru swojej marki dla tła lub neutralnej bieli/jasnej szarości dla maksymalnej czytelności.
-   **Kolor ramki wyskakującego okienka:**
    *   **Co robi to ustawienie:** Pozwala wybrać kolor ramki wokół okna pop-up.
    *   **Wpływ zmiany tego ustawienia:** Dodaje wizualną ramkę do pop-upu, definiując jego krawędzie.
    *   **Zalecana wartość:** Często subtelny kolor ramki, który pasuje do estetyki Twojego sklepu lub kontrastujący kolor, aby pop-up wyróżniał się.
    *   **Scenariusz / przykład dla sprzedawcy:** Jasnoszara ramka dla czystego wyglądu lub żywy kolor, jeśli pop-up ma bardzo przyciągać uwagę.
-   **Szerokość ramki wyskakującego okienka (px):**
    *   **Co robi to ustawienie:** Definiuje grubość ramki pop-upu w pikselach.
    *   **Wpływ zmiany tego ustawienia:** Wyższa wartość sprawia, że ramka jest grubsza i bardziej widoczna.
    *   **Zalecana wartość:** `1px` lub `2px` dla subtelnej ramki.
    *   **Scenariusz / przykład dla sprzedawcy:** Ramka `5px` może być użyta dla bardzo odważnej, pilnej wiadomości, podczas gdy `1px` jest bardziej powszechny dla ogólnych informacji.
-   **Promień ramki wyskakującego okienka (px):**
    *   **Co robi to ustawienie:** Kontroluje zaokrąglenie rogów pop-upu. Wartość `0` oznacza ostre, kwadratowe rogi. Wyższe wartości tworzą bardziej zaokrąglone rogi.
    *   **Wpływ zmiany tego ustawienia:** Wpływa na ogólną estetykę pop-upu, sprawiając, że wygląda on łagodniej lub bardziej nowocześnie.
    *   **Zalecana wartość:** `0px` dla ostrych rogów, `5px` do `10px` dla lekko zaokrąglonych rogów.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli projekt Twojego sklepu wykorzystuje zaokrąglone elementy, promień ramki `10px` sprawiłby, że pop-up lepiej by się wpasował.
-   **Kolor nakładki wyskakującego okienka:**
    *   **Co robi to ustawienie:** Jest to kolor półprzezroczystej warstwy, która pojawia się za pop-upem, przyciemniając resztę strony produktu.
    *   **Wpływ zmiany tego ustawienia:** Zmienia kontrast wizualny między pop-upem a tłem. Ciemniejsza nakładka sprawia, że pop-up bardziej się wyróżnia.
    *   **Zalecana wartość:** Półprzezroczysta czerń (`#000000` z pewną przezroczystością) jest standardem.
    *   **Scenariusz / przykład dla sprzedawcy:** Nieco jaśniejsza nakładka może być użyta, jeśli chcesz, aby informacje o produkcie w tle były nadal nieco widoczne.
-   **Przezroczystość nakładki wyskakującego okienka (0-100):**
    *   **Co robi to ustawienie:** Kontroluje przezroczystość koloru nakładki. `0` oznacza pełną przezroczystość (niewidoczny), `100` oznacza pełną nieprzezroczystość (jednolity kolor, całkowicie ukrywa tło).
    *   **Wpływ zmiany tego ustawienia:** Określa, ile z podstawowej strony produktu jest widoczne przez nakładkę.
    *   **Zalecana wartość:** `70` do `80` to dobry balans, sprawiający, że pop-up jest widoczny, ale nie całkowicie zasłaniający stronę.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klient nadal delikatnie widział obraz produktu za pop-upem, użyj niższej przezroczystości, np. `50`.
-   **Produkty dla tego wyskakującego okienka:**
    *   **Co robi to ustawienie:** To kluczowa część, w której wybierasz, które konkretne produkty wywołają ten pop-up. Możesz wyszukiwać produkty po nazwie.
    *   **Wpływ zmiany tego ustawienia:** Pop-up pojawi się *tylko* na stronach produktów, które tutaj wybierzesz. Jeśli nie wybrano żadnych produktów, pop-up nie pojawi się nigdzie.
    *   **Zalecana wartość:** Wybierz wszystkie odpowiednie produkty dla tej konkretnej wiadomości.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli utworzyłeś pop-up z przewodnikiem po rozmiarach dla „Męskich koszulek”, wybierzesz tutaj wszystkie swoje męskie koszulki.

Po skonfigurowaniu wszystkich ustawień kliknij przycisk **„Zapisz”**, aby utworzyć nowe wyskakujące okienko.

#### 2.1.2 Zakładka „Lista wyskakujących okienek”

Ta zakładka wyświetla tabelę wszystkich utworzonych przez Ciebie pop-upów.

-   **Kolumny tabeli:**
    *   **ID:** Unikalny identyfikator pop-upu.
    *   **Nazwa:** Wewnętrzna nazwa, którą nadałeś pop-upowi.
    *   **Produkty:** Wyświetla liczbę produktów powiązanych z tym pop-upem.
    *   **Akcje:**
        *   **Edytuj:** Kliknij ikonę ołówka, aby wrócić do zakładki „Dodaj nowe wyskakujące okienko” ze wszystkimi aktualnymi ustawieniami pop-upu wstępnie wypełnionymi, co pozwala na ich modyfikację.
        *   **Usuń:** Kliknij ikonę kosza, aby trwale usunąć pop-up. Pojawi się monit potwierdzający.
-   **Wpływ zmian:**
    *   **Edytowanie:** Pozwala aktualizować treść, stylizację lub powiązania produktów dla istniejącego pop-upu bez tworzenia nowego.
    *   **Usuwanie:** Trwale usuwa pop-up z Twojego sklepu. Nie będzie już wyświetlany na żadnych stronach produktów.
-   **Zalecany przepływ pracy:** Regularnie przeglądaj tę listę, aby upewnić się, że wszystkie Twoje pop-upy są aktualne i trafne. Usuń wszelkie przestarzałe promocje lub informacje.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Dodaj nowe wyskakujące okienko** | Nazwa wyskakującego okienka | Opisowa nazwa | Wewnętrzna identyfikacja dla panelu administracyjnego. |
| | Treść wyskakującego okienka | Niestandardowy HTML/Tekst | Główna wiadomość wyświetlana klientowi. |
| | Szerokość wyskakującego okienka (px) | 600px | Rozmiar poziomy wyskakującego okienka. |
| | Wysokość wyskakującego okienka (px) | 400px | Rozmiar pionowy wyskakującego okienka. |
| | Kolor tła wyskakującego okienka | Biały / Kolor marki | Kolor tła obszaru treści wyskakującego okienka. |
| | Kolor ramki wyskakującego okienka | Subtelny / Kolor marki | Kolor ramki wokół wyskakującego okienka. |
| | Szerokość ramki wyskakującego okienka (px) | 1px - 2px | Grubość ramki wyskakującego okienka. |
| | Promień ramki wyskakującego okienka (px) | 0px - 10px | Zaokrąglenie rogów wyskakującego okienka. |
| | Kolor nakładki wyskakującego okienka | Półprzezroczysta czerń | Kolor przyciemnionego tła. |
| | Przezroczystość nakładki wyskakującego okienka (0-100) | 70 - 80 | Przezroczystość nakładki tła. |
| | Produkty dla tego wyskakującego okienka | Wybierz odpowiednie produkty | Określa, na których stronach produktów pojawi się wyskakujące okienko. |
| **Lista wyskakujących okienek** | Akcja Edytuj | N/A | Modyfikuj ustawienia istniejącego wyskakującego okienka. |
| | Akcja Usuń | N/A | Trwale usuń wyskakujące okienko. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje wyskakujące okienko nie pojawia się na stronie produktu. Co powinienem sprawdzić?**
O:

1.  **Czy wyskakujące okienko jest powiązane z właściwym produktem?** Przejdź do konfiguracji modułu, edytuj swoje wyskakujące okienko i upewnij się, że konkretny produkt, na którym testujesz, jest wybrany w polu „Produkty dla tego wyskakującego okienka”.
2.  **Czy moduł jest włączony?** W **Moduły > Menedżer modułów** upewnij się, że „Wyskakujące okienko na stronie produktu” jest zainstalowane i włączone.
3.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Pamięć podręczna przeglądarki również może wymagać wyczyszczenia (Ctrl+F5 lub Cmd+R).
4.  **Sprawdź błędy JavaScript:** Otwórz konsolę deweloperską przeglądarki (F12) i poszukaj błędów w zakładce „Konsola”. Jeśli widzisz błędy, może to wskazywać na konflikt z innym modułem lub Twoim motywem.

**P: Wyskakujące okienko wygląda dziwnie lub nie pasuje do stylistyki mojego motywu.**
O:

1.  **Przejrzyj ustawienia stylizacji wyskakującego okienka:** Dokładnie sprawdź ustawienia „Kolor tła wyskakującego okienka”, „Kolor ramki wyskakującego okienka”, „Szerokość ramki wyskakującego okienka” i „Promień ramki wyskakującego okienka” w konfiguracji modułu.
2.  **Konflikty motywu:** CSS Twojego motywu może nadpisywać style modułu. Jeśli czujesz się komfortowo z CSS, możesz sprawdzić elementy wyskakującego okienka za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować konflikty stylów. W przypadku złożonych problemów ze stylizacją może być potrzebna pomoc programisty.

**P: Czy mogę mieć wiele wyskakujących okienek na tej samej stronie produktu?**
O: Nie, moduł jest zaprojektowany do wyświetlania jednego konkretnego wyskakującego okienka na stronę produktu. Jeśli produkt jest powiązany z wieloma wyskakującymi okienkami, zostanie wyświetlone tylko jedno (zazwyczaj pierwsze znalezione lub to z najniższym ID, chociaż to zachowanie nie jest wyraźnie gwarantowane i należy go unikać). Najlepszą praktyką jest tworzenie jednego kompleksowego wyskakującego okienka na produkt lub grupę produktów.

**P: Jak przetłumaczyć treść wyskakującego okienka na różne języki?**
O: Pole „Treść wyskakującego okienka” w konfiguracji modułu powinno oferować zakładki językowe, jeśli Twój sklep PrestaShop ma włączonych wiele języków. Po prostu przełącz się na żądaną zakładkę językową i wprowadź przetłumaczoną treść dla tego języka.

**P: Treść wyskakującego okienka jest zbyt długa i wymaga przewijania. Jak to naprawić?**
O:

1.  **Zwiększ wysokość wyskakującego okienka:** W konfiguracji modułu zwiększ wartość „Wysokość wyskakującego okienka (px)”.
2.  **Skróć treść:** Spróbuj uczynić treść wyskakującego okienka bardziej zwięzłą. Używaj punktorów, krótszych akapitów i, jeśli to możliwe, linków do zewnętrznych stron dla bardzo szczegółowych informacji.
3.  **Zoptymalizuj obrazy/filmy:** Upewnij się, że wszelkie media w wyskakującym okienku są zoptymalizowane do użytku internetowego, aby zapobiec nadmiernemu czasowi ładowania i poprawić wyświetlanie.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Product page popup` dla PrestaShop 1.5.x i 1.6.x stosuje prosty, monolityczny wzorzec projektowy typowy dla starszych modułów PrestaShop. Głównie wykorzystuje klasę `Module` do swojej podstawowej funkcjonalności, obsługując instalację, deinstalację i konfigurację. Wyświetlanie na front-office jest zarządzane poprzez podłączanie się do standardowych punktów wyświetlania, podczas gdy konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu. Dane są przechowywane bezpośrednio w `ps_configuration` i zarządzane poprzez standardowe interakcje z bazą danych PrestaShop. Nie ma niestandardowych klas `ObjectModel` ani dedykowanych kontrolerów front/admin poza głównym plikiem modułu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów front-office ani back-office w katalogu `controllers/`. Cała logika front-office jest obsługiwana bezpośrednio w głównym pliku modułu za pomocą hooków, a cała konfiguracja back-office jest zarządzana przez metodę `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie zawiera żadnych niestandardowych klas PHP ani modeli w katalogu `classes/`. Cała obsługa danych i logika biznesowa są hermetyzowane w głównym pliku modułu `ajax_productpopup.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`productpopup/js/jscolor/jscolor.js`**
    *   **Zakres:** Panel administracyjny.
    *   **Opis:** Jest to zewnętrzna biblioteka JavaScript zapewniająca funkcjonalność wyboru kolorów. Jest używana w formularzu konfiguracji modułu, aby umożliwić sprzedawcom łatwe wybieranie kolorów tła, ramki i nakładki wyskakującego okienka. Zazwyczaj działa poprzez dołączanie się do pól wejściowych o określonej klasie (np. `jscolor`).
-   **`productpopup/js/script.js`**
    *   **Zakres:** Front-office.
    *   **Opis:** Ten skrypt zawiera podstawową logikę wyświetlania wyskakującego okienka na front-office.
        *   **Słuchacze zdarzeń:** Prawdopodobnie nasłuchuje zdarzenia `DOMContentLoaded` lub podobnego, aby upewnić się, że strona jest w pełni załadowana.
        *   **Manipulacja DOM:** Jest odpowiedzialny za:
            *   Sprawdzanie, czy bieżący identyfikator produktu ma powiązane wyskakujące okienko.
            *   Dynamiczne tworzenie struktury HTML wyskakującego okienka (nakładka, kontener wyskakującego okienka, obszar treści, przycisk zamykania).
            *   Wstrzykiwanie treści wyskakującego okienka (pobranej z konfiguracji modułu).
            *   Stosowanie skonfigurowanych stylów (szerokość, wysokość, kolory, ramka, przezroczystość).
            *   Wyświetlanie wyskakującego okienka z animacją (np. zanikanie).
            *   Wiązanie zdarzeń do zamykania wyskakującego okienka (kliknięcie przycisku zamykania, kliknięcie na nakładkę, naciśnięcie klawisza ESC).
-   **`productpopup/js/tinymce16.inc.js`**
    *   **Zakres:** Panel administracyjny.
    *   **Opis:** Ten plik jest skryptem integracyjnym dla edytora tekstu sformatowanego TinyMCE, specjalnie dostosowanym do środowisk PrestaShop 1.6.x. Inicjalizuje edytor TinyMCE dla pola tekstowego „Treść wyskakującego okienka” w formularzu konfiguracji modułu, zapewniając sprzedawcy interfejs WYSIWYG do tworzenia bogatej treści HTML dla wyskakujących okienek. Konfiguruje opcje TinyMCE, takie jak dostępne przyciski, wtyczki i ustawienia językowe.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`productpopup/css/productpopup.css`**
    *   **Zakres:** Front-office.
    *   **Opis:** Ten arkusz stylów definiuje domyślny wygląd wizualny i układ wyskakującego okienka na stronie produktu oraz jego nakładki.
        *   **Główne komponenty interfejsu użytkownika:** Style dla `.productpopup-overlay` (przyciemnione tło) i `.productpopup-container` (rzeczywiste pole wyskakującego okienka).
        *   **Kluczowe selektory klas CSS:**
            *   `.productpopup-overlay`: Kontroluje `position`, `top`, `left`, `width`, `height`, `background-color`, `opacity`, `z-index`.
            *   `.productpopup-container`: Kontroluje `position`, `top`, `left`, `transform` (do centrowania), `background-color`, `border`, `border-radius`, `box-shadow`, `z-index`, `overflow`.
            *   `.productpopup-content`: Style dla wewnętrznego obszaru treści, w tym `padding`, `font-size`, `line-height`.
            *   `.productpopup-close`: Style dla przycisku zamykania (np. `position`, `top`, `right`, `font-size`, `color`, `cursor`).
        *   **Nadpisywanie przez dewelopera:** Deweloperzy mogą nadpisać te style w pliku `global.css` swojego motywu lub tworząc niestandardowy arkusz stylów załadowany po tym, celując w te konkretne klasy.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Ten moduł nie definiuje jawnie szablonów dla konkretnych hooków w tym katalogu. Kod HTML wyskakującego okienka na front-office jest prawdopodobnie generowany dynamicznie przez `script.js` na podstawie konfiguracji.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   **`productpopup/views/templates/admin/tabs-no-product.tpl`**
        *   **Opis:** Ten szablon jest prawdopodobnie używany w metodzie `getContent()` modułu do renderowania formularza „Dodaj nowe wyskakujące okienko”, gdy żadne konkretne wyskakujące okienko nie jest edytowane, lub być może uproszczonej wersji formularza. Zawiera pola wejściowe dla nazwy wyskakującego okienka, treści, wymiarów, kolorów i interfejsu wyboru produktu.
    *   **`productpopup/views/templates/admin/tabs.tpl`**
        *   **Opis:** Jest to główny szablon strony konfiguracji modułu w panelu administracyjnym. Zazwyczaj renderuje strukturę zakładek (np. „Dodaj nowe wyskakujące okienko” i „Lista wyskakujących okienek”) i zawiera treść innych szablonów administracyjnych (takich jak `tabs-no-product.tpl`) w swoich panelach zakładek. Renderuje również tabelę do wyświetlania istniejących wyskakujących okienek.
-   **Szablony front-office (`views/templates/front/`)**:
    *   **`productpopup/views/templates/front/footer.tpl`**
        *   **Opis:** Ten szablon jest prawdopodobnie używany do wyprowadzania małego, ukrytego kontenera HTML lub zmiennej JavaScript, która przechowuje dane wyskakującego okienka (treść, style, identyfikatory produktów) dla skryptu `script.js` na front-office, aby je pobrać i dynamicznie renderować wyskakujące okienko. Zazwyczaj jest podłączony do `displayFooter` lub `displayHeader`, aby zapewnić dostępność danych przy każdym ładowaniu strony.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy niestandardowych tabel SQL. Wszystkie ustawienia konfiguracji i dane wyskakujących okienek są przechowywane w standardowej tabeli konfiguracji PrestaShop: `ps_configuration`.
    *   **Klucze konfiguracji**:
        *   `PRODUCTPOPUP_DATA`: Przechowuje serializowane dane dla wszystkich utworzonych wyskakujących okienek, w tym ich treść, stylizację i powiązane identyfikatory produktów. Ten klucz przechowuje złożoną strukturę tablicową.
        *   Inne klucze mogą istnieć dla globalnych ustawień modułu, jeśli takie są, ale podstawowe dane znajdują się w `PRODUCTPOPUP_DATA`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Prawdopodobnie używany do dołączania plików CSS i JavaScript (`productpopup.css`, `script.js`) dla funkcjonalności wyskakującego okienka na front-office. |
| `displayFooter` | Wykonywany na końcu sekcji `<body>` każdej strony. | Może być używany do wyprowadzania ukrytych danych dla `script.js` lub do zapewnienia, że struktura HTML wyskakującego okienka zostanie dołączona do DOM po całej innej treści. |
| `displayProductTab` (PrestaShop 1.6.x) / `displayProductExtraContent` (PrestaShop 1.7+) | Wykonywany na stronie produktu, zazwyczaj w zakładkach produktu lub obszarze dodatkowej treści. | Chociaż opis modułu sugeruje okno modalne, może używać tego hooka do wstrzykiwania wyzwalacza dla wyskakującego okienka lub do zapewnienia, że jego JS jest ładowany specjalnie na stronach produktów. |
| `displayRightColumn` / `displayLeftColumn` | Wykonywany w bocznych kolumnach sklepu. | Mniej prawdopodobne dla wyskakującego okienka na stronie produktu, ale może być używane do wstrzykiwania globalnego wyzwalacza lub małego skryptu, jeśli to konieczne. |
| `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Wykonywany, gdy produkt jest dodawany, aktualizowany lub usuwany. | Może być używany do aktualizacji lub czyszczenia `PRODUCTPOPUP_DATA` w `ps_configuration`, jeśli produkt powiązany z wyskakującym okienkiem zostanie usunięty. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia deweloperskiego, prosimy odnieść się do swojego konta klienta na MyPresta.eu. Upewnij się, że pobierasz najnowszą wersję modułu „Wyskakujące okienko na stronie produktu” kompatybilną z Twoją instalacją PrestaShop. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
