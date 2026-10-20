---
title: "Dodatkowe pola wyboru podczas rejestracji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Dodatkowe pola wyboru podczas rejestracji” od MyPresta.eu."
sidebar:
  label: "Dodatkowe pola wyboru podczas rejestracji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Additional checkboxes during register na MyPresta.eu](https://mypresta.eu/modules/front-office-features/additional-checkboxes-during-register.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/additional-checkboxes-during-register/)
>
> ---


# Dodatkowe pola wyboru podczas rejestracji

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny po kliknięciu „Konfiguruj” po instalacji.

-   **Co robi to ustawienie:** Ten ekran głównie obsługuje ogólne ustawienia modułu i pozwala zarządzać aktualizacjami.
-   **Wpływ zmiany tego ustawienia:**
    -   `mypresta_updates`: Jest to ogólne ustawienie dla modułów MyPresta.eu do sprawdzania aktualizacji.
        -   *Gdy włączone:* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowych wersji, powiadamiając Cię w Panelu administracyjnym, jeśli dostępna jest aktualizacja. Pomaga to utrzymać moduł bezpieczny i aktualny z najnowszymi funkcjami i poprawkami błędów.
        -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał aktualizacji. Musiałbyś ręcznie sprawdzać swoje konto MyPresta.eu pod kątem nowych wersji.
    -   `update_`: To ustawienie jest związane z funkcją sprawdzania aktualizacji.
    -   `updatev_`: To ustawienie jest związane z funkcją sprawdzania aktualizacji.
-   **Zalecana wartość:** Dla `mypresta_updates` **zaleca się pozostawienie go włączonym**, aby zawsze być informowanym o najnowszych wersjach modułu. Pozostałe dwa ustawienia są wewnętrzne i zazwyczaj powinny pozostać bez zmian.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Twój sklep zawsze działa na najbardziej bezpiecznej i bogatej w funkcje wersji modułu. Włączenie sprawdzania aktualizacji oznacza, że zostaniesz powiadomiony bezpośrednio w panelu administracyjnym PrestaShop, gdy zostanie wydana nowa wersja, co ułatwia bycie na bieżąco.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminAddTosListController (Panel administracyjny > Moduły > Dodatkowe pola wyboru > Lista pól wyboru)

Ten ekran służy do definiowania i zarządzania wszystkimi indywidualnymi polami wyboru, które pojawią się podczas rejestracji klienta.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran znajdziesz, przechodząc do **Moduły > Dodatkowe pola wyboru > Lista pól wyboru** w menu Panelu administracyjnego PrestaShop.
-   **Dostępne akcje i ustawienia:**
    -   **Lista pól wyboru:** Ta strona wyświetla tabelę wszystkich niestandardowych pól wyboru, które utworzyłeś. Każdy wiersz pokazuje nazwę pola wyboru, czy jest wymagane, jego status (włączone/wyłączone) i jego pozycję.
    -   **Dodaj nowe pole wyboru:** Będzie przycisk (np. „Dodaj nowe pole wyboru” lub ikona plusa) do utworzenia zupełnie nowego pola wyboru. Podczas dodawania/edycji pola wyboru zazwyczaj konfigurujesz:
        -   **Nazwa/Etykieta:** Tekst, który pojawia się obok pola wyboru (np. „Zgadzam się z Polityką Prywatności”). Powinien być jasny i zwięzły.
        -   **Link (Opcjonalnie):** Adres URL do strony (np. Twojej strony Polityki Prywatności, konkretnej strony z warunkami), którą klienci mogą kliknąć, aby przeczytać pełne szczegóły. Jest to kluczowe dla przejrzystości.
        -   **Wymagane:** Przełącznik (Tak/Nie) określający, czy klient *musi* zaznaczyć to pole, aby zakończyć rejestrację.
            -   *Gdy włączone (Tak):* Klienci nie mogą się zarejestrować bez zaznaczenia tego pola. Jest to idealne dla podstawowych umów prawnych.
            -   *Gdy wyłączone (Nie):* Klienci mogą się zarejestrować, nawet jeśli nie zaznaczą tego pola. Jest to odpowiednie dla opcjonalnych zgód, takich jak subskrypcje newslettera.
        -   **Aktywne:** Przełącznik (Tak/Nie) do włączania lub wyłączania wyświetlania pola wyboru w front-office.
            -   *Gdy włączone (Tak):* Pole wyboru będzie widoczne w formularzu rejestracyjnym.
            -   *Gdy wyłączone (Nie):* Pole wyboru będzie ukryte w formularzu rejestracyjnym, ale zachowane w Panelu administracyjnym do przyszłego użytku.
        -   **Pozycja:** Liczba całkowita kontrolująca kolejność, w jakiej pola wyboru pojawiają się w formularzu rejestracyjnym. Niższe liczby pojawiają się wyżej.
    -   **Edytuj/Usuń:** Każde pole wyboru na liście będzie miało akcje do edycji jego szczegółów lub całkowitego usunięcia.
-   **Wpływ zmian:**
    -   **Dodanie nowego pola wyboru:** Nowe pole wyboru natychmiast pojawi się w formularzu rejestracyjnym klienta (jeśli jest aktywne) i na stronie „Moje dane osobowe” klienta.
    -   **Edycja pola wyboru:** Zmiany w etykiecie, linku, statusie wymaganym lub statusie aktywnym zostaną natychmiast odzwierciedlone w front-office.
    -   **Usunięcie pola wyboru:** Pole wyboru zostanie usunięte z front-office. Istniejące zgody klientów dla tego konkretnego pola wyboru pozostaną zarejestrowane w historii, ale nowe zgody nie będą mogły być udzielane.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zidentyfikuj potrzeby zgody:** Przed dodaniem określ, jakie konkretne zgody potrzebujesz (np. Polityka Prywatności, Newsletter, Weryfikacja wieku, specyficzne warunki usługi).
    2.  **Utwórz strony treści:** Upewnij się, że masz dedykowane strony CMS (lub linki zewnętrzne) dla każdej polityki lub warunku, do którego chcesz linkować.
    3.  **Dodaj pola wyboru:** Przejdź do „Lista pól wyboru” i kliknij „Dodaj nowe pole wyboru”. Wypełnij etykietę, link, ustaw jako wymagane/opcjonalne i aktywuj.
    4.  **Uporządkuj pola wyboru:** Użyj pola „Pozycja”, aby ułożyć je logicznie.
    5.  **Przejrzyj Front-Office:** Zawsze testuj proces rejestracji w front-office swojego sklepu po wprowadzeniu zmian, aby upewnić się, że wszystko wyświetla się i działa zgodnie z oczekiwaniami.

#### AdminAddTosHistoryController (Panel administracyjny > Moduły > Dodatkowe pola wyboru > Historia)

Ten ekran zapewnia historyczny zapis zgód klientów dla każdego pola wyboru.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran znajdziesz, przechodząc do **Moduły > Dodatkowe pola wyboru > Historia** w menu Panelu administracyjnego PrestaShop.
-   **Dostępne akcje i ustawienia:**
    -   **Tabela historii zgód:** Ta strona wyświetla szczegółowy dziennik, kiedy każdy klient zgodził się (lub nie zgodził) na konkretne pole wyboru.
    -   **Kolumny zazwyczaj zawierają:**
        -   **Nazwa klienta:** Nazwa klienta.
        -   **Nazwa pola wyboru:** Etykieta pola wyboru, z którym wchodzili w interakcję.
        -   **Status zgody:** Czy zaakceptowali (zaznaczyli) czy odrzucili (odznaczyli) pole.
        -   **Data:** Znacznik czasu, kiedy zgoda została zarejestrowana.
        -   **Adres IP:** Adres IP, z którego zgoda została udzielona (ważne dla zgodności z prawem).
    -   **Filtrowanie/Wyszukiwanie:** Zazwyczaj możesz filtrować tę listę według klienta, pola wyboru lub zakresu dat, aby znaleźć konkretne rekordy zgód.
-   **Wpływ zmian:** Ten ekran służy głównie do przeglądania i audytu. Nie możesz bezpośrednio modyfikować rekordów zgód tutaj, ponieważ reprezentują one fakty historyczne.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   **Audyt i zgodność:** Użyj tego ekranu do weryfikacji zgód klientów w przypadku sporów lub do wewnętrznych audytów zgodności.
    -   **Żądania dotyczące prywatności danych:** Jeśli klient prosi o informacje o danych, które posiadasz lub na które wyraził zgodę, ta historia zapewnia jasny zapis.

#### index.php (addtos/controllers/admin/index.php)

Ten plik jest plikiem zastępczym i zazwyczaj zawiera proste `header('Location: ../../../index.php?controller=AdminHome');` lub podobne przekierowanie, aby zapobiec bezpośredniemu dostępowi do katalogu. Nie stanowi on konfigurowalnego ekranu dla sprzedawcy.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Sprawdzanie aktualizacji MyPresta.eu | Włączone | Powiadamia o nowych wersjach modułu dla bezpieczeństwa i funkcji. |
| **Lista pól wyboru** | Nazwa/Etykieta pola wyboru | N/A (definiowane przez użytkownika) | Widoczny tekst obok pola wyboru w formularzu rejestracyjnym. |
| **Lista pól wyboru** | Link (URL) | N/A (definiowane przez użytkownika) | URL do strony z polityką; dostarcza szczegółów dla pola wyboru. |
| **Lista pól wyboru** | Wymagane | Nie (Opcjonalne) | Jeśli Tak, klient *musi* zaznaczyć, aby się zarejestrować. Jeśli Nie, jest opcjonalne. |
| **Lista pól wyboru** | Aktywne | Tak | Jeśli Tak, pole wyboru jest widoczne w front-office. Jeśli Nie, jest ukryte. |
| **Lista pól wyboru** | Pozycja | N/A (definiowane przez użytkownika) | Określa kolejność wyświetlania pól wyboru w formularzu. |
| **Historia** | Nazwa klienta | N/A (tylko podgląd) | Wyświetla, który klient udzielił zgody. |
| **Historia** | Nazwa pola wyboru | N/A (tylko podgląd) | Wyświetla, z którym polem wyboru wchodzono w interakcję. |
| **Historia** | Status zgody | N/A (tylko podgląd) | Pokazuje, czy klient zaakceptował, czy odrzucił. |
| **Historia** | Data | N/A (tylko podgląd) | Znacznik czasu rekordu zgody. |
| **Historia** | Adres IP | N/A (tylko podgląd) | Adres IP, z którego udzielono zgody. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Dodałem nowe pole wyboru, ale nie pojawia się na stronie rejestracji.**
**O1:**

-   **Sprawdź status „Aktywne”:** Przejdź do **Moduły > Dodatkowe pola wyboru > Lista pól wyboru** i upewnij się, że przełącznik „Aktywne” dla Twojego pola wyboru jest ustawiony na „Tak”.
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się nowej zawartości. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”.
-   **Pozycja modułu:** Upewnij się, że moduł jest poprawnie podpięty. Chociaż moduł zazwyczaj obsługuje to automatycznie, jeśli dokonałeś modyfikacji motywu, warto sprawdzić hooki modułu w **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach). Moduł zazwyczaj używa `displayAdditionalCustomerFormFields` lub podobnych hooków.

**P2: Tekst mojego pola wyboru jest za długi i źle wygląda na urządzeniach mobilnych.**
**O2:**

-   **Zachowaj zwięzłość:** Spróbuj skrócić etykietę pola wyboru do jej istoty (np. „Zgadzam się z Polityką Prywatności” zamiast „Przeczytałem i zgadzam się z warunkami polityki prywatności tej strony internetowej”).
-   **Użyj linków:** Umieść szczegółowe informacje na oddzielnej stronie CMS i połącz je z etykietą pola wyboru. Dzięki temu formularz pozostaje przejrzysty, zapewniając jednocześnie pełną przejrzystość.
-   **Dostosowanie motywu:** Jeśli problem nadal występuje, CSS Twojego motywu może ograniczać wyświetlanie. Webmaster może dostosować CSS dla `.addtos-checkbox` lub podobnych klas, aby poprawić responsywność.

**P3: Czy mogę przetłumaczyć etykiety pól wyboru na różne języki?**
**O3:** Tak! Podczas edycji pola wyboru w **Moduły > Dodatkowe pola wyboru > Lista pól wyboru** powinieneś zobaczyć selektor języka obok pola „Nazwa/Etykieta” (często ikona flagi). Kliknij flagę, aby przełączyć się na inny język i wprowadź przetłumaczony tekst dla tego języka. Pamiętaj, aby zapisać zmiany dla każdego języka.

**P4: Co się stanie, jeśli usunę pole wyboru? Czy usunie to historię zgód klienta?**
**O4:** Nie, usunięcie pola wyboru z „Listy pól wyboru” spowoduje usunięcie go z formularza rejestracyjnego w front-office, ale **nie usunie historycznych rekordów zgód**, które klienci wcześniej udzielili dla tego pola wyboru. Te rekordy pozostają w sekcji „Historia” do celów audytu i zgodności. Nowi klienci po prostu nie będą już widzieć tego pola wyboru.

**P5: Chcę zmienić kolejność pól wyboru na stronie rejestracji.**
**O5:** Przejdź do **Moduły > Dodatkowe pola wyboru > Lista pól wyboru**. W tabeli powinieneś zobaczyć kolumnę „Pozycja”. Zazwyczaj możesz przeciągać i upuszczać wiersze, aby zmienić ich kolejność, lub mogą być strzałki w górę/w dół lub edytowalne pole liczbowe do zmiany pozycji. Pamiętaj, aby zapisać zmiany, jeśli jest to wymagane.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Dodatkowe pola wyboru podczas rejestracji” stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), głównie rozszerzając `Module` dla swojej podstawowej funkcjonalności i `AdminController` dla zarządzania Panelu administracyjnego. Wykorzystuje system hooków PrestaShop do wstrzykiwania niestandardowych pól do formularzy rejestracji i tożsamości klienta oraz do rejestrowania danych zgody. Moduł wprowadza niestandardowe tabele bazy danych do przechowywania definicji pól wyboru i historii zgód klientów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Ten moduł nie używa dedykowanych kontrolerów front-office. Wszystkie interakcje front-office (wyświetlanie pól wyboru, przetwarzanie zgody) są obsługiwane bezpośrednio przez podstawowe kontrolery klienta PrestaShop poprzez wykorzystanie specyficznych hooków.
-   **Kontrolery Panelu administracyjnego**:

    -   `addtos/controllers/admin/AdminAddTosHistory.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminAddTosHistoryController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja**: Zarządza historycznymi rekordami zgód klientów. Jest dostępny poprzez zakładkę „Historia” w głównym menu modułu. Ten kontroler wyświetla widok `list` obiektów `TosHistory`, pokazując klienta, pole wyboru, status zgody, datę i adres IP. Nie pozwala na edycję ani dodawanie rekordów, ponieważ jest to dziennik historyczny.
    -   `addtos/controllers/admin/AdminAddTosList.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminAddTosListController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja**: Zarządza definicją niestandardowych pól wyboru. Jest dostępny poprzez zakładkę „Lista pól wyboru”. Ten kontroler zapewnia widoki `list`, `add` i `edit` dla obiektów `Tos`, umożliwiając administratorom definiowanie etykiety pola wyboru, linku, statusu wymaganego, statusu aktywnego i pozycji.
    -   `addtos/controllers/admin/index.php`
        -   Jest to standardowy plik zastępczy, aby zapobiec listowaniu katalogów. Zazwyczaj zawiera `header('Location: ../../../index.php?controller=AdminHome');` lub podobne. Nie pełni żadnej funkcji w logice modułu.

### 4.3 Podstawowe klasy i modele (`classes/`)

Podstawowe klasy modułu są prawdopodobnie zdefiniowane w głównym pliku `addtos.php` lub bezpośrednio w katalogu `classes/`, jeśli jest obecny (chociaż inwentaryzacja sugeruje, że mogą być w głównym pliku).

-   `Tos` (Prawdopodobnie zdefiniowane w `addtos.php` lub `classes/Tos.php`):

    -   **Tabela bazy danych**: `ps_addtos_tos` (lub podobna, na podstawie nazwy encji `tos`).
    -   **Rozszerza `ObjectModel`**: Tak.
    -   **Pola `$definition`**:
        -   `id_tos`: Klucz podstawowy.
        -   `name`: Pole `HTML`, `isLang` (wielojęzyczne) - etykieta pola wyboru.
        -   `link`: Pole `HTML`, `isLang` (wielojęzyczne) - adres URL dla więcej informacji.
        -   `required`: `BOOL` - czy pole wyboru jest obowiązkowe.
        -   `active`: `BOOL` - czy pole wyboru jest aktualnie wyświetlane.
        -   `position`: `INT` - kolejność wyświetlania.
    -   **Kluczowe metody publiczne**: Standardowe metody `ObjectModel` dla operacji CRUD.
-   `TosHistory` (Prawdopodobnie zdefiniowane w `addtos.php` lub `classes/TosHistory.php`):

    -   **Tabela bazy danych**: `ps_addtos_toshistory` (lub podobna, na podstawie nazwy encji `toshistory`).
    -   **Rozszerza `ObjectModel`**: Tak.
    -   **Pola `$definition`**:
        -   `id_toshistory`: Klucz podstawowy.
        -   `id_customer`: `INT` - ID klienta, który udzielił zgody.
        -   `id_tos`: `INT` - ID pola wyboru.
        -   `accepted`: `BOOL` - `1` jeśli zaakceptowano, `0` jeśli odrzucono (lub `NULL` jeśli opcjonalne i nie zaznaczone).
        -   `date_add`: `DATE` - znacznik czasu zgody.
        -   `ip_address`: `STRING` - adres IP klienta w momencie zgody.
    -   **Kluczowe metody publiczne**: Głównie dla operacji `add` i `read`, ponieważ rekordy historii są niezmienne.

### 4.4 Zasoby JavaScript (`views/js/`)

Inwentaryzacja wskazuje, że nie ma specyficznych plików JavaScript. Sugeruje to, że wszelkie walidacje po stronie klienta lub dynamiczne zachowania dla pól wyboru są obsługiwane przez podstawowy JS PrestaShop, JS motywu, lub nie są główną funkcją tego modułu (polegając na walidacji po stronie serwera).

### 4.5 Arkusze stylów CSS (`views/css/`)

Inwentaryzacja wskazuje, że nie ma specyficznych plików CSS. Oznacza to, że moduł opiera się na domyślnych stylach PrestaShop dla elementów formularzy lub na CSS aktywnego motywu do stylizowania pól wyboru. Programiści chcący dostosować wygląd będą celować w standardowe selektory pól formularzy lub potencjalnie klasy dodane przez moduł w jego szablonach.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `addtos/views/templates/hook/addtos_bo.tpl`: Ten szablon jest prawdopodobnie używany w Panelu administracyjnym, być może do wyświetlania bloku modułu lub informacji na stronie administracyjnej, lub do renderowania treści na stronie konfiguracji modułu (np. powiadomienia o aktualizacjach).
-   **Szablony administracyjne (`views/templates/admin/`)**: Nie ma wymienionych dedykowanych szablonów administracyjnych, co sugeruje, że `AdminAddTosListController` i `AdminAddTosHistoryController` opierają się na domyślnych szablonach PrestaShop `list.tpl` i `form.tpl` do renderowania swoich widoków.
-   **Szablony front-office (`views/templates/front/`)**:
    -   `addtos/views/templates/front/identity.tpl`: Ten szablon jest prawdopodobnie podpięty do strony „Moje dane osobowe” (Tożsamość) klienta. Wyświetlałby listę pól wyboru i aktualny status zgody klienta, potencjalnie umożliwiając im aktualizację swoich preferencji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_addtos_tos`: Przechowuje definicje każdego niestandardowego pola wyboru (etykieta, link, status wymagany, status aktywny, pozycja).
    -   `ps_addtos_tos_lang`: Przechowuje wielojęzyczną zawartość dla pól `name` i `link` tabeli `ps_addtos_tos`.
    -   `ps_addtos_toshistory`: Przechowuje historyczne rekordy zgód klientów (ID klienta, ID pola wyboru, status akceptacji, znacznik czasu, adres IP).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionValidateOrder` | Po zatwierdzeniu zamówienia. | Potencjalnie używany do rejestrowania zgody związanej z warunkami specyficznymi dla zamówienia, choć rzadziej dla pól wyboru rejestracji. |
| `validateCustomerFormFields` | Podczas walidacji formularza rejestracji klienta. | Kluczowy dla walidacji po stronie serwera wymaganych pól wyboru. Jeśli wymagane pole wyboru nie jest zaznaczone, ten hook uniemożliwi rejestrację. |
| `displayAdditionalCustomerFormFields` | Renderuje dodatkowe pola w formularzu rejestracji klienta. | Główny hook do wyświetlania niestandardowych pól wyboru na stronie rejestracji w front-office. |
| `displaytermsAndConditions` | Renderuje treść regulaminu. | Może być używany do wyświetlania pól wyboru w pobliżu standardowego regulaminu lub jako alternatywa. |
| `displayvalidateCustomerFormFields` | Renderuje komunikaty walidacyjne dla pól formularza klienta. | Używany do wyświetlania komunikatów o błędach, jeśli wymagane pole wyboru nie jest zaznaczone. |
| `additionalCustomerFormFields` | Podobny do `displayAdditionalCustomerFormFields`, potencjalnie dla różnych kontekstów lub wersji. | Inny hook do wstrzykiwania niestandardowych pól do formularzy klienta. |
| `termsAndConditions` | Podobny do `displaytermsAndConditions`. | Inny hook do wstrzykiwania regulaminu. |
| `actionCustomerAccountAdd` | Po pomyślnym utworzeniu nowego konta klienta. | Używany do rejestrowania wyborów zgody klienta dla wszystkich aktywnych pól wyboru w tabeli `ps_addtos_toshistory`. |
| `displayAdminCustomers` | Renderuje treść na stronie listy/edycji klientów w Panelu administracyjnym. | Może być używany do wyświetlania podsumowania zgód klienta bezpośrednio w jego profilu w Panelu administracyjnym. |
| `displayCustomerAccountForm` | Renderuje treść na stronie „Moje dane osobowe” (Tożsamość) klienta. | Używany do wyświetlania pól wyboru i umożliwiania klientom przeglądania/aktualizowania ich preferencji zgody po rejestracji. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Dodatkowe pola wyboru podczas rejestracji”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
"""
