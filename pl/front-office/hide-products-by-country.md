---
title: "Ukryj produkty według kraju - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Ukryj produkty według kraju” od MyPresta.eu."
sidebar:
  label: "Ukryj produkty według kraju - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Hide products by country na MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-products-by-country.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/hide-products-by-country/)
>
> ---


# Ukryj produkty według kraju

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Możesz uzyskać dostęp do konfiguracji modułu, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Ukryj produkty według kraju”, a następnie klikając „Konfiguruj”.

#### Ustawienia ogólne

-   **Włączony / Wyłączony (Przełącznik)**

    -   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł aktywnie filtruje produkty na podstawie Twoich ustawień.
        -   *Gdy wyłączony:* Moduł przestaje filtrować produkty, a wszystkie produkty będą widoczne dla wszystkich klientów niezależnie od kraju.
    -   **Zalecana wartość:** **Włączony** po skonfigurowaniu reguł.
    -   **Scenariusz / przykład dla sprzedawcy:** Konfigurujesz moduł po raz pierwszy i chcesz go przetestować przed uruchomieniem, więc pozostawiasz go wyłączonym. Gdy jest gotowy, włączasz go.
-   **Co chcesz zrobić? (Lista rozwijana)**

    -   **Co robi to ustawienie:** Definiuje podstawową logikę Twoich reguł ukrywania produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ukryj produkty dla wybranych krajów:* Produkty wybrane w sekcjach „Wybierz kategorie” i „Wybierz producenta” zostaną ukryte przed klientami z listy „Wybierz kraje”. Jest to najczęstszy przypadek użycia.
        -   *Pokaż produkty tylko dla wybranych krajów:* Wybrane produkty będą widoczne TYLKO dla klientów z listy „Wybierz kraje”. Dla wszystkich innych krajów te produkty zostaną ukryte.
    -   **Zalecana wartość:** Zazwyczaj **Ukryj produkty dla wybranych krajów**.
    -   **Scenariusz / przykład dla sprzedawcy:**
        -   *Ukryj produkty:* Sprzedajesz konkretną markę, której nie można sprzedawać w Niemczech. Wybierasz „Ukryj produkty dla wybranych krajów”, wybierasz markę i wybierasz Niemcy.
        -   *Pokaż produkty tylko:* Masz specjalną kolekcję produktów wyłącznie na rynek amerykański. Wybierasz „Pokaż produkty tylko dla wybranych krajów”, wybierasz kolekcję i wybierasz Stany Zjednoczone.
-   **Wybierz kraje (Lista wielokrotnego wyboru)**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretne kraje, do których będzie stosowana Twoja reguła „Co chcesz zrobić?”.
    -   **Efekt zmiany tego ustawienia:** Tylko klienci zidentyfikowani jako pochodzący z tych wybranych krajów zostaną objęci ustawionymi przez Ciebie regułami widoczności produktów.
    -   **Zalecana wartość:** Wybierz wszystkie odpowiednie kraje dla swoich reguł.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli ukrywasz produkty dla klientów we Francji i Hiszpanii, wybierzesz „Francja” i „Hiszpania” z tej listy.
-   **Wybierz kategorie (Drzewo kategorii)**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretne kategorie produktów, których produkty będą podlegać regule ukrywania/pokazywania.
    -   **Efekt zmiany tego ustawienia:** Wszystkie produkty w wybranych kategoriach (i ich podkategoriach, jeśli zdecydujesz się je uwzględnić) zostaną objęte regułą „Co chcesz zrobić?”.
    -   **Zalecana wartość:** Wybierz kategorie zawierające produkty, które chcesz kontrolować.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz ukryć wszystkie produkty w kategorii „Elektronika” dla klientów w Kanadzie. Wybierzesz tutaj „Elektronika”.
-   **Wybierz producenta (Lista wielokrotnego wyboru)**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretnych producentów, których produkty będą podlegać regule ukrywania/pokazywania.
    -   **Efekt zmiany tego ustawienia:** Wszystkie produkty od wybranych producentów zostaną objęte regułą „Co chcesz zrobić?”.
    -   **Zalecana wartość:** Wybierz producentów, których produkty chcesz kontrolować.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz umowę dystrybucyjną, która uniemożliwia sprzedaż produktów „Marki X” w Australii. Wybierzesz tutaj „Markę X”.
-   **Wyklucz grupy klientów (Lista wielokrotnego wyboru)**

    -   **Co robi to ustawienie:** Pozwala wyłączyć niektóre grupy klientów z reguł ukrywania produktów modułu.
    -   **Efekt zmiany tego ustawienia:** Klienci należący do wybranych grup zawsze będą widzieć wszystkie produkty, niezależnie od ich kraju lub ustawień modułu. Jest to przydatne dla partnerów B2B lub VIP-ów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne grupy klientów, które muszą ominąć reguły.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz grupę klientów „Hurtownicy”, którzy zawsze powinni widzieć cały Twój katalog, nawet jeśli niektóre produkty są ograniczone dla zwykłych klientów w ich kraju. Wybierzesz tutaj „Hurtownicy”.
-   **Wyklucz klientów (Pole wyszukiwania)**

    -   **Co robi to ustawienie:** Pozwala wyłączyć poszczególnych klientów z reguł ukrywania produktów modułu.
    -   **Efekt zmiany tego ustawienia:** Wybrani przez Ciebie klienci zawsze będą widzieć wszystkie produkty, niezależnie od ich kraju lub ustawień modułu.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretnych klientów, którzy muszą ominąć reguły.
    -   **Scenariusz / przykład dla sprzedawcy:** Konkretny menedżer klienta kluczowego musi widzieć wszystkie produkty dla klienta, nawet jeśli przegląda z kraju objętego ograniczeniami. Wyszukasz i wybierzesz tego klienta tutaj.

#### Ustawienia geolokalizacji i symulacji

-   **Ustaw priorytet metod identyfikacji pochodzenia (Lista przeciągnij i upuść)**

    -   **Co robi to ustawienie:** Określa kolejność, w jakiej moduł próbuje zidentyfikować kraj klienta. Jest to kluczowe, ponieważ różne metody mogą czasami dawać różne wyniki.
    -   **Efekt zmiany tego ustawienia:** Moduł będzie próbował metod od góry do dołu. Pierwsza udana identyfikacja zostanie użyta.
        -   *Adres dostawy:* Używa kraju z wybranego adresu dostawy klienta (wymaga, aby klient był zalogowany i miał adres).
        -   *Adres IP (Geolokalizacja):* Używa adresu IP klienta do określenia jego kraju (najczęściej dla gości).
        -   *Język przeglądarki:* Wnioskuje kraj z ustawień językowych przeglądarki klienta (mniej wiarygodne dla precyzyjnej identyfikacji kraju).
    -   **Zalecana wartość:**
        1.  Adres dostawy (jeśli adres zalogowanego klienta jest najważniejszy)
        2.  Adres IP (dla ogólnej dokładności dla wszystkich odwiedzających)
        3.  Język przeglądarki (jako rezerwowy, mniej precyzyjny)
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz nadać priorytet rzeczywistemu adresowi dostawy klienta, jeśli jest zalogowany, ponieważ jest to najdokładniejsze dla wysyłki. Dla gości chcesz polegać na geolokalizacji IP. Przeciągnąłbyś „Adres dostawy” na górę, a następnie „Adres IP”.
-   **Użyj adresu dostawy (Przełącznik)**

    -   **Co robi to ustawienie:** Kontroluje, czy moduł uwzględnia kraj wybranego adresu dostawy klienta do filtrowania produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Jeśli klient jest zalogowany i ma wybrany adres dostawy, moduł użyje kraju tego adresu do określenia widoczności produktu.
        -   *Gdy wyłączony:* Moduł zignoruje adres dostawy i będzie polegał na innych metodach (takich jak adres IP) nawet dla zalogowanych klientów.
    -   **Zalecana wartość:** **Włączony** dla zalogowanych klientów, ponieważ adres dostawy jest często najdokładniejszym wskaźnikiem miejsca, do którego produkt ma trafić.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient z USA przegląda z Kanady. Jeśli „Użyj adresu dostawy” jest włączone i mają wybrany adres dostawy w USA, zobaczą produkty dostępne w USA. Jeśli wyłączone, mogą zobaczyć produkty dostępne w Kanadzie (na podstawie ich adresu IP).
-   **Aktywuj białą listę (Przełącznik)**

    -   **Co robi to ustawienie:** To ustawienie działa w połączeniu z wbudowaną funkcją geolokalizacji PrestaShop (znajdującą się w **Parametry sklepu > Ogólne > Geolokalizacja**). Jeśli geolokalizacja PrestaShop jest włączona, ten moduł może używać jej białej listy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Jeśli natywna geolokalizacja PrestaShop jest aktywna i skonfigurowana z białą listą (kraje dozwolone do przeglądania), ten moduł będzie przestrzegał tej białej listy. Odwiedzający z krajów *nie* znajdujących się na białej liście PrestaShop mogą zostać zablokowani lub przekierowani, zanim ten moduł zastosuje swoje reguły.
        -   *Gdy wyłączony:* Ten moduł zignoruje białą listę geolokalizacji PrestaShop i zastosuje swoje reguły na podstawie własnej identyfikacji kraju.
    -   **Zalecana wartość:** **Wyłączony**, chyba że aktywnie używasz i zarządzasz natywną białą listą geolokalizacji PrestaShop.
    -   **Scenariusz / przykład dla sprzedawcy:** Skonfigurowałeś geolokalizację PrestaShop tak, aby zezwalała tylko na odwiedzających z krajów UE. Jeśli włączysz tutaj „Aktywuj białą listę”, odwiedzający spoza UE zostaną obsłużeni przez podstawowy system PrestaShop, a ten moduł zastosuje swoje reguły dotyczące produktów do dozwolonych odwiedzających z UE.
-   **Symuluj wizytę (Przełącznik)**

    -   **Co robi to ustawienie:** Jest to potężne narzędzie testowe, które pozwala udawać, że przeglądasz z innego kraju, bez faktycznej zmiany lokalizacji lub używania VPN.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pole „Symuluj IP” staje się aktywne, umożliwiając wprowadzenie adresu IP. Moduł będzie wtedy traktował Twoją bieżącą sesję przeglądania tak, jakbyś odwiedzał z kraju powiązanego z tym adresem IP.
        -   *Gdy wyłączony:* Moduł normalnie identyfikuje Twój kraj.
    -   **Zalecana wartość:** **Wyłączony** dla sklepów działających na żywo. Włączaj tylko tymczasowo do testowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz sprawdzić, czy produkty są poprawnie ukryte dla klientów w Niemczech. Włączasz „Symuluj wizytę”, wprowadzasz niemiecki adres IP (np. 85.214.132.112), a następnie przeglądasz swój sklep, aby sprawdzić, czy odpowiednie produkty są ukryte.
-   **Symuluj IP (Pole tekstowe)**

    -   **Co robi to ustawienie:** Gdy „Symuluj wizytę” jest włączone, wprowadzasz tutaj adres IP, aby zasymulować odwiedzającego z kraju tego IP.
    -   **Efekt zmiany tego ustawienia:** Twoja bieżąca sesja przeglądania będzie zachowywać się tak, jakbyś znajdował się w kraju powiązanym z wprowadzonym adresem IP, co pozwala testować reguły widoczności produktów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że „Symuluj wizytę” jest włączone do testowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Po włączeniu „Symuluj wizytę” wprowadzasz „192.168.1.1” (powszechny lokalny adres IP, ale użyłbyś prawdziwego publicznego adresu IP dla kraju) do testowania. Dla niemieckiego adresu IP możesz użyć „85.214.132.112”.

#### Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Włączony** | Włączony | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | **Co chcesz zrobić?** | Ukryj produkty dla wybranych krajów | Definiuje, czy produkty są ukrywane dla wybranych krajów, czy tylko im pokazywane. |
| Konfiguracja modułu | **Wybierz kraje** | (Puste) / Wybierz odpowiednie | Kraje objęte regułą widoczności produktów. |
| Konfiguracja modułu | **Wybierz kategorie** | (Puste) / Wybierz odpowiednie | Kategorie, których produkty są objęte. |
| Konfiguracja modułu | **Wybierz producenta** | (Puste) / Wybierz odpowiednie | Producenci, których produkty są objęte. |
| Konfiguracja modułu | **Wyklucz grupy klientów** | (Puste) | Grupy klientów zwolnione z reguł ukrywania. |
| Konfiguracja modułu | **Wyklucz klientów** | (Puste) | Indywidualni klienci zwolnieni z reguł ukrywania. |
| Konfiguracja modułu | **Ustaw priorytet metod identyfikacji pochodzenia** | Adres dostawy, Adres IP, Język przeglądarki | Kolejność metod identyfikacji kraju klienta. |
| Konfiguracja modułu | **Użyj adresu dostawy** | Włączony | Użyj kraju adresu dostawy klienta do filtrowania. |
| Konfiguracja modułu | **Aktywuj białą listę** | Wyłączony | Przestrzegaj natywnej białej listy geolokalizacji PrestaShop. |
| Konfiguracja modułu | **Symuluj wizytę** | Wyłączony | Włącz, aby testować widoczność produktów z określonego adresu IP. |
| Konfiguracja modułu | **Symuluj IP** | (Puste) | Adres IP do symulacji, gdy „Symuluj wizytę” jest włączone. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale produkty nadal są widoczne/ukryte nieprawidłowo. Co powinienem sprawdzić w pierwszej kolejności?**
O:

1.  **Moduł włączony:** Sprawdź dwukrotnie, czy główny przełącznik „Włączony” na stronie konfiguracji modułu jest włączony.
2.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu). Pamięć podręczna przeglądarki również może czasami przeszkadzać, więc spróbuj twardego odświeżenia (Ctrl+F5 lub Cmd+Shift+R) lub okna incognito/prywatnego przeglądania.
3.  **Symulacja:** Jeśli testujesz, upewnij się, że „Symuluj wizytę” jest włączone, a „Symuluj IP” jest ustawione poprawnie. Jeśli nie symulujesz, upewnij się, że „Symuluj wizytę” jest wyłączone.
4.  **Logika reguł:** Przejrzyj ustawienie „Co chcesz zrobić?” („Ukryj produkty dla wybranych krajów” vs. „Pokaż produkty tylko dla wybranych krajów”) i upewnij się, że odpowiada Twoim intencjom.
5.  **Wybór kraju/kategorii/producenta:** Upewnij się, że poprawnie wybrałeś kraje, kategorie i producentów, którzy powinni być objęci.

**P: Jak moduł identyfikuje kraj klienta?**
O: Moduł używa systemu priorytetów, który konfigurujesz:

1.  **Adres dostawy:** Jeśli klient jest zalogowany i ma adres dostawy, jest to najbardziej dokładne.
2.  **Adres IP (Geolokalizacja):** Dla gości lub jeśli nie użyto adresu dostawy, używa adresu IP odwiedzającego do określenia jego kraju.
3.  **Język przeglądarki:** Jako rezerwowy, może wnioskować kraj z ustawień językowych przeglądarki, chociaż jest to mniej precyzyjne. Możesz dostosować priorytet w ustawieniach modułu.

**P: Czy ten moduł wpłynie na moje SEO? Czy Google nadal będzie indeksować moje ukryte produkty?**
O: Moduł ukrywa produkty z widoku front-office dla określonych krajów. Ogólnie rzecz biorąc, roboty wyszukiwarek (takie jak Googlebot) często indeksują z określonych adresów IP (np. adresów IP z USA). Jeśli Twoje produkty są ukryte dla USA, Google może ich nie widzieć. Jeśli są ukryte dla innych krajów, ale widoczne dla USA, Google może je nadal indeksować. W przypadku krytycznych problemów z SEO rozważ użycie natywnej funkcji PrestaShop „Wyłącz produkt” lub specyficznych reguł robots.txt, jeśli absolutnie nie chcesz, aby produkt był indeksowany gdziekolwiek. Ten moduł służy przede wszystkim do poprawy doświadczenia użytkownika na front-endzie i zgodności, a nie do kontroli SEO.

**P: Czy mogę ukryć produkty dla konkretnych klientów lub grup klientów, niezależnie od ich kraju?**
O: Tak! Moduł zawiera ustawienia „Wyklucz grupy klientów” i „Wyklucz klientów”. Pozwalają one określić grupy lub pojedynczych klientów, którzy *zawsze* będą widzieć wszystkie produkty, skutecznie omijając reguły ukrywania oparte na kraju. Jest to przydatne dla VIP-ów, partnerów B2B lub personelu wewnętrznego.

**P: Co się stanie, jeśli klient z kraju objętego ograniczeniami spróbuje uzyskać dostęp do ukrytego produktu za pomocą bezpośredniego linku?**
O: Moduł jest zaprojektowany tak, aby uniemożliwić dostęp. Zazwyczaj zostaną przekierowani na stronę główną lub do błędu „strona nie znaleziona”, co zapewni, że nie będą mogli przeglądać ani dodawać ograniczonego produktu do koszyka.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Ukryj produkty według kraju” (`hbc`) działa głównie poprzez nadpisywanie podstawowych klas PrestaShop i wykorzystywanie hooków do przechwytywania i modyfikowania zapytań o produkty przed ich wyświetleniem klientowi. Wykorzystuje `ObjectModel` PrestaShop do przechowywania konfiguracji i opiera się na geolokalizacji IP lub danych adresowych klienta w celu określenia kraju odwiedzającego. Logika modułu jest wstrzykiwana w proces filtrowania produktów, zapewniając, że ograniczone produkty są usuwane z list, wyników wyszukiwania i prób bezpośredniego dostępu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych dedykowanych kontrolerów Front-Office ani Back-Office Admin. Jego konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł implementuje nadpisywania w celu modyfikacji podstawowego zachowania PrestaShop.

-   **`hbc/override/classes/index.php`**: Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.
-   **`hbc/override/classes/shop/index.php`**: Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.
-   **`hbc/override/classes/shop/Shop.php`**:
    -   **Nazwa klasy**: `Shop` (nadpisuje podstawową klasę `Shop` PrestaShop)
    -   **Klasa nadrzędna**: `ShopCore`
    -   **Odpowiedzialność**: To nadpisanie jest krytyczne. Prawdopodobnie modyfikuje sposób określania kontekstu produktu lub kontekstu sklepu, potencjalnie wstrzykując logikę filtrowania specyficzną dla kraju na bardzo fundamentalnym poziomie systemu PrestaShop do obsługi wielu sklepów i pobierania produktów. Zapewnia to, że reguły widoczności produktów są stosowane konsekwentnie w różnych częściach sklepu. Deweloperzy powinni być świadomi, że nadpisywanie `Shop.php` może mieć szerokie konsekwencje i może kolidować z innymi modułami, które również nadpisują tę podstawową klasę.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`hbc/lib/searchTool/views/js/autocomplete.js`**:
    -   **Zakres**: Panel administracyjny (prawdopodobnie używany w formularzu konfiguracji modułu).
    -   **Cel**: Ten skrypt zapewnia funkcjonalność autouzupełniania, w szczególności dla pola wejściowego „Wyklucz klientów” w konfiguracji modułu. Prawdopodobnie wykonuje wywołania AJAX do punktu końcowego administratora PrestaShop w celu wyszukiwania klientów podczas pisania przez administratora, poprawiając użyteczność wyboru poszczególnych klientów.
    -   **Kluczowa funkcjonalność**:
        -   Inicjalizuje widżet autouzupełniania na określonym polu wejściowym (np. `#hbc_exclude_customer`).
        -   Wysyła żądania AJAX (np. do `admin-ajax.php` lub dedykowanego kontrolera administratora) z wpisanym zapytaniem.
        -   Analizuje odpowiedzi JSON zawierające dane klienta (ID, nazwa, e-mail).
        -   Wyświetla sugestie w liście rozwijanej.
        -   Obsługuje wybór klienta, wypełniając ukryte pole wejściowe identyfikatorem klienta i wyświetlając nazwę.
        -   Zarządza usuwaniem wybranych klientów z listy.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`hbc/lib/searchTool/views/css/autocomplete.css`**:
    -   **Zakres**: Panel administracyjny (stylizuje widżet autouzupełniania).
    -   **Cel**: Zapewnia stylizację narzędzia wyszukiwania autouzupełniania klientów używanego w konfiguracji modułu. Obejmuje to stylizację pola wejściowego, listy rozwijanej sugestii i potencjalnie wyświetlania wybranych tagów/tokenów.
    -   **Kluczowe selektory**: Prawdopodobnie celuje w klasy i identyfikatory związane z widżetem autouzupełniania, takie jak `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item` oraz elementy do wyświetlania wybranych tagów/tokenów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`hbc/lib/searchTool/views/scripts.tpl`**:

    -   **Zakres**: Panel administracyjny.
    -   **Cel**: Ten szablon prawdopodobnie zawiera niezbędne pliki JavaScript i CSS dla narzędzia wyszukiwania autouzupełniania (`autocomplete.js` i `autocomplete.css`) i potencjalnie inicjalizuje logikę JavaScript. Prawdopodobnie jest on dołączony do głównego szablonu konfiguracji.
-   **`hbc/views/templates/admin/AdminTab.tpl`**:

    -   **Zakres**: Panel administracyjny.
    -   **Cel**: Ten szablon jest prawdopodobnie ogólnym wrapperem lub komponentem używanym na stronie konfiguracji modułu. Może definiować strukturę interfejsu z zakładkami lub konkretnej sekcji w ustawieniach modułu.
-   **`hbc/views/templates/admin/button-subcategories.tpl`**:

    -   **Zakres**: Panel administracyjny.
    -   **Cel**: Ten szablon prawdopodobnie renderuje przycisk lub element interfejsu użytkownika związany z wyborem kategorii, w szczególności do włączania/wyłączania podkategorii podczas wybierania kategorii nadrzędnych w formularzu konfiguracji.
-   **`hbc/views/templates/admin/configuration.tpl`**:

    -   **Zakres**: Panel administracyjny.
    -   **Cel**: Jest to główny szablon Smarty dla strony konfiguracji modułu. Renderuje wszystkie ustawienia, pola wejściowe, przełączniki i listy opisane w sekcji 4.1. Wykorzystuje komponenty formularzy pomocniczych PrestaShop i prawdopodobnie zawiera `scripts.tpl` dla funkcjonalności autouzupełniania.
-   **`hbc/views/templates/hook/displayHeader.tpl`**:

    -   **Zakres**: Front-office.
    -   **Hook**: `displayHeader`
    -   **Cel**: Ten szablon jest renderowany w sekcji `<head>` każdej strony front-office. Może być używany do:
        -   Wstrzykiwania wbudowanego kodu JavaScript do wykrywania kraju po stronie klienta (mniej prawdopodobne, biorąc pod uwagę filtrowanie po stronie serwera).
        -   Ustawiania zmiennych JavaScript na podstawie konfiguracji modułu (np. tryb symulacji).
        -   Dołączania dodatkowych plików CSS lub JS, które są potrzebne globalnie do funkcjonalności front-office modułu (chociaż podstawowe filtrowanie odbywa się po stronie serwera).
        -   Potencjalnie obsługi przekierowań lub wstępnych sprawdzeń na podstawie geolokalizacji przed pełnym załadowaniem strony.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł używa głównie tabeli `ps_configuration` PrestaShop do przechowywania swoich ustawień.
    -   Klucze konfiguracji obejmują: `HBC_EXCLUDE_GROUP`, `HBC_EXCLUDE_CUSTOMER`, `HBC_SIMULATE_ON`, `HBC_SIMULATE_IP`, `HBC_DELIVERY`, `HBC_WHITELIST_ON`, `HBC_COUNTRY`, `HBC_WTD`, `HBC_MANUFACT`, `HBC_CATEGORIES`, `HBC_PRIORITY`.
    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | W sekcji `<head>` każdej strony. | Potencjalnie do wstrzykiwania skryptów po stronie klienta, meta tagów lub wstępnych sprawdzeń. |
| `actionAdminControllerSetMedia` | Panel administracyjny | Gdy kontroler administratora ustawia swoje zasoby multimedialne. | Służy do ładowania CSS/JS dla strony konfiguracji modułu (np. `autocomplete.js`, `autocomplete.css`). |
| `actionDispatcherAfter` | Front-office | Po przetworzeniu żądania przez dispatcher. | Może być używany do wykonywania przekierowań lub końcowych sprawdzeń po zidentyfikowaniu strony, ale przed renderowaniem. |
| `displayFilterProductSearch` | Front-office | Podczas filtrowania wyszukiwania produktów. | **KRYTYCZNE**: Ten hook służy do wstrzykiwania logiki modułu do zapytania wyszukiwania produktów, zapewniając wykluczenie ukrytych produktów z wyników wyszukiwania. |
| `actionProductUpdate` | Panel administracyjny | Po zaktualizowaniu produktu w Panelu administracyjnym. | Może być używany do czyszczenia pamięci podręcznej związanej z widocznością produktu lub ponownej oceny reguł dla zaktualizowanego produktu. |
| `displayAdminProductsExtra` | Panel administracyjny | Na stronie edycji produktu w Panelu administracyjnym. | Może być używany do wyświetlania dodatkowych informacji lub ustawień związanych z ukrywaniem produktu dla edytowanego produktu (chociaż nie jest to wyraźnie zidentyfikowane w ustawieniach). |
| `actionCartSave` | Front-office | Gdy koszyk jest zapisywany (np. produkt dodany/usunięty). | Może być używany do zapobiegania dodawaniu ukrytych produktów do koszyka lub do ich usuwania, jeśli kraj klienta się zmieni. |
| `FilterProductSearch` | Front-office | Podczas filtrowania wyszukiwania produktów (podobnie jak `displayFilterProductSearch`). | **KRYTYCZNE**: Kolejny hook do modyfikowania zapytań wyszukiwania produktów, zapewniający kompleksowe filtrowanie w różnych kontekstach wyszukiwania. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Ukryj produkty według kraju”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
