---
title: "Eksportuj klientów z adresem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Eksportuj klientów z adresem” od MyPresta.eu."
sidebar:
  label: "Eksportuj klientów z adresem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Export Customers with address na MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-customers-with-address.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/export-customers-with-address/)
>
> ---


# Eksportuj klientów z adresem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające dla modułów PrestaShop. Brak specjalnych wymagań hostingowych poza standardowym środowiskiem PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” na module przeniesie Cię do jego głównej strony konfiguracji. Ten ekran głównie obsługuje wewnętrzne ustawienia modułu związane z aktualizacjami.

- **Co robi to ustawienie:** Ta sekcja zazwyczaj zarządza wewnętrznymi kontrolami aktualizacji modułu i informacjami o wersji. Te ustawienia są zazwyczaj do wewnętrznego użytku modułu, aby zapewnić, że używasz najnowszej wersji i aby dostarczać powiadomienia o aktualizacjach.
- **Wpływ zmiany tego ustawienia:**
  - *`mypresta_updates`*: Jest to prawdopodobnie wewnętrzna flaga do włączania lub wyłączania kontroli aktualizacji z MyPresta.eu.
  - *`update_`*: Może przechowywać czas ostatniej kontroli aktualizacji.
  - *`updatev_`*: Może przechowywać najnowszą wykrytą dostępną wersję.
- **Zalecana wartość:** Ogólnie zaleca się pozostawienie tych ustawień na ich domyślnych wartościach, aby zapewnić otrzymywanie ważnych powiadomień o aktualizacjach.
- **Scenariusz/przykład dla sprzedawcy:** Zazwyczaj nie wchodzisz w bezpośrednią interakcję z tymi ustawieniami. Działają one w tle, informując Cię, czy dostępna jest nowa wersja modułu, zapewniając dostęp do najnowszych funkcji i poprawek błędów.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

#### 2.2.1 Eksportuj klientów z adresem (Panel administracyjny > Zaawansowane > Eksportuj klientów z adresem)

Jest to główny ekran, na którym będziesz wykonywać eksport klientów. Możesz go znaleźć w menu „Zaawansowane” w panelu administracyjnym PrestaShop.

- **Nazwa ekranu i lokalizacja w menu:** **Zaawansowane > Eksportuj klientów z adresem**
- **Dostępne działania i ustawienia:**
  - Po przejściu do tego ekranu zobaczysz przycisk lub link do rozpoczęcia procesu eksportu. Moduł automatycznie przygotowuje plik CSV zawierający wszystkie dane klientów i ich powiązane adresy.
  - Wyeksportowany plik będzie zawierał następujące kolumny, sformatowane dla narzędzia importu PrestaShop:
    - **ID klienta**: Unikalny identyfikator klienta.
    - **Aktywny (0/1)**: Czy konto klienta jest aktywne (1) czy nieaktywne (0).
    - **ID tytułu (Pan = 1, Pani = 2, inne = 0)**: ID odpowiadające tytułowi klienta (np. Pan, Pani).
    - \*\*E-mail \*\*\*: Adres e-mail klienta (obowiązkowy).
    - \*\*Hasło \*\*\*: Hasło klienta (obowiązkowe, zazwyczaj zahashowane).
    - **Data urodzenia (rrrr-mm-dd)**: Data urodzenia klienta.
    - \*\*Nazwisko \*\*\*: Nazwisko klienta (obowiązkowe).
    - \*\*Imię \*\*\*: Imię klienta (obowiązkowe).
    - **Newsletter (0/1)**: Czy klient jest subskrybentem newslettera (1) czy nie (0).
    - **Zgoda (0/1)**: Czy klient wyraził zgodę na oferty partnerów (1) czy nie (0).
    - **Data rejestracji**: Data rejestracji konta klienta.
    - **Grupy (x,y,z…)**: Lista identyfikatorów grup klientów, do których należy klient, oddzielona przecinkami.
    - **Domyślny ID grupy**: ID domyślnej grupy klienta.
    - **ID / Nazwa sklepu**: ID lub nazwa sklepu, z którym klient jest powiązany (przydatne w środowiskach wielosklepowych).
    - **ID adresu**: Unikalny identyfikator adresu klienta.
    - \*\*Alias \*\*\*: Alias dla adresu (np. „Mój adres domowy”).
    - \*\*E-mail klienta \*\*\*: Adres e-mail powiązany z tym adresem (powinien odpowiadać adresowi e-mail klienta).
    - **Producent**: (Jeśli dotyczy)
    - **Dostawca**: (Jeśli dotyczy)
    - **Firma**: Nazwa firmy powiązana z adresem.
    - … i inne standardowe pola adresowe, takie jak `Adres1`, `Adres2`, `Kod pocztowy`, `Miasto`, `Kraj`, `Telefon`, `Telefon komórkowy`, `Numer VAT` itp.
- **Wpływ zmian:** Kliknięcie przycisku eksportu wygeneruje i pobierze plik CSV na Twój komputer. Ta akcja nie modyfikuje żadnych danych w Twoim sklepie PrestaShop; jedynie je wyodrębnia.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. **Regularne kopie zapasowe:** Okresowo eksportuj dane klientów jako kopię zapasową, zwłaszcza przed dużymi aktualizacjami sklepu lub migracjami.
  2. **Generowanie list marketingowych:** Eksportuj dane klientów, aby tworzyć listy do kampanii e-mail marketingowych, segmentując je według grup lub dat rejestracji.
  3. **Aktualizacje CRM:** Jeśli używasz zewnętrznego CRM, eksportuj dane, aby utrzymać je zsynchronizowane z bazą klientów PrestaShop.

#### 2.2.2 AdminExportCustomersController (index.php)

Ten plik prawdopodobnie służy jako punkt wejścia lub pomocnik dla `AdminExportCustomersController`, zapewniając prawidłowe funkcjonowanie interfejsu administracyjnego modułu w panelu administracyjnym PrestaShop. Nie przedstawia oddzielnego konfigurowalnego ekranu, ale raczej ułatwia wyświetlanie i funkcjonalność głównego ekranu eksportu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | `mypresta_updates` | Włączone | Wewnętrzna flaga dla kontroli aktualizacji MyPresta.eu. Pozostaw włączone dla powiadomień. |
| Strona konfiguracji modułu | `update_` | (Wewnętrzne) | Przechowuje znacznik czasu ostatniej kontroli aktualizacji. |
| Strona konfiguracji modułu | `updatev_` | (Wewnętrzne) | Przechowuje najnowszą dostępną wersję modułu. |
| Zaawansowane > Eksportuj klientów z adresem | Przycisk Eksportuj | N/A | Inicjuje pobieranie pliku CSV zawierającego wszystkie dane klientów i adresów. |
| Zaawansowane > Eksportuj klientów z adresem | Wyeksportowane kolumny CSV | N/A | Zawiera ID klienta, Aktywny, ID tytułu, E-mail, Hasło, Data urodzenia, Nazwisko, Imię, Newsletter, Zgoda, Data rejestracji, Grupy, Domyślny ID grupy, ID/Nazwa sklepu, ID adresu, Alias, E-mail klienta, Firma i wszystkie standardowe pola adresowe. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Kliknąłem przycisk eksportu, ale nic się nie stało lub plik jest pusty.**
**O1:**

- **Sprawdź blokery wyskakujących okienek w przeglądarce:** Twoja przeglądarka może blokować pobieranie pliku. Poszukaj powiadomienia lub ikony na pasku adresu przeglądarki i zezwól na pobieranie z panelu administracyjnego PrestaShop.
- **Uprawnienia modułu:** Upewnij się, że moduł ma niezbędne uprawnienia systemu plików do tworzenia i udostępniania pliku CSV. Chociaż rzadko, nieprawidłowe uprawnienia mogą uniemożliwić generowanie pliku.
- **Limity pamięci serwera:** Jeśli masz bardzo dużą liczbę klientów, proces eksportu może przekroczyć limity pamięci PHP na Twoim serwerze. Sprawdź logi błędów PHP serwera (często znajdujące się w `var/logs` lub w panelu sterowania hostingu) pod kątem błędów związanych z pamięcią. Może być konieczne tymczasowe zwiększenie `memory_limit` w pliku `php.ini`.
- **Pusta baza danych klientów:** Upewnij się, że faktycznie masz zarejestrowanych klientów w swoim sklepie.

**P2: Wyeksportowany plik CSV wygląda na zniekształcony lub zawiera dziwne znaki.**
**O2:** Jest to często problem z kodowaniem.

- **Otwórz z prawidłowym kodowaniem:** Podczas otwierania pliku CSV w programie arkusza kalkulacyjnego (takim jak Excel) upewnij się, że wybierasz **UTF-8** jako źródło pliku lub kodowanie. Większość nowoczesnych systemów używa UTF-8, a eksporty PrestaShop są zazwyczaj w tym formacie.
- **Sprawdź ustawienia języka PrestaShop:** Upewnij się, że domyślny język i zestaw znaków Twojego sklepu PrestaShop są poprawnie skonfigurowane w **Międzynarodowe > Lokalizacja**.

**P3: Czy mogę wybrać, które pola mają być eksportowane?**
**O3:** Ten moduł eksportuje predefiniowany zestaw pól klienta i adresu, które są kompatybilne z natywnym narzędziem importu PrestaShop. Nie oferuje opcji wyboru lub odznaczania poszczególnych pól. Jeśli potrzebujesz wysoce spersonalizowanego eksportu, możesz potrzebować bardziej zaawansowanego modułu eksportu lub niestandardowego rozwoju.

**P4: Czy eksportowanie klientów wpłynie na wydajność mojego sklepu?**
**O4:** Dla większości sklepów jednorazowy eksport będzie miał znikomy wpływ. Dla sklepów z setkami tysięcy klientów proces eksportu może zająć kilka chwil i zużyć pewne zasoby serwera. Ogólnie zaleca się wykonywanie dużych eksportów poza godzinami szczytu, jeśli przewidujesz bardzo długi czas przetwarzania. Moduł jest zaprojektowany tak, aby był wydajny, ale zasoby serwera zawsze są czynnikiem.

**P5: Chcę ponownie zaimportować klientów po wprowadzeniu zmian. Jak to zrobić?**
**O5:** Ten moduł obsługuje tylko eksport. Aby ponownie zaimportować, użyj natywnego narzędzia importu PrestaShop:

1. Przejdź do **Zaawansowane > Importuj**.
2. Wybierz „Klienci” lub „Adresy” jako encję do importu.
3. Prześlij zmodyfikowany plik CSV.
4. Ostrożnie zmapuj kolumny z pliku CSV do pól bazy danych PrestaShop.

Zawsze testuj importy najpierw w środowisku deweloperskim lub testowym i upewnij się, że masz pełną kopię zapasową bazy danych przed wykonaniem jakichkolwiek importów na dużą skalę w swoim sklepie produkcyjnym. Nieprawidłowe importy mogą prowadzić do utraty lub uszkodzenia danych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Eksportuj klientów z adresem” (`exportcustomers`) to prosty moduł PrestaShop, skupiający się głównie na funkcjonalności Back Office. Podąża za standardowym wzorcem MVC PrestaShop dla swojego interfejsu administracyjnego. Główna logika znajduje się w głównym pliku modułu i dedykowanym kontrolerze administracyjnym. Nie wprowadza nowych tabel bazy danych, ale wykorzystuje istniejące struktury `ObjectModel` `Customer` i `Address` PrestaShop do pobierania i formatowania danych do eksportu. Prostota modułu oznacza, że nie ma on komponentów Front Office, niestandardowych klas ani złożonych zasobów JavaScript/CSS.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front Office**: Brak. Ten moduł nie ma funkcjonalności Front Office.
- **Kontrolery administracyjne Back Office**:

  - `exportcustomers/controllers/admin/AdminExportCustomers.php`
    - **Nazwa klasy i klasa nadrzędna**: `AdminExportCustomersController` rozszerzający `ModuleAdminController`.
    - **Odpowiedzialność**: Jest to główny kontroler odpowiedzialny za obsługę logiki eksportu klientów i adresów. Po uzyskaniu dostępu za pośrednictwem menu panelu administracyjnego PrestaShop inicjuje proces pobierania danych klientów i adresów z bazy danych, formatowania ich w ciąg CSV i wysyłania jako plik do pobrania do przeglądarki. Konstruuje wiersz nagłówka CSV ze wszystkimi określonymi polami (ID klienta, E-mail, ID adresu, Alias itp.), a następnie iteruje przez obiekty `Customer` i `Address`, aby wypełnić wiersze danych.
  - `exportcustomers/controllers/admin/index.php`
    - **Odpowiedzialność**: Jest to typowy plik zastępczy w katalogach kontrolerów administracyjnych modułów PrestaShop. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome')` lub podobne przekierowanie, aby zapobiec bezpośredniemu listowaniu katalogów lub dostępowi, zapewniając bezpieczeństwo i prawidłowe routowanie w panelu administracyjnym PrestaShop. Nie zawiera żadnej logiki funkcjonalnej dla samego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowe klasy `ObjectModel` PrestaShop `Customer` i `Address` do pobierania danych z bazy danych.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Proces eksportu jest zazwyczaj inicjowany przez proste przesłanie formularza lub bezpośredni link, obsługiwany w całości przez kontroler PHP.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Jego interfejs Back Office opiera się w całości na domyślnej stylizacji panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. `AdminExportCustomersController` prawdopodobnie renderuje bardzo prosty widok, być może tylko przycisk lub wiadomość, bezpośrednio w swojej metodzie `renderForm()` lub `initContent()`, lub bezpośrednio wyzwala pobieranie pliku bez renderowania złożonego szablonu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Odczytuje dane z istniejących tabel PrestaShop, głównie `ps_customer` i `ps_address`.

  - `ps_configuration`: Moduł przechowuje swoje wewnętrzne ustawienia konfiguracyjne (`mypresta_updates`, `update_`, `updatev_`) w tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:
  Ten moduł nie rejestruje żadnych hooków Front Office. Jego funkcjonalność jest całkowicie ograniczona do Back Office.
  Prawdopodobnie używa hooka `actionAdminControllerSetMedia` (niejawnie lub jawnie) dla swojego kontrolera administracyjnego, a potencjalnie `displayAdminProductsExtra` lub podobnego dla swojego elementu menu Back Office.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany podczas inicjalizacji kontrolera administracyjnego. | Używany przez `ModuleAdminController` do dodawania zasobów CSS/JS (chociaż ten moduł ich nie ma). |
| `displayAdminAdvancedParameters` | Renderuje zawartość w sekcji „Zaawansowane” panelu administracyjnego. | Prawdopodobnie używany do dodawania linku/punktu wejścia modułu do menu „Zaawansowane”. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Eksportuj klientów z adresem” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
