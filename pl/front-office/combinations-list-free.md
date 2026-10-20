---
title: "Combinations List Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop Combinations List Free od MyPresta.eu."
sidebar:
  label: "Combinations List Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Combinations List Free na MyPresta.eu](https://mypresta.eu/modules/front-office-features/combinations-list-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/combinations-list-free/)
>
> ---


# Combinations List Free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop, ale ten moduł nie ma żadnych specyficznych egzotycznych wymagań poza standardowym środowiskiem PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Combinations List Free” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ta sekcja kontroluje ogólne zachowanie i wygląd listy kombinacji na stronach produktów.

    -   **Wyświetl listę kombinacji na stronie produktu:**

        -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania funkcjonalności modułu.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Moduł spróbuje wyświetlić listę kombinacji na stronach produktów zgodnie z innymi ustawieniami.
            -   *Gdy wyłączone (NIE):* Moduł będzie nieaktywny, a strony produktów powrócą do domyślnych selektorów kombinacji PrestaShop (rozwijane listy).
        -   **Zalecana wartość:** TAK (aby używać modułu).
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz go wyłączyć bez odinstalowywania, ustaw to na NIE.
    -   **Hook do wyświetlania listy kombinacji:**

        -   **Co robi to ustawienie:** Określa, gdzie na stronie produktu pojawi się lista kombinacji. Jest to kluczowe dla wizualnej integracji listy z Twoim szablonem.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy ustawione na `displayProductButtons` (lub podobny hook związany z produktem):* Lista zazwyczaj pojawi się w pobliżu przycisku „Dodaj do koszyka” lub ceny produktu, często poniżej głównych szczegółów produktu.
            -   *Gdy ustawione na `displayProductExtraContent` (lub podobny hook związany z zakładkami):* Lista pojawi się w nowej lub istniejącej zakładce produktu, utrzymując główny obszar opisu produktu w czystości.
            -   *Gdy ustawione na `displayFooterProduct` (lub podobny hook stopki):* Lista pojawi się na samym dole strony produktu.
        -   **Zalecana wartość:** Eksperymentuj z różnymi hookami, aby znaleźć najlepszą wizualną integrację z Twoim konkretnym szablonem. `displayProductButtons` lub `displayProductExtraContent` to popularne wybory.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja strona produktu jest już długa, umieszczenie listy w zakładce `displayProductExtraContent` może sprawić, że strona będzie mniej zagracona. Jeśli chcesz, aby lista była natychmiast widoczna, lepszy jest hook taki jak `displayProductButtons`.
    -   **Pokaż obraz kombinacji:**

        -   **Co robi to ustawienie:** Kontroluje, czy mały obraz specyficzny dla każdej kombinacji jest wyświetlany na liście.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Jeśli przesłałeś konkretne obrazy dla każdej kombinacji produktu, pojawią się one obok odpowiedniej kombinacji na liście.
            -   *Gdy wyłączone (NIE):* Wyświetlana będzie tylko nazwa kombinacji, referencja i cena, bez obrazu.
        -   **Zalecana wartość:** TAK, jeśli masz unikalne obrazy dla kombinacji. To znacznie pomaga klientom wizualizować dokładnie ten produkt, który wybierają.
        -   **Scenariusz / przykład dla sprzedawcy:** W przypadku odzieży, pokazanie obrazu czerwonej koszulki dla kombinacji „Czerwony - Duży” jest znacznie jaśniejsze niż tylko tekst.
    -   **Pokaż referencję kombinacji:**

        -   **Co robi to ustawienie:** Określa, czy wewnętrzny numer referencyjny dla każdej kombinacji jest wyświetlany.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Referencja kombinacji (np. SKU) będzie widoczna na liście.
            -   *Gdy wyłączone (NIE):* Numer referencyjny zostanie ukryty.
        -   **Zalecana wartość:** TAK, zwłaszcza dla sklepów B2B lub produktów, gdzie klienci często zamawiają według referencji.
        -   **Scenariusz / przykład dla sprzedawcy:** Klient ponownie zamawiający konkretną część może znać ją po numerze referencyjnym, co ułatwia jej znalezienie.
    -   **Pokaż pole ilości kombinacji:**

        -   **Co robi to ustawienie:** Pozwala klientom określić ilość dla każdej kombinacji bezpośrednio na liście, zamiast dodawać po jednej sztuce na raz.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Pole do wprowadzania ilości (np. pole numeryczne) pojawi się obok każdej kombinacji, umożliwiając klientom wprowadzenie żądanej ilości przed kliknięciem „Dodaj do koszyka”.
            -   *Gdy wyłączone (NIE):* Przycisk „Dodaj do koszyka” zazwyczaj doda jedną jednostkę kombinacji do koszyka.
        -   **Zalecana wartość:** TAK, dla większości sklepów, ponieważ poprawia to efektywność dla klientów kupujących wiele jednostek tej samej kombinacji.
        -   **Scenariusz / przykład dla sprzedawcy:** Klient kupujący 5 sztuk „Niebieski - Średni” i 3 sztuki „Zielony - Duży” może to zrobić szybko z listy.
    -   **Pokaż cenę kombinacji:**

        -   **Co robi to ustawienie:** Kontroluje, czy cena każdej indywidualnej kombinacji jest wyświetlana na liście.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Cena dla każdej konkretnej kombinacji zostanie pokazana.
            -   *Gdy wyłączone (NIE):* Cena zostanie ukryta, a klienci mogą widzieć tylko główną cenę produktu lub muszą ją wywnioskować.
        -   **Zalecana wartość:** TAK. Przejrzystość cen jest kluczowa dla zaufania klienta i podejmowania decyzji.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli różne rozmiary lub kolory mają różne ceny, pokazanie dokładnej ceny dla każdej kombinacji jest niezbędne.
    -   **Pokaż dostępność kombinacji:**

        -   **Co robi to ustawienie:** Wyświetla status magazynowy (np. „Dostępny,” „Brak w magazynie,” „Ostatnie sztuki!”) dla każdej kombinacji.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Klienci zobaczą status dostępności dla każdej kombinacji, co pomoże im podjąć świadome decyzje zakupowe.
            -   *Gdy wyłączone (NIE):* Status magazynowy nie będzie wyświetlany na liście.
        -   **Zalecana wartość:** TAK. Zapobiega to dodawaniu przez klientów niedostępnych produktów do koszyka, zmniejszając frustrację i porzucone koszyki.
        -   **Scenariusz / przykład dla sprzedawcy:** Klient może natychmiast zobaczyć, że koszulka „Czerwony - Duży” jest niedostępna i zamiast niej wybrać „Niebieski - Duży”.
    -   **Pokaż opis kombinacji:**

        -   **Co robi to ustawienie:** Jeśli masz specyficzne opisy dla każdej kombinacji, to ustawienie kontroluje ich wyświetlanie.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Każdy unikalny opis związany z kombinacją zostanie wyświetlony na liście.
            -   *Gdy wyłączone (NIE):* Opisy specyficzne dla kombinacji zostaną ukryte.
        -   **Zalecana wartość:** TAK, jeśli Twoje kombinacje mają odrębne opisy, które dodają wartości do decyzji klienta.
        -   **Scenariusz / przykład dla sprzedawcy:** W przypadku produktu konfigurowalnego, opis kombinacji może szczegółowo opisywać konkretne materiały użyte dla tego wariantu.
    -   **Tekst przycisku „Dodaj do koszyka”:**

        -   **Co robi to ustawienie:** Pozwala dostosować tekst wyświetlany na przycisku „Dodaj do koszyka” dla każdej kombinacji.
        -   **Efekt zmiany tego ustawienia:**
            -   *Po zmianie:* Tekst przycisku zostanie zaktualizowany do Twojej niestandardowej frazy.
            -   *Gdy pozostawione puste:* Zostanie użyty domyślny tekst „Dodaj do koszyka” (lub domyślny tekst Twojego szablonu).
        -   **Zalecana wartość:** „Dodaj do koszyka” lub „Kup teraz” dla jasności. Zachowaj zwięzłość.
        -   **Scenariusz / przykład dla sprzedawcy:** Możesz zmienić go na „Wybierz i kup”, jeśli chcesz podkreślić wybór przed zakupem.
    -   **Wyświetl kombinacje jako tabelę:**

        -   **Co robi to ustawienie:** Zmienia wizualną prezentację kombinacji z prostej listy na ustrukturyzowaną tabelę HTML.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Kombinacje zostaną przedstawione w formacie tabeli z kolumnami na obraz, nazwę, referencję, cenę, ilość i dodaj do koszyka. Jest to często bardziej kompaktowe i zorganizowane dla wielu kombinacji.
            -   *Gdy wyłączone (NIE):* Kombinacje zostaną wyświetlone jako mniej ustrukturyzowana lista, zazwyczaj jedna kombinacja na linię.
        -   **Zalecana wartość:** TAK, w większości przypadków, ponieważ tabela zapewnia lepszą czytelność i wyrównanie, zwłaszcza przy wielu opcjach.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz ponad 20 kombinacji, tabela znacznie ułatwia skanowanie i porównywanie.
    -   **Wyświetl kombinacje jako zakładkę:**

        -   **Co robi to ustawienie:** To ustawienie jest prawdopodobnie starszą funkcją lub szczegółem implementacji. Biorąc pod uwagę ustawienie `Hook do wyświetlania listy kombinacji`, może być ono zbędne lub odnosić się do konkretnego szablonu.
        -   **Efekt zmiany tego ustawienia:**
            -   *Gdy włączone (TAK):* Może wymusić wyświetlanie listy kombinacji w strukturze przypominającej zakładkę, potencjalnie nadpisując wybrany hook, jeśli ten hook naturalnie nie tworzy zakładki.
            -   *Gdy wyłączone (NIE):* Wyświetlanie będzie bardziej bezpośrednio zgodne z wybranym hookiem.
        -   **Zalecana wartość:** Generalnie NIE, chyba że wyraźnie chcesz zakładki, a wybrany hook jej nie zapewnia. Polegaj na ustawieniu „Hook do wyświetlania listy kombinacji” dla umiejscowienia.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój szablon nie tworzy automatycznie zakładek dla `displayProductExtraContent`, włączenie tego może wymusić wygląd przypominający zakładkę.

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl listę kombinacji na stronie produktu | TAK | Główny przełącznik do włączania/wyłączania wyświetlania modułu w front-office. |
| Konfiguracja modułu | Hook do wyświetlania listy kombinacji | `displayProductButtons` lub `displayProductExtraContent` | Określa dokładną pozycję listy na stronie produktu. |
| Konfiguracja modułu | Pokaż obraz kombinacji | TAK (jeśli istnieją obrazy) | Wyświetla unikalne obrazy dla każdej kombinacji. |
| Konfiguracja modułu | Pokaż referencję kombinacji | TAK | Pokazuje numer SKU/referencyjny dla każdej kombinacji. |
| Konfiguracja modułu | Pokaż pole ilości kombinacji | TAK | Pozwala klientom wprowadzać ilości dla każdej kombinacji. |
| Konfiguracja modułu | Pokaż cenę kombinacji | TAK | Wyświetla konkretną cenę dla każdej kombinacji. |
| Konfiguracja modułu | Pokaż dostępność kombinacji | TAK | Pokazuje status magazynowy (np. „Dostępny”) dla każdej kombinacji. |
| Konfiguracja modułu | Pokaż opis kombinacji | TAK (jeśli istnieją opisy) | Wyświetla unikalne opisy dla każdej kombinacji. |
| Konfiguracja modułu | Tekst przycisku „Dodaj do koszyka” | „Dodaj do koszyka” | Dostosowuje tekst na przyciskach „Dodaj do koszyka”. |
| Konfiguracja modułu | Wyświetl kombinacje jako tabelę | TAK | Prezentuje kombinacje w ustrukturyzowanej formie tabeli dla lepszej czytelności. |
| Konfiguracja modułu | Wyświetl kombinacje jako zakładkę | NIE | (Prawdopodobnie starsze/specyficzne) Kontroluje wyświetlanie w formie zakładki; preferuj ustawienie hooka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Lista kombinacji nie wyświetla się na mojej stronie produktu.**
**O1:**

-   Najpierw sprawdź, czy „Wyświetl listę kombinacji na stronie produktu” jest ustawione na TAK w konfiguracji modułu.
-   Następnie zweryfikuj ustawienie „Hook do wyświetlania listy kombinacji”. Niektóre szablony mogą nie renderować wszystkich standardowych hooków PrestaShop w ten sam sposób. Spróbuj przełączyć na inny hook (np. `displayProductButtons`, `displayProductExtraContent`, `displayFooterProduct`), aby sprawdzić, czy się pojawi.
-   Upewnij się, że przeglądany produkt faktycznie ma zdefiniowane kombinacje.
-   Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P2: Moje obrazy kombinacji nie pojawiają się na liście.**
**O2:**

-   Upewnij się, że „Pokaż obraz kombinacji” jest włączone w ustawieniach modułu.
-   Co najważniejsze, musisz przesłać konkretne obrazy dla każdej kombinacji w edytorze produktów PrestaShop (Produkt > zakładka Kombinacje > Edytuj każdą kombinację > Dodaj obraz). Jeśli do kombinacji nie jest przypisany żaden konkretny obraz, nie pojawi się on.

**P3: Lista wygląda niechlujnie lub nie pasuje do projektu mojego szablonu.**
**O3:**

-   Spróbuj włączyć „Wyświetl kombinacje jako tabelę”, jeśli jeszcze tego nie zrobiłeś. Często zapewnia to bardziej ustrukturyzowany i atrakcyjny wizualnie układ.
-   Moduł używa własnego CSS. CSS Twojego szablonu może go nadpisywać lub z nim kolidować. Może być konieczne, aby programista internetowy dostosował CSS modułu (`mycombtabfree.css`) lub dodał niestandardowy CSS do Twojego szablonu, aby dostosować go do Twoich upodobań.
-   Eksperymentuj z różnymi hookami. Niektóre hooki mogą mieć lepsze domyślne style z Twojego szablonu.

**P4: Czy mogę przetłumaczyć tekst przycisku „Dodaj do koszyka” na inne języki?**
**O4:** Tak. Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz „Combinations List Free” z rozwijanej listy modułów. Możesz wtedy przetłumaczyć tekst przycisku i wszelkie inne frazy specyficzne dla modułu.

**P5: Dlaczego niektóre kombinacje pokazują „Brak w magazynie”, mimo że mam zapasy?**
**O5:**

-   Sprawdź ustawienia magazynowe produktu w edytorze produktów PrestaShop. Upewnij się, że konkretna kombinacja ma dostępną ilość.
-   Zweryfikuj globalne ustawienia zarządzania zapasami (Parametry sklepu > Ustawienia produktów > Zapasy produktów).
-   Wyczyść pamięć podręczną PrestaShop po dokonaniu jakichkolwiek korekt zapasów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Combinations List Free” (`mycombtabfree`) to standardowy moduł PrestaShop zaprojektowany w celu ulepszenia strony produktu w front-office. Działa głównie poprzez podłączanie się do różnych punktów wyświetlania na stronie produktu w celu wstrzyknięcia niestandardowej struktury HTML dla kombinacji produktów. Moduł stosuje podstawowy wzorzec podobny do MVC w ramach struktury modułów PrestaShop, używając głównej klasy modułu do konfiguracji i rejestracji hooków oraz szablonów Smarty do renderowania danych wyjściowych w front-office. Wykorzystuje istniejące podstawowe funkcjonalności PrestaShop do pobierania danych o produktach i kombinacjach.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu, a renderowanie w front-office odbywa się bezpośrednio za pośrednictwem hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie zawiera żadnych niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Opiera się całkowicie na podstawowych klasach PrestaShop `Product` i `Combination` do pobierania i wyświetlania danych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`mycombtabfree/js/atc.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten skrypt jest odpowiedzialny za obsługę funkcjonalności „Dodaj do koszyka” dla kombinacji wyświetlanych przez moduł. Prawdopodobnie przechwytuje zdarzenia kliknięcia na niestandardowych przyciskach „Dodaj do koszyka” generowanych przez moduł.
    -   **Funkcjonalność:**
        -   Wiąże słuchaczy zdarzeń z przyciskami „Dodaj do koszyka” w liście/tabeli kombinacji.
        -   Po kliknięciu przycisku zbiera `id_product`, `id_product_attribute` (ID kombinacji) i potencjalnie ilość z powiązanego pola wejściowego.
        -   Następnie wykonuje żądanie AJAX do podstawowego kontrolera `cart` PrestaShop (lub podobnego punktu końcowego), aby dodać wybraną kombinację do koszyka.
        -   Może również aktualizować blok koszyka, wyświetlać powiadomienia (sukces/błąd) lub obsługiwać inne informacje zwrotne interfejsu użytkownika po wywołaniu AJAX.
        -   Prawdopodobnie używa jQuery lub natywnych zdarzeń `prestashop.on` PrestaShop do dynamicznych aktualizacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`mycombtabfree/css/admin.css`**

    -   **Zakres:** Stylizacja formularza administracyjnego w back-office.
    -   **Cel:** Zawiera style specyficzne dla strony konfiguracji modułu w Panelu administracyjnym PrestaShop. Może to obejmować stylizację elementów formularza, alertów lub dostosowania układu, aby interfejs konfiguracji był przyjazny dla użytkownika.
    -   **Kluczowe selektory:** Prawdopodobnie celuje w elementy w ramach danych wyjściowych `getContent()` modułu, takie jak `.panel`, `.form-group`, `.alert` itp., aby zapewnić spójny interfejs użytkownika administratora.
-   **`mycombtabfree/css/mycombtabfree.css`**

    -   **Zakres:** Stylizacja dla klientów w front-office.
    -   **Cel:** Zapewnia podstawową stylizację wizualną dla listy/tabeli kombinacji wyświetlanej na stronie produktu w front-office. Obejmuje to układ, typografię, kolory i responsywność.
    -   **Kluczowe selektory:**
        -   `.mycombtabfree-container`: Główny kontener dla listy kombinacji.
        -   `.mycombtabfree-table`: Style dla elementu `<table>`, gdy włączone jest „Wyświetl kombinacje jako tabelę”.
        -   `.mycombtabfree-row`, `.mycombtabfree-cell`: Style dla wierszy i komórek tabeli.
        -   `.mycombtabfree-image`, `.mycombtabfree-name`, `.mycombtabfree-reference`, `.mycombtabfree-price`, `.mycombtabfree-qty`, `.mycombtabfree-atc`: Specyficzne style dla każdego elementu danych kombinacji.
        -   Zapytania medialne do responsywnych dostosowań na mniejszych ekranach.
    -   **Nadpisywanie przez programistę:** Programiści mogą nadpisać te style w plikach CSS swojego niestandardowego szablonu, używając bardziej specyficznych selektorów lub modyfikując ten plik bezpośrednio (chociaż to ostatnie nie jest zalecane ze względu na łatwość aktualizacji).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`mycombtabfree/views/templates/admin/configure.tpl`**

    -   **Zakres:** Panel konfiguracji administratora.
    -   **Cel:** Renderuje formularz HTML dla ustawień konfiguracji modułu w Panelu administracyjnym PrestaShop. Ten szablon jest ładowany przez metodę `getContent()` głównej klasy modułu.
    -   **Zawartość:** Zawiera pola formularza (pola wyboru, pola tekstowe, rozwijane listy wyboru) odpowiadające ustawieniom opisanym w Sekcji 4.1.
-   **`mycombtabfree/views/templates/admin/pro-upsell.tpl`**

    -   **Zakres:** Panel konfiguracji administratora.
    -   **Cel:** Wyświetla treści promocyjne lub baner sprzedażowy dla wersji „Pro” modułu w konfiguracji Panelu administracyjnego. Jest to powszechna praktyka dla darmowych modułów.
-   **`mycombtabfree/views/templates/hook/pro-banner.tpl`**

    -   **Zakres:** Hook front-office.
    -   **Cel:** Renderuje baner promocyjny dla wersji „Pro” modułu, prawdopodobnie wyświetlany w mniej inwazyjnym hooku front-office (np. `displayFooter` lub `displayLeftColumn`).
-   **`mycombtabfree/views/templates/hook/tab.tpl`**

    -   **Zakres:** Hook front-office.
    -   **Cel:** Ten szablon jest prawdopodobnie używany, gdy włączone jest ustawienie „Wyświetl kombinacje jako zakładkę” lub gdy moduł jest podłączony do pozycji, która naturalnie tworzy zakładkę (np. `displayProductExtraContent`). Zawierałby strukturę zakładki produktu, w której renderowana byłaby rzeczywista lista/tabela kombinacji.
-   **`mycombtabfree/views/templates/hook/table.tpl`**

    -   **Zakres:** Hook front-office.
    -   **Cel:** Jest to główny szablon odpowiedzialny za renderowanie rzeczywistej listy lub tabeli kombinacji produktów w front-office. Iteruje przez dostępne kombinacje dla danego produktu i wyświetla każdą z nich zgodnie z ustawieniami konfiguracji modułu (np. pokazując obraz, referencję, cenę, pole ilości, przycisk dodaj do koszyka).
    -   **Logika:** Zawiera pętle Smarty (`{foreach}`) do iteracji po tablicy `$combinations`, instrukcje warunkowe (`{if}`) do wyświetlania elementów na podstawie ustawień modułu oraz zmienne takie jak `$combination.id_product_attribute`, `$combination.name`, `$combination.price` itp.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Klucze konfiguracyjne zazwyczaj będą miały wzorzec taki jak `MYCOMBTABFREE_SETTING_NAME`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do rejestrowania zasobów CSS (`mycombtabfree.css`) i JavaScript (`atc.js`) dla front-office. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” na stronie produktu. | Powszechny hook do wyświetlania listy kombinacji bezpośrednio pod szczegółami produktu. |
| `displayProductExtraContent` | W obszarze zakładek produktu na stronie produktu. | Pozwala na wyświetlanie listy kombinacji w jej własnej dedykowanej zakładce. |
| `displayFooterProduct` | Na dole treści strony produktu. | Inna możliwa lokalizacja dla listy kombinacji, często mniej widoczna. |
| `actionFrontControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler front-office. | Służy do dodawania plików CSS i JS specyficznych dla modułu do strony. |
| `moduleRoutes` | Podczas inicjalizacji przepisywania adresów URL. | (Nie jest jawnie używany przez ten moduł, ale jest to powszechny hook dla modułów z niestandardowymi adresami URL). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia deweloperskiego dla modułu „Combinations List Free”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/). Upewnij się, że pobierasz najnowszą wersję kompatybilną z Twoją instalacją PrestaShop z historii zamówień.
