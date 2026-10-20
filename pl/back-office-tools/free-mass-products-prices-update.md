---
title: "Darmowa masowa aktualizacja cen produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Darmowa masowa aktualizacja cen produktów” od MyPresta.eu."
sidebar:
  label: "Darmowa masowa aktualizacja cen produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free mass products prices update na MyPresta.eu](https://mypresta.eu/modules/administration-tools/free-mass-products-prices-update.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/free-mass-products-prices-update/)
>
> ---


# Darmowa masowa aktualizacja cen produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Darmowa masowa aktualizacja cen produktów)

Jest to główny i jedyny ekran konfiguracji modułu „Darmowa masowa aktualizacja cen produktów”. Tutaj zdefiniujesz, w jaki sposób chcesz dostosować ceny swoich produktów.

#### **Typ korekty ceny**

-   **Co robi to ustawienie:** To kluczowe ustawienie określa, czy chcesz zwiększyć, czy zmniejszyć ceny swoich produktów.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy ustawione na „Zwiększ” (Increase):* Moduł doda określony procent do aktualnej ceny każdego produktu.
    *   *Gdy ustawione na „Zmniejsz” (Decrease):* Moduł odejmie określony procent od aktualnej ceny każdego produktu.
-   **Zalecana wartość:** Wybierz na podstawie swoich bieżących potrzeb biznesowych (np. „Zwiększ” dla ogólnej podwyżki cen, „Zmniejsz” dla wyprzedaży).
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli koszty dostawcy wzrosły, wybierzesz „Zwiększ”. Jeśli prowadzisz szybką wyprzedaż, wybierzesz „Zmniejsz”.

#### **Wartość procentowa**

-   **Co robi to ustawienie:** To pole pozwala wprowadzić dokładny procent, o który chcesz skorygować ceny.
-   **Efekt zmiany tego ustawienia:**
    *   *Gdy ustawione na „10”:* Jeśli wybrano „Zwiększ”, ceny wzrosną o 10%. Jeśli wybrano „Zmniejsz”, ceny spadną o 10%.
    *   *Gdy ustawione na „0”:* Nie nastąpi żadna zmiana ceny.
-   **Zalecana wartość:** Wprowadź dokładny procent, którego potrzebujesz. Użyj liczb całkowitych lub dziesiętnych (np. „5” dla 5%, „2.5” dla 2.5%).
-   **Scenariusz / przykład dla sprzedawcy:** Aby zaoferować 15% zniżki w całym sklepie, ustawisz „Typ korekty ceny” na „Zmniejsz” i „Wartość procentową” na „15”. Aby zwiększyć ceny o 7.5%, ustawisz „Typ korekty ceny” na „Zwiększ” i „Wartość procentową” na „7.5”.

#### **Przycisk Zastosuj zmiany**

-   **Co to robi:** Ten przycisk inicjuje faktyczny proces aktualizacji cen.
-   **Efekt kliknięcia tego przycisku:** Po kliknięciu moduł przetworzy wszystkie produkty w Twoim sklepie zgodnie z ustawionym „Typem korekty ceny” i „Wartością procentową”. **Ta akcja jest nieodwracalna bez kopii zapasowej bazy danych.**
-   **Zalecane działanie:** Zawsze dokładnie sprawdź „Typ korekty ceny” i „Wartość procentową” przed kliknięciem tego przycisku. Upewnij się, że masz aktualną kopię zapasową bazy danych.
-   **Scenariusz / przykład dla sprzedawcy:** Po starannym ustawieniu „Zmniejsz” i „20” dla weekendowej wyprzedaży, klikasz „Zastosuj zmiany”, aby natychmiast zaktualizować wszystkie ceny produktów o -20%.

:::warning WAŻNA UWAGA
Moduł „Darmowa masowa aktualizacja cen produktów” wykonuje bezpośrednią aktualizację cen Twoich produktów. **Nie ma przycisku „cofnij”.** Przed zastosowaniem jakichkolwiek zmian, **KRYTYCZNE** jest utworzenie pełnej kopii zapasowej bazy danych PrestaShop. Pozwoli to na przywrócenie cen do poprzedniego stanu, jeśli popełnisz błąd lub zmienisz zdanie.
:::

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Typ korekty ceny | (Wybierz Zwiększ/Zmniejsz) | Określa, czy ceny wzrosną, czy spadną. |
| Konfiguracja modułu | Wartość procentowa | (Wprowadź żądany procent) | Dokładny procent korekty ceny. |
| Konfiguracja modułu | Przycisk Zastosuj zmiany | (Kliknij z ostrożnością) | Wykonuje masową aktualizację cen. **Nieodwracalne bez kopii zapasowej.** |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zaktualizowałem ceny, ale nie wyświetlają się w moim sklepie. Co jest nie tak?**
O1: Po każdej znaczącej zmianie danych w PrestaShop, zwłaszcza związanej z produktami, dobrą praktyką jest wyczyszczenie pamięci podręcznej sklepu.
\* Przejdź do **Zaawansowane > Wydajność** w swoim Panelu administracyjnym.
\* Kliknij przycisk „Wyczyść pamięć podręczną” w prawym górnym rogu.
\* Upewnij się również, że pamięć podręczna przeglądarki jest wyczyszczona, lub spróbuj przeglądać swój sklep w oknie incognito/prywatnym.

**P2: Popełniłem błąd i niepoprawnie zaktualizowałem ceny. Jak mogę to cofnąć?**
O2: Jak wspomniano, ten moduł nie ma przycisku „cofnij”. Dlatego kopia zapasowa bazy danych jest kluczowa.
\* Jeśli wykonałeś kopię zapasową *przed* zastosowaniem zmian, będziesz musiał przywrócić bazę danych z tej kopii zapasowej. Zazwyczaj wymaga to dostępu do panelu sterowania hostingu (np. cPanel, Plesk) lub użycia modułu kopii zapasowej PrestaShop.
\* Jeśli *nie* wykonałeś kopii zapasowej, będziesz musiał ręcznie ponownie wprowadzić poprawne ceny dla swoich produktów lub ponownie użyć modułu z odwrotnym obliczeniem (np. jeśli zmniejszyłeś o 20%, musiałbyś zwiększyć o 25%, aby wrócić do pierwotnej wartości, ale może to nie być idealnie dokładne z powodu zaokrągleń).

**P3: Czy ten moduł wpływa na konkretne ceny lub kombinacje?**
O3: Moduł aktualizuje *cenę bazową* Twoich produktów. Nie zarządza bezpośrednio konkretnymi cenami (rabatami, rabatami ilościowymi) ani wpływami cenowymi kombinacji produktów. Jeśli masz ustawione konkretne ceny, zmiana ceny bazowej wpłynie na punkt początkowy dla tych konkretnych cen.

**P4: Czy możliwe jest aktualizowanie cen tylko dla konkretnych kategorii lub producentów?**
O4: Nie, ta darmowa wersja modułu wykonuje masową aktualizację *wszystkich* produktów w Twoim sklepie. Nie oferuje filtrowania według kategorii, producenta ani innych kryteriów. W przypadku bardziej zaawansowanych, filtrowanych aktualizacji cen, zazwyczaj potrzebny jest bardziej wyrafinowany, często płatny, moduł importu/eksportu lub masowej aktualizacji.

**P5: Moduł wydaje się zablokowany lub nie reaguje, gdy klikam „Zastosuj zmiany”.**
O5: W przypadku sklepów z bardzo dużą liczbą produktów (tysiące), proces aktualizacji może zająć trochę czasu.
\* Upewnij się, że limit czasu wykonywania PHP na Twoim serwerze jest wystarczający. Możesz zobaczyć „Błąd wewnętrzny serwera 500” lub przekroczenie limitu czasu, jeśli jest zbyt niski. Jest to problem konfiguracji serwera, a nie błąd modułu.
\* Sprawdź dzienniki błędów PrestaShop (znajdujące się w `var/logs/` w PrestaShop 1.7/8/9) pod kątem konkretnych błędów.
\* Jeśli problem nadal występuje, skontaktuj się z dostawcą hostingu lub programistą internetowym, aby sprawdzić dzienniki serwera i ustawienia PHP.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Darmowa masowa aktualizacja cen produktów” to prosty moduł PrestaShop zaprojektowany głównie do administracji Back Office. Wykorzystuje podstawową strukturę modułu PrestaShop, korzystając z klasy `Module` i jej metody `getContent()` do konfiguracji. Bezpośrednio wchodzi w interakcje z bazą danych PrestaShop w celu aktualizacji cen produktów bez niestandardowych kontrolerów, modeli ani złożonych interakcji JavaScript. Logika modułu jest zawarta w jego głównym pliku PHP.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** wykorzystuje żadnych niestandardowych kontrolerów Front Office ani Back Office. Cała funkcjonalność jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Bezpośrednio wchodzi w interakcje z metodami `Product` i `Product::updatePrice()` dostarczonymi przez rdzeń PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Stylizacja strony konfiguracji jest obsługiwana przez domyślny motyw Back Office PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa dwóch prostych szablonów Smarty:

-   **`masspricefree/views/advert.tpl`**:
    *   **Zakres:** Back Office (strona konfiguracji modułu).
    *   **Cel:** Prawdopodobnie używany do wyświetlania reklamy lub wiadomości promocyjnej od MyPresta.eu w interfejsie konfiguracji modułu. Zazwyczaj jest renderowany na górze lub na dole wyjścia `getContent()`.
-   **`masspricefree/views/script.tpl`**:
    *   **Zakres:** Back Office (strona konfiguracji modułu).
    *   **Cel:** Ten szablon może zawierać wbudowany kod JavaScript lub proste elementy HTML, które są częścią formularza konfiguracji modułu, chociaż opis modułu sugeruje minimalny JS. Biorąc pod uwagę prostotę modułu, bardziej prawdopodobne jest, że jest to symbol zastępczy lub zawiera bardzo podstawowe elementy interfejsu użytkownika.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych.
    *   Bezpośrednio modyfikuje dane w tabeli `ps_product` (konkretnie kolumnę `price`) i potencjalnie `ps_product_shop` (dla kontekstów wielu sklepów) poprzez wywoływanie podstawowych metod PrestaShop.
    *   Ustawienia konfiguracji (Typ korekty ceny, Wartość procentowa) są przechowywane w tabeli `ps_configuration` przy użyciu standardowych kluczy konfiguracji PrestaShop (np. `PS_MASS_PRICE_FREE_TYPE`, `PS_MASS_PRICE_FREE_VALUE`).
-   **Tabela zarejestrowanych hooków**:
    Ten moduł **nie** rejestruje żadnych konkretnych hooków do wyświetlania w Front Office ani akcji w Back Office poza standardowymi `displayBackOfficeHeader` (niejawnie dla konfiguracji modułu) i `actionModuleInstall`/`actionModuleUninstall`. Jego główną funkcją jest bezpośrednia manipulacja bazą danych wyzwalana przez przesłanie formularza administracyjnego.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` Back Office. | Używane przez `getContent()` do potencjalnego ładowania zasobów lub wyświetlania powiadomień, chociaż nie jest jawnie używane do niestandardowych zasobów w tym module. |
| `actionModuleInstall` | Wyzwalane podczas instalacji modułu. | Używane do ustawiania domyślnych wartości konfiguracji w `ps_configuration`. |
| `actionModuleUninstall` | Wyzwalane podczas deinstalacji modułu. | Używane do usuwania wartości konfiguracji z `ps_configuration`. |

### 4.8 Główny plik modułu (`masspricefree/index.php`)

Główna logika znajduje się w `masspricefree/index.php`.

-   **Nazwa klasy:** `MassPriceFree`
-   **Klasa nadrzędna:** `Module`
-   **Kluczowe metody:**
    *   `__construct()`: Inicjalizuje właściwości modułu (nazwa, zakładka, wersja, autor, `need_instance`, `bootstrap`).
    *   `install()`: Rejestruje moduł, ustawia domyślne wartości konfiguracji (np. `PS_MASS_PRICE_FREE_TYPE` na „increase”, `PS_MASS_PRICE_FREE_VALUE` na „0”).
    *   `uninstall()`: Usuwa wartości konfiguracji.
    *   `getContent()`: Jest to główna metoda funkcjonalności modułu.
        *   Obsługuje przesłanie formularza (`Tools::isSubmit('submitMassPriceFree')`).
        *   Pobiera `price_type` i `price_value` z przesłanego formularza.
        *   Aktualizuje `ps_configuration` nowymi ustawieniami.
        *   **Co najważniejsze, iteruje przez wszystkie aktywne produkty (`Product::getProducts(Context::getContext()->language->id, 0, 0, 'id_product', 'ASC', false, true)`) i aktualizuje ich ceny na podstawie skonfigurowanego procentu i typu.** Używa do tego `Product::updatePrice()`.
        *   Renderuje formularz konfiguracji za pomocą `displayForm()` i zawiera szablony `advert.tpl` oraz `script.tpl`.
    *   `displayForm()`: Generuje kod HTML dla formularza konfiguracji modułu, w tym przyciski radiowe dla zwiększania/zmniejszania i pole wprowadzania wartości procentowej.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia dla modułu „Darmowa masowa aktualizacja cen produktów”, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
