---
title: "Produkty na stronach CMS - Instrukcja obsługi i konfiguracji dla sprzedawcy"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Produkty na stronach CMS” od MyPresta.eu."
sidebar:
  label: "Produkty na stronach CMS - Instrukcja obsługi i konfiguracji dla sprzedawcy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Products on CMS pages na MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-on-cms-pages.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/products-on-cms-pages/)
>
> ---


# Produkty na stronach CMS

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Produkty na stronach CMS” w Menedżerze modułów. Zobaczysz główny ekran konfiguracji.

#### **Ukryj produkty i shortcode’y**

- **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł przetwarza i wyświetla produkty z shortcode’ów umieszczonych na stronach CMS. Wpływa również na to, czy same shortcode’y są widoczne dla klientów, jeśli moduł ich nie przetwarza.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł *nie* będzie przetwarzał shortcode’ów. Zamiast wyświetlać listy produktów, shortcode’y (np. `[products ids="1,2,3"]`) będą ukryte przed widokiem klienta w front office. Jest to przydatne, jeśli chcesz tymczasowo wyłączyć wyświetlanie produktów bez usuwania shortcode’ów z treści CMS.
  - *Gdy wyłączone (NIE):* Moduł będzie aktywnie szukał i przetwarzał shortcode’y na stronach CMS. Zastąpi je odpowiednimi listami produktów, czyniąc Twoje produkty widocznymi dla klientów.
- **Zalecana wartość:** **NIE** (chyba że chcesz specjalnie ukryć listy produktów i shortcode’y).
- **Scenariusz / przykład dla sprzedawcy:**
  - Skonfigurowałeś kilka stron CMS z shortcode’ami produktów do promocji sezonowej. Gdy promocja się zakończy, zamiast ręcznie edytować każdą stronę CMS, aby usunąć shortcode’y, możesz po prostu włączyć „Ukryj produkty i shortcode’y”, aby natychmiast ukryć wszystkie listy produktów z tych stron. Gdy rozpocznie się następna promocja, wyłączasz to ponownie.

### 2.2 Jak używać shortcode’ów na stronach CMS

Ten moduł nie ma dedykowanych ekranów administracyjnych poza główną konfiguracją. Jego podstawowa funkcjonalność jest kontrolowana przez „shortcode’y”, które wstawiasz bezpośrednio do treści strony CMS.

**Aby dodać produkty do strony CMS:**

1. Przejdź do **Parametry sklepu > Strony CMS** w Panelu administracyjnym PrestaShop.
2. Edytuj istniejącą stronę CMS lub utwórz nową.
3. W głównym edytorze treści (zazwyczaj edytorze tekstu sformatowanego, takim jak TinyMCE) możesz wpisać lub wkleić shortcode’y.

**Dostępne shortcode’y:**

- **Wyświetl konkretne produkty według ID:**

  - `[products ids="1,2,3,4"]`
  - **Cel:** Ten shortcode pozwala wyświetlić listę konkretnych produktów według ich unikalnych numerów ID. ID produktów znajdziesz w Panelu administracyjnym w **Katalog > Produkty**.
  - **Przykład:** Jeśli chcesz wyświetlić Produkt A (ID 1), Produkt B (ID 2) i Produkt C (ID 3), użyjesz `[products ids="1,2,3"]`.
- **Wyświetl produkty z konkretnej kategorii:**

  - `[products category="5"]`
  - **Cel:** Ten shortcode wyświetla wszystkie produkty należące do konkretnej kategorii. ID kategorii znajdziesz w Panelu administracyjnym w **Katalog > Kategorie**, edytując kategorię i patrząc na URL lub kolumnę „ID” na liście kategorii.
  - **Przykład:** Aby wyświetlić wszystkie produkty z kategorii „Elektronika” (zakładając, że jej ID to 5), użyjesz `[products category="5"]`.
- **Wyświetl produkty od konkretnego producenta/marki:**

  - `[products manufacturer="1"]`
  - **Cel:** Ten shortcode wyświetla wszystkie produkty powiązane z konkretnym producentem lub marką. ID producentów można znaleźć w **Katalog > Marki i dostawcy > Marki**.
  - **Przykład:** Aby wyświetlić wszystkie produkty od „Apple” (zakładając, że jej ID to 1), użyjesz `[products manufacturer="1"]`.
- **Wyświetl nowe produkty:**

  - `[products new="5"]`
  - **Cel:** Ten shortcode wyświetla najnowsze produkty dodane do Twojego sklepu. Liczba „5” wskazuje, ile nowych produktów chcesz wyświetlić.
  - **Przykład:** Aby wyświetlić 5 najnowszych produktów, użyj `[products new="5"]`.
- **Wyświetl najlepiej sprzedające się produkty:**

  - `[products bestseller="5"]`
  - **Cel:** Ten shortcode wyświetla Twoje najlepiej sprzedające się produkty. Liczba „5” wskazuje, ile najlepiej sprzedających się produktów chcesz wyświetlić.
  - **Przykład:** Aby wyświetlić 5 najlepiej sprzedających się produktów, użyj `[products bestseller="5"]`.
- **Wyświetl produkty w promocji:**

  - `[products sale="5"]`
  - **Cel:** Ten shortcode wyświetla produkty, które są aktualnie w promocji. Liczba „5” wskazuje, ile produktów w promocji chcesz wyświetlić.
  - **Przykład:** Aby wyświetlić 5 produktów, które są aktualnie przecenione, użyj `[products sale="5"]`.
- **Wyświetl polecane produkty (ze strony głównej):**

  - `[products featured="5"]`
  - **Cel:** Ten shortcode wyświetla produkty oznaczone jako „polecane” na Twojej stronie głównej (zazwyczaj kontrolowane przez moduł „Polecane produkty”). Liczba „5” wskazuje, ile polecanych produktów chcesz wyświetlić.
  - **Przykład:** Aby wyświetlić 5 polecanych produktów, użyj `[products featured="5"]`.

**Ważne uwagi:**

- Możesz łączyć shortcode’y na tej samej stronie, ale każdy shortcode wygeneruje własną listę produktów.
- Upewnij się, że nie ma dodatkowych spacji ani literówek w nawiasach shortcode’a `[]`.
- Po dodaniu shortcode’ów zapisz stronę CMS. Produkty pojawią się w front office automatycznie (chyba że masz włączone „Ukryj produkty i shortcode’y” w konfiguracji modułu).

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Ukryj produkty i shortcode’y | NIE | Kontroluje, czy listy produktów z shortcode’ów są wyświetlane (NIE) czy ukryte (TAK) na stronach CMS. |
| Edytor strony CMS | `[products ids="1,2,3"]` | N/A | Wyświetla konkretne produkty według ich ID. |
| Edytor strony CMS | `[products category="5"]` | N/A | Wyświetla wszystkie produkty z konkretnej kategorii. |
| Edytor strony CMS | `[products manufacturer="1"]` | N/A | Wyświetla wszystkie produkty od konkretnego producenta. |
| Edytor strony CMS | `[products new="5"]` | N/A | Wyświetla 5 najnowszych produktów. |
| Edytor strony CMS | `[products bestseller="5"]` | N/A | Wyświetla 5 najlepiej sprzedających się produktów. |
| Edytor strony CMS | `[products sale="5"]` | N/A | Wyświetla 5 produktów aktualnie w promocji. |
| Edytor strony CMS | `[products featured="5"]` | N/A | Wyświetla 5 polecanych produktów ze strony głównej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje produkty nie wyświetlają się na stronie CMS, ale shortcode’y są widoczne.**
O: Sprawdź stronę konfiguracji modułu (**Moduły > Menedżer modułów > Konfiguruj** dla „Produkty na stronach CMS”). Upewnij się, że „Ukryj produkty i shortcode’y” jest ustawione na **NIE**. Jeśli jest ustawione na TAK, moduł ukryje produkty i same shortcode’y. Sprawdź również składnię shortcode’a pod kątem literówek lub brakujących cudzysłowów.

**P: Moje produkty nie wyświetlają się, ani shortcode’y (tylko pusta przestrzeń).**
O: Zazwyczaj oznacza to, że moduł jest aktywny i próbuje przetwarzać shortcode’y, ale napotyka problem.
1. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
2. **Sprawdź ID produktów/kategorii:** Upewnij się, że ID używane w `[products ids="..."]`, `[products category="..."]` lub `[products manufacturer="..."]` są poprawne i odpowiadają istniejącym, aktywnym produktom/kategoriom/producentom w Twoim sklepie.
3. **Widoczność produktu:** Upewnij się, że produkty, które próbujesz wyświetlić, są aktywne i widoczne w Twoim sklepie (nie wyłączone, niedostępne w magazynie, jeśli zarządzanie zapasami jest ścisłe, lub ustawione na „ukryte”).

**P: Produkty się pojawiają, ale nie wyglądają dobrze z moim stylem motywu.**
O: Moduł używa podstawowego stylu, ale CSS Twojego motywu może go nadpisywać lub z nim kolidować.
1. **Dostosowanie motywu:** Większość motywów ma opcje niestandardowego CSS. Ty lub Twój webmaster możecie dodać niestandardowe reguły CSS, aby celować w listy produktów generowane przez ten moduł.
2. **Skontaktuj się z deweloperem motywu:** Jeśli nie masz pewności, skontaktuj się z deweloperem motywu, aby uzyskać porady, jak najlepiej stylizować siatki produktów.
3. **Skontaktuj się z pomocą techniczną MyPresta.eu:** Jeśli podejrzewasz problem ze stylem specyficznym dla modułu, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Czy mogę używać wielu shortcode’ów na tej samej stronie CMS?**
O: Tak, możesz używać dowolnej liczby różnych shortcode’ów na jednej stronie CMS. Każdy shortcode wygeneruje własną, oddzielną listę produktów.

**P: Czy ten moduł obsługuje sklepy wielojęzyczne?**
O: Tak, moduł współpracuje z funkcjami wielojęzycznymi PrestaShop. Nazwy i opisy produktów wyświetlane będą w języku wybranym przez klienta, tak jak na zwykłych stronach produktów lub kategorii. Same shortcode’y (`[products ids="..."]`) pozostają takie same we wszystkich językach.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Produkty na stronach CMS” działa głównie poprzez nadpisywanie podstawowego `CmsController`, aby przechwytywać i przetwarzać treści przed ich renderowaniem użytkownikowi. Wykorzystuje wyrażenia regularne do znajdowania konkretnych shortcode’ów w treści strony CMS i zastępuje je dynamicznie generowanymi listami produktów. Dane produktów są pobierane za pomocą metod PrestaShop `Product::getProducts` i `Product::getProductsProperties`, a następnie renderowane za pomocą szablonów Smarty.

### 4.2 Kontrolery (`controllers/`)

Ten moduł wykorzystuje nadpisanie do rozszerzenia podstawowej funkcjonalności PrestaShop.

- **Kontrolery Front-Office**:

  - `cmsproducts/override/controllers/front/CmsController.php`
    - **Nazwa klasy i klasa nadrzędna**: `CmsController` (nadpisuje `CmsControllerCore`)
    - **Odpowiedzialność**: To jest rdzeń funkcjonalności modułu. Nadpisuje metodę `initContent()` standardowego `CmsController`. Wewnątrz `initContent()` pobiera treść strony CMS, skanuje ją w poszukiwaniu zdefiniowanych shortcode’ów (np. `[products ids="...]`), przetwarza te shortcode’y, pobierając odpowiednie dane produktów, a następnie zastępuje shortcode’y renderowanym kodem HTML produktów, zanim treść strony zostanie wyświetlona. Zapewnia również załadowanie CSS modułu.
  - `cmsproducts/override/controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna**: N/A (pusty plik)
    - **Odpowiedzialność**: Jest to standardowy pusty plik `index.php` umieszczony w podkatalogach, aby zapobiec listowaniu katalogów, co jest powszechną praktyką bezpieczeństwa. Nie ma wpływu funkcjonalnego na logikę modułu.
- **Kontrolery administracyjne Back-Office**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Wykorzystuje on istniejące podstawowe klasy PrestaShop, takie jak `Product`, `Category`, `Manufacturer`, `Context`, `Tools` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

W tym module nie ma niestandardowych plików JavaScript. Cała funkcjonalność jest obsługiwana po stronie serwera za pośrednictwem PHP.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera dwa pliki CSS do stylizacji list produktów. Są one ładowane za pomocą haka `actionAdminControllerSetMedia` (dla kontekstu back-office, chociaż nadpisanie obsługuje ładowanie front-office).

- `cmsproducts/cmsproducts.css`
  - **Zakres**: Stylizacja dla klienta w front-office.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Zawiera ogólną stylizację dla siatki/listy produktów generowanej przez shortcode’y. Obejmowałoby to style dla kontenerów produktów, obrazów, nazw, cen i potencjalnie przycisków „Dodaj do koszyka”, aby zapewnić spójny wygląd.
  - **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać**: Prawdopodobnie celuje w klasy takie jak `.cmsproducts-product-list`, `.cmsproducts-product-item`, `.cmsproducts-product-image`, `.cmsproducts-product-name`, `.cmsproducts-product-price`.
- `cmsproducts/css.css`
  - **Zakres**: Stylizacja dla klienta w front-office.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Podobnie jak `cmsproducts.css`, ten plik prawdopodobnie dostarcza dodatkowe lub specyficzne reguły stylizacji dla wyświetlania produktów, potencjalnie dla responsywności lub specyficznych dostosowań układu.
  - **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać**: Podobnie jak `cmsproducts.css`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje szablony Smarty do renderowania list produktów.

- **Szablony haków (`views/templates/hook/`)**: Brak jawnie zdefiniowanych jako szablony haków. Szablony są renderowane bezpośrednio przez nadpisanie `CmsController`.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak.
- **Szablony front-office (`views/templates/front/`)**:
  - `cmsproducts/html.tpl`
    - **Cel**: Ten szablon prawdopodobnie służy jako opakowanie lub ogólny kontener dla list produktów. Może zawierać podstawową strukturę HTML otaczającą elementy produktów.
  - `cmsproducts/products-carousel.tpl`
    - **Cel**: Ten szablon jest przeznaczony do renderowania produktów w formacie karuzeli lub suwaka. Zawierałby niezbędną strukturę HTML i potencjalnie inicjalizację JavaScript dla karuzeli produktów. Ten szablon jest prawdopodobnie używany, gdy konkretny parametr shortcode’a lub ustawienie modułu (nieujawnione w bieżącej konfiguracji) implikuje wyświetlanie karuzeli.
  - `cmsproducts/products.tpl`
    - **Cel**: To jest główny szablon do renderowania standardowej siatki lub listy produktów. Iteruje przez dane produktów przekazane z kontrolera PHP i wyświetla indywidualne szczegóły produktu (obraz, nazwa, cena, przycisk dodania do koszyka itp.). Jest to najczęściej używany szablon dla shortcode’ów `[products ...]`.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration`.
  - Wpisy `ps_configuration`:
    - `mypresta_updates`: Przechowuje informacje związane z aktualizacjami modułu z MyPresta.eu.
    - `cmsproducts_hide`: Przechowuje wartość ustawienia „Ukryj produkty i shortcode’y” (1 dla włączonego/TAK, 0 dla wyłączonego/NIE).
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Chociaż wymieniony, główne ładowanie CSS dla front office jest obsługiwane przez nadpisanie `CmsController`. Ten hak może być używany do potencjalnej przyszłej stylizacji po stronie administratora lub jeśli moduł miał kontroler administracyjny. |

Główna funkcjonalność przetwarzania shortcode’ów i renderowania produktów jest osiągana poprzez nadpisanie `CmsController`, które bezpośrednio manipuluje treścią przed wyświetleniem, zamiast polegać na konkretnym haku front-office do wstrzykiwania treści.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Produkty na stronach CMS”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i deweloperom w wszelkich pytaniach lub problemach związanych z modułem.
