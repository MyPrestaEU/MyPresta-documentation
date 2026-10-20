---
title: "Obsługa wysyłki do płatności + produktów wirtualnych - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Obsługa wysyłki do płatności + produktów wirtualnych” od MyPresta.eu."
sidebar:
  label: "Obsługa wysyłki do płatności + produktów wirtualnych - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Ship to pay + virtual products support na MyPresta.eu](https://mypresta.eu/modules/payment-process/ship-to-pay-virtual-products-support.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/ship-to-pay-virtual-products-support/)
>
> ---


# Obsługa wysyłki do płatności + produktów wirtualnych

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są zwykle obecne w każdym kompatybilnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Obsługa wysyłki do płatności + produktów wirtualnych”. Zostanie wyświetlony pojedynczy, kompleksowy ekran konfiguracji.

Ten ekran wyświetla macierz (siatkę), w której możesz połączyć dostępne metody wysyłki z zainstalowanymi modułami płatności.

**Zrozumienie siatki konfiguracji:**

- **Wiersze (Przewoźnicy):** Każdy wiersz reprezentuje przewoźnika, którego skonfigurowałeś w swoim sklepie PrestaShop (np. „Mój przewoźnik”, „Domyślny przewoźnik PrestaShop”, „DHL”, „UPS” itp.).
- **Kolumny (Moduły płatności):** Każda kolumna reprezentuje moduł płatności, który zainstalowałeś i włączyłeś w swoim sklepie PrestaShop (np. „Przelew bankowy”, „Płatność przy odbiorze”, „PayPal”, „Stripe” itp.).
- **Pola wyboru:** Na przecięciu każdego wiersza przewoźnika i kolumny modułu płatności znajduje się pole wyboru.

**Jak skonfigurować:**

1. **Zidentyfikuj swoich przewoźników:** Spójrz na lewą kolumnę, aby zobaczyć wszystkich aktywnych przewoźników.
2. **Zidentyfikuj swoje metody płatności:** Spójrz na górny wiersz, aby zobaczyć wszystkie aktywne moduły płatności.
3. **Połącz je:** Dla każdego przewoźnika przejdź wzdłuż jego wiersza i **zaznacz pole** dla każdej metody płatności, którą chcesz zezwolić dla tego konkretnego przewoźnika.
   - *Co robi to ustawienie:* To pole wyboru określa, czy dana metoda płatności zostanie zaoferowana klientowi, gdy wybierze on odpowiedniego przewoźnika podczas realizacji zamówienia.
   - *Efekt zmiany tego ustawienia:*
     - **Po zaznaczeniu:** Metoda płatności będzie widoczna i możliwa do wybrania przez klienta, jeśli wybierze tego przewoźnika.
     - **Po odznaczeniu:** Metoda płatności będzie ukryta i niedostępna dla klienta, jeśli wybierze tego przewoźnika.
   - *Zalecana wartość:* Zaznacz tylko te kombinacje, które mają sens dla Twojej logiki biznesowej.
   - *Scenariusz/przykład sprzedawcy:* Jeśli „DHL Express” to szybka, premium usługa, możesz zaznaczyć tylko „PayPal” i „Karta kredytowa (Stripe)” dla niej, a odznaczyć „Przelew bankowy”, aby zapewnić szybką płatność za szybką dostawę.

**Specjalny wiersz: „Produkty wirtualne”**

Ten moduł zawiera unikalną funkcję dla produktów wirtualnych. Zobaczysz dedykowany wiersz oznaczony **„Produkty wirtualne”** (lub podobny, w zależności od wersji i języka PrestaShop).

- **Co robi to ustawienie:** Ten wiersz pozwala określić, które metody płatności są dostępne, gdy koszyk klienta zawiera *tylko* produkty wirtualne. Ponieważ produkty wirtualne nie mają tradycyjnej metody wysyłki, ten wiersz działa jako ich „przewoźnik” do powiązania metod płatności.
- *Efekt zmiany tego ustawienia:*
  - **Po zaznaczeniu (dla metody płatności w wierszu „Produkty wirtualne”):** Ta metoda płatności będzie dostępna, jeśli koszyk klienta składa się wyłącznie z produktów wirtualnych.
  - **Po odznaczeniu:** Ta metoda płatności nie będzie dostępna dla koszyków zawierających tylko produkty wirtualne.
- *Zalecana wartość:* Zaznacz metody płatności, które są odpowiednie do natychmiastowej dostawy cyfrowej, zazwyczaj bramki płatności online, takie jak PayPal, Stripe lub moduły kart kredytowych.
- *Scenariusz/przykład sprzedawcy:* Jeśli sprzedajesz e-booki, prawdopodobnie zaznaczyłbyś „PayPal” i „Karta kredytowa (Stripe)” w wierszu „Produkty wirtualne”, ale odznaczyłbyś „Płatność przy odbiorze” lub „Przelew bankowy”, ponieważ są one nieodpowiednie do natychmiastowej dostawy cyfrowej.

**Zapisywanie konfiguracji:**

- Po dokonaniu wszystkich wyborów pamiętaj, aby kliknąć przycisk **„Zapisz”** (zazwyczaj na dole strony), aby zastosować zmiany.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Pole wyboru dla Przewoźnika X / Płatności Y | Domyślnie odznaczone | **Cel:** Łączy konkretną metodę płatności z konkretnym przewoźnikiem. **Wpływ:** Jeśli zaznaczone, metoda płatności jest dostępna po wybraniu Przewoźnika X. Jeśli odznaczone, jest ukryta. |
| Strona konfiguracji modułu | Pole wyboru dla „Produktów wirtualnych” / Płatności Y | Domyślnie odznaczone | **Cel:** Łączy konkretną metodę płatności z koszykami zawierającymi tylko produkty wirtualne. **Wpływ:** Jeśli zaznaczone, metoda płatności jest dostępna dla koszyków zawierających tylko produkty wirtualne. Jeśli odznaczone, jest ukryta. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem moduł, ale metody płatności nie zmieniają się w kasie. Co jest nie tak?**
O1:

- **Wyczyść pamięć podręczną:** Najczęstszy problem. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
- **Moduł włączony:** Upewnij się, że moduł „Obsługa wysyłki do płatności + produktów wirtualnych” jest faktycznie włączony w **Moduły > Menedżer modułów**.
- **Moduły płatności włączone:** Upewnij się, że moduły płatności, które próbujesz połączyć, są również włączone i poprawnie skonfigurowane w Twoim sklepie.
- **Kompatybilność z motywem:** Chociaż rzadko, niektóre mocno dostosowane motywy mogą kolidować. Jeśli wyczyszczenie pamięci podręcznej nie działa, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby sprawdzić, czy problem nadal występuje. Jeśli to rozwiąże problem, Twój motyw może wymagać dostosowania.

**P2: Dlaczego niektóre metody płatności nadal są wyświetlane, mimo że je odznaczyłem dla przewoźnika?**
O2:

- **Wiele przewoźników w koszyku:** Jeśli klient ma w koszyku produkty, które korzystałyby z różnych przewoźników (np. jeden produkt wysyłany przez przewoźnika A, inny przez przewoźnika B), logika realizacji zamówienia PrestaShop może stać się złożona. Ten moduł działa przede wszystkim, gdy dla całego koszyka wybrana jest jedna metoda wysyłki.
- **Produkty wirtualne w koszyku:** Jeśli koszyk zawiera mieszankę produktów fizycznych i wirtualnych, logika modułu dla produktów wirtualnych może wchodzić w interakcje z logiką specyficzną dla przewoźnika. Upewnij się, że wiersz „Produkty wirtualne” jest skonfigurowany zgodnie z zamierzeniami.
- **Inne moduły:** Inny moduł może nadpisywać opcje płatności. Tymczasowo wyłącz inne moduły związane z płatnościami, aby sprawdzić, czy nie ma konfliktów.

**P3: Jak przetłumaczyć tekst modułu na inne języki?**
O3:

- Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
- Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz język, na który chcesz przetłumaczyć.
- Znajdź moduł „Obsługa wysyłki do płatności + produktów wirtualnych” na liście i kliknij „Modyfikuj”. Możesz wtedy edytować dowolne przetłumaczalne ciągi znaków.

**P4: Dodałem nowego przewoźnika lub moduł płatności, ale nie wyświetla się on w siatce konfiguracji.**
O4:

- **Odśwież konfigurację modułu:** Czasami PrestaShop potrzebuje odświeżenia, aby wykryć nowe encje. Przejdź do **Moduły > Menedżer modułów**, znajdź „Obsługa wysyłki do płatności + produktów wirtualnych” i ponownie kliknij „Konfiguruj”. Powinno to ponownie załadować stronę konfiguracji i wyświetlić nowego przewoźnika/moduł płatności.
- **Upewnij się, że jest włączony:** Upewnij się, że nowy przewoźnik lub moduł płatności jest w pełni włączony i skonfigurowany w odpowiedniej sekcji Panelu administracyjnego PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Obsługa wysyłki do płatności + produktów wirtualnych” działa poprzez nadpisywanie podstawowej klasy PrestaShop odpowiedzialnej za znajdowanie dostępnych opcji płatności podczas realizacji zamówienia. Pozwala to na wstrzyknięcie niestandardowej logiki opartej na wybranych przewoźnikach i obecności produktów wirtualnych w koszyku, filtrując metody płatności prezentowane klientowi. Wykorzystuje system nadpisywania PrestaShop i standardowe przechowywanie konfiguracji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego logika jest obsługiwana głównie przez główny plik modułu i nadpisanie.

### 4.3 Klasy i modele podstawowe (`classes/`)

- **`shiptopay/override/classes/checkout/PaymentOptionsFinder.php`**
  - **Cel:** To jest rdzeń funkcjonalności modułu. Nadpisuje domyślną klasę `PaymentOptionsFinder` PrestaShop, która jest odpowiedzialna za określanie, które opcje płatności są dostępne dla klienta podczas realizacji zamówienia.
  - **Klasa nadrzędna:** `PaymentOptionsFinderCore`
  - **Kluczowe metody i logika:**
    - Nadpisana metoda `find()` (lub podobna, w zależności od wersji PrestaShop) jest przechwytywana.
    - Wewnątrz tej metody moduł pobiera aktualnie wybrany identyfikator przewoźnika (z koszyka lub sesji) i sprawdza, czy koszyk zawiera tylko produkty wirtualne.
    - Następnie odpytuje konfigurację modułu (przechowywaną w `ps_configuration`), aby określić, które moduły płatności są dozwolone dla wybranego przewoźnika lub dla produktów wirtualnych.
    - Oryginalna lista opcji płatności zwrócona przez `PaymentOptionsFinderCore` jest następnie filtrowana, usuwając wszelkie metody płatności, które nie są dozwolone zgodnie z konfiguracją modułu.
    - Zapewnia to, że klientowi wyświetlane są tylko dozwolone metody płatności.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Dynamiczne aktualizowanie opcji płatności jest obsługiwane przez podstawowy JavaScript realizacji zamówienia PrestaShop, który reaguje na zmiany w wyborze metody wysyłki i ponownie renderuje sekcję płatności na podstawie przefiltrowanych opcji dostarczonych przez nadpisaną klasę `PaymentOptionsFinder`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Integruje się płynnie z istniejącym stylem motywu PrestaShop dla opcji płatności.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`shiptopay/views/shiptopay.tpl`**
  - **Cel:** Ten szablon jest prawdopodobnie używany do renderowania formularza konfiguracji modułu w Panelu administracyjnym PrestaShop. Konstruuje macierz HTML (siatkę) przewoźników i metod płatności z polami wyboru, umożliwiając sprzedawcy ich połączenie.
  - **Zakres:** Szablon administratora.
  - **Zmienne:** Zazwyczaj iterowałby po tablicach `$carriers` i `$payment_modules`, używając `Configuration::get()` do pobierania zapisanych ustawień dla każdego pola wyboru.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych:**

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Ustawienia konfiguracji (powiązania między przewoźnikami/produktami wirtualnymi a metodami płatności) są przechowywane w tabeli `ps_configuration`. Każde ustawienie byłoby zazwyczaj przechowywane jako para klucz-wartość, gdzie kluczem może być `SHIP_TO_PAY_CARRIER_X_PAYMENT_Y`, a wartością `1` (włączone) lub `0` (wyłączone). Ustawienia „Produktów wirtualnych” byłyby zgodne z podobną konwencją nazewnictwa.
- **Tabela zarejestrowanych hooków:**

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayHeader` | W sekcji `<head>` każdej strony. | Chociaż wymieniony jako potencjalny hook front-office, ten moduł używa głównie nadpisywania i zazwyczaj nie renderuje widocznej zawartości za pomocą `displayHeader`. Może być używany do wewnętrznej inicjalizacji modułu lub ładowania zasobów, jeśli takie byłyby obecne. |
  | `displayRightColumn` | W prawej kolumnie stron (jeśli włączone przez motyw). | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu, ponieważ jego wpływ dotyczy opcji płatności w kasie. |
  | `displayLeftColumn` | W lewej kolumnie stron (jeśli włączone przez motyw). | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu, ponieważ jego wpływ dotyczy opcji płatności w kasie. |
  | `displayFooter` | W sekcji stopki każdej strony. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu, ponieważ jego wpływ dotyczy opcji płatności w kasie. |
  | `displayModuleConfigureExtraButtons` | W menedżerze modułów, obok przycisku konfiguracji. | Nie jest wyraźnie używany do podstawowej funkcjonalności, ale może być używany do dodatkowych działań administracyjnych. |
  | `actionPaymentOptionsModifier` | (Niejawne/Wewnętrzne) | Ten moduł działa przede wszystkim poprzez nadpisywanie `PaymentOptionsFinder`, który jest wywoływany wewnętrznie podczas procesu realizacji zamówienia w celu wygenerowania listy opcji płatności. Chociaż nie jest to tradycyjny hook `hookDisplay` ani `action`, nadpisanie działa jako punkt przechwytywania. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Obsługa wysyłki do płatności + produktów wirtualnych”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
