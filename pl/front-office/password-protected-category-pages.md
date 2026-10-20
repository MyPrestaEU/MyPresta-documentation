---
title: "Strony kategorii chronione hasłem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Strony kategorii chronione hasłem” od MyPresta.eu."
sidebar:
  label: "Strony kategorii chronione hasłem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Password protected category pages na MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-category-pages.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/password-protected-category-pages/)
>
> ---


# Strony kategorii chronione hasłem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego głównych ustawień. Ten ekran zawiera ogólne opcje zarządzania modułem.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera standardowe ustawienia modułów MyPresta.eu związane z aktualizacjami i licencjonowaniem. Zapewnia, że Twój moduł jest aktualny i prawidłowo licencjonowany.
-   **Wpływ zmiany tego ustawienia:**
    -   *`mypresta_updates`*: To ustawienie kontroluje, czy moduł automatycznie sprawdza dostępność aktualizacji. Utrzymywanie go włączonym zapewnia powiadomienia o nowych wersjach.
    -   *`update_` i `updatev_`*: Są to wewnętrzne ustawienia używane przez moduł do zarządzania sprawdzaniem aktualizacji i informacjami o wersji. Zazwyczaj nie musisz z nimi bezpośrednio wchodzić w interakcje.
-   **Zalecana wartość:** Utrzymuj `mypresta_updates` włączone, aby otrzymywać ważne aktualizacje i poprawki błędów.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz mieć pewność, że Twój moduł zawsze ma najnowsze funkcje i poprawki bezpieczeństwa, pozostaw włączone sprawdzanie aktualizacji. Jeśli masz wysoce spersonalizowany sklep i wolisz ręcznie kontrolować aktualizacje po dokładnym przetestowaniu, możesz je wyłączyć, ale ogólnie nie jest to zalecane dla większości sprzedawców.

### 2.2 Dedykowany ekran administracyjny: Hasła kategorii (Panel administracyjny > Katalog > Hasła kategorii)

Jest to główny ekran zarządzania do ustawiania i zarządzania hasłami dla Twoich kategorii.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran znajdziesz, przechodząc do **Katalog > Hasła kategorii** w menu Panelu administracyjnego PrestaShop.
-   **Dostępne działania i ustawienia:**
    -   **Lista kategorii:** Ten ekran wyświetla listę wszystkich Twoich kategorii. Dla każdej kategorii zobaczysz, czy jest ona aktualnie chroniona hasłem i ile haseł jest do niej przypisanych.
    -   **Dodaj/Edytuj hasła:** Dla każdej kategorii możesz kliknąć przycisk „Edytuj” lub „Zarządzaj hasłami” (lub podobną ikonę), aby otworzyć dedykowany interfejs. Tutaj możesz:
        -   **Wybierz kategorię:** Wybierz konkretną kategorię, którą chcesz chronić.
        -   **Dodaj nowe hasło:** Wprowadź nowe hasło dla wybranej kategorii. Możesz dodać wiele haseł dla jednej kategorii. Jest to przydatne, jeśli chcesz nadać różne kody dostępu różnym grupom klientów (np. „VIP123” dla klientów premium, „HURT456” dla partnerów B2B).
        -   **Usuń hasło:** Usuń istniejące hasła.
        -   **Włącz/Wyłącz ochronę:** Może być dostępny przełącznik lub pole wyboru, aby szybko włączyć lub wyłączyć ochronę hasłem dla kategorii bez usuwania wszystkich jej haseł.
-   **Wpływ zmian:**
    -   **Dodanie hasła:** Wybrana kategoria natychmiast stanie się chroniona hasłem w front-office. Klienci będą musieli wprowadzić jedno z przypisanych haseł, aby wyświetlić jej produkty.
    -   **Usunięcie hasła:** To konkretne hasło nie będzie już udzielać dostępu. Jeśli było to jedyne hasło dla kategorii, kategoria może stać się niezabezpieczona (w zależności od dokładnej logiki modułu, bezpieczniej jest jawnie wyłączyć ochronę, jeśli chcesz, aby była otwarta).
    -   **Wyłączenie ochrony:** Kategoria ponownie stanie się publicznie dostępna, a klienci zobaczą jej produkty bez potrzeby podawania hasła.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Przejdź do **Katalog > Hasła kategorii**.
    2.  Zidentyfikuj kategorię, którą chcesz chronić.
    3.  Kliknij ikonę „Zarządzaj hasłami” lub „Edytuj” obok niej.
    4.  Na nowym ekranie dodaj jedno lub więcej haseł. Pamiętaj, że każde dodane hasło udzieli dostępu.
    5.  Zapisz zmiany.
    6.  Aby usunąć ochronę, usuń wszystkie hasła dla tej kategorii lub użyj przełącznika „Włącz/Wyłącz”, jeśli jest dostępny.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | `mypresta_updates` | Włączone | Kontroluje automatyczne sprawdzanie aktualizacji modułu. Pozostaw włączone dla najnowszych funkcji i bezpieczeństwa. |
| Strona konfiguracji modułu | `update_`, `updatev_` | (Wewnętrzne) | Wewnętrzne ustawienia do zarządzania aktualizacjami. Nie wymaga interakcji sprzedawcy. |
| Hasła kategorii (Katalog > Hasła kategorii) | Lista kategorii | N/A | Przegląd wszystkich kategorii i ich statusu ochrony hasłem. |
| Hasła kategorii (Katalog > Hasła kategorii) | Dodaj/Edytuj hasła | N/A | Umożliwia dodawanie, edytowanie lub usuwanie haseł dla konkretnych kategorii. Obsługiwane są wielokrotne hasła dla jednej kategorii. |
| Hasła kategorii (Katalog > Hasła kategorii) | Włącz/Wyłącz ochronę | N/A | Włącza lub wyłącza ochronę hasłem dla kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem hasło, ale kategoria jest nadal widoczna bez niego. Co jest nie tak?**
O1:

-   **Wyczyść pamięć podręczną:** Najczęstszą przyczyną jest buforowanie. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” i „Wyczyść pamięć podręczną” dla wszystkich pamięci podręcznych).
-   **Sprawdź status kategorii:** Upewnij się, że sama kategoria jest aktywna i widoczna w Twoim sklepie.
-   **Zweryfikuj wprowadzenie hasła:** Dokładnie sprawdź, czy poprawnie wprowadziłeś i zapisałeś hasło(a) w sekcji **Katalog > Hasła kategorii**.
-   **Pozycja modułu:** Upewnij się, że moduł jest prawidłowo podpięty. Chociaż moduł obsługuje to automatycznie, jeśli masz mocno spersonalizowane szablony, czasami hooki mogą zostać nadpisane.

**P2: Czy mogę mieć wiele haseł do jednej kategorii?**
O2: Tak! Ten moduł wyraźnie obsługuje nieograniczoną liczbę haseł dla jednej kategorii. Jest to przydatne do nadawania różnych kodów dostępu różnym grupom (np. hasło „VIP”, hasło „Hurt”).

**P3: Co się stanie, jeśli klient spróbuje uzyskać dostęp do produktu bezpośrednio z chronionej kategorii za pomocą jego adresu URL?**
O3: Jeśli produkt należy do kategorii chronionej hasłem, dostęp do strony produktu bezpośrednio będzie nadal wymagał wcześniejszego wprowadzenia hasła kategorii. Moduł zapewnia, że kontekst kategorii jest przestrzegany, uniemożliwiając bezpośredni dostęp do produktów w zabezpieczonej kategorii bez uwierzytelnienia.

**P4: Jak usunąć ochronę hasłem z kategorii?**
O4: Przejdź do **Katalog > Hasła kategorii**. Znajdź kategorię, którą chcesz odblokować. Możesz albo usunąć wszystkie hasła powiązane z tą kategorią, albo, jeśli istnieje jawny przełącznik „Włącz/Wyłącz” dla ochrony kategorii, użyj go. Po usunięciu wszystkich haseł lub wyłączeniu ochrony kategoria ponownie stanie się publicznie dostępna.

**P5: Formularz hasła nie wygląda dobrze na moim niestandardowym szablonie. Jak to naprawić?**
O5: Moduł używa standardowego szablonowania PrestaShop i CSS. Jeśli nie wygląda to dobrze, prawdopodobnie jest to konflikt CSS z Twoim niestandardowym szablonem.

-   **Zbadaj element:** Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać elementy formularza hasła. Poszukaj sprzecznych reguł CSS z Twojego szablonu.
-   **Niestandardowy CSS:** Możesz dodać niestandardowy CSS do pliku `custom.css` swojego szablonu (lub podobnego), aby nadpisać domyślne style modułu i dopasować je do swojego szablonu.
-   **Skontaktuj się z pomocą techniczną:** Jeśli nie czujesz się komfortowo z CSS, skontaktuj się z deweloperem swojego szablonu lub pomocą techniczną MyPresta.eu w celu uzyskania pomocy.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Strony kategorii chronione hasłem” integruje się z architekturą MVC PrestaShop głównie poprzez nadpisywanie podstawowego `CategoryController` w celu przechwytywania żądań do stron kategorii. Wykorzystuje dedykowany kontroler administracyjny (`AdminCatPasswordController`) do zarządzania powiązaniami kategorii z hasłami, przechowując je w niestandardowej tabeli bazy danych. Wyświetlanie w front-office jest obsługiwane za pomocą niestandardowego szablonu Smarty dla formularza wprowadzania hasła.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `catpswd/override/controllers/front/listing/CategoryController.php`
        -   **Nazwa klasy:** `CategoryController` (nadpisuje podstawowy `CategoryController` PrestaShop)
        -   **Klasa nadrzędna:** `CategoryControllerCore`
        -   **Odpowiedzialność:** To nadpisanie jest rdzeniem funkcjonalności front-office modułu. Przechwytuje żądania do stron kategorii. Przed wyświetleniem rzeczywistej zawartości kategorii sprawdza, czy kategoria jest chroniona hasłem. Jeśli tak, a użytkownik nie wprowadził jeszcze poprawnego hasła (lub sesja wygasła), renderuje formularz wprowadzania hasła (`category.tpl`) zamiast standardowej strony kategorii. Obsługuje przesyłanie formularza hasła, waliduje wprowadzone hasło i ustawia zmienną sesji po pomyślnym uwierzytelnieniu.
    -   `catpswd/override/controllers/front/listing/index.php`
        -   **Odpowiedzialność:** Jest to standardowy plik `index.php` PrestaShop w katalogu nadpisywania, zazwyczaj używany do zapobiegania bezpośredniemu listowaniu katalogów i zapewnienia prawidłowego ładowania modułu. Sam w sobie nie zawiera aktywnej logiki kontrolera.
-   **Kontrolery administracyjne Back-Office**:

    -   `catpswd/controllers/admin/AdminCatPasswordController.php`
        -   **Nazwa zakładki:** „Hasła kategorii” (w menu Katalog)
        -   **Zarządzana encja:** `CatPassword` (chociaż nie ma jawnie wymienionego `ObjectModel`, ten kontroler zarządza relacjami kategorii z hasłami, prawdopodobnie bezpośrednio wchodząc w interakcje z bazą danych lub klasą pomocniczą).
        -   **Odpowiedzialność:** Ten kontroler zapewnia interfejs w Panelu administracyjnym PrestaShop dla administratorów do zarządzania ochroną hasłem dla kategorii. Wyświetla listę kategorii, umożliwia dodawanie wielu haseł do kategorii i ich usuwanie. Obsługuje operacje CRUD dla danych kategorii-hasła.
    -   `catpswd/controllers/admin/index.php`
        -   **Odpowiedzialność:** Podobnie jak `index.php` w front-office, ten plik zapobiega bezpośredniemu listowaniu katalogu dla kontrolerów administracyjnych.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak jawnych klas w katalogu `classes/`. Sugeruje to, że `AdminCatPasswordController` prawdopodobnie obsługuje interakcje z bazą danych bezpośrednio lub używa prostej funkcji pomocniczej w głównym pliku modułu (`catpswd.php`) do zarządzania danymi, zamiast dedykowanego `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu wskazuje brak konkretnych plików JavaScript. Przesyłanie i walidacja hasła są prawdopodobnie obsługiwane za pomocą standardowego przesyłania formularza HTML i przetwarzania po stronie serwera w ramach nadpisania `CategoryController`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu wskazuje brak konkretnych plików CSS. Stylizacja formularza wprowadzania hasła jest prawdopodobnie minimalna i opiera się na podstawowych stylach domyślnego szablonu PrestaShop. Deweloperzy, którzy chcą dostosować wygląd, powinni celować w elementy formularza w szablonie `category.tpl` za pomocą niestandardowego CSS swojego szablonu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `catpswd/lib/searchTool/views/scripts.tpl`
        -   **Hook:** Prawdopodobnie używany w `displayHeader` lub `actionAdminControllerSetMedia` (jeśli zawiera dołączenia JS/CSS dla narzędzia wyszukiwania).
        -   **Wyjście:** Ten szablon prawdopodobnie zawiera dołączenia JavaScript lub CSS, być może dla narzędzia wyszukiwania używanego w interfejsie administracyjnym modułu lub dla funkcjonalności front-office.
-   **Szablony Front-office (`views/templates/front/`)**:
    -   `catpswd/views/templates/front/category.tpl`
        -   **Cel:** Jest to szablon renderowany przez nadpisany `CategoryController`, gdy do chronionej hasłem kategorii uzyskuje się dostęp bez uwierzytelnienia. Wyświetla formularz wprowadzania hasła klientowi. Zazwyczaj zawiera pola na hasło, przycisk przesyłania i komunikaty o udanych lub nieudanych próbach.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   `ps_catpassword`: Ta niestandardowa tabela jest tworzona przez moduł podczas instalacji. Przechowuje powiązania między identyfikatorami kategorii a ich odpowiednimi hasłami.
        -   **Kolumny (oczekiwane):** `id_catpassword` (klucz podstawowy), `id_category` (klucz obcy do `ps_category`), `password` (ciąg hasła w postaci zaszyfrowanej lub jawnej).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używany do dołączania globalnych zasobów CSS lub JS, lub do ustawiania metatagów związanych z funkcjonalnością modułu. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany i ustawiane są jego media (JS/CSS). | Używany przez moduł do wstrzykiwania jego specyficznych plików JavaScript i CSS do Back Office dla `AdminCatPasswordController` lub innych stron administracyjnych, gdzie potrzebne są zasoby modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i profesjonalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i zapewnienie płynnego działania Twojego modułu.
