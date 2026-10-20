---
title: "Kopia zapasowa bazy danych lokalnie i w chmurze - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Kopia zapasowa bazy danych lokalnie i w chmurze” od MyPresta.eu."
sidebar:
  label: "Kopia zapasowa bazy danych lokalnie i w chmurze - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Database backup locally and in cloud na MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-backup-locally-and-in-cloud.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/database-backup-locally-and-in-cloud/)
>
> ---


# Kopia zapasowa bazy danych lokalnie i w chmurze

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Wystarczające zasoby serwera (CPU, pamięć) do eksportu bazy danych, zwłaszcza dla bardzo dużych baz danych, chociaż moduł został zaprojektowany w celu łagodzenia tych problemów za pomocą fragmentowania. Prawa do zapisu dla katalogu kopii zapasowych na Twoim serwerze.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Kopia zapasowa bazy danych lokalnie i w chmurze” zapewnia kompleksowy interfejs do zarządzania kopiami zapasowymi. Będziesz głównie korzystać z dwóch głównych obszarów: głównej strony konfiguracji modułu i dedykowanego ekranu administracyjnego „Moje kopie zapasowe”.

### 2.1 Główna strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj „Kopia zapasowa bazy danych lokalnie i w chmurze”)

Ta początkowa strona konfiguracji (`mybackups/index.php` poprzez `getContent()`) obsługuje podstawową konfigurację i integrację modułu.

#### Ustawienia ogólne

- **Co robi to ustawienie:** Te ustawienia kontrolują podstawowe aspekty działania modułu i jego integracji ze środowiskiem PrestaShop.
- **Wpływ zmiany tego ustawienia:** Dostosowanie tych ustawień może wpłynąć na wydajność, bezpieczeństwo i ogólną niezawodność Twoich kopii zapasowych.
- **Zalecana wartość:** Zazwyczaj trzymaj się wartości domyślnych, chyba że masz konkretny powód lub zalecenie wsparcia technicznego.

#### Integracje z przechowywaniem w chmurze

- **Co robi to ustawienie:** Ta sekcja umożliwia połączenie Twojego sklepu PrestaShop z różnymi dostawcami usług przechowywania w chmurze, gdzie będą przechowywane Twoje kopie zapasowe. Każdy dostawca (Google Drive, Dropbox, FTP/FTPS, Amazon S3) będzie miał swój własny zestaw danych połączeniowych.
- **Wpływ zmiany tego ustawienia:** Pomyślne połączenie z usługą chmurową umożliwia jej jako miejsce docelowe kopii zapasowych. Nieprawidłowe dane uwierzytelniające uniemożliwią przesyłanie kopii zapasowych do tej konkretnej chmury.
- **Zalecana wartość:** Połącz się z co najmniej jednym dostawcą usług przechowywania w chmurze w celu tworzenia kopii zapasowych poza siedzibą. Google Drive i Dropbox są często najłatwiejsze do skonfigurowania dla większości sprzedawców.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz przechowywać swoje kopie zapasowe na Google Drive. Kliknij przycisk „Połącz z Google Drive”, wykonaj kroki uwierzytelniania i udziel modułowi pozwolenia na dostęp do określonego folderu na Twoim Google Drive. Zapewnia to, że nawet jeśli Twój serwer ulegnie awarii, Twoje kopie zapasowe są bezpieczne w chmurze.

### 2.2 Dedykowany ekran administracyjny: Moje kopie zapasowe (Panel administracyjny > Moje kopie zapasowe)

To centralne centrum zarządzania wszystkimi kopiami zapasowymi bazy danych. Ten ekran znajdziesz pod nową pozycją menu, zazwyczaj nazwaną „Moje kopie zapasowe” lub podobnie, dodaną do nawigacji Panelu administracyjnego PrestaShop. Ten ekran jest obsługiwany przez `mybackups/controllers/admin/AdminMyBackupsController.php`.

#### Pulpit nawigacyjny i lista kopii zapasowych

- **Nazwa ekranu i lokalizacja w menu:** „Moje kopie zapasowe” znajdziesz w głównym menu PrestaShop, zazwyczaj pogrupowane z „Administracja” lub „Zaawansowane”.
- **Dostępne działania i ustawienia:**
  - **Lista kopii zapasowych:** Ta tabela wyświetla wszystkie istniejące kopie zapasowe bazy danych, niezależnie od tego, czy są przechowywane lokalnie, czy w chmurze. Każdy wpis zazwyczaj pokazuje:
    - **Data/Godzina:** Kiedy kopia zapasowa została utworzona.
    - **Rozmiar:** Rozmiar skompresowanego pliku kopii zapasowej.
    - **Lokalizacja:** Gdzie kopia zapasowa jest przechowywana (Lokalnie, Google Drive, Dropbox, FTP, S3).
    - **Działania:**
      - **Pobierz:** Pobierz plik kopii zapasowej na swój komputer.
      - **Przywróć:** Rozpocznij proces przywracania bazy danych za pomocą tej kopii zapasowej. (Zachowaj szczególną ostrożność przy tej czynności, ponieważ nadpisze ona Twoją bieżącą bazę danych!)
      - **Usuń:** Usuń plik kopii zapasowej z miejsca jego przechowywania.
  - **Przycisk Utwórz nową kopię zapasową:** Widoczny przycisk do ręcznego inicjowania nowej kopii zapasowej bazy danych.
  - **Status przechowywania w chmurze:** Wizualne wskaźniki pokazujące, które usługi chmurowe są aktualnie połączone i dostępne.
  - **Zaplanowane kopie zapasowe:** Sekcja do przeglądania i zarządzania zautomatyzowanymi zadaniami tworzenia kopii zapasowych (zadania cron).
- **Wpływ zmian:**
  - **Tworzenie nowej kopii zapasowej:** Generuje nowy skompresowany zrzut SQL Twojej bazy danych i przechowuje go w skonfigurowanych lokalizacjach (lokalnie i/lub w chmurze).
  - **Przywracanie kopii zapasowej:** Zastępuje Twoją bieżącą aktywną bazę danych danymi z wybranego pliku kopii zapasowej. Jest to potężne i potencjalnie destrukcyjne działanie; zawsze upewnij się, że masz świeżą kopię zapasową przed próbą przywrócenia.
  - **Usuwanie kopii zapasowej:** Trwale usuwa plik kopii zapasowej z miejsca jego przechowywania.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1.  **Początkowa konfiguracja:** Połącz się z preferowanymi dostawcami usług przechowywania w chmurze na stronie konfiguracji modułu.
  2.  **Zaplanuj kopie zapasowe:** Skonfiguruj zadanie cron (patrz „Praktyczne przypadki użycia” poniżej), aby automatycznie tworzyć kopie zapasowe codziennie lub co tydzień, w zależności od aktywności Twojego sklepu. Upewnij się, że te zaplanowane kopie zapasowe są wysyłane do co najmniej jednej lokalizacji w chmurze.
  3.  **Regularne monitorowanie:** Okresowo sprawdzaj pulpit nawigacyjny „Moje kopie zapasowe”, aby upewnić się, że kopie zapasowe są tworzone pomyślnie i że Twoje połączenia z chmurą są aktywne.
  4.  **Ręczna kopia zapasowa (opcjonalnie):** Utwórz ręczną kopię zapasową przed wprowadzeniem jakichkolwiek większych zmian w sklepie (np. instalacja modułów, aktualizacje motywów, import produktów).
  5.  **Testowe przywracanie (KRYTYCZNE):** Od czasu do czasu wykonaj testowe przywracanie w *środowisku deweloperskim lub testowym* (NIGDY w swoim sklepie produkcyjnym bez ekstremalnej ostrożności), aby upewnić się, że Twoje kopie zapasowe są prawidłowe, a proces przywracania działa zgodnie z oczekiwaniami.

#### Formularz tworzenia kopii zapasowej

Po kliknięciu „Utwórz nową kopię zapasową” zazwyczaj zostaną wyświetlone opcje:

- **Nazwa kopii zapasowej:**
  - **Co robi to ustawienie:** Pozwala nadać niestandardową nazwę plikowi kopii zapasowej dla łatwej identyfikacji.
  - **Wpływ zmiany tego ustawienia:** Plik kopii zapasowej zostanie zapisany pod tą nazwą (np. `moja-kopia-zapasowa-sklepu-2023-10-27.sql.zip`).
  - **Zalecana wartość:** Użyj opisowej nazwy, być może zawierającej datę lub krótką notatkę o przyczynie utworzenia kopii zapasowej (np. „Kopia zapasowa przed aktualizacją”).
- **Lokalizacje przechowywania:**
  - **Co robi to ustawienie:** Wybierz, gdzie plik kopii zapasowej ma zostać zapisany. Opcje zazwyczaj obejmują „Serwer lokalny” i wszelkie połączone usługi chmurowe (Google Drive, Dropbox, FTP, S3).
  - **Wpływ zmiany tego ustawienia:** Kopia zapasowa zostanie zapisana tylko w wybranych lokalizacjach.
  - **Zalecana wartość:** Zawsze wybieraj „Serwer lokalny” i co najmniej jedną opcję przechowywania w chmurze dla redundancji.
- **Wyklucz tabele:**
  - **Co robi to ustawienie:** Pozwala wybrać konkretne tabele bazy danych, które *nie* powinny być uwzględnione w kopii zapasowej. Może to być przydatne dla bardzo dużych tabel zawierających dane niekrytyczne lub łatwe do ponownego wygenerowania (np. tabele pamięci podręcznej, tabele logów).
  - **Wpływ zmiany tego ustawienia:** Wybrane tabele zostaną pominięte, co spowoduje mniejszy plik kopii zapasowej.
  - **Zalecana wartość:** Dla większości sprzedawców pozostaw to puste, aby utworzyć kopię zapasową całej bazy danych. Wykluczaj tabele tylko wtedy, gdy rozumiesz konsekwencje i próbujesz zmniejszyć rozmiar kopii zapasowej z powodu poważnych ograniczeń hostingu.
- **Przycisk Rozpocznij tworzenie kopii zapasowej:** Inicjuje proces tworzenia kopii zapasowej. Zazwyczaj zobaczysz pasek postępu lub aktualizacje statusu podczas tworzenia i przesyłania kopii zapasowej.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Ustawienia ogólne | Domyślne | Kontroluje podstawowe operacje modułu, wydajność i bezpieczeństwo. |
| | Integracja z Google Drive | Połącz | Włącza Google Drive jako miejsce docelowe kopii zapasowych. |
| | Integracja z Dropbox | Połącz | Włącza Dropbox jako miejsce docelowe kopii zapasowych. |
| | Integracja z FTP/FTPS | Konfiguruj | Włącza FTP/FTPS jako miejsce docelowe kopii zapasowych. |
| | Integracja z Amazon S3 | Konfiguruj | Włącza Amazon S3 jako miejsce docelowe kopii zapasowych. |
| **Pulpit nawigacyjny Moje kopie zapasowe** | Utwórz nową kopię zapasową | N/A | Ręcznie inicjuje nową kopię zapasową bazy danych. |
| | Lista kopii zapasowych (Pobierz) | N/A | Pobiera plik kopii zapasowej na komputer lokalny. |
| | Lista kopii zapasowych (Przywróć) | N/A | **KRYTYCZNE:** Nadpisuje bieżącą bazę danych wybraną kopią zapasową. Używaj z najwyższą ostrożnością, najlepiej na środowisku testowym. |
| | Lista kopii zapasowych (Usuń) | N/A | Trwale usuwa plik kopii zapasowej z miejsca jego przechowywania. |
| **Formularz tworzenia kopii zapasowej** | Nazwa kopii zapasowej | Automatycznie generowana | Niestandardowa nazwa pliku kopii zapasowej. |
| | Lokalizacje przechowywania | Lokalnie + Chmura | Wybiera, gdzie kopia zapasowa zostanie zapisana (serwer lokalny, usługi chmurowe). |
| | Wyklucz tabele | Brak | Pomija określone tabele z kopii zapasowej w celu zmniejszenia rozmiaru pliku. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kopie zapasowe kończą się niepowodzeniem lub trwają zbyt długo. Co powinienem zrobić?**
O:

-   **Sprawdź zasoby serwera:** Duże bazy danych wymagają znacznej pamięci serwera i czasu wykonania. Chociaż moduł fragmentuje eksporty, bardzo ograniczone środowiska hostingowe nadal mogą mieć problemy. Skontaktuj się z hostem, aby sprawdzić limity pamięci PHP (`memory_limit`) i maksymalny czas wykonania (`max_execution_time`).
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może zakłócać działanie. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
-   **Wyklucz tabele:** Rozważ wykluczenie niekrytycznych tabel (takich jak tabele pamięci podręcznej lub statystyk) z kopii zapasowej, jeśli są bardzo duże. Może to znacznie zmniejszyć rozmiar i czas tworzenia kopii zapasowej.
-   **Sprawdź dzienniki błędów:** Poszukaj w dziennikach błędów PrestaShop (zazwyczaj `var/logs/` lub `app/logs/` w zależności od wersji PS) lub w dziennikach błędów PHP serwera konkretnych komunikatów o błędach.

**P: Połączyłem się z Google Drive/Dropbox, ale nie widzę tam moich kopii zapasowych.**
O:

-   **Sprawdź status połączenia:** Przejdź do strony konfiguracji modułu i sprawdź, czy Twoja usługa chmurowa wyświetla się jako „Połączona”. Jeśli nie, spróbuj ponownie się połączyć.
-   **Uprawnienia do folderu:** Upewnij się, że moduł ma niezbędne uprawnienia do zapisu w określonym folderze w Twojej pamięci masowej w chmurze. W przypadku Google Drive/Dropbox moduł zazwyczaj tworzy własny folder.
-   **Test ręcznego przesyłania:** Spróbuj utworzyć małą ręczną kopię zapasową i wyraźnie wybierz usługę chmurową jako miejsce docelowe, aby sprawdzić, czy przesyłanie zakończy się pomyślnie.
-   **Sprawdź pamięć masową w chmurze bezpośrednio:** Zaloguj się do swojego konta Google Drive lub Dropbox za pośrednictwem ich strony internetowej i ręcznie przeglądaj foldery, aby sprawdzić, czy kopie zapasowe tam są, być może w nieoczekiwanej lokalizacji.

**P: Jak przywrócić moją bazę danych z kopii zapasowej?**
O:

-   **OSTRZEŻENIE:** Przywrócenie bazy danych nadpisze Twoją bieżącą aktywną bazę danych. Jest to działanie wysoce destrukcyjne. **Zawsze miej świeżą kopię zapasową swojej bieżącej bazy danych przed próbą przywrócenia.**
-   Przejdź do **Panel administracyjny > Moje kopie zapasowe**.
-   Znajdź na liście plik kopii zapasowej, który chcesz przywrócić.
-   Kliknij przycisk „Przywróć” obok tej kopii zapasowej.
-   Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie. Moduł poprowadzi Cię przez ten proces.
-   Jeśli Twój sklep jest całkowicie niedostępny, być może będziesz musiał ręcznie przesłać plik kopii zapasowej za pośrednictwem FTP, a następnie użyć interfejsu modułu lub narzędzia takiego jak phpMyAdmin, aby go zaimportować. W takich krytycznych sytuacjach najlepiej skonsultować się z deweloperem lub dostawcą hostingu.

**P: Co się stanie, jeśli na moim serwerze zabraknie miejsca na dysku podczas tworzenia lokalnej kopii zapasowej?**
O: Proces tworzenia kopii zapasowej prawdopodobnie zakończy się niepowodzeniem, a zobaczysz komunikat o błędzie związany z miejscem na dysku. Upewnij się, że masz wystarczającą ilość wolnego miejsca na dysku na swoim serwerze, zwłaszcza jeśli przechowujesz wiele lokalnych kopii zapasowych lub masz bardzo dużą bazę danych. Regularnie usuwaj stare lokalne kopie zapasowe, które zostały już bezpiecznie przesłane do chmury.

**P: Mój niestandardowy motyw nie wyświetla się poprawnie po przywróceniu.**
O: Kopie zapasowe bazy danych przede wszystkim przywracają Twoje dane. Pliki motywów, pliki modułów i obrazy są zazwyczaj przechowywane w systemie plików serwera, a nie bezpośrednio w bazie danych.

-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść wszystkie pamięci podręczne (Smarty, system plików itp.).
-   **Sprawdź system plików:** Upewnij się, że wszystkie pliki motywu, pliki modułów i foldery obrazów są obecne i mają prawidłowe uprawnienia na serwerze. Przywracanie bazy danych nie wpłynie na te pliki. Jeśli przywróciłeś z bardzo starej kopii zapasowej, niektóre konfiguracje modułów mogą wymagać ponownego zapisania w Panelu administracyjnym.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd architektury technicznej i bazy kodu modułu „Kopia zapasowa bazy danych lokalnie i w chmurze” dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł MyBackups został zaprojektowany z silnym naciskiem na niezawodność, skalowalność i odporność na błędy, szczególnie w zakresie obsługi dużych operacji na bazach danych i integracji z zewnętrznymi usługami chmurowymi. Przyjmuje modułowe, obiektowe podejście, wykorzystując wzorzec MVC PrestaShop tam, gdzie jest to stosowne, ale także implementując własną wewnętrzną architekturę zorientowaną na usługi dla podstawowej logiki tworzenia/przywracania kopii zapasowych.

Kluczowe wzorce architektoniczne obejmują:

-   **Przetwarzanie fragmentowane:** Eksport i import bazy danych są dzielone na mniejsze, łatwe do zarządzania fragmenty, aby obejść limity czasu wykonania i pamięci PHP.
-   **Zarządzanie stanem:** Solidny system zarządzania stanem (`MyBackupsStateManager`) śledzi postęp długotrwałych zadań tworzenia/przywracania kopii zapasowych, umożliwiając wykonywanie zadań web-cron i odzyskiwanie po przerwach.
-   **Abstrakcja przechowywania:** Projekt oparty na interfejsach (`MyBackupsStorageInterface`) umożliwia łatwą integrację nowych dostawców usług przechowywania w chmurze bez zmiany podstawowej logiki tworzenia kopii zapasowych.
-   **Integracja OAuth:** Bezpieczne przepływy OAuth 2.0 dla Google Drive i Dropbox, obsługujące przechowywanie i odświeżanie tokenów.
-   **Cron/Job Runner:** Dedykowane kontrolery front-end i klasy do wyzwalania i zarządzania zadaniami w tle za pośrednictwem crona lub web-cron.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są używane głównie do zadań w tle i wywołań zwrotnych OAuth, a nie do renderowania treści widocznych dla klienta.

-   `mybackups/controllers/front/cron.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyBackupsCronModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler służy jako punkt wejścia dla zaplanowanych zadań cron. Po uzyskaniu dostępu z prawidłowym tokenem, wyzwala `MyBackupsCronRunner` do przetwarzania oczekujących zadań tworzenia kopii zapasowych. Jest zaprojektowany do wywoływania zewnętrznie przez demona cron serwera lub usługę web-cron.
-   `mybackups/controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyBackupsIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Zastępczy lub domyślny kontroler front-end, często używany do routingu modułów lub prostych przekierowań, jeśli nie jest wymagana żadna konkretna akcja. W tym module może służyć jako podstawa lub rezerwowy.
-   `mybackups/controllers/front/job.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyBackupsJobModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Obsługuje żądania AJAX związane z postępem i statusem trwających zadań tworzenia/przywracania kopii zapasowych. Współpracuje z `MyBackupsJobRunner` i `MyBackupsStateManager`, aby dostarczać aktualizacje w czasie rzeczywistym do interfejsu Panelu administracyjnego.
-   `mybackups/controllers/front/oauthdropbox.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyBackupsOauthdropboxModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to adres URI wywołania zwrotnego dla przepływu OAuth 2.0 Dropbox. Po autoryzacji modułu przez sprzedawcę w Dropbox, Dropbox przekierowuje do tego kontrolera, który następnie obsługuje wymianę kodu autoryzacji na token dostępu i bezpiecznie go przechowuje.
-   `mybackups/controllers/front/oauthgdrive.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyBackupsOauthgdriveModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Podobnie jak `oauthdropbox.php`, jest to adres URI wywołania zwrotnego dla przepływu OAuth 2.0 Google Drive. Przetwarza kod autoryzacji z Google i uzyskuje/przechowuje niezbędne tokeny dostępu i odświeżania.

#### Kontrolery administracyjne Back-Office

Te kontrolery zarządzają interfejsem modułu w Panelu administracyjnym PrestaShop.

-   `mybackups/controllers/admin/AdminMyBackupsController.php`
    -   **Nazwa karty i zarządzana encja:** Jest to główny kontroler administracyjny dla pulpitu nawigacyjnego „Moje kopie zapasowe”. Zarządza listowaniem, tworzeniem, pobieraniem, przywracaniem i usuwaniem plików kopii zapasowych. Koordynuje interakcje z `MyBackupsCatalog`, `MyBackupsExporter`, `MyBackupsImporter` i różnymi klasami przechowywania.
-   `mybackups/controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** Standardowy plik `index.php` PrestaShop dla katalogów kontrolerów administracyjnych.
    -   **Odpowiedzialność:** Zapobiega bezpośredniemu listowaniu katalogów i zapewnia bezpieczny dostęp do kontrolerów administracyjnych.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

-   `mybackups/classes/index.php`: Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.
-   `mybackups/classes/MyBackupsAdminAjax.php`: Obsługuje różne żądania AJAX z interfejsu administracyjnego, takie jak pobieranie list kopii zapasowych, inicjowanie konkretnych działań lub aktualizowanie elementów interfejsu użytkownika.
-   `mybackups/classes/MyBackupsAdminForms.php`: Prawdopodobnie odpowiedzialny za renderowanie i przetwarzanie formularzy konfiguracyjnych modułu w Panelu administracyjnym, w tym ustawień integracji z chmurą.
-   `mybackups/classes/MyBackupsCatalog.php`: Zarządza katalogiem plików kopii zapasowych, zarówno lokalnych, jak i w chmurze. Udostępnia metody do listowania, filtrowania i pobierania informacji o istniejących kopiach zapasowych.
-   `mybackups/classes/MyBackupsCloudUi.php`: Pomaga w generowaniu elementów interfejsu użytkownika i logiki dla integracji przechowywania w chmurze w Panelu administracyjnym (np. przyciski połączenia, wskaźniki statusu).
-   `mybackups/classes/MyBackupsCronRunner.php`: Podstawowa logika do wykonywania zaplanowanych zadań tworzenia kopii zapasowych. Sprawdza oczekujące zadania i inicjuje `MyBackupsJobRunner` dla każdego z nich.
-   `mybackups/classes/MyBackupsDumpVerifier.php`: Odpowiedzialny za weryfikację integralności i poprawności plików zrzutów SQL, potencjalnie sprawdzając typowe błędy lub niekompletne zrzuty.
-   `mybackups/classes/MyBackupsExporter.php`: Obsługuje rzeczywisty proces eksportu bazy danych, w tym fragmentowanie zrzutu SQL, filtrowanie tabel i kompresję.
-   `mybackups/classes/MyBackupsImporter.php`: Zarządza procesem importu (przywracania) bazy danych, analizując zrzut SQL i wykonując zapytania w fragmentach.
-   `mybackups/classes/MyBackupsJobLock.php`: Implementuje mechanizm blokowania, aby zapobiec jednoczesnemu uruchamianiu wielu zadań tworzenia/przywracania kopii zapasowych, zapewniając spójność danych i zapobiegając rywalizacji o zasoby.
-   `mybackups/classes/MyBackupsJobRunner.php`: Koordynuje całe zadanie tworzenia lub przywracania kopii zapasowej, zarządzając sekwencją kroków (eksport, kompresja, przesyłanie/pobieranie, import) i współpracując z `MyBackupsStateManager`.
-   `mybackups/classes/MyBackupsMemoryGuard.php`: Klasa narzędziowa do monitorowania i zarządzania zużyciem pamięci PHP podczas intensywnych operacji, pomagająca zapobiegać błędom braku pamięci.
-   `mybackups/classes/MyBackupsOAuthReturn.php`: Obsługuje końcowe kroki procesu wywołania zwrotnego OAuth, przetwarzając zwrócony kod autoryzacji i zarządzając przechowywaniem tokenów.
-   `mybackups/classes/MyBackupsOAuthState.php`: Zarządza parametrem stanu podczas przepływów OAuth, aby zapobiec atakom CSRF.
-   `mybackups/classes/MyBackupsPaths.php`: Zapewnia scentralizowane zarządzanie ścieżkami plików i katalogami używanymi przez moduł (np. katalog przechowywania kopii zapasowych).
-   `mybackups/classes/MyBackupsStateManager.php`: Kluczowy dla długotrwałych zadań. Przechowuje i pobiera bieżący stan operacji tworzenia/przywracania kopii zapasowej, umożliwiając wstrzymywanie i wznawianie zadań w wielu żądaniach HTTP (np. podczas wykonywania crona lub aktualizacji postępu w sieci).
-   `mybackups/classes/MyBackupsTableFilter.php`: Implementuje logikę filtrowania tabel bazy danych podczas eksportu, na podstawie wyborów użytkownika.
-   `mybackups/classes/MyBackupsTimeBudget.php`: Pomaga zarządzać limitami czasu wykonania dla długotrwałych procesów, umożliwiając modułowi gracefulne zatrzymanie i zapisanie stanu przed osiągnięciem `max_execution_time`.
-   `mybackups/classes/MyBackupsTokenCrypto.php`: Obsługuje szyfrowanie i deszyfrowanie wrażliwych tokenów OAuth i kluczy API w celu bezpiecznego przechowywania.
-   `mybackups/classes/MyBackupsZip.php`: Zarządza kompresją i dekompresją plików kopii zapasowych do archiwów ZIP.

#### Podklasy przechowywania (`classes/storage/`)

Ten katalog zawiera klasy implementujące `MyBackupsStorageInterface` dla różnych backendów przechowywania.

-   `mybackups/classes/storage/index.php`: Standardowy pusty plik `index.php`.
-   `mybackups/classes/storage/MyBackupsCloudUploader.php`: Ogólna klasa do zarządzania procesem przesyłania do pamięci masowej w chmurze, potencjalnie obsługująca przesyłanie fragmentowane i śledzenie postępu.
-   `mybackups/classes/storage/MyBackupsDropboxStorage.php`: Implementuje `MyBackupsStorageInterface` do interakcji z API Dropbox.
-   `mybackups/classes/storage/MyBackupsFtpStorage.php`: Implementuje `MyBackupsStorageInterface` do interakcji z serwerami FTP/FTPS.
-   `mybackups/classes/storage/MyBackupsGoogleDriveStorage.php`: Implementuje `MyBackupsStorageInterface` do interakcji z API Google Drive.
-   `mybackups/classes/storage/MyBackupsHttp.php`: Klasa narzędziowa do wykonywania żądań HTTP, prawdopodobnie używana przez klasy przechowywania w chmurze do wywołań API.
-   `mybackups/classes/storage/MyBackupsLocalStorage.php`: Implementuje `MyBackupsStorageInterface` do przechowywania i pobierania kopii zapasowych w lokalnym systemie plików serwera.
-   `mybackups/classes/storage/MyBackupsS3Storage.php`: Implementuje `MyBackupsStorageInterface` do interakcji z Amazon S3.
-   `mybackups/classes/storage/MyBackupsStorageFactory.php`: Klasa wzorca fabryki odpowiedzialna za tworzenie instancji odpowiedniej klasy przechowywania na podstawie konfiguracji.
-   `mybackups/classes/storage/MyBackupsStorageInterface.php`: Definiuje kontrakt (metody), które muszą implementować wszystkie klasy przechowywania (np. `upload`, `download`, `delete`, `list_files`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `mybackups/lib/searchTool/views/js/autocomplete.js`:
    -   **Zakres:** Prawdopodobnie Panel administracyjny.
    -   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania, być może do wyszukiwania w tabelach bazy danych podczas konfigurowania wykluczeń lub do filtrowania list kopii zapasowych.
-   `mybackups/views/js/mybackups-cloud.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Obsługuje interakcje po stronie klienta dla konfiguracji przechowywania w chmurze. Obejmuje to wywołania AJAX do łączenia/rozłączania z usługami, aktualizowania interfejsu użytkownika na podstawie statusu połączenia i potencjalnie obsługi przeglądania folderów w usługach chmurowych.
-   `mybackups/views/js/mybackups-job.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Zarządza wyświetlaniem postępu w czasie rzeczywistym dla zadań tworzenia i przywracania kopii zapasowych. Używa AJAX do odpytywania kontrolera front-end `job.php` o aktualizacje stanu zadania, aktualizując paski postępu, komunikaty o statusie i obsługując powiadomienia o zakończeniu lub niepowodzeniu zadania.
-   `mybackups/views/js/mybackups-table-picker.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Zapewnia interaktywny interfejs do wybierania lub wykluczania tabel bazy danych podczas tworzenia kopii zapasowej, potencjalnie obejmujący funkcje wyszukiwania i wielokrotnego wyboru.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `mybackups/lib/searchTool/views/css/autocomplete.css`:
    -   **Zakres:** Stylizacja Panelu administracyjnego.
    -   **Szczegóły:** Style dla pól wprowadzania autouzupełniania i list sugestii używanych w Panelu administracyjnym.
-   `mybackups/views/css/admin.css`:
    -   **Zakres:** Stylizacja Panelu administracyjnego.
    -   **Szczegóły:** Zawiera główną stylizację interfejsu Panelu administracyjnego modułu, w tym pulpitu nawigacyjnego, listy kopii zapasowych, formularzy, pasków postępu i sekcji integracji z chmurą. Deweloperzy mogą nadpisać te style w swoim niestandardowym motywie administracyjnym lub dodając niestandardowy CSS za pomocą haka, jeśli to konieczne.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   `mybackups/lib/searchTool/views/scripts.tpl`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Prawdopodobnie zawiera zasoby JavaScript i CSS dla narzędzia wyszukiwania/autouzupełniania, potencjalnie podłączone do `displayBackOfficeHeader` lub podobnego.
-   `mybackups/views/templates/admin/backups.tpl`:
    -   **Zakres:** Szablon administracyjny.
    -   **Szczegóły:** Główny szablon do wyświetlania listy istniejących kopii zapasowych, w tym kolumn dla daty, rozmiaru, lokalizacji i przycisków akcji (pobierz, przywróć, usuń). Jest to rdzeń wyświetlania `AdminMyBackupsController`.
-   `mybackups/views/templates/admin/configure.tpl`:
    -   **Zakres:** Szablon administracyjny.
    -   **Szczegóły:** Renderuje główny formularz konfiguracyjny modułu, zazwyczaj dostępny za pośrednictwem `getContent()` w głównym pliku modułu. Obejmuje to ustawienia ogólne i początkową konfigurację integracji usług chmurowych.
-   `mybackups/views/templates/admin/dashboard.tpl`:
    -   **Zakres:** Szablon administracyjny.
    -   **Szczegóły:** Nadrzędny szablon pulpitu nawigacyjnego dla sekcji „Moje kopie zapasowe”, łączący elementy takie jak lista kopii zapasowych, przycisk „Utwórz nową kopię zapasową”, wskaźniki statusu chmury i potencjalnie informacje o zaplanowanych kopiach zapasowych.
-   `mybackups/views/templates/admin/job-progress.tpl`:
    -   **Zakres:** Szablon administracyjny.
    -   **Szczegóły:** Wyświetla pasek postępu i komunikaty o statusie dla trwających zadań tworzenia lub przywracania kopii zapasowych, dynamicznie aktualizowane przez `mybackups-job.js`.
-   `mybackups/views/templates/admin/table-picker.tpl`:
    -   **Zakres:** Szablon administracyjny.
    -   **Szczegóły:** Renderuje interfejs do wybierania lub wykluczania tabel bazy danych podczas tworzenia kopii zapasowej.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL do przechowywania samych danych kopii zapasowych, ponieważ kopie zapasowe są plikami.
    -   Będzie przechowywać wartości konfiguracyjne w tabeli `ps_configuration` PrestaShop, takie jak:
        -   Klucze/sekrety API chmury (zaszyfrowane).
        -   Tokeny OAuth (zaszyfrowane).
        -   Ustawienia specyficzne dla modułu (np. domyślne lokalizacje kopii zapasowych, token cron).
        -   Informacje o stanie zadania dla `MyBackupsStateManager`.
-   **Tabela zarejestrowanych haków**:
    Moduł wykorzystuje głównie haki Panelu administracyjnego i kontrolery front-end do swojej funkcjonalności. Wymienione haki front-office (Header, Columns, Product, Footer) prawdopodobnie *nie* są używane przez ten moduł, ponieważ jego funkcjonalność jest czysto administracyjna i skoncentrowana na backendzie. Gdyby były używane, byłoby to w bardzo specyficznych, niewidocznych celach, takich jak ładowanie zasobów lub wykonywanie kontroli w tle.

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` stron Panelu administracyjnego. | Służy do wstrzykiwania CSS specyficznego dla modułu (`admin.css`) i JavaScript (`mybackups-cloud.js`, `mybackups-job.js`, `mybackups-table-picker.js`, `autocomplete.js`) do panelu administracyjnego. |
| `displayAdminProductsExtra` (lub podobny) | Potencjalnie do dodania opcji kopii zapasowej na stronie edycji produktu, choć mało prawdopodobne dla tego modułu. | (Jeśli używany) Do dodania konkretnej akcji kopii zapasowej lub informacji związanych z danymi produktu. |
| `actionModuleInstall` | Wykonywany podczas instalacji modułu. | Tworzy niezbędne katalogi, ustawia domyślne wartości konfiguracyjne, rejestruje zakładki menu administracyjnego i potencjalnie konfiguruje początkowe instrukcje zadania cron. |
| `actionModuleUninstall` | Wykonywany podczas odinstalowywania modułu. | Czyści wartości konfiguracyjne, usuwa zakładki menu administracyjnego i usuwa katalogi specyficzne dla modułu (choć często pozostawia pliki kopii zapasowych dla bezpieczeństwa). |
| `actionAdminControllerSetMedia` | Wykonywany przed renderowaniem strony przez kontroler administracyjny. | Służy do dodawania specyficznych zasobów CSS/JS tylko do własnych stron administracyjnych modułu (`AdminMyBackupsController`). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Kopia zapasowa bazy danych lokalnie i w chmurze”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności i konfiguracji modułu.
