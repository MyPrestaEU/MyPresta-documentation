---
title: "Conditional Order Fees - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Conditional Order Fees od MyPresta.eu."
sidebar:
  label: "Conditional Order Fees - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Conditional Order Fees na MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-fees.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/conditional-order-fees/)
>
> ---


# Conditional Order Fees

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Conditional Order Fees)

Jest to główny ekran konfiguracji, na którym włączasz lub wyłączasz moduł i konfigurujesz podstawowy „produkt”, który reprezentuje Twoje opłaty.

- **Lokalizacja w menu:** Panel administracyjny > Moduły > Menedżer modułów > Conditional Order Fees > Konfiguruj

#### Ustawienia ogólne

- **Włącz moduł:**

  - **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Moduł będzie aktywnie oceniał zdefiniowane zasady opłat i stosował opłaty do koszyków, które spełniają warunki.
    - *Gdy wyłączony:* Moduł nie będzie stosował żadnych opłat, niezależnie od ustawień zasad.
  - **Zalecana wartość:** TAK (po skonfigurowaniu zasad).
  - **Scenariusz / przykład sprzedawcy:** Skończyłeś konfigurować wszystkie zasady opłat i jesteś gotowy do uruchomienia. Włącz to, aby zacząć pobierać opłaty. Jeśli musisz tymczasowo wstrzymać wszystkie opłaty z powodu konserwacji lub promocji, wyłącz to.
- **ID produktu opłaty:**

  - **Co robi to ustawienie:** To kluczowe ustawienie łączy Twoje opłaty z konkretnym, ukrytym produktem w Twoim katalogu. PrestaShop potrzebuje „produktu” do reprezentowania każdego elementu dodanego do koszyka, nawet jeśli jest to usługa lub opłata. Ten moduł tworzy specjalny, niewidoczny produkt do tego celu podczas instalacji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na prawidłowy ID produktu:* Moduł użyje tego produktu do reprezentowania opłaty w koszyku, realizacji zamówienia i szczegółach zamówienia. Nazwa produktu zostanie zastąpiona niestandardową etykietą opłaty, a jego cena zostanie nadpisana przez obliczoną opłatę.
    - *Gdy ustawiony na nieprawidłowy lub nieistniejący ID produktu:* Moduł nie będzie w stanie dodać opłat do koszyka, ponieważ nie będzie miał prawidłowego produktu „zastępczego” do użycia.
  - **Zalecana wartość:** Użyj ID specjalnego produktu „Conditional Order Fee” utworzonego przez moduł podczas instalacji. Możesz znaleźć to ID, wyszukując „Conditional Order Fee” na liście produktów (choć zazwyczaj jest on ukryty w front-office). Moduł często wstępnie wypełni to pole za Ciebie.
  - **Scenariusz / przykład sprzedawcy:** Moduł automatycznie tworzy produkt o nazwie „Conditional Order Fee” (lub podobnej) i ustawia jego ID tutaj. Zazwyczaj nie powinieneś tego zmieniać, chyba że celowo chcesz użyć innego produktu jako zastępczego dla opłaty (co nie jest zalecane dla większości użytkowników).

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia dedykowane sekcje w Panelu administracyjnym PrestaShop do zarządzania zasadami opłat i przeglądania ich zastosowania.

#### 2.2.1 Panel Conditional Order Fees (Panel administracyjny > Conditional Order Fees > Panel)

Ten ekran zapewnia przegląd aktywności modułu, w tym podsumowanie zastosowanych opłat i szybki dostęp do zarządzania zasadami.

- **Nazwa ekranu i lokalizacja w menu:** **Conditional Order Fees > Panel** (znajduje się pod główną pozycją menu „Conditional Order Fees” w lewym pasku bocznym).
- **Dostępne działania i ustawienia:**
  - **Statystyki podsumowania:** Wyświetl kluczowe metryki, takie jak całkowite zebrane opłaty, liczba zamówień z opłatami i średnia opłata za zamówienie. Pomaga to zrozumieć wpływ zasad opłat.
  - **Ostatnio zastosowane opłaty:** Szybka lista najnowszych zamówień, w których zastosowano opłatę warunkową, w tym ID zamówienia, klienta i kwotę opłaty.
  - **Szybkie linki:** Bezpośrednie linki do „Zarządzaj zasadami” i „Wyświetl dziennik audytu”.
- **Efekt zmian:** Ten ekran służy głównie do monitorowania i nawigacji. Nie dokonuje się tu bezpośrednich zmian, ale odzwierciedla wpływ zasad opłat.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj ten panel, aby monitorować wydajność zasad opłat i upewnić się, że działają zgodnie z oczekiwaniami.

#### 2.2.2 Zarządzaj zasadami opłat (Panel administracyjny > Conditional Order Fees > Zasady)

Tutaj definiujesz, edytujesz i zarządzasz wszystkimi swoimi regułami opłat warunkowych. Każda „zasada” to zestaw warunków, które po spełnieniu spowodują zastosowanie określonej opłaty.

- **Nazwa ekranu i lokalizacja w menu:** **Conditional Order Fees > Zasady** (znajduje się pod główną pozycją menu „Conditional Order Fees” w lewym pasku bocznym).
- **Dostępne działania i ustawienia:**
  - **Lista zasad:** Tabela wyświetlająca wszystkie istniejące zasady opłat, w tym ich nazwę, status (włączony/wyłączony), priorytet i kwotę/typ opłaty.
  - **Dodaj nową zasadę:** Kliknij przycisk „Dodaj nową zasadę”, aby utworzyć nową regułę opłaty.
    - **Nazwa zasady:** Opisowa nazwa do wewnętrznego użytku (np. „Opłata manipulacyjna za małe zamówienie”, „Dopłata za delikatne opakowanie”).
    - **Status:** Włącz lub wyłącz zasadę.
    - **Priorytet:** Jeśli wiele zasad może dotyczyć tego samego koszyka, najpierw zostanie oceniona ta z najwyższym priorytetem (najniższa liczba). Jeśli włączono „Zatrzymaj przetwarzanie dalszych reguł”, zastosowana zostanie tylko reguła o najwyższym priorytecie.
    - **Typ opłaty:**
      - **Stała kwota:** Określona wartość pieniężna (np. 5,00 zł).
      - **Procent od wartości koszyka:** Procent od sumy częściowej koszyka (np. 2%).
      - **Procent od produktów w koszyku:** Procent od całkowitej ceny produktów w koszyku (bez wysyłki/podatków).
    - **Wartość opłaty:** Rzeczywista kwota lub procent w zależności od wybranego typu opłaty.
    - **Etykieta opłaty (wielojęzyczna):** Tekst, który klienci zobaczą w swoim koszyku i podsumowaniu zamówienia (np. „Opłata manipulacyjna”, „Opłata za usługę”). Może być przetłumaczony na różne języki.
    - **Kreator warunków:** To jest rdzeń zasady. Możesz budować złożone reguły za pomocą grup „AND” / „OR”, łącząc warunki takie jak:
      - Wartość koszyka (całkowita, suma częściowa, ilość)
      - Grupa klientów
      - Kraj, województwo lub strefa
      - Przewoźnik
      - Konkretne produkty w koszyku (według ID, kategorii, producenta, dostawcy)
      - Metoda płatności
      - I wiele innych…
    - **Zatrzymaj przetwarzanie dalszych reguł:** Jeśli włączone, po zastosowaniu tej zasady, żadne inne zasady o niższym priorytecie nie będą oceniane dla tego samego koszyka.
  - **Edytuj/Usuń zasady:** Modyfikuj istniejące zasady lub usuwaj je.
  - **Duplikuj zasadę:** Szybko utwórz nową zasadę na podstawie istniejącej, oszczędzając czas podczas tworzenia podobnych reguł.
- **Efekt zmian:** Dodawanie, edytowanie lub usuwanie zasad bezpośrednio wpływa na to, które opłaty są stosowane do koszyków klientów i w jakich okolicznościach. Nieprawidłowo skonfigurowane zasady mogą prowadzić do nieoczekiwanych opłat lub utraconych przychodów.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1.  Zacznij od zdefiniowania najczęstszych scenariuszy opłat.
  2.  Użyj przycisku „Dodaj nową zasadę”, aby utworzyć każdą regułę.
  3.  Starannie konstruuj warunki za pomocą kreatora. Dokładnie przetestuj za pomocą symulatora (jeśli dostępny, patrz dziennik audytu), aby upewnić się, że działają zgodnie z oczekiwaniami.
  4.  Ustaw odpowiednie priorytety, zwłaszcza jeśli masz nakładające się warunki.
  5.  Regularnie przeglądaj i aktualizuj zasady w miarę zmian potrzeb biznesowych lub promocji.

#### 2.2.3 Dziennik audytu (Panel administracyjny > Conditional Order Fees > Dziennik audytu)

Dziennik audytu zawiera szczegółową historię każdego przypadku, w którym moduł ocenił koszyk i zastosował (lub nie zastosował) opłatę. Jest to nieocenione narzędzie do rozwiązywania problemów i zrozumienia, dlaczego niektóre opłaty zostały lub nie zostały naliczone.

- **Nazwa ekranu i lokalizacja w menu:** **Conditional Order Fees > Dziennik audytu** (znajduje się pod główną pozycją menu „Conditional Order Fees” w lewym pasku bocznym).
- **Dostępne działania i ustawienia:**
  - **Wpisy dziennika:** Tabela pokazująca każde zdarzenie oceny, w tym:
    - Data i godzina
    - Klient (jeśli zalogowany)
    - ID koszyka
    - Zastosowana zasada (jeśli istnieje)
    - Kwota opłaty (jeśli zastosowana)
    - Status (np. „Opłata zastosowana”, „Brak opłaty”, „Zasada nie spełniona”)
  - **Widok szczegółowy:** Kliknij wpis dziennika, aby zobaczyć pełne zestawienie, jak warunki zostały ocenione dla tego konkretnego koszyka, pokazując, które warunki zostały spełnione, a które nie. Jest to jak „symulator” dla przeszłych zdarzeń.
  - **Filtrowanie i wyszukiwanie:** Filtruj wpisy dziennika według daty, klienta, ID koszyka lub zasady, aby szybko znaleźć konkretne zdarzenia.
- **Efekt zmian:** Ten ekran służy do przeglądania i debugowania. Nie dokonuje się tu bezpośrednich zmian, ale dostarcza kluczowych informacji o zachowaniu modułu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1.  Jeśli klient zgłosi nieoczekiwaną opłatę lub brak oczekiwanej opłaty, użyj dziennika audytu, aby zbadać sprawę.
  2.  Filtruj według nazwy klienta lub ID koszyka, aby dokładnie zobaczyć, które zasady zostały ocenione i dlaczego.
  3.  Użyj widoku szczegółowego, aby dokładnie określić, który konkretny warunek spowodował, że zasada została spełniona lub nie.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik do aktywacji/dezaktywacji wszystkich funkcji modułu. |
|  | ID produktu opłaty | Automatycznie generowane ID | Łączy opłaty z ukrytym produktem dla systemu koszyka PrestaShop. Nie zmieniaj, chyba że zostaniesz poinstruowany. |
| **Zasady** | Nazwa zasady | N/A | Wewnętrzna etykieta dla Twojej reguły opłaty. |
|  | Status | Włączony | Aktywuje/dezaktywuje pojedynczą zasadę opłaty. |
|  | Priorytet | 1 (najniższa liczba = najwyższy priorytet) | Określa kolejność oceny, jeśli może zastosować się wiele zasad. |
|  | Typ opłaty | Stała kwota | Wybierz sposób obliczania opłaty (stała, % koszyka, % produktów). |
|  | Wartość opłaty | 0.00 | Kwota lub procent opłaty. |
|  | Etykieta opłaty | „Opłata manipulacyjna” (przykład) | Tekst widoczny dla klienta w koszyku/zamówieniu. |
|  | Kreator warunków | N/A | Zdefiniuj konkretne kryteria (koszyk, klient, produkt itp.), aby opłata została zastosowana. |
|  | Zatrzymaj przetwarzanie dalszych reguł | Nie | Jeśli włączone, zapobiega zastosowaniu zasad o niższym priorytecie, gdy ta zostanie dopasowana. |
| **Dziennik audytu** | (Wszystkie wpisy) | N/A | Zapewnia szczegółową historię ocen opłat do rozwiązywania problemów i monitorowania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem zasadę, ale opłata nie pojawia się w koszyku.**
O1:

-   **Sprawdź status modułu:** Upewnij się, że ustawienie „Włącz moduł” na głównej stronie konfiguracji jest ustawione na TAK.
-   **Sprawdź status zasady:** Upewnij się, że konkretna zasada, której oczekujesz, jest „Włączona” na liście zasad.
-   **Przejrzyj warunki:** Dokładnie sprawdź warunki swojej zasady. Czy wszystkie są rzeczywiście spełnione przez bieżący koszyk? Użyj Dziennika audytu (Conditional Order Fees > Dziennik audytu), aby zobaczyć, jak Twoje warunki zostały ocenione dla koszyka testowego.
-   **ID produktu opłaty:** Sprawdź, czy „ID produktu opłaty” na głównej stronie konfiguracji jest prawidłowe i wskazuje na specjalny produkt utworzony przez moduł.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność) i pamięć podręczną przeglądarki.

**P2: Opłata się wyświetla, ale etykieta lub kwota jest nieprawidłowa.**
O2:

-   **Ustawienia zasady:** Przejdź do konkretnej zasady w „Conditional Order Fees > Zasady” i zweryfikuj ustawienia „Wartość opłaty” i „Etykieta opłaty”. Upewnij się, że etykieta jest poprawnie przetłumaczona na język, który testujesz.
-   **Wiele zasad:** Jeśli potencjalnie może zastosować się wiele zasad, sprawdź ich „Priorytet” i ustawienie „Zatrzymaj przetwarzanie dalszych reguł”. Zasada o wyższym priorytecie może być stosowana zamiast tej, której oczekujesz.

**P3: Czy mogę przetłumaczyć etykietę opłaty na różne języki?**
O3: Tak! Podczas edycji zasady, pole „Etykieta opłaty” będzie zazwyczaj miało selektor języka (ikonę flagi). Kliknij go, aby wprowadzić tłumaczenia dla każdego języka zainstalowanego w Twoim sklepie.

**P4: Co się stanie, jeśli usunę „Produkt opłaty”, którego używa moduł?**
O4: Jeśli usuniesz produkt określony w ustawieniu „ID produktu opłaty”, moduł nie będzie już w stanie dodawać opłat do koszyka. Kluczowe jest, aby nie usuwać tego produktu. Jeśli zostanie przypadkowo usunięty, może być konieczne ponowne zainstalowanie modułu (co go odtworzy) lub ręczne utworzenie nowego ukrytego produktu i zaktualizowanie ustawienia „ID produktu opłaty”.

**P5: Moduł wydaje się spowalniać proces realizacji zamówienia.**
O5: Chociaż moduł jest zoptymalizowany pod kątem wydajności, złożone zasady z wieloma warunkami, zwłaszcza te obejmujące obszerne sprawdzanie produktów, mogą powodować niewielkie obciążenie.

-   **Uprość warunki:** Przejrzyj swoje zasady. Czy można uprościć lub połączyć jakieś warunki?
-   **Ustal priorytety:** Skutecznie używaj ustawień „Priorytet” i „Zatrzymaj przetwarzanie dalszych reguł”, aby zminimalizować liczbę zasad, które wymagają pełnej oceny dla danego koszyka.
-   **Zasoby serwera:** Upewnij się, że Twoje środowisko hostingowe spełnia zalecane specyfikacje PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Conditional Order Fees jest zbudowany zgodnie z wzorcem MVC PrestaShop, w dużym stopniu wykorzystując `ObjectModel` do trwałości danych i solidną architekturę sterowaną zdarzeniami poprzez hooki PrestaShop. Wprowadza wyrafinowany silnik oceny warunków, umożliwiający złożoną, zagnieżdżoną logikę `AND`/`OR` do określania zastosowania opłat. Moduł płynnie integruje się z przepływem przetwarzania koszyka i zamówień, dynamicznie dodając „wirtualny produkt” do koszyka, gdy warunki są spełnione. Interfejsy administracyjne są zbudowane przy użyciu `AdminController` PrestaShop i komponentów `HelperList`/`HelperForm`, z niestandardowym JavaScriptem dla kreatora warunków i symulatora.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `conorderfee/controllers/front/index.php`
  - **Nazwa klasy:** `ConorderfeeIndexModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako rezerwowy lub prosty punkt wejścia, ale podstawowa logika stosowania opłat jest obsługiwana głównie przez hooki, a nie bezpośrednie trasy front-kontrolera. Może być używany do podstawowych informacji o module lub przekierowania, jeśli jest dostępny bezpośrednio.

#### Kontrolery administracyjne Back-Office

- `conorderfee/controllers/admin/AdminconorderfeeAuditLog.php`
  - **Nazwa klasy:** `AdminconorderfeeAuditLogController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Conditional Order Fees > Dziennik audytu
  - **Zarządzana encja:** `ConorderfeeLog` (ORM dla tabeli `ps_conorderfee_log`).
  - **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem dziennika audytu opłat. Używa `HelperList` do renderowania tabeli wpisów dziennika i zapewnia szczegółowe widoki dla poszczególnych wpisów dziennika, pokazując proces oceny warunków.
- `conorderfee/controllers/admin/AdminconorderfeePolicies.php`
  - **Nazwa klasy:** `AdminconorderfeePoliciesController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Conditional Order Fees > Zasady
  - **Zarządzana encja:** `ConorderfeePolicy` (ORM dla tabeli `ps_conorderfee_policy`).
  - **Odpowiedzialność:** Zarządza tworzeniem, edycją, duplikowaniem i usuwaniem zasad opłat. Używa `HelperList` do przeglądu zasad i `HelperForm` do formularza tworzenia/edycji zasad, który zawiera złożony interfejs kreatora warunków.
- `conorderfee/controllers/admin/index.php`
  - **Nazwa klasy:** `ConorderfeeIndexModuleAdminController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Conditional Order Fees > Panel
  - **Zarządzana encja:** N/A (widok panelu)
  - **Odpowiedzialność:** Służy jako główny panel modułu w back office, wyświetlając statystyki i szybkie linki. Jest to domyślny kontroler ładowany po kliknięciu głównej pozycji menu modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `conorderfee/classes/ConorderfeeAdmin.php`
  - **Odpowiedzialność:** Klasa narzędziowa dla funkcji specyficznych dla administratora, potencjalnie obsługująca rejestrację menu, zarządzanie zakładkami i ogólne pomocniki związane z administracją.
- `conorderfee/classes/ConorderfeeAuditLog.php`
  - **Tabela bazy danych:** `ps_conorderfee_log`
  - **Rozszerza ObjectModel:** Tak.
  - **Pola `$definition`:** `id_conorderfee_log`, `id_cart`, `id_order`, `id_customer`, `id_conorderfee_policy`, `fee_amount`, `fee_label`, `conditions_snapshot`, `evaluation_result`, `date_add`.
  - **Kluczowe metody publiczne:** Metody do zapisywania wpisów dziennika, pobierania danych dziennika i potencjalnie formatowania szczegółów dziennika do wyświetlenia.
- `conorderfee/classes/ConorderfeeCartState.php`
  - **Odpowiedzialność:** Klasa pomocnicza do hermetyzacji bieżącego stanu koszyka i powiązanego kontekstu (klient, adres, przewoźnik itp.) do oceny warunków. Zapewnia metody do pobierania różnych właściwości koszyka potrzebnych przez warunki.
- `conorderfee/classes/ConorderfeeCompatibility.php`
  - **Odpowiedzialność:** Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop (np. 1.7 vs. 8.x vs. 9.x), aby zapewnić prawidłowe działanie modułu we wszystkich obsługiwanych wersjach.
- `conorderfee/classes/ConorderfeeCondition.php`
  - **Tabela bazy danych:** `ps_conorderfee_condition`
  - **Rozszerza ObjectModel:** Tak.
  - **Pola `$definition`:** `id_conorderfee_condition`, `id_conorderfee_condition_group`, `type`, `operator`, `value`, `is_inverted`.
  - **Kluczowe metody publiczne:** Reprezentuje pojedynczy warunek w ramach zasady (np. „Całkowita wartość koszyka > 100”). Metody do zapisywania, ładowania i potencjalnie walidacji danych warunku.
- `conorderfee/classes/ConorderfeeConditionEvaluator.php`
  - **Odpowiedzialność:** Podstawowy silnik logiczny do oceny `ConorderfeeConditionTree` względem `ConorderfeeCartState`. Rekurencyjnie przetwarza grupy warunków i poszczególne warunki, aby określić, czy zasada ma zastosowanie.
- `conorderfee/classes/ConorderfeeConditionGroup.php`
  - **Tabela bazy danych:** `ps_conorderfee_condition_group`
  - **Rozszerza ObjectModel:** Tak.
  - **Pola `$definition`:** `id_conorderfee_condition_group`, `id_conorderfee_policy`, `id_parent_group`, `operator` (`AND`/`OR`).
  - **Kluczowe metody publiczne:** Reprezentuje grupę warunków (np. „Warunek A AND (Warunek B OR Warunek C)”). Zarządza swoimi warunkami podrzędnymi i podgrupami.
- `conorderfee/classes/ConorderfeeConditionTree.php`
  - **Odpowiedzialność:** Reprezentuje hierarchiczną strukturę warunków dla zasady (grupa główna, podgrupy, poszczególne warunki). Używana przez `ConorderfeeConditionEvaluator`.
- `conorderfee/classes/ConorderfeeContext.php`
  - **Odpowiedzialność:** Wrapper wokół obiektu `Context` PrestaShop, potencjalnie dodający dane kontekstowe specyficzne dla modułu lub upraszczający dostęp do wspólnych elementów kontekstu.
- `conorderfee/classes/ConorderfeeDashboard.php`
  - **Odpowiedzialność:** Dostarcza dane i logikę dla widoku panelu modułu, pobierając statystyki i ostatnie wpisy dziennika.
- `conorderfee/classes/ConorderfeeEngine.php`
  - **Odpowiedzialność:** Centralny orkiestrator logiki front-office modułu. Podłącza się do różnych zdarzeń PrestaShop, pobiera aktywne zasady, używa `ConorderfeeConditionEvaluator` do sprawdzania warunków i dodaje produkt opłaty do koszyka, jeśli ma to zastosowanie.
- `conorderfee/classes/ConorderfeeFeeProduct.php`
  - **Odpowiedzialność:** Zarządza specjalnym „produktem opłaty”, który reprezentuje opłatę warunkową w koszyku. Obsługuje jego tworzenie podczas instalacji i zapewnia, że jest on prawidłowo skonfigurowany jako wirtualny, niewidoczny produkt.
- `conorderfee/classes/ConorderfeeListRenderer.php`
  - **Odpowiedzialność:** Klasa pomocnicza do renderowania list w back office, potencjalnie rozszerzająca `HelperList` lub zapewniająca niestandardową logikę renderowania kolumn.
- `conorderfee/classes/ConorderfeeLog.php`
  - **Tabela bazy danych:** `ps_conorderfee_log` (to samo co `ConorderfeeAuditLog`, prawdopodobnie alias lub klasa bazowa)
  - **Rozszerza ObjectModel:** Tak.
  - **Pola `$definition`:** Takie same jak `ConorderfeeAuditLog`.
  - **Kluczowe metody publiczne:** Metody do logowania zdarzeń, przechowywania wyników oceny i pobierania danych dziennika.
- `conorderfee/classes/ConorderfeePolicy.php`
  - **Tabela bazy danych:** `ps_conorderfee_policy`
  - **Rozszerza ObjectModel:** Tak.
  - **Pola `$definition`:** `id_conorderfee_policy`, `name`, `active`, `priority`, `fee_type`, `fee_value`, `fee_label`, `stop_further_rules`, `date_add`, `date_upd`.
  - **Kluczowe metody publiczne:** Reprezentuje kompletną zasadę opłaty. Metody do zapisywania, ładowania i zarządzania powiązanymi `ConorderfeeConditionGroup`ami.
- `conorderfee/classes/ConorderfeePolicyDuplicator.php`
  - **Odpowiedzialność:** Obsługuje logikę duplikowania istniejącej zasady opłaty, w tym wszystkich powiązanych warunków i grup, w celu usprawnienia tworzenia zasad.
- `conorderfee/classes/ConorderfeePreset.php`
  - **Odpowiedzialność:** Zarządza predefiniowanymi typami warunków i operatorami dla kreatora warunków (np. „Całkowita wartość koszyka”, „Grupa klientów”, „jest większa niż”, „jest jednym z”).
- `conorderfee/classes/ConorderfeeRule.php`
  - **Odpowiedzialność:** Prawdopodobnie abstrakcyjna lub bazowa klasa do definiowania reguł, lub specyficzny typ reguły w kreatorze warunków.
- `conorderfee/classes/ConorderfeeTreeRepository.php`
  - **Odpowiedzialność:** Zarządza trwałością i pobieraniem struktury drzewa warunków (zasady, grupy, warunki) z bazy danych.
- `conorderfee/classes/index.php`
  - **Odpowiedzialność:** Pusty plik, zazwyczaj używany do zapobiegania listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

- `conorderfee/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back-office.
  - **Opis:** Zapewnia funkcjonalność autouzupełniania dla pól wyszukiwania, prawdopodobnie używaną do wybierania produktów, kategorii, klientów itp. w kreatorze warunków.
- `conorderfee/lib/searchTool/views/views/js/autocomplete.js`
  - **Zakres:** Back-office.
  - **Opis:** Duplikat powyższego, prawdopodobnie błąd ścieżki lub plik dziedziczony.
- `conorderfee/views/js/adminConditionBuilder.js`
  - **Zakres:** Back-office (`AdminconorderfeePoliciesController`).
  - **Opis:** Podstawowy JavaScript dla interaktywnego interfejsu kreatora warunków. Obsługuje dodawanie/usuwanie warunków i grup, zarządzanie logiką `AND`/`OR`, dynamiczne ładowanie typów warunków i operatorów oraz aktualizowanie interfejsu użytkownika na podstawie danych wejściowych użytkownika.
- `conorderfee/views/js/adminConorderfeeDashboard.js`
  - **Zakres:** Back-office (`AdminconorderfeeDashboardController`).
  - **Opis:** JavaScript dla panelu, potencjalnie obsługujący aktualizacje AJAX dla statystyk, renderowanie wykresów lub interaktywne elementy na panelu.
- `conorderfee/views/js/adminConorderfeeSearchTool.js`
  - **Zakres:** Back-office.
  - **Opis:** Integruje narzędzie wyszukiwania autouzupełniania (z `lib/searchTool`) z różnymi formularzami administracyjnymi, w szczególności do wybierania encji w warunkach.
- `conorderfee/views/js/adminConorderfeeSimulator.js`
  - **Zakres:** Back-office (prawdopodobnie na stronie edycji zasad lub w dzienniku audytu).
  - **Opis:** Zapewnia narzędzie do oceny warunków w czasie rzeczywistym lub symulacji w back office, umożliwiając administratorom testowanie zasad w hipotetycznych scenariuszach koszyka bez składania prawdziwego zamówienia.
- `conorderfee/views/js/adminPolicyRules.js`
  - **Zakres:** Back-office (`AdminconorderfeePoliciesController`).
  - **Opis:** Obsługuje ogólne interakcje JavaScript na stronach listy i edycji zasad, takie jak włączanie/wyłączanie zasad, obsługa duplikacji i zarządzanie ogólnym formularzem zasad.
- `conorderfee/views/js/checkout.js`
  - **Zakres:** Front-office.
  - **Opis:** Ten skrypt prawdopodobnie monitoruje zmiany w koszyku podczas procesu realizacji zamówienia (np. aktualizacje ilości, wybór przewoźnika) i wyzwala wywołania AJAX w celu ponownej oceny opłat, zapewniając, że suma koszyka jest zawsze dokładna. Może również aktualizować wyświetlanie pozycji opłaty.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `conorderfee/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Back-office (Admin).
  - **Opis:** Style dla pól wyszukiwania autouzupełniania i ich sugestii rozwijanych.
- `conorderfee/lib/searchTool/views/views/css/autocomplete.css`
  - **Zakres:** Back-office (Admin).
  - **Opis:** Duplikat powyższego, prawdopodobnie błąd ścieżki lub plik dziedziczony.
- `conorderfee/views/css/admin_conorderfee.css`
  - **Zakres:** Back-office (Admin).
  - **Opis:** Ogólne style dla interfejsów back-office modułu, w tym panelu, listy zasad, dziennika audytu, a zwłaszcza złożonego kreatora warunków, zapewniając spójny i przyjazny dla użytkownika układ.
- `conorderfee/views/css/front.css`
  - **Zakres:** Front-office (Klient).
  - **Opis:** Minimalne style dla sposobu wyświetlania pozycji opłaty w podsumowaniu koszyka i na stronach realizacji zamówienia, zapewniające wizualną integrację z motywem sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

- `conorderfee/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Wyjście:** Wyświetla informacje o zastosowanych opłatach warunkowych w widoku zamówienia w Panelu administracyjnym PrestaShop, umożliwiając administratorom sprawdzenie, które zasady zostały zastosowane do konkretnego zamówienia.

#### Szablony administracyjne (`views/templates/admin/`)

- `conorderfee/lib/searchTool/views/scripts.tpl`
  - **Wyjście:** Zawiera niezbędne JavaScript i CSS dla narzędzia wyszukiwania w back office.
- `conorderfee/lib/searchTool/views/views/scripts.tpl`
  - **Wyjście:** Duplikat powyższego, prawdopodobnie błąd ścieżki lub plik dziedziczony.
- `conorderfee/views/templates/admin/auditPreview.tpl`
  - **Wyjście:** Renderuje szczegółowy widok pojedynczego wpisu dziennika audytu, pokazując pełny proces oceny warunków.
- `conorderfee/views/templates/admin/dashboard.tpl`
  - **Wyjście:** Główny widok panelu modułu, wyświetlający statystyki i szybkie linki.
- `conorderfee/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Wyjście:** Niestandardowy szablon dla przycisku akcji „duplikuj” w widokach `HelperList`, specjalnie dla zasad.
- `conorderfee/views/templates/admin/policiesPreview.tpl`
  - **Wyjście:** Renderuje podgląd lub podsumowanie zasady, potencjalnie używane w dzienniku audytu lub symulatorze.
- `conorderfee/views/templates/admin/policyConditionBuilder.tpl`
  - **Wyjście:** Złożona struktura HTML dla interaktywnego interfejsu kreatora warunków używanego podczas tworzenia lub edycji zasady.
- `conorderfee/views/templates/admin/policyRuleCard.tpl`
  - **Wyjście:** Renderuje pojedynczą regułę lub warunek w kreatorze warunków, zazwyczaj wizualną kartę lub blok.
- `conorderfee/views/templates/admin/policyRulesTable.tpl`
  - **Wyjście:** Renderuje tabelę zasad w widoku listy `AdminconorderfeePolicies`.
- `conorderfee/views/templates/admin/scopeSelector.tpl`
  - **Wyjście:** Szablon do wyboru zakresu warunku (np. „Koszyk”, „Produkt”, „Klient”), używany w kreatorze warunków.

#### Szablony front-office (`views/templates/front/`)

- `conorderfee/controllers/front/index.php` (Brak konkretnego pliku .tpl na liście, prawdopodobnie obsługuje wyjście bezpośrednio lub przekierowuje)

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

- `ps_conorderfee_policy`: Przechowuje główne definicje zasad opłat (nazwa, status aktywności, typ opłaty, wartość, etykieta, priorytet).
- `ps_conorderfee_condition_group`: Przechowuje hierarchiczną strukturę grup warunków (logika AND/OR) w ramach każdej zasady.
- `ps_conorderfee_condition`: Przechowuje poszczególne warunki (typ, operator, wartość) powiązane z grupami warunków.
- `ps_conorderfee_log`: Przechowuje ścieżkę audytu każdego razu, gdy opłata została oceniona, w tym szczegóły koszyka, zastosowaną zasadę, kwotę opłaty i migawkę wyniku oceny.
- `ps_configuration`: Przechowuje wartości konfiguracyjne specyficzne dla modułu, takie jak `CONORDERFEE_ENABLED` i `CONORDERFEE_FEE_PRODUCT_ID`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Nie jest wyraźnie wymieniony w informacjach o module, ale często używany do ładowania CSS/JS front-office. |
| `displayBeforeCarrier` | Przed wyborem przewoźnika na stronie realizacji zamówienia. | Potencjalnie używany do ponownej oceny opłat, jeśli wybór przewoźnika wpływa na warunki. |
| `actionObjectProductInCartDeleteBefore` | Przed usunięciem produktu z koszyka. | Ponowna ocena opłat w celu dostosowania, jeśli usunięty produkt był częścią warunku. |
| `actionPresentCart` | Gdy dane koszyka są prezentowane w front-office. | **KRYTYCZNE:** Główny hook do wstrzykiwania pozycji opłaty do podsumowania koszyka. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany, przed jego zawartością. | Ładuje CSS i JavaScript back-office dla interfejsów administracyjnych modułu. |
| `actionPresentProductListing` | Gdy prezentowane są listy produktów. | Nie jest bezpośrednio związane z opłatami, ale może być używane do wskaźników opłat specyficznych dla produktu. |
| `actionValidateOrderBefore` | Tuż przed zatwierdzeniem zamówienia. | Ostateczne sprawdzenie i zastosowanie opłat w celu zapewnienia prawidłowej sumy zamówienia. |
| `actionGetProductPropertiesAfter` | Po pobraniu właściwości produktu. | Potencjalnie używany do identyfikacji konkretnych produktów, które wyzwalają opłaty. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w Panelu administracyjnym. | Wyświetla informacje o zastosowanych opłatach dla konkretnego zamówienia. |
| `actionFrontControllerInitAfter` | Po zainicjowaniu kontrolera front-office. | Ogólna inicjalizacja front-office, potencjalnie ustawiająca kontekst do oceny opłat. |
| `actionPresentProduct` | Gdy prezentowany jest pojedynczy produkt. | Podobnie jak `actionPresentProductListing`. |
| `actionPresentCartProduct` | Gdy prezentowany jest produkt w koszyku. | Umożliwia modyfikację danych produktu w koszyku, potencjalnie do wyświetlania związanego z opłatami. |
| `actionProductPriceCalculation` | Podczas obliczania ceny produktu. | Zapewnia, że cena produktu opłaty jest prawidłowo nadpisywana przez obliczoną opłatę. |
| `actionFrontControllerSetVariables` | Przed przypisaniem zmiennych Smarty w kontrolerze front-office. | Przekazuje dane związane z opłatami do szablonów front-office. |
| `actionCartSave` | Po zapisaniu koszyka (np. zmiana ilości, dodanie/usunięcie produktu). | **KRYTYCZNE:** Wyzwala główną logikę oceny opłat za każdym razem, gdy zmienia się zawartość koszyka. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Loguje ostateczne zastosowanie opłaty i wiąże ją z nowym ID zamówienia. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia dla programistów, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Zawsze upewnij się, że pobierasz najnowszą wersję kompatybilną z Twoją instalacją PrestaShop.
