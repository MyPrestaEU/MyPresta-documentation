---
title: "Zasady warunkowej metody wysyłki - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zasady warunkowej metody wysyłki” od MyPresta.eu."
sidebar:
  label: "Zasady warunkowej metody wysyłki"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Conditional Shipping Method Rules na MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-shipping-method-rules.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/conditional-shipping-method-rules/)
>
> ---


# Zasady warunkowej metody wysyłki

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Możesz uzyskać dostęp do tego ekranu, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Zasady warunkowej metody wysyłki” i klikając „Konfiguruj”.

Ta strona zawiera ogólne ustawienia dotyczące zachowania modułu.

-   **Włącz moduł:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Wszystkie zdefiniowane zasady wysyłki będą aktywne i będą wpływać na metody wysyłki wyświetlane podczas realizacji zamówienia.
        -   *Gdy wyłączone:* Moduł będzie nieaktywny, a domyślny wybór metody wysyłki PrestaShop będzie obowiązywał, ignorując wszystkie Twoje niestandardowe zasady.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład sprzedawcy:** Możesz tymczasowo wyłączyć go podczas konserwacji lub jeśli musisz szybko wrócić do domyślnego zachowania wysyłki. Do normalnego działania pozostaw go włączonym.

-   **Strategia łączenia dla wielu zasad:**
    -   **Co robi to ustawienie:** Określa, w jaki sposób moduł łączy wyniki wielu aktywnych zasad, gdy dotyczą one tej samej metody wysyłki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Opcja A (Priorytet „POKAŻ”):* Jeśli *jakakolwiek* aktywna zasada mówi „POKAŻ” przewoźnika, zostanie on pokazany, nawet jeśli inne zasady mówią „UKRYJ” go. Jest to bardziej liberalna strategia.
        -   *Opcja B (Priorytet „UKRYJ”):* Jeśli *jakakolwiek* aktywna zasada mówi „UKRYJ” przewoźnika, zostanie on ukryty, nawet jeśli inne zasady mówią „POKAŻ” go. Jest to bardziej restrykcyjna strategia.
        -   *Opcja C (Niestandardowa strategia łączenia 1):* [Szczegółowe wyjaśnienie konkretnej logiki, np. „Pokaż tylko, jeśli WSZYSTKIE obowiązujące zasady mówią POKAŻ”]
        -   *Opcja D (Niestandardowa strategia łączenia 2):* [Szczegółowe wyjaśnienie konkretnej logiki]
        -   *Opcja E (Niestandardowa strategia łączenia 3):* [Szczegółowe wyjaśnienie konkretnej logiki]
    -   **Zalecana wartość:** Priorytet „UKRYJ” (dla bezpieczeństwa, aby upewnić się, że nie są wyświetlane niechciane przewoźnicy). Jednak zależy to w dużej mierze od Twojej konkretnej konfiguracji zasad.
    -   **Scenariusz / przykład sprzedawcy:** Jeśli masz zasadę „POKAŻ” darmową wysyłkę dla zamówień powyżej 100 USD, ale inną zasadę „UKRYJ” darmową wysyłkę dla konkretnego produktu, strategia łączenia określa, która zasada wygrywa. „Priorytet UKRYJ” ukryłby darmową wysyłkę dla tego produktu, nawet jeśli zamówienie jest powyżej 100 USD.

-   **Wyświetlaj komunikaty o niedostępności metody wysyłki:**
    -   **Co robi to ustawienie:** Kontroluje, czy klienci widzą wyjaśnienie, gdy metoda wysyłki jest ukryta przez zasadę.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli przewoźnik jest ukryty, klientowi zostanie wyświetlony komunikat (który definiujesz dla każdej zasady), wyjaśniający, dlaczego jest niedostępny.
        -   *Gdy wyłączone:* Ukryci przewoźnicy po prostu znikną z listy bez żadnego wyjaśnienia.
    -   **Zalecana wartość:** TAK (Poprawia doświadczenie klienta i zmniejsza zamieszanie).
    -   **Scenariusz / przykład sprzedawcy:** Jeśli „Wysyłka ekspresowa” jest ukryta, ponieważ koszyk klienta zawiera „Kruchy przedmiot”, którego nie można wysłać ekspresowo, włączenie tej opcji wyświetli komunikat, taki jak „Wysyłka ekspresowa nie jest dostępna dla kruchych przedmiotów”.

-   **Retencja dziennika audytu (dni):**
    -   **Co robi to ustawienie:** Definiuje, jak długo moduł przechowuje zapisy ocen zasad i ich wyników w dzienniku audytu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawienie liczby (np. 30):* Moduł automatycznie usunie wpisy dziennika starsze niż ta liczba dni.
        -   *Ustawienie na 0 lub puste:* Moduł będzie przechowywał wszystkie wpisy dziennika bezterminowo (może prowadzić do dużej bazy danych z czasem).
    -   **Zalecana wartość:** 30-90 dni (wystarczające do rozwiązywania problemów bez nadmiernego wzrostu bazy danych).
    -   **Scenariusz / przykład sprzedawcy:** Jeśli klient skarży się na brak widoczności konkretnej metody wysyłki, możesz sprawdzić dziennik audytu pod kątem ostatnich ocen. Przechowywanie dzienników przez 30 dni pozwala na badanie ostatnich problemów bez przechowywania danych z lat.

-   **Włącz symulator realizacji zamówienia:**
    -   **Co robi to ustawienie:** Aktywuje narzędzie w panelu administracyjnym, które pozwala testować zasady wysyłki, symulując różne scenariusze klienta i koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zakładka „Symulator realizacji zamówienia” pojawi się w konfiguracji modułu, zapewniając potężne środowisko testowe.
        -   *Gdy wyłączone:* Symulator nie będzie dostępny.
    -   **Zalecana wartość:** TAK (Niezbędne do testowania złożonych zasad przed wdrożeniem).
    -   **Scenariusz / przykład sprzedawcy:** Przed uruchomieniem nowej promocji wysyłkowej możesz użyć symulatora, aby upewnić się, że Twoje zasady poprawnie pokazują/ukrywają promocyjną wysyłkę dla różnych wartości koszyka, grup klientów i adresów.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zasady wysyłki (Panel administracyjny > Moduły > Zasady warunkowej metody wysyłki > Zasady wysyłki)
Jest to główny ekran, na którym definiujesz i zarządzasz wszystkimi swoimi zasadami wysyłki.

-   **Nazwa ekranu i lokalizacja w menu:** **Zasady warunkowej metody wysyłki > Zasady wysyłki** (znajduje się w sekcji „Moduły” w menu panelu administracyjnego PrestaShop).
-   **Dostępne działania i ustawienia:**
    -   **Lista zasad:** Tabela wyświetlająca wszystkie utworzone zasady wysyłki. Każda zasada ma nazwę, status (włączona/wyłączona) i działania.
    -   **Dodaj nową zasadę:** Przycisk do tworzenia nowej zasady wysyłki.
    -   **Edytuj zasadę:** Kliknij istniejącą zasadę, aby zmodyfikować jej reguły, warunki i ustawienia.
    -   **Duplikuj zasadę:** Szybko utwórz kopię istniejącej zasady, przydatne do wprowadzania drobnych zmian.
    -   **Włącz/Wyłącz zasadę:** Przełącz status aktywności zasady bez jej usuwania.
    -   **Usuń zasadę:** Usuń zasadę na stałe.
    -   **Formularz konfiguracji zasady (podczas dodawania/edycji):**
        -   **Nazwa zasady:** Opisowa nazwa dla Twojego zestawu reguł (np. „Darmowa wysyłka powyżej 100 USD”, „Ograniczenia wysyłki ekspresowej”).
        -   **Status:** Włącz lub wyłącz tę konkretną zasadę.
        -   **Priorytet:** Jeśli zastosowanie ma wiele zasad, określa to kolejność ich oceny. Niższe liczby oznaczają wyższy priorytet.
        -   **Przewoźnicy docelowi:** Wybierz, których konkretnych przewoźników wysyłkowych dotyczy ta zasada.
        -   **Akcja (POKAŻ/UKRYJ):** Wybierz, czy ta zasada ma *pokazać* wybranych przewoźników, jeśli warunki są spełnione, czy *ukryć* ich.
        -   **Komunikat o niedostępności:** Jeśli wybrałeś „UKRYJ” i „Wyświetlaj komunikaty o niedostępności metody wysyłki” jest włączone w głównej konfiguracji, jest to komunikat, który zobaczą klienci (wielojęzyczny).
        -   **Kreator warunków:** Tutaj definiujesz część „JEŚLI” swojej zasady. Możesz dodać wiele grup warunków (logika ORAZ/LUB) na podstawie:
            -   Całkowitej wartości koszyka, wagi, ilości
            -   Konkretnych produktów lub kategorii w koszyku
            -   Grupy klientów, kraju, stanu, kodu pocztowego
            -   Daty i godziny
            -   I wielu innych kryteriów.
-   **Efekt zmian:**
    -   Dodawanie, edytowanie lub usuwanie zasad bezpośrednio wpływa na to, które metody wysyłki są prezentowane klientom podczas realizacji zamówienia, na podstawie zdefiniowanych warunków.
    -   Zmiana statusu zasady (włącz/wyłącz) natychmiast aktywuje lub dezaktywuje jej wpływ na front office.
    -   Dostosowanie priorytetu może rozwiązać konflikty, jeśli wiele zasad dotyczy tego samego przewoźnika.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zaplanuj swoją zasadę:** Przed utworzeniem jasno określ, co chcesz osiągnąć (np. „Jeśli całkowita wartość koszyka > 50 USD ORAZ klient jest w USA, WÓWCZAS POKAŻ 'Standardową wysyłkę'”).
    2.  **Utwórz nową zasadę:** Nadaj jej jasną nazwę.
    3.  **Wybierz przewoźników docelowych:** Wybierz przewoźników, których dotyczy ta zasada.
    4.  **Ustaw akcję:** Zdecyduj, czy zasada ma POKAZAĆ, czy UKRYĆ tych przewoźników.
    5.  **Zbuduj warunki:** Użyj intuicyjnego kreatora warunków, aby ustawić swoje instrukcje „JEŚLI”. Użyj „Dodaj grupę warunków” dla logiki LUB i „Dodaj warunek” w grupie dla logiki ORAZ.
    6.  **Testuj za pomocą symulatora:** Co najważniejsze, użyj „Symulatora realizacji zamówienia” (patrz następna sekcja), aby zweryfikować, czy Twoje zasady działają zgodnie z oczekiwaniami w różnych scenariuszach.
    7.  **Włącz:** Po przetestowaniu włącz zasadę.

#### 2.2.2 Dziennik audytu (Panel administracyjny > Moduły > Zasady warunkowej metody wysyłki > Dziennik audytu)
Ten ekran zawiera historyczny zapis sposobu oceny Twoich zasad wysyłki.

-   **Nazwa ekranu i lokalizacja w menu:** **Zasady warunkowej metody wysyłki > Dziennik audytu** (znajduje się w sekcji „Moduły” w menu panelu administracyjnego PrestaShop).
-   **Dostępne działania i ustawienia:**
    -   **Tabela dziennika:** Szczegółowa lista każdego razu, gdy moduł oceniał zasady wysyłki dla koszyka klienta.
    -   **Kolumny:** Zawiera informacje takie jak:
        -   Data i godzina oceny
        -   ID klienta (jeśli zalogowany)
        -   ID koszyka
        -   Zastosowane zasady: Które zasady zostały wzięte pod uwagę.
        -   Wynik: Którzy przewoźnicy zostali pokazani/ukryci i dlaczego.
        -   Migawka zamówienia: Link do wyświetlenia dokładnego stanu koszyka w momencie oceny.
    -   **Filtrowanie i sortowanie:** Standardowe funkcje listy PrestaShop do filtrowania według daty, klienta lub ID koszyka.
-   **Efekt zmian:** Jest to ekran tylko do odczytu, służący do monitorowania i rozwiązywania problemów. Nie można tutaj wprowadzać bezpośrednich zmian, ale dane pomagają zrozumieć, jak działają Twoje zasady.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Użyj tego dziennika do diagnozowania problemów zgłaszanych przez klientów (np. „Nie widziałem darmowej wysyłki”). Możesz znaleźć ich ID koszyka lub ID klienta i zobaczyć dokładnie, które zasady zostały zastosowane i jaki był wynik.
    -   Okresowo przeglądaj dziennik, aby upewnić się, że zasady działają zgodnie z oczekiwaniami, zwłaszcza po wprowadzeniu zmian w zasadach.

#### 2.2.3 Symulator realizacji zamówienia (Panel administracyjny > Moduły > Zasady warunkowej metody wysyłki > Symulator realizacji zamówienia)
To potężne narzędzie pozwala testować zasady wysyłki bez składania prawdziwego zamówienia.

-   **Nazwa ekranu i lokalizacja w menu:** **Zasady warunkowej metody wysyłki > Symulator realizacji zamówienia** (znajduje się w sekcji „Moduły” w menu panelu administracyjnego PrestaShop, widoczny tylko, jeśli „Włącz symulator realizacji zamówienia” jest aktywny w głównej konfiguracji).
-   **Dostępne działania i ustawienia:**
    -   **Wybór klienta:** Wybierz istniejącego klienta ze swojego sklepu lub zasymuluj gościa.
    -   **Wybór adresu:** Wybierz konkretny adres dla wybranego klienta lub ręcznie wprowadź dane adresowe.
    -   **Zawartość koszyka:** Dodaj konkretne produkty, ilości i kombinacje, aby zasymulować koszyk klienta.
    -   **Przycisk symulacji:** Kliknij, aby uruchomić symulację.
    -   **Wyświetlanie wyników:** Pokazuje, które metody wysyłki byłyby dostępne (i które byłyby ukryte wraz z ich komunikatami) dla symulowanego scenariusza. Szczegółowo opisuje również, które zasady zostały zastosowane i dlaczego.
-   **Efekt zmian:** Ten ekran nie zmienia żadnych danych sklepu na żywo. Jest to wyłącznie środowisko testowe.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   **Przed aktywacją nowych zasad:** Zawsze dokładnie je tutaj testuj.
    -   **Rozwiązywanie problemów:** Odtwórz zgłoszony problem klienta, symulując jego dokładny koszyk i adres, aby zobaczyć, dlaczego przewoźnik został lub nie został pokazany.
    -   **Złożone scenariusze:** Testuj przypadki brzegowe, takie jak minimalne/maksymalne wartości zamówienia, specyficzne kombinacje produktów lub różne grupy klientów.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Strategia łączenia dla wielu zasad | Priorytet „UKRYJ” | Jak rozwiązywane są sprzeczne zasady (POKAŻ vs. UKRYJ). |
| | Wyświetlaj komunikaty o niedostępności metody wysyłki | TAK | Pokaż klientom wyjaśnienia dotyczące ukrytych przewoźników. |
| | Retencja dziennika audytu (dni) | 30-90 | Jak długo przechowywane są dzienniki oceny zasad. |
| | Włącz symulator realizacji zamówienia | TAK | Aktywuje narzędzie testowe w panelu administracyjnym. |
| **Zasady wysyłki** | Nazwa zasady | Opisowa nazwa | Identyfikuje zestaw reguł. |
| | Status | Włączone | Aktywuje/dezaktywuje tę konkretną zasadę. |
| | Priorytet | Niższa liczba = wyższy priorytet | Określa kolejność oceny dla sprzecznych zasad. |
| | Przewoźnicy docelowi | Konkretni przewoźnicy | Które metody wysyłki dotyczą tej zasady. |
| | Akcja (POKAŻ/UKRYJ) | POKAŻ/UKRYJ | Czy pokazać, czy ukryć przewoźników docelowych, jeśli warunki są spełnione. |
| | Komunikat o niedostępności | Niestandardowy tekst (wielojęzyczny) | Komunikat wyświetlany, gdy przewoźnik jest ukryty (jeśli włączone). |
| | Kreator warunków | Różne | Definiuje kryteria „JEŚLI” dla zastosowania zasady. |
| **Dziennik audytu** | (Wszystkie kolumny) | N/A (Tylko do odczytu) | Zapewnia historyczne zapisy ocen zasad do rozwiązywania problemów. |
| **Symulator realizacji zamówienia** | (Wszystkie pola) | N/A (Narzędzie testowe) | Pozwala symulować scenariusze klienta/koszyka w celu testowania zasad. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje zasady nie działają lub widzę nieoczekiwane opcje wysyłki. Co powinienem zrobić?**
O1:
1.  **Sprawdź status modułu:** Upewnij się, że ustawienie „Włącz moduł” na głównej stronie konfiguracji jest ustawione na TAK.
2.  **Sprawdź status zasad:** Przejdź do „Zasady wysyłki” i sprawdź, czy konkretne zasady, które mają być aktywne, są włączone.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami PrestaShop buforuje stare konfiguracje.
4.  **Użyj symulatora realizacji zamówienia:** To Twój najlepszy przyjaciel! Odtwórz dokładnie scenariusz (klient, adres, zawartość koszyka) w symulatorze. Pokaże Ci dokładnie, które zasady zostały zastosowane i dlaczego, pomagając zlokalizować problem.
5.  **Przejrzyj dziennik audytu:** Jeśli klient zgłosił problem, sprawdź „Dziennik audytu” dla jego koszyka/ID klienta, aby zobaczyć, jak zasady zostały ocenione dla jego konkretnego zamówienia.
6.  **Strategia łączenia:** Przejrzyj ustawienie „Strategia łączenia dla wielu zasad”. Jeśli masz sprzeczne zasady POKAŻ i UKRYJ, to ustawienie określa wynik.

**P2: Dlaczego mój niestandardowy „Komunikat o niedostępności” się nie wyświetla?**
O2:
1.  **Włącz wyświetlanie komunikatów:** Na głównej stronie konfiguracji modułu upewnij się, że „Wyświetlaj komunikaty o niedostępności metody wysyłki” jest ustawione na TAK.
2.  **Akcja zasady:** Sprawdź, czy „Akcja” zasady jest ustawiona na „UKRYJ” dla przewoźnika docelowego. Komunikaty wyświetlają się tylko, gdy przewoźnik jest ukryty.
3.  **Treść komunikatu:** Upewnij się, że faktycznie wprowadziłeś komunikat w polu „Komunikat o niedostępności” dla konkretnej zasady i że jest on przetłumaczony na odpowiednie języki.

**P3: Moduł spowalnia moją realizację zamówienia. Czy to normalne?**
O3: Moduł jest wysoce zoptymalizowany, ale bardzo złożone zasady (np. setki warunków, wiele zasad) mogą dodać niewielki narzut.
1.  **Uprość zasady:** Przejrzyj swoje zasady. Czy można je połączyć lub uprościć?
2.  **Priorytetyzuj:** Upewnij się, że Twoje najczęściej wyzwalane zasady mają wyższy priorytet (niższą liczbę), aby były oceniane jako pierwsze.
3.  **Rozmiar bazy danych:** Sprawdź ustawienie „Retencja dziennika audytu”. Jeśli jest ustawione na przechowywanie dzienników bezterminowo, bardzo duża tabela dziennika może wpłynąć na wydajność. Ustaw ją na rozsądną liczbę dni (np. 30-90).

**P4: Jak upewnić się, że mój niestandardowy motyw poprawnie wyświetla opcje wysyłki?**
O4: Moduł integruje się ze standardowym procesem realizacji zamówienia PrestaShop.
1.  **Standardowe hooki:** Moduł używa standardowych hooków PrestaShop. Jeśli Twój motyw mocno dostosowuje realizację zamówienia, upewnij się, że nadal poprawnie wywołuje `displayCarrierList` lub podobne hooki, gdzie renderowane są opcje wysyłki.
2.  **Konflikty CSS:** Jeśli wyświetlanie wygląda nieprawidłowo (np. komunikaty są źle wyrównane), może występować konflikt CSS z Twoim motywem. Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać elementy i zidentyfikować sprzeczne reguły CSS. Może być konieczne dodanie niestandardowego CSS do Twojego motywu, aby zastąpić style modułu lub motywu.
3.  **Skontaktuj się z pomocą techniczną:** Jeśli używasz wysoce dostosowanego motywu i napotykasz uporczywe problemy z wyświetlaniem, podaj szczegóły do wsparcia MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Zasady warunkowej metody wysyłki” (`shipmethodrules`) jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop, w dużym stopniu wykorzystując `ObjectModel` do trwałości danych i niestandardowy silnik zasad do oceny reguł. Wprowadza kilka niestandardowych kontrolerów administracyjnych do zarządzania zasadami, przeglądania dzienników audytu i symulowania scenariuszy realizacji zamówienia. Podstawowa logika obraca się wokół obiektów `ShipmethodrulesPolicy`, które hermetyzują encje `ShipmethodrulesConditionGroup` i `ShipmethodrulesCondition`, umożliwiając złożoną zagnieżdżoną logikę ORAZ/LUB. `ShipmethodrulesEngine` jest odpowiedzialny za ocenę tych zasad w stosunku do danego `ShipmethodrulesContext` (reprezentującego bieżący koszyk, klienta i adres) oraz określanie widoczności przewoźników wysyłkowych.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office
-   `controllers/front/index.php`:
    -   Nazwa klasy: `ShipmethodrulesIndexModuleFrontController`
    -   Klasa nadrzędna: `ModuleFrontController`
    -   Odpowiedzialność: Prawdopodobnie jest to symbol zastępczy lub kontroler bazowy. W wielu modułach może to obsługiwać początkową konfigurację lub przekierowanie, jeśli potrzebna jest dedykowana strona front-office. W przypadku tego modułu główna logika front-office jest zintegrowana za pomocą hooków w proces realizacji zamówienia.
-   `controllers/front/simulate.php`:
    -   Nazwa klasy: `ShipmethodrulesSimulateModuleFrontController`
    -   Klasa nadrzędna: `ModuleFrontController`
    -   Odpowiedzialność: Obsługuje żądania AJAX związane z symulatorem realizacji zamówienia. Otrzymuje symulowane dane koszyka, klienta i adresu, a następnie używa `ShipmethodrulesEngine` do oceny zasad i zwraca wynikową widoczność przewoźnika.
-   `controllers/front/visibility.php`:
    -   Nazwa klasy: `ShipmethodrulesVisibilityModuleFrontController`
    -   Klasa nadrzędna: `ModuleFrontController`
    -   Odpowiedzialność: Ten kontroler jest kluczowy dla aktualizacji w czasie rzeczywistym na stronie realizacji zamówienia. Odpowiada na żądania AJAX (np. gdy klient zmienia adres lub zawartość koszyka), aby ponownie ocenić zasady wysyłki i zwrócić zaktualizowaną listę dostępnych przewoźników i ich powiązanych komunikatów.

#### Kontrolery administracyjne Back-Office
-   `controllers/admin/AdminShipmethodrulesAuditLog.php`:
    -   Nazwa klasy: `AdminShipmethodrulesAuditLogController`
    -   Klasa nadrzędna: `ModuleAdminController`
    -   Nazwa zakładki: „Dziennik audytu”
    -   Zarządzana encja: `ShipmethodrulesLog`
    -   Odpowiedzialność: Zarządza wyświetlaniem i filtrowaniem tabeli `ps_shipmethodrules_log`. Zapewnia widok siatki wszystkich ocen zasad, w tym szczegóły dotyczące koszyka, klienta, zastosowanych zasad i ostatecznego wyniku (którzy przewoźnicy zostali pokazani/ukryci).
-   `controllers/admin/AdminShipmethodrulesPolicies.php`:
    -   Nazwa klasy: `AdminShipmethodrulesPoliciesController`
    -   Klasa nadrzędna: `ModuleAdminController`
    -   Nazwa zakładki: „Zasady wysyłki”
    -   Zarządzana encja: `ShipmethodrulesPolicy`
    -   Odpowiedzialność: Jest to główny kontroler do zarządzania zasadami wysyłki. Obsługuje listowanie, dodawanie, edytowanie, duplikowanie, włączanie/wyłączanie i usuwanie obiektów `ShipmethodrulesPolicy`. Koordynuje również interfejs kreatora warunków.
-   `controllers/admin/index.php`:
    -   Nazwa klasy: `ShipmethodrulesAdminController` (lub podobna, jeśli jest to kontroler bazowy dla sekcji administracyjnej modułu)
    -   Klasa nadrzędna: `ModuleAdminController`
    -   Odpowiedzialność: Często działa jako dispatcher lub domyślny kontroler dla głównego wpisu menu administracyjnego modułu, przekierowując do głównej konfiguracji lub listy zasad.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/ShipmethodrulesAdmin.php`: Prawdopodobnie klasa pomocnicza dla wspólnych funkcji związanych z administracją lub statystykami pulpitu nawigacyjnego.
-   `classes/ShipmethodrulesAuditLog.php`: Rozszerza `ObjectModel`. Mapuje do tabeli `ps_shipmethodrules_log`. Przechowuje szczegóły każdego zdarzenia oceny zasad do celów audytu.
    -   Pola `$definition`: `id_cart`, `id_customer`, `id_address_delivery`, `policies_applied`, `carriers_visibility`, `timestamp`.
-   `classes/ShipmethodrulesCompatibility.php`: Udostępnia metody do obsługi różnic między PrestaShop 1.7, 8 i 9, zapewniając kompatybilność między wersjami dla podstawowych funkcji (np. rejestracja hooków, dostęp do konfiguracji).
-   `classes/ShipmethodrulesCondition.php`: Rozszerza `ObjectModel`. Reprezentuje pojedynczy warunek w grupie warunków (np. „Całkowita wartość koszyka > 100 USD”).
    -   Pola `$definition`: `id_shipmethodrules_condition_group`, `type`, `operator`, `value`, `id_product`, `id_category` itp.
-   `classes/ShipmethodrulesConditionEvaluator.php`: Zawiera logikę do oceny pojedynczego `ShipmethodrulesCondition` w stosunku do bieżącego `ShipmethodrulesContext`.
-   `classes/ShipmethodrulesConditionGroup.php`: Rozszerza `ObjectModel`. Reprezentuje grupę warunków połączonych operatorem ORAZ. Wiele grup może być połączonych operatorem LUB w ramach zasady.
    -   Pola `$definition`: `id_shipmethodrules_policy`, `logic_operator` (niejawnie ORAZ dla warunków wewnątrz, LUB dla grup).
-   `classes/ShipmethodrulesConditionTree.php`: Zarządza hierarchiczną strukturą warunków i grup warunków dla zasady, ułatwiając ich przechowywanie i pobieranie.
-   `classes/ShipmethodrulesContext.php`: Obiekt, który hermetyzuje wszystkie istotne dane do oceny zasad: bieżący `Cart`, `Customer`, `Address`, `Currency`, `Language` itp. Zapewnia to spójny interfejs dla `ShipmethodrulesEngine`.
-   `classes/ShipmethodrulesDashboard.php`: Klasa pomocnicza do generowania statystyk pulpitu nawigacyjnego lub podsumowań związanych z aktywnością modułu.
-   `classes/ShipmethodrulesEngine.php`: Centralna klasa do oceny zasad. Przyjmuje `ShipmethodrulesContext` i listę obiektów `ShipmethodrulesPolicy`, stosuje skonfigurowaną strategię łączenia i zwraca ostateczny status widoczności dla każdego przewoźnika.
-   `classes/ShipmethodrulesListRenderer.php`: Niestandardowy renderer dla list administracyjnych, potencjalnie dodający specyficzne działania (takie jak duplikowanie) lub niestandardowe formatowanie kolumn.
-   `classes/ShipmethodrulesLog.php`: Alias lub specyficzna implementacja dla `ShipmethodrulesAuditLog`.
-   `classes/ShipmethodrulesOrderSnapshot.php`: Przechwytuje i przechowuje migawkę stanu zamówienia (koszyk, klient, adres) w momencie oceny zasad, przydatne do debugowania.
-   `classes/ShipmethodrulesPolicy.php`: Rozszerza `ObjectModel`. Główny model dla zasady wysyłki. Zawiera nazwę zasady, status, priorytet, przewoźników docelowych, akcję (POKAŻ/UKRYJ), komunikat o niedostępności i kolekcję obiektów `ShipmethodrulesConditionGroup`.
    -   Pola `$definition`: `name`, `active`, `priority`, `action`, `unavailable_message`, `target_carriers`.
-   `classes/ShipmethodrulesPolicyDuplicator.php`: Obsługuje logikę duplikowania `ShipmethodrulesPolicy`, w tym wszystkich powiązanych grup warunków i warunków.
-   `classes/ShipmethodrulesPreset.php`: Prawdopodobnie zarządza predefiniowanymi zestawami warunków lub zasad, które można szybko zastosować.
-   `classes/ShipmethodrulesRule.php`: Bardziej ogólna reprezentacja zasady, prawdopodobnie abstrakcyjna klasa bazowa lub starsza iteracja `ShipmethodrulesPolicy`.
-   `classes/ShipmethodrulesTreeRepository.php`: Zarządza trwałością i pobieraniem struktury drzewa warunków.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `shipmethodrules/lib/searchTool/views/js/autocomplete.js`: Ogólna funkcjonalność autouzupełniania, prawdopodobnie używana do wyszukiwania produktów, kategorii lub klientów w kreatorze warunków.
-   `shipmethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplikat lub specyficzna instancja skryptu autouzupełniania.
-   `shipmethodrules/views/js/adminConditionBuilder.js`: Obsługuje dynamiczne tworzenie, modyfikowanie i usuwanie warunków i grup warunków w interfejsie edycji zasad. Zarządza złożonym interfejsem użytkownika do budowania reguł.
-   `shipmethodrules/views/js/adminPolicyRules.js`: Specyficzny JS dla kontrolera `AdminShipmethodrulesPolicies`, zarządzający listą zasad, działaniami masowymi i potencjalnie interakcjami z kreatorem warunków.
-   `shipmethodrules/views/js/adminShipmethodrulesDashboard.js`: Skrypty dla wszelkich widżetów pulpitu nawigacyjnego lub statystyk wyświetlanych w sekcji administracyjnej modułu.
-   `shipmethodrules/views/js/adminShipmethodrulesSearchTool.js`: Integruje narzędzie wyszukiwania (autouzupełnianie) specjalnie dla formularzy administracyjnych modułu.
-   `shipmethodrules/views/js/adminShipmethodrulesSimulator.js`: Zasila interfejs „Symulatora realizacji zamówienia”, obsługując dane wejściowe użytkownika dla klienta, adresu i koszyka oraz wykonując wywołania AJAX do `controllers/front/simulate.php`.
-   `shipmethodrules/views/js/checkout.js`: Skrypt front-office wstrzykiwany do procesu realizacji zamówienia. Nasłuchuje zmian w koszyku lub adresie dostawy, a następnie wykonuje wywołania AJAX do `controllers/front/visibility.php`, aby dynamicznie aktualizować wyświetlane metody wysyłki.
-   `shipmethodrules/views/js/unavailableUi.js`: Obsługuje wyświetlanie i stylizowanie komunikatów o niedostępności metody wysyłki na stronie realizacji zamówienia w front office.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `shipmethodrules/lib/searchTool/views/css/autocomplete.css`: Style dla narzędzia wyszukiwania autouzupełniania.
-   `shipmethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplikat lub specyficzna instancja stylów autouzupełniania.
-   `shipmethodrules/views/css/admin_order_snapshot.css`: Style do wyświetlania szczegółów migawki zamówienia w dzienniku audytu lub symulatorze.
-   `shipmethodrules/views/css/admin_shipmethodrules.css`: Ogólne style dla interfejsów back-office modułu, w tym list zasad, kreatora warunków i symulatora.
-   `shipmethodrules/views/css/front.css`: Style front-office do wyświetlania komunikatów o niedostępności metody wysyłki lub wyróżniania konkretnych opcji wysyłki na stronie realizacji zamówienia.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)
-   `shipmethodrules/views/templates/hook/carrier_guard.tpl`: Renderuje ukryte pole wejściowe lub skrypt, aby „chronić” przed nieprawidłowymi wyborami przewoźników, zapewniając, że tylko dozwoleni przewoźnicy mogą zostać przesłani.
-   `shipmethodrules/views/templates/hook/carrier_list.tpl`: Zastępuje lub rozszerza domyślny szablon listy przewoźników w realizacji zamówienia, aby zastosować zasady widoczności i wyświetlić komunikaty o niedostępności. Tutaj faktycznie renderowana jest filtrowana lista przewoźników.

#### Szablony administracyjne (`views/templates/admin/`)
-   `shipmethodrules/views/templates/admin/auditPreview.tpl`: Szablon do wyświetlania szczegółowego podglądu wpisu dziennika audytu.
-   `shipmethodrules/views/templates/admin/dashboard.tpl`: Szablon dla głównej konfiguracji modułu lub widoku pulpitu nawigacyjnego.
-   `shipmethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Niestandardowy szablon dla przycisku akcji „duplikuj” na listach administracyjnych (np. dla zasad).
-   `shipmethodrules/views/templates/admin/policiesPreview.tpl`: Szablon do wyświetlania podglądu zasady wysyłki.
-   `shipmethodrules/views/templates/admin/policyConditionBuilder.tpl`: Złożony szablon, który renderuje interfejs użytkownika do budowania warunków (listy rozwijane, pola wejściowe, logika ORAZ/LUB).
-   `shipmethodrules/views/templates/admin/policyRuleCard.tpl`: Renderuje pojedynczą zasadę lub politykę jako kartę w widoku listy.
-   `shipmethodrules/views/templates/admin/policyRulesTable.tpl`: Renderuje tabelę zasad wysyłki.
-   `shipmethodrules/views/templates/admin/scopeSelector.tpl`: Szablon do wyboru zakresu warunku (np. „Całkowita wartość koszyka”, „Grupa klientów”).

#### Inne szablony
-   `shipmethodrules/lib/searchTool/views/scripts.tpl`: Zawiera JavaScript dla narzędzia wyszukiwania.
-   `shipmethodrules/lib/searchTool/views/views/scripts.tpl`: Duplikat lub specyficzna instancja skryptów narzędzia wyszukiwania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych
-   `ps_shipmethodrules_policy`: Przechowuje główne definicje zasad wysyłki (nazwa, status aktywności, priorytet, akcja, komunikat o niedostępności, przewoźnicy docelowi).
-   `ps_shipmethodrules_condition_group`: Przechowuje grupy warunków powiązanych z zasadą.
-   `ps_shipmethodrules_condition`: Przechowuje pojedyncze warunki (typ, operator, wartość, powiązane encje, takie jak ID produktu/kategorii).
-   `ps_shipmethodrules_log`: Przechowuje wpisy dziennika audytu ocen zasad (ID koszyka, ID klienta, znacznik czasu, zastosowane zasady, widoczność przewoźników).
-   `ps_shipmethodrules_order_snapshot`: Przechowuje szczegółowe migawki danych koszyka/zamówienia dla wpisów dziennika audytu.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` wszystkich stron front-office. | Wstrzykuje niezbędne pliki CSS i JS dla funkcjonalności front-office (np. `checkout.js`, `front.css`). |
| `displayCarrierList` | Na stronie realizacji zamówienia, gdzie wyświetlane są metody wysyłki. | Główny hook do filtrowania i renderowania dostępnych metod wysyłki na podstawie zdefiniowanych zasad. |
| `actionCarrierProcess` | Po wybraniu przewoźnika, ale przed zatwierdzeniem zamówienia. | Działa jako „strażnik” do ponownej walidacji wybranego przewoźnika w stosunku do zasad, zapobiegając przesłaniu nieprawidłowego wyboru. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Potencjalnie loguje ostatecznie wybraną metodę wysyłki i zastosowane zasady do dziennika audytu. |
| `actionAdminControllerSetMedia` | W panelu administracyjnym, gdy ładowany jest kontroler administracyjny. | Wstrzykuje CSS i JS dla interfejsów administracyjnych modułu (kreator zasad, symulator, dziennik audytu). |
| `actionObjectCarrierAddAfter` | Po dodaniu nowego przewoźnika. | Potencjalnie aktualizuje wewnętrzne dane modułu lub pamięci podręczne związane z przewoźnikami. |
| `actionObjectCarrierUpdateAfter` | Po zaktualizowaniu przewoźnika. | Potencjalnie aktualizuje wewnętrzne dane modułu lub pamięci podręczne związane z przewoźnikami. |
| `actionObjectCarrierDeleteAfter` | Po usunięciu przewoźnika. | Czyści wszelkie odniesienia do usuniętego przewoźnika w zasadach. |
| `displayBackOfficeHeader` | W nagłówku wszystkich stron back-office. | Wstrzykuje globalne CSS/JS administracyjne lub specyficzne skrypty dla stron administracyjnych modułu. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zasady warunkowej metody wysyłki”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
