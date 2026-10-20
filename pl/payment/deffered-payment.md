---
title: "Płatność odroczona - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop Płatność odroczona od MyPresta.eu."
sidebar:
  label: "Płatność odroczona - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Deffered Payment na MyPresta.eu](https://mypresta.eu/modules/payment-process/deffered-payment.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/deffered-payment/)
>
> ---


# Płatność odroczona

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i ogólnie wystarczające dla tego modułu. Nie są potrzebne żadne nietypowe rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Płatność odroczona)

Jest to główny ekran konfiguracji, na którym definiujesz podstawowe zachowanie modułu Płatność odroczona.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Płatność odroczona” > Kliknij „Konfiguruj”

#### Ustawienia ogólne

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Włącz płatność odroczoną** | TAK | **Co robi to ustawienie:** Jest to główny przełącznik modułu.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Opcja Płatność odroczona będzie dostępna przy kasie dla uprawnionych klientów.   *Gdy wyłączone:* Opcja Płatność odroczona będzie ukryta przed wszystkimi klientami, niezależnie od innych ustawień.   **Zalecana wartość:** TAK (aby używać modułu).   **Scenariusz sprzedawcy:** Włącz to, gdy będziesz gotowy do oferowania tej metody płatności. |
| **Dozwolone grupy klientów** | (Wybierz odpowiednie grupy) | **Co robi to ustawienie:** Określa, które grupy klientów mogą widzieć i używać opcji Płatność odroczona.   **Efekt zmiany tego ustawienia:**   *Gdy wybrane:* Tylko klienci należący do wybranych grup zobaczą Płatność odroczoną przy kasie.   *Gdy niewybrane:* Klienci w niewybranych grupach nie zobaczą tej opcji.   **Zalecana wartość:** Wybierz konkretne grupy (np. „Hurtownicy”, „Klienci VIP”). Unikaj „Wszyscy klienci”, chyba że zamierzasz oferować płatność odroczoną wszystkim.   **Scenariusz sprzedawcy:** Masz grupę „Klienci B2B”. Wybierz tylko tę grupę, aby tylko Twoi klienci biznesowi mogli korzystać z płatności odroczonej. |
| **Dni na płatność** | 30 | **Co robi to ustawienie:** Definiuje liczbę dni po złożeniu zamówienia, w ciągu których płatność jest należna.   **Efekt zmiany tego ustawienia:** Ta wartość zostanie użyta do obliczenia terminu płatności wyświetlanego klientowi oraz do wewnętrznego śledzenia.   **Zalecana wartość:** 30 (typowe dla warunków net-30), 7, 14, 60 itd., w zależności od polityki Twojej firmy.   **Scenariusz sprzedawcy:** Ustaw na 30 dla warunków płatności „Net 30”. |
| **Minimalna kwota zamówienia dla płatności odroczonej** | 0.00 | **Co robi to ustawienie:** Ustawia minimalną wartość zamówienia (w Twojej domyślnej walucie), którą zamówienie musi spełnić, aby kwalifikować się do płatności odroczonej.   **Efekt zmiany tego ustawienia:**   *Jeśli suma zamówienia jest poniżej tej wartości:* Płatność odroczona nie będzie dostępna, nawet dla uprawnionych grup klientów.   *Jeśli suma zamówienia jest powyżej lub równa tej wartości:* Płatność odroczona będzie dostępna (jeśli spełnione są inne warunki).   **Zalecana wartość:** 0.00 (brak minimum) lub konkretna wartość (np. 100.00 dla B2B).   **Scenariusz sprzedawcy:** Chcesz oferować płatność odroczoną tylko dla dużych zamówień, więc ustawiasz ją na 500.00. |
| **Status zamówienia dla płatności odroczonej** | Oczekuje na płatność odroczoną | **Co robi to ustawienie:** Określa początkowy status zamówienia, który zostanie przypisany do zamówień złożonych metodą Płatność odroczona.   **Efekt zmiany tego ustawienia:** Ten status będzie widoczny na liście zamówień w Twoim Panelu administracyjnym oraz dla klienta w jego historii zamówień. Pomaga szybko identyfikować zamówienia oczekujące na płatność.   **Zalecana wartość:** Utwórz konkretny status, taki jak „Oczekuje na płatność odroczoną” lub „Płatność należna” w **Statusach zamówień** (Panel administracyjny > Parametry sklepu > Ustawienia zamówień > Statusy) i wybierz go tutaj.   **Scenariusz sprzedawcy:** Chcesz mieć jasny status, aby odróżnić te zamówienia od „Oczekuje na przelew bankowy” lub „Płatność zaakceptowana”. |
| **URL zadania Cron** | (Wyświetlany URL) | **Co robi to ustawienie:** Ten URL służy do wyzwalania zautomatyzowanych zadań związanych z płatnościami odroczonymi (np. sprawdzanie terminów płatności, wysyłanie przypomnień, jeśli takie funkcje są zaimplementowane lub rozszerzone).   **Efekt zmiany tego ustawienia:** Jest to pole tylko do odczytu. Powinieneś skonfigurować zadanie cron na swoim serwerze, aby regularnie odwiedzało ten URL (np. raz dziennie).   **Zalecana wartość:** Skopiuj ten URL i dodaj go do harmonogramu zadań cron na swoim serwerze.   **Scenariusz sprzedawcy:** Chcesz zautomatyzować wszelkie procesy w tle, które moduł może mieć, takie jak aktualizacja statusów zamówień lub wysyłanie powiadomień. |

#### Produkty docelowe (Kwalifikacja konkretnych produktów)

Ta sekcja pozwala ograniczyć płatność odroczoną do konkretnych produktów lub kategorii.

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Zastosuj tylko do konkretnych produktów** | NIE | **Co robi to ustawienie:** Określa, czy opcja płatności odroczonej jest ograniczona do zamówień zawierających tylko konkretne produkty.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Opcja „Płatność odroczona” pojawi się przy kasie tylko wtedy, gdy *wszystkie* produkty w koszyku znajdują się na Twojej zatwierdzonej liście.   *Gdy wyłączone:* Moduł będzie stosowany na podstawie grup klientów i minimalnej kwoty zamówienia, niezależnie od konkretnych produktów.   **Zalecana wartość:** NIE (do ogólnego użytku) lub TAK (dla bardzo specyficznych scenariuszy).   **Scenariusz sprzedawcy:** Oferujesz płatność odroczoną tylko dla swoich wysokowartościowych produktów „Usługi Premium”. Włączasz to i dodajesz te produkty poniżej. |
| **Produkty dozwolone dla płatności odroczonej** | (Puste) | **Co robi to ustawienie:** Jeśli „Zastosuj tylko do konkretnych produktów” jest włączone, to pole pozwala wyszukiwać i dodawać konkretne produkty.   **Efekt zmiany tego ustawienia:** Tylko zamówienia zawierające te produkty (i żadne inne) będą kwalifikować się do płatności odroczonej.   **Zalecana wartość:** Dodaj odpowiednie produkty, jeśli „Zastosuj tylko do konkretnych produktów” jest TAK.   **Scenariusz sprzedawcy:** Dodajesz „Produkt A” i „Produkt B”. Jeśli koszyk klienta zawiera „Produkt A” i „Produkt C”, płatność odroczona nie będzie dostępna. Jeśli zawiera tylko „Produkt A”, będzie dostępna. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł dodaje kilka nowych sekcji do menu Panelu administracyjnego PrestaShop w celu zarządzania płatnościami odroczonymi.

#### 2.2.1 Użytkownicy płatności odroczonej (Panel administracyjny > Płatność odroczona > Użytkownicy płatności odroczonej)

Ten ekran pozwala zarządzać indywidualnymi uprawnieniami klientów do płatności odroczonej, zastępując lub uzupełniając ustawienia grup klientów.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Płatność odroczona > Użytkownicy płatności odroczonej
- **Dostępne akcje i ustawienia:**
  - **Tabela listy:** Wyświetla listę klientów, którym specjalnie przyznano lub odmówiono dostępu do płatności odroczonej.
  - **Dodaj nowego / Edytuj użytkownika:**
    - **Wyszukiwanie klienta:** Znajdź konkretnego klienta po imieniu lub adresie e-mail.
    - **Włącz płatność odroczoną:** Przełącznik TAK/NIE, aby przyznać lub odebrać dostęp do płatności odroczonej temu indywidualnemu klientowi.
    - **Dni na płatność (nadpisanie):** Opcjonalnie ustaw niestandardową liczbę dni na płatność dla tego konkretnego klienta, nadpisując ustawienie globalne.
    - **Limit kredytowy:** Ustaw maksymalną zaległą kwotę (w Twojej domyślnej walucie, na podstawie `PS_CURRENCY_DEFAULT`), jaką ten klient może mieć w zamówieniach z płatnością odroczoną.
  - **Efekt zmian:**
    - Dodanie klienta i włączenie płatności odroczonej przyznaje mu dostęp, nawet jeśli jego grupa nie jest wybrana w głównej konfiguracji modułu.
    - Wyłączenie dla klienta odbiera mu dostęp, nawet jeśli jego grupa jest wybrana.
    - Niestandardowe dni na płatność i limity kredytowe dotyczą tylko tego konkretnego klienta.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Użyj tej sekcji, aby przyznać specjalne warunki płatności odroczonej indywidualnym klientom VIP lub zablokować problematycznych klientów.
  2. Regularnie przeglądaj limity kredytowe dla użytkowników płatności odroczonej o dużym wolumenie.

#### 2.2.2 Dziennik aktywności płatności odroczonej (Panel administracyjny > Płatność odroczona > Dziennik aktywności)

Ten ekran zapewnia historyczny zapis działań i zdarzeń związanych z płatnościami odroczonymi.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Płatność odroczona > Dziennik aktywności
- **Dostępne akcje i ustawienia:**
  - **Tabela listy:** Wyświetla dziennik zdarzeń, który może obejmować:
    - Kiedy złożono zamówienie z płatnością odroczoną.
    - Kiedy płatność została oznaczona jako otrzymana.
    - Zmiany w ustawieniach użytkownika płatności odroczonej.
    - Wykonania zadań cron.
  - **Kolumny:** Zazwyczaj obejmuje Datę/Godzinę, Typ zdarzenia, Powiązane zamówienie/klienta, Opis.
- **Efekt zmian:** Jest to dziennik tylko do odczytu. Nie możesz bezpośrednio zmieniać wpisów tutaj, ale zapewnia cenne informacje do audytu i rozwiązywania problemów.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Okresowo sprawdzaj dziennik, aby monitorować aktywność płatności odroczonej i upewnić się, że wszystko działa płynnie.
  2. Użyj go do badania wszelkich problemów zgłoszonych przez klientów dotyczących ich zamówień z płatnością odroczoną.

#### 2.2.3 Pulpit (Panel administracyjny > Płatność odroczona > Pulpit)

Ten ekran (prawdopodobnie reprezentowany przez `defpay/controllers/admin/index.php`) zazwyczaj zapewnia przegląd lub podsumowanie działań związanych z płatnościami odroczonymi.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Płatność odroczona > Pulpit (lub główna pozycja menu „Płatność odroczona”)
- **Dostępne akcje i ustawienia:**
  - **Widok siatki / zarządzania:** Ten ekran prawdopodobnie przedstawia kluczowe statystyki, oczekujące płatności, zaległe płatności lub szybkie podsumowanie zamówień z płatnością odroczoną. Może oferować filtry lub możliwości wyszukiwania.
- **Efekt zmian:** Jest to przede wszystkim informacyjny pulpit nawigacyjny. Wszelkie podjęte działania (np. oznaczenie zamówienia jako opłacone) zazwyczaj przekierowują do konkretnej strony zamówienia lub innego ekranu zarządzania.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Użyj tego jako głównego przeglądu, aby szybko zidentyfikować zamówienia wymagające uwagi (np. zbliżające się terminy płatności, zaległe płatności).
  2. Monitoruj ogólny stan swojego systemu płatności odroczonej.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|
| **Konfiguracja modułu** | Włącz płatność odroczoną | TAK | Główny przełącznik dla metody płatności. |
| | Dozwolone grupy klientów | (Wybierz odpowiednie grupy) | Ogranicza dostęp do konkretnych segmentów klientów. |
| | Dni na płatność | 30 | Ustawia domyślny termin płatności w dniach. |
| | Minimalna kwota zamówienia dla płatności odroczonej | 0.00 | Minimalna wartość koszyka dla kwalifikacji do płatności odroczonej. |
| | Status zamówienia dla płatności odroczonej | Oczekuje na płatność odroczoną | Początkowy status dla zamówień złożonych tą metodą. |
| | URL zadania Cron | (Wyświetlany URL) | URL dla zadań automatyzacji po stronie serwera. |
| | Zastosuj tylko do konkretnych produktów | NIE | Ogranicza płatność odroczoną do konkretnych produktów. |
| | Produkty dozwolone dla płatności odroczonej | (Puste) | Lista produktów kwalifikujących się, jeśli „Zastosuj tylko do konkretnych produktów” jest TAK. |
| **Użytkownicy płatności odroczonej** | Wyszukiwanie klienta | N/A | Znajdź i zarządzaj indywidualnym dostępem klienta. |
| | Włącz płatność odroczoną (na użytkownika) | TAK/NIE | Indywidualne nadpisanie dostępu do płatności odroczonej. |
| | Dni na płatność (nadpisanie) | (Puste dla globalnego) | Niestandardowe warunki płatności dla konkretnego klienta. |
| | Limit kredytowy | (Puste dla braku limitu) | Maksymalna zaległa kwota dla konkretnego klienta. |
| **Dziennik aktywności** | N/A | N/A | Dziennik zdarzeń płatności odroczonej tylko do odczytu. |
| **Pulpit** | N/A | N/A | Przegląd zamówień z płatnością odroczoną i statystyk. |

## 3. Rozwiązywanie problemów dla sprzedawcy i często zadawane pytania (FAQ)

**P: Dlaczego płatność odroczona nie pojawia się dla moich klientów przy kasie?**
O:

1.  **Czy moduł jest włączony?** Sprawdź „Włącz płatność odroczoną” w konfiguracji modułu.
2.  **Czy grupy klientów są poprawne?** Upewnij się, że klient jest zalogowany i należy do jednej z „Dozwolonych grup klientów” wybranych w ustawieniach modułu.
3.  **Minimalna kwota zamówienia:** Czy suma koszyka jest powyżej „Minimalnej kwoty zamówienia dla płatności odroczonej”?
4.  **Konkretne produkty:** Jeśli „Zastosuj tylko do konkretnych produktów” jest włączone, czy koszyk zawiera *tylko* produkty z Twojej zatwierdzonej listy?
5.  **Indywidualne ustawienia użytkownika:** Sprawdź „Użytkownicy płatności odroczonej”, aby sprawdzić, czy klient został indywidualnie wyłączony lub ma specyficzne nadpisania.
6.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność) i pamięć podręczną przeglądarki.

**P: Jak zmienić status zamówienia po otrzymaniu płatności odroczonej?**
O: Musisz ręcznie zaktualizować status zamówienia w Panelu administracyjnym PrestaShop. Przejdź do **Zamówienia > Zamówienia**, znajdź odpowiednie zamówienie i zmień jego status z „Oczekuje na płatność odroczoną” (lub cokolwiek skonfigurowałeś) na „Płatność zaakceptowana” lub „Dostarczono”, w zależności od sytuacji.

**P: Czy mogę ustawić różne dni na płatność dla różnych klientów?**
O: Tak! Użyj ekranu „Użytkownicy płatności odroczonej”. Możesz wyszukać konkretnego klienta i ustawić dla niego niestandardowe „Dni na płatność (nadpisanie)”, które będą miały pierwszeństwo przed ustawieniem globalnym.

**P: Do czego służy URL zadania Cron i czy muszę go konfigurować?**
O: URL zadania Cron służy do zautomatyzowanych zadań, które moduł może wykonywać w tle (np. sprawdzanie zaległych płatności, wysyłanie powiadomień, jeśli są zaimplementowane). Chociaż moduł może działać bez niego dla podstawowego przetwarzania płatności, zdecydowanie zaleca się skonfigurowanie go na serwerze, aby zapewnić prawidłowe działanie wszystkich zautomatyzowanych funkcji. Twój dostawca usług hostingowych lub deweloper może pomóc w skonfigurowaniu zadania cron, aby codziennie odwiedzało ten URL.

**P: Moduł jest zainstalowany, ale nie widzę pozycji menu „Płatność odroczona” w Panelu administracyjnym.**
O:

1.  **Uprawnienia:** Sprawdź swoje uprawnienia pracownika (Zaawansowane > Zespół > Pracownicy > Edytuj swój profil > zakładka Uprawnienia). Upewnij się, że masz dostęp do modułu „Płatność odroczona” i związanych z nim kontrolerów administracyjnych.
2.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność).

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu Płatność odroczona dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł Płatność odroczona jest zgodny ze standardowym wzorcem MVC (Model-View-Controller) PrestaShop. Integruje się jako moduł płatności, rozszerzając `PaymentModule` i udostępniając niestandardowe kontrolery administracyjne do zarządzania użytkownikami płatności odroczonej i dziennikami. Wykorzystuje system konfiguracji PrestaShop do ustawień i hooki do wyświetlania w Front Office oraz integracji zamówień w Back Office. Moduł wprowadza niestandardowe tabele bazy danych (`defpay_log`, `defpayuser`) do przechowywania specyficznych danych płatności odroczonej.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

- `defpay/controllers/front/cron.php`
  - **Nazwa klasy:** `DefPayCronModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Obsługuje wykonywanie zadań cron. Ten kontroler jest dostępny za pośrednictwem `Cron Job URL` podanego w konfiguracji modułu. Jest przeznaczony do okresowego wywoływania przez harmonogram cron po stronie serwera w celu wykonywania operacji w tle, takich jak sprawdzanie terminów płatności, aktualizowanie statusów zamówień lub wyzwalanie powiadomień.
- `defpay/controllers/front/index.php`
  - **Nazwa klasy:** `DefPayIndexModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Zastępczy lub domyślny kontroler Front Office. Często używany do podstawowego routingu modułu lub jeśli moduł potrzebuje domyślnego punktu wejścia Front Office, który nie odpowiada bezpośrednio konkretnej akcji. W tym module może nie mieć bezpośredniej funkcji skierowanej do użytkownika.
- `defpay/controllers/front/statement.php`
  - **Nazwa klasy:** `DefPayStatementModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Prawdopodobnie obsługuje wyświetlanie lub generowanie wyciągów z płatności odroczonej dla klientów. Może to być strona w obszarze konta klienta pokazująca oczekujące płatności lub link do pobrania faktury.
- `defpay/controllers/front/validation.php`
  - **Nazwa klasy:** `DefPayValidationModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Główny kontroler walidacji płatności. Gdy klient wybierze „Płatność odroczoną” przy kasie i potwierdzi zamówienie, ten kontroler przetwarza zamówienie, ustawia odpowiedni status zamówienia i przekierowuje klienta na stronę potwierdzenia zamówienia.

#### Kontrolery administracyjne Back Office

- `defpay/controllers/admin/AdminDefPayActivityLog.php`
  - **Nazwa klasy:** `AdminDefPayActivityLogController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** `Dziennik aktywności płatności odroczonej`
  - **Zarządzana encja:** `defpay_log` (niestandardowa tabela bazy danych)
  - **Odpowiedzialność:** Zapewnia interfejs zarządzania listą dla tabeli `defpay_log`. Wyświetla historyczny zapis zdarzeń związanych z płatnościami odroczonymi, takich jak złożenie zamówienia, zmiany statusu lub działania zadań cron.
- `defpay/controllers/admin/AdminDefPayUsers.php`
  - **Nazwa klasy:** `AdminDefPayUsersController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** `Użytkownicy płatności odroczonej`
  - **Zarządzana encja:** `defpayuser` (niestandardowa tabela bazy danych)
  - **Odpowiedzialność:** Zarządza indywidualnymi ustawieniami klienta dla płatności odroczonej. Umożliwia administratorom włączanie/wyłączanie płatności odroczonej dla konkretnych klientów, ustawianie niestandardowych dni na płatność i definiowanie limitów kredytowych. Współdziała z tabelą `ps_currency` (za pośrednictwem `PS_CURRENCY_DEFAULT`) dla waluty limitu kredytowego.
- `defpay/controllers/admin/index.php`
  - **Nazwa klasy:** `AdminDefPayDashboardController` (prawdopodobnie, rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** `Pulpit płatności odroczonej` (lub główna pozycja menu)
  - **Zarządzana encja:** Brak bezpośredniej pojedynczej encji; agreguje dane.
  - **Odpowiedzialność:** Służy jako główny pulpit nawigacyjny lub przegląd modułu Płatność odroczona w Back Office. Prawdopodobnie wyświetla kluczowe statystyki, podsumowania oczekujących/zaległych płatności i szybkie linki do innych sekcji zarządzania.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczone informacje o module nie wskazują na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że podstawowa logika modułu, w tym definicje `ObjectModel` dla `defpay_log` i `defpayuser`, może być bezpośrednio osadzona w głównym pliku `defpay/cronjob.php` lub w samych kontrolerach administracyjnych. Jest to mniej powszechne, ale czasami stosowane podejście dla prostszych modułów.

Jeśli `defpay_log` i `defpayuser` są rzeczywiście niestandardowymi tabelami, ich definicje `ObjectModel` (np. klasy `DefPayLog` i `DefPayUser`) zazwyczaj znajdowałyby się w `classes/`. Jeśli nie, są one prawdopodobnie zdefiniowane wbudowane lub zarządzane bezpośrednio za pomocą wywołań klasy `Db`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `defpay/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Zakres:** Back Office.
  - **Opis:** Prawdopodobnie zapewnia funkcjonalność do zarządzania szablonami e-maili w konfiguracji modułu lub na konkretnych ekranach administracyjnych. Może to obejmować dynamiczne pola formularzy, podgląd szablonów lub zapisywanie zawartości szablonów.
- `defpay/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back Office (np. `AdminDefPayUsers` do wyszukiwania klientów lub konfiguracja modułu do wyszukiwania produktów).
  - **Opis:** Implementuje funkcję autouzupełniania dla pól wyszukiwania, takich jak wyszukiwanie klientów lub produktów. Nasłuchuje na dane wejściowe użytkownika, wykonuje wywołania AJAX w celu pobrania sugestii i wyświetla je w rozwijanej liście.
- `defpay/tools/browser-demo-simulator.js`
  - **Zakres:** Potencjalnie oba, ale bardziej prawdopodobne dla rozwoju/testowania.
  - **Opis:** Skrypt narzędziowy, prawdopodobnie do symulowania zachowania przeglądarki lub interakcji modułu w celach testowych. Zazwyczaj nie jest używany w środowisku produkcyjnym.
- `defpay/views/js/adminDefPayActivityPreview.js`
  - **Zakres:** Back Office (`AdminDefPayActivityLog`).
  - **Opis:** Zapewnia interaktywne funkcje dla dziennika aktywności, takie jak rozwijanie wpisów dziennika, filtrowanie lub podgląd szczegółów aktywności.
- `defpay/views/js/adminDefPayCollections.js`
  - **Zakres:** Back Office (prawdopodobnie związane z zarządzaniem windykacją płatności odroczonych).
  - **Opis:** Implementuje logikę JavaScript dla interfejsu zarządzania „windykacją”, która może obejmować oznaczanie płatności jako otrzymanych, wysyłanie przypomnień lub zarządzanie zaległymi kontami.
- `defpay/views/js/adminDefPayDashboard.js`
  - **Zakres:** Back Office (Pulpit).
  - **Opis:** Obsługuje interaktywne elementy pulpitu płatności odroczonej, takie jak dynamiczne wykresy, filtrowanie danych lub aktualizacje statystyk za pomocą AJAX.
- `defpay/views/js/adminDefPayPortfolio.js`
  - **Zakres:** Back Office.
  - **Opis:** Prawdopodobnie związane z zarządzaniem „portfelem” kont lub zamówień z płatnością odroczoną, być może oferując zaawansowane filtrowanie, raportowanie lub działania zbiorcze.
- `defpay/views/js/defpay_target_products.js`
  - **Zakres:** Back Office (Konfiguracja modułu).
  - **Opis:** Zapewnia funkcjonalność JavaScript dla sekcji „Produkty docelowe” w konfiguracji modułu, umożliwiając wyszukiwanie, wybieranie i usuwanie produktów kwalifikujących się do płatności odroczonej.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `defpay/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Zakres:** Back Office.
  - **Opis:** Style dla interfejsu zarządzania szablonami e-maili, zapewniające spójny wygląd w panelu administracyjnym PrestaShop.
- `defpay/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Back Office.
  - **Opis:** Style dla sugestii wyszukiwania autouzupełniania, zapewniające ich wizualną odrębność i łatwość użytkowania.
- `defpay/views/css/admin_defpay.css`
  - **Zakres:** Back Office.
  - **Opis:** Ogólne style dla niestandardowych ekranów administracyjnych modułu (Pulpit, Użytkownicy, Dziennik aktywności), zapewniające spójny projekt w Panelu administracyjnym PrestaShop.
- `defpay/views/css/defpay.css`
  - **Zakres:** Front Office.
  - **Opis:** Ogólne style dla komponentów Front Office modułu, takich jak wyświetlanie opcji płatności na stronie kasy lub sekcje konta klienta.
- `defpay/views/css/statement-document.css`
  - **Zakres:** Front Office (do druku/PDF).
  - **Opis:** Specyficzne style dla wersji do druku lub PDF wyciągu z płatności odroczonej, zoptymalizowane pod kątem układu dokumentu.
- `defpay/views/css/statement.css`
  - **Zakres:** Front Office.
  - **Opis:** Style dla wyświetlania na ekranie wyciągów z płatności odroczonej w obszarze konta klienta.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

- `defpay/views/templates/hook/confirmation.tpl`
  - **Hook:** `displayOrderConfirmation` (lub podobny).
  - **Wyjście:** Treść wyświetlana na stronie potwierdzenia zamówienia po złożeniu zamówienia z płatnością odroczoną, informująca klienta o warunkach płatności.
- `defpay/views/templates/hook/displayAdminOrder16.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.6).
  - **Wyjście:** Dodaje blok informacji lub działań związanych z płatnością odroczoną na stronie szczegółów zamówienia w Panelu administracyjnym PrestaShop 1.6.
- `defpay/views/templates/hook/displayAdminOrder17.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.7+).
  - **Wyjście:** Podobnie jak `displayAdminOrder16.tpl`, ale dostosowany do strony szczegółów zamówienia w Panelu administracyjnym PrestaShop 1.7+, pokazujący status płatności odroczonej, termin płatności i ewentualne działania windykacyjne.
- `defpay/views/templates/hook/displayCustomerAccount.tpl`
  - **Hook:** `displayCustomerAccount` lub `displayMyAccountBlock`.
  - **Wyjście:** Dodaje link lub blok do strony „Moje konto” klienta, potencjalnie łącząc się z jego wyciągiem z płatności odroczonej lub historią.
- `defpay/views/templates/hook/displayOrderDetail.tpl`
  - **Hook:** `displayOrderDetail` (Front Office).
  - **Wyjście:** Wyświetla informacje specyficzne dla płatności odroczonej (np. termin płatności, status płatności) na stronie szczegółów zamówienia w Front Office klienta.
- `defpay/views/templates/hook/payment.tpl`
  - **Hook:** `displayPayment` (lub `paymentOptions` dla PS 1.7+).
  - **Wyjście:** Renderuje opcję „Płatność odroczona” na stronie wyboru płatności przy kasie.

#### Szablony administracyjne (`views/templates/admin/`)

- `defpay/views/templates/admin/cron_setup.tpl`
  - **Cel:** Prawdopodobnie używany na głównej stronie konfiguracji modułu (`getContent()`) do wyświetlania URL zadania Cron i instrukcji.
- `defpay/views/templates/admin/defpay_target_products.tpl`
  - **Cel:** Renderuje interfejs do wyboru konkretnych produktów kwalifikujących się do płatności odroczonej w konfiguracji modułu.

#### Szablony Front Office (`views/templates/front/`)

- `defpay/views/templates/front/statement_preview.tpl`
  - **Cel:** Wyświetla podgląd wyciągu z płatności odroczonej klientowi w Front Office.
- `defpay/views/templates/front/validation.tpl`
  - **Cel:** Szablon renderowany przez kontroler Front Office `validation.php`, zazwyczaj komunikat potwierdzający lub podsumowanie po pomyślnym złożeniu zamówienia z płatnością odroczoną.

#### Szablony PDF (`views/templates/pdf/`)

- `defpay/views/templates/pdf/statement.tpl`
  - **Cel:** Szablon używany do generowania wersji PDF wyciągu z płatności odroczonej lub faktury.

#### Szablony bibliotek (`defpay/lib/emailTemplatesManager/views/` i `defpay/lib/searchTool/views/`)

Te szablony są częścią wbudowanych bibliotek w module:

- `defpay/lib/emailTemplatesManager/views/buttonManager.tpl`
- `defpay/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/mainForm.tpl`
- `defpay/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Cel:** Te szablony są używane do renderowania różnych komponentów interfejsu zarządzania szablonami e-maili w Back Office.
- `defpay/lib/searchTool/views/scripts.tpl`
  - **Cel:** Prawdopodobnie zawiera inicjalizację JavaScript lub konfigurację dla narzędzia wyszukiwania autouzupełniania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

- `ps_defpay_log` (lub `defpay_log`):
  - Przechowuje wpisy dziennika aktywności związane z płatnościami odroczonymi.
  - Pola prawdopodobnie obejmują: `id_defpay_log`, `id_order`, `id_customer`, `event_type`, `description`, `date_add`.
- `ps_defpayuser` (lub `defpayuser`):
  - Przechowuje indywidualne ustawienia płatności odroczonej dla klientów.
  - Pola prawdopodobnie obejmują: `id_defpayuser`, `id_customer`, `deferred_payment_enabled` (boolean), `payment_due_days_override` (int), `credit_limit` (decimal), `date_add`, `date_upd`.
- `ps_configuration`:
  - Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `DEFPAY_ENABLED`, `DEFPAY_GROUPS`, `DEFPAY_DUE_DAYS`, `DEFPAY_MIN_TOTAL`, `DEFPAY_ORDER_STATUS`, `DEFPAY_CRON_URL`, `DEFPAY_TARGET_PRODUCTS_ENABLED`, `DEFPAY_TARGET_PRODUCTS_LIST`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayPayment` (PS 1.6) | Na etapie wyboru płatności przy kasie. | Renderuje opcję „Płatność odroczona”. |
| `paymentOptions` (PS 1.7+) | Na etapie wyboru płatności przy kasie. | Renderuje opcję „Płatność odroczona” (nowoczesny hook). |
| `displayOrderConfirmation` | Po pomyślnym złożeniu zamówienia. | Wyświetla szczegóły płatności odroczonej na stronie potwierdzenia. |
| `displayCustomerAccount` / `displayMyAccountBlock` | Na stronie „Moje konto” klienta. | Dodaje link do wyciągów z płatności odroczonej lub historii. |
| `displayOrderDetail` | Na stronie szczegółów zamówienia w Front Office klienta. | Pokazuje informacje specyficzne dla płatności odroczonej dla zamówienia. |
| `displayAdminOrder` (PS 1.6) | Na stronie szczegółów zamówienia w Back Office (PS 1.6). | Wstrzykuje status płatności odroczonej i narzędzia do zarządzania. |
| `displayAdminOrder` (PS 1.7+) | Na stronie szczegółów zamówienia w Back Office (PS 1.7+). | Wstrzykuje status płatności odroczonej i narzędzia do zarządzania. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Służy do wykonywania działań, takich jak ustawienie początkowego statusu zamówienia z płatnością odroczoną, rejestrowanie zdarzenia lub tworzenie wpisu `defpayuser` w razie potrzeby. |
| `actionOrderStatusUpdate` | Gdy status zamówienia zostanie zmieniony. | Może być używany do wyzwalania działań na podstawie zmian statusu (np. otrzymanie płatności, zaległość). |
| `actionFrontControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler Front Office. | Służy do kolejkowania zasobów CSS i JS Front Office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler administracyjny. | Służy do kolejkowania zasobów CSS i JS Back Office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Znajdziesz tam zakupione moduły i dostęp do naszych kanałów wsparcia.
