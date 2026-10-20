---
title: "Specials Homepage Tab - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Specials Homepage Tab” od MyPresta.eu."
sidebar:
  label: "Specials Homepage Tab - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Specials Homepage Tab na MyPresta.eu](https://mypresta.eu/modules/front-office-features/specials-homepage-tab.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/specials-homepage-tab/)
>
> ---


# Specials Homepage Tab

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Specials Homepage Tab”, aby uzyskać dostęp do jego ustawień.

#### Ustawienia i opcje:

-   **Liczba produktów**

    -   **Co robi to ustawienie:** Kontroluje, ile produktów objętych ofertą specjalną zostanie wyświetlonych w zakładce „Promocje” na Twojej stronie głównej.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po ustawieniu na wyższą liczbę (np. 12):* Więcej produktów będzie widocznych w zakładce, dając klientom szerszy wybór ofert. Może to wymagać więcej przewijania lub paginacji w zależności od Twojego motywu.
        -   *Po ustawieniu na niższą liczbę (np. 4):* Mniej produktów zostanie wyświetlonych, tworząc bardziej zwięzły widok. Może to być przydatne, jeśli chcesz wyróżnić tylko swoje najlepsze oferty lub utrzymać stronę główną w czystości.
    -   **Zalecana wartość:** Zacznij od liczby, która dobrze pasuje do projektu Twojego motywu (np. 8 lub 12) i dostosuj ją w zależności od tego, ile ofert specjalnych zazwyczaj masz i ile miejsca chcesz, aby zajmowały.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz wiele produktów w promocji i chcesz pokazać różnorodność, ustaw na 12. Jeśli wolisz minimalistyczną stronę główną i chcesz wyróżnić tylko kilka gwiazdorskich ofert, ustaw na 4.
-   **Produkty losowe**

    -   **Co robi to ustawienie:** Określa, czy produkty objęte ofertą specjalną wyświetlane w zakładce są pokazywane w stałej kolejności (np. według ID, daty dodania) czy w losowej kolejności za każdym razem, gdy strona jest ładowana.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu (TAK):* Za każdym razem, gdy klient odwiedza Twoją stronę główną, kolejność produktów w zakładce „Promocje” będzie losowa. Zapewnia to widoczność różnych produktów i zapobiega, aby te same kilka pozycji zawsze znajdowało się na górze.
        -   *Po wyłączeniu (NIE):* Produkty będą wyświetlane w spójnej, nielosowej kolejności (zazwyczaj według ID produktu lub daty utworzenia, w zależności od domyślnego sortowania promocji w PrestaShop). Oznacza to, że te same produkty zawsze będą pojawiać się jako pierwsze.
    -   **Zalecana wartość:** **TAK**. Losowanie produktów jest ogólnie zalecane, aby dać wszystkim Twoim ofertom specjalnym uczciwą szansę na zobaczenie i aby strona główna była świeża dla powracających klientów.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz 20 produktów w promocji, ale wyświetlasz tylko 8, włączenie „Produktów losowych” zapewnia, że z czasem wszystkie 20 produktów ostatecznie pojawi się w zakładce, a nie tylko pierwsze 8.

#### Inne klucze konfiguracyjne (Wewnętrzne ustawienia PrestaShop):

Moduł współpracuje również z kilkoma kluczowymi kluczami konfiguracyjnymi PrestaShop. Chociaż nie są one bezpośrednio konfigurowalne w samym module, zrozumienie ich celu pomaga w rozwiązywaniu problemów lub zaawansowanej personalizacji:

-   `PS_CATALOG_MODE`: Jeśli Twój sklep jest w trybie katalogowym (bez cen, bez dodawania do koszyka), ceny specjalne nie będą istotne.
-   `PS_LANG_DEFAULT`: Domyślny język Twojego sklepu, używany do pobierania nazw i opisów produktów.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Określa, czy pracownicy mogą zmieniać język formularzy w panelu administracyjnym.
-   `PS_TAX_ADDRESS_TYPE`: Sposób obliczania podatków (np. na podstawie adresu dostawy lub faktury).
-   `PS_COUNTRY_DEFAULT`: Domyślny kraj dla Twojego sklepu, wpływający na obliczenia podatków i wysyłki.
-   `PS_NB_DAYS_NEW_PRODUCT`: Liczba dni, przez które produkt jest uważany za „nowy”. (Nie jest bezpośrednio związany z promocjami, ale często występuje w modułach, które listują produkty).

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Liczba produktów | 8-12 (Dostosuj do motywu) | Określa, ile produktów objętych ofertą specjalną jest wyświetlanych w zakładce. |
| Konfiguracja modułu | Produkty losowe | TAK | Losuje kolejność produktów w zakładce dla świeżego wyświetlania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moja zakładka „Promocje” jest pusta lub nie wyświetla żadnych produktów, mimo że mam produkty w promocji.**

-   **O:** Po pierwsze, upewnij się, że Twoje produkty są poprawnie oznaczone jako „w promocji” w ich ustawieniach produktu w panelu administracyjnym PrestaShop (w zakładce „Ceny” upewnij się, że „Ceny specyficzne” są skonfigurowane i aktywne). Sprawdź również ustawienie „Liczba produktów” w konfiguracji modułu; jeśli jest ustawione na 0, żadne produkty nie zostaną wyświetlone. Na koniec wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).

**P2: Zakładka „Promocje” w ogóle nie pojawia się na mojej stronie głównej.**

-   **O:**
    1.  **Moduł włączony:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Specials Homepage Tab” jest włączony.
    2.  **Poprawnie podpięty:** Moduł używa `displayHomeTab` i `displayHomeTabContent`. Twój motyw musi obsługiwać te hooki, aby zakładka się pojawiła. Większość standardowych motywów PrestaShop to robi. Jeśli używasz mocno spersonalizowanego motywu, może on nie wywoływać tych hooków.
    3.  **Pamięć podręczna:** Zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) po zainstalowaniu lub skonfigurowaniu modułów.
    4.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, bardzo stare lub mocno spersonalizowane motywy mogą wymagać drobnych korekt. Jeśli problemy nadal występują, skontaktuj się z pomocą techniczną MyPresta.eu.

**P3: Produkty w zakładce „Promocje” nie wyglądają dobrze lub nie pasują do projektu mojego motywu.**

-   **O:** Moduł wykorzystuje istniejące style Twojego motywu dla list produktów. Jeśli produkty wyglądają niepoprawnie, zazwyczaj jest to problem z CSS Twojego motywu, a nie samego modułu.
    -   **Sprawdź CSS motywu:** Przejrzyj CSS swojego motywu pod kątem stylów list produktów.
    -   **Niestandardowy CSS:** Może być konieczne dodanie niestandardowego CSS do pliku `custom.css` Twojego motywu (jeśli jest dostępny) lub bezpośrednia edycja arkusza stylów Twojego motywu w celu dostosowania wyglądu.
    -   **Responsywność mobilna:** Przetestuj na różnych urządzeniach. Jeśli wygląda dobrze na komputerze stacjonarnym, ale nie na urządzeniach mobilnych, jest to problem z responsywnością CSS Twojego motywu.

**P4: Czy mogę zmienić tytuł zakładki „Promocje” (np. na „Okazje” lub „Oferty”)?**

-   **O:** Moduł używa domyślnego tłumaczenia PrestaShop dla „Promocje”. Aby to zmienić, zazwyczaj należy przejść do **Lokalizacja > Tłumaczenia**, wybrać „Tłumaczenia zainstalowanych modułów”, wybrać swój motyw, a następnie znaleźć moduł „Specials Homepage Tab”. Następnie możesz edytować tłumaczenie tytułu zakładki.

**P5: Dlaczego niektóre produkty, które są w promocji, nie pojawiają się w zakładce?**

-   **O:**
    1.  **Limit liczby produktów:** Sprawdź ustawienie „Liczba produktów” w konfiguracji modułu. Jeśli masz więcej promocji niż ten limit, wyświetli się tylko pierwsza (lub losowa, jeśli włączono) grupa.
    2.  **Widoczność produktu:** Upewnij się, że produkt jest aktywny, widoczny i ma skonfigurowaną rzeczywistą cenę specyficzną (nie tylko zwykłą obniżkę ceny).
    3.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Specials Homepage Tab” (`blockspecialstab`) to lekki moduł PrestaShop, skupiający się głównie na wyświetlaniu w front-office. Przestrzega standardowej architektury modułów PrestaShop, wykorzystując hooki do wstrzykiwania treści na stronę główną. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonego JavaScript/CSS poza tym, co jest niezbędne do podstawowego szablonowania. Jego podstawowa funkcjonalność obraca się wokół pobierania produktów z cenami specyficznymi i renderowania ich w strukturze zakładek.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest hermetyzowana w głównej klasie modułu (`blockspecialstab.php`).

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Ten moduł **nie** wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Opiera się na podstawowych klasach PrestaShop `Product` i `SpecificPrice` do pobierania danych produktów.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność przełączania zakładek i wyświetlanie produktów są obsługiwane przez istniejący JavaScript motywu (np. jQuery, Bootstrap JS), który zazwyczaj zarządza interakcjami `displayHomeTab` i `displayHomeTabContent`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Jest zaprojektowany tak, aby dziedziczyć stylizację aktywnego motywu PrestaShop dla list produktów, zapewniając bezproblemową integrację. Programiści powinni odwołać się do CSS swojego motywu w celu stylizacji siatek produktów i zakładek.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa dwóch głównych szablonów Smarty, oba znajdujące się w katalogu `views/templates/hook/`, do renderowania zakładki i jej zawartości.

-   **`blockspecialstab/views/templates/hook/blockspecialstab.tpl`**

    -   **Cel:** Ten szablon jest odpowiedzialny za renderowanie *nagłówka* zakładki „Promocje”, który pojawia się obok innych zakładek (np. „Nowości”).
    -   **Hook:** Renderowany głównie za pomocą `displayHomeTab`.
    -   **Wyjście:** Zazwyczaj wyprowadza element `<li>` zawierający tag `<a>` z linkiem do zawartości zakładki (np. `#blockspecialstab`).
    -   **Kluczowe elementy dla programistów:**
        -   `id="home-page-tabs"`: Kontener dla wszystkich zakładek strony głównej (zazwyczaj w motywie).
        -   `id="blockspecialstab"`: ID samej zakładki, używane do linkowania do jej zawartości.
        -   `{l s='Specials' mod='blockspecialstab'}`: Tekst do przetłumaczenia dla tytułu zakładki.
-   **`blockspecialstab/views/templates/hook/blockspecialstabcontents.tpl`**

    -   **Cel:** Ten szablon renderuje *zawartość*, która pojawia się po kliknięciu zakładki „Promocje”. Zawiera rzeczywistą listę produktów objętych ofertą specjalną.
    -   **Hook:** Renderowany głównie za pomocą `displayHomeTabContent`.
    -   **Wyjście:** Zazwyczaj wyprowadza element `<div>` zawierający pętlę, która iteruje przez zmienną `$products` (przekazaną z modułu) i wyświetla każdy produkt za pomocą wspólnego fragmentu listy produktów z motywu (np. `product-list.tpl` lub podobny fragment).
    -   **Kluczowe elementy dla programistów:**
        -   `id="blockspecialstab"`: ID bloku zawartości, pasujące do nagłówka zakładki.
        -   `{$products}`: Tablica obiektów `Product` (lub tablic asocjacyjnych reprezentujących produkty) przekazana z modułu, zawierająca szczegóły takie jak ID, nazwa, cena, obraz itp.
        -   `{include file='catalog/_partials/miniatures/product.tpl' product=$product}` (przykład dla PS 1.7/8): Moduł zazwyczaj używa standardowego fragmentu motywu do renderowania każdego produktu, zapewniając spójną stylizację. Programiści powinni sprawdzić plik `_partials/miniatures/product.tpl` lub `product-list.tpl` swojego motywu, aby dowiedzieć się, jak renderowane są poszczególne produkty.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` za pomocą kluczy takich jak `BLOCKSTAB_NB_CACHES` (starsze), `BLOCKSTABS_NB_CACHES` (aktualne) i `BLOCKSTABS_RAND`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHomeTab` | Renderuje w obszarze nawigacji zakładek strony głównej. | Wstrzykuje nagłówek zakładki „Promocje” (`blockspecialstab.tpl`) do głównej listy zakładek strony głównej. |
| `displayHomeTabContent` | Renderuje w obszarze zawartości strony głównej, odpowiadającym zakładce. | Wstrzykuje listę produktów objętych ofertą specjalną (`blockspecialstabcontents.tpl`), gdy zakładka „Promocje” jest aktywna. |
| `addproduct` | Po dodaniu produktu. | Czyści wewnętrzną pamięć podręczną modułu, aby upewnić się, że nowe produkty są brane pod uwagę w promocjach. |
| `updateproduct` | Po zaktualizowaniu produktu. | Czyści wewnętrzną pamięć podręczną modułu, aby odzwierciedlić zmiany w cenach lub statusie produktów. |
| `deleteproduct` | Po usunięciu produktu. | Czyści wewnętrzną pamięć podręczną modułu, aby usunąć usunięte produkty z promocji. |
| `displayAddProduct` | (Starszy hook, często używany do formularzy administracyjnych) | Czyści wewnętrzną pamięć podręczną modułu. |
| `displayUpdateProduct` | (Starszy hook, często używany do formularzy administracyjnych) | Czyści wewnętrzną pamięć podręczną modułu. |
| `displayDeleteProduct` | (Starszy hook, często używany do formularzy administracyjnych) | Czyści wewnętrzną pamięć podręczną modułu. |

Hooki `addproduct`, `updateproduct`, `deleteproduct`, `displayAddProduct`, `displayUpdateProduct` i `displayDeleteProduct` są używane głównie do wywołania czyszczenia pamięci podręcznej w module. Zapewnia to, że lista produktów specjalnych wyświetlanych na stronie głównej jest zawsze aktualna, gdy zmieniają się informacje o produkcie (zwłaszcza ceny lub status).

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Specials Homepage Tab”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
