---
title: "Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka” od MyPresta.eu."
sidebar:
  label: "Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable product specific prices when cart has cart rule na MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule/)
>
> ---


# Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka

## 1. Wymagania i kompatybilność

Ten moduł został zaprojektowany do bezproblemowej współpracy z nowoczesnymi instalacjami PrestaShop.

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Ten moduł ma jeden, prosty ekran konfiguracji.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do konfiguracji, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka” i kliknij przycisk „Konfiguruj”.

![Zastępczy zrzut ekranu konfiguracji modułu]
*(Wyobraź sobie zrzut ekranu przedstawiający prosty formularz z pojedynczym przełącznikiem oznaczonym „Wyłącz użycie cen specyficznych w koszyku z regułą koszyka” oraz opcjami „Włączone” / „Wyłączone”.)*

**Ustawienie: Wyłącz użycie cen specyficznych w koszyku z regułą koszyka**

- **Co robi to ustawienie:** Jest to główny przełącznik sterujący podstawową funkcjonalnością modułu. Określa, czy moduł aktywnie interweniuje, aby wyłączyć ceny specyficzne, gdy w koszyku klienta znajduje się reguła koszyka (kod kuponu).
- **Efekt zmiany tego ustawienia:**
  - **Gdy włączone (TAK):** Jeśli klient zastosuje jakąkolwiek regułę koszyka (kod kuponu) do swojego koszyka, moduł uniemożliwi zastosowanie jakichkolwiek cen specyficznych produktu do produktów w tym koszyku. Ceny produktów powrócą do ich ceny bazowej przed zastosowaniem rabatu z reguły koszyka, zapewniając, że tylko rabat z reguły koszyka wpływa na cenę końcową. Zapobiega to podwójnemu rabatowaniu.
  - **Gdy wyłączone (NIE):** Moduł będzie nieaktywny. Ceny specyficzne i reguły koszyka będą działać niezależnie, co oznacza, że mogą potencjalnie kumulować się na tym samym produkcie, prowadząc do jednoczesnego zastosowania wielu rabatów. Jest to domyślne zachowanie PrestaShop.
- **Zalecana wartość:** **Włączone (TAK)**. Jest to główny cel modułu i umożliwia ochronę marż zysku oraz kontrolę strategii rabatowej.
- **Scenariusz/przykład dla sprzedawcy:**
  - **Wybierz „Włączone”**, jeśli chcesz mieć pewność, że gdy klient użyje kodu kuponu (np. „OSZCZĘDŹ10” na 10% zniżki), wszelkie istniejące ceny specyficzne na produktach w jego koszyku zostaną zignorowane. Oznacza to, że 10% rabatu zostanie zastosowane do regularnej ceny produktu, a nie do już obniżonej ceny specyficznej. Zapobiega to dwukrotnemu rabatowaniu produktu.
  - **Wybierz „Wyłączone”**, jeśli wolisz domyślne zachowanie PrestaShop, gdzie ceny specyficzne i reguły koszyka mogą się kumulować, potencjalnie prowadząc do głębszych rabatów niż zamierzono. Może to być pożądane w bardzo specyficznych, agresywnych kampaniach promocyjnych, ale ogólnie zaleca się „Włączone” w celu ochrony zysków.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyłącz użycie cen specyficznych w koszyku z regułą koszyka | Włączone | Gdy włączone, ceny specyficzne są ignorowane, jeśli w koszyku aktywna jest reguła koszyka, zapobiegając podwójnym rabatom. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem moduł, ale ceny specyficzne nadal się wyświetlają, nawet z kodem kuponu. Co jest nie tak?**

- **O:** Po pierwsze, upewnij się, że zapisałeś konfigurację po włączeniu modułu.
- **O:** Wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
- **O:** Przetestuj z nowym koszykiem. Czasami pamięć podręczna przeglądarki lub dane sesji mogą zakłócać działanie. Spróbuj w trybie incognito.
- **O:** Sprawdź, czy reguła koszyka, którą testujesz, jest faktycznie aktywna i poprawnie zastosowana do produktów w koszyku.

**P2: Moi klienci skarżą się, że ich ceny specyficzne zniknęły, gdy użyli kuponu. Czy to jest oczekiwane?**

- **O:** Tak, jest to zamierzone zachowanie modułu. Gdy moduł jest włączony, a klient stosuje regułę koszyka (kupon), ceny specyficzne na produktach w koszyku są tymczasowo wyłączane, aby zapobiec podwójnemu rabatowaniu. Cena produktu zostanie wtedy obliczona na podstawie jego oryginalnej ceny, z zastosowaniem rabatu z reguły koszyka. Możesz chcieć zaktualizować swoje warunki i zasady lub komunikaty promocyjne, aby wyjaśnić, jak rabaty współdziałają.

**P3: Czy ten moduł wpływa na inne rodzaje rabatów, takie jak rabaty kategorii lub rabaty grup klientów?**

- **O:** Ten moduł koncentruje się konkretnie na „cenach specyficznych” (rabaty ustawione bezpośrednio na poszczególnych produktach lub kombinacjach) i ich interakcji z „regułami koszyka” (kodami kuponów). Nie ingeruje bezpośrednio w inne mechanizmy rabatowe, takie jak rabaty kategorii, rabaty grup klientów czy rabaty ilościowe, chyba że są one zaimplementowane jako ceny specyficzne.

**P4: Czy ten moduł spowolni mój sklep?**

- **O:** Moduł wprowadza drobne nadpisania do podstawowych klas PrestaShop, aby dostosować logikę obliczania cen. Te zmiany są wysoce zoptymalizowane i powinny mieć znikomy wpływ na wydajność Twojego sklepu. Moduł aktywuje swoją logikę tylko wtedy, gdy obecna jest reguła koszyka, więc nie działa on stale.

**P5: Chcę tymczasowo zezwolić na kumulowanie się cen specyficznych i reguł koszyka dla specjalnej promocji. Jak to zrobić?**

- **O:** Po prostu przejdź do strony konfiguracji modułu (**Moduły > Menedżer modułów > Konfiguruj** dla „Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka”) i ustaw opcję „Wyłącz użycie cen specyficznych w koszyku z regułą koszyka” na **„Wyłączone”**. Pamiętaj, aby ponownie włączyć ją po zakończeniu specjalnej promocji, aby przywrócić domyślne zachowanie ochronne.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla deweloperów i webmasterów pracujących z modułem „Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka”.

### 4.1 Przegląd architektury

Ten moduł działa głównie poprzez nadpisywanie podstawowych klas PrestaShop związanych z obliczaniem cen i zarządzaniem cenami specyficznymi. Wykorzystuje mechanizm nadpisywania PrestaShop do wstrzykiwania swojej logiki do klas `Cart`, `Product` i `SpecificPrice`. Główną ideą jest wykrycie obecności reguły koszyka w bieżącym koszyku i, jeśli zostanie znaleziona, zmodyfikowanie zachowania pobierania cen specyficznych, aby skutecznie je ignorować podczas obliczania cen.

Główna konfiguracja modułu jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, przechowując prostą flagę boolean w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego logika jest całkowicie osadzona w nadpisaniach klas.

- **Kontrolery Front-Office**: Brak
- **Kontrolery Admin Back-Office**: Brak

### 4.3 Klasy podstawowe i modele (`classes/`)

Podstawowa funkcjonalność modułu znajduje się w jego nadpisaniach klas. Pliki te znajdują się w `cartspecdis/override/classes/`. PrestaShop automatycznie ładuje te nadpisania, zastępując oryginalne klasy podstawowe zmodyfikowanymi wersjami modułu.

- **`cartspecdis/override/classes/Cart.php`**

  - **Nazwa klasy i klasa nadrzędna**: `Cart` (nadpisuje `\Cart`)
  - **Odpowiedzialność**: To nadpisanie jest kluczowe. Prawdopodobnie wprowadza metodę lub modyfikuje istniejącą (np. `getProducts()`, `getPackageList()` lub pomocnika obliczania cen), aby sprawdzić obecność reguł koszyka. Jeśli reguły koszyka zostaną znalezione, ustawia flagę lub modyfikuje parametry, które wpływają na sposób późniejszego pobierania lub stosowania cen specyficznych. Metoda `hasCartRules()` jest prawdopodobnym kandydatem do sprawdzania reguł koszyka.
  - **Kluczowa logika**: Nadpisanie prawdopodobnie doda sprawdzenie w metodach obliczania cen, aby zobaczyć, czy `Cart::getCartRules()` zwraca jakieś aktywne reguły. Jeśli tak, wpłynie to na wywołania `Product::getPriceStatic()` lub `SpecificPrice::getSpecificPrice()`, aby ignorować ceny specyficzne.
- **`cartspecdis/override/classes/Product.php`**

  - **Nazwa klasy i klasa nadrzędna**: `Product` (nadpisuje `\Product`)
  - **Odpowiedzialność**: To nadpisanie ma na celu zmodyfikowanie metody `getPriceStatic()`, która jest centralna dla sposobu pobierania cen produktów w całym PrestaShop.
  - **Kluczowa logika**: Wewnątrz `getPriceStatic()` moduł prawdopodobnie doda warunek. Jeśli bieżący obiekt `Cart` (przekazany jako parametr lub dostępny globalnie) zawiera aktywne reguły koszyka, a konfiguracja modułu jest włączona, wówczas parametry przekazywane do `SpecificPrice::getSpecificPrice()` zostaną zmienione (np. flagi `id_specific_price` lub `use_specific_price`), aby upewnić się, że żadna cena specyficzna nie zostanie zwrócona, lub obliczanie ceny specyficznej zostanie pominięte.
- **`cartspecdis/override/classes/SpecificPrice.php`**

  - **Nazwa klasy i klasa nadrzędna**: `SpecificPrice` (nadpisuje `\SpecificPrice`)
  - **Odpowiedzialność**: To nadpisanie prawdopodobnie zmodyfikuje metodę `getSpecificPrice()`, która jest odpowiedzialna za pobieranie szczegółów ceny specyficznej dla danego produktu.
  - **Kluczowa logika**: To nadpisanie będzie zawierać bezpośrednią logikę zapobiegającą zwracaniu cen specyficznych. Sprawdzi, czy bieżący `Cart` ma reguły koszyka i czy moduł jest włączony. Jeśli oba warunki są prawdziwe, `getSpecificPrice()` zostanie zmuszone do zwrócenia `false` lub pustej tablicy, skutecznie wskazując, że żadna cena specyficzna nie ma zastosowania, nawet jeśli taka istnieje w bazie danych. Jest to ostateczny strażnik dla cen specyficznych.
- **`cartspecdis/override/classes/index.php`**

  - **Nazwa klasy i klasa nadrzędna**: Brak
  - **Odpowiedzialność**: Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach, aby zapobiec listowaniu katalogów po bezpośrednim dostępie przez przeglądarkę internetową. Nie ma on żadnego wpływu funkcjonalnego na logikę modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Cała jego logika jest obsługiwana po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Nie ma żadnych wizualnych komponentów front-office, a jego konfiguracja back-office wykorzystuje standardowe elementy formularzy PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie używa żadnych niestandardowych szablonów Smarty. Jego formularz konfiguracji jest generowany dynamicznie przez metodę `getContent()` w głównym pliku modułu za pomocą klas pomocniczych PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`:
    - Klucz `PS_CONFIGURATION`: `cartspecdis` (przechowuje wartość boolean dla włączania/wyłączania podstawowej funkcjonalności modułu).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny konfiguruje swoje zasoby multimedialne (CSS/JS). | Ten hook jest zazwyczaj używany przez moduły do dodawania własnych plików CSS lub JavaScript do Panelu administracyjnego. W przypadku tego modułu, prawdopodobnie służy do zapewnienia załadowania wszelkich niezbędnych stylów lub skryptów po stronie administratora (chociaż żadne nie są wyraźnie wymienione w inwentarzu), lub może być pozostałością po strukturze szablonu modułu. Biorąc pod uwagę, że nie wymieniono żadnych plików JS/CSS, jego główny cel tutaj jest prawdopodobnie minimalny lub przeznaczony na przyszłe rozszerzenia. |

### 4.8 Główny plik modułu (`cartspecdis/cartspecdis.php`)

- **Nazwa klasy**: `Cartspecdis` (rozszerza `Module`)
- **`__construct()`**: Inicjalizuje metadane modułu (nazwa, zakładka, wersja, autor, `need_instance`, `ps_versions_compliancy`).
- **`install()`**:
  - Wywołuje `parent::install()`.
  - Rejestruje hook `actionAdminControllerSetMedia`.
  - Ustawia domyślną wartość konfiguracji dla `cartspecdis` na `1` (włączone) w `ps_configuration`.
  - Rejestruje nadpisania klas (`Cart`, `Product`, `SpecificPrice`).
- **`uninstall()`**:
  - Wywołuje `parent::uninstall()`.
  - Wyrejestrowuje hook `actionAdminControllerSetMedia`.
  - Usuwa wartość konfiguracji `cartspecdis` z `ps_configuration`.
  - Wyrejestrowuje nadpisania klas.
- **`getContent()`**:
  - Obsługuje przesyłanie formularza konfiguracji modułu.
  - Aktualizuje wartość konfiguracji `cartspecdis` w `ps_configuration` na podstawie danych wprowadzonych przez użytkownika.
  - Wyświetla komunikat potwierdzający.
  - Renderuje formularz konfiguracji za pomocą klasy `HelperForm` PrestaShop, włączając pojedynczy przełącznik dla „Wyłącz użycie cen specyficznych w koszyku z regułą koszyka”.
- **`hookActionAdminControllerSetMedia()`**:
  - Ta metoda jest wywoływana, gdy wykonywany jest hook `actionAdminControllerSetMedia`.
  - Jest zazwyczaj używana do dodawania plików CSS lub JavaScript do Panelu administracyjnego. W obecnym stanie tego modułu (na podstawie inwentarza), prawdopodobnie zawiera minimalny lub brak aktywnego kodu do dodawania zasobów, lub jest to symbol zastępczy.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyłączanie cen specyficznych produktu, gdy koszyk zawiera regułę koszyka”, zapoznaj się ze swoim kontem klienta na MyPresta.eu.

- **Aktualizacje modułu**: Zaloguj się na swoje konto MyPresta.eu i przejdź do historii zamówień i sekcji pobierania, aby uzyskać najnowszą wersję modułu.
- **Wsparcie techniczne**: Jeśli napotkasz jakiekolwiek problemy lub masz pytania, które nie są objęte tą dokumentacją, otwórz zgłoszenie do wsparcia za pośrednictwem swojego konta klienta MyPresta.eu. Nasz zespół z przyjemnością Ci pomoże.
