---
title: "Limituj liczbę dozwolonych zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Limituj liczbę dozwolonych zamówień” od MyPresta.eu."
sidebar:
  label: "Limituj liczbę dozwolonych zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Limit number of allowed orders na MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-number-of-allowed-orders.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/limit-number-of-allowed-orders/)
>
> ---


# Limituj liczbę dozwolonych zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, na którym definiujesz globalne limity dla swoich klientów.

-   **Co robi to ustawienie:** Jest to kluczowe ustawienie modułu. Definiuje maksymalną liczbę zamówień, jaką *każdy* klient może złożyć w Twoim sklepie, zanim zostanie mu uniemożliwione składanie kolejnych.
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy ustawione na konkretną liczbę (np. 3):* Każdy klient, który pomyślnie złożył 3 zamówienia, nie będzie mógł złożyć 4. zamówienia. Zobaczy komunikat uniemożliwiający mu dokończenie realizacji zamówienia.
    -   *Gdy ustawione na 0 lub pozostawione puste:* Moduł zostanie faktycznie wyłączony dla globalnych limitów, co oznacza, że klienci mogą składać nieograniczoną liczbę zamówień (chyba że zostaną ustawione specyficzne limity dla klientów, patrz sekcja 4.2).
-   **Zalecana wartość:** Zacznij od wartości, która jest zgodna z Twoim celem biznesowym (np. 1 dla ścisłej promocji „jeden na klienta”, 5 dla ogólnego limitu). Jeśli chcesz ograniczyć tylko konkretnych klientów, możesz pozostawić to pole puste i użyć dedykowanego ekranu zarządzania klientami.
-   **Scenariusz/przykład dla sprzedawcy:** Prowadzisz szybką wyprzedaż bardzo poszukiwanego produktu i chcesz zapewnić, że każdy klient ma tylko jedną szansę na zakup. Ustawisz tę wartość na `1`.

### 2.2 Dedykowany ekran administracyjny: Limity zamówień klienta (Panel administracyjny > Moduły > Limituj liczbę dozwolonych zamówień > Limity zamówień klienta)

Ten ekran pozwala zarządzać indywidualnymi limitami zamówień dla konkretnych klientów, nadpisując globalny limit ustawiony w sekcji 4.1.

-   **Nazwa ekranu i lokalizacja w menu:** Możesz uzyskać dostęp do tego ekranu, przechodząc do **Moduły > Menedżer modułów**, znajdując „Limituj liczbę dozwolonych zamówień”, klikając „Konfiguruj”, a następnie szukając zakładki lub linku o nazwie „Limity zamówień klienta” lub podobnej. Alternatywnie, może pojawić się bezpośrednio w Twoim głównym menu PrestaShop pod nowym wpisem utworzonym przez moduł (np. **Klienci > Limity zamówień klienta**).
-   **Dostępne działania i ustawienia:**

    -   **Wyszukiwanie/Wybór klienta:** Zazwyczaj znajdziesz pasek wyszukiwania lub rozwijaną listę do wyboru istniejącego klienta z Twojego sklepu.
    -   **Ustaw indywidualny limit:** Po wybraniu klienta możesz wprowadzić konkretną liczbę dozwolonych zamówień dla *tego konkretnego klienta*.
    -   **Wyświetl/Edytuj istniejące limity:** Tabela lub lista wyświetli wszystkich klientów, dla których ustawiłeś niestandardowe limity, wraz z ich aktualnym limitem i ewentualnie aktualną liczbą zamówień. Możesz edytować lub usuwać te wpisy.
    -   **Wyświetlanie waluty:** Moduł może wyświetlać informacje o walucie (np. `PS_CURRENCY_DEFAULT`) w kontekście zamówień klienta, chociaż same limity są liczbowymi zliczeniami zamówień, a nie wartościami pieniężnymi.
-   **Wpływ zmian:**

    -   *Dodanie nowego limitu klienta:* Wybrany klient będzie teraz ograniczony przez konkretną liczbę zamówień, którą dla niego ustawiłeś, nadpisując globalny limit (jeśli jest ustawiony).
    -   *Edycja istniejącego limitu klienta:* Liczba dozwolonych zamówień klienta zostanie natychmiast zaktualizowana.
    -   *Usunięcie limitu klienta:* Klient powróci do podlegania globalnemu limitowi zamówień (jeśli jest ustawiony) lub nie będzie miał limitu, jeśli żaden globalny limit nie jest aktywny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zidentyfikuj specyficzne potrzeby:** Określ, czy niektórzy klienci VIP, problematyczni klienci lub klienci uczestniczący w specjalnych programach wymagają unikalnych limitów zamówień.
    2.  **Wyszukaj i dodaj:** Użyj funkcji wyszukiwania, aby znaleźć klienta.
    3.  **Zastosuj limit:** Wprowadź żądaną maksymalną liczbę zamówień dla tego klienta.
    4.  **Monitoruj:** Okresowo przeglądaj listę klientów z niestandardowymi limitami, aby upewnić się, że ustawienia są nadal odpowiednie.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Maksymalna dozwolona liczba zamówień (globalnie)** | 0 (Bez limitu) / Twoje potrzeby biznesowe | Ustawia ogólnosklepową maksymalną liczbę zamówień dla *wszystkich* klientów. Zapobiega realizacji zamówienia, jeśli limit zostanie przekroczony. |
| Limity zamówień klienta | **Wyszukiwanie i wybór klienta** | N/A | Pozwala znaleźć i wybrać konkretnych klientów, aby zastosować indywidualne limity. |
| Limity zamówień klienta | **Indywidualny limit zamówień klienta** | N/A | Nadpisuje globalny limit dla konkretnego klienta. Zapobiega realizacji zamówienia dla tego klienta, jeśli jego indywidualny limit zostanie przekroczony. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nadal mogą składać nieograniczone zamówienia, nawet po ustawieniu globalnego limitu. Co jest nie tak?**
O:

1.  **Sprawdź ustawienie:** Upewnij się, że zapisałeś ustawienie „Maksymalna dozwolona liczba zamówień (globalnie)” na głównej stronie konfiguracji modułu.
2.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Zapewni to natychmiastowe zastosowanie nowych ustawień.
3.  **Status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**.
4.  **Specyficzne nadpisania klienta:** Sprawdź ekran „Limity zamówień klienta”. Jeśli dla konkretnego klienta ustawiono indywidualny limit na `0` lub bardzo wysoką liczbę, nadpisze to globalny limit dla niego.

**P: Czy mogę ustawić limit dla klienta na podstawie *wartości* jego zamówień, a nie tylko liczby?**
O: Ten moduł ogranicza konkretnie *liczbę* zamówień. Obecnie nie obsługuje limitowania na podstawie wartości pieniężnej. W przypadku limitów opartych na wartości potrzebny byłby inny typ modułu lub niestandardowe rozwiązanie.

**P: Co się dzieje, gdy klient osiągnie swój limit? Co widzi?**
O: Gdy klient próbuje złożyć zamówienie, które przekroczyłoby jego limit, moduł uniemożliwi sfinalizowanie zamówienia. Zazwyczaj na stronie realizacji zamówienia lub w koszyku zostanie wyświetlony jasny komunikat informujący, że osiągnął maksymalną dozwoloną liczbę zamówień i nie może kontynuować. Dokładne sformułowanie może zależeć od Twojej wersji PrestaShop i motywu.

**P: Czy ten moduł wpływa na poprzednie zamówienia?**
O: Nie, ten moduł wpływa tylko na *przyszłe* zamówienia. Liczy istniejące udane zamówienia, aby określić, czy nowa próba zamówienia przekroczyłaby limit, ale nie modyfikuje ani nie anuluje żadnych wcześniej złożonych zamówień.

**P: Chcę tymczasowo znieść limit dla konkretnego klienta. Jak to zrobić?**
O: Przejdź do ekranu „Limity zamówień klienta”. Znajdź klienta, edytuj jego indywidualny limit i ustaw go na `0` (dla nieograniczonego) lub bardzo wysoką liczbę. Pamiętaj, aby zapisać zmiany. Zawsze możesz później ponownie zastosować bardziej rygorystyczny limit.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Limituj liczbę dozwolonych zamówień” wykorzystuje standardową architekturę modułów PrestaShop, wykorzystując hooki do integracji i AdminController do zarządzania specyficznymi limitami klientów. Działa głównie poprzez sprawdzanie historii zamówień klienta w stosunku do skonfigurowanych limitów podczas procesu walidacji zamówienia. Moduł opiera się na systemie konfiguracji PrestaShop dla ustawień globalnych i niestandardowej tabeli bazy danych dla indywidualnych limitów klientów.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Ten moduł nie używa dedykowanych kontrolerów front-office. Jego logika sprawdzania limitów jest zintegrowana bezpośrednio z procesem zamówień PrestaShop za pomocą hooków.
-   **Kontrolery Panelu administracyjnego**:
    -   `controllers/admin/AdminLimitOrdersUserController.php`
        -   **Nazwa klasy**: `AdminLimitOrdersUserController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność**: Ten kontroler zarządza niestandardowymi limitami zamówień dla poszczególnych klientów. Zapewnia standardowy interfejs PrestaShop `list` i `form` do dodawania, edytowania i usuwania limitów zamówień specyficznych dla klienta. Współpracuje z modelem `LimitOrdersUser` ObjectModel (chociaż nie zidentyfikowano jawnego pliku `classes/`, jest to implikowane przez nazwę i funkcję kontrolera). Prawdopodobnie używa `PS_CURRENCY_DEFAULT` do wyświetlania kontekstu waluty, chociaż same limity są liczbowe.
        -   **Nazwa zakładki**: Prawdopodobnie „Limity zamówień klienta” lub podobna, dostępna ze strony konfiguracji modułu lub dedykowanego wpisu w menu.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy**: (Nie jest klasą, zazwyczaj pusty plik lub przekierowanie ze względów bezpieczeństwa)
        -   **Odpowiedzialność**: Ten plik jest zazwyczaj placeholderem lub środkiem bezpieczeństwa zapobiegającym bezpośredniemu listowaniu katalogów. Nie zawiera aktywnej logiki kontrolera.

### 4.3 Klasy i modele podstawowe (`classes/`)

Na podstawie dostarczonych informacji nie zidentyfikowano jawnych niestandardowych klas w katalogu `classes/`. Jednak `AdminLimitOrdersUserController` silnie sugeruje istnienie klasy `ObjectModel`, prawdopodobnie nazwanej `LimitOrdersUser`, która mapowałaby się do niestandardowej tabeli bazy danych (np. `ps_limitorders_user`). Ten `ObjectModel` definiowałby pola takie jak `id_customer` i `max_orders`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Zakres**: Prawdopodobnie Panel administracyjny.
    -   **Cel**: Zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania i wybierania klientów w formularzu `AdminLimitOrdersUserController` podczas ustawiania indywidualnych limitów. Wiązałoby się to z polami wejściowymi, wysyłałoby żądania AJAX do kontrolera backendu (prawdopodobnie samego `AdminLimitOrdersUserController` lub dedykowanego punktu końcowego AJAX) i wyświetlałoby sugestie.
-   `views/js/limitorders.js`
    -   **Zakres**: Potencjalnie zarówno Front-office (do wyświetlania komunikatów), jak i Panel administracyjny (do ogólnej funkcjonalności modułu).
    -   **Cel**: Ten plik zawierałby podstawową logikę JavaScript dla modułu. W Panelu administracyjnym mógłby obsługiwać walidacje formularzy lub dynamiczne elementy interfejsu użytkownika na stronach konfiguracji. W Front-office, jeśli potrzebne są jakiekolwiek dynamiczne komunikaty lub interakcje, gdy klient osiągnie swój limit (np. wyskakujące okienko modalne, dynamiczna aktualizacja koszyka), ten skrypt zarządzałby tym.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Zakres**: Stylizacja Panelu administracyjnego.
    -   **Cel**: Stylizuje rozwijaną listę autouzupełniania i pola wejściowe używane w panelu administracyjnym, zapewniając spójne i przyjazne dla użytkownika doświadczenie wyszukiwania klientów.
-   `views/css/limitorders.css`
    -   **Zakres**: Zarówno Front-office, jak i Panel administracyjny.
    -   **Cel**: Zawiera ogólną stylizację dla wszelkich widocznych elementów wprowadzonych przez moduł. W Panelu administracyjnym stylizowałby formularze konfiguracji i tabele. W Front-office stylizowałby komunikaty wyświetlane klientom, gdy osiągną swój limit zamówień, zapewniając ich dobrą integrację z motywem sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   Ten moduł nie wymienia jawnie szablonów w katalogu `hook/`, ale jego funkcjonalność sugeruje, że mógłby używać hooków `displayShoppingCart` lub `displayShoppingCartFooter` do wyświetlania komunikatów.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   Szablony dla `AdminLimitOrdersUserController` (np. `list.tpl`, `form.tpl`) znajdowałyby się tutaj, definiując strukturę interfejsu zarządzania limitami klientów.
-   **Szablony Front-office (`views/templates/front/`)**:
    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie renderowany, gdy moduł używa hooka `displayShoppingCart`. Zawierałby logikę wyświetlania komunikatu klientowi *w jego koszyku*, jeśli osiągnął limit zamówień, uniemożliwiając mu przejście do realizacji zamówienia.
    -   `views/templates/front/displayShoppingCartEmpty.tpl`
        -   **Cel**: Ten szablon może być używany w konkretnym scenariuszu, w którym moduł musi wyświetlić komunikat związany z limitami zamówień, nawet gdy koszyk jest pusty, lub jako alternatywny/zapasowy sposób wyświetlania komunikatu. Jego dokładne zastosowanie zależałoby od wewnętrznej logiki modułu dla różnych stanów.
-   `lib/searchTool/views/scripts.tpl`
    -   **Cel**: Ten szablon prawdopodobnie zawiera niezbędne pliki JavaScript i CSS dla komponentów `autocomplete.js` i `autocomplete.css`, zapewniając ich prawidłowe załadowanie w Panelu administracyjnym.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   `ps_configuration`: Przechowuje globalną maksymalną dozwoloną liczbę zamówień (np. `LIMITORDERS_MAX_ORDERS`).
    -   `ps_limitorders_user`: (Implikowana niestandardowa tabela) Przechowuje indywidualne limity zamówień klienta.
        -   `id_limitorders_user` (Klucz główny)
        -   `id_customer` (Klucz obcy do `ps_customer`)
        -   `max_orders` (INT, maksymalna liczba zamówień dozwolona dla tego konkretnego klienta)
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Potencjalnie do ładowania zasobów CSS/JS front-office lub do wczesnych sprawdzeń. |
| `displayRightColumn` / `displayLeftColumn` | Renderuje się w prawej/lewej kolumnie stron front-office. | Może być używany do wyświetlania subtelnego komunikatu o limitach zamówień, choć mniej prawdopodobne dla tego modułu. |
| `displayProductButtons` / `displayProductExtraContent` | Renderuje się na stronie produktu. | Może być używany do wyświetlania komunikatu, jeśli klient osiągnął swój limit i nie może dodać do koszyka. |
| `displayShoppingCart` | Renderuje się w podsumowaniu koszyka. | **KRYTYCZNE:** Prawdopodobnie używane do wyświetlania komunikatów klientowi, jeśli osiągnął limit zamówień, uniemożliwiając realizację zamówienia. |
| `displayShoppingCartFooter` | Renderuje się poniżej podsumowania koszyka. | Podobnie jak `displayShoppingCart`, do wyświetlania komunikatów lub ostrzeżeń. |
| `displayFooter` | Renderuje się w stopce wszystkich stron front-office. | Mniej prawdopodobne dla podstawowej funkcjonalności, być może dla ogólnych informacji o module lub skryptów. |
| `actionValidateOrder` | Wykonywane *po* pomyślnym zatwierdzeniu i zapisaniu zamówienia w bazie danych. | **KRYTYCZNE:** Ten hook jest niezbędny, aby moduł zwiększał liczbę zamówień dla klienta i potencjalnie aktualizował jego status, jeśli osiągnął limit. |
| `actionBeforeCartUpdateQuantity` | Wykonywane przed aktualizacją ilości produktu w koszyku. | Może być używane do wstępnego sprawdzenia limitów przed zezwoleniem na dodanie/aktualizację pozycji. |
| `actionFrontControllerSetMedia` | Pozwala dodawać CSS/JS do stron front-office. | Używane do ładowania `limitorders.js` i `limitorders.css` na odpowiednich stronach front-office. |
| `actionAdminControllerSetMedia` | Pozwala dodawać CSS/JS do stron panelu administracyjnego. | Używane do ładowania CSS/JS specyficznych dla panelu administracyjnego dla ekranów konfiguracji i `AdminLimitOrdersUserController`. |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` wszystkich stron panelu administracyjnego. | Do ładowania CSS/JS specyficznych dla panelu administracyjnego lub wyświetlania powiadomień administracyjnych. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i profesjonalnego wsparcia dla modułu „Limituj liczbę dozwolonych zamówień”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie doskonałego funkcjonowania modułu i pomoc w osiągnięciu celów e-commerce.
