---
title: "Suwak ostatnich zamówień - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Suwak ostatnich zamówień” od MyPresta.eu."
sidebar:
  label: "Suwak ostatnich zamówień - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Last orders slider na MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-orders-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/last-orders-slider/)
>
> ---


# Suwak ostatnich zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.6+, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj domyślnie włączone w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Suwak ostatnich zamówień”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok modułu „Suwak ostatnich zamówień”.

#### Ustawienia ogólne

- **Co robi to ustawienie:** Ta sekcja kontroluje podstawowe zachowanie i wygląd suwaka zamówień.
- **Wpływ zmiany tego ustawienia:** Dostosowanie tych ustawień bezpośrednio wpłynie na wygląd suwaka, miejsce jego pojawiania się i informacje, które wyświetla klientom.

| Ustawienie / Opcja | Co robi to ustawienie | Wpływ zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Włącz moduł** | Włącza lub wyłącza całą funkcjonalność suwaka. | *Po włączeniu:* Suwak pojawi się w Twoim front office zgodnie z innymi ustawieniami. *Po wyłączeniu:* Suwak nie będzie widoczny dla klientów. | TAK | Chcesz tymczasowo ukryć suwak na czas konserwacji lub specjalnej kampanii. |
| **Liczba wyświetlanych zamówień** | Określa, ile ostatnich zamówień będzie cyklicznie wyświetlanych przez suwak. | *Po ustawieniu na 5:* Suwak pokaże informacje o 5 najnowszych zamówieniach. *Po ustawieniu na 10:* Pokaże 10. | 5-10 (w zależności od wolumenu zamówień) | Jeśli masz bardzo duży wolumen zamówień, wyświetlanie większej liczby może być przytłaczające. Jeśli masz mniej zamówień, wyświetlanie większej liczby zapewnia, że zawsze będzie jakaś treść. |
| **Statusy zamówień do wyświetlenia** | Wybiera, które statusy zamówień (np. „Płatność zaakceptowana”, „Dostarczono”) są uważane za „ostatnie zamówienia” dla suwaka. | *Po wybraniu „Płatność zaakceptowana”:* Pojawią się tylko zamówienia, które osiągnęły ten status. *Po wybraniu „Anulowano”:* Mogą pojawić się anulowane zamówienia (niezalecane dla dowodu społecznego). | „Płatność zaakceptowana”, „W trakcie realizacji”, „Dostarczono” | Chcesz wyświetlać tylko zamówienia, które są potwierdzone i przetwarzane lub zostały pomyślnie dostarczone, aby budować pozytywne zaufanie. |
| **Wyświetl imię klienta** | Kontroluje, czy wyświetlane jest imię i pierwsza litera nazwiska klienta. | *Po włączeniu:* „Jan K. z Krakowa…” *Po wyłączeniu:* „Ktoś z Krakowa…” | TAK | Wyświetlanie częściowego imienia dodaje osobistego akcentu i sprawia, że zamówienia wydają się bardziej realne, wzmacniając dowód społeczny. |
| **Wyświetl miasto klienta** | Kontroluje, czy wyświetlane jest miasto klienta. | *Po włączeniu:* „…z Krakowa właśnie kupił…” *Po wyłączeniu:* „…właśnie kupił…” | TAK | Wyświetlanie miasta dodaje warstwę autentyczności i może rezonować z lokalnymi klientami. |
| **Wyświetl nazwę produktu** | Kontroluje, czy wyświetlana jest nazwa zakupionego produktu. | *Po włączeniu:* „…właśnie kupił koszulkę.” *Po wyłączeniu:* „…właśnie złożył zamówienie.” | TAK | Wyświetlanie nazwy produktu sprawia, że zakup jest bardziej namacalny i może podkreślać popularne przedmioty. |
| **Wyświetl zdjęcie produktu** | Kontroluje, czy wyświetlane jest małe zdjęcie zakupionego produktu. | *Po włączeniu:* Obok tekstu pojawi się mała miniatura produktu. *Po wyłączeniu:* Wyświetlany będzie tylko tekst. | TAK | Wizualizacje są angażujące. Zdjęcie produktu sprawia, że suwak jest bardziej atrakcyjny i informacyjny. |
| **Szybkość animacji (milisekundy)** | Ustawia, jak szybko suwak przechodzi między różnymi zamówieniami. | *Niższa wartość (np. 3000):* Szybsze przejścia, zamówienia zmieniają się co 3 sekundy. *Wyższa wartość (np. 8000):* Wolniejsze przejścia, zamówienia zmieniają się co 8 sekund. | 5000 (5 sekund) | Umiarkowana prędkość sprawia, że suwak jest dynamiczny, nie będąc zbyt szybkim do odczytania ani zbyt wolnym do aktualizacji. |
| **Kolor tekstu** | Ustawia kolor tekstu wyświetlanego w suwaku. | *Po ustawieniu na #000000 (czarny):* Tekst będzie czarny. *Po ustawieniu na #FF0000 (czerwony):* Tekst będzie czerwony. | #FFFFFF (biały) lub kolor kontrastujący z tłem | Wybierz kolor, który wyróżnia się na tle wybranego koloru tła i pasuje do estetyki Twojej marki. |
| **Kolor tła** | Ustawia kolor tła paska suwaka. | *Po ustawieniu na #FFFFFF (biały):* Tło suwaka będzie białe. *Po ustawieniu na #000000 (czarny):* Tło suwaka będzie czarne. | #000000 (czarny) lub kolor kontrastujący z Twoim motywem | Wybierz kolor, który sprawi, że suwak będzie widoczny i uzupełni projekt Twojego sklepu. |
| **Hook do wyświetlania suwaka** | Wybiera, gdzie w Twoim motywie PrestaShop pojawi się suwak. | *Po wybraniu „displayTop”:* Suwak pojawia się w górnej części Twojego sklepu. *Po wybraniu „displayFooter”:* Suwak pojawia się na dole. | displayTop lub displayNavFullWidth | Wybierz widoczne miejsce, gdzie klienci łatwo go zobaczą, nie zasłaniając krytycznej treści. |

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł | TAK | Włącza/wyłącza suwak. |
| Konfiguracja modułu | Liczba wyświetlanych zamówień | 5-10 | Kontroluje, ile ostatnich zamówień jest wyświetlanych. |
| Konfiguracja modułu | Statusy zamówień do wyświetlenia | Płatność zaakceptowana, W trakcie realizacji, Dostarczono | Filtruje zamówienia według ich statusu do wyświetlenia. |
| Konfiguracja modułu | Wyświetl imię klienta | TAK | Pokazuje imię i pierwszą literę nazwiska klienta. |
| Konfiguracja modułu | Wyświetl miasto klienta | TAK | Pokazuje miasto klienta. |
| Konfiguracja modułu | Wyświetl nazwę produktu | TAK | Pokazuje nazwę zakupionego produktu. |
| Konfiguracja modułu | Wyświetl zdjęcie produktu | TAK | Pokazuje małe zdjęcie zakupionego produktu. |
| Konfiguracja modułu | Szybkość animacji (milisekundy) | 5000 | Ustawia szybkość przejścia między zamówieniami. |
| Konfiguracja modułu | Kolor tekstu | #FFFFFF (biały) | Definiuje kolor tekstu w suwaku. |
| Konfiguracja modułu | Kolor tła | #000000 (czarny) | Definiuje kolor tła suwaka. |
| Konfiguracja modułu | Hook do wyświetlania suwaka | displayTop / displayNavFullWidth | Określa pozycję suwaka w Twoim motywie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Suwak nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O:

-   **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Suwak ostatnich zamówień” jest zainstalowany i włączony.
-   **Zweryfikuj wybór hooka:** W konfiguracji modułu dokładnie sprawdź, czy wybrałeś prawidłowy „Hook do wyświetlania suwaka” (np. `displayTop`, `displayNavFullWidth`). Niektóre hooki mogą nie być obecne lub aktywne we wszystkich motywach.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się nowej treści.
-   **Sprawdź statusy zamówień:** Upewnij się, że wybrałeś co najmniej jeden „Status zamówienia do wyświetlenia”, który ma z nim powiązane ostatnie zamówienia. Jeśli żadne zamówienia nie pasują do wybranych statusów, suwak będzie pusty.
-   **Kompatybilność z motywem:** Chociaż moduł został zaprojektowany z myślą o szerokiej kompatybilności, bardzo mocno dostosowane motywy mogą wymagać drobnych korekt. Jeśli wszystko inne zawiedzie, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Suwak się wyświetla, ale kolory nie pasują do mojego motywu.**
O:

-   **Dostosuj kolory w konfiguracji:** Przejdź do strony konfiguracji modułu. Użyj ustawień „Kolor tekstu” i „Kolor tła”, aby wybrać kolory, które uzupełniają projekt Twojego sklepu. Możesz użyć narzędzia do wybierania kolorów (dostępnego online lub jako rozszerzenia przeglądarki), aby znaleźć dokładne kody szesnastkowe z Twojego motywu.
-   **Niestandardowy CSS (zaawansowane):** Jeśli opcje kolorów modułu nie są wystarczające, Twój webmaster może dodać niestandardowe reguły CSS do arkusza stylów Twojego motywu, aby zastąpić domyślne style modułu. (Zobacz sekcję 7.5, aby uzyskać szczegółowe informacje dla programistów).

**P3: Suwak jest pusty lub nie aktualizuje się o nowe zamówienia.**
A:

-   **Statusy zamówień:** Upewnij się, że ustawienie „Statusy zamówień do wyświetlenia” zawiera statusy Twoich najnowszych zamówień (np. „Płatność zaakceptowana”, „Dostarczono”). Jeśli Twoje ostatnie zamówienia mają status, który nie został wybrany, nie pojawią się.
-   **Ostatnie zamówienia:** Moduł wyświetla *ostatnie* zamówienia. Jeśli Twój sklep nie miał żadnych zamówień od jakiegoś czasu lub jeśli „Liczba wyświetlanych zamówień” jest ustawiona zbyt nisko, może wydawać się pusty.
-   **Pamięć podręczna:** Ponownie, wyczyszczenie pamięci podręcznej PrestaShop (**Zaawansowane > Wydajność**) może pomóc w zapewnieniu, że moduł pobiera najnowsze dane.

**P4: Jak przetłumaczyć tekst w suwaku na inne języki?**
O:

-   **Narzędzie tłumaczeń PrestaShop:** Przejdź do **Lokalizacja > Tłumaczenia**.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz swój język.
-   Znajdź moduł „Suwak ostatnich zamówień” na liście. Będziesz mógł przetłumaczyć wszelkie zakodowane na stałe ciągi znaków (takie jak „właśnie kupił” lub „z”), których używa moduł.
-   **Dynamiczna treść:** Nazwy klientów, miasta i nazwy produktów są pobierane bezpośrednio z danych Twojego sklepu i pojawią się w języku, w którym zostały wprowadzone lub skonfigurowane w Twoim katalogu produktów.

**P5: Suwak jest za szybki/wolny lub wyświetla za dużo/za mało zamówień.**
O:

-   **Szybkość animacji:** Dostosuj ustawienie „Szybkość animacji (milisekundy)” w konfiguracji modułu. Wyższa liczba oznacza wolniejsze przejścia.
-   **Liczba zamówień:** Zmodyfikuj ustawienie „Liczba wyświetlanych zamówień”, aby kontrolować, ile unikalnych zamówień jest cyklicznie wyświetlanych. Eksperymentuj z tymi wartościami, aby znaleźć idealną równowagę dla ruchu w Twoim sklepie i wolumenu zamówień.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółową analizę techniczną modułu „Suwak ostatnich zamówień”, przeznaczoną dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Suwak ostatnich zamówień” (`lastord`) to standardowy moduł PrestaShop, zaprojektowany głównie do wyświetlania dynamicznej treści w front office. Wykorzystuje system hooków PrestaShop do wstrzykiwania swojej treści w różne części motywu. Główna logika znajduje się w głównym pliku modułu (`index.php`), który obsługuje konfigurację, pobieranie danych i renderowanie szablonów. Nie wprowadza niestandardowych kontrolerów ani złożonych ObjectModels, opierając się zamiast tego na bezpośrednich zapytaniach do bazy danych (za pośrednictwem `Db::getInstance()`) w celu pobierania danych zamówień i szablonach Smarty do prezentacji. Stylizacja jest zarządzana za pomocą dedykowanego pliku CSS.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pośrednictwem metody `getContent()` w głównym pliku modułu, a renderowanie front-office odbywa się bezpośrednio za pośrednictwem metod hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Całe pobieranie danych i logika biznesowa są hermetyzowane w klasie `Lastord` w `index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność animacji i suwaka jest prawdopodobnie obsługiwana przez animacje CSS lub bardzo lekki, wbudowany skrypt w szablonie, lub przez bibliotekę zewnętrzną już załadowaną przez PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`lastord/views/css/lastord.css`**
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów odpowiada za wygląd wizualny samego paska suwaka zamówień, w tym jego pozycjonowanie, tło, style tekstu i potencjalnie właściwości animacji.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie:**
        -   `.lastord_wrapper`: Główny kontener dla całego suwaka.
        -   `.lastord_item`: Pojedynczy element zamówienia w suwaku.
        -   `.lastord_text`: Treść tekstowa (klient, produkt, miasto).
        -   `.lastord_image`: Kontener obrazu produktu.
        -   Reguły `@keyframes` (jeśli są zdefiniowane dla animacji).
        Programiści mogą nadpisać te selektory w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do swoich specyficznych wymagań projektowych.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   **`lastord/views/templates/hook/lo_orders.tpl`**
        -   **Hook:** Jest to główny szablon renderowany przez metody `hook` modułu (np. `hookDisplayTop`, `hookDisplayNavFullWidth`, `hookDisplayFooter` itp.).
        -   **Cel:** Zawiera strukturę HTML dla opakowania suwaka i iteruje przez zmienną `$orders` (przekazaną z logiki PHP modułu), aby wyświetlić każde ostatnie zamówienie. Zawiera logikę warunkową do pokazywania/ukrywania imienia klienta, miasta, nazwy produktu i obrazu na podstawie konfiguracji modułu. Stosuje również wbudowane style dla kolorów tekstu i tła.
    -   **`lastord/views/templates/hook/displayBanner.tpl`**
        -   **Hook:** `displayBanner`
        -   **Cel:** Ten szablon prawdopodobnie działa jako opakowanie lub bezpośredni punkt włączenia dla `lo_orders.tpl`, gdy moduł jest podpięty do `displayBanner`. Zapewnia prawidłowe renderowanie treści suwaka w ramach tego konkretnego hooka.
    -   **`lastord/views/templates/hook/displayNavFullWidth.tpl`**
        -   **Hook:** `displayNavFullWidth`
        -   **Cel:** Podobnie jak `displayBanner.tpl`, ten szablon jest używany do renderowania treści `lo_orders.tpl`, gdy moduł jest podpięty do `displayNavFullWidth`.
    -   **`lastord/views/templates/hook/displayTop.tpl`**
        -   **Hook:** `displayTop`
        -   **Cel:** Ten szablon jest używany do renderowania treści `lo_orders.tpl`, gdy moduł jest podpięty do `displayTop`.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   **`lastord/views/templates/admin/orderstates.tpl`**
        -   **Cel:** Ten szablon jest używany w metodzie `getContent()` modułu do renderowania listy pól wyboru statusów zamówień na stronie konfiguracji w panelu administracyjnym. Iteruje przez dostępne statusy zamówień i wyświetla je z ich aktualnym statusem wyboru.
-   **Szablony front-office (`views/templates/front/`)**: Brak zidentyfikowanych.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` za pomocą kluczy takich jak `LASTORD_ENABLED`, `LASTORD_ORDERS_COUNT`, `LASTORD_ORDER_STATES`, `LASTORD_DISPLAY_NAME`, `LASTORD_DISPLAY_CITY`, `LASTORD_DISPLAY_PRODUCT`, `LASTORD_DISPLAY_IMAGE`, `LASTORD_ANIMATION_SPEED`, `LASTORD_TEXT_COLOR`, `LASTORD_BACKGROUND_COLOR`, `LASTORD_HOOK`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` front office. | Służy do rejestrowania zasobów (CSS) i potencjalnie wbudowanego JavaScriptu. |
| `displayTop` | Zazwyczaj na samej górze strony, poniżej nagłówka. | Renderuje suwak w widocznym miejscu na górze. |
| `displayNavFullWidth` | Często sekcja o pełnej szerokości powyżej lub poniżej głównej nawigacji. | Renderuje suwak w obszarze nawigacji o pełnej szerokości. |
| `displayBanner` | Typowy hook dla banerów, często na samej górze. | Renderuje suwak jako baner. |
| `displayLeftColumn` | W lewym pasku bocznym. | Renderuje suwak w lewej kolumnie. |
| `displayRightColumn` | W prawym pasku bocznym. | Renderuje suwak w prawej kolumnie. |
| `displayFooter` | W sekcji stopki strony. | Renderuje suwak na dole strony. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku „dodaj do koszyka”. | Renderuje suwak na stronie produktu, aby skupić się na konwersji. |
| `displayFooterProduct` | W sekcji stopki strony produktu. | Renderuje suwak na dole strony produktu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Suwak ostatnich zamówień”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności i integracji modułu.
