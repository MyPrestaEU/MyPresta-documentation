---
title: "Block Search Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu Block Search Pro dla PrestaShop od MyPresta.eu."
sidebar:
  label: "Block Search Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Block Search Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-search-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/block-search-pro/)
>
> ---


# Block Search Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Block Search Pro)

Jest to główny ekran konfiguracji, na którym kontrolujesz, jak moduł Block Search Pro zachowuje się i wygląda w Twoim sklepie.

#### 2.1.1 Ustawienia ogólne

**1. Włącz wyszukiwanie AJAX**

- **Co robi to ustawienie:** Kontroluje, czy wyniki wyszukiwania pojawiają się natychmiast, gdy klient pisze (AJAX), czy też musi nacisnąć Enter/kliknąć przycisk wyszukiwania, aby zobaczyć wyniki.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Gdy klienci piszą w pasku wyszukiwania, lista rozwijana pasujących produktów pojawi się w czasie rzeczywistym poniżej pola wyszukiwania. Zapewnia to natychmiastową informację zwrotną i przyspiesza proces wyszukiwania.
  - *Gdy wyłączone (NIE):* Klienci muszą wpisać pełne zapytanie wyszukiwania, a następnie nacisnąć Enter lub kliknąć przycisk wyszukiwania, aby zostać przekierowanym na stronę wyników wyszukiwania.
- **Zalecana wartość:** TAK. Znacząco poprawia to doświadczenie użytkownika, oferując natychmiastową satysfakcję i redukując kroki do znalezienia produktu.
- **Scenariusz/przykład dla sprzedawcy:** Klient wpisuje „sukienka” i natychmiast widzi sugestie, takie jak „Czerwona sukienka wieczorowa”, „Letnia sukienka maxi” i „Czarna sukienka koktajlowa”, co pozwala mu kliknąć bezpośrednio na stronę produktu bez czekania.

**2. Wyszukiwanie błyskawiczne**

- **Co robi to ustawienie:** Podobnie jak wyszukiwanie AJAX, odnosi się to konkretnie do „błyskawicznego” wyświetlania wyników wyszukiwania na samej stronie wyników wyszukiwania, aktualizującego się w miarę, jak użytkownik precyzuje swoje zapytanie. (Uwaga: W wielu nowoczesnych wersjach PrestaShop „wyszukiwanie AJAX” często obejmuje natychmiastową listę rozwijaną, podczas gdy „Wyszukiwanie błyskawiczne” może odnosić się do zachowania na rzeczywistej stronie wyników wyszukiwania).
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Jeśli klient znajduje się na stronie wyników wyszukiwania i modyfikuje swoje zapytanie wyszukiwania w pasku wyszukiwania, wyniki na tej stronie zostaną zaktualizowane natychmiast bez pełnego przeładowania strony.
  - *Gdy wyłączone (NIE):* Klient musiałby ponownie przesłać zmodyfikowane zapytanie wyszukiwania, aby strona wyników się odświeżyła.
- **Zalecana wartość:** TAK. Zapewnia to bardziej dynamiczne i responsywne doświadczenie wyszukiwania.
- **Scenariusz/przykład dla sprzedawcy:** Klient szuka „butów”, trafia na stronę wyników wyszukiwania, a następnie wpisuje „czerwone” w pasku wyszukiwania na tej stronie. Dzięki wyszukiwaniu błyskawicznemu wyniki natychmiast filtrują się, aby pokazać tylko czerwone buty.

**3. Zezwól na wysyłanie wyszukiwania z pustym polem słowa kluczowego**

- **Co robi to ustawienie:** Określa, czy klient może kliknąć przycisk wyszukiwania lub nacisnąć Enter bez wpisywania żadnych słów kluczowych.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Jeśli klient kliknie wyszukiwanie z pustym polem, zostanie przekierowany na ogólną stronę wyników wyszukiwania, która może wyświetlać wszystkie produkty lub domyślny komunikat w zależności od Twojego motywu. Może to być czasami używane do przeglądania wszystkich produktów.
  - *Gdy wyłączone (NIE):* Przycisk wyszukiwania będzie nieaktywny lub wyświetli komunikat o błędzie, jeśli pole wprowadzania jest puste, zmuszając klienta do wpisania słowa kluczowego przed wyszukiwaniem.
- **Zalecana wartość:** NIE. Generalnie lepiej jest kierować klientów do wprowadzenia zapytania, aby uniknąć zamieszania lub pustych stron wyników wyszukiwania.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli klient przypadkowo kliknie wyszukiwanie bez wpisywania, wyłączenie tej opcji zapobiega lądowaniu na potencjalnie mylącej pustej stronie.

**4. Minimalna długość słowa (w znakach)**

- **Co robi to ustawienie:** Ustawia minimalną liczbę znaków, które klient musi wpisać, zanim funkcja wyszukiwania (w tym wyszukiwanie AJAX/błyskawiczne) zacznie szukać wyników.
- **Efekt zmiany tego ustawienia:**
  - *Ustawione na 3:* Klienci muszą wpisać co najmniej trzy znaki (np. „czer”) zanim pojawią się jakiekolwiek sugestie wyszukiwania lub wyszukiwanie zostanie przesłane.
  - *Ustawione na 1:* Nawet pojedynczy znak (np. „a”) wywoła wyszukiwanie.
- **Zalecana wartość:** 3. Zapewnia to równowagę między responsywnością a trafnością. Zbyt niska wartość (np. 1-2 znaki) może generować zbyt wiele nieistotnych sugestii, podczas gdy zbyt wysoka może frustrować użytkowników.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli ustawione na 3, wpisanie „bu” nie pokaże wyników, ale wpisanie „but” zacznie wyświetlać sugestie dla „buty”, „bluzy” itp.

#### 2.1.2 Opcje filtrowania wyszukiwania

**5. Wybierz kategorie**

- **Co robi to ustawienie:** Pozwala ograniczyć wyszukiwanie tylko do określonych kategorii produktów. Moduł zwróci wyniki tylko z kategorii, które tutaj wybierzesz.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrane są konkretne kategorie:* Wyszukiwanie będzie dotyczyć tylko produktów w wybranych kategoriach. Produkty w niewybranych kategoriach nie pojawią się w wynikach wyszukiwania, nawet jeśli pasują do słowa kluczowego.
  - *Gdy nie wybrano żadnych kategorii:* Wyszukiwanie domyślnie będzie przeszukiwać wszystkie kategorie w Twoim sklepie.
- **Zalecana wartość:** Wybierz kategorie, jeśli chcesz kierować klientów do konkretnych typów produktów, lub pozostaw puste, jeśli chcesz szerokiego wyszukiwania.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz zarówno odzież, jak i elektronikę, ale chcesz, aby pasek wyszukiwania w nagłówku znajdował tylko odzież, wybierz tutaj tylko kategorie odzieżowe.

**6. Szukaj w podkategoriach**

- **Co robi to ustawienie:** Ta opcja działa w połączeniu z „Wybierz kategorie”. Określa, czy wyszukiwanie powinno również obejmować produkty w podkategoriach wybranych kategorii nadrzędnych.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Jeśli wybierzesz „Elektronika” jako kategorię, wyszukiwanie będzie również przeszukiwać „Laptopy”, „Smartfony” i wszelkie inne podkategorie „Elektroniki”.
  - *Gdy wyłączone (NIE):* Wyszukiwanie będzie dotyczyć tylko produktów bezpośrednio przypisanych do wybranych kategorii nadrzędnych, ignorując ich podkategorie.
- **Zalecana wartość:** TAK. Większość sprzedawców chce, aby wyszukiwania były kompleksowe w ramach wybranego drzewa kategorii.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli wybierzesz „Odzież” i włączysz „Szukaj w podkategoriach”, wyszukiwanie „koszula” znajdzie koszule w „T-shirtach męskich”, „Bluzkach damskich” itp.

**7. Producenci**

- **Co robi to ustawienie:** Pozwala ograniczyć wyszukiwanie tylko do produktów od określonych producentów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrani są konkretni producenci:* Wyszukiwanie zwróci tylko produkty wyprodukowane przez wybranych producentów. Produkty od niewybranych producentów nie pojawią się.
  - *Gdy nie wybrano żadnych producentów:* Wyszukiwanie domyślnie będzie przeszukiwać wszystkich producentów w Twoim sklepie.
- **Zalecana wartość:** Wybierz producentów, jeśli chcesz zaoferować wyszukiwanie specyficzne dla marki, lub pozostaw puste dla ogólnego wyszukiwania.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli masz dedykowany blok wyszukiwania dla „Marek Premium”, możesz wybrać tutaj tylko producentów z wyższej półki.

#### 2.1.3 Ustawienia wyświetlania

**8. Rozmiar bloku wyszukiwania**

- **Co robi to ustawienie:** Kontroluje wizualną szerokość pola wprowadzania wyszukiwania w pikselach.
- **Efekt zmiany tego ustawienia:**
  - *Ustawione na 280px:* Pasek wyszukiwania będzie miał 280 pikseli szerokości.
  - *Ustawione na 100% (lub pozostaw puste dla automatycznego wykrywania):* Pasek wyszukiwania dostosuje się do dostępnej przestrzeni, często wypełniając swój kontener.
- **Zalecana wartość:** Pozostaw puste dla automatycznego wykrywania lub ustaw na procent (np. 100%), aby zapewnić responsywność. Jeśli potrzebujesz stałej szerokości ze względów projektowych, określ wartość w pikselach.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój motyw ma bardzo wąski nagłówek, może być konieczne dostosowanie tego ustawienia, aby pasek wyszukiwania pasował bez naruszania układu. W przypadku większości nowoczesnych motywów najlepiej jest pozwolić motywowi zarządzać szerokością.

#### 2.1.4 Inne ustawienia

**9. Ustawienia aktualizacji na żywo MyPresta.eu (`mypresta_updates`, `update_`, `updatev_`)**

- **Co robi to ustawienie:** Są to wewnętrzne ustawienia związane z systemem aktualizacji modułów MyPresta.eu. Pozwalają modułowi sprawdzać i powiadamiać Cię o nowych wersjach.
- **Efekt zmiany tego ustawienia:** Nie są one konfigurowalne bezpośrednio przez interfejs użytkownika, ale są zarządzane przez sam moduł. Zapewnienie, że Twój sklep ma dostęp do internetu, pozwala na funkcjonowanie tych kontroli.
- **Zalecana wartość:** Są to ustawienia wewnętrzne i nie powinny być zmieniane ręcznie.
- **Scenariusz/przykład dla sprzedawcy:** Otrzymasz powiadomienie w panelu administracyjnym PrestaShop, jeśli dostępna jest nowa wersja Block Search Pro, co zapewni, że Twój moduł będzie aktualny z najnowszymi funkcjami i poprawkami bezpieczeństwa.

**10. `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**

- **Co robi to ustawienie:** Są to standardowe zmienne konfiguracyjne PrestaShop związane z domyślnym językiem Twojego sklepu i tym, czy pracownicy mogą zmieniać język formularzy w panelu administracyjnym. Moduł używa ich, aby upewnić się, że wyświetla się poprawnie w aktywnym języku panelu administracyjnego.
- **Efekt zmiany tego ustawienia:** Są to globalne ustawienia PrestaShop i nie są bezpośrednio kontrolowane przez Block Search Pro. Moduł po prostu je odczytuje, aby dostosować swoje wyświetlanie.
- **Zalecana wartość:** Zarządzane przez ogólną konfigurację PrestaShop.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój panel administracyjny jest ustawiony na francuski, etykiety konfiguracji modułu pojawią się w języku francuskim (jeśli dostępne są tłumaczenia).

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz wyszukiwanie AJAX | TAK | Pokazuje natychmiastowe sugestie produktów podczas pisania przez klienta. |
| Konfiguracja modułu | Wyszukiwanie błyskawiczne | TAK | Natychmiast aktualizuje stronę wyników wyszukiwania po zmianie zapytania. |
| Konfiguracja modułu | Zezwól na wysyłanie wyszukiwania z pustym polem słowa kluczowego | NIE | Zapobiega wyszukiwaniu z pustym polem wprowadzania. |
| Konfiguracja modułu | Minimalna długość słowa (w znakach) | 3 | Minimalna liczba znaków wymagana do uruchomienia wyszukiwania. |
| Konfiguracja modułu | Wybierz kategorie | Pozostaw puste (szuka we wszystkich) | Ogranicza wyszukiwanie do wybranych kategorii. |
| Konfiguracja modułu | Szukaj w podkategoriach | TAK | Uwzględnia podkategorie, gdy wybrane są kategorie nadrzędne. |
| Konfiguracja modułu | Producenci | Pozostaw puste (szuka we wszystkich) | Ogranicza wyszukiwanie do wybranych producentów. |
| Konfiguracja modułu | Rozmiar bloku wyszukiwania | Pozostaw puste (auto-wykrywanie) | Wizualna szerokość pola wprowadzania wyszukiwania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje wyniki wyszukiwania nie pokazują produktów, o których wiem, że istnieją. Co jest nie tak?**
O1: Sprawdź ustawienia „Wybierz kategorie” i „Producenci” w konfiguracji modułu. Jeśli ograniczyłeś wyszukiwanie do określonych kategorii lub producentów, produkty spoza tych wyborów nie pojawią się. Upewnij się również, że Twoje produkty są aktywne i widoczne w wybranych kategoriach.

**P2: Wyszukiwanie błyskawiczne (AJAX) nie działa lub sugestie z listy rozwijanej nie pojawiają się.**
O2:
\* **Włącz wyszukiwanie AJAX:** Upewnij się, że „Włącz wyszukiwanie AJAX” jest ustawione na TAK w konfiguracji modułu.
\* **Minimalna długość słowa:** Sprawdź „Minimalna długość słowa”. Jeśli jest ustawiona zbyt wysoko, sugestie nie pojawią się, dopóki nie zostanie wpisana wystarczająca liczba znaków.
\* **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną PrestaShop (pamięć podręczna Smarty, pamięć podręczna systemu plików).
\* **Konflikty motywów:** Czasami niestandardowe motywy lub inne moduły mogą kolidować z funkcjonalnością AJAX. Tymczasowo wyłącz inne moduły lub przełącz się na domyślny motyw PrestaShop, aby zdiagnozować problem.
\* **Błędy JavaScript:** Otwórz konsolę programisty w przeglądarce (F12) i sprawdź, czy nie ma błędów JavaScript. Jeśli widzisz błędy, skontaktuj się z pomocą techniczną MyPresta.eu.

**P3: Blok wyszukiwania wygląda dziwnie lub nie pasuje do mojego motywu.**
O3:
\* **Rozmiar bloku wyszukiwania:** Dostosuj ustawienie „Rozmiar bloku wyszukiwania” w konfiguracji modułu. Spróbuj pozostawić je puste dla automatycznego wykrywania lub ustawić na procent (np. 100%).
\* **Konflikty CSS:** CSS Twojego motywu może nadpisywać style modułu. Zazwyczaj wymaga to od webmastera sprawdzenia CSS.
\* **Umiejscowienie haka:** Upewnij się, że moduł jest podłączony do odpowiedniej pozycji (np. `displayTop`), która ma wystarczająco dużo miejsca w Twoim motywie. Możesz zarządzać pozycjami modułów w **Wygląd > Pozycje**.

**P4: Jak przetłumaczyć tekst bloku wyszukiwania (np. „Szukaj w naszym katalogu”)?**
O4:
\* Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.
\* Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz swój język.
\* Znajdź moduł „Block Search Pro” na liście i możesz tam edytować ciągi tekstowe.

**P5: Chcę umieścić blok wyszukiwania w innym miejscu na mojej stronie.**
O5:
\* Przejdź do **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach PS).
\* Znajdź moduł „Block Search Pro” na liście modułów.
\* Możesz „przeszczepić” (podłączyć) moduł do różnych dostępnych haków, takich jak `displayHeader`, `displayTop`, `displayLeftColumn`, `displayRightColumn` lub `displayNav`. Przeciągnij i upuść, aby zmienić kolejność w ramach haka.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu Block Search Pro dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł Block Search Pro rozszerza podstawową funkcjonalność wyszukiwania PrestaShop poprzez nadpisanie klasy `Search`, co pozwala mu wstrzykiwać niestandardową logikę filtrowania (kategorie, producenci) do zapytania wyszukiwania. Wykorzystuje standardowe wzorce MVC PrestaShop do wyświetlania w front-office (haki, szablony) i konfiguracji w back-office (metoda `getContent()` w głównym pliku modułu). Funkcjonalność AJAX jest obsługiwana za pośrednictwem dedykowanego pliku JavaScript, który współdziała z podstawowym mechanizmem wyszukiwania PrestaShop.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza niestandardowych kontrolerów Front-Office ani Back-Office Admin. Jego funkcjonalność front-office jest głównie obsługiwana przez nadpisaną klasę `Search`, a jej wyświetlanie za pośrednictwem haków modułu. Konfiguracja back-office jest zarządzana bezpośrednio w metodzie `getContent()` pliku modułu `blocksearchpro.php`.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   **`blocksearchpro/override/classes/index.php`**:
    -   Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach, aby zapobiec listowaniu katalogów. Nie ma on wpływu funkcjonalnego na logikę modułu.
-   **`blocksearchpro/override/classes/Search.php`**:
    -   **Nazwa klasy**: `Search` (nadpisuje podstawową klasę `Search`)
    -   **Klasa nadrzędna**: `SearchCore`
    -   **Odpowiedzialność**: Jest to najważniejszy plik. Nadpisuje domyślną klasę `Search` PrestaShop, w szczególności modyfikując metodę `find()` (lub podobne metody związane z wyszukiwaniem), aby włączyć niestandardową logikę filtrowania modułu.
        -   Odczytuje wartości konfiguracyjne (`bsp_cat_exc`, `bsp_subcat`, `bsp_cat`, `bsp_man`) z `ps_configuration`.
        -   Modyfikuje zapytanie SQL używane do wyszukiwania produktów, aby uwzględnić klauzule `WHERE`, które filtrują według wybranych kategorii i/lub producentów.
        -   Zapewnia, że wyszukiwanie uwzględnia ustawienie „Szukaj w podkategoriach”, gdy zastosowane są filtry kategorii.
        -   To nadpisanie pozwala modułowi wstrzykiwać jego możliwości filtrowania bezpośrednio do podstawowego mechanizmu wyszukiwania PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`blocksearchpro/blocksearchpro.js`**:
    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Ten skrypt poprawia doświadczenie użytkownika dla bloku wyszukiwania.
        -   Prawdopodobnie wiąże słuchaczy zdarzeń z polem wprowadzania wyszukiwania (np. `keyup`, `focus`, `blur`).
        -   Obsługuje żądania AJAX dla natychmiastowych sugestii wyszukiwania, wysyłając bieżącą wartość wprowadzania do podstawowego punktu końcowego AJAX wyszukiwania PrestaShop.
        -   Przetwarza odpowiedź JSON z wywołania AJAX i dynamicznie wypełnia listę rozwijaną sugestii produktów poniżej paska wyszukiwania.
        -   Zarządza wyświetlaniem i ukrywaniem listy sugestii, nawigacją klawiaturą w ramach sugestii oraz zdarzeniami kliknięcia na sugestie w celu przekierowania na strony produktów.
        -   Może również obsługiwać logikę „Zezwól na wysyłanie wyszukiwania z pustym polem słowa kluczowego” po stronie klienta.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`blocksearchpro/blocksearchpro.css`**:
    -   **Zakres**: Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**:
        -   Samo pole wprowadzania wyszukiwania (`#search_query_top`, `.search_query`).
        -   Przycisk wyszukiwania (`#search_button`, `.button-search`).
        -   Kontener dla sugestii wyszukiwania AJAX (`.ac_results`, `.block_search_pro_results`).
        -   Poszczególne elementy sugestii w liście rozwijanej.
        -   Zapewnia responsywność dla różnych rozmiarów ekranu.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**:
        -   `.block_search_pro` (główny kontener)
        -   `.search_query` (pole wprowadzania)
        -   `.button-search` (przycisk wysyłania)
        -   `.ac_results` (kontener wyników AJAX)
        -   `.ac_odd`, `.ac_even`, `.ac_over` (stylizacja dla elementów sugestii i stanów najechania)
        -   Programiści mogą nadpisać te style w pliku `custom.css` swojego motywu lub tworząc motyw potomny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   **`blocksearchpro/blocksearchpro-top.tpl`**:
        -   **Hak**: `displayTop`, `displayNav` (i potencjalnie `displayHeader` w zależności od motywu).
        -   **Cel**: Renderuje pole wprowadzania wyszukiwania i przycisk, zazwyczaj dla głównego paska wyszukiwania w nagłówku. Zawiera niezbędną strukturę HTML dla formularza wyszukiwania i kontenera wyników AJAX.
    -   **`blocksearchpro/blocksearchpro.tpl`**:
        -   **Hak**: `displayLeftColumn`, `displayRightColumn`.
        -   **Cel**: Renderuje blok wyszukiwania dla bocznych kolumn. Ten szablon może mieć nieco inny układ lub stylizację w porównaniu do górnego paska wyszukiwania, zoptymalizowany pod kątem węższych przestrzeni kolumn. Zawiera również formularz wyszukiwania i kontener wyników AJAX.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:
    -   Ten moduł nie tworzy niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli PrestaShop `ps_configuration`.
    -   Używane klucze konfiguracyjne: `mypresta_updates`, `update_`, `updatev_`, `PS_SEARCH_AJAX`, `bsp_cat_exc`, `PS_INSTANT_SEARCH`, `bsp_empty`, `PS_SEARCH_MINWORDLEN`, `bsp_subcat`, `bsp_cat`, `bsp_man`, `bsp_size`.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje zasoby CSS (`blocksearchpro.css`) i JavaScript (`blocksearchpro.js`) dla funkcjonalności front-office. |
| `displayTop` | Zazwyczaj w głównym obszarze nagłówka sklepu. | Renderuje blok wyszukiwania za pomocą `blocksearchpro-top.tpl`. |
| `displayNav` | Często w bardzo górnym pasku nawigacji (powyżej `displayTop`). | Renderuje blok wyszukiwania za pomocą `blocksearchpro-top.tpl`. |
| `displayLeftColumn` | W lewym pasku bocznym stron, które go posiadają. | Renderuje blok wyszukiwania za pomocą `blocksearchpro.tpl`. |
| `displayRightColumn` | W prawym pasku bocznym stron, które go posiadają. | Renderuje blok wyszukiwania za pomocą `blocksearchpro.tpl`. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | (Nie jest bezpośrednio używany przez ten moduł do jego podstawowej funkcjonalności wyszukiwania, ale jest to wspólny hak dla innych modułów. Brak konkretnej akcji tutaj dla Block Search Pro.) |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem Block Search Pro, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest gotowy pomóc w przypadku wszelkich problemów lub pytań.
