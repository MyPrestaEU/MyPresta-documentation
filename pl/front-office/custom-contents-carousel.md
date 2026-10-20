---
title: "Karuzela niestandardowych treści - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Karuzela niestandardowych treści” od MyPresta.eu."
sidebar:
  label: "Karuzela niestandardowych treści - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Custom contents carousel na MyPresta.eu](https://mypresta.eu/modules/front-office-features/custom-contents-carousel.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/custom-contents-carousel/)
>
> ---


# Karuzela niestandardowych treści

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Karuzela niestandardowych treści” organizuje swoje ustawienia na kilku ekranach w Panelu administracyjnym PrestaShop. Najpierw skonfigurujesz ustawienia globalne, następnie utworzysz „Grupy” (które są Twoimi karuzelami), a na koniec dodasz „Elementy” (poszczególne slajdy) do każdej grupy.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Karuzela niestandardowych treści)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

- **Co robi to ustawienie:** Ten ekran obsługuje głównie ogólne ustawienia modułu i sprawdzanie aktualizacji.
- **Efekt zmiany tego ustawienia:**
  - `mypresta_updates`, `update_`, `updatev_`: Są to wewnętrzne ustawienia używane przez moduły MyPresta.eu do zarządzania aktualizacjami i sprawdzania wersji. Nie wpływają bezpośrednio na wyświetlanie w front-office, ale zapewniają, że moduł jest zawsze aktualny.
  - `CCAROUSEL_LIGHTSLIDER`: To ustawienie prawdopodobnie kontroluje aktywację biblioteki JavaScript LightSlider, która odpowiada za funkcjonalność karuzeli.
    - *Gdy włączone (TAK)*: Biblioteka LightSlider zostanie załadowana w Twoim front-office, umożliwiając prawidłowe działanie karuzel.
    - *Gdy wyłączone (NIE)*: Biblioteka LightSlider może się nie załadować, potencjalnie zakłócając wyświetlanie i funkcjonalność karuzeli.
- **Zalecana wartość:**
  - `CCAROUSEL_LIGHTSLIDER`: **TAK** (Włączone). Jest to kluczowe dla działania karuzeli.
  - Inne ustawienia: Pozostaw domyślne.
- **Scenariusz/przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz upewnić się, że wszystkie niezbędne skrypty są załadowane. Sprawdzasz, czy `CCAROUSEL_LIGHTSLIDER` jest włączony. Jeśli kiedykolwiek napotkasz problemy z niedziałającą karuzelą, będzie to jedno z pierwszych miejsc do sprawdzenia.

### 2.2 Dedykowany ekran administracyjny: Grupy niestandardowych treści (Panel administracyjny > Moduły > Karuzela niestandardowych treści > Grupy niestandardowych treści)

Ten ekran umożliwia tworzenie i zarządzanie poszczególnymi karuzelami. Każda „grupa” reprezentuje odrębną karuzelę, którą możesz następnie wypełnić slajdami.

- **Nazwa ekranu i lokalizacja w menu:** Znajdziesz to w **Moduły > Karuzela niestandardowych treści > Grupy niestandardowych treści** w menu Panelu administracyjnego PrestaShop.
- **Dostępne akcje i ustawienia:**
  - **Widok siatki**: Wyświetla listę wszystkich istniejących grup karuzeli. Możesz zobaczyć ich nazwy, status (aktywny/nieaktywny) i akcje.
  - **Dodaj nową grupę**: Kliknij przycisk „Dodaj nową”, aby utworzyć zupełnie nową karuzelę.
  - **Edytuj/Usuń grupę**: Dla każdej grupy będziesz mieć opcje edycji jej ustawień (np. nazwa, opcje wyświetlania) lub całkowitego usunięcia.
  - **Przełącznik statusu**: Szybko aktywuj lub dezaktywuj grupę karuzeli bez jej usuwania. Nieaktywna grupa nie pojawi się w Twoim front-office.
- **Efekt zmian:**
  - **Dodanie nowej grupy**: Tworzy nowy, pusty kontener karuzeli. Następnie będziesz musiał dodać do niego elementy (slajdy).
  - **Edycja grupy**: Umożliwia zmianę nazwy karuzeli, jej ustawień wyświetlania (np. auto-odtwarzanie, prędkość, liczba widocznych slajdów) i jej pozycji.
  - **Aktywacja/Dezaktywacja**: Kontroluje, czy karuzela jest widoczna dla Twoich klientów w front-office.
  - **Usunięcie grupy**: Trwale usuwa karuzelę i wszystkie powiązane z nią elementy (slajdy).
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Zacznij od utworzenia nowej grupy dla każdej karuzeli, którą chcesz wyświetlić (np. „Karuzela banerów na stronie głównej”, „Slider nowości”).
  2. Nadaj każdej grupie jasną, opisową nazwę.
  3. Skonfiguruj ustawienia wyświetlania grupy (np. auto-odtwarzanie, pętla, pauza po najechaniu myszką), aby dopasować je do pożądanego doświadczenia użytkownika.
  4. Po utworzeniu grupy przejdź do ekranu „Elementy niestandardowych treści”, aby dodać do niej slajdy.

### 2.3 Dedykowany ekran administracyjny: Elementy niestandardowych treści (Panel administracyjny > Moduły > Karuzela niestandardowych treści > Elementy niestandardowych treści)

Ten ekran służy do zarządzania poszczególnymi slajdami (elementami) w Twoich karuzelach. Każdy element może być obrazem, filmem, tekstem lub osadzoną treścią.

- **Nazwa ekranu i lokalizacja w menu:** Znajdziesz to w **Moduły > Karuzela niestandardowych treści > Elementy niestandardowych treści** w menu Panelu administracyjnego PrestaShop.
- **Dostępne akcje i ustawienia:**
  - **Widok siatki**: Wyświetla listę wszystkich pojedynczych slajdów, pokazując, do której grupy należą, ich typ treści i status.
  - **Dodaj nowy element**: Kliknij „Dodaj nowy”, aby utworzyć nowy slajd. Następnie wybierzesz grupę, do której należy, i zdefiniujesz jego zawartość.
  - **Edytuj/Usuń element**: Modyfikuj zawartość, link lub kolejność wyświetlania istniejącego slajdu lub usuń go.
  - **Przełącznik statusu**: Aktywuj lub dezaktywuj poszczególne slajdy. Nieaktywny slajd nie pojawi się w swojej karuzeli.
  - **Zmień kolejność metodą „przeciągnij i upuść”**: Łatwo zmieniaj kolejność wyświetlania slajdów w grupie.
- **Efekt zmian:**
  - **Dodanie nowego elementu**: Tworzy nowy slajd. Określisz jego zawartość (przesyłanie obrazu, URL wideo, tekst, HTML), link i przypiszesz go do jednej z istniejących grup karuzeli.
  - **Edycja elementu**: Umożliwia aktualizację zawartości, zmianę linku, modyfikację obrazu lub dostosowanie jego pozycji w karuzeli.
  - **Aktywacja/Dezaktywacja**: Kontroluje, czy konkretny slajd jest widoczny w swojej karuzeli.
  - **Usunięcie elementu**: Trwale usuwa slajd z jego karuzeli.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Wybierz grupę karuzeli, do której chcesz dodać slajdy (jeśli masz ich wiele).
  2. Kliknij „Dodaj nowy element” i wybierz typ treści (obraz, wideo, tekst, HTML).
  3. Prześlij obraz, wklej URL wideo lub wprowadź tekst/HTML.
  4. Dodaj odpowiedni link, jeśli slajd ma kierować klientów do produktu, kategorii lub strony zewnętrznej.
  5. Ustaw kolejność wyświetlania.
  6. Powtórz dla wszystkich slajdów w Twojej karuzeli.
  7. Użyj funkcji „przeciągnij i upuść”, aby precyzyjnie dostosować kolejność slajdów.

### 2.4 Dedykowany ekran administracyjny: index.php (ccarousel/controllers/admin/index.php)

Ten plik jest standardową praktyką PrestaShop w celu zabezpieczenia katalogów administracyjnych. Zazwyczaj zawiera prostą instrukcję `die('No direct script access allowed');` i sam w sobie nie przedstawia konfigurowalnego ekranu ani zarządzanej jednostki. Jest to środek bezpieczeństwa, a nie interfejs konfiguracji.

### 2.5 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | `CCAROUSEL_LIGHTSLIDER` | TAK | Włącza/wyłącza podstawową bibliotekę JavaScript dla funkcjonalności karuzeli. **Musi być TAK, aby karuzele działały.** |
| Grupy niestandardowych treści | Nazwa grupy | Zdefiniowana przez użytkownika | Identyfikuje Twoją karuzelę (np. „Banery na stronie głównej”). |
| Grupy niestandardowych treści | Status | Włączony | Kontroluje widoczność całej karuzeli w front-office. |
| Grupy niestandardowych treści | Ustawienia karuzeli | Zdefiniowane przez użytkownika | Kontroluje auto-odtwarzanie, prędkość, pętlę, nawigację itp. dla każdej karuzeli. |
| Elementy niestandardowych treści | Zawartość elementu | Zdefiniowana przez użytkownika | Rzeczywista zawartość slajdu (obraz, wideo, tekst, HTML). |
| Elementy niestandardowych treści | Link elementu | Opcjonalny URL | Gdzie slajd kieruje klientów po kliknięciu. |
| Elementy niestandardowych treści | Status | Włączony | Kontroluje widoczność poszczególnych slajdów w karuzeli. |
| Elementy niestandardowych treści | Pozycja | Zdefiniowana przez użytkownika | Określa kolejność slajdów w karuzeli. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moja karuzela nie wyświetla się na stronie głównej.**

-   **O:** Najpierw sprawdź, czy moduł „Karuzela niestandardowych treści” jest włączony w **Moduły > Menedżer modułów**. Następnie przejdź do **Moduły > Karuzela niestandardowych treści > Grupy niestandardowych treści** i upewnij się, że Twoja grupa karuzeli jest aktywna (zielony znacznik). Na koniec upewnij się, że masz co najmniej jeden aktywny „Element niestandardowych treści” przypisany do tej grupy. Sprawdź również, czy ustawienie `CCAROUSEL_LIGHTSLIDER` na głównej stronie konfiguracji modułu jest włączone.

**P2: Obrazy w mojej karuzeli są rozmazane lub zniekształcone.**

-   **O:** Upewnij się, że przesyłane obrazy są wysokiej jakości i mają odpowiednie wymiary dla miejsca, w którym wyświetlana jest karuzela. Jeśli Twój szablon ma konkretne zalecenia dotyczące rozmiaru obrazu dla banerów lub sliderów, spróbuj je dopasować. Moduł będzie skalować obrazy, ale kluczowe jest rozpoczęcie od dobrego obrazu źródłowego.

**P3: Karuzela nie przesuwa się ani nie odtwarza automatycznie.**

-   **O:** Jest to często problem z JavaScriptem.
    1.  Przejdź do **Moduły > Konfiguruj > Karuzela niestandardowych treści** i upewnij się, że `CCAROUSEL_LIGHTSLIDER` jest ustawione na „TAK”.
    2.  Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
    3.  Wyczyść pamięć podręczną przeglądarki.
    4.  Jeśli problem nadal występuje, może występować konflikt JavaScript z innym modułem lub Twoim szablonem. Sprawdź konsolę programisty przeglądarki (F12) pod kątem błędów JavaScript.

**P4: Jak zmienić kolejność slajdów w mojej karuzeli?**

-   **O:** Przejdź do **Moduły > Karuzela niestandardowych treści > Elementy niestandardowych treści**. Powinieneś zobaczyć listę swoich slajdów. Poszukaj kolumny ze strzałkami lub ikoną „przeciągnij i upuść”. Zazwyczaj możesz przeciągać i upuszczać wiersze, aby zmienić ich kolejność, lub może istnieć pole „Pozycja”, które możesz edytować. Pamiętaj, aby zapisać zmiany.

**P5: Czy mogę mieć wiele karuzel na różnych stronach?**

-   **O:** Moduł wykorzystuje głównie hook `displayHome`, co oznacza, że jest przeznaczony dla strony głównej. Chociaż możesz tworzyć wiele *grup* (karuzel), wszystkie zazwyczaj będą renderowane w tej samej pozycji hooka. Aby wyświetlać karuzele na różnych stronach lub w różnych pozycjach, wymagana byłaby niestandardowa integracja z szablonem lub dodatkowa rejestracja hooka (patrz Przewodnik dla programistów).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów utrzymujących lub rozszerzających moduł „Karuzela niestandardowych treści”.

### 4.1 Przegląd architektury

Moduł „Karuzela niestandardowych treści” stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller) dla swoich komponentów Back Office. Wykorzystuje klasę `Module` PrestaShop do podstawowej funkcjonalności oraz `AdminController` do zarządzania grupami treści i elementami. Wyświetlanie w front-office jest obsługiwane głównie za pomocą szablonu Smarty podłączonego do `displayHome`, z zasobami JavaScript (LightSlider) i CSS ładowanymi za pośrednictwem `displayHeader`. Trwałość danych jest zarządzana za pomocą niestandardowych klas `ObjectModel`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    Moduł nie zawiera żadnych dedykowanych kontrolerów front-office. Całe renderowanie front-office jest obsługiwane bezpośrednio przez główną klasę modułu (`ccarousel.php`) poprzez rejestrowanie hooków i renderowanie szablonów.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminCustomContentsGroupsController.php`
        -   Nazwa klasy: `AdminCustomContentsGroupsController`
        -   Klasa nadrzędna: `ModuleAdminController`
        -   Odpowiedzialność: Zarządza encją `gcarousel` (grupami karuzeli). Ten kontroler obsługuje listowanie, dodawanie, edytowanie i usuwanie grup karuzeli. Definiuje pola formularza do konfiguracji grup (np. nazwa, status, ustawienia karuzeli, takie jak auto-odtwarzanie, prędkość).
    -   `controllers/admin/AdminCustomContentsItemsController.php`
        -   Nazwa klasy: `AdminCustomContentsItemsController`
        -   Klasa nadrzędna: `ModuleAdminController`
        -   Odpowiedzialność: Zarządza encją `gcitem` (poszczególnymi slajdami/elementami karuzeli). Ten kontroler obsługuje listowanie, dodawanie, edytowanie i usuwanie slajdów. Definiuje pola formularza dla zawartości slajdu (przesyłanie obrazu, URL wideo, tekst/HTML, link, pozycja, powiązana grupa). Zarządza również funkcjonalnością zmiany kolejności slajdów metodą „przeciągnij i upuść”.
    -   `controllers/admin/index.php`
        -   Nazwa klasy: N/A (prosty plik PHP)
        -   Klasa nadrzędna: N/A
        -   Odpowiedzialność: Środek bezpieczeństwa zapobiegający bezpośredniemu listowaniu katalogów lub dostępowi. Zawiera `die('No direct script access allowed');`.

### 4.3 Podstawowe klasy i modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że definicje `ObjectModel` dla `gcarousel` i `gcitem` są prawdopodobnie osadzone bezpośrednio w głównym pliku modułu (`ccarousel.php`) lub w odpowiednich plikach `AdminController`.

-   **`gcarousel` (Model grupy karuzeli)**:

    -   Prawdopodobnie rozszerza `ObjectModel`.
    -   Współdziała z niestandardową tabelą bazy danych (np. `ps_gcarousel`).
    -   Pola `$definition` obejmowałyby: `id_gcarousel`, `name`, `active`, `settings` (prawdopodobnie serializowana tablica lub ciąg JSON dla opcji wyświetlania karuzeli).
    -   Kluczowe metody: `add()`, `update()`, `delete()`, `getGroups()`.
-   **`gcitem` (Model elementu/slajdu karuzeli)**:

    -   Prawdopodobnie rozszerza `ObjectModel`.
    -   Współdziała z niestandardową tabelą bazy danych (np. `ps_gcitem`).
    -   Pola `$definition` obejmowałyby: `id_gcitem`, `id_gcarousel` (klucz obcy), `position`, `active`, `type` (obraz, wideo, tekst, html), `content` (ścieżka do obrazu, URL wideo, tekst), `link`, `title`, `description` (dla obsługi wielu języków).
    -   Kluczowe metody: `add()`, `update()`, `delete()`, `getItemsByGroup()`, `updatePosition()`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `ccarousel/lib/src/js/lightslider.js`
    -   Zakres: Front-office.
    -   Odpowiedzialność: Jest to podstawowa biblioteka LightSlider. Inicjalizuje i zarządza funkcjonalnością karuzeli. Wiąże słuchaczy zdarzeń dla nawigacji (strzałki, kropki), obsługuje gesty dotyku/przesuwania, auto-odtwarzanie, zapętlanie i responsywne dostosowania. Metoda `hookDisplayHeader` lub `hookDisplayHome` modułu zazwyczaj dodaje ten skrypt do kolejki, a następnie skrypt inline lub oddzielny plik JS modułu wywołuje `$('#your-carousel-selector').lightSlider({...});` w celu inicjalizacji konkretnych karuzel.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `ccarousel/css.css`
    -   Zakres: Front-office.
    -   Odpowiedzialność: Prawdopodobnie zawiera niestandardowe style specyficzne dla modułu „Karuzela niestandardowych treści”, nadpisujące lub rozszerzające podstawowe style LightSlider, aby pasowały do domyślnego szablonu PrestaShop lub zapewniały modułowe dostosowania wizualne.
-   `ccarousel/lib/src/css/ccarousel.css`
    -   Zakres: Front-office.
    -   Odpowiedzialność: Może to być podstawowy arkusz stylów dla struktury modułu lub placeholder. Biorąc pod uwagę nazwę, prawdopodobnie są to style specyficzne dla modułu.
-   `ccarousel/lib/src/css/lightslider.css`
    -   Zakres: Front-office.
    -   Odpowiedzialność: Domyślny arkusz stylów dla biblioteki LightSlider. Zapewnia podstawowe style dla kontenera karuzeli, slajdów, strzałek nawigacyjnych i kropek paginacji. Programiści mogą nadpisać te style w pliku `custom.css` swojego szablonu lub modyfikując `ccarousel/css.css`.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `ccarousel/views/templates/hook/ccarousel.tpl`
        -   Renderowany w: `displayHome` (i potencjalnie innych hookach, jeśli skonfigurowano w module).
        -   Wyjścia: Struktura HTML dla jednej lub więcej karuzel. Ten szablon iteruje przez grupy karuzeli i powiązane z nimi elementy, generując niezbędne elementy `<ul>` i `<li>`, których oczekuje LightSlider. Zawiera tagi obrazów, osadzone filmy lub surową zawartość HTML w zależności od typu elementu, wraz z linkami. Prawdopodobnie zawiera również wywołanie inicjalizacyjne JavaScript dla LightSlider, przekazując opcje konfiguracji pobrane z ustawień `gcarousel`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_gcarousel`: Przechowuje informacje o każdej grupie karuzeli.
        -   `id_gcarousel` (PK, INT)
        -   `name` (VARCHAR)
        -   `active` (TINYINT)
        -   `settings` (TEXT lub JSON, dla serializowanych opcji LightSlider)
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)
    -   `ps_gcitem`: Przechowuje informacje o każdym pojedynczym slajdzie/elemencie.
        -   `id_gcitem` (PK, INT)
        -   `id_gcarousel` (FK do `ps_gcarousel`, INT)
        -   `position` (INT)
        -   `active` (TINYINT)
        -   `type` (VARCHAR, np. ‘image’, ‘video’, ‘text’, ‘html’)
        -   `content` (TEXT, przechowuje ścieżkę do obrazu, URL wideo lub surowy tekst/HTML)
        -   `link` (VARCHAR)
        -   `title` (VARCHAR, dla wielu języków)
        -   `description` (TEXT, dla wielu języków)
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)
    -   `ps_configuration`: Przechowuje wartości konfiguracyjne specyficzne dla modułu, takie jak `CCAROUSEL_LIGHTSLIDER`, `MYPRESTA_UPDATES` itp.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Dodaje do kolejki niezbędne pliki CSS (`lightslider.css`, `ccarousel.css`) i JavaScript (`lightslider.js`), aby karuzela działała i była poprawnie ostylowana. |
| `displayHome` | W głównym obszarze treści strony głównej. | Renderuje szablon `ccarousel.tpl`, który generuje strukturę HTML dla aktywnych grup karuzeli i ich elementów, wraz ze skryptem inicjalizującym LightSlider. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz upewnienia się, że używasz najnowszej, najbezpieczniejszej wersji modułu „Karuzela niestandardowych treści”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
