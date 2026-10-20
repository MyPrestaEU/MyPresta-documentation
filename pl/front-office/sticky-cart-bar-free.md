---
title: "Sticky Cart Bar FREE - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Sticky Cart Bar FREE od MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar FREE - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Sticky Cart Bar FREE na MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/sticky-cart-bar-free/)
>
> ---


# Sticky Cart Bar FREE

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Sticky Cart Bar FREE)

To jest główny ekran konfiguracji, na którym kontrolujesz zachowanie i wygląd przyklejonego paska koszyka na stronach produktów.

#### **Włącz przyklejony pasek koszyka**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcjonalności przyklejonego paska koszyka dla Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Przyklejony pasek koszyka pojawi się na stronach produktów zgodnie z innymi ustawieniami, gdy klienci przewiną poza główny przycisk „Dodaj do koszyka”.
  - *Gdy wyłączone (NIE):* Przyklejony pasek koszyka nie pojawi się na żadnych stronach produktów, skutecznie dezaktywując moduł.
- **Zalecana wartość:** TAK (aby wykorzystać korzyści modułu).
- **Scenariusz / przykład sprzedawcy:** Jeśli testujesz moduł lub chcesz go tymczasowo wyłączyć bez odinstalowywania, ustaw to na NIE. Do działania na żywo powinno być TAK.

#### **Pozycja przyklejonego paska koszyka**

- **Co robi to ustawienie:** Określa, gdzie przyklejony pasek będzie „przyklejony” na ekranie klienta – u góry lub u dołu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Góra” (Top):* Przyklejony pasek pojawi się na samej górze okna przeglądarki, poniżej nagłówka.
  - *Gdy ustawione na „Dół” (Bottom):* Przyklejony pasek pojawi się na samym dole okna przeglądarki, powyżej stopki.
- **Zalecana wartość:** „Dół” (często mniej inwazyjne, ponieważ nie zakrywa głównej nawigacji ani logo). Jednak „Góra” może być bardziej widoczna. Przetestuj obie opcje, aby zobaczyć, co najlepiej działa dla Twojego motywu i odbiorców.
- **Scenariusz / przykład sprzedawcy:** Jeśli Twój sklep ma bardzo zajęty nagłówek lub stałe menu u góry, umieszczenie przyklejonego paska na „Dole” może zapobiec wizualnemu bałaganowi. Jeśli chcesz maksymalnej widoczności dla przycisku „Dodaj do koszyka”, preferowane może być „Góra”.

#### **Wyświetlaj na urządzeniach mobilnych**

- **Co robi to ustawienie:** Kontroluje, czy przyklejony pasek koszyka jest wyświetlany klientom przeglądającym Twój sklep na smartfonach lub innych urządzeniach mobilnych.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Przyklejony pasek koszyka będzie aktywny i widoczny na mobilnych stronach produktów.
  - *Gdy wyłączone (NIE):* Przyklejony pasek koszyka nie pojawi się na urządzeniach mobilnych, tylko na komputerach stacjonarnych/tabletach.
- **Zalecana wartość:** TAK (Użytkownicy mobilni dużo przewijają, a ta funkcja jest dla nich bardzo korzystna).
- **Scenariusz / przykład sprzedawcy:** Biorąc pod uwagę ograniczoną przestrzeń ekranu na urządzeniach mobilnych, utrzymanie widoczności przycisku „Dodaj do koszyka” jest jeszcze bardziej krytyczne. Wyłącz to tylko, jeśli napotkasz specyficzne konflikty układu z Twoim motywem mobilnym.

#### **Wyświetlaj na urządzeniach stacjonarnych**

- **Co robi to ustawienie:** Kontroluje, czy przyklejony pasek koszyka jest wyświetlany klientom przeglądającym Twój sklep na komputerach stacjonarnych lub większych ekranach tabletów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Przyklejony pasek koszyka będzie aktywny i widoczny na stronach produktów na komputerach stacjonarnych.
  - *Gdy wyłączone (NIE):* Przyklejony pasek koszyka nie pojawi się na urządzeniach stacjonarnych, tylko na urządzeniach mobilnych (jeśli włączone).
- **Zalecana wartość:** TAK (Nawet na komputerach stacjonarnych długie strony produktów korzystają z tej funkcji).
- **Scenariusz / przykład sprzedawcy:** Większość sklepów będzie chciała, aby ta opcja była włączona dla wszystkich typów urządzeń, aby zmaksymalizować potencjał konwersji.

#### **Ukryj oryginalny przycisk „Dodaj do koszyka”**

- **Co robi to ustawienie:** Ta opcja pozwala ukryć oryginalny przycisk „Dodaj do koszyka” na stronie produktu, gdy pojawi się przyklejony pasek.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Gdy przyklejony pasek jest widoczny, oryginalny przycisk „Dodaj do koszyka” na stronie produktu zostanie ukryty. Może to zmniejszyć wizualną redundancję.
  - *Gdy wyłączone (NIE):* Zarówno przycisk „Dodaj do koszyka” z przyklejonego paska, jak i oryginalny przycisk „Dodaj do koszyka” będą widoczne jednocześnie (gdy oryginalny jest w widoku).
- **Zalecana wartość:** NIE (Ogólnie bezpieczniej jest pozostawić oryginalny przycisk widoczny, jeśli znajduje się w obszarze widoku, ponieważ niektórzy klienci mogą go preferować. Ukrycie go może spowodować zamieszanie, jeśli przyklejony pasek szybko zniknie).
- **Scenariusz / przykład sprzedawcy:** Jeśli uważasz, że podwójne przyciski „Dodaj do koszyka” są wizualnie rozpraszające lub mylące, gdy przyklejony pasek jest aktywny, możesz to włączyć. W przeciwnym razie pozostaw to wyłączone.

#### **Kompatybilność z motywem**

- **Co robi to ustawienie:** To ustawienie pomaga modułowi dostosować jego styl i zachowanie do różnych motywów PrestaShop, w szczególności Classic i Hummingbird (domyślny motyw dla PrestaShop 8+).
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Classic”:* Moduł załaduje CSS i JavaScript zoptymalizowane dla motywu PrestaShop Classic i motywów na nim opartych.
  - *Gdy ustawione na „Hummingbird”:* Moduł załaduje CSS i JavaScript zoptymalizowane dla motywu PrestaShop Hummingbird (domyślny dla PrestaShop 8.x i 9.x) i motywów na nim opartych.
- **Zalecana wartość:** Wybierz motyw, którego obecnie używa Twój sklep. Jeśli używasz PrestaShop 8.x lub 9.x, prawdopodobnie jest to „Hummingbird”. Jeśli używasz PrestaShop 1.7.x i domyślnego motywu, jest to „Classic”. Jeśli używasz niestandardowego motywu, wypróbuj oba, aby zobaczyć, który lepiej się integruje.
- **Scenariusz / przykład sprzedawcy:** Jeśli Twój sklep jest na PrestaShop 8.1 i wybierzesz „Classic”, przyklejony pasek może nie wyglądać ani nie działać poprawnie. Zawsze dopasuj to do swojego aktywnego motywu.

#### **Zwiastun wersji Pro**

- **Co robi to ustawienie:** Ta sekcja to obszar promocyjny dla modułu „Sticky Cart Bar PRO”, oferujący zaawansowane funkcje niedostępne w wersji FREE. Nie wpływa na funkcjonalność modułu FREE.
- **Efekt zmiany tego ustawienia:** Brak bezpośredniego wpływu na zachowanie modułu FREE. Dostarcza informacji o uaktualnieniu.
- **Zalecana wartość:** N/A (Tylko informacyjne).
- **Scenariusz / przykład sprzedawcy:** Jeśli uważasz, że moduł FREE jest korzystny i potrzebujesz większej kontroli nad targetowaniem, projektem lub konkretnymi wykluczeniami produktów, możesz zapoznać się z funkcjami wersji PRO tutaj.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz przyklejony pasek koszyka | TAK | Główny przełącznik modułu. TAK aktywuje przyklejony pasek. |
| Konfiguracja modułu | Pozycja przyklejonego paska koszyka | Dół | Określa, czy pasek przykleja się do góry, czy do dołu ekranu. |
| Konfiguracja modułu | Wyświetlaj na urządzeniach mobilnych | TAK | Kontroluje widoczność na smartfonach/tabletach. TAK jest zalecane. |
| Konfiguracja modułu | Wyświetlaj na urządzeniach stacjonarnych | TAK | Kontroluje widoczność na komputerach stacjonarnych. TAK jest zalecane. |
| Konfiguracja modułu | Ukryj oryginalny przycisk „Dodaj do koszyka” | NIE | Ukrywa oryginalny przycisk, gdy przyklejony pasek jest aktywny. NIE jest ogólnie bezpieczniejsze. |
| Konfiguracja modułu | Kompatybilność z motywem | Hummingbird (dla PS 8/9) | Zapewnia prawidłowe style i funkcjonalność dla Twojego aktywnego motywu. Dopasuj do swojego motywu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przyklejony pasek koszyka nie pojawia się na moich stronach produktów.**
O:

- **Sprawdź „Włącz przyklejony pasek koszyka”**: Upewnij się, że to ustawienie jest ustawione na TAK w konfiguracji modułu.
- **Sprawdź „Kompatybilność z motywem”**: Upewnij się, że wybrałeś prawidłowy motyw (Classic lub Hummingbird), który pasuje do aktywnego motywu Twojego sklepu. Nieprawidłowy wybór może uniemożliwić załadowanie paska.
- **Wyczyść pamięć podręczną**: Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają pojawienie się nowych zmian modułu.
- **Przewiń poza oryginalny przycisk**: Pamiętaj, że pasek pojawia się tylko wtedy, gdy przewiniesz poza oryginalny przycisk „Dodaj do koszyka”. Upewnij się, że przewijasz wystarczająco daleko w dół strony.
- **Sprawdź ustawienia urządzenia**: Upewnij się, że „Wyświetlaj na urządzeniach mobilnych” i/lub „Wyświetlaj na urządzeniach stacjonarnych” są włączone dla urządzenia, na którym testujesz.

**P2: Przyklejony pasek koszyka wygląda dziwnie lub jest źle wyrównany z moim niestandardowym motywem.**
O:

- **Kompatybilność z motywem**: Sprawdź dwukrotnie, czy wybrałeś prawidłową opcję „Kompatybilność z motywem” w ustawieniach modułu. Jeśli masz bardzo dostosowany motyw, może on zachowywać się inaczej. Spróbuj przełączać się między „Classic” a „Hummingbird”, aby zobaczyć, który działa lepiej.
- **Niestandardowy CSS (potrzebny programista)**: Jeśli problem nadal występuje, Twój niestandardowy motyw może mieć sprzeczne style CSS. Programista może zbadać stronę za pomocą narzędzi deweloperskich przeglądarki i napisać kilka linii niestandardowego CSS, aby dostosować wygląd przyklejonego paska. Zazwyczaj wiąże się to z nadpisaniem istniejących stylów w pliku `custom.css` Twojego motywu.

**P3: Przycisk „Dodaj do koszyka” w przyklejonym pasku nie działa.**
O:

- **Wyczyść pamięć podręczną**: Podobnie jak w przypadku problemów z wyświetlaniem, wyczyszczenie pamięci podręcznej PrestaShop (**Zaawansowane > Wydajność**) może rozwiązać problemy związane z JavaScriptem.
- **Kompatybilność z motywem**: Upewnij się, że wybrano prawidłowy motyw. JavaScript może nie inicjalizować się poprawnie, jeśli wybrano niewłaściwy motyw.
- **Błędy konsoli przeglądarki (potrzebny programista)**: Poproś swojego programistę o sprawdzenie konsoli JavaScript przeglądarki pod kątem błędów. Konflikty z innymi modułami lub JavaScriptem motywu mogą czasami uniemożliwić działanie przycisku.

**P4: Czy mogę dostosować kolory lub zawartość przyklejonego paska?**
O:

- Wersja FREE modułu oferuje ograniczone opcje stylizacji (głównie dostosowanie do Twojego motywu). Aby uzyskać zaawansowane dostosowania, takie jak zmiana kolorów, czcionek, dodawanie niestandardowego tekstu lub bardziej szczegółową kontrolę nad wyświetlanymi informacjami, zazwyczaj musiałbyś uaktualnić do modułu **Sticky Cart Bar PRO**.
- W przypadku drobnych poprawek wizualnych w wersji FREE, programista może użyć niestandardowego CSS do nadpisania domyślnych stylów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Sticky Cart Bar FREE przestrzega standardowej architektury modułów PrestaShop, głównie wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji. Integruje się z front-office poprzez hooki, dynamicznie wstrzykując przyklejony pasek w oparciu o zachowanie przewijania użytkownika. Moduł wykorzystuje kombinację szablonów Smarty do struktury, CSS do stylizacji i JavaScript do funkcji przyklejania i interakcji z głównym przyciskiem „Dodaj do koszyka”. Kompatybilność z różnymi motywami PrestaShop (Classic vs. Hummingbird) jest obsługiwana poprzez ładowanie zasobów specyficznych dla motywu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- `stickycartbarfree/classes/index.php`:
  - Jest to zazwyczaj pusty plik używany do zapobiegania listowaniu katalogów, co jest powszechną praktyką bezpieczeństwa w modułach PrestaShop. Nie zawiera kodu funkcjonalnego.
- `stickycartbarfree/classes/ScbfCompatibility.php`:
  - **Nazwa klasy**: `ScbfCompatibility`
  - **Klasa nadrzędna**: Brak (samodzielna klasa narzędziowa)
  - **Odpowiedzialność**: Ta klasa prawdopodobnie zawiera statyczne metody pomocnicze do obsługi różnic kompatybilności między różnymi wersjami lub motywami PrestaShop. Może abstrahować różnice w sposobie pobierania danych produktu lub rejestrowania zasobów, zapewniając działanie modułu w obsługiwanych środowiskach. Nie wchodzi w bezpośrednią interakcję z konkretną tabelą bazy danych, ale może odpytywać `ps_configuration` o informacje o motywie.
  - **Kluczowe metody publiczne**: Prawdopodobnie statyczne metody do sprawdzania kontekstu motywu, wersji PrestaShop lub pobierania wartości konfiguracyjnych w kompatybilny sposób.

### 4.4 Zasoby JavaScript (`views/js/`)

- `stickycartbarfree/views/js/front.js`:
  - **Zakres**: Front-office.
  - **Opis**: Jest to główny plik JavaScript odpowiedzialny za zachowanie przyklejania paska koszyka.
  - **Funkcjonalność**:
    - **Słuchacze zdarzeń**: Wiąże się ze zdarzeniem `scroll` w oknie, aby wykrywać przewijanie przez użytkownika.
    - **Manipulacja DOM**:
      - Oblicza pozycję oryginalnego przycisku „Dodaj do koszyka” (`#add_to_cart` lub podobny selektor).
      - Monitoruje pozycję przewijania względem oryginalnego przycisku.
      - Dodaje/usuwa klasę CSS (np. `is-visible`) do kontenera przyklejonego paska koszyka (`#sticky-cart-bar`), aby go pokazać lub ukryć.
      - Potencjalnie ukrywa oryginalny przycisk „Dodaj do koszyka”, jeśli włączone jest odpowiednie ustawienie modułu.
    - **Interakcja**: Obsługuje kliknięcia na przycisk „Dodaj do koszyka” w przyklejonym pasku, prawdopodobnie naśladując zachowanie oryginalnego przycisku (np. wysyłanie formularza produktu, wykonywanie wywołania AJAX w celu dodania do koszyka).
    - **Responsywność**: Może zawierać logikę ponownej oceny pozycji w przypadku zdarzeń `resize`.
    - **Zdarzenia PrestaShop**: Prawdopodobnie używa `prestashop.on('updateProduct', ...)` lub podobnych zdarzeń do aktualizacji zawartości przyklejonego paska (cena, ilość, atrybuty) po zmianie opcji produktu na stronie.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `stickycartbarfree/views/css/admin-config.css`:
  - **Zakres**: Stylizacja formularza administracyjnego Back-office.
  - **Opis**: Zawiera style specyficzne dla strony konfiguracji modułu w panelu administracyjnym PrestaShop, zapewniając spójny i przyjazny dla użytkownika interfejs administracyjny.
  - **Główne komponenty UI**: Style elementów formularza, etykiet, przycisków i potencjalnie specyficznych elementów układu w ramach wyjścia `getContent()`.
- `stickycartbarfree/views/css/admin-pro-teaser.css`:
  - **Zakres**: Stylizacja formularza administracyjnego Back-office.
  - **Opis**: Style dla treści promocyjnych związanych z wersją PRO modułu wyświetlanych na stronie konfiguracji.
  - **Główne komponenty UI**: Style pól zwiastunów, przycisków aktualizacji, list funkcji i obrazów podglądu dla wersji PRO.
- `stickycartbarfree/views/css/front-classic.css`:
  - **Zakres**: Stylizacja klienta Front-office (motyw Classic).
  - **Opis**: Zapewnia specyficzne dostosowania stylizacji dla przyklejonego paska koszyka, gdy wybrana jest opcja kompatybilności z motywem „Classic”. Zapewnia to wizualną integrację paska z projektem motywu Classic.
  - **Kluczowe selektory klas CSS**: Celuje w elementy w `sticky-cart-bar`, aby dopasować czcionki, kolory, odstępy i style przycisków motywu Classic.
- `stickycartbarfree/views/css/front-hummingbird.css`:
  - **Zakres**: Stylizacja klienta Front-office (motyw Hummingbird).
  - **Opis**: Zapewnia specyficzne dostosowania stylizacji dla przyklejonego paska koszyka, gdy wybrana jest opcja kompatybilności z motywem „Hummingbird”. Zapewnia to wizualną integrację paska z domyślnym motywem PrestaShop 8.x/9.x.
  - **Kluczowe selektory klas CSS**: Celuje w elementy w `sticky-cart-bar`, aby dopasować czcionki, kolory, odstępy i style przycisków motywu Hummingbird.
- `stickycartbarfree/views/css/front.css`:
  - **Zakres**: Stylizacja klienta Front-office (ogólna).
  - **Opis**: Zawiera podstawowe, wspólne style dla przyklejonego paska koszyka, które mają zastosowanie niezależnie od wybranej kompatybilności z motywem. Obejmuje to podstawowe pozycjonowanie, widoczność i responsywność.
  - **Kluczowe selektory klas CSS**: Definiuje właściwości `#sticky-cart-bar`, takie jak `position: fixed`, `z-index`, `width`, `padding`, `background-color` i responsywne zapytania mediów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-classic.tpl`: Renderowany, gdy wybrana jest kompatybilność z motywem „Classic”. Zawiera główną strukturę przyklejonego paska, dostosowaną do oczekiwań HTML i CSS motywu Classic.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-hummingbird.tpl`: Renderowany, gdy wybrana jest kompatybilność z motywem „Hummingbird”. Zawiera główną strukturę przyklejonego paska, dostosowaną do oczekiwań HTML i CSS motywu Hummingbird.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-inner.tpl`: Ten szablon prawdopodobnie zawiera główną zawartość przyklejonego paska (nazwa produktu, cena, pole ilości, przycisk dodawania do koszyka). Prawdopodobnie jest on dołączany przez `sticky-cart-bar-classic.tpl` i `sticky-cart-bar-hummingbird.tpl`, aby uniknąć duplikacji kodu.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar.tpl`: Może to być szablon opakowujący lub awaryjny, lub może to być główny punkt wejścia, który warunkowo zawiera `sticky-cart-bar-classic.tpl` lub `sticky-cart-bar-hummingbird.tpl` w oparciu o konfigurację.
  - **Cel**: Te szablony są zazwyczaj podłączane do `displayFooter` lub `displayBeforeBodyClosingTag`, aby zapewnić obecność kodu HTML przyklejonego paska na stronach produktów. Wyświetlają strukturę HTML dla przyklejonego paska, wypełnioną danymi produktu przekazanymi z modułu.
- **Szablony administracyjne (`views/templates/admin/`)**:

  - `stickycartbarfree/views/templates/admin/configure.tpl`: Jest to główny szablon strony konfiguracji modułu w Panelu administracyjnym. Renderuje wszystkie ustawienia, pola wprowadzania i opcje zdefiniowane w metodzie `getContent()` modułu.
  - `stickycartbarfree/views/templates/admin/pro-teaser-intro.tpl`: Renderuje wstępną część zwiastuna wersji PRO na stronie konfiguracji.
  - `stickycartbarfree/views/templates/admin/pro-teaser-preview.tpl`: Renderuje podgląd lub wizualną reprezentację funkcji wersji PRO.
  - `stickycartbarfree/views/templates/admin/pro-teaser.tpl`: Główny szablon dla sekcji zwiastuna wersji PRO, prawdopodobnie zawierający szablony intro i podglądu.
  - **Cel**: Te szablony zapewniają interfejs użytkownika dla ustawień modułu i treści promocyjnych w Panelu administracyjnym PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`, z kluczami zazwyczaj poprzedzonymi `SCBF_` (np. `SCBF_ENABLE`, `SCBF_POSITION`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do rejestrowania zasobów CSS i JavaScript (`front.js`, `front.css`, CSS specyficznego dla motywu) dla front-office. |
| `displayFooter` | Przed zamykającym tagiem `</body>` na każdej stronie. | Służy do wstrzykiwania głównej struktury HTML przyklejonego paska koszyka (`sticky-cart-bar.tpl` lub jego wariantów) do strony. |
| `actionFrontControllerSetMedia` | Po ustawieniu mediów (CSS/JS) przez kontroler front-office. | Alternatywny hook do rejestrowania zasobów, zapewniający ich prawidłowe załadowanie. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w panelu administracyjnym. | (Prawdopodobnie nie używany w wersji FREE, ale powszechny dla modułów, które muszą wyczyścić pamięć podręczną lub ponownie indeksować dane produktu). |
| `actionCartUpdateQuantity` | Gdy ilość produktu jest aktualizowana w koszyku. | (Prawdopodobnie nie używany w wersji FREE, ale mógłby być użyty do aktualizacji selektora ilości w przyklejonym pasku, gdyby był bardziej interaktywny). |
| `actionAjaxDieProduct` | Gdy żądanie AJAX związane z danymi produktu umiera. | (Może być używany do debugowania lub specyficznych interakcji AJAX). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz zapoznania się z zaawansowanymi funkcjami dostępnymi w wersji PRO modułu, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących modułu Sticky Cart Bar FREE.
