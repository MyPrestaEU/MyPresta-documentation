---
title: "Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami - Podręcznik sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop „Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami” od MyPresta.eu."
sidebar:
  label: "Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami - Podręcznik sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Loyalty points – Customer overview & points management na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-customer-overview-points-management.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/loyalty-points-customer-overview-points-management/)
>
> ---


# Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i są zazwyczaj dostępne we wszystkich kompatybilnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu „Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami”. Ten ekran zawiera ogólne ustawienia dotyczące zachowania modułu.

#### Włącz ręczne powiadomienia e-mail

-   **Co robi to ustawienie:** Ten przełącznik kontroluje, czy powiadomienie e-mail jest wysyłane do klienta, gdy ręcznie dostosujesz jego punkty lojalnościowe.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Jeśli ręcznie dodasz lub usuniesz punkty dla klienta, otrzyma on e-mail informujący o zmianie i jego nowym saldzie. Pomaga to informować klientów i buduje przejrzystość.
    -   *Gdy wyłączone:* Ręczne dostosowania punktów będą odbywać się cicho, bez żadnego powiadomienia e-mail do klienta. Może to być preferowane w przypadku drobnych wewnętrznych korekt lub jeśli zarządzasz komunikacją z klientami za pośrednictwem innych kanałów.
-   **Zalecana wartość:** TAK
-   **Scenariusz/przykład sprzedawcy:** Właśnie dodałeś 50 punktów bonusowych do konta klienta jako prezent urodzinowy. Jeśli to ustawienie jest włączone, klient natychmiast otrzymuje e-mail z informacją: „Wszystkiego najlepszego! Dodaliśmy 50 punktów lojalnościowych do Twojego konta. Twoje nowe saldo to X punktów.” Zwiększa to doświadczenie klienta i sprawia, że nagroda jest namacalna.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### Zarządzanie punktami lojalnościowymi klienta (Panel administracyjny > Katalog > Punkty lojalnościowe)

Jest to główny ekran zarządzania modułem, dostępny poprzez nową pozycję menu w Panelu administracyjnym PrestaShop.

-   **Nazwa ekranu i lokalizacja w menu:** **Katalog > Punkty lojalnościowe** (lub podobna, w zależności od wersji PrestaShop i dostosowania menu).
-   **Dostępne działania i ustawienia:**
    -   **Lista klientów:** Zobaczysz kompleksową listę wszystkich swoich klientów, wraz z ich aktualnymi saldami punktów lojalnościowych.
    -   **Wyszukiwanie i filtrowanie:** Łatwo znajdź konkretnych klientów po nazwie, adresie e-mail lub ID.
    -   **Wyświetl historię:** Dla każdego klienta możesz kliknąć, aby wyświetlić szczegółowy dziennik wszystkich transakcji punktów lojalnościowych (zarobionych, wydanych, wygasłych i ręcznie dostosowanych).
    -   **Dodaj/Usuń punkty:**
        -   Kliknij wiersz klienta lub ikonę „Edytuj”, aby uzyskać dostęp do jego indywidualnego interfejsu zarządzania punktami.
        -   Znajdziesz pola do ręcznego dodawania lub odejmowania określonej liczby punktów lojalnościowych.
        -   Pole „Powód” pozwala zanotować, dlaczego dokonano korekty (np. „Bonus urodzinowy”, „Rekompensata za opóźnione zamówienie”, „Korekta punktów”). Ten powód jest kluczowy dla Twoich wewnętrznych rejestrów i obsługi klienta.
        -   Po zapisaniu saldo klienta jest aktualizowane, a jeśli ustawienie „Włącz ręczne powiadomienia e-mail” jest aktywne, wysyłany jest e-mail.
    -   **Paginacja:** Zastosowana zostanie standardowa paginacja PrestaShop (`PS_LIST_LIMIT`), umożliwiająca kontrolę liczby klientów wyświetlanych na stronie.
-   **Efekt zmian:**
    -   **Dodawanie punktów:** Zwiększa saldo punktów lojalnościowych klienta. Może być używane do nagradzania klientów, oferowania rekompensat lub prowadzenia specjalnych promocji.
    -   **Usuwanie punktów:** Zmniejsza saldo punktów lojalnościowych klienta. Może to być konieczne do poprawienia błędów, cofnięcia punktów za zwrócone zamówienia lub zarządzania oszukańczymi działaniami.
    -   **Wyświetlanie historii:** Zapewnia przejrzysty ślad audytu wszystkich ruchów punktów, nieoceniony dla obsługi klienta i raportowania wewnętrznego.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Regularnie sprawdzaj salda punktów klientów:** Zwłaszcza po promocjach lub jeśli klienci zgłaszają rozbieżności.
    2.  **Starannie używaj pola „Powód”:** Zawsze podawaj jasny, zwięzły powód każdej ręcznej korekty. Zaoszczędzi to czas i zamieszanie później podczas przeglądania historii lub wyjaśniania zmian klientom.
    3.  **Wykorzystaj powiadomienia e-mail:** W przypadku pozytywnych korekt (bonusy, nagrody) włączenie powiadomień e-mail może znacznie zwiększyć satysfakcję klienta i świadomość jego korzyści lojalnościowych. W przypadku korekt rozważ, czy e-mail jest konieczny, czy wystarczą wewnętrzne notatki.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz ręczne powiadomienia e-mail | TAK | Kontroluje, czy klienci otrzymują e-mail, gdy ich punkty lojalnościowe są ręcznie dostosowywane. |
| Katalog > Punkty lojalnościowe | Lista klientów i wyszukiwanie | N/A | Wyświetla wszystkich klientów i ich aktualne salda punktów lojalnościowych. |
| Katalog > Punkty lojalnościowe | Dodaj/Usuń punkty | N/A | Umożliwia ręczne dostosowanie punktów lojalnościowych klienta. |
| Katalog > Punkty lojalnościowe | Powód korekty | N/A (Wymagane wprowadzenie) | Zapewnia wewnętrzną notatkę, dlaczego punkty zostały dodane lub usunięte. |
| Katalog > Punkty lojalnościowe | Wyświetl historię | N/A | Pokazuje szczegółowy dziennik wszystkich transakcji punktów lojalnościowych dla konkretnego klienta. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P1: Dodałem punkty, ale klient twierdzi, że nie otrzymał e-maila.**
O: Najpierw sprawdź, czy „Włącz ręczne powiadomienia e-mail” jest ustawione na TAK w głównej konfiguracji modułu. Jeśli tak, sprawdź logi e-mail swojego sklepu (jeśli są dostępne) lub logi poczty serwera, aby sprawdzić, czy e-mail został wysłany. Doradź również klientowi, aby sprawdził folder spamu/śmieci. Upewnij się, że ustawienia e-mail PrestaShop są poprawnie skonfigurowane, a Twój serwer pocztowy działa.

**P2: Nie mogę znaleźć pozycji menu „Punkty lojalnościowe” w moim Panelu administracyjnym.**
O: Po instalacji moduł powinien utworzyć nową pozycję menu, zazwyczaj w sekcji „Katalog” lub „Klienci”. Jeśli jej brakuje, spróbuj wyczyścić pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Jeśli nadal się nie pojawia, upewnij się, że moduł jest włączony i poprawnie zainstalowany. Sprawdź również swoje uprawnienia użytkownika w **Zaawansowane > Zespół > Profile**, aby upewnić się, że Twój profil administratora ma dostęp do kontrolera modułu.

**P3: Saldo punktów lojalnościowych klienta nie aktualizuje się w Front Office po ręcznej zmianie.**
O: Jest to zazwyczaj problem z pamięcią podręczną. Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Jeśli używasz modułu buforowania innej firmy lub CDN, wyczyść również jego pamięć podręczną. Moduł aktualizuje bazę danych bezpośrednio, więc Front Office powinien odzwierciedlać zmiany po odświeżeniu pamięci podręcznej.

**P4: Czy mogę importować/eksportować dane punktów lojalnościowych za pomocą tego modułu?**
O: Ten moduł koncentruje się na ręcznym zarządzaniu i przeglądaniu w Panelu administracyjnym PrestaShop. Nie zawiera wbudowanych funkcji importu/eksportu dla operacji masowych. Do takich zadań może być konieczne rozważenie niestandardowych zapytań do bazy danych lub innych specjalistycznych modułów.

**P5: Co się stanie, jeśli odinstaluję ten moduł?**
O: Po odinstalowaniu moduł usunie swoje dedykowane pozycje menu administracyjnego i potencjalnie swoje ustawienia konfiguracyjne. Jednak jest on zaprojektowany do zarządzania istniejącymi punktami lojalnościowymi, które są zazwyczaj częścią podstawowego systemu lojalnościowego PrestaShop lub innego modułu lojalnościowego. Same punkty powinny pozostać w bazie danych, ale straciłbyś wygodny interfejs zarządzania dostarczany przez ten moduł. Zawsze twórz kopię zapasową bazy danych przed odinstalowaniem jakiegokolwiek modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami” (`myprestaloyalty_customerpoints`) jest zbudowany zgodnie ze wzorcem MVC PrestaShop, głównie rozszerzając `Module` dla swojej podstawowej funkcjonalności i `AdminController` dla swojego dedykowanego interfejsu Panelu administracyjnego. Współdziała z podstawowym systemem lojalnościowym PrestaShop (lub kompatybilnym modułem lojalnościowym), zapewniając ulepszoną warstwę zarządzania. Moduł wprowadza niestandardowy `ObjectModel` do rejestrowania ręcznych korekt punktów, zapewniając ślad audytu.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front Office**: Ten moduł nie zawiera żadnych dedykowanych kontrolerów Front Office. Wszystkie interakcje z klientem dotyczące punktów lojalnościowych są obsługiwane przez podstawowy moduł lojalnościowy PrestaShop lub sam szablon.
-   **Kontrolery Panelu administracyjnego**:

    -   `controllers/admin/AdminMyprestaloyaltyCustomerPointsController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminMyprestaloyaltyCustomerPointsController` rozszerza `ModuleAdminController`.
        -   **Odpowiedzialność**: Jest to główny kontroler Panelu administracyjnego do zarządzania punktami lojalnościowymi klientów. Zapewnia widok listy klientów z ich saldami lojalnościowymi, umożliwia wyszukiwanie i filtrowanie oraz obsługuje formularz do ręcznego dodawania/usuwania punktów dla poszczególnych klientów. Zarządza encją `customer_points` (chociaż głównie współdziała z istniejącymi danymi punktów lojalnościowych, rejestruje również ręczne zmiany za pośrednictwem `MyprestaloyaltyCustomerPointsManualLog`).
        -   **Nazwa zakładki**: „Punkty lojalnościowe” (lub podobna, dynamicznie ustawiana podczas instalacji).
        -   **Zarządzana encja**: Wyświetla i umożliwia modyfikację punktów lojalnościowych klienta, rejestrując te zmiany.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Ten plik zazwyczaj służy jako symbol zastępczy lub proste przekierowanie w modułach PrestaShop. Może zawierać podstawową instrukcję `die()` lub przekierowanie, aby zapobiec bezpośredniemu dostępowi, zapewniając, że logika kontrolera jest wykonywana za pośrednictwem mechanizmu dyspozytorskiego PrestaShop. Nie zarządza konkretną encją ani nie zapewnia odrębnego widoku.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/MyprestaloyaltyCustomerPointsManualLog.php`
    -   **Nazwa klasy**: `MyprestaloyaltyCustomerPointsManualLog` rozszerza `ObjectModel`.
    -   **Tabela bazy danych**: `_myprestaloyalty_customer_points_manual_log` (lub podobna, z prefiksem `_DB_PREFIX_`).
    -   **Pola `$definition`**:
        -   `id_myprestaloyalty_customer_points_manual_log`: Klucz główny.
        -   `id_customer`: ID klienta, którego punkty zostały dostosowane.
        -   `id_employee`: ID pracownika, który dokonał korekty.
        -   `points_change`: Liczba dodanych lub usuniętych punktów (może być dodatnia lub ujemna).
        -   `reason`: Pole tekstowe wyjaśniające powód korekty.
        -   `date_add`: Sygnatura czasowa, kiedy dokonano korekty.
    -   **Kluczowe metody publiczne i logika biznesowa**: Ta klasa jest odpowiedzialna za utrwalanie szczegółów każdej ręcznej korekty punktów lojalnościowych dokonanej za pośrednictwem interfejsu Panelu administracyjnego. Zapewnia historyczny zapis, kluczowy dla audytu i obsługi klienta.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Wszystkie interakcje na ekranie zarządzania Panelu administracyjnego są obsługiwane przez domyślne mechanizmy jQuery i przesyłania formularzy PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Opiera się na domyślnych stylach Panelu administracyjnego PrestaShop dla swoich formularzy konfiguracyjnych i widoków list, zapewniając spójny wygląd i działanie.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Formularz konfiguracyjny oraz widoki listy/edycji Panelu administracyjnego są renderowane przy użyciu domyślnych szablonów `getContent()` i `ModuleAdminController` PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_myprestaloyalty_customer_points_manual_log`:
        -   `id_myprestaloyalty_customer_points_manual_log` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_customer` INT(10) UNSIGNED NOT NULL
        -   `id_employee` INT(10) UNSIGNED NOT NULL
        -   `points_change` INT(11) NOT NULL
        -   `reason` TEXT NULL
        -   `date_add` DATETIME NOT NULL
        -   PRIMARY KEY (`id_myprestaloyalty_customer_points_manual_log`)
        -   KEY `id_customer` (`id_customer`)
        -   KEY `id_employee` (`id_employee`)
    -   **Rekordy konfiguracji (w `ps_configuration`)**:
        -   `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Przechowuje wartość logiczną dla włączania/wyłączania powiadomień e-mail o ręcznych korektach punktów.
-   **Tabela zarejestrowanych hooków**:
    Ten moduł głównie zapewnia funkcjonalność Panelu administracyjnego i nie rejestruje żadnych hooków wyświetlania Front Office (`displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductExtraContent` itp.) ani hooków akcji (`actionValidateOrder`, `actionProductUpdate` itp.) w swojej podstawowej metodzie `install()`. Jego integracja odbywa się poprzez `AdminController` i bezpośrednią interakcję z bazą danych w celu logowania.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Punkty lojalnościowe – Przegląd klienta i zarządzanie punktami”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
