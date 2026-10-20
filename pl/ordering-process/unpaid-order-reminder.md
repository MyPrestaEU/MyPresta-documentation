---
title: "Przypomnienie o niezapłaconym zamówieniu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Przypomnienie o niezapłaconym zamówieniu” od MyPresta.eu."
sidebar:
  label: "Przypomnienie o niezapłaconym zamówieniu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Unpaid order reminder na MyPresta.eu](https://mypresta.eu/modules/ordering-process/unpaid-order-reminder.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/unpaid-order-reminder/)
>
> ---


# Przypomnienie o niezapłaconym zamówieniu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Upewnij się, że funkcja cron job Twojego serwera jest włączona i poprawnie skonfigurowana, aby automatyczne przypomnienia modułu działały.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Moduł „Przypomnienie o niezapłaconym zamówieniu” oferuje kilka ekranów konfiguracji do zarządzania ustawieniami przypomnień, przeglądania historii i obsługi klientów, którzy zrezygnowali z subskrypcji.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Przypomnienie o niezapłaconym zamówieniu)

Jest to główny ekran konfiguracji, na którym ustawiasz podstawowe zachowanie modułu.

- **Co robi to ustawienie:** Ta sekcja pozwala włączyć lub wyłączyć moduł, skonfigurować zadanie cron i zarządzać ogólnymi ustawieniami dla e-maili z przypomnieniami.
- **Wpływ zmiany tego ustawienia:** Kontroluje ogólną funkcjonalność i automatyzację systemu przypomnień.

#### Ustawienia ogólne

- **Włącz moduł:**

  - **Co robi to ustawienie:** Włącza lub wyłącza cały moduł „Przypomnienie o niezapłaconym zamówieniu”.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączony:* Moduł zacznie wysyłać przypomnienia zgodnie z zdefiniowanymi regułami i zadaniem cron.
    - *Gdy wyłączony:* Nie będą wysyłane żadne przypomnienia, a moduł będzie nieaktywny.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład dla sprzedawcy:** Włącz to po skonfigurowaniu reguł przypomnień, aby rozpocząć odzyskiwanie niezapłaconych zamówień. Wyłącz, jeśli musisz tymczasowo wstrzymać wszystkie przypomnienia z powodu konserwacji lub konkretnej kampanii.
- **URL zadania Cron:**

  - **Co robi to ustawienie:** Wyświetla unikalny adres URL, który zadanie cron Twojego serwera musi okresowo wykonywać. Ten adres URL uruchamia moduł, aby sprawdzić niezapłacone zamówienia i wysłać przypomnienia.
  - **Wpływ zmiany tego ustawienia:** Ten adres URL jest kluczowy dla automatyzacji modułu. Bez jego wywołania przez zadanie cron, żadne przypomnienia nie zostaną wysłane automatycznie.
  - **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go w menedżerze zadań cron w panelu sterowania hostingu.
  - **Scenariusz / przykład dla sprzedawcy:** Zazwyczaj konfigurujesz to raz podczas początkowej konfiguracji. Na przykład, możesz skonfigurować swój serwer, aby wywoływał ten adres URL co godzinę, aby zapewnić terminowe przypomnienia.
- **Link do rezygnacji z subskrypcji w e-mailu:**

  - **Co robi to ustawienie:** Określa, czy link do rezygnacji z subskrypcji jest dołączany do e-maili z przypomnieniami.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączony:* Klienci mogą kliknąć link w e-mailu, aby zrezygnować z przyszłych przypomnień o niezapłaconych zamówieniach.
    - *Gdy wyłączony:* Klienci nie mogą łatwo zrezygnować, co może prowadzić do frustracji lub oznaczenia Twoich e-maili jako spam.
  - **Zalecana wartość:** TAK (Wysoce zalecane dla zgodności i satysfakcji klienta).
  - **Scenariusz / przykład dla sprzedawcy:** Zawsze dołączaj to, aby dać klientom kontrolę i utrzymać dobrą reputację nadawcy.
- **Statusy zamówień do przypomnienia:**

  - **Co robi to ustawienie:** Pozwala wybrać, które konkretne statusy zamówień powinny wywołać przypomnienie. Zazwyczaj są to statusy wskazujące, że zamówienie oczekuje na płatność (np. „Oczekiwanie na przelew bankowy”, „Oczekiwanie na płatność czekiem”).
  - **Wpływ zmiany tego ustawienia:** Tylko zamówienia z wybranymi statusami będą brane pod uwagę do przypomnień.
  - **Zalecana wartość:** Wybierz wszystkie statusy, które reprezentują zamówienie oczekujące na płatność.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli używasz „Oczekiwanie na przelew bankowy” i „Oczekiwanie na płatność czekiem”, wybierz oba. Jeśli masz niestandardowy status, taki jak „Oczekująca płatność bramki”, również go uwzględnij.
- **Statusy zamówień do zatrzymania przypomnień:**

  - **Co robi to ustawienie:** Definiuje, które statusy zamówień, jeśli zostaną osiągnięte, powinny zatrzymać dalsze przypomnienia dla tego konkretnego zamówienia. Zazwyczaj obejmuje to statusy takie jak „Płatność zaakceptowana”, „Wysłane” lub „Anulowane”.
  - **Wpływ zmiany tego ustawienia:** Gdy zamówienie osiągnie jeden z tych statusów, moduł nie będzie już wysyłać przypomnień dla niego, zapobiegając niepotrzebnym lub mylącym e-mailom.
  - **Zalecana wartość:** Wybierz wszystkie statusy, które wskazują, że płatność została otrzymana, zamówienie jest przetwarzane lub zamówienie jest już nieważne (np. „Płatność zaakceptowana”, „Anulowane”, „Zwrócone”).
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli klient zapłaci za zamówienie, nie chcesz, aby otrzymał kolejne przypomnienie. Wybranie „Płatność zaakceptowana” tutaj to zapewnia.

#### Reguły przypomnień

Ta sekcja służy do definiowania rzeczywistych e-maili z przypomnieniami. Możesz tworzyć wiele reguł, każda z innym czasem i treścią e-maila.

- **Dodaj nową regułę przypomnienia:**
  - **Co robi to ustawienie:** Pozwala utworzyć nowy zestaw parametrów przypomnienia.
  - **Wpływ zmiany tego ustawienia:** Otwiera formularz do zdefiniowania nowego e-maila z przypomnieniem.
  - **Zalecana wartość:** Utwórz co najmniej jedną regułę.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć wysłać pierwsze przypomnienie po 24 godzinach, a drugie, bardziej pilne, po 72 godzinach.

Podczas dodawania/edycji reguły skonfigurujesz:

- **Dni po utworzeniu zamówienia:**

  - **Co robi to ustawienie:** Określa, ile dni po złożeniu zamówienia powinien zostać wysłany ten konkretny e-mail z przypomnieniem.
  - **Wpływ zmiany tego ustawienia:** Kontroluje czas wysyłki przypomnienia.
  - **Zalecana wartość:** Zacznij od 1 lub 2 dni dla pierwszego przypomnienia.
  - **Scenariusz / przykład dla sprzedawcy:** Ustaw na „1” dla pierwszego przypomnienia 24 godziny po zamówieniu. Ustaw na „3” dla drugiego przypomnienia 3 dni po zamówieniu.
- **Temat e-maila:**

  - **Co robi to ustawienie:** Temat e-maila z przypomnieniem.
  - **Wpływ zmiany tego ustawienia:** To, co klienci widzą w swojej skrzynce odbiorczej. Jasny, zwięzły temat zwiększa wskaźniki otwarć.
  - **Zalecana wartość:** Coś w stylu „Przypomnienie: Twoje niezapłacone zamówienie w [Nazwa sklepu]” lub „Wymagana akcja: Dokończ zamówienie #[ID zamówienia]”.
  - **Scenariusz / przykład dla sprzedawcy:** „Nie zapomnij o swoim zamówieniu z MyPresta.eu!”
- **Treść e-maila:**

  - **Co robi to ustawienie:** Główna treść e-maila z przypomnieniem. Możesz używać zmiennych (takich jak `{customer_name}`, `{order_id}`, `{shop_name}`) do personalizacji wiadomości.
  - **Wpływ zmiany tego ustawienia:** To jest główna wiadomość do Twojego klienta. Najlepiej sprawdzi się przyjazny, pomocny ton.
  - **Zalecana wartość:** Dołącz powitanie, wspomnij o niezapłaconym zamówieniu, podaj instrukcje, jak zapłacić lub gdzie znaleźć szczegóły płatności, i zaoferuj pomoc.
  - **Scenariusz / przykład dla sprzedawcy:** „Drogi {customer\_name}, To jest przypomnienie o Twoim ostatnim zamówieniu #{order\_id} w {shop\_name}. Wygląda na to, że płatność za to zamówienie jest nadal w toku. Prosimy o jak najszybsze dokonanie płatności, aby Twoje zamówienie zostało przetworzone. Szczegóły zamówienia możesz sprawdzić tutaj: [Link do historii zamówień]. W razie pytań prosimy o kontakt.”
- **Aktywny:**

  - **Co robi to ustawienie:** Włącza lub wyłącza tę konkretną regułę przypomnienia.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączony:* To przypomnienie zostanie wysłane zgodnie z jego harmonogramem.
    - *Gdy wyłączony:* To przypomnienie nie zostanie wysłane, nawet jeśli moduł jest aktywny.
  - **Zalecana wartość:** TAK dla aktywnych reguł.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz wyłączyć regułę, jeśli testujesz nową treść lub chcesz tymczasowo wstrzymać konkretne przypomnienie.

### 2.2 Zarządzanie przypomnieniami o zamówieniach (Panel administracyjny > Moduły > Przypomnienie o niezapłaconym zamówieniu > Przypomnienia o zamówieniach)

Ten dedykowany ekran, dostępny poprzez menu modułu w Panelu administracyjnym, pozwala przeglądać i zarządzać zamówieniami, które są obecnie kwalifikowane do przypomnień.

- **Nazwa ekranu i lokalizacja w menu:** **Przypomnienia o zamówieniach** (w pozycji menu „Przypomnienie o niezapłaconym zamówieniu”).
- **Dostępne akcje i ustawienia:** Ten ekran wyświetla listę zamówień, które aktualnie spełniają kryteria „Statusy zamówień do przypomnienia”.
  - **Widok siatki / zarządzania:** Zobaczysz tabelę z kolumnami takimi jak ID zamówienia, Nazwa klienta, Data zamówienia, Bieżący status i potencjalnie data następnego przypomnienia.
  - **Akcje:** Możesz mieć akcje do ręcznego wysłania przypomnienia dla konkretnego zamówienia lub do wykluczenia zamówienia z przyszłych przypomnień.
- **Wpływ zmian:**
  - **Ręczne wysłanie przypomnienia:** Natychmiast wysyła następny zaplanowany e-mail z przypomnieniem dla tego zamówienia.
  - **Wykluczenie zamówienia:** Zapobiega wysyłaniu przez moduł dalszych przypomnień dla tego konkretnego zamówienia, nawet jeśli jego status nadal odpowiada kryteriom przypomnienia.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj tę listę, aby uzyskać przegląd oczekujących niezapłaconych zamówień. Użyj opcji ręcznego wysyłania, jeśli klient dzwoni i chcesz natychmiast ponownie wysłać mu szczegóły płatności. Wyklucz zamówienia, jeśli zawarłeś specjalne porozumienie z klientem lub jeśli zamówienie jest problematyczne.

### 2.3 Historia przypomnień o zamówieniach (Panel administracyjny > Moduły > Przypomnienie o niezapłaconym zamówieniu > Historia)

Ten ekran zawiera dziennik wszystkich e-maili z przypomnieniami, które zostały wysłane przez moduł.

- **Nazwa ekranu i lokalizacja w menu:** **Historia** (w pozycji menu „Przypomnienie o niezapłaconym zamówieniu”).
- **Dostępne akcje i ustawienia:** Ten ekran wyświetla tabelę ze szczegółami każdego wysłanego przypomnienia:
  - Kolumny zazwyczaj obejmują: ID zamówienia, Nazwa klienta, Adres e-mail, Reguła przypomnienia (która reguła je wywołała), Data wysłania i potencjalnie temat e-maila.
- **Wpływ zmian:** Jest to dziennik tylko do odczytu. Nie dokonuje się tutaj bezpośrednich zmian, ale dostarcza on cennych informacji.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu, aby zweryfikować, czy przypomnienia są wysyłane poprawnie. Jeśli klient twierdzi, że nie otrzymał przypomnienia, możesz sprawdzić tę historię, aby potwierdzić, czy zostało ono wysłane.

### 2.4 Klienci, którzy zrezygnowali z subskrypcji (Panel administracyjny > Moduły > Przypomnienie o niezapłaconym zamówieniu > Klienci, którzy zrezygnowali z subskrypcji)

Ten ekran wyświetla listę klientów, którzy zrezygnowali z otrzymywania przypomnień o niezapłaconych zamówieniach.

- **Nazwa ekranu i lokalizacja w menu:** **Klienci, którzy zrezygnowali z subskrypcji** (w pozycji menu „Przypomnienie o niezapłaconym zamówieniu”).
- **Dostępne akcje i ustawienia:** Ten ekran wyświetla tabelę z:
  - Kolumny zazwyczaj obejmują: ID klienta, Nazwa klienta, Adres e-mail i Data rezygnacji z subskrypcji.
  - **Akcje:** Możesz mieć opcję ręcznego usunięcia klienta z tej listy, co skutecznie ponownie zasubskrybuje go do przypomnień (używaj ostrożnie i tylko na prośbę klienta).
- **Wpływ zmian:**
  - **Usunięcie z listy:** Klient ponownie będzie kwalifikował się do otrzymywania przypomnień, jeśli status jego zamówienia będzie zgodny.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Monitoruj tę listę, aby zrozumieć preferencje klientów. Ponownie subskrybuj klienta tylko wtedy, gdy wyraźnie o to poprosi.

### 2.5 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Włącza/wyłącza funkcjonalność modułu. |
|  | URL zadania Cron | Kopiuj i konfiguruj | Niezbędne do automatycznego wysyłania przypomnień. |
|  | Link do rezygnacji z subskrypcji w e-mailu | TAK | Pozwala klientom zrezygnować z subskrypcji, poprawia reputację nadawcy. |
|  | Statusy zamówień do przypomnienia | Oczekiwanie na przelew bankowy, Oczekiwanie na czek itp. | Definiuje, które statusy zamówień wywołują przypomnienia. |
|  | Statusy zamówień do zatrzymania przypomnień | Płatność zaakceptowana, Anulowane itp. | Zapobiega przypomnieniom dla opłaconych lub nieważnych zamówień. |
|  | **Reguły przypomnień** |  |  |
|  | Dni po utworzeniu zamówienia | 1, 3, 7 (przykład) | Ustawia czas dla każdego e-maila z przypomnieniem. |
|  | Temat e-maila | „Przypomnienie: Twoje niezapłacone zamówienie…” | Temat e-maila z przypomnieniem. |
|  | Treść e-maila | Spersonalizowana wiadomość ze zmiennymi | Treść e-maila z przypomnieniem. |
|  | Aktywny (dla każdej reguły) | TAK | Włącza/wyłącza poszczególne reguły przypomnień. |
| **Przypomnienia o zamówieniach** | (Lista kwalifikujących się zamówień) | N/A | Przegląd zamówień oczekujących na płatność. |
|  | Ręczne wysłanie przypomnienia | N/A | Natychmiast wysyła następne przypomnienie dla wybranego zamówienia. |
|  | Wyklucz zamówienie | N/A | Zapobiega przyszłym przypomnieniom dla wybranego zamówienia. |
| **Historia** | (Dziennik wysłanych przypomnień) | N/A | Ścieżka audytu wszystkich wysłanych e-maili z przypomnieniami. |
| **Klienci, którzy zrezygnowali z subskrypcji** | (Lista klientów, którzy zrezygnowali z subskrypcji) | N/A | Pokazuje klientów, którzy zrezygnowali z przypomnień. |
|  | Usuń z listy rezygnacji z subskrypcji | N/A | Ponownie subskrybuje klienta do przypomnień (używaj ostrożnie). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje przypomnienia nie są wysyłane. Co powinienem sprawdzić w pierwszej kolejności?**
**O1:**

-   **Moduł włączony:** Przejdź do **Moduły > Menedżer modułów > Przypomnienie o niezapłaconym zamówieniu** i upewnij się, że ustawienie „Włącz moduł” jest ustawione na TAK.
-   **Zadanie Cron:** Najczęstszy problem. Musisz skonfigurować zadanie cron na swoim serwerze hostingowym. Skopiuj „URL zadania Cron” ze strony konfiguracji modułu i dodaj go do menedżera zadań cron w panelu sterowania hostingu. Upewnij się, że jest ustawione na częste uruchamianie (np. co godzinę). Jeśli nie wiesz, jak to zrobić, skontaktuj się ze swoim dostawcą hostingu.
-   **Statusy zamówień:** Dokładnie sprawdź „Statusy zamówień do przypomnienia” i „Statusy zamówień do zatrzymania przypomnień” w konfiguracji modułu. Upewnij się, że zamówienia, dla których oczekujesz przypomnień, mają status wybrany na liście „do przypomnienia” i nie osiągnęły statusu na liście „do zatrzymania”.
-   **Reguły przypomnień aktywne:** Upewnij się, że poszczególne reguły przypomnień, które utworzyłeś, są oznaczone jako „Aktywne”.

**P2: Klienci otrzymują zbyt wiele przypomnień lub przypomnienia po dokonaniu płatności. Jak to naprawić?**
**O2:**

-   **„Statusy zamówień do zatrzymania przypomnień”:** To jest kluczowe. Upewnij się, że wszystkie statusy wskazujące na opłacone lub zakończone zamówienie (np. „Płatność zaakceptowana”, „Wysłane”, „Anulowane”, „Zwrócone”) są wybrane w tym ustawieniu. To informuje moduł, aby przestał wysyłać przypomnienia, gdy zamówienie osiągnie jeden z tych stanów.
-   **Czas reguły przypomnienia:** Przejrzyj „Dni po utworzeniu zamówienia” dla każdej reguły przypomnienia. Upewnij się, że są one odpowiednio rozłożone i nie nakładają się w sposób, który wysyła zbyt wiele e-maili zbyt szybko.

**P3: Czy mogę dostosować szablony e-maili?**
**O3:** Tak, moduł pozwala dostosować temat i treść e-maila bezpośrednio w ustawieniach reguły przypomnienia. Możesz używać specyficznych zmiennych (takich jak `{customer_name}`, `{order_id}`, `{shop_name}`) do personalizacji wiadomości. W celu bardziej zaawansowanej wizualnej personalizacji, deweloper musiałby zmodyfikować podstawowe pliki szablonów e-maili (znajdujące się w `mails/` w Twojej instalacji PrestaShop, korzystając ze struktury szablonów modułu jako przewodnika).

**P4: Link do rezygnacji z subskrypcji nie działa, lub klienci nadal otrzymują e-maile po rezygnacji z subskrypcji.**
**O4:**

-   **Link do rezygnacji z subskrypcji włączony:** Upewnij się, że „Link do rezygnacji z subskrypcji w e-mailu” jest ustawiony na TAK w głównej konfiguracji modułu.
-   **Sprawdź listę „Klienci, którzy zrezygnowali z subskrypcji”:** Przejdź do **Moduły > Przypomnienie o niezapłaconym zamówieniu > Klienci, którzy zrezygnowali z subskrypcji**. Sprawdź, czy adres e-mail klienta pojawia się na tej liście. Jeśli nie, być może nie zrezygnował z subskrypcji pomyślnie.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) po wprowadzeniu jakichkolwiek zmian w konfiguracji.

**P5: Co się stanie, jeśli klient ma wiele niezapłaconych zamówień?**
**O5:** Moduł będzie traktował każde niezapłacone zamówienie indywidualnie. Jeśli klient ma dwa oddzielne niezapłacone zamówienia, otrzyma przypomnienia dla każdego zamówienia zgodnie z Twoimi zdefiniowanymi regułami, o ile te zamówienia spełniają kryteria.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Przypomnienie o niezapłaconym zamówieniu”, przeznaczony dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Przypomnienie o niezapłaconym zamówieniu” (`oreminders`) przestrzega standardowej architektury modułów PrestaShop, wykorzystując zasady MVC. Skupia się głównie na administracji w panelu administracyjnym dla konfiguracji i zadaniu cron w front-office dla zautomatyzowanego przetwarzania. Rozszerza `Module` dla swojej podstawowej funkcjonalności i wykorzystuje niestandardowe klasy `AdminController` do zarządzania przypomnieniami, historią i klientami, którzy zrezygnowali z subskrypcji. Szablonowanie e-maili jest obsługiwane przez niestandardowy menedżer, a konfiguracja jest przechowywana w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/CronJob.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OremindersCronJobModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest zaprojektowany do wywoływania przez zadanie cron po stronie serwera. Jest to punkt wejścia dla zautomatyzowanej logiki modułu. Po wykonaniu, iteruje przez niezapłacone zamówienia, sprawdza je pod kątem zdefiniowanych reguł przypomnień i wysyła e-maile z przypomnieniami. Zazwyczaj zwraca prostą wiadomość o sukcesie/porażce lub dane wyjściowe dziennika.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OremindersIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to prawdopodobnie symbol zastępczy lub kontroler awaryjny. W wielu modułach `index.php` w `controllers/front` służy jako domyślny lub prosty punkt wejścia, jeśli nie jest wymagana żadna konkretna akcja. Może obsługiwać podstawowe wyświetlanie modułu lub przekierowanie, jeśli moduł miał obecność w front-office. Biorąc pod uwagę charakter modułu, jego główna interakcja z front-office odbywa się za pośrednictwem `CronJob.php`.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminOrderReminders.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminOrderRemindersController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Zarządza listą „Przypomnienia o zamówieniach”. Ten kontroler jest odpowiedzialny za wyświetlanie listy zamówień, które są obecnie kwalifikowane do przypomnień na podstawie konfiguracji modułu. Zapewnia akcje do ręcznego wysyłania przypomnień lub wykluczania konkretnych zamówień.
-   `controllers/admin/AdminOrderRemindersHistory.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminOrderRemindersHistoryController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Zarządza dziennikiem „Historii”. Ten kontroler wyświetla listę tylko do odczytu wszystkich e-maili z przypomnieniami, które zostały pomyślnie wysłane przez moduł, w tym szczegóły takie jak ID zamówienia, klient i data wysłania.
-   `controllers/admin/AdminOrderRemindersUnsub.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminOrderRemindersUnsubController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Zarządza listą „Klientów, którzy zrezygnowali z subskrypcji”. Ten kontroler wyświetla klientów, którzy zrezygnowali z otrzymywania przypomnień i pozwala na ich ponowne subskrybowanie (w razie potrzeby).
-   `controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminOremindersIndexController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Podobnie jak `index.php` w front-office, może służyć jako domyślny lub awaryjny kontroler administracyjny. Może potencjalnie obsługiwać główną konfigurację modułu, jeśli `getContent()` w głównym pliku modułu przekierowuje do niego, lub jeśli jest używany do konkretnej, prostej akcji administracyjnej.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczony spis nie zawiera jawnie plików SQL do tworzenia niestandardowych tabel. Sugeruje to jednak, że moduł może używać `ObjectModel` bezpośrednio w swoim głównym pliku modułu lub kontrolerach administracyjnych, albo zarządza danymi poprzez bezpośrednie zapytania do bazy danych lub poprzez rozszerzanie istniejących podstawowych modeli PrestaShop (np. `Order`, `Customer`).

Jeśli niestandardowe dane są przechowywane, prawdopodobnie są zarządzane za pośrednictwem `ps_configuration` dla ustawień i potencjalnie niestandardowych tabel bazy danych utworzonych podczas instalacji (chociaż nie wymieniono żadnych plików SQL, więc tworzenie tabel odbywałoby się w `install()`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `oreminders/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Ten skrypt prawdopodobnie zapewnia dynamiczną funkcjonalność dla interfejsu zarządzania szablonami e-maili w konfiguracji modułu. Może to obejmować:
        -   Dynamiczne dodawanie/usuwanie reguł przypomnień.
        -   Obsługę żądań AJAX do zapisywania/ładowania szablonów e-maili.
        -   Implementację edytora tekstu sformatowanego (np. integracja TinyMCE) dla treści e-maili.
        -   Zarządzanie wstawianiem zmiennych do szablonów e-maili.
        -   Walidację po stronie klienta dla pól formularza związanych z regułami e-maili.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `oreminders/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych w panelu administracyjnym.
    -   **Szczegóły:** Ten arkusz stylów zapewnia specyficzną stylizację dla interfejsu menedżera szablonów e-maili w konfiguracji modułu w Panelu administracyjnym. Definiowałby style dla:
        -   Układu formularzy reguł przypomnień.
        -   Stylizacji pól wejściowych, przycisków i obszarów tekstowych w edytorze szablonów.
        -   Zapewnienia spójnego wyglądu i działania z motywem Panelu administracyjnego PrestaShop.
    -   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać:** Szukaj specyficznych klas z prefiksem `oreminders-` lub `email-templates-manager-` w szablonach administracyjnych modułu, aby zidentyfikować elementy, które można dostosować.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `oreminders/views/templates/hook/form.tpl`
    -   **Hook:** Potencjalnie `displayAdminModuleConfigure` lub podobny, jeśli używany do małego formularza w kontekście hooka. Bardziej prawdopodobne, że jest to ogólny szablon formularza używany wewnętrznie.
    -   **Wyjście:** Renderuje ogólną strukturę formularza.
-   `oreminders/views/templates/hook/header.tpl`
    -   **Hook:** `displayHeader` (Front-office).
    -   **Wyjście:** Używany do dołączania niezbędnych plików CSS lub JavaScript w sekcji `<head>` front-office, jeśli moduł miał jakiekolwiek komponenty front-endowe (np. dla strony rezygnacji z subskrypcji).
-   `oreminders/views/templates/hook/identity.tpl`
    -   **Hook:** Niejasne z nazwy, ale `displayCustomerAccount` lub podobny do wyświetlania informacji specyficznych dla klienta, lub być może związany z procesem rezygnacji z subskrypcji.
    -   **Wyjście:** Może renderować wiadomość lub formularz związany z tożsamością lub preferencjami klienta.

#### Szablony administracyjne (`views/templates/admin/`)

-   `oreminders/lib/emailTemplatesManager/views/buttonManager.tpl`
    -   **Kontekst:** Używany w menedżerze szablonów e-maili.
    -   **Wyjście:** Renderuje przyciski do zarządzania szablonami e-maili (np. „Dodaj nową regułę”, „Zapisz”, „Usuń”).
-   `oreminders/lib/emailTemplatesManager/views/createTemplateForm.tpl`
    -   **Kontekst:** Używany w menedżerze szablonów e-maili.
    -   **Wyjście:** Renderuje formularz do tworzenia nowego szablonu/reguły e-maila z przypomnieniem.
-   `oreminders/lib/emailTemplatesManager/views/editTemplateForm.tpl`
    -   **Kontekst:** Używany w menedżerze szablonów e-maili.
    -   **Wyjście:** Renderuje formularz do edycji istniejącego szablonu/reguły e-maila z przypomnieniem.
-   `oreminders/lib/emailTemplatesManager/views/mainForm.tpl`
    -   **Kontekst:** Używany w menedżerze szablonów e-maili.
    -   **Wyjście:** Główny szablon opakowujący dla interfejsu zarządzania szablonami e-maili, prawdopodobnie łączący `buttonManager`, `createTemplateForm` i `editTemplateForm`.
-   `oreminders/lib/emailTemplatesManager/views/selectInput.tpl`
    -   **Kontekst:** Używany w menedżerze szablonów e-maili.
    -   **Wyjście:** Szablon wielokrotnego użytku do renderowania rozwijanego pola `<select>`, prawdopodobnie do wyboru statusów zamówień lub innych opcji.
-   `oreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    -   **Kontekst:** Używany przez `AdminOrderRemindersController` dla jego widoków formularzy (np. jeśli istnieje formularz dodawania/edycji wpisu przypomnienia o zamówieniu, chociaż jest to głównie kontroler listy).
    -   **Wyjście:** Renderuje standardowy formularz administracyjny PrestaShop.
-   `oreminders/views/templates/admin/order_reminders/helpers/list/list_action_email.tpl`
    -   **Kontekst:** Używany przez `AdminOrderRemindersController` w widoku listy.
    -   **Wyjście:** Renderuje konkretny przycisk akcji lub link w liście przypomnień o zamówieniach, prawdopodobnie dla „Wyślij e-mail” lub „Wyświetl e-mail”.
-   `oreminders/views/templates/admin/script.tpl`
    -   **Kontekst:** Panel administracyjny.
    -   **Wyjście:** Prawdopodobnie zawiera wbudowany kod JavaScript lub zmienne konfiguracyjne potrzebne przez interfejs Panelu administracyjnego, być może dla wywołań AJAX lub dynamicznych elementów interfejsu użytkownika.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Opis modułu i spis plików nie wymieniają jawnie plików SQL do tworzenia niestandardowych tabel. Jednak na podstawie kontrolerów administracyjnych, moduł prawdopodobnie wchodzi w interakcje z następującymi (albo niestandardowymi tabelami, albo `ps_configuration` dla ustawień):

-   `ps_configuration`: Przechowuje wszystkie ustawienia modułu (np. `OREMINDERS_ENABLED`, `OREMINDERS_CRON_URL`, `OREMINDERS_UNSUB_LINK`, `OREMINDERS_STATUSES_REMIND`, `OREMINDERS_STATUSES_STOP` oraz serializowane dane dla poszczególnych reguł przypomnień).
-   `ps_or` (lub podobne, zarządzane przez `AdminOrderRemindersController`): Prawdopodobnie niestandardowa tabela do przechowywania informacji o zamówieniach, dla których obecnie wysyłane są przypomnienia, lub do oznaczania zamówień jako wykluczonych.
-   `ps_or_history` (lub podobne, zarządzane przez `AdminOrderRemindersHistoryController`): Niestandardowa tabela do logowania każdego wysłanego e-maila z przypomnieniem, w tym `id_order`, `id_customer`, `email`, `id_reminder_rule`, `date_sent`.
-   `ps_or_ounsub` (lub podobne, zarządzane przez `AdminOrderRemindersUnsubController`): Niestandardowa tabela do przechowywania identyfikatorów klientów lub adresów e-mail tych, którzy zrezygnowali z przypomnień.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | W sekcji `<head>` wszystkich stron front-office. | Do dołączania specyficznych dla modułu plików CSS/JS dla komponentów front-office (np. strony rezygnacji z subskrypcji). |
| `displayAdminModuleConfigure` | Back-Office | Podczas przeglądania głównej strony konfiguracji modułu. | Do renderowania głównego formularza konfiguracji modułu (metoda `getContent()`). |
| `actionValidateOrder` | Back-Office | Po pomyślnym zatwierdzeniu zamówienia. | Potencjalnie używany do inicjowania śledzenia przypomnień dla nowych zamówień, chociaż zadanie cron jest głównym wyzwalaczem. |
| `actionOrderStatusUpdate` | Back-Office | Gdy status zamówienia zostanie zmieniony. | Do sprawdzenia, czy nowy status zamówienia powinien zatrzymać przypomnienia (np. jeśli zmieni się na „Płatność zaakceptowana”). |
| `actionCronJob` | Back-Office (przez kontroler Front) | Wykonywany przez zadanie cron serwera. | Główny hook, który wyzwala logikę modułu do znajdowania niezapłaconych zamówień i wysyłania przypomnień. |
| (Implicit Hooks for Admin Tabs) | Back-Office | Podczas renderowania menu Panelu administracyjnego. | Do dodawania niestandardowych pozycji menu modułu (Przypomnienia o zamówieniach, Historia, Klienci, którzy zrezygnowali z subskrypcji). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Przypomnienie o niezapłaconym zamówieniu”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
