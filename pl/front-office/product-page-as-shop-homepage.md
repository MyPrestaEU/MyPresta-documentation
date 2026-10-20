---
title: "Strona produktu jako strona główna sklepu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Strona produktu jako strona główna sklepu” od MyPresta.eu."
sidebar:
  label: "Strona produktu jako strona główna sklepu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product page as shop homepage na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-as-shop-homepage.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-page-as-shop-homepage/)
>
> ---


# Strona produktu jako strona główna sklepu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Strona produktu jako strona główna sklepu”. Zobaczysz jedną, prostą opcję konfiguracji.

-   **Nazwa ustawienia:** Produkt do wyświetlenia na stronie głównej
    -   **Co robi to ustawienie:** To najważniejsze ustawienie. Pozwala dokładnie wybrać, który produkt z Twojego katalogu stanie się nową stroną główną Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy produkt jest wybrany:* Główny adres URL Twojego sklepu wyświetli pełną stronę wybranego produktu.
        -   *Gdy żaden produkt nie jest wybrany (lub moduł jest wyłączony):* Twój sklep powróci do domyślnego zachowania strony głównej (np. wyświetlania polecanych produktów, kategorii lub niestandardowej strony CMS).
    -   **Zalecana wartość:** Wybierz produkt, który chcesz najbardziej wyróżnić. Użyj paska wyszukiwania, aby szybko znaleźć pożądany produkt.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie wprowadziłeś rewolucyjny nowy gadżet. Chcesz, aby każdy odwiedzający Twój sklep zobaczył ten produkt jako pierwszy. Wpisujesz nazwę produktu (np. „Super Gadżet X”) w polu wyszukiwania, wybierasz go z listy rozwijanej i zapisujesz. Teraz każdy, kto odwiedzi `www.twojskep.com`, trafi bezpośrednio na stronę produktu „Super Gadżet X”.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Produkt do wyświetlenia na stronie głównej | (Początkowo brak wyboru) / Wybierz swój kluczowy produkt | Definiuje, która strona produktu zastąpi domyślną stronę główną Twojego sklepu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moja strona główna nadal wyświetla starą zawartość po skonfigurowaniu modułu. Co powinienem zrobić?**
O: Jest to zazwyczaj problem z pamięcią podręczną.
1.  Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop.
2.  Kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
3.  Wyczyść również pamięć podręczną i pliki cookie swojej przeglądarki, a następnie spróbuj ponownie uzyskać dostęp do swojego sklepu.

**P: Czy mogę łatwo zmienić wyróżniony produkt?**
O: Tak! Po prostu wróć do **Moduły > Menedżer modułów**, znajdź „Strona produktu jako strona główna sklepu”, kliknij „Konfiguruj” i wybierz inny produkt z listy rozwijanej. Zapisz zmiany i wyczyść pamięć podręczną.

**P: Co się stanie, jeśli wybrany produkt jest niedostępny lub wyłączony?**
O: Jeśli wybrany produkt jest niedostępny, jego strona produktu nadal będzie wyświetlana, ale przycisk „Dodaj do koszyka” może być wyłączony lub wyświetlać komunikat „Brak w magazynie”, w zależności od ustawień magazynu PrestaShop. Jeśli produkt jest całkowicie wyłączony, PrestaShop może wyświetlić błąd „Strona nie znaleziona” lub powrócić do domyślnej strony głównej. Zawsze upewnij się, że wybrany produkt jest aktywny i dostępny.

**P: Czy ten moduł wpływa na moje SEO?**
O: Kiedy ustawiasz stronę produktu jako stronę główną, główny adres URL Twojego sklepu (`www.twojskep.com`) będzie teraz serwował zawartość tej strony produktu. Wyszukiwarki będą indeksować tę zawartość dla Twojej głównej domeny. Jeśli wcześniej miałeś bogatą, zoptymalizowaną pod kątem słów kluczowych stronę główną, możesz zauważyć zmianę w rankingu Twojej głównej domeny. Upewnij się, że wybrana strona produktu jest dobrze zoptymalizowana pod kątem SEO (tytuł, opis, obrazy, treść).

**P: Czy mogę używać tego z niestandardowym motywem?**
O: Tak, moduł działa poprzez nadpisywanie sposobu, w jaki PrestaShop rozsyła `IndexController`. Powinien być kompatybilny z większością niestandardowych motywów, ponieważ wykorzystuje standardowe renderowanie strony produktu PrestaShop. Jeśli napotkasz problemy ze stylizacją, prawdopodobnie są one związane z CSS Twojego motywu, a nie z podstawową funkcjonalnością modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Strona produktu jako strona główna sklepu” działa poprzez nadpisywanie głównych kontrolerów front-office PrestaShop w celu przekierowania domyślnego zachowania strony głównej (`IndexController`). Zamiast ładowania standardowego szablonu strony głównej, wymusza on na `ProductController` renderowanie strony dla określonego ID produktu, efektywnie czyniąc stronę produktu domyślną stroną docelową dla głównego adresu URL sklepu. Osiąga się to poprzez serię nadpisań w katalogu `override/`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł wykorzystuje głównie nadpisania do modyfikowania zachowania kontrolerów.

-   **Kontrolery Front-Office**:
    -   `homepageproduct/override/controllers/front/index.php`
        -   Ten plik jest placeholderem lub starszym nadpisaniem. W nowoczesnym PrestaShop `IndexController` jest zazwyczaj nadpisywany bezpośrednio. Jego obecność sugeruje mechanizm kompatybilności lub starsze podejście.
    -   `homepageproduct/override/controllers/front/IndexController.php`
        -   **Nazwa klasy i klasa nadrzędna:** `IndexController` (nadpisuje `IndexControllerCore`)
        -   **Odpowiedzialność:** To jest główne nadpisanie. Kiedy uzyskuje się dostęp do głównego adresu URL sklepu, PrestaShop normalnie rozsyła `IndexController`. To nadpisanie przechwytuje to rozsyłanie. Sprawdza konfigurację modułu pod kątem ID `homepageproduct_product`. Jeśli ID produktu jest ustawione, wewnętrznie przekierowuje lub przekazuje żądanie do `ProductController` dla tego konkretnego produktu, efektywnie renderując stronę produktu zamiast domyślnej strony głównej. Zapewnia to, że bieżący kontekst kontrolera jest poprawnie ustawiony na `ProductController` i że dane produktu są ładowane.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł wykorzystuje nadpisania do modyfikowania zachowania klas podstawowych, w szczególności związanych z obsługą kontrolerów.

-   `homepageproduct/override/classes/controller/FrontController.php`
    -   **Nazwa klasy i klasa nadrzędna:** `FrontController` (nadpisuje `FrontControllerCore`)
    -   **Odpowiedzialność:** To nadpisanie prawdopodobnie zawiera logikę zapewniającą, że nadpisanie `IndexController` działa poprawnie w procesie rozsyłania `FrontController`. Może dostosowywać sposób inicjalizacji kontrolera lub sposób przypisywania szablonów, gdy strona główna jest serwowana jako strona produktu.
-   `homepageproduct/override/classes/controller/index.php`
    -   Podobnie jak `override/controllers/front/index.php`, wydaje się to być placeholderem lub starszym mechanizmem nadpisywania.
-   `homepageproduct/override/classes/index.php`
    -   Kolejny placeholder lub starsze nadpisanie.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Cała interaktywność front-office dla strony produktu pochodzi z podstawowego JS strony produktu PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja strony produktu jest w całości obsługiwana przez aktywny motyw PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie wprowadza nowych szablonów front-office do wyświetlania. Wykorzystuje istniejące szablony stron produktów PrestaShop.

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `homepageproduct/lib/searchTool/views/scripts.tpl`
        -   Ten szablon jest prawdopodobnie używany w metodzie `getContent()` modułu w panelu administracyjnym. Prawdopodobnie zawiera logikę JavaScript lub Smarty do renderowania pola wyszukiwania produktów, umożliwiając administratorowi łatwe znajdowanie i wybieranie produktu według nazwy lub ID dla strony głównej. Może zawierać wywołania AJAX do `AdminProducts` lub podobnych kontrolerów w celu sugerowania produktów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Przechowuje swoją konfigurację w tabeli `ps_configuration`:
        -   `homepageproduct_product`: Przechowuje ID produktu wybranego jako strona główna.
        -   `mypresta_updates`, `update_`, `updatev_`: Używane do sprawdzania aktualizacji modułu przez MyPresta.eu.
        -   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standardowy klucz konfiguracji PrestaShop, nie zarządzany bezpośrednio przez ten moduł, ale potencjalnie dostępny.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie żadnych nowych hooków wyświetlania. Jego funkcjonalność jest osiągana poprzez nadpisania kontrolerów. Jednakże, ponieważ renderuje standardową stronę produktu, wszystkie hooki normalnie obecne na stronie produktu (np. `displayHeader`, `displayProductButtons`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductExtraContent`, `actionValidateOrder`) zostaną wykonane tak, jakby była to zwykła strona produktu.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Przed zawartością strony | Do włączania CSS, JS, meta tagów. |
| `displayLeftColumn` | Lewa kolumna strony produktu | Wyświetlanie bloków, takich jak kategorie, filtry. |
| `displayRightColumn` | Prawa kolumna strony produktu | Wyświetlanie bloków, takich jak koszyk, niestandardowa zawartość. |
| `displayFooter` | Na dole strony | Do włączania JS, zawartości stopki. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” | Dodawanie niestandardowych przycisków lub akcji na stronie produktu. |
| `displayProductExtraContent` | Poniżej opisu produktu | Dodawanie dodatkowych zakładek lub treści do strony produktu. |
| `actionValidateOrder` | Po zatwierdzeniu zamówienia | Do przetwarzania po zamówieniu (np. śledzenie). |
| *(Każdy inny hook normalnie na stronie produktu)* | Różnie | Standardowe wykonanie hooka strony produktu PrestaShop. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Strona produktu jako strona główna sklepu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania naszych modułów.
