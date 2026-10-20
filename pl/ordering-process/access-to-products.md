---
title: "Dostęp do produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Dostęp do produktów” od MyPresta.eu."
sidebar:
  label: "Dostęp do produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Access to Products na MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/access-to-products/)
>
> ---


# Dostęp do produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Dostęp do produktów)

Jest to główny ekran konfiguracji, na którym definiujesz zasady dostępu do produktów.

#### Ustawienia ogólne

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Włącz moduł** | TAK | **Cel:** Włącza lub wyłącza funkcjonalność modułu. **Efekt:** *Gdy włączony:* Wszystkie skonfigurowane ograniczenia będą aktywne w front office. *Gdy wyłączony:* Moduł nie będzie miał żadnego wpływu, a wszystkie produkty będą widoczne i możliwe do zakupu przez wszystkich klientów, niezależnie od grupy. **Zalecane:** TAK, po skonfigurowaniu reguł. |
| **Zablokuj możliwość przeglądania strony produktu** | NIE | **Cel:** Kontroluje, czy klienci nie należący do dozwolonych grup mogą w ogóle zobaczyć dedykowaną stronę produktu. **Efekt:** *Gdy włączony:* Jeśli klient nie należący do dozwolonej grupy spróbuje uzyskać dostęp do strony produktu bezpośrednio (np. za pomocą linku lub wyszukiwarki), zostanie przekierowany lub zobaczy komunikat o odmowie dostępu. *Gdy wyłączony:* Nieautoryzowani klienci nadal mogą przeglądać stronę produktu, ale zostanie im uniemożliwione dodanie go do koszyka. **Zalecane:** TAK dla produktów naprawdę ekskluzywnych, NIE, jeśli chcesz, aby widzieli produkt, ale nie mogli go kupić (np. „skontaktuj się z nami w sprawie hurtu”). |
| **Ukryj produkt na listach produktów** | NIE | **Cel:** Określa, czy produkty objęte ograniczeniami są ukrywane na stronach kategorii, w wynikach wyszukiwania i innych listach produktów dla nieautoryzowanych klientów. **Efekt:** *Gdy włączony:* Produkty po prostu nie pojawią się na żadnych listach produktów dla klientów nie należących do dozwolonych grup. *Gdy wyłączony:* Produkty pojawią się na listach, ale gdy klient na nie kliknie, zostanie zablokowany dostęp do strony (jeśli „Zablokuj możliwość przeglądania strony produktu” jest TAK) lub zablokowane dodanie do koszyka. **Zalecane:** TAK dla czystszego, bardziej ukierunkowanego doświadczenia przeglądania dla każdej grupy klientów. |
| **Wiadomość dla niedozwolonych klientów** | „Nie masz uprawnień do zamówienia tego produktu.” | **Cel:** Tekst wyświetlany klientom, którzy próbują dodać ograniczony produkt do koszyka lub przeglądać stronę ograniczonego produktu (jeśli „Zablokuj możliwość przeglądania strony produktu” jest NIE). **Efekt:** Ta wiadomość pojawia się w koszyku obok ograniczonego produktu lub na stronie produktu. **Zalecane:** Jasna, uprzejma wiadomość. Możesz ją dostosować, aby wyjaśnić dlaczego (np. „Ten produkt jest przeznaczony tylko dla klientów hurtowych. Zaloguj się na swoje konto hurtowe.”). |

#### Tabela ograniczeń produktów

Ta sekcja wyświetla listę wszystkich produktów, dla których zdefiniowałeś ograniczenia dostępu. Możesz tutaj dodawać nowe ograniczenia lub edytować istniejące.

-   **Nazwa produktu:** Nazwa produktu, który jest objęty ograniczeniem.
-   **Dozwolone grupy klientów:** Lista grup klientów, które *mają* prawo do przeglądania i/lub zakupu tego produktu.
-   **Akcje:** Edytuj (ikona ołówka) lub Usuń (ikona kosza) ograniczenie.

#### Dodawanie/Edytowanie ograniczeń produktów

Po kliknięciu „Dodaj nowe ograniczenie” lub ikony „Edytuj” dla istniejącego ograniczenia, zobaczysz formularz:

-   **Wybierz produkt:**

    -   **Co robi to ustawienie:** Pozwala wyszukać i wybrać konkretny produkt, który chcesz ograniczyć.
    -   **Efekt zmiany tego ustawienia:** Łączy regułę ograniczenia z konkretnym produktem w Twoim katalogu.
    -   **Zalecana wartość:** Wybierz dokładny produkt.
    -   **Scenariusz sprzedawcy:** Chcesz ograniczyć „Hurtową mieszankę kawy” tylko dla swoich klientów hurtowych. Wyszukasz i wybierzesz „Hurtową mieszankę kawy”.
-   **Wybierz grupy klientów:**

    -   **Co robi to ustawienie:** Lista wszystkich grup klientów zdefiniowanych w Twoim sklepie PrestaShop (np. Odwiedzający, Gość, Klient, Hurtownik, VIP). Wybierasz, które z tych grup *mają prawo* dostępu do produktu.
    -   **Efekt zmiany tego ustawienia:** Tylko klienci należący do wybranych grup będą mogli wchodzić w interakcje z produktem zgodnie z Twoimi ogólnymi ustawieniami (przeglądać, dodawać do koszyka). Wszystkie inne grupy będą objęte ograniczeniami.
    -   **Zalecana wartość:** Wybierz tylko te grupy, które powinny mieć dostęp.
    -   **Scenariusz sprzedawcy:** Dla „Hurtowej mieszanki kawy” wybierzesz „Hurtownik”. Jeśli chcesz, aby VIP-y również miały dostęp, wybierzesz „Hurtownik” i „VIP”.

Po dokonaniu wyboru kliknij **„Zapisz”**, aby zastosować ograniczenie.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|
| Konfiguracja modułu | Włącz moduł | TAK | Aktywuje/dezaktywuje całą funkcjonalność modułu. |
| Konfiguracja modułu | Zablokuj możliwość przeglądania strony produktu | NIE (rozważ TAK dla ekskluzywności) | Zapobiega nieautoryzowanym klientom przeglądania strony produktu. |
| Konfiguracja modułu | Ukryj produkt na listach produktów | NIE (rozważ TAK dla ukierunkowanego wyświetlania) | Ukrywa produkty objęte ograniczeniami z wyników kategorii/wyszukiwania dla nieautoryzowanych klientów. |
| Konfiguracja modułu | Wiadomość dla niedozwolonych klientów | „Nie masz uprawnień do zamówienia tego produktu.” | Konfigurowalna wiadomość wyświetlana nieautoryzowanym klientom. |
| Tabela ograniczeń produktów | Wybierz produkt | N/A | Wybierz produkt, do którego mają być zastosowane ograniczenia. |
| Tabela ograniczeń produktów | Wybierz grupy klientów | N/A | Zdefiniuj, które grupy klientów *mają prawo* dostępu do wybranego produktu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem ograniczenia, ale wydaje się, że nie działają. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Upewnij się, że „Włącz moduł” jest ustawione na TAK w konfiguracji modułu.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Jest to kluczowe, aby zmiany zaczęły obowiązywać.
3.  **Przypisanie do grupy klientów:** Sprawdź dokładnie, czy klient, którego testujesz, jest poprawnie przypisany do zamierzonej grupy klientów (Klienci > Klienci, a następnie edytuj klienta).
4.  **Wybór produktu:** Sprawdź, czy wybrałeś prawidłowy produkt w ustawieniach ograniczeń modułu.
5.  **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub przetestować w oknie incognito/prywatnym, aby wykluczyć problemy z buforowaniem po stronie klienta.

**P: Jak przetłumaczyć „Wiadomość dla niedozwolonych klientów” na inne języki?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów” jako Typ tłumaczenia.
3.  Wybierz swój motyw.
4.  Wybierz język, na który chcesz przetłumaczyć.
5.  Znajdź moduł „Dostęp do produktów”. Powinieneś tam zobaczyć pole na wiadomość, gotowe do tłumaczenia.

**P: Czy ten moduł spowolni mój sklep?**
O: Moduł został zaprojektowany tak, aby był lekki i wydajny. Integruje się bezpośrednio z podstawową logiką produktów i koszyka PrestaShop. Wszelki wpływ na wydajność powinien być znikomy, zwłaszcza po buforowaniu. Jeśli zauważysz znaczne spowolnienia, upewnij się, że Twój serwer spełnia minimalne wymagania PrestaShop i że używasz najnowszej wersji PHP.

**P: Co się stanie, jeśli klient należy do wielu grup, a jedna grupa jest dozwolona, a inna nie?**
O: Jeśli klient należy do *jakiejkolwiek* grupy, która ma wyraźnie dozwolony dostęp do produktu, będzie miał dostęp. Moduł przyznaje dostęp, jeśli *którakolwiek* z grup klienta pasuje do dozwolonej grupy dla tego produktu. Jest to logika „LUB”: jeśli Grupa A jest dozwolona LUB Grupa B jest dozwolona, a klient należy do Grupy A, otrzymuje dostęp.

**P: Czy mogę ograniczyć dostęp do całych kategorii zamiast pojedynczych produktów?**
O: Ten moduł koncentruje się na ograniczeniach pojedynczych produktów. Aby ograniczyć całe kategorie, musiałbyś zastosować ograniczenie do każdego produktu w tej kategorii. W przypadku ograniczeń na poziomie kategorii, możesz potrzebować innego modułu lub niestandardowego rozwoju.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Dostęp do produktów” (`pga`) działa głównie poprzez nadpisywanie podstawowych klas PrestaShop w celu wstrzyknięcia logiki kontroli dostępu. Wykorzystuje `ObjectModel` PrestaShop do przechowywania konfiguracji i modyfikuje widoczność produktów oraz zachowanie koszyka w kluczowych punktach cyklu życia żądania front-office. Główna logika modułu znajduje się w `index.php` (główny plik modułu) i jego nadpisaniach.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu (`pga/index.php`).

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł wykorzystuje mechanizm nadpisywania PrestaShop do modyfikowania podstawowego zachowania.

-   `pga/override/classes/Pack.php`

    -   **Nazwa klasy:** `Pack` (nadpisuje klasę `Pack` PrestaShop)
    -   **Odpowiedzialność:** To nadpisanie prawdopodobnie modyfikuje sposób obsługi pakietów produktów, w szczególności w odniesieniu do widoczności i dostępu do produktów. Zapewnia, że jeśli produkt w pakiecie jest objęty ograniczeniami, sam pakiet przestrzega tych ograniczeń. Jest to kluczowe dla utrzymania spójnej kontroli dostępu do produktów w pakietach.
    -   **Kluczowe metody (prawdopodobnie zmodyfikowane/dodane):** Metody związane z `getPackProducts()` lub `isPack()` mogą być rozszerzone w celu filtrowania produktów na podstawie ograniczeń `pga`.
-   `pga/override/classes/shop/Shop.php`

    -   **Nazwa klasy:** `Shop` (nadpisuje klasę `Shop` PrestaShop)
    -   **Odpowiedzialność:** To nadpisanie jest mniej powszechne dla modułów dostępu do produktów i sugeruje głębszą integrację. Może być używane do zapewnienia, że ograniczenia produktów są poprawnie stosowane w różnych sklepach w środowisku wielu sklepów, lub do modyfikowania sposobu pobierania danych produktów na bardzo podstawowym poziomie, potencjalnie wpływając na zapytania o produkty.
    -   **Kluczowe metody (prawdopodobnie zmodyfikowane/dodane):** Metody takie jak `getProducts()` lub `getProductById()` mogą być rozszerzone w celu filtrowania wyników na podstawie reguł `pga`, zanim zostaną zwrócone przez kontekst `Shop`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `pga/views/js/pga.js`
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Ten skrypt jest prawdopodobnie odpowiedzialny za poprawę doświadczenia użytkownika na stronie konfiguracji modułu. Może obsługiwać wywołania AJAX do wyszukiwania produktów, dynamiczne aktualizacje tabeli ograniczeń produktów lub walidację po stronie klienta dla formularza konfiguracji.
    -   **Kluczowa funkcjonalność:**
        -   Słuchacze zdarzeń dla pól wejściowych wyszukiwania produktów (np. zdarzenia `keyup` do wyzwalania sugestii AJAX).
        -   Żądania AJAX do punktu końcowego modułu (za pośrednictwem `AdminController` lub `index.php?fc=module&module=pga&controller=ajax`) w celu pobrania danych produktów lub zapisania ograniczeń.
        -   Manipulacja DOM w celu wyświetlania wyników wyszukiwania, dodawania wybranych produktów do listy ograniczeń lub aktualizowania wiadomości.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `pga/views/css/pga.css`
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Zapewnia stylizację interfejsu konfiguracji modułu w Panelu administracyjnym PrestaShop.
    -   **Główne komponenty interfejsu użytkownika:** Style dla pola wyszukiwania produktów, tabeli ograniczeń produktów, przycisków i wszelkich niestandardowych elementów wprowadzonych przez metodę `getContent()` modułu.
    -   **Kluczowe selektory klas CSS:** Programiści mogą sprawdzić wyjście HTML modułu w Panelu administracyjnym, aby zidentyfikować konkretne klasy (np. `.pga-product-search`, `.pga-restriction-table`) w celu potencjalnych nadpisań, jeśli wymagana jest niestandardowa stylizacja motywu administracyjnego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Wszystkie szablony są przeznaczone do konfiguracji Panelu administracyjnego.

-   `pga/views/templates/admin/AdminTab.tpl`

    -   **Cel:** Ten szablon jest prawdopodobnie ogólnym opakowaniem lub częściowym szablonem używanym w głównym widoku konfiguracji. Może definiować strukturę dla interfejsu z zakładkami lub wspólny nagłówek/stopkę dla stron administracyjnych.
-   `pga/views/templates/admin/csv.tpl`

    -   **Cel:** Sugeruje funkcjonalność związaną z importem/eksportem CSV ograniczeń produktów. Ten szablon renderowałby interfejs do przesyłania pliku CSV lub generowania go.
-   `pga/views/templates/admin/csv_file.tpl`

    -   **Cel:** Podszablon lub część używana przez `csv.tpl`, prawdopodobnie do wyświetlania formularza przesyłania plików lub listy plików CSV.
-   `pga/views/templates/admin/customerGroups.tpl`

    -   **Cel:** Ten szablon jest kluczowy dla funkcjonalności „Wybierz grupy klientów”. Renderuje listę grup klientów z polami wyboru lub rozwijaną listą wielokrotnego wyboru, umożliwiając administratorowi wybór, które grupy są dozwolone dla konkretnego produktu.
-   `pga/views/templates/admin/main.tpl`

    -   **Cel:** Jest to główny szablon strony konfiguracji modułu (renderowany przez `getContent()`). Koordynuje wszystkie inne części i wyświetla ogólne ustawienia, tabelę ograniczeń produktów oraz formularze dodawania/edycji ograniczeń.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł przechowuje swoją konfigurację w tabeli `ps_configuration` PrestaShop dla ustawień ogólnych (np. `PGA_ENABLED`, `PGA_BLOCK_VIEW`, `PGA_HIDE_LISTS`, `PGA_MESSAGE`).
    -   Dla ograniczeń specyficznych dla produktów, moduł prawdopodobnie tworzy niestandardową tabelę bazy danych (np. `ps_pga_product_group`) do przechowywania mapowania między `id_product` a `id_group`. Metoda `install()` w `pga/index.php` zdefiniowałaby tę tabelę.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używany do ładowania CSS/JS specyficznych dla modułu dla wyświetlania w front-office (np. jeśli niestandardowa wiadomość wymaga stylizacji) lub do wykonywania wczesnych sprawdzeń przekierowania strony produktu. |
| `displayRightColumn` / `displayLeftColumn` | W prawej/lewej kolumnie bocznej stron front-office. | Mniej prawdopodobne dla tego modułu, ale może być używane do wyświetlania niestandardowego bloku (np. „Zaloguj się, aby uzyskać ekskluzywny dostęp”), jeśli jest skonfigurowane. |
| `displayProductButtons` / `displayProductActions` (lub podobne hooki strony produktu) | Na stronie produktu, w pobliżu przycisku „Dodaj do koszyka”. | Używany do ukrywania lub wyłączania przycisku „Dodaj do koszyka” dla nieautoryzowanych użytkowników lub do wyświetlania niestandardowej wiadomości o ograniczeniu. |
| `displayFooter` | W stopce każdej strony front-office. | Mniej powszechne dla podstawowej funkcjonalności, ale może być używane do późno ładowanych skryptów lub analiz związanych z dostępem do produktów. |
| `actionCartSave` / `actionObjectCartAddAfter` (lub podobne hooki koszyka) | Gdy produkt jest dodawany lub zapisywany w koszyku. | **KRYTYCZNE:** To tutaj moduł przechwytuje proces koszyka, aby sprawdzić, czy dodany produkt jest objęty ograniczeniami dla grupy bieżącego klienta. Jeśli jest objęty ograniczeniami, zapobiega dodaniu lub oznacza element jako nieprawidłowy, wyświetlając niestandardową wiadomość. |
| `actionProductListOverride` (lub podobne hooki list produktów) | Gdy PrestaShop generuje listę produktów (np. strona kategorii, wyniki wyszukiwania). | **KRYTYCZNE:** Używany do filtrowania produktów objętych ograniczeniami z list produktów, jeśli „Ukryj produkt na listach produktów” jest włączone. |
| `actionDispatcherBefore` / `actionFrontControllerSetMedia` | Przed wysłaniem kontrolera front-office lub przed ustawieniem zasobów multimedialnych. | Może być używany do implementacji logiki przekierowania dla „Zablokuj możliwość przeglądania strony produktu” poprzez sprawdzenie żądanego identyfikatora produktu pod kątem ograniczeń. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Dostęp do produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
