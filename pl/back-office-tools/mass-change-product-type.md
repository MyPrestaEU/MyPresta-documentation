---
title: "Masowa zmiana typu produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Masowa zmiana typu produktu” od MyPresta.eu."
sidebar:
  label: "Masowa zmiana typu produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Mass change product type na MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-change-product-type.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/mass-change-product-type/)
>
> ---


# Masowa zmiana typu produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Masowa zmiana typu produktu” zapewnia jeden, intuicyjny ekran konfiguracji w Panelu administracyjnym PrestaShop. Ten ekran prowadzi Cię przez wybór produktów, a następnie zastosowanie pożądanej zmiany typu produktu.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do konfiguracji modułu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Masowa zmiana typu produktu” i kliknij **„Konfiguruj”**.

Strona konfiguracji jest podzielona na dwie główne sekcje: **1. Wybierz produkty** i **2. Co zrobić z wybranymi produktami**.

#### Sekcja 1: Wybierz produkty

Ta sekcja pozwala zdefiniować, które produkty zostaną objęte masową zmianą. Możesz wybrać produkty na podstawie różnych kryteriów.

##### 1.1 Wybierz produkty według kategorii

- **Co robi to ustawienie:** Pozwala wybrać wszystkie produkty należące do jednej lub więcej określonych kategorii.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy kategorie są wybrane:* Tylko produkty z wybranych kategorii zostaną uwzględnione w zmianie typu.
  - *Gdy żadne kategorie nie są wybrane:* To kryterium nie będzie używane do filtrowania produktów.
- **Zalecana wartość:** Wybierz kategorie istotne dla Twojej operacji masowej zmiany.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz przekształcić wszystkie produkty w kategorii „Pobrane pliki cyfrowe” ze standardowych produktów na produkty wirtualne. Wybierzesz tutaj kategorię „Pobrane pliki cyfrowe”.

##### 1.2 Wybierz produkty według marki

- **Co robi to ustawienie:** Pozwala wybrać wszystkie produkty powiązane z jedną lub więcej określonymi markami (producentami).
- **Wpływ zmiany tego ustawienia:**
  - *Gdy marki są wybrane:* Tylko produkty od wybranych marek zostaną uwzględnione w zmianie typu.
  - *Gdy żadne marki nie są wybrane:* To kryterium nie będzie używane do filtrowania produktów.
- **Zalecana wartość:** Wybierz marki istotne dla Twojej operacji masowej zmiany.
- **Scenariusz / przykład dla sprzedawcy:** Zdecydowałeś się sprzedawać wszystkie produkty marki „Brand X” jako pakiety. Wybierzesz tutaj „Brand X”.

##### 1.3 Wybierz produkty według cechy

- **Co robi to ustawienie:** Pozwala wybrać produkty, które mają określoną cechę i, opcjonalnie, określoną wartość dla tej cechy.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy cecha (i opcjonalnie wartość) jest wybrana:* Tylko produkty pasujące do tego kryterium cechy zostaną uwzględnione.
  - *Gdy żadna cecha nie jest wybrana:* To kryterium nie będzie używane do filtrowania produktów.
- **Zalecana wartość:** Wybierz cechę i wartość, które precyzyjnie identyfikują produkty, które chcesz zmodyfikować.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz zmienić wszystkie produkty z cechą „Materiał” ustawioną na „Cyfrowy” na produkty wirtualne. Wybierzesz tutaj „Materiał”, a następnie „Cyfrowy”.

##### 1.4 Wybierz produkty według atrybutu

- **Co robi to ustawienie:** Pozwala wybrać produkty, które mają określony atrybut i, opcjonalnie, określoną wartość dla tego atrybutu. Jest to przydatne dla produktów z kombinacjami.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy atrybut (i opcjonalnie wartość) jest wybrany:* Tylko produkty pasujące do tego kryterium atrybutu zostaną uwzględnione.
  - *Gdy żaden atrybut nie jest wybrany:* To kryterium nie będzie używane do filtrowania produktów.
- **Zalecana wartość:** Wybierz atrybut i wartość, które precyzyjnie identyfikują produkty, które chcesz zmodyfikować.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz przekształcić wszystkie produkty, które mają atrybut „Rozmiar” ustawiony na „Do pobrania” na produkty wirtualne. Wybierzesz tutaj „Rozmiar”, a następnie „Do pobrania”.

##### 1.5 Wybierz produkty według frazy wyszukiwania

- **Co robi to ustawienie:** Pozwala wybrać produkty, których nazwy zawierają określoną frazę. Wykorzystuje narzędzie wyszukiwania do znajdowania produktów.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy wprowadzono frazę wyszukiwania:* Produkty, których nazwy pasują do frazy, zostaną dodane do wyboru.
  - *Gdy nie wprowadzono frazy wyszukiwania:* To kryterium nie będzie używane do filtrowania produktów.
- **Zalecana wartość:** Wprowadź jasną i zwięzłą frazę, aby zidentyfikować docelowe produkty.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz zmienić wszystkie produkty z „eBook” w nazwie na produkty wirtualne. Wpiszesz „eBook” w polu wyszukiwania.

##### 1.6 Lista wybranych produktów

- **Co robi to ustawienie:** Po zastosowaniu któregokolwiek z powyższych filtrów, w tym obszarze zostanie wyświetlona lista produktów, które spełniają Twoje kryteria. Możesz ręcznie usunąć produkty z tej listy, jeśli nie chcesz, aby zostały objęte zmianą.
- **Wpływ zmiany tego ustawienia:**
  - *Usunięcie produktu:* Ten konkretny produkt zostanie wykluczony z masowej zmiany typu.
  - *Pozostawienie produktów na liście:* Zostaną one uwzględnione w masowej zmianie typu.
- **Zalecana wartość:** Zawsze dokładnie przeglądaj tę listę, aby upewnić się, że wybrane są tylko zamierzone produkty.
- **Scenariusz / przykład dla sprzedawcy:** Wyszukałeś „eBook”, ale pojawiła się jedna fizyczna książka zatytułowana „Instrukcja czytnika eBooków”. Usuniesz ten konkretny produkt z listy.

#### Sekcja 2: Co zrobić z wybranymi produktami

Po wybraniu docelowych produktów, ta sekcja pozwala wybrać nowy typ produktu, który chcesz zastosować.

##### 2.1 Zmień typ produktu na:

- **Co robi to ustawienie:** To rozwijane menu pozwala wybrać nowy typ produktu dla wszystkich produktów zidentyfikowanych w Sekcji 1.
- **Opcje:**
  - **Produkt standardowy:** Zwykły produkt fizyczny.
  - **Pakiet produktów:** Zestaw innych produktów.
  - **Produkt z kombinacjami:** Produkt z wariantami (np. rozmiar, kolor).
  - **Produkt wirtualny:** Produkt niefizyczny (np. usługa, plik do pobrania).
- **Wpływ zmiany tego ustawienia:**
  - *Wybranie opcji:* Wszystkie wybrane produkty zostaną przekonwertowane na ten nowy typ.
- **Zalecana wartość:** Wybierz typ produktu, który dokładnie odzwierciedla nową naturę wybranych produktów.
- **Scenariusz / przykład dla sprzedawcy:** Wybrałeś wszystkie produkty „eBook”. Wybierzesz tutaj „Produkt wirtualny”.

##### 2.2 Przycisk Zastosuj zmiany

- **Co robi to ustawienie:** Ten przycisk wykonuje operację masowej zmiany.
- **Wpływ zmiany tego ustawienia:**
  - *Kliknięcie przycisku:* Moduł przetworzy wszystkie produkty z „Listy wybranych produktów” i zmieni ich typ produktu na ten wybrany w „Zmień typ produktu na:”. Zazwyczaj pojawi się komunikat potwierdzający.
- **Zalecana wartość:** Kliknij to tylko wtedy, gdy jesteś absolutnie pewien swojego wyboru produktów i pożądanego nowego typu.
- **Scenariusz / przykład dla sprzedawcy:** Po przejrzeniu wybranych eBooków i potwierdzeniu „Produkt wirtualny” jako nowego typu, klikasz „Zastosuj zmiany”, aby je wszystkie przekonwertować.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Wybierz produkty według kategorii** | Wybierz odpowiednie kategorie | Filtruje produkty według przypisanych im kategorii. |
| Konfiguracja modułu | **Wybierz produkty według marki** | Wybierz odpowiednie marki | Filtruje produkty według ich producenta/marki. |
| Konfiguracja modułu | **Wybierz produkty według cechy** | Wybierz cechę i wartość | Filtruje produkty według określonych cech i ich wartości. |
| Konfiguracja modułu | **Wybierz produkty według atrybutu** | Wybierz atrybut i wartość | Filtruje produkty według określonych atrybutów i ich wartości (dla kombinacji). |
| Konfiguracja modułu | **Wybierz produkty według frazy wyszukiwania** | Wprowadź termin wyszukiwania | Filtruje produkty według słów kluczowych w ich nazwie. |
| Konfiguracja modułu | **Lista wybranych produktów** | Dokładnie przejrzyj | Wyświetla wybrane produkty; umożliwia ręczne usunięcie przed przetworzeniem. |
| Konfiguracja modułu | **Zmień typ produktu na:** | Wybierz pożądany typ | Ustawia nowy typ produktu (Standardowy, Pakiet, Kombinacje, Wirtualny) dla wszystkich wybranych produktów. |
| Konfiguracja modułu | **Przycisk Zastosuj zmiany** | Kliknij, aby wykonać | Inicjuje masową zmianę typu produktu dla wszystkich wybranych produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zmieniłem typy produktów, ale nie widzę zmian w części front-office mojego sklepu.**
O: Po wprowadzeniu zmian w Panelu administracyjnym zawsze wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Pamięć podręczna Twojej przeglądarki również może wymagać wyczyszczenia (Ctrl+F5 lub Cmd+R).

**P: Niektóre produkty nie zostały zmienione, mimo że były w moim wyborze.**
O:

1.  **Sprawdź ponownie „Listę wybranych produktów”:** Czy przypadkowo usunąłeś je z listy przed zastosowaniem zmian?
2.  **Zweryfikuj kryteria:** Dokładnie sprawdź kryteria wyboru (kategoria, marka, cecha, atrybut, fraza wyszukiwania). Czy produkty rzeczywiście pasują do wszystkich wybranych filtrów?
3.  **Status produktu:** Upewnij się, że produkty są aktywne i nie są wyłączone.
4.  **Błędy:** Sprawdź, czy podczas procesu „Zastosuj zmiany” pojawiły się jakieś komunikaty o błędach.

**P: Czy mogę cofnąć zmiany wprowadzone przez ten moduł?**
O: Ten moduł wykonuje bezpośrednie aktualizacje bazy danych. W samym module nie ma przycisku „cofnij”. Dlatego **kopia zapasowa bazy danych przed użyciem jest kluczowa**. Jeśli musisz cofnąć zmiany, zazwyczaj przywróciłbyś bazę danych z kopii zapasowej wykonanej *przed* użyciem modułu. Alternatywnie, musiałbyś ponownie użyć modułu, aby zmienić typy produktów z powrotem na ich pierwotny stan, lub edytować je ręcznie.

**P: Czy ten moduł wpłynie na SEO lub adresy URL moich produktów?**
O: Zmiana typu produktu sama w sobie nie zmienia bezpośrednio jego przyjaznego dla SEO adresu URL. Jednakże, jeśli zmiana typu prowadzi do innych modyfikacji (np. usunięcie kombinacji, zmiana struktury produktu), zawsze warto sprawdzić strony produktów i potencjalnie ponownie wygenerować adresy URL (sekcja SEO i URL w PrestaShop), jeśli zauważysz jakiekolwiek problemy, choć jest to rzadkie w przypadku samej zmiany typu.

**P: Moduł nie wyświetla żadnych produktów, gdy używam frazy wyszukiwania.**
O:

1.  **Sprawdź błędy pisowni:** Upewnij się, że fraza wyszukiwania jest poprawnie napisana.
2.  **Wielkość liter:** Nazwy produktów mogą być wrażliwe na wielkość liter w zależności od konfiguracji bazy danych, spróbuj użyć innej wielkości liter.
3.  **Język:** Upewnij się, że wyszukujesz w prawidłowym języku, jeśli Twój sklep jest wielojęzyczny.
4.  **Konflikt modułów:** Tymczasowo wyłącz inne moduły związane z wyszukiwaniem, aby sprawdzić, czy nie ma konfliktów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów utrzymujących lub rozszerzających sklep PrestaShop za pomocą modułu „Masowa zmiana typu produktu”.

### 4.1 Przegląd architektury

Moduł „Masowa zmiana typu produktu” (`massptype`) to standardowy moduł PrestaShop działający głównie w Panelu administracyjnym. Wykorzystuje klasę `Module` PrestaShop i używa AJAX do filtrowania produktów oraz procesu masowej aktualizacji. Główna logika znajduje się w głównym pliku modułu, obsługując konfigurację, wybór produktów i masową aktualizację typów produktów. Integruje niestandardowe narzędzie wyszukiwania do wyboru produktów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani back-office w katalogach `controllers/admin` lub `controllers/front`. Cała logika jest obsługiwana w głównym pliku modułu `massptype.php` i jego metodzie `getContent()`, która działa jako główny punkt wejścia konfiguracji. Żądania AJAX są wysyłane za pośrednictwem pliku `ajax_products_list.php` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie definiuje niestandardowych klas `ObjectModel`. Bezpośrednio wchodzi w interakcje z podstawowymi metodami PrestaShop `Product` i `Product::updateProductFlags()` w celu modyfikacji typów produktów.

### 4.4 Zasoby JavaScript (`views/js/`)

- `massptype/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back-office (używany na stronie konfiguracji modułu).
  - **Cel:** Zapewnia podstawową logikę dla funkcji autouzupełniania wyszukiwania produktów. Prawdopodobnie obsługuje wysyłanie żądań AJAX do punktu końcowego `ajax_products_list.php` modułu w celu pobrania sugestii produktów na podstawie danych wprowadzonych przez użytkownika.
- `massptype/views/js/jquery.autocomplete.js`
  - **Zakres:** Back-office (używany na stronie konfiguracji modułu).
  - **Cel:** Wydaje się, że jest to wtyczka jQuery do funkcji autouzupełniania, prawdopodobnie zależność lub niestandardowa implementacja używana przez narzędzie wyszukiwania. Obsługuje aspekt interfejsu użytkownika wyświetlania sugestii i interakcji użytkownika.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `massptype/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Back-office (stylizuje elementy na stronie konfiguracji modułu).
  - **Cel:** Stylizuje rozwijane menu autouzupełniania, pola wprowadzania i potencjalnie listę wybranych produktów w interfejsie narzędzia wyszukiwania modułu. Programiści mogą nadpisać te style w swoim niestandardowym motywie Panelu administracyjnego lub dodając bardziej szczegółowe reguły CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `massptype/views/templates/hook/form.tpl`
    - **Hook:** Nie jest bezpośrednio podłączony w tradycyjnym sensie, ale renderowany przez `getContent()` głównego pliku modułu.
    - **Cel:** Jest to główny szablon formularza konfiguracji modułu w Panelu administracyjnym. Zawiera strukturę HTML do wyboru produktów według różnych kryteriów i wyboru nowego typu produktu.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `massptype/views/templates/admin/target_products.tpl`
    - **Cel:** Ten szablon jest prawdopodobnie używany do renderowania listy wybranych produktów po zastosowaniu kryteriów filtrowania. Dynamicznie aktualizuje się za pomocą AJAX, aby pokazać, które produkty zostaną objęte zmianą.
  - `massptype/views/templates/admin/wtd.tpl` (Co zrobić)
    - **Cel:** Ten szablon prawdopodobnie renderuje sekcję, w której użytkownik wybiera nowy typ produktu (Standardowy, Pakiet, Kombinacje, Wirtualny) oraz przycisk „Zastosuj zmiany”.
- **Inne szablony**:
  - `massptype/lib/searchTool/views/scripts.tpl`
    - **Cel:** Ten szablon prawdopodobnie zawiera kod JavaScript lub inicjalizuje funkcję autouzupełniania JavaScript dla narzędzia wyszukiwania produktów. Może być dołączony do `form.tpl`.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Moduł nie tworzy niestandardowych tabel bazy danych. Modyfikuje istniejące podstawowe tabele PrestaShop, w szczególności `ps_product` (i potencjalnie `ps_product_shop`), aktualizując pola `cache_is_pack`, `cache_has_attachments`, `is_virtual` i `cache_default_attribute`, które określają typ produktu. Ustawienia konfiguracji są przechowywane w `ps_configuration` przy użyciu standardowych kluczy (np. `_PS_MASS_PTYPE_...`).
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje żadnych tradycyjnych hooków wyświetlania front-office ani back-office. Jego funkcjonalność jest w całości zawarta w metodzie `getContent()` i wywołaniach AJAX.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionModuleInstall` | Podczas instalacji modułu | Ustawia początkową konfigurację. |
| `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści konfigurację. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Masowa zmiana typu produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
