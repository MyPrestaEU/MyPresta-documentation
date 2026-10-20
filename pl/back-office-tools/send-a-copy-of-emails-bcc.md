---
title: "Wyślij kopię e-maili (UDW) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Wyślij kopię e-maili (UDW)” od MyPresta.eu."
sidebar:
  label: "Wyślij kopię e-maili (UDW)"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Send a copy of emails (BCC) na MyPresta.eu](https://mypresta.eu/modules/administration-tools/send-a-copy-of-emails-bcc.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/send-a-copy-of-emails-bcc/)
>
> ---


# Wyślij kopię e-maili (UDW)

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu.

#### **Aktualizacje MyPresta.eu i sprawdzanie wersji**
Na górze strony konfiguracji zazwyczaj zobaczysz ustawienia związane z aktualizacjami MyPresta.eu. Są to standardowe ustawienia dla modułów MyPresta.eu i pomagają utrzymać moduł w aktualności.

-   **Co robi to ustawienie:** Te pola (często oznaczone jako `mypresta_updates`, `update_`, `updatev_`) są używane przez moduł do sprawdzania dostępności nowych wersji z MyPresta.eu i informowania Cię, czy aktualizacja jest potrzebna. Zazwyczaj są one wstępnie wypełnione lub zarządzane automatycznie.
-   **Efekt zmiany tego ustawienia:**
    -   *Jeśli włączone/aktywne:* Moduł może okresowo sprawdzać dostępność aktualizacji, powiadamiając Cię w panelu administracyjnym PrestaShop, jeśli dostępna jest nowa wersja.
    -   *Jeśli wyłączone/nieaktywne:* Możesz nie otrzymywać automatycznych powiadomień o aktualizacjach modułu, co wymaga ręcznego sprawdzania.
-   **Zalecana wartość:** Pozostaw te ustawienia tak, jak są, zazwyczaj włączone lub zarządzane automatycznie, aby mieć pewność, że zawsze jesteś informowany o najnowszych wersjach modułu i poprawkach bezpieczeństwa.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz być powiadamiany, gdy zostanie wydana nowa wersja modułu, która zawiera nowe funkcje lub poprawki błędów, dlatego utrzymujesz te sprawdzenia aktualizacji aktywne.

#### **Główne ustawienia modułu**
Poniżej ustawień aktualizacji znajdziesz podstawowe opcje konfiguracji funkcji e-mail UDW.

-   **Adres e-mail dla UDW:**
    -   **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Definiuje adres e-mail, na który będą wysyłane wszystkie wybrane kopie UDW.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu prawidłowego adresu e-mail:* Wszystkie e-maile wybrane na poniższej liście będą miały ukrytą kopię wysłaną na ten adres.
        -   *Po pozostawieniu pustego lub ustawieniu nieprawidłowego adresu:* Nie zostaną wysłane żadne kopie UDW, nawet jeśli e-maile są wybrane na liście.
    -   **Zalecana wartość:** Dedykowany adres e-mail do archiwizacji (np. `archive@twojskep.com`, `support@twojskep.com` lub Twój osobisty adres e-mail administratora).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby wszystkie potwierdzenia zamówień były kopiowane do skrzynki odbiorczej Twojego zespołu obsługi klienta, `support@twojskep.com`, więc wprowadzasz ten adres tutaj.

-   **Wybierz e-maile do UDW:**
    -   **Co robi to ustawienie:** Ta sekcja przedstawia listę wszystkich szablonów e-maili (typów e-maili), które może wysyłać Twój sklep PrestaShop. Możesz wybrać, które konkretne typy e-maili chcesz wysyłać jako UDW.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy typ e-maila jest zaznaczony:* Kopia UDW tego konkretnego typu e-maila zostanie wysłana na „Adres e-mail dla UDW” za każdym razem, gdy Twój sklep go wyśle.
        -   *Gdy typ e-maila jest odznaczony:* Nie zostanie wysłana żadna kopia UDW dla tego konkretnego typu e-maila.
    -   **Zalecana wartość:** Wybierz tylko te typy e-maili, które są krytyczne dla Twojego prowadzenia rejestrów lub potrzeb operacyjnych. Nadmierne wysyłanie UDW może zalać skrzynkę odbiorczą. Typowe wybory to:
        -   `order_conf` (Potwierdzenie zamówienia)
        -   `shipped` (Zamówienie wysłane)
        -   `contact_form` (Wysłanie formularza kontaktowego)
        -   `password` (Resetowanie hasła)
        -   `account` (Utworzenie nowego konta)
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz prowadzić rejestr wszystkich nowych zamówień i zapytań klientów. Zaznaczyłbyś `order_conf` i `contact_form` z listy.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### **Zarządzanie UDW poczty (Panel administracyjny > Zaawansowane > UDW poczty)**
Ten moduł tworzy dedykowany element menu w panelu administracyjnym PrestaShop w sekcji „Zaawansowane” (lub podobnej, w zależności od wersji PrestaShop) o nazwie „UDW poczty”. Ten ekran jest zarządzany przez `AdminMailBccController`.

-   **Nazwa ekranu i lokalizacja w menu:** **Zaawansowane > UDW poczty**
-   **Dostępne akcje i ustawienia:** Ten ekran zazwyczaj przedstawia siatkę (listę) wszystkich typów e-maili, które skonfigurowałeś do wysyłania jako UDW, wraz z adresem e-mail UDW. Działa jako interfejs podsumowujący i zarządzający Twoimi ustawieniami UDW.
    -   Możesz zobaczyć kolumny takie jak:
        -   **ID:** Wewnętrzny identyfikator reguły UDW.
        -   **Szablon e-maila:** Nazwa szablonu e-maila (np. `order_conf`).
        -   **E-mail UDW:** Adres e-mail, na który wysyłana jest kopia.
        -   **Włączone:** Przełącznik do szybkiego włączania lub wyłączania UDW dla tego konkretnego typu e-maila.
        -   **Akcje:** Przyciski do edycji lub usuwania reguły UDW (chociaż często główna strona konfiguracji modułu jest używana do masowego wyboru).
-   **Efekt zmian:**
    -   *Włączanie/wyłączanie reguły:* Bezpośrednio kontroluje, czy kopia UDW jest wysyłana dla tego konkretnego typu e-maila.
    -   *Edycja reguły:* Umożliwia zmianę adresu e-mail UDW dla konkretnego typu e-maila (jeśli moduł obsługuje adresy UDW dla poszczególnych e-maili, w przeciwnym razie będzie odzwierciedlać ustawienie globalne).
    -   *Usuwanie reguły:* Usuwa ustawienie UDW dla tego typu e-maila.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu, aby szybko sprawdzić, które e-maile są wysyłane jako UDW i dokonać szybkich zmian włączania/wyłączania bez powrotu do głównej konfiguracji modułu. Aby dodać nowe typy e-maili lub zmienić główny adres UDW, strona konfiguracji głównego modułu jest zazwyczaj bardziej efektywna.

#### **index.php (bccmail/controllers/admin/index.php)**
Ten plik jest standardową praktyką PrestaShop w celu zabezpieczania katalogów kontrolerów administracyjnych i zazwyczaj nie przedstawia ekranu użytkownika ani opcji konfiguracji bezpośrednio. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome');` lub podobne, aby przekierować nieautoryzowany dostęp, zapobiegając bezpośredniemu przeglądaniu katalogu. Sprzedawcy nie będą wchodzić w interakcje z tym plikiem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| **Strona konfiguracji modułu** | Aktualizacje MyPresta.eu | Włączone | Informuje o aktualizacjach modułu. |
| | **Adres e-mail dla UDW** | Twój e-mail administratora / `archive@twojskep.com` | Docelowy adres e-mail dla wszystkich kopii UDW. Kluczowy dla archiwizacji. |
| | **Wybierz e-maile do UDW** | `order_conf`, `contact_form`, `shipped` | Wybierz, które konkretne typy e-maili mają być kopiowane. Zapobiega zalewaniu skrzynki odbiorczej. |
| **Zaawansowane > UDW poczty** | Lista szablonów e-maili | Zależy od wyboru | Przegląd i szybkie przełączanie dla skonfigurowanych typów e-maili UDW. |
| | Przełącznik Włączone | Włączone | Szybko aktywuj/dezaktywuj UDW dla konkretnego typu e-maila. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale nie otrzymuję żadnych e-maili UDW. Co powinienem sprawdzić?**
O:
1.  **Sprawdź ponownie adres e-mail UDW:** Przejdź do **Moduły > Menedżer modułów > Konfiguruj** dla „Wyślij kopię e-maili (UDW)” i upewnij się, że „Adres e-mail dla UDW” jest poprawnie wpisany i ważny.
2.  **Zweryfikuj wybrane typy e-maili:** Upewnij się, że konkretne typy e-maili, które mają być kopiowane (np. `order_conf`), są faktycznie zaznaczone w konfiguracji modułu.
3.  **Sprawdź folder spamu:** E-maile UDW mogą trafiać do folderu spamu lub śmieci w skrzynce odbiorczej odbiorcy UDW.
4.  **Ustawienia e-mail PrestaShop:** Upewnij się, że ogólne ustawienia e-mail Twojego sklepu PrestaShop (**Zaawansowane > E-mail**) są poprawnie skonfigurowane i że Twój sklep może ogólnie wysyłać e-maile. Przetestuj, wysyłając testowy e-mail z PrestaShop.
5.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe wprowadzenie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).

**P: Czy mogę wysyłać kopie UDW na wiele adresów e-mail?**
O: Podstawowa konfiguracja modułu pozwala na jeden główny adres e-mail UDW. Jeśli potrzebujesz wysyłać kopie na wiele adresów, masz dwie opcje:
1.  Ustaw adres e-mail UDW na listę dystrybucyjną lub grupowy adres e-mail, który przekazuje wiadomości do wielu odbiorców.
2.  Skonfiguruj regułę e-mail w skrzynce odbiorczej odbiorcy UDW, aby automatycznie przekazywać kopie na inne adresy na podstawie nadawcy lub tematu.

**P: Czy ten moduł spowolni mój sklep lub wysyłanie e-maili?**
O: Wpływ na wydajność jest zazwyczaj znikomy. Wysyłanie dodatkowej kopii UDW to bardzo niewielka operacja dla serwera pocztowego. Moduł wykorzystuje standardowy mechanizm wysyłania e-maili PrestaShop, po prostu dodając dodatkowego odbiorcę.

**P: Mój niestandardowy motyw ma niestandardowe szablony e-maili. Czy ten moduł nadal będzie działać?**
O: Tak, moduł integruje się z podstawową klasą `Mail` PrestaShop, która jest odpowiedzialna za wysyłanie wszystkich e-maili, niezależnie od tego, czy używają one domyślnych, czy niestandardowych szablonów. Dopóki PrestaShop wysyła e-mail, ten moduł może go wysyłać jako UDW.

**P: Jak przetłumaczyć interfejs modułu na inny język?**
O: Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Wyślij kopię e-maili (UDW)”. Następnie możesz przetłumaczyć dowolne ciągi znaków wyświetlane przez moduł w panelu administracyjnym.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowe informacje na temat technicznej implementacji modułu „Wyślij kopię e-maili (UDW)” dla deweloperów i webmasterów.

### 4.1 Przegląd architektury
Moduł „Wyślij kopię e-maili (UDW)” (`bccmail`) działa głównie poprzez nadpisywanie podstawowej klasy `Mail` PrestaShop. Jest to powszechna i potężna technika w PrestaShop do modyfikowania podstawowego zachowania bez bezpośredniej edycji plików rdzenia. Nadpisując `Mail.php`, moduł przechwytuje wszystkie operacje wysyłania e-maili i wstrzykuje funkcjonalność UDW na podstawie swojej konfiguracji. Moduł ten ma standardową strukturę modułu PrestaShop z głównym plikiem modułu, kontrolerami administracyjnymi do konfiguracji i klasą nadpisywania.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery front-office**: Ten moduł nie ma żadnych dedykowanych kontrolerów front-office, ponieważ jego funkcjonalność jest całkowicie związana z back-office i po stronie serwera.

-   **Kontrolery administracyjne back-office**:
    *   `bccmail/controllers/admin/AdminMailBcc.php`
        *   **Nazwa klasy i klasa nadrzędna:** `AdminMailBccController` rozszerza `ModuleAdminController`.
        *   **Nazwa zakładki i zarządzana encja:** Ten kontroler zarządza zakładką „UDW poczty” w sekcji „Zaawansowane”. Jest odpowiedzialny za wyświetlanie i zarządzanie listą skonfigurowanych typów e-maili UDW. Prawdopodobnie używa `HelperList` lub `HelperView` PrestaShop do renderowania siatki obiektów `MailBcc` (lub reprezentacji konfiguracji modułu).
        *   **Odpowiedzialność:** Obsługuje wyświetlanie podsumowania konfiguracji UDW, potencjalnie umożliwiając indywidualną aktywację/dezaktywację lub usunięcie reguły. Współdziała z danymi konfiguracyjnymi modułu (prawdopodobnie przechowywanymi w `ps_configuration` lub niestandardowej tabeli, jeśli potrzebne są bardziej złożone dane dla każdej reguły UDW).
    *   `bccmail/controllers/admin/index.php`
        *   **Nazwa klasy i klasa nadrzędna:** Nie jest klasą, ale plikiem bezpieczeństwa.
        *   **Odpowiedzialność:** Ten plik jest standardowym środkiem bezpieczeństwa PrestaShop. Zazwyczaj zawiera `header('Location: ../../index.php?controller=AdminHome');` lub podobne, aby zapobiec bezpośredniemu listowaniu katalogów i nieautoryzowanemu dostępowi do katalogu `controllers/admin`. Nie dostarcza żadnej funkcjonalnej logiki dla samego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `bccmail/override/classes/Mail.php`
    *   **Z jaką tabelą bazy danych współdziała:** Pośrednio współdziała z `ps_configuration` w celu pobrania ustawień modułu (adres e-mail UDW i wybrane szablony e-maili).
    *   **Czy rozszerza `ObjectModel`:** Nie, nadpisuje podstawową klasę `Mail`.
    *   **Kluczowe metody publiczne i hermetyzowana logika biznesowa:**
        *   Ten plik zawiera podstawową logikę przechwytywania wysyłania e-maili. Nadpisuje metodę `send()` (lub podobną metodę) oryginalnej klasy `Mail`.
        *   Wewnątrz nadpisanej metody `send()` będzie:
            1.  Pobierać konfigurację modułu: globalny adres e-mail UDW i listę szablonów e-maili wybranych do UDW.
            2.  Sprawdzać, czy aktualnie wysyłany e-mail (identyfikowany przez nazwę szablonu, np. `order_conf`) znajduje się na liście wybranych szablonów UDW.
            3.  Jeśli znaleziono dopasowanie, modyfikuje nagłówki lub parametry e-maila, aby uwzględnić skonfigurowany adres e-mail UDW przed wywołaniem metody nadrzędnej `Mail::send()` w celu wysłania e-maila.
        *   Zapewnia to dodanie odbiorcy UDW do listy ukrytych kopii e-maila, czyniąc go niewidocznym dla głównych odbiorców.

-   `bccmail/override/classes/index.php`
    *   **Odpowiedzialność:** Podobnie jak `controllers/admin/index.php`, jest to plik bezpieczeństwa, który zapobiega bezpośredniemu listowaniu katalogu `override/classes`. Zazwyczaj zawiera pusty tag PHP lub przekierowanie.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `bccmail/views/templates/admin/js/bccmail.js`
    *   **Zakres:** Back-office.
    *   **Jakie nasłuchiwacze zdarzeń wiąże:** Ten skrypt jest prawdopodobnie używany na stronie konfiguracji modułu lub na ekranie `AdminMailBccController`. Może wiązać nasłuchiwacze dla:
        *   Zdarzeń przesyłania formularzy w celu obsługi zapisywania konfiguracji.
        *   Zmian pól wyboru do wybierania szablonów e-maili do UDW.
        *   Walidacji pól wejściowych dla adresu e-mail UDW.
        *   Wywołań AJAX w celu dynamicznej aktualizacji ustawień bez pełnego przeładowania strony.
    *   **Jakie manipulacje DOM, wyskakujące okienka modalne, animacje lub wywołania zewnętrznych SDK stron trzecich wykonuje:** Może wykonywać proste manipulacje DOM, takie jak pokazywanie/ukrywanie elementów na podstawie wyborów, wyświetlanie komunikatów o sukcesie/błędzie lub podstawową walidację formularzy. Jest mało prawdopodobne, aby obejmował złożone animacje lub SDK stron trzecich dla funkcjonalności tego modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)
Moduł nie wydaje się zawierać żadnych niestandardowych plików CSS w swoim archiwum. Prawdopodobnie opiera się na domyślnych stylach back-office PrestaShop dla swoich formularzy konfiguracyjnych i list, lub stylach wbudowanych, jeśli jest to absolutnie konieczne.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Żadne nie są wyraźnie wymienione, ale główny formularz konfiguracyjny modułu (`getContent()`) renderowałby swoje ustawienia za pomocą szablonu Smarty, zazwyczaj znajdującego się w `views/templates/admin/configure.tpl` lub podobnym, nawet jeśli nie jest wyraźnie wymieniony w inwentarzu jako oddzielny plik.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `bccmail/lib/searchTool/views/scripts.tpl`
        *   **Cel:** Ten szablon jest prawdopodobnie częścią biblioteki pomocniczej lub narzędziowej w module (np. narzędzia wyszukiwania szablonów e-maili). Zawierałby logikę JavaScript lub Smarty do renderowania pól wyszukiwania, filtrowania list lub obsługi dynamicznego ładowania treści w interfejsie administracyjnym. Nie jest to samodzielna strona, ale komponent.
-   **Szablony front-office (`views/templates/front/`)**: Brak. Moduł nie ma obecności w front-office.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł przechowuje swoją konfigurację głównie w tabeli `ps_configuration` PrestaShop.
        *   Klucze `PS_CONFIGURATION` obejmowałyby:
            *   `BCCMAIL_EMAIL_ADDRESS`: Przechowuje główny adres e-mail dla UDW.
            *   `BCCMAIL_SELECTED_TEMPLATES`: Przechowuje serializowaną tablicę lub ciąg znaków oddzielonych przecinkami nazw szablonów e-maili wybranych do UDW.
            *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Do sprawdzania aktualizacji modułu.
    *   Na podstawie dostarczonego inwentarza ten moduł nie tworzy żadnych niestandardowych tabel SQL.

-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje żadnych standardowych hooków wyświetlania (takich jak `displayHeader`, `displayRightColumn`, `displayFooter`), ponieważ nie ma obecności w front-office. Jego podstawowa funkcjonalność opiera się na nadpisywaniu klasy `Mail`, a nie na używaniu tradycyjnych hooków PrestaShop do wysyłania e-maili.

    Jednakże, niejawnie „integruje się” z procesem wysyłania e-maili poprzez swoje nadpisanie.
    *   **`actionEmailSend` (Niejawne poprzez nadpisanie)**: Chociaż nie jest to formalnie zarejestrowany hook, `override/classes/Mail.php` modułu skutecznie przechwytuje metodę `Mail::send()`, która jest podstawową akcją wysyłania e-maila. To tutaj wstrzykiwana jest logika UDW.
        *   **Czas wykonania:** Za każdym razem, gdy `Mail::send()` jest wywoływane przez PrestaShop (np. przy potwierdzeniu zamówienia, rejestracji klienta, przesłaniu formularza kontaktowego).
        *   **Cel techniczny:** Dodanie skonfigurowanego odbiorcy UDW do e-maila przed jego wysłaniem przez program pocztowy PrestaShop.

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje modułu, wsparcie techniczne i dodatkowe zasoby, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Wyślij kopię e-maili (UDW)”.
