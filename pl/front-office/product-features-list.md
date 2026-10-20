---
title: "Lista cech produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Lista cech produktu” od MyPresta.eu."
sidebar:
  label: "Lista cech produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product features list na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-features-list.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-features-list/)
>
> ---


# Lista cech produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Lista cech produktu)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

-   **Co robi to ustawienie:** To ustawienie kontroluje, gdzie wizualnie pojawi się lista cech produktu na stronach z listą produktów (strony kategorii, wyniki wyszukiwania itp.).
-   **Wpływ zmiany tego ustawienia:**
    -   *Gdy ustawione na „displayProductListReviews”*: Cechy pojawią się w pobliżu sekcji recenzji produktu na liście produktów. Jest to często dobre miejsce do grupowania dowodów społecznych z kluczowymi atrybutami produktu.
    -   *Gdy ustawione na „displayProductDeliveryTime”*: Cechy pojawią się w pobliżu wszelkich wyświetlanych informacji o czasie dostawy. Może to być przydatne dla produktów, gdzie cechy są ściśle związane z logistyką lub dostępnością.
    -   *Gdy ustawione na „displayHeader”*: Ta opcja jest mniej powszechna dla wizualnego wyświetlania na listach produktów i może umieścić cechy w nagłówku strony, co zazwyczaj nie jest miejscem, w którym chciałbyś, aby pojawiały się cechy specyficzne dla produktu. Jest to przede wszystkim techniczny hook.
-   **Zalecana wartość:** „displayProductListReviews” lub „displayProductDeliveryTime”. Wybierz tę, która najlepiej integruje się z układem Twojego motywu i gdzie uważasz, że cechy będą najbardziej widoczne bez zaśmiecania.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw wyraźnie pokazuje oceny gwiazdkowe i liczbę recenzji, „displayProductListReviews” umieściłoby cechy tuż obok nich, tworząc bogaty blok informacyjny. Jeśli Twoje produkty często mają specyficzne szczegóły dostawy (np. „Wysyłka w 24h”), umieszczenie cech z „displayProductDeliveryTime” może mieć sens.

### 2.2 Dedykowany ekran administracyjny: Powiązanie cech (Panel administracyjny > Moduły > Lista cech produktu > Konfiguruj > „Zarządzaj powiązaniami cech” lub podobny link)

Ten ekran jest kluczowy do zdefiniowania, *które* cechy pojawiają się dla *których* produktów i kategorii. To tutaj powiązujesz konkretne cechy produktu z kategoriami.

-   **Nazwa ekranu i lokalizacja w menu:** Po skonfigurowaniu głównego modułu, zazwyczaj znajdziesz link lub przycisk na stronie konfiguracji modułu (lub nową pozycję menu w sekcji „Katalog”), który prowadzi do „Zarządzaj powiązaniami cech” lub „Lista cech produktu”. Dokładna ścieżka może się nieznacznie różnić w zależności od Twojej wersji PrestaShop, ale będzie ona połączona z głównej konfiguracji modułu.
-   **Dostępne akcje i ustawienia:**
    -   **Widok siatki/zarządzania:** Zobaczysz tabelę zawierającą Twoje istniejące cechy produktu (są to standardowe cechy, które definiujesz w **Katalog > Atrybuty i cechy > Cechy**).
    -   **Przycisk Edytuj/Powiąż:** Dla każdej cechy będzie przycisk „Edytuj” lub „Powiąż”. Kliknięcie go otworzy formularz, w którym możesz:
        -   **Wybierz kategorie:** Wybierz jedną lub więcej kategorii, dla których ta konkretna cecha ma być wyświetlana na listach produktów. Na przykład, jeśli masz cechę „Materiał”, możesz ją powiązać z kategoriami „T-shirty”, „Sukienki” i „Kurtki”.
        -   **Włącz/Wyłącz:** Możesz mieć opcję włączenia lub wyłączenia wyświetlania tej cechy na listach produktów globalnie lub dla każdej kategorii.
-   **Wpływ zmian:**
    -   *Gdy powiążesz cechę z kategorią:* Produkty w tej kategorii, które posiadają tę cechę, wyświetlą ją w swoim wpisie na liście produktów.
    -   *Gdy usuniesz powiązanie:* Cecha nie będzie już wyświetlana dla produktów w tej kategorii na listach produktów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Najpierw upewnij się, że wszystkie Twoje cechy produktu są poprawnie skonfigurowane w **Katalog > Atrybuty i cechy > Cechy**.
    2.  Przejdź do ekranu „Zarządzaj powiązaniami cech” modułu „Lista cech produktu”.
    3.  Przejrzyj każdą odpowiednią cechę.
    4.  Dla każdej cechy wybierz kategorie, w których chcesz, aby ta cecha była widoczna na stronach z listą produktów.
    5.  Zapisz zmiany.
    6.  Okresowo przeglądaj te powiązania, zwłaszcza podczas dodawania nowych produktów, kategorii lub cech, aby upewnić się, że Twoje listy produktów pozostają informacyjne.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Pozycja tagów (`fplist_position`) | `displayProductListReviews` | Określa, gdzie cechy pojawiają się na stronach z listą produktów (np. w pobliżu recenzji, w pobliżu czasu dostawy). |
| Powiązanie cech | Nazwa cechy (np. „Materiał”) | N/A | Standardowa cecha PrestaShop do zarządzania. |
| Powiązanie cech | Powiązane kategorie | N/A | Wybierz kategorie, w których ta cecha ma być widoczna na listach produktów. |
| Powiązanie cech | Włącz/Wyłącz cechę | Włączone | Kontroluje, czy cecha jest aktywnie wyświetlana dla powiązanych z nią kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale cechy nie wyświetlają się na moich stronach kategorii.**
O:

1.  **Sprawdź powiązania cech:** Przejdź do ekranu „Zarządzaj powiązaniami cech” i upewnij się, że cechy, które spodziewasz się zobaczyć, są faktycznie powiązane z przeglądanymi kategoriami.
2.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”, jeśli jest dostępna).
3.  **Pozycja modułu:** Sprawdź ponownie ustawienie „Pozycja tagów” w głównej konfiguracji modułu. Upewnij się, że jest ustawione na hook, który Twój motyw faktycznie renderuje w kontekście listy produktów (np. `displayProductListReviews` lub `displayProductDeliveryTime`). Niektóre niestandardowe motywy mogą nie wywoływać jawnie wszystkich standardowych hooków.
4.  **Dane produktu:** Sprawdź, czy dane produkty faktycznie *mają* wartości dla cech, które próbujesz wyświetlić (np. jeśli chcesz wyświetlić „Materiał”, upewnij się, że produkt ma przypisany materiał).

**P: Cechy są wyświetlane, ale wyglądają niechlujnie lub nie pasują do projektu mojego motywu.**
O:

1.  **Konflikt CSS:** Jest to prawdopodobnie konflikt stylów z Twoim motywem. Moduł zawiera własny CSS (`fplist/views/css/fplist.css`), ale style Twojego motywu mogą go nadpisywać lub powodować problemy z układem.
2.  **Niestandardowy motyw:** Jeśli używasz bardzo spersonalizowanego motywu, możesz potrzebować webmastera lub programisty, aby dostosować CSS modułu lub CSS Twojego motywu, aby zapewnić prawidłową integrację.
3.  **Pozycjonowanie:** Spróbuj zmienić ustawienie „Pozycja tagów”, aby sprawdzić, czy inny hook lepiej integruje się wizualnie z Twoim motywem.

**P: Czy mogę wyświetlać różne cechy dla różnych kategorii?**
O: Tak, absolutnie! Jest to jedna z podstawowych zalet modułu. Użyj ekranu „Zarządzaj powiązaniami cech”, aby wybrać konkretne kategorie dla każdej cechy. Pozwala to precyzyjnie dostosować wyświetlane informacje do kontekstu listy produktów.

**P: Czy ten moduł wpływa na moje strony produktów?**
O: Nie, ten moduł jest skierowany konkretnie na strony *listy* produktów (kategoria, wyniki wyszukiwania itp.). Nie zmienia sposobu wyświetlania cech na indywidualnych stronach szczegółów produktu.

**P: Mój sklep jest wielojęzyczny. Czy nazwy cech są tłumaczone?**
O: Tak, standardowe cechy PrestaShop (których używa ten moduł) są w pełni przetłumaczalne. Upewnij się, że podałeś tłumaczenia dla nazw i wartości swoich cech w **Katalog > Atrybuty i cechy > Cechy** dla wszystkich aktywnych języków w Twoim sklepie. Moduł wyświetli wtedy prawidłowe tłumaczenie w front office.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Lista cech produktu” (`fplist`) stosuje standardową architekturę modułu PrestaShop, głównie rozszerzając `Module` dla swojej podstawowej funkcjonalności i `AdminController` dla interfejsu zarządzania w Panelu administracyjnym. Wykorzystuje system hooków PrestaShop do wstrzykiwania treści na strony z listą produktów i używa `ObjectModel` (pośrednio poprzez `AdminFplistAssociationController`) do zarządzania powiązaniem między cechami a kategoriami. Wyświetlanie modułu w front-office jest obsługiwane przez szablon Smarty renderowany za pomocą hooka.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Ten moduł nie zawiera dedykowanych kontrolerów front-office. Cała logika wyświetlania w front-office jest obsługiwana bezpośrednio w głównym pliku modułu (`fplist.php`) poprzez zarejestrowane hooki.
-   **Kontrolery administracyjne Back-Office**:

    -   `fplist/controllers/admin/AdminFplistAssociation.php`
        -   **Nazwa klasy:** `AdminFplistAssociationController` (rozszerza `ModuleAdminController`)
        -   **Odpowiedzialność:** Ten kontroler zarządza powiązaniem między cechami PrestaShop a kategoriami. Zapewnia interfejs Panelu administracyjnego (listę i potencjalnie formularz edycji) dla administratorów do wyboru, które cechy powinny być wyświetlane na listach produktów dla konkretnych kategorii. Współpracuje z wewnętrznym magazynem danych modułu (prawdopodobnie tabela `ps_fplist_association`, chociaż w dossier nie ma jawnego `ObjectModel`, kontroler implikuje jego istnienie i zarządzanie).
    -   `fplist/controllers/admin/index.php`
        -   **Nazwa klasy:** N/A (jest to zazwyczaj pusty plik lub przekierowanie, aby zapobiec bezpośredniemu dostępowi do katalogu, a nie funkcjonalny kontroler).
        -   **Odpowiedzialność:** Standardowy środek bezpieczeństwa PrestaShop zapobiegający listowaniu katalogów.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. `AdminFplistAssociationController` implikuje istnienie modelu danych dla powiązań cecha-kategoria, który jest prawdopodobnie obsługiwany bezpośrednio w kontrolerze lub głównym pliku modułu za pomocą zapytań `Db::getInstance()`, a nie dedykowanego `ObjectModel`. Gdyby `ObjectModel` był obecny, zazwyczaj nazywałby się `FplistAssociation` lub podobnie.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu nie wskazuje na niestandardowe pliki JavaScript. Wszelkie dynamiczne zachowania lub interakcje AJAX musiałyby być zaimplementowane bezpośrednio w plikach PHP lub szablonach modułu, lub opierać się na podstawowym JS PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `fplist/views/css/fplist.css`
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów jest odpowiedzialny za wizualną prezentację listy cech produktu na stronach kategorii i list. Definiuje style dla kontenera zawierającego cechy, poszczególnych elementów cech oraz potencjalnie ikon lub etykiet z nimi związanych.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści powinni sprawdzić renderowany HTML, aby zidentyfikować konkretne klasy (np. `.fplist-container`, `.fplist-item`, `.fplist-feature-name`, `.fplist-feature-value`), aby nadpisać je w pliku `custom.css` lub `theme.css` swojego motywu w celu bezproblemowej integracji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `fplist/views/templates/fplist-front.tpl`
        -   **Hook:** Ten szablon jest renderowany w hookach `displayProductListReviews` i `displayProductDeliveryTime` (zgodnie z konfiguracją `fplist_position`).
        -   **Wyjście:** Generuje strukturę HTML dla listy cech pojedynczego produktu na stronie z listą produktów. Iteruje przez cechy pobrane przez moduł dla bieżącego produktu i kategorii, wyświetlając ich nazwy i wartości.
    -   `fplist/views/templates/fplist.tpl`
        -   **Hook:** Ten szablon jest prawdopodobnie używany dla głównej strony konfiguracji modułu w Panelu administracyjnym (poprzez `getContent()`).
        -   **Wyjście:** Renderuje formularz dla ustawienia „Pozycja tagów” i potencjalnie linki do `AdminFplistAssociationController` do zarządzania powiązaniami cech.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_fplist_association` (implikowane): Ta tabela nie jest jawnie zdefiniowana w dossier, ale jest niezbędna dla `AdminFplistAssociationController` do przechowywania relacji wiele do wielu między cechami PrestaShop a kategoriami. Zazwyczaj zawierałaby kolumny takie jak `id_feature`, `id_category` i potencjalnie `id_shop`.
    -   Rekordy konfiguracji w `ps_configuration`:
        -   `mypresta_updates`: Przechowuje informacje o aktualizacjach dla modułów MyPresta.eu.
        -   `update_`: Związane ze sprawdzaniem aktualizacji modułu.
        -   `updatev_`: Związane ze sprawdzaniem aktualizacji modułu.
        -   `fplist_position`: Przechowuje wybraną nazwę hooka do wyświetlania cech (np. `displayProductListReviews`).
        -   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standardowa konfiguracja PrestaShop dla języka formularza pracownika.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Głównie używany do ładowania zasobów CSS/JS lub meta tagów. Moduł używa go jako konfigurowalnej pozycji dla cech, choć rzadziej do wizualnego wyświetlania. |
| `displayProductListReviews` | W elemencie listy produktów, zazwyczaj w pobliżu recenzji produktu. | Wstrzykuje HTML listy cech do każdego wpisu produktu na stronach kategorii/wyszukiwania. |
| `displayProductDeliveryTime` | W elemencie listy produktów, zazwyczaj w pobliżu informacji o czasie dostawy. | Wstrzykuje HTML listy cech do każdego wpisu produktu na stronach kategorii/wyszukiwania. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | (Nie jest jawnie używany przez ten moduł, ale jest to powszechny hook dla działań związanych z zamówieniami). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji modułu, poprawek błędów i profesjonalnego wsparcia, prosimy zapoznać się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Lista cech produktu”.
