---
title: "Block IP address Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop Block IP address Pro od MyPresta.eu."
sidebar:
  label: "Block IP address Pro"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Block IP address Pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/block-ip-address-pro/)
>
> ---


# Block IP address Pro

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Block IP address Pro)

Jest to główny ekran konfiguracji modułu, gdzie definiujesz globalne zachowanie dla zablokowanych odwiedzających.

-   **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Block IP address Pro > Konfiguruj

#### Ustawienia i opcje:

1.  **Wyświetlaj powiadomienia o aktualizacjach**
    -   **Co robi to ustawienie:** Kontroluje, czy otrzymujesz powiadomienia w panelu administracyjnym PrestaShop, gdy dostępna jest nowa wersja modułu „Block IP address Pro”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zobaczysz alerty lub wiadomości w panelu administracyjnym, jeśli zostanie wydana aktualizacja, co pomoże Ci utrzymać moduł w aktualnym stanie.
        -   *Gdy wyłączone:* Nie będziesz otrzymywać tych powiadomień i będziesz musiał ręcznie sprawdzać aktualizacje na MyPresta.eu.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia, że zawsze będziesz świadomy nowych funkcji, poprawek błędów lub ulepszeń bezpieczeństwa dla modułu.

2.  **Wiadomość dla zablokowanych użytkowników (`banippro_msg`)**
    -   **Co robi to ustawienie:** Jest to niestandardowa wiadomość, która zostanie wyświetlona użytkownikom, których adres IP został zablokowany, *jeśli* zdecydujesz się ich nie przekierowywać.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione:* Zablokowani użytkownicy zobaczą ten konkretny tekst na pustej stronie zamiast zawartości Twojego sklepu.
        -   *Gdy puste:* Jeśli przekierowanie jest również wyłączone, zablokowani użytkownicy mogą zobaczyć ogólny błąd lub pustą stronę bez konkretnej wiadomości.
    -   **Zalecana wartość:** „Dostęp do tego sklepu został zablokowany dla Twojego adresu IP.” (lub podobna uprzejma, ale stanowcza wiadomość).
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć wyświetlić „Przepraszamy, ale dostęp z Twojej lokalizacji został ograniczony z powodu nietypowej aktywności”, aby poinformować użytkownika bez podawania zbyt wielu szczegółów.

3.  **Przekieruj zablokowanych użytkowników (`banippro_redirect`)**
    -   **Co robi to ustawienie:** Określa, czy zablokowani użytkownicy mają zobaczyć wiadomość, czy zostać automatycznie przekierowani na inną stronę internetową.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zablokowani użytkownicy zostaną natychmiast przekierowani na adres URL określony w ustawieniu „Adres URL przekierowania”.
        -   *Gdy wyłączone:* Zablokowani użytkownicy zobaczą zdefiniowaną przez Ciebie „Wiadomość dla zablokowanych użytkowników”.
    -   **Zalecana wartość:** TAK (Przekierowanie jest często czystszym doświadczeniem użytkownika niż pusta strona z wiadomością).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz całkowicie odesłać spamerów z Twojej witryny lub skierować problematycznego klienta na stronę obsługi klienta, włącz tę opcję.

4.  **Adres URL przekierowania (`banippro_url`)**
    -   **Co robi to ustawienie:** Konkretny adres internetowy (URL), na który zablokowani użytkownicy zostaną przekierowani, jeśli włączone jest ustawienie „Przekieruj zablokowanych użytkowników”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wypełnione prawidłowym adresem URL:* Zablokowani użytkownicy zostaną wysłani na tę konkretną stronę.
        -   *Gdy puste:* Jeśli przekierowanie jest włączone, ale nie podano adresu URL, zachowanie modułu może być nieprzewidywalne lub może domyślnie wyświetlać wiadomość.
    -   **Zalecana wartość:** Adres URL strony głównej Twojego sklepu (np. `https://www.twoj-sklep.com/`), lub konkretna strona „Kontakt”, a nawet zewnętrzna witryna, taka jak Google.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz przekierować ich na `https://www.twoj-sklep.com/kontakt`, jeśli chcesz, aby się z Tobą skontaktowali, lub na `https://www.google.com`, aby po prostu usunąć ich z Twojej witryny.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Wyświetlaj powiadomienia o aktualizacjach | TAK | Pokazuje alerty o nowych wersjach modułu. |
| Konfiguracja modułu | Wiadomość dla zablokowanych użytkowników | „Dostęp do tego sklepu został zablokowany dla Twojego adresu IP.” | Tekst wyświetlany zablokowanym użytkownikom, jeśli nie są przekierowywani. |
| Konfiguracja modułu | Przekieruj zablokowanych użytkowników | TAK | Jeśli włączone, wysyła zablokowanych użytkowników na określony adres URL. |
| Konfiguracja modułu | Adres URL przekierowania | Adres URL strony głównej Twojego sklepu | Cel dla przekierowanych zablokowanych użytkowników. |

### 2.2 Dedykowany ekran administracyjny: Zarządzanie adresami IP (Panel administracyjny > Moduły > Block IP address Pro > Zarządzaj adresami IP)

Jest to główny ekran zarządzania, gdzie dodajesz, edytujesz, aktywujesz i dezaktywujesz konkretne adresy IP do zablokowania.

-   **Lokalizacja menu:** Po zainstalowaniu modułu, nowa pozycja menu pojawi się pod **Moduły > Block IP address Pro** (lub podobnie, w zależności od wersji PrestaShop i rejestracji menu modułu). Kliknij „Zarządzaj adresami IP” lub „Zablokuj adresy IP”.

#### Dostępne działania i ustawienia:

1.  **Tabela listy adresów IP:**
    -   Ta tabela wyświetla wszystkie adresy IP, które skonfigurowałeś do blokowania.
    -   **Kolumny:**
        -   **ID:** Unikalny identyfikator wpisu zablokowanego adresu IP.
        -   **Adres IP:** Rzeczywisty adres IP, który jest blokowany (np. `192.168.1.1`, `203.0.113.45`).
        -   **Liczba wyświetleń:** Statystyka pokazująca, ile razy ten konkretny adres IP próbował uzyskać dostęp do Twojego sklepu i został zablokowany. Jest to nieocenione do identyfikacji uporczywych zagrożeń.
        -   **Komentarz:** Twoja wewnętrzna notatka o tym, dlaczego ten adres IP został zablokowany (np. „Bot spamujący”, „Skrobanie przez konkurencję”, „Problematyczny klient”).
        -   **Aktywny:** Przełącznik (Wł./Wył.) do szybkiego włączania lub wyłączania blokowania dla tego konkretnego adresu IP bez usuwania wpisu.
        -   **Działania:** Przyciski „Edytuj” lub „Usuń” dla poszczególnych wpisów IP.

2.  **Dodawanie nowego adresu IP:**
    -   Kliknij przycisk „Dodaj nowy adres IP” (lub podobny, zazwyczaj ikona plusa lub przycisk „Dodaj nowy” w prawym górnym rogu tabeli).
    -   **Pola formularza:**
        -   **IP:** Wprowadź dokładny adres IP, który chcesz zablokować.
        -   **Komentarz:** Dodaj opisową notatkę dla Twojej referencji (np. „Znane źródło spamu z analityki”, „Klient 'Jan Kowalski' powodujący problemy”).
        -   **Aktywny:** Wybierz „Wł.”, aby natychmiast aktywować blokadę, lub „Wył.”, aby zapisać wpis, ale na razie pozostawić go nieaktywnym.
    -   **Zapisz:** Kliknij „Zapisz”, aby dodać nowy adres IP do listy blokad.

3.  **Edytowanie istniejącego adresu IP:**
    -   Kliknij ikonę „Edytuj” obok adresu IP w tabeli listy.
    -   Możesz modyfikować „IP”, „Komentarz” i status „Aktywny”.
    -   **Zapisz:** Kliknij „Zapisz”, aby zastosować zmiany.

4.  **Usuwanie adresu IP:**
    -   Kliknij ikonę „Usuń” obok adresu IP.
    -   Potwierdź usunięcie. Spowoduje to trwałe usunięcie adresu IP z listy blokad.

#### Efekt zmian:
-   **Dodawanie adresu IP:** Po zapisaniu i aktywowaniu, każdy odwiedzający próbujący uzyskać dostęp do Twojego sklepu z tego adresu IP zostanie natychmiast zablokowany lub przekierowany zgodnie z globalną konfiguracją modułu.
-   **Edytowanie adresu IP:** Zmiany w adresie IP, komentarzu lub statusie aktywności zaczną obowiązywać natychmiast.
-   **Dezaktywowanie adresu IP:** Adres IP pozostaje na Twojej liście, ale odwiedzający z tego adresu IP nie będą już blokowani. Jest to przydatne w przypadku tymczasowych blokad lub jeśli adres IP został zablokowany przez pomyłkę.
-   **Usuwanie adresu IP:** Adres IP jest trwale usuwany z listy blokad, a odwiedzający z tego adresu IP odzyskują pełny dostęp do Twojego sklepu.

#### Zalecany przepływ pracy dla codziennego zarządzania sklepem:
1.  **Monitoruj analitykę:** Regularnie sprawdzaj analitykę swojej witryny pod kątem podejrzanych wzorców ruchu, wysokiego współczynnika odrzuceń z konkretnych adresów IP lub nietypowej aktywności.
2.  **Identyfikuj problematyczne adresy IP:** Jeśli znajdziesz adres IP, który konsekwentnie powoduje problemy (np. powtarzające się nieudane próby logowania, nadmierne skrobanie stron, komentarze spamowe), zanotuj go.
3.  **Dodaj do listy blokad:** Przejdź do ekranu „Zarządzaj adresami IP”, kliknij „Dodaj nowy adres IP”, wprowadź adres IP, dodaj opisowy komentarz i ustaw go na „Wł.”.
4.  **Przejrzyj statystyki:** Okresowo sprawdzaj kolumnę „Liczba wyświetleń” dla zablokowanych adresów IP. Wysokie liczby wskazują na uporczywe próby, potwierdzając skuteczność Twojej blokady.
5.  **Zarządzaj i udoskonalaj:** Jeśli adres IP nie stanowi już zagrożenia, możesz go dezaktywować (ustaw „Aktywny” na „Wył.”) lub całkowicie usunąć.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Zarządzanie adresami IP | Dodaj nowy adres IP | N/A | Dodaje nowy adres IP do listy blokad. |
| Zarządzanie adresami IP | Adres IP (pole) | N/A | Konkretny adres IP do zablokowania. |
| Zarządzanie adresami IP | Komentarz (pole) | N/A | Twoja wewnętrzna notatka dla zablokowanego adresu IP. |
| Zarządzanie adresami IP | Aktywny (przełącznik) | Wł. | Włącza/wyłącza blokowanie dla konkretnego adresu IP. |
| Zarządzanie adresami IP | Liczba wyświetleń (kolumna) | 0 | Śledzi, ile razy adres IP został zablokowany. |
| Zarządzanie adresami IP | Działania Edytuj / Usuń | N/A | Modyfikuj lub usuwaj istniejące wpisy zablokowanych adresów IP. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Zablokowałem adres IP, ale użytkownik nadal może uzyskać dostęp do mojego sklepu. Co jest nie tak?**
O:
1.  **Sprawdź status „Aktywny”:** Upewnij się, że przełącznik „Aktywny” dla tego konkretnego adresu IP na ekranie „Zarządzaj adresami IP” jest ustawiony na „Wł.”.
2.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” dla starszych wersji). Zapewnia to ponowne załadowanie ustawień modułu.
3.  **Zweryfikuj adres IP:** Dokładnie sprawdź, czy wprowadziłeś prawidłowy adres IP. Czasami dynamiczne adresy IP się zmieniają lub możesz mieć problem z proxy/CDN.
4.  **Pamięć podręczna przeglądarki:** Poproś zablokowanego użytkownika o wyczyszczenie pamięci podręcznej przeglądarki lub spróbowanie dostępu z okna incognito.

**P: Mój legalny klient jest zablokowany! Jak to naprawić?**
O:
1.  **Zidentyfikuj ich adres IP:** Poproś klienta o jego aktualny adres IP (może go znaleźć, wyszukując „jaki jest mój IP” w Google).
2.  **Sprawdź swoją listę blokad:** Przejdź do **Moduły > Block IP address Pro > Zarządzaj adresami IP** i wyszukaj ich adres IP.
3.  **Dezaktywuj lub usuń:** Jeśli znaleziono, ustaw przełącznik „Aktywny” na „Wył.” dla tego wpisu lub całkowicie go usuń.
4.  **Wyczyść pamięć podręczną:** Pamiętaj, aby później wyczyścić pamięć podręczną PrestaShop.

**P: Czy mogę zablokować zakres adresów IP zamiast tylko jednego?**
O: Obecna wersja modułu obsługuje blokowanie pojedynczych adresów IP. Aby zablokować zakresy, musiałbyś wprowadzić każdy adres IP w zakresie indywidualnie lub rozważyć blokowanie adresów IP na poziomie serwera, jeśli masz dostęp do zapory serwera (np. za pomocą reguł `.htaccess`).

**P: Co się stanie, jeśli włączę przekierowanie, ale nie podam adresu URL przekierowania?**
O: Jeśli opcja „Przekieruj zablokowanych użytkowników” jest włączona, ale „Adres URL przekierowania” jest pusty, zachowanie modułu może być niespójne. Najlepszą praktyką jest zawsze podawanie prawidłowego adresu URL, jeśli przekierowanie jest aktywne. Jeśli nie chcesz przekierowywać, wyłącz opcję „Przekieruj zablokowanych użytkowników” i zamiast tego użyj niestandardowej wiadomości.

**P: Czy ten moduł spowolni mój sklep?**
O: Nie, moduł został zaprojektowany tak, aby był bardzo lekki i wydajny. Sprawdza adres IP odwiedzającego bardzo wcześnie w procesie ładowania PrestaShop. Jeśli adres IP jest zablokowany, żądanie jest przerywane lub przekierowywane szybko, często *zanim* Twój sklep zacznie ładować swoją pełną zawartość, co może faktycznie *poprawić* wydajność, zmniejszając niechciane obciążenie serwera.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowe informacje techniczne na temat modułu „Block IP address Pro” dla programistów i webmasterów.

### 4.1 Przegląd architektury
Moduł „Block IP address Pro” wykorzystuje standardową architekturę modułów PrestaShop, głównie klasę `Module` do instalacji/deinstalacji i konfiguracji oraz `AdminController` do zarządzania w panelu administracyjnym. Wykorzystuje niestandardową tabelę bazy danych do przechowywania zablokowanych adresów IP i integruje się z hookiem `actionFrontControllerAfterInit`, aby wykonać sprawdzenie adresu IP jak najwcześniej w cyklu życia żądania.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    Moduł nie posiada dedykowanych kontrolerów front-office. Logika blokowania adresów IP jest obsługiwana bezpośrednio w głównym pliku modułu (`banippro.php`) za pośrednictwem hooka, co zapewnia wczesne wykonanie.

-   **Kontrolery Back-Office Admin**:
    1.  `banippro/controllers/admin/AdminBanIpProController.php`
        *   **Nazwa klasy i klasa nadrzędna:** `AdminBanIpProController` rozszerza `ModuleAdminController`.
        *   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za zarządzanie listą zablokowanych adresów IP w panelu administracyjnym PrestaShop. Zapewnia standardowy interfejs CRUD (Create, Read, Update, Delete) dla encji `BanIpPro`. Obsługuje:
            *   Wyświetlanie listy zablokowanych adresów IP z ich szczegółami (IP, wyświetlenia, komentarz, status aktywności).
            *   Dodawanie nowych adresów IP do listy blokad.
            *   Edytowanie istniejących wpisów adresów IP.
            *   Usuwanie adresów IP z listy blokad.
            *   Zarządzanie przełącznikiem statusu „Aktywny” dla każdego adresu IP.
            *   Metody `initContent()`, `renderList()`, `renderForm()` są zazwyczaj nadpisywane tutaj w celu dostosowania wyświetlania i formularzy.
            *   Mapuje się do tabeli bazy danych `ban` (lub podobnej, zgodnie z definicją modelu `BanIpPro`, jeśli istniał).

    2.  `banippro/controllers/admin/index.php`
        *   **Odpowiedzialność:** Jest to standardowy pusty plik `index.php` często spotykany w podkatalogach modułów PrestaShop. Jego głównym celem jest zapobieganie listowaniu katalogów na serwerach WWW ze względów bezpieczeństwa. Nie zawiera żadnej logiki funkcjonalnej dla modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)
Opis modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Encja `BanIpPro` (dla zablokowanych adresów IP) jest prawdopodobnie zarządzana bezpośrednio w `AdminBanIpProController` i głównym pliku `banippro.php`, potencjalnie przy użyciu prostej interakcji z klasą `Db` lub wewnętrznej struktury tablicowej, jeśli nie jest w pełni zgodna z `ObjectModel`. Gdyby użyto `ObjectModel`, zazwyczaj nazywałaby się `BanIpPro` i znajdowałaby się w `classes/BanIpPro.php`.

Biorąc pod uwagę, że `AdminBanIpProController` zarządza encją „ban”, oznacza to istnienie podstawowej struktury danych. Jeśli nie jest to dedykowany `ObjectModel`, byłyby to bezpośrednie zapytania do bazy danych.

### 4.4 Zasoby JavaScript (`views/js/`)
Opis modułu wskazuje brak niestandardowych plików JavaScript. Wszelkie interaktywne elementy w panelu administracyjnym (takie jak przełączniki lub walidacja formularzy) są prawdopodobnie obsługiwane przez podstawowy JS PrestaShop lub skrypty inline w szablonach.

### 4.5 Arkusze stylów CSS (`views/css/`)
Opis modułu wskazuje brak niestandardowych plików CSS. Stylizacja konfiguracji panelu administracyjnego i ekranów zarządzania adresami IP będzie całkowicie opierać się na domyślnym CSS motywu panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Opis modułu wskazuje brak niestandardowych plików szablonów.
-   **Szablony hooków**: Zachowanie front-office modułu (blokowanie/przekierowywanie) jest obsługiwane programowo w hooku, a nie za pośrednictwem szablonu.
-   **Szablony administracyjne**: Formularz konfiguracji dla `getContent()` oraz widoki listy/formularza dla `AdminBanIpProController` są prawdopodobnie renderowane przy użyciu domyślnych klas pomocniczych PrestaShop (`HelperForm`, `HelperList`), które generują HTML bezpośrednio, lub opierają się na bardzo minimalnych szablonach inline, jeśli w ogóle.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł tworzy co najmniej jedną niestandardową tabelę podczas instalacji do przechowywania zablokowanych adresów IP.
    -   `ps_banippro` (lub podobnie, np. `ps_ban_ip_pro`):
        *   `id_banippro` (Klucz główny, INT)
        *   `ip_address` (VARCHAR, przechowuje adres IP do zablokowania)
        *   `comment` (TEXT, na notatki administratora)
        *   `views` (INT, licznik, ile razy ten adres IP został zablokowany)
        *   `active` (TINYINT(1), 0 lub 1, aby włączyć/wyłączyć blokadę)

    Ustawienia konfiguracji (`mypresta_updates`, `banippro_msg`, `banippro_redirect`, `banippro_url`) są przechowywane w tabeli `ps_configuration`.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionFrontControllerAfterInit` | Wykonany po zainicjowaniu kontrolera front-office, ale przed renderowaniem jakiejkolwiek zawartości. | **KRYTYCZNE:** To tutaj moduł wykonuje swoją podstawową funkcję: sprawdzanie adresu IP odwiedzającego na liście zablokowanych. Jeśli znaleziono dopasowanie, wyświetla niestandardową wiadomość lub wykonuje przekierowanie, skutecznie zatrzymując dalsze wykonywanie strony. |
| `displayHome` | Renderuje zawartość na stronie głównej. | Prawdopodobnie używany do powiadomień o aktualizacjach lub innych treści specyficznych dla modułu, jeśli moduł miał komponent front-office. W kontekście tego modułu może to być przestarzały hook lub używany do bardzo specyficznej, nieblokującej logiki. |
| `home` | Alias dla `displayHome` w niektórych kontekstach. | To samo co `displayHome`. |
| `header` | Renderuje zawartość w sekcji `<head>` kodu HTML. | Używany do dodawania CSS, JavaScript lub meta tagów. W tym module może być używany do powiadomień o aktualizacjach lub do zapewnienia wczesnego ładowania skryptów/stylów, jeśli jest to potrzebne. |
| `actionAdminControllerSetMedia` | Wykonany, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Używany przez moduł do dodawania wszelkich specyficznych plików CSS lub JavaScript wymaganych dla jego stron konfiguracji panelu administracyjnego (np. dla `AdminBanIpProController`). |
| `ActionAdminControllerSetMedia` | (Duplikat powyższego, różnica w wielkości liter) | To samo co `actionAdminControllerSetMedia`. Hooki PrestaShop są zazwyczaj niewrażliwe na wielkość liter, ale moduły czasami rejestrują oba dla kompatybilności. |
| `displayHeader` | Renderuje zawartość w sekcji `<header>` kodu HTML (często w `<body>` przed główną zawartością). | Podobnie jak `header`, ale zazwyczaj dla widocznych elementów. W tym module jest mniej prawdopodobne, aby miał bezpośredni wpływ na front-office, biorąc pod uwagę jego blokujący charakter. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i profesjonalne wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i zapewnienie płynnego działania Twojego modułu.
-   **MyPresta.eu Historia zamówień i pobieranie:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
-   **MyPresta.eu Kontakt z pomocą techniczną:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
