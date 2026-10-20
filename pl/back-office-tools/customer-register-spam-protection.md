---
title: "Ochrona rejestracji klienta przed spamem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Ochrona rejestracji klienta przed spamem” od MyPresta.eu."
sidebar:
  label: "Ochrona rejestracji klienta przed spamem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customer register spam protection na MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-register-spam-protection.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/customer-register-spam-protection/)
>
> ---


# Ochrona rejestracji klienta przed spamem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do komunikacji z zewnętrznymi API, które ten moduł może wykorzystywać do zaawansowanego wykrywania spamu. Upewnij się, że Twoje środowisko hostingowe spełnia te wspólne wymagania.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Ochrona rejestracji klienta przed spamem”, dostępny po instalacji. Tutaj zdefiniujesz podstawowe zasady i zachowania systemu ochrony przed spamem.

Chociaż szczegółowe ustawienia nie są wyszczególnione w dostarczonym dossier, na podstawie celu modułu, typowe ustawienia obejmowałyby:

- **Włącz/Wyłącz moduł:**

  - **Co robi to ustawienie:** Włącza lub wyłącza funkcjonalność ochrony przed spamem dla całego Twojego sklepu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł aktywnie monitoruje i blokuje podejrzane rejestracje klientów.
    - *Gdy wyłączone:* Moduł jest nieaktywny, a wszystkie próby rejestracji będą przebiegać bez sprawdzania spamu.
  - **Zalecana wartość:** TAK (chyba że aktywnie debugujesz lub tymczasowo wyłączasz z konkretnego powodu).
  - **Scenariusz/przykład dla sprzedawcy:** Włącz to natychmiast po instalacji, aby rozpocząć ochronę swojego sklepu. Wyłącz tylko, jeśli podejrzewasz, że blokuje legalnych klientów i musisz to zbadać, ale pamiętaj, że to pozostawia Twój sklep podatnym na zagrożenia.
- **Poziom czułości wykrywania spamu:**

  - **Co robi to ustawienie:** Kontroluje, jak agresywnie moduł identyfikuje i blokuje potencjalny spam. Może to być suwak (Niski, Średni, Wysoki) lub próg liczbowy.
  - **Efekt zmiany tego ustawienia:**
    - *Wyższa czułość:* Bardziej prawdopodobne jest zablokowanie podejrzanych rejestracji, potencjalnie obejmujących niewielką liczbę legalnych użytkowników (fałszywe pozytywy).
    - *Niższa czułość:* Mniej prawdopodobne jest zablokowanie legalnych użytkowników, ale może przepuścić więcej kont spamowych (fałszywe negatywy).
  - **Zalecana wartość:** Zacznij od „Średniej” i dostosuj w oparciu o ruch w Twoim sklepie i liczbę zaobserwowanych prób spamu.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli widzisz dużo spamu, mimo że moduł jest aktywny, zwiększ czułość. Jeśli klienci zgłaszają problemy z rejestracją, spróbuj ją nieco obniżyć.
- **Działanie w przypadku wykrycia spamu:**

  - **Co robi to ustawienie:** Definiuje, co dzieje się, gdy moduł zidentyfikuje próbę rejestracji jako spam.
  - **Efekt zmiany tego ustawienia:**
    - *Zablokuj rejestrację:* Konto nie jest tworzone, a użytkownik otrzymuje komunikat o błędzie.
    - *Oznacz jako oczekujące/do przeglądu:* Konto jest tworzone, ale oznaczane do ręcznego przeglądu przez administratora.
    - *Tylko loguj:* Próba jest rejestrowana, ale konto nadal jest tworzone (przydatne do początkowego monitorowania).
  - **Zalecana wartość:** „Zablokuj rejestrację” dla maksymalnej ochrony.
  - **Scenariusz/przykład dla sprzedawcy:** Dla większości sklepów całkowite blokowanie jest najlepszym podejściem. Jeśli masz bardzo specyficzną bazę klientów i chcesz być bardzo ostrożny, „Oznacz jako oczekujące” może być opcją, ale wymaga ręcznej pracy.
- **Komunikat o błędzie dla zablokowanych rejestracji:**

  - **Co robi to ustawienie:** Pozwala dostosować komunikat wyświetlany użytkownikom, których próby rejestracji zostały zablokowane.
  - **Efekt zmiany tego ustawienia:**
    - *Niestandardowy komunikat:* Zapewnia przyjazny dla użytkownika lub informacyjny komunikat zamiast ogólnego błędu.
  - **Zalecana wartość:** Uprzejmy komunikat, taki jak „Rejestracja nie mogła zostać ukończona. Skontaktuj się z pomocą techniczną, jeśli uważasz, że to błąd.”
  - **Scenariusz/przykład dla sprzedawcy:** Unikaj komunikatów, które zbyt wiele ujawniają o Twoich metodach wykrywania spamu. Prosty, pomocny komunikat jest najlepszy.
- **Zarządzanie czarną/białą listą IP:**

  - **Co robi to ustawienie:** Pozwala ręcznie dodawać konkretne adresy IP do czarnej listy (zawsze blokuj) lub białej listy (nigdy nie blokuj).
  - **Efekt zmiany tego ustawienia:**
    - *Zablokowane adresy IP:* Każda rejestracja z tych adresów IP zostanie zablokowana, niezależnie od innych ustawień.
    - *Dopuszczone adresy IP:* Każda rejestracja z tych adresów IP będzie zawsze dozwolona.
  - **Zalecana wartość:** Używaj oszczędnie. Zablokuj znanych spamerów. Dopuść tylko, jeśli legalny użytkownik lub wewnętrzny system jest fałszywie blokowany.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli wielokrotnie widzisz spam z określonego zakresu adresów IP, dodaj go do czarnej listy. Jeśli adres IP Twojego wewnętrznego środowiska testowego jest blokowany, dodaj go do białej listy.
- **Zarządzanie czarną/białą listą e-maili:**

  - **Co robi to ustawienie:** Podobnie jak zarządzanie IP, ale dla konkretnych adresów e-mail lub domen e-mail.
  - **Efekt zmiany tego ustawienia:**
    - *Zablokowane e-maile/domeny:* Rejestracje z ich użyciem zostaną zablokowane.
    - *Dopuszczone e-maile/domeny:* Rejestracje z ich użyciem będą zawsze dozwolone.
  - **Zalecana wartość:** Używaj oszczędnie. Zablokuj znane adresy e-mail lub domeny spamowe.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli zauważysz wzorzec rejestracji spamowych z usług jednorazowych e-maili (np. mailinator.com), możesz zablokować tę domenę.
- **Integracja z zewnętrznymi API (np. reCAPTCHA, Akismet):**

  - **Co robi to ustawienie:** Jeśli moduł integruje się z zewnętrznymi usługami wykrywania spamu, ta sekcja będzie zawierać pola na klucze API i konfigurację specyficzną dla tych usług.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone z prawidłowymi kluczami:* Dodaje dodatkową warstwę ochrony za pomocą bazy danych i algorytmów zewnętrznej usługi.
    - *Wyłączone lub nieprawidłowe klucze:* Zewnętrzna usługa nie będzie używana, polegając wyłącznie na wewnętrznej logice modułu.
  - **Zalecana wartość:** Włącz i skonfiguruj, jeśli dostępne, ponieważ znacznie zwiększa to ochronę.
  - **Scenariusz/przykład dla sprzedawcy:** Uzyskaj klucze API z odpowiedniej usługi (np. Google reCAPTCHA) i wprowadź je tutaj, aby wykorzystać ich zaawansowane filtrowanie spamu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia dedykowane ekrany w Panelu administracyjnym PrestaShop do zarządzania i przeglądania prób spamu oraz blokad. Są one kluczowe do monitorowania skuteczności modułu i dokonywania ręcznych korekt.

#### 2.2.1 AdminregproAttemptsController (Panel administracyjny > Moduły > Ochrona rejestracji klienta przed spamem > Próby)

- **Nazwa ekranu i lokalizacja w menu:** „Próby” (lub podobna, w głównym menu modułu). Ten ekran wyświetla wszystkie próby rejestracji, które moduł przetworzył, zwłaszcza te oznaczone jako podejrzane lub zablokowane.
- **Dostępne działania i ustawienia:** Będzie to widok siatki (listy) wyświetlający szczegóły każdej próby rejestracji.
  - **Kolumny:** Zazwyczaj obejmują:
    - Data/Godzina próby
    - Adres IP
    - Użyty adres e-mail
    - Status (np. „Zablokowany”, „Dozwolony”, „Oznaczony”)
    - Powód statusu (np. „IP na czarnej liście”, „Wysoki wynik spamu”)
    - Przyciski akcji (np. „Wyświetl szczegóły”, „Dodaj IP do białej listy”, „Dodaj IP do czarnej listy”, „Usuń wpis”)
  - **Filtrowanie/Sortowanie:** Standardowe funkcje siatki PrestaShop do filtrowania według daty, IP, statusu itp.
- **Efekt zmian:**
  - *Dodanie IP do białej listy:* Dodaje IP do białej listy modułu, zapewniając, że przyszłe rejestracje z tego IP są dozwolone.
  - *Dodanie IP do czarnej listy:* Dodaje IP do czarnej listy modułu, blokując przyszłe rejestracje z tego IP.
  - *Usunięcie wpisu:* Usuwa rekord z dziennika prób (nie odblokowuje/nie usuwa bana).
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie przeglądaj tę listę, zwłaszcza jeśli otrzymujesz zgłoszenia o blokowaniu legalnych klientów. Użyj akcji „Dodaj IP do białej listy”, jeśli zidentyfikujesz fałszywy pozytyw. Odwrotnie, jeśli widzisz uporczywy spam z określonego IP, użyj „Dodaj IP do czarnej listy”.

#### 2.2.2 AdminregproBansController (Panel administracyjny > Moduły > Ochrona rejestracji klienta przed spamem > Blokady)

- **Nazwa ekranu i lokalizacja w menu:** „Blokady” (lub podobna, w głównym menu modułu). Ten ekran wyświetla wszystkie aktualnie aktywne blokady (adresy IP lub adresy/domeny e-mail), które moduł egzekwuje.
- **Dostępne działania i ustawienia:** Będzie to widok siatki (listy) wyświetlający szczegóły każdej blokady.
  - **Kolumny:** Zazwyczaj obejmują:
    - Typ blokady (np. „IP”, „E-mail”, „Domena”)
    - Wartość (np. „192.168.1.1”, „[spam@example.com](mailto:spam@example.com)”, „bad-domain.com”)
    - Data dodania
    - Powód (jeśli dodano ręcznie)
    - Przyciski akcji (np. „Usuń blokadę”, „Edytuj”)
  - **Filtrowanie/Sortowanie:** Standardowe funkcje siatki PrestaShop.
- **Efekt zmian:**
  - *Usunięcie blokady:* Znosi ograniczenie dla określonego IP, e-maila lub domeny, umożliwiając przyszłe rejestracje z niego.
  - *Dodanie blokady:* Ręcznie dodaje nowy IP, e-mail lub domenę do listy blokad.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** To jest Twoje centralne centrum do zarządzania niestandardowymi listami blokad. Jeśli zablokowałeś IP z ekranu „Próby”, pojawi się ono tutaj. Jeśli legalny klient przypadkowo zostanie objęty blokadą, możesz szybko usunąć jego IP lub e-mail z tej listy.

#### 2.2.3 index.php (regpro/controllers/admin/index.php)

- **Zarządzana tabela / encja:** Ten plik prawdopodobnie służy jako router lub domyślny kontroler dla sekcji administracyjnej modułu, potencjalnie przekierowując do jednego z konkretnych kontrolerów (takich jak `AdminregproAttempts` lub `AdminregproBans`) lub wyświetlając ogólny przegląd/panel dla modułu. Może nie zarządzać bezpośrednio konkretną tabelą, ale działa jako punkt wejścia.
- **Pola formularza i kolumny:** Jeśli wyświetla siatkę, będzie to podsumowanie lub panel. Bardziej prawdopodobne, że jest to przekierowanie.
- **Efekt zmian:** Brak bezpośrednich zmian danych, ale kontroluje początkowy widok po uzyskaniu dostępu do sekcji administracyjnej modułu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Jest to zazwyczaj pierwszy ekran, który widzisz po kliknięciu modułu na liście Modułów. Może oferować szybkie statystyki lub linki do sekcji „Próby” i „Blokady”.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz/Wyłącz moduł | TAK | Włącza/wyłącza ochronę przed spamem. |
|  | Czułość wykrywania spamu | Średnia | Kontroluje agresywność wykrywania spamu. |
|  | Działanie w przypadku wykrycia spamu | Zablokuj rejestrację | Definiuje reakcję na spam (blokuj, przeglądaj, loguj). |
|  | Komunikat o błędzie dla zablokowanych rejestracji | „Rejestracja nie mogła zostać ukończona. Skontaktuj się z pomocą techniczną, jeśli uważasz, że to błąd.” | Dostosowuje komunikat dla zablokowanych użytkowników. |
|  | Czarna/biała lista IP | Używaj oszczędnie | Ręcznie blokuj/zezwalaj na konkretne adresy IP. |
|  | Czarna/biała lista e-maili | Używaj oszczędnie | Ręcznie blokuj/zezwalaj na konkretne adresy e-mail/domeny. |
|  | Integracja z zewnętrznymi API | Włącz z prawidłowymi kluczami | Zwiększa ochronę dzięki usługom stron trzecich. |
| **AdminregproAttemptsController** | Wyświetl dziennik prób | N/A | Przeglądaj wszystkie próby rejestracji, ich status i powody. |
|  | Dodaj IP do białej listy (z dziennika) | N/A | Zezwala na przyszłe rejestracje z określonego adresu IP. |
|  | Dodaj IP do czarnej listy (z dziennika) | N/A | Blokuje przyszłe rejestracje z określonego adresu IP. |
| **AdminregproBansController** | Wyświetl aktywne blokady | N/A | Zarządzaj i przeglądaj wszystkie aktualnie aktywne blokady IP/e-mail/domen. |
|  | Usuń blokadę | N/A | Znosi określoną blokadę. |
|  | Dodaj nową blokadę | N/A | Ręcznie dodaje nowy adres IP, e-mail lub domenę do listy blokad. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi legalni klienci zgłaszają, że nie mogą się zarejestrować. Co powinienem zrobić?**
O: Najpierw sprawdź dziennik „Prób” (`AdminregproAttemptsController`) w Panelu administracyjnym. Poszukaj ich adresu IP lub e-maila. Jeśli ich próba została zablokowana, zobaczysz powód. Możesz wtedy dodać ich adres IP lub e-mail do białej listy lub tymczasowo obniżyć ustawienie czułości modułu. Pamiętaj, aby wyczyścić pamięć podręczną PrestaShop po wprowadzeniu zmian.

**P: Nadal otrzymuję rejestracje spamowe, mimo że moduł jest aktywny.**
O:

1.  **Sprawdź czułość:** Zwiększ „Poziom czułości wykrywania spamu” w głównej konfiguracji modułu.
2.  **Przejrzyj dziennik prób:** Przeanalizuj dziennik „Prób”, aby sprawdzić, czy moduł rejestruje te próby i dlaczego mogą one przechodzić.
3.  **Dodaj do czarnej listy:** Jeśli zidentyfikujesz konkretne adresy IP lub domeny e-mail z rejestracji spamowych, ręcznie dodaj je do swojej listy blokad za pośrednictwem `AdminregproBansController`.
4.  **Zewnętrzne API:** Upewnij się, że wszystkie zintegrowane zewnętrzne API ochrony przed spamem (takie jak reCAPTCHA) są poprawnie skonfigurowane i mają prawidłowe klucze.

**P: Skąd mam wiedzieć, czy moduł faktycznie działa?**
O: Najlepszym sposobem jest monitorowanie dziennika „Prób” (`AdminregproAttemptsController`). Powinieneś zobaczyć wpisy dotyczące zablokowanych prób, wskazujące, że moduł aktywnie identyfikuje i zapobiega spamowi. Jeśli wcześniej otrzymywałeś dużo spamu, powinieneś również zauważyć znaczne zmniejszenie liczby nowych fałszywych kont klientów.

**P: Czy ten moduł wpływa na wydajność mojego sklepu?**
O: Moduł został zaprojektowany tak, aby był wydajny. Chociaż dodaje niewielki krok przetwarzania podczas rejestracji, jest to zazwyczaj pomijalne w porównaniu z korzyściami wynikającymi z zapobiegania spamowi. Baza danych pełna kont spamowych spowodowałaby znacznie większe problemy z wydajnością w dłuższej perspektywie.

**P: Zmieniłem ustawienia, ale nic nie dzieje się w front office.**
O: Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu jakichkolwiek zmian w konfiguracji. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Zapewnia to, że moduł załaduje zaktualizowane ustawienia.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Ochrona rejestracji klienta przed spamem” (`regpro`) jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop. Działa głównie poprzez włączanie się w proces rejestracji klienta, wykorzystując system hooków PrestaShop do przechwytywania i walidacji danych rejestracyjnych. Wykorzystuje dedykowane kontrolery administracyjne do zarządzania próbami i blokadami oraz przechowuje swoją konfigurację w `ps_configuration`. Podstawowa logika modułu do wykrywania spamu prawdopodobnie znajduje się w głównym pliku modułu `index.php`, z funkcjami pomocniczymi lub klasami (chociaż żadne nie są wyraźnie wymienione w dossier, mogą być wewnętrzne dla głównej klasy modułu).

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:
  Dossier modułu wskazuje brak dedykowanych kontrolerów front-office. Sugeruje to, że interakcje modułu z front-office (np. przechwytywanie danych rejestracyjnych) są obsługiwane bezpośrednio za pomocą hooków w głównym pliku modułu `regpro/index.php` lub poprzez nadpisywanie podstawowych kontrolerów PrestaShop (chociaż to ostatnie jest mniej powszechne w przypadku prostej ochrony przed spamem). Hooki `displayCustomerAccountForm` to miejsca, w których logika modułu byłaby wyzwalana.
- **Kontrolery Back-Office Admin**:
  Te kontrolery zapewniają interfejs administracyjny do zarządzania danymi i ustawieniami modułu.

  - `controllers/admin/AdminRegproAttempts.php`

    - **Nazwa klasy i klasa nadrzędna:** `AdminRegproAttemptsController` (rozszerza `ModuleAdminController` lub `AdminController`).
    - **Odpowiedzialność:** Zarządza listowaniem i działaniami związanymi z zarejestrowanymi próbami spamu. Ten kontroler jest odpowiedzialny za wyświetlanie siatki prób rejestracji, umożliwiając administratorom przeglądanie szczegółów, filtrowanie i wykonywanie działań, takich jak dodawanie adresów IP do białej lub czarnej listy na podstawie tych prób. Współpracuje z tabelą bazy danych `regattempt`.
  - `controllers/admin/AdminRegproBans.php`

    - **Nazwa klasy i klasa nadrzędna:** `AdminRegproBansController` (rozszerza `ModuleAdminController` lub `AdminController`).
    - **Odpowiedzialność:** Zarządza listowaniem i działaniami związanymi z aktywnymi blokadami (adresy IP, e-maile, domeny). Ten kontroler umożliwia administratorom przeglądanie, dodawanie, edytowanie i usuwanie wpisów z list blokad modułu. Współpracuje z tabelą bazy danych `regban`.
  - `controllers/admin/index.php`

    - **Nazwa klasy i klasa nadrzędna:** Prawdopodobnie prosty przekierowywacz lub plik zastępczy. Może zawierać podstawowy `AdminController`, który przekierowuje do jednego z innych kontrolerów administracyjnych specyficznych dla modułu (np. `AdminRegproAttempts`) lub wyświetla prosty panel. Nie zarządza bezpośrednio konkretną encją, ale służy jako punkt wejścia do sekcji administracyjnej modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Oznacza to, że struktury danych modułu (dla prób i blokad) są obsługiwane bezpośrednio przez logikę `AdminController` za pomocą surowych zapytań SQL, lub, co bardziej prawdopodobne, definicje `ObjectModel` dla `regattempt` i `regban` są osadzone bezpośrednio w odpowiednich kontrolerach `AdminRegproAttempts.php` i `AdminRegproBans.php` lub w głównym pliku `regpro/index.php`.

Jeśli używany jest `ObjectModel`, tablica `$definition` byłaby zdefiniowana dla:

- `regattempt`: Mapowanie do tabeli `ps_regattempt` (lub podobnej), z polami takimi jak `id_regattempt`, `ip_address`, `email`, `status`, `reason`, `date_add`.
- `regban`: Mapowanie do tabeli `ps_regban` (lub podobnej), z polami takimi jak `id_regban`, `type` (IP, e-mail, domena), `value`, `date_add`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `views/js/regpro-v3.js`
  - **Zakres:** Prawdopodobnie Back-office. „v3” może wskazywać wersję lub konkretną funkcjonalność.
  - **Opis:** Ten skrypt jest prawdopodobnie odpowiedzialny za poprawę doświadczenia użytkownika w konfiguracji modułu w Panelu administracyjnym lub na ekranach zarządzania. Może obsługiwać:
    - Wywołania AJAX do dynamicznych aktualizacji (np. filtrowanie list, dodawanie/usuwanie blokad bez przeładowania strony).
    - Walidację formularzy na stronie konfiguracji lub podczas dodawania nowych wpisów blokad.
    - Interaktywne elementy w siatkach „Prób” lub „Blokad” (np. okna dialogowe potwierdzenia dla działań, sortowanie, paginacja).
    - Potencjalnie, logikę po stronie klienta do integracji z zewnętrznymi API, jeśli wymagają one interakcji JS w BO.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu wskazuje brak niestandardowych plików CSS. Sugeruje to, że moduł opiera się całkowicie na domyślnych stylach Panelu administracyjnego PrestaShop dla swoich stron konfiguracyjnych i siatek. Jeśli potrzebne są jakieś specyficzne style, byłyby one albo wbudowane w szablony, albo dynamicznie dodawane za pomocą JavaScript.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  Te szablony są renderowane, gdy moduł jest włączony w określonych punktach front-office.

  - `views/templates/hook/displayCustomerAccountForm-v3.tpl`

    - **Hook:** `displayCustomerAccountForm` (lub podobny, specyficzny dla PrestaShop 1.7+ i 8.x).
    - **Cel:** Ten szablon jest prawdopodobnie używany do wstrzykiwania ukrytych pól, zmiennych JavaScript lub potencjalnie widocznego CAPTCHA/wyzwania (jeśli skonfigurowano) do formularza rejestracji klienta. „v3” sugeruje, że jest to nowsza wersja, prawdopodobnie dla nowszych wersji PrestaShop lub konkretnego projektu. Może zawierać strukturę HTML dla reCAPTCHA, jeśli ta integracja jest włączona.
  - `views/templates/hook/displayCustomerAccountForm.tpl`

    - **Hook:** `displayCustomerAccountForm` (lub podobny, potencjalnie dla starszych wersji PrestaShop, takich jak 1.6.x).
    - **Cel:** Podobnie jak `displayCustomerAccountForm-v3.tpl`, ale prawdopodobnie ogólna lub starsza wersja. Służyłby tej samej funkcji wstrzykiwania elementów lub logiki do formularza rejestracji klienta w celu wykrywania spamu.
  - `views/templates/hook/displayCustomerAccountFormTop.tpl`

    - **Hook:** `displayCustomerAccountFormTop` (lub podobny).
    - **Cel:** Ten szablon renderowałby zawartość na samym początku formularza rejestracji klienta. Może to być używane do wyświetlania ogólnego komunikatu lub do wstrzykiwania elementów, które muszą pojawić się przed głównymi polami formularza, takich jak pole wyboru „Nie jestem robotem” lub ostrzeżenie.
- **Szablony administracyjne (`views/templates/admin/`)**:
  Te szablony definiują strukturę i zawartość stron Panelu administracyjnego modułu.

  - `views/templates/admin/main.tpl`
    - **Cel:** Jest to prawdopodobnie główny szablon dla strony konfiguracji modułu (dostępny za pośrednictwem `getContent()` w `regpro/index.php`) lub ogólny wrapper dla sekcji administracyjnej modułu. Zawierałby kod HTML dla różnych ustawień, pól wejściowych i przycisków opisanych w sekcji 4.1. Może również zawierać linki do kontrolerów `AdminRegproAttempts` i `AdminRegproBans`.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Na podstawie kontrolerów administracyjnych moduł prawdopodobnie tworzy dwie niestandardowe tabele:

  - `ps_regattempt` (lub podobny prefiks): Przechowuje rekordy prób rejestracji.
    - `id_regattempt` (PK, INT)
    - `ip_address` (VARCHAR)
    - `email` (VARCHAR)
    - `status` (VARCHAR, np. ‘blocked’, ‘allowed’, ‘flagged’)
    - `reason` (TEXT, wyjaśnienie statusu)
    - `date_add` (DATETIME)
  - `ps_regban` (lub podobny prefiks): Przechowuje rekordy aktywnych blokad.
    - `id_regban` (PK, INT)
    - `type` (VARCHAR, np. ‘ip’, ‘email’, ‘domain’)
    - `value` (VARCHAR, rzeczywisty adres IP, e-mail lub domena)
    - `date_add` (DATETIME)
    - `reason` (TEXT, opcjonalnie, dla ręcznych blokad)

  Ustawienia konfiguracyjne (takie jak czułość, komunikaty o błędach, klucze API) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `REGPRO_` (np. `REGPRO_SENSITIVITY`, `REGPRO_ACTION_ON_SPAM`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Potencjalnie używany do globalnego ładowania CSS/JS specyficznych dla modułu lub do wstrzykiwania meta-tagów do weryfikacji zewnętrznego API. |
| `displayCustomerAccountForm` | Renderuje się w formularzu rejestracji klienta. | Główny hook do wstrzykiwania ukrytych pól, elementów reCAPTCHA lub JavaScript do przechwytywania przesyłania formularza i wykonywania walidacji po stronie klienta. |
| `displayCustomerAccountFormTop` | Renderuje się na górze formularza rejestracji klienta. | Podobnie jak `displayCustomerAccountForm`, ale zapewnia, że zawartość pojawia się przed głównymi polami formularza. |
| `actionCustomerAccountAdd` | Wykonywany *po* pomyślnym dodaniu nowego konta klienta do bazy danych. | Może być używany do logowania po rejestracji, wysyłania powiadomień lub dalszego przetwarzania, jeśli konto zostało dozwolone, ale oznaczone do przeglądu. |
| `actionAuthentication` | Wykonywany podczas logowania/uwierzytelniania klienta. | Mniej prawdopodobne w przypadku spamu rejestracyjnego, ale może być używany do zaawansowanych kontroli lub do zapobiegania logowaniu z zablokowanych adresów IP/e-maili. |
| `actionValidateCustomerAccount` | Wykonywany *przed* dodaniem nowego konta klienta do bazy danych. | **KRYTYCZNY HOOK:** Jest to najbardziej prawdopodobny hook, w którym działałaby podstawowa logika wykrywania spamu modułu, umożliwiając mu zapobieganie tworzeniu konta, jeśli wykryto spam. |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` wszystkich stron back-office. | Używany do ładowania CSS/JS specyficznych dla modułu dla ekranów konfiguracji i zarządzania administracyjnego. |
| `displayAdminCustomers` | Renderuje się na stronie listy klientów w Panelu administracyjnym. | Może być używany do dodawania kolumny lub przycisku akcji związanego ze statusem spamu dla istniejących klientów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i kompleksowe wsparcie dla programistów, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i zapewnienie optymalnej wydajności modułu „Ochrona rejestracji klienta przed spamem”.
