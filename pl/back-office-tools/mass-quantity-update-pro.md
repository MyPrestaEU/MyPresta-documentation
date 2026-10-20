---
title: "Masowa aktualizacja ilości pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Masowa aktualizacja ilości pro” od MyPresta.eu."
sidebar:
  label: "Masowa aktualizacja ilości pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Mass quantity update pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-quantity-update-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/mass-quantity-update-pro/)
>
> ---


# Masowa aktualizacja ilości pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Masowa aktualizacja ilości pro” zapewnia jeden, intuicyjny ekran konfiguracji w Panelu administracyjnym PrestaShop, gdzie definiujesz produkty do aktualizacji i zmiany ilości do zastosowania.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do konfiguracji modułu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Masowa aktualizacja ilości pro” i kliknij przycisk „Konfiguruj”.

Strona konfiguracji jest podzielona na dwie główne sekcje: **Produkty docelowe** i **Co zrobić?**.

#### 2.1.1 Produkty docelowe

Ta sekcja pozwala zdefiniować, *które* produkty lub kombinacje produktów zostaną objęte aktualizacją ilości. Możesz wybrać produkty na podstawie różnych kryteriów.

-   **Do czego służy to ustawienie:** Ta sekcja definiuje zakres aktualizacji ilości. Wybierasz konkretną grupę produktów, których ilości zostaną zmodyfikowane.
-   **Efekt zmiany tego ustawienia:** Tylko produkty spełniające wybrane kryteria zostaną uwzględnione w aktualizacji ilości. Jeśli żadne kryteria nie zostaną wybrane, żadne produkty nie zostaną objęte.
-   **Zalecana wartość:** Wybierz jedno lub więcej kryteriów, które precyzyjnie definiują produkty, które zamierzasz zmodyfikować.

**Dostępne kryteria:**

1.  **Produkty z kategorii:**
    -   **Do czego służy to ustawienie:** Pozwala wybrać jedną lub więcej konkretnych kategorii produktów. Wszystkie produkty (i ich kombinacje) należące do tych kategorii zostaną objęte.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Produkty z wybranych kategorii zostaną uwzględnione.
        -   *Gdy nie wybrano:* Produkty nie są filtrowane według kategorii.
    -   **Zalecana wartość:** Wybierz to, jeśli musisz zaktualizować zapasy dla całej linii produktów lub działu.
    -   **Scenariusz / przykład sprzedawcy:** Otrzymałeś nową dostawę wszystkich produktów z kategorii „Kolekcja letnia”. Możesz wybrać tę kategorię, aby zaktualizować ich zapasy.
2.  **Produkty według marki:**
    -   **Do czego służy to ustawienie:** Pozwala wybrać jedną lub więcej konkretnych marek produktów (producentów). Wszystkie produkty (i ich kombinacje) powiązane z tymi markami zostaną objęte.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Produkty z wybranych marek zostaną uwzględnione.
        -   *Gdy nie wybrano:* Produkty nie są filtrowane według marki.
    -   **Zalecana wartość:** Wybierz to, jeśli musisz zaktualizować zapasy dla produktów od konkretnego dostawcy lub marki.
    -   **Scenariusz / przykład sprzedawcy:** Twój dostawca „Fashionista Inc.” dostarczył nowy towar. Wybierasz „Fashionista Inc.”, aby zaktualizować wszystkie ich produkty.
3.  **Produkty według cech:**
    -   **Do czego służy to ustawienie:** Pozwala wybrać produkty na podstawie przypisanych im cech (np. „Kolor: Czerwony”, „Materiał: Bawełna”). Możesz wybrać cechę, a następnie konkretne wartości dla tej cechy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Tylko produkty posiadające określoną cechę i wartość zostaną uwzględnione.
        -   *Gdy nie wybrano:* Produkty nie są filtrowane według cech.
    -   **Zalecana wartość:** Przydatne do bardzo specyficznych aktualizacji opartych na charakterystyce produktu.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zaktualizować zapasy wszystkich koszulek „Bawełna organiczna”. Wybierasz „Materiał” jako cechę i „Bawełna organiczna” jako wartość.
4.  **Produkty według atrybutów:**
    -   **Do czego służy to ustawienie:** Pozwala wybrać produkty na podstawie ich atrybutów (np. „Rozmiar: M”, „Kolor: Niebieski”). Jest to szczególnie przydatne dla kombinacji produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Tylko kombinacje produktów z określonym atrybutem i wartością zostaną uwzględnione.
        -   *Gdy nie wybrano:* Produkty nie są filtrowane według atrybutów.
    -   **Zalecana wartość:** Niezbędne do zarządzania zapasami konkretnych wariantów produktów.
    -   **Scenariusz / przykład sprzedawcy:** Otrzymałeś nową dostawę koszulek „Rozmiar L”. Wybierasz „Rozmiar” jako atrybut i „L” jako wartość, aby zaktualizować tylko te kombinacje.
5.  **Produkty według powiązań z regułami podatkowymi:**
    -   **Do czego służy to ustawienie:** Pozwala wybrać produkty na podstawie grupy reguł podatkowych do nich zastosowanych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Tylko produkty powiązane z wybraną grupą reguł podatkowych zostaną uwzględnione.
        -   *Gdy nie wybrano:* Produkty nie są filtrowane według reguł podatkowych.
    -   **Zalecana wartość:** Przydatne dla sklepów ze złożonymi strukturami podatkowymi lub gdy aktualizacje zapasów są powiązane z inwentarzem związanym z podatkami.
    -   **Scenariusz / przykład sprzedawcy:** Musisz dostosować zapasy dla wszystkich produktów podlegających określonej regule podatkowej „Cło importowe”.
6.  **Konkretne produkty:**
    -   **Do czego służy to ustawienie:** Udostępnia pole wyszukiwania z autouzupełnianiem, aby ręcznie wybrać pojedyncze produkty według nazwy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po dodaniu produktów:* Tylko wyraźnie wybrane produkty (i ich kombinacje) zostaną objęte.
        -   *Gdy puste:* W ten sposób nie są objęte żadne konkretne produkty.
    -   **Zalecana wartość:** Użyj tego do bardzo precyzyjnych aktualizacji na małym, ręcznie wybranym zestawie produktów.
    -   **Scenariusz / przykład sprzedawcy:** Musisz zaktualizować zapasy dla „Produktu A”, „Produktu B” i „Produktu C”, które nie są powiązane kategorią ani marką.

#### 2.1.2 Co zrobić?

Ta sekcja definiuje, *jak* zostaną zmienione ilości docelowych produktów.

-   **Do czego służy to ustawienie:** Ta sekcja określa typ modyfikacji ilości (zwiększenie, zmniejszenie lub ustawienie na stałą wartość) oraz wielkość zmiany.
-   **Efekt zmiany tego ustawienia:** Wybrana operacja zostanie zastosowana do ilości wszystkich produktów zdefiniowanych w sekcji „Produkty docelowe”.
-   **Zalecana wartość:** Wybierz operację, która dokładnie odzwierciedla Twoją korektę inwentarza.

**Dostępne operacje:**

1.  **Zwiększ ilość o:**
    -   **Do czego służy to ustawienie:** Dodaje określoną liczbę do bieżącej ilości każdego docelowego produktu/kombinacji.
    -   **Efekt zmiany tego ustawienia:** Poziom zapasów dla każdego docelowego elementu wzrośnie o wprowadzoną kwotę.
    -   **Zalecana wartość:** Użyj, gdy nadejdzie nowy towar. Wprowadź dodatnią liczbę całkowitą (np. `10`).
    -   **Scenariusz / przykład sprzedawcy:** Otrzymałeś 50 sztuk produktu. Wybierasz „Zwiększ ilość o” i wprowadzasz `50`.
2.  **Zmniejsz ilość o:**
    -   **Do czego służy to ustawienie:** Odejmuje określoną liczbę od bieżącej ilości każdego docelowego produktu/kombinacji.
    -   **Efekt zmiany tego ustawienia:** Poziom zapasów dla każdego docelowego elementu spadnie o wprowadzoną kwotę.
    -   **Zalecana wartość:** Użyj, gdy zapasy muszą zostać zmniejszone z powodu uszkodzeń, zwrotów lub użytku wewnętrznego. Wprowadź dodatnią liczbę całkowitą (np. `5`).
    -   **Scenariusz / przykład sprzedawcy:** 5 przedmiotów zostało uszkodzonych w magazynie. Wybierasz „Zmniejsz ilość o” i wprowadzasz `5`.
3.  **Ustaw ilość na:**
    -   **Do czego służy to ustawienie:** Zmienia bieżącą ilość każdego docelowego produktu/kombinacji na konkretną, stałą liczbę.
    -   **Efekt zmiany tego ustawienia:** Poziom zapasów dla każdego docelowego elementu stanie się dokładnie wprowadzona kwota, niezależnie od jego poprzedniej ilości.
    -   **Zalecana wartość:** Użyj, gdy musisz zsynchronizować zapasy z systemem zewnętrznym lub skorygować absolutną liczbę zapasów. Wprowadź nieujemną liczbę całkowitą (np. `100`).
    -   **Scenariusz / przykład sprzedawcy:** Po pełnej inwentaryzacji wiesz, że masz dokładnie 100 sztuk produktu. Wybierasz „Ustaw ilość na” i wprowadzasz `100`.

**Ważna uwaga:** Po zdefiniowaniu zarówno „Produktów docelowych”, jak i „Co zrobić?”, musisz kliknąć przycisk **„Aktualizuj ilości”**, aby zastosować zmiany. Nie ma przycisku „cofnij”, więc zawsze dokładnie sprawdź swoje wybory przed potwierdzeniem.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Produkty docelowe** | | Definiuje, które produkty/kombinacje zostaną objęte. |
| | Produkty z kategorii | Wybierz według potrzeb | Celuje we wszystkie produkty w wybranych kategoriach. |
| | Produkty według marki | Wybierz według potrzeb | Celuje we wszystkie produkty wybranych marek. |
| | Produkty według cech | Wybierz według potrzeb | Celuje w produkty o określonych cechach/wartościach. |
| | Produkty według atrybutów | Wybierz według potrzeb | Celuje w kombinacje produktów o określonych atrybutach/wartościach. |
| | Produkty według powiązań z regułami podatkowymi | Wybierz według potrzeb | Celuje w produkty powiązane z wybranymi regułami podatkowymi. |
| | Konkretne produkty | Wybierz według potrzeb | Celuje w indywidualnie wybrane produkty. |
| | **Co zrobić?** | | Definiuje, jak zostaną zmienione ilości. |
| | Zwiększ ilość o | Wprowadź dodatnią liczbę całkowitą | Dodaje określoną kwotę do bieżącego stanu magazynowego. |
| | Zmniejsz ilość o | Wprowadź dodatnią liczbę całkowitą | Odejmuje określoną kwotę od bieżącego stanu magazynowego. |
| | Ustaw ilość na | Wprowadź nieujemną liczbę całkowitą | Ustawia stan magazynowy na dokładną, określoną kwotę. |
| | **Przycisk Aktualizuj ilości** | Kliknij, aby zastosować | Wykonuje zdefiniowane zmiany ilości. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zaktualizowałem ilości, ale mój sklep nadal pokazuje stare liczby. Co jest nie tak?**
**O1:** Zazwyczaj jest to problem z pamięcią podręczną. PrestaShop używa pamięci podręcznej, aby przyspieszyć działanie Twojego sklepu.

-   **Rozwiązanie:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” / „Wyczyść pamięć podręczną” w zależności od wersji PrestaShop). To powinno wymusić na Twoim sklepie wyświetlanie zaktualizowanych ilości.

**P2: Popełniłem błąd i zaktualizowałem niewłaściwe produkty/ilości. Czy mogę to cofnąć?**
**O2:** Moduł nie posiada przycisku „cofnij”. Dlatego tak ważne jest, aby dokładnie sprawdzić swoje wybory przed kliknięciem „Aktualizuj ilości”.

-   **Rozwiązanie:** Jeśli masz aktualną kopię zapasową swojej bazy danych, możesz ją przywrócić (chociaż może to spowodować cofnięcie innych ostatnich zmian). W przeciwnym razie będziesz musiał ręcznie skorygować ilości dla dotkniętych produktów lub ponownie użyć modułu z prawidłowymi ustawieniami, aby je ponownie dostosować. Na przykład, jeśli przypadkowo zwiększyłeś o 10, możesz zmniejszyć o 10.

**P3: Moduł nie znajduje produktów, gdy wpisuję w polu wyszukiwania „Konkretne produkty”.**
**O3:** Upewnij się, że wpisujesz pełną lub częściową nazwę istniejącego produktu w swoim sklepie. Funkcja autouzupełniania opiera się na JavaScript.

-   **Rozwiązanie:**
    1.  Sprawdź konsolę swojej przeglądarki pod kątem błędów JavaScript (klawisz F12, a następnie zakładka „Konsola”).
    2.  Spróbuj wyczyścić pamięć podręczną przeglądarki.
    3.  Upewnij się, że Twój sklep PrestaShop działa na kompatybilnej wersji PHP (patrz sekcja 3).
    4.  Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P4: Czy mogę aktualizować ilości dla produktów, które mają kombinacje (atrybuty)?**
**O4:** Tak, absolutnie! Moduł jest zaprojektowany do obsługi kombinacji produktów. Kiedy wybierzesz produkty według kategorii, marki, cechy lub konkretnego produktu, zastosuje zmianę ilości do wszystkich powiązanych kombinacji tych produktów. Jeśli użyjesz „Produkty według atrybutów”, możesz nawet bezpośrednio celować w konkretne kombinacje.

**P5: Moduł wydaje się działać wolno podczas aktualizacji bardzo dużej liczby produktów.**
**O5:** Aktualizacja tysięcy produktów może być zasobochłonna.

-   **Rozwiązanie:**
    1.  Upewnij się, że Twój serwer spełnia zalecane specyfikacje PrestaShop.
    2.  Zwiększ limity czasu wykonania PHP (`max_execution_time`) i limity pamięci (`memory_limit`) w pliku `php.ini` (skonsultuj się z dostawcą hostingu lub webmasterem).
    3.  Jeśli to możliwe, podziel bardzo duże aktualizacje na mniejsze partie (np. aktualizuj jedną kategorię na raz zamiast wszystkich kategorii).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Masowa aktualizacja ilości pro”.

### 4.1 Przegląd architektury

Moduł `MassQtyPro` przestrzega standardowej architektury modułu PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i metodę `getContent()` dla swojego pojedynczego interfejsu konfiguracji w Panelu administracyjnym. Integruje niestandardowe narzędzie wyszukiwania do wyboru produktów, wykorzystując AJAX do funkcji autouzupełniania. Moduł bezpośrednio współpracuje z klasami PrestaShop `Product` i `StockAvailable` w celu wykonywania aktualizacji ilości.

### 4.2 Kontrolery (`controllers/`)

Moduł nie wykorzystuje niestandardowych kontrolerów front-office ani back-office. Cała logika konfiguracji i przetwarzania dla back-office jest obsługiwana w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani dedykowanych klas w katalogu `classes/`. Cała podstawowa logika znajduje się w głównym pliku `massqtypro.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`massqtypro/lib/searchTool/views/js/autocomplete.js`**
    -   **Zakres:** Back-office (używany na stronie konfiguracji modułu).
    -   **Opis:** Ten skrypt prawdopodobnie implementuje lub integruje ogólną funkcjonalność autouzupełniania. Nasłuchuje danych wprowadzanych przez użytkownika w polach tekstowych (szczególnie do wyszukiwania produktów) i wysyła żądania AJAX w celu pobrania pasujących nazw produktów. Następnie wyświetla te sugestie na liście rozwijanej, umożliwiając użytkownikowi wybór produktów. Zarządza wyświetlaniem i wyborem wyników autouzupełniania.
-   **`massqtypro/views/js/jquery.autocomplete.js`**
    -   **Zakres:** Back-office (używany na stronie konfiguracji modułu).
    -   **Opis:** Wydaje się, że jest to wtyczka jQuery do funkcji autouzupełniania. Zapewnia podstawową strukturę dla pola wyszukiwania produktów na stronie konfiguracji modułu. Obsługuje wywołania AJAX do serwera (prawdopodobnie do metody `getContent()` lub konkretnego hooka, który dostarcza dane produktów), przetwarza odpowiedź JSON i renderuje sugestie. Zarządza również wyborem elementu z listy i wypełnianiem pola wejściowego lub ukrytego pola identyfikatorem wybranego produktu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`massqtypro/lib/searchTool/views/css/autocomplete.css`**
    -   **Zakres:** Back-office (stylizacja strony konfiguracji modułu).
    -   **Opis:** Ten arkusz stylów zapewnia wizualną prezentację pola wyszukiwania z autouzupełnianiem i jego listy sugestii. Definiuje style dla pola wejściowego, kontenera rozwijanego, poszczególnych elementów sugestii i potencjalnie stanów najechania/aktywności dla lepszej interakcji użytkownika. Programiści mogą nadpisać te style w swoim niestandardowym motywie administracyjnym lub dodając specyficzne reguły CSS, aby celować w elementy modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania formularza konfiguracji w Panelu administracyjnym.

-   **`massqtypro/lib/searchTool/views/scripts.tpl`**
    -   **Zakres:** Back-office (zawarty na stronie konfiguracji modułu).
    -   **Opis:** Ten szablon prawdopodobnie zawiera niezbędne pliki JavaScript i CSS dla narzędzia wyszukiwania z autouzupełnianiem. Może również zawierać wbudowany JavaScript do inicjalizacji wtyczki autouzupełniania na określonych polach wejściowych, przekazywania opcji konfiguracji i definiowania funkcji zwrotnych po wybraniu produktu.
-   **`massqtypro/views/templates/admin/target_products.tpl`**
    -   **Zakres:** Back-office (część formularza konfiguracji modułu).
    -   **Opis:** Ten szablon renderuje sekcję „Produkty docelowe” na stronie konfiguracji modułu. Zawiera kod HTML dla wszystkich kryteriów wyboru produktów: rozwijane listy kategorii, rozwijane listy marek, selektory cech/atrybutów, selektory reguł podatkowych i pole wejściowe autouzupełniania dla konkretnych produktów. Wykorzystuje standardowe pomocniki formularzy PrestaShop i potencjalnie niestandardowy kod HTML dla dynamicznych elementów wyboru.
-   **`massqtypro/views/templates/admin/wtd.tpl`**
    -   **Zakres:** Back-office (część formularza konfiguracji modułu).
    -   **Opis:** Ten szablon renderuje sekcję „Co zrobić?” na stronie konfiguracji modułu. Zawiera kod HTML dla operacji aktualizacji ilości: przyciski radiowe dla „Zwiększ”, „Zmniejsz” lub „Ustaw na” oraz odpowiednie pole wejściowe dla wartości ilości. Zawiera również przycisk przesyłania „Aktualizuj ilości”.
-   **`massqtypro/views/templates/hook/form.tpl`**
    -   **Zakres:** Back-office (główny formularz konfiguracji).
    -   **Opis:** Jest to główny szablon dla strony konfiguracji modułu. Prawdopodobnie opakowuje szablony `target_products.tpl` i `wtd.tpl`, łącząc je w kompletny formularz konfiguracji. Obsługiwałby również ogólne przesyłanie formularza i wyświetlanie wszelkich komunikatów o sukcesie lub błędach.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Głównie współpracuje z istniejącymi tabelami PrestaShop, w szczególności `ps_product`, `ps_product_attribute`, `ps_stock_available`, `ps_category_product`, `ps_manufacturer`, `ps_feature_product`, `ps_product_attribute_combination` i `ps_tax_rule_group_product`. Ustawienia konfiguracji są przechowywane w `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:
    Główna funkcjonalność modułu jest wykonywana za pomocą metody `getContent()` w Panelu administracyjnym. Nie rejestruje się on jawnie do hooków front-office w celach wyświetlania. Jednak moduł może wewnętrznie używać hooków do działań administracyjnych lub pobierania danych.

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` Panelu administracyjnego. | Potencjalnie używany do ładowania CSS/JS specyficznych dla modułu na stronie konfiguracji, chociaż często obsługiwany bezpośrednio w `getContent()`. |
    | `actionProductUpdate` | Po zaktualizowaniu produktu. | Może być używany do wewnętrznego logowania lub do wyzwalania powiązanych działań, chociaż nie jest to wyraźnie określone w funkcjach. |
    | `actionUpdateQuantity` | Po zaktualizowaniu ilości produktu. | Może być używany do wewnętrznego logowania lub do wyzwalania powiązanych działań, chociaż nie jest to wyraźnie określone w funkcjach. |

    Podstawowa logika modułu do aktualizacji ilości bezpośrednio manipuluje wpisami `StockAvailable`, co wewnętrznie wyzwala mechanizmy aktualizacji zapasów PrestaShop.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie techniczne, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w wszelkich problemach lub pytaniach związanych z modułem „Masowa aktualizacja ilości pro”.
"""
