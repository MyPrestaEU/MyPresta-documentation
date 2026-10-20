---
title: "Blok obrazów producentów (marek) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Blok obrazów producentów (marek)” od MyPresta.eu."
sidebar:
  label: "Blok obrazów producentów (marek) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Manufacturers (brands) images block na MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturers-brands-images-block.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/manufacturers-brands-images-block/)
>
> ---


# Blok obrazów producentów (marek)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „Blok obrazów producentów (marek)”. Tutaj możesz dostosować wygląd i zachowanie bloku marek w Twoim sklepie.

#### **Pozycja bloku producentów**

-   **Co robi to ustawienie:** To kluczowe ustawienie określa, gdzie blok obrazów marek pojawi się na Twojej stronie internetowej. Możesz wybrać spośród różnych predefiniowanych lokalizacji (hooków) w Twoim szablonie PrestaShop.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy ustawione na `displayRightColumn` (lub `displayLeftColumn`):* Blok marek pojawi się w prawej (lub lewej) kolumnie bocznej Twojego sklepu, zazwyczaj obok innych bloków, takich jak kategorie czy bestsellery. Jest to świetne dla stałej widoczności.
    *   *Gdy ustawione na `displayFooter`:* Blok pojawi się na samym dole Twojej strony internetowej, często używany do dodatkowej nawigacji.
    *   *Gdy ustawione na `displayTop` (lub `displayTopColumn`):* Blok będzie widoczny w górnej części Twojej strony, często w obszarze nagłówka, co sprawia, że marki są natychmiast zauważalne.
    *   *Gdy ustawione na `displayHome`:* Blok pojawi się tylko na stronie głównej Twojego sklepu, czyniąc go centralnym elementem odkrywania marek.
-   **Zalecana wartość:** `displayHome` dla prominentnej funkcji na stronie głównej, lub `displayRightColumn` (lub `displayLeftColumn`) dla stałej widoczności na stronach produktów i kategorii.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klienci mogli łatwo przeglądać marki podczas zakupów produktów, wybierz `displayRightColumn`. Jeśli chcesz mocno podkreślić marki na swojej stronie głównej, wybierz `displayHome`.

#### **Włącz karuzelę**

-   **Co robi to ustawienie:** To ustawienie przekształca statyczną siatkę logotypów marek w animowaną, przewijaną karuzelę.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Logotypy marek będą przewijać się poziomo, umożliwiając wyświetlenie wielu marek w kompaktowej przestrzeni. Jest to wizualnie dynamiczne i oszczędza miejsce na ekranie.
    *   *Gdy wyłączone (NIE):* Logotypy marek będą wyświetlane jako statyczna siatka, pokazując wszystkie dostępne logotypy jednocześnie (lub tyle, ile zmieści się w wymiarach bloku). Oferuje to natychmiastowy przegląd bez interakcji.
-   **Zalecana wartość:** `TAK`, jeśli masz wiele marek lub chcesz uzyskać bardziej nowoczesny, dynamiczny wygląd. `NIE`, jeśli masz tylko kilka marek i preferujesz statyczne wyświetlanie.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli oferujesz ponad 50 marek, włączenie karuzeli jest niezbędne, aby uniknąć bardzo długiego, zagraconego bloku. Jeśli masz tylko 5-10 marek, statyczne wyświetlanie może być wystarczające.

#### **Aktywuj filtr kategorii**

-   **Co robi to ustawienie:** Pozwala modułowi wyświetlać tylko tych producentów, którzy są powiązani z produktami w *aktualnie przeglądanej kategorii*.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Na stronie kategorii (np. „T-shirty”) blok marek pokaże tylko loga producentów, którzy produkują T-shirty. Dzięki temu blok jest bardzo istotny dla aktualnego kontekstu przeglądania klienta.
    *   *Gdy wyłączone (NIE):* Blok marek zawsze pokaże *wszystkich* aktywnych producentów w Twoim sklepie, niezależnie od aktualnej strony czy kategorii.
-   **Zalecana wartość:** `TAK` dla lepszego doświadczenia użytkownika i trafności, zwłaszcza w sklepach z różnorodnymi kategoriami produktów.
-   **Scenariusz / przykład dla sprzedawcy:** Klient przeglądający „Smartfony” zobaczy tylko marki takie jak Apple, Samsung i Xiaomi, jeśli ta opcja jest włączona, zamiast widzieć również marki odzieżowe. Pomaga to zawęzić wyszukiwanie.

#### **Włącz automatyczne przewijanie karuzeli**

-   **Co robi to ustawienie:** Jeśli karuzela jest włączona, to ustawienie kontroluje, czy loga marek automatycznie przewijają się bez interakcji klienta.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Karuzela będzie automatycznie przesuwać się przez loga marek z ustaloną prędkością, tworząc dynamiczny efekt wizualny.
    *   *Gdy wyłączone (NIE):* Karuzela będzie przewijać się tylko wtedy, gdy klient ręcznie kliknie strzałki nawigacyjne lub przeciągnie karuzelę.
-   **Zalecana wartość:** `TAK` dla bardziej angażującego i dynamicznego wyświetlania, ale upewnij się, że prędkość nie jest zbyt duża.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz zapewnić, aby wszystkie Twoje marki były widoczne, nawet jeśli klienci nie wchodzą w interakcję z karuzelą. Włączenie automatycznego przewijania to osiąga.

#### **Prędkość automatycznego przewijania**

-   **Co robi to ustawienie:** To ustawienie określa, jak szybko karuzela automatycznie przewija się z jednego zestawu marek do następnego, mierzone w milisekundach. (Dotyczy tylko, jeśli „Włącz automatyczne przewijanie karuzeli” jest ustawione na TAK).
-   **Efekt zmiany tego ustawienia:**
    *   *Wyższa wartość (np. 5000ms = 5 sekund):* Wolniejsza prędkość przewijania, dająca klientom więcej czasu na obejrzenie każdego zestawu logotypów.
    *   *Niższa wartość (np. 2000ms = 2 sekundy):* Szybsza prędkość przewijania, czyniąca karuzelę bardziej dynamiczną, ale potencjalnie trudniejszą do odczytania.
-   **Zalecana wartość:** 3000-5000 milisekund (3-5 sekund) dla komfortowego oglądania.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz wiele marek i chcesz, aby klienci zobaczyli je wszystkie bez pośpiechu, ustaw wolniejszą prędkość, np. 4000ms.

#### **Wstrzymaj karuzelę po najechaniu myszką**

-   **Co robi to ustawienie:** Jeśli automatyczne przewijanie jest włączone, to ustawienie kontroluje, czy karuzela tymczasowo zatrzymuje przewijanie, gdy klient przesunie kursor myszy nad blokiem marek.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Karuzela zatrzyma się, umożliwiając klientowi wygodne obejrzenie logo marki lub kliknięcie go bez przesuwania się karuzeli. Poprawia to doświadczenie użytkownika.
    *   *Gdy wyłączone (NIE):* Karuzela będzie kontynuować automatyczne przewijanie, nawet jeśli mysz znajduje się nad nią, co może być frustrujące dla klientów próbujących wchodzić w interakcję.
-   **Zalecana wartość:** `TAK` dla lepszego doświadczenia użytkownika.
-   **Scenariusz / przykład dla sprzedawcy:** Klient widzi markę, którą lubi, i przesuwa mysz, aby ją kliknąć. Jeśli karuzela się zatrzyma, może łatwo kliknąć. Jeśli nie, marka może się przewinąć, zanim zdąży zareagować.

#### **Rozmiar obrazu marki**

-   **Co robi to ustawienie:** To ustawienie pozwala zdefiniować maksymalną szerokość obrazów marek wyświetlanych w bloku. Wysokość będzie skalowana proporcjonalnie.
-   **Efekt zmiany tego ustawienia:**
    *   *Większa wartość (np. 150px):* Loga marek będą większe, co sprawi, że będą bardziej widoczne i łatwiejsze do zauważenia. Może to zająć więcej miejsca w bloku.
    *   *Mniejsza wartość (np. 80px):* Loga marek będą mniejsze, co pozwoli zmieścić więcej logotypów w danej przestrzeni, ale potencjalnie uczyni je mniej zauważalnymi.
-   **Zalecana wartość:** 100-120 pikseli dla dobrej równowagi między widocznością a efektywnością przestrzeni. Dostosuj w zależności od układu Twojego szablonu.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój pasek boczny jest wąski, możesz potrzebować ustawić mniejszy rozmiar obrazu (np. 80px), aby zapobiec przepełnieniu logotypów. W szerokim bloku na stronie głównej możesz użyć 150px dla większego efektu.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Pozycja bloku producentów | `displayHome` lub `displayRightColumn` | Określa, gdzie pojawia się blok marek (np. strona główna, pasek boczny, stopka). |
| Konfiguracja modułu | Włącz karuzelę | `TAK` | Przekształca statyczną siatkę w przewijaną karuzelę dla dynamicznego wyświetlania. |
| Konfiguracja modułu | Aktywuj filtr kategorii | `TAK` | Pokazuje tylko marki związane z aktualnie przeglądaną kategorią. |
| Konfiguracja modułu | Włącz automatyczne przewijanie karuzeli | `TAK` | Sprawia, że karuzela automatycznie przewija się przez marki. |
| Konfiguracja modułu | Prędkość automatycznego przewijania | 3000-5000ms | Kontroluje szybkość przewijania karuzeli (w milisekundach). |
| Konfiguracja modułu | Wstrzymaj karuzelę po najechaniu myszką | `TAK` | Zatrzymuje automatyczne przewijanie, gdy klient najedzie kursorem na blok. |
| Konfiguracja modułu | Rozmiar obrazu marki | 100-120px | Ustawia maksymalną szerokość dla logotypów marek w bloku. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój blok marek nie wyświetla się po instalacji lub jest w niewłaściwym miejscu.**

-   **O:** Najpierw sprawdź stronę konfiguracji modułu w Panelu administracyjnym. Upewnij się, że ustawienie „Pozycja bloku producentów” jest poprawnie wybrane. Jeśli jest ustawione na `displayHome`, pojawi się tylko na stronie głównej. Jeśli jest ustawione na kolumnę, upewnij się, że Twój szablon faktycznie wyświetla tę kolumnę na przeglądanych stronach.
-   **O:** Wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami zmiany w szablonie lub instalacja nowych modułów wymagają odświeżenia pamięci podręcznej.
-   **O:** Sprawdź „Pozycje” swojego szablonu (Wygląd > Pozycje w PS 1.7/8). Upewnij się, że moduł jest podpięty do żądanej pozycji. Jeśli nie ma go na liście, spróbuj ponownie zapisać konfigurację modułu.

**P2: Moje obrazy marek wyglądają na zniekształcone lub mają niewłaściwy rozmiar.**

-   **O:** Przejdź do konfiguracji modułu i dostosuj ustawienie „Rozmiar obrazu marki”. Kontroluje to maksymalną szerokość.
-   **O:** Upewnij się, że oryginalne obrazy producentów przesłane do PrestaShop (Katalog > Producenci) są dobrej jakości i idealnie mają spójny współczynnik proporcji. Chociaż moduł je skaluje, mocno zniekształcone obrazy źródłowe nadal będą wyglądać źle.
-   **O:** Po zmianie rozmiarów obrazów często dobrym pomysłem jest ponowne wygenerowanie miniatur. Przejdź do **Wygląd > Ustawienia obrazów** (lub **Preferencje > Obrazy** w starszych wersjach PS) i kliknij „Wygeneruj miniatury”. Wybierz „producenci” jako typ obrazu.

**P3: Karuzela nie przewija się lub automatyczne przewijanie nie działa.**

-   **O:** Sprawdź, czy „Włącz karuzelę” jest ustawione na `TAK`. Jeśli nie, będzie to statyczny blok.
-   **O:** Jeśli karuzela jest włączona, sprawdź, czy „Włącz automatyczne przewijanie karuzeli” również jest ustawione na `TAK`. Jeśli jest to `NIE`, karuzela będzie poruszać się tylko ręcznie.
-   **O:** Jeśli oba są włączone, sprawdź konsolę deweloperską przeglądarki (F12) pod kątem błędów JavaScript. Konflikty z innymi modułami lub skryptami szablonu mogą czasami uniemożliwić działanie karuzeli. Spróbuj tymczasowo wyłączyć inne moduły, aby wyizolować problem.

**P4: „Aktywuj filtr kategorii” nie działa; nadal widzę wszystkie marki na stronach kategorii.**

-   **O:** Upewnij się, że to ustawienie jest ustawione na `TAK` w konfiguracji modułu.
-   **O:** Sprawdź, czy Twoje produkty są poprawnie powiązane zarówno z kategorią, jak i producentem w Twoim katalogu PrestaShop. Jeśli produkt nie jest powiązany z producentem lub producent nie jest powiązany z żadnymi produktami w tej kategorii, nie pojawi się po filtrowaniu.
-   **O:** Wyczyść pamięć podręczną PrestaShop po wprowadzeniu jakichkolwiek zmian w powiązaniach produktów/producentów.

**P5: Jak przetłumaczyć tytuł lub tekst modułu?**

-   **O:** Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon i wybierz język, na który chcesz przetłumaczyć.
-   Znajdź moduł „Blok obrazów producentów (marek)” na liście i możesz edytować wszelkie dostępne do tłumaczenia ciągi znaków (np. tytuł bloku).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Blok obrazów producentów (marek)” (`mib`) to standardowy moduł PrestaShop, który wykorzystuje wzorzec zbliżony do MVC. Głównie wykorzystuje system hooków PrestaShop do wstrzykiwania swojej zawartości w różne pozycje front-office. Główna logika znajduje się w głównym pliku `mib.php`, który obsługuje instalację, deinstalację, konfigurację i renderowanie zawartości dla hooków. Wykorzystuje zewnętrzną bibliotekę JavaScript (`lightslider.js`) do funkcjonalności karuzeli oraz niestandardowy CSS do stylizacji. Ustawienia konfiguracyjne są przechowywane w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, a renderowanie front-office odbywa się bezpośrednio za pomocą metod hooków.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani encji `ObjectModel`. Bezpośrednio współdziała z podstawowymi obiektami PrestaShop `Manufacturer` i `Category` oraz `Configuration` dla ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`mib/lib/js/lightslider.js`**
    *   **Zakres:** Front-office.
    *   **Opis:** Jest to zewnętrzna wtyczka jQuery odpowiedzialna za tworzenie responsywnej karuzeli treści. Obsługuje animację przesuwania, kontrolki nawigacji i responsywne zachowanie dla logotypów marek, gdy opcja karuzeli jest włączona.
    *   **Kluczowa funkcjonalność:** Inicjalizuje `lightSlider` na określonym elemencie HTML, zarządza przejściami slajdów, gestami dotyku/przeciągania i responsywnymi dostosowaniami.
-   **`mib/views/js/mib.js`**
    *   **Zakres:** Front-office.
    *   **Opis:** Jest to niestandardowy plik JavaScript modułu. Zawiera logikę inicjalizacji wtyczki `lightslider.js` na podstawie ustawień konfiguracyjnych modułu.
    *   **Kluczowa funkcjonalność:**
        *   Sprawdza, czy karuzela jest włączona (konfiguracja `MIB_CAROUSEL`).
        *   Inicjalizuje `lightSlider` na elemencie `#lightSlider` w szablonie modułu.
        *   Przekazuje opcje konfiguracyjne do `lightSlider`, takie jak `auto`, `pause`, `pauseOnHover`, `item`, `slideMove`, `speed`, `loop`, `controls`, `responsive` na podstawie ustawień `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED` i `MIB_IMG`.
        *   Zapewnia, że suwak jest inicjalizowany tylko wtedy, gdy element istnieje.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`mib/lib/css/lightslider.css`**
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Opis:** Jest to podstawowy arkusz stylów dla wtyczki `lightslider.js`. Zapewnia niezbędną stylizację dla struktury karuzeli, strzałek nawigacyjnych i kropek paginacji.
    *   **Kluczowe selektory CSS:** `.lightSlider`, `.lSAction`, `.lSPager`, `.lslide` itp. Programiści mogą je nadpisać, aby dostosować wygląd karuzeli.
-   **`mib/mib.css`**
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Opis:** Jest to niestandardowy arkusz stylów modułu. Zapewnia specyficzną stylizację dla kontenera bloku marek, pojedynczych obrazów marek i wszelkich efektów najechania kursorem.
    *   **Kluczowe selektory CSS:**
        *   `#manufacturers_block_top`, `#manufacturers_block_left`, `#manufacturers_block_right`, `#manufacturers_block_home`, `#manufacturers_block_footer`: Główne identyfikatory kontenerów dla różnych pozycji hooków.
        *   `.mib_manufacturer_item`: Style dla pojedynczych linków/kontenerów producentów.
        *   `.mib_manufacturer_item img`: Style dla obrazów marek, w tym dostosowania `max-width` i `height`.
        *   `.mib_manufacturer_item:hover img`: Definiuje animację najechania kursorem (np. `transform: scale(1.1)` dla efektu powiększenia).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   **`mib/views/templates/hook/mib.tpl`**
        *   **Podpięty do:** `displayRightColumn`, `displayFooter`, `displayTop`, `displayLeftColumn`, `displayHome`, `displayTopColumn`.
        *   **Cel:** Jest to główny szablon front-office odpowiedzialny za renderowanie bloku marek. Dynamicznie generuje strukturę HTML dla statycznej siatki logotypów producentów lub karuzeli `lightSlider`, w zależności od konfiguracji modułu.
        *   **Kluczowe elementy:**
            *   Warunkowe renderowanie karuzeli (`{if $mib_carousel}`).
            *   Pętla przez tablicę `$manufacturers` w celu wyświetlenia obrazu i linku każdej marki.
            *   Zawiera `mib.js` i `lightslider.js`, jeśli karuzela jest włączona.
            *   Zawiera `mib.css` i `lightslider.css`.
            *   Używa `{$link->getManufacturerLink($manufacturer.id_manufacturer, $manufacturer.link_rewrite)}` dla adresów URL producentów.
            *   Używa `{$manufacturer.image}` dla ścieżek obrazów marek.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   **`mib/views/templates/admin/admin.tpl`**
        *   **Cel:** Ten szablon renderuje formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Wyświetla wszystkie ustawienia (pozycja, opcje karuzeli, rozmiar obrazu itp.) jako pola wejściowe, listy rozwijane i przełączniki.
        *   **Kluczowe elementy:**
            *   Standardowa struktura formularza pomocniczego PrestaShop (`{include file="{$smarty.const._PS_ROOT_DIR_}/src/PrestaShopBundle/Resources/views/Admin/Configure/AdvancedParameters/Blocks/form_block_content.html.twig"}`).
            *   Pola wejściowe dla `MIB_WHERE`, `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`.
            *   Używa `{$mib_form_action}` do przesyłania formularza.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    *   Ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`, `MIB_WHERE`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas i miejsce wykonania | Cel techniczny |
| --- | --- | --- |
| `displayRightColumn` | Renderuje się w prawej kolumnie bocznej front-office. | Wyświetla blok marek w prawej kolumnie. |
| `displayFooter` | Renderuje się w sekcji stopki front-office. | Wyświetla blok marek w stopce sklepu. |
| `displayTop` | Renderuje się w górnej sekcji front-office (często nagłówek). | Wyświetla blok marek w obszarze nagłówka. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Służy do dołączania plików CSS i JS modułu w Panelu administracyjnym do konfiguracji. |
| `displayLeftColumn` | Renderuje się w lewej kolumnie bocznej front-office. | Wyświetla blok marek w lewej kolumnie. |
| `displayHome` | Renderuje się na stronie głównej front-office. | Wyświetla blok marek w widocznym miejscu na stronie głównej. |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Służy do dołączania niezbędnych plików CSS i JS do wyświetlania front-office. |
| `displayTopColumn` | Renderuje się w górnej sekcji kolumny front-office (poniżej `displayTop`). | Wyświetla blok marek w obszarze górnej kolumny. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Blok obrazów producentów (marek)”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
