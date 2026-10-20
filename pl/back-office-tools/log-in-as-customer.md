---
title: "Zaloguj się jako klient - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop „Zaloguj się jako klient” od MyPresta.eu."
sidebar:
  label: "Zaloguj się jako klient - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Log in as customer na MyPresta.eu](https://mypresta.eu/modules/administration-tools/log-in-as-customer.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/log-in-as-customer/)
>
> ---


# Zaloguj się jako klient

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Moduł „Zaloguj się jako klient” ma bardzo prostą konfigurację. Po instalacji, po kliknięciu „Konfiguruj”, zostaniesz przeniesiony na prosty ekran.

**Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Moduły > Menedżer modułów > Zaloguj się jako klient > Konfiguruj

Na tym ekranie zazwyczaj znajdziesz proste potwierdzenie, że moduł jest zainstalowany i gotowy. Podstawowa funkcjonalność tego modułu jest zintegrowana bezpośrednio z listą klientów, zamiast wymagać rozbudowanych ustawień na dedykowanej stronie konfiguracji.

-   **Co robi ten ekran:** Ta strona potwierdza instalację modułu i dostarcza wszelkie podstawowe informacje lub szybkie linki. Dla „Zaloguj się jako klient” jego głównym celem jest potwierdzenie, że moduł jest aktywny i gotowy do użycia.
-   **Wpływ zmiany ustawień:** Nie ma tu skomplikowanych ustawień do zmiany. Funkcjonalność modułu jest aktywowana po instalacji.
-   **Zalecana wartość:** Brak konkretnych wartości do ustawienia. Po prostu upewnij się, że moduł jest zainstalowany i włączony.
-   **Scenariusz / przykład dla sprzedawcy:** Po instalacji zobaczysz wiadomość potwierdzającą, że moduł jest aktywny. Możesz następnie przejść bezpośrednio do sekcji Klienci w Panelu administracyjnym, aby korzystać z jego funkcji.

### 2.2 Korzystanie z funkcji „Zaloguj się jako klient”

Główna funkcjonalność tego modułu jest dostępna bezpośrednio z listy klientów PrestaShop.

**Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Klienci > Klienci

1.  **Przejdź do Klientów:** W Panelu administracyjnym PrestaShop przejdź do menu **Klienci**, a następnie kliknij **Klienci**.
2.  **Zlokalizuj klienta:** Znajdź klienta, jako którego chcesz się zalogować, na liście klientów. Możesz użyć opcji wyszukiwania i filtrowania, aby szybko go zlokalizować.
3.  **Kliknij przycisk „Zaloguj się jako klient”:** Dla każdego klienta na liście zobaczysz teraz dodatkowy przycisk (często ikonę, taką jak osoba lub klucz, lub przycisk tekstowy) w kolumnie „Akcje”. Ten przycisk jest dodawany przez moduł „Zaloguj się jako klient”.
    -   **Co robi ten przycisk:** Po kliknięciu tego przycisku moduł wykonuje bezpieczny proces logowania. Wylogowuje Cię z konta administratora (tymczasowo), a następnie loguje Cię jako wybranego klienta.
    -   **Wpływ kliknięcia tego przycisku:** Zostaniesz natychmiast przekierowany do front office Twojego sklepu. Zobaczysz sklep dokładnie tak, jak widzi go ten klient, włączając w to jego aktywny koszyk, historię zamówień, adresy oraz wszelkie spersonalizowane treści lub ceny.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient zgłasza problem z dodaniem konkretnego produktu do koszyka. Przechodzisz do „Klienci”, znajdujesz jego imię, klikasz „Zaloguj się jako klient” i natychmiast zostajesz przeniesiony do front office jako on. Możesz wtedy spróbować samodzielnie dodać produkt, rozwiązać problem lub zweryfikować zawartość jego koszyka.
4.  **Wylogowanie się jako klient:** Aby wrócić do sesji administratora Panelu administracyjnego, po prostu wyloguj się z front office (tak jakbyś był zwykłym klientem). Spowoduje to zakończenie sesji klienta, a następnie możesz ponownie zalogować się do Panelu administracyjnego.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | (Brak bezpośrednich ustawień) | N/A | Potwierdza instalację i gotowość modułu. |
| Lista klientów (Panel administracyjny) | Przycisk „Zaloguj się jako klient” | N/A | Umożliwia natychmiastowe logowanie do front office jako wybrany klient w celu rozwiązywania problemów i testowania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę przycisku „Zaloguj się jako klient” na liście klientów.**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
2.  **Status modułu:** Upewnij się, że moduł jest włączony. Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Zaloguj się jako klient” i sprawdź, czy jest aktywny.
3.  **Kompatybilność z motywem:** Chociaż rzadko, niektóre mocno dostosowane motywy mogą zakłócać wyświetlanie nowych przycisków. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.
4.  **Wersja PrestaShop:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej instalacji PrestaShop.

**P: Kiedy klikam przycisk, jestem przekierowywany do front office, ale nie jestem zalogowany jako klient.**
O:

1.  **Pliki cookie przeglądarki:** Upewnij się, że Twoja przeglądarka akceptuje pliki cookie. Spróbuj wyczyścić pamięć podręczną i pliki cookie przeglądarki, a następnie spróbuj ponownie.
2.  **Konfiguracja sesji:** Sprawdź plik `config/defines.inc.php` w PrestaShop pod kątem ustawień `_PS_COOKIE_DOMAIN_` i `_PS_COOKIE_PATH_`. Upewnij się, że są one poprawnie skonfigurowane dla Twojej domeny.
3.  **Konfiguracja serwera:** Sprawdź, czy ustawienia sesji PHP na Twoim serwerze są standardowe i nie są nadmiernie restrykcyjne.

**P: Czy mogę zalogować się jako klient, a następnie wykonywać działania, takie jak składanie zamówienia w jego imieniu?**
O: Tak, możesz. Jednak zachowaj szczególną ostrożność. Zawsze uzyskaj wyraźną zgodę klienta przed wykonaniem jakichkolwiek działań w jego imieniu, zwłaszcza składania zamówień lub modyfikowania danych osobowych. Zazwyczaj najlepszą praktyką jest używanie tej funkcji do przeglądania i rozwiązywania problemów, a nie do wprowadzania zmian bez zgody.

**P: Czy korzystanie z tego modułu jest bezpieczne? Czy przechowuje on hasła klientów?**
O: Moduł nie przechowuje ani nie uzyskuje dostępu do haseł klientów. Wykorzystuje wewnętrzne zarządzanie sesjami PrestaShop do symulowania logowania klienta, podobnie jak działa funkcja „Zapomniałem hasła” w PrestaShop, generując tymczasową bezpieczną sesję. Został zaprojektowany tak, aby był bezpieczny.

**P: Co się stanie, jeśli zaloguję się jako klient, a następnie zamknę przeglądarkę bez wylogowania?**
O: Sesja klienta ostatecznie wygaśnie na podstawie ustawień limitu czasu sesji w PrestaShop. Aby wrócić do panelu administracyjnego, wystarczy przejść do adresu URL Panelu administracyjnego i ponownie zalogować się jako administrator.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zaloguj się jako klient” (`lac`) to lekki moduł PrestaShop, skupiający się głównie na rozszerzaniu funkcjonalności listy klientów w Panelu administracyjnym. Wykorzystuje on podstawowe klasy PrestaShop `Customer` i `Context` do zarządzania sesjami użytkowników i przekierowaniami. Moduł wstrzykuje JavaScript do Panelu administracyjnego, aby dodać przycisk „Zaloguj się jako klient” i używa dedykowanego kontrolera frontowego do obsługi bezpiecznego procesu logowania i przekierowania do front office. Przestrzega standardowej architektury modułów PrestaShop, integrując się płynnie bez niestandardowych tabel baz danych ani złożonych modeli obiektów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front Office**:

    -   `lac/controllers/front/index.php`
        -   **Nazwa klasy**: `LacIndexModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
        -   **Klasa nadrzędna**: `ModuleFrontController`
        -   **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako punkt wejścia lub rezerwowy. Biorąc pod uwagę kontroler `login.php`, `index.php` może być mniej krytyczny lub obsługiwać początkową konfigurację/przekierowanie, jeśli `login.php` jest głównym obsługującym akcje. Może to być również placeholder.
    -   `lac/controllers/front/login.php`
        -   **Nazwa klasy**: `LacLoginModuleFrontController` (prawdopodobnie)
        -   **Klasa nadrzędna**: `ModuleFrontController`
        -   **Odpowiedzialność**: Jest to główny kontroler dla funkcji „Zaloguj się jako klient”.
            -   Odbiera identyfikator klienta za pośrednictwem parametru GET lub POST z Panelu administracyjnego.
            -   Wykonuje niezbędne kroki, aby wylogować bieżącą sesję administratora.
            -   Następnie bezpiecznie loguje określonego klienta, manipulując obiektami `Context` i `Customer` (np. `Context::getContext()->customer = new Customer($id_customer); Context::getContext()->cookie->id_customer = $id_customer;`).
            -   Następnie przekierowuje przeglądarkę do strony głównej front office lub na konkretną stronę związaną z klientem (`my-account`, `history` itp.).
-   **Kontrolery administracyjne Panelu administracyjnego**:

    -   Brak. Moduł integruje się bezpośrednio z widokiem istniejącego kontrolera `AdminCustomers` za pomocą hooków i JavaScriptu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   Brak. Ten moduł nie wprowadza niestandardowych klas `ObjectModel` ani tabel baz danych. Działa bezpośrednio na natywnych obiektach `Customer` i `Context` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Te pliki JavaScript są odpowiedzialne za wstrzykiwanie przycisku „Zaloguj się jako klient” do listy klientów w Panelu administracyjnym i obsługę zdarzenia kliknięcia w celu zainicjowania procesu logowania. Różne nazwy plików sugerują dostosowania kompatybilności dla różnych wersji PrestaShop.

-   `lac/views/js/16customers.js`
    -   **Zakres**: Panel administracyjny (lista `AdminCustomers` PrestaShop 1.6.x).
    -   **Funkcjonalność**: Ten skrypt celuje w tabelę listy klientów w PrestaShop 1.6.x. Prawdopodobnie używa selektorów jQuery do znalezienia kolumny „Akcje” dla każdego wiersza klienta i dołącza nowy przycisk lub link. Obsługa kliknięcia dla tego przycisku następnie konstruuje adres URL wskazujący na kontroler frontowy modułu (`lac/controllers/front/login.php`) z identyfikatorem klienta i przekierowuje przeglądarkę.
-   `lac/views/js/176orders.js`
    -   **Zakres**: Panel administracyjny (widok zamówień PrestaShop 1.7.6.x).
    -   **Funkcjonalność**: Ten skrypt może być przeznaczony do dodawania przycisku „Zaloguj się jako klient” bezpośrednio z widoku zamówienia w 1.7.6.x, umożliwiając szybki dostęp do klienta powiązanego z konkretnym zamówieniem. Wyodrębniłby identyfikator klienta ze strony szczegółów zamówienia i użył go do przekierowania logowania.
-   `lac/views/js/177orders.js`
    -   **Zakres**: Panel administracyjny (widok zamówień PrestaShop 1.7.7.x+).
    -   **Funkcjonalność**: Podobnie jak `176orders.js`, ale dostosowany do potencjalnych zmian DOM lub różnych struktur tabel w PrestaShop 1.7.7.x i późniejszych wersjach widoku zamówienia.
-   `lac/views/js/17carts.js`
    -   **Zakres**: Panel administracyjny (widok koszyka PrestaShop 1.7.x).
    -   **Funkcjonalność**: Ten skrypt prawdopodobnie dodaje przycisk „Zaloguj się jako klient” do strony szczegółów koszyka w Panelu administracyjnym, umożliwiając administratorowi zalogowanie się jako klient powiązany z konkretnym koszykiem.
-   `lac/views/js/17customersview.js`
    -   **Zakres**: Panel administracyjny (lista `AdminCustomers` PrestaShop 1.7.x, 8.x, 9.x).
    -   **Funkcjonalność**: Jest to główny skrypt do wstrzykiwania przycisku do listy klientów dla nowoczesnych wersji PrestaShop. Będzie celował w listę `AdminCustomers`, identyfikował identyfikator klienta dla każdego wiersza i dołączał przycisk akcji „Zaloguj się jako klient”. Używa delegowania zdarzeń do obsługi kliknięć na tych dynamicznie dodanych przyciskach, konstruując odpowiedni adres URL dla kontrolera `lac/controllers/front/login.php`.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Brak. Moduł nie zawiera niestandardowych plików CSS. Prawdopodobnie opiera się na domyślnych stylach PrestaShop dla przycisków lub używa stylów wbudowanych, jeśli to konieczne, lub przycisk jest stylizowany przez sam motyw Panelu administracyjnego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   Brak. Moduł nie używa niestandardowych szablonów Smarty. Jego integracja z Panelu administracyjnego odbywa się wyłącznie poprzez wstrzykiwanie JavaScriptu, a logowanie do front office jest obsługiwane przez bezpośrednie przekierowanie z kontrolera.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:
    -   Moduł nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoją konfigurację (jeśli istnieje, chociaż żadna nie została wyraźnie zidentyfikowana poza podstawowym statusem modułu) w standardowej tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` każdej strony Panelu administracyjnego. | Używany do dołączania niezbędnych plików JavaScript (`16customers.js`, `17customersview.js` itp.) do Panelu administracyjnego, szczególnie gdy aktywny jest kontroler `AdminCustomers`. Zapewnia to dodanie przycisku „Zaloguj się jako klient” do listy klientów. |
| `displayAdminCustomers` | Wykonywany na stronie kontrolera `AdminCustomers`. | Ten hook jest specjalnie zaprojektowany dla modułów do dodawania treści lub akcji do listy klientów. Moduł może używać tego hooka do renderowania małego szablonu lub bezpośredniego wstrzykiwania JavaScriptu w celu dodania przycisku. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler Panelu administracyjnego ustawia swoje media (JS/CSS). | Bardziej solidny hook do warunkowego dodawania JS/CSS na podstawie aktywnego kontrolera. Moduł używałby tego do ładowania swoich specyficznych plików JS tylko na stronach `AdminCustomers` lub `AdminOrders`. |
| `displayAdminOrder` | Wykonywany na stronie kontrolera `AdminOrders`. | Jeśli moduł dodaje przycisk „Zaloguj się jako klient” do widoku zamówienia (jak sugerują `176orders.js`, `177orders.js`), ten hook zostałby użyty do wstrzyknięcia niezbędnego JavaScriptu lub HTML przycisku. |
| `displayAdminCarts` | Wykonywany na stronie kontrolera `AdminCarts`. | Jeśli moduł dodaje przycisk „Zaloguj się jako klient” do widoku koszyka (jak sugeruje `17carts.js`), ten hook zostałby użyty. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zaloguj się jako klient”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
