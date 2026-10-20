---
title: "Shortcodes - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu Shortcodes PrestaShop od MyPresta.eu."
sidebar:
  label: "Shortcodes"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Shortcodes na MyPresta.eu](https://mypresta.eu/modules/front-office-features/shortcodes.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/shortcodes/)
>
> ---


# Shortcodes

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)
Po zainstalowaniu modułu przejdź do **Moduły > Menedżer modułów** i wyszukaj „Shortcodes”. Kliknij przycisk „Konfiguruj”, aby uzyskać dostęp do jego ustawień.

Strona konfiguracji modułu Shortcodes jest prosta i skupia się na jednym, kluczowym ustawieniu:

#### Wyłącz wszystkie shortcode'y
-   **Co robi to ustawienie:** Jest to główny przełącznik, który kontroluje, czy moduł przetwarza i zastępuje shortcode'y na całej Twojej stronie internetowej.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (ustawione na „Włączone”):* Moduł będzie aktywnie skanował Twoje treści i pliki szablonu w poszukiwaniu rozpoznanych shortcode'ów (np. `[products]`, `[categories]`, `[html]`) i zastępował je odpowiednią dynamiczną treścią. Jest to zamierzony tryb działania modułu.
    -   *Gdy wyłączone (ustawione na „Wyłączone”):* Moduł przestanie przetwarzać wszystkie shortcode'y. Wszelkie shortcode'y, które umieściłeś w swoich treściach lub plikach szablonu, pojawią się po prostu jako zwykły tekst (np. `[products]` będzie widoczne jako `[products]` dla Twoich klientów) i nie zostaną zastąpione dynamiczną treścią.
-   **Zalecana wartość:** **Włączone**
-   **Scenariusz / przykład dla sprzedawcy:**
    -   Ustawisz to na „Włączone”, aby aktywować funkcjonalność shortcode'ów i wyświetlać dynamiczną treść.
    -   Możesz tymczasowo ustawić to na „Wyłączone”, jeśli debugujesz problem, wykonujesz konserwację lub jeśli chcesz wyłączyć całą dynamiczną treść generowaną przez shortcode'y w całym sklepie bez odinstalowywania modułu. Pamiętaj, aby zapisać zmiany po przełączeniu tego ustawienia.

:::tip
Po zmianie jakichkolwiek ustawień zawsze kliknij przycisk „Zapisz”, aby zastosować modyfikacje.
:::

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | Wyłącz wszystkie shortcode'y | Włączone | Kontroluje, czy moduł przetwarza i zastępuje shortcode'y dynamiczną treścią. Ustaw na „Włączone”, aby aktywować, „Wyłączone”, aby dezaktywować. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje shortcode'y wyświetlają się jako zwykły tekst (np. `[products]`) zamiast dynamicznej treści. Co jest nie tak?**
**O1:**
1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Shortcodes” jest zainstalowany i włączony.
2.  **Sprawdź konfigurację modułu:** Przejdź do strony konfiguracji modułu i upewnij się, że opcja „Wyłącz wszystkie shortcode'y” jest ustawiona na **„Włączone”**.
3.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
4.  **Poprawna składnia shortcode'a:** Dokładnie sprawdź, czy wpisałeś shortcode dokładnie tak, jak jest wymagane, włączając nawiasy `[]` i wszelkie parametry (np. `[products type="new"]`). Każda literówka uniemożliwi jego przetworzenie.

**P2: Dynamiczna treść (np. karuzela produktów) nie jest poprawnie ostylowana lub wygląda na uszkodzoną w moim szablonie.**
**O2:**
Zazwyczaj wskazuje to na konflikt CSS lub brakujące style specyficzne dla Twojego szablonu.
1.  **Kompatybilność z szablonem:** Chociaż moduł zapewnia podstawowe style, niestandardowe szablony mogą nadpisywać lub nie posiadać stylów dla niektórych elementów.
2.  **Pomoc programisty:** Może być konieczne, aby programista zbadał stronę za pomocą narzędzi deweloperskich przeglądarki (F12) w celu zidentyfikowania konfliktów CSS i dodania niestandardowych reguł CSS do Twojego szablonu, aby zapewnić wizualną integrację wyników shortcode'a. Plik CSS modułu (`cmsproductspro.css`) może być punktem wyjścia do odniesienia.

**P3: Czy mogę używać shortcode'ów w sklepach wielojęzycznych?**
**O3:** Tak, same shortcode'y są niezależne od języka. Treść, którą generują (np. nazwy produktów, opisy), będzie automatycznie wyświetlana w języku wybranym przez klienta, pod warunkiem, że Twoje produkty i kategorie mają tłumaczenia dla tego języka. Umieszczając shortcode'y na stronach CMS lub w opisach produktów, upewnij się, że edytujesz treść dla właściwego języka w panelu administracyjnym.

**P4: Dodałem shortcode do nowej strony CMS, ale nie pojawia się on w front-office.**
**O4:**
1.  **Status strony:** Upewnij się, że Twoja strona CMS jest włączona i widoczna w menu nawigacyjnym lub połączona z innej strony.
2.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
3.  **Umiejscowienie shortcode'a:** Sprawdź, czy shortcode jest umieszczony w obszarze treści, który jest faktycznie renderowany przez Twój szablon dla tej strony CMS. Niektóre szablony mogą mieć specyficzne bloki treści.

**P5: Jakie shortcode'y są dostępne i jakich parametrów mogę używać?**
**O5:** Dokumentacja modułu (ten przewodnik) lub strona konfiguracji modułu (jeśli je wymienia) powinny szczegółowo opisywać dostępne shortcode'y. Typowe shortcode'y to:
-   `[products]` (dla różnych list produktów, takich jak nowe, bestsellery, konkretne ID)
-   `[categories]` (do wyświetlania list kategorii)
-   `[html]` (do osadzania niestandardowego kodu HTML)
-   `[imageManufacturer]` (do wyświetlania obrazów producentów)
Będziesz musiał odwołać się do konkretnej implementacji modułu, aby uzyskać dokładne parametry (np. `limit`, `carousel`, `id`, `type`).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera techniczny przegląd dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzać moduł Shortcodes.

### 4.1 Przegląd architektury
Moduł Shortcodes (`cmsproductspro`) działa przede wszystkim jako filtr treści. Wpina się w proces renderowania wyjścia PrestaShop, aby przechwycić zawartość HTML, zanim zostanie wysłana do przeglądarki. Następnie używa wyrażeń regularnych do znajdowania i zastępowania predefiniowanych wzorców shortcode'ów dynamicznie generowaną zawartością HTML. Konfiguracja modułu jest minimalna, skupiając się na globalnym przełączniku włącz/wyłącz. Logika generowania treści jest hermetyzowana w głównej klasie modułu, wykorzystując podstawowe funkcjonalności PrestaShop do pobierania danych (produktów, kategorii, producentów).

### 4.2 Kontrolery (`controllers/`)
Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika konfiguracji i przetwarzania treści jest obsługiwana w głównym pliku modułu (`cmsproductspro.php`).

### 4.3 Klasy i modele rdzenia (`classes/`)
Ten moduł **nie** definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Cała logika rdzenia znajduje się w pliku `cmsproductspro.php`.

### 4.4 Zasoby JavaScript (`views/js/`)
Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Wszelkie dynamiczne zachowania (takie jak karuzele) zazwyczaj opierałyby się na istniejących bibliotekach JavaScript dostarczanych przez PrestaShop lub szablon (np. Owl Carousel, Slick Carousel), jeśli wynik shortcode'a zawiera takie komponenty.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   **`cmsproductspro/cmsproductspro.css`**
    *   **Zakres:** Stylizacja front-office dla klienta.
    *   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów zapewnia podstawową stylizację dla wyjścia HTML generowanego przez shortcode'y. Obejmuje to:
        *   Siatki produktów i karuzele (np. `.cmsproductspro-products-grid`, `.cmsproductspro-carousel`).
        *   Pojedyncze elementy produktu (np. `.cmsproductspro-product-item`, `.cmsproductspro-product-image`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`).
        *   Listy kategorii (np. `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`).
        *   Obrazy producentów (np. `.cmsproductspro-manufacturer-image`).
        *   Ogólny układ i responsywność dla tych elementów.
    *   **Kluczowe selektory klas CSS, które programiści mogą nadpisywać:** Programiści mogą celować w klasy takie jak `.cmsproductspro-products-grid`, `.cmsproductspro-product-item`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`, `.cmsproductspro-manufacturer-image`, aby dostosować wygląd treści generowanej przez shortcode w swoim szablonie.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Moduł używa kilku szablonów Smarty do renderowania dynamicznej treści dla różnych shortcode'ów. Szablony te znajdują się w `views/templates/`.

-   **Szablony hooków (`views/templates/hook/`)**: Ten moduł nie używa jawnie podkatalogu `hook/` dla swoich szablonów. Szablony znajdują się bezpośrednio w `views/templates/` i są renderowane na podstawie wykrytego shortcode'a.

-   **Szablony administracyjne (`views/templates/admin/`)**: Ten moduł nie zawiera żadnych specyficznych szablonów administracyjnych poza standardowym formularzem konfiguracji obsługiwanym przez `getContent()`.

-   **Szablony front-office (`views/templates/front/`)**:
    *   **`cmsproductspro/categories.tpl`**:
        *   **Cel:** Renderuje listę kategorii, zazwyczaj używaną przez shortcode `[categories]`.
        *   **Zmienne:** Oczekuje zmiennych takich jak `$categories` (tablica obiektów kategorii), `$display_subcategories`, `$image` itp.
        *   **Wynik:** Generuje HTML dla siatki lub listy kategorii, potencjalnie z obrazami i linkami.
    *   **`cmsproductspro/html.tpl`**:
        *   **Cel:** Renderuje surową zawartość HTML, używaną przez shortcode `[html]`.
        *   **Zmienne:** Oczekuje zmiennej `$content` zawierającej ciąg HTML do wyświetlenia.
        *   **Wynik:** Bezpośrednio wyświetla dostarczoną zawartość HTML.
    *   **`cmsproductspro/imageManufacturer.tpl`**:
        *   **Cel:** Wyświetla obraz producenta, używany przez shortcode `[imageManufacturer]`.
        *   **Zmienne:** Oczekuje `$manufacturer` (obiekt z danymi producenta, w tym ścieżką do obrazu) i potencjalnie `$link` do strony producenta.
        *   **Wynik:** Generuje tag `<img>` dla logo producenta, często opakowany w link.
    *   **`cmsproductspro/productGallery.tpl`**:
        *   **Cel:** Renderuje galerię produktów, potencjalnie z określonym układem lub funkcjami. Może to być bardziej ogólny szablon wyświetlania produktów.
        *   **Zmienne:** Oczekuje `$products` (tablica obiektów produktów) i innych opcji wyświetlania.
        *   **Wynik:** Struktura HTML dla galerii produktów.
    *   **`cmsproductspro/products-carousel.tpl`**:
        *   **Cel:** Renderuje listę produktów specjalnie zaprojektowaną do użycia w komponencie karuzeli.
        *   **Zmienne:** Oczekuje `$products` (tablica obiektów produktów) i potencjalnie opcji specyficznych dla karuzeli.
        *   **Wynik:** Struktura HTML dla listy produktów, często z klasami odpowiednimi dla biblioteki JavaScript karuzeli.
    *   **`cmsproductspro/products.tpl`**:
        *   **Cel:** Renderuje ogólną listę lub siatkę produktów, używaną przez shortcode `[products]`.
        *   **Zmienne:** Oczekuje `$products` (tablica obiektów produktów) i innych opcji wyświetlania, takich jak `$grid_class`, `$item_class`.
        *   **Wynik:** Struktura HTML dla siatki lub listy produktów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych. Jego konfiguracja jest przechowywana w tabeli `ps_configuration` przy użyciu kluczy takich jak `CMSPRODUCTSPRO_HIDE` (dla ustawienia „Wyłącz wszystkie shortcode'y”).

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionOutputHTMLBefore` | Wykonywany tuż przed wysłaniem końcowego wyjścia HTML do przeglądarki. | Jest to główny hook, w którym moduł przechwytuje całą zawartość strony, skanuje w poszukiwaniu shortcode'ów i wykonuje zamiany. |
| `displayHeader` | Wykonywany w sekcji `<head>` kodu HTML. | Służy do dołączania niezbędnych plików CSS (`cmsproductspro.css`) dla treści generowanej przez shortcode. |
| `actionAjaxDieProductControllerdisplayAjaxQuickviewBefore` | Wykonywany przed metodą `displayAjaxQuickview` w `ProductController` (dla modalnych okien szybkiego podglądu). | Ten hook zapewnia, że shortcode'y są również przetwarzane i zastępowane w treści ładowanej za pośrednictwem AJAX dla szybkich podglądów produktów, zachowując spójność. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Shortcodes”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
