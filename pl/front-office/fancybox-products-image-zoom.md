---
title: "Fancybox products image zoom - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Fancybox products image zoom od MyPresta.eu."
sidebar:
  label: "Fancybox products image zoom - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Fancybox products image zoom na MyPresta.eu](https://mypresta.eu/modules/front-office-features/fancybox-products-image-zoom.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/fancybox-products-image-zoom/)
>
> ---


# Fancybox products image zoom

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu Fancybox products image zoom. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Fancybox products image zoom” i klikając „Konfiguruj”.

#### Ustawienia obsługi motywu i selektora

Te ustawienia pomagają modułowi zidentyfikować prawidłowe elementy na stronie produktu, aby zastosować powiększenie Fancybox, co jest szczególnie ważne w przypadku niestandardowych motywów.

-   **Obsługa motywu**

    *   **Co robi to ustawienie:** Jest to kluczowe ustawienie, które informuje moduł, jakiej struktury motywu powinien się spodziewać. Pomaga modułowi poprawnie zidentyfikować główne zdjęcie produktu i jego miniatury na stronach produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na „Classic”:* Moduł użyje predefiniowanych selektorów, które doskonale współpracują z domyślnym motywem PrestaShop „Classic”. Jest to najczęstsze i zalecane ustawienie, jeśli używasz motywu Classic lub motywu bardzo ściśle na nim opartego.
        *   *Gdy ustawione na „Hummingbird”:* Moduł użyje predefiniowanych selektorów dla motywu „Hummingbird”, który jest domyślnym motywem dla PrestaShop 8.1 i nowszych.
        *   *Gdy ustawione na „Custom”:* Ta opcja pozwala ręcznie określić selektory CSS dla głównego zdjęcia produktu i miniatur. Jest to niezbędne, jeśli używasz mocno dostosowanego motywu lub motywu innej firmy, który nie jest zgodny ze strukturą „Classic” lub „Hummingbird”.
    *   **Zalecana wartość:** „Classic”, jeśli używasz PrestaShop 1.7.x do 8.0.x z motywem Classic. „Hummingbird”, jeśli używasz PrestaShop 8.1+ z motywem Hummingbird. „Custom”, jeśli masz unikalny motyw.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli zdjęcia produktów nie powiększają się poprawnie po instalacji, a używasz niestandardowego motywu, przełączenie tego na „Custom” i następnie dostosowanie selektorów poniżej jest kolejnym krokiem.
-   **Wykryty profil motywu**

    *   **Co robi to ustawienie:** To pole wyświetla profil motywu, który moduł automatycznie wykrył na podstawie wyboru „Obsługa motywu”. Jest to pole informacyjne, niekonfigurowalne bezpośrednio.
    *   **Efekt zmiany tego ustawienia:** Brak bezpośredniego efektu, ponieważ jest to pole tylko do wyświetlania. Po prostu potwierdza, który zestaw selektorów jest aktualnie używany przez moduł.
    *   **Zalecana wartość:** N/A (informacyjne).
    *   **Scenariusz/przykład dla sprzedawcy:** Ustawiono „Obsługa motywu” na „Classic”, a to pole potwierdza, że wykryto „Classic”.
-   **Selektor okładki Hummingbird** (Widoczne tylko, jeśli „Obsługa motywu” to „Hummingbird”)

    *   **Co robi to ustawienie:** Określa selektor CSS dla głównego kontenera obrazu okładki produktu podczas korzystania z motywu Hummingbird. Pomaga to modułowi wskazać prawidłowy obszar do powiększenia.
    *   **Efekt zmiany tego ustawienia:** Jeśli jest nieprawidłowy, powiększenie Fancybox może nie aktywować się na głównym zdjęciu produktu lub może wskazywać niewłaściwy element.
    *   **Zalecana wartość:** Pozostaw jako domyślne, chyba że Twój motyw oparty na Hummingbird znacząco zmienił swoją strukturę.
    *   **Scenariusz/przykład dla sprzedawcy:** Twój motyw Hummingbird ma unikalną strukturę dla głównego obrazu. Może być konieczne sprawdzenie kodu motywu, aby znaleźć prawidłową klasę CSS lub ID dla głównego kontenera obrazu i wprowadzenie jej tutaj.
-   **Selektor obrazu Hummingbird** (Widoczne tylko, jeśli „Obsługa motywu” to „Hummingbird”)

    *   **Co robi to ustawienie:** Określa selektor CSS dla rzeczywistego tagu `<img>` głównego obrazu okładki produktu w motywie Hummingbird.
    *   **Efekt zmiany tego ustawienia:** Podobnie jak w przypadku selektora okładki, nieprawidłowa wartość uniemożliwi działanie powiększenia na głównym obrazie.
    *   **Zalecana wartość:** Pozostaw jako domyślne.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli powiększenie nie działa na głównym obrazie, a używasz Hummingbird, sprawdź ten selektor.
-   **Selektor miniatur Hummingbird** (Widoczne tylko, jeśli „Obsługa motywu” to „Hummingbird”)

    *   **Co robi to ustawienie:** Określa selektor CSS dla kontenera miniatur produktów podczas korzystania z motywu Hummingbird. Jest to ważne do tworzenia galerii z miniatur.
    *   **Efekt zmiany tego ustawienia:** Jeśli jest nieprawidłowy, moduł może nie być w stanie utworzyć galerii Fancybox z miniatur lub kliknięcie miniatur może nie otwierać Fancybox.
    *   **Zalecana wartość:** Pozostaw jako domyślne.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli kliknięcie miniatur nie otwiera galerii Fancybox, zweryfikuj ten selektor.
-   **Selektor głównego obrazu okładki** (Widoczne tylko, jeśli „Obsługa motywu” to „Custom”)

    *   **Co robi to ustawienie:** Gdy wybrano obsługę motywu „Custom”, to pole pozwala ręcznie wprowadzić selektor CSS dla elementu kontenera, który zawiera główne zdjęcie produktu na stronie produktu.
    *   **Efekt zmiany tego ustawienia:** Jeśli ten selektor jest nieprawidłowy, powiększenie Fancybox nie aktywuje się na głównym zdjęciu produktu.
    *   **Zalecana wartość:** Będziesz musiał użyć narzędzi deweloperskich przeglądarki (F12), aby zbadać stronę produktu i znaleźć unikalną klasę CSS lub ID elementu `<div>` lub innego elementu kontenera, który otacza główne zdjęcie produktu.
    *   **Scenariusz/przykład dla sprzedawcy:** Twój niestandardowy motyw używa `<div id="my-custom-main-image-wrapper">` dla głównego obrazu. Wprowadź tutaj `#my-custom-main-image-wrapper`.
-   **Główne zdjęcie okładki** (Widoczne tylko, jeśli „Obsługa motywu” to „Custom”)

    *   **Co robi to ustawienie:** Gdy wybrano obsługę motywu „Custom”, to pole pozwala ręcznie wprowadzić selektor CSS dla rzeczywistego tagu `<img>` głównego zdjęcia produktu.
    *   **Efekt zmiany tego ustawienia:** Jeśli ten selektor jest nieprawidłowy, powiększenie Fancybox nie aktywuje się na głównym zdjęciu produktu.
    *   **Zalecana wartość:** Użyj narzędzi deweloperskich przeglądarki, aby znaleźć unikalną klasę CSS lub ID samego tagu `<img>`.
    *   **Scenariusz/przykład dla sprzedawcy:** Twój niestandardowy motyw używa `<img class="product-main-image-src">` dla głównego obrazu. Wprowadź tutaj `.product-main-image-src`.
-   **Selektor miniatur zdjęć** (Widoczne tylko, jeśli „Obsługa motywu” to „Custom”)

    *   **Co robi to ustawienie:** Gdy wybrano obsługę motywu „Custom”, to pole pozwala ręcznie wprowadzić selektor CSS dla elementu kontenera, który zawiera miniatury produktów.
    *   **Efekt zmiany tego ustawienia:** Jeśli ten selektor jest nieprawidłowy, moduł nie będzie w stanie utworzyć galerii Fancybox z miniatur lub kliknięcie miniatur może nie otwierać Fancybox.
    *   **Zalecana wartość:** Użyj narzędzi deweloperskich przeglądarki, aby znaleźć unikalną klasę CSS lub ID elementu `<div>` lub innego elementu kontenera, który otacza miniatury produktów.
    *   **Scenariusz/przykład dla sprzedawcy:** Twój niestandardowy motyw używa `<ul id="product-thumbnails-list">` dla miniatur. Wprowadź tutaj `#product-thumbnails-list`.

#### Ustawienia zachowania Fancybox

Te ustawienia kontrolują, jak powiększenie Fancybox zachowuje się i wchodzi w interakcje z Twoimi klientami.

-   **Utwórz galerię**

    *   **Co robi to ustawienie:** Określa, czy wszystkie zdjęcia produktów (główne zdjęcie i miniatury) są grupowane w jedną galerię Fancybox. Gdy jest włączone, kliknięcie dowolnego zdjęcia otworzy Fancybox, a klienci mogą następnie nawigować po wszystkich zdjęciach produktów za pomocą strzałek.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („On”):* Klienci mogą przeglądać wszystkie zdjęcia produktów w pełnoekranowej nakładce Fancybox, używając strzałek nawigacyjnych. Zapewnia to kompleksowy widok produktu.
        *   *Gdy wyłączone („Off”):* Kliknięcie zdjęcia otworzy tylko to konkretne zdjęcie w Fancybox. Klienci nie mogą nawigować do innych zdjęć produktów z widoku Fancybox.
    *   **Zalecana wartość:** „On” dla lepszego doświadczenia użytkownika i zachęcenia klientów do przeglądania produktu pod różnymi kątami.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby klienci mogli łatwo przeglądać wszystkie zdjęcia produktów bez zamykania i ponownego otwierania powiększenia dla każdego z nich. Włącz to.
-   **Przesuń**

    *   **Co robi to ustawienie:** Włącza lub wyłącza gesty przesuwania do nawigacji po galerii Fancybox na urządzeniach z ekranem dotykowym (smartfony, tablety).
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („On”):* Klienci mogą przesuwać palcem w lewo lub w prawo na swoich urządzeniach dotykowych, aby przechodzić między obrazami w galerii Fancybox.
        *   *Gdy wyłączone („Off”):* Gesty przesuwania nie będą działać. Klienci będą musieli używać strzałek nawigacyjnych (jeśli „Utwórz galerię” jest włączone).
    *   **Zalecana wartość:** „On” dla nowoczesnego, intuicyjnego doświadczenia mobilnego.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby Twoi użytkownicy mobilni mieli płynny, naturalny sposób przeglądania zdjęć produktów. Pozostaw to włączone.
-   **Unikaj podwójnego obrazu okładki w galerii**

    *   **Co robi to ustawienie:** Gdy „Utwórz galerię” jest włączone, czasami główne zdjęcie produktu może pojawić się dwukrotnie w galerii (raz jako główne zdjęcie, a ponownie, jeśli jest również wymienione jako miniatura). To ustawienie zapobiega tej duplikacji.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („On”):* Moduł spróbuje wykryć i usunąć wszelkie zduplikowane główne zdjęcie produktu z galerii Fancybox, zapewniając, że każde zdjęcie pojawi się tylko raz.
        *   *Gdy wyłączone („Off”):* Jeśli główne zdjęcie produktu jest również częścią listy miniatur, może pojawić się dwukrotnie w galerii Fancybox.
    *   **Zalecana wartość:** „On” dla czystszego, bardziej profesjonalnego doświadczenia galerii.
    *   **Scenariusz/przykład dla sprzedawcy:** Zauważasz, że gdy klienci otwierają galerię Fancybox, pierwsze zdjęcie jest identyczne z drugim. Włączenie tego naprawi to.
-   **Wyświetlaj podpisy (tytuły obrazów)**

    *   **Co robi to ustawienie:** Kontroluje, czy tytuł/podpis powiązany z każdym zdjęciem produktu jest wyświetlany w nakładce Fancybox. Te tytuły są zazwyczaj ustawiane w zarządzaniu zdjęciami produktów w PrestaShop.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („On”):* Tytuł obrazu pojawi się jako podpis poniżej lub powyżej obrazu w nakładce Fancybox.
        *   *Gdy wyłączone („Off”):* Nie zostanie wyświetlony żaden podpis, zapewniając czystszy widok tylko obrazu.
    *   **Zalecana wartość:** „On”, jeśli tytuły Twoich obrazów dostarczają użytecznych informacji (np. „Widok z przodu”, „Szczegół tkaniny”, „Model noszący produkt”). „Off”, jeśli tytuły Twoich obrazów są ogólne lub wolisz minimalistyczny wygląd.
    *   **Scenariusz/przykład dla sprzedawcy:** Używasz opisowych tytułów dla swoich zdjęć produktów i chcesz, aby klienci je widzieli podczas powiększania. Włącz to.
-   **Zmień główne zdjęcie po najechaniu myszą na miniaturę**

    *   **Co robi to ustawienie:** Określa, czy najechanie myszą na miniaturę produktu automatycznie zmienia główne zdjęcie produktu wyświetlane na stronie produktu, *przed* kliknięciem, aby otworzyć Fancybox.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („On”):* Przesunięcie kursora myszy nad miniaturę natychmiast zamieni główne zdjęcie produktu na wyświetlaną miniaturę. Jest to powszechna i wygodna funkcja dla kupujących.
        *   *Gdy wyłączone („Off”):* Główne zdjęcie produktu zmieni się tylko po kliknięciu miniatury, a nie tylko po najechaniu kursorem.
    *   **Zalecana wartość:** „On” dla bardziej interaktywnego i przyjaznego dla użytkownika doświadczenia przeglądania.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby klienci szybko podglądali różne zdjęcia produktów, po prostu przesuwając mysz, bez konieczności klikania. Włącz to.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Obsługa motywu** | Classic / Hummingbird | Wybiera predefiniowane selektory CSS dla Twojego motywu (Classic, Hummingbird lub Custom). Kluczowe dla funkcjonalności modułu. |
| Konfiguracja modułu | **Wykryty profil motywu** | N/A (Informacyjne) | Pokazuje, który profil motywu jest aktualnie aktywny. |
| Konfiguracja modułu | **Selektor okładki Hummingbird** | Domyślne | Selektor CSS dla głównego kontenera obrazu (motyw Hummingbird). |
| Konfiguracja modułu | **Selektor obrazu Hummingbird** | Domyślne | Selektor CSS dla głównego tagu `<img>` (motyw Hummingbird). |
| Konfiguracja modułu | **Selektor miniatur Hummingbird** | Domyślne | Selektor CSS dla kontenera miniatur (motyw Hummingbird). |
| Konfiguracja modułu | **Selektor głównego obrazu okładki** | Niestandardowy (Sprawdź motyw) | Selektor CSS dla głównego kontenera obrazu (motyw niestandardowy). |
| Konfiguracja modułu | **Główne zdjęcie okładki** | Niestandardowy (Sprawdź motyw) | Selektor CSS dla głównego tagu `<img>` (motyw niestandardowy). |
| Konfiguracja modułu | **Selektor miniatur zdjęć** | Niestandardowy (Sprawdź motyw) | Selektor CSS dla kontenera miniatur (motyw niestandardowy). |
| Konfiguracja modułu | **Utwórz galerię** | Włączone | Grupuje wszystkie zdjęcia produktów w przeglądalną galerię Fancybox. |
| Konfiguracja modułu | **Przesuń** | Włączone | Włącza gesty przesuwania do nawigacji po galerii na urządzeniach dotykowych. |
| Konfiguracja modułu | **Unikaj podwójnego obrazu okładki w galerii** | Włączone | Zapobiega podwójnemu wyświetlaniu głównego obrazu w galerii. |
| Konfiguracja modułu | **Wyświetlaj podpisy (tytuły obrazów)** | Włączone / Wyłączone (Preferencje sprzedawcy) | Pokazuje tytuły obrazów jako podpisy w nakładce Fancybox. |
| Konfiguracja modułu | **Zmień główne zdjęcie po najechaniu myszą na miniaturę** | Włączone | Zmienia główne zdjęcie produktu po najechaniu myszą na miniaturę. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Powiększenie Fancybox w ogóle nie pojawia się na moich stronach produktów.**
O:

1.  **Sprawdź status modułu:** Upewnij się, że moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
2.  **Ustawienie obsługi motywu:** Przejdź do strony konfiguracji modułu. Jeśli używasz motywu „Classic”, upewnij się, że „Obsługa motywu” jest ustawiona na „Classic”. Jeśli używasz PrestaShop 8.1+ z motywem Hummingbird, ustaw ją na „Hummingbird”. Jeśli masz niestandardowy motyw, ustaw ją na „Custom” i dokładnie sprawdź wprowadzone selektory CSS (patrz następny punkt).
3.  **Niestandardowe selektory motywu:** Jeśli „Obsługa motywu” to „Custom”, najczęstszym problemem są nieprawidłowe selektory CSS. Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać stronę produktu. Znajdź dokładne klasy CSS lub identyfikatory dla kontenera głównego zdjęcia produktu, tagu `<img>` i kontenera miniatur. Zaktualizuj je w ustawieniach modułu.

**P: Fancybox otwiera się, ale pokazuje niewłaściwy obraz lub tylko jeden obraz.**
O:

1.  **Ustawienie „Utwórz galerię”:** Upewnij się, że „Utwórz galerię” jest ustawione na „On” w konfiguracji modułu, jeśli chcesz przeglądać wiele obrazów.
2.  **Selektory miniatur:** Jeśli „Utwórz galerię” jest włączone, ale pojawia się tylko jeden obraz, sprawdź swój „Selektor miniatur zdjęć” (zwłaszcza jeśli „Obsługa motywu” to „Custom”). Moduł musi poprawnie zidentyfikować wszystkie Twoje miniatury, aby zbudować galerię.
3.  **Tytuły/podpisy obrazów:** Jeśli podpisy nie są wyświetlane, upewnij się, że „Wyświetlaj podpisy (tytuły obrazów)” jest ustawione na „On” i że Twoje zdjęcia produktów faktycznie mają zdefiniowane tytuły w panelu administracyjnym PrestaShop.

**P: Gesty przesuwania nie działają na moim urządzeniu mobilnym.**
O:

1.  **Ustawienie „Przesuń”:** Upewnij się, że opcja „Przesuń” jest ustawiona na „On” w konfiguracji modułu.
2.  **Galeria włączona:** Przesuwanie działa tylko wtedy, gdy „Utwórz galerię” jest również ustawione na „On”, ponieważ służy do nawigacji między wieloma obrazami.
3.  **Kompatybilność przeglądarki/urządzenia:** Chociaż szeroko obsługiwane, bardzo stare przeglądarki lub specyficzne konfiguracje urządzeń mogą mieć problemy. Przetestuj na nowoczesnej przeglądarce mobilnej.

**P: Układ mojej strony produktu wygląda trochę dziwnie po zainstalowaniu modułu.**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami stare pliki pamięci podręcznej mogą kolidować z nowym stylem modułu.
2.  **Konflikty motywów:** Chociaż moduł stara się być kompatybilny, bardzo specyficzny CSS niestandardowego motywu może powodować konflikty. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, tymczasowo wyłącz moduł, aby sprawdzić, czy problem zniknie. Jeśli tak, może być konieczne, aby programista internetowy dostosował CSS Twojego motywu lub niestandardowe selektory modułu.

**P: Jak znaleźć prawidłowe selektory CSS dla mojego niestandardowego motywu?**
O:

1.  Otwórz stronę produktu w przeglądarce internetowej (Chrome, Firefox, Edge).
2.  Kliknij prawym przyciskiem myszy na głównym zdjęciu produktu i wybierz „Zbadaj” lub „Zbadaj element”.
3.  Spowoduje to otwarcie narzędzi deweloperskich przeglądarki. Poszukaj tagu `<img>` głównego obrazu i jego nadrzędnego `<div>` lub innego kontenera. Zapisz wszelkie unikalne atrybuty `id` (np. `id="my-image"`) lub atrybuty `class` (np. `class="product-image-wrapper"`).
4.  Powtórz to dla miniatur produktów.
5.  Użyj tych identyfikatorów (poprzedzonych `#`, np. `#my-image`) lub klas (poprzedzonych `.`, np. `.product-image-wrapper`) w ustawieniach motywu „Custom” modułu. Może być konieczne trochę eksperymentowania, aby znaleźć najbardziej specyficzne i niezawodne selektory.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `fancyzoom` to lekki moduł PrestaShop, zaprojektowany przede wszystkim do zastąpienia domyślnej funkcji powiększania obrazów produktów za pomocą Fancybox. Osiąga to poprzez podłączenie się do `displayHeader` w celu wstrzyknięcia niestandardowego kodu JavaScript i CSS, a także poprzez użycie JavaScript do identyfikacji i ponownej inicjalizacji elementów obrazu za pomocą Fancybox. Konfiguracja modułu jest obsługiwana za pomocą standardowej metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`. Moduł nie wprowadza niestandardowych tabel baz danych, klas `ObjectModel` ani dedykowanych kontrolerów front-office/admin, poza główną konfiguracją modułu.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Cała funkcjonalność front-office jest wstrzykiwana za pomocą hooków i obsługiwana przez JavaScript.
-   **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja back-office jest obsługiwana przez metodę `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   W katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Cała podstawowa logika znajduje się w głównym pliku modułu `fancyzoom.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera dwa pliki JavaScript, głównie dla funkcjonalności front-office. Są one rejestrowane za pomocą hooka `displayHeader`.

-   `fancyzoom/views/templates/js/fancyzoom.js`

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Jest to główny skrypt, który inicjalizuje Fancybox. Dynamicznie identyfikuje główne zdjęcie produktu i miniatury na podstawie skonfigurowanych selektorów CSS (lub domyślnych selektorów Classic/Hummingbird). Następnie wiąże zdarzenia kliknięcia z tymi obrazami, aby otwierać je w galerii Fancybox. Obsługuje również funkcjonalność „zmień główne zdjęcie po najechaniu myszą na miniaturę”. Jest odpowiedzialny za wyłączanie domyślnego powiększenia PrestaShop.
    *   **Kluczowe funkcjonalności:**
        *   Wyłącza domyślne powiększenie obrazu PrestaShop.
        *   Wykrywa profil motywu (Classic, Hummingbird, Custom) i stosuje odpowiednie selektory.
        *   Inicjalizuje Fancybox na zdjęciach produktów.
        *   Zarządza tworzeniem galerii Fancybox i opcjami (przesuwanie, podpisy, podwójne obrazy).
        *   Obsługuje efekt najechania myszą na miniaturę, aby zmienić główny obraz.
        *   Nasłuchuje zdarzenia `updateProduct` (aktualizacje strony produktu PrestaShop 1.7+) w celu ponownej inicjalizacji Fancybox.
-   `fancyzoom/views/templates/js/touchswipe.js`

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Jest to biblioteka zewnętrzna, która zapewnia solidne wykrywanie zdarzeń przesuwania dotykowego. Jest używana przez `fancyzoom.js` do włączania nawigacji przesuwania w galerii Fancybox na urządzeniach dotykowych.
    *   **Kluczowe funkcjonalności:** Zapewnia wtyczkę jQuery do wykrywania gestów przesuwania (w lewo, w prawo, w górę, w dół) i innych zdarzeń dotykowych.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera jeden plik CSS do stylizacji front-office.

-   `fancyzoom/views/templates/css/fancyzoom.css`
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Odpowiedzialność:** Zawiera niezbędny CSS dla samej nakładki Fancybox, w tym stylizację strzałek nawigacyjnych, przycisku zamykania, podpisów i ogólnego wyglądu. Zapewnia, że modal Fancybox jest prawidłowo pozycjonowany i stylizowany.
    *   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:**
        *   `.fancybox-container`: Główny kontener dla nakładki Fancybox.
        *   `.fancybox-bg`: Tło nakładki.
        *   `.fancybox-toolbar`: Pasek narzędzi z przyciskiem zamykania itp.
        *   `.fancybox-caption`: Obszar podpisu.
        *   `.fancybox-button`: Przyciski (zamknij, nawigacja).
        *   `.fancybox-image`: Sam obraz w Fancybox.
          Programiści mogą nadpisać te klasy w pliku `custom.css` swojego motywu lub podobnym pliku, aby dopasować je do brandingu swojego sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    *   `fancyzoom/views/templates/hook/fancyzoom.tpl`
        *   **Hook:** `displayHeader`
        *   **Cel:** Ten szablon jest odpowiedzialny za wstrzykiwanie niezbędnych zmiennych JavaScript oraz plików JS i CSS modułu do sekcji `<head>` front-office. Przekazuje zmienne konfiguracyjne z panelu administracyjnego (takie jak selektory, opcje galerii) do skryptu `fancyzoom.js`.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    *   `fancyzoom/views/templates/admin/admin.tpl`
        *   **Cel:** Ten szablon renderuje formularz konfiguracji modułu w panelu administracyjnym PrestaShop. Wyświetla wszystkie ustawienia opisane w Sekcji 4.1, w tym pola wprowadzania selektorów, pola wyboru dla opcji galerii i wykrywanie profilu motywu.
-   **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel baz danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `FZ_` (np. `FZ_THEME`, `FZ_COVER_DIV`, `FZ_GALLERY`).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS i JavaScript modułu oraz przekazuje zmienne konfiguracyjne do skryptów front-endowych. To tutaj ładowana jest biblioteka Fancybox i jej logika inicjalizacji. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Fancybox products image zoom”, prosimy zalogować się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
