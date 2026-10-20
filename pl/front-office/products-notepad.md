---
title: "Notatnik Produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Notatnik Produktów od MyPresta.eu."
sidebar:
  label: "Notatnik Produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Products Notepad na MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-notepad.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/products-notepad/)
>
> ---


# Notatnik Produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do ogólnego działania PrestaShop. Dla tego modułu nie są potrzebne żadne dodatkowe rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Notatnik Produktów” w Menedżerze Modułów. Spowoduje to przejście do głównego ekranu konfiguracji.

#### Ustawienia ogólne

- **Co robi to ustawienie:** Ta sekcja kontroluje podstawowe zachowanie i wyświetlanie modułu Notatnik Produktów w Twoim sklepie.

  - **Zapamiętaj produkty w notatniku:**

    - **Co robi to ustawienie:** Określa, czy produkty dodane przez klienta do notatnika są zapamiętywane w różnych sesjach przeglądania, czy też notatnik jest czyszczony po zamknięciu przeglądarki.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Produkty dodane do notatnika będą zachowane, nawet jeśli klient opuści Twoją witrynę i wróci później (np. następnego dnia). Wykorzystuje to pliki cookie przeglądarki do przechowywania zawartości notatnika.
      - *Gdy wyłączone (NIE):* Notatnik zostanie wyczyszczony, gdy klient zamknie przeglądarkę lub wyczyści pliki cookie. Każda nowa sesja rozpocznie się z pustym notatnikiem.
    - **Zalecana wartość:** **TAK**. Zapewnia to znacznie lepsze doświadczenie klienta, ponieważ pozwala klientom budować listę w czasie bez utraty postępów.
    - **Scenariusz / przykład dla sprzedawcy:** Klient dodaje kilka pozycji do notatnika w poniedziałek. Jeśli „Zapamiętaj produkty” jest ustawione na TAK, może wrócić w środę i znaleźć swoją listę nienaruszoną. Jeśli NIE, lista byłaby pusta.
  - **Ogranicz liczbę produktów w notatniku:**

    - **Co robi to ustawienie:** Pozwala ustawić maksymalną liczbę produktów, jaką klient może zapisać w swoim notatniku.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Notatnik pozwoli tylko na określoną liczbę produktów. Po osiągnięciu limitu klienci nie będą mogli dodawać więcej produktów, dopóki nie usuną istniejących.
      - *Gdy wyłączone (NIE):* Klienci mogą dodawać nieograniczoną liczbę produktów do swojego notatnika.
    - **Zalecana wartość:** **NIE** (chyba że masz konkretny powód, aby to ograniczyć, np. obawy o wydajność przy bardzo długich listach). Pozwolenie na nieograniczoną liczbę pozycji daje klientom maksymalną elastyczność.
    - **Scenariusz / przykład dla sprzedawcy:** Jeśli włączysz to ustawienie i ustawisz limit na 10, klient, który spróbuje dodać 11. produkt, otrzyma komunikat informujący, że notatnik jest pełny.
  - **Wartość limitu:** (Pojawia się tylko, jeśli „Ogranicz liczbę produktów w notatniku” jest ustawione na TAK)

    - **Co robi to ustawienie:** Określa dokładną maksymalną liczbę produktów dozwolonych w notatniku.
    - **Efekt zmiany tego ustawienia:** Ustawia liczbowy limit dla notatnika.
    - **Zalecana wartość:** Jeśli zdecydujesz się na ograniczenie, rozsądna liczba, taka jak **20-50**, jest często wystarczająca, równoważąc elastyczność klienta z potencjalną wydajnością.
    - **Scenariusz / przykład dla sprzedawcy:** Jeśli „Ogranicz liczbę produktów” jest TAK, a „Wartość limitu” to 25, klienci mogą zapisać do 25 produktów.

#### Ustawienia wyświetlania

- **Co robi to ustawienie:** Ta sekcja kontroluje, gdzie blok Notatnik Produktów pojawia się w front-office Twojego sklepu.

  - **Wyświetl w lewej kolumnie:**

    - **Co robi to ustawienie:** Kontroluje, czy blok podsumowania notatnika jest wyświetlany w lewej kolumnie Twojego sklepu.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Blok notatnika pojawi się w lewej kolumnie na stronach, które mają lewą kolumnę (np. strony kategorii, strony produktów, strony CMS).
      - *Gdy wyłączone (NIE):* Blok notatnika nie będzie wyświetlany w lewej kolumnie.
    - **Zalecana wartość:** **TAK** (lub prawa kolumna), ponieważ kolumny są typowym miejscem na takie bloki narzędziowe.
    - **Scenariusz / przykład dla sprzedawcy:** Klient przeglądający stronę kategorii zobaczy podsumowanie swojego notatnika w lewym pasku bocznym, co ułatwia dostęp.
  - **Wyświetl w prawej kolumnie:**

    - **Co robi to ustawienie:** Kontroluje, czy blok podsumowania notatnika jest wyświetlany w prawej kolumnie Twojego sklepu.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Blok notatnika pojawi się w prawej kolumnie na stronach, które mają prawą kolumnę.
      - *Gdy wyłączone (NIE):* Blok notatnika nie będzie wyświetlany w prawej kolumnie.
    - **Zalecana wartość:** **TAK** (lub lewa kolumna). Wybierz jedną lub obie w zależności od układu Twojego szablonu i innych modułów, które posiadasz.
    - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój szablon używa prawej kolumny do promocji, możesz umieścić tam notatnik, aby lewa kolumna pozostała wolna dla nawigacji.
  - **Wyświetl w stopce:**

    - **Co robi to ustawienie:** Kontroluje, czy blok podsumowania notatnika jest wyświetlany w sekcji stopki Twojego sklepu.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Blok notatnika pojawi się na dole każdej strony, zazwyczaj jako część ogólnej zawartości stopki.
      - *Gdy wyłączone (NIE):* Blok notatnika nie będzie wyświetlany w stopce.
    - **Zalecana wartość:** **NIE** (chyba że Twój szablon ma bardzo widoczną sekcję stopki dla bloków narzędziowych). Kolumny są zazwyczaj bardziej widoczne dla tego typu funkcji.
    - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja stopka jest już zatłoczona linkami i informacjami prawnymi, dodanie tam notatnika może sprawić, że będzie mniej zauważalny.
  - **Wyświetl w nagłówku:**

    - **Co robi to ustawienie:** Kontroluje, czy blok podsumowania notatnika jest wyświetlany w sekcji nagłówka Twojego sklepu.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Blok notatnika pojawi się na górze każdej strony, często w pobliżu koszyka lub linków do konta.
      - *Gdy wyłączone (NIE):* Blok notatnika nie będzie wyświetlany w nagłówku.
    - **Zalecana wartość:** **NIE** (chyba że Twój szablon ma dużo miejsca i specyficzny projekt dla tego). Nagłówki są często zarezerwowane dla krytycznej nawigacji i koszyka.
    - **Scenariusz / przykład dla sprzedawcy:** Kompaktowa ikona w nagłówku może działać, ale pełny blok może zaśmiecać nagłówek.
  - **Wyświetl na stronie produktu:**

    - **Co robi to ustawienie:** Kontroluje, czy przycisk „Dodaj do notatnika” i potencjalnie małe podsumowanie notatnika są wyświetlane bezpośrednio na poszczególnych stronach produktów.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Klienci zobaczą przycisk „Dodaj do notatnika” na każdej stronie produktu, co ułatwia zapisywanie pozycji podczas przeglądania.
      - *Gdy wyłączone (NIE):* Przycisk „Dodaj do notatnika” nie pojawi się na stronach produktów, co sprawi, że funkcja będzie mniej dostępna.
    - **Zalecana wartość:** **TAK**. Jest to kluczowe miejsce dla skuteczności funkcji.
    - **Scenariusz / przykład dla sprzedawcy:** Klient przeglądający produkt może natychmiast dodać go do swojego notatnika w celu późniejszego porównania z innymi produktami.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Zapamiętaj produkty w notatniku | TAK | Zachowuje elementy notatnika w różnych sesjach dla lepszego UX. |
| Konfiguracja modułu | Ogranicz liczbę produktów w notatniku | NIE | Pozwala na nieograniczoną liczbę produktów w notatniku, maksymalizując wybór klienta. |
| Konfiguracja modułu | Wartość limitu | (N/A, jeśli limit to NIE) | Ustawia maksymalną liczbę produktów, jeśli limitowanie jest włączone. |
| Konfiguracja modułu | Wyświetl w lewej kolumnie | TAK | Pokazuje podsumowanie notatnika w lewym pasku bocznym. |
| Konfiguracja modułu | Wyświetl w prawej kolumnie | TAK | Pokazuje podsumowanie notatnika w prawym pasku bocznym. |
| Konfiguracja modułu | Wyświetl w stopce | NIE | Unika zaśmiecania stopki, mniej widoczne. |
| Konfiguracja modułu | Wyświetl w nagłówku | NIE | Unika zaśmiecania nagłówka, mniej widoczne. |
| Konfiguracja modułu | Wyświetl na stronie produktu | TAK | Niezbędne, aby klienci mogli łatwo dodawać produkty do notatnika. |

## 3. Rozwiązywanie problemów przez sprzedawcę i często zadawane pytania (FAQ)

**P1: Notatnik nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O1: Najpierw sprawdź konfigurację modułu w Panelu Administracyjnym (**Moduły > Menedżer modułów > Notatnik Produktów > Konfiguruj**). Upewnij się, że co najmniej jedna opcja wyświetlania (np. „Wyświetl w lewej kolumnie” lub „Wyświetl na stronie produktu”) jest ustawiona na TAK. Jeśli nadal się nie wyświetla, spróbuj wyczyścić pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Czasami konflikty szablonów mogą również uniemożliwiać wyświetlanie modułów; tymczasowo przełącz się na domyślny szablon PrestaShop, aby to wykluczyć.

**P2: Produkty nie są zapamiętywane w notatniku po zamknięciu przeglądarki przez klienta.**
O2: Przejdź do strony konfiguracji modułu (**Moduły > Menedżer modułów > Notatnik Produktów > Konfiguruj**) i upewnij się, że ustawienie „Zapamiętaj produkty w notatniku” jest ustawione na **TAK**. Ta opcja wykorzystuje pliki cookie przeglądarki do przechowywania zawartości notatnika, więc upewnij się, że klienci nie wyłączyli plików cookie w swojej przeglądarce.

**P3: Przycisk „Dodaj do notatnika” wygląda dziwnie lub nie jest poprawnie ostylowany na moich stronach produktów.**
O3: Jest to często konflikt CSS z Twoim niestandardowym szablonem. Moduł zapewnia własne podstawowe style, ale style Twojego szablonu mogą je nadpisywać. Możesz:
1. Skontaktować się z twórcą swojego szablonu w celu uzyskania pomocy.
2. Użyć edytora szablonów na żywo PrestaShop (jeśli dostępny w Twojej wersji) lub narzędzi deweloperskich przeglądarki (F12), aby zbadać przycisk i zastosować niestandardowe nadpisania CSS w pliku `custom.css` Twojego szablonu.
3. Skontaktować się z pomocą techniczną MyPresta.eu w celu uzyskania wskazówek.

**P4: Czy klienci mogą udostępniać swój notatnik innym?**
O4: Nie, ten moduł jest przeznaczony do indywidualnego użytku klienta i nie zawiera funkcji udostępniania. Jest to osobista pomoc w przeglądaniu, a nie wspólna lista życzeń.

**P5: Czy notatnik będzie działał ze sklepami wielojęzycznymi?**
O5: Tak, moduł jest zaprojektowany tak, aby był kompatybilny z funkcjami wielojęzycznymi PrestaShop. Każdy tekst wyświetlany przez moduł (takie jak etykiety przycisków lub tytuły bloków) może być przetłumaczony za pośrednictwem interfejsu tłumaczeń PrestaShop (**Lokalizacja > Tłumaczenia > Tłumaczenia zainstalowanych modułów**).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Notatnik Produktów to standardowy moduł PrestaShop, zgodny ze wzorcem MVC. Wykorzystuje głównie kontrolery front-end do interakcji AJAX i renderowania, oraz szablony Smarty do wyświetlania w front-office. W przypadku konfiguracji zapamiętywania produktów, polega na plikach cookie przeglądarki. Główna logika modułu znajduje się w `notepad.php` i powiązanych z nim kontrolerach front-end.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `controllers/front/ajaxload.php`
    - **Nazwa klasy i klasa nadrzędna**: `NotepadAjaxloadModuleFrontController` rozszerzający `ModuleFrontController`.
    - **Odpowiedzialność**: Ten kontroler obsługuje wszystkie żądania AJAX związane z funkcjonalnością notatnika. Jest odpowiedzialny za dodawanie produktów do notatnika, ich usuwanie i potencjalne aktualizowanie wyświetlania notatnika. Przetwarza dane wysyłane za pośrednictwem POST lub GET i zwraca odpowiedzi JSON do front-endowego JavaScriptu.
  - `controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna**: `NotepadIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    - **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako rezerwowy lub dedykowana strona dla notatnika, jeśli zaimplementowano widok pełnoekranowy. Biorąc pod uwagę główny charakter modułu oparty na AJAX, może to być rzadziej używany punkt wejścia, prawdopodobnie przekierowujący lub renderujący pełny widok notatnika.
- **Kontrolery administracyjne Back-Office**: Brak. Cała konfiguracja jest obsługiwana za pośrednictwem metody `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

W tym module nie są zdefiniowane żadne niestandardowe klasy `ObjectModel`. Dane produktów są prawdopodobnie przechowywane bezpośrednio w plikach cookie przeglądarki lub zmiennych sesji, pobierane i przetwarzane przez główną klasę modułu i kontrolery front-end.

### 4.4 Zasoby JavaScript (`views/js/`)

- `admin.js`
  - **Zakres**: Back-office.
  - **Opis**: Ten skrypt prawdopodobnie obsługuje interakcje na stronie konfiguracji modułu w Panelu Administracyjnym PrestaShop. Może zarządzać widocznością ustawień (np. `notepad_limit_value` w zależności od `notepad_limit`), przesyłaniem formularzy lub walidacją.
- `jscolor.js`
  - **Zakres**: Back-office (prawdopodobnie).
  - **Opis**: Biblioteka JavaScript innej firmy do wyboru kolorów. Gdyby moduł miał opcje dostosowywania kolorów dla wyświetlania notatnika, ten skrypt zapewniałby interfejs użytkownika do wyboru kolorów w panelu administracyjnym. (Na podstawie inwentaryzacji jest obecny, ale może być pozostałością lub do przyszłego użytku, jeśli obecnie nie są udostępniane żadne ustawienia kolorów).
- `lib/searchTool/views/js/autocomplete.js`
  - **Zakres**: Front-office (potencjalnie Back-office, jeśli używany do wyboru produktów).
  - **Opis**: Ten skrypt zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania produktów. Gdyby notatnik miał funkcję dodawania produktów poprzez wyszukiwanie, lub gdyby był częścią szerszej biblioteki „narzędzi wyszukiwania” dołączonej do modułu, ten skrypt obsługiwałby wywołania AJAX i wyświetlanie sugestii wyszukiwania.
- `notepad.js`
  - **Zakres**: Front-office.
  - **Opis**: Jest to podstawowy JavaScript front-office dla funkcjonalności notatnika.
    - **Słuchacze zdarzeń**: Wiąże zdarzenia kliknięcia z przyciskami „Dodaj do notatnika” (np. na stronach produktów, listach produktów), linkami/przyciskami „Usuń z notatnika” w bloku notatnika, a potencjalnie także z nagłówkiem bloku notatnika, aby przełączać jego widoczność lub nawigować do pełnego widoku.
    - **Wywołania AJAX**: Wykonuje asynchroniczne żądania do `controllers/front/ajaxload.php` w celu dodawania, usuwania lub pobierania zawartości notatnika.
    - **Manipulacja DOM**: Aktualizuje blok wyświetlania notatnika (np. liczbę produktów, listę produktów), wyświetla komunikaty o sukcesie/błędzie i dynamicznie renderuje wpisy produktów w notatniku.
    - **Zarządzanie plikami cookie**: Współpracuje z plikami cookie przeglądarki w celu przechowywania i pobierania identyfikatorów produktów z notatnika, jeśli opcja „Zapamiętaj produkty” jest włączona.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `css/admincss.css`
  - **Zakres**: Stylizacja formularza administracyjnego Back-office.
  - **Opis**: Style dla strony konfiguracji modułu w Panelu Administracyjnym PrestaShop, zapewniające spójny wygląd i działanie z motywem administracyjnym PrestaShop.
- `css/css.css`
  - **Zakres**: Stylizacja klienta Front-office.
  - **Opis**: Zawiera podstawowe style dla bloku wyświetlania notatnika, przycisku „Dodaj do notatnika” i wszelkich powiązanych elementów w sklepie.
  - **Kluczowe selektory klas CSS**: Programiści mogą sprawdzić wygenerowany kod HTML pod kątem klas takich jak `.notepad-block`, `.add-to-notepad`, `.notepad-product-item`, aby nadpisać style w pliku `custom.css` lub `theme.css` swojego szablonu.
- `lib/searchTool/views/css/autocomplete.css`
  - **Zakres**: Front-office (lub Back-office, jeśli narzędzie wyszukiwania jest tam używane).
  - **Opis**: Style dla rozwijanej listy wyników wyszukiwania autouzupełniania, jeśli skrypt `autocomplete.js` jest aktywnie używany do funkcji wyszukiwania produktów w module.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `extraleft.tpl`
    - **Hook**: Prawdopodobnie `displayLeftColumn` lub podobny.
    - **Cel**: Renderuje główny blok podsumowania notatnika, który pojawia się w lewej kolumnie. Zazwyczaj pokazuje tytuł, liczbę pozycji i krótką listę lub link do pełnego notatnika.
  - `notepad.tpl`
    - **Hook**: Może to być ogólny szablon dołączany przez inne szablony lub bezpośrednio podłączony do `displayRightColumn`, `displayFooter` lub `displayHeader` w zależności od konfiguracji. Prawdopodobnie zawiera podstawową strukturę bloku notatnika.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak jawnie wymienionych, konfiguracja jest prawdopodobnie obsługiwana bezpośrednio przez `notepad.php` renderujący elementy formularza.
- **Szablony Front-office (`views/templates/front/`)**:
  - `views/addToCart.tpl`
    - **Cel**: Ten szablon jest renderowany na stronach produktów (i potencjalnie na listach produktów) w celu wyświetlenia przycisku „Dodaj do notatnika”. Prawdopodobnie jest podłączony do `displayProductButtons` lub `displayProductActions`.
  - `views/selectedProducts.tpl`
    - **Cel**: Ten szablon służy do wyświetlania szczegółowej listy produktów w notatniku, albo w wyskakującym okienku, na dedykowanej stronie, albo w rozszerzonym bloku kolumny. Iteruje po produktach zapisanych w notatniku i wyświetla ich obraz, nazwę, cenę oraz opcję „usuń”.
  - `lib/searchTool/views/scripts.tpl`
    - **Cel**: Ten szablon prawdopodobnie zawiera niezbędne JavaScript i CSS dla biblioteki `searchTool`, takie jak `autocomplete.js` i `autocomplete.css`, jeśli moduł wykorzystuje funkcję wyszukiwania. Byłby podłączony do `displayHeader` lub `displayFooter` w celu załadowania tych zasobów.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Moduł nie wydaje się tworzyć żadnych niestandardowych tabel SQL. Identyfikatory produktów i powiązane dane dla notatnika są zarządzane po stronie klienta, głównie za pośrednictwem plików cookie przeglądarki lub zmiennych sesji. Ustawienia konfiguracji są przechowywane w `ps_configuration` (np. `NOTEPAD_REMEMBER`, `NOTEPAD_LIMIT`, `NOTEPAD_LIMIT_VALUE`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Aby załadować zasoby CSS i JS modułu (np. `notepad.js`, `css.css`) i potencjalnie renderować kompaktowe podsumowanie notatnika, jeśli jest skonfigurowane. |
| `displayLeftColumn` | W lewym pasku bocznym stron, które go posiadają. | Aby wyświetlić główny blok podsumowania notatnika (`extraleft.tpl`). |
| `displayRightColumn` | W prawym pasku bocznym stron, które go posiadają. | Aby wyświetlić główny blok podsumowania notatnika (`notepad.tpl` lub podobny). |
| `displayFooter` | W sekcji stopki każdej strony. | Aby wyświetlić blok podsumowania notatnika, jeśli jest skonfigurowany, lub załadować odroczony JS. |
| `displayProductButtons` / `displayProductActions` (lub podobny hook strony produktu) | Na stronie produktu, w pobliżu przycisku „Dodaj do koszyka”. | Aby wyrenderować przycisk „Dodaj do notatnika” (`views/addToCart.tpl`). |
| `actionFrontControllerSetMedia` | Przed renderowaniem danych wyjściowych przez kontroler front-end. | Aby zarejestrować pliki CSS i JS modułu w celu optymalnego ładowania. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Notatnik Produktów, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
