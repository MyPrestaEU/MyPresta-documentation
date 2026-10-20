---
title: "Related Products Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Related Products Pro od MyPresta.eu."
sidebar:
  label: "Related Products Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Related Products Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/related-products-pro/)
>
> ---


# Related Products Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane i są domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Related Products Pro > Konfiguruj)

Jest to główny ekran konfiguracji, na którym będziesz zarządzać wszystkimi aspektami list powiązanych produktów. Interfejs został zaprojektowany tak, aby był intuicyjny, umożliwiając łatwe tworzenie, edytowanie i przypisywanie powiązanych produktów.

Strona konfiguracji zazwyczaj przedstawia listę istniejących list powiązanych produktów (jeśli takie istnieją) oraz opcje tworzenia nowych lub zarządzania ustawieniami globalnymi.

#### **Główne elementy interfejsu:**

-   **Lista istniejących bloków powiązanych produktów:** Ta tabela pokaże wszystkie utworzone listy powiązanych produktów. Dla każdej listy zobaczysz szczegóły, takie jak jej nazwa, produkty, do których jest przypisana, oraz opcje edycji lub usunięcia.
-   **Przycisk „Dodaj nowy blok powiązanych produktów”:** Kliknij, aby utworzyć zupełnie nowy zestaw powiązanych produktów.
-   **Ustawienia globalne / Preferencje:** (Jeśli dostępne) Te ustawienia mogą kontrolować ogólne opcje wyświetlania lub domyślne zachowania dla wszystkich bloków powiązanych produktów.

#### **Podczas dodawania/edycji bloku powiązanych produktów:**

Po kliknięciu, aby dodać nowy blok lub edytować istniejący, zazwyczaj zobaczysz formularz z następującymi ustawieniami:

1.  **Nazwa bloku:**

    -   **Co robi to ustawienie:** Jest to wewnętrzna nazwa Twojej listy powiązanych produktów, widoczna tylko w Panelu administracyjnym. Pomaga zidentyfikować różne listy.
    -   **Efekt zmiany tego ustawienia:** Zmienia etykietę dla tego konkretnego bloku powiązanych produktów w Twoim panelu administracyjnym.
    -   **Zalecana wartość:** Użyj opisowej nazwy, np. „Produkt X - Uzupełniające elementy”, „Kategoria Y - Bestsellery”.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz nazwać listę „Sukienki letnie - Pasujące sandały”, aby łatwo ją później znaleźć.
2.  **Lokalizacja wyświetlania (Hook):**

    -   **Co robi to ustawienie:** Określa, gdzie na stronie produktu pojawi się ten konkretny blok powiązanych produktów. Wybierasz „hook” PrestaShop, który jest wyznaczonym obszarem wyświetlania.
    -   **Efekt zmiany tego ustawienia:** Powiązane produkty przeniosą się do wybranej lokalizacji na stronie produktu w sklepie.
    -   **Zalecana wartość:** Eksperymentuj z różnymi hookami w zależności od Twojego szablonu. Typowe wybory to `displayProductExtraContent` (często w pobliżu opisu produktu), `displayProductFooter` (na dole strony produktu) lub `displayRightColumnProduct` (jeśli Twój szablon ma prawą kolumnę na stronach produktów).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby powiązane produkty pojawiały się tuż pod głównym obrazem i opisem produktu, możesz wybrać `displayProductExtraContent`. Jeśli wolisz je na samym dole strony, `displayProductFooter` byłby lepszy.
3.  **Produkty do wyświetlenia:**

    -   **Co robi to ustawienie:** Tutaj definiujesz, *które* produkty zostaną pokazane w tym bloku powiązanych produktów. Zazwyczaj będziesz mieć kilka opcji:
        -   **Konkretne produkty (ręczny wybór):**
            -   **Co to robi:** Pozwala ręcznie wyszukać i wybrać pojedyncze produkty do włączenia do listy.
            -   **Efekt:** Pojawią się tylko produkty, które wyraźnie wybierzesz.
            -   **Zalecane:** Używaj do wysoce spersonalizowanych rekomendacji.
            -   **Scenariusz:** Dla konkretnego aparatu możesz ręcznie wybrać statyw, torbę na aparat i dodatkowy obiektyw.
        -   **Produkty z wybranych kategorii:**
            -   **Co to robi:** Wyświetla produkty z jednej lub więcej wybranych kategorii.
            -   **Efekt:** Lista będzie dynamicznie pokazywać produkty z tych kategorii.
            -   **Zalecane:** Dobre do pokazywania powiązanych produktów w ramach linii produktów lub działu.
            -   **Scenariusz:** Dla „Koszuli męskiej” możesz wybrać kategorie „Spodnie męskie” i „Akcesoria męskie”.
        -   **Nowe produkty:**
            -   **Co to robi:** Automatycznie wyświetla najnowsze produkty dodane do Twojego sklepu.
            -   **Efekt:** Lista zawsze będzie pokazywać Twoje najnowsze dodatki.
            -   **Zalecane:** Świetne do promowania nowości.
            -   **Scenariusz:** Użyj tego bloku, aby wyróżnić swoją najnowszą kolekcję biżuterii.
        -   **Bestsellery:**
            -   **Co to robi:** Automatycznie wyświetla najlepiej sprzedające się produkty w Twoim sklepie.
            -   **Efekt:** Lista będzie dynamicznie aktualizować się, aby pokazywać Twoje najpopularniejsze produkty.
            -   **Zalecane:** Doskonałe do dowodu społecznego i promowania popularnych produktów.
            -   **Scenariusz:** Pokaż produkty „Klienci kupili również” na podstawie ogólnej popularności sklepu.
    -   **Liczba produktów do wyświetlenia:**
        -   **Co to robi:** Kontroluje, ile powiązanych produktów jest wyświetlanych w bloku.
        -   **Efekt:** Ogranicza widoczne produkty.
        -   **Zalecane:** 4-8 produktów dla czystego wyglądu, w zależności od układu.
        -   **Scenariusz:** Wyświetl 5 powiązanych produktów, aby sekcja była zwięzła.
4.  **Przypisz do produktów:**

    -   **Co robi to ustawienie:** To jest kluczowe – określa, *na których stronach produktów* pojawi się ten konkretny blok powiązanych produktów.
    -   **Efekt zmiany tego ustawienia:** Blok powiązanych produktów będzie widoczny tylko na stronach produktów, które tutaj wybierzesz.
    -   **Zalecana wartość:** Możesz przypisać go do:
        -   **Wszystkie produkty:** Jeśli jest to ogólny blok „Bestsellery” lub „Nowości”.
        -   **Konkretne produkty (ręczny wybór):** Dla wysoce ukierunkowanych rekomendacji.
        -   **Produkty z wybranych kategorii:** Aby zastosować blok do całego zakresu kategorii.
    -   **Scenariusz / przykład dla sprzedawcy:** Tworzysz listę „Akcesoria do iPhone’a”. Następnie przypisujesz ten blok tylko do stron produktów iPhone’a. Lub tworzysz blok „Produkty z letniej wyprzedaży” i przypisujesz go do wszystkich produktów w kategorii „Kolekcja letnia”.
5.  **Typ / szablon wyświetlania:**

    -   **Co robi to ustawienie:** Pozwala wybrać układ wizualny lub szablon, w jaki sposób powiązane produkty są wyświetlane (np. siatka, karuzela, lista, tabela). Moduł często zawiera różne szablony, z których niektóre mogą być zoptymalizowane pod kątem konkretnych szablonów (takich jak szablony Panda, Warehouse, Zone).
    -   **Efekt zmiany tego ustawienia:** Zmienia wizualną prezentację powiązanych produktów w sklepie.
    -   **Zalecana wartość:** Eksperymentuj, aby znaleźć najlepsze dopasowanie do Twojego szablonu i wybranego hooka. Karuzela jest często dobra do oszczędzania miejsca, podczas gdy siatka może być lepsza dla dedykowanej sekcji.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz eleganckiego, oszczędzającego miejsce wyświetlacza, możesz wybrać szablon „karuzela”. Jeśli masz dużo miejsca i chcesz pokazać więcej szczegółów, „siatka” lub „tabela” mogą być lepsze. Niektóre szablony mogą być specjalnie nazwane dla popularnych szablonów (np. `panda-blocksProductsCart.tpl`), aby zapewnić lepszą integrację.
6.  **Ustawienia karuzeli (jeśli dotyczy):**

    -   **Co robi to ustawienie:** Jeśli wybierzesz typ wyświetlania karuzeli, możesz mieć dodatkowe opcje, takie jak:
        -   **Autoodtwarzanie:** Czy karuzela przewija się automatycznie.
        -   **Pętla:** Czy karuzela powtarza się od początku po ostatnim elemencie.
        -   **Elementy na widok:** Ile produktów jest widocznych jednocześnie w karuzeli.
        -   **Strzałki/kropki nawigacyjne:** Czy wyświetlać kontrolki do ręcznego przewijania.
    -   **Efekt zmiany tego ustawienia:** Kontroluje zachowanie i wygląd karuzeli produktów.
    -   **Zalecana wartość:** Autoodtwarzanie może być angażujące, ale może również rozpraszać. Rozważ swoją publiczność. 3-5 elementów na widok to często dobry balans.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz subtelnej karuzeli, która automatycznie przewija się co 5 sekund, pokazując 4 produkty jednocześnie, ze strzałkami nawigacyjnymi dla użytkowników, którzy chcą przeglądać ręcznie.

#### **Zapisywanie zmian:**

Zawsze pamiętaj, aby kliknąć przycisk „Zapisz” lub „Aktualizuj” po wprowadzeniu jakichkolwiek zmian w bloku powiązanych produktów, aby upewnić się, że Twoje ustawienia zostały zastosowane.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | **Nazwa bloku** | Opisowa (np. „Produkt X - Cross-Sell”) | Wewnętrzna etykieta do identyfikacji bloku powiązanych produktów w Panelu administracyjnym. |
| | **Lokalizacja wyświetlania (Hook)** | `displayProductExtraContent` lub `displayProductFooter` | Określa, gdzie blok pojawia się na stronie produktu w sklepie. |
| | **Produkty do wyświetlenia: Konkretne produkty** | Ręczny wybór | Pokazuje tylko ręcznie wybrane produkty. Najlepsze dla wysoce spersonalizowanych rekomendacji. |
| | **Produkty do wyświetlenia: Z wybranych kategorii** | Wybierz odpowiednie kategorie | Dynamicznie pokazuje produkty z wybranych kategorii. Dobre dla powiązanych linii produktów. |
| | **Produkty do wyświetlenia: Nowe produkty** | Automatycznie wypełniane | Automatycznie pokazuje najnowsze produkty w Twoim sklepie. Świetne dla nowości. |
| | **Produkty do wyświetlenia: Bestsellery** | Automatycznie wypełniane | Automatycznie pokazuje najlepiej sprzedające się produkty w Twoim sklepie. Doskonałe dla dowodu społecznego. |
| | **Liczba produktów do wyświetlenia** | 4-8 | Ogranicza liczbę produktów wyświetlanych w bloku dla czystego układu. |
| | **Przypisz do produktów: Wszystkie produkty** | N/A | Wyświetla blok na każdej stronie produktu. Używaj do ogólnych rekomendacji. |
| | **Przypisz do produktów: Konkretne produkty** | Ręczny wybór | Wyświetla blok tylko na wybranych stronach produktów. Dla ukierunkowanych cross-sellów. |
| | **Przypisz do produktów: Z wybranych kategorii** | Wybierz odpowiednie kategorie | Wyświetla blok na stronach produktów w wybranych kategoriach. |
| | **Typ / szablon wyświetlania** | `accessories.tpl` lub specyficzny dla szablonu | Kontroluje układ wizualny (siatka, karuzela, lista). Wybierz na podstawie szablonu i hooka. |
| | **Ustawienia karuzeli (Autoodtwarzanie, Pętla, Elementy na widok, Nawigacja)** | Różne, często włączone | Kontroluje zachowanie wyświetlaczy karuzelowych. Dostosuj do doświadczenia użytkownika. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje powiązane produkty nie wyświetlają się w sklepie.**

-   **O:** Po pierwsze, upewnij się, że moduł jest włączony i skonfigurowany. Sprawdź, czy faktycznie *przypisałeś* blok powiązanych produktów do konkretnych produktów lub kategorii, które przeglądasz. Sprawdź również, czy wybrana „Lokalizacja wyświetlania (Hook)” jest faktycznie renderowana przez Twój szablon na stronie produktu. Na koniec wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P2: Powiązane produkty wyglądają dziwnie lub nie pasują do projektu mojego szablonu.**

-   **O:** Jest to często konflikt stylów z Twoim niestandardowym szablonem.
    -   **Rozwiązanie 1:** Wypróbuj różne opcje „Typ / szablon wyświetlania” w konfiguracji modułu. Niektóre szablony są zaprojektowane dla konkretnych popularnych szablonów (np. `panda-blocksProductsCart.tpl`).
    -   **Rozwiązanie 2:** Wyczyść pamięć podręczną przeglądarki i pamięć podręczną Smarty PrestaShop (Zaawansowane > Wydajność).
    -   **Rozwiązanie 3:** Jeśli problem nadal występuje, może to wymagać niestandardowych dostosowań CSS. Jest to zadanie dla webmastera lub programisty (patrz sekcja 7.5).

**P3: Czy mogę mieć wiele bloków powiązanych produktów na tej samej stronie produktu?**

-   **O:** Tak! Moduł jest do tego przeznaczony. Możesz utworzyć kilka odrębnych bloków powiązanych produktów, każdy z własnymi produktami, typem wyświetlania i przypisaną lokalizacją (hookiem). Upewnij się tylko, że umieścisz je w różnych hookach, aby uniknąć nakładania się.

**P4: Jak przetłumaczyć tekst modułu (np. „Powiązane produkty”) na inne języki?**

-   **O:** Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz „Related Products Pro” z rozwijanej listy modułów. Następnie możesz edytować ciągi tekstowe dla każdego języka.

**P5: Karuzela nie działa lub produkty są ułożone pionowo.**

-   **O:** Zazwyczaj wskazuje to na konflikt JavaScript lub brakującą bibliotekę JS.
    -   **Rozwiązanie 1:** Upewnij się, że Twój szablon jest aktualny.
    -   **Rozwiązanie 2:** Wyczyść pamięć podręczną PrestaShop i pamięć podręczną przeglądarki.
    -   **Rozwiązanie 3:** Sprawdź błędy konsoli w narzędziach deweloperskich przeglądarki (F12). Jeśli widzisz błędy JavaScript, może to wskazywać na konflikt z innym modułem lub Twoim szablonem. Wymagałoby to zbadania przez programistę.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółową analizę techniczną modułu „Related Products Pro” dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Related Products Pro” (`ppb`) stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności. Koncentruje się na rozszerzaniu doświadczenia strony produktu w sklepie poprzez wstrzykiwanie niestandardowych list produktów do różnych hooków wyświetlania. Moduł zarządza swoją konfiguracją i danymi powiązanych produktów bezpośrednio w metodzie `getContent()` pliku `index.php`, która obsługuje zarówno renderowanie formularzy, jak i trwałość danych. Wykorzystuje niestandardowy system szablonów do elastycznego wyświetlania w sklepie, w tym specyficzne szablony dla popularnych szablonów. Zasoby JavaScript i CSS są ładowane warunkowo, aby poprawić interfejs użytkownika i zapewnić funkcjonalność karuzeli.

### 4.2 Kontrolery (`controllers/`)

Moduł nie wydaje się używać dedykowanych klas `ModuleFrontController` ani `AdminController`. Całe renderowanie w sklepie jest obsługiwane za pośrednictwem hooków, a konfiguracja w Panelu administracyjnym jest zarządzana w metodzie `getContent()` głównego pliku `index.php`.

### 4.3 Podstawowe klasy i modele (`classes/`)

Moduł nie definiuje niestandardowych klas rozszerzających `ObjectModel` w dedykowanym katalogu `classes/`. Trwałość danych dla konfiguracji powiązanych produktów jest prawdopodobnie obsługiwana bezpośrednio za pomocą `Configuration::updateValue()` lub niestandardowych tabel baz danych zarządzanych w głównym pliku `index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`ppb/lib/searchTool/views/js/autocomplete.js`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wyboru produktów w formularzach konfiguracji modułu, prawdopodobnie do ręcznego wybierania konkretnych produktów do włączenia lub przypisania. Nasłuchuje danych wprowadzanych przez użytkownika w polach tekstowych i sugeruje produkty na podstawie częściowych dopasowań.
-   **`ppb/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Prawdopodobnie część ogólnego narzędzia do zarządzania szablonami Smarty w interfejsie administracyjnym. Może obsługiwać dynamiczne ładowanie, zapisywanie lub podgląd kodu szablonu, prawdopodobnie używane do funkcji tworzenia lub modyfikacji niestandardowych szablonów w module.
-   **`ppb/lib/src/js/lightslider.js`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Jest to biblioteka zewnętrzna do tworzenia responsywnych karuzel treści. Wiąże się z określonymi elementami HTML (prawdopodobnie `<ul>` lub `<div>` z wyznaczoną klasą), aby przekształcić je w slider. Obsługuje zdarzenia dotyku/przeciągania, nawigację, autoodtwarzanie i responsywne dostosowania.
-   **`ppb/views/admin/ppb.js`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Zawiera podstawową logikę JavaScript dla strony konfiguracji modułu w Panelu administracyjnym. Obejmowałoby to nasłuchiwanie zdarzeń przesyłania formularzy, dynamiczne aktualizacje ustawień na podstawie wyborów użytkownika (np. pokazywanie/ukrywanie opcji karuzeli), wywołania AJAX do zapisywania danych i potencjalnie zarządzanie listą bloków powiązanych produktów.
-   **`ppb/views/admin/ppb8.js`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Podobnie jak `ppb.js`, ale prawdopodobnie zawiera specyficzne adaptacje lub dodatkowe funkcjonalności dla środowisk PrestaShop 8.x, uwzględniające zmiany API lub różnice w interfejsie użytkownika w nowszych wersjach PrestaShop.
-   **`ppb/views/js/accessories.js`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Zawiera specyficzny dla sklepu JavaScript dla bloków powiązanych produktów. Może to obejmować logikę inicjalizacji karuzeli `lightslider.js`, obsługę kliknięć produktów lub wszelkie dynamiczne interakcje w wyświetlanych listach powiązanych produktów.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`ppb/css.css`**:
    -   **Zakres:** Zarówno sklep, jak i Panel administracyjny.
    -   **Odpowiedzialność:** Ogólne style dla całego modułu. Może zawierać podstawowe style dla bloków powiązanych produktów lub wspólnych elementów używanych w module.
-   **`ppb/lib/searchTool/views/css/autocomplete.css`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Style dla rozwijanych list autouzupełniania i pól wprowadzania używanych w narzędziu do wyboru produktów w Panelu administracyjnym.
-   **`ppb/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Stylizacja interfejsu zarządzania szablonami Smarty w konfiguracji modułu.
-   **`ppb/lib/src/css/lightslider.css`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Podstawowe style dla karuzeli `lightslider.js`, definiujące jej strukturę, strzałki nawigacyjne, kropki i responsywne zachowanie. Programiści mogą nadpisać te style, aby dopasować je do swojego szablonu.
-   **`ppb/views/admin/ppb.css`**:
    -   **Zakres:** Panel administracyjny.
    -   **Odpowiedzialność:** Specyficzne style dla strony konfiguracji modułu w panelu administracyjnym PrestaShop, zapewniające dobrą integrację z interfejsem użytkownika Panelu administracyjnego PrestaShop.
-   **`ppb/views/css/ppb-table.css`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Stylizacja list powiązanych produktów wyświetlanych w formacie tabelarycznym, prawdopodobnie używana dla specyficznych szablonów „table-list”.
-   **`ppb/views/css/ppb.css`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Podstawowe style dla bloków powiązanych produktów w sklepie, w tym układy kart produktów, odstępy i ogólny wygląd.
-   **`ppb/views/css/ppbcarousell.css`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Dodatkowe lub specyficzne style dla wyświetlania karuzelowego powiązanych produktów, potencjalnie nadpisujące lub rozszerzające `lightslider.css` dla niestandardowej estetyki modułu.
-   **`ppb/views/css/ppb_custom.css`**:
    -   **Zakres:** Sklep.
    -   **Odpowiedzialność:** Prawdopodobnie przeznaczony do niestandardowego CSS zdefiniowanego przez użytkownika lub nadpisań specyficznych dla szablonu, aby dostosować wygląd bloków powiązanych produktów bez modyfikowania podstawowych plików modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł dostarcza bogaty zestaw szablonów, z których wiele jest dostosowanych do konkretnych hooków i popularnych szablonów PrestaShop.

-   **`ppb/lib/searchTool/views/scripts.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Zawiera inicjalizację JavaScript lub konfigurację narzędzia wyszukiwania autouzupełniania używanego w Panelu administracyjnym.
-   **`ppb/lib/smartyTemplatesManager/tpl/example.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Przykładowy szablon, prawdopodobnie używany jako odniesienie lub do demonstrowania możliwości menedżera szablonów Smarty.
-   **`ppb/lib/smartyTemplatesManager/views/buttonManager.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Renderuje przyciski lub kontrolki do zarządzania szablonami w interfejsie administracyjnym.
-   **`ppb/lib/smartyTemplatesManager/views/createTemplateForm.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Renderuje formularz do tworzenia nowych niestandardowych szablonów wyświetlania dla powiązanych produktów.
-   **`ppb/lib/smartyTemplatesManager/views/editTemplateForm.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Renderuje formularz do edycji istniejących niestandardowych szablonów wyświetlania.
-   **`ppb/lib/smartyTemplatesManager/views/mainForm.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Główny formularz dla menedżera szablonów Smarty, prawdopodobnie wyświetlający listę szablonów i oferujący opcje.
-   **`ppb/lib/smartyTemplatesManager/views/selectInput.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Renderuje rozwijane pole wyboru, prawdopodobnie używane do wyboru szablonów lub innych opcji.
-   **`ppb/views/templates/admin/tabs.tpl`**:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Renderuje strukturę nawigacji po zakładkach dla strony konfiguracji modułu, jeśli używa ona wielu zakładek dla różnych ustawień.
-   **Szablony hooków (`views/templates/hook/`)**: Te szablony są renderowane na stronie produktu w sklepie za pośrednictwem różnych hooków PrestaShop. Wiele z nich jest specyficznych dla szablonu, aby zapewnić optymalną integrację.

    -   **`accessories.tpl`**:
        -   **Hook:** Konfigurowalny, często `displayProductExtraContent` lub `displayProductFooter`.
        -   **Wynik:** Ogólny szablon do wyświetlania powiązanych produktów, zazwyczaj w siatce lub karuzeli.
    -   **`blocksProductsCart.tpl`**:
        -   **Hook:** Konfigurowalny, często `displayProductExtraContent` lub `displayProductFooter`.
        -   **Wynik:** Blok produktów, potencjalnie stylizowany na wygląd koszyka lub do ogólnych rekomendacji produktów.
    -   **`blocksProductsOrder.tpl`**:
        -   **Hook:** Konfigurowalny.
        -   **Wynik:** Podobnie jak `blocksProductsCart.tpl`, ale może być stylizowany dla innego kontekstu lub układu.
    -   **`custom-pictures-only.tpl`**:
        -   **Hook:** Konfigurowalny.
        -   **Wynik:** Minimalistyczny wyświetlacz pokazujący tylko zdjęcia produktów, idealny do kompaktowych przestrzeni lub wizualnego przeglądania.
    -   **`panda-blocksProductsCart.tpl`**, **`panda-blocksProductsOrder.tpl`**, **`panda-ProductExtraContent.tpl`**, **`panda-productFooter.tpl`**, **`panda-productTab.tpl`**, **`panda-productTabContent.tpl`**:
        -   **Hook:** Konfigurowalny, zaprojektowany dla szablonu Panda.
        -   **Wynik:** Szablony specyficzne dla szablonu, zapewniające płynną integrację i stylizację z językiem projektowania szablonu Panda. Będą renderować powiązane produkty w określonych obszarach szablonu Panda (np. dodatkowa zawartość produktu, stopka lub dedykowane zakładki).
    -   **`ProductExtraContent.tpl`**:
        -   **Hook:** `displayProductExtraContent`.
        -   **Wynik:** Renderuje powiązane produkty w hooku `displayProductExtraContent`, zazwyczaj w widocznym miejscu w pobliżu głównych szczegółów produktu.
    -   **`productFooter.tpl`**:
        -   **Hook:** `displayProductFooter`.
        -   **Wynik:** Renderuje powiązane produkty na dole strony produktu.
    -   **`productTab.tpl`**:
        -   **Hook:** Konfigurowalny, często `displayProductButtons` lub `displayProductExtraContent` (aby dodać nową zakładkę).
        -   **Wynik:** Renderuje *nagłówek zakładki* dla dedykowanej zakładki „Powiązane produkty” na stronie produktu.
    -   **`productTabContent.tpl`**:
        -   **Hook:** Konfigurowalny, często `displayProductContent` lub `displayProductExtraContent` (aby dodać zawartość dla nowej zakładki).
        -   **Wynik:** Renderuje *zawartość* dla dedykowanej zakładki „Powiązane produkty”, pojawiającą się po kliknięciu nagłówka `productTab.tpl`.
    -   **`table-list.tpl`**:
        -   **Hook:** Konfigurowalny.
        -   **Wynik:** Wyświetla powiązane produkty w formacie tabelarycznym, potencjalnie przydatnym do porównywania funkcji lub dla bardziej ustrukturyzowanej listy.
    -   **`warehouse-blocksProductsCart.tpl`**, **`warehouse-blocksProductsOrder.tpl`** itd. (wszystkie szablony z prefiksem `warehouse-`):
        -   **Hook:** Konfigurowalny, zaprojektowany dla szablonu Warehouse.
        -   **Wynik:** Szablony specyficzne dla szablonu Warehouse, zapewniające prawidłową stylizację i integrację układu.
    -   **`zone-blocksProductsCart.tpl`**, **`zone-blocksProductsOrder.tpl`** itd. (wszystkie szablony z prefiksem `zone-`):
        -   **Hook:** Konfigurowalny, zaprojektowany dla szablonu Zone.
        -   **Wynik:** Szablony specyficzne dla szablonu Zone, zapewniające prawidłową stylizację i integrację układu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**: Moduł prawdopodobnie przechowuje swoje dane konfiguracyjne (definicje bloków powiązanych produktów, przypisane produkty, ustawienia wyświetlania) w niestandardowych tabelach baz danych utworzonych podczas instalacji, lub może w dużym stopniu polegać na `ps_configuration` dla prostszych ustawień. Biorąc pod uwagę złożoność wielu list powiązanych produktów, niestandardowe tabele są bardziej prawdopodobne. Programiści musieliby sprawdzić metodę `install()` w `ppb/index.php` pod kątem wywołań `Db::getInstance()->execute()`, aby zidentyfikować tworzenie tabel.

    -   **Prawdopodobne tabele (hipotetyczne na podstawie funkcjonalności):**
        -   `ps_ppb_blocks`: Przechowuje główną definicję każdego bloku powiązanych produktów (ID, nazwa, hook, typ wyświetlania itp.).
        -   `ps_ppb_block_products`: Tabela wiele-do-wielu łącząca bloki powiązanych produktów z produktami, które powinny wyświetlać.
        -   `ps_ppb_block_assignments`: Tabela wiele-do-wielu łącząca bloki powiązanych produktów ze stronami produktów, na których powinny się pojawiać.
        -   `ps_ppb_block_categories`: Tabela do przechowywania przypisań kategorii dla dynamicznego wyboru lub przypisania produktów.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do warunkowego ładowania zasobów CSS i JavaScript (np. `lightslider.js`, `ppb.css`) tylko na stronach produktów lub globalnie. |
| `displayRightColumnProduct` | W prawej kolumnie strony produktu. | Renderuje bloki powiązanych produktów w prawym pasku bocznym. |
| `displayLeftColumnProduct` | W lewej kolumnie strony produktu. | Renderuje bloki powiązanych produktów w lewym pasku bocznym. |
| `displayProductExtraContent` | Elastyczny hook często znajdujący się w pobliżu opisu/obrazu produktu. | Powszechny i wysoce zalecany hook do wstrzykiwania bloków powiązanych produktów bezpośrednio do głównego obszaru treści. |
| `displayProductFooter` | Na dole strony produktu, przed ogólną stopką. | Renderuje bloki powiązanych produktów w dedykowanej sekcji na końcu treści strony produktu. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” lub akcji produktu. | Może być używany do dodania nagłówka zakładki „Powiązane produkty”. |
| `displayProductContent` | W głównym obszarze treści produktu. | Może być używany do renderowania treści zakładki „Powiązane produkty”. |
| `displayFooter` | W globalnej stopce sklepu. | Mniej powszechne dla powiązanych produktów, ale możliwe dla bardzo szerokich rekomendacji. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Potencjalnie używane do czyszczenia pamięci podręcznej lub ponownego indeksowania danych powiązanych produktów, jeśli używane są listy dynamiczne. |
| `actionProductDelete` | Po usunięciu produktu. | Do czyszczenia wszelkich przypisań powiązanych produktów dotyczących usuniętego produktu. |
| `actionCategoryUpdate` | Po zaktualizowaniu kategorii. | Do ponownej oceny list powiązanych produktów, które zależą od wyborów kategorii. |
| `actionCategoryDelete` | Po usunięciu kategorii. | Do czyszczenia przypisań powiązanych produktów dotyczących usuniętej kategorii. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących modułu „Related Products Pro”.
