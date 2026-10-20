---
title: "Zakładka CMS na stronie produktu - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Zakładka CMS na stronie produktu” od MyPresta.eu."
sidebar:
  label: "Zakładka CMS na stronie produktu - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product page CMS tab na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-cms-tab.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-page-cms-tab/)
>
> ---


# Zakładka CMS na stronie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są domyślnie dostępne w większości środowisk hostingowych. Dla tego modułu nie są potrzebne żadne specjalne ani nietypowe rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Zakładka CMS na stronie produktu” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji.

#### **Wybierz stronę CMS do wyświetlenia jako zakładka**

Jest to kluczowe ustawienie modułu. Określa, która z istniejących stron CMS zostanie wyświetlona jako nowa zakładka na wszystkich stronach produktów.

-   **Co robi to ustawienie:** To rozwijane menu zawiera listę wszystkich stron CMS, które utworzyłeś w swoim sklepie PrestaShop (znajdujące się w **Wygląd > Strony** lub **Wygląd > CMS** w starszych wersjach). Musisz wybrać jedną z tych stron.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy strona CMS jest wybrana:* Nowa zakładka pojawi się na każdej stronie produktu w Twoim sklepie. Tytuł tej zakładki będzie tytułem wybranej strony CMS, a zawartość wyświetlana po kliknięciu zakładki będzie zawartością tej strony CMS.
    -   *Gdy wybrano „--- Wybierz ---”:* Na stronach produktów nie pojawi się żadna nowa zakładka. Moduł będzie faktycznie nieaktywny pod względem wyświetlania w front-office.
-   **Zalecana wartość:** Wybierz stronę CMS, która zawiera informacje, które chcesz udostępnić uniwersalnie na wszystkich stronach produktów (np. strona „Informacje o wysyłce”, „Tabela rozmiarów” lub „Szczegóły gwarancji”).
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz udostępnić szczegółową „Tabelę rozmiarów” dla wszystkich produktów odzieżowych. Najpierw utworzysz stronę CMS zatytułowaną „Tabela rozmiarów” ze wszystkimi odpowiednimi informacjami. Następnie w konfiguracji tego modułu wybierzesz „Tabela rozmiarów” z rozwijanego menu. Teraz każda strona produktu będzie miała zakładkę „Tabela rozmiarów”.

#### **Typ zakładki**

To ustawienie kontroluje sposób integracji modułu z systemem zakładek PrestaShop, szczególnie dla różnych wersji PrestaShop.

-   **Co robi to ustawienie:** To rozwijane menu pozwala wybrać metodę, której moduł używa do wyświetlania zakładki. Jest to przede wszystkim ustawienie kompatybilności dla różnych wersji PrestaShop.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy wybrano „PrestaShop 1.7 / 8.x / 9.x”:* Moduł użyje hooka `displayProductExtraContent`, który jest standardowym i zalecanym sposobem dodawania nowych zakładek w nowoczesnych wersjach PrestaShop. Zapewnia to natywny wygląd i działanie.
    -   *Gdy wybrano „PrestaShop 1.6”:* Moduł użyje starszych hooków, takich jak `productTab` i `productTabContent`, które były standardem w PrestaShop 1.6. Ta opcja służy do zapewnienia wstecznej kompatybilności, jeśli używasz starszego, nieobsługiwanego sklepu PrestaShop 1.6 (chociaż moduł jest oficjalnie przeznaczony dla 1.7+).
-   **Zalecana wartość:** Dla sklepów PrestaShop 1.7, 8.x i 9.x zawsze wybieraj **„PrestaShop 1.7 / 8.x / 9.x”**.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli używasz PrestaShop 8.1, wybierzesz „PrestaShop 1.7 / 8.x / 9.x”, aby zapewnić prawidłowe wyświetlanie zakładki i płynną integrację z projektem Twojego motywu. Jeśli z jakiegoś powodu używałbyś tego modułu w starym sklepie PrestaShop 1.6, wybrałbyś „PrestaShop 1.6”.

#### **MyPresta.eu Aktualizacje na żywo**

Ta sekcja jest wspólna dla modułów MyPresta.eu i pomaga zarządzać aktualizacjami modułów.

-   **Co robi to ustawienie:** Ta funkcja sprawdza dostępność nowych wersji modułu bezpośrednio z MyPresta.eu.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Moduł będzie okresowo sprawdzał dostępność aktualizacji. Jeśli dostępna jest nowa wersja, zobaczysz powiadomienie na liście modułów lub na stronie konfiguracji modułu. Pomaga to być na bieżąco z poprawkami błędów i nowymi funkcjami.
    -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał dostępności aktualizacji. Musiałbyś ręcznie sprawdzić swoje konto MyPresta.eu pod kątem nowych wersji.
-   **Zalecana wartość:** **TAK**. Utrzymywanie modułów w aktualności jest kluczowe dla bezpieczeństwa, kompatybilności i dostępu do najnowszych funkcji.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Twój moduł zawsze ma najnowsze poprawki bezpieczeństwa. Włączając tę opcję, zostaniesz powiadomiony, gdy dostępna będzie aktualizacja, co skłoni Cię do jej pobrania i zainstalowania.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Wybierz stronę CMS do wyświetlenia jako zakładka** | --- Wybierz --- / Wybrana strona CMS | Określa, która zawartość strony CMS pojawi się jako nowa zakładka na wszystkich stronach produktów. |
| Strona konfiguracji modułu | **Typ zakładki** | PrestaShop 1.7 / 8.x / 9.x | Zapewnia prawidłowe wyświetlanie zakładki i integrację z architekturą Twojej wersji PrestaShop. |
| Strona konfiguracji modułu | **MyPresta.eu Aktualizacje na żywo** | TAK | Włącza automatyczne sprawdzanie aktualizacji modułu z MyPresta.eu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Nowa zakładka nie pojawia się na moich stronach produktów. Co powinienem zrobić?**
O:

1.  **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Zakładka CMS na stronie produktu” i kliknij „Konfiguruj”. Upewnij się, że wybrałeś prawidłową stronę CMS z rozwijanego menu „Wybierz stronę CMS do wyświetlenia jako zakładka”. Jeśli wybrano „--- Wybierz ---”, zakładka się nie pojawi.
2.  **Sprawdź typ zakładki:** Upewnij się, że „Typ zakładki” jest ustawiony na „PrestaShop 1.7 / 8.x / 9.x” dla nowoczesnych wersji PrestaShop.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się zmian.
4.  **Sprawdź status strony CMS:** Upewnij się, że wybrana strona CMS jest aktywna i publicznie widoczna (nie wyłączona ani prywatna). Możesz to sprawdzić w **Wygląd > Strony**.
5.  **Kompatybilność motywu:** Chociaż moduł używa standardowych hooków PrestaShop, bardzo mocno dostosowane motywy mogą czasami kolidować. Jeśli powyższe kroki nie działają, tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy zakładka się pojawi. Jeśli tak, Twój motyw może wymagać niewielkiej korekty.

**P: Czy mogę mieć różne zakładki CMS dla różnych produktów?**
O: Ten moduł jest przeznaczony do wyświetlania *jednej konkretnej strony CMS* jako zakładki na *wszystkich* stronach produktów. Nie obsługuje przypisywania różnych stron CMS do poszczególnych produktów. Jeśli potrzebujesz zakładek specyficznych dla produktu, zazwyczaj potrzebujesz bardziej zaawansowanego modułu lub niestandardowego rozwoju.

**P: Treść w zakładce wygląda dziwnie lub jest nieostylowana.**
O: Moduł po prostu pobiera zawartość z Twojej strony CMS. Stylizacja tej zawartości jest zazwyczaj obsługiwana przez CSS Twojego motywu PrestaShop.

1.  **Sprawdź zawartość strony CMS:** Upewnij się, że zawartość na oryginalnej stronie CMS (w **Wygląd > Strony**) jest poprawnie sformatowana i nie zawiera uszkodzonego kodu HTML.
2.  **CSS motywu:** CSS Twojego motywu może nie mieć specyficznych stylów dla treści w zakładkach produktów lub może nadpisywać domyślne style. Jeśli masz programistę, może on zbadać stronę, aby zidentyfikować i naprawić wszelkie konflikty stylów.

**P: Zaktualizowałem moją stronę CMS, ale zawartość zakładki na stronach produktów się nie zmieniła.**
O: Po zaktualizowaniu strony CMS zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Twój sklep może serwować starszą, buforowaną wersję treści.

**P: Jak przetłumaczyć tytuł zakładki, jeśli mój sklep jest wielojęzyczny?**
O: Tytuł zakładki jest automatycznie pobierany z tytułu wybranej strony CMS. Aby go przetłumaczyć, musisz edytować samą stronę CMS (**Wygląd > Strony**) i podać tłumaczenia jej tytułu i treści dla każdego obsługiwanego języka. Moduł wyświetli wtedy prawidłowy przetłumaczony tytuł w oparciu o wybrany język klienta.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Zakładka CMS na stronie produktu” (`cmstab`) to lekki moduł PrestaShop zaprojektowany do wstrzykiwania istniejącej zawartości strony CMS na strony produktów jako nowej zakładki. Wykorzystuje on głównie system hooków PrestaShop do osiągnięcia tego celu. Główna logika modułu znajduje się w jego głównym pliku PHP, `cmstab.php`, który obsługuje instalację, deinstalację, konfigurację i rejestrację hooków. Nie wprowadza niestandardowych tabel bazy danych ani złożonych ObjectModels, opierając się zamiast tego na natywnej klasie `CMS` PrestaShop do pobierania treści. Moduł udostępnia dwa zestawy szablonów, aby zapewnić kompatybilność z mechanizmami renderowania zakładek PrestaShop 1.6 i 1.7+, wybierane za pomocą konfiguracji w panelu administracyjnym.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała funkcjonalność jest zarządzana za pośrednictwem głównej klasy modułu i systemu hooków PrestaShop.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Bezpośrednio wykorzystuje podstawową klasę `CMS` PrestaShop do pobierania treści na podstawie skonfigurowanego ID strony CMS.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`cmstab/trusted.js`**
    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Cel:** Ten skrypt jest zazwyczaj dołączany do modułów MyPresta.eu w celu obsługi funkcji „MyPresta.eu Aktualizacje na żywo”. Komunikuje się z API MyPresta.eu, aby sprawdzać dostępność nowych wersji modułu i wyświetlać powiadomienia o aktualizacjach w panelu administracyjnym PrestaShop. Nie wpływa na wyświetlanie w front-office ani interakcję z klientem.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja zakładki i jej zawartości jest dziedziczona z aktywnego motywu PrestaShop. Deweloperzy, którzy chcą stylizować zakładkę, powinni celować w odpowiednie selektory dostarczone przez motyw lub podstawowy system zakładek PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł udostępnia dwa zestawy szablonów, aby dostosować się do różnych podejść do renderowania zakładek w różnych wersjach PrestaShop. Konkretny używany zestaw jest określany przez ustawienie „Typ zakładki” w konfiguracji modułu.

-   **Szablony hooków (`views/templates/hook/`)**: Ten katalog nie jest jawnie używany do bezpośredniego renderowania hooków w tym module. Szablony są bezpośrednio odwoływane z `views/front/`.
-   **Szablony front-office (`views/templates/front/`)**:

    -   **`cmstab/views/front/tab.tpl`**

        -   **Cel:** Ten szablon jest przeznaczony dla kompatybilności z PrestaShop 1.6. Jest renderowany, gdy „Typ zakładki” jest ustawiony na „PrestaShop 1.6”. Wyświetla kod HTML dla *nagłówka* zakładki (części zakładki, którą można kliknąć) używając tytułu strony CMS.
        -   **Hook:** `productTab` (specyficzny dla PrestaShop 1.6)
        -   **Zmienne:** `$cmstab_title` (tytuł wybranej strony CMS).
    -   **`cmstab/views/front/tab16.tpl`**

        -   **Cel:** Ten szablon jest również przeznaczony dla kompatybilności z PrestaShop 1.6. Wyświetla kod HTML dla *obszaru zawartości* zakładki, pokazując rzeczywistą zawartość wybranej strony CMS.
        -   **Hook:** `productTabContent` (specyficzny dla PrestaShop 1.6)
        -   **Zmienne:** `$cmstab_content` (zawartość HTML wybranej strony CMS).
    -   **`cmstab/views/front/tabcontents.tpl`**

        -   **Cel:** Ten szablon jest przeznaczony dla kompatybilności z PrestaShop 1.7, 8.x i 9.x. Jest renderowany, gdy „Typ zakładki” jest ustawiony na „PrestaShop 1.7 / 8.x / 9.x”. Wyświetla całą strukturę zakładki, w tym zarówno nagłówek zakładki, jak i jej zawartość, zgodnie z oczekiwaniami hooka `displayProductExtraContent`.
        -   **Hook:** `displayProductExtraContent` (standard PrestaShop 1.7+)
        -   **Zmienne:**
            -   `$cmstab_title`: Tytuł wybranej strony CMS.
            -   `$cmstab_content`: Zawartość HTML wybranej strony CMS.
            -   `$cmstab_id`: Unikalny identyfikator zakładki, pochodzący z ID strony CMS.
    -   **`cmstab/views/front/tabcontents16.tpl`**

        -   **Cel:** Ten szablon wydaje się być redundantną lub alternatywną wersją `tab16.tpl` lub `tabcontents.tpl`, prawdopodobnie dla specyficznych scenariuszy 1.6 lub starszej implementacji. Biorąc pod uwagę obecną logikę modułu, `tabcontents.tpl` jest używany dla 1.7+, a `tab.tpl`/`tab16.tpl` dla 1.6. Deweloperzy powinni skupić się przede wszystkim na `tabcontents.tpl` dla nowoczesnych wersji PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop:
        -   `CMSTAB_ID`: Przechowuje ID wybranej strony CMS.
        -   `CMSTAB_TYPE`: Przechowuje wybrany typ zakładki (np. '17' dla PrestaShop 1.7+, '16' dla PrestaShop 1.6).
        -   `MYPRESTA_UPDATES`: Przechowuje ustawienie dla aktualizacji na żywo.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Używany przez moduł do rejestrowania swojego JavaScriptu dla aktualizacji na żywo w panelu administracyjnym. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony panelu administracyjnego. | Używany przez moduł do rejestrowania swojego JavaScriptu dla aktualizacji na żywo w panelu administracyjnym. |
| `displayProductExtraContent` | Na stronach produktów, do dodawania nowych zakładek (PrestaShop 1.7+). | Główny hook do renderowania zakładki CMS i jej zawartości w nowoczesnych wersjach PrestaShop. |
| `productTab` | Na stronach produktów, do dodawania nowych nagłówków zakładek (PrestaShop 1.6). | Używany do wstecznej kompatybilności do renderowania nagłówka zakładki w PrestaShop 1.6. |
| `productTabContent` | Na stronach produktów, do dodawania nowej zawartości zakładek (PrestaShop 1.6). | Używany do wstecznej kompatybilności do renderowania zawartości zakładki w PrestaShop 1.6. |
| `actionAdminControllerSetMedia` | Gdy kontroler administratora ustawia swoje zasoby multimedialne. | Używany przez moduł do rejestrowania swojego JavaScriptu dla aktualizacji na żywo w panelu administracyjnym. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji modułu, poprawek błędów i profesjonalnego wsparcia, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w świadczenie terminowej pomocy i zapewnienie optymalnej wydajności Twoich modułów.
