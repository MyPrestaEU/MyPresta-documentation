---
title: "Warunkowe rabaty na zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Warunkowe rabaty na zamówienia” od MyPresta.eu."
sidebar:
  label: "Warunkowe rabaty na zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Conditional Order Discounts na MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-discounts.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/conditional-order-discounts/)
>
> ---


# Warunkowe rabaty na zamówienia

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu.

-   **Włącz warunkowe rabaty na zamówienia:**
    *   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu. Gdy jest włączony, logika modułu do stosowania warunkowych rabatów będzie aktywna w Twoim sklepie. Gdy jest wyłączony, żadne warunkowe rabaty nie zostaną zastosowane, niezależnie od utworzonych polityk.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony:* Moduł rozpocznie ocenę zdefiniowanych polityk rabatowych i stosowanie rabatów lub darmowych prezentów do koszyków klientów, gdy się zakwalifikują.
        *   *Gdy wyłączony:* Wszystkie polityki warunkowych rabatów utworzone za pomocą tego modułu zostaną zignorowane, a żadne rabaty nie zostaną zastosowane.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Właśnie zakończyłeś ustawianie swojej pierwszej polityki „Kup 2, otrzymaj 1 gratis” i chcesz ją uruchomić. Włączyłbyś to ustawienie. Jeśli musisz tymczasowo wstrzymać wszystkie warunkowe rabaty na wyprzedaż w całym sklepie zarządzaną innymi środkami, wyłączyłbyś to.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł Warunkowe rabaty na zamówienia dodaje nową główną pozycję menu do Twojego Panelu administracyjnego PrestaShop, zazwyczaj pod **Katalogiem** lub **Marketingiem**, o nazwie **„Warunkowe rabaty”**. To menu zawiera kilka podpozycji do zarządzania Twoimi politykami i przeglądania dzienników.

#### 2.2.1 Warunkowe rabaty > Polityki (AdminConorderdisPoliciesController)

Tutaj definiujesz i zarządzasz wszystkimi swoimi politykami warunkowych rabatów.

-   **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Warunkowe rabaty > Polityki
-   **Dostępne akcje i ustawienia:**

    *   **Lista polityk:** Zobaczysz tabelę zawierającą listę wszystkich istniejących polityk rabatowych. Każda polityka będzie pokazywać swoją nazwę, status (aktywna/nieaktywna) i inne kluczowe szczegóły.
    *   **Dodaj nową politykę:** Kliknij przycisk „Dodaj nową politykę”, aby utworzyć zupełnie nową regułę warunkowego rabatu.
    *   **Edytuj politykę:** Kliknij ikonę „Edytuj” obok istniejącej polityki, aby zmodyfikować jej warunki, promocje lub ustawienia.
    *   **Duplikuj politykę:** To bardzo przydatna funkcja! Kliknij ikonę „Duplikuj”, aby utworzyć dokładną kopię istniejącej polityki. To oszczędza dużo czasu, jeśli musisz stworzyć podobne promocje.
    *   **Włącz/Wyłącz politykę:** Możesz szybko aktywować lub dezaktywować poszczególne polityki bezpośrednio z listy.
    *   **Usuń politykę:** Usuń politykę ze swojego sklepu.
    *   **Formularz konfiguracji polityki (podczas dodawania/edycji):**
        *   **Nazwa polityki:** Opisowa nazwa do Twojej wewnętrznej referencji (np. „BOGO Koszulki”, „Wydaj 100$ Otrzymaj 10% rabatu”).
        *   **Status (Aktywna/Nieaktywna):** Kontroluje, czy ta konkretna polityka jest obecnie aktywna w Twoim sklepie.
        *   **Kreator warunków:** To jest rdzeń modułu. Użyjesz wizualnego interfejsu do zdefiniowania *kiedy* rabat ma zastosowanie. Przykłady:
            *   „Całkowita wartość koszyka jest większa niż 100$”
            *   „Klient należy do grupy ‘Hurtownicy’”
            *   „Produkt ‘X’ jest w koszyku w ilości >= 2”
            *   „Dowolny produkt z kategorii ‘Wyprzedaż letnia’ jest w koszyku”
            *   Możesz łączyć wiele warunków za pomocą logiki „AND” lub „OR”.
        *   **Kreator promocji:** To definiuje *jaki* rabat lub prezent otrzyma klient, jeśli warunki zostaną spełnione. Przykłady:
            *   „Zastosuj 10% rabatu do całego zamówienia”
            *   „Oddaj najtańszy przedmiot z kategorii ‘Akcesoria’ za darmo”
            *   „Dodaj produkt ‘Pudełko prezentowe’ do koszyka za darmo”
            *   „Zastosuj 50% rabatu do drugiej sztuki produktu ‘Y’”
        *   **Selektor zakresu:** Zdefiniuj, do których sklepów (dla konfiguracji multistore), grup klientów lub walut ma zastosowanie ta polityka.
        *   **Priorytet:** Jeśli wiele polityk może mieć zastosowanie do jednego koszyka, to określa, która z nich ma pierwszeństwo. Niższe liczby oznaczają wyższy priorytet.
        *   **Daty ważności:** Ustaw datę rozpoczęcia i zakończenia promocji.
        *   **Symulator koszyka:** Potężne narzędzie w edytorze polityk, które pozwala dodawać produkty do symulowanego koszyka i natychmiast zobaczyć, czy Twoja polityka ma zastosowanie i jaki rabat jest przyznawany. To jest kluczowe do testowania!
-   **Efekt zmian:**

    *   Dodanie nowej polityki sprawia, że nowa promocja jest dostępna (jeśli aktywna) w Twoim sklepie.
    *   Edycja polityki zmienia warunki lub promocje istniejącej oferty.
    *   Włączanie/wyłączanie polityk bezpośrednio kontroluje ich widoczność i zastosowanie w front office.
    *   Duplikowanie polityk pozwala na szybkie tworzenie podobnych promocji bez rozpoczynania od zera.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Zaplanuj promocję:** Zdecyduj o ofercie (np. „Kup 3, otrzymaj 1 gratis na wszystkie skarpetki”).
    2.  **Utwórz nową politykę:** Przejdź do „Polityki” i kliknij „Dodaj nową politykę”.
    3.  **Zdefiniuj warunki:** Użyj wizualnego kreatora, aby określić, które produkty, kategorie, ilości lub wartości koszyka wywołują rabat.
    4.  **Zdefiniuj promocje:** Określ typ rabatu (procentowy, stała kwota, darmowy prezent) i do czego ma zastosowanie.
    5.  **Dokładnie przetestuj za pomocą Symulatora koszyka:** Przed zapisaniem użyj symulatora, aby dodać różne produkty i ilości, aby upewnić się, że rabat jest stosowany dokładnie tak, jak zamierzono.
    6.  **Ustaw daty ważności i priorytet:** Upewnij się, że promocja działa tylko wtedy, gdy tego chcesz i prawidłowo współdziała z innymi promocjami.
    7.  **Aktywuj politykę:** Po przetestowaniu i gotowości ustaw jej status na „Aktywna”.
    8.  **Monitoruj za pomocą Dziennika audytu:** Sprawdź Dziennik audytu (patrz następna sekcja), aby potwierdzić, że polityki są prawidłowo stosowane w aktywnych koszykach.

#### 2.2.2 Warunkowe rabaty > Dziennik audytu (AdminConorderdisAuditLogController)

Ten ekran zapewnia szczegółową historię tego, jak Twoje polityki warunkowych rabatów zostały zastosowane (lub próbowano je zastosować) do koszyków klientów.

-   **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Warunkowe rabaty > Dziennik audytu
-   **Dostępne akcje i ustawienia:**
    *   **Lista dziennika:** Tabela wyświetlająca wpisy dla każdego razu, gdy polityka była oceniana. Każdy wpis zazwyczaj zawiera:
        *   **Data/Godzina:** Kiedy zdarzenie miało miejsce.
        *   **Klient:** Który klient (jeśli zalogowany) był zaangażowany.
        *   **ID koszyka:** ID koszyka zakupowego.
        *   **Nazwa polityki:** Która polityka była oceniana.
        *   **Wynik:** Czy warunki polityki zostały spełnione i czy rabat został zastosowany.
        *   **Szczegóły:** Bardziej szczegółowe informacje o spełnionych warunkach, zastosowanym rabacie lub dlaczego nie został zastosowany.
    *   **Filtrowanie i wyszukiwanie:** Możesz filtrować dziennik według daty, klienta, polityki lub wyniku, aby szybko znaleźć konkretne zdarzenia.
-   **Efekt zmian:** Jest to ekran tylko do odczytu. Nie wprowadzasz tutaj zmian, ale raczej obserwujesz zachowanie modułu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    *   **Rozwiązywanie problemów:** Jeśli klient zgłosi problem z niezastosowaniem rabatu lub jeśli podejrzewasz, że polityka nie działa zgodnie z oczekiwaniami, sprawdź dziennik audytu. Możesz dokładnie zobaczyć, co się stało, gdy jego koszyk był oceniany.
    *   **Monitorowanie:** Regularnie przeglądaj dziennik, aby upewnić się, że Twoje promocje są prawidłowo wyzwalane i aby zidentyfikować wszelkie nieoczekiwane zachowania.
    *   **Zrozumienie interakcji polityk:** Jeśli masz wiele polityk, dziennik może pomóc Ci zrozumieć, które polityki są brane pod uwagę i która ostatecznie ma zastosowanie na podstawie priorytetów.

#### 2.2.3 Warunkowe rabaty > Pulpit (AdminConorderdisDashboardController)

Ten ekran zapewnia przegląd i potencjalnie szybki dostęp do kluczowych funkcji modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Warunkowe rabaty > Pulpit
-   **Dostępne akcje i ustawienia:** Ten pulpit zazwyczaj zapewnia:
    *   **Statystyki podsumowujące:** Szybkie liczniki aktywnych polityk, wszystkich polityk lub ostatnich wpisów w dzienniku audytu.
    *   **Szybkie linki:** Skróty do „Dodaj nową politykę”, „Wyświetl polityki” lub „Wyświetl dziennik audytu”.
    *   **Dostęp do symulatora:** Widoczny link lub wbudowane narzędzie do symulatora koszyka, aby szybko testować polityki.
    *   **Status modułu:** Wskazanie, czy moduł jest włączony, czy wyłączony.
-   **Efekt zmian:** Jest to przede wszystkim ekran informacyjny i nawigacyjny. Zmiany są wprowadzane za pośrednictwem połączonych sekcji „Polityki” lub „Dziennik audytu”.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Używaj tego jako punktu wyjścia do zarządzania swoimi promocjami, uzyskiwania szybkiego przeglądu aktywnych kampanii i dostępu do symulatora w celu testowania.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz warunkowe rabaty na zamówienia | TAK | Główny przełącznik do aktywacji/dezaktywacji wszystkich funkcji modułu. |
| Polityki (Dodaj/Edytuj) | Nazwa polityki | Nazwa opisowa | Wewnętrzna etykieta dla Twojej promocji. |
| Polityki (Dodaj/Edytuj) | Status | Aktywna | Kontroluje, czy konkretna polityka jest aktywna w sklepie. |
| Polityki (Dodaj/Edytuj) | Kreator warunków | Różne | Definiuje kryteria kwalifikacji do rabatu (np. całkowita wartość koszyka, produkty w koszyku). |
| Polityki (Dodaj/Edytuj) | Kreator promocji | Różne | Definiuje zastosowany rabat lub darmowy prezent (np. % zniżki, darmowy produkt). |
| Polityki (Dodaj/Edytuj) | Selektor zakresu | Wszystkie sklepy/grupy/waluty | Ogranicza zastosowanie polityki do określonych kontekstów. |
| Polityki (Dodaj/Edytuj) | Priorytet | Niższa liczba = wyższy priorytet | Określa, która polityka ma zastosowanie, jeśli wiele jest kwalifikujących się. |
| Polityki (Dodaj/Edytuj) | Daty ważności | Brak daty zakończenia | Ustawia okres aktywności promocji. |
| Polityki (Dodaj/Edytuj) | Symulator koszyka | N/A | Narzędzie do testowania zastosowania polityki przed zapisaniem. |
| Polityki (Lista) | Akcja duplikowania polityki | N/A | Tworzy kopię istniejącej polityki, oszczędzając czas konfiguracji. |
| Dziennik audytu | Wpisy dziennika | N/A | Rejestruje każdą ocenę polityki, pokazując sukces/porażkę i szczegóły. |
| Pulpit | Szybkie linki / Podsumowanie | N/A | Zapewnia przegląd i skróty do kluczowych funkcji modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój rabat nie jest stosowany, mimo że ustawiłem politykę.**
O1:

-   **Czy moduł jest włączony?** Sprawdź **Moduły > Menedżer modułów > Warunkowe rabaty na zamówienia** i upewnij się, że główny przełącznik jest WŁĄCZONY.
-   **Czy konkretna polityka jest aktywna?** Przejdź do **Warunkowe rabaty > Polityki** i sprawdź kolumnę „Status” dla swojej polityki.
-   **Czy warunki są spełnione?** Użyj **Symulatora koszyka** w edytorze polityk. Dodaj produkty do symulowanego koszyka dokładnie tak, jak zrobiłby to klient. Czy symulator pokazuje, że rabat jest stosowany? Jeśli nie, dokładnie przejrzyj swoje warunki.
-   **Sprawdź daty ważności:** Czy polityka mieści się w swoim aktywnym zakresie dat?
-   **Sprawdź priorytet:** Jeśli wiele polityk może mieć zastosowanie, upewnij się, że ta, której oczekujesz, ma prawidłowy priorytet (niższa liczba = wyższy priorytet).
-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami dane z pamięci podręcznej mogą uniemożliwić natychmiastowe wejście w życie nowych reguł.

**P2: Rabat jest stosowany, ale nie jest to prawidłowa kwota ani produkt.**
O2:

-   **Przejrzyj swój Kreator promocji:** Dokładnie sprawdź typ rabatu (procentowy, stała kwota), wartość i do czego ma zastosowanie (całe zamówienie, konkretne produkty, najtańszy przedmiot itp.).
-   **Ponownie sprawdź warunki:** Czasami subtelny warunek może prowadzić do nieoczekiwanego wyniku. Na przykład, jeśli masz „dowolny produkt z kategorii X”, ale klient ma produkty z innych kategorii, które również spełniają regułę „najtańszego przedmiotu”.
-   **Intensywnie używaj Symulatora koszyka:** To Twój najlepszy przyjaciel do weryfikacji złożonych reguł. Testuj przypadki brzegowe.
-   **Dziennik audytu:** Sprawdź **Warunkowe rabaty > Dziennik audytu**, aby zobaczyć dokładne szczegóły, jak moduł ocenił koszyk i jaki rabat próbował zastosować. Może to ujawnić rozbieżności.

**P3: Mój niestandardowy szablon nie wyświetla jasno komunikatów o rabatach ani darmowych prezentów.**
O3:

-   Moduł integruje się z natywnymi regułami koszyka PrestaShop, więc sam rabat powinien pojawić się w podsumowaniu koszyka. Jeśli jednak chcesz, aby niestandardowe komunikaty, takie jak „Zakwalifikowałeś się do darmowego prezentu!” lub „Kup 2, otrzymaj 1 gratis!” pojawiały się dynamicznie na stronach produktów lub w koszyku, zazwyczaj wymaga to niestandardowych modyfikacji szablonu.
-   **Skonsultuj się z programistą:** Twój webmaster lub programista PrestaShop może pomóc Ci zintegrować dynamiczne komunikaty z plikami `product.tpl`, `cart.tpl` lub `checkout.tpl` Twojego szablonu, potencjalnie używając hooków modułu (patrz Przewodnik dla programistów).

**P4: Czy mogę używać tego modułu z innymi modułami rabatowymi lub natywnymi regułami koszyka?**
O4:

-   Tak, ten moduł działa poprzez tworzenie i zarządzanie natywnymi regułami koszyka PrestaShop w tle. Oznacza to, że jest on ogólnie kompatybilny z innymi modułami, które również opierają się na podstawowym systemie rabatów PrestaShop.
-   **Priorytet jest kluczowy:** Pamiętaj o ustawieniach priorytetów dla swoich polityk Warunkowych rabatów na zamówienia i wszelkich innych natywnych reguł koszyka, które utworzyłeś ręcznie. PrestaShop stosuje rabaty na podstawie ich priorytetu. Dokładnie przetestuj za pomocą Symulatora koszyka i przejrzyj Dziennik audytu, jeśli masz wiele nakładających się promocji.

**P5: Jak zarządzać tłumaczeniami wielojęzycznymi dla nazw polityk lub opisów?**
O5:

-   Nazwy polityk i wszelkie niestandardowe teksty, które wprowadzasz dla warunków lub promocji, są zazwyczaj zarządzane bezpośrednio na ekranie edycji polityki. Standardowy interfejs tłumaczeń PrestaShop (w **Lokalizacja > Tłumaczenia**) może nie mieć bezpośredniego zastosowania do dynamicznej zawartości generowanej przez kreator polityk modułu.
-   Jeśli moduł udostępnia konkretne pola dla różnych języków w edytorze polityk, użyj ich. W przeciwnym razie upewnij się, że nazwy Twoich polityk są jasne i zwięzłe, lub rozważ dodanie statycznych bloków informacyjnych w swoim szablonie dla różnych języków, aby wyjaśnić promocje.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd architektury technicznej modułu Warunkowe rabaty na zamówienia, szczegółowo opisując jego strukturę plików, klasy, kontrolery i punkty integracji dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł Warunkowe rabaty na zamówienia jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop. W dużym stopniu wykorzystuje natywny system `CartRule` PrestaShop, skutecznie działając jako zaawansowany kreator i menedżer reguł dla tych podstawowych obiektów. Wprowadza kilka niestandardowych klas `ObjectModel` do zarządzania politykami, warunkami, promocjami i dziennikiem audytu. Moduł wykorzystuje solidny silnik do oceny złożonych warunków względem stanu koszyka klienta, a następnie materializuje odpowiednie obiekty `CartRule`. Zawiera również zaawansowany kreator warunków i symulator w Panelu administracyjnym dla łatwości użytkowania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `conorderdis/controllers/front/index.php`
    *   **Nazwa klasy:** `ConorderdisIndexModuleFrontController` (lub podobna, w zależności od wersji PrestaShop i struktury modułu, często `ModuleFrontController`).
    *   **Odpowiedzialność:** Ten plik zazwyczaj służy jako placeholder lub domyślny punkt wejścia dla interakcji modułu z front-office. W kontekście tego modułu, bezpośrednie kontrolery front-office są mniej krytyczne, ponieważ większość logiki jest obsługiwana za pomocą hooków, które współdziałają z koszykiem i procesem zamówienia. Może obsługiwać żądania AJAX związane z aktualizacjami koszyka lub specyficznymi interakcjami front-end, jeśli są zaimplementowane, ale podstawowa logika rabatowa działa za pośrednictwem hooków.

#### Kontrolery administracyjne Back-Office

-   `conorderdis/controllers/admin/AdminconorderdisAuditLog.php`
    *   **Nazwa zakładki:** Warunkowe rabaty > Dziennik audytu
    *   **Zarządzana encja:** `ConorderdisAuditLog` (mapuje na tabelę `ps_conorderdis_log`).
    *   **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem wpisów dziennika audytu. Rozszerza `AdminController` i używa `HelperList` do renderowania tabeli dziennika, umożliwiając administratorom przeglądanie, jak polityki były stosowane lub oceniane względem koszyków klientów.
-   `conorderdis/controllers/admin/AdminconorderdisPolicies.php`
    *   **Nazwa zakładki:** Warunkowe rabaty > Polityki
    *   **Zarządzana encja:** `ConorderdisPolicy` (mapuje na tabelę `ps_conorderdis_policy`).
    *   **Odpowiedzialność:** Jest to główny kontroler do zarządzania politykami rabatowymi. Rozszerza `AdminController` i zapewnia funkcjonalność CRUD (Create, Read, Update, Delete) dla polityk. Integruje wizualne kreatory warunków i promocji, selektor produktów i symulator koszyka. Używa `HelperList` do przeglądu polityk i `HelperForm` do formularzy dodawania/edycji polityk.
-   `conorderdis/controllers/admin/index.php`
    *   **Odpowiedzialność:** Jest to standardowa praktyka PrestaShop, aby zapobiec listowaniu katalogów. Zazwyczaj zawiera prostą instrukcję `die('No direct script access allowed');`. Nie zarządza żadną konkretną encją ani nie zapewnia funkcjonalności poza bezpieczeństwem.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `conorderdis/classes/ConorderdisAdmin.php`
    *   **Odpowiedzialność:** Prawdopodobnie zawiera metody pomocnicze lub narzędzia specyficzne dla administracji Back Office, takie jak renderowanie konkretnych elementów formularza, obsługa żądań AJAX z formularzy administracyjnych lub zarządzanie konfiguracjami specyficznymi dla modułu.
-   `conorderdis/classes/ConorderdisAuditLog.php`
    *   **Rozszerza:** `ObjectModel`
    *   **Tabela bazy danych:** `ps_conorderdis_log`
    *   **Pola `$definition`:** Przechowuje szczegóły dotyczące ocen polityk, w tym `id_cart`, `id_customer`, `id_policy`, `result`, `details`, `date_add`.
    *   **Odpowiedzialność:** Reprezentuje wpis w dzienniku audytu. Zapewnia metody do logowania zdarzeń zastosowania polityki, sukcesów i niepowodzeń.
-   `conorderdis/classes/ConorderdisCartRuleManager.php`
    *   **Odpowiedzialność:** Zarządza tworzeniem, aktualizacją i usuwaniem natywnych obiektów `CartRule` PrestaShop na podstawie definicji `ConorderdisPolicy` modułu. Ta klasa jest kluczowa do tłumaczenia złożonych reguł modułu na standardowe rabaty PrestaShop.
-   `conorderdis/classes/ConorderdisCartState.php`
    *   **Odpowiedzialność:** Hermetyzuje bieżący stan koszyka klienta, zapewniając warstwę abstrakcji dla silnika rabatowego do oceny warunków. Może zawierać metody do pobierania całkowitej wartości koszyka, ilości produktów, grupy klientów itp.
-   `conorderdis/classes/ConorderdisCompatibility.php`
    *   **Odpowiedzialność:** Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop (np. 1.7.x, 8.x, 9.x) lub specyficznych wersji PHP. Zapewnia, że moduł działa poprawnie w całym obsługiwanym zakresie środowiska, dostarczając polyfills lub alternatywne implementacje dla przestarzałych funkcji/metod.
-   `conorderdis/classes/ConorderdisConditionTree.php`
    *   **Odpowiedzialność:** Zarządza złożoną strukturą logiczną warunków (np. grupy „AND”, „OR”, zagnieżdżone warunki). Prawdopodobnie analizuje dane warunków z bazy danych i dostarcza metody do oceny, czy dany `ConorderdisCartState` spełnia zdefiniowane warunki.
-   `conorderdis/classes/ConorderdisContext.php`
    *   **Odpowiedzialność:** Wrapper wokół globalnego obiektu `Context` PrestaShop, potencjalnie dodający dane kontekstowe specyficzne dla modułu lub upraszczający dostęp do wspólnych właściwości kontekstu.
-   `conorderdis/classes/ConorderdisDashboard.php`
    *   **Odpowiedzialność:** Dostarcza dane i logikę dla widoku pulpitu Back Office, podsumowując kluczowe statystyki i zapewniając szybkie linki.
-   `conorderdis/classes/ConorderdisEngine.php`
    *   **Odpowiedzialność:** Podstawowy silnik logiczny modułu. Ta klasa orkiestruje ocenę polityk. Przyjmuje `ConorderdisCartState`, iteruje przez aktywne obiekty `ConorderdisPolicy`, ocenia ich `ConorderdisConditionTree`, a jeśli warunki są spełnione, instruuje `ConorderdisPromoMaterializer` do zastosowania rabatu.
-   `conorderdis/classes/ConorderdisFreeGift.php`
    *   **Odpowiedzialność:** Specjalnie obsługuje logikę dodawania darmowych produktów do koszyka, gdy promocja tego wymaga. Współdziała z obiektem `Cart`, aby upewnić się, że produkt jest dodany prawidłowo i oznaczony jako darmowy.
-   `conorderdis/classes/ConorderdisListRenderer.php`
    *   **Odpowiedzialność:** Klasa pomocnicza do renderowania list w Back Office, potencjalnie rozszerzająca `HelperList` lub dostarczająca niestandardową logikę renderowania dla konkretnych kolumn lub akcji (np. akcja duplikowania).
-   `conorderdis/classes/ConorderdisLog.php`
    *   **Rozszerza:** `ObjectModel` (prawdopodobnie alias lub starsza wersja `ConorderdisAuditLog`).
    *   **Tabela bazy danych:** `ps_conorderdis_log`
    *   **Odpowiedzialność:** Podobnie jak `ConorderdisAuditLog`, obsługuje logowanie zdarzeń modułu.
-   `conorderdis/classes/ConorderdisPolicy.php`
    *   **Rozszerza:** `ObjectModel`
    *   **Tabela bazy danych:** `ps_conorderdis_policy`
    *   **Pola `$definition`:** Przechowuje wszystkie dane związane z polityką, w tym `name`, `active`, `conditions_data` (serializowana JSON/tablica), `promotions_data` (serializowana JSON/tablica), `priority`, `date_from`, `date_to`, `id_shop`, `id_customer_group`, `id_currency`.
    *   **Odpowiedzialność:** Reprezentuje pojedynczą politykę warunkowego rabatu. Zapewnia metody do zapisywania, ładowania i zarządzania danymi polityki, w tym jej warunkami i promocjami.
-   `conorderdis/classes/ConorderdisPolicyDuplicator.php`
    *   **Odpowiedzialność:** Obsługuje logikę duplikowania obiektów `ConorderdisPolicy`, zapewniając prawidłowe skopiowanie wszystkich powiązanych danych (warunków, promocji).
-   `conorderdis/classes/ConorderdisProductPicker.php`
    *   **Odpowiedzialność:** Zapewnia funkcjonalność wyboru produktów, kategorii lub producentów w kreatorze polityk Back Office, prawdopodobnie za pomocą narzędzia wyszukiwania opartego na AJAX.
-   `conorderdis/classes/ConorderdisPromoMaterializer.php`
    *   **Odpowiedzialność:** Przyjmuje wynik `ConorderdisEngine` (tj. „ta promocja powinna zostać zastosowana”) i tłumaczy go na rzeczywiste zmiany w koszyku PrestaShop, głównie poprzez tworzenie lub modyfikowanie obiektów `CartRule` za pośrednictwem `ConorderdisCartRuleManager`.
-   `conorderdis/classes/ConorderdisPromotionCalculator.php`
    *   **Odpowiedzialność:** Oblicza dokładną kwotę rabatu lub identyfikuje darmowy produkt na podstawie zdefiniowanych reguł promocji i bieżącego stanu koszyka.
-   `conorderdis/classes/ConorderdisPromotionType.php`
    *   **Odpowiedzialność:** Definiuje i zarządza różnymi typami promocji (np. rabat procentowy, stała kwota, darmowy prezent, najtańszy przedmiot gratis). Prawdopodobnie zawiera logikę specyficzną dla każdego typu promocji.
-   `conorderdis/classes/ConorderdisRule.php`
    *   **Odpowiedzialność:** Ogólna klasa reprezentująca pojedynczą regułę lub warunek w `ConorderdisConditionTree`.
-   `conorderdis/classes/ConorderdisSchema.php`
    *   **Odpowiedzialność:** Zarządza schematem bazy danych modułu, w tym instalacją i deinstalacją niestandardowych tabel (`ps_conorderdis_policy`, `ps_conorderdis_log`).
-   `conorderdis/classes/ConorderdisUnitPool.php`
    *   **Odpowiedzialność:** Prawdopodobnie używany w złożonych scenariuszach „Kup N, otrzymaj M” lub „najtańszy przedmiot gratis” do zarządzania i śledzenia poszczególnych jednostek produktów w koszyku w celu obliczenia rabatu.
-   `conorderdis/classes/index.php`
    *   **Odpowiedzialność:** Standardowa praktyka PrestaShop, aby zapobiec listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `conorderdis/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Back-office (używany w formularzach administracyjnych).
    *   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych, prawdopodobnie używaną w kreatorze polityk do wybierania produktów, kategorii lub producentów. Wiąże się z polami wejściowymi, wykonuje wywołania AJAX do kontrolera wyszukiwania i wyświetla sugestie.
-   `conorderdis/views/js/adminConditionBuilder.js`
    *   **Zakres:** Back-office (kontroler AdminConorderdisPolicies).
    *   **Szczegóły:** Zasila wizualny interfejs kreatora warunków. Obsługuje dodawanie/usuwanie warunków, grupowanie warunków (AND/OR), wybieranie typów warunków i dynamiczne aktualizowanie interfejsu użytkownika na podstawie danych wejściowych użytkownika. Zarządza strukturą danych reprezentującą drzewo warunków.
-   `conorderdis/views/js/adminConorderdisDashboard.js`
    *   **Zakres:** Back-office (kontroler AdminConorderdisDashboard).
    *   **Szczegóły:** Zapewnia interaktywne elementy lub dynamiczną zawartość dla pulpitu modułu, takie jak pobieranie statystyk podsumowujących za pośrednictwem AJAX lub obsługa kliknięć szybkich linków.
-   `conorderdis/views/js/adminConorderdisSearchTool.js`
    *   **Zakres:** Back-office (kontroler AdminConorderdisPolicies).
    *   **Szczegóły:** Bardziej ogólne narzędzie wyszukiwania, potencjalnie używane do wyboru produktów/kategorii w kreatorze polityk, podobne do `autocomplete.js`, ale prawdopodobnie z bardziej zaawansowanymi opcjami filtrowania lub wyświetlania.
-   `conorderdis/views/js/adminConorderdisSimulator.js`
    *   **Zakres:** Back-office (kontroler AdminConorderdisPolicies).
    *   **Szczegóły:** Implementuje interaktywny symulator koszyka. Wiąże się z polami wejściowymi do dodawania symulowanych produktów, wykonuje wywołania AJAX do punktu końcowego symulacji (prawdopodobnie w `AdminConorderdisPolicies`) i aktualizuje interfejs użytkownika z symulowanym stanem koszyka i zastosowanymi rabatami.
-   `conorderdis/views/js/adminPolicyRules.js`
    *   **Zakres:** Back-office (kontroler AdminConorderdisPolicies).
    *   **Szczegóły:** Zarządza ogólną interakcją i logiką dla formularza tworzenia/edycji polityki, koordynując między kreatorem warunków, kreatorem promocji i symulatorem.
-   `conorderdis/views/js/adminPromotionBuilder.js`
    *   **Zakres:** Back-office (kontroler AdminConorderdisPolicies).
    *   **Szczegóły:** Zasila wizualny interfejs kreatora promocji. Obsługuje dodawanie/usuwanie promocji, wybieranie typów promocji (np. procentowe, darmowy prezent) i dynamiczne aktualizowanie interfejsu użytkownika na podstawie wybranego typu promocji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `conorderdis/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Back-office (formularze administracyjne).
    *   **Szczegóły:** Stylizuje rozwijane listy autouzupełniania i wyniki wyszukiwania dostarczane przez skrypt `autocomplete.js`.
-   `conorderdis/views/css/admin_conorderdis.css`
    *   **Zakres:** Back-office (formularze i strony administracyjne).
    *   **Szczegóły:** Zawiera ogólne style dla interfejsów Back Office modułu, w tym listy polityk, edytora polityk (kreatory warunków i promocji), pulpitu i dziennika audytu. Definiuje układy, kolory i specyficzne komponenty interfejsu użytkownika dla spójnego wyglądu w panelu administracyjnym PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `conorderdis/views/templates/hook/admin_order.tpl`
    *   **Hook:** `displayAdminOrder`
    *   **Wynik:** Ten szablon jest renderowany w Back Office podczas przeglądania zamówienia. Prawdopodobnie wyświetla informacje związane z wszelkimi warunkowymi rabatami zastosowanymi do tego konkretnego zamówienia, potencjalnie łącząc się z dziennikiem audytu lub pokazując, które polityki były aktywne.

#### Szablony administracyjne (`views/templates/admin/`)

-   `conorderdis/lib/searchTool/views/scripts.tpl`
    *   **Wynik:** Zawiera inicjalizację lub konfigurację JavaScript dla narzędzia wyszukiwania, często dołączane do formularzy administracyjnych, gdzie narzędzie wyszukiwania jest używane.
-   `conorderdis/views/templates/admin/auditPreview.tpl`
    *   **Wynik:** Renderuje podgląd lub szczegółowy widok wpisu dziennika audytu, prawdopodobnie w oknie modalnym lub w określonej sekcji strony `AdminconorderdisAuditLog`.
-   `conorderdis/views/templates/admin/dashboard.tpl`
    *   **Wynik:** Główny szablon dla kontrolera `AdminConorderdisDashboard`, wyświetlający statystyki podsumowujące, szybkie linki i potencjalnie wbudowany symulator.
-   `conorderdis/views/templates/admin/helpers/list/list_action_duplicate.tpl`
    *   **Wynik:** Niestandardowy szablon do renderowania ikony i linku akcji „Duplikuj” w tabeli `HelperList`, specjalnie dla polityk.
-   `conorderdis/views/templates/admin/policiesPreview.tpl`
    *   **Wynik:** Renderuje podgląd lub szczegółowy widok polityki, prawdopodobnie w oknie modalnym lub w określonej sekcji strony `AdminconorderdisPolicies`.
-   `conorderdis/views/templates/admin/policyConditionBuilder.tpl`
    *   **Wynik:** Szablon Smarty dla wizualnego interfejsu kreatora warunków w edytorze polityk. Definiuje strukturę do dodawania, grupowania i konfigurowania warunków.
-   `conorderdis/views/templates/admin/policyRuleCard.tpl`
    *   **Wynik:** Szablon wielokrotnego użytku do wyświetlania pojedynczej reguły lub warunku w kreatorze warunków, często używany do dynamicznego renderowania za pomocą JavaScript.
-   `conorderdis/views/templates/admin/policyRulesTable.tpl`
    *   **Wynik:** Renderuje tabelę lub listę reguł/warunków w edytorze polityk.
-   `conorderdis/views/templates/admin/scopeSelector.tpl`
    *   **Wynik:** Renderuje interfejs do wyboru sklepów, grup klientów i walut dla polityki.

#### Szablony Front-Office (`views/templates/front/`)

-   `conorderdis/controllers/front/index.php` (Brak konkretnych plików `.tpl` wymienionych dla front-office, co oznacza minimalne bezpośrednie renderowanie front-end, opierające się na hookach do wstrzykiwania treści lub modyfikowania istniejących elementów.)

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_conorderdis_policy`: Przechowuje definicję każdej polityki warunkowego rabatu.
    *   `id_conorderdis_policy` (Klucz podstawowy)
    *   `name` (Nazwa polityki)
    *   `active` (Boolean, 1 dla aktywnej, 0 dla nieaktywnej)
    *   `conditions_data` (TEXT, tablica warunków zakodowana w JSON)
    *   `promotions_data` (TEXT, tablica promocji zakodowana w JSON)
    *   `priority` (INT, niższa liczba = wyższy priorytet)
    *   `date_from` (DATETIME)
    *   `date_to` (DATETIME)
    *   `id_shop` (INT, dla zakresu multistore)
    *   `id_customer_group` (INT, dla zakresu grupy klientów)
    *   `id_currency` (INT, dla zakresu waluty)
    *   `date_add` (DATETIME)
    *   `date_upd` (DATETIME)
-   `ps_conorderdis_log`: Przechowuje wpisy dziennika audytu dla ocen polityk.
    *   `id_conorderdis_log` (Klucz podstawowy)
    *   `id_cart` (INT)
    *   `id_customer` (INT)
    *   `id_policy` (INT, klucz obcy do `ps_conorderdis_policy`)
    *   `result` (VARCHAR, np. ‘applied’, ‘not\_met’, ‘error’)
    *   `details` (TEXT, szczegóły oceny zakodowane w JSON)
    *   `date_add` (DATETIME)
-   `ps_configuration`: Moduł przechowuje tutaj swoje główne ustawienie `CONORDERDIS_ENABLED`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do dołączania plików CSS/JS modułu dla front-office, jeśli takie istnieją, lub do wstrzykiwania meta tagów. |
| `actionFrontControllerInitAfter` | Po zainicjalizowaniu kontrolera front-office. | Wczesny punkt do modyfikacji kontekstu, rejestrowania usług lub przygotowania do oceny reguł koszyka. |
| `actionCartSave` | Po zapisaniu koszyka (np. dodaniu/usunięciu produktu). | Główny hook do ponownej oceny polityk warunkowych rabatów na podstawie zaktualizowanej zawartości koszyka. |
| `actionValidateCartRule` | Przed walidacją/zastosowaniem reguły koszyka. | Pozwala modułowi na interwencję lub modyfikację natywnego zachowania reguł koszyka, choć mniej prawdopodobne dla tego modułu, który tworzy własne reguły. |
| `actionValidateOrderBefore` | Przed walidacją zamówienia. | Ostateczne sprawdzenie warunkowych rabatów przed utworzeniem zamówienia, zapewniające prawidłowe zastosowanie wszystkich reguł. |
| `actionValidateOrder` | Po pomyślnej walidacji zamówienia. | Służy do finalizacji wszelkich działań specyficznych dla modułu po zamówieniu, takich jak logowanie ostatecznego zastosowania rabatu lub czyszczenie danych tymczasowych. |
| `actionObjectProductInCartDeleteBefore` | Przed usunięciem produktu z koszyka. | Pozwala modułowi reagować na usunięcie produktu, potencjalnie dostosowując rabaty lub darmowe prezenty. |
| `actionObjectProductInCartDeleteAfter` | Po usunięciu produktu z koszyka. | Podobnie jak `DeleteBefore`, ale dla logiki po usunięciu, potencjalnie wyzwalając ponowną ocenę reguł koszyka. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Służy do dołączania plików CSS i JavaScript modułu dla Back Office dla jego stron konfiguracyjnych i niestandardowych kontrolerów. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w Back Office. | Służy do wyświetlania informacji specyficznych dla modułu, związanych z warunkowymi rabatami zastosowanymi do przeglądanego zamówienia (np. za pośrednictwem `admin_order.tpl`). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Znajdziesz tam zakupione moduły i dostęp do naszych kanałów wsparcia.
"""
