---
title: "Prestashop Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Slider od MyPresta.eu."
sidebar:
  label: "Prestashop Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Prestashop Slider na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/prestashop-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/prestashop-slider/)
>
> ---


# Prestashop Slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj preinstalowane w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny panel sterowania dla Twojego Prestashop Slider. Tutaj zdefiniujesz wygląd, styl i zawartość swoich sliderów.

#### **Ustawienia ogólne**

-   **Co robi to ustawienie:** Te ustawienia kontrolują ogólne zachowanie i wygląd Twojego slidera.
-   **Efekt zmiany tego ustawienia:**
    -   *Szerokość slidera:* Określa, jak szeroki będzie slider. Może to być stała wartość w pikselach lub procent dla responsywności.
    -   *Wysokość slidera:* Określa wysokość slidera.
    -   *Typ animacji:* Wybiera jeden z 40 dostępnych efektów przejścia między slajdami.
    -   *Prędkość animacji:* Kontroluje, jak szybko następuje przejście między slajdami.
    -   *Interwał slajdów:* Ustawia czas wyświetlania każdego slajdu przed automatycznym przejściem do następnego.
    -   *Strzałki nawigacyjne:* Włącza/wyłącza strzałki w lewo/prawo do ręcznej nawigacji po slajdach.
    -   *Kropki/punkty nawigacyjne:* Włącza/wyłącza małe kropki, zazwyczaj znajdujące się na dole slidera, do bezpośredniego wyboru slajdu.
    -   *Miniatury:* Włącza/wyłącza małe obrazy podglądu każdego slajdu, często wyświetlane poniżej głównego slidera.
    -   *Podgląd miniatur:* Jeśli miniatury są włączone, to ustawienie kontroluje, czy większy podgląd pojawia się po najechaniu kursorem na miniaturę.
    -   *Wyświetlanie podpisów:* Kontroluje, czy i jak wyświetlane są podpisy tekstowe związane z każdym slajdem.
-   **Zalecana wartość:**
    -   *Szerokość slidera:* `100%` dla responsywnego slidera na całą szerokość, lub konkretna wartość w pikselach, np. `1140px`, aby dopasować do głównego obszaru treści Twojego motywu.
    -   *Wysokość slidera:* Zacznij od `400px` i dostosuj w zależności od proporcji obrazu i projektu.
    -   *Typ animacji:* Eksperymentuj! `fade` lub `slice` to dobre punkty wyjścia dla czystego wyglądu.
    -   *Prędkość animacji:* `800` (milisekund) dla płynnego przejścia.
    -   *Interwał slajdów:* `5000` (5 sekund) to dobry balans, aby użytkownicy mogli przeczytać treść bez pośpiechu.
    -   *Strzałki nawigacyjne:* `TAK` dla lepszej kontroli użytkownika.
    -   *Kropki/punkty nawigacyjne:* `TAK` dla łatwego przeglądu i nawigacji.
    -   *Miniatury:* Początkowo `NIE`, włącz, jeśli masz wiele slajdów i chcesz mieć wizualny indeks.
    -   *Podgląd miniatur:* `TAK`, jeśli miniatury są włączone.
    -   *Wyświetlanie podpisów:* `TAK`, jeśli planujesz dodać tekst do swoich slajdów.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz mieć baner na całą szerokość na swojej stronie głównej, który obraca się przez trzy nowe linie produktów. Ustawisz szerokość na `100%`, wybierzesz animację `fade` i ustawisz interwał `5 sekund`. Włączysz strzałki nawigacyjne i kropki, aby klienci mogli przeglądać ręcznie, jeśli zechcą.

#### **Sekcja zarządzania slajdami**

-   **Co robi to ustawienie:** Ta sekcja umożliwia dodawanie, edytowanie i usuwanie pojedynczych slajdów z Twojego slidera. Każdy slajd składa się z obrazu i powiązanych ustawień.
-   **Efekt zmiany tego ustawienia:**
    -   *Dodawanie nowego slajdu:* Nowy obraz zostanie dodany do rotacji slidera. Prześlesz obraz, zdefiniujesz jego link, podpis i potencjalnie unikalną animację.
    -   *Edytowanie istniejącego slajdu:* Możesz zmienić obraz, jego link docelowy, tekst podpisu lub indywidualny typ animacji dla tego konkretnego slajdu.
    -   *Usuwanie slajdu:* Wybrany slajd zostanie usunięty z Twojego slidera.
    -   *Zmienianie kolejności slajdów:* Możesz przeciągać i upuszczać slajdy, aby zmienić kolejność, w jakiej pojawiają się w rotacji.
-   **Zalecana wartość:** Zawsze używaj wysokiej jakości, zoptymalizowanych obrazów, które są spójne pod względem rozmiaru i proporcji, aby uzyskać profesjonalny wygląd.
-   **Scenariusz/przykład dla sprzedawcy:** Wprowadzasz nową kolekcję letnią. Dodasz trzy slajdy: jeden dla sukienek, jeden dla strojów kąpielowych i jeden dla akcesoriów. Każdy slajd będzie zawierał obraz główny, podpis, np. „Kup sukienki letnie teraz!”, i link bezpośrednio do odpowiedniej strony kategorii. Slajd ze strojami kąpielowymi możesz animować „kostką” dla zabawnego efektu, podczas gdy inne użyją „zanikania”.

#### **Wybór haka (Hook Selection)**

-   **Co robi to ustawienie:** Pozwala wybrać, gdzie w Twoim sklepie PrestaShop slider będzie wyświetlany.
-   **Efekt zmiany tego ustawienia:** Wybierając hak (np. `displayHeader`, `displayLeftColumn`), moduł wstrzyknie kod slidera w ten konkretny obszar Twojego motywu.
-   **Zalecana wartość:**
    -   Dla widocznego banera na całą szerokość: `displayHeader` lub niestandardowy hak dostarczony przez Twój motyw dla górnych banerów.
    -   Dla mniejszego, kontekstowego slidera: `displayLeftColumn` lub `displayRightColumn`.
    -   Dla sliderów specyficznych dla produktu: `displayProductExtraContent` lub `displayProductButtons`.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby Twój główny slider promocyjny pojawiał się tuż pod głównym menu Twojej witryny. Wybrałbyś hak `displayHeader` (lub podobny hak specyficzny dla motywu, jeśli jest dostępny). Jeśli chciałbyś mniejszy slider pokazujący „powiązane produkty” z boku, wybrałbyś `displayLeftColumn`.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Szerokość slidera | `100%` / `1140px` | Ustawia rozmiar poziomy slidera. |
| Konfiguracja modułu | Wysokość slidera | `400px` | Ustawia rozmiar pionowy slidera. |
| Konfiguracja modułu | Typ animacji | `fade` / `slice` | Definiuje wizualne przejście między slajdami (40 opcji). |
| Konfiguracja modułu | Prędkość animacji | `800` (ms) | Jak szybko następuje przejście animacji. |
| Konfiguracja modułu | Interwał slajdów | `5000` (ms) | Jak długo każdy slajd jest widoczny przed zmianą. |
| Konfiguracja modułu | Strzałki nawigacyjne | `TAK` | Wyświetla strzałki w lewo/prawo do ręcznej nawigacji. |
| Konfiguracja modułu | Kropki/punkty nawigacyjne | `TAK` | Wyświetla kropki/punkty do bezpośredniego wyboru slajdu. |
| Konfiguracja modułu | Miniatury | `NIE` | Wyświetla małe obrazy podglądu każdego slajdu. |
| Konfiguracja modułu | Podgląd miniatur | `TAK` | Pokazuje większy podgląd po najechaniu kursorem na miniaturę (jeśli włączone). |
| Konfiguracja modułu | Wyświetlanie podpisów | `TAK` | Kontroluje widoczność podpisów tekstowych na slajdach. |
| Konfiguracja modułu | Dodaj/Edytuj slajd | N/A | Prześlij obraz, ustaw link, podpis i indywidualną animację. |
| Konfiguracja modułu | Wybór haka | `displayHeader` | Określa, gdzie slider pojawia się w Twoim sklepie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój slider nie wyświetla się po konfiguracji. Co powinienem zrobić?**
O:

1.  **Sprawdź wybór haka:** Wróć do konfiguracji modułu i upewnij się, że wybrałeś co najmniej jeden hak (np. `displayHeader`).
2.  **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
3.  **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły, które mogą używać tego samego haka lub modyfikować te same obszary strony (zwłaszcza inne moduły sliderów).
4.  **Kompatybilność z motywem:** Niektóre bardzo spersonalizowane motywy mogą wymagać drobnych dostosowań. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P: Moje obrazy wyglądają na rozmyte lub rozciągnięte w sliderze.**
O: Zazwyczaj oznacza to, że Twoje obrazy nie mają prawidłowych wymiarów lub rozdzielczości dla ustawień slidera.

1.  **Spójne wymiary:** Upewnij się, że wszystkie obrazy przesłane do slajdów mają taką samą szerokość i wysokość.
2.  **Wysoka rozdzielczość:** Prześlij obrazy o wystarczającej rozdzielczości. Jeśli Twój slider ma `1140px` szerokości, Twoje obrazy powinny mieć co najmniej `1140px` szerokości.
3.  **Proporcje:** Dopasuj proporcje swoich obrazów do skonfigurowanej szerokości i wysokości slidera. Jeśli Twój slider ma `1140x400px`, spróbuj użyć obrazów o podobnych proporcjach 114:40.

**P: Jak przetłumaczyć podpisy do moich slajdów na różne języki?**
O: Moduł powinien obsługiwać standardowy system tłumaczeń PrestaShop.

1.  Przejdź do **Lokalizacja > Tłumaczenia**.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”, swój motyw i język, na który chcesz tłumaczyć.
3.  Znajdź moduł „Prestashop Slider” na liście. Powinieneś być w stanie edytować podpisy dla każdego slajdu bezpośrednio tam. Jeśli nie, moduł może przechowywać podpisy bezpośrednio w bazie danych, co wymaga edycji każdego slajdu dla każdego języka w konfiguracji modułu.

**P: Slider wygląda dobrze na komputerze stacjonarnym, ale jest uszkodzony na urządzeniach mobilnych.**
O:

1.  **Sprawdź responsywność:** Moduł jest zaprojektowany tak, aby był responsywny. Upewnij się, że Twój motyw sam w sobie jest responsywny.
2.  **Konflikty CSS:** Inny moduł lub CSS Twojego motywu może nadpisywać responsywne style slidera. Użyj narzędzi deweloperskich przeglądarki, aby zbadać slider na urządzeniach mobilnych i poszukać konfliktowych reguł CSS.
3.  **Rozmiar obrazu:** Bardzo duże obrazy mogą czasami powodować problemy na urządzeniach mobilnych. Upewnij się, że obrazy są zoptymalizowane.

**P: Czy mogę mieć wiele sliderów na różnych stronach?**
O: Obecna konfiguracja modułu zazwyczaj zarządza jedną główną instancją slidera z jej zestawem slajdów. Jeśli potrzebujesz wielu *różnych* sliderów z różną zawartością i ustawieniami na różnych stronach, być może będziesz musiał zduplikować moduł (jeśli Twój motyw na to pozwala) lub użyć bardziej zaawansowanego rozwiązania slidera. Dla tego modułu skonfigurujesz jeden slider i wybierzesz jego umiejscowienie za pomocą haków.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu Prestashop Slider, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `Prestashop Slider` (`pslider`) to standardowy moduł PrestaShop, który głównie wykorzystuje klasę `Module`. Zarządza swoją konfiguracją i danymi slajdów bezpośrednio w tabeli `ps_configuration`. Wyświetlanie w front-office jest obsługiwane przez szablony Smarty renderowane za pośrednictwem systemu haków PrestaShop, wstrzykując zasoby JavaScript i CSS dla funkcjonalności slidera. Moduł wykorzystuje wtyczkę jQuery `Skitter` do swoich możliwości animacji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje niestandardowych klas rozszerzających `ObjectModel`. Wszystkie dane konfiguracyjne i slajdów są przechowywane jako serializowane tablice w tabeli `ps_configuration`, zarządzane bezpośrednio przez klasę `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł opiera się na wtyczce jQuery Skitter dla swojej funkcjonalności slidera.

-   `pslider/js/jquery.easing.1.3.js`:
    -   **Zakres:** Front-office.
    -   **Cel:** Zapewnia zaawansowane funkcje easing dla animacji jQuery, zwiększając wizualną płynność przejść używanych przez wtyczkę Skitter.
-   `pslider/js/jquery.skitter.js`:
    -   **Zakres:** Front-office.
    -   **Cel:** To jest podstawowa wtyczka slidera Skitter. Inicjuje slider, obsługuje przejścia slajdów, nawigację i responsywność. Odczytuje opcje konfiguracji (typ animacji, prędkość, interwał itp.) z ustawień modułu i stosuje je do instancji slidera.
-   `pslider/js/noconflict.js`:
    -   **Zakres:** Front-office.
    -   **Cel:** Zapewnia, że jQuery działa w trybie `noConflict()`, zapobiegając konfliktom z innymi bibliotekami JavaScript (takimi jak Prototype.js, które PrestaShop 1.6 i wcześniejsze czasami używały), które również mogą używać aliasu `$`. Jest to kluczowe dla kompatybilności.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera pojedynczy plik CSS do stylizacji slidera Skitter.

-   `pslider/css/skitter.styles.css`:
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Cel:** Zawiera wszystkie domyślne style wizualne dla slidera Skitter, w tym:
        -   Układ kontenera slidera (`.box_skitter`).
        -   Stylizacja elementów nawigacyjnych (strzałki, kropki, miniatury).
        -   Domyślny wygląd podpisów.
        -   Responsywne dostosowania.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:**
        -   `.box_skitter`: Główny kontener slidera.
        -   `.box_skitter ul`: Lista slajdów.
        -   `.box_skitter .info_slide`: Kontener podpisu.
        -   `.box_skitter .nav_cont`: Kontener nawigacji.
        -   `.box_skitter .prev_button`, `.box_skitter .next_button`: Strzałki nawigacyjne.
        -   `.box_skitter .info_slide_dots`: Kropki nawigacyjne.
        -   `.box_skitter .box_thumbs`: Kontener miniatur.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje szablony Smarty do renderowania treści front-office i części konfiguracji back-office.

-   **Szablony haków (`views/templates/hook/`)**:

    -   `pslider/header.tpl`: Ten szablon jest prawdopodobnie przeznaczony do podłączenia do `displayHeader` lub podobnego haka na górze strony. Zawiera główną strukturę HTML dla slidera i często zawiera niezbędny kod inicjalizacyjny JavaScript dla wtyczki Skitter.
    -   `pslider/top.tpl`: Podobnie do `header.tpl`, ten może być używany dla innego haka najwyższego poziomu, potencjalnie `displayTop` lub innego haka banerowego specyficznego dla motywu. Również zawierałby HTML i inicjalizację JS slidera.
    -   `pslider/views/templates/hook/left-column.tpl`: Ten szablon jest specjalnie zaprojektowany do umieszczenia w haku `displayLeftColumn`. Zawierałby mniejszą, potencjalnie inną instancję slidera lub zmodyfikowany układ odpowiedni dla paska bocznego.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `pslider/views/templates/front/form.tpl`: Pomimo tego, że znajduje się w `views/templates/front/`, ten plik jest faktycznie używany do formularza konfiguracji modułu w Panelu administracyjnym. Definiuje strukturę HTML dla pól ustawień (szerokość, wysokość, animacja, zarządzanie slajdami itp.), z którymi sprzedawca wchodzi w interakcję. Jest to renderowane przez metodę `getContent()` w `ajax_pslider.php`.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Wszystkie ustawienia konfiguracyjne i dane slajdów (ścieżki obrazów, linki, podpisy, indywidualne typy animacji) są przechowywane jako serializowane tablice w tabeli `ps_configuration`. Nazwy kluczy zazwyczaj będą zgodne z wzorcem, takim jak `PSLIDER_WIDTH`, `PSLIDER_SLIDES` itp.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` strony front-office lub na samym początku `<body>`. | Wstrzykuje zasoby CSS i JavaScript, a potencjalnie główną strukturę HTML slidera. |
| `displayTop` | Renderuje się na górze treści strony, zazwyczaj powyżej głównego obszaru treści, ale poniżej nagłówka. | Wyświetla główny baner slidera. |
| `displayLeftColumn` | Renderuje się w lewym pasku bocznym strony front-office. | Wyświetla slider specyficzny dla paska bocznego. |
| `displayRightColumn` | Renderuje się w prawym pasku bocznym strony front-office. | Wyświetla slider specyficzny dla paska bocznego. |
| `displayFooter` | Renderuje się w sekcji stopki strony front-office. | Wyświetla slider specyficzny dla stopki. |
| `displayProductExtraContent` | Renderuje się na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Wyświetla slidery związane z produktem (np. alternatywne widoki, funkcje). |
| `displayProductButtons` | Renderuje się w pobliżu przycisku „Dodaj do koszyka” na stronie produktu. | Może być używany do małych, kontekstowych sliderów związanych z produktem. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje zasoby multimedialne. | Pozwala modułowi warunkowo rejestrować swoje pliki JS i CSS. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Prestashop Slider, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
