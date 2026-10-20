---
title: "Atrybuty listy produktów (kombinacje) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Atrybuty listy produktów (kombinacje)” od MyPresta.eu."
sidebar:
  label: "Atrybuty listy produktów (kombinacje)"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product list attributes (combinations) na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-list-attributes-combinations.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-list-attributes-combinations/)
>
> ---


# Atrybuty listy produktów (kombinacje)

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „Atrybuty listy produktów (kombinacje)”. Tutaj kontrolujesz, jak kombinacje są wyświetlane na listach produktów.

#### Ustawienia ogólne

-   **Wyświetlaj kombinacje na liście produktów:**
    -   **Co robi to ustawienie:** To jest główny przełącznik modułu. Kontroluje, czy kombinacje produktów są w ogóle wyświetlane na stronach z listą produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł wstrzyknie interfejs wyboru kombinacji do szablonów listy produktów, umożliwiając klientom bezpośredni wybór wariantów.
        -   *Gdy wyłączone (NIE):* Moduł będzie nieaktywny w front office, a listy produktów będą zachowywać się jak standardowy PrestaShop, wymagając od klientów odwiedzenia strony produktu w celu wybrania kombinacji.
    -   **Zalecana wartość:** TAK (aby wykorzystać podstawową funkcjonalność modułu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zaoferować szybsze zakupy, włącz to. Jeśli wolisz, aby klienci zawsze trafiali na stronę produktu w celu uzyskania szczegółów, wyłącz to.

-   **Wyświetl przycisk „Dodaj do koszyka”:**
    -   **Co robi to ustawienie:** Określa, czy przycisk „Dodaj do koszyka” jest wyświetlany obok selektorów kombinacji na liście produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Przycisk „Dodaj do koszyka” pojawi się obok opcji kombinacji. Po wybraniu kombinacji klient może kliknąć ten przycisk, aby dodać ją do koszyka.
        -   *Gdy wyłączone (NIE):* Selektory kombinacji będą nadal widoczne, ale klienci będą musieli kliknąć obraz produktu lub nazwę, aby przejść do strony produktu i dodać go do koszyka. Może to być przydatne, jeśli chcesz pokazać opcje, ale nadal zachęcać do odwiedzania stron produktów.
    -   **Zalecana wartość:** TAK (dla maksymalnej wygody i konwersji).
    -   **Scenariusz / przykład dla sprzedawcy:** Aby uzyskać szybkie zakupy, włącz to. Jeśli Twoje produkty wymagają obszernego czytania lub dostosowywania przed zakupem, możesz to wyłączyć, aby skierować klientów na stronę produktu.

-   **Wyświetl pole ilości:**
    -   **Co robi to ustawienie:** Kontroluje, czy pole wprowadzania ilości jest wyświetlane obok przycisku „Dodaj do koszyka” na liście produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Klienci mogą określić ilość wybranej kombinacji, którą chcą dodać do koszyka, bezpośrednio z listy produktów.
        -   *Gdy wyłączone (NIE):* Przycisk „Dodaj do koszyka” doda pojedynczą jednostkę wybranej kombinacji. Klienci musieliby wtedy dostosować ilości w koszyku lub na stronie produktu.
    -   **Zalecana wartość:** TAK (dla większości sklepów, ponieważ oferuje większą elastyczność).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli klienci często kupują wiele sztuk tego samego przedmiotu (np. skarpetki, artykuły papiernicze), włącz to. Jeśli Twoje produkty są zazwyczaj kupowane pojedynczo, możesz to wyłączyć, aby uzyskać czystszy wygląd.

-   **Wyświetl referencję produktu:**
    -   **Co robi to ustawienie:** Pokazuje lub ukrywa numer referencyjny produktu (SKU) obok opcji kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Referencja produktu będzie widoczna, co może być pomocne dla klientów śledzących konkretne przedmioty lub dla klientów B2B.
        -   *Gdy wyłączone (NIE):* Referencja nie będzie wyświetlana, co prowadzi do czystszego, mniej zaśmieconego interfejsu.
    -   **Zalecana wartość:** NIE (chyba że Twoja grupa docelowa wyraźnie korzysta z widoczności referencji).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla sklepów B2B lub produktów technicznych, gdzie klienci często zamawiają według SKU, włącz to. W przypadku ogólnego handlu detalicznego zazwyczaj nie jest to konieczne.

-   **Wyświetl EAN13/JAN produktu:**
    -   **Co robi to ustawienie:** Pokazuje lub ukrywa numer kodu kreskowego EAN13 lub JAN produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* EAN13/JAN będzie widoczny, co może być przydatne dla klientów, którzy muszą porównywać produkty za pomocą tych identyfikatorów.
        -   *Gdy wyłączone (NIE):* EAN13/JAN nie będzie wyświetlany.
    -   **Zalecana wartość:** NIE (podobnie jak referencja, włącz tylko wtedy, gdy istnieje specyficzna potrzeba klienta).
    -   **Scenariusz / przykład dla sprzedawcy:** Rzadko potrzebne do wyświetlania w front office, ale może być przydatne dla specyficznych nisz lub B2B.

-   **Wyświetl UPC produktu:**
    -   **Co robi to ustawienie:** Pokazuje lub ukrywa numer kodu kreskowego UPC produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* UPC będzie widoczne.
        -   *Gdy wyłączone (NIE):* UPC nie będzie wyświetlane.
    -   **Zalecana wartość:** NIE (podobnie jak EAN13/JAN).
    -   **Scenariusz / przykład dla sprzedawcy:** Podobnie jak EAN13/JAN, zazwyczaj nie jest to wymóg front office dla większości handlu detalicznego.

-   **Wyświetl wagę produktu:**
    -   **Co robi to ustawienie:** Pokazuje lub ukrywa wagę produktu obok opcji kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Waga produktu będzie widoczna, co może być ważne dla klientów dbających o koszty wysyłki lub obsługę.
        -   *Gdy wyłączone (NIE):* Waga nie będzie wyświetlana.
    -   **Zalecana wartość:** NIE (chyba że waga jest krytycznym czynnikiem dla Twoich produktów).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla produktów, gdzie waga jest istotnym czynnikiem zakupu (np. towary masowe, ciężkie części maszyn), włącz to.

-   **Wyświetl cenę produktu:**
    -   **Co robi to ustawienie:** Kontroluje, czy cena wybranej kombinacji jest dynamicznie aktualizowana i wyświetlana na liście produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Gdy klient wybiera różne kombinacje, wyświetlana cena zostanie zaktualizowana, aby odzwierciedlić cenę konkretnej kombinacji (w tym wszelkie wpływy cen atrybutów).
        -   *Gdy wyłączone (NIE):* Cena wyświetlana na liście produktów pozostanie ceną podstawową produktu, a klienci mogą potrzebować wywnioskować ceny kombinacji lub przejść do strony produktu.
    -   **Zalecana wartość:** TAK (kluczowe dla przejrzystości i świadomego zakupu).
    -   **Scenariusz / przykład dla sprzedawcy:** Zawsze włącz to dla jasnych cen. Jeśli wyłączone, klienci mogą być zdezorientowani zmianami cen przy kasie.

-   **Wyświetl dostępność produktu:**
    -   **Co robi to ustawienie:** Pokazuje lub ukrywa status dostępności magazynowej dla wybranej kombinacji (np. „W magazynie”, „Brak w magazynie”, „Ostatnie sztuki!”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Klienci zobaczą status magazynowy, co pomoże im w podejmowaniu decyzji zakupowych i zapobiegnie frustracji z prób zamawiania produktów niedostępnych.
        -   *Gdy wyłączone (NIE):* Status magazynowy nie będzie wyświetlany, co potencjalnie może prowadzić do prób dodawania przez klientów niedostępnych produktów do koszyka.
    -   **Zalecana wartość:** TAK (wysoce zalecane do zarządzania oczekiwaniami klientów).
    -   **Scenariusz / przykład dla sprzedawcy:** Niezbędne dla każdego sklepu, aby zapobiec zamówieniom na niedostępne przedmioty. Zawsze włącz.

-   **Wyświetl opis produktu:**
    -   **Co robi to ustawienie:** Pokazuje lub ukrywa krótki opis produktu poniżej kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Pojawi się krótki opis produktu, oferując więcej kontekstu bez konieczności klikania na stronę produktu.
        -   *Gdy wyłączone (NIE):* Opis nie będzie wyświetlany, co sprawi, że lista produktów będzie zwięzła.
    -   **Zalecana wartość:** NIE (listy produktów są zazwyczaj do szybkiego przeglądania; szczegółowe opisy należą do strony produktu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz bardzo krótkie, wpływowe opisy, które pomagają w szybkich decyzjach, możesz to włączyć. W przeciwnym razie wyłącz to, aby uniknąć bałaganu.

-   **Wyświetl krótki opis produktu:**
    -   **Co robi to ustawienie:** Podobnie jak „Wyświetl opis produktu”, ale konkretnie dla pola krótkiego opisu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Krótki opis produktu będzie widoczny.
        -   *Gdy wyłączone (NIE):* Krótki opis nie będzie wyświetlany.
    -   **Zalecana wartość:** NIE (z tych samych powodów co pełny opis).
    -   **Scenariusz / przykład dla sprzedawcy:** Używaj oszczędnie, tylko jeśli Twoje krótkie opisy są niezwykle zwięzłe i kluczowe dla zakupu z widoku listy.

-   **Wyświetl obrazy produktu:**
    -   **Co robi to ustawienie:** Określa, czy obraz produktu aktualizuje się dynamicznie, gdy klient wybierze inną kombinację (np. wybranie „niebieskiej” koszuli pokazuje obraz niebieskiej koszuli).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Główny obraz produktu na liście zmieni się, aby odzwierciedlić obraz związany z wybraną kombinacją. Zapewnia to bogatą wizualną informację zwrotną.
        -   *Gdy wyłączone (NIE):* Obraz produktu pozostanie statyczny, pokazując domyślny obraz produktu niezależnie od wybranej kombinacji.
    -   **Zalecana wartość:** TAK (wysoce zalecane dla wizualnego potwierdzenia i lepszego doświadczenia użytkownika).
    -   **Scenariusz / przykład dla sprzedawcy:** Kluczowe dla odzieży, elektroniki lub dowolnego produktu, gdzie wizualna reprezentacja wariantu jest ważna.

-   **Wyświetl atrybuty produktu jako:**
    -   **Co robi to ustawienie:** To kluczowe ustawienie, które definiuje, w jaki sposób opcje kombinacji (np. rozmiar, kolor) są prezentowane klientowi.
    -   **Efekt zmiany tego ustawienia:**
        -   *Lista rozwijana:* Atrybuty pojawią się jako standardowe elementy HTML `<select>` (rozwijane listy). Jest to kompaktowe i odpowiednie dla wielu opcji.
        -   *Przyciski radiowe:* Atrybuty pojawią się jako przyciski radiowe. Dobre dla małej liczby odrębnych opcji.
        -   *Wybór koloru:* Jeśli Twoje atrybuty są zdefiniowane jako typ „kolor” w PrestaShop, wyświetli je jako klikalne próbki kolorów.
    -   **Zalecana wartość:**
        -   *Wybór koloru* dla atrybutów koloru.
        -   *Lista rozwijana* dla atrybutów z wieloma opcjami (np. rozmiary S-XXL).
        -   *Przyciski radiowe* dla atrybutów z niewielką liczbą odrębnych opcji (np. „Tak/Nie”, „Z/Bez”).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla sklepu odzieżowego prawdopodobnie użyjesz „Wybór koloru” dla kolorów i „Listy rozwijanej” dla rozmiarów. Dla prostego produktu z dwoma opcjami, takimi jak „Zapakowane na prezent: Tak/Nie”, przyciski radiowe mogą być najlepsze.

-   **Wyświetl atrybuty produktu dla:**
    -   **Co robi to ustawienie:** Pozwala określić, które atrybuty produktu powinny mieć swoje kombinacje wyświetlane na liście produktów. Możesz wybrać konkretne grupy atrybutów (np. „Rozmiar”, „Kolor”, „Materiał”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Wybrane grupy atrybutów:* Wyświetlane będą tylko kombinacje obejmujące wybrane grupy atrybutów. Na przykład, jeśli wybierzesz „Kolor” i „Rozmiar”, klienci zobaczą opcje kolorów i rozmiarów.
        -   *Brak wyboru:* Jeśli nic nie zostanie wybrane, moduł może domyślnie wyświetlać wszystkie atrybuty lub żadne, w zależności od wewnętrznej logiki modułu. Najlepiej jest wyraźnie wybrać.
    -   **Zalecana wartość:** Wybierz wszystkie odpowiednie grupy atrybutów, które definiują Twoje kombinacje produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz T-shirty w różnych kolorach i rozmiarach, wybierz „Kolor” i „Rozmiar”. Jeśli masz również atrybut „Materiał”, ale nie chcesz go wyświetlać na liście, pozostaw go niewybranym.

-   **Hook do wyświetlania modułu:**
    -   **Co robi to ustawienie:** Określa, gdzie na stronach z listą produktów zostaną wstrzyknięte selektory kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   `displayProductListFunctionalButtons`: Ten hook jest zazwyczaj umieszczony w pobliżu przycisku „Dodaj do koszyka” lub innych elementów funkcjonalnych na elementach listy produktów.
        -   `displayProductListReviews`: Często w pobliżu gwiazdek recenzji lub liczby recenzji.
        -   `displayProductListPrice`: Zazwyczaj w pobliżu ceny produktu.
        -   `displayProductListExtraContent`: Ogólny hook dla dodatkowej zawartości, często na dole karty produktu.
        -   `displayProductListFooter`: Na samym dole karty produktu.
    -   **Zalecana wartość:** `displayProductListFunctionalButtons` lub `displayProductListExtraContent` to popularne wybory, ale zależy to w dużej mierze od układu Twojego motywu. Może być konieczne eksperymentowanie, aby znaleźć najlepsze wizualne umiejscowienie.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma czysty obszar poniżej nazwy produktu i ceny, `displayProductListFunctionalButtons` może pasować. Jeśli chcesz, aby opcje pojawiały się bardziej widocznie, `displayProductListExtraContent` może być lepsze.

-   **Wyklucz produkty z modułu:**
    -   **Co robi to ustawienie:** Pozwala określić pojedyncze produkty według ich ID, które *nie* powinny wyświetlać kombinacji na liście produktów, nawet jeśli moduł jest ogólnie włączony.
    -   **Efekt zmiany tego ustawienia:**
        -   *Wprowadzanie ID produktów (rozdzielone przecinkami):* Określone produkty powrócą do standardowego zachowania PrestaShop na listach produktów, wymagając kliknięcia na stronę produktu w celu wyboru kombinacji.
        -   *Pozostawienie pustego:* Wszystkie produkty z kombinacjami będą je wyświetlać na liście.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne produkty, które wymagają pełnej wizyty na stronie produktu.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz mieć kilka złożonych produktów z wieloma atrybutami lub produktów, które wymagają szczegółowego konfiguratora, gdzie wolisz, aby klienci najpierw trafili na stronę produktu.

-   **Wyklucz kategorie z modułu:**
    -   **Co robi to ustawienie:** Pozwala określić kategorie według ich ID, które *nie* powinny wyświetlać kombinacji na swoich listach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Wprowadzanie ID kategorii (rozdzielone przecinkami):* Produkty w tych kategoriach nie będą wyświetlać kombinacji na swoich odpowiednich stronach z listą.
        -   *Pozostawienie pustego:* Wszystkie kategorie będą wyświetlać kombinacje produktów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne kategorie, w których ta funkcja nie jest pożądana.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz kategorię „Wyprzedaż”, gdzie wszystkie produkty są jednowariantowe i chcesz zachować bardzo minimalistyczny wygląd, możesz ją wykluczyć.

#### 2.1.1 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Wyświetlaj kombinacje na liście produktów | TAK | Główny przełącznik do włączania/wyłączania wyświetlania kombinacji na listach produktów. |
| Konfiguracja modułu | Wyświetl przycisk „Dodaj do koszyka” | TAK | Pokazuje przycisk „Dodaj do koszyka” obok kombinacji do bezpośredniego zakupu. |
| Konfiguracja modułu | Wyświetl pole ilości | TAK | Pozwala klientom wybrać ilość bezpośrednio na liście produktów. |
| Konfiguracja modułu | Wyświetl referencję produktu | NIE | Pokazuje/ukrywa SKU produktu. |
| Konfiguracja modułu | Wyświetl EAN13/JAN produktu | NIE | Pokazuje/ukrywa EAN13/JAN produktu. |
| Konfiguracja modułu | Wyświetl UPC produktu | NIE | Pokazuje/ukrywa UPC produktu. |
| Konfiguracja modułu | Wyświetl wagę produktu | NIE | Pokazuje/ukrywa wagę produktu. |
| Konfiguracja modułu | Wyświetl cenę produktu | TAK | Dynamicznie aktualizuje cenę na podstawie wybranej kombinacji. |
| Konfiguracja modułu | Wyświetl dostępność produktu | TAK | Pokazuje status magazynowy dla wybranej kombinacji. |
| Konfiguracja modułu | Wyświetl opis produktu | NIE | Pokazuje/ukrywa pełny opis produktu. |
| Konfiguracja modułu | Wyświetl krótki opis produktu | NIE | Pokazuje/ukrywa krótki opis produktu. |
| Konfiguracja modułu | Wyświetl obrazy produktu | TAK | Dynamicznie aktualizuje obraz produktu na podstawie wybranej kombinacji. |
| Konfiguracja modułu | Wyświetl atrybuty produktu jako | Rozwijana lista, Przyciski radiowe, Wybór koloru | Definiuje wizualną prezentację opcji atrybutów. |
| Konfiguracja modułu | Wyświetl atrybuty produktu dla | Wybierz odpowiednie grupy | Określa, które grupy atrybutów mają być wyświetlane. |
| Konfiguracja modułu | Hook do wyświetlania modułu | `displayProductListFunctionalButtons` | Określa wizualne umiejscowienie modułu na kartach produktów. |
| Konfiguracja modułu | Wyklucz produkty z modułu | Pozostaw puste | ID produktów rozdzielone przecinkami do wykluczenia z funkcji. |
| Konfiguracja modułu | Wyklucz kategorie z modułu | Pozostaw puste | ID kategorii rozdzielone przecinkami do wykluczenia z funkcji. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł używa niestandardowych kontrolerów administracyjnych do wewnętrznego zarządzania, ale zazwyczaj nie są one bezpośrednio dostępne dla sprzedawcy w celu codziennej konfiguracji. Służą one głównie do wewnętrznych operacji modułu lub zaawansowanego debugowania.

#### 2.2.1 AdminPlaSearchController (Panel administracyjny > Moduły > Atrybuty listy produktów (kombinacje) > Konfiguracja wyszukiwania)
-   **Nazwa ekranu i lokalizacja w menu:** Ten kontroler jest prawdopodobnie używany do wewnętrznej konfiguracji wyszukiwania lub zarządzania danymi związanymi z indeksowaniem lub pobieraniem kombinacji. Może nie mieć bezpośredniego, widocznego elementu menu dla sprzedawcy, lub może być wewnętrzną zakładką w głównej konfiguracji modułu.
-   **Dostępne akcje i ustawienia:** Ten ekran zazwyczaj przedstawiałby widok siatki lub listy danych (np. indeksowane produkty, mapowania atrybutów) i mógłby oferować akcje takie jak „Przebuduj indeks”, „Wyczyść pamięć podręczną” lub „Edytuj ustawienia wyszukiwania”.
-   **Efekt zmian:** Zmiany tutaj wpłynęłyby na wydajność lub dokładność wyświetlania kombinacji, zwłaszcza w dużych katalogach. Nieprawidłowe ustawienia mogłyby prowadzić do tego, że kombinacje nie pojawiałyby się lub ładowałyby się wolno.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Sprzedawcy zazwyczaj nie muszą wchodzić w interakcje z tym ekranem, chyba że zostaną poinformowani przez wsparcie lub w celu zaawansowanego rozwiązywania problemów. Główna strona konfiguracji modułu obsługuje wszystkie ustawienia skierowane do użytkownika.

#### 2.2.2 index.php (pla/controllers/admin/index.php)
-   **Nazwa ekranu i lokalizacja w menu:** Ten plik `index.php` w katalogu kontrolera `admin` jest powszechną praktyką PrestaShop, aby zapobiec listowaniu katalogów. Zazwyczaj nie reprezentuje ekranu skierowanego do użytkownika, ale raczej zapewnia bezpieczeństwo i prawidłowe routowanie dla innych kontrolerów administracyjnych w module.
-   **Dostępne akcje i ustawienia:** Brak bezpośrednich akcji lub ustawień skierowanych do sprzedawcy.
-   **Efekt zmian:** Brak bezpośredniego wpływu na wyświetlanie sklepu lub dane, ponieważ jest to plik strukturalny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Nie wymaga interakcji.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Kombinacje nie pojawiają się na mojej liście produktów. Co powinienem zrobić?**
O:
1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Atrybuty listy produktów (kombinacje)” i upewnij się, że jest zainstalowany i włączony.
2.  **Sprawdź konfigurację modułu:** Przejdź do strony konfiguracji modułu. Upewnij się, że „Wyświetlaj kombinacje na liście produktów” jest ustawione na TAK.
3.  **Sprawdź grupy atrybutów:** Upewnij się, że wybrałeś prawidłowe grupy „Wyświetl atrybuty produktu dla” (np. „Rozmiar”, „Kolor”).
4.  **Sprawdź wykluczenia:** Sprawdź, czy testowany produkt lub kategoria nie jest wymieniona w „Wyklucz produkty z modułu” lub „Wyklucz kategorie z modułu”.
5.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają wyświetlanie nowej zawartości modułu.
6.  **Kompatybilność z motywem:** Twój motyw może być mocno dostosowany i nie używać standardowych hooków PrestaShop. Spróbuj zmienić ustawienie „Hook do wyświetlania modułu” na inny hook (np. `displayProductListExtraContent`) i wyczyść pamięć podręczną. Jeśli problemy nadal występują, skontaktuj się z webmasterem lub wsparciem MyPresta.eu.

**P: Przycisk „Dodaj do koszyka” lub pole ilości nie są wyświetlane.**
O:
1.  **Sprawdź konfigurację modułu:** Upewnij się, że „Wyświetl przycisk 'Dodaj do koszyka'” i „Wyświetl pole ilości” są ustawione na TAK w konfiguracji modułu.
2.  **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P: Obraz produktu nie zmienia się, gdy wybieram inną kombinację.**
O:
1.  **Sprawdź konfigurację modułu:** Upewnij się, że „Wyświetl obrazy produktu” jest ustawione na TAK.
2.  **Obrazy produktów:** Sprawdź, czy Twoje kombinacje produktów faktycznie mają przypisane obrazy. Na stronie produktu w panelu administracyjnym przejdź do zakładki „Kombinacje” i upewnij się, że każda kombinacja ma do niej przypisane obrazy.
3.  **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop.

**P: Stylizacja (kolory, wyrównanie) kombinacji wygląda źle w moim sklepie.**
O:
Jest to zazwyczaj konflikt CSS z Twoim motywem.
1.  **Wyczyść pamięć podręczną:** Czasami pomaga wyczyszczenie pamięci podręcznej.
2.  **Dostosowanie motywu:** Twój motyw może mieć specyficzne reguły stylizacji, które nadpisują lub kolidują z domyślnym CSS modułu. Wymaga to od webmastera lub programisty sprawdzenia CSS i wprowadzenia zmian w arkuszu stylów Twojego motywu. Moduł dostarcza własne pliki CSS, ale motywy zawsze mogą je nadpisać.

**P: Czy ten moduł działa ze sklepami wielojęzycznymi?**
O: Tak, moduł jest zaprojektowany tak, aby był kompatybilny z funkcjami wielojęzycznymi PrestaShop. Nazwy i wartości atrybutów będą wyświetlane w wybranym języku front office, pod warunkiem, że są poprawnie przetłumaczone w panelu administracyjnym PrestaShop (Katalog > Atrybuty i cechy).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Atrybuty listy produktów (kombinacje)” dla programistów i webmasterów.

### 4.1 Przegląd architektury
Moduł stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), głównie rozszerzając `Module` dla swojej podstawowej funkcjonalności i `ModuleFrontController` dla interakcji AJAX. Wykorzystuje system hooków PrestaShop do wstrzykiwania swojej zawartości do szablonów list produktów. Główna logika modułu znajduje się w `index.php` (główny plik modułu), który obsługuje instalację, deinstalację i metodę `getContent()` dla konfiguracji w panelu administracyjnym. Wyświetlanie w front office jest zarządzane za pomocą szablonów Smarty renderowanych za pośrednictwem hooków, z dynamicznymi interakcjami zasilanymi przez JavaScript i AJAX.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office
-   `controllers/front/ajax.php`
    *   **Nazwa klasy i klasa nadrzędna:** `PlaAjaxModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler obsługuje wszystkie żądania AJAX z front office. Gdy klient wchodzi w interakcję z selektorami kombinacji (np. zmienia rozmiar lub kolor), ten kontroler jest odpowiedzialny za odbieranie żądania, przetwarzanie go (np. pobieranie zaktualizowanych cen, stanu magazynowego, obrazów dla wybranej kombinacji) i zwracanie odpowiedzi JSON w celu dynamicznej aktualizacji front-endu bez pełnego przeładowania strony. Jest to kluczowe dla interaktywnego doświadczenia modułu.
-   `controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** `PlaIndexModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Jest to kontroler frontowy-placeholder, często używany do zapobiegania listowaniu katalogów lub jako rezerwowy dla tras specyficznych dla modułu. W kontekście tego modułu może nie mieć bezpośredniego, aktywnego routingu, ale służy jako standardowa praktyka PrestaShop. Główna interakcja z front office odbywa się za pośrednictwem `ajax.php`.

#### Kontrolery administracyjne Back-Office
-   `controllers/admin/AdminPlaSearchController.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminPlaSearchController` rozszerza `ModuleAdminController`.
    *   **Nazwa zakładki i zarządzana encja:** Ten kontroler prawdopodobnie zarządza wewnętrznymi mechanizmami wyszukiwania lub indeksowania kombinacji produktów. Może nie mieć bezpośredniego wpisu w menu, ale może być wewnętrznie dostępny przez moduł do zadań takich jak przebudowa indeksu wyszukiwania dla kombinacji. Zazwyczaj zarządzałby wirtualną encją związaną z danymi wyszukiwania, a nie bezpośrednim `ObjectModel`.
-   `controllers/admin/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** Nie jest to bezpośrednia klasa kontrolera, ale standardowy plik `index.php`.
    *   **Nazwa zakładki i zarządzana encja:** Ten plik jest środkiem bezpieczeństwa, aby zapobiec listowaniu katalogów folderu `admin`. Sam w sobie nie reprezentuje funkcjonalnego ekranu administracyjnego.

### 4.3 Klasy podstawowe i modele (`classes/`)
Dossier modułu wskazuje brak niestandardowych klas lub modeli w katalogu `classes/`. Sugeruje to, że moduł działa głównie poprzez rozszerzanie istniejących podstawowych funkcjonalności PrestaShop (takich jak `Product`, `Combination`) i używa bezpośrednich zapytań do bazy danych lub klasy `Db` PrestaShop do interakcji z danymi, zamiast definiować własne encje `ObjectModel`. Cała podstawowa logika jest prawdopodobnie hermetyzowana w głównym pliku modułu (`pla/index.php`) i jego kontrolerach.

### 4.4 Zasoby JavaScript (`views/js/`)
-   `pla/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Potencjalnie zarówno Front-office (dla funkcji wyszukiwania na żywo, jeśli zintegrowana) i Back-office (dla pól wyszukiwania administracyjnego). Biorąc pod uwagę fokus modułu, jest to bardziej prawdopodobne dla konfiguracji wyszukiwania w panelu administracyjnym związanej z `AdminPlaSearchController`.
    *   **Szczegóły:** Obsługuje funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania produktów lub atrybutów w konfiguracji administracyjnej modułu lub niestandardowej funkcji wyszukiwania. Wiązałby się z polami wejściowymi, nasłuchiwałby zdarzeń `keyup` i wykonywałby wywołania AJAX w celu pobrania sugestii.
-   `pla/views/templates/js/pla.js`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** To jest główny plik JavaScript dla funkcjonalności front-office.
        *   **Słuchacze zdarzeń:** Wiąże zdarzenia `change` z selektorami kombinacji (rozwijane listy, przyciski radiowe, wybory kolorów) na elementach listy produktów.
        *   **Manipulacja DOM:** Aktualizuje ceny produktów, status magazynowy, obrazy produktów i stany przycisków „Dodaj do koszyka” na podstawie wybranych kombinacji.
        *   **Wywołania AJAX:** Wykonuje żądania AJAX do `controllers/front/ajax.php` w celu pobrania zaktualizowanych danych kombinacji (cena, stan magazynowy, URL obrazu itp.) po zmianie wyboru.
        *   **Inicjalizacja modułu:** Prawdopodobnie zawiera kod do inicjalizacji selektorów kombinacji po załadowaniu strony i ponownej ich inicjalizacji po aktualizacjach AJAX (np. nieskończone przewijanie, filtrowanie kategorii).

### 4.5 Arkusze stylów CSS (`views/css/`)
-   `pla/css.css`
    *   **Zakres:** Prawdopodobnie Front-office.
    *   **Szczegóły:** Ogólna stylizacja elementów wyświetlania kombinacji na listach produktów. Zawiera podstawowe style dla rozwijanych list, przycisków radiowych, pól ilości i przycisków „Dodaj do koszyka” renderowanych przez moduł.
-   `pla/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Potencjalnie zarówno Front-office, jak i Back-office.
    *   **Szczegóły:** Style dla listy sugestii autouzupełniania i pól wejściowych, prawdopodobnie używane w połączeniu z `autocomplete.js`.
-   `pla/views/templates/css/pla-classic.css`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Specyficzna stylizacja dostosowana do starszych motywów PrestaShop (np. motyw Classic lub podobne struktury). Może zawierać bardziej jawne nadpisania lub style rezerwowe.
-   `pla/views/templates/css/pla.css`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Podstawowa stylizacja elementów front-office modułu, potencjalnie dla nowszych wersji PrestaShop lub bardziej ogólnego podejścia. Zawiera style dla wrapperów kombinacji, opcji atrybutów i dynamicznych elementów.
    *   **Kluczowe selektory klas CSS:** Programiści mogą spodziewać się obecności klas takich jak `.pla-combinations-wrapper`, `.pla-attribute-group`, `.pla-attribute-option`, `.pla-add-to-cart-btn`, `.pla-quantity-input`, `.pla-price-display`, `.pla-availability-status` i mogą je nadpisać w pliku `custom.css` lub `theme.css` swojego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)
-   `pla/views/templates/hook/pla.tpl`
    *   **Hook:** Głównie przeznaczony dla hooków takich jak `displayProductListFunctionalButtons`, `displayProductListExtraContent` itp.
    *   **Wyjście:** To jest główny szablon odpowiedzialny za renderowanie selektorów kombinacji, przycisku „Dodaj do koszyka”, pola ilości, ceny i dostępności dla każdego elementu produktu na liście produktów. Iteruje przez dostępne grupy atrybutów i wartości, generując odpowiedni kod HTML (rozwijane listy, przyciski radiowe, próbki kolorów) na podstawie konfiguracji modułu.

#### Szablony administracyjne (`views/templates/admin/`)
-   `pla/views/templates/admin/admin.tpl`
    *   **Cel:** Ten szablon jest używany dla głównej strony konfiguracji modułu w panelu administracyjnym PrestaShop (dostępnej za pośrednictwem `getContent()` w `pla/index.php`). Zawiera formularze dla wszystkich ustawień opisanych w Sekcji 4.1.
-   `pla/views/templates/admin/selectedCa.tpl`
    *   **Cel:** Prawdopodobnie częściowy szablon używany w formularzu administracyjnym lub siatce do wyświetlania wybranych kategorii (np. dla ustawienia „Wyklucz kategorie z modułu”). Renderowałby listę wybranych kategorii, prawdopodobnie z opcjami ich usunięcia.
-   `pla/views/templates/admin/selectedProducts.tpl`
    *   **Cel:** Podobnie jak `selectedCa.tpl`, ale dla wybranych produktów (np. dla ustawienia „Wyklucz produkty z modułu”). Wyświetlałby listę wybranych produktów.

#### Szablony JavaScript (`views/templates/js/`)
-   `pla/views/templates/js/pla_admin.tpl`
    *   **Zakres:** Back-office.
    *   **Wyjście:** Ten szablon prawdopodobnie zawiera kod JavaScript specjalnie dla panelu administracyjnego. Może zawierać skrypty do obsługi dynamicznych elementów formularzy, wywołań AJAX w panelu administracyjnym lub inicjalizacji komponentów na stronie konfiguracji modułu.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych
Dossier modułu wskazuje brak niestandardowych plików SQL. Oznacza to, że moduł przechowuje swoje ustawienia konfiguracyjne głównie w tabeli `ps_configuration` PrestaShop.
-   **`ps_configuration`**: Przechowuje ustawienia modułu (np. `PLA_DISPLAY_COMBINATIONS`, `PLA_DISPLAY_ADD_TO_CART`, `PLA_EXCLUDE_PRODUCTS`, `PLA_HOOK_NAME` itp.). Te klucze są zazwyczaj poprzedzone prefiksem `PLA_` lub `MYPRESTA_PLA_`.

#### Tabela zarejestrowanych hooków
Moduł rejestruje i wykorzystuje kilka hooków PrestaShop do integracji swojej funkcjonalności.

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Aby dołączyć niezbędne pliki CSS i JavaScript dla funkcjonalności front-office modułu. |
| `displayProductListFunctionalButtons` | W każdym elemencie produktu na stronach z listą produktów, zazwyczaj w pobliżu przycisków akcji. | Powszechny hook do wstrzykiwania selektorów kombinacji i przycisku „Dodaj do koszyka”. |
| `displayProductListReviews` | W każdym elemencie produktu na stronach z listą produktów, często w pobliżu elementów recenzji. | Alternatywny hook do wyświetlania opcji kombinacji. |
| `displayProductListPrice` | W każdym elemencie produktu na stronach z listą produktów, w pobliżu ceny produktu. | Alternatywny hook do wyświetlania opcji kombinacji. |
| `displayProductListExtraContent` | Ogólny hook w każdym elemencie produktu dla dodatkowej zawartości. | Elastyczny hook do wstrzykiwania selektorów kombinacji, często na dole karty produktu. |
| `displayProductListFooter` | Na samym dole każdego elementu produktu na stronach z listą produktów. | Kolejny alternatywny hook do wyświetlania opcji kombinacji. |
| `actionFrontControllerSetMedia` | Przed renderowaniem zawartości przez kontroler frontowy, umożliwiając modułom dodawanie zasobów. | Aby warunkowo ładować specyficzne zasoby JS/CSS tylko wtedy, gdy są potrzebne przez moduł na odpowiednich stronach. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w panelu administracyjnym. | Potencjalnie używane do czyszczenia pamięci podręcznej specyficznej dla modułu lub ponownego indeksowania danych kombinacji produktów, jeśli moduł ma wewnętrzny mechanizm indeksowania. |
| `actionAttributeGroupUpdate` / `actionAttributeUpdate` | Po zaktualizowaniu grup atrybutów lub atrybutów. | Podobnie jak `actionProductUpdate`, do czyszczenia pamięci podręcznej lub ponownego indeksowania. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół jest zaangażowany w świadczenie pomocy i zapewnienie płynnego działania Twojego modułu.
