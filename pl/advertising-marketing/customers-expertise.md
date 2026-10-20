---
title: "Customers Expertise - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop Customers Expertise od MyPresta.eu."
sidebar:
  label: "Customers Expertise - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customers Expertise na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/customers-expertise.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/customers-expertise/)
>
> ---


# Customers Expertise

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle obecne w każdym nowoczesnym środowisku hostingowym. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Customers Expertise)

Jest to główny ekran konfiguracji, na którym definiujesz swoje osiągnięcia, ich kryteria i nagrody. Konfiguracja modułu jest zarządzana za pomocą dedykowanego interfejsu, który pozwala dodawać, edytować i usuwać osiągnięcia.

**Nazwa ekranu i lokalizacja w menu:**
Możesz uzyskać dostęp do tego ekranu, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Customers Expertise” i klikając przycisk „Konfiguruj”.

**Dostępne działania i ustawienia:**
Strona konfiguracji wyświetli listę aktualnie zdefiniowanych osiągnięć. Zazwyczaj znajdziesz opcje do:

-   **Dodaj nowe osiągnięcie:** Przycisk lub link do utworzenia nowego osiągnięcia.
-   **Edytuj istniejące osiągnięcie:** Ikona (np. ołówek) obok każdego osiągnięcia na liście, aby zmodyfikować jego ustawienia.
-   **Usuń osiągnięcie:** Ikona (np. kosz na śmieci) obok każdego osiągnięcia, aby je usunąć.

Podczas dodawania lub edytowania osiągnięcia zazwyczaj napotkasz następujące ustawienia:

#### **Szczegóły osiągnięcia**

-   **Nazwa osiągnięcia:**

    -   **Co robi to ustawienie:** Jest to tytuł osiągnięcia, który zobaczą Twoi klienci (np. „Pierwszy Kupujący”, „Mistrz Recenzji”, „VIP Kupujący”).
    -   **Wpływ zmiany tego ustawienia:** Ta nazwa jest wyświetlana w sekcji „Moje osiągnięcia” klienta. Jasna i atrakcyjna nazwa zachęca do zaangażowania.
    -   **Zalecana wartość:** Coś opisowego i motywującego.
    -   **Scenariusz/przykład dla sprzedawcy:** „Bohater Pierwszego Zamówienia” dla pierwszego zakupu klienta.
-   **Opis osiągnięcia:**

    -   **Co robi to ustawienie:** Krótkie wyjaśnienie, czym jest osiągnięcie i jak je zdobyć. Pomaga to klientom zrozumieć cel.
    -   **Wpływ zmiany tego ustawienia:** Ten opis pojawia się obok nazwy. Dobry opis wyjaśnia kryteria osiągnięcia.
    -   **Zalecana wartość:** Zwięzła i zachęcająca.
    -   **Scenariusz/przykład dla sprzedawcy:** „Dokonaj swojego pierwszego zakupu w naszym sklepie, aby zdobyć tę odznakę!”
-   **Obraz/Ikona osiągnięcia:**

    -   **Co robi to ustawienie:** Pozwala przesłać wizualną reprezentację (odznakę, ikonę) osiągnięcia.
    -   **Wpływ zmiany tego ustawienia:** Ten obraz jest wyświetlany obok nazwy osiągnięcia, czyniąc je wizualnie atrakcyjnym i rozpoznawalnym.
    -   **Zalecana wartość:** Unikalny, wysokiej jakości obraz, który odzwierciedla temat osiągnięcia.
    -   **Scenariusz/przykład dla sprzedawcy:** Ikona „gwiazdy” dla osiągnięcia „Najlepszy Recenzent”.
-   **Aktywne / Włączone:**

    -   **Co robi to ustawienie:** Przełącznik do włączania lub wyłączania osiągnięcia.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone:* Osiągnięcie jest aktywne, klienci mogą je zdobywać i pojawi się na ich liście osiągnięć.
        -   *Gdy wyłączone:* Osiągnięcie jest ukryte, klienci nie mogą go zdobywać i nie pojawi się w front office. Przydatne dla osiągnięć sezonowych lub tych, które są jeszcze w przygotowaniu.
    -   **Zalecana wartość:** TAK dla aktywnych osiągnięć.
    -   **Scenariusz/przykład dla sprzedawcy:** Wyłącz osiągnięcie „Świąteczny Kupujący” po sezonie świątecznym.

#### **Kryteria osiągnięcia (Jak je zdobyć)**

To jest rdzeń modułu, gdzie definiujesz warunki, które klient musi spełnić. Moduł prawdopodobnie oferuje różne typy kryteriów. Typowe przykłady to:

-   **Liczba zamówień:**

    -   **Co robi to ustawienie:** Klient musi złożyć określoną liczbę zamówień.
    -   **Wpływ zmiany tego ustawienia:** Określa, ile udanych zamówień jest wymaganych.
    -   **Zalecana wartość:** Zacznij od niskich liczb dla początkowych osiągnięć (np. 1, 3) i zwiększaj dla wyższych poziomów.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustaw na „1” dla „Pierwszy Kupujący”, „5” dla „Lojalny Klient”.
-   **Całkowita wydana kwota:**

    -   **Co robi to ustawienie:** Skumulowane wydatki klienta we wszystkich zamówieniach muszą osiągnąć określoną kwotę.
    -   **Wpływ zmiany tego ustawienia:** Definiuje próg monetarny.
    -   **Zalecana wartość:** Dostosuj do swojej średniej wartości zamówienia i segmentów klientów.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustaw na „100 €” dla „Brązowego Wydawcy”, „500 €” dla „Srebrnego Wydawcy”.
-   **Liczba zakupionych produktów:**

    -   **Co robi to ustawienie:** Klient musi zakupić określoną łączną ilość produktów (we wszystkich zamówieniach).
    -   **Wpływ zmiany tego ustawienia:** Ustawia próg ilościowy.
    -   **Zalecana wartość:** Przydatne do zachęcania do zakupów hurtowych lub wypróbowywania różnych produktów.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustaw na „10” dla „Kolekcjonera Produktów”.
-   **Liczba recenzji produktów:**

    -   **Co robi to ustawienie:** Klient musi przesłać określoną liczbę zatwierdzonych recenzji produktów.
    -   **Wpływ zmiany tego ustawienia:** Zachęca do treści generowanych przez użytkowników i dowodów społecznych.
    -   **Zalecana wartość:** Ustaw na „1” dla „Pierwszego Recenzenta”, „5” dla „Mistrza Recenzji”.
    -   **Scenariusz/przykład dla sprzedawcy:** Nagradzaj klientów za wartościowe opinie.
-   **Zakup konkretnego produktu/kategorii:**

    -   **Co robi to ustawienie:** Klient musi zakupić produkt z określonej kategorii lub konkretny produkt.
    -   **Wpływ zmiany tego ustawienia:** Promuje konkretne przedmioty lub kategorie.
    -   **Zalecana wartość:** Użyj dla nowych produktów lub wolno sprzedających się zapasów.
    -   **Scenariusz/przykład dla sprzedawcy:** „Kupiono przedmiot z nowej kolekcji” za zakup z kategorii „Nowości”.

#### **Nagroda za osiągnięcie (Kupon rabatowy)**

-   **Typ kuponu:**

    -   **Co robi to ustawienie:** Definiuje typ kodu rabatowego, który otrzymuje klient (np. procentowy, stała kwota, darmowa wysyłka).
    -   **Wpływ zmiany tego ustawienia:** Określa charakter nagrody.
    -   **Zalecana wartość:** Rabaty procentowe są często popularne, ale stałe kwoty mogą być dobre dla mniejszych zakupów.
    -   **Scenariusz/przykład dla sprzedawcy:** „Rabat procentowy” na 10% zniżki na następne zamówienie.
-   **Wartość kuponu:**

    -   **Co robi to ustawienie:** Rzeczywista wartość rabatu (np. „10” dla 10%, „5 €” dla stałej kwoty).
    -   **Wpływ zmiany tego ustawienia:** Bezpośrednio wpływa na zachętę dla klienta.
    -   **Zalecana wartość:** Zrównoważ hojność z marżami zysku.
    -   **Scenariusz/przykład dla sprzedawcy:** „15” dla 15% rabatu.
-   **Okres ważności kuponu (dni):**

    -   **Co robi to ustawienie:** Ile dni wygenerowany kupon jest ważny od momentu jego odebrania przez klienta.
    -   **Wpływ zmiany tego ustawienia:** Tworzy pilność dla klienta, aby użyć kuponu.
    -   **Zalecana wartość:** 7-30 dni jest powszechne. Zbyt krótki może frustrować, zbyt długi zmniejsza pilność.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustaw na „14” dni, aby zachęcić do szybkiego ponownego zakupu.
-   **Minimalna kwota zamówienia dla kuponu:**

    -   **Co robi to ustawienie:** Czy kupon wymaga minimalnej wartości zakupu, aby mógł być użyty.
    -   **Wpływ zmiany tego ustawienia:** Pomaga chronić Twoje marże i zachęca klientów do wydawania więcej.
    -   **Zalecana wartość:** Ustaw rozsądne minimum, które zachęca do sprzedaży dodatkowej, nie będąc zbyt restrykcyjnym.
    -   **Scenariusz/przykład dla sprzedawcy:** „30 €” minimalne zamówienie dla 5 € rabatu.
-   **Prefiks kuponu:**

    -   **Co robi to ustawienie:** Niestandardowy prefiks dla generowanych kodów rabatowych (np. „OSIĄGNIĘCIE-”, „ODZNAKA-”).
    -   **Wpływ zmiany tego ustawienia:** Pomaga zidentyfikować źródło kodów rabatowych w raportach sprzedaży PrestaShop.
    -   **Zalecana wartość:** Krótki, łatwy do zapamiętania prefiks.
    -   **Scenariusz/przykład dla sprzedawcy:** „EKSPERT-” aby wiedzieć, że kupon pochodzi z modułu Customers Expertise.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Zaplanuj swoje osiągnięcia:** Przed utworzeniem zdecyduj, jakie zachowania chcesz nagradzać i ile poziomów osiągnięć chcesz mieć.
2.  **Zacznij prosto:** Rozpocznij od 2-3 podstawowych osiągnięć (np. pierwsze zamówienie, całkowita wydana kwota, liczba recenzji), aby przetestować.
3.  **Utwórz każde osiągnięcie:** Przejdź przez proces „Dodaj nowe osiągnięcie”, starannie definiując kryteria i nagrody.
4.  **Monitoruj zaangażowanie klientów:** Sprawdź swoje sprzedaże i konta klientów, aby zobaczyć, jak klienci wchodzą w interakcje z osiągnięciami.
5.  **Dostosuj i rozszerzaj:** Na podstawie wyników, udoskonalaj istniejące osiągnięcia lub wprowadzaj nowe, bardziej złożone.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Nazwa osiągnięcia | Opisowa | Tytuł wyświetlany klientowi. |
| | Opis osiągnięcia | Informacyjny | Wyjaśnia, jak zdobyć osiągnięcie. |
| | Obraz/Ikona osiągnięcia | Unikalny obraz | Wizualna reprezentacja odznaki. |
| | Aktywne / Włączone | TAK | Przełącza widoczność i kwalifikowalność osiągnięcia. |
| | **Kryteria: Liczba zamówień** | 1, 3, 5 | Klient musi złożyć X zamówień. |
| | **Kryteria: Całkowita wydana kwota** | 50 €, 100 €, 500 € | Całkowite wydatki klienta muszą osiągnąć X. |
| | **Kryteria: Liczba zakupionych produktów** | 5, 10, 20 | Klient musi kupić łącznie X produktów. |
| | **Kryteria: Liczba recenzji produktów** | 1, 3, 5 | Klient musi przesłać X zatwierdzonych recenzji. |
| | **Kryteria: Zakup konkretnego produktu/kategorii** | (Wybierz produkt/kategorię) | Klient musi kupić z konkretnego produktu/kategorii. |
| | **Nagroda: Typ kuponu** | Procentowy | Typ rabatu (%, stała kwota, darmowa wysyłka). |
| | **Nagroda: Wartość kuponu** | 10 (dla %) | Kwota rabatu. |
| | **Nagroda: Okres ważności kuponu (dni)** | 14-30 | Jak długo kupon jest ważny po odebraniu. |
| | **Nagroda: Minimalna kwota zamówienia dla kuponu** | (Opcjonalnie) | Minimalna wartość koszyka wymagana do użycia kuponu. |
| | **Nagroda: Prefiks kuponu** | EKSPERT- | Niestandardowy prefiks dla generowanych kodów rabatowych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie widzą sekcji osiągnięć na swoim koncie.**
O: Najpierw upewnij się, że moduł „Customers Expertise” jest zainstalowany i włączony w Twoim Panelu administracyjnym. Sprawdź konfigurację modułu, aby upewnić się, że masz co najmniej jedno osiągnięcie utworzone i ustawione jako „Aktywne”. Sprawdź również, czy plik `customer-account.tpl` (lub jego odpowiednik) Twojego motywu jest poprawnie podpięty, aby wyświetlać link modułu. Jeśli masz niestandardowy motyw, może być konieczne, aby webmaster upewnił się, że hook jest renderowany.

**P: Klienci zdobywają osiągnięcia, ale nie otrzymują kodów rabatowych.**
O: Przejdź do konfiguracji modułu i edytuj konkretne osiągnięcie. Sprawdź dokładnie, czy „Typ kuponu” i „Wartość kuponu” są poprawnie zdefiniowane dla nagrody. Upewnij się, że nie ma literówek ani nieprawidłowych ustawień w parametrach kuponu. Sprawdź również swoje „Reguły koszyka” PrestaShop (lub „Rabaty” w starszych wersjach), aby zobaczyć, czy wygenerowane kupony się tam pojawiają.

**P: Obrazy osiągnięć nie wyświetlają się poprawnie.**
O: Zazwyczaj wskazuje to na problem z przesyłaniem obrazu lub uprawnieniami do plików. Upewnij się, że przesłany plik obrazu jest w standardowym formacie internetowym (JPG, PNG, GIF) i nie jest zbyt duży. Sprawdź uprawnienia do plików na swoim serwerze dla katalogu obrazów modułu (np. `modules/customersexpertise/img/`), aby upewnić się, że PrestaShop może tam zapisywać i odczytywać pliki. Wyczyść również pamięć podręczną PrestaShop (Zaawansowane > Wydajność).

**P: Czy mogę przetłumaczyć nazwy i opisy osiągnięć na wiele języków?**
O: Tak, podobnie jak większość modułów PrestaShop, pola tekstowe dla nazw i opisów osiągnięć powinny obsługiwać wprowadzanie w wielu językach. Podczas edytowania osiągnięcia szukaj flag językowych obok pól wprowadzania, co pozwoli Ci podać tłumaczenia dla każdego języka zainstalowanego w Twoim sklepie.

**P: Co się stanie, jeśli klient zdobędzie osiągnięcie, ale później je wyłączę?**
O: Jeśli osiągnięcie zostanie wyłączone, nowi klienci nie będą już mogli go zdobyć, a zazwyczaj zostanie ono ukryte w front office. Klienci, którzy już je zdobyli, zazwyczaj zachowają swój status i wszelkie związane z nim kupony, które odebrali przed wyłączeniem osiągnięcia. Jednak nie będą mogli ponownie odebrać kuponów, jeśli osiągnięcie zostanie ponownie włączone, a oni już je posiadają.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla deweloperów i webmasterów pracujących z modułem Customers Expertise.

### 4.1 Przegląd architektury

Moduł Customers Expertise opiera się na standardowej architekturze modułów PrestaShop, wykorzystując głównie kontrolery front-office do interakcji z klientem oraz główną klasę modułu do zarządzania konfiguracją i hookami. Integruje logikę gamifikacji poprzez śledzenie działań klienta (zamówienia, recenzje) i dynamiczne generowanie obiektów `CartRule` (kuponów) PrestaShop jako nagród. Podstawowa logika modułu znajduje się w jego głównym pliku PHP i dedykowanych kontrolerach front-office, a szablony Smarty obsługują warstwę prezentacji.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują logikę i wyświetlanie osiągnięć oraz powiązanych funkcji dla klienta.

-   `controllers/front/achievements.php`

    -   **Nazwa klasy i klasa nadrzędna:** `CustomersExpertiseAchievementsModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to główny kontroler do wyświetlania osiągnięć klienta. Pobiera wszystkie zdefiniowane osiągnięcia, sprawdza kwalifikowalność i status zdobycia dla każdego z nich dla bieżącego klienta oraz przygotowuje dane dla szablonu `achievements.tpl`. Prawdopodobnie obsługuje logikę odbierania kuponów po zdobyciu osiągnięcia.
    -   **Trasy:** Zazwyczaj dostępny poprzez URL, np. `twojasklep.com/module/customersexpertise/achievements`.
-   `controllers/front/affiliationlink.php`

    -   **Nazwa klasy i klasa nadrzędna:** `CustomersExpertiseAffiliationlinkModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Chociaż opis modułu nie wspomina wyraźnie o afiliacji, ten kontroler sugeruje potencjalną funkcję dla klientów do generowania i zarządzania linkami afiliacyjnymi, być może jako nagroda za osiągnięcie lub samodzielna funkcja. Obsługiwałby wyświetlanie i generowanie takich linków.
    -   **Trasy:** Prawdopodobnie `twojasklep.com/module/customersexpertise/affiliationlink`.
-   `controllers/front/index.php`

    -   **Nazwa klasy i klasa nadrzędna:** `CustomersExpertiseIndexModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Często służy jako domyślny lub awaryjny kontroler front-office. Może przekierowywać do kontrolera `achievements` lub wyświetlać ogólną stronę docelową dla modułu, jeśli nie jest wymagane żadne konkretne działanie.
    -   **Trasy:** `twojasklep.com/module/customersexpertise/index` lub `twojasklep.com/module/customersexpertise`.
-   `controllers/front/voucher.php`

    -   **Nazwa klasy i klasa nadrzędna:** `CustomersExpertiseVoucherModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za faktyczny proces generowania i przypisywania kuponu rabatowego klientowi po odebraniu przez niego zdobytego osiągnięcia. Będzie on współdziałał z obiektem `CartRule` PrestaShop w celu utworzenia kuponu i potencjalnie aktualizacji statusu osiągnięcia klienta.
    -   **Trasy:** Może to być punkt końcowy AJAX lub bezpośredni URL do odbierania kuponów, np. `twojasklep.com/module/customersexpertise/voucher`.

#### Kontrolery administracyjne Back-Office

Moduł nie wydaje się mieć dedykowanych niestandardowych kontrolerów administracyjnych. Konfiguracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczony spis nie wskazuje na żadne niestandardowe klasy w katalogu `classes/`. Sugeruje to, że podstawowa logika modułu, definicje osiągnięć i śledzenie klientów są prawdopodobnie zarządzane bezpośrednio w głównym pliku modułu (`ajax_customersexpertise.php`) i potencjalnie poprzez wykorzystanie istniejących klas `ObjectModel` PrestaShop, takich jak `Customer`, `Order`, `Product` i `CartRule`.

Moduł wewnętrznie zarządzałby danymi osiągnięć, prawdopodobnie poprzez:

-   Przechowywanie definicji osiągnięć (nazwa, opis, kryteria, nagroda) w tabeli `ps_configuration` jako serializowane tablice lub JSON.
-   Przechowywanie statusu osiągnięć klienta (zdobyte, odebrany kupon) w niestandardowej tabeli utworzonej podczas instalacji lub również w `ps_configuration` lub metadanych `ps_customer`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `customersexpertise/lib/voucherengine/script.js`
    -   **Zakres:** Prawdopodobnie Front-office.
    -   **Szczegóły:** Ten skrypt jest prawdopodobnie odpowiedzialny za poprawę doświadczenia użytkownika na stronie osiągnięć klienta. Może obsługiwać:
        -   Żądania AJAX dotyczące odbierania kuponów (np. gdy klient kliknie przycisk „Odbierz kupon”).
        -   Dynamiczne aktualizacje strony po odebraniu kuponu (np. wyświetlanie kodu kuponu, oznaczanie osiągnięcia jako odebranego).
        -   Walidację po stronie klienta lub interaktywne elementy związane z funkcjami gamifikacji.
        -   Potencjalnie może współdziałać z kontrolerem front-office `voucher.php`.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `customersexpertise/css/customersexpertise.css`

    -   **Zakres:** Stylizacja klienta w front-office.
    -   **Szczegóły:** Jest to główny arkusz stylów dla komponentów front-office modułu. Definiuje wygląd listy osiągnięć, poszczególnych kart osiągnięć, wyświetlania kuponów i wszelkich innych elementów interfejsu użytkownika prezentowanych klientowi.
    -   **Kluczowe selektory klas CSS:** Deweloperzy mogą spodziewać się klas takich jak `.customersexpertise-achievements`, `.achievement-item`, `.achievement-badge`, `.voucher-code` itp., które można nadpisać w pliku `custom.css` lub `theme.css` niestandardowego motywu, aby dopasować je do brandingu sklepu.
-   `customersexpertise/lib/voucherengine/ps16.css`

    -   **Zakres:** Stylizacja klienta w front-office, specjalnie dla kompatybilności z PrestaShop 1.6.
    -   **Szczegóły:** Ten arkusz stylów prawdopodobnie zawiera specyficzne nadpisania lub dodatkowe style, aby zapewnić prawidłowe i wizualnie spójne wyświetlanie modułu w front-office z motywami PrestaShop 1.6. Może dotyczyć różnic w układzie lub specyficznej stylizacji elementów, które zmieniły się między wersjami PrestaShop. Dla nowszych wersji PrestaShop (1.7, 8.x, 9.x) ten plik może być ładowany warunkowo lub jego style mogą być mniej istotne, opierając się bardziej na `customersexpertise.css`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony front-office (`views/templates/front/`)**:

    -   `customersexpertise/views/templates/front/achievements.tpl`
        -   **Cel:** Jest to główny szablon do wyświetlania strony osiągnięć klienta. Iteruje przez dane osiągnięć przekazane z kontrolera `achievements.php`, pokazując zdobyte odznaki, kryteria dla niezrealizowanych i opcje odbierania kuponów.
    -   `customersexpertise/views/templates/front/affiliation-link.tpl`
        -   **Cel:** Jeśli kontroler `affiliationlink.php` jest aktywny, ten szablon renderowałby interfejs dla klientów do przeglądania lub generowania ich linków afiliacyjnych.
    -   `customersexpertise/views/templates/front/voucher.tpl`
        -   **Cel:** Ten szablon może być używany do wyświetlania pojedynczego kodu kuponu lub komunikatu potwierdzającego po odebraniu kuponu, potencjalnie jako część odpowiedzi AJAX lub dedykowanej strony.
-   **Szablony hooków (`views/templates/hook/`)**:

    -   `customersexpertise/views/templates/hook/customer-account.tpl`
        -   **Hook:** `displayCustomerAccount` (lub podobny, w zależności od wersji PrestaShop).
        -   **Cel:** Ten szablon renderuje link lub blok, który pojawia się w panelu „Moje konto” klienta, kierując go do strony „Moje osiągnięcia”. Jest to kluczowe dla odkrywalności funkcji modułu przez klienta.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Opis modułu i spis plików nie wymieniają jawnie niestandardowych plików SQL do tworzenia tabel. Sugeruje to, że moduł może przechowywać swoje dane w jeden z następujących sposobów:

    -   **`ps_configuration`**: Definicje osiągnięć (kryteria, nagrody) mogą być przechowywane jako serializowane tablice lub ciągi JSON w tabeli `ps_configuration`, używając unikalnych kluczy konfiguracyjnych (np. `CUSTOMERS_EXPERTISE_ACHIEVEMENTS`).
    -   **Istniejące tabele PrestaShop**: Status osiągnięć klienta (które osiągnięcia zdobył, które kupony odebrał) może być przechowywany w niestandardowym polu dodanym do tabel `ps_customer` lub `ps_customer_group`, lub w niestandardowej tabeli utworzonej dynamicznie przez metodę `install()` modułu bez dedykowanego pliku `.sql`.
    -   **`ps_cart_rule`**: Moduł bezpośrednio współdziała z systemem `CartRule` (kuponów rabatowych) PrestaShop w celu generowania nagród.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` wszystkich stron front-office. | Do globalnego włączania zasobów CSS i JavaScript lub dodawania meta tagów. |
| `displayLeftColumn` / `displayRightColumn` | W lewej/prawej kolumnie stron front-office. | Do wyświetlania małego bloku promocyjnego lub linku do strony osiągnięć. |
| `displayProductButtons` / `displayProductExtraContent` (lub podobne hooki strony produktu) | Na stronie produktu. | Potencjalnie do śledzenia wyświetleń/zakupów produktów dla kryteriów osiągnięć lub do sygnalizowania gamifikacji. |
| `displayFooter` | W stopce wszystkich stron front-office. | Do wyświetlania linku do strony osiągnięć lub ogólnej promocji gamifikacji. |
| `displayCustomerAccount` | W panelu „Moje konto” klienta. | **KRYTYCZNE:** Do dodania linku „Moje osiągnięcia” dla klientów. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia klienta. | **KRYTYCZNE:** Do sprawdzania, czy zamówienie spełnia jakiekolwiek kryteria osiągnięć (np. pierwsze zamówienie, całkowita wydana kwota, zakup produktu) i przyznawania osiągnięć. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Po dodaniu lub zaktualizowaniu produktu. | Mniej prawdopodobne, ale może być używane do aktualizacji kryteriów osiągnięć, jeśli dotyczą one atrybutów produktu. |
| `actionObjectCustomerAddAfter` | Po zarejestrowaniu nowego klienta. | Do inicjowania śledzenia osiągnięć dla nowych klientów. |
| `actionObjectReviewAddAfter` (lub podobne dla modułów recenzji) | Po przesłaniu recenzji produktu przez klienta. | **KRYTYCZNE:** Do sprawdzania, czy recenzja spełnia jakiekolwiek kryteria osiągnięć (np. liczba recenzji). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Customers Expertise, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnego działania modułu z Twoim sklepem PrestaShop.
