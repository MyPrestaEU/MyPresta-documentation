---
title: "Powiększenie atrybutu koloru / tekstury - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop „Powiększenie atrybutu koloru / tekstury” od MyPresta.eu."
sidebar:
  label: "Powiększenie atrybutu koloru / tekstury - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Color / texture attribute zoom na MyPresta.eu](https://mypresta.eu/modules/front-office-features/color-texture-attribute-zoom.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/color-texture-attribute-zoom/)
>
> ---


# Powiększenie atrybutu koloru / tekstury

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Powiększenie atrybutu koloru / tekstury”, dostępny po instalacji poprzez kliknięcie przycisku „Konfiguruj”.

#### **Włącz / Wyłącz moduł**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania funkcjonalności modułu w całym sklepie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Funkcja powiększenia koloru/tekstury będzie aktywna na stronach produktów i w wyskakujących oknach szybkiego podglądu, zgodnie z innymi wybranymi ustawieniami.
  - *Gdy wyłączony:* Funkcja powiększenia zostanie całkowicie dezaktywowana, a powiększone podglądy nie będą się pojawiać.
- **Zalecana wartość:** **Włączony** (aby korzystać z funkcji modułu).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz tymczasowo wyłączyć funkcję powiększenia w celu konserwacji lub testowania, możesz ją wyłączyć bez odinstalowywania modułu.

#### **Pokaż nazwę koloru / tekstury (wartość)**

- **Co robi to ustawienie:** Określa, czy tekstowa nazwa koloru lub tekstury (np. „Czerwony”, „Skóra”) pojawia się obok powiększonego okna podglądu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Nazwa atrybutu zostanie wyświetlona obok powiększonego obrazu, dostarczając klientowi dodatkowego kontekstu.
  - *Gdy wyłączony:* Pojawi się tylko powiększony obraz, bez etykiety tekstowej.
- **Zalecana wartość:** **Włączony**. Zapewnia to jaśniejsze informacje dla klienta, zwłaszcza jeśli kolory są podobne lub tekstury są subtelne.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz wiele odcieni niebieskiego (np. „Błękit nieba”, „Granatowy”), pokazanie nazwy pomaga klientom wyraźnie je rozróżnić.

#### **Wyłącz zmianę atrybutu po dotknięciu**

- **Co robi to ustawienie:** Kontroluje zachowanie modułu na urządzeniach dotykowych (takich jak smartfony i tablety), gdy klient dotknie próbki koloru/tekstury.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Dotknięcie próbki koloru/tekstury pokaże tylko podgląd powiększenia. Główny obraz produktu na stronie NIE zmieni się, aby odzwierciedlić dotknięty atrybut.
  - *Gdy wyłączony:* Dotknięcie próbki koloru/tekstury pokaże podgląd powiększenia ORAZ zaktualizuje główny obraz produktu, aby pokazać produkt w wybranym kolorze/teksturze.
- **Zalecana wartość:** **Wyłączony**. Większość klientów oczekuje, że główny obraz produktu zaktualizuje się po wybraniu koloru/tekstury, nawet na urządzeniach mobilnych. Włącz to tylko, jeśli masz konkretny powód, aby nie zmieniać głównego obrazu po dotknięciu.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje obrazy produktów są ogólne i nie zmieniają się w zależności od atrybutów koloru, lub jeśli chcesz zapobiec przypadkowym zmianom głównego obrazu na urządzeniach mobilnych, możesz to włączyć. W przeciwnym razie pozostaw to wyłączone dla standardowego zachowania.

#### **Szerokość okna podglądu koloru**

- **Co robi to ustawienie:** Ustawia szerokość (w pikselach) wyskakującego okna, które wyświetla powiększony podgląd koloru.
- **Efekt zmiany tego ustawienia:**
  - *Zwiększenie wartości:* Sprawia, że okno podglądu jest szersze, pokazując więcej szczegółów.
  - *Zmniejszenie wartości:* Sprawia, że okno podglądu jest węższe.
- **Zalecana wartość:** Wartość między **200px a 300px** jest zazwyczaj dobrym kompromisem. Zacznij od `280` i dostosuj w zależności od obrazów produktów i projektu motywu.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje próbki kolorów są bardzo małe i chcesz pokazać znaczące powiększenie, zwiększ tę wartość. Jeśli układ strony produktu jest bardzo wąski, być może będziesz musiał ją zmniejszyć.

#### **Wysokość okna podglądu koloru**

- **Co robi to ustawienie:** Ustawia wysokość (w pikselach) wyskakującego okna, które wyświetla powiększony podgląd koloru.
- **Efekt zmiany tego ustawienia:**
  - *Zwiększenie wartości:* Sprawia, że okno podglądu jest wyższe, pokazując więcej szczegółów.
  - *Zmniejszenie wartości:* Sprawia, że okno podglądu jest niższe.
- **Zalecana wartość:** Wartość między **200px a 300px** jest zazwyczaj dobrym kompromisem. Zacznij od `280` i dostosuj w zależności od obrazów produktów i projektu motywu.
- **Scenariusz / przykład dla sprzedawcy:** Podobnie jak w przypadku szerokości, dostosuj to, aby upewnić się, że powiększony kolor jest wyraźnie widoczny, nie będąc nadmiernie dużym ani małym dla strony produktu.

#### **Aktywuj powiększenie w tabeli kombinacji**

- **Co robi to ustawienie:** Określa, czy funkcja powiększenia powinna również dotyczyć atrybutów koloru/tekstury wyświetlanych w tabeli kombinacji produktów (jeśli Twój motyw jej używa).
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Klienci mogą najeżdżać kursorem/dotykać próbek koloru/tekstury w tabeli kombinacji, aby zobaczyć powiększony podgląd.
  - *Gdy wyłączony:* Funkcja powiększenia będzie działać tylko dla atrybutów koloru/tekstury poza tabelami kombinacji.
- **Zalecana wartość:** **Włączony**. Zapewnia to spójne i pomocne doświadczenie we wszystkich obszarach, gdzie wyświetlane są atrybuty koloru/tekstury.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz koszulki z tabelą pokazującą rozmiary i dostępne kolory, włączenie tej opcji pozwala klientom powiększyć kolory bezpośrednio z tej tabeli.

#### **Szerokość okna podglądu tekstury**

- **Co robi to ustawienie:** Ustawia szerokość (w pikselach) wyskakującego okna, które wyświetla powiększony podgląd tekstury. Jest to oddzielne od szerokości podglądu koloru, co pozwala zoptymalizować dla różnych typów obrazów atrybutów.
- **Efekt zmiany tego ustawienia:**
  - *Zwiększenie wartości:* Sprawia, że podgląd tekstury jest szerszy.
  - *Zmniejszenie wartości:* Sprawia, że podgląd tekstury jest węższy.
- **Zalecana wartość:** Podobnie jak w przypadku koloru, wartość między **200px a 300px** jest często odpowiednia. Zacznij od `280`.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje obrazy tekstur są bardzo szczegółowe i wymagają większego widoku, aby je docenić, możesz ustawić tutaj większą szerokość niż dla prostych próbek kolorów.

#### **Wyklucz niektóre grupy atrybutów koloru z ZOOM**

- **Co robi to ustawienie:** Pozwala określić niektóre grupy atrybutów (np. „Rozmiar”, „Materiał”), dla których funkcja powiększenia NIE powinna być stosowana, nawet jeśli używają obrazów koloru lub tekstury.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wprowadzono identyfikatory grup atrybutów:* Funkcja powiększenia zostanie wyłączona dla wszystkich atrybutów należących do określonych grup.
  - *Gdy pozostawiono puste:* Funkcja powiększenia zostanie zastosowana do wszystkich grup atrybutów koloru/tekstury.
- **Zalecana wartość:** Pozostaw **puste**, chyba że masz konkretny powód, aby wykluczyć grupy. Jeśli musisz wykluczyć, wprowadź numeryczne identyfikatory grup atrybutów, oddzielone przecinkami (np. `1, 5, 12`). Identyfikatory grup atrybutów można znaleźć w Panelu administracyjnym PrestaShop w sekcji **Katalog > Atrybuty i cechy > Grupy atrybutów**.
- **Scenariusz / przykład dla sprzedawcy:** Możesz mieć grupę atrybutów „Dostępność”, która używa próbek kolorów (np. zielony dla dostępnych, czerwony dla niedostępnych), ale nie chcesz, aby te wywoływały powiększenie. W takim przypadku znajdziesz identyfikator grupy atrybutów „Dostępność” i wprowadzisz go tutaj.

#### **Typ animacji**

- **Co robi to ustawienie:** Wybiera efekt wizualny używany, gdy pojawia się okno podglądu powiększenia.
- **Efekt zmiany tego ustawienia:** Zmienia sposób animacji okna podglądu (np. pojawianie się z zanikaniem, przesuwanie).
- **Zalecana wartość:** **Zanikanie**. Jest to zazwyczaj najbardziej subtelna i profesjonalnie wyglądająca animacja. Eksperymentuj z innymi, jeśli wolisz inny efekt.
- **Scenariusz / przykład dla sprzedawcy:** Możesz wybrać animację, która najlepiej pasuje do ogólnej estetyki Twojego sklepu.

#### **Typ animacji aktualizacji**

- **Co robi to ustawienie:** Wybiera efekt wizualny używany, gdy zmienia się zawartość okna podglądu powiększenia (np. podczas przełączania między różnymi kolorami/teksturami, gdy podgląd jest już otwarty).
- **Efekt zmiany tego ustawienia:** Zmienia animację dla aktualizacji zawartości w podglądzie.
- **Zalecana wartość:** **Zanikanie**. Podobnie jak w przypadku początkowej animacji, zanikanie jest zazwyczaj płynne i nie rozprasza uwagi.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli klient szybko najedzie kursorem na wiele próbek kolorów, ta animacja określa, jak płynnie przechodzi zawartość podglądu.

#### Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz moduł | Włączony | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | Pokaż nazwę koloru / tekstury (wartość) | Włączony | Wyświetla nazwę atrybutu z podglądem powiększenia. |
| Konfiguracja modułu | Wyłącz zmianę atrybutu po dotknięciu | Wyłączony | Zapobiega zmianie głównego obrazu po dotknięciu na urządzeniach mobilnych (jeśli włączone). |
| Konfiguracja modułu | Szerokość okna podglądu koloru | 280 | Szerokość wyskakującego okna powiększenia koloru w pikselach. |
| Konfiguracja modułu | Wysokość okna podglądu koloru | 280 | Wysokość wyskakującego okna powiększenia koloru w pikselach. |
| Konfiguracja modułu | Aktywuj powiększenie w tabeli kombinacji | Włączony | Rozszerza powiększenie na atrybuty w tabelach kombinacji. |
| Konfiguracja modułu | Szerokość okna podglądu tekstury | 280 | Szerokość wyskakującego okna powiększenia tekstury w pikselach. |
| Konfiguracja modułu | Wyklucz niektóre grupy atrybutów koloru z ZOOM | Puste | Identyfikatory grup atrybutów do zignorowania dla powiększenia, oddzielone przecinkami. |
| Konfiguracja modułu | Typ animacji | Zanikanie | Animacja pojawiania się podglądu powiększenia. |
| Konfiguracja modułu | Typ animacji aktualizacji | Zanikanie | Animacja zmian zawartości w podglądzie powiększenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Powiększenie nie pojawia się na mojej stronie produktu. Co powinienem sprawdzić?**
O:

1.  **Moduł włączony:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Powiększenie atrybutu koloru / tekstury” jest włączony.
2.  **Konfiguracja atrybutów:** Sprawdź, czy Twoje atrybuty produktu są poprawnie skonfigurowane jako typ „Kolor” lub „Tekstura” w **Katalog > Atrybuty i cechy > Atrybuty**. Upewnij się, że przesłałeś rzeczywiste obrazy dla tych atrybutów, a nie tylko kody kolorów.
3.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”. Wyczyść również pamięć podręczną przeglądarki.
4.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, bardzo mocno dostosowane motywy mogą czasami powodować zakłócenia. Jeśli powyższe kroki nie działają, tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy powiększenie się pojawi. Jeśli tak, Twój motyw może wymagać niewielkiej korekty.

**P: Okno podglądu powiększenia jest za małe/za duże.**
O: Dostosuj ustawienia „Szerokość okna podglądu koloru”, „Wysokość okna podglądu koloru” i „Szerokość okna podglądu tekstury” na stronie konfiguracji modułu. Zwiększ wartości, aby powiększyć okno, zmniejsz je, aby je zmniejszyć. Pamiętaj, aby zapisać zmiany i wyczyścić pamięć podręczną.

**P: Nazwa koloru/tekstury nie pojawia się z powiększeniem.**
O: Sprawdź ustawienie „Pokaż nazwę koloru / tekstury (wartość)” w konfiguracji modułu. Upewnij się, że jest ustawione na „Włączony”.

**P: Na urządzeniach mobilnych, gdy dotykam koloru, główny obraz produktu się nie zmienia, ale chcę, żeby się zmieniał.**
O: Przejdź do konfiguracji modułu i upewnij się, że opcja „Wyłącz zmianę atrybutu po dotknięciu” jest ustawiona na „Wyłączony”. Pozwoli to na aktualizację głównego obrazu produktu po dotknięciu koloru/tekstury.

**P: Chcę wykluczyć konkretną grupę atrybutów z funkcji powiększenia.**
O: Przejdź do **Katalog > Atrybuty i cechy > Grupy atrybutów** w Panelu administracyjnym PrestaShop. Znajdź grupę atrybutów, którą chcesz wykluczyć i zanotuj jej ID (zazwyczaj widoczne w adresie URL podczas edycji lub w samej tabeli). Następnie przejdź do konfiguracji modułu, znajdź „Wyklucz niektóre grupy atrybutów koloru z ZOOM” i wprowadź ID(y) oddzielone przecinkami (np. `1,5,12`).

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Powiększenie atrybutu koloru / tekstury” (`colorzoom`) to moduł funkcji front-office zaprojektowany w celu ulepszenia wizualizacji atrybutów produktu. Wykorzystuje on głównie system hooków PrestaShop do wstrzykiwania swoich zasobów JavaScript i CSS do nagłówka front-office oraz do renderowania specyficznego szablonu powiększenia na stronach produktów. Wykorzystuje bibliotekę `tooltipster` do rzeczywistej funkcji powiększenia/podpowiedzi, dynamicznie dołączając ją do elementów atrybutów koloru i tekstury. Konfiguracja jest zarządzana za pomocą standardowej metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Moduł zawiera dwa kontrolery front-office, chociaż ich podstawowa funkcja w tym module jest często minimalna lub służy do specyficznych potrzeb AJAX, a większość logiki jest obsługiwana po stronie klienta za pomocą JavaScript.

-   **Kontrolery Front-Office**:

    -   `controllers/front/index.php`
        -   Nazwa klasy: `ColorzoomIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   Odpowiedzialność: Ten kontroler prawdopodobnie służy jako rezerwowy lub ogólny punkt wejścia. Biorąc pod uwagę, że główną funkcją modułu jest ulepszanie interfejsu użytkownika za pomocą JS/CSS, ten kontroler może nie mieć rozbudowanej logiki lub może być używany do prostego pobierania danych, jeśli jest to potrzebne przez front-end.
    -   `controllers/front/loader.php`
        -   Nazwa klasy: `ColorzoomLoaderModuleFrontController` (rozszerza `ModuleFrontController`)
        -   Odpowiedzialność: Ten kontroler może być używany do dynamicznego ładowania określonych zasobów lub danych, potencjalnie dla żądań AJAX związanych z funkcją powiększenia, chociaż podstawowa logika powiększenia jest po stronie klienta.
-   **Kontrolery administracyjne Back-Office**: Brak. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani dedykowanych klas logiki biznesowej w katalogu `classes/`. Jego podstawowa funkcjonalność jest zaimplementowana w głównym pliku `colorzoom.php` oraz poprzez jego zasoby JavaScript.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł w dużym stopniu opiera się na JavaScript w zakresie interaktywnej funkcji powiększenia, w szczególności na bibliotece `tooltipster`.

-   `colorzoom/lib/tooltipster/dist/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
    -   Zakres: Front-office.
    -   Szczegóły: Wtyczka do biblioteki `tooltipster`, specjalnie do obsługi elementów SVG w podpowiedziach. Może być używana, jeśli obrazy atrybutów są oparte na SVG lub jeśli moduł musi wchodzić w interakcje z elementami SVG na stronie.
-   `colorzoom/lib/tooltipster/dist/js/tooltipster.bundle.js`
    -   Zakres: Front-office.
    -   Szczegóły: Pełna, spakowana wersja biblioteki `tooltipster`, zapewniająca podstawową funkcjonalność do tworzenia elastycznych i konfigurowalnych podpowiedzi. Jest to główna biblioteka odpowiedzialna za wyskakujące okna powiększenia.
-   `colorzoom/lib/tooltipster/dist/js/tooltipster.core.js`
    -   Zakres: Front-office.
    -   Szczegóły: Podstawowy plik JavaScript dla biblioteki `tooltipster`. Możliwe, że `tooltipster.bundle.js` już go zawiera, ale jest wymieniony oddzielnie, co wskazuje na modułowe włączenie.
-   `colorzoom/views/js/colorzoom-combinationstable.js`
    -   Zakres: Front-office.
    -   Szczegóły: Ten skrypt jest specjalnie przeznaczony dla tabel kombinacji produktów. Prawdopodobnie zawiera logikę do identyfikowania atrybutów koloru/tekstury w tych tabelach i inicjowania na nich funkcji powiększenia `tooltipster`, z uwzględnieniem ustawienia konfiguracji `cz_ctab`. Wiąże słuchaczy zdarzeń z elementami w tych tabelach.
-   `colorzoom/views/js/colorzoom.js`
    -   Zakres: Front-office.
    -   Szczegóły: Jest to główny niestandardowy JavaScript dla modułu. Jest odpowiedzialny za:
        -   Identyfikowanie elementów atrybutów koloru/tekstury na stronie produktu (poza tabelami kombinacji).
        -   Inicjowanie `tooltipster` na tych elementach z konfiguracjami specyficznymi dla modułu (szerokość, wysokość, typ animacji, wyświetlanie nazwy).
        -   Obsługę logiki „Wyłącz zmianę atrybutu po dotknięciu” dla urządzeń mobilnych.
        -   Potencjalne nasłuchiwanie zdarzeń `prestashop.on`, takich jak `updateProduct`, w celu ponownego zainicjowania podpowiedzi, jeśli zawartość produktu zmienia się za pośrednictwem AJAX.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera CSS do stylizacji podglądów powiększenia i biblioteki `tooltipster`.

-   `colorzoom/lib/tooltipster/dist/css/tooltipster.bundle.css`
    -   Zakres: Stylizacja klienta front-office.
    -   Szczegóły: Spakowany CSS dla biblioteki `tooltipster`, zapewniający domyślną stylizację podpowiedzi (okien podglądu powiększenia).
-   `colorzoom/lib/tooltipster/dist/css/tooltipster.core.css`
    -   Zakres: Stylizacja klienta front-office.
    -   Szczegóły: Podstawowy CSS dla `tooltipster`, definiujący fundamentalne style.
-   `colorzoom/views/css/colorszoom.css`
    -   Zakres: Stylizacja klienta front-office.
    -   Szczegóły: Niestandardowy CSS specyficzny dla modułu „Powiększenie atrybutu koloru / tekstury”. Ten plik prawdopodobnie zawiera nadpisania lub dodatkowe style, aby płynnie zintegrować podpowiedzi `tooltipster` ze stroną produktu PrestaShop, zapewniając prawidłowe pozycjonowanie, rozmiary czcionek dla nazw atrybutów i responsywność. Deweloperzy mogą sprawdzić ten plik pod kątem kluczowych selektorów do nadpisania w niestandardowym CSS swojego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do wstrzykiwania swojego JavaScript i CSS oraz do renderowania zawartości podglądu powiększenia.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `colorzoom/views/header.tpl`
        -   Hook: `displayHeader`
        -   Cel: Ten szablon jest odpowiedzialny za włączenie plików CSS i JavaScript modułu do sekcji `<head>` stron front-office. Przekazuje również zmienne konfiguracyjne z back office (takie jak `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_ctab`, `cz_exclusions`) do JavaScript front-endu, czyniąc je dostępnymi do dynamicznej inicjalizacji.
-   **Szablony front-office (`views/templates/front/`)**:
    -   `colorzoom/views/quickview.tpl`
        -   Cel: Ten szablon jest prawdopodobnie zaprojektowany do renderowania w wyskakującym oknie szybkiego podglądu produktu. Zawiera niezbędne znaczniki lub logikę, aby zapewnić prawidłowe zainicjowanie funkcji powiększenia dla atrybutów wyświetlanych w modalach szybkiego podglądu.
    -   `colorzoom/views/zoom.tpl`
        -   Cel: Jest to podstawowy szablon dla zawartości wyświetlanej w podglądzie powiększenia (podpowiedzi). Dynamicznie odbiera adres URL obrazu atrybutu i nazwę atrybutu, renderując je w strukturze podpowiedzi. Jest to wizualny komponent, który wyświetli biblioteka `tooltipster`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `cz_` (np. `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_exclusions`, `cz_ctab`) oraz `mypresta_updates`, `update_`, `updatev_` do zarządzania aktualizacjami.
-   **Tabela zarejestrowanych hooków**:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS i JavaScript modułu oraz przekazuje zmienne konfiguracyjne do front-endu. |
    | `displayProductAdditionalInfo` | W bloku informacji o produkcie na stronie produktu. | Ten hook jest używany do renderowania niezbędnej inicjalizacji JavaScript lub specyficznych znaczników dla funkcji powiększenia na stronie produktu, zapewniając jej aktywność dla atrybutów koloru/tekstury. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy, prosimy o zapoznanie się z kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnianie terminowego wsparcia i optymalnego funkcjonowania modułu.
