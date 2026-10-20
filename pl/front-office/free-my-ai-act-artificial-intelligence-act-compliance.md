---
title: "Free My AI Act - Zgodność z ustawą o sztucznej inteligencji - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Free My AI Act - Zgodność z ustawą o sztucznej inteligencji od MyPresta.eu."
sidebar:
  label: "Free My AI Act - Zgodność z ustawą o sztucznej inteligencji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free My AI Act - Artificial Intelligence Act compliance na MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-my-ai-act-artificial-intelligence-act-compliance.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/free-my-ai-act-artificial-intelligence-act-compliance/)
>
> ---


# Free My AI Act - Zgodność z ustawą o sztucznej inteligencji

## 1. Wymagania i kompatybilność
-   **Obsługiwane wersje PrestaShop**: PrestaShop 9.x
-   **Kompatybilność z PHP**: PHP 7.4 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Aby uzyskać dostęp do konfiguracji modułu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Free My AI Act” i kliknij przycisk „Konfiguruj”.

Ten ekran zawiera wszystkie niezbędne ustawienia do kontrolowania sposobu ujawniania treści AI w Twoim sklepie.

#### **Ustawienia ogólne**

-   **Włącz zgodność z ustawą o sztucznej inteligencji:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywowania lub dezaktywowania funkcji modułu w całym Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Wszystkie skonfigurowane funkcje ujawniania AI (odznaki, banery, powiadomienia) zostaną aktywowane w Twoim front office.
        -   *Po wyłączeniu:* Wszystkie funkcje ujawniania AI zostaną ukryte, a moduł nie będzie wyświetlał żadnych informacji związanych z AI klientom.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś konfigurację i jesteś gotowy do uruchomienia zgodności z ustawą o sztucznej inteligencji. Włącz to ustawienie. Jeśli musisz tymczasowo wyłączyć wszystkie ujawnienia w celu konserwacji, przełącz je na NIE.

#### **Opcje ujawniania treści AI**

-   **Pokaż odznakę AI na zdjęciach produktów:**
    -   **Co robi to ustawienie:** Kontroluje, czy mała odznaka (np. „Wygenerowane przez AI” lub ikona) pojawia się bezpośrednio na zdjęciach produktów w listach kategorii i na stronie produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Wizualny wskaźnik zostanie nałożony na zdjęcia produktów, które oznaczyłeś jako wygenerowane przez AI.
        -   *Po wyłączeniu:* Na zdjęciach produktów nie pojawi się żadna odznaka, nawet jeśli są one oznaczone jako wygenerowane przez AI.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Używasz AI do generowania lub ulepszania wielu zdjęć produktów. Włączenie tej opcji zapewnia natychmiastowe wizualne ujawnienie klientom podczas przeglądania.

-   **Pokaż dodatkową informację na stronie produktu:**
    -   **Co robi to ustawienie:** Określa, czy na poszczególnych stronach produktów wyświetlana jest dedykowana informacja tekstowa, aby poinformować klientów o treściach generowanych przez AI (tekst lub obrazy) dla tego konkretnego produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Na stronach produktów pojawi się konfigurowalny blok tekstowy, zazwyczaj pod opisem lub w nowej zakładce, szczegółowo opisujący użycie AI dla treści tego produktu.
        -   *Po wyłączeniu:* Na stronach produktów nie będzie wyświetlana żadna konkretna informacja o ujawnieniu AI.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz dostarczyć bardziej szczegółowe wyjaśnienie dotyczące treści AI dla każdego produktu. Ta informacja pozwala na rozbudowanie poza samą odznakę.

-   **Pokaż ogólnosklepowy baner polityki AI:**
    -   **Co robi to ustawienie:** Aktywuje baner, który pojawia się konsekwentnie w całym Twoim sklepie (np. na górze lub na dole każdej strony), aby informować odwiedzających o Twojej ogólnej polityce dotyczącej treści AI.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Konfigurowalny baner będzie widoczny na wszystkich stronach, często z linkiem do bardziej kompleksowej strony z polityką AI.
        -   *Po wyłączeniu:* Nie będzie wyświetlany żaden baner ogólnosklepowy.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zamieścić ogólne oświadczenie dotyczące użycia AI w Twoim sklepie i skierować klientów do dedykowanej strony z polityką w celu pełnej przejrzystości.

-   **Link do strony polityki AI (URL):**
    -   **Co robi to ustawienie:** Pozwala określić adres URL strony CMS lub zewnętrznego linku, gdzie klienci mogą znaleźć Twoją szczegółową politykę dotyczącą treści AI. Ten link będzie zazwyczaj umieszczony w banerze ogólnosklepowym lub dodatkowych informacjach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wprowadzeniu adresu URL:* Baner i powiadomienia będą zawierać klikalny link do tej strony.
        -   *Po pozostawieniu pustego:* Nie zostanie podany żaden link, lub baner/powiadomienie może się nie pojawić, jeśli zależy od tego linku.
    -   **Zalecana wartość:** `[Adres URL Twojej strony CMS, np. /content/10-ai-policy]`
    -   **Scenariusz / przykład dla sprzedawcy:** Stworzyłeś dedykowaną stronę CMS wyjaśniającą Twoje użycie AI, praktyki dotyczące danych i zaangażowanie w przejrzystość. Wprowadź tutaj jej adres URL, aby klienci mogli łatwo do niej uzyskać dostęp.

#### **Dostosowanie treści**

-   **Tekst odznaki AI (np. „AI”):**
    -   **Co robi to ustawienie:** Definiuje krótki tekst, który pojawia się na odznace AI nałożonej na zdjęcia produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Tekst na odznace zostanie odpowiednio zaktualizowany.
    -   **Zalecana wartość:** AI
    -   **Scenariusz / przykład dla sprzedawcy:** Wolisz krótszą etykietę, taką jak „AI”, zamiast „Wygenerowane przez AI”, aby odznaka była zwięzła.

-   **Kolor odznaki AI:**
    -   **Co robi to ustawienie:** Ustawia kolor tła odznaki AI.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Kolor tła odznaki zostanie zaktualizowany, co pozwoli dopasować go do brandingu Twojego sklepu.
    -   **Zalecana wartość:** #FF0000 (Czerwony) lub kolor, który dobrze kontrastuje ze zdjęciami produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja marka używa określonej palety kolorów. Możesz ustawić kolor odznaki na kontrastujący odcień, który nadal jest atrakcyjny wizualnie.

-   **Kolor tekstu odznaki AI:**
    -   **Co robi to ustawienie:** Ustawia kolor tekstu w odznace AI.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Kolor tekstu na odznace zostanie zaktualizowany.
    -   **Zalecana wartość:** #FFFFFF (Biały) lub kolor, który dobrze kontrastuje z wybranym tłem odznaki.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli tło Twojej odznaki jest ciemne, będziesz potrzebować białego lub jasnego tekstu dla czytelności.

-   **Tekst dodatkowej informacji:**
    -   **Co robi to ustawienie:** Pozwala dostosować pełny tekst wyświetlany w „Dodatkowej informacji” na stronach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Treść informacji na stronach produktów będzie odzwierciedlać Twój niestandardowy tekst.
    -   **Zalecana wartość:** „Uwaga: Części opisu tego produktu i/lub zdjęć mogły zostać wygenerowane lub ulepszone przy użyciu sztucznej inteligencji, aby zapewnić Państwu kompleksowe informacje.”
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz jasno określić, że zarówno tekst, jak i obrazy mogą być generowane przez AI i wyjaśnić dlaczego (np. dla kompleksowych informacji).

-   **Tekst banera ogólnosklepowego:**
    -   **Co robi to ustawienie:** Dostosowuje wiadomość wyświetlaną w ogólnosklepowym banerze polityki AI.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Tekst w banerze na wszystkich stronach zostanie zaktualizowany.
    -   **Zalecana wartość:** „Nasz sklep używa AI do ulepszania treści. Dowiedz się więcej o naszej polityce AI.”
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zwięzłą wiadomość w banerze, która zachęca klientów do kliknięcia linku, aby uzyskać więcej szczegółów.

#### **Oznaczanie produktów jako generowanych przez AI**

Ten moduł integruje się również bezpośrednio ze stroną edycji produktu. Podczas edycji produktu w Panelu administracyjnym (**Katalog > Produkty > Edytuj produkt**) znajdziesz nową zakładkę lub sekcję związaną z „Zgodnością z ustawą o sztucznej inteligencji”.

-   **Oznacz treść produktu jako wygenerowaną przez AI:**
    -   **Co robi to ustawienie:** Pole wyboru lub przełącznik na stronie edycji produktu, który pozwala indywidualnie oznaczyć tekstową treść konkretnego produktu (opis, krótki opis, cechy) jako wygenerowaną przez AI.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu dla produktu:* „Dodatkowa informacja” (jeśli włączona w konfiguracji modułu) pojawi się na stronie tego produktu, a wszelkie inne tekstowe ujawnienia AI zostaną aktywowane.
        -   *Po wyłączeniu dla produktu:* Dla tego konkretnego produktu nie pojawią się żadne tekstowe ujawnienia AI.
    -   **Zalecana wartość:** Włącz dla każdego produktu, dla którego AI zostało użyte do tekstu.
    -   **Scenariusz / przykład dla sprzedawcy:** Użyłeś asystenta pisania AI do stworzenia długiego opisu nowego produktu. Włączyłbyś to ustawienie dla tego konkretnego produktu.

-   **Oznacz zdjęcia produktów jako wygenerowane przez AI:**
    -   **Co robi to ustawienie:** Pole wyboru lub przełącznik na stronie edycji produktu, który pozwala indywidualnie oznaczyć zdjęcia konkretnego produktu jako wygenerowane przez AI lub ulepszone przez AI.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu dla produktu:* „Odznaka AI” (jeśli włączona w konfiguracji modułu) pojawi się na zdjęciach tego produktu, a także aktywuje się „Dodatkowa informacja”.
        -   *Po wyłączeniu dla produktu:* Na zdjęciach tego konkretnego produktu nie pojawi się żadna odznaka AI.
    -   **Zalecana wartość:** Włącz dla każdego produktu, dla którego AI zostało użyte do zdjęć.
    -   **Scenariusz / przykład dla sprzedawcy:** Użyłeś generatora lub ulepszacza obrazów AI dla głównego zdjęcia produktu. Włączyłbyś to ustawienie dla tego konkretnego produktu.

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Włącz zgodność z ustawą o sztucznej inteligencji | TAK | Główny przełącznik dla wszystkich funkcji modułu. |
| Konfiguracja modułu | Pokaż odznakę AI na zdjęciach produktów | TAK | Wyświetla odznakę „AI” na zdjęciach produktów oznaczonych jako AI. |
| Konfiguracja modułu | Pokaż dodatkową informację na stronie produktu | TAK | Wyświetla informację tekstową na stronach produktów oznaczonych jako AI. |
| Konfiguracja modułu | Pokaż ogólnosklepowy baner polityki AI | TAK | Wyświetla baner na wszystkich stronach dla ogólnej polityki. |
| Konfiguracja modułu | Link do strony polityki AI (URL) | `/content/10-ai-policy` | Adres URL Twojej szczegółowej strony polityki AI. |
| Konfiguracja modułu | Tekst odznaki AI | AI | Tekst wyświetlany na odznace zdjęcia produktu. |
| Konfiguracja modułu | Kolor odznaki AI | `#FF0000` (Czerwony) | Kolor tła odznaki AI. |
| Konfiguracja modułu | Kolor tekstu odznaki AI | `#FFFFFF` (Biały) | Kolor tekstu odznaki AI. |
| Konfiguracja modułu | Tekst dodatkowej informacji | Konfigurowalny | Pełny tekst dla informacji na stronie produktu. |
| Konfiguracja modułu | Tekst banera ogólnosklepowego | Konfigurowalny | Pełny tekst dla banera ogólnosklepowego. |
| Strona edycji produktu | Oznacz treść produktu jako wygenerowaną przez AI | N/A (na produkt) | Oznacza tekstową treść produktu jako wygenerowaną przez AI. |
| Strona edycji produktu | Oznacz zdjęcia produktów jako wygenerowane przez AI | N/A (na produkt) | Oznacza zdjęcia produktów jako wygenerowane przez AI. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem moduł i skonfigurowałem ustawienia, ale nie widzę żadnych odznak AI ani banerów w moim sklepie.**
**O1:**
1.  **Sprawdź „Włącz zgodność z ustawą o sztucznej inteligencji”:** Upewnij się, że główny przełącznik w konfiguracji modułu jest ustawiony na TAK.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Pamięć podręczna przeglądarki również może wymagać wyczyszczenia (Ctrl+F5 lub Cmd+R).
3.  **Sprawdź indywidualne ustawienia produktu:** W przypadku odznak i powiadomień na stronach produktów, upewnij się, że indywidualnie oznaczyłeś konkretne produkty jako zawierające treści/obrazy generowane przez AI na ich odpowiednich stronach edycji produktu.
4.  **Kompatybilność z motywem:** Chociaż moduł jest przeznaczony dla PrestaShop 9.x, niestandardowe motywy mogą czasami powodować konflikty. Jeśli problemy nadal występują, tymczasowo przełącz się na domyślny motyw PrestaShop, aby wykluczyć konflikt motywu.

**P2: Odznaka AI lub baner wyglądają dziwnie lub są źle umieszczone w moim niestandardowym motywie.**
**O2:** Jest to często konflikt CSS z Twoim motywem.
1.  **Zbadaj element:** Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać odznakę/baner AI. Poszukaj sprzecznych reguł CSS.
2.  **Niestandardowy CSS:** Może być konieczne dodanie niestandardowego CSS do arkusza stylów Twojego motywu (lub za pośrednictwem niestandardowego modułu CSS), aby dostosować pozycjonowanie lub stylizację. Klasy CSS modułu są zazwyczaj dobrze zdefiniowane (np. `.myaiactfree-badge`, `.myaiactfree-banner`).
3.  **Skontaktuj się z pomocą techniczną:** Jeśli nie czujesz się komfortowo z CSS, skontaktuj się z pomocą techniczną MyPresta.eu lub swoim programistą.

**P3: Jak przetłumaczyć tekst odznaki AI, tekst banera lub dodatkową informację na inne języki?**
**O3:**
1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów” dla „Typu tłumaczenia”.
3.  Wybierz swój motyw i język, na który chcesz przetłumaczyć.
4.  Znajdź moduł „Free My AI Act” na liście. Będziesz mógł przetłumaczyć skonfigurowane pola tekstowe (Tekst odznaki AI, Tekst dodatkowej informacji, Tekst banera ogólnosklepowego) bezpośrednio tam.
5.  Zapisz zmiany.

**P4: Jaka jest różnica między tym modułem „Free” a „My AI Act Pro”?**
**O4:** Moduł „Free My AI Act” zapewnia podstawowe funkcje ujawniania informacji dla podstawowej zgodności. „My AI Act Pro” (oddzielny, płatny moduł) oferuje zaawansowane funkcjonalności, takie jak integracja z AI Studio, dostęp do API do automatycznego oznaczania, ścieżki audytu i zaawansowane możliwości znakowania wodnego dla obrazów. Wersja Free jest doskonałym punktem wyjścia, a możesz uaktualnić do wersji Pro, jeśli Twoje potrzeby staną się bardziej złożone.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, rozszerzyć lub rozwiązać problemy z modułem „Free My AI Act”.

### 4.1 Przegląd architektury
Moduł `myaiactfree` stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie hooki do wyświetlania w front-office i `getContent()` do konfiguracji w back-office. Integruje się bezpośrednio z interfejsem edycji produktu, podłączając się do `displayAdminProductsExtra`, aby zapewnić opcje oznaczania produktów jako generowanych przez AI. Konfiguracja jest przechowywana w `ps_configuration`, a renderowanie w front-office odbywa się za pomocą szablonów Smarty i dedykowanego pliku JavaScript do dynamicznych interakcji.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie zawiera żadnych dedykowanych kontrolerów front-office ani back-office. Cała logika front-office jest obsługiwana za pomocą hooków w głównym pliku modułu, a konfiguracja back-office jest zarządzana przez metodę `getContent()`.

### 4.3 Klasy i modele rdzenia (`classes/`)
Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Wszystkie dane są zarządzane bezpośrednio za pomocą `Configuration` dla ustawień globalnych i właściwości `Product` dla flag specyficznych dla produktu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`myaiactfree/views/js/front.js`**
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Ten skrypt jest prawdopodobnie odpowiedzialny za wszelkie dynamiczne zachowania w front-office związane z elementami ujawniania AI. Może to obejmować:
        *   Inicjalizację wyświetlania odznaki AI na zdjęciach produktów po załadowaniu DOM.
        *   Obsługę zdarzeń kliknięcia na banerze polityki AI (jeśli jest zamykalny lub ma interaktywne elementy).
        *   Zapewnienie prawidłowego pozycjonowania i responsywności odznaki lub banera AI, zwłaszcza jeśli obrazy są ładowane dynamicznie lub zmieniane rozmiary.
        *   Potencjalne dodawanie podpowiedzi lub wyskakujących okienek po najechaniu kursorem na odznaki AI.
        *   Wiązanie z zdarzeniami `prestashop.on` dla dynamicznych aktualizacji treści (np. `updateProduct` na stronie produktu).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`myaiactfree/views/css/admin.css`**
    *   **Zakres:** Stylizacja formularza administracyjnego back-office.
    *   **Odpowiedzialność:** Zapewnia stylizację dla strony konfiguracji modułu (`configure.tpl`) i potencjalnie niestandardowej zakładki/sekcji dodanej do strony edycji produktu (`product_tab.tpl`). Zapewnia to spójny i przyjazny dla użytkownika wygląd w Panelu administracyjnym PrestaShop.
    *   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w elementy w formularzu konfiguracji modułu, takie jak określone pola wejściowe, etykiety lub bloki informacyjne.

-   **`myaiactfree/views/css/front.css`**
    *   **Zakres:** Stylizacja dla klientów w front-office.
    *   **Odpowiedzialność:** Definiuje wygląd wszystkich elementów ujawniania AI widocznych dla klientów. Obejmuje to:
        *   Stylizację odznaki AI (np. `.myaiactfree-badge`, `.myaiactfree-badge-text`, `.myaiactfree-badge-icon`), w tym jej pozycję, kolor tła, kolor tekstu, dopełnienie i promień obramowania.
        *   Stylizację dodatkowej informacji na stronach produktów (np. `.myaiactfree-additional-info`).
        *   Stylizację ogólnosklepowego banera polityki AI (np. `.myaiactfree-banner`, `.myaiactfree-banner-text`, `.myaiactfree-banner-link`).
    *   **Kluczowe selektory klas CSS:** Programiści mogą nadpisać te klasy w niestandardowym CSS swojego motywu, aby dopasować je do projektu swojej marki.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   **`myaiactfree/views/templates/hook/additional_info.tpl`**:
        *   **Hook:** Prawdopodobnie renderowany w `displayProductExtraContent` lub podobnych hookach strony produktu.
        *   **Wyjście:** Wyświetla konfigurowalny tekst „Dodatkowej informacji” na stronie produktu, gdy produkt jest oznaczony jako wygenerowany przez AI.
    *   **`myaiactfree/views/templates/hook/ai_badge.tpl`**:
        *   **Hook:** Prawdopodobnie renderowany w `displayProductListReviews` (dla list produktów) lub `displayProductAdditionalInfo` (dla obrazu na stronie produktu).
        *   **Wyjście:** Generuje strukturę HTML dla odznaki AI, która nakłada się na zdjęcia produktów, w tym konfigurowalny tekst i stylizację.
    *   **`myaiactfree/views/templates/hook/banner.tpl`**:
        *   **Hook:** Prawdopodobnie renderowany w `displayHeader`, `displayTop`, `displayWrapperTop` lub `displayFooter`.
        *   **Wyjście:** Renderuje ogólnosklepowy baner polityki AI, w tym konfigurowalny tekst i link do strony polityki AI.

-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   **`myaiactfree/views/templates/admin/configure.tpl`**:
        *   **Cel:** Jest to główny szablon dla strony konfiguracji modułu dostępnej za pośrednictwem `getContent()`. Renderuje wszystkie globalne ustawienia (włącz/wyłącz, tekst odznaki, tekst banera itp.), jak opisano w sekcji 4.1.
    *   **`myaiactfree/views/templates/admin/configure_intro.tpl`**:
        *   **Cel:** Prawdopodobnie wyświetla wiadomość wprowadzającą lub wyjaśnienie na górze strony konfiguracji modułu, być może wyjaśniając ustawę o sztucznej inteligencji lub cel modułu.
    *   **`myaiactfree/views/templates/admin/product_tab.tpl`**:
        *   **Hook:** Renderowany za pośrednictwem `displayAdminProductsExtra`.
        *   **Cel:** Ten szablon zapewnia interfejs na stronie edycji produktu (Panel administracyjny > Katalog > Produkty > Edytuj produkt), gdzie sprzedawcy mogą indywidualnie oznaczyć treść i obrazy produktu jako wygenerowane przez AI. Zawiera pola wyboru lub przełączniki dla flag AI specyficznych dla produktu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy niestandardowych tabel SQL.
    *   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy zazwyczaj poprzedzonych prefiksem `MYAIACTFREE_`. Przykłady:
        *   `MYAIACTFREE_ENABLED`
        *   `MYAIACTFREE_SHOW_BADGE`
        *   `MYAIACTFREE_BADGE_TEXT`
        *   `MYAIACTFREE_BADGE_COLOR`
        *   `MYAIACTFREE_BADGE_TEXT_COLOR`
        *   `MYAIACTFREE_SHOW_ADDITIONAL_INFO`
        *   `MYAIACTFREE_ADDITIONAL_INFO_TEXT`
        *   `MYAIACTFREE_SHOW_BANNER`
        *   `MYAIACTFREE_BANNER_TEXT`
        *   `MYAIACTFREE_POLICY_URL`
    *   Flagi AI specyficzne dla produktu (dla treści i obrazów) są prawdopodobnie przechowywane jako właściwości obiektu `Product` lub w niestandardowym polu związanym z encją `Product`, być może poprzez `Configuration::updateValue` z sufiksem ID produktu lub bezpośrednio modyfikując dane obiektu `Product`.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie zasobów CSS/JS (`front.css`, `front.js`) i potencjalnie ogólnosklepowego banera (`banner.tpl`). |
| `displayTop` / `displayWrapperTop` | Często na samym szczycie treści strony. | Alternatywny hook dla ogólnosklepowego banera (`banner.tpl`). |
| `displayFooter` | Na dole każdej strony. | Alternatywny hook dla ogólnosklepowego banera (`banner.tpl`). |
| `displayProductListReviews` | Na stronach list produktów, w pobliżu zdjęć produktów. | Renderowanie odznaki AI (`ai_badge.tpl`) na miniaturach produktów. |
| `displayProductAdditionalInfo` | Na stronie produktu, w pobliżu bloku obrazu/ceny produktu. | Renderowanie odznaki AI (`ai_badge.tpl`) na głównym obrazie produktu. |
| `displayProductExtraContent` | Na stronie produktu, zazwyczaj pod opisem lub w nowej zakładce. | Renderowanie dodatkowej informacji (`additional_info.tpl`). |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Wstrzykiwanie niestandardowej zakładki/sekcji do oznaczania produktów jako generowanych przez AI (`product_tab.tpl`). |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Zapisywanie flag AI specyficznych dla produktu (treść/obraz) do bazy danych. |
| `actionProductAdd` | Po dodaniu nowego produktu w Panelu administracyjnym. | Inicjalizacja flag AI specyficznych dla nowych produktów. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Free My AI Act - Artificial Intelligence Act compliance” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub kompatybilności modułu.
