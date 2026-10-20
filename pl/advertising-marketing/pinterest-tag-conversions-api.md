---
title: "Pinterest Tag & Conversions API - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Pinterest Tag & Conversions API od MyPresta.eu."
sidebar:
  label: "Pinterest Tag & Conversions API - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Pinterest Tag & Conversions API na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/pinterest-tag-conversions-api.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/pinterest-tag-conversions-api/)
>
> ---


# Pinterest Tag & Conversions API

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twój serwer musi być w stanie wykonywać wychodzące żądania HTTP do punktów końcowych API Pinterest.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główne centrum do ustawiania śledzenia Pinterest. Znajdziesz różne sekcje i zakładki do zarządzania Pinterest Tag, Conversions API i jakością danych.

#### Ustawienia ogólne i tryb śledzenia

- **Identyfikator Pinterest Tag (wymagane)**

  - **Co robi to ustawienie:** Jest to Twój unikalny identyfikator dostarczony przez Pinterest. Informuje Pinterest, do którego konta reklamowego należą dane z Twojej witryny.
  - **Efekt zmiany tego ustawienia:**
    - *Po wprowadzeniu:* Umożliwia modułowi wysyłanie danych do Twojego konta reklamowego Pinterest. Bez niego śledzenie nie może nastąpić.
    - *Gdy puste:* Moduł nie może wysyłać żadnych danych do Pinterest.
  - **Zalecana wartość:** Twój identyfikator Pinterest Tag. Możesz go znaleźć w Menedżerze reklam Pinterest w sekcji „Reklamy” > „Konwersje” > „Pinterest Tag”.
  - **Scenariusz / przykład dla sprzedawcy:** Właśnie utworzyłeś konto reklamowe Pinterest i musisz połączyć z nim swój sklep. Skopiuj identyfikator Tag z Pinterest i wklej go tutaj.
- **Tryb śledzenia**

  - **Co robi to ustawienie:** Określa, w jaki sposób Twój sklep wysyła dane do Pinterest. Możesz wybrać między tradycyjnym Pinterest Tag (po stronie przeglądarki), bardziej niezawodnym Conversions API (po stronie serwera) lub kombinacją obu.
  - **Efekt zmiany tego ustawienia:**
    - *Pinterest Tag (po stronie przeglądarki):* Dane są wysyłane bezpośrednio z przeglądarki klienta. Jest to prostsze, ale może być podatne na blokery reklam lub ustawienia prywatności przeglądarki.
    - *Conversions API (po stronie serwera):* Dane są wysyłane bezpośrednio z Twojego serwera PrestaShop do Pinterest. Jest to bardziej niezawodne i mniej podatne na blokowanie, oferując lepszą dokładność danych.
    - *Oba (hybrydowe z deduplikacją):* Dane są wysyłane obiema metodami. Moduł automatycznie dodaje unikalny `event_id` do każdego zdarzenia, umożliwiając Pinterest identyfikację i ignorowanie zduplikowanych zdarzeń, zapewniając maksymalne pokrycie danych bez nadmiernego zliczania.
  - **Zalecana wartość:** **Oba (hybrydowe z deduplikacją)** dla najbardziej niezawodnego i kompleksowego śledzenia.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Twoje kampanie Pinterest są jak najdokładniejsze, nawet przy rosnących środkach ochrony prywatności. Wybór „Oba” zapewnia najlepsze z obu światów.

#### Ustawienia Conversions API (CAPI) (widoczne, jeśli wybrano tryb CAPI lub Oba)

- **Token dostępu do Conversions API (wymagane dla CAPI)**

  - **Co robi to ustawienie:** Jest to bezpieczny token, który uwierzytelnia Twój serwer podczas wysyłania danych bezpośrednio do Conversions API Pinterest. Jest to jak hasło dla Twojego serwera do komunikacji z Pinterest.
  - **Efekt zmiany tego ustawienia:**
    - *Po wprowadzeniu:* Umożliwia Twojemu serwerowi wysyłanie danych za pośrednictwem Conversions API.
    - *Gdy puste:* Śledzenie Conversions API nie będzie działać, nawet jeśli wybrano je jako tryb śledzenia.
  - **Zalecana wartość:** Twój token dostępu do Conversions API Pinterest. Wygeneruj go w Menedżerze reklam Pinterest w sekcji „Reklamy” > „Konwersje” > „Conversions API”.
  - **Scenariusz / przykład dla sprzedawcy:** Zdecydowałeś się użyć Conversions API dla bardziej niezawodnego śledzenia. Wygenerujesz ten token w Pinterest i wkleisz go tutaj.
- **Włącz rozszerzone dopasowanie dla CAPI**

  - **Co robi to ustawienie:** Po włączeniu moduł wysyła dodatkowe informacje o kliencie (takie jak e-mail, numer telefonu, imię, adres – wszystkie zahaszowane dla prywatności) wraz ze zdarzeniami Conversions API. Pomaga to Pinterest dokładniej dopasowywać zdarzenia do konkretnych użytkowników, nawet jeśli nie są zalogowani na Pinterest.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Poprawia dokładność dopasowywania zdarzeń na Pinterest, co prowadzi do lepszego targetowania odbiorców i optymalizacji kampanii.
    - *Po wyłączeniu:* Wysyłane są tylko podstawowe dane zdarzeń, co potencjalnie zmniejsza dokładność dopasowania.
  - **Zalecana wartość:** **TAK**. To znacząco poprawia jakość danych i wydajność reklam.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Pinterest może dokładnie przypisać sprzedaż do Twoich reklam, nawet jeśli klienci używają różnych urządzeń lub przeglądarek. Rozszerzone dopasowanie pomaga wypełnić te luki.

#### Prywatność danych i zgoda

- **Integracja z modułem zgody na pliki cookie**
  - **Co robi to ustawienie:** Jeśli używasz oddzielnego modułu zgody na pliki cookie (np. modułu zgodności z RODO), włączenie tej opcji zapewnia, że śledzenie Pinterest uruchamia się tylko po wyrażeniu zgody przez klienta.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Śledzenie Pinterest będzie respektować wybory klienta dotyczące zgody z Twojego modułu plików cookie. Jeśli zgoda zostanie odrzucona, żadne dane Pinterest nie zostaną wysłane.
    - *Po wyłączeniu:* Śledzenie Pinterest będzie uruchamiane niezależnie od innych ustawień zgody na pliki cookie, co potencjalnie prowadzi do problemów z zgodnością.
  - **Zalecana wartość:** **TAK**, jeśli używasz modułu zgody na pliki cookie. **NIE**, jeśli nie używasz go lub obsługujesz zgodę ręcznie.
  - **Scenariusz / przykład dla sprzedawcy:** Twój sklep musi być zgodny z RODO. Włączając tę opcję, zapewniasz, że śledzenie Pinterest jest zgodne z preferencjami prywatności Twoich klientów.

#### Ustawienia zaawansowane i debugowanie

- **Włącz tryb debugowania**

  - **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla szczegółowe informacje o wysyłanych zdarzeniach Pinterest bezpośrednio w konsoli programisty Twojej przeglądarki. Jest to przydatne do weryfikacji, czy Twoje śledzenie działa poprawnie.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Programiści i webmasterzy mogą zobaczyć dane zdarzeń Pinterest w czasie rzeczywistym w konsoli przeglądarki. Nigdy nie należy włączać tej opcji w działającym sklepie produkcyjnym do ogólnego wglądu publicznego.
    - *Po wyłączeniu:* Nie są wyświetlane żadne informacje debugowania.
  - **Zalecana wartość:** **NIE** dla działającego sklepu produkcyjnego. **TAK** tylko podczas konfiguracji i testowania.
  - **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz potwierdzić, że zdarzenia „Dodaj do koszyka” są uruchamiane poprawnie. Włączasz tryb debugowania, dodajesz produkt do koszyka i sprawdzasz konsolę przeglądarki pod kątem danych zdarzeń.
- **Domeny łączące (do śledzenia między domenami)**

  - **Co robi to ustawienie:** Jeśli Twój sklep używa wielu subdomen lub przekierowuje do innej domeny podczas procesu realizacji zamówienia (np. oddzielna domena bramki płatności), możesz wymienić te domeny tutaj. Pomaga to Pinterest poprawnie przypisywać działania między różnymi domenami.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy domeny są wymienione:* Pinterest może utrzymać ciągłość śledzenia między tymi domenami, zapobiegając utracie danych.
    - *Gdy puste:* Śledzenie może zostać przerwane, jeśli klienci nawigują między różnymi domenami podczas swojej podróży, co prowadzi do niekompletnych danych.
  - **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzne potrzeby śledzenia między domenami. Jeśli tak, wprowadź każdą domenę w nowej linii.
  - **Scenariusz / przykład dla sprzedawcy:** Twój główny sklep to `shop.example.com`, ale Twój blog to `blog.example.com` i chcesz śledzić użytkowników, którzy odwiedzają oba. Dodałbyś `blog.example.com` tutaj.

#### Jakość danych i ocena kondycji (sekcje informacyjne)

Te sekcje dostarczają wglądu w Twoją konfigurację śledzenia i nie są bezpośrednimi ustawieniami konfiguracji, ale raczej raportami generowanymi przez moduł.

- **Ocena kondycji**: Pokazuje ogólną ocenę wskazującą jakość i kompletność konfiguracji śledzenia Pinterest. Wyższa ocena oznacza bardziej niezawodne dane.
- **Doktor katalogu**: Pomaga zidentyfikować potencjalne problemy z danymi katalogu produktów, które mogą wpływać na zdolność Pinterest do dopasowywania produktów do reklam dynamicznych.
- **Trener jakości danych**: Dostarcza rekomendacje i ostrzeżenia dotyczące danych zdarzeń, takie jak brakujące parametry lub nieprawidłowe formatowanie, aby pomóc Ci poprawić dokładność.
- **Statystyki na żywo**: Wyświetla ostatnie zdarzenia wysłane do Pinterest, umożliwiając monitorowanie aktywności w czasie rzeczywistym.
- **Ostatnie zdarzenia**: Dziennik najnowszych zdarzeń przetworzonych przez moduł.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminMypinterestAjaxController (Panel administracyjny > Moduły > Pinterest Tag & Conversions API > Statystyki na żywo / Ocena kondycji / Trener jakości danych)

Ten kontroler zasila dynamiczne, interaktywne sekcje na głównej stronie konfiguracji modułu, w szczególności dla funkcji takich jak Statystyki na żywo, Ocena kondycji i Trener jakości danych.

- **Nazwa ekranu i lokalizacja w menu:** Nie są to samodzielne elementy menu, ale raczej interaktywne panele na głównej stronie konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj „Pinterest Tag & Conversions API”).
- **Dostępne działania i ustawienia:** Ten kontroler obsługuje żądania AJAX w celu pobierania i wyświetlania danych i raportów w czasie rzeczywistym.
  - **Statystyki na żywo**: Pokazuje strumień zdarzeń w czasie rzeczywistym (np. PageView, AddToCart, Purchase) w miarę ich wysyłania do Pinterest, w tym, czy zostały wysłane za pośrednictwem Tag, CAPI, czy obu. Pozwala to szybko zweryfikować, czy zdarzenia są uruchamiane.
  - **Ocena kondycji**: Wyświetla podsumowanie kondycji Twojej konfiguracji śledzenia, podkreślając obszary do poprawy (np. brakujący token CAPI, niska jakość dopasowania zdarzeń).
  - **Trener jakości danych**: Oferuje konkretne rekomendacje dotyczące poprawy jakości danych wysyłanych do Pinterest, takie jak zapewnienie, że wszystkie wymagane parametry są uwzględnione dla każdego typu zdarzenia.
  - **Doktor katalogu**: Analizuje Twój kanał katalogu produktów (jeśli używasz go dla Pinterest) i wskazuje potencjalne problemy, które mogą utrudniać dynamiczne reklamy produktów.
- **Efekt zmian:** Interakcja z tymi panelami (np. odświeżanie Statystyk na żywo) wyzwala wywołania AJAX, które pobierają najnowsze dane z Twojego serwera lub API Pinterest, dostarczając aktualnych informacji bez przeładowywania całej strony.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj Ocenę kondycji i Trenera jakości danych, aby upewnić się, że Twoje śledzenie pozostaje optymalne. Używaj Statystyk na żywo podczas testowania lub po wprowadzeniu zmian, aby zweryfikować, czy zdarzenia są uruchamiane poprawnie.

#### 2.2.2 index.php (mypinterest/controllers/admin/index.php)

Ten plik jest plikiem zastępczym i zazwyczaj służy jako środek bezpieczeństwa, aby zapobiec bezpośredniemu listowaniu katalogów w folderach administracyjnych PrestaShop. Nie reprezentuje on konfigurowalnego ekranu ani zarządzanej jednostki.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator Pinterest Tag | Twój identyfikator Tag | Łączy Twój sklep z Twoim kontem reklamowym Pinterest do śledzenia. |
| Konfiguracja modułu | Tryb śledzenia | Oba (hybrydowy) | Wysyła dane za pośrednictwem przeglądarki (Tag) i serwera (CAPI) dla maksymalnej niezawodności. |
| Konfiguracja modułu | Token dostępu do Conversions API | Twój token CAPI | Uwierzytelnia wysyłanie danych po stronie serwera do Pinterest. |
| Konfiguracja modułu | Włącz rozszerzone dopasowanie dla CAPI | TAK | Poprawia dokładność dopasowania zdarzeń na Pinterest dla lepszego targetowania. |
| Konfiguracja modułu | Integracja z modułem zgody na pliki cookie | TAK (jeśli dotyczy) | Zapewnia, że śledzenie Pinterest respektuje wybory klienta dotyczące prywatności. |
| Konfiguracja modułu | Włącz tryb debugowania | NIE (w działającym sklepie) | Pokazuje szczegółowe informacje o śledzeniu w konsoli przeglądarki do testowania. |
| Konfiguracja modułu | Domeny łączące | Puste (chyba że potrzebne) | Utrzymuje ciągłość śledzenia między wieloma powiązanymi domenami. |
| Panel Statystyk na żywo | N/A | N/A | Wyświetla zdarzenia Pinterest w czasie rzeczywistym do weryfikacji. |
| Panel Oceny kondycji | N/A | N/A | Dostarcza ogólną ocenę jakości konfiguracji śledzenia. |
| Panel Trenera jakości danych | N/A | N/A | Oferuje rekomendacje dotyczące poprawy dokładności danych zdarzeń. |
| Panel Doktora katalogu | N/A | N/A | Identyfikuje problemy w Twoim katalogu produktów dla reklam Pinterest. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zainstalowałem moduł, ale nie widzę żadnych danych w Menedżerze reklam Pinterest. Co powinienem zrobić?**
O1: Najpierw dokładnie sprawdź, czy Twój **Identyfikator Pinterest Tag** i **Token dostępu do Conversions API** (jeśli używasz CAPI) są poprawnie wprowadzone w konfiguracji modułu. Upewnij się, że nie ma literówek. Następnie wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Następnie odwiedź front office swojego sklepu i wykonaj kilka działań (przeglądaj produkt, dodaj do koszyka, dokonaj testowego zakupu). Jeśli masz włączony „Tryb debugowania” w module, sprawdź konsolę programisty swojej przeglądarki pod kątem zdarzeń Pinterest. Jeśli nadal nie ma danych, zweryfikuj konfigurację Menedżera reklam Pinterest i upewnij się, że Twoje konto jest aktywne.

**P2: Mój Pinterest Tag wydaje się być blokowany przez blokery reklam. Jak mogę zapewnić, że moje dane są nadal zbierane?**
O2: Właśnie dlatego Conversions API (CAPI) jest tak ważne! Upewnij się, że Twój „Tryb śledzenia” jest ustawiony na **„Oba (hybrydowe z deduplikacją)”**. W ten sposób, nawet jeśli Pinterest Tag po stronie przeglądarki zostanie zablokowany, Twój serwer PrestaShop nadal będzie wysyłał dane zdarzeń bezpośrednio do Pinterest za pośrednictwem Conversions API, zapewniając, że Twoje śledzenie pozostaje niezawodne.

**P3: Jak ten moduł radzi sobie z prywatnością klientów i RODO/CCPA?**
O3: Moduł zawiera opcję **„Integracja z modułem zgody na pliki cookie”**. Jeśli masz zainstalowany oddzielny moduł zgody na pliki cookie (co jest wysoce zalecane dla zgodności z prywatnością), włącz to ustawienie. Śledzenie Pinterest zostanie wtedy aktywowane dopiero po wyrażeniu zgody przez klienta za pośrednictwem Twojego istniejącego rozwiązania zgody. Moduł również haszuje wrażliwe dane klienta przed wysłaniem ich za pośrednictwem rozszerzonego dopasowania dla CAPI, dodając kolejną warstwę prywatności.

**P4: Widzę niską „Ocenę kondycji” lub ostrzeżenia w „Trenerze jakości danych”. Co to oznacza?**
O4: Te sekcje mają na celu pomóc Ci zoptymalizować śledzenie. Niska Ocena kondycji lub ostrzeżenia zazwyczaj wskazują, że niektóre parametry danych mogą być brakujące lub nieprawidłowo sformatowane, lub że Twoja konfiguracja nie jest w pełni zoptymalizowana (np. CAPI nie jest włączone). Przejrzyj konkretne rekomendacje zawarte w panelach „Trener jakości danych” i „Doktor katalogu”. Poprowadzą Cię one, jak poprawić jakość danych, co bezpośrednio wpływa na skuteczność Twoich reklam na Pinterest.

**P5: Czy ten moduł spowolni moją stronę internetową?**
O5: Moduł został zaprojektowany tak, aby był wysoce zoptymalizowany. Pinterest Tag po stronie przeglądarki jest ładowany asynchronicznie, co oznacza, że nie blokuje ładowania strony. Wywołania Conversions API po stronie serwera odbywają się w tle i nie wpływają na czas ładowania strony front office. Nie powinieneś doświadczyć żadnych zauważalnych spowolnień z powodu tego modułu.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Pinterest Tag & Conversions API` (`mypinterest`) implementuje hybrydową strategię śledzenia dla Pinterest, łącząc tradycyjny Pinterest Tag po stronie przeglądarki z Conversions API (CAPI) po stronie serwera. W miarę możliwości stosuje wzorzec MVC PrestaShop, wykorzystując hooki do wstrzykiwania zdarzeń do front office oraz dedykowane kontrolery administracyjne do konfiguracji i raportowania danych. Kluczowe komponenty architektoniczne obejmują:

- **Fabryka trackerów**: Dynamicznie tworzy instancję odpowiedniego mechanizmu śledzenia (Tag, CAPI lub hybrydowy) na podstawie konfiguracji modułu.
- **Mapowanie zdarzeń**: Tłumaczy wewnętrzne zdarzenia PrestaShop (np. `actionCartSave`, `actionValidateOrder`) na standardowe nazwy zdarzeń i parametry Pinterest.
- **Narzędzia do jakości danych**: Dedykowane klasy do oceny kondycji, diagnostyki katalogu i coachingu jakości danych, dostarczające praktycznych informacji w panelu administracyjnym.
- **Zarządzanie zgodami**: Integracja z modułami zgody na pliki cookie innych firm w celu zapewnienia zgodności z RODO/CCPA.
- **Statystyki na żywo**: Monitorowanie zdarzeń w czasie rzeczywistym za pośrednictwem AJAX do debugowania i weryfikacji.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

- `controllers/front/ajax.php`
  - **Nazwa klasy i klasa nadrzędna**: `MypinterestAjaxModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność**: Obsługuje żądania AJAX z front office, głównie do wysyłania zdarzeń po stronie serwera (CAPI), które są wyzwalane przez działania po stronie klienta, ale muszą być przetwarzane bezpiecznie na serwerze. Może to obejmować zdarzenia, które są trudne do śledzenia wyłącznie po stronie klienta lub do celów deduplikacji. Prawdopodobnie odbiera dane zdarzeń z `mypinterest.js` i przekazuje je do klienta CAPI.
- `controllers/front/cron.php`
  - **Nazwa klasy i klasa nadrzędna**: `MypinterestCronModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność**: Udostępnia punkt końcowy dla zadania cron. Może być używany do zadań takich jak wysyłanie odroczonych zdarzeń CAPI, synchronizacja katalogów produktów lub przeprowadzanie okresowych kontroli jakości danych bez bezpośredniej interakcji użytkownika.
- `controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna**: `MypinterestIndexModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność**: Kontroler frontowy zastępczy, zazwyczaj używany do zapobiegania bezpośredniemu listowaniu katalogów lub jako rezerwowy dla tras specyficznych dla modułu, które nie pasują do innych kontrolerów. W tym module prawdopodobnie pełni minimalną rolę lub przekierowuje.

#### Kontrolery administracyjne Back Office

- `controllers/admin/AdminMypinterestAjaxController.php`
  - **Nazwa klasy i klasa nadrzędna**: `AdminMypinterestAjaxController` rozszerza `ModuleAdminController`.
  - **Nazwa zakładki i zarządzana jednostka**: Ten kontroler nie jest bezpośrednio eksponowany jako zakładka menu, ale służy jako punkt końcowy AJAX dla strony konfiguracji modułu. Obsługuje żądania dotyczące dynamicznych danych wyświetlanych w panelach „Statystyki na żywo”, „Ocena kondycji”, „Trener jakości danych” i „Doktor katalogu” na głównej stronie konfiguracji modułu. Pobiera dzienniki zdarzeń w czasie rzeczywistym, metryki kondycji i raporty diagnostyczne.
- `controllers/admin/index.php`
  - **Nazwa klasy i klasa nadrzędna**: Nie jest kontrolerem funkcjonalnym.
  - **Nazwa zakładki i zarządzana jednostka**: Jest to zabezpieczenie, zapobiegające listowaniu katalogów.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `classes/autoload.php`: Standardowy plik autoload PrestaShop, zapewniający prawidłowe ładowanie klas modułu.
- `classes/MypinterestCapiClient.php`:
  - **Tabela bazy danych**: Brak bezpośrednio.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Obsługuje rzeczywiste żądania HTTP do punktu końcowego Conversions API Pinterest. Hermetyzuje logikę budowania ładunków CAPI, w tym danych zdarzeń, danych użytkownika i tokenów dostępu.
- `classes/MypinterestCapiTracker.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Implementuje `MypinterestTrackerInterface`.
  - **Kluczowe metody publiczne**: Zarządza logiką śledzenia zdarzeń specjalnie za pośrednictwem Conversions API. Formatuje dane dla CAPI, obsługuje deduplikację zdarzeń (`event_id`) i deleguje wysyłanie do `MypinterestCapiClient`.
- `classes/MypinterestCatalogDoctor.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Zawiera logikę do analizy danych produktów (np. z kanałów produktów lub obiektów `Product`) i identyfikowania potencjalnych problemów, które mogą wpływać na zdolność Pinterest do dopasowywania produktów do reklam dynamicznych. Dostarcza raporty diagnostyczne.
- `classes/MypinterestConsent.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Zarządza integracją z modułami zgody na pliki cookie innych firm. Sprawdza status zgody użytkownika i określa, czy śledzenie Pinterest powinno być włączone lub wyłączone na podstawie zgody.
- `classes/MypinterestCurrencyHelper.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Klasa narzędziowa do obsługi formatowania i konwersji walut, zapewniająca, że zdarzenia Pinterest wysyłają wartości walut w prawidłowym formacie.
- `classes/MypinterestDataQualityCoach.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Analizuje jakość wysyłanych danych zdarzeń (np. obecność wymaganych parametrów, prawidłowe typy danych) i dostarcza rekomendacje dotyczące poprawy.
- `classes/MypinterestEventId.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Generuje i zarządza unikalnymi wartościami `event_id` do deduplikacji zdarzeń, kluczowymi dla śledzenia hybrydowego.
- `classes/MypinterestEventMap.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Definiuje mapowanie między działaniami/danymi PrestaShop a standardowymi nazwami zdarzeń Pinterest oraz ich wymaganymi/zalecanymi parametrami.
- `classes/MypinterestEvents.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Centralizuje logikę wyzwalania i zarządzania różnymi zdarzeniami Pinterest (PageView, AddToCart, Purchase itp.) w całym module.
- `classes/MypinterestHealthScore.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Oblicza ogólną „ocenę kondycji” konfiguracji śledzenia Pinterest na podstawie różnych czynników, takich jak obecność tokena CAPI, tryb śledzenia i jakość danych.
- `classes/MypinterestHybridTracker.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Implementuje `MypinterestTrackerInterface`.
  - **Kluczowe metody publiczne**: Koordynuje śledzenie, gdy wybrany jest tryb „Oba”. Wywołuje zarówno `MypinterestTagTracker`, jak i `MypinterestCapiTracker`, zapewniając spójność `event_id` dla deduplikacji.
- `classes/MypinterestLiveStats.php`:
  - **Tabela bazy danych**: Przechowuje ostatnie dzienniki zdarzeń (np. w `ps_configuration` lub niestandardowej tabeli).
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Rejestruje i pobiera ostatnie zdarzenia Pinterest do wyświetlenia w panelu „Statystyki na żywo” w panelu administracyjnym.
- `classes/MypinterestProductIdResolver.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Pomaga rozwiązywać i formatować identyfikatory produktów, aby pasowały do wymagań katalogu Pinterest, zapewniając dokładne dopasowanie produktów do reklam dynamicznych.
- `classes/MypinterestPropertyRules.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Definiuje reguły i walidacje dla właściwości zdarzeń Pinterest, zapewniając, że dane wysyłane do Pinterest są zgodne z ich specyfikacjami.
- `classes/MypinterestTagTracker.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Implementuje `MypinterestTrackerInterface`.
  - **Kluczowe metody publiczne**: Zarządza logiką wstrzykiwania skryptu Pinterest Tag po stronie przeglądarki i wyzwalania zdarzeń za pośrednictwem wywołań `pintrk()`.
- `classes/MypinterestTrackerFactory.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Klasa wzorca fabryki odpowiedzialna za tworzenie i zwracanie prawidłowej instancji trackera (`MypinterestTagTracker`, `MypinterestCapiTracker` lub `MypinterestHybridTracker`) na podstawie konfiguracji modułu.
- `classes/MypinterestTrackerInterface.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Definiuje wspólny interfejs dla wszystkich trackerów Pinterest, zapewniając spójność w obsłudze zdarzeń niezależnie od podstawowej metody śledzenia.
- `classes/MypinterestUserData.php`:
  - **Tabela bazy danych**: Brak.
  - **Rozszerza**: Brak `ObjectModel`.
  - **Kluczowe metody publiczne**: Gromadzi i formatuje dane klienta (e-mail, telefon, adres itp.) dla „Rozszerzonego dopasowania”, zapewniając, że są one zahaszowane i zgodne z wymaganiami Pinterest.

### 4.4 Zasoby JavaScript (`views/js/`)

- `mypinterest/views/js/mypinterest-admin.js`:
  - **Zakres**: Panel administracyjny.
  - **Opis**: Zawiera JavaScript dla interfejsu administracyjnego modułu. Obsługuje wywołania AJAX do `AdminMypinterestAjaxController` w celu pobierania statystyk na żywo, ocen kondycji i innych dynamicznych treści. Zarządza interakcjami interfejsu użytkownika na stronie konfiguracji.
- `mypinterest/views/js/mypinterest-debug.js`:
  - **Zakres**: Front office.
  - **Opis**: Ładowany, gdy włączony jest „Tryb debugowania”. Zapewnia logowanie do konsoli i wizualne nakładki do wyświetlania danych zdarzeń Pinterest w miarę ich wysyłania, pomagając w rozwiązywaniu problemów i weryfikacji.
- `mypinterest/views/js/mypinterest-ghost.js`:
  - **Zakres**: Front office.
  - **Opis**: Potencjalnie związane z „duchowym” lub odroczonym śledzeniem, lub mechanizmem awaryjnym dla zdarzeń, które mogą nie uruchomić się natychmiast. Może być używany do określonych typów zdarzeń lub opóźnień związanych ze zgodą.
- `mypinterest/views/js/mypinterest-live.js`:
  - **Zakres**: Panel administracyjny.
  - **Opis**: Specjalnie dla panelu „Statystyki na żywo”. Zarządza aktualizacją dzienników zdarzeń w czasie rzeczywistym, odpytując serwer za pośrednictwem AJAX w celu wyświetlania ostatnich zdarzeń Pinterest.
- `mypinterest/views/js/mypinterest-tcf.js`:
  - **Zakres**: Front office.
  - **Opis**: Obsługuje integrację z modułami zgody na pliki cookie zgodnymi z Transparency and Consent Framework (TCF). Nasłuchuje zdarzeń zgody i odpowiednio włącza/wyłącza śledzenie Pinterest.
- `mypinterest/views/js/mypinterest-wizard.js`:
  - **Zakres**: Panel administracyjny.
  - **Opis**: Zasila funkcjonalność kreatora konfiguracji w konfiguracji modułu. Prowadzi sprzedawcę przez początkowe kroki konfiguracji, walidując dane wejściowe i dostarczając informacji zwrotnych.
- `mypinterest/views/js/mypinterest.js`:
  - **Zakres**: Front office.
  - **Opis**: Główny JavaScript front office dla Pinterest Tag. Wstrzykuje bibliotekę `pintrk()`, inicjalizuje Pinterest Tag z identyfikatorem Tag i wyzwala standardowe zdarzenia (PageView, AddToCart, Checkout, Purchase) na podstawie zdarzeń DOM lub hooków JavaScript PrestaShop. Odpowiada również za generowanie `event_id` do deduplikacji i potencjalnie wysyłanie wywołań AJAX do `controllers/front/ajax.php` dla zdarzeń CAPI.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `mypinterest/views/css/mypinterest-admin.css`:
  - **Zakres**: Stylizacja formularza administracyjnego Back Office.
  - **Opis**: Style dla strony konfiguracji modułu, w tym układ zakładek, pól wejściowych, przycisków i dynamicznych paneli dla Statystyk na żywo, Oceny kondycji itp.
  - **Kluczowe selektory klas CSS**: `.mypinterest-config`, `.mypinterest-tab-content`, `.mypinterest-health-score`, `.mypinterest-live-stats`.
- `mypinterest/views/css/mypinterest-debug.css`:
  - **Zakres**: Stylizacja klienta Front Office (tylko gdy tryb debugowania jest aktywny).
  - **Opis**: Zapewnia stylizację dla nakładki debugowania lub danych wyjściowych konsoli, czyniąc informacje debugowania bardziej czytelnymi dla programistów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

- `mypinterest/views/templates/hook/capi-pageview.tpl`:
  - **Hook**: Prawdopodobnie `displayHeader` lub `displayFooter`.
  - **Wynik**: Renderuje ukryty element lub mały skrypt do wyzwolenia zdarzenia PageView po stronie serwera za pośrednictwem CAPI, często używanego do początkowego śledzenia ładowania strony lub jako rezerwowy.
- `mypinterest/views/templates/hook/debug.tpl`:
  - **Hook**: `displayHeader` lub `displayFooter` (renderowane warunkowo).
  - **Wynik**: Wstrzykuje skrypt `mypinterest-debug.js` i potencjalnie strukturę HTML nakładki debugowania, gdy tryb debugowania jest aktywny.
- `mypinterest/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook**: `displayOrderConfirmation`.
  - **Wynik**: Renderuje skrypt zdarzenia „Zakup” Pinterest, w tym szczegóły zamówienia (wartość, waluta, identyfikator zamówienia, produkty) zarówno dla Pinterest Tag, jak i CAPI (za pośrednictwem wywołania AJAX).
- `mypinterest/views/templates/hook/ghost.tpl`:
  - **Hook**: `displayHeader` lub `displayFooter`.
  - **Wynik**: Potencjalnie związane ze skryptem `mypinterest-ghost.js`, używanym do specyficznych, być może odroczonych lub działających w tle, mechanizmów śledzenia.
- `mypinterest/views/templates/hook/header.tpl`:
  - **Hook**: `displayHeader`.
  - **Wynik**: Wstrzykuje główny kod bazowy Pinterest Tag (`pintrk()`) i skrypt `mypinterest.js`. Inicjalizuje Pinterest Tag z identyfikatorem Tag i potencjalnie wyzwala początkowe zdarzenie „PageView”.
- `mypinterest/views/templates/hook/payment.tpl`:
  - **Hook**: `displayPayment` lub `displayPaymentTop`.
  - **Wynik**: Może być używany do śledzenia rozpoczęcia procesu realizacji zamówienia lub wyboru metody płatności, potencjalnie wyzwalając zdarzenie „Checkout” lub „InitiateCheckout”.
- `mypinterest/views/templates/hook/product-details.tpl`:
  - **Hook**: `displayProductButtons` lub `displayFooterProduct`.
  - **Wynik**: Renderuje JavaScript do śledzenia zdarzeń „ViewContent” po załadowaniu strony produktu, w tym identyfikatora produktu, nazwy, ceny i kategorii. Prawdopodobnie zawiera również logikę dla zdarzeń „Dodaj do koszyka”.

#### Szablony administracyjne (`views/templates/admin/`)

- `mypinterest/views/templates/admin/consent-guide.tpl`: Wyświetla informacje i wskazówki dotyczące integracji z modułami zgody na pliki cookie.
- `mypinterest/views/templates/admin/doctor.tpl`: Renderuje panel „Doktor katalogu”, pokazując diagnostykę danych katalogu produktów.
- `mypinterest/views/templates/admin/dq.tpl`: Renderuje panel „Trener jakości danych”, dostarczając rekomendacji dotyczących poprawy danych zdarzeń.
- `mypinterest/views/templates/admin/health.tpl`: Renderuje panel „Ocena kondycji”, wyświetlając ogólną kondycję śledzenia.
- `mypinterest/views/templates/admin/linker-domains.tpl`: Szablon dla pola wejściowego „Domeny łączące”.
- `mypinterest/views/templates/admin/live-maintain.tpl`: Prawdopodobnie komunikat o konserwacji lub statusie funkcji statystyk na żywo.
- `mypinterest/views/templates/admin/live.tpl`: Renderuje panel „Statystyki na żywo”, wyświetlając dzienniki zdarzeń w czasie rzeczywistym.
- `mypinterest/views/templates/admin/mode-context.tpl`: Dostarcza informacji kontekstowych o wybranym trybie śledzenia.
- `mypinterest/views/templates/admin/mode-note-both.tpl`: Specyficzna uwaga/wyjaśnienie dla trybu śledzenia „Oba (hybrydowe)”.
- `mypinterest/views/templates/admin/mode-note-capi.tpl`: Specyficzna uwaga/wyjaśnienie dla trybu śledzenia „Conversions API”.
- `mypinterest/views/templates/admin/mode-note-tag.tpl`: Specyficzna uwaga/wyjaśnienie dla trybu śledzenia „Pinterest Tag”.
- `mypinterest/views/templates/admin/mode-picker.tpl`: Renderuje przyciski radiowe lub listę rozwijaną do wyboru „Trybu śledzenia”.
- `mypinterest/views/templates/admin/properties-list.tpl`: Wyświetla listę właściwości zdarzeń i ich status (np. wymagane, zalecane).
- `mypinterest/views/templates/admin/recent-events.tpl`: Renderuje tabelę lub listę ostatnich zdarzeń dla panelu „Statystyki na żywo”.
- `mypinterest/views/templates/admin/tabs.tpl`: Renderuje strukturę nawigacji po zakładkach dla strony konfiguracji modułu.
- `mypinterest/views/templates/admin/tag-chips.tpl`: Prawdopodobnie do wyświetlania identyfikatorów Pinterest Tag w atrakcyjnym wizualnie formacie „chipów”.
- `mypinterest/views/templates/admin/tag-ids.tpl`: Renderuje pola wejściowe dla identyfikatora Pinterest Tag i tokena dostępu CAPI.
- `mypinterest/views/templates/admin/wizard.tpl`: Renderuje interfejs kreatora konfiguracji krok po kroku.

#### Szablony Front Office (`views/templates/front/`)

- `mypinterest/views/templates/front/index.tpl`: Szablon zastępczy, prawdopodobnie nie używany do bezpośredniego renderowania, ale jako domyślny dla `MypinterestIndexModuleFrontController`.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł używa głównie `ps_configuration` do przechowywania swoich ustawień (np. `MYPINTEREST_TAG_ID`, `MYPINTEREST_TRACKING_MODE`, `MYPINTEREST_CAPI_TOKEN`).
  - Może również używać niestandardowej tabeli (np. `ps_mypinterest_events_log`) do przechowywania ostatnich danych zdarzeń dla funkcji „Statystyki na żywo”, chociaż można to również przechowywać w `ps_configuration` jako dane serializowane. (Nie znaleziono jawnych plików SQL, więc prawdopodobnie `ps_configuration` lub dynamiczne tworzenie tabel).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje podstawowy JavaScript Pinterest Tag, `mypinterest.js` i potencjalnie początkowe zdarzenia PageView. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Wyzwala zdarzenie „Zakup”, wysyłając szczegółowe dane zamówienia i produktu do Pinterest. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku „Dodaj do koszyka”. | Wstrzykuje JavaScript do śledzenia zdarzeń „ViewContent” i „Dodaj do koszyka”. |
| `displayFooter` | Na końcu sekcji `<body>` każdej strony. | Może być używany jako alternatywna lub dodatkowa lokalizacja do wstrzykiwania skryptów, zwłaszcza dla zdarzeń, które nie muszą blokować renderowania strony. |
| `actionCartSave` | Gdy koszyk jest aktualizowany (np. produkt dodany/usunięty). | Wyzwala zdarzenia „AddToCart” lub „RemoveFromCart”, często obsługiwane po stronie serwera za pośrednictwem CAPI lub po stronie klienta za pośrednictwem AJAX. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Wyzwala zdarzenie „Zakup” po stronie serwera za pośrednictwem CAPI dla maksymalnej niezawodności, uzupełniając zdarzenie `displayOrderConfirmation` po stronie klienta. |
| `actionFrontControllerSetMedia` | Gdy kontroler frontowy ustawia swoje media (JS/CSS). | Umożliwia modułowi rejestrowanie plików JavaScript i CSS front office. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje media (JS/CSS). | Umożliwia modułowi rejestrowanie plików JavaScript i CSS back office. |
| `actionObjectProductUpdateAfter` / `actionObjectProductAddAfter` | Po zaktualizowaniu lub dodaniu produktu. | Potencjalnie używane do aktualizacji danych katalogu produktów lub wyzwalania diagnostyki katalogu. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Potencjalnie używane do aktualizacji danych katalogu produktów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Pinterest Tag & Conversions API, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
