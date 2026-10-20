---
title: "Efekt ładowania przy zmianie atrybutu - preloader - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Efekt ładowania przy zmianie atrybutu - preloader” od MyPresta.eu."
sidebar:
  label: "Efekt ładowania przy zmianie atrybutu - preloader - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Loading effect on attribute change - preloader na MyPresta.eu](https://mypresta.eu/modules/front-office-features/loading-effect-on-attribute-change-preloader.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/loading-effect-on-attribute-change-preloader/)
>
> ---


# Efekt ładowania przy zmianie atrybutu - preloader

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień. Ten moduł ma prostą stronę konfiguracji.

#### **Włącz / Wyłącz Preloader**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania efektu ładowania w całym sklepie.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Animacja ładowania pojawi się na stronach produktów za każdym razem, gdy klient zmieni atrybuty produktu.
  - *Gdy wyłączone (NIE):* Animacja ładowania nie pojawi się, a strony produktów będą zachowywać się tak, jak przed zainstalowaniem modułu (tj. brak wizualnej informacji zwrotnej podczas zmian atrybutów).
- **Zalecana wartość:** TAK
- **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz go aktywować. Ustaw to na TAK. Jeśli musisz tymczasowo go wyłączyć do testów lub podczas dużej aktualizacji motywu, możesz przełączyć go na NIE.

#### **Typ Preloadera**

- **Co robi to ustawienie:** Ta opcja pozwala wybrać styl lub typ animacji ładowania, która będzie wyświetlana. Moduł zazwyczaj zawiera wybór predefiniowanych animacji wskaźnika.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na „Wskaźnik 1”:* Zostanie wyświetlony określony typ animowanego wskaźnika (np. prosty obracający się okrąg).
  - *Gdy ustawione na „Wskaźnik 2”:* Zostanie wyświetlony inny animowany wskaźnik (np. pulsująca kropka, zanikający pasek).
  - *Gdy ustawione na „Niestandardowy obraz”:* Jeśli dostępne, ta opcja pozwoliłaby na przesłanie własnego pliku GIF lub obrazu do użycia jako preloader. (Na podstawie opisu modułu, może to być przyszłe ulepszenie lub bardziej zaawansowana opcja niebezpośrednio wspomniana, ale jest to powszechna funkcja dla ustawień „typu preloadera”).
- **Zalecana wartość:** Eksperymentuj z dostępnymi opcjami, aby zobaczyć, która najlepiej pasuje do projektu i marki Twojego sklepu. Prosty, czysty wskaźnik jest często najlepszy.
- **Scenariusz / przykład dla sprzedawcy:** Twój sklep ma minimalistyczny design, więc możesz wybrać „Wskaźnik 1”, jeśli jest to czysta, nienachalna animacja. Jeśli Twoja marka jest bardziej zabawna, możesz wybrać bardziej dynamiczny „Wskaźnik 2” lub nawet przesłać niestandardowy GIF z logo, jeśli opcja jest dostępna.

#### **Kolor Preloadera**

- **Co robi to ustawienie:** Pozwala to zdefiniować kolor animacji ładowania. Jest to kluczowe dla dopasowania preloadera do schematu kolorów Twojego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na `#007bff` (niebieski):* Wskaźnik pojawi się w kolorze niebieskim.
  - *Gdy ustawione na `#ff0000` (czerwony):* Wskaźnik pojawi się w kolorze czerwonym.
- **Zalecana wartość:** Kolor, który uzupełnia podstawowe lub akcentujące kolory Twojego sklepu. Często dobrze sprawdza się neutralna szarość, biel lub główny kolor akcji Twojej marki.
- **Scenariusz / przykład dla sprzedawcy:** Główne przyciski wezwania do działania w Twoim sklepie są zielone. Ustawienie koloru preloadera na zielony sprawi, że będzie on wyglądał jak zintegrowana część projektu Twojego sklepu, a nie ogólny element.

#### **Rozmiar Preloadera (w pikselach)**

- **Co robi to ustawienie:** Kontroluje fizyczne wymiary (szerokość i wysokość) animacji ładowania.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na `32px`:* Wskaźnik będzie mały i subtelny.
  - *Gdy ustawione na `64px`:* Wskaźnik będzie większy i bardziej widoczny.
- **Zalecana wartość:** Zacznij od umiarkowanego rozmiaru, takiego jak `40px` lub `48px`. Przetestuj na komputerze stacjonarnym i urządzeniach mobilnych, aby upewnić się, że jest widoczny, ale nie jest zbyt inwazyjny.
- **Scenariusz / przykład dla sprzedawcy:** Na stronie produktu z dużymi obrazami wskaźnik `32px` może zginąć. Zwiększenie go do `48px` lub `56px` sprawiłoby, że byłby bardziej zauważalny, nie rozpraszając uwagi. Odwrotnie, jeśli obrazy produktów są małe, mniejszy wskaźnik może być bardziej odpowiedni.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz Preloader | TAK | Aktywuje lub dezaktywuje animację ładowania przy zmianach atrybutów produktu. |
| Konfiguracja modułu | Typ Preloadera | (Wybierz według preferencji) | Wybiera styl wizualny wskaźnika ładowania. |
| Konfiguracja modułu | Kolor Preloadera | (Dopasuj do swojej marki) | Ustawia kolor animacji ładowania, aby zintegrować ją z projektem Twojego sklepu. |
| Konfiguracja modułu | Rozmiar Preloadera (w pikselach) | 40px - 56px | Dostosowuje fizyczny rozmiar wskaźnika dla widoczności i estetyki. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale nie widzę żadnego efektu ładowania na mojej stronie produktu.**
O:

1.  **Wyczyść pamięć podręczną:** Najczęstszy powód. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
2.  **Pozycja modułu:** Upewnij się, że moduł jest poprawnie podpięty. Chociaż moduł automatycznie to obsługuje, czasami konflikty motywów mogą to uniemożliwić. Moduł zazwyczaj wstrzykuje swoje CSS/JS do haka `displayHeader`.
3.  **Nadpisania motywu:** Jeśli używasz mocno dostosowanego motywu, może on nadpisywać domyślne zachowanie JavaScript PrestaShop dla zmian atrybutów, uniemożliwiając modułowi wykrycie zdarzenia. Skontaktuj się z twórcą motywu lub ekspertem PrestaShop.
4.  **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub przetestować w oknie incognito/prywatnym.

**P: Preloader pojawia się, ale wygląda nie na miejscu lub nie pasuje do projektu mojego sklepu.**
O:

1.  **Dostosuj kolor i rozmiar:** Przejdź do strony konfiguracji modułu i eksperymentuj z ustawieniami „Kolor Preloadera” i „Rozmiar Preloadera”. Spróbuj dopasować podstawowe lub akcentujące kolory swojej marki.
2.  **Zmień typ preloadera:** Jeśli dostępne, wypróbuj różne opcje „Typ Preloadera”, aby znaleźć taki, który wizualnie lepiej pasuje do Twojego motywu.
3.  **Niestandardowy CSS:** W celu zaawansowanej personalizacji, webmaster może użyć niestandardowego CSS do dopracowania jego wyglądu (patrz Przewodnik dla deweloperów).

**P: Preloader pojawia się, ale pozostaje na ekranie zbyt długo, nawet po zaktualizowaniu atrybutów produktu.**
O: Zazwyczaj wskazuje to na konflikt JavaScript lub problem z mechanizmem aktualizacji atrybutów Twojego motywu. Moduł opiera się na standardowych zdarzeniach PrestaShop, aby wiedzieć, kiedy ukryć preloader.

1.  **Sprawdź błędy JavaScript:** Otwórz konsolę deweloperską przeglądarki (F12) i poszukaj czerwonych komunikatów o błędach w zakładce „Konsola” podczas zmiany atrybutów.
2.  **Konflikty modułów:** Tymczasowo wyłącz inne moduły front-office, które modyfikują zachowanie strony produktu (np. moduły szybkiego podglądu, niestandardowe moduły atrybutów), aby sprawdzić, czy któryś z nich powoduje konflikt.
3.  **Kompatybilność motywu:** Upewnij się, że Twój motyw jest w pełni kompatybilny z Twoją wersją PrestaShop i nie ma przestarzałego JavaScriptu.

**P: Czy ten moduł spowalnia moją witrynę?**
O: Nie, sam moduł jest bardzo lekki. Dodaje niewielką ilość CSS i JavaScript do Twojej strony. Jego celem jest *wizualne zarządzanie* percepcją czasu ładowania, a nie jego powodowanie. Jeśli Twoja strona jest wolna, problem leży gdzie indziej (np. duże obrazy, niezoptymalizowany serwer, inne ciężkie moduły).

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Efekt ładowania przy zmianie atrybutu - preloader” (`ppreloader`) to lekki moduł skoncentrowany na front-office, zaprojektowany w celu poprawy doświadczenia użytkownika podczas aktualizacji atrybutów produktu napędzanych przez AJAX. Wykorzystuje on głównie hak `displayHeader` PrestaShop do wstrzykiwania swojego CSS i JavaScript, który następnie nasłuchuje określonych zmian DOM lub zdarzeń na stronie produktu, aby wywołać i ukryć animację ładowania. Nie wprowadza nowych tabel baz danych ani złożonej logiki backendowej, koncentrując się wyłącznie na prezentacji front-endowej.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Działa całkowicie za pośrednictwem swojego głównego pliku modułu i zasobów front-endowych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`ppreloader/views/js/ppreloader.js`**
    -   **Zakres:** Front-office (Strona Produktu).
    -   **Odpowiedzialność:** Ten skrypt jest rdzeniem funkcjonalności modułu.
        -   Czeka na gotowość DOM.
        -   Nasłuchuje zmian w selektorach atrybutów produktu (np. `select[name="group[X]"]`, przyciski radiowe, selektory kolorów itp., w zależności od struktury motywu).
        -   Prawdopodobnie nasłuchuje również zdarzeń AJAX związanych z aktualizacjami kombinacji produktów (np. zdarzenie `updateProduct` lub wywołania `ajaxComplete` celujące w określone adresy URL).
        -   Po wykryciu zmiany atrybutu i zainicjowaniu wywołania AJAX, dynamicznie wstawia strukturę HTML preloadera (zdefiniowaną w `header.tpl` lub generowaną na bieżąco) do odpowiedniego kontenera na stronie produktu (np. `$('#product_images')` lub `$('#product-details')`).
        -   Stosuje wybrany `Typ Preloadera`, `Kolor Preloadera` i `Rozmiar Preloadera` z konfiguracji modułu.
        -   Po zakończeniu wywołania AJAX i zaktualizowaniu informacji o produkcie, usuwa HTML preloadera z DOM.
        -   Zapewnia responsywność preloadera na urządzeniach mobilnych.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`ppreloader/views/css/ppreloader.css`**
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Odpowiedzialność:** Ten arkusz stylów definiuje wygląd wizualny i animację preloadera ładowania.
        -   Zawiera style dla nakładki, która może zakrywać obszar produktu podczas ładowania.
        -   Definiuje CSS dla różnych typów preloaderów (wskaźniki, kropki itp.), w tym ich klatki kluczowe animacji.
        -   Zapewnia, że preloader jest wyśrodkowany i prawidłowo umieszczony w swoim kontenerze.
        -   Obsługuje podstawową responsywność dla różnych rozmiarów ekranu.
    -   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać:**
        -   `.ppreloader-overlay`: Główny kontener nakładki.
        -   `.ppreloader-spinner`: Kontener dla rzeczywistej animacji wskaźnika.
        -   Specyficzne klasy dla różnych typów wskaźników (np. `.ppreloader-spinner-type1`, `.ppreloader-spinner-type2`).
        -   Reguły `@keyframes` dla animacji.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **`ppreloader/views/header.tpl`**
    -   **Zakres:** Front-office.
    -   **Hak:** `displayHeader`
    -   **Odpowiedzialność:** Ten szablon jest przede wszystkim odpowiedzialny za włączenie plików CSS i JavaScript modułu do sekcji `<head>` stron front-office.
        -   Używa `{$css_dir}ppreloader.css` do linkowania arkusza stylów.
        -   Używa `{$js_dir}ppreloader.js` do linkowania pliku JavaScript.
        -   Prawdopodobnie zawiera również wbudowany JavaScript do przekazywania ustawień konfiguracyjnych modułu (status włączenia, typ, kolor, rozmiar) z Back Office do skryptu `ppreloader.js`, udostępniając je do dynamicznego użycia. Jest to kluczowe, aby JS wiedział, jak renderować preloader.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele baz danych**: Ten moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu standardowych kluczy konfiguracyjnych PrestaShop (np. `PPRELOADER_ENABLED`, `PPRELOADER_TYPE`, `PPRELOADER_COLOR`, `PPRELOADER_SIZE`).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS (`ppreloader.css`) i JavaScript (`ppreloader.js`) modułu, a także przekazuje zmienne konfiguracyjne do JS. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i pobrania najnowszych wersji modułu „Efekt ładowania przy zmianie atrybutu - preloader”, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
