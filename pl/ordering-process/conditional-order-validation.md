---
title: "Warunkowa Walidacja Zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Warunkowa Walidacja Zamówień od MyPresta.eu."
sidebar:
  label: "Warunkowa Walidacja Zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Conditional Order Validation na MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-validation.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/conditional-order-validation/)
>
> ---


# Warunkowa Walidacja Zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj > Warunkowa Walidacja Zamówień)

Jest to główny punkt wejścia dla globalnych ustawień modułu.

- **Lokalizacja w menu:** Panel Administracyjny > Moduły > Menedżer modułów > Warunkowa Walidacja Zamówień > Konfiguruj

#### 2.1.1 Ustawienia ogólne

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Włącz Warunkową Walidację Zamówień** | TAK | **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu. Jeśli jest wyłączony, żadna z Twoich zdefiniowanych zasad nie będzie aktywna, a klienci będą mogli zrealizować zamówienie bez żadnych ograniczeń ze strony tego modułu. **Efekt zmiany tego ustawienia:** *Po włączeniu:* Moduł rozpocznie ocenę wszystkich aktywnych zasad, które utworzyłeś. Jeśli koszyk naruszy zasadę, klient zobaczy ostrzeżenia lub zostanie zablokowany przed realizacją zamówienia zgodnie z ustawieniami Twojej zasady. *Po wyłączeniu:* Moduł staje się nieaktywny. Żadne zasady nie są sprawdzane, a żadne komunikaty nie są wyświetlane. **Zalecana wartość:** TAK (po skonfigurowaniu zasad). **Scenariusz dla sprzedawcy:** Włącz to po skonfigurowaniu kilku pierwszych zasad i przetestowaniu ich za pomocą symulatora. |
| **Wyświetlaj komunikaty walidacji na** | Koszyk i Realizacja zamówienia | **Co robi to ustawienie:** Kontroluje, gdzie wyświetlane są komunikaty ostrzegawcze lub blokujące modułu dla klienta. **Efekt zmiany tego ustawienia:** *Po ustawieniu na „Koszyk i Realizacja zamówienia”:* Komunikaty będą pojawiać się zarówno na stronie koszyka, jak i podczas różnych etapów procesu realizacji zamówienia. Zapewnia to maksymalną widoczność i wczesną informację zwrotną dla klienta. *Po ustawieniu na „Tylko koszyk”:* Komunikaty będą pojawiać się tylko na stronie koszyka. Klienci mogą przejść dalej w procesie realizacji zamówienia, zanim zostaną zablokowani, jeśli zignorują ostrzeżenie w koszyku. *Po ustawieniu na „Tylko realizacja zamówienia”:* Komunikaty będą pojawiać się tylko podczas procesu realizacji zamówienia. Klienci nie zobaczą ostrzeżeń na stronie koszyka, co potencjalnie może prowadzić do frustracji później w procesie. **Zalecana wartość:** Koszyk i Realizacja zamówienia. **Scenariusz dla sprzedawcy:** Dla najlepszego doświadczenia klienta, wyświetlaj komunikaty wcześnie i często (Koszyk i Realizacja zamówienia), aby klienci mogli naprawić swój koszyk, zanim zainwestują czas w proces realizacji zamówienia. |
| **Zezwól na realizację zamówienia z ostrzeżeniami** | NIE | **Co robi to ustawienie:** Określa, czy klienci mogą kontynuować realizację zamówienia, nawet jeśli ich koszyk wyzwala zasadę „ostrzegawczą” (w przeciwieństwie do zasady „blokującej”). **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Jeśli zasada jest ustawiona na „Ostrzeżenie”, klient zobaczy komunikat ostrzegawczy, ale nadal będzie mógł kliknąć przycisk „Przejdź do realizacji zamówienia” lub „Złóż zamówienie”. Jest to przydatne w przypadku łagodnych rekomendacji lub niekrytycznych problemów. *Po wyłączeniu (NIE):* Jeśli zasada jest ustawiona na „Ostrzeżenie”, klient zobaczy komunikat ostrzegawczy, a przycisk „Przejdź do realizacji zamówienia” lub „Złóż zamówienie” zostanie wyłączony, dopóki warunek ostrzeżenia nie zostanie rozwiązany. To skutecznie sprawia, że „ostrzeżenia” zachowują się jak „blokady” na etapie realizacji zamówienia. **Zalecana wartość:** NIE (chyba że masz bardzo specyficzne „łagodne” ostrzeżenia). **Scenariusz dla sprzedawcy:** Jeśli masz zasadę taką jak „Klienci kupujący za ponad 100 $ otrzymują darmową wysyłkę” i chcesz *sugerować* im dodanie więcej do koszyka, ale nie *zmuszać* ich do tego, możesz to włączyć. Jednak dla większości zasad biznesowych będziesz chciał to wyłączyć, aby zapewnić zgodność. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł wprowadza dwie nowe, potężne sekcje w menu Panelu Administracyjnego PrestaShop: „Zasady” i „Dziennik audytu”.

#### 2.2.1 Zasady (Panel Administracyjny > Warunkowa Walidacja Zamówień > Zasady)

Tutaj definiujesz, zarządzasz i aktywujesz swoje reguły warunkowej walidacji zamówień. Każda „zasada” to zestaw warunków, które, jeśli zostaną spełnione, zablokują lub ostrzegą klienta.

- **Lokalizacja w menu:** Panel Administracyjny > Warunkowa Walidacja Zamówień > Zasady
- **Dostępne działania i ustawienia:**

  - **Lista zasad:** Tabela wyświetlająca wszystkie utworzone zasady, pokazująca ich nazwę, status (włączona/wyłączona), typ (blokująca/ostrzegawcza) i priorytet.
  - **Dodaj nową zasadę:** Kliknij ten przycisk, aby utworzyć nową zasadę walidacji.
  - **Edytuj zasadę:** Modyfikuj nazwę, warunki, komunikaty i status istniejącej zasady.
  - **Duplikuj zasadę:** Szybko utwórz kopię istniejącej zasady, aby użyć jej jako punktu wyjścia dla nowej. Oszczędza to czas podczas tworzenia podobnych reguł.
  - **Włącz/Wyłącz zasadę:** Przełącz aktywny status zasady bez jej usuwania.
  - **Usuń zasadę:** Usuń zasadę na stałe.
  - **Symulator:** Kluczowe narzędzie (często znajdujące się na ekranie tworzenia/edycji zasad lub jako dedykowana zakładka), które pozwala przetestować zasady z symulowanym koszykiem, zanim zostaną uruchomione. Pomaga to zapobiec niezamierzonemu blokowaniu legalnych zamówień.
- **Formularz tworzenia/edycji zasad:**

  - **Nazwa zasady:** Opisowa nazwa dla Twojej zasady (np. „Minimalna wartość zamówienia dla hurtu”, „Ograniczenie wiekowe dla alkoholu”).
  - **Status:** Włącz lub wyłącz zasadę.
  - **Typ zasady:**
    - **Blokująca:** Jeśli warunki są spełnione, klient jest *uniemożliwiony* w realizacji zamówienia.
    - **Ostrzegawcza:** Jeśli warunki są spełnione, klient widzi komunikat ostrzegawczy, ale *może lub nie może* kontynuować, w zależności od globalnego ustawienia „Zezwól na realizację zamówienia z ostrzeżeniami”.
  - **Priorytet:** Jeśli wiele zasad jest aktywnych i wyzwalanych, to określa kolejność wyświetlania komunikatów lub która zasada ma pierwszeństwo (niższa liczba = wyższy priorytet).
  - **Kreator warunków:** To jest rdzeń zasady. Zbudujesz drzewo warunków, używając logiki „AND” / „OR”.
    - **Typy warunków:** Zazwyczaj możesz wybierać z szerokiej gamy warunków:
      - **Na poziomie koszyka:** Całkowita wartość koszyka, całkowita ilość przedmiotów, liczba unikalnych produktów.
      - **Na poziomie produktu:** Konkretne identyfikatory produktów, kategorie, producenci, dostawcy, atrybuty produktów, minimalna/maksymalna ilość konkretnego produktu.
      - **Na poziomie klienta:** Grupa klienta, konkretny identyfikator klienta, kraj klienta.
      - **Na poziomie wysyłki:** Wybrany przewoźnik, strefa wysyłki.
    - **Operatory:** (np. „jest równe”, „jest większe niż”, „zawiera”, „nie jest”).
    - **Wartości:** Konkretny punkt danych do porównania (np. „100” dla minimalnej wartości, „Elektronika” dla kategorii).
  - **Wiadomość dla klienta:** Wiadomość wyświetlana klientowi w front office, gdy ta zasada jest wyzwalana. Uczyń ją jasną, pomocną i możliwą do działania (np. „Twój koszyk musi zawierać co najmniej 5 sztuk produktu X, aby kontynuować.”).
  - **Wiadomość dla administratora (opcjonalnie):** Wewnętrzna notatka dla Ciebie lub innych administratorów.
- **Wpływ zmian:**

  - Dodawanie/modyfikowanie zasady bezpośrednio wpływa na doświadczenie realizacji zamówienia w front office dla klientów.
  - Włączenie zasady aktywuje jej reguły. Wyłączenie jej dezaktywuje je bez usuwania.
  - Symulator pozwala testować zmiany bez wpływu na żywych klientów.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

  1.  Zidentyfikuj regułę biznesową, którą chcesz egzekwować (np. „Klienci hurtowi muszą zamówić za minimum 500 $”).
  2.  Przejdź do „Zasady” i kliknij „Dodaj nową zasadę”.
  3.  Nadaj jej jasną nazwę, ustaw ją na „Blokująca” i zdefiniuj warunki (np. „Grupa klienta JEST Hurtowa” ORAZ „Całkowita wartość koszyka JEST WIĘKSZA LUB RÓWNA 500”).
  4.  Napisz pomocną wiadomość dla klienta (np. „Zamówienia hurtowe wymagają minimalnej wartości 500 $. Proszę dodać więcej produktów do koszyka.”).
  5.  Użyj „Symulatora”, aby przetestować różne scenariusze (np. klient hurtowy z koszykiem za 400 $, klient detaliczny z koszykiem za 400 $, klient hurtowy z koszykiem za 600 $).
  6.  Po zadowoleniu włącz zasadę.

#### 2.2.2 Dziennik audytu (Panel Administracyjny > Warunkowa Walidacja Zamówień > Dziennik audytu)

Dziennik audytu zapewnia historyczny zapis, kiedy zasady zostały wyzwolone, przez kogo i jaki był wynik. Jest to nieocenione narzędzie do rozwiązywania problemów i zrozumienia zachowań klientów.

- **Lokalizacja w menu:** Panel Administracyjny > Warunkowa Walidacja Zamówień > Dziennik audytu
- **Dostępne działania i ustawienia:**

  - **Lista logów:** Tabela pokazująca wpisy dla każdego przypadku, gdy zasada została oceniona i wyzwolona.
  - **Kolumny:**
    - **Data/Godzina:** Kiedy zdarzenie miało miejsce.
    - **Klient:** Klient, który wyzwolił zasadę (jeśli zalogowany).
    - **ID koszyka:** ID koszyka zakupowego.
    - **Nazwa zasady:** Nazwa zasady, która została wyzwolona.
    - **Typ zasady:** Czy była to zasada „Blokująca” czy „Ostrzegawcza”.
    - **Wiadomość:** Wiadomość wyświetlona klientowi.
    - **Status:** Czy zamówienie zostało ostatecznie zatwierdzone, zablokowane czy ostrzeżone.
  - **Filtrowanie/Wyszukiwanie:** Standardowe filtrowanie list PrestaShop pozwala wyszukiwać według klienta, zasady, zakresu dat itp.
  - **Wyświetl szczegóły koszyka:** Często można kliknąć ID koszyka, aby sprawdzić zawartość koszyka w momencie wyzwolenia zasady.
- **Wpływ zmian:** Ten ekran służy wyłącznie do przeglądania i audytu; nie można tu wprowadzać zmian. Jest to zapis zdarzeń.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

  - Jeśli klient zgłasza problem z realizacją zamówienia, sprawdź Dziennik audytu, aby zobaczyć, czy jakiekolwiek zasady zostały wyzwolone dla jego koszyka. Może to szybko zidentyfikować, czy zasada jest błędnie skonfigurowana, czy też klient po prostu nie spełnił wymagań.
  - Okresowo przeglądaj dziennik, aby zrozumieć, które zasady są najczęściej wyzwalane i czy potrzebne są jakieś korekty.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| **Konfiguracja modułu** | Włącz Warunkową Walidację Zamówień | TAK | Główny przełącznik funkcjonalności modułu. |
| **Konfiguracja modułu** | Wyświetlaj komunikaty walidacji na | Koszyk i Realizacja zamówienia | Gdzie pojawiają się komunikaty dla klienta (koszyk, realizacja zamówienia lub oba). |
| **Konfiguracja modułu** | Zezwól na realizację zamówienia z ostrzeżeniami | NIE | Określa, czy zasady „ostrzegawcze” blokują realizację zamówienia, czy tylko informują. |
| **Zasady (Admin)** | Nazwa zasady | N/A | Opisowy identyfikator Twojej reguły. |
| **Zasady (Admin)** | Status | Włączona | Aktywuje lub dezaktywuje konkretną zasadę. |
| **Zasady (Admin)** | Typ zasady | Blokująca / Ostrzegawcza | Definiuje, czy zasada uniemożliwia realizację zamówienia, czy tylko wyświetla komunikat. |
| **Zasady (Admin)** | Priorytet | N/A | Kolejność oceny/wyświetlania dla wielu wyzwolonych zasad. |
| **Zasady (Admin)** | Kreator warunków | N/A | Definiuje logiczne reguły, kiedy zasada jest wyzwalana. |
| **Zasady (Admin)** | Wiadomość dla klienta | N/A | Wiadomość wyświetlana klientowi, gdy zasada jest wyzwalana. |
| **Zasady (Admin)** | Wiadomość dla administratora | N/A | Wewnętrzne notatki dla administratorów. |
| **Dziennik audytu (Admin)** | (Wszystkie kolumny) | N/A | Rejestruje wszystkie przypadki wyzwolenia zasad do przeglądu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje zasady nie działają, lub klienci nadal realizują zamówienia, mimo że nie powinni.**
O:

1.  **Czy moduł jest włączony?** Sprawdź „Włącz Warunkową Walidację Zamówień” w głównej konfiguracji modułu.
2.  **Czy konkretne zasady są włączone?** Przejdź do „Zasady” i upewnij się, że kolumna „Status” dla Twoich zasad jest ustawiona na „Włączona”.
3.  **Sprawdź typ zasady:** Czy jest ustawiona na „Blokująca” czy „Ostrzegawcza”? Jeśli „Ostrzegawcza”, sprawdź globalne ustawienie „Zezwól na realizację zamówienia z ostrzeżeniami”. Jeśli jest włączone, klienci mogą ominąć ostrzeżenia.
4.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
5.  **Symulator:** Użyj wbudowanego „Symulatora” na ekranie tworzenia/edycji zasad, aby przetestować swoje warunki w różnych scenariuszach koszyka. Jest to najskuteczniejszy sposób debugowania.
6.  **Dziennik audytu:** Sprawdź „Dziennik audytu”, aby zobaczyć, czy Twoje zasady w ogóle są wyzwalane i jaki był wynik.

**P: Komunikaty ostrzegawcze/blokujące nie wyglądają dobrze w moim motywie.**
O: Moduł wykorzystuje standardowe style PrestaShop, gdzie to możliwe, ale niestandardowe motywy mogą wymagać nadpisania lub specyficznych dostosowań CSS.

1.  **Podstawowy CSS:** CSS modułu jest zaprojektowany tak, aby był ogólny. Jeśli Twój motyw ma bardzo specyficzne style, możesz potrzebować webmastera, aby dodał niestandardowy CSS do pliku `custom.css` Twojego motywu, aby dopasować go do Twojej marki.
2.  **Nadpisywanie szablonów:** Zaawansowani użytkownicy mogą nadpisać pliki szablonów modułu (np. `views/templates/hook/validation_banner.tpl`) w swoim motywie, aby całkowicie dostosować strukturę HTML i wygląd.

**P: Czy mogę przetłumaczyć komunikaty na różne języki?**
O: Tak, wszystkie komunikaty dla klienta, które definiujesz w swoich zasadach, są tłumaczone.

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu Administracyjnym.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw i wybierz język.
3.  Znajdź moduł „Warunkowa Walidacja Zamówień” i przetłumacz tam komunikaty zasad.

**P: Utworzyłem zasadę, ale blokuje ona *wszystkie* zamówienia, nawet te prawidłowe.**
O: Zazwyczaj oznacza to, że Twoje warunki są zbyt ogólne lub nieprawidłowo skonfigurowane.

1.  **Przejrzyj warunki:** Dokładnie przeczytaj każdy warunek w swojej zasadzie. Upewnij się, że operatory (np. „JEST”, „NIE JEST”, „WIĘKSZE NIŻ”) i wartości są poprawne.
2.  **Logika AND/OR:** Zwróć szczególną uwagę na to, czy używasz „AND” czy „OR” między grupami warunków. „AND” oznacza, że *wszystkie* warunki muszą być prawdziwe; „OR” oznacza, że *dowolny* jeden warunek musi być prawdziwy. Częstym błędem jest użycie „OR”, gdy zamierzone jest „AND”, lub odwrotnie.
3.  **Użyj symulatora:** To jest kluczowe. Symuluj różne „dobre” i „złe” koszyki, aby dokładnie zobaczyć, dlaczego zasada jest wyzwalana.

**P: Jak obsługiwać konfiguracje wielosklepowe?**
O: Moduł jest zaprojektowany tak, aby był kompatybilny z wieloma sklepami. Podczas tworzenia lub edytowania zasad powinieneś zobaczyć opcję wyboru, do których sklepów zasada ma zastosowanie. Upewnij się, że Twoje zasady są przypisane do prawidłowych kontekstów sklepu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu Warunkowa Walidacja Zamówień dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł Warunkowa Walidacja Zamówień podąża za solidnym wzorcem MVC (Model-View-Controller) w ramach frameworka PrestaShop. W dużym stopniu wykorzystuje `ObjectModel` do trwałości danych (zasady, dzienniki audytu), niestandardowe kontrolery administracyjne do zarządzania tymi encjami oraz zaawansowany silnik oceny warunków do przetwarzania reguł w czasie rzeczywistym. Moduł integruje się głęboko z hakami walidacji zamówień i prezentacji koszyka, zapewniając egzekwowanie zasad na krytycznych etapach podróży klienta. Kluczowym aspektem jest `ConordervalidEngine`, który orkiestruje ocenę obiektów `ConordervalidPolicy`, z których każdy zawiera `ConordervalidConditionTree`.

### 4.2 Kontrolery (`controllers/`)

#### 4.2.1 Kontrolery Front-Office

- `conordervalid/controllers/front/index.php`
  - **Nazwa klasy:** `ConordervalidIndexModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Ten kontroler może służyć jako ogólny punkt wejścia lub obsługiwać specyficzne żądania AJAX z front-office związane z walidacją koszyka lub wyświetlaniem komunikatów. Biorąc pod uwagę jego nazwę, może to być rezerwowy lub prosty kontroler wyświetlania.
- `conordervalid/controllers/front/validate.php`
  - **Nazwa klasy:** `ConordervalidValidateModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Ten kontroler jest kluczowy dla walidacji koszyka w czasie rzeczywistym. Prawdopodobnie obsługuje żądania AJAX ze stron koszyka lub realizacji zamówienia, aby sprawdzić, czy bieżący stan koszyka narusza jakiekolwiek aktywne zasady. Zwracałby odpowiedzi JSON wskazujące, czy koszyk jest prawidłowy, wszelkie komunikaty ostrzegawcze lub powody blokowania. To tutaj zostałby wywołany `ConordervalidEngine`.

#### 4.2.2 Kontrolery administracyjne Back-Office

- `conordervalid/controllers/admin/AdminconordervalidAuditLog.php`
  - **Nazwa klasy:** `AdminconordervalidAuditLogController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Dziennik audytu (w menu Warunkowa Walidacja Zamówień)
  - **Zarządzana encja:** `ConordervalidAuditLog` (mapowana na tabelę `ps_conordervalid_log`)
  - **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem wpisów dziennika audytu. Wykorzystuje `HelperList` do renderowania siatki, umożliwiając administratorom przeglądanie historycznych zapisów wyzwalania zasad.
- `conordervalid/controllers/admin/AdminconordervalidPolicies.php`
  - **Nazwa klasy:** `AdminconordervalidPoliciesController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Zasady (w menu Warunkowa Walidacja Zamówień)
  - **Zarządzana encja:** `ConordervalidPolicy` (mapowana na tabelę `ps_conordervalid_policy`)
  - **Odpowiedzialność:** Jest to główny kontroler do zarządzania zasadami walidacji. Obsługuje operacje CRUD dla zasad, w tym złożony interfejs kreatora warunków. Wykorzystuje `HelperList` do przeglądu zasad i `HelperForm` do tworzenia/edycji zasad, integrując logikę `ConordervalidConditionTree` i `ConordervalidConditionBuilder`.
- `conordervalid/controllers/admin/index.php`
  - **Nazwa klasy:** (Prawdopodobnie proste przekierowanie lub placeholder)
  - **Odpowiedzialność:** Często `index.php` w katalogu kontrolerów jest środkiem bezpieczeństwa zapobiegającym bezpośredniemu listowaniu katalogów lub prostym przekierowaniem do głównej konfiguracji modułu lub pulpitu nawigacyjnego.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `conordervalid/classes/ConordervalidAdmin.php`
  - **Odpowiedzialność:** Prawdopodobnie zawiera metody pomocnicze lub narzędzia specyficzne dla interfejsu administracyjnego, takie jak rejestracja menu, zarządzanie zakładkami lub wspólna logika renderowania formularzy.
- `conordervalid/classes/ConordervalidAuditLog.php`
  - **Rozszerza:** `ObjectModel`
  - **Tabela bazy danych:** `ps_conordervalid_log`
  - **Pola `$definition`:** `id_conordervalid_log`, `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
  - **Odpowiedzialność:** Reprezentuje pojedynczy wpis w dzienniku audytu, przechowując szczegóły dotyczące wyzwolonej zasady.
- `conordervalid/classes/ConordervalidCartState.php`
  - **Odpowiedzialność:** Klasa narzędziowa do hermetyzacji bieżącego stanu koszyka klienta (produkty, ilości, suma, informacje o kliencie, wybrany przewoźnik itp.). Ten obiekt jest przekazywany do `ConordervalidConditionEvaluator`.
- `conordervalid/classes/ConordervalidCompatibility.php`
  - **Odpowiedzialność:** Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop (np. różnice w nazwach haków, strukturach klas lub wywołaniach API między PS 1.7, 8.x i 9.x).
- `conordervalid/classes/ConordervalidCondition.php`
  - **Rozszerza:** (Prawdopodobnie klasa bazowa lub `ObjectModel`, jeśli warunki są przechowywane indywidualnie)
  - **Odpowiedzialność:** Reprezentuje pojedynczy warunek w ramach zasady (np. „Całkowita wartość koszyka > 100”). Definiuje typ warunku, operator i wartość.
- `conordervalid/classes/ConordervalidConditionEvaluator.php`
  - **Odpowiedzialność:** Główna logika do oceny `ConordervalidCondition` lub `ConordervalidConditionGroup` względem obiektu `ConordervalidCartState`. Zawiera metody do porównywania różnych typów danych i stosowania operatorów.
- `conordervalid/classes/ConordervalidConditionGroup.php`
  - **Rozszerza:** (Prawdopodobnie klasa bazowa)
  - **Odpowiedzialność:** Reprezentuje logiczne grupowanie warunków (np. „Warunek A ORAZ (Warunek B LUB Warunek C)”). Zarządza logiką `AND`/`OR`.
- `conordervalid/classes/ConordervalidConditionTree.php`
  - **Rozszerza:** (Prawdopodobnie klasa bazowa lub `ObjectModel`)
  - **Odpowiedzialność:** Reprezentuje całą hierarchiczną strukturę warunków dla zasady. Jest to struktura danych przypominająca drzewo, złożona z obiektów `ConordervalidConditionGroup` i `ConordervalidCondition`.
- `conordervalid/classes/ConordervalidContext.php`
  - **Odpowiedzialność:** Wrapper lub rozszerzenie klasy `Context` PrestaShop, potencjalnie dodające dane kontekstowe specyficzne dla modułu lub metody pomocnicze.
- `conordervalid/classes/ConordervalidDashboard.php`
  - **Odpowiedzialność:** Prawdopodobnie dostarcza dane i logikę dla potencjalnego pulpitu nawigacyjnego modułu w Panelu Administracyjnym, podsumowującego wydajność zasad lub statystyki dziennika audytu.
- `conordervalid/classes/ConordervalidEngine.php`
  - **Odpowiedzialność:** Centralny orkiestrator. Pobiera aktywne obiekty `ConordervalidPolicy`, iteruje przez nie i używa `ConordervalidConditionEvaluator` do sprawdzenia, czy dany koszyk narusza jakąkolwiek zasadę. Określa ostateczny wynik (zablokowany, ostrzeżony, prawidłowy) i zbiera komunikaty.
- `conordervalid/classes/ConordervalidListRenderer.php`
  - **Odpowiedzialność:** Klasa narzędziowa do renderowania list lub tabel w Panelu Administracyjnym, potencjalnie dostosowująca zachowanie `HelperList` lub zapewniająca specyficzne formatowanie kolumn.
- `conordervalid/classes/ConordervalidLog.php`
  - **Rozszerza:** `ObjectModel` (prawdopodobnie alias lub starsza wersja `ConordervalidAuditLog`)
  - **Tabela bazy danych:** `ps_conordervalid_log`
  - **Pola `$definition`:** Podobne do `ConordervalidAuditLog`.
  - **Odpowiedzialność:** Przechowuje wpisy dziennika audytu.
- `conordervalid/classes/ConordervalidPolicy.php`
  - **Rozszerza:** `ObjectModel`
  - **Tabela bazy danych:** `ps_conordervalid_policy`
  - **Pola `$definition`:** `id_conordervalid_policy`, `name`, `active`, `type` (blocking/warning), `priority`, `conditions_json` (przechowuje `ConordervalidConditionTree` jako JSON), `customer_message`, `admin_message`, `date_add`, `date_upd`.
  - **Odpowiedzialność:** Reprezentuje pojedynczą zasadę walidacji, w tym jej warunki, komunikaty i ustawienia.
- `conordervalid/classes/ConordervalidPolicyDuplicator.php`
  - **Odpowiedzialność:** Obsługuje logikę duplikowania obiektów `ConordervalidPolicy`, zapewniając prawidłowe skopiowanie wszystkich powiązanych warunków i ustawień.
- `conordervalid/classes/ConordervalidPreset.php`
  - **Odpowiedzialność:** Prawdopodobnie definiuje predefiniowane zestawy warunków lub szablony zasad, które mogą być szybko ładowane przez administratorów.
- `conordervalid/classes/ConordervalidRule.php`
  - **Rozszerza:** (Prawdopodobnie klasa bazowa lub `ObjectModel`)
  - **Odpowiedzialność:** Może być aliasem dla `ConordervalidCondition` lub abstrakcją wyższego poziomu dla pojedynczej reguły w ramach zasady.
- `conordervalid/classes/ConordervalidTreeRepository.php`
  - **Odpowiedzialność:** Zarządza przechowywaniem i pobieraniem obiektów `ConordervalidConditionTree`, prawdopodobnie serializując/deserializując je do/z pola `conditions_json` w `ConordervalidPolicy`.
- `conordervalid/classes/index.php`
  - **Odpowiedzialność:** Standardowy środek bezpieczeństwa zapobiegający listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

- `conordervalid/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back-office (formularze administracyjne)
  - **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych w panelu administracyjnym, prawdopodobnie używaną podczas wybierania produktów, kategorii, klientów itp. w kreatorze warunków.
- `conordervalid/lib/searchTool/views/views/js/autocomplete.js`
  - **Zakres:** Back-office (formularze administracyjne)
  - **Odpowiedzialność:** Duplikat powyższego, prawdopodobnie błąd w pakowaniu lub ścieżka dziedziczona.
- `conordervalid/views/js/adminConditionBuilder.js`
  - **Zakres:** Back-office (`AdminconordervalidPoliciesController`)
  - **Odpowiedzialność:** Obsługuje interaktywny interfejs kreatora warunków w formularzu tworzenia/edycji zasad. Obsługuje dodawanie/usuwanie warunków, zarządzanie logiką AND/OR oraz aktualizowanie bazowej struktury JSON drzewa warunków.
- `conordervalid/views/js/adminConordervalidDashboard.js`
  - **Zakres:** Back-office (Panel administracyjny, jeśli zaimplementowany)
  - **Odpowiedzialność:** Zapewnia dynamiczną funkcjonalność dla potencjalnego pulpitu nawigacyjnego modułu, takiego jak renderowanie wykresów, filtrowanie danych lub aktualizacje AJAX.
- `conordervalid/views/js/adminConordervalidSearchTool.js`
  - **Zakres:** Back-office (formularze administracyjne)
  - **Odpowiedzialność:** Integruje narzędzie wyszukiwania (np. dla produktów, kategorii) z różnymi formularzami administracyjnymi, prawdopodobnie używanymi przez kreatora warunków.
- `conordervalid/views/js/adminConordervalidSimulator.js`
  - **Zakres:** Back-office (`AdminconordervalidPoliciesController`)
  - **Odpowiedzialność:** Obsługuje logikę symulatora zasad. Przechwytuje symulowane dane koszyka, wysyła je za pośrednictwem AJAX do kontrolera front-office (np. `validate.php`) i dynamicznie aktualizuje interfejs użytkownika, aby wyświetlić wyniki walidacji.
- `conordervalid/views/js/adminPolicyRules.js`
  - **Zakres:** Back-office (`AdminconordervalidPoliciesController`)
  - **Odpowiedzialność:** Zawiera specyficzną logikę JS do zarządzania wyświetlaniem i interakcją reguł zasad w interfejsie administracyjnym, potencjalnie związaną z przeciąganiem i upuszczaniem w celu zmiany kolejności lub szybkimi edycjami.
- `conordervalid/views/js/validation.js`
  - **Zakres:** Front-office (strony koszyka, realizacji zamówienia)
  - **Odpowiedzialność:** Jest to główny JS front-office. Nasłuchuje zmian w koszyku (np. aktualizacja ilości, usunięcie produktu), wyzwala wywołania AJAX do kontrolera front-office `validate.php`, a następnie dynamicznie aktualizuje interfejs użytkownika, aby wyświetlić komunikaty ostrzegawcze/blokujące lub włączyć/wyłączyć przyciski realizacji zamówienia na podstawie odpowiedzi. Prawdopodobnie używa `prestashop.on` do wiązania zdarzeń.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `conordervalid/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Back-office (formularze administracyjne)
  - **Główne komponenty interfejsu użytkownika:** Style dla rozwijanych list autouzupełniania i pól wejściowych używanych w narzędziu wyszukiwania administracyjnego.
  - **Kluczowe selektory:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `conordervalid/lib/searchTool/views/views/css/autocomplete.css`
  - **Zakres:** Back-office (formularze administracyjne)
  - **Główne komponenty interfejsu użytkownika:** Duplikat powyższego.
  - **Kluczowe selektory:** Takie same jak powyżej.
- `conordervalid/views/css/admin_conordervalid.css`
  - **Zakres:** Back-office (formularze i listy administracyjne)
  - **Główne komponenty interfejsu użytkownika:** Style dla listy zasad, formularza tworzenia/edycji zasad, kreatora warunków i dziennika audytu.
  - **Kluczowe selektory:** `.conordervalid-policy-card`, `.conordervalid-condition-group`, `.conordervalid-condition-row`, `.conordervalid-simulator-results`.
- `conordervalid/views/css/front.css`
  - **Zakres:** Front-office (strony koszyka, realizacji zamówienia)
  - **Główne komponenty interfejsu użytkownika:** Style dla banerów ostrzegawczych/blokujących i komunikatów wyświetlanych klientom.
  - **Kluczowe selektory:** `.conordervalid-validation-banner`, `.conordervalid-warning`, `.conordervalid-blocking`, `.conordervalid-message-list`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### 4.6.1 Szablony haków (`views/templates/hook/`)

- `conordervalid/views/templates/hook/admin_order.tpl`
  - **Hak:** `DisplayAdminOrder`
  - **Wyjścia:** Blok w widoku zamówienia w Panelu Administracyjnym, potencjalnie pokazujący, które zasady zostały wyzwolone dla konkretnego zamówienia lub koszyka.
- `conordervalid/views/templates/hook/validation_banner.tpl`
  - **Hak:** `DisplayPaymentTop`, `DisplayShoppingCartFooter`, `DisplayCheckoutSummaryTop`
  - **Wyjścia:** Struktura HTML dla komunikatów ostrzegawczych/blokujących w front-office wyświetlanych klientowi. Ten szablon otrzymuje zmienne takie jak `$validation_messages`, `$is_blocked` itp.

#### 4.6.2 Szablony administracyjne (`views/templates/admin/`)

- `conordervalid/lib/searchTool/views/scripts.tpl`
  - **Wyjścia:** Szablon Smarty do dołączania zasobów JS/CSS związanych z narzędziem wyszukiwania w panelu administracyjnym.
- `conordervalid/lib/searchTool/views/views/scripts.tpl`
  - **Wyjścia:** Duplikat powyższego.
- `conordervalid/views/templates/admin/auditPreview.tpl`
  - **Wyjścia:** Częściowy szablon do wyświetlania podglądu lub podsumowania wpisów dziennika audytu, prawdopodobnie używany w panelu administracyjnym lub konkretnym widoku.
- `conordervalid/views/templates/admin/dashboard.tpl`
  - **Wyjścia:** Główny szablon dla potencjalnego pulpitu nawigacyjnego modułu w Panelu Administracyjnym, wyświetlający statystyki, ostatnie logi lub podsumowania zasad.
- `conordervalid/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Wyjścia:** Niestandardowy przycisk akcji do duplikowania zasad w widoku `HelperList` dla `AdminconordervalidPoliciesController`.
- `conordervalid/views/templates/admin/policiesPreview.tpl`
  - **Wyjścia:** Częściowy szablon do wyświetlania podglądu lub podsumowania zasad, podobny do `auditPreview.tpl`.
- `conordervalid/views/templates/admin/policyConditionBuilder.tpl`
  - **Wyjścia:** Złożona struktura HTML dla interaktywnego interfejsu kreatora warunków używanego podczas tworzenia lub edytowania zasady. Ten szablon ściśle współpracuje z `adminConditionBuilder.js`.
- `conordervalid/views/templates/admin/policyRuleCard.tpl`
  - **Wyjścia:** Mniejszy, wielokrotnego użytku szablon do wyświetlania pojedynczej reguły lub warunku w kreatorze warunków.
- `conordervalid/views/templates/admin/policyRulesTable.tpl`
  - **Wyjścia:** Struktura tabelaryczna do wyświetlania listy reguł, prawdopodobnie używana w przeglądzie zasad lub symulatorze.
- `conordervalid/views/templates/admin/scopeSelector.tpl`
  - **Wyjścia:** Szablon do wyboru zakresu zasady (np. konkretne sklepy w środowisku wielosklepowym).

#### 4.6.3 Szablony Front-office (`views/templates/front/`)

- (Nie zidentyfikowano dedykowanych samodzielnych szablonów front-office, ponieważ wyświetlanie w front-office jest obsługiwane za pomocą szablonów haków, takich jak `validation_banner.tpl`.)

### 4.7 Schemat bazy danych i mapa haków

#### 4.7.1 Tabele bazy danych

- `ps_conordervalid_policy`
  - **Cel:** Przechowuje definicję każdej zasady walidacji.
  - **Kluczowe pola:** `id_conordervalid_policy` (PK), `name`, `active` (boolean), `type` (enum: ‘blocking’, ‘warning’), `priority`, `conditions_json` (TEXT, przechowuje serializowane `ConordervalidConditionTree`), `customer_message` (TEXT), `admin_message` (TEXT), `date_add`, `date_upd`.
- `ps_conordervalid_log`
  - **Cel:** Przechowuje wpisy dziennika audytu dla wyzwolonych zasad.
  - **Kluczowe pola:** `id_conordervalid_log` (PK), `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
- `ps_configuration`
  - **Cel:** Przechowuje globalne ustawienia modułu.
  - **Kluczowe pola:** `CONORDERVALID_DISPLAY_SURFACES` (np. ‘cart,checkout’), `CONORDERVALID_ENABLED` (boolean), `CONORDERVALID_ALLOW_WARN_CHECKOUT` (boolean).

#### 4.7.2 Tabela zarejestrowanych haków

| Nazwa haka | Czas i kontekst wykonania | Cel techniczny |
| --- | --- | --- |
| `DisplayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Wstrzykuje zasoby CSS (`front.css`) i JS (`validation.js`) front-office. |
| `ActionFrontControllerInitAfter` | Po zainicjalizowaniu kontrolera front-office. | Potencjalnie używany do inicjalizacji kontekstu modułu, ładowania zasad lub wykonywania wczesnych kontroli walidacji. |
| `ActionObjectProductInCartDeleteBefore` | Przed usunięciem produktu z koszyka. | Może być używany do logowania stanu koszyka przed zmianą lub do zapobiegania usunięciu, jeśli narusza zasadę. |
| `ActionObjectProductInCartDeleteAfter` | Po usunięciu produktu z koszyka. | Ponowna ocena zasad koszyka po usunięciu produktu, wyzwolenie aktualizacji AJAX. |
| `ActionCartSave` | Po zapisaniu koszyka (np. aktualizacja ilości, dodanie/usunięcie produktu). | Wyzwala ponowną ocenę wszystkich aktywnych zasad względem zaktualizowanego koszyka. |
| `actionPresentCart` | Gdy koszyk jest przygotowywany do wyświetlenia (np. na stronie koszyka). | Wstrzykuje komunikaty walidacji do szablonu strony koszyka. |
| `DisplayShoppingCartFooter` | Na dole strony koszyka. | Renderuje `validation_banner.tpl` z wszelkimi komunikatami ostrzegawczymi/blokującymi. |
| `DisplayPaymentTop` | Na górze sekcji wyboru płatności podczas realizacji zamówienia. | Renderuje `validation_banner.tpl` z wszelkimi komunikatami ostrzegawczymi/blokującymi, potencjalnie wyłączając opcje płatności. |
| `DisplayCheckoutSummaryTop` | Na górze strony podsumowania realizacji zamówienia (przed ostatecznym potwierdzeniem zamówienia). | Renderuje `validation_banner.tpl` z wszelkimi komunikatami ostrzegawczymi/blokującymi, potencjalnie wyłączając przycisk potwierdzenia zamówienia. |
| `ActionFilterPaymentOptions` | Filtruje dostępne opcje płatności podczas realizacji zamówienia. | Może być używany do ukrywania lub wyłączania metod płatności, jeśli zasada jest naruszona (np. „Płatność za pobraniem niedozwolona dla zamówień powyżej X $”). |
| `ActionValidateOrderBefore` | Tuż przed oficjalnym zatwierdzeniem zamówienia. | Ostateczna krytyczna kontrola blokująca zamówienie, jeśli naruszone są jakiekolwiek zasady blokujące. Loguje próbę. |
| `ActionValidateOrder` | Po pomyślnym zatwierdzeniu i utworzeniu zamówienia. | Loguje pomyślną walidację zamówienia, potencjalnie rejestruje, które zasady *nie* zostały naruszone. |
| `DisplayAdminOrder` | Renderuje blok w szczegółach zamówienia w Panelu Administracyjnym. | Wyświetla informacje o zasadach, które zostały wyzwolone (lub przeszły) dla konkretnego zamówienia, używając `admin_order.tpl`. |
| `ActionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje media (JS/CSS). | Wstrzykuje specyficzne dla Panelu Administracyjnego JS (`adminConditionBuilder.js`, `adminConordervalidSimulator.js`) i CSS (`admin_conordervalid.css`) do zarządzania zasadami. |
| `DisplayReassurance` | Często używany do wyświetlania elementów zaufania (np. ikon bezpiecznych płatności). | Potencjalnie może być używany do wyświetlania małego, trwałego ostrzeżenia lub statusu, jeśli koszyk jest nieprawidłowy. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Warunkowa Walidacja Zamówień, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
