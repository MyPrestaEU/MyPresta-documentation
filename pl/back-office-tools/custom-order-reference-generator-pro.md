---
title: "Custom Order Reference Generator Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Custom Order Reference Generator Pro od MyPresta.eu."
sidebar:
  label: "Custom Order Reference Generator Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Custom Order Reference Generator Pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/custom-order-reference-generator-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/custom-order-reference-generator-pro/)
>
> ---


# Custom Order Reference Generator Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Custom Order Reference Generator Pro)

Jest to główny ekran konfiguracji, na którym definiujesz niestandardowe wzorce i reguły referencji zamówień. Strona jest zazwyczaj zorganizowana w kilka zakładek lub sekcji dla przejrzystości.

#### **Zakładka Ustawienia ogólne**

Ta zakładka kontroluje podstawowe zachowanie modułu.

- **Włącz generowanie niestandardowych referencji zamówień:**

  - **Co robi to ustawienie:** Jest to główny przełącznik modułu. Po włączeniu moduł przejmie generowanie referencji zamówień. Po wyłączeniu PrestaShop powróci do domyślnej metody generowania referencji zamówień.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Wszystkie nowe zamówienia otrzymają referencję wygenerowaną przez ten moduł zgodnie z Twoimi zdefiniowanymi regułami.
    - *Po wyłączeniu:* Wszystkie nowe zamówienia będą używać domyślnego formatu referencji PrestaShop. Istniejące zamówienia zachowają swoje referencje.
  - **Zalecana wartość:** TAK (aby aktywować funkcjonalność modułu).
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz zacząć używać niestandardowych referencji, włącz to. Jeśli musisz tymczasowo wrócić do domyślnych ustawień PrestaShop w celu rozwiązywania problemów, wyłącz to.
- **Domyślny wzorzec referencji:**

  - **Co robi to ustawienie:** Definiuje podstawową strukturę dla Twoich niestandardowych referencji zamówień. Możesz łączyć statyczny tekst z dynamicznymi „shortcode'ami”, które pobierają informacje z zamówienia, klienta lub daty.
  - **Efekt zmiany tego ustawienia:** Bezpośrednio dyktuje format Twoich referencji zamówień, gdy nie ma zastosowania żadna konkretna reguła.
  - **Zalecana wartość:** Zacznij od czegoś prostego, np. `MYSTORE-{DATE:YMD}-{ID_ORDER}` lub `ORD-{RAND:6}`.
  - **Scenariusz/przykład dla sprzedawcy:**
    - `MYSTORE-{DATE:YMD}-{ID_ORDER}`: Generuje referencje takie jak `MYSTORE-20231027-12345`. Jest to świetne do łatwego identyfikowania zamówień z Twojego sklepu i widzenia daty ich złożenia, wraz z sekwencyjnym ID zamówienia.
    - `ORD-{RAND:6}`: Generuje referencje takie jak `ORD-A1B2C3`. Zapewnia to krótką, losową i unikalną referencję.
    - `{CUSTOMER_LASTNAME}-{ID_ORDER}`: Generuje referencje takie jak `SMITH-12345`. Przydatne dla B2B lub spersonalizowanej obsługi.
  - **Dostępne shortcode'y:**
    - `{ID_ORDER}`: Unikalne ID zamówienia (sekwencyjne).
    - `{ID_CUSTOMER}`: Unikalne ID klienta.
    - `{DATE:format}`: Aktualna data i godzina. `format` używa składni funkcji PHP `date()` (np. `YMD` dla 20231027, `His` dla 143059).
    - `{RAND:length}`: Losowy ciąg znaków alfanumerycznych, `length` określa liczbę znaków (np. `RAND:6`).
    - `{CUSTOMER_FIRSTNAME}`: Imię klienta.
    - `{CUSTOMER_LASTNAME}`: Nazwisko klienta.
    - `{CUSTOMER_EMAIL}`: Adres e-mail klienta.
    - `{PAYMENT_METHOD}`: Metoda płatności użyta do zamówienia.
    - `{DELIVERY_COUNTRY_ISO}`: Kod ISO kraju dostawy (np. US, FR).
    - `{DELIVERY_CITY}`: Miasto adresu dostawy.
    - `{CART_TOTAL}`: Całkowita wartość koszyka.
    - `{PRODUCT_SKU}`: SKU pierwszego produktu w koszyku (używać ostrożnie, może być długie).
    - `{PRODUCT_NAME}`: Nazwa pierwszego produktu w koszyku (używać ostrożnie).
    - `{SHOP_NAME}`: Nazwa Twojego sklepu PrestaShop.
- **Wartość początkowa licznika sekwencyjnego:**

  - **Co robi to ustawienie:** Jeśli Twój wzorzec referencji zawiera `{ID_ORDER}` lub podobny element sekwencyjny, to definiuje początkowy numer dla tej sekwencji.
  - **Efekt zmiany tego ustawienia:** Nowe zamówienia rozpoczną swoją sekwencyjną numerację od tej wartości. Jest to przydatne, jeśli migrujesz z innego systemu lub chcesz ponownie rozpocząć numerację.
  - **Zalecana wartość:** 1 (dla nowego startu) lub wyższa liczba, jeśli musisz kontynuować sekwencję.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli wcześniej miałeś 1000 zamówień i chcesz, aby Twoje nowe niestandardowe referencje zaczynały się od 1001, ustaw to na 1001.
- **Limit długości referencji:**

  - **Co robi to ustawienie:** PrestaShop ma domyślny limit długości referencji zamówienia. Pozwala to zdefiniować maksymalną długość dla generowanych referencji. Jeśli referencja przekroczy tę długość, zostanie obcięta.
  - **Efekt zmiany tego ustawienia:** Zapewnia, że Twoje referencje mieszczą się w ograniczeniach bazy danych i wyświetlają się poprawnie we wszystkich obszarach PrestaShop.
  - **Zalecana wartość:** 9 (domyślna wartość PrestaShop to często 9, ale możesz ją zwiększyć, jeśli Twój motyw/baza danych to obsługuje, do 32 znaków jest ogólnie bezpieczne).
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój wzorzec `MYSTORE-{DATE:YMD}-{ID_ORDER}` daje `MYSTORE-20231027-12345` (21 znaków), a ustawisz limit na 9, może to stać się `MYSTORE-2`. Pamiętaj o obcinaniu.
- **Podgląd referencji:**

  - **Co robi to ustawienie:** Jest to pole narzędziowe, które pozwala przetestować Twój `Domyślny wzorzec referencji` z fikcyjnym ID zamówienia, aby zobaczyć, jak wyglądałaby wygenerowana referencja.
  - **Efekt zmiany tego ustawienia:** Brak bezpośredniego wpływu na Twój sklep, wyłącznie narzędzie testowe.
  - **Zalecana wartość:** Używaj często podczas projektowania swoich wzorców.
  - **Scenariusz/przykład dla sprzedawcy:** Wprowadź `12345` jako fikcyjne ID zamówienia i kliknij „Generuj podgląd”, aby zobaczyć, jak wyglądałoby `MYSTORE-{DATE:YMD}-{ID_ORDER}`.

#### **Zakładka Reguły**

Ta zakładka służy do definiowania konkretnych warunków, w których powinny być stosowane różne wzorce referencji zamówień, zastępując wzorzec domyślny. Reguły są przetwarzane od góry do dołu, a pierwsza pasująca reguła jest stosowana.

- **Dodaj nową regułę / Edytuj regułę:**

  - **Co to robi:** Pozwala utworzyć nową regułę lub zmodyfikować istniejącą. Każda reguła składa się z:
    - **Nazwa reguły:** Opisowa nazwa dla Twojej wewnętrznej referencji (np. „Zamówienia o wysokiej wartości”, „Klienci francuscy”).
    - **Wzorzec reguły:** Niestandardowy wzorzec referencji do użycia, jeśli ta reguła pasuje (te same shortcode'y co wzorzec domyślny).
    - **Warunki:** Jedno lub więcej kryteriów, które muszą być spełnione, aby ta reguła została zastosowana.
  - **Efekt zmiany tego ustawienia:** Dodaje lub modyfikuje warunkowy wzorzec referencji.
  - **Zalecana wartość:** Twórz reguły dla najważniejszych segmentów Twojej działalności.
  - **Scenariusz/przykład dla sprzedawcy:**
    - **Reguła 1: Zamówienia o wysokiej wartości**
      - **Wzorzec:** `VIP-{ID_ORDER}-{DATE:YMD}`
      - **Warunek:** `Całkowita wartość koszyka` jest `większa niż` `500`
      - **Efekt:** Każde zamówienie powyżej 500 € otrzyma referencję taką jak `VIP-12345-20231027`.
    - **Reguła 2: Klienci francuscy**
      - **Wzorzec:** `FR-{ID_ORDER}`
      - **Warunek:** `Kraj dostawy` to `Francja`
      - **Efekt:** Zamówienia wysyłane do Francji otrzymają `FR-12345`.
    - **Reguła 3: Zamówienia na konkretny produkt**
      - **Wzorzec:** `PROD-XYZ-{ID_ORDER}`
      - **Warunek:** `Produkt w koszyku` to `Nazwa produktu XYZ`
      - **Efekt:** Zamówienia zawierające „Nazwa produktu XYZ” otrzymają `PROD-XYZ-12345`.
- **Warunki reguły (dla każdej reguły):**

  - **Co to robi:** Definiuje kryteria, aby reguła była aktywna. Możesz łączyć wiele warunków za pomocą logiki „AND”.
  - **Dostępne warunki:**
    - **Całkowita wartość koszyka:** Na podstawie całkowitej wartości zamówienia.
    - **Grupa klientów:** Na podstawie grupy, do której należy klient (np. Odwiedzający, Klienci, Goście lub niestandardowe grupy).
    - **Kraj dostawy:** Na podstawie kraju adresu wysyłki.
    - **Metoda płatności:** Na podstawie użytego modułu płatności (np. Przelew bankowy, PayPal).
    - **Produkt w koszyku:** Na podstawie tego, czy konkretny produkt (według ID lub nazwy) jest obecny w zamówieniu.
    - **Przewoźnik:** Na podstawie wybranego przewoźnika.
  - **Efekt zmiany tego ustawienia:** Określa, kiedy używany jest konkretny niestandardowy wzorzec referencji.
  - **Zalecana wartość:** Używaj warunków, które jasno segmentują Twoje zamówienia.
  - **Scenariusz/przykład dla sprzedawcy:** Reguła dla „Klientów hurtowych” może używać `Grupa klientów to Hurtowi`. Reguła dla „Wysyłki ekspresowej” może używać `Przewoźnik to DHL Express`.

#### **Zakładka Ustawienia zaawansowane**

Ta zakładka zawiera ustawienia dotyczące bardziej technicznych aspektów i konserwacji.

- **Kopia zapasowa / Przywracanie JSON:**

  - **Co to robi:** Pozwala wyeksportować konfigurację modułu (wzorce, reguły) do pliku JSON lub zaimportować wcześniej zapisaną konfigurację.
  - **Efekt zmiany tego ustawienia:**
    - *Kopia zapasowa:* Tworzy plik do pobrania z Twoimi ustawieniami.
    - *Przywracanie:* Nadpisuje bieżące ustawienia tymi z przesłanego pliku JSON.
  - **Zalecana wartość:** Zawsze twórz kopię zapasową swojej konfiguracji przed wprowadzeniem poważnych zmian lub aktualizacją sklepu PrestaShop.
  - **Scenariusz/przykład dla sprzedawcy:** Przed aktualizacją PrestaShop lub przeniesieniem sklepu na nowy serwer, pobierz kopię zapasową swoich niestandardowych reguł referencji. Jeśli popełnisz błąd w regule, możesz łatwo przywrócić poprzednią wersję.
- **Resetuj konfigurację modułu:**

  - **Co to robi:** Usuwa wszystkie niestandardowe wzorce i reguły, przywracając moduł do jego domyślnego, świeżo zainstalowanego stanu.
  - **Efekt zmiany tego ustawienia:** Wszystkie Twoje niestandardowe wzorce i reguły referencji zostaną utracone.
  - **Zalecana wartość:** Używaj z najwyższą ostrożnością, tylko jeśli chcesz całkowicie zacząć od nowa.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje reguły stały się zbyt skomplikowane lub powodują problemy i chcesz zacząć od zera, możesz to wykorzystać. Zawsze najpierw wykonaj kopię zapasową!

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Ustawienia ogólne** | Włącz generowanie niestandardowych referencji zamówień | TAK | Aktywuje/dezaktywuje logikę niestandardowych referencji modułu. |
|  | Domyślny wzorzec referencji | `ORD-{RAND:6}` (przykład) | Definiuje awaryjny format referencji, gdy żadne reguły nie pasują. |
|  | Wartość początkowa licznika sekwencyjnego | 1 | Ustawia początkowy numer dla `{ID_ORDER}` w nowych referencjach. |
|  | Limit długości referencji | 9 (lub więcej, jeśli bezpieczne) | Ogranicza maksymalną długość generowanych referencji, aby zapobiec problemom. |
|  | Podgląd referencji | (N/A) | Narzędzie do testowania wzorca z fikcyjnym ID zamówienia. |
| **Zakładka Reguły** | Dodaj/Edytuj regułę | N/A | Twórz warunkowe wzorce referencji na podstawie kryteriów. |
|  | Nazwa reguły | Opisowa (np. „Zamówienia o wysokiej wartości”) | Wewnętrzna etykieta dla reguły. |
|  | Wzorzec reguły | Niestandardowy (np. `VIP-{ID_ORDER}`) | Format referencji dla tej konkretnej reguły. |
|  | Warunki reguły | Różne (np. `Całkowita wartość koszyka > 500`) | Kryteria, które muszą być spełnione, aby reguła została zastosowana. |
| **Ustawienia zaawansowane** | Kopia zapasowa / Przywracanie JSON | N/A | Eksport/import konfiguracji modułu dla bezpieczeństwa lub migracji. |
|  | Resetuj konfigurację modułu | N/A | Usuwa wszystkie ustawienia i reguły modułu. Używać z najwyższą ostrożnością. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje niestandardowe referencje nie wyświetlają się lub nadal widzę domyślne referencje PrestaShop.**
O1: Najpierw upewnij się, że moduł jest **włączony** w zakładce „Ustawienia ogólne”. Sprawdź również, czy wyczyściłeś pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Jeśli masz konkretne reguły, upewnij się, że ich warunki są spełnione i że reguły są poprawnie uporządkowane (stosowana jest pierwsza pasująca reguła).

**P2: Moje niestandardowe referencje są za długie lub są obcinane.**
O2: Sprawdź „Limit długości referencji” w zakładce „Ustawienia ogólne”. PrestaShop ma domyślny limit (często 9 znaków) dla referencji zamówień w swojej bazie danych. Jeśli Twój niestandardowy wzorzec generuje dłuższe referencje, może być konieczne zwiększenie tego limitu. Bądź ostrożny, ponieważ zbyt duże zwiększenie może spowodować problemy z wyświetlaniem w niektórych motywach lub starszych wersjach PrestaShop. Ogólnie bezpieczne jest zwiększenie do 32 znaków. Jeśli potrzebujesz dłuższych, skonsultuj się z programistą.

**P3: Popełniłem błąd w moich regułach i teraz moje referencje są błędne. Jak to naprawić?**
O3: Jeśli masz aktualną kopię zapasową JSON (z zakładki „Ustawienia zaawansowane”), możesz ją przywrócić. W przeciwnym razie będziesz musiał ręcznie edytować lub usunąć problematyczne reguły. Jeśli chcesz zacząć całkowicie od nowa, użyj opcji „Resetuj konfigurację modułu”, ale pamiętaj, że spowoduje to usunięcie *wszystkich* Twoich niestandardowych wzorców i reguł.

**P4: Czy mogę używać tego modułu z wieloma sklepami (konfiguracja multistore)?**
O4: Tak, moduł jest zaprojektowany tak, aby był kompatybilny z funkcją multistore PrestaShop. Możesz skonfigurować różne wzorce i reguły referencji dla każdego sklepu ze strony konfiguracji modułu, wybierając konkretny kontekst sklepu w panelu administracyjnym PrestaShop.

**P5: Co dzieje się z istniejącymi zamówieniami, gdy zmieniam wzorzec referencji?**
O5: Zmiana wzorca referencji lub reguł wpływa tylko na *nowe* zamówienia złożone po zmianie. Istniejące zamówienia zachowają swoje oryginalne referencje zamówień. Moduł nie modyfikuje wstecznie danych poprzednich zamówień.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Custom Order Reference Generator Pro” rozszerza głównie podstawową klasę `Order` PrestaShop poprzez nadpisanie, aby przechwycić i zmodyfikować proces generowania referencji zamówienia. Przyjmuje podejście oparte na zdarzeniach, gdzie moduł włącza się w cykl życia tworzenia zamówienia. Konfiguracja jest zarządzana za pomocą standardowej metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration` i niestandardowe reguły we własnych tabelach bazy danych (chociaż nie wymieniono żadnych konkretnych plików SQL, oznacza to dynamiczne tworzenie tabel lub przechowywanie konfiguracji). Moduł wykorzystuje `RulesEngine` do oceny warunków i `ReferenceGenerator` do konstruowania ostatecznej referencji na podstawie zdefiniowanych wzorców i shortcode'ów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wydaje się używać niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `refchangepro/classes/PayloadFactory.php`

  - **Nazwa klasy:** `PayloadFactory`
  - **Klasa nadrzędna:** Brak (prawdopodobnie klasa narzędziowa)
  - **Odpowiedzialność:** Odpowiedzialna za tworzenie ładunku danych (kontekstu), którego mogą używać `RulesEngine` i `ReferenceGenerator`. Ten ładunek zawierałby informacje o aktualnie przetwarzanym zamówieniu (np. całkowita wartość koszyka, ID klienta, kraj dostawy, produkty). Działa jako warstwa abstrakcji do zbierania wszystkich niezbędnych danych do oceny reguł i generowania referencji.
- `refchangepro/classes/ReferenceContext.php`

  - **Nazwa klasy:** `ReferenceContext`
  - **Klasa nadrzędna:** Brak (prawdopodobnie obiekt transferu danych lub obiekt wartości)
  - **Odpowiedzialność:** Prosta klasa do przechowywania i zarządzania danymi kontekstowymi (np. ID zamówienia, dane klienta, dane koszyka), które są przekazywane podczas procesu generowania referencji. Zapewnia spójność dostępu do danych dla generatora i silnika reguł.
- `refchangepro/classes/ReferenceGenerator.php`

  - **Nazwa klasy:** `ReferenceGenerator`
  - **Klasa nadrzędna:** Brak (prawdopodobnie klasa usługowa)
  - **Odpowiedzialność:** Główna logika do konstruowania ostatecznego ciągu referencji zamówienia. Przyjmuje wzorzec (np. `MYSTORE-{DATE:YMD}-{ID_ORDER}`) i obiekt `ReferenceContext`, a następnie zastępuje shortcode'y rzeczywistymi wartościami. Obsługuje formatowanie daty, generowanie losowych ciągów znaków i wstawianie sekwencyjnych ID.
- `refchangepro/classes/RulesEngine.php`

  - **Nazwa klasy:** `RulesEngine`
  - **Klasa nadrzędna:** Brak (prawdopodobnie klasa usługowa)
  - **Odpowiedzialność:** Ocenia zdefiniowane reguły względem bieżącego kontekstu zamówienia. Iteruje przez skonfigurowane reguły, sprawdza, czy warunki (np. całkowita wartość koszyka, grupa klientów, kraj) są spełnione i zwraca wzorzec pierwszej pasującej reguły. Jeśli żadne reguły nie pasują, wskazuje, że należy użyć wzorca domyślnego.
- `refchangepro/classes/Runtime.php`

  - **Nazwa klasy:** `Runtime`
  - **Klasa nadrzędna:** Brak (prawdopodobnie klasa narzędziowa lub pomocnicza)
  - **Odpowiedzialność:** Może obsługiwać konfiguracje środowiska uruchomieniowego, buforowanie lub inne aspekty operacyjne modułu. Może być odpowiedzialna za ładowanie reguł z konfiguracji, zarządzanie licznikiem sekwencyjnym lub dostarczanie metod narzędziowych używanych w całym module.
- `refchangepro/override/classes/order/Order.php`

  - **Dokładna ścieżka pliku:** `refchangepro/override/classes/order/Order.php`
  - **Nazwa klasy:** `Order`
  - **Klasa nadrzędna:** `OrderCore` (podstawowa klasa Order PrestaShop)
  - **Odpowiedzialność:** Jest to krytyczne nadpisanie. Przechwytuje metodę `generateReference()` (lub podobną metodę odpowiedzialną za ustawianie referencji zamówienia) w podstawowej klasie `Order` PrestaShop. Wewnątrz tej nadpisanej metody wywołuje `RulesEngine` modułu, aby określić prawidłowy wzorzec, a następnie `ReferenceGenerator`, aby utworzyć niestandardową referencję, ostatecznie ustawiając ją dla obiektu zamówienia. Zapewnia to, że każde nowe zamówienie utworzone używa logiki modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

- `refchangepro/lib/searchTool/views/js/autocomplete.js`

  - **Zakres:** Prawdopodobnie Panel administracyjny.
  - **Opis:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wybierania produktów, klientów lub innych encji podczas definiowania reguł. Wiązałoby się to z polami wejściowymi, wykonywaniem żądań AJAX do kontrolera administracyjnego PrestaShop (lub metody `getContent` modułu) i wyświetlaniem sugestii.
- `refchangepro/views/js/admin-tabs.js`

  - **Zakres:** Panel administracyjny.
  - **Opis:** Zarządza interfejsem z zakładkami na stronie konfiguracji modułu. Wiąże zdarzenia kliknięcia z nagłówkami zakładek, pokazuje/ukrywa odpowiednią zawartość zakładek i może obsługiwać zmiany hasha URL dla bezpośredniego linkowania do zakładek.
- `refchangepro/views/js/rules-builder.js`

  - **Zakres:** Panel administracyjny.
  - **Opis:** Jest to podstawowy JavaScript dla zakładki „Reguły”. Obsługuje dynamiczne dodawanie, edytowanie i usuwanie warunków reguł. Wiąże zdarzenia z przyciskami „Dodaj warunek”, zarządza rozwijanymi listami dla typów warunków (np. „Całkowita wartość koszyka”, „Grupa klientów”) i dynamicznie renderuje pola wejściowe na podstawie wybranego typu warunku (np. pole numeryczne dla całkowitej wartości koszyka, pole wyboru dla grup klientów). Prawdopodobnie serializuje dane reguły do ukrytego pola wejściowego w celu przesłania.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `refchangepro/lib/searchTool/views/css/autocomplete.css`

  - **Zakres:** Stylizacja panelu administracyjnego.
  - **Opis:** Stylizuje listy sugestii autouzupełniania i pola wejściowe, zapewniając ich wizualną spójność i łatwość użytkowania w panelu administracyjnym PrestaShop.
- `refchangepro/views/css/admin.css`

  - **Zakres:** Stylizacja panelu administracyjnego.
  - **Opis:** Zapewnia ogólną stylizację strony konfiguracji modułu, w tym układ, typografię, style przycisków i ogólną prezentację wizualną, aby bezproblemowo zintegrować się z motywem panelu administracyjnego PrestaShop.
- `refchangepro/views/css/rules-builder.css`

  - **Zakres:** Stylizacja panelu administracyjnego.
  - **Opis:** Specyficzne style dla interfejsu konstruktora reguł, w tym układu poszczególnych bloków reguł, wierszy warunków oraz wszelkich elementów do przeciągania i upuszczania lub zmiany kolejności.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- `refchangepro/lib/searchTool/views/scripts.tpl`
  - **Zakres:** Panel administracyjny.
  - **Opis:** Ten szablon prawdopodobnie zawiera niezbędny JavaScript i potencjalnie CSS dla narzędzia wyszukiwania autouzupełniania. Zostałby on dołączony do głównego szablonu konfiguracji modułu w celu załadowania funkcjonalności autouzupełniania.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Opis modułu wspomina: „Inteligentne reguły stosują różne wzorce według wartości koszyka, kraju, produktu lub grupy klientów”. To silnie sugeruje utworzenie niestandardowych tabel bazy danych do przechowywania tych reguł i związanych z nimi warunków.
  - Oczekiwane tabele (nazwy są ilustracyjne, rzeczywiste nazwy byłyby poprzedzone `ps_` i nazwą modułu):
    - `ps_refchangepro_rules`: Przechowuje główne definicje reguł (ID, nazwa, wzorzec, status aktywności).
    - `ps_refchangepro_conditions`: Przechowuje poszczególne warunki dla każdej reguły (ID reguły, typ warunku, operator, wartość).
  - Ustawienia konfiguracji (takie jak `PS_REFCHANGEPRO_ENABLED`, `PS_REFCHANGEPRO_DEFAULT_PATTERN`, `PS_REFCHANGEPRO_COUNTER_START`) są przechowywane w tabeli `ps_configuration` PrestaShop.
  - Licznik sekwencyjny dla `{ID_ORDER}` może być przechowywany w `ps_configuration` lub w dedykowanej tabeli dla bardziej solidnego blokowania.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionOrderAdd` / `actionObjectOrderAddAfter` | Po utworzeniu nowego obiektu zamówienia w bazie danych. | Nadpisanie metody `Order::generateReference()` modułu jest głównym mechanizmem. Jednakże, jeśli moduł musi wykonać dodatkowe działania *po* pełnym zapisaniu zamówienia z jego nową referencją, te hooki zostałyby użyte. Na przykład, aby zarejestrować wygenerowaną referencję lub zaktualizować niestandardowy licznik. |
| `displayBackOfficeHeader` | W sekcji `<head>` Panelu administracyjnego. | Używane do ładowania specyficznych dla modułu CSS (`admin.css`, `rules-builder.css`, `autocomplete.css`) i JavaScript (`admin-tabs.js`, `rules-builder.js`, `autocomplete.js`) dla strony konfiguracji. |
| `displayAdminProductsExtra` / `displayAdminCustomers` (Hipoteza) | Na stronach edycji produktów lub klientów w Panelu administracyjnym. | Gdyby moduł miał oferować specyficzne ustawienia referencji dla każdego produktu lub klienta, włączyłby się tutaj, aby wyświetlić te opcje. (Nie jest to wyraźnie stwierdzone, ale jest to powszechne w wersjach „Pro”). |
| `displayModuleConfigure` (Wewnętrzny) | Po załadowaniu strony konfiguracji modułu. | Metoda `getContent()` głównego pliku modułu jest tutaj niejawnie włączona, aby renderować formularz konfiguracji. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszych informacji dotyczących modułu „Custom Order Reference Generator Pro”, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich pytań lub problemów.
