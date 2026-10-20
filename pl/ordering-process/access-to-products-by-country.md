---
title: "Dostęp do produktów według kraju - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Dostęp do produktów według kraju” od MyPresta.eu."
sidebar:
  label: "Dostęp do produktów według kraju - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Access to products by country na MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products-by-country.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/access-to-products-by-country/)
>
> ---


# Dostęp do produktów według kraju

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Dostęp do produktów według kraju”. Znajdziesz tu wszystkie ustawienia, aby zdefiniować, w jaki sposób dostęp do produktów jest ograniczany.

#### Ustawienia ogólne

-   **Włączony / Wyłączony (Status modułu)**

    -   **Co robi to ustawienie:** Jest to główny przełącznik modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł będzie aktywnie filtrować produkty na podstawie ograniczeń krajowych.
        -   *Gdy wyłączony:* Moduł będzie nieaktywny, a wszystkie produkty będą widoczne dla wszystkich klientów, niezależnie od ich kraju.
    -   **Zalecana wartość:** **Włączony** po skonfigurowaniu reguł.
    -   **Scenariusz / przykład dla sprzedawcy:** Konfigurujesz moduł po raz pierwszy; pozostaw go wyłączonym, dopóki nie zdefiniujesz wszystkich reguł, a następnie włącz go, aby uruchomić.
-   **Co chcesz zrobić? (Typ ograniczenia)**

    -   **Co robi to ustawienie:** Definiuje podstawową logikę ograniczeń krajowych: czy chcesz *blokować* produkty w wybranych krajach, czy *zezwalać* na produkty *tylko* w wybranych krajach?
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Blokuj dostęp do produktów w wybranych krajach”:* Skonfigurowane produkty będą ukryte przed klientami w określonych krajach. Będą widoczne wszędzie indziej.
        -   *Gdy ustawione na „Zezwalaj na dostęp do produktów TYLKO w wybranych krajach”:* Skonfigurowane produkty będą widoczne *tylko* dla klientów w określonych krajach. Będą ukryte wszędzie indziej.
    -   **Zalecana wartość:** Wybierz na podstawie swojego głównego przypadku użycia. Jeśli masz kilka krajów, w których produkt jest ograniczony, wybierz „Blokuj”. Jeśli produkt jest dostępny wyłącznie w kilku krajach, wybierz „Zezwalaj TYLKO”.
    -   **Scenariusz / przykład dla sprzedawcy:**
        -   *Blokuj:* Sprzedajesz konkretną markę, której nie można wysyłać do Kanady. Wybierzesz „Blokuj dostęp”, a następnie wybierzesz Kanadę dla tego produktu.
        -   *Zezwalaj TYLKO:* Masz produkt z edycji specjalnej dostępny tylko w USA i Meksyku. Wybierzesz „Zezwalaj na dostęp TYLKO”, a następnie wybierzesz USA i Meksyk dla tego produktu.
-   **Wybierz kraje**

    -   **Co robi to ustawienie:** Tutaj wybierasz konkretne kraje, które zostaną objęte regułą „Co chcesz zrobić?”.
    -   **Efekt zmiany tego ustawienia:** Wybrane kraje będą albo zablokowane przed widzeniem produktu, albo będą jedynymi, którym wolno go zobaczyć, w zależności od ustawienia „Co chcesz zrobić?”.
    -   **Zalecana wartość:** Wybierz wszystkie odpowiednie kraje na podstawie ograniczeń produktowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli blokujesz sprzedaż do Kanady i Australii, wybierzesz zarówno Kanadę, jak i Australię z listy.
-   **Wybierz kategorie**

    -   **Co robi to ustawienie:** Pozwala zastosować reguły ograniczeń krajowych do całych kategorii produktów zamiast do pojedynczych produktów.
    -   **Efekt zmiany tego ustawienia:** Wszystkie produkty w wybranych kategoriach odziedziczą reguły ograniczeń krajowych zdefiniowane powyżej.
    -   **Zalecana wartość:** Użyj tego dla szerokich ograniczeń. Pozostaw puste, jeśli chcesz zarządzać ograniczeniami produkt po produkcie.
    -   **Scenariusz / przykład dla sprzedawcy:** Wszystkie produkty w Twojej kategorii „Elektronika” nie mogą być sprzedawane w Brazylii. Wybierzesz tutaj kategorię „Elektronika”.
-   **Wybierz producenta**

    -   **Co robi to ustawienie:** Pozwala zastosować reguły ograniczeń krajowych do wszystkich produktów od konkretnych producentów.
    -   **Efekt zmiany tego ustawienia:** Wszystkie produkty od wybranych producentów odziedziczą reguły ograniczeń krajowych.
    -   **Zalecana wartość:** Użyj tego dla ograniczeń na poziomie marki. Pozostaw puste, jeśli chcesz zarządzać ograniczeniami produkt po produkcie lub kategoria po kategorii.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz umowę dystrybucyjną, która uniemożliwia sprzedaż produktów „Marki X” w Europie. Wybierzesz tutaj „Markę X”.

#### Wykluczenia klientów i grup

-   **Wyklucz grupy klientów**

    -   **Co robi to ustawienie:** Pozwala wyłączyć niektóre grupy klientów z ograniczeń krajowych. Na przykład, możesz mieć specjalną grupę B2B, która może kupować produkty objęte ograniczeniami.
    -   **Efekt zmiany tego ustawienia:** Klienci należący do wybranych grup *nie* będą podlegać ograniczeniom krajowym zdefiniowanym przez ten moduł. Będą widzieć wszystkie produkty.
    -   **Zalecana wartość:** Wybierz grupy, które potrzebują specjalnego dostępu, takie jak „Klienci hurtowi” lub „Pracownicy”. Pozostaw puste, jeśli wszyscy klienci powinni podlegać ograniczeniom.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz grupę „Klientów VIP”, którzy mogą kupować produkty, które w innym przypadku są ograniczone w ich kraju. Wybierzesz tutaj grupę „Klientów VIP”.
-   **Wyklucz klientów**

    -   **Co robi to ustawienie:** Pozwala wyłączyć konkretnych pojedynczych klientów z ograniczeń krajowych.
    -   **Efekt zmiany tego ustawienia:** Wybrani pojedynczy klienci *nie* będą podlegać ograniczeniom krajowym. Będą widzieć wszystkie produkty.
    -   **Zalecana wartość:** Użyj tego dla konkretnych wyjątków. Pozostaw puste, jeśli nie jest potrzebne.
    -   **Scenariusz / przykład dla sprzedawcy:** Konkretny klient jest długoterminowym partnerem i potrzebuje dostępu do wszystkich produktów niezależnie od jego lokalizacji. Wybierzesz tutaj jego konto klienta.

#### Ustawienia geolokalizacji i symulacji

-   **Ustaw priorytet metod identyfikacji pochodzenia**

    -   **Co robi to ustawienie:** Określa kolejność, w jakiej moduł próbuje zidentyfikować kraj klienta. Jest to kluczowe dla dokładności.
    -   **Efekt zmiany tego ustawienia:** Moduł najpierw spróbuje metody na górze listy. Jeśli to się nie powiedzie lub nie jest dostępne, przechodzi do następnej.
    -   **Zalecana wartość:**
        1.  **Adres dostawy (jeśli dostępny):** Jest to najbardziej dokładne dla rzeczywistej intencji zakupu.
        2.  **Geolokalizacja:** Dobra do początkowego przeglądania.
        3.  **Kraj konta klienta:** Jeśli zalogowany.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient przegląda z USA (geolokalizacja), ale zamierza wysłać do Kanady. Jeśli „Adres dostawy” ma priorytet, moduł użyje Kanady do ograniczeń, gdy klient wprowadzi go do koszyka.
-   **Użyj adresu dostawy**

    -   **Co robi to ustawienie:** Gdy włączone, moduł będzie brał pod uwagę wybrany kraj adresu dostawy klienta w koszyku jako jego „pochodzenie” do stosowania ograniczeń.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli klient doda ograniczony produkt do koszyka, a następnie wybierze adres dostawy w zablokowanym kraju, moduł uniemożliwi realizację zamówienia lub usunie produkt.
        -   *Gdy wyłączone:* Moduł będzie polegał wyłącznie na geolokalizacji IP lub zarejestrowanym kraju klienta, co może nie odpowiadać zamierzonemu miejscu wysyłki.
    -   **Zalecana wartość:** **TAK**. Zapewnia to najbardziej dokładne i praktyczne egzekwowanie ograniczeń podczas procesu realizacji zamówienia.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient z Niemiec (gdzie produkt jest dozwolony) dodaje go do koszyka, ale następnie wybiera adres wysyłki w Austrii (gdzie produkt jest zablokowany). Przy włączonym tym ustawieniu moduł uniemożliwi zamówienie.
-   **Symuluj wizytę**

    -   **Co robi to ustawienie:** Pozwala przetestować ograniczenia krajowe, symulując wizytę z określonego kraju bez faktycznej zmiany adresu IP.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie traktował Twoją bieżącą sesję tak, jakbyś przeglądał z kraju określonego w „Symuluj IP”.
        -   *Gdy wyłączone:* Moduł używa Twojego rzeczywistego adresu IP do geolokalizacji.
    -   **Zalecana wartość:** **Wyłączone** dla sklepów działających. **Włączone** tylko do testowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz sprawdzić, czy produkt jest poprawnie ukryty dla klientów we Francji. Włączasz „Symuluj wizytę”, wprowadzasz francuski adres IP (lub wybierasz Francję, jeśli jest dostępna), a następnie przeglądasz swój sklep.
-   **Symuluj IP**

    -   **Co robi to ustawienie:** Gdy „Symuluj wizytę” jest włączone, to pole pozwala wprowadzić adres IP z kraju, który chcesz symulować, lub wybrać kraj z listy rozwijanej.
    -   **Efekt zmiany tego ustawienia:** Moduł użyje tego IP/kraju do wszystkich kontroli ograniczeń podczas Twojej symulowanej sesji.
    -   **Zalecana wartość:** Wprowadź prawidłowy adres IP lub wybierz kraj do celów testowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zasymulować wizytę z Niemiec, możesz wprowadzić `88.130.179.0` (niemiecki IP) lub po prostu wybrać „Niemcy” z listy.

#### Ustawienia białej listy

-   **Aktywuj białą listę**

    -   **Co robi to ustawienie:** To ustawienie wykorzystuje wbudowaną funkcję białej listy geolokalizacji PrestaShop. Jeśli geolokalizacja PrestaShop jest aktywna, ta biała lista pozwala zdefiniować konkretne adresy IP lub zakresy IP, które *zawsze* powinny mieć dostęp do Twojego sklepu, niezależnie od wykrytego kraju. Jest to przydatne dla adresów IP Twojego biura lub zaufanych partnerów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie respektował białą listę geolokalizacji PrestaShop. Adresy IP z tej listy ominą wszelkie ograniczenia krajowe.
        -   *Gdy wyłączone:* Biała lista nie będzie brana pod uwagę.
    -   **Zalecana wartość:** **TAK**, jeśli używasz geolokalizacji PrestaShop i masz adresy IP, które chcesz umieścić na białej liście.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoje biuro znajduje się w kraju, gdzie niektóre produkty są ograniczone, ale potrzebujesz do nich dostępu w celach administracyjnych. Dodasz adres IP swojego biura do białej listy geolokalizacji PrestaShop i włączysz to ustawienie.
-   **Biała lista**

    -   **Co robi to ustawienie:** Tutaj zarządzasz konkretnymi adresami IP lub zakresami IP, które są na białej liście. Odpowiada to bezpośrednio ustawieniu PrestaShop `PS_GEOLOCATION_WHITELIST`.
    -   **Efekt zmiany tego ustawienia:** Każdy adres IP lub zakres wprowadzony tutaj ominie wszystkie ograniczenia oparte na geolokalizacji.
    -   **Zalecana wartość:** Dodaj adresy IP swojego biura, adresy IP serwerów deweloperskich lub inne zaufane adresy IP, które zawsze powinny mieć pełny dostęp.
    -   **Scenariusz / przykład dla sprzedawcy:** Dodajesz `192.168.1.1/24` (sieć Twojego biura), aby zapewnić wszystkim pracownikom dostęp do wszystkich produktów.

#### Ustawienia aktualizacji (wewnętrzne)

-   **mypresta\_updates, update\_, updatev\_**
    -   **Co robią te ustawienia:** Są to wewnętrzne ustawienia używane przez moduły MyPresta.eu do zarządzania aktualizacjami i sprawdzaniem wersji. Nie są przeznaczone do bezpośredniej interakcji sprzedawcy.
    -   **Efekt zmiany tego ustawienia:** Modyfikacja tych ustawień może zakłócić powiadomienia o aktualizacjach modułu.
    -   **Zalecana wartość:** Pozostaw te ustawienia bez zmian.
    -   **Scenariusz / przykład dla sprzedawcy:** Brak scenariusza dla sprzedawcy; są to ustawienia do wewnętrznego zarządzania modułem.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Włączony / Wyłączony** | Włączony | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | **Co chcesz zrobić?** | Blokuj dostęp | Definiuje, czy reguły blokują dostęp, czy zezwalają na dostęp TYLKO. |
| Konfiguracja modułu | **Wybierz kraje** | (Brak) | Kraje objęte regułą ograniczenia. |
| Konfiguracja modułu | **Wybierz kategorie** | (Brak) | Kategorie, których produkty są objęte regułą. |
| Konfiguracja modułu | **Wybierz producenta** | (Brak) | Producenci, których produkty są objęte regułą. |
| Konfiguracja modułu | **Wyklucz grupy klientów** | (Brak) | Grupy klientów zwolnione z ograniczeń. |
| Konfiguracja modułu | **Wyklucz klientów** | (Brak) | Indywidualni klienci zwolnieni z ograniczeń. |
| Konfiguracja modułu | **Ustaw priorytet metod identyfikacji pochodzenia** | Adres dostawy, Geolokalizacja, Kraj konta klienta | Kolejność metod określania kraju klienta. |
| Konfiguracja modułu | **Użyj adresu dostawy** | TAK | Uwzględnia adres dostawy do egzekwowania ograniczeń. |
| Konfiguracja modułu | **Symuluj wizytę** | Wyłączone | Włącza/wyłącza symulację IP do testowania. |
| Konfiguracja modułu | **Symuluj IP** | (Puste) | Adres IP/kraj do symulacji w celach testowych. |
| Konfiguracja modułu | **Aktywuj białą listę** | TAK | Włącza/wyłącza białą listę geolokalizacji PrestaShop. |
| Konfiguracja modułu | **Biała lista** | (Puste) | Lista adresów IP/zakresów do omijania ograniczeń. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Produkty są nadal widoczne w zablokowanym kraju, co powinienem zrobić?**
O1: Najpierw sprawdź konfigurację modułu:
\* Czy moduł jest „Włączony”?
\* Czy „Co chcesz zrobić?” jest ustawione poprawnie (np. „Blokuj dostęp”, jeśli chcesz je ukryć)?
\* Czy wybrano poprawne „Wybierz kraje”?
\* Czy „Wybierz kategorie” lub „Wybierz producenta” są poprawnie zastosowane do danych produktów?
\* Jeśli testujesz, upewnij się, że „Symuluj wizytę” jest włączone, a „Symuluj IP” jest ustawione na właściwy kraj.
\* Na koniec wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) i pamięć podręczną przeglądarki.

**P2: Mój własny adres IP wydaje się być zablokowany, mimo że jestem w dozwolonym kraju.**
O2: Może się to zdarzyć, jeśli Twój adres IP został w jakiś sposób błędnie zidentyfikowany lub jeśli popełniłeś błąd w konfiguracji.
\* Sprawdź ustawienie „Biała lista” i upewnij się, że adres IP Twojego biura lub osobisty adres IP został tam dodany, jeśli chcesz ominąć wszystkie ograniczenia.
\* Zweryfikuj swój rzeczywisty publiczny adres IP (możesz użyć stron internetowych takich jak „jaki jest mój IP”).
\* Upewnij się, że „Aktywuj białą listę” jest włączone, jeśli używasz wbudowanej białej listy geolokalizacji PrestaShop.

**P3: Jak moduł określa kraj klienta?**
O3: Moduł używa systemu priorytetów:
1.  **Adres dostawy:** Jeśli „Użyj adresu dostawy” jest włączone, a klient wprowadził adres wysyłki do koszyka, ma to priorytet.
2.  **Geolokalizacja:** Używa adresu IP klienta do określenia jego położenia geograficznego.
3.  **Kraj konta klienta:** Jeśli klient jest zalogowany, używa kraju zarejestrowanego na jego koncie.
Możesz dostosować priorytet tych metod w konfiguracji modułu.

**P4: Mam niestandardowy szablon, czy ten moduł będzie działać?**
O4: Tak, moduł jest zaprojektowany do pracy ze standardowymi szablonami PrestaShop. Głównie filtruje produkty na poziomie danych, zanim zostaną one wyrenderowane przez szablon. Jednakże, jeśli Twój niestandardowy szablon ma bardzo nietypową logikę listowania produktów lub nadpisuje podstawowe hooki wyświetlania produktów PrestaShop, mogą być potrzebne drobne korekty. Jeśli napotkasz problemy, skontaktuj się z pomocą techniczną MyPresta.eu.

**P5: Czy mogę ograniczyć dostęp do konkretnych produktów, a nie tylko kategorii lub producentów?**
O5: Tak, moduł działa poprzez filtrowanie produktów. Chociaż główny ekran konfiguracji pozwala wybierać kategorie i producentów, podstawowa logika modułu dotyczy poszczególnych produktów. Możesz pozostawić „Wybierz kategorie” i „Wybierz producenta” puste i zarządzać ograniczeniami bezpośrednio na stronach poszczególnych produktów (jeśli moduł dodaje tam zakładkę, co jest typowe dla takich modułów). *Na podstawie dostarczonych informacji, moduł działa poprzez konfigurowanie reguł, które mają zastosowanie do produktów na podstawie kategorii/producentów wybranych w głównej konfiguracji. Nie ma wyraźnej wzmianki o zakładce konfiguracji na poziomie produktu, ale opis sugeruje „każdy produkt indywidualnie”. Jeśli nie ma zakładki produktu, wybór kategorii/producenta jest głównym sposobem na targetowanie produktów.*

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Dostęp do produktów według kraju” (`atpbc`) jest zbudowany jako standardowy moduł PrestaShop, wykorzystujący wzorzec MVC tam, gdzie jest to stosowne. Jego główną funkcją jest przechwytywanie zapytań o produkty i filtrowanie wyników na podstawie skonfigurowanych ograniczeń krajowych i zidentyfikowanej lokalizacji klienta. Integruje się z rdzeniem PrestaShop poprzez podłączanie się do różnych punktów wyświetlania i akcji, w szczególności tych związanych z pobieraniem i wyświetlaniem produktów. Geolokalizacja jest kluczowym komponentem, określającym pochodzenie klienta, które jest następnie krzyżowo sprawdzane z regułami modułu.

### 4.2 Kontrolery (`controllers/`)

Moduł nie wydaje się mieć niestandardowych kontrolerów front-office ani back-office w swoim katalogu `controllers/` na podstawie dostarczonego spisu. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)

Moduł nie wydaje się mieć niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Podstawowa logika i obsługa danych są prawdopodobnie hermetyzowane w głównym pliku `atpbc.php`, używając `Configuration` do ustawień i bezpośrednich zapytań do bazy danych lub klas `Product` i `Category` PrestaShop do manipulacji danymi.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`atpbc/lib/searchTool/views/js/autocomplete.js`**
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Ten skrypt prawdopodobnie zapewnia funkcjonalność autouzupełniania dla pól wejściowych w konfiguracji modułu, takich jak wybieranie klientów, kategorii lub producentów. Poprawia doświadczenie użytkownika, sugerując opcje podczas wpisywania przez administratora, zmniejszając błędy i przyspieszając konfigurację.
    -   **Funkcjonalność:** Wiąże słuchaczy zdarzeń z określonymi polami wejściowymi (np. `keyup`, `focus`), wysyła żądania AJAX do punktu końcowego panelu administracyjnego (prawdopodobnie obsługiwanego przez główny plik modułu lub podstawowy kontroler administratora PrestaShop) w celu pobrania sugestii i wyświetla te sugestie w rozwijanej liście. Obsługuje wybór i wypełnianie pola wejściowego.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`atpbc/lib/searchTool/views/css/autocomplete.css`**
    -   **Zakres:** Stylizacja formularza administracyjnego panelu administracyjnego.
    -   **Cel:** Zapewnia stylizację dla rozwijanej listy sugestii autouzupełniania i potencjalnie samych pól wejściowych, zapewniając spójny i przyjazny dla użytkownika wygląd w panelu administracyjnym PrestaShop.
    -   **Kluczowe selektory:** Prawdopodobnie celuje w klasy takie jak `.autocomplete-suggestions`, `.autocomplete-suggestion-item`, `.autocomplete-input`, aby kontrolować układ, kolory, czcionki i stany najechania myszą. Programiści mogą je nadpisać w swoim niestandardowym szablonie administracyjnym lub dodając CSS o wyższej specyficzności.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`atpbc/lib/searchTool/views/scripts.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Ten szablon jest prawdopodobnie używany do dołączania skryptu `autocomplete.js` i potencjalnie innych konfiguracji związanych z JavaScriptem lub skryptów inline dla funkcjonalności `searchTool`. Może również definiować zmienne przekazywane do JavaScriptu.
    -   **Renderowany w:** Prawdopodobnie podłączony do `actionAdminControllerSetMedia` lub bezpośrednio dołączony do głównego szablonu konfiguracji.
-   **`atpbc/views/templates/admin/AdminTab.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Ten szablon jest prawdopodobnie ogólnym szablonem dla niestandardowej zakładki administracyjnej lub sekcji w konfiguracji modułu. Może zawierać strukturę do wyświetlania list, formularzy lub innej zawartości administracyjnej.
    -   **Renderowany w:** Może być dołączony przez `configuration.tpl` lub używany, jeśli moduł miał dedykowany kontroler administracyjny.
-   **`atpbc/views/templates/admin/button-subcategories.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Ten szablon prawdopodobnie renderuje przycisk lub element interfejsu użytkownika specjalnie do zarządzania podkategoriami w konfiguracji modułu, być może dla ustawienia „Wybierz kategorie” w celu rozwijania/zwijania drzew kategorii.
    -   **Renderowany w:** W `configuration.tpl` podczas wyświetlania opcji wyboru kategorii.
-   **`atpbc/views/templates/admin/configuration.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Jest to główny szablon Smarty dla strony konfiguracji modułu, renderowany przez metodę `getContent()` w `atpbc.php`. Zawiera wszystkie formularze HTML, pola wejściowe, przełączniki i listy wyboru dla ustawień modułu.
    -   **Renderowany w:** Podczas uzyskiwania dostępu do strony konfiguracji modułu w Panelu administracyjnym PrestaShop.
-   **`atpbc/views/templates/hook/displayHeader.tpl`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten szablon jest podłączony do `displayHeader`. Jest zazwyczaj używany do dołączania CSS, JavaScriptu lub metatagów front-office, które muszą być załadowane wcześnie na stronie. Dla tego modułu może zawierać logikę do wykrywania kraju klienta lub ustawiania zmiennych po stronie klienta do późniejszego użycia.
    -   **Renderowany w:** Sekcja `<head>` każdej strony front-office.
-   **`atpbc/views/templates/hook/displayHeaderNoAccess.tpl`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten szablon jest prawdopodobnie rezerwowym lub specyficznym wyświetlaniem, gdy klientowi wykryto „brak dostępu” do określonego produktu lub strony. Może zawierać skrypt przekierowania, wiadomość lub specyficzną stylizację do ukrycia treści.
    -   **Renderowany w:** Potencjalnie w `displayHeader` lub innym hooku, warunkowo od ograniczeń dostępu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł używa głównie tabeli `ps_configuration` PrestaShop do przechowywania swoich ustawień (np. `atpbc_EXCLUDE_GROUP`, `atpbc_EXCLUDE_CUSTOMER`, `atpbc_COUNTRY`, `atpbc_WTD`, `atpbc_MANUFACT`, `atpbc_CATEGORIES`, `atpbc_PRIORITY`, `atpbc_SIMULATE_ON`, `atpbc_SIMULATE_IP`, `atpbc_DELIVERY`, `atpbc_WHITELIST_ON`).
    -   Nie wydaje się tworzyć niestandardowych tabel SQL na podstawie dostarczonego spisu.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Przed renderowaniem zawartości kontrolera administracyjnego, po ustawieniu mediów. | Do dołączania JS/CSS panelu administracyjnego (np. `autocomplete.js`, `autocomplete.css`) dla strony konfiguracji modułu. |
| `actionDispatcherAfter` | Po przetworzeniu żądania przez dispatcher. | Potencjalnie używane do wykonywania przekierowań lub modyfikowania odpowiedzi na podstawie reguł dostępu po zidentyfikowaniu strony. |
| `displayFilterProductSearch` | Podczas filtrowania wyszukiwania produktów. | Do modyfikowania wyników wyszukiwania produktów, usuwając produkty objęte ograniczeniami krajowymi. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Potencjalnie do czyszczenia pamięci podręcznej związanej z dostępnością produktu lub ponownej oceny reguł dla zaktualizowanego produktu. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Do dodawania dodatkowych pól lub zakładki dla reguł dostępu specyficznych dla produktu (chociaż nie jest to wyraźnie stwierdzone, jest to powszechne zastosowanie tego hooka). |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka. | Do sprawdzania, czy produkty w koszyku są dozwolone dla zidentyfikowanego kraju klienta (zwłaszcza jeśli „Użyj adresu dostawy” jest włączone). |
| `FilterProductSearch` | Podczas filtrowania wyszukiwania produktów (podobnie do `displayFilterProductSearch`, często do bezpośredniej manipulacji zapytaniem). | Do modyfikowania zapytania do bazy danych dla wyszukiwania produktów, zapewniając, że produkty objęte ograniczeniami nie są pobierane. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Do dołączania JavaScriptu/CSS front-office (np. `displayHeader.tpl`, `displayHeaderNoAccess.tpl`) lub wykonywania wczesnego wykrywania kraju. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i profesjonalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnego funkcjonowania Twojego modułu i zapewnienie najlepszego możliwego doświadczenia dla Twojego sklepu.
