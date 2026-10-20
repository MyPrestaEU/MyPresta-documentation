---
title: "Strony CMS chronione hasłem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Strony CMS chronione hasłem” od MyPresta.eu."
sidebar:
  label: "Strony CMS chronione hasłem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Password protected CMS pages na MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-cms-pages.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/password-protected-cms-pages/)
>
> ---


# Strony CMS chronione hasłem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji, kliknięcie „Konfiguruj” na module przeniesie Cię do jego głównego ekranu konfiguracji. Ten ekran służy przede wszystkim jako punkt wejścia do dedykowanego obszaru zarządzania chronionymi stronami CMS.

-   **Co robi ten ekran:** Ta strona zazwyczaj zawiera krótki przegląd lub bezpośredni link do głównego interfejsu zarządzania, gdzie faktycznie będziesz konfigurować i zarządzać swoimi stronami CMS chronionymi hasłem. Może również zawierać ogólne ustawienia, jeśli moduł takie posiadał, ale dla tego modułu podstawowa funkcjonalność jest zarządzana w oddzielnej sekcji.
-   **Wpływ zmiany ustawień:** Wszelkie ustawienia tutaj bezpośrednio wpływałyby na globalne zachowanie lub wygląd modułu.
-   **Zalecana wartość:** Postępuj zgodnie z instrukcjami na ekranie, zazwyczaj klikając przycisk, aby przejść do zarządzania stronami CMS.
-   **Scenariusz sprzedawcy / przykład:** Właśnie zainstalowałeś moduł. Prawdopodobnie zobaczysz przycisk taki jak „Zarządzaj chronionymi stronami CMS” lub „Konfiguruj hasła CMS”. Kliknięcie tego przeniesie Cię do dedykowanego ekranu, aby rozpocząć ochronę swoich stron.

### 2.2 Dedykowany ekran administracyjny: Zarządzaj chronionymi stronami CMS (Panel administracyjny > Moduły > Strony CMS chronione hasłem > Konfiguruj > [Link do zarządzania])

Jest to główny ekran, na którym będziesz zarządzać, które strony CMS są chronione i jakie są ich hasła. Dostęp do tego ekranu uzyskujesz zazwyczaj, klikając link lub przycisk z głównej strony konfiguracji modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Zazwyczaj znajdziesz nową pozycję menu w **Moduły > Menedżer modułów > Strony CMS chronione hasłem > Konfiguruj**, która następnie przekieruje Cię do interfejsu zarządzania. Adres URL może wyglądać mniej więcej tak: `admin/index.php?controller=AdminPcmsController`.
-   **Dostępne akcje i ustawienia:**
    -   **Tabela listująca:** Ten ekran wyświetli tabelę listującą wszystkie Twoje istniejące strony CMS. Dla każdej strony zobaczysz jej nazwę, ID i informację, czy jest obecnie chroniona.
    -   **Dodaj/Edytuj ochronę:** Dla każdej strony CMS na liście zazwyczaj znajdziesz przycisk/ikonę „Edytuj” lub „Konfiguruj”. Kliknięcie tego otworzy formularz, w którym możesz:
        -   **Włącz/Wyłącz ochronę:** Prosty przełącznik (Tak/Nie) do włączania lub wyłączania ochrony hasłem dla tej konkretnej strony CMS.
            -   *Gdy włączone:* Strona będzie wymagać hasła do wyświetlenia jej zawartości w front office.
            -   *Gdy wyłączone:* Strona będzie publicznie dostępna jako standardowa strona CMS.
            -   *Zalecana wartość:* „Tak” dla stron, które chcesz chronić, „Nie” dla stron publicznych.
            -   *Scenariusz sprzedawcy:* Chcesz chronić swoją stronę „Oferty VIP”, więc włączasz ochronę.
        -   **Ustaw hasło:** Pole wprowadzania, w którym definiujesz hasło dla tej konkretnej strony CMS.
            -   *Wpływ zmiany:* Jest to dokładne hasło, które klienci będą musieli wprowadzić, aby wyświetlić stronę.
            -   *Zalecana wartość:* Wybierz silne, unikalne hasło dla każdej chronionej strony.
            -   *Scenariusz sprzedawcy:* Ustawiasz „MOJATAJNAOFERTA” jako hasło dla swojej strony „Oferty VIP”.
    -   **Akcje masowe:** W zależności od wersji modułu, mogą istnieć opcje włączania/wyłączania ochrony dla wielu stron jednocześnie, chociaż indywidualne zarządzanie stronami jest bardziej powszechne dla ustawień haseł.
-   **Wpływ zmian:**
    -   Gdy włączysz ochronę i ustawisz hasło dla strony CMS, ta strona natychmiast staje się chroniona hasłem w Twoim front office. Klienci odwiedzający jej adres URL zobaczą monit o hasło.
    -   Wyłączenie ochrony sprawia, że strona ponownie staje się publicznie widoczna.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zdecyduj, które strony CMS muszą być prywatne lub ekskluzywne.
    2.  Przejdź do ekranu „Zarządzaj chronionymi stronami CMS”.
    3.  Znajdź żądaną stronę CMS na liście.
    4.  Kliknij „Edytuj” lub równoważną akcję dla tej strony.
    5.  Włącz przełącznik ochrony hasłem.
    6.  Wprowadź silne, unikalne hasło.
    7.  Zapisz zmiany.
    8.  Przekaż hasło swojej docelowej grupie odbiorców.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Zarządzaj chronionymi stronami CMS** | Włącz/Wyłącz ochronę | Nie / Tak (w zależności od potrzeb) | Kontroluje, czy konkretna strona CMS wymaga hasła do wyświetlenia. |
| | Hasło dla strony CMS | (Puste) / Silne, unikalne hasło | Dokładny ciąg znaków, który klienci muszą wprowadzić, aby uzyskać dostęp do chronionej treści. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Ustawiłem hasło, ale strona jest nadal widoczna bez niego. Co jest nie tak?**
O:

1.  **Sprawdź, czy ochrona jest włączona:** Przejdź do ekranu „Zarządzaj chronionymi stronami CMS” i upewnij się, że przełącznik „Włącz ochronę” dla tej konkretnej strony CMS jest ustawiony na „Tak”.
2.  **Wyczyść pamięć podręczną przeglądarki:** Twoja przeglądarka może wyświetlać Ci buforowaną wersję strony. Spróbuj wyczyścić pamięć podręczną przeglądarki lub otworzyć stronę w trybie incognito/prywatnym.
3.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** w swoim Panelu administracyjnym i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Zapewnia to, że PrestaShop serwuje najnowszą konfigurację.

**P: Czy mogę mieć różne hasła do różnych stron CMS?**
O: Tak! Ten moduł jest do tego właśnie przeznaczony. Każda strona CMS może mieć swoje własne unikalne hasło, co pozwala tworzyć wiele poziomów chronionych treści.

**P: Co się stanie, jeśli klient wprowadzi błędne hasło?**
O: Moduł wyświetli komunikat o błędzie (np. „Nieprawidłowe hasło. Spróbuj ponownie.”) i ponownie pojawi się formularz wprowadzania hasła, umożliwiając klientowi ponowne wprowadzenie hasła.

**P: Czy mogę dostosować wygląd formularza wprowadzania hasła?**
O: Moduł używa podstawowego stylu dla formularza hasła. W celu zaawansowanej personalizacji, potrzebny byłby webmaster lub programista do modyfikacji pliku CSS modułu (`css.css`) lub nadpisania jego szablonu (`cms.tpl`).

**P: Zaktualizowałem swój motyw PrestaShop, a teraz formularz hasła wygląda dziwnie. Co powinienem zrobić?**
O: Niestandardowe motywy czasami mają własne style, które mogą kolidować z wyświetlaniem modułów.

1.  **Wyczyść pamięć podręczną PrestaShop:** Zawsze spróbuj tego najpierw (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
2.  **Skontaktuj się z twórcą motywu:** Mogą mieć oni konkretne instrukcje dotyczące kompatybilności modułów.
3.  **Skonsultuj się z webmasterem:** Programista może zbadać CSS i HTML, aby zidentyfikować i rozwiązać konflikty stylów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Strony CMS chronione hasłem” (`passcms`) działa głównie poprzez nadpisanie podstawowego `CmsController` w celu przechwytywania żądań stron CMS. Gdy żądana jest chroniona strona CMS, sprawdza on poprawność hasła w sesji. Jeśli nie znaleziono poprawnego hasła, renderuje formularz wprowadzania hasła zamiast rzeczywistej zawartości CMS. Moduł używa dedykowanego kontrolera administracyjnego (`AdminPcmsController`) do zarządzania ustawieniami haseł dla każdej strony CMS.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `passcms/override/controllers/front/CmsController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CmsController` (nadpisuje podstawowy `CmsController`)
        -   **Odpowiedzialność**: To jest rdzeń funkcjonalności front-office. Przechwytuje metodę `initContent()` oryginalnego `CmsController`. Sprawdza, czy żądana strona CMS (identyfikowana przez `id_cms`) jest skonfigurowana jako chroniona hasłem. Jeśli tak i w sesji nie ma poprawnego hasła, renderuje szablon `cms.tpl` z formularzem wprowadzania hasła. Obsługuje również żądanie POST dla przesłania hasła, walidując je względem zapisanego hasła i ustawiając zmienną sesji po sukcesie.
    -   `passcms/override/controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Nie jest klasą, zazwyczaj pusty plik lub podstawowe zabezpieczenie zapobiegające bezpośredniemu listowaniu katalogów.
        -   **Odpowiedzialność**: Standardowa praktyka PrestaShop dla katalogów `override`.
-   **Kontrolery administracyjne Back-Office**:

    -   `passcms/controllers/admin/AdminPcmsController.php`
        -   **Nazwa zakładki i zarządzana encja**: Zarządza ustawieniami ochrony hasłem dla poszczególnych stron CMS. Ten kontroler rozszerza `ModuleAdminController` i zapewnia interfejs do listowania stron CMS oraz konfigurowania ich haseł. Obsługuje operacje CRUD dla encji `pcms` (chociaż nie ma jawnie wymienionego `ObjectModel`, prawdopodobnie bezpośrednio współdziała z `ps_configuration` lub niestandardową tabelą do przechowywania haseł). Renderuje widok siatki stron CMS i formularz do edycji ustawień haseł.
    -   `passcms/controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Nie jest klasą, zazwyczaj pusty plik lub podstawowe zabezpieczenie zapobiegające bezpośredniemu listowaniu katalogów.
        -   **Odpowiedzialność**: Standardowa praktyka PrestaShop dla katalogów kontrolerów.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł prawdopodobnie przechowuje swoją konfigurację bezpośrednio w tabeli `ps_configuration`, używając kluczy takich jak `PCMS_PASSWORD_ID_CMS_X`, gdzie `X` to `id_cms`, lub może używać niestandardowej tabeli, która jest zarządzana bezpośrednio przez `AdminPcmsController` bez dedykowanego `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu wskazuje brak niestandardowych plików JavaScript. Przesyłanie hasła jest prawdopodobnie obsługiwane za pomocą standardowego formularza HTML POST lub prostego wbudowanego JS, jeśli obecne jest jakiekolwiek dynamiczne zachowanie.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `passcms/css.css`
    -   **Zakres**: Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Ten plik zawiera podstawową stylizację formularza wprowadzania hasła wyświetlanego na chronionych stronach CMS. Prawdopodobnie celuje w elementy takie jak kontener formularza, pole wprowadzania i przycisk przesyłania.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: Programiści mogą zbadać wyrenderowany kod HTML formularza hasła, aby zidentyfikować konkretne klasy (np. `.passcms-form`, `.passcms-input`, `.passcms-button`, `.passcms-error`) i nadpisać je w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `passcms/admin.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie używany dla głównej strony konfiguracji modułu, zapewniając punkt wejścia lub ogólne informacje, potencjalnie linkując do interfejsu zarządzania `AdminPcmsController`.
    -   `passcms/views/templates/admin/script.tpl`
        -   **Cel**: Ten szablon może zawierać wbudowany kod JavaScript lub zmienne Smarty, które są renderowane w Panelu administracyjnym dla `AdminPcmsController` w celu obsługi dynamicznego zachowania lub przekazywania danych.
-   **Szablony front-office (`views/templates/front/`)**:

    -   `passcms/views/templates/front/cms.tpl`
        -   **Cel**: Jest to kluczowy szablon renderowany przez nadpisany `CmsController`, gdy chroniona strona CMS jest dostępna bez ważnego hasła. Zawiera strukturę HTML dla formularza wprowadzania hasła, w tym pole wprowadzania, przycisk przesyłania i wszelkie komunikaty o błędach.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy jawnie niestandardowej tabeli SQL na podstawie dossier. Jest bardzo prawdopodobne, że ustawienia haseł dla każdej strony CMS są przechowywane w tabeli `ps_configuration` przy użyciu unikalnych kluczy konfiguracyjnych, np. `PCMS_PASSWORD_ID_CMS_X`, gdzie `X` to `id_cms`.
    -   `ps_configuration`: Przechowuje wartości konfiguracji modułu, w tym potencjalnie hasła dla każdej strony CMS.
-   **Tabela zarejestrowanych hooków**:
    Moduł działa głównie poprzez nadpisanie kontrolera, a nie tradycyjne hooki dla swojej podstawowej funkcjonalności. Może jednak rejestrować niektóre standardowe hooki dla ogólnej integracji modułu lub wyświetlania.

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` stron Panelu administracyjnego. | Używany do dołączania CSS (`css.css`) lub JS dla interfejsu `AdminPcmsController`. |
    | `displayHeader` | Renderuje się w sekcji `<head>` stron front-office. | Może być używany do dołączania CSS (`css.css`) lub JS front-office, jeśli jest potrzebny globalnie, chociaż jest bardziej prawdopodobne, że jest ładowany warunkowo przez nadpisanie `CmsController`. |
    | `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje zasoby multimedialne. | Alternatywa dla `displayHeader` do warunkowego ładowania zasobów w zależności od bieżącego kontrolera. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Strony CMS chronione hasłem”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
