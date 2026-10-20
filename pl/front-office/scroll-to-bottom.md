---
title: "Przewiń do dołu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Przewiń do dołu” od MyPresta.eu."
sidebar:
  label: "Przewiń do dołu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Scroll to bottom na MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-bottom.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/scroll-to-bottom/)
>
> ---


# Przewiń do dołu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Przewiń do dołu”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Przewiń do dołu”, a następnie klikając przycisk „Konfiguruj”.

#### Ustawienia i opcje

-   **Kolor przycisku (st\_color)**

    -   **Co robi to ustawienie:** Pozwala zdefiniować kolor przycisku „Przewiń do dołu”. Możesz użyć standardowych nazw kolorów HTML (takich jak `red`, `blue`, `green`) lub szesnastkowych kodów kolorów (takich jak `#FF0000` dla czerwonego, `#0000FF` dla niebieskiego).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony na konkretny kolor (np. `#007bff`):* Przycisk wyświetli się w dokładnie tym kolorze w Twoim front office.
        -   *Gdy pozostawiony pusty lub nieprawidłowy:* Przycisk prawdopodobnie powróci do domyślnego koloru zdefiniowanego przez CSS modułu, który może nie pasować do Twojej marki.
    -   **Zalecana wartość:** Wybierz kolor, który uzupełnia projekt Twojego sklepu i jest wyraźnie widoczny na tle, ale nie jest zbyt rozpraszający. Użyj głównego lub drugorzędnego koloru swojej marki.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja marka używa dużo ciemnego niebieskiego, ustawienie tego na `#000080` (granatowy) sprawi, że przycisk będzie ładnie się komponował, pozostając jednocześnie funkcjonalnym.
-   **Pozycja X przycisku (st\_x)**

    -   **Co robi to ustawienie:** Kontroluje poziomą pozycję przycisku na ekranie. Określa, jak daleko od prawej krawędzi okna przeglądarki pojawi się przycisk. Wartość jest zazwyczaj podawana w pikselach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony na niższą wartość (np. `20`):* Przycisk będzie bliżej prawej krawędzi ekranu.
        -   *Gdy ustawiony na wyższą wartość (np. `80`):* Przycisk będzie dalej od prawej krawędzi, przesuwając się w kierunku środka ekranu.
    -   **Zalecana wartość:** `20` lub `30` pikseli to powszechne i nieinwazyjne umiejscowienie. Utrzymuje to przycisk poza głównym obszarem treści, ale nadal łatwo dostępnym.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz inne stałe elementy po prawej stronie ekranu (takie jak widżet czatu), możesz potrzebować zwiększyć tę wartość do `50px`, aby zapobiec nakładaniu się przycisku „Przewiń do dołu”.
-   **Pozycja Y przycisku (st\_y)**

    -   **Co robi to ustawienie:** Kontroluje pionową pozycję przycisku na ekranie. Określa, jak daleko od górnej krawędzi okna przeglądarki pojawi się przycisk. Wartość jest zazwyczaj podawana w pikselach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony na niższą wartość (np. `20`):* Przycisk będzie bliżej górnej krawędzi ekranu.
        -   *Gdy ustawiony na wyższą wartość (np. `80`):* Przycisk będzie dalej od górnej krawędzi.
    -   **Zalecana wartość:** `20` lub `30` pikseli to dobry punkt wyjścia. Umieszcza go w prawym górnym rogu, nie będąc ani za wysoko, ani za nisko.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli nagłówek Twojego sklepu jest bardzo wysoki lub masz przycisk „Przewiń do góry” również w prawym górnym rogu, możesz dostosować to do `60px` lub `70px`, aby upewnić się, że oba przyciski mają wystarczająco dużo miejsca i nie nakładają się.
-   **Przezroczystość przycisku (st\_o)**

    -   **Co robi to ustawienie:** Kontroluje przezroczystość przycisku. Wartości przezroczystości wahają się od `0` (całkowicie przezroczysty/niewidoczny) do `1` (całkowicie nieprzezroczysty/solidny). Możesz użyć wartości dziesiętnych, takich jak `0.5` dla 50% przezroczystości.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiony na `1`:* Przycisk będzie w pełni widoczny i solidny.
        -   *Gdy ustawiony na `0.5`:* Przycisk będzie półprzezroczysty, umożliwiając widoczność treści w tle.
        -   *Gdy ustawiony na `0`:* Przycisk będzie niewidoczny (choć nadal klikalny, jeśli wiesz, gdzie się znajduje).
    -   **Zalecana wartość:** `0.8` lub `0.9` to często dobry balans. Sprawia, że przycisk jest nieco mniej inwazyjny, jednocześnie pozostając wyraźnie widocznym. `1` jest również całkowicie w porządku, jeśli chcesz, aby bardziej się wyróżniał.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli uważasz, że przycisk jest zbyt widoczny lub rozpraszający, zmniejszenie jego przezroczystości do `0.7` może sprawić, że będzie się bardziej subtelnie komponował z projektem Twojego sklepu, nie tracąc swojej funkcjonalności.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Kolor przycisku (st\_color) | `#007bff` (przykład) | Ustawia kolor przycisku. Wpływa na widoczność i spójność marki. |
| Konfiguracja modułu | Pozycja X przycisku (st\_x) | `20` | Pozioma odległość od prawej krawędzi. Zapobiega nakładaniu się z innymi elementami. |
| Konfiguracja modułu | Pozycja Y przycisku (st\_y) | `20` | Pionowa odległość od górnej krawędzi. Wyraźnie pozycjonuje przycisk. |
| Konfiguracja modułu | Przezroczystość przycisku (st\_o) | `0.8` | Przezroczystość przycisku. Kontroluje, jak inwazyjny lub subtelny się wydaje. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

-   **P: Przycisk nie wyświetla się w moim sklepie.**
    -   **O:** Najpierw upewnij się, że moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**. Następnie sprawdź stronę konfiguracji modułu, aby upewnić się, że wszystkie ustawienia są zapisane. Jeśli nadal się nie pojawia, spróbuj wyczyścić pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Czasami niestandardowe szablony mogą również zakłócać działanie; tymczasowo przełącz się na domyślny szablon PrestaShop, aby to wykluczyć.
-   **P: Przycisk wyświetla się, ale jest w złym miejscu lub wygląda dziwnie.**
    -   **O:** Przejdź do strony konfiguracji modułu. Dostosuj ustawienia „Pozycja X” i „Pozycja Y”, aby przesunąć przycisk poziomo i pionowo. Eksperymentuj z różnymi wartościami, aż znajdzie się w zadowalającej lokalizacji. W przypadku problemów z wyglądem sprawdź ustawienia „Kolor” i „Przezroczystość”. Jeśli nadal wygląda źle, CSS Twojego szablonu może nadpisywać style modułu.
-   **P: Animacja przewijania nie jest płynna lub nie działa.**
    -   **O:** Ten moduł używa JavaScript do płynnego efektu przewijania. Upewnij się, że na Twojej stronie nie ma błędów JavaScript (możesz sprawdzić konsolę programisty przeglądarki pod kątem błędów). Konflikty z innymi modułami lub niestandardowym JavaScriptem szablonu mogą czasami uniemożliwić prawidłowe działanie animacji. Wyczyść pamięć podręczną to dobry pierwszy krok.
-   **P: Czy mogę zmienić ikonę przycisku?**
    -   **O:** Obecna wersja modułu nie oferuje bezpośredniego ustawienia zmiany ikony z panelu administracyjnego. Wymagałoby to niestandardowego CSS lub modyfikacji szablonu (więcej szczegółów technicznych znajdziesz w Przewodniku dla programistów).
-   **P: Czy ten moduł wpływa na wydajność mojego sklepu lub SEO?**
    -   **O:** Ten moduł jest bardzo lekki, dodaje minimalny CSS i JavaScript. Powinien mieć znikomy wpływ na szybkość ładowania Twojego sklepu lub SEO. Funkcjonalność służy wyłącznie poprawie doświadczenia użytkownika i nie zmienia treści w sposób, który wpływałby na indeksowanie przez wyszukiwarki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Przewiń do dołu” to prosta funkcja front-office zaimplementowana jako standardowy moduł PrestaShop. Wykorzystuje głównie system hooków PrestaShop do wstrzykiwania swojego CSS, JavaScriptu i struktury HTML przycisku do front office. Konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`. Nie ma niestandardowych kontrolerów, ObjectModels ani złożonych interakcji z bazą danych.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Funkcjonalność front-office modułu jest wstrzykiwana bezpośrednio za pomocą hooków.
-   **Kontrolery Back-Office Admin**: Brak. Konfiguracja jest obsługiwana w głównym pliku modułu.

### 4.3 Główne klasy i modele (`classes/`)

-   Brak. Moduł nie definiuje żadnych niestandardowych klas ani ObjectModels. Cała logika zawarta jest w `scrollbottom.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `scrollbottom/scrollbottom.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Ten skrypt odpowiada za podstawową funkcjonalność przycisku „Przewiń do dołu”.
        -   Prawdopodobnie nasłuchuje gotowości DOM.
        -   Dołącza nasłuch zdarzeń kliknięcia do elementu przycisku „Przewiń do dołu”.
        -   Po kliknięciu używa metody JavaScript `window.scrollTo()` lub `element.scrollIntoView()`, często z `behavior: 'smooth'`, aby animować przewijanie do dołu strony (konkretnie do maksymalnej wysokości przewijania elementu `body` lub `html`).
        -   Może również obsługiwać widoczność przycisku, sprawiając, że pojawia się lub znika w zależności od pozycji przewijania użytkownika (np. wyświetla się tylko, gdy użytkownik przewinął w dół o określoną wartość).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `scrollbottom/scrollbottom.css`
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Główne komponenty UI i kontenery, które stylizuje:** Ten arkusz stylów definiuje wygląd wizualny i pozycjonowanie przycisku „Przewiń do dołu”.
        -   Prawdopodobnie będzie celował w konkretny ID lub klasę dla przycisku (np. `#scrollbottom_button`).
        -   Definiuje właściwości takie jak `position: fixed`, `right`, `top`, `z-index`, `background-color`, `color`, `padding`, `border-radius`, `cursor` i potencjalnie `display: none` początkowo, z JavaScriptem kontrolującym jego widoczność.
        -   Może również zawierać style dla ikony strzałki wewnątrz przycisku (np. używając ikony czcionki lub obrazu tła).
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim szablonie:** Programiści mogą sprawdzić wygenerowany HTML, aby znaleźć dokładny ID/klasę przycisku (np. `#scrollbottom_button`) i nadpisać jego style w pliku `custom.css` swojego szablonu lub równoważnym pliku, aby uzyskać niestandardowy wygląd.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `scrollbottom/adv.tpl`: Ten szablon jest prawdopodobnie używany do wyświetlania reklamy lub treści promocyjnych związanych z MyPresta.eu, często wstrzykiwany do hooka takiego jak `displayAdminHome` lub podobnego, ale nie jest bezpośrednio związany z funkcjonalnością przycisku front-office.
    -   `scrollbottom/footer.tpl`: To jest główny szablon dla przycisku front-office.
        -   **Podłączony do:** `displayFooter` lub `footer` (w zależności od wersji PrestaShop i szablonu).
        -   **Wyjścia:** Struktura HTML dla przycisku „Przewiń do dołu”, w tym jego ID/klasa, ikona strzałki i potencjalnie style inline lub atrybuty danych pochodzące z ustawień konfiguracji modułu (kolor, pozycja, przezroczystość).
-   **Szablony administracyjne (`views/templates/admin/`)**: Brak.
-   **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `ST_COLOR`, `ST_X`, `ST_Y`, `ST_O`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` front office. | Używany do rejestrowania i dołączania plików CSS (`scrollbottom.css`) i JavaScript (`scrollbottom.js`) modułu, zapewniając ich załadowanie przed treścią strony. |
| `header` | Alias dla `displayHeader` w niektórych kontekstach. | To samo co `displayHeader`. |
| `displayFooter` | Na końcu sekcji `<body>`, przed zamykającym tagiem `</body>`. | Używany do renderowania szablonu `footer.tpl`, który zawiera strukturę HTML dla przycisku „Przewiń do dołu”. |
| `footer` | Alias dla `displayFooter` w niektórych kontekstach. | To samo co `displayFooter`. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Przewiń do dołu”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
