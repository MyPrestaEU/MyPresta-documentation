---
title: "Responsywna ramka polubień Facebooka - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Responsywna ramka polubień Facebooka” od MyPresta.eu."
sidebar:
  label: "Responsywna ramka polubień Facebooka - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Responsive Facebook Like Box na MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-facebook-like-box.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/responsive-facebook-like-box/)
>
> ---


# Responsywna ramka polubień Facebooka

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu „Responsywna ramka polubień Facebooka”. Tutaj zdefiniujesz, jak Twoja ramka polubień Facebooka wygląda i zachowuje się w Twoim sklepie.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Responsywna ramka polubień Facebooka” > Kliknij „Konfiguruj”.

#### Ustawienia i opcje:

1.  **Adres URL strony fanowskiej Facebooka:**

    -   **Co robi to ustawienie:** To najważniejsze ustawienie. Informuje moduł, którą konkretną stronę na Facebooku ma wyświetlać w ramce polubień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony jest adres URL Twojej strony na Facebooku (np. `https://www.facebook.com/MyPresta.eu`):* Moduł wyświetli ramkę polubień dla tej konkretnej strony.
        -   *Gdy pozostawiony pusty lub ustawiony na nieprawidłowy adres URL:* Ramka polubień nie wyświetli się poprawnie lub wcale.
    -   **Zalecana wartość:** Twój oficjalny adres URL strony fanowskiej Facebooka.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli strona Twojego sklepu na Facebooku to `https://www.facebook.com/MyAwesomeStore`, wpiszesz ten adres URL tutaj.
2.  **Szerokość ramki polubień (w pikselach):**

    -   **Co robi to ustawienie:** Kontroluje poziomą wielkość ramki polubień Facebooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest konkretna wartość w pikselach (np. `340`):* Ramka polubień spróbuje renderować się z dokładnie tą szerokością.
        -   *Gdy ustawiona jest mniejsza wartość:* Ramka będzie węższa, potencjalnie ukrywając część treści lub zmniejszając tekst.
        -   *Gdy ustawiona jest większa wartość:* Ramka będzie szersza, zajmując więcej miejsca w poziomie.
    -   **Zalecana wartość:** `340` (Jest to często domyślna wartość dla Page Plugin Facebooka i często dobrze sprawdza się w bocznych kolumnach). Dla sekcji o pełnej szerokości możesz użyć większej wartości lub pozostawić ją do automatycznego dostosowania, jeśli motyw na to pozwala.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja prawa kolumna ma 300px szerokości, ustawienie tej wartości na 280-300px zapewni idealne dopasowanie bez przepełnienia.
3.  **Wysokość ramki polubień (w pikselach):**

    -   **Co robi to ustawienie:** Kontroluje pionową wielkość ramki polubień Facebooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest konkretna wartość w pikselach (np. `500`):* Ramka polubień renderuje się z dokładnie tą wysokością.
        -   *Gdy ustawiona jest mniejsza wartość:* Ramka będzie krótsza, potencjalnie wymagając przewijania, aby zobaczyć całą zawartość (taką jak ostatnie posty lub twarze znajomych).
        -   *Gdy ustawiona jest większa wartość:* Ramka będzie wyższa, zajmując więcej miejsca w pionie.
    -   **Zalecana wartość:** `500` (Dobra równowaga, aby pokazać trochę treści bez bycia nadmiernie długą). Dostosuj w zależności od tego, ile treści chcesz wyświetlić (np. więcej postów = większa wysokość).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz wyświetlić 3-4 ostatnie posty z Twojej strony na Facebooku, możesz potrzebować wysokości 500px lub więcej. Jeśli chcesz wyświetlić tylko przycisk „Lubię to” i zdjęcie w tle, mniejsza wysokość, np. 200px, może wystarczyć.
4.  **Pokaż twarze znajomych:**

    -   **Co robi to ustawienie:** Określa, czy ramka polubień wyświetla zdjęcia profilowe osób, które polubiły Twoją stronę i są również znajomymi aktualnego widza.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Ramka polubień pokaże twarze, dodając element dowodu społecznego, ponieważ odwiedzający widzą swoich znajomych połączonych z Twoją marką.
        -   *Gdy wyłączone (NIE):* Twarze nie będą wyświetlane, co skutkuje czystszym, bardziej kompaktowym wyglądem.
    -   **Zalecana wartość:** TAK (Wykorzystuje dowód społeczny do zachęcania do większej liczby polubień).
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji może zwiększyć zaufanie i zaangażowanie, ponieważ klienci są bardziej skłonni do śledzenia marki, którą ich znajomi już lubią.
5.  **Pokaż strumień (posty z Twojej strony):**

    -   **Co robi to ustawienie:** Kontroluje, czy ostatnie posty z Twojej strony na Facebooku są wyświetlane w ramce polubień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Twoje najnowsze posty z Facebooka pojawią się w ramce, dostarczając świeżej treści i zachęcając do interakcji.
        -   *Gdy wyłączone (NIE):* Widoczne będzie tylko zdjęcie w tle, nazwa strony i przycisk „Lubię to”, co sprawi, że ramka będzie bardziej kompaktowa.
    -   **Zalecana wartość:** TAK (Utrzymuje świeżość treści i pokazuje odwiedzającym, jakiego rodzaju treści mogą się spodziewać, jeśli Cię obserwują).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli regularnie publikujesz aktualizacje, promocje lub ciekawe treści na Facebooku, wyświetlanie strumienia utrzymuje zaangażowanie odwiedzających Twoją witrynę w Twoją aktywność w mediach społecznościowych.
6.  **Pokaż nagłówek:**

    -   **Co robi to ustawienie:** Określa, czy mały nagłówek „Facebook” jest wyświetlany na górze ramki polubień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Pojawi się mały nagłówek z logo i tekstem Facebooka.
        -   *Gdy wyłączone (NIE):* Nagłówek zostanie usunięty, co da nieco bardziej zintegrowany wygląd, ale potencjalnie mniej jasne będzie, że jest to widżet Facebooka.
    -   **Zalecana wartość:** TAK (Zapewnia wyraźne oznaczenie marki i kontekst).
    -   **Scenariusz / przykład dla sprzedawcy:** Zachowanie nagłówka pomaga użytkownikom natychmiast rozpoznać go jako widżet Facebooka.
7.  **Użyj małego nagłówka:**

    -   **Co robi to ustawienie:** Jeśli opcja „Pokaż nagłówek” jest włączona, ta opcja kontroluje, czy używana jest mniejsza wersja nagłówka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Nagłówek będzie bardziej kompaktowy.
        -   *Gdy wyłączone (NIE):* Użyty zostanie nagłówek o standardowym rozmiarze.
    -   **Zalecana wartość:** TAK (Często wygląda lepiej w bocznych kolumnach lub mniejszych przestrzeniach).
    -   **Scenariusz / przykład dla sprzedawcy:** Przydatne, jeśli umieszczasz ramkę polubień w wąskiej kolumnie, gdzie przestrzeń jest ograniczona.
8.  **Dostosuj do szerokości kontenera:**

    -   **Co robi to ustawienie:** To kluczowe ustawienie responsywności. Informuje ramkę polubień Facebooka, aby automatycznie dostosowała swoją szerokość do szerokości kontenera, w którym jest umieszczona (np. kolumny Twojego motywu).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Ramka polubień dynamicznie zmieni rozmiar, czyniąc ją prawdziwie responsywną i zapobiegając problemom z przepełnieniem na różnych rozmiarach ekranu. Ustawienie „Szerokość ramki polubień” może zostać nadpisane lub użyte jako maksimum.
        -   *Gdy wyłączone (NIE):* Ramka polubień będzie próbowała zachować ustawienie „Szerokość ramki polubień”, potencjalnie prowadząc do problemów z układem na mniejszych ekranach, jeśli ustawiona szerokość jest zbyt duża.
    -   **Zalecana wartość:** TAK (Niezbędne dla responsywnego projektu i dobrego doświadczenia użytkownika na urządzeniach mobilnych).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli umieścisz ramkę polubień w responsywnym pasku bocznym, włączenie tej opcji zapewni, że zawsze będzie idealnie pasować, niezależnie od urządzenia, z którego korzysta Twój klient.
9.  **Kolor tła (kod szesnastkowy):**

    -   **Co robi to ustawienie:** Pozwala ustawić niestandardowy kolor tła dla ramki polubień za pomocą szesnastkowego kodu koloru (np. `#FFFFFF` dla białego).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony jest konkretny kod szesnastkowy:* Tło ramki polubień zmieni się na ten kolor.
        -   *Gdy pozostawiony pusty lub ustawiony na nieprawidłowy kod:* Użyty zostanie domyślny kolor tła Facebooka (zazwyczaj jasnoszary lub biały).
    -   **Zalecana wartość:** Dopasuj kolor tła do swojego motywu lub pozostaw puste dla wartości domyślnej.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep ma ciemny motyw, możesz ustawić ten kolor na ciemnoszary, aby lepiej się wtopił.
10. **Hak umieszczenia (Placement Hook):**

    -   **Co robi to ustawienie:** Określa, gdzie w Twoim sklepie PrestaShop zostanie wyświetlona ramka polubień Facebooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony na `displayHeader`:* Ramka polubień pojawi się w sekcji nagłówka Twojego sklepu.
        -   *Gdy ustawiony na `displayLeftColumn` lub `displayRightColumn`:* Ramka polubień pojawi się w odpowiednim pasku bocznym.
        -   *Gdy ustawiony na `displayFooter`:* Ramka polubień pojawi się w sekcji stopki.
        -   *Gdy ustawiony na `displayProductButtons` lub podobny hak strony produktu:* Ramka polubień pojawi się na stronach produktów.
    -   **Zalecana wartość:** `displayRightColumn` lub `displayLeftColumn` (Powszechne i skuteczne dla widoczności bez bycia inwazyjnym).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby ramka polubień była widoczna na większości stron bez zajmowania głównego miejsca w nagłówku, umieszczenie jej w kolumnie jest dobrym wyborem. Jeśli chcesz, aby była bardzo widoczna, preferowany może być nagłówek.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Adres URL strony fanowskiej Facebooka | Adres URL Twojej strony na Facebooku | Łączy moduł z Twoją konkretną stroną na Facebooku. |
| Konfiguracja modułu | Szerokość ramki polubień (px) | 340 | Ustawia rozmiar poziomy. |
| Konfiguracja modułu | Wysokość ramki polubień (px) | 500 | Ustawia rozmiar pionowy. |
| Konfiguracja modułu | Pokaż twarze znajomych | TAK | Wyświetla zdjęcia profilowe znajomych dla dowodu społecznego. |
| Konfiguracja modułu | Pokaż strumień (posty) | TAK | Wyświetla ostatnie posty z Twojej strony na Facebooku. |
| Konfiguracja modułu | Pokaż nagłówek | TAK | Wyświetla nagłówek „Facebook”. |
| Konfiguracja modułu | Użyj małego nagłówka | TAK | Używa kompaktowego nagłówka, jeśli „Pokaż nagłówek” jest włączone. |
| Konfiguracja modułu | Dostosuj do szerokości kontenera | TAK | Sprawia, że ramka polubień jest responsywna do swojego kontenera nadrzędnego. |
| Konfiguracja modułu | Kolor tła (Hex) | (Pozostaw puste dla domyślnego) | Dostosowuje kolor tła ramki. |
| Konfiguracja modułu | Hak umieszczenia | displayRightColumn / displayLeftColumn | Określa, gdzie ramka pojawia się w Twoim sklepie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ramka polubień Facebooka nie wyświetla się w moim sklepie. Co powinienem zrobić?**

-   **O:** Najpierw dokładnie sprawdź, czy wprowadziłeś poprawny i kompletny **„Adres URL strony fanowskiej Facebooka”** w konfiguracji modułu. Upewnij się, że zaczyna się od `https://`.
-   **O:** Sprawdź, czy wybrany **„Hak umieszczenia”** jest faktycznie aktywny i wyświetlany przez Twój motyw. Niektóre motywy mogą nie wyświetlać niektórych haków (np. lewej kolumny) na wszystkich stronach. Spróbuj przełączyć się na inny hak, taki jak `displayFooter`, aby sprawdzić, czy tam się pojawi.
-   **O:** Wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Wyczyść również pamięć podręczną przeglądarki.
-   **O:** Upewnij się, że moduł jest włączony. W **Moduły > Menedżer modułów** wyszukaj moduł i upewnij się, że nie jest wyłączony.

**P2: Ramka polubień wygląda zbyt szeroko/wąsko lub zbyt wysoko/nisko.**

-   **O:** Dostosuj ustawienia **„Szerokość ramki polubień”** i **„Wysokość ramki polubień”** w konfiguracji modułu.
-   **O:** Jeśli chcesz, aby automatycznie dostosowywała się do kolumny Twojego motywu, upewnij się, że opcja **„Dostosuj do szerokości kontenera”** jest ustawiona na TAK. Jest to szczególnie ważne dla responsywnych motywów.

**P3: Dlaczego w ramce polubień nie wyświetlają się ostatnie posty ani twarze znajomych?**

-   **O:** Sprawdź ustawienia konfiguracji modułu:
    -   Upewnij się, że opcja **„Pokaż strumień (posty z Twojej strony)”** jest ustawiona na TAK, aby wyświetlać posty.
    -   Upewnij się, że opcja **„Pokaż twarze znajomych”** jest ustawiona na TAK, aby wyświetlać twarze znajomych.
-   **O:** API Facebooka czasami ma ograniczenia lub opóźnienia. Upewnij się, że Twoja strona na Facebooku ma ostatnie publiczne posty.

**P4: Ustawiony przeze mnie kolor tła nie pojawia się.**

-   **O:** Upewnij się, że wprowadziłeś prawidłowy szesnastkowy kod koloru (np. `#RRGGBB`). Jeśli używasz niestandardowego motywu, mogą występować konflikty stylów CSS. Może być konieczne, aby programista internetowy zbadał element i zastosował bardziej specyficzną regułę CSS, jeśli ustawienie modułu jest nadpisywane.

**P5: Moduł działa na komputerze, ale wygląda dziwnie na urządzeniach mobilnych.**

-   **O:** Jest to prawie zawsze spowodowane ustawieniem **„Dostosuj do szerokości kontenera”**. Upewnij się, że jest ustawione na TAK. Informuje to widżet Facebooka, aby był responsywny. Sprawdź również responsywność swojego motywu; jeśli kontener, w którym znajduje się moduł, nie jest responsywny, moduł nie może się idealnie dostosować.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Responsywna ramka polubień Facebooka” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `Responsywna ramka polubień Facebooka` (`likebox/ar.php`) to standardowy moduł PrestaShop, który w stosownych przypadkach stosuje wzorzec MVC do swojej konfiguracji. Wykorzystuje on głównie system haków PrestaShop do wstrzykiwania wtyczki strony Facebooka (ramki polubień) w różne miejsca w front-office. Podstawowa funkcjonalność opiera się na JavaScript SDK wtyczki strony Facebooka, który jest dynamicznie ładowany i konfigurowany na podstawie ustawień modułu. Konfiguracja jest zarządzana za pomocą `Configuration::get()` i `Configuration::updateValue()` w głównej klasie modułu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Główne klasy i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała logika jest hermetyzowana w głównym pliku modułu `ar.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    -   **Zakres:** Back-office (strona konfiguracji administratora).
    -   **Cel:** Jest to zewnętrzna biblioteka JavaScript do wyboru kolorów. Jest używana na stronie konfiguracji modułu, aby zapewnić przyjazny dla użytkownika interfejs do wyboru ustawienia „Kolor tła”.
    -   **Funkcjonalność:** Przekształca standardowe pole tekstowe w interaktywny selektor kolorów, umożliwiając administratorowi wizualne wybranie szesnastkowego kodu koloru.
-   **`likebox/script.js`**

    -   **Zakres:** Front-office.
    -   **Cel:** Ten skrypt jest odpowiedzialny za dynamiczne ładowanie Facebook JavaScript SDK i inicjalizację wtyczki strony Facebooka (ramki polubień) w front-office.
    -   **Funkcjonalność:**
        -   Zazwyczaj sprawdza istnienie Facebook SDK (`FB`) i ładuje go, jeśli nie jest jeszcze obecny.
        -   Następnie wywołuje `FB.XFBML.parse()` lub podobne metody, aby renderować element `div` z klasą `fb-page`, stosując atrybuty (data-href, data-width itp.) na podstawie konfiguracji modułu.
        -   Zapewnia poprawne renderowanie ramki polubień po przygotowaniu DOM.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`likebox/css/css.css`**

    -   **Zakres:** Front-office.
    -   **Cel:** Zawiera ogólne reguły stylów dla kontenera ramki polubień Facebooka i potencjalnie niektóre responsywne dostosowania.
    -   **Kluczowe selektory:** Prawdopodobnie celuje w główny element `div` opakowujący wtyczkę strony Facebooka, zapewniając, że pasuje do układu motywu i obsługuje podstawową responsywność. Programiści mogą nadpisać te style w pliku `custom.css` lub `theme.css` swojego motywu, jeśli zajdzie taka potrzeba.
-   **`likebox/css.css`**

    -   **Zakres:** Front-office.
    -   **Cel:** Podobnie jak `likebox/css/css.css`, ten plik prawdopodobnie zawiera dodatkowe lub alternatywne reguły stylów dla wyświetlania ramki polubień w front-office. Może zawierać reguły dla konkretnych miejsc umieszczenia lub drobne poprawki wizualne.
    -   **Kluczowe selektory:** Celuje w kontener ramki polubień Facebooka i powiązane elementy.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`likebox/header.tpl`**

    -   **Zakres:** Front-office.
    -   **Hak:** `displayHeader` (lub podobny hak związany z nagłówkiem).
    -   **Cel:** Ten szablon jest odpowiedzialny za wyprowadzanie struktury HTML dla ramki polubień Facebooka, gdy moduł jest skonfigurowany do wyświetlania w nagłówku. Zawiera element `div` z klasą `fb-page` i atrybutami `data-*`, których Facebook SDK używa do renderowania wtyczki.
    -   **Zmienne:** Dostęp do zmiennych konfiguracyjnych (np. `{$facebook_page_url}`, `{$width}`, `{$height}`, `{$show_faces}` itp.) przekazanych z logiki PHP modułu.
-   **`likebox/rightcolumn.tpl`**

    -   **Zakres:** Front-office.
    -   **Hak:** `displayRightColumn` (lub `displayLeftColumn`, `displayFooter`, `displayProductButtons` itp., w zależności od wybranego haka).
    -   **Cel:** Ten szablon jest odpowiedzialny za wyprowadzanie struktury HTML dla ramki polubień Facebooka, gdy moduł jest skonfigurowany do wyświetlania w kolumnie lub innych obszarach treści. Zawiera element `div` z klasą `fb-page` i atrybutami `data-*`.
    -   **Zmienne:** Podobnie jak `header.tpl`, ma dostęp do zmiennych konfiguracyjnych w celu dynamicznego ustawiania atrybutów wtyczki.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` (lub z prefiksem `_configuration`) przy użyciu kluczy takich jak `RESPONSIVE_FB_LIKEBOX_URL`, `RESPONSIVE_FB_LIKEBOX_WIDTH` itp.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` strony lub na górze `<body>`. | Wstrzykuje HTML ramki polubień Facebooka i potencjalnie skrypt inicjalizacyjny Facebook SDK. |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym sklepu. | Wstrzykuje HTML ramki polubień Facebooka do lewej kolumny. |
| `displayRightColumn` | Renderuje zawartość w prawym pasku bocznym sklepu. | Wstrzykuje HTML ramki polubień Facebooka do prawej kolumny. |
| `displayFooter` | Renderuje zawartość w sekcji stopki sklepu. | Wstrzykuje HTML ramki polubień Facebooka do stopki. |
| `displayProductButtons` (lub podobny hak strony produktu) | Renderuje zawartość na stronie produktu, często w pobliżu przycisku dodawania do koszyka lub opisu. | Wstrzykuje HTML ramki polubień Facebooka na strony produktów. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje media (JS/CSS). | Rejestruje pliki CSS i JavaScript modułu do wyświetlania w front-office. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administratora ustawia swoje media (JS/CSS). | Rejestruje skrypt `jscolor.js` i potencjalnie CSS specyficzny dla administratora dla strony konfiguracji modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, nowe wersje i oficjalne wsparcie dla modułu „Responsywna ramka polubień Facebooka”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich pytań lub problemów, które możesz napotkać.
