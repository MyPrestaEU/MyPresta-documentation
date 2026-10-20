---
title: "Strony produktów chronione hasłem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kro kroku oraz odniesienie dla programistów dla modułu PrestaShop „Strony produktów chronione hasłem” od MyPresta.eu."
sidebar:
  label: "Strony produktów chronione hasłem"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Password protected product pages na MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-product-pages.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/password-protected-product-pages/)
>
> ---


# Strony produktów chronione hasłem

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Jest to główny ekran konfiguracji modułu, dostępny po kliknięciu „Konfiguruj” po instalacji lub z Menedżera modułów.

- **Co robi to ustawienie:** Ten ekran zazwyczaj zawiera ogólne ustawienia modułu, chociaż w przypadku „Stron produktów chronionych hasłem” główne zarządzanie hasłami dla konkretnych produktów odbywa się na dedykowanym ekranie administracyjnym (patrz 4.2). Ten ekran może oferować opcje dotyczące wyglądu strony wprowadzania hasła lub ogólnego zachowania modułu.
- **Wpływ zmiany tego ustawienia:** Wszelkie zmiany tutaj wpłynęłyby na globalne zachowanie mechanizmu ochrony hasłem lub domyślny wygląd formularza wprowadzania hasła.
- **Zalecana wartość:** Wartości domyślne są zazwyczaj dobrym punktem wyjścia.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli istnieje opcja dostosowania wiadomości wyświetlanej na stronie hasła, możesz zmienić ją z „Wprowadź hasło” na „Proszę wprowadzić swój kod dostępu VIP”.

### 2.2 Dedykowany ekran administracyjny: Hasła produktów (Panel administracyjny > Katalog > Hasła produktów)
Jest to najważniejszy ekran do zarządzania tym, które produkty są chronione hasłem i jakie są te hasła. Ten nowy element menu znajdziesz w sekcji **Katalog** w Panelu administracyjnym PrestaShop.

- **Nazwa ekranu i lokalizacja w menu:** **Katalog > Hasła produktów**
- **Dostępne akcje i ustawienia:**
    -   **Tabela listy:** Ten ekran wyświetla listę wszystkich produktów, które aktualnie mają przypisane hasło. Zazwyczaj zobaczysz kolumny takie jak:
        -   **Nazwa produktu:** Nazwa chronionego produktu.
        -   **ID produktu:** Unikalny identyfikator produktu.
        -   **Hasło:** Hasło wymagane do uzyskania dostępu do strony produktu.
        -   **Akcje:** Przyciski do „Edytuj” lub „Usuń” hasło dla konkretnego produktu.
    -   **Dodaj nowe hasło:** Będzie przycisk (np. „Dodaj nowe hasło produktu” lub ikona plusa) do dodania nowego wpisu ochrony hasłem. Po kliknięciu tego przycisku zazwyczaj zostanie wyświetlony formularz:
        -   **Selektor produktu:** Pole do wyszukiwania i wybierania produktu, który chcesz chronić. Może to być pole autouzupełniania, w którym wpisujesz nazwę produktu.
        -   **Pole hasła:** Pole wprowadzania, w którym definiujesz hasło dla tego konkretnego produktu.
    -   **Edytuj hasło:** Kliknięcie „Edytuj” obok istniejącego wpisu pozwala zmienić hasło dla tego produktu lub potencjalnie zmienić powiązany produkt.
    -   **Usuń hasło:** Kliknięcie „Usuń” usuwa ochronę hasłem z tego produktu, czyniąc go ponownie publicznie dostępnym.
- **Wpływ zmian:**
    -   **Dodanie hasła:** Strona wybranego produktu natychmiast stanie się chroniona hasłem w front office.
    -   **Zmiana hasła:** Klienci będą musieli użyć nowego hasła, aby uzyskać dostęp do strony produktu.
    -   **Usunięcie hasła:** Strona produktu powróci do stanu publicznie dostępnego bez wymogu hasła.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Aby chronić nowy produkt: Przejdź do **Katalog > Hasła produktów**, kliknij „Dodaj nowe hasło produktu”, wybierz swój produkt i ustaw silne, unikalne hasło.
    2.  Aby zaktualizować hasło: Znajdź produkt na liście, kliknij „Edytuj” i wprowadź nowe hasło.
    3.  Aby usunąć ochronę: Znajdź produkt na liście i kliknij „Usuń”.
    4.  Regularnie przeglądaj swoje chronione produkty, aby upewnić się, że hasła są nadal aktualne i bezpieczne.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | (Ustawienia ogólne, jeśli istnieją) | (Domyślne modułu) | Globalne zachowanie lub wygląd strony wprowadzania hasła. |
| Katalog > Hasła produktów | Dodaj nowe hasło produktu | N/A | Wybierz produkt i przypisz hasło, aby ograniczyć dostęp do jego strony. |
| Katalog > Hasła produktów | Edytuj hasło produktu | N/A | Zmodyfikuj hasło dla już chronionego produktu. |
| Katalog > Hasła produktów | Usuń hasło produktu | N/A | Usuń ochronę hasłem, czyniąc stronę produktu ponownie publiczną. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem hasło, ale strona produktu jest nadal publiczna. Co jest nie tak?**
O1:
*   **Sprawdź wpis hasła:** Dokładnie sprawdź w **Katalog > Hasła produktów**, czy produkt jest wymieniony i czy hasło jest poprawnie ustawione.
*   **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”, jeśli jest dostępna). Zapewnia to, że Twój sklep ładuje najnowszą konfigurację.
*   **Status modułu:** Upewnij się, że moduł „Strony produktów chronione hasłem” jest włączony w **Moduły > Menedżer modułów**.
*   **Status produktu:** Upewnij się, że sam produkt jest włączony i widoczny w Twoim katalogu.

**P2: Czy mogę mieć różne hasła dla różnych produktów?**
O2: Tak, absolutnie! Moduł jest do tego przeznaczony. Możesz przypisać unikalne hasło do każdego pojedynczego produktu, który chcesz chronić, za pośrednictwem ekranu **Katalog > Hasła produktów**.

**P3: Co się stanie, jeśli klient spróbuje uzyskać dostęp do chronionej strony produktu bezpośrednio za pomocą jej adresu URL bez hasła?**
O3: Zostanie przekierowany na stronę wprowadzania hasła. Nie będzie mógł zobaczyć treści produktu, dopóki nie wprowadzi prawidłowego hasła.

**P4: Jak przetłumaczyć tekst na stronie wprowadzania hasła (np. „Wprowadź hasło”)?**
O4: Zazwyczaj możesz przetłumaczyć teksty modułów za pomocą interfejsu tłumaczeń PrestaShop. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz moduł „Strony produktów chronione hasłem”. Powinieneś tam znaleźć edytowalne ciągi tekstowe.

**P5: Czy ten moduł będzie działał z moim niestandardowym szablonem?**
O5: Moduł jest zaprojektowany tak, aby bezproblemowo integrować się ze standardowymi szablonami PrestaShop. Jednak wysoce spersonalizowane szablony mogą wymagać drobnych korekt CSS, aby formularz wprowadzania hasła wyglądał idealnie. Jeśli napotkasz problemy ze stylizacją, skonsultuj się ze swoim webmasterem lub twórcą szablonu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury
Moduł „Strony produktów chronione hasłem” działa głównie poprzez nadpisywanie domyślnego `ProductController` w celu przechwytywania żądań dla chronionych produktów. Wykorzystuje dedykowany kontroler administracyjny do zarządzania powiązaniami produktów z hasłami, które są przechowywane w bazie danych. Logika front-office sprawdza, czy istnieje prawidłowy plik cookie sesji zawierający hasło dla danego produktu, zanim wyrenderuje rzeczywistą stronę produktu.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    *   `prodpswd/controllers/front/ProductPasswd.php`
        *   **Nazwa klasy i klasa nadrzędna:** `ProductPasswdModuleFrontController` rozszerzający `ModuleFrontController`.
        *   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za renderowanie formularza wprowadzania hasła, gdy uzyskiwany jest dostęp do chronionego produktu. Obsługuje żądanie POST, gdy użytkownik przesyła hasło, waliduje je względem przechowywanego hasła dla produktu i ustawia sesję lub plik cookie po pomyślnym uwierzytelnieniu, aby udzielić dostępu. Może również obsługiwać przekierowanie do rzeczywistej strony produktu.
    *   `prodpswd/override/controllers/front/ProductController.php`
        *   **Nazwa klasy i klasa nadrzędna:** `ProductController` (nadpisany).
        *   **Odpowiedzialność:** Jest to kluczowe nadpisanie. Przechwytuje metodę `init()` lub `postProcess()` podstawowego `ProductController`. Zanim zostanie załadowana standardowa zawartość strony produktu, to nadpisanie sprawdza, czy bieżący produkt jest chroniony hasłem i czy użytkownik już podał prawidłowe hasło (np. za pośrednictwem pliku cookie sesji). Jeśli produkt jest chroniony i nie znaleziono prawidłowego hasła, przekierowuje użytkownika do `ProductPasswdModuleFrontController` (lub bezpośrednio renderuje jego szablon), aby poprosić o hasło.

-   **Kontrolery administracyjne Back-Office**:
    *   `prodpswd/controllers/admin/AdminProdPasswordController.php`
        *   **Nazwa zakładki i zarządzana encja:** Dostępne przez **Katalog > Hasła produktów**. Zarządza encjami `prodpassword` (ID produktu i powiązane hasło).
        *   **Odpowiedzialność:** Jest to standardowy `AdminController` odpowiedzialny za operacje CRUD (Create, Read, Update, Delete) dla powiązań produktów z hasłami. Wyświetla listę chronionych produktów, umożliwia administratorom dodawanie nowych wpisów produktów z hasłami, edytowanie istniejących haseł i ich usuwanie. Prawdopodobnie używa `HelperList` do widoku siatki i `HelperForm` do formularzy dodawania/edycji.
    *   `prodpswd/controllers/admin/index.php`
        *   **Odpowiedzialność:** Ten plik jest zazwyczaj pustym plikiem `index.php` umieszczonym w podkatalogach modułów PrestaShop, aby zapobiec listowaniu katalogów, zwiększając bezpieczeństwo. Nie zawiera żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)
Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Encja `prodpassword` jest prawdopodobnie zarządzana bezpośrednio przez `AdminProdPasswordController` za pomocą prostej definicji `ObjectModel` w głównym pliku modułu lub w samym kontrolerze, lub może bezpośrednio współdziałać z `Configuration` lub niestandardową tabelą bez dedykowanego `ObjectModel`. Biorąc pod uwagę, że `AdminProdPasswordController` zarządza tabelą `prodpassword`, jest bardzo prawdopodobne, że istnieje dla niej zdefiniowany `ObjectModel`, nawet jeśli nie znajduje się w osobnym folderze `classes/`.

### 4.4 Zasoby JavaScript (`views/js/`)
Dossier modułu wskazuje brak niestandardowych plików JavaScript. Formularz hasła w front-office oraz siatka/formularz w back-office mają polegać na standardowym JS PrestaShop lub prostych przesłaniach formularzy HTML.

### 4.5 Arkusze stylów CSS (`views/css/`)
Dossier modułu wskazuje brak niestandardowych plików CSS. Stylizacja strony wprowadzania hasła w front office i formularzy administracyjnych prawdopodobnie będzie dziedziczona z aktywnego szablonu PrestaShop i stylów back-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   Nie wymieniono żadnych konkretnych szablonów hooków, co sugeruje, że moduł działa głównie poprzez nadpisywanie kontrolerów i dedykowane szablony front-office, a nie poprzez wstrzykiwanie treści do standardowych hooków.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   Nie wymieniono żadnych konkretnych szablonów administracyjnych. `AdminProdPasswordController` prawdopodobnie używa standardowych szablonów PrestaShop `HelperList` i `HelperForm` dla swojego interfejsu.
-   **Szablony front-office (`views/templates/front/`)**:
    *   `prodpswd/views/templates/front/product.tpl`
        *   **Cel:** Ten szablon jest prawdopodobnie niestandardowym formularzem wprowadzania hasła wyświetlanym klientom, gdy próbują uzyskać dostęp do chronionej strony produktu. Zawiera strukturę HTML dla pola wprowadzania hasła, przycisku przesyłania i wszelkich towarzyszących wiadomości (np. „Wprowadź hasło, aby wyświetlić ten produkt”).
    *   `prodpswd/lib/searchTool/views/scripts.tpl`
        *   **Cel:** Ten szablon prawdopodobnie zawiera logikę JavaScript lub Smarty związaną z narzędziem wyszukiwania, prawdopodobnie używanym w konfiguracji administracyjnej do wybierania produktów do ochrony. Może zawierać wywołania AJAX lub dynamiczne możliwości filtrowania dla wyboru produktu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   `ps_prodpassword` (lub podobna): Oczekuje się, że ta niestandardowa tabela będzie przechowywać ID produktu (`id_product`) i powiązane hasło (`password`) dla każdego chronionego produktu. Jest tworzona podczas metody `install()` modułu.
    *   Rekordy konfiguracji w `ps_configuration`: Ogólne ustawienia modułu (jeśli istnieją) byłyby przechowywane tutaj.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionFrontControllerSetMedia` | Przed załadowaniem mediów (JS/CSS) kontrolera front-office. | Potencjalnie do ładowania niestandardowego JS/CSS dla formularza hasła, chociaż żadne nie są wymienione w dossier. |
| `displayHeader` | W sekcji `<head>` front-office. | Może być używany do metatagów lub warunkowego JS/CSS, ale nie jest wyraźnie używany do treści. |
| `displayRightColumn` | W prawej kolumnie front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu. |
| `displayLeftColumn` | W lewej kolumnie front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu. |
| `displayFooter` | W stopce front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu. |
| `actionProductControllerSetMedia` | Po ustawieniu mediów przez `ProductController`. | Może być używany do wstrzykiwania specyficznego JS/CSS dla strony produktu, ale mało prawdopodobne, biorąc pod uwagę nadpisanie. |
| `actionDispatcherBefore` | Przed wysłaniem kontrolera front-office. | `override/controllers/front/ProductController.php` działa efektywnie na tym etapie dla stron produktów. |
| `actionDispatcherAfter` | Po wysłaniu kontrolera front-office. | Mniej prawdopodobne dla podstawowej funkcjonalności tego modułu. |

Głównym mechanizmem tego modułu jest nadpisanie `ProductController`, które działa jako niejawny hook, przechwytując żądania, zanim standardowe hooki zostaną przetworzone dla treści strony produktu.

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Strony produktów chronione hasłem”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
