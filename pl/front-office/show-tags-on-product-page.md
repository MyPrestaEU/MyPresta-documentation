---
title: "Wyświetlaj tagi na stronie produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyświetlaj tagi na stronie produktu” od MyPresta.eu."
sidebar:
  label: "Wyświetlaj tagi na stronie produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Show tags on product page na MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-tags-on-product-page.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/show-tags-on-product-page/)
>
> ---


# Wyświetlaj tagi na stronie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) typowo dostępne w każdym nowoczesnym środowisku hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł posiada prostą stronę konfiguracji, umożliwiającą szybkie włączanie lub wyłączanie jego funkcjonalności oraz wybór miejsca, w którym tagi będą wyświetlane na stronach produktów.

**Dostęp:** Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Wyświetlaj tagi na stronie produktu” i kliknij „Konfiguruj”.

#### **Włącz / Wyłącz moduł**

- **Co robi to ustawienie:** Jest to główny przełącznik funkcjonalności modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Moduł zacznie wyświetlać tagi produktów na stronach produktów w Twoim sklepie zgodnie z wybranym hakiem.
  - *Gdy wyłączone:* Moduł przestanie wyświetlać tagi produktów. Wszystkie inne ustawienia zostaną zapisane, ale będą nieaktywne.
- **Zalecana wartość:** TAK
- **Scenariusz / przykład dla sprzedawcy:** Chcesz przetestować moduł lub tymczasowo ukryć tagi podczas przebudowy witryny. Wyłączysz go, a następnie ponownie włączysz, gdy będzie gotowy.

#### **Wybierz hak do wyświetlania tagów**

- **Co robi to ustawienie:** To kluczowe ustawienie określa, *gdzie* na stronie produktu będą wyświetlane tagi. PrestaShop używa „haków” jako specyficznych punktów w kodzie strony, gdzie moduły mogą wstawiać swoją zawartość.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na `displayProductButtons` (PrestaShop 1.7+):* Tagi zazwyczaj pojawią się w pobliżu przycisku „Dodaj do koszyka” lub innych przycisków akcji produktu. Jest to często widoczne i skuteczne miejsce.
  - *Gdy ustawione na `displayProductExtraContent` (PrestaShop 1.7+):* Tagi pojawią się w dedykowanej sekcji dla dodatkowej zawartości produktu, często poniżej głównych informacji o produkcie lub w zakładce.
  - *Gdy ustawione na `displayFooterProduct` (PrestaShop 1.7+):* Tagi pojawią się na dole strony produktu, często powyżej stopki całej witryny.
  - *Gdy ustawione na `displayLeftColumnProduct` (PrestaShop 1.7+):* Tagi pojawią się w lewej kolumnie specjalnie na stronie produktu.
  - *Gdy ustawione na `displayRightColumnProduct` (PrestaShop 1.7+):* Tagi pojawią się w prawej kolumnie specjalnie na stronie produktu.
  - *Inne haki (np. `displayProductTab`, `displayProductTabContent`, `displayFooter`):* Dokładne umiejscowienie będzie zależeć od implementacji tych haków w Twoim motywie. `displayFooter` umieściłby tagi w ogólnej stopce witryny, co zazwyczaj nie jest specyficzne dla produktu.
- **Zalecana wartość:** `displayProductButtons` lub `displayProductExtraContent` są zazwyczaj najbardziej skuteczne pod względem widoczności i kontekstu. Eksperymentuj, aby zobaczyć, co wygląda najlepiej z Twoim motywem.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby tagi były bardzo widoczne, aby zachęcić do natychmiastowego odkrywania podobnych produktów, więc wybierasz `displayProductButtons`. Jeśli wolisz, aby były mniej inwazyjne i stanowiły część informacji uzupełniających, `displayProductExtraContent` może być lepsze.

#### **Tytuł bloku tagów**

- **Co robi to ustawienie:** Pozwala ustawić niestandardowy tytuł, który pojawi się nad listą tagów na stronie produktu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wprowadzono tytuł (np. „Tagi produktu”, „Powiązane słowa kluczowe”):* Ten tytuł zostanie wyświetlony nad listą tagów, zapewniając wyraźny nagłówek dla Twoich klientów.
  - *Gdy pozostawiono puste:* Nie zostanie wyświetlony żaden tytuł, a pojawi się tylko lista tagów.
- **Zalecana wartość:** „Tagi produktu” lub „Słowa kluczowe”
- **Scenariusz / przykład dla sprzedawcy:** Chcesz wyraźnie oznaczyć sekcję, aby klienci zrozumieli jej cel. Ustawienie tytułu na „Powiązane tagi” pomaga w ich interakcji.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł | TAK | Aktywuje/dezaktywuje funkcjonalność wyświetlania tagów modułu. |
| Konfiguracja modułu | Wybierz hak do wyświetlania tagów | `displayProductButtons` lub `displayProductExtraContent` | Określa dokładną pozycję tagów na stronie produktu. |
| Konfiguracja modułu | Tytuł bloku tagów | „Tagi produktu” | Ustawia nagłówek dla wyświetlanych tagów, poprawiając przejrzystość dla klientów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zainstalowałem i skonfigurowałem moduł, ale tagi nie wyświetlają się na moich stronach produktów. Co jest nie tak?**
**O1:**

-   **Sprawdź status modułu:** Upewnij się, że moduł jest „Włączony” w swojej konfiguracji.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). PrestaShop często buforuje zawartość, a nowe dane z modułu mogą nie pojawić się, dopóki pamięć podręczna nie zostanie wyczyszczona.
-   **Zweryfikuj tagi produktu:** Upewnij się, że konkretny produkt, który przeglądasz, ma przypisane tagi. Edytuj produkt w Panelu administracyjnym i sprawdź zakładkę „SEO” lub „Tagi”.
-   **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą nadpisywać standardowe haki PrestaShop lub mieć unikalne układy. Spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop (np. Classic), aby sprawdzić, czy tagi się pojawiają. Jeśli tak, Twój niestandardowy motyw może wymagać niewielkiej korekty (patrz P3).
-   **Wybór haka:** Sprawdź dokładnie, czy wybrałeś odpowiedni hak w konfiguracji modułu. Niektóre haki mogą nie być renderowane przez Twój motyw w widocznym miejscu.

**P2: Tagi się wyświetlają, ale wyglądają prosto lub nie pasują do stylu mojego motywu.**
**O2:**

-   Moduł zapewnia podstawowe style. Jeśli chcesz, aby idealnie pasowały do Twojego motywu, musisz dodać niestandardowy CSS.
-   **Jak to zrobić:**
    1.  Sprawdź tagi na stronie produktu za pomocą narzędzi deweloperskich przeglądarki (kliknij prawym przyciskiem myszy, a następnie „Zbadaj element”).
    2.  Zidentyfikuj klasy CSS używane przez tagi (np. `ptags_block`, `ptags_item`).
    3.  Dodaj niestandardowe reguły CSS do pliku `custom.css` Twojego motywu (jeśli taki posiada) lub bezpośrednio do pliku `ptags.css` modułu (chociaż modyfikowanie plików modułu bezpośrednio nie jest zalecane, ponieważ aktualizacje je nadpiszą).
    -   **Przykład CSS:**

    ```
    .ptags\_block { margin-top: 20px; padding: 15px; border: 1px solid #eee; background-color: #f9f9f9;}.ptags\_block h3 { font-size: 18px; color: #333; margin-bottom: 10px;}.ptags\_item { display: inline-block; margin-right: 8px; margin-bottom: 8px;}.ptags\_item a { background-color: #007bff; color: white; padding: 5px 10px; border-radius: 3px; text-decoration: none; font-size: 14px;}.ptags\_item a:hover { background-color: #0056b3;}
    ```

**P3: Tagi się pojawiają, ale są w niewygodnej pozycji lub chcę je umieścić w bardzo konkretnym miejscu, którego nie ma na liście opcji haków.**
**O3:**

-   Moduł opiera się na standardowych hakach PrestaShop. Jeśli potrzebujesz bardzo specyficznego, niestandardowego umiejscowienia, zazwyczaj wymaga to modyfikacji motywu.
-   **Rozwiązanie:** Ty lub Twój programista internetowy będziecie musieli ręcznie wstawić funkcję wyświetlania modułu do pliku szablonu strony produktu Twojego motywu (`product.tpl` lub `product-details.tpl` w folderze motywu).
    -   Znajdź dokładne miejsce w pliku `.tpl` Twojego motywu, gdzie chcesz, aby tagi się pojawiły.
    -   Wstaw następujący kod Smarty: `{hook h='displayProductTags' product=$product}` (Uwaga: `displayProductTags` to niestandardowa nazwa haka, którą zarejestrowałbyś w module, lub możesz użyć `displayProductButtons`, jeśli tak skonfigurowałeś).
    -   Alternatywnie, możesz wywołać moduł bezpośrednio: `{Module::getInstanceByName('ptags')->hookDisplayProductTags(['product' => $product])}`. Jest to bardziej bezpośrednie, ale mniej elastyczne niż użycie haka.
-   **Ważne:** Wymaga to podstawowej wiedzy na temat tworzenia motywów PrestaShop.

**P4: Czy ten moduł spowolni mój sklep?**
**O4:**

-   Nie, ten moduł jest bardzo lekki. Wykonuje proste zapytanie do bazy danych, aby pobrać tagi powiązane z bieżącym produktem. Ta operacja jest wysoce zoptymalizowana przez rdzeń PrestaShop i nie wpłynie zauważalnie na czas ładowania strony.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Wyświetlaj tagi na stronie produktu” (`ptags`) to prosty moduł PrestaShop zaprojektowany do rozszerzania funkcjonalności front-office. Wykorzystuje klasyczną architekturę modułu PrestaShop, głównie klasę `Module` oraz jej metody `install()`, `uninstall()` i `hook`. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonego JavaScriptu. Jego podstawową funkcją jest pobieranie tagów produktów i renderowanie ich za pomocą szablonu Smarty w wybranym haku front-office.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała logika jest hermetyzowana w głównej klasie modułu (`ptags/index.php`) i wykonywana za pośrednictwem systemu haków PrestaShop.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Ten moduł **nie** wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Bezpośrednio wykorzystuje podstawowe klasy PrestaShop `Tag` i `Product` do pobierania niezbędnych danych.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Jego funkcjonalność to czyste renderowanie HTML po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **Ścieżka pliku**: `ptags/views/css/ptags.css`
-   **Zakres**: Stylowanie dla klienta front-office.
-   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Ten arkusz stylów zapewnia podstawowe stylowanie dla bloku zawierającego tagi produktów i poszczególne linki tagów.
-   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie**:
    -   `.ptags_block`: Stylizuje główny blok kontenera dla tagów.
    -   `.ptags_block h3`: Stylizuje tytuł bloku tagów.
    -   `.ptags_item`: Stylizuje każdy pojedynczy element tagu (np. `display: inline-block`, marginesy).
    -   `.ptags_item a`: Stylizuje klikalne linki tagów (np. tło, kolor, dopełnienie, promień obramowania).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   **Ścieżka pliku**: `ptags/views/front/ptags.tpl`
    -   **Renderowane w haku**: Ten szablon jest renderowany przez metody `hook` modułu (np. `hookDisplayProductButtons`, `hookDisplayProductExtraContent` itp., w zależności od konfiguracji).
    -   **Wyjście bloku wizualnego**: Ten szablon jest odpowiedzialny za generowanie struktury HTML dla bloku tagów, w tym opcjonalnego tytułu i listy klikalnych linków tagów. Iteruje przez zmienną `$tags` (tablicę obiektów tagów) przekazaną z metody haka modułu.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się na istniejących tabelach PrestaShop, głównie `ps_tag`, `ps_product_tag` i `ps_lang` dla danych tagów.

    -   Ustawienia konfiguracji są przechowywane w `ps_configuration` z kluczami takimi jak `PTAGS_ENABLED`, `PTAGS_HOOK`, `PTAGS_TITLE`.
-   **Tabela zarejestrowanych haków**:

    | Nazwa haka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayHeader` | W sekcji `<head>` każdej strony. | Służy do ładowania arkusza stylów CSS modułu (`ptags.css`). |
    | `displayProductButtons` | Na stronie produktu, zazwyczaj w pobliżu przycisku „Dodaj do koszyka”. | Wyświetla blok tagów produktu. (PrestaShop 1.7+) |
    | `displayProductExtraContent` | Na stronie produktu, w dedykowanej sekcji dla dodatkowej zawartości. | Wyświetla blok tagów produktu. (PrestaShop 1.7+) |
    | `displayFooterProduct` | Na dole zawartości strony produktu. | Wyświetla blok tagów produktu. (PrestaShop 1.7+) |
    | `displayLeftColumnProduct` | W lewej kolumnie specjalnie na stronie produktu. | Wyświetla blok tagów produktu. (PrestaShop 1.7+) |
    | `displayRightColumnProduct` | W prawej kolumnie specjalnie na stronie produktu. | Wyświetla blok tagów produktu. (PrestaShop 1.7+) |
    | `displayProductTab` | Dodaje nową zakładkę do strony produktu. | (Jeśli skonfigurowano) Wyświetla tagi produktu w zakładce. |
    | `displayProductTabContent` | Zawartość dla zakładki strony produktu. | (Jeśli skonfigurowano) Wyświetla tagi produktu jako zawartość zakładki. |
    | `displayFooter` | W ogólnej stopce witryny. | (Jeśli skonfigurowano) Wyświetla blok tagów produktu w globalnej stopce. |
    | `displayLeftColumn` | W lewej kolumnie stron (nie specyficznych dla produktu). | (Jeśli skonfigurowano) Wyświetla blok tagów produktu w globalnej lewej kolumnie. |
    | `displayRightColumn` | W prawej kolumnie stron (nie specyficznych dla produktu). | (Jeśli skonfigurowano) Wyświetla blok tagów produktu w globalnej prawej kolumnie. |

    Moduł dynamicznie rejestruje się do haka wybranego w jego konfiguracji. Plik `index.php` zawiera metody `hook[HookName]`, które pobierają ID produktu, odzyskują powiązane tagi i przekazują je do `ptags.tpl` w celu renderowania.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyświetlaj tagi na stronie produktu”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań związanych z funkcjonalnością i integracją modułu.
