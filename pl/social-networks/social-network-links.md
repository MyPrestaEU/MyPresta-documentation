---
title: "Linki do sieci społecznościowych - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kro kroku oraz dokumentacja dla programistów modułu Linki do sieci społecznościowych PrestaShop od MyPresta.eu."
sidebar:
  label: "Linki do sieci społecznościowych - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Social Network Links na MyPresta.eu](https://mypresta.eu/modules/social-networks/social-network-links.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/social-network-links/)
>
> ---


# Linki do sieci społecznościowych

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj preinstalowane w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Linki do sieci społecznościowych)

Jest to główny i jedyny ekran konfiguracji modułu „Linki do sieci społecznościowych”. Tutaj zdefiniujesz, które sieci społecznościowe mają być wyświetlane i gdzie mają się pojawiać w Twoim sklepie.

**Dostęp:** Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Linki do sieci społecznościowych” i kliknij „Konfiguruj”.

#### **Ustawienia ogólne**

-   **URL Facebooka:**
    -   **Co robi to ustawienie:** Tutaj wprowadzasz pełny adres internetowy (URL) swojej strony na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione:* Ikona Facebooka pojawi się w bloku modułu, linkując bezpośrednio do podanego URL-a.
        -   *Gdy puste:* Ikona Facebooka nie zostanie wyświetlona.
    -   **Zalecana wartość:** Oficjalny URL Twojej strony na Facebooku (np. `https://www.facebook.com/nazwatwojegosklepu`).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja strona na Facebooku to `https://www.facebook.com/MojSuperSklep`, wprowadź ten URL tutaj. Klienci klikający ikonę Facebooka zostaną przeniesieni na Twoją stronę.
-   **URL Twittera:**
    -   **Co robi to ustawienie:** Wprowadź pełny adres internetowy (URL) swojego profilu na Twitterze.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione:* Ikona Twittera pojawi się, linkując do Twojego profilu na Twitterze.
        -   *Gdy puste:* Ikona Twittera nie zostanie wyświetlona.
    -   **Zalecana wartość:** Oficjalny URL Twojego profilu na Twitterze (np. `https://twitter.com/nazwatwojegosklepu`).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój uchwyt na Twitterze to `@MojSuperSklep`, Twój URL może wyglądać tak: `https://twitter.com/MojSuperSklep`.
-   **URL YouTube:**
    -   **Co robi to ustawienie:** Wprowadź pełny adres internetowy (URL) swojego kanału na YouTube.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione:* Ikona YouTube pojawi się, linkując do Twojego kanału.
        -   *Gdy puste:* Ikona YouTube nie zostanie wyświetlona.
    -   **Zalecana wartość:** Oficjalny URL Twojego kanału na YouTube (np. `https://www.youtube.com/channel/identyfikator_twojego_kanalu`).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz filmy z recenzjami produktów lub samouczki na YouTube, podlinkuj swój kanał tutaj.
-   **URL Google+:**
    -   **Co robi to ustawienie:** Wprowadź pełny adres internetowy (URL) swojego profilu lub strony na Google+.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione:* Ikona Google+ pojawi się, linkując do Twojego profilu.
        -   *Gdy puste:* Ikona Google+ nie zostanie wyświetlona.
    -   **Zalecana wartość:** Oficjalny URL Twojego profilu/strony na Google+ (np. `https://plus.google.com/+NazwaTwojegoSklepu`).
    -   **Scenariusz / przykład dla sprzedawcy:** Chociaż Google+ jest w dużej mierze przestarzałe, jeśli nadal utrzymujesz tam obecność lub masz starsze treści, możesz je tutaj podlinkować. W przeciwnym razie pozostaw puste.
-   **URL RSS:**
    -   **Co robi to ustawienie:** Wprowadź pełny adres internetowy (URL) swojego kanału RSS. Jest to zazwyczaj używane w przypadku blogów lub sekcji wiadomości, aby umożliwić użytkownikom subskrybowanie aktualizacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione:* Ikona RSS pojawi się, linkując do Twojego kanału.
        -   *Gdy puste:* Ikona RSS nie zostanie wyświetlona.
    -   **Zalecana wartość:** Jeśli Twój sklep ma bloga lub sekcję wiadomości z kanałem RSS, wprowadź jego URL (np. `https://twojskep.com/blog/feed`). W przeciwnym razie pozostaw puste.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli regularnie publikujesz posty na blogu o swoich produktach lub branży, udostępnienie kanału RSS pozwala klientom obeznanym z technologią na bezpośrednie otrzymywanie aktualizacji.

#### **Ustawienia wyświetlania**

-   **Wyświetl w nagłówku:**
    -   **Co robi to ustawienie:** Kontroluje, czy blok linków do sieci społecznościowych pojawia się w sekcji nagłówka Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Blok linków społecznościowych będzie widoczny w górnej części Twojej strony internetowej.
        -   *Gdy wyłączone (Nie):* Blok nie pojawi się w nagłówku.
    -   **Zalecana wartość:** **Tak**, jeśli chcesz, aby Twoje linki społecznościowe były dobrze widoczne.
    -   **Scenariusz / przykład dla sprzedawcy:** Włącz to, jeśli chcesz, aby klienci natychmiast widzieli Twoją obecność w mediach społecznościowych po wejściu na Twoją stronę.
-   **Wyświetl w lewej kolumnie:**
    -   **Co robi to ustawienie:** Kontroluje, czy blok linków do sieci społecznościowych pojawia się w lewej kolumnie bocznej Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Blok linków społecznościowych będzie widoczny w lewej kolumnie (jeśli Twój motyw ją posiada).
        -   *Gdy wyłączone (Nie):* Blok nie pojawi się w lewej kolumnie.
    -   **Zalecana wartość:** **Nie**, chyba że masz konkretny powód, aby umieścić go tam i Twój motyw obsługuje lewą kolumnę. Często preferowana jest prawa kolumna lub stopka.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma widoczną lewą kolumnę i chcesz, aby linki były widoczne, gdy klienci przeglądają kategorie, włącz to.
-   **Wyświetl w prawej kolumnie:**
    -   **Co robi to ustawienie:** Kontroluje, czy blok linków do sieci społecznościowych pojawia się w prawej kolumnie bocznej Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Blok linków społecznościowych będzie widoczny w prawej kolumnie (jeśli Twój motyw ją posiada).
        -   *Gdy wyłączone (Nie):* Blok nie pojawi się w prawej kolumnie.
    -   **Zalecana wartość:** **Tak**, jeśli chcesz wyświetlać linki w pasku bocznym.
    -   **Scenariusz / przykład dla sprzedawcy:** Dobra opcja, aby linki społecznościowe były widoczne, nie zaśmiecając zbytnio nagłówka ani stopki.
-   **Wyświetl w stopce:**
    -   **Co robi to ustawienie:** Kontroluje, czy blok linków do sieci społecznościowych pojawia się w sekcji stopki Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Blok linków społecznościowych będzie widoczny na dole Twojej strony internetowej.
        -   *Gdy wyłączone (Nie):* Blok nie pojawi się w stopce.
    -   **Zalecana wartość:** **Tak**, ponieważ stopka jest standardowym i oczekiwanym miejscem na linki do mediów społecznościowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Włącz to, aby zapewnić spójne miejsce na linki społecznościowe, których klienci często szukają na dole strony.
-   **Wyświetl na stronie produktu:**
    -   **Co robi to ustawienie:** Kontroluje, czy blok linków do sieci społecznościowych pojawia się na poszczególnych stronach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Blok linków społecznościowych będzie widoczny na każdej stronie szczegółów produktu.
        -   *Gdy wyłączone (Nie):* Blok nie pojawi się na stronach produktów.
    -   **Zalecana wartość:** **Tak**, jeśli chcesz zachęcać do udostępniania w mediach społecznościowych lub śledzenia bezpośrednio ze stron produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klienci łatwo znajdowali Twoje media społecznościowe, gdy rozważają zakup, włącz to.

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | URL Facebooka | Puste / URL Twojej strony na Facebooku | Link do Twojego profilu na Facebooku. Puste = brak ikony. |
| Konfiguracja modułu | URL Twittera | Puste / URL Twojego profilu na Twitterze | Link do Twojego profilu na Twitterze. Puste = brak ikony. |
| Konfiguracja modułu | URL YouTube | Puste / URL Twojego kanału na YouTube | Link do Twojego kanału na YouTube. Puste = brak ikony. |
| Konfiguracja modułu | URL Google+ | Puste / URL Twojego profilu na Google+ | Link do Twojego profilu na Google+. Puste = brak ikony. |
| Konfiguracja modułu | URL RSS | Puste / URL Twojego kanału RSS | Link do Twojego kanału RSS. Puste = brak ikony. |
| Konfiguracja modułu | Wyświetl w nagłówku | Nie / Tak | Pokaż linki społecznościowe w nagłówku sklepu. |
| Konfiguracja modułu | Wyświetl w lewej kolumnie | Nie / Nie | Pokaż linki społecznościowe w lewej kolumnie bocznej. |
| Konfiguracja modułu | Wyświetl w prawej kolumnie | Nie / Tak | Pokaż linki społecznościowe w prawej kolumnie bocznej. |
| Konfiguracja modułu | Wyświetl w stopce | Nie / Tak | Pokaż linki społecznościowe w stopce sklepu. |
| Konfiguracja modułu | Wyświetl na stronie produktu | Nie / Tak | Pokaż linki społecznościowe na poszczególnych stronach produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

-   **P: Moje ikony społecznościowe nie pojawiają się po konfiguracji.**
    -   **O:** Najpierw dokładnie sprawdź, czy wprowadziłeś pełne adresy URL swoich sieci społecznościowych w konfiguracji modułu. Upewnij się również, że wybrałeś co najmniej jedną opcję „Wyświetl w…” (np. „Wyświetl w stopce” na Tak). Na koniec wyczyść pamięć podręczną PrestaShop w **Zaawansowane > Wydajność** (kliknij przycisk „Wyczyść pamięć podręczną”). Czasami buforowanie motywu może również uniemożliwić natychmiastowe pojawienie się zmian.
-   **P: Ikony są widoczne, ale wyglądają na źle wyrównane lub nie pasują do mojego motywu.**
    -   **O:** Moduł zapewnia podstawowe style. Jeśli Twój motyw ma bardzo specyficzne reguły CSS, mogą one nadpisywać lub kolidować ze stylami modułu.
        -   **Rozwiązanie 1 (Podstawowe):** Spróbuj wyczyścić pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+R).
        -   **Rozwiązanie 2 (Zaawansowane):** Zazwyczaj wymaga to od webmastera lub programisty sprawdzenia CSS Twojego motywu i potencjalnego dodania niestandardowych reguł CSS do pliku `custom.css` Twojego motywu, aby dostosować wygląd. Plik CSS modułu (`socialnetworklinks.css`) może służyć jako odniesienie.
-   **P: Czy mogę dodać inne sieci społecznościowe, których nie ma na liście (np. Instagram, Pinterest)?**
    -   **O:** Obecna wersja modułu obsługuje Facebooka, Twittera, YouTube, Google+ i RSS. Aby dodać inne sieci, wymagałoby to niestandardowego rozwoju w celu modyfikacji kodu modułu i dodania nowych ikon oraz pól wejściowych. Alternatywnie, poszukaj bardziej kompleksowego modułu mediów społecznościowych, jeśli potrzebujesz szerszego zakresu platform.
-   **P: Linki otwierają się w tej samej karcie, ale chcę, aby otwierały się w nowej karcie.**
    -   **O:** Domyślnie moduł jest zaprojektowany tak, aby otwierać linki w nowej karcie (`target="_blank"`). Jeśli tak się nie dzieje, może to być spowodowane konfliktem z JavaScriptem Twojego motywu lub starszą przeglądarką. Upewnij się, że Twój PrestaShop i przeglądarka są aktualne. Jeśli problem nadal występuje, programista musiałby sprawdzić wygenerowany kod HTML.
-   **P: Włączyłem „Wyświetl w lewej/prawej kolumnie”, ale nic się nie pojawia.**
    -   **O:** Wiele nowoczesnych motywów PrestaShop jest zaprojektowanych bez tradycyjnych lewych lub prawych kolumn na wszystkich stronach, zwłaszcza na stronach produktów lub stronie głównej. Jeśli Twój motyw nie renderuje tych kolumn, moduł nie będzie miał miejsca do wyświetlenia swojego bloku. Sprawdź dokumentację swojego motywu lub dostosuj jego układ, aby włączyć kolumny tam, gdzie chcesz, aby moduł się pojawił. Stopka i nagłówek są zazwyczaj bardziej niezawodnymi miejscami wyświetlania w różnych motywach.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Linki do sieci społecznościowych” to prosty moduł PrestaShop, który stosuje podstawowy wzorzec podobny do MVC w zakresie modułu. Wykorzystuje głównie klasę `Module` do swojej podstawowej funkcjonalności, konfiguracji i rejestracji hooków. Przechowuje swoje ustawienia bezpośrednio w tabeli `ps_configuration` PrestaShop. Wyświetlanie modułu w front-office jest obsługiwane za pomocą pojedynczego szablonu Smarty renderowanego za pomocą różnych hooków wyświetlania.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** zawiera żadnych niestandardowych klas ani definicji `ObjectModel`. Cała logika jest hermetyzowana w głównej klasie `SocialNetworkLinks`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność otwierania linków w nowych kartach jest obsługiwana bezpośrednio w kodzie HTML szablonu za pomocą `target="_blank"`.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`socialnetworklinks/css/socialnetworklinks.css`**
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów zapewnia podstawowy wygląd wizualny ikon mediów społecznościowych, w tym ich rozmiar, odstępy i potencjalne efekty najechania. Celuje w główny blok kontenera i poszczególne elementy linków społecznościowych.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie:**
        -   `.socialnetworklinks_block`: Główny kontener dla bloku linków społecznościowych.
        -   `.socialnetworklinks_block ul`: Lista nieuporządkowana zawierająca ikony społecznościowe.
        -   `.socialnetworklinks_block li`: Poszczególne elementy listy dla każdej ikony społecznościowej.
        -   `.socialnetworklinks_block li a`: Tag `<a>` dla każdego linku społecznościowego.
        -   `.socialnetworklinks_block li a i`: Element ikony (np. Font Awesome lub podobny, w zależności od motywu).
        -   Specyficzne klasy dla każdej sieci społecznościowej (np. `.facebook`, `.twitter` itp.) mogą być obecne lub mogą zostać dodane w celu niestandardowej stylizacji dla każdej sieci.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   **`socialnetworklinks/views/front/column.tpl`**:
        -   **Hook(i) renderowane w:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (lub podobny hook strony produktu w zależności od wersji PrestaShop i motywu).
        -   **Wyjście bloku wizualnego:** Ten szablon renderuje strukturę HTML dla bloku linków do sieci społecznościowych. Iteruje po skonfigurowanych adresach URL sieci społecznościowych i wyświetla ikonę (zazwyczaj za pomocą biblioteki ikon czcionek, takiej jak Font Awesome, która jest zazwyczaj dostarczana przez motyw lub rdzeń PrestaShop) dla każdego aktywnego linku. Każda ikona jest opakowana w tag `<a>` z `target="_blank"`, aby otworzyć link w nowej karcie.
        -   **Dostępne zmienne:**
            -   `$facebook_url`: Skonfigurowany URL Facebooka.
            -   `$twitter_url`: Skonfigurowany URL Twittera.
            -   `$youtube_url`: Skonfigurowany URL YouTube.
            -   `$google_url`: Skonfigurowany URL Google+.
            -   `$rss_url`: Skonfigurowany URL RSS.
            -   `$module_dir`: Podstawowy katalog modułu, przydatny do linkowania do zasobów modułu (choć nie jest intensywnie używany w tym konkretnym szablonie).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `SOCIALNETWORKLINKS_`.

    -   `PS_SOCIALNETWORKLINKS_FACEBOOK_URL`
    -   `PS_SOCIALNETWORKLINKS_TWITTER_URL`
    -   `PS_SOCIALNETWORKLINKS_YOUTUBE_URL`
    -   `PS_SOCIALNETWORKLINKS_GOOGLE_URL`
    -   `PS_SOCIALNETWORKLINKS_RSS_URL`
    -   `PS_SOCIALNETWORKLINKS_DISPLAY_HEADER`
    -   `PS_SOCIALNETWORKLINKS_DISPLAY_LEFT_COLUMN`
    -   `PS_SOCIALNETWORKLINKS_DISPLAY_RIGHT_COLUMN`
    -   `PS_SOCIALNETWORKLINKS_DISPLAY_FOOTER`
    -   `PS_SOCIALNETWORKLINKS_DISPLAY_PRODUCT_PAGE`
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` lub na samym początku `<body>`. | Służy do wyświetlania bloku linków społecznościowych w nagłówku sklepu. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie bocznej. | Służy do wyświetlania bloku linków społecznościowych w lewej kolumnie. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie bocznej. | Służy do wyświetlania bloku linków społecznościowych w prawej kolumnie. |
| `displayFooter` | Renderuje zawartość w stopce sklepu. | Służy do wyświetlania bloku linków społecznościowych w stopce. |
| `displayProductButtons` (lub podobny hook strony produktu) | Renderuje zawartość na stronie produktu, często w pobliżu przycisku „Dodaj do koszyka” lub opisu produktu. | Służy do wyświetlania bloku linków społecznościowych na poszczególnych stronach produktów. |
| `moduleRoutes` | (Niejawnie obsługiwane przez PrestaShop dla konfiguracji modułu) | Nie jest bezpośrednio używane do wyświetlania w front-office, ale jest częścią cyklu życia modułu. |
| `actionAdminControllerSetMedia` | (Niejawnie obsługiwane przez PrestaShop dla konfiguracji modułu) | Służy do ładowania CSS/JS w panelu administracyjnym dla strony konfiguracji modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Linki do sieci społecznościowych”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
