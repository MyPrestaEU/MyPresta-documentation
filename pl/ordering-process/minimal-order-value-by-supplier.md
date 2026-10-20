---
title: "Minimalna wartość zamówienia według dostawcy - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Minimalna wartość zamówienia według dostawcy” od MyPresta.eu."
sidebar:
  label: "Minimalna wartość zamówienia według dostawcy - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Minimal order value by supplier na MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-supplier.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/minimal-order-value-by-supplier/)
>
> ---


# Minimalna wartość zamówienia według dostawcy

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu. Tutaj możesz włączyć lub wyłączyć moduł i uzyskać dostęp do głównego ekranu zarządzania minimalnymi wartościami dla dostawców.

-   **Co robi to ustawienie:** Ten ekran służy jako centralny punkt dla modułu. Pozwala włączyć lub wyłączyć całą funkcjonalność modułu i zapewnia bezpośredni link do zarządzania minimalnymi wartościami zamówień dla dostawców.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy włączony:* Moduł będzie aktywnie sprawdzał koszyki klientów pod kątem zdefiniowanych minimalnych wartości zamówień od dostawców i blokował realizację zamówienia, jeśli wymagania nie zostaną spełnione.
    *   *Gdy wyłączony:* Moduł przestanie działać. Nie będą wykonywane żadne sprawdzenia minimalnej wartości zamówienia, a klienci będą mogli zrealizować zamówienie niezależnie od sumy zamówień od dostawców.
-   **Zalecana wartość:** „TAK” (Włączony), jeśli zamierzasz korzystać z funkcji modułu.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, włączysz go tutaj. Jeśli musisz tymczasowo zawiesić reguły (np. podczas promocji w całym sklepie, gdzie chcesz zezwolić na wszystkie zamówienia), możesz go tutaj wyłączyć.

Na tym ekranie znajdziesz również przycisk lub link do **„Zarządzaj minimalnymi wartościami zamówień według dostawcy”**. Kliknięcie tego przeniesie Cię do dedykowanego ekranu administracyjnego, gdzie zdefiniujesz rzeczywiste reguły.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminMobsController (Panel administracyjny > Moduły > Minimalna wartość zamówienia według dostawcy > Zarządzaj minimalnymi wartościami zamówień)

To jest główny ekran, na którym definiujesz i zarządzasz minimalnymi wartościami zamówień dla każdego z Twoich dostawców.

-   **Nazwa ekranu i lokalizacja w menu:** Dostęp do tego ekranu uzyskujesz, przechodząc do **Moduły > Menedżer modułów**, znajdując „Minimalna wartość zamówienia według dostawcy”, klikając „Konfiguruj”, a następnie klikając przycisk/link „Zarządzaj minimalnymi wartościami zamówień według dostawcy”.
-   **Dostępne akcje i ustawienia:**
    *   **Tabela listy:** Ten ekran wyświetla tabelę wszystkich aktualnie skonfigurowanych minimalnych wartości zamówień. Każdy wiersz zazwyczaj pokazuje:
        *   **Nazwa dostawcy:** Nazwa dostawcy, dla którego obowiązuje reguła.
        *   **Minimalna wartość zamówienia:** Kwota pieniężna, jaką produkty od tego dostawcy muszą osiągnąć w koszyku.
        *   **Akcje:** Zazwyczaj przyciski „Edytuj” i „Usuń” do modyfikacji lub usunięcia istniejącej reguły.
    *   **Przycisk Dodaj nową regułę:** Przycisk (np. „Dodaj nową minimalną wartość zamówienia”) do tworzenia nowej reguły.
    *   **Formularz dodawania/edycji:** Podczas dodawania nowej reguły lub edytowania istniejącej, zazwyczaj zobaczysz formularz z następującymi polami:
        *   **Wybór dostawcy:** Rozwijana lista lub pole wyszukiwania do wyboru jednego z istniejących dostawców.
        *   **Minimalna wartość:** Pole wprowadzania, w którym wprowadzasz numeryczną minimalną kwotę zamówienia wymaganą dla produktów od wybranego dostawcy. Ta wartość będzie w domyślnej walucie Twojego sklepu (np. EUR, USD).
        *   **Przycisk Zapisz:** Aby zastosować zmiany.
-   **Efekt zmian:**
    *   *Dodanie reguły:* Po zapisaniu, nowa minimalna wartość zamówienia dla wybranego dostawcy staje się natychmiast aktywna. Klienci będą musieli spełnić tę wartość dla produktów od tego dostawcy.
    *   *Edycja reguły:* Modyfikacja minimalnej wartości lub zmiana dostawcy dla istniejącej reguły aktualizuje aktywne wymaganie.
    *   *Usunięcie reguły:* Usuwa wymaganie minimalnej wartości zamówienia dla tego konkretnego dostawcy. Klienci nie będą już ograniczeni minimalnym zakupem od tego dostawcy.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zidentyfikuj dostawców:** Określ, którzy dostawcy wymagają minimalnych wartości zamówień na podstawie Twoich potrzeb biznesowych (np. wysokie koszty wysyłki, umowy dropshippingowe).
    2.  **Dodaj reguły:** Dla każdego zidentyfikowanego dostawcy kliknij „Dodaj nową minimalną wartość zamówienia”, wybierz dostawcę, wprowadź minimalną kwotę i zapisz.
    3.  **Monitoruj i dostosowuj:** Regularnie przeglądaj umowy z dostawcami i dane sprzedażowe. Jeśli dostawca zmieni swoje warunki lub jeśli zauważysz trend nieopłacalnych małych zamówień, wróć do tego ekranu, aby dostosować lub dodać nowe reguły.
    4.  **Testuj:** Po dodaniu lub zmodyfikowaniu reguł zawsze przetestuj funkcjonalność, dodając produkty od dotkniętych dostawców do koszyka w front office i próbując zrealizować zamówienie.

#### index.php (mobs/controllers/admin/index.php)

Ten plik zazwyczaj służy jako placeholder lub przekierowanie w katalogu kontrolerów administracyjnych i nie przedstawia bezpośredniego ekranu konfiguracji dla sprzedawcy. Jego główną funkcją jest zazwyczaj zapewnienie, że bezpośredni dostęp do katalogu jest obsługiwany w sposób łagodny, często przekierowując do głównej konfiguracji modułu lub strony błędu. Sprzedawcy nie będą bezpośrednio wchodzić w interakcje z tym plikiem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz/Wyłącz moduł | Włączony | Kontroluje, czy funkcjonalność modułu (sprawdzanie minimalnej wartości zamówienia) jest aktywna czy nieaktywna. |
| **AdminMobsController** | Dodaj nową regułę (Dostawca) | N/A | Wybiera dostawcę, do którego ma zostać zastosowana reguła minimalnej wartości zamówienia. |
| **AdminMobsController** | Dodaj nową regułę (Minimalna wartość) | N/A | Ustawia próg monetarny dla produktów od wybranego dostawcy. |
| **AdminMobsController** | Edytuj regułę (Dostawca) | N/A | Modyfikuje dostawcę powiązanego z istniejącą regułą. |
| **AdminMobsController** | Edytuj regułę (Minimalna wartość) | N/A | Zmienia próg monetarny dla istniejącej reguły dostawcy. |
| **AdminMobsController** | Usuń regułę | N/A | Usuwa wymaganie minimalnej wartości zamówienia dla konkretnego dostawcy. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ustawiłem minimalną wartość, ale nie działa ona w koszyku. Co powinienem sprawdzić?**
O1:

1.  **Czy moduł jest włączony?** Przejdź do **Moduły > Menedżer modułów**, znajdź „Minimalna wartość zamówienia według dostawcy” i upewnij się, że jest włączony.
2.  **Czy reguła jest poprawnie skonfigurowana?** Przejdź do ekranu „Zarządzaj minimalnymi wartościami zamówień według dostawcy” i sprawdź, czy dostawca jest poprawnie wybrany, a minimalna wartość jest wprowadzona jako liczba (bez symboli waluty).
3.  **Czy produkty są poprawnie przypisane do dostawcy?** Dokładnie sprawdź produkty w koszyku klienta, aby upewnić się, że są one rzeczywiście powiązane z dostawcą, dla którego ustawiłeś regułę.
4.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P2: Komunikat powiadomienia jest wyświetlany, ale nie jest w języku mojego sklepu.**
O2: Komunikaty modułu w front office są tłumaczone.

1.  Przejdź do **Lokalizacja > Tłumaczenia**.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, wybierz swój język i kliknij „Modyfikuj”.
3.  Znajdź moduł „mobs” (Minimalna wartość zamówienia według dostawcy) i przetłumacz odpowiednie ciągi znaków. Zapisz zmiany.

**P3: Moduł blokuje realizację zamówienia, ale chcę zezwolić na wyjątek dla konkretnego klienta lub zamówienia.**
O3: Moduł egzekwuje reguły globalnie. Aby zrobić wyjątek, musiałbyś tymczasowo wyłączyć regułę dla konkretnego dostawcy w konfiguracji modułu (**Moduły > Minimalna wartość zamówienia według dostawcy > Zarządzaj minimalnymi wartościami zamówień**) lub wyłączyć cały moduł, jeśli aktywnych jest wiele reguł. Pamiętaj, aby włączyć go ponownie później. Nie ma wbudowanej funkcji „nadpisania” dla klienta lub zamówienia.

**P4: Moduł jest aktywny, ale stylizacja komunikatu powiadomienia nie pasuje do mojego motywu.**
O4: Moduł jest dostarczany z podstawową stylizacją. Jeśli koliduje ona z Twoim niestandardowym motywem, Twój webmaster lub programista może nadpisać CSS modułu. Plik CSS modułu to `mobs/views/css/mobs.css`. Mogą dodać niestandardowe style do pliku `custom.css` lub `theme.css` Twojego motywu, celując w elementy powiadomień modułu, aby pasowały do Twojej marki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Minimalna wartość zamówienia według dostawcy” (`mobs`) stosuje standardową architekturę modułów PrestaShop, wykorzystując zasady MVC. Składa się głównie z głównej klasy modułu, dedykowanego kontrolera administracyjnego do zarządzania regułami oraz kontrolera front-office do interakcji AJAX i wyświetlania powiadomień. Nie używa niestandardowych klas `ObjectModel`, ale przechowuje konfigurację bezpośrednio w `ps_configuration` i zarządza minimalnymi wartościami dla dostawców za pośrednictwem `AdminMobsController`, który prawdopodobnie wchodzi w interakcje z niestandardową tabelą lub rozszerza ogólny `AdminController` do zarządzania danymi. Interakcja z front-office jest obsługiwana za pośrednictwem dedykowanego szablonu dla koszyka i kontrolera AJAX do dynamicznych sprawdzeń.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MobsAjaxModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest odpowiedzialny za obsługę żądań AJAX z front-office, zazwyczaj inicjowanych ze strony koszyka. Prawdopodobnie wykonuje on sprawdzenia w czasie rzeczywistym zawartości koszyka pod kątem skonfigurowanych minimalnych wartości zamówień od dostawców. Zwraca odpowiedzi JSON wskazujące, czy minimalne wartości zostały spełnione i dostarcza odpowiednie komunikaty, jeśli nie. Pozwala to na dynamiczne aktualizacje wyświetlania koszyka bez pełnego przeładowania strony.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MobsIndexModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler może służyć jako domyślny punkt wejścia dla części front-office modułu, chociaż jego główną funkcją jest często przekierowanie lub wyświetlenie podstawowej strony, jeśli moduł nie ma dedykowanej strony front-office. Biorąc pod uwagę funkcjonalność modułu, bardziej prawdopodobne jest, że kontroler `ajax.php` obsługuje główną logikę front-office, a `index.php` jest rezerwową lub minimalną stroną.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminMobs.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminMobsController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza regułami „Minimalnych wartości zamówień według dostawcy”. Zapewnia interfejs do listowania, dodawania, edytowania i usuwania tych reguł. Prawdopodobnie wchodzi w interakcje z niestandardową tabelą bazy danych (np. `ps_mobs_rules`) w celu przechowywania ID dostawcy i powiązanej minimalnej wartości. Widok siatki i pola formularza są renderowane przy użyciu klas PrestaShop `HelperList` i `HelperForm`.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Brak konkretnej klasy, zazwyczaj prosty plik PHP.
        -   **Odpowiedzialność**: Ten plik jest zazwyczaj placeholderem lub środkiem bezpieczeństwa, aby zapobiec bezpośredniemu listowaniu katalogów. Często zawiera proste `header('Location: ../../../index.php?controller=AdminHome');` lub podobne przekierowanie do panelu administracyjnego PrestaShop, zapewniając, że bezpośredni dostęp do `yourshop.com/modules/mobs/controllers/admin/` nie ujawnia wrażliwych informacji ani nie powoduje błędów. Nie przedstawia ekranu dla użytkownika.

### 4.3 Główne klasy i modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że moduł albo:

1.  Przechowuje swoją konfigurację bezpośrednio w `ps_configuration` dla prostych ustawień.
2.  Zarządza swoimi danymi (minimalnymi wartościami dostawców) bezpośrednio w `AdminMobsController` za pomocą standardowych metod zapytań do bazy danych PrestaShop, potencjalnie wchodząc w interakcje z niestandardową tabelą utworzoną podczas instalacji, bez dedykowanego `ObjectModel`.

Jeśli używana jest niestandardowa tabela, jej struktura byłaby zdefiniowana w metodzie `install()` głównego pliku modułu (`mobs/index.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/mobs.js`
    -   **Zakres**: Front-office.
    -   **Opis**: Ten plik JavaScript jest odpowiedzialny za interakcje po stronie klienta związane ze sprawdzaniem minimalnej wartości zamówienia. Prawdopodobnie:
        -   Wiąże słuchaczy zdarzeń ze zmianami ilości w koszyku, usuwaniem produktów lub przyciskiem „Przejdź do kasy”.
        -   Wysyła żądania AJAX do `controllers/front/ajax.php` w celu walidacji koszyka pod kątem minimalnych wartości dostawców.
        -   Odbiera odpowiedzi JSON od kontrolera AJAX.
        -   Dynamicznie aktualizuje wyświetlanie koszyka, pokazując komunikaty powiadomień, jeśli minimalne wartości nie zostały spełnione.
        -   Wyłącza lub włącza przycisk „Przejdź do kasy” na podstawie wyników walidacji.
        -   Może zawierać logikę wyświetlania wyskakujących okien modalnych lub wbudowanych komunikatów o błędach.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `views/css/mobs.css`
    -   **Zakres**: Stylizacja klienta w front-office.
    -   **Opis**: Ten arkusz stylów zapewnia wizualną prezentację elementów modułu w front-office, głównie komunikatów powiadomień wyświetlanych w koszyku.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Prawdopodobnie będzie celować w konkretne klasy CSS dodane przez moduł do szablonu koszyka, takie jak `div.mobs-notification`, `p.mobs-error-message` lub podobne elementy, które wyświetlają ostrzeżenia o niespełnionych minimalnych wartościach zamówienia.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: Programiści mogą sprawdzić wyjście HTML powiadomień modułu, aby zidentyfikować dokładne nazwy klas (np. `.mobs-alert`, `.mobs-supplier-name`, `.mobs-required-value`) i nadpisać je w pliku `custom.css` swojego motywu, aby pasowały do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   W spisie nie ma wymienionych konkretnych szablonów hooków, co sugeruje, że wyjście front-office modułu jest głównie wstrzykiwane do istniejącego szablonu, takiego jak `displayShoppingCart.tpl`, lub poprzez bezpośrednie renderowanie szablonu w kontrolerze.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   Dossier modułu nie wymienia konkretnych szablonów administracyjnych. `AdminMobsController` prawdopodobnie używa domyślnych szablonów `HelperList` i `HelperForm` PrestaShop dla swoich widoków siatki i formularzy, które są częścią podstawowego frameworka PrestaShop.
-   **Szablony front-office (`views/templates/front/`)**:

    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Opis**: Ten szablon jest specjalnie zaprojektowany do włączenia lub renderowania na stronie koszyka. Zawiera strukturę HTML do wyświetlania klientowi powiadomień o minimalnej wartości zamówienia. Prawdopodobnie będzie iterować przez wszystkie niespełnione minimalne wartości dostawców i wyświetlać komunikat dla każdego z nich, być może zawierający nazwę dostawcy i pozostałą wymaganą kwotę. Ten szablon jest dynamicznie aktualizowany przez skrypt `mobs.js` na podstawie odpowiedzi AJAX.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Dossier modułu nie wymienia jawnie niestandardowych klas ani plików SQL, ale aby `AdminMobsController` mógł zarządzać „Minimalnymi wartościami zamówień według dostawcy”, musi przechowywać te dane. Jest bardzo prawdopodobne, że moduł tworzy niestandardową tabelę podczas swojej metody `install()` w `mobs/index.php`.
    -   **Prawdopodobna nazwa tabeli**: `ps_mobs_rules` (lub podobna, np. `ps_minimal_order_by_supplier`).
    -   **Prawdopodobna struktura tabeli**:
        -   `id_mobs_rule` (KLUCZ GŁÓWNY, INT)
        -   `id_supplier` (INT, KLUCZ OBCY do `ps_supplier.id_supplier`)
        -   `min_value` (DECIMAL(20,6))
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)
    -   **Rekordy konfiguracji**: Główny status włączenia/wyłączenia modułu jest prawdopodobnie przechowywany w `ps_configuration` z kluczem takim jak `MOBS_ENABLED`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Aby dołączyć pliki CSS (`mobs.css`) i JavaScript (`mobs.js`) dla funkcjonalności front-office. |
| `displayShoppingCartFooter` | Na dole strony koszyka. | Aby wyświetlić szablon `displayShoppingCart.tpl`, który zawiera komunikaty powiadomień o niespełnionych minimalnych wartościach zamówienia. |
| `actionCartSave` | Po zapisaniu koszyka (np. zmiana ilości, dodanie/usunięcie produktu). | Aby wywołać logikę, która sprawdza minimalne wartości zamówienia i potencjalnie aktualizuje status koszyka lub zmienne sesji. |
| `actionValidateOrder` | Przed oficjalną walidacją zamówienia. | Aby wykonać ostateczne sprawdzenie minimalnych wartości zamówienia i zapobiec walidacji zamówienia, jeśli wymagania nie zostaną spełnione. |
| `displayBeforeCarrier` | Przed krokiem wyboru przewoźnika w kasie. | Aby wyświetlić ostrzeżenia lub zablokować postęp, jeśli minimalne wartości nie zostaną spełnione na wcześniejszym etapie realizacji zamówienia. |
| `displayPaymentTop` | Na górze strony wyboru płatności. | Aby wyświetlić ostrzeżenia lub zablokować postęp, jeśli minimalne wartości nie zostaną spełnione przed płatnością. |

*Uwaga: Dossier modułu wspomina o „Header, Columns, Product lub Footer” jako hookach front-office. Chociaż `displayHeader` jest pewny, moduł prawdopodobnie używa `displayShoppingCartFooter` lub podobnego hooka specyficznego dla koszyka do swojego głównego wyjścia, a `actionCartSave`/`actionValidateOrder` do swojej podstawowej logiki. `displayRightColumn` lub `displayLeftColumn` mogą być używane do opcjonalnych statycznych bloków, ale są mniej prawdopodobne dla podstawowej funkcjonalności.*

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Minimalna wartość zamówienia według dostawcy”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
