---
title: "Załączniki e-mail - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Załączniki e-mail” od MyPresta.eu."
sidebar:
  label: "Załączniki e-mail - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Email attachments na MyPresta.eu](https://mypresta.eu/modules/administration-tools/email-attachments.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/email-attachments/)
>
> ---


# Załączniki e-mail

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Załączniki e-mail” oferuje prosty proces konfiguracji, głównie poprzez dedykowany ekran administracyjny, na którym zarządzasz załącznikami i łączysz je z konkretnymi szablonami wiadomości e-mail.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po pierwszym kliknięciu „Konfiguruj” po instalacji zostaniesz przeniesiony na główną stronę konfiguracji modułu. Ta strona służy przede wszystkim jako punkt wejścia i może zawierać ogólne informacje lub link do dedykowanego ekranu zarządzania załącznikami.

-   **Co robi ten ekran:** Ten początkowy ekran zawiera krótki przegląd modułu i zazwyczaj kieruje Cię do głównego interfejsu do zarządzania załącznikami e-mail. Może również zawierać ogólne ustawienia, jeśli moduł takie posiadał, ale w przypadku tego modułu podstawowa funkcjonalność jest zarządzana w osobnym kontrolerze administracyjnym.
-   **Wpływ zmiany ustawień:** Wszelkie ustawienia tutaj wpłynęłyby na ogólne zachowanie modułu. Jednak w przypadku „Załączników e-mail” główną akcją jest nawigacja do dedykowanej strony zarządzania „Załącznikami e-mail”.
-   **Zalecana wartość:** Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, które zazwyczaj obejmują kliknięcie przycisku lub linku, aby przejść do obszaru zarządzania załącznikami.

### 2.2 Dedykowany ekran administracyjny: Załączniki e-mail (Panel administracyjny > Moduły > Załączniki e-mail)

To jest główne centrum zarządzania wszystkimi załącznikami e-mail. Zazwyczaj znajdziesz nową pozycję menu pod **Moduły** lub **Parametry sklepu** (w zależności od wersji PrestaShop i projektu modułu) o nazwie „Załączniki e-mail” lub podobnej.

**Lokalizacja menu:** Panel administracyjny > Moduły > Załączniki e-mail (lub podobne, sprawdź swoje menu administracyjne po instalacji)

#### Przegląd ekranu zarządzania „Załącznikami e-mail”

Ten ekran wyświetli listę („siatkę” lub „tabelę”) wszystkich skonfigurowanych załączników e-mail. Z tego miejsca możesz:

-   **Dodaj nowy załącznik:** Utwórz nową regułę załącznika.
-   **Edytuj istniejący załącznik:** Zmodyfikuj ustawienia dla już utworzonego załącznika.
-   **Usuń załącznik:** Usuń regułę załącznika.

#### Dodawanie/Edytowanie załącznika e-mail

Po kliknięciu „Dodaj nowy załącznik” lub „Edytuj” istniejący, zostanie wyświetlony formularz do zdefiniowania właściwości załącznika.

**Pola i opcje formularza:**

1.  **Nazwa załącznika:**

    -   **Co robi to ustawienie:** Jest to wewnętrzna nazwa dla Twojego odniesienia w Panelu administracyjnym. Pomaga łatwo zidentyfikować regułę załącznika.
    -   **Wpływ zmiany tego ustawienia:** Zmienia tylko etykietę, którą widzisz na liście administracyjnej. Nie wpływa na nazwę pliku widoczną dla klienta.
    -   **Zalecana wartość:** Opisowa nazwa, np. „PDF Przewodnik powitalny”, „Potwierdzenie zamówienia Regulamin”, „Instrukcja produktu dla nowych zamówień”.
    -   **Scenariusz sprzedawcy:** Masz wiele załączników do różnych celów; wyraźna nazwa pomaga je rozróżnić.
2.  **Wybierz szablon(y) e-mail:**

    -   **Co robi to ustawienie:** To kluczowe ustawienie określa, do *których* wiadomości e-mail PrestaShop zostanie dodany ten załącznik. Zazwyczaj zobaczysz listę wszystkich standardowych szablonów wiadomości e-mail PrestaShop (np. `account`, `order_conf`, `shipped`, `contact_form`). Możesz wybrać jeden lub wiele szablonów.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po wybraniu:* Załącznik zostanie dołączony do każdej wiadomości e-mail wysłanej przy użyciu wybranych szablonów.
        -   *Po odznaczeniu:* Załącznik nie zostanie dołączony do wiadomości e-mail używających tego szablonu.
    -   **Zalecana wartość:** Wybierz tylko odpowiednie szablony wiadomości e-mail. Na przykład, „Przewodnik powitalny” powinien być dołączony tylko do wiadomości e-mail `account` (utworzenie konta klienta).
    -   **Scenariusz sprzedawcy:** Chcesz dołączyć plik PDF „Polityka zwrotów” do wiadomości e-mail `order_conf` (potwierdzenie zamówienia) i `shipped` (powiadomienie o wysyłce).
3.  **Typ załącznika:**

    -   **Co robi to ustawienie:** Definiuje źródło pliku załącznika. Moduł oferuje różne opcje:
        -   **Prześlij plik:** Dołącz istniejący plik z komputera.
        -   **Generuj PDF ze strony CMS:** Utwórz plik PDF z jednej z istniejących stron CMS PrestaShop.
        -   **Utwórz PDF z edytora tekstu sformatowanego:** Zaprojektuj niestandardową treść PDF bezpośrednio w module za pomocą edytora wizualnego.
    -   **Wpływ zmiany tego ustawienia:** Określa następny zestaw opcji, które zobaczysz do określenia zawartości załącznika.
    -   **Zalecana wartość:** Wybierz typ, który najlepiej pasuje do Twojego źródła treści.
    -   **Scenariusz sprzedawcy:** Masz gotowy plik „Gwarancja.pdf” (Prześlij plik), lub chcesz przekonwertować swoją stronę CMS „O nas” na plik PDF (Generuj PDF ze strony CMS), lub musisz napisać niestandardowy plik PDF „Oferta specjalna” (Utwórz PDF z edytora tekstu sformatowanego).

    **Podustawienia w zależności od typu załącznika:**

    -   **Jeśli wybrano „Prześlij plik”:**

        -   **Pole przesyłania pliku:**
            -   **Co robi to ustawienie:** Umożliwia przeglądanie komputera i przesyłanie pliku (np. PDF, JPG, DOCX).
            -   **Wpływ zmiany tego ustawienia:** Wybrany plik zostanie zapisany na serwerze i użyty jako załącznik.
            -   **Zalecana wartość:** Prześlij plik, który nie jest zbyt duży, aby uniknąć problemów z dostarczaniem wiadomości e-mail. Pliki PDF są zazwyczaj preferowane dla dokumentów.
            -   **Scenariusz sprzedawcy:** Dołączanie pliku PDF „Warunki i zasady” Twojej firmy.
    -   **Jeśli wybrano „Generuj PDF ze strony CMS”:**

        -   **Wybierz stronę CMS:**
            -   **Co robi to ustawienie:** Udostępnia listę rozwijaną wszystkich aktywnych stron CMS PrestaShop.
            -   **Wpływ zmiany tego ustawienia:** Treść wybranej strony CMS zostanie przekonwertowana na plik PDF i dołączona.
            -   **Zalecana wartość:** Wybierz stronę CMS z treścią, która nadaje się do dokumentu PDF (np. „O nas”, „Polityka prywatności”).
            -   **Scenariusz sprzedawcy:** Automatyczne dołączanie strony CMS „Polityka zwrotów” jako pliku PDF do odpowiednich wiadomości e-mail.
    -   **Jeśli wybrano „Utwórz PDF z edytora tekstu sformatowanego”:**

        -   **Edytor tekstu sformatowanego (WYSIWYG):**
            -   **Co robi to ustawienie:** Edytor wizualny, w którym można wpisywać i formatować niestandardową treść, dodawać obrazy, linki itp. Ta treść zostanie następnie przekonwertowana na plik PDF.
            -   **Wpływ zmiany tego ustawienia:** Treść, którą tutaj utworzysz, będzie stanowić treść dołączonego pliku PDF.
            -   **Zalecana wartość:** Użyj tego do treści dynamicznych lub unikalnych, które nie istnieją jako plik lub strona CMS. Zachowaj prosty projekt, aby uzyskać najlepsze wyniki konwersji PDF.
            -   **Scenariusz sprzedawcy:** Tworzenie niestandardowej wiadomości „Dziękujemy” z kodem rabatowym jako załącznik PDF.
4.  **Nazwa pliku załącznika (widoczna dla klienta):**

    -   **Co robi to ustawienie:** Jest to nazwa pliku, którą klient zobaczy w swoim kliencie poczty e-mail, gdy otrzyma załącznik.
    -   **Wpływ zmiany tego ustawienia:** Zmienia sposób wyświetlania pliku w skrzynce odbiorczej klienta.
    -   **Zalecana wartość:** Jasna, opisowa i profesjonalna nazwa pliku (np. `Twoje-Potwierdzenie-Zamowienia.pdf`, `Informacje-Gwarancyjne.pdf`). Dołącz rozszerzenie pliku (np. `.pdf`).
    -   **Scenariusz sprzedawcy:** Przesłałeś `moj_wewnetrzny_dokument_v2.pdf`, ale chcesz, aby klient widział `Przewodnik-Produktu.pdf`.
5.  **Aktywny:**

    -   **Co robi to ustawienie:** Prosty przełącznik WŁ./WYŁ. do włączania lub wyłączania tej konkretnej reguły załącznika.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu:* Reguła załącznika jest aktywna i zostanie zastosowana do wybranych wiadomości e-mail.
        -   *Po wyłączeniu:* Reguła załącznika jest nieaktywna i nie będzie dodawać plików do wiadomości e-mail.
    -   **Zalecana wartość:** Ustaw na „TAK”, gdy chcesz, aby załącznik został wysłany.
    -   **Scenariusz sprzedawcy:** Testujesz załącznik i chcesz go tymczasowo wyłączyć bez usuwania konfiguracji.

#### 2.2.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Załączniki e-mail (Kontroler administracyjny)** | Nazwa załącznika | Tekst opisowy | Wewnętrzna etykieta ułatwiająca identyfikację w BO. |
| | Wybierz szablon(y) e-mail | Konkretne szablony (np. `order_conf`) | Określa, które wiadomości e-mail otrzymają załącznik. |
| | Typ załącznika | Różne (Prześlij plik, Strona CMS, Tekst sformatowany) | Definiuje źródło treści załącznika. |
| | *Jeśli Prześlij plik:* Pole przesyłania pliku | N/A | Przesyła istniejący plik z komputera. |
| | *Jeśli Generuj PDF ze strony CMS:* Wybierz stronę CMS | Konkretna strona CMS | Konwertuje treść wybranej strony CMS na PDF. |
| | *Jeśli Utwórz PDF z edytora tekstu sformatowanego:* Edytor tekstu sformatowanego | Niestandardowa treść | Tworzy PDF z treści wprowadzonej w edytorze. |
| | Nazwa pliku załącznika | Opisowa nazwa pliku (np. `dokument.pdf`) | Nazwa, którą klienci widzą w swoim kliencie poczty e-mail. |
| | Aktywny | TAK | Włącza/wyłącza regułę załącznika. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P1: Moje załączniki nie są wysyłane, lub klienci zgłaszają, że ich nie otrzymują.**

-   **O:** Najpierw sprawdź, czy reguła załącznika jest „Aktywna” w konfiguracji modułu.
-   **O:** Upewnij się, że wybrałeś prawidłowy szablon(y) wiadomości e-mail dla załącznika. Przetestuj, wyzwalając jedną z tych wiadomości e-mail samodzielnie (np. złóż zamówienie testowe, utwórz nowe konto klienta).
-   **O:** Sprawdź ustawienia wiadomości e-mail PrestaShop (Parametry sklepu > E-mail), aby upewnić się, że wiadomości e-mail są ogólnie wysyłane poprawnie. Spróbuj wysłać wiadomość e-mail testową z PrestaShop.
-   **O:** Plik załącznika może być zbyt duży, co powoduje odrzucenie wiadomości e-mail przez dostawców poczty. Spróbuj użyć mniejszego rozmiaru pliku.
-   **O:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P2: Plik PDF wygenerowany ze strony CMS wygląda dziwnie lub ma problemy z formatowaniem.**

-   **O:** Generowanie plików PDF z HTML może być czasami trudne. Upewnij się, że treść Twojej strony CMS to czysty HTML bez złożonego JavaScriptu lub bardzo dynamicznych elementów.
-   **O:** Spróbuj uprościć układ swojej strony CMS. Unikaj zbyt złożonego CSS lub bardzo szerokich obrazów, które mogą nie pasować dobrze do standardowej strony PDF.
-   **O:** Jeśli problemy nadal występują, rozważ utworzenie dedykowanego pliku PDF zewnętrznie i użycie zamiast tego opcji „Prześlij plik”.

**P3: Czy mogę dołączać różne pliki w zależności od zamówionego produktu lub grupy klientów?**

-   **O:** Ten moduł, w swojej standardowej konfiguracji, dołącza pliki do *wszystkich* wiadomości e-mail wybranego typu, niezależnie od konkretnego produktu lub grupy klientów. W przypadku bardziej zaawansowanych, warunkowych załączników, może być wymagane niestandardowe opracowanie lub bardziej wyspecjalizowany moduł.

**P4: Jak przetłumaczyć treść pliku PDF utworzonego za pomocą edytora tekstu sformatowanego na różne języki?**

-   **O:** Podczas korzystania z edytora tekstu sformatowanego powinieneś zobaczyć zakładki językowe (np. angielski, francuski, hiszpański), jeśli Twój sklep PrestaShop obsługuje wiele języków. Będziesz musiał wprowadzić i sformatować treść dla każdego języka oddzielnie w edytorze. Moduł następnie dołączy poprawną wersję językową na podstawie wybranego języka klienta.

**P5: Gdzie są przechowywane przesłane pliki na moim serwerze?**

-   **O:** Przesłane pliki są zazwyczaj przechowywane w katalogu modułu lub w wyznaczonym folderze przesyłania w module. Zazwyczaj nie musisz bezpośrednio wchodzić w interakcje z tymi plikami za pośrednictwem FTP, ponieważ moduł nimi zarządza.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Załączniki e-mail”.

### 4.1 Przegląd architektury

Moduł „Załączniki e-mail” (`mattach`) rozszerza podstawową funkcjonalność poczty e-mail PrestaShop poprzez nadpisanie klasy `Mail`. Pozwala to na wstrzykiwanie niestandardowych załączników do wychodzących wiadomości e-mail bez bezpośredniej modyfikacji plików rdzenia. Moduł ten stosuje standardowy wzorzec MVC PrestaShop dla swojego interfejsu zarządzania w Panelu administracyjnym, wykorzystując `AdminController` do zarządzania encjami `mailfile`, które reprezentują konfiguracje załączników. Generowanie plików PDF jest obsługiwane wewnętrznie, poprzez konwersję treści CMS lub danych z edytora tekstu sformatowanego.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front Office**:

    -   Ten moduł **nie** zawiera żadnych dedykowanych kontrolerów front office. Wszystkie jego operacje są wykonywane w Panelu administracyjnym lub poprzez nadpisywanie klas rdzenia podczas wysyłania wiadomości e-mail.
-   **Kontrolery administracyjne Back Office**:

    -   `mattach/controllers/admin/AdminMailAttachments.php`

        -   **Nazwa klasy**: `AdminMailAttachmentsController`
        -   **Klasa nadrzędna**: `ModuleAdminController`
        -   **Odpowiedzialność**: Jest to główny kontroler do zarządzania regułami załączników e-mail. Obsługuje operacje CRUD (Create, Read, Update, Delete) dla encji `mailfile`. Wyświetla listę skonfigurowanych załączników, udostępnia formularze do ich dodawania/edycji oraz zarządza przesyłaniem plików, wyborem stron CMS i treścią edytora tekstu sformatowanego do generowania plików PDF. Wykorzystuje `HelperList` PrestaShop do widoku siatki i `HelperForm` do formularzy dodawania/edycji.
        -   **Zarządzana tabela / encja**: `mailfile` (niestandardowa tabela dla danych modułu).
        -   **Powiązane klucze konfiguracyjne**: `PS_LANG_DEFAULT` (używane dla pól wielojęzycznych).
    -   `mattach/controllers/admin/index.php`

        -   **Nazwa klasy**: (Brak jawnej klasy, zazwyczaj symbol zastępczy lub przekierowanie)
        -   **Odpowiedzialność**: Ten plik jest często środkiem bezpieczeństwa (aby zapobiec bezpośredniemu listowaniu katalogów) lub prostym przekierowaniem w strukturze administracyjnej PrestaShop. Nie zawiera aktywnej logiki kontrolera dla funkcjonalności modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)

-   `mattach/override/classes/index.php`

    -   **Odpowiedzialność**: Standardowy plik bezpieczeństwa PrestaShop zapobiegający listowaniu katalogów.
-   `mattach/override/classes/Mail.php`

    -   **Nazwa klasy**: `Mail` (nadpisuje podstawową klasę `Mail` PrestaShop)
    -   **Klasa nadrzędna**: `MailCore`
    -   **Odpowiedzialność**: Jest to najbardziej krytyczna część funkcjonalności modułu. Nadpisując klasę `Mail`, moduł przechwytuje metodę `send()`. W nadpisanej metodzie `send()` sprawdza, czy dla wysyłanego szablonu wiadomości e-mail skonfigurowano jakieś reguły załączników. Jeśli znaleziono dopasowania, pobiera dane załącznika (ścieżka przesłanego pliku, wygenerowana treść PDF), tworzy niezbędne obiekty `Swift_Attachment` i dodaje je do wiadomości e-mail przed jej wysłaniem. Zapewnia to bezproblemowe dołączanie załączników do wszystkich odpowiednich wychodzących wiadomości e-mail.
    -   **Interakcja z bazą danych**: Współdziała z niestandardową tabelą `mailfile` modułu w celu pobrania konfiguracji załączników.
    -   **Kluczowe metody publiczne**: Nadpisuje `send()` w celu wstrzyknięcia logiki załączników.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `mattach/views/templates/admin/js/mattach.js`
    -   **Zakres**: Panel administracyjny (`AdminMailAttachmentsController`).
    -   **Funkcjonalność**: Ten skrypt prawdopodobnie obsługuje dynamiczne zachowanie formularza konfiguracji załączników. Może to obejmować:
        -   Pokazywanie/ukrywanie konkretnych pól wejściowych w zależności od wybranego „Typu załącznika” (np. pokazywanie pola przesyłania pliku tylko po wybraniu „Prześlij plik”).
        -   Wywołania AJAX do pobierania list stron CMS lub innych dynamicznych danych.
        -   Inicjalizacja edytora tekstu sformatowanego (np. TinyMCE lub CKEditor) dla opcji „Utwórz PDF z edytora tekstu sformatowanego”.
        -   Walidacja po stronie klienta lub ulepszenia interfejsu użytkownika dla interfejsu zarządzania załącznikami.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Ten moduł **nie** wydaje się zawierać żadnych niestandardowych plików CSS w dostarczonym inwentarzu. Prawdopodobnie opiera się na domyślnych stylach Panelu administracyjnego PrestaShop dla swoich formularzy konfiguracji i list.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   Ten moduł **nie** zawiera żadnych konkretnych szablonów hooków w dostarczonym inwentarzu. Jego wpływ na front office odbywa się wyłącznie poprzez załączniki e-mail, a nie elementy wizualne.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `mattach/views/templates/admin/orderstates.tpl`
        -   **Cel**: Nazwa tego szablonu sugeruje, że może być używany do wyświetlania lub zarządzania statusami zamówień w odniesieniu do załączników, lub być może do wyboru statusów zamówień dla warunkowych załączników (chociaż opis modułu nie wspomina wyraźnie o tej zaawansowanej funkcji). Może być częścią formularza `AdminMailAttachmentsController`, potencjalnie do wyboru, które zmiany statusu zamówienia wyzwalają wiadomość e-mail z załącznikiem.
    -   `mattach/lib/searchTool/views/scripts.tpl`
        -   **Cel**: Ten szablon prawdopodobnie zawiera logikę JavaScript lub Smarty związaną z narzędziem wyszukiwania lub filtrowania używanym w interfejsie administracyjnym, być może do wyszukiwania szablonów wiadomości e-mail lub stron CMS. Jest to szablon narzędziowy do ulepszania interfejsu użytkownika administracyjnego.
-   **Szablony Front Office (`views/templates/front/`)**:

    -   Ten moduł **nie** zawiera żadnych szablonów front office.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_mailfile`: Jest to główna niestandardowa tabela utworzona przez moduł do przechowywania każdej konfiguracji załącznika e-mail.
        -   `id_mailfile`: Klucz główny.
        -   `name`: Wewnętrzna nazwa reguły załącznika.
        -   `file_name`: Rzeczywista nazwa pliku (lub wygenerowana nazwa) załącznika.
        -   `file_path`: Ścieżka do przesłanego pliku lub miejsca tymczasowego przechowywania wygenerowanego pliku PDF.
        -   `file_type`: Typ załącznika (np. „upload”, „cms”, „editor”).
        -   `id_cms`: Jeśli `file_type` to „cms”, przechowuje ID strony CMS.
        -   `content`: Jeśli `file_type` to „editor”, przechowuje treść tekstu sformatowanego (wielojęzyczną).
        -   `mail_templates`: Serializowana tablica lub ciąg znaków oddzielonych przecinkami nazw szablonów wiadomości e-mail (np. `account`, `order_conf`), do których ten załącznik ma zastosowanie.
        -   `active`: Wartość logiczna (0 lub 1) wskazująca, czy reguła załącznika jest aktywna.
    -   `ps_mailfile_lang`: Tabela towarzysząca dla pól wielojęzycznych, takich jak `content` (jeśli `file_type` to „editor”).
        -   `id_mailfile`: Klucz obcy do `ps_mailfile`.
        -   `id_lang`: ID języka.
        -   `content`: Przetłumaczona treść tekstu sformatowanego.
-   **Tabela zarejestrowanych hooków**:

    -   Moduł działa głównie poprzez nadpisywanie podstawowej klasy `Mail`, co jest bardziej bezpośrednią i potężną metodą niż poleganie wyłącznie na hookach do modyfikacji wiadomości e-mail. Chociaż może rejestrować niektóre standardowe hooki do instalacji/deinstalacji modułu lub integracji menu Panelu administracyjnego, jego podstawowa logika wstrzykiwania załączników znajduje się w nadpisaniu `Mail`.
    -   Metoda `install()`:
        -   Rejestruje moduł w menu Panelu administracyjnego.
        -   Tworzy tabele bazy danych `ps_mailfile` i `ps_mailfile_lang`.
        -   Instaluje nadpisanie klasy `Mail`.
    -   Metoda `uninstall()`:
        -   Usuwa moduł z menu Panelu administracyjnego.
        -   Usuwa tabele bazy danych `ps_mailfile` i `ps_mailfile_lang`.
        -   Odinstalowuje nadpisanie klasy `Mail`.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Załączniki e-mail”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
