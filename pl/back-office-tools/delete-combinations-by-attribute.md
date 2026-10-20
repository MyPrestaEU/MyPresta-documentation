---
title: "Usuwanie kombinacji według atrybutu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Usuwanie kombinacji według atrybutu” od MyPresta.eu."
sidebar:
  label: "Usuwanie kombinacji według atrybutu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Delete combinations by attribute na MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-combinations-by-attribute.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/delete-combinations-by-attribute/)
>
> ---


# Usuwanie kombinacji według atrybutu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Usuwanie kombinacji według atrybutu”. Znajdziesz tu wszystkie narzędzia do wybierania i usuwania kombinacji.

#### **Górna sekcja: Aktualizacje modułu i informacje**

Ta sekcja zazwyczaj wyświetla informacje o aktualizacjach modułu i wersjach z MyPresta.eu.

-   **Co robi to ustawienie:** Dostarcza informacji o dostępnych aktualizacjach modułu, zapewniając, że używasz najnowszej wersji z poprawkami błędów i nowymi funkcjami.
-   **Wpływ zmiany tego ustawienia:** Są to pola informacyjne i nie mają bezpośrednich ustawień, które można zmienić. Po prostu wyświetlają dane.
-   **Zalecana wartość:** Utrzymuj moduł zaktualizowany do najnowszej wersji.
-   **Scenariusz / przykład dla sprzedawcy:** Widzisz powiadomienie, że dostępna jest nowa wersja `1.3.1`. Następnie pobierasz ją z MyPresta.eu i aktualizujesz moduł.

#### **Główne opcje konfiguracji**

1.  **Wartość atrybutu**

    -   **Co robi to ustawienie:** Jest to główny filtr. Pozwala wybrać konkretną wartość atrybutu (np. „Czerwony”, „Mały”, „Bawełna”), którą chcesz usunąć. Moduł wyszuka wszystkie kombinacje produktów, które zawierają tę wybraną wartość atrybutu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy wartość jest wybrana:* Moduł zidentyfikuje wszystkie kombinacje w Twoim sklepie, które używają tej konkretnej wartości atrybutu.
        -   *Gdy żadna wartość nie jest wybrana:* Nie możesz kontynuować procesu usuwania, ponieważ moduł nie wie, które kombinacje mają być celem.
    -   **Zalecana wartość:** Wybierz dokładną wartość atrybutu, dla której chcesz usunąć kombinacje.
    -   **Scenariusz / przykład dla sprzedawcy:** Wycofałeś wszystkie produkty w kolorze „Pomarańczowym”. Wybierzesz „Pomarańczowy” z tej listy rozwijanej, aby usunąć wszystkie kombinacje, które mają „Pomarańczowy” jako jeden z atrybutów.
2.  **Ilość**

    -   **Co robi to ustawienie:** Pozwala filtrować kombinacje na podstawie ich aktualnej ilości w magazynie. Możesz wybrać usunięcie kombinacji tylko wtedy, gdy ich ilość jest poniżej, równa lub powyżej określonej liczby.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy „Co zrobić” jest ustawione na „mniej niż” i „Ilość” wynosi 5:* Tylko kombinacje z ilością w magazynie 4 lub mniej zostaną uwzględnione do usunięcia.
        -   *Gdy „Co zrobić” jest ustawione na „równe” i „Ilość” wynosi 0:* Tylko kombinacje z dokładnie 0 sztukami w magazynie zostaną uwzględnione.
    -   **Zalecana wartość:** Często używane z „równe” i „0” do czyszczenia kombinacji niedostępnych w magazynie.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz usunąć wszystkie kombinacje produktów „Pomarańczowych”, które są obecnie niedostępne w magazynie. Wybierzesz „Pomarańczowy” w „Wartość atrybutu”, a następnie ustawisz „Co zrobić” na „równe” i „Ilość” na „0”.
3.  **Co zrobić (z ilością)**

    -   **Co robi to ustawienie:** Ta lista rozwijana działa w połączeniu z polem „Ilość”, aby zdefiniować warunek filtrowania zapasów. Opcje zazwyczaj obejmują „mniej niż”, „równe”, „więcej niż”.
    -   **Wpływ zmiany tego ustawienia:** Modyfikuje logikę porównania dla filtra „Ilość”.
    -   **Zalecana wartość:** „równe” jest często używane do celowania w produkty niedostępne w magazynie.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby usunąć kombinacje, które mają bardzo niski stan magazynowy, możesz wybrać „mniej niż” i ustawić „Ilość” na „3”.
4.  **Lista kodów referencyjnych**

    -   **Co robi to ustawienie:** To pole pozwala określić listę kodów referencyjnych produktów (SKU) do włączenia lub wykluczenia z procesu usuwania. Jest to przydatne, jeśli chcesz wpłynąć tylko na podzbiór produktów.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy „Pole kodu” to „Referencja” i „Co zrobić” to „uwzględnij”:* Tylko kombinacje należące do produktów z tymi konkretnymi kodami referencyjnymi zostaną zmienione.
        -   *Gdy „Pole kodu” to „Referencja” i „Co zrobić” to „wyklucz”:* Kombinacje należące do produktów z tymi konkretnymi kodami referencyjnymi zostaną pominięte.
    -   **Zalecana wartość:** Użyj tego, aby zawęzić zakres usuwania do konkretnych produktów. Wprowadź jeden kod na linię.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz usunąć kombinacje „Pomarańczowe” tylko z produktów o kodach referencyjnych `PROD-A`, `PROD-B` i `PROD-C`. Wprowadź te kody, wybierz „Referencja” dla „Pola kodu” i „uwzględnij” dla „Co zrobić”.
5.  **Pole kodu**

    -   **Co robi to ustawienie:** Definiuje, do którego pola identyfikatora produktu odnosi się „Lista kodów”. Opcje to zazwyczaj „Referencja” (SKU) lub „EAN13” (kod kreskowy).
    -   **Wpływ zmiany tego ustawienia:** Zmienia sposób, w jaki moduł interpretuje kody wprowadzone w „Lista kodów”.
    -   **Zalecana wartość:** „Referencja” dla wewnętrznych SKU, „EAN13” dla kodów kreskowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja lista zawiera kody kreskowe EAN13, wybierz tutaj „EAN13”.
6.  **Lista kodów (Co zrobić)**

    -   **Co robi to ustawienie:** Określa, czy „Lista kodów referencyjnych” (lub kodów EAN) powinna być *uwzględniona* w procesie usuwania (usuń tylko z tych produktów) czy *wykluczona* (usuń ze wszystkich produktów Z WYJĄTKIEM tych).
    -   **Wpływ zmiany tego ustawienia:** Kontroluje zakres produktów objętych usunięciem.
    -   **Zalecana wartość:** „uwzględnij” dla ukierunkowanych usunięć, „wyklucz” dla szerokich usunięć z wyjątkami.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz usunąć kombinacje „Pomarańczowe” ze wszystkich produktów *oprócz* Twojego najlepiej sprzedającego się `BESTSELLER-01`. Wprowadź `BESTSELLER-01` w „Lista kodów” i wybierz tutaj „wyklucz”.
7.  **Produkt**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretny produkt po jego nazwie. Jeśli zostanie wybrany, usunięcie będzie dotyczyć *tylko* kombinacji tego jednego produktu, zastępując wszelkie inne filtry na poziomie produktu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy produkt jest wybrany:* Moduł będzie przetwarzał tylko kombinacje należące do tego konkretnego produktu.
        -   *Gdy pozostawione puste:* Moduł zastosuje kryteria usuwania do wszystkich produktów w Twoim sklepie (z zastrzeżeniem innych filtrów, takich jak „Lista kodów referencyjnych”).
    -   **Zalecana wartość:** Użyj tego do bardzo ukierunkowanych usunięć dla pojedynczego produktu.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz usunąć kombinacje „Pomarańczowe” tylko z produktu „Sukienka letnia”. Wybierzesz tutaj „Sukienka letnia”.

#### **Przycisk akcji**

-   **Przycisk „Usuń wybrane kombinacje”**
    -   **Co robi ten przycisk:** Jest to przycisk akcji, który po kliknięciu wykonuje proces usuwania na podstawie wszystkich ustawionych kryteriów.
    -   **Wpływ kliknięcia tego przycisku:** **Ta akcja jest nieodwracalna!** Wszystkie kombinacje produktów pasujące do wybranej „Wartości atrybutu”, filtrów „Ilość” oraz filtrów „Produkt” lub „Referencja/EAN” zostaną trwale usunięte z Twojej bazy danych. Obejmuje to ich powiązany stan magazynowy, obrazy i ceny specyficzne.
    -   **Zalecana wartość:** **ZAWSZE wykonaj pełną kopię zapasową bazy danych przed kliknięciem tego przycisku.** Dokładnie sprawdź wszystkie ustawienia.
    -   **Scenariusz / przykład dla sprzedawcy:** Po starannym wybraniu „Kolor: Pomarańczowy”, ustawieniu „Ilość: równa 0” i potwierdzeniu kopii zapasowej, klikasz ten przycisk, aby usunąć wszystkie niedostępne kombinacje pomarańczowe.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Wartość atrybutu** | *Wybierz konkretną wartość* | Główny filtr: Usuwa kombinacje zawierające tę wartość atrybutu. |
| Konfiguracja modułu | **Ilość** | *0 lub pożądana liczba* | Filtruje kombinacje na podstawie ich ilości w magazynie. |
| Konfiguracja modułu | **Co zrobić (z ilością)** | *równe* | Definiuje logikę porównania dla filtra „Ilość” (mniej niż, równe, więcej niż). |
| Konfiguracja modułu | **Lista kodów referencyjnych** | *Puste lub konkretne kody* | Lista kodów referencyjnych produktu (SKU) lub EAN do uwzględnienia/wykluczenia. Jeden na linię. |
| Konfiguracja modułu | **Pole kodu** | *Referencja* | Określa, czy „Lista kodów” odnosi się do „Referencji” czy „EAN13”. |
| Konfiguracja modułu | **Lista kodów (Co zrobić)** | *uwzględnij* | Określa, czy wymienione kody są uwzględniane w usunięciu, czy wykluczane z niego. |
| Konfiguracja modułu | **Produkt** | *Puste lub konkretna nazwa produktu* | Celuje usunięcie w pojedynczy produkt, zastępując inne filtry produktów. |
| Konfiguracja modułu | **Usuń wybrane kombinacje** | **Kliknij z ostrożnością!** | Wykonuje nieodwracalne usunięcie kombinacji na podstawie wszystkich kryteriów. **Najpierw wykonaj kopię zapasową!** |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Kliknąłem „Usuń”, ale nic się nie stało lub nie wszystkie kombinacje zostały usunięte.**
O:

-   **Sprawdź filtry:** Ponownie zweryfikuj wszystkie ustawienia: „Wartość atrybutu”, warunki „Ilość”, „Lista kodów” (uwzględnij/wyklucz) i wybór „Produktu”. Nawet niewielka niezgodność może uniemożliwić celowanie w kombinacje.
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może powodować problemy z wyświetlaniem. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
-   **Konflikty modułów:** Inny moduł może zakłócać działanie. Spróbuj wyłączyć inne moduły jeden po drugim (zwłaszcza te związane z zarządzaniem produktami lub kombinacjami), aby sprawdzić, czy problem zostanie rozwiązany.

**P: Przypadkowo usunąłem kombinacje, których nie chciałem. Czy mogę je odzyskać?**
O: **Nie, nie bezpośrednio za pomocą modułu.** Dlatego kopia zapasowa jest kluczowa. Jeśli masz aktualną kopię zapasową bazy danych, możesz przywrócić swój sklep do stanu sprzed usunięcia. Jeśli nie masz kopii zapasowej, będziesz musiał ręcznie odtworzyć kombinacje.

**P: Wartość atrybutu, którą chcę usunąć, nie pojawia się na liście rozwijanej.**
O:

-   **Sprawdź, czy istnieje:** Upewnij się, że wartość atrybutu faktycznie istnieje w Twoim katalogu PrestaShop i jest przypisana do co najmniej jednego produktu. Przejdź do **Katalog > Atrybuty i cechy**, aby to zweryfikować.
-   **Język:** Upewnij się, że przeglądasz Panel administracyjny w prawidłowym języku, jeśli nazwa wartości atrybutu jest zależna od języka.

**P: Czy mogę usunąć kombinacje na podstawie cech zamiast atrybutów?**
O: Nie, ten moduł jest specjalnie zaprojektowany do pracy z **atrybutami i wartościami atrybutów**. Cechy to inna koncepcja w PrestaShop i nie są obsługiwane przez ten moduł do usuwania.

**P: Czy usunięcie kombinacji spowoduje również usunięcie powiązanych obrazów lub cen specyficznych?**
O: Tak, gdy kombinacja zostanie usunięta, wszystkie dane bezpośrednio powiązane z tą konkretną kombinacją (takie jak jej unikalny obraz, specyficzne reguły cenowe dla tej kombinacji i jej ilość w magazynie) również zostaną usunięte. Główny obraz produktu i ogólne ceny specyficzne produktu pozostaną.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `delcombs` to prosty moduł PrestaShop, skupiający się głównie na funkcjonalności Back Office. Przestrzega struktury modułów PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji. Jego podstawowa logika znajduje się w metodzie `getContent()` głównego pliku modułu, gdzie obsługuje przesyłanie formularzy, walidację danych i wykonywanie operacji na bazie danych w celu usunięcia kombinacji produktów. Nie wprowadza niestandardowych kontrolerów front-office ani złożonych ObjectModels, opierając się zamiast tego na bezpośrednich zapytaniach do bazy danych oraz podstawowych klasach PrestaShop `Product` i `Combination` do manipulacji danymi.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front Office**: Brak. Cała funkcjonalność jest ograniczona do Back Office.
-   **Kontrolery administracyjne Back Office**: Brak. Logika konfiguracji i przetwarzania modułu jest obsługiwana w metodzie `getContent()` głównej klasy modułu, która jest renderowana jako część standardowej strony konfiguracji modułu.

### 4.3 Podstawowe klasy i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas w katalogu `classes/`. Bezpośrednio współdziała z podstawowymi klasami PrestaShop `Product` i `Combination` oraz wykonuje bezpośrednie zapytania do bazy danych w celu efektywnego masowego usuwania.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `delcombs/views/js/delcombs-admin.js`
    -   **Zakres:** Back Office (strona konfiguracji modułu).
    -   **Cel:** Ten skrypt prawdopodobnie obsługuje dynamiczne zachowanie na formularzu konfiguracji modułu. Może to obejmować:
        -   Wywołania AJAX do wyszukiwania produktów lub atrybutów (np. dla pola wyboru „Produkt”).
        -   Warunkowe wyświetlanie pól formularza na podstawie wyborów użytkownika (np. pokazywanie/ukrywanie filtrów ilości).
        -   Walidacja danych wejściowych przed przesłaniem formularza.
        -   Okna dialogowe potwierdzenia przed wykonaniem akcji usunięcia.
        -   Interakcje z `searchTool` (prawdopodobnie niestandardowy komponent wyszukiwania produktów/atrybutów).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `delcombs/views/css/delcombs-admin.css`
    -   **Zakres:** Back Office (strona konfiguracji modułu).
    -   **Cel:** Zapewnia stylizację elementów formularza konfiguracji modułu, zapewniając spójny i przyjazny dla użytkownika interfejs w Panelu administracyjnym PrestaShop.
    -   **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w konkretne identyfikatory lub klasy w danych wyjściowych `getContent()` modułu, takie jak grupy formularzy, pola wejściowe i potencjalnie komponent `searchTool`. Programiści mogą nadpisać te style w swoich niestandardowych motywach administracyjnych lub dodając CSS o wyższej specyficzności.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   `delcombs/lib/searchTool/views/scripts.tpl`
    -   **Zakres:** Back Office.
    -   **Cel:** Ten szablon prawdopodobnie zawiera kod JavaScript lub zmienne Smarty potrzebne przez ogólny komponent narzędzia wyszukiwania używany w module. Może inicjalizować pola wyszukiwania, definiować punkty końcowe AJAX dla zapytań wyszukiwania lub konfigurować obsługę danych po stronie klienta dla wyników wyszukiwania. Prawdopodobnie jest on dołączany przez główny szablon konfiguracji.
-   `delcombs/views/templates/admin/tabs.tpl`
    -   **Zakres:** Back Office (strona konfiguracji modułu).
    -   **Cel:** Jest to główny szablon Smarty renderowany przez metodę `getContent()` modułu `delcombs`. Strukturyzuje cały formularz konfiguracji, w tym:
        -   Różne pola wejściowe (listy rozwijane dla atrybutów, obszary tekstowe dla kodów, pola wejściowe ilości).
        -   Przycisk „Usuń wybrane kombinacje”.
        -   Wszelkie komunikaty informacyjne lub ostrzeżenia.
        -   Prawdopodobnie zawiera `scripts.tpl` dla funkcji wyszukiwania.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Działa bezpośrednio na podstawowych tabelach PrestaShop, głównie:
        -   `ps_product_attribute` (główna tabela kombinacji)
        -   `ps_product_attribute_combination` (łączy kombinacje z wartościami atrybutów)
        -   `ps_product_attribute_shop` (dane kombinacji specyficzne dla sklepu)
        -   `ps_stock_available` (stan magazynowy dla kombinacji)
        -   `ps_specific_price` (ceny specyficzne dla kombinacji)
        -   `ps_image` (obrazy powiązane z kombinacjami)
        -   `ps_product` (do filtrowania według ID produktu, referencji, EAN)
        -   `ps_attribute_lang`, `ps_attribute_group_lang` (do wyświetlania nazw atrybutów w listach rozwijanych)
    -   Ustawienia konfiguracji są przechowywane w `ps_configuration` z kluczami takimi jak `delcombs_attribute`, `delcombs_product`, `delcombs_qty_wtd`, `delcombs_qty`, `delcombs_ref_codes`, `delcombs_ref_type`, `delcombs_ean_codes`, `delcombs_ean_type`, `delcombs_ean_field`, `delcombs_product_mode`.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje żadnych hooków wyświetlania front-office ani back-office. Jego funkcjonalność jest całkowicie zawarta na stronie konfiguracji.
    Może używać hooków akcji wewnętrznie (np. `actionProductUpdate` lub `actionAttributeCombinationSave`) do czyszczenia pamięci podręcznej lub reagowania na zmiany, ale nie są one jawnie wymienione jako zarejestrowane hooki do interakcji z modułami zewnętrznymi.
    Podstawowa logika modułu jest wyzwalana przez przesłanie formularza w jego metodzie `getContent()`, a nie przez standardowy hook PrestaShop.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i pobrania najnowszych wersji modułu „Usuwanie kombinacji według atrybutu”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
