---
title: "GPSR Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop GPSR Free od MyPresta.eu."
sidebar:
  label: "GPSR Free"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł GPSR Free na MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/gpsr-free/)
>
> ---


# GPSR Free

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > GPSR Free)

Jest to główny ekran konfiguracji modułu GPSR Free, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy blok informacji GPSR jest wyświetlany na stronach produktów w front office.
- **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Blok informacji GPSR, zawierający dane producenta, osoby odpowiedzialnej i ostrzeżenia, pojawi się na stronach produktów, dla których przypisano odpowiednie informacje.
    - *Gdy wyłączone (Nie):* Blok informacji GPSR zostanie ukryty ze wszystkich stron produktów, niezależnie od skonfigurowanych przypisań.
- **Zalecana wartość:** **Tak**. Aby zachować zgodność z GPSR i wyświetlać informacje, to ustawienie powinno być włączone.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli aktywnie konfigurujesz dane GPSR i chcesz, aby były widoczne dla klientów, włącz to ustawienie. Jeśli nadal jesteś w trakcie konfiguracji danych lub tymczasowo chcesz ukryć blok (np. podczas przeprojektowywania witryny), możesz go wyłączyć.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł GPSR Free dodaje kilka nowych pozycji menu w głównej sekcji „GPSR Free” w Panelu Administracyjnym PrestaShop. Ekrany te umożliwiają zarządzanie różnymi fragmentami informacji wymaganymi do zgodności z GPSR.

#### 2.2.1 Panel GPSR Free (Panel administracyjny > GPSR Free > Panel)
Ten ekran służy jako główny punkt wejścia do dedykowanej administracji modułu. Zazwyczaj zapewnia przegląd lub szybkie linki do innych sekcji zarządzania.

- **Dostępne akcje i ustawienia:** Ten widok zazwyczaj przedstawia interfejs przypominający panel, potencjalnie pokazujący statystyki lub szybkie linki do zarządzania producentami, podmiotami, ostrzeżeniami i mapami produktów.
- **Efekt zmian:** Sam ten ekran nie posiada bezpośrednich ustawień, które zmieniają zachowanie front-office, ale jest Twoim centrum nawigacyjnym dla wszystkich danych GPSR.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Zacznij tutaj, aby uzyskać przegląd, a następnie przejdź do konkretnych sekcji (Producenci, Podmioty, Ostrzeżenia, Mapa Produktów), aby dodać lub zmodyfikować dane.

#### 2.2.2 Producenci (Panel administracyjny > GPSR Free > Producenci)
Ten ekran umożliwia definiowanie i zarządzanie producentami Twoich produktów.

- **Dostępne akcje i ustawienia:**
    - **Tabela listy:** Wyświetla wszystkich dodanych producentów, z kolumnami dla nazwy, adresu i akcji, takich jak „Edytuj” lub „Usuń”.
    - **Przycisk „Dodaj nowego producenta”:** Kliknięcie tego przycisku otwiera formularz do tworzenia nowego wpisu producenta.
    - **Pola formularza (do dodawania/edycji producenta):**
        - **Nazwa:** Oficjalna nazwa producenta.
        - **Adres:** Pełny adres pocztowy producenta.
        - **Czy producent jest z UE?**: Przełącznik wskazujący, czy producent ma siedzibę w Unii Europejskiej. Jest to kluczowe dla określenia, czy należy przypisać „Osobę odpowiedzialną w UE”.
- **Efekt zmian:** Dodawanie lub edytowanie producentów tutaj tworzy lub aktualizuje centralną listę producentów, którą można następnie powiązać z produktami. Informacje te będą wyświetlane na stronach produktów, jeśli zostaną przypisane.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Przed przypisaniem produktów upewnij się, że wszyscy producenci Twoich produktów są tutaj wymienieni z dokładnymi danymi. Jeśli nowa linia produktów pochodzi od nowego producenta, dodaj go tutaj najpierw.

#### 2.2.3 Osoby odpowiedzialne w UE (Panel administracyjny > GPSR Free > Osoby odpowiedzialne w UE)
Ten ekran służy do zarządzania „Osobami odpowiedzialnymi w UE” (określanymi również jako „Podmioty” w wewnętrznym nazewnictwie modułu), które są wyznaczone dla produktów wytwarzanych poza UE.

- **Dostępne akcje i ustawienia:**
    - **Tabela listy:** Wyświetla wszystkie zdefiniowane Osoby odpowiedzialne w UE, z ich nazwą, adresem i akcjami.
    - **Przycisk „Dodaj nową osobę odpowiedzialną w UE”:** Otwiera formularz do dodawania nowej osoby odpowiedzialnej.
    - **Pola formularza (do dodawania/edycji Osoby odpowiedzialnej w UE):**
        - **Nazwa:** Nazwa osoby lub podmiotu odpowiedzialnego w UE (np. importer, upoważniony przedstawiciel).
        - **Adres:** Pełny adres pocztowy osoby odpowiedzialnej w UE, znajdujący się w UE.
- **Efekt zmian:** Tworzy lub aktualizuje listę Osób odpowiedzialnych w UE, które mogą być powiązane z producentami spoza UE lub bezpośrednio z produktami. Informacje te są wyświetlane na stronach produktów, gdy ma to zastosowanie.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Jeśli importujesz produkty spoza UE, upewnij się, że masz tutaj wprowadzone prawidłowe dane Osoby odpowiedzialnej w UE.

#### 2.2.4 Ostrzeżenia (Panel administracyjny > GPSR Free > Ostrzeżenia)
Ten ekran umożliwia tworzenie i zarządzanie niestandardowymi ostrzeżeniami lub zastrzeżeniami dotyczącymi bezpieczeństwa.

- **Dostępne akcje i ustawienia:**
    - **Tabela listy:** Wyświetla wszystkie utworzone ostrzeżenia, z ich tekstem i akcjami.
    - **Przycisk „Dodaj nowe ostrzeżenie”:** Otwiera formularz do tworzenia nowego ostrzeżenia.
    - **Pola formularza (do dodawania/edycji ostrzeżenia):**
        - **Tekst ostrzeżenia:** Rzeczywisty tekst ostrzeżenia lub instrukcji dotyczącej bezpieczeństwa. To pole jest zazwyczaj wielojęzyczne, co pozwala na dostarczenie tłumaczeń dla każdego języka włączonego w Twoim sklepie (kontrolowane przez `PS_LANG_DEFAULT`).
- **Efekt zmian:** Dodawanie lub edytowanie ostrzeżeń tutaj tworzy lub aktualizuje pulę ostrzeżeń, które można powiązać z produktami. Wybrane ostrzeżenia pojawią się na stronie produktu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Twórz ogólne ostrzeżenia, które dotyczą wielu produktów (np. „Przechowywać poza zasięgiem dzieci”, „Przeczytaj instrukcję przed użyciem”). Następnie możesz łatwo wybrać je dla poszczególnych produktów.

#### 2.2.5 Mapa Produktów (Panel administracyjny > GPSR Free > Mapa Produktów)
Jest to najważniejszy ekran, na którym łączysz swoje produkty z zdefiniowanymi producentami, osobami odpowiedzialnymi w UE i ostrzeżeniami.

- **Dostępne akcje i ustawienia:**
    - **Tabela listy:** Wyświetla istniejące mapowania produktów, zazwyczaj pokazując nazwę produktu, powiązanego producenta, osobę odpowiedzialną w UE i ostrzeżenia.
    - **Przycisk „Dodaj nowe mapowanie produktu”:** Otwiera formularz do tworzenia nowego mapowania.
    - **Pola formularza (do dodawania/edycji mapowania produktu):**
        - **Wyszukiwanie produktu:** Pole do wyszukiwania i wybierania konkretnego produktu, który chcesz zmapować.
        - **Producent:** Lista rozwijana do wyboru jednego z producentów zdefiniowanych w sekcji „Producenci”.
        - **Osoba odpowiedzialna w UE:** Lista rozwijana do wyboru jednej z Osób odpowiedzialnych w UE, które zdefiniowałeś. To pole może być obowiązkowe lub pojawić się tylko wtedy, gdy wybrany producent *nie* jest producentem z UE.
        - **Ostrzeżenia:** Pole wielokrotnego wyboru lub lista kontrolna do wyboru jednego lub więcej ostrzeżeń z sekcji „Ostrzeżenia” do powiązania z tym produktem.
- **Efekt zmian:** Po zapisaniu mapowania produktu, wybrany producent, osoba odpowiedzialna w UE (jeśli dotyczy) i ostrzeżenia zostaną wyświetlone na stronie produktu w front office dla tego konkretnego produktu, pod warunkiem, że ustawienie „Włącz blok GPSR” jest aktywne.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Po skonfigurowaniu producentów, osób odpowiedzialnych w UE i ostrzeżeń, przejrzyj swój katalog produktów i zmapuj tutaj każdy odpowiedni produkt. To tutaj informacje GPSR są łączone w celu wyświetlenia.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Włącz blok GPSR | Tak | Kontroluje widoczność bloku informacji GPSR na stronach produktów. |
| Producenci | Nazwa | N/A | Oficjalna nazwa producenta produktu. |
| Producenci | Adres | N/A | Pełny adres pocztowy producenta. |
| Producenci | Czy producent jest z UE? | Tak | Wskazuje, czy producent ma siedzibę w UE, wpływając na potrzebę wyznaczenia Osoby odpowiedzialnej w UE. |
| Osoby odpowiedzialne w UE | Nazwa | N/A | Nazwa wyznaczonej Osoby/Podmiotu odpowiedzialnego w UE. |
| Osoby odpowiedzialne w UE | Adres | N/A | Pełny adres pocztowy Osoby odpowiedzialnej w UE w obrębie UE. |
| Ostrzeżenia | Tekst ostrzeżenia | N/A | Rzeczywisty tekst ostrzeżenia lub instrukcji dotyczącej bezpieczeństwa (wielojęzyczny). |
| Mapa Produktów | Produkt | N/A | Wybiera produkt, do którego zostaną przypisane informacje GPSR. |
| Mapa Produktów | Producent | N/A | Powiązuje zdefiniowanego producenta z wybranym produktem. |
| Mapa Produktów | Osoba odpowiedzialna w UE | N/A | Powiązuje zdefiniowaną Osobę odpowiedzialną w UE z wybranym produktem (jeśli producent jest spoza UE). |
| Mapa Produktów | Ostrzeżenia | N/A | Wybiera jedno lub więcej zdefiniowanych ostrzeżeń do wyświetlenia dla produktu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem wszystko, ale blok GPSR nie wyświetla się na moich stronach produktów.**
O:
1.  **Sprawdź „Włącz blok GPSR”:** Przejdź do **Moduły > Menedżer modułów > GPSR Free > Konfiguruj** i upewnij się, że ustawienie „Włącz blok GPSR” jest ustawione na „Tak”.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się nowej zawartości.
3.  **Mapowanie produktu:** Sprawdź dokładnie, czy konkretny produkt, który przeglądasz, został zmapowany w **GPSR Free > Mapa Produktów** z producentem i co najmniej jednym ostrzeżeniem/podmiotem.
4.  **Kompatybilność z motywem:** Chociaż moduł stara się być kompatybilny z większością motywów, bardzo mocno dostosowane motywy mogą wymagać drobnych korekt. Jeśli blok całkowicie brakuje po sprawdzeniu powyższych punktów, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Tekst ostrzeżenia lub dane producenta nie wyświetlają się w prawidłowym języku.**
O:
1.  **Sprawdź tłumaczenia:** Podczas edycji ostrzeżenia lub producenta upewnij się, że dostarczyłeś tłumaczenia dla wszystkich aktywnych języków w Twoim sklepie. Szukaj zakładek językowych obok pól wprowadzania.
2.  **Język domyślny:** Moduł używa domyślnego języka PrestaShop (`PS_LANG_DEFAULT`), jeśli brakuje konkretnego tłumaczenia. Upewnij się, że Twój domyślny język jest poprawnie ustawiony w **Międzynarodowe > Lokalizacja**.

**P: Jak usunąć dane przykładowe zainstalowane z modułem?**
O: Możesz przejść do każdego odpowiedniego ekranu zarządzania (**GPSR Free > Producenci**, **GPSR Free > Osoby odpowiedzialne w UE**, **GPSR Free > Ostrzeżenia**, **GPSR Free > Mapa Produktów**) i użyć akcji „Usuń” dla każdego przykładowego wpisu.

**P: Czy mogę dostosować wygląd bloku GPSR?**
O: Tak, moduł zawiera plik `front.css`. W przypadku podstawowych zmian stylów (kolory, czcionki, odstępy) często można nadpisać te style w niestandardowym pliku CSS motywu bez bezpośredniej modyfikacji modułu. W przypadku bardziej zaawansowanych zmian układu może być konieczne dostosowanie szablonu `product-footer.tpl`. (Zobacz sekcję 7, aby uzyskać szczegółowe informacje dla programistów).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł GPSR Free jest zgodny z wzorcem MVC (Model-View-Controller) PrestaShop. Wykorzystuje niestandardowe kontrolery administracyjne do zarządzania danymi związanymi z GPSR (Producenci, Podmioty, Ostrzeżenia, Mapy Produktów) i wykorzystuje `ObjectModel` PrestaShop do trwałości danych. Wyświetlanie w front-office jest obsługiwane za pomocą szablonu haka. Moduł używa wzorca repozytorium (`GpsrFreeRepository`) do interakcji z bazą danych, promując czystszy kod i separację odpowiedzialności.

### 4.2 Kontrolery (`controllers/`)

Moduł wykorzystuje głównie kontrolery administracyjne Back-Office do zarządzania danymi. Nie ma dedykowanych kontrolerów front-office, ponieważ wyświetlanie w front-office jest obsługiwane bezpośrednio za pomocą haków.

-   **Kontrolery administracyjne Back-Office**:
    -   `controllers/admin/AdminGpsrFreeController.php`
        -   **Nazwa klasy:** `AdminGpsrFreeController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** GPSR Free (główny wpis w panelu)
        -   **Odpowiedzialność:** Służy jako główny punkt wejścia do administracji modułu, prawdopodobnie wyświetlając panel lub linki do innych specyficznych ekranów zarządzania. Nie zarządza konkretnym podmiotem, ale orkiestruje dostęp do innych kontrolerów.
    -   `controllers/admin/AdminGpsrFreeEntitiesController.php`
        -   **Nazwa klasy:** `AdminGpsrFreeEntitiesController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** Osoby odpowiedzialne w UE
        -   **Zarządzany podmiot:** `GpsrFreeEntity` (mapuje na tabelę `ps_gpsrfree_entity`)
        -   **Odpowiedzialność:** Zarządza tworzeniem, edycją, listowaniem i usuwaniem Osób odpowiedzialnych w UE (podmiotów). Zapewnia standardowy widok listy i formularza PrestaShop dla tych danych.
    -   `controllers/admin/AdminGpsrFreeManufacturersController.php`
        -   **Nazwa klasy:** `AdminGpsrFreeManufacturersController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** Producenci
        -   **Zarządzany podmiot:** `GpsrFreeManufacturer` (mapuje na tabelę `ps_gpsrfree_manufacturer`)
        -   **Odpowiedzialność:** Zarządza tworzeniem, edycją, listowaniem i usuwaniem producentów produktów. Zawiera logikę dla `is_eu_manufacturer`.
    -   `controllers/admin/AdminGpsrFreeMapController.php`
        -   **Nazwa klasy:** `AdminGpsrFreeMapController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** Mapa Produktów
        -   **Zarządzany podmiot:** `GpsrFreeProductMap` (mapuje na tabelę `ps_gpsrfree_product_map`)
        -   **Odpowiedzialność:** Zarządza mapowaniem między produktami, producentami, osobami odpowiedzialnymi w UE i ostrzeżeniami. Ten kontroler obsługuje złożone relacje między różnymi typami danych GPSR.
    -   `controllers/admin/AdminGpsrFreeWarningsController.php`
        -   **Nazwa klasy:** `AdminGpsrFreeWarningsController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** Ostrzeżenia
        -   **Zarządzany podmiot:** `GpsrFreeWarning` (mapuje na tabelę `ps_gpsrfree_warning`)
        -   **Odpowiedzialność:** Zarządza tworzeniem, edycją, listowaniem i usuwaniem ostrzeżeń dotyczących bezpieczeństwa. Obsługuje pola wielojęzyczne.
    -   `controllers/admin/GpsrFreeAdminController.php`
        -   **Nazwa klasy:** `GpsrFreeAdminController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** (Prawdopodobnie kontroler bazowy lub abstrakcyjny dla innych kontrolerów administracyjnych, lub starszy/zbędny punkt wejścia)
        -   **Odpowiedzialność:** Biorąc pod uwagę jego ogólną nazwę, może służyć jako klasa bazowa dla innych kontrolerów administracyjnych w module, dostarczając wspólne metody lub właściwości, lub może być starszym punktem wejścia.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy:** N/A
        -   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający bezpośredniemu listowaniu katalogów.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/GpsrFreeAdminUi.php`
    -   **Nazwa klasy:** `GpsrFreeAdminUi`
    -   **Odpowiedzialność:** Prawdopodobnie klasa pomocnicza do generowania lub zarządzania elementami interfejsu użytkownika w Back Office, takimi jak pola formularzy, konfiguracje list lub wspólne komponenty interfejsu administracyjnego. Pomaga standaryzować wygląd i działanie ekranów administracyjnych modułu.
-   `classes/GpsrFreeEntity.php`
    -   **Nazwa klasy:** `GpsrFreeEntity` (rozszerza `ObjectModel`)
    -   **Tabela bazy danych:** `ps_gpsrfree_entity`
    -   **Pola `$definition`:** Definiuje pola takie jak `name`, `address`.
    -   **Kluczowe metody publiczne:** Standardowe metody `ObjectModel` dla operacji CRUD. Reprezentuje Osobę odpowiedzialną w UE.
-   `classes/GpsrFreeManufacturer.php`
    -   **Nazwa klasy:** `GpsrFreeManufacturer` (rozszerza `ObjectModel`)
    -   **Tabela bazy danych:** `ps_gpsrfree_manufacturer`
    -   **Pola `$definition`:** Definiuje pola takie jak `name`, `address`, `is_eu_manufacturer`.
    -   **Kluczowe metody publiczne:** Standardowe metody `ObjectModel` dla operacji CRUD. Reprezentuje producenta produktu.
-   `classes/GpsrFreeProductMap.php`
    -   **Nazwa klasy:** `GpsrFreeProductMap` (rozszerza `ObjectModel`)
    -   **Tabela bazy danych:** `ps_gpsrfree_product_map`
    -   **Pola `$definition`:** Definiuje pola takie jak `id_product`, `id_manufacturer`, `id_entity`, `id_warning`. Ta tabela prawdopodobnie przechowuje relacje wiele do wielu lub bezpośrednie mapowania.
    -   **Kluczowe metody publiczne:** Standardowe metody `ObjectModel` dla operacji CRUD. Zarządza powiązaniami między produktami a danymi GPSR.
-   `classes/GpsrFreeRepository.php`
    -   **Nazwa klasy:** `GpsrFreeRepository`
    -   **Odpowiedzialność:** Implementuje wzorzec repozytorium. Ta klasa jest odpowiedzialna za wszystkie bezpośrednie interakcje z bazą danych, abstrahując je od kontrolerów i modeli. Zawiera metody do pobierania, wstawiania, aktualizowania i usuwania danych związanych z GPSR, często używając klasy `Db` PrestaShop. Zawierałaby metody takie jak `getMappedProductData($id_product)`.
-   `classes/GpsrFreeWarning.php`
    -   **Nazwa klasy:** `GpsrFreeWarning` (rozszerza `ObjectModel`)
    -   **Tabela bazy danych:** `ps_gpsrfree_warning`
    -   **Pola `$definition`:** Definiuje pola takie jak `text` (wielojęzyczne).
    -   **Kluczowe metody publiczne:** Standardowe metody `ObjectModel` dla operacji CRUD. Reprezentuje ostrzeżenie dotyczące bezpieczeństwa.
-   `classes/index.php`
    -   **Nazwa klasy:** N/A
    -   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający bezpośredniemu listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)
Dostarczony spis inwentarza wskazuje, że w module nie ma niestandardowych plików JavaScript. Sugeruje to, że moduł opiera się głównie na wbudowanych funkcjonalnościach JavaScript PrestaShop dla swoich formularzy administracyjnych i potencjalnie minimalnych interakcji w front-office, lub że wszelkie dynamiczne zachowania są obsługiwane po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `views/css/admin.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych Back-Office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Prawdopodobnie zapewnia specyficzną stylizację dla niestandardowych stron administracyjnych modułu, takich jak tabele list, elementy formularzy lub widżety panelu, aby zapewnić spójny wygląd w Panelu Administracyjnym PrestaShop.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Wszelkie niestandardowe klasy używane w szablonach administracyjnych modułu (np. `.gpsrfree-admin-panel`, `.gpsrfree-table`).
-   `views/css/front.css`
    -   **Zakres:** Stylizacja dla klientów w front-office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Stylizuje blok informacji GPSR wyświetlany na stronach produktów. Obejmowałoby to stylizację dla kontenera bloku, nagłówków, szczegółów producenta, szczegółów osoby odpowiedzialnej w UE i list ostrzeżeń.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Klasy takie jak `.gpsrfree-block`, `.gpsrfree-manufacturer`, `.gpsrfree-entity`, `.gpsrfree-warnings` itp. Programiści mogą celować w te klasy w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   `views/templates/hook/product-footer.tpl`
        -   **Hak:** `displayFooterProduct` (i potencjalnie `displayProductButtons` lub podobne, chociaż `displayFooterProduct` jest wyraźnie wymieniony).
        -   **Wyjście bloku wizualnego:** Ten szablon jest odpowiedzialny za renderowanie całego bloku informacji GPSR na stronie produktu. Będzie zawierał logikę wyświetlania szczegółów producenta, szczegółów osoby odpowiedzialnej w UE (jeśli dotyczy) oraz listy powiązanych ostrzeżeń, na podstawie danych pobranych z `GpsrFreeRepository` dla bieżącego produktu.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `views/templates/admin/configure.tpl`
        -   **Hak:** Renderowany przez metodę `getContent()` głównego pliku modułu `gpsrfree.php`.
        -   **Wyjście bloku wizualnego:** Ten szablon renderuje główny formularz konfiguracji modułu w Back Office, w szczególności przełącznik „Włącz blok GPSR”. Może również zawierać linki lub tekst wprowadzający do nawigacji do dedykowanych kontrolerów administracyjnych.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:
    -   `ps_gpsrfree_entity`: Przechowuje informacje o Osobach odpowiedzialnych w UE (id, nazwa, adres).
    -   `ps_gpsrfree_manufacturer`: Przechowuje informacje o producentach produktów (id, nazwa, adres, is_eu_manufacturer).
    -   `ps_gpsrfree_product_map`: Przechowuje relacje mapowania między produktami, producentami, osobami odpowiedzialnymi w UE i ostrzeżeniami (id_product, id_manufacturer, id_entity, id_warning). Ta tabela prawdopodobnie obsługuje relacje wiele do wielu, przechowując wiele wpisów dla jednego produktu, jeśli ma on wiele ostrzeżeń.
    -   `ps_gpsrfree_warning`: Przechowuje tekst ostrzeżeń dotyczących bezpieczeństwa (id, text - wielojęzyczne).
    -   `ps_configuration`: Ustawienia modułu, takie jak `GPSRFREE_ENABLED`, są przechowywane tutaj.

-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używane do ładowania CSS front-office (`front.css`) lub JavaScript (jeśli był obecny) globalnie. |
| `displayFooterProduct` | Na dole strony produktu, zazwyczaj poniżej głównej zawartości produktu. | Główny hak do renderowania bloku informacji GPSR (`product-footer.tpl`) na stronie produktu. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony Back Office. | Używane do ładowania CSS Back Office (`admin.css`) lub JavaScript dla ekranów administracyjnych modułu. |
| `displayAdminProductsExtra` | (Niejawne, często używane do dodawania zakładek/sekcji do strony edycji produktu) | Chociaż nie jest wyraźnie wymieniony jako zarejestrowany, moduły często używają tego lub podobnych haków do integracji ze stroną edycji produktu, jeśli mapowanie odbywało się bezpośrednio tam. Biorąc pod uwagę `AdminGpsrFreeMapController`, jest to prawdopodobnie oddzielny ekran. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | (Nie jest wyraźnie wymieniony jako zarejestrowany, ale powszechny dla modułów wchodzących w interakcje z zamówieniami. Jeśli jest obecny, służyłby do przetwarzania danych GPSR związanych z zamówieniem, co nie jest wskazane w opisie modułu.) |

*Uwaga: Dokumentacja modułu wymieniała `DisplayHeader`, `DisplayFooterProduct`, `displayHeader`, `DisplayBackOfficeHeader`, `displayFooterProduct`, `displayBackOfficeHeader`. Są to duplikaty ze względu na wrażliwość na wielkość liter, ale funkcjonalnie odnoszą się do tych samych haków.*

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu GPSR Free, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
