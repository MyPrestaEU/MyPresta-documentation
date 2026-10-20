---
title: "Fullscreen Banner Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Fullscreen Banner Slider PrestaShop od MyPresta.eu."
sidebar:
  label: "Fullscreen Banner Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Fullscreen Banner Slider na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/fullscreen-banner-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/fullscreen-banner-slider/)
>
> ---


# Fullscreen Banner Slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Fullscreen Banner Slider” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji, gdzie możesz zarządzać wszystkimi aspektami swojego slidera.

Konfiguracja modułu jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, prezentując standardowy formularz konfiguracji PrestaShop.

#### **Ustawienia ogólne**

- **Co robi to ustawienie:** Te ustawienia kontrolują ogólne zachowanie i wygląd Twojego pełnoekranowego slidera.
- **Wpływ zmiany tego ustawienia:** Dostosowanie tych wartości bezpośrednio wpłynie na to, jak slider jest wyświetlany Twoim klientom, jego rozmiar, szybkość i czy jest aktywny.

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Włącz pełnoekranowy slider** | TAK | **Cel:** Włącza lub wyłącza całą funkcję slidera.   **Efekt:**   *Gdy włączone:* Pełnoekranowy slider pojawi się nowym odwiedzającym.   *Gdy wyłączone:* Slider nie będzie wyświetlany w Twoim sklepie.   **Zalecane:** TAK, aby aktywować funkcję. |
| **Szerokość slidera** | 100% | **Cel:** Definiuje szerokość slidera.   **Efekt:**   *Ustawione na 100% (zalecane):* Slider rozciągnie się na całą szerokość okna przeglądarki.   *Ustawione na stałą wartość w pikselach (np. 1200px):* Slider będzie miał stałą szerokość, potencjalnie pozostawiając puste miejsce na bardzo szerokich ekranach.   **Zalecane:** 100% dla prawdziwie pełnoekranowego doświadczenia. |
| **Wysokość slidera** | 100% | **Cel:** Definiuje wysokość slidera.   **Efekt:**   *Ustawione na 100% (zalecane):* Slider rozciągnie się na całą wysokość okna przeglądarki.   *Ustawione na stałą wartość w pikselach (np. 800px):* Slider będzie miał stałą wysokość, potencjalnie pozostawiając puste miejsce na bardzo wysokich lub krótkich ekranach.   **Zalecane:** 100% dla prawdziwie pełnoekranowego doświadczenia. |
| **Typ animacji** | (Rozwijana lista z różnymi opcjami) | **Cel:** Wybiera wizualny efekt przejścia między banerami.   **Efekt:** Każda opcja zapewnia inny styl animacji (np. zanikanie, przesuwanie, kostka itp.). Eksperymentuj, aby znaleźć taki, który pasuje do Twojej marki.   **Zalecane:** Wybierz animację, która jest płynna i niezbyt rozpraszająca. „Zanikanie” lub „Przesuwanie” są często dobrymi punktami wyjścia. |
| **Szybkość animacji (ms)** | 800 | **Cel:** Kontroluje szybkość przejścia między banerami, w milisekundach (1000ms = 1 sekunda).   **Efekt:**   *Wyższa wartość (np. 1500):* Wolniejsze, bardziej stopniowe przejścia.   *Niższa wartość (np. 400):* Szybsze, bardziej dynamiczne przejścia.   **Zalecane:** 800-1000ms dla zrównoważonego, profesjonalnego wyglądu. |
| **Interwał między slajdami (ms)** | 3000 | **Cel:** Ustawia czas wyświetlania każdego banera przed przejściem do następnego, w milisekundach.   **Efekt:**   *Wyższa wartość (np. 5000):* Banery pozostają na ekranie dłużej, dając odwiedzającym więcej czasu na przeczytanie/obejrzenie.   *Niższa wartość (np. 2000):* Banery zmieniają się szybciej, tworząc dynamiczne wrażenie.   **Zalecane:** 3000-5000ms, w zależności od złożoności treści banera. |
| **Pokaż strzałki nawigacyjne** | TAK | **Cel:** Określa, czy strzałki „następny” i „poprzedni” są widoczne do ręcznej nawigacji po slajdach.   **Efekt:**   *Gdy włączone:* Strzałki pojawiają się po bokach slidera, umożliwiając użytkownikom klikanie banerów.   *Gdy wyłączone:* Banery zmieniają się tylko automatycznie na podstawie interwału.   **Zalecane:** TAK, dla lepszej kontroli użytkownika. |
| **Pokaż kropki paginacji** | TAK | **Cel:** Określa, czy małe kropki (lub miniatury) reprezentujące każdy slajd są widoczne, zazwyczaj na dole slidera.   **Efekt:**   *Gdy włączone:* Pojawiają się kropki, umożliwiając użytkownikom zobaczenie, ile jest slajdów i przejście do konkretnego.   *Gdy wyłączone:* Brak wizualnego wskaźnika liczby slajdów lub bezpośredniej nawigacji.   **Zalecane:** TAK, dla lepszej orientacji i nawigacji użytkownika. |
| **Autoodtwarzanie slidera** | TAK | **Cel:** Kontroluje, czy slider automatycznie przechodzi przez banery.   **Efekt:**   *Gdy włączone:* Banery będą automatycznie zmieniać się po ustawionym interwale.   *Gdy wyłączone:* Banery będą zmieniać się tylko, jeśli użytkownik kliknie strzałki nawigacyjne lub kropki paginacji.   **Zalecane:** TAK, aby upewnić się, że wszystkie Twoje wiadomości zostaną zobaczone. |
| **Tekst przycisku zamknięcia** | Zamknij | **Cel:** Pozwala dostosować tekst wyświetlany na przycisku zamykającym pełnoekranowy slider.   **Efekt:** Zmienia tekst na przycisku.   **Zalecane:** „Zamknij”, „Pomiń” lub „Przejdź do sklepu”. |
| **Wygaśnięcie pliku cookie (dni)** | 7 | **Cel:** Ustawia, jak długo moduł pamięta, że użytkownik widział slider, zapobiegając jego ponownemu wyświetleniu.   **Efekt:**   *Ustawione na 7 dni:* Slider pojawi się ponownie dla tego samego użytkownika po 7 dniach.   *Ustawione na 0:* Slider pojawi się przy każdej wizycie (niezalecane dla doświadczenia użytkownika).   *Ustawione na wysoką liczbę (np. 365):* Slider pojawi się tylko raz w roku dla powracających odwiedzających.   **Zalecane:** 7 dni to dobry balans, pozwalający na ponowne zaangażowanie powracających odwiedzających nowymi ofertami okresowo, bez bycia natrętnym. |

#### **Zarządzanie banerami**

Ta sekcja pozwala dodawać, edytować i usuwać poszczególne banery, które będą wyświetlane w Twoim sliderze.

- **Co robi to ustawienie:** Każdy wpis tutaj reprezentuje jeden obraz (baner) w Twoim sliderze. Możesz przesłać obraz, połączyć go z konkretną stroną i ustawić jego kolejność wyświetlania.
- **Wpływ zmiany tego ustawienia:**
  - *Dodanie nowego banera:* Wprowadza nowy slajd do Twojej rotacji.
  - *Edycja banera:* Aktualizuje jego obraz, link lub pozycję.
  - *Usunięcie banera:* Usuwa go ze slidera.

Dla każdego banera zazwyczaj znajdziesz pola takie jak:

- **Obraz banera:** Prześlij plik obrazu dla swojego slajdu. Upewnij się, że obrazy są wysokiej rozdzielczości i zoptymalizowane pod kątem sieci, aby zapewnić szybkie ładowanie.
- **Link banera (URL):** Adres internetowy (URL), na który klienci zostaną przekierowani po kliknięciu tego banera. Pozostaw puste, jeśli baner ma charakter wyłącznie informacyjny.
- **Kolejność wyświetlania:** Wartość numeryczna, która określa kolejność banerów. Banery z niższymi numerami pojawiają się jako pierwsze.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|
| Konfiguracja modułu | Włącz pełnoekranowy slider | TAK | Aktywuje/dezaktywuje całą funkcję slidera. |
| Konfiguracja modułu | Szerokość slidera | 100% | Ustawia szerokość slidera (np. 100% dla pełnej szerokości). |
| Konfiguracja modułu | Wysokość slidera | 100% | Ustawia wysokość slidera (np. 100% dla pełnej wysokości). |
| Konfiguracja modułu | Typ animacji | (Różne) | Wybiera wizualny efekt przejścia między slajdami. |
| Konfiguracja modułu | Szybkość animacji (ms) | 800 | Kontroluje szybkość przejść slajdów. |
| Konfiguracja modułu | Interwał między slajdami (ms) | 3000 | Ustawia, jak długo wyświetlany jest każdy baner. |
| Konfiguracja modułu | Pokaż strzałki nawigacyjne | TAK | Wyświetla/ukrywa strzałki do ręcznej nawigacji po slajdach. |
| Konfiguracja modułu | Pokaż kropki paginacji | TAK | Wyświetla/ukrywa kropki/miniaturki do bezpośredniego dostępu do slajdów. |
| Konfiguracja modułu | Autoodtwarzanie slidera | TAK | Włącza/wyłącza automatyczne przechodzenie slajdów. |
| Konfiguracja modułu | Tekst przycisku zamknięcia | Zamknij | Dostosowuje tekst na przycisku zamykającym slider. |
| Konfiguracja modułu | Wygaśnięcie pliku cookie (dni) | 7 | Określa, jak długo użytkownik nie będzie widział slidera po jego zamknięciu. |
| Konfiguracja modułu | Obraz banera | (Prześlij) | Przesyła obraz dla pojedynczego slajdu. |
| Konfiguracja modułu | Link banera (URL) | (Puste) | Ustawia docelowy adres URL po kliknięciu banera. |
| Konfiguracja modułu | Kolejność wyświetlania | (Liczba) | Definiuje kolejność, w jakiej pojawiają się banery. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Slider nie pojawia się w moim sklepie. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Fullscreen Banner Slider” jest zainstalowany i włączony.
2.  **Konfiguracja:** Sprawdź, czy opcja „Włącz pełnoekranowy slider” jest ustawiona na TAK w konfiguracji modułu.
3.  **Wygaśnięcie pliku cookie:** Jeśli widziałeś slider wcześniej, może to być spowodowane plikiem cookie. Spróbuj wyczyścić pliki cookie przeglądarki lub otworzyć sklep w oknie incognito/prywatnym, aby zasymulować pierwszego odwiedzającego.
4.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop w **Zaawansowane > Wydajność**. Wyczyść również pamięć podręczną przeglądarki.
5.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, czasami niestandardowe motywy mogą powodować zakłócenia. Tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy slider się pojawi. Jeśli tak, Twój motyw może wymagać niewielkiej korekty (skontaktuj się z twórcą motywu lub webmasterem).

**P: Moje obrazy banerów wyglądają na rozmyte lub rozciągnięte. Jak to naprawić?**
O: Zazwyczaj dzieje się tak, jeśli przesłane obrazy nie mają wystarczająco wysokiej rozdzielczości lub mają nieprawidłowe proporcje dla wyświetlania pełnoekranowego.

1.  **Jakość obrazu:** Zawsze używaj obrazów o wysokiej rozdzielczości.
2.  **Proporcje:** Chociaż moduł skaluje, spróbuj używać obrazów, które są szerokie i stosunkowo krótkie, odpowiednie dla pełnoekranowego banera (np. 1920x1080 pikseli lub podobne szerokie formaty). Unikaj bardzo wysokich lub wąskich obrazów.
3.  **Optymalizacja:** Upewnij się, że Twoje obrazy są zoptymalizowane pod kątem sieci (skompresowane), aby zapobiec długiemu ładowaniu, nawet jeśli mają wysoką rozdzielczość.

**P: Czy mogę mieć różne slidery dla różnych stron lub grup klientów?**
O: Ta konkretna wersja modułu Fullscreen Banner Slider jest przeznaczona do pojedynczego, pełnoekranowego wyświetlania na całej stronie, które pojawia się raz na sesję/plik cookie użytkownika. Nie oferuje zaawansowanych opcji targetowania dla konkretnych stron lub grup klientów. Jeśli potrzebujesz takiej funkcjonalności, możesz potrzebować bardziej zaawansowanego modułu do zarządzania banerami lub niestandardowego rozwoju.

**P: Jak przetłumaczyć tekst przycisku „Zamknij” na inne języki?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów” jako Typ tłumaczenia.
3.  Wybierz swój motyw.
4.  Wybierz język, na który chcesz przetłumaczyć.
5.  Znajdź moduł „Fullscreen Banner Slider” na liście. Powinieneś tam zobaczyć pole „Tekst przycisku zamknięcia” do przetłumaczenia. Zapisz zmiany.

**P: Slider się pojawia, ale animacje nie działają lub układ jest nieprawidłowy.**
O:

1.  **Konflikty JavaScript:** Często jest to spowodowane konfliktami z JavaScriptem innych modułów lub JavaScriptem Twojego motywu. Sprawdź konsolę programisty przeglądarki (klawisz F12) pod kątem błędów JavaScript.
2.  **Konflikty CSS:** Podobnie jak w przypadku JS, CSS Twojego motywu może nadpisywać style modułu.
3.  **Ponowna instalacja modułu:** Czasami świeża ponowna instalacja może rozwiązać nieoczekiwane problemy. Odinstaluj moduł (bez usuwania danych, jeśli zostaniesz o to poproszony), a następnie zainstaluj go ponownie.
    Jeśli błędy nadal występują, skonsultuj się z webmasterem lub skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły z konsoli programisty przeglądarki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Fullscreen Banner Slider (`fullscreenslider`) to standardowy moduł PrestaShop, zaimplementowany głównie w jego głównym pliku PHP, `ajax_fullscreenslider.php`. Wykorzystuje klasę `Module` PrestaShop do instalacji, deinstalacji i konfiguracji (`getContent()`). Wyświetlanie w front-office jest zarządzane poprzez podpięcie się do `displayHeader` i renderowanie szablonu Smarty. Sama funkcjonalność slidera opiera się na zewnętrznych wtyczkach jQuery (`jquery.skitter.js`, `jquery.easing.1.3.js`) do animacji oraz `noconflict.js` w celu zapewnienia kompatybilności jQuery. Wartości konfiguracyjne są przechowywane w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel` w katalogu `classes/`. Wszystkie dane (obrazy banerów, linki, kolejność) są zarządzane bezpośrednio poprzez ustawienia konfiguracyjne modułu, zazwyczaj serializowane i przechowywane w `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie dla podstawowej funkcjonalności i animacji slidera. Są one zazwyczaj ładowane w front-office.

- `fullscreenslider/js/jquery.easing.1.3.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Zapewnia dodatkowe funkcje easing dla animacji jQuery, umożliwiając bardziej zróżnicowane i płynne efekty przejścia poza domyślne liniowe lub swing. Jest to zależność dla `jquery.skitter.js`.
- `fullscreenslider/js/jquery.skitter.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Jest to główna wtyczka jQuery odpowiedzialna za funkcjonalność slidera. Obsługuje ładowanie obrazów, przejścia animacji, nawigację (strzałki, paginacja), autoodtwarzanie i wiązanie zdarzeń dla interakcji użytkownika. Inicjalizuje slider na podstawie ustawień konfiguracyjnych przekazanych z modułu.
- `fullscreenslider/js/noconflict.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Ten skrypt jest kluczowy dla zapewnienia kompatybilności, gdy wiele bibliotek JavaScript (zwłaszcza różne wersje jQuery) jest ładowanych na tej samej stronie. Zazwyczaj opakowuje kod jQuery w natychmiast wywoływaną funkcję (IIFE), która przekazuje `jQuery` jako argument, pozwalając na jego aliasowanie jako `$` lokalnie bez konfliktu z innymi bibliotekami, które również mogą używać `$`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera jeden główny plik CSS do stylizacji slidera.

- `fullscreenslider/css/skitter.styles.css`
  - **Zakres:** Stylizacja klienta w front-office.
  - **Odpowiedzialność:** Zawiera wszystkie niezbędne reguły CSS do stylizacji pełnoekranowego slidera, w tym jego kontenera, strzałek nawigacyjnych, kropek paginacji i efektów wizualnych wybranego typu animacji. Definiuje domyślny wygląd i styl slidera.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:**
    - `.box_skitter` (główny kontener slidera)
    - `.box_skitter ul` (lista slajdów)
    - `.box_skitter ul li` (pojedynczy slajd)
    - `.box_skitter .info_slide` (podpisy/informacje slajdów, jeśli używane)
    - `.box_skitter .prev_button`, `.box_skitter .next_button` (strzałki nawigacyjne)
    - `.box_skitter .info_slide_dots`, `.box_skitter .info_slide_thumb` (elementy paginacji)
    - Specyficzne klasy dla typów animacji (np. `.cube`, `.fade` itp.)

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania treści w front-office.

- **Szablony hooków (`views/templates/hook/`)**:

  - `fullscreenslider/header.tpl`
    - **Hook:** `displayHeader` (lub podobny, w zależności od implementacji metody `hook` modułu).
    - **Cel:** Ten szablon jest prawdopodobnie odpowiedzialny za wstrzykiwanie niezbędnych plików CSS i JavaScript do sekcji `<head>` HTML, a potencjalnie początkowej struktury HTML dla kontenera slidera, który zostanie następnie wypełniony i animowany przez JavaScript. Może również zawierać logikę sprawdzania pliku cookie, który określa, czy slider powinien być wyświetlany.
  - `fullscreenslider/top.tpl`
    - **Hook:** Ten szablon jest prawdopodobnie renderowany w hooku `displayTop` lub bezpośrednio dołączany przez `header.tpl` w celu wyprowadzenia głównej struktury HTML samego pełnoekranowego slidera.
    - **Cel:** Zawiera elementy `div` i strukturę `ul/li`, której `jquery.skitter.js` oczekuje, aby zainicjować slider. Iteruje przez skonfigurowane banery, wyprowadzając każdy obraz z powiązanym linkiem. Zawiera również HTML dla przycisku zamknięcia.
- **Szablony administracyjne (`views/templates/admin/`)**: Ten moduł nie wydaje się używać dedykowanych szablonów administracyjnych, ponieważ konfiguracja jest obsługiwana bezpośrednio w `getContent()`.
- **Szablony front-office (`views/templates/front/`)**: Ten moduł nie wydaje się używać dedykowanych, samodzielnych szablonów stron front-office.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy niestandardowych tabel SQL.
  - Ustawienia konfiguracyjne (w tym serializowane dane dla banerów, takie jak ścieżki obrazów, linki i kolejność) są przechowywane w tabeli `ps_configuration`. Klucze zazwyczaj mają wzorzec `FULLSCREENSLIDER_SETTING_NAME`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS i JavaScript modułu, a potencjalnie początkową strukturę HTML dla slidera, wraz z logiką sprawdzania plików cookie. |
| `displayTop` (lub podobny) | Wykonywany w górnej sekcji strony front-office, często tuż pod nagłówkiem. | Renderuje główną strukturę HTML pełnoekranowego slidera, w tym obrazy banerów i elementy nawigacyjne. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Fullscreen Banner Slider, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
