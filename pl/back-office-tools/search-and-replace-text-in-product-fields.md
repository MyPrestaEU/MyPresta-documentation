---
title: "Wyszukaj i zamień tekst w polach produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyszukaj i zamień tekst w polach produktu” od MyPresta.eu."
sidebar:
  label: "Wyszukaj i zamień tekst w polach produktu"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Search and replace text in product fields na MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-and-replace-text-in-product-fields.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/search-and-replace-text-in-product-fields/)
>
> ---


# Wyszukaj i zamień tekst w polach produktu

## 1. Wymagania i kompatybilność
-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Wyszukaj i zamień tekst w polach produktu” nie posiada tradycyjnej strony konfiguracji z ustawieniami takimi jak przełączniki czy pola wprowadzania. Zamiast tego, integruje się bezpośrednio z listą produktów PrestaShop, zapewniając nową akcję do wykonywania operacji wyszukiwania i zamiany.

### 2.1 Dostęp do narzędzia wyszukiwania i zamiany

Funkcjonalność modułu jest dostępna bezpośrednio z listy produktów PrestaShop:

1.  **Przejdź do listy produktów:**
    -   W Panelu administracyjnym PrestaShop przejdź do **Katalog > Produkty**.
2.  **Wybierz produkty:**
    -   Możesz wybrać jeden lub więcej konkretnych produktów, zaznaczając pola obok nich, lub możesz zdecydować się zastosować wyszukiwanie i zamianę do *wszystkich* produktów aktualnie wyświetlanych na liście (np. jeśli przefiltrowałeś listę).
3.  **Dostęp do menu akcji masowych:**
    -   Po wybraniu produktów pojawi się rozwijane menu „Akcje masowe” (zazwyczaj na górze lub na dole listy produktów).
4.  **Wybierz „Wyszukaj i zamień tekst w polach produktu”:**
    -   Kliknij rozwijane menu „Akcje masowe” i wybierz opcję oznaczoną **„Wyszukaj i zamień tekst w polach produktu”**.

### 2.2 Interfejs wyszukiwania i zamiany

Po wybraniu akcji „Wyszukaj i zamień tekst w polach produktu” pojawi się okno modalne lub dedykowany interfejs. To tutaj definiujesz operację wyszukiwania i zamiany.

**Dostępne pola do wyszukiwania i zamiany:**
Moduł umożliwia celowanie w różne pola tekstowe związane z Twoimi produktami. Zazwyczaj obejmują one:
-   **Nazwa produktu:** Główny tytuł Twojego produktu.
-   **Krótki opis:** Krótkie podsumowanie często wyświetlane w pobliżu obrazu produktu.
-   **Opis:** Pełny, szczegółowy opis produktu.
-   **Meta tytuł:** Tytuł wyświetlany w zakładkach przeglądarki i wynikach wyszukiwania.
-   **Meta opis:** Krótkie podsumowanie wyświetlane pod tytułem w wynikach wyszukiwania.
-   **Przyjazny URL:** Część adresu internetowego produktu przyjazna dla SEO.
-   **Tagi:** Słowa kluczowe związane z produktem.
-   **Cechy:** Wartości niestandardowych cech produktu (np. „Kolor: Czerwony” – możesz zastąpić „Czerwony” na „Karmazynowy”).
-   **Wartości atrybutów:** Wartości atrybutów produktu (np. „Rozmiar: S” – możesz zastąpić „S” na „Mały”).
-   **Pola personalizacji:** Pola tekstowe, które klienci mogą wypełnić w celu personalizacji produktu.

**Kluczowe ustawienia w interfejsie:**

-   **Szukaj:**
    -   **Co robi to ustawienie:** Jest to dokładna fraza tekstowa, którą chcesz znaleźć w wybranych polach produktu.
    -   **Efekt zmiany tego ustawienia:** Moduł będzie szukał tego precyzyjnego ciągu znaków. Domyślnie jest to wyszukiwanie z uwzględnieniem wielkości liter, chyba że dostępna jest opcja „Bez uwzględniania wielkości liter” (sprawdź interfejs pod tym kątem).
    -   **Zalecana wartość:** Wprowadź dokładny tekst, który chcesz znaleźć.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zmienić „stara nazwa marki” na „nowa nazwa marki”, wpisz tutaj „stara nazwa marki”.

-   **Zastąp przez:**
    -   **Co robi to ustawienie:** Jest to nowa fraza tekstowa, która zastąpi każde wystąpienie tekstu „Szukaj” znalezionego.
    -   **Efekt zmiany tego ustawienia:** Wszystkie wystąpienia tekstu „Szukaj” zostaną zaktualizowane na ten nowy tekst. Jeśli pozostawione puste, tekst „Szukaj” zostanie usunięty.
    -   **Zalecana wartość:** Wprowadź nowy tekst, którego chcesz użyć.
    -   **Scenariusz / przykład dla sprzedawcy:** Zgodnie z powyższym przykładem, wpisz tutaj „nowa nazwa marki”.

-   **Wybierz pola do przeszukania:**
    -   **Co robi to ustawienie:** Jest to lista pól wyboru lub rozwijane menu wielokrotnego wyboru, w którym wybierasz, które konkretne pola tekstowe produktu (np. „Opis”, „Krótki opis”, „Meta tytuł”) moduł powinien przetworzyć.
    -   **Efekt zmiany tego ustawienia:** Tylko wybrane pola zostaną przeskanowane i zmodyfikowane. Niewybrane pola pozostaną nietknięte.
    -   **Zalecana wartość:** Wybierz tylko pola istotne dla Twojego bieżącego zadania, aby uniknąć niezamierzonych zmian.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zaktualizować tylko główny opis produktu, zaznacz tylko „Opis”. Jeśli aktualizujesz nazwę marki wszędzie, możesz zaznaczyć „Nazwa produktu”, „Krótki opis”, „Opis”, „Meta tytuł” i „Meta opis”.

-   **Zastosuj do wybranych produktów / Zastosuj do wszystkich przefiltrowanych produktów:**
    -   **Co robi to ustawienie:** Potwierdza, czy operacja dotyczy tylko produktów, które ręcznie zaznaczyłeś na liście, czy też wszystkich produktów aktualnie widocznych na liście produktów (która może być przefiltrowanym podzbiorem).
    -   **Efekt zmiany tego ustawienia:** Określa zakres operacji. Bądź bardzo ostrożny z opcją „wszystkie przefiltrowane produkty”, aby upewnić się, że Twoje filtry są poprawnie zastosowane.
    -   **Zalecana wartość:** Zawsze dokładnie sprawdzaj swój wybór produktów przed kontynuowaniem.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli przefiltrowałeś listę produktów, aby wyświetlić tylko produkty z określonej kategorii, a następnie wybierzesz „Zastosuj do wszystkich przefiltrowanych produktów”, zmiany będą dotyczyć tylko produktów z tej kategorii.

-   **Z uwzględnieniem wielkości liter / Bez uwzględniania wielkości liter (jeśli dostępne):**
    -   **Co robi to ustawienie:** Określa, czy wyszukiwanie powinno rozróżniać wielkie i małe litery.
    -   **Efekt zmiany tego ustawienia:**
        -   *Z uwzględnieniem wielkości liter:* „Apple” nie będzie pasować do „apple”.
        -   *Bez uwzględniania wielkości liter:* „Apple” będzie pasować do „apple”, „APPLE”, „Apple” itp.
    -   **Zalecana wartość:** Użyj opcji bez uwzględniania wielkości liter dla szerokich zamian (np. poprawianie typowej literówki, która może pojawić się w różnych przypadkach). Użyj opcji z uwzględnieniem wielkości liter dla precyzyjnych zamian, gdzie wielkość liter ma znaczenie.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zastąpić „ProduktX” na „Produkt Y”, ale niektóre opisy mogą zawierać „produktX”, użycie opcji bez uwzględniania wielkości liter złapie oba.

-   **Podgląd / Test (jeśli dostępne):**
    -   **Co robi to ustawienie:** Niektóre zaawansowane narzędzia wyszukiwania i zamiany oferują tryb „podglądu” lub „testu”, który pokazuje, jakie zmiany *zostałyby* wprowadzone bez faktycznego ich zapisywania.
    -   **Efekt zmiany tego ustawienia:** Pozwala przejrzeć wpływ operacji przed jej zatwierdzeniem, zapobiegając przypadkowej utracie danych.
    -   **Zalecana wartość:** Zawsze używaj podglądu, jeśli jest dostępny, zwłaszcza w przypadku operacji na dużą skalę.
    -   **Scenariusz / przykład dla sprzedawcy:** Przed zastąpieniem „stary” na „nowy” w 1000 produktów, podgląd pokazałby dokładnie, które produkty i pola zostałyby zmienione.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Lista produktów (Akcje masowe) | Szukaj | Zdefiniowane przez użytkownika | Dokładny ciąg tekstowy do znalezienia. Z uwzględnieniem wielkości liter, chyba że określono inaczej. |
| Lista produktów (Akcje masowe) | Zastąp przez | Zdefiniowane przez użytkownika | Ciąg tekstowy, którym należy zastąpić tekst „Szukaj”. Puste pole usuwa tekst. |
| Lista produktów (Akcje masowe) | Wybierz pola do przeszukania | Zdefiniowane przez użytkownika | Pola wyboru do zaznaczenia, które pola produktu (opis, nazwa, meta itp.) mają zostać zmodyfikowane. |
| Lista produktów (Akcje masowe) | Zastosuj do wybranych produktów / wszystkich przefiltrowanych produktów | Zdefiniowane przez użytkownika | Definiuje zakres operacji: tylko zaznaczone produkty lub wszystkie aktualnie przefiltrowane produkty. |
| Lista produktów (Akcje masowe) | Z uwzględnieniem wielkości liter / Bez uwzględniania wielkości liter | (Sprawdź interfejs modułu) | Określa, czy wyszukiwanie rozróżnia wielkie i małe litery. |
| Lista produktów (Akcje masowe) | Podgląd / Test | (Jeśli dostępne, zawsze używaj) | Pokazuje potencjalne zmiany przed ich zastosowaniem, zapobiegając błędom. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Uruchomiłem wyszukiwanie i zamianę, ale nie widzę zmian na mojej stronie.**
O: PrestaShop używa buforowania, aby przyspieszyć działanie Twojego sklepu. Po wprowadzeniu zmian w Panelu administracyjnym, często musisz wyczyścić pamięć podręczną, aby pojawiły się one w Front Office.
    -   Przejdź do **Zaawansowane > Wydajność**.
    -   Kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
    -   Jeśli używasz modułu buforowania innej firmy lub CDN, wyczyść również ich pamięci podręczne.

**P: Moduł nie pojawia się w menu „Akcje masowe” na liście produktów.**
O:
    1.  **Sprawdź instalację:** Upewnij się, że moduł jest poprawnie zainstalowany i włączony w **Moduły > Menedżer modułów**.
    2.  **Uprawnienia:** Sprawdź, czy Twoje konto użytkownika ma niezbędne uprawnienia do zarządzania modułami i produktami.
    3.  **Konflikty modułów:** Rzadko, inny moduł, który mocno modyfikuje listę produktów lub akcje masowe, może powodować konflikt. Spróbuj tymczasowo wyłączyć inne ostatnio zainstalowane moduły, aby sprawdzić, czy problem zostanie rozwiązany.

**P: Przypadkowo zastąpiłem niewłaściwy tekst lub popełniłem błąd. Jak mogę to cofnąć?**
O: Niestety, moduł wykonuje bezpośrednią aktualizację bazy danych i nie ma wbudowanego przycisku „cofnij”. Dlatego kopie zapasowe są kluczowe.
    -   **Przywróć z kopii zapasowej:** Najbezpieczniejszym sposobem na cofnięcie jest przywrócenie bazy danych z kopii zapasowej wykonanej *przed* uruchomieniem operacji.
    -   **Uruchom operację odwrotną:** Jeśli zmieniłeś tylko prostą frazę, możesz spróbować uruchomić inną operację wyszukiwania i zamiany, aby ją cofnąć (np. wyszukaj „nowy tekst” i zastąp „stary tekst”). Jest to ryzykowne i działa tylko w przypadku prostych, bezpośrednich zamian.

**P: Czy mogę używać tego modułu w sklepach wielojęzycznych?**
O: Tak, moduł działa na polach produktów, które często są wielojęzyczne w PrestaShop. Kiedy wybierzesz pola takie jak „Opis” lub „Nazwa produktu”, moduł zazwyczaj zastosuje wyszukiwanie i zamianę do wszystkich aktywnych języków dla tych pól. Interfejs powinien pozwolić Ci określić, które języki mają być docelowe, jeśli ta opcja jest dostępna.

**P: Operacja wyszukiwania i zamiany jest bardzo wolna lub przekracza limit czasu dla dużej liczby produktów.**
O:
    1.  **Zasoby serwera:** Duże operacje na tysiącach produktów mogą być zasobochłonne. Upewnij się, że Twój serwer ma odpowiednie limity pamięci PHP i czasu wykonania. Może być konieczne zwiększenie `memory_limit` i `max_execution_time` w pliku `php.ini` (skonsultuj się z dostawcą hostingu lub webmasterem).
    2.  **Przetwarzaj w partiach:** Jeśli to możliwe, filtruj listę produktów i uruchamiaj operację na mniejszych partiach produktów (np. według kategorii, marki lub zakresu ID) zamiast próbować przetwarzać cały katalog naraz.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzyć moduł „Wyszukaj i zamień tekst w polach produktu”.

### 4.1 Przegląd architektury
Moduł `snrp` to prosty moduł PrestaShop, skupiający się głównie na rozszerzaniu funkcjonalności listy produktów w Panelu administracyjnym. Wykorzystuje system hooków PrestaShop do wstrzyknięcia nowej akcji masowej do kontrolera `AdminProducts`. Główna logika znajduje się w głównym pliku modułu, obsługując wyświetlanie formularza wyszukiwania/zamiany i wykonywanie aktualizacji bazy danych. Nie używa niestandardowych klas `ObjectModel` ani dedykowanych kontrolerów administracyjnych, ale raczej rozszerza istniejące widoki administracyjne PrestaShop.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front Office ani Back Office. Jego funkcjonalność jest zintegrowana z istniejącym kontrolerem `AdminProducts` za pośrednictwem hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)
Ten moduł nie definiuje żadnych niestandardowych klas w katalogu `classes/`. Cała logika rdzenia znajduje się w głównym pliku modułu `snrp/index.php`. Moduł bezpośrednio współdziała z `ObjectModel` PrestaShop `Product` i `ProductLang`, a potencjalnie z danymi `FeatureValue`, `AttributeGroup` i `Tag`, wykonując aktualizacje SQL na podstawie danych wprowadzonych przez użytkownika.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`snrp/views/js/snrp.js`**
    *   **Zakres:** Panel administracyjny (konkretnie strona listy `AdminProducts`).
    *   **Odpowiedzialność:** Ten skrypt odpowiada za zachowanie po stronie klienta narzędzia wyszukiwania i zamiany.
        *   Prawdopodobnie wiąże słuchacza zdarzeń z opcją „Wyszukaj i zamień tekst w polach produktu” w rozwijanym menu „Akcje masowe”.
        *   Po wybraniu, wyzwala wyświetlanie okna modalnego lub formularza, w którym użytkownik wprowadza termin wyszukiwania, termin zastępczy i wybiera pola docelowe.
        *   Obsługuje żądanie AJAX do metody `getContent()` modułu (lub dedykowanego punktu końcowego AJAX, jeśli zostałby zaimplementowany w `index.php`) w celu przesłania parametrów wyszukiwania i zamiany.
        *   Zarządza informacjami zwrotnymi interfejsu użytkownika podczas i po operacji (np. wskaźniki ładowania, komunikaty o sukcesie/błędzie).
        *   Może zawierać logikę walidacji pól wejściowych przed przesłaniem.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`snrp/views/css/snrp.css`**
    *   **Zakres:** Panel administracyjny (konkretnie strona listy `AdminProducts`).
    *   **Odpowiedzialność:** Ten arkusz stylów zapewnia wizualne style dla interfejsu wyszukiwania i zamiany.
        *   Definiuje wygląd okna modalnego (rozmiar, pozycjonowanie, nakładka tła).
        *   Stylizuje pola wejściowe, przyciski, pola wyboru i wszelkie inne elementy interfejsu użytkownika w formularzu wyszukiwania i zamiany.
        *   Zapewnia wizualną integrację interfejsu z motywem Panelu administracyjnego PrestaShop.
    *   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści mogą sprawdzić wygenerowany kod HTML okna modalnego, aby zidentyfikować konkretne nazwy klas (np. `.snrp-modal`, `.snrp-form-group`, `.snrp-button`) w celu dostosowania jego wyglądu w swoich niestandardowych motywach administracyjnych lub za pośrednictwem `override/css/admin.css`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Opis modułu wskazuje brak plików `.tpl` w `views/templates/`. Sugeruje to, że formularz konfiguracji modułu i interfejs modalny wyszukiwania/zamiany są prawdopodobnie renderowane bezpośrednio w metodzie `getContent()` pliku `snrp/index.php` przy użyciu czystego kodu HTML i PHP lub poprzez dynamiczne generowanie elementów formularza za pomocą JavaScript.

Jeśli używane jest okno modalne, możliwe jest, że struktura HTML jest wstrzykiwana bezpośrednio do DOM przez `snrp.js` lub renderowana jako część odpowiedzi `getContent()`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    *   Bezpośrednio modyfikuje istniejące tabele PrestaShop, głównie:
        *   `ps_product_lang`: Dla nazw produktów, krótkich opisów, opisów, meta tytułów, meta opisów i przyjaznych adresów URL (pola specyficzne dla języka).
        *   `ps_tag`: Dla tagów produktów.
        *   Potencjalnie `ps_feature_product` i `ps_product_attribute_lang`, jeśli wartości cech i wartości atrybutów są docelowe.
    *   Ustawienia konfiguracji (jeśli byłyby obecne) byłyby zazwyczaj przechowywane w `ps_configuration`.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` Panelu administracyjnego. | Służy do dołączania `snrp.js` i `snrp.css` na odpowiednich stronach administracyjnych (np. `AdminProducts`). |
| `displayAdminProductsExtra` | Renderuje dodatkową zawartość na stronie listy `AdminProducts`. | Ten hook jest prawdopodobnie używany do wstrzyknięcia struktury HTML dla opcji „Wyszukaj i zamień tekst w polach produktu” do rozwijanego menu „Akcje masowe” lub do dodania przycisku, który wyzwala okno modalne. |
| `actionProductUpdate` / `actionObjectProductUpdateAfter` | Wykonywane po aktualizacji produktu. | Chociaż nie jest to wyraźnie określone, moduł może zaczepiać się o te hooki, aby wykonywać dodatkowe działania lub logowanie po udanej operacji wyszukiwania i zamiany, chociaż bezpośrednie aktualizacje SQL są bardziej prawdopodobne ze względu na wydajność. |
| `actionAdminProductsListingResultsModifier` | Modyfikuje wyniki listy produktów. | Mniej prawdopodobne dla tego modułu, ale może być używane do dodania kolumny lub modyfikacji wyświetlanych danych przed wyzwoleniem akcji wyszukiwania/zamiany. |

Główna funkcjonalność wykonywania logiki wyszukiwania i zamiany będzie obsługiwana w metodzie `getContent()` modułu (lub dedykowanej metodzie AJAX w `index.php`) po przesłaniu formularza, przetwarzając wybrane identyfikatory produktów i pola.

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyszukaj i zamień tekst w polach produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
