---
title: "Facebook Like Box Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Facebook Like Box Free od MyPresta.eu."
sidebar:
  label: "Facebook Like Box Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Like Box Free na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-like-box-free/)
>
> ---


# Facebook Like Box Free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu Facebook Like Box Free. Znajdziesz tutaj wszystkie ustawienia do kontrolowania jego wyglądu i zachowania.

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Włączony** / **Wyłączony** | Kontroluje, czy Facebook Like Box jest aktywny i widoczny w Twoim sklepie. | *Gdy włączony:* Like Box pojawi się w Twoim sklepie w wybranej pozycji. *Gdy wyłączony:* Like Box zostanie ukryty w Twoim sklepie. | **Włączony** | Chcesz zacząć promować swoją stronę na Facebooku. |
| **Pozycja** | Określa, gdzie Like Box będzie wyświetlany w Twoim sklepie. | *Gdy ustawiony na Lewa kolumna:* Like Box pojawia się w lewym pasku bocznym. *Gdy ustawiony na Prawa kolumna:* Like Box pojawia się w prawym pasku bocznym. *Gdy ustawiony na Strona główna:* Like Box pojawia się w głównym obszarze treści Twojej strony głównej. *Gdy ustawiony na Stopka:* Like Box pojawia się na dole każdej strony. | **Prawa kolumna** lub **Strona główna** | Chcesz, aby Like Box był wyraźnie widoczny, nie przeszkadzając w przeglądaniu produktów. |
| **URL strony na Facebooku** | Jest to bezpośredni link do Twojej oficjalnej strony na Facebooku. | *Gdy ustawiony na URL Twojej strony (np. `https://www.facebook.com/MyPrestaEU`):* Like Box wyświetli treści i przycisk „Lubię to” dla *Twojej* konkretnej strony na Facebooku. *Gdy pozostawiony pusty lub nieprawidłowy:* Like Box może nie wyświetlać się poprawnie lub pokaże błąd. | Twój rzeczywisty URL strony na Facebooku | Chcesz połączyć odwiedzających Twój sklep z obecnością Twojej marki na Facebooku. |
| **Szerokość** | Ustawia szerokość Like Box w pikselach. | *Gdy ustawiony na konkretną wartość w pikselach (np. `280`):* Like Box będzie miał dokładnie taką szerokość. *Gdy pozostawiony pusty:* Moduł spróbuje automatycznie dostosować szerokość, ale często lepiej jest ustawić konkretną wartość dla spójnego projektu. | `280` (lub dostosuj, aby pasował do Twojej kolumny/układu) | Twoja prawa kolumna ma 300px szerokości, więc ustawiasz szerokość Like Box na 280px, aby ładnie pasował z pewnym marginesem. |
| **Wysokość** | Ustawia wysokość Like Box w pikselach. | *Gdy ustawiony na konkretną wartość w pikselach (np. `500`):* Like Box będzie miał dokładnie taką wysokość. *Gdy pozostawiony pusty:* Moduł spróbuje automatycznie dostosować wysokość. | `500` (lub dostosuj w zależności od treści, które chcesz pokazać) | Chcesz pokazać kilka ostatnich postów, więc ustawiasz wysokość na 500px, aby zapewnić wystarczającą przestrzeń. |
| **Ukryj okładkę** | Kontroluje, czy duże zdjęcie w tle Twojej strony na Facebooku jest wyświetlane na górze Like Box. | *Gdy włączone:* Zdjęcie w tle zostanie ukryte, co sprawi, że Like Box będzie bardziej kompaktowy. *Gdy wyłączone:* Zdjęcie w tle będzie widoczne. | **Włączone** (dla czystszego wyglądu) | Preferujesz minimalistyczny design i chcesz, aby Like Box zajmował mniej miejsca w pionie. |
| **Zdjęcia profilowe** (Pokaż Facepile) | Określa, czy zdjęcia profilowe osób, które lubią Twoją stronę, są wyświetlane poniżej przycisku „Lubię to”. | *Gdy włączone:* Pojawi się rząd małych zdjęć profilowych, pokazując dowód społeczny. *Gdy wyłączone:* Te zdjęcia profilowe nie będą wyświetlane. | **Włączone** (dla dowodu społecznego) | Chcesz pokazać odwiedzającym, że wielu innych już lubi Twoją stronę, zachęcając ich do tego samego. |
| **Pokaż posty** (Pokaż strumień) | Kontroluje, czy ostatnie posty z Twojej strony na Facebooku są wyświetlane w Like Box. | *Gdy włączone:* Twoje najnowsze posty na Facebooku będą widoczne, co sprawi, że Like Box będzie bardziej dynamiczny. *Gdy wyłączone:* Wyświetlany będzie tylko przycisk „Lubię to” i facepile (jeśli włączone). | **Włączone** | Aktywnie publikujesz na Facebooku i chcesz prezentować swoje najnowsze treści bezpośrednio w swoim sklepie. |
| **Przycisk wezwania do działania** (Ukryj CTA) | Kontroluje, czy przycisk „Wezwanie do działania” (np. „Wyślij wiadomość”, „Kup teraz”) z Twojej strony na Facebooku jest ukryty. | *Gdy włączone:* Przycisk CTA zostanie ukryty. *Gdy wyłączone:* Przycisk CTA będzie widoczny, jeśli skonfigurowano go na Twojej stronie na Facebooku. | **Włączone** (często dla czystszego wyglądu) | Chcesz skupić się wyłącznie na uzyskaniu „Polubienia” i nie chcesz, aby inny przycisk rozpraszał odwiedzających. |
| **Mały nagłówek** | Sprawia, że nagłówek Like Box jest mniejszy. | *Gdy włączone:* Nagłówek (zawierający nazwę Twojej strony i przycisk „Lubię to”) będzie bardziej kompaktowy. *Gdy wyłączone:* Nagłówek będzie miał standardowy rozmiar. | **Włączone** (dla bardziej kompaktowego projektu) | Chcesz, aby Like Box był mniej inwazyjny i bardziej płynnie wtapiał się w projekt Twojego sklepu. |
| **Biblioteka Facebooka** (Dołącz aplikację) | To ustawienie kontroluje, czy niezbędny Facebook JavaScript SDK jest ładowany. | *Gdy włączone:* Moduł załaduje Facebook SDK, co jest niezbędne do prawidłowego działania Like Box. *Gdy wyłączone:* Like Box prawdopodobnie nie będzie wyświetlany lub nie będzie działał poprawnie. | **Włączone** | Jest to kluczowe dla działania Like Box. |

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włączony/Wyłączony | Włączony | Aktywuje/Dezaktywuje Like Box w Twoim sklepie. |
| Konfiguracja modułu | Pozycja | Prawa kolumna / Strona główna | Określa, gdzie pojawia się Like Box (Lewa/Prawa kolumna, Strona główna, Stopka). |
| Konfiguracja modułu | URL strony na Facebooku | URL Twojej strony na Facebooku | Łączy Like Box z Twoją konkretną stroną na Facebooku. |
| Konfiguracja modułu | Szerokość | 280 | Ustawia szerokość Like Box w pikselach. |
| Konfiguracja modułu | Wysokość | 500 | Ustawia wysokość Like Box w pikselach. |
| Konfiguracja modułu | Ukryj okładkę | Włączone | Ukrywa duże zdjęcie w tle dla bardziej kompaktowego wyglądu. |
| Konfiguracja modułu | Zdjęcia profilowe (Pokaż Facepile) | Włączone | Pokazuje zdjęcia profilowe osób, które lubią Twoją stronę (dowód społeczny). |
| Konfiguracja modułu | Pokaż posty (Pokaż strumień) | Włączone | Wyświetla ostatnie posty z Twojej strony na Facebooku. |
| Konfiguracja modułu | Przycisk wezwania do działania (Ukryj CTA) | Włączone | Ukrywa przycisk wezwania do działania strony na Facebooku. |
| Konfiguracja modułu | Mały nagłówek | Włączone | Sprawia, że nagłówek Like Box jest bardziej kompaktowy. |
| Konfiguracja modułu | Biblioteka Facebooka (Dołącz aplikację) | Włączone | Ładuje niezbędny Facebook JavaScript SDK do działania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Facebook Like Box nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Facebook Like Box Free” jest zainstalowany i włączony.
2.  **Zweryfikuj konfigurację:** Przejdź do strony konfiguracji modułu.
    -   Upewnij się, że „Włączony” jest ustawione na TAK.
    -   Dokładnie sprawdź, czy „URL strony na Facebooku” jest poprawny i kompletny (np. `https://www.facebook.com/MyPrestaEU`).
    -   Upewnij się, że „Biblioteka Facebooka” (Dołącz aplikację) jest włączona.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają wyświetlanie nowych modułów.
4.  **Sprawdź pozycję haka:** Upewnij się, że wybrana „Pozycja” (np. Prawa kolumna, Strona główna) jest faktycznie aktywna w Twoim motywie. Niektóre motywy mogą nie wyświetlać niektórych kolumn. Możesz sprawdzić **Wygląd > Pozycje**, aby zobaczyć, czy moduł jest poprawnie podpięty.

**P: Like Box wygląda na zbyt szeroki/wąski lub zbyt wysoki/niski.**
O: Dostosuj ustawienia „Szerokość” i „Wysokość” na stronie konfiguracji modułu. Eksperymentuj z różnymi wartościami pikseli, aż idealnie dopasuje się do układu Twojego motywu. Pamiętaj, aby wyczyścić pamięć podręczną przeglądarki po wprowadzeniu zmian, aby zobaczyć aktualizację.

**P: Zmieniłem ustawienia, ale nic się nie stało w moim sklepie.**
O: Po zapisaniu zmian w konfiguracji modułu zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**), a następnie wyczyść pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+R), aby upewnić się, że widzisz najnowszą wersję swojego sklepu.

**P: Like Box wyświetla komunikat o błędzie lub nie ładuje treści.**
O:

1.  **Nieprawidłowy URL:** Najczęstszą przyczyną jest nieprawidłowy „URL strony na Facebooku”. Sprawdź go dokładnie pod kątem literówek.
2.  **Problemy z API Facebooka:** Czasami mogą występować tymczasowe problemy z API Facebooka. Poczekaj chwilę i sprawdź ponownie.
3.  **Konflikty motywu:** Rzadko, JavaScript lub CSS Twojego motywu może powodować konflikty. Jeśli powyższe kroki nie działają, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby wykluczyć konflikt motywu.

**P: Czy mogę przetłumaczyć tekst „Polub stronę” na inne języki?**
O: Tekst w samym Facebook Like Box (takie jak „Polub stronę” lub treść posta) jest kontrolowany przez Facebooka i automatycznie dostosuje się do ustawień językowych użytkownika na Facebooku. Ustawienia modułu w panelu administracyjnym są przetłumaczalne za pośrednictwem **Lokalizacja > Tłumaczenia** w PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera techniczny przegląd dla programistów i webmasterów pracujących z modułem Facebook Like Box Free.

### 4.1 Przegląd architektury

Moduł `Facebook Like Box Free` to prosty moduł PrestaShop, zaprojektowany głównie do osadzania wtyczki strony Facebooka (dawniej Like Box) za pomocą oficjalnego Facebook JavaScript SDK. Podąża za podstawową strukturą modułu PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji. Jego podstawowa funkcjonalność polega na wyświetlaniu widżetu Facebooka za pośrednictwem szablonu Smarty podpiętego do różnych pozycji front-office. Nie ma tu niestandardowych tabel baz danych ani złożonych ObjectModels; cała konfiguracja jest przechowywana w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest hermetyzowana w głównym pliku modułu (`likeboxfree.php`).

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Cała logika modułu znajduje się w głównym pliku `likeboxfree.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript w `views/js/`.
Facebook JavaScript SDK jest dynamicznie ładowany przez szablon modułu, jeśli ustawienie `lbf_includeapp` jest włączone. Jest to obsługiwane przez własny skrypt Facebooka, a nie niestandardowy skrypt modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`likeboxfree/css.css`**
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten plik zapewnia podstawową stylizację dla opakowania wokół Facebook Like Box, aby zapewnić jego czystą integrację z układem PrestaShop, szczególnie dla haków kolumn. Może zawierać reguły dotyczące dopełnienia, marginesów lub podstawowej responsywności.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści mogą sprawdzić wygenerowany kod HTML, aby znaleźć element opakowujący (np. `div` z określonym ID lub klasą wygenerowaną przez moduł) i nadpisać jego style w pliku `custom.css` lub `theme.css` swojego motywu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   **`likeboxfree/rightcolumn.tpl`**
        -   **Podpięty do:** `displayHome`, `displayFooter`, `displayRightColumn`, `displayLeftColumn` (w zależności od konfiguracji `likeboxfree_position`).
        -   **Wyjście bloku wizualnego:** Ten szablon jest odpowiedzialny za renderowanie struktury HTML, która osadza wtyczkę strony Facebooka. Dynamicznie generuje element `div` z klasą `fb-page` i atrybutami danych (`data-href`, `data-width`, `data-height` itp.) na podstawie ustawień konfiguracji modułu. Zawiera również niezbędny fragment JavaScript do inicjalizacji Facebook SDK i parsowania wtyczki.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele baz danych**:
    Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `likeboxfree_` lub `lbf_`.

    -   Wpisy `ps_configuration`:
        -   `likeboxfree_position`: Przechowuje wybraną pozycję haka (np. `displayRightColumn`).
        -   `lbf_width`: Szerokość Like Box.
        -   `lbf_height`: Wysokość Like Box.
        -   `lbf_hide_cover`: Wartość logiczna (0/1) dla ukrywania zdjęcia w tle.
        -   `lbf_show_facepile`: Wartość logiczna (0/1) dla pokazywania zdjęć profilowych.
        -   `lbf_show_posts`: Wartość logiczna (0/1) dla pokazywania postów.
        -   `lbf_hide_cta`: Wartość logiczna (0/1) dla ukrywania przycisku wezwania do działania.
        -   `lbf_small_header`: Wartość logiczna (0/1) dla małego nagłówka.
        -   `lbf_url`: URL strony na Facebooku.
        -   `lbf_includeapp`: Wartość logiczna (0/1) dla dołączania Facebook SDK.
        -   (Mogą również istnieć starsze/nieużywane klucze z poprzednich wersji, ale powyższe są aktywne).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHome` | Renderuje zawartość na stronie głównej. | Wyświetla Facebook Like Box w głównym obszarze treści strony głównej, jeśli skonfigurowano. |
| `displayFooter` | Renderuje zawartość w stopce sklepu. | Wyświetla Facebook Like Box na dole każdej strony, jeśli skonfigurowano. |
| `displayRightColumn` | Renderuje zawartość w prawym pasku bocznym. | Wyświetla Facebook Like Box w prawej kolumnie stron, jeśli skonfigurowano. |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym. | Wyświetla Facebook Like Box w lewej kolumnie stron, jeśli skonfigurowano. |

Metody `hookDisplay*` modułu sprawdzają wartość konfiguracji `likeboxfree_position` i renderują szablon `rightcolumn.tpl` tylko wtedy, gdy bieżący hak odpowiada skonfigurowanej pozycji.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Facebook Like Box Free”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
"""
