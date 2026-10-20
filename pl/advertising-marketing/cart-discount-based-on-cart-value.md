---
title: "Rabat koszyka na podstawie wartości koszyka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Rabat koszyka na podstawie wartości koszyka” od MyPresta.eu."
sidebar:
  label: "Rabat koszyka na podstawie wartości koszyka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cart discount based on cart value na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-discount-based-on-cart-value.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/cart-discount-based-on-cart-value/)
>
> ---


# Rabat koszyka na podstawie wartości koszyka

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym kontrolujesz ogólne zachowanie i ustawienia programu rabatów koszyka.

-   **Aktywuj program**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całego programu rabatów koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie aktywnie sprawdzał wartości koszyka i stosował rabaty zgodnie z zdefiniowanymi zasadami.
        -   *Gdy wyłączone (NIE):* Nie będą stosowane żadne rabaty koszyka, a żadne powiązane wiadomości nie pojawią się na stronie koszyka, niezależnie od innych ustawień.
    -   **Zalecana wartość:** TAK (po skonfigurowaniu zasad rabatowych).
    -   **Scenariusz/przykład sprzedawcy:** Możesz tymczasowo wyłączyć go podczas specjalnej wyprzedaży, gdzie obowiązują inne zasady rabatowe, lub jeśli musisz przeprowadzić konserwację.
-   **Wyłącz program rabatów koszyka dla wybranych grup klientów**

    -   **Co robi to ustawienie:** Pozwala zapobiec otrzymywaniu tych rabatów opartych na wartości koszyka przez określone grupy klientów (np. hurtowników, VIP-ów lub gości).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane:* Klienci należący do wybranych grup nie otrzymają żadnych rabatów z tego modułu, nawet jeśli wartość ich koszyka spełnia kryteria.
        -   *Gdy niewybrane:* Wszystkie grupy klientów są uprawnione do rabatów.
    -   **Zalecana wartość:** Zależy od Twojej strategii biznesowej. Jeśli masz specjalne ceny dla niektórych grup, możesz je wykluczyć.
    -   **Scenariusz/przykład sprzedawcy:** Masz grupę klientów „Hurtownicy”, która już otrzymuje specjalne ceny. Wybierzesz tę grupę tutaj, aby uniknąć kumulowania rabatów.
-   **Typ ceny**

    -   **Co robi to ustawienie:** Określa, czy wartość koszyka do obliczenia rabatu powinna zawierać, czy wykluczać podatki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Cena z podatkiem”:* Rabat jest obliczany na podstawie całkowitej wartości koszyka *wraz z* VAT/podatkami.
        -   *Gdy ustawione na „Cena bez podatku”:* Rabat jest obliczany na podstawie całkowitej wartości koszyka *bez* VAT/podatków.
    -   **Zalecana wartość:** „Cena z podatkiem” dla większości sklepów B2C, „Cena bez podatku” dla sklepów B2B lub jeśli Twoje podstawowe ceny są bez podatku.
    -   **Scenariusz/przykład sprzedawcy:** Jeśli Twoi klienci są przyzwyczajeni do widzenia cen z podatkiem, obliczanie rabatu na podstawie „Ceny z podatkiem” będzie dla nich bardziej naturalne i przejrzyste.
-   **Wyklucz produkty z rabatem**

    -   **Co robi to ustawienie:** Kontroluje, czy produkty, które są już w promocji lub mają określoną cenę (np. z reguły katalogowej), powinny być wliczane do wartości koszyka do obliczenia rabatu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Produkty już objęte rabatem zostaną zignorowane podczas obliczania całkowitej wartości koszyka dla rabatu wielopoziomowego.
        -   *Gdy wyłączone (NIE):* Wszystkie produkty w koszyku, niezależnie od tego, czy są już objęte rabatem, przyczynią się do wartości koszyka dla rabatu wielopoziomowego.
    -   **Zalecana wartość:** TAK, aby zapobiec „podwójnemu rabatowaniu” i chronić Twoje marże.
    -   **Scenariusz/przykład sprzedawcy:** Prowadzisz wyprzedaż 20% na konkretne T-shirty. Jeśli klient kupi T-shirt i inne przedmioty, a to ustawienie jest TAK, wartość T-shirtu nie pomoże mu osiągnąć kolejnego poziomu rabatu koszyka.
-   **Wyklucz produkty od producenta**

    -   **Co robi to ustawienie:** Pozwala określić konkretnych producentów, których produkty nie powinny przyczyniać się do wartości koszyka podczas obliczania rabatu wielopoziomowego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane:* Produkty od wybranych producentów zostaną zignorowane podczas obliczania całkowitej wartości koszyka dla rabatu wielopoziomowego.
        -   *Gdy niewybrane:* Wszystkie produkty, niezależnie od producenta, przyczyniają się do wartości koszyka.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne umowy lub produkty o niskiej marży od niektórych producentów.
    -   **Scenariusz/przykład sprzedawcy:** Sprzedajesz produkty od marki premium, która ma ścisłe zasady cenowe i nie może być objęta ogólnymi rabatami. Wybierzesz tego producenta tutaj.
-   **Wyklucz produkty objęte rabatem z wartości rabatu**

    -   **Co robi to ustawienie:** Określa, czy *wartość* produktów, które są już objęte rabatem, powinna być wykluczona z *kwoty* zastosowanego rabatu koszyka. Jest to subtelne, ale ważne rozróżnienie od „Wyklucz produkty z rabatem”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Jeśli zastosowany zostanie rabat koszyka w wysokości 5%, a niektóre produkty w koszyku są już objęte rabatem, 5% będzie dotyczyć tylko produktów nieobjętych rabatem.
        -   *Gdy wyłączone (NIE):* Rabat koszyka w wysokości 5% będzie dotyczyć *całej* wartości koszyka, nawet jeśli niektóre przedmioty w nim są już objęte rabatem.
    -   **Zalecana wartość:** TAK, aby chronić marże i zapobiegać nadmiernym rabatom na już przecenione produkty.
    -   **Scenariusz/przykład sprzedawcy:** Klient ma koszyk o wartości 100 €, z jednym produktem o wartości 20 € już objętym 10% rabatem. Jeśli zastosowany zostanie 5% rabat koszyka, a to ustawienie jest TAK, 5% będzie dotyczyć tylko produktów o wartości 80 € nieobjętych rabatem.
-   **Wyklucz koszyk z kodem kuponu**

    -   **Co robi to ustawienie:** Zapobiega stosowaniu rabatów modułu opartych na wartości koszyka, jeśli klient wprowadził już oddzielny kod kuponu w swoim koszyku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Jeśli klient użyje kodu kuponu, automatyczny rabat koszyka modułu nie zostanie zastosowany, unikając kumulowania rabatów.
        -   *Gdy wyłączone (NIE):* Rabat modułu zostanie zastosowany nawet jeśli kod kuponu jest obecny, potencjalnie kumulując rabaty.
    -   **Zalecana wartość:** TAK, aby zapobiec nadmiernemu rabatowaniu i zachować kontrolę nad swoimi promocjami.
    -   **Scenariusz/przykład sprzedawcy:** Prowadzisz specjalną kampanię e-mailową z unikalnym kuponem na 10% zniżki. Chcesz, aby klienci wybierali między tym kuponem a wielopoziomowym rabatem koszyka, a nie oboma.
-   **Pokaż informacje o programie rabatowym na stronie koszyka**

    -   **Co robi to ustawienie:** Kontroluje, czy wiadomości o programie rabatów koszyka (np. „Wydaj X więcej, aby uzyskać Y% rabatu!”) są wyświetlane na stronie koszyka zakupowego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Na stronie koszyka pojawią się informacyjne wiadomości, kierujące klientów do większych wydatków.
        -   *Gdy wyłączone (NIE):* Na stronie koszyka nie będą wyświetlane żadne wiadomości związane z rabatami tego modułu. Rabat nadal będzie stosowany, jeśli jest aktywny, ale bez komunikatów promocyjnych.
    -   **Zalecana wartość:** TAK, ponieważ jest to kluczowa funkcja zachęcająca do wyższego AOV.
    -   **Scenariusz/przykład sprzedawcy:** Chcesz aktywnie zachęcać klientów do osiągnięcia kolejnego poziomu rabatu. Włączenie tego pokaże im dokładnie, ile więcej muszą wydać.
-   **Dodatkowa niestandardowa zawartość**

    -   **Co robi to ustawienie:** Pozwala dodać niestandardowy tekst, HTML, a nawet obrazy, które będą wyświetlane wraz z informacjami o programie rabatowym na stronie koszyka. Ta zawartość może być tłumaczona na różne języki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzono zawartość:* Twoja niestandardowa wiadomość pojawi się na stronie koszyka, wzmacniając komunikat promocyjny.
        -   *Gdy pozostawiono puste:* Nie będzie wyświetlana żadna dodatkowa niestandardowa zawartość.
    -   **Zalecana wartość:** Użyj tego, aby dodać przekonujące wezwanie do działania lub wyjaśnić korzyści z programu rabatowego.
    -   **Scenariusz/przykład sprzedawcy:** Możesz dodać „Nie przegap oszczędności! Im więcej kupujesz, tym więcej oszczędzasz!” lub link do swoich warunków i zasad rabatów.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminCdisListController (Panel administracyjny > Moduły > Rabat koszyka na podstawie wartości koszyka > przycisk „Konfiguruj”, a następnie przejdź do zakładki „Rabaty” lub podobnej)

Ten ekran służy do definiowania i zarządzania rzeczywistymi zasadami rabatowymi. Zazwyczaj jest dostępny po kliknięciu „Konfiguruj” w module, a następnie przejściu do konkretnej zakładki lub linku „Rabaty” lub „Zasady”.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran jest zazwyczaj dostępny za pośrednictwem dedykowanej zakładki lub linku w głównej stronie konfiguracji modułu, często oznaczonej jako „Rabaty”, „Zasady” lub „Zarządzaj rabatami”.
-   **Dostępne akcje i ustawienia:**
    -   **Widok siatki / zarządzania:** Zobaczysz tabelę zawierającą wszystkie zdefiniowane zasady rabatowe. Każdy wiersz reprezentuje zasadę z kolumnami takimi jak:
        -   **Minimalna wartość koszyka:** Próg, który koszyk musi osiągnąć.
        -   **Typ rabatu:** Czy jest to procent, czy stała kwota.
        -   **Wartość rabatu:** Procent (np. 5) lub stała kwota (np. 10.00).
        -   **Aktywny:** Czy zasada jest aktualnie włączona.
        -   **Akcje:** Przyciski do „Edytuj” lub „Usuń” poszczególnych zasad.
    -   **Przycisk Dodaj nową zasadę:** Przycisk (np. „Dodaj nową zasadę rabatową”) do tworzenia nowego warunku rabatowego. Po kliknięciu otworzy się formularz do zdefiniowania nowej zasady.
    -   **Formularz edycji zasady:** Podczas dodawania lub edytowania zasady zazwyczaj znajdziesz pola dla:
        -   **Minimalna wartość koszyka:** (np. 500) - Minimalna całkowita wartość koszyka, aby ten rabat został zastosowany.
        -   **Typ rabatu:** (np. Procent, Stała kwota) - Wybierz, jak obliczany jest rabat.
        -   **Wartość rabatu:** (np. 5 dla 5%, lub 10.00 dla 10 €) - Rzeczywisty rabat do zastosowania.
        -   **Aktywny:** (Przełącznik Tak/Nie) - Aby włączyć lub wyłączyć tę konkretną zasadę bez jej usuwania.
        -   **Priorytet:** (np. 1, 2, 3) - Jeśli może obowiązywać wiele zasad (np. wartość koszyka wynosi 1000 €, a masz zasady dla 500 € i 1000 €), priorytet określa, która z nich ma pierwszeństwo. Niższe liczby zazwyczaj oznaczają wyższy priorytet.
-   **Efekt zmian:**
    -   **Dodanie zasady:** Nowy warunek rabatowy staje się aktywny w Twoim sklepie, automatycznie stosując się do koszyków klientów, które spełniają kryteria.
    -   **Edycja zasady:** Modyfikuje istniejący warunek rabatowy, zmieniając jego próg, wartość lub status aktywności.
    -   **Usunięcie zasady:** Trwale usuwa warunek rabatowy, a nie będzie on już stosowany do koszyków.
    -   **Aktywacja/Dezaktywacja:** Przełącza dostępność konkretnej zasady rabatowej bez usuwania jej konfiguracji.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zacznij od zaplanowania poziomów rabatów (np. 250 € za 2%, 500 € za 5%, 1000 € za 10%).
    2.  Kliknij „Dodaj nową zasadę rabatową” dla każdego poziomu.
    3.  Wprowadź „Minimalną wartość koszyka”, wybierz „Typ rabatu” (zazwyczaj Procent) i wprowadź „Wartość rabatu”.
    4.  Upewnij się, że „Aktywny” jest ustawione na TAK.
    5.  Ustaw priorytety, jeśli masz nakładające się zakresy (np. zasada dla >500 € i inna dla >1000 €, upewnij się, że zasada dla 1000 € ma wyższy priorytet, jeśli chcesz, aby była stosowana zamiast zasady dla 500 €, gdy koszyk przekracza 1000 €). Moduł zazwyczaj radzi sobie z tym, stosując rabat o najwyższej wartości dla najwyższego osiągniętego poziomu.
    6.  Regularnie przeglądaj swoje zasady rabatowe, zwłaszcza przed dużymi wyprzedażami lub okresami promocyjnymi, aby upewnić się, że są zgodne z Twoją aktualną strategią marketingową.

#### 2.2.2 index.php (cartdiscount/controllers/admin/index.php)

Ten plik jest plikiem zastępczym i zazwyczaj zawiera tylko instrukcję bezpieczeństwa `die()`, aby zapobiec bezpośredniemu dostępowi do katalogu. Nie reprezentuje konfigurowalnego ekranu ani widoku zarządzania encjami dla sprzedawcy.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Aktywuj program | TAK | Główny przełącznik dla całego programu rabatowego. |
| | Wyłącz program rabatów koszyka dla wybranych grup klientów | (Brak wybranych) | Wyklucza wybrane grupy klientów z otrzymywania rabatów. |
| | Typ ceny | Cena z podatkiem | Określa, czy wartość koszyka zawiera, czy wyklucza podatek do obliczeń. |
| | Wyklucz produkty z rabatem | TAK | Zapobiega wliczaniu już przecenionych produktów do progu wartości koszyka. |
| | Wyklucz produkty od producenta | (Brak wybranych) | Ignoruje produkty od wybranych producentów przy obliczaniu wartości koszyka. |
| | Wyklucz produkty objęte rabatem z wartości rabatu | TAK | Zapewnia, że rabat koszyka dotyczy tylko produktów nieobjętych rabatem w koszyku. |
| | Wyklucz koszyk z kodem kuponu | TAK | Zapobiega rabatom modułu, jeśli użyto oddzielnego kodu kuponu. |
| | Pokaż informacje o programie rabatowym na stronie koszyka | TAK | Wyświetla komunikaty promocyjne na stronie koszyka. |
| | Dodatkowa niestandardowa zawartość | (Puste) | Dodaje niestandardowy tekst/HTML do informacji o rabacie na stronie koszyka. |
| **AdminCdisListController (Lista rabatów)** | Minimalna wartość koszyka | (Zdefiniowane przez sprzedawcę) | Próg całkowitej wartości koszyka, aby uruchomić rabat. |
| | Typ rabatu | Procent | Sposób obliczania rabatu (procent lub stała kwota). |
| | Wartość rabatu | (Zdefiniowane przez sprzedawcę) | Rzeczywista kwota rabatu (np. 5 dla 5%, 10.00 dla 10 €). |
| | Aktywny | TAK | Włącza lub wyłącza konkretną zasadę rabatową. |
| | Priorytet | (Auto/Zdefiniowane przez sprzedawcę) | Określa, która zasada ma zastosowanie, jeśli spełniono wiele progów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje rabaty nie są stosowane, mimo że ustawiłem zasady. Co jest nie tak?**
O:

1.  **Sprawdź „Aktywuj program”:** Upewnij się, że główny przełącznik na stronie konfiguracji modułu jest ustawiony na TAK.
2.  **Sprawdź status „Aktywny” poszczególnych zasad:** Upewnij się, że każda zasada rabatowa, którą utworzyłeś w `AdminCdisListController`, jest również ustawiona na TAK.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). PrestaShop często buforuje ustawienia modułów.
4.  **Sprawdź grupy klientów:** Sprawdź, czy grupa klientów, z którą testujesz, nie jest wykluczona w sekcji „Wyłącz program rabatów koszyka dla wybranych grup klientów”.
5.  **Próg wartości koszyka:** Dokładnie sprawdź, czy wartość Twojego koszyka faktycznie spełnia „Minimalną wartość koszyka”, aby rabat został uruchomiony.

**P: Rabat jest stosowany, ale wiadomość na stronie koszyka nie pojawia się.**
O:

1.  **Sprawdź „Pokaż informacje o programie rabatowym na stronie koszyka”:** Upewnij się, że to ustawienie jest włączone (TAK) na głównej stronie konfiguracji modułu.
2.  **Kompatybilność z motywem:** Twój niestandardowy motyw może nadpisywać standardowe wyświetlanie koszyka. Sprawdź, czy hook `displayShoppingCartFooter` jest poprawnie zaimplementowany w pliku `shopping-cart.tpl` Twojego motywu lub równoważnym. Jeśli nie, programista może potrzebować ręcznie dodać ten hook.
3.  **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P: Wartość rabatu wydaje się nieprawidłowa lub nie dotyczy wszystkich produktów.**
O:

1.  **„Typ ceny”:** Sprawdź, czy wybrałeś „Cena z podatkiem” czy „Cena bez podatku” do obliczeń.
2.  **„Wyklucz produkty z rabatem”:** Jeśli włączone, produkty już objęte wyprzedażą nie będą wliczane do progu.
3.  **„Wyklucz produkty objęte rabatem z wartości rabatu”:** Jeśli włączone, rabat procentowy będzie dotyczył tylko produktów nieobjętych rabatem w koszyku. Przejrzyj te ustawienia, aby upewnić się, że odpowiadają zamierzonemu zachowaniu.
4.  **„Wyklucz koszyk z kodem kuponu”:** Jeśli klient zastosował oddzielny kupon, a to ustawienie jest TAK, rabat modułu nie zostanie zastosowany.

**P: Jak przetłumaczyć dodaną niestandardową zawartość?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz język, który chcesz przetłumaczyć.
3.  Znajdź moduł „Rabat koszyka na podstawie wartości koszyka”. Powinieneś zobaczyć pola do przetłumaczenia „Dodatkowej niestandardowej zawartości” dla każdego języka.

**P: Widzę błąd po aktualizacji PrestaShop lub innego modułu.**
O:

1.  **Sprawdź wersję modułu:** Upewnij się, że używasz najnowszej wersji modułu „Rabat koszyka na podstawie wartości koszyka” kompatybilnej z Twoją wersją PrestaShop. Pobierz prawidłowy plik ZIP z MyPresta.eu.
2.  **Kompatybilność z PHP:** Sprawdź, czy wersja PHP Twojego serwera mieści się w obsługiwanym zakresie modułu (PHP 5.6 - 8.5).
3.  **Wyłącz nadpisywanie (dla programistów):** Jeśli podejrzewasz konflikt, tymczasowo wyłącz nadpisywanie w **Zaawansowane > Wydajność** (ustaw „Wyłącz moduły inne niż PrestaShop” na TAK, a następnie wyczyść pamięć podręczną). Jeśli problem zostanie rozwiązany, prawdopodobnie jest to konflikt nadpisywania. Włącz ponownie i skonsultuj się z programistą.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Rabat koszyka na podstawie wartości koszyka” rozszerza podstawowe funkcjonalności `Cart` i `CartRule` PrestaShop poprzez nadpisywanie, aby dynamicznie stosować rabaty. Wykorzystuje dedykowany kontroler administracyjny (`AdminCdisListController`) do zarządzania zasadami rabatowymi przechowywanymi w niestandardowej tabeli bazy danych. Integracja z front-office jest osiągana głównie poprzez hooki, aby wyświetlać komunikaty informacyjne i zapewniać stosowanie rabatów podczas procesów koszyka i realizacji zamówienia.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak jawnie zdefiniowanych w katalogu `controllers/front/` modułu. Logika front-office dla stosowania rabatów jest obsługiwana poprzez nadpisywanie i hooki.
-   **Kontrolery administracyjne Back-Office**:

    -   `cartdiscount/controllers/admin/AdminCdisList.php`
        -   **Nazwa klasy i klasa nadrzędna:** `AdminCdisListController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja:** Zarządza listą i formularzami dla encji `Cdis` (Rabat koszyka). Ten kontroler zapewnia interfejs do tworzenia, edytowania i usuwania wielopoziomowych zasad rabatowych. Definiuje widok listy (`renderList()`) i widok formularza (`renderForm()`) dla zasad rabatowych.
    -   `cartdiscount/controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna:** N/A (plik bezpieczeństwa).
        -   **Odpowiedzialność:** Zawiera instrukcję `die('No direct script access allowed');`, aby zapobiec bezpośredniemu dostępowi do katalogu, co jest standardową praktyką bezpieczeństwa PrestaShop.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł w dużym stopniu opiera się na nadpisywaniu, aby wstrzyknąć swoją logikę do podstawowych klas PrestaShop.

-   `cartdiscount/override/classes/Cart.php`
    -   **Oryginalna klasa:** `Cart`
    -   **Odpowiedzialność:** To nadpisanie jest kluczowe. Rozszerza klasę `Cart`, aby modyfikować sposób obliczania sum koszyka, w szczególności w celu zastosowania dynamicznych rabatów na podstawie zasad modułu. Prawdopodobnie przechwytuje metody takie jak `getProducts()`, `getProductsTotal()` lub `getPackageShippingCost()`, aby dostosować ceny przed ich finalizacją. Zawiera również logikę do określania, czy rabat powinien zostać zastosowany na podstawie bieżącej wartości koszyka i skonfigurowanych zasad.
-   `cartdiscount/override/classes/CartRule.php`
    -   **Oryginalna klasa:** `CartRule`
    -   **Odpowiedzialność:** To nadpisanie prawdopodobnie rozszerza klasę `CartRule`, aby umożliwić modułowi tworzenie i zarządzanie własnymi wewnętrznymi obiektami `CartRule` dynamicznie. Kiedy moduł stosuje rabat, często odbywa się to poprzez utworzenie tymczasowej lub specyficznej `CartRule`, która odzwierciedla obliczony rabat, który następnie jest stosowany do koszyka. To nadpisanie zapewnia kompatybilność i prawidłową obsługę tych dynamicznie generowanych zasad.
-   `cartdiscount/override/classes/index.php`
    -   **Odpowiedzialność:** Plik bezpieczeństwa, `die('No direct script access allowed');`.
-   `cartdiscount/override/classes/order/index.php`
    -   **Odpowiedzialność:** Plik bezpieczeństwa, `die('No direct script access allowed');`.
-   `cartdiscount/override/classes/order/Order.php`
    -   **Oryginalna klasa:** `Order`
    -   **Odpowiedzialność:** To nadpisanie zapewnia, że rabaty zastosowane przez moduł są poprawnie przenoszone i przechowywane podczas składania zamówienia. Może modyfikować metody związane z tworzeniem zamówienia lub obliczaniem sumy, aby odzwierciedlić zastosowane zasady koszyka.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `cartdiscount/views/admin/js/cdis.js`
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Ten skrypt prawdopodobnie obsługuje interakcje po stronie klienta dla `AdminCdisListController`. Może to obejmować:
        -   Wywołania AJAX do zapisywania/aktualizowania zasad rabatowych.
        -   Walidację formularza dla formularza „Dodaj/Edytuj zasadę rabatową”.
        -   Dynamiczne aktualizacje interfejsu użytkownika lub interakcje w siatce zarządzania zasadami rabatowymi.
        -   Potencjalnie, obsługę pól „Wyklucz produkty od producenta” lub innych dynamicznych pól wyboru.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `cartdiscount/views/admin/css/cdis.css`
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Odpowiedzialność:** Zapewnia specyficzną stylizację interfejsu `AdminCdisListController`, zapewniając, że formularze i listy zarządzania zasadami rabatowymi są dobrze prezentowane i zgodne z interfejsem użytkownika panelu administracyjnego PrestaShop.
    -   **Kluczowe selektory klas CSS:** Programiści mogą sprawdzić kod HTML generowany przez `AdminCdisListController`, aby znaleźć konkretne klasy (np. `.cdis-form`, `.cdis-list-table`) do nadpisania, jeśli potrzebna jest niestandardowa stylizacja panelu administracyjnego.
-   `cartdiscount/views/css/cartdiscount.css`
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Odpowiedzialność:** Stylizuje komunikaty informacyjne wyświetlane na stronie koszyka (np. „Wydaj X więcej, aby uzyskać Y% rabatu!”).
    -   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w elementy w szablonie `myDiscount.tpl` (np. `.cartdiscount-info`, `.cartdiscount-message`, `.cartdiscount-progress`). Programiści mogą nadpisać te klasy w pliku `custom.css` swojego motywu lub równoważnym, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `cartdiscount/views/templates/hook/myDiscount.tpl`
        -   **Hook:** `displayShoppingCartFooter` (i potencjalnie inne, takie jak `displayHeader` do włączania JS/CSS).
        -   **Blok wizualny:** Ten szablon jest odpowiedzialny za renderowanie dynamicznych wiadomości na stronie koszyka zakupowego. Wyświetla informacje o bieżącej wartości koszyka, zastosowanym rabacie i ile więcej klient musi wydać, aby osiągnąć kolejny poziom rabatu. Renderuje również „Dodatkową niestandardową zawartość”, jeśli jest skonfigurowana.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `AdminCdisListController` będzie używał standardowych szablonów administracyjnych PrestaShop do renderowania widoków listy i formularzy, zazwyczaj znajdujących się w `_partials` lub `helpers/list/list_header.tpl`, `helpers/form/form.tpl` itp., które są częścią rdzenia PrestaShop. Sam moduł może nie mieć niestandardowych plików `.tpl` w `views/templates/admin/`, ale raczej polega na kontrolerze, aby przekazać dane do podstawowych pomocników.
-   **Szablony front-office (`views/templates/front/`)**: Brak jawnie zdefiniowanych.
-   `cartdiscount/lib/searchTool/views/scripts.tpl`
    -   **Zakres:** Prawdopodobnie używany do włączania zasobów JavaScript lub CSS dla komponentu narzędzia wyszukiwania w konfiguracji modułu lub konkretnej funkcji. Jego dokładne użycie zależałoby od implementacji narzędzia wyszukiwania (np. do wybierania producentów do wykluczenia).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_cdis`: Ta niestandardowa tabela przechowuje rzeczywiste zasady rabatowe zdefiniowane przez sprzedawcę (minimalna wartość koszyka, typ rabatu, wartość rabatu, status aktywności, priorytet).
    -   `ps_configuration`: Ustawienia modułu, takie jak `CDIS_ACTIVE`, `CDIS_PRICETYPE`, `CDIS_GROUPSNOT`, `CDIS_EXMANUFACTURER`, `CDIS_SHOWINFO_CART`, `CDIS_EXSPECIFIC`, `CDIS_ORDERCOUPON`, `cdis_contents` (dla niestandardowej zawartości) i `mypresta_updates` są przechowywane tutaj.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Używany do włączania CSS front-office modułu (`cartdiscount.css`) i potencjalnie JavaScript, zapewniając załadowanie stylów i skryptów dla strony koszyka. |
| `ActionAdminControllerSetMedia` | Gdy kontroler administracyjny jest inicjalizowany, a jego media (JS/CSS) są ustawiane. | Używany do włączania CSS back-office modułu (`cdis.css`) i JavaScript (`cdis.js`) dla `AdminCdisListController`, zapewniając prawidłową stylizację i funkcjonalność interfejsu administracyjnego. |
| `displayShoppingCartFooter` | Na dole strony podsumowania koszyka zakupowego. | Renderuje szablon `myDiscount.tpl`, wyświetlając komunikaty informacyjne o programie rabatowym, bieżących oszczędnościach i kolejnych poziomach rabatów dla klienta. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Rabat koszyka na podstawie wartości koszyka”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
