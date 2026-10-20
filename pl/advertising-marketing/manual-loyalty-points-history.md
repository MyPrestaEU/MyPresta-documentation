---
title: "Ręczne punkty lojalnościowe i historia - Podręcznik sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop „Ręczne punkty lojalnościowe i historia” od MyPresta.eu."
sidebar:
  label: "Ręczne punkty lojalnościowe i historia - Podręcznik sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Manual Loyalty Points & History na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/manual-loyalty-points-history.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/manual-loyalty-points-history/)
>
> ---


# Ręczne punkty lojalnościowe i historia

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Ten moduł wymaga również, aby główny system lojalnościowy PrestaShop (np. `myprestaloyalty` lub domyślny moduł lojalnościowy PrestaShop) był zainstalowany i aktywny, ponieważ rozszerza jego funkcjonalność.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, gdzie możesz ustawić globalne preferencje.

- **Włącz powiadomienia e-mail o ręcznych zmianach punktów:**
  - **Co robi to ustawienie:** Kontroluje, czy klienci otrzymują powiadomienie e-mail, gdy ich punkty lojalnościowe są ręcznie korygowane przez administratora.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Po ręcznym dodaniu lub odjęciu punktów dla klienta, na jego zarejestrowany adres e-mail zostanie wysłany e-mail informujący o zmianie i nowym saldzie.
    - *Gdy wyłączone (NIE):* Żadne powiadomienia e-mail nie będą wysyłane do klientów w przypadku ręcznych korekt punktów.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład sprzedawcy:** Włącz to, aby klienci byli w pełni poinformowani i zaangażowani w program lojalnościowy. Jeśli klient otrzymuje punkty jako rekompensatę, powiadomienie e-mail potwierdza działanie i wzmacnia obsługę klienta. Jeśli wyłączone, klienci mogą nie od razu zauważyć, że ich saldo się zmieniło.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

#### 2.2.1 Ręczne zarządzanie punktami lojalnościowymi (Panel administracyjny > Moduły > Ręczne punkty lojalnościowe)

Jest to główny ekran, na którym będziesz zarządzać i rejestrować wszystkie ręczne korekty punktów lojalnościowych. Ten ekran znajdziesz, przechodząc do **Moduły > Ręczne punkty lojalnościowe** w menu panelu administracyjnego PrestaShop.

Ten ekran przedstawia listę wszystkich historycznych ręcznych korekt punktów lojalnościowych. Możesz również dodać nowe korekty stąd.

**Dostępne działania i ustawienia:**

- **Przycisk „Dodaj nową korektę punktów lojalnościowych”:**

  - **Co robi ten przycisk:** Kliknięcie tego przycisku przenosi Cię do formularza, w którym możesz ręcznie dodać lub odjąć punkty lojalnościowe dla konkretnego klienta.
  - **Efekt kliknięcia tego przycisku:** Otwiera nowy formularz do utworzenia nowego wpisu punktów lojalnościowych.
- **Formularz korekty punktów lojalnościowych (dostępny poprzez „Dodaj nową korektę punktów lojalnościowych”):**

  - **Pole wyszukiwania klienta:**

    - **Co robi to pole:** Pozwala wyszukać i wybrać klienta, którego punkty lojalnościowe chcesz skorygować. Zacznij wpisywać imię lub e-mail klienta, a pojawi się lista pasujących klientów.
    - **Efekt zmiany tego ustawienia:** Po wybraniu klienta korekta zostanie zastosowana do jego konta.
    - **Zalecana wartość:** Wybierz prawidłowego klienta.
    - **Scenariusz / przykład sprzedawcy:** Musisz dodać punkty dla „Jana Kowalskiego”. Wpisz „Jan” i wybierz go z listy rozwijanej.
  - **Pole Punkty do dodania/odjęcia:**

    - **Co robi to pole:** Tutaj wprowadzasz liczbę punktów lojalnościowych do skorygowania.
    - **Efekt zmiany tego ustawienia:**
      - *Liczba dodatnia (np. 50):* Dodaje 50 punktów do salda lojalnościowego klienta.
      - *Liczba ujemna (np. -25):* Odejmuje 25 punktów od salda lojalnościowego klienta.
    - **Zalecana wartość:** Dokładna liczba punktów, które zamierzasz dodać lub odjąć.
    - **Scenariusz / przykład sprzedawcy:** Klient otrzymał uszkodzony przedmiot, więc dodajesz „100” punktów jako rekompensatę. Inny klient zwrócił przedmiot, za który zdobył punkty, więc odejmujesz „-50” punktów.
  - **Pole Okres ważności (dni):**

    - **Co robi to pole:** Definiuje, ile dni ręcznie dodane punkty będą ważne od daty korekty. Po tym okresie punkty wygasną.
    - **Efekt zmiany tego ustawienia:**
      - *Ustawione na liczbę (np. 365):* Punkty wygasną po 365 dniach.
      - *Ustawione na 0 lub puste:* Punkty nie będą miały daty ważności (lub będą przestrzegać domyślnego wygaśnięcia Twojego głównego modułu lojalnościowego, jeśli taki istnieje).
    - **Zalecana wartość:** Rozważ ogólną strategię swojego programu lojalnościowego. Jeśli chcesz zachęcić do szybkiej realizacji, ustaw krótszy okres. Dla ogólnej dobrej woli, dłuższy okres lub brak wygaśnięcia może być lepszy.
    - **Scenariusz / przykład sprzedawcy:** Dajesz 50 punktów jako prezent urodzinowy, ważny przez „30” dni, aby zachęcić do szybkiego zakupu. W przypadku dużej rekompensaty możesz pozostawić to pole puste, aby nie było daty ważności.
  - **Pole Powód / Komentarz:**

    - **Co robi to pole:** Pole tekstowe do zapisania powodu korekty punktów lojalnościowych. Służy to do wewnętrznego śledzenia i audytu.
    - **Efekt zmiany tego ustawienia:** Ten tekst zostanie zapisany w dzienniku lojalności, zapewniając jasną historię, dlaczego punkty zostały skorygowane. Nie jest widoczny dla klienta.
    - **Zalecana wartość:** Zawsze podawaj jasny i zwięzły powód.
    - **Scenariusz / przykład sprzedawcy:** „Rekompensata za uszkodzony produkt #12345”, „Prezent urodzinowy dla klienta VIP”, „Punkty za udział w wydarzeniu offline”.
  - **Przycisk „Zapisz”:**

    - **Co robi ten przycisk:** Stosuje korektę punktów lojalnościowych do konta klienta i zapisuje wpis w dzienniku historii.
    - **Efekt kliknięcia tego przycisku:** Punkty lojalnościowe klienta są aktualizowane, a nowy wpis pojawia się w tabeli „Ręczne zarządzanie punktami lojalnościowymi”. Jeśli włączone są powiadomienia e-mail, klient otrzymuje e-mail.
- **Tabela historii punktów lojalnościowych:**

  - **Co robi ta tabela:** Wyświetla chronologiczną listę wszystkich ręcznych korekt punktów lojalnościowych dokonanych za pomocą tego modułu.
  - **Kolumny:**
    - **ID:** Unikalny identyfikator wpisu w dzienniku.
    - **Klient:** Nazwa klienta, którego punkty zostały skorygowane.
    - **Punkty:** Liczba dodanych lub odjętych punktów.
    - **Ważność (dni):** Okres ważności ustawiony dla punktów.
    - **Powód:** Wewnętrzny komentarz podany dla korekty.
    - **Data dodania:** Data i godzina dokonania korekty.
    - **Administrator:** Nazwa administratora, który dokonał korekty.
  - **Efekt zmian:** Ta tabela zapewnia pełny ślad audytu. Możesz sortować i filtrować wpisy, aby przeglądać przeszłe korekty.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1. Gdy pojawi się sytuacja wymagająca ręcznej korekty punktów (np. skarga klienta, specjalna promocja), przejdź do **Moduły > Ręczne punkty lojalnościowe**.
2. Kliknij „Dodaj nową korektę punktów lojalnościowych”.
3. Wyszukaj i wybierz klienta.
4. Wprowadź liczbę punktów (dodatnia dla dodania, ujemna dla odjęcia).
5. Ustaw okres ważności, jeśli chcesz.
6. Co najważniejsze, dodaj jasny „Powód / Komentarz” do przyszłego odniesienia.
7. Kliknij „Zapisz”.
8. Przejrzyj tabelę historii, aby potwierdzić wpis.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz powiadomienia e-mail | TAK | Wyślij e-mail do klienta o ręcznych zmianach punktów. |
| Ręczne punkty lojalnościowe | Wyszukiwanie klienta | N/A | Wybierz klienta do korekty punktów. |
| Ręczne punkty lojalnościowe | Punkty do dodania/odjęcia | N/A | Wprowadź wartość dodatnią lub ujemną dla punktów. |
| Ręczne punkty lojalnościowe | Okres ważności (dni) | Puste (bez wygaśnięcia) | Ustaw wygaśnięcie dla ręcznie dodanych punktów. |
| Ręczne punkty lojalnościowe | Powód / Komentarz | N/A | Wewnętrzna notatka do śladu audytu. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Dodałem punkty, ale klient twierdzi, że nie otrzymał e-maila.**
O: Najpierw sprawdź, czy opcja „Włącz powiadomienia e-mail o ręcznych zmianach punktów” jest ustawiona na TAK w konfiguracji modułu. Jeśli tak, sprawdź dzienniki e-maili swojego sklepu (jeśli są dostępne) lub dzienniki poczty serwera, aby sprawdzić, czy e-mail został wysłany. Ponadto, doradź klientowi, aby sprawdził folder spamu lub niechcianej poczty. Upewnij się, że ustawienia e-mail PrestaShop są poprawnie skonfigurowane i pomyślnie wysyłają e-maile.

**P: Saldo punktów lojalnościowych klienta nie zaktualizowało się po dodaniu punktów.**
O: Ten moduł aktualizuje podstawowy system lojalnościowy PrestaShop. Jeśli saldo się nie wyświetla, najpierw wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Jeśli problem nadal występuje, upewnij się, że Twój główny moduł lojalnościowy (np. domyślny moduł lojalnościowy PrestaShop lub `myprestaloyalty`) jest poprawnie zainstalowany i aktywny, ponieważ ten moduł na nim polega.

**P: Czy mogę edytować korektę punktów lojalnościowych po jej zapisaniu?**
O: Nie, ze względu na audyt i integralność danych, poszczególne korekty punktów lojalnościowych nie mogą być edytowane po zapisaniu. Jeśli popełniłeś błąd, powinieneś dodać *nową* korektę, aby go poprawić (np. jeśli przypadkowo dodałeś 100 punktów zamiast 50, dodaj nowy wpis odejmujący 50 punktów) i wyraźnie zaznacz poprawkę w polu „Powód / Komentarz”.

**P: Co się stanie, jeśli odejmę więcej punktów, niż ma klient?**
O: System zazwyczaj pozwoli na odjęcie, co spowoduje ujemne saldo punktów lojalnościowych dla klienta. Może to być przydatne w określonych scenariuszach, ale ogólnie powinieneś upewnić się, że klienci mają wystarczającą liczbę punktów przed odjęciem.

**P: Jak dowiedzieć się, kto dokonał konkretnej korekty punktów?**
O: Kolumna „Administrator” w tabeli historii „Ręczne zarządzanie punktami lojalnościowymi” wyraźnie pokazuje, które konto administratora dokonało każdej korekty, zapewniając pełny ślad audytu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Ręczne punkty lojalnościowe i historia` (myprestaloyalty_manual) jest zaprojektowany jako standardowy moduł PrestaShop, rozszerzający podstawową funkcjonalność lojalnościową. Działa głównie w panelu administracyjnym, zapewniając interfejs administracyjny do ręcznych korekt punktów i logowania. Wykorzystuje wzorzec MVC PrestaShop dla swojego kontrolera administracyjnego i używa `ObjectModel` do trwałego przechowywania ręcznych wpisów dziennika. Moduł integruje się z istniejącym systemem lojalnościowym poprzez bezpośrednie manipulowanie punktami lojalnościowymi klienta.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery front-office**: Ten moduł nie zawiera żadnych dedykowanych kontrolerów front-office. Całe wyświetlanie punktów lojalnościowych dla klienta jest obsługiwane przez główny moduł lojalnościowy.
- **Kontrolery administracyjne back-office**:

  - `controllers/admin/AdminMyprestaloyaltyManualController.php`

    - **Nazwa klasy i klasa nadrzędna**: `AdminMyprestaloyaltyManualController` rozszerza `ModuleAdminController`.
    - **Odpowiedzialność**: Jest to główny kontroler administracyjny do zarządzania ręcznymi korektami punktów lojalnościowych. Obsługuje wyświetlanie listy dziennika lojalności (za pomocą `HelperList`) i formularza do dodawania nowych korekt (za pomocą `HelperForm`). Przetwarza przesłane formularze, waliduje dane, tworzy obiekty `MyprestaloyaltyManualLog` i aktualizuje punkty lojalnościowe klienta. Wyzwala również powiadomienia e-mail, jeśli są włączone.
    - **Nazwa zakładki**: „Ręczne punkty lojalnościowe” (w menu Moduły).
    - **Zarządzana encja**: `MyprestaloyaltyManualLog` (dziennik ręcznych korekt).
  - `controllers/admin/index.php`

    - **Odpowiedzialność**: Jest to pusty plik zastępczy, często dołączany do katalogów `controllers/admin` modułów PrestaShop, aby zapobiec listowaniu katalogów. Nie zawiera żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `classes/index.php`

  - **Odpowiedzialność**: Pusty plik zastępczy, aby zapobiec listowaniu katalogów.
- `classes/MyprestaloyaltyManualLog.php`

  - **Z jaką tabelą bazy danych wchodzi w interakcję**: `ps_myprestaloyalty_manual_log`
  - **Rozszerza `ObjectModel`**: Tak.
  - **Pola `$definition`**:
    - `id_myprestaloyalty_manual_log`: Klucz podstawowy.
    - `id_customer`: ID klienta, którego dotyczy.
    - `points`: Liczba skorygowanych punktów (może być dodatnia lub ujemna).
    - `validity`: Okres ważności w dniach dla punktów.
    - `reason`: Tekstowy powód korekty.
    - `id_employee`: ID administratora, który dokonał korekty.
    - `date_add`: Sygnatura czasowa dodania wpisu.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa**:
    - Standardowe metody `ObjectModel` (`add`, `update`, `delete`).
    - Obsługuje walidację danych dla swoich pól.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Wykorzystywany jest standardowy JS PrestaShop do obsługi formularzy i AJAX (np. wyszukiwanie klientów).

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Opiera się na domyślnych stylach panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Opiera się na domyślnych szablonach `HelperList` i `HelperForm` dla swojego interfejsu panelu administracyjnego.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_myprestaloyalty_manual_log`:
    - `id_myprestaloyalty_manual_log` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `points` INT(10) NOT NULL
    - `validity` INT(10) UNSIGNED DEFAULT 0
    - `reason` TEXT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_manual_log`)
    - KEY `id_customer` (`id_customer`)
- **Rekordy konfiguracji (w `ps_configuration`)**:

  - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Przechowuje wartość logiczną (0 lub 1) dla włączania/wyłączania powiadomień e-mail.
- **Tabela zarejestrowanych hooków**:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` panelu administracyjnego. | Służy do dołączania CSS/JS specyficznego dla modułu (chociaż ten moduł ich nie ma) lub do rejestrowania pozycji menu administratora. |
  | `actionCustomerAccountAdd` | Po utworzeniu nowego konta klienta. | Nie jest jawnie używany przez ten moduł, ale jest to wspólny hook lojalnościowy. |
  | `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Nie jest jawnie używany przez ten moduł, ale jest to wspólny hook lojalnościowy. |
  | `actionObjectCustomerUpdateAfter` | Po zaktualizowaniu obiektu klienta. | Nie jest jawnie używany przez ten moduł. |
  | `actionObjectCustomerDeleteAfter` | Po usunięciu obiektu klienta. | Nie jest jawnie używany przez ten moduł. |

  *Uwaga: Główna funkcjonalność modułu (dodawanie/odejmowanie punktów) jest wyzwalana bezpośrednio z jego kontrolera administracyjnego, a nie za pośrednictwem hooków front-office. Moduł wchodzi w interakcję z metodami podstawowego systemu lojalnościowego w celu dostosowania punktów.*

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Ręczne punkty lojalnościowe i historia”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
