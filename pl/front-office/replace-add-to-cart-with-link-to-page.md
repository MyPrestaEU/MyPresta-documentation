---
title: "Zastąp dodaj do koszyka linkiem do strony - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Zastąp dodaj do koszyka linkiem do strony” od MyPresta.eu."
sidebar:
  label: "Zastąp dodaj do koszyka linkiem do strony - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Replace add to cart with link to page na MyPresta.eu](https://mypresta.eu/modules/front-office-features/replace-add-to-cart-with-link-to-page.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/replace-add-to-cart-with-link-to-page/)
>
> ---


# Zastąp dodaj do koszyka linkiem do strony

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym kontrolujesz globalne zachowanie modułu.

-   **Włączony**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania funkcjonalności modułu w całym sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł zacznie zastępować przyciski „Dodaj do koszyka” niestandardowymi linkami na podstawie ustawień specyficznych dla produktu i innych globalnych konfiguracji.
        -   *Gdy wyłączony:* Moduł będzie nieaktywny, a wszystkie przyciski „Dodaj do koszyka” powrócą do domyślnego zachowania PrestaShop.
    -   **Zalecana wartość:** TAK (aby aktywować moduł).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz wyłączyć jego funkcjonalność bez odinstalowywania go, możesz ustawić to na NIE. Do aktywnego użytku powinno być TAK.
-   **Tekst przycisku**

    -   **Co robi to ustawienie:** Definiuje tekst, który pojawi się na niestandardowym przycisku, zastępując „Dodaj do koszyka”. Ten tekst można przetłumaczyć na różne języki.
    -   **Efekt zmiany tego ustawienia:** Tekst na przycisku zmieni się na określoną wartość.
    -   **Zalecana wartość:** Coś opisowego, np. „Dowiedz się więcej”, „Poproś o wycenę”, „Zobacz szczegóły” lub „Odwiedź stronę partnera”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli linkujesz do zewnętrznej strony w celu uzyskania więcej informacji, możesz ustawić to na „Dowiedz się więcej”. Jeśli kierujesz klientów do formularza wyceny, odpowiednie byłoby „Poproś o wycenę”.
-   **Ukryj pole ilości**

    -   **Co robi to ustawienie:** Kontroluje, czy pole wprowadzania ilości (gdzie klienci wybierają, ile przedmiotów dodać) jest widoczne na stronach produktów, gdy moduł jest aktywny.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Selektor ilości zostanie ukryty, ponieważ nie jest istotny, gdy przycisk przekierowuje zamiast dodawać do koszyka.
        -   *Gdy wyłączony:* Selektor ilości pozostanie widoczny, co może być mylące, jeśli przycisk nie dodaje do koszyka.
    -   **Zalecana wartość:** TAK.
    -   **Scenariusz / przykład dla sprzedawcy:** Ponieważ przycisk nie dodaje już do koszyka, zazwyczaj nie ma potrzeby pola ilości. Ukrycie go upraszcza interfejs i zapobiega zamieszaniu.
-   **Klasa CSS przycisku dodaj do koszyka na stronie produktu**

    -   **Co robi to ustawienie:** Pozwala określić niestandardową klasę CSS dla przycisku zastępczego na stronie produktu. Jest to przydatne do stylizowania przycisku tak, aby pasował do Twojego motywu lub aby go wyróżnić.
    -   **Efekt zmiany tego ustawienia:** Przycisk odziedziczy style zdefiniowane przez tę klasę CSS w arkuszu stylów Twojego motywu.
    -   **Zalecana wartość:** Pozostaw puste, jeśli domyślne stylizowanie przycisku Twojego motywu jest akceptowalne, lub użyj klasy takiej jak `btn btn-primary` lub `my-custom-button`, jeśli masz specyficzne style.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw używa `btn-success` dla głównych przycisków akcji, możesz wpisać `btn-success` tutaj, aby Twój niestandardowy przycisk był zielony i widoczny.
-   **Klasa CSS ilości**

    -   **Co robi to ustawienie:** Pozwala określić klasę CSS dla pola wprowadzania ilości na stronie produktu. Jest to przede wszystkim do zaawansowanego stylizowania lub jeśli musisz celować w pole ilości za pomocą niestandardowego CSS.
    -   **Efekt zmiany tego ustawienia:** Pole wprowadzania ilości otrzyma tę klasę CSS.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzną potrzebę stylizacji.
    -   **Scenariusz / przykład dla sprzedawcy:** Deweloper może użyć tego do zastosowania określonej szerokości lub wypełnienia do pola ilości, jeśli nie jest ono ukryte.
-   **Zastosuj moduł do listy produktów**

    -   **Co robi to ustawienie:** Określa, czy funkcjonalność modułu (zastępowanie „Dodaj do koszyka” niestandardowym linkiem) dotyczy również przycisków produktów wyświetlanych na listach (np. strony kategorii, wyniki wyszukiwania, wyróżnione produkty na stronie głównej).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przyciski „Dodaj do koszyka” na listach produktów również zostaną zastąpione niestandardowym linkiem.
        -   *Gdy wyłączony:* Tylko przycisk „Dodaj do koszyka” na stronie produktu zostanie zmieniony; przyciski na listach produktów zachowają swoje domyślne zachowanie.
    -   **Zalecana wartość:** TAK, dla spójności w całym sklepie, zwłaszcza jeśli niestandardowy link jest kluczową częścią Twojego lejka sprzedażowego.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli wszystkie produkty wymagające tego niestandardowego linku to usługi, które wymagają wyceny, chcesz, aby to było włączone, aby klienci nie próbowali „dodawać do koszyka” ze strony kategorii.
-   **Klasa CSS elementu z produktem**

    -   **Co robi to ustawienie:** Jest to ustawienie techniczne, które pomaga modułowi zidentyfikować główny kontener dla produktu w widoku listy. Jest to kluczowe, aby moduł poprawnie znalazł i zmodyfikował przycisk „Dodaj do koszyka” w każdym elemencie produktu.
    -   **Efekt zmiany tego ustawienia:** Jeśli jest nieprawidłowe, moduł może nie zastosować swoich zmian do elementów listy produktów.
    -   **Zalecana wartość:** Jest to bardzo zależne od motywu. Typowe wartości to `product-miniature`, `product-container`, `product-item`. Może być konieczne sprawdzenie kodu HTML Twojego motywu, aby znaleźć poprawną klasę.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw używa `<div class="product-card">` dla każdego produktu na liście, wpisałbyś tutaj `product-card`.
-   **Klasa CSS** (Prawdopodobnie odnosi się do samego przycisku „Dodaj do koszyka” w elemencie listy produktów)

    -   **Co robi to ustawienie:** Określa klasę CSS przycisku „Dodaj do koszyka” w elementach listy produktów. Pomaga to modułowi celować w poprawny przycisk do zastąpienia.
    -   **Efekt zmiany tego ustawienia:** Jeśli jest nieprawidłowe, moduł może nie zastąpić przycisku „Dodaj do koszyka” na listach produktów.
    -   **Zalecana wartość:** Jest to bardzo zależne od motywu. Typowe wartości to `add-to-cart`, `product-add-to-cart`, `btn-primary`. Sprawdź kod HTML swojego motywu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli przycisk „Dodaj do koszyka” w listach Twojego motywu ma klasę `btn-add-to-cart`, wpisałbyś to tutaj.
-   **Klasa CSS pola ilości na liście produktów**

    -   **Co robi to ustawienie:** Podobnie jak w ustawieniu strony produktu, pozwala to określić klasę CSS dla pola wprowadzania ilości, gdy produkty są wyświetlane na liście. Służy to do ukrycia go, jeśli `Ukryj pole ilości` jest włączone.
    -   **Efekt zmiany tego ustawienia:** Jeśli jest nieprawidłowe, pole ilości może pozostać widoczne na listach produktów, nawet jeśli wybrałeś jego ukrycie.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzną potrzebę stylizacji lub jeśli pole ilości nie jest poprawnie ukrywane. Sprawdź kod HTML swojego motywu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw używa `product-quantity-input` dla pola ilości na listach, wpisałbyś to tutaj.
-   **Ukryj dymek nad przyciskiem**

    -   **Co robi to ustawienie:** Kontroluje, czy domyślny dymek PrestaShop (często pokazujący „Dodaj do koszyka” lub podobne) pojawia się po najechaniu kursorem na niestandardowy przycisk.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Dymek zostanie ukryty, zapobiegając potencjalnie mylącym komunikatom.
        -   *Gdy wyłączony:* Domyślny dymek może nadal się pojawiać, co może kolidować z przeznaczeniem niestandardowego przycisku.
    -   **Zalecana wartość:** TAK.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój niestandardowy przycisk mówi „Poproś o wycenę”, nie chcesz, aby wyskakiwał dymek mówiący „Dodaj do koszyka”. Ukrycie go zapewnia jasny komunikat.
-   **Dodaj rel=“nofollow”**

    -   **Co robi to ustawienie:** Dodaje atrybut `rel="nofollow"` do niestandardowego linku. Informuje to wyszukiwarki, aby nie śledziły linku i nie przekazywały żadnego „link juice” do miejsca docelowego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Link będzie miał `rel="nofollow"`, co jest przydatne dla linków zewnętrznych, których nie chcesz popierać, lub dla linków wewnętrznych, które nie są krytyczne dla SEO (np. strony logowania).
        -   *Gdy wyłączony:* Link będzie standardowym, śledzonym linkiem.
    -   **Zalecana wartość:** TAK dla linków zewnętrznych, zwłaszcza linków afiliacyjnych lub linków do stron, których nie kontrolujesz w pełni. NIE dla linków wewnętrznych w Twojej własnej witrynie, które chcesz, aby wyszukiwarki indeksowały.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli linkujesz do strony internetowej partnera afiliacyjnego, włączenie `nofollow` jest najlepszą praktyką, aby uniknąć potencjalnych kar SEO i jasno wskazać, że jest to link sponsorowany lub zewnętrzny.
-   **Otwórz linki w nowym oknie (karcie)**

    -   **Co robi to ustawienie:** Określa, czy niestandardowy link otwiera się w tej samej karcie przeglądarki, czy w nowej.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Link otworzy się w nowej karcie przeglądarki, pozostawiając stronę Twojego sklepu otwartą w oryginalnej karcie.
        -   *Gdy wyłączony:* Link otworzy się w tej samej karcie, nawigując klienta poza Twój sklep.
    -   **Zalecana wartość:** TAK dla linków zewnętrznych, aby utrzymać klientów na Twojej stronie. NIE dla linków wewnętrznych, gdzie chcesz, aby klient nawigował w Twoim sklepie.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli kierujesz klientów na zewnętrzną stronę partnera, otwarcie w nowej karcie jest zazwyczaj lepsze, aby mogli łatwo wrócić na stronę Twojego produktu.
-   **Widoczność modułu dla wybranych produktów**

    -   **Co robi to ustawienie:** Jest to kluczowe ustawienie, które definiuje, *które* produkty będą miały zastąpiony przycisk „Dodaj do koszyka”. Działa w połączeniu z ustawieniami specyficznymi dla produktu, które znajdziesz na stronie edycji każdego produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Włączony:* Moduł będzie stosowany tylko do produktów, dla których wyraźnie zdefiniowałeś niestandardowy adres URL w ich ustawieniach produktu.
        -   *Wyłączony:* Moduł nie będzie stosowany do żadnych produktów, niezależnie od ich indywidualnych ustawień.
    -   **Zalecana wartość:** Włączony. Pozwala to selektywnie stosować funkcję niestandardowego linku do konkretnych produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zastąpić przycisk „Dodaj do koszyka” tylko dla mebli wykonanych na zamówienie, a nie dla standardowych akcesoriów. Włączyłbyś to ustawienie, a następnie przeszedł do każdego produktu meblowego i ustawił jego niestandardowy adres URL.

#### Ustawienia specyficzne dla produktu (Panel administracyjny > Katalog > Produkty > Edytuj produkt > Zakładka Moduły)

Po zainstalowaniu i włączeniu modułu, podczas edycji poszczególnych produktów znajdziesz nowe ustawienia.

-   **Pole URL produktu**
    -   **Co robi to ustawienie:** Tutaj wprowadzasz konkretny adres URL, na który przycisk „Dodaj do koszyka” dla *tego konkretnego produktu* będzie przekierowywał.
    -   **Efekt zmiany tego ustawienia:** Gdy klient kliknie niestandardowy przycisk na stronie tego produktu (lub na liście, jeśli włączone), zostanie przeniesiony na ten adres URL.
    -   **Zalecana wartość:** Pełny, prawidłowy adres URL (np. `https://example.com/request-a-quote` lub `/contact-us`).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla produktu „Usługa projektowania na zamówienie” możesz wpisać tutaj `https://twoj-sklep.com/kontakt?temat=Zapytanie%20o%20projekt%20na%20zamowienie`.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminAtcurlSearchController (Panel administracyjny > Moduły > Zastąp dodaj do koszyka linkiem do strony > Konfiguruj > Zakładka „Wybrane produkty”)

Ten ekran zapewnia scentralizowany sposób zarządzania i przeglądania, które produkty mają skonfigurowane niestandardowe adresy URL.

-   **Nazwa ekranu i lokalizacja w menu:** Dostęp do tego ekranu uzyskujesz, przechodząc do **Moduły > Menedżer modułów**, znajdując „Zastąp dodaj do koszyka linkiem do strony”, klikając „Konfiguruj”, a następnie wybierając zakładkę „Wybrane produkty” (lub podobną, w zależności od wersji modułu).
-   **Dostępne akcje i ustawienia:** Ten ekran zazwyczaj wyświetla siatkę lub listę produktów, które obecnie mają zdefiniowany niestandardowy adres URL.
    -   **Kolumny:** Zazwyczaj zobaczysz kolumny takie jak ID produktu, Nazwa produktu i Niestandardowy adres URL.
    -   **Wyszukiwanie/Filtrowanie:** Mogą istnieć opcje wyszukiwania lub filtrowania, aby szybko znaleźć konkretne produkty.
    -   **Edytuj/Usuń:** Możesz mieć bezpośrednie linki do edycji produktu (które przenoszą Cię do standardowej strony edycji produktu) lub usunięcia niestandardowego adresu URL dla produktu bezpośrednio z tej listy.
-   **Efekt zmian:**
    -   Modyfikacja adresu URL tutaj (jeśli dostępna jest bezpośrednia edycja) lub za pośrednictwem strony edycji produktu natychmiast zmieni miejsce, do którego przycisk przekierowuje dla tego produktu.
    -   Usunięcie produktu z tej listy (lub wyczyszczenie jego niestandardowego adresu URL na stronie edycji produktu) przywróci jego przycisk „Dodaj do koszyka” do domyślnego zachowania PrestaShop.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu, aby szybko sprawdzić, które produkty korzystają z funkcji niestandardowego linku. Jeśli musisz zaktualizować wiele linków produktów, ten widok pomoże Ci śledzić. Aby dodać nowe linki, zazwyczaj bardziej efektywne jest przejście bezpośrednio do strony edycji produktu.

#### index.php (atcurl/controllers/admin/index.php)

Ten plik jest plikiem zastępczym i zazwyczaj nie reprezentuje ekranu administracyjnego dostępnego dla użytkownika. W PrestaShop pliki `index.php` w katalogach kontrolerów są często używane do zapobiegania bezpośredniemu listowaniu katalogów lub do dołączania innych plików. Nie jest to ekran konfiguracji dla sprzedawców.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włączony | TAK | Główny przełącznik do aktywacji/dezaktywacji funkcjonalności modułu. |
| | Tekst przycisku | „Dowiedz się więcej” (przykład) | Tekst wyświetlany na niestandardowym przycisku. |
| | Ukryj pole ilości | TAK | Ukrywa selektor ilości na stronach produktów. |
| | Klasa CSS przycisku dodaj do koszyka na stronie produktu | (Puste / Zależne od motywu) | Niestandardowa klasa CSS dla przycisku na stronach produktów. |
| | Klasa CSS ilości | (Puste) | Niestandardowa klasa CSS dla pola ilości na stronach produktów. |
| | Zastosuj moduł do listy produktów | TAK | Rozszerza funkcjonalność modułu na strony list produktów. |
| | Klasa CSS elementu z produktem | `product-miniature` (przykład) | Pomaga modułowi zidentyfikować kontenery produktów na listach. |
| | Klasa CSS (przycisk Dodaj do koszyka na liście) | `add-to-cart` (przykład) | Pomaga modułowi zidentyfikować przyciski „Dodaj do koszyka” na listach. |
| | Klasa CSS pola ilości na liście produktów | (Puste) | Niestandardowa klasa CSS dla pola ilości na listach produktów. |
| | Ukryj dymek nad przyciskiem | TAK | Zapobiega domyślnemu dymkowi „Dodaj do koszyka” na niestandardowym przycisku. |
| | Dodaj rel=“nofollow” | TAK (dla zewnętrznych) / NIE (dla wewnętrznych) | Dodaje atrybut `nofollow` do niestandardowego linku. |
| | Otwórz linki w nowym oknie (karcie) | TAK (dla zewnętrznych) / NIE (dla wewnętrznych) | Otwiera niestandardowy link w nowej karcie przeglądarki. |
| | Widoczność modułu dla wybranych produktów | Włączony | Aktywuje konfigurację URL specyficzną dla produktu. |
| **Strona edycji produktu (zakładka Moduły)** | Pole URL produktu | (Niestandardowy URL) | Definiuje konkretny adres URL przekierowania dla *tego* produktu. |
| **AdminAtcurlSearchController** | Siatka produktów z niestandardowymi adresami URL | N/A | Scentralizowany widok do zarządzania produktami z niestandardowymi linkami. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój przycisk „Dodaj do koszyka” nie zmienia się, nawet po skonfigurowaniu adresu URL.**
O1:

-   **Sprawdź status modułu:** Najpierw upewnij się, że przełącznik „Włączony” na głównej stronie konfiguracji modułu jest ustawiony na TAK.
-   **Sprawdź widoczność produktu:** Upewnij się, że „Widoczność modułu dla wybranych produktów” jest ustawiona na „Włączony” na stronie konfiguracji modułu.
-   **Sprawdź URL produktu:** Zweryfikuj, czy wprowadziłeś prawidłowy adres URL w polu „URL produktu” dla konkretnego produktu, który testujesz (na stronie edycji produktu w zakładce „Moduły”).
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop buforuje stare treści.
-   **Kompatybilność z motywem:** Twój motyw może używać niestandardowych klas CSS dla przycisku „Dodaj do koszyka” lub kontenerów produktów. Sprawdź ustawienia „Klasa CSS elementu z produktem” i „Klasa CSS” na stronie konfiguracji modułu. Może być konieczne użycie narzędzi deweloperskich przeglądarki (F12), aby sprawdzić kod HTML i znaleźć poprawne klasy.

**P2: Pole ilości jest nadal widoczne, mimo że wybrałem jego ukrycie.**
O2:

-   **Sprawdź „Ukryj pole ilości”:** Upewnij się, że to ustawienie jest włączone na stronie konfiguracji modułu.
-   **Sprawdź „Klasa CSS pola ilości”:** Jeśli Twój motyw używa niestandardowej klasy dla pola ilości, moduł może nie być w stanie go znaleźć i ukryć. Użyj narzędzi deweloperskich przeglądarki, aby sprawdzić pole wprowadzania ilości i wprowadź jego klasę CSS w ustawieniu „Klasa CSS ilości” (dla strony produktu) i „Klasa CSS pola ilości na liście produktów” (dla list produktów).
-   **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P3: Moduł działa na stronach produktów, ale nie na stronach kategorii/list.**
O3:

-   **Sprawdź „Zastosuj moduł do listy produktów”:** Upewnij się, że to ustawienie jest włączone na stronie konfiguracji modułu.
-   **Sprawdź klasy CSS dla list:** Moduł musi wiedzieć, jak Twój motyw strukturyzuje listy produktów. Zweryfikuj, czy ustawienia „Klasa CSS elementu z produktem” i „Klasa CSS” (dla przycisku) są poprawne dla Twojego motywu. Często różnią się one od klas na stronie produktu. Użyj narzędzi deweloperskich przeglądarki, aby sprawdzić elementy na stronie kategorii.
-   **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop.

**P4: Mój niestandardowy przycisk nie wygląda prawidłowo (niewłaściwy kolor, rozmiar itp.).**
O4:

-   **Klasa CSS do stylizacji:** Użyj ustawienia „Klasa CSS przycisku dodaj do koszyka na stronie produktu”. Wprowadź klasę CSS, która już istnieje w Twoim motywie i zapewnia pożądaną stylizację (np. `btn btn-primary`, `btn-success`).
-   **Niestandardowy CSS:** Jeśli potrzebujesz unikalnej stylizacji, będziesz musiał dodać niestandardowy CSS do swojego motywu. Możesz celować w przycisk, używając klasy, którą ustawiłeś w konfiguracji modułu, lub sprawdzając jego kod HTML. Na przykład:

    ```
    .my-custom-button-class { background-color: #ff6600; color: white; border-radius: 5px; padding: 10px 20px;}
    ```

    Dodaj ten CSS do niestandardowego pliku CSS swojego motywu lub za pośrednictwem modułu niestandardowego CSS.
-   **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop.

**P5: Jak przetłumaczyć tekst przycisku na inne języki?**
O5:

-   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz język, który chcesz przetłumaczyć.
-   Znajdź moduł „Zastąp dodaj do koszyka linkiem do strony”. Zobaczysz tam pole „Tekst przycisku”, umożliwiające wprowadzenie tłumaczeń dla każdego języka.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zastąp dodaj do koszyka linkiem do strony” (`atcurl`) to standardowy moduł PrestaShop, zgodny z wzorcem MVC. Przede wszystkim rozszerza istniejącą funkcjonalność PrestaShop poprzez hooki, aby modyfikować wyświetlanie stron produktów i list produktów w front-office. Konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu i przechowywana w `ps_configuration`. Adresy URL specyficzne dla produktu są przechowywane jako `Product::specific_fields` lub potencjalnie w niestandardowej tabeli, a kontroler administracyjny (`AdminAtcurlSearchController`) zapewnia interfejs zarządzania. JavaScript jest intensywnie używany do dynamicznego zastępowania przycisków i ukrywania elementów w front-office.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Ten moduł nie zawiera żadnych dedykowanych kontrolerów front-office. Wszystkie modyfikacje front-office są obsługiwane za pomocą hooków i JavaScriptu.
-   **Kontrolery administracyjne Back-Office**:

    -   `atcurl/controllers/admin/AdminAtcurlSearchController.php`
        -   **Nazwa klasy i klasa nadrzędna:** `AdminAtcurlSearchController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja:** Ten kontroler jest prawdopodobnie odpowiedzialny za wyświetlanie siatki lub listy produktów, które mają skonfigurowany niestandardowy adres URL przez moduł. Zapewnia scentralizowany widok do zarządzania tymi powiązaniami produktów, potencjalnie umożliwiając szybką edycję lub usunięcie niestandardowego adresu URL. Nie zarządza dedykowanym `ObjectModel`, ale raczej wchodzi w interakcje z danymi produktu i konfiguracją modułu.
    -   `atcurl/controllers/admin/index.php`
        -   Jest to standardowy plik zastępczy PrestaShop, zazwyczaj zawierający `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` w celu zapobiegania bezpośredniemu listowaniu katalogów i przekierowywania do głównego panelu administracyjnego. Nie dostarcza żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie wydaje się definiować żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Adresy URL specyficzne dla produktu są prawdopodobnie przechowywane jako `Product::specific_fields` lub bezpośrednio w tabeli `ps_configuration`, kluczowane przez ID produktu, lub potencjalnie niestandardowe pole dodane do encji produktu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `atcurl/lib/js/admin/atcurl177.js`
    -   **Zakres:** Back-office (Admin).
    -   **Odpowiedzialność:** Prawdopodobnie obsługuje logikę specyficzną dla strony konfiguracji modułu lub `AdminAtcurlSearchController` dla wersji PrestaShop 1.7.7+. Może to obejmować wywołania AJAX do zapisywania ustawień, dynamiczne aktualizacje interfejsu użytkownika lub interakcje z narzędziem wyszukiwania/wyboru produktów.
-   `atcurl/lib/js/front/atcurl-list-177.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Specjalnie celuje w strony list produktów (kategoria, wyszukiwanie, bloki strony głównej). Nasłuchuje zmian DOM (np. gdy produkty są ładowane za pomocą AJAX) i dynamicznie zastępuje przyciski „Dodaj do koszyka” niestandardowym linkiem, ukrywa pola ilości i stosuje niestandardowe klasy CSS zgodnie z konfiguracją. Jest dostosowany do motywów PrestaShop 1.7.7+.
-   `atcurl/lib/js/front/atcurl177.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Przede wszystkim celuje w pojedynczą stronę produktu. Identyfikuje przycisk „Dodaj do koszyka”, zastępuje go niestandardowym linkiem, ukrywa pole wprowadzania ilości i stosuje atrybuty `nofollow` lub `target="_blank"` na podstawie ustawień modułu. Obsługuje również ukrywanie dymków. Dostosowany do motywów PrestaShop 1.7.7+.
-   `atcurl/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Back-office (Admin).
    -   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wybierania produktów w konfiguracji modułu lub w siatce `AdminAtcurlSearchController`. Pomaga to administratorom szybko znaleźć i powiązać produkty z niestandardowymi adresami URL.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `atcurl/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Back-office (Admin).
    -   **Odpowiedzialność:** Stylizuje rozwijane menu autouzupełniania i powiązane elementy interfejsu użytkownika używane w narzędziu wyszukiwania administracyjnego, zapewniając jego wizualną integrację z motywem Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `atcurl/views/hook/displayProductAdditionalInfo.tpl`
        -   **Hook:** `displayProductAdditionalInfo`
        -   **Cel:** Ten szablon jest prawdopodobnie renderowany na stronie produktu, dostarczając kontener lub rzeczywisty kod HTML niestandardowego przycisku, który zastępuje standardowy przycisk „Dodaj do koszyka”. Zawierałby logikę wyświetlania niestandardowego tekstu przycisku i linku.
    -   `atcurl/views/hook/displayProductListReviews.tpl`
        -   **Hook:** `displayProductListReviews` (Ta nazwa hooka jest nietypowa dla zastępowania przycisków i może być literówką lub pośrednim sposobem wstrzykiwania JS/CSS dla list produktów. Bardziej powszechne jest użycie `displayProductListFunctionalButtons` lub `displayProductActions` do modyfikacji przycisków na listach).
        -   **Cel:** Jeśli używany, ten szablon wstrzykiwałby JavaScript lub ukryty element do elementów listy produktów, który następnie skrypt `atcurl-list-177.js` wykorzystuje do wykonania zastąpienia przycisku. Mniej prawdopodobne jest, aby zawierał bezpośrednio kod HTML przycisku.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `atcurl/lib/searchTool/views/scripts.tpl`
        -   **Cel:** Ten szablon jest prawdopodobnie dołączany w Back Office w celu załadowania niezbędnego JavaScriptu (`autocomplete.js`) i potencjalnie CSS (`autocomplete.css`) dla narzędzia wyszukiwania/wyboru produktów używanego w konfiguracji modułu lub `AdminAtcurlSearchController`.
    -   `atcurl/views/tpl/selectedProducts.tpl`
        -   **Cel:** Ten szablon jest używany przez `AdminAtcurlSearchController` do renderowania siatki lub listy produktów, które mają skonfigurowane niestandardowe adresy URL. Definiuje strukturę tabeli i sposób wyświetlania informacji o każdym produkcie (ID, nazwa, URL).
-   **Szablony Front-Office (`views/templates/front/`)**: Żadne wyraźnie wymienione, ponieważ zmiany w front-office są obsługiwane głównie przez JS i szablony hooków.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie wydaje się tworzyć niestandardowych tabel SQL.
    -   **`ps_configuration`**: Przechowuje globalne ustawienia modułu (np. `ATC_URL_BUTTON_FRONT`, `ATC_URL_BUTTON_TEXT`, `ATC_URL_BLANK`, `ATC_URL_NOFOLLOW`, `ATC_HIDE_TOOLTIP`, `ATC_URL_PL`, `ATC_URL_visibility_rule`, `ATC_URL_BUTTON_QTY_HIDE`, `ATC_URL_visibility_products`, `ATC_URL_visibility_cat`).
    -   **`ps_product_shop` / `ps_product_lang`**: Adresy URL specyficzne dla produktu są prawdopodobnie przechowywane jako dodatkowe pole powiązane z produktem, potencjalnie za pomocą mechanizmu `specific_fields` PrestaShop lub poprzez bezpośrednią aktualizację właściwości produktu. Metoda `install()` modułu dodałaby to pole.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayProductAdditionalInfo` | Front-Office | Na stronie produktu, zazwyczaj poniżej opisu produktu lub bloku ceny. | Wstrzykuje kod HTML niestandardowego przycisku lub symbol zastępczy dla JS do celowania. |
| `ActionAdminControllerSetMedia` | Back-Office | Gdy kontroler administracyjny ładuje swoje media (JS/CSS). | Ładuje JavaScript specyficzny dla administratora (`atcurl177.js`, `autocomplete.js`) i CSS (`autocomplete.css`) dla konfiguracji modułu i zarządzania produktami. |
| `actionProductUpdate` | Back-Office | Po zaktualizowaniu/zapisaniu produktu w Back Office. | Pozwala modułowi zapisać niestandardowy adres URL powiązany z produktem. |
| `displayHeader` | Front-Office | W sekcji `<head>` każdej strony front-office. | Wstrzykuje JavaScript front-office (`atcurl177.js`, `atcurl-list-177.js`) i potencjalnie wbudowany CSS lub zmienne konfiguracyjne dla skryptów JS. |
| `displayProductListReviews` | Front-Office | W elementach listy produktów, często w pobliżu nazwy produktu lub oceny. | (Jak wspomniano powyżej, ten hook jest nietypowy dla zastępowania przycisków. Prawdopodobnie jest używany do wstrzykiwania JS do przetwarzania elementów listy, lub może to być hook starszego typu. Deweloperzy powinni zweryfikować jego rzeczywiste użycie w kodzie modułu.) |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Zastąp dodaj do koszyka linkiem do strony”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół jest zaangażowany w zapewnienie optymalnego funkcjonowania modułu z Twoim sklepem PrestaShop.
