---
title: "Popup Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Popup Slider od MyPresta.eu."
sidebar:
  label: "Popup Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Popup Slider na MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/popup-slider/)
>
> ---


# Popup Slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu Popup Slider, gdzie zdefiniujesz, jak wygląda i zachowuje się Twoje wyskakujące okienko.

#### Ustawienia ogólne

-   **Szerokość wyskakującego okienka (px):**

    -   **Co robi to ustawienie:** Definiuje szerokość okna wyskakującego w pikselach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretną wartość (np. 800):* Wyskakujące okienko pojawi się dokładnie o szerokości 800 pikseli na ekranach komputerów stacjonarnych.
        -   *Gdy ustawione na inną wartość:* Wyskakujące okienko odpowiednio zmieni rozmiar.
    -   **Zalecana wartość:** 800px (lub dostosuj w zależności od rozmiarów obrazów i projektu).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje obrazy suwaka mają szerokość 800px, ustawienie tej wartości na 800px zapewnia, że pasują idealnie bez problemów ze skalowaniem.
-   **Wysokość wyskakującego okienka (px):**

    -   **Co robi to ustawienie:** Definiuje wysokość okna wyskakującego w pikselach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretną wartość (np. 500):* Wyskakujące okienko pojawi się dokładnie o wysokości 500 pikseli.
        -   *Gdy ustawione na inną wartość:* Wyskakujące okienko odpowiednio zmieni rozmiar.
    -   **Zalecana wartość:** 500px (lub dostosuj w zależności od rozmiarów obrazów i projektu).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje obrazy suwaka mają wysokość 500px, ustawienie tej wartości na 500px zapewnia, że pasują idealnie.
-   **Kolor tła wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor tła samego okna wyskakującego (obszar za obrazami suwaka). Możesz użyć próbnika kolorów do wyboru.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretny kolor (np. #FFFFFF dla białego):* Tło wyskakującego okienka wyświetli ten kolor.
        -   *Gdy ustawione na inny kolor:* Kolor tła zmienia się.
    -   **Zalecana wartość:** #FFFFFF (biały) lub kolor, który uzupełnia projekt Twojego sklepu.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep ma ciemny motyw, możesz wybrać jasnoszary (#F5F5F5) dla tła wyskakującego okienka, aby zawartość wyróżniała się.
-   **Kolor ramki wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor ramki wokół okna wyskakującego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretny kolor (np. #CCCCCC dla jasnoszarego):* Wyskakujące okienko będzie miało ramkę w tym kolorze.
        -   *Gdy ustawione na inny kolor:* Kolor ramki zmienia się.
    -   **Zalecana wartość:** #CCCCCC (jasnoszary) lub kolor pasujący do Twojej marki.
    -   **Scenariusz/przykład dla sprzedawcy:** Subtelna ramka może pomóc zdefiniować wyskakujące okienko na tle zajętego tła.
-   **Szerokość ramki wyskakującego okienka (px):**

    -   **Co robi to ustawienie:** Definiuje grubość ramki wyskakującego okienka w pikselach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 1:* Ramka będzie miała grubość 1 piksela.
        -   *Gdy ustawione na 0:* Ramka nie będzie widoczna.
    -   **Zalecana wartość:** 1px lub 0px.
    -   **Scenariusz/przykład dla sprzedawcy:** Ramka o grubości 0px może stworzyć bardziej płynny, nowoczesny wygląd, jeśli Twój projekt nie wymaga widocznej ramki.
-   **Promień ramki wyskakującego okienka (px):**

    -   **Co robi to ustawienie:** Kontroluje zaokrąglenie rogów wyskakującego okienka. Wyższa wartość oznacza bardziej zaokrąglone rogi.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 0:* Wyskakujące okienko będzie miało ostre, kwadratowe rogi.
        -   *Gdy ustawione na 10:* Rogi będą lekko zaokrąglone.
    -   **Zalecana wartość:** 5px lub 0px.
    -   **Scenariusz/przykład dla sprzedawcy:** Zaokrąglone rogi mogą nadać Twojemu wyskakującemu okienku bardziej miękki, nowoczesny wygląd.
-   **Cień wyskakującego okienka:**

    -   **Co robi to ustawienie:** Dodaje efekt cienia wokół wyskakującego okienka, sprawiając, że wydaje się unosić nad stroną.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Wokół wyskakującego okienka pojawi się subtelny cień.
        -   *Gdy wyłączone (NIE):* Wyskakujące okienko nie będzie miało cienia.
    -   **Zalecana wartość:** TAK.
    -   **Scenariusz/przykład dla sprzedawcy:** Cień pomaga wyskakującemu okienku wyróżnić się z tła, poprawiając widoczność i postrzeganą głębię.
-   **Kolor nakładki wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor półprzezroczystej nakładki, która pokrywa resztę zawartości Twojego sklepu, gdy wyskakujące okienko jest aktywne.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na konkretny kolor (np. #000000 dla czarnego):* Nakładka będzie miała ten kolor.
    -   **Zalecana wartość:** #000000 (czarny).
    -   **Scenariusz/przykład dla sprzedawcy:** Ciemna nakładka pomaga skupić uwagę odwiedzającego wyłącznie na zawartości wyskakującego okienka.
-   **Przezroczystość nakładki wyskakującego okienka (0-1):**

    -   **Co robi to ustawienie:** Kontroluje przezroczystość nakładki. 0 oznacza pełną przezroczystość, 1 oznacza pełną nieprzezroczystość.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 0.5:* Nakładka będzie w 50% przezroczysta, pozwalając na zobaczenie części zawartości sklepu w tle.
        -   *Gdy ustawione na 0.8:* Nakładka będzie w 80% nieprzezroczysta, sprawiając, że zawartość w tle będzie bardzo słabo widoczna.
    -   **Zalecana wartość:** 0.7 lub 0.8.
    -   **Scenariusz/przykład dla sprzedawcy:** Wyższa przezroczystość zapewnia, że wyskakujące okienko jest głównym punktem uwagi, podczas gdy niższa przezroczystość może być używana, jeśli chcesz subtelnie zasugerować zawartość za wyskakującym okienkiem.
-   **Czas ponownego wyświetlania wyskakującego okienka (godziny):**

    -   **Co robi to ustawienie:** Określa, ile godzin musi upłynąć, zanim wyskakujące okienko zostanie ponownie pokazane temu samemu odwiedzającemu po jego zamknięciu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 0:* Wyskakujące okienko będzie pojawiać się za każdym razem, gdy odwiedzający załaduje stronę (niezalecane dla doświadczenia użytkownika).
        -   *Gdy ustawione na 24:* Wyskakujące okienko pojawi się ponownie po 24 godzinach.
        -   *Gdy ustawione na bardzo wysoką liczbę (np. 8760 na 1 rok):* Wyskakujące okienko będzie wyświetlane efektywnie tylko raz na odwiedzającego.
    -   **Zalecana wartość:** 24 (dla codziennych promocji) lub 168 (dla cotygodniowych promocji) lub bardzo wysoka liczba, taka jak 8760 (dla raz w roku lub efektywnie raz na zawsze).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli prowadzisz codzienne oferty, ustawienie tej wartości na 24 godziny zapewnia, że odwiedzający widzą nową ofertę każdego dnia. Jeśli chcesz wyświetlić wiadomość powitalną tylko raz, ustaw ją na bardzo wysoką liczbę.
-   **Pokaż przycisk zamykania:**

    -   **Co robi to ustawienie:** Przełącza widoczność przycisku zamykania „X” na wyskakującym okienku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Przycisk zamykania będzie widoczny, umożliwiając odwiedzającym łatwe zamknięcie wyskakującego okienka.
        -   *Gdy wyłączone (NIE):* Przycisk zamykania nie będzie wyświetlany. Odwiedzający będą musieli kliknąć poza wyskakującym okienkiem lub odejść, aby je zamknąć.
    -   **Zalecana wartość:** TAK.
    -   **Scenariusz/przykład dla sprzedawcy:** Zawsze zapewnij użytkownikom jasny sposób na zamknięcie wyskakującego okienka, aby uniknąć frustracji i poprawić doświadczenie użytkownika.
-   **Zamknij po kliknięciu nakładki:**

    -   **Co robi to ustawienie:** Określa, czy kliknięcie półprzezroczystej nakładki (poza zawartością wyskakującego okienka) zamknie wyskakujące okienko.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Kliknięcie nakładki zamknie wyskakujące okienko.
        -   *Gdy wyłączone (NIE):* Tylko przycisk zamykania (jeśli włączony) lub odejście zamknie wyskakujące okienko.
    -   **Zalecana wartość:** TAK.
    -   **Scenariusz/przykład dla sprzedawcy:** Zapewnia to intuicyjny i powszechny sposób zamykania wyskakujących okienek przez użytkowników, zwiększając użyteczność.

#### Konfiguracja obrazów suwaka

Ta sekcja umożliwia dodawanie, edytowanie i zarządzanie obrazami, które pojawią się w suwaku wyskakującego okienka. Możesz dodać nieograniczoną liczbę obrazów.

Dla każdego miejsca na obraz zazwyczaj znajdziesz:

-   **Pole przesyłania obrazu:**

    -   **Co robi to ustawienie:** Umożliwia przesłanie pliku obrazu z komputera, który ma być wyświetlany w suwaku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po przesłaniu obrazu:* Zastępuje on istniejący obraz w tym miejscu lub dodaje nowy do suwaka.
    -   **Zalecana wartość:** Używaj wysokiej jakości, zoptymalizowanych obrazów, które pasują do proporcji szerokości/wysokości wyskakującego okienka.
    -   **Scenariusz/przykład dla sprzedawcy:** Prześlij swoje najnowsze zdjęcie produktu, baner wyprzedaży lub grafikę promującą nową funkcję.
-   **Link do obrazu (URL):**

    -   **Co robi to ustawienie:** Określa adres URL, na który odwiedzający zostaną przekierowani po kliknięciu tego konkretnego obrazu suwaka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wprowadzeniu adresu URL:* Kliknięcie obrazu przeniesie odwiedzającego na tę stronę.
        -   *Gdy pozostawione puste:* Obraz nie będzie klikalny.
    -   **Zalecana wartość:** Zawsze linkuj do odpowiednich stron (produkt, kategoria, wpis na blogu, strona kontaktowa).
    -   **Scenariusz/przykład dla sprzedawcy:** Połącz baner „Nowości” ze stroną kategorii nowych produktów lub baner „Letnia wyprzedaż” ze stroną docelową wyprzedaży.
-   **Tytuł obrazu/Tekst alternatywny:**

    -   **Co robi to ustawienie:** Zapewnia tekstowy opis obrazu. Ten tekst jest ważny dla SEO (wyszukiwarki) i dostępności (czytniki ekranu dla użytkowników z wadami wzroku).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wprowadzeniu tekstu:* Ten tekst będzie używany przez wyszukiwarki do zrozumienia zawartości obrazu i przez czytniki ekranu do opisania obrazu.
    -   **Zalecana wartość:** Zwięzła, opisowa fraza, która dokładnie opisuje zawartość obrazu i zawiera odpowiednie słowa kluczowe.
    -   **Scenariusz/przykład dla sprzedawcy:** Dla obrazu nowej sukienki użyj „Nowa Kolekcja Letnia Sukienka - Kup Teraz”.
-   **Przycisk usuwania obrazu:**

    -   **Co robi to ustawienie:** Usuwa wybrany obraz z suwaka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po kliknięciu:* Obraz i związane z nim ustawienia są usuwane z konfiguracji suwaka.
    -   **Zalecana wartość:** Użyj tego, aby usunąć nieaktualne promocje lub obrazy.
    -   **Scenariusz/przykład dla sprzedawcy:** Po zakończeniu wyprzedaży usuń obraz banera promującego tę wyprzedaż.
-   **Przycisk dodawania nowego obrazu:**

    -   **Co robi to ustawienie:** Dodaje nowe puste miejsce, abyś mógł przesłać kolejny obraz do suwaka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po kliknięciu:* Pojawia się nowy zestaw pól do przesyłania obrazu, linku i tytułu.
    -   **Zalecana wartość:** Użyj tego, aby rozszerzyć zawartość suwaka.
    -   **Scenariusz/przykład dla sprzedawcy:** Dodaj nowy slajd dla nadchodzącej promocji świątecznej.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Szerokość wyskakującego okienka (px) | 800 | Ustawia szerokość okna wyskakującego. |
| Konfiguracja modułu | Wysokość wyskakującego okienka (px) | 500 | Ustawia wysokość okna wyskakującego. |
| Konfiguracja modułu | Kolor tła wyskakującego okienka | #FFFFFF | Kolor tła obszaru zawartości wyskakującego okienka. |
| Konfiguracja modułu | Kolor ramki wyskakującego okienka | #CCCCCC | Kolor ramki wokół wyskakującego okienka. |
| Konfiguracja modułu | Szerokość ramki wyskakującego okienka (px) | 1 | Grubość ramki wyskakującego okienka. |
| Konfiguracja modułu | Promień ramki wyskakującego okienka (px) | 5 | Zaokrąglenie rogów wyskakującego okienka. |
| Konfiguracja modułu | Cień wyskakującego okienka | TAK | Dodaje efekt cienia dla głębi. |
| Konfiguracja modułu | Kolor nakładki wyskakującego okienka | #000000 | Kolor półprzezroczystej nakładki tła. |
| Konfiguracja modułu | Przezroczystość nakładki wyskakującego okienka (0-1) | 0.7 | Poziom przezroczystości nakładki. |
| Konfiguracja modułu | Czas ponownego wyświetlania wyskakującego okienka (godziny) | 24 | Ile czasu musi upłynąć, zanim wyskakujące okienko ponownie pojawi się odwiedzającemu. |
| Konfiguracja modułu | Pokaż przycisk zamykania | TAK | Wyświetla przycisk „X” do zamykania wyskakującego okienka. |
| Konfiguracja modułu | Zamknij po kliknięciu nakładki | TAK | Umożliwia zamknięcie wyskakującego okienka poprzez kliknięcie poza nim. |
| Konfiguracja modułu | Pole przesyłania obrazu | N/A | Przesyła obraz dla slajdu. |
| Konfiguracja modułu | Link do obrazu (URL) | N/A | Adres URL, na który należy przejść po kliknięciu obrazu slajdu. |
| Konfiguracja modułu | Tytuł obrazu/Tekst alternatywny | N/A | Tekst opisowy dla SEO i dostępności. |
| Konfiguracja modułu | Przycisk usuwania obrazu | N/A | Usuwa slajd z suwaka. |
| Konfiguracja modułu | Przycisk dodawania nowego obrazu | N/A | Dodaje nowe puste miejsce na slajd. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje wyskakujące okienko w ogóle się nie wyświetla. Co powinienem sprawdzić?**
O1:

-   **Moduł włączony:** Najpierw upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**.
-   **Konfiguracja zapisana:** Upewnij się, że zapisałeś ustawienia konfiguracji po wprowadzeniu zmian.
-   **Obrazy dodane:** Czy przesłałeś co najmniej jeden obraz do konfiguracji suwaka? Suwak nie pojawi się, jeśli nie ma obrazów.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) i pamięć podręczną przeglądarki. Czasami stare pliki pamięci podręcznej uniemożliwiają załadowanie nowej zawartości modułu.
-   **Czas ponownego wyświetlania:** Jeśli odwiedziłeś swoją witrynę wcześniej, „Czas ponownego wyświetlania wyskakującego okienka” może uniemożliwiać jego ponowne wyświetlenie. Spróbuj otworzyć swój sklep w oknie incognito/prywatnym przeglądarki, aby zasymulować pierwszego odwiedzającego.

**P2: Moje wyskakujące okienko wygląda dziwnie lub nie jest poprawnie wyśrodkowane w moim niestandardowym motywie.**
O2:

-   **Konflikty motywów:** Niestandardowe motywy czasami mają sprzeczne style CSS.
-   **Ustawienia szerokości/wysokości:** Sprawdź ponownie ustawienia „Szerokość wyskakującego okienka” i „Wysokość wyskakującego okienka” w konfiguracji modułu. Upewnij się, że są one odpowiednie dla Twoich obrazów i rozmiarów ekranu.
-   **Pomoc programisty:** Jeśli problem nadal występuje, może wymagać niewielkiej korekty CSS przez programistę zaznajomionego z Twoim motywem. Mogą oni zbadać elementy i zastosować niestandardowe style, aby rozwiązać konflikty.

**P3: Obrazy w moim suwaku są rozmyte lub zniekształcone.**
O3:

-   **Jakość obrazu:** Upewnij się, że przesyłane obrazy są wysokiej rozdzielczości i nie są pikselowane.
-   **Proporcje:** Obrazy powinny idealnie pasować do proporcji (stosunek szerokości do wysokości) ustawionych dla „Szerokości wyskakującego okienka” i „Wysokości wyskakującego okienka”. Jeśli Twoje obrazy mają inne proporcje, mogą zostać rozciągnięte lub ściśnięte, aby pasowały.
-   **Optymalizacja obrazu:** Chociaż wysoka rozdzielczość jest dobra, nadmiernie duże rozmiary plików mogą spowolnić Twoją witrynę. Zoptymalizuj swoje obrazy do użytku w sieci (np. skompresuj je) przed przesłaniem.

**P4: Czy mogę mieć różne wyskakujące okienka dla różnych stron lub grup klientów?**
O4: Moduł Popup Slider, w swojej obecnej wersji, wyświetla jedno, globalne wyskakujące okienko wszystkim odwiedzającym na podstawie logiki ponownego wyświetlania. Nie obsługuje natywnie różnych wyskakujących okienek dla konkretnych stron lub grup klientów. Do takiej zaawansowanej funkcjonalności zazwyczaj potrzebny byłby bardziej złożony moduł lub niestandardowe opracowanie.

**P5: Jak przetłumaczyć tekst modułu (np. tekst przycisku zamykania, jeśli taki istnieje)?**
O5: Chociaż ten moduł używa głównie obrazów, wszelkie domyślne elementy tekstowe byłyby możliwe do przetłumaczenia za pomocą systemu tłumaczeń PrestaShop:

-   Przejdź do **Lokalizacja > Tłumaczenia**.
-   Wybierz „Tłumaczenia zainstalowanych modułów”.
-   Wybierz swój motyw, swój język, a następnie znajdź „Popup Slider” na liście modułów.
-   Możesz wtedy edytować dowolne przetłumaczalne ciągi znaków.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółową analizę techniczną architektury modułu Popup Slider, przeznaczoną dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł Popup Slider (`popupslider/cz.php`) to klasyczny moduł PrestaShop 1.4-1.6, wykorzystujący głównie klasę `Module` do swojej podstawowej funkcjonalności. Integruje się z front-office za pomocą haka (zazwyczaj `displayHeader` lub `displayFooter` niejawnie, chociaż dokumentacja wspomina `Header, Columns, Product, or Footer` jako potencjalne obszary wyświetlania, dostarczony szablon `header.tpl` sugeruje, że `displayHeader` jest głównym punktem integracji). Konfiguracja jest zarządzana za pomocą metody `getContent()`, przechowując ustawienia w `ps_configuration`. Interakcja z front-office jest obsługiwana przez wstrzykiwanie JavaScript i CSS, które następnie renderują suwak za pomocą biblioteki bxSlider.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Wszystkie dane konfiguracyjne są przechowywane bezpośrednio w tabeli `ps_configuration` za pomocą standardowych metod `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł w dużym stopniu opiera się na JavaScript dla swojej funkcjonalności front-office, w szczególności dla zachowania wyskakującego okienka i suwaka.

-   **`popupslider/jscolor/jscolor.js`**:

    -   **Zakres:** Back-office (używany na stronie konfiguracji modułu).
    -   **Odpowiedzialność:** Zapewnia funkcjonalność próbnika kolorów JavaScript dla formularza konfiguracji modułu, umożliwiając sprzedawcom łatwe wybieranie kolorów tła, ramki i nakładki wyskakującego okienka.
    -   **Szczegóły:** Jest to biblioteka zewnętrzna zintegrowana w celu ulepszenia interfejsu użytkownika w panelu administracyjnym.
-   **`popupslider/js/bxslider.js`**:

    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Jest to podstawowa biblioteka dla animowanego suwaka obrazów w wyskakującym okienku. Obsługuje przejścia, elementy sterujące nawigacji (strzałki, kropki) i responsywne zachowanie prezentacji slajdów.
    -   **Szczegóły:** Powszechnie używany suwak treści jQuery. Moduł inicjalizuje ten suwak na obrazach w wyskakującym okienku.
-   **`popupslider/js/script.js`**:

    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Ten niestandardowy skrypt orkiestruje wygląd i zachowanie wyskakującego okienka.
        -   **Zarządzanie plikami cookie:** Sprawdza plik cookie, aby określić, czy użytkownik jest odwiedzającym po raz pierwszy, czy też upłynął czas ponownego wyświetlania.
        -   **Wyświetlanie wyskakującego okienka:** Wyzwala wyświetlanie nakładki wyskakującego okienka i zawartości suwaka.
        -   **Obsługa zdarzeń:** Wiąże zdarzenia zamykania wyskakującego okienka (np. kliknięcie przycisku zamykania, kliknięcie nakładki).
        -   **Inicjalizacja bxSlider:** Inicjalizuje `bxslider.js` na odpowiednim elemencie DOM zawierającym obrazy suwaka.
    -   **Szczegóły:** Ten skrypt jest kluczowy dla „inteligentnej” logiki wyświetlania modułu i interakcji użytkownika.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie wymienia jawnie niestandardowych plików CSS w dostarczonym spisie. Jednak jest bardzo prawdopodobne, że biblioteka `bxslider.js` zawiera własny CSS (np. `jquery.bxslider.css` lub podobny), który zostałby załadowany, a `header.tpl` lub `cz.php` modułu może wstrzykiwać style inline na podstawie ustawień konfiguracyjnych (kolory, wymiary).

Gdyby były obecne jakiekolwiek pliki CSS, zazwyczaj by:

-   **Zakres:** Front-office (do stylizacji wyskakującego okienka i suwaka).
-   **Główne komponenty interfejsu użytkownika:** Stylizuj kontener wyskakującego okienka, nakładkę, przycisk zamykania, nawigację suwaka (strzałki, kropki) i pojedyncze obrazy slajdów.
-   **Kluczowe selektory klas CSS:** Programiści powinni szukać klas takich jak `.popupslider-overlay`, `.popupslider-container`, `.popupslider-close`, `.bx-wrapper`, `.bx-viewport`, `.bx-controls` itp., aby nadpisać je w `custom.css` swojego motywu lub motywu potomnego.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   **`popupslider/header.tpl`**:
        -   **Hak:** Prawdopodobnie `displayHeader` (lub podobny, biorąc pod uwagę nazwę). Ten szablon jest odpowiedzialny za renderowanie struktury HTML nakładki wyskakującego okienka, kontenera wyskakującego okienka i samego suwaka obrazów.
        -   **Wyjście:** Generuje niezbędne elementy `div` dla nakładki, głównego pola wyskakującego okienka, przycisku zamykania i listy `ul`, którą `bxslider.js` przekształci w interaktywną prezentację slajdów. Prawdopodobnie zawiera również style inline pochodzące z ustawień konfiguracyjnych modułu (szerokość, wysokość, kolory itp.) oraz zawiera niezbędne zasoby JavaScript i CSS.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy niestandardowych tabel bazy danych. Wszystkie ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`.
    -   **Klucze konfiguracyjne (przykłady):**
        -   `POPUP_SLIDER_WIDTH`
        -   `POPUP_SLIDER_HEIGHT`
        -   `POPUP_SLIDER_BG_COLOR`
        -   `POPUP_SLIDER_BORDER_COLOR`
        -   `POPUP_SLIDER_BORDER_WIDTH`
        -   `POPUP_SLIDER_BORDER_RADIUS`
        -   `POPUP_SLIDER_SHADOW`
        -   `POPUP_SLIDER_OVERLAY_COLOR`
        -   `POPUP_SLIDER_OVERLAY_OPACITY`
        -   `POPUP_SLIDER_REDISPLAY_TIME`
        -   `POPUP_SLIDER_SHOW_CLOSE_BTN`
        -   `POPUP_SLIDER_CLOSE_ON_OVERLAY_CLICK`
        -   `POPUP_SLIDER_IMAGE_X` (gdzie X to inkrementujący identyfikator dla każdego obrazu, przechowujący URL, link, tekst alternatywny).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Służy do wstrzykiwania plików CSS i JavaScript modułu oraz potencjalnie początkowej struktury HTML wyskakującego okienka (chociaż samo wyskakujące okienko jest zazwyczaj ukryte, dopóki nie zostanie wyzwolone przez JS). |
| `displayFooter` (Potencjalny) | Wykonywany na końcu sekcji `<body>` każdej strony front-office. | Może być używany jako alternatywa dla `displayHeader` do wstrzykiwania HTML i JS wyskakującego okienka, często preferowany ze względu na wydajność, ponieważ nie blokuje renderowania strony. |
| `displayRightColumn` (Potencjalny) | Wykonywany w prawej kolumnie front-office. | Chociaż wspomniano w opisie dla sprzedawcy, jest mało prawdopodobne, aby pełnoekranowe wyskakujące okienko było renderowane tutaj. Bardziej prawdopodobne dla małego banera lub wyzwalacza. |
| `displayLeftColumn` (Potencjalny) | Wykonywany w lewej kolumnie front-office. | Podobnie jak `displayRightColumn`, mało prawdopodobne dla pełnoekranowego wyskakującego okienka. |
| `displayProductButtons` (Potencjalny) | Wykonywany na stronie produktu, w pobliżu przycisku dodaj do koszyka. | Mało prawdopodobne dla globalnego wyskakującego okienka, ale może być używane dla wyskakującego okienka specyficznego dla produktu, jeśli moduł miałby takie zaawansowane funkcje. |

Biorąc pod uwagę plik `header.tpl`, `displayHeader` jest najbardziej prawdopodobnym hakiem do wstrzykiwania zasobów modułu i początkowej struktury wyskakującego okienka.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Popup Slider, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w świadczenie pomocy i zapewnienie optymalnego funkcjonowania Twojego modułu.

-   **MyPresta.eu Historia Zamówień i Pliki do Pobrania:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Kontakt z Działem Wsparcia:** <https://mypresta.eu/contact>
