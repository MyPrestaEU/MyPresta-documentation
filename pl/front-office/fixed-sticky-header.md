---
title: "Stały, przyklejony nagłówek - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Stały, przyklejony nagłówek” od MyPresta.eu."
sidebar:
  label: "Stały, przyklejony nagłówek - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Fixed sticky header na MyPresta.eu](https://mypresta.eu/modules/front-office-features/fixed-sticky-header.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/fixed-sticky-header/)
>
> ---


# Stały, przyklejony nagłówek

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Moduł działa z domyślnymi szablonami bootstrap i classic oraz ze wszystkimi motywami o podobnej strukturze.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Stały, przyklejony nagłówek” w Menedżerze modułów. Spowoduje to przejście do głównej strony konfiguracji modułu.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera standardowe ustawienia modułów MyPresta.eu dotyczące aktualizacji i wsparcia.
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy włączone:* Pozwala modułowi sprawdzać dostępne aktualizacje z MyPresta.eu i potencjalnie wyświetlać powiadomienia w Twoim Panelu administracyjnym. Zapewnia to, że zawsze używasz najnowszej, najbezpieczniejszej i najbardziej funkcjonalnej wersji modułu.
    -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał aktualizacji. Musiałbyś ręcznie sprawdzać nowe wersje, logując się na swoje konto MyPresta.eu.
-   **Zalecana wartość:** **TAK** (lub włączone). Utrzymywanie tego ustawienia aktywnego jest wysoce zalecane, aby zapewnić otrzymywanie terminowych aktualizacji i poprawek błędów, które są kluczowe dla bezpieczeństwa i kompatybilności z przyszłymi wersjami PrestaShop.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz być powiadamiany, jeśli zostanie wydana nowa wersja modułu, która naprawia błąd lub dodaje nową funkcję. Utrzymywanie tego włączonego zapewnia, że zawsze jesteś informowany.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Sprawdzanie aktualizacji (mypresta\_updates, update\_, updatev\_) | Włączone | Pozwala modułowi sprawdzać i powiadamiać o dostępnych aktualizacjach z MyPresta.eu, zapewniając najnowsze funkcje i poprawki bezpieczeństwa. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Nagłówek się nie przykleja lub nakłada na inne elementy. Co powinienem zrobić?**
O1: Często dzieje się tak z powodu konfliktów z CSS lub JavaScriptem Twojego motywu, zwłaszcza jeśli Twój motyw ma bardzo niestandardową strukturę nagłówka.
\* **Wyczyść pamięć podręczną:** Najpierw spróbuj wyczyścić pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
\* **Kompatybilność motywu:** Moduł jest zaprojektowany do pracy ze standardowymi motywami PrestaShop (takimi jak Classic) i motywami o podobnych strukturach. Jeśli masz mocno dostosowany motyw, mogą być potrzebne drobne korekty CSS.
\* **Skontaktuj się z pomocą techniczną:** Jeśli problem nadal występuje, zbierz zrzuty ekranu i szczegóły dotyczące Twojego motywu, a następnie skontaktuj się z pomocą techniczną MyPresta.eu. Mogą pomóc w diagnozie i dostarczyć niestandardowe fragmenty CSS, jeśli zajdzie taka potrzeba.

**P2: Mój nagłówek wygląda dziwnie lub ma dodatkową przestrzeń, gdy staje się przyklejony.**
O2: Może to być problem ze stylizacją.
\* **Sprawdź element:** Użyj narzędzi deweloperskich przeglądarki (kliknij prawym przyciskiem myszy na nagłówku i wybierz „Zbadaj”), aby zobaczyć, jakie reguły CSS są stosowane. Szukaj `position: fixed;` i `top: 0;`.
\* **Stylizacja motywu:** Twój motyw może mieć specyficzne reguły dotyczące dopełnienia lub marginesów, które kolidują. Może być konieczne dodanie niestandardowego CSS, aby dostosować wygląd przyklejonego nagłówka. Pomoc techniczna MyPresta.eu może Cię w tym pokierować.

**P3: Czy ten moduł spowolni moją stronę internetową?**
A3: Moduł „Stały, przyklejony nagłówek” jest bardzo lekki, wykorzystuje minimalną ilość JavaScriptu i CSS. Powinien mieć znikomy wpływ na szybkość ładowania i wydajność Twojej strony internetowej. Efekt jest aktywowany tylko podczas przewijania, więc nie dodaje narzutu do początkowego ładowania strony.

**P4: Jak przetłumaczyć moduł, jeśli miałby jakiś widoczny tekst?**
A4: Chociaż ten moduł przede wszystkim zapewnia efekt wizualny i zazwyczaj nie zawiera tekstu widocznego dla użytkownika, jeśli jakakolwiek przyszła wersja wprowadzi konfigurowalny tekst, przetłumaczyłbyś go za pomocą:
\* **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
\* Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Stały, przyklejony nagłówek” z rozwijanej listy modułów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Stały, przyklejony nagłówek” to lekki moduł funkcji front-office zaprojektowany w celu poprawy doświadczenia użytkownika poprzez uczynienie głównego nagłówka przyklejonym podczas przewijania. Wykorzystuje on głównie JavaScript do wykrywania zdarzeń przewijania i stosowania klas CSS do elementu nagłówka, co następnie wyzwala styl `position: fixed`. Przestrzega standardowej struktury modułu PrestaShop, wykorzystując hook `displayHeader` do wstrzykiwania swoich zasobów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Funkcjonalność modułu jest w całości obsługiwana przez JavaScript wstrzykiwany za pomocą hooka.
-   **Kontrolery Back-Office Admin**: Brak. Konfiguracja jest zarządzana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   Nie użyto żadnych niestandardowych klas ani definicji `ObjectModel`. Moduł działa poprzez manipulowanie istniejącymi elementami DOM.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`fixedheader/fixedheader.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten skrypt odpowiada za podstawową funkcjonalność przyklejonego nagłówka.
    -   **Szczegóły:**
        -   Nasłuchuje zdarzenia `scroll` na obiekcie `window`.
        -   Określa pozycję przewijania i początkowe przesunięcie elementu nagłówka.
        -   Gdy użytkownik przewinie poza określony próg (początkową wysokość nagłówka), dodaje określoną klasę CSS (np. `fixed-header-active` lub podobną, zdefiniowaną w `fixedheader.css`) do głównego kontenera nagłówka.
        -   Gdy użytkownik przewinie z powrotem powyżej progu, usuwa tę klasę.
        -   Prawdopodobnie celuje w wspólny selektor nagłówka (np. `#header`, `.header-container` lub podobny, w zależności od struktury motywu), aby zastosować zachowanie przyklejania.
        -   Może również obsługiwać dodawanie `padding-top` do `body` lub głównego opakowania treści, aby zapobiec „skakaniu” treści lub ukrywaniu się za stałym nagłówkiem.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`fixedheader/fixedheader.css`**
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Cel:** Zapewnia niezbędne reguły CSS, aby nagłówek był przyklejony, gdy JavaScript dodaje klasę aktywacji.
    -   **Szczegóły:**
        -   Definiuje style dla aktywnego stanu przyklejonego nagłówka. Kluczowe właściwości będą obejmować:
            -   `position: fixed;`
            -   `top: 0;`
            -   `width: 100%;`
            -   `z-index: 1000;` (lub wysoką wartość, aby upewnić się, że pozostaje nad inną zawartością).
            -   Potencjalnie `box-shadow` lub `background-color`, aby wizualnie odróżnić przyklejony nagłówek.
        -   Może również zawierać reguły do obsługi dopełnienia lub marginesu `body`, aby zapobiec nakładaniu się treści.
        -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Główna klasa dodana przez JS (np. `.fixed-header-active` lub podobna) i selektor dla samego elementu nagłówka (np. `#header`, `.header-container`). Programiści mogą nadpisać te style w niestandardowym CSS swojego motywu, aby dopasować je do swojego projektu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   Nie użyto niestandardowych plików `.tpl`. Moduł wstrzykuje swój JavaScript i CSS bezpośrednio do sekcji `<head>` za pomocą hooka `displayHeader`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Nie są tworzone żadne niestandardowe tabele bazy danych. Konfiguracja jest przechowywana w `ps_configuration` przy użyciu kluczy takich jak `MYPRESTA_UPDATES`, `UPDATE_FIXEDHEADER`, `UPDATEV_FIXEDHEADER`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS (`fixedheader.css`) i JavaScript (`fixedheader.js`) modułu do strony, zapewniając ich załadowanie przed renderowaniem zawartości strony i dostępność do natychmiastowego wykonania. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Stały, przyklejony nagłówek” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
