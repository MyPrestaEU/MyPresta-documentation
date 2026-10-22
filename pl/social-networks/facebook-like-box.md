---
title: "Facebook Like Box - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: ""
sidebar:
  label: "Facebook Like Box - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Like Box na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-like-box/)
>
> ---


> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Like Box na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-like-box/)
>
> ---


# Facebook Like Box

## 1. Wymagania i Kompatybilność

- **Obsługiwane Wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania Hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i każdego modułu wchodzącego w interakcje z zewnętrznymi API, takimi jak Facebook.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel Administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu Facebook Like Box. Tutaj zdefiniujesz, jak Twój Like Box wygląda i zachowuje się w Twoim sklepie.

**Nazwa Ekranu i Lokalizacja w Menu:** Panel Administracyjny > Moduły > Menedżer modułów > Facebook Like Box > Konfiguruj

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Adres URL Strony na Facebooku** | Jest to bezpośredni link do Twojej oficjalnej strony na Facebooku. | *Po ustawieniu:* Like Box będzie wyświetlał zawartość z tej konkretnej strony na Facebooku. *Gdy puste:* Moduł nie będzie działał poprawnie, ponieważ nie będzie wiedział, którą stronę wyświetlić. | Adres URL Twojej strony na Facebooku (np. `https://www.facebook.com/myprestaeu`) | Chcesz promować swoją główną stronę biznesową na Facebooku. |
| **ID Aplikacji (Facebook)** | ID Twojej aplikacji na Facebooku, wymagane dla niektórych zaawansowanych funkcji i integracji API. | *Po ustawieniu:* Umożliwia modułowi interakcję z Graph API Facebooka za pomocą Twojej aplikacji. *Gdy puste:* Może skutkować błędami „Aplikacja nie skonfigurowana”, jeśli moduł wymaga dostępu do API. | ID Twojej aplikacji na Facebooku (np. `123456789012345`) | Musisz rozwiązać błąd „Aplikacja nie skonfigurowana” lub włączyć zaawansowane funkcje API Facebooka. |
| **Szerokość** | Kontroluje szerokość Facebook Like Box w pikselach. | *Po ustawieniu na konkretną wartość (np. 280):* Like Box zachowa dokładnie tę szerokość. *Gdy puste lub ustawione na 0:* Like Box spróbuje być responsywny i automatycznie dostosuje swoją szerokość do swojego kontenera. | Pozostaw puste dla automatycznego wykrywania (zachowanie responsywne) lub ustaw konkretną wartość, np. `280`, jeśli potrzebujesz stałej szerokości. | Chcesz, aby Like Box idealnie pasował do wąskiej kolumny, więc ustawiasz go na `280`. |
| **Wysokość** | Kontroluje wysokość Facebook Like Box w pikselach. | *Po ustawieniu na konkretną wartość (np. 500):* Like Box zachowa dokładnie tę wysokość. *Gdy puste lub ustawione na 0:* Like Box spróbuje być responsywny i automatycznie dostosuje swoją wysokość. | Pozostaw puste dla automatycznego wykrywania (zachowanie responsywne) lub ustaw konkretną wartość, np. `500`, jeśli chcesz pokazać więcej strumienia postów. | Chcesz wyświetlić więcej ostatnich postów ze swojej strony na Facebooku, więc zwiększasz wysokość do `500`. |
| **Pokaż Twarze** | Określa, czy wyświetlane są zdjęcia profilowe osób, które polubiły Twoją stronę. | *Po włączeniu (TAK):* Małe zdjęcia profilowe niektórych Twoich fanów na Facebooku pojawią się pod przyciskiem „Lubię to”, dodając dowód społeczny. *Po wyłączeniu (NIE):* Wyświetlony zostanie tylko przycisk „Lubię to” i informacje o stronie, bez indywidualnych twarzy. | TAK | Chcesz pokazać, że prawdziwi ludzie lubią Twoją stronę, zachęcając innych do dołączenia. |
| **Pokaż Strumień** | Kontroluje, czy ostatnie posty z Twojej strony na Facebooku są wyświetlane w Like Box. | *Po włączeniu (TAK):* Twoje najnowsze posty na Facebooku będą przewijać się w Like Box, dostarczając świeżej zawartości. *Po wyłączeniu (NIE):* Widoczne będzie tylko zdjęcie w tle strony, profil i przycisk „Lubię to”, co sprawi, że pole będzie bardziej kompaktowe. | TAK | Często publikujesz aktualizacje na Facebooku i chcesz udostępniać je bezpośrednio w swoim sklepie. |
| **Pokaż Nagłówek** | Kontroluje, czy nagłówek „Facebook” jest wyświetlany na górze Like Box. | *Po włączeniu (TAK):* Mały tytuł „Facebook” pojawi się na górze widżetu. *Po wyłączeniu (NIE):* Nagłówek zostanie ukryty, co sprawi, że widżet będzie wyglądał czyściej i bardziej zintegrowanie. | NIE | Preferujesz minimalistyczny wygląd Like Box i nie potrzebujesz wyraźnego nagłówka „Facebook”. |
| **Mały Nagłówek** | Używa mniejszej wersji nagłówka. | *Po włączeniu (TAK):* Nagłówek będzie bardziej kompaktowy. *Po wyłączeniu (NIE):* Użyty zostanie standardowy rozmiar nagłówka. | NIE | Chcesz zaoszczędzić miejsce w pionie w swoim układzie. |
| **Ukryj Okładkę** | Ukrywa zdjęcie w tle Twojej strony na Facebooku. | *Po włączeniu (TAK):* Widoczne będzie tylko zdjęcie profilowe i nazwa Twojej strony, co sprawi, że widżet będzie bardziej kompaktowy. *Po wyłączeniu (NIE):* Zdjęcie w tle Twojej strony na Facebooku zostanie wyświetlone na górze widżetu. | NIE | Masz bardzo wąską przestrzeń i chcesz priorytetowo traktować przycisk „Lubię to” i posty nad zdjęciem w tle. |
| **Dostosuj do szerokości kontenera** | Pozwala Like Box automatycznie dostosować swoją szerokość do kontenera nadrzędnego, w którym jest umieszczony. | *Po włączeniu (TAK):* Widżet zmieni rozmiar, aby wypełnić dostępną szerokość, czyniąc go responsywnym. *Po wyłączeniu (NIE):* Widżet będzie trzymał się określonego ustawienia `Szerokość`, potencjalnie powodując przepełnienie lub pustą przestrzeń. | TAK | Chcesz, aby Like Box wyglądał dobrze na wszystkich urządzeniach i rozmiarach ekranu bez ręcznych regulacji. |
| **Niestandardowy CSS** | Pozwala dodać niestandardowe reguły CSS do dalszego stylizowania Like Box. | *Po wypełnieniu kodem CSS:* Twoje niestandardowe style zostaną zastosowane, nadpisując domyślne style. *Gdy puste:* Moduł użyje swojego domyślnego stylu lub domyślnego stylu Facebooka. | Pozostaw puste, chyba że masz specyficzne potrzeby stylizacyjne. | Chcesz zmienić rozmiar czcionki lub kolor tekstu w Like Box, aby pasował do motywu Twojej marki. |
| **Hook do wyświetlania modułu** | Wybiera, gdzie w Twoim sklepie pojawi się Like Box. | *Po wybraniu hooka:* Moduł wyświetli swoją zawartość w tej konkretnej lokalizacji (np. `displayRightColumn`, `displayFooter`). *Gdy nie wybrano hooka:* Moduł nie będzie widoczny w Twoim front office. | `displayRightColumn` lub `displayLeftColumn` są powszechne, ale wybierz w oparciu o układ Twojego motywu. | Chcesz, aby Like Box był widoczny z boku Twoich list produktów, więc wybierasz `displayRightColumn`. |
| **Kolor Tła** | Ustawia kolor tła Like Box. | *Po wybraniu koloru:* Like Box będzie miał ten kolor tła. *Gdy puste:* Like Box zazwyczaj dziedziczy kolor tła swojego kontenera nadrzędnego lub używa domyślnego koloru Facebooka. | Pozostaw puste lub dopasuj do koloru tła Twojego motywu. | Twój motyw ma ciemne tło, a Ty chcesz, aby Like Box się w nie wtopił, więc ustawiasz ciemny kolor tła. |
| **Kolor Ramki** | Ustawia kolor ramki wokół Like Box. | *Po wybraniu koloru:* Like Box będzie miał ramkę w tym kolorze. *Gdy puste:* Like Box zazwyczaj nie będzie miał ramki lub będzie miał domyślną ramkę Facebooka. | Pozostaw puste lub dopasuj do kolorów ramek Twojego motywu. | Chcesz subtelną szarą ramkę wokół Like Box, aby oddzielić go od innej zawartości. |

### 2.2 Tabela Szybkiego Odniesienia do Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| Konfiguracja Modułu | Adres URL Strony na Facebooku | Adres URL Twojej strony na Facebooku | Łączy widżet z Twoją konkretną stroną na Facebooku. |
| Konfiguracja Modułu | ID Aplikacji (Facebook) | Puste (jeśli nie wymagane) | ID Twojej aplikacji na Facebooku do integracji API. |
| Konfiguracja Modułu | Szerokość | Puste (Responsywne) | Kontroluje szerokość widżetu; puste dla automatycznego dopasowania. |
| Konfiguracja Modułu | Wysokość | Puste (Responsywne) | Kontroluje wysokość widżetu; puste dla automatycznego dopasowania. |
| Konfiguracja Modułu | Pokaż Twarze | TAK | Wyświetla zdjęcia profilowe osób, które polubiły, dla dowodu społecznego. |
| Konfiguracja Modułu | Pokaż Strumień | TAK | Wyświetla ostatnie posty z Twojej strony na Facebooku. |
| Konfiguracja Modułu | Pokaż Nagłówek | NIE | Ukrywa tytuł „Facebook” dla czystszego wyglądu. |
| Konfiguracja Modułu | Mały Nagłówek | NIE | Używa mniejszego nagłówka, jeśli `Pokaż Nagłówek` jest TAK. |
| Konfiguracja Modułu | Ukryj Okładkę | NIE | Pokazuje zdjęcie w tle Twojej strony na Facebooku. |
| Konfiguracja Modułu | Dostosuj do szerokości kontenera | TAK | Zapewnia responsywność widżetu do jego kontenera nadrzędnego. |
| Konfiguracja Modułu | Niestandardowy CSS | Puste | Umożliwia zaawansowane stylizowanie za pomocą niestandardowych reguł CSS. |
| Konfiguracja Modułu | Hook do wyświetlania modułu | `displayRightColumn` (lub odpowiednia kolumna) | Określa, gdzie moduł pojawia się w Twoim sklepie. |
| Konfiguracja Modułu | Kolor Tła | Puste | Ustawia kolor tła widżetu. |
| Konfiguracja Modułu | Kolor Ramki | Puste | Ustawia kolor ramki widżetu. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P1: Facebook Like Box nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O1:

-   **Sprawdź Status Modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Facebook Like Box” jest zainstalowany i włączony.
-   **Zweryfikuj Wybór Hooka:** W konfiguracji modułu upewnij się, że wybrałeś „Hook do wyświetlania modułu” (np. `displayRightColumn`, `displayFooter`). Jeśli Twój motyw nie renderuje wybranego hooka, nie pojawi się on. Spróbuj innego, popularnego hooka.
-   **Wyczyść Pamięć Podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się nowych modułów.
-   **Adres URL Strony na Facebooku:** Sprawdź dwukrotnie, czy „Adres URL Strony na Facebooku” w konfiguracji modułu jest poprawny i dostępny.

**P2: Like Box wygląda zbyt szeroko/wąsko lub nie pasuje prawidłowo do mojego motywu.**
O2:

-   **Ustawienia Responsywne:** W konfiguracji modułu upewnij się, że „Dostosuj do szerokości kontenera” jest ustawione na TAK, a pola „Szerokość” i „Wysokość” pozostaw puste. Pozwala to Facebookowi zarządzać responsywnością.
-   **Konflikty z Motywem:** CSS Twojego motywu może nadpisywać style modułu. Jeśli czujesz się komfortowo z CSS, użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać element i zobaczyć, które reguły CSS są stosowane.
-   **Niestandardowy CSS:** Użyj pola „Niestandardowy CSS” w konfiguracji modułu, aby dodać specyficzne reguły w celu dostosowania jego rozmiaru lub wyglądu, jeśli to konieczne. Na przykład: `.fb_iframe_widget { max-width: 100% !important; }`.

**P3: Like Box wyświetla błąd lub nie ładuje treści z mojej strony na Facebooku.**
O3:

-   **Poprawny Adres URL:** Sprawdź, czy „Adres URL Strony na Facebooku” jest absolutnie poprawny i wskazuje na publiczną stronę na Facebooku (nie na profil osobisty ani grupę).
-   **Problemy z API Facebooka:** Czasami API Facebooka może doświadczać tymczasowych problemów. Poczekaj chwilę i sprawdź ponownie.
-   **Ograniczenia Strony:** Upewnij się, że Twoja strona na Facebooku nie ma żadnych ograniczeń krajowych ani wiekowych, które mogłyby uniemożliwić ładowanie widżetu dla wszystkich odwiedzających.

:::caution
\*\*Błąd „Aplikacja nie skonfigurowana” (Moduł Wersja 1.8 i wyższe)\*\*
Jeśli napotkasz błąd „Aplikacja nie skonfigurowana”, szczególnie w przypadku modułu w wersji 1.8 lub wyższej, która obsługuje Facebook Graph API v18.0:
1.  \*\*Wprowadź ID swojej aplikacji na Facebooku:\*\* Upewnij się, że poprawnie wprowadziłeś ID swojej aplikacji na Facebooku w polu konfiguracji modułu.
2.  \*\*Zweryfikuj Ustawienia Domeny na Facebooku:\*\* Zaloguj się na swoje konto dewelopera Facebooka ([developers.facebook.com](https://developers.facebook.com/)). Przejdź do ustawień swojej aplikacji i potwierdź, że domena Twojego sklepu (np. `twojasklep.com`) jest poprawnie dodana i zweryfikowana w ustawieniach aplikacji.
:::

**P4: Czy mogę mieć wiele Facebook Like Boxów na różnych stronach?**
O4: Ten moduł jest zaprojektowany do wyświetlania jednego Facebook Like Box skonfigurowanego globalnie. Jeśli potrzebujesz wielu, odrębnych Like Boxów (np. dla różnych stron na Facebooku lub z różnymi ustawieniami), zazwyczaj musiałbyś zainstalować moduł wiele razy (jeśli jest to obsługiwane przez system modułów PrestaShop, co jest rzadkie w przypadku modułów jednokrotnego użycia) lub użyć niestandardowego kodu. W przypadku tego konkretnego modułu, zazwyczaj jest to jedna instancja, jedna konfiguracja.

**P5: Jak przetłumaczyć tekst w Like Box (np. „Polub stronę”)?**
O5: Tekst w samym Facebook Like Box (takie jak „Polub stronę”, „Obserwuj”, „Udostępnij”) jest kontrolowany przez Facebooka na podstawie ustawień językowych przeglądarki użytkownika i własnej lokalizacji Facebooka. Ten moduł nie tłumaczy bezpośrednio tych elementów. Każdy tekst *wokół* Like Box, który dodajesz w swoim motywie lub innych modułach, byłby możliwy do przetłumaczenia za pośrednictwem systemu tłumaczeń PrestaShop.

## 4. Przewodnik dla Deweloperów i Webmasterów (Architektura Techniczna i Mapa Kodu)

### 4.1 Przegląd Architektury

Moduł Facebook Like Box (`likebox`) to standardowy moduł PrestaShop, który stosuje podstawowy wzorzec MVC. Głównie wykorzystuje klasę `Module` do obsługi instalacji, deinstalacji i konfiguracji. Podstawowa funkcjonalność polega na renderowaniu szablonu Smarty, który osadza wtyczkę Facebook Page Plugin (dawniej Like Box) za pomocą oficjalnego SDK JavaScript Facebooka. Ustawienia konfiguracji są przechowywane w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy Podstawowe i Modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała logika zawarta jest w głównym pliku modułu (`likebox/ar.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora)
    -   **Cel:** Jest to zewnętrzna biblioteka JavaScript, która zapewnia funkcjonalność wyboru koloru. Jest używana na stronie konfiguracji modułu, aby umożliwić sprzedawcy wizualne wybranie ustawień „Kolor Tła” i „Kolor Ramki”.
    -   **Interakcja:** Wiąże się z konkretnymi polami wejściowymi (prawdopodobnie z klasą taką jak `jscolor`), aby otworzyć paletę wyboru koloru.
-   **`likebox/script.js`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora)
    -   **Cel:** Ten skrypt obsługuje dynamiczne aktualizacje i funkcjonalność podglądu na żywo na stronie konfiguracji modułu. Pobiera ustawienia wprowadzone przez sprzedawcę (adres URL strony na Facebooku, szerokość, wysokość, pokaż twarze itp.) i dynamicznie aktualizuje `<iframe>` lub obszar podglądu, aby pokazać, jak będzie wyglądał Facebook Like Box.
    -   **Interakcja:**
        -   Nasłuchuje zdarzeń `change` i `keyup` na różnych polach wejściowych (np. `#facebook_page_url`, `#width`, `#height`, pola wyboru).
        -   Konstruuje parametry URL wtyczki Facebook Page Plugin na podstawie bieżących ustawień.
        -   Aktualizuje atrybut `src` podglądu `<iframe>` lub dynamicznie generuje kod osadzania Facebook SDK, aby odzwierciedlić zmiany w czasie rzeczywistym.
        -   Prawdopodobnie używa `jscolor.js` do pobierania wartości kolorów dla tła i ramki.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   **`likebox/css.css`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji administratora)
    -   **Cel:** Zapewnia stylizację formularza konfiguracji modułu w Panelu Administracyjnym PrestaShop. Może to obejmować dostosowania układu, stylizację pól wejściowych lub stylizację obszaru podglądu na żywo.
    -   **Kluczowe Selektory:** Prawdopodobnie celuje w elementy w ramach danych wyjściowych `getContent()`, takie jak grupy formularzy, etykiety i kontener podglądu.
-   **`likebox/css/css.css`**
    -   **Zakres:** Front-office (sklep widoczny dla klienta)
    -   **Cel:** Zapewnia minimalną stylizację samego widżetu Facebook Like Box, głównie w celu zapewnienia jego dobrej integracji z układem sklepu. Może to obejmować domyślne wypełnienie, marginesy lub podstawowe dostosowania responsywne.
    -   **Kluczowe Selektory:** Celuje w element kontenera, w którym osadzony jest widżet Facebooka (np. `.facebook_like_box_container`) i potencjalnie stosuje `max-width: 100%` dla responsywności. Deweloperzy mogą nadpisać te style w pliku `custom.css` lub `theme.css` swojego motywu.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

Szablony modułu znajdują się bezpośrednio w katalogu głównym modułu.

-   **`likebox/header.tpl`**
    -   **Zakres:** Front-office
    -   **Hook:** `displayHeader`
    -   **Cel:** Ten szablon jest przeznaczony do podłączenia do `displayHeader`. Jego główną rolą jest dołączenie Facebook JavaScript SDK, które jest niezbędne do prawidłowego renderowania wtyczki Facebook Page Plugin. Zawiera również element `div`, w którym Like Box zostanie wyrenderowany przez SDK.
    -   **Wyjście:**

        ```
        <div id="fb-root"></div><script> (function(d, s, id) { var js, fjs = d.getElementsByTagName(s)[0]; if (d.getElementById(id)) return; js = d.createElement(s); js.id = id; js.src = "//connect.facebook.net/en\_US/sdk.js#xfbml=1&version=v2.8&appId={$app\_id}"; // Wersja może się różnić, dodano appId fjs.parentNode.insertBefore(js, fjs); }(document, 'script', 'facebook-jssdk'));</script><div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div></div>
        ```

        (Uwaga: Rzeczywista wersja SDK i atrybuty danych mogą się nieznacznie różnić w zależności od dokładnej implementacji modułu i zmian w API Facebooka.)
-   **`likebox/rightcolumn.tpl`**
    -   **Zakres:** Front-office
    -   **Hook:** `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayProductButtons` itp. (w zależności od konfiguracji modułu)
    -   **Cel:** Ten szablon działa jako opakowanie dla Facebook Like Box. Jest zaprojektowany tak, aby był elastyczny i mógł być podłączony w różnych pozycjach. Zazwyczaj zawiera element `div` z klasą `fb-page`, który SDK Facebooka przekształci w wizualny Like Box.
    -   **Wyjście:**

        ```
        <div class="block facebook\_like\_box\_container"> <h4>{l s='Follow us on Facebook' mod='likebox'}</h4> <div class="block\_content"> <div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div> </div> </div></div>
        ```

        Ten szablon zawiera również tytuł `<h4>` i strukturę `block_content` typową dla bloków kolumn PrestaShop.

### 4.7 Schemat Bazy Danych i Mapa Hooków

-   **Tabele Bazy Danych**:
    -   Ten moduł nie tworzy niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy zazwyczaj poprzedzonych prefiksem `LIKEBOX_` (np. `LIKEBOX_FACEBOOK_PAGE_URL`, `LIKEBOX_WIDTH`, `LIKEBOX_HEIGHT`, `LIKEBOX_APP_ID` itp.).
-   **Tabela Zarejestrowanych Hooków**:

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` każdej strony. | Służy do dołączenia Facebook JavaScript SDK i początkowego div `fb-root`, niezbędnego do działania Like Box. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie bocznej. | Wyświetla widżet Facebook Like Box w lewej kolumnie. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie bocznej. | Wyświetla widżet Facebook Like Box w prawej kolumnie. |
| `displayFooter` | Renderuje zawartość w sekcji stopki sklepu. | Wyświetla widżet Facebook Like Box w stopce. |
| `displayHome` | Renderuje zawartość na stronie głównej. | Wyświetla widżet Facebook Like Box na stronie głównej. |
| `displayProductButtons` | Renderuje zawartość w pobliżu przycisków akcji produktu na stronie produktu. | Wyświetla widżet Facebook Like Box na stronach produktów. |
| `displayProductExtraContent` | Renderuje dodatkową zawartość na stronie produktu, często w zakładce lub poniżej głównej zawartości. | Wyświetla widżet Facebook Like Box na stronach produktów. |
| `displayMyAccountBlock` | Renderuje zawartość w bloku „Moje Konto” klienta. | Wyświetla widżet Facebook Like Box w obszarze konta klienta (rzadziej dla tego modułu). |
| `displayMyAccountBlockfooter` | Renderuje zawartość w stopce bloku „Moje Konto”. | Wyświetla widżet Facebook Like Box w obszarze konta klienta. |

(Uwaga: Metoda `install()` modułu rejestruje te hooki, a metody `hook<HookName>()` w `ar.php` są odpowiedzialne za renderowanie `rightcolumn.tpl` lub `header.tpl` w zależności od hooka.)

## 5. Oficjalne Wsparcie i Aktualizacje

Aby uzyskać najnowsze wersje, aktualizacje i dedykowane wsparcie dla modułu Facebook Like Box, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
