---
title: "Aktywacja konta linkiem e-mail - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Aktywacja konta linkiem e-mail” od MyPresta.eu."
sidebar:
  label: "Aktywacja konta linkiem e-mail - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Account activation by email link na MyPresta.eu](https://mypresta.eu/modules/front-office-features/account-activation-by-email-link.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/account-activation-by-email-link/)
>
> ---


# Aktywacja konta linkiem e-mail

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Aktywacja konta linkiem e-mail”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok nazwy modułu.

#### **Ustawienia ogólne**

-   **Wyślij e-mail z linkiem aktywacyjnym konta do administratora:**

    -   **Co robi to ustawienie:** Kontroluje, czy powiadomienie e-mail jest również wysyłane do administratora sklepu (Ciebie) za każdym razem, gdy nowy klient rejestruje się i musi aktywować swoje konto.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Tak”):* Otrzymasz powiadomienie e-mail na główny adres e-mail kontaktowy Twojego sklepu (zazwyczaj `PS_SHOP_EMAIL`) za każdym razem, gdy nowy klient zarejestruje się i czeka na aktywację. Może to być przydatne do monitorowania nowych rejestracji.
        -   *Gdy wyłączone („Nie”):* Żadne powiadomienie e-mail nie zostanie wysłane do administratora po rejestracji nowego klienta.
    -   **Zalecana wartość:** „Nie” dla większości sklepów, aby uniknąć zaśmiecania skrzynki e-mail, chyba że potrzebujesz konkretnie monitorować każdą nową rejestrację.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli prowadzisz mały, niszowy sklep i chcesz osobiście powitać lub przejrzeć każdego nowego klienta, włączenie tej opcji może Cię informować. Dla większych sklepów jest to zazwyczaj niepotrzebne.
-   **Tytuł e-maila do administratora:**

    -   **Co robi to ustawienie:** Definiuje temat e-maila wysyłanego do administratora, gdy nowe konto jest rejestrowane (jeśli „Wyślij e-mail z linkiem aktywacyjnym konta do administratora” jest włączone).
    -   **Efekt zmiany tego ustawienia:** Zmienia temat e-maila z powiadomieniem dla administratora.
    -   **Zalecana wartość:** „Nowa rejestracja klienta oczekująca na aktywację - {shop\_name}” (lub podobne, używając `{shop_name}` dla nazwy Twojego sklepu).
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz chcieć umieścić nazwę swojego sklepu w tytule dla łatwej identyfikacji w skrzynce odbiorczej, np. „Nowy klient w Moim Niesamowitym Sklepie - Aktywacja w toku”.
-   **Automatyczne logowanie klienta po aktywacji:**

    -   **Co robi to ustawienie:** Określa, czy klient jest automatycznie logowany na swoje konto natychmiast po kliknięciu linku aktywacyjnego w e-mailu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Tak”):* Po kliknięciu linku aktywacyjnego, klient jest płynnie logowany na swoje nowo aktywowane konto i zazwyczaj przekierowywany do panelu konta lub strony głównej. Zapewnia to płynniejsze doświadczenie użytkownika.
        -   *Gdy wyłączone („Nie”):* Po kliknięciu linku aktywacyjnego, konto klienta jest aktywowane, ale *nie* jest on automatycznie logowany. Zostanie przekierowany na stronę logowania i poproszony o ręczne wprowadzenie swoich danych uwierzytelniających.
    -   **Zalecana wartość:** „Tak” dla lepszego doświadczenia klienta, zmniejszając tarcie.
    -   **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji sprawia, że proces aktywacji wydaje się bardziej kompletny i przyjazny dla użytkownika, ponieważ klient nie musi wykonywać dodatkowego kroku po zweryfikowaniu swojego adresu e-mail.
-   **Aktywuj konto na konkretnej stronie:**

    -   **Co robi to ustawienie:** Pozwala zdefiniować konkretną stronę w Twoim sklepie, na którą klient zostanie przekierowany *po* pomyślnej aktywacji konta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone („Tak”):* Moduł użyje adresu URL określonego w polu „Link do konkretnej strony aktywacji” do przekierowania po aktywacji.
        -   *Gdy wyłączone („Nie”):* Klient zostanie przekierowany na domyślną stronę (zazwyczaj stronę główną lub stronę konta klienta) po aktywacji.
    -   **Zalecana wartość:** „Nie” domyślnie, chyba że masz konkretną strategię marketingową lub onboardingową.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz chcieć przekierować nowych klientów na stronę „Witaj” z ofertami specjalnymi, przewodnikiem po Twoim sklepie lub konkretną kategorią produktów, aby zachęcić ich do pierwszego zakupu.
-   **Link do konkretnej strony aktywacji:**

    -   **Co robi to ustawienie:** To pole pojawia się tylko, jeśli „Aktywuj konto na konkretnej stronie” jest włączone. Tutaj wprowadzasz pełny adres URL strony, na którą chcesz przekierować klientów po aktywacji.
    -   **Efekt zmiany tego ustawienia:** Definiuje dokładny docelowy adres URL dla przekierowania po aktywacji.
    -   **Zalecana wartość:** Pozostaw puste, jeśli „Aktywuj konto na konkretnej stronie” jest „Nie”. Jeśli włączone, podaj pełny, prawidłowy adres URL (np. `https://twojskep.com/content/1-dostawa`).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz stronę „Witaj nowy kliencie” pod adresem `https://twojskep.com/witamy-nowych-klientow`, wprowadź ten adres URL tutaj.

#### **Ustawienia treści e-maila**

-   **Tytuł e-maila do klienta:**
    -   **Co robi to ustawienie:** Definiuje temat e-maila aktywacyjnego wysyłanego do klienta.
    -   **Efekt zmiany tego ustawienia:** Zmienia temat, który klienci widzą w swojej skrzynce odbiorczej dla e-maila aktywacyjnego.
    -   **Zalecana wartość:** „Aktywuj swoje konto w {shop\_name}” lub „Proszę zweryfikuj swój adres e-mail dla {shop\_name}” (używając `{shop_name}` dla nazwy Twojego sklepu).
    -   **Scenariusz/przykład dla sprzedawcy:** Jasny i zwięzły temat pomaga klientom zidentyfikować e-mail i zachęca ich do otwarcia go, zmniejszając ryzyko oznaczenia go jako spam.

#### **Inne ustawienia (wewnętrzne / techniczne)**

-   **mypresta\_updates, update\_, updatev\_:** Są to wewnętrzne ustawienia używane przez moduły MyPresta.eu do sprawdzania aktualizacji i zarządzania wersjami. Zazwyczaj **nie** powinieneś ich modyfikować.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Są to standardowe wartości konfiguracyjne PrestaShop, które moduł może odczytywać lub wyświetlać dla kontekstu, ale nie są bezpośrednio konfigurowalne w samym module. Odzwierciedlają one Twoje ogólne ustawienia PrestaShop.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyślij e-mail z linkiem aktywacyjnym konta do administratora | Nie | Kontroluje powiadomienia administratora o nowych rejestracjach. |
| Konfiguracja modułu | Tytuł e-maila do administratora | „Nowa rejestracja klienta oczekująca na aktywację - {shop\_name}” | Temat e-maila z powiadomieniem dla administratora. |
| Konfiguracja modułu | Automatyczne logowanie klienta po aktywacji | Tak | Automatycznie loguje klienta po pomyślnej aktywacji. |
| Konfiguracja modułu | Aktywuj konto na konkretnej stronie | Nie | Włącza przekierowanie na niestandardową stronę po aktywacji. |
| Konfiguracja modułu | Link do konkretnej strony aktywacji | (Puste, jeśli wyłączone) | Adres URL dla przekierowania po aktywacji (jeśli włączone). |
| Konfiguracja modułu | Tytuł e-maila do klienta | „Aktywuj swoje konto w {shop\_name}” | Temat e-maila aktywacyjnego dla klienta. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują e-maila aktywacyjnego. Co powinienem zrobić?**

-   **Odp.:**
    1.  **Sprawdź foldery spam/śmieci:** Doradź klientom, aby sprawdzili swoje foldery spam lub śmieci.
    2.  **Zweryfikuj ustawienia e-mail sklepu:** Przejdź do **Parametry sklepu > Kontakt > Sklepy** (lub **Zaawansowane > E-mail** w starszych wersjach) w Panelu administracyjnym PrestaShop. Upewnij się, że konfiguracja e-mail Twojego sklepu jest poprawna i że e-maile są wysyłane pomyślnie (przetestuj, wysyłając e-mail testowy).
    3.  **Funkcjonalność poczty serwera:** Skontaktuj się z dostawcą hostingu, aby upewnić się, że funkcja poczty Twojego serwera (PHP `mail()` lub SMTP) działa poprawnie i nie jest blokowana.
    4.  **Konfiguracja modułu:** Dokładnie sprawdź „Tytuł e-maila do klienta” w ustawieniach modułu. Bardzo ogólny lub podejrzany tytuł może wywołać filtry antyspamowe.
    5.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami problemy z pamięcią podręczną mogą uniemożliwić wysyłanie e-maili.

**P2: Klient aktywował swoje konto, ale nadal nie może się zalogować.**

-   **Odp.:**
    1.  **Sprawdź status klienta:** W Panelu administracyjnym PrestaShop przejdź do **Klienci > Klienci**. Znajdź konto klienta i sprawdź, czy jego status „Włączone” jest ustawiony na „Tak”. Jeśli nie, włącz go ręcznie.
    2.  **Resetowanie hasła:** Zasugeruj klientowi skorzystanie z linku „Nie pamiętasz hasła” na stronie logowania. Może to rozwiązać problemy, jeśli klient źle pamięta swoje hasło.
    3.  **Pamięć podręczna/pliki cookie przeglądarki:** Poproś klienta o wyczyszczenie pamięci podręcznej i plików cookie przeglądarki lub spróbowanie zalogowania się z innej przeglądarki lub okna incognito.
    4.  **Konflikt modułów:** Tymczasowo wyłącz inne moduły, które wchodzą w interakcje z kontami klientów lub procesami logowania, aby wykluczyć konflikty.

**P3: Jak mogę ręcznie aktywować konto klienta, jeśli nie może on otrzymać e-maila?**

-   **Odp.:** Możesz ręcznie aktywować konto klienta z Panelu administracyjnego PrestaShop:
    1.  Przejdź do **Klienci > Klienci**.
    2.  Znajdź nazwisko klienta na liście i kliknij „Edytuj” (ikonę ołówka).
    3.  Na stronie szczegółów klienta znajdź przełącznik „Włączone” i ustaw go na „Tak”.
    4.  Kliknij „Zapisz”. Klient będzie teraz mógł się zalogować.

**P4: Link aktywacyjny przekierowuje na niewłaściwą stronę lub wyświetla błąd.**

-   **Odp.:**
    1.  **Sprawdź „Link do konkretnej strony aktywacji”:** Jeśli masz włączone „Aktywuj konto na konkretnej stronie”, sprawdź, czy adres URL wprowadzony w polu „Link do konkretnej strony aktywacji” jest absolutnie poprawny i dostępny. Błąd typograficzny lub nieprawidłowy adres URL spowoduje problemy z przekierowaniem.
    2.  **Przyjazne adresy URL:** Upewnij się, że Twoje Przyjazne adresy URL są włączone i działają poprawnie (**Parametry sklepu > Ruch i SEO**).
    3.  **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
    4.  **Sprawdź .htaccess:** Jeśli wprowadziłeś jakiekolwiek ręczne zmiany w pliku `.htaccess`, przywróć je lub upewnij się, że nie kolidują z przepisywaniem adresów URL.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Aktywacja konta linkiem e-mail” (`acactiv`) to standardowy moduł PrestaShop, zaprojektowany przede wszystkim do przechwytywania procesu rejestracji klienta. Wykorzystuje system hooków PrestaShop do modyfikowania domyślnego zachowania, w szczególności `actionCustomerAccountAdd` do oznaczania nowych kont jako nieaktywnych i wysyłania e-maili aktywacyjnych, oraz `displayHeader` do wstrzykiwania niezbędnego kodu JavaScript. Moduł nie wprowadza nowych tabel bazy danych ani złożonych struktur `ObjectModel`, zamiast tego opiera się na modyfikowaniu istniejących właściwości obiektu `Customer` i używaniu `ps_configuration` do swoich ustawień.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani back-office. Cała logika jest obsługiwana w głównym pliku modułu (`acactiv.php`) i jego zarejestrowanych hookach. Sam link aktywacyjny wskazuje na główny dispatch modułu, który następnie obsługuje logikę aktywacji.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio wchodzi w interakcje z podstawową klasą `Customer` i klasą `Configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`acactiv/views/acactiv-compat.js`**

    -   **Zakres:** Front-office.
    -   **Cel:** Ten skrypt prawdopodobnie zawiera poprawki kompatybilności lub polifille dla starszych wersji PrestaShop lub przeglądarek, zapewniając, że funkcjonalność front-end modułu działa w szerszym zakresie środowisk. Może dotyczyć różnic w wersjach jQuery lub metodach manipulacji DOM.
    -   **Słuchacze zdarzeń/Manipulacja DOM:** Szczegóły wymagałyby przeglądu kodu, ale zazwyczaj obejmuje to upewnienie się, że elementy są obecne lub dostosowanie zachowań w zależności od wersji PrestaShop.
-   **`acactiv/views/acactiv.js`**

    -   **Zakres:** Front-office.
    -   **Cel:** Jest to główny plik JavaScript do interakcji z front-office. Jest odpowiedzialny za wyświetlanie wiadomości użytkownikowi po rejestracji (np. „Sprawdź swój e-mail w celu uzyskania linku aktywacyjnego”) i potencjalnie obsługę aspektów procesu aktywacji po stronie klienta.
    -   **Słuchacze zdarzeń/Manipulacja DOM:**
        -   Może nasłuchiwać przesyłania formularzy na stronie rejestracji w celu wyświetlania niestandardowych wiadomości.
        -   Może manipulować DOM w celu pokazywania/ukrywania elementów, wyświetlania wyskakujących powiadomień lub przekierowywania użytkownika po określonych działaniach.
        -   Może używać `prestashop.on('updatedProduct', function(event) { ... });` lub podobnych słuchaczy zdarzeń PrestaShop, jeśli musi reagować na dynamiczne aktualizacje treści, choć jest to mniej prawdopodobne dla podstawowej funkcji tego modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`acactiv/views/acactiv.css`**
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Cel:** Zapewnia podstawową stylizację dla wszelkich niestandardowych wiadomości lub elementów wprowadzonych przez moduł w front-office. Może to obejmować stylizację wiadomości „konto oczekujące na aktywację” lub potwierdzenia „konto aktywowane”.
    -   **Kluczowe selektory klas CSS:** Programiści powinni sprawdzić wyjściowy kod HTML modułu, aby zidentyfikować konkretne klasy (np. `.acactiv-message`, `.acactiv-success`, `.acactiv-error`), które można nadpisać w pliku `custom.css` lub `theme.css` ich motywu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   **`acactiv/views/checkout_notice.tpl`**
        -   **Hook:** Nie jest wyraźnie określony jako szablon hooka, ale jego nazwa sugeruje, że może być renderowany w kontekście związanym z kasą lub tworzeniem konta, prawdopodobnie za pośrednictwem `displayCustomerAccountForm` lub podobnego, w celu wyświetlenia powiadomienia o aktywacji.
        -   **Wyjście:** Prawdopodobnie wyświetla informacyjną wiadomość dla klienta po rejestracji, instruując go, aby sprawdził swój e-mail w celu uzyskania linku aktywacyjnego.
    -   **`acactiv/views/displayHeader.tpl`**
        -   **Hook:** `displayHeader`
        -   **Wyjście:** Ten szablon jest zazwyczaj używany do dołączania plików CSS i JavaScript w sekcji `<head>` stron front-office. Będzie zawierał tagi `<link>` dla `acactiv.css` i tagi `<script>` dla `acactiv-compat.js` i `acactiv.js`, zapewniając, że te zasoby są ładowane na odpowiednich stronach.
-   **Szablony administratora (`views/templates/admin/`)**: Brak zidentyfikowanych. Konfiguracja jest obsługiwana bezpośrednio w `getContent()` w `acactiv.php`.
-   **Szablony front-office (`views/templates/front/`)**: Brak zidentyfikowanych jako dedykowane samodzielne strony.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy niestandardowych tabel SQL.
    -   Modyfikuje kolumnę `active` tabeli `ps_customer` (ustawiając ją na `0` dla nowych rejestracji do momentu aktywacji).
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` z kluczami takimi jak `ACACTIV_SENDTOME`, `ACACTIV_SPECURLFEATURE`, `ACACTIV_SPECURL`, `ACACTIV_AUTOLOGIN`, `ACACTIV_ATITLE`, `ACACTIV_CTITLE`.
-   **Tabela zarejestrowanych hooków**:
"""
