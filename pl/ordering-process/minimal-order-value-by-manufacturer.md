---
title: "Minimalna wartość zamówienia według producenta - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop „Minimalna wartość zamówienia według producenta” od MyPresta.eu."
sidebar:
  label: "Minimalna wartość zamówienia według producenta - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Minimal order value by manufacturer na MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-manufacturer.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/minimal-order-value-by-manufacturer/)
>
> ---


# Minimalna wartość zamówienia według producenta

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny bezpośrednio po instalacji lub po kliknięciu „Konfiguruj” obok modułu w Menedżerze modułów.

- **Co robi ten ekran:** Ta strona umożliwia włączanie/wyłączanie modułu i zarządzanie podstawowymi ustawieniami, które kontrolują jego zachowanie.

#### Ustawienia i opcje

- **Włącz / Wyłącz moduł:**

  - **Co robi to ustawienie:** Jest to globalny przełącznik do włączania lub wyłączania całej funkcjonalności modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Moduł będzie aktywnie sprawdzał minimalne wartości zamówień według producenta w koszykach klientów i stosował ograniczenia, jeśli warunki nie zostaną spełnione.
    - *Gdy wyłączony:* Moduł przestanie działać. Nie będą wykonywane żadne sprawdzenia minimalnej wartości zamówienia, a klienci będą mogli zamawiać dowolną kwotę od dowolnego producenta.
  - **Zalecana wartość:** **TAK** (aby aktywować podstawową funkcję modułu).
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz wyłączyć wszystkie zasady minimalnego zamówienia bez ich usuwania, możesz to wyłączyć.
- **Wyświetl wiadomość na stronie koszyka:**

  - **Co robi to ustawienie:** Kontroluje, czy na stronie koszyka wyświetlana jest wiadomość ostrzegawcza dla klienta, jeśli minimalna wartość zamówienia producenta nie zostanie spełniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Klienci zobaczą jasną, informacyjną wiadomość na stronie koszyka, wskazującą, którego minimum producenta nie spełniono i ile jeszcze muszą dodać.
    - *Gdy wyłączony:* Na stronie koszyka nie pojawi się żadna wiadomość. Ograniczenie nadal będzie obowiązywać, ale klient może odkryć je dopiero później podczas realizacji zamówienia, co może prowadzić do frustracji.
  - **Zalecana wartość:** **TAK**.
  - **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji zapewnia lepsze doświadczenie użytkownika, kierując klientów do rozwiązania problemu wcześnie, zamiast zaskakiwać ich przy kasie.
- **Wyświetl wiadomość na stronie realizacji zamówienia:**

  - **Co robi to ustawienie:** Kontroluje, czy na stronie realizacji zamówienia wyświetlana jest wiadomość ostrzegawcza dla klienta, jeśli minimalna wartość zamówienia producenta nie zostanie spełniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Klienci zobaczą wiadomość na stronie realizacji zamówienia, uniemożliwiającą im sfinalizowanie zamówienia, dopóki minimum nie zostanie spełnione.
    - *Gdy wyłączony:* Proces realizacji zamówienia może po prostu zatrzymać się bez jasnego wyjaśnienia, lub moduł może uniemożliwić postęp bez konkretnej wiadomości, co może wprowadzić klientów w błąd.
  - **Zalecana wartość:** **TAK**.
  - **Scenariusz/przykład dla sprzedawcy:** Jest to kluczowe dla zapobiegania zamówieniom, które nie spełniają Twoich kryteriów, oraz dla jasnego komunikowania klientowi powodu.
- **Wiadomość do wyświetlenia (dla stron koszyka i realizacji zamówienia):**

  - **Co robi to ustawienie:** Umożliwia dostosowanie tekstu wiadomości ostrzegawczej wyświetlanej klientom, gdy minimalna wartość zamówienia nie zostanie spełniona. Możesz używać symboli zastępczych, takich jak `{manufacturer_name}` i `{missing_amount}`.
  - **Efekt zmiany tego ustawienia:**
    - *Po zmianie:* Niestandardowa wiadomość pojawi się w front-office.
    - *Po pozostawieniu domyślnej:* Zostanie użyta standardowa wiadomość.
  - **Zalecana wartość:** Dostosuj, aby była jasna i pomocna. Przykład: „Aby sfinalizować zamówienie, musisz dodać {missing\_amount} więcej produktów od {manufacturer\_name}.”
  - **Scenariusz/przykład dla sprzedawcy:** Możesz chcieć, aby wiadomość była bardziej przyjazna, zawierała wezwanie do działania lub była zgodna z tonem Twojej marki.

### 2.2 Dedykowane ekrany administracyjne: Zasady minimalnej wartości zamówienia według producenta (Panel administracyjny > Katalog > Minimalna wartość zamówienia według producenta)

Ten ekran służy do definiowania i zarządzania rzeczywistymi zasadami minimalnej wartości zamówienia dla każdego producenta.

- **Nazwa ekranu i lokalizacja w menu:** „Minimalna wartość zamówienia według producenta” w menu **Katalog**.
- **Co robi ten ekran:** Jest to dedykowany obszar zarządzania do dodawania, edytowania i usuwania zasad dotyczących minimalnych wartości zamówień dla każdego producenta. Przedstawia listę wszystkich aktualnie skonfigurowanych zasad.

#### Dostępne akcje i ustawienia

- **Lista zasad:**

  - **Co to robi:** Wyświetla tabelę wszystkich istniejących zasad minimalnej wartości zamówienia. Każdy wiersz zazwyczaj pokazuje nazwę producenta, ustawioną minimalną wartość oraz opcje edycji lub usunięcia zasady.
  - **Efekt zmian:** Ta tabela zapewnia przegląd wszystkich aktywnych zasad.
  - **Zalecany przepływ pracy:** Regularnie przeglądaj tę listę, aby upewnić się, że Twoje zasady są aktualne z potrzebami Twojej firmy.
- **Przycisk „Dodaj nową zasadę”:**

  - **Co to robi:** Kliknięcie tego przycisku przenosi Cię do formularza, w którym możesz utworzyć nową zasadę minimalnej wartości zamówienia.
  - **Efekt zmian:** Otwiera nowy formularz.
  - **Zalecany przepływ pracy:** Użyj tego, gdy musisz ustawić nowe minimum dla producenta, którego jeszcze nie ma na liście.
- **Przycisk „Edytuj” (dla każdej zasady):**

  - **Co to robi:** Umożliwia modyfikację ustawień istniejącej zasady.
  - **Efekt zmian:** Otwiera formularz zasady z wstępnie wypełnionymi danymi, umożliwiając zmianę producenta lub minimalnej wartości.
  - **Zalecany przepływ pracy:** Użyj tego, aby dostosować minima w oparciu o nowe umowy z dostawcami lub strategie sprzedaży.
- **Przycisk „Usuń” (dla każdej zasady):**

  - **Co to robi:** Usuwa konkretną zasadę minimalnej wartości zamówienia.
  - **Efekt zmian:** Zasada jest natychmiast usuwana, a powiązany producent nie będzie już miał wymogu minimalnej wartości zamówienia.
  - **Zalecany przepływ pracy:** Użyj tego, gdy producent nie wymaga już minimalnego zamówienia lub jeśli wycofujesz markę.

#### Formularz dodawania/edycji zasady

Podczas dodawania nowej zasady lub edytowania istniejącej zazwyczaj zobaczysz następujące pola:

- **Producent:**

  - **Co robi to ustawienie:** To pole umożliwia wybranie konkretnego producenta, do którego będzie miała zastosowanie ta zasada minimalnej wartości zamówienia. Zazwyczaj zawiera wyszukiwanie z autouzupełnianiem, aby ułatwić znalezienie producentów.
  - **Efekt zmiany tego ustawienia:** Łączy zasadę z konkretnym producentem.
  - **Zalecana wartość:** Wybierz dokładnie producenta, do którego zamierzasz zastosować zasadę.
  - **Scenariusz/przykład dla sprzedawcy:** Możesz wybrać „Apple”, aby ustawić minimum dla wszystkich produktów Apple, lub „Samsung” dla produktów Samsung.
- **Minimalna wartość zamówienia:**

  - **Co robi to ustawienie:** Tutaj wprowadzasz wartość liczbową (w domyślnej walucie Twojego sklepu, np. USD, EUR), która reprezentuje minimalną całkowitą kwotę wymaganą dla produktów od wybranego producenta.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiona jest wartość (np. 50.00):* Klienci muszą mieć w koszyku produkty od wybranego producenta o wartości co najmniej 50.00, aby kontynuować.
    - *Gdy ustawiona na 0 lub pozostawiona pusta:* Skutecznie wyłącza to minimum dla tego producenta (chociaż lepiej jest usunąć zasadę, jeśli nie jest potrzebne żadne minimum).
  - **Zalecana wartość:** Dodatnia wartość liczbowa odzwierciedlająca Twoje wymagania biznesowe.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój dostawca dla „BrandX” wymaga od Ciebie zamówienia produktów o wartości co najmniej 100 USD, ustawisz to na „100.00” dla „BrandX”.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz moduł | TAK | Globalny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | Wyświetl wiadomość na stronie koszyka | TAK | Pokazuje ostrzeżenie w koszyku, jeśli minimum nie zostało spełnione. |
| Konfiguracja modułu | Wyświetl wiadomość na stronie realizacji zamówienia | TAK | Pokazuje ostrzeżenie przy kasie, jeśli minimum nie zostało spełnione. |
| Konfiguracja modułu | Wiadomość do wyświetlenia | Możliwość dostosowania | Dostosowuje tekst wiadomości ostrzegawczej. |
| AdminMobmController | Producent (Dodaj/Edytuj zasadę) | Wybierz z listy | Łączy zasadę z konkretnym producentem. |
| AdminMobmController | Minimalna wartość zamówienia (Dodaj/Edytuj zasadę) | Wartość liczbowa | Ustawia minimalną całkowitą wartość dla produktów wybranego producenta. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem minimum, ale nie działa ono w front-office. Co powinienem sprawdzić?**
O1:

- **Czy moduł jest włączony?** Przejdź do `Moduły > Menedżer modułów` i upewnij się, że „Minimalna wartość zamówienia według producenta” jest aktywny.
- **Czy konkretna zasada jest włączona?** Sprawdź `Katalog > Minimalna wartość zamówienia według producenta`, aby upewnić się, że zasada dla danego producenta jest poprawnie skonfigurowana z dodatnią wartością.
- **Wyczyść pamięć podręczną:** Przejdź do `Zaawansowane > Wydajność` i kliknij „Wyczyść pamięć podręczną” (dla wszystkich pamięci podręcznych). Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian.
- **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły, które modyfikują koszyk lub proces realizacji zamówienia, aby sprawdzić, czy nie ma konfliktu.

**P2: Wiadomość na stronie koszyka/realizacji zamówienia nie wyświetla się.**
O2:

- **Sprawdź konfigurację modułu:** Przejdź do `Moduły > Menedżer modułów > Konfiguruj` dla „Minimalna wartość zamówienia według producenta”. Upewnij się, że „Wyświetl wiadomość na stronie koszyka” i „Wyświetl wiadomość na stronie realizacji zamówienia” są ustawione na **TAK**.
- **Czy minimum faktycznie nie zostało spełnione?** Sprawdź dokładnie, czy produkty w koszyku od konkretnego producenta faktycznie spadają poniżej ustawionego minimum.

**P3: Czy mogę ustawić różne minima dla różnych grup klientów?**
O3: Ten moduł, w swojej standardowej formie, stosuje jedną minimalną wartość na producenta dla wszystkich klientów. Jeśli potrzebujesz minimów specyficznych dla grup klientów, wymagałoby to niestandardowego rozwoju lub innego modułu.

**P4: Jak moduł obsługuje sklepy wielowalutowe?**
O4: Moduł używa domyślnej waluty Twojego sklepu (zdefiniowanej w `Lokalizacja > Waluty` i `Lokalizacja > Lokalizacja`) dla ustawionej „Minimalnej wartości zamówienia”. Automatycznie przeliczy całkowitą wartość koszyka klienta na domyślną walutę do porównania, zapewniając spójność.

**P5: Moduł wydaje się spowalniać moją witrynę. Co mogę zrobić?**
O5:

- **Wyczyść pamięć podręczną:** Upewnij się, że wszystkie pamięci podręczne są regularnie czyszczone (`Zaawansowane > Wydajność`).
- **Zasoby serwera:** Sprawdź zasoby środowiska hostingowego (CPU, RAM). Jeśli Twój sklep ma bardzo dużą liczbę producentów lub produktów, upewnij się, że Twój serwer może obsłużyć obciążenie.
- **Aktualizacje modułu:** Zawsze używaj najnowszej wersji modułu z MyPresta.eu, ponieważ aktualizacje często zawierają ulepszenia wydajności.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Minimalna wartość zamówienia według producenta” dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller). Głównie rozszerza `Module` dla swojej podstawowej funkcjonalności i konfiguracji, wykorzystuje `AdminController` do zarządzania zasadami w panelu administracyjnym oraz `ModuleFrontController` do interakcji AJAX w front-office związanych z walidacją koszyka. Nie wydaje się używać niestandardowych klas `ObjectModel`, zamiast tego opiera się na `Configuration` dla ogólnych ustawień i bezpośredniej interakcji z bazą danych (lub potencjalnie prostej strukturze tablicowej) dla zasad specyficznych dla producenta. Haki są szeroko wykorzystywane do integracji z przepływem koszyka i realizacji zamówienia.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery front-office

- `controllers/front/ajax.php`
  - **Nazwa klasy:** `MobmAjaxModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików) rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za obsługę żądań AJAX z front-office, w szczególności tych związanych z aktualizacjami koszyka lub postępem realizacji zamówienia. Otrzymywałby dane koszyka, wykonywałby sprawdzenia minimalnej wartości zamówienia i zwracałby odpowiedź JSON wskazującą, czy warunki są spełnione i jakie wiadomości powinny być wyświetlone. Jest to kluczowe dla dynamicznych aktualizacji bez pełnego przeładowania strony.
- `controllers/front/index.php`
  - **Nazwa klasy:** `MobmIndexModuleFrontController` (prawdopodobnie) rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Ten plik może być placeholderem lub używany do prostej strony front-office, jeśli moduł taką posiadał. Biorąc pod uwagę cel modułu, jest mniej prawdopodobne, aby renderował pełną stronę, a bardziej prawdopodobne, że będzie to rezerwa lub część łańcucha przekierowań, jeśli `ajax.php` jest głównym punktem interakcji.

#### Kontrolery administracyjne back-office

- `controllers/admin/AdminMobm.php`
  - **Nazwa klasy:** `AdminMobmController` rozszerzająca `ModuleAdminController`.
  - **Nazwa zakładki:** „Minimalna wartość zamówienia według producenta” (w menu Katalog).
  - **Zarządzana encja:** Zarządza encją `mobm`, która reprezentuje indywidualne zasady minimalnej wartości zamówienia dla producentów.
  - **Odpowiedzialność:** Jest to główny kontroler do zarządzania listą zasad minimalnej wartości zamówienia producenta. Obsługuje:
    - Wyświetlanie listy istniejących zasad (za pomocą `renderList()`).
    - Dodawanie nowych zasad (za pomocą `renderForm()` dla formularza dodawania).
    - Edytowanie istniejących zasad (za pomocą `renderForm()` dla formularza edycji).
    - Usuwanie zasad.
    - Walidację formularzy i zapisywanie danych.
    - Prawdopodobnie współdziała z tabelą `ps_configuration` lub niestandardową tabelą w celu przechowywania identyfikatora producenta i powiązanej z nim minimalnej wartości.
- `controllers/admin/index.php`
  - **Nazwa klasy:** `AdminMobmIndexModuleAdminController` (prawdopodobnie) rozszerzająca `ModuleAdminController`.
  - **Odpowiedzialność:** Podobnie jak `index.php` w front-office, może to być placeholder lub domyślny punkt wejścia. W PrestaShop pliki `index.php` w katalogach kontrolerów często służą jako podstawowe środki bezpieczeństwa (np. `die('Access Denied');`) lub proste routowanie, jeśli nie są jawnie obsługiwane przez bardziej specyficzny kontroler.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł albo:

1. Przechowuje swoje zasady producenta bezpośrednio w tabeli `ps_configuration` (np. jako serializowana tablica).
2. Używa bezpośrednich zapytań do bazy danych w głównym pliku modułu lub kontrolerze administracyjnym do zarządzania niestandardową tabelą.
3. Zarządza danymi jako prostą tablicą w kontekście modułu bez formalnej klasy `ObjectModel`.

Biorąc pod uwagę, że `AdminMobmController` zarządza encją `mobm`, jest bardzo prawdopodobne, że niestandardowa tabela (np. `ps_mobm`) jest tworzona podczas instalacji, a `AdminMobmController` niejawnie obsługuje operacje CRUD dla tej tabeli bez dedykowanej klasy `ObjectModel` w `classes/`. Definicja `$definition` dla tej encji byłaby wtedy zdefiniowana bezpośrednio w `AdminMobmController` lub głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

- `mobm/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Panel administracyjny (prawdopodobnie dla formularza `AdminMobmController`).
  - **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania do wyboru producentów w formularzu „Dodaj/Edytuj zasadę”. Nasłuchuje na dane wejściowe użytkownika w polu tekstowym, wysyła żądania AJAX do kontrolera back-office (np. `AdminManufacturers` lub niestandardowej metody `AdminMobm`) w celu pobrania pasujących nazw producentów i wyświetla sugestie.
- `mobm/views/js/mobm.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Jest to główny plik JavaScript front-office dla modułu. Prawdopodobnie:
    - Wiąże się z zdarzeniami na stronie koszyka (np. zmiany ilości, dodawanie/usuwanie produktów).
    - Wiąże się z zdarzeniami na stronie realizacji zamówienia (np. kliknięcia przycisku „Przejdź do kasy”).
    - Wysyła żądania AJAX do `controllers/front/ajax.php` w celu walidacji koszyka pod kątem minimów producenta.
    - Odbiera odpowiedzi JSON i dynamicznie aktualizuje interfejs użytkownika za pomocą wiadomości ostrzegawczych lub zapobiega postępowi, jeśli minima nie zostaną spełnione.
    - Może obsługiwać wyskakujące okienka modalne lub wizualne wskazówki dla klienta.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `mobm/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Stylizuje rozwijaną listę autouzupełniania i pole wprowadzania używane do wyboru producenta w formularzu administracyjnym.
  - **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w klasy takie jak `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` itp.
- `mobm/views/css/mobm.css`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Stylizuje wiadomości ostrzegawcze wyświetlane na stronach koszyka i realizacji zamówienia. Zapewnia, że te wiadomości są wizualnie odrębne i dobrze integrują się z motywem.
  - **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w niestandardowe klasy dodane przez moduł do kontenerów wiadomości ostrzegawczych, np. `.mobm-warning-message`, `.mobm-error-block`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- `mobm/lib/searchTool/views/scripts.tpl`
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Ten szablon prawdopodobnie zawiera niezbędny JavaScript dla funkcjonalności autouzupełniania (z `autocomplete.js`) i potencjalnie jakiś skrypt inline lub konfigurację dla niego. Byłby renderowany w metodzie `renderForm()` kontrolera `AdminMobmController`.
- `mobm/views/templates/front/displayShoppingCart.tpl`
  - **Zakres:** Front-office.
  - **Hak:** Ten szablon jest przeznaczony do renderowania w haku, który wyświetla zawartość na stronie koszyka, takim jak `displayShoppingCartFooter` lub `displayBeforeShoppingCartBlock`.
  - **Odpowiedzialność:** Wyświetla wiadomość ostrzegawczą dla klienta, jeśli minimalna wartość zamówienia producenta nie zostanie spełniona. Będzie zawierać logikę wyświetlania wiadomości tylko wtedy, gdy `{$mobm_warning_message}` (lub podobna zmienna przekazana z modułu) nie jest pusta.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

- **`ps_configuration`**: Przechowuje ogólne ustawienia modułu (np. `PS_MOVB_ENABLED`, `PS_MOVB_CART_MSG_ENABLED`, `PS_MOVB_CHECKOUT_MSG_ENABLED`, `PS_MOVB_CUSTOM_MESSAGE`).
- **`ps_mobm` (Prawdopodobnie niestandardowa tabela)**: Ta tabela jest bardzo prawdopodobna, biorąc pod uwagę, że `AdminMobmController` zarządza encją `mobm`.
  - **Kolumny (hipotetyczne):**
    - `id_mobm` (Klucz podstawowy, INT)
    - `id_manufacturer` (INT, Klucz obcy do `ps_manufacturer`)
    - `min_value` (DECIMAL(20,6), przechowuje minimalną kwotę zamówienia)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)

#### Tabela zarejestrowanych haków

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` wszystkich stron front-office. | Aby dołączyć zasoby CSS (`mobm.css`) i JavaScript (`mobm.js`) front-office. |
| `actionCartSave` | Po zapisaniu koszyka (np. zmiana ilości, dodanie/usunięcie produktu). | Aby wykonać walidację minimalnych wartości producenta w czasie rzeczywistym i potencjalnie zapisać status walidacji. |
| `actionValidateOrder` | Przed oficjalną walidacją zamówienia. | Aby zapobiec walidacji zamówienia, jeśli minimalne wartości producenta nie zostaną spełnione. |
| `displayShoppingCartFooter` (lub podobny) | Na dole strony koszyka. | Aby wyświetlić wiadomość ostrzegawczą (`displayShoppingCart.tpl`), jeśli minima nie zostaną spełnione. |
| `displayPaymentTop` (lub podobny hak realizacji zamówienia) | Na górze kroku wyboru płatności w realizacji zamówienia. | Aby wyświetlić wiadomość ostrzegawczą i zapobiec postępowi, jeśli minima nie zostaną spełnione. |
| `displayAdminProductsExtra` (lub podobny) | Na stronie edycji produktu w panelu administracyjnym. | Potencjalnie do wyświetlania informacji o minimalnej wartości producenta bezpośrednio na stronach produktów (mniej prawdopodobne, ale możliwe). |
| `displayBackOfficeHeader` | W sekcji `<head>` wszystkich stron panelu administracyjnego. | Aby dołączyć zasoby CSS (`autocomplete.css`) i JavaScript (`autocomplete.js`) panelu administracyjnego dla formularza `AdminMobmController`. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i upewnienia się, że używasz najnowszej, najbardziej kompatybilnej wersji modułu „Minimalna wartość zamówienia według producenta”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
