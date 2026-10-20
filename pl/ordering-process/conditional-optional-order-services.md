---
title: "Warunkowe Opcjonalne Usługi Zamówienia - Instrukcja Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Warunkowe Opcjonalne Usługi Zamówienia” od MyPresta.eu."
sidebar:
  label: "Warunkowe Opcjonalne Usługi Zamówienia - Instrukcja Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Conditional Optional Order Services na MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-optional-order-services.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/conditional-optional-order-services/)
>
> ---


# Warunkowe Opcjonalne Usługi Zamówienia

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Moduł „Warunkowe Opcjonalne Usługi Zamówienia” oferuje potężny zestaw narzędzi do zarządzania opcjonalnymi usługami. Będziesz głównie wchodzić w interakcje z modułem poprzez jego dedykowane wpisy menu w Panelu administracyjnym PrestaShop.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest początkowy ekran, który widzisz po zainstalowaniu modułu lub kliknięciu „Konfiguruj” w Menedżerze modułów. Zapewnia szybki sposób na włączenie lub wyłączenie podstawowej funkcjonalności modułu.

- **Nazwa ustawienia:** Włącz Warunkowe Opcjonalne Usługi Zamówienia
- **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu. Po włączeniu, logika modułu zostanie uruchomiona, a zdefiniowane usługi będą oferowane klientom zgodnie z Twoimi zasadami. Po wyłączeniu, żadne usługi nie będą oferowane, a moduł będzie faktycznie nieaktywny w Twoim front-office.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu:* Moduł rozpocznie ocenę Twoich zasad usług i wyświetlanie odpowiednich usług klientom w front-office (np. na stronie realizacji zamówienia).
  - *Po wyłączeniu:* Wszystkie warunkowe usługi zostaną ukryte przed klientami, a logika modułu nie zostanie wykonana.
- **Zalecana wartość:** **TAK** (Włączone) po skonfigurowaniu zasad.
- **Scenariusz / przykład sprzedawcy:** Właśnie zainstalowałeś moduł i jesteś gotowy do definiowania swoich usług. Włączysz to ustawienie, aby Twoje usługi były widoczne dla klientów po ich skonfigurowaniu. Jeśli musisz tymczasowo przestać oferować wszystkie usługi (np. podczas konserwacji lub okresu świątecznego), możesz szybko wyłączyć je tutaj bez usuwania swoich zasad.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Po początkowej konfiguracji znajdziesz nowe wpisy menu w sekcji **Sprzedaż > Usługi zamówienia** (lub podobnej lokalizacji, w zależności od Twojej wersji PrestaShop i motywu).

#### 2.2.1 Zasady (Panel administracyjny > Sprzedaż > Usługi zamówienia > Zasady)

Tutaj definiujesz i zarządzasz wszystkimi swoimi warunkowymi opcjonalnymi usługami zamówienia. Każda „Zasada” reprezentuje konkretną usługę, którą chcesz zaoferować, wraz z regułami, które określają, kiedy i komu jest ona oferowana.

- **Nazwa ekranu i lokalizacja w menu:** Zasady (W sekcji **Sprzedaż > Usługi zamówienia** w głównym menu PrestaShop).
- **Dostępne działania i ustawienia:**

  - **Lista zasad:** Tabela wyświetlająca wszystkie utworzone zasady, pokazująca ich nazwę, status (aktywny/nieaktywny) i inne kluczowe informacje.
  - **Dodaj nową zasadę:** Kliknij ten przycisk, aby utworzyć zupełnie nową opcjonalną usługę.
  - **Edytuj zasadę:** Kliknij ikonę „Edytuj” obok istniejącej zasady, aby zmodyfikować jej szczegóły, warunki i reguły.
  - **Duplikuj zasadę:** Bardzo przydatna funkcja! Kliknij ikonę „Duplikuj”, aby utworzyć dokładną kopię istniejącej zasady. Pozwala to zaoszczędzić czas, jeśli musisz utworzyć podobne usługi.
  - **Usuń zasadę:** Usuń zasadę na stałe.
  - **Działania masowe:** Wybierz wiele zasad i wykonaj działania takie jak „Włącz”, „Wyłącz” lub „Usuń” je jednocześnie.
- **Podczas dodawania/edycji zasady skonfigurujesz:**

  - **Informacje ogólne:**
    - **Nazwa:** Jasna, wewnętrzna nazwa Twojej zasady (np. „Usługa pakowania na prezent”, „Ubezpieczenie przesyłki ekspresowej”).
    - **Status:** Włącz lub wyłącz tę konkretną zasadę. Nieaktywna zasada nigdy nie zostanie pokazana klientom.
    - **Opis:** Tekst, który klienci zobaczą, wyjaśniający usługę. Bądź zwięzły i podkreśl korzyści.
    - **Cena:** Koszt tej opcjonalnej usługi. Zostanie on dodany do koszyka klienta, jeśli zostanie wybrany.
    - **Reguła podatkowa:** Wybierz odpowiednią regułę podatkową dla tej usługi (np. „Stawka standardowa”, „Stawka obniżona”).
    - **Obraz/Ikona:** Prześlij obraz lub ikonę, aby wizualnie przedstawić usługę klientom. Dzięki temu jest ona bardziej atrakcyjna i łatwiejsza do zidentyfikowania.
  - **Warunki:** To jest rdzeń mocy modułu. Tutaj budujesz reguły za pomocą wizualnego kreatora warunków, aby określić, *kiedy* ta usługa powinna być oferowana.
    - Możesz łączyć wiele warunków za pomocą logiki „AND” lub „OR”.
    - **Przykłady warunków:**
      - **Wartość koszyka:** Oferuj usługę tylko wtedy, gdy suma koszyka jest powyżej/poniżej określonej kwoty.
      - **Produkt w koszyku:** Oferuj usługę tylko wtedy, gdy w koszyku znajdują się konkretne produkty lub produkty z określonych kategorii/producentów.
      - **Grupa klientów:** Oferuj usługę tylko określonym grupom klientów (np. „Hurtownicy”, „Klienci VIP”).
      - **Przewoźnik:** Oferuj usługę tylko wtedy, gdy wybrany jest konkretny przewoźnik.
      - **Zakres dat:** Oferuj usługę tylko w określonym okresie promocyjnym.
      - **Kraj/Strefa:** Oferuj usługę tylko klientom z określonych krajów lub stref wysyłki.
  - **Ustawienia wyświetlania:** Kontroluj, jak usługa pojawia się w front-office.
    - **Pozycja:** Jeśli oferowanych jest wiele usług, możesz ustawić ich kolejność wyświetlania.
    - **Widoczność:** Gdzie dokładnie w procesie realizacji zamówienia pojawia się usługa.
- **Efekt zmian:**

  - Dodanie nowej zasady sprawia, że nowa opcjonalna usługa jest dostępna do wyświetlenia klientom, z zastrzeżeniem jej warunków.
  - Edycja zasady zmienia jej nazwę, cenę, opis, obraz lub warunki, w których jest oferowana. Zmiany te są natychmiast odzwierciedlane w front-office.
  - Włączenie/wyłączenie zasady kontroluje jej widoczność dla klientów.
  - Usunięcie zasady usuwa ją całkowicie i nie będzie już oferowana.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

  1. Zacznij od zdefiniowania najczęściej używanych usług (np. pakowanie na prezent, ubezpieczenie).
  2. Użyj kreatora warunków, aby te usługi były bardzo trafne. Na przykład, pakowanie na prezent może być oferowane tylko dla produktów fizycznych, a nie dla pobrań cyfrowych.
  3. Regularnie przeglądaj swoje zasady, zwłaszcza przed promocjami lub wyprzedażami sezonowymi, aby upewnić się, że są aktywne i poprawnie skonfigurowane.
  4. Wykorzystaj funkcję „Duplikuj”, aby szybko tworzyć warianty istniejących usług (np. „Pakowanie na prezent Premium” vs. „Standardowe pakowanie na prezent”).

#### 2.2.2 Dziennik audytu (Panel administracyjny > Sprzedaż > Usługi zamówienia > Dziennik audytu)

Ten ekran zapewnia szczegółową historię wszystkich działań związanych z zasadami i usługami modułu. Jest to nieocenione narzędzie do śledzenia zmian i rozwiązywania problemów.

- **Nazwa ekranu i lokalizacja w menu:** Dziennik audytu (W sekcji **Sprzedaż > Usługi zamówienia** w głównym menu PrestaShop).
- **Dostępne działania i ustawienia:**
  - **Lista logów:** Tabela pokazująca chronologiczną listę zdarzeń.
  - **Kolumny zazwyczaj obejmują:**
    - **Data:** Kiedy zdarzenie miało miejsce.
    - **Pracownik:** Który użytkownik Panelu administracyjnego wykonał akcję.
    - **Akcja:** Jaka akcja została podjęta (np. „Zasada dodana”, „Zasada edytowana”, „Zasada usunięta”, „Moduł włączony/wyłączony”).
    - **Szczegóły:** Konkretne informacje o zmianie (np. której zasady dotyczyła, jakie wartości zostały zmienione).
  - **Filtrowanie/Wyszukiwanie:** Narzędzia do filtrowania dziennika według daty, pracownika lub typu akcji, aby znaleźć konkretne zdarzenia.
- **Efekt zmian:** Ten ekran służy tylko do przeglądania; nie można tutaj wprowadzać bezpośrednich zmian. Służy jako zapis wszystkich modyfikacji dokonanych w konfiguracji modułu i zasadach.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  - Użyj dziennika audytu, aby śledzić, kto wprowadził zmiany w Twoich zasadach usług, zwłaszcza w środowiskach wieloużytkownikowych.
  - Jeśli usługa nie pojawia się zgodnie z oczekiwaniami, sprawdź dziennik audytu, aby zobaczyć, czy zasada została przypadkowo wyłączona lub zmodyfikowana.
  - Monitoruj wszelkie nieoczekiwane zachowania modułu zarejestrowane w dziennikach.

#### 2.2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz Warunkowe Opcjonalne Usługi Zamówienia | TAK (po konfiguracji) | Główny przełącznik dla funkcjonalności modułu w front-office. |
| **Zasady (Lista)** | Dodaj nową zasadę | N/A | Utwórz nową opcjonalną usługę z własnymi regułami i cenami. |
| **Zasady (Lista)** | Edytuj zasadę | N/A | Modyfikuj szczegóły, warunki lub wyświetlanie istniejącej usługi. |
| **Zasady (Lista)** | Duplikuj zasadę | N/A | Szybko utwórz kopię istniejącej zasady, aby zaoszczędzić czas. |
| **Zasady (Lista)** | Usuń zasadę | N/A | Trwale usuń opcjonalną usługę. |
| **Zasady (Formularz edycji)** | Nazwa | Opisowa nazwa | Wewnętrzny identyfikator usługi. |
| **Zasady (Formularz edycji)** | Status | Włączone | Kontroluje, czy ta konkretna usługa jest aktywna i widoczna dla klientów. |
| **Zasady (Formularz edycji)** | Opis | Jasne wyjaśnienie | Tekst wyświetlany klientom o usłudze. |
| **Zasady (Formularz edycji)** | Cena | 0.00 (ustaw wartość) | Koszt dodawany do koszyka, jeśli usługa zostanie wybrana. |
| **Zasady (Formularz edycji)** | Reguła podatkowa | Domyślna reguła podatkowa | Obowiązujący podatek dla usługi. |
| **Zasady (Formularz edycji)** | Obraz/Ikona | Przesłany obraz | Wizualna reprezentacja usługi dla klientów. |
| **Zasady (Formularz edycji)** | Warunki (Kreator) | Niestandardowe reguły | Definiuje, *kiedy* i *komu* usługa jest oferowana (np. wartość koszyka, produkt w koszyku, grupa klientów). |
| **Zasady (Formularz edycji)** | Pozycja | Auto (ustaw wartość) | Kolejność wyświetlania, jeśli oferowanych jest wiele usług. |
| **Dziennik audytu** | (Wszystkie wpisy) | N/A | Zapewnia historyczny zapis wszystkich zmian dokonanych w ustawieniach modułu i zasadach. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P1: Moje opcjonalne usługi nie pojawiają się na stronie realizacji zamówienia. Co powinienem sprawdzić?**
O1:

1.  **Moduł włączony?** Przejdź do **Moduły > Menedżer modułów**, znajdź „Warunkowe Opcjonalne Usługi Zamówienia” i upewnij się, że jest włączony.
2.  **Status zasady?** Przejdź do **Sprzedaż > Usługi zamówienia > Zasady**. Upewnij się, że konkretna zasada, którą spodziewasz się zobaczyć, jest „Aktywna”.
3.  **Warunki zasady spełnione?** To najczęstszy powód. Dokładnie przejrzyj warunki, które ustawiłeś dla zasady. Czy Twój obecny koszyk testowy spełnia *wszystkie* warunki „AND” i *dowolne* warunki „OR”? Na przykład, jeśli ustawiłeś „Suma koszyka > 50 $”, a Twój koszyk wynosi 45 $, usługa się nie pojawi.
4.  **Pamięć podręczna?** Wyczyść pamięć podręczną PrestaShop w **Zaawansowane > Wydajność**. Czasami stare dane z pamięci podręcznej mogą uniemożliwić pojawienie się nowych konfiguracji modułu.
5.  **Kompatybilność motywu?** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, bardzo mocno dostosowane motywy mogą wymagać drobnych poprawek. Sprawdź konsolę deweloperską przeglądarki pod kątem błędów JavaScript.

**P2: Cena mojej usługi nie jest poprawnie dodawana do sumy koszyka.**
O2:

1.  **Cena zasady ustawiona?** Sprawdź dwukrotnie pole „Cena” w konfiguracji zasady.
2.  **Reguła podatkowa zastosowana?** Upewnij się, że dla usługi wybrano poprawną „Regułę podatkową”. Ostateczna cena zawiera podatki oparte na tej regule.
3.  **Waluta?** Sprawdź, czy cena jest ustawiona w domyślnej walucie Twojego sklepu lub czy ustawienia wielu walut są poprawnie obsługiwane przez PrestaShop.

**P3: Jak przetłumaczyć nazwy i opisy usług na inne języki?**
O3:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz swój język.
3.  Znajdź moduł „Warunkowe Opcjonalne Usługi Zamówienia”. Powinieneś być w stanie przetłumaczyć nazwy i opisy swoich zasad bezpośrednio w formularzach konfiguracji modułu, ponieważ są one zazwyczaj przechowywane jako pola do tłumaczenia. Jeśli nie, pojawią się tutaj.

**P4: Czy mogę zmienić kolejność, w jakiej usługi pojawiają się na stronie realizacji zamówienia?**
O4: Tak, w konfiguracji każdej zasady powinno znajdować się ustawienie „Pozycja”. Możesz ustawić wartość liczbową (np. 10, 20, 30), aby kontrolować kolejność wyświetlania. Niższe liczby pojawiają się jako pierwsze.

**P5: Moduł powoduje problem wizualny lub konflikt z innym modułem.**
O5:

1.  **Izoluj problem:** Tymczasowo wyłącz inne ostatnio zainstalowane lub zaktualizowane moduły, aby sprawdzić, czy konflikt zniknie.
2.  **Sprawdź błędy:** Użyj konsoli deweloperskiej przeglądarki (F12), aby wyszukać błędy JavaScript lub CSS.
3.  **Skontaktuj się z pomocą techniczną:** Jeśli nie możesz rozwiązać problemu, dostarcz wsparciu MyPresta.eu szczegóły dotyczące problemu, Twojej wersji PrestaShop i wszelkich innych modułów, które podejrzewasz o konflikt.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Warunkowe Opcjonalne Usługi Zamówienia”, przeznaczony dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł wykorzystuje solidny wzorzec MVC (Model-View-Controller) typowy dla modułów PrestaShop. W dużym stopniu opiera się na systemie hooków PrestaShop, aby wstrzykiwać swoją funkcjonalność w różnych punktach front-office (realizacja zamówienia, strona produktu) i back-office (widok zamówienia administratora, konfiguracja modułu).
Kluczowe komponenty architektoniczne obejmują:

-   **Zasady (`conorderservicesPolicy`):** Główna encja reprezentująca opcjonalną usługę, rozszerzająca `ObjectModel`.
-   **Warunki (`conorderservicesCondition`, `conorderservicesConditionGroup`, `conorderservicesConditionTree`):** Zaawansowany system do budowania złożonych reguł określających kwalifikowalność usługi.
-   **Silnik (`conorderservicesEngine`):** Centralna klasa odpowiedzialna za ocenę warunków i określanie, które usługi mają być prezentowane klientowi.
-   **Dziennik audytu (`conorderservicesAuditLog`):** Rejestruje wszystkie istotne działania w module w celu śledzenia.
-   **Warstwa kompatybilności (`conorderservicesCompatibility`):** Obsługuje różnice między PrestaShop 1.7, 8 i 9.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `conorderservices/controllers/front/ajax.php`
    -   **Nazwa klasy:** `ConorderservicesAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje żądania AJAX z front-office, głównie w celu dynamicznego aktualizowania wybranych usług lub ponownego obliczania sumy koszyka, gdy usługa jest dodawana/usuwana przez klienta. Prawdopodobnie przekazuje żądania do `conorderservicesEngine` w celu wykonania obliczeń i zwraca odpowiedzi JSON.
-   `conorderservices/controllers/front/index.php`
    -   **Nazwa klasy:** `ConorderservicesIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Kontroler zastępczy lub awaryjny. Często używany do bezpośredniego dostępu do modułu, jeśli jest to konieczne, chociaż większość interakcji z front-office odbywa się za pośrednictwem hooków lub AJAX.

#### Kontrolery administracyjne Back-Office

-   `conorderservices/controllers/admin/AdminconorderservicesAuditLog.php`
    -   **Nazwa klasy:** `AdminconorderservicesAuditLogController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Dziennik audytu (w sekcji „Sprzedaż > Usługi zamówienia”)
    -   **Zarządzana encja:** `conorderservicesAuditLog`
    -   **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem wpisów dziennika audytu. Wykorzystuje `HelperList` PrestaShop do renderowania tabeli dziennika.
-   `conorderservices/controllers/admin/AdminconorderservicesPolicies.php`
    -   **Nazwa klasy:** `AdminconorderservicesPoliciesController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Zasady (w sekcji „Sprzedaż > Usługi zamówienia”)
    -   **Zarządzana encja:** `conorderservicesPolicy`
    -   **Odpowiedzialność:** Główny kontroler do zarządzania zasadami opcjonalnych usług. Obsługuje listowanie, dodawanie, edytowanie, duplikowanie i usuwanie obiektów `conorderservicesPolicy`. Wykorzystuje `HelperList` do listy zasad i `HelperForm` do formularzy dodawania/edycji zasad, w tym złożonego kreatora warunków.
-   `conorderservices/controllers/admin/index.php`
    -   **Nazwa klasy:** `AdminconorderservicesIndexController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** (Prawdopodobnie główny punkt wejścia „Usługi zamówienia”)
    -   **Zarządzana encja:** Brak bezpośrednio, często przekierowuje do `AdminconorderservicesPolicies` lub wyświetla pulpit nawigacyjny.
    -   **Odpowiedzialność:** Służy jako główny punkt wejścia do sekcji administracyjnej modułu, potencjalnie wyświetlając pulpit nawigacyjny lub przekierowując do listy zasad.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `conorderservices/classes/conorderservicesAdmin.php`
    -   **Cel:** Klasa narzędziowa dla funkcji specyficznych dla administratora, potencjalnie obsługująca uprawnienia, generowanie menu lub wspólne zadania administracyjne.
-   `conorderservices/classes/conorderservicesAuditLog.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_conorderservices_log`
    -   **Pola `$definition`:** `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`
    -   **Cel:** Reprezentuje wpis w dzienniku audytu modułu. Udostępnia metody dodawania nowych wpisów do dziennika.
-   `conorderservices/classes/conorderservicesCartState.php`
    -   **Cel:** Zarządza i utrwala stan wybranych opcjonalnych usług w koszyku klienta. Prawdopodobnie wchodzi w interakcje z `Context::getContext()->cart` i przechowuje wybrane usługi.
-   `conorderservices/classes/conorderservicesCompatibility.php`
    -   **Cel:** Zapewnia warstwę abstrakcji dla funkcji lub zachowań specyficznych dla wersji PrestaShop, zapewniając działanie modułu w wersjach 1.7, 8 i 9.
-   `conorderservices/classes/conorderservicesCondition.php`
    -   **Rozszerza:** `ObjectModel` (prawdopodobnie, lub klasa bazowa dla warunków)
    -   **Tabela bazy danych:** `ps_conorderservices_condition`
    -   **Pola `$definition`:** `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`
    -   **Cel:** Reprezentuje pojedynczy warunek w grupie warunków (np. „Suma koszyka” „jest większa niż” „100”).
-   `conorderservices/classes/conorderservicesConditionEvaluator.php`
    -   **Cel:** Silnik logiki do oceny zestawu warunków w kontekście bieżącego koszyka, klienta i produktu. Określa, czy warunki zasady są spełnione.
-   `conorderservices/classes/conorderservicesConditionGroup.php`
    -   **Rozszerza:** `ObjectModel` (prawdopodobnie)
    -   **Tabela bazy danych:** `ps_conorderservices_condition_group`
    -   **Pola `$definition`:** `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR)
    -   **Cel:** Grupuje wiele obiektów `conorderservicesCondition`, definiując logiczną relację między nimi (AND/OR).
-   `conorderservices/classes/conorderservicesConditionTree.php`
    -   **Cel:** Zarządza hierarchiczną strukturą grup warunków i poszczególnych warunków, umożliwiając budowanie złożonych reguł.
-   `conorderservices/classes/conorderservicesContext.php`
    -   **Cel:** Wrapper lub rozszerzenie klasy `Context` PrestaShop, dostarczający danych kontekstowych specyficznych dla modułu (np. bieżący koszyk, klient, język) do oceny warunków.
-   `conorderservices/classes/conorderservicesDashboard.php`
    -   **Cel:** Dostarcza danych i logiki dla widoku pulpitu nawigacyjnego modułu (jeśli istnieje), potencjalnie pokazując analizy lub szybkie statystyki.
-   `conorderservices/classes/conorderservicesEngine.php`
    -   **Cel:** Centralna jednostka przetwarzająca modułu. Pobiera aktywne zasady, przekazuje je do `ConditionEvaluator` i określa, które usługi są kwalifikowalne dla bieżącego koszyka. Obsługuje również dodawanie/usuwanie produktów usługowych z koszyka.
-   `conorderservices/classes/conorderservicesListRenderer.php`
    -   **Cel:** Klasa pomocnicza do renderowania list w Back Office, potencjalnie rozszerzająca `HelperList` lub dostarczająca niestandardową logikę renderowania.
-   `conorderservices/classes/conorderservicesLog.php`
    -   **Cel:** Alias lub specyficzna implementacja do logowania, prawdopodobnie odrębna od `conorderservicesAuditLog` dla różnych typów logowania.
-   `conorderservices/classes/conorderservicesPolicy.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_conorderservices_policy`
    -   **Pola `$definition`:** `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd` (oraz pola `_lang` dla tłumaczeń `name`, `description`).
    -   **Cel:** Główny model dla opcjonalnej usługi. Przechowuje całą konfigurację usługi, w tym jej szczegóły, cenę, obraz i powiązane grupy warunków.
-   `conorderservices/classes/conorderservicesPolicyDuplicator.php`
    -   **Cel:** Obsługuje logikę duplikowania całej zasady, w tym jej warunków i powiązanych danych.
-   `conorderservices/classes/conorderservicesPreset.php`
    -   **Cel:** Prawdopodobnie dostarcza predefiniowane zestawy warunków lub zasad, które mogą być szybko ładowane przez sprzedawcę.
-   `conorderservices/classes/conorderservicesRule.php`
    -   **Cel:** Bardziej ogólny termin dla warunku lub zestawu warunków. Może być abstrakcyjną klasą bazową lub specyficznym typem reguły.
-   `conorderservices/classes/ConorderservicesRuleImage.php`
    -   **Cel:** Zarządza obrazami/ikonami powiązanymi z zasadami lub regułami.
-   `conorderservices/classes/ConorderservicesServiceProduct.php`
    -   **Rozszerza:** `Product` (lub wrapper wokół niego)
    -   **Cel:** Reprezentuje „wirtualny produkt”, który jest dodawany do koszyka, gdy klient wybierze opcjonalną usługę. Zapewnia, że usługa zachowuje się jak zwykły produkt w procesie koszyka i zamówienia.
-   `conorderservices/classes/conorderservicesTreeRepository.php`
    -   **Cel:** Zarządza przechowywaniem i pobieraniem struktury drzewa warunków.
-   `conorderservices/classes/index.php`
    -   **Cel:** Standardowy pusty plik zapobiegający listowaniu katalogów.
-   `conorderservices/classes/load.php`
    -   **Cel:** Plik autoloader lub plik, który zawiera inne definicje klas.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `conorderservices/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Back-office (do wyboru produktu/kategorii w kreatorze warunków)
    -   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych, prawdopodobnie używaną podczas wybierania produktów, kategorii lub producentów w kreatorze warunków.
-   `conorderservices/lib/searchTool/views/views/js/autocomplete.js`
    -   **Zakres:** Back-office (redundantne lub specyficzne dla innego widoku narzędzia wyszukiwania)
    -   **Szczegóły:** Podobnie jak powyżej, prawdopodobnie duplikat lub specyficzna wersja skryptu autouzupełniania.
-   `conorderservices/views/js/adminConditionBuilder.js`
    -   **Zakres:** Back-office (`AdminconorderservicesPoliciesController`)
    -   **Szczegóły:** Podstawowy JS dla wizualnego kreatora warunków. Obsługuje dodawanie/usuwanie warunków i grup warunków, zarządzanie operatorami logicznymi (AND/OR) oraz aktualizowanie interfejsu użytkownika na podstawie danych wejściowych użytkownika.
-   `conorderservices/views/js/adminconorderservicesDashboard.js`
    -   **Zakres:** Back-office (`AdminconorderservicesIndexController` lub widok pulpitu nawigacyjnego)
    -   **Szczegóły:** Skrypty dla interaktywnych elementów na pulpicie nawigacyjnym modułu, takich jak wykresy, statystyki lub szybkie linki.
-   `conorderservices/views/js/adminconorderservicesSearchTool.js`
    -   **Zakres:** Back-office (`AdminconorderservicesPoliciesController`)
    -   **Szczegóły:** Integruje narzędzie wyszukiwania (autouzupełnianie) z kreatorem warunków, umożliwiając administratorom łatwe znajdowanie i wybieranie encji (produktów, kategorii itp.) dla warunków.
-   `conorderservices/views/js/adminconorderservicesSimulator.js`
    -   **Zakres:** Back-office (`AdminconorderservicesPoliciesController` - prawdopodobnie dedykowana zakładka lub modal)
    -   **Szczegóły:** Zapewnia funkcjonalność symulatora zasad, umożliwiając administratorom testowanie warunków z fikcyjnymi danymi koszyka, aby zobaczyć, które usługi byłyby oferowane.
-   `conorderservices/views/js/adminPolicyRuleImage.js`
    -   **Zakres:** Back-office (`AdminconorderservicesPoliciesController`)
    -   **Szczegóły:** Obsługuje funkcjonalność przesyłania i podglądu obrazów dla ikon/obrazów zasad.
-   `conorderservices/views/js/adminPolicyRules.js`
    -   **Zakres:** Back-office (`AdminconorderservicesPoliciesController`)
    -   **Szczegóły:** Ogólne skrypty do zarządzania regułami zasad, potencjalnie obejmujące zmianę kolejności metodą przeciągnij i upuść lub inne interakcje interfejsu użytkownika na stronie edycji zasad.
-   `conorderservices/views/js/adminSettingsOfferDisplay.js`
    -   **Zakres:** Back-office (Główna konfiguracja modułu lub edycja zasad)
    -   **Szczegóły:** Skrypty związane z konfigurowaniem sposobu i miejsca wyświetlania opcjonalnych usług w front-office.
-   `conorderservices/views/js/checkout.js`
    -   **Zakres:** Front-office (strona realizacji zamówienia)
    -   **Szczegóły:** To jest krytyczny skrypt front-office. Nasłuchuje interakcji użytkownika (np. zaznaczania/odznaczania usługi), wysyła żądania AJAX do `ajax.php` w celu aktualizacji koszyka i dynamicznie aktualizuje podsumowanie koszyka oraz sumę na stronie realizacji zamówienia. Prawdopodobnie wiąże się z zdarzeniami `prestashop.on` dla aktualizacji koszyka.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `conorderservices/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Back-office
    -   **Szczegóły:** Style dla rozwijanych list autouzupełniania i pól wejściowych używanych w narzędziu wyszukiwania administratora.
-   `conorderservices/lib/searchTool/views/views/css/autocomplete.css`
    -   **Zakres:** Back-office (redundantne lub specyficzne dla innego widoku narzędzia wyszukiwania)
    -   **Szczegóły:** Podobnie jak powyżej, prawdopodobnie duplikat lub specyficzna wersja stylów autouzupełniania.
-   `conorderservices/views/css/admin_conorderservices.css`
    -   **Zakres:** Back-office
    -   **Szczegóły:** Ogólne style dla stron administracyjnych modułu, w tym listy zasad, kreatora warunków i dziennika audytu. Zawiera style dla elementów formularzy, tabel i niestandardowych komponentów interfejsu użytkownika.
-   `conorderservices/views/css/front.css`
    -   **Zakres:** Front-office
    -   **Szczegóły:** Style dla sposobu wyświetlania opcjonalnych usług na stronie realizacji zamówienia. Zawiera style dla bloku usług, poszczególnych wierszy usług, pól wyboru, cen i ikon. Deweloperzy mogą nadpisać te klasy w pliku `custom.css` lub `theme.css` swojego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `conorderservices/views/templates/hook/admin_order.tpl`
    -   **Hook:** `displayAdminOrder`
    -   **Wyjście:** Wyświetla informacje o wybranych opcjonalnych usługach w widoku zamówienia w Panelu administracyjnym PrestaShop. Pozwala administratorom zobaczyć, które usługi zostały zakupione wraz z zamówieniem.
-   `conorderservices/views/templates/hook/checkout_services.tpl`
    -   **Hook:** `displayShoppingCart`, `displayShoppingCartFooter` (lub podobne hooki realizacji zamówienia)
    -   **Wyjście:** Główny szablon do renderowania listy dostępnych opcjonalnych usług na stronie realizacji zamówienia w front-office. Iteruje przez kwalifikujące się zasady i wyświetla je.
-   `conorderservices/views/templates/hook/partials/checkout_offer_row.tpl`
    -   **Hook:** Dołączony przez `checkout_services.tpl`
    -   **Wyjście:** Renderuje pojedynczy wiersz lub kartę dla opcjonalnej usługi na liście realizacji zamówienia, w tym jej nazwę, opis, cenę i pole wyboru (np. checkbox).

#### Szablony administracyjne (`views/templates/admin/`)

-   `conorderservices/views/templates/admin/auditPreview.tpl`
    -   **Cel:** Renderuje szczegółowy widok lub podgląd wpisu dziennika audytu.
-   `conorderservices/views/templates/admin/dashboard.tpl`
    -   **Cel:** Główny szablon dla pulpitu nawigacyjnego modułu w Back Office, potencjalnie wyświetlający analizy lub podsumowanie informacji.
-   `conorderservices/views/templates/admin/helpers/list/list_action_duplicate.tpl`
    -   **Cel:** Niestandardowy szablon dla przycisku akcji „Duplikuj” w widokach `HelperList` (specyficznie dla zasad).
-   `conorderservices/views/templates/admin/policiesPreview.tpl`
    -   **Cel:** Renderuje podgląd zasady, potencjalnie używany w symulatorze lub szybkim podglądzie.
-   `conorderservices/views/templates/admin/policyConditionBuilder.tpl`
    -   **Cel:** Szablon dla wizualnego interfejsu kreatora warunków w formularzu edycji zasad. Jest to złożony szablon, który dynamicznie dodaje/usuwa grupy warunków i pojedyncze warunki.
-   `conorderservices/views/templates/admin/policyRuleCard.tpl`
    -   **Cel:** Renderuje pojedynczą regułę lub grupę warunków jako kartę w kreatorze warunków, czyniąc ją wizualnie odrębną.
-   `conorderservices/views/templates/admin/policyRulesTable.tpl`
    -   **Cel:** Renderuje strukturę tabelaryczną do wyświetlania reguł, być może alternatywę lub komponent w kreatorze warunków.
-   `conorderservices/views/templates/admin/scopeSelector.tpl`
    -   **Cel:** Szablon do wyboru zakresu warunku (np. produkt, kategoria, klient).

#### Szablony bibliotek (`conorderservices/lib/searchTool/views/`)

-   `conorderservices/lib/searchTool/views/helpers.tpl`
    -   **Cel:** Szablony pomocnicze dla narzędzia wyszukiwania, być może do renderowania wyników wyszukiwania lub pól wejściowych.
-   `conorderservices/lib/searchTool/views/scripts.tpl`
    -   **Cel:** Zawiera JavaScript dla narzędzia wyszukiwania.
-   `conorderservices/lib/searchTool/views/views/scripts.tpl`
    -   **Cel:** Duplikat lub specyficzna wersja skryptów narzędzia wyszukiwania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_conorderservices_policy`
    -   Przechowuje podstawowe informacje o zasadach: `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd`.
    -   Zawiera również pola specyficzne dla języka dla `name` i `description` (np. `ps_conorderservices_policy_lang`).
-   `ps_conorderservices_condition_group`
    -   Przechowuje grupy warunków: `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR).
-   `ps_conorderservices_condition`
    -   Przechowuje pojedyncze warunki: `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`.
-   `ps_conorderservices_log`
    -   Przechowuje wpisy dziennika audytu: `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`.
-   `ps_conorderservices_cart_state` (prawdopodobnie)
    -   Przechowuje, które usługi są wybrane dla danego koszyka: `id_cart`, `id_conorderservices_policy`, `date_add`.
-   `ps_configuration`
    -   `CONORDERSERVICES_ENABLED`: Przechowuje główny status włączenia/wyłączenia modułu.
    -   `PS_CURRENCY_DEFAULT`: Używane do wyświetlania cen w panelu administracyjnym.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `ActionObjectProductInCartDeleteBefore` | Przed usunięciem produktu z koszyka. | Zapewnia, że jeśli produkt wymagany do usługi zostanie usunięty, usługa również zostanie usunięta lub ponownie oceniona. |
| `actionPresentCart` | Gdy dane koszyka są prezentowane (np. na stronie realizacji zamówienia). | Wstrzykuje listę kwalifikujących się opcjonalnych usług do danych prezentacji koszyka. |
| `ActionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany i jego media (JS/CSS) są ustawiane. | Wstrzykuje JS i CSS specyficzne dla modułu dla stron Back Office (zasady, dziennik audytu, kreator warunków). |
| `ActionPresentProductListing` | Gdy dane produktu są prezentowane na liście (np. strona kategorii). | Potencjalnie używane do wyświetlania wskaźników dostępności usług na listach produktów. |
| `ActionValidateOrderBefore` | Przed walidacją zamówienia. | Wykonuje ostateczne sprawdzenia wybranych usług, zapewnia ich ważność i dodaje je jako szczegóły zamówienia. |
| `ActionGetProductPropertiesAfter` | Po pobraniu właściwości produktu. | Potencjalnie modyfikuje właściwości produktu, jeśli usługa na nie wpływa (np. dodanie wirtualnego produktu dla usługi). |
| `DisplayAdminOrder` | Na stronie szczegółów zamówienia w Back Office. | Wyświetla wybrane opcjonalne usługi powiązane z zamówieniem. |
| `ActionFrontControllerInitAfter` | Po zainicjowaniu kontrolera front-office. | Inicjuje kontekst lub logikę front-office specyficzną dla modułu. |
| `ActionPresentProduct` | Gdy dane pojedynczego produktu są prezentowane (np. strona produktu). | Potencjalnie używane do wyświetlania wskaźników dostępności usług na stronach produktów. |
| `ActionPresentCartProduct` | Gdy produkt w koszyku jest prezentowany. | Modyfikuje prezentację produktów w koszyku, jeśli są do nich dołączone usługi. |
| `ActionProductPriceCalculation` | Podczas obliczania ceny produktu. | Zapewnia, że ceny usług są poprawnie uwzględniane w sumie. |
| `DisplayShoppingCart` | Na stronie koszyka. | Wyświetla blok opcjonalnych usług. |
| `DisplayShoppingCartFooter` | W stopce strony koszyka. | Alternatywne lub dodatkowe umiejscowienie bloku opcjonalnych usług. |
| `ActionCartSave` | Po zapisaniu koszyka. | Utrwala stan wybranych opcjonalnych usług w koszyku. |
| `ActionValidateOrder` | Po walidacji zamówienia. | Finalizuje zamówienie z wybranymi usługami, potencjalnie aktualizując stan magazynowy lub wyzwalając działania następcze. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Warunkowe Opcjonalne Usługi Zamówienia”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
