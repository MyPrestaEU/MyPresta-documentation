---
title: "Blok nowych produktów na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Blok nowych produktów na stronie głównej” od MyPresta.eu."
sidebar:
  label: "Blok nowych produktów na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Home new products block na MyPresta.eu](https://mypresta.eu/modules/front-office-features/home-new-products-block.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/home-new-products-block/)
>
> ---


# Blok nowych produktów na stronie głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Blok nowych produktów na stronie głównej”, aby uzyskać dostęp do jego ustawień.

#### Ustawienie: Liczba produktów do wyświetlenia

-   **Co robi to ustawienie:** To pole pozwala kontrolować, ile najnowszych produktów zostanie wyświetlonych w bloku na stronie głównej.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po ustawieniu na wyższą liczbę (np. 10):* Więcej nowych produktów będzie widocznych w bloku, dając klientom szerszy wybór najnowszych pozycji. Może to sprawić, że blok będzie dłuższy lub będzie wymagał więcej przewijania.
    -   *Po ustawieniu na niższą liczbę (np. 4):* Mniej nowych produktów zostanie wyświetlonych, co sprawi, że blok będzie bardziej kompaktowy. Może to być przydatne, jeśli masz ograniczoną przestrzeń lub chcesz wyróżnić tylko absolutnie najświeższe pozycje.
-   **Zalecana wartość:** Dobrym punktem wyjścia jest `8` lub `12` produktów. Zapewnia to przyzwoity wybór bez przytłaczania strony.
-   **Scenariusz/przykład sprzedawcy:** Jeśli prowadzisz sklep odzieżowy i co tydzień dodajesz 20 nowych pozycji, ustawienie tej wartości na `12` zapewnia, że zawsze widoczna jest dobra różnorodność. Jeśli dodajesz tylko kilka nowych produktów rzemieślniczych każdego miesiąca, `4` lub `6` może być bardziej odpowiednie, aby blok był zwięzły.

#### Ustawienie: Wyświetl na stronie głównej

-   **Co robi to ustawienie:** Jest to prosty przełącznik WŁ./WYŁ., który kontroluje, czy „Blok nowych produktów na stronie głównej” jest widoczny na stronie głównej Twojego sklepu.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po włączeniu (TAK):* Blok z nowymi produktami pojawi się na stronie głównej, zgodnie z opisem w Sekcji 2.
    -   *Po wyłączeniu (NIE):* Blok zostanie ukryty ze strony głównej. Może to być przydatne, jeśli tymczasowo chcesz go usunąć bez odinstalowywania modułu, lub jeśli wolisz używać innych metod do prezentowania nowych produktów.
-   **Zalecana wartość:** `TAK` (Włączone). Głównym celem tego modułu jest wyświetlanie nowych produktów na stronie głównej.
-   **Scenariusz/przykład sprzedawcy:** Możesz tymczasowo wyłączyć go, jeśli prowadzisz specjalną kampanię sezonową, która wymaga całej przestrzeni na stronie głównej dla banerów promocyjnych, a następnie ponownie włączyć go po zakończeniu kampanii.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Liczba produktów do wyświetlenia | 8-12 | Kontroluje, ile nowych produktów pojawia się w bloku. Wyższa liczba pokazuje więcej, niższa liczba sprawia, że jest bardziej kompaktowy. |
| Strona konfiguracji modułu | Wyświetl na stronie głównej | TAK | Przełącza widoczność bloku nowych produktów na stronie głównej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój blok nowych produktów nie wyświetla się na stronie głównej po instalacji.**
O:

1.  **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Blok nowych produktów na stronie głównej” i kliknij „Konfiguruj”. Upewnij się, że „Wyświetl na stronie głównej” jest ustawione na `TAK`.
2.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
3.  **Sprawdź pozycję hooka:** Chociaż moduł jest zaprojektowany do automatycznego podłączania, czasami konflikty motywów lub inne moduły mogą zakłócać działanie. Przejdź do **Wygląd > Pozycje**. Wyszukaj `displayHome` (lub `displayHomeTabContent`, jeśli Twój motyw używa zakładek). Upewnij się, że `home-new-products-block` jest wymieniony i włączony w jednym z tych hooków. Jeśli nie, być może będziesz musiał „Przeszczepić moduł” do `displayHome`.

**P: Blok wyświetla stare produkty, a nie nowe.**
O: Moduł wyświetla produkty na podstawie ich „daty dodania” w PrestaShop. Upewnij się, że podczas dodawania nowych produktów ich data utworzenia jest poprawnie ustawiona na bieżącą datę. Jeśli zaimportowałeś produkty ze starymi datami, mogą one nie pojawić się jako „nowe”. Może być konieczne ręczne zaktualizowanie pola `date_add` dla tych produktów w bazie danych (zaawansowane zadanie, skonsultuj się z programistą) lub ponowne ich dodanie.

**P: Chcę zmienić miejsce, w którym blok pojawia się na mojej stronie głównej (np. wyżej lub w kolumnie).**
O: Możesz dostosować pozycję modułu za pomocą wbudowanej funkcji „Edycja na żywo” w PrestaShop.

1.  Przejdź do **Wygląd > Pozycje**.
2.  Kliknij przycisk „Uruchom edycję na żywo” (zazwyczaj w prawym górnym rogu).
3.  Przejdź do swojej strony głównej.
4.  Powinieneś zobaczyć obramowania wokół różnych bloków modułów. Znajdź „Blok nowych produktów na stronie głównej” i przeciągnij go w wybrane miejsce. Możesz również użyć przycisku „Przeszczep moduł”, aby przenieść go do innego hooka (np. `displayLeftColumn`, `displayRightColumn`, `displayFooter`).

**P: Blok wygląda dziwnie lub nie pasuje do stylu mojego motywu.**
O: Ten moduł używa standardowych szablonów wyświetlania produktów PrestaShop, które powinny dziedziczyć większość stylów Twojego motywu. Jeśli wygląda to niepoprawnie:

1.  **Wyczyść pamięć podręczną:** Jak wyżej, wyczyść pamięć podręczną PrestaShop.
2.  **Nadpisania motywu:** Twój motyw może mieć specyficzny CSS, który powoduje konflikty. Zazwyczaj wymaga to od programisty internetowego sprawdzenia CSS Twojej witryny i potencjalnego dodania niestandardowych stylów do pliku `custom.css` Twojego motywu lub jego odpowiednika, aby nadpisać domyślne.
3.  **Aktualizacja modułu:** Upewnij się, że masz najnowszą wersję modułu z MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Blok nowych produktów na stronie głównej” to prosty moduł PrestaShop, zgodny ze standardową strukturą modułów. Wykorzystuje głównie klasę `Module` do zarządzania swoim cyklem życia (instalacja, deinstalacja) oraz metody `hook` do renderowania treści we front office. Pobiera dane produktów bezpośrednio z podstawowych tabel bazy danych PrestaShop, wykorzystując istniejące funkcjonalności `Product` i `Category`. Nie ma niestandardowych kontrolerów ani złożonych ObjectModels, co czyni go lekkim i łatwym do zintegrowania.

### 4.2 Kontrolery (`controllers/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała logika jest hermetyzowana w głównym pliku modułu i wykonywana za pośrednictwem hooków.

### 4.3 Podstawowe klasy i modele (`classes/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Opiera się na podstawowych klasach PrestaShop `Product` i `Category` do pobierania danych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Wszelkie dynamiczne zachowania (np. karuzele) byłyby zazwyczaj obsługiwane przez istniejący JS motywu lub oddzielny moduł.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Opiera się na domyślnych stylach motywu dla list produktów i siatek. Programiści, którzy chcą stylizować ten blok w specyficzny sposób, powinni celować w jego strukturę HTML (np. `div#home_new_products`) w pliku `custom.css` swojego motywu lub jego odpowiedniku.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   Ten moduł używa głównie jednego pliku szablonu do renderowania swojej zawartości.

    -   **Szablony hooków (`views/templates/hook/`)**:
        -   `views/templates/hook/home-new-products-block.tpl`: Jest to główny plik szablonu odpowiedzialny za renderowanie bloku nowych produktów na stronie głównej.
        -   **Hook:** Głównie przeznaczony dla `displayHome` (lub `displayHomeTabContent` w niektórych motywach).
        -   **Cel:** Iteruje przez zmienną `$products` (tablicę obiektów `Product`) przekazaną z metody `hookDisplayHome` i wyświetla obraz, nazwę, cenę i przycisk „Dodaj do koszyka” każdego produktu, zazwyczaj używając pętli i dołączając standardowy szablon elementu listy produktów (np. `product-miniature.tpl` lub podobny, w zależności od wersji PrestaShop i motywu).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. `HOME_NEW_PRODUCTS_NBR`, `HOME_NEW_PRODUCTS_DISPLAY`) w standardowej tabeli `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHome` | Renderuje zawartość w głównym obszarze strony głównej. | Wyświetla blok nowych produktów na stronie głównej sklepu. |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Służy do rejestrowania zasobów (CSS/JS), jeśli takie były obecne, choć ten moduł nie używa go do tego celu. Może być używany do meta tagów lub innych globalnych elementów. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie bocznej. | Pozwala na przeniesienie bloku nowych produktów do lewej kolumny za pomocą „Wygląd > Pozycje”. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie bocznej. | Pozwala na przeniesienie bloku nowych produktów do prawej kolumny za pomocą „Wygląd > Pozycje”. |
| `displayFooter` | Renderuje zawartość w stopce sklepu. | Pozwala na przeniesienie bloku nowych produktów do stopki za pomocą „Wygląd > Pozycje”. |
| `actionProductAdd` | Wykonywany po dodaniu nowego produktu. | Może być używany do czyszczenia pamięci podręcznej lub ponownego indeksowania, choć nie jest to wyraźnie używane przez ten moduł. |
| `actionProductUpdate` | Wykonywany po aktualizacji produktu. | Może być używany do czyszczenia pamięci podręcznej lub ponownego indeksowania, choć nie jest to wyraźnie używane przez ten moduł. |
| `actionProductDelete` | Wykonywany po usunięciu produktu. | Może być używany do czyszczenia pamięci podręcznej lub ponownego indeksowania, choć nie jest to wyraźnie używane przez ten moduł. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Blok nowych produktów na stronie głównej”, zapoznaj się ze swoim kontem klienta MyPresta.eu. Możesz pobrać najnowsze wersje i uzyskać dostęp do zasobów wsparcia bezpośrednio z [MyPresta.eu](https://mypresta.eu).
