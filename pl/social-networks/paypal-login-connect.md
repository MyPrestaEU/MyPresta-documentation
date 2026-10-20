---
title: "PayPal login connect - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „PayPal login connect” od MyPresta.eu."
sidebar:
  label: "PayPal login connect - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł PayPal login connect na MyPresta.eu](https://mypresta.eu/modules/social-networks/paypal-login-connect.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/paypal-login-connect/)
>
> ---


# PayPal login connect

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „PayPal login connect”, aby uzyskać dostęp do jego ustawień.

#### **Dane uwierzytelniające API PayPal**

Te ustawienia łączą Twój sklep z Twoim kontem deweloperskim PayPal, umożliwiając modułowi bezpieczne uwierzytelnianie użytkowników.

-   **Co robi to ustawienie:** Te pola wymagają Twojego unikalnego identyfikatora klienta (Client ID) i tajnego klucza klienta (Client Secret) uzyskanych z Twojego konta deweloperskiego PayPal. Te dane uwierzytelniające są kluczowe dla komunikacji Twojego sklepu z usługą logowania PayPal.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po poprawnym wprowadzeniu:* Przycisk „Zaloguj się z PayPal” będzie działał, umożliwiając klientom logowanie.
    -   *Gdy są niepoprawne lub puste:* Moduł nie będzie mógł połączyć się z PayPal, a funkcja logowania zakończy się niepowodzeniem lub nie pojawi się.
-   **Zalecana wartość:** Wprowadź dokładny identyfikator klienta (Client ID) i tajny klucz klienta (Client Secret) dostarczone przez PayPal.
-   **Scenariusz/przykład dla sprzedawcy:** Utworzyłeś konto deweloperskie PayPal i skonfigurowałeś aplikację „Zaloguj się z PayPal”. PayPal dostarcza Ci identyfikator klienta (długi ciąg znaków) i tajny klucz klienta (inny długi, bezpieczny ciąg). Kopiujesz i wklejasz je w odpowiednie pola tutaj.

#### **Włącz logowanie PayPal**

To jest główny przełącznik funkcjonalności modułu.

-   **Co robi to ustawienie:** Kontroluje, czy funkcja „Zaloguj się z PayPal” jest aktywna i widoczna w Twoim sklepie.
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy włączone (TAK):* Przyciski logowania PayPal pojawią się w wybranych miejscach, a funkcjonalność będzie aktywna.
    -   *Gdy wyłączone (NIE):* Przyciski logowania PayPal zostaną ukryte, a klienci nie będą mogli korzystać z tej funkcji.
-   **Zalecana wartość:** TAK
-   **Scenariusz/przykład dla sprzedawcy:** Zakończyłeś konfigurację modułu i chcesz go uruchomić dla swoich klientów. Ustawiasz to na TAK. Jeśli musisz tymczasowo wyłączyć go do konserwacji, możesz ustawić to na NIE.

#### **Wyświetl przycisk w**

Ta sekcja pozwala wybrać, gdzie przycisk „Zaloguj się z PayPal” będzie się pojawiał w Twoim sklepie.

-   **Co robi to ustawienie:** Określa konkretne miejsca (hooki), w których przycisk logowania PayPal zostanie wyświetlony w Twoim front office.
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy lokalizacja jest zaznaczona:* Przycisk logowania PayPal pojawi się w tym konkretnym obszarze Twojego sklepu.
    -   *Gdy lokalizacja jest odznaczona:* Przycisk nie zostanie wyświetlony w tym obszarze.
-   **Zalecana wartość:** Wybierz lokalizacje, które są najbardziej odpowiednie dla logowania/rejestracji klienta, takie jak `displayNav` (górna nawigacja), `displayCustomerLoginFormAfter` (po standardowym formularzu logowania) i `createAccountForm` (na stronie rejestracji).
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby przycisk był łatwo dostępny w nagłówku i na głównej stronie logowania. Zaznaczyłbyś `displayNav` i `displayCustomerLoginFormAfter`. Jeśli Twój motyw ma niestandardowe wyskakujące okienko logowania, możesz również zaznaczyć `displayPopUpLogin`.

#### **Styl przycisku**

Dostosuj wygląd wizualny przycisku logowania PayPal.

-   **Co robi to ustawienie:** Pozwala wybrać spośród różnych predefiniowanych stylów dla przycisku „Zaloguj się z PayPal”, aby dopasować go do projektu Twojego sklepu lub wytycznych marki PayPal.
-   **Wpływ zmiany tego ustawienia:** Zmienia wygląd wizualny (np. kolor, rozmiar, tekst) przycisków logowania PayPal w całym Twoim sklepie.
-   **Zalecana wartość:** Wybierz styl, który najlepiej integruje się z projektem Twojego sklepu, jednocześnie pozostając wyraźnie identyfikowalnym jako przycisk PayPal.
-   **Scenariusz/przykład dla sprzedawcy:** Twój sklep używa ciemnego motywu, więc możesz wybrać biały przycisk PayPal z ciemnym tekstem dla lepszego kontrastu. Lub możesz preferować standardowy niebieski przycisk PayPal dla maksymalnego rozpoznania marki.

#### **Adres URL przekierowania po zalogowaniu**

Określ, dokąd klienci są wysyłani po pomyślnym zalogowaniu się za pomocą PayPal.

-   **Co robi to ustawienie:** Definiuje stronę, na którą klient jest przekierowywany natychmiast po pomyślnym uwierzytelnieniu za pomocą PayPal i powrocie do Twojego sklepu.
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy ustawione na „Moje konto”:* Klienci lądują na swoim osobistym panelu konta.
    -   *Gdy ustawione na „Strona główna”:* Klienci są przekierowywani z powrotem na główną stronę Twojego sklepu.
    -   *Gdy ustawione na „Poprzednia strona”:* Klienci są zwracani na stronę, na której byli przed zainicjowaniem logowania.
-   **Zalecana wartość:** „Poprzednia strona” lub „Moje konto” dla płynnego doświadczenia. „Poprzednia strona” jest często preferowana podczas realizacji zamówienia.
-   **Scenariusz/przykład dla sprzedawcy:** Klient jest na stronie produktu i klika „Zaloguj się z PayPal”. Jeśli wybrano „Poprzednia strona”, wróci na tę stronę produktu. Jeśli był w procesie realizacji zamówienia, wróci do kroku realizacji zamówienia.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator klienta PayPal | (Puste) / Twój identyfikator klienta PayPal | Unikalny identyfikator Twojej aplikacji PayPal. **Wymagane do działania modułu.** |
| Konfiguracja modułu | Tajny klucz klienta PayPal | (Puste) / Twój tajny klucz klienta PayPal | Tajny klucz dla Twojej aplikacji PayPal. **Wymagane do działania modułu.** |
| Konfiguracja modułu | Włącz logowanie PayPal | TAK | Główny przełącznik do aktywacji/dezaktywacji funkcji logowania PayPal. |
| Konfiguracja modułu | Wyświetl przycisk w: displayNav | TAK | Pokazuje przycisk w głównym pasku nawigacji. |
| Konfiguracja modułu | Wyświetl przycisk w: displayCustomerLoginFormAfter | TAK | Pokazuje przycisk po standardowym formularzu logowania. |
| Konfiguracja modułu | Wyświetl przycisk w: createAccountForm | TAK | Pokazuje przycisk na stronie rejestracji klienta. |
| Konfiguracja modułu | Wyświetl przycisk w: displayFooter | NIE | Pokazuje przycisk w stopce sklepu. |
| Konfiguracja modułu | Wyświetl przycisk w: displayHome | NIE | Pokazuje przycisk na stronie głównej. |
| Konfiguracja modułu | Wyświetl przycisk w: displayLeftColumn | NIE | Pokazuje przycisk w lewej kolumnie. |
| Konfiguracja modułu | Wyświetl przycisk w: displayNav1 | NIE | Pokazuje przycisk w alternatywnym hooku nawigacji (zależne od motywu). |
| Konfiguracja modułu | Wyświetl przycisk w: displayNav2 | NIE | Pokazuje przycisk w innym alternatywnym hooku nawigacji (zależne od motywu). |
| Konfiguracja modułu | Wyświetl przycisk w: displayPopUpLogin | TAK | Pokazuje przycisk w wyskakujących formularzach logowania (jeśli Twój motyw ich używa). |
| Konfiguracja modułu | Wyświetl przycisk w: displayRightColumn | NIE | Pokazuje przycisk w prawej kolumnie. |
| Konfiguracja modułu | Wyświetl przycisk w: displayTop | NIE | Pokazuje przycisk w bardzo górnej sekcji strony (zależne od motywu). |
| Konfiguracja modułu | Wyświetl przycisk w: header | NIE | Pokazuje przycisk w sekcji HTML `<head>` (rzadziej dla widocznych przycisków). |
| Konfiguracja modułu | Wyświetl przycisk w: shoppingCart | NIE | Pokazuje przycisk w podsumowaniu koszyka. |
| Konfiguracja modułu | Wyświetl przycisk w: shoppingCartExtra | NIE | Pokazuje przycisk w dodatkowej sekcji koszyka (zależne od motywu). |
| Konfiguracja modułu | Styl przycisku | (Domyślny styl PayPal) | Wygląd wizualny przycisku logowania PayPal. |
| Konfiguracja modułu | Adres URL przekierowania po zalogowaniu | Poprzednia strona | Strona docelowa po pomyślnym zalogowaniu przez PayPal. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Przycisk logowania PayPal nie wyświetla się w moim sklepie.**
O:

1.  **Sprawdź „Włącz logowanie PayPal”:** Upewnij się, że to ustawienie jest ustawione na TAK w konfiguracji modułu.
2.  **Zweryfikuj ustawienia „Wyświetl przycisk w”:** Upewnij się, że wybrałeś co najmniej jeden hook (np. `displayNav`, `displayCustomerLoginFormAfter`), w którym chcesz, aby przycisk się pojawił.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną PrestaShop (pamięć podręczna Smarty, pamięć podręczna systemu plików). Pamięć podręczna przeglądarki również może wymagać wyczyszczenia.
4.  **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą wymagać drobnych korekt. Jeśli przycisk nadal się nie pojawia, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Kiedy klikam przycisk PayPal, nic się nie dzieje lub otrzymuję błąd.**
O:

1.  **Sprawdź dane uwierzytelniające API:** Dokładnie sprawdź swój identyfikator klienta PayPal (Client ID) i tajny klucz klienta (Client Secret) w konfiguracji modułu. Nawet pojedynczy nieprawidłowy znak uniemożliwi połączenie.
2.  **Konfiguracja aplikacji PayPal:** Upewnij się, że Twoja aplikacja „Zaloguj się z PayPal” na Twoim koncie deweloperskim PayPal jest poprawnie skonfigurowana, zwłaszcza „Adres URL powrotu” lub „URI przekierowania”, który powinien wskazywać na stronę uwierzytelniania Twojego sklepu (np. `https://twoj-sklep.com/authentication?paypal_login=1`).
3.  **Kompatybilność z PHP:** Sprawdź, czy wersja PHP Twojego serwera mieści się w obsługiwanym zakresie (PHP 5.6 - 8.5).

**P: Moi klienci są przekierowywani na niewłaściwą stronę po zalogowaniu.**
O:

1.  **Sprawdź „Adres URL przekierowania po zalogowaniu”:** Przejrzyj to ustawienie w konfiguracji modułu. Wybierz żądaną opcję (np. „Moje konto”, „Poprzednia strona”).
2.  **Wyczyść pamięć podręczną:** Po zmianie tego ustawienia wyczyść pamięć podręczną PrestaShop i przeglądarki.

**P: Czy mogę zmienić tekst na przycisku logowania PayPal?**
O: Moduł zazwyczaj używa standardowego brandingu PayPal dla tekstu i stylu przycisku. Bezpośrednia modyfikacja tekstu zazwyczaj nie jest opcją w samej konfiguracji modułu, ponieważ jest on zaprojektowany tak, aby przestrzegać wytycznych PayPal. Jeśli potrzebujesz niestandardowego tekstu, wymagałoby to nadpisania na poziomie motywu lub dostosowania modułu (patrz Przewodnik dla programistów).

**P: Czy ten moduł działa ze sklepami wielojęzycznymi?**
O: Tak, moduł jest zaprojektowany tak, aby był kompatybilny z funkcjami wielojęzycznymi PrestaShop. Sam interfejs logowania PayPal jest obsługiwany przez PayPal, który zazwyczaj dostosowuje się do języka przeglądarki użytkownika. Wszelkie teksty specyficzne dla modułu (jeśli występują) można przetłumaczyć za pomocą **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „PayPal login connect” (`plogin`) to standardowy moduł PrestaShop, zaimplementowany głównie w jego głównym pliku `index.php`, który działa jako punkt wejścia modułu i obsługa konfiguracji. Wykorzystuje system hooków PrestaShop do wstrzykiwania przycisku „Zaloguj się z PayPal” w różne miejsca w front-office. Moduł obsługuje przepływ OAuth 2.0 z PayPal w celu uwierzytelniania użytkownika, tworząc konto klienta, jeśli takie nie istnieje, i logując użytkownika. Nie wprowadza niestandardowych tabel baz danych ani złożonych struktur `ObjectModel`, opierając się na natywnych klasach PrestaShop `Customer` i `Configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów front-office ani back-office w katalogu `controllers/`. Cała logika front-office związana z wywołaniem zwrotnym PayPal jest obsługiwana bezpośrednio w pliku `index.php` (głównej klasie modułu) za pomocą parametrów `$_GET`, a konfiguracja back-office jest zarządzana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie zawiera niestandardowych klas ani modeli w katalogu `classes/`. Cała logika podstawowa, w tym interakcja z API i obsługa klienta, jest hermetyzowana w głównej klasie `plogin` zdefiniowanej w `index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`plogin/js/plogin.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten skrypt prawdopodobnie obsługuje interakcję po stronie klienta dla przycisku logowania PayPal. Może to obejmować:
        -   Otwieranie okna uwierzytelniania PayPal jako wyskakującego okienka.
        -   Obsługa przekierowania po uwierzytelnieniu PayPal.
        -   Potencjalne zarządzanie żądaniami AJAX dla statusu logowania lub dynamicznego renderowania przycisków.
        -   Wiązanie zdarzeń kliknięcia z przyciskami logowania PayPal.
        -   Zapewnienie funkcjonalności przycisku w różnych przeglądarkach i urządzeniach.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`plogin/css.css`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten arkusz stylów prawdopodobnie zawiera ogólne style dla przycisku logowania PayPal i wszelkich powiązanych elementów. Może definiować podstawowy układ, wypełnienie, marginesy i style czcionek.
    -   **Kluczowe selektory:** Programiści mogą sprawdzić ten plik pod kątem nazw klas (np. `.paypal-login-button`, `.plogin-container`), aby nadpisać style w pliku `custom.css` lub `theme.css` swojego motywu.
-   **`plogin/css/plogin.css`**
    -   **Zakres:** Front-office.
    -   **Cel:** Podobnie jak `css.css`, ten plik zapewnia dodatkowe lub bardziej szczegółowe style dla przycisku logowania PayPal, potencjalnie obejmując różne style przycisków w zależności od konfiguracji, efektów najechania myszą lub responsywnych dostosowań.
    -   **Kluczowe selektory:** Szukaj konkretnych klas przycisków (np. `.plogin-btn-blue`, `.plogin-btn-white`), aby je dostosować.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje kompleksowy zestaw szablonów Smarty do wstrzykiwania przycisku logowania PayPal w różne hooki PrestaShop.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `plogin/createAccountForm.tpl`: Renderuje przycisk PayPal w formularzu rejestracji klienta.
    -   `plogin/displayCustomerLoginFormAfter.tpl`: Renderuje przycisk PayPal po standardowym formularzu logowania klienta.
    -   `plogin/displayFooter.tpl`: Renderuje przycisk PayPal w stopce sklepu.
    -   `plogin/displayHome.tpl`: Renderuje przycisk PayPal na stronie głównej.
    -   `plogin/displayleftColumn.tpl`: Renderuje przycisk PayPal w lewej kolumnie.
    -   `plogin/displayNav.tpl`: Renderuje przycisk PayPal w głównym pasku nawigacji (powszechny hook dla linków na górze).
    -   `plogin/displayNav1.tpl`: Renderuje przycisk PayPal w alternatywnym hooku nawigacji (zależne od motywu).
    -   `plogin/displayNav2.tpl`: Renderuje przycisk PayPal w innym alternatywnym hooku nawigacji (zależne od motywu).
    -   `plogin/displayPopUpLogin.tpl`: Renderuje przycisk PayPal w wyskakującym formularzu logowania (jeśli jest używany przez motyw).
    -   `plogin/displayrightColumn.tpl`: Renderuje przycisk PayPal w prawej kolumnie.
    -   `plogin/displayTop.tpl`: Renderuje przycisk PayPal w bardzo górnej sekcji strony (zależne od motywu).
    -   `plogin/header.tpl`: Ten szablon jest prawdopodobnie używany do dołączania zasobów CSS/JS w sekcji `<head>`, gdy używany jest hook `displayHeader`, zamiast wyświetlania widocznego przycisku.
    -   `plogin/shoppingCart.tpl`: Renderuje przycisk PayPal w podsumowaniu koszyka.
    -   `plogin/shoppingCartExtra.tpl`: Renderuje przycisk PayPal w dodatkowej sekcji koszyka (zależne od motywu).
    -   `plogin/top.tpl`: Podobnie jak `displayTop`, dla górnej sekcji strony.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:
    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Ustawienia konfiguracji (identyfikator klienta, tajny klucz klienta, status włączenia, wybrane hooki, adres URL przekierowania, styl przycisku) są przechowywane w tabeli `ps_configuration` PrestaShop, zazwyczaj z kluczami poprzedzonymi `PLOGIN_` (np. `PLOGIN_CLIENT_ID`, `PLOGIN_ENABLED`).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas / Lokalizacja wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Do globalnego dołączania zasobów CSS i JavaScript dla modułu. |
| `displayNav` | W głównym pasku nawigacji, zazwyczaj na górze strony. | Wyświetla przycisk logowania PayPal w widocznym obszarze nawigacji. |
| `displayNav1` | Alternatywny hook nawigacji (zależny od motywu). | Zapewnia elastyczność dla motywów z wieloma obszarami nawigacji. |
| `displayNav2` | Inny alternatywny hook nawigacji (zależny od motywu). | Zapewnia elastyczność dla motywów z wieloma obszarami nawigacji. |
| `displayTop` | W bardzo górnej sekcji strony, powyżej głównej zawartości. | Wyświetla przycisk logowania PayPal w górnym pasku. |
| `displayLeftColumn` | W lewym pasku bocznym stron, które go posiadają. | Wyświetla przycisk logowania PayPal w lewej kolumnie. |
| `displayRightColumn` | W prawym pasku bocznym stron, które go posiadają. | Wyświetla przycisk logowania PayPal w prawej kolumnie. |
| `displayFooter` | W sekcji stopki sklepu. | Wyświetla przycisk logowania PayPal w stopce. |
| `displayHome` | Na stronie głównej sklepu. | Wyświetla przycisk logowania PayPal na głównej stronie docelowej. |
| `displayCustomerLoginFormAfter` | Po standardowym formularzu logowania na stronie uwierzytelniania. | Zapewnia opcję logowania PayPal jako alternatywę dla adresu e-mail/hasła. |
| `createAccountForm` | Na stronie rejestracji klienta. | Oferuje PayPal jako szybką metodę rejestracji. |
| `displayPopUpLogin` | W wyskakującym oknie logowania (jeśli zaimplementowane przez motyw). | Integruje się z nowoczesnymi wyskakującymi oknami logowania motywu. |
| `shoppingCart` | W bloku podsumowania koszyka. | Oferuje logowanie/rejestrację podczas fazy przeglądania koszyka. |
| `shoppingCartExtra` | W dodatkowej sekcji koszyka (zależne od motywu). | Zapewnia dodatkową elastyczność umieszczania w koszyku. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „PayPal login connect”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
