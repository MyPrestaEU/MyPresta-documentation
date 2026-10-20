---
title: "Wewnętrzne, niestandardowe pola produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wewnętrzne, niestandardowe pola produktu” od MyPresta.eu."
sidebar:
  label: "Wewnętrzne, niestandardowe pola produktu"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Internal, custom product fields na MyPresta.eu](https://mypresta.eu/modules/administration-tools/internal-custom-product-fields.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/internal-custom-product-fields/)
>
> ---


# Wewnętrzne, niestandardowe pola produktu

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Wewnętrzne, niestandardowe pola produktu)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

-   **Co robi to ustawienie:** Ten ekran przede wszystkim obsługuje wewnętrzny mechanizm aktualizacji modułu i podstawowe ustawienia.
-   **Efekt zmiany tego ustawienia:**
    -   `mypresta_updates`: To wewnętrzne ustawienie kontroluje, czy moduł sprawdza aktualizacje z MyPresta.eu.
    -   `update_`: Związane z procesem sprawdzania aktualizacji.
    -   `updatev_`: Związane z procesem sprawdzania aktualizacji.
    -   `PS_LANG_DEFAULT`: Jest to standardowy klucz konfiguracji PrestaShop i jest zazwyczaj odczytywany przez moduły w celu określenia domyślnego języka wyświetlania treści w Panelu administracyjnym. Nie jest to ustawienie, które zazwyczaj zmieniasz bezpośrednio w konfiguracji tego modułu.
-   **Zalecana wartość:** Dla `mypresta_updates` ogólnie zaleca się pozostawienie go włączonym, aby otrzymywać powiadomienia o nowych wersjach i poprawkach błędów. Pozostałe ustawienia są wewnętrzne i nie powinny być ręcznie zmieniane.
-   **Scenariusz/przykład dla sprzedawcy:** Zazwyczaj nie wchodzisz w interakcje z tymi konkretnymi ustawieniami bezpośrednio. Głównym celem tego ekranu jest zapewnienie strony docelowej dla modułu i upewnienie się, że jego mechanizm aktualizacji jest aktywny.

### 2.2 Dedykowany ekran administracyjny: Zarządzanie polami wewnętrznymi (Panel administracyjny > Katalog > Pola wewnętrzne)

Jest to główny ekran, na którym definiujesz i zarządzasz swoimi niestandardowymi wewnętrznymi polami produktu. Po zainstalowaniu modułu w menu „Katalog” w Panelu administracyjnym PrestaShop pojawi się nowa pozycja menu o nazwie „Pola wewnętrzne”.

-   **Nazwa ekranu i lokalizacja w menu:** **Katalog > Pola wewnętrzne**
-   **Dostępne działania i ustawienia:**
    -   **Widok siatki:** Ten ekran wyświetla listę wszystkich utworzonych niestandardowych pól wewnętrznych. Każdy wiersz pokazuje nazwę pola i jego status (włączone/wyłączone).
    -   **Przycisk „Dodaj nowe pole”:** Kliknij ten przycisk, aby utworzyć zupełnie nowe niestandardowe pole.
    -   **Akcje Edytuj/Usuń:** Dla każdego pola na liście zobaczysz przyciski akcji (ikona ołówka do edycji, ikona kosza na śmieci do usunięcia) do modyfikowania lub usuwania istniejących pól.
    -   **Formularz tworzenia/edycji pola:** Podczas dodawania lub edytowania pola zazwyczaj zobaczysz:
        -   **Nazwa pola:** (np. „SKU dostawcy”, „Lokalizacja magazynowa”, „Specjalne uwagi dotyczące obsługi”). Jest to etykieta, która pojawi się obok pola wprowadzania na stronie edycji produktu.
        -   **Przełącznik Aktywne/Nieaktywne:** Kontroluje, czy to niestandardowe pole jest aktualnie dostępne do użytku na stronach produktów. Jeśli jest nieaktywne, nie będzie wyświetlane.
        -   **Typ pola:** (np. Tekst, Obszar tekstowy, Liczba itp. - *na podstawie rzeczywistych możliwości modułu, na razie zakładamy tekst*). Określa typ pola wprowadzania.
        -   **Przycisk Zapisz:** Aby zapisać zmiany lub nowe pole.
-   **Efekt zmian:**
    -   **Dodanie nowego pola:** Po zapisaniu to nowe pole natychmiast pojawi się na stronie edycji *każdego* produktu w Twoim Panelu administracyjnym, gotowe do wprowadzenia danych.
    -   **Edycja pola:** Zmiany nazwy pola lub statusu natychmiast odzwierciedlą się na wszystkich stronach edycji produktów.
    -   **Usunięcie pola:** Pole zostanie usunięte ze wszystkich stron edycji produktów. **Bądź ostrożny:** Usunięcie pola spowoduje również usunięcie wszystkich danych wcześniej wprowadzonych do tego pola dla wszystkich produktów.
    -   **Aktywacja/dezaktywacja pola:** Aktywne pole jest widoczne na stronach produktów; nieaktywne pole jest ukryte.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Przejdź do **Katalog > Pola wewnętrzne**.
    2.  Kliknij „Dodaj nowe pole”, aby utworzyć pole takie jak „Numer części dostawcy” lub „Wewnętrzne uwagi”.
    3.  Ustaw nazwę pola i upewnij się, że jest aktywne.
    4.  Zapisz pole.
    5.  Teraz, gdy przejdziesz do **Katalog > Produkty** i edytujesz dowolny produkt, zobaczysz nowe pole wprowadzania dla „Numeru części dostawcy”, gdzie możesz wprowadzić specyficzne dane dla tego produktu.
    6.  Powtórz dla wszelkich innych wewnętrznych danych, które musisz śledzić.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | `mypresta_updates` | Włączone | Kontroluje sprawdzanie aktualizacji modułu. Pozostaw włączone dla aktualizacji. |
| Strona konfiguracji modułu | `update_`, `updatev_` | (Wewnętrzne) | Wewnętrzne zmienne mechanizmu aktualizacji. Nie modyfikuj. |
| Strona konfiguracji modułu | `PS_LANG_DEFAULT` | (Wewnętrzne) | Domyślny identyfikator języka PrestaShop. Tylko do odczytu. |
| Katalog > Pola wewnętrzne | **Dodaj nowe pole** | N/A | Tworzy nowe niestandardowe wewnętrzne pole produktu. |
| Katalog > Pola wewnętrzne | **Nazwa pola** | Zdefiniowane przez użytkownika | Etykieta dla niestandardowego pola na stronach edycji produktu. |
| Katalog > Pola wewnętrzne | **Aktywne/Nieaktywne** | Aktywne | Kontroluje widoczność pola na stronach edycji produktu. |
| Katalog > Pola wewnętrzne | **Akcje Edytuj/Usuń** | N/A | Modyfikuj lub usuwaj istniejące niestandardowe pola. Usunięcie usuwa wszystkie powiązane dane. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Utworzyłem nowe pole, ale nie widzę go na stronie edycji produktu.**
O:
1.  Przejdź do **Katalog > Pola wewnętrzne** i upewnij się, że utworzone pole jest oznaczone jako „Aktywne”.
2.  Wyczyść pamięć podręczną PrestaShop: Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
3.  Spróbuj ponownie edytować produkt. Jeśli nadal się nie pojawia, upewnij się, że Twoja wersja PrestaShop jest w pełni kompatybilna z modułem.

**P: Czy mogę wyświetlać te niestandardowe pola w moim front-office dla klientów?**
O: Nie, ten moduł jest specjalnie zaprojektowany wyłącznie do użytku wewnętrznego w Panelu administracyjnym. Dane wprowadzone do tych pól nie są przeznaczone do wyświetlania klientom. Jeśli potrzebujesz niestandardowych pól dla front-office, potrzebowałbyś innego typu modułu lub niestandardowego rozwoju.

**P: Co się stanie, jeśli usunę niestandardowe pole?**
O: Po usunięciu niestandardowego pola z **Katalog > Pola wewnętrzne**, wszystkie dane, które wprowadziłeś do tego konkretnego pola dla *wszystkich* Twoich produktów, zostaną trwale usunięte. Zawsze upewnij się, że nie potrzebujesz już danych przed usunięciem pola.

**P: Moduł wydaje się powodować problemy z moim niestandardowym motywem. Co powinienem zrobić?**
O:
1.  Najpierw wyczyść pamięć podręczną Smarty (jak wspomniano powyżej).
2.  Jeśli problem nadal występuje, spróbuj tymczasowo wyłączyć inne moduły jeden po drugim, aby sprawdzić, czy nie ma konfliktu.
3.  Sprawdź konsolę programisty przeglądarki (F12) pod kątem błędów JavaScript.
4.  Jeśli nadal nie możesz tego rozwiązać, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu i konkretny problem.

**P: Jak przetłumaczyć nazwy moich niestandardowych pól na różne języki?**
O: Moduł powinien umożliwiać zdefiniowanie nazwy pola dla każdego języka włączonego w Twoim sklepie PrestaShop podczas tworzenia lub edycji pola. Poszukaj zakładek językowych obok pola wprowadzania „Nazwa pola” w formularzu tworzenia/edycji pola.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury
Moduł „Wewnętrzne, niestandardowe pola produktu” rozszerza możliwości zarządzania produktami w PrestaShop poprzez wstrzykiwanie niestandardowych pól na stronę edycji produktu w Panelu administracyjnym. Wykorzystuje wzorzec MVC PrestaShop, głównie poprzez kontroler administracyjny do zarządzania definicjami niestandardowych pól i nadpisywanie w celu integracji tych pól z istniejącymi formularzami produktów. Dane są przechowywane w dedykowanej tabeli bazy danych, a JavaScript jest używany do dynamicznej manipulacji formularzami.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Ten moduł nie posiada dedykowanych kontrolerów front-office, ponieważ jego funkcjonalność jest całkowicie zorientowana na Panel administracyjny. Haki front-office są prawdopodobnie używane do ogólnej konfiguracji modułu lub do zapewnienia braku konfliktów z front-office.

-   **Kontrolery administracyjne Back-Office**:
    *   `aipf/controllers/admin/AdminInternalFields.php`
        *   **Nazwa klasy**: `AdminInternalFieldsController` (rozszerza `ModuleAdminController`)
        *   **Nazwa zakładki**: „Pola wewnętrzne” (w menu Katalog)
        *   **Odpowiedzialność**: Jest to główny kontroler do zarządzania definicjami niestandardowych wewnętrznych pól produktu. Obsługuje listowanie, tworzenie, edycję i usuwanie tych pól. Wykorzystuje `HelperList` PrestaShop do widoku siatki i `HelperForm` do formularzy dodawania/edycji. Współpracuje z niestandardowym `ObjectModel` modułu (prawdopodobnie `AipfInternalField`) w celu utrwalania definicji pól.
    *   `aipf/controllers/admin/index.php`
        *   **Odpowiedzialność**: Jest to standardowy pusty plik `index.php` często umieszczany w katalogach w celu zapobiegania listowaniu katalogów na serwerach WWW, zwiększając bezpieczeństwo. Nie zawiera żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł wykorzystuje nadpisywanie w celu integracji swojej funkcjonalności z rdzeniem PrestaShop.

-   `aipf/override/classes/controller/Controller.php`
    *   **Nazwa klasy**: `Controller` (nadpisuje podstawową klasę `Controller`)
    *   **Odpowiedzialność**: To nadpisanie jest prawdopodobnie używane do wstrzykiwania specyficznego dla modułu JavaScript lub CSS globalnie lub warunkowo, lub do modyfikowania zachowania wszystkich kontrolerów. Biorąc pod uwagę cel modułu, może być używane do zapewnienia załadowania niezbędnych zasobów dla strony produktu lub do obsługi specyficznych żądań AJAX związanych z niestandardowymi polami.
-   `aipf/override/classes/controller/index.php`
    *   **Odpowiedzialność**: Zastępczy plik bezpieczeństwa.
-   `aipf/override/classes/index.php`
    *   **Odpowiedzialność**: Zastępczy plik bezpieczeństwa.

*Uwaga: Na podstawie opisu powinna istnieć klasa `ObjectModel` dla `AipfInternalField` (np. `classes/AipfInternalField.php`) do zarządzania definicjami niestandardowych pól i potencjalnie inna do zarządzania rzeczywistymi danymi produktu dla tych pól. Nie jest to jawnie wymienione w inwentarzu, ale jest implikowane przez funkcjonalność.*

### 4.4 Zasoby JavaScript (`views/js/`)

-   `aipf/lib/js/admin/aipf-configuration.js`
    *   **Zakres**: Panel administracyjny (konfiguracja modułu).
    *   **Cel**: Prawdopodobnie obsługuje specyficzną logikę JavaScript dla głównego ekranu konfiguracji modułu, taką jak sprawdzanie aktualizacji lub proste interakcje z formularzami.
-   `aipf/lib/js/admin/aipf.js`
    *   **Zakres**: Panel administracyjny (ogólny panel administracyjny, potencjalnie strona produktu).
    *   **Cel**: Zawiera podstawową logikę JavaScript dla modułu w Panelu administracyjnym. Może to obejmować wywołania AJAX do zapisywania danych pól produktu, dynamiczne renderowanie pól na stronie produktu lub interakcje z `AdminInternalFieldsController`.
-   `aipf/lib/js/front/aipf-front.js`
    *   **Zakres**: Front-office.
    *   **Cel**: Chociaż moduł jest przeznaczony do użytku wewnętrznego, ten plik może istnieć jako zastępczy lub do obsługi bardzo specyficznych, niewizualnych zadań front-office, takich jak zapewnienie braku konfliktów z innymi skryptami, lub dla potencjalnej przyszłej funkcji, która nie została zaimplementowana. Biorąc pod uwagę opis modułu, jego wpływ na front-office powinien być minimalny lub żaden.
-   `aipf/views/js/AdminInternalFields.js`
    *   **Zakres**: Panel administracyjny (ekran AdminInternalFieldsController).
    *   **Cel**: Specyficzny JavaScript dla ekranu zarządzania „Katalog > Pola wewnętrzne”. Obsługiwałby interakcje w siatce, walidację formularzy dla dodawania/edycji pól oraz żądania AJAX związane z zarządzaniem polami.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `aipf/lib/css/aipf.css`
    *   **Zakres**: Głównie Panel administracyjny, potencjalnie minimalny front-office.
    *   **Cel**: Zapewnia stylizację niestandardowych pól na stronie edycji produktu, ekranie zarządzania „Pola wewnętrzne” oraz wszelkich innych elementów interfejsu użytkownika wprowadzonych przez moduł w Panelu administracyjnym. Może również zawierać style resetujące lub bardzo podstawowe reguły, które mogłyby mieć zastosowanie do front-office w celu zapobiegania konfliktom, chociaż jego głównym celem jest interfejs administracyjny.
    *   **Kluczowe selektory klas CSS**: Programiści mogą szukać klas takich jak `.aipf-field-container`, `.aipf-input`, `.aipf-label`, aby nadpisać lub dostosować wygląd niestandardowych pól.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**: Nie są jawnie wymienione, ale moduł prawdopodobnie używałby szablonów dla haków takich jak `displayAdminProductsExtra` lub `displayAdminProductsMainStepLeftColumnMiddle` w celu wstrzyknięcia niestandardowych pól na stronę edycji produktu.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `aipf/views/templates/admin/combination.tpl`
        *   **Cel**: Ten szablon jest specjalnie zaprojektowany do wstrzykiwania niestandardowych pól wewnętrznych do interfejsu edycji kombinacji produktu (wariantu) w Panelu administracyjnym. Renderowałby pola wprowadzania dla niestandardowych danych związanych z każdą kombinacją produktu. Jest to kluczowe dla produktów z atrybutami (takimi jak rozmiar, kolor), gdzie każda kombinacja może wymagać własnych wewnętrznych notatek lub identyfikatorów.
-   **Szablony front-office (`views/templates/front/`)**: Żadne jawnie wymienione, co jest zgodne z charakterem modułu tylko dla Panelu administracyjnego.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:
    *   `ps_aipf_internal_field`: Ta tabela przechowywałaby definicje niestandardowych pól wewnętrznych (np. `id_aipf_internal_field`, `name`, `active`, `field_type`).
    *   `ps_aipf_internal_field_lang`: Jeśli nazwy pól są tłumaczone, ta tabela przechowywałaby nazwy specyficzne dla języka dla niestandardowych pól (np. `id_aipf_internal_field`, `id_lang`, `name`).
    *   `ps_aipf_product_data`: Ta tabela przechowywałaby rzeczywiste dane wprowadzone przez sprzedawcę dla każdego niestandardowego pola, powiązane z konkretnym produktem i potencjalnie konkretną kombinacją (np. `id_aipf_internal_field`, `id_product`, `id_product_attribute` (jeśli dotyczy), `value`).
    *   `ps_configuration`: Standardowa tabela PrestaShop używana do przechowywania wartości konfiguracji modułu, takich jak `mypresta_updates`, `update_`, `updatev_`.

-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Zakres | Czas wykonania | Cel techniczny |
|---|---|---|---|
| `actionAjaxDieProductControllerdisplayAjaxRefreshBefore` | Front/Admin | Przed odpowiedzią AJAX w ProductController | Potencjalnie do wstępnego przetwarzania żądań AJAX związanych z danymi produktu, zapewniając uwzględnienie niestandardowych pól. |
| `actionOutputHTMLBefore` | Front/Admin | Przed wyjściem HTML | Ogólny hak, może być używany do globalnego wstrzykiwania zasobów lub wczesnego przetwarzania. |
| `ActionAfterUpdateCombinationFormFormHandler` | Admin | Po zaktualizowaniu formularza kombinacji | Do zapisywania lub przetwarzania niestandardowych danych pól związanych z kombinacjami produktów. |
| `actionAdminControllerSetMedia` | Admin | Gdy kontroler administracyjny ustawia media | Do wstrzykiwania specyficznego dla modułu CSS/JS na strony Panelu administracyjnego (np. strona edycji produktu, konfiguracja modułu). |
| `actionCombinationFormFormBuilderModifier` | Admin | Gdy modyfikowany jest konstruktor formularza kombinacji | Do dynamicznego dodawania niestandardowych pól do formularza kombinacji produktu. |
| `actionProductUpdate` | Admin | Po zaktualizowaniu produktu | Do zapisywania lub przetwarzania niestandardowych danych pól po zapisaniu produktu. |
| `ActionFrontControllerSetMedia` | Front | Gdy kontroler front-office ustawia media | Do wstrzykiwania specyficznego dla modułu CSS/JS na strony Front-Office (jeśli potrzebne, choć mało prawdopodobne dla tego modułu). |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wewnętrzne, niestandardowe pola produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
