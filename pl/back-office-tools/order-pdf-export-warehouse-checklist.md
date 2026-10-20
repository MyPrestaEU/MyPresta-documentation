---
title: "Eksport PDF zamówień i lista kontrolna magazynu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Eksport PDF zamówień i lista kontrolna magazynu” od MyPresta.eu."
sidebar:
  label: "Eksport PDF zamówień i lista kontrolna magazynu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order PDF Export & Warehouse Checklist na MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-pdf-export-warehouse-checklist.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/order-pdf-export-warehouse-checklist/)
>
> ---


# Eksport PDF zamówień i lista kontrolna magazynu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do tego ekranu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Eksport PDF zamówień i lista kontrolna magazynu” i kliknij „Konfiguruj”.

#### **Szablon PDF**

-   **Co robi to ustawienie:** Pozwala wybrać projekt wizualny i układ dokumentów PDF generowanych przez moduł. Możesz wybrać spośród różnych wstępnie zaprojektowanych szablonów.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Clean” (Czysty):* Twoje pliki PDF będą miały minimalistyczny, nowoczesny wygląd.
    -   *Gdy ustawione na „Warehouse Big” (Magazyn Duży):* PDF zostanie zoptymalizowany do użytku magazynowego, potencjalnie z większymi czcionkami i wyraźnymi sekcjami do kompletacji.
    -   *Gdy ustawione na „Retro”:* Twoje pliki PDF przyjmą projekt inspirowany stylem vintage.
-   **Zalecana wartość:** Zacznij od „Clean” lub „Warehouse Big” w zależności od Twojego głównego przypadku użycia (dowód dostawy dla klienta vs. wewnętrzna lista kompletacji). Eksperymentuj, aby znaleźć najlepsze dopasowanie do Twojej marki i potrzeb operacyjnych.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby Twoje dowody dostawy odzwierciedlały nowoczesny, profesjonalny wizerunek marki, możesz wybrać „Clean” lub „Elegant Serif”. Jeśli Twoim głównym celem jest zapewnienie bardzo czytelnej listy kompletacji dla personelu magazynu, „Warehouse Big” może być bardziej odpowiedni.

#### **Włącz aktualizacje MyPresta.eu** (`mypresta_updates`)

-   **Co robi to ustawienie:** Kontroluje, czy moduł może sprawdzać i powiadamiać o dostępnych aktualizacjach z MyPresta.eu.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (Tak):* Moduł będzie okresowo sprawdzał nowe wersje, zapewniając, że jesteś na bieżąco z najnowszymi funkcjami, poprawkami błędów i ulepszeniami kompatybilności. Możesz zobaczyć powiadomienia w panelu administracyjnym PrestaShop, gdy dostępna jest aktualizacja.
    -   *Gdy wyłączone (Nie):* Moduł nie będzie sprawdzał aktualizacji. Będziesz musiał ręcznie sprawdzać swoje konto MyPresta.eu pod kątem nowych wersji.
-   **Zalecana wartość:** **Tak**. Utrzymywanie modułów w aktualności jest kluczowe dla bezpieczeństwa, wydajności i kompatybilności z nowymi wersjami PrestaShop.
-   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia, że zawsze używasz najbardziej stabilnej i bogatej w funkcje wersji modułu, bez konieczności ciągłego ręcznego sprawdzania.

#### **Wersja aktualizacji** (`update_`) i **Wartość wersji aktualizacji** (`updatev_`)

-   **Co robią te ustawienia:** Są to wewnętrzne ustawienia używane przez moduł do zarządzania mechanizmem aktualizacji. Przechowują informacje o najnowszej dostępnej wersji lub aktualnie zainstalowanej wersji.
-   **Efekt zmiany tego ustawienia:** Te ustawienia **nie są przeznaczone do ręcznej zmiany** przez sprzedawcę. Zmiana ich może zakłócić zdolność modułu do prawidłowego sprawdzania i stosowania aktualizacji.
-   **Zalecana wartość:** Pozostaw te ustawienia bez zmian. Są one zarządzane automatycznie przez moduł.
-   **Scenariusz / przykład dla sprzedawcy:** Zazwyczaj nie będziesz wchodzić w interakcję z tymi ustawieniami. Są one częścią wewnętrznej logiki aktualizacji modułu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł dodaje nowe pozycje menu w sekcji **Zamówienia** w Panelu administracyjnym PrestaShop, umożliwiając zarządzanie kategoriami i elementami listy kontrolnej magazynu.

#### **Nazwa ekranu: Kategorie listy kontrolnej**

-   **Lokalizacja menu:** Panel administracyjny > Zamówienia > **Kategorie listy kontrolnej**
-   **Dostępne działania i ustawienia:** Ten ekran umożliwia tworzenie, edytowanie i usuwanie kategorii dla listy kontrolnej magazynu. Pomyśl o kategoriach jako o logicznych grupach dla pozycji listy kontrolnej (np. „Jakość opakowania”, „Weryfikacja produktu”, „Dokumenty wysyłkowe”).
    -   **Dodawanie nowej kategorii:** Kliknij „Dodaj nową kategorię”, aby zdefiniować nową grupę. Zazwyczaj podajesz nazwę kategorii (np. „Inspekcja produktu”).
    -   **Edytowanie/usuwanie kategorii:** Możesz modyfikować istniejące kategorie lub usuwać je, jeśli nie są już potrzebne.
-   **Efekt zmian:**
    -   *Dodanie kategorii:* Tworzy nową sekcję, pod którą można później dodawać konkretne elementy listy kontrolnej.
    -   *Modyfikacja kategorii:* Zmienia nazwę lub właściwości istniejącej kategorii.
    -   *Usunięcie kategorii:* Usuwa kategorię i wszystkie powiązane elementy listy kontrolnej z systemu. Nie będzie to już pojawiać się na generowanych plikach PDF.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zacznij od zdefiniowania szerokich kategorii, które odzwierciedlają Twój proces magazynowy. Na przykład: „Dokładność zamówienia”, „Integralność opakowania”, „Dokumentacja”.
    2.  Upewnij się, że nazwy kategorii są jasne i opisowe dla Twojego personelu.

#### **Nazwa ekranu: Elementy listy kontrolnej**

-   **Lokalizacja menu:** Panel administracyjny > Zamówienia > **Elementy listy kontrolnej**
-   **Dostępne działania i ustawienia:** Ten ekran służy do definiowania rzeczywistych pozycji, które pojawią się na liście kontrolnej magazynu w pliku PDF. Każdy element może być przypisany do wcześniej utworzonej kategorii.
    -   **Dodawanie nowego elementu:** Kliknij „Dodaj nowy element”. Określisz:
        -   **Nazwa:** Tekst pozycji listy kontrolnej (np. „Wszystkie pozycje obecne i rozliczone?”).
        -   **Kategoria:** Przypisz ją do jednej z zdefiniowanych kategorii (np. „Dokładność zamówienia”).
        -   **Aktywny:** Czy ten element powinien pojawić się na liście kontrolnej.
    -   **Edytowanie/usuwanie elementów:** Modyfikuj lub usuwaj pojedyncze pozycje listy kontrolnej.
-   **Efekt zmian:**
    -   *Dodanie elementu:* Nowa pozycja pojawi się na wygenerowanej liście kontrolnej PDF w przypisanej kategorii.
    -   *Modyfikacja elementu:* Zmienia tekst lub kategorię istniejącej pozycji listy kontrolnej.
    -   *Usunięcie elementu:* Usuwa pozycję z listy kontrolnej w plikach PDF.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Po skonfigurowaniu kategorii, wypełnij je konkretnymi, możliwymi do wykonania pozycjami listy kontrolnej.
    2.  Przykłady: „Ilość produktu zgodna z zamówieniem?”, „Kruche przedmioty odpowiednio zabezpieczone?”, „Etykieta wysyłkowa poprawna?”, „Faktura dołączona?”.
    3.  Regularnie przeglądaj i aktualizuj elementy listy kontrolnej, aby odzwierciedlały zmiany w Twoich produktach, opakowaniach lub procedurach wysyłki.

#### **Nazwa ekranu: Lista zamówień (z przyciskiem eksportu)**

-   **Lokalizacja menu:** Panel administracyjny > Zamówienia > **Zamówienia**
-   **Dostępne działania i ustawienia:** Ten moduł integruje się bezpośrednio ze standardową listą zamówień PrestaShop. Znajdziesz nowe przyciski lub opcje do generowania plików PDF dla pojedynczych zamówień lub potencjalnie masowo.
    -   **Eksport pojedynczego zamówienia:** Podczas przeglądania konkretnego zamówienia w Panelu administracyjnym zobaczysz nowy przycisk (np. „Eksportuj PDF” lub „Drukuj listę kompletacji”), który umożliwia wygenerowanie dostosowanego pliku PDF dla tego zamówienia.
    -   **Eksport masowy zamówień:** (W zależności od wersji modułu i wersji PrestaShop) Możesz być w stanie wybrać wiele zamówień z listy zamówień i wygenerować dla nich pliki PDF jednocześnie.
-   **Efekt zmian:** Kliknięcie tych przycisków spowoduje pobranie dokumentu PDF na Twój komputer, sformatowanego zgodnie z wybranym szablonem i zawierającego Twoją niestandardową listę kontrolną.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Po złożeniu i zatwierdzeniu zamówienia przejdź do listy zamówień.
    2.  Otwórz konkretne zamówienie, które musisz zrealizować.
    3.  Kliknij przycisk „Eksportuj PDF”, aby wygenerować listę kompletacji/dowód dostawy z listą kontrolną.
    4.  Wydrukuj plik PDF i przekaż go personelowi magazynu do realizacji.
    5.  Personel używa pliku PDF do kompletowania pozycji, weryfikacji dokładności za pomocą listy kontrolnej i potencjalnie zbierania podpisów przed pakowaniem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Szablon PDF | Clean / Warehouse Big | Wybiera wizualny układ i projekt generowanych dokumentów PDF. |
| **Konfiguracja modułu** | Włącz aktualizacje MyPresta.eu | Tak | Umożliwia modułowi sprawdzanie i powiadamianie o nowych wersjach. |
| **Kategorie listy kontrolnej** | Dodaj/Edytuj/Usuń kategorię | N/A | Zarządza logicznymi grupami dla pozycji listy kontrolnej magazynu. |
| **Elementy listy kontrolnej** | Dodaj/Edytuj/Usuń element | N/A | Definiuje konkretne pozycje, które pojawiają się na liście kontrolnej magazynu w pliku PDF. |
| **Lista zamówień / Widok zamówienia** | Przycisk Eksportuj PDF | N/A | Generuje dokument PDF dla wybranych zamówień, używając skonfigurowanego szablonu i listy kontrolnej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Plik PDF wygląda dziwnie lub ma problemy z formatowaniem. Co powinienem zrobić?**
O:

1.  **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Przewiń do „Pamięć podręczna” i kliknij „Wyczyść pamięć podręczną”. Czasami stare pliki szablonów mogą powodować problemy z wyświetlaniem.
2.  **Wypróbuj inny szablon PDF:** W konfiguracji modułu spróbuj wybrać inny „Szablon PDF”, aby sprawdzić, czy problem dotyczy konkretnego układu.
3.  **Sprawdź konflikty z motywem:** Jeśli używasz mocno dostosowanego motywu, może on zawierać CSS lub JS, które kolidują. Tymczasowo przełącz się na domyślny motyw PrestaShop (np. Classic) i przetestuj ponownie. Jeśli działa, Twój motyw może wymagać dostosowania.
4.  **Skontaktuj się z pomocą techniczną:** Jeśli problemy nadal występują, zbierz zrzuty ekranu i szczegóły, a następnie skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Moje niestandardowe pozycje listy kontrolnej nie pojawiają się w pliku PDF.**
O:

1.  **Sprawdź „Kategorie listy kontrolnej”:** Upewnij się, że utworzyłeś kategorie w **Zamówienia > Kategorie listy kontrolnej**.
2.  **Sprawdź „Elementy listy kontrolnej”:** Zweryfikuj, czy dodałeś elementy w **Zamówienia > Elementy listy kontrolnej** i czy są one przypisane do aktywnej kategorii. Upewnij się również, że przełącznik „Aktywny” dla każdego elementu jest ustawiony na „Tak”.
3.  **Konfiguracja modułu:** Upewnij się, że moduł jest prawidłowo skonfigurowany i zapisany.

**P: Nie widzę przycisku „Eksportuj PDF” na stronach moich zamówień.**
O:

1.  **Moduł zainstalowany i włączony:** Sprawdź dwukrotnie, czy moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
2.  **Uprawnienia:** Upewnij się, że Twój profil pracownika ma niezbędne uprawnienia do dostępu i korzystania z tego modułu. Przejdź do **Zaawansowane > Zespół > Profile** i sprawdź uprawnienia dla profilu przypisanego do Twojego konta pracownika.
3.  **Wersja PrestaShop:** Potwierdź, że Twoja wersja PrestaShop jest kompatybilna (1.7.x, 8.x, 9.x).
4.  **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).

**P: Czy mogę dalej dostosowywać szablony PDF (np. dodać moje logo, zmienić czcionki)?**
O: Tak, ale wymaga to wiedzy technicznej. Moduł udostępnia kilka szablonów, ale do głębokiej personalizacji (takiej jak dodanie konkretnego logo, zmiana czcionek lub zmiana układu poza tym, co oferują ustawienia modułu) będziesz musiał:

1.  **Zidentyfikować plik szablonu:** Zlokalizuj plik `.tpl` dla wybranego szablonu PDF w katalogu `pdf/en/` modułu.
2.  **Edytować szablon:** Wymaga to edycji kodu szablonu Smarty i potencjalnie HTML/CSS. Jest to zadanie dla webmastera lub programisty.
3.  **Rozważyć niestandardowy szablon:** W przypadku znaczących zmian często lepiej jest utworzyć nowy niestandardowy szablon, zamiast modyfikować podstawowe pliki modułu, aby zapewnić, że Twoje zmiany nie zostaną nadpisane podczas aktualizacji modułu.

**P: Moduł nie sprawdza aktualizacji.**
O:

1.  **Włącz sprawdzanie aktualizacji:** Przejdź do strony konfiguracji modułu (**Moduły > Menedżer modułów > Konfiguruj** dla „Eksport PDF zamówień i lista kontrolna magazynu”) i upewnij się, że „Włącz aktualizacje MyPresta.eu” jest ustawione na „Tak”.
2.  **Łączność z serwerem:** Upewnij się, że Twój serwer ma wychodzący dostęp do Internetu, aby połączyć się z serwerami aktualizacji MyPresta.eu. Może to wymagać sprawdzenia ustawień zapory sieciowej lub konfiguracji proxy u Twojego dostawcy hostingu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Eksport PDF zamówień i lista kontrolna magazynu” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), głównie rozszerzając `Module` dla swojej podstawowej funkcjonalności i `AdminController` dla ekranów zarządzania w Panelu administracyjnym. Wykorzystuje `ObjectModel` do zarządzania niestandardowymi encjami bazy danych (kategorie i elementy listy kontrolnej). Generowanie PDF jest obsługiwane przez dedykowaną klasę (`OrderPdfGenerator`), która wykorzystuje szablony Smarty do renderowania zawartości PDF, prawdopodobnie integrując się z biblioteką taką jak Dompdf lub TCPDF (chociaż konkretna biblioteka nie jest wyraźnie określona, struktura `.tpl` sugeruje silnik renderowania). Haki są używane do integracji funkcjonalności modułu z Panelu administracyjnego PrestaShop, w szczególności do dodawania przycisków eksportu PDF do stron zamówień.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery administracyjne Back-Office

-   `orderexportpdf/controllers/admin/AdminOrderExportChecklistCategoriesController.php`

    -   **Nazwa klasy:** `AdminOrderExportChecklistCategoriesController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza operacjami CRUD (Create, Read, Update, Delete) dla obiektów `OrderExportChecklistCategory`. Zapewnia interfejs Panelu administracyjnego do listowania, dodawania, edytowania i usuwania kategorii listy kontrolnej. Ten kontroler jest mapowany do pozycji menu „Kategorie listy kontrolnej” w sekcji „Zamówienia”.
    -   **Nazwa zakładki:** Checklist Categories
    -   **Zarządzana encja:** `OrderExportChecklistCategory` (mapowana do tabeli `ps_orderexport_checklist_cat`).
-   `orderexportpdf/controllers/admin/AdminOrderExportChecklistElementsController.php`

    -   **Nazwa klasy:** `AdminOrderExportChecklistElementsController`
    -   **Klasa nadrzędna:** `ModuleAdminController`
    -   **Odpowiedzialność:** Zarządza operacjami CRUD dla obiektów `OrderExportChecklistElement`. Zapewnia interfejs Panelu administracyjnego do listowania, dodawania, edytowania i usuwania pojedynczych elementów listy kontrolnej, umożliwiając przypisanie do kategorii. Ten kontroler jest mapowany do pozycji menu „Elementy listy kontrolnej” w sekcji „Zamówienia”.
    -   **Nazwa zakładki:** Checklist Elements
    -   **Zarządzana encja:** `OrderExportChecklistElement` (mapowana do tabeli `ps_orderexport_checklist_elem`).
-   `orderexportpdf/controllers/admin/index.php`

    -   **Odpowiedzialność:** Jest to zazwyczaj pusty plik lub plik zawierający instrukcję bezpieczeństwa `die()` zapobiegającą bezpośredniemu listowaniu katalogów. Sam w sobie nie zawiera logiki kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `orderexportpdf/classes/index.php`

    -   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop, zazwyczaj zawiera `<?php exit;` aby zapobiec listowaniu katalogów.
-   `orderexportpdf/classes/OrderExport.php`

    -   **Nazwa klasy:** `OrderExport`
    -   **Klasa nadrzędna:** `Object` (prawdopodobnie, lub niestandardowa klasa bazowa)
    -   **Odpowiedzialność:** Ta klasa prawdopodobnie zawiera metody pomocnicze lub podstawową logikę związaną z ogólnym procesem eksportu zamówień, być może obsługując pobieranie danych, formatowanie lub interakcję z klasą generowania PDF. Może nie być `ObjectModel`, ale klasą narzędziową.
-   `orderexportpdf/classes/OrderExportChecklistCategory.php`

    -   **Nazwa klasy:** `OrderExportChecklistCategory`
    -   **Klasa nadrzędna:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_orderexport_checklist_cat`
    -   **Pola `$definition`:** Definiuje strukturę kategorii listy kontrolnej, w tym pola takie jak `id_orderexport_checklist_cat`, `name` (wielojęzyczne), `active`, `position`.
    -   **Kluczowe metody publiczne:** Standardowe metody `ObjectModel` (`add`, `update`, `delete`, `getFields`, `validateFields`, `validateController`). Może zawierać metody do pobierania wszystkich aktywnych kategorii lub kategorii według ID.
-   `orderexportpdf/classes/OrderExportChecklistElement.php`

    -   **Nazwa klasy:** `OrderExportChecklistElement`
    -   **Klasa nadrzędna:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_orderexport_checklist_elem`
    -   **Pola `$definition`:** Definiuje strukturę elementu listy kontrolnej, w tym pola takie jak `id_orderexport_checklist_elem`, `id_orderexport_checklist_cat` (klucz obcy), `name` (wielojęzyczne), `active`, `position`.
    -   **Kluczowe metody publiczne:** Standardowe metody `ObjectModel`. Może zawierać metody do pobierania elementów według kategorii lub wszystkich aktywnych elementów.
-   `orderexportpdf/classes/OrderPdfGenerator.php`

    -   **Nazwa klasy:** `OrderPdfGenerator`
    -   **Klasa nadrzędna:** Prawdopodobnie `Object` lub niestandardowa klasa bazowa.
    -   **Odpowiedzialność:** Jest to podstawowa klasa odpowiedzialna za generowanie dokumentów PDF. Przyjmuje ID zamówienia, wybrany szablon i dane listy kontrolnej, a następnie renderuje zawartość do formatu PDF. Prawdopodobnie wewnętrznie używa zewnętrznej biblioteki PDF (np. Dompdf, mPDF).
    -   **Kluczowe metody publiczne:** `generatePdf($orderId, $templateName, $checklistData)`, `renderTemplate($templatePath, $data)`, `downloadPdf()`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `orderexportpdf/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`

    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Prawdopodobnie obsługuje dynamiczne zarządzanie szablonami PDF w interfejsie konfiguracji modułu. Może to obejmować wywołania AJAX do zapisywania ustawień szablonów, podglądu szablonów lub przełączania między różnymi opcjami szablonów.
-   `orderexportpdf/views/js/order-list-legacy.js`

    -   **Zakres:** Panel administracyjny (dla PrestaShop 1.7.x lub starszych wersji używających starszego JS).
    -   **Odpowiedzialność:** Integruje funkcjonalność przycisku eksportu PDF z widokiem listy zamówień w Panelu administracyjnym PrestaShop dla starszych wersji PrestaShop. Wiąże zdarzenia kliknięcia z przyciskami, potencjalnie wykonuje wywołania AJAX w celu wywołania generowania PDF i obsługuje pobieranie wygenerowanego pliku PDF.
-   `orderexportpdf/views/js/order-list-modern.js`

    -   **Zakres:** Panel administracyjny (dla PrestaShop 8.x, 9.x lub nowszych wersji używających nowoczesnego JS).
    -   **Odpowiedzialność:** Podobnie jak `order-list-legacy.js`, ale dostosowany do nowszych interfejsów Panelu administracyjnego PrestaShop i potencjalnie wykorzystujący nowoczesne praktyki JavaScript (np. ES6, zasoby skompilowane przez Webpack). Zapewnia, że przycisk eksportu PDF jest poprawnie wyświetlany i funkcjonalny na liście zamówień i stronach widoku pojedynczego zamówienia.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `orderexportpdf/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`

    -   **Zakres:** Stylizacja formularzy administracyjnych Panelu administracyjnego.
    -   **Odpowiedzialność:** Zapewnia stylizację interfejsu konfiguracji modułu, w szczególności dla sekcji menedżera szablonów PDF. Może to obejmować style dla przycisków, rozwijanych list, obszarów podglądu lub elementów formularza związanych z wyborem szablonu.
-   `orderexportpdf/views/css/order-export.css`

    -   **Zakres:** Stylizacja formularzy administracyjnych Panelu administracyjnego.
    -   **Odpowiedzialność:** Ogólna stylizacja dla komponentów Panelu administracyjnego modułu, takich jak ekrany zarządzania kategoriami i elementami listy kontrolnej, lub potencjalnie stylizacja dla dodanych przycisków na stronach zamówień.
    -   **Kluczowe selektory klas CSS:** Programiści mogą sprawdzić wygenerowany kod HTML pod kątem klas takich jak `.orderexportpdf-button`, `.orderexport-checklist-table` itp., aby nadpisać style w swoim niestandardowym motywie administracyjnym.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony haków (`views/templates/hook/`)

-   `orderexportpdf/lib/pdfTemplatesManager/views/buttonManager.tpl`

    -   **Hak:** Prawdopodobnie renderowany w haku w konfiguracji modułu lub na stronie zamówienia administracyjnego w celu wyświetlenia przycisków związanych z zarządzaniem szablonami (np. „Zarządzaj szablonami”, „Utwórz nowy szablon”).
    -   **Wynik:** Kod HTML dla przycisków lub linków do zarządzania szablonami PDF.
-   `orderexportpdf/lib/pdfTemplatesManager/views/createTemplateForm.tpl`

    -   **Hak:** Wewnętrzny dla menedżera szablonów modułu, wyświetlany podczas tworzenia nowego szablonu PDF.
    -   **Wynik:** Formularz HTML do definiowania właściwości nowego szablonu PDF.
-   `orderexportpdf/lib/pdfTemplatesManager/views/editTemplateForm.tpl`

    -   **Hak:** Wewnętrzny dla menedżera szablonów modułu, wyświetlany podczas edycji istniejącego szablonu PDF.
    -   **Wynik:** Formularz HTML do modyfikowania właściwości istniejącego szablonu PDF.
-   `orderexportpdf/lib/pdfTemplatesManager/views/mainForm.tpl`

    -   **Hak:** Główny formularz konfiguracji modułu (np. metoda `getContent()`).
    -   **Wynik:** Główny formularz HTML zawierający rozwijaną listę wyboru „Szablon PDF” i inne ustawienia na poziomie modułu.
-   `orderexportpdf/lib/pdfTemplatesManager/views/selectInput.tpl`

    -   **Hak:** Wielokrotnego użytku częściowy szablon, prawdopodobnie zawarty w `mainForm.tpl` lub innych formularzach, do renderowania rozwijanego pola (`<select>`) do wyboru szablonów.
    -   **Wynik:** Kod HTML dla elementu `<select>` wypełnionego dostępnymi szablonami PDF.
-   `orderexportpdf/pdf/en/*.tpl` (np. `blue-line-dompdf.tpl`, `boxed-layout-dompdf.tpl`, `clean-dompdf.tpl`, `warehouse-big-dompdf.tpl` itp.)

    -   **Hak:** To **nie są** szablony haków PrestaShop. Są to rzeczywiste **szablony układu PDF** używane przez `OrderPdfGenerator` do renderowania zawartości listy kompletacji/dowodu dostawy. Są one wybierane za pomocą konfiguracji modułu.
    -   **Wynik:** Struktura HTML/CSS, która zostanie przekonwertowana na dokument PDF. Te szablony zawierają miejsca na szczegóły zamówienia, listy produktów, informacje o kliencie i niestandardową listę kontrolną.
    -   **Uwaga:** Sufiks `dompdf` sugeruje użycie biblioteki Dompdf do konwersji HTML na PDF.
-   `orderexportpdf/pdf/fr/kids-play.tpl`

    -   **Hak:** Podobnie jak szablony `en`, ale francuska wersja układu PDF „kids-play”. Wskazuje to na wielojęzyczne wsparcie dla szablonów PDF.
-   `orderexportpdf/pdf/en/order-export.tpl`

    -   **Hak:** Może to być ogólny szablon bazowy lub szablon awaryjny do generowania PDF.
    -   **Wynik:** Ogólna struktura PDF eksportu zamówienia.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

-   `ps_orderexport_checklist_cat`: Przechowuje informacje o niestandardowych kategoriach listy kontrolnej.

    -   `id_orderexport_checklist_cat` (Klucz główny, INT)
    -   `name` (VARCHAR, Wielojęzyczne): Nazwa kategorii listy kontrolnej.
    -   `active` (TINYINT): Czy kategoria jest aktywna.
    -   `position` (INT): Kolejność wyświetlania kategorii.
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_orderexport_checklist_elem`: Przechowuje informacje o poszczególnych elementach listy kontrolnej.

    -   `id_orderexport_checklist_elem` (Klucz główny, INT)
    -   `id_orderexport_checklist_cat` (Klucz obcy do `ps_orderexport_checklist_cat`, INT): Kategoria, do której należy ten element.
    -   `name` (VARCHAR, Wielojęzyczne): Tekst pozycji listy kontrolnej.
    -   `active` (TINYINT): Czy element jest aktywny.
    -   `position` (INT): Kolejność wyświetlania elementów w kategorii.
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_configuration`: Moduł przechowuje tutaj swoje główne ustawienia konfiguracyjne.

    -   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: (Ustawienie podstawowe PrestaShop, nie specyficzne dla modułu)
    -   `MYPRESTA_UPDATES`: (Ustawienie modułu) Przechowuje stan sprawdzania aktualizacji (1 dla włączonego, 0 dla wyłączonego).
    -   `UPDATE_`: (Ustawienie modułu) Wewnętrzne śledzenie wersji aktualizacji.
    -   `UPDATEV_`: (Ustawienie modułu) Wewnętrzna wartość wersji aktualizacji.
    -   `ORDEREXPORTPDF_TEMPLATE`: (Ustawienie modułu) Przechowuje nazwę aktualnie wybranego szablonu PDF.

#### Tabela zarejestrowanych haków

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy AdminController ładuje swoje zasoby. | Wstrzykuje specyficzne dla modułu CSS (`order-export.css`, `pdfTemplatesManager.css`) i JavaScript (`order-list-legacy.js`, `order-list-modern.js`, `pdfTemplatesManager.js`) do Panelu administracyjnego, w szczególności dla stron zamówień i konfiguracji modułu. |
| `displayAdminOrder` | Wykonywany na stronie widoku pojedynczego zamówienia w Panelu administracyjnym. | Renderuje przycisk „Eksportuj PDF” lub podobny widżet na stronie szczegółów zamówienia, umożliwiając generowanie PDF dla pojedynczego zamówienia. |
| `actionGetAdminOrderButtons` | Wykonywany, aby umożliwić modułom dodawanie niestandardowych przycisków do widoku zamówienia administracyjnego. | Zapewnia mechanizm do wstrzykiwania niestandardowych przycisków (takich jak „Eksportuj PDF”) do widoku zamówienia PrestaShop 1.7+, zapewniając kompatybilność z nowoczesnym interfejsem użytkownika. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Eksport PDF zamówień i lista kontrolna magazynu” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub konfiguracji modułu.
