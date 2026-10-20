---
title: "Peeling Corner Banner - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Peeling Corner Banner od MyPresta.eu."
sidebar:
  label: "Peeling Corner Banner - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Peeling Corner Banner na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/peeling-corner-banner.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/peeling-corner-banner/)
>
> ---


# Peeling Corner Banner

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień. Tutaj dostosujesz wygląd i zachowanie swojego banera z efektem odklejania.

#### **Obrazek dla rogu (Mały obrazek)**

-   **Co robi to ustawienie:** Jest to mały obrazek, który pojawia się na zwiniętym rogu Twojej strony. To początkowa zapowiedź, która przyciąga wzrok klienta.
-   **Efekt zmiany tego ustawienia:**
    *   *Po przesłaniu obrazka:* Ten obrazek zostanie wyświetlony na małym, zwiniętym rogu.
    *   *Gdy nie przesłano obrazka:* Róg może pojawić się pusty lub użyć domyślnego stylu, co jest mniej efektywne.
-   **Zalecana wartość:** Prześlij mały, atrakcyjny obrazek (np. małą ikonę, etykietę „Wyprzedaż” lub fragment logo), który sugeruje promocję, nie ujawniając wszystkiego.
-   **Scenariusz/przykład dla sprzedawcy:** Prowadzisz letnią wyprzedaż. Możesz przesłać mały obrazek ikony słońca lub małą plakietkę „WYPRZEDAŻ” do tego ustawienia.

#### **Obrazek dla banera (Duży obrazek)**

-   **Co robi to ustawienie:** Jest to główny obraz banera, który jest ujawniany, gdy klient najedzie myszką na róg. Tutaj powinna znajdować się Twoja główna wiadomość, obraz produktu lub wezwanie do działania.
-   **Efekt zmiany tego ustawienia:**
    *   *Po przesłaniu obrazka:* Ten większy obraz zostanie wyświetlony, gdy róg się odwinie.
    *   *Gdy nie przesłano obrazka:* Odsłonięty obszar będzie pusty, co sprawi, że moduł będzie nieskuteczny.
-   **Zalecana wartość:** Prześlij wyraźny, przekonujący obraz, który zawiera pełną wiadomość promocyjną, zdjęcie produktu lub silne wezwanie do działania. Upewnij się, że ma odpowiedni rozmiar dla banera (np. 200-300px szerokości, podobna wysokość).
-   **Scenariusz/przykład dla sprzedawcy:** Kontynuując przykład letniej wyprzedaży, ten obraz byłby pełnym banerem ogłaszającym „Letnia wyprzedaż! Do 50% zniżki na wszystkie stroje kąpielowe!” z atrakcyjnymi zdjęciami produktów.

#### **Link dla banera**

-   **Co robi to ustawienie:** Jest to adres URL (adres internetowy), na który klienci zostaną przekierowani po kliknięciu odsłoniętego banera.
-   **Efekt zmiany tego ustawienia:**
    *   *Po wprowadzeniu prawidłowego adresu URL:* Kliknięcie banera przeniesie klienta na tę stronę.
    *   *Gdy pozostawiono puste lub wprowadzono nieprawidłowy adres URL:* Kliknięcie banera może nic nie zrobić lub prowadzić do strony błędu, frustrując klientów.
-   **Zalecana wartość:** Zawsze podawaj pełny, prawidłowy adres URL (np. `https://twojskep.com/kategoria-letnia-wyprzedaz`).
-   **Scenariusz/przykład dla sprzedawcy:** Możesz połączyć to z dedykowaną stroną kategorii „Letnia wyprzedaż” lub konkretną stroną produktu, którą chcesz wyróżnić.

#### **Pozycja banera**

-   **Co robi to ustawienie:** Kontroluje, w którym rogu Twojej witryny pojawi się baner z efektem odklejania.
-   **Efekt zmiany tego ustawienia:**
    *   *Lewo:* Baner pojawi się w lewym górnym rogu okna przeglądarki.
    *   *Prawo:* Baner pojawi się w prawym górnym rogu okna przeglądarki.
-   **Zalecana wartość:** Wybierz róg, który najlepiej pasuje do projektu Twojej witryny i nie zasłania ważnych elementów. „Prawo” jest często dobrym ustawieniem domyślnym, ponieważ rzadziej znajdują się tam nawigacja lub logo.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje główne logo i nawigacja znajdują się po lewej stronie, wybierzesz „Prawo”, aby uniknąć wizualnego bałaganu.

#### **Włącz/Wyłącz moduł**

-   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcji banera z efektem odklejania bez odinstalowywania modułu.
-   **Efekt zmiany tego ustawienia:**
    *   *Włączony:* Baner z efektem odklejania będzie widoczny w Twoim front office zgodnie z innymi ustawieniami.
    *   *Wyłączony:* Baner z efektem odklejania nie pojawi się w Twoim front office.
-   **Zalecana wartość:** „Włączony”, gdy chcesz używać banera, „Wyłączony”, jeśli musisz tymczasowo go ukryć w celu konserwacji lub w określonych okresach.
-   **Scenariusz/przykład dla sprzedawcy:** Zakończyłeś promocję świąteczną i chcesz tymczasowo ukryć baner do następnej kampanii. Wyłączyłbyś go tutaj.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Obrazek dla rogu | Prześlij mały obrazek zapowiedzi | Mały obrazek na zwiniętym rogu. Przyciąga uwagę. |
| Konfiguracja modułu | Obrazek dla banera | Prześlij większy obrazek promocyjny | Główny obraz banera ujawniany po najechaniu. Zawiera główną wiadomość. |
| Konfiguracja modułu | Link dla banera | Pełny adres URL (np. `https://twojskep.com/promocja`) | Docelowy adres URL po kliknięciu banera. Kieruje ruch. |
| Konfiguracja modułu | Pozycja banera | Prawo | W którym rogu ekranu pojawia się baner (Lewo/Prawo). |
| Konfiguracja modułu | Włącz/Wyłącz moduł | Włączony | Główny przełącznik do pokazywania lub ukrywania banera w sklepie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój baner nie wyświetla się po konfiguracji. Co powinienem zrobić?**
O:

1.  **Sprawdź „Włącz/Wyłącz moduł”:** Upewnij się, że moduł jest włączony w jego konfiguracji.
2.  **Zweryfikuj przesłane obrazy:** Upewnij się, że zarówno „Obrazek dla rogu”, jak i „Obrazek dla banera” zostały pomyślnie przesłane.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają wyświetlanie nowej zawartości modułu.
4.  **Hook modułu:** Moduł powinien automatycznie zaczepić się w `displayHeader`. Jeśli się nie wyświetla, upewnij się, że jest poprawnie zaczepiony. Możesz to sprawdzić w **Wygląd > Pozycje** (lub **Moduły > Pozycje**). Wyszukaj `peelingcornerbanner` i potwierdź, że jest powiązany z `displayHeader`.

**P: Obrazy banera wyglądają na rozmyte lub rozciągnięte.**
O: Zazwyczaj oznacza to, że przesłane obrazy nie są zoptymalizowane pod kątem rozmiaru wyświetlania banera.

1.  **Wymiary obrazu:** Sprawdź rzeczywisty rozmiar banera, gdy się odkleja (możesz potrzebować użyć narzędzi deweloperskich przeglądarki). Następnie zmień rozmiar „Obrazka dla banera”, aby pasował do tych wymiarów lub był nieco większy, zapewniając dobrą jakość.
2.  **Rozmiar pliku:** Chociaż jakość jest ważna, utrzymuj rozmiary plików obrazów tak małe, jak to możliwe (poniżej 100-200 KB), aby zapewnić szybkie ładowanie strony. Użyj narzędzi takich jak TinyPNG lub internetowych optymalizatorów obrazów.

**P: Baner pojawia się, ale kliknięcie go nic nie robi.**
O:

1.  **Sprawdź „Link dla banera”:** Wróć do konfiguracji modułu i dokładnie sprawdź adres URL, który wprowadziłeś dla linku banera. Upewnij się, że jest to kompletny i prawidłowy adres URL (np. `https://www.twojskep.com/kategoria/produkt.html`).
2.  **Przetestuj link:** Skopiuj i wklej link bezpośrednio do przeglądarki, aby upewnić się, że działa poprawnie poza modułem.

**P: Baner nakłada się na inne elementy na mojej stronie.**
O:

1.  **Zmień pozycję:** Spróbuj zmienić „Pozycję banera” z Lewo na Prawo (lub odwrotnie) w konfiguracji modułu.
2.  **Konflikty z motywem:** Jeśli zmiana pozycji nie pomaga, może to być konflikt z CSS Twojego konkretnego motywu PrestaShop. Może to wymagać od webmastera dostosowania CSS modułu lub motywu (szczegóły dla programistów w sekcji 7).

**P: Czy mogę mieć wiele banerów z efektem odklejania?**
O: Nie, ten moduł jest zaprojektowany do wyświetlania jednego banera z efektem odklejania naraz. Jeśli potrzebujesz wielu, musiałbyś zduplikować i zmodyfikować moduł, co wymaga wiedzy programistycznej.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Peeling Corner Banner (`pcb`) to prosty moduł PrestaShop, zaprojektowany głównie do wstrzykiwania efektu wizualnego opartego na JavaScript do front-office. Podąża za podstawową strukturą modułu PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji (`getContent()`). Podstawowa funkcjonalność opiera się na niestandardowym pliku JavaScript (`peelback.js`), który obsługuje manipulację DOM i animację, oraz szablonie Smarty (`header.tpl`) do renderowania początkowej struktury HTML w hooku `displayHeader`. Ustawienia konfiguracji są przechowywane w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   Brak niestandardowych kontrolerów Front-Office.
-   Brak niestandardowych kontrolerów Back-Office Admin.
    Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   Brak niestandardowych klas lub definicji `ObjectModel`.
    Wszystkie konfiguracje są zarządzane za pomocą `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `pcb/peelback.js`
    -   **Zakres:** Front-office.
    -   **Opis:** Jest to główny plik JavaScript odpowiedzialny za animację odklejającego się rogu. Prawdopodobnie inicjuje wtyczkę jQuery lub niestandardowy skrypt, który:
        -   Wykrywa obecność struktury HTML banera (np. `div` z określonym ID, takim jak `#peelback`).
        -   Dołącza słuchacze zdarzeń, głównie `mouseover` i `mouseout`, do elementu rogu.
        -   Przy `mouseover` animuje większy obraz banera, aby „odkleił się” do widoku (np. poprzez zmianę właściwości CSS, takich jak `width`, `height`, `top`, `left`, `z-index`).
        -   Przy `mouseout` animuje baner z powrotem do jego początkowego zwiniętego stanu.
        -   Obsługuje zdarzenie kliknięcia na banerze, aby przekierować do skonfigurowanego adresu URL.
        -   Prawdopodobnie używa funkcji `animate()` jQuery do płynnych przejść.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   W archiwum modułu nie znaleziono dedykowanych plików CSS.
    Oznacza to, że stylizacja banera (początkowa pozycja, wymiary, z-index itp.) jest:
    1.  Wstrzykiwana bezpośrednio za pomocą stylów inline w szablonie `header.tpl`.
    2.  Obsługiwana w całości przez JavaScript, który dynamicznie ustawia właściwości CSS.
    3.  Opiera się na minimalnej domyślnej stylizacji przeglądarki lub oczekuje, że motyw zapewni podstawowe resetowanie.
        Programiści, którzy chcą dostosować wygląd, będą musieli sprawdzić wygenerowany kod HTML i JavaScript pod kątem stylów inline lub dynamicznie stosowanych klas/stylów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `pcb/header.tpl`
        -   **Hook:** `displayHeader` (lub `displayTop` w starszych wersjach, ale `displayHeader` jest standardem do wstrzykiwania globalnych elementów).
        -   **Wyjście:** Ten szablon renderuje początkową strukturę HTML dla banera z efektem odklejania. Zazwyczaj zawiera:
            -   Kontener `div` dla całego banera.
            -   Tag `img` dla małego obrazka rogu.
            -   Tag `img` dla większego obrazka banera (początkowo ukryty lub częściowo ukryty).
            -   Tag `<a>` otaczający te obrazy, połączony ze skonfigurowanym adresem URL.
            -   Prawdopodobnie użyje zmiennych Smarty przekazanych z metody `hookDisplayHeader()` modułu do wyprowadzenia adresów URL obrazów, adresu URL linku i pozycji banera (lewo/prawo).
            -   Może zawierać inline tagi `<style>` lub polegać na `peelback.js` do dynamicznego stosowania stylów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` (lub prefiksie `_configuration`) z kluczami takimi jak:
        -   `PCB_CORNER_IMAGE` (ścieżka do małego obrazka rogu)
        -   `PCB_BANNER_IMAGE` (ścieżka do dużego obrazka banera)
        -   `PCB_BANNER_LINK` (adres URL banera)
        -   `PCB_BANNER_POSITION` (np. „left” lub „right”)
        -   `PCB_ENABLED` (1 dla włączonego, 0 dla wyłączonego)
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Wstrzykuje niezbędną strukturę HTML dla banera i rejestruje skrypt `peelback.js`. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy media (JS/CSS) są ustawiane dla kontrolera front-office. | (Niejawnie używany przez `displayHeader` lub `hookDisplayHeader` do rejestrowania JS/CSS, choć nie jest jawnie wymieniony jako oddzielny hook w metodzie `install()` modułu, tak PrestaShop obsługuje rejestrację mediów). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Peeling Corner Banner, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania naszych modułów.
